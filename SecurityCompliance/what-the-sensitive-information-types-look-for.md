---
title: Tipi di informazioni riservate disponibili da cercare
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 6/29/2018
audience: Admin
search.appverid: MET150
ms.topic: reference
f1_keywords:
- ms.o365.cc.UnifiedDLPRuleContainsSensitiveInformation
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
description: La prevenzione della perdita di dati (DLP) nel centro &amp; sicurezza e conformità di Office 365 include 80 tipi di informazioni riservate pronte per l'uso nei criteri DLP. In questo argomento vengono elencati tutti questi tipi di informazioni riservate e illustrata la ricerca eseguita dal criterio DLP quando rileva ciascun tipo di informazioni.
ms.openlocfilehash: dc2958af5b64f9e9318faab5d55ed340404f1857
ms.sourcegitcommit: 0d5a863f48914eeaaf29f7d2a2022618de186247
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2019
ms.locfileid: "34077552"
---
# <a name="what-the-sensitive-information-types-look-for"></a><span data-ttu-id="2500b-104">Tipi di informazioni riservate disponibili da cercare</span><span class="sxs-lookup"><span data-stu-id="2500b-104">What the sensitive information types look for</span></span>

<span data-ttu-id="2500b-105">La prevenzione della perdita di dati (DLP) nel centro &amp; sicurezza e conformità di Office 365 include numerosi tipi di informazioni riservate pronte per l'uso nei criteri DLP.</span><span class="sxs-lookup"><span data-stu-id="2500b-105">Data loss prevention (DLP) in the Office 365 Security &amp; Compliance Center includes many sensitive information types that are ready for you to use in your DLP policies.</span></span> <span data-ttu-id="2500b-106">In questo argomento vengono elencati tutti questi tipi di informazioni riservate e illustrata la ricerca eseguita dal criterio DLP quando rileva ciascun tipo di informazioni.</span><span class="sxs-lookup"><span data-stu-id="2500b-106">This topic lists all of these sensitive information types and shows what a DLP policy looks for when it detects each type.</span></span> <span data-ttu-id="2500b-107">Una tipologia di informazioni riservate viene definita da un modello identificato da un'espressione regolare o da una funzione.</span><span class="sxs-lookup"><span data-stu-id="2500b-107">A sensitive information type is defined by a pattern that can be identified by a regular expression or a function.</span></span> <span data-ttu-id="2500b-108">Inoltre, è possibile utilizzare elementi probatori, ad esempio, parole chiave e checksum per identificare una tipologia di informazioni riservate.</span><span class="sxs-lookup"><span data-stu-id="2500b-108">In addition, corroborative evidence such as keywords and checksums can be used to identify a sensitive information type.</span></span> <span data-ttu-id="2500b-109">In questa procedura di valutazione vengono usati anche il livello di probabilità e la prossimità.</span><span class="sxs-lookup"><span data-stu-id="2500b-109">Confidence level and proximity are also used in the evaluation process.</span></span>
  
## <a name="aba-routing-number"></a><span data-ttu-id="2500b-110">Numero di registrazione ABA</span><span class="sxs-lookup"><span data-stu-id="2500b-110">ABA Routing Number</span></span>

### <a name="format"></a><span data-ttu-id="2500b-111">Formato</span><span class="sxs-lookup"><span data-stu-id="2500b-111">Format</span></span>

<span data-ttu-id="2500b-112">9 cifre formattate o meno</span><span class="sxs-lookup"><span data-stu-id="2500b-112">9 digits which may be in a formatted or unformatted pattern</span></span>

### <a name="pattern"></a><span data-ttu-id="2500b-113">Modello</span><span class="sxs-lookup"><span data-stu-id="2500b-113">Pattern</span></span>

<span data-ttu-id="2500b-114">Formattato</span><span class="sxs-lookup"><span data-stu-id="2500b-114">Formatted:</span></span>
- <span data-ttu-id="2500b-115">Quattro cifre che iniziano con 0, 1, 2, 3, 6, 7 o 8</span><span class="sxs-lookup"><span data-stu-id="2500b-115">Four digits beginning with 0, 1, 2, 3, 6, 7, or 8</span></span>
- <span data-ttu-id="2500b-116">Una lineetta</span><span class="sxs-lookup"><span data-stu-id="2500b-116">A hyphen</span></span>
- <span data-ttu-id="2500b-117">Quattro cifre</span><span class="sxs-lookup"><span data-stu-id="2500b-117">Four digits</span></span>
- <span data-ttu-id="2500b-118">Una lineetta</span><span class="sxs-lookup"><span data-stu-id="2500b-118">A hyphen</span></span>
- <span data-ttu-id="2500b-119">Una cifra</span><span class="sxs-lookup"><span data-stu-id="2500b-119">A digit</span></span>

<span data-ttu-id="2500b-120">Non formattato: 9 cifre consecutive che iniziano con 0, 1, 2, 3, 6, 7 o 8</span><span class="sxs-lookup"><span data-stu-id="2500b-120">Unformatted: 9 consecutive digits beginning with 0, 1, 2, 3, 6, 7, or 8</span></span> 

### <a name="checksum"></a><span data-ttu-id="2500b-121">Checksum</span><span class="sxs-lookup"><span data-stu-id="2500b-121">Checksum</span></span>

<span data-ttu-id="2500b-122">No</span><span class="sxs-lookup"><span data-stu-id="2500b-122">No</span></span>

### <a name="definition"></a><span data-ttu-id="2500b-123">Definizione</span><span class="sxs-lookup"><span data-stu-id="2500b-123">Definition</span></span>

<span data-ttu-id="2500b-124">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="2500b-124">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2500b-125">La funzione Func_aba_routing restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="2500b-125">The function Func_aba_routing finds content that matches the pattern.</span></span>
- <span data-ttu-id="2500b-126">Viene trovata una parola chiave da Keyword_ABA_Routing.</span><span class="sxs-lookup"><span data-stu-id="2500b-126">A keyword from Keyword_ABA_Routing is found.</span></span>

```
<!-- ABA Routing Number -->
<Entity id="cb353f78-2b72-4c3c-8827-92ebe4f69fdf" patternsProximity="300" recommendedConfidence="75">
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_aba_routing" />
        <Match idRef="Keyword_ABA_Routing" />
      </Pattern>
 </Entity>
```


### <a name="keywords"></a><span data-ttu-id="2500b-127">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="2500b-127">Keywords</span></span>

#### <a name="keywordabarouting"></a><span data-ttu-id="2500b-128">Keyword_ABA_Routing</span><span class="sxs-lookup"><span data-stu-id="2500b-128">Keyword_ABA_Routing</span></span>

- <span data-ttu-id="2500b-129">ABA</span><span class="sxs-lookup"><span data-stu-id="2500b-129">aba</span></span>
- <span data-ttu-id="2500b-130">aba #</span><span class="sxs-lookup"><span data-stu-id="2500b-130">aba #</span></span>
- <span data-ttu-id="2500b-131">aba routing #</span><span class="sxs-lookup"><span data-stu-id="2500b-131">aba routing #</span></span>
- <span data-ttu-id="2500b-132">aba routing number</span><span class="sxs-lookup"><span data-stu-id="2500b-132">aba routing number</span></span>
- <span data-ttu-id="2500b-133">ABA</span><span class="sxs-lookup"><span data-stu-id="2500b-133">aba#</span></span>
- <span data-ttu-id="2500b-134">abarouting#</span><span class="sxs-lookup"><span data-stu-id="2500b-134">abarouting#</span></span>
- <span data-ttu-id="2500b-135">aba number</span><span class="sxs-lookup"><span data-stu-id="2500b-135">aba number</span></span>
- <span data-ttu-id="2500b-136">abaroutingnumber</span><span class="sxs-lookup"><span data-stu-id="2500b-136">abaroutingnumber</span></span>
- <span data-ttu-id="2500b-137">american bank association routing #</span><span class="sxs-lookup"><span data-stu-id="2500b-137">american bank association routing #</span></span>
- <span data-ttu-id="2500b-138">american bank association routing number</span><span class="sxs-lookup"><span data-stu-id="2500b-138">american bank association routing number</span></span>
- <span data-ttu-id="2500b-139">americanbankassociationrouting#</span><span class="sxs-lookup"><span data-stu-id="2500b-139">americanbankassociationrouting#</span></span>
- <span data-ttu-id="2500b-140">americanbankassociationroutingnumber</span><span class="sxs-lookup"><span data-stu-id="2500b-140">americanbankassociationroutingnumber</span></span>
- <span data-ttu-id="2500b-141">bank routing number</span><span class="sxs-lookup"><span data-stu-id="2500b-141">bank routing number</span></span>
- <span data-ttu-id="2500b-142">bankrouting#</span><span class="sxs-lookup"><span data-stu-id="2500b-142">bankrouting#</span></span>
- <span data-ttu-id="2500b-143">bankroutingnumber</span><span class="sxs-lookup"><span data-stu-id="2500b-143">bankroutingnumber</span></span>
- <span data-ttu-id="2500b-144">routing transit number</span><span class="sxs-lookup"><span data-stu-id="2500b-144">routing transit number</span></span>
- <span data-ttu-id="2500b-145">RTN</span><span class="sxs-lookup"><span data-stu-id="2500b-145">RTN</span></span> 
   
## <a name="argentina-national-identity-dni-number"></a><span data-ttu-id="2500b-146">Argentina - Numero di identità nazionale (DNI)</span><span class="sxs-lookup"><span data-stu-id="2500b-146">Argentina National Identity (DNI) Number</span></span>

### <a name="format"></a><span data-ttu-id="2500b-147">Formato</span><span class="sxs-lookup"><span data-stu-id="2500b-147">Format</span></span>

<span data-ttu-id="2500b-148">Otto cifre separate da spazi</span><span class="sxs-lookup"><span data-stu-id="2500b-148">Eight digits separated by periods</span></span>

### <a name="pattern"></a><span data-ttu-id="2500b-149">Modello</span><span class="sxs-lookup"><span data-stu-id="2500b-149">Pattern</span></span>

<span data-ttu-id="2500b-150">Otto cifre</span><span class="sxs-lookup"><span data-stu-id="2500b-150">Eight digits:</span></span>
- <span data-ttu-id="2500b-151">Due cifre</span><span class="sxs-lookup"><span data-stu-id="2500b-151">Two digits</span></span>
- <span data-ttu-id="2500b-152">Un punto </span><span class="sxs-lookup"><span data-stu-id="2500b-152">A period</span></span>
- <span data-ttu-id="2500b-153">Tre cifre</span><span class="sxs-lookup"><span data-stu-id="2500b-153">Three digits</span></span>
- <span data-ttu-id="2500b-154">Un punto </span><span class="sxs-lookup"><span data-stu-id="2500b-154">A period</span></span>
- <span data-ttu-id="2500b-155">Tre cifre</span><span class="sxs-lookup"><span data-stu-id="2500b-155">Three digits</span></span>

### <a name="checksum"></a><span data-ttu-id="2500b-156">Checksum</span><span class="sxs-lookup"><span data-stu-id="2500b-156">Checksum</span></span>

<span data-ttu-id="2500b-157">No</span><span class="sxs-lookup"><span data-stu-id="2500b-157">No</span></span>

### <a name="definition"></a><span data-ttu-id="2500b-158">Definizione</span><span class="sxs-lookup"><span data-stu-id="2500b-158">Definition</span></span>

<span data-ttu-id="2500b-159">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="2500b-159">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2500b-160">L'espressione regolare Regex_argentina_national_id trova il contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="2500b-160">The regular expression Regex_argentina_national_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="2500b-161">Viene trovata una parola chiave da Keyword_argentina_national_id.</span><span class="sxs-lookup"><span data-stu-id="2500b-161">A keyword from Keyword_argentina_national_id is found.</span></span>

```
<!-- Argentina National Identity (DNI) Number -->
<Entity id="eefbb00e-8282-433c-8620-8f1da3bffdb2" recommendedConfidence="75" patternsProximity="300">
   <Pattern confidenceLevel="75">
      <IdMatch idRef="Regex_argentina_national_id"/>
      <Match idRef="Keyword_argentina_national_id"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="2500b-162">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="2500b-162">Keywords</span></span>

#### <a name="keywordargentinanationalid"></a><span data-ttu-id="2500b-163">Keyword_argentina_national_id</span><span class="sxs-lookup"><span data-stu-id="2500b-163">Keyword_argentina_national_id</span></span>

- <span data-ttu-id="2500b-164">Argentina - Numero di identità nazionale</span><span class="sxs-lookup"><span data-stu-id="2500b-164">Argentina National Identity number</span></span> 
- <span data-ttu-id="2500b-165">Identità</span><span class="sxs-lookup"><span data-stu-id="2500b-165">Identity</span></span> 
- <span data-ttu-id="2500b-166">Carta di identità nazionale di identificazione</span><span class="sxs-lookup"><span data-stu-id="2500b-166">Identification National Identity Card</span></span> 
- <span data-ttu-id="2500b-167">DNI</span><span class="sxs-lookup"><span data-stu-id="2500b-167">DNI</span></span> 
- <span data-ttu-id="2500b-168">Registro nazionale delle persone di NIC</span><span class="sxs-lookup"><span data-stu-id="2500b-168">NIC National Registry of Persons</span></span> 
- <span data-ttu-id="2500b-169">Documento Nacional de Identidad</span><span class="sxs-lookup"><span data-stu-id="2500b-169">Documento Nacional de Identidad</span></span> 
- <span data-ttu-id="2500b-170">Registro Nacional de las Personas</span><span class="sxs-lookup"><span data-stu-id="2500b-170">Registro Nacional de las Personas</span></span> 
- <span data-ttu-id="2500b-171">Identidad</span><span class="sxs-lookup"><span data-stu-id="2500b-171">Identidad</span></span> 
- <span data-ttu-id="2500b-172">Identificación</span><span class="sxs-lookup"><span data-stu-id="2500b-172">Identificación</span></span> 
   
## <a name="australia-bank-account-number"></a><span data-ttu-id="2500b-173">Australia - Numero di conto bancario</span><span class="sxs-lookup"><span data-stu-id="2500b-173">Australia Bank Account Number</span></span>

### <a name="format"></a><span data-ttu-id="2500b-174">Formato</span><span class="sxs-lookup"><span data-stu-id="2500b-174">Format</span></span>

<span data-ttu-id="2500b-175">6-10 cifre con o senza un numero BSB (Bank/State/Branch)</span><span class="sxs-lookup"><span data-stu-id="2500b-175">6-10 digits with or without a bank state branch number</span></span>

### <a name="pattern"></a><span data-ttu-id="2500b-176">Modello</span><span class="sxs-lookup"><span data-stu-id="2500b-176">Pattern</span></span>

<span data-ttu-id="2500b-177">Il numero di conto comprende 6-10 cifre.</span><span class="sxs-lookup"><span data-stu-id="2500b-177">Account number is 6-10 digits.</span></span>
<span data-ttu-id="2500b-178">Numero BSB australiano:</span><span class="sxs-lookup"><span data-stu-id="2500b-178">Australia bank state branch number:</span></span>
- <span data-ttu-id="2500b-179">Tre cifre</span><span class="sxs-lookup"><span data-stu-id="2500b-179">Three digits</span></span> 
- <span data-ttu-id="2500b-180">Una lineetta</span><span class="sxs-lookup"><span data-stu-id="2500b-180">A hyphen</span></span> 
- <span data-ttu-id="2500b-181">Tre cifre</span><span class="sxs-lookup"><span data-stu-id="2500b-181">Three digits</span></span>

### <a name="checksum"></a><span data-ttu-id="2500b-182">Checksum</span><span class="sxs-lookup"><span data-stu-id="2500b-182">Checksum</span></span>

<span data-ttu-id="2500b-183">No</span><span class="sxs-lookup"><span data-stu-id="2500b-183">No</span></span>

### <a name="definition"></a><span data-ttu-id="2500b-184">Definizione</span><span class="sxs-lookup"><span data-stu-id="2500b-184">Definition</span></span>

<span data-ttu-id="2500b-185">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="2500b-185">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2500b-186">L'espressione regolare Regex_australia_bank_account_number restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="2500b-186">The regular expression Regex_australia_bank_account_number finds content that matches the pattern..</span></span>
- <span data-ttu-id="2500b-187">Viene trovata una parola chiave da Keyword_australia_bank_account_number.</span><span class="sxs-lookup"><span data-stu-id="2500b-187">A keyword from Keyword_australia_bank_account_number is found.</span></span>
- <span data-ttu-id="2500b-188">L'espressione regolare Regex_australia_bank_account_number_bsb restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="2500b-188">The regular expression Regex_australia_bank_account_number_bsb finds content that matches the pattern.</span></span>

<span data-ttu-id="2500b-189">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="2500b-189">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2500b-190">L'espressione regolare Regex_australia_bank_account_number restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="2500b-190">The regular expression Regex_australia_bank_account_number finds content that matches the pattern..</span></span>
- <span data-ttu-id="2500b-191">Viene trovata una parola chiave da Keyword_australia_bank_account_number.</span><span class="sxs-lookup"><span data-stu-id="2500b-191">A keyword from Keyword_australia_bank_account_number is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="2500b-192">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="2500b-192">Keywords</span></span>

#### <a name="keywordaustraliabankaccountnumber"></a><span data-ttu-id="2500b-193">Keyword_australia_bank_account_number</span><span class="sxs-lookup"><span data-stu-id="2500b-193">Keyword_australia_bank_account_number</span></span>

- <span data-ttu-id="2500b-194">swift bank code</span><span class="sxs-lookup"><span data-stu-id="2500b-194">swift bank code</span></span>
- <span data-ttu-id="2500b-195">correspondent bank</span><span class="sxs-lookup"><span data-stu-id="2500b-195">correspondent bank</span></span>
- <span data-ttu-id="2500b-196">base currency</span><span class="sxs-lookup"><span data-stu-id="2500b-196">base currency</span></span>
- <span data-ttu-id="2500b-197">usa account</span><span class="sxs-lookup"><span data-stu-id="2500b-197">usa account</span></span>
- <span data-ttu-id="2500b-198">holder address</span><span class="sxs-lookup"><span data-stu-id="2500b-198">holder address</span></span>
- <span data-ttu-id="2500b-199">bank address</span><span class="sxs-lookup"><span data-stu-id="2500b-199">bank address</span></span>
- <span data-ttu-id="2500b-200">information account</span><span class="sxs-lookup"><span data-stu-id="2500b-200">information account</span></span>
- <span data-ttu-id="2500b-201">fund transfers</span><span class="sxs-lookup"><span data-stu-id="2500b-201">fund transfers</span></span>
- <span data-ttu-id="2500b-202">bank charges</span><span class="sxs-lookup"><span data-stu-id="2500b-202">bank charges</span></span>
- <span data-ttu-id="2500b-203">bank details</span><span class="sxs-lookup"><span data-stu-id="2500b-203">bank details</span></span>
- <span data-ttu-id="2500b-204">banking information</span><span class="sxs-lookup"><span data-stu-id="2500b-204">banking information</span></span>
- <span data-ttu-id="2500b-205">full names</span><span class="sxs-lookup"><span data-stu-id="2500b-205">full names</span></span>
- <span data-ttu-id="2500b-206">AIEA</span><span class="sxs-lookup"><span data-stu-id="2500b-206">iaea</span></span>

   
## <a name="australia-drivers-license-number"></a><span data-ttu-id="2500b-207">Australia - Numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="2500b-207">Australia Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="2500b-208">Formato</span><span class="sxs-lookup"><span data-stu-id="2500b-208">Format</span></span>

<span data-ttu-id="2500b-209">Nove lettere e numeri</span><span class="sxs-lookup"><span data-stu-id="2500b-209">Nine letters and digits</span></span>

### <a name="pattern"></a><span data-ttu-id="2500b-210">Modello</span><span class="sxs-lookup"><span data-stu-id="2500b-210">Pattern</span></span>

<span data-ttu-id="2500b-211">Nove lettere e numeri:</span><span class="sxs-lookup"><span data-stu-id="2500b-211">Nine letters and digits:</span></span> 

- <span data-ttu-id="2500b-212">Due cifre o lettere (senza distinzione tra maiuscole/minuscole)</span><span class="sxs-lookup"><span data-stu-id="2500b-212">Two digits or letters (not case sensitive)</span></span> 
- <span data-ttu-id="2500b-213">Due cifre</span><span class="sxs-lookup"><span data-stu-id="2500b-213">Two digits</span></span> 
- <span data-ttu-id="2500b-214">Cinque cifre o lettere (senza distinzione tra maiuscole/minuscole)</span><span class="sxs-lookup"><span data-stu-id="2500b-214">Five digits or letters (not case sensitive)</span></span>

<span data-ttu-id="2500b-215">O</span><span class="sxs-lookup"><span data-stu-id="2500b-215">OR</span></span>

- <span data-ttu-id="2500b-216">1-2 lettere facoltative (senza distinzione tra maiuscole/minuscole)</span><span class="sxs-lookup"><span data-stu-id="2500b-216">1-2 optional letters (not case sensitive)</span></span> 
- <span data-ttu-id="2500b-217">4-9 cifre</span><span class="sxs-lookup"><span data-stu-id="2500b-217">4-9 digits</span></span>

<span data-ttu-id="2500b-218">O</span><span class="sxs-lookup"><span data-stu-id="2500b-218">OR</span></span>

- <span data-ttu-id="2500b-219">Nove cifre o lettere (senza distinzione tra maiuscole/minuscole)</span><span class="sxs-lookup"><span data-stu-id="2500b-219">Nine digits or letters (not case sensitive)</span></span>

### <a name="checksum"></a><span data-ttu-id="2500b-220">Checksum</span><span class="sxs-lookup"><span data-stu-id="2500b-220">Checksum</span></span>

<span data-ttu-id="2500b-221">No</span><span class="sxs-lookup"><span data-stu-id="2500b-221">No</span></span>

### <a name="definition"></a><span data-ttu-id="2500b-222">Definizione</span><span class="sxs-lookup"><span data-stu-id="2500b-222">Definition</span></span>

<span data-ttu-id="2500b-223">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="2500b-223">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2500b-224">L'espressione regolare Regex_australia_drivers_license_number restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="2500b-224">The regular expression Regex_australia_drivers_license_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="2500b-225">Viene trovata una parola chiave da Keyword_australia_drivers_license_number.</span><span class="sxs-lookup"><span data-stu-id="2500b-225">A keyword from Keyword_australia_drivers_license_number is found.</span></span>
- <span data-ttu-id="2500b-226">Non vengono trovate parole chiava da Keyword_australia_drivers_license_number_exclusions.</span><span class="sxs-lookup"><span data-stu-id="2500b-226">No keyword from Keyword_australia_drivers_license_number_exclusions is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="2500b-227">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="2500b-227">Keywords</span></span>

#### <a name="keywordaustraliadriverslicensenumber"></a><span data-ttu-id="2500b-228">Keyword_australia_drivers_license_number</span><span class="sxs-lookup"><span data-stu-id="2500b-228">Keyword_australia_drivers_license_number</span></span>

- <span data-ttu-id="2500b-229">international driving permits</span><span class="sxs-lookup"><span data-stu-id="2500b-229">international driving permits</span></span>
- <span data-ttu-id="2500b-230">australian automobile association</span><span class="sxs-lookup"><span data-stu-id="2500b-230">australian automobile association</span></span>
- <span data-ttu-id="2500b-231">international driving permit</span><span class="sxs-lookup"><span data-stu-id="2500b-231">international driving permit</span></span>
- <span data-ttu-id="2500b-232">DriverLicence</span><span class="sxs-lookup"><span data-stu-id="2500b-232">DriverLicence</span></span>
- <span data-ttu-id="2500b-233">DriverLicences</span><span class="sxs-lookup"><span data-stu-id="2500b-233">DriverLicences</span></span>
- <span data-ttu-id="2500b-234">Driver Lic</span><span class="sxs-lookup"><span data-stu-id="2500b-234">Driver Lic</span></span>
- <span data-ttu-id="2500b-235">Driver Licence</span><span class="sxs-lookup"><span data-stu-id="2500b-235">Driver Licence</span></span>
- <span data-ttu-id="2500b-236">Driver Licences</span><span class="sxs-lookup"><span data-stu-id="2500b-236">Driver Licences</span></span>
- <span data-ttu-id="2500b-237">DriversLic</span><span class="sxs-lookup"><span data-stu-id="2500b-237">DriversLic</span></span>
- <span data-ttu-id="2500b-238">DriversLicence</span><span class="sxs-lookup"><span data-stu-id="2500b-238">DriversLicence</span></span>
- <span data-ttu-id="2500b-239">DriversLicences</span><span class="sxs-lookup"><span data-stu-id="2500b-239">DriversLicences</span></span>
- <span data-ttu-id="2500b-240">Drivers Lic</span><span class="sxs-lookup"><span data-stu-id="2500b-240">Drivers Lic</span></span>
- <span data-ttu-id="2500b-241">Drivers Lics</span><span class="sxs-lookup"><span data-stu-id="2500b-241">Drivers Lics</span></span>
- <span data-ttu-id="2500b-242">Drivers Licence</span><span class="sxs-lookup"><span data-stu-id="2500b-242">Drivers Licence</span></span>
- <span data-ttu-id="2500b-243">Drivers Licences</span><span class="sxs-lookup"><span data-stu-id="2500b-243">Drivers Licences</span></span>
- <span data-ttu-id="2500b-244">Driver'Lic</span><span class="sxs-lookup"><span data-stu-id="2500b-244">Driver'Lic</span></span>
- <span data-ttu-id="2500b-245">Driver ' LiCS</span><span class="sxs-lookup"><span data-stu-id="2500b-245">Driver'Lics</span></span>
- <span data-ttu-id="2500b-246">Driver'Licence</span><span class="sxs-lookup"><span data-stu-id="2500b-246">Driver'Licence</span></span>
- <span data-ttu-id="2500b-247">Driver'Licences</span><span class="sxs-lookup"><span data-stu-id="2500b-247">Driver'Licences</span></span>
- <span data-ttu-id="2500b-248">Driver'Lic</span><span class="sxs-lookup"><span data-stu-id="2500b-248">Driver' Lic</span></span>
- <span data-ttu-id="2500b-249">Driver'Lics</span><span class="sxs-lookup"><span data-stu-id="2500b-249">Driver' Lics</span></span>
- <span data-ttu-id="2500b-250">Driver'Licence</span><span class="sxs-lookup"><span data-stu-id="2500b-250">Driver' Licence</span></span>
- <span data-ttu-id="2500b-251">Driver' Licences</span><span class="sxs-lookup"><span data-stu-id="2500b-251">Driver' Licences</span></span>
- <span data-ttu-id="2500b-252">Driver'sLic</span><span class="sxs-lookup"><span data-stu-id="2500b-252">Driver'sLic</span></span>
- <span data-ttu-id="2500b-253">Driver'sLics</span><span class="sxs-lookup"><span data-stu-id="2500b-253">Driver'sLics</span></span>
- <span data-ttu-id="2500b-254">Driver'sLicence</span><span class="sxs-lookup"><span data-stu-id="2500b-254">Driver'sLicence</span></span>
- <span data-ttu-id="2500b-255">Driver'sLicences</span><span class="sxs-lookup"><span data-stu-id="2500b-255">Driver'sLicences</span></span>
- <span data-ttu-id="2500b-256">Driver's Lic</span><span class="sxs-lookup"><span data-stu-id="2500b-256">Driver's Lic</span></span>
- <span data-ttu-id="2500b-257">Driver's Lics</span><span class="sxs-lookup"><span data-stu-id="2500b-257">Driver's Lics</span></span>
- <span data-ttu-id="2500b-258">Driver's Licence</span><span class="sxs-lookup"><span data-stu-id="2500b-258">Driver's Licence</span></span>
- <span data-ttu-id="2500b-259">Driver's Licences</span><span class="sxs-lookup"><span data-stu-id="2500b-259">Driver's Licences</span></span>
- <span data-ttu-id="2500b-260">DriverLic#</span><span class="sxs-lookup"><span data-stu-id="2500b-260">DriverLic#</span></span>
- <span data-ttu-id="2500b-261">DriverLics#</span><span class="sxs-lookup"><span data-stu-id="2500b-261">DriverLics#</span></span>
- <span data-ttu-id="2500b-262">DriverLicence#</span><span class="sxs-lookup"><span data-stu-id="2500b-262">DriverLicence#</span></span>
- <span data-ttu-id="2500b-263">DriverLicences#</span><span class="sxs-lookup"><span data-stu-id="2500b-263">DriverLicences#</span></span>
- <span data-ttu-id="2500b-264">Driver Lic#</span><span class="sxs-lookup"><span data-stu-id="2500b-264">Driver Lic#</span></span>
- <span data-ttu-id="2500b-265">Driver Lics#</span><span class="sxs-lookup"><span data-stu-id="2500b-265">Driver Lics#</span></span>
- <span data-ttu-id="2500b-266">Driver Licence#</span><span class="sxs-lookup"><span data-stu-id="2500b-266">Driver Licence#</span></span>
- <span data-ttu-id="2500b-267">Driver Licences#</span><span class="sxs-lookup"><span data-stu-id="2500b-267">Driver Licences#</span></span>
- <span data-ttu-id="2500b-268">DriversLic#</span><span class="sxs-lookup"><span data-stu-id="2500b-268">DriversLic#</span></span>
- <span data-ttu-id="2500b-269">DriversLics#</span><span class="sxs-lookup"><span data-stu-id="2500b-269">DriversLics#</span></span>
- <span data-ttu-id="2500b-270">DriversLicence#</span><span class="sxs-lookup"><span data-stu-id="2500b-270">DriversLicence#</span></span>
- <span data-ttu-id="2500b-271">DriversLicences#</span><span class="sxs-lookup"><span data-stu-id="2500b-271">DriversLicences#</span></span>
- <span data-ttu-id="2500b-272">Drivers Lic#</span><span class="sxs-lookup"><span data-stu-id="2500b-272">Drivers Lic#</span></span>
- <span data-ttu-id="2500b-273">Drivers Lics#</span><span class="sxs-lookup"><span data-stu-id="2500b-273">Drivers Lics#</span></span>
- <span data-ttu-id="2500b-274">Drivers Licence#</span><span class="sxs-lookup"><span data-stu-id="2500b-274">Drivers Licence#</span></span>
- <span data-ttu-id="2500b-275">Drivers Licences#</span><span class="sxs-lookup"><span data-stu-id="2500b-275">Drivers Licences#</span></span>
- <span data-ttu-id="2500b-276">Driver'Lic#</span><span class="sxs-lookup"><span data-stu-id="2500b-276">Driver'Lic#</span></span>
- <span data-ttu-id="2500b-277">Driver ' LiCS</span><span class="sxs-lookup"><span data-stu-id="2500b-277">Driver'Lics#</span></span>
- <span data-ttu-id="2500b-278">Driver'Licence#</span><span class="sxs-lookup"><span data-stu-id="2500b-278">Driver'Licence#</span></span>
- <span data-ttu-id="2500b-279">Driver'Licences#</span><span class="sxs-lookup"><span data-stu-id="2500b-279">Driver'Licences#</span></span>
- <span data-ttu-id="2500b-280">Driver' Lic#</span><span class="sxs-lookup"><span data-stu-id="2500b-280">Driver' Lic#</span></span>
- <span data-ttu-id="2500b-281">Driver'Lics#</span><span class="sxs-lookup"><span data-stu-id="2500b-281">Driver' Lics#</span></span>
- <span data-ttu-id="2500b-282">Driver'Licence#</span><span class="sxs-lookup"><span data-stu-id="2500b-282">Driver' Licence#</span></span>
- <span data-ttu-id="2500b-283">Driver' Licences#</span><span class="sxs-lookup"><span data-stu-id="2500b-283">Driver' Licences#</span></span>
- <span data-ttu-id="2500b-284">Driver'sLic#</span><span class="sxs-lookup"><span data-stu-id="2500b-284">Driver'sLic#</span></span>
- <span data-ttu-id="2500b-285">Driver'sLics#</span><span class="sxs-lookup"><span data-stu-id="2500b-285">Driver'sLics#</span></span>
- <span data-ttu-id="2500b-286">Driver'sLicence#</span><span class="sxs-lookup"><span data-stu-id="2500b-286">Driver'sLicence#</span></span>
- <span data-ttu-id="2500b-287">Driver'sLicences#</span><span class="sxs-lookup"><span data-stu-id="2500b-287">Driver'sLicences#</span></span>
- <span data-ttu-id="2500b-288">Driver's Lic#</span><span class="sxs-lookup"><span data-stu-id="2500b-288">Driver's Lic#</span></span>
- <span data-ttu-id="2500b-289">Driver's Lics#</span><span class="sxs-lookup"><span data-stu-id="2500b-289">Driver's Lics#</span></span>
- <span data-ttu-id="2500b-290">Driver's Licence#</span><span class="sxs-lookup"><span data-stu-id="2500b-290">Driver's Licence#</span></span>
- <span data-ttu-id="2500b-291">Driver's Licences#</span><span class="sxs-lookup"><span data-stu-id="2500b-291">Driver's Licences#</span></span> 

#### <a name="keywordaustraliadriverslicensenumberexclusions"></a><span data-ttu-id="2500b-292">Keyword_australia_drivers_license_number_exclusions</span><span class="sxs-lookup"><span data-stu-id="2500b-292">Keyword_australia_drivers_license_number_exclusions</span></span>

- <span data-ttu-id="2500b-293">AAA</span><span class="sxs-lookup"><span data-stu-id="2500b-293">aaa</span></span>
- <span data-ttu-id="2500b-294">DriverLicense</span><span class="sxs-lookup"><span data-stu-id="2500b-294">DriverLicense</span></span>
- <span data-ttu-id="2500b-295">DriverLicenses</span><span class="sxs-lookup"><span data-stu-id="2500b-295">DriverLicenses</span></span>
- <span data-ttu-id="2500b-296">Driver License</span><span class="sxs-lookup"><span data-stu-id="2500b-296">Driver License</span></span>
- <span data-ttu-id="2500b-297">Driver Licenses</span><span class="sxs-lookup"><span data-stu-id="2500b-297">Driver Licenses</span></span>
- <span data-ttu-id="2500b-298">DriversLicense</span><span class="sxs-lookup"><span data-stu-id="2500b-298">DriversLicense</span></span>
- <span data-ttu-id="2500b-299">DriversLicenses</span><span class="sxs-lookup"><span data-stu-id="2500b-299">DriversLicenses</span></span>
- <span data-ttu-id="2500b-300">Drivers License</span><span class="sxs-lookup"><span data-stu-id="2500b-300">Drivers License</span></span>
- <span data-ttu-id="2500b-301">Drivers Licenses</span><span class="sxs-lookup"><span data-stu-id="2500b-301">Drivers Licenses</span></span>
- <span data-ttu-id="2500b-302">Driver ' License</span><span class="sxs-lookup"><span data-stu-id="2500b-302">Driver'License</span></span>
- <span data-ttu-id="2500b-303">Driver ' licenses</span><span class="sxs-lookup"><span data-stu-id="2500b-303">Driver'Licenses</span></span>
- <span data-ttu-id="2500b-304">Driver' License</span><span class="sxs-lookup"><span data-stu-id="2500b-304">Driver' License</span></span>
- <span data-ttu-id="2500b-305">Driver' Licenses</span><span class="sxs-lookup"><span data-stu-id="2500b-305">Driver' Licenses</span></span>
- <span data-ttu-id="2500b-306">Secondola</span><span class="sxs-lookup"><span data-stu-id="2500b-306">Driver'sLicense</span></span>
- <span data-ttu-id="2500b-307">Driver'sLicenses</span><span class="sxs-lookup"><span data-stu-id="2500b-307">Driver'sLicenses</span></span>
- <span data-ttu-id="2500b-308">Driver's License</span><span class="sxs-lookup"><span data-stu-id="2500b-308">Driver's License</span></span>
- <span data-ttu-id="2500b-309">Driver's Licenses</span><span class="sxs-lookup"><span data-stu-id="2500b-309">Driver's Licenses</span></span>
- <span data-ttu-id="2500b-310">DriverLicense#</span><span class="sxs-lookup"><span data-stu-id="2500b-310">DriverLicense#</span></span>
- <span data-ttu-id="2500b-311">DriverLicenses#</span><span class="sxs-lookup"><span data-stu-id="2500b-311">DriverLicenses#</span></span>
- <span data-ttu-id="2500b-312">Driver License#</span><span class="sxs-lookup"><span data-stu-id="2500b-312">Driver License#</span></span>
- <span data-ttu-id="2500b-313">Driver Licenses#</span><span class="sxs-lookup"><span data-stu-id="2500b-313">Driver Licenses#</span></span>
- <span data-ttu-id="2500b-314">DriversLicense#</span><span class="sxs-lookup"><span data-stu-id="2500b-314">DriversLicense#</span></span>
- <span data-ttu-id="2500b-315">DriversLicenses#</span><span class="sxs-lookup"><span data-stu-id="2500b-315">DriversLicenses#</span></span>
- <span data-ttu-id="2500b-316">Drivers License#</span><span class="sxs-lookup"><span data-stu-id="2500b-316">Drivers License#</span></span>
- <span data-ttu-id="2500b-317">Drivers Licenses#</span><span class="sxs-lookup"><span data-stu-id="2500b-317">Drivers Licenses#</span></span>
- <span data-ttu-id="2500b-318">Driver ' License</span><span class="sxs-lookup"><span data-stu-id="2500b-318">Driver'License#</span></span>
- <span data-ttu-id="2500b-319">Driver ' licenses</span><span class="sxs-lookup"><span data-stu-id="2500b-319">Driver'Licenses#</span></span>
- <span data-ttu-id="2500b-320">Driver' License#</span><span class="sxs-lookup"><span data-stu-id="2500b-320">Driver' License#</span></span>
- <span data-ttu-id="2500b-321">Driver' Licenses#</span><span class="sxs-lookup"><span data-stu-id="2500b-321">Driver' Licenses#</span></span>
- <span data-ttu-id="2500b-322">Secondola</span><span class="sxs-lookup"><span data-stu-id="2500b-322">Driver'sLicense#</span></span>
- <span data-ttu-id="2500b-323">Driver'sLicenses#</span><span class="sxs-lookup"><span data-stu-id="2500b-323">Driver'sLicenses#</span></span>
- <span data-ttu-id="2500b-324">Driver's License#</span><span class="sxs-lookup"><span data-stu-id="2500b-324">Driver's License#</span></span>
- <span data-ttu-id="2500b-325">Driver's Licenses#</span><span class="sxs-lookup"><span data-stu-id="2500b-325">Driver's Licenses#</span></span>
   
## <a name="australia-medical-account-number"></a><span data-ttu-id="2500b-326">Australia - Numero di tessera sanitaria</span><span class="sxs-lookup"><span data-stu-id="2500b-326">Australia Medical Account Number</span></span>

### <a name="format"></a><span data-ttu-id="2500b-327">Formato</span><span class="sxs-lookup"><span data-stu-id="2500b-327">Format</span></span>

<span data-ttu-id="2500b-328">10-11 cifre</span><span class="sxs-lookup"><span data-stu-id="2500b-328">10-11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="2500b-329">Modello</span><span class="sxs-lookup"><span data-stu-id="2500b-329">Pattern</span></span>

<span data-ttu-id="2500b-330">10-11 cifre:</span><span class="sxs-lookup"><span data-stu-id="2500b-330">10-11 digits:</span></span>
- <span data-ttu-id="2500b-331">La prima cifra è compresa nell'intervallo 2-6</span><span class="sxs-lookup"><span data-stu-id="2500b-331">First digit is in the range 2-6</span></span>
- <span data-ttu-id="2500b-332">La nona cifra è una cifra di controllo</span><span class="sxs-lookup"><span data-stu-id="2500b-332">Ninth digit is a check digit</span></span>
- <span data-ttu-id="2500b-333">La decima cifra è la cifra del problema</span><span class="sxs-lookup"><span data-stu-id="2500b-333">Tenth digit is the issue digit</span></span>
- <span data-ttu-id="2500b-334">L'undicesima cifra (facoltativa) è il numero singolo</span><span class="sxs-lookup"><span data-stu-id="2500b-334">Eleventh digit (optional) is the individual number</span></span>

### <a name="checksum"></a><span data-ttu-id="2500b-335">Checksum</span><span class="sxs-lookup"><span data-stu-id="2500b-335">Checksum</span></span>

<span data-ttu-id="2500b-336">Sì</span><span class="sxs-lookup"><span data-stu-id="2500b-336">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="2500b-337">Definizione</span><span class="sxs-lookup"><span data-stu-id="2500b-337">Definition</span></span>

<span data-ttu-id="2500b-338">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 95%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="2500b-338">A DLP policy is 95% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2500b-339">La funzione Func_australian_medical_account_number restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="2500b-339">The function Func_australian_medical_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="2500b-340">Viene trovata una parola chiave da Keyword_Australia_Medical_Account_Number.</span><span class="sxs-lookup"><span data-stu-id="2500b-340">A keyword from Keyword_Australia_Medical_Account_Number is found.</span></span>
- <span data-ttu-id="2500b-341">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="2500b-341">The checksum passes.</span></span>

<span data-ttu-id="2500b-342">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="2500b-342">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2500b-343">La funzione Func_australian_medical_account_number restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="2500b-343">The function Func_australian_medical_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="2500b-344">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="2500b-344">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="2500b-345">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="2500b-345">Keywords</span></span>

#### <a name="keywordaustraliamedicalaccountnumber"></a><span data-ttu-id="2500b-346">Keyword_Australia_Medical_Account_Number</span><span class="sxs-lookup"><span data-stu-id="2500b-346">Keyword_Australia_Medical_Account_Number</span></span>

- <span data-ttu-id="2500b-347">bank account details</span><span class="sxs-lookup"><span data-stu-id="2500b-347">bank account details</span></span>
- <span data-ttu-id="2500b-348">medicare payments</span><span class="sxs-lookup"><span data-stu-id="2500b-348">medicare payments</span></span>
- <span data-ttu-id="2500b-349">mortgage account</span><span class="sxs-lookup"><span data-stu-id="2500b-349">mortgage account</span></span>
- <span data-ttu-id="2500b-350">bank payments</span><span class="sxs-lookup"><span data-stu-id="2500b-350">bank payments</span></span>
- <span data-ttu-id="2500b-351">information branch</span><span class="sxs-lookup"><span data-stu-id="2500b-351">information branch</span></span>
- <span data-ttu-id="2500b-352">credit card loan</span><span class="sxs-lookup"><span data-stu-id="2500b-352">credit card loan</span></span>
- <span data-ttu-id="2500b-353">department of human services</span><span class="sxs-lookup"><span data-stu-id="2500b-353">department of human services</span></span>
- <span data-ttu-id="2500b-354">local service</span><span class="sxs-lookup"><span data-stu-id="2500b-354">local service</span></span>
- <span data-ttu-id="2500b-355">Medicare</span><span class="sxs-lookup"><span data-stu-id="2500b-355">medicare</span></span>

   
## <a name="australia-passport-number"></a><span data-ttu-id="2500b-356">Australia - Numero di passaporto</span><span class="sxs-lookup"><span data-stu-id="2500b-356">Australia Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="2500b-357">Formato</span><span class="sxs-lookup"><span data-stu-id="2500b-357">Format</span></span>

<span data-ttu-id="2500b-358">Una lettera seguita da sette cifre</span><span class="sxs-lookup"><span data-stu-id="2500b-358">A letter followed by seven digits</span></span>

### <a name="pattern"></a><span data-ttu-id="2500b-359">Modello</span><span class="sxs-lookup"><span data-stu-id="2500b-359">Pattern</span></span>

<span data-ttu-id="2500b-360">Una lettera (senza distinzione tra maiuscole/minuscole) seguita da sette cifre</span><span class="sxs-lookup"><span data-stu-id="2500b-360">A letter (not case sensitive) followed by seven digits</span></span>

### <a name="checksum"></a><span data-ttu-id="2500b-361">Checksum</span><span class="sxs-lookup"><span data-stu-id="2500b-361">Checksum</span></span>

<span data-ttu-id="2500b-362">No</span><span class="sxs-lookup"><span data-stu-id="2500b-362">No</span></span>

### <a name="definition"></a><span data-ttu-id="2500b-363">Definizione</span><span class="sxs-lookup"><span data-stu-id="2500b-363">Definition</span></span>

<span data-ttu-id="2500b-364">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="2500b-364">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2500b-365">L'espressione regolare Regex_australia_passport_number restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="2500b-365">The regular expression Regex_australia_passport_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="2500b-366">Viene trovata una parola chiave da Keyword_passport o Keyword_australia_passport_number.</span><span class="sxs-lookup"><span data-stu-id="2500b-366">A keyword from Keyword_passport or Keyword_australia_passport_number is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="2500b-367">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="2500b-367">Keywords</span></span>

#### <a name="keywordpassport"></a><span data-ttu-id="2500b-368">Keyword_passport</span><span class="sxs-lookup"><span data-stu-id="2500b-368">Keyword_passport</span></span>

- <span data-ttu-id="2500b-369">Passport Number</span><span class="sxs-lookup"><span data-stu-id="2500b-369">Passport Number</span></span>
- <span data-ttu-id="2500b-370">Passport No</span><span class="sxs-lookup"><span data-stu-id="2500b-370">Passport No</span></span>
- <span data-ttu-id="2500b-371">Passport#</span><span class="sxs-lookup"><span data-stu-id="2500b-371">Passport #</span></span>
- <span data-ttu-id="2500b-372">Passaporto</span><span class="sxs-lookup"><span data-stu-id="2500b-372">Passport#</span></span>
- <span data-ttu-id="2500b-373">PassportID</span><span class="sxs-lookup"><span data-stu-id="2500b-373">PassportID</span></span>
- <span data-ttu-id="2500b-374">Passportno</span><span class="sxs-lookup"><span data-stu-id="2500b-374">Passportno</span></span>
- <span data-ttu-id="2500b-375">passportnumber</span><span class="sxs-lookup"><span data-stu-id="2500b-375">passportnumber</span></span>
- <span data-ttu-id="2500b-376">パスポート</span><span class="sxs-lookup"><span data-stu-id="2500b-376">パスポート</span></span>
- <span data-ttu-id="2500b-377">パスポート番号</span><span class="sxs-lookup"><span data-stu-id="2500b-377">パスポート番号</span></span>
- <span data-ttu-id="2500b-378">パスポートのNum</span><span class="sxs-lookup"><span data-stu-id="2500b-378">パスポートのNum</span></span>
- <span data-ttu-id="2500b-379">パスポート ＃</span><span class="sxs-lookup"><span data-stu-id="2500b-379">パスポート ＃</span></span> 
- <span data-ttu-id="2500b-380">Numéro de passeport</span><span class="sxs-lookup"><span data-stu-id="2500b-380">Numéro de passeport</span></span>
- <span data-ttu-id="2500b-381">Passeport n °</span><span class="sxs-lookup"><span data-stu-id="2500b-381">Passeport n °</span></span>
- <span data-ttu-id="2500b-382">Passeport Non</span><span class="sxs-lookup"><span data-stu-id="2500b-382">Passeport Non</span></span>
- <span data-ttu-id="2500b-383">Passeport#</span><span class="sxs-lookup"><span data-stu-id="2500b-383">Passeport #</span></span>
- <span data-ttu-id="2500b-384">Passeport</span><span class="sxs-lookup"><span data-stu-id="2500b-384">Passeport#</span></span>
- <span data-ttu-id="2500b-385">PasseportNon</span><span class="sxs-lookup"><span data-stu-id="2500b-385">PasseportNon</span></span>
- <span data-ttu-id="2500b-386">Passeportn °</span><span class="sxs-lookup"><span data-stu-id="2500b-386">Passeportn °</span></span>

#### <a name="keywordaustraliapassportnumber"></a><span data-ttu-id="2500b-387">Keyword_australia_passport_number</span><span class="sxs-lookup"><span data-stu-id="2500b-387">Keyword_australia_passport_number</span></span>

- <span data-ttu-id="2500b-388">passaporto</span><span class="sxs-lookup"><span data-stu-id="2500b-388">passport</span></span>
- <span data-ttu-id="2500b-389">passport details</span><span class="sxs-lookup"><span data-stu-id="2500b-389">passport details</span></span>
- <span data-ttu-id="2500b-390">immigration and citizenship</span><span class="sxs-lookup"><span data-stu-id="2500b-390">immigration and citizenship</span></span>
- <span data-ttu-id="2500b-391">commonwealth of australia</span><span class="sxs-lookup"><span data-stu-id="2500b-391">commonwealth of australia</span></span>
- <span data-ttu-id="2500b-392">department of immigration</span><span class="sxs-lookup"><span data-stu-id="2500b-392">department of immigration</span></span>
- <span data-ttu-id="2500b-393">residential address</span><span class="sxs-lookup"><span data-stu-id="2500b-393">residential address</span></span>
- <span data-ttu-id="2500b-394">department of immigration and citizenship</span><span class="sxs-lookup"><span data-stu-id="2500b-394">department of immigration and citizenship</span></span>
- <span data-ttu-id="2500b-395">esempio</span><span class="sxs-lookup"><span data-stu-id="2500b-395">visa</span></span>
- <span data-ttu-id="2500b-396">national identity card</span><span class="sxs-lookup"><span data-stu-id="2500b-396">national identity card</span></span>
- <span data-ttu-id="2500b-397">passport number</span><span class="sxs-lookup"><span data-stu-id="2500b-397">passport number</span></span>
- <span data-ttu-id="2500b-398">travel document</span><span class="sxs-lookup"><span data-stu-id="2500b-398">travel document</span></span>
- <span data-ttu-id="2500b-399">issuing authority</span><span class="sxs-lookup"><span data-stu-id="2500b-399">issuing authority</span></span>
   
## <a name="australia-tax-file-number"></a><span data-ttu-id="2500b-400">Australia - Identificativo fiscale</span><span class="sxs-lookup"><span data-stu-id="2500b-400">Australia Tax File Number</span></span>

### <a name="format"></a><span data-ttu-id="2500b-401">Formato</span><span class="sxs-lookup"><span data-stu-id="2500b-401">Format</span></span>

<span data-ttu-id="2500b-402">8-9 cifre</span><span class="sxs-lookup"><span data-stu-id="2500b-402">8-9 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="2500b-403">Modello</span><span class="sxs-lookup"><span data-stu-id="2500b-403">Pattern</span></span>

<span data-ttu-id="2500b-404">8-9 cifre in genere presentate con spazi, come mostrato di seguito:</span><span class="sxs-lookup"><span data-stu-id="2500b-404">8-9 digits typically presented with spaces as follows:</span></span>
- <span data-ttu-id="2500b-405">Tre cifre</span><span class="sxs-lookup"><span data-stu-id="2500b-405">Three digits</span></span> 
- <span data-ttu-id="2500b-406">Uno spazio facoltativo</span><span class="sxs-lookup"><span data-stu-id="2500b-406">An optional space</span></span> 
- <span data-ttu-id="2500b-407">Tre cifre</span><span class="sxs-lookup"><span data-stu-id="2500b-407">Three digits</span></span> 
- <span data-ttu-id="2500b-408">Uno spazio facoltativo</span><span class="sxs-lookup"><span data-stu-id="2500b-408">An optional space</span></span> 
- <span data-ttu-id="2500b-409">2-3 cifre e l'ultima è una cifra di controllo</span><span class="sxs-lookup"><span data-stu-id="2500b-409">2-3 digits where the last digit is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="2500b-410">Checksum</span><span class="sxs-lookup"><span data-stu-id="2500b-410">Checksum</span></span>

<span data-ttu-id="2500b-411">Sì</span><span class="sxs-lookup"><span data-stu-id="2500b-411">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="2500b-412">Definizione</span><span class="sxs-lookup"><span data-stu-id="2500b-412">Definition</span></span>

<span data-ttu-id="2500b-413">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="2500b-413">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2500b-414">La funzione Func_australian_tax_file_number restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="2500b-414">The function Func_australian_tax_file_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="2500b-415">Non vengono trovate parole chiave da Keyword_Australia_Tax_File_Number o da Keyword_number_exclusions.</span><span class="sxs-lookup"><span data-stu-id="2500b-415">No keyword from Keyword_Australia_Tax_File_Number or Keyword_number_exclusions is found.</span></span>
- <span data-ttu-id="2500b-416">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="2500b-416">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="2500b-417">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="2500b-417">Keywords</span></span>

#### <a name="keywordaustraliataxfilenumber"></a><span data-ttu-id="2500b-418">Keyword_Australia_Tax_File_Number</span><span class="sxs-lookup"><span data-stu-id="2500b-418">Keyword_Australia_Tax_File_Number</span></span>

- <span data-ttu-id="2500b-419">australian business number</span><span class="sxs-lookup"><span data-stu-id="2500b-419">australian business number</span></span>
- <span data-ttu-id="2500b-420">marginal tax rate</span><span class="sxs-lookup"><span data-stu-id="2500b-420">marginal tax rate</span></span>
- <span data-ttu-id="2500b-421">medicare levy</span><span class="sxs-lookup"><span data-stu-id="2500b-421">medicare levy</span></span>
- <span data-ttu-id="2500b-422">portfolio number</span><span class="sxs-lookup"><span data-stu-id="2500b-422">portfolio number</span></span>
- <span data-ttu-id="2500b-423">service veterans</span><span class="sxs-lookup"><span data-stu-id="2500b-423">service veterans</span></span>
- <span data-ttu-id="2500b-424">withholding tax</span><span class="sxs-lookup"><span data-stu-id="2500b-424">withholding tax</span></span>
- <span data-ttu-id="2500b-425">individual tax return</span><span class="sxs-lookup"><span data-stu-id="2500b-425">individual tax return</span></span>
- <span data-ttu-id="2500b-426">tax file number</span><span class="sxs-lookup"><span data-stu-id="2500b-426">tax file number</span></span>

#### <a name="keywordnumberexclusions"></a><span data-ttu-id="2500b-427">Keyword_number_exclusions</span><span class="sxs-lookup"><span data-stu-id="2500b-427">Keyword_number_exclusions</span></span>

- <span data-ttu-id="2500b-428">00000000</span><span class="sxs-lookup"><span data-stu-id="2500b-428">00000000</span></span>
- <span data-ttu-id="2500b-429">11111111</span><span class="sxs-lookup"><span data-stu-id="2500b-429">11111111</span></span>
- <span data-ttu-id="2500b-430">22222222</span><span class="sxs-lookup"><span data-stu-id="2500b-430">22222222</span></span>
- <span data-ttu-id="2500b-431">33333333</span><span class="sxs-lookup"><span data-stu-id="2500b-431">33333333</span></span>
- <span data-ttu-id="2500b-432">44444444</span><span class="sxs-lookup"><span data-stu-id="2500b-432">44444444</span></span>
- <span data-ttu-id="2500b-433">55555555</span><span class="sxs-lookup"><span data-stu-id="2500b-433">55555555</span></span>
- <span data-ttu-id="2500b-434">66666666</span><span class="sxs-lookup"><span data-stu-id="2500b-434">66666666</span></span>
- <span data-ttu-id="2500b-435">77777777</span><span class="sxs-lookup"><span data-stu-id="2500b-435">77777777</span></span>
- <span data-ttu-id="2500b-436">88888888</span><span class="sxs-lookup"><span data-stu-id="2500b-436">88888888</span></span>
- <span data-ttu-id="2500b-437">99999999</span><span class="sxs-lookup"><span data-stu-id="2500b-437">99999999</span></span>
- <span data-ttu-id="2500b-438">000000000</span><span class="sxs-lookup"><span data-stu-id="2500b-438">000000000</span></span>
- <span data-ttu-id="2500b-439">111111111</span><span class="sxs-lookup"><span data-stu-id="2500b-439">111111111</span></span>
- <span data-ttu-id="2500b-440">222222222</span><span class="sxs-lookup"><span data-stu-id="2500b-440">222222222</span></span>
- <span data-ttu-id="2500b-441">333333333</span><span class="sxs-lookup"><span data-stu-id="2500b-441">333333333</span></span>
- <span data-ttu-id="2500b-442">444444444</span><span class="sxs-lookup"><span data-stu-id="2500b-442">444444444</span></span>
- <span data-ttu-id="2500b-443">555555555</span><span class="sxs-lookup"><span data-stu-id="2500b-443">555555555</span></span>
- <span data-ttu-id="2500b-444">666666666</span><span class="sxs-lookup"><span data-stu-id="2500b-444">666666666</span></span>
- <span data-ttu-id="2500b-445">777777777</span><span class="sxs-lookup"><span data-stu-id="2500b-445">777777777</span></span>
- <span data-ttu-id="2500b-446">888888888</span><span class="sxs-lookup"><span data-stu-id="2500b-446">888888888</span></span>
- <span data-ttu-id="2500b-447">999999999</span><span class="sxs-lookup"><span data-stu-id="2500b-447">999999999</span></span>
- <span data-ttu-id="2500b-448">0000000000</span><span class="sxs-lookup"><span data-stu-id="2500b-448">0000000000</span></span>
- <span data-ttu-id="2500b-449">1111111111</span><span class="sxs-lookup"><span data-stu-id="2500b-449">1111111111</span></span>
- <span data-ttu-id="2500b-450">2222222222</span><span class="sxs-lookup"><span data-stu-id="2500b-450">2222222222</span></span>
- <span data-ttu-id="2500b-451">3333333333</span><span class="sxs-lookup"><span data-stu-id="2500b-451">3333333333</span></span>
- <span data-ttu-id="2500b-452">4444444444</span><span class="sxs-lookup"><span data-stu-id="2500b-452">4444444444</span></span>
- <span data-ttu-id="2500b-453">5555555555</span><span class="sxs-lookup"><span data-stu-id="2500b-453">5555555555</span></span>
- <span data-ttu-id="2500b-454">6666666666</span><span class="sxs-lookup"><span data-stu-id="2500b-454">6666666666</span></span>
- <span data-ttu-id="2500b-455">7777777777</span><span class="sxs-lookup"><span data-stu-id="2500b-455">7777777777</span></span>
- <span data-ttu-id="2500b-456">8888888888</span><span class="sxs-lookup"><span data-stu-id="2500b-456">8888888888</span></span>
- <span data-ttu-id="2500b-457">9999999999</span><span class="sxs-lookup"><span data-stu-id="2500b-457">9999999999</span></span>

## <a name="azure-documentdb-auth-key"></a><span data-ttu-id="2500b-458">Chiave di autenticazione di DocumentDB di Azure</span><span class="sxs-lookup"><span data-stu-id="2500b-458">Azure DocumentDB Auth Key</span></span>

### <a name="format"></a><span data-ttu-id="2500b-459">Formato</span><span class="sxs-lookup"><span data-stu-id="2500b-459">Format</span></span>

<span data-ttu-id="2500b-460">La stringa "DocumentDb" seguita dai caratteri e dalle stringhe delineate nel modello seguente.</span><span class="sxs-lookup"><span data-stu-id="2500b-460">The string "DocumentDb" followed by the characters and strings outlined in the pattern below.</span></span>

### <a name="pattern"></a><span data-ttu-id="2500b-461">Modello</span><span class="sxs-lookup"><span data-stu-id="2500b-461">Pattern</span></span>

- <span data-ttu-id="2500b-462">La stringa "DocumentDb"</span><span class="sxs-lookup"><span data-stu-id="2500b-462">The string "DocumentDb"</span></span>
- <span data-ttu-id="2500b-463">Qualsiasi combinazione tra 3-200 lettere, cifre, simboli, caratteri speciali o spazi in maiuscolo o minuscolo</span><span class="sxs-lookup"><span data-stu-id="2500b-463">Any combination of between 3-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="2500b-464">Un simbolo maggiore di (>), un segno di uguale (=), un segno di virgolette (") oppure un apostrofo (')</span><span class="sxs-lookup"><span data-stu-id="2500b-464">A greater than symbol (>), an equal sign (=), a quotation mark ("), or an apostrophe (')</span></span>
- <span data-ttu-id="2500b-465">Qualsiasi combinazione di 86 lettere maiuscole e minuscole, cifre, barra (/) o segno più (+)</span><span class="sxs-lookup"><span data-stu-id="2500b-465">Any combination of 86 lower- or uppercase letters, digits, forward slash (/), or plus sign (+)</span></span>
- <span data-ttu-id="2500b-466">Due segni uguali (=)</span><span class="sxs-lookup"><span data-stu-id="2500b-466">Two equal signs (=)</span></span>

### <a name="checksum"></a><span data-ttu-id="2500b-467">Checksum</span><span class="sxs-lookup"><span data-stu-id="2500b-467">Checksum</span></span>

<span data-ttu-id="2500b-468">No</span><span class="sxs-lookup"><span data-stu-id="2500b-468">No</span></span>

### <a name="definition"></a><span data-ttu-id="2500b-469">Definizione</span><span class="sxs-lookup"><span data-stu-id="2500b-469">Definition</span></span>

<span data-ttu-id="2500b-470">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="2500b-470">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2500b-471">L'espressione regolare CEP_Regex_AzureDocumentDBAuthKey trova il contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="2500b-471">The regular expression CEP_Regex_AzureDocumentDBAuthKey finds content that matches the pattern.</span></span>
- <span data-ttu-id="2500b-472">L'espressione regolare CEP_CommonExampleKeywords non \*\*\*\* trova contenuto corrispondente al modello.</span><span class="sxs-lookup"><span data-stu-id="2500b-472">The regular expression CEP_CommonExampleKeywords does **not** find content that matches the pattern.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="2500b-473">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="2500b-473">Keywords</span></span>

#### <a name="cepcommonexamplekeywords"></a><span data-ttu-id="2500b-474">CEP_CommonExampleKeywords</span><span class="sxs-lookup"><span data-stu-id="2500b-474">CEP_CommonExampleKeywords</span></span>

<span data-ttu-id="2500b-475">Si noti che tecnicamente questo tipo di informazioni riservate identifica queste parole chiave utilizzando un'espressione regolare, non un elenco di parola chiave.</span><span class="sxs-lookup"><span data-stu-id="2500b-475">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="2500b-476">contoso</span><span class="sxs-lookup"><span data-stu-id="2500b-476">contoso</span></span>
- <span data-ttu-id="2500b-477">Fabrikam</span><span class="sxs-lookup"><span data-stu-id="2500b-477">fabrikam</span></span>
- <span data-ttu-id="2500b-478">Northwind</span><span class="sxs-lookup"><span data-stu-id="2500b-478">northwind</span></span>
- <span data-ttu-id="2500b-479">sandbox</span><span class="sxs-lookup"><span data-stu-id="2500b-479">sandbox</span></span>
- <span data-ttu-id="2500b-480">OneBox</span><span class="sxs-lookup"><span data-stu-id="2500b-480">onebox</span></span>
- <span data-ttu-id="2500b-481">localhost</span><span class="sxs-lookup"><span data-stu-id="2500b-481">localhost</span></span>
- <span data-ttu-id="2500b-482">127.0.0.1</span><span class="sxs-lookup"><span data-stu-id="2500b-482">127.0.0.1</span></span>
- <span data-ttu-id="2500b-483">testacs.</span><span class="sxs-lookup"><span data-stu-id="2500b-483">testacs.</span></span><!--no-hyperlink--><span data-ttu-id="2500b-484">com</span><span class="sxs-lookup"><span data-stu-id="2500b-484">com</span></span>
- <span data-ttu-id="2500b-485">s-int.</span><span class="sxs-lookup"><span data-stu-id="2500b-485">s-int.</span></span><!--no-hyperlink--><span data-ttu-id="2500b-486">NET</span><span class="sxs-lookup"><span data-stu-id="2500b-486">net</span></span>

## <a name="azure-iaas-database-connection-string-and-azure-sql-connection-string"></a><span data-ttu-id="2500b-487">Stringa di connessione del database di Azure IAAS e stringa di connessione SQL di Azure</span><span class="sxs-lookup"><span data-stu-id="2500b-487">Azure IAAS Database Connection String and Azure SQL Connection String</span></span>

### <a name="format"></a><span data-ttu-id="2500b-488">Formato</span><span class="sxs-lookup"><span data-stu-id="2500b-488">Format</span></span>

<span data-ttu-id="2500b-489">Stringa "Server", "Server" o "Data Source" seguito dai caratteri e dalle stringhe delineati nel modello seguente, inclusa la stringa "cloudapp. Azure.</span><span class="sxs-lookup"><span data-stu-id="2500b-489">The string "Server", "server", or "data source" followed by the characters and strings outlined in the pattern below, including the string "cloudapp.azure.</span></span><!--no-hyperlink--><span data-ttu-id="2500b-490">com "o" cloudapp. Azure.</span><span class="sxs-lookup"><span data-stu-id="2500b-490">com" or "cloudapp.azure.</span></span><!--no-hyperlink--><span data-ttu-id="2500b-491">NET "o" database. Windows.</span><span class="sxs-lookup"><span data-stu-id="2500b-491">net" or "database.windows.</span></span><!--no-hyperlink--><span data-ttu-id="2500b-492">NET "e la stringa" password "o" password "o" pwd ".</span><span class="sxs-lookup"><span data-stu-id="2500b-492">net", and the string "Password" or "password" or "pwd".</span></span>

### <a name="pattern"></a><span data-ttu-id="2500b-493">Modello</span><span class="sxs-lookup"><span data-stu-id="2500b-493">Pattern</span></span>

- <span data-ttu-id="2500b-494">La stringa "Server", "Server" o "Data Source"</span><span class="sxs-lookup"><span data-stu-id="2500b-494">The string "Server", "server", or "data source"</span></span>
- <span data-ttu-id="2500b-495">0-2 caratteri dello spazio vuoto</span><span class="sxs-lookup"><span data-stu-id="2500b-495">0-2 whitespace characters</span></span>
- <span data-ttu-id="2500b-496">Segno di uguale (=)</span><span class="sxs-lookup"><span data-stu-id="2500b-496">An equal sign (=)</span></span>
- <span data-ttu-id="2500b-497">0-2 caratteri dello spazio vuoto</span><span class="sxs-lookup"><span data-stu-id="2500b-497">0-2 whitespace characters</span></span>
- <span data-ttu-id="2500b-498">Qualsiasi combinazione tra 1-200 lettere, cifre, simboli, caratteri speciali o spazi in maiuscolo o minuscolo</span><span class="sxs-lookup"><span data-stu-id="2500b-498">Any combination of between 1-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="2500b-499">La stringa "cloudapp. Azure.</span><span class="sxs-lookup"><span data-stu-id="2500b-499">The string "cloudapp.azure.</span></span><!--no-hyperlink--><span data-ttu-id="2500b-500">com "," cloudapp. Azure.</span><span class="sxs-lookup"><span data-stu-id="2500b-500">com", "cloudapp.azure.</span></span><!--no-hyperlink--><span data-ttu-id="2500b-501">NET "o" database. Windows.</span><span class="sxs-lookup"><span data-stu-id="2500b-501">net", or "database.windows.</span></span><!--no-hyperlink--><span data-ttu-id="2500b-502">NET</span><span class="sxs-lookup"><span data-stu-id="2500b-502">net"</span></span>
- <span data-ttu-id="2500b-503">Qualsiasi combinazione tra 1-300 lettere, cifre, simboli, caratteri speciali o spazi in maiuscolo o minuscolo</span><span class="sxs-lookup"><span data-stu-id="2500b-503">Any combination of between 1-300 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="2500b-504">La stringa "password", "password" o "pwd"</span><span class="sxs-lookup"><span data-stu-id="2500b-504">The string "Password", "password", or "pwd"</span></span>
- <span data-ttu-id="2500b-505">0-2 caratteri dello spazio vuoto</span><span class="sxs-lookup"><span data-stu-id="2500b-505">0-2 whitespace characters</span></span>
- <span data-ttu-id="2500b-506">Segno di uguale (=)</span><span class="sxs-lookup"><span data-stu-id="2500b-506">An equal sign (=)</span></span>
- <span data-ttu-id="2500b-507">0-2 caratteri dello spazio vuoto</span><span class="sxs-lookup"><span data-stu-id="2500b-507">0-2 whitespace characters</span></span>
- <span data-ttu-id="2500b-508">Uno o più caratteri non costituiti da un punto e virgola (;), virgolette (") o apostrofo (')</span><span class="sxs-lookup"><span data-stu-id="2500b-508">One or more characters that is not a semicolon (;), quotation mark ("), or apostrophe (')</span></span>
- <span data-ttu-id="2500b-509">Un punto e virgola (;), virgolette (") o apostrofo (')</span><span class="sxs-lookup"><span data-stu-id="2500b-509">A semicolon (;), quotation mark ("), or apostrophe (')</span></span>

### <a name="checksum"></a><span data-ttu-id="2500b-510">Checksum</span><span class="sxs-lookup"><span data-stu-id="2500b-510">Checksum</span></span>

<span data-ttu-id="2500b-511">No</span><span class="sxs-lookup"><span data-stu-id="2500b-511">No</span></span>

### <a name="definition"></a><span data-ttu-id="2500b-512">Definizione</span><span class="sxs-lookup"><span data-stu-id="2500b-512">Definition</span></span>

<span data-ttu-id="2500b-513">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="2500b-513">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2500b-514">L'espressione regolare CEP_Regex_AzureConnectionString trova il contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="2500b-514">The regular expression CEP_Regex_AzureConnectionString finds content that matches the pattern.</span></span>
- <span data-ttu-id="2500b-515">L'espressione regolare CEP_CommonExampleKeywords non \*\*\*\* trova contenuto corrispondente al modello.</span><span class="sxs-lookup"><span data-stu-id="2500b-515">The regular expression CEP_CommonExampleKeywords does **not** find content that matches the pattern.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="2500b-516">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="2500b-516">Keywords</span></span>

#### <a name="cepcommonexamplekeywords"></a><span data-ttu-id="2500b-517">CEP_CommonExampleKeywords</span><span class="sxs-lookup"><span data-stu-id="2500b-517">CEP_CommonExampleKeywords</span></span>

<span data-ttu-id="2500b-518">Si noti che tecnicamente questo tipo di informazioni riservate identifica queste parole chiave utilizzando un'espressione regolare, non un elenco di parola chiave.</span><span class="sxs-lookup"><span data-stu-id="2500b-518">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="2500b-519">contoso</span><span class="sxs-lookup"><span data-stu-id="2500b-519">contoso</span></span>
- <span data-ttu-id="2500b-520">Fabrikam</span><span class="sxs-lookup"><span data-stu-id="2500b-520">fabrikam</span></span>
- <span data-ttu-id="2500b-521">Northwind</span><span class="sxs-lookup"><span data-stu-id="2500b-521">northwind</span></span>
- <span data-ttu-id="2500b-522">sandbox</span><span class="sxs-lookup"><span data-stu-id="2500b-522">sandbox</span></span>
- <span data-ttu-id="2500b-523">OneBox</span><span class="sxs-lookup"><span data-stu-id="2500b-523">onebox</span></span>
- <span data-ttu-id="2500b-524">localhost</span><span class="sxs-lookup"><span data-stu-id="2500b-524">localhost</span></span>
- <span data-ttu-id="2500b-525">127.0.0.1</span><span class="sxs-lookup"><span data-stu-id="2500b-525">127.0.0.1</span></span>
- <span data-ttu-id="2500b-526">testacs.</span><span class="sxs-lookup"><span data-stu-id="2500b-526">testacs.</span></span><!--no-hyperlink--><span data-ttu-id="2500b-527">com</span><span class="sxs-lookup"><span data-stu-id="2500b-527">com</span></span>
- <span data-ttu-id="2500b-528">s-int.</span><span class="sxs-lookup"><span data-stu-id="2500b-528">s-int.</span></span><!--no-hyperlink--><span data-ttu-id="2500b-529">NET</span><span class="sxs-lookup"><span data-stu-id="2500b-529">net</span></span>

## <a name="azure-iot-connection-string"></a><span data-ttu-id="2500b-530">Stringa di connessione di Azure.</span><span class="sxs-lookup"><span data-stu-id="2500b-530">Azure IoT Connection String</span></span>

### <a name="format"></a><span data-ttu-id="2500b-531">Formato</span><span class="sxs-lookup"><span data-stu-id="2500b-531">Format</span></span>

<span data-ttu-id="2500b-532">La stringa "HostName" seguita dai caratteri e dalle stringhe delineati nel modello seguente, incluse le stringhe "Azure-Devices.</span><span class="sxs-lookup"><span data-stu-id="2500b-532">The string "HostName" followed by the characters and strings outlined in the pattern below, including the strings "azure-devices.</span></span><!--no-hyperlink--><span data-ttu-id="2500b-533">NET "e" SharedAccessKey ".</span><span class="sxs-lookup"><span data-stu-id="2500b-533">net" and "SharedAccessKey".</span></span>

### <a name="pattern"></a><span data-ttu-id="2500b-534">Modello</span><span class="sxs-lookup"><span data-stu-id="2500b-534">Pattern</span></span>

- <span data-ttu-id="2500b-535">La stringa "HostName"</span><span class="sxs-lookup"><span data-stu-id="2500b-535">The string "HostName"</span></span>
- <span data-ttu-id="2500b-536">0-2 caratteri dello spazio vuoto</span><span class="sxs-lookup"><span data-stu-id="2500b-536">0-2 whitespace characters</span></span>
- <span data-ttu-id="2500b-537">Segno di uguale (=)</span><span class="sxs-lookup"><span data-stu-id="2500b-537">An equal sign (=)</span></span>
- <span data-ttu-id="2500b-538">0-2 caratteri dello spazio vuoto</span><span class="sxs-lookup"><span data-stu-id="2500b-538">0-2 whitespace characters</span></span>
- <span data-ttu-id="2500b-539">Qualsiasi combinazione tra 1-200 lettere, cifre, simboli, caratteri speciali o spazi in maiuscolo o minuscolo</span><span class="sxs-lookup"><span data-stu-id="2500b-539">Any combination of between 1-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="2500b-540">La stringa "Azure-Devices.</span><span class="sxs-lookup"><span data-stu-id="2500b-540">The string "azure-devices.</span></span><!--no-hyperlink--><span data-ttu-id="2500b-541">NET</span><span class="sxs-lookup"><span data-stu-id="2500b-541">net"</span></span>
- <span data-ttu-id="2500b-542">Qualsiasi combinazione tra 1-200 lettere, cifre, simboli, caratteri speciali o spazi in maiuscolo o minuscolo</span><span class="sxs-lookup"><span data-stu-id="2500b-542">Any combination of between 1-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="2500b-543">La stringa "SharedAccessKey"</span><span class="sxs-lookup"><span data-stu-id="2500b-543">The string "SharedAccessKey"</span></span>
- <span data-ttu-id="2500b-544">0-2 caratteri dello spazio vuoto</span><span class="sxs-lookup"><span data-stu-id="2500b-544">0-2 whitespace characters</span></span>
- <span data-ttu-id="2500b-545">Segno di uguale (=)</span><span class="sxs-lookup"><span data-stu-id="2500b-545">An equal sign (=)</span></span>
- <span data-ttu-id="2500b-546">0-2 caratteri dello spazio vuoto</span><span class="sxs-lookup"><span data-stu-id="2500b-546">0-2 whitespace characters</span></span>
- <span data-ttu-id="2500b-547">Qualsiasi combinazione di 43 lettere maiuscole e minuscole, cifre, barra (/) o segno più (+)</span><span class="sxs-lookup"><span data-stu-id="2500b-547">Any combination of 43 lower- or uppercase letters, digits, forward slash (/), or plus sign (+)</span></span>
- <span data-ttu-id="2500b-548">Segno di uguale (=)</span><span class="sxs-lookup"><span data-stu-id="2500b-548">An equal sign (=)</span></span>

### <a name="checksum"></a><span data-ttu-id="2500b-549">Checksum</span><span class="sxs-lookup"><span data-stu-id="2500b-549">Checksum</span></span>

<span data-ttu-id="2500b-550">No</span><span class="sxs-lookup"><span data-stu-id="2500b-550">No</span></span>

### <a name="definition"></a><span data-ttu-id="2500b-551">Definizione</span><span class="sxs-lookup"><span data-stu-id="2500b-551">Definition</span></span>

<span data-ttu-id="2500b-552">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="2500b-552">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2500b-553">L'espressione regolare CEP_Regex_AzureIoTConnectionString trova il contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="2500b-553">The regular expression CEP_Regex_AzureIoTConnectionString finds content that matches the pattern.</span></span>
- <span data-ttu-id="2500b-554">L'espressione regolare CEP_CommonExampleKeywords non \*\*\*\* trova contenuto corrispondente al modello.</span><span class="sxs-lookup"><span data-stu-id="2500b-554">The regular expression CEP_CommonExampleKeywords does **not** find content that matches the pattern.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="2500b-555">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="2500b-555">Keywords</span></span>

#### <a name="cepcommonexamplekeywords"></a><span data-ttu-id="2500b-556">CEP_CommonExampleKeywords</span><span class="sxs-lookup"><span data-stu-id="2500b-556">CEP_CommonExampleKeywords</span></span>

<span data-ttu-id="2500b-557">Si noti che tecnicamente questo tipo di informazioni riservate identifica queste parole chiave utilizzando un'espressione regolare, non un elenco di parola chiave.</span><span class="sxs-lookup"><span data-stu-id="2500b-557">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="2500b-558">contoso</span><span class="sxs-lookup"><span data-stu-id="2500b-558">contoso</span></span>
- <span data-ttu-id="2500b-559">Fabrikam</span><span class="sxs-lookup"><span data-stu-id="2500b-559">fabrikam</span></span>
- <span data-ttu-id="2500b-560">Northwind</span><span class="sxs-lookup"><span data-stu-id="2500b-560">northwind</span></span>
- <span data-ttu-id="2500b-561">sandbox</span><span class="sxs-lookup"><span data-stu-id="2500b-561">sandbox</span></span>
- <span data-ttu-id="2500b-562">OneBox</span><span class="sxs-lookup"><span data-stu-id="2500b-562">onebox</span></span>
- <span data-ttu-id="2500b-563">localhost</span><span class="sxs-lookup"><span data-stu-id="2500b-563">localhost</span></span>
- <span data-ttu-id="2500b-564">127.0.0.1</span><span class="sxs-lookup"><span data-stu-id="2500b-564">127.0.0.1</span></span>
- <span data-ttu-id="2500b-565">testacs.</span><span class="sxs-lookup"><span data-stu-id="2500b-565">testacs.</span></span><!--no-hyperlink--><span data-ttu-id="2500b-566">com</span><span class="sxs-lookup"><span data-stu-id="2500b-566">com</span></span>
- <span data-ttu-id="2500b-567">s-int.</span><span class="sxs-lookup"><span data-stu-id="2500b-567">s-int.</span></span><!--no-hyperlink--><span data-ttu-id="2500b-568">NET</span><span class="sxs-lookup"><span data-stu-id="2500b-568">net</span></span>

## <a name="azure-publish-setting-password"></a><span data-ttu-id="2500b-569">Password per l'impostazione di pubblicazione di Azure</span><span class="sxs-lookup"><span data-stu-id="2500b-569">Azure Publish Setting Password</span></span>

### <a name="format"></a><span data-ttu-id="2500b-570">Formato</span><span class="sxs-lookup"><span data-stu-id="2500b-570">Format</span></span>

<span data-ttu-id="2500b-571">La stringa "UserPwd =" seguita da una stringa alfanumerica.</span><span class="sxs-lookup"><span data-stu-id="2500b-571">The string "userpwd=" followed by an alphanumeric string.</span></span>

### <a name="pattern"></a><span data-ttu-id="2500b-572">Modello</span><span class="sxs-lookup"><span data-stu-id="2500b-572">Pattern</span></span>

- <span data-ttu-id="2500b-573">La stringa "UserPwd ="</span><span class="sxs-lookup"><span data-stu-id="2500b-573">The string "userpwd="</span></span>
- <span data-ttu-id="2500b-574">Qualsiasi combinazione di lettere o cifre minuscole di 60</span><span class="sxs-lookup"><span data-stu-id="2500b-574">Any combination of 60 lowercase letters or digits</span></span>
- <span data-ttu-id="2500b-575">Virgolette (")</span><span class="sxs-lookup"><span data-stu-id="2500b-575">A quotation mark (")</span></span>

### <a name="checksum"></a><span data-ttu-id="2500b-576">Checksum</span><span class="sxs-lookup"><span data-stu-id="2500b-576">Checksum</span></span>

<span data-ttu-id="2500b-577">No</span><span class="sxs-lookup"><span data-stu-id="2500b-577">No</span></span>

### <a name="definition"></a><span data-ttu-id="2500b-578">Definizione</span><span class="sxs-lookup"><span data-stu-id="2500b-578">Definition</span></span>

<span data-ttu-id="2500b-579">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="2500b-579">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2500b-580">L'espressione regolare CEP_Regex_AzurePublishSettingPasswords trova il contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="2500b-580">The regular expression CEP_Regex_AzurePublishSettingPasswords finds content that matches the pattern.</span></span>
- <span data-ttu-id="2500b-581">L'espressione regolare CEP_CommonExampleKeywords non \*\*\*\* trova contenuto corrispondente al modello.</span><span class="sxs-lookup"><span data-stu-id="2500b-581">The regular expression CEP_CommonExampleKeywords does **not** find content that matches the pattern.</span></span>


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

### <a name="keywords"></a><span data-ttu-id="2500b-582">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="2500b-582">Keywords</span></span>

#### <a name="cepcommonexamplekeywords"></a><span data-ttu-id="2500b-583">CEP_CommonExampleKeywords</span><span class="sxs-lookup"><span data-stu-id="2500b-583">CEP_CommonExampleKeywords</span></span>

<span data-ttu-id="2500b-584">Si noti che tecnicamente questo tipo di informazioni riservate identifica queste parole chiave utilizzando un'espressione regolare, non un elenco di parola chiave.</span><span class="sxs-lookup"><span data-stu-id="2500b-584">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="2500b-585">contoso</span><span class="sxs-lookup"><span data-stu-id="2500b-585">contoso</span></span>
- <span data-ttu-id="2500b-586">Fabrikam</span><span class="sxs-lookup"><span data-stu-id="2500b-586">fabrikam</span></span>
- <span data-ttu-id="2500b-587">Northwind</span><span class="sxs-lookup"><span data-stu-id="2500b-587">northwind</span></span>
- <span data-ttu-id="2500b-588">sandbox</span><span class="sxs-lookup"><span data-stu-id="2500b-588">sandbox</span></span>
- <span data-ttu-id="2500b-589">OneBox</span><span class="sxs-lookup"><span data-stu-id="2500b-589">onebox</span></span>
- <span data-ttu-id="2500b-590">localhost</span><span class="sxs-lookup"><span data-stu-id="2500b-590">localhost</span></span>
- <span data-ttu-id="2500b-591">127.0.0.1</span><span class="sxs-lookup"><span data-stu-id="2500b-591">127.0.0.1</span></span>
- <span data-ttu-id="2500b-592">testacs.</span><span class="sxs-lookup"><span data-stu-id="2500b-592">testacs.</span></span><!--no-hyperlink--><span data-ttu-id="2500b-593">com</span><span class="sxs-lookup"><span data-stu-id="2500b-593">com</span></span>
- <span data-ttu-id="2500b-594">s-int.</span><span class="sxs-lookup"><span data-stu-id="2500b-594">s-int.</span></span><!--no-hyperlink--><span data-ttu-id="2500b-595">NET</span><span class="sxs-lookup"><span data-stu-id="2500b-595">net</span></span>

## <a name="azure-redis-cache-connection-string"></a><span data-ttu-id="2500b-596">Stringa di connessione della cache di Azure Redis</span><span class="sxs-lookup"><span data-stu-id="2500b-596">Azure Redis Cache Connection String</span></span>

### <a name="format"></a><span data-ttu-id="2500b-597">Formato</span><span class="sxs-lookup"><span data-stu-id="2500b-597">Format</span></span>

<span data-ttu-id="2500b-598">La stringa "Redis. cache. Windows.</span><span class="sxs-lookup"><span data-stu-id="2500b-598">The string "redis.cache.windows.</span></span><!--no-hyperlink--><span data-ttu-id="2500b-599">NET "seguito dai caratteri e dalle stringhe delineati nel modello seguente, inclusa la stringa" password "o" pwd ".</span><span class="sxs-lookup"><span data-stu-id="2500b-599">net" followed by the characters and strings outlined in the pattern below, including the string "password" or "pwd".</span></span>

### <a name="pattern"></a><span data-ttu-id="2500b-600">Modello</span><span class="sxs-lookup"><span data-stu-id="2500b-600">Pattern</span></span>

- <span data-ttu-id="2500b-601">La stringa "Redis. cache. Windows.</span><span class="sxs-lookup"><span data-stu-id="2500b-601">The string "redis.cache.windows.</span></span><!--no-hyperlink--><span data-ttu-id="2500b-602">NET</span><span class="sxs-lookup"><span data-stu-id="2500b-602">net"</span></span>
- <span data-ttu-id="2500b-603">Qualsiasi combinazione tra 1-200 lettere, cifre, simboli, caratteri speciali o spazi in maiuscolo o minuscolo</span><span class="sxs-lookup"><span data-stu-id="2500b-603">Any combination of between 1-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="2500b-604">La stringa "password" o "pwd"</span><span class="sxs-lookup"><span data-stu-id="2500b-604">The string "password" or "pwd"</span></span>
- <span data-ttu-id="2500b-605">0-2 caratteri dello spazio vuoto</span><span class="sxs-lookup"><span data-stu-id="2500b-605">0-2 whitespace characters</span></span>
- <span data-ttu-id="2500b-606">Segno di uguale (=)</span><span class="sxs-lookup"><span data-stu-id="2500b-606">An equal sign (=)</span></span>
- <span data-ttu-id="2500b-607">0-2 caratteri dello spazio vuoto</span><span class="sxs-lookup"><span data-stu-id="2500b-607">0-2 whitespace characters</span></span>
- <span data-ttu-id="2500b-608">Qualsiasi combinazione di 43 caratteri che sono lettere maiuscole o minuscole, cifre, barra (/) o segno più (+)</span><span class="sxs-lookup"><span data-stu-id="2500b-608">Any combination of 43 characters that are lower- or uppercase letters, digits, forward slash (/), or plus sign (+)</span></span>
- <span data-ttu-id="2500b-609">Segno di uguale (=)</span><span class="sxs-lookup"><span data-stu-id="2500b-609">An equal sign (=)</span></span>

### <a name="checksum"></a><span data-ttu-id="2500b-610">Checksum</span><span class="sxs-lookup"><span data-stu-id="2500b-610">Checksum</span></span>

<span data-ttu-id="2500b-611">No</span><span class="sxs-lookup"><span data-stu-id="2500b-611">No</span></span>

### <a name="definition"></a><span data-ttu-id="2500b-612">Definizione</span><span class="sxs-lookup"><span data-stu-id="2500b-612">Definition</span></span>

<span data-ttu-id="2500b-613">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="2500b-613">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2500b-614">L'espressione regolare CEP_Regex_AzureRedisCacheConnectionString trova il contenuto corrispondente al modello.</span><span class="sxs-lookup"><span data-stu-id="2500b-614">The regular expression CEP_Regex_AzureRedisCacheConnectionString finds content that matches the pattern..</span></span>
- <span data-ttu-id="2500b-615">L'espressione regolare CEP_CommonExampleKeywords non \*\*\*\* trova contenuto corrispondente al modello.</span><span class="sxs-lookup"><span data-stu-id="2500b-615">The regular expression CEP_CommonExampleKeywords does **not** find content that matches the pattern.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="2500b-616">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="2500b-616">Keywords</span></span>

#### <a name="cepcommonexamplekeywords"></a><span data-ttu-id="2500b-617">CEP_CommonExampleKeywords</span><span class="sxs-lookup"><span data-stu-id="2500b-617">CEP_CommonExampleKeywords</span></span>

<span data-ttu-id="2500b-618">Si noti che tecnicamente questo tipo di informazioni riservate identifica queste parole chiave utilizzando un'espressione regolare, non un elenco di parola chiave.</span><span class="sxs-lookup"><span data-stu-id="2500b-618">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="2500b-619">contoso</span><span class="sxs-lookup"><span data-stu-id="2500b-619">contoso</span></span>
- <span data-ttu-id="2500b-620">Fabrikam</span><span class="sxs-lookup"><span data-stu-id="2500b-620">fabrikam</span></span>
- <span data-ttu-id="2500b-621">Northwind</span><span class="sxs-lookup"><span data-stu-id="2500b-621">northwind</span></span>
- <span data-ttu-id="2500b-622">sandbox</span><span class="sxs-lookup"><span data-stu-id="2500b-622">sandbox</span></span>
- <span data-ttu-id="2500b-623">OneBox</span><span class="sxs-lookup"><span data-stu-id="2500b-623">onebox</span></span>
- <span data-ttu-id="2500b-624">localhost</span><span class="sxs-lookup"><span data-stu-id="2500b-624">localhost</span></span>
- <span data-ttu-id="2500b-625">127.0.0.1</span><span class="sxs-lookup"><span data-stu-id="2500b-625">127.0.0.1</span></span>
- <span data-ttu-id="2500b-626">testacs.</span><span class="sxs-lookup"><span data-stu-id="2500b-626">testacs.</span></span><!--no-hyperlink--><span data-ttu-id="2500b-627">com</span><span class="sxs-lookup"><span data-stu-id="2500b-627">com</span></span>
- <span data-ttu-id="2500b-628">s-int.</span><span class="sxs-lookup"><span data-stu-id="2500b-628">s-int.</span></span><!--no-hyperlink--><span data-ttu-id="2500b-629">NET</span><span class="sxs-lookup"><span data-stu-id="2500b-629">net</span></span>

## <a name="azure-sas"></a><span data-ttu-id="2500b-630">SAS di Azure</span><span class="sxs-lookup"><span data-stu-id="2500b-630">Azure SAS</span></span>

### <a name="format"></a><span data-ttu-id="2500b-631">Formato</span><span class="sxs-lookup"><span data-stu-id="2500b-631">Format</span></span>

<span data-ttu-id="2500b-632">La stringa "sig" seguita dai caratteri e dalle stringhe delineate nel modello seguente.</span><span class="sxs-lookup"><span data-stu-id="2500b-632">The string "sig" followed by the characters and strings outlined in the pattern below.</span></span>

### <a name="pattern"></a><span data-ttu-id="2500b-633">Modello</span><span class="sxs-lookup"><span data-stu-id="2500b-633">Pattern</span></span>

- <span data-ttu-id="2500b-634">La stringa "sig"</span><span class="sxs-lookup"><span data-stu-id="2500b-634">The string "sig"</span></span>
- <span data-ttu-id="2500b-635">0-2 caratteri dello spazio vuoto</span><span class="sxs-lookup"><span data-stu-id="2500b-635">0-2 whitespace characters</span></span>
- <span data-ttu-id="2500b-636">Segno di uguale (=)</span><span class="sxs-lookup"><span data-stu-id="2500b-636">An equal sign (=)</span></span>
- <span data-ttu-id="2500b-637">0-2 caratteri dello spazio vuoto</span><span class="sxs-lookup"><span data-stu-id="2500b-637">0-2 whitespace characters</span></span>
- <span data-ttu-id="2500b-638">Qualsiasi combinazione tra 43-53 caratteri che sono minuscoli o maiuscoli, cifre o il segno di percentuale (%)</span><span class="sxs-lookup"><span data-stu-id="2500b-638">Any combination of between 43-53 characters that are lower- or uppercase letters, digits, or the percent sign (%)</span></span>
- <span data-ttu-id="2500b-639">La stringa "% 3D"</span><span class="sxs-lookup"><span data-stu-id="2500b-639">The string "%3d"</span></span>
- <span data-ttu-id="2500b-640">Qualsiasi carattere che non sia una lettera, una cifra o un segno di percentuale inferiore o maiuscolo (%)</span><span class="sxs-lookup"><span data-stu-id="2500b-640">Any character that is not a lower- or uppercase letter, digit, or percent sign (%)</span></span>

### <a name="checksum"></a><span data-ttu-id="2500b-641">Checksum</span><span class="sxs-lookup"><span data-stu-id="2500b-641">Checksum</span></span>

<span data-ttu-id="2500b-642">No</span><span class="sxs-lookup"><span data-stu-id="2500b-642">No</span></span>

### <a name="definition"></a><span data-ttu-id="2500b-643">Definizione</span><span class="sxs-lookup"><span data-stu-id="2500b-643">Definition</span></span>

<span data-ttu-id="2500b-644">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="2500b-644">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2500b-645">L'espressione regolare CEP_Regex_AzureSAS trova il contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="2500b-645">The regular expression CEP_Regex_AzureSAS finds content that matches the pattern.</span></span>

```
<!--Azure SAS-->
<Entity id="4d235014-e564-47f4-a6fb-6ebb4a826834" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_AzureSAS" />
  </Pattern>
</Entity>
```

## <a name="azure-service-bus-connection-string"></a><span data-ttu-id="2500b-646">Stringa di connessione bus di servizio di Azure</span><span class="sxs-lookup"><span data-stu-id="2500b-646">Azure Service Bus Connection String</span></span>

### <a name="format"></a><span data-ttu-id="2500b-647">Formato</span><span class="sxs-lookup"><span data-stu-id="2500b-647">Format</span></span>

<span data-ttu-id="2500b-648">Stringa "EndPoint" seguita dai caratteri e dalle stringhe delineati nel modello seguente, incluse le stringhe "ServiceBus. Windows.</span><span class="sxs-lookup"><span data-stu-id="2500b-648">The string "EndPoint" followed by the characters and strings outlined in the pattern below, including the strings "servicebus.windows.</span></span><!--no-hyperlink--><span data-ttu-id="2500b-649">NET "e" SharedAccesKey ".</span><span class="sxs-lookup"><span data-stu-id="2500b-649">net" and "SharedAccesKey".</span></span>

### <a name="pattern"></a><span data-ttu-id="2500b-650">Modello</span><span class="sxs-lookup"><span data-stu-id="2500b-650">Pattern</span></span>

- <span data-ttu-id="2500b-651">La stringa "EndPoint"</span><span class="sxs-lookup"><span data-stu-id="2500b-651">The string "EndPoint"</span></span>
- <span data-ttu-id="2500b-652">0-2 caratteri dello spazio vuoto</span><span class="sxs-lookup"><span data-stu-id="2500b-652">0-2 whitespace characters</span></span>
- <span data-ttu-id="2500b-653">Segno di uguale (=)</span><span class="sxs-lookup"><span data-stu-id="2500b-653">An equal sign (=)</span></span>
- <span data-ttu-id="2500b-654">0-2 caratteri dello spazio vuoto</span><span class="sxs-lookup"><span data-stu-id="2500b-654">0-2 whitespace characters</span></span>
- <span data-ttu-id="2500b-655">Qualsiasi combinazione tra 1-200 lettere, cifre, simboli, caratteri speciali o spazi in maiuscolo o minuscolo</span><span class="sxs-lookup"><span data-stu-id="2500b-655">Any combination of between 1-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="2500b-656">La stringa "ServiceBus. Windows.</span><span class="sxs-lookup"><span data-stu-id="2500b-656">The string "servicebus.windows.</span></span><!--no-hyperlink--><span data-ttu-id="2500b-657">NET</span><span class="sxs-lookup"><span data-stu-id="2500b-657">net"</span></span>
- <span data-ttu-id="2500b-658">Qualsiasi combinazione tra 1-200 lettere, cifre, simboli, caratteri speciali o spazi in maiuscolo o minuscolo</span><span class="sxs-lookup"><span data-stu-id="2500b-658">Any combination of between 1-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="2500b-659">La stringa "SharedAccessKey"</span><span class="sxs-lookup"><span data-stu-id="2500b-659">The string "SharedAccessKey"</span></span>
- <span data-ttu-id="2500b-660">0-2 caratteri dello spazio vuoto</span><span class="sxs-lookup"><span data-stu-id="2500b-660">0-2 whitespace characters</span></span>
- <span data-ttu-id="2500b-661">Segno di uguale (=)</span><span class="sxs-lookup"><span data-stu-id="2500b-661">An equal sign (=)</span></span>
- <span data-ttu-id="2500b-662">0-2 caratteri dello spazio vuoto</span><span class="sxs-lookup"><span data-stu-id="2500b-662">0-2 whitespace characters</span></span>
- <span data-ttu-id="2500b-663">Qualsiasi combinazione di 43 caratteri che sono lettere maiuscole o minuscole, cifre, barra (/) o segno più (+)</span><span class="sxs-lookup"><span data-stu-id="2500b-663">Any combination of 43 characters that are lower- or uppercase letters, digits, forward slash (/), or plus sign (+)</span></span>
- <span data-ttu-id="2500b-664">Segno di uguale (=)</span><span class="sxs-lookup"><span data-stu-id="2500b-664">An equal sign (=)</span></span>

### <a name="checksum"></a><span data-ttu-id="2500b-665">Checksum</span><span class="sxs-lookup"><span data-stu-id="2500b-665">Checksum</span></span>

<span data-ttu-id="2500b-666">No</span><span class="sxs-lookup"><span data-stu-id="2500b-666">No</span></span>

### <a name="definition"></a><span data-ttu-id="2500b-667">Definizione</span><span class="sxs-lookup"><span data-stu-id="2500b-667">Definition</span></span>

<span data-ttu-id="2500b-668">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="2500b-668">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2500b-669">L'espressione regolare CEP_Regex_AzureServiceBusConnectionString trova il contenuto corrispondente al modello.</span><span class="sxs-lookup"><span data-stu-id="2500b-669">The regular expression CEP_Regex_AzureServiceBusConnectionString finds content that matches the pattern..</span></span>
- <span data-ttu-id="2500b-670">L'espressione regolare CEP_CommonExampleKeywords non \*\*\*\* trova contenuto corrispondente al modello.</span><span class="sxs-lookup"><span data-stu-id="2500b-670">The regular expression CEP_CommonExampleKeywords does **not** find content that matches the pattern.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="2500b-671">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="2500b-671">Keywords</span></span>

#### <a name="cepcommonexamplekeywords"></a><span data-ttu-id="2500b-672">CEP_CommonExampleKeywords</span><span class="sxs-lookup"><span data-stu-id="2500b-672">CEP_CommonExampleKeywords</span></span>

<span data-ttu-id="2500b-673">Si noti che tecnicamente questo tipo di informazioni riservate identifica queste parole chiave utilizzando un'espressione regolare, non un elenco di parola chiave.</span><span class="sxs-lookup"><span data-stu-id="2500b-673">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="2500b-674">contoso</span><span class="sxs-lookup"><span data-stu-id="2500b-674">contoso</span></span>
- <span data-ttu-id="2500b-675">Fabrikam</span><span class="sxs-lookup"><span data-stu-id="2500b-675">fabrikam</span></span>
- <span data-ttu-id="2500b-676">Northwind</span><span class="sxs-lookup"><span data-stu-id="2500b-676">northwind</span></span>
- <span data-ttu-id="2500b-677">sandbox</span><span class="sxs-lookup"><span data-stu-id="2500b-677">sandbox</span></span>
- <span data-ttu-id="2500b-678">OneBox</span><span class="sxs-lookup"><span data-stu-id="2500b-678">onebox</span></span>
- <span data-ttu-id="2500b-679">localhost</span><span class="sxs-lookup"><span data-stu-id="2500b-679">localhost</span></span>
- <span data-ttu-id="2500b-680">127.0.0.1</span><span class="sxs-lookup"><span data-stu-id="2500b-680">127.0.0.1</span></span>
- <span data-ttu-id="2500b-681">testacs.</span><span class="sxs-lookup"><span data-stu-id="2500b-681">testacs.</span></span><!--no-hyperlink--><span data-ttu-id="2500b-682">com</span><span class="sxs-lookup"><span data-stu-id="2500b-682">com</span></span>
- <span data-ttu-id="2500b-683">s-int.</span><span class="sxs-lookup"><span data-stu-id="2500b-683">s-int.</span></span><!--no-hyperlink--><span data-ttu-id="2500b-684">NET</span><span class="sxs-lookup"><span data-stu-id="2500b-684">net</span></span>

## <a name="azure-storage-account-key"></a><span data-ttu-id="2500b-685">Chiave dell'account di archiviazione di Azure</span><span class="sxs-lookup"><span data-stu-id="2500b-685">Azure Storage Account Key</span></span>

### <a name="format"></a><span data-ttu-id="2500b-686">Formato</span><span class="sxs-lookup"><span data-stu-id="2500b-686">Format</span></span>

<span data-ttu-id="2500b-687">La stringa "DefaultEndpointsProtocol" seguita dai caratteri e dalle stringhe delineate nel modello seguente, inclusa la stringa "AccountKey".</span><span class="sxs-lookup"><span data-stu-id="2500b-687">The string "DefaultEndpointsProtocol" followed by the characters and strings outlined in the pattern below, including the string "AccountKey".</span></span>

### <a name="pattern"></a><span data-ttu-id="2500b-688">Modello</span><span class="sxs-lookup"><span data-stu-id="2500b-688">Pattern</span></span>

- <span data-ttu-id="2500b-689">La stringa "DefaultEndpointsProtocol"</span><span class="sxs-lookup"><span data-stu-id="2500b-689">The string "DefaultEndpointsProtocol"</span></span>
- <span data-ttu-id="2500b-690">0-2 caratteri dello spazio vuoto</span><span class="sxs-lookup"><span data-stu-id="2500b-690">0-2 whitespace characters</span></span>
- <span data-ttu-id="2500b-691">Segno di uguale (=)</span><span class="sxs-lookup"><span data-stu-id="2500b-691">An equal sign (=)</span></span>
- <span data-ttu-id="2500b-692">0-2 caratteri dello spazio vuoto</span><span class="sxs-lookup"><span data-stu-id="2500b-692">0-2 whitespace characters</span></span>
- <span data-ttu-id="2500b-693">Qualsiasi combinazione tra 1-200 lettere, cifre, simboli, caratteri speciali o spazi in maiuscolo o minuscolo</span><span class="sxs-lookup"><span data-stu-id="2500b-693">Any combination of between 1-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="2500b-694">La stringa "AccountKey"</span><span class="sxs-lookup"><span data-stu-id="2500b-694">The string "AccountKey"</span></span>
- <span data-ttu-id="2500b-695">0-2 caratteri dello spazio vuoto</span><span class="sxs-lookup"><span data-stu-id="2500b-695">0-2 whitespace characters</span></span>
- <span data-ttu-id="2500b-696">Segno di uguale (=)</span><span class="sxs-lookup"><span data-stu-id="2500b-696">An equal sign (=)</span></span>
- <span data-ttu-id="2500b-697">0-2 caratteri dello spazio vuoto</span><span class="sxs-lookup"><span data-stu-id="2500b-697">0-2 whitespace characters</span></span>
- <span data-ttu-id="2500b-698">Qualsiasi combinazione di 86 caratteri che sono lettere maiuscole o minuscole, cifre, barra (/) o segno più (+)</span><span class="sxs-lookup"><span data-stu-id="2500b-698">Any combination of 86 characters that are lower- or uppercase letters, digits, forward slash (/), or plus sign (+)</span></span>
- <span data-ttu-id="2500b-699">Due segni uguali (=)</span><span class="sxs-lookup"><span data-stu-id="2500b-699">Two equal signs (=)</span></span>

### <a name="checksum"></a><span data-ttu-id="2500b-700">Checksum</span><span class="sxs-lookup"><span data-stu-id="2500b-700">Checksum</span></span>

<span data-ttu-id="2500b-701">No</span><span class="sxs-lookup"><span data-stu-id="2500b-701">No</span></span>

### <a name="definition"></a><span data-ttu-id="2500b-702">Definizione</span><span class="sxs-lookup"><span data-stu-id="2500b-702">Definition</span></span>

<span data-ttu-id="2500b-703">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="2500b-703">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2500b-704">L'espressione regolare CEP_Regex_AzureStorageAccountKey trova il contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="2500b-704">The regular expression CEP_Regex_AzureStorageAccountKey finds content that matches the pattern.</span></span>
- <span data-ttu-id="2500b-705">L'espressione regolare CEP_AzureEmulatorStorageAccountFilter non \*\*\*\* trova contenuto corrispondente al modello.</span><span class="sxs-lookup"><span data-stu-id="2500b-705">The regular expression CEP_AzureEmulatorStorageAccountFilter does **not** find content that matches the pattern.</span></span>
- <span data-ttu-id="2500b-706">L'espressione regolare CEP_CommonExampleKeywords non \*\*\*\* trova contenuto corrispondente al modello.</span><span class="sxs-lookup"><span data-stu-id="2500b-706">The regular expression CEP_CommonExampleKeywords does **not** find content that matches the pattern.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="2500b-707">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="2500b-707">Keywords</span></span>

#### <a name="cepazureemulatorstorageaccountfilter"></a><span data-ttu-id="2500b-708">CEP_AzureEmulatorStorageAccountFilter</span><span class="sxs-lookup"><span data-stu-id="2500b-708">CEP_AzureEmulatorStorageAccountFilter</span></span>

<span data-ttu-id="2500b-709">Si noti che tecnicamente questo tipo di informazioni riservate identifica queste parole chiave utilizzando un'espressione regolare, non un elenco di parola chiave.</span><span class="sxs-lookup"><span data-stu-id="2500b-709">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="2500b-710">Eby8vdM02xNOcqFlqUwJPLlmEtlCDXJ1OUzFT50uSRZ6IFsuFq2UVErCz4I6tq/K1SZFPTOtr/KBHBeksoGMGw = =</span><span class="sxs-lookup"><span data-stu-id="2500b-710">Eby8vdM02xNOcqFlqUwJPLlmEtlCDXJ1OUzFT50uSRZ6IFsuFq2UVErCz4I6tq/K1SZFPTOtr/KBHBeksoGMGw==</span></span>

#### <a name="cepcommonexamplekeywords"></a><span data-ttu-id="2500b-711">CEP_CommonExampleKeywords</span><span class="sxs-lookup"><span data-stu-id="2500b-711">CEP_CommonExampleKeywords</span></span>

<span data-ttu-id="2500b-712">Si noti che tecnicamente questo tipo di informazioni riservate identifica queste parole chiave utilizzando un'espressione regolare, non un elenco di parola chiave.</span><span class="sxs-lookup"><span data-stu-id="2500b-712">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="2500b-713">contoso</span><span class="sxs-lookup"><span data-stu-id="2500b-713">contoso</span></span>
- <span data-ttu-id="2500b-714">Fabrikam</span><span class="sxs-lookup"><span data-stu-id="2500b-714">fabrikam</span></span>
- <span data-ttu-id="2500b-715">Northwind</span><span class="sxs-lookup"><span data-stu-id="2500b-715">northwind</span></span>
- <span data-ttu-id="2500b-716">sandbox</span><span class="sxs-lookup"><span data-stu-id="2500b-716">sandbox</span></span>
- <span data-ttu-id="2500b-717">OneBox</span><span class="sxs-lookup"><span data-stu-id="2500b-717">onebox</span></span>
- <span data-ttu-id="2500b-718">localhost</span><span class="sxs-lookup"><span data-stu-id="2500b-718">localhost</span></span>
- <span data-ttu-id="2500b-719">127.0.0.1</span><span class="sxs-lookup"><span data-stu-id="2500b-719">127.0.0.1</span></span>
- <span data-ttu-id="2500b-720">testacs.</span><span class="sxs-lookup"><span data-stu-id="2500b-720">testacs.</span></span><!--no-hyperlink--><span data-ttu-id="2500b-721">com</span><span class="sxs-lookup"><span data-stu-id="2500b-721">com</span></span>
- <span data-ttu-id="2500b-722">s-int.</span><span class="sxs-lookup"><span data-stu-id="2500b-722">s-int.</span></span><!--no-hyperlink--><span data-ttu-id="2500b-723">NET</span><span class="sxs-lookup"><span data-stu-id="2500b-723">net</span></span>

## <a name="azure-storage-account-key-generic"></a><span data-ttu-id="2500b-724">Chiave dell'account di archiviazione di Azure (generico)</span><span class="sxs-lookup"><span data-stu-id="2500b-724">Azure Storage Account Key (Generic)</span></span>

### <a name="format"></a><span data-ttu-id="2500b-725">Formato</span><span class="sxs-lookup"><span data-stu-id="2500b-725">Format</span></span>

<span data-ttu-id="2500b-726">Qualsiasi combinazione di 86 lettere maiuscole e minuscole, cifre, barra (/) o segno più (+), preceduto o seguito dai caratteri delineati nel modello seguente.</span><span class="sxs-lookup"><span data-stu-id="2500b-726">Any combination of 86 lower- or uppercase letters, digits, the forward slash (/), or plus sign (+), preceded or followed by the characters outlined in the pattern below.</span></span>

### <a name="pattern"></a><span data-ttu-id="2500b-727">Modello</span><span class="sxs-lookup"><span data-stu-id="2500b-727">Pattern</span></span>

- <span data-ttu-id="2500b-728">0-1 del simbolo maggiore di (>), apostrofo ('), segno di uguale (=), virgolette (") o segno numerico (#)</span><span class="sxs-lookup"><span data-stu-id="2500b-728">0-1 of the greater than symbol (>), apostrophe ('), equal sign (=), quotation mark ("), or number sign (#)</span></span>
- <span data-ttu-id="2500b-729">Qualsiasi combinazione di 86 caratteri che sono lettere maiuscole o minuscole, cifre, barra (/) o segno più (+)</span><span class="sxs-lookup"><span data-stu-id="2500b-729">Any combination of 86 characters that are lower- or uppercase letters, digits, the forward slash (/), or plus sign (+)</span></span>
- <span data-ttu-id="2500b-730">Due segni uguali (=)</span><span class="sxs-lookup"><span data-stu-id="2500b-730">Two equal signs (=)</span></span>


### <a name="checksum"></a><span data-ttu-id="2500b-731">Checksum</span><span class="sxs-lookup"><span data-stu-id="2500b-731">Checksum</span></span>

<span data-ttu-id="2500b-732">No</span><span class="sxs-lookup"><span data-stu-id="2500b-732">No</span></span>

### <a name="definition"></a><span data-ttu-id="2500b-733">Definizione</span><span class="sxs-lookup"><span data-stu-id="2500b-733">Definition</span></span>

<span data-ttu-id="2500b-734">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="2500b-734">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2500b-735">L'espressione regolare CEP_Regex_AzureStorageAccountKeyGeneric trova il contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="2500b-735">The regular expression CEP_Regex_AzureStorageAccountKeyGeneric finds content that matches the pattern.</span></span>

```
<!--Azure Storage Account Key (Generic)-->
<Entity id="7ff41bd0-5419-4523-91d6-383b3a37f084" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_AzureStorageAccountKeyGeneric" />
  </Pattern>
</Entity>
```

## <a name="belgium-national-number"></a><span data-ttu-id="2500b-736">Belgio - Numero nazionale</span><span class="sxs-lookup"><span data-stu-id="2500b-736">Belgium National Number</span></span>

### <a name="format"></a><span data-ttu-id="2500b-737">Formato</span><span class="sxs-lookup"><span data-stu-id="2500b-737">Format</span></span>

<span data-ttu-id="2500b-738">11 cifre più delimitatori</span><span class="sxs-lookup"><span data-stu-id="2500b-738">11 digits plus delimiters</span></span>

### <a name="pattern"></a><span data-ttu-id="2500b-739">Modello</span><span class="sxs-lookup"><span data-stu-id="2500b-739">Pattern</span></span>

<span data-ttu-id="2500b-740">11 cifre più delimitatori:</span><span class="sxs-lookup"><span data-stu-id="2500b-740">11 digits plus delimiters:</span></span>
- <span data-ttu-id="2500b-741">Sei cifre e due punti nel formato AA.MM.GG per data di nascita </span><span class="sxs-lookup"><span data-stu-id="2500b-741">Six digits and two periods in the format YY.MM.DD for date of birth</span></span> 
- <span data-ttu-id="2500b-742">Una lineetta</span><span class="sxs-lookup"><span data-stu-id="2500b-742">A hyphen</span></span> 
- <span data-ttu-id="2500b-743">Tre cifre sequenziali (dispari sia per uomini che per donne) </span><span class="sxs-lookup"><span data-stu-id="2500b-743">Three sequential digits (odd for males, even for females)</span></span> 
- <span data-ttu-id="2500b-744">Un punto</span><span class="sxs-lookup"><span data-stu-id="2500b-744">A period</span></span> 
- <span data-ttu-id="2500b-745">Due cifre, ovvero una cifra di controllo</span><span class="sxs-lookup"><span data-stu-id="2500b-745">Two digits that are a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="2500b-746">Checksum</span><span class="sxs-lookup"><span data-stu-id="2500b-746">Checksum</span></span>

<span data-ttu-id="2500b-747">Sì</span><span class="sxs-lookup"><span data-stu-id="2500b-747">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="2500b-748">Definizione</span><span class="sxs-lookup"><span data-stu-id="2500b-748">Definition</span></span>

<span data-ttu-id="2500b-749">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="2500b-749">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2500b-750">La funzione Func_belgium_national_number trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="2500b-750">The function Func_belgium_national_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="2500b-751">Viene trovata una parola chiave da Keyword_belgium_national_number.</span><span class="sxs-lookup"><span data-stu-id="2500b-751">A keyword from Keyword_belgium_national_number is found.</span></span>
- <span data-ttu-id="2500b-752">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="2500b-752">The checksum passes.</span></span>

```
<!-- Belgium National Number -->
  <Entity id="fb969c9e-0fd1-4b18-8091-a2123c5e6a54" recommendedConfidence="75" patternsProximity="300">
   <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_belgium_national_number"/>
     <Match idRef="Keyword_belgium_national_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="2500b-753">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="2500b-753">Keywords</span></span>

#### <a name="keywordbelgiumnationalnumber"></a><span data-ttu-id="2500b-754">Keyword_belgium_national_number</span><span class="sxs-lookup"><span data-stu-id="2500b-754">Keyword_belgium_national_number</span></span>

- <span data-ttu-id="2500b-755">Identità</span><span class="sxs-lookup"><span data-stu-id="2500b-755">Identity</span></span>
- <span data-ttu-id="2500b-756">Registrazione</span><span class="sxs-lookup"><span data-stu-id="2500b-756">Registration</span></span>
- <span data-ttu-id="2500b-757">Identificazione</span><span class="sxs-lookup"><span data-stu-id="2500b-757">Identification</span></span> 
- <span data-ttu-id="2500b-758">ID</span><span class="sxs-lookup"><span data-stu-id="2500b-758">ID</span></span> 
- <span data-ttu-id="2500b-759">Identiteitskaart</span><span class="sxs-lookup"><span data-stu-id="2500b-759">Identiteitskaart</span></span>
- <span data-ttu-id="2500b-760">Registratie nummer</span><span class="sxs-lookup"><span data-stu-id="2500b-760">Registratie nummer</span></span> 
- <span data-ttu-id="2500b-761">Identificatie nummer</span><span class="sxs-lookup"><span data-stu-id="2500b-761">Identificatie nummer</span></span> 
- <span data-ttu-id="2500b-762">Identiteit</span><span class="sxs-lookup"><span data-stu-id="2500b-762">Identiteit</span></span>
- <span data-ttu-id="2500b-763">Registratie</span><span class="sxs-lookup"><span data-stu-id="2500b-763">Registratie</span></span>
- <span data-ttu-id="2500b-764">Identificatie</span><span class="sxs-lookup"><span data-stu-id="2500b-764">Identificatie</span></span> 
- <span data-ttu-id="2500b-765">Carte d’identité</span><span class="sxs-lookup"><span data-stu-id="2500b-765">Carte d’identité</span></span> 
- <span data-ttu-id="2500b-766">numéro d'immatriculation</span><span class="sxs-lookup"><span data-stu-id="2500b-766">numéro d'immatriculation</span></span>
- <span data-ttu-id="2500b-767">numéro d'identification</span><span class="sxs-lookup"><span data-stu-id="2500b-767">numéro d'identification</span></span>
- <span data-ttu-id="2500b-768">identité</span><span class="sxs-lookup"><span data-stu-id="2500b-768">identité</span></span> 
- <span data-ttu-id="2500b-769">iscrizione</span><span class="sxs-lookup"><span data-stu-id="2500b-769">inscription</span></span> 
- <span data-ttu-id="2500b-770">Identifikation</span><span class="sxs-lookup"><span data-stu-id="2500b-770">Identifikation</span></span>
- <span data-ttu-id="2500b-771">Identifizierung</span><span class="sxs-lookup"><span data-stu-id="2500b-771">Identifizierung</span></span>
- <span data-ttu-id="2500b-772">Identifikationsnummer</span><span class="sxs-lookup"><span data-stu-id="2500b-772">Identifikationsnummer</span></span>
- <span data-ttu-id="2500b-773">Personalausweis</span><span class="sxs-lookup"><span data-stu-id="2500b-773">Personalausweis</span></span>
- <span data-ttu-id="2500b-774">Registrierung</span><span class="sxs-lookup"><span data-stu-id="2500b-774">Registrierung</span></span>
- <span data-ttu-id="2500b-775">Registrationsnummer</span><span class="sxs-lookup"><span data-stu-id="2500b-775">Registrationsnummer</span></span>

   
## <a name="brazil-cpf-number"></a><span data-ttu-id="2500b-776">Numero CPF Brasile</span><span class="sxs-lookup"><span data-stu-id="2500b-776">Brazil CPF Number</span></span>

### <a name="format"></a><span data-ttu-id="2500b-777">Formato</span><span class="sxs-lookup"><span data-stu-id="2500b-777">Format</span></span>

<span data-ttu-id="2500b-778">11 cifre che includono una cifra di controllo e possono essere formattate o non formattate</span><span class="sxs-lookup"><span data-stu-id="2500b-778">11 digits that include a check digit and can be formatted or unformatted</span></span>

### <a name="pattern"></a><span data-ttu-id="2500b-779">Modello</span><span class="sxs-lookup"><span data-stu-id="2500b-779">Pattern</span></span>

<span data-ttu-id="2500b-780">Formattato</span><span class="sxs-lookup"><span data-stu-id="2500b-780">Formatted:</span></span>
- <span data-ttu-id="2500b-781">Tre cifre</span><span class="sxs-lookup"><span data-stu-id="2500b-781">Three digits</span></span> 
- <span data-ttu-id="2500b-782">Un punto </span><span class="sxs-lookup"><span data-stu-id="2500b-782">A period</span></span> 
- <span data-ttu-id="2500b-783">Tre cifre</span><span class="sxs-lookup"><span data-stu-id="2500b-783">Three digits</span></span> 
- <span data-ttu-id="2500b-784">Un punto </span><span class="sxs-lookup"><span data-stu-id="2500b-784">A period</span></span> 
- <span data-ttu-id="2500b-785">Tre cifre</span><span class="sxs-lookup"><span data-stu-id="2500b-785">Three digits</span></span> 
- <span data-ttu-id="2500b-786">Una lineetta</span><span class="sxs-lookup"><span data-stu-id="2500b-786">A hyphen</span></span> 
- <span data-ttu-id="2500b-787">Due cifre, ovvero le cifre di controllo</span><span class="sxs-lookup"><span data-stu-id="2500b-787">Two digits which are check digits</span></span>

<span data-ttu-id="2500b-788">Formattato</span><span class="sxs-lookup"><span data-stu-id="2500b-788">Unformatted:</span></span>
- <span data-ttu-id="2500b-789">11 cifre dove le ultime due sono cifre di controllo</span><span class="sxs-lookup"><span data-stu-id="2500b-789">11 digits where the last two digits are check digits</span></span>

### <a name="checksum"></a><span data-ttu-id="2500b-790">Checksum</span><span class="sxs-lookup"><span data-stu-id="2500b-790">Checksum</span></span>

<span data-ttu-id="2500b-791">Sì</span><span class="sxs-lookup"><span data-stu-id="2500b-791">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="2500b-792">Definizione</span><span class="sxs-lookup"><span data-stu-id="2500b-792">Definition</span></span>

<span data-ttu-id="2500b-793">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="2500b-793">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2500b-794">La funzione Func_brazil_cpf trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="2500b-794">The function Func_brazil_cpf finds content that matches the pattern.</span></span>
- <span data-ttu-id="2500b-795">Viene trovata una parola chiave da Keyword_brazil_cpf.</span><span class="sxs-lookup"><span data-stu-id="2500b-795">A keyword from Keyword_brazil_cpf is found.</span></span>
- <span data-ttu-id="2500b-796">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="2500b-796">The checksum passes.</span></span>

<span data-ttu-id="2500b-797">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="2500b-797">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2500b-798">La funzione Func_brazil_cpf trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="2500b-798">The function Func_brazil_cpf finds content that matches the pattern.</span></span>
- <span data-ttu-id="2500b-799">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="2500b-799">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="2500b-800">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="2500b-800">Keywords</span></span>

#### <a name="keywordbrazilcpf"></a><span data-ttu-id="2500b-801">Keyword_brazil_cpf</span><span class="sxs-lookup"><span data-stu-id="2500b-801">Keyword_brazil_cpf</span></span>

- <span data-ttu-id="2500b-802">CPF</span><span class="sxs-lookup"><span data-stu-id="2500b-802">CPF</span></span>
- <span data-ttu-id="2500b-803">Identificazione</span><span class="sxs-lookup"><span data-stu-id="2500b-803">Identification</span></span>
- <span data-ttu-id="2500b-804">Registrazione</span><span class="sxs-lookup"><span data-stu-id="2500b-804">Registration</span></span>
- <span data-ttu-id="2500b-805">Entrate</span><span class="sxs-lookup"><span data-stu-id="2500b-805">Revenue</span></span>
- <span data-ttu-id="2500b-806">Cadastro de Pessoas Físicas</span><span class="sxs-lookup"><span data-stu-id="2500b-806">Cadastro de Pessoas Físicas</span></span> 
- <span data-ttu-id="2500b-807">Imposto</span><span class="sxs-lookup"><span data-stu-id="2500b-807">Imposto</span></span> 
- <span data-ttu-id="2500b-808">Identificação</span><span class="sxs-lookup"><span data-stu-id="2500b-808">Identificação</span></span> 
- <span data-ttu-id="2500b-809">Inscrição</span><span class="sxs-lookup"><span data-stu-id="2500b-809">Inscrição</span></span> 
- <span data-ttu-id="2500b-810">Receita</span><span class="sxs-lookup"><span data-stu-id="2500b-810">Receita</span></span> 
   
## <a name="brazil-legal-entity-number-cnpj"></a><span data-ttu-id="2500b-811">Brasile - Codice fiscale persone giuridiche (CNPJ)</span><span class="sxs-lookup"><span data-stu-id="2500b-811">Brazil Legal Entity Number (CNPJ)</span></span>

### <a name="format"></a><span data-ttu-id="2500b-812">Formato</span><span class="sxs-lookup"><span data-stu-id="2500b-812">Format</span></span>

<span data-ttu-id="2500b-813">14 cifre che includono il numero di registrazione, il codice della filiale, le cifre di controllo e i delimitatori</span><span class="sxs-lookup"><span data-stu-id="2500b-813">14 digits that include a registration number, branch number, and check digits, plus delimiters</span></span>

### <a name="pattern"></a><span data-ttu-id="2500b-814">Modello</span><span class="sxs-lookup"><span data-stu-id="2500b-814">Pattern</span></span>
<span data-ttu-id="2500b-815">14 cifre più delimitatori:</span><span class="sxs-lookup"><span data-stu-id="2500b-815">14 digits, plus delimiters:</span></span>
- <span data-ttu-id="2500b-816">Due cifre</span><span class="sxs-lookup"><span data-stu-id="2500b-816">Two digits</span></span> 
- <span data-ttu-id="2500b-817">Un punto </span><span class="sxs-lookup"><span data-stu-id="2500b-817">A period</span></span> 
- <span data-ttu-id="2500b-818">Tre cifre</span><span class="sxs-lookup"><span data-stu-id="2500b-818">Three digits</span></span> 
- <span data-ttu-id="2500b-819">Un punto </span><span class="sxs-lookup"><span data-stu-id="2500b-819">A period</span></span> 
- <span data-ttu-id="2500b-820">Tre cifre (le prime otto sono il numero di registrazione) </span><span class="sxs-lookup"><span data-stu-id="2500b-820">Three digits (these first eight digits are the registration number)</span></span> 
- <span data-ttu-id="2500b-821">Una barra</span><span class="sxs-lookup"><span data-stu-id="2500b-821">A forward slash</span></span> 
- <span data-ttu-id="2500b-822">Numero del ramo a quattro cifre </span><span class="sxs-lookup"><span data-stu-id="2500b-822">Four-digit branch number</span></span> 
- <span data-ttu-id="2500b-823">Una lineetta</span><span class="sxs-lookup"><span data-stu-id="2500b-823">A hyphen</span></span> 
- <span data-ttu-id="2500b-824">Due cifre, ovvero le cifre di controllo</span><span class="sxs-lookup"><span data-stu-id="2500b-824">Two digits which are check digits</span></span>

### <a name="checksum"></a><span data-ttu-id="2500b-825">Checksum</span><span class="sxs-lookup"><span data-stu-id="2500b-825">Checksum</span></span>

<span data-ttu-id="2500b-826">Sì</span><span class="sxs-lookup"><span data-stu-id="2500b-826">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="2500b-827">Definizione</span><span class="sxs-lookup"><span data-stu-id="2500b-827">Definition</span></span>

<span data-ttu-id="2500b-828">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="2500b-828">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2500b-829">La funzione Func_brazil_cnpj trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="2500b-829">The function Func_brazil_cnpj finds content that matches the pattern.</span></span>
- <span data-ttu-id="2500b-830">Viene trovata una parola chiave da Keyword_brazil_cnpj.</span><span class="sxs-lookup"><span data-stu-id="2500b-830">A keyword from Keyword_brazil_cnpj is found.</span></span>
- <span data-ttu-id="2500b-831">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="2500b-831">The checksum passes.</span></span>

<span data-ttu-id="2500b-832">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="2500b-832">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2500b-833">La funzione Func_brazil_cnpj trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="2500b-833">The function Func_brazil_cnpj finds content that matches the pattern.</span></span>
- <span data-ttu-id="2500b-834">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="2500b-834">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="2500b-835">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="2500b-835">Keywords</span></span>

#### <a name="keywordbrazilcnpj"></a><span data-ttu-id="2500b-836">Keyword_brazil_cnpj</span><span class="sxs-lookup"><span data-stu-id="2500b-836">Keyword_brazil_cnpj</span></span>

- <span data-ttu-id="2500b-837">CNPJ</span><span class="sxs-lookup"><span data-stu-id="2500b-837">CNPJ</span></span> 
- <span data-ttu-id="2500b-838">CNPJ/MF</span><span class="sxs-lookup"><span data-stu-id="2500b-838">CNPJ/MF</span></span> 
- <span data-ttu-id="2500b-839">CNPJ-MF</span><span class="sxs-lookup"><span data-stu-id="2500b-839">CNPJ-MF</span></span> 
- <span data-ttu-id="2500b-840">Codice fiscale persone giuridiche</span><span class="sxs-lookup"><span data-stu-id="2500b-840">National Registry of Legal Entities</span></span> 
- <span data-ttu-id="2500b-841">Registro contribuenti</span><span class="sxs-lookup"><span data-stu-id="2500b-841">Taxpayers Registry</span></span> 
- <span data-ttu-id="2500b-842">Persona giuridica</span><span class="sxs-lookup"><span data-stu-id="2500b-842">Legal entity</span></span> 
- <span data-ttu-id="2500b-843">Persone giuridiche</span><span class="sxs-lookup"><span data-stu-id="2500b-843">Legal entities</span></span> 
- <span data-ttu-id="2500b-844">Stato della registrazione</span><span class="sxs-lookup"><span data-stu-id="2500b-844">Registration Status</span></span> 
- <span data-ttu-id="2500b-845">Business</span><span class="sxs-lookup"><span data-stu-id="2500b-845">Business</span></span> 
- <span data-ttu-id="2500b-846">Company</span><span class="sxs-lookup"><span data-stu-id="2500b-846">Company</span></span>
- <span data-ttu-id="2500b-847">CNPJ</span><span class="sxs-lookup"><span data-stu-id="2500b-847">CNPJ</span></span> 
- <span data-ttu-id="2500b-848">Cadastro Nacional da Pessoa Jurídica</span><span class="sxs-lookup"><span data-stu-id="2500b-848">Cadastro Nacional da Pessoa Jurídica</span></span> 
- <span data-ttu-id="2500b-849">Cadastro Geral de Contribuintes</span><span class="sxs-lookup"><span data-stu-id="2500b-849">Cadastro Geral de Contribuintes</span></span> 
- <span data-ttu-id="2500b-850">CGC</span><span class="sxs-lookup"><span data-stu-id="2500b-850">CGC</span></span> 
- <span data-ttu-id="2500b-851">Pessoa jurídica</span><span class="sxs-lookup"><span data-stu-id="2500b-851">Pessoa jurídica</span></span> 
- <span data-ttu-id="2500b-852">Pessoas jurídicas</span><span class="sxs-lookup"><span data-stu-id="2500b-852">Pessoas jurídicas</span></span> 
- <span data-ttu-id="2500b-853">Situação cadastral</span><span class="sxs-lookup"><span data-stu-id="2500b-853">Situação cadastral</span></span> 
- <span data-ttu-id="2500b-854">Inscrição</span><span class="sxs-lookup"><span data-stu-id="2500b-854">Inscrição</span></span> 
- <span data-ttu-id="2500b-855">Empresa</span><span class="sxs-lookup"><span data-stu-id="2500b-855">Empresa</span></span> 
   
## <a name="brazil-national-id-card-rg"></a><span data-ttu-id="2500b-856">	Carta d'identità (Brasile) (RG)</span><span class="sxs-lookup"><span data-stu-id="2500b-856">Brazil National ID Card (RG)</span></span>

### <a name="format"></a><span data-ttu-id="2500b-857">Formato</span><span class="sxs-lookup"><span data-stu-id="2500b-857">Format</span></span>

<span data-ttu-id="2500b-858">Registro Geral (formato precedente): nove cifre</span><span class="sxs-lookup"><span data-stu-id="2500b-858">Registro Geral (old format): Nine digits</span></span>

<span data-ttu-id="2500b-859">Registro de Identidade (RIC) (nuovo formato): 11 cifre</span><span class="sxs-lookup"><span data-stu-id="2500b-859">Registro de Identidade (RIC) (new format): 11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="2500b-860">Modello</span><span class="sxs-lookup"><span data-stu-id="2500b-860">Pattern</span></span>

<span data-ttu-id="2500b-861">Registro Geral (formato precedente):</span><span class="sxs-lookup"><span data-stu-id="2500b-861">Registro Geral (old format):</span></span>
- <span data-ttu-id="2500b-862">Due cifre</span><span class="sxs-lookup"><span data-stu-id="2500b-862">Two digits</span></span> 
- <span data-ttu-id="2500b-863">Un punto </span><span class="sxs-lookup"><span data-stu-id="2500b-863">A period</span></span> 
- <span data-ttu-id="2500b-864">Tre cifre</span><span class="sxs-lookup"><span data-stu-id="2500b-864">Three digits</span></span> 
- <span data-ttu-id="2500b-865">Un punto </span><span class="sxs-lookup"><span data-stu-id="2500b-865">A period</span></span> 
- <span data-ttu-id="2500b-866">Tre cifre</span><span class="sxs-lookup"><span data-stu-id="2500b-866">Three digits</span></span> 
- <span data-ttu-id="2500b-867">Una lineetta</span><span class="sxs-lookup"><span data-stu-id="2500b-867">A hyphen</span></span> 
- <span data-ttu-id="2500b-868">Una cifra, ovvero una cifra di controllo</span><span class="sxs-lookup"><span data-stu-id="2500b-868">One digit which is a check digit</span></span>

<span data-ttu-id="2500b-869">Registro de Identidade (RIC) (nuovo formato):</span><span class="sxs-lookup"><span data-stu-id="2500b-869">Registro de Identidade (RIC) (new format):</span></span>
- <span data-ttu-id="2500b-870">10 cifre</span><span class="sxs-lookup"><span data-stu-id="2500b-870">10 digits</span></span> 
- <span data-ttu-id="2500b-871">Una lineetta</span><span class="sxs-lookup"><span data-stu-id="2500b-871">A hyphen</span></span> 
- <span data-ttu-id="2500b-872">Una cifra, ovvero una cifra di controllo</span><span class="sxs-lookup"><span data-stu-id="2500b-872">One digit which is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="2500b-873">Checksum</span><span class="sxs-lookup"><span data-stu-id="2500b-873">Checksum</span></span>

<span data-ttu-id="2500b-874">Sì</span><span class="sxs-lookup"><span data-stu-id="2500b-874">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="2500b-875">Definizione</span><span class="sxs-lookup"><span data-stu-id="2500b-875">Definition</span></span>

<span data-ttu-id="2500b-876">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="2500b-876">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2500b-877">La funzione Func_brazil_rg trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="2500b-877">The function Func_brazil_rg finds content that matches the pattern.</span></span>
- <span data-ttu-id="2500b-878">Viene trovata una parola chiave da Keyword_brazil_rg.</span><span class="sxs-lookup"><span data-stu-id="2500b-878">A keyword from Keyword_brazil_rg is found.</span></span>
- <span data-ttu-id="2500b-879">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="2500b-879">The checksum passes.</span></span>

<span data-ttu-id="2500b-880">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="2500b-880">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2500b-881">La funzione Func_brazil_rg trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="2500b-881">The function Func_brazil_rg finds content that matches the pattern.</span></span>
- <span data-ttu-id="2500b-882">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="2500b-882">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="2500b-883">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="2500b-883">Keywords</span></span>

#### <a name="keywordbrazilrg"></a><span data-ttu-id="2500b-884">Keyword_brazil_rg</span><span class="sxs-lookup"><span data-stu-id="2500b-884">Keyword_brazil_rg</span></span>

<span data-ttu-id="2500b-885">Cédula de Identidade identità Card National ID número de rregistro Registro de Iidentidade registro Geral RG (questa parola chiave è distinzione tra maiuscole e minuscole) RIC (questa parola chiave è distinzione tra maiuscole e minuscole)</span><span class="sxs-lookup"><span data-stu-id="2500b-885">Cédula de identidade identity card national id número de rregistro registro de Iidentidade registro geral RG (this keyword is case sensitive) RIC (this keyword is case sensitive)</span></span> 
   
## <a name="canada-bank-account-number"></a><span data-ttu-id="2500b-886">Canada - Numero di conto bancario</span><span class="sxs-lookup"><span data-stu-id="2500b-886">Canada Bank Account Number</span></span>

### <a name="format"></a><span data-ttu-id="2500b-887">Formato</span><span class="sxs-lookup"><span data-stu-id="2500b-887">Format</span></span>

<span data-ttu-id="2500b-888">7 o 12 cifre</span><span class="sxs-lookup"><span data-stu-id="2500b-888">Seven or twelve digits</span></span>

### <a name="pattern"></a><span data-ttu-id="2500b-889">Modello</span><span class="sxs-lookup"><span data-stu-id="2500b-889">Pattern</span></span>

<span data-ttu-id="2500b-890">Un numero di conto corrente canadese comprende 7 o 12 cifre.</span><span class="sxs-lookup"><span data-stu-id="2500b-890">A Canada Bank Account Number is seven or twelve digits.</span></span>

<span data-ttu-id="2500b-891">Un numero di transito bancario canadese comprende:</span><span class="sxs-lookup"><span data-stu-id="2500b-891">A Canada bank account transit number is:</span></span>
- <span data-ttu-id="2500b-892">Cinque cifre</span><span class="sxs-lookup"><span data-stu-id="2500b-892">Five digits</span></span> 
- <span data-ttu-id="2500b-893">Una lineetta</span><span class="sxs-lookup"><span data-stu-id="2500b-893">A hyphen</span></span> 
- <span data-ttu-id="2500b-894">Tre cifre o</span><span class="sxs-lookup"><span data-stu-id="2500b-894">Three digits OR</span></span>
- <span data-ttu-id="2500b-895">Uno zero "0"</span><span class="sxs-lookup"><span data-stu-id="2500b-895">A zero "0"</span></span> 
- <span data-ttu-id="2500b-896">Otto cifre</span><span class="sxs-lookup"><span data-stu-id="2500b-896">Eight digits</span></span>

### <a name="checksum"></a><span data-ttu-id="2500b-897">Checksum</span><span class="sxs-lookup"><span data-stu-id="2500b-897">Checksum</span></span>

<span data-ttu-id="2500b-898">No</span><span class="sxs-lookup"><span data-stu-id="2500b-898">No</span></span>

### <a name="definition"></a><span data-ttu-id="2500b-899">Definizione</span><span class="sxs-lookup"><span data-stu-id="2500b-899">Definition</span></span>

<span data-ttu-id="2500b-900">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="2500b-900">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2500b-901">L'espressione regolare Regex_canada_bank_account_number restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="2500b-901">The regular expression Regex_canada_bank_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="2500b-902">Viene trovata una parola chiave da Keyword_canada_bank_account_number.</span><span class="sxs-lookup"><span data-stu-id="2500b-902">A keyword from Keyword_canada_bank_account_number is found.</span></span>
- <span data-ttu-id="2500b-903">L'espressione regolare Regex_canada_bank_account_transit_number restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="2500b-903">The regular expression Regex_canada_bank_account_transit_number finds content that matches the pattern.</span></span>

<span data-ttu-id="2500b-904">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="2500b-904">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2500b-905">L'espressione regolare Regex_canada_bank_account_number restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="2500b-905">The regular expression Regex_canada_bank_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="2500b-906">Viene trovata una parola chiave da Keyword_canada_bank_account_number.</span><span class="sxs-lookup"><span data-stu-id="2500b-906">A keyword from Keyword_canada_bank_account_number is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="2500b-907">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="2500b-907">Keywords</span></span>

#### <a name="keywordcanadabankaccountnumber"></a><span data-ttu-id="2500b-908">Keyword_canada_bank_account_number</span><span class="sxs-lookup"><span data-stu-id="2500b-908">Keyword_canada_bank_account_number</span></span>

- <span data-ttu-id="2500b-909">canada savings bonds</span><span class="sxs-lookup"><span data-stu-id="2500b-909">canada savings bonds</span></span>
- <span data-ttu-id="2500b-910">canada revenue agency</span><span class="sxs-lookup"><span data-stu-id="2500b-910">canada revenue agency</span></span>
- <span data-ttu-id="2500b-911">canadian financial institution</span><span class="sxs-lookup"><span data-stu-id="2500b-911">canadian financial institution</span></span>
- <span data-ttu-id="2500b-912">direct deposit form</span><span class="sxs-lookup"><span data-stu-id="2500b-912">direct deposit form</span></span>
- <span data-ttu-id="2500b-913">canadian citizen</span><span class="sxs-lookup"><span data-stu-id="2500b-913">canadian citizen</span></span>
- <span data-ttu-id="2500b-914">legal representative</span><span class="sxs-lookup"><span data-stu-id="2500b-914">legal representative</span></span>
- <span data-ttu-id="2500b-915">notary public</span><span class="sxs-lookup"><span data-stu-id="2500b-915">notary public</span></span>
- <span data-ttu-id="2500b-916">commissioner for oaths</span><span class="sxs-lookup"><span data-stu-id="2500b-916">commissioner for oaths</span></span>
- <span data-ttu-id="2500b-917">child care benefit</span><span class="sxs-lookup"><span data-stu-id="2500b-917">child care benefit</span></span>
- <span data-ttu-id="2500b-918">universal child care</span><span class="sxs-lookup"><span data-stu-id="2500b-918">universal child care</span></span>
- <span data-ttu-id="2500b-919">canada child tax benefit</span><span class="sxs-lookup"><span data-stu-id="2500b-919">canada child tax benefit</span></span>
- <span data-ttu-id="2500b-920">income tax benefit</span><span class="sxs-lookup"><span data-stu-id="2500b-920">income tax benefit</span></span>
- <span data-ttu-id="2500b-921">harmonized sales tax</span><span class="sxs-lookup"><span data-stu-id="2500b-921">harmonized sales tax</span></span>
- <span data-ttu-id="2500b-922">social insurance number</span><span class="sxs-lookup"><span data-stu-id="2500b-922">social insurance number</span></span>
- <span data-ttu-id="2500b-923">income tax refund</span><span class="sxs-lookup"><span data-stu-id="2500b-923">income tax refund</span></span>
- <span data-ttu-id="2500b-924">child tax benefit</span><span class="sxs-lookup"><span data-stu-id="2500b-924">child tax benefit</span></span>
- <span data-ttu-id="2500b-925">territorial payments</span><span class="sxs-lookup"><span data-stu-id="2500b-925">territorial payments</span></span>
- <span data-ttu-id="2500b-926">institution number</span><span class="sxs-lookup"><span data-stu-id="2500b-926">institution number</span></span>
- <span data-ttu-id="2500b-927">deposit request</span><span class="sxs-lookup"><span data-stu-id="2500b-927">deposit request</span></span>
- <span data-ttu-id="2500b-928">banking information</span><span class="sxs-lookup"><span data-stu-id="2500b-928">banking information</span></span>
- <span data-ttu-id="2500b-929">direct deposit</span><span class="sxs-lookup"><span data-stu-id="2500b-929">direct deposit</span></span>
   
## <a name="canada-drivers-license-number"></a><span data-ttu-id="2500b-930">Canada - Numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="2500b-930">Canada Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="2500b-931">Formato</span><span class="sxs-lookup"><span data-stu-id="2500b-931">Format</span></span>

<span data-ttu-id="2500b-932">Varia in base alla provincia</span><span class="sxs-lookup"><span data-stu-id="2500b-932">Varies by province</span></span>

### <a name="pattern"></a><span data-ttu-id="2500b-933">Modello</span><span class="sxs-lookup"><span data-stu-id="2500b-933">Pattern</span></span>

<span data-ttu-id="2500b-934">Vari modelli per Alberta, Columbia Britannica, Manitoba, Nuovo Brunswick, Terranova e Labrador, Nuova Scozia, Ontario, Isola del Principe Edoardo, Quebec e Saskatchewan</span><span class="sxs-lookup"><span data-stu-id="2500b-934">Various patterns covering Alberta, British Columbia, Manitoba, New Brunswick, Newfoundland/Labrador, Nova Scotia, Ontario, Prince Edward Island, Quebec, and Saskatchewan</span></span>

### <a name="checksum"></a><span data-ttu-id="2500b-935">Checksum</span><span class="sxs-lookup"><span data-stu-id="2500b-935">Checksum</span></span>

<span data-ttu-id="2500b-936">No</span><span class="sxs-lookup"><span data-stu-id="2500b-936">No</span></span>

### <a name="definition"></a><span data-ttu-id="2500b-937">Definizione</span><span class="sxs-lookup"><span data-stu-id="2500b-937">Definition</span></span>

<span data-ttu-id="2500b-938">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="2500b-938">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2500b-939">La funzione Func_[province_name]_drivers_license_number restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="2500b-939">The function Func_[province_name]_drivers_license_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="2500b-940">Viene trovata una parola chiave da Keyword_[province_name]_drivers_license_name.</span><span class="sxs-lookup"><span data-stu-id="2500b-940">A keyword from Keyword_[province_name]_drivers_license_name is found.</span></span>
- <span data-ttu-id="2500b-941">Viene trovata una parola chiave da Keyword_canada_drivers_license.</span><span class="sxs-lookup"><span data-stu-id="2500b-941">A keyword from Keyword_canada_drivers_license is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="2500b-942">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="2500b-942">Keywords</span></span>

#### <a name="keywordprovincenamedriverslicensename"></a><span data-ttu-id="2500b-943">Keyword_[province_name]_drivers_license_name</span><span class="sxs-lookup"><span data-stu-id="2500b-943">Keyword_[province_name]_drivers_license_name</span></span>

- <span data-ttu-id="2500b-944">L'abbreviazione della provincia, ad esempio, AB</span><span class="sxs-lookup"><span data-stu-id="2500b-944">The province abbreviation, for example AB</span></span>
- <span data-ttu-id="2500b-945">Il nome della provincia, ad esempio, Alberta</span><span class="sxs-lookup"><span data-stu-id="2500b-945">The province name, for example Alberta</span></span>

#### <a name="keywordcanadadriverslicense"></a><span data-ttu-id="2500b-946">Keyword_canada_drivers_license</span><span class="sxs-lookup"><span data-stu-id="2500b-946">Keyword_canada_drivers_license</span></span>

- <span data-ttu-id="2500b-947">DL</span><span class="sxs-lookup"><span data-stu-id="2500b-947">DL</span></span>
- <span data-ttu-id="2500b-948">DLS</span><span class="sxs-lookup"><span data-stu-id="2500b-948">DLS</span></span>
- <span data-ttu-id="2500b-949">CDL</span><span class="sxs-lookup"><span data-stu-id="2500b-949">CDL</span></span>
- <span data-ttu-id="2500b-950">CDLS</span><span class="sxs-lookup"><span data-stu-id="2500b-950">CDLS</span></span>
- <span data-ttu-id="2500b-951">DriverLic</span><span class="sxs-lookup"><span data-stu-id="2500b-951">DriverLic</span></span>
- <span data-ttu-id="2500b-952">DriverLics</span><span class="sxs-lookup"><span data-stu-id="2500b-952">DriverLics</span></span>
- <span data-ttu-id="2500b-953">DriverLicense</span><span class="sxs-lookup"><span data-stu-id="2500b-953">DriverLicense</span></span>
- <span data-ttu-id="2500b-954">DriverLicenses</span><span class="sxs-lookup"><span data-stu-id="2500b-954">DriverLicenses</span></span>
- <span data-ttu-id="2500b-955">DriverLicence</span><span class="sxs-lookup"><span data-stu-id="2500b-955">DriverLicence</span></span>
- <span data-ttu-id="2500b-956">DriverLicences</span><span class="sxs-lookup"><span data-stu-id="2500b-956">DriverLicences</span></span>
- <span data-ttu-id="2500b-957">Driver Lic</span><span class="sxs-lookup"><span data-stu-id="2500b-957">Driver Lic</span></span>
- <span data-ttu-id="2500b-958">Driver Lics</span><span class="sxs-lookup"><span data-stu-id="2500b-958">Driver Lics</span></span>
- <span data-ttu-id="2500b-959">Driver License</span><span class="sxs-lookup"><span data-stu-id="2500b-959">Driver License</span></span>
- <span data-ttu-id="2500b-960">Driver Licenses</span><span class="sxs-lookup"><span data-stu-id="2500b-960">Driver Licenses</span></span>
- <span data-ttu-id="2500b-961">Driver Licence</span><span class="sxs-lookup"><span data-stu-id="2500b-961">Driver Licence</span></span>
- <span data-ttu-id="2500b-962">Driver Licences</span><span class="sxs-lookup"><span data-stu-id="2500b-962">Driver Licences</span></span>
- <span data-ttu-id="2500b-963">DriversLic</span><span class="sxs-lookup"><span data-stu-id="2500b-963">DriversLic</span></span>
- <span data-ttu-id="2500b-964">DriversLics</span><span class="sxs-lookup"><span data-stu-id="2500b-964">DriversLics</span></span>
- <span data-ttu-id="2500b-965">DriversLicence</span><span class="sxs-lookup"><span data-stu-id="2500b-965">DriversLicence</span></span>
- <span data-ttu-id="2500b-966">DriversLicences</span><span class="sxs-lookup"><span data-stu-id="2500b-966">DriversLicences</span></span>
- <span data-ttu-id="2500b-967">DriversLicense</span><span class="sxs-lookup"><span data-stu-id="2500b-967">DriversLicense</span></span>
- <span data-ttu-id="2500b-968">DriversLicenses</span><span class="sxs-lookup"><span data-stu-id="2500b-968">DriversLicenses</span></span>
- <span data-ttu-id="2500b-969">Drivers Lic</span><span class="sxs-lookup"><span data-stu-id="2500b-969">Drivers Lic</span></span>
- <span data-ttu-id="2500b-970">Drivers Lics</span><span class="sxs-lookup"><span data-stu-id="2500b-970">Drivers Lics</span></span>
- <span data-ttu-id="2500b-971">Drivers License</span><span class="sxs-lookup"><span data-stu-id="2500b-971">Drivers License</span></span>
- <span data-ttu-id="2500b-972">Drivers Licenses</span><span class="sxs-lookup"><span data-stu-id="2500b-972">Drivers Licenses</span></span>
- <span data-ttu-id="2500b-973">Drivers Licence</span><span class="sxs-lookup"><span data-stu-id="2500b-973">Drivers Licence</span></span>
- <span data-ttu-id="2500b-974">Drivers Licences</span><span class="sxs-lookup"><span data-stu-id="2500b-974">Drivers Licences</span></span>
- <span data-ttu-id="2500b-975">Driver'Lic</span><span class="sxs-lookup"><span data-stu-id="2500b-975">Driver'Lic</span></span>
- <span data-ttu-id="2500b-976">Driver ' LiCS</span><span class="sxs-lookup"><span data-stu-id="2500b-976">Driver'Lics</span></span>
- <span data-ttu-id="2500b-977">Driver ' License</span><span class="sxs-lookup"><span data-stu-id="2500b-977">Driver'License</span></span>
- <span data-ttu-id="2500b-978">Driver ' licenses</span><span class="sxs-lookup"><span data-stu-id="2500b-978">Driver'Licenses</span></span>
- <span data-ttu-id="2500b-979">Driver'Licence</span><span class="sxs-lookup"><span data-stu-id="2500b-979">Driver'Licence</span></span>
- <span data-ttu-id="2500b-980">Driver'Licences</span><span class="sxs-lookup"><span data-stu-id="2500b-980">Driver'Licences</span></span>
- <span data-ttu-id="2500b-981">Driver'Lic</span><span class="sxs-lookup"><span data-stu-id="2500b-981">Driver' Lic</span></span>
- <span data-ttu-id="2500b-982">Driver' Lics</span><span class="sxs-lookup"><span data-stu-id="2500b-982">Driver' Lics</span></span>
- <span data-ttu-id="2500b-983">Driver' License</span><span class="sxs-lookup"><span data-stu-id="2500b-983">Driver' License</span></span>
- <span data-ttu-id="2500b-984">Driver' Licenses</span><span class="sxs-lookup"><span data-stu-id="2500b-984">Driver' Licenses</span></span>
- <span data-ttu-id="2500b-985">Driver' Licence</span><span class="sxs-lookup"><span data-stu-id="2500b-985">Driver' Licence</span></span>
- <span data-ttu-id="2500b-986">Driver' Licences</span><span class="sxs-lookup"><span data-stu-id="2500b-986">Driver' Licences</span></span>
- <span data-ttu-id="2500b-987">Driver'sLic</span><span class="sxs-lookup"><span data-stu-id="2500b-987">Driver'sLic</span></span>
- <span data-ttu-id="2500b-988">Driver'sLics</span><span class="sxs-lookup"><span data-stu-id="2500b-988">Driver'sLics</span></span>
- <span data-ttu-id="2500b-989">Secondola</span><span class="sxs-lookup"><span data-stu-id="2500b-989">Driver'sLicense</span></span>
- <span data-ttu-id="2500b-990">Driver'sLicenses</span><span class="sxs-lookup"><span data-stu-id="2500b-990">Driver'sLicenses</span></span>
- <span data-ttu-id="2500b-991">Driver'sLicence</span><span class="sxs-lookup"><span data-stu-id="2500b-991">Driver'sLicence</span></span>
- <span data-ttu-id="2500b-992">Driver'sLicences</span><span class="sxs-lookup"><span data-stu-id="2500b-992">Driver'sLicences</span></span>
- <span data-ttu-id="2500b-993">Driver's Lic</span><span class="sxs-lookup"><span data-stu-id="2500b-993">Driver's Lic</span></span>
- <span data-ttu-id="2500b-994">Driver's Lics</span><span class="sxs-lookup"><span data-stu-id="2500b-994">Driver's Lics</span></span>
- <span data-ttu-id="2500b-995">Driver's License</span><span class="sxs-lookup"><span data-stu-id="2500b-995">Driver's License</span></span>
- <span data-ttu-id="2500b-996">Driver's Licenses</span><span class="sxs-lookup"><span data-stu-id="2500b-996">Driver's Licenses</span></span>
- <span data-ttu-id="2500b-997">Driver's Licence</span><span class="sxs-lookup"><span data-stu-id="2500b-997">Driver's Licence</span></span>
- <span data-ttu-id="2500b-998">Driver's Licences</span><span class="sxs-lookup"><span data-stu-id="2500b-998">Driver's Licences</span></span>
- <span data-ttu-id="2500b-999">Permis de Conduire</span><span class="sxs-lookup"><span data-stu-id="2500b-999">Permis de Conduire</span></span>
- <span data-ttu-id="2500b-1000">id</span><span class="sxs-lookup"><span data-stu-id="2500b-1000">id</span></span>
- <span data-ttu-id="2500b-1001">ID</span><span class="sxs-lookup"><span data-stu-id="2500b-1001">ids</span></span>
- <span data-ttu-id="2500b-1002">idcard number</span><span class="sxs-lookup"><span data-stu-id="2500b-1002">idcard number</span></span>
- <span data-ttu-id="2500b-1003">idcard numbers</span><span class="sxs-lookup"><span data-stu-id="2500b-1003">idcard numbers</span></span>
- <span data-ttu-id="2500b-1004">idcard #</span><span class="sxs-lookup"><span data-stu-id="2500b-1004">idcard #</span></span>
- <span data-ttu-id="2500b-1005">idcard #s</span><span class="sxs-lookup"><span data-stu-id="2500b-1005">idcard #s</span></span>
- <span data-ttu-id="2500b-1006">idcard card</span><span class="sxs-lookup"><span data-stu-id="2500b-1006">idcard card</span></span>
- <span data-ttu-id="2500b-1007">idcard cards</span><span class="sxs-lookup"><span data-stu-id="2500b-1007">idcard cards</span></span>
- <span data-ttu-id="2500b-1008">idcard</span><span class="sxs-lookup"><span data-stu-id="2500b-1008">idcard</span></span>
- <span data-ttu-id="2500b-1009">identification number</span><span class="sxs-lookup"><span data-stu-id="2500b-1009">identification number</span></span>
- <span data-ttu-id="2500b-1010">identification numbers</span><span class="sxs-lookup"><span data-stu-id="2500b-1010">identification numbers</span></span>
- <span data-ttu-id="2500b-1011">identification #</span><span class="sxs-lookup"><span data-stu-id="2500b-1011">identification #</span></span>
- <span data-ttu-id="2500b-1012">identification #s</span><span class="sxs-lookup"><span data-stu-id="2500b-1012">identification #s</span></span>
- <span data-ttu-id="2500b-1013">identification card</span><span class="sxs-lookup"><span data-stu-id="2500b-1013">identification card</span></span>
- <span data-ttu-id="2500b-1014">identification cards</span><span class="sxs-lookup"><span data-stu-id="2500b-1014">identification cards</span></span>
- <span data-ttu-id="2500b-1015">identificazione</span><span class="sxs-lookup"><span data-stu-id="2500b-1015">identification</span></span> 
- <span data-ttu-id="2500b-1016">DL</span><span class="sxs-lookup"><span data-stu-id="2500b-1016">DL#</span></span>
- <span data-ttu-id="2500b-1017">DLS</span><span class="sxs-lookup"><span data-stu-id="2500b-1017">DLS#</span></span> 
- <span data-ttu-id="2500b-1018">CDL</span><span class="sxs-lookup"><span data-stu-id="2500b-1018">CDL#</span></span> 
- <span data-ttu-id="2500b-1019">CDLS</span><span class="sxs-lookup"><span data-stu-id="2500b-1019">CDLS#</span></span> 
- <span data-ttu-id="2500b-1020">DriverLic#</span><span class="sxs-lookup"><span data-stu-id="2500b-1020">DriverLic#</span></span> 
- <span data-ttu-id="2500b-1021">DriverLics#</span><span class="sxs-lookup"><span data-stu-id="2500b-1021">DriverLics#</span></span> 
- <span data-ttu-id="2500b-1022">DriverLicense#</span><span class="sxs-lookup"><span data-stu-id="2500b-1022">DriverLicense#</span></span> 
- <span data-ttu-id="2500b-1023">DriverLicenses#</span><span class="sxs-lookup"><span data-stu-id="2500b-1023">DriverLicenses#</span></span> 
- <span data-ttu-id="2500b-1024">DriverLicence#</span><span class="sxs-lookup"><span data-stu-id="2500b-1024">DriverLicence#</span></span> 
- <span data-ttu-id="2500b-1025">DriverLicences#</span><span class="sxs-lookup"><span data-stu-id="2500b-1025">DriverLicences#</span></span> 
- <span data-ttu-id="2500b-1026">Driver Lic#</span><span class="sxs-lookup"><span data-stu-id="2500b-1026">Driver Lic#</span></span>
- <span data-ttu-id="2500b-1027">Driver Lics#</span><span class="sxs-lookup"><span data-stu-id="2500b-1027">Driver Lics#</span></span> 
- <span data-ttu-id="2500b-1028">Driver License#</span><span class="sxs-lookup"><span data-stu-id="2500b-1028">Driver License#</span></span> 
- <span data-ttu-id="2500b-1029">Driver Licenses#</span><span class="sxs-lookup"><span data-stu-id="2500b-1029">Driver Licenses#</span></span> 
- <span data-ttu-id="2500b-1030">Driver License#</span><span class="sxs-lookup"><span data-stu-id="2500b-1030">Driver License#</span></span> 
- <span data-ttu-id="2500b-1031">Driver Licences#</span><span class="sxs-lookup"><span data-stu-id="2500b-1031">Driver Licences#</span></span> 
- <span data-ttu-id="2500b-1032">DriversLic#</span><span class="sxs-lookup"><span data-stu-id="2500b-1032">DriversLic#</span></span> 
- <span data-ttu-id="2500b-1033">DriversLics#</span><span class="sxs-lookup"><span data-stu-id="2500b-1033">DriversLics#</span></span> 
- <span data-ttu-id="2500b-1034">DriversLicense#</span><span class="sxs-lookup"><span data-stu-id="2500b-1034">DriversLicense#</span></span> 
- <span data-ttu-id="2500b-1035">DriversLicenses#</span><span class="sxs-lookup"><span data-stu-id="2500b-1035">DriversLicenses#</span></span> 
- <span data-ttu-id="2500b-1036">DriversLicence#</span><span class="sxs-lookup"><span data-stu-id="2500b-1036">DriversLicence#</span></span> 
- <span data-ttu-id="2500b-1037">DriversLicences#</span><span class="sxs-lookup"><span data-stu-id="2500b-1037">DriversLicences#</span></span> 
- <span data-ttu-id="2500b-1038">Drivers Lic#</span><span class="sxs-lookup"><span data-stu-id="2500b-1038">Drivers Lic#</span></span> 
- <span data-ttu-id="2500b-1039">Drivers Lics#</span><span class="sxs-lookup"><span data-stu-id="2500b-1039">Drivers Lics#</span></span> 
- <span data-ttu-id="2500b-1040">Drivers License#</span><span class="sxs-lookup"><span data-stu-id="2500b-1040">Drivers License#</span></span> 
- <span data-ttu-id="2500b-1041">Drivers Licenses#</span><span class="sxs-lookup"><span data-stu-id="2500b-1041">Drivers Licenses#</span></span> 
- <span data-ttu-id="2500b-1042">Drivers Licence#</span><span class="sxs-lookup"><span data-stu-id="2500b-1042">Drivers Licence#</span></span> 
- <span data-ttu-id="2500b-1043">Drivers Licences#</span><span class="sxs-lookup"><span data-stu-id="2500b-1043">Drivers Licences#</span></span> 
- <span data-ttu-id="2500b-1044">Driver'Lic#</span><span class="sxs-lookup"><span data-stu-id="2500b-1044">Driver'Lic#</span></span> 
- <span data-ttu-id="2500b-1045">Driver ' LiCS</span><span class="sxs-lookup"><span data-stu-id="2500b-1045">Driver'Lics#</span></span> 
- <span data-ttu-id="2500b-1046">Driver ' License</span><span class="sxs-lookup"><span data-stu-id="2500b-1046">Driver'License#</span></span> 
- <span data-ttu-id="2500b-1047">Driver ' licenses</span><span class="sxs-lookup"><span data-stu-id="2500b-1047">Driver'Licenses#</span></span> 
- <span data-ttu-id="2500b-1048">Driver'Licence#</span><span class="sxs-lookup"><span data-stu-id="2500b-1048">Driver'Licence#</span></span> 
- <span data-ttu-id="2500b-1049">Driver'Licences#</span><span class="sxs-lookup"><span data-stu-id="2500b-1049">Driver'Licences#</span></span> 
- <span data-ttu-id="2500b-1050">Driver' Lic#</span><span class="sxs-lookup"><span data-stu-id="2500b-1050">Driver' Lic#</span></span> 
- <span data-ttu-id="2500b-1051">Driver' Lics#</span><span class="sxs-lookup"><span data-stu-id="2500b-1051">Driver' Lics#</span></span> 
- <span data-ttu-id="2500b-1052">Driver' License#</span><span class="sxs-lookup"><span data-stu-id="2500b-1052">Driver' License#</span></span> 
- <span data-ttu-id="2500b-1053">Driver' Licenses#</span><span class="sxs-lookup"><span data-stu-id="2500b-1053">Driver' Licenses#</span></span> 
- <span data-ttu-id="2500b-1054">Driver' Licence#</span><span class="sxs-lookup"><span data-stu-id="2500b-1054">Driver' Licence#</span></span> 
- <span data-ttu-id="2500b-1055">Driver' Licences#</span><span class="sxs-lookup"><span data-stu-id="2500b-1055">Driver' Licences#</span></span> 
- <span data-ttu-id="2500b-1056">Driver'sLic#</span><span class="sxs-lookup"><span data-stu-id="2500b-1056">Driver'sLic#</span></span> 
- <span data-ttu-id="2500b-1057">Driver'sLics#</span><span class="sxs-lookup"><span data-stu-id="2500b-1057">Driver'sLics#</span></span> 
- <span data-ttu-id="2500b-1058">Secondola</span><span class="sxs-lookup"><span data-stu-id="2500b-1058">Driver'sLicense#</span></span> 
- <span data-ttu-id="2500b-1059">Driver'sLicenses#</span><span class="sxs-lookup"><span data-stu-id="2500b-1059">Driver'sLicenses#</span></span> 
- <span data-ttu-id="2500b-1060">Driver'sLicence#</span><span class="sxs-lookup"><span data-stu-id="2500b-1060">Driver'sLicence#</span></span> 
- <span data-ttu-id="2500b-1061">Driver'sLicences#</span><span class="sxs-lookup"><span data-stu-id="2500b-1061">Driver'sLicences#</span></span> 
- <span data-ttu-id="2500b-1062">Driver's Lic#</span><span class="sxs-lookup"><span data-stu-id="2500b-1062">Driver's Lic#</span></span> 
- <span data-ttu-id="2500b-1063">Driver's Lics#</span><span class="sxs-lookup"><span data-stu-id="2500b-1063">Driver's Lics#</span></span> 
- <span data-ttu-id="2500b-1064">Driver's License#</span><span class="sxs-lookup"><span data-stu-id="2500b-1064">Driver's License#</span></span> 
- <span data-ttu-id="2500b-1065">Driver's Licenses#</span><span class="sxs-lookup"><span data-stu-id="2500b-1065">Driver's Licenses#</span></span> 
- <span data-ttu-id="2500b-1066">Driver's Licence#</span><span class="sxs-lookup"><span data-stu-id="2500b-1066">Driver's Licence#</span></span> 
- <span data-ttu-id="2500b-1067">Driver's Licences#</span><span class="sxs-lookup"><span data-stu-id="2500b-1067">Driver's Licences#</span></span> 
- <span data-ttu-id="2500b-1068">Permis de Conduire#</span><span class="sxs-lookup"><span data-stu-id="2500b-1068">Permis de Conduire#</span></span> 
- <span data-ttu-id="2500b-1069">ID</span><span class="sxs-lookup"><span data-stu-id="2500b-1069">id#</span></span> 
- <span data-ttu-id="2500b-1070">ID</span><span class="sxs-lookup"><span data-stu-id="2500b-1070">ids#</span></span> 
- <span data-ttu-id="2500b-1071">idcard card#</span><span class="sxs-lookup"><span data-stu-id="2500b-1071">idcard card#</span></span> 
- <span data-ttu-id="2500b-1072">idcard cards#</span><span class="sxs-lookup"><span data-stu-id="2500b-1072">idcard cards#</span></span> 
- <span data-ttu-id="2500b-1073">idcard#</span><span class="sxs-lookup"><span data-stu-id="2500b-1073">idcard#</span></span> 
- <span data-ttu-id="2500b-1074">identification card#</span><span class="sxs-lookup"><span data-stu-id="2500b-1074">identification card#</span></span> 
- <span data-ttu-id="2500b-1075">identification cards#</span><span class="sxs-lookup"><span data-stu-id="2500b-1075">identification cards#</span></span> 
- <span data-ttu-id="2500b-1076">identificazione</span><span class="sxs-lookup"><span data-stu-id="2500b-1076">identification#</span></span> 
   
## <a name="canada-health-service-number"></a><span data-ttu-id="2500b-1077">Canada - Codice del servizio sanitario</span><span class="sxs-lookup"><span data-stu-id="2500b-1077">Canada Health Service Number</span></span>

### <a name="format"></a><span data-ttu-id="2500b-1078">Formato</span><span class="sxs-lookup"><span data-stu-id="2500b-1078">Format</span></span>

<span data-ttu-id="2500b-1079">10 cifre</span><span class="sxs-lookup"><span data-stu-id="2500b-1079">10 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="2500b-1080">Modello</span><span class="sxs-lookup"><span data-stu-id="2500b-1080">Pattern</span></span>

<span data-ttu-id="2500b-1081">10 cifre</span><span class="sxs-lookup"><span data-stu-id="2500b-1081">10 digits</span></span>

### <a name="checksum"></a><span data-ttu-id="2500b-1082">Checksum</span><span class="sxs-lookup"><span data-stu-id="2500b-1082">Checksum</span></span>

<span data-ttu-id="2500b-1083">No</span><span class="sxs-lookup"><span data-stu-id="2500b-1083">No</span></span>

### <a name="definition"></a><span data-ttu-id="2500b-1084">Definizione</span><span class="sxs-lookup"><span data-stu-id="2500b-1084">Definition</span></span>

<span data-ttu-id="2500b-1085">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="2500b-1085">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2500b-1086">L'espressione regolare Regex_canada_health_service_number restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="2500b-1086">The regular expression Regex_canada_health_service_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="2500b-1087">Viene trovata una parola chiave da Keyword_canada_health_service_number.</span><span class="sxs-lookup"><span data-stu-id="2500b-1087">A keyword from Keyword_canada_health_service_number is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="2500b-1088">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="2500b-1088">Keywords</span></span>

#### <a name="keywordcanadahealthservicenumber"></a><span data-ttu-id="2500b-1089">Keyword_canada_health_service_number</span><span class="sxs-lookup"><span data-stu-id="2500b-1089">Keyword_canada_health_service_number</span></span>

- <span data-ttu-id="2500b-1090">personal health number</span><span class="sxs-lookup"><span data-stu-id="2500b-1090">personal health number</span></span>
- <span data-ttu-id="2500b-1091">patient information</span><span class="sxs-lookup"><span data-stu-id="2500b-1091">patient information</span></span>
- <span data-ttu-id="2500b-1092">health services</span><span class="sxs-lookup"><span data-stu-id="2500b-1092">health services</span></span>
- <span data-ttu-id="2500b-1093">speciality services</span><span class="sxs-lookup"><span data-stu-id="2500b-1093">speciality services</span></span>
- <span data-ttu-id="2500b-1094">automobile accident</span><span class="sxs-lookup"><span data-stu-id="2500b-1094">automobile accident</span></span>
- <span data-ttu-id="2500b-1095">patient hospital</span><span class="sxs-lookup"><span data-stu-id="2500b-1095">patient hospital</span></span>
- <span data-ttu-id="2500b-1096">psichiatra</span><span class="sxs-lookup"><span data-stu-id="2500b-1096">psychiatrist</span></span>
- <span data-ttu-id="2500b-1097">workers compensation</span><span class="sxs-lookup"><span data-stu-id="2500b-1097">workers compensation</span></span>
- <span data-ttu-id="2500b-1098">Disability</span><span class="sxs-lookup"><span data-stu-id="2500b-1098">disability</span></span>
      
## <a name="canada-passport-number"></a><span data-ttu-id="2500b-1099">Canada - Numero di passaporto</span><span class="sxs-lookup"><span data-stu-id="2500b-1099">Canada Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="2500b-1100">Formato</span><span class="sxs-lookup"><span data-stu-id="2500b-1100">Format</span></span>

<span data-ttu-id="2500b-1101">Due lettere maiuscole seguite da 6 cifre</span><span class="sxs-lookup"><span data-stu-id="2500b-1101">Two uppercase letters followed by six digits</span></span>

### <a name="pattern"></a><span data-ttu-id="2500b-1102">Modello</span><span class="sxs-lookup"><span data-stu-id="2500b-1102">Pattern</span></span>

<span data-ttu-id="2500b-1103">Due lettere maiuscole seguite da 6 cifre</span><span class="sxs-lookup"><span data-stu-id="2500b-1103">Two uppercase letters followed by six digits</span></span>

### <a name="checksum"></a><span data-ttu-id="2500b-1104">Checksum</span><span class="sxs-lookup"><span data-stu-id="2500b-1104">Checksum</span></span>

<span data-ttu-id="2500b-1105">No</span><span class="sxs-lookup"><span data-stu-id="2500b-1105">No</span></span>

### <a name="definition"></a><span data-ttu-id="2500b-1106">Definizione</span><span class="sxs-lookup"><span data-stu-id="2500b-1106">Definition</span></span>

<span data-ttu-id="2500b-1107">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="2500b-1107">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2500b-1108">L'espressione regolare Regex_canada_passport_number restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="2500b-1108">The regular expression Regex_canada_passport_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="2500b-1109">Viene trovata una parola chiave da Keyword_canada_passport_number o Keyword_passport.</span><span class="sxs-lookup"><span data-stu-id="2500b-1109">A keyword from Keyword_canada_passport_number or Keyword_passport is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="2500b-1110">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="2500b-1110">Keywords</span></span>

#### <a name="keywordcanadapassportnumber"></a><span data-ttu-id="2500b-1111">Keyword_canada_passport_number</span><span class="sxs-lookup"><span data-stu-id="2500b-1111">Keyword_canada_passport_number</span></span>

- <span data-ttu-id="2500b-1112">canadian citizenship</span><span class="sxs-lookup"><span data-stu-id="2500b-1112">canadian citizenship</span></span>
- <span data-ttu-id="2500b-1113">canadian passport</span><span class="sxs-lookup"><span data-stu-id="2500b-1113">canadian passport</span></span>
- <span data-ttu-id="2500b-1114">passport application</span><span class="sxs-lookup"><span data-stu-id="2500b-1114">passport application</span></span>
- <span data-ttu-id="2500b-1115">passport photos</span><span class="sxs-lookup"><span data-stu-id="2500b-1115">passport photos</span></span>
- <span data-ttu-id="2500b-1116">certified translator</span><span class="sxs-lookup"><span data-stu-id="2500b-1116">certified translator</span></span>
- <span data-ttu-id="2500b-1117">canadian citizens</span><span class="sxs-lookup"><span data-stu-id="2500b-1117">canadian citizens</span></span>
- <span data-ttu-id="2500b-1118">processing times</span><span class="sxs-lookup"><span data-stu-id="2500b-1118">processing times</span></span>
- <span data-ttu-id="2500b-1119">renewal application</span><span class="sxs-lookup"><span data-stu-id="2500b-1119">renewal application</span></span>

#### <a name="keywordpassport"></a><span data-ttu-id="2500b-1120">Keyword_passport</span><span class="sxs-lookup"><span data-stu-id="2500b-1120">Keyword_passport</span></span>

- <span data-ttu-id="2500b-1121">Passport Number</span><span class="sxs-lookup"><span data-stu-id="2500b-1121">Passport Number</span></span>
- <span data-ttu-id="2500b-1122">Passport No</span><span class="sxs-lookup"><span data-stu-id="2500b-1122">Passport No</span></span>
- <span data-ttu-id="2500b-1123">Passport#</span><span class="sxs-lookup"><span data-stu-id="2500b-1123">Passport #</span></span>
- <span data-ttu-id="2500b-1124">Passaporto</span><span class="sxs-lookup"><span data-stu-id="2500b-1124">Passport#</span></span>
- <span data-ttu-id="2500b-1125">PassportID</span><span class="sxs-lookup"><span data-stu-id="2500b-1125">PassportID</span></span>
- <span data-ttu-id="2500b-1126">Passportno</span><span class="sxs-lookup"><span data-stu-id="2500b-1126">Passportno</span></span>
- <span data-ttu-id="2500b-1127">passportnumber</span><span class="sxs-lookup"><span data-stu-id="2500b-1127">passportnumber</span></span>
- <span data-ttu-id="2500b-1128">パスポート</span><span class="sxs-lookup"><span data-stu-id="2500b-1128">パスポート</span></span>
- <span data-ttu-id="2500b-1129">パスポート番号</span><span class="sxs-lookup"><span data-stu-id="2500b-1129">パスポート番号</span></span>
- <span data-ttu-id="2500b-1130">パスポートのNum</span><span class="sxs-lookup"><span data-stu-id="2500b-1130">パスポートのNum</span></span>
- <span data-ttu-id="2500b-1131">パスポート＃</span><span class="sxs-lookup"><span data-stu-id="2500b-1131">パスポート＃</span></span>
- <span data-ttu-id="2500b-1132">Numéro de passeport</span><span class="sxs-lookup"><span data-stu-id="2500b-1132">Numéro de passeport</span></span>
- <span data-ttu-id="2500b-1133">Passeport n °</span><span class="sxs-lookup"><span data-stu-id="2500b-1133">Passeport n °</span></span>
- <span data-ttu-id="2500b-1134">Passeport Non</span><span class="sxs-lookup"><span data-stu-id="2500b-1134">Passeport Non</span></span>
- <span data-ttu-id="2500b-1135">Passeport#</span><span class="sxs-lookup"><span data-stu-id="2500b-1135">Passeport #</span></span>
- <span data-ttu-id="2500b-1136">Passeport</span><span class="sxs-lookup"><span data-stu-id="2500b-1136">Passeport#</span></span>
- <span data-ttu-id="2500b-1137">PasseportNon</span><span class="sxs-lookup"><span data-stu-id="2500b-1137">PasseportNon</span></span>
- <span data-ttu-id="2500b-1138">Passeportn °</span><span class="sxs-lookup"><span data-stu-id="2500b-1138">Passeportn °</span></span>
   
## <a name="canada-personal-health-identification-number-phin"></a><span data-ttu-id="2500b-1139">Canada - Numero di identificazione sanitaria personale (PHIN)</span><span class="sxs-lookup"><span data-stu-id="2500b-1139">Canada Personal Health Identification Number (PHIN)</span></span>

### <a name="format"></a><span data-ttu-id="2500b-1140">Formato</span><span class="sxs-lookup"><span data-stu-id="2500b-1140">Format</span></span>

<span data-ttu-id="2500b-1141">9 cifre</span><span class="sxs-lookup"><span data-stu-id="2500b-1141">Nine digits</span></span>

### <a name="pattern"></a><span data-ttu-id="2500b-1142">Modello</span><span class="sxs-lookup"><span data-stu-id="2500b-1142">Pattern</span></span>

<span data-ttu-id="2500b-1143">9 cifre</span><span class="sxs-lookup"><span data-stu-id="2500b-1143">Nine digits</span></span>

### <a name="checksum"></a><span data-ttu-id="2500b-1144">Checksum</span><span class="sxs-lookup"><span data-stu-id="2500b-1144">Checksum</span></span>

<span data-ttu-id="2500b-1145">No</span><span class="sxs-lookup"><span data-stu-id="2500b-1145">No</span></span>

### <a name="definition"></a><span data-ttu-id="2500b-1146">Definizione</span><span class="sxs-lookup"><span data-stu-id="2500b-1146">Definition</span></span>

<span data-ttu-id="2500b-1147">Un criterio DLP è 75% fiducioso di aver rilevato questo tipo di informazioni riservate se, entro 300 caratteri: l'espressione regolare Regex_canada_phin trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="2500b-1147">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The regular expression Regex_canada_phin finds content that matches the pattern.</span></span>
<span data-ttu-id="2500b-1148">Sono state trovate almeno due parole chiave di Keyword_canada_phin o Keyword_canada_provinces..</span><span class="sxs-lookup"><span data-stu-id="2500b-1148">At least two keywords from Keyword_canada_phin or Keyword_canada_provinces are found..</span></span>

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

### <a name="keywords"></a><span data-ttu-id="2500b-1149">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="2500b-1149">Keywords</span></span>

#### <a name="keywordcanadaphin"></a><span data-ttu-id="2500b-1150">Keyword_canada_phin</span><span class="sxs-lookup"><span data-stu-id="2500b-1150">Keyword_canada_phin</span></span>

- <span data-ttu-id="2500b-1151">social insurance number</span><span class="sxs-lookup"><span data-stu-id="2500b-1151">social insurance number</span></span>
- <span data-ttu-id="2500b-1152">health information act</span><span class="sxs-lookup"><span data-stu-id="2500b-1152">health information act</span></span>
- <span data-ttu-id="2500b-1153">income tax information</span><span class="sxs-lookup"><span data-stu-id="2500b-1153">income tax information</span></span>
- <span data-ttu-id="2500b-1154">manitoba health</span><span class="sxs-lookup"><span data-stu-id="2500b-1154">manitoba health</span></span>
- <span data-ttu-id="2500b-1155">health registration</span><span class="sxs-lookup"><span data-stu-id="2500b-1155">health registration</span></span>
- <span data-ttu-id="2500b-1156">prescription purchases</span><span class="sxs-lookup"><span data-stu-id="2500b-1156">prescription purchases</span></span>
- <span data-ttu-id="2500b-1157">benefit eligibility</span><span class="sxs-lookup"><span data-stu-id="2500b-1157">benefit eligibility</span></span>
- <span data-ttu-id="2500b-1158">personal health</span><span class="sxs-lookup"><span data-stu-id="2500b-1158">personal health</span></span>
- <span data-ttu-id="2500b-1159">power of attorney</span><span class="sxs-lookup"><span data-stu-id="2500b-1159">power of attorney</span></span>
- <span data-ttu-id="2500b-1160">registration number</span><span class="sxs-lookup"><span data-stu-id="2500b-1160">registration number</span></span>
- <span data-ttu-id="2500b-1161">personal health number</span><span class="sxs-lookup"><span data-stu-id="2500b-1161">personal health number</span></span>
- <span data-ttu-id="2500b-1162">practitioner referral</span><span class="sxs-lookup"><span data-stu-id="2500b-1162">practitioner referral</span></span>
- <span data-ttu-id="2500b-1163">wellness professional</span><span class="sxs-lookup"><span data-stu-id="2500b-1163">wellness professional</span></span>
- <span data-ttu-id="2500b-1164">patient referral</span><span class="sxs-lookup"><span data-stu-id="2500b-1164">patient referral</span></span>
- <span data-ttu-id="2500b-1165">health and wellness</span><span class="sxs-lookup"><span data-stu-id="2500b-1165">health and wellness</span></span>

#### <a name="keywordcanadaprovinces"></a><span data-ttu-id="2500b-1166">Keyword_canada_provinces</span><span class="sxs-lookup"><span data-stu-id="2500b-1166">Keyword_canada_provinces</span></span>

- <span data-ttu-id="2500b-1167">Nunavut</span><span class="sxs-lookup"><span data-stu-id="2500b-1167">Nunavut</span></span>
- <span data-ttu-id="2500b-1168">Quebec</span><span class="sxs-lookup"><span data-stu-id="2500b-1168">Quebec</span></span>
- <span data-ttu-id="2500b-1169">Northwest Territories</span><span class="sxs-lookup"><span data-stu-id="2500b-1169">Northwest Territories</span></span>
- <span data-ttu-id="2500b-1170">Ontario</span><span class="sxs-lookup"><span data-stu-id="2500b-1170">Ontario</span></span>
- <span data-ttu-id="2500b-1171">British Columbia</span><span class="sxs-lookup"><span data-stu-id="2500b-1171">British Columbia</span></span>
- <span data-ttu-id="2500b-1172">Filippa</span><span class="sxs-lookup"><span data-stu-id="2500b-1172">Alberta</span></span>
- <span data-ttu-id="2500b-1173">Saskatchewan</span><span class="sxs-lookup"><span data-stu-id="2500b-1173">Saskatchewan</span></span>
- <span data-ttu-id="2500b-1174">Manitoba</span><span class="sxs-lookup"><span data-stu-id="2500b-1174">Manitoba</span></span>
- <span data-ttu-id="2500b-1175">Yukon</span><span class="sxs-lookup"><span data-stu-id="2500b-1175">Yukon</span></span>
- <span data-ttu-id="2500b-1176">Newfoundland and Labrador</span><span class="sxs-lookup"><span data-stu-id="2500b-1176">Newfoundland and Labrador</span></span>
- <span data-ttu-id="2500b-1177">New Brunswick</span><span class="sxs-lookup"><span data-stu-id="2500b-1177">New Brunswick</span></span>
- <span data-ttu-id="2500b-1178">Nova Scotia</span><span class="sxs-lookup"><span data-stu-id="2500b-1178">Nova Scotia</span></span>
- <span data-ttu-id="2500b-1179">Prince Edward Island</span><span class="sxs-lookup"><span data-stu-id="2500b-1179">Prince Edward Island</span></span>
- <span data-ttu-id="2500b-1180">Canada</span><span class="sxs-lookup"><span data-stu-id="2500b-1180">Canada</span></span>
   
## <a name="canada-social-insurance-number"></a><span data-ttu-id="2500b-1181">Canada - Numero di assicurazione sociale</span><span class="sxs-lookup"><span data-stu-id="2500b-1181">Canada Social Insurance Number</span></span>

### <a name="format"></a><span data-ttu-id="2500b-1182">Formato</span><span class="sxs-lookup"><span data-stu-id="2500b-1182">Format</span></span>

<span data-ttu-id="2500b-1183">9 cifre con spazi o lineette facoltativi</span><span class="sxs-lookup"><span data-stu-id="2500b-1183">Nine digits with optional hyphens or spaces</span></span>

### <a name="pattern"></a><span data-ttu-id="2500b-1184">Modello</span><span class="sxs-lookup"><span data-stu-id="2500b-1184">Pattern</span></span>

<span data-ttu-id="2500b-1185">Formattato</span><span class="sxs-lookup"><span data-stu-id="2500b-1185">Formatted:</span></span>
- <span data-ttu-id="2500b-1186">Tre cifre</span><span class="sxs-lookup"><span data-stu-id="2500b-1186">Three digits</span></span> 
- <span data-ttu-id="2500b-1187">Una lineetta o uno spazio</span><span class="sxs-lookup"><span data-stu-id="2500b-1187">A hyphen or space</span></span> 
- <span data-ttu-id="2500b-1188">Tre cifre</span><span class="sxs-lookup"><span data-stu-id="2500b-1188">Three digits</span></span> 
- <span data-ttu-id="2500b-1189">Una lineetta o uno spazio</span><span class="sxs-lookup"><span data-stu-id="2500b-1189">A hyphen or space</span></span> 
- <span data-ttu-id="2500b-1190">Tre cifre</span><span class="sxs-lookup"><span data-stu-id="2500b-1190">Three digits</span></span>

<span data-ttu-id="2500b-1191">Non formattato: nove cifre</span><span class="sxs-lookup"><span data-stu-id="2500b-1191">Unformatted: Nine digits</span></span>

### <a name="checksum"></a><span data-ttu-id="2500b-1192">Checksum</span><span class="sxs-lookup"><span data-stu-id="2500b-1192">Checksum</span></span>

<span data-ttu-id="2500b-1193">Sì</span><span class="sxs-lookup"><span data-stu-id="2500b-1193">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="2500b-1194">Definizione</span><span class="sxs-lookup"><span data-stu-id="2500b-1194">Definition</span></span>

<span data-ttu-id="2500b-1195">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="2500b-1195">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2500b-1196">La funzione Func_canadian_sin restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="2500b-1196">The function Func_canadian_sin finds content that matches the pattern.</span></span>
- <span data-ttu-id="2500b-1197">Almeno due delle seguenti combinazioni:</span><span class="sxs-lookup"><span data-stu-id="2500b-1197">At least two of any combination of the following:</span></span>
    - <span data-ttu-id="2500b-1198">Viene trovata una parola chiave da Keyword_sin.</span><span class="sxs-lookup"><span data-stu-id="2500b-1198">A keyword from Keyword_sin is found.</span></span>
    - <span data-ttu-id="2500b-1199">Viene trovata una parola chiave da Keyword_sin_collaborative.</span><span class="sxs-lookup"><span data-stu-id="2500b-1199">A keyword from Keyword_sin_collaborative is found.</span></span>
    - <span data-ttu-id="2500b-1200">La funzione Func_eu_date rileva una data nel formato corretto.</span><span class="sxs-lookup"><span data-stu-id="2500b-1200">The function Func_eu_date finds a date in the right date format.</span></span>
- <span data-ttu-id="2500b-1201">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="2500b-1201">The checksum passes.</span></span>

<span data-ttu-id="2500b-1202">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="2500b-1202">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2500b-1203">La funzione Func_unformatted_canadian_sin restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="2500b-1203">The function Func_unformatted_canadian_sin finds content that matches the pattern.</span></span>
- <span data-ttu-id="2500b-1204">Viene trovata una parola chiave da Keyword_sin.</span><span class="sxs-lookup"><span data-stu-id="2500b-1204">A keyword from Keyword_sin is found.</span></span>
- <span data-ttu-id="2500b-1205">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="2500b-1205">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="2500b-1206">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="2500b-1206">Keywords</span></span>

#### <a name="keywordsin"></a><span data-ttu-id="2500b-1207">Keyword_sin</span><span class="sxs-lookup"><span data-stu-id="2500b-1207">Keyword_sin</span></span>

- <span data-ttu-id="2500b-1208">sin</span><span class="sxs-lookup"><span data-stu-id="2500b-1208">sin</span></span> 
- <span data-ttu-id="2500b-1209">social insurance</span><span class="sxs-lookup"><span data-stu-id="2500b-1209">social insurance</span></span> 
- <span data-ttu-id="2500b-1210">numero d'assurance sociale</span><span class="sxs-lookup"><span data-stu-id="2500b-1210">numero d'assurance sociale</span></span> 
- <span data-ttu-id="2500b-1211">peccati</span><span class="sxs-lookup"><span data-stu-id="2500b-1211">sins</span></span> 
- <span data-ttu-id="2500b-1212">SSN</span><span class="sxs-lookup"><span data-stu-id="2500b-1212">ssn</span></span> 
- <span data-ttu-id="2500b-1213">SNSS</span><span class="sxs-lookup"><span data-stu-id="2500b-1213">ssns</span></span> 
- <span data-ttu-id="2500b-1214">social security</span><span class="sxs-lookup"><span data-stu-id="2500b-1214">social security</span></span> 
- <span data-ttu-id="2500b-1215">numero d'assurance social</span><span class="sxs-lookup"><span data-stu-id="2500b-1215">numero d'assurance social</span></span> 
- <span data-ttu-id="2500b-1216">national identification number</span><span class="sxs-lookup"><span data-stu-id="2500b-1216">national identification number</span></span> 
- <span data-ttu-id="2500b-1217">national id</span><span class="sxs-lookup"><span data-stu-id="2500b-1217">national id</span></span> 
- <span data-ttu-id="2500b-1218">sin</span><span class="sxs-lookup"><span data-stu-id="2500b-1218">sin#</span></span> 
- <span data-ttu-id="2500b-1219">soc ins</span><span class="sxs-lookup"><span data-stu-id="2500b-1219">soc ins</span></span> 
- <span data-ttu-id="2500b-1220">social ins</span><span class="sxs-lookup"><span data-stu-id="2500b-1220">social ins</span></span> 

#### <a name="keywordsincollaborative"></a><span data-ttu-id="2500b-1221">Keyword_sin_collaborative</span><span class="sxs-lookup"><span data-stu-id="2500b-1221">Keyword_sin_collaborative</span></span>

- <span data-ttu-id="2500b-1222">driver's license</span><span class="sxs-lookup"><span data-stu-id="2500b-1222">driver's license</span></span> 
- <span data-ttu-id="2500b-1223">drivers license</span><span class="sxs-lookup"><span data-stu-id="2500b-1223">drivers license</span></span> 
- <span data-ttu-id="2500b-1224">driver's licence</span><span class="sxs-lookup"><span data-stu-id="2500b-1224">driver's licence</span></span> 
- <span data-ttu-id="2500b-1225">drivers licence</span><span class="sxs-lookup"><span data-stu-id="2500b-1225">drivers licence</span></span> 
- <span data-ttu-id="2500b-1226">DOB</span><span class="sxs-lookup"><span data-stu-id="2500b-1226">DOB</span></span> 
- <span data-ttu-id="2500b-1227">Data di nascita</span><span class="sxs-lookup"><span data-stu-id="2500b-1227">Birthdate</span></span> 
- <span data-ttu-id="2500b-1228">Compleanno</span><span class="sxs-lookup"><span data-stu-id="2500b-1228">Birthday</span></span> 
- <span data-ttu-id="2500b-1229">Date of Birth</span><span class="sxs-lookup"><span data-stu-id="2500b-1229">Date of Birth</span></span> 
   
## <a name="chile-identity-card-number"></a><span data-ttu-id="2500b-1230">	Cile - Numero di carta di identità</span><span class="sxs-lookup"><span data-stu-id="2500b-1230">Chile Identity Card Number</span></span>

### <a name="format"></a><span data-ttu-id="2500b-1231">Formato</span><span class="sxs-lookup"><span data-stu-id="2500b-1231">Format</span></span>

<span data-ttu-id="2500b-1232">7-8 cifre più delimitatori una cifra di controllo o una lettera</span><span class="sxs-lookup"><span data-stu-id="2500b-1232">7-8 digits plus delimiters a check digit or letter</span></span>

### <a name="pattern"></a><span data-ttu-id="2500b-1233">Modello</span><span class="sxs-lookup"><span data-stu-id="2500b-1233">Pattern</span></span>

<span data-ttu-id="2500b-1234">7-8 cifre più delimitatori:</span><span class="sxs-lookup"><span data-stu-id="2500b-1234">7-8 digits plus delimiters:</span></span>
- <span data-ttu-id="2500b-1235">1-2 cifre</span><span class="sxs-lookup"><span data-stu-id="2500b-1235">1-2 digits</span></span> 
- <span data-ttu-id="2500b-1236">Un punto </span><span class="sxs-lookup"><span data-stu-id="2500b-1236">A period</span></span> 
- <span data-ttu-id="2500b-1237">Tre cifre</span><span class="sxs-lookup"><span data-stu-id="2500b-1237">Three digits</span></span> 
- <span data-ttu-id="2500b-1238">Un punto </span><span class="sxs-lookup"><span data-stu-id="2500b-1238">A period</span></span> 
- <span data-ttu-id="2500b-1239">Tre cifre</span><span class="sxs-lookup"><span data-stu-id="2500b-1239">Three digits</span></span> 
- <span data-ttu-id="2500b-1240">Un trattino</span><span class="sxs-lookup"><span data-stu-id="2500b-1240">A dash</span></span> 
- <span data-ttu-id="2500b-1241">Una cifra o una lettera (senza distinzione tra maiuscole e minuscole) che corrisponde a una cifra di controllo</span><span class="sxs-lookup"><span data-stu-id="2500b-1241">One digit or letter (not case sensitive) which is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="2500b-1242">Checksum</span><span class="sxs-lookup"><span data-stu-id="2500b-1242">Checksum</span></span>

<span data-ttu-id="2500b-1243">Sì</span><span class="sxs-lookup"><span data-stu-id="2500b-1243">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="2500b-1244">Definizione</span><span class="sxs-lookup"><span data-stu-id="2500b-1244">Definition</span></span>

<span data-ttu-id="2500b-1245">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="2500b-1245">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2500b-1246">La funzione Func_chile_id_card trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="2500b-1246">The function Func_chile_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="2500b-1247">Viene trovata una parola chiave da Keyword_chile_id_card.</span><span class="sxs-lookup"><span data-stu-id="2500b-1247">A keyword from Keyword_chile_id_card is found.</span></span>
- <span data-ttu-id="2500b-1248">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="2500b-1248">The checksum passes.</span></span>

<span data-ttu-id="2500b-1249">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="2500b-1249">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2500b-1250">La funzione Func_chile_id_card trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="2500b-1250">The function Func_chile_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="2500b-1251">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="2500b-1251">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="2500b-1252">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="2500b-1252">Keywords</span></span>

#### <a name="keywordchileidcard"></a><span data-ttu-id="2500b-1253">Keyword_chile_id_card</span><span class="sxs-lookup"><span data-stu-id="2500b-1253">Keyword_chile_id_card</span></span>

- <span data-ttu-id="2500b-1254">Numero di carta d’identità</span><span class="sxs-lookup"><span data-stu-id="2500b-1254">National Identification Number</span></span> 
- <span data-ttu-id="2500b-1255">Carta di identità</span><span class="sxs-lookup"><span data-stu-id="2500b-1255">Identity card</span></span> 
- <span data-ttu-id="2500b-1256">ID</span><span class="sxs-lookup"><span data-stu-id="2500b-1256">ID</span></span> 
- <span data-ttu-id="2500b-1257">Identificazione</span><span class="sxs-lookup"><span data-stu-id="2500b-1257">Identification</span></span> 
- <span data-ttu-id="2500b-1258">Rol Único Nacional</span><span class="sxs-lookup"><span data-stu-id="2500b-1258">Rol Único Nacional</span></span> 
- <span data-ttu-id="2500b-1259">Correre</span><span class="sxs-lookup"><span data-stu-id="2500b-1259">RUN</span></span> 
- <span data-ttu-id="2500b-1260">Rol Único Tributario</span><span class="sxs-lookup"><span data-stu-id="2500b-1260">Rol Único Tributario</span></span> 
- <span data-ttu-id="2500b-1261">CARREGGIATA</span><span class="sxs-lookup"><span data-stu-id="2500b-1261">RUT</span></span> 
- <span data-ttu-id="2500b-1262">Cédula de Identidad</span><span class="sxs-lookup"><span data-stu-id="2500b-1262">Cédula de Identidad</span></span> 
- <span data-ttu-id="2500b-1263">Número De Identificación Nacional</span><span class="sxs-lookup"><span data-stu-id="2500b-1263">Número De Identificación Nacional</span></span> 
- <span data-ttu-id="2500b-1264">Tarjeta de identificación</span><span class="sxs-lookup"><span data-stu-id="2500b-1264">Tarjeta de identificación</span></span> 
- <span data-ttu-id="2500b-1265">Identificación</span><span class="sxs-lookup"><span data-stu-id="2500b-1265">Identificación</span></span> 
   
## <a name="china-resident-identity-card-prc-number"></a><span data-ttu-id="2500b-1266">	Numero carta di identità per residenti in Cina (RPC)</span><span class="sxs-lookup"><span data-stu-id="2500b-1266">China Resident Identity Card (PRC) Number</span></span>

### <a name="format"></a><span data-ttu-id="2500b-1267">Formato</span><span class="sxs-lookup"><span data-stu-id="2500b-1267">Format</span></span>

<span data-ttu-id="2500b-1268">18 cifre</span><span class="sxs-lookup"><span data-stu-id="2500b-1268">18 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="2500b-1269">Modello</span><span class="sxs-lookup"><span data-stu-id="2500b-1269">Pattern</span></span>

<span data-ttu-id="2500b-1270">18 cifre:</span><span class="sxs-lookup"><span data-stu-id="2500b-1270">18 digits:</span></span>
- <span data-ttu-id="2500b-1271">Sei cifre, ovvero un codice indirizzo </span><span class="sxs-lookup"><span data-stu-id="2500b-1271">Six digits which are an address code</span></span> 
- <span data-ttu-id="2500b-1272">Otto cifre nel formato AAAAMMGG, ovvero la data di nascita </span><span class="sxs-lookup"><span data-stu-id="2500b-1272">Eight digits in the form YYYYMMDD which are the date of birth</span></span> 
- <span data-ttu-id="2500b-1273">Tre cifre, ovvero un codice di ordine </span><span class="sxs-lookup"><span data-stu-id="2500b-1273">Three digits which are an order code</span></span> 
- <span data-ttu-id="2500b-1274">Una cifra, ovvero una cifra di controllo</span><span class="sxs-lookup"><span data-stu-id="2500b-1274">One digit which is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="2500b-1275">Checksum</span><span class="sxs-lookup"><span data-stu-id="2500b-1275">Checksum</span></span>

<span data-ttu-id="2500b-1276">Sì</span><span class="sxs-lookup"><span data-stu-id="2500b-1276">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="2500b-1277">Definizione</span><span class="sxs-lookup"><span data-stu-id="2500b-1277">Definition</span></span>

<span data-ttu-id="2500b-1278">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="2500b-1278">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2500b-1279">La funzione Func_china_resident_id trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="2500b-1279">The function Func_china_resident_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="2500b-1280">Viene trovata una parola chiave da Keyword_china_resident_id.</span><span class="sxs-lookup"><span data-stu-id="2500b-1280">A keyword from Keyword_china_resident_id is found.</span></span>
- <span data-ttu-id="2500b-1281">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="2500b-1281">The checksum passes.</span></span>

<span data-ttu-id="2500b-1282">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="2500b-1282">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2500b-1283">La funzione Func_china_resident_id trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="2500b-1283">The function Func_china_resident_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="2500b-1284">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="2500b-1284">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="2500b-1285">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="2500b-1285">Keywords</span></span>

### <a name="keywordchinaresidentid"></a><span data-ttu-id="2500b-1286">Keyword_china_resident_id</span><span class="sxs-lookup"><span data-stu-id="2500b-1286">Keyword_china_resident_id</span></span>

- <span data-ttu-id="2500b-1287">Carta d’identità per residenti</span><span class="sxs-lookup"><span data-stu-id="2500b-1287">Resident Identity Card</span></span> 
- <span data-ttu-id="2500b-1288">RPC</span><span class="sxs-lookup"><span data-stu-id="2500b-1288">PRC</span></span> 
- <span data-ttu-id="2500b-1289">Carta d’identità</span><span class="sxs-lookup"><span data-stu-id="2500b-1289">National Identification Card</span></span> 
- <span data-ttu-id="2500b-1290">身份证</span><span class="sxs-lookup"><span data-stu-id="2500b-1290">身份证</span></span> 
- <span data-ttu-id="2500b-1291">居民 身份证</span><span class="sxs-lookup"><span data-stu-id="2500b-1291">居民 身份证</span></span> 
- <span data-ttu-id="2500b-1292">居民身份证</span><span class="sxs-lookup"><span data-stu-id="2500b-1292">居民身份证</span></span> 
- <span data-ttu-id="2500b-1293">鉴定</span><span class="sxs-lookup"><span data-stu-id="2500b-1293">鉴定</span></span> 
- <span data-ttu-id="2500b-1294">身分證</span><span class="sxs-lookup"><span data-stu-id="2500b-1294">身分證</span></span> 
- <span data-ttu-id="2500b-1295">居民 身份證</span><span class="sxs-lookup"><span data-stu-id="2500b-1295">居民 身份證</span></span>
- <span data-ttu-id="2500b-1296">鑑定</span><span class="sxs-lookup"><span data-stu-id="2500b-1296">鑑定</span></span> 
   
## <a name="credit-card-number"></a><span data-ttu-id="2500b-1297">Credit Card Number</span><span class="sxs-lookup"><span data-stu-id="2500b-1297">Credit Card Number</span></span>

### <a name="format"></a><span data-ttu-id="2500b-1298">Formato</span><span class="sxs-lookup"><span data-stu-id="2500b-1298">Format</span></span>

<span data-ttu-id="2500b-1299">16 cifre che possono essere formattate o non formattate (dddddddddddddddd) e devono superare il test di Luhn.</span><span class="sxs-lookup"><span data-stu-id="2500b-1299">16 digits which can be formatted or unformatted (dddddddddddddddd) and must pass the Luhn test.</span></span>

### <a name="pattern"></a><span data-ttu-id="2500b-1300">Modello</span><span class="sxs-lookup"><span data-stu-id="2500b-1300">Pattern</span></span>

<span data-ttu-id="2500b-1301">Modello molto complesso e solido che rileva carte di credito dei maggiori circuiti del mondo, ad esempio, Visa, MasterCard, Discover Card, JCB, American Express, nonché carte regalo e ticket restaurant.</span><span class="sxs-lookup"><span data-stu-id="2500b-1301">Very complex and robust pattern that detects cards from all major brands worldwide, including Visa, MasterCard, Discover Card, JCB, American Express, gift cards, and diner cards.</span></span>

### <a name="checksum"></a><span data-ttu-id="2500b-1302">Checksum</span><span class="sxs-lookup"><span data-stu-id="2500b-1302">Checksum</span></span>

<span data-ttu-id="2500b-1303">Yes, il checksum Luhn</span><span class="sxs-lookup"><span data-stu-id="2500b-1303">Yes, the Luhn checksum</span></span>

### <a name="definition"></a><span data-ttu-id="2500b-1304">Definizione</span><span class="sxs-lookup"><span data-stu-id="2500b-1304">Definition</span></span>

<span data-ttu-id="2500b-1305">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="2500b-1305">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2500b-1306">La funzione Func_credit_card restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="2500b-1306">The function Func_credit_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="2500b-1307">Si verifica una delle situazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="2500b-1307">One of the following is true:</span></span>
    - <span data-ttu-id="2500b-1308">Viene trovata una parola chiave da Keyword_cc_verification.</span><span class="sxs-lookup"><span data-stu-id="2500b-1308">A keyword from Keyword_cc_verification is found.</span></span>
    - <span data-ttu-id="2500b-1309">Viene trovata una parola chiave da Keyword_cc_name.</span><span class="sxs-lookup"><span data-stu-id="2500b-1309">A keyword from Keyword_cc_name is found.</span></span>
    - <span data-ttu-id="2500b-1310">La funzione Func_expiration_date rileva una data nel formato corretto.</span><span class="sxs-lookup"><span data-stu-id="2500b-1310">The function Func_expiration_date finds a date in the right date format.</span></span>
- <span data-ttu-id="2500b-1311">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="2500b-1311">The checksum passes.</span></span>

<span data-ttu-id="2500b-1312">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 65%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="2500b-1312">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2500b-1313">La funzione Func_credit_card restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="2500b-1313">The function Func_credit_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="2500b-1314">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="2500b-1314">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="2500b-1315">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="2500b-1315">Keywords</span></span>

#### <a name="keywordccverification"></a><span data-ttu-id="2500b-1316">Keyword_cc_verification</span><span class="sxs-lookup"><span data-stu-id="2500b-1316">Keyword_cc_verification</span></span>

- <span data-ttu-id="2500b-1317">card verification</span><span class="sxs-lookup"><span data-stu-id="2500b-1317">card verification</span></span>
- <span data-ttu-id="2500b-1318">card identification number</span><span class="sxs-lookup"><span data-stu-id="2500b-1318">card identification number</span></span>
- <span data-ttu-id="2500b-1319">CVN</span><span class="sxs-lookup"><span data-stu-id="2500b-1319">cvn</span></span>
- <span data-ttu-id="2500b-1320">ID</span><span class="sxs-lookup"><span data-stu-id="2500b-1320">cid</span></span>
- <span data-ttu-id="2500b-1321">CVC2</span><span class="sxs-lookup"><span data-stu-id="2500b-1321">cvc2</span></span>
- <span data-ttu-id="2500b-1322">CVV2</span><span class="sxs-lookup"><span data-stu-id="2500b-1322">cvv2</span></span>
- <span data-ttu-id="2500b-1323">pin block</span><span class="sxs-lookup"><span data-stu-id="2500b-1323">pin block</span></span>
- <span data-ttu-id="2500b-1324">security code</span><span class="sxs-lookup"><span data-stu-id="2500b-1324">security code</span></span>
- <span data-ttu-id="2500b-1325">security number</span><span class="sxs-lookup"><span data-stu-id="2500b-1325">security number</span></span>
- <span data-ttu-id="2500b-1326">security no</span><span class="sxs-lookup"><span data-stu-id="2500b-1326">security no</span></span>
- <span data-ttu-id="2500b-1327">issue number</span><span class="sxs-lookup"><span data-stu-id="2500b-1327">issue number</span></span>
- <span data-ttu-id="2500b-1328">issue no</span><span class="sxs-lookup"><span data-stu-id="2500b-1328">issue no</span></span>
- <span data-ttu-id="2500b-1329">cryptogramme</span><span class="sxs-lookup"><span data-stu-id="2500b-1329">cryptogramme</span></span>
- <span data-ttu-id="2500b-1330">numéro de sécurité</span><span class="sxs-lookup"><span data-stu-id="2500b-1330">numéro de sécurité</span></span>
- <span data-ttu-id="2500b-1331">numero de securite</span><span class="sxs-lookup"><span data-stu-id="2500b-1331">numero de securite</span></span>
- <span data-ttu-id="2500b-1332">kreditkartenprüfnummer</span><span class="sxs-lookup"><span data-stu-id="2500b-1332">kreditkartenprüfnummer</span></span>
- <span data-ttu-id="2500b-1333">kreditkartenprufnummer</span><span class="sxs-lookup"><span data-stu-id="2500b-1333">kreditkartenprufnummer</span></span>
- <span data-ttu-id="2500b-1334">prüfziffer</span><span class="sxs-lookup"><span data-stu-id="2500b-1334">prüfziffer</span></span>
- <span data-ttu-id="2500b-1335">Prufziffer</span><span class="sxs-lookup"><span data-stu-id="2500b-1335">prufziffer</span></span>
- <span data-ttu-id="2500b-1336">sicherheits Kode</span><span class="sxs-lookup"><span data-stu-id="2500b-1336">sicherheits Kode</span></span>
- <span data-ttu-id="2500b-1337">sicherheitscode</span><span class="sxs-lookup"><span data-stu-id="2500b-1337">sicherheitscode</span></span>
- <span data-ttu-id="2500b-1338">sicherheitsnummer</span><span class="sxs-lookup"><span data-stu-id="2500b-1338">sicherheitsnummer</span></span>
- <span data-ttu-id="2500b-1339">verfalldatum</span><span class="sxs-lookup"><span data-stu-id="2500b-1339">verfalldatum</span></span>
- <span data-ttu-id="2500b-1340">codice di verifica</span><span class="sxs-lookup"><span data-stu-id="2500b-1340">codice di verifica</span></span>
- <span data-ttu-id="2500b-1341">Cod.</span><span class="sxs-lookup"><span data-stu-id="2500b-1341">cod.</span></span> <span data-ttu-id="2500b-1342">sicurezza</span><span class="sxs-lookup"><span data-stu-id="2500b-1342">sicurezza</span></span>
- <span data-ttu-id="2500b-1343">cod sicurezza</span><span class="sxs-lookup"><span data-stu-id="2500b-1343">cod sicurezza</span></span>
- <span data-ttu-id="2500b-1344">n autorizzazione</span><span class="sxs-lookup"><span data-stu-id="2500b-1344">n autorizzazione</span></span>
- <span data-ttu-id="2500b-1345">Código</span><span class="sxs-lookup"><span data-stu-id="2500b-1345">código</span></span>
- <span data-ttu-id="2500b-1346">Codigo</span><span class="sxs-lookup"><span data-stu-id="2500b-1346">codigo</span></span>
- <span data-ttu-id="2500b-1347">Cod.</span><span class="sxs-lookup"><span data-stu-id="2500b-1347">cod.</span></span> <span data-ttu-id="2500b-1348">SEG</span><span class="sxs-lookup"><span data-stu-id="2500b-1348">seg</span></span>
- <span data-ttu-id="2500b-1349">cod seg</span><span class="sxs-lookup"><span data-stu-id="2500b-1349">cod seg</span></span>
- <span data-ttu-id="2500b-1350">código de segurança</span><span class="sxs-lookup"><span data-stu-id="2500b-1350">código de segurança</span></span>
- <span data-ttu-id="2500b-1351">codigo de seguranca</span><span class="sxs-lookup"><span data-stu-id="2500b-1351">codigo de seguranca</span></span>
- <span data-ttu-id="2500b-1352">codigo de segurança</span><span class="sxs-lookup"><span data-stu-id="2500b-1352">codigo de segurança</span></span>
- <span data-ttu-id="2500b-1353">código de seguranca</span><span class="sxs-lookup"><span data-stu-id="2500b-1353">código de seguranca</span></span>
- <span data-ttu-id="2500b-1354">cód.</span><span class="sxs-lookup"><span data-stu-id="2500b-1354">cód.</span></span> <span data-ttu-id="2500b-1355">Segurança</span><span class="sxs-lookup"><span data-stu-id="2500b-1355">segurança</span></span>
- <span data-ttu-id="2500b-1356">Cod.</span><span class="sxs-lookup"><span data-stu-id="2500b-1356">cod.</span></span> <span data-ttu-id="2500b-1357">SEGURANCA Cod.</span><span class="sxs-lookup"><span data-stu-id="2500b-1357">seguranca cod.</span></span> <span data-ttu-id="2500b-1358">Segurança</span><span class="sxs-lookup"><span data-stu-id="2500b-1358">segurança</span></span>
- <span data-ttu-id="2500b-1359">cód.</span><span class="sxs-lookup"><span data-stu-id="2500b-1359">cód.</span></span> <span data-ttu-id="2500b-1360">seguranca</span><span class="sxs-lookup"><span data-stu-id="2500b-1360">seguranca</span></span>
- <span data-ttu-id="2500b-1361">cód segurança</span><span class="sxs-lookup"><span data-stu-id="2500b-1361">cód segurança</span></span>
- <span data-ttu-id="2500b-1362">Cod SEGURANCA Cod Segurança</span><span class="sxs-lookup"><span data-stu-id="2500b-1362">cod seguranca cod segurança</span></span>
- <span data-ttu-id="2500b-1363">cód seguranca</span><span class="sxs-lookup"><span data-stu-id="2500b-1363">cód seguranca</span></span>
- <span data-ttu-id="2500b-1364">número de verificação</span><span class="sxs-lookup"><span data-stu-id="2500b-1364">número de verificação</span></span>
- <span data-ttu-id="2500b-1365">numero de verificacao</span><span class="sxs-lookup"><span data-stu-id="2500b-1365">numero de verificacao</span></span>
- <span data-ttu-id="2500b-1366">ablauf</span><span class="sxs-lookup"><span data-stu-id="2500b-1366">ablauf</span></span>
- <span data-ttu-id="2500b-1367">gültig bis</span><span class="sxs-lookup"><span data-stu-id="2500b-1367">gültig bis</span></span>
- <span data-ttu-id="2500b-1368">gültigkeitsdatum</span><span class="sxs-lookup"><span data-stu-id="2500b-1368">gültigkeitsdatum</span></span>
- <span data-ttu-id="2500b-1369">gultig bis</span><span class="sxs-lookup"><span data-stu-id="2500b-1369">gultig bis</span></span>
- <span data-ttu-id="2500b-1370">gultigkeitsdatum</span><span class="sxs-lookup"><span data-stu-id="2500b-1370">gultigkeitsdatum</span></span>
- <span data-ttu-id="2500b-1371">scadenza</span><span class="sxs-lookup"><span data-stu-id="2500b-1371">scadenza</span></span>
- <span data-ttu-id="2500b-1372">data scad</span><span class="sxs-lookup"><span data-stu-id="2500b-1372">data scad</span></span>
- <span data-ttu-id="2500b-1373">fecha de expiracion</span><span class="sxs-lookup"><span data-stu-id="2500b-1373">fecha de expiracion</span></span>
- <span data-ttu-id="2500b-1374">fecha de venc</span><span class="sxs-lookup"><span data-stu-id="2500b-1374">fecha de venc</span></span>
- <span data-ttu-id="2500b-1375">vencimiento</span><span class="sxs-lookup"><span data-stu-id="2500b-1375">vencimiento</span></span>
- <span data-ttu-id="2500b-1376">válido hasta</span><span class="sxs-lookup"><span data-stu-id="2500b-1376">válido hasta</span></span>
- <span data-ttu-id="2500b-1377">valido hasta</span><span class="sxs-lookup"><span data-stu-id="2500b-1377">valido hasta</span></span>
- <span data-ttu-id="2500b-1378">VTO</span><span class="sxs-lookup"><span data-stu-id="2500b-1378">vto</span></span>
- <span data-ttu-id="2500b-1379">data de expiração</span><span class="sxs-lookup"><span data-stu-id="2500b-1379">data de expiração</span></span>
- <span data-ttu-id="2500b-1380">data de expiracao</span><span class="sxs-lookup"><span data-stu-id="2500b-1380">data de expiracao</span></span>
- <span data-ttu-id="2500b-1381">data em que expira</span><span class="sxs-lookup"><span data-stu-id="2500b-1381">data em que expira</span></span>
- <span data-ttu-id="2500b-1382">validade</span><span class="sxs-lookup"><span data-stu-id="2500b-1382">validade</span></span>
- <span data-ttu-id="2500b-1383">Valor</span><span class="sxs-lookup"><span data-stu-id="2500b-1383">valor</span></span>
- <span data-ttu-id="2500b-1384">vencimento</span><span class="sxs-lookup"><span data-stu-id="2500b-1384">vencimento</span></span>
- <span data-ttu-id="2500b-1385">Venc</span><span class="sxs-lookup"><span data-stu-id="2500b-1385">Venc</span></span> 

#### <a name="keywordccname"></a><span data-ttu-id="2500b-1386">Keyword_cc_name</span><span class="sxs-lookup"><span data-stu-id="2500b-1386">Keyword_cc_name</span></span>

- <span data-ttu-id="2500b-1387">Amex</span><span class="sxs-lookup"><span data-stu-id="2500b-1387">amex</span></span>
- <span data-ttu-id="2500b-1388">american express</span><span class="sxs-lookup"><span data-stu-id="2500b-1388">american express</span></span>
- <span data-ttu-id="2500b-1389">AmericanExpress</span><span class="sxs-lookup"><span data-stu-id="2500b-1389">americanexpress</span></span>
- <span data-ttu-id="2500b-1390">Esempio</span><span class="sxs-lookup"><span data-stu-id="2500b-1390">Visa</span></span>
- <span data-ttu-id="2500b-1391">Mastercard</span><span class="sxs-lookup"><span data-stu-id="2500b-1391">mastercard</span></span>
- <span data-ttu-id="2500b-1392">master card</span><span class="sxs-lookup"><span data-stu-id="2500b-1392">master card</span></span>
- <span data-ttu-id="2500b-1393">MC</span><span class="sxs-lookup"><span data-stu-id="2500b-1393">mc</span></span> 
- <span data-ttu-id="2500b-1394">Mastercard</span><span class="sxs-lookup"><span data-stu-id="2500b-1394">mastercards</span></span>
- <span data-ttu-id="2500b-1395">master cards</span><span class="sxs-lookup"><span data-stu-id="2500b-1395">master cards</span></span>
- <span data-ttu-id="2500b-1396">diner's Club</span><span class="sxs-lookup"><span data-stu-id="2500b-1396">diner's Club</span></span>
- <span data-ttu-id="2500b-1397">diners club</span><span class="sxs-lookup"><span data-stu-id="2500b-1397">diners club</span></span>
- <span data-ttu-id="2500b-1398">DinersClub</span><span class="sxs-lookup"><span data-stu-id="2500b-1398">dinersclub</span></span>
- <span data-ttu-id="2500b-1399">discover card</span><span class="sxs-lookup"><span data-stu-id="2500b-1399">discover card</span></span>
- <span data-ttu-id="2500b-1400">discovercard</span><span class="sxs-lookup"><span data-stu-id="2500b-1400">discovercard</span></span>
- <span data-ttu-id="2500b-1401">discover cards</span><span class="sxs-lookup"><span data-stu-id="2500b-1401">discover cards</span></span>
- <span data-ttu-id="2500b-1402">JCB</span><span class="sxs-lookup"><span data-stu-id="2500b-1402">JCB</span></span>
- <span data-ttu-id="2500b-1403">japanese card bureau</span><span class="sxs-lookup"><span data-stu-id="2500b-1403">japanese card bureau</span></span>
- <span data-ttu-id="2500b-1404">carte blanche</span><span class="sxs-lookup"><span data-stu-id="2500b-1404">carte blanche</span></span>
- <span data-ttu-id="2500b-1405">carteblanche</span><span class="sxs-lookup"><span data-stu-id="2500b-1405">carteblanche</span></span>
- <span data-ttu-id="2500b-1406">credit card</span><span class="sxs-lookup"><span data-stu-id="2500b-1406">credit card</span></span>
- <span data-ttu-id="2500b-1407">CC</span><span class="sxs-lookup"><span data-stu-id="2500b-1407">cc#</span></span>
- <span data-ttu-id="2500b-1408">CC #:</span><span class="sxs-lookup"><span data-stu-id="2500b-1408">cc#:</span></span>
- <span data-ttu-id="2500b-1409">expiration date</span><span class="sxs-lookup"><span data-stu-id="2500b-1409">expiration date</span></span>
- <span data-ttu-id="2500b-1410">exp date</span><span class="sxs-lookup"><span data-stu-id="2500b-1410">exp date</span></span>
- <span data-ttu-id="2500b-1411">expiry date</span><span class="sxs-lookup"><span data-stu-id="2500b-1411">expiry date</span></span>
- <span data-ttu-id="2500b-1412">date d’expiration</span><span class="sxs-lookup"><span data-stu-id="2500b-1412">date d’expiration</span></span>
- <span data-ttu-id="2500b-1413">date d'exp</span><span class="sxs-lookup"><span data-stu-id="2500b-1413">date d'exp</span></span>
- <span data-ttu-id="2500b-1414">date expiration</span><span class="sxs-lookup"><span data-stu-id="2500b-1414">date expiration</span></span>
- <span data-ttu-id="2500b-1415">bank card</span><span class="sxs-lookup"><span data-stu-id="2500b-1415">bank card</span></span>
- <span data-ttu-id="2500b-1416">Bankcard</span><span class="sxs-lookup"><span data-stu-id="2500b-1416">bankcard</span></span>
- <span data-ttu-id="2500b-1417">card number</span><span class="sxs-lookup"><span data-stu-id="2500b-1417">card number</span></span>
- <span data-ttu-id="2500b-1418">card num</span><span class="sxs-lookup"><span data-stu-id="2500b-1418">card num</span></span>
- <span data-ttu-id="2500b-1419">cardnumber</span><span class="sxs-lookup"><span data-stu-id="2500b-1419">cardnumber</span></span>
- <span data-ttu-id="2500b-1420">cardnumbers</span><span class="sxs-lookup"><span data-stu-id="2500b-1420">cardnumbers</span></span>
- <span data-ttu-id="2500b-1421">card numbers</span><span class="sxs-lookup"><span data-stu-id="2500b-1421">card numbers</span></span>
- <span data-ttu-id="2500b-1422">CreditCard</span><span class="sxs-lookup"><span data-stu-id="2500b-1422">creditcard</span></span>
- <span data-ttu-id="2500b-1423">credit cards</span><span class="sxs-lookup"><span data-stu-id="2500b-1423">credit cards</span></span>
- <span data-ttu-id="2500b-1424">creditcards.com</span><span class="sxs-lookup"><span data-stu-id="2500b-1424">creditcards</span></span>
- <span data-ttu-id="2500b-1425">Ccn</span><span class="sxs-lookup"><span data-stu-id="2500b-1425">ccn</span></span>
- <span data-ttu-id="2500b-1426">card holder</span><span class="sxs-lookup"><span data-stu-id="2500b-1426">card holder</span></span>
- <span data-ttu-id="2500b-1427">titolare</span><span class="sxs-lookup"><span data-stu-id="2500b-1427">cardholder</span></span>
- <span data-ttu-id="2500b-1428">card holders</span><span class="sxs-lookup"><span data-stu-id="2500b-1428">card holders</span></span>
- <span data-ttu-id="2500b-1429">titolari</span><span class="sxs-lookup"><span data-stu-id="2500b-1429">cardholders</span></span>
- <span data-ttu-id="2500b-1430">check card</span><span class="sxs-lookup"><span data-stu-id="2500b-1430">check card</span></span>
- <span data-ttu-id="2500b-1431">checkcard</span><span class="sxs-lookup"><span data-stu-id="2500b-1431">checkcard</span></span>
- <span data-ttu-id="2500b-1432">check cards</span><span class="sxs-lookup"><span data-stu-id="2500b-1432">check cards</span></span>
- <span data-ttu-id="2500b-1433">checkcards</span><span class="sxs-lookup"><span data-stu-id="2500b-1433">checkcards</span></span>
- <span data-ttu-id="2500b-1434">debit card</span><span class="sxs-lookup"><span data-stu-id="2500b-1434">debit card</span></span>
- <span data-ttu-id="2500b-1435">debitcard</span><span class="sxs-lookup"><span data-stu-id="2500b-1435">debitcard</span></span>
- <span data-ttu-id="2500b-1436">debit cards</span><span class="sxs-lookup"><span data-stu-id="2500b-1436">debit cards</span></span>
- <span data-ttu-id="2500b-1437">debitcards</span><span class="sxs-lookup"><span data-stu-id="2500b-1437">debitcards</span></span>
- <span data-ttu-id="2500b-1438">atm card</span><span class="sxs-lookup"><span data-stu-id="2500b-1438">atm card</span></span>
- <span data-ttu-id="2500b-1439">atmcard</span><span class="sxs-lookup"><span data-stu-id="2500b-1439">atmcard</span></span>
- <span data-ttu-id="2500b-1440">atm cards</span><span class="sxs-lookup"><span data-stu-id="2500b-1440">atm cards</span></span>
- <span data-ttu-id="2500b-1441">atmcards</span><span class="sxs-lookup"><span data-stu-id="2500b-1441">atmcards</span></span>
- <span data-ttu-id="2500b-1442">Enroute</span><span class="sxs-lookup"><span data-stu-id="2500b-1442">enroute</span></span>
- <span data-ttu-id="2500b-1443">en route</span><span class="sxs-lookup"><span data-stu-id="2500b-1443">en route</span></span>
- <span data-ttu-id="2500b-1444">card type</span><span class="sxs-lookup"><span data-stu-id="2500b-1444">card type</span></span>
- <span data-ttu-id="2500b-1445">carte bancaire</span><span class="sxs-lookup"><span data-stu-id="2500b-1445">carte bancaire</span></span>
- <span data-ttu-id="2500b-1446">carte de crédit</span><span class="sxs-lookup"><span data-stu-id="2500b-1446">carte de crédit</span></span>
- <span data-ttu-id="2500b-1447">carte de credit</span><span class="sxs-lookup"><span data-stu-id="2500b-1447">carte de credit</span></span>
- <span data-ttu-id="2500b-1448">numéro de carte</span><span class="sxs-lookup"><span data-stu-id="2500b-1448">numéro de carte</span></span>
- <span data-ttu-id="2500b-1449">numero de carte</span><span class="sxs-lookup"><span data-stu-id="2500b-1449">numero de carte</span></span>
- <span data-ttu-id="2500b-1450">nº de la carte</span><span class="sxs-lookup"><span data-stu-id="2500b-1450">nº de la carte</span></span>
- <span data-ttu-id="2500b-1451">nº de carte</span><span class="sxs-lookup"><span data-stu-id="2500b-1451">nº de carte</span></span>
- <span data-ttu-id="2500b-1452">kreditkarte</span><span class="sxs-lookup"><span data-stu-id="2500b-1452">kreditkarte</span></span>
- <span data-ttu-id="2500b-1453">Karte</span><span class="sxs-lookup"><span data-stu-id="2500b-1453">karte</span></span>
- <span data-ttu-id="2500b-1454">karteninhaber</span><span class="sxs-lookup"><span data-stu-id="2500b-1454">karteninhaber</span></span>
- <span data-ttu-id="2500b-1455">karteninhabers</span><span class="sxs-lookup"><span data-stu-id="2500b-1455">karteninhabers</span></span>
- <span data-ttu-id="2500b-1456">kreditkarteninhaber</span><span class="sxs-lookup"><span data-stu-id="2500b-1456">kreditkarteninhaber</span></span>
- <span data-ttu-id="2500b-1457">kreditkarteninstitut</span><span class="sxs-lookup"><span data-stu-id="2500b-1457">kreditkarteninstitut</span></span>
- <span data-ttu-id="2500b-1458">kreditkartentyp</span><span class="sxs-lookup"><span data-stu-id="2500b-1458">kreditkartentyp</span></span>
- <span data-ttu-id="2500b-1459">eigentümername</span><span class="sxs-lookup"><span data-stu-id="2500b-1459">eigentümername</span></span>
- <span data-ttu-id="2500b-1460">kartennr</span><span class="sxs-lookup"><span data-stu-id="2500b-1460">kartennr</span></span> 
- <span data-ttu-id="2500b-1461">kartennummer</span><span class="sxs-lookup"><span data-stu-id="2500b-1461">kartennummer</span></span>
- <span data-ttu-id="2500b-1462">kreditkartennummer</span><span class="sxs-lookup"><span data-stu-id="2500b-1462">kreditkartennummer</span></span>
- <span data-ttu-id="2500b-1463">Kreditkarten-Nummer</span><span class="sxs-lookup"><span data-stu-id="2500b-1463">kreditkarten-nummer</span></span>
- <span data-ttu-id="2500b-1464">carta di credito</span><span class="sxs-lookup"><span data-stu-id="2500b-1464">carta di credito</span></span>
- <span data-ttu-id="2500b-1465">carta credito</span><span class="sxs-lookup"><span data-stu-id="2500b-1465">carta credito</span></span>
- <span data-ttu-id="2500b-1466">carta</span><span class="sxs-lookup"><span data-stu-id="2500b-1466">carta</span></span>
- <span data-ttu-id="2500b-1467">n carta</span><span class="sxs-lookup"><span data-stu-id="2500b-1467">n carta</span></span>
- <span data-ttu-id="2500b-1468">Nr.</span><span class="sxs-lookup"><span data-stu-id="2500b-1468">nr.</span></span> <span data-ttu-id="2500b-1469">carta</span><span class="sxs-lookup"><span data-stu-id="2500b-1469">carta</span></span>
- <span data-ttu-id="2500b-1470">nr carta</span><span class="sxs-lookup"><span data-stu-id="2500b-1470">nr carta</span></span>
- <span data-ttu-id="2500b-1471">numero carta</span><span class="sxs-lookup"><span data-stu-id="2500b-1471">numero carta</span></span>
- <span data-ttu-id="2500b-1472">numero della carta</span><span class="sxs-lookup"><span data-stu-id="2500b-1472">numero della carta</span></span>
- <span data-ttu-id="2500b-1473">numero di carta</span><span class="sxs-lookup"><span data-stu-id="2500b-1473">numero di carta</span></span>
- <span data-ttu-id="2500b-1474">tarjeta credito</span><span class="sxs-lookup"><span data-stu-id="2500b-1474">tarjeta credito</span></span>
- <span data-ttu-id="2500b-1475">tarjeta de credito</span><span class="sxs-lookup"><span data-stu-id="2500b-1475">tarjeta de credito</span></span>
- <span data-ttu-id="2500b-1476">tarjeta crédito</span><span class="sxs-lookup"><span data-stu-id="2500b-1476">tarjeta crédito</span></span>
- <span data-ttu-id="2500b-1477">tarjeta de crédito</span><span class="sxs-lookup"><span data-stu-id="2500b-1477">tarjeta de crédito</span></span>
- <span data-ttu-id="2500b-1478">tarjeta de atm</span><span class="sxs-lookup"><span data-stu-id="2500b-1478">tarjeta de atm</span></span>
- <span data-ttu-id="2500b-1479">tarjeta atm</span><span class="sxs-lookup"><span data-stu-id="2500b-1479">tarjeta atm</span></span>
- <span data-ttu-id="2500b-1480">tarjeta debito</span><span class="sxs-lookup"><span data-stu-id="2500b-1480">tarjeta debito</span></span>
- <span data-ttu-id="2500b-1481">tarjeta de debito</span><span class="sxs-lookup"><span data-stu-id="2500b-1481">tarjeta de debito</span></span>
- <span data-ttu-id="2500b-1482">tarjeta débito</span><span class="sxs-lookup"><span data-stu-id="2500b-1482">tarjeta débito</span></span>
- <span data-ttu-id="2500b-1483">tarjeta de débito</span><span class="sxs-lookup"><span data-stu-id="2500b-1483">tarjeta de débito</span></span>
- <span data-ttu-id="2500b-1484">nº de tarjeta</span><span class="sxs-lookup"><span data-stu-id="2500b-1484">nº de tarjeta</span></span>
- <span data-ttu-id="2500b-1485">No.</span><span class="sxs-lookup"><span data-stu-id="2500b-1485">no.</span></span> <span data-ttu-id="2500b-1486">de tarjeta</span><span class="sxs-lookup"><span data-stu-id="2500b-1486">de tarjeta</span></span>
- <span data-ttu-id="2500b-1487">no de tarjeta</span><span class="sxs-lookup"><span data-stu-id="2500b-1487">no de tarjeta</span></span>
- <span data-ttu-id="2500b-1488">numero de tarjeta</span><span class="sxs-lookup"><span data-stu-id="2500b-1488">numero de tarjeta</span></span>
- <span data-ttu-id="2500b-1489">número de tarjeta</span><span class="sxs-lookup"><span data-stu-id="2500b-1489">número de tarjeta</span></span>
- <span data-ttu-id="2500b-1490">tarjeta no</span><span class="sxs-lookup"><span data-stu-id="2500b-1490">tarjeta no</span></span>
- <span data-ttu-id="2500b-1491">tarjetahabiente</span><span class="sxs-lookup"><span data-stu-id="2500b-1491">tarjetahabiente</span></span>
- <span data-ttu-id="2500b-1492">cartão de crédito</span><span class="sxs-lookup"><span data-stu-id="2500b-1492">cartão de crédito</span></span>
- <span data-ttu-id="2500b-1493">cartão de credito</span><span class="sxs-lookup"><span data-stu-id="2500b-1493">cartão de credito</span></span>
- <span data-ttu-id="2500b-1494">cartao de crédito</span><span class="sxs-lookup"><span data-stu-id="2500b-1494">cartao de crédito</span></span>
- <span data-ttu-id="2500b-1495">cartao de credito</span><span class="sxs-lookup"><span data-stu-id="2500b-1495">cartao de credito</span></span>
- <span data-ttu-id="2500b-1496">cartão de débito</span><span class="sxs-lookup"><span data-stu-id="2500b-1496">cartão de débito</span></span>
- <span data-ttu-id="2500b-1497">cartao de débito</span><span class="sxs-lookup"><span data-stu-id="2500b-1497">cartao de débito</span></span>
- <span data-ttu-id="2500b-1498">cartão de debito</span><span class="sxs-lookup"><span data-stu-id="2500b-1498">cartão de debito</span></span>
- <span data-ttu-id="2500b-1499">cartao de debito</span><span class="sxs-lookup"><span data-stu-id="2500b-1499">cartao de debito</span></span>
- <span data-ttu-id="2500b-1500">débito automático</span><span class="sxs-lookup"><span data-stu-id="2500b-1500">débito automático</span></span>
- <span data-ttu-id="2500b-1501">debito automatico</span><span class="sxs-lookup"><span data-stu-id="2500b-1501">debito automatico</span></span>
- <span data-ttu-id="2500b-1502">número do cartão</span><span class="sxs-lookup"><span data-stu-id="2500b-1502">número do cartão</span></span>
- <span data-ttu-id="2500b-1503">numero do cartão</span><span class="sxs-lookup"><span data-stu-id="2500b-1503">numero do cartão</span></span> 
- <span data-ttu-id="2500b-1504">número do cartao</span><span class="sxs-lookup"><span data-stu-id="2500b-1504">número do cartao</span></span>
- <span data-ttu-id="2500b-1505">numero do cartao</span><span class="sxs-lookup"><span data-stu-id="2500b-1505">numero do cartao</span></span>
- <span data-ttu-id="2500b-1506">número de cartão</span><span class="sxs-lookup"><span data-stu-id="2500b-1506">número de cartão</span></span>
- <span data-ttu-id="2500b-1507">numero de cartão</span><span class="sxs-lookup"><span data-stu-id="2500b-1507">numero de cartão</span></span>
- <span data-ttu-id="2500b-1508">número de cartao</span><span class="sxs-lookup"><span data-stu-id="2500b-1508">número de cartao</span></span>
- <span data-ttu-id="2500b-1509">numero de cartao</span><span class="sxs-lookup"><span data-stu-id="2500b-1509">numero de cartao</span></span>
- <span data-ttu-id="2500b-1510">nº do cartão</span><span class="sxs-lookup"><span data-stu-id="2500b-1510">nº do cartão</span></span>
- <span data-ttu-id="2500b-1511">nº do cartao</span><span class="sxs-lookup"><span data-stu-id="2500b-1511">nº do cartao</span></span>
- <span data-ttu-id="2500b-1512">n º.</span><span class="sxs-lookup"><span data-stu-id="2500b-1512">nº.</span></span> <span data-ttu-id="2500b-1513">do cartão</span><span class="sxs-lookup"><span data-stu-id="2500b-1513">do cartão</span></span>
- <span data-ttu-id="2500b-1514">no do cartão</span><span class="sxs-lookup"><span data-stu-id="2500b-1514">no do cartão</span></span>
- <span data-ttu-id="2500b-1515">no do cartao</span><span class="sxs-lookup"><span data-stu-id="2500b-1515">no do cartao</span></span>
- <span data-ttu-id="2500b-1516">No.</span><span class="sxs-lookup"><span data-stu-id="2500b-1516">no.</span></span> <span data-ttu-id="2500b-1517">do cartão</span><span class="sxs-lookup"><span data-stu-id="2500b-1517">do cartão</span></span>
- <span data-ttu-id="2500b-1518">No.</span><span class="sxs-lookup"><span data-stu-id="2500b-1518">no.</span></span> <span data-ttu-id="2500b-1519">do cartao</span><span class="sxs-lookup"><span data-stu-id="2500b-1519">do cartao</span></span> 
   
## <a name="croatia-identity-card-number"></a><span data-ttu-id="2500b-1520">Numero di carta di identità della Croazia</span><span class="sxs-lookup"><span data-stu-id="2500b-1520">Croatia Identity Card Number</span></span>

### <a name="format"></a><span data-ttu-id="2500b-1521">Formato</span><span class="sxs-lookup"><span data-stu-id="2500b-1521">Format</span></span>

<span data-ttu-id="2500b-1522">9 cifre</span><span class="sxs-lookup"><span data-stu-id="2500b-1522">Nine digits</span></span>

### <a name="pattern"></a><span data-ttu-id="2500b-1523">Modello</span><span class="sxs-lookup"><span data-stu-id="2500b-1523">Pattern</span></span>

<span data-ttu-id="2500b-1524">9 cifre consecutive</span><span class="sxs-lookup"><span data-stu-id="2500b-1524">Nine consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="2500b-1525">Checksum</span><span class="sxs-lookup"><span data-stu-id="2500b-1525">Checksum</span></span>

<span data-ttu-id="2500b-1526">No</span><span class="sxs-lookup"><span data-stu-id="2500b-1526">No</span></span>

### <a name="definition"></a><span data-ttu-id="2500b-1527">Definizione</span><span class="sxs-lookup"><span data-stu-id="2500b-1527">Definition</span></span>

<span data-ttu-id="2500b-1528">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="2500b-1528">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2500b-1529">La funzione Func_croatia_id_card trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="2500b-1529">The function Func_croatia_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="2500b-1530">Viene trovata una parola chiave da Keyword_croatia_id_card.</span><span class="sxs-lookup"><span data-stu-id="2500b-1530">A keyword from Keyword_croatia_id_card is found.</span></span>

```
<!--Croatia Identity Card Number-->
<Entity id="ff12f884-c20a-4189-b185-34c8e7258d47" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_croatia_id_card"/>
     <Match idRef="Keyword_croatia_id_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="2500b-1531">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="2500b-1531">Keywords</span></span>

#### <a name="keywordcroatiaidcard"></a><span data-ttu-id="2500b-1532">Keyword_croatia_id_card</span><span class="sxs-lookup"><span data-stu-id="2500b-1532">Keyword_croatia_id_card</span></span>

- <span data-ttu-id="2500b-1533">Carta d’identità croata</span><span class="sxs-lookup"><span data-stu-id="2500b-1533">Croatian identity card</span></span>
- <span data-ttu-id="2500b-1534">Osobna iskaznica</span><span class="sxs-lookup"><span data-stu-id="2500b-1534">Osobna iskaznica</span></span>

   
## <a name="croatia-personal-identification-oib-number"></a><span data-ttu-id="2500b-1535">Numero di identificazione personale (OIB) - Croazia</span><span class="sxs-lookup"><span data-stu-id="2500b-1535">Croatia Personal Identification (OIB) Number</span></span>

### <a name="format"></a><span data-ttu-id="2500b-1536">Formato</span><span class="sxs-lookup"><span data-stu-id="2500b-1536">Format</span></span>

<span data-ttu-id="2500b-1537">11 cifre</span><span class="sxs-lookup"><span data-stu-id="2500b-1537">11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="2500b-1538">Modello</span><span class="sxs-lookup"><span data-stu-id="2500b-1538">Pattern</span></span>

<span data-ttu-id="2500b-1539">11 cifre:</span><span class="sxs-lookup"><span data-stu-id="2500b-1539">11 digits:</span></span>
- <span data-ttu-id="2500b-1540">10 cifre</span><span class="sxs-lookup"><span data-stu-id="2500b-1540">10 digits</span></span> 
- <span data-ttu-id="2500b-1541">La cifra finale è una cifra di controllo ai fini dello scambio di dati internazionali, le lettere HR vengono aggiunte prima delle undici cifre.</span><span class="sxs-lookup"><span data-stu-id="2500b-1541">Final digit is a check digit For the purposes of international data exchange, the letters HR are added preceding the eleven digits.</span></span>

### <a name="checksum"></a><span data-ttu-id="2500b-1542">Checksum</span><span class="sxs-lookup"><span data-stu-id="2500b-1542">Checksum</span></span>

<span data-ttu-id="2500b-1543">Sì</span><span class="sxs-lookup"><span data-stu-id="2500b-1543">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="2500b-1544">Definizione</span><span class="sxs-lookup"><span data-stu-id="2500b-1544">Definition</span></span>

<span data-ttu-id="2500b-1545">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="2500b-1545">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2500b-1546">La funzione Func_croatia_oib_number trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="2500b-1546">The function Func_croatia_oib_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="2500b-1547">Viene trovata una parola chiave da Keyword_croatia_oib_number.</span><span class="sxs-lookup"><span data-stu-id="2500b-1547">A keyword from Keyword_croatia_oib_number is found.</span></span>
- <span data-ttu-id="2500b-1548">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="2500b-1548">The checksum passes.</span></span>

<span data-ttu-id="2500b-1549">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="2500b-1549">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2500b-1550">La funzione Func_croatia_oib_number trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="2500b-1550">The function Func_croatia_oib_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="2500b-1551">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="2500b-1551">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="2500b-1552">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="2500b-1552">Keywords</span></span>

#### <a name="keywordcroatiaoibnumber"></a><span data-ttu-id="2500b-1553">Keyword_croatia_oib_number</span><span class="sxs-lookup"><span data-stu-id="2500b-1553">Keyword_croatia_oib_number</span></span>

- <span data-ttu-id="2500b-1554">Codice PIN</span><span class="sxs-lookup"><span data-stu-id="2500b-1554">Personal Identification Number</span></span>
- <span data-ttu-id="2500b-1555">Osobni identifikacijski broj</span><span class="sxs-lookup"><span data-stu-id="2500b-1555">Osobni identifikacijski broj</span></span> 
- <span data-ttu-id="2500b-1556">OIB</span><span class="sxs-lookup"><span data-stu-id="2500b-1556">OIB</span></span> 

   
## <a name="czech-personal-identity-number"></a><span data-ttu-id="2500b-1557">Numero di identità personale ceco</span><span class="sxs-lookup"><span data-stu-id="2500b-1557">Czech Personal Identity Number</span></span>

### <a name="format"></a><span data-ttu-id="2500b-1558">Formato</span><span class="sxs-lookup"><span data-stu-id="2500b-1558">Format</span></span>

<span data-ttu-id="2500b-1559">Nove cifre con Slash opzionale (formato precedente) 10 cifre con barra di inoltro facoltativa (nuovo formato)</span><span class="sxs-lookup"><span data-stu-id="2500b-1559">Nine digits with optional forward slash (old format) 10 digits with optional forward slash (new format)</span></span>

### <a name="pattern"></a><span data-ttu-id="2500b-1560">Modello</span><span class="sxs-lookup"><span data-stu-id="2500b-1560">Pattern</span></span>

<span data-ttu-id="2500b-1561">Nove cifre (formato obsoleto):</span><span class="sxs-lookup"><span data-stu-id="2500b-1561">Nine digits (old format):</span></span>
- <span data-ttu-id="2500b-1562">9 cifre</span><span class="sxs-lookup"><span data-stu-id="2500b-1562">Nine digits</span></span>

<span data-ttu-id="2500b-1563">O</span><span class="sxs-lookup"><span data-stu-id="2500b-1563">OR</span></span>

- <span data-ttu-id="2500b-1564">Sei cifre che rappresentano la data di nascita</span><span class="sxs-lookup"><span data-stu-id="2500b-1564">Six digits that represent date of birth</span></span>
- <span data-ttu-id="2500b-1565">Una barra</span><span class="sxs-lookup"><span data-stu-id="2500b-1565">A forward slash</span></span>
- <span data-ttu-id="2500b-1566">Tre cifre</span><span class="sxs-lookup"><span data-stu-id="2500b-1566">Three digits</span></span>

<span data-ttu-id="2500b-1567">10 cifre (nuovo formato):</span><span class="sxs-lookup"><span data-stu-id="2500b-1567">10 digits (new format):</span></span>
- <span data-ttu-id="2500b-1568">10 cifre</span><span class="sxs-lookup"><span data-stu-id="2500b-1568">10 digits</span></span>

<span data-ttu-id="2500b-1569">O</span><span class="sxs-lookup"><span data-stu-id="2500b-1569">OR</span></span>

- <span data-ttu-id="2500b-1570">Sei cifre che rappresentano la data di nascita</span><span class="sxs-lookup"><span data-stu-id="2500b-1570">Six digits that represent date of birth</span></span>
- <span data-ttu-id="2500b-1571">Una barra</span><span class="sxs-lookup"><span data-stu-id="2500b-1571">A forward slash</span></span> 
- <span data-ttu-id="2500b-1572">Quattro cifre in cui l'ultima cifra è una cifra di controllo</span><span class="sxs-lookup"><span data-stu-id="2500b-1572">Four digits where last digit is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="2500b-1573">Checksum</span><span class="sxs-lookup"><span data-stu-id="2500b-1573">Checksum</span></span>

<span data-ttu-id="2500b-1574">Sì</span><span class="sxs-lookup"><span data-stu-id="2500b-1574">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="2500b-1575">Definizione</span><span class="sxs-lookup"><span data-stu-id="2500b-1575">Definition</span></span>

<span data-ttu-id="2500b-1576">Un criterio DLP è 85% fiducioso di aver rilevato questo tipo di informazioni riservate se, entro 300 caratteri: la funzione Func_czech_id_card trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="2500b-1576">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The function Func_czech_id_card finds content that matches the pattern.</span></span>
<span data-ttu-id="2500b-1577">Viene trovata una parola chiave da Keyword_czech_id_card.</span><span class="sxs-lookup"><span data-stu-id="2500b-1577">A keyword from Keyword_czech_id_card is found.</span></span>
<span data-ttu-id="2500b-1578">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="2500b-1578">The checksum passes.</span></span>

```
<!-- Czech Personal Identity Number -->
<Entity id="60c0725a-4eb6-455b-9dda-05d8a7396497"      patternsProximity="300" recommendedConfidence="85">
   <Pattern confidenceLevel="85">
      <IdMatch idRef="Func_czech_id_card" />
      <Match idRef="Keyword_czech_id_card" />
   </Pattern>
</Entity>
```
### <a name="keywords"></a><span data-ttu-id="2500b-1579">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="2500b-1579">Keywords</span></span>

- <span data-ttu-id="2500b-1580">numero di identità personale ceco</span><span class="sxs-lookup"><span data-stu-id="2500b-1580">czech personal identity number</span></span>
- <span data-ttu-id="2500b-1581">Rodné číslo</span><span class="sxs-lookup"><span data-stu-id="2500b-1581">Rodné číslo</span></span>
   
## <a name="denmark-personal-identification-number"></a><span data-ttu-id="2500b-1582">Codice PIN - Danimarca</span><span class="sxs-lookup"><span data-stu-id="2500b-1582">Denmark Personal Identification Number</span></span>

### <a name="format"></a><span data-ttu-id="2500b-1583">Formato</span><span class="sxs-lookup"><span data-stu-id="2500b-1583">Format</span></span>

<span data-ttu-id="2500b-1584">10 cifre contenenti una lineetta</span><span class="sxs-lookup"><span data-stu-id="2500b-1584">10 digits containing a hyphen</span></span>

### <a name="pattern"></a><span data-ttu-id="2500b-1585">Modello</span><span class="sxs-lookup"><span data-stu-id="2500b-1585">Pattern</span></span>

<span data-ttu-id="2500b-1586">10 cifre:</span><span class="sxs-lookup"><span data-stu-id="2500b-1586">10 digits:</span></span>
- <span data-ttu-id="2500b-1587">Sei cifre nel formato GGMMAA, ovvero la data di nascita</span><span class="sxs-lookup"><span data-stu-id="2500b-1587">Six digits in the format DDMMYY which are the date of birth</span></span> 
- <span data-ttu-id="2500b-1588">Una lineetta</span><span class="sxs-lookup"><span data-stu-id="2500b-1588">A hyphen</span></span> 
- <span data-ttu-id="2500b-1589">Quattro cifre, dove l'ultima è una cifra di controllo</span><span class="sxs-lookup"><span data-stu-id="2500b-1589">Four digits where the final digit is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="2500b-1590">Checksum</span><span class="sxs-lookup"><span data-stu-id="2500b-1590">Checksum</span></span>

<span data-ttu-id="2500b-1591">Sì</span><span class="sxs-lookup"><span data-stu-id="2500b-1591">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="2500b-1592">Definizione</span><span class="sxs-lookup"><span data-stu-id="2500b-1592">Definition</span></span>

<span data-ttu-id="2500b-1593">Un criterio DLP è 75% fiducioso di aver rilevato questo tipo di informazioni riservate se, entro 300 caratteri: l'espressione regolare Regex_denmark_id trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="2500b-1593">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The regular expression Regex_denmark_id finds content that matches the pattern.</span></span>
<span data-ttu-id="2500b-1594">Viene trovata una parola chiave da Keyword_denmark_id.</span><span class="sxs-lookup"><span data-stu-id="2500b-1594">A keyword from Keyword_denmark_id is found.</span></span>
<span data-ttu-id="2500b-1595">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="2500b-1595">The checksum passes.</span></span>

```
<!-- Denmark Personal Identification Number -->
<Entity id="6c4f2fef-56e1-4c00-8093-88d7a01cf460" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_denmark_id"/>
     <Match idRef="Keyword_denmark_id"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="2500b-1596">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="2500b-1596">Keywords</span></span>

#### <a name="keyworddenmarkid"></a><span data-ttu-id="2500b-1597">Keyword_denmark_id</span><span class="sxs-lookup"><span data-stu-id="2500b-1597">Keyword_denmark_id</span></span>

- <span data-ttu-id="2500b-1598">Codice PIN</span><span class="sxs-lookup"><span data-stu-id="2500b-1598">Personal Identification Number</span></span>
- <span data-ttu-id="2500b-1599">CPR</span><span class="sxs-lookup"><span data-stu-id="2500b-1599">CPR</span></span>
- <span data-ttu-id="2500b-1600">Det Centrale Personregister</span><span class="sxs-lookup"><span data-stu-id="2500b-1600">Det Centrale Personregister</span></span>
- <span data-ttu-id="2500b-1601">Personnummer</span><span class="sxs-lookup"><span data-stu-id="2500b-1601">Personnummer</span></span>
   
## <a name="drug-enforcement-agency-dea-number"></a><span data-ttu-id="2500b-1602">Numero della Drug Enforcement Agency (DEA)</span><span class="sxs-lookup"><span data-stu-id="2500b-1602">Drug Enforcement Agency (DEA) Number</span></span>

### <a name="format"></a><span data-ttu-id="2500b-1603">Formato</span><span class="sxs-lookup"><span data-stu-id="2500b-1603">Format</span></span>

<span data-ttu-id="2500b-1604">Due lettere seguite da 7 cifre</span><span class="sxs-lookup"><span data-stu-id="2500b-1604">Two letters followed by seven digits</span></span>

### <a name="pattern"></a><span data-ttu-id="2500b-1605">Modello</span><span class="sxs-lookup"><span data-stu-id="2500b-1605">Pattern</span></span>

<span data-ttu-id="2500b-1606">Il modello deve includere tutti gli elementi seguenti:</span><span class="sxs-lookup"><span data-stu-id="2500b-1606">Pattern must include all of the following:</span></span>
- <span data-ttu-id="2500b-1607">Una lettera (senza distinzione tra maiuscole/minuscole) da questo gruppo di lettere: abcdefghjklmnprstux, ovvero un codice registrante</span><span class="sxs-lookup"><span data-stu-id="2500b-1607">One letter (not case sensitive) from this set of possible letters: abcdefghjklmnprstux, which is a registrant code</span></span> 
- <span data-ttu-id="2500b-1608">Una lettera (senza distinzione tra maiuscole/minuscole), ovvero la prima lettera del cognome del registrante</span><span class="sxs-lookup"><span data-stu-id="2500b-1608">One letter (not case sensitive), which is the first letter of the registrant's last name</span></span> 
- <span data-ttu-id="2500b-1609">7 cifre e l'ultima è quella di controllo</span><span class="sxs-lookup"><span data-stu-id="2500b-1609">Seven digits, the last of which is the check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="2500b-1610">Checksum</span><span class="sxs-lookup"><span data-stu-id="2500b-1610">Checksum</span></span>

<span data-ttu-id="2500b-1611">Sì</span><span class="sxs-lookup"><span data-stu-id="2500b-1611">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="2500b-1612">Definizione</span><span class="sxs-lookup"><span data-stu-id="2500b-1612">Definition</span></span>

<span data-ttu-id="2500b-1613">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="2500b-1613">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2500b-1614">La funzione Func_dea_number restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="2500b-1614">The function Func_dea_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="2500b-1615">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="2500b-1615">The checksum passes.</span></span>

```
<!-- DEA Number -->
<Entity id="9a5445ad-406e-43eb-8bd7-cac17ab6d0e4" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_dea_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="2500b-1616">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="2500b-1616">Keywords</span></span>

<span data-ttu-id="2500b-1617">Nessuno</span><span class="sxs-lookup"><span data-stu-id="2500b-1617">None</span></span>

   
## <a name="eu-debit-card-number"></a><span data-ttu-id="2500b-1618">Unione Europea - Numero di carta di debito</span><span class="sxs-lookup"><span data-stu-id="2500b-1618">EU Debit Card Number</span></span>

### <a name="format"></a><span data-ttu-id="2500b-1619">Formato</span><span class="sxs-lookup"><span data-stu-id="2500b-1619">Format</span></span>

<span data-ttu-id="2500b-1620">16 cifre</span><span class="sxs-lookup"><span data-stu-id="2500b-1620">16 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="2500b-1621">Modello</span><span class="sxs-lookup"><span data-stu-id="2500b-1621">Pattern</span></span>

<span data-ttu-id="2500b-1622">Modello molto complesso e solido</span><span class="sxs-lookup"><span data-stu-id="2500b-1622">Very complex and robust pattern</span></span>

### <a name="checksum"></a><span data-ttu-id="2500b-1623">Checksum</span><span class="sxs-lookup"><span data-stu-id="2500b-1623">Checksum</span></span>

<span data-ttu-id="2500b-1624">Sì</span><span class="sxs-lookup"><span data-stu-id="2500b-1624">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="2500b-1625">Definizione</span><span class="sxs-lookup"><span data-stu-id="2500b-1625">Definition</span></span>

<span data-ttu-id="2500b-1626">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="2500b-1626">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2500b-1627">La funzione Func_eu_debit_card restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="2500b-1627">The function Func_eu_debit_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="2500b-1628">Si verifica almeno una delle situazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="2500b-1628">At least one of the following is true:</span></span>
    - <span data-ttu-id="2500b-1629">Viene trovata una parola chiave da Keyword_eu_debit_card.</span><span class="sxs-lookup"><span data-stu-id="2500b-1629">A keyword from Keyword_eu_debit_card is found.</span></span>
    - <span data-ttu-id="2500b-1630">Viene trovata una parola chiave da Keyword_card_terms_dict.</span><span class="sxs-lookup"><span data-stu-id="2500b-1630">A keyword from Keyword_card_terms_dict is found.</span></span>
    - <span data-ttu-id="2500b-1631">Viene trovata una parola chiave da Keyword_card_security_terms_dict.</span><span class="sxs-lookup"><span data-stu-id="2500b-1631">A keyword from Keyword_card_security_terms_dict is found.</span></span>
    - <span data-ttu-id="2500b-1632">Viene trovata una parola chiave da Keyword_card_expiration_terms_dict.</span><span class="sxs-lookup"><span data-stu-id="2500b-1632">A keyword from Keyword_card_expiration_terms_dict is found.</span></span>
    - <span data-ttu-id="2500b-1633">La funzione Func_expiration_date rileva una data nel formato corretto.</span><span class="sxs-lookup"><span data-stu-id="2500b-1633">The function Func_expiration_date finds a date in the right date format.</span></span>
- <span data-ttu-id="2500b-1634">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="2500b-1634">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="2500b-1635">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="2500b-1635">Keywords</span></span>

#### <a name="keywordeudebitcard"></a><span data-ttu-id="2500b-1636">Keyword_eu_debit_card</span><span class="sxs-lookup"><span data-stu-id="2500b-1636">Keyword_eu_debit_card</span></span>

- <span data-ttu-id="2500b-1637">account number</span><span class="sxs-lookup"><span data-stu-id="2500b-1637">account number</span></span> 
- <span data-ttu-id="2500b-1638">card number</span><span class="sxs-lookup"><span data-stu-id="2500b-1638">card number</span></span> 
- <span data-ttu-id="2500b-1639">card no.</span><span class="sxs-lookup"><span data-stu-id="2500b-1639">card no.</span></span> 
- <span data-ttu-id="2500b-1640">security number</span><span class="sxs-lookup"><span data-stu-id="2500b-1640">security number</span></span> 
- <span data-ttu-id="2500b-1641">CC</span><span class="sxs-lookup"><span data-stu-id="2500b-1641">cc#</span></span> 

#### <a name="keywordcardtermsdict"></a><span data-ttu-id="2500b-1642">Keyword_card_terms_dict</span><span class="sxs-lookup"><span data-stu-id="2500b-1642">Keyword_card_terms_dict</span></span>

- <span data-ttu-id="2500b-1643">acct nbr</span><span class="sxs-lookup"><span data-stu-id="2500b-1643">acct nbr</span></span> 
- <span data-ttu-id="2500b-1644">acct num</span><span class="sxs-lookup"><span data-stu-id="2500b-1644">acct num</span></span> 
- <span data-ttu-id="2500b-1645">acct no</span><span class="sxs-lookup"><span data-stu-id="2500b-1645">acct no</span></span> 
- <span data-ttu-id="2500b-1646">american express</span><span class="sxs-lookup"><span data-stu-id="2500b-1646">american express</span></span> 
- <span data-ttu-id="2500b-1647">AmericanExpress</span><span class="sxs-lookup"><span data-stu-id="2500b-1647">americanexpress</span></span> 
- <span data-ttu-id="2500b-1648">americano espresso</span><span class="sxs-lookup"><span data-stu-id="2500b-1648">americano espresso</span></span> 
- <span data-ttu-id="2500b-1649">Amex</span><span class="sxs-lookup"><span data-stu-id="2500b-1649">amex</span></span> 
- <span data-ttu-id="2500b-1650">atm card</span><span class="sxs-lookup"><span data-stu-id="2500b-1650">atm card</span></span> 
- <span data-ttu-id="2500b-1651">atm cards</span><span class="sxs-lookup"><span data-stu-id="2500b-1651">atm cards</span></span> 
- <span data-ttu-id="2500b-1652">atm kaart</span><span class="sxs-lookup"><span data-stu-id="2500b-1652">atm kaart</span></span> 
- <span data-ttu-id="2500b-1653">atmcard</span><span class="sxs-lookup"><span data-stu-id="2500b-1653">atmcard</span></span> 
- <span data-ttu-id="2500b-1654">atmcards</span><span class="sxs-lookup"><span data-stu-id="2500b-1654">atmcards</span></span> 
- <span data-ttu-id="2500b-1655">atmkaart</span><span class="sxs-lookup"><span data-stu-id="2500b-1655">atmkaart</span></span> 
- <span data-ttu-id="2500b-1656">atmkaarten</span><span class="sxs-lookup"><span data-stu-id="2500b-1656">atmkaarten</span></span> 
- <span data-ttu-id="2500b-1657">Bancontact</span><span class="sxs-lookup"><span data-stu-id="2500b-1657">bancontact</span></span> 
- <span data-ttu-id="2500b-1658">bank card</span><span class="sxs-lookup"><span data-stu-id="2500b-1658">bank card</span></span> 
- <span data-ttu-id="2500b-1659">bankkaart</span><span class="sxs-lookup"><span data-stu-id="2500b-1659">bankkaart</span></span> 
- <span data-ttu-id="2500b-1660">card holder</span><span class="sxs-lookup"><span data-stu-id="2500b-1660">card holder</span></span> 
- <span data-ttu-id="2500b-1661">card holders</span><span class="sxs-lookup"><span data-stu-id="2500b-1661">card holders</span></span> 
- <span data-ttu-id="2500b-1662">card num</span><span class="sxs-lookup"><span data-stu-id="2500b-1662">card num</span></span> 
- <span data-ttu-id="2500b-1663">card number</span><span class="sxs-lookup"><span data-stu-id="2500b-1663">card number</span></span> 
- <span data-ttu-id="2500b-1664">card numbers</span><span class="sxs-lookup"><span data-stu-id="2500b-1664">card numbers</span></span> 
- <span data-ttu-id="2500b-1665">card type</span><span class="sxs-lookup"><span data-stu-id="2500b-1665">card type</span></span> 
- <span data-ttu-id="2500b-1666">cardano numerico</span><span class="sxs-lookup"><span data-stu-id="2500b-1666">cardano numerico</span></span> 
- <span data-ttu-id="2500b-1667">titolare</span><span class="sxs-lookup"><span data-stu-id="2500b-1667">cardholder</span></span> 
- <span data-ttu-id="2500b-1668">titolari</span><span class="sxs-lookup"><span data-stu-id="2500b-1668">cardholders</span></span> 
- <span data-ttu-id="2500b-1669">cardnumber</span><span class="sxs-lookup"><span data-stu-id="2500b-1669">cardnumber</span></span> 
- <span data-ttu-id="2500b-1670">cardnumbers</span><span class="sxs-lookup"><span data-stu-id="2500b-1670">cardnumbers</span></span> 
- <span data-ttu-id="2500b-1671">carta bianca</span><span class="sxs-lookup"><span data-stu-id="2500b-1671">carta bianca</span></span> 
- <span data-ttu-id="2500b-1672">carta credito</span><span class="sxs-lookup"><span data-stu-id="2500b-1672">carta credito</span></span> 
- <span data-ttu-id="2500b-1673">carta di credito</span><span class="sxs-lookup"><span data-stu-id="2500b-1673">carta di credito</span></span> 
- <span data-ttu-id="2500b-1674">cartao de credito</span><span class="sxs-lookup"><span data-stu-id="2500b-1674">cartao de credito</span></span> 
- <span data-ttu-id="2500b-1675">cartao de crédito</span><span class="sxs-lookup"><span data-stu-id="2500b-1675">cartao de crédito</span></span> 
- <span data-ttu-id="2500b-1676">cartao de debito</span><span class="sxs-lookup"><span data-stu-id="2500b-1676">cartao de debito</span></span> 
- <span data-ttu-id="2500b-1677">○cartao de débito</span><span class="sxs-lookup"><span data-stu-id="2500b-1677">cartao de débito</span></span> 
- <span data-ttu-id="2500b-1678">carte bancaire</span><span class="sxs-lookup"><span data-stu-id="2500b-1678">carte bancaire</span></span> 
- <span data-ttu-id="2500b-1679">carte blanche</span><span class="sxs-lookup"><span data-stu-id="2500b-1679">carte blanche</span></span> 
- <span data-ttu-id="2500b-1680">carte bleue</span><span class="sxs-lookup"><span data-stu-id="2500b-1680">carte bleue</span></span> 
- <span data-ttu-id="2500b-1681">carte de credit</span><span class="sxs-lookup"><span data-stu-id="2500b-1681">carte de credit</span></span> 
- <span data-ttu-id="2500b-1682">carte de crédit</span><span class="sxs-lookup"><span data-stu-id="2500b-1682">carte de crédit</span></span> 
- <span data-ttu-id="2500b-1683">carte di credito</span><span class="sxs-lookup"><span data-stu-id="2500b-1683">carte di credito</span></span> 
- <span data-ttu-id="2500b-1684">carteblanche</span><span class="sxs-lookup"><span data-stu-id="2500b-1684">carteblanche</span></span> 
- <span data-ttu-id="2500b-1685">cartão de credito</span><span class="sxs-lookup"><span data-stu-id="2500b-1685">cartão de credito</span></span> 
- <span data-ttu-id="2500b-1686">cartão de crédito</span><span class="sxs-lookup"><span data-stu-id="2500b-1686">cartão de crédito</span></span> 
- <span data-ttu-id="2500b-1687">cartão de debito</span><span class="sxs-lookup"><span data-stu-id="2500b-1687">cartão de debito</span></span> 
- <span data-ttu-id="2500b-1688">cartão de débito</span><span class="sxs-lookup"><span data-stu-id="2500b-1688">cartão de débito</span></span> 
- <span data-ttu-id="2500b-1689">CB</span><span class="sxs-lookup"><span data-stu-id="2500b-1689">cb</span></span> 
- <span data-ttu-id="2500b-1690">Ccn</span><span class="sxs-lookup"><span data-stu-id="2500b-1690">ccn</span></span> 
- <span data-ttu-id="2500b-1691">check card</span><span class="sxs-lookup"><span data-stu-id="2500b-1691">check card</span></span> 
- <span data-ttu-id="2500b-1692">check cards</span><span class="sxs-lookup"><span data-stu-id="2500b-1692">check cards</span></span> 
- <span data-ttu-id="2500b-1693">checkcard</span><span class="sxs-lookup"><span data-stu-id="2500b-1693">checkcard</span></span>
- <span data-ttu-id="2500b-1694">checkcards</span><span class="sxs-lookup"><span data-stu-id="2500b-1694">checkcards</span></span> 
- <span data-ttu-id="2500b-1695">chequekaart</span><span class="sxs-lookup"><span data-stu-id="2500b-1695">chequekaart</span></span> 
- <span data-ttu-id="2500b-1696">Cirrus</span><span class="sxs-lookup"><span data-stu-id="2500b-1696">cirrus</span></span> 
- <span data-ttu-id="2500b-1697">Cirrus-Edc-Maestro</span><span class="sxs-lookup"><span data-stu-id="2500b-1697">cirrus-edc-maestro</span></span> 
- <span data-ttu-id="2500b-1698">controlekaart</span><span class="sxs-lookup"><span data-stu-id="2500b-1698">controlekaart</span></span> 
- <span data-ttu-id="2500b-1699">controlekaarten</span><span class="sxs-lookup"><span data-stu-id="2500b-1699">controlekaarten</span></span> 
- <span data-ttu-id="2500b-1700">credit card</span><span class="sxs-lookup"><span data-stu-id="2500b-1700">credit card</span></span> 
- <span data-ttu-id="2500b-1701">credit cards</span><span class="sxs-lookup"><span data-stu-id="2500b-1701">credit cards</span></span> 
- <span data-ttu-id="2500b-1702">CreditCard</span><span class="sxs-lookup"><span data-stu-id="2500b-1702">creditcard</span></span> 
- <span data-ttu-id="2500b-1703">creditcards.com</span><span class="sxs-lookup"><span data-stu-id="2500b-1703">creditcards</span></span> 
- <span data-ttu-id="2500b-1704">debetkaart</span><span class="sxs-lookup"><span data-stu-id="2500b-1704">debetkaart</span></span> 
- <span data-ttu-id="2500b-1705">carte</span><span class="sxs-lookup"><span data-stu-id="2500b-1705">debetkaarten</span></span> 
- <span data-ttu-id="2500b-1706">debit card</span><span class="sxs-lookup"><span data-stu-id="2500b-1706">debit card</span></span> 
- <span data-ttu-id="2500b-1707">debit cards</span><span class="sxs-lookup"><span data-stu-id="2500b-1707">debit cards</span></span> 
- <span data-ttu-id="2500b-1708">debitcard</span><span class="sxs-lookup"><span data-stu-id="2500b-1708">debitcard</span></span> 
- <span data-ttu-id="2500b-1709">debitcards</span><span class="sxs-lookup"><span data-stu-id="2500b-1709">debitcards</span></span> 
- <span data-ttu-id="2500b-1710">debito automatico</span><span class="sxs-lookup"><span data-stu-id="2500b-1710">debito automatico</span></span> 
- <span data-ttu-id="2500b-1711">diners club</span><span class="sxs-lookup"><span data-stu-id="2500b-1711">diners club</span></span> 
- <span data-ttu-id="2500b-1712">DinersClub</span><span class="sxs-lookup"><span data-stu-id="2500b-1712">dinersclub</span></span> 
- <span data-ttu-id="2500b-1713">individuare</span><span class="sxs-lookup"><span data-stu-id="2500b-1713">discover</span></span> 
- <span data-ttu-id="2500b-1714">discover card</span><span class="sxs-lookup"><span data-stu-id="2500b-1714">discover card</span></span> 
- <span data-ttu-id="2500b-1715">discover cards</span><span class="sxs-lookup"><span data-stu-id="2500b-1715">discover cards</span></span> 
- <span data-ttu-id="2500b-1716">discovercard</span><span class="sxs-lookup"><span data-stu-id="2500b-1716">discovercard</span></span> 
- <span data-ttu-id="2500b-1717">discovercards</span><span class="sxs-lookup"><span data-stu-id="2500b-1717">discovercards</span></span> 
- <span data-ttu-id="2500b-1718">débito automático</span><span class="sxs-lookup"><span data-stu-id="2500b-1718">débito automático</span></span>
- <span data-ttu-id="2500b-1719">EDC</span><span class="sxs-lookup"><span data-stu-id="2500b-1719">edc</span></span> 
- <span data-ttu-id="2500b-1720">eigentümername</span><span class="sxs-lookup"><span data-stu-id="2500b-1720">eigentümername</span></span> 
- <span data-ttu-id="2500b-1721">european debit card</span><span class="sxs-lookup"><span data-stu-id="2500b-1721">european debit card</span></span> 
- <span data-ttu-id="2500b-1722">hoofdkaart</span><span class="sxs-lookup"><span data-stu-id="2500b-1722">hoofdkaart</span></span> 
- <span data-ttu-id="2500b-1723">hoofdkaarten</span><span class="sxs-lookup"><span data-stu-id="2500b-1723">hoofdkaarten</span></span> 
- <span data-ttu-id="2500b-1724">in viaggio</span><span class="sxs-lookup"><span data-stu-id="2500b-1724">in viaggio</span></span> 
- <span data-ttu-id="2500b-1725">japanese card bureau</span><span class="sxs-lookup"><span data-stu-id="2500b-1725">japanese card bureau</span></span> 
- <span data-ttu-id="2500b-1726">japanse kaartdienst</span><span class="sxs-lookup"><span data-stu-id="2500b-1726">japanse kaartdienst</span></span> 
- <span data-ttu-id="2500b-1727">JCB</span><span class="sxs-lookup"><span data-stu-id="2500b-1727">jcb</span></span> 
- <span data-ttu-id="2500b-1728">kaart</span><span class="sxs-lookup"><span data-stu-id="2500b-1728">kaart</span></span> 
- <span data-ttu-id="2500b-1729">kaart num</span><span class="sxs-lookup"><span data-stu-id="2500b-1729">kaart num</span></span> 
- <span data-ttu-id="2500b-1730">kaartaantal</span><span class="sxs-lookup"><span data-stu-id="2500b-1730">kaartaantal</span></span> 
- <span data-ttu-id="2500b-1731">kaartaantallen</span><span class="sxs-lookup"><span data-stu-id="2500b-1731">kaartaantallen</span></span> 
- <span data-ttu-id="2500b-1732">kaarthouder</span><span class="sxs-lookup"><span data-stu-id="2500b-1732">kaarthouder</span></span> 
- <span data-ttu-id="2500b-1733">kaarthouders</span><span class="sxs-lookup"><span data-stu-id="2500b-1733">kaarthouders</span></span> 
- <span data-ttu-id="2500b-1734">Karte</span><span class="sxs-lookup"><span data-stu-id="2500b-1734">karte</span></span>  
- <span data-ttu-id="2500b-1735">karteninhaber</span><span class="sxs-lookup"><span data-stu-id="2500b-1735">karteninhaber</span></span> 
- <span data-ttu-id="2500b-1736">karteninhabers</span><span class="sxs-lookup"><span data-stu-id="2500b-1736">karteninhabers</span></span>
- <span data-ttu-id="2500b-1737">kartennr</span><span class="sxs-lookup"><span data-stu-id="2500b-1737">kartennr</span></span> 
- <span data-ttu-id="2500b-1738">kartennummer</span><span class="sxs-lookup"><span data-stu-id="2500b-1738">kartennummer</span></span> 
- <span data-ttu-id="2500b-1739">kreditkarte</span><span class="sxs-lookup"><span data-stu-id="2500b-1739">kreditkarte</span></span> 
- <span data-ttu-id="2500b-1740">Kreditkarten-Nummer</span><span class="sxs-lookup"><span data-stu-id="2500b-1740">kreditkarten-nummer</span></span> 
- <span data-ttu-id="2500b-1741">kreditkarteninhaber</span><span class="sxs-lookup"><span data-stu-id="2500b-1741">kreditkarteninhaber</span></span> 
- <span data-ttu-id="2500b-1742">kreditkarteninstitut</span><span class="sxs-lookup"><span data-stu-id="2500b-1742">kreditkarteninstitut</span></span> 
- <span data-ttu-id="2500b-1743">kreditkartennummer</span><span class="sxs-lookup"><span data-stu-id="2500b-1743">kreditkartennummer</span></span> 
- <span data-ttu-id="2500b-1744">kreditkartentyp</span><span class="sxs-lookup"><span data-stu-id="2500b-1744">kreditkartentyp</span></span> 
- <span data-ttu-id="2500b-1745">Maestro</span><span class="sxs-lookup"><span data-stu-id="2500b-1745">maestro</span></span> 
- <span data-ttu-id="2500b-1746">master card</span><span class="sxs-lookup"><span data-stu-id="2500b-1746">master card</span></span> 
- <span data-ttu-id="2500b-1747">master cards</span><span class="sxs-lookup"><span data-stu-id="2500b-1747">master cards</span></span> 
- <span data-ttu-id="2500b-1748">Mastercard</span><span class="sxs-lookup"><span data-stu-id="2500b-1748">mastercard</span></span> 
- <span data-ttu-id="2500b-1749">Mastercard</span><span class="sxs-lookup"><span data-stu-id="2500b-1749">mastercards</span></span> 
- <span data-ttu-id="2500b-1750">MC</span><span class="sxs-lookup"><span data-stu-id="2500b-1750">mc</span></span> 
- <span data-ttu-id="2500b-1751">mister cash</span><span class="sxs-lookup"><span data-stu-id="2500b-1751">mister cash</span></span> 
- <span data-ttu-id="2500b-1752">n carta</span><span class="sxs-lookup"><span data-stu-id="2500b-1752">n carta</span></span> 
- <span data-ttu-id="2500b-1753">carta</span><span class="sxs-lookup"><span data-stu-id="2500b-1753">carta</span></span> 
- <span data-ttu-id="2500b-1754">no de tarjeta</span><span class="sxs-lookup"><span data-stu-id="2500b-1754">no de tarjeta</span></span> 
- <span data-ttu-id="2500b-1755">no do cartao</span><span class="sxs-lookup"><span data-stu-id="2500b-1755">no do cartao</span></span> 
- <span data-ttu-id="2500b-1756">no do cartão</span><span class="sxs-lookup"><span data-stu-id="2500b-1756">no do cartão</span></span> 
- <span data-ttu-id="2500b-1757">No.</span><span class="sxs-lookup"><span data-stu-id="2500b-1757">no.</span></span> <span data-ttu-id="2500b-1758">de tarjeta</span><span class="sxs-lookup"><span data-stu-id="2500b-1758">de tarjeta</span></span> 
- <span data-ttu-id="2500b-1759">No.</span><span class="sxs-lookup"><span data-stu-id="2500b-1759">no.</span></span> <span data-ttu-id="2500b-1760">do cartao</span><span class="sxs-lookup"><span data-stu-id="2500b-1760">do cartao</span></span> 
- <span data-ttu-id="2500b-1761">No.</span><span class="sxs-lookup"><span data-stu-id="2500b-1761">no.</span></span> <span data-ttu-id="2500b-1762">do cartão</span><span class="sxs-lookup"><span data-stu-id="2500b-1762">do cartão</span></span> 
- <span data-ttu-id="2500b-1763">nr carta</span><span class="sxs-lookup"><span data-stu-id="2500b-1763">nr carta</span></span> 
- <span data-ttu-id="2500b-1764">Nr.</span><span class="sxs-lookup"><span data-stu-id="2500b-1764">nr.</span></span> <span data-ttu-id="2500b-1765">carta</span><span class="sxs-lookup"><span data-stu-id="2500b-1765">carta</span></span> 
- <span data-ttu-id="2500b-1766">numeri di scheda</span><span class="sxs-lookup"><span data-stu-id="2500b-1766">numeri di scheda</span></span> 
- <span data-ttu-id="2500b-1767">numero carta</span><span class="sxs-lookup"><span data-stu-id="2500b-1767">numero carta</span></span> 
- <span data-ttu-id="2500b-1768">numero de cartao</span><span class="sxs-lookup"><span data-stu-id="2500b-1768">numero de cartao</span></span> 
- <span data-ttu-id="2500b-1769">numero de carte</span><span class="sxs-lookup"><span data-stu-id="2500b-1769">numero de carte</span></span> 
- <span data-ttu-id="2500b-1770">numero de cartão</span><span class="sxs-lookup"><span data-stu-id="2500b-1770">numero de cartão</span></span> 
- <span data-ttu-id="2500b-1771">numero de tarjeta</span><span class="sxs-lookup"><span data-stu-id="2500b-1771">numero de tarjeta</span></span>
- <span data-ttu-id="2500b-1772">numero della carta</span><span class="sxs-lookup"><span data-stu-id="2500b-1772">numero della carta</span></span> 
- <span data-ttu-id="2500b-1773">numero di carta</span><span class="sxs-lookup"><span data-stu-id="2500b-1773">numero di carta</span></span> 
- <span data-ttu-id="2500b-1774">numero di scheda</span><span class="sxs-lookup"><span data-stu-id="2500b-1774">numero di scheda</span></span> 
- <span data-ttu-id="2500b-1775">numero do cartao</span><span class="sxs-lookup"><span data-stu-id="2500b-1775">numero do cartao</span></span> 
- <span data-ttu-id="2500b-1776">numero do cartão</span><span class="sxs-lookup"><span data-stu-id="2500b-1776">numero do cartão</span></span> 
- <span data-ttu-id="2500b-1777">numéro de carte</span><span class="sxs-lookup"><span data-stu-id="2500b-1777">numéro de carte</span></span> 
- <span data-ttu-id="2500b-1778">nº carta</span><span class="sxs-lookup"><span data-stu-id="2500b-1778">nº carta</span></span> 
- <span data-ttu-id="2500b-1779">nº de carte</span><span class="sxs-lookup"><span data-stu-id="2500b-1779">nº de carte</span></span> 
- <span data-ttu-id="2500b-1780">nº de la carte</span><span class="sxs-lookup"><span data-stu-id="2500b-1780">nº de la carte</span></span> 
- <span data-ttu-id="2500b-1781">nº de tarjeta</span><span class="sxs-lookup"><span data-stu-id="2500b-1781">nº de tarjeta</span></span> 
- <span data-ttu-id="2500b-1782">nº do cartao</span><span class="sxs-lookup"><span data-stu-id="2500b-1782">nº do cartao</span></span> 
- <span data-ttu-id="2500b-1783">nº do cartão</span><span class="sxs-lookup"><span data-stu-id="2500b-1783">nº do cartão</span></span> 
- <span data-ttu-id="2500b-1784">n º.</span><span class="sxs-lookup"><span data-stu-id="2500b-1784">nº.</span></span> <span data-ttu-id="2500b-1785">do cartão</span><span class="sxs-lookup"><span data-stu-id="2500b-1785">do cartão</span></span> 
- <span data-ttu-id="2500b-1786">número de cartao</span><span class="sxs-lookup"><span data-stu-id="2500b-1786">número de cartao</span></span> 
- <span data-ttu-id="2500b-1787">número de cartão</span><span class="sxs-lookup"><span data-stu-id="2500b-1787">número de cartão</span></span> 
- <span data-ttu-id="2500b-1788">número de tarjeta</span><span class="sxs-lookup"><span data-stu-id="2500b-1788">número de tarjeta</span></span> 
- <span data-ttu-id="2500b-1789">número do cartao</span><span class="sxs-lookup"><span data-stu-id="2500b-1789">número do cartao</span></span> 
- <span data-ttu-id="2500b-1790">scheda dell'assegno</span><span class="sxs-lookup"><span data-stu-id="2500b-1790">scheda dell'assegno</span></span> 
- <span data-ttu-id="2500b-1791">scheda dell'atmosfera</span><span class="sxs-lookup"><span data-stu-id="2500b-1791">scheda dell'atmosfera</span></span> 
- <span data-ttu-id="2500b-1792">scheda dell'atmosfera</span><span class="sxs-lookup"><span data-stu-id="2500b-1792">scheda dell'atmosfera</span></span> 
- <span data-ttu-id="2500b-1793">scheda della banca</span><span class="sxs-lookup"><span data-stu-id="2500b-1793">scheda della banca</span></span> 
- <span data-ttu-id="2500b-1794">scheda di controllo</span><span class="sxs-lookup"><span data-stu-id="2500b-1794">scheda di controllo</span></span> 
- <span data-ttu-id="2500b-1795">scheda di debito</span><span class="sxs-lookup"><span data-stu-id="2500b-1795">scheda di debito</span></span> 
- <span data-ttu-id="2500b-1796">scheda matrice</span><span class="sxs-lookup"><span data-stu-id="2500b-1796">scheda matrice</span></span> 
- <span data-ttu-id="2500b-1797">schede dell'atmosfera</span><span class="sxs-lookup"><span data-stu-id="2500b-1797">schede dell'atmosfera</span></span> 
- <span data-ttu-id="2500b-1798">schede di controllo</span><span class="sxs-lookup"><span data-stu-id="2500b-1798">schede di controllo</span></span> 
- <span data-ttu-id="2500b-1799">schede di debito</span><span class="sxs-lookup"><span data-stu-id="2500b-1799">schede di debito</span></span> 
- <span data-ttu-id="2500b-1800">schede matrici</span><span class="sxs-lookup"><span data-stu-id="2500b-1800">schede matrici</span></span> 
- <span data-ttu-id="2500b-1801">scoprono la scheda</span><span class="sxs-lookup"><span data-stu-id="2500b-1801">scoprono la scheda</span></span> 
- <span data-ttu-id="2500b-1802">scoprono le schede</span><span class="sxs-lookup"><span data-stu-id="2500b-1802">scoprono le schede</span></span> 
- <span data-ttu-id="2500b-1803">solo</span><span class="sxs-lookup"><span data-stu-id="2500b-1803">solo</span></span> 
- <span data-ttu-id="2500b-1804">supporti di scheda</span><span class="sxs-lookup"><span data-stu-id="2500b-1804">supporti di scheda</span></span> 
- <span data-ttu-id="2500b-1805">supporto di scheda</span><span class="sxs-lookup"><span data-stu-id="2500b-1805">supporto di scheda</span></span> 
- <span data-ttu-id="2500b-1806">opzione</span><span class="sxs-lookup"><span data-stu-id="2500b-1806">switch</span></span> 
- <span data-ttu-id="2500b-1807">tarjeta atm</span><span class="sxs-lookup"><span data-stu-id="2500b-1807">tarjeta atm</span></span> 
- <span data-ttu-id="2500b-1808">tarjeta credito</span><span class="sxs-lookup"><span data-stu-id="2500b-1808">tarjeta credito</span></span> 
- <span data-ttu-id="2500b-1809">tarjeta de atm</span><span class="sxs-lookup"><span data-stu-id="2500b-1809">tarjeta de atm</span></span> 
- <span data-ttu-id="2500b-1810">tarjeta de credito</span><span class="sxs-lookup"><span data-stu-id="2500b-1810">tarjeta de credito</span></span> 
- <span data-ttu-id="2500b-1811">tarjeta de debito</span><span class="sxs-lookup"><span data-stu-id="2500b-1811">tarjeta de debito</span></span> 
- <span data-ttu-id="2500b-1812">tarjeta debito</span><span class="sxs-lookup"><span data-stu-id="2500b-1812">tarjeta debito</span></span> 
- <span data-ttu-id="2500b-1813">tarjeta no</span><span class="sxs-lookup"><span data-stu-id="2500b-1813">tarjeta no</span></span>
- <span data-ttu-id="2500b-1814">tarjetahabiente</span><span class="sxs-lookup"><span data-stu-id="2500b-1814">tarjetahabiente</span></span> 
- <span data-ttu-id="2500b-1815">tipo della scheda</span><span class="sxs-lookup"><span data-stu-id="2500b-1815">tipo della scheda</span></span> 
- <span data-ttu-id="2500b-1816">ufficio giapponese della</span><span class="sxs-lookup"><span data-stu-id="2500b-1816">ufficio giapponese della</span></span> 
- <span data-ttu-id="2500b-1817">scheda</span><span class="sxs-lookup"><span data-stu-id="2500b-1817">scheda</span></span> 
- <span data-ttu-id="2500b-1818">v pay</span><span class="sxs-lookup"><span data-stu-id="2500b-1818">v pay</span></span> 
- <span data-ttu-id="2500b-1819">v-pay</span><span class="sxs-lookup"><span data-stu-id="2500b-1819">v-pay</span></span> 
- <span data-ttu-id="2500b-1820">esempio</span><span class="sxs-lookup"><span data-stu-id="2500b-1820">visa</span></span> 
- <span data-ttu-id="2500b-1821">visa plus</span><span class="sxs-lookup"><span data-stu-id="2500b-1821">visa plus</span></span> 
- <span data-ttu-id="2500b-1822">visa electron</span><span class="sxs-lookup"><span data-stu-id="2500b-1822">visa electron</span></span> 
- <span data-ttu-id="2500b-1823">visto</span><span class="sxs-lookup"><span data-stu-id="2500b-1823">visto</span></span> 
- <span data-ttu-id="2500b-1824">Visum</span><span class="sxs-lookup"><span data-stu-id="2500b-1824">visum</span></span> 
- <span data-ttu-id="2500b-1825">vpay</span><span class="sxs-lookup"><span data-stu-id="2500b-1825">vpay</span></span>   

#### <a name="keywordcardsecuritytermsdict"></a><span data-ttu-id="2500b-1826">Keyword_card_security_terms_dict</span><span class="sxs-lookup"><span data-stu-id="2500b-1826">Keyword_card_security_terms_dict</span></span>

- <span data-ttu-id="2500b-1827">card identification number</span><span class="sxs-lookup"><span data-stu-id="2500b-1827">card identification number</span></span>
- <span data-ttu-id="2500b-1828">card verification</span><span class="sxs-lookup"><span data-stu-id="2500b-1828">card verification</span></span> 
- <span data-ttu-id="2500b-1829">cardi la verifica</span><span class="sxs-lookup"><span data-stu-id="2500b-1829">cardi la verifica</span></span> 
- <span data-ttu-id="2500b-1830">ID</span><span class="sxs-lookup"><span data-stu-id="2500b-1830">cid</span></span> 
- <span data-ttu-id="2500b-1831">cod seg</span><span class="sxs-lookup"><span data-stu-id="2500b-1831">cod seg</span></span> 
- <span data-ttu-id="2500b-1832">cod seguranca</span><span class="sxs-lookup"><span data-stu-id="2500b-1832">cod seguranca</span></span> 
- <span data-ttu-id="2500b-1833">cod segurança</span><span class="sxs-lookup"><span data-stu-id="2500b-1833">cod segurança</span></span> 
- <span data-ttu-id="2500b-1834">cod sicurezza</span><span class="sxs-lookup"><span data-stu-id="2500b-1834">cod sicurezza</span></span> 
- <span data-ttu-id="2500b-1835">Cod.</span><span class="sxs-lookup"><span data-stu-id="2500b-1835">cod.</span></span> <span data-ttu-id="2500b-1836">SEG</span><span class="sxs-lookup"><span data-stu-id="2500b-1836">seg</span></span> 
- <span data-ttu-id="2500b-1837">Cod.</span><span class="sxs-lookup"><span data-stu-id="2500b-1837">cod.</span></span> <span data-ttu-id="2500b-1838">seguranca</span><span class="sxs-lookup"><span data-stu-id="2500b-1838">seguranca</span></span> 
- <span data-ttu-id="2500b-1839">Cod.</span><span class="sxs-lookup"><span data-stu-id="2500b-1839">cod.</span></span> <span data-ttu-id="2500b-1840">Segurança</span><span class="sxs-lookup"><span data-stu-id="2500b-1840">segurança</span></span> 
- <span data-ttu-id="2500b-1841">Cod.</span><span class="sxs-lookup"><span data-stu-id="2500b-1841">cod.</span></span> <span data-ttu-id="2500b-1842">sicurezza</span><span class="sxs-lookup"><span data-stu-id="2500b-1842">sicurezza</span></span> 
- <span data-ttu-id="2500b-1843">codice di sicurezza</span><span class="sxs-lookup"><span data-stu-id="2500b-1843">codice di sicurezza</span></span> 
- <span data-ttu-id="2500b-1844">codice di verifica</span><span class="sxs-lookup"><span data-stu-id="2500b-1844">codice di verifica</span></span> 
- <span data-ttu-id="2500b-1845">Codigo</span><span class="sxs-lookup"><span data-stu-id="2500b-1845">codigo</span></span> 
- <span data-ttu-id="2500b-1846">codigo de seguranca</span><span class="sxs-lookup"><span data-stu-id="2500b-1846">codigo de seguranca</span></span> 
- <span data-ttu-id="2500b-1847">codigo de segurança</span><span class="sxs-lookup"><span data-stu-id="2500b-1847">codigo de segurança</span></span> 
- <span data-ttu-id="2500b-1848">crittogramma</span><span class="sxs-lookup"><span data-stu-id="2500b-1848">crittogramma</span></span> 
- <span data-ttu-id="2500b-1849">crittogramma</span><span class="sxs-lookup"><span data-stu-id="2500b-1849">cryptogram</span></span> 
- <span data-ttu-id="2500b-1850">cryptogramme</span><span class="sxs-lookup"><span data-stu-id="2500b-1850">cryptogramme</span></span> 
- <span data-ttu-id="2500b-1851">CV2</span><span class="sxs-lookup"><span data-stu-id="2500b-1851">cv2</span></span> 
- <span data-ttu-id="2500b-1852">CVC</span><span class="sxs-lookup"><span data-stu-id="2500b-1852">cvc</span></span> 
- <span data-ttu-id="2500b-1853">CVC2</span><span class="sxs-lookup"><span data-stu-id="2500b-1853">cvc2</span></span> 
- <span data-ttu-id="2500b-1854">CVN</span><span class="sxs-lookup"><span data-stu-id="2500b-1854">cvn</span></span> 
- <span data-ttu-id="2500b-1855">CVV</span><span class="sxs-lookup"><span data-stu-id="2500b-1855">cvv</span></span> 
- <span data-ttu-id="2500b-1856">CVV2</span><span class="sxs-lookup"><span data-stu-id="2500b-1856">cvv2</span></span> 
- <span data-ttu-id="2500b-1857">cód seguranca</span><span class="sxs-lookup"><span data-stu-id="2500b-1857">cód seguranca</span></span> 
- <span data-ttu-id="2500b-1858">cód segurança</span><span class="sxs-lookup"><span data-stu-id="2500b-1858">cód segurança</span></span> 
- <span data-ttu-id="2500b-1859">cód.</span><span class="sxs-lookup"><span data-stu-id="2500b-1859">cód.</span></span> <span data-ttu-id="2500b-1860">seguranca</span><span class="sxs-lookup"><span data-stu-id="2500b-1860">seguranca</span></span> 
- <span data-ttu-id="2500b-1861">cód.</span><span class="sxs-lookup"><span data-stu-id="2500b-1861">cód.</span></span> <span data-ttu-id="2500b-1862">Segurança</span><span class="sxs-lookup"><span data-stu-id="2500b-1862">segurança</span></span> 
- <span data-ttu-id="2500b-1863">Código</span><span class="sxs-lookup"><span data-stu-id="2500b-1863">código</span></span> 
- <span data-ttu-id="2500b-1864">código de seguranca</span><span class="sxs-lookup"><span data-stu-id="2500b-1864">código de seguranca</span></span> 
- <span data-ttu-id="2500b-1865">código de segurança</span><span class="sxs-lookup"><span data-stu-id="2500b-1865">código de segurança</span></span> 
- <span data-ttu-id="2500b-1866">de kaart controle</span><span class="sxs-lookup"><span data-stu-id="2500b-1866">de kaart controle</span></span> 
- <span data-ttu-id="2500b-1867">geeft nr uit</span><span class="sxs-lookup"><span data-stu-id="2500b-1867">geeft nr uit</span></span> 
- <span data-ttu-id="2500b-1868">issue no</span><span class="sxs-lookup"><span data-stu-id="2500b-1868">issue no</span></span> 
- <span data-ttu-id="2500b-1869">issue number</span><span class="sxs-lookup"><span data-stu-id="2500b-1869">issue number</span></span> 
- <span data-ttu-id="2500b-1870">kaartidentificatienummer</span><span class="sxs-lookup"><span data-stu-id="2500b-1870">kaartidentificatienummer</span></span> 
- <span data-ttu-id="2500b-1871">kreditkartenprufnummer</span><span class="sxs-lookup"><span data-stu-id="2500b-1871">kreditkartenprufnummer</span></span> 
- <span data-ttu-id="2500b-1872">kreditkartenprüfnummer</span><span class="sxs-lookup"><span data-stu-id="2500b-1872">kreditkartenprüfnummer</span></span> 
- <span data-ttu-id="2500b-1873">kwestieaantal</span><span class="sxs-lookup"><span data-stu-id="2500b-1873">kwestieaantal</span></span> 
- <span data-ttu-id="2500b-1874">No.</span><span class="sxs-lookup"><span data-stu-id="2500b-1874">no.</span></span> <span data-ttu-id="2500b-1875">dell'edizione</span><span class="sxs-lookup"><span data-stu-id="2500b-1875">dell'edizione</span></span> 
- <span data-ttu-id="2500b-1876">No.</span><span class="sxs-lookup"><span data-stu-id="2500b-1876">no.</span></span> <span data-ttu-id="2500b-1877">di sicurezza</span><span class="sxs-lookup"><span data-stu-id="2500b-1877">di sicurezza</span></span> 
- <span data-ttu-id="2500b-1878">numero de securite</span><span class="sxs-lookup"><span data-stu-id="2500b-1878">numero de securite</span></span> 
- <span data-ttu-id="2500b-1879">numero de verificacao</span><span class="sxs-lookup"><span data-stu-id="2500b-1879">numero de verificacao</span></span> 
- <span data-ttu-id="2500b-1880">numero dell'edizione</span><span class="sxs-lookup"><span data-stu-id="2500b-1880">numero dell'edizione</span></span> 
- <span data-ttu-id="2500b-1881">numero di identificazione della</span><span class="sxs-lookup"><span data-stu-id="2500b-1881">numero di identificazione della</span></span> 
- <span data-ttu-id="2500b-1882">scheda</span><span class="sxs-lookup"><span data-stu-id="2500b-1882">scheda</span></span> 
- <span data-ttu-id="2500b-1883">numero di sicurezza</span><span class="sxs-lookup"><span data-stu-id="2500b-1883">numero di sicurezza</span></span> 
- <span data-ttu-id="2500b-1884">numero van veiligheid</span><span class="sxs-lookup"><span data-stu-id="2500b-1884">numero van veiligheid</span></span> 
- <span data-ttu-id="2500b-1885">numéro de sécurité</span><span class="sxs-lookup"><span data-stu-id="2500b-1885">numéro de sécurité</span></span> 
- <span data-ttu-id="2500b-1886">nº autorizzazione</span><span class="sxs-lookup"><span data-stu-id="2500b-1886">nº autorizzazione</span></span> 
- <span data-ttu-id="2500b-1887">número de verificação</span><span class="sxs-lookup"><span data-stu-id="2500b-1887">número de verificação</span></span> 
- <span data-ttu-id="2500b-1888">perno il blocco</span><span class="sxs-lookup"><span data-stu-id="2500b-1888">perno il blocco</span></span> 
- <span data-ttu-id="2500b-1889">pin block</span><span class="sxs-lookup"><span data-stu-id="2500b-1889">pin block</span></span> 
- <span data-ttu-id="2500b-1890">Prufziffer</span><span class="sxs-lookup"><span data-stu-id="2500b-1890">prufziffer</span></span> 
- <span data-ttu-id="2500b-1891">prüfziffer</span><span class="sxs-lookup"><span data-stu-id="2500b-1891">prüfziffer</span></span> 
- <span data-ttu-id="2500b-1892">security code</span><span class="sxs-lookup"><span data-stu-id="2500b-1892">security code</span></span> 
- <span data-ttu-id="2500b-1893">security no</span><span class="sxs-lookup"><span data-stu-id="2500b-1893">security no</span></span> 
- <span data-ttu-id="2500b-1894">security number</span><span class="sxs-lookup"><span data-stu-id="2500b-1894">security number</span></span> 
- <span data-ttu-id="2500b-1895">sicherheits kode</span><span class="sxs-lookup"><span data-stu-id="2500b-1895">sicherheits kode</span></span> 
- <span data-ttu-id="2500b-1896">sicherheitscode</span><span class="sxs-lookup"><span data-stu-id="2500b-1896">sicherheitscode</span></span> 
- <span data-ttu-id="2500b-1897">sicherheitsnummer</span><span class="sxs-lookup"><span data-stu-id="2500b-1897">sicherheitsnummer</span></span> 
- <span data-ttu-id="2500b-1898">speldblok</span><span class="sxs-lookup"><span data-stu-id="2500b-1898">speldblok</span></span> 
- <span data-ttu-id="2500b-1899">veiligheid nr</span><span class="sxs-lookup"><span data-stu-id="2500b-1899">veiligheid nr</span></span> 
- <span data-ttu-id="2500b-1900">veiligheidsaantal</span><span class="sxs-lookup"><span data-stu-id="2500b-1900">veiligheidsaantal</span></span> 
- <span data-ttu-id="2500b-1901">veiligheidscode</span><span class="sxs-lookup"><span data-stu-id="2500b-1901">veiligheidscode</span></span> 
- <span data-ttu-id="2500b-1902">veiligheidsnummer</span><span class="sxs-lookup"><span data-stu-id="2500b-1902">veiligheidsnummer</span></span> 
- <span data-ttu-id="2500b-1903">verfalldatum</span><span class="sxs-lookup"><span data-stu-id="2500b-1903">verfalldatum</span></span> 

#### <a name="keywordcardexpirationtermsdict"></a><span data-ttu-id="2500b-1904">Keyword_card_expiration_terms_dict</span><span class="sxs-lookup"><span data-stu-id="2500b-1904">Keyword_card_expiration_terms_dict</span></span>

- <span data-ttu-id="2500b-1905">ablauf</span><span class="sxs-lookup"><span data-stu-id="2500b-1905">ablauf</span></span> 
- <span data-ttu-id="2500b-1906">data de expiracao</span><span class="sxs-lookup"><span data-stu-id="2500b-1906">data de expiracao</span></span> 
- <span data-ttu-id="2500b-1907">data de expiração</span><span class="sxs-lookup"><span data-stu-id="2500b-1907">data de expiração</span></span> 
- <span data-ttu-id="2500b-1908">data del exp</span><span class="sxs-lookup"><span data-stu-id="2500b-1908">data del exp</span></span> 
- <span data-ttu-id="2500b-1909">data di exp</span><span class="sxs-lookup"><span data-stu-id="2500b-1909">data di exp</span></span> 
- <span data-ttu-id="2500b-1910">data di scadenza</span><span class="sxs-lookup"><span data-stu-id="2500b-1910">data di scadenza</span></span> 
- <span data-ttu-id="2500b-1911">data em que expira</span><span class="sxs-lookup"><span data-stu-id="2500b-1911">data em que expira</span></span> 
- <span data-ttu-id="2500b-1912">data scad</span><span class="sxs-lookup"><span data-stu-id="2500b-1912">data scad</span></span> 
- <span data-ttu-id="2500b-1913">data scadenza</span><span class="sxs-lookup"><span data-stu-id="2500b-1913">data scadenza</span></span> 
- <span data-ttu-id="2500b-1914">date de validité</span><span class="sxs-lookup"><span data-stu-id="2500b-1914">date de validité</span></span> 
- <span data-ttu-id="2500b-1915">datum afloop</span><span class="sxs-lookup"><span data-stu-id="2500b-1915">datum afloop</span></span> 
- <span data-ttu-id="2500b-1916">datum van exp</span><span class="sxs-lookup"><span data-stu-id="2500b-1916">datum van exp</span></span> 
- <span data-ttu-id="2500b-1917">de afloop</span><span class="sxs-lookup"><span data-stu-id="2500b-1917">de afloop</span></span> 
- <span data-ttu-id="2500b-1918">espira</span><span class="sxs-lookup"><span data-stu-id="2500b-1918">espira</span></span> 
- <span data-ttu-id="2500b-1919">espira</span><span class="sxs-lookup"><span data-stu-id="2500b-1919">espira</span></span> 
- <span data-ttu-id="2500b-1920">exp date</span><span class="sxs-lookup"><span data-stu-id="2500b-1920">exp date</span></span> 
- <span data-ttu-id="2500b-1921">exp datum</span><span class="sxs-lookup"><span data-stu-id="2500b-1921">exp datum</span></span> 
- <span data-ttu-id="2500b-1922">scadenza</span><span class="sxs-lookup"><span data-stu-id="2500b-1922">expiration</span></span> 
- <span data-ttu-id="2500b-1923">scadenza</span><span class="sxs-lookup"><span data-stu-id="2500b-1923">expire</span></span> 
- <span data-ttu-id="2500b-1924">scade</span><span class="sxs-lookup"><span data-stu-id="2500b-1924">expires</span></span> 
- <span data-ttu-id="2500b-1925">scadenza</span><span class="sxs-lookup"><span data-stu-id="2500b-1925">expiry</span></span> 
- <span data-ttu-id="2500b-1926">fecha de expiracion</span><span class="sxs-lookup"><span data-stu-id="2500b-1926">fecha de expiracion</span></span> 
- <span data-ttu-id="2500b-1927">fecha de venc</span><span class="sxs-lookup"><span data-stu-id="2500b-1927">fecha de venc</span></span> 
- <span data-ttu-id="2500b-1928">gultig bis</span><span class="sxs-lookup"><span data-stu-id="2500b-1928">gultig bis</span></span> 
- <span data-ttu-id="2500b-1929">gultigkeitsdatum</span><span class="sxs-lookup"><span data-stu-id="2500b-1929">gultigkeitsdatum</span></span> 
- <span data-ttu-id="2500b-1930">gültig bis</span><span class="sxs-lookup"><span data-stu-id="2500b-1930">gültig bis</span></span> 
- <span data-ttu-id="2500b-1931">gültigkeitsdatum</span><span class="sxs-lookup"><span data-stu-id="2500b-1931">gültigkeitsdatum</span></span> 
- <span data-ttu-id="2500b-1932">la scadenza</span><span class="sxs-lookup"><span data-stu-id="2500b-1932">la scadenza</span></span> 
- <span data-ttu-id="2500b-1933">scadenza</span><span class="sxs-lookup"><span data-stu-id="2500b-1933">scadenza</span></span> 
- <span data-ttu-id="2500b-1934">valable</span><span class="sxs-lookup"><span data-stu-id="2500b-1934">valable</span></span> 
- <span data-ttu-id="2500b-1935">validade</span><span class="sxs-lookup"><span data-stu-id="2500b-1935">validade</span></span> 
- <span data-ttu-id="2500b-1936">valido hasta</span><span class="sxs-lookup"><span data-stu-id="2500b-1936">valido hasta</span></span> 
- <span data-ttu-id="2500b-1937">Valor</span><span class="sxs-lookup"><span data-stu-id="2500b-1937">valor</span></span> 
- <span data-ttu-id="2500b-1938">venc</span><span class="sxs-lookup"><span data-stu-id="2500b-1938">venc</span></span> 
- <span data-ttu-id="2500b-1939">vencimento</span><span class="sxs-lookup"><span data-stu-id="2500b-1939">vencimento</span></span> 
- <span data-ttu-id="2500b-1940">vencimiento</span><span class="sxs-lookup"><span data-stu-id="2500b-1940">vencimiento</span></span> 
- <span data-ttu-id="2500b-1941">verloopt</span><span class="sxs-lookup"><span data-stu-id="2500b-1941">verloopt</span></span> 
- <span data-ttu-id="2500b-1942">vervaldag</span><span class="sxs-lookup"><span data-stu-id="2500b-1942">vervaldag</span></span> 
- <span data-ttu-id="2500b-1943">vervaldatum</span><span class="sxs-lookup"><span data-stu-id="2500b-1943">vervaldatum</span></span> 
- <span data-ttu-id="2500b-1944">VTO</span><span class="sxs-lookup"><span data-stu-id="2500b-1944">vto</span></span> 
- <span data-ttu-id="2500b-1945">válido hasta</span><span class="sxs-lookup"><span data-stu-id="2500b-1945">válido hasta</span></span> 
   
## <a name="eu-drivers-license-number"></a><span data-ttu-id="2500b-1946">Numero della patente di guida dell'Unione europea</span><span class="sxs-lookup"><span data-stu-id="2500b-1946">EU Driver's License Number</span></span>

<span data-ttu-id="2500b-1947">Per ulteriori informazioni, vedere [tipo di informazione sensibile al numero di patente dell'Unione europea](eu-driver-s-license-number.md).</span><span class="sxs-lookup"><span data-stu-id="2500b-1947">To learn more, see [EU Driver's License Number sensitive information type](eu-driver-s-license-number.md).</span></span>
  
## <a name="eu-national-identification-number"></a><span data-ttu-id="2500b-1948">Numero di identificazione nazionale dell'Unione europea</span><span class="sxs-lookup"><span data-stu-id="2500b-1948">EU National Identification Number</span></span>

<span data-ttu-id="2500b-1949">Per ulteriori informazioni, vedere [tipo di informazione riservata del numero di identificazione nazionale dell'Unione europea](eu-national-identification-number.md).</span><span class="sxs-lookup"><span data-stu-id="2500b-1949">To learn more, see [EU National Identification Number sensitive information type](eu-national-identification-number.md).</span></span>
  
## <a name="eu-passport-number"></a><span data-ttu-id="2500b-1950">Numero di passaporto EU</span><span class="sxs-lookup"><span data-stu-id="2500b-1950">EU Passport Number</span></span>

<span data-ttu-id="2500b-1951">Per ulteriori informazioni, vedere [tipo di informazione sensibile al numero di passaporto dell'Unione europea](eu-passport-number.md).</span><span class="sxs-lookup"><span data-stu-id="2500b-1951">To learn more, see [EU Passport Number sensitive information type](eu-passport-number.md).</span></span>
  
## <a name="eu-social-security-number-or-equivalent-id"></a><span data-ttu-id="2500b-1952">Codice di previdenza sociale dell'Unione europea o ID equivalente</span><span class="sxs-lookup"><span data-stu-id="2500b-1952">EU Social Security Number or Equivalent ID</span></span>

<span data-ttu-id="2500b-1953">Per ulteriori informazioni, vedere [codice di previdenza sociale dell'Unione europea o tipo di dati sensibili ID equivalente](eu-social-security-number-or-equivalent-id.md).</span><span class="sxs-lookup"><span data-stu-id="2500b-1953">To learn more, see [EU Social Security Number or Equivalent ID sensitive information type](eu-social-security-number-or-equivalent-id.md).</span></span>
  
## <a name="eu-tax-identification-number"></a><span data-ttu-id="2500b-1954">Numero di identificazione fiscale dell'Unione europea</span><span class="sxs-lookup"><span data-stu-id="2500b-1954">EU Tax Identification Number</span></span>

<span data-ttu-id="2500b-1955">Per ulteriori informazioni, vedere [tipo di informazione riservata del numero di identificazione fiscale dell'Unione europea](eu-tax-identification-number.md).</span><span class="sxs-lookup"><span data-stu-id="2500b-1955">To learn more, see [EU Tax Identification Number sensitive information type](eu-tax-identification-number.md).</span></span>
  
## <a name="finland-national-id"></a><span data-ttu-id="2500b-1956">Finland National ID</span><span class="sxs-lookup"><span data-stu-id="2500b-1956">Finland National ID</span></span>

### <a name="format"></a><span data-ttu-id="2500b-1957">Formato</span><span class="sxs-lookup"><span data-stu-id="2500b-1957">Format</span></span>

<span data-ttu-id="2500b-1958">6 cifre, un carattere di indicazione del secolo, tre cifre più una cifra di controllo</span><span class="sxs-lookup"><span data-stu-id="2500b-1958">Six digits plus a character indicating a century plus three digits plus a check digit</span></span>

### <a name="pattern"></a><span data-ttu-id="2500b-1959">Modello</span><span class="sxs-lookup"><span data-stu-id="2500b-1959">Pattern</span></span>

<span data-ttu-id="2500b-1960">Il modello deve includere tutti gli elementi seguenti:</span><span class="sxs-lookup"><span data-stu-id="2500b-1960">Pattern must include all of the following:</span></span>
- <span data-ttu-id="2500b-1961">Sei cifre nel formato DDMMYY che corrisponde alla data di nascita</span><span class="sxs-lookup"><span data-stu-id="2500b-1961">Six digits in the format format DDMMYY which are a date of birth</span></span> 
- <span data-ttu-id="2500b-1962">Indicatore del secolo ("-", "+" o "a")</span><span class="sxs-lookup"><span data-stu-id="2500b-1962">Century marker (either '-', '+' or 'a')</span></span> 
- <span data-ttu-id="2500b-1963">Codice PIN di 3 cifre</span><span class="sxs-lookup"><span data-stu-id="2500b-1963">Three-digit personal identification number</span></span> 
- <span data-ttu-id="2500b-1964">Una cifra o una lettera (con distinzione tra maiuscole/minuscole) che corrisponde a una cifra di controllo</span><span class="sxs-lookup"><span data-stu-id="2500b-1964">A digit or letter (case insensitive) which is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="2500b-1965">Checksum</span><span class="sxs-lookup"><span data-stu-id="2500b-1965">Checksum</span></span>

<span data-ttu-id="2500b-1966">Sì</span><span class="sxs-lookup"><span data-stu-id="2500b-1966">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="2500b-1967">Definizione</span><span class="sxs-lookup"><span data-stu-id="2500b-1967">Definition</span></span>

<span data-ttu-id="2500b-1968">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="2500b-1968">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2500b-1969">La funzione Func_finnish_national_id restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="2500b-1969">The function Func_finnish_national_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="2500b-1970">Viene trovata una parola chiave da Keyword_finnish_national_id.</span><span class="sxs-lookup"><span data-stu-id="2500b-1970">A keyword from Keyword_finnish_national_id is found.</span></span>
- <span data-ttu-id="2500b-1971">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="2500b-1971">The checksum passes.</span></span>

```
<!-- Finnish National ID-->
<Entity id="338FD995-4CB5-4F87-AD35-79BD1DD926C1" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_finnish_national_id" />
          <Match idRef="Keyword_finnish_national_id" />
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="2500b-1972">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="2500b-1972">Keywords</span></span>

- <span data-ttu-id="2500b-1973">Keyword_finnish_national_id</span><span class="sxs-lookup"><span data-stu-id="2500b-1973">Keyword_finnish_national_id</span></span>
- <span data-ttu-id="2500b-1974">Sosiaaliturvatunnus</span><span class="sxs-lookup"><span data-stu-id="2500b-1974">Sosiaaliturvatunnus</span></span>
- <span data-ttu-id="2500b-1975">SOTU Henkilötunnus HETU</span><span class="sxs-lookup"><span data-stu-id="2500b-1975">SOTU Henkilötunnus HETU</span></span>
- <span data-ttu-id="2500b-1976">Personbeteckning</span><span class="sxs-lookup"><span data-stu-id="2500b-1976">Personbeteckning</span></span>
- <span data-ttu-id="2500b-1977">Personnummer</span><span class="sxs-lookup"><span data-stu-id="2500b-1977">Personnummer</span></span>
   
## <a name="finland-passport-number"></a><span data-ttu-id="2500b-1978">Finlandia - Numero di passaporto</span><span class="sxs-lookup"><span data-stu-id="2500b-1978">Finland Passport Number</span></span>

<span data-ttu-id="2500b-1979">Combinazione di formato di nove lettere e combinazioni di caratteri di nove lettere e cifre: due lettere (senza distinzione tra maiuscole/minuscole) sette cifre checksum nessuna definizione un criterio DLP è 75% sicuro che sia stato rilevato questo tipo di informazioni riservate se, all'interno di un prossimità di 300 caratteri: l'espressione regolare Regex_finland_passport_number trova il contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="2500b-1979">Format Combination of nine letters and digits Pattern Combination of nine letters and digits: Two letters (not case sensitive) Seven digits Checksum No Definition A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The regular expression Regex_finland_passport_number finds content that matches the pattern.</span></span>
<span data-ttu-id="2500b-1980">Viene trovata una parola chiave da Keyword_finland_passport_number.</span><span class="sxs-lookup"><span data-stu-id="2500b-1980">A keyword from Keyword_finland_passport_number is found.</span></span>
<!-- Finland Passport Number -->
<span data-ttu-id="2500b-1981"><Entity id="d1685ac3-1d3a-40f8-8198-32ef5669c7a5" recommendedConfidence="75" patternsProximity="300"> <Pattern confidenceLevel="75"> <IdMatch idRef="Regex_finland_passport_number"/> <Match idRef="Keyword_finland_passport_number"/> </Pattern>
</Entity></span><span class="sxs-lookup"><span data-stu-id="2500b-1981"></span></span>
<span data-ttu-id="2500b-1982">Parole chiave Keyword_finland_passport_number passaporto passi</span><span class="sxs-lookup"><span data-stu-id="2500b-1982">Keywords Keyword_finland_passport_number Passport Passi</span></span>
   
## <a name="france-drivers-license-number"></a><span data-ttu-id="2500b-1983">Francia - Numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="2500b-1983">France Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="2500b-1984">Formato</span><span class="sxs-lookup"><span data-stu-id="2500b-1984">Format</span></span>

<span data-ttu-id="2500b-1985">12 cifre</span><span class="sxs-lookup"><span data-stu-id="2500b-1985">12 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="2500b-1986">Modello</span><span class="sxs-lookup"><span data-stu-id="2500b-1986">Pattern</span></span>

<span data-ttu-id="2500b-1987">12 cifre con convalida per scontare modelli analoghi, ad esempio, quello dei numeri telefonici francesi</span><span class="sxs-lookup"><span data-stu-id="2500b-1987">12 digits with validation to discount similar patterns such as French telephone numbers</span></span>

### <a name="checksum"></a><span data-ttu-id="2500b-1988">Checksum</span><span class="sxs-lookup"><span data-stu-id="2500b-1988">Checksum</span></span>

<span data-ttu-id="2500b-1989">No</span><span class="sxs-lookup"><span data-stu-id="2500b-1989">No</span></span>

### <a name="definition"></a><span data-ttu-id="2500b-1990">Definizione</span><span class="sxs-lookup"><span data-stu-id="2500b-1990">Definition</span></span>

<span data-ttu-id="2500b-1991">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="2500b-1991">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2500b-1992">La funzione Func_french_drivers_license restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="2500b-1992">The function Func_french_drivers_license finds content that matches the pattern.</span></span>
- <span data-ttu-id="2500b-1993">Si verifica almeno una delle situazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="2500b-1993">At least one of the following is true:</span></span>
- <span data-ttu-id="2500b-1994">Viene trovata una parola chiave da Keyword_french_drivers_license.</span><span class="sxs-lookup"><span data-stu-id="2500b-1994">A keyword from Keyword_french_drivers_license is found.</span></span>
- <span data-ttu-id="2500b-1995">La funzione Func_eu_date rileva una data nel formato corretto.</span><span class="sxs-lookup"><span data-stu-id="2500b-1995">The function Func_eu_date finds a date in the right date format.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="2500b-1996">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="2500b-1996">Keywords</span></span>

#### <a name="keywordfrenchdriverslicense"></a><span data-ttu-id="2500b-1997">Keyword_french_drivers_license</span><span class="sxs-lookup"><span data-stu-id="2500b-1997">Keyword_french_drivers_license</span></span>

- <span data-ttu-id="2500b-1998">drivers licence</span><span class="sxs-lookup"><span data-stu-id="2500b-1998">drivers licence</span></span>
- <span data-ttu-id="2500b-1999">drivers license</span><span class="sxs-lookup"><span data-stu-id="2500b-1999">drivers license</span></span>
- <span data-ttu-id="2500b-2000">driving licence</span><span class="sxs-lookup"><span data-stu-id="2500b-2000">driving licence</span></span>
- <span data-ttu-id="2500b-2001">driving license</span><span class="sxs-lookup"><span data-stu-id="2500b-2001">driving license</span></span>
- <span data-ttu-id="2500b-2002">permis de conduire</span><span class="sxs-lookup"><span data-stu-id="2500b-2002">permis de conduire</span></span>
- <span data-ttu-id="2500b-2003">licence number</span><span class="sxs-lookup"><span data-stu-id="2500b-2003">licence number</span></span>
- <span data-ttu-id="2500b-2004">license number</span><span class="sxs-lookup"><span data-stu-id="2500b-2004">license number</span></span>
- <span data-ttu-id="2500b-2005">licence numbers</span><span class="sxs-lookup"><span data-stu-id="2500b-2005">licence numbers</span></span>
- <span data-ttu-id="2500b-2006">license numbers</span><span class="sxs-lookup"><span data-stu-id="2500b-2006">license numbers</span></span>

## <a name="france-national-id-card-cni"></a><span data-ttu-id="2500b-2007">Francia - Carta d'identità nazionale (CNI)</span><span class="sxs-lookup"><span data-stu-id="2500b-2007">France National ID Card (CNI)</span></span>

### <a name="format"></a><span data-ttu-id="2500b-2008">Formato</span><span class="sxs-lookup"><span data-stu-id="2500b-2008">Format</span></span>

<span data-ttu-id="2500b-2009">12 cifre</span><span class="sxs-lookup"><span data-stu-id="2500b-2009">12 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="2500b-2010">Modello</span><span class="sxs-lookup"><span data-stu-id="2500b-2010">Pattern</span></span>

<span data-ttu-id="2500b-2011">12 cifre</span><span class="sxs-lookup"><span data-stu-id="2500b-2011">12 digits</span></span>

### <a name="checksum"></a><span data-ttu-id="2500b-2012">Checksum</span><span class="sxs-lookup"><span data-stu-id="2500b-2012">Checksum</span></span>

<span data-ttu-id="2500b-2013">No</span><span class="sxs-lookup"><span data-stu-id="2500b-2013">No</span></span>

### <a name="definition"></a><span data-ttu-id="2500b-2014">Definizione</span><span class="sxs-lookup"><span data-stu-id="2500b-2014">Definition</span></span>

<span data-ttu-id="2500b-2015">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 65%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="2500b-2015">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2500b-2016">L'espressione regolare Regex_france_cni restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="2500b-2016">The regular expression Regex_france_cni finds content that matches the pattern.</span></span>

```
<!-- France CNI -->
<Entity id="f741ac74-1bc0-4665-b69b-f0c7f927c0c4" patternsProximity="300" recommendedConfidence="65">
  <Pattern confidenceLevel="65">
        <IdMatch idRef="Regex_france_cni" />
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="2500b-2017">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="2500b-2017">Keywords</span></span>

<span data-ttu-id="2500b-2018">Nessuno</span><span class="sxs-lookup"><span data-stu-id="2500b-2018">None</span></span>
   
## <a name="france-passport-number"></a><span data-ttu-id="2500b-2019">Francia - Numero di passaporto</span><span class="sxs-lookup"><span data-stu-id="2500b-2019">France Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="2500b-2020">Formato</span><span class="sxs-lookup"><span data-stu-id="2500b-2020">Format</span></span>

<span data-ttu-id="2500b-2021">Nove cifre e lettere</span><span class="sxs-lookup"><span data-stu-id="2500b-2021">Nine digits and letters</span></span>

### <a name="pattern"></a><span data-ttu-id="2500b-2022">Modello</span><span class="sxs-lookup"><span data-stu-id="2500b-2022">Pattern</span></span>

<span data-ttu-id="2500b-2023">Nove cifre e lettere:</span><span class="sxs-lookup"><span data-stu-id="2500b-2023">Nine digits and letters:</span></span>
- <span data-ttu-id="2500b-2024">Due cifre</span><span class="sxs-lookup"><span data-stu-id="2500b-2024">Two digits</span></span> 
- <span data-ttu-id="2500b-2025">Due lettere (senza distinzione tra maiuscole/minuscole)</span><span class="sxs-lookup"><span data-stu-id="2500b-2025">Two letters (not case sensitive)</span></span> 
- <span data-ttu-id="2500b-2026">Cinque cifre</span><span class="sxs-lookup"><span data-stu-id="2500b-2026">Five digits</span></span>

### <a name="checksum"></a><span data-ttu-id="2500b-2027">Checksum</span><span class="sxs-lookup"><span data-stu-id="2500b-2027">Checksum</span></span>

<span data-ttu-id="2500b-2028">No</span><span class="sxs-lookup"><span data-stu-id="2500b-2028">No</span></span>

### <a name="definition"></a><span data-ttu-id="2500b-2029">Definizione</span><span class="sxs-lookup"><span data-stu-id="2500b-2029">Definition</span></span>

<span data-ttu-id="2500b-2030">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="2500b-2030">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2500b-2031">La funzione Func_fr_passport restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="2500b-2031">The function Func_fr_passport finds content that matches the pattern.</span></span>
- <span data-ttu-id="2500b-2032">Viene trovata una parola chiave da Keyword_passport.</span><span class="sxs-lookup"><span data-stu-id="2500b-2032">A keyword from Keyword_passport is found.</span></span>

```
<!-- France Passport Number -->
<Entity id="3008b884-8c8c-4cd8-a289-99f34fc7ff5d" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_fr_passport" />
        <Match idRef="Keyword_passport" />
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="2500b-2033">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="2500b-2033">Keywords</span></span>

#### <a name="keywordpassport"></a><span data-ttu-id="2500b-2034">Keyword_passport</span><span class="sxs-lookup"><span data-stu-id="2500b-2034">Keyword_passport</span></span>

- <span data-ttu-id="2500b-2035">Passport Number</span><span class="sxs-lookup"><span data-stu-id="2500b-2035">Passport Number</span></span>
- <span data-ttu-id="2500b-2036">Passport No</span><span class="sxs-lookup"><span data-stu-id="2500b-2036">Passport No</span></span>
- <span data-ttu-id="2500b-2037">Passport#</span><span class="sxs-lookup"><span data-stu-id="2500b-2037">Passport #</span></span>
- <span data-ttu-id="2500b-2038">Passaporto</span><span class="sxs-lookup"><span data-stu-id="2500b-2038">Passport#</span></span>
- <span data-ttu-id="2500b-2039">PassportID</span><span class="sxs-lookup"><span data-stu-id="2500b-2039">PassportID</span></span>
- <span data-ttu-id="2500b-2040">Passportno</span><span class="sxs-lookup"><span data-stu-id="2500b-2040">Passportno</span></span>
- <span data-ttu-id="2500b-2041">passportnumber</span><span class="sxs-lookup"><span data-stu-id="2500b-2041">passportnumber</span></span>
- <span data-ttu-id="2500b-2042">パスポート</span><span class="sxs-lookup"><span data-stu-id="2500b-2042">パスポート</span></span>
- <span data-ttu-id="2500b-2043">パスポート番号</span><span class="sxs-lookup"><span data-stu-id="2500b-2043">パスポート番号</span></span>
- <span data-ttu-id="2500b-2044">パスポートのNum</span><span class="sxs-lookup"><span data-stu-id="2500b-2044">パスポートのNum</span></span>
- <span data-ttu-id="2500b-2045">パスポート ＃</span><span class="sxs-lookup"><span data-stu-id="2500b-2045">パスポート ＃</span></span> 
- <span data-ttu-id="2500b-2046">Numéro de passeport</span><span class="sxs-lookup"><span data-stu-id="2500b-2046">Numéro de passeport</span></span>
- <span data-ttu-id="2500b-2047">Passeport n °</span><span class="sxs-lookup"><span data-stu-id="2500b-2047">Passeport n °</span></span>
- <span data-ttu-id="2500b-2048">Passeport Non</span><span class="sxs-lookup"><span data-stu-id="2500b-2048">Passeport Non</span></span>
- <span data-ttu-id="2500b-2049">Passeport#</span><span class="sxs-lookup"><span data-stu-id="2500b-2049">Passeport #</span></span>
- <span data-ttu-id="2500b-2050">Passeport</span><span class="sxs-lookup"><span data-stu-id="2500b-2050">Passeport#</span></span>
- <span data-ttu-id="2500b-2051">PasseportNon</span><span class="sxs-lookup"><span data-stu-id="2500b-2051">PasseportNon</span></span>
- <span data-ttu-id="2500b-2052">Passeportn °</span><span class="sxs-lookup"><span data-stu-id="2500b-2052">Passeportn °</span></span>

      
## <a name="france-social-security-number-insee"></a><span data-ttu-id="2500b-2053">Francia - Numero di previdenza sociale (INSEE)</span><span class="sxs-lookup"><span data-stu-id="2500b-2053">France Social Security Number (INSEE)</span></span>

### <a name="format"></a><span data-ttu-id="2500b-2054">Formato</span><span class="sxs-lookup"><span data-stu-id="2500b-2054">Format</span></span>

<span data-ttu-id="2500b-2055">15 cifre</span><span class="sxs-lookup"><span data-stu-id="2500b-2055">15 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="2500b-2056">Modello</span><span class="sxs-lookup"><span data-stu-id="2500b-2056">Pattern</span></span>

<span data-ttu-id="2500b-2057">Deve corrispondere a uno di questi due modelli:</span><span class="sxs-lookup"><span data-stu-id="2500b-2057">Must match one of two patterns:</span></span>
- <span data-ttu-id="2500b-2058">13 cifre seguite da uno spazio seguito da due cifre</span><span class="sxs-lookup"><span data-stu-id="2500b-2058">13 digits followed by a space followed by two digits</span></span><br/>
<span data-ttu-id="2500b-2059">oppure</span><span class="sxs-lookup"><span data-stu-id="2500b-2059">or</span></span>
- <span data-ttu-id="2500b-2060">15 cifre consecutive</span><span class="sxs-lookup"><span data-stu-id="2500b-2060">15 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="2500b-2061">Checksum</span><span class="sxs-lookup"><span data-stu-id="2500b-2061">Checksum</span></span>

<span data-ttu-id="2500b-2062">Sì</span><span class="sxs-lookup"><span data-stu-id="2500b-2062">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="2500b-2063">Definizione</span><span class="sxs-lookup"><span data-stu-id="2500b-2063">Definition</span></span>

<span data-ttu-id="2500b-2064">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 95%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="2500b-2064">A DLP policy is 95% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2500b-2065">La funzione Func_french_insee o Func_fr_insee trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="2500b-2065">The function Func_french_insee or Func_fr_insee finds content that matches the pattern.</span></span>
- <span data-ttu-id="2500b-2066">Viene trovata una parola chiave da Keyword_fr_insee.</span><span class="sxs-lookup"><span data-stu-id="2500b-2066">A keyword from Keyword_fr_insee is found.</span></span>
- <span data-ttu-id="2500b-2067">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="2500b-2067">The checksum passes.</span></span>

<span data-ttu-id="2500b-2068">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="2500b-2068">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2500b-2069">La funzione Func_french_insee o Func_fr_insee trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="2500b-2069">The function Func_french_insee or Func_fr_insee finds content that matches the pattern.</span></span>
- <span data-ttu-id="2500b-2070">Non vengono trovate parole chiave da Keyword_fr_insee.</span><span class="sxs-lookup"><span data-stu-id="2500b-2070">No keyword from Keyword_fr_insee is found.</span></span>
- <span data-ttu-id="2500b-2071">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="2500b-2071">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="2500b-2072">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="2500b-2072">Keywords</span></span>

#### <a name="keywordfrinsee"></a><span data-ttu-id="2500b-2073">Keyword_fr_insee</span><span class="sxs-lookup"><span data-stu-id="2500b-2073">Keyword_fr_insee</span></span>

- <span data-ttu-id="2500b-2074">INSEE</span><span class="sxs-lookup"><span data-stu-id="2500b-2074">insee</span></span>
- <span data-ttu-id="2500b-2075">securité sociale</span><span class="sxs-lookup"><span data-stu-id="2500b-2075">securité sociale</span></span>
- <span data-ttu-id="2500b-2076">securite sociale</span><span class="sxs-lookup"><span data-stu-id="2500b-2076">securite sociale</span></span>
- <span data-ttu-id="2500b-2077">national id</span><span class="sxs-lookup"><span data-stu-id="2500b-2077">national id</span></span>
- <span data-ttu-id="2500b-2078">national identification</span><span class="sxs-lookup"><span data-stu-id="2500b-2078">national identification</span></span>
- <span data-ttu-id="2500b-2079">numéro d'identité</span><span class="sxs-lookup"><span data-stu-id="2500b-2079">numéro d'identité</span></span>
- <span data-ttu-id="2500b-2080">no d'identité</span><span class="sxs-lookup"><span data-stu-id="2500b-2080">no d'identité</span></span>
- <span data-ttu-id="2500b-2081">No.</span><span class="sxs-lookup"><span data-stu-id="2500b-2081">no.</span></span> <span data-ttu-id="2500b-2082">d'identité</span><span class="sxs-lookup"><span data-stu-id="2500b-2082">d'identité</span></span>
- <span data-ttu-id="2500b-2083">numero d'identite</span><span class="sxs-lookup"><span data-stu-id="2500b-2083">numero d'identite</span></span>
- <span data-ttu-id="2500b-2084">no d'identite</span><span class="sxs-lookup"><span data-stu-id="2500b-2084">no d'identite</span></span>
- <span data-ttu-id="2500b-2085">No.</span><span class="sxs-lookup"><span data-stu-id="2500b-2085">no.</span></span> <span data-ttu-id="2500b-2086">d'identite</span><span class="sxs-lookup"><span data-stu-id="2500b-2086">d'identite</span></span>
- <span data-ttu-id="2500b-2087">social security number</span><span class="sxs-lookup"><span data-stu-id="2500b-2087">social security number</span></span>
- <span data-ttu-id="2500b-2088">social security code</span><span class="sxs-lookup"><span data-stu-id="2500b-2088">social security code</span></span>
- <span data-ttu-id="2500b-2089">social insurance number</span><span class="sxs-lookup"><span data-stu-id="2500b-2089">social insurance number</span></span>
- <span data-ttu-id="2500b-2090">le numéro d'identification nationale</span><span class="sxs-lookup"><span data-stu-id="2500b-2090">le numéro d'identification nationale</span></span>
- <span data-ttu-id="2500b-2091">d'identité nationale</span><span class="sxs-lookup"><span data-stu-id="2500b-2091">d'identité nationale</span></span>
- <span data-ttu-id="2500b-2092">numéro de sécurité sociale</span><span class="sxs-lookup"><span data-stu-id="2500b-2092">numéro de sécurité sociale</span></span>
- <span data-ttu-id="2500b-2093">le code de la sécurité sociale</span><span class="sxs-lookup"><span data-stu-id="2500b-2093">le code de la sécurité sociale</span></span>
- <span data-ttu-id="2500b-2094">numéro d'assurance sociale</span><span class="sxs-lookup"><span data-stu-id="2500b-2094">numéro d'assurance sociale</span></span>
- <span data-ttu-id="2500b-2095">numéro de sécu</span><span class="sxs-lookup"><span data-stu-id="2500b-2095">numéro de sécu</span></span>
- <span data-ttu-id="2500b-2096">code sécu</span><span class="sxs-lookup"><span data-stu-id="2500b-2096">code sécu</span></span> 
   
## <a name="german-drivers-license-number"></a><span data-ttu-id="2500b-2097">Germania - Numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="2500b-2097">German Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="2500b-2098">Formato</span><span class="sxs-lookup"><span data-stu-id="2500b-2098">Format</span></span>

<span data-ttu-id="2500b-2099">Combinazione di 11 cifre e lettere</span><span class="sxs-lookup"><span data-stu-id="2500b-2099">Combination of 11 digits and letters</span></span>

### <a name="pattern"></a><span data-ttu-id="2500b-2100">Modello</span><span class="sxs-lookup"><span data-stu-id="2500b-2100">Pattern</span></span>

<span data-ttu-id="2500b-2101">11 cifre e lettere (senza distinzione tra maiuscole/minuscole):</span><span class="sxs-lookup"><span data-stu-id="2500b-2101">11 digits and letters (not case sensitive):</span></span>
- <span data-ttu-id="2500b-2102">Una cifra o una lettera</span><span class="sxs-lookup"><span data-stu-id="2500b-2102">A digit or letter</span></span> 
- <span data-ttu-id="2500b-2103">Due cifre</span><span class="sxs-lookup"><span data-stu-id="2500b-2103">Two digits</span></span> 
- <span data-ttu-id="2500b-2104">Sei cifre o lettere</span><span class="sxs-lookup"><span data-stu-id="2500b-2104">Six digits or letters</span></span> 
- <span data-ttu-id="2500b-2105">Una cifra</span><span class="sxs-lookup"><span data-stu-id="2500b-2105">A digit</span></span> 
- <span data-ttu-id="2500b-2106">Una cifra o una lettera</span><span class="sxs-lookup"><span data-stu-id="2500b-2106">A digit or letter</span></span>

### <a name="checksum"></a><span data-ttu-id="2500b-2107">Checksum</span><span class="sxs-lookup"><span data-stu-id="2500b-2107">Checksum</span></span>

<span data-ttu-id="2500b-2108">Sì</span><span class="sxs-lookup"><span data-stu-id="2500b-2108">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="2500b-2109">Definizione</span><span class="sxs-lookup"><span data-stu-id="2500b-2109">Definition</span></span>

<span data-ttu-id="2500b-2110">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="2500b-2110">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2500b-2111">La funzione Func_german_drivers_license restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="2500b-2111">The function Func_german_drivers_license finds content that matches the pattern.</span></span>
- <span data-ttu-id="2500b-2112">Si verifica almeno una delle situazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="2500b-2112">At least one of the following is true:</span></span>
    - <span data-ttu-id="2500b-2113">Viene trovata una parola chiave da Keyword_german_drivers_license_number.</span><span class="sxs-lookup"><span data-stu-id="2500b-2113">A keyword from Keyword_german_drivers_license_number is found.</span></span>
    - <span data-ttu-id="2500b-2114">Viene trovata una parola chiave da Keyword_german_drivers_license_collaborative.</span><span class="sxs-lookup"><span data-stu-id="2500b-2114">A keyword from Keyword_german_drivers_license_collaborative is found.</span></span>
    - <span data-ttu-id="2500b-2115">Viene trovata una parola chiave da Keyword_german_drivers_license.</span><span class="sxs-lookup"><span data-stu-id="2500b-2115">A keyword from Keyword_german_drivers_license is found.</span></span>
- <span data-ttu-id="2500b-2116">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="2500b-2116">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="2500b-2117">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="2500b-2117">Keywords</span></span>

#### <a name="keywordgermandriverslicensenumber"></a><span data-ttu-id="2500b-2118">Keyword_german_drivers_license_number</span><span class="sxs-lookup"><span data-stu-id="2500b-2118">Keyword_german_drivers_license_number</span></span>

- <span data-ttu-id="2500b-2119">Führerschein</span><span class="sxs-lookup"><span data-stu-id="2500b-2119">Führerschein</span></span>
- <span data-ttu-id="2500b-2120">Fuhrerschein</span><span class="sxs-lookup"><span data-stu-id="2500b-2120">Fuhrerschein</span></span>
- <span data-ttu-id="2500b-2121">Fuehrerschein</span><span class="sxs-lookup"><span data-stu-id="2500b-2121">Fuehrerschein</span></span>
- <span data-ttu-id="2500b-2122">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="2500b-2122">Führerscheinnummer</span></span>
- <span data-ttu-id="2500b-2123">Fuhrerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="2500b-2123">Fuhrerscheinnummer</span></span>
- <span data-ttu-id="2500b-2124">Fuehrerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="2500b-2124">Fuehrerscheinnummer</span></span>
- <span data-ttu-id="2500b-2125">Führerschein-</span><span class="sxs-lookup"><span data-stu-id="2500b-2125">Führerschein-</span></span> 
- <span data-ttu-id="2500b-2126">Fuhrerschein-</span><span class="sxs-lookup"><span data-stu-id="2500b-2126">Fuhrerschein-</span></span> 
- <span data-ttu-id="2500b-2127">Fuehrerschein-</span><span class="sxs-lookup"><span data-stu-id="2500b-2127">Fuehrerschein-</span></span> 
- <span data-ttu-id="2500b-2128">FührerscheinnummerNr</span><span class="sxs-lookup"><span data-stu-id="2500b-2128">FührerscheinnummerNr</span></span>
- <span data-ttu-id="2500b-2129">FuhrerscheinnummerNr</span><span class="sxs-lookup"><span data-stu-id="2500b-2129">FuhrerscheinnummerNr</span></span>
- <span data-ttu-id="2500b-2130">FuehrerscheinnummerNr</span><span class="sxs-lookup"><span data-stu-id="2500b-2130">FuehrerscheinnummerNr</span></span>
- <span data-ttu-id="2500b-2131">FührerscheinnummerKlasse</span><span class="sxs-lookup"><span data-stu-id="2500b-2131">FührerscheinnummerKlasse</span></span>
- <span data-ttu-id="2500b-2132">FuhrerscheinnummerKlasse</span><span class="sxs-lookup"><span data-stu-id="2500b-2132">FuhrerscheinnummerKlasse</span></span>
- <span data-ttu-id="2500b-2133">FuehrerscheinnummerKlasse</span><span class="sxs-lookup"><span data-stu-id="2500b-2133">FuehrerscheinnummerKlasse</span></span>
- <span data-ttu-id="2500b-2134">Führerschein- Nr</span><span class="sxs-lookup"><span data-stu-id="2500b-2134">Führerschein- Nr</span></span>
- <span data-ttu-id="2500b-2135">Fuhrerschein- Nr</span><span class="sxs-lookup"><span data-stu-id="2500b-2135">Fuhrerschein- Nr</span></span>
- <span data-ttu-id="2500b-2136">Fuehrerschein- Nr</span><span class="sxs-lookup"><span data-stu-id="2500b-2136">Fuehrerschein- Nr</span></span> 
- <span data-ttu-id="2500b-2137">Führerschein- Klasse</span><span class="sxs-lookup"><span data-stu-id="2500b-2137">Führerschein- Klasse</span></span> 
- <span data-ttu-id="2500b-2138">Fuhrerschein- Klasse</span><span class="sxs-lookup"><span data-stu-id="2500b-2138">Fuhrerschein- Klasse</span></span> 
- <span data-ttu-id="2500b-2139">Fuehrerschein- Klasse</span><span class="sxs-lookup"><span data-stu-id="2500b-2139">Fuehrerschein- Klasse</span></span>
- <span data-ttu-id="2500b-2140">FührerscheinnummerNr</span><span class="sxs-lookup"><span data-stu-id="2500b-2140">FührerscheinnummerNr</span></span> 
- <span data-ttu-id="2500b-2141">FuhrerscheinnummerNr</span><span class="sxs-lookup"><span data-stu-id="2500b-2141">FuhrerscheinnummerNr</span></span> 
- <span data-ttu-id="2500b-2142">FuehrerscheinnummerNr</span><span class="sxs-lookup"><span data-stu-id="2500b-2142">FuehrerscheinnummerNr</span></span> 
- <span data-ttu-id="2500b-2143">FührerscheinnummerKlasse</span><span class="sxs-lookup"><span data-stu-id="2500b-2143">FührerscheinnummerKlasse</span></span> 
- <span data-ttu-id="2500b-2144">FuhrerscheinnummerKlasse</span><span class="sxs-lookup"><span data-stu-id="2500b-2144">FuhrerscheinnummerKlasse</span></span> 
- <span data-ttu-id="2500b-2145">FuehrerscheinnummerKlasse</span><span class="sxs-lookup"><span data-stu-id="2500b-2145">FuehrerscheinnummerKlasse</span></span> 
- <span data-ttu-id="2500b-2146">Führerschein- Nr</span><span class="sxs-lookup"><span data-stu-id="2500b-2146">Führerschein- Nr</span></span> 
- <span data-ttu-id="2500b-2147">Fuhrerschein- Nr</span><span class="sxs-lookup"><span data-stu-id="2500b-2147">Fuhrerschein- Nr</span></span> 
- <span data-ttu-id="2500b-2148">Fuehrerschein- Nr</span><span class="sxs-lookup"><span data-stu-id="2500b-2148">Fuehrerschein- Nr</span></span> 
- <span data-ttu-id="2500b-2149">Führerschein- Klasse</span><span class="sxs-lookup"><span data-stu-id="2500b-2149">Führerschein- Klasse</span></span> 
- <span data-ttu-id="2500b-2150">Fuhrerschein- Klasse</span><span class="sxs-lookup"><span data-stu-id="2500b-2150">Fuhrerschein- Klasse</span></span> 
- <span data-ttu-id="2500b-2151">Fuehrerschein- Klasse</span><span class="sxs-lookup"><span data-stu-id="2500b-2151">Fuehrerschein- Klasse</span></span> 
- <span data-ttu-id="2500b-2152">DL</span><span class="sxs-lookup"><span data-stu-id="2500b-2152">DL</span></span> 
- <span data-ttu-id="2500b-2153">DLS</span><span class="sxs-lookup"><span data-stu-id="2500b-2153">DLS</span></span>
- <span data-ttu-id="2500b-2154">Driv Lic</span><span class="sxs-lookup"><span data-stu-id="2500b-2154">Driv Lic</span></span> 
- <span data-ttu-id="2500b-2155">Driv Licen</span><span class="sxs-lookup"><span data-stu-id="2500b-2155">Driv Licen</span></span> 
- <span data-ttu-id="2500b-2156">Driv License</span><span class="sxs-lookup"><span data-stu-id="2500b-2156">Driv License</span></span>
- <span data-ttu-id="2500b-2157">Driv Licenses</span><span class="sxs-lookup"><span data-stu-id="2500b-2157">Driv Licenses</span></span> 
- <span data-ttu-id="2500b-2158">Driv Licence</span><span class="sxs-lookup"><span data-stu-id="2500b-2158">Driv Licence</span></span> 
- <span data-ttu-id="2500b-2159">Driv Licences</span><span class="sxs-lookup"><span data-stu-id="2500b-2159">Driv Licences</span></span> 
- <span data-ttu-id="2500b-2160">Driv Lic</span><span class="sxs-lookup"><span data-stu-id="2500b-2160">Driv Lic</span></span> 
- <span data-ttu-id="2500b-2161">Driver Licen</span><span class="sxs-lookup"><span data-stu-id="2500b-2161">Driver Licen</span></span> 
- <span data-ttu-id="2500b-2162">Driver License</span><span class="sxs-lookup"><span data-stu-id="2500b-2162">Driver License</span></span> 
- <span data-ttu-id="2500b-2163">Driver Licenses</span><span class="sxs-lookup"><span data-stu-id="2500b-2163">Driver Licenses</span></span> 
- <span data-ttu-id="2500b-2164">Driver Licence</span><span class="sxs-lookup"><span data-stu-id="2500b-2164">Driver Licence</span></span> 
- <span data-ttu-id="2500b-2165">Driver Licences</span><span class="sxs-lookup"><span data-stu-id="2500b-2165">Driver Licences</span></span> 
- <span data-ttu-id="2500b-2166">Drivers Lic</span><span class="sxs-lookup"><span data-stu-id="2500b-2166">Drivers Lic</span></span> 
- <span data-ttu-id="2500b-2167">Drivers Licen</span><span class="sxs-lookup"><span data-stu-id="2500b-2167">Drivers Licen</span></span> 
- <span data-ttu-id="2500b-2168">Drivers License</span><span class="sxs-lookup"><span data-stu-id="2500b-2168">Drivers License</span></span> 
- <span data-ttu-id="2500b-2169">Drivers Licenses</span><span class="sxs-lookup"><span data-stu-id="2500b-2169">Drivers Licenses</span></span> 
- <span data-ttu-id="2500b-2170">Drivers Licence</span><span class="sxs-lookup"><span data-stu-id="2500b-2170">Drivers Licence</span></span> 
- <span data-ttu-id="2500b-2171">Drivers Licences</span><span class="sxs-lookup"><span data-stu-id="2500b-2171">Drivers Licences</span></span> 
- <span data-ttu-id="2500b-2172">Driver's Lic</span><span class="sxs-lookup"><span data-stu-id="2500b-2172">Driver's Lic</span></span> 
- <span data-ttu-id="2500b-2173">Driver's Licen</span><span class="sxs-lookup"><span data-stu-id="2500b-2173">Driver's Licen</span></span> 
- <span data-ttu-id="2500b-2174">Driver's License</span><span class="sxs-lookup"><span data-stu-id="2500b-2174">Driver's License</span></span> 
- <span data-ttu-id="2500b-2175">Driver's Licenses</span><span class="sxs-lookup"><span data-stu-id="2500b-2175">Driver's Licenses</span></span> 
- <span data-ttu-id="2500b-2176">Driver's Licence</span><span class="sxs-lookup"><span data-stu-id="2500b-2176">Driver's Licence</span></span> 
- <span data-ttu-id="2500b-2177">Driver's Licences</span><span class="sxs-lookup"><span data-stu-id="2500b-2177">Driver's Licences</span></span> 
- <span data-ttu-id="2500b-2178">Driving Lic</span><span class="sxs-lookup"><span data-stu-id="2500b-2178">Driving Lic</span></span> 
- <span data-ttu-id="2500b-2179">Driving Licen</span><span class="sxs-lookup"><span data-stu-id="2500b-2179">Driving Licen</span></span> 
- <span data-ttu-id="2500b-2180">Driving License</span><span class="sxs-lookup"><span data-stu-id="2500b-2180">Driving License</span></span> 
- <span data-ttu-id="2500b-2181">Driving Licenses</span><span class="sxs-lookup"><span data-stu-id="2500b-2181">Driving Licenses</span></span> 
- <span data-ttu-id="2500b-2182">Driving Licence</span><span class="sxs-lookup"><span data-stu-id="2500b-2182">Driving Licence</span></span> 
- <span data-ttu-id="2500b-2183">Driving Licences</span><span class="sxs-lookup"><span data-stu-id="2500b-2183">Driving Licences</span></span>

#### <a name="keywordgermandriverslicensecollaborative"></a><span data-ttu-id="2500b-2184">Keyword_german_drivers_license_collaborative</span><span class="sxs-lookup"><span data-stu-id="2500b-2184">Keyword_german_drivers_license_collaborative</span></span>

- <span data-ttu-id="2500b-2185">Nr-Führerschein</span><span class="sxs-lookup"><span data-stu-id="2500b-2185">Nr-Führerschein</span></span> 
- <span data-ttu-id="2500b-2186">Nr-Fuhrerschein</span><span class="sxs-lookup"><span data-stu-id="2500b-2186">Nr-Fuhrerschein</span></span> 
- <span data-ttu-id="2500b-2187">Nr-Fuehrerschein</span><span class="sxs-lookup"><span data-stu-id="2500b-2187">Nr-Fuehrerschein</span></span> 
- <span data-ttu-id="2500b-2188">No-Führerschein</span><span class="sxs-lookup"><span data-stu-id="2500b-2188">No-Führerschein</span></span> 
- <span data-ttu-id="2500b-2189">No-Fuhrerschein</span><span class="sxs-lookup"><span data-stu-id="2500b-2189">No-Fuhrerschein</span></span> 
- <span data-ttu-id="2500b-2190">No-Fuehrerschein</span><span class="sxs-lookup"><span data-stu-id="2500b-2190">No-Fuehrerschein</span></span> 
- <span data-ttu-id="2500b-2191">N-Führerschein</span><span class="sxs-lookup"><span data-stu-id="2500b-2191">N-Führerschein</span></span> 
- <span data-ttu-id="2500b-2192">N-Fuhrerschein</span><span class="sxs-lookup"><span data-stu-id="2500b-2192">N-Fuhrerschein</span></span> 
- <span data-ttu-id="2500b-2193">N-Fuehrerschein</span><span class="sxs-lookup"><span data-stu-id="2500b-2193">N-Fuehrerschein</span></span>
- <span data-ttu-id="2500b-2194">Nr-Führerschein</span><span class="sxs-lookup"><span data-stu-id="2500b-2194">Nr-Führerschein</span></span> 
- <span data-ttu-id="2500b-2195">Nr-Fuhrerschein</span><span class="sxs-lookup"><span data-stu-id="2500b-2195">Nr-Fuhrerschein</span></span> 
- <span data-ttu-id="2500b-2196">Nr-Fuehrerschein</span><span class="sxs-lookup"><span data-stu-id="2500b-2196">Nr-Fuehrerschein</span></span> 
- <span data-ttu-id="2500b-2197">No-Führerschein</span><span class="sxs-lookup"><span data-stu-id="2500b-2197">No-Führerschein</span></span> 
- <span data-ttu-id="2500b-2198">No-Fuhrerschein</span><span class="sxs-lookup"><span data-stu-id="2500b-2198">No-Fuhrerschein</span></span> 
- <span data-ttu-id="2500b-2199">No-Fuehrerschein</span><span class="sxs-lookup"><span data-stu-id="2500b-2199">No-Fuehrerschein</span></span> 
- <span data-ttu-id="2500b-2200">N-Führerschein</span><span class="sxs-lookup"><span data-stu-id="2500b-2200">N-Führerschein</span></span> 
- <span data-ttu-id="2500b-2201">N-Fuhrerschein</span><span class="sxs-lookup"><span data-stu-id="2500b-2201">N-Fuhrerschein</span></span> 
- <span data-ttu-id="2500b-2202">N-Fuehrerschein</span><span class="sxs-lookup"><span data-stu-id="2500b-2202">N-Fuehrerschein</span></span> 

#### <a name="keywordgermandriverslicense"></a><span data-ttu-id="2500b-2203">Keyword_german_drivers_license</span><span class="sxs-lookup"><span data-stu-id="2500b-2203">Keyword_german_drivers_license</span></span>

- <span data-ttu-id="2500b-2204">ausstellungsdatum</span><span class="sxs-lookup"><span data-stu-id="2500b-2204">ausstellungsdatum</span></span>
- <span data-ttu-id="2500b-2205">ausstellungsort</span><span class="sxs-lookup"><span data-stu-id="2500b-2205">ausstellungsort</span></span>
- <span data-ttu-id="2500b-2206">ausstellende behöde</span><span class="sxs-lookup"><span data-stu-id="2500b-2206">ausstellende behöde</span></span>
- <span data-ttu-id="2500b-2207">ausstellende behorde</span><span class="sxs-lookup"><span data-stu-id="2500b-2207">ausstellende behorde</span></span>
- <span data-ttu-id="2500b-2208">ausstellende behoerde</span><span class="sxs-lookup"><span data-stu-id="2500b-2208">ausstellende behoerde</span></span>
   
## <a name="german-passport-number"></a><span data-ttu-id="2500b-2209">Germania - Numero di passaporto</span><span class="sxs-lookup"><span data-stu-id="2500b-2209">German Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="2500b-2210">Formato</span><span class="sxs-lookup"><span data-stu-id="2500b-2210">Format</span></span>

<span data-ttu-id="2500b-2211">10 cifre o lettere</span><span class="sxs-lookup"><span data-stu-id="2500b-2211">10 digits or letters</span></span>

### <a name="pattern"></a><span data-ttu-id="2500b-2212">Modello</span><span class="sxs-lookup"><span data-stu-id="2500b-2212">Pattern</span></span>

<span data-ttu-id="2500b-2213">Il modello deve includere tutti gli elementi seguenti:</span><span class="sxs-lookup"><span data-stu-id="2500b-2213">Pattern must include all of the following:</span></span>
- <span data-ttu-id="2500b-2214">Il primo carattere è una cifra o una lettera del gruppo seguente: C, F, G, H, J, K</span><span class="sxs-lookup"><span data-stu-id="2500b-2214">First character is a digit or a letter from this set (C, F, G, H, J, K)</span></span> 
- <span data-ttu-id="2500b-2215">Tre cifre</span><span class="sxs-lookup"><span data-stu-id="2500b-2215">Three digits</span></span> 
- <span data-ttu-id="2500b-2216">Cinque cifre o lettere del gruppo seguente: C, -H, J-N, P, R, T, V-Z</span><span class="sxs-lookup"><span data-stu-id="2500b-2216">Five digits or letters from this set (C, -H, J-N, P, R, T, V-Z)</span></span> 
- <span data-ttu-id="2500b-2217">Una cifra</span><span class="sxs-lookup"><span data-stu-id="2500b-2217">A digit</span></span>

### <a name="checksum"></a><span data-ttu-id="2500b-2218">Checksum</span><span class="sxs-lookup"><span data-stu-id="2500b-2218">Checksum</span></span>

<span data-ttu-id="2500b-2219">Sì</span><span class="sxs-lookup"><span data-stu-id="2500b-2219">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="2500b-2220">Definizione</span><span class="sxs-lookup"><span data-stu-id="2500b-2220">Definition</span></span>

<span data-ttu-id="2500b-2221">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="2500b-2221">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2500b-2222">La funzione Func_german_passport restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="2500b-2222">The function Func_german_passport finds content that matches the pattern.</span></span>
- <span data-ttu-id="2500b-2223">Viene trovata una parola chiave fra le cinque elencate.</span><span class="sxs-lookup"><span data-stu-id="2500b-2223">A keyword from any of the five keyword lists is found.</span></span>
- <span data-ttu-id="2500b-2224">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="2500b-2224">The checksum passes.</span></span>

<span data-ttu-id="2500b-2225">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="2500b-2225">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2500b-2226">La funzione Func_german_passport_data restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="2500b-2226">The function Func_german_passport_data finds content that matches the pattern.</span></span>
- <span data-ttu-id="2500b-2227">Viene trovata una parola chiave fra le cinque elencate.</span><span class="sxs-lookup"><span data-stu-id="2500b-2227">A keyword from any of the five keyword lists is found.</span></span>
- <span data-ttu-id="2500b-2228">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="2500b-2228">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="2500b-2229">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="2500b-2229">Keywords</span></span>

#### <a name="keywordgermanpassport"></a><span data-ttu-id="2500b-2230">Keyword_german_passport</span><span class="sxs-lookup"><span data-stu-id="2500b-2230">Keyword_german_passport</span></span>

- <span data-ttu-id="2500b-2231">reisepass</span><span class="sxs-lookup"><span data-stu-id="2500b-2231">reisepass</span></span>
- <span data-ttu-id="2500b-2232">reisepasse</span><span class="sxs-lookup"><span data-stu-id="2500b-2232">reisepasse</span></span>
- <span data-ttu-id="2500b-2233">reisepassnummer</span><span class="sxs-lookup"><span data-stu-id="2500b-2233">reisepassnummer</span></span>
- <span data-ttu-id="2500b-2234">passaporto</span><span class="sxs-lookup"><span data-stu-id="2500b-2234">passport</span></span>
- <span data-ttu-id="2500b-2235">passaporti</span><span class="sxs-lookup"><span data-stu-id="2500b-2235">passports</span></span>

#### <a name="keywordgermanpassportcollaborative"></a><span data-ttu-id="2500b-2236">Keyword_german_passport_collaborative</span><span class="sxs-lookup"><span data-stu-id="2500b-2236">Keyword_german_passport_collaborative</span></span>

- <span data-ttu-id="2500b-2237">geburtsdatum</span><span class="sxs-lookup"><span data-stu-id="2500b-2237">geburtsdatum</span></span>
- <span data-ttu-id="2500b-2238">ausstellungsdatum</span><span class="sxs-lookup"><span data-stu-id="2500b-2238">ausstellungsdatum</span></span>
- <span data-ttu-id="2500b-2239">ausstellungsort</span><span class="sxs-lookup"><span data-stu-id="2500b-2239">ausstellungsort</span></span>

#### <a name="keywordgermanpassportnumber"></a><span data-ttu-id="2500b-2240">Keyword_german_passport_number</span><span class="sxs-lookup"><span data-stu-id="2500b-2240">Keyword_german_passport_number</span></span>

<span data-ttu-id="2500b-2241">No-Reisepass Nr-Reisepass</span><span class="sxs-lookup"><span data-stu-id="2500b-2241">No-Reisepass Nr-Reisepass</span></span>

#### <a name="keywordgermanpassport1"></a><span data-ttu-id="2500b-2242">Keyword_german_passport1</span><span class="sxs-lookup"><span data-stu-id="2500b-2242">Keyword_german_passport1</span></span>

<span data-ttu-id="2500b-2243">Reisepass-Nr</span><span class="sxs-lookup"><span data-stu-id="2500b-2243">Reisepass-Nr</span></span>

#### <a name="keywordgermanpassport2"></a><span data-ttu-id="2500b-2244">Keyword_german_passport2</span><span class="sxs-lookup"><span data-stu-id="2500b-2244">Keyword_german_passport2</span></span>

<span data-ttu-id="2500b-2245">bnationalit. t</span><span class="sxs-lookup"><span data-stu-id="2500b-2245">bnationalit.t</span></span>
   
## <a name="germany-identity-card-number"></a><span data-ttu-id="2500b-2246">Germania - Numero carta di identità</span><span class="sxs-lookup"><span data-stu-id="2500b-2246">Germany Identity Card Number</span></span>

### <a name="format"></a><span data-ttu-id="2500b-2247">Formato</span><span class="sxs-lookup"><span data-stu-id="2500b-2247">Format</span></span>

<span data-ttu-id="2500b-2248">Dal 1 ° novembre 2010: nove lettere e cifre</span><span class="sxs-lookup"><span data-stu-id="2500b-2248">Since 1 November 2010: Nine letters and digits</span></span>

<span data-ttu-id="2500b-2249">Dal 1 ° aprile 1987 al 31 ottobre 2010:10 cifre</span><span class="sxs-lookup"><span data-stu-id="2500b-2249">From 1 April 1987 until 31 October 2010: 10 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="2500b-2250">Modello</span><span class="sxs-lookup"><span data-stu-id="2500b-2250">Pattern</span></span>

<span data-ttu-id="2500b-2251">A partire dal 1° novembre 2010:</span><span class="sxs-lookup"><span data-stu-id="2500b-2251">Since 1 November 2010:</span></span>
- <span data-ttu-id="2500b-2252">Una lettera (senza distinzione tra maiuscole/minuscole)</span><span class="sxs-lookup"><span data-stu-id="2500b-2252">One letter (not case sensitive)</span></span> 
- <span data-ttu-id="2500b-2253">Otto cifre</span><span class="sxs-lookup"><span data-stu-id="2500b-2253">Eight digits</span></span>

<span data-ttu-id="2500b-2254">Dal 1 ° aprile 1987 al 31 ottobre 2010:</span><span class="sxs-lookup"><span data-stu-id="2500b-2254">From 1 April 1987 until 31 October 2010:</span></span>
- <span data-ttu-id="2500b-2255">10 cifre</span><span class="sxs-lookup"><span data-stu-id="2500b-2255">10 digits</span></span>

### <a name="checksum"></a><span data-ttu-id="2500b-2256">Checksum</span><span class="sxs-lookup"><span data-stu-id="2500b-2256">Checksum</span></span>

<span data-ttu-id="2500b-2257">No</span><span class="sxs-lookup"><span data-stu-id="2500b-2257">No</span></span>

### <a name="definition"></a><span data-ttu-id="2500b-2258">Definizione</span><span class="sxs-lookup"><span data-stu-id="2500b-2258">Definition</span></span>

<span data-ttu-id="2500b-2259">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 65%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="2500b-2259">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2500b-2260">L'espressione regolare Regex_germany_id_card trova il contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="2500b-2260">The regular expression Regex_germany_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="2500b-2261">Viene trovata una parola chiave da Keyword_germany_id_card.</span><span class="sxs-lookup"><span data-stu-id="2500b-2261">A keyword from Keyword_germany_id_card is found.</span></span>

```
<!-- Germany Identity Card Number -->
<Entity id="e577372f-c42e-47a0-9d85-bebed1c237d4" recommendedConfidence="65" patternsProximity="300">
  <Pattern confidenceLevel="65">
     <IdMatch idRef="Regex_germany_id_card"/>
     <Match idRef="Keyword_germany_id_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="2500b-2262">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="2500b-2262">Keywords</span></span>

#### <a name="keywordgermanyidcard"></a><span data-ttu-id="2500b-2263">Keyword_germany_id_card</span><span class="sxs-lookup"><span data-stu-id="2500b-2263">Keyword_germany_id_card</span></span>

- <span data-ttu-id="2500b-2264">Carta di identità</span><span class="sxs-lookup"><span data-stu-id="2500b-2264">Identity Card</span></span>
- <span data-ttu-id="2500b-2265">ID</span><span class="sxs-lookup"><span data-stu-id="2500b-2265">ID</span></span>
- <span data-ttu-id="2500b-2266">Identificazione</span><span class="sxs-lookup"><span data-stu-id="2500b-2266">Identification</span></span>
- <span data-ttu-id="2500b-2267">Personalausweis</span><span class="sxs-lookup"><span data-stu-id="2500b-2267">Personalausweis</span></span>
- <span data-ttu-id="2500b-2268">Identifizierungsnummer</span><span class="sxs-lookup"><span data-stu-id="2500b-2268">Identifizierungsnummer</span></span>
- <span data-ttu-id="2500b-2269">Ausweis</span><span class="sxs-lookup"><span data-stu-id="2500b-2269">Ausweis</span></span>
- <span data-ttu-id="2500b-2270">Identifikation</span><span class="sxs-lookup"><span data-stu-id="2500b-2270">Identifikation</span></span>
   
## <a name="greece-national-id-card"></a><span data-ttu-id="2500b-2271">Carta d'identità (Grecia)</span><span class="sxs-lookup"><span data-stu-id="2500b-2271">Greece National ID Card</span></span>

### <a name="format"></a><span data-ttu-id="2500b-2272">Formato</span><span class="sxs-lookup"><span data-stu-id="2500b-2272">Format</span></span>

<span data-ttu-id="2500b-2273">Combinazione di 7-8 lettere e numeri, oltre a un trattino</span><span class="sxs-lookup"><span data-stu-id="2500b-2273">Combination of 7-8 letters and numbers plus a dash</span></span>

### <a name="pattern"></a><span data-ttu-id="2500b-2274">Modello</span><span class="sxs-lookup"><span data-stu-id="2500b-2274">Pattern</span></span>

<span data-ttu-id="2500b-2275">Sette lettere e numeri (formato precedente):</span><span class="sxs-lookup"><span data-stu-id="2500b-2275">Seven letters and numbers (old format):</span></span>
- <span data-ttu-id="2500b-2276">Una lettera (qualsiasi lettera dell'alfabeto greco) </span><span class="sxs-lookup"><span data-stu-id="2500b-2276">One letter (any letter of the Greek alphabet)</span></span> 
- <span data-ttu-id="2500b-2277">Un trattino</span><span class="sxs-lookup"><span data-stu-id="2500b-2277">A dash</span></span> 
- <span data-ttu-id="2500b-2278">Sei cifre</span><span class="sxs-lookup"><span data-stu-id="2500b-2278">Six digits</span></span>

<span data-ttu-id="2500b-2279">Otto lettere e numeri (nuovo formato):</span><span class="sxs-lookup"><span data-stu-id="2500b-2279">Eight letters and numbers (new format):</span></span>
- <span data-ttu-id="2500b-2280">Due lettere in maiuscolo sia in alfabeto latino che greco (ABEZHIKMNOPTYX) </span><span class="sxs-lookup"><span data-stu-id="2500b-2280">Two letters whose uppercase character occurs in both the Greek and Latin alphabets (ABEZHIKMNOPTYX)</span></span> 
- <span data-ttu-id="2500b-2281">Un trattino</span><span class="sxs-lookup"><span data-stu-id="2500b-2281">A dash</span></span> 
- <span data-ttu-id="2500b-2282">Sei cifre</span><span class="sxs-lookup"><span data-stu-id="2500b-2282">Six digits</span></span>

### <a name="checksum"></a><span data-ttu-id="2500b-2283">Checksum</span><span class="sxs-lookup"><span data-stu-id="2500b-2283">Checksum</span></span>

<span data-ttu-id="2500b-2284">No</span><span class="sxs-lookup"><span data-stu-id="2500b-2284">No</span></span>

### <a name="definition"></a><span data-ttu-id="2500b-2285">Definizione</span><span class="sxs-lookup"><span data-stu-id="2500b-2285">Definition</span></span>

<span data-ttu-id="2500b-2286">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="2500b-2286">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2500b-2287">L'espressione regolare Regex_greece_id_card trova il contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="2500b-2287">The regular expression Regex_greece_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="2500b-2288">Viene trovata una parola chiave da Keyword_greece_id_card.</span><span class="sxs-lookup"><span data-stu-id="2500b-2288">A keyword from Keyword_greece_id_card is found.</span></span>

```
<!-- Greece National ID Card -->
<Entity id="82568215-1da1-46d3-874a-d2294d81b5ac" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Regex_greece_id_card"/>
     <Match idRef="Keyword_greece_id_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="2500b-2289">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="2500b-2289">Keywords</span></span>

#### <a name="keywordgreeceidcard"></a><span data-ttu-id="2500b-2290">Keyword_greece_id_card</span><span class="sxs-lookup"><span data-stu-id="2500b-2290">Keyword_greece_id_card</span></span>

- <span data-ttu-id="2500b-2291">Carta d’identità greca</span><span class="sxs-lookup"><span data-stu-id="2500b-2291">Greek identity Card</span></span>
- <span data-ttu-id="2500b-2292">Tautotita</span><span class="sxs-lookup"><span data-stu-id="2500b-2292">Tautotita</span></span>
- <span data-ttu-id="2500b-2293">Δελτίο αστυνομικής ταυτότητας</span><span class="sxs-lookup"><span data-stu-id="2500b-2293">Δελτίο αστυνομικής ταυτότητας</span></span>
- <span data-ttu-id="2500b-2294">Ταυτότητα</span><span class="sxs-lookup"><span data-stu-id="2500b-2294">Ταυτότητα</span></span>
   
## <a name="hong-kong-identity-card-hkid-number"></a><span data-ttu-id="2500b-2295">Hong Kong - Numero di carta di identità (HKID)</span><span class="sxs-lookup"><span data-stu-id="2500b-2295">Hong Kong Identity Card (HKID) Number</span></span>

### <a name="format"></a><span data-ttu-id="2500b-2296">Formato</span><span class="sxs-lookup"><span data-stu-id="2500b-2296">Format</span></span>

<span data-ttu-id="2500b-2297">Combinazione di 8-9 lettere e numeri. Facoltativamente, l’ultimo carattere può essere racchiuso tra parentesi</span><span class="sxs-lookup"><span data-stu-id="2500b-2297">Combination of 8-9 letters and numbers plus optional parentheses around the final character</span></span>

### <a name="pattern"></a><span data-ttu-id="2500b-2298">Modello</span><span class="sxs-lookup"><span data-stu-id="2500b-2298">Pattern</span></span>

<span data-ttu-id="2500b-2299">Combinazione di 8-9 lettere:</span><span class="sxs-lookup"><span data-stu-id="2500b-2299">Combination of 8-9 letters:</span></span>
- <span data-ttu-id="2500b-2300">1-2 lettere (senza distinzione tra maiuscole e minuscole)</span><span class="sxs-lookup"><span data-stu-id="2500b-2300">1-2 letters (not case sensitive)</span></span> 
- <span data-ttu-id="2500b-2301">Sei cifre</span><span class="sxs-lookup"><span data-stu-id="2500b-2301">Six digits</span></span> 
- <span data-ttu-id="2500b-2302">L'ultimo carattere (qualsiasi cifra o la lettera A), è rappresentato dal numero di controllo. Facoltativamente, può essere racchiuso tra parentesi.</span><span class="sxs-lookup"><span data-stu-id="2500b-2302">The final character (any digit or the letter A), which is the check digit and is optionally enclosed in parentheses.</span></span>

### <a name="checksum"></a><span data-ttu-id="2500b-2303">Checksum</span><span class="sxs-lookup"><span data-stu-id="2500b-2303">Checksum</span></span>

<span data-ttu-id="2500b-2304">Sì</span><span class="sxs-lookup"><span data-stu-id="2500b-2304">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="2500b-2305">Definizione</span><span class="sxs-lookup"><span data-stu-id="2500b-2305">Definition</span></span>

<span data-ttu-id="2500b-2306">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="2500b-2306">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2500b-2307">La funzione Func_hong_kong_id_card trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="2500b-2307">The function Func_hong_kong_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="2500b-2308">Viene trovata una parola chiave da Keyword_hong_kong_id_card.</span><span class="sxs-lookup"><span data-stu-id="2500b-2308">A keyword from Keyword_hong_kong_id_card is found.</span></span>
- <span data-ttu-id="2500b-2309">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="2500b-2309">The checksum passes.</span></span>

<span data-ttu-id="2500b-2310">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 65%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="2500b-2310">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2500b-2311">La funzione Func_hong_kong_id_card trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="2500b-2311">The function Func_hong_kong_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="2500b-2312">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="2500b-2312">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="2500b-2313">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="2500b-2313">Keywords</span></span>

#### <a name="keywordhongkongidcard"></a><span data-ttu-id="2500b-2314">Keyword_hong_kong_id_card</span><span class="sxs-lookup"><span data-stu-id="2500b-2314">Keyword_hong_kong_id_card</span></span>

- <span data-ttu-id="2500b-2315">carta di identità di Hong Kong</span><span class="sxs-lookup"><span data-stu-id="2500b-2315">hong kong identity card</span></span>
- <span data-ttu-id="2500b-2316">HKIDC</span><span class="sxs-lookup"><span data-stu-id="2500b-2316">HKIDC</span></span>
- <span data-ttu-id="2500b-2317">id card</span><span class="sxs-lookup"><span data-stu-id="2500b-2317">id card</span></span>
- <span data-ttu-id="2500b-2318">carta di identità</span><span class="sxs-lookup"><span data-stu-id="2500b-2318">identity card</span></span>
- <span data-ttu-id="2500b-2319">carta di identità HK</span><span class="sxs-lookup"><span data-stu-id="2500b-2319">hk identity card</span></span>
- <span data-ttu-id="2500b-2320">ID Hong Kong</span><span class="sxs-lookup"><span data-stu-id="2500b-2320">hong kong id</span></span>
- <span data-ttu-id="2500b-2321">香港身份證</span><span class="sxs-lookup"><span data-stu-id="2500b-2321">香港身份證</span></span>
- <span data-ttu-id="2500b-2322">香港永久性居民身份證</span><span class="sxs-lookup"><span data-stu-id="2500b-2322">香港永久性居民身份證</span></span>
- <span data-ttu-id="2500b-2323">身份證</span><span class="sxs-lookup"><span data-stu-id="2500b-2323">身份證</span></span>
- <span data-ttu-id="2500b-2324">身份証</span><span class="sxs-lookup"><span data-stu-id="2500b-2324">身份証</span></span>
- <span data-ttu-id="2500b-2325">身分證</span><span class="sxs-lookup"><span data-stu-id="2500b-2325">身分證</span></span>
- <span data-ttu-id="2500b-2326">身分証</span><span class="sxs-lookup"><span data-stu-id="2500b-2326">身分証</span></span>
- <span data-ttu-id="2500b-2327">香港身份証</span><span class="sxs-lookup"><span data-stu-id="2500b-2327">香港身份証</span></span>
- <span data-ttu-id="2500b-2328">香港身分證</span><span class="sxs-lookup"><span data-stu-id="2500b-2328">香港身分證</span></span>
- <span data-ttu-id="2500b-2329">香港身分証</span><span class="sxs-lookup"><span data-stu-id="2500b-2329">香港身分証</span></span>
- <span data-ttu-id="2500b-2330">香港身份證</span><span class="sxs-lookup"><span data-stu-id="2500b-2330">香港身份證</span></span>
- <span data-ttu-id="2500b-2331">香港居民身份證</span><span class="sxs-lookup"><span data-stu-id="2500b-2331">香港居民身份證</span></span>
- <span data-ttu-id="2500b-2332">香港居民身份証</span><span class="sxs-lookup"><span data-stu-id="2500b-2332">香港居民身份証</span></span>
- <span data-ttu-id="2500b-2333">香港居民身分證</span><span class="sxs-lookup"><span data-stu-id="2500b-2333">香港居民身分證</span></span>
- <span data-ttu-id="2500b-2334">香港居民身分証</span><span class="sxs-lookup"><span data-stu-id="2500b-2334">香港居民身分証</span></span>
- <span data-ttu-id="2500b-2335">香港永久性居民身份証</span><span class="sxs-lookup"><span data-stu-id="2500b-2335">香港永久性居民身份証</span></span>
- <span data-ttu-id="2500b-2336">香港永久性居民身分證</span><span class="sxs-lookup"><span data-stu-id="2500b-2336">香港永久性居民身分證</span></span>
- <span data-ttu-id="2500b-2337">香港永久性居民身分証</span><span class="sxs-lookup"><span data-stu-id="2500b-2337">香港永久性居民身分証</span></span>
- <span data-ttu-id="2500b-2338">香港永久性居民身份證</span><span class="sxs-lookup"><span data-stu-id="2500b-2338">香港永久性居民身份證</span></span>
- <span data-ttu-id="2500b-2339">香港非永久性居民身份證</span><span class="sxs-lookup"><span data-stu-id="2500b-2339">香港非永久性居民身份證</span></span>
- <span data-ttu-id="2500b-2340">香港非永久性居民身份証</span><span class="sxs-lookup"><span data-stu-id="2500b-2340">香港非永久性居民身份証</span></span>
- <span data-ttu-id="2500b-2341">香港非永久性居民身分證</span><span class="sxs-lookup"><span data-stu-id="2500b-2341">香港非永久性居民身分證</span></span>
- <span data-ttu-id="2500b-2342">香港非永久性居民身分証</span><span class="sxs-lookup"><span data-stu-id="2500b-2342">香港非永久性居民身分証</span></span>
- <span data-ttu-id="2500b-2343">香港特別行政區永久性居民身份證</span><span class="sxs-lookup"><span data-stu-id="2500b-2343">香港特別行政區永久性居民身份證</span></span>
- <span data-ttu-id="2500b-2344">香港特別行政區永久性居民身份証</span><span class="sxs-lookup"><span data-stu-id="2500b-2344">香港特別行政區永久性居民身份証</span></span>
- <span data-ttu-id="2500b-2345">香港特別行政區永久性居民身分證</span><span class="sxs-lookup"><span data-stu-id="2500b-2345">香港特別行政區永久性居民身分證</span></span>
- <span data-ttu-id="2500b-2346">香港特別行政區永久性居民身分証</span><span class="sxs-lookup"><span data-stu-id="2500b-2346">香港特別行政區永久性居民身分証</span></span>
- <span data-ttu-id="2500b-2347">香港特別行政區非永久性居民身份證</span><span class="sxs-lookup"><span data-stu-id="2500b-2347">香港特別行政區非永久性居民身份證</span></span>
- <span data-ttu-id="2500b-2348">香港特別行政區非永久性居民身份証</span><span class="sxs-lookup"><span data-stu-id="2500b-2348">香港特別行政區非永久性居民身份証</span></span>
- <span data-ttu-id="2500b-2349">香港特別行政區非永久性居民身分證</span><span class="sxs-lookup"><span data-stu-id="2500b-2349">香港特別行政區非永久性居民身分證</span></span>
- <span data-ttu-id="2500b-2350">香港特別行政區非永久性居民身分証</span><span class="sxs-lookup"><span data-stu-id="2500b-2350">香港特別行政區非永久性居民身分証</span></span>
   
## <a name="india-permanent-account-number-pan"></a><span data-ttu-id="2500b-2351">India - Numero di conto permanente (PAN)</span><span class="sxs-lookup"><span data-stu-id="2500b-2351">India Permanent Account Number (PAN)</span></span>

### <a name="format"></a><span data-ttu-id="2500b-2352">Formato</span><span class="sxs-lookup"><span data-stu-id="2500b-2352">Format</span></span>

<span data-ttu-id="2500b-2353">10 lettere o cifre</span><span class="sxs-lookup"><span data-stu-id="2500b-2353">10 letters or digits</span></span>

### <a name="pattern"></a><span data-ttu-id="2500b-2354">Modello</span><span class="sxs-lookup"><span data-stu-id="2500b-2354">Pattern</span></span>

<span data-ttu-id="2500b-2355">10 lettere o cifre:</span><span class="sxs-lookup"><span data-stu-id="2500b-2355">10 letters or digits:</span></span>
- <span data-ttu-id="2500b-2356">Cinque lettere (senza distinzione tra maiuscole e minuscole)</span><span class="sxs-lookup"><span data-stu-id="2500b-2356">Five letters (not case sensitive)</span></span> 
- <span data-ttu-id="2500b-2357">Quattro cifre</span><span class="sxs-lookup"><span data-stu-id="2500b-2357">Four digits</span></span> 
- <span data-ttu-id="2500b-2358">Una lettera, ovvero una cifra di controllo alfabetica</span><span class="sxs-lookup"><span data-stu-id="2500b-2358">A letter which is an alphabetic check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="2500b-2359">Checksum</span><span class="sxs-lookup"><span data-stu-id="2500b-2359">Checksum</span></span>

<span data-ttu-id="2500b-2360">Sì</span><span class="sxs-lookup"><span data-stu-id="2500b-2360">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="2500b-2361">Definizione</span><span class="sxs-lookup"><span data-stu-id="2500b-2361">Definition</span></span>

<span data-ttu-id="2500b-2362">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="2500b-2362">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2500b-2363">L'espressione regolare Regex_india_permanent_account_number trova il contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="2500b-2363">The regular expression Regex_india_permanent_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="2500b-2364">Viene trovata una parola chiave da Keyword_india_permanent_account_number.</span><span class="sxs-lookup"><span data-stu-id="2500b-2364">A keyword from Keyword_india_permanent_account_number is found.</span></span>
- <span data-ttu-id="2500b-2365">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="2500b-2365">The checksum passes.</span></span>

```
<!-- India Permanent Account Number -->
<Entity id="2602bfee-9bb0-47a5-a7a6-2bf3053e2804" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Regex_india_permanent_account_number"/>
     <Match idRef="Keyword_india_permanent_account_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="2500b-2366">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="2500b-2366">Keywords</span></span>

#### <a name="keywordindiapermanentaccountnumber"></a><span data-ttu-id="2500b-2367">Keyword_india_permanent_account_number</span><span class="sxs-lookup"><span data-stu-id="2500b-2367">Keyword_india_permanent_account_number</span></span>

- <span data-ttu-id="2500b-2368">Permanent Account Number</span><span class="sxs-lookup"><span data-stu-id="2500b-2368">Permanent Account Number</span></span> 
- <span data-ttu-id="2500b-2369">PAN</span><span class="sxs-lookup"><span data-stu-id="2500b-2369">PAN</span></span> 
   
## <a name="india-unique-identification-aadhaar-number"></a><span data-ttu-id="2500b-2370">India - Numero di identificazione univoco (Aadhaar)</span><span class="sxs-lookup"><span data-stu-id="2500b-2370">India Unique Identification (Aadhaar) Number</span></span>

### <a name="format"></a><span data-ttu-id="2500b-2371">Formato</span><span class="sxs-lookup"><span data-stu-id="2500b-2371">Format</span></span>

<span data-ttu-id="2500b-2372">12 cifre contenenti spazi o trattini facoltativi </span><span class="sxs-lookup"><span data-stu-id="2500b-2372">12 digits containing optional spaces or dashes</span></span>

### <a name="pattern"></a><span data-ttu-id="2500b-2373">Modello</span><span class="sxs-lookup"><span data-stu-id="2500b-2373">Pattern</span></span>

<span data-ttu-id="2500b-2374">12 cifre:</span><span class="sxs-lookup"><span data-stu-id="2500b-2374">12 digits:</span></span>
- <span data-ttu-id="2500b-2375">Quattro cifre</span><span class="sxs-lookup"><span data-stu-id="2500b-2375">Four digits</span></span> 
- <span data-ttu-id="2500b-2376">Uno spazio o un trattino facoltativo </span><span class="sxs-lookup"><span data-stu-id="2500b-2376">An optional space or dash</span></span> 
- <span data-ttu-id="2500b-2377">Quattro cifre</span><span class="sxs-lookup"><span data-stu-id="2500b-2377">Four digits</span></span> 
- <span data-ttu-id="2500b-2378">Uno spazio o un trattino facoltativo </span><span class="sxs-lookup"><span data-stu-id="2500b-2378">An optional space or dash</span></span> 
- <span data-ttu-id="2500b-2379">L'ultimo carattere, ovvero il numero di controllo</span><span class="sxs-lookup"><span data-stu-id="2500b-2379">The final digit which is the check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="2500b-2380">Checksum</span><span class="sxs-lookup"><span data-stu-id="2500b-2380">Checksum</span></span>

<span data-ttu-id="2500b-2381">Sì</span><span class="sxs-lookup"><span data-stu-id="2500b-2381">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="2500b-2382">Definizione</span><span class="sxs-lookup"><span data-stu-id="2500b-2382">Definition</span></span>

<span data-ttu-id="2500b-2383">Un criterio DLP è 85% fiducioso di aver rilevato questo tipo di informazioni riservate se, entro 300 caratteri: la funzione Func_india_aadhaar trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="2500b-2383">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The function Func_india_aadhaar finds content that matches the pattern.</span></span>
<span data-ttu-id="2500b-2384">Viene trovata una parola chiave da Keyword_india_aadhar.</span><span class="sxs-lookup"><span data-stu-id="2500b-2384">A keyword from Keyword_india_aadhar is found.</span></span>
<span data-ttu-id="2500b-2385">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="2500b-2385">The checksum passes.</span></span>
<span data-ttu-id="2500b-2386">Un criterio DLP è 75% fiducioso di aver rilevato questo tipo di informazioni riservate se, entro 300 caratteri: la funzione Func_india_aadhaar trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="2500b-2386">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The function Func_india_aadhaar finds content that matches the pattern.</span></span>
<span data-ttu-id="2500b-2387">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="2500b-2387">The checksum passes.</span></span>
<!-- India Unique Identification (Aadhaar) number -->
<span data-ttu-id="2500b-2388"><Entity id="1ca46b29-76f5-4f46-9383-cfa15e91048f" recommendedConfidence="85" patternsProximity="300"> <Pattern confidenceLevel="85"> <IdMatch idRef="Func_india_aadhaar"/> <Match idRef="Keyword_india_aadhar"/> </Pattern> <Pattern confidenceLevel="75"> <IdMatch idRef="Func_india_aadhaar"/> </Pattern>
</Entity></span><span class="sxs-lookup"><span data-stu-id="2500b-2388"></span></span>

### <a name="keywords"></a><span data-ttu-id="2500b-2389">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="2500b-2389">Keywords</span></span>
   
#### <a name="keywordindiaaadhar"></a><span data-ttu-id="2500b-2390">Keyword_india_aadhar</span><span class="sxs-lookup"><span data-stu-id="2500b-2390">Keyword_india_aadhar</span></span>
- <span data-ttu-id="2500b-2391">Aadhar</span><span class="sxs-lookup"><span data-stu-id="2500b-2391">Aadhar</span></span>
- <span data-ttu-id="2500b-2392">Aadhaar</span><span class="sxs-lookup"><span data-stu-id="2500b-2392">Aadhaar</span></span>
- <span data-ttu-id="2500b-2393">UID</span><span class="sxs-lookup"><span data-stu-id="2500b-2393">UID</span></span>
- <span data-ttu-id="2500b-2394">आधार</span><span class="sxs-lookup"><span data-stu-id="2500b-2394">आधार</span></span>
   
## <a name="indonesia-identity-card-ktp-number"></a><span data-ttu-id="2500b-2395">Indonesia - Numero di carta di identità (KTP)</span><span class="sxs-lookup"><span data-stu-id="2500b-2395">Indonesia Identity Card (KTP) Number</span></span>

### <a name="format"></a><span data-ttu-id="2500b-2396">Formato</span><span class="sxs-lookup"><span data-stu-id="2500b-2396">Format</span></span>

<span data-ttu-id="2500b-2397">16 cifre contenenti punti facoltativi </span><span class="sxs-lookup"><span data-stu-id="2500b-2397">16 digits containing optional periods</span></span>

### <a name="pattern"></a><span data-ttu-id="2500b-2398">Modello</span><span class="sxs-lookup"><span data-stu-id="2500b-2398">Pattern</span></span>

<span data-ttu-id="2500b-2399">16 cifre:</span><span class="sxs-lookup"><span data-stu-id="2500b-2399">16 digits:</span></span>
- <span data-ttu-id="2500b-2400">Codice provincia a due cifre </span><span class="sxs-lookup"><span data-stu-id="2500b-2400">Two-digit province code</span></span> 
- <span data-ttu-id="2500b-2401">Un punto (facoltativo) </span><span class="sxs-lookup"><span data-stu-id="2500b-2401">A period (optional)</span></span> 
- <span data-ttu-id="2500b-2402">Codice città o area a due cifre </span><span class="sxs-lookup"><span data-stu-id="2500b-2402">Two-digit regency or city code</span></span> 
- <span data-ttu-id="2500b-2403">Codice sotto-distretto a due cifre </span><span class="sxs-lookup"><span data-stu-id="2500b-2403">Two-digit subdistrict code</span></span> 
- <span data-ttu-id="2500b-2404">Un punto (facoltativo) </span><span class="sxs-lookup"><span data-stu-id="2500b-2404">A period (optional)</span></span> 
- <span data-ttu-id="2500b-2405">Sei cifre nel formato GGMMAA, ovvero la data di nascita</span><span class="sxs-lookup"><span data-stu-id="2500b-2405">Six digits in the format DDMMYY which are the date of birth</span></span> 
- <span data-ttu-id="2500b-2406">Un punto (facoltativo) </span><span class="sxs-lookup"><span data-stu-id="2500b-2406">A period (optional)</span></span> 
- <span data-ttu-id="2500b-2407">Quattro cifre</span><span class="sxs-lookup"><span data-stu-id="2500b-2407">Four digits</span></span>

### <a name="checksum"></a><span data-ttu-id="2500b-2408">Checksum</span><span class="sxs-lookup"><span data-stu-id="2500b-2408">Checksum</span></span>

<span data-ttu-id="2500b-2409">No</span><span class="sxs-lookup"><span data-stu-id="2500b-2409">No</span></span>

### <a name="definition"></a><span data-ttu-id="2500b-2410">Definizione</span><span class="sxs-lookup"><span data-stu-id="2500b-2410">Definition</span></span>

<span data-ttu-id="2500b-2411">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="2500b-2411">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2500b-2412">L'espressione regolare Regex_indonesia_id_card trova il contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="2500b-2412">The regular expression Regex_indonesia_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="2500b-2413">Viene trovata una parola chiave da Keyword_indonesia_id_card.</span><span class="sxs-lookup"><span data-stu-id="2500b-2413">A keyword from Keyword_indonesia_id_card is found.</span></span>

<span data-ttu-id="2500b-2414">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="2500b-2414">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2500b-2415">L'espressione regolare Regex_indonesia_id_card trova il contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="2500b-2415">The regular expression Regex_indonesia_id_card finds content that matches the pattern.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="2500b-2416">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="2500b-2416">Keywords</span></span>
   
#### <a name="keywordindonesiaidcard"></a><span data-ttu-id="2500b-2417">Keyword_indonesia_id_card</span><span class="sxs-lookup"><span data-stu-id="2500b-2417">Keyword_indonesia_id_card</span></span>

- <span data-ttu-id="2500b-2418">KTP</span><span class="sxs-lookup"><span data-stu-id="2500b-2418">KTP</span></span>
- <span data-ttu-id="2500b-2419">Kartu Tanda Penduduk</span><span class="sxs-lookup"><span data-stu-id="2500b-2419">Kartu Tanda Penduduk</span></span> 
- <span data-ttu-id="2500b-2420">Nomor Induk Kependudukan</span><span class="sxs-lookup"><span data-stu-id="2500b-2420">Nomor Induk Kependudukan</span></span> 
   
## <a name="international-banking-account-number-iban"></a><span data-ttu-id="2500b-2421">Numero di conto bancario internazionale (IBAN)</span><span class="sxs-lookup"><span data-stu-id="2500b-2421">International Banking Account Number (IBAN)</span></span>

### <a name="format"></a><span data-ttu-id="2500b-2422">Formato</span><span class="sxs-lookup"><span data-stu-id="2500b-2422">Format</span></span>

<span data-ttu-id="2500b-2423">Codice paese (due lettere) più cifre di controllo (due cifre) più numero BBAN (fino a 30 caratteri)</span><span class="sxs-lookup"><span data-stu-id="2500b-2423">Country code (two letters) plus check digits (two digits) plus bban number (up to 30 characters)</span></span>

### <a name="pattern"></a><span data-ttu-id="2500b-2424">Modello</span><span class="sxs-lookup"><span data-stu-id="2500b-2424">Pattern</span></span>

<span data-ttu-id="2500b-2425">Il modello deve includere tutti gli elementi seguenti:</span><span class="sxs-lookup"><span data-stu-id="2500b-2425">Pattern must include all of the following:</span></span>

- <span data-ttu-id="2500b-2426">Codice paese a due lettere</span><span class="sxs-lookup"><span data-stu-id="2500b-2426">Two-letter country code</span></span>
- <span data-ttu-id="2500b-2427">Due cifre di controllo (seguite da uno spazio facoltativo)</span><span class="sxs-lookup"><span data-stu-id="2500b-2427">Two check digits (followed by an optional space)</span></span> 
- <span data-ttu-id="2500b-2428">1-7 gruppi di quattro lettere o cifre (possono essere separati da spazi)</span><span class="sxs-lookup"><span data-stu-id="2500b-2428">1-7 groups of four letters or digits (can be separated by spaces)</span></span>
- <span data-ttu-id="2500b-2429">1-3 lettere o cifre</span><span class="sxs-lookup"><span data-stu-id="2500b-2429">1-3 letters or digits</span></span>

<span data-ttu-id="2500b-2430">Il formato di ogni paese è leggermente diverso.</span><span class="sxs-lookup"><span data-stu-id="2500b-2430">The format for each country is slightly different.</span></span> <span data-ttu-id="2500b-2431">Il tipo di informazioni riservate IBAN copre questi 60 paesi:</span><span class="sxs-lookup"><span data-stu-id="2500b-2431">The IBAN sensitive information type covers these 60 countries:</span></span>

<span data-ttu-id="2500b-2432">ad, AE, al, at, AZ, BA, be, BG, BH, ch, CR, CY, CZ, de, DK, do, EE, es, Fi, fo, fr, GB, GE, Gi, GL, gr, HR, HU, IE, il, is, it, kW, KZ, lb, li, LT, Lu, LV, MC, MD, me, MK, Mr, MT, MU , NL, no, pl, PT, ro, RS, SA, se, si, SK, SM, TN, TR, VG</span><span class="sxs-lookup"><span data-stu-id="2500b-2432">ad, ae, al, at, az, ba, be, bg, bh, ch, cr, cy, cz, de, dk, do, ee, es, fi, fo, fr, gb, ge, gi, gl, gr, hr, hu, ie, il, is, it, kw, kz, lb, li, lt, lu, lv, mc, md, me, mk, mr, mt, mu, nl, no, pl, pt, ro, rs, sa, se, si, sk, sm, tn, tr, vg</span></span>

### <a name="checksum"></a><span data-ttu-id="2500b-2433">Checksum</span><span class="sxs-lookup"><span data-stu-id="2500b-2433">Checksum</span></span>

<span data-ttu-id="2500b-2434">Sì</span><span class="sxs-lookup"><span data-stu-id="2500b-2434">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="2500b-2435">Definizione</span><span class="sxs-lookup"><span data-stu-id="2500b-2435">Definition</span></span>

<span data-ttu-id="2500b-2436">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="2500b-2436">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2500b-2437">La funzione Func_iban restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="2500b-2437">The function Func_iban finds content that matches the pattern.</span></span>
- <span data-ttu-id="2500b-2438">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="2500b-2438">The checksum passes.</span></span>

```
<Entity id="e7dc4711-11b7-4cb0-b88b-2c394a771f0e" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_iban" />
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="2500b-2439">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="2500b-2439">Keywords</span></span>

<span data-ttu-id="2500b-2440">Nessuno</span><span class="sxs-lookup"><span data-stu-id="2500b-2440">None</span></span>

   
## <a name="ip-address"></a><span data-ttu-id="2500b-2441">Indirizzo IP</span><span class="sxs-lookup"><span data-stu-id="2500b-2441">IP Address</span></span>

### <a name="format"></a><span data-ttu-id="2500b-2442">Formato</span><span class="sxs-lookup"><span data-stu-id="2500b-2442">Format</span></span>

#### <a name="ipv4"></a><span data-ttu-id="2500b-2443">IPv4</span><span class="sxs-lookup"><span data-stu-id="2500b-2443">IPv4:</span></span>
<span data-ttu-id="2500b-2444">Modello complesso che rappresenta le versioni formattate (punti) e quelle non formattate (senza punti) degli indirizzi IPv4</span><span class="sxs-lookup"><span data-stu-id="2500b-2444">Complex pattern which accounts for formatted (periods) and unformatted (no periods) versions of the IPv4 addresses</span></span>

#### <a name="ipv6"></a><span data-ttu-id="2500b-2445">IPv6</span><span class="sxs-lookup"><span data-stu-id="2500b-2445">IPv6:</span></span>
<span data-ttu-id="2500b-2446">Modello complesso che rappresenta i numeri dell'indirizzo IPv6 non formattati (include i due punti)</span><span class="sxs-lookup"><span data-stu-id="2500b-2446">Complex pattern which accounts for formatted IPv6 numbers (which include colons)</span></span>

### <a name="pattern"></a><span data-ttu-id="2500b-2447">Modello</span><span class="sxs-lookup"><span data-stu-id="2500b-2447">Pattern</span></span>

### <a name="checksum"></a><span data-ttu-id="2500b-2448">Checksum</span><span class="sxs-lookup"><span data-stu-id="2500b-2448">Checksum</span></span>

<span data-ttu-id="2500b-2449">No</span><span class="sxs-lookup"><span data-stu-id="2500b-2449">No</span></span>

### <a name="definition"></a><span data-ttu-id="2500b-2450">Definizione</span><span class="sxs-lookup"><span data-stu-id="2500b-2450">Definition</span></span>

<span data-ttu-id="2500b-2451">Nel caso di IPv6, un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="2500b-2451">For IPv6, a DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2500b-2452">L'espressione regolare Regex_ipv6_address restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="2500b-2452">The regular expression Regex_ipv6_address finds content that matches the pattern.</span></span>
- <span data-ttu-id="2500b-2453">Non vengono trovate parole chiave da Keyword_ipaddress.</span><span class="sxs-lookup"><span data-stu-id="2500b-2453">No keyword from Keyword_ipaddress is found.</span></span>

<span data-ttu-id="2500b-2454">Nel caso di IPv4, un criterio DLP rileva questo tipo di informazioni con una probabilità del 95%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="2500b-2454">For IPv4, a DLP policy is 95% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2500b-2455">L'espressione regolare Regex_ipv4_address restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="2500b-2455">The regular expression Regex_ipv4_address finds content that matches the pattern.</span></span>
- <span data-ttu-id="2500b-2456">Viene trovata una parola chiave da Keyword_ipaddress.</span><span class="sxs-lookup"><span data-stu-id="2500b-2456">A keyword from Keyword_ipaddress is found.</span></span>

<span data-ttu-id="2500b-2457">Nel caso di IPv6, un criterio DLP rileva questo tipo di informazioni con una probabilità del 95%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="2500b-2457">For IPv6, a DLP policy is 95% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2500b-2458">L'espressione regolare Regex_ipv6_address restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="2500b-2458">The regular expression Regex_ipv6_address finds content that matches the pattern.</span></span>
- <span data-ttu-id="2500b-2459">Non vengono trovate parole chiave da Keyword_ipaddress.</span><span class="sxs-lookup"><span data-stu-id="2500b-2459">No keyword from Keyword_ipaddress is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="2500b-2460">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="2500b-2460">Keywords</span></span>

#### <a name="keywordipaddress"></a><span data-ttu-id="2500b-2461">Keyword_ipaddress</span><span class="sxs-lookup"><span data-stu-id="2500b-2461">Keyword_ipaddress</span></span>

- <span data-ttu-id="2500b-2462">IP (per questa parola chiave viene fatta distinzione tra maiuscole e minuscole)</span><span class="sxs-lookup"><span data-stu-id="2500b-2462">IP (this keyword is case sensitive)</span></span>
- <span data-ttu-id="2500b-2463">ip address</span><span class="sxs-lookup"><span data-stu-id="2500b-2463">ip address</span></span> 
- <span data-ttu-id="2500b-2464">Indirizzi IP</span><span class="sxs-lookup"><span data-stu-id="2500b-2464">ip addresses</span></span>
- <span data-ttu-id="2500b-2465">internet protocol</span><span class="sxs-lookup"><span data-stu-id="2500b-2465">internet protocol</span></span>
- <span data-ttu-id="2500b-2466">IP-כתובת ה</span><span class="sxs-lookup"><span data-stu-id="2500b-2466">IP-כתובת ה</span></span> 
   
## <a name="international-classification-of-diseases-icd-10-cm"></a><span data-ttu-id="2500b-2467">Classificazione internazionale delle malattie (ICD-10-CM)</span><span class="sxs-lookup"><span data-stu-id="2500b-2467">International Classification of Diseases (ICD-10-CM)</span></span>

### <a name="format"></a><span data-ttu-id="2500b-2468">Formato</span><span class="sxs-lookup"><span data-stu-id="2500b-2468">Format</span></span>

<span data-ttu-id="2500b-2469">Dizionario</span><span class="sxs-lookup"><span data-stu-id="2500b-2469">Dictionary</span></span>

### <a name="pattern"></a><span data-ttu-id="2500b-2470">Modello</span><span class="sxs-lookup"><span data-stu-id="2500b-2470">Pattern</span></span>

<span data-ttu-id="2500b-2471">Parola chiave</span><span class="sxs-lookup"><span data-stu-id="2500b-2471">Keyword</span></span>

### <a name="checksum"></a><span data-ttu-id="2500b-2472">Checksum</span><span class="sxs-lookup"><span data-stu-id="2500b-2472">Checksum</span></span>

<span data-ttu-id="2500b-2473">No</span><span class="sxs-lookup"><span data-stu-id="2500b-2473">No</span></span>

### <a name="definition"></a><span data-ttu-id="2500b-2474">Definizione</span><span class="sxs-lookup"><span data-stu-id="2500b-2474">Definition</span></span>

<span data-ttu-id="2500b-2475">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="2500b-2475">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2500b-2476">Viene trovata una parola chiave da Dictionary_icd_10_cm.</span><span class="sxs-lookup"><span data-stu-id="2500b-2476">A keyword from Dictionary_icd_10_cm is found.</span></span>

```
      <!-- ICD-10 CM -->
      <Entity id="3356946c-6bb7-449b-b253-6ffa419c0ce7" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Dictionary_icd_10_cm" />
        </Pattern>
      </Entity>
```

<span data-ttu-id="2500b-2477">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="2500b-2477">Keywords</span></span>

<span data-ttu-id="2500b-2478">Qualsiasi termine del dizionario di parole chiave Dictionary_icd_10_cm, basato sulla [classificazione internazionale delle malattie, la decima revisione, la modifica clinica (ICD-10-cm)](https://go.microsoft.com/fwlink/?linkid=852604).</span><span class="sxs-lookup"><span data-stu-id="2500b-2478">Any term from the Dictionary_icd_10_cm keyword dictionary, which is based on the [International Classification of Diseases, Tenth Revision, Clinical Modification (ICD-10-CM)](https://go.microsoft.com/fwlink/?linkid=852604).</span></span> <span data-ttu-id="2500b-2479">Questo tipo di ricerca viene visualizzato solo per il termine, non per i codici assicurativi.</span><span class="sxs-lookup"><span data-stu-id="2500b-2479">This type looks only for the term, not the insurance codes.</span></span>

   
## <a name="international-classification-of-diseases-icd-9-cm"></a><span data-ttu-id="2500b-2480">Classificazione internazionale delle malattie (ICD-9-CM)</span><span class="sxs-lookup"><span data-stu-id="2500b-2480">International Classification of Diseases (ICD-9-CM)</span></span>

### <a name="format"></a><span data-ttu-id="2500b-2481">Formato</span><span class="sxs-lookup"><span data-stu-id="2500b-2481">Format</span></span>

<span data-ttu-id="2500b-2482">Dizionario</span><span class="sxs-lookup"><span data-stu-id="2500b-2482">Dictionary</span></span>

### <a name="pattern"></a><span data-ttu-id="2500b-2483">Modello</span><span class="sxs-lookup"><span data-stu-id="2500b-2483">Pattern</span></span>

<span data-ttu-id="2500b-2484">Parola chiave</span><span class="sxs-lookup"><span data-stu-id="2500b-2484">Keyword</span></span>

### <a name="checksum"></a><span data-ttu-id="2500b-2485">Checksum</span><span class="sxs-lookup"><span data-stu-id="2500b-2485">Checksum</span></span>

<span data-ttu-id="2500b-2486">No</span><span class="sxs-lookup"><span data-stu-id="2500b-2486">No</span></span>

### <a name="definition"></a><span data-ttu-id="2500b-2487">Definizione</span><span class="sxs-lookup"><span data-stu-id="2500b-2487">Definition</span></span>

<span data-ttu-id="2500b-2488">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="2500b-2488">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2500b-2489">Viene trovata una parola chiave da Dictionary_icd_9_cm.</span><span class="sxs-lookup"><span data-stu-id="2500b-2489">A keyword from Dictionary_icd_9_cm is found.</span></span>

```
      <Entity id="fa3f9c74-ee07-4c52-b5f2-085d6b2c0ec4" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Dictionary_icd_9_cm" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a><span data-ttu-id="2500b-2490">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="2500b-2490">Keywords</span></span>

<span data-ttu-id="2500b-2491">Qualsiasi termine del dizionario di parole chiave Dictionary_icd_9_cm, basato sulla [classificazione internazionale delle malattie, la nona revisione, la modifica clinica (ICD-9-cm)](https://go.microsoft.com/fwlink/?linkid=852605).</span><span class="sxs-lookup"><span data-stu-id="2500b-2491">Any term from the Dictionary_icd_9_cm keyword dictionary, which is based on the [International Classification of Diseases,Ninth Revision, Clinical Modification (ICD-9-CM)](https://go.microsoft.com/fwlink/?linkid=852605).</span></span> <span data-ttu-id="2500b-2492">Questo tipo di ricerca viene visualizzato solo per il termine, non per i codici assicurativi.</span><span class="sxs-lookup"><span data-stu-id="2500b-2492">This type looks only for the term, not the insurance codes.</span></span>
   
## <a name="ireland-personal-public-service-pps-number"></a><span data-ttu-id="2500b-2493">Irlanda - Numero personale di servizio pubblico (PPS)</span><span class="sxs-lookup"><span data-stu-id="2500b-2493">Ireland Personal Public Service (PPS) Number</span></span>

### <a name="format"></a><span data-ttu-id="2500b-2494">Formato</span><span class="sxs-lookup"><span data-stu-id="2500b-2494">Format</span></span>

<span data-ttu-id="2500b-2495">Formato precedente (fino al 31 dicembre 2012):</span><span class="sxs-lookup"><span data-stu-id="2500b-2495">Old format (until 31 Dec 2012):</span></span>
- <span data-ttu-id="2500b-2496">Sette cifre seguite da 1-2 lettere </span><span class="sxs-lookup"><span data-stu-id="2500b-2496">Seven digits followed by 1-2 letters</span></span> 

<span data-ttu-id="2500b-2497">Nuovo formato (1 gen 2013 e successive):</span><span class="sxs-lookup"><span data-stu-id="2500b-2497">New format (1 Jan 2013 and after):</span></span>
- <span data-ttu-id="2500b-2498">Sette cifre seguite da due lettere</span><span class="sxs-lookup"><span data-stu-id="2500b-2498">Seven digits followed by two letters</span></span>

### <a name="pattern"></a><span data-ttu-id="2500b-2499">Modello</span><span class="sxs-lookup"><span data-stu-id="2500b-2499">Pattern</span></span>

<span data-ttu-id="2500b-2500">Formato precedente (fino al 31 dicembre 2012):</span><span class="sxs-lookup"><span data-stu-id="2500b-2500">Old format (until 31 Dec 2012):</span></span>
- <span data-ttu-id="2500b-2501">Sette cifre</span><span class="sxs-lookup"><span data-stu-id="2500b-2501">Seven digits</span></span> 
- <span data-ttu-id="2500b-2502">1-2 lettere (senza distinzione tra maiuscole e minuscole)</span><span class="sxs-lookup"><span data-stu-id="2500b-2502">1-2 letters (not case sensitive)</span></span> 

<span data-ttu-id="2500b-2503">Nuovo formato (1 gen 2013 e successive):</span><span class="sxs-lookup"><span data-stu-id="2500b-2503">New format (1 Jan 2013 and after):</span></span>
- <span data-ttu-id="2500b-2504">Sette cifre</span><span class="sxs-lookup"><span data-stu-id="2500b-2504">Seven digits</span></span> 
- <span data-ttu-id="2500b-2505">Una lettera (senza distinzione tra maiuscole e minuscole) che corrisponde a una cifra di controllo alfabetica </span><span class="sxs-lookup"><span data-stu-id="2500b-2505">A letter (not case sensitive) which is an alphabetic check digit</span></span> 
- <span data-ttu-id="2500b-2506">La lettera "A" o "H" (senza distinzione tra maiuscole e minuscole)</span><span class="sxs-lookup"><span data-stu-id="2500b-2506">The letter "A" or "H" (not case sensitive)</span></span>

### <a name="checksum"></a><span data-ttu-id="2500b-2507">Checksum</span><span class="sxs-lookup"><span data-stu-id="2500b-2507">Checksum</span></span>

<span data-ttu-id="2500b-2508">Sì</span><span class="sxs-lookup"><span data-stu-id="2500b-2508">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="2500b-2509">Definizione</span><span class="sxs-lookup"><span data-stu-id="2500b-2509">Definition</span></span>

<span data-ttu-id="2500b-2510">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="2500b-2510">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2500b-2511">La funzione Func_ireland_pps trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="2500b-2511">The function Func_ireland_pps finds content that matches the pattern.</span></span>
- <span data-ttu-id="2500b-2512">Si verifica una delle situazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="2500b-2512">One of the following is true:</span></span>
    - <span data-ttu-id="2500b-2513">Viene trovata una parola chiave da Keyword_ireland_pps.</span><span class="sxs-lookup"><span data-stu-id="2500b-2513">A keyword from Keyword_ireland_pps is found.</span></span>
    - <span data-ttu-id="2500b-2514">La funzione Func_eu_date rileva una data nel formato corretto.</span><span class="sxs-lookup"><span data-stu-id="2500b-2514">The function Func_eu_date finds a date in the right date format.</span></span>
- <span data-ttu-id="2500b-2515">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="2500b-2515">The checksum passes.</span></span>

<span data-ttu-id="2500b-2516">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 65%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="2500b-2516">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2500b-2517">La funzione Func_ireland_pps trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="2500b-2517">The function Func_ireland_pps finds content that matches the pattern.</span></span>
- <span data-ttu-id="2500b-2518">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="2500b-2518">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="2500b-2519">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="2500b-2519">Keywords</span></span>

#### <a name="keywordirelandpps"></a><span data-ttu-id="2500b-2520">Keyword_ireland_pps</span><span class="sxs-lookup"><span data-stu-id="2500b-2520">Keyword_ireland_pps</span></span>

- <span data-ttu-id="2500b-2521">Numero personale di servizio pubblico</span><span class="sxs-lookup"><span data-stu-id="2500b-2521">Personal Public Service Number</span></span> 
- <span data-ttu-id="2500b-2522">Numero PPS</span><span class="sxs-lookup"><span data-stu-id="2500b-2522">PPS Number</span></span> 
- <span data-ttu-id="2500b-2523">Num. PPS
</span><span class="sxs-lookup"><span data-stu-id="2500b-2523">PPS Num</span></span> 
- <span data-ttu-id="2500b-2524">N° PPS</span><span class="sxs-lookup"><span data-stu-id="2500b-2524">PPS No.</span></span> 
- <span data-ttu-id="2500b-2525">PPS #</span><span class="sxs-lookup"><span data-stu-id="2500b-2525">PPS #</span></span> 
- <span data-ttu-id="2500b-2526">PPS</span><span class="sxs-lookup"><span data-stu-id="2500b-2526">PPS#</span></span> 
- <span data-ttu-id="2500b-2527">PPSN</span><span class="sxs-lookup"><span data-stu-id="2500b-2527">PPSN</span></span> 
- <span data-ttu-id="2500b-2528">Scheda servizi pubblici</span><span class="sxs-lookup"><span data-stu-id="2500b-2528">Public Services Card</span></span> 
- <span data-ttu-id="2500b-2529">Uimhir Phearsanta Seirbhíse Poiblí</span><span class="sxs-lookup"><span data-stu-id="2500b-2529">Uimhir Phearsanta Seirbhíse Poiblí</span></span> 
- <span data-ttu-id="2500b-2530">Uimh.</span><span class="sxs-lookup"><span data-stu-id="2500b-2530">Uimh.</span></span> <span data-ttu-id="2500b-2531">PSP</span><span class="sxs-lookup"><span data-stu-id="2500b-2531">PSP</span></span> 
- <span data-ttu-id="2500b-2532">PSP</span><span class="sxs-lookup"><span data-stu-id="2500b-2532">PSP</span></span> 
   
## <a name="israel-bank-account-number"></a><span data-ttu-id="2500b-2533">Israele - Numero di conto bancario</span><span class="sxs-lookup"><span data-stu-id="2500b-2533">Israel Bank Account Number</span></span>

### <a name="format"></a><span data-ttu-id="2500b-2534">Formato</span><span class="sxs-lookup"><span data-stu-id="2500b-2534">Format</span></span>

<span data-ttu-id="2500b-2535">13 cifre</span><span class="sxs-lookup"><span data-stu-id="2500b-2535">13 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="2500b-2536">Modello</span><span class="sxs-lookup"><span data-stu-id="2500b-2536">Pattern</span></span>

<span data-ttu-id="2500b-2537">Formattato</span><span class="sxs-lookup"><span data-stu-id="2500b-2537">Formatted:</span></span>
- <span data-ttu-id="2500b-2538">Due cifre</span><span class="sxs-lookup"><span data-stu-id="2500b-2538">Two digits</span></span> 
- <span data-ttu-id="2500b-2539">Un trattino</span><span class="sxs-lookup"><span data-stu-id="2500b-2539">A dash</span></span> 
- <span data-ttu-id="2500b-2540">Tre cifre</span><span class="sxs-lookup"><span data-stu-id="2500b-2540">Three digits</span></span> 
- <span data-ttu-id="2500b-2541">Un trattino</span><span class="sxs-lookup"><span data-stu-id="2500b-2541">A dash</span></span> 
- <span data-ttu-id="2500b-2542">Otto cifre</span><span class="sxs-lookup"><span data-stu-id="2500b-2542">Eight digits</span></span>

<span data-ttu-id="2500b-2543">Formattato</span><span class="sxs-lookup"><span data-stu-id="2500b-2543">Unformatted:</span></span>
- <span data-ttu-id="2500b-2544">13 cifre consecutive</span><span class="sxs-lookup"><span data-stu-id="2500b-2544">13 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="2500b-2545">Checksum</span><span class="sxs-lookup"><span data-stu-id="2500b-2545">Checksum</span></span>

<span data-ttu-id="2500b-2546">No</span><span class="sxs-lookup"><span data-stu-id="2500b-2546">No</span></span>

### <a name="definition"></a><span data-ttu-id="2500b-2547">Definizione</span><span class="sxs-lookup"><span data-stu-id="2500b-2547">Definition</span></span>

<span data-ttu-id="2500b-2548">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="2500b-2548">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2500b-2549">L'espressione regolare Regex_israel_bank_account_number restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="2500b-2549">The regular expression Regex_israel_bank_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="2500b-2550">Viene trovata una parola chiave da Keyword_israel_bank_account_number.</span><span class="sxs-lookup"><span data-stu-id="2500b-2550">A keyword from Keyword_israel_bank_account_number is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="2500b-2551">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="2500b-2551">Keywords</span></span>

#### <a name="keywordisraelbankaccountnumber"></a><span data-ttu-id="2500b-2552">Keyword_israel_bank_account_number</span><span class="sxs-lookup"><span data-stu-id="2500b-2552">Keyword_israel_bank_account_number</span></span>

- <span data-ttu-id="2500b-2553">Bank Account Number</span><span class="sxs-lookup"><span data-stu-id="2500b-2553">Bank Account Number</span></span> 
- <span data-ttu-id="2500b-2554">Bank Account</span><span class="sxs-lookup"><span data-stu-id="2500b-2554">Bank Account</span></span> 
- <span data-ttu-id="2500b-2555">Account Number</span><span class="sxs-lookup"><span data-stu-id="2500b-2555">Account Number</span></span> 
- <span data-ttu-id="2500b-2556">מספר חשבון בנק</span><span class="sxs-lookup"><span data-stu-id="2500b-2556">מספר חשבון בנק</span></span> 
   
## <a name="israel-national-id"></a><span data-ttu-id="2500b-2557">Carta di identità (Israele)</span><span class="sxs-lookup"><span data-stu-id="2500b-2557">Israel National ID</span></span>

### <a name="format"></a><span data-ttu-id="2500b-2558">Formato</span><span class="sxs-lookup"><span data-stu-id="2500b-2558">Format</span></span>

<span data-ttu-id="2500b-2559">9 cifre</span><span class="sxs-lookup"><span data-stu-id="2500b-2559">Nine digits</span></span>

### <a name="pattern"></a><span data-ttu-id="2500b-2560">Modello</span><span class="sxs-lookup"><span data-stu-id="2500b-2560">Pattern</span></span>

<span data-ttu-id="2500b-2561">9 cifre consecutive</span><span class="sxs-lookup"><span data-stu-id="2500b-2561">Nine consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="2500b-2562">Checksum</span><span class="sxs-lookup"><span data-stu-id="2500b-2562">Checksum</span></span>

<span data-ttu-id="2500b-2563">Sì</span><span class="sxs-lookup"><span data-stu-id="2500b-2563">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="2500b-2564">Definizione</span><span class="sxs-lookup"><span data-stu-id="2500b-2564">Definition</span></span>

<span data-ttu-id="2500b-2565">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="2500b-2565">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2500b-2566">La funzione Func_israeli_national_id_number restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="2500b-2566">The function Func_israeli_national_id_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="2500b-2567">Viene trovata una parola chiave da Keyword_Israel_National_ID.</span><span class="sxs-lookup"><span data-stu-id="2500b-2567">A keyword from Keyword_Israel_National_ID is found.</span></span>
- <span data-ttu-id="2500b-2568">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="2500b-2568">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="2500b-2569">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="2500b-2569">Keywords</span></span>

#### <a name="keywordisraelnationalid"></a><span data-ttu-id="2500b-2570">Keyword_Israel_National_ID</span><span class="sxs-lookup"><span data-stu-id="2500b-2570">Keyword_Israel_National_ID</span></span>

- <span data-ttu-id="2500b-2571">מספר זהות</span><span class="sxs-lookup"><span data-stu-id="2500b-2571">מספר זהות</span></span> 
- <span data-ttu-id="2500b-2572">National ID Number</span><span class="sxs-lookup"><span data-stu-id="2500b-2572">National ID Number</span></span>
   
## <a name="italy-drivers-license-number"></a><span data-ttu-id="2500b-2573">Italia - Numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="2500b-2573">Italy Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="2500b-2574">Formato</span><span class="sxs-lookup"><span data-stu-id="2500b-2574">Format</span></span>

<span data-ttu-id="2500b-2575">Una combinazione di 10 lettere e cifre</span><span class="sxs-lookup"><span data-stu-id="2500b-2575">A combination of 10 letters and digits</span></span>

### <a name="pattern"></a><span data-ttu-id="2500b-2576">Modello</span><span class="sxs-lookup"><span data-stu-id="2500b-2576">Pattern</span></span>

- <span data-ttu-id="2500b-2577">Una combinazione di 10 lettere e cifre:</span><span class="sxs-lookup"><span data-stu-id="2500b-2577">A combination of 10 letters and digits:</span></span>
- <span data-ttu-id="2500b-2578">Una lettera (senza distinzione tra maiuscole/minuscole)</span><span class="sxs-lookup"><span data-stu-id="2500b-2578">One letter (not case sensitive)</span></span> 
- <span data-ttu-id="2500b-2579">La lettera "A" o "V" (senza distinzione tra maiuscole/minuscole)</span><span class="sxs-lookup"><span data-stu-id="2500b-2579">The letter "A" or "V" (not case sensitive)</span></span> 
- <span data-ttu-id="2500b-2580">7 lettere (senza distinzione tra maiuscole/minuscole), cifre o carattere di sottolineatura</span><span class="sxs-lookup"><span data-stu-id="2500b-2580">Seven letters (not case sensitive), digits, or the underscore character</span></span> 
- <span data-ttu-id="2500b-2581">Una lettera (senza distinzione tra maiuscole/minuscole)</span><span class="sxs-lookup"><span data-stu-id="2500b-2581">One letter (not case sensitive)</span></span>

### <a name="checksum"></a><span data-ttu-id="2500b-2582">Checksum</span><span class="sxs-lookup"><span data-stu-id="2500b-2582">Checksum</span></span>

<span data-ttu-id="2500b-2583">No</span><span class="sxs-lookup"><span data-stu-id="2500b-2583">No</span></span>

### <a name="definition"></a><span data-ttu-id="2500b-2584">Definizione</span><span class="sxs-lookup"><span data-stu-id="2500b-2584">Definition</span></span>

<span data-ttu-id="2500b-2585">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="2500b-2585">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2500b-2586">L'espressione regolare Regex_italy_drivers_license_number restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="2500b-2586">The regular expression Regex_italy_drivers_license_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="2500b-2587">Viene trovata una parola chiave da Keyword_italy_drivers_license_number.</span><span class="sxs-lookup"><span data-stu-id="2500b-2587">A keyword from Keyword_italy_drivers_license_number is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="2500b-2588">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="2500b-2588">Keywords</span></span>

#### <a name="keyworditalydriverslicensenumber"></a><span data-ttu-id="2500b-2589">Keyword_italy_drivers_license_number</span><span class="sxs-lookup"><span data-stu-id="2500b-2589">Keyword_italy_drivers_license_number</span></span>

- <span data-ttu-id="2500b-2590">numero di patente di guida</span><span class="sxs-lookup"><span data-stu-id="2500b-2590">numero di patente di guida</span></span> 
- <span data-ttu-id="2500b-2591">patente di guida</span><span class="sxs-lookup"><span data-stu-id="2500b-2591">patente di guida</span></span> 
   
## <a name="japan-bank-account-number"></a><span data-ttu-id="2500b-2592">Giappone - Numero di conto bancario</span><span class="sxs-lookup"><span data-stu-id="2500b-2592">Japan Bank Account Number</span></span>

### <a name="format"></a><span data-ttu-id="2500b-2593">Formato</span><span class="sxs-lookup"><span data-stu-id="2500b-2593">Format</span></span>

<span data-ttu-id="2500b-2594">Sette o otto cifre</span><span class="sxs-lookup"><span data-stu-id="2500b-2594">Seven or eight digits</span></span>

### <a name="pattern"></a><span data-ttu-id="2500b-2595">Modello</span><span class="sxs-lookup"><span data-stu-id="2500b-2595">Pattern</span></span>

<span data-ttu-id="2500b-2596">Numero di conto corrente:</span><span class="sxs-lookup"><span data-stu-id="2500b-2596">Bank account number:</span></span>
- <span data-ttu-id="2500b-2597">Sette o otto cifre</span><span class="sxs-lookup"><span data-stu-id="2500b-2597">Seven or eight digits</span></span>
- <span data-ttu-id="2500b-2598">Codice della filiale del conto corrente:</span><span class="sxs-lookup"><span data-stu-id="2500b-2598">Bank account branch code:</span></span>
- <span data-ttu-id="2500b-2599">Quattro cifre</span><span class="sxs-lookup"><span data-stu-id="2500b-2599">Four digits</span></span> 
- <span data-ttu-id="2500b-2600">Uno spazio o un trattino (facoltativo)</span><span class="sxs-lookup"><span data-stu-id="2500b-2600">A space or dash (optional)</span></span> 
- <span data-ttu-id="2500b-2601">Tre cifre</span><span class="sxs-lookup"><span data-stu-id="2500b-2601">Three digits</span></span>

<span data-ttu-id="2500b-2602">Checksum</span><span class="sxs-lookup"><span data-stu-id="2500b-2602">Checksum</span></span>

<span data-ttu-id="2500b-2603">No</span><span class="sxs-lookup"><span data-stu-id="2500b-2603">No</span></span>

### <a name="definition"></a><span data-ttu-id="2500b-2604">Definizione</span><span class="sxs-lookup"><span data-stu-id="2500b-2604">Definition</span></span>

<span data-ttu-id="2500b-2605">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="2500b-2605">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2500b-2606">La funzione Func_jp_bank_account restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="2500b-2606">The function Func_jp_bank_account finds content that matches the pattern.</span></span>
- <span data-ttu-id="2500b-2607">Viene trovata una parola chiave da Keyword_jp_bank_account.</span><span class="sxs-lookup"><span data-stu-id="2500b-2607">A keyword from Keyword_jp_bank_account is found.</span></span>
- <span data-ttu-id="2500b-2608">Si verifica una delle situazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="2500b-2608">One of the following is true:</span></span>
- <span data-ttu-id="2500b-2609">La funzione Func_jp_bank_account_branch_code restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="2500b-2609">The function Func_jp_bank_account_branch_code finds content that matches the pattern.</span></span>
- <span data-ttu-id="2500b-2610">Viene trovata una parola chiave da Keyword_jp_bank_branch_code.</span><span class="sxs-lookup"><span data-stu-id="2500b-2610">A keyword from Keyword_jp_bank_branch_code is found.</span></span>

<span data-ttu-id="2500b-2611">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="2500b-2611">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2500b-2612">La funzione Func_jp_bank_account restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="2500b-2612">The function Func_jp_bank_account finds content that matches the pattern.</span></span>
- <span data-ttu-id="2500b-2613">Viene trovata una parola chiave da Keyword_jp_bank_account.</span><span class="sxs-lookup"><span data-stu-id="2500b-2613">A keyword from Keyword_jp_bank_account is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="2500b-2614">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="2500b-2614">Keywords</span></span>

#### <a name="keywordjpbankaccount"></a><span data-ttu-id="2500b-2615">Keyword_jp_bank_account</span><span class="sxs-lookup"><span data-stu-id="2500b-2615">Keyword_jp_bank_account</span></span>

- <span data-ttu-id="2500b-2616">Checking Account Number</span><span class="sxs-lookup"><span data-stu-id="2500b-2616">Checking Account Number</span></span> 
- <span data-ttu-id="2500b-2617">Checking Account</span><span class="sxs-lookup"><span data-stu-id="2500b-2617">Checking Account</span></span> 
- <span data-ttu-id="2500b-2618">Checking Account #</span><span class="sxs-lookup"><span data-stu-id="2500b-2618">Checking Account #</span></span> 
- <span data-ttu-id="2500b-2619">Checking Acct Number</span><span class="sxs-lookup"><span data-stu-id="2500b-2619">Checking Acct Number</span></span> 
- <span data-ttu-id="2500b-2620">Checking Acct #</span><span class="sxs-lookup"><span data-stu-id="2500b-2620">Checking Acct #</span></span> 
- <span data-ttu-id="2500b-2621">Checking Acct No.</span><span class="sxs-lookup"><span data-stu-id="2500b-2621">Checking Acct No.</span></span> 
- <span data-ttu-id="2500b-2622">Checking Account No.</span><span class="sxs-lookup"><span data-stu-id="2500b-2622">Checking Account No.</span></span> 
- <span data-ttu-id="2500b-2623">Bank Account Number</span><span class="sxs-lookup"><span data-stu-id="2500b-2623">Bank Account Number</span></span> 
- <span data-ttu-id="2500b-2624">Bank Account</span><span class="sxs-lookup"><span data-stu-id="2500b-2624">Bank Account</span></span> 
- <span data-ttu-id="2500b-2625">Bank Account #</span><span class="sxs-lookup"><span data-stu-id="2500b-2625">Bank Account #</span></span> 
- <span data-ttu-id="2500b-2626">Bank Acct Number</span><span class="sxs-lookup"><span data-stu-id="2500b-2626">Bank Acct Number</span></span> 
- <span data-ttu-id="2500b-2627">Bank Acct #</span><span class="sxs-lookup"><span data-stu-id="2500b-2627">Bank Acct #</span></span> 
- <span data-ttu-id="2500b-2628">Bank Acct No.</span><span class="sxs-lookup"><span data-stu-id="2500b-2628">Bank Acct No.</span></span> 
- <span data-ttu-id="2500b-2629">Bank Account No.</span><span class="sxs-lookup"><span data-stu-id="2500b-2629">Bank Account No.</span></span> 
- <span data-ttu-id="2500b-2630">Savings Account Number</span><span class="sxs-lookup"><span data-stu-id="2500b-2630">Savings Account Number</span></span> 
- <span data-ttu-id="2500b-2631">Savings Account</span><span class="sxs-lookup"><span data-stu-id="2500b-2631">Savings Account</span></span> 
- <span data-ttu-id="2500b-2632">Savings Account #</span><span class="sxs-lookup"><span data-stu-id="2500b-2632">Savings Account #</span></span> 
- <span data-ttu-id="2500b-2633">Savings Acct Number</span><span class="sxs-lookup"><span data-stu-id="2500b-2633">Savings Acct Number</span></span> 
- <span data-ttu-id="2500b-2634">Savings Acct #</span><span class="sxs-lookup"><span data-stu-id="2500b-2634">Savings Acct #</span></span> 
- <span data-ttu-id="2500b-2635">Savings Acct No.</span><span class="sxs-lookup"><span data-stu-id="2500b-2635">Savings Acct No.</span></span> 
- <span data-ttu-id="2500b-2636">Savings Account No.</span><span class="sxs-lookup"><span data-stu-id="2500b-2636">Savings Account No.</span></span> 
- <span data-ttu-id="2500b-2637">Debit Account Number</span><span class="sxs-lookup"><span data-stu-id="2500b-2637">Debit Account Number</span></span> 
- <span data-ttu-id="2500b-2638">Debit Account</span><span class="sxs-lookup"><span data-stu-id="2500b-2638">Debit Account</span></span> 
- <span data-ttu-id="2500b-2639">Debit Account #</span><span class="sxs-lookup"><span data-stu-id="2500b-2639">Debit Account #</span></span> 
- <span data-ttu-id="2500b-2640">Debit Acct Number</span><span class="sxs-lookup"><span data-stu-id="2500b-2640">Debit Acct Number</span></span> 
- <span data-ttu-id="2500b-2641">Debit Acct #</span><span class="sxs-lookup"><span data-stu-id="2500b-2641">Debit Acct #</span></span> 
- <span data-ttu-id="2500b-2642">Debit Acct No.</span><span class="sxs-lookup"><span data-stu-id="2500b-2642">Debit Acct No.</span></span> 
- <span data-ttu-id="2500b-2643">Debit Account No.</span><span class="sxs-lookup"><span data-stu-id="2500b-2643">Debit Account No.</span></span> 
- <span data-ttu-id="2500b-2644">口座番号を当座預金口座の確認</span><span class="sxs-lookup"><span data-stu-id="2500b-2644">口座番号を当座預金口座の確認</span></span> 
- <span data-ttu-id="2500b-2645">#アカウントの確認 、 勘定番号の確認</span><span class="sxs-lookup"><span data-stu-id="2500b-2645">＃アカウントの確認、勘定番号の確認</span></span> 
- <span data-ttu-id="2500b-2646">#勘定の確認</span><span class="sxs-lookup"><span data-stu-id="2500b-2646">＃勘定の確認</span></span> 
- <span data-ttu-id="2500b-2647">勘定番号の確認</span><span class="sxs-lookup"><span data-stu-id="2500b-2647">勘定番号の確認</span></span> 
- <span data-ttu-id="2500b-2648">口座番号の確認</span><span class="sxs-lookup"><span data-stu-id="2500b-2648">口座番号の確認</span></span> 
- <span data-ttu-id="2500b-2649">銀行口座番号</span><span class="sxs-lookup"><span data-stu-id="2500b-2649">銀行口座番号</span></span> 
- <span data-ttu-id="2500b-2650">銀行口座</span><span class="sxs-lookup"><span data-stu-id="2500b-2650">銀行口座</span></span> 
- <span data-ttu-id="2500b-2651">銀行口座＃</span><span class="sxs-lookup"><span data-stu-id="2500b-2651">銀行口座＃</span></span> 
- <span data-ttu-id="2500b-2652">銀行の勘定番号</span><span class="sxs-lookup"><span data-stu-id="2500b-2652">銀行の勘定番号</span></span> 
- <span data-ttu-id="2500b-2653">銀行のacct＃</span><span class="sxs-lookup"><span data-stu-id="2500b-2653">銀行のacct＃</span></span> 
- <span data-ttu-id="2500b-2654">銀行の勘定いいえ</span><span class="sxs-lookup"><span data-stu-id="2500b-2654">銀行の勘定いいえ</span></span> 
- <span data-ttu-id="2500b-2655">銀行口座番号</span><span class="sxs-lookup"><span data-stu-id="2500b-2655">銀行口座番号</span></span>
- <span data-ttu-id="2500b-2656">普通預金口座番号</span><span class="sxs-lookup"><span data-stu-id="2500b-2656">普通預金口座番号</span></span> 
- <span data-ttu-id="2500b-2657">預金口座</span><span class="sxs-lookup"><span data-stu-id="2500b-2657">預金口座</span></span> 
- <span data-ttu-id="2500b-2658">貯蓄口座＃</span><span class="sxs-lookup"><span data-stu-id="2500b-2658">貯蓄口座＃</span></span> 
- <span data-ttu-id="2500b-2659">貯蓄勘定の数</span><span class="sxs-lookup"><span data-stu-id="2500b-2659">貯蓄勘定の数</span></span> 
- <span data-ttu-id="2500b-2660">貯蓄勘定＃</span><span class="sxs-lookup"><span data-stu-id="2500b-2660">貯蓄勘定＃</span></span> 
- <span data-ttu-id="2500b-2661">貯蓄勘定番号</span><span class="sxs-lookup"><span data-stu-id="2500b-2661">貯蓄勘定番号</span></span> 
- <span data-ttu-id="2500b-2662">普通預金口座番号</span><span class="sxs-lookup"><span data-stu-id="2500b-2662">普通預金口座番号</span></span> 
- <span data-ttu-id="2500b-2663">引き落とし口座番号</span><span class="sxs-lookup"><span data-stu-id="2500b-2663">引き落とし口座番号</span></span> 
- <span data-ttu-id="2500b-2664">口座番号</span><span class="sxs-lookup"><span data-stu-id="2500b-2664">口座番号</span></span> 
- <span data-ttu-id="2500b-2665">口座番号＃</span><span class="sxs-lookup"><span data-stu-id="2500b-2665">口座番号＃</span></span> 
- <span data-ttu-id="2500b-2666">デビットのacct番号</span><span class="sxs-lookup"><span data-stu-id="2500b-2666">デビットのacct番号</span></span> 
- <span data-ttu-id="2500b-2667">デビット勘定＃</span><span class="sxs-lookup"><span data-stu-id="2500b-2667">デビット勘定＃</span></span> 
- <span data-ttu-id="2500b-2668">デビットACCTの番号</span><span class="sxs-lookup"><span data-stu-id="2500b-2668">デビットACCTの番号</span></span> 
- <span data-ttu-id="2500b-2669">デビット口座番号</span><span class="sxs-lookup"><span data-stu-id="2500b-2669">デビット口座番号</span></span> 

#### <a name="keywordjpbankbranchcode"></a><span data-ttu-id="2500b-2670">Keyword_jp_bank_branch_code</span><span class="sxs-lookup"><span data-stu-id="2500b-2670">Keyword_jp_bank_branch_code</span></span>

<span data-ttu-id="2500b-2671">Otemachi</span><span class="sxs-lookup"><span data-stu-id="2500b-2671">Otemachi</span></span>

## <a name="japan-drivers-license-number"></a><span data-ttu-id="2500b-2672">Giappone - Numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="2500b-2672">Japan Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="2500b-2673">Formato</span><span class="sxs-lookup"><span data-stu-id="2500b-2673">Format</span></span>

<span data-ttu-id="2500b-2674">12 cifre</span><span class="sxs-lookup"><span data-stu-id="2500b-2674">12 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="2500b-2675">Modello</span><span class="sxs-lookup"><span data-stu-id="2500b-2675">Pattern</span></span>

<span data-ttu-id="2500b-2676">12 cifre consecutive</span><span class="sxs-lookup"><span data-stu-id="2500b-2676">12 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="2500b-2677">Checksum</span><span class="sxs-lookup"><span data-stu-id="2500b-2677">Checksum</span></span>

<span data-ttu-id="2500b-2678">No</span><span class="sxs-lookup"><span data-stu-id="2500b-2678">No</span></span>

### <a name="definition"></a><span data-ttu-id="2500b-2679">Definizione</span><span class="sxs-lookup"><span data-stu-id="2500b-2679">Definition</span></span>

<span data-ttu-id="2500b-2680">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="2500b-2680">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2500b-2681">La funzione Func_jp_drivers_license_number restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="2500b-2681">The function Func_jp_drivers_license_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="2500b-2682">Viene trovata una parola chiave da Keyword_jp_drivers_license_number.</span><span class="sxs-lookup"><span data-stu-id="2500b-2682">A keyword from Keyword_jp_drivers_license_number is found.</span></span>

```
<!-- Japan Driver's License Number -->
<Entity id="c6011143-d087-451c-8313-7f6d4aed2270" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_jp_drivers_license_number" />
        <Match idRef ="Keyword_jp_drivers_license_number" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="2500b-2683">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="2500b-2683">Keywords</span></span>

#### <a name="keywordjpdriverslicensenumber"></a><span data-ttu-id="2500b-2684">Keyword_jp_drivers_license_number</span><span class="sxs-lookup"><span data-stu-id="2500b-2684">Keyword_jp_drivers_license_number</span></span>

- <span data-ttu-id="2500b-2685">DL</span><span class="sxs-lookup"><span data-stu-id="2500b-2685">dl#</span></span> 
- <span data-ttu-id="2500b-2686">DL</span><span class="sxs-lookup"><span data-stu-id="2500b-2686">DL＃</span></span> 
- <span data-ttu-id="2500b-2687">DLS</span><span class="sxs-lookup"><span data-stu-id="2500b-2687">dls#</span></span> 
- <span data-ttu-id="2500b-2688">DLS</span><span class="sxs-lookup"><span data-stu-id="2500b-2688">DLS＃</span></span> 
- <span data-ttu-id="2500b-2689">driver license</span><span class="sxs-lookup"><span data-stu-id="2500b-2689">driver license</span></span> 
- <span data-ttu-id="2500b-2690">driver licenses</span><span class="sxs-lookup"><span data-stu-id="2500b-2690">driver licenses</span></span> 
- <span data-ttu-id="2500b-2691">drivers license</span><span class="sxs-lookup"><span data-stu-id="2500b-2691">drivers license</span></span> 
- <span data-ttu-id="2500b-2692">driver's license</span><span class="sxs-lookup"><span data-stu-id="2500b-2692">driver's license</span></span> 
- <span data-ttu-id="2500b-2693">drivers licenses</span><span class="sxs-lookup"><span data-stu-id="2500b-2693">drivers licenses</span></span> 
- <span data-ttu-id="2500b-2694">driver's licenses</span><span class="sxs-lookup"><span data-stu-id="2500b-2694">driver's licenses</span></span> 
- <span data-ttu-id="2500b-2695">driving licence</span><span class="sxs-lookup"><span data-stu-id="2500b-2695">driving licence</span></span> 
- <span data-ttu-id="2500b-2696">driver'lic</span><span class="sxs-lookup"><span data-stu-id="2500b-2696">lic#</span></span> 
- <span data-ttu-id="2500b-2697">DRIVER'LIC</span><span class="sxs-lookup"><span data-stu-id="2500b-2697">LIC＃</span></span> 
- <span data-ttu-id="2500b-2698">driver'lics</span><span class="sxs-lookup"><span data-stu-id="2500b-2698">lics#</span></span> 
- <span data-ttu-id="2500b-2699">state id</span><span class="sxs-lookup"><span data-stu-id="2500b-2699">state id</span></span> 
- <span data-ttu-id="2500b-2700">state identification</span><span class="sxs-lookup"><span data-stu-id="2500b-2700">state identification</span></span> 
- <span data-ttu-id="2500b-2701">state identification number</span><span class="sxs-lookup"><span data-stu-id="2500b-2701">state identification number</span></span> 
- <span data-ttu-id="2500b-2702">低所得国＃</span><span class="sxs-lookup"><span data-stu-id="2500b-2702">低所得国＃</span></span> 
- <span data-ttu-id="2500b-2703">免許証</span><span class="sxs-lookup"><span data-stu-id="2500b-2703">免許証</span></span> 
- <span data-ttu-id="2500b-2704">状態ID</span><span class="sxs-lookup"><span data-stu-id="2500b-2704">状態ID</span></span>
- <span data-ttu-id="2500b-2705">状態の識別</span><span class="sxs-lookup"><span data-stu-id="2500b-2705">状態の識別</span></span> 
- <span data-ttu-id="2500b-2706">状態の識別番号</span><span class="sxs-lookup"><span data-stu-id="2500b-2706">状態の識別番号</span></span> 
- <span data-ttu-id="2500b-2707">運転免許</span><span class="sxs-lookup"><span data-stu-id="2500b-2707">運転免許</span></span> 
- <span data-ttu-id="2500b-2708">運転免許証</span><span class="sxs-lookup"><span data-stu-id="2500b-2708">運転免許証</span></span> 
- <span data-ttu-id="2500b-2709">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="2500b-2709">運転免許証番号</span></span> 
   
## <a name="japan-passport-number"></a><span data-ttu-id="2500b-2710">Giappone - Numero di passaporto</span><span class="sxs-lookup"><span data-stu-id="2500b-2710">Japan Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="2500b-2711">Formato</span><span class="sxs-lookup"><span data-stu-id="2500b-2711">Format</span></span>

<span data-ttu-id="2500b-2712">Due lettere seguite da 7 cifre</span><span class="sxs-lookup"><span data-stu-id="2500b-2712">Two letters followed by seven digits</span></span>

### <a name="pattern"></a><span data-ttu-id="2500b-2713">Modello</span><span class="sxs-lookup"><span data-stu-id="2500b-2713">Pattern</span></span>

<span data-ttu-id="2500b-2714">Due lettere (senza distinzione tra maiuscole/minuscole) seguite da sette cifre</span><span class="sxs-lookup"><span data-stu-id="2500b-2714">Two letters (not case sensitive) followed by seven digits</span></span>

### <a name="checksum"></a><span data-ttu-id="2500b-2715">Checksum</span><span class="sxs-lookup"><span data-stu-id="2500b-2715">Checksum</span></span>

<span data-ttu-id="2500b-2716">No</span><span class="sxs-lookup"><span data-stu-id="2500b-2716">No</span></span>

### <a name="definition"></a><span data-ttu-id="2500b-2717">Definizione</span><span class="sxs-lookup"><span data-stu-id="2500b-2717">Definition</span></span>

<span data-ttu-id="2500b-2718">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="2500b-2718">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2500b-2719">La funzione Func_jp_passport restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="2500b-2719">The function Func_jp_passport finds content that matches the pattern.</span></span>
- <span data-ttu-id="2500b-2720">Viene trovata una parola chiave da Keyword_jp_passport.</span><span class="sxs-lookup"><span data-stu-id="2500b-2720">A keyword from Keyword_jp_passport is found.</span></span>

```
<!-- Japan Passport Number -->
<Entity id="75177310-1a09-4613-bf6d-833aae3743f8" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_jp_passport" />
        <Match idRef="Keyword_jp_passport" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="2500b-2721">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="2500b-2721">Keywords</span></span>

#### <a name="keywordjppassport"></a><span data-ttu-id="2500b-2722">Keyword_jp_passport</span><span class="sxs-lookup"><span data-stu-id="2500b-2722">Keyword_jp_passport</span></span>

- <span data-ttu-id="2500b-2723">パスポート</span><span class="sxs-lookup"><span data-stu-id="2500b-2723">パスポート</span></span> 
- <span data-ttu-id="2500b-2724">パスポート番号</span><span class="sxs-lookup"><span data-stu-id="2500b-2724">パスポート番号</span></span> 
- <span data-ttu-id="2500b-2725">パスポートのNum</span><span class="sxs-lookup"><span data-stu-id="2500b-2725">パスポートのNum</span></span> 
- <span data-ttu-id="2500b-2726">パスポート＃</span><span class="sxs-lookup"><span data-stu-id="2500b-2726">パスポート＃</span></span> 
   
## <a name="japan-resident-registration-number"></a><span data-ttu-id="2500b-2727">Giappone - Numero di registrazione dei residenti</span><span class="sxs-lookup"><span data-stu-id="2500b-2727">Japan Resident Registration Number</span></span>

### <a name="format"></a><span data-ttu-id="2500b-2728">Formato</span><span class="sxs-lookup"><span data-stu-id="2500b-2728">Format</span></span>

<span data-ttu-id="2500b-2729">11 cifre</span><span class="sxs-lookup"><span data-stu-id="2500b-2729">11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="2500b-2730">Modello</span><span class="sxs-lookup"><span data-stu-id="2500b-2730">Pattern</span></span>

<span data-ttu-id="2500b-2731">11 cifre consecutive</span><span class="sxs-lookup"><span data-stu-id="2500b-2731">11 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="2500b-2732">Checksum</span><span class="sxs-lookup"><span data-stu-id="2500b-2732">Checksum</span></span>

<span data-ttu-id="2500b-2733">No</span><span class="sxs-lookup"><span data-stu-id="2500b-2733">No</span></span>

### <a name="definition"></a><span data-ttu-id="2500b-2734">Definizione</span><span class="sxs-lookup"><span data-stu-id="2500b-2734">Definition</span></span>

<span data-ttu-id="2500b-2735">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="2500b-2735">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2500b-2736">La funzione Func_jp_resident_registration_number restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="2500b-2736">The function Func_jp_resident_registration_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="2500b-2737">Viene trovata una parola chiave da Keyword_jp_resident_registration_number.</span><span class="sxs-lookup"><span data-stu-id="2500b-2737">A keyword from Keyword_jp_resident_registration_number is found.</span></span>

```
<!-- Japan Resident Registration Number -->
<Entity id="01c1209b-6389-4faf-a5f8-3f7e13899652" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_jp_resident_registration_number" />
        <Match idRef ="Keyword_jp_resident_registration_number" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="2500b-2738">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="2500b-2738">Keywords</span></span>

#### <a name="keywordjpresidentregistrationnumber"></a><span data-ttu-id="2500b-2739">Keyword_jp_resident_registration_number</span><span class="sxs-lookup"><span data-stu-id="2500b-2739">Keyword_jp_resident_registration_number</span></span>

- <span data-ttu-id="2500b-2740">Resident Registration Number</span><span class="sxs-lookup"><span data-stu-id="2500b-2740">Resident Registration Number</span></span>
- <span data-ttu-id="2500b-2741">Resident Register Number</span><span class="sxs-lookup"><span data-stu-id="2500b-2741">Resident Register Number</span></span> 
- <span data-ttu-id="2500b-2742">Residents Basic Registry Number</span><span class="sxs-lookup"><span data-stu-id="2500b-2742">Residents Basic Registry Number</span></span> 
- <span data-ttu-id="2500b-2743">Resident Registration No.</span><span class="sxs-lookup"><span data-stu-id="2500b-2743">Resident Registration No.</span></span> 
- <span data-ttu-id="2500b-2744">Resident Register No.</span><span class="sxs-lookup"><span data-stu-id="2500b-2744">Resident Register No.</span></span> 
- <span data-ttu-id="2500b-2745">Residents Basic Registry No.</span><span class="sxs-lookup"><span data-stu-id="2500b-2745">Residents Basic Registry No.</span></span> 
- <span data-ttu-id="2500b-2746">Basic Resident Register No.</span><span class="sxs-lookup"><span data-stu-id="2500b-2746">Basic Resident Register No.</span></span> 
- <span data-ttu-id="2500b-2747">住民登録番号、登録番号をレジデント</span><span class="sxs-lookup"><span data-stu-id="2500b-2747">住民登録番号、登録番号をレジデント</span></span> 
- <span data-ttu-id="2500b-2748">住民基本登録番号、登録番号</span><span class="sxs-lookup"><span data-stu-id="2500b-2748">住民基本登録番号、登録番号</span></span> 
- <span data-ttu-id="2500b-2749">住民基本レジストリ番号を常駐</span><span class="sxs-lookup"><span data-stu-id="2500b-2749">住民基本レジストリ番号を常駐</span></span> 
- <span data-ttu-id="2500b-2750">登録番号を常駐住民基本台帳登録番号</span><span class="sxs-lookup"><span data-stu-id="2500b-2750">登録番号を常駐住民基本台帳登録番号</span></span> 

   
## <a name="japan-social-insurance-number-sin"></a><span data-ttu-id="2500b-2751">Giappone - Numero di assicurazione sociale (SIN)</span><span class="sxs-lookup"><span data-stu-id="2500b-2751">Japan Social Insurance Number (SIN)</span></span>

### <a name="format"></a><span data-ttu-id="2500b-2752">Formato</span><span class="sxs-lookup"><span data-stu-id="2500b-2752">Format</span></span>

<span data-ttu-id="2500b-2753">7-12 cifre</span><span class="sxs-lookup"><span data-stu-id="2500b-2753">7-12 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="2500b-2754">Modello</span><span class="sxs-lookup"><span data-stu-id="2500b-2754">Pattern</span></span>

<span data-ttu-id="2500b-2755">7-12 cifre:</span><span class="sxs-lookup"><span data-stu-id="2500b-2755">7-12 digits:</span></span>
- <span data-ttu-id="2500b-2756">Quattro cifre</span><span class="sxs-lookup"><span data-stu-id="2500b-2756">Four digits</span></span> 
- <span data-ttu-id="2500b-2757">Una lineetta (facoltativa)</span><span class="sxs-lookup"><span data-stu-id="2500b-2757">A hyphen (optional)</span></span> 
- <span data-ttu-id="2500b-2758">Sei cifre o</span><span class="sxs-lookup"><span data-stu-id="2500b-2758">Six digits OR</span></span>
- <span data-ttu-id="2500b-2759">7-12 cifre consecutive</span><span class="sxs-lookup"><span data-stu-id="2500b-2759">7-12 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="2500b-2760">Checksum</span><span class="sxs-lookup"><span data-stu-id="2500b-2760">Checksum</span></span>

<span data-ttu-id="2500b-2761">No</span><span class="sxs-lookup"><span data-stu-id="2500b-2761">No</span></span>

### <a name="definition"></a><span data-ttu-id="2500b-2762">Definizione</span><span class="sxs-lookup"><span data-stu-id="2500b-2762">Definition</span></span>

<span data-ttu-id="2500b-2763">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="2500b-2763">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2500b-2764">La funzione Func_jp_sin restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="2500b-2764">The function Func_jp_sin finds content that matches the pattern.</span></span>
- <span data-ttu-id="2500b-2765">Viene trovata una parola chiave da Keyword_jp_sin.</span><span class="sxs-lookup"><span data-stu-id="2500b-2765">A keyword from Keyword_jp_sin is found.</span></span>

<span data-ttu-id="2500b-2766">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="2500b-2766">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2500b-2767">La funzione Func_jp_sin_pre_1997 restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="2500b-2767">The function Func_jp_sin_pre_1997 finds content that matches the pattern.</span></span>
- <span data-ttu-id="2500b-2768">Viene trovata una parola chiave da Keyword_jp_sin.</span><span class="sxs-lookup"><span data-stu-id="2500b-2768">A keyword from Keyword_jp_sin is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="2500b-2769">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="2500b-2769">Keywords</span></span>

#### <a name="keywordjpsin"></a><span data-ttu-id="2500b-2770">Keyword_jp_sin</span><span class="sxs-lookup"><span data-stu-id="2500b-2770">Keyword_jp_sin</span></span>

- <span data-ttu-id="2500b-2771">Social Insurance No.</span><span class="sxs-lookup"><span data-stu-id="2500b-2771">Social Insurance No.</span></span> 
- <span data-ttu-id="2500b-2772">Social Insurance Num</span><span class="sxs-lookup"><span data-stu-id="2500b-2772">Social Insurance Num</span></span> 
- <span data-ttu-id="2500b-2773">Social Insurance Number</span><span class="sxs-lookup"><span data-stu-id="2500b-2773">Social Insurance Number</span></span> 
- <span data-ttu-id="2500b-2774">社会保険のテンキー</span><span class="sxs-lookup"><span data-stu-id="2500b-2774">社会保険のテンキー</span></span> 
- <span data-ttu-id="2500b-2775">社会保険番号</span><span class="sxs-lookup"><span data-stu-id="2500b-2775">社会保険番号</span></span> 

## <a name="japanese-residence-card-number"></a><span data-ttu-id="2500b-2776">Numero di carta di soggiorno giapponese</span><span class="sxs-lookup"><span data-stu-id="2500b-2776">Japanese Residence Card Number</span></span>

### <a name="format"></a><span data-ttu-id="2500b-2777">Formato</span><span class="sxs-lookup"><span data-stu-id="2500b-2777">Format</span></span>

<span data-ttu-id="2500b-2778">12 lettere e cifre</span><span class="sxs-lookup"><span data-stu-id="2500b-2778">12 letters and digits</span></span>

### <a name="pattern"></a><span data-ttu-id="2500b-2779">Modello</span><span class="sxs-lookup"><span data-stu-id="2500b-2779">Pattern</span></span>

<span data-ttu-id="2500b-2780">12 lettere e cifre:</span><span class="sxs-lookup"><span data-stu-id="2500b-2780">12 letters and digits:</span></span>
- <span data-ttu-id="2500b-2781">Due lettere (senza distinzione tra maiuscole/minuscole)</span><span class="sxs-lookup"><span data-stu-id="2500b-2781">Two letters (not case sensitive)</span></span>
- <span data-ttu-id="2500b-2782">Otto cifre</span><span class="sxs-lookup"><span data-stu-id="2500b-2782">Eight digits</span></span> 
- <span data-ttu-id="2500b-2783">Due lettere (senza distinzione tra maiuscole/minuscole)</span><span class="sxs-lookup"><span data-stu-id="2500b-2783">Two letters (not case sensitive)</span></span>

### <a name="checksum"></a><span data-ttu-id="2500b-2784">Checksum</span><span class="sxs-lookup"><span data-stu-id="2500b-2784">Checksum</span></span>

<span data-ttu-id="2500b-2785">No</span><span class="sxs-lookup"><span data-stu-id="2500b-2785">No</span></span>

### <a name="definition"></a><span data-ttu-id="2500b-2786">Definizione</span><span class="sxs-lookup"><span data-stu-id="2500b-2786">Definition</span></span>

<span data-ttu-id="2500b-2787">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="2500b-2787">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2500b-2788">L'espressione regolare Regex_jp_residence_card_number trova il contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="2500b-2788">The regular expression Regex_jp_residence_card_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="2500b-2789">Viene trovata una parola chiave da Keyword_jp_residence_card_number.</span><span class="sxs-lookup"><span data-stu-id="2500b-2789">A keyword from Keyword_jp_residence_card_number is found.</span></span>

```
<!--Japan Residence Card Number-->
-<Entity id="ac36fef2-a289-4e2c-bb48-b02366e89fc0" recommendedConfidence="75" patternsProximity="300">
   -<Pattern confidenceLevel="75">
      <IdMatch idRef="Regex_jp_residence_card_number"/>
      <Match idRef="Keyword_jp_residence_card_number"/>
   </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="2500b-2790">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="2500b-2790">Keywords</span></span>

#### <a name="keywordjpresidencecardnumber"></a><span data-ttu-id="2500b-2791">Keyword_jp_residence_card_number</span><span class="sxs-lookup"><span data-stu-id="2500b-2791">Keyword_jp_residence_card_number</span></span>

- <span data-ttu-id="2500b-2792">Numero di carta di soggiorno</span><span class="sxs-lookup"><span data-stu-id="2500b-2792">Residence card number</span></span>
- <span data-ttu-id="2500b-2793">Carta di soggiorno No</span><span class="sxs-lookup"><span data-stu-id="2500b-2793">Residence card no</span></span>
- <span data-ttu-id="2500b-2794">Carta di soggiorno #</span><span class="sxs-lookup"><span data-stu-id="2500b-2794">Residence card #</span></span>
- <span data-ttu-id="2500b-2795">在留カード番号</span><span class="sxs-lookup"><span data-stu-id="2500b-2795">在留カード番号</span></span>
   
## <a name="malaysia-id-card-number"></a><span data-ttu-id="2500b-2796">Malesia - Numero di carta d’identità</span><span class="sxs-lookup"><span data-stu-id="2500b-2796">Malaysia ID Card Number</span></span>

### <a name="format"></a><span data-ttu-id="2500b-2797">Formato</span><span class="sxs-lookup"><span data-stu-id="2500b-2797">Format</span></span>

<span data-ttu-id="2500b-2798">12 cifre contenenti lineette facoltative</span><span class="sxs-lookup"><span data-stu-id="2500b-2798">12 digits containing optional hyphens</span></span>

### <a name="pattern"></a><span data-ttu-id="2500b-2799">Modello</span><span class="sxs-lookup"><span data-stu-id="2500b-2799">Pattern</span></span>

<span data-ttu-id="2500b-2800">12 cifre:</span><span class="sxs-lookup"><span data-stu-id="2500b-2800">12 digits:</span></span>
- <span data-ttu-id="2500b-2801">Sei cifre nel formato AAMMGG, ovvero la data di nascita</span><span class="sxs-lookup"><span data-stu-id="2500b-2801">Six digits in the format YYMMDD which are the date of birth</span></span> 
- <span data-ttu-id="2500b-2802">Un trattino (facoltativo)</span><span class="sxs-lookup"><span data-stu-id="2500b-2802">A dash (optional)</span></span> 
- <span data-ttu-id="2500b-2803">Codice luogo di nascita a due lettere </span><span class="sxs-lookup"><span data-stu-id="2500b-2803">Two-letter place-of-birth code</span></span> 
- <span data-ttu-id="2500b-2804">Un trattino (facoltativo)</span><span class="sxs-lookup"><span data-stu-id="2500b-2804">A dash (optional)</span></span> 
- <span data-ttu-id="2500b-2805">Tre cifre casuali </span><span class="sxs-lookup"><span data-stu-id="2500b-2805">Three random digits</span></span> 
- <span data-ttu-id="2500b-2806">Codice genere a una cifra singola</span><span class="sxs-lookup"><span data-stu-id="2500b-2806">One-digit gender code</span></span>

### <a name="checksum"></a><span data-ttu-id="2500b-2807">Checksum</span><span class="sxs-lookup"><span data-stu-id="2500b-2807">Checksum</span></span>

<span data-ttu-id="2500b-2808">No</span><span class="sxs-lookup"><span data-stu-id="2500b-2808">No</span></span>

### <a name="definition"></a><span data-ttu-id="2500b-2809">Definizione</span><span class="sxs-lookup"><span data-stu-id="2500b-2809">Definition</span></span>

<span data-ttu-id="2500b-2810">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="2500b-2810">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2500b-2811">L'espressione regolare Regex_malaysia_id_card_number trova il contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="2500b-2811">The regular expression Regex_malaysia_id_card_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="2500b-2812">Viene trovata una parola chiave da Keyword_malaysia_id_card_number.</span><span class="sxs-lookup"><span data-stu-id="2500b-2812">A keyword from Keyword_malaysia_id_card_number is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="2500b-2813">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="2500b-2813">Keywords</span></span>
   
#### <a name="keywordmalaysiaidcardnumber"></a><span data-ttu-id="2500b-2814">Keyword_malaysia_id_card_number</span><span class="sxs-lookup"><span data-stu-id="2500b-2814">Keyword_malaysia_id_card_number</span></span>

- <span data-ttu-id="2500b-2815">scheda dell'applicazione digitale</span><span class="sxs-lookup"><span data-stu-id="2500b-2815">digital application card</span></span>
- <span data-ttu-id="2500b-2816">i/c</span><span class="sxs-lookup"><span data-stu-id="2500b-2816">i/c</span></span>
- <span data-ttu-id="2500b-2817">i/c no</span><span class="sxs-lookup"><span data-stu-id="2500b-2817">i/c no</span></span>
- <span data-ttu-id="2500b-2818">IC</span><span class="sxs-lookup"><span data-stu-id="2500b-2818">ic</span></span>
- <span data-ttu-id="2500b-2819">IC No</span><span class="sxs-lookup"><span data-stu-id="2500b-2819">ic no</span></span>
- <span data-ttu-id="2500b-2820">id card</span><span class="sxs-lookup"><span data-stu-id="2500b-2820">id card</span></span>
- <span data-ttu-id="2500b-2821">Scheda di identificazione</span><span class="sxs-lookup"><span data-stu-id="2500b-2821">identification Card</span></span>
- <span data-ttu-id="2500b-2822">carta di identità</span><span class="sxs-lookup"><span data-stu-id="2500b-2822">identity card</span></span>
- <span data-ttu-id="2500b-2823">k/p</span><span class="sxs-lookup"><span data-stu-id="2500b-2823">k/p</span></span>
- <span data-ttu-id="2500b-2824">k/p no</span><span class="sxs-lookup"><span data-stu-id="2500b-2824">k/p no</span></span>
- <span data-ttu-id="2500b-2825">diri akuan Kad</span><span class="sxs-lookup"><span data-stu-id="2500b-2825">kad akuan diri</span></span>
- <span data-ttu-id="2500b-2826">Kad Aplikasi digitale</span><span class="sxs-lookup"><span data-stu-id="2500b-2826">kad aplikasi digital</span></span>
- <span data-ttu-id="2500b-2827">Kad Pengenalan Malaysia</span><span class="sxs-lookup"><span data-stu-id="2500b-2827">kad pengenalan malaysia</span></span>
- <span data-ttu-id="2500b-2828">KP</span><span class="sxs-lookup"><span data-stu-id="2500b-2828">kp</span></span>
- <span data-ttu-id="2500b-2829">KP No</span><span class="sxs-lookup"><span data-stu-id="2500b-2829">kp no</span></span>
- <span data-ttu-id="2500b-2830">MyKad</span><span class="sxs-lookup"><span data-stu-id="2500b-2830">mykad</span></span>
- <span data-ttu-id="2500b-2831">MYKAS</span><span class="sxs-lookup"><span data-stu-id="2500b-2831">mykas</span></span>
- <span data-ttu-id="2500b-2832">mykid</span><span class="sxs-lookup"><span data-stu-id="2500b-2832">mykid</span></span>
- <span data-ttu-id="2500b-2833">mypr</span><span class="sxs-lookup"><span data-stu-id="2500b-2833">mypr</span></span>
- <span data-ttu-id="2500b-2834">mytentera</span><span class="sxs-lookup"><span data-stu-id="2500b-2834">mytentera</span></span>
- <span data-ttu-id="2500b-2835">carta di identità Malaysia</span><span class="sxs-lookup"><span data-stu-id="2500b-2835">malaysia identity card</span></span>
- <span data-ttu-id="2500b-2836">carta di identità malaysiana</span><span class="sxs-lookup"><span data-stu-id="2500b-2836">malaysian identity card</span></span>
- <span data-ttu-id="2500b-2837">NRIC</span><span class="sxs-lookup"><span data-stu-id="2500b-2837">nric</span></span>
- <span data-ttu-id="2500b-2838">scheda di identificazione personale</span><span class="sxs-lookup"><span data-stu-id="2500b-2838">personal identification card</span></span>
   
## <a name="netherlands-citizens-service-bsn-number"></a><span data-ttu-id="2500b-2839">Paesi Bassi - Numero di servizio cittadino (BSN)</span><span class="sxs-lookup"><span data-stu-id="2500b-2839">Netherlands Citizen's Service (BSN) Number</span></span>

### <a name="format"></a><span data-ttu-id="2500b-2840">Formato</span><span class="sxs-lookup"><span data-stu-id="2500b-2840">Format</span></span>

<span data-ttu-id="2500b-2841">8-9 cifre contenenti spazi facoltativi </span><span class="sxs-lookup"><span data-stu-id="2500b-2841">8-9 digits containing optional spaces</span></span>

### <a name="pattern"></a><span data-ttu-id="2500b-2842">Modello</span><span class="sxs-lookup"><span data-stu-id="2500b-2842">Pattern</span></span>

<span data-ttu-id="2500b-2843">8-9 cifre:</span><span class="sxs-lookup"><span data-stu-id="2500b-2843">8-9 digits:</span></span>
- <span data-ttu-id="2500b-2844">Tre cifre</span><span class="sxs-lookup"><span data-stu-id="2500b-2844">Three digits</span></span> 
- <span data-ttu-id="2500b-2845">Uno spazio (facoltativo)</span><span class="sxs-lookup"><span data-stu-id="2500b-2845">A space (optional)</span></span> 
- <span data-ttu-id="2500b-2846">Tre cifre</span><span class="sxs-lookup"><span data-stu-id="2500b-2846">Three digits</span></span> 
- <span data-ttu-id="2500b-2847">Uno spazio (facoltativo)</span><span class="sxs-lookup"><span data-stu-id="2500b-2847">A space (optional)</span></span> 
- <span data-ttu-id="2500b-2848">2-3 cifre</span><span class="sxs-lookup"><span data-stu-id="2500b-2848">2-3 digits</span></span>

### <a name="checksum"></a><span data-ttu-id="2500b-2849">Checksum</span><span class="sxs-lookup"><span data-stu-id="2500b-2849">Checksum</span></span>

<span data-ttu-id="2500b-2850">Sì</span><span class="sxs-lookup"><span data-stu-id="2500b-2850">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="2500b-2851">Definizione</span><span class="sxs-lookup"><span data-stu-id="2500b-2851">Definition</span></span>

<span data-ttu-id="2500b-2852">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="2500b-2852">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2500b-2853">La funzione Func_netherlands_bsn trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="2500b-2853">The function Func_netherlands_bsn finds content that matches the pattern.</span></span>
- <span data-ttu-id="2500b-2854">Viene trovata una parola chiave da Keyword_netherlands_bsn.</span><span class="sxs-lookup"><span data-stu-id="2500b-2854">A keyword from Keyword_netherlands_bsn is found.</span></span>
- <span data-ttu-id="2500b-2855">La funzione Func_eu_date2 rileva una data nel formato di data appropriato.</span><span class="sxs-lookup"><span data-stu-id="2500b-2855">The function Func_eu_date2 finds a date in the right date format.</span></span>
- <span data-ttu-id="2500b-2856">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="2500b-2856">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="2500b-2857">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="2500b-2857">Keywords</span></span>

#### <a name="keywordnetherlandsbsn"></a><span data-ttu-id="2500b-2858">Keyword_netherlands_bsn</span><span class="sxs-lookup"><span data-stu-id="2500b-2858">Keyword_netherlands_bsn</span></span>

- <span data-ttu-id="2500b-2859">Numero di servizio cittadino</span><span class="sxs-lookup"><span data-stu-id="2500b-2859">Citizen service number</span></span> 
- <span data-ttu-id="2500b-2860">BSN</span><span class="sxs-lookup"><span data-stu-id="2500b-2860">BSN</span></span> 
- <span data-ttu-id="2500b-2861">Burgerservicenummer</span><span class="sxs-lookup"><span data-stu-id="2500b-2861">Burgerservicenummer</span></span> 
- <span data-ttu-id="2500b-2862">Sofinummer</span><span class="sxs-lookup"><span data-stu-id="2500b-2862">Sofinummer</span></span> 
- <span data-ttu-id="2500b-2863">Persoonsgebonden nummer</span><span class="sxs-lookup"><span data-stu-id="2500b-2863">Persoonsgebonden nummer</span></span> 
- <span data-ttu-id="2500b-2864">Persoonsnummer</span><span class="sxs-lookup"><span data-stu-id="2500b-2864">Persoonsnummer</span></span>    

   
## <a name="new-zealand-ministry-of-health-number"></a><span data-ttu-id="2500b-2865">Nuova Zelanda - Numero del Ministero della Sanità</span><span class="sxs-lookup"><span data-stu-id="2500b-2865">New Zealand Ministry of Health Number</span></span>

### <a name="format"></a><span data-ttu-id="2500b-2866">Formato</span><span class="sxs-lookup"><span data-stu-id="2500b-2866">Format</span></span>

<span data-ttu-id="2500b-2867">Tre lettere, uno spazio (facoltativo) e quattro cifre</span><span class="sxs-lookup"><span data-stu-id="2500b-2867">Three letters, a space (optional), and four digits</span></span>

### <a name="pattern"></a><span data-ttu-id="2500b-2868">Modello</span><span class="sxs-lookup"><span data-stu-id="2500b-2868">Pattern</span></span>

<span data-ttu-id="2500b-2869">Tre lettere (senza distinzione tra maiuscole/minuscole) uno spazio (facoltativo) quattro cifre</span><span class="sxs-lookup"><span data-stu-id="2500b-2869">Three letters (not case sensitive) a space (optional) four digits</span></span>

### <a name="checksum"></a><span data-ttu-id="2500b-2870">Checksum</span><span class="sxs-lookup"><span data-stu-id="2500b-2870">Checksum</span></span>

<span data-ttu-id="2500b-2871">Sì</span><span class="sxs-lookup"><span data-stu-id="2500b-2871">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="2500b-2872">Definizione</span><span class="sxs-lookup"><span data-stu-id="2500b-2872">Definition</span></span>

<span data-ttu-id="2500b-2873">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="2500b-2873">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2500b-2874">La funzione Func_new_zealand_ministry_of_health_number restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="2500b-2874">The function Func_new_zealand_ministry_of_health_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="2500b-2875">Viene trovata una parola chiave da Keyword_nz_terms.</span><span class="sxs-lookup"><span data-stu-id="2500b-2875">A keyword from Keyword_nz_terms is found.</span></span>
- <span data-ttu-id="2500b-2876">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="2500b-2876">The checksum passes.</span></span>

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

<span data-ttu-id="2500b-2877">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="2500b-2877">Keywords</span></span>

<span data-ttu-id="2500b-2878">Keyword_nz_terms</span><span class="sxs-lookup"><span data-stu-id="2500b-2878">Keyword_nz_terms</span></span>

- <span data-ttu-id="2500b-2879">NHI</span><span class="sxs-lookup"><span data-stu-id="2500b-2879">NHI</span></span> 
- <span data-ttu-id="2500b-2880">New Zealand</span><span class="sxs-lookup"><span data-stu-id="2500b-2880">New Zealand</span></span> 
- <span data-ttu-id="2500b-2881">Integrità</span><span class="sxs-lookup"><span data-stu-id="2500b-2881">Health</span></span> 
- <span data-ttu-id="2500b-2882">trattamento</span><span class="sxs-lookup"><span data-stu-id="2500b-2882">treatment</span></span> 
   
## <a name="norway-identification-number"></a><span data-ttu-id="2500b-2883">Norvegia - Numero di identificazione
</span><span class="sxs-lookup"><span data-stu-id="2500b-2883">Norway Identification Number</span></span>

### <a name="format"></a><span data-ttu-id="2500b-2884">Formato</span><span class="sxs-lookup"><span data-stu-id="2500b-2884">Format</span></span>

<span data-ttu-id="2500b-2885">11 cifre</span><span class="sxs-lookup"><span data-stu-id="2500b-2885">11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="2500b-2886">Modello</span><span class="sxs-lookup"><span data-stu-id="2500b-2886">Pattern</span></span>

<span data-ttu-id="2500b-2887">11 cifre:</span><span class="sxs-lookup"><span data-stu-id="2500b-2887">11 digits:</span></span>
- <span data-ttu-id="2500b-2888">Sei cifre nel formato GGMMAA, ovvero la data di nascita</span><span class="sxs-lookup"><span data-stu-id="2500b-2888">Six digits in the format DDMMYY which are the date of birth</span></span> 
- <span data-ttu-id="2500b-2889">Numero individuale composto da tre cifre </span><span class="sxs-lookup"><span data-stu-id="2500b-2889">Three-digit individual number</span></span> 
- <span data-ttu-id="2500b-2890">Due cifre di controllo</span><span class="sxs-lookup"><span data-stu-id="2500b-2890">Two check digits</span></span>

### <a name="checksum"></a><span data-ttu-id="2500b-2891">Checksum</span><span class="sxs-lookup"><span data-stu-id="2500b-2891">Checksum</span></span>

<span data-ttu-id="2500b-2892">Sì</span><span class="sxs-lookup"><span data-stu-id="2500b-2892">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="2500b-2893">Definizione</span><span class="sxs-lookup"><span data-stu-id="2500b-2893">Definition</span></span>

<span data-ttu-id="2500b-2894">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="2500b-2894">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2500b-2895">La funzione Func_norway_id_number trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="2500b-2895">The function Func_norway_id_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="2500b-2896">Viene trovata una parola chiave da Keyword_norway_id_number.</span><span class="sxs-lookup"><span data-stu-id="2500b-2896">A keyword from Keyword_norway_id_number is found.</span></span>
- <span data-ttu-id="2500b-2897">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="2500b-2897">The checksum passes.</span></span>
- <span data-ttu-id="2500b-2898">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="2500b-2898">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2500b-2899">La funzione Func_norway_id_numbe trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="2500b-2899">The function Func_norway_id_numbe finds content that matches the pattern.</span></span>
- <span data-ttu-id="2500b-2900">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="2500b-2900">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="2500b-2901">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="2500b-2901">Keywords</span></span>

#### <a name="keywordnorwayidnumber"></a><span data-ttu-id="2500b-2902">Keyword_norway_id_number</span><span class="sxs-lookup"><span data-stu-id="2500b-2902">Keyword_norway_id_number</span></span>

- <span data-ttu-id="2500b-2903">Codice PIN</span><span class="sxs-lookup"><span data-stu-id="2500b-2903">Personal identification number</span></span>
- <span data-ttu-id="2500b-2904">Numero ID norvegese</span><span class="sxs-lookup"><span data-stu-id="2500b-2904">Norwegian ID Number</span></span>
- <span data-ttu-id="2500b-2905">Numero ID
</span><span class="sxs-lookup"><span data-stu-id="2500b-2905">ID Number</span></span>
- <span data-ttu-id="2500b-2906">Identificazione</span><span class="sxs-lookup"><span data-stu-id="2500b-2906">Identification</span></span>
- <span data-ttu-id="2500b-2907">Personnummer</span><span class="sxs-lookup"><span data-stu-id="2500b-2907">Personnummer</span></span>
- <span data-ttu-id="2500b-2908">Fødselsnummer</span><span class="sxs-lookup"><span data-stu-id="2500b-2908">Fødselsnummer</span></span>

   
## <a name="philippines-unified-multi-purpose-id-number"></a><span data-ttu-id="2500b-2909">Filippine - Numero ID multifunzione unificato</span><span class="sxs-lookup"><span data-stu-id="2500b-2909">Philippines Unified Multi-Purpose ID Number</span></span>

### <a name="format"></a><span data-ttu-id="2500b-2910">Formato</span><span class="sxs-lookup"><span data-stu-id="2500b-2910">Format</span></span>

<span data-ttu-id="2500b-2911">12 cifre separate da dei segni meno</span><span class="sxs-lookup"><span data-stu-id="2500b-2911">12 digits separated by hyphens</span></span>

### <a name="pattern"></a><span data-ttu-id="2500b-2912">Modello</span><span class="sxs-lookup"><span data-stu-id="2500b-2912">Pattern</span></span>

<span data-ttu-id="2500b-2913">12 cifre:</span><span class="sxs-lookup"><span data-stu-id="2500b-2913">12 digits:</span></span>
- <span data-ttu-id="2500b-2914">Quattro cifre</span><span class="sxs-lookup"><span data-stu-id="2500b-2914">Four digits</span></span> 
- <span data-ttu-id="2500b-2915">Una lineetta</span><span class="sxs-lookup"><span data-stu-id="2500b-2915">A hyphen</span></span> 
- <span data-ttu-id="2500b-2916">Sette cifre</span><span class="sxs-lookup"><span data-stu-id="2500b-2916">Seven digits</span></span> 
- <span data-ttu-id="2500b-2917">Una lineetta</span><span class="sxs-lookup"><span data-stu-id="2500b-2917">A hyphen</span></span> 
- <span data-ttu-id="2500b-2918">Una cifra</span><span class="sxs-lookup"><span data-stu-id="2500b-2918">One digit</span></span>

### <a name="checksum"></a><span data-ttu-id="2500b-2919">Checksum</span><span class="sxs-lookup"><span data-stu-id="2500b-2919">Checksum</span></span>

<span data-ttu-id="2500b-2920">No</span><span class="sxs-lookup"><span data-stu-id="2500b-2920">No</span></span>

### <a name="definition"></a><span data-ttu-id="2500b-2921">Definizione</span><span class="sxs-lookup"><span data-stu-id="2500b-2921">Definition</span></span>

<span data-ttu-id="2500b-2922">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="2500b-2922">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2500b-2923">L'espressione regolare Regex_philippines_unified_id trova il contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="2500b-2923">The regular expression Regex_philippines_unified_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="2500b-2924">Viene trovata una parola chiave da Keyword_philippines_id.</span><span class="sxs-lookup"><span data-stu-id="2500b-2924">A keyword from Keyword_philippines_id is found.</span></span>

```
<!-- Philippines Unified Multi-Purpose ID number -->
<Entity id="019b39dd-8c25-4765-91a3-d9c6baf3c3b3" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_philippines_unified_id"/>
     <Match idRef="Keyword_philippines_id"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="2500b-2925">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="2500b-2925">Keywords</span></span>
   
#### <a name="keywordphilippinesid"></a><span data-ttu-id="2500b-2926">Keyword_philippines_id</span><span class="sxs-lookup"><span data-stu-id="2500b-2926">Keyword_philippines_id</span></span>

- <span data-ttu-id="2500b-2927">ID multifunzione unificato</span><span class="sxs-lookup"><span data-stu-id="2500b-2927">Unified Multi-Purpose ID</span></span> 
- <span data-ttu-id="2500b-2928">UMID</span><span class="sxs-lookup"><span data-stu-id="2500b-2928">UMID</span></span> 
- <span data-ttu-id="2500b-2929">Carta di identità</span><span class="sxs-lookup"><span data-stu-id="2500b-2929">Identity Card</span></span> 
- <span data-ttu-id="2500b-2930">Pinag-isang Multi-Layunin ID</span><span class="sxs-lookup"><span data-stu-id="2500b-2930">Pinag-isang Multi-Layunin ID</span></span>
   
## <a name="poland-identity-card"></a><span data-ttu-id="2500b-2931">Carta di identita - Polonia</span><span class="sxs-lookup"><span data-stu-id="2500b-2931">Poland Identity Card</span></span>

### <a name="format"></a><span data-ttu-id="2500b-2932">Formato</span><span class="sxs-lookup"><span data-stu-id="2500b-2932">Format</span></span>

<span data-ttu-id="2500b-2933">Tre lettere e sei cifre</span><span class="sxs-lookup"><span data-stu-id="2500b-2933">Three letters and six digits</span></span>

### <a name="pattern"></a><span data-ttu-id="2500b-2934">Modello</span><span class="sxs-lookup"><span data-stu-id="2500b-2934">Pattern</span></span>

<span data-ttu-id="2500b-2935">Tre lettere (senza distinzione tra maiuscole/minuscole) seguite da sei cifre</span><span class="sxs-lookup"><span data-stu-id="2500b-2935">Three letters (not case sensitive) followed by six digits</span></span>

### <a name="checksum"></a><span data-ttu-id="2500b-2936">Checksum</span><span class="sxs-lookup"><span data-stu-id="2500b-2936">Checksum</span></span>

<span data-ttu-id="2500b-2937">Sì</span><span class="sxs-lookup"><span data-stu-id="2500b-2937">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="2500b-2938">Definizione</span><span class="sxs-lookup"><span data-stu-id="2500b-2938">Definition</span></span>

<span data-ttu-id="2500b-2939">Un criterio DLP è 75% fiducioso di aver rilevato questo tipo di informazioni riservate se, entro 300 caratteri: la funzione Func_polish_national_id trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="2500b-2939">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The function Func_polish_national_id finds content that matches the pattern.</span></span>
<span data-ttu-id="2500b-2940">Viene trovata una parola chiave da Keyword_polish_national_id_passport_number.</span><span class="sxs-lookup"><span data-stu-id="2500b-2940">A keyword from Keyword_polish_national_id_passport_number is found.</span></span>
<span data-ttu-id="2500b-2941">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="2500b-2941">The checksum passes.</span></span>

```
<!-- Poland Identity Card-->
<Entity id="25E64989-ED5D-40CA-A939-6C14183BB7BF" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_polish_national_id" />
          <Match idRef="Keyword_polish_national_id_passport_number" />
      </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="2500b-2942">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="2500b-2942">Keywords</span></span>

#### <a name="keywordpolishnationalidpassportnumber"></a><span data-ttu-id="2500b-2943">Keyword_polish_national_id_passport_number</span><span class="sxs-lookup"><span data-stu-id="2500b-2943">Keyword_polish_national_id_passport_number</span></span>

- <span data-ttu-id="2500b-2944">Dowód osobisty</span><span class="sxs-lookup"><span data-stu-id="2500b-2944">Dowód osobisty</span></span>
- <span data-ttu-id="2500b-2945">Numero dowodu osobistego</span><span class="sxs-lookup"><span data-stu-id="2500b-2945">Numer dowodu osobistego</span></span>
- <span data-ttu-id="2500b-2946">Nazwa i numeri dowodu osobistego</span><span class="sxs-lookup"><span data-stu-id="2500b-2946">Nazwa i numer dowodu osobistego</span></span>
- <span data-ttu-id="2500b-2947">Nazwa i Nr dowodu osobistego</span><span class="sxs-lookup"><span data-stu-id="2500b-2947">Nazwa i nr dowodu osobistego</span></span>
- <span data-ttu-id="2500b-2948">Nazwa i nr dowodu tożsamości</span><span class="sxs-lookup"><span data-stu-id="2500b-2948">Nazwa i nr dowodu tożsamości</span></span>
- <span data-ttu-id="2500b-2949">Dowód Tożsamości</span><span class="sxs-lookup"><span data-stu-id="2500b-2949">Dowód Tożsamości</span></span>
- <span data-ttu-id="2500b-2950">Dow.</span><span class="sxs-lookup"><span data-stu-id="2500b-2950">dow.</span></span> <span data-ttu-id="2500b-2951">OS.</span><span class="sxs-lookup"><span data-stu-id="2500b-2951">os.</span></span>

   
## <a name="poland-national-id-pesel"></a><span data-ttu-id="2500b-2952">ID nazionale Polonia (PESEL)</span><span class="sxs-lookup"><span data-stu-id="2500b-2952">Poland National ID (PESEL)</span></span>

### <a name="format"></a><span data-ttu-id="2500b-2953">Formato</span><span class="sxs-lookup"><span data-stu-id="2500b-2953">Format</span></span>

<span data-ttu-id="2500b-2954">11 cifre</span><span class="sxs-lookup"><span data-stu-id="2500b-2954">11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="2500b-2955">Modello</span><span class="sxs-lookup"><span data-stu-id="2500b-2955">Pattern</span></span>

<span data-ttu-id="2500b-2956">11 cifre consecutive</span><span class="sxs-lookup"><span data-stu-id="2500b-2956">11 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="2500b-2957">Checksum</span><span class="sxs-lookup"><span data-stu-id="2500b-2957">Checksum</span></span>

<span data-ttu-id="2500b-2958">Sì</span><span class="sxs-lookup"><span data-stu-id="2500b-2958">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="2500b-2959">Definizione</span><span class="sxs-lookup"><span data-stu-id="2500b-2959">Definition</span></span>

<span data-ttu-id="2500b-2960">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="2500b-2960">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2500b-2961">La funzione Func_pesel_identification_number restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="2500b-2961">The function Func_pesel_identification_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="2500b-2962">Viene trovata una parola chiave da Keyword_pesel_identification_number.</span><span class="sxs-lookup"><span data-stu-id="2500b-2962">A keyword from Keyword_pesel_identification_number is found.</span></span>
- <span data-ttu-id="2500b-2963">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="2500b-2963">The checksum passes.</span></span>

```
<!-- Poland National ID (PESEL) -->      
<Entity id="E3AAF206-4297-412F-9E06-BA8487E22456" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_pesel_identification_number" />
          <Match idRef="Keyword_pesel_identification_number" />
      </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="2500b-2964">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="2500b-2964">Keywords</span></span>

#### <a name="keywordpeselidentificationnumber"></a><span data-ttu-id="2500b-2965">Keyword_pesel_identification_number</span><span class="sxs-lookup"><span data-stu-id="2500b-2965">Keyword_pesel_identification_number</span></span>

- <span data-ttu-id="2500b-2966">Nr PESEL</span><span class="sxs-lookup"><span data-stu-id="2500b-2966">Nr PESEL</span></span>
- <span data-ttu-id="2500b-2967">PESEL</span><span class="sxs-lookup"><span data-stu-id="2500b-2967">PESEL</span></span>   

   
## <a name="poland-passport"></a><span data-ttu-id="2500b-2968">Passaporto Polonia</span><span class="sxs-lookup"><span data-stu-id="2500b-2968">Poland Passport</span></span>

### <a name="format"></a><span data-ttu-id="2500b-2969">Formato</span><span class="sxs-lookup"><span data-stu-id="2500b-2969">Format</span></span>

<span data-ttu-id="2500b-2970">Due lettere e sette cifre</span><span class="sxs-lookup"><span data-stu-id="2500b-2970">Two letters and seven digits</span></span>

### <a name="pattern"></a><span data-ttu-id="2500b-2971">Modello</span><span class="sxs-lookup"><span data-stu-id="2500b-2971">Pattern</span></span>

<span data-ttu-id="2500b-2972">Due lettere (senza distinzione tra maiuscole/minuscole) seguite da sette cifre</span><span class="sxs-lookup"><span data-stu-id="2500b-2972">Two letters (not case sensitive) followed by seven digits</span></span>

### <a name="checksum"></a><span data-ttu-id="2500b-2973">Checksum</span><span class="sxs-lookup"><span data-stu-id="2500b-2973">Checksum</span></span>

<span data-ttu-id="2500b-2974">Sì</span><span class="sxs-lookup"><span data-stu-id="2500b-2974">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="2500b-2975">Definizione</span><span class="sxs-lookup"><span data-stu-id="2500b-2975">Definition</span></span>

<span data-ttu-id="2500b-2976">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="2500b-2976">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2500b-2977">La funzione Func_polish_passport_number restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="2500b-2977">The function Func_polish_passport_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="2500b-2978">Viene trovata una parola chiave da Keyword_polish_national_id_passport_number.</span><span class="sxs-lookup"><span data-stu-id="2500b-2978">A keyword from Keyword_polish_national_id_passport_number is found.</span></span>
- <span data-ttu-id="2500b-2979">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="2500b-2979">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="2500b-2980">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="2500b-2980">Keywords</span></span>

#### <a name="keywordpolishnationalidpassportnumber"></a><span data-ttu-id="2500b-2981">Keyword_polish_national_id_passport_number</span><span class="sxs-lookup"><span data-stu-id="2500b-2981">Keyword_polish_national_id_passport_number</span></span>

- <span data-ttu-id="2500b-2982">Numero Paszportu</span><span class="sxs-lookup"><span data-stu-id="2500b-2982">Numer paszportu</span></span>
- <span data-ttu-id="2500b-2983">Nr.</span><span class="sxs-lookup"><span data-stu-id="2500b-2983">Nr.</span></span> <span data-ttu-id="2500b-2984">Paszportu</span><span class="sxs-lookup"><span data-stu-id="2500b-2984">Paszportu</span></span>
- <span data-ttu-id="2500b-2985">Paszport</span><span class="sxs-lookup"><span data-stu-id="2500b-2985">Paszport</span></span>

   
## <a name="portugal-citizen-card-number"></a><span data-ttu-id="2500b-2986">Portogallo - Numero di carta del cittadino</span><span class="sxs-lookup"><span data-stu-id="2500b-2986">Portugal Citizen Card Number</span></span>

### <a name="format"></a><span data-ttu-id="2500b-2987">Formato</span><span class="sxs-lookup"><span data-stu-id="2500b-2987">Format</span></span>

<span data-ttu-id="2500b-2988">Otto cifre</span><span class="sxs-lookup"><span data-stu-id="2500b-2988">Eight digits</span></span>

### <a name="pattern"></a><span data-ttu-id="2500b-2989">Modello</span><span class="sxs-lookup"><span data-stu-id="2500b-2989">Pattern</span></span>

<span data-ttu-id="2500b-2990">Otto cifre</span><span class="sxs-lookup"><span data-stu-id="2500b-2990">Eight digits</span></span>

### <a name="checksum"></a><span data-ttu-id="2500b-2991">Checksum</span><span class="sxs-lookup"><span data-stu-id="2500b-2991">Checksum</span></span>

<span data-ttu-id="2500b-2992">No</span><span class="sxs-lookup"><span data-stu-id="2500b-2992">No</span></span>

### <a name="definition"></a><span data-ttu-id="2500b-2993">Definizione</span><span class="sxs-lookup"><span data-stu-id="2500b-2993">Definition</span></span>

<span data-ttu-id="2500b-2994">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="2500b-2994">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2500b-2995">L'espressione regolare Regex_portugal_citizen_card trova il contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="2500b-2995">The regular expression Regex_portugal_citizen_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="2500b-2996">Viene trovata una parola chiave da Keyword_portugal_citizen_card.</span><span class="sxs-lookup"><span data-stu-id="2500b-2996">A keyword from Keyword_portugal_citizen_card is found.</span></span>

```
<!-- Portugal Citizen Card Number -->
<Entity id="91a7ece2-add4-4986-9a15-c84544d81ecd" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Regex_portugal_citizen_card"/>
     <Match idRef="Keyword_portugal_citizen_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="2500b-2997">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="2500b-2997">Keywords</span></span>

#### <a name="keywordportugalcitizencard"></a><span data-ttu-id="2500b-2998">Keyword_portugal_citizen_card</span><span class="sxs-lookup"><span data-stu-id="2500b-2998">Keyword_portugal_citizen_card</span></span>

- <span data-ttu-id="2500b-2999">Scheda cittadino</span><span class="sxs-lookup"><span data-stu-id="2500b-2999">Citizen Card</span></span>
- <span data-ttu-id="2500b-3000">Carta ID</span><span class="sxs-lookup"><span data-stu-id="2500b-3000">National ID Card</span></span>
- <span data-ttu-id="2500b-3001">CC</span><span class="sxs-lookup"><span data-stu-id="2500b-3001">CC</span></span>
- <span data-ttu-id="2500b-3002">Cartão de Cidadão</span><span class="sxs-lookup"><span data-stu-id="2500b-3002">Cartão de Cidadão</span></span>
- <span data-ttu-id="2500b-3003">Bilhete de Identidade</span><span class="sxs-lookup"><span data-stu-id="2500b-3003">Bilhete de Identidade</span></span>
   
## <a name="saudi-arabia-national-id"></a><span data-ttu-id="2500b-3004">Arabia Saudita - Identificativo nazionale</span><span class="sxs-lookup"><span data-stu-id="2500b-3004">Saudi Arabia National ID</span></span>

### <a name="format"></a><span data-ttu-id="2500b-3005">Formato</span><span class="sxs-lookup"><span data-stu-id="2500b-3005">Format</span></span>

<span data-ttu-id="2500b-3006">10 cifre</span><span class="sxs-lookup"><span data-stu-id="2500b-3006">10 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="2500b-3007">Modello</span><span class="sxs-lookup"><span data-stu-id="2500b-3007">Pattern</span></span>

<span data-ttu-id="2500b-3008">10 cifre consecutive</span><span class="sxs-lookup"><span data-stu-id="2500b-3008">10 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="2500b-3009">Checksum</span><span class="sxs-lookup"><span data-stu-id="2500b-3009">Checksum</span></span>

<span data-ttu-id="2500b-3010">No</span><span class="sxs-lookup"><span data-stu-id="2500b-3010">No</span></span>

### <a name="definition"></a><span data-ttu-id="2500b-3011">Definizione</span><span class="sxs-lookup"><span data-stu-id="2500b-3011">Definition</span></span>

<span data-ttu-id="2500b-3012">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="2500b-3012">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2500b-3013">L'espressione regolare Regex_saudi_arabia_national_id restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="2500b-3013">The regular expression Regex_saudi_arabia_national_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="2500b-3014">Viene trovata una parola chiave da Keyword_saudi_arabia_national_id.</span><span class="sxs-lookup"><span data-stu-id="2500b-3014">A keyword from Keyword_saudi_arabia_national_id is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="2500b-3015">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="2500b-3015">Keywords</span></span>

#### <a name="keywordsaudiarabianationalid"></a><span data-ttu-id="2500b-3016">Keyword_saudi_arabia_national_id</span><span class="sxs-lookup"><span data-stu-id="2500b-3016">Keyword_saudi_arabia_national_id</span></span>

- <span data-ttu-id="2500b-3017">Identification Card</span><span class="sxs-lookup"><span data-stu-id="2500b-3017">Identification Card</span></span> 
- <span data-ttu-id="2500b-3018">I card number</span><span class="sxs-lookup"><span data-stu-id="2500b-3018">I card number</span></span> 
- <span data-ttu-id="2500b-3019">ID number</span><span class="sxs-lookup"><span data-stu-id="2500b-3019">ID number</span></span> 
- <span data-ttu-id="2500b-3020">الوطنية الهوية بطاقة رقم</span><span class="sxs-lookup"><span data-stu-id="2500b-3020">الوطنية الهوية بطاقة رقم</span></span> 

   
## <a name="singapore-national-registration-identity-card-nric-number"></a><span data-ttu-id="2500b-3021">Singapore - Numero di carta di identità di registrazione nazionale (NRIC)</span><span class="sxs-lookup"><span data-stu-id="2500b-3021">Singapore National Registration Identity Card (NRIC) Number</span></span>

### <a name="format"></a><span data-ttu-id="2500b-3022">Formato</span><span class="sxs-lookup"><span data-stu-id="2500b-3022">Format</span></span>

<span data-ttu-id="2500b-3023">Nove lettere e numeri</span><span class="sxs-lookup"><span data-stu-id="2500b-3023">Nine letters and digits</span></span>

### <a name="pattern"></a><span data-ttu-id="2500b-3024">Modello</span><span class="sxs-lookup"><span data-stu-id="2500b-3024">Pattern</span></span>

- <span data-ttu-id="2500b-3025">Nove lettere e numeri:</span><span class="sxs-lookup"><span data-stu-id="2500b-3025">Nine letters and digits:</span></span>
- <span data-ttu-id="2500b-3026">La lettera "F", "G", "S" o "T" (senza distinzione tra maiuscole e minuscole) </span><span class="sxs-lookup"><span data-stu-id="2500b-3026">The letter "F", "G", "S", or "T" (not case sensitive)</span></span> 
- <span data-ttu-id="2500b-3027">Sette cifre</span><span class="sxs-lookup"><span data-stu-id="2500b-3027">Seven digits</span></span> 
- <span data-ttu-id="2500b-3028">Una cifra di controllo alfabetica</span><span class="sxs-lookup"><span data-stu-id="2500b-3028">An alphabetic check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="2500b-3029">Checksum</span><span class="sxs-lookup"><span data-stu-id="2500b-3029">Checksum</span></span>

<span data-ttu-id="2500b-3030">Sì</span><span class="sxs-lookup"><span data-stu-id="2500b-3030">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="2500b-3031">Definizione</span><span class="sxs-lookup"><span data-stu-id="2500b-3031">Definition</span></span>

<span data-ttu-id="2500b-3032">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="2500b-3032">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2500b-3033">L'espressione regolare Regex_singapore_nric trova il contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="2500b-3033">The regular expression Regex_singapore_nric finds content that matches the pattern.</span></span>
- <span data-ttu-id="2500b-3034">Viene trovata una parola chiave da Keyword_singapore_nric.</span><span class="sxs-lookup"><span data-stu-id="2500b-3034">A keyword from Keyword_singapore_nric is found.</span></span>
- <span data-ttu-id="2500b-3035">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="2500b-3035">The checksum passes.</span></span>

<span data-ttu-id="2500b-3036">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="2500b-3036">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2500b-3037">L'espressione regolare Regex_singapore_nric trova il contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="2500b-3037">The regular expression Regex_singapore_nric finds content that matches the pattern.</span></span>
- <span data-ttu-id="2500b-3038">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="2500b-3038">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="2500b-3039">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="2500b-3039">Keywords</span></span>
   
#### <a name="keywordsingaporenric"></a><span data-ttu-id="2500b-3040">Keyword_singapore_nric</span><span class="sxs-lookup"><span data-stu-id="2500b-3040">Keyword_singapore_nric</span></span>

- <span data-ttu-id="2500b-3041">Carta di identità di registrazione nazionale</span><span class="sxs-lookup"><span data-stu-id="2500b-3041">National Registration Identity Card</span></span> 
- <span data-ttu-id="2500b-3042">Numero di carta di identità</span><span class="sxs-lookup"><span data-stu-id="2500b-3042">Identity Card Number</span></span> 
- <span data-ttu-id="2500b-3043">NRIC</span><span class="sxs-lookup"><span data-stu-id="2500b-3043">NRIC</span></span> 
- <span data-ttu-id="2500b-3044">IC</span><span class="sxs-lookup"><span data-stu-id="2500b-3044">IC</span></span> 
- <span data-ttu-id="2500b-3045">Numero di identificazione per stranieri</span><span class="sxs-lookup"><span data-stu-id="2500b-3045">Foreign Identification Number</span></span> 
- <span data-ttu-id="2500b-3046">FIN</span><span class="sxs-lookup"><span data-stu-id="2500b-3046">FIN</span></span> 
- <span data-ttu-id="2500b-3047">身份证</span><span class="sxs-lookup"><span data-stu-id="2500b-3047">身份证</span></span> 
- <span data-ttu-id="2500b-3048">身份證</span><span class="sxs-lookup"><span data-stu-id="2500b-3048">身份證</span></span> 
   
## <a name="south-africa-identification-number"></a><span data-ttu-id="2500b-3049">Sudafrica - Numero di identificazione
</span><span class="sxs-lookup"><span data-stu-id="2500b-3049">South Africa Identification Number</span></span>

### <a name="format"></a><span data-ttu-id="2500b-3050">Formato</span><span class="sxs-lookup"><span data-stu-id="2500b-3050">Format</span></span>

<span data-ttu-id="2500b-3051">13 cifre che possono contenere spazi</span><span class="sxs-lookup"><span data-stu-id="2500b-3051">13 digits that may contain spaces</span></span>

### <a name="pattern"></a><span data-ttu-id="2500b-3052">Modello</span><span class="sxs-lookup"><span data-stu-id="2500b-3052">Pattern</span></span>

<span data-ttu-id="2500b-3053">13 cifre:</span><span class="sxs-lookup"><span data-stu-id="2500b-3053">13 digits:</span></span>
- <span data-ttu-id="2500b-3054">Sei cifre nel formato AAMMGG, ovvero la data di nascita</span><span class="sxs-lookup"><span data-stu-id="2500b-3054">Six digits in the format YYMMDD which are the date of birth</span></span> 
- <span data-ttu-id="2500b-3055">Quattro cifre</span><span class="sxs-lookup"><span data-stu-id="2500b-3055">Four digits</span></span> 
- <span data-ttu-id="2500b-3056">Un indicatore di cittadinanza a una cifra </span><span class="sxs-lookup"><span data-stu-id="2500b-3056">A single-digit citizenship indicator</span></span> 
- <span data-ttu-id="2500b-3057">La cifra "8" o "9" </span><span class="sxs-lookup"><span data-stu-id="2500b-3057">The digit "8" or "9"</span></span> 
- <span data-ttu-id="2500b-3058">Una cifra, ovvero una cifra di checksum</span><span class="sxs-lookup"><span data-stu-id="2500b-3058">One digit which is a checksum digit</span></span>

### <a name="checksum"></a><span data-ttu-id="2500b-3059">Checksum</span><span class="sxs-lookup"><span data-stu-id="2500b-3059">Checksum</span></span>

<span data-ttu-id="2500b-3060">Sì</span><span class="sxs-lookup"><span data-stu-id="2500b-3060">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="2500b-3061">Definizione</span><span class="sxs-lookup"><span data-stu-id="2500b-3061">Definition</span></span>

<span data-ttu-id="2500b-3062">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="2500b-3062">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2500b-3063">La funzione Func_south_africa_identification_number trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="2500b-3063">The function Func_south_africa_identification_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="2500b-3064">Viene trovata una parola chiave da Keyword_south_africa_identification_number.</span><span class="sxs-lookup"><span data-stu-id="2500b-3064">A keyword from Keyword_south_africa_identification_number is found.</span></span>
- <span data-ttu-id="2500b-3065">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="2500b-3065">The checksum passes.</span></span>

```
<!-- South Africa Identification Number -->
<Entity id="e2adf7cb-8ea6-4048-a2ed-d89eb65f2780" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_south_africa_identification_number"/>
     <Match idRef="Keyword_south_africa_identification_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="2500b-3066">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="2500b-3066">Keywords</span></span>
   
#### <a name="keywordsouthafricaidentificationnumber"></a><span data-ttu-id="2500b-3067">Keyword_south_africa_identification_number</span><span class="sxs-lookup"><span data-stu-id="2500b-3067">Keyword_south_africa_identification_number</span></span>

- <span data-ttu-id="2500b-3068">Carta di identità</span><span class="sxs-lookup"><span data-stu-id="2500b-3068">Identity card</span></span>
- <span data-ttu-id="2500b-3069">ID</span><span class="sxs-lookup"><span data-stu-id="2500b-3069">ID</span></span>
- <span data-ttu-id="2500b-3070">Identificazione</span><span class="sxs-lookup"><span data-stu-id="2500b-3070">Identification</span></span> 
   
## <a name="south-korea-resident-registration-number"></a><span data-ttu-id="2500b-3071">Corea del Sud - Numero di registrazione dei residenti</span><span class="sxs-lookup"><span data-stu-id="2500b-3071">South Korea Resident Registration Number</span></span>

### <a name="format"></a><span data-ttu-id="2500b-3072">Formato</span><span class="sxs-lookup"><span data-stu-id="2500b-3072">Format</span></span>

<span data-ttu-id="2500b-3073">13 cifre contenenti un segno meno</span><span class="sxs-lookup"><span data-stu-id="2500b-3073">13 digits containing a hyphen</span></span>

### <a name="pattern"></a><span data-ttu-id="2500b-3074">Modello</span><span class="sxs-lookup"><span data-stu-id="2500b-3074">Pattern</span></span>

<span data-ttu-id="2500b-3075">13 cifre:</span><span class="sxs-lookup"><span data-stu-id="2500b-3075">13 digits:</span></span>
- <span data-ttu-id="2500b-3076">Sei cifre nel formato AAMMGG, ovvero la data di nascita</span><span class="sxs-lookup"><span data-stu-id="2500b-3076">Six digits in the format YYMMDD which are the date of birth</span></span> 
- <span data-ttu-id="2500b-3077">Una lineetta</span><span class="sxs-lookup"><span data-stu-id="2500b-3077">A hyphen</span></span> 
- <span data-ttu-id="2500b-3078">Una cifra determinata dal secolo e dal sesso </span><span class="sxs-lookup"><span data-stu-id="2500b-3078">One digit determined by the century and gender</span></span> 
- <span data-ttu-id="2500b-3079">Codice di quattro cifre dell’area geografica di nascita </span><span class="sxs-lookup"><span data-stu-id="2500b-3079">Four-digit region-of-birth code</span></span> 
- <span data-ttu-id="2500b-3080">Una cifra utilizzata per distinguere persone i cui numeri precedenti sono uguali </span><span class="sxs-lookup"><span data-stu-id="2500b-3080">One digit used to differentiate people for whom the preceding numbers are identical</span></span> 
- <span data-ttu-id="2500b-3081">Una cifra di controllo.</span><span class="sxs-lookup"><span data-stu-id="2500b-3081">A check digit.</span></span>

### <a name="checksum"></a><span data-ttu-id="2500b-3082">Checksum</span><span class="sxs-lookup"><span data-stu-id="2500b-3082">Checksum</span></span>

<span data-ttu-id="2500b-3083">Sì</span><span class="sxs-lookup"><span data-stu-id="2500b-3083">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="2500b-3084">Definizione</span><span class="sxs-lookup"><span data-stu-id="2500b-3084">Definition</span></span>

<span data-ttu-id="2500b-3085">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="2500b-3085">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2500b-3086">La funzione Func_south_korea_resident_number trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="2500b-3086">The function Func_south_korea_resident_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="2500b-3087">Viene trovata una parola chiave da Keyword_south_korea_resident_number.</span><span class="sxs-lookup"><span data-stu-id="2500b-3087">A keyword from Keyword_south_korea_resident_number is found.</span></span>
- <span data-ttu-id="2500b-3088">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="2500b-3088">The checksum passes.</span></span>

<span data-ttu-id="2500b-3089">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="2500b-3089">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2500b-3090">La funzione Func_south_korea_resident_number trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="2500b-3090">The function Func_south_korea_resident_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="2500b-3091">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="2500b-3091">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="2500b-3092">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="2500b-3092">Keywords</span></span>
   
#### <a name="keywordsouthkorearesidentnumber"></a><span data-ttu-id="2500b-3093">Keyword_south_korea_resident_number</span><span class="sxs-lookup"><span data-stu-id="2500b-3093">Keyword_south_korea_resident_number</span></span>

- <span data-ttu-id="2500b-3094">Carta di identità</span><span class="sxs-lookup"><span data-stu-id="2500b-3094">National ID card</span></span> 
- <span data-ttu-id="2500b-3095">Numero di registrazione del cittadino</span><span class="sxs-lookup"><span data-stu-id="2500b-3095">Citizen's Registration Number</span></span> 
- <span data-ttu-id="2500b-3096">Jumin deungnok beonho</span><span class="sxs-lookup"><span data-stu-id="2500b-3096">Jumin deungnok beonho</span></span> 
- <span data-ttu-id="2500b-3097">RRN</span><span class="sxs-lookup"><span data-stu-id="2500b-3097">RRN</span></span> 
- <span data-ttu-id="2500b-3098">주민등록번호</span><span class="sxs-lookup"><span data-stu-id="2500b-3098">주민등록번호</span></span>
   
## <a name="spain-social-security-number-ssn"></a><span data-ttu-id="2500b-3099">Spagna - Numero di previdenza sociale (SSN)</span><span class="sxs-lookup"><span data-stu-id="2500b-3099">Spain Social Security Number (SSN)</span></span>

### <a name="format"></a><span data-ttu-id="2500b-3100">Formato</span><span class="sxs-lookup"><span data-stu-id="2500b-3100">Format</span></span>

<span data-ttu-id="2500b-3101">11-12 cifre</span><span class="sxs-lookup"><span data-stu-id="2500b-3101">11-12 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="2500b-3102">Modello</span><span class="sxs-lookup"><span data-stu-id="2500b-3102">Pattern</span></span>

<span data-ttu-id="2500b-3103">11-12 cifre:</span><span class="sxs-lookup"><span data-stu-id="2500b-3103">11-12 digits:</span></span>
- <span data-ttu-id="2500b-3104">Due cifre</span><span class="sxs-lookup"><span data-stu-id="2500b-3104">Two digits</span></span> 
- <span data-ttu-id="2500b-3105">Una barra (facoltativa)</span><span class="sxs-lookup"><span data-stu-id="2500b-3105">A forward slash (optional)</span></span> 
- <span data-ttu-id="2500b-3106">7-8 cifre</span><span class="sxs-lookup"><span data-stu-id="2500b-3106">7-8 digits</span></span> 
- <span data-ttu-id="2500b-3107">Una barra (facoltativa)</span><span class="sxs-lookup"><span data-stu-id="2500b-3107">A forward slash (optional)</span></span> 
- <span data-ttu-id="2500b-3108">Due cifre</span><span class="sxs-lookup"><span data-stu-id="2500b-3108">Two digits</span></span>

### <a name="checksum"></a><span data-ttu-id="2500b-3109">Checksum</span><span class="sxs-lookup"><span data-stu-id="2500b-3109">Checksum</span></span>

<span data-ttu-id="2500b-3110">Sì</span><span class="sxs-lookup"><span data-stu-id="2500b-3110">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="2500b-3111">Definizione</span><span class="sxs-lookup"><span data-stu-id="2500b-3111">Definition</span></span>

<span data-ttu-id="2500b-3112">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="2500b-3112">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2500b-3113">La funzione Func_spanish_social_security_number restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="2500b-3113">The function Func_spanish_social_security_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="2500b-3114">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="2500b-3114">The checksum passes.</span></span>

```
<!-- Spain SSN -->
<Entity id="5df987c0-8eae-4bce-ace7-b316347f3070" patternsProximity="300" recommendedConfidence="85">
    <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_spanish_social_security_number" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="2500b-3115">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="2500b-3115">Keywords</span></span>

<span data-ttu-id="2500b-3116">Nessuno</span><span class="sxs-lookup"><span data-stu-id="2500b-3116">None</span></span>

## <a name="sql-server-connection-string"></a><span data-ttu-id="2500b-3117">Stringa di connessione di SQL Server</span><span class="sxs-lookup"><span data-stu-id="2500b-3117">SQL Server Connection String</span></span>

### <a name="format"></a><span data-ttu-id="2500b-3118">Formato</span><span class="sxs-lookup"><span data-stu-id="2500b-3118">Format</span></span>

<span data-ttu-id="2500b-3119">Stringa "ID utente", "ID utente", "UID" o "UserId" seguito dai caratteri e dalle stringhe delineati nel modello seguente.</span><span class="sxs-lookup"><span data-stu-id="2500b-3119">The string "User Id", "User ID", "uid", or "UserId" followed by the characters and strings outlined in the pattern below.</span></span>

### <a name="pattern"></a><span data-ttu-id="2500b-3120">Modello</span><span class="sxs-lookup"><span data-stu-id="2500b-3120">Pattern</span></span>

- <span data-ttu-id="2500b-3121">Stringa "ID utente", "ID utente", "UID" o "UserId"</span><span class="sxs-lookup"><span data-stu-id="2500b-3121">The string "User Id", "User ID", "uid", or "UserId"</span></span>
- <span data-ttu-id="2500b-3122">Qualsiasi combinazione tra 1-200 lettere, cifre, simboli, caratteri speciali o spazi in maiuscolo o minuscolo</span><span class="sxs-lookup"><span data-stu-id="2500b-3122">Any combination of between 1-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="2500b-3123">La stringa "password" o "pwd", dove "pwd" non è preceduta da una lettera minuscola</span><span class="sxs-lookup"><span data-stu-id="2500b-3123">The string "Password" or "pwd" where "pwd" is not preceded by a lowercase letter</span></span>
- <span data-ttu-id="2500b-3124">Segno di uguale (=)</span><span class="sxs-lookup"><span data-stu-id="2500b-3124">An equal sign (=)</span></span>
- <span data-ttu-id="2500b-3125">Qualsiasi carattere non costituito da un segno di dollaro ($), un simbolo di percentuale (%), un simbolo maggiore di (>), un simbolo (@), una virgoletta ("), un punto e virgola (;), una parentesi graffa sinistra ([) o una parentesi quadra sinistra ({)</span><span class="sxs-lookup"><span data-stu-id="2500b-3125">Any character that is not a dollar sign ($), percent symbol (%), greater than symbol (>), at symbol (@), quotation mark ("), semicolon (;), left brace ([), or left bracket ({)</span></span>
- <span data-ttu-id="2500b-3126">Qualsiasi combinazione di 7-128 caratteri che non sono un punto e virgola (;), barra (/) o virgolette (")</span><span class="sxs-lookup"><span data-stu-id="2500b-3126">Any combination of 7-128 characters that are not a semicolon (;), forward slash (/), or quotation mark (")</span></span>
- <span data-ttu-id="2500b-3127">Un punto e virgola (;) o virgolette (")</span><span class="sxs-lookup"><span data-stu-id="2500b-3127">A semicolon (;) or quotation mark (")</span></span>

### <a name="checksum"></a><span data-ttu-id="2500b-3128">Checksum</span><span class="sxs-lookup"><span data-stu-id="2500b-3128">Checksum</span></span>

<span data-ttu-id="2500b-3129">No</span><span class="sxs-lookup"><span data-stu-id="2500b-3129">No</span></span>

### <a name="definition"></a><span data-ttu-id="2500b-3130">Definizione</span><span class="sxs-lookup"><span data-stu-id="2500b-3130">Definition</span></span>

<span data-ttu-id="2500b-3131">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="2500b-3131">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2500b-3132">L'espressione regolare CEP_Regex_SQLServerConnectionString trova il contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="2500b-3132">The regular expression CEP_Regex_SQLServerConnectionString finds content that matches the pattern.</span></span>
- <span data-ttu-id="2500b-3133">**Non** viene trovata una parola chiave da CEP_GlobalFilter.</span><span class="sxs-lookup"><span data-stu-id="2500b-3133">A keyword from CEP_GlobalFilter is **not** found.</span></span>
- <span data-ttu-id="2500b-3134">L'espressione regolare CEP_PasswordPlaceHolder non \*\*\*\* trova contenuto corrispondente al modello.</span><span class="sxs-lookup"><span data-stu-id="2500b-3134">The regular expression CEP_PasswordPlaceHolder does **not** find content that matches the pattern.</span></span>
- <span data-ttu-id="2500b-3135">L'espressione regolare CEP_CommonExampleKeywords non \*\*\*\* trova contenuto corrispondente al modello.</span><span class="sxs-lookup"><span data-stu-id="2500b-3135">The regular expression CEP_CommonExampleKeywords does **not** find content that matches the pattern.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="2500b-3136">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="2500b-3136">Keywords</span></span>

#### <a name="cepglobalfilter"></a><span data-ttu-id="2500b-3137">CEP_GlobalFilter</span><span class="sxs-lookup"><span data-stu-id="2500b-3137">CEP_GlobalFilter</span></span>

- <span data-ttu-id="2500b-3138">some-password</span><span class="sxs-lookup"><span data-stu-id="2500b-3138">some-password</span></span>
- <span data-ttu-id="2500b-3139">somepassword</span><span class="sxs-lookup"><span data-stu-id="2500b-3139">somepassword</span></span>
- <span data-ttu-id="2500b-3140">secretPassword</span><span class="sxs-lookup"><span data-stu-id="2500b-3140">secretPassword</span></span>
- <span data-ttu-id="2500b-3141">esempio</span><span class="sxs-lookup"><span data-stu-id="2500b-3141">sample</span></span>

#### <a name="ceppasswordplaceholder"></a><span data-ttu-id="2500b-3142">CEP_PasswordPlaceHolder</span><span class="sxs-lookup"><span data-stu-id="2500b-3142">CEP_PasswordPlaceHolder</span></span>

<span data-ttu-id="2500b-3143">Si noti che tecnicamente questo tipo di informazioni riservate identifica queste parole chiave utilizzando un'espressione regolare, non un elenco di parola chiave.</span><span class="sxs-lookup"><span data-stu-id="2500b-3143">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="2500b-3144">Password o pwd seguito da 0-2 spazi, un segno di uguale (=), 0-2 spazi e un asterisco (\*)-----------------</span><span class="sxs-lookup"><span data-stu-id="2500b-3144">Password or pwd followed by 0-2 spaces, an equal sign (=), 0-2 spaces, and an asterisk (\*) --OR--</span></span>
- <span data-ttu-id="2500b-3145">Password o pwd seguito da:</span><span class="sxs-lookup"><span data-stu-id="2500b-3145">Password or pwd followed by:</span></span>
    - <span data-ttu-id="2500b-3146">Segno di uguale (=)</span><span class="sxs-lookup"><span data-stu-id="2500b-3146">Equal sign (=)</span></span>
    - <span data-ttu-id="2500b-3147">Valore minore di (<)</span><span class="sxs-lookup"><span data-stu-id="2500b-3147">Less than symbol (<)</span></span>
    - <span data-ttu-id="2500b-3148">Qualsiasi combinazione di 1-200 caratteri che sono lettere maiuscole o minuscole, cifre, asterisco (\*), segno meno (-), sottolineatura (_) o carattere dello spazio vuoto</span><span class="sxs-lookup"><span data-stu-id="2500b-3148">Any combination of 1-200 characters that are upper- or lowercase letters, digits, an asterisk (\*), hyphen (-), underline (_), or whitespace character</span></span>
    - <span data-ttu-id="2500b-3149">Simbolo maggiore di (>)</span><span class="sxs-lookup"><span data-stu-id="2500b-3149">Greater than symbol (>)</span></span>

#### <a name="cepcommonexamplekeywords"></a><span data-ttu-id="2500b-3150">CEP_CommonExampleKeywords</span><span class="sxs-lookup"><span data-stu-id="2500b-3150">CEP_CommonExampleKeywords</span></span>

<span data-ttu-id="2500b-3151">Si noti che tecnicamente questo tipo di informazioni riservate identifica queste parole chiave utilizzando un'espressione regolare, non un elenco di parola chiave.</span><span class="sxs-lookup"><span data-stu-id="2500b-3151">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="2500b-3152">contoso</span><span class="sxs-lookup"><span data-stu-id="2500b-3152">contoso</span></span>
- <span data-ttu-id="2500b-3153">Fabrikam</span><span class="sxs-lookup"><span data-stu-id="2500b-3153">fabrikam</span></span>
- <span data-ttu-id="2500b-3154">Northwind</span><span class="sxs-lookup"><span data-stu-id="2500b-3154">northwind</span></span>
- <span data-ttu-id="2500b-3155">sandbox</span><span class="sxs-lookup"><span data-stu-id="2500b-3155">sandbox</span></span>
- <span data-ttu-id="2500b-3156">OneBox</span><span class="sxs-lookup"><span data-stu-id="2500b-3156">onebox</span></span>
- <span data-ttu-id="2500b-3157">localhost</span><span class="sxs-lookup"><span data-stu-id="2500b-3157">localhost</span></span>
- <span data-ttu-id="2500b-3158">127.0.0.1</span><span class="sxs-lookup"><span data-stu-id="2500b-3158">127.0.0.1</span></span>
- <span data-ttu-id="2500b-3159">testacs.</span><span class="sxs-lookup"><span data-stu-id="2500b-3159">testacs.</span></span><!--no-hyperlink--><span data-ttu-id="2500b-3160">com</span><span class="sxs-lookup"><span data-stu-id="2500b-3160">com</span></span>
- <span data-ttu-id="2500b-3161">s-int.</span><span class="sxs-lookup"><span data-stu-id="2500b-3161">s-int.</span></span><!--no-hyperlink--><span data-ttu-id="2500b-3162">NET</span><span class="sxs-lookup"><span data-stu-id="2500b-3162">net</span></span>

## <a name="sweden-national-id"></a><span data-ttu-id="2500b-3163">Svezia - Identificativo nazionale</span><span class="sxs-lookup"><span data-stu-id="2500b-3163">Sweden National ID</span></span>

### <a name="format"></a><span data-ttu-id="2500b-3164">Formato</span><span class="sxs-lookup"><span data-stu-id="2500b-3164">Format</span></span>

<span data-ttu-id="2500b-3165">10 o 12 cifre e un delimitatore facoltativo</span><span class="sxs-lookup"><span data-stu-id="2500b-3165">10 or 12 digits and an optional delimiter</span></span>

### <a name="pattern"></a><span data-ttu-id="2500b-3166">Modello</span><span class="sxs-lookup"><span data-stu-id="2500b-3166">Pattern</span></span>

<span data-ttu-id="2500b-3167">10 o 12 cifre e un delimitatore facoltativo:</span><span class="sxs-lookup"><span data-stu-id="2500b-3167">10 or 12 digits and an optional delimiter:</span></span>
- <span data-ttu-id="2500b-3168">2-4 cifre (facoltative)</span><span class="sxs-lookup"><span data-stu-id="2500b-3168">2-4 digits (optional)</span></span> 
- <span data-ttu-id="2500b-3169">Sei cifre nel formato data AAMMGG</span><span class="sxs-lookup"><span data-stu-id="2500b-3169">Six digits in date format YYMMDD</span></span> 
- <span data-ttu-id="2500b-3170">Delimitatore di "-" o "+" (facoltativo) più</span><span class="sxs-lookup"><span data-stu-id="2500b-3170">Delimiter of "-" or "+" (optional), plus</span></span>
- <span data-ttu-id="2500b-3171">Quattro cifre</span><span class="sxs-lookup"><span data-stu-id="2500b-3171">Four digits</span></span>

### <a name="checksum"></a><span data-ttu-id="2500b-3172">Checksum</span><span class="sxs-lookup"><span data-stu-id="2500b-3172">Checksum</span></span>

<span data-ttu-id="2500b-3173">Sì</span><span class="sxs-lookup"><span data-stu-id="2500b-3173">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="2500b-3174">Definizione</span><span class="sxs-lookup"><span data-stu-id="2500b-3174">Definition</span></span>

<span data-ttu-id="2500b-3175">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="2500b-3175">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2500b-3176">La funzione Func_swedish_national_identifier restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="2500b-3176">The function Func_swedish_national_identifier finds content that matches the pattern.</span></span>
- <span data-ttu-id="2500b-3177">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="2500b-3177">The checksum passes.</span></span>

```
<!-- Sweden National ID -->
<Entity id="f69aaf40-79be-4fac-8f05-fd1910d272c8" patternsProximity="300" recommendedConfidence="85">
    <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_swedish_national_identifier" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="2500b-3178">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="2500b-3178">Keywords</span></span>

<span data-ttu-id="2500b-3179">No</span><span class="sxs-lookup"><span data-stu-id="2500b-3179">No</span></span>
   
## <a name="sweden-passport-number"></a><span data-ttu-id="2500b-3180">Svezia - Numero di passaporto</span><span class="sxs-lookup"><span data-stu-id="2500b-3180">Sweden Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="2500b-3181">Formato</span><span class="sxs-lookup"><span data-stu-id="2500b-3181">Format</span></span>

<span data-ttu-id="2500b-3182">Otto cifre</span><span class="sxs-lookup"><span data-stu-id="2500b-3182">Eight digits</span></span>

### <a name="pattern"></a><span data-ttu-id="2500b-3183">Modello</span><span class="sxs-lookup"><span data-stu-id="2500b-3183">Pattern</span></span>

<span data-ttu-id="2500b-3184">Otto cifre consecutive</span><span class="sxs-lookup"><span data-stu-id="2500b-3184">Eight consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="2500b-3185">Checksum</span><span class="sxs-lookup"><span data-stu-id="2500b-3185">Checksum</span></span>

<span data-ttu-id="2500b-3186">No</span><span class="sxs-lookup"><span data-stu-id="2500b-3186">No</span></span>

### <a name="definition"></a><span data-ttu-id="2500b-3187">Definizione</span><span class="sxs-lookup"><span data-stu-id="2500b-3187">Definition</span></span>

<span data-ttu-id="2500b-3188">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="2500b-3188">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2500b-3189">L'espressione regolare Regex_sweden_passport_number restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="2500b-3189">The regular expression Regex_sweden_passport_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="2500b-3190">Si verifica una delle situazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="2500b-3190">One of the following is true:</span></span>
    - <span data-ttu-id="2500b-3191">Viene trovata una parola chiave da Keyword_passport.</span><span class="sxs-lookup"><span data-stu-id="2500b-3191">A keyword from Keyword_passport is found.</span></span>
    - <span data-ttu-id="2500b-3192">Viene trovata una parola chiave da Keyword_sweden_passport.</span><span class="sxs-lookup"><span data-stu-id="2500b-3192">A keyword from Keyword_sweden_passport is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="2500b-3193">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="2500b-3193">Keywords</span></span>
   
#### <a name="keywordswedenpassport"></a><span data-ttu-id="2500b-3194">Keyword_sweden_passport</span><span class="sxs-lookup"><span data-stu-id="2500b-3194">Keyword_sweden_passport</span></span>

- <span data-ttu-id="2500b-3195">visa requirements</span><span class="sxs-lookup"><span data-stu-id="2500b-3195">visa requirements</span></span> 
- <span data-ttu-id="2500b-3196">Alien Registration Card</span><span class="sxs-lookup"><span data-stu-id="2500b-3196">Alien Registration Card</span></span> 
- <span data-ttu-id="2500b-3197">Schengen visas</span><span class="sxs-lookup"><span data-stu-id="2500b-3197">Schengen visas</span></span> 
- <span data-ttu-id="2500b-3198">Schengen visa</span><span class="sxs-lookup"><span data-stu-id="2500b-3198">Schengen visa</span></span> 
- <span data-ttu-id="2500b-3199">Visa Processing</span><span class="sxs-lookup"><span data-stu-id="2500b-3199">Visa Processing</span></span> 
- <span data-ttu-id="2500b-3200">Visa Type</span><span class="sxs-lookup"><span data-stu-id="2500b-3200">Visa Type</span></span> 
- <span data-ttu-id="2500b-3201">Single Entry</span><span class="sxs-lookup"><span data-stu-id="2500b-3201">Single Entry</span></span> 
- <span data-ttu-id="2500b-3202">Multiple Entry</span><span class="sxs-lookup"><span data-stu-id="2500b-3202">Multiple Entry</span></span> 
- <span data-ttu-id="2500b-3203">G3 Processing Fees</span><span class="sxs-lookup"><span data-stu-id="2500b-3203">G3 Processing Fees</span></span> 

#### <a name="keywordpassport"></a><span data-ttu-id="2500b-3204">Keyword_passport</span><span class="sxs-lookup"><span data-stu-id="2500b-3204">Keyword_passport</span></span>

- <span data-ttu-id="2500b-3205">Passport Number</span><span class="sxs-lookup"><span data-stu-id="2500b-3205">Passport Number</span></span> 
- <span data-ttu-id="2500b-3206">Passport No</span><span class="sxs-lookup"><span data-stu-id="2500b-3206">Passport No</span></span> 
- <span data-ttu-id="2500b-3207">Passport#</span><span class="sxs-lookup"><span data-stu-id="2500b-3207">Passport #</span></span> 
- <span data-ttu-id="2500b-3208">Passaporto</span><span class="sxs-lookup"><span data-stu-id="2500b-3208">Passport#</span></span> 
- <span data-ttu-id="2500b-3209">PassportID</span><span class="sxs-lookup"><span data-stu-id="2500b-3209">PassportID</span></span> 
- <span data-ttu-id="2500b-3210">Passportno</span><span class="sxs-lookup"><span data-stu-id="2500b-3210">Passportno</span></span> 
- <span data-ttu-id="2500b-3211">passportnumber</span><span class="sxs-lookup"><span data-stu-id="2500b-3211">passportnumber</span></span> 
- <span data-ttu-id="2500b-3212">パスポート</span><span class="sxs-lookup"><span data-stu-id="2500b-3212">パスポート</span></span> 
- <span data-ttu-id="2500b-3213">パスポート番号</span><span class="sxs-lookup"><span data-stu-id="2500b-3213">パスポート番号</span></span> 
- <span data-ttu-id="2500b-3214">パスポートのNum</span><span class="sxs-lookup"><span data-stu-id="2500b-3214">パスポートのNum</span></span> 
- <span data-ttu-id="2500b-3215">パスポート＃</span><span class="sxs-lookup"><span data-stu-id="2500b-3215">パスポート＃</span></span> 
- <span data-ttu-id="2500b-3216">Numéro de passeport</span><span class="sxs-lookup"><span data-stu-id="2500b-3216">Numéro de passeport</span></span> 
- <span data-ttu-id="2500b-3217">Passeport n °</span><span class="sxs-lookup"><span data-stu-id="2500b-3217">Passeport n °</span></span> 
- <span data-ttu-id="2500b-3218">Passeport Non</span><span class="sxs-lookup"><span data-stu-id="2500b-3218">Passeport Non</span></span> 
- <span data-ttu-id="2500b-3219">Passeport#</span><span class="sxs-lookup"><span data-stu-id="2500b-3219">Passeport #</span></span> 
- <span data-ttu-id="2500b-3220">Passeport</span><span class="sxs-lookup"><span data-stu-id="2500b-3220">Passeport#</span></span> 
- <span data-ttu-id="2500b-3221">PasseportNon</span><span class="sxs-lookup"><span data-stu-id="2500b-3221">PasseportNon</span></span> 
- <span data-ttu-id="2500b-3222">Passeportn °</span><span class="sxs-lookup"><span data-stu-id="2500b-3222">Passeportn °</span></span> 
   
## <a name="swift-code"></a><span data-ttu-id="2500b-3223">Codice SWIFT</span><span class="sxs-lookup"><span data-stu-id="2500b-3223">SWIFT Code</span></span>

### <a name="format"></a><span data-ttu-id="2500b-3224">Formato</span><span class="sxs-lookup"><span data-stu-id="2500b-3224">Format</span></span>

<span data-ttu-id="2500b-3225">Quattro lettere seguite da 5-31 lettere o cifre</span><span class="sxs-lookup"><span data-stu-id="2500b-3225">Four letters followed by 5-31 letters or digits</span></span>

### <a name="pattern"></a><span data-ttu-id="2500b-3226">Modello</span><span class="sxs-lookup"><span data-stu-id="2500b-3226">Pattern</span></span>

<span data-ttu-id="2500b-3227">Quattro lettere seguite da 5-31 lettere o cifre:</span><span class="sxs-lookup"><span data-stu-id="2500b-3227">Four letters followed by 5-31 letters or digits:</span></span>
- <span data-ttu-id="2500b-3228">Codice ABI di quattro cifre (senza distinzione tra maiuscole/minuscole)</span><span class="sxs-lookup"><span data-stu-id="2500b-3228">Four-letter bank code (not case sensitive)</span></span> 
- <span data-ttu-id="2500b-3229">Uno spazio facoltativo</span><span class="sxs-lookup"><span data-stu-id="2500b-3229">An optional space</span></span> 
- <span data-ttu-id="2500b-3230">4-28 lettere o cifre (BBAN)</span><span class="sxs-lookup"><span data-stu-id="2500b-3230">4-28 letters or digits (the Basic Bank Account Number (BBAN))</span></span> 
- <span data-ttu-id="2500b-3231">Uno spazio facoltativo</span><span class="sxs-lookup"><span data-stu-id="2500b-3231">An optional space</span></span> 
- <span data-ttu-id="2500b-3232">1-3 lettere o cifre (resto del BBAN)</span><span class="sxs-lookup"><span data-stu-id="2500b-3232">1-3 letters or digits (remainder of the BBAN)</span></span>

### <a name="checksum"></a><span data-ttu-id="2500b-3233">Checksum</span><span class="sxs-lookup"><span data-stu-id="2500b-3233">Checksum</span></span>

<span data-ttu-id="2500b-3234">No</span><span class="sxs-lookup"><span data-stu-id="2500b-3234">No</span></span>

### <a name="definition"></a><span data-ttu-id="2500b-3235">Definizione</span><span class="sxs-lookup"><span data-stu-id="2500b-3235">Definition</span></span>

<span data-ttu-id="2500b-3236">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="2500b-3236">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2500b-3237">L'espressione regolare Regex_swift restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="2500b-3237">The regular expression Regex_swift finds content that matches the pattern.</span></span>
- <span data-ttu-id="2500b-3238">Viene trovata una parola chiave da Keyword_swift.</span><span class="sxs-lookup"><span data-stu-id="2500b-3238">A keyword from Keyword_swift is found.</span></span>

```
<Entity id="cb2ab58c-9cb8-4c81-baf8-a4e106791df4" patternsProximity="300" recommendedConfidence="75">
<Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_swift" />
        <Match idRef="Keyword_swift" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="2500b-3239">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="2500b-3239">Keywords</span></span>
   
#### <a name="keywordswift"></a><span data-ttu-id="2500b-3240">Keyword_swift</span><span class="sxs-lookup"><span data-stu-id="2500b-3240">Keyword_swift</span></span>

- <span data-ttu-id="2500b-3241">international organization for standardization 9362</span><span class="sxs-lookup"><span data-stu-id="2500b-3241">international organization for standardization 9362</span></span> 
- <span data-ttu-id="2500b-3242">iso 9362</span><span class="sxs-lookup"><span data-stu-id="2500b-3242">iso 9362</span></span> 
- <span data-ttu-id="2500b-3243">iso9362</span><span class="sxs-lookup"><span data-stu-id="2500b-3243">iso9362</span></span> 
- <span data-ttu-id="2500b-3244">Swift\#</span><span class="sxs-lookup"><span data-stu-id="2500b-3244">swift\#</span></span> 
- <span data-ttu-id="2500b-3245">swiftcode</span><span class="sxs-lookup"><span data-stu-id="2500b-3245">swiftcode</span></span> 
- <span data-ttu-id="2500b-3246">swiftnumber</span><span class="sxs-lookup"><span data-stu-id="2500b-3246">swiftnumber</span></span> 
- <span data-ttu-id="2500b-3247">swiftroutingnumber</span><span class="sxs-lookup"><span data-stu-id="2500b-3247">swiftroutingnumber</span></span> 
- <span data-ttu-id="2500b-3248">swift code</span><span class="sxs-lookup"><span data-stu-id="2500b-3248">swift code</span></span> 
- <span data-ttu-id="2500b-3249">swift number #</span><span class="sxs-lookup"><span data-stu-id="2500b-3249">swift number #</span></span> 
- <span data-ttu-id="2500b-3250">swift routing number</span><span class="sxs-lookup"><span data-stu-id="2500b-3250">swift routing number</span></span> 
- <span data-ttu-id="2500b-3251">bic number</span><span class="sxs-lookup"><span data-stu-id="2500b-3251">bic number</span></span> 
- <span data-ttu-id="2500b-3252">bic code</span><span class="sxs-lookup"><span data-stu-id="2500b-3252">bic code</span></span> 
- <span data-ttu-id="2500b-3253">BIC\#</span><span class="sxs-lookup"><span data-stu-id="2500b-3253">bic \#</span></span> 
- <span data-ttu-id="2500b-3254">BIC\#</span><span class="sxs-lookup"><span data-stu-id="2500b-3254">bic\#</span></span> 
- <span data-ttu-id="2500b-3255">bank identifier code</span><span class="sxs-lookup"><span data-stu-id="2500b-3255">bank identifier code</span></span> 
- <span data-ttu-id="2500b-3256">標準化 9362</span><span class="sxs-lookup"><span data-stu-id="2500b-3256">標準化9362</span></span> 
- <span data-ttu-id="2500b-3257">迅速＃</span><span class="sxs-lookup"><span data-stu-id="2500b-3257">迅速＃</span></span> 
- <span data-ttu-id="2500b-3258">SWIFTコード</span><span class="sxs-lookup"><span data-stu-id="2500b-3258">SWIFTコード</span></span> 
- <span data-ttu-id="2500b-3259">SWIFT番号</span><span class="sxs-lookup"><span data-stu-id="2500b-3259">SWIFT番号</span></span> 
- <span data-ttu-id="2500b-3260">迅速なルーティング番号</span><span class="sxs-lookup"><span data-stu-id="2500b-3260">迅速なルーティング番号</span></span> 
- <span data-ttu-id="2500b-3261">BIC番号</span><span class="sxs-lookup"><span data-stu-id="2500b-3261">BIC番号</span></span> 
- <span data-ttu-id="2500b-3262">BICコード</span><span class="sxs-lookup"><span data-stu-id="2500b-3262">BICコード</span></span> 
- <span data-ttu-id="2500b-3263">銀行識別コードのための国際組織</span><span class="sxs-lookup"><span data-stu-id="2500b-3263">銀行識別コードのための国際組織</span></span> 
- <span data-ttu-id="2500b-3264">Organisation internationale de normalisation 9362</span><span class="sxs-lookup"><span data-stu-id="2500b-3264">Organisation internationale de normalisation 9362</span></span> 
- <span data-ttu-id="2500b-3265">rapide\#</span><span class="sxs-lookup"><span data-stu-id="2500b-3265">rapide \#</span></span> 
- <span data-ttu-id="2500b-3266">code SWIFT</span><span class="sxs-lookup"><span data-stu-id="2500b-3266">code SWIFT</span></span> 
- <span data-ttu-id="2500b-3267">le numéro de swift</span><span class="sxs-lookup"><span data-stu-id="2500b-3267">le numéro de swift</span></span> 
- <span data-ttu-id="2500b-3268">swift numéro d'acheminement</span><span class="sxs-lookup"><span data-stu-id="2500b-3268">swift numéro d'acheminement</span></span> 
- <span data-ttu-id="2500b-3269">le numéro BIC</span><span class="sxs-lookup"><span data-stu-id="2500b-3269">le numéro BIC</span></span> 
- <span data-ttu-id="2500b-3270">\#BIC</span><span class="sxs-lookup"><span data-stu-id="2500b-3270">\# BIC</span></span> 
- <span data-ttu-id="2500b-3271">code identificateur de banque</span><span class="sxs-lookup"><span data-stu-id="2500b-3271">code identificateur de banque</span></span> 
   
## <a name="taiwan-national-id"></a><span data-ttu-id="2500b-3272">Taiwan National ID</span><span class="sxs-lookup"><span data-stu-id="2500b-3272">Taiwan National ID</span></span>

### <a name="format"></a><span data-ttu-id="2500b-3273">Formato</span><span class="sxs-lookup"><span data-stu-id="2500b-3273">Format</span></span>

<span data-ttu-id="2500b-3274">Una lettera (in lingua inglese) seguita da nove cifre</span><span class="sxs-lookup"><span data-stu-id="2500b-3274">One letter (in English) followed by nine digits</span></span>

### <a name="pattern"></a><span data-ttu-id="2500b-3275">Modello</span><span class="sxs-lookup"><span data-stu-id="2500b-3275">Pattern</span></span>

<span data-ttu-id="2500b-3276">Una lettera (in lingua inglese) seguita da nove cifre:</span><span class="sxs-lookup"><span data-stu-id="2500b-3276">One letter (in English) followed by nine digits:</span></span>
- <span data-ttu-id="2500b-3277">Una lettera (in inglese, senza distinzione tra tra maiuscole/minuscole)</span><span class="sxs-lookup"><span data-stu-id="2500b-3277">One letter (in English, not case sensitive)</span></span> 
- <span data-ttu-id="2500b-3278">La cifra "1" o "2"</span><span class="sxs-lookup"><span data-stu-id="2500b-3278">The digit "1" or "2"</span></span> 
- <span data-ttu-id="2500b-3279">Otto cifre</span><span class="sxs-lookup"><span data-stu-id="2500b-3279">Eight digits</span></span>

### <a name="checksum"></a><span data-ttu-id="2500b-3280">Checksum</span><span class="sxs-lookup"><span data-stu-id="2500b-3280">Checksum</span></span>

<span data-ttu-id="2500b-3281">Sì</span><span class="sxs-lookup"><span data-stu-id="2500b-3281">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="2500b-3282">Definizione</span><span class="sxs-lookup"><span data-stu-id="2500b-3282">Definition</span></span>

<span data-ttu-id="2500b-3283">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="2500b-3283">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2500b-3284">La funzione Func_taiwanese_national_id restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="2500b-3284">The function Func_taiwanese_national_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="2500b-3285">Viene trovata una parola chiave da Keyword_taiwanese_national_id.</span><span class="sxs-lookup"><span data-stu-id="2500b-3285">A keyword from Keyword_taiwanese_national_id is found.</span></span>
- <span data-ttu-id="2500b-3286">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="2500b-3286">The checksum passes.</span></span>

```
<!-- Taiwanese National ID -->
<Entity id="4C7BFC34-8DD1-421D-8FB7-6C6182C2AF03" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_taiwanese_national_id" />
          <Match idRef="Keyword_taiwanese_national_id" />
      </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="2500b-3287">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="2500b-3287">Keywords</span></span>

#### <a name="keywordtaiwanesenationalid"></a><span data-ttu-id="2500b-3288">Keyword_taiwanese_national_id</span><span class="sxs-lookup"><span data-stu-id="2500b-3288">Keyword_taiwanese_national_id</span></span>

- <span data-ttu-id="2500b-3289">身份證字號</span><span class="sxs-lookup"><span data-stu-id="2500b-3289">身份證字號</span></span> 
- <span data-ttu-id="2500b-3290">身份證</span><span class="sxs-lookup"><span data-stu-id="2500b-3290">身份證</span></span> 
- <span data-ttu-id="2500b-3291">身份證號碼</span><span class="sxs-lookup"><span data-stu-id="2500b-3291">身份證號碼</span></span> 
- <span data-ttu-id="2500b-3292">身份證號</span><span class="sxs-lookup"><span data-stu-id="2500b-3292">身份證號</span></span> 
- <span data-ttu-id="2500b-3293">身分證字號</span><span class="sxs-lookup"><span data-stu-id="2500b-3293">身分證字號</span></span> 
- <span data-ttu-id="2500b-3294">身分證</span><span class="sxs-lookup"><span data-stu-id="2500b-3294">身分證</span></span> 
- <span data-ttu-id="2500b-3295">身分證號碼</span><span class="sxs-lookup"><span data-stu-id="2500b-3295">身分證號碼</span></span> 
- <span data-ttu-id="2500b-3296">身份證號</span><span class="sxs-lookup"><span data-stu-id="2500b-3296">身份證號</span></span> 
- <span data-ttu-id="2500b-3297">身分證統一編號</span><span class="sxs-lookup"><span data-stu-id="2500b-3297">身分證統一編號</span></span> 
- <span data-ttu-id="2500b-3298">國民身分證統一編號</span><span class="sxs-lookup"><span data-stu-id="2500b-3298">國民身分證統一編號</span></span> 
- <span data-ttu-id="2500b-3299">簽名</span><span class="sxs-lookup"><span data-stu-id="2500b-3299">簽名</span></span> 
- <span data-ttu-id="2500b-3300">蓋章</span><span class="sxs-lookup"><span data-stu-id="2500b-3300">蓋章</span></span> 
- <span data-ttu-id="2500b-3301">簽名或蓋章</span><span class="sxs-lookup"><span data-stu-id="2500b-3301">簽名或蓋章</span></span> 
- <span data-ttu-id="2500b-3302">簽章</span><span class="sxs-lookup"><span data-stu-id="2500b-3302">簽章</span></span>   
   
## <a name="taiwan-passport-number"></a><span data-ttu-id="2500b-3303">	Taiwan - Numero di passaporto</span><span class="sxs-lookup"><span data-stu-id="2500b-3303">Taiwan Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="2500b-3304">Formato</span><span class="sxs-lookup"><span data-stu-id="2500b-3304">Format</span></span>

- <span data-ttu-id="2500b-3305">Numero di passaporto biometrico: nove cifre</span><span class="sxs-lookup"><span data-stu-id="2500b-3305">Biometric passport number: Nine digits</span></span>
- <span data-ttu-id="2500b-3306">Numero di passaporto non biometrico: nove cifre</span><span class="sxs-lookup"><span data-stu-id="2500b-3306">Non-biometric passport number: Nine digits</span></span>

### <a name="pattern"></a><span data-ttu-id="2500b-3307">Modello</span><span class="sxs-lookup"><span data-stu-id="2500b-3307">Pattern</span></span>
<span data-ttu-id="2500b-3308">Numero di passaporto biometrico:</span><span class="sxs-lookup"><span data-stu-id="2500b-3308">Biometric passport number:</span></span>
- <span data-ttu-id="2500b-3309">La cifra "3" </span><span class="sxs-lookup"><span data-stu-id="2500b-3309">The digit "3"</span></span> 
- <span data-ttu-id="2500b-3310">Otto cifre</span><span class="sxs-lookup"><span data-stu-id="2500b-3310">Eight digits</span></span>

<span data-ttu-id="2500b-3311">Numero di passaporto non biometrico:</span><span class="sxs-lookup"><span data-stu-id="2500b-3311">Non-biometric passport number:</span></span>
- <span data-ttu-id="2500b-3312">9 cifre</span><span class="sxs-lookup"><span data-stu-id="2500b-3312">Nine digits</span></span>

### <a name="checksum"></a><span data-ttu-id="2500b-3313">Checksum</span><span class="sxs-lookup"><span data-stu-id="2500b-3313">Checksum</span></span>

<span data-ttu-id="2500b-3314">No</span><span class="sxs-lookup"><span data-stu-id="2500b-3314">No</span></span>

### <a name="definition"></a><span data-ttu-id="2500b-3315">Definizione</span><span class="sxs-lookup"><span data-stu-id="2500b-3315">Definition</span></span>

<span data-ttu-id="2500b-3316">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="2500b-3316">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2500b-3317">L'espressione regolare Regex_taiwan_passport trova il contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="2500b-3317">The regular expression Regex_taiwan_passport finds content that matches the pattern.</span></span>
- <span data-ttu-id="2500b-3318">Viene trovata una parola chiave da Keyword_taiwan_passport.</span><span class="sxs-lookup"><span data-stu-id="2500b-3318">A keyword from Keyword_taiwan_passport is found.</span></span>

```
<!-- Taiwan Passport Number -->
<Entity id="e7251cb4-4c2c-41df-963e-924eb3dae04a" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_taiwan_passport"/>
     <Match idRef="Keyword_taiwan_passport"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="2500b-3319">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="2500b-3319">Keywords</span></span>

#### <a name="keywordtaiwanpassport"></a><span data-ttu-id="2500b-3320">Keyword_taiwan_passport</span><span class="sxs-lookup"><span data-stu-id="2500b-3320">Keyword_taiwan_passport</span></span>

- <span data-ttu-id="2500b-3321">Numero passaporto ROC</span><span class="sxs-lookup"><span data-stu-id="2500b-3321">ROC passport number</span></span> 
- <span data-ttu-id="2500b-3322">Numero passaporto</span><span class="sxs-lookup"><span data-stu-id="2500b-3322">Passport number</span></span> 
- <span data-ttu-id="2500b-3323">N° passaporto</span><span class="sxs-lookup"><span data-stu-id="2500b-3323">Passport no</span></span> 
- <span data-ttu-id="2500b-3324">Num. passaporto
</span><span class="sxs-lookup"><span data-stu-id="2500b-3324">Passport Num</span></span> 
- <span data-ttu-id="2500b-3325">Passport #</span><span class="sxs-lookup"><span data-stu-id="2500b-3325">Passport #</span></span> 
- <span data-ttu-id="2500b-3326">护照</span><span class="sxs-lookup"><span data-stu-id="2500b-3326">护照</span></span> 
- <span data-ttu-id="2500b-3327">中華民國護照</span><span class="sxs-lookup"><span data-stu-id="2500b-3327">中華民國護照</span></span> 
- <span data-ttu-id="2500b-3328">Zhōnghuá Mínguó hùzhào</span><span class="sxs-lookup"><span data-stu-id="2500b-3328">Zhōnghuá Mínguó hùzhào</span></span>
   
## <a name="taiwan-resident-certificate-arctarc-number"></a><span data-ttu-id="2500b-3329">Taiwan - Numero certificato di residenza (ARC/TARC)</span><span class="sxs-lookup"><span data-stu-id="2500b-3329">Taiwan Resident Certificate (ARC/TARC) Number</span></span>

### <a name="format"></a><span data-ttu-id="2500b-3330">Formato</span><span class="sxs-lookup"><span data-stu-id="2500b-3330">Format</span></span>

<span data-ttu-id="2500b-3331">10 lettere e cifre</span><span class="sxs-lookup"><span data-stu-id="2500b-3331">10 letters and digits</span></span>

### <a name="pattern"></a><span data-ttu-id="2500b-3332">Modello</span><span class="sxs-lookup"><span data-stu-id="2500b-3332">Pattern</span></span>

<span data-ttu-id="2500b-3333">10 lettere e cifre:</span><span class="sxs-lookup"><span data-stu-id="2500b-3333">10 letters and digits:</span></span>
- <span data-ttu-id="2500b-3334">Due lettere (senza distinzione tra maiuscole/minuscole)</span><span class="sxs-lookup"><span data-stu-id="2500b-3334">Two letters (not case sensitive)</span></span> 
- <span data-ttu-id="2500b-3335">Otto cifre</span><span class="sxs-lookup"><span data-stu-id="2500b-3335">Eight digits</span></span>

### <a name="checksum"></a><span data-ttu-id="2500b-3336">Checksum</span><span class="sxs-lookup"><span data-stu-id="2500b-3336">Checksum</span></span>

<span data-ttu-id="2500b-3337">No</span><span class="sxs-lookup"><span data-stu-id="2500b-3337">No</span></span>

### <a name="definition"></a><span data-ttu-id="2500b-3338">Definizione</span><span class="sxs-lookup"><span data-stu-id="2500b-3338">Definition</span></span>

<span data-ttu-id="2500b-3339">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="2500b-3339">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2500b-3340">L'espressione regolare Regex_taiwan_resident_certificate trova il contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="2500b-3340">The regular expression Regex_taiwan_resident_certificate finds content that matches the pattern.</span></span>
- <span data-ttu-id="2500b-3341">Viene trovata una parola chiave da Keyword_taiwan_resident_certificate.</span><span class="sxs-lookup"><span data-stu-id="2500b-3341">A keyword from Keyword_taiwan_resident_certificate is found.</span></span>

```
<!-- Taiwan Resident Certificate (ARC/TARC) -->
<Entity id="48269fec-05ea-46ea-b326-f5623a58c6e9" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_taiwan_resident_certificate"/>
     <Match idRef="Keyword_taiwan_resident_certificate"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="2500b-3342">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="2500b-3342">Keywords</span></span>

#### <a name="keywordtaiwanresidentcertificate"></a><span data-ttu-id="2500b-3343">Keyword_taiwan_resident_certificate</span><span class="sxs-lookup"><span data-stu-id="2500b-3343">Keyword_taiwan_resident_certificate</span></span>

- <span data-ttu-id="2500b-3344">Certificato di residenza</span><span class="sxs-lookup"><span data-stu-id="2500b-3344">Resident Certificate</span></span> 
- <span data-ttu-id="2500b-3345">Cert. di resid
</span><span class="sxs-lookup"><span data-stu-id="2500b-3345">Resident Cert</span></span> 
- <span data-ttu-id="2500b-3346">Cert. di resid.
</span><span class="sxs-lookup"><span data-stu-id="2500b-3346">Resident Cert.</span></span> 
- <span data-ttu-id="2500b-3347">Carta d’identità</span><span class="sxs-lookup"><span data-stu-id="2500b-3347">Identification card</span></span> 
- <span data-ttu-id="2500b-3348">Certificato residente straniero</span><span class="sxs-lookup"><span data-stu-id="2500b-3348">Alien Resident Certificate</span></span> 
- <span data-ttu-id="2500b-3349">ARCO</span><span class="sxs-lookup"><span data-stu-id="2500b-3349">ARC</span></span> 
- <span data-ttu-id="2500b-3350">Certificato residente nell’area di Taiwan</span><span class="sxs-lookup"><span data-stu-id="2500b-3350">Taiwan Area Resident Certificate</span></span> 
- <span data-ttu-id="2500b-3351">TARC Tax</span><span class="sxs-lookup"><span data-stu-id="2500b-3351">TARC</span></span> 
- <span data-ttu-id="2500b-3352">居留證</span><span class="sxs-lookup"><span data-stu-id="2500b-3352">居留證</span></span> 
- <span data-ttu-id="2500b-3353">外僑居留證</span><span class="sxs-lookup"><span data-stu-id="2500b-3353">外僑居留證</span></span> 
- <span data-ttu-id="2500b-3354">台灣地區居留證</span><span class="sxs-lookup"><span data-stu-id="2500b-3354">台灣地區居留證</span></span> 

## <a name="thai-population-identification-code"></a><span data-ttu-id="2500b-3355">Codice di identificazione della popolazione tailandese</span><span class="sxs-lookup"><span data-stu-id="2500b-3355">Thai Population Identification Code</span></span>

### <a name="format"></a><span data-ttu-id="2500b-3356">Formato</span><span class="sxs-lookup"><span data-stu-id="2500b-3356">Format</span></span>

<span data-ttu-id="2500b-3357">13 cifre</span><span class="sxs-lookup"><span data-stu-id="2500b-3357">13 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="2500b-3358">Modello</span><span class="sxs-lookup"><span data-stu-id="2500b-3358">Pattern</span></span>

<span data-ttu-id="2500b-3359">13 cifre:</span><span class="sxs-lookup"><span data-stu-id="2500b-3359">13 digits:</span></span>
- <span data-ttu-id="2500b-3360">La prima cifra non è 0 o 9</span><span class="sxs-lookup"><span data-stu-id="2500b-3360">First digit is not 0 or 9</span></span> 
- <span data-ttu-id="2500b-3361">12 cifre</span><span class="sxs-lookup"><span data-stu-id="2500b-3361">12 digits</span></span>

### <a name="checksum"></a><span data-ttu-id="2500b-3362">Checksum</span><span class="sxs-lookup"><span data-stu-id="2500b-3362">Checksum</span></span>

<span data-ttu-id="2500b-3363">Sì</span><span class="sxs-lookup"><span data-stu-id="2500b-3363">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="2500b-3364">Definizione</span><span class="sxs-lookup"><span data-stu-id="2500b-3364">Definition</span></span>

<span data-ttu-id="2500b-3365">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="2500b-3365">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2500b-3366">La funzione Func_Thai_Citizen_Id trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="2500b-3366">The function Func_Thai_Citizen_Id finds content that matches the pattern.</span></span>
- <span data-ttu-id="2500b-3367">Viene trovata una parola chiave da Keyword_Thai_Citizen_Id.</span><span class="sxs-lookup"><span data-stu-id="2500b-3367">A keyword from Keyword_Thai_Citizen_Id is found.</span></span>

<span data-ttu-id="2500b-3368">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="2500b-3368">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2500b-3369">La funzione Func_Thai_Citizen_Id trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="2500b-3369">The function Func_Thai_Citizen_Id finds content that matches the pattern.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="2500b-3370">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="2500b-3370">Keywords</span></span>

#### <a name="keywordthaicitizenid"></a><span data-ttu-id="2500b-3371">Keyword_Thai_Citizen_Id</span><span class="sxs-lookup"><span data-stu-id="2500b-3371">Keyword_Thai_Citizen_Id</span></span>

- <span data-ttu-id="2500b-3372">Numero ID
</span><span class="sxs-lookup"><span data-stu-id="2500b-3372">ID Number</span></span>
- <span data-ttu-id="2500b-3373">Numero di identificazione</span><span class="sxs-lookup"><span data-stu-id="2500b-3373">Identification Number</span></span>
- <span data-ttu-id="2500b-3374">บัตรประชาชน</span><span class="sxs-lookup"><span data-stu-id="2500b-3374">บัตรประชาชน</span></span>
- <span data-ttu-id="2500b-3375">รหัสบัตรประชาชน</span><span class="sxs-lookup"><span data-stu-id="2500b-3375">รหัสบัตรประชาชน</span></span>
- <span data-ttu-id="2500b-3376">บัตรประชาชน</span><span class="sxs-lookup"><span data-stu-id="2500b-3376">บัตรประชาชน</span></span>
- <span data-ttu-id="2500b-3377">รหัสบัตรประชาชน</span><span class="sxs-lookup"><span data-stu-id="2500b-3377">รหัสบัตรประชาชน</span></span>
  
## <a name="turkish-national-identification-number"></a><span data-ttu-id="2500b-3378">Numero di identificazione nazionale turco</span><span class="sxs-lookup"><span data-stu-id="2500b-3378">Turkish National Identification Number</span></span>

### <a name="format"></a><span data-ttu-id="2500b-3379">Formato</span><span class="sxs-lookup"><span data-stu-id="2500b-3379">Format</span></span>

<span data-ttu-id="2500b-3380">11 cifre</span><span class="sxs-lookup"><span data-stu-id="2500b-3380">11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="2500b-3381">Modello</span><span class="sxs-lookup"><span data-stu-id="2500b-3381">Pattern</span></span>

<span data-ttu-id="2500b-3382">11 cifre</span><span class="sxs-lookup"><span data-stu-id="2500b-3382">11 digits</span></span>

### <a name="checksum"></a><span data-ttu-id="2500b-3383">Checksum</span><span class="sxs-lookup"><span data-stu-id="2500b-3383">Checksum</span></span>

<span data-ttu-id="2500b-3384">Sì</span><span class="sxs-lookup"><span data-stu-id="2500b-3384">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="2500b-3385">Definizione</span><span class="sxs-lookup"><span data-stu-id="2500b-3385">Definition</span></span>

<span data-ttu-id="2500b-3386">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="2500b-3386">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2500b-3387">La funzione Func_Turkish_National_Id trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="2500b-3387">The function Func_Turkish_National_Id finds content that matches the pattern.</span></span>
- <span data-ttu-id="2500b-3388">Viene trovata una parola chiave da Keyword_Turkish_National_Id.</span><span class="sxs-lookup"><span data-stu-id="2500b-3388">A keyword from Keyword_Turkish_National_Id is found.</span></span>

<span data-ttu-id="2500b-3389">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="2500b-3389">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2500b-3390">La funzione Func_Turkish_National_Id trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="2500b-3390">The function Func_Turkish_National_Id finds content that matches the pattern.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="2500b-3391">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="2500b-3391">Keywords</span></span>

#### <a name="keywordturkishnationalid"></a><span data-ttu-id="2500b-3392">Keyword_Turkish_National_Id</span><span class="sxs-lookup"><span data-stu-id="2500b-3392">Keyword_Turkish_National_Id</span></span>

- <span data-ttu-id="2500b-3393">TC Kimlik No</span><span class="sxs-lookup"><span data-stu-id="2500b-3393">TC Kimlik No</span></span>
- <span data-ttu-id="2500b-3394">Numarası Kimlik TC</span><span class="sxs-lookup"><span data-stu-id="2500b-3394">TC Kimlik numarası</span></span>
- <span data-ttu-id="2500b-3395">Vatandaşlık numarası</span><span class="sxs-lookup"><span data-stu-id="2500b-3395">Vatandaşlık numarası</span></span>
- <span data-ttu-id="2500b-3396">Vatandaşlık No</span><span class="sxs-lookup"><span data-stu-id="2500b-3396">Vatandaşlık no</span></span>

## <a name="uk-drivers-license-number"></a><span data-ttu-id="2500b-p142">Regno Unito - Numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="2500b-p142">U.K. Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="2500b-3399">Formato</span><span class="sxs-lookup"><span data-stu-id="2500b-3399">Format</span></span>

<span data-ttu-id="2500b-3400">Combinazione di 18 lettere e numeri nel formato specificato</span><span class="sxs-lookup"><span data-stu-id="2500b-3400">Combination of 18 letters and digits in the specified format</span></span>

### <a name="pattern"></a><span data-ttu-id="2500b-3401">Modello</span><span class="sxs-lookup"><span data-stu-id="2500b-3401">Pattern</span></span>

<span data-ttu-id="2500b-3402">18 lettere e cifre:</span><span class="sxs-lookup"><span data-stu-id="2500b-3402">18 letters and digits:</span></span>
- <span data-ttu-id="2500b-3403">Cinque lettere (senza distinzione fra maiuscole/minuscole) o la cifra 9 al posto di una lettera</span><span class="sxs-lookup"><span data-stu-id="2500b-3403">Five letters (not case sensitive) or the digit "9" in place of a letter</span></span> 
- <span data-ttu-id="2500b-3404">Una cifra</span><span class="sxs-lookup"><span data-stu-id="2500b-3404">One digit</span></span> 
- <span data-ttu-id="2500b-3405">5 cifre nel formato data GGMMA relativo alla data di nascita</span><span class="sxs-lookup"><span data-stu-id="2500b-3405">Five digits in the date format DDMMY for date of birth</span></span> 
- <span data-ttu-id="2500b-3406">Due lettere (senza distinzione fra maiuscole/minuscole) o la cifra 9 al posto di una lettera</span><span class="sxs-lookup"><span data-stu-id="2500b-3406">Two letters (not case sensitive) or the digit "9" in place of a letter</span></span> 
- <span data-ttu-id="2500b-3407">Cinque cifre</span><span class="sxs-lookup"><span data-stu-id="2500b-3407">Five digits</span></span>

### <a name="checksum"></a><span data-ttu-id="2500b-3408">Checksum</span><span class="sxs-lookup"><span data-stu-id="2500b-3408">Checksum</span></span>

<span data-ttu-id="2500b-3409">Sì</span><span class="sxs-lookup"><span data-stu-id="2500b-3409">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="2500b-3410">Definizione</span><span class="sxs-lookup"><span data-stu-id="2500b-3410">Definition</span></span>

<span data-ttu-id="2500b-3411">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="2500b-3411">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2500b-3412">La funzione Func_uk_drivers_license restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="2500b-3412">The function Func_uk_drivers_license finds content that matches the pattern.</span></span>
- <span data-ttu-id="2500b-3413">Viene trovata una parola chiave da Keyword_uk_drivers_license.</span><span class="sxs-lookup"><span data-stu-id="2500b-3413">A keyword from Keyword_uk_drivers_license is found.</span></span>
- <span data-ttu-id="2500b-3414">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="2500b-3414">The checksum passes.</span></span>

```
<!-- U.K. Driver's License Number -->
<Entity id="f93de4be-d94c-40df-a8be-461738047551" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_uk_drivers_license" />
        <Match idRef="Keyword_uk_drivers_license" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="2500b-3415">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="2500b-3415">Keywords</span></span>

#### <a name="keywordukdriverslicense"></a><span data-ttu-id="2500b-3416">Keyword_uk_drivers_license</span><span class="sxs-lookup"><span data-stu-id="2500b-3416">Keyword_uk_drivers_license</span></span>

- <span data-ttu-id="2500b-3417">DVLA</span><span class="sxs-lookup"><span data-stu-id="2500b-3417">DVLA</span></span> 
- <span data-ttu-id="2500b-3418">light vans</span><span class="sxs-lookup"><span data-stu-id="2500b-3418">light vans</span></span> 
- <span data-ttu-id="2500b-3419">quadbikes</span><span class="sxs-lookup"><span data-stu-id="2500b-3419">quadbikes</span></span> 
- <span data-ttu-id="2500b-3420">motor cars</span><span class="sxs-lookup"><span data-stu-id="2500b-3420">motor cars</span></span> 
- <span data-ttu-id="2500b-3421">125cc</span><span class="sxs-lookup"><span data-stu-id="2500b-3421">125cc</span></span> 
- <span data-ttu-id="2500b-3422">sidecar</span><span class="sxs-lookup"><span data-stu-id="2500b-3422">sidecar</span></span> 
- <span data-ttu-id="2500b-3423">tricicli</span><span class="sxs-lookup"><span data-stu-id="2500b-3423">tricycles</span></span> 
- <span data-ttu-id="2500b-3424">moto</span><span class="sxs-lookup"><span data-stu-id="2500b-3424">motorcycles</span></span> 
- <span data-ttu-id="2500b-3425">photocard licence</span><span class="sxs-lookup"><span data-stu-id="2500b-3425">photocard licence</span></span> 
- <span data-ttu-id="2500b-3426">learner drivers</span><span class="sxs-lookup"><span data-stu-id="2500b-3426">learner drivers</span></span> 
- <span data-ttu-id="2500b-3427">licence holder</span><span class="sxs-lookup"><span data-stu-id="2500b-3427">licence holder</span></span> 
- <span data-ttu-id="2500b-3428">licence holders</span><span class="sxs-lookup"><span data-stu-id="2500b-3428">licence holders</span></span> 
- <span data-ttu-id="2500b-3429">driving licences</span><span class="sxs-lookup"><span data-stu-id="2500b-3429">driving licences</span></span> 
- <span data-ttu-id="2500b-3430">driving licence</span><span class="sxs-lookup"><span data-stu-id="2500b-3430">driving licence</span></span> 
- <span data-ttu-id="2500b-3431">dual control car</span><span class="sxs-lookup"><span data-stu-id="2500b-3431">dual control car</span></span> 
   
## <a name="uk-electoral-roll-number"></a><span data-ttu-id="2500b-p143">Regno Unito - Numero di iscrizione alle liste elettorali</span><span class="sxs-lookup"><span data-stu-id="2500b-p143">U.K. Electoral Roll Number</span></span>

### <a name="format"></a><span data-ttu-id="2500b-3434">Formato</span><span class="sxs-lookup"><span data-stu-id="2500b-3434">Format</span></span>

<span data-ttu-id="2500b-3435">Due lettere seguite da 1-4 cifre</span><span class="sxs-lookup"><span data-stu-id="2500b-3435">Two letters followed by 1-4 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="2500b-3436">Modello</span><span class="sxs-lookup"><span data-stu-id="2500b-3436">Pattern</span></span>

<span data-ttu-id="2500b-3437">Due lettere (senza distinzione fra maiuscole/minuscole) seguite da 1-4 numeri</span><span class="sxs-lookup"><span data-stu-id="2500b-3437">Two letters (not case sensitive) followed by 1-4 numbers</span></span>

### <a name="checksum"></a><span data-ttu-id="2500b-3438">Checksum</span><span class="sxs-lookup"><span data-stu-id="2500b-3438">Checksum</span></span>

<span data-ttu-id="2500b-3439">No</span><span class="sxs-lookup"><span data-stu-id="2500b-3439">No</span></span>

### <a name="definition"></a><span data-ttu-id="2500b-3440">Definizione</span><span class="sxs-lookup"><span data-stu-id="2500b-3440">Definition</span></span>

<span data-ttu-id="2500b-3441">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="2500b-3441">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2500b-3442">L'espressione regolare Regex_uk_electoral restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="2500b-3442">The regular expression Regex_uk_electoral finds content that matches the pattern.</span></span>
- <span data-ttu-id="2500b-3443">Viene trovata una parola chiave da Keyword_uk_electoral.</span><span class="sxs-lookup"><span data-stu-id="2500b-3443">A keyword from Keyword_uk_electoral is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="2500b-3444">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="2500b-3444">Keywords</span></span>

#### <a name="keywordukelectoral"></a><span data-ttu-id="2500b-3445">Keyword_uk_electoral</span><span class="sxs-lookup"><span data-stu-id="2500b-3445">Keyword_uk_electoral</span></span>

- <span data-ttu-id="2500b-3446">council nomination</span><span class="sxs-lookup"><span data-stu-id="2500b-3446">council nomination</span></span> 
- <span data-ttu-id="2500b-3447">nomination form</span><span class="sxs-lookup"><span data-stu-id="2500b-3447">nomination form</span></span> 
- <span data-ttu-id="2500b-3448">electoral register</span><span class="sxs-lookup"><span data-stu-id="2500b-3448">electoral register</span></span> 
- <span data-ttu-id="2500b-3449">electoral roll</span><span class="sxs-lookup"><span data-stu-id="2500b-3449">electoral roll</span></span>

   
## <a name="uk-national-health-service-number"></a><span data-ttu-id="2500b-p144">Regno Unito - Codice del servizio sanitario nazionale</span><span class="sxs-lookup"><span data-stu-id="2500b-p144">U.K. National Health Service Number</span></span>

### <a name="format"></a><span data-ttu-id="2500b-3452">Formato</span><span class="sxs-lookup"><span data-stu-id="2500b-3452">Format</span></span>

<span data-ttu-id="2500b-3453">10-17 cifre separate da spazi</span><span class="sxs-lookup"><span data-stu-id="2500b-3453">10-17 digits separated by spaces</span></span>

### <a name="pattern"></a><span data-ttu-id="2500b-3454">Modello</span><span class="sxs-lookup"><span data-stu-id="2500b-3454">Pattern</span></span>

<span data-ttu-id="2500b-3455">10-17 cifre:</span><span class="sxs-lookup"><span data-stu-id="2500b-3455">10-17 digits:</span></span>
- <span data-ttu-id="2500b-3456">3 o 10 cifre</span><span class="sxs-lookup"><span data-stu-id="2500b-3456">Either 3 or 10 digits</span></span> 
- <span data-ttu-id="2500b-3457">Uno spazio</span><span class="sxs-lookup"><span data-stu-id="2500b-3457">A space</span></span> 
- <span data-ttu-id="2500b-3458">Tre cifre</span><span class="sxs-lookup"><span data-stu-id="2500b-3458">Three digits</span></span> 
- <span data-ttu-id="2500b-3459">Uno spazio</span><span class="sxs-lookup"><span data-stu-id="2500b-3459">A space</span></span> 
- <span data-ttu-id="2500b-3460">Quattro cifre</span><span class="sxs-lookup"><span data-stu-id="2500b-3460">Four digits</span></span>

### <a name="checksum"></a><span data-ttu-id="2500b-3461">Checksum</span><span class="sxs-lookup"><span data-stu-id="2500b-3461">Checksum</span></span>

<span data-ttu-id="2500b-3462">Sì</span><span class="sxs-lookup"><span data-stu-id="2500b-3462">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="2500b-3463">Definizione</span><span class="sxs-lookup"><span data-stu-id="2500b-3463">Definition</span></span>

<span data-ttu-id="2500b-3464">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="2500b-3464">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2500b-3465">La funzione Func_uk_nhs_number restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="2500b-3465">The function Func_uk_nhs_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="2500b-3466">Si verifica una delle situazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="2500b-3466">One of the following is true:</span></span>
    - <span data-ttu-id="2500b-3467">Viene trovata una parola chiave da Keyword_uk_nhs_number.</span><span class="sxs-lookup"><span data-stu-id="2500b-3467">A keyword from Keyword_uk_nhs_number is found.</span></span>
    - <span data-ttu-id="2500b-3468">Viene trovata una parola chiave da Keyword_uk_nhs_number1.</span><span class="sxs-lookup"><span data-stu-id="2500b-3468">A keyword from Keyword_uk_nhs_number1 is found.</span></span>
    - <span data-ttu-id="2500b-3469">Viene trovata una parola chiave da Keyword_uk_nhs_number_dob.</span><span class="sxs-lookup"><span data-stu-id="2500b-3469">A keyword from Keyword_uk_nhs_number_dob is found.</span></span>
- <span data-ttu-id="2500b-3470">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="2500b-3470">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="2500b-3471">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="2500b-3471">Keywords</span></span>
   
#### <a name="keyworduknhsnumber"></a><span data-ttu-id="2500b-3472">Keyword_uk_nhs_number</span><span class="sxs-lookup"><span data-stu-id="2500b-3472">Keyword_uk_nhs_number</span></span>

- <span data-ttu-id="2500b-3473">national health service</span><span class="sxs-lookup"><span data-stu-id="2500b-3473">national health service</span></span> 
- <span data-ttu-id="2500b-3474">NHS</span><span class="sxs-lookup"><span data-stu-id="2500b-3474">nhs</span></span> 
- <span data-ttu-id="2500b-3475">health services authority</span><span class="sxs-lookup"><span data-stu-id="2500b-3475">health services authority</span></span> 
- <span data-ttu-id="2500b-3476">health authority</span><span class="sxs-lookup"><span data-stu-id="2500b-3476">health authority</span></span>

#### <a name="keyworduknhsnumber1"></a><span data-ttu-id="2500b-3477">Keyword_uk_nhs_number1</span><span class="sxs-lookup"><span data-stu-id="2500b-3477">Keyword_uk_nhs_number1</span></span>

- <span data-ttu-id="2500b-3478">patient id</span><span class="sxs-lookup"><span data-stu-id="2500b-3478">patient id</span></span> 
- <span data-ttu-id="2500b-3479">patient identification</span><span class="sxs-lookup"><span data-stu-id="2500b-3479">patient identification</span></span> 
- <span data-ttu-id="2500b-3480">patient no</span><span class="sxs-lookup"><span data-stu-id="2500b-3480">patient no</span></span> 
- <span data-ttu-id="2500b-3481">patient number</span><span class="sxs-lookup"><span data-stu-id="2500b-3481">patient number</span></span>

#### <a name="keyworduknhsnumberdob"></a><span data-ttu-id="2500b-3482">Keyword_uk_nhs_number_dob</span><span class="sxs-lookup"><span data-stu-id="2500b-3482">Keyword_uk_nhs_number_dob</span></span>

- <span data-ttu-id="2500b-3483">GP</span><span class="sxs-lookup"><span data-stu-id="2500b-3483">GP</span></span> 
- <span data-ttu-id="2500b-3484">DOB</span><span class="sxs-lookup"><span data-stu-id="2500b-3484">DOB</span></span> 
- <span data-ttu-id="2500b-3485">D. O. B</span><span class="sxs-lookup"><span data-stu-id="2500b-3485">D.O.B</span></span> 
- <span data-ttu-id="2500b-3486">Date of Birth</span><span class="sxs-lookup"><span data-stu-id="2500b-3486">Date of Birth</span></span> 
- <span data-ttu-id="2500b-3487">Birth Date</span><span class="sxs-lookup"><span data-stu-id="2500b-3487">Birth Date</span></span> 
   
## <a name="uk-national-insurance-number-nino"></a><span data-ttu-id="2500b-p145">Regno Unito - Numero di assicurazione nazionale (NINO)</span><span class="sxs-lookup"><span data-stu-id="2500b-p145">U.K. National Insurance Number (NINO)</span></span>

### <a name="format"></a><span data-ttu-id="2500b-3490">Formato</span><span class="sxs-lookup"><span data-stu-id="2500b-3490">Format</span></span>

<span data-ttu-id="2500b-3491">7 caratteri o 9 caratteri separati da spazi o trattini</span><span class="sxs-lookup"><span data-stu-id="2500b-3491">7 characters or 9 characters separated by spaces or dashes</span></span>

### <a name="pattern"></a><span data-ttu-id="2500b-3492">Modello</span><span class="sxs-lookup"><span data-stu-id="2500b-3492">Pattern</span></span>

<span data-ttu-id="2500b-3493">Due modelli possibili:</span><span class="sxs-lookup"><span data-stu-id="2500b-3493">Two possible patterns:</span></span>

- <span data-ttu-id="2500b-3494">Due lettere (NINOs valido utilizza solo alcuni caratteri in questo prefisso, che questo modello convalida; senza distinzione tra maiuscole e minuscole)</span><span class="sxs-lookup"><span data-stu-id="2500b-3494">Two letters (valid NINOs use only certain characters in this prefix, which this pattern validates; not case sensitive)</span></span>
- <span data-ttu-id="2500b-3495">Sei cifre</span><span class="sxs-lookup"><span data-stu-id="2500b-3495">Six digits</span></span>
- <span data-ttu-id="2500b-3496">' A ',' B ',' c'o ' d'(come il prefisso, solo alcuni caratteri sono consentiti nel suffisso, senza distinzione tra maiuscole e minuscole)</span><span class="sxs-lookup"><span data-stu-id="2500b-3496">Either 'A', 'B', 'C', or 'D' (like the prefix, only certain characters are allowed in the suffix; not case sensitive)</span></span>

<span data-ttu-id="2500b-3497">O</span><span class="sxs-lookup"><span data-stu-id="2500b-3497">OR</span></span>

- <span data-ttu-id="2500b-3498">Due lettere</span><span class="sxs-lookup"><span data-stu-id="2500b-3498">Two letters</span></span>
- <span data-ttu-id="2500b-3499">Uno spazio o un trattino</span><span class="sxs-lookup"><span data-stu-id="2500b-3499">A space or dash</span></span>
- <span data-ttu-id="2500b-3500">Due cifre</span><span class="sxs-lookup"><span data-stu-id="2500b-3500">Two digits</span></span>
- <span data-ttu-id="2500b-3501">Uno spazio o un trattino</span><span class="sxs-lookup"><span data-stu-id="2500b-3501">A space or dash</span></span>
- <span data-ttu-id="2500b-3502">Due cifre</span><span class="sxs-lookup"><span data-stu-id="2500b-3502">Two digits</span></span>
- <span data-ttu-id="2500b-3503">Uno spazio o un trattino</span><span class="sxs-lookup"><span data-stu-id="2500b-3503">A space or dash</span></span>
- <span data-ttu-id="2500b-3504">Due cifre</span><span class="sxs-lookup"><span data-stu-id="2500b-3504">Two digits</span></span>
- <span data-ttu-id="2500b-3505">Uno spazio o un trattino</span><span class="sxs-lookup"><span data-stu-id="2500b-3505">A space or dash</span></span>
- <span data-ttu-id="2500b-3506">' A ',' B ',' c'o ' d'</span><span class="sxs-lookup"><span data-stu-id="2500b-3506">Either 'A', 'B', 'C', or 'D'</span></span>

### <a name="checksum"></a><span data-ttu-id="2500b-3507">Checksum</span><span class="sxs-lookup"><span data-stu-id="2500b-3507">Checksum</span></span>

<span data-ttu-id="2500b-3508">No</span><span class="sxs-lookup"><span data-stu-id="2500b-3508">No</span></span>

### <a name="definition"></a><span data-ttu-id="2500b-3509">Definizione</span><span class="sxs-lookup"><span data-stu-id="2500b-3509">Definition</span></span>

<span data-ttu-id="2500b-3510">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="2500b-3510">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2500b-3511">La funzione Func_uk_nino restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="2500b-3511">The function Func_uk_nino finds content that matches the pattern.</span></span>
- <span data-ttu-id="2500b-3512">Viene trovata una parola chiave da Keyword_uk_nino.</span><span class="sxs-lookup"><span data-stu-id="2500b-3512">A keyword from Keyword_uk_nino is found.</span></span>

<span data-ttu-id="2500b-3513">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="2500b-3513">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2500b-3514">La funzione Func_uk_nino restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="2500b-3514">The function Func_uk_nino finds content that matches the pattern.</span></span>
- <span data-ttu-id="2500b-3515">Non vengono trovate parole chiave da Keyword_uk_nino.</span><span class="sxs-lookup"><span data-stu-id="2500b-3515">No keyword from Keyword_uk_nino is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="2500b-3516">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="2500b-3516">Keywords</span></span>

#### <a name="keyworduknino"></a><span data-ttu-id="2500b-3517">Keyword_uk_nino</span><span class="sxs-lookup"><span data-stu-id="2500b-3517">Keyword_uk_nino</span></span>

- <span data-ttu-id="2500b-3518">national insurance number</span><span class="sxs-lookup"><span data-stu-id="2500b-3518">national insurance number</span></span> 
- <span data-ttu-id="2500b-3519">national insurance contributions</span><span class="sxs-lookup"><span data-stu-id="2500b-3519">national insurance contributions</span></span> 
- <span data-ttu-id="2500b-3520">protection act</span><span class="sxs-lookup"><span data-stu-id="2500b-3520">protection act</span></span> 
- <span data-ttu-id="2500b-3521">Insurance</span><span class="sxs-lookup"><span data-stu-id="2500b-3521">insurance</span></span> 
- <span data-ttu-id="2500b-3522">social security number</span><span class="sxs-lookup"><span data-stu-id="2500b-3522">social security number</span></span> 
- <span data-ttu-id="2500b-3523">insurance application</span><span class="sxs-lookup"><span data-stu-id="2500b-3523">insurance application</span></span> 
- <span data-ttu-id="2500b-3524">medical application</span><span class="sxs-lookup"><span data-stu-id="2500b-3524">medical application</span></span> 
- <span data-ttu-id="2500b-3525">social insurance</span><span class="sxs-lookup"><span data-stu-id="2500b-3525">social insurance</span></span> 
- <span data-ttu-id="2500b-3526">medical attention</span><span class="sxs-lookup"><span data-stu-id="2500b-3526">medical attention</span></span> 
- <span data-ttu-id="2500b-3527">social security</span><span class="sxs-lookup"><span data-stu-id="2500b-3527">social security</span></span> 
- <span data-ttu-id="2500b-3528">great britain</span><span class="sxs-lookup"><span data-stu-id="2500b-3528">great britain</span></span> 
- <span data-ttu-id="2500b-3529">Insurance</span><span class="sxs-lookup"><span data-stu-id="2500b-3529">insurance</span></span>    
   
## <a name="us--uk-passport-number"></a><span data-ttu-id="2500b-p146">Stati Uniti/Regno Unito - Numero di passaporto</span><span class="sxs-lookup"><span data-stu-id="2500b-p146">U.S. / U.K. Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="2500b-3532">Formato</span><span class="sxs-lookup"><span data-stu-id="2500b-3532">Format</span></span>

<span data-ttu-id="2500b-3533">9 cifre</span><span class="sxs-lookup"><span data-stu-id="2500b-3533">Nine digits</span></span>

### <a name="pattern"></a><span data-ttu-id="2500b-3534">Modello</span><span class="sxs-lookup"><span data-stu-id="2500b-3534">Pattern</span></span>

<span data-ttu-id="2500b-3535">9 cifre consecutive</span><span class="sxs-lookup"><span data-stu-id="2500b-3535">Nine consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="2500b-3536">Checksum</span><span class="sxs-lookup"><span data-stu-id="2500b-3536">Checksum</span></span>

<span data-ttu-id="2500b-3537">No</span><span class="sxs-lookup"><span data-stu-id="2500b-3537">No</span></span>

### <a name="definition"></a><span data-ttu-id="2500b-3538">Definizione</span><span class="sxs-lookup"><span data-stu-id="2500b-3538">Definition</span></span>

<span data-ttu-id="2500b-3539">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="2500b-3539">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2500b-3540">La funzione Func_usa_uk_passport restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="2500b-3540">The function Func_usa_uk_passport finds content that matches the pattern.</span></span>
- <span data-ttu-id="2500b-3541">Viene trovata una parola chiave da Keyword_passport.</span><span class="sxs-lookup"><span data-stu-id="2500b-3541">A keyword from Keyword_passport is found.</span></span>

```
<Entity id="178ec42a-18b4-47cc-85c7-d62c92fd67f8" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_usa_uk_passport" />
        <Match idRef="Keyword_passport" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="2500b-3542">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="2500b-3542">Keywords</span></span>

#### <a name="keywordpassport"></a><span data-ttu-id="2500b-3543">Keyword_passport</span><span class="sxs-lookup"><span data-stu-id="2500b-3543">Keyword_passport</span></span>

- <span data-ttu-id="2500b-3544">Passport Number</span><span class="sxs-lookup"><span data-stu-id="2500b-3544">Passport Number</span></span> 
- <span data-ttu-id="2500b-3545">Passport No</span><span class="sxs-lookup"><span data-stu-id="2500b-3545">Passport No</span></span> 
- <span data-ttu-id="2500b-3546">Passport#</span><span class="sxs-lookup"><span data-stu-id="2500b-3546">Passport #</span></span> 
- <span data-ttu-id="2500b-3547">Passaporto</span><span class="sxs-lookup"><span data-stu-id="2500b-3547">Passport#</span></span> 
- <span data-ttu-id="2500b-3548">PassportID</span><span class="sxs-lookup"><span data-stu-id="2500b-3548">PassportID</span></span> 
- <span data-ttu-id="2500b-3549">Passportno</span><span class="sxs-lookup"><span data-stu-id="2500b-3549">Passportno</span></span> 
- <span data-ttu-id="2500b-3550">passportnumber</span><span class="sxs-lookup"><span data-stu-id="2500b-3550">passportnumber</span></span> 
- <span data-ttu-id="2500b-3551">パスポート</span><span class="sxs-lookup"><span data-stu-id="2500b-3551">パスポート</span></span> 
- <span data-ttu-id="2500b-3552">パスポート番号</span><span class="sxs-lookup"><span data-stu-id="2500b-3552">パスポート番号</span></span> 
- <span data-ttu-id="2500b-3553">パスポートのNum</span><span class="sxs-lookup"><span data-stu-id="2500b-3553">パスポートのNum</span></span> 
- <span data-ttu-id="2500b-3554">パスポート＃</span><span class="sxs-lookup"><span data-stu-id="2500b-3554">パスポート＃</span></span> 
- <span data-ttu-id="2500b-3555">Numéro de passeport</span><span class="sxs-lookup"><span data-stu-id="2500b-3555">Numéro de passeport</span></span> 
- <span data-ttu-id="2500b-3556">Passeport n °</span><span class="sxs-lookup"><span data-stu-id="2500b-3556">Passeport n °</span></span> 
- <span data-ttu-id="2500b-3557">Passeport Non</span><span class="sxs-lookup"><span data-stu-id="2500b-3557">Passeport Non</span></span> 
- <span data-ttu-id="2500b-3558">Passeport#</span><span class="sxs-lookup"><span data-stu-id="2500b-3558">Passeport #</span></span> 
- <span data-ttu-id="2500b-3559">Passeport</span><span class="sxs-lookup"><span data-stu-id="2500b-3559">Passeport#</span></span> 
- <span data-ttu-id="2500b-3560">PasseportNon</span><span class="sxs-lookup"><span data-stu-id="2500b-3560">PasseportNon</span></span> 
- <span data-ttu-id="2500b-3561">Passeportn °</span><span class="sxs-lookup"><span data-stu-id="2500b-3561">Passeportn °</span></span> 
   
## <a name="us-bank-account-number"></a><span data-ttu-id="2500b-3562">Stati Uniti - Numero di conto bancario</span><span class="sxs-lookup"><span data-stu-id="2500b-3562">U.S. Bank Account Number</span></span>

### <a name="format"></a><span data-ttu-id="2500b-3563">Formato</span><span class="sxs-lookup"><span data-stu-id="2500b-3563">Format</span></span>

<span data-ttu-id="2500b-3564">8-17 cifre</span><span class="sxs-lookup"><span data-stu-id="2500b-3564">8-17 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="2500b-3565">Modello</span><span class="sxs-lookup"><span data-stu-id="2500b-3565">Pattern</span></span>

<span data-ttu-id="2500b-3566">8-17 cifre consecutive</span><span class="sxs-lookup"><span data-stu-id="2500b-3566">8-17 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="2500b-3567">Checksum</span><span class="sxs-lookup"><span data-stu-id="2500b-3567">Checksum</span></span>

<span data-ttu-id="2500b-3568">No</span><span class="sxs-lookup"><span data-stu-id="2500b-3568">No</span></span>

### <a name="definition"></a><span data-ttu-id="2500b-3569">Definizione</span><span class="sxs-lookup"><span data-stu-id="2500b-3569">Definition</span></span>

<span data-ttu-id="2500b-3570">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="2500b-3570">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2500b-3571">L'espressione regolare Regex_usa_bank_account_number restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="2500b-3571">The regular expression Regex_usa_bank_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="2500b-3572">Viene trovata una parola chiave da Keyword_usa_Bank_Account.</span><span class="sxs-lookup"><span data-stu-id="2500b-3572">A keyword from Keyword_usa_Bank_Account is found.</span></span>

```
<!-- U.S. Bank Account Number -->
<Entity id="a2ce32a8-f935-4bb6-8e96-2a5157672e2c" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_usa_bank_account_number" />
        <Match idRef="Keyword_usa_Bank_Account" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="2500b-3573">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="2500b-3573">Keywords</span></span>

#### <a name="keywordusabankaccount"></a><span data-ttu-id="2500b-3574">Keyword_usa_Bank_Account</span><span class="sxs-lookup"><span data-stu-id="2500b-3574">Keyword_usa_Bank_Account</span></span>

- <span data-ttu-id="2500b-3575">Checking Account Number</span><span class="sxs-lookup"><span data-stu-id="2500b-3575">Checking Account Number</span></span> 
- <span data-ttu-id="2500b-3576">Checking Account</span><span class="sxs-lookup"><span data-stu-id="2500b-3576">Checking Account</span></span> 
- <span data-ttu-id="2500b-3577">Checking Account #</span><span class="sxs-lookup"><span data-stu-id="2500b-3577">Checking Account #</span></span> 
- <span data-ttu-id="2500b-3578">Checking Acct Number</span><span class="sxs-lookup"><span data-stu-id="2500b-3578">Checking Acct Number</span></span> 
- <span data-ttu-id="2500b-3579">Checking Acct #</span><span class="sxs-lookup"><span data-stu-id="2500b-3579">Checking Acct #</span></span> 
- <span data-ttu-id="2500b-3580">Checking Acct No.</span><span class="sxs-lookup"><span data-stu-id="2500b-3580">Checking Acct No.</span></span> 
- <span data-ttu-id="2500b-3581">Checking Account No.</span><span class="sxs-lookup"><span data-stu-id="2500b-3581">Checking Account No.</span></span> 
- <span data-ttu-id="2500b-3582">Bank Account Number</span><span class="sxs-lookup"><span data-stu-id="2500b-3582">Bank Account Number</span></span> 
- <span data-ttu-id="2500b-3583">Bank Account #</span><span class="sxs-lookup"><span data-stu-id="2500b-3583">Bank Account #</span></span> 
- <span data-ttu-id="2500b-3584">Bank Acct Number</span><span class="sxs-lookup"><span data-stu-id="2500b-3584">Bank Acct Number</span></span> 
- <span data-ttu-id="2500b-3585">Bank Acct #</span><span class="sxs-lookup"><span data-stu-id="2500b-3585">Bank Acct #</span></span> 
- <span data-ttu-id="2500b-3586">Bank Acct No.</span><span class="sxs-lookup"><span data-stu-id="2500b-3586">Bank Acct No.</span></span> 
- <span data-ttu-id="2500b-3587">Bank Account No.</span><span class="sxs-lookup"><span data-stu-id="2500b-3587">Bank Account No.</span></span> 
- <span data-ttu-id="2500b-3588">Savings Account Number</span><span class="sxs-lookup"><span data-stu-id="2500b-3588">Savings Account Number</span></span> 
- <span data-ttu-id="2500b-3589">Savings Account.</span><span class="sxs-lookup"><span data-stu-id="2500b-3589">Savings Account.</span></span> 
- <span data-ttu-id="2500b-3590">Savings Account #</span><span class="sxs-lookup"><span data-stu-id="2500b-3590">Savings Account #</span></span> 
- <span data-ttu-id="2500b-3591">Savings Acct Number</span><span class="sxs-lookup"><span data-stu-id="2500b-3591">Savings Acct Number</span></span> 
- <span data-ttu-id="2500b-3592">Savings Acct #</span><span class="sxs-lookup"><span data-stu-id="2500b-3592">Savings Acct #</span></span> 
- <span data-ttu-id="2500b-3593">Savings Acct No.</span><span class="sxs-lookup"><span data-stu-id="2500b-3593">Savings Acct No.</span></span> 
- <span data-ttu-id="2500b-3594">Savings Account No.</span><span class="sxs-lookup"><span data-stu-id="2500b-3594">Savings Account No.</span></span> 
- <span data-ttu-id="2500b-3595">Debit Account Number</span><span class="sxs-lookup"><span data-stu-id="2500b-3595">Debit Account Number</span></span> 
- <span data-ttu-id="2500b-3596">Debit Account</span><span class="sxs-lookup"><span data-stu-id="2500b-3596">Debit Account</span></span> 
- <span data-ttu-id="2500b-3597">Debit Account #</span><span class="sxs-lookup"><span data-stu-id="2500b-3597">Debit Account #</span></span> 
- <span data-ttu-id="2500b-3598">Debit Acct Number</span><span class="sxs-lookup"><span data-stu-id="2500b-3598">Debit Acct Number</span></span> 
- <span data-ttu-id="2500b-3599">Debit Acct #</span><span class="sxs-lookup"><span data-stu-id="2500b-3599">Debit Acct #</span></span> 
- <span data-ttu-id="2500b-3600">Debit Acct No.</span><span class="sxs-lookup"><span data-stu-id="2500b-3600">Debit Acct No.</span></span> 
- <span data-ttu-id="2500b-3601">Debit Account No.</span><span class="sxs-lookup"><span data-stu-id="2500b-3601">Debit Account No.</span></span> 
   
## <a name="us-drivers-license-number"></a><span data-ttu-id="2500b-3602">Stati Uniti - Numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="2500b-3602">U.S. Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="2500b-3603">Formato</span><span class="sxs-lookup"><span data-stu-id="2500b-3603">Format</span></span>

<span data-ttu-id="2500b-3604">Varia in base allo stato</span><span class="sxs-lookup"><span data-stu-id="2500b-3604">Depends on the state</span></span>

### <a name="pattern"></a><span data-ttu-id="2500b-3605">Modello</span><span class="sxs-lookup"><span data-stu-id="2500b-3605">Pattern</span></span>

<span data-ttu-id="2500b-3606">Varia in base allo stato. Ad esempio, per New York:</span><span class="sxs-lookup"><span data-stu-id="2500b-3606">Depends on the state -- for example, New York:</span></span>
- <span data-ttu-id="2500b-3607">Nove cifre formattate come ddd ddd ddd corrisponderanno.</span><span class="sxs-lookup"><span data-stu-id="2500b-3607">Nine digits formatted like ddd ddd ddd will match.</span></span>
- <span data-ttu-id="2500b-3608">Nove cifre come ddddddddd non corrispondono.</span><span class="sxs-lookup"><span data-stu-id="2500b-3608">Nine digits like ddddddddd will not match.</span></span>

### <a name="checksum"></a><span data-ttu-id="2500b-3609">Checksum</span><span class="sxs-lookup"><span data-stu-id="2500b-3609">Checksum</span></span>

<span data-ttu-id="2500b-3610">No</span><span class="sxs-lookup"><span data-stu-id="2500b-3610">No</span></span>

### <a name="definition"></a><span data-ttu-id="2500b-3611">Definizione</span><span class="sxs-lookup"><span data-stu-id="2500b-3611">Definition</span></span>

<span data-ttu-id="2500b-3612">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="2500b-3612">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2500b-3613">La funzione Func_new_york_drivers_license_number restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="2500b-3613">The function Func_new_york_drivers_license_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="2500b-3614">Viene trovata una parola chiave da Keyword_[state_name]_drivers_license_name.</span><span class="sxs-lookup"><span data-stu-id="2500b-3614">A keyword from Keyword_[state_name]_drivers_license_name is found.</span></span>
- <span data-ttu-id="2500b-3615">Viene trovata una parola chiave da Keyword_us_drivers_license.</span><span class="sxs-lookup"><span data-stu-id="2500b-3615">A keyword from Keyword_us_drivers_license is found.</span></span>

<span data-ttu-id="2500b-3616">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 65%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="2500b-3616">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2500b-3617">La funzione Func_new_york_drivers_license_number restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="2500b-3617">The function Func_new_york_drivers_license_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="2500b-3618">Viene trovata una parola chiave da Keyword_[state_name]_drivers_license_name.</span><span class="sxs-lookup"><span data-stu-id="2500b-3618">A keyword from Keyword_[state_name]_drivers_license_name is found.</span></span>
- <span data-ttu-id="2500b-3619">Viene trovata una parola chiave da Keyword_us_drivers_license_abbreviations.</span><span class="sxs-lookup"><span data-stu-id="2500b-3619">A keyword from Keyword_us_drivers_license_abbreviations is found.</span></span>
- <span data-ttu-id="2500b-3620">Non vengono trovate parole chiave da Keyword_us_drivers_license.</span><span class="sxs-lookup"><span data-stu-id="2500b-3620">No keyword from Keyword_us_drivers_license is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="2500b-3621">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="2500b-3621">Keywords</span></span>

#### <a name="keywordusdriverslicenseabbreviations"></a><span data-ttu-id="2500b-3622">Keyword_us_drivers_license_abbreviations</span><span class="sxs-lookup"><span data-stu-id="2500b-3622">Keyword_us_drivers_license_abbreviations</span></span>

- <span data-ttu-id="2500b-3623">DL</span><span class="sxs-lookup"><span data-stu-id="2500b-3623">DL</span></span> 
- <span data-ttu-id="2500b-3624">DLS</span><span class="sxs-lookup"><span data-stu-id="2500b-3624">DLS</span></span> 
- <span data-ttu-id="2500b-3625">CDL</span><span class="sxs-lookup"><span data-stu-id="2500b-3625">CDL</span></span> 
- <span data-ttu-id="2500b-3626">CDLS</span><span class="sxs-lookup"><span data-stu-id="2500b-3626">CDLS</span></span> 
- <span data-ttu-id="2500b-3627">ID</span><span class="sxs-lookup"><span data-stu-id="2500b-3627">ID</span></span> 
- <span data-ttu-id="2500b-3628">ID</span><span class="sxs-lookup"><span data-stu-id="2500b-3628">IDs</span></span> 
- <span data-ttu-id="2500b-3629">DL</span><span class="sxs-lookup"><span data-stu-id="2500b-3629">DL#</span></span> 
- <span data-ttu-id="2500b-3630">DLS</span><span class="sxs-lookup"><span data-stu-id="2500b-3630">DLS#</span></span> 
- <span data-ttu-id="2500b-3631">CDL</span><span class="sxs-lookup"><span data-stu-id="2500b-3631">CDL#</span></span> 
- <span data-ttu-id="2500b-3632">CDLS</span><span class="sxs-lookup"><span data-stu-id="2500b-3632">CDLS#</span></span> 
- <span data-ttu-id="2500b-3633">ID</span><span class="sxs-lookup"><span data-stu-id="2500b-3633">ID#</span></span>
- <span data-ttu-id="2500b-3634">ID</span><span class="sxs-lookup"><span data-stu-id="2500b-3634">IDs#</span></span> 
- <span data-ttu-id="2500b-3635">ID number</span><span class="sxs-lookup"><span data-stu-id="2500b-3635">ID number</span></span> 
- <span data-ttu-id="2500b-3636">ID numbers</span><span class="sxs-lookup"><span data-stu-id="2500b-3636">ID numbers</span></span> 
- <span data-ttu-id="2500b-3637">DRIVER'LIC</span><span class="sxs-lookup"><span data-stu-id="2500b-3637">LIC</span></span> 
- <span data-ttu-id="2500b-3638">DRIVER'LIC</span><span class="sxs-lookup"><span data-stu-id="2500b-3638">LIC#</span></span> 

#### <a name="keywordusdriverslicense"></a><span data-ttu-id="2500b-3639">Keyword_us_drivers_license</span><span class="sxs-lookup"><span data-stu-id="2500b-3639">Keyword_us_drivers_license</span></span>

- <span data-ttu-id="2500b-3640">DriverLic</span><span class="sxs-lookup"><span data-stu-id="2500b-3640">DriverLic</span></span> 
- <span data-ttu-id="2500b-3641">DriverLics</span><span class="sxs-lookup"><span data-stu-id="2500b-3641">DriverLics</span></span> 
- <span data-ttu-id="2500b-3642">DriverLicense</span><span class="sxs-lookup"><span data-stu-id="2500b-3642">DriverLicense</span></span> 
- <span data-ttu-id="2500b-3643">DriverLicenses</span><span class="sxs-lookup"><span data-stu-id="2500b-3643">DriverLicenses</span></span> 
- <span data-ttu-id="2500b-3644">Driver Lic</span><span class="sxs-lookup"><span data-stu-id="2500b-3644">Driver Lic</span></span> 
- <span data-ttu-id="2500b-3645">Driver Lics</span><span class="sxs-lookup"><span data-stu-id="2500b-3645">Driver Lics</span></span> 
- <span data-ttu-id="2500b-3646">Driver License</span><span class="sxs-lookup"><span data-stu-id="2500b-3646">Driver License</span></span> 
- <span data-ttu-id="2500b-3647">Driver Licenses</span><span class="sxs-lookup"><span data-stu-id="2500b-3647">Driver Licenses</span></span> 
- <span data-ttu-id="2500b-3648">DriversLic</span><span class="sxs-lookup"><span data-stu-id="2500b-3648">DriversLic</span></span> 
- <span data-ttu-id="2500b-3649">DriversLics</span><span class="sxs-lookup"><span data-stu-id="2500b-3649">DriversLics</span></span> 
- <span data-ttu-id="2500b-3650">DriversLicense</span><span class="sxs-lookup"><span data-stu-id="2500b-3650">DriversLicense</span></span> 
- <span data-ttu-id="2500b-3651">DriversLicenses</span><span class="sxs-lookup"><span data-stu-id="2500b-3651">DriversLicenses</span></span> 
- <span data-ttu-id="2500b-3652">Drivers Lic</span><span class="sxs-lookup"><span data-stu-id="2500b-3652">Drivers Lic</span></span> 
- <span data-ttu-id="2500b-3653">Drivers Lics</span><span class="sxs-lookup"><span data-stu-id="2500b-3653">Drivers Lics</span></span> 
- <span data-ttu-id="2500b-3654">Drivers License</span><span class="sxs-lookup"><span data-stu-id="2500b-3654">Drivers License</span></span> 
- <span data-ttu-id="2500b-3655">Drivers Licenses</span><span class="sxs-lookup"><span data-stu-id="2500b-3655">Drivers Licenses</span></span> 
- <span data-ttu-id="2500b-3656">Driver'Lic</span><span class="sxs-lookup"><span data-stu-id="2500b-3656">Driver'Lic</span></span> 
- <span data-ttu-id="2500b-3657">Driver ' LiCS</span><span class="sxs-lookup"><span data-stu-id="2500b-3657">Driver'Lics</span></span> 
- <span data-ttu-id="2500b-3658">Driver ' License</span><span class="sxs-lookup"><span data-stu-id="2500b-3658">Driver'License</span></span> 
- <span data-ttu-id="2500b-3659">Driver ' licenses</span><span class="sxs-lookup"><span data-stu-id="2500b-3659">Driver'Licenses</span></span> 
- <span data-ttu-id="2500b-3660">Driver'Lic</span><span class="sxs-lookup"><span data-stu-id="2500b-3660">Driver' Lic</span></span> 
- <span data-ttu-id="2500b-3661">Driver' Lics</span><span class="sxs-lookup"><span data-stu-id="2500b-3661">Driver' Lics</span></span> 
- <span data-ttu-id="2500b-3662">Driver' License</span><span class="sxs-lookup"><span data-stu-id="2500b-3662">Driver' License</span></span> 
- <span data-ttu-id="2500b-3663">Driver' Licenses</span><span class="sxs-lookup"><span data-stu-id="2500b-3663">Driver' Licenses</span></span>
- <span data-ttu-id="2500b-3664">Driver'sLic</span><span class="sxs-lookup"><span data-stu-id="2500b-3664">Driver'sLic</span></span> 
- <span data-ttu-id="2500b-3665">Driver'sLics</span><span class="sxs-lookup"><span data-stu-id="2500b-3665">Driver'sLics</span></span> 
- <span data-ttu-id="2500b-3666">Secondola</span><span class="sxs-lookup"><span data-stu-id="2500b-3666">Driver'sLicense</span></span> 
- <span data-ttu-id="2500b-3667">Driver'sLicenses</span><span class="sxs-lookup"><span data-stu-id="2500b-3667">Driver'sLicenses</span></span> 
- <span data-ttu-id="2500b-3668">Driver's Lic</span><span class="sxs-lookup"><span data-stu-id="2500b-3668">Driver's Lic</span></span> 
- <span data-ttu-id="2500b-3669">Driver's Lics</span><span class="sxs-lookup"><span data-stu-id="2500b-3669">Driver's Lics</span></span> 
- <span data-ttu-id="2500b-3670">Driver's License</span><span class="sxs-lookup"><span data-stu-id="2500b-3670">Driver's License</span></span> 
- <span data-ttu-id="2500b-3671">Driver's Licenses</span><span class="sxs-lookup"><span data-stu-id="2500b-3671">Driver's Licenses</span></span> 
- <span data-ttu-id="2500b-3672">identification number</span><span class="sxs-lookup"><span data-stu-id="2500b-3672">identification number</span></span> 
- <span data-ttu-id="2500b-3673">identification numbers</span><span class="sxs-lookup"><span data-stu-id="2500b-3673">identification numbers</span></span> 
- <span data-ttu-id="2500b-3674">identification#</span><span class="sxs-lookup"><span data-stu-id="2500b-3674">identification #</span></span> 
- <span data-ttu-id="2500b-3675">id card</span><span class="sxs-lookup"><span data-stu-id="2500b-3675">id card</span></span> 
- <span data-ttu-id="2500b-3676">id cards</span><span class="sxs-lookup"><span data-stu-id="2500b-3676">id cards</span></span> 
- <span data-ttu-id="2500b-3677">identification card</span><span class="sxs-lookup"><span data-stu-id="2500b-3677">identification card</span></span> 
- <span data-ttu-id="2500b-3678">identification cards</span><span class="sxs-lookup"><span data-stu-id="2500b-3678">identification cards</span></span> 
- <span data-ttu-id="2500b-3679">DriverLic#</span><span class="sxs-lookup"><span data-stu-id="2500b-3679">DriverLic#</span></span> 
- <span data-ttu-id="2500b-3680">DriverLics#</span><span class="sxs-lookup"><span data-stu-id="2500b-3680">DriverLics#</span></span> 
- <span data-ttu-id="2500b-3681">DriverLicense#</span><span class="sxs-lookup"><span data-stu-id="2500b-3681">DriverLicense#</span></span> 
- <span data-ttu-id="2500b-3682">DriverLicenses#</span><span class="sxs-lookup"><span data-stu-id="2500b-3682">DriverLicenses#</span></span> 
- <span data-ttu-id="2500b-3683">Driver Lic#</span><span class="sxs-lookup"><span data-stu-id="2500b-3683">Driver Lic#</span></span> 
- <span data-ttu-id="2500b-3684">Driver Lics#</span><span class="sxs-lookup"><span data-stu-id="2500b-3684">Driver Lics#</span></span> 
- <span data-ttu-id="2500b-3685">Driver License#</span><span class="sxs-lookup"><span data-stu-id="2500b-3685">Driver License#</span></span> 
- <span data-ttu-id="2500b-3686">Driver Licenses#</span><span class="sxs-lookup"><span data-stu-id="2500b-3686">Driver Licenses#</span></span> 
- <span data-ttu-id="2500b-3687">DriversLic#</span><span class="sxs-lookup"><span data-stu-id="2500b-3687">DriversLic#</span></span> 
- <span data-ttu-id="2500b-3688">DriversLics#</span><span class="sxs-lookup"><span data-stu-id="2500b-3688">DriversLics#</span></span> 
- <span data-ttu-id="2500b-3689">DriversLicense#</span><span class="sxs-lookup"><span data-stu-id="2500b-3689">DriversLicense#</span></span> 
- <span data-ttu-id="2500b-3690">DriversLicenses#</span><span class="sxs-lookup"><span data-stu-id="2500b-3690">DriversLicenses#</span></span> 
- <span data-ttu-id="2500b-3691">Drivers Lic#</span><span class="sxs-lookup"><span data-stu-id="2500b-3691">Drivers Lic#</span></span> 
- <span data-ttu-id="2500b-3692">Drivers Lics#</span><span class="sxs-lookup"><span data-stu-id="2500b-3692">Drivers Lics#</span></span> 
- <span data-ttu-id="2500b-3693">Drivers License#</span><span class="sxs-lookup"><span data-stu-id="2500b-3693">Drivers License#</span></span> 
- <span data-ttu-id="2500b-3694">Drivers Licenses#</span><span class="sxs-lookup"><span data-stu-id="2500b-3694">Drivers Licenses#</span></span> 
- <span data-ttu-id="2500b-3695">Driver'Lic#</span><span class="sxs-lookup"><span data-stu-id="2500b-3695">Driver'Lic#</span></span> 
- <span data-ttu-id="2500b-3696">Driver ' LiCS</span><span class="sxs-lookup"><span data-stu-id="2500b-3696">Driver'Lics#</span></span> 
- <span data-ttu-id="2500b-3697">Driver ' License</span><span class="sxs-lookup"><span data-stu-id="2500b-3697">Driver'License#</span></span> 
- <span data-ttu-id="2500b-3698">Driver ' licenses</span><span class="sxs-lookup"><span data-stu-id="2500b-3698">Driver'Licenses#</span></span> 
- <span data-ttu-id="2500b-3699">Driver' Lic#</span><span class="sxs-lookup"><span data-stu-id="2500b-3699">Driver' Lic#</span></span> 
- <span data-ttu-id="2500b-3700">Driver' Lics#</span><span class="sxs-lookup"><span data-stu-id="2500b-3700">Driver' Lics#</span></span> 
- <span data-ttu-id="2500b-3701">Driver' License#</span><span class="sxs-lookup"><span data-stu-id="2500b-3701">Driver' License#</span></span> 
- <span data-ttu-id="2500b-3702">Driver' Licenses#</span><span class="sxs-lookup"><span data-stu-id="2500b-3702">Driver' Licenses#</span></span> 
- <span data-ttu-id="2500b-3703">Driver'sLic#</span><span class="sxs-lookup"><span data-stu-id="2500b-3703">Driver'sLic#</span></span> 
- <span data-ttu-id="2500b-3704">Driver'sLics#</span><span class="sxs-lookup"><span data-stu-id="2500b-3704">Driver'sLics#</span></span> 
- <span data-ttu-id="2500b-3705">Secondola</span><span class="sxs-lookup"><span data-stu-id="2500b-3705">Driver'sLicense#</span></span> 
- <span data-ttu-id="2500b-3706">Driver'sLicenses#</span><span class="sxs-lookup"><span data-stu-id="2500b-3706">Driver'sLicenses#</span></span> 
- <span data-ttu-id="2500b-3707">Driver's Lic#</span><span class="sxs-lookup"><span data-stu-id="2500b-3707">Driver's Lic#</span></span> 
- <span data-ttu-id="2500b-3708">Driver's Lics#</span><span class="sxs-lookup"><span data-stu-id="2500b-3708">Driver's Lics#</span></span> 
- <span data-ttu-id="2500b-3709">Driver's License#</span><span class="sxs-lookup"><span data-stu-id="2500b-3709">Driver's License#</span></span> 
- <span data-ttu-id="2500b-3710">Driver's Licenses#</span><span class="sxs-lookup"><span data-stu-id="2500b-3710">Driver's Licenses#</span></span> 
- <span data-ttu-id="2500b-3711">id card#</span><span class="sxs-lookup"><span data-stu-id="2500b-3711">id card#</span></span> 
- <span data-ttu-id="2500b-3712">id cards#</span><span class="sxs-lookup"><span data-stu-id="2500b-3712">id cards#</span></span> 
- <span data-ttu-id="2500b-3713">identification card#</span><span class="sxs-lookup"><span data-stu-id="2500b-3713">identification card#</span></span> 
- <span data-ttu-id="2500b-3714">identification cards#</span><span class="sxs-lookup"><span data-stu-id="2500b-3714">identification cards#</span></span> 


#### <a name="keywordstatenamedriverslicensename"></a><span data-ttu-id="2500b-3715">Keyword_[state_name]_drivers_license_name</span><span class="sxs-lookup"><span data-stu-id="2500b-3715">Keyword_[state_name]_drivers_license_name</span></span>

- <span data-ttu-id="2500b-3716">Abbreviazione dello stato (ad esempio, "NY")</span><span class="sxs-lookup"><span data-stu-id="2500b-3716">State abbreviation (for example, "NY")</span></span> 
- <span data-ttu-id="2500b-3717">Nome dello stato (ad esempio, "New York")</span><span class="sxs-lookup"><span data-stu-id="2500b-3717">State name (for example, "New York")</span></span>    
   
## <a name="us-individual-taxpayer-identification-number-itin"></a><span data-ttu-id="2500b-3718">Stati Uniti - Codice identificativo del contribuente individuale (ITIN)</span><span class="sxs-lookup"><span data-stu-id="2500b-3718">U.S. Individual Taxpayer Identification Number (ITIN)</span></span>

### <a name="format"></a><span data-ttu-id="2500b-3719">Formato</span><span class="sxs-lookup"><span data-stu-id="2500b-3719">Format</span></span>

<span data-ttu-id="2500b-3720">Nove cifre che iniziano con "9" e contengono un "7" o un "8" come quarta cifra. Può essere formattato con spazi e trattini (facoltativo)</span><span class="sxs-lookup"><span data-stu-id="2500b-3720">Nine digits that start with a "9" and contain a "7" or "8" as the fourth digit, optionally formatted with spaces or dashes</span></span>

### <a name="pattern"></a><span data-ttu-id="2500b-3721">Modello</span><span class="sxs-lookup"><span data-stu-id="2500b-3721">Pattern</span></span>

<span data-ttu-id="2500b-3722">Formattato</span><span class="sxs-lookup"><span data-stu-id="2500b-3722">Formatted:</span></span>
- <span data-ttu-id="2500b-3723">La cifra "9"</span><span class="sxs-lookup"><span data-stu-id="2500b-3723">The digit "9"</span></span> 
- <span data-ttu-id="2500b-3724">Due cifre</span><span class="sxs-lookup"><span data-stu-id="2500b-3724">Two digits</span></span> 
- <span data-ttu-id="2500b-3725">Uno spazio o un trattino</span><span class="sxs-lookup"><span data-stu-id="2500b-3725">A space or dash</span></span> 
- <span data-ttu-id="2500b-3726">Un "7" o un "8"</span><span class="sxs-lookup"><span data-stu-id="2500b-3726">A "7" or "8"</span></span> 
- <span data-ttu-id="2500b-3727">Una cifra</span><span class="sxs-lookup"><span data-stu-id="2500b-3727">A digit</span></span> 
- <span data-ttu-id="2500b-3728">Uno spazio o un trattino</span><span class="sxs-lookup"><span data-stu-id="2500b-3728">A space, or dash</span></span> 
- <span data-ttu-id="2500b-3729">Quattro cifre</span><span class="sxs-lookup"><span data-stu-id="2500b-3729">Four digits</span></span>

<span data-ttu-id="2500b-3730">Formattato</span><span class="sxs-lookup"><span data-stu-id="2500b-3730">Unformatted:</span></span>
- <span data-ttu-id="2500b-3731">La cifra "9"</span><span class="sxs-lookup"><span data-stu-id="2500b-3731">The digit "9"</span></span> 
- <span data-ttu-id="2500b-3732">Due cifre</span><span class="sxs-lookup"><span data-stu-id="2500b-3732">Two digits</span></span> 
- <span data-ttu-id="2500b-3733">Un "7" o un "8"</span><span class="sxs-lookup"><span data-stu-id="2500b-3733">A "7" or "8"</span></span> 
- <span data-ttu-id="2500b-3734">Cinque cifre</span><span class="sxs-lookup"><span data-stu-id="2500b-3734">Five digits</span></span>

### <a name="checksum"></a><span data-ttu-id="2500b-3735">Checksum</span><span class="sxs-lookup"><span data-stu-id="2500b-3735">Checksum</span></span>

<span data-ttu-id="2500b-3736">No</span><span class="sxs-lookup"><span data-stu-id="2500b-3736">No</span></span>

### <a name="definition"></a><span data-ttu-id="2500b-3737">Definizione</span><span class="sxs-lookup"><span data-stu-id="2500b-3737">Definition</span></span>

<span data-ttu-id="2500b-3738">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="2500b-3738">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2500b-3739">La funzione Func_formatted_itin restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="2500b-3739">The function Func_formatted_itin finds content that matches the pattern.</span></span>
- <span data-ttu-id="2500b-3740">Si verifica almeno una delle situazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="2500b-3740">At least one of the following is true:</span></span>
    - <span data-ttu-id="2500b-3741">Viene trovata una parola chiave da Keyword_itin.</span><span class="sxs-lookup"><span data-stu-id="2500b-3741">A keyword from Keyword_itin is found.</span></span>
    - <span data-ttu-id="2500b-3742">La funzione Func_us_address rileva un indirizzo nel formato di data corretto.</span><span class="sxs-lookup"><span data-stu-id="2500b-3742">The function Func_us_address finds an address in the right date format.</span></span>
    - <span data-ttu-id="2500b-3743">La funzione Func_us_date rileva una data nel formato corretto.</span><span class="sxs-lookup"><span data-stu-id="2500b-3743">The function Func_us_date finds a date in the right date format.</span></span>
    - <span data-ttu-id="2500b-3744">Viene trovata una parola chiave da Keyword_itin_collaborative.</span><span class="sxs-lookup"><span data-stu-id="2500b-3744">A keyword from Keyword_itin_collaborative is found.</span></span>

<span data-ttu-id="2500b-3745">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="2500b-3745">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2500b-3746">La funzione Func_unformatted_itin restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="2500b-3746">The function Func_unformatted_itin finds content that matches the pattern.</span></span>
- <span data-ttu-id="2500b-3747">Si verifica almeno una delle situazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="2500b-3747">At least one of the following is true:</span></span>
    - <span data-ttu-id="2500b-3748">Viene trovata una parola chiave da Keyword_itin_collaborative.</span><span class="sxs-lookup"><span data-stu-id="2500b-3748">A keyword from Keyword_itin_collaborative is found.</span></span>
    - <span data-ttu-id="2500b-3749">La funzione Func_us_address rileva un indirizzo nel formato di data corretto.</span><span class="sxs-lookup"><span data-stu-id="2500b-3749">The function Func_us_address finds an address in the right date format.</span></span>
    - <span data-ttu-id="2500b-3750">La funzione Func_us_date rileva una data nel formato corretto.</span><span class="sxs-lookup"><span data-stu-id="2500b-3750">The function Func_us_date finds a date in the right date format.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="2500b-3751">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="2500b-3751">Keywords</span></span>

#### <a name="keyworditin"></a><span data-ttu-id="2500b-3752">Keyword_itin</span><span class="sxs-lookup"><span data-stu-id="2500b-3752">Keyword_itin</span></span>

- <span data-ttu-id="2500b-3753">contribuente</span><span class="sxs-lookup"><span data-stu-id="2500b-3753">taxpayer</span></span> 
- <span data-ttu-id="2500b-3754">tax id</span><span class="sxs-lookup"><span data-stu-id="2500b-3754">tax id</span></span> 
- <span data-ttu-id="2500b-3755">tax identification</span><span class="sxs-lookup"><span data-stu-id="2500b-3755">tax identification</span></span> 
- <span data-ttu-id="2500b-3756">Itin</span><span class="sxs-lookup"><span data-stu-id="2500b-3756">itin</span></span> 
- <span data-ttu-id="2500b-3757">SSN</span><span class="sxs-lookup"><span data-stu-id="2500b-3757">ssn</span></span> 
- <span data-ttu-id="2500b-3758">latta</span><span class="sxs-lookup"><span data-stu-id="2500b-3758">tin</span></span> 
- <span data-ttu-id="2500b-3759">social security</span><span class="sxs-lookup"><span data-stu-id="2500b-3759">social security</span></span> 
- <span data-ttu-id="2500b-3760">tax payer</span><span class="sxs-lookup"><span data-stu-id="2500b-3760">tax payer</span></span> 
- <span data-ttu-id="2500b-3761">itins</span><span class="sxs-lookup"><span data-stu-id="2500b-3761">itins</span></span> 
- <span data-ttu-id="2500b-3762">taxid</span><span class="sxs-lookup"><span data-stu-id="2500b-3762">taxid</span></span> 
- <span data-ttu-id="2500b-3763">individual taxpayer</span><span class="sxs-lookup"><span data-stu-id="2500b-3763">individual taxpayer</span></span> 

#### <a name="keyworditincollaborative"></a><span data-ttu-id="2500b-3764">Keyword_itin_collaborative</span><span class="sxs-lookup"><span data-stu-id="2500b-3764">Keyword_itin_collaborative</span></span>

- <span data-ttu-id="2500b-3765">License</span><span class="sxs-lookup"><span data-stu-id="2500b-3765">License</span></span> 
- <span data-ttu-id="2500b-3766">DL</span><span class="sxs-lookup"><span data-stu-id="2500b-3766">DL</span></span> 
- <span data-ttu-id="2500b-3767">DOB</span><span class="sxs-lookup"><span data-stu-id="2500b-3767">DOB</span></span> 
- <span data-ttu-id="2500b-3768">Data di nascita</span><span class="sxs-lookup"><span data-stu-id="2500b-3768">Birthdate</span></span> 
- <span data-ttu-id="2500b-3769">Compleanno</span><span class="sxs-lookup"><span data-stu-id="2500b-3769">Birthday</span></span> 
- <span data-ttu-id="2500b-3770">Date of Birth</span><span class="sxs-lookup"><span data-stu-id="2500b-3770">Date of Birth</span></span> 
   
## <a name="us-social-security-number-ssn"></a><span data-ttu-id="2500b-3771">Stati Uniti - Numero di previdenza sociale (SSN)</span><span class="sxs-lookup"><span data-stu-id="2500b-3771">U.S. Social Security Number (SSN)</span></span>

### <a name="format"></a><span data-ttu-id="2500b-3772">Formato</span><span class="sxs-lookup"><span data-stu-id="2500b-3772">Format</span></span>

<span data-ttu-id="2500b-3773">9 cifre formattate o meno</span><span class="sxs-lookup"><span data-stu-id="2500b-3773">9 digits, which may be in a formatted or unformatted pattern</span></span>

> [!NOTE]
> <span data-ttu-id="2500b-3774">Se emesso prima della metà del 2011, un SSN ha una formattazione complessa in cui alcune parti del numero devono rientrare in alcuni intervalli per essere valide (ma non c'è nessun checksum).</span><span class="sxs-lookup"><span data-stu-id="2500b-3774">If issued before mid-2011, an SSN has strong formatting where certain parts of the number must fall within certain ranges to be valid (but there's no checksum).</span></span>

### <a name="pattern"></a><span data-ttu-id="2500b-3775">Modello</span><span class="sxs-lookup"><span data-stu-id="2500b-3775">Pattern</span></span>

<span data-ttu-id="2500b-3776">Quattro funzioni cercano SNSS in quattro modelli diversi:</span><span class="sxs-lookup"><span data-stu-id="2500b-3776">Four functions look for SSNs in four different patterns:</span></span>
- <span data-ttu-id="2500b-3777">Func_ssn trova SNSS con una formattazione complessa pre2011 che è formattata con trattini o spazi (ddd-dd-dddd o ddd dd dddd)</span><span class="sxs-lookup"><span data-stu-id="2500b-3777">Func_ssn finds SSNs with pre-2011 strong formatting that are formatted with dashes or spaces (ddd-dd-dddd OR ddd dd dddd)</span></span>
- <span data-ttu-id="2500b-3778">Func_unformatted_ssn trova SNSS con una formattazione complessa pre2011 che non è formattata come nove cifre consecutive (ddddddddd)</span><span class="sxs-lookup"><span data-stu-id="2500b-3778">Func_unformatted_ssn finds SSNs with pre-2011 strong formatting that are unformatted as nine consecutive digits (ddddddddd)</span></span>
- <span data-ttu-id="2500b-3779">Func_randomized_formatted_ssn trova post-2011 SNSS formattati con trattini o spazi (ddd-dd-dddd o ddd dd dddd)</span><span class="sxs-lookup"><span data-stu-id="2500b-3779">Func_randomized_formatted_ssn finds post-2011 SSNs that are formatted with dashes or spaces (ddd-dd-dddd OR ddd dd dddd)</span></span>
- <span data-ttu-id="2500b-3780">Func_randomized_unformatted_ssn trova post-2011 SNSS che non sono formattati come nove cifre consecutive (ddddddddd)</span><span class="sxs-lookup"><span data-stu-id="2500b-3780">Func_randomized_unformatted_ssn finds post-2011 SSNs that are unformatted as nine consecutive digits (ddddddddd)</span></span>

### <a name="checksum"></a><span data-ttu-id="2500b-3781">Checksum</span><span class="sxs-lookup"><span data-stu-id="2500b-3781">Checksum</span></span>

<span data-ttu-id="2500b-3782">No</span><span class="sxs-lookup"><span data-stu-id="2500b-3782">No</span></span>


### <a name="definition"></a><span data-ttu-id="2500b-3783">Definizione</span><span class="sxs-lookup"><span data-stu-id="2500b-3783">Definition</span></span>

<span data-ttu-id="2500b-3784">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="2500b-3784">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2500b-3785">La funzione Func_ssn restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="2500b-3785">The function Func_ssn finds content that matches the pattern.</span></span>
- <span data-ttu-id="2500b-3786">Viene trovata una parola chiave da Keyword_ssn.</span><span class="sxs-lookup"><span data-stu-id="2500b-3786">A keyword from Keyword_ssn is found.</span></span>

<span data-ttu-id="2500b-3787">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="2500b-3787">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2500b-3788">La funzione Func_unformatted_ssn trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="2500b-3788">The function Func_unformatted_ssn finds content that matches the pattern.</span></span>
- <span data-ttu-id="2500b-3789">Viene trovata una parola chiave da Keyword_ssn.</span><span class="sxs-lookup"><span data-stu-id="2500b-3789">A keyword from Keyword_ssn is found.</span></span>

<span data-ttu-id="2500b-3790">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 65%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="2500b-3790">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2500b-3791">La funzione Func_randomized_formatted_ssn restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="2500b-3791">The function Func_randomized_formatted_ssn finds content that matches the pattern.</span></span>
- <span data-ttu-id="2500b-3792">Viene trovata una parola chiave da Keyword_ssn.</span><span class="sxs-lookup"><span data-stu-id="2500b-3792">A keyword from Keyword_ssn is found.</span></span>
- <span data-ttu-id="2500b-3793">La funzione Func_ssn non trovare contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="2500b-3793">The function Func_ssn does not find content that matches the pattern.</span></span>

<span data-ttu-id="2500b-3794">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 55%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="2500b-3794">A DLP policy is 55% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="2500b-3795">La funzione Func_randomized_unformatted_ssn restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="2500b-3795">The function Func_randomized_unformatted_ssn finds content that matches the pattern.</span></span>
- <span data-ttu-id="2500b-3796">Viene trovata una parola chiave da Keyword_ssn.</span><span class="sxs-lookup"><span data-stu-id="2500b-3796">A keyword from Keyword_ssn is found.</span></span>
- <span data-ttu-id="2500b-3797">La funzione Func_unformatted_ssn non trovare contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="2500b-3797">The function Func_unformatted_ssn does not find content that matches the pattern.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="2500b-3798">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="2500b-3798">Keywords</span></span>

#### <a name="keywordssn"></a><span data-ttu-id="2500b-3799">Keyword_ssn</span><span class="sxs-lookup"><span data-stu-id="2500b-3799">Keyword_ssn</span></span>

- <span data-ttu-id="2500b-3800">Social Security</span><span class="sxs-lookup"><span data-stu-id="2500b-3800">Social Security</span></span> 
- <span data-ttu-id="2500b-3801">Social Security#</span><span class="sxs-lookup"><span data-stu-id="2500b-3801">Social Security#</span></span> 
- <span data-ttu-id="2500b-3802">Soc Sec</span><span class="sxs-lookup"><span data-stu-id="2500b-3802">Soc Sec</span></span> 
- <span data-ttu-id="2500b-3803">SSN</span><span class="sxs-lookup"><span data-stu-id="2500b-3803">SSN</span></span> 
- <span data-ttu-id="2500b-3804">SNSS</span><span class="sxs-lookup"><span data-stu-id="2500b-3804">SSNS</span></span> 
- <span data-ttu-id="2500b-3805">SSN</span><span class="sxs-lookup"><span data-stu-id="2500b-3805">SSN#</span></span> 
- <span data-ttu-id="2500b-3806">SS</span><span class="sxs-lookup"><span data-stu-id="2500b-3806">SS#</span></span> 
- <span data-ttu-id="2500b-3807">SSID</span><span class="sxs-lookup"><span data-stu-id="2500b-3807">SSID</span></span> 
   

