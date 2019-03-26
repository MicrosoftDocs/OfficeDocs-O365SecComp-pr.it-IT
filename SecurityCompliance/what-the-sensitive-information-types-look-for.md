---
title: Tipi di informazioni riservate disponibili da cercare
ms.author: deniseb
author: denisebmsft
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
ms.openlocfilehash: d161435c75149183289cfbfd6abe79d55e371e31
ms.sourcegitcommit: b688d67935edb036658bb5aa1671328498d5ddd3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2019
ms.locfileid: "30639193"
---
# <a name="what-the-sensitive-information-types-look-for"></a><span data-ttu-id="13996-104">Tipi di informazioni riservate disponibili da cercare</span><span class="sxs-lookup"><span data-stu-id="13996-104">What the sensitive information types look for</span></span>

<span data-ttu-id="13996-105">La prevenzione della perdita di dati (DLP) nel centro &amp; sicurezza e conformità di Office 365 include numerosi tipi di informazioni riservate pronte per l'uso nei criteri DLP.</span><span class="sxs-lookup"><span data-stu-id="13996-105">Data loss prevention (DLP) in the Office 365 Security &amp; Compliance Center includes many sensitive information types that are ready for you to use in your DLP policies.</span></span> <span data-ttu-id="13996-106">In questo argomento vengono elencati tutti questi tipi di informazioni riservate e illustrata la ricerca eseguita dal criterio DLP quando rileva ciascun tipo di informazioni.</span><span class="sxs-lookup"><span data-stu-id="13996-106">This topic lists all of these sensitive information types and shows what a DLP policy looks for when it detects each type.</span></span> <span data-ttu-id="13996-107">Una tipologia di informazioni riservate viene definita da un modello identificato da un'espressione regolare o da una funzione.</span><span class="sxs-lookup"><span data-stu-id="13996-107">A sensitive information type is defined by a pattern that can be identified by a regular expression or a function.</span></span> <span data-ttu-id="13996-108">Inoltre, è possibile utilizzare elementi probatori, ad esempio, parole chiave e checksum per identificare una tipologia di informazioni riservate.</span><span class="sxs-lookup"><span data-stu-id="13996-108">In addition, corroborative evidence such as keywords and checksums can be used to identify a sensitive information type.</span></span> <span data-ttu-id="13996-109">In questa procedura di valutazione vengono usati anche il livello di probabilità e la prossimità.</span><span class="sxs-lookup"><span data-stu-id="13996-109">Confidence level and proximity are also used in the evaluation process.</span></span>
  
## <a name="aba-routing-number"></a><span data-ttu-id="13996-110">Numero di registrazione ABA</span><span class="sxs-lookup"><span data-stu-id="13996-110">ABA Routing Number</span></span>

### <a name="format"></a><span data-ttu-id="13996-111">Formato</span><span class="sxs-lookup"><span data-stu-id="13996-111">Format</span></span>

<span data-ttu-id="13996-112">9 cifre formattate o meno</span><span class="sxs-lookup"><span data-stu-id="13996-112">9 digits which may be in a formatted or unformatted pattern</span></span>

### <a name="pattern"></a><span data-ttu-id="13996-113">Modello</span><span class="sxs-lookup"><span data-stu-id="13996-113">Pattern</span></span>

<span data-ttu-id="13996-114">Formattato</span><span class="sxs-lookup"><span data-stu-id="13996-114">Formatted:</span></span>
- <span data-ttu-id="13996-115">Quattro cifre che iniziano con 0, 1, 2, 3, 6, 7 o 8</span><span class="sxs-lookup"><span data-stu-id="13996-115">Four digits beginning with 0, 1, 2, 3, 6, 7, or 8</span></span>
- <span data-ttu-id="13996-116">Una lineetta</span><span class="sxs-lookup"><span data-stu-id="13996-116">A hyphen</span></span>
- <span data-ttu-id="13996-117">Quattro cifre</span><span class="sxs-lookup"><span data-stu-id="13996-117">Four digits</span></span>
- <span data-ttu-id="13996-118">Una lineetta</span><span class="sxs-lookup"><span data-stu-id="13996-118">A hyphen</span></span>
- <span data-ttu-id="13996-119">Una cifra</span><span class="sxs-lookup"><span data-stu-id="13996-119">A digit</span></span>

<span data-ttu-id="13996-120">Non formattato: 9 cifre consecutive che iniziano con 0, 1, 2, 3, 6, 7 o 8</span><span class="sxs-lookup"><span data-stu-id="13996-120">Unformatted: 9 consecutive digits beginning with 0, 1, 2, 3, 6, 7, or 8</span></span> 

### <a name="checksum"></a><span data-ttu-id="13996-121">Checksum</span><span class="sxs-lookup"><span data-stu-id="13996-121">Checksum</span></span>

<span data-ttu-id="13996-122">No</span><span class="sxs-lookup"><span data-stu-id="13996-122">No</span></span>

### <a name="definition"></a><span data-ttu-id="13996-123">Definizione</span><span class="sxs-lookup"><span data-stu-id="13996-123">Definition</span></span>

<span data-ttu-id="13996-124">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="13996-124">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="13996-125">La funzione Func_aba_routing restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="13996-125">The function Func_aba_routing finds content that matches the pattern.</span></span>
- <span data-ttu-id="13996-126">Viene trovata una parola chiave da Keyword_ABA_Routing.</span><span class="sxs-lookup"><span data-stu-id="13996-126">A keyword from Keyword_ABA_Routing is found.</span></span>

```
<!-- ABA Routing Number -->
<Entity id="cb353f78-2b72-4c3c-8827-92ebe4f69fdf" patternsProximity="300" recommendedConfidence="75">
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_aba_routing" />
        <Match idRef="Keyword_ABA_Routing" />
      </Pattern>
 </Entity>
```


### <a name="keywords"></a><span data-ttu-id="13996-127">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="13996-127">Keywords</span></span>

#### <a name="keywordabarouting"></a><span data-ttu-id="13996-128">Keyword_ABA_Routing</span><span class="sxs-lookup"><span data-stu-id="13996-128">Keyword_ABA_Routing</span></span>

- <span data-ttu-id="13996-129">ABA</span><span class="sxs-lookup"><span data-stu-id="13996-129">aba</span></span>
- <span data-ttu-id="13996-130">aba #</span><span class="sxs-lookup"><span data-stu-id="13996-130">aba #</span></span>
- <span data-ttu-id="13996-131">aba routing #</span><span class="sxs-lookup"><span data-stu-id="13996-131">aba routing #</span></span>
- <span data-ttu-id="13996-132">aba routing number</span><span class="sxs-lookup"><span data-stu-id="13996-132">aba routing number</span></span>
- <span data-ttu-id="13996-133">ABA</span><span class="sxs-lookup"><span data-stu-id="13996-133">aba#</span></span>
- <span data-ttu-id="13996-134">abarouting #</span><span class="sxs-lookup"><span data-stu-id="13996-134">abarouting#</span></span>
- <span data-ttu-id="13996-135">aba number</span><span class="sxs-lookup"><span data-stu-id="13996-135">aba number</span></span>
- <span data-ttu-id="13996-136">abaroutingnumber</span><span class="sxs-lookup"><span data-stu-id="13996-136">abaroutingnumber</span></span>
- <span data-ttu-id="13996-137">american bank association routing #</span><span class="sxs-lookup"><span data-stu-id="13996-137">american bank association routing #</span></span>
- <span data-ttu-id="13996-138">american bank association routing number</span><span class="sxs-lookup"><span data-stu-id="13996-138">american bank association routing number</span></span>
- <span data-ttu-id="13996-139">americanbankassociationrouting #</span><span class="sxs-lookup"><span data-stu-id="13996-139">americanbankassociationrouting#</span></span>
- <span data-ttu-id="13996-140">americanbankassociationroutingnumber</span><span class="sxs-lookup"><span data-stu-id="13996-140">americanbankassociationroutingnumber</span></span>
- <span data-ttu-id="13996-141">bank routing number</span><span class="sxs-lookup"><span data-stu-id="13996-141">bank routing number</span></span>
- <span data-ttu-id="13996-142">bankrouting #</span><span class="sxs-lookup"><span data-stu-id="13996-142">bankrouting#</span></span>
- <span data-ttu-id="13996-143">bankroutingnumber</span><span class="sxs-lookup"><span data-stu-id="13996-143">bankroutingnumber</span></span>
- <span data-ttu-id="13996-144">routing transit number</span><span class="sxs-lookup"><span data-stu-id="13996-144">routing transit number</span></span>
- <span data-ttu-id="13996-145">RTN</span><span class="sxs-lookup"><span data-stu-id="13996-145">RTN</span></span> 
   
## <a name="argentina-national-identity-dni-number"></a><span data-ttu-id="13996-146">Argentina - Numero di identità nazionale (DNI)</span><span class="sxs-lookup"><span data-stu-id="13996-146">Argentina National Identity (DNI) Number</span></span>

### <a name="format"></a><span data-ttu-id="13996-147">Formato</span><span class="sxs-lookup"><span data-stu-id="13996-147">Format</span></span>

<span data-ttu-id="13996-148">Otto cifre separate da spazi</span><span class="sxs-lookup"><span data-stu-id="13996-148">Eight digits separated by periods</span></span>

### <a name="pattern"></a><span data-ttu-id="13996-149">Modello</span><span class="sxs-lookup"><span data-stu-id="13996-149">Pattern</span></span>

<span data-ttu-id="13996-150">Otto cifre</span><span class="sxs-lookup"><span data-stu-id="13996-150">Eight digits:</span></span>
- <span data-ttu-id="13996-151">Due cifre</span><span class="sxs-lookup"><span data-stu-id="13996-151">Two digits</span></span>
- <span data-ttu-id="13996-152">Un punto </span><span class="sxs-lookup"><span data-stu-id="13996-152">A period</span></span>
- <span data-ttu-id="13996-153">Tre cifre</span><span class="sxs-lookup"><span data-stu-id="13996-153">Three digits</span></span>
- <span data-ttu-id="13996-154">Un punto </span><span class="sxs-lookup"><span data-stu-id="13996-154">A period</span></span>
- <span data-ttu-id="13996-155">Tre cifre</span><span class="sxs-lookup"><span data-stu-id="13996-155">Three digits</span></span>

### <a name="checksum"></a><span data-ttu-id="13996-156">Checksum</span><span class="sxs-lookup"><span data-stu-id="13996-156">Checksum</span></span>

<span data-ttu-id="13996-157">No</span><span class="sxs-lookup"><span data-stu-id="13996-157">No</span></span>

### <a name="definition"></a><span data-ttu-id="13996-158">Definizione</span><span class="sxs-lookup"><span data-stu-id="13996-158">Definition</span></span>

<span data-ttu-id="13996-159">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="13996-159">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="13996-160">L'espressione regolare Regex_argentina_national_id trova il contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="13996-160">The regular expression Regex_argentina_national_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="13996-161">Viene trovata una parola chiave da Keyword_argentina_national_id.</span><span class="sxs-lookup"><span data-stu-id="13996-161">A keyword from Keyword_argentina_national_id is found.</span></span>

```
<!-- Argentina National Identity (DNI) Number -->
<Entity id="eefbb00e-8282-433c-8620-8f1da3bffdb2" recommendedConfidence="75" patternsProximity="300">
   <Pattern confidenceLevel="75">
      <IdMatch idRef="Regex_argentina_national_id"/>
      <Match idRef="Keyword_argentina_national_id"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="13996-162">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="13996-162">Keywords</span></span>

#### <a name="keywordargentinanationalid"></a><span data-ttu-id="13996-163">Keyword_argentina_national_id</span><span class="sxs-lookup"><span data-stu-id="13996-163">Keyword_argentina_national_id</span></span>

- <span data-ttu-id="13996-164">Argentina - Numero di identità nazionale</span><span class="sxs-lookup"><span data-stu-id="13996-164">Argentina National Identity number</span></span> 
- <span data-ttu-id="13996-165">Identità</span><span class="sxs-lookup"><span data-stu-id="13996-165">Identity</span></span> 
- <span data-ttu-id="13996-166">Carta di identità nazionale di identificazione</span><span class="sxs-lookup"><span data-stu-id="13996-166">Identification National Identity Card</span></span> 
- <span data-ttu-id="13996-167">DNI</span><span class="sxs-lookup"><span data-stu-id="13996-167">DNI</span></span> 
- <span data-ttu-id="13996-168">Registro nazionale delle persone di NIC</span><span class="sxs-lookup"><span data-stu-id="13996-168">NIC National Registry of Persons</span></span> 
- <span data-ttu-id="13996-169">Documento Nacional de Identidad</span><span class="sxs-lookup"><span data-stu-id="13996-169">Documento Nacional de Identidad</span></span> 
- <span data-ttu-id="13996-170">Registro Nacional de las Personas</span><span class="sxs-lookup"><span data-stu-id="13996-170">Registro Nacional de las Personas</span></span> 
- <span data-ttu-id="13996-171">Identidad</span><span class="sxs-lookup"><span data-stu-id="13996-171">Identidad</span></span> 
- <span data-ttu-id="13996-172">Identificación</span><span class="sxs-lookup"><span data-stu-id="13996-172">Identificación</span></span> 
   
## <a name="australia-bank-account-number"></a><span data-ttu-id="13996-173">Australia - Numero di conto bancario</span><span class="sxs-lookup"><span data-stu-id="13996-173">Australia Bank Account Number</span></span>

### <a name="format"></a><span data-ttu-id="13996-174">Formato</span><span class="sxs-lookup"><span data-stu-id="13996-174">Format</span></span>

<span data-ttu-id="13996-175">6-10 cifre con o senza un numero BSB (Bank/State/Branch)</span><span class="sxs-lookup"><span data-stu-id="13996-175">6-10 digits with or without a bank state branch number</span></span>

### <a name="pattern"></a><span data-ttu-id="13996-176">Modello</span><span class="sxs-lookup"><span data-stu-id="13996-176">Pattern</span></span>

<span data-ttu-id="13996-177">Il numero di conto comprende 6-10 cifre.</span><span class="sxs-lookup"><span data-stu-id="13996-177">Account number is 6-10 digits.</span></span>
<span data-ttu-id="13996-178">Numero BSB australiano:</span><span class="sxs-lookup"><span data-stu-id="13996-178">Australia bank state branch number:</span></span>
- <span data-ttu-id="13996-179">Tre cifre</span><span class="sxs-lookup"><span data-stu-id="13996-179">Three digits</span></span> 
- <span data-ttu-id="13996-180">Una lineetta</span><span class="sxs-lookup"><span data-stu-id="13996-180">A hyphen</span></span> 
- <span data-ttu-id="13996-181">Tre cifre</span><span class="sxs-lookup"><span data-stu-id="13996-181">Three digits</span></span>

### <a name="checksum"></a><span data-ttu-id="13996-182">Checksum</span><span class="sxs-lookup"><span data-stu-id="13996-182">Checksum</span></span>

<span data-ttu-id="13996-183">No</span><span class="sxs-lookup"><span data-stu-id="13996-183">No</span></span>

### <a name="definition"></a><span data-ttu-id="13996-184">Definizione</span><span class="sxs-lookup"><span data-stu-id="13996-184">Definition</span></span>

<span data-ttu-id="13996-185">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="13996-185">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="13996-186">L'espressione regolare Regex_australia_bank_account_number restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="13996-186">The regular expression Regex_australia_bank_account_number finds content that matches the pattern..</span></span>
- <span data-ttu-id="13996-187">Viene trovata una parola chiave da Keyword_australia_bank_account_number.</span><span class="sxs-lookup"><span data-stu-id="13996-187">A keyword from Keyword_australia_bank_account_number is found.</span></span>
- <span data-ttu-id="13996-188">L'espressione regolare Regex_australia_bank_account_number_bsb restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="13996-188">The regular expression Regex_australia_bank_account_number_bsb finds content that matches the pattern.</span></span>

<span data-ttu-id="13996-189">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="13996-189">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="13996-190">L'espressione regolare Regex_australia_bank_account_number restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="13996-190">The regular expression Regex_australia_bank_account_number finds content that matches the pattern..</span></span>
- <span data-ttu-id="13996-191">Viene trovata una parola chiave da Keyword_australia_bank_account_number.</span><span class="sxs-lookup"><span data-stu-id="13996-191">A keyword from Keyword_australia_bank_account_number is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="13996-192">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="13996-192">Keywords</span></span>

#### <a name="keywordaustraliabankaccountnumber"></a><span data-ttu-id="13996-193">Keyword_australia_bank_account_number</span><span class="sxs-lookup"><span data-stu-id="13996-193">Keyword_australia_bank_account_number</span></span>

- <span data-ttu-id="13996-194">swift bank code</span><span class="sxs-lookup"><span data-stu-id="13996-194">swift bank code</span></span>
- <span data-ttu-id="13996-195">correspondent bank</span><span class="sxs-lookup"><span data-stu-id="13996-195">correspondent bank</span></span>
- <span data-ttu-id="13996-196">base currency</span><span class="sxs-lookup"><span data-stu-id="13996-196">base currency</span></span>
- <span data-ttu-id="13996-197">usa account</span><span class="sxs-lookup"><span data-stu-id="13996-197">usa account</span></span>
- <span data-ttu-id="13996-198">holder address</span><span class="sxs-lookup"><span data-stu-id="13996-198">holder address</span></span>
- <span data-ttu-id="13996-199">bank address</span><span class="sxs-lookup"><span data-stu-id="13996-199">bank address</span></span>
- <span data-ttu-id="13996-200">information account</span><span class="sxs-lookup"><span data-stu-id="13996-200">information account</span></span>
- <span data-ttu-id="13996-201">fund transfers</span><span class="sxs-lookup"><span data-stu-id="13996-201">fund transfers</span></span>
- <span data-ttu-id="13996-202">bank charges</span><span class="sxs-lookup"><span data-stu-id="13996-202">bank charges</span></span>
- <span data-ttu-id="13996-203">bank details</span><span class="sxs-lookup"><span data-stu-id="13996-203">bank details</span></span>
- <span data-ttu-id="13996-204">banking information</span><span class="sxs-lookup"><span data-stu-id="13996-204">banking information</span></span>
- <span data-ttu-id="13996-205">full names</span><span class="sxs-lookup"><span data-stu-id="13996-205">full names</span></span>
- <span data-ttu-id="13996-206">AIEA</span><span class="sxs-lookup"><span data-stu-id="13996-206">iaea</span></span>

   
## <a name="australia-drivers-license-number"></a><span data-ttu-id="13996-207">Australia - Numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="13996-207">Australia Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="13996-208">Formato</span><span class="sxs-lookup"><span data-stu-id="13996-208">Format</span></span>

<span data-ttu-id="13996-209">Nove lettere e numeri</span><span class="sxs-lookup"><span data-stu-id="13996-209">Nine letters and digits</span></span>

### <a name="pattern"></a><span data-ttu-id="13996-210">Modello</span><span class="sxs-lookup"><span data-stu-id="13996-210">Pattern</span></span>

<span data-ttu-id="13996-211">Nove lettere e numeri:</span><span class="sxs-lookup"><span data-stu-id="13996-211">Nine letters and digits:</span></span> 

- <span data-ttu-id="13996-212">Due cifre o lettere (senza distinzione tra maiuscole/minuscole)</span><span class="sxs-lookup"><span data-stu-id="13996-212">Two digits or letters (not case sensitive)</span></span> 
- <span data-ttu-id="13996-213">Due cifre</span><span class="sxs-lookup"><span data-stu-id="13996-213">Two digits</span></span> 
- <span data-ttu-id="13996-214">Cinque cifre o lettere (senza distinzione tra maiuscole/minuscole)</span><span class="sxs-lookup"><span data-stu-id="13996-214">Five digits or letters (not case sensitive)</span></span>

<span data-ttu-id="13996-215">O</span><span class="sxs-lookup"><span data-stu-id="13996-215">OR</span></span>

- <span data-ttu-id="13996-216">1-2 lettere facoltative (senza distinzione tra maiuscole/minuscole)</span><span class="sxs-lookup"><span data-stu-id="13996-216">1-2 optional letters (not case sensitive)</span></span> 
- <span data-ttu-id="13996-217">4-9 cifre</span><span class="sxs-lookup"><span data-stu-id="13996-217">4-9 digits</span></span>

<span data-ttu-id="13996-218">O</span><span class="sxs-lookup"><span data-stu-id="13996-218">OR</span></span>

- <span data-ttu-id="13996-219">Nove cifre o lettere (senza distinzione tra maiuscole/minuscole)</span><span class="sxs-lookup"><span data-stu-id="13996-219">Nine digits or letters (not case sensitive)</span></span>

### <a name="checksum"></a><span data-ttu-id="13996-220">Checksum</span><span class="sxs-lookup"><span data-stu-id="13996-220">Checksum</span></span>

<span data-ttu-id="13996-221">No</span><span class="sxs-lookup"><span data-stu-id="13996-221">No</span></span>

### <a name="definition"></a><span data-ttu-id="13996-222">Definizione</span><span class="sxs-lookup"><span data-stu-id="13996-222">Definition</span></span>

<span data-ttu-id="13996-223">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="13996-223">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="13996-224">L'espressione regolare Regex_australia_drivers_license_number restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="13996-224">The regular expression Regex_australia_drivers_license_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="13996-225">Viene trovata una parola chiave da Keyword_australia_drivers_license_number.</span><span class="sxs-lookup"><span data-stu-id="13996-225">A keyword from Keyword_australia_drivers_license_number is found.</span></span>
- <span data-ttu-id="13996-226">Non vengono trovate parole chiava da Keyword_australia_drivers_license_number_exclusions.</span><span class="sxs-lookup"><span data-stu-id="13996-226">No keyword from Keyword_australia_drivers_license_number_exclusions is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="13996-227">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="13996-227">Keywords</span></span>

#### <a name="keywordaustraliadriverslicensenumber"></a><span data-ttu-id="13996-228">Keyword_australia_drivers_license_number</span><span class="sxs-lookup"><span data-stu-id="13996-228">Keyword_australia_drivers_license_number</span></span>

- <span data-ttu-id="13996-229">international driving permits</span><span class="sxs-lookup"><span data-stu-id="13996-229">international driving permits</span></span>
- <span data-ttu-id="13996-230">australian automobile association</span><span class="sxs-lookup"><span data-stu-id="13996-230">australian automobile association</span></span>
- <span data-ttu-id="13996-231">international driving permit</span><span class="sxs-lookup"><span data-stu-id="13996-231">international driving permit</span></span>
- <span data-ttu-id="13996-232">DriverLicence</span><span class="sxs-lookup"><span data-stu-id="13996-232">DriverLicence</span></span>
- <span data-ttu-id="13996-233">DriverLicences</span><span class="sxs-lookup"><span data-stu-id="13996-233">DriverLicences</span></span>
- <span data-ttu-id="13996-234">Driver Lic</span><span class="sxs-lookup"><span data-stu-id="13996-234">Driver Lic</span></span>
- <span data-ttu-id="13996-235">Driver Licence</span><span class="sxs-lookup"><span data-stu-id="13996-235">Driver Licence</span></span>
- <span data-ttu-id="13996-236">Driver Licences</span><span class="sxs-lookup"><span data-stu-id="13996-236">Driver Licences</span></span>
- <span data-ttu-id="13996-237">DriversLic</span><span class="sxs-lookup"><span data-stu-id="13996-237">DriversLic</span></span>
- <span data-ttu-id="13996-238">DriversLicence</span><span class="sxs-lookup"><span data-stu-id="13996-238">DriversLicence</span></span>
- <span data-ttu-id="13996-239">DriversLicences</span><span class="sxs-lookup"><span data-stu-id="13996-239">DriversLicences</span></span>
- <span data-ttu-id="13996-240">Drivers Lic</span><span class="sxs-lookup"><span data-stu-id="13996-240">Drivers Lic</span></span>
- <span data-ttu-id="13996-241">Drivers Lics</span><span class="sxs-lookup"><span data-stu-id="13996-241">Drivers Lics</span></span>
- <span data-ttu-id="13996-242">Drivers Licence</span><span class="sxs-lookup"><span data-stu-id="13996-242">Drivers Licence</span></span>
- <span data-ttu-id="13996-243">Drivers Licences</span><span class="sxs-lookup"><span data-stu-id="13996-243">Drivers Licences</span></span>
- <span data-ttu-id="13996-244">Driver'Lic</span><span class="sxs-lookup"><span data-stu-id="13996-244">Driver'Lic</span></span>
- <span data-ttu-id="13996-245">Driver ' LiCS</span><span class="sxs-lookup"><span data-stu-id="13996-245">Driver'Lics</span></span>
- <span data-ttu-id="13996-246">Driver'Licence</span><span class="sxs-lookup"><span data-stu-id="13996-246">Driver'Licence</span></span>
- <span data-ttu-id="13996-247">Driver'Licences</span><span class="sxs-lookup"><span data-stu-id="13996-247">Driver'Licences</span></span>
- <span data-ttu-id="13996-248">Driver'Lic</span><span class="sxs-lookup"><span data-stu-id="13996-248">Driver' Lic</span></span>
- <span data-ttu-id="13996-249">Driver'Lics</span><span class="sxs-lookup"><span data-stu-id="13996-249">Driver' Lics</span></span>
- <span data-ttu-id="13996-250">Driver'Licence</span><span class="sxs-lookup"><span data-stu-id="13996-250">Driver' Licence</span></span>
- <span data-ttu-id="13996-251">Driver' Licences</span><span class="sxs-lookup"><span data-stu-id="13996-251">Driver' Licences</span></span>
- <span data-ttu-id="13996-252">Driver'sLic</span><span class="sxs-lookup"><span data-stu-id="13996-252">Driver'sLic</span></span>
- <span data-ttu-id="13996-253">Driver'sLics</span><span class="sxs-lookup"><span data-stu-id="13996-253">Driver'sLics</span></span>
- <span data-ttu-id="13996-254">Driver'sLicence</span><span class="sxs-lookup"><span data-stu-id="13996-254">Driver'sLicence</span></span>
- <span data-ttu-id="13996-255">Driver'sLicences</span><span class="sxs-lookup"><span data-stu-id="13996-255">Driver'sLicences</span></span>
- <span data-ttu-id="13996-256">Driver's Lic</span><span class="sxs-lookup"><span data-stu-id="13996-256">Driver's Lic</span></span>
- <span data-ttu-id="13996-257">Driver's Lics</span><span class="sxs-lookup"><span data-stu-id="13996-257">Driver's Lics</span></span>
- <span data-ttu-id="13996-258">Driver's Licence</span><span class="sxs-lookup"><span data-stu-id="13996-258">Driver's Licence</span></span>
- <span data-ttu-id="13996-259">Driver's Licences</span><span class="sxs-lookup"><span data-stu-id="13996-259">Driver's Licences</span></span>
- <span data-ttu-id="13996-260">DriverLic #</span><span class="sxs-lookup"><span data-stu-id="13996-260">DriverLic#</span></span>
- <span data-ttu-id="13996-261">DriverLics #</span><span class="sxs-lookup"><span data-stu-id="13996-261">DriverLics#</span></span>
- <span data-ttu-id="13996-262">DriverLicence #</span><span class="sxs-lookup"><span data-stu-id="13996-262">DriverLicence#</span></span>
- <span data-ttu-id="13996-263">DriverLicences #</span><span class="sxs-lookup"><span data-stu-id="13996-263">DriverLicences#</span></span>
- <span data-ttu-id="13996-264">Driver Lic#</span><span class="sxs-lookup"><span data-stu-id="13996-264">Driver Lic#</span></span>
- <span data-ttu-id="13996-265">Driver Lics#</span><span class="sxs-lookup"><span data-stu-id="13996-265">Driver Lics#</span></span>
- <span data-ttu-id="13996-266">Driver Licence#</span><span class="sxs-lookup"><span data-stu-id="13996-266">Driver Licence#</span></span>
- <span data-ttu-id="13996-267">Driver Licences#</span><span class="sxs-lookup"><span data-stu-id="13996-267">Driver Licences#</span></span>
- <span data-ttu-id="13996-268">DriversLic #</span><span class="sxs-lookup"><span data-stu-id="13996-268">DriversLic#</span></span>
- <span data-ttu-id="13996-269">DriversLics #</span><span class="sxs-lookup"><span data-stu-id="13996-269">DriversLics#</span></span>
- <span data-ttu-id="13996-270">DriversLicence #</span><span class="sxs-lookup"><span data-stu-id="13996-270">DriversLicence#</span></span>
- <span data-ttu-id="13996-271">DriversLicences #</span><span class="sxs-lookup"><span data-stu-id="13996-271">DriversLicences#</span></span>
- <span data-ttu-id="13996-272">Drivers Lic#</span><span class="sxs-lookup"><span data-stu-id="13996-272">Drivers Lic#</span></span>
- <span data-ttu-id="13996-273">Drivers Lics#</span><span class="sxs-lookup"><span data-stu-id="13996-273">Drivers Lics#</span></span>
- <span data-ttu-id="13996-274">Drivers Licence#</span><span class="sxs-lookup"><span data-stu-id="13996-274">Drivers Licence#</span></span>
- <span data-ttu-id="13996-275">Drivers Licences#</span><span class="sxs-lookup"><span data-stu-id="13996-275">Drivers Licences#</span></span>
- <span data-ttu-id="13996-276">Driver'Lic #</span><span class="sxs-lookup"><span data-stu-id="13996-276">Driver'Lic#</span></span>
- <span data-ttu-id="13996-277">Driver ' LiCS</span><span class="sxs-lookup"><span data-stu-id="13996-277">Driver'Lics#</span></span>
- <span data-ttu-id="13996-278">Driver'Licence #</span><span class="sxs-lookup"><span data-stu-id="13996-278">Driver'Licence#</span></span>
- <span data-ttu-id="13996-279">Driver'Licences #</span><span class="sxs-lookup"><span data-stu-id="13996-279">Driver'Licences#</span></span>
- <span data-ttu-id="13996-280">Driver' Lic#</span><span class="sxs-lookup"><span data-stu-id="13996-280">Driver' Lic#</span></span>
- <span data-ttu-id="13996-281">Driver'Lics#</span><span class="sxs-lookup"><span data-stu-id="13996-281">Driver' Lics#</span></span>
- <span data-ttu-id="13996-282">Driver'Licence#</span><span class="sxs-lookup"><span data-stu-id="13996-282">Driver' Licence#</span></span>
- <span data-ttu-id="13996-283">Driver' Licences#</span><span class="sxs-lookup"><span data-stu-id="13996-283">Driver' Licences#</span></span>
- <span data-ttu-id="13996-284">Driver'sLic #</span><span class="sxs-lookup"><span data-stu-id="13996-284">Driver'sLic#</span></span>
- <span data-ttu-id="13996-285">Driver'sLics #</span><span class="sxs-lookup"><span data-stu-id="13996-285">Driver'sLics#</span></span>
- <span data-ttu-id="13996-286">Driver'sLicence #</span><span class="sxs-lookup"><span data-stu-id="13996-286">Driver'sLicence#</span></span>
- <span data-ttu-id="13996-287">Driver'sLicences #</span><span class="sxs-lookup"><span data-stu-id="13996-287">Driver'sLicences#</span></span>
- <span data-ttu-id="13996-288">Driver's Lic#</span><span class="sxs-lookup"><span data-stu-id="13996-288">Driver's Lic#</span></span>
- <span data-ttu-id="13996-289">Driver's Lics#</span><span class="sxs-lookup"><span data-stu-id="13996-289">Driver's Lics#</span></span>
- <span data-ttu-id="13996-290">Driver's Licence#</span><span class="sxs-lookup"><span data-stu-id="13996-290">Driver's Licence#</span></span>
- <span data-ttu-id="13996-291">Driver's Licences#</span><span class="sxs-lookup"><span data-stu-id="13996-291">Driver's Licences#</span></span> 

#### <a name="keywordaustraliadriverslicensenumberexclusions"></a><span data-ttu-id="13996-292">Keyword_australia_drivers_license_number_exclusions</span><span class="sxs-lookup"><span data-stu-id="13996-292">Keyword_australia_drivers_license_number_exclusions</span></span>

- <span data-ttu-id="13996-293">AAA</span><span class="sxs-lookup"><span data-stu-id="13996-293">aaa</span></span>
- <span data-ttu-id="13996-294">DriverLicense</span><span class="sxs-lookup"><span data-stu-id="13996-294">DriverLicense</span></span>
- <span data-ttu-id="13996-295">DriverLicenses</span><span class="sxs-lookup"><span data-stu-id="13996-295">DriverLicenses</span></span>
- <span data-ttu-id="13996-296">Driver License</span><span class="sxs-lookup"><span data-stu-id="13996-296">Driver License</span></span>
- <span data-ttu-id="13996-297">Driver Licenses</span><span class="sxs-lookup"><span data-stu-id="13996-297">Driver Licenses</span></span>
- <span data-ttu-id="13996-298">DriversLicense</span><span class="sxs-lookup"><span data-stu-id="13996-298">DriversLicense</span></span>
- <span data-ttu-id="13996-299">DriversLicenses</span><span class="sxs-lookup"><span data-stu-id="13996-299">DriversLicenses</span></span>
- <span data-ttu-id="13996-300">Drivers License</span><span class="sxs-lookup"><span data-stu-id="13996-300">Drivers License</span></span>
- <span data-ttu-id="13996-301">Drivers Licenses</span><span class="sxs-lookup"><span data-stu-id="13996-301">Drivers Licenses</span></span>
- <span data-ttu-id="13996-302">Driver ' License</span><span class="sxs-lookup"><span data-stu-id="13996-302">Driver'License</span></span>
- <span data-ttu-id="13996-303">Driver ' licenses</span><span class="sxs-lookup"><span data-stu-id="13996-303">Driver'Licenses</span></span>
- <span data-ttu-id="13996-304">Driver' License</span><span class="sxs-lookup"><span data-stu-id="13996-304">Driver' License</span></span>
- <span data-ttu-id="13996-305">Driver' Licenses</span><span class="sxs-lookup"><span data-stu-id="13996-305">Driver' Licenses</span></span>
- <span data-ttu-id="13996-306">Secondola</span><span class="sxs-lookup"><span data-stu-id="13996-306">Driver'sLicense</span></span>
- <span data-ttu-id="13996-307">Driver'sLicenses</span><span class="sxs-lookup"><span data-stu-id="13996-307">Driver'sLicenses</span></span>
- <span data-ttu-id="13996-308">Driver's License</span><span class="sxs-lookup"><span data-stu-id="13996-308">Driver's License</span></span>
- <span data-ttu-id="13996-309">Driver's Licenses</span><span class="sxs-lookup"><span data-stu-id="13996-309">Driver's Licenses</span></span>
- <span data-ttu-id="13996-310">DriverLicense #</span><span class="sxs-lookup"><span data-stu-id="13996-310">DriverLicense#</span></span>
- <span data-ttu-id="13996-311">DriverLicenses #</span><span class="sxs-lookup"><span data-stu-id="13996-311">DriverLicenses#</span></span>
- <span data-ttu-id="13996-312">Driver License#</span><span class="sxs-lookup"><span data-stu-id="13996-312">Driver License#</span></span>
- <span data-ttu-id="13996-313">Driver Licenses#</span><span class="sxs-lookup"><span data-stu-id="13996-313">Driver Licenses#</span></span>
- <span data-ttu-id="13996-314">DriversLicense #</span><span class="sxs-lookup"><span data-stu-id="13996-314">DriversLicense#</span></span>
- <span data-ttu-id="13996-315">DriversLicenses #</span><span class="sxs-lookup"><span data-stu-id="13996-315">DriversLicenses#</span></span>
- <span data-ttu-id="13996-316">Drivers License#</span><span class="sxs-lookup"><span data-stu-id="13996-316">Drivers License#</span></span>
- <span data-ttu-id="13996-317">Drivers Licenses#</span><span class="sxs-lookup"><span data-stu-id="13996-317">Drivers Licenses#</span></span>
- <span data-ttu-id="13996-318">Driver ' License</span><span class="sxs-lookup"><span data-stu-id="13996-318">Driver'License#</span></span>
- <span data-ttu-id="13996-319">Driver ' licenses</span><span class="sxs-lookup"><span data-stu-id="13996-319">Driver'Licenses#</span></span>
- <span data-ttu-id="13996-320">Driver' License#</span><span class="sxs-lookup"><span data-stu-id="13996-320">Driver' License#</span></span>
- <span data-ttu-id="13996-321">Driver' Licenses#</span><span class="sxs-lookup"><span data-stu-id="13996-321">Driver' Licenses#</span></span>
- <span data-ttu-id="13996-322">Secondola</span><span class="sxs-lookup"><span data-stu-id="13996-322">Driver'sLicense#</span></span>
- <span data-ttu-id="13996-323">Driver'sLicenses #</span><span class="sxs-lookup"><span data-stu-id="13996-323">Driver'sLicenses#</span></span>
- <span data-ttu-id="13996-324">Driver's License#</span><span class="sxs-lookup"><span data-stu-id="13996-324">Driver's License#</span></span>
- <span data-ttu-id="13996-325">Driver's Licenses#</span><span class="sxs-lookup"><span data-stu-id="13996-325">Driver's Licenses#</span></span>
   
## <a name="australia-medical-account-number"></a><span data-ttu-id="13996-326">Australia - Numero di tessera sanitaria</span><span class="sxs-lookup"><span data-stu-id="13996-326">Australia Medical Account Number</span></span>

### <a name="format"></a><span data-ttu-id="13996-327">Formato</span><span class="sxs-lookup"><span data-stu-id="13996-327">Format</span></span>

<span data-ttu-id="13996-328">10-11 cifre</span><span class="sxs-lookup"><span data-stu-id="13996-328">10-11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="13996-329">Modello</span><span class="sxs-lookup"><span data-stu-id="13996-329">Pattern</span></span>

<span data-ttu-id="13996-330">10-11 cifre:</span><span class="sxs-lookup"><span data-stu-id="13996-330">10-11 digits:</span></span>
- <span data-ttu-id="13996-331">La prima cifra è compresa nell'intervallo 2-6</span><span class="sxs-lookup"><span data-stu-id="13996-331">First digit is in the range 2-6</span></span>
- <span data-ttu-id="13996-332">La nona cifra è una cifra di controllo</span><span class="sxs-lookup"><span data-stu-id="13996-332">Ninth digit is a check digit</span></span>
- <span data-ttu-id="13996-333">La decima cifra è la cifra del problema</span><span class="sxs-lookup"><span data-stu-id="13996-333">Tenth digit is the issue digit</span></span>
- <span data-ttu-id="13996-334">L'undicesima cifra (facoltativa) è il numero singolo</span><span class="sxs-lookup"><span data-stu-id="13996-334">Eleventh digit (optional) is the individual number</span></span>

### <a name="checksum"></a><span data-ttu-id="13996-335">Checksum</span><span class="sxs-lookup"><span data-stu-id="13996-335">Checksum</span></span>

<span data-ttu-id="13996-336">Sì</span><span class="sxs-lookup"><span data-stu-id="13996-336">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="13996-337">Definizione</span><span class="sxs-lookup"><span data-stu-id="13996-337">Definition</span></span>

<span data-ttu-id="13996-338">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 95%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="13996-338">A DLP policy is 95% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="13996-339">La funzione Func_australian_medical_account_number restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="13996-339">The function Func_australian_medical_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="13996-340">Viene trovata una parola chiave da Keyword_Australia_Medical_Account_Number.</span><span class="sxs-lookup"><span data-stu-id="13996-340">A keyword from Keyword_Australia_Medical_Account_Number is found.</span></span>
- <span data-ttu-id="13996-341">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="13996-341">The checksum passes.</span></span>

<span data-ttu-id="13996-342">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="13996-342">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="13996-343">La funzione Func_australian_medical_account_number restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="13996-343">The function Func_australian_medical_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="13996-344">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="13996-344">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="13996-345">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="13996-345">Keywords</span></span>

#### <a name="keywordaustraliamedicalaccountnumber"></a><span data-ttu-id="13996-346">Keyword_Australia_Medical_Account_Number</span><span class="sxs-lookup"><span data-stu-id="13996-346">Keyword_Australia_Medical_Account_Number</span></span>

- <span data-ttu-id="13996-347">bank account details</span><span class="sxs-lookup"><span data-stu-id="13996-347">bank account details</span></span>
- <span data-ttu-id="13996-348">medicare payments</span><span class="sxs-lookup"><span data-stu-id="13996-348">medicare payments</span></span>
- <span data-ttu-id="13996-349">mortgage account</span><span class="sxs-lookup"><span data-stu-id="13996-349">mortgage account</span></span>
- <span data-ttu-id="13996-350">bank payments</span><span class="sxs-lookup"><span data-stu-id="13996-350">bank payments</span></span>
- <span data-ttu-id="13996-351">information branch</span><span class="sxs-lookup"><span data-stu-id="13996-351">information branch</span></span>
- <span data-ttu-id="13996-352">credit card loan</span><span class="sxs-lookup"><span data-stu-id="13996-352">credit card loan</span></span>
- <span data-ttu-id="13996-353">department of human services</span><span class="sxs-lookup"><span data-stu-id="13996-353">department of human services</span></span>
- <span data-ttu-id="13996-354">local service</span><span class="sxs-lookup"><span data-stu-id="13996-354">local service</span></span>
- <span data-ttu-id="13996-355">Medicare</span><span class="sxs-lookup"><span data-stu-id="13996-355">medicare</span></span>

   
## <a name="australia-passport-number"></a><span data-ttu-id="13996-356">Australia - Numero di passaporto</span><span class="sxs-lookup"><span data-stu-id="13996-356">Australia Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="13996-357">Formato</span><span class="sxs-lookup"><span data-stu-id="13996-357">Format</span></span>

<span data-ttu-id="13996-358">Una lettera seguita da sette cifre</span><span class="sxs-lookup"><span data-stu-id="13996-358">A letter followed by seven digits</span></span>

### <a name="pattern"></a><span data-ttu-id="13996-359">Modello</span><span class="sxs-lookup"><span data-stu-id="13996-359">Pattern</span></span>

<span data-ttu-id="13996-360">Una lettera (senza distinzione tra maiuscole/minuscole) seguita da sette cifre</span><span class="sxs-lookup"><span data-stu-id="13996-360">A letter (not case sensitive) followed by seven digits</span></span>

### <a name="checksum"></a><span data-ttu-id="13996-361">Checksum</span><span class="sxs-lookup"><span data-stu-id="13996-361">Checksum</span></span>

<span data-ttu-id="13996-362">No</span><span class="sxs-lookup"><span data-stu-id="13996-362">No</span></span>

### <a name="definition"></a><span data-ttu-id="13996-363">Definizione</span><span class="sxs-lookup"><span data-stu-id="13996-363">Definition</span></span>

<span data-ttu-id="13996-364">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="13996-364">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="13996-365">L'espressione regolare Regex_australia_passport_number restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="13996-365">The regular expression Regex_australia_passport_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="13996-366">Viene trovata una parola chiave da Keyword_passport o Keyword_australia_passport_number.</span><span class="sxs-lookup"><span data-stu-id="13996-366">A keyword from Keyword_passport or Keyword_australia_passport_number is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="13996-367">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="13996-367">Keywords</span></span>

#### <a name="keywordpassport"></a><span data-ttu-id="13996-368">Keyword_passport</span><span class="sxs-lookup"><span data-stu-id="13996-368">Keyword_passport</span></span>

- <span data-ttu-id="13996-369">Passport Number</span><span class="sxs-lookup"><span data-stu-id="13996-369">Passport Number</span></span>
- <span data-ttu-id="13996-370">Passport No</span><span class="sxs-lookup"><span data-stu-id="13996-370">Passport No</span></span>
- <span data-ttu-id="13996-371">Passport#</span><span class="sxs-lookup"><span data-stu-id="13996-371">Passport #</span></span>
- <span data-ttu-id="13996-372">Passaporto</span><span class="sxs-lookup"><span data-stu-id="13996-372">Passport#</span></span>
- <span data-ttu-id="13996-373">PassportID</span><span class="sxs-lookup"><span data-stu-id="13996-373">PassportID</span></span>
- <span data-ttu-id="13996-374">Passportno</span><span class="sxs-lookup"><span data-stu-id="13996-374">Passportno</span></span>
- <span data-ttu-id="13996-375">passportnumber</span><span class="sxs-lookup"><span data-stu-id="13996-375">passportnumber</span></span>
- <span data-ttu-id="13996-376">パスポート</span><span class="sxs-lookup"><span data-stu-id="13996-376">パスポート</span></span>
- <span data-ttu-id="13996-377">パスポート番号</span><span class="sxs-lookup"><span data-stu-id="13996-377">パスポート番号</span></span>
- <span data-ttu-id="13996-378">パスポートのNum</span><span class="sxs-lookup"><span data-stu-id="13996-378">パスポートのNum</span></span>
- <span data-ttu-id="13996-379">パスポート ＃</span><span class="sxs-lookup"><span data-stu-id="13996-379">パスポート ＃</span></span> 
- <span data-ttu-id="13996-380">Numéro de passeport</span><span class="sxs-lookup"><span data-stu-id="13996-380">Numéro de passeport</span></span>
- <span data-ttu-id="13996-381">Passeport n °</span><span class="sxs-lookup"><span data-stu-id="13996-381">Passeport n °</span></span>
- <span data-ttu-id="13996-382">Passeport Non</span><span class="sxs-lookup"><span data-stu-id="13996-382">Passeport Non</span></span>
- <span data-ttu-id="13996-383">Passeport#</span><span class="sxs-lookup"><span data-stu-id="13996-383">Passeport #</span></span>
- <span data-ttu-id="13996-384">Passeport</span><span class="sxs-lookup"><span data-stu-id="13996-384">Passeport#</span></span>
- <span data-ttu-id="13996-385">PasseportNon</span><span class="sxs-lookup"><span data-stu-id="13996-385">PasseportNon</span></span>
- <span data-ttu-id="13996-386">Passeportn °</span><span class="sxs-lookup"><span data-stu-id="13996-386">Passeportn °</span></span>

#### <a name="keywordaustraliapassportnumber"></a><span data-ttu-id="13996-387">Keyword_australia_passport_number</span><span class="sxs-lookup"><span data-stu-id="13996-387">Keyword_australia_passport_number</span></span>

- <span data-ttu-id="13996-388">passaporto</span><span class="sxs-lookup"><span data-stu-id="13996-388">passport</span></span>
- <span data-ttu-id="13996-389">passport details</span><span class="sxs-lookup"><span data-stu-id="13996-389">passport details</span></span>
- <span data-ttu-id="13996-390">immigration and citizenship</span><span class="sxs-lookup"><span data-stu-id="13996-390">immigration and citizenship</span></span>
- <span data-ttu-id="13996-391">commonwealth of australia</span><span class="sxs-lookup"><span data-stu-id="13996-391">commonwealth of australia</span></span>
- <span data-ttu-id="13996-392">department of immigration</span><span class="sxs-lookup"><span data-stu-id="13996-392">department of immigration</span></span>
- <span data-ttu-id="13996-393">residential address</span><span class="sxs-lookup"><span data-stu-id="13996-393">residential address</span></span>
- <span data-ttu-id="13996-394">department of immigration and citizenship</span><span class="sxs-lookup"><span data-stu-id="13996-394">department of immigration and citizenship</span></span>
- <span data-ttu-id="13996-395">esempio</span><span class="sxs-lookup"><span data-stu-id="13996-395">visa</span></span>
- <span data-ttu-id="13996-396">national identity card</span><span class="sxs-lookup"><span data-stu-id="13996-396">national identity card</span></span>
- <span data-ttu-id="13996-397">passport number</span><span class="sxs-lookup"><span data-stu-id="13996-397">passport number</span></span>
- <span data-ttu-id="13996-398">travel document</span><span class="sxs-lookup"><span data-stu-id="13996-398">travel document</span></span>
- <span data-ttu-id="13996-399">issuing authority</span><span class="sxs-lookup"><span data-stu-id="13996-399">issuing authority</span></span>
   
## <a name="australia-tax-file-number"></a><span data-ttu-id="13996-400">Australia - Identificativo fiscale</span><span class="sxs-lookup"><span data-stu-id="13996-400">Australia Tax File Number</span></span>

### <a name="format"></a><span data-ttu-id="13996-401">Formato</span><span class="sxs-lookup"><span data-stu-id="13996-401">Format</span></span>

<span data-ttu-id="13996-402">8-9 cifre</span><span class="sxs-lookup"><span data-stu-id="13996-402">8-9 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="13996-403">Modello</span><span class="sxs-lookup"><span data-stu-id="13996-403">Pattern</span></span>

<span data-ttu-id="13996-404">8-9 cifre in genere presentate con spazi, come mostrato di seguito:</span><span class="sxs-lookup"><span data-stu-id="13996-404">8-9 digits typically presented with spaces as follows:</span></span>
- <span data-ttu-id="13996-405">Tre cifre</span><span class="sxs-lookup"><span data-stu-id="13996-405">Three digits</span></span> 
- <span data-ttu-id="13996-406">Uno spazio facoltativo</span><span class="sxs-lookup"><span data-stu-id="13996-406">An optional space</span></span> 
- <span data-ttu-id="13996-407">Tre cifre</span><span class="sxs-lookup"><span data-stu-id="13996-407">Three digits</span></span> 
- <span data-ttu-id="13996-408">Uno spazio facoltativo</span><span class="sxs-lookup"><span data-stu-id="13996-408">An optional space</span></span> 
- <span data-ttu-id="13996-409">2-3 cifre e l'ultima è una cifra di controllo</span><span class="sxs-lookup"><span data-stu-id="13996-409">2-3 digits where the last digit is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="13996-410">Checksum</span><span class="sxs-lookup"><span data-stu-id="13996-410">Checksum</span></span>

<span data-ttu-id="13996-411">Sì</span><span class="sxs-lookup"><span data-stu-id="13996-411">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="13996-412">Definizione</span><span class="sxs-lookup"><span data-stu-id="13996-412">Definition</span></span>

<span data-ttu-id="13996-413">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="13996-413">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="13996-414">La funzione Func_australian_tax_file_number restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="13996-414">The function Func_australian_tax_file_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="13996-415">Non vengono trovate parole chiave da Keyword_Australia_Tax_File_Number o da Keyword_number_exclusions.</span><span class="sxs-lookup"><span data-stu-id="13996-415">No keyword from Keyword_Australia_Tax_File_Number or Keyword_number_exclusions is found.</span></span>
- <span data-ttu-id="13996-416">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="13996-416">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="13996-417">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="13996-417">Keywords</span></span>

#### <a name="keywordaustraliataxfilenumber"></a><span data-ttu-id="13996-418">Keyword_Australia_Tax_File_Number</span><span class="sxs-lookup"><span data-stu-id="13996-418">Keyword_Australia_Tax_File_Number</span></span>

- <span data-ttu-id="13996-419">australian business number</span><span class="sxs-lookup"><span data-stu-id="13996-419">australian business number</span></span>
- <span data-ttu-id="13996-420">marginal tax rate</span><span class="sxs-lookup"><span data-stu-id="13996-420">marginal tax rate</span></span>
- <span data-ttu-id="13996-421">medicare levy</span><span class="sxs-lookup"><span data-stu-id="13996-421">medicare levy</span></span>
- <span data-ttu-id="13996-422">portfolio number</span><span class="sxs-lookup"><span data-stu-id="13996-422">portfolio number</span></span>
- <span data-ttu-id="13996-423">service veterans</span><span class="sxs-lookup"><span data-stu-id="13996-423">service veterans</span></span>
- <span data-ttu-id="13996-424">withholding tax</span><span class="sxs-lookup"><span data-stu-id="13996-424">withholding tax</span></span>
- <span data-ttu-id="13996-425">individual tax return</span><span class="sxs-lookup"><span data-stu-id="13996-425">individual tax return</span></span>
- <span data-ttu-id="13996-426">tax file number</span><span class="sxs-lookup"><span data-stu-id="13996-426">tax file number</span></span>

#### <a name="keywordnumberexclusions"></a><span data-ttu-id="13996-427">Keyword_number_exclusions</span><span class="sxs-lookup"><span data-stu-id="13996-427">Keyword_number_exclusions</span></span>

- <span data-ttu-id="13996-428">00000000</span><span class="sxs-lookup"><span data-stu-id="13996-428">00000000</span></span>
- <span data-ttu-id="13996-429">11111111</span><span class="sxs-lookup"><span data-stu-id="13996-429">11111111</span></span>
- <span data-ttu-id="13996-430">22222222</span><span class="sxs-lookup"><span data-stu-id="13996-430">22222222</span></span>
- <span data-ttu-id="13996-431">33333333</span><span class="sxs-lookup"><span data-stu-id="13996-431">33333333</span></span>
- <span data-ttu-id="13996-432">44444444</span><span class="sxs-lookup"><span data-stu-id="13996-432">44444444</span></span>
- <span data-ttu-id="13996-433">55555555</span><span class="sxs-lookup"><span data-stu-id="13996-433">55555555</span></span>
- <span data-ttu-id="13996-434">66666666</span><span class="sxs-lookup"><span data-stu-id="13996-434">66666666</span></span>
- <span data-ttu-id="13996-435">77777777</span><span class="sxs-lookup"><span data-stu-id="13996-435">77777777</span></span>
- <span data-ttu-id="13996-436">88888888</span><span class="sxs-lookup"><span data-stu-id="13996-436">88888888</span></span>
- <span data-ttu-id="13996-437">99999999</span><span class="sxs-lookup"><span data-stu-id="13996-437">99999999</span></span>
- <span data-ttu-id="13996-438">000000000</span><span class="sxs-lookup"><span data-stu-id="13996-438">000000000</span></span>
- <span data-ttu-id="13996-439">111111111</span><span class="sxs-lookup"><span data-stu-id="13996-439">111111111</span></span>
- <span data-ttu-id="13996-440">222222222</span><span class="sxs-lookup"><span data-stu-id="13996-440">222222222</span></span>
- <span data-ttu-id="13996-441">333333333</span><span class="sxs-lookup"><span data-stu-id="13996-441">333333333</span></span>
- <span data-ttu-id="13996-442">444444444</span><span class="sxs-lookup"><span data-stu-id="13996-442">444444444</span></span>
- <span data-ttu-id="13996-443">555555555</span><span class="sxs-lookup"><span data-stu-id="13996-443">555555555</span></span>
- <span data-ttu-id="13996-444">666666666</span><span class="sxs-lookup"><span data-stu-id="13996-444">666666666</span></span>
- <span data-ttu-id="13996-445">777777777</span><span class="sxs-lookup"><span data-stu-id="13996-445">777777777</span></span>
- <span data-ttu-id="13996-446">888888888</span><span class="sxs-lookup"><span data-stu-id="13996-446">888888888</span></span>
- <span data-ttu-id="13996-447">999999999</span><span class="sxs-lookup"><span data-stu-id="13996-447">999999999</span></span>
- <span data-ttu-id="13996-448">0000000000</span><span class="sxs-lookup"><span data-stu-id="13996-448">0000000000</span></span>
- <span data-ttu-id="13996-449">1111111111</span><span class="sxs-lookup"><span data-stu-id="13996-449">1111111111</span></span>
- <span data-ttu-id="13996-450">2222222222</span><span class="sxs-lookup"><span data-stu-id="13996-450">2222222222</span></span>
- <span data-ttu-id="13996-451">3333333333</span><span class="sxs-lookup"><span data-stu-id="13996-451">3333333333</span></span>
- <span data-ttu-id="13996-452">4444444444</span><span class="sxs-lookup"><span data-stu-id="13996-452">4444444444</span></span>
- <span data-ttu-id="13996-453">5555555555</span><span class="sxs-lookup"><span data-stu-id="13996-453">5555555555</span></span>
- <span data-ttu-id="13996-454">6666666666</span><span class="sxs-lookup"><span data-stu-id="13996-454">6666666666</span></span>
- <span data-ttu-id="13996-455">7777777777</span><span class="sxs-lookup"><span data-stu-id="13996-455">7777777777</span></span>
- <span data-ttu-id="13996-456">8888888888</span><span class="sxs-lookup"><span data-stu-id="13996-456">8888888888</span></span>
- <span data-ttu-id="13996-457">9999999999</span><span class="sxs-lookup"><span data-stu-id="13996-457">9999999999</span></span>

## <a name="azure-documentdb-auth-key"></a><span data-ttu-id="13996-458">Chiave di autenticazione di DocumentDB di Azure</span><span class="sxs-lookup"><span data-stu-id="13996-458">Azure DocumentDB Auth Key</span></span>

### <a name="format"></a><span data-ttu-id="13996-459">Formato</span><span class="sxs-lookup"><span data-stu-id="13996-459">Format</span></span>

<span data-ttu-id="13996-460">La stringa "DocumentDb" seguita dai caratteri e dalle stringhe delineate nel modello seguente.</span><span class="sxs-lookup"><span data-stu-id="13996-460">The string "DocumentDb" followed by the characters and strings outlined in the pattern below.</span></span>

### <a name="pattern"></a><span data-ttu-id="13996-461">Modello</span><span class="sxs-lookup"><span data-stu-id="13996-461">Pattern</span></span>

- <span data-ttu-id="13996-462">La stringa "DocumentDb"</span><span class="sxs-lookup"><span data-stu-id="13996-462">The string "DocumentDb"</span></span>
- <span data-ttu-id="13996-463">Qualsiasi combinazione tra 3-200 lettere, cifre, simboli, caratteri speciali o spazi in maiuscolo o minuscolo</span><span class="sxs-lookup"><span data-stu-id="13996-463">Any combination of between 3-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="13996-464">Un simbolo maggiore di (>), un segno di uguale (=), un segno di virgolette (") oppure un apostrofo (')</span><span class="sxs-lookup"><span data-stu-id="13996-464">A greater than symbol (>), an equal sign (=), a quotation mark ("), or an apostrophe (')</span></span>
- <span data-ttu-id="13996-465">Qualsiasi combinazione di 86 lettere maiuscole e minuscole, cifre, barra (/) o segno più (+)</span><span class="sxs-lookup"><span data-stu-id="13996-465">Any combination of 86 lower- or uppercase letters, digits, forward slash (/), or plus sign (+)</span></span>
- <span data-ttu-id="13996-466">Due segni uguali (=)</span><span class="sxs-lookup"><span data-stu-id="13996-466">Two equal signs (=)</span></span>

### <a name="checksum"></a><span data-ttu-id="13996-467">Checksum</span><span class="sxs-lookup"><span data-stu-id="13996-467">Checksum</span></span>

<span data-ttu-id="13996-468">No</span><span class="sxs-lookup"><span data-stu-id="13996-468">No</span></span>

### <a name="definition"></a><span data-ttu-id="13996-469">Definizione</span><span class="sxs-lookup"><span data-stu-id="13996-469">Definition</span></span>

<span data-ttu-id="13996-470">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="13996-470">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="13996-471">L'espressione regolare CEP_Regex_AzureDocumentDBAuthKey trova il contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="13996-471">The regular expression CEP_Regex_AzureDocumentDBAuthKey finds content that matches the pattern.</span></span>
- <span data-ttu-id="13996-472">L'espressione regolare CEP_CommonExampleKeywords non \*\*\*\* trova contenuto corrispondente al modello.</span><span class="sxs-lookup"><span data-stu-id="13996-472">The regular expression CEP_CommonExampleKeywords does **not** find content that matches the pattern.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="13996-473">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="13996-473">Keywords</span></span>

#### <a name="cepcommonexamplekeywords"></a><span data-ttu-id="13996-474">CEP_CommonExampleKeywords</span><span class="sxs-lookup"><span data-stu-id="13996-474">CEP_CommonExampleKeywords</span></span>

<span data-ttu-id="13996-475">Si noti che tecnicamente questo tipo di informazioni riservate identifica queste parole chiave utilizzando un'espressione regolare, non un elenco di parola chiave.</span><span class="sxs-lookup"><span data-stu-id="13996-475">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="13996-476">contoso</span><span class="sxs-lookup"><span data-stu-id="13996-476">contoso</span></span>
- <span data-ttu-id="13996-477">Fabrikam</span><span class="sxs-lookup"><span data-stu-id="13996-477">fabrikam</span></span>
- <span data-ttu-id="13996-478">Northwind</span><span class="sxs-lookup"><span data-stu-id="13996-478">northwind</span></span>
- <span data-ttu-id="13996-479">sandbox</span><span class="sxs-lookup"><span data-stu-id="13996-479">sandbox</span></span>
- <span data-ttu-id="13996-480">OneBox</span><span class="sxs-lookup"><span data-stu-id="13996-480">onebox</span></span>
- <span data-ttu-id="13996-481">localhost</span><span class="sxs-lookup"><span data-stu-id="13996-481">localhost</span></span>
- <span data-ttu-id="13996-482">127.0.0.1</span><span class="sxs-lookup"><span data-stu-id="13996-482">127.0.0.1</span></span>
- <span data-ttu-id="13996-483">testacs.</span><span class="sxs-lookup"><span data-stu-id="13996-483">testacs.</span></span><!--no-hyperlink--><span data-ttu-id="13996-484">com</span><span class="sxs-lookup"><span data-stu-id="13996-484">com</span></span>
- <span data-ttu-id="13996-485">s-int.</span><span class="sxs-lookup"><span data-stu-id="13996-485">s-int.</span></span><!--no-hyperlink--><span data-ttu-id="13996-486">NET</span><span class="sxs-lookup"><span data-stu-id="13996-486">net</span></span>

## <a name="azure-iaas-database-connection-string-and-azure-sql-connection-string"></a><span data-ttu-id="13996-487">Stringa di connessione del database di Azure IAAS e stringa di connessione SQL di Azure</span><span class="sxs-lookup"><span data-stu-id="13996-487">Azure IAAS Database Connection String and Azure SQL Connection String</span></span>

### <a name="format"></a><span data-ttu-id="13996-488">Formato</span><span class="sxs-lookup"><span data-stu-id="13996-488">Format</span></span>

<span data-ttu-id="13996-489">Stringa "Server", "Server" o "Data Source" seguito dai caratteri e dalle stringhe delineati nel modello seguente, inclusa la stringa "cloudapp. Azure.</span><span class="sxs-lookup"><span data-stu-id="13996-489">The string "Server", "server", or "data source" followed by the characters and strings outlined in the pattern below, including the string "cloudapp.azure.</span></span><!--no-hyperlink--><span data-ttu-id="13996-490">com "o" cloudapp. Azure.</span><span class="sxs-lookup"><span data-stu-id="13996-490">com" or "cloudapp.azure.</span></span><!--no-hyperlink--><span data-ttu-id="13996-491">NET "o" database. Windows.</span><span class="sxs-lookup"><span data-stu-id="13996-491">net" or "database.windows.</span></span><!--no-hyperlink--><span data-ttu-id="13996-492">NET "e la stringa" password "o" password "o" pwd ".</span><span class="sxs-lookup"><span data-stu-id="13996-492">net", and the string "Password" or "password" or "pwd".</span></span>

### <a name="pattern"></a><span data-ttu-id="13996-493">Modello</span><span class="sxs-lookup"><span data-stu-id="13996-493">Pattern</span></span>

- <span data-ttu-id="13996-494">La stringa "Server", "Server" o "Data Source"</span><span class="sxs-lookup"><span data-stu-id="13996-494">The string "Server", "server", or "data source"</span></span>
- <span data-ttu-id="13996-495">0-2 caratteri dello spazio vuoto</span><span class="sxs-lookup"><span data-stu-id="13996-495">0-2 whitespace characters</span></span>
- <span data-ttu-id="13996-496">Segno di uguale (=)</span><span class="sxs-lookup"><span data-stu-id="13996-496">An equal sign (=)</span></span>
- <span data-ttu-id="13996-497">0-2 caratteri dello spazio vuoto</span><span class="sxs-lookup"><span data-stu-id="13996-497">0-2 whitespace characters</span></span>
- <span data-ttu-id="13996-498">Qualsiasi combinazione tra 1-200 lettere, cifre, simboli, caratteri speciali o spazi in maiuscolo o minuscolo</span><span class="sxs-lookup"><span data-stu-id="13996-498">Any combination of between 1-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="13996-499">La stringa "cloudapp. Azure.</span><span class="sxs-lookup"><span data-stu-id="13996-499">The string "cloudapp.azure.</span></span><!--no-hyperlink--><span data-ttu-id="13996-500">com "," cloudapp. Azure.</span><span class="sxs-lookup"><span data-stu-id="13996-500">com", "cloudapp.azure.</span></span><!--no-hyperlink--><span data-ttu-id="13996-501">NET "o" database. Windows.</span><span class="sxs-lookup"><span data-stu-id="13996-501">net", or "database.windows.</span></span><!--no-hyperlink--><span data-ttu-id="13996-502">NET</span><span class="sxs-lookup"><span data-stu-id="13996-502">net"</span></span>
- <span data-ttu-id="13996-503">Qualsiasi combinazione tra 1-300 lettere, cifre, simboli, caratteri speciali o spazi in maiuscolo o minuscolo</span><span class="sxs-lookup"><span data-stu-id="13996-503">Any combination of between 1-300 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="13996-504">La stringa "password", "password" o "pwd"</span><span class="sxs-lookup"><span data-stu-id="13996-504">The string "Password", "password", or "pwd"</span></span>
- <span data-ttu-id="13996-505">0-2 caratteri dello spazio vuoto</span><span class="sxs-lookup"><span data-stu-id="13996-505">0-2 whitespace characters</span></span>
- <span data-ttu-id="13996-506">Segno di uguale (=)</span><span class="sxs-lookup"><span data-stu-id="13996-506">An equal sign (=)</span></span>
- <span data-ttu-id="13996-507">0-2 caratteri dello spazio vuoto</span><span class="sxs-lookup"><span data-stu-id="13996-507">0-2 whitespace characters</span></span>
- <span data-ttu-id="13996-508">Uno o più caratteri non costituiti da un punto e virgola (;), virgolette (") o apostrofo (')</span><span class="sxs-lookup"><span data-stu-id="13996-508">One or more characters that is not a semicolon (;), quotation mark ("), or apostrophe (')</span></span>
- <span data-ttu-id="13996-509">Un punto e virgola (;), virgolette (") o apostrofo (')</span><span class="sxs-lookup"><span data-stu-id="13996-509">A semicolon (;), quotation mark ("), or apostrophe (')</span></span>

### <a name="checksum"></a><span data-ttu-id="13996-510">Checksum</span><span class="sxs-lookup"><span data-stu-id="13996-510">Checksum</span></span>

<span data-ttu-id="13996-511">No</span><span class="sxs-lookup"><span data-stu-id="13996-511">No</span></span>

### <a name="definition"></a><span data-ttu-id="13996-512">Definizione</span><span class="sxs-lookup"><span data-stu-id="13996-512">Definition</span></span>

<span data-ttu-id="13996-513">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="13996-513">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="13996-514">L'espressione regolare CEP_Regex_AzureConnectionString trova il contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="13996-514">The regular expression CEP_Regex_AzureConnectionString finds content that matches the pattern.</span></span>
- <span data-ttu-id="13996-515">L'espressione regolare CEP_CommonExampleKeywords non \*\*\*\* trova contenuto corrispondente al modello.</span><span class="sxs-lookup"><span data-stu-id="13996-515">The regular expression CEP_CommonExampleKeywords does **not** find content that matches the pattern.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="13996-516">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="13996-516">Keywords</span></span>

#### <a name="cepcommonexamplekeywords"></a><span data-ttu-id="13996-517">CEP_CommonExampleKeywords</span><span class="sxs-lookup"><span data-stu-id="13996-517">CEP_CommonExampleKeywords</span></span>

<span data-ttu-id="13996-518">Si noti che tecnicamente questo tipo di informazioni riservate identifica queste parole chiave utilizzando un'espressione regolare, non un elenco di parola chiave.</span><span class="sxs-lookup"><span data-stu-id="13996-518">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="13996-519">contoso</span><span class="sxs-lookup"><span data-stu-id="13996-519">contoso</span></span>
- <span data-ttu-id="13996-520">Fabrikam</span><span class="sxs-lookup"><span data-stu-id="13996-520">fabrikam</span></span>
- <span data-ttu-id="13996-521">Northwind</span><span class="sxs-lookup"><span data-stu-id="13996-521">northwind</span></span>
- <span data-ttu-id="13996-522">sandbox</span><span class="sxs-lookup"><span data-stu-id="13996-522">sandbox</span></span>
- <span data-ttu-id="13996-523">OneBox</span><span class="sxs-lookup"><span data-stu-id="13996-523">onebox</span></span>
- <span data-ttu-id="13996-524">localhost</span><span class="sxs-lookup"><span data-stu-id="13996-524">localhost</span></span>
- <span data-ttu-id="13996-525">127.0.0.1</span><span class="sxs-lookup"><span data-stu-id="13996-525">127.0.0.1</span></span>
- <span data-ttu-id="13996-526">testacs.</span><span class="sxs-lookup"><span data-stu-id="13996-526">testacs.</span></span><!--no-hyperlink--><span data-ttu-id="13996-527">com</span><span class="sxs-lookup"><span data-stu-id="13996-527">com</span></span>
- <span data-ttu-id="13996-528">s-int.</span><span class="sxs-lookup"><span data-stu-id="13996-528">s-int.</span></span><!--no-hyperlink--><span data-ttu-id="13996-529">NET</span><span class="sxs-lookup"><span data-stu-id="13996-529">net</span></span>

## <a name="azure-iot-connection-string"></a><span data-ttu-id="13996-530">Stringa di connessione di Azure.</span><span class="sxs-lookup"><span data-stu-id="13996-530">Azure IoT Connection String</span></span>

### <a name="format"></a><span data-ttu-id="13996-531">Formato</span><span class="sxs-lookup"><span data-stu-id="13996-531">Format</span></span>

<span data-ttu-id="13996-532">La stringa "HostName" seguita dai caratteri e dalle stringhe delineati nel modello seguente, incluse le stringhe "Azure-Devices.</span><span class="sxs-lookup"><span data-stu-id="13996-532">The string "HostName" followed by the characters and strings outlined in the pattern below, including the strings "azure-devices.</span></span><!--no-hyperlink--><span data-ttu-id="13996-533">NET "e" SharedAccessKey ".</span><span class="sxs-lookup"><span data-stu-id="13996-533">net" and "SharedAccessKey".</span></span>

### <a name="pattern"></a><span data-ttu-id="13996-534">Modello</span><span class="sxs-lookup"><span data-stu-id="13996-534">Pattern</span></span>

- <span data-ttu-id="13996-535">La stringa "HostName"</span><span class="sxs-lookup"><span data-stu-id="13996-535">The string "HostName"</span></span>
- <span data-ttu-id="13996-536">0-2 caratteri dello spazio vuoto</span><span class="sxs-lookup"><span data-stu-id="13996-536">0-2 whitespace characters</span></span>
- <span data-ttu-id="13996-537">Segno di uguale (=)</span><span class="sxs-lookup"><span data-stu-id="13996-537">An equal sign (=)</span></span>
- <span data-ttu-id="13996-538">0-2 caratteri dello spazio vuoto</span><span class="sxs-lookup"><span data-stu-id="13996-538">0-2 whitespace characters</span></span>
- <span data-ttu-id="13996-539">Qualsiasi combinazione tra 1-200 lettere, cifre, simboli, caratteri speciali o spazi in maiuscolo o minuscolo</span><span class="sxs-lookup"><span data-stu-id="13996-539">Any combination of between 1-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="13996-540">La stringa "Azure-Devices.</span><span class="sxs-lookup"><span data-stu-id="13996-540">The string "azure-devices.</span></span><!--no-hyperlink--><span data-ttu-id="13996-541">NET</span><span class="sxs-lookup"><span data-stu-id="13996-541">net"</span></span>
- <span data-ttu-id="13996-542">Qualsiasi combinazione tra 1-200 lettere, cifre, simboli, caratteri speciali o spazi in maiuscolo o minuscolo</span><span class="sxs-lookup"><span data-stu-id="13996-542">Any combination of between 1-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="13996-543">La stringa "SharedAccessKey"</span><span class="sxs-lookup"><span data-stu-id="13996-543">The string "SharedAccessKey"</span></span>
- <span data-ttu-id="13996-544">0-2 caratteri dello spazio vuoto</span><span class="sxs-lookup"><span data-stu-id="13996-544">0-2 whitespace characters</span></span>
- <span data-ttu-id="13996-545">Segno di uguale (=)</span><span class="sxs-lookup"><span data-stu-id="13996-545">An equal sign (=)</span></span>
- <span data-ttu-id="13996-546">0-2 caratteri dello spazio vuoto</span><span class="sxs-lookup"><span data-stu-id="13996-546">0-2 whitespace characters</span></span>
- <span data-ttu-id="13996-547">Qualsiasi combinazione di 43 lettere maiuscole e minuscole, cifre, barra (/) o segno più (+)</span><span class="sxs-lookup"><span data-stu-id="13996-547">Any combination of 43 lower- or uppercase letters, digits, forward slash (/), or plus sign (+)</span></span>
- <span data-ttu-id="13996-548">Segno di uguale (=)</span><span class="sxs-lookup"><span data-stu-id="13996-548">An equal sign (=)</span></span>

### <a name="checksum"></a><span data-ttu-id="13996-549">Checksum</span><span class="sxs-lookup"><span data-stu-id="13996-549">Checksum</span></span>

<span data-ttu-id="13996-550">No</span><span class="sxs-lookup"><span data-stu-id="13996-550">No</span></span>

### <a name="definition"></a><span data-ttu-id="13996-551">Definizione</span><span class="sxs-lookup"><span data-stu-id="13996-551">Definition</span></span>

<span data-ttu-id="13996-552">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="13996-552">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="13996-553">L'espressione regolare CEP_Regex_AzureIoTConnectionString trova il contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="13996-553">The regular expression CEP_Regex_AzureIoTConnectionString finds content that matches the pattern.</span></span>
- <span data-ttu-id="13996-554">L'espressione regolare CEP_CommonExampleKeywords non \*\*\*\* trova contenuto corrispondente al modello.</span><span class="sxs-lookup"><span data-stu-id="13996-554">The regular expression CEP_CommonExampleKeywords does **not** find content that matches the pattern.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="13996-555">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="13996-555">Keywords</span></span>

#### <a name="cepcommonexamplekeywords"></a><span data-ttu-id="13996-556">CEP_CommonExampleKeywords</span><span class="sxs-lookup"><span data-stu-id="13996-556">CEP_CommonExampleKeywords</span></span>

<span data-ttu-id="13996-557">Si noti che tecnicamente questo tipo di informazioni riservate identifica queste parole chiave utilizzando un'espressione regolare, non un elenco di parola chiave.</span><span class="sxs-lookup"><span data-stu-id="13996-557">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="13996-558">contoso</span><span class="sxs-lookup"><span data-stu-id="13996-558">contoso</span></span>
- <span data-ttu-id="13996-559">Fabrikam</span><span class="sxs-lookup"><span data-stu-id="13996-559">fabrikam</span></span>
- <span data-ttu-id="13996-560">Northwind</span><span class="sxs-lookup"><span data-stu-id="13996-560">northwind</span></span>
- <span data-ttu-id="13996-561">sandbox</span><span class="sxs-lookup"><span data-stu-id="13996-561">sandbox</span></span>
- <span data-ttu-id="13996-562">OneBox</span><span class="sxs-lookup"><span data-stu-id="13996-562">onebox</span></span>
- <span data-ttu-id="13996-563">localhost</span><span class="sxs-lookup"><span data-stu-id="13996-563">localhost</span></span>
- <span data-ttu-id="13996-564">127.0.0.1</span><span class="sxs-lookup"><span data-stu-id="13996-564">127.0.0.1</span></span>
- <span data-ttu-id="13996-565">testacs.</span><span class="sxs-lookup"><span data-stu-id="13996-565">testacs.</span></span><!--no-hyperlink--><span data-ttu-id="13996-566">com</span><span class="sxs-lookup"><span data-stu-id="13996-566">com</span></span>
- <span data-ttu-id="13996-567">s-int.</span><span class="sxs-lookup"><span data-stu-id="13996-567">s-int.</span></span><!--no-hyperlink--><span data-ttu-id="13996-568">NET</span><span class="sxs-lookup"><span data-stu-id="13996-568">net</span></span>

## <a name="azure-publish-setting-password"></a><span data-ttu-id="13996-569">Password per l'impostazione di pubblicazione di Azure</span><span class="sxs-lookup"><span data-stu-id="13996-569">Azure Publish Setting Password</span></span>

### <a name="format"></a><span data-ttu-id="13996-570">Formato</span><span class="sxs-lookup"><span data-stu-id="13996-570">Format</span></span>

<span data-ttu-id="13996-571">La stringa "UserPwd =" seguita da una stringa alfanumerica.</span><span class="sxs-lookup"><span data-stu-id="13996-571">The string "userpwd=" followed by an alphanumeric string.</span></span>

### <a name="pattern"></a><span data-ttu-id="13996-572">Modello</span><span class="sxs-lookup"><span data-stu-id="13996-572">Pattern</span></span>

- <span data-ttu-id="13996-573">La stringa "UserPwd ="</span><span class="sxs-lookup"><span data-stu-id="13996-573">The string "userpwd="</span></span>
- <span data-ttu-id="13996-574">Qualsiasi combinazione di lettere o cifre minuscole di 60</span><span class="sxs-lookup"><span data-stu-id="13996-574">Any combination of 60 lowercase letters or digits</span></span>
- <span data-ttu-id="13996-575">Virgolette (")</span><span class="sxs-lookup"><span data-stu-id="13996-575">A quotation mark (")</span></span>

### <a name="checksum"></a><span data-ttu-id="13996-576">Checksum</span><span class="sxs-lookup"><span data-stu-id="13996-576">Checksum</span></span>

<span data-ttu-id="13996-577">No</span><span class="sxs-lookup"><span data-stu-id="13996-577">No</span></span>

### <a name="definition"></a><span data-ttu-id="13996-578">Definizione</span><span class="sxs-lookup"><span data-stu-id="13996-578">Definition</span></span>

<span data-ttu-id="13996-579">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="13996-579">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="13996-580">L'espressione regolare CEP_Regex_AzurePublishSettingPasswords trova il contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="13996-580">The regular expression CEP_Regex_AzurePublishSettingPasswords finds content that matches the pattern.</span></span>
- <span data-ttu-id="13996-581">L'espressione regolare CEP_CommonExampleKeywords non \*\*\*\* trova contenuto corrispondente al modello.</span><span class="sxs-lookup"><span data-stu-id="13996-581">The regular expression CEP_CommonExampleKeywords does **not** find content that matches the pattern.</span></span>


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

### <a name="keywords"></a><span data-ttu-id="13996-582">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="13996-582">Keywords</span></span>

#### <a name="cepcommonexamplekeywords"></a><span data-ttu-id="13996-583">CEP_CommonExampleKeywords</span><span class="sxs-lookup"><span data-stu-id="13996-583">CEP_CommonExampleKeywords</span></span>

<span data-ttu-id="13996-584">Si noti che tecnicamente questo tipo di informazioni riservate identifica queste parole chiave utilizzando un'espressione regolare, non un elenco di parola chiave.</span><span class="sxs-lookup"><span data-stu-id="13996-584">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="13996-585">contoso</span><span class="sxs-lookup"><span data-stu-id="13996-585">contoso</span></span>
- <span data-ttu-id="13996-586">Fabrikam</span><span class="sxs-lookup"><span data-stu-id="13996-586">fabrikam</span></span>
- <span data-ttu-id="13996-587">Northwind</span><span class="sxs-lookup"><span data-stu-id="13996-587">northwind</span></span>
- <span data-ttu-id="13996-588">sandbox</span><span class="sxs-lookup"><span data-stu-id="13996-588">sandbox</span></span>
- <span data-ttu-id="13996-589">OneBox</span><span class="sxs-lookup"><span data-stu-id="13996-589">onebox</span></span>
- <span data-ttu-id="13996-590">localhost</span><span class="sxs-lookup"><span data-stu-id="13996-590">localhost</span></span>
- <span data-ttu-id="13996-591">127.0.0.1</span><span class="sxs-lookup"><span data-stu-id="13996-591">127.0.0.1</span></span>
- <span data-ttu-id="13996-592">testacs.</span><span class="sxs-lookup"><span data-stu-id="13996-592">testacs.</span></span><!--no-hyperlink--><span data-ttu-id="13996-593">com</span><span class="sxs-lookup"><span data-stu-id="13996-593">com</span></span>
- <span data-ttu-id="13996-594">s-int.</span><span class="sxs-lookup"><span data-stu-id="13996-594">s-int.</span></span><!--no-hyperlink--><span data-ttu-id="13996-595">NET</span><span class="sxs-lookup"><span data-stu-id="13996-595">net</span></span>

## <a name="azure-redis-cache-connection-string"></a><span data-ttu-id="13996-596">Stringa di connessione della cache di Azure Redis</span><span class="sxs-lookup"><span data-stu-id="13996-596">Azure Redis Cache Connection String</span></span>

### <a name="format"></a><span data-ttu-id="13996-597">Formato</span><span class="sxs-lookup"><span data-stu-id="13996-597">Format</span></span>

<span data-ttu-id="13996-598">La stringa "Redis. cache. Windows.</span><span class="sxs-lookup"><span data-stu-id="13996-598">The string "redis.cache.windows.</span></span><!--no-hyperlink--><span data-ttu-id="13996-599">NET "seguito dai caratteri e dalle stringhe delineati nel modello seguente, inclusa la stringa" password "o" pwd ".</span><span class="sxs-lookup"><span data-stu-id="13996-599">net" followed by the characters and strings outlined in the pattern below, including the string "password" or "pwd".</span></span>

### <a name="pattern"></a><span data-ttu-id="13996-600">Modello</span><span class="sxs-lookup"><span data-stu-id="13996-600">Pattern</span></span>

- <span data-ttu-id="13996-601">La stringa "Redis. cache. Windows.</span><span class="sxs-lookup"><span data-stu-id="13996-601">The string "redis.cache.windows.</span></span><!--no-hyperlink--><span data-ttu-id="13996-602">NET</span><span class="sxs-lookup"><span data-stu-id="13996-602">net"</span></span>
- <span data-ttu-id="13996-603">Qualsiasi combinazione tra 1-200 lettere, cifre, simboli, caratteri speciali o spazi in maiuscolo o minuscolo</span><span class="sxs-lookup"><span data-stu-id="13996-603">Any combination of between 1-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="13996-604">La stringa "password" o "pwd"</span><span class="sxs-lookup"><span data-stu-id="13996-604">The string "password" or "pwd"</span></span>
- <span data-ttu-id="13996-605">0-2 caratteri dello spazio vuoto</span><span class="sxs-lookup"><span data-stu-id="13996-605">0-2 whitespace characters</span></span>
- <span data-ttu-id="13996-606">Segno di uguale (=)</span><span class="sxs-lookup"><span data-stu-id="13996-606">An equal sign (=)</span></span>
- <span data-ttu-id="13996-607">0-2 caratteri dello spazio vuoto</span><span class="sxs-lookup"><span data-stu-id="13996-607">0-2 whitespace characters</span></span>
- <span data-ttu-id="13996-608">Qualsiasi combinazione di 43 caratteri che sono lettere maiuscole o minuscole, cifre, barra (/) o segno più (+)</span><span class="sxs-lookup"><span data-stu-id="13996-608">Any combination of 43 characters that are lower- or uppercase letters, digits, forward slash (/), or plus sign (+)</span></span>
- <span data-ttu-id="13996-609">Segno di uguale (=)</span><span class="sxs-lookup"><span data-stu-id="13996-609">An equal sign (=)</span></span>

### <a name="checksum"></a><span data-ttu-id="13996-610">Checksum</span><span class="sxs-lookup"><span data-stu-id="13996-610">Checksum</span></span>

<span data-ttu-id="13996-611">No</span><span class="sxs-lookup"><span data-stu-id="13996-611">No</span></span>

### <a name="definition"></a><span data-ttu-id="13996-612">Definizione</span><span class="sxs-lookup"><span data-stu-id="13996-612">Definition</span></span>

<span data-ttu-id="13996-613">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="13996-613">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="13996-614">L'espressione regolare CEP_Regex_AzureRedisCacheConnectionString trova il contenuto corrispondente al modello.</span><span class="sxs-lookup"><span data-stu-id="13996-614">The regular expression CEP_Regex_AzureRedisCacheConnectionString finds content that matches the pattern..</span></span>
- <span data-ttu-id="13996-615">L'espressione regolare CEP_CommonExampleKeywords non \*\*\*\* trova contenuto corrispondente al modello.</span><span class="sxs-lookup"><span data-stu-id="13996-615">The regular expression CEP_CommonExampleKeywords does **not** find content that matches the pattern.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="13996-616">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="13996-616">Keywords</span></span>

#### <a name="cepcommonexamplekeywords"></a><span data-ttu-id="13996-617">CEP_CommonExampleKeywords</span><span class="sxs-lookup"><span data-stu-id="13996-617">CEP_CommonExampleKeywords</span></span>

<span data-ttu-id="13996-618">Si noti che tecnicamente questo tipo di informazioni riservate identifica queste parole chiave utilizzando un'espressione regolare, non un elenco di parola chiave.</span><span class="sxs-lookup"><span data-stu-id="13996-618">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="13996-619">contoso</span><span class="sxs-lookup"><span data-stu-id="13996-619">contoso</span></span>
- <span data-ttu-id="13996-620">Fabrikam</span><span class="sxs-lookup"><span data-stu-id="13996-620">fabrikam</span></span>
- <span data-ttu-id="13996-621">Northwind</span><span class="sxs-lookup"><span data-stu-id="13996-621">northwind</span></span>
- <span data-ttu-id="13996-622">sandbox</span><span class="sxs-lookup"><span data-stu-id="13996-622">sandbox</span></span>
- <span data-ttu-id="13996-623">OneBox</span><span class="sxs-lookup"><span data-stu-id="13996-623">onebox</span></span>
- <span data-ttu-id="13996-624">localhost</span><span class="sxs-lookup"><span data-stu-id="13996-624">localhost</span></span>
- <span data-ttu-id="13996-625">127.0.0.1</span><span class="sxs-lookup"><span data-stu-id="13996-625">127.0.0.1</span></span>
- <span data-ttu-id="13996-626">testacs.</span><span class="sxs-lookup"><span data-stu-id="13996-626">testacs.</span></span><!--no-hyperlink--><span data-ttu-id="13996-627">com</span><span class="sxs-lookup"><span data-stu-id="13996-627">com</span></span>
- <span data-ttu-id="13996-628">s-int.</span><span class="sxs-lookup"><span data-stu-id="13996-628">s-int.</span></span><!--no-hyperlink--><span data-ttu-id="13996-629">NET</span><span class="sxs-lookup"><span data-stu-id="13996-629">net</span></span>

## <a name="azure-sas"></a><span data-ttu-id="13996-630">SAS di Azure</span><span class="sxs-lookup"><span data-stu-id="13996-630">Azure SAS</span></span>

### <a name="format"></a><span data-ttu-id="13996-631">Formato</span><span class="sxs-lookup"><span data-stu-id="13996-631">Format</span></span>

<span data-ttu-id="13996-632">La stringa "sig" seguita dai caratteri e dalle stringhe delineate nel modello seguente.</span><span class="sxs-lookup"><span data-stu-id="13996-632">The string "sig" followed by the characters and strings outlined in the pattern below.</span></span>

### <a name="pattern"></a><span data-ttu-id="13996-633">Modello</span><span class="sxs-lookup"><span data-stu-id="13996-633">Pattern</span></span>

- <span data-ttu-id="13996-634">La stringa "sig"</span><span class="sxs-lookup"><span data-stu-id="13996-634">The string "sig"</span></span>
- <span data-ttu-id="13996-635">0-2 caratteri dello spazio vuoto</span><span class="sxs-lookup"><span data-stu-id="13996-635">0-2 whitespace characters</span></span>
- <span data-ttu-id="13996-636">Segno di uguale (=)</span><span class="sxs-lookup"><span data-stu-id="13996-636">An equal sign (=)</span></span>
- <span data-ttu-id="13996-637">0-2 caratteri dello spazio vuoto</span><span class="sxs-lookup"><span data-stu-id="13996-637">0-2 whitespace characters</span></span>
- <span data-ttu-id="13996-638">Qualsiasi combinazione tra 43-53 caratteri che sono minuscoli o maiuscoli, cifre o il segno di percentuale (%)</span><span class="sxs-lookup"><span data-stu-id="13996-638">Any combination of between 43-53 characters that are lower- or uppercase letters, digits, or the percent sign (%)</span></span>
- <span data-ttu-id="13996-639">La stringa "% 3D"</span><span class="sxs-lookup"><span data-stu-id="13996-639">The string "%3d"</span></span>
- <span data-ttu-id="13996-640">Qualsiasi carattere che non sia una lettera, una cifra o un segno di percentuale inferiore o maiuscolo (%)</span><span class="sxs-lookup"><span data-stu-id="13996-640">Any character that is not a lower- or uppercase letter, digit, or percent sign (%)</span></span>

### <a name="checksum"></a><span data-ttu-id="13996-641">Checksum</span><span class="sxs-lookup"><span data-stu-id="13996-641">Checksum</span></span>

<span data-ttu-id="13996-642">No</span><span class="sxs-lookup"><span data-stu-id="13996-642">No</span></span>

### <a name="definition"></a><span data-ttu-id="13996-643">Definizione</span><span class="sxs-lookup"><span data-stu-id="13996-643">Definition</span></span>

<span data-ttu-id="13996-644">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="13996-644">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="13996-645">L'espressione regolare CEP_Regex_AzureSAS trova il contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="13996-645">The regular expression CEP_Regex_AzureSAS finds content that matches the pattern.</span></span>

```
<!--Azure SAS-->
<Entity id="4d235014-e564-47f4-a6fb-6ebb4a826834" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_AzureSAS" />
  </Pattern>
</Entity>
```

## <a name="azure-service-bus-connection-string"></a><span data-ttu-id="13996-646">Stringa di connessione bus di servizio di Azure</span><span class="sxs-lookup"><span data-stu-id="13996-646">Azure Service Bus Connection String</span></span>

### <a name="format"></a><span data-ttu-id="13996-647">Formato</span><span class="sxs-lookup"><span data-stu-id="13996-647">Format</span></span>

<span data-ttu-id="13996-648">Stringa "EndPoint" seguita dai caratteri e dalle stringhe delineati nel modello seguente, incluse le stringhe "ServiceBus. Windows.</span><span class="sxs-lookup"><span data-stu-id="13996-648">The string "EndPoint" followed by the characters and strings outlined in the pattern below, including the strings "servicebus.windows.</span></span><!--no-hyperlink--><span data-ttu-id="13996-649">NET "e" SharedAccesKey ".</span><span class="sxs-lookup"><span data-stu-id="13996-649">net" and "SharedAccesKey".</span></span>

### <a name="pattern"></a><span data-ttu-id="13996-650">Modello</span><span class="sxs-lookup"><span data-stu-id="13996-650">Pattern</span></span>

- <span data-ttu-id="13996-651">La stringa "EndPoint"</span><span class="sxs-lookup"><span data-stu-id="13996-651">The string "EndPoint"</span></span>
- <span data-ttu-id="13996-652">0-2 caratteri dello spazio vuoto</span><span class="sxs-lookup"><span data-stu-id="13996-652">0-2 whitespace characters</span></span>
- <span data-ttu-id="13996-653">Segno di uguale (=)</span><span class="sxs-lookup"><span data-stu-id="13996-653">An equal sign (=)</span></span>
- <span data-ttu-id="13996-654">0-2 caratteri dello spazio vuoto</span><span class="sxs-lookup"><span data-stu-id="13996-654">0-2 whitespace characters</span></span>
- <span data-ttu-id="13996-655">Qualsiasi combinazione tra 1-200 lettere, cifre, simboli, caratteri speciali o spazi in maiuscolo o minuscolo</span><span class="sxs-lookup"><span data-stu-id="13996-655">Any combination of between 1-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="13996-656">La stringa "ServiceBus. Windows.</span><span class="sxs-lookup"><span data-stu-id="13996-656">The string "servicebus.windows.</span></span><!--no-hyperlink--><span data-ttu-id="13996-657">NET</span><span class="sxs-lookup"><span data-stu-id="13996-657">net"</span></span>
- <span data-ttu-id="13996-658">Qualsiasi combinazione tra 1-200 lettere, cifre, simboli, caratteri speciali o spazi in maiuscolo o minuscolo</span><span class="sxs-lookup"><span data-stu-id="13996-658">Any combination of between 1-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="13996-659">La stringa "SharedAccessKey"</span><span class="sxs-lookup"><span data-stu-id="13996-659">The string "SharedAccessKey"</span></span>
- <span data-ttu-id="13996-660">0-2 caratteri dello spazio vuoto</span><span class="sxs-lookup"><span data-stu-id="13996-660">0-2 whitespace characters</span></span>
- <span data-ttu-id="13996-661">Segno di uguale (=)</span><span class="sxs-lookup"><span data-stu-id="13996-661">An equal sign (=)</span></span>
- <span data-ttu-id="13996-662">0-2 caratteri dello spazio vuoto</span><span class="sxs-lookup"><span data-stu-id="13996-662">0-2 whitespace characters</span></span>
- <span data-ttu-id="13996-663">Qualsiasi combinazione di 43 caratteri che sono lettere maiuscole o minuscole, cifre, barra (/) o segno più (+)</span><span class="sxs-lookup"><span data-stu-id="13996-663">Any combination of 43 characters that are lower- or uppercase letters, digits, forward slash (/), or plus sign (+)</span></span>
- <span data-ttu-id="13996-664">Segno di uguale (=)</span><span class="sxs-lookup"><span data-stu-id="13996-664">An equal sign (=)</span></span>

### <a name="checksum"></a><span data-ttu-id="13996-665">Checksum</span><span class="sxs-lookup"><span data-stu-id="13996-665">Checksum</span></span>

<span data-ttu-id="13996-666">No</span><span class="sxs-lookup"><span data-stu-id="13996-666">No</span></span>

### <a name="definition"></a><span data-ttu-id="13996-667">Definizione</span><span class="sxs-lookup"><span data-stu-id="13996-667">Definition</span></span>

<span data-ttu-id="13996-668">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="13996-668">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="13996-669">L'espressione regolare CEP_Regex_AzureServiceBusConnectionString trova il contenuto corrispondente al modello.</span><span class="sxs-lookup"><span data-stu-id="13996-669">The regular expression CEP_Regex_AzureServiceBusConnectionString finds content that matches the pattern..</span></span>
- <span data-ttu-id="13996-670">L'espressione regolare CEP_CommonExampleKeywords non \*\*\*\* trova contenuto corrispondente al modello.</span><span class="sxs-lookup"><span data-stu-id="13996-670">The regular expression CEP_CommonExampleKeywords does **not** find content that matches the pattern.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="13996-671">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="13996-671">Keywords</span></span>

#### <a name="cepcommonexamplekeywords"></a><span data-ttu-id="13996-672">CEP_CommonExampleKeywords</span><span class="sxs-lookup"><span data-stu-id="13996-672">CEP_CommonExampleKeywords</span></span>

<span data-ttu-id="13996-673">Si noti che tecnicamente questo tipo di informazioni riservate identifica queste parole chiave utilizzando un'espressione regolare, non un elenco di parola chiave.</span><span class="sxs-lookup"><span data-stu-id="13996-673">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="13996-674">contoso</span><span class="sxs-lookup"><span data-stu-id="13996-674">contoso</span></span>
- <span data-ttu-id="13996-675">Fabrikam</span><span class="sxs-lookup"><span data-stu-id="13996-675">fabrikam</span></span>
- <span data-ttu-id="13996-676">Northwind</span><span class="sxs-lookup"><span data-stu-id="13996-676">northwind</span></span>
- <span data-ttu-id="13996-677">sandbox</span><span class="sxs-lookup"><span data-stu-id="13996-677">sandbox</span></span>
- <span data-ttu-id="13996-678">OneBox</span><span class="sxs-lookup"><span data-stu-id="13996-678">onebox</span></span>
- <span data-ttu-id="13996-679">localhost</span><span class="sxs-lookup"><span data-stu-id="13996-679">localhost</span></span>
- <span data-ttu-id="13996-680">127.0.0.1</span><span class="sxs-lookup"><span data-stu-id="13996-680">127.0.0.1</span></span>
- <span data-ttu-id="13996-681">testacs.</span><span class="sxs-lookup"><span data-stu-id="13996-681">testacs.</span></span><!--no-hyperlink--><span data-ttu-id="13996-682">com</span><span class="sxs-lookup"><span data-stu-id="13996-682">com</span></span>
- <span data-ttu-id="13996-683">s-int.</span><span class="sxs-lookup"><span data-stu-id="13996-683">s-int.</span></span><!--no-hyperlink--><span data-ttu-id="13996-684">NET</span><span class="sxs-lookup"><span data-stu-id="13996-684">net</span></span>

## <a name="azure-storage-account-key"></a><span data-ttu-id="13996-685">Chiave dell'account di archiviazione di Azure</span><span class="sxs-lookup"><span data-stu-id="13996-685">Azure Storage Account Key</span></span>

### <a name="format"></a><span data-ttu-id="13996-686">Formato</span><span class="sxs-lookup"><span data-stu-id="13996-686">Format</span></span>

<span data-ttu-id="13996-687">La stringa "DefaultEndpointsProtocol" seguita dai caratteri e dalle stringhe delineate nel modello seguente, inclusa la stringa "AccountKey".</span><span class="sxs-lookup"><span data-stu-id="13996-687">The string "DefaultEndpointsProtocol" followed by the characters and strings outlined in the pattern below, including the string "AccountKey".</span></span>

### <a name="pattern"></a><span data-ttu-id="13996-688">Modello</span><span class="sxs-lookup"><span data-stu-id="13996-688">Pattern</span></span>

- <span data-ttu-id="13996-689">La stringa "DefaultEndpointsProtocol"</span><span class="sxs-lookup"><span data-stu-id="13996-689">The string "DefaultEndpointsProtocol"</span></span>
- <span data-ttu-id="13996-690">0-2 caratteri dello spazio vuoto</span><span class="sxs-lookup"><span data-stu-id="13996-690">0-2 whitespace characters</span></span>
- <span data-ttu-id="13996-691">Segno di uguale (=)</span><span class="sxs-lookup"><span data-stu-id="13996-691">An equal sign (=)</span></span>
- <span data-ttu-id="13996-692">0-2 caratteri dello spazio vuoto</span><span class="sxs-lookup"><span data-stu-id="13996-692">0-2 whitespace characters</span></span>
- <span data-ttu-id="13996-693">Qualsiasi combinazione tra 1-200 lettere, cifre, simboli, caratteri speciali o spazi in maiuscolo o minuscolo</span><span class="sxs-lookup"><span data-stu-id="13996-693">Any combination of between 1-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="13996-694">La stringa "AccountKey"</span><span class="sxs-lookup"><span data-stu-id="13996-694">The string "AccountKey"</span></span>
- <span data-ttu-id="13996-695">0-2 caratteri dello spazio vuoto</span><span class="sxs-lookup"><span data-stu-id="13996-695">0-2 whitespace characters</span></span>
- <span data-ttu-id="13996-696">Segno di uguale (=)</span><span class="sxs-lookup"><span data-stu-id="13996-696">An equal sign (=)</span></span>
- <span data-ttu-id="13996-697">0-2 caratteri dello spazio vuoto</span><span class="sxs-lookup"><span data-stu-id="13996-697">0-2 whitespace characters</span></span>
- <span data-ttu-id="13996-698">Qualsiasi combinazione di 86 caratteri che sono lettere maiuscole o minuscole, cifre, barra (/) o segno più (+)</span><span class="sxs-lookup"><span data-stu-id="13996-698">Any combination of 86 characters that are lower- or uppercase letters, digits, forward slash (/), or plus sign (+)</span></span>
- <span data-ttu-id="13996-699">Due segni uguali (=)</span><span class="sxs-lookup"><span data-stu-id="13996-699">Two equal signs (=)</span></span>

### <a name="checksum"></a><span data-ttu-id="13996-700">Checksum</span><span class="sxs-lookup"><span data-stu-id="13996-700">Checksum</span></span>

<span data-ttu-id="13996-701">No</span><span class="sxs-lookup"><span data-stu-id="13996-701">No</span></span>

### <a name="definition"></a><span data-ttu-id="13996-702">Definizione</span><span class="sxs-lookup"><span data-stu-id="13996-702">Definition</span></span>

<span data-ttu-id="13996-703">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="13996-703">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="13996-704">L'espressione regolare CEP_Regex_AzureStorageAccountKey trova il contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="13996-704">The regular expression CEP_Regex_AzureStorageAccountKey finds content that matches the pattern.</span></span>
- <span data-ttu-id="13996-705">L'espressione regolare CEP_AzureEmulatorStorageAccountFilter non \*\*\*\* trova contenuto corrispondente al modello.</span><span class="sxs-lookup"><span data-stu-id="13996-705">The regular expression CEP_AzureEmulatorStorageAccountFilter does **not** find content that matches the pattern.</span></span>
- <span data-ttu-id="13996-706">L'espressione regolare CEP_CommonExampleKeywords non \*\*\*\* trova contenuto corrispondente al modello.</span><span class="sxs-lookup"><span data-stu-id="13996-706">The regular expression CEP_CommonExampleKeywords does **not** find content that matches the pattern.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="13996-707">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="13996-707">Keywords</span></span>

#### <a name="cepazureemulatorstorageaccountfilter"></a><span data-ttu-id="13996-708">CEP_AzureEmulatorStorageAccountFilter</span><span class="sxs-lookup"><span data-stu-id="13996-708">CEP_AzureEmulatorStorageAccountFilter</span></span>

<span data-ttu-id="13996-709">Si noti che tecnicamente questo tipo di informazioni riservate identifica queste parole chiave utilizzando un'espressione regolare, non un elenco di parola chiave.</span><span class="sxs-lookup"><span data-stu-id="13996-709">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="13996-710">Eby8vdM02xNOcqFlqUwJPLlmEtlCDXJ1OUzFT50uSRZ6IFsuFq2UVErCz4I6tq/K1SZFPTOtr/KBHBeksoGMGw = =</span><span class="sxs-lookup"><span data-stu-id="13996-710">Eby8vdM02xNOcqFlqUwJPLlmEtlCDXJ1OUzFT50uSRZ6IFsuFq2UVErCz4I6tq/K1SZFPTOtr/KBHBeksoGMGw==</span></span>

#### <a name="cepcommonexamplekeywords"></a><span data-ttu-id="13996-711">CEP_CommonExampleKeywords</span><span class="sxs-lookup"><span data-stu-id="13996-711">CEP_CommonExampleKeywords</span></span>

<span data-ttu-id="13996-712">Si noti che tecnicamente questo tipo di informazioni riservate identifica queste parole chiave utilizzando un'espressione regolare, non un elenco di parola chiave.</span><span class="sxs-lookup"><span data-stu-id="13996-712">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="13996-713">contoso</span><span class="sxs-lookup"><span data-stu-id="13996-713">contoso</span></span>
- <span data-ttu-id="13996-714">Fabrikam</span><span class="sxs-lookup"><span data-stu-id="13996-714">fabrikam</span></span>
- <span data-ttu-id="13996-715">Northwind</span><span class="sxs-lookup"><span data-stu-id="13996-715">northwind</span></span>
- <span data-ttu-id="13996-716">sandbox</span><span class="sxs-lookup"><span data-stu-id="13996-716">sandbox</span></span>
- <span data-ttu-id="13996-717">OneBox</span><span class="sxs-lookup"><span data-stu-id="13996-717">onebox</span></span>
- <span data-ttu-id="13996-718">localhost</span><span class="sxs-lookup"><span data-stu-id="13996-718">localhost</span></span>
- <span data-ttu-id="13996-719">127.0.0.1</span><span class="sxs-lookup"><span data-stu-id="13996-719">127.0.0.1</span></span>
- <span data-ttu-id="13996-720">testacs.</span><span class="sxs-lookup"><span data-stu-id="13996-720">testacs.</span></span><!--no-hyperlink--><span data-ttu-id="13996-721">com</span><span class="sxs-lookup"><span data-stu-id="13996-721">com</span></span>
- <span data-ttu-id="13996-722">s-int.</span><span class="sxs-lookup"><span data-stu-id="13996-722">s-int.</span></span><!--no-hyperlink--><span data-ttu-id="13996-723">NET</span><span class="sxs-lookup"><span data-stu-id="13996-723">net</span></span>

## <a name="azure-storage-account-key-generic"></a><span data-ttu-id="13996-724">Chiave dell'account di archiviazione di Azure (generico)</span><span class="sxs-lookup"><span data-stu-id="13996-724">Azure Storage Account Key (Generic)</span></span>

### <a name="format"></a><span data-ttu-id="13996-725">Formato</span><span class="sxs-lookup"><span data-stu-id="13996-725">Format</span></span>

<span data-ttu-id="13996-726">Qualsiasi combinazione di 86 lettere maiuscole e minuscole, cifre, barra (/) o segno più (+), preceduto o seguito dai caratteri delineati nel modello seguente.</span><span class="sxs-lookup"><span data-stu-id="13996-726">Any combination of 86 lower- or uppercase letters, digits, the forward slash (/), or plus sign (+), preceded or followed by the characters outlined in the pattern below.</span></span>

### <a name="pattern"></a><span data-ttu-id="13996-727">Modello</span><span class="sxs-lookup"><span data-stu-id="13996-727">Pattern</span></span>

- <span data-ttu-id="13996-728">0-1 del simbolo maggiore di (>), apostrofo ('), segno di uguale (=), virgolette (") o segno numerico (#)</span><span class="sxs-lookup"><span data-stu-id="13996-728">0-1 of the greater than symbol (>), apostrophe ('), equal sign (=), quotation mark ("), or number sign (#)</span></span>
- <span data-ttu-id="13996-729">Qualsiasi combinazione di 86 caratteri che sono lettere maiuscole o minuscole, cifre, barra (/) o segno più (+)</span><span class="sxs-lookup"><span data-stu-id="13996-729">Any combination of 86 characters that are lower- or uppercase letters, digits, the forward slash (/), or plus sign (+)</span></span>
- <span data-ttu-id="13996-730">Due segni uguali (=)</span><span class="sxs-lookup"><span data-stu-id="13996-730">Two equal signs (=)</span></span>


### <a name="checksum"></a><span data-ttu-id="13996-731">Checksum</span><span class="sxs-lookup"><span data-stu-id="13996-731">Checksum</span></span>

<span data-ttu-id="13996-732">No</span><span class="sxs-lookup"><span data-stu-id="13996-732">No</span></span>

### <a name="definition"></a><span data-ttu-id="13996-733">Definizione</span><span class="sxs-lookup"><span data-stu-id="13996-733">Definition</span></span>

<span data-ttu-id="13996-734">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="13996-734">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="13996-735">L'espressione regolare CEP_Regex_AzureStorageAccountKeyGeneric trova il contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="13996-735">The regular expression CEP_Regex_AzureStorageAccountKeyGeneric finds content that matches the pattern.</span></span>

```
<!--Azure Storage Account Key (Generic)-->
<Entity id="7ff41bd0-5419-4523-91d6-383b3a37f084" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_AzureStorageAccountKeyGeneric" />
  </Pattern>
</Entity>
```

## <a name="belgium-national-number"></a><span data-ttu-id="13996-736">Belgio - Numero nazionale</span><span class="sxs-lookup"><span data-stu-id="13996-736">Belgium National Number</span></span>

### <a name="format"></a><span data-ttu-id="13996-737">Formato</span><span class="sxs-lookup"><span data-stu-id="13996-737">Format</span></span>

<span data-ttu-id="13996-738">11 cifre più delimitatori</span><span class="sxs-lookup"><span data-stu-id="13996-738">11 digits plus delimiters</span></span>

### <a name="pattern"></a><span data-ttu-id="13996-739">Modello</span><span class="sxs-lookup"><span data-stu-id="13996-739">Pattern</span></span>

<span data-ttu-id="13996-740">11 cifre più delimitatori:</span><span class="sxs-lookup"><span data-stu-id="13996-740">11 digits plus delimiters:</span></span>
- <span data-ttu-id="13996-741">Sei cifre e due punti nel formato AA.MM.GG per data di nascita </span><span class="sxs-lookup"><span data-stu-id="13996-741">Six digits and two periods in the format YY.MM.DD for date of birth</span></span> 
- <span data-ttu-id="13996-742">Una lineetta</span><span class="sxs-lookup"><span data-stu-id="13996-742">A hyphen</span></span> 
- <span data-ttu-id="13996-743">Tre cifre sequenziali (dispari sia per uomini che per donne) </span><span class="sxs-lookup"><span data-stu-id="13996-743">Three sequential digits (odd for males, even for females)</span></span> 
- <span data-ttu-id="13996-744">Un punto</span><span class="sxs-lookup"><span data-stu-id="13996-744">A period</span></span> 
- <span data-ttu-id="13996-745">Due cifre, ovvero una cifra di controllo</span><span class="sxs-lookup"><span data-stu-id="13996-745">Two digits that are a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="13996-746">Checksum</span><span class="sxs-lookup"><span data-stu-id="13996-746">Checksum</span></span>

<span data-ttu-id="13996-747">Sì</span><span class="sxs-lookup"><span data-stu-id="13996-747">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="13996-748">Definizione</span><span class="sxs-lookup"><span data-stu-id="13996-748">Definition</span></span>

<span data-ttu-id="13996-749">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="13996-749">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="13996-750">La funzione Func_belgium_national_number trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="13996-750">The function Func_belgium_national_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="13996-751">Viene trovata una parola chiave da Keyword_belgium_national_number.</span><span class="sxs-lookup"><span data-stu-id="13996-751">A keyword from Keyword_belgium_national_number is found.</span></span>
- <span data-ttu-id="13996-752">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="13996-752">The checksum passes.</span></span>

```
<!-- Belgium National Number -->
  <Entity id="fb969c9e-0fd1-4b18-8091-a2123c5e6a54" recommendedConfidence="75" patternsProximity="300">
   <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_belgium_national_number"/>
     <Match idRef="Keyword_belgium_national_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="13996-753">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="13996-753">Keywords</span></span>

#### <a name="keywordbelgiumnationalnumber"></a><span data-ttu-id="13996-754">Keyword_belgium_national_number</span><span class="sxs-lookup"><span data-stu-id="13996-754">Keyword_belgium_national_number</span></span>

- <span data-ttu-id="13996-755">Identità</span><span class="sxs-lookup"><span data-stu-id="13996-755">Identity</span></span>
- <span data-ttu-id="13996-756">Registrazione</span><span class="sxs-lookup"><span data-stu-id="13996-756">Registration</span></span>
- <span data-ttu-id="13996-757">Identificazione</span><span class="sxs-lookup"><span data-stu-id="13996-757">Identification</span></span> 
- <span data-ttu-id="13996-758">ID</span><span class="sxs-lookup"><span data-stu-id="13996-758">ID</span></span> 
- <span data-ttu-id="13996-759">Identiteitskaart</span><span class="sxs-lookup"><span data-stu-id="13996-759">Identiteitskaart</span></span>
- <span data-ttu-id="13996-760">Registratie nummer</span><span class="sxs-lookup"><span data-stu-id="13996-760">Registratie nummer</span></span> 
- <span data-ttu-id="13996-761">Identificatie nummer</span><span class="sxs-lookup"><span data-stu-id="13996-761">Identificatie nummer</span></span> 
- <span data-ttu-id="13996-762">Identiteit</span><span class="sxs-lookup"><span data-stu-id="13996-762">Identiteit</span></span>
- <span data-ttu-id="13996-763">Registratie</span><span class="sxs-lookup"><span data-stu-id="13996-763">Registratie</span></span>
- <span data-ttu-id="13996-764">Identificatie</span><span class="sxs-lookup"><span data-stu-id="13996-764">Identificatie</span></span> 
- <span data-ttu-id="13996-765">Carte d’identité</span><span class="sxs-lookup"><span data-stu-id="13996-765">Carte d’identité</span></span> 
- <span data-ttu-id="13996-766">numéro d'immatriculation</span><span class="sxs-lookup"><span data-stu-id="13996-766">numéro d'immatriculation</span></span>
- <span data-ttu-id="13996-767">numéro d'identification</span><span class="sxs-lookup"><span data-stu-id="13996-767">numéro d'identification</span></span>
- <span data-ttu-id="13996-768">identité</span><span class="sxs-lookup"><span data-stu-id="13996-768">identité</span></span> 
- <span data-ttu-id="13996-769">iscrizione</span><span class="sxs-lookup"><span data-stu-id="13996-769">inscription</span></span> 
- <span data-ttu-id="13996-770">Identifikation</span><span class="sxs-lookup"><span data-stu-id="13996-770">Identifikation</span></span>
- <span data-ttu-id="13996-771">Identifizierung</span><span class="sxs-lookup"><span data-stu-id="13996-771">Identifizierung</span></span>
- <span data-ttu-id="13996-772">Identifikationsnummer</span><span class="sxs-lookup"><span data-stu-id="13996-772">Identifikationsnummer</span></span>
- <span data-ttu-id="13996-773">Personalausweis</span><span class="sxs-lookup"><span data-stu-id="13996-773">Personalausweis</span></span>
- <span data-ttu-id="13996-774">Registrierung</span><span class="sxs-lookup"><span data-stu-id="13996-774">Registrierung</span></span>
- <span data-ttu-id="13996-775">Registrationsnummer</span><span class="sxs-lookup"><span data-stu-id="13996-775">Registrationsnummer</span></span>

   
## <a name="brazil-cpf-number"></a><span data-ttu-id="13996-776">Numero CPF Brasile</span><span class="sxs-lookup"><span data-stu-id="13996-776">Brazil CPF Number</span></span>

### <a name="format"></a><span data-ttu-id="13996-777">Formato</span><span class="sxs-lookup"><span data-stu-id="13996-777">Format</span></span>

<span data-ttu-id="13996-778">11 cifre che includono una cifra di controllo e possono essere formattate o non formattate</span><span class="sxs-lookup"><span data-stu-id="13996-778">11 digits that include a check digit and can be formatted or unformatted</span></span>

### <a name="pattern"></a><span data-ttu-id="13996-779">Modello</span><span class="sxs-lookup"><span data-stu-id="13996-779">Pattern</span></span>

<span data-ttu-id="13996-780">Formattato</span><span class="sxs-lookup"><span data-stu-id="13996-780">Formatted:</span></span>
- <span data-ttu-id="13996-781">Tre cifre</span><span class="sxs-lookup"><span data-stu-id="13996-781">Three digits</span></span> 
- <span data-ttu-id="13996-782">Un punto </span><span class="sxs-lookup"><span data-stu-id="13996-782">A period</span></span> 
- <span data-ttu-id="13996-783">Tre cifre</span><span class="sxs-lookup"><span data-stu-id="13996-783">Three digits</span></span> 
- <span data-ttu-id="13996-784">Un punto </span><span class="sxs-lookup"><span data-stu-id="13996-784">A period</span></span> 
- <span data-ttu-id="13996-785">Tre cifre</span><span class="sxs-lookup"><span data-stu-id="13996-785">Three digits</span></span> 
- <span data-ttu-id="13996-786">Una lineetta</span><span class="sxs-lookup"><span data-stu-id="13996-786">A hyphen</span></span> 
- <span data-ttu-id="13996-787">Due cifre, ovvero le cifre di controllo</span><span class="sxs-lookup"><span data-stu-id="13996-787">Two digits which are check digits</span></span>

<span data-ttu-id="13996-788">Formattato</span><span class="sxs-lookup"><span data-stu-id="13996-788">Unformatted:</span></span>
- <span data-ttu-id="13996-789">11 cifre dove le ultime due sono cifre di controllo</span><span class="sxs-lookup"><span data-stu-id="13996-789">11 digits where the last two digits are check digits</span></span>

### <a name="checksum"></a><span data-ttu-id="13996-790">Checksum</span><span class="sxs-lookup"><span data-stu-id="13996-790">Checksum</span></span>

<span data-ttu-id="13996-791">Sì</span><span class="sxs-lookup"><span data-stu-id="13996-791">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="13996-792">Definizione</span><span class="sxs-lookup"><span data-stu-id="13996-792">Definition</span></span>

<span data-ttu-id="13996-793">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="13996-793">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="13996-794">La funzione Func_brazil_cpf trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="13996-794">The function Func_brazil_cpf finds content that matches the pattern.</span></span>
- <span data-ttu-id="13996-795">Viene trovata una parola chiave da Keyword_brazil_cpf.</span><span class="sxs-lookup"><span data-stu-id="13996-795">A keyword from Keyword_brazil_cpf is found.</span></span>
- <span data-ttu-id="13996-796">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="13996-796">The checksum passes.</span></span>

<span data-ttu-id="13996-797">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="13996-797">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="13996-798">La funzione Func_brazil_cpf trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="13996-798">The function Func_brazil_cpf finds content that matches the pattern.</span></span>
- <span data-ttu-id="13996-799">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="13996-799">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="13996-800">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="13996-800">Keywords</span></span>

#### <a name="keywordbrazilcpf"></a><span data-ttu-id="13996-801">Keyword_brazil_cpf</span><span class="sxs-lookup"><span data-stu-id="13996-801">Keyword_brazil_cpf</span></span>

- <span data-ttu-id="13996-802">CPF</span><span class="sxs-lookup"><span data-stu-id="13996-802">CPF</span></span>
- <span data-ttu-id="13996-803">Identificazione</span><span class="sxs-lookup"><span data-stu-id="13996-803">Identification</span></span>
- <span data-ttu-id="13996-804">Registrazione</span><span class="sxs-lookup"><span data-stu-id="13996-804">Registration</span></span>
- <span data-ttu-id="13996-805">Entrate</span><span class="sxs-lookup"><span data-stu-id="13996-805">Revenue</span></span>
- <span data-ttu-id="13996-806">Cadastro de Pessoas Físicas</span><span class="sxs-lookup"><span data-stu-id="13996-806">Cadastro de Pessoas Físicas</span></span> 
- <span data-ttu-id="13996-807">Imposto</span><span class="sxs-lookup"><span data-stu-id="13996-807">Imposto</span></span> 
- <span data-ttu-id="13996-808">Identificação</span><span class="sxs-lookup"><span data-stu-id="13996-808">Identificação</span></span> 
- <span data-ttu-id="13996-809">Inscrição</span><span class="sxs-lookup"><span data-stu-id="13996-809">Inscrição</span></span> 
- <span data-ttu-id="13996-810">Receita</span><span class="sxs-lookup"><span data-stu-id="13996-810">Receita</span></span> 
   
## <a name="brazil-legal-entity-number-cnpj"></a><span data-ttu-id="13996-811">Brasile - Codice fiscale persone giuridiche (CNPJ)</span><span class="sxs-lookup"><span data-stu-id="13996-811">Brazil Legal Entity Number (CNPJ)</span></span>

### <a name="format"></a><span data-ttu-id="13996-812">Formato</span><span class="sxs-lookup"><span data-stu-id="13996-812">Format</span></span>

<span data-ttu-id="13996-813">14 cifre che includono il numero di registrazione, il codice della filiale, le cifre di controllo e i delimitatori</span><span class="sxs-lookup"><span data-stu-id="13996-813">14 digits that include a registration number, branch number, and check digits, plus delimiters</span></span>

### <a name="pattern"></a><span data-ttu-id="13996-814">Modello</span><span class="sxs-lookup"><span data-stu-id="13996-814">Pattern</span></span>
<span data-ttu-id="13996-815">14 cifre più delimitatori:</span><span class="sxs-lookup"><span data-stu-id="13996-815">14 digits, plus delimiters:</span></span>
- <span data-ttu-id="13996-816">Due cifre</span><span class="sxs-lookup"><span data-stu-id="13996-816">Two digits</span></span> 
- <span data-ttu-id="13996-817">Un punto </span><span class="sxs-lookup"><span data-stu-id="13996-817">A period</span></span> 
- <span data-ttu-id="13996-818">Tre cifre</span><span class="sxs-lookup"><span data-stu-id="13996-818">Three digits</span></span> 
- <span data-ttu-id="13996-819">Un punto </span><span class="sxs-lookup"><span data-stu-id="13996-819">A period</span></span> 
- <span data-ttu-id="13996-820">Tre cifre (le prime otto sono il numero di registrazione) </span><span class="sxs-lookup"><span data-stu-id="13996-820">Three digits (these first eight digits are the registration number)</span></span> 
- <span data-ttu-id="13996-821">Una barra</span><span class="sxs-lookup"><span data-stu-id="13996-821">A forward slash</span></span> 
- <span data-ttu-id="13996-822">Numero del ramo a quattro cifre </span><span class="sxs-lookup"><span data-stu-id="13996-822">Four-digit branch number</span></span> 
- <span data-ttu-id="13996-823">Una lineetta</span><span class="sxs-lookup"><span data-stu-id="13996-823">A hyphen</span></span> 
- <span data-ttu-id="13996-824">Due cifre, ovvero le cifre di controllo</span><span class="sxs-lookup"><span data-stu-id="13996-824">Two digits which are check digits</span></span>

### <a name="checksum"></a><span data-ttu-id="13996-825">Checksum</span><span class="sxs-lookup"><span data-stu-id="13996-825">Checksum</span></span>

<span data-ttu-id="13996-826">Sì</span><span class="sxs-lookup"><span data-stu-id="13996-826">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="13996-827">Definizione</span><span class="sxs-lookup"><span data-stu-id="13996-827">Definition</span></span>

<span data-ttu-id="13996-828">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="13996-828">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="13996-829">La funzione Func_brazil_cnpj trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="13996-829">The function Func_brazil_cnpj finds content that matches the pattern.</span></span>
- <span data-ttu-id="13996-830">Viene trovata una parola chiave da Keyword_brazil_cnpj.</span><span class="sxs-lookup"><span data-stu-id="13996-830">A keyword from Keyword_brazil_cnpj is found.</span></span>
- <span data-ttu-id="13996-831">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="13996-831">The checksum passes.</span></span>

<span data-ttu-id="13996-832">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="13996-832">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="13996-833">La funzione Func_brazil_cnpj trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="13996-833">The function Func_brazil_cnpj finds content that matches the pattern.</span></span>
- <span data-ttu-id="13996-834">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="13996-834">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="13996-835">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="13996-835">Keywords</span></span>

#### <a name="keywordbrazilcnpj"></a><span data-ttu-id="13996-836">Keyword_brazil_cnpj</span><span class="sxs-lookup"><span data-stu-id="13996-836">Keyword_brazil_cnpj</span></span>

- <span data-ttu-id="13996-837">CNPJ</span><span class="sxs-lookup"><span data-stu-id="13996-837">CNPJ</span></span> 
- <span data-ttu-id="13996-838">CNPJ/MF</span><span class="sxs-lookup"><span data-stu-id="13996-838">CNPJ/MF</span></span> 
- <span data-ttu-id="13996-839">CNPJ-MF</span><span class="sxs-lookup"><span data-stu-id="13996-839">CNPJ-MF</span></span> 
- <span data-ttu-id="13996-840">Codice fiscale persone giuridiche</span><span class="sxs-lookup"><span data-stu-id="13996-840">National Registry of Legal Entities</span></span> 
- <span data-ttu-id="13996-841">Registro contribuenti</span><span class="sxs-lookup"><span data-stu-id="13996-841">Taxpayers Registry</span></span> 
- <span data-ttu-id="13996-842">Persona giuridica</span><span class="sxs-lookup"><span data-stu-id="13996-842">Legal entity</span></span> 
- <span data-ttu-id="13996-843">Persone giuridiche</span><span class="sxs-lookup"><span data-stu-id="13996-843">Legal entities</span></span> 
- <span data-ttu-id="13996-844">Stato della registrazione</span><span class="sxs-lookup"><span data-stu-id="13996-844">Registration Status</span></span> 
- <span data-ttu-id="13996-845">Business</span><span class="sxs-lookup"><span data-stu-id="13996-845">Business</span></span> 
- <span data-ttu-id="13996-846">Company</span><span class="sxs-lookup"><span data-stu-id="13996-846">Company</span></span>
- <span data-ttu-id="13996-847">CNPJ</span><span class="sxs-lookup"><span data-stu-id="13996-847">CNPJ</span></span> 
- <span data-ttu-id="13996-848">Cadastro Nacional da Pessoa Jurídica</span><span class="sxs-lookup"><span data-stu-id="13996-848">Cadastro Nacional da Pessoa Jurídica</span></span> 
- <span data-ttu-id="13996-849">Cadastro Geral de Contribuintes</span><span class="sxs-lookup"><span data-stu-id="13996-849">Cadastro Geral de Contribuintes</span></span> 
- <span data-ttu-id="13996-850">CGC</span><span class="sxs-lookup"><span data-stu-id="13996-850">CGC</span></span> 
- <span data-ttu-id="13996-851">Pessoa jurídica</span><span class="sxs-lookup"><span data-stu-id="13996-851">Pessoa jurídica</span></span> 
- <span data-ttu-id="13996-852">Pessoas jurídicas</span><span class="sxs-lookup"><span data-stu-id="13996-852">Pessoas jurídicas</span></span> 
- <span data-ttu-id="13996-853">Situação cadastral</span><span class="sxs-lookup"><span data-stu-id="13996-853">Situação cadastral</span></span> 
- <span data-ttu-id="13996-854">Inscrição</span><span class="sxs-lookup"><span data-stu-id="13996-854">Inscrição</span></span> 
- <span data-ttu-id="13996-855">Empresa</span><span class="sxs-lookup"><span data-stu-id="13996-855">Empresa</span></span> 
   
## <a name="brazil-national-id-card-rg"></a><span data-ttu-id="13996-856">	Carta d'identità (Brasile) (RG)</span><span class="sxs-lookup"><span data-stu-id="13996-856">Brazil National ID Card (RG)</span></span>

### <a name="format"></a><span data-ttu-id="13996-857">Formato</span><span class="sxs-lookup"><span data-stu-id="13996-857">Format</span></span>

<span data-ttu-id="13996-858">Registro Geral (formato precedente): nove cifre</span><span class="sxs-lookup"><span data-stu-id="13996-858">Registro Geral (old format): Nine digits</span></span>

<span data-ttu-id="13996-859">Registro de Identidade (RIC) (nuovo formato): 11 cifre</span><span class="sxs-lookup"><span data-stu-id="13996-859">Registro de Identidade (RIC) (new format): 11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="13996-860">Modello</span><span class="sxs-lookup"><span data-stu-id="13996-860">Pattern</span></span>

<span data-ttu-id="13996-861">Registro Geral (formato precedente):</span><span class="sxs-lookup"><span data-stu-id="13996-861">Registro Geral (old format):</span></span>
- <span data-ttu-id="13996-862">Due cifre</span><span class="sxs-lookup"><span data-stu-id="13996-862">Two digits</span></span> 
- <span data-ttu-id="13996-863">Un punto </span><span class="sxs-lookup"><span data-stu-id="13996-863">A period</span></span> 
- <span data-ttu-id="13996-864">Tre cifre</span><span class="sxs-lookup"><span data-stu-id="13996-864">Three digits</span></span> 
- <span data-ttu-id="13996-865">Un punto </span><span class="sxs-lookup"><span data-stu-id="13996-865">A period</span></span> 
- <span data-ttu-id="13996-866">Tre cifre</span><span class="sxs-lookup"><span data-stu-id="13996-866">Three digits</span></span> 
- <span data-ttu-id="13996-867">Una lineetta</span><span class="sxs-lookup"><span data-stu-id="13996-867">A hyphen</span></span> 
- <span data-ttu-id="13996-868">Una cifra, ovvero una cifra di controllo</span><span class="sxs-lookup"><span data-stu-id="13996-868">One digit which is a check digit</span></span>

<span data-ttu-id="13996-869">Registro de Identidade (RIC) (nuovo formato):</span><span class="sxs-lookup"><span data-stu-id="13996-869">Registro de Identidade (RIC) (new format):</span></span>
- <span data-ttu-id="13996-870">10 cifre</span><span class="sxs-lookup"><span data-stu-id="13996-870">10 digits</span></span> 
- <span data-ttu-id="13996-871">Una lineetta</span><span class="sxs-lookup"><span data-stu-id="13996-871">A hyphen</span></span> 
- <span data-ttu-id="13996-872">Una cifra, ovvero una cifra di controllo</span><span class="sxs-lookup"><span data-stu-id="13996-872">One digit which is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="13996-873">Checksum</span><span class="sxs-lookup"><span data-stu-id="13996-873">Checksum</span></span>

<span data-ttu-id="13996-874">Sì</span><span class="sxs-lookup"><span data-stu-id="13996-874">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="13996-875">Definizione</span><span class="sxs-lookup"><span data-stu-id="13996-875">Definition</span></span>

<span data-ttu-id="13996-876">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="13996-876">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="13996-877">La funzione Func_brazil_rg trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="13996-877">The function Func_brazil_rg finds content that matches the pattern.</span></span>
- <span data-ttu-id="13996-878">Viene trovata una parola chiave da Keyword_brazil_rg.</span><span class="sxs-lookup"><span data-stu-id="13996-878">A keyword from Keyword_brazil_rg is found.</span></span>
- <span data-ttu-id="13996-879">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="13996-879">The checksum passes.</span></span>

<span data-ttu-id="13996-880">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="13996-880">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="13996-881">La funzione Func_brazil_rg trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="13996-881">The function Func_brazil_rg finds content that matches the pattern.</span></span>
- <span data-ttu-id="13996-882">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="13996-882">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="13996-883">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="13996-883">Keywords</span></span>

#### <a name="keywordbrazilrg"></a><span data-ttu-id="13996-884">Keyword_brazil_rg</span><span class="sxs-lookup"><span data-stu-id="13996-884">Keyword_brazil_rg</span></span>

<span data-ttu-id="13996-885">Cédula de Identidade identità Card National ID número de rregistro Registro de Iidentidade registro Geral RG (questa parola chiave è distinzione tra maiuscole e minuscole) RIC (questa parola chiave è distinzione tra maiuscole e minuscole)</span><span class="sxs-lookup"><span data-stu-id="13996-885">Cédula de identidade identity card national id número de rregistro registro de Iidentidade registro geral RG (this keyword is case sensitive) RIC (this keyword is case sensitive)</span></span> 
   
## <a name="canada-bank-account-number"></a><span data-ttu-id="13996-886">Canada - Numero di conto bancario</span><span class="sxs-lookup"><span data-stu-id="13996-886">Canada Bank Account Number</span></span>

### <a name="format"></a><span data-ttu-id="13996-887">Formato</span><span class="sxs-lookup"><span data-stu-id="13996-887">Format</span></span>

<span data-ttu-id="13996-888">7 o 12 cifre</span><span class="sxs-lookup"><span data-stu-id="13996-888">Seven or twelve digits</span></span>

### <a name="pattern"></a><span data-ttu-id="13996-889">Modello</span><span class="sxs-lookup"><span data-stu-id="13996-889">Pattern</span></span>

<span data-ttu-id="13996-890">Un numero di conto corrente canadese comprende 7 o 12 cifre.</span><span class="sxs-lookup"><span data-stu-id="13996-890">A Canada Bank Account Number is seven or twelve digits.</span></span>

<span data-ttu-id="13996-891">Un numero di transito bancario canadese comprende:</span><span class="sxs-lookup"><span data-stu-id="13996-891">A Canada bank account transit number is:</span></span>
- <span data-ttu-id="13996-892">Cinque cifre</span><span class="sxs-lookup"><span data-stu-id="13996-892">Five digits</span></span> 
- <span data-ttu-id="13996-893">Una lineetta</span><span class="sxs-lookup"><span data-stu-id="13996-893">A hyphen</span></span> 
- <span data-ttu-id="13996-894">Tre cifre o</span><span class="sxs-lookup"><span data-stu-id="13996-894">Three digits OR</span></span>
- <span data-ttu-id="13996-895">Uno zero "0"</span><span class="sxs-lookup"><span data-stu-id="13996-895">A zero "0"</span></span> 
- <span data-ttu-id="13996-896">Otto cifre</span><span class="sxs-lookup"><span data-stu-id="13996-896">Eight digits</span></span>

### <a name="checksum"></a><span data-ttu-id="13996-897">Checksum</span><span class="sxs-lookup"><span data-stu-id="13996-897">Checksum</span></span>

<span data-ttu-id="13996-898">No</span><span class="sxs-lookup"><span data-stu-id="13996-898">No</span></span>

### <a name="definition"></a><span data-ttu-id="13996-899">Definizione</span><span class="sxs-lookup"><span data-stu-id="13996-899">Definition</span></span>

<span data-ttu-id="13996-900">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="13996-900">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="13996-901">L'espressione regolare Regex_canada_bank_account_number restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="13996-901">The regular expression Regex_canada_bank_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="13996-902">Viene trovata una parola chiave da Keyword_canada_bank_account_number.</span><span class="sxs-lookup"><span data-stu-id="13996-902">A keyword from Keyword_canada_bank_account_number is found.</span></span>
- <span data-ttu-id="13996-903">L'espressione regolare Regex_canada_bank_account_transit_number restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="13996-903">The regular expression Regex_canada_bank_account_transit_number finds content that matches the pattern.</span></span>

<span data-ttu-id="13996-904">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="13996-904">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="13996-905">L'espressione regolare Regex_canada_bank_account_number restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="13996-905">The regular expression Regex_canada_bank_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="13996-906">Viene trovata una parola chiave da Keyword_canada_bank_account_number.</span><span class="sxs-lookup"><span data-stu-id="13996-906">A keyword from Keyword_canada_bank_account_number is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="13996-907">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="13996-907">Keywords</span></span>

#### <a name="keywordcanadabankaccountnumber"></a><span data-ttu-id="13996-908">Keyword_canada_bank_account_number</span><span class="sxs-lookup"><span data-stu-id="13996-908">Keyword_canada_bank_account_number</span></span>

- <span data-ttu-id="13996-909">canada savings bonds</span><span class="sxs-lookup"><span data-stu-id="13996-909">canada savings bonds</span></span>
- <span data-ttu-id="13996-910">canada revenue agency</span><span class="sxs-lookup"><span data-stu-id="13996-910">canada revenue agency</span></span>
- <span data-ttu-id="13996-911">canadian financial institution</span><span class="sxs-lookup"><span data-stu-id="13996-911">canadian financial institution</span></span>
- <span data-ttu-id="13996-912">direct deposit form</span><span class="sxs-lookup"><span data-stu-id="13996-912">direct deposit form</span></span>
- <span data-ttu-id="13996-913">canadian citizen</span><span class="sxs-lookup"><span data-stu-id="13996-913">canadian citizen</span></span>
- <span data-ttu-id="13996-914">legal representative</span><span class="sxs-lookup"><span data-stu-id="13996-914">legal representative</span></span>
- <span data-ttu-id="13996-915">notary public</span><span class="sxs-lookup"><span data-stu-id="13996-915">notary public</span></span>
- <span data-ttu-id="13996-916">commissioner for oaths</span><span class="sxs-lookup"><span data-stu-id="13996-916">commissioner for oaths</span></span>
- <span data-ttu-id="13996-917">child care benefit</span><span class="sxs-lookup"><span data-stu-id="13996-917">child care benefit</span></span>
- <span data-ttu-id="13996-918">universal child care</span><span class="sxs-lookup"><span data-stu-id="13996-918">universal child care</span></span>
- <span data-ttu-id="13996-919">canada child tax benefit</span><span class="sxs-lookup"><span data-stu-id="13996-919">canada child tax benefit</span></span>
- <span data-ttu-id="13996-920">income tax benefit</span><span class="sxs-lookup"><span data-stu-id="13996-920">income tax benefit</span></span>
- <span data-ttu-id="13996-921">harmonized sales tax</span><span class="sxs-lookup"><span data-stu-id="13996-921">harmonized sales tax</span></span>
- <span data-ttu-id="13996-922">social insurance number</span><span class="sxs-lookup"><span data-stu-id="13996-922">social insurance number</span></span>
- <span data-ttu-id="13996-923">income tax refund</span><span class="sxs-lookup"><span data-stu-id="13996-923">income tax refund</span></span>
- <span data-ttu-id="13996-924">child tax benefit</span><span class="sxs-lookup"><span data-stu-id="13996-924">child tax benefit</span></span>
- <span data-ttu-id="13996-925">territorial payments</span><span class="sxs-lookup"><span data-stu-id="13996-925">territorial payments</span></span>
- <span data-ttu-id="13996-926">institution number</span><span class="sxs-lookup"><span data-stu-id="13996-926">institution number</span></span>
- <span data-ttu-id="13996-927">deposit request</span><span class="sxs-lookup"><span data-stu-id="13996-927">deposit request</span></span>
- <span data-ttu-id="13996-928">banking information</span><span class="sxs-lookup"><span data-stu-id="13996-928">banking information</span></span>
- <span data-ttu-id="13996-929">direct deposit</span><span class="sxs-lookup"><span data-stu-id="13996-929">direct deposit</span></span>
   
## <a name="canada-drivers-license-number"></a><span data-ttu-id="13996-930">Canada - Numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="13996-930">Canada Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="13996-931">Formato</span><span class="sxs-lookup"><span data-stu-id="13996-931">Format</span></span>

<span data-ttu-id="13996-932">Varia in base alla provincia</span><span class="sxs-lookup"><span data-stu-id="13996-932">Varies by province</span></span>

### <a name="pattern"></a><span data-ttu-id="13996-933">Modello</span><span class="sxs-lookup"><span data-stu-id="13996-933">Pattern</span></span>

<span data-ttu-id="13996-934">Vari modelli per Alberta, Columbia Britannica, Manitoba, Nuovo Brunswick, Terranova e Labrador, Nuova Scozia, Ontario, Isola del Principe Edoardo, Quebec e Saskatchewan</span><span class="sxs-lookup"><span data-stu-id="13996-934">Various patterns covering Alberta, British Columbia, Manitoba, New Brunswick, Newfoundland/Labrador, Nova Scotia, Ontario, Prince Edward Island, Quebec, and Saskatchewan</span></span>

### <a name="checksum"></a><span data-ttu-id="13996-935">Checksum</span><span class="sxs-lookup"><span data-stu-id="13996-935">Checksum</span></span>

<span data-ttu-id="13996-936">No</span><span class="sxs-lookup"><span data-stu-id="13996-936">No</span></span>

### <a name="definition"></a><span data-ttu-id="13996-937">Definizione</span><span class="sxs-lookup"><span data-stu-id="13996-937">Definition</span></span>

<span data-ttu-id="13996-938">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="13996-938">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="13996-939">La funzione Func_[province_name]_drivers_license_number restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="13996-939">The function Func_[province_name]_drivers_license_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="13996-940">Viene trovata una parola chiave da Keyword_[province_name]_drivers_license_name.</span><span class="sxs-lookup"><span data-stu-id="13996-940">A keyword from Keyword_[province_name]_drivers_license_name is found.</span></span>
- <span data-ttu-id="13996-941">Viene trovata una parola chiave da Keyword_canada_drivers_license.</span><span class="sxs-lookup"><span data-stu-id="13996-941">A keyword from Keyword_canada_drivers_license is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="13996-942">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="13996-942">Keywords</span></span>

#### <a name="keywordprovincenamedriverslicensename"></a><span data-ttu-id="13996-943">Keyword_ [province_name] _drivers_license_name</span><span class="sxs-lookup"><span data-stu-id="13996-943">Keyword_[province_name]_drivers_license_name</span></span>

- <span data-ttu-id="13996-944">L'abbreviazione della provincia, ad esempio, AB</span><span class="sxs-lookup"><span data-stu-id="13996-944">The province abbreviation, for example AB</span></span>
- <span data-ttu-id="13996-945">Il nome della provincia, ad esempio, Alberta</span><span class="sxs-lookup"><span data-stu-id="13996-945">The province name, for example Alberta</span></span>

#### <a name="keywordcanadadriverslicense"></a><span data-ttu-id="13996-946">Keyword_canada_drivers_license</span><span class="sxs-lookup"><span data-stu-id="13996-946">Keyword_canada_drivers_license</span></span>

- <span data-ttu-id="13996-947">DL</span><span class="sxs-lookup"><span data-stu-id="13996-947">DL</span></span>
- <span data-ttu-id="13996-948">DLS</span><span class="sxs-lookup"><span data-stu-id="13996-948">DLS</span></span>
- <span data-ttu-id="13996-949">CDL</span><span class="sxs-lookup"><span data-stu-id="13996-949">CDL</span></span>
- <span data-ttu-id="13996-950">CDLS</span><span class="sxs-lookup"><span data-stu-id="13996-950">CDLS</span></span>
- <span data-ttu-id="13996-951">DriverLic</span><span class="sxs-lookup"><span data-stu-id="13996-951">DriverLic</span></span>
- <span data-ttu-id="13996-952">DriverLics</span><span class="sxs-lookup"><span data-stu-id="13996-952">DriverLics</span></span>
- <span data-ttu-id="13996-953">DriverLicense</span><span class="sxs-lookup"><span data-stu-id="13996-953">DriverLicense</span></span>
- <span data-ttu-id="13996-954">DriverLicenses</span><span class="sxs-lookup"><span data-stu-id="13996-954">DriverLicenses</span></span>
- <span data-ttu-id="13996-955">DriverLicence</span><span class="sxs-lookup"><span data-stu-id="13996-955">DriverLicence</span></span>
- <span data-ttu-id="13996-956">DriverLicences</span><span class="sxs-lookup"><span data-stu-id="13996-956">DriverLicences</span></span>
- <span data-ttu-id="13996-957">Driver Lic</span><span class="sxs-lookup"><span data-stu-id="13996-957">Driver Lic</span></span>
- <span data-ttu-id="13996-958">Driver Lics</span><span class="sxs-lookup"><span data-stu-id="13996-958">Driver Lics</span></span>
- <span data-ttu-id="13996-959">Driver License</span><span class="sxs-lookup"><span data-stu-id="13996-959">Driver License</span></span>
- <span data-ttu-id="13996-960">Driver Licenses</span><span class="sxs-lookup"><span data-stu-id="13996-960">Driver Licenses</span></span>
- <span data-ttu-id="13996-961">Driver Licence</span><span class="sxs-lookup"><span data-stu-id="13996-961">Driver Licence</span></span>
- <span data-ttu-id="13996-962">Driver Licences</span><span class="sxs-lookup"><span data-stu-id="13996-962">Driver Licences</span></span>
- <span data-ttu-id="13996-963">DriversLic</span><span class="sxs-lookup"><span data-stu-id="13996-963">DriversLic</span></span>
- <span data-ttu-id="13996-964">DriversLics</span><span class="sxs-lookup"><span data-stu-id="13996-964">DriversLics</span></span>
- <span data-ttu-id="13996-965">DriversLicence</span><span class="sxs-lookup"><span data-stu-id="13996-965">DriversLicence</span></span>
- <span data-ttu-id="13996-966">DriversLicences</span><span class="sxs-lookup"><span data-stu-id="13996-966">DriversLicences</span></span>
- <span data-ttu-id="13996-967">DriversLicense</span><span class="sxs-lookup"><span data-stu-id="13996-967">DriversLicense</span></span>
- <span data-ttu-id="13996-968">DriversLicenses</span><span class="sxs-lookup"><span data-stu-id="13996-968">DriversLicenses</span></span>
- <span data-ttu-id="13996-969">Drivers Lic</span><span class="sxs-lookup"><span data-stu-id="13996-969">Drivers Lic</span></span>
- <span data-ttu-id="13996-970">Drivers Lics</span><span class="sxs-lookup"><span data-stu-id="13996-970">Drivers Lics</span></span>
- <span data-ttu-id="13996-971">Drivers License</span><span class="sxs-lookup"><span data-stu-id="13996-971">Drivers License</span></span>
- <span data-ttu-id="13996-972">Drivers Licenses</span><span class="sxs-lookup"><span data-stu-id="13996-972">Drivers Licenses</span></span>
- <span data-ttu-id="13996-973">Drivers Licence</span><span class="sxs-lookup"><span data-stu-id="13996-973">Drivers Licence</span></span>
- <span data-ttu-id="13996-974">Drivers Licences</span><span class="sxs-lookup"><span data-stu-id="13996-974">Drivers Licences</span></span>
- <span data-ttu-id="13996-975">Driver'Lic</span><span class="sxs-lookup"><span data-stu-id="13996-975">Driver'Lic</span></span>
- <span data-ttu-id="13996-976">Driver ' LiCS</span><span class="sxs-lookup"><span data-stu-id="13996-976">Driver'Lics</span></span>
- <span data-ttu-id="13996-977">Driver ' License</span><span class="sxs-lookup"><span data-stu-id="13996-977">Driver'License</span></span>
- <span data-ttu-id="13996-978">Driver ' licenses</span><span class="sxs-lookup"><span data-stu-id="13996-978">Driver'Licenses</span></span>
- <span data-ttu-id="13996-979">Driver'Licence</span><span class="sxs-lookup"><span data-stu-id="13996-979">Driver'Licence</span></span>
- <span data-ttu-id="13996-980">Driver'Licences</span><span class="sxs-lookup"><span data-stu-id="13996-980">Driver'Licences</span></span>
- <span data-ttu-id="13996-981">Driver'Lic</span><span class="sxs-lookup"><span data-stu-id="13996-981">Driver' Lic</span></span>
- <span data-ttu-id="13996-982">Driver' Lics</span><span class="sxs-lookup"><span data-stu-id="13996-982">Driver' Lics</span></span>
- <span data-ttu-id="13996-983">Driver' License</span><span class="sxs-lookup"><span data-stu-id="13996-983">Driver' License</span></span>
- <span data-ttu-id="13996-984">Driver' Licenses</span><span class="sxs-lookup"><span data-stu-id="13996-984">Driver' Licenses</span></span>
- <span data-ttu-id="13996-985">Driver' Licence</span><span class="sxs-lookup"><span data-stu-id="13996-985">Driver' Licence</span></span>
- <span data-ttu-id="13996-986">Driver' Licences</span><span class="sxs-lookup"><span data-stu-id="13996-986">Driver' Licences</span></span>
- <span data-ttu-id="13996-987">Driver'sLic</span><span class="sxs-lookup"><span data-stu-id="13996-987">Driver'sLic</span></span>
- <span data-ttu-id="13996-988">Driver'sLics</span><span class="sxs-lookup"><span data-stu-id="13996-988">Driver'sLics</span></span>
- <span data-ttu-id="13996-989">Secondola</span><span class="sxs-lookup"><span data-stu-id="13996-989">Driver'sLicense</span></span>
- <span data-ttu-id="13996-990">Driver'sLicenses</span><span class="sxs-lookup"><span data-stu-id="13996-990">Driver'sLicenses</span></span>
- <span data-ttu-id="13996-991">Driver'sLicence</span><span class="sxs-lookup"><span data-stu-id="13996-991">Driver'sLicence</span></span>
- <span data-ttu-id="13996-992">Driver'sLicences</span><span class="sxs-lookup"><span data-stu-id="13996-992">Driver'sLicences</span></span>
- <span data-ttu-id="13996-993">Driver's Lic</span><span class="sxs-lookup"><span data-stu-id="13996-993">Driver's Lic</span></span>
- <span data-ttu-id="13996-994">Driver's Lics</span><span class="sxs-lookup"><span data-stu-id="13996-994">Driver's Lics</span></span>
- <span data-ttu-id="13996-995">Driver's License</span><span class="sxs-lookup"><span data-stu-id="13996-995">Driver's License</span></span>
- <span data-ttu-id="13996-996">Driver's Licenses</span><span class="sxs-lookup"><span data-stu-id="13996-996">Driver's Licenses</span></span>
- <span data-ttu-id="13996-997">Driver's Licence</span><span class="sxs-lookup"><span data-stu-id="13996-997">Driver's Licence</span></span>
- <span data-ttu-id="13996-998">Driver's Licences</span><span class="sxs-lookup"><span data-stu-id="13996-998">Driver's Licences</span></span>
- <span data-ttu-id="13996-999">Permis de Conduire</span><span class="sxs-lookup"><span data-stu-id="13996-999">Permis de Conduire</span></span>
- <span data-ttu-id="13996-1000">id</span><span class="sxs-lookup"><span data-stu-id="13996-1000">id</span></span>
- <span data-ttu-id="13996-1001">ID</span><span class="sxs-lookup"><span data-stu-id="13996-1001">ids</span></span>
- <span data-ttu-id="13996-1002">idcard number</span><span class="sxs-lookup"><span data-stu-id="13996-1002">idcard number</span></span>
- <span data-ttu-id="13996-1003">idcard numbers</span><span class="sxs-lookup"><span data-stu-id="13996-1003">idcard numbers</span></span>
- <span data-ttu-id="13996-1004">idcard #</span><span class="sxs-lookup"><span data-stu-id="13996-1004">idcard #</span></span>
- <span data-ttu-id="13996-1005">idcard #s</span><span class="sxs-lookup"><span data-stu-id="13996-1005">idcard #s</span></span>
- <span data-ttu-id="13996-1006">idcard card</span><span class="sxs-lookup"><span data-stu-id="13996-1006">idcard card</span></span>
- <span data-ttu-id="13996-1007">idcard cards</span><span class="sxs-lookup"><span data-stu-id="13996-1007">idcard cards</span></span>
- <span data-ttu-id="13996-1008">IDcard</span><span class="sxs-lookup"><span data-stu-id="13996-1008">idcard</span></span>
- <span data-ttu-id="13996-1009">identification number</span><span class="sxs-lookup"><span data-stu-id="13996-1009">identification number</span></span>
- <span data-ttu-id="13996-1010">identification numbers</span><span class="sxs-lookup"><span data-stu-id="13996-1010">identification numbers</span></span>
- <span data-ttu-id="13996-1011">identification #</span><span class="sxs-lookup"><span data-stu-id="13996-1011">identification #</span></span>
- <span data-ttu-id="13996-1012">identification #s</span><span class="sxs-lookup"><span data-stu-id="13996-1012">identification #s</span></span>
- <span data-ttu-id="13996-1013">identification card</span><span class="sxs-lookup"><span data-stu-id="13996-1013">identification card</span></span>
- <span data-ttu-id="13996-1014">identification cards</span><span class="sxs-lookup"><span data-stu-id="13996-1014">identification cards</span></span>
- <span data-ttu-id="13996-1015">identificazione</span><span class="sxs-lookup"><span data-stu-id="13996-1015">identification</span></span> 
- <span data-ttu-id="13996-1016">DL</span><span class="sxs-lookup"><span data-stu-id="13996-1016">DL#</span></span>
- <span data-ttu-id="13996-1017">DLS</span><span class="sxs-lookup"><span data-stu-id="13996-1017">DLS#</span></span> 
- <span data-ttu-id="13996-1018">CDL</span><span class="sxs-lookup"><span data-stu-id="13996-1018">CDL#</span></span> 
- <span data-ttu-id="13996-1019">CDLS</span><span class="sxs-lookup"><span data-stu-id="13996-1019">CDLS#</span></span> 
- <span data-ttu-id="13996-1020">DriverLic #</span><span class="sxs-lookup"><span data-stu-id="13996-1020">DriverLic#</span></span> 
- <span data-ttu-id="13996-1021">DriverLics #</span><span class="sxs-lookup"><span data-stu-id="13996-1021">DriverLics#</span></span> 
- <span data-ttu-id="13996-1022">DriverLicense #</span><span class="sxs-lookup"><span data-stu-id="13996-1022">DriverLicense#</span></span> 
- <span data-ttu-id="13996-1023">DriverLicenses #</span><span class="sxs-lookup"><span data-stu-id="13996-1023">DriverLicenses#</span></span> 
- <span data-ttu-id="13996-1024">DriverLicence #</span><span class="sxs-lookup"><span data-stu-id="13996-1024">DriverLicence#</span></span> 
- <span data-ttu-id="13996-1025">DriverLicences #</span><span class="sxs-lookup"><span data-stu-id="13996-1025">DriverLicences#</span></span> 
- <span data-ttu-id="13996-1026">Driver Lic#</span><span class="sxs-lookup"><span data-stu-id="13996-1026">Driver Lic#</span></span>
- <span data-ttu-id="13996-1027">Driver Lics#</span><span class="sxs-lookup"><span data-stu-id="13996-1027">Driver Lics#</span></span> 
- <span data-ttu-id="13996-1028">Driver License#</span><span class="sxs-lookup"><span data-stu-id="13996-1028">Driver License#</span></span> 
- <span data-ttu-id="13996-1029">Driver Licenses#</span><span class="sxs-lookup"><span data-stu-id="13996-1029">Driver Licenses#</span></span> 
- <span data-ttu-id="13996-1030">Driver License#</span><span class="sxs-lookup"><span data-stu-id="13996-1030">Driver License#</span></span> 
- <span data-ttu-id="13996-1031">Driver Licences#</span><span class="sxs-lookup"><span data-stu-id="13996-1031">Driver Licences#</span></span> 
- <span data-ttu-id="13996-1032">DriversLic #</span><span class="sxs-lookup"><span data-stu-id="13996-1032">DriversLic#</span></span> 
- <span data-ttu-id="13996-1033">DriversLics #</span><span class="sxs-lookup"><span data-stu-id="13996-1033">DriversLics#</span></span> 
- <span data-ttu-id="13996-1034">DriversLicense #</span><span class="sxs-lookup"><span data-stu-id="13996-1034">DriversLicense#</span></span> 
- <span data-ttu-id="13996-1035">DriversLicenses #</span><span class="sxs-lookup"><span data-stu-id="13996-1035">DriversLicenses#</span></span> 
- <span data-ttu-id="13996-1036">DriversLicence #</span><span class="sxs-lookup"><span data-stu-id="13996-1036">DriversLicence#</span></span> 
- <span data-ttu-id="13996-1037">DriversLicences #</span><span class="sxs-lookup"><span data-stu-id="13996-1037">DriversLicences#</span></span> 
- <span data-ttu-id="13996-1038">Drivers Lic#</span><span class="sxs-lookup"><span data-stu-id="13996-1038">Drivers Lic#</span></span> 
- <span data-ttu-id="13996-1039">Drivers Lics#</span><span class="sxs-lookup"><span data-stu-id="13996-1039">Drivers Lics#</span></span> 
- <span data-ttu-id="13996-1040">Drivers License#</span><span class="sxs-lookup"><span data-stu-id="13996-1040">Drivers License#</span></span> 
- <span data-ttu-id="13996-1041">Drivers Licenses#</span><span class="sxs-lookup"><span data-stu-id="13996-1041">Drivers Licenses#</span></span> 
- <span data-ttu-id="13996-1042">Drivers Licence#</span><span class="sxs-lookup"><span data-stu-id="13996-1042">Drivers Licence#</span></span> 
- <span data-ttu-id="13996-1043">Drivers Licences#</span><span class="sxs-lookup"><span data-stu-id="13996-1043">Drivers Licences#</span></span> 
- <span data-ttu-id="13996-1044">Driver'Lic #</span><span class="sxs-lookup"><span data-stu-id="13996-1044">Driver'Lic#</span></span> 
- <span data-ttu-id="13996-1045">Driver ' LiCS</span><span class="sxs-lookup"><span data-stu-id="13996-1045">Driver'Lics#</span></span> 
- <span data-ttu-id="13996-1046">Driver ' License</span><span class="sxs-lookup"><span data-stu-id="13996-1046">Driver'License#</span></span> 
- <span data-ttu-id="13996-1047">Driver ' licenses</span><span class="sxs-lookup"><span data-stu-id="13996-1047">Driver'Licenses#</span></span> 
- <span data-ttu-id="13996-1048">Driver'Licence #</span><span class="sxs-lookup"><span data-stu-id="13996-1048">Driver'Licence#</span></span> 
- <span data-ttu-id="13996-1049">Driver'Licences #</span><span class="sxs-lookup"><span data-stu-id="13996-1049">Driver'Licences#</span></span> 
- <span data-ttu-id="13996-1050">Driver' Lic#</span><span class="sxs-lookup"><span data-stu-id="13996-1050">Driver' Lic#</span></span> 
- <span data-ttu-id="13996-1051">Driver' Lics#</span><span class="sxs-lookup"><span data-stu-id="13996-1051">Driver' Lics#</span></span> 
- <span data-ttu-id="13996-1052">Driver' License#</span><span class="sxs-lookup"><span data-stu-id="13996-1052">Driver' License#</span></span> 
- <span data-ttu-id="13996-1053">Driver' Licenses#</span><span class="sxs-lookup"><span data-stu-id="13996-1053">Driver' Licenses#</span></span> 
- <span data-ttu-id="13996-1054">Driver' Licence#</span><span class="sxs-lookup"><span data-stu-id="13996-1054">Driver' Licence#</span></span> 
- <span data-ttu-id="13996-1055">Driver' Licences#</span><span class="sxs-lookup"><span data-stu-id="13996-1055">Driver' Licences#</span></span> 
- <span data-ttu-id="13996-1056">Driver'sLic #</span><span class="sxs-lookup"><span data-stu-id="13996-1056">Driver'sLic#</span></span> 
- <span data-ttu-id="13996-1057">Driver'sLics #</span><span class="sxs-lookup"><span data-stu-id="13996-1057">Driver'sLics#</span></span> 
- <span data-ttu-id="13996-1058">Secondola</span><span class="sxs-lookup"><span data-stu-id="13996-1058">Driver'sLicense#</span></span> 
- <span data-ttu-id="13996-1059">Driver'sLicenses #</span><span class="sxs-lookup"><span data-stu-id="13996-1059">Driver'sLicenses#</span></span> 
- <span data-ttu-id="13996-1060">Driver'sLicence #</span><span class="sxs-lookup"><span data-stu-id="13996-1060">Driver'sLicence#</span></span> 
- <span data-ttu-id="13996-1061">Driver'sLicences #</span><span class="sxs-lookup"><span data-stu-id="13996-1061">Driver'sLicences#</span></span> 
- <span data-ttu-id="13996-1062">Driver's Lic#</span><span class="sxs-lookup"><span data-stu-id="13996-1062">Driver's Lic#</span></span> 
- <span data-ttu-id="13996-1063">Driver's Lics#</span><span class="sxs-lookup"><span data-stu-id="13996-1063">Driver's Lics#</span></span> 
- <span data-ttu-id="13996-1064">Driver's License#</span><span class="sxs-lookup"><span data-stu-id="13996-1064">Driver's License#</span></span> 
- <span data-ttu-id="13996-1065">Driver's Licenses#</span><span class="sxs-lookup"><span data-stu-id="13996-1065">Driver's Licenses#</span></span> 
- <span data-ttu-id="13996-1066">Driver's Licence#</span><span class="sxs-lookup"><span data-stu-id="13996-1066">Driver's Licence#</span></span> 
- <span data-ttu-id="13996-1067">Driver's Licences#</span><span class="sxs-lookup"><span data-stu-id="13996-1067">Driver's Licences#</span></span> 
- <span data-ttu-id="13996-1068">Permis de Conduire#</span><span class="sxs-lookup"><span data-stu-id="13996-1068">Permis de Conduire#</span></span> 
- <span data-ttu-id="13996-1069">ID</span><span class="sxs-lookup"><span data-stu-id="13996-1069">id#</span></span> 
- <span data-ttu-id="13996-1070">ID</span><span class="sxs-lookup"><span data-stu-id="13996-1070">ids#</span></span> 
- <span data-ttu-id="13996-1071">idcard card#</span><span class="sxs-lookup"><span data-stu-id="13996-1071">idcard card#</span></span> 
- <span data-ttu-id="13996-1072">idcard cards#</span><span class="sxs-lookup"><span data-stu-id="13996-1072">idcard cards#</span></span> 
- <span data-ttu-id="13996-1073">IDcard #</span><span class="sxs-lookup"><span data-stu-id="13996-1073">idcard#</span></span> 
- <span data-ttu-id="13996-1074">identification card#</span><span class="sxs-lookup"><span data-stu-id="13996-1074">identification card#</span></span> 
- <span data-ttu-id="13996-1075">identification cards#</span><span class="sxs-lookup"><span data-stu-id="13996-1075">identification cards#</span></span> 
- <span data-ttu-id="13996-1076">identificazione</span><span class="sxs-lookup"><span data-stu-id="13996-1076">identification#</span></span> 
   
## <a name="canada-health-service-number"></a><span data-ttu-id="13996-1077">Canada - Codice del servizio sanitario</span><span class="sxs-lookup"><span data-stu-id="13996-1077">Canada Health Service Number</span></span>

### <a name="format"></a><span data-ttu-id="13996-1078">Formato</span><span class="sxs-lookup"><span data-stu-id="13996-1078">Format</span></span>

<span data-ttu-id="13996-1079">10 cifre</span><span class="sxs-lookup"><span data-stu-id="13996-1079">10 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="13996-1080">Modello</span><span class="sxs-lookup"><span data-stu-id="13996-1080">Pattern</span></span>

<span data-ttu-id="13996-1081">10 cifre</span><span class="sxs-lookup"><span data-stu-id="13996-1081">10 digits</span></span>

### <a name="checksum"></a><span data-ttu-id="13996-1082">Checksum</span><span class="sxs-lookup"><span data-stu-id="13996-1082">Checksum</span></span>

<span data-ttu-id="13996-1083">No</span><span class="sxs-lookup"><span data-stu-id="13996-1083">No</span></span>

### <a name="definition"></a><span data-ttu-id="13996-1084">Definizione</span><span class="sxs-lookup"><span data-stu-id="13996-1084">Definition</span></span>

<span data-ttu-id="13996-1085">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="13996-1085">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="13996-1086">L'espressione regolare Regex_canada_health_service_number restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="13996-1086">The regular expression Regex_canada_health_service_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="13996-1087">Viene trovata una parola chiave da Keyword_canada_health_service_number.</span><span class="sxs-lookup"><span data-stu-id="13996-1087">A keyword from Keyword_canada_health_service_number is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="13996-1088">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="13996-1088">Keywords</span></span>

#### <a name="keywordcanadahealthservicenumber"></a><span data-ttu-id="13996-1089">Keyword_canada_health_service_number</span><span class="sxs-lookup"><span data-stu-id="13996-1089">Keyword_canada_health_service_number</span></span>

- <span data-ttu-id="13996-1090">personal health number</span><span class="sxs-lookup"><span data-stu-id="13996-1090">personal health number</span></span>
- <span data-ttu-id="13996-1091">patient information</span><span class="sxs-lookup"><span data-stu-id="13996-1091">patient information</span></span>
- <span data-ttu-id="13996-1092">health services</span><span class="sxs-lookup"><span data-stu-id="13996-1092">health services</span></span>
- <span data-ttu-id="13996-1093">speciality services</span><span class="sxs-lookup"><span data-stu-id="13996-1093">speciality services</span></span>
- <span data-ttu-id="13996-1094">automobile accident</span><span class="sxs-lookup"><span data-stu-id="13996-1094">automobile accident</span></span>
- <span data-ttu-id="13996-1095">patient hospital</span><span class="sxs-lookup"><span data-stu-id="13996-1095">patient hospital</span></span>
- <span data-ttu-id="13996-1096">psichiatra</span><span class="sxs-lookup"><span data-stu-id="13996-1096">psychiatrist</span></span>
- <span data-ttu-id="13996-1097">workers compensation</span><span class="sxs-lookup"><span data-stu-id="13996-1097">workers compensation</span></span>
- <span data-ttu-id="13996-1098">Disability</span><span class="sxs-lookup"><span data-stu-id="13996-1098">disability</span></span>
      
## <a name="canada-passport-number"></a><span data-ttu-id="13996-1099">Canada - Numero di passaporto</span><span class="sxs-lookup"><span data-stu-id="13996-1099">Canada Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="13996-1100">Formato</span><span class="sxs-lookup"><span data-stu-id="13996-1100">Format</span></span>

<span data-ttu-id="13996-1101">Due lettere maiuscole seguite da 6 cifre</span><span class="sxs-lookup"><span data-stu-id="13996-1101">Two uppercase letters followed by six digits</span></span>

### <a name="pattern"></a><span data-ttu-id="13996-1102">Modello</span><span class="sxs-lookup"><span data-stu-id="13996-1102">Pattern</span></span>

<span data-ttu-id="13996-1103">Due lettere maiuscole seguite da 6 cifre</span><span class="sxs-lookup"><span data-stu-id="13996-1103">Two uppercase letters followed by six digits</span></span>

### <a name="checksum"></a><span data-ttu-id="13996-1104">Checksum</span><span class="sxs-lookup"><span data-stu-id="13996-1104">Checksum</span></span>

<span data-ttu-id="13996-1105">No</span><span class="sxs-lookup"><span data-stu-id="13996-1105">No</span></span>

### <a name="definition"></a><span data-ttu-id="13996-1106">Definizione</span><span class="sxs-lookup"><span data-stu-id="13996-1106">Definition</span></span>

<span data-ttu-id="13996-1107">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="13996-1107">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="13996-1108">L'espressione regolare Regex_canada_passport_number restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="13996-1108">The regular expression Regex_canada_passport_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="13996-1109">Viene trovata una parola chiave da Keyword_canada_passport_number o Keyword_passport.</span><span class="sxs-lookup"><span data-stu-id="13996-1109">A keyword from Keyword_canada_passport_number or Keyword_passport is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="13996-1110">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="13996-1110">Keywords</span></span>

#### <a name="keywordcanadapassportnumber"></a><span data-ttu-id="13996-1111">Keyword_canada_passport_number</span><span class="sxs-lookup"><span data-stu-id="13996-1111">Keyword_canada_passport_number</span></span>

- <span data-ttu-id="13996-1112">canadian citizenship</span><span class="sxs-lookup"><span data-stu-id="13996-1112">canadian citizenship</span></span>
- <span data-ttu-id="13996-1113">canadian passport</span><span class="sxs-lookup"><span data-stu-id="13996-1113">canadian passport</span></span>
- <span data-ttu-id="13996-1114">passport application</span><span class="sxs-lookup"><span data-stu-id="13996-1114">passport application</span></span>
- <span data-ttu-id="13996-1115">passport photos</span><span class="sxs-lookup"><span data-stu-id="13996-1115">passport photos</span></span>
- <span data-ttu-id="13996-1116">certified translator</span><span class="sxs-lookup"><span data-stu-id="13996-1116">certified translator</span></span>
- <span data-ttu-id="13996-1117">canadian citizens</span><span class="sxs-lookup"><span data-stu-id="13996-1117">canadian citizens</span></span>
- <span data-ttu-id="13996-1118">processing times</span><span class="sxs-lookup"><span data-stu-id="13996-1118">processing times</span></span>
- <span data-ttu-id="13996-1119">renewal application</span><span class="sxs-lookup"><span data-stu-id="13996-1119">renewal application</span></span>

#### <a name="keywordpassport"></a><span data-ttu-id="13996-1120">Keyword_passport</span><span class="sxs-lookup"><span data-stu-id="13996-1120">Keyword_passport</span></span>

- <span data-ttu-id="13996-1121">Passport Number</span><span class="sxs-lookup"><span data-stu-id="13996-1121">Passport Number</span></span>
- <span data-ttu-id="13996-1122">Passport No</span><span class="sxs-lookup"><span data-stu-id="13996-1122">Passport No</span></span>
- <span data-ttu-id="13996-1123">Passport#</span><span class="sxs-lookup"><span data-stu-id="13996-1123">Passport #</span></span>
- <span data-ttu-id="13996-1124">Passaporto</span><span class="sxs-lookup"><span data-stu-id="13996-1124">Passport#</span></span>
- <span data-ttu-id="13996-1125">PassportID</span><span class="sxs-lookup"><span data-stu-id="13996-1125">PassportID</span></span>
- <span data-ttu-id="13996-1126">Passportno</span><span class="sxs-lookup"><span data-stu-id="13996-1126">Passportno</span></span>
- <span data-ttu-id="13996-1127">passportnumber</span><span class="sxs-lookup"><span data-stu-id="13996-1127">passportnumber</span></span>
- <span data-ttu-id="13996-1128">パスポート</span><span class="sxs-lookup"><span data-stu-id="13996-1128">パスポート</span></span>
- <span data-ttu-id="13996-1129">パスポート番号</span><span class="sxs-lookup"><span data-stu-id="13996-1129">パスポート番号</span></span>
- <span data-ttu-id="13996-1130">パスポートのNum</span><span class="sxs-lookup"><span data-stu-id="13996-1130">パスポートのNum</span></span>
- <span data-ttu-id="13996-1131">パスポート #</span><span class="sxs-lookup"><span data-stu-id="13996-1131">パスポート＃</span></span>
- <span data-ttu-id="13996-1132">Numéro de passeport</span><span class="sxs-lookup"><span data-stu-id="13996-1132">Numéro de passeport</span></span>
- <span data-ttu-id="13996-1133">Passeport n °</span><span class="sxs-lookup"><span data-stu-id="13996-1133">Passeport n °</span></span>
- <span data-ttu-id="13996-1134">Passeport Non</span><span class="sxs-lookup"><span data-stu-id="13996-1134">Passeport Non</span></span>
- <span data-ttu-id="13996-1135">Passeport#</span><span class="sxs-lookup"><span data-stu-id="13996-1135">Passeport #</span></span>
- <span data-ttu-id="13996-1136">Passeport</span><span class="sxs-lookup"><span data-stu-id="13996-1136">Passeport#</span></span>
- <span data-ttu-id="13996-1137">PasseportNon</span><span class="sxs-lookup"><span data-stu-id="13996-1137">PasseportNon</span></span>
- <span data-ttu-id="13996-1138">Passeportn °</span><span class="sxs-lookup"><span data-stu-id="13996-1138">Passeportn °</span></span>
   
## <a name="canada-personal-health-identification-number-phin"></a><span data-ttu-id="13996-1139">Canada - Numero di identificazione sanitaria personale (PHIN)</span><span class="sxs-lookup"><span data-stu-id="13996-1139">Canada Personal Health Identification Number (PHIN)</span></span>

### <a name="format"></a><span data-ttu-id="13996-1140">Formato</span><span class="sxs-lookup"><span data-stu-id="13996-1140">Format</span></span>

<span data-ttu-id="13996-1141">9 cifre</span><span class="sxs-lookup"><span data-stu-id="13996-1141">Nine digits</span></span>

### <a name="pattern"></a><span data-ttu-id="13996-1142">Modello</span><span class="sxs-lookup"><span data-stu-id="13996-1142">Pattern</span></span>

<span data-ttu-id="13996-1143">9 cifre</span><span class="sxs-lookup"><span data-stu-id="13996-1143">Nine digits</span></span>

### <a name="checksum"></a><span data-ttu-id="13996-1144">Checksum</span><span class="sxs-lookup"><span data-stu-id="13996-1144">Checksum</span></span>

<span data-ttu-id="13996-1145">No</span><span class="sxs-lookup"><span data-stu-id="13996-1145">No</span></span>

### <a name="definition"></a><span data-ttu-id="13996-1146">Definizione</span><span class="sxs-lookup"><span data-stu-id="13996-1146">Definition</span></span>

<span data-ttu-id="13996-1147">Un criterio DLP è 75% fiducioso di aver rilevato questo tipo di informazioni riservate se, entro 300 caratteri: l'espressione regolare Regex_canada_phin trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="13996-1147">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The regular expression Regex_canada_phin finds content that matches the pattern.</span></span>
<span data-ttu-id="13996-1148">Sono state trovate almeno due parole chiave di Keyword_canada_phin o Keyword_canada_provinces..</span><span class="sxs-lookup"><span data-stu-id="13996-1148">At least two keywords from Keyword_canada_phin or Keyword_canada_provinces are found..</span></span>

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

### <a name="keywords"></a><span data-ttu-id="13996-1149">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="13996-1149">Keywords</span></span>

#### <a name="keywordcanadaphin"></a><span data-ttu-id="13996-1150">Keyword_canada_phin</span><span class="sxs-lookup"><span data-stu-id="13996-1150">Keyword_canada_phin</span></span>

- <span data-ttu-id="13996-1151">social insurance number</span><span class="sxs-lookup"><span data-stu-id="13996-1151">social insurance number</span></span>
- <span data-ttu-id="13996-1152">health information act</span><span class="sxs-lookup"><span data-stu-id="13996-1152">health information act</span></span>
- <span data-ttu-id="13996-1153">income tax information</span><span class="sxs-lookup"><span data-stu-id="13996-1153">income tax information</span></span>
- <span data-ttu-id="13996-1154">manitoba health</span><span class="sxs-lookup"><span data-stu-id="13996-1154">manitoba health</span></span>
- <span data-ttu-id="13996-1155">health registration</span><span class="sxs-lookup"><span data-stu-id="13996-1155">health registration</span></span>
- <span data-ttu-id="13996-1156">prescription purchases</span><span class="sxs-lookup"><span data-stu-id="13996-1156">prescription purchases</span></span>
- <span data-ttu-id="13996-1157">benefit eligibility</span><span class="sxs-lookup"><span data-stu-id="13996-1157">benefit eligibility</span></span>
- <span data-ttu-id="13996-1158">personal health</span><span class="sxs-lookup"><span data-stu-id="13996-1158">personal health</span></span>
- <span data-ttu-id="13996-1159">power of attorney</span><span class="sxs-lookup"><span data-stu-id="13996-1159">power of attorney</span></span>
- <span data-ttu-id="13996-1160">registration number</span><span class="sxs-lookup"><span data-stu-id="13996-1160">registration number</span></span>
- <span data-ttu-id="13996-1161">personal health number</span><span class="sxs-lookup"><span data-stu-id="13996-1161">personal health number</span></span>
- <span data-ttu-id="13996-1162">practitioner referral</span><span class="sxs-lookup"><span data-stu-id="13996-1162">practitioner referral</span></span>
- <span data-ttu-id="13996-1163">wellness professional</span><span class="sxs-lookup"><span data-stu-id="13996-1163">wellness professional</span></span>
- <span data-ttu-id="13996-1164">patient referral</span><span class="sxs-lookup"><span data-stu-id="13996-1164">patient referral</span></span>
- <span data-ttu-id="13996-1165">health and wellness</span><span class="sxs-lookup"><span data-stu-id="13996-1165">health and wellness</span></span>

#### <a name="keywordcanadaprovinces"></a><span data-ttu-id="13996-1166">Keyword_canada_provinces</span><span class="sxs-lookup"><span data-stu-id="13996-1166">Keyword_canada_provinces</span></span>

- <span data-ttu-id="13996-1167">Nunavut</span><span class="sxs-lookup"><span data-stu-id="13996-1167">Nunavut</span></span>
- <span data-ttu-id="13996-1168">Quebec</span><span class="sxs-lookup"><span data-stu-id="13996-1168">Quebec</span></span>
- <span data-ttu-id="13996-1169">Northwest Territories</span><span class="sxs-lookup"><span data-stu-id="13996-1169">Northwest Territories</span></span>
- <span data-ttu-id="13996-1170">Ontario</span><span class="sxs-lookup"><span data-stu-id="13996-1170">Ontario</span></span>
- <span data-ttu-id="13996-1171">British Columbia</span><span class="sxs-lookup"><span data-stu-id="13996-1171">British Columbia</span></span>
- <span data-ttu-id="13996-1172">Filippa</span><span class="sxs-lookup"><span data-stu-id="13996-1172">Alberta</span></span>
- <span data-ttu-id="13996-1173">Saskatchewan</span><span class="sxs-lookup"><span data-stu-id="13996-1173">Saskatchewan</span></span>
- <span data-ttu-id="13996-1174">Manitoba</span><span class="sxs-lookup"><span data-stu-id="13996-1174">Manitoba</span></span>
- <span data-ttu-id="13996-1175">Yukon</span><span class="sxs-lookup"><span data-stu-id="13996-1175">Yukon</span></span>
- <span data-ttu-id="13996-1176">Newfoundland and Labrador</span><span class="sxs-lookup"><span data-stu-id="13996-1176">Newfoundland and Labrador</span></span>
- <span data-ttu-id="13996-1177">New Brunswick</span><span class="sxs-lookup"><span data-stu-id="13996-1177">New Brunswick</span></span>
- <span data-ttu-id="13996-1178">Nova Scotia</span><span class="sxs-lookup"><span data-stu-id="13996-1178">Nova Scotia</span></span>
- <span data-ttu-id="13996-1179">Prince Edward Island</span><span class="sxs-lookup"><span data-stu-id="13996-1179">Prince Edward Island</span></span>
- <span data-ttu-id="13996-1180">Canada</span><span class="sxs-lookup"><span data-stu-id="13996-1180">Canada</span></span>
   
## <a name="canada-social-insurance-number"></a><span data-ttu-id="13996-1181">Canada - Numero di assicurazione sociale</span><span class="sxs-lookup"><span data-stu-id="13996-1181">Canada Social Insurance Number</span></span>

### <a name="format"></a><span data-ttu-id="13996-1182">Formato</span><span class="sxs-lookup"><span data-stu-id="13996-1182">Format</span></span>

<span data-ttu-id="13996-1183">9 cifre con spazi o lineette facoltativi</span><span class="sxs-lookup"><span data-stu-id="13996-1183">Nine digits with optional hyphens or spaces</span></span>

### <a name="pattern"></a><span data-ttu-id="13996-1184">Modello</span><span class="sxs-lookup"><span data-stu-id="13996-1184">Pattern</span></span>

<span data-ttu-id="13996-1185">Formattato</span><span class="sxs-lookup"><span data-stu-id="13996-1185">Formatted:</span></span>
- <span data-ttu-id="13996-1186">Tre cifre</span><span class="sxs-lookup"><span data-stu-id="13996-1186">Three digits</span></span> 
- <span data-ttu-id="13996-1187">Una lineetta o uno spazio</span><span class="sxs-lookup"><span data-stu-id="13996-1187">A hyphen or space</span></span> 
- <span data-ttu-id="13996-1188">Tre cifre</span><span class="sxs-lookup"><span data-stu-id="13996-1188">Three digits</span></span> 
- <span data-ttu-id="13996-1189">Una lineetta o uno spazio</span><span class="sxs-lookup"><span data-stu-id="13996-1189">A hyphen or space</span></span> 
- <span data-ttu-id="13996-1190">Tre cifre</span><span class="sxs-lookup"><span data-stu-id="13996-1190">Three digits</span></span>

<span data-ttu-id="13996-1191">Non formattato: nove cifre</span><span class="sxs-lookup"><span data-stu-id="13996-1191">Unformatted: Nine digits</span></span>

### <a name="checksum"></a><span data-ttu-id="13996-1192">Checksum</span><span class="sxs-lookup"><span data-stu-id="13996-1192">Checksum</span></span>

<span data-ttu-id="13996-1193">Sì</span><span class="sxs-lookup"><span data-stu-id="13996-1193">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="13996-1194">Definizione</span><span class="sxs-lookup"><span data-stu-id="13996-1194">Definition</span></span>

<span data-ttu-id="13996-1195">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="13996-1195">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="13996-1196">La funzione Func_canadian_sin restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="13996-1196">The function Func_canadian_sin finds content that matches the pattern.</span></span>
- <span data-ttu-id="13996-1197">Almeno due delle seguenti combinazioni:</span><span class="sxs-lookup"><span data-stu-id="13996-1197">At least two of any combination of the following:</span></span>
    - <span data-ttu-id="13996-1198">Viene trovata una parola chiave da Keyword_sin.</span><span class="sxs-lookup"><span data-stu-id="13996-1198">A keyword from Keyword_sin is found.</span></span>
    - <span data-ttu-id="13996-1199">Viene trovata una parola chiave da Keyword_sin_collaborative.</span><span class="sxs-lookup"><span data-stu-id="13996-1199">A keyword from Keyword_sin_collaborative is found.</span></span>
    - <span data-ttu-id="13996-1200">La funzione Func_eu_date rileva una data nel formato corretto.</span><span class="sxs-lookup"><span data-stu-id="13996-1200">The function Func_eu_date finds a date in the right date format.</span></span>
- <span data-ttu-id="13996-1201">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="13996-1201">The checksum passes.</span></span>

<span data-ttu-id="13996-1202">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="13996-1202">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="13996-1203">La funzione Func_unformatted_canadian_sin restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="13996-1203">The function Func_unformatted_canadian_sin finds content that matches the pattern.</span></span>
- <span data-ttu-id="13996-1204">Viene trovata una parola chiave da Keyword_sin.</span><span class="sxs-lookup"><span data-stu-id="13996-1204">A keyword from Keyword_sin is found.</span></span>
- <span data-ttu-id="13996-1205">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="13996-1205">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="13996-1206">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="13996-1206">Keywords</span></span>

#### <a name="keywordsin"></a><span data-ttu-id="13996-1207">Keyword_sin</span><span class="sxs-lookup"><span data-stu-id="13996-1207">Keyword_sin</span></span>

- <span data-ttu-id="13996-1208">sin</span><span class="sxs-lookup"><span data-stu-id="13996-1208">sin</span></span> 
- <span data-ttu-id="13996-1209">social insurance</span><span class="sxs-lookup"><span data-stu-id="13996-1209">social insurance</span></span> 
- <span data-ttu-id="13996-1210">numero d'assurance sociale</span><span class="sxs-lookup"><span data-stu-id="13996-1210">numero d'assurance sociale</span></span> 
- <span data-ttu-id="13996-1211">peccati</span><span class="sxs-lookup"><span data-stu-id="13996-1211">sins</span></span> 
- <span data-ttu-id="13996-1212">SSN</span><span class="sxs-lookup"><span data-stu-id="13996-1212">ssn</span></span> 
- <span data-ttu-id="13996-1213">SNSS</span><span class="sxs-lookup"><span data-stu-id="13996-1213">ssns</span></span> 
- <span data-ttu-id="13996-1214">social security</span><span class="sxs-lookup"><span data-stu-id="13996-1214">social security</span></span> 
- <span data-ttu-id="13996-1215">numero d'assurance social</span><span class="sxs-lookup"><span data-stu-id="13996-1215">numero d'assurance social</span></span> 
- <span data-ttu-id="13996-1216">national identification number</span><span class="sxs-lookup"><span data-stu-id="13996-1216">national identification number</span></span> 
- <span data-ttu-id="13996-1217">national id</span><span class="sxs-lookup"><span data-stu-id="13996-1217">national id</span></span> 
- <span data-ttu-id="13996-1218">sin</span><span class="sxs-lookup"><span data-stu-id="13996-1218">sin#</span></span> 
- <span data-ttu-id="13996-1219">soc ins</span><span class="sxs-lookup"><span data-stu-id="13996-1219">soc ins</span></span> 
- <span data-ttu-id="13996-1220">social ins</span><span class="sxs-lookup"><span data-stu-id="13996-1220">social ins</span></span> 

#### <a name="keywordsincollaborative"></a><span data-ttu-id="13996-1221">Keyword_sin_collaborative</span><span class="sxs-lookup"><span data-stu-id="13996-1221">Keyword_sin_collaborative</span></span>

- <span data-ttu-id="13996-1222">driver's license</span><span class="sxs-lookup"><span data-stu-id="13996-1222">driver's license</span></span> 
- <span data-ttu-id="13996-1223">drivers license</span><span class="sxs-lookup"><span data-stu-id="13996-1223">drivers license</span></span> 
- <span data-ttu-id="13996-1224">driver's licence</span><span class="sxs-lookup"><span data-stu-id="13996-1224">driver's licence</span></span> 
- <span data-ttu-id="13996-1225">drivers licence</span><span class="sxs-lookup"><span data-stu-id="13996-1225">drivers licence</span></span> 
- <span data-ttu-id="13996-1226">DOB</span><span class="sxs-lookup"><span data-stu-id="13996-1226">DOB</span></span> 
- <span data-ttu-id="13996-1227">Data di nascita</span><span class="sxs-lookup"><span data-stu-id="13996-1227">Birthdate</span></span> 
- <span data-ttu-id="13996-1228">Compleanno</span><span class="sxs-lookup"><span data-stu-id="13996-1228">Birthday</span></span> 
- <span data-ttu-id="13996-1229">Date of Birth</span><span class="sxs-lookup"><span data-stu-id="13996-1229">Date of Birth</span></span> 
   
## <a name="chile-identity-card-number"></a><span data-ttu-id="13996-1230">	Cile - Numero di carta di identità</span><span class="sxs-lookup"><span data-stu-id="13996-1230">Chile Identity Card Number</span></span>

### <a name="format"></a><span data-ttu-id="13996-1231">Formato</span><span class="sxs-lookup"><span data-stu-id="13996-1231">Format</span></span>

<span data-ttu-id="13996-1232">7-8 cifre più delimitatori una cifra di controllo o una lettera</span><span class="sxs-lookup"><span data-stu-id="13996-1232">7-8 digits plus delimiters a check digit or letter</span></span>

### <a name="pattern"></a><span data-ttu-id="13996-1233">Modello</span><span class="sxs-lookup"><span data-stu-id="13996-1233">Pattern</span></span>

<span data-ttu-id="13996-1234">7-8 cifre più delimitatori:</span><span class="sxs-lookup"><span data-stu-id="13996-1234">7-8 digits plus delimiters:</span></span>
- <span data-ttu-id="13996-1235">1-2 cifre</span><span class="sxs-lookup"><span data-stu-id="13996-1235">1-2 digits</span></span> 
- <span data-ttu-id="13996-1236">Un punto </span><span class="sxs-lookup"><span data-stu-id="13996-1236">A period</span></span> 
- <span data-ttu-id="13996-1237">Tre cifre</span><span class="sxs-lookup"><span data-stu-id="13996-1237">Three digits</span></span> 
- <span data-ttu-id="13996-1238">Un punto </span><span class="sxs-lookup"><span data-stu-id="13996-1238">A period</span></span> 
- <span data-ttu-id="13996-1239">Tre cifre</span><span class="sxs-lookup"><span data-stu-id="13996-1239">Three digits</span></span> 
- <span data-ttu-id="13996-1240">Un trattino</span><span class="sxs-lookup"><span data-stu-id="13996-1240">A dash</span></span> 
- <span data-ttu-id="13996-1241">Una cifra o una lettera (senza distinzione tra maiuscole e minuscole) che corrisponde a una cifra di controllo</span><span class="sxs-lookup"><span data-stu-id="13996-1241">One digit or letter (not case sensitive) which is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="13996-1242">Checksum</span><span class="sxs-lookup"><span data-stu-id="13996-1242">Checksum</span></span>

<span data-ttu-id="13996-1243">Sì</span><span class="sxs-lookup"><span data-stu-id="13996-1243">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="13996-1244">Definizione</span><span class="sxs-lookup"><span data-stu-id="13996-1244">Definition</span></span>

<span data-ttu-id="13996-1245">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="13996-1245">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="13996-1246">La funzione Func_chile_id_card trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="13996-1246">The function Func_chile_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="13996-1247">Viene trovata una parola chiave da Keyword_chile_id_card.</span><span class="sxs-lookup"><span data-stu-id="13996-1247">A keyword from Keyword_chile_id_card is found.</span></span>
- <span data-ttu-id="13996-1248">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="13996-1248">The checksum passes.</span></span>

<span data-ttu-id="13996-1249">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="13996-1249">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="13996-1250">La funzione Func_chile_id_card trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="13996-1250">The function Func_chile_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="13996-1251">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="13996-1251">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="13996-1252">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="13996-1252">Keywords</span></span>

#### <a name="keywordchileidcard"></a><span data-ttu-id="13996-1253">Keyword_chile_id_card</span><span class="sxs-lookup"><span data-stu-id="13996-1253">Keyword_chile_id_card</span></span>

- <span data-ttu-id="13996-1254">Numero di carta d’identità</span><span class="sxs-lookup"><span data-stu-id="13996-1254">National Identification Number</span></span> 
- <span data-ttu-id="13996-1255">Carta di identità</span><span class="sxs-lookup"><span data-stu-id="13996-1255">Identity card</span></span> 
- <span data-ttu-id="13996-1256">ID</span><span class="sxs-lookup"><span data-stu-id="13996-1256">ID</span></span> 
- <span data-ttu-id="13996-1257">Identificazione</span><span class="sxs-lookup"><span data-stu-id="13996-1257">Identification</span></span> 
- <span data-ttu-id="13996-1258">Rol Único Nacional</span><span class="sxs-lookup"><span data-stu-id="13996-1258">Rol Único Nacional</span></span> 
- <span data-ttu-id="13996-1259">Correre</span><span class="sxs-lookup"><span data-stu-id="13996-1259">RUN</span></span> 
- <span data-ttu-id="13996-1260">Rol Único Tributario</span><span class="sxs-lookup"><span data-stu-id="13996-1260">Rol Único Tributario</span></span> 
- <span data-ttu-id="13996-1261">CARREGGIATA</span><span class="sxs-lookup"><span data-stu-id="13996-1261">RUT</span></span> 
- <span data-ttu-id="13996-1262">Cédula de Identidad</span><span class="sxs-lookup"><span data-stu-id="13996-1262">Cédula de Identidad</span></span> 
- <span data-ttu-id="13996-1263">Número De Identificación Nacional</span><span class="sxs-lookup"><span data-stu-id="13996-1263">Número De Identificación Nacional</span></span> 
- <span data-ttu-id="13996-1264">Tarjeta de identificación</span><span class="sxs-lookup"><span data-stu-id="13996-1264">Tarjeta de identificación</span></span> 
- <span data-ttu-id="13996-1265">Identificación</span><span class="sxs-lookup"><span data-stu-id="13996-1265">Identificación</span></span> 
   
## <a name="china-resident-identity-card-prc-number"></a><span data-ttu-id="13996-1266">	Numero carta di identità per residenti in Cina (RPC)</span><span class="sxs-lookup"><span data-stu-id="13996-1266">China Resident Identity Card (PRC) Number</span></span>

### <a name="format"></a><span data-ttu-id="13996-1267">Formato</span><span class="sxs-lookup"><span data-stu-id="13996-1267">Format</span></span>

<span data-ttu-id="13996-1268">18 cifre</span><span class="sxs-lookup"><span data-stu-id="13996-1268">18 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="13996-1269">Modello</span><span class="sxs-lookup"><span data-stu-id="13996-1269">Pattern</span></span>

<span data-ttu-id="13996-1270">18 cifre:</span><span class="sxs-lookup"><span data-stu-id="13996-1270">18 digits:</span></span>
- <span data-ttu-id="13996-1271">Sei cifre, ovvero un codice indirizzo </span><span class="sxs-lookup"><span data-stu-id="13996-1271">Six digits which are an address code</span></span> 
- <span data-ttu-id="13996-1272">Otto cifre nel formato AAAAMMGG, ovvero la data di nascita </span><span class="sxs-lookup"><span data-stu-id="13996-1272">Eight digits in the form YYYYMMDD which are the date of birth</span></span> 
- <span data-ttu-id="13996-1273">Tre cifre, ovvero un codice di ordine </span><span class="sxs-lookup"><span data-stu-id="13996-1273">Three digits which are an order code</span></span> 
- <span data-ttu-id="13996-1274">Una cifra, ovvero una cifra di controllo</span><span class="sxs-lookup"><span data-stu-id="13996-1274">One digit which is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="13996-1275">Checksum</span><span class="sxs-lookup"><span data-stu-id="13996-1275">Checksum</span></span>

<span data-ttu-id="13996-1276">Sì</span><span class="sxs-lookup"><span data-stu-id="13996-1276">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="13996-1277">Definizione</span><span class="sxs-lookup"><span data-stu-id="13996-1277">Definition</span></span>

<span data-ttu-id="13996-1278">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="13996-1278">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="13996-1279">La funzione Func_china_resident_id trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="13996-1279">The function Func_china_resident_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="13996-1280">Viene trovata una parola chiave da Keyword_china_resident_id.</span><span class="sxs-lookup"><span data-stu-id="13996-1280">A keyword from Keyword_china_resident_id is found.</span></span>
- <span data-ttu-id="13996-1281">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="13996-1281">The checksum passes.</span></span>

<span data-ttu-id="13996-1282">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="13996-1282">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="13996-1283">La funzione Func_china_resident_id trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="13996-1283">The function Func_china_resident_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="13996-1284">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="13996-1284">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="13996-1285">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="13996-1285">Keywords</span></span>

### <a name="keywordchinaresidentid"></a><span data-ttu-id="13996-1286">Keyword_china_resident_id</span><span class="sxs-lookup"><span data-stu-id="13996-1286">Keyword_china_resident_id</span></span>

- <span data-ttu-id="13996-1287">Carta d’identità per residenti</span><span class="sxs-lookup"><span data-stu-id="13996-1287">Resident Identity Card</span></span> 
- <span data-ttu-id="13996-1288">RPC</span><span class="sxs-lookup"><span data-stu-id="13996-1288">PRC</span></span> 
- <span data-ttu-id="13996-1289">Carta d’identità</span><span class="sxs-lookup"><span data-stu-id="13996-1289">National Identification Card</span></span> 
- <span data-ttu-id="13996-1290">身份证</span><span class="sxs-lookup"><span data-stu-id="13996-1290">身份证</span></span> 
- <span data-ttu-id="13996-1291">居民 身份证</span><span class="sxs-lookup"><span data-stu-id="13996-1291">居民 身份证</span></span> 
- <span data-ttu-id="13996-1292">居民身份证</span><span class="sxs-lookup"><span data-stu-id="13996-1292">居民身份证</span></span> 
- <span data-ttu-id="13996-1293">鉴定</span><span class="sxs-lookup"><span data-stu-id="13996-1293">鉴定</span></span> 
- <span data-ttu-id="13996-1294">身分證</span><span class="sxs-lookup"><span data-stu-id="13996-1294">身分證</span></span> 
- <span data-ttu-id="13996-1295">居民 身份證</span><span class="sxs-lookup"><span data-stu-id="13996-1295">居民 身份證</span></span>
- <span data-ttu-id="13996-1296">鑑定</span><span class="sxs-lookup"><span data-stu-id="13996-1296">鑑定</span></span> 
   
## <a name="credit-card-number"></a><span data-ttu-id="13996-1297">Credit Card Number</span><span class="sxs-lookup"><span data-stu-id="13996-1297">Credit Card Number</span></span>

### <a name="format"></a><span data-ttu-id="13996-1298">Formato</span><span class="sxs-lookup"><span data-stu-id="13996-1298">Format</span></span>

<span data-ttu-id="13996-1299">16 cifre che possono essere formattate o non formattate (dddddddddddddddd) e devono superare il test di Luhn.</span><span class="sxs-lookup"><span data-stu-id="13996-1299">16 digits which can be formatted or unformatted (dddddddddddddddd) and must pass the Luhn test.</span></span>

### <a name="pattern"></a><span data-ttu-id="13996-1300">Modello</span><span class="sxs-lookup"><span data-stu-id="13996-1300">Pattern</span></span>

<span data-ttu-id="13996-1301">Modello molto complesso e solido che rileva carte di credito dei maggiori circuiti del mondo, ad esempio, Visa, MasterCard, Discover Card, JCB, American Express, nonché carte regalo e ticket restaurant.</span><span class="sxs-lookup"><span data-stu-id="13996-1301">Very complex and robust pattern that detects cards from all major brands worldwide, including Visa, MasterCard, Discover Card, JCB, American Express, gift cards, and diner cards.</span></span>

### <a name="checksum"></a><span data-ttu-id="13996-1302">Checksum</span><span class="sxs-lookup"><span data-stu-id="13996-1302">Checksum</span></span>

<span data-ttu-id="13996-1303">Yes, il checksum Luhn</span><span class="sxs-lookup"><span data-stu-id="13996-1303">Yes, the Luhn checksum</span></span>

### <a name="definition"></a><span data-ttu-id="13996-1304">Definizione</span><span class="sxs-lookup"><span data-stu-id="13996-1304">Definition</span></span>

<span data-ttu-id="13996-1305">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="13996-1305">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="13996-1306">La funzione Func_credit_card restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="13996-1306">The function Func_credit_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="13996-1307">Si verifica una delle situazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="13996-1307">One of the following is true:</span></span>
    - <span data-ttu-id="13996-1308">Viene trovata una parola chiave da Keyword_cc_verification.</span><span class="sxs-lookup"><span data-stu-id="13996-1308">A keyword from Keyword_cc_verification is found.</span></span>
    - <span data-ttu-id="13996-1309">Viene trovata una parola chiave da Keyword_cc_name.</span><span class="sxs-lookup"><span data-stu-id="13996-1309">A keyword from Keyword_cc_name is found.</span></span>
    - <span data-ttu-id="13996-1310">La funzione Func_expiration_date rileva una data nel formato corretto.</span><span class="sxs-lookup"><span data-stu-id="13996-1310">The function Func_expiration_date finds a date in the right date format.</span></span>
- <span data-ttu-id="13996-1311">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="13996-1311">The checksum passes.</span></span>

<span data-ttu-id="13996-1312">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 65%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="13996-1312">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="13996-1313">La funzione Func_credit_card restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="13996-1313">The function Func_credit_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="13996-1314">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="13996-1314">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="13996-1315">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="13996-1315">Keywords</span></span>

#### <a name="keywordccverification"></a><span data-ttu-id="13996-1316">Keyword_cc_verification</span><span class="sxs-lookup"><span data-stu-id="13996-1316">Keyword_cc_verification</span></span>

- <span data-ttu-id="13996-1317">card verification</span><span class="sxs-lookup"><span data-stu-id="13996-1317">card verification</span></span>
- <span data-ttu-id="13996-1318">card identification number</span><span class="sxs-lookup"><span data-stu-id="13996-1318">card identification number</span></span>
- <span data-ttu-id="13996-1319">CVN</span><span class="sxs-lookup"><span data-stu-id="13996-1319">cvn</span></span>
- <span data-ttu-id="13996-1320">ID</span><span class="sxs-lookup"><span data-stu-id="13996-1320">cid</span></span>
- <span data-ttu-id="13996-1321">CVC2</span><span class="sxs-lookup"><span data-stu-id="13996-1321">cvc2</span></span>
- <span data-ttu-id="13996-1322">CVV2</span><span class="sxs-lookup"><span data-stu-id="13996-1322">cvv2</span></span>
- <span data-ttu-id="13996-1323">pin block</span><span class="sxs-lookup"><span data-stu-id="13996-1323">pin block</span></span>
- <span data-ttu-id="13996-1324">security code</span><span class="sxs-lookup"><span data-stu-id="13996-1324">security code</span></span>
- <span data-ttu-id="13996-1325">security number</span><span class="sxs-lookup"><span data-stu-id="13996-1325">security number</span></span>
- <span data-ttu-id="13996-1326">security no</span><span class="sxs-lookup"><span data-stu-id="13996-1326">security no</span></span>
- <span data-ttu-id="13996-1327">issue number</span><span class="sxs-lookup"><span data-stu-id="13996-1327">issue number</span></span>
- <span data-ttu-id="13996-1328">issue no</span><span class="sxs-lookup"><span data-stu-id="13996-1328">issue no</span></span>
- <span data-ttu-id="13996-1329">cryptogramme</span><span class="sxs-lookup"><span data-stu-id="13996-1329">cryptogramme</span></span>
- <span data-ttu-id="13996-1330">numéro de sécurité</span><span class="sxs-lookup"><span data-stu-id="13996-1330">numéro de sécurité</span></span>
- <span data-ttu-id="13996-1331">numero de securite</span><span class="sxs-lookup"><span data-stu-id="13996-1331">numero de securite</span></span>
- <span data-ttu-id="13996-1332">kreditkartenprüfnummer</span><span class="sxs-lookup"><span data-stu-id="13996-1332">kreditkartenprüfnummer</span></span>
- <span data-ttu-id="13996-1333">kreditkartenprufnummer</span><span class="sxs-lookup"><span data-stu-id="13996-1333">kreditkartenprufnummer</span></span>
- <span data-ttu-id="13996-1334">prüfziffer</span><span class="sxs-lookup"><span data-stu-id="13996-1334">prüfziffer</span></span>
- <span data-ttu-id="13996-1335">Prufziffer</span><span class="sxs-lookup"><span data-stu-id="13996-1335">prufziffer</span></span>
- <span data-ttu-id="13996-1336">sicherheits Kode</span><span class="sxs-lookup"><span data-stu-id="13996-1336">sicherheits Kode</span></span>
- <span data-ttu-id="13996-1337">Sicherheitscode</span><span class="sxs-lookup"><span data-stu-id="13996-1337">sicherheitscode</span></span>
- <span data-ttu-id="13996-1338">sicherheitsnummer</span><span class="sxs-lookup"><span data-stu-id="13996-1338">sicherheitsnummer</span></span>
- <span data-ttu-id="13996-1339">Verfalldatum</span><span class="sxs-lookup"><span data-stu-id="13996-1339">verfalldatum</span></span>
- <span data-ttu-id="13996-1340">codice di verifica</span><span class="sxs-lookup"><span data-stu-id="13996-1340">codice di verifica</span></span>
- <span data-ttu-id="13996-1341">Cod.</span><span class="sxs-lookup"><span data-stu-id="13996-1341">cod.</span></span> <span data-ttu-id="13996-1342">sicurezza</span><span class="sxs-lookup"><span data-stu-id="13996-1342">sicurezza</span></span>
- <span data-ttu-id="13996-1343">cod sicurezza</span><span class="sxs-lookup"><span data-stu-id="13996-1343">cod sicurezza</span></span>
- <span data-ttu-id="13996-1344">n autorizzazione</span><span class="sxs-lookup"><span data-stu-id="13996-1344">n autorizzazione</span></span>
- <span data-ttu-id="13996-1345">Código</span><span class="sxs-lookup"><span data-stu-id="13996-1345">código</span></span>
- <span data-ttu-id="13996-1346">Codigo</span><span class="sxs-lookup"><span data-stu-id="13996-1346">codigo</span></span>
- <span data-ttu-id="13996-1347">Cod.</span><span class="sxs-lookup"><span data-stu-id="13996-1347">cod.</span></span> <span data-ttu-id="13996-1348">SEG</span><span class="sxs-lookup"><span data-stu-id="13996-1348">seg</span></span>
- <span data-ttu-id="13996-1349">cod seg</span><span class="sxs-lookup"><span data-stu-id="13996-1349">cod seg</span></span>
- <span data-ttu-id="13996-1350">código de segurança</span><span class="sxs-lookup"><span data-stu-id="13996-1350">código de segurança</span></span>
- <span data-ttu-id="13996-1351">codigo de seguranca</span><span class="sxs-lookup"><span data-stu-id="13996-1351">codigo de seguranca</span></span>
- <span data-ttu-id="13996-1352">codigo de segurança</span><span class="sxs-lookup"><span data-stu-id="13996-1352">codigo de segurança</span></span>
- <span data-ttu-id="13996-1353">código de seguranca</span><span class="sxs-lookup"><span data-stu-id="13996-1353">código de seguranca</span></span>
- <span data-ttu-id="13996-1354">cód.</span><span class="sxs-lookup"><span data-stu-id="13996-1354">cód.</span></span> <span data-ttu-id="13996-1355">Segurança</span><span class="sxs-lookup"><span data-stu-id="13996-1355">segurança</span></span>
- <span data-ttu-id="13996-1356">Cod.</span><span class="sxs-lookup"><span data-stu-id="13996-1356">cod.</span></span> <span data-ttu-id="13996-1357">SEGURANCA Cod.</span><span class="sxs-lookup"><span data-stu-id="13996-1357">seguranca cod.</span></span> <span data-ttu-id="13996-1358">Segurança</span><span class="sxs-lookup"><span data-stu-id="13996-1358">segurança</span></span>
- <span data-ttu-id="13996-1359">cód.</span><span class="sxs-lookup"><span data-stu-id="13996-1359">cód.</span></span> <span data-ttu-id="13996-1360">seguranca</span><span class="sxs-lookup"><span data-stu-id="13996-1360">seguranca</span></span>
- <span data-ttu-id="13996-1361">cód segurança</span><span class="sxs-lookup"><span data-stu-id="13996-1361">cód segurança</span></span>
- <span data-ttu-id="13996-1362">Cod SEGURANCA Cod Segurança</span><span class="sxs-lookup"><span data-stu-id="13996-1362">cod seguranca cod segurança</span></span>
- <span data-ttu-id="13996-1363">cód seguranca</span><span class="sxs-lookup"><span data-stu-id="13996-1363">cód seguranca</span></span>
- <span data-ttu-id="13996-1364">número de verificação</span><span class="sxs-lookup"><span data-stu-id="13996-1364">número de verificação</span></span>
- <span data-ttu-id="13996-1365">numero de verificacao</span><span class="sxs-lookup"><span data-stu-id="13996-1365">numero de verificacao</span></span>
- <span data-ttu-id="13996-1366">Ablauf</span><span class="sxs-lookup"><span data-stu-id="13996-1366">ablauf</span></span>
- <span data-ttu-id="13996-1367">gültig bis</span><span class="sxs-lookup"><span data-stu-id="13996-1367">gültig bis</span></span>
- <span data-ttu-id="13996-1368">gültigkeitsdatum</span><span class="sxs-lookup"><span data-stu-id="13996-1368">gültigkeitsdatum</span></span>
- <span data-ttu-id="13996-1369">gultig bis</span><span class="sxs-lookup"><span data-stu-id="13996-1369">gultig bis</span></span>
- <span data-ttu-id="13996-1370">gultigkeitsdatum</span><span class="sxs-lookup"><span data-stu-id="13996-1370">gultigkeitsdatum</span></span>
- <span data-ttu-id="13996-1371">scadenza</span><span class="sxs-lookup"><span data-stu-id="13996-1371">scadenza</span></span>
- <span data-ttu-id="13996-1372">data scad</span><span class="sxs-lookup"><span data-stu-id="13996-1372">data scad</span></span>
- <span data-ttu-id="13996-1373">fecha de expiracion</span><span class="sxs-lookup"><span data-stu-id="13996-1373">fecha de expiracion</span></span>
- <span data-ttu-id="13996-1374">fecha de venc</span><span class="sxs-lookup"><span data-stu-id="13996-1374">fecha de venc</span></span>
- <span data-ttu-id="13996-1375">vencimiento</span><span class="sxs-lookup"><span data-stu-id="13996-1375">vencimiento</span></span>
- <span data-ttu-id="13996-1376">válido hasta</span><span class="sxs-lookup"><span data-stu-id="13996-1376">válido hasta</span></span>
- <span data-ttu-id="13996-1377">valido hasta</span><span class="sxs-lookup"><span data-stu-id="13996-1377">valido hasta</span></span>
- <span data-ttu-id="13996-1378">VTO</span><span class="sxs-lookup"><span data-stu-id="13996-1378">vto</span></span>
- <span data-ttu-id="13996-1379">data de expiração</span><span class="sxs-lookup"><span data-stu-id="13996-1379">data de expiração</span></span>
- <span data-ttu-id="13996-1380">data de expiracao</span><span class="sxs-lookup"><span data-stu-id="13996-1380">data de expiracao</span></span>
- <span data-ttu-id="13996-1381">data em que expira</span><span class="sxs-lookup"><span data-stu-id="13996-1381">data em que expira</span></span>
- <span data-ttu-id="13996-1382">validade</span><span class="sxs-lookup"><span data-stu-id="13996-1382">validade</span></span>
- <span data-ttu-id="13996-1383">Valor</span><span class="sxs-lookup"><span data-stu-id="13996-1383">valor</span></span>
- <span data-ttu-id="13996-1384">vencimento</span><span class="sxs-lookup"><span data-stu-id="13996-1384">vencimento</span></span>
- <span data-ttu-id="13996-1385">Venc</span><span class="sxs-lookup"><span data-stu-id="13996-1385">Venc</span></span> 

#### <a name="keywordccname"></a><span data-ttu-id="13996-1386">Keyword_cc_name</span><span class="sxs-lookup"><span data-stu-id="13996-1386">Keyword_cc_name</span></span>

- <span data-ttu-id="13996-1387">Amex</span><span class="sxs-lookup"><span data-stu-id="13996-1387">amex</span></span>
- <span data-ttu-id="13996-1388">american express</span><span class="sxs-lookup"><span data-stu-id="13996-1388">american express</span></span>
- <span data-ttu-id="13996-1389">AmericanExpress</span><span class="sxs-lookup"><span data-stu-id="13996-1389">americanexpress</span></span>
- <span data-ttu-id="13996-1390">Esempio</span><span class="sxs-lookup"><span data-stu-id="13996-1390">Visa</span></span>
- <span data-ttu-id="13996-1391">Mastercard</span><span class="sxs-lookup"><span data-stu-id="13996-1391">mastercard</span></span>
- <span data-ttu-id="13996-1392">master card</span><span class="sxs-lookup"><span data-stu-id="13996-1392">master card</span></span>
- <span data-ttu-id="13996-1393">MC</span><span class="sxs-lookup"><span data-stu-id="13996-1393">mc</span></span> 
- <span data-ttu-id="13996-1394">Mastercard</span><span class="sxs-lookup"><span data-stu-id="13996-1394">mastercards</span></span>
- <span data-ttu-id="13996-1395">master cards</span><span class="sxs-lookup"><span data-stu-id="13996-1395">master cards</span></span>
- <span data-ttu-id="13996-1396">diner's Club</span><span class="sxs-lookup"><span data-stu-id="13996-1396">diner's Club</span></span>
- <span data-ttu-id="13996-1397">diners club</span><span class="sxs-lookup"><span data-stu-id="13996-1397">diners club</span></span>
- <span data-ttu-id="13996-1398">DinersClub</span><span class="sxs-lookup"><span data-stu-id="13996-1398">dinersclub</span></span>
- <span data-ttu-id="13996-1399">discover card</span><span class="sxs-lookup"><span data-stu-id="13996-1399">discover card</span></span>
- <span data-ttu-id="13996-1400">discovercard</span><span class="sxs-lookup"><span data-stu-id="13996-1400">discovercard</span></span>
- <span data-ttu-id="13996-1401">discover cards</span><span class="sxs-lookup"><span data-stu-id="13996-1401">discover cards</span></span>
- <span data-ttu-id="13996-1402">JCB</span><span class="sxs-lookup"><span data-stu-id="13996-1402">JCB</span></span>
- <span data-ttu-id="13996-1403">japanese card bureau</span><span class="sxs-lookup"><span data-stu-id="13996-1403">japanese card bureau</span></span>
- <span data-ttu-id="13996-1404">carte blanche</span><span class="sxs-lookup"><span data-stu-id="13996-1404">carte blanche</span></span>
- <span data-ttu-id="13996-1405">CarteBlanche</span><span class="sxs-lookup"><span data-stu-id="13996-1405">carteblanche</span></span>
- <span data-ttu-id="13996-1406">credit card</span><span class="sxs-lookup"><span data-stu-id="13996-1406">credit card</span></span>
- <span data-ttu-id="13996-1407">CC</span><span class="sxs-lookup"><span data-stu-id="13996-1407">cc#</span></span>
- <span data-ttu-id="13996-1408">CC #:</span><span class="sxs-lookup"><span data-stu-id="13996-1408">cc#:</span></span>
- <span data-ttu-id="13996-1409">expiration date</span><span class="sxs-lookup"><span data-stu-id="13996-1409">expiration date</span></span>
- <span data-ttu-id="13996-1410">exp date</span><span class="sxs-lookup"><span data-stu-id="13996-1410">exp date</span></span>
- <span data-ttu-id="13996-1411">expiry date</span><span class="sxs-lookup"><span data-stu-id="13996-1411">expiry date</span></span>
- <span data-ttu-id="13996-1412">date d’expiration</span><span class="sxs-lookup"><span data-stu-id="13996-1412">date d’expiration</span></span>
- <span data-ttu-id="13996-1413">date d'exp</span><span class="sxs-lookup"><span data-stu-id="13996-1413">date d'exp</span></span>
- <span data-ttu-id="13996-1414">date expiration</span><span class="sxs-lookup"><span data-stu-id="13996-1414">date expiration</span></span>
- <span data-ttu-id="13996-1415">bank card</span><span class="sxs-lookup"><span data-stu-id="13996-1415">bank card</span></span>
- <span data-ttu-id="13996-1416">Bankcard</span><span class="sxs-lookup"><span data-stu-id="13996-1416">bankcard</span></span>
- <span data-ttu-id="13996-1417">card number</span><span class="sxs-lookup"><span data-stu-id="13996-1417">card number</span></span>
- <span data-ttu-id="13996-1418">card num</span><span class="sxs-lookup"><span data-stu-id="13996-1418">card num</span></span>
- <span data-ttu-id="13996-1419">CardNumber</span><span class="sxs-lookup"><span data-stu-id="13996-1419">cardnumber</span></span>
- <span data-ttu-id="13996-1420">cardnumbers</span><span class="sxs-lookup"><span data-stu-id="13996-1420">cardnumbers</span></span>
- <span data-ttu-id="13996-1421">card numbers</span><span class="sxs-lookup"><span data-stu-id="13996-1421">card numbers</span></span>
- <span data-ttu-id="13996-1422">CreditCard</span><span class="sxs-lookup"><span data-stu-id="13996-1422">creditcard</span></span>
- <span data-ttu-id="13996-1423">credit cards</span><span class="sxs-lookup"><span data-stu-id="13996-1423">credit cards</span></span>
- <span data-ttu-id="13996-1424">creditcards.com</span><span class="sxs-lookup"><span data-stu-id="13996-1424">creditcards</span></span>
- <span data-ttu-id="13996-1425">Ccn</span><span class="sxs-lookup"><span data-stu-id="13996-1425">ccn</span></span>
- <span data-ttu-id="13996-1426">card holder</span><span class="sxs-lookup"><span data-stu-id="13996-1426">card holder</span></span>
- <span data-ttu-id="13996-1427">titolare</span><span class="sxs-lookup"><span data-stu-id="13996-1427">cardholder</span></span>
- <span data-ttu-id="13996-1428">card holders</span><span class="sxs-lookup"><span data-stu-id="13996-1428">card holders</span></span>
- <span data-ttu-id="13996-1429">titolari</span><span class="sxs-lookup"><span data-stu-id="13996-1429">cardholders</span></span>
- <span data-ttu-id="13996-1430">check card</span><span class="sxs-lookup"><span data-stu-id="13996-1430">check card</span></span>
- <span data-ttu-id="13996-1431">checkcard</span><span class="sxs-lookup"><span data-stu-id="13996-1431">checkcard</span></span>
- <span data-ttu-id="13996-1432">check cards</span><span class="sxs-lookup"><span data-stu-id="13996-1432">check cards</span></span>
- <span data-ttu-id="13996-1433">checkcards</span><span class="sxs-lookup"><span data-stu-id="13996-1433">checkcards</span></span>
- <span data-ttu-id="13996-1434">debit card</span><span class="sxs-lookup"><span data-stu-id="13996-1434">debit card</span></span>
- <span data-ttu-id="13996-1435">debitcard</span><span class="sxs-lookup"><span data-stu-id="13996-1435">debitcard</span></span>
- <span data-ttu-id="13996-1436">debit cards</span><span class="sxs-lookup"><span data-stu-id="13996-1436">debit cards</span></span>
- <span data-ttu-id="13996-1437">debitcards</span><span class="sxs-lookup"><span data-stu-id="13996-1437">debitcards</span></span>
- <span data-ttu-id="13996-1438">atm card</span><span class="sxs-lookup"><span data-stu-id="13996-1438">atm card</span></span>
- <span data-ttu-id="13996-1439">atmcard</span><span class="sxs-lookup"><span data-stu-id="13996-1439">atmcard</span></span>
- <span data-ttu-id="13996-1440">atm cards</span><span class="sxs-lookup"><span data-stu-id="13996-1440">atm cards</span></span>
- <span data-ttu-id="13996-1441">atmcards</span><span class="sxs-lookup"><span data-stu-id="13996-1441">atmcards</span></span>
- <span data-ttu-id="13996-1442">Enroute</span><span class="sxs-lookup"><span data-stu-id="13996-1442">enroute</span></span>
- <span data-ttu-id="13996-1443">en route</span><span class="sxs-lookup"><span data-stu-id="13996-1443">en route</span></span>
- <span data-ttu-id="13996-1444">card type</span><span class="sxs-lookup"><span data-stu-id="13996-1444">card type</span></span>
- <span data-ttu-id="13996-1445">carte bancaire</span><span class="sxs-lookup"><span data-stu-id="13996-1445">carte bancaire</span></span>
- <span data-ttu-id="13996-1446">carte de crédit</span><span class="sxs-lookup"><span data-stu-id="13996-1446">carte de crédit</span></span>
- <span data-ttu-id="13996-1447">carte de credit</span><span class="sxs-lookup"><span data-stu-id="13996-1447">carte de credit</span></span>
- <span data-ttu-id="13996-1448">numéro de carte</span><span class="sxs-lookup"><span data-stu-id="13996-1448">numéro de carte</span></span>
- <span data-ttu-id="13996-1449">numero de carte</span><span class="sxs-lookup"><span data-stu-id="13996-1449">numero de carte</span></span>
- <span data-ttu-id="13996-1450">nº de la carte</span><span class="sxs-lookup"><span data-stu-id="13996-1450">nº de la carte</span></span>
- <span data-ttu-id="13996-1451">nº de carte</span><span class="sxs-lookup"><span data-stu-id="13996-1451">nº de carte</span></span>
- <span data-ttu-id="13996-1452">Kreditkarte</span><span class="sxs-lookup"><span data-stu-id="13996-1452">kreditkarte</span></span>
- <span data-ttu-id="13996-1453">Karte</span><span class="sxs-lookup"><span data-stu-id="13996-1453">karte</span></span>
- <span data-ttu-id="13996-1454">Karteninhaber</span><span class="sxs-lookup"><span data-stu-id="13996-1454">karteninhaber</span></span>
- <span data-ttu-id="13996-1455">karteninhabers</span><span class="sxs-lookup"><span data-stu-id="13996-1455">karteninhabers</span></span>
- <span data-ttu-id="13996-1456">kreditkarteninhaber</span><span class="sxs-lookup"><span data-stu-id="13996-1456">kreditkarteninhaber</span></span>
- <span data-ttu-id="13996-1457">Kreditkarteninstitut</span><span class="sxs-lookup"><span data-stu-id="13996-1457">kreditkarteninstitut</span></span>
- <span data-ttu-id="13996-1458">kreditkartentyp</span><span class="sxs-lookup"><span data-stu-id="13996-1458">kreditkartentyp</span></span>
- <span data-ttu-id="13996-1459">eigentümername</span><span class="sxs-lookup"><span data-stu-id="13996-1459">eigentümername</span></span>
- <span data-ttu-id="13996-1460">kartennr</span><span class="sxs-lookup"><span data-stu-id="13996-1460">kartennr</span></span> 
- <span data-ttu-id="13996-1461">kartennummer</span><span class="sxs-lookup"><span data-stu-id="13996-1461">kartennummer</span></span>
- <span data-ttu-id="13996-1462">kreditkartennummer</span><span class="sxs-lookup"><span data-stu-id="13996-1462">kreditkartennummer</span></span>
- <span data-ttu-id="13996-1463">Kreditkarten-Nummer</span><span class="sxs-lookup"><span data-stu-id="13996-1463">kreditkarten-nummer</span></span>
- <span data-ttu-id="13996-1464">carta di credito</span><span class="sxs-lookup"><span data-stu-id="13996-1464">carta di credito</span></span>
- <span data-ttu-id="13996-1465">carta credito</span><span class="sxs-lookup"><span data-stu-id="13996-1465">carta credito</span></span>
- <span data-ttu-id="13996-1466">carta</span><span class="sxs-lookup"><span data-stu-id="13996-1466">carta</span></span>
- <span data-ttu-id="13996-1467">n carta</span><span class="sxs-lookup"><span data-stu-id="13996-1467">n carta</span></span>
- <span data-ttu-id="13996-1468">Nr.</span><span class="sxs-lookup"><span data-stu-id="13996-1468">nr.</span></span> <span data-ttu-id="13996-1469">carta</span><span class="sxs-lookup"><span data-stu-id="13996-1469">carta</span></span>
- <span data-ttu-id="13996-1470">nr carta</span><span class="sxs-lookup"><span data-stu-id="13996-1470">nr carta</span></span>
- <span data-ttu-id="13996-1471">numero carta</span><span class="sxs-lookup"><span data-stu-id="13996-1471">numero carta</span></span>
- <span data-ttu-id="13996-1472">numero della carta</span><span class="sxs-lookup"><span data-stu-id="13996-1472">numero della carta</span></span>
- <span data-ttu-id="13996-1473">numero di carta</span><span class="sxs-lookup"><span data-stu-id="13996-1473">numero di carta</span></span>
- <span data-ttu-id="13996-1474">tarjeta credito</span><span class="sxs-lookup"><span data-stu-id="13996-1474">tarjeta credito</span></span>
- <span data-ttu-id="13996-1475">tarjeta de credito</span><span class="sxs-lookup"><span data-stu-id="13996-1475">tarjeta de credito</span></span>
- <span data-ttu-id="13996-1476">tarjeta crédito</span><span class="sxs-lookup"><span data-stu-id="13996-1476">tarjeta crédito</span></span>
- <span data-ttu-id="13996-1477">tarjeta de crédito</span><span class="sxs-lookup"><span data-stu-id="13996-1477">tarjeta de crédito</span></span>
- <span data-ttu-id="13996-1478">tarjeta de atm</span><span class="sxs-lookup"><span data-stu-id="13996-1478">tarjeta de atm</span></span>
- <span data-ttu-id="13996-1479">tarjeta atm</span><span class="sxs-lookup"><span data-stu-id="13996-1479">tarjeta atm</span></span>
- <span data-ttu-id="13996-1480">tarjeta debito</span><span class="sxs-lookup"><span data-stu-id="13996-1480">tarjeta debito</span></span>
- <span data-ttu-id="13996-1481">tarjeta de debito</span><span class="sxs-lookup"><span data-stu-id="13996-1481">tarjeta de debito</span></span>
- <span data-ttu-id="13996-1482">tarjeta débito</span><span class="sxs-lookup"><span data-stu-id="13996-1482">tarjeta débito</span></span>
- <span data-ttu-id="13996-1483">tarjeta de débito</span><span class="sxs-lookup"><span data-stu-id="13996-1483">tarjeta de débito</span></span>
- <span data-ttu-id="13996-1484">nº de tarjeta</span><span class="sxs-lookup"><span data-stu-id="13996-1484">nº de tarjeta</span></span>
- <span data-ttu-id="13996-1485">No.</span><span class="sxs-lookup"><span data-stu-id="13996-1485">no.</span></span> <span data-ttu-id="13996-1486">de tarjeta</span><span class="sxs-lookup"><span data-stu-id="13996-1486">de tarjeta</span></span>
- <span data-ttu-id="13996-1487">no de tarjeta</span><span class="sxs-lookup"><span data-stu-id="13996-1487">no de tarjeta</span></span>
- <span data-ttu-id="13996-1488">numero de tarjeta</span><span class="sxs-lookup"><span data-stu-id="13996-1488">numero de tarjeta</span></span>
- <span data-ttu-id="13996-1489">número de tarjeta</span><span class="sxs-lookup"><span data-stu-id="13996-1489">número de tarjeta</span></span>
- <span data-ttu-id="13996-1490">tarjeta no</span><span class="sxs-lookup"><span data-stu-id="13996-1490">tarjeta no</span></span>
- <span data-ttu-id="13996-1491">tarjetahabiente</span><span class="sxs-lookup"><span data-stu-id="13996-1491">tarjetahabiente</span></span>
- <span data-ttu-id="13996-1492">cartão de crédito</span><span class="sxs-lookup"><span data-stu-id="13996-1492">cartão de crédito</span></span>
- <span data-ttu-id="13996-1493">cartão de credito</span><span class="sxs-lookup"><span data-stu-id="13996-1493">cartão de credito</span></span>
- <span data-ttu-id="13996-1494">cartao de crédito</span><span class="sxs-lookup"><span data-stu-id="13996-1494">cartao de crédito</span></span>
- <span data-ttu-id="13996-1495">cartao de credito</span><span class="sxs-lookup"><span data-stu-id="13996-1495">cartao de credito</span></span>
- <span data-ttu-id="13996-1496">cartão de débito</span><span class="sxs-lookup"><span data-stu-id="13996-1496">cartão de débito</span></span>
- <span data-ttu-id="13996-1497">cartao de débito</span><span class="sxs-lookup"><span data-stu-id="13996-1497">cartao de débito</span></span>
- <span data-ttu-id="13996-1498">cartão de debito</span><span class="sxs-lookup"><span data-stu-id="13996-1498">cartão de debito</span></span>
- <span data-ttu-id="13996-1499">cartao de debito</span><span class="sxs-lookup"><span data-stu-id="13996-1499">cartao de debito</span></span>
- <span data-ttu-id="13996-1500">débito automático</span><span class="sxs-lookup"><span data-stu-id="13996-1500">débito automático</span></span>
- <span data-ttu-id="13996-1501">debito automatico</span><span class="sxs-lookup"><span data-stu-id="13996-1501">debito automatico</span></span>
- <span data-ttu-id="13996-1502">número do cartão</span><span class="sxs-lookup"><span data-stu-id="13996-1502">número do cartão</span></span>
- <span data-ttu-id="13996-1503">numero do cartão</span><span class="sxs-lookup"><span data-stu-id="13996-1503">numero do cartão</span></span> 
- <span data-ttu-id="13996-1504">número do cartao</span><span class="sxs-lookup"><span data-stu-id="13996-1504">número do cartao</span></span>
- <span data-ttu-id="13996-1505">numero do cartao</span><span class="sxs-lookup"><span data-stu-id="13996-1505">numero do cartao</span></span>
- <span data-ttu-id="13996-1506">número de cartão</span><span class="sxs-lookup"><span data-stu-id="13996-1506">número de cartão</span></span>
- <span data-ttu-id="13996-1507">numero de cartão</span><span class="sxs-lookup"><span data-stu-id="13996-1507">numero de cartão</span></span>
- <span data-ttu-id="13996-1508">número de cartao</span><span class="sxs-lookup"><span data-stu-id="13996-1508">número de cartao</span></span>
- <span data-ttu-id="13996-1509">numero de cartao</span><span class="sxs-lookup"><span data-stu-id="13996-1509">numero de cartao</span></span>
- <span data-ttu-id="13996-1510">nº do cartão</span><span class="sxs-lookup"><span data-stu-id="13996-1510">nº do cartão</span></span>
- <span data-ttu-id="13996-1511">nº do cartao</span><span class="sxs-lookup"><span data-stu-id="13996-1511">nº do cartao</span></span>
- <span data-ttu-id="13996-1512">n º.</span><span class="sxs-lookup"><span data-stu-id="13996-1512">nº.</span></span> <span data-ttu-id="13996-1513">do cartão</span><span class="sxs-lookup"><span data-stu-id="13996-1513">do cartão</span></span>
- <span data-ttu-id="13996-1514">no do cartão</span><span class="sxs-lookup"><span data-stu-id="13996-1514">no do cartão</span></span>
- <span data-ttu-id="13996-1515">no do cartao</span><span class="sxs-lookup"><span data-stu-id="13996-1515">no do cartao</span></span>
- <span data-ttu-id="13996-1516">No.</span><span class="sxs-lookup"><span data-stu-id="13996-1516">no.</span></span> <span data-ttu-id="13996-1517">do cartão</span><span class="sxs-lookup"><span data-stu-id="13996-1517">do cartão</span></span>
- <span data-ttu-id="13996-1518">No.</span><span class="sxs-lookup"><span data-stu-id="13996-1518">no.</span></span> <span data-ttu-id="13996-1519">do cartao</span><span class="sxs-lookup"><span data-stu-id="13996-1519">do cartao</span></span> 
   
## <a name="croatia-identity-card-number"></a><span data-ttu-id="13996-1520">Numero di carta di identità della Croazia</span><span class="sxs-lookup"><span data-stu-id="13996-1520">Croatia Identity Card Number</span></span>

### <a name="format"></a><span data-ttu-id="13996-1521">Formato</span><span class="sxs-lookup"><span data-stu-id="13996-1521">Format</span></span>

<span data-ttu-id="13996-1522">9 cifre</span><span class="sxs-lookup"><span data-stu-id="13996-1522">Nine digits</span></span>

### <a name="pattern"></a><span data-ttu-id="13996-1523">Modello</span><span class="sxs-lookup"><span data-stu-id="13996-1523">Pattern</span></span>

<span data-ttu-id="13996-1524">9 cifre consecutive</span><span class="sxs-lookup"><span data-stu-id="13996-1524">Nine consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="13996-1525">Checksum</span><span class="sxs-lookup"><span data-stu-id="13996-1525">Checksum</span></span>

<span data-ttu-id="13996-1526">No</span><span class="sxs-lookup"><span data-stu-id="13996-1526">No</span></span>

### <a name="definition"></a><span data-ttu-id="13996-1527">Definizione</span><span class="sxs-lookup"><span data-stu-id="13996-1527">Definition</span></span>

<span data-ttu-id="13996-1528">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="13996-1528">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="13996-1529">La funzione Func_croatia_id_card trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="13996-1529">The function Func_croatia_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="13996-1530">Viene trovata una parola chiave da Keyword_croatia_id_card.</span><span class="sxs-lookup"><span data-stu-id="13996-1530">A keyword from Keyword_croatia_id_card is found.</span></span>

```
<!--Croatia Identity Card Number-->
<Entity id="ff12f884-c20a-4189-b185-34c8e7258d47" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_croatia_id_card"/>
     <Match idRef="Keyword_croatia_id_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="13996-1531">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="13996-1531">Keywords</span></span>

#### <a name="keywordcroatiaidcard"></a><span data-ttu-id="13996-1532">Keyword_croatia_id_card</span><span class="sxs-lookup"><span data-stu-id="13996-1532">Keyword_croatia_id_card</span></span>

- <span data-ttu-id="13996-1533">Carta d’identità croata</span><span class="sxs-lookup"><span data-stu-id="13996-1533">Croatian identity card</span></span>
- <span data-ttu-id="13996-1534">Osobna iskaznica</span><span class="sxs-lookup"><span data-stu-id="13996-1534">Osobna iskaznica</span></span>

   
## <a name="croatia-personal-identification-oib-number"></a><span data-ttu-id="13996-1535">Numero di identificazione personale (OIB) - Croazia</span><span class="sxs-lookup"><span data-stu-id="13996-1535">Croatia Personal Identification (OIB) Number</span></span>

### <a name="format"></a><span data-ttu-id="13996-1536">Formato</span><span class="sxs-lookup"><span data-stu-id="13996-1536">Format</span></span>

<span data-ttu-id="13996-1537">11 cifre</span><span class="sxs-lookup"><span data-stu-id="13996-1537">11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="13996-1538">Modello</span><span class="sxs-lookup"><span data-stu-id="13996-1538">Pattern</span></span>

<span data-ttu-id="13996-1539">11 cifre:</span><span class="sxs-lookup"><span data-stu-id="13996-1539">11 digits:</span></span>
- <span data-ttu-id="13996-1540">10 cifre</span><span class="sxs-lookup"><span data-stu-id="13996-1540">10 digits</span></span> 
- <span data-ttu-id="13996-1541">La cifra finale è una cifra di controllo ai fini dello scambio di dati internazionali, le lettere HR vengono aggiunte prima delle undici cifre.</span><span class="sxs-lookup"><span data-stu-id="13996-1541">Final digit is a check digit For the purposes of international data exchange, the letters HR are added preceding the eleven digits.</span></span>

### <a name="checksum"></a><span data-ttu-id="13996-1542">Checksum</span><span class="sxs-lookup"><span data-stu-id="13996-1542">Checksum</span></span>

<span data-ttu-id="13996-1543">Sì</span><span class="sxs-lookup"><span data-stu-id="13996-1543">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="13996-1544">Definizione</span><span class="sxs-lookup"><span data-stu-id="13996-1544">Definition</span></span>

<span data-ttu-id="13996-1545">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="13996-1545">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="13996-1546">La funzione Func_croatia_oib_number trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="13996-1546">The function Func_croatia_oib_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="13996-1547">Viene trovata una parola chiave da Keyword_croatia_oib_number.</span><span class="sxs-lookup"><span data-stu-id="13996-1547">A keyword from Keyword_croatia_oib_number is found.</span></span>
- <span data-ttu-id="13996-1548">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="13996-1548">The checksum passes.</span></span>

<span data-ttu-id="13996-1549">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="13996-1549">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="13996-1550">La funzione Func_croatia_oib_number trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="13996-1550">The function Func_croatia_oib_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="13996-1551">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="13996-1551">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="13996-1552">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="13996-1552">Keywords</span></span>

#### <a name="keywordcroatiaoibnumber"></a><span data-ttu-id="13996-1553">Keyword_croatia_oib_number</span><span class="sxs-lookup"><span data-stu-id="13996-1553">Keyword_croatia_oib_number</span></span>

- <span data-ttu-id="13996-1554">Codice PIN</span><span class="sxs-lookup"><span data-stu-id="13996-1554">Personal Identification Number</span></span>
- <span data-ttu-id="13996-1555">Osobni identifikacijski broj</span><span class="sxs-lookup"><span data-stu-id="13996-1555">Osobni identifikacijski broj</span></span> 
- <span data-ttu-id="13996-1556">OIB</span><span class="sxs-lookup"><span data-stu-id="13996-1556">OIB</span></span> 

   
## <a name="czech-personal-identity-number"></a><span data-ttu-id="13996-1557">Numero di identità personale ceco</span><span class="sxs-lookup"><span data-stu-id="13996-1557">Czech Personal Identity Number</span></span>

### <a name="format"></a><span data-ttu-id="13996-1558">Formato</span><span class="sxs-lookup"><span data-stu-id="13996-1558">Format</span></span>

<span data-ttu-id="13996-1559">Nove cifre con Slash opzionale (formato precedente) 10 cifre con barra di inoltro facoltativa (nuovo formato)</span><span class="sxs-lookup"><span data-stu-id="13996-1559">Nine digits with optional forward slash (old format) 10 digits with optional forward slash (new format)</span></span>

### <a name="pattern"></a><span data-ttu-id="13996-1560">Modello</span><span class="sxs-lookup"><span data-stu-id="13996-1560">Pattern</span></span>

<span data-ttu-id="13996-1561">Nove cifre (formato obsoleto):</span><span class="sxs-lookup"><span data-stu-id="13996-1561">Nine digits (old format):</span></span>
- <span data-ttu-id="13996-1562">9 cifre</span><span class="sxs-lookup"><span data-stu-id="13996-1562">Nine digits</span></span>

<span data-ttu-id="13996-1563">O</span><span class="sxs-lookup"><span data-stu-id="13996-1563">OR</span></span>

- <span data-ttu-id="13996-1564">Sei cifre che rappresentano la data di nascita</span><span class="sxs-lookup"><span data-stu-id="13996-1564">Six digits that represent date of birth</span></span>
- <span data-ttu-id="13996-1565">Una barra</span><span class="sxs-lookup"><span data-stu-id="13996-1565">A forward slash</span></span>
- <span data-ttu-id="13996-1566">Tre cifre</span><span class="sxs-lookup"><span data-stu-id="13996-1566">Three digits</span></span>

<span data-ttu-id="13996-1567">10 cifre (nuovo formato):</span><span class="sxs-lookup"><span data-stu-id="13996-1567">10 digits (new format):</span></span>
- <span data-ttu-id="13996-1568">10 cifre</span><span class="sxs-lookup"><span data-stu-id="13996-1568">10 digits</span></span>

<span data-ttu-id="13996-1569">O</span><span class="sxs-lookup"><span data-stu-id="13996-1569">OR</span></span>

- <span data-ttu-id="13996-1570">Sei cifre che rappresentano la data di nascita</span><span class="sxs-lookup"><span data-stu-id="13996-1570">Six digits that represent date of birth</span></span>
- <span data-ttu-id="13996-1571">Una barra</span><span class="sxs-lookup"><span data-stu-id="13996-1571">A forward slash</span></span> 
- <span data-ttu-id="13996-1572">Quattro cifre in cui l'ultima cifra è una cifra di controllo</span><span class="sxs-lookup"><span data-stu-id="13996-1572">Four digits where last digit is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="13996-1573">Checksum</span><span class="sxs-lookup"><span data-stu-id="13996-1573">Checksum</span></span>

<span data-ttu-id="13996-1574">Sì</span><span class="sxs-lookup"><span data-stu-id="13996-1574">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="13996-1575">Definizione</span><span class="sxs-lookup"><span data-stu-id="13996-1575">Definition</span></span>

<span data-ttu-id="13996-1576">Un criterio DLP è 85% fiducioso di aver rilevato questo tipo di informazioni riservate se, entro 300 caratteri: la funzione Func_czech_id_card trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="13996-1576">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The function Func_czech_id_card finds content that matches the pattern.</span></span>
<span data-ttu-id="13996-1577">Viene trovata una parola chiave da Keyword_czech_id_card.</span><span class="sxs-lookup"><span data-stu-id="13996-1577">A keyword from Keyword_czech_id_card is found.</span></span>
<span data-ttu-id="13996-1578">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="13996-1578">The checksum passes.</span></span>

```
<!-- Czech Personal Identity Number -->
<Entity id="60c0725a-4eb6-455b-9dda-05d8a7396497"      patternsProximity="300" recommendedConfidence="85">
   <Pattern confidenceLevel="85">
      <IdMatch idRef="Func_czech_id_card" />
      <Match idRef="Keyword_czech_id_card" />
   </Pattern>
</Entity>
```
### <a name="keywords"></a><span data-ttu-id="13996-1579">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="13996-1579">Keywords</span></span>

- <span data-ttu-id="13996-1580">numero di identità personale ceco</span><span class="sxs-lookup"><span data-stu-id="13996-1580">czech personal identity number</span></span>
- <span data-ttu-id="13996-1581">Rodné číslo</span><span class="sxs-lookup"><span data-stu-id="13996-1581">Rodné číslo</span></span>
   
## <a name="denmark-personal-identification-number"></a><span data-ttu-id="13996-1582">Codice PIN - Danimarca</span><span class="sxs-lookup"><span data-stu-id="13996-1582">Denmark Personal Identification Number</span></span>

### <a name="format"></a><span data-ttu-id="13996-1583">Formato</span><span class="sxs-lookup"><span data-stu-id="13996-1583">Format</span></span>

<span data-ttu-id="13996-1584">10 cifre contenenti una lineetta</span><span class="sxs-lookup"><span data-stu-id="13996-1584">10 digits containing a hyphen</span></span>

### <a name="pattern"></a><span data-ttu-id="13996-1585">Modello</span><span class="sxs-lookup"><span data-stu-id="13996-1585">Pattern</span></span>

<span data-ttu-id="13996-1586">10 cifre:</span><span class="sxs-lookup"><span data-stu-id="13996-1586">10 digits:</span></span>
- <span data-ttu-id="13996-1587">Sei cifre nel formato GGMMAA, ovvero la data di nascita</span><span class="sxs-lookup"><span data-stu-id="13996-1587">Six digits in the format DDMMYY which are the date of birth</span></span> 
- <span data-ttu-id="13996-1588">Una lineetta</span><span class="sxs-lookup"><span data-stu-id="13996-1588">A hyphen</span></span> 
- <span data-ttu-id="13996-1589">Quattro cifre, dove l'ultima è una cifra di controllo</span><span class="sxs-lookup"><span data-stu-id="13996-1589">Four digits where the final digit is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="13996-1590">Checksum</span><span class="sxs-lookup"><span data-stu-id="13996-1590">Checksum</span></span>

<span data-ttu-id="13996-1591">Sì</span><span class="sxs-lookup"><span data-stu-id="13996-1591">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="13996-1592">Definizione</span><span class="sxs-lookup"><span data-stu-id="13996-1592">Definition</span></span>

<span data-ttu-id="13996-1593">Un criterio DLP è 75% fiducioso di aver rilevato questo tipo di informazioni riservate se, entro 300 caratteri: l'espressione regolare Regex_denmark_id trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="13996-1593">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The regular expression Regex_denmark_id finds content that matches the pattern.</span></span>
<span data-ttu-id="13996-1594">Viene trovata una parola chiave da Keyword_denmark_id.</span><span class="sxs-lookup"><span data-stu-id="13996-1594">A keyword from Keyword_denmark_id is found.</span></span>
<span data-ttu-id="13996-1595">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="13996-1595">The checksum passes.</span></span>

```
<!-- Denmark Personal Identification Number -->
<Entity id="6c4f2fef-56e1-4c00-8093-88d7a01cf460" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_denmark_id"/>
     <Match idRef="Keyword_denmark_id"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="13996-1596">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="13996-1596">Keywords</span></span>

#### <a name="keyworddenmarkid"></a><span data-ttu-id="13996-1597">Keyword_denmark_id</span><span class="sxs-lookup"><span data-stu-id="13996-1597">Keyword_denmark_id</span></span>

- <span data-ttu-id="13996-1598">Codice PIN</span><span class="sxs-lookup"><span data-stu-id="13996-1598">Personal Identification Number</span></span>
- <span data-ttu-id="13996-1599">CPR</span><span class="sxs-lookup"><span data-stu-id="13996-1599">CPR</span></span>
- <span data-ttu-id="13996-1600">Det Centrale Personregister</span><span class="sxs-lookup"><span data-stu-id="13996-1600">Det Centrale Personregister</span></span>
- <span data-ttu-id="13996-1601">Personnummer</span><span class="sxs-lookup"><span data-stu-id="13996-1601">Personnummer</span></span>
   
## <a name="drug-enforcement-agency-dea-number"></a><span data-ttu-id="13996-1602">Numero della Drug Enforcement Agency (DEA)</span><span class="sxs-lookup"><span data-stu-id="13996-1602">Drug Enforcement Agency (DEA) Number</span></span>

### <a name="format"></a><span data-ttu-id="13996-1603">Formato</span><span class="sxs-lookup"><span data-stu-id="13996-1603">Format</span></span>

<span data-ttu-id="13996-1604">Due lettere seguite da 7 cifre</span><span class="sxs-lookup"><span data-stu-id="13996-1604">Two letters followed by seven digits</span></span>

### <a name="pattern"></a><span data-ttu-id="13996-1605">Modello</span><span class="sxs-lookup"><span data-stu-id="13996-1605">Pattern</span></span>

<span data-ttu-id="13996-1606">Il modello deve includere tutti gli elementi seguenti:</span><span class="sxs-lookup"><span data-stu-id="13996-1606">Pattern must include all of the following:</span></span>
- <span data-ttu-id="13996-1607">Una lettera (senza distinzione tra maiuscole/minuscole) da questo gruppo di lettere: abcdefghjklmnprstux, ovvero un codice registrante</span><span class="sxs-lookup"><span data-stu-id="13996-1607">One letter (not case sensitive) from this set of possible letters: abcdefghjklmnprstux, which is a registrant code</span></span> 
- <span data-ttu-id="13996-1608">Una lettera (senza distinzione tra maiuscole/minuscole), ovvero la prima lettera del cognome del registrante</span><span class="sxs-lookup"><span data-stu-id="13996-1608">One letter (not case sensitive), which is the first letter of the registrant's last name</span></span> 
- <span data-ttu-id="13996-1609">7 cifre e l'ultima è quella di controllo</span><span class="sxs-lookup"><span data-stu-id="13996-1609">Seven digits, the last of which is the check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="13996-1610">Checksum</span><span class="sxs-lookup"><span data-stu-id="13996-1610">Checksum</span></span>

<span data-ttu-id="13996-1611">Sì</span><span class="sxs-lookup"><span data-stu-id="13996-1611">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="13996-1612">Definizione</span><span class="sxs-lookup"><span data-stu-id="13996-1612">Definition</span></span>

<span data-ttu-id="13996-1613">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="13996-1613">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="13996-1614">La funzione Func_dea_number restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="13996-1614">The function Func_dea_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="13996-1615">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="13996-1615">The checksum passes.</span></span>

```
<!-- DEA Number -->
<Entity id="9a5445ad-406e-43eb-8bd7-cac17ab6d0e4" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_dea_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="13996-1616">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="13996-1616">Keywords</span></span>

<span data-ttu-id="13996-1617">Nessuno</span><span class="sxs-lookup"><span data-stu-id="13996-1617">None</span></span>

   
## <a name="eu-debit-card-number"></a><span data-ttu-id="13996-1618">Unione Europea - Numero di carta di debito</span><span class="sxs-lookup"><span data-stu-id="13996-1618">EU Debit Card Number</span></span>

### <a name="format"></a><span data-ttu-id="13996-1619">Formato</span><span class="sxs-lookup"><span data-stu-id="13996-1619">Format</span></span>

<span data-ttu-id="13996-1620">16 cifre</span><span class="sxs-lookup"><span data-stu-id="13996-1620">16 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="13996-1621">Modello</span><span class="sxs-lookup"><span data-stu-id="13996-1621">Pattern</span></span>

<span data-ttu-id="13996-1622">Modello molto complesso e solido</span><span class="sxs-lookup"><span data-stu-id="13996-1622">Very complex and robust pattern</span></span>

### <a name="checksum"></a><span data-ttu-id="13996-1623">Checksum</span><span class="sxs-lookup"><span data-stu-id="13996-1623">Checksum</span></span>

<span data-ttu-id="13996-1624">Sì</span><span class="sxs-lookup"><span data-stu-id="13996-1624">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="13996-1625">Definizione</span><span class="sxs-lookup"><span data-stu-id="13996-1625">Definition</span></span>

<span data-ttu-id="13996-1626">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="13996-1626">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="13996-1627">La funzione Func_eu_debit_card restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="13996-1627">The function Func_eu_debit_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="13996-1628">Si verifica almeno una delle situazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="13996-1628">At least one of the following is true:</span></span>
    - <span data-ttu-id="13996-1629">Viene trovata una parola chiave da Keyword_eu_debit_card.</span><span class="sxs-lookup"><span data-stu-id="13996-1629">A keyword from Keyword_eu_debit_card is found.</span></span>
    - <span data-ttu-id="13996-1630">Viene trovata una parola chiave da Keyword_card_terms_dict.</span><span class="sxs-lookup"><span data-stu-id="13996-1630">A keyword from Keyword_card_terms_dict is found.</span></span>
    - <span data-ttu-id="13996-1631">Viene trovata una parola chiave da Keyword_card_security_terms_dict.</span><span class="sxs-lookup"><span data-stu-id="13996-1631">A keyword from Keyword_card_security_terms_dict is found.</span></span>
    - <span data-ttu-id="13996-1632">Viene trovata una parola chiave da Keyword_card_expiration_terms_dict.</span><span class="sxs-lookup"><span data-stu-id="13996-1632">A keyword from Keyword_card_expiration_terms_dict is found.</span></span>
    - <span data-ttu-id="13996-1633">La funzione Func_expiration_date rileva una data nel formato corretto.</span><span class="sxs-lookup"><span data-stu-id="13996-1633">The function Func_expiration_date finds a date in the right date format.</span></span>
- <span data-ttu-id="13996-1634">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="13996-1634">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="13996-1635">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="13996-1635">Keywords</span></span>

#### <a name="keywordeudebitcard"></a><span data-ttu-id="13996-1636">Keyword_eu_debit_card</span><span class="sxs-lookup"><span data-stu-id="13996-1636">Keyword_eu_debit_card</span></span>

- <span data-ttu-id="13996-1637">account number</span><span class="sxs-lookup"><span data-stu-id="13996-1637">account number</span></span> 
- <span data-ttu-id="13996-1638">card number</span><span class="sxs-lookup"><span data-stu-id="13996-1638">card number</span></span> 
- <span data-ttu-id="13996-1639">card no.</span><span class="sxs-lookup"><span data-stu-id="13996-1639">card no.</span></span> 
- <span data-ttu-id="13996-1640">security number</span><span class="sxs-lookup"><span data-stu-id="13996-1640">security number</span></span> 
- <span data-ttu-id="13996-1641">CC</span><span class="sxs-lookup"><span data-stu-id="13996-1641">cc#</span></span> 

#### <a name="keywordcardtermsdict"></a><span data-ttu-id="13996-1642">Keyword_card_terms_dict</span><span class="sxs-lookup"><span data-stu-id="13996-1642">Keyword_card_terms_dict</span></span>

- <span data-ttu-id="13996-1643">acct nbr</span><span class="sxs-lookup"><span data-stu-id="13996-1643">acct nbr</span></span> 
- <span data-ttu-id="13996-1644">acct num</span><span class="sxs-lookup"><span data-stu-id="13996-1644">acct num</span></span> 
- <span data-ttu-id="13996-1645">acct no</span><span class="sxs-lookup"><span data-stu-id="13996-1645">acct no</span></span> 
- <span data-ttu-id="13996-1646">american express</span><span class="sxs-lookup"><span data-stu-id="13996-1646">american express</span></span> 
- <span data-ttu-id="13996-1647">AmericanExpress</span><span class="sxs-lookup"><span data-stu-id="13996-1647">americanexpress</span></span> 
- <span data-ttu-id="13996-1648">americano espresso</span><span class="sxs-lookup"><span data-stu-id="13996-1648">americano espresso</span></span> 
- <span data-ttu-id="13996-1649">Amex</span><span class="sxs-lookup"><span data-stu-id="13996-1649">amex</span></span> 
- <span data-ttu-id="13996-1650">atm card</span><span class="sxs-lookup"><span data-stu-id="13996-1650">atm card</span></span> 
- <span data-ttu-id="13996-1651">atm cards</span><span class="sxs-lookup"><span data-stu-id="13996-1651">atm cards</span></span> 
- <span data-ttu-id="13996-1652">atm kaart</span><span class="sxs-lookup"><span data-stu-id="13996-1652">atm kaart</span></span> 
- <span data-ttu-id="13996-1653">atmcard</span><span class="sxs-lookup"><span data-stu-id="13996-1653">atmcard</span></span> 
- <span data-ttu-id="13996-1654">atmcards</span><span class="sxs-lookup"><span data-stu-id="13996-1654">atmcards</span></span> 
- <span data-ttu-id="13996-1655">atmkaart</span><span class="sxs-lookup"><span data-stu-id="13996-1655">atmkaart</span></span> 
- <span data-ttu-id="13996-1656">atmkaarten</span><span class="sxs-lookup"><span data-stu-id="13996-1656">atmkaarten</span></span> 
- <span data-ttu-id="13996-1657">Bancontact</span><span class="sxs-lookup"><span data-stu-id="13996-1657">bancontact</span></span> 
- <span data-ttu-id="13996-1658">bank card</span><span class="sxs-lookup"><span data-stu-id="13996-1658">bank card</span></span> 
- <span data-ttu-id="13996-1659">bankkaart</span><span class="sxs-lookup"><span data-stu-id="13996-1659">bankkaart</span></span> 
- <span data-ttu-id="13996-1660">card holder</span><span class="sxs-lookup"><span data-stu-id="13996-1660">card holder</span></span> 
- <span data-ttu-id="13996-1661">card holders</span><span class="sxs-lookup"><span data-stu-id="13996-1661">card holders</span></span> 
- <span data-ttu-id="13996-1662">card num</span><span class="sxs-lookup"><span data-stu-id="13996-1662">card num</span></span> 
- <span data-ttu-id="13996-1663">card number</span><span class="sxs-lookup"><span data-stu-id="13996-1663">card number</span></span> 
- <span data-ttu-id="13996-1664">card numbers</span><span class="sxs-lookup"><span data-stu-id="13996-1664">card numbers</span></span> 
- <span data-ttu-id="13996-1665">card type</span><span class="sxs-lookup"><span data-stu-id="13996-1665">card type</span></span> 
- <span data-ttu-id="13996-1666">cardano numerico</span><span class="sxs-lookup"><span data-stu-id="13996-1666">cardano numerico</span></span> 
- <span data-ttu-id="13996-1667">titolare</span><span class="sxs-lookup"><span data-stu-id="13996-1667">cardholder</span></span> 
- <span data-ttu-id="13996-1668">titolari</span><span class="sxs-lookup"><span data-stu-id="13996-1668">cardholders</span></span> 
- <span data-ttu-id="13996-1669">CardNumber</span><span class="sxs-lookup"><span data-stu-id="13996-1669">cardnumber</span></span> 
- <span data-ttu-id="13996-1670">cardnumbers</span><span class="sxs-lookup"><span data-stu-id="13996-1670">cardnumbers</span></span> 
- <span data-ttu-id="13996-1671">carta bianca</span><span class="sxs-lookup"><span data-stu-id="13996-1671">carta bianca</span></span> 
- <span data-ttu-id="13996-1672">carta credito</span><span class="sxs-lookup"><span data-stu-id="13996-1672">carta credito</span></span> 
- <span data-ttu-id="13996-1673">carta di credito</span><span class="sxs-lookup"><span data-stu-id="13996-1673">carta di credito</span></span> 
- <span data-ttu-id="13996-1674">cartao de credito</span><span class="sxs-lookup"><span data-stu-id="13996-1674">cartao de credito</span></span> 
- <span data-ttu-id="13996-1675">cartao de crédito</span><span class="sxs-lookup"><span data-stu-id="13996-1675">cartao de crédito</span></span> 
- <span data-ttu-id="13996-1676">cartao de debito</span><span class="sxs-lookup"><span data-stu-id="13996-1676">cartao de debito</span></span> 
- <span data-ttu-id="13996-1677">○cartao de débito</span><span class="sxs-lookup"><span data-stu-id="13996-1677">cartao de débito</span></span> 
- <span data-ttu-id="13996-1678">carte bancaire</span><span class="sxs-lookup"><span data-stu-id="13996-1678">carte bancaire</span></span> 
- <span data-ttu-id="13996-1679">carte blanche</span><span class="sxs-lookup"><span data-stu-id="13996-1679">carte blanche</span></span> 
- <span data-ttu-id="13996-1680">carte bleue</span><span class="sxs-lookup"><span data-stu-id="13996-1680">carte bleue</span></span> 
- <span data-ttu-id="13996-1681">carte de credit</span><span class="sxs-lookup"><span data-stu-id="13996-1681">carte de credit</span></span> 
- <span data-ttu-id="13996-1682">carte de crédit</span><span class="sxs-lookup"><span data-stu-id="13996-1682">carte de crédit</span></span> 
- <span data-ttu-id="13996-1683">carte di credito</span><span class="sxs-lookup"><span data-stu-id="13996-1683">carte di credito</span></span> 
- <span data-ttu-id="13996-1684">CarteBlanche</span><span class="sxs-lookup"><span data-stu-id="13996-1684">carteblanche</span></span> 
- <span data-ttu-id="13996-1685">cartão de credito</span><span class="sxs-lookup"><span data-stu-id="13996-1685">cartão de credito</span></span> 
- <span data-ttu-id="13996-1686">cartão de crédito</span><span class="sxs-lookup"><span data-stu-id="13996-1686">cartão de crédito</span></span> 
- <span data-ttu-id="13996-1687">cartão de debito</span><span class="sxs-lookup"><span data-stu-id="13996-1687">cartão de debito</span></span> 
- <span data-ttu-id="13996-1688">cartão de débito</span><span class="sxs-lookup"><span data-stu-id="13996-1688">cartão de débito</span></span> 
- <span data-ttu-id="13996-1689">CB</span><span class="sxs-lookup"><span data-stu-id="13996-1689">cb</span></span> 
- <span data-ttu-id="13996-1690">Ccn</span><span class="sxs-lookup"><span data-stu-id="13996-1690">ccn</span></span> 
- <span data-ttu-id="13996-1691">check card</span><span class="sxs-lookup"><span data-stu-id="13996-1691">check card</span></span> 
- <span data-ttu-id="13996-1692">check cards</span><span class="sxs-lookup"><span data-stu-id="13996-1692">check cards</span></span> 
- <span data-ttu-id="13996-1693">checkcard</span><span class="sxs-lookup"><span data-stu-id="13996-1693">checkcard</span></span>
- <span data-ttu-id="13996-1694">checkcards</span><span class="sxs-lookup"><span data-stu-id="13996-1694">checkcards</span></span> 
- <span data-ttu-id="13996-1695">chequekaart</span><span class="sxs-lookup"><span data-stu-id="13996-1695">chequekaart</span></span> 
- <span data-ttu-id="13996-1696">Cirrus</span><span class="sxs-lookup"><span data-stu-id="13996-1696">cirrus</span></span> 
- <span data-ttu-id="13996-1697">Cirrus-Edc-Maestro</span><span class="sxs-lookup"><span data-stu-id="13996-1697">cirrus-edc-maestro</span></span> 
- <span data-ttu-id="13996-1698">controlekaart</span><span class="sxs-lookup"><span data-stu-id="13996-1698">controlekaart</span></span> 
- <span data-ttu-id="13996-1699">controlekaarten</span><span class="sxs-lookup"><span data-stu-id="13996-1699">controlekaarten</span></span> 
- <span data-ttu-id="13996-1700">credit card</span><span class="sxs-lookup"><span data-stu-id="13996-1700">credit card</span></span> 
- <span data-ttu-id="13996-1701">credit cards</span><span class="sxs-lookup"><span data-stu-id="13996-1701">credit cards</span></span> 
- <span data-ttu-id="13996-1702">CreditCard</span><span class="sxs-lookup"><span data-stu-id="13996-1702">creditcard</span></span> 
- <span data-ttu-id="13996-1703">creditcards.com</span><span class="sxs-lookup"><span data-stu-id="13996-1703">creditcards</span></span> 
- <span data-ttu-id="13996-1704">debetkaart</span><span class="sxs-lookup"><span data-stu-id="13996-1704">debetkaart</span></span> 
- <span data-ttu-id="13996-1705">carte</span><span class="sxs-lookup"><span data-stu-id="13996-1705">debetkaarten</span></span> 
- <span data-ttu-id="13996-1706">debit card</span><span class="sxs-lookup"><span data-stu-id="13996-1706">debit card</span></span> 
- <span data-ttu-id="13996-1707">debit cards</span><span class="sxs-lookup"><span data-stu-id="13996-1707">debit cards</span></span> 
- <span data-ttu-id="13996-1708">debitcard</span><span class="sxs-lookup"><span data-stu-id="13996-1708">debitcard</span></span> 
- <span data-ttu-id="13996-1709">debitcards</span><span class="sxs-lookup"><span data-stu-id="13996-1709">debitcards</span></span> 
- <span data-ttu-id="13996-1710">debito automatico</span><span class="sxs-lookup"><span data-stu-id="13996-1710">debito automatico</span></span> 
- <span data-ttu-id="13996-1711">diners club</span><span class="sxs-lookup"><span data-stu-id="13996-1711">diners club</span></span> 
- <span data-ttu-id="13996-1712">DinersClub</span><span class="sxs-lookup"><span data-stu-id="13996-1712">dinersclub</span></span> 
- <span data-ttu-id="13996-1713">individuare</span><span class="sxs-lookup"><span data-stu-id="13996-1713">discover</span></span> 
- <span data-ttu-id="13996-1714">discover card</span><span class="sxs-lookup"><span data-stu-id="13996-1714">discover card</span></span> 
- <span data-ttu-id="13996-1715">discover cards</span><span class="sxs-lookup"><span data-stu-id="13996-1715">discover cards</span></span> 
- <span data-ttu-id="13996-1716">discovercard</span><span class="sxs-lookup"><span data-stu-id="13996-1716">discovercard</span></span> 
- <span data-ttu-id="13996-1717">discovercards</span><span class="sxs-lookup"><span data-stu-id="13996-1717">discovercards</span></span> 
- <span data-ttu-id="13996-1718">débito automático</span><span class="sxs-lookup"><span data-stu-id="13996-1718">débito automático</span></span>
- <span data-ttu-id="13996-1719">EDC</span><span class="sxs-lookup"><span data-stu-id="13996-1719">edc</span></span> 
- <span data-ttu-id="13996-1720">eigentümername</span><span class="sxs-lookup"><span data-stu-id="13996-1720">eigentümername</span></span> 
- <span data-ttu-id="13996-1721">european debit card</span><span class="sxs-lookup"><span data-stu-id="13996-1721">european debit card</span></span> 
- <span data-ttu-id="13996-1722">hoofdkaart</span><span class="sxs-lookup"><span data-stu-id="13996-1722">hoofdkaart</span></span> 
- <span data-ttu-id="13996-1723">hoofdkaarten</span><span class="sxs-lookup"><span data-stu-id="13996-1723">hoofdkaarten</span></span> 
- <span data-ttu-id="13996-1724">in viaggio</span><span class="sxs-lookup"><span data-stu-id="13996-1724">in viaggio</span></span> 
- <span data-ttu-id="13996-1725">japanese card bureau</span><span class="sxs-lookup"><span data-stu-id="13996-1725">japanese card bureau</span></span> 
- <span data-ttu-id="13996-1726">japanse kaartdienst</span><span class="sxs-lookup"><span data-stu-id="13996-1726">japanse kaartdienst</span></span> 
- <span data-ttu-id="13996-1727">JCB</span><span class="sxs-lookup"><span data-stu-id="13996-1727">jcb</span></span> 
- <span data-ttu-id="13996-1728">kaart</span><span class="sxs-lookup"><span data-stu-id="13996-1728">kaart</span></span> 
- <span data-ttu-id="13996-1729">kaart num</span><span class="sxs-lookup"><span data-stu-id="13996-1729">kaart num</span></span> 
- <span data-ttu-id="13996-1730">kaartaantal</span><span class="sxs-lookup"><span data-stu-id="13996-1730">kaartaantal</span></span> 
- <span data-ttu-id="13996-1731">kaartaantallen</span><span class="sxs-lookup"><span data-stu-id="13996-1731">kaartaantallen</span></span> 
- <span data-ttu-id="13996-1732">kaarthouder</span><span class="sxs-lookup"><span data-stu-id="13996-1732">kaarthouder</span></span> 
- <span data-ttu-id="13996-1733">kaarthouders</span><span class="sxs-lookup"><span data-stu-id="13996-1733">kaarthouders</span></span> 
- <span data-ttu-id="13996-1734">Karte</span><span class="sxs-lookup"><span data-stu-id="13996-1734">karte</span></span>  
- <span data-ttu-id="13996-1735">Karteninhaber</span><span class="sxs-lookup"><span data-stu-id="13996-1735">karteninhaber</span></span> 
- <span data-ttu-id="13996-1736">karteninhabers</span><span class="sxs-lookup"><span data-stu-id="13996-1736">karteninhabers</span></span>
- <span data-ttu-id="13996-1737">kartennr</span><span class="sxs-lookup"><span data-stu-id="13996-1737">kartennr</span></span> 
- <span data-ttu-id="13996-1738">kartennummer</span><span class="sxs-lookup"><span data-stu-id="13996-1738">kartennummer</span></span> 
- <span data-ttu-id="13996-1739">Kreditkarte</span><span class="sxs-lookup"><span data-stu-id="13996-1739">kreditkarte</span></span> 
- <span data-ttu-id="13996-1740">Kreditkarten-Nummer</span><span class="sxs-lookup"><span data-stu-id="13996-1740">kreditkarten-nummer</span></span> 
- <span data-ttu-id="13996-1741">kreditkarteninhaber</span><span class="sxs-lookup"><span data-stu-id="13996-1741">kreditkarteninhaber</span></span> 
- <span data-ttu-id="13996-1742">Kreditkarteninstitut</span><span class="sxs-lookup"><span data-stu-id="13996-1742">kreditkarteninstitut</span></span> 
- <span data-ttu-id="13996-1743">kreditkartennummer</span><span class="sxs-lookup"><span data-stu-id="13996-1743">kreditkartennummer</span></span> 
- <span data-ttu-id="13996-1744">kreditkartentyp</span><span class="sxs-lookup"><span data-stu-id="13996-1744">kreditkartentyp</span></span> 
- <span data-ttu-id="13996-1745">Maestro</span><span class="sxs-lookup"><span data-stu-id="13996-1745">maestro</span></span> 
- <span data-ttu-id="13996-1746">master card</span><span class="sxs-lookup"><span data-stu-id="13996-1746">master card</span></span> 
- <span data-ttu-id="13996-1747">master cards</span><span class="sxs-lookup"><span data-stu-id="13996-1747">master cards</span></span> 
- <span data-ttu-id="13996-1748">Mastercard</span><span class="sxs-lookup"><span data-stu-id="13996-1748">mastercard</span></span> 
- <span data-ttu-id="13996-1749">Mastercard</span><span class="sxs-lookup"><span data-stu-id="13996-1749">mastercards</span></span> 
- <span data-ttu-id="13996-1750">MC</span><span class="sxs-lookup"><span data-stu-id="13996-1750">mc</span></span> 
- <span data-ttu-id="13996-1751">mister cash</span><span class="sxs-lookup"><span data-stu-id="13996-1751">mister cash</span></span> 
- <span data-ttu-id="13996-1752">n carta</span><span class="sxs-lookup"><span data-stu-id="13996-1752">n carta</span></span> 
- <span data-ttu-id="13996-1753">carta</span><span class="sxs-lookup"><span data-stu-id="13996-1753">carta</span></span> 
- <span data-ttu-id="13996-1754">no de tarjeta</span><span class="sxs-lookup"><span data-stu-id="13996-1754">no de tarjeta</span></span> 
- <span data-ttu-id="13996-1755">no do cartao</span><span class="sxs-lookup"><span data-stu-id="13996-1755">no do cartao</span></span> 
- <span data-ttu-id="13996-1756">no do cartão</span><span class="sxs-lookup"><span data-stu-id="13996-1756">no do cartão</span></span> 
- <span data-ttu-id="13996-1757">No.</span><span class="sxs-lookup"><span data-stu-id="13996-1757">no.</span></span> <span data-ttu-id="13996-1758">de tarjeta</span><span class="sxs-lookup"><span data-stu-id="13996-1758">de tarjeta</span></span> 
- <span data-ttu-id="13996-1759">No.</span><span class="sxs-lookup"><span data-stu-id="13996-1759">no.</span></span> <span data-ttu-id="13996-1760">do cartao</span><span class="sxs-lookup"><span data-stu-id="13996-1760">do cartao</span></span> 
- <span data-ttu-id="13996-1761">No.</span><span class="sxs-lookup"><span data-stu-id="13996-1761">no.</span></span> <span data-ttu-id="13996-1762">do cartão</span><span class="sxs-lookup"><span data-stu-id="13996-1762">do cartão</span></span> 
- <span data-ttu-id="13996-1763">nr carta</span><span class="sxs-lookup"><span data-stu-id="13996-1763">nr carta</span></span> 
- <span data-ttu-id="13996-1764">Nr.</span><span class="sxs-lookup"><span data-stu-id="13996-1764">nr.</span></span> <span data-ttu-id="13996-1765">carta</span><span class="sxs-lookup"><span data-stu-id="13996-1765">carta</span></span> 
- <span data-ttu-id="13996-1766">numeri di scheda</span><span class="sxs-lookup"><span data-stu-id="13996-1766">numeri di scheda</span></span> 
- <span data-ttu-id="13996-1767">numero carta</span><span class="sxs-lookup"><span data-stu-id="13996-1767">numero carta</span></span> 
- <span data-ttu-id="13996-1768">numero de cartao</span><span class="sxs-lookup"><span data-stu-id="13996-1768">numero de cartao</span></span> 
- <span data-ttu-id="13996-1769">numero de carte</span><span class="sxs-lookup"><span data-stu-id="13996-1769">numero de carte</span></span> 
- <span data-ttu-id="13996-1770">numero de cartão</span><span class="sxs-lookup"><span data-stu-id="13996-1770">numero de cartão</span></span> 
- <span data-ttu-id="13996-1771">numero de tarjeta</span><span class="sxs-lookup"><span data-stu-id="13996-1771">numero de tarjeta</span></span>
- <span data-ttu-id="13996-1772">numero della carta</span><span class="sxs-lookup"><span data-stu-id="13996-1772">numero della carta</span></span> 
- <span data-ttu-id="13996-1773">numero di carta</span><span class="sxs-lookup"><span data-stu-id="13996-1773">numero di carta</span></span> 
- <span data-ttu-id="13996-1774">numero di scheda</span><span class="sxs-lookup"><span data-stu-id="13996-1774">numero di scheda</span></span> 
- <span data-ttu-id="13996-1775">numero do cartao</span><span class="sxs-lookup"><span data-stu-id="13996-1775">numero do cartao</span></span> 
- <span data-ttu-id="13996-1776">numero do cartão</span><span class="sxs-lookup"><span data-stu-id="13996-1776">numero do cartão</span></span> 
- <span data-ttu-id="13996-1777">numéro de carte</span><span class="sxs-lookup"><span data-stu-id="13996-1777">numéro de carte</span></span> 
- <span data-ttu-id="13996-1778">nº carta</span><span class="sxs-lookup"><span data-stu-id="13996-1778">nº carta</span></span> 
- <span data-ttu-id="13996-1779">nº de carte</span><span class="sxs-lookup"><span data-stu-id="13996-1779">nº de carte</span></span> 
- <span data-ttu-id="13996-1780">nº de la carte</span><span class="sxs-lookup"><span data-stu-id="13996-1780">nº de la carte</span></span> 
- <span data-ttu-id="13996-1781">nº de tarjeta</span><span class="sxs-lookup"><span data-stu-id="13996-1781">nº de tarjeta</span></span> 
- <span data-ttu-id="13996-1782">nº do cartao</span><span class="sxs-lookup"><span data-stu-id="13996-1782">nº do cartao</span></span> 
- <span data-ttu-id="13996-1783">nº do cartão</span><span class="sxs-lookup"><span data-stu-id="13996-1783">nº do cartão</span></span> 
- <span data-ttu-id="13996-1784">n º.</span><span class="sxs-lookup"><span data-stu-id="13996-1784">nº.</span></span> <span data-ttu-id="13996-1785">do cartão</span><span class="sxs-lookup"><span data-stu-id="13996-1785">do cartão</span></span> 
- <span data-ttu-id="13996-1786">número de cartao</span><span class="sxs-lookup"><span data-stu-id="13996-1786">número de cartao</span></span> 
- <span data-ttu-id="13996-1787">número de cartão</span><span class="sxs-lookup"><span data-stu-id="13996-1787">número de cartão</span></span> 
- <span data-ttu-id="13996-1788">número de tarjeta</span><span class="sxs-lookup"><span data-stu-id="13996-1788">número de tarjeta</span></span> 
- <span data-ttu-id="13996-1789">número do cartao</span><span class="sxs-lookup"><span data-stu-id="13996-1789">número do cartao</span></span> 
- <span data-ttu-id="13996-1790">scheda dell'assegno</span><span class="sxs-lookup"><span data-stu-id="13996-1790">scheda dell'assegno</span></span> 
- <span data-ttu-id="13996-1791">scheda dell'atmosfera</span><span class="sxs-lookup"><span data-stu-id="13996-1791">scheda dell'atmosfera</span></span> 
- <span data-ttu-id="13996-1792">scheda dell'atmosfera</span><span class="sxs-lookup"><span data-stu-id="13996-1792">scheda dell'atmosfera</span></span> 
- <span data-ttu-id="13996-1793">scheda della banca</span><span class="sxs-lookup"><span data-stu-id="13996-1793">scheda della banca</span></span> 
- <span data-ttu-id="13996-1794">scheda di controllo</span><span class="sxs-lookup"><span data-stu-id="13996-1794">scheda di controllo</span></span> 
- <span data-ttu-id="13996-1795">scheda di debito</span><span class="sxs-lookup"><span data-stu-id="13996-1795">scheda di debito</span></span> 
- <span data-ttu-id="13996-1796">scheda matrice</span><span class="sxs-lookup"><span data-stu-id="13996-1796">scheda matrice</span></span> 
- <span data-ttu-id="13996-1797">schede dell'atmosfera</span><span class="sxs-lookup"><span data-stu-id="13996-1797">schede dell'atmosfera</span></span> 
- <span data-ttu-id="13996-1798">schede di controllo</span><span class="sxs-lookup"><span data-stu-id="13996-1798">schede di controllo</span></span> 
- <span data-ttu-id="13996-1799">schede di debito</span><span class="sxs-lookup"><span data-stu-id="13996-1799">schede di debito</span></span> 
- <span data-ttu-id="13996-1800">schede matrici</span><span class="sxs-lookup"><span data-stu-id="13996-1800">schede matrici</span></span> 
- <span data-ttu-id="13996-1801">scoprono la scheda</span><span class="sxs-lookup"><span data-stu-id="13996-1801">scoprono la scheda</span></span> 
- <span data-ttu-id="13996-1802">scoprono le schede</span><span class="sxs-lookup"><span data-stu-id="13996-1802">scoprono le schede</span></span> 
- <span data-ttu-id="13996-1803">solo</span><span class="sxs-lookup"><span data-stu-id="13996-1803">solo</span></span> 
- <span data-ttu-id="13996-1804">supporti di scheda</span><span class="sxs-lookup"><span data-stu-id="13996-1804">supporti di scheda</span></span> 
- <span data-ttu-id="13996-1805">supporto di scheda</span><span class="sxs-lookup"><span data-stu-id="13996-1805">supporto di scheda</span></span> 
- <span data-ttu-id="13996-1806">opzione</span><span class="sxs-lookup"><span data-stu-id="13996-1806">switch</span></span> 
- <span data-ttu-id="13996-1807">tarjeta atm</span><span class="sxs-lookup"><span data-stu-id="13996-1807">tarjeta atm</span></span> 
- <span data-ttu-id="13996-1808">tarjeta credito</span><span class="sxs-lookup"><span data-stu-id="13996-1808">tarjeta credito</span></span> 
- <span data-ttu-id="13996-1809">tarjeta de atm</span><span class="sxs-lookup"><span data-stu-id="13996-1809">tarjeta de atm</span></span> 
- <span data-ttu-id="13996-1810">tarjeta de credito</span><span class="sxs-lookup"><span data-stu-id="13996-1810">tarjeta de credito</span></span> 
- <span data-ttu-id="13996-1811">tarjeta de debito</span><span class="sxs-lookup"><span data-stu-id="13996-1811">tarjeta de debito</span></span> 
- <span data-ttu-id="13996-1812">tarjeta debito</span><span class="sxs-lookup"><span data-stu-id="13996-1812">tarjeta debito</span></span> 
- <span data-ttu-id="13996-1813">tarjeta no</span><span class="sxs-lookup"><span data-stu-id="13996-1813">tarjeta no</span></span>
- <span data-ttu-id="13996-1814">tarjetahabiente</span><span class="sxs-lookup"><span data-stu-id="13996-1814">tarjetahabiente</span></span> 
- <span data-ttu-id="13996-1815">tipo della scheda</span><span class="sxs-lookup"><span data-stu-id="13996-1815">tipo della scheda</span></span> 
- <span data-ttu-id="13996-1816">ufficio giapponese della</span><span class="sxs-lookup"><span data-stu-id="13996-1816">ufficio giapponese della</span></span> 
- <span data-ttu-id="13996-1817">scheda</span><span class="sxs-lookup"><span data-stu-id="13996-1817">scheda</span></span> 
- <span data-ttu-id="13996-1818">v pay</span><span class="sxs-lookup"><span data-stu-id="13996-1818">v pay</span></span> 
- <span data-ttu-id="13996-1819">v-pay</span><span class="sxs-lookup"><span data-stu-id="13996-1819">v-pay</span></span> 
- <span data-ttu-id="13996-1820">esempio</span><span class="sxs-lookup"><span data-stu-id="13996-1820">visa</span></span> 
- <span data-ttu-id="13996-1821">visa plus</span><span class="sxs-lookup"><span data-stu-id="13996-1821">visa plus</span></span> 
- <span data-ttu-id="13996-1822">visa electron</span><span class="sxs-lookup"><span data-stu-id="13996-1822">visa electron</span></span> 
- <span data-ttu-id="13996-1823">visto</span><span class="sxs-lookup"><span data-stu-id="13996-1823">visto</span></span> 
- <span data-ttu-id="13996-1824">Visum</span><span class="sxs-lookup"><span data-stu-id="13996-1824">visum</span></span> 
- <span data-ttu-id="13996-1825">vpay</span><span class="sxs-lookup"><span data-stu-id="13996-1825">vpay</span></span>   

#### <a name="keywordcardsecuritytermsdict"></a><span data-ttu-id="13996-1826">Keyword_card_security_terms_dict</span><span class="sxs-lookup"><span data-stu-id="13996-1826">Keyword_card_security_terms_dict</span></span>

- <span data-ttu-id="13996-1827">card identification number</span><span class="sxs-lookup"><span data-stu-id="13996-1827">card identification number</span></span>
- <span data-ttu-id="13996-1828">card verification</span><span class="sxs-lookup"><span data-stu-id="13996-1828">card verification</span></span> 
- <span data-ttu-id="13996-1829">cardi la verifica</span><span class="sxs-lookup"><span data-stu-id="13996-1829">cardi la verifica</span></span> 
- <span data-ttu-id="13996-1830">ID</span><span class="sxs-lookup"><span data-stu-id="13996-1830">cid</span></span> 
- <span data-ttu-id="13996-1831">cod seg</span><span class="sxs-lookup"><span data-stu-id="13996-1831">cod seg</span></span> 
- <span data-ttu-id="13996-1832">cod seguranca</span><span class="sxs-lookup"><span data-stu-id="13996-1832">cod seguranca</span></span> 
- <span data-ttu-id="13996-1833">cod segurança</span><span class="sxs-lookup"><span data-stu-id="13996-1833">cod segurança</span></span> 
- <span data-ttu-id="13996-1834">cod sicurezza</span><span class="sxs-lookup"><span data-stu-id="13996-1834">cod sicurezza</span></span> 
- <span data-ttu-id="13996-1835">Cod.</span><span class="sxs-lookup"><span data-stu-id="13996-1835">cod.</span></span> <span data-ttu-id="13996-1836">SEG</span><span class="sxs-lookup"><span data-stu-id="13996-1836">seg</span></span> 
- <span data-ttu-id="13996-1837">Cod.</span><span class="sxs-lookup"><span data-stu-id="13996-1837">cod.</span></span> <span data-ttu-id="13996-1838">seguranca</span><span class="sxs-lookup"><span data-stu-id="13996-1838">seguranca</span></span> 
- <span data-ttu-id="13996-1839">Cod.</span><span class="sxs-lookup"><span data-stu-id="13996-1839">cod.</span></span> <span data-ttu-id="13996-1840">Segurança</span><span class="sxs-lookup"><span data-stu-id="13996-1840">segurança</span></span> 
- <span data-ttu-id="13996-1841">Cod.</span><span class="sxs-lookup"><span data-stu-id="13996-1841">cod.</span></span> <span data-ttu-id="13996-1842">sicurezza</span><span class="sxs-lookup"><span data-stu-id="13996-1842">sicurezza</span></span> 
- <span data-ttu-id="13996-1843">codice di sicurezza</span><span class="sxs-lookup"><span data-stu-id="13996-1843">codice di sicurezza</span></span> 
- <span data-ttu-id="13996-1844">codice di verifica</span><span class="sxs-lookup"><span data-stu-id="13996-1844">codice di verifica</span></span> 
- <span data-ttu-id="13996-1845">Codigo</span><span class="sxs-lookup"><span data-stu-id="13996-1845">codigo</span></span> 
- <span data-ttu-id="13996-1846">codigo de seguranca</span><span class="sxs-lookup"><span data-stu-id="13996-1846">codigo de seguranca</span></span> 
- <span data-ttu-id="13996-1847">codigo de segurança</span><span class="sxs-lookup"><span data-stu-id="13996-1847">codigo de segurança</span></span> 
- <span data-ttu-id="13996-1848">crittogramma</span><span class="sxs-lookup"><span data-stu-id="13996-1848">crittogramma</span></span> 
- <span data-ttu-id="13996-1849">crittogramma</span><span class="sxs-lookup"><span data-stu-id="13996-1849">cryptogram</span></span> 
- <span data-ttu-id="13996-1850">cryptogramme</span><span class="sxs-lookup"><span data-stu-id="13996-1850">cryptogramme</span></span> 
- <span data-ttu-id="13996-1851">CV2</span><span class="sxs-lookup"><span data-stu-id="13996-1851">cv2</span></span> 
- <span data-ttu-id="13996-1852">CVC</span><span class="sxs-lookup"><span data-stu-id="13996-1852">cvc</span></span> 
- <span data-ttu-id="13996-1853">CVC2</span><span class="sxs-lookup"><span data-stu-id="13996-1853">cvc2</span></span> 
- <span data-ttu-id="13996-1854">CVN</span><span class="sxs-lookup"><span data-stu-id="13996-1854">cvn</span></span> 
- <span data-ttu-id="13996-1855">CVV</span><span class="sxs-lookup"><span data-stu-id="13996-1855">cvv</span></span> 
- <span data-ttu-id="13996-1856">CVV2</span><span class="sxs-lookup"><span data-stu-id="13996-1856">cvv2</span></span> 
- <span data-ttu-id="13996-1857">cód seguranca</span><span class="sxs-lookup"><span data-stu-id="13996-1857">cód seguranca</span></span> 
- <span data-ttu-id="13996-1858">cód segurança</span><span class="sxs-lookup"><span data-stu-id="13996-1858">cód segurança</span></span> 
- <span data-ttu-id="13996-1859">cód.</span><span class="sxs-lookup"><span data-stu-id="13996-1859">cód.</span></span> <span data-ttu-id="13996-1860">seguranca</span><span class="sxs-lookup"><span data-stu-id="13996-1860">seguranca</span></span> 
- <span data-ttu-id="13996-1861">cód.</span><span class="sxs-lookup"><span data-stu-id="13996-1861">cód.</span></span> <span data-ttu-id="13996-1862">Segurança</span><span class="sxs-lookup"><span data-stu-id="13996-1862">segurança</span></span> 
- <span data-ttu-id="13996-1863">Código</span><span class="sxs-lookup"><span data-stu-id="13996-1863">código</span></span> 
- <span data-ttu-id="13996-1864">código de seguranca</span><span class="sxs-lookup"><span data-stu-id="13996-1864">código de seguranca</span></span> 
- <span data-ttu-id="13996-1865">código de segurança</span><span class="sxs-lookup"><span data-stu-id="13996-1865">código de segurança</span></span> 
- <span data-ttu-id="13996-1866">de kaart controle</span><span class="sxs-lookup"><span data-stu-id="13996-1866">de kaart controle</span></span> 
- <span data-ttu-id="13996-1867">geeft nr uit</span><span class="sxs-lookup"><span data-stu-id="13996-1867">geeft nr uit</span></span> 
- <span data-ttu-id="13996-1868">issue no</span><span class="sxs-lookup"><span data-stu-id="13996-1868">issue no</span></span> 
- <span data-ttu-id="13996-1869">issue number</span><span class="sxs-lookup"><span data-stu-id="13996-1869">issue number</span></span> 
- <span data-ttu-id="13996-1870">kaartidentificatienummer</span><span class="sxs-lookup"><span data-stu-id="13996-1870">kaartidentificatienummer</span></span> 
- <span data-ttu-id="13996-1871">kreditkartenprufnummer</span><span class="sxs-lookup"><span data-stu-id="13996-1871">kreditkartenprufnummer</span></span> 
- <span data-ttu-id="13996-1872">kreditkartenprüfnummer</span><span class="sxs-lookup"><span data-stu-id="13996-1872">kreditkartenprüfnummer</span></span> 
- <span data-ttu-id="13996-1873">kwestieaantal</span><span class="sxs-lookup"><span data-stu-id="13996-1873">kwestieaantal</span></span> 
- <span data-ttu-id="13996-1874">No.</span><span class="sxs-lookup"><span data-stu-id="13996-1874">no.</span></span> <span data-ttu-id="13996-1875">Dell'Edizione</span><span class="sxs-lookup"><span data-stu-id="13996-1875">dell'edizione</span></span> 
- <span data-ttu-id="13996-1876">No.</span><span class="sxs-lookup"><span data-stu-id="13996-1876">no.</span></span> <span data-ttu-id="13996-1877">di sicurezza</span><span class="sxs-lookup"><span data-stu-id="13996-1877">di sicurezza</span></span> 
- <span data-ttu-id="13996-1878">numero de securite</span><span class="sxs-lookup"><span data-stu-id="13996-1878">numero de securite</span></span> 
- <span data-ttu-id="13996-1879">numero de verificacao</span><span class="sxs-lookup"><span data-stu-id="13996-1879">numero de verificacao</span></span> 
- <span data-ttu-id="13996-1880">numero dell'edizione</span><span class="sxs-lookup"><span data-stu-id="13996-1880">numero dell'edizione</span></span> 
- <span data-ttu-id="13996-1881">numero di identificazione della</span><span class="sxs-lookup"><span data-stu-id="13996-1881">numero di identificazione della</span></span> 
- <span data-ttu-id="13996-1882">scheda</span><span class="sxs-lookup"><span data-stu-id="13996-1882">scheda</span></span> 
- <span data-ttu-id="13996-1883">numero di sicurezza</span><span class="sxs-lookup"><span data-stu-id="13996-1883">numero di sicurezza</span></span> 
- <span data-ttu-id="13996-1884">numero van veiligheid</span><span class="sxs-lookup"><span data-stu-id="13996-1884">numero van veiligheid</span></span> 
- <span data-ttu-id="13996-1885">numéro de sécurité</span><span class="sxs-lookup"><span data-stu-id="13996-1885">numéro de sécurité</span></span> 
- <span data-ttu-id="13996-1886">nº autorizzazione</span><span class="sxs-lookup"><span data-stu-id="13996-1886">nº autorizzazione</span></span> 
- <span data-ttu-id="13996-1887">número de verificação</span><span class="sxs-lookup"><span data-stu-id="13996-1887">número de verificação</span></span> 
- <span data-ttu-id="13996-1888">perno il blocco</span><span class="sxs-lookup"><span data-stu-id="13996-1888">perno il blocco</span></span> 
- <span data-ttu-id="13996-1889">pin block</span><span class="sxs-lookup"><span data-stu-id="13996-1889">pin block</span></span> 
- <span data-ttu-id="13996-1890">Prufziffer</span><span class="sxs-lookup"><span data-stu-id="13996-1890">prufziffer</span></span> 
- <span data-ttu-id="13996-1891">prüfziffer</span><span class="sxs-lookup"><span data-stu-id="13996-1891">prüfziffer</span></span> 
- <span data-ttu-id="13996-1892">security code</span><span class="sxs-lookup"><span data-stu-id="13996-1892">security code</span></span> 
- <span data-ttu-id="13996-1893">security no</span><span class="sxs-lookup"><span data-stu-id="13996-1893">security no</span></span> 
- <span data-ttu-id="13996-1894">security number</span><span class="sxs-lookup"><span data-stu-id="13996-1894">security number</span></span> 
- <span data-ttu-id="13996-1895">sicherheits kode</span><span class="sxs-lookup"><span data-stu-id="13996-1895">sicherheits kode</span></span> 
- <span data-ttu-id="13996-1896">Sicherheitscode</span><span class="sxs-lookup"><span data-stu-id="13996-1896">sicherheitscode</span></span> 
- <span data-ttu-id="13996-1897">sicherheitsnummer</span><span class="sxs-lookup"><span data-stu-id="13996-1897">sicherheitsnummer</span></span> 
- <span data-ttu-id="13996-1898">speldblok</span><span class="sxs-lookup"><span data-stu-id="13996-1898">speldblok</span></span> 
- <span data-ttu-id="13996-1899">veiligheid nr</span><span class="sxs-lookup"><span data-stu-id="13996-1899">veiligheid nr</span></span> 
- <span data-ttu-id="13996-1900">veiligheidsaantal</span><span class="sxs-lookup"><span data-stu-id="13996-1900">veiligheidsaantal</span></span> 
- <span data-ttu-id="13996-1901">Veiligheidscode</span><span class="sxs-lookup"><span data-stu-id="13996-1901">veiligheidscode</span></span> 
- <span data-ttu-id="13996-1902">veiligheidsnummer</span><span class="sxs-lookup"><span data-stu-id="13996-1902">veiligheidsnummer</span></span> 
- <span data-ttu-id="13996-1903">Verfalldatum</span><span class="sxs-lookup"><span data-stu-id="13996-1903">verfalldatum</span></span> 

#### <a name="keywordcardexpirationtermsdict"></a><span data-ttu-id="13996-1904">Keyword_card_expiration_terms_dict</span><span class="sxs-lookup"><span data-stu-id="13996-1904">Keyword_card_expiration_terms_dict</span></span>

- <span data-ttu-id="13996-1905">Ablauf</span><span class="sxs-lookup"><span data-stu-id="13996-1905">ablauf</span></span> 
- <span data-ttu-id="13996-1906">data de expiracao</span><span class="sxs-lookup"><span data-stu-id="13996-1906">data de expiracao</span></span> 
- <span data-ttu-id="13996-1907">data de expiração</span><span class="sxs-lookup"><span data-stu-id="13996-1907">data de expiração</span></span> 
- <span data-ttu-id="13996-1908">data del exp</span><span class="sxs-lookup"><span data-stu-id="13996-1908">data del exp</span></span> 
- <span data-ttu-id="13996-1909">data di exp</span><span class="sxs-lookup"><span data-stu-id="13996-1909">data di exp</span></span> 
- <span data-ttu-id="13996-1910">data di scadenza</span><span class="sxs-lookup"><span data-stu-id="13996-1910">data di scadenza</span></span> 
- <span data-ttu-id="13996-1911">data em que expira</span><span class="sxs-lookup"><span data-stu-id="13996-1911">data em que expira</span></span> 
- <span data-ttu-id="13996-1912">data scad</span><span class="sxs-lookup"><span data-stu-id="13996-1912">data scad</span></span> 
- <span data-ttu-id="13996-1913">data scadenza</span><span class="sxs-lookup"><span data-stu-id="13996-1913">data scadenza</span></span> 
- <span data-ttu-id="13996-1914">date de validité</span><span class="sxs-lookup"><span data-stu-id="13996-1914">date de validité</span></span> 
- <span data-ttu-id="13996-1915">datum afloop</span><span class="sxs-lookup"><span data-stu-id="13996-1915">datum afloop</span></span> 
- <span data-ttu-id="13996-1916">datum van exp</span><span class="sxs-lookup"><span data-stu-id="13996-1916">datum van exp</span></span> 
- <span data-ttu-id="13996-1917">de afloop</span><span class="sxs-lookup"><span data-stu-id="13996-1917">de afloop</span></span> 
- <span data-ttu-id="13996-1918">espira</span><span class="sxs-lookup"><span data-stu-id="13996-1918">espira</span></span> 
- <span data-ttu-id="13996-1919">espira</span><span class="sxs-lookup"><span data-stu-id="13996-1919">espira</span></span> 
- <span data-ttu-id="13996-1920">exp date</span><span class="sxs-lookup"><span data-stu-id="13996-1920">exp date</span></span> 
- <span data-ttu-id="13996-1921">exp datum</span><span class="sxs-lookup"><span data-stu-id="13996-1921">exp datum</span></span> 
- <span data-ttu-id="13996-1922">scadenza</span><span class="sxs-lookup"><span data-stu-id="13996-1922">expiration</span></span> 
- <span data-ttu-id="13996-1923">scadenza</span><span class="sxs-lookup"><span data-stu-id="13996-1923">expire</span></span> 
- <span data-ttu-id="13996-1924">scade</span><span class="sxs-lookup"><span data-stu-id="13996-1924">expires</span></span> 
- <span data-ttu-id="13996-1925">scadenza</span><span class="sxs-lookup"><span data-stu-id="13996-1925">expiry</span></span> 
- <span data-ttu-id="13996-1926">fecha de expiracion</span><span class="sxs-lookup"><span data-stu-id="13996-1926">fecha de expiracion</span></span> 
- <span data-ttu-id="13996-1927">fecha de venc</span><span class="sxs-lookup"><span data-stu-id="13996-1927">fecha de venc</span></span> 
- <span data-ttu-id="13996-1928">gultig bis</span><span class="sxs-lookup"><span data-stu-id="13996-1928">gultig bis</span></span> 
- <span data-ttu-id="13996-1929">gultigkeitsdatum</span><span class="sxs-lookup"><span data-stu-id="13996-1929">gultigkeitsdatum</span></span> 
- <span data-ttu-id="13996-1930">gültig bis</span><span class="sxs-lookup"><span data-stu-id="13996-1930">gültig bis</span></span> 
- <span data-ttu-id="13996-1931">gültigkeitsdatum</span><span class="sxs-lookup"><span data-stu-id="13996-1931">gültigkeitsdatum</span></span> 
- <span data-ttu-id="13996-1932">la scadenza</span><span class="sxs-lookup"><span data-stu-id="13996-1932">la scadenza</span></span> 
- <span data-ttu-id="13996-1933">scadenza</span><span class="sxs-lookup"><span data-stu-id="13996-1933">scadenza</span></span> 
- <span data-ttu-id="13996-1934">valable</span><span class="sxs-lookup"><span data-stu-id="13996-1934">valable</span></span> 
- <span data-ttu-id="13996-1935">validade</span><span class="sxs-lookup"><span data-stu-id="13996-1935">validade</span></span> 
- <span data-ttu-id="13996-1936">valido hasta</span><span class="sxs-lookup"><span data-stu-id="13996-1936">valido hasta</span></span> 
- <span data-ttu-id="13996-1937">Valor</span><span class="sxs-lookup"><span data-stu-id="13996-1937">valor</span></span> 
- <span data-ttu-id="13996-1938">venc</span><span class="sxs-lookup"><span data-stu-id="13996-1938">venc</span></span> 
- <span data-ttu-id="13996-1939">vencimento</span><span class="sxs-lookup"><span data-stu-id="13996-1939">vencimento</span></span> 
- <span data-ttu-id="13996-1940">vencimiento</span><span class="sxs-lookup"><span data-stu-id="13996-1940">vencimiento</span></span> 
- <span data-ttu-id="13996-1941">verloopt</span><span class="sxs-lookup"><span data-stu-id="13996-1941">verloopt</span></span> 
- <span data-ttu-id="13996-1942">vervaldag</span><span class="sxs-lookup"><span data-stu-id="13996-1942">vervaldag</span></span> 
- <span data-ttu-id="13996-1943">vervaldatum</span><span class="sxs-lookup"><span data-stu-id="13996-1943">vervaldatum</span></span> 
- <span data-ttu-id="13996-1944">VTO</span><span class="sxs-lookup"><span data-stu-id="13996-1944">vto</span></span> 
- <span data-ttu-id="13996-1945">válido hasta</span><span class="sxs-lookup"><span data-stu-id="13996-1945">válido hasta</span></span> 
   
## <a name="eu-drivers-license-number"></a><span data-ttu-id="13996-1946">Numero della patente di guida dell'Unione europea</span><span class="sxs-lookup"><span data-stu-id="13996-1946">EU Driver's License Number</span></span>

<span data-ttu-id="13996-1947">Per ulteriori informazioni, vedere [tipo di informazione sensibile al numero di patente dell'Unione europea](eu-driver-s-license-number.md).</span><span class="sxs-lookup"><span data-stu-id="13996-1947">To learn more, see [EU Driver's License Number sensitive information type](eu-driver-s-license-number.md).</span></span>
  
## <a name="eu-national-identification-number"></a><span data-ttu-id="13996-1948">Numero di identificazione nazionale dell'Unione europea</span><span class="sxs-lookup"><span data-stu-id="13996-1948">EU National Identification Number</span></span>

<span data-ttu-id="13996-1949">Per ulteriori informazioni, vedere [tipo di informazione riservata del numero di identificazione nazionale dell'Unione europea](eu-national-identification-number.md).</span><span class="sxs-lookup"><span data-stu-id="13996-1949">To learn more, see [EU National Identification Number sensitive information type](eu-national-identification-number.md).</span></span>
  
## <a name="eu-passport-number"></a><span data-ttu-id="13996-1950">Numero di passaporto EU</span><span class="sxs-lookup"><span data-stu-id="13996-1950">EU Passport Number</span></span>

<span data-ttu-id="13996-1951">Per ulteriori informazioni, vedere [tipo di informazione sensibile al numero di passaporto dell'Unione europea](eu-passport-number.md).</span><span class="sxs-lookup"><span data-stu-id="13996-1951">To learn more, see [EU Passport Number sensitive information type](eu-passport-number.md).</span></span>
  
## <a name="eu-social-security-number-or-equivalent-id"></a><span data-ttu-id="13996-1952">Codice di preVidenza sociale dell'Unione europea o ID equivalente</span><span class="sxs-lookup"><span data-stu-id="13996-1952">EU Social Security Number or Equivalent ID</span></span>

<span data-ttu-id="13996-1953">Per ulteriori informazioni, vedere [codice di PrevideNza sociale dell'Unione europea o tipo di dati sensibili ID equivalente](eu-social-security-number-or-equivalent-id.md).</span><span class="sxs-lookup"><span data-stu-id="13996-1953">To learn more, see [EU Social Security Number or Equivalent ID sensitive information type](eu-social-security-number-or-equivalent-id.md).</span></span>
  
## <a name="eu-tax-identification-number"></a><span data-ttu-id="13996-1954">Numero di identificazione fiscale dell'Unione europea</span><span class="sxs-lookup"><span data-stu-id="13996-1954">EU Tax Identification Number</span></span>

<span data-ttu-id="13996-1955">Per ulteriori informazioni, vedere [tipo di informazione riservata del numero di identificazione fiscale dell'Unione europea](eu-tax-identification-number.md).</span><span class="sxs-lookup"><span data-stu-id="13996-1955">To learn more, see [EU Tax Identification Number sensitive information type](eu-tax-identification-number.md).</span></span>
  
## <a name="finland-national-id"></a><span data-ttu-id="13996-1956">Finland National ID</span><span class="sxs-lookup"><span data-stu-id="13996-1956">Finland National ID</span></span>

### <a name="format"></a><span data-ttu-id="13996-1957">Formato</span><span class="sxs-lookup"><span data-stu-id="13996-1957">Format</span></span>

<span data-ttu-id="13996-1958">6 cifre, un carattere di indicazione del secolo, tre cifre più una cifra di controllo</span><span class="sxs-lookup"><span data-stu-id="13996-1958">Six digits plus a character indicating a century plus three digits plus a check digit</span></span>

### <a name="pattern"></a><span data-ttu-id="13996-1959">Modello</span><span class="sxs-lookup"><span data-stu-id="13996-1959">Pattern</span></span>

<span data-ttu-id="13996-1960">Il modello deve includere tutti gli elementi seguenti:</span><span class="sxs-lookup"><span data-stu-id="13996-1960">Pattern must include all of the following:</span></span>
- <span data-ttu-id="13996-1961">Sei cifre nel formato DDMMYY che corrisponde alla data di nascita</span><span class="sxs-lookup"><span data-stu-id="13996-1961">Six digits in the format format DDMMYY which are a date of birth</span></span> 
- <span data-ttu-id="13996-1962">Indicatore del secolo ("-", "+" o "a")</span><span class="sxs-lookup"><span data-stu-id="13996-1962">Century marker (either '-', '+' or 'a')</span></span> 
- <span data-ttu-id="13996-1963">Codice PIN di 3 cifre</span><span class="sxs-lookup"><span data-stu-id="13996-1963">Three-digit personal identification number</span></span> 
- <span data-ttu-id="13996-1964">Una cifra o una lettera (con distinzione tra maiuscole/minuscole) che corrisponde a una cifra di controllo</span><span class="sxs-lookup"><span data-stu-id="13996-1964">A digit or letter (case insensitive) which is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="13996-1965">Checksum</span><span class="sxs-lookup"><span data-stu-id="13996-1965">Checksum</span></span>

<span data-ttu-id="13996-1966">Sì</span><span class="sxs-lookup"><span data-stu-id="13996-1966">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="13996-1967">Definizione</span><span class="sxs-lookup"><span data-stu-id="13996-1967">Definition</span></span>

<span data-ttu-id="13996-1968">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="13996-1968">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="13996-1969">La funzione Func_finnish_national_id restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="13996-1969">The function Func_finnish_national_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="13996-1970">Viene trovata una parola chiave da Keyword_finnish_national_id.</span><span class="sxs-lookup"><span data-stu-id="13996-1970">A keyword from Keyword_finnish_national_id is found.</span></span>
- <span data-ttu-id="13996-1971">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="13996-1971">The checksum passes.</span></span>

```
<!-- Finnish National ID-->
<Entity id="338FD995-4CB5-4F87-AD35-79BD1DD926C1" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_finnish_national_id" />
          <Match idRef="Keyword_finnish_national_id" />
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="13996-1972">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="13996-1972">Keywords</span></span>

- <span data-ttu-id="13996-1973">Keyword_finnish_national_id</span><span class="sxs-lookup"><span data-stu-id="13996-1973">Keyword_finnish_national_id</span></span>
- <span data-ttu-id="13996-1974">Sosiaaliturvatunnus</span><span class="sxs-lookup"><span data-stu-id="13996-1974">Sosiaaliturvatunnus</span></span>
- <span data-ttu-id="13996-1975">SOTU Henkilötunnus HETU</span><span class="sxs-lookup"><span data-stu-id="13996-1975">SOTU Henkilötunnus HETU</span></span>
- <span data-ttu-id="13996-1976">Personbeteckning</span><span class="sxs-lookup"><span data-stu-id="13996-1976">Personbeteckning</span></span>
- <span data-ttu-id="13996-1977">Personnummer</span><span class="sxs-lookup"><span data-stu-id="13996-1977">Personnummer</span></span>
   
## <a name="finland-passport-number"></a><span data-ttu-id="13996-1978">Finlandia - Numero di passaporto</span><span class="sxs-lookup"><span data-stu-id="13996-1978">Finland Passport Number</span></span>

<span data-ttu-id="13996-1979">Combinazione di formato di nove lettere e combinazioni di caratteri di nove lettere e cifre: due lettere (senza distinzione tra maiuscole/minuscole) sette cifre checksum nessuna definizione un criterio DLP è 75% sicuro che sia stato rilevato questo tipo di informazioni riservate se, all'interno di un prossimità di 300 caratteri: l'espressione regolare Regex_finland_passport_number trova il contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="13996-1979">Format Combination of nine letters and digits Pattern Combination of nine letters and digits: Two letters (not case sensitive) Seven digits Checksum No Definition A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The regular expression Regex_finland_passport_number finds content that matches the pattern.</span></span>
<span data-ttu-id="13996-1980">Viene trovata una parola chiave da Keyword_finland_passport_number.</span><span class="sxs-lookup"><span data-stu-id="13996-1980">A keyword from Keyword_finland_passport_number is found.</span></span>
<!-- Finland Passport Number -->
<span data-ttu-id="13996-1981"><Entity id="d1685ac3-1d3a-40f8-8198-32ef5669c7a5" recommendedConfidence="75" patternsProximity="300"> <Pattern confidenceLevel="75"> <IdMatch idRef="Regex_finland_passport_number"/> <Match idRef="Keyword_finland_passport_number"/> </Pattern>
</Entity></span><span class="sxs-lookup"><span data-stu-id="13996-1981"></span></span>
<span data-ttu-id="13996-1982">Parole chiave Keyword_finland_passport_number passaporto passi</span><span class="sxs-lookup"><span data-stu-id="13996-1982">Keywords Keyword_finland_passport_number Passport Passi</span></span>
   
## <a name="france-drivers-license-number"></a><span data-ttu-id="13996-1983">Francia - Numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="13996-1983">France Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="13996-1984">Formato</span><span class="sxs-lookup"><span data-stu-id="13996-1984">Format</span></span>

<span data-ttu-id="13996-1985">12 cifre</span><span class="sxs-lookup"><span data-stu-id="13996-1985">12 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="13996-1986">Modello</span><span class="sxs-lookup"><span data-stu-id="13996-1986">Pattern</span></span>

<span data-ttu-id="13996-1987">12 cifre con convalida per scontare modelli analoghi, ad esempio, quello dei numeri telefonici francesi</span><span class="sxs-lookup"><span data-stu-id="13996-1987">12 digits with validation to discount similar patterns such as French telephone numbers</span></span>

### <a name="checksum"></a><span data-ttu-id="13996-1988">Checksum</span><span class="sxs-lookup"><span data-stu-id="13996-1988">Checksum</span></span>

<span data-ttu-id="13996-1989">No</span><span class="sxs-lookup"><span data-stu-id="13996-1989">No</span></span>

### <a name="definition"></a><span data-ttu-id="13996-1990">Definizione</span><span class="sxs-lookup"><span data-stu-id="13996-1990">Definition</span></span>

<span data-ttu-id="13996-1991">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="13996-1991">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="13996-1992">La funzione Func_french_drivers_license restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="13996-1992">The function Func_french_drivers_license finds content that matches the pattern.</span></span>
- <span data-ttu-id="13996-1993">Si verifica almeno una delle situazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="13996-1993">At least one of the following is true:</span></span>
- <span data-ttu-id="13996-1994">Viene trovata una parola chiave da Keyword_french_drivers_license.</span><span class="sxs-lookup"><span data-stu-id="13996-1994">A keyword from Keyword_french_drivers_license is found.</span></span>
- <span data-ttu-id="13996-1995">La funzione Func_eu_date rileva una data nel formato corretto.</span><span class="sxs-lookup"><span data-stu-id="13996-1995">The function Func_eu_date finds a date in the right date format.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="13996-1996">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="13996-1996">Keywords</span></span>

#### <a name="keywordfrenchdriverslicense"></a><span data-ttu-id="13996-1997">Keyword_french_drivers_license</span><span class="sxs-lookup"><span data-stu-id="13996-1997">Keyword_french_drivers_license</span></span>

- <span data-ttu-id="13996-1998">drivers licence</span><span class="sxs-lookup"><span data-stu-id="13996-1998">drivers licence</span></span>
- <span data-ttu-id="13996-1999">drivers license</span><span class="sxs-lookup"><span data-stu-id="13996-1999">drivers license</span></span>
- <span data-ttu-id="13996-2000">driving licence</span><span class="sxs-lookup"><span data-stu-id="13996-2000">driving licence</span></span>
- <span data-ttu-id="13996-2001">driving license</span><span class="sxs-lookup"><span data-stu-id="13996-2001">driving license</span></span>
- <span data-ttu-id="13996-2002">permis de conduire</span><span class="sxs-lookup"><span data-stu-id="13996-2002">permis de conduire</span></span>
- <span data-ttu-id="13996-2003">licence number</span><span class="sxs-lookup"><span data-stu-id="13996-2003">licence number</span></span>
- <span data-ttu-id="13996-2004">license number</span><span class="sxs-lookup"><span data-stu-id="13996-2004">license number</span></span>
- <span data-ttu-id="13996-2005">licence numbers</span><span class="sxs-lookup"><span data-stu-id="13996-2005">licence numbers</span></span>
- <span data-ttu-id="13996-2006">license numbers</span><span class="sxs-lookup"><span data-stu-id="13996-2006">license numbers</span></span>

## <a name="france-national-id-card-cni"></a><span data-ttu-id="13996-2007">Francia - Carta d'identità nazionale (CNI)</span><span class="sxs-lookup"><span data-stu-id="13996-2007">France National ID Card (CNI)</span></span>

### <a name="format"></a><span data-ttu-id="13996-2008">Formato</span><span class="sxs-lookup"><span data-stu-id="13996-2008">Format</span></span>

<span data-ttu-id="13996-2009">12 cifre</span><span class="sxs-lookup"><span data-stu-id="13996-2009">12 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="13996-2010">Modello</span><span class="sxs-lookup"><span data-stu-id="13996-2010">Pattern</span></span>

<span data-ttu-id="13996-2011">12 cifre</span><span class="sxs-lookup"><span data-stu-id="13996-2011">12 digits</span></span>

### <a name="checksum"></a><span data-ttu-id="13996-2012">Checksum</span><span class="sxs-lookup"><span data-stu-id="13996-2012">Checksum</span></span>

<span data-ttu-id="13996-2013">No</span><span class="sxs-lookup"><span data-stu-id="13996-2013">No</span></span>

### <a name="definition"></a><span data-ttu-id="13996-2014">Definizione</span><span class="sxs-lookup"><span data-stu-id="13996-2014">Definition</span></span>

<span data-ttu-id="13996-2015">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 65%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="13996-2015">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="13996-2016">L'espressione regolare Regex_france_cni restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="13996-2016">The regular expression Regex_france_cni finds content that matches the pattern.</span></span>

```
<!-- France CNI -->
<Entity id="f741ac74-1bc0-4665-b69b-f0c7f927c0c4" patternsProximity="300" recommendedConfidence="65">
  <Pattern confidenceLevel="65">
        <IdMatch idRef="Regex_france_cni" />
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="13996-2017">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="13996-2017">Keywords</span></span>

<span data-ttu-id="13996-2018">Nessuno</span><span class="sxs-lookup"><span data-stu-id="13996-2018">None</span></span>
   
## <a name="france-passport-number"></a><span data-ttu-id="13996-2019">Francia - Numero di passaporto</span><span class="sxs-lookup"><span data-stu-id="13996-2019">France Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="13996-2020">Formato</span><span class="sxs-lookup"><span data-stu-id="13996-2020">Format</span></span>

<span data-ttu-id="13996-2021">Nove cifre e lettere</span><span class="sxs-lookup"><span data-stu-id="13996-2021">Nine digits and letters</span></span>

### <a name="pattern"></a><span data-ttu-id="13996-2022">Modello</span><span class="sxs-lookup"><span data-stu-id="13996-2022">Pattern</span></span>

<span data-ttu-id="13996-2023">Nove cifre e lettere:</span><span class="sxs-lookup"><span data-stu-id="13996-2023">Nine digits and letters:</span></span>
- <span data-ttu-id="13996-2024">Due cifre</span><span class="sxs-lookup"><span data-stu-id="13996-2024">Two digits</span></span> 
- <span data-ttu-id="13996-2025">Due lettere (senza distinzione tra maiuscole/minuscole)</span><span class="sxs-lookup"><span data-stu-id="13996-2025">Two letters (not case sensitive)</span></span> 
- <span data-ttu-id="13996-2026">Cinque cifre</span><span class="sxs-lookup"><span data-stu-id="13996-2026">Five digits</span></span>

### <a name="checksum"></a><span data-ttu-id="13996-2027">Checksum</span><span class="sxs-lookup"><span data-stu-id="13996-2027">Checksum</span></span>

<span data-ttu-id="13996-2028">No</span><span class="sxs-lookup"><span data-stu-id="13996-2028">No</span></span>

### <a name="definition"></a><span data-ttu-id="13996-2029">Definizione</span><span class="sxs-lookup"><span data-stu-id="13996-2029">Definition</span></span>

<span data-ttu-id="13996-2030">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="13996-2030">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="13996-2031">La funzione Func_fr_passport restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="13996-2031">The function Func_fr_passport finds content that matches the pattern.</span></span>
- <span data-ttu-id="13996-2032">Viene trovata una parola chiave da Keyword_passport.</span><span class="sxs-lookup"><span data-stu-id="13996-2032">A keyword from Keyword_passport is found.</span></span>

```
<!-- France Passport Number -->
<Entity id="3008b884-8c8c-4cd8-a289-99f34fc7ff5d" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_fr_passport" />
        <Match idRef="Keyword_passport" />
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="13996-2033">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="13996-2033">Keywords</span></span>

#### <a name="keywordpassport"></a><span data-ttu-id="13996-2034">Keyword_passport</span><span class="sxs-lookup"><span data-stu-id="13996-2034">Keyword_passport</span></span>

- <span data-ttu-id="13996-2035">Passport Number</span><span class="sxs-lookup"><span data-stu-id="13996-2035">Passport Number</span></span>
- <span data-ttu-id="13996-2036">Passport No</span><span class="sxs-lookup"><span data-stu-id="13996-2036">Passport No</span></span>
- <span data-ttu-id="13996-2037">Passport#</span><span class="sxs-lookup"><span data-stu-id="13996-2037">Passport #</span></span>
- <span data-ttu-id="13996-2038">Passaporto</span><span class="sxs-lookup"><span data-stu-id="13996-2038">Passport#</span></span>
- <span data-ttu-id="13996-2039">PassportID</span><span class="sxs-lookup"><span data-stu-id="13996-2039">PassportID</span></span>
- <span data-ttu-id="13996-2040">Passportno</span><span class="sxs-lookup"><span data-stu-id="13996-2040">Passportno</span></span>
- <span data-ttu-id="13996-2041">passportnumber</span><span class="sxs-lookup"><span data-stu-id="13996-2041">passportnumber</span></span>
- <span data-ttu-id="13996-2042">パスポート</span><span class="sxs-lookup"><span data-stu-id="13996-2042">パスポート</span></span>
- <span data-ttu-id="13996-2043">パスポート番号</span><span class="sxs-lookup"><span data-stu-id="13996-2043">パスポート番号</span></span>
- <span data-ttu-id="13996-2044">パスポートのNum</span><span class="sxs-lookup"><span data-stu-id="13996-2044">パスポートのNum</span></span>
- <span data-ttu-id="13996-2045">パスポート ＃</span><span class="sxs-lookup"><span data-stu-id="13996-2045">パスポート ＃</span></span> 
- <span data-ttu-id="13996-2046">Numéro de passeport</span><span class="sxs-lookup"><span data-stu-id="13996-2046">Numéro de passeport</span></span>
- <span data-ttu-id="13996-2047">Passeport n °</span><span class="sxs-lookup"><span data-stu-id="13996-2047">Passeport n °</span></span>
- <span data-ttu-id="13996-2048">Passeport Non</span><span class="sxs-lookup"><span data-stu-id="13996-2048">Passeport Non</span></span>
- <span data-ttu-id="13996-2049">Passeport#</span><span class="sxs-lookup"><span data-stu-id="13996-2049">Passeport #</span></span>
- <span data-ttu-id="13996-2050">Passeport</span><span class="sxs-lookup"><span data-stu-id="13996-2050">Passeport#</span></span>
- <span data-ttu-id="13996-2051">PasseportNon</span><span class="sxs-lookup"><span data-stu-id="13996-2051">PasseportNon</span></span>
- <span data-ttu-id="13996-2052">Passeportn °</span><span class="sxs-lookup"><span data-stu-id="13996-2052">Passeportn °</span></span>

      
## <a name="france-social-security-number-insee"></a><span data-ttu-id="13996-2053">Francia - Numero di previdenza sociale (INSEE)</span><span class="sxs-lookup"><span data-stu-id="13996-2053">France Social Security Number (INSEE)</span></span>

### <a name="format"></a><span data-ttu-id="13996-2054">Formato</span><span class="sxs-lookup"><span data-stu-id="13996-2054">Format</span></span>

<span data-ttu-id="13996-2055">15 cifre</span><span class="sxs-lookup"><span data-stu-id="13996-2055">15 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="13996-2056">Modello</span><span class="sxs-lookup"><span data-stu-id="13996-2056">Pattern</span></span>

<span data-ttu-id="13996-2057">Deve corrispondere a uno di questi due modelli:</span><span class="sxs-lookup"><span data-stu-id="13996-2057">Must match one of two patterns:</span></span>
- <span data-ttu-id="13996-2058">13 cifre seguite da uno spazio seguito da due cifre</span><span class="sxs-lookup"><span data-stu-id="13996-2058">13 digits followed by a space followed by two digits</span></span><br/>
<span data-ttu-id="13996-2059">oppure</span><span class="sxs-lookup"><span data-stu-id="13996-2059">or</span></span>
- <span data-ttu-id="13996-2060">15 cifre consecutive</span><span class="sxs-lookup"><span data-stu-id="13996-2060">15 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="13996-2061">Checksum</span><span class="sxs-lookup"><span data-stu-id="13996-2061">Checksum</span></span>

<span data-ttu-id="13996-2062">Sì</span><span class="sxs-lookup"><span data-stu-id="13996-2062">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="13996-2063">Definizione</span><span class="sxs-lookup"><span data-stu-id="13996-2063">Definition</span></span>

<span data-ttu-id="13996-2064">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 95%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="13996-2064">A DLP policy is 95% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="13996-2065">La funzione Func_french_insee o Func_fr_insee trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="13996-2065">The function Func_french_insee or Func_fr_insee finds content that matches the pattern.</span></span>
- <span data-ttu-id="13996-2066">Viene trovata una parola chiave da Keyword_fr_insee.</span><span class="sxs-lookup"><span data-stu-id="13996-2066">A keyword from Keyword_fr_insee is found.</span></span>
- <span data-ttu-id="13996-2067">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="13996-2067">The checksum passes.</span></span>

<span data-ttu-id="13996-2068">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="13996-2068">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="13996-2069">La funzione Func_french_insee o Func_fr_insee trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="13996-2069">The function Func_french_insee or Func_fr_insee finds content that matches the pattern.</span></span>
- <span data-ttu-id="13996-2070">Non vengono trovate parole chiave da Keyword_fr_insee.</span><span class="sxs-lookup"><span data-stu-id="13996-2070">No keyword from Keyword_fr_insee is found.</span></span>
- <span data-ttu-id="13996-2071">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="13996-2071">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="13996-2072">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="13996-2072">Keywords</span></span>

#### <a name="keywordfrinsee"></a><span data-ttu-id="13996-2073">Keyword_fr_insee</span><span class="sxs-lookup"><span data-stu-id="13996-2073">Keyword_fr_insee</span></span>

- <span data-ttu-id="13996-2074">INSEE</span><span class="sxs-lookup"><span data-stu-id="13996-2074">insee</span></span>
- <span data-ttu-id="13996-2075">securité sociale</span><span class="sxs-lookup"><span data-stu-id="13996-2075">securité sociale</span></span>
- <span data-ttu-id="13996-2076">securite sociale</span><span class="sxs-lookup"><span data-stu-id="13996-2076">securite sociale</span></span>
- <span data-ttu-id="13996-2077">national id</span><span class="sxs-lookup"><span data-stu-id="13996-2077">national id</span></span>
- <span data-ttu-id="13996-2078">national identification</span><span class="sxs-lookup"><span data-stu-id="13996-2078">national identification</span></span>
- <span data-ttu-id="13996-2079">numéro d'identité</span><span class="sxs-lookup"><span data-stu-id="13996-2079">numéro d'identité</span></span>
- <span data-ttu-id="13996-2080">no d'identité</span><span class="sxs-lookup"><span data-stu-id="13996-2080">no d'identité</span></span>
- <span data-ttu-id="13996-2081">No.</span><span class="sxs-lookup"><span data-stu-id="13996-2081">no.</span></span> <span data-ttu-id="13996-2082">d'identité</span><span class="sxs-lookup"><span data-stu-id="13996-2082">d'identité</span></span>
- <span data-ttu-id="13996-2083">numero d'identite</span><span class="sxs-lookup"><span data-stu-id="13996-2083">numero d'identite</span></span>
- <span data-ttu-id="13996-2084">no d'identite</span><span class="sxs-lookup"><span data-stu-id="13996-2084">no d'identite</span></span>
- <span data-ttu-id="13996-2085">No.</span><span class="sxs-lookup"><span data-stu-id="13996-2085">no.</span></span> <span data-ttu-id="13996-2086">d'identite</span><span class="sxs-lookup"><span data-stu-id="13996-2086">d'identite</span></span>
- <span data-ttu-id="13996-2087">social security number</span><span class="sxs-lookup"><span data-stu-id="13996-2087">social security number</span></span>
- <span data-ttu-id="13996-2088">social security code</span><span class="sxs-lookup"><span data-stu-id="13996-2088">social security code</span></span>
- <span data-ttu-id="13996-2089">social insurance number</span><span class="sxs-lookup"><span data-stu-id="13996-2089">social insurance number</span></span>
- <span data-ttu-id="13996-2090">le numéro d'identification nationale</span><span class="sxs-lookup"><span data-stu-id="13996-2090">le numéro d'identification nationale</span></span>
- <span data-ttu-id="13996-2091">d'identité nationale</span><span class="sxs-lookup"><span data-stu-id="13996-2091">d'identité nationale</span></span>
- <span data-ttu-id="13996-2092">numéro de sécurité sociale</span><span class="sxs-lookup"><span data-stu-id="13996-2092">numéro de sécurité sociale</span></span>
- <span data-ttu-id="13996-2093">le code de la sécurité sociale</span><span class="sxs-lookup"><span data-stu-id="13996-2093">le code de la sécurité sociale</span></span>
- <span data-ttu-id="13996-2094">numéro d'assurance sociale</span><span class="sxs-lookup"><span data-stu-id="13996-2094">numéro d'assurance sociale</span></span>
- <span data-ttu-id="13996-2095">numéro de sécu</span><span class="sxs-lookup"><span data-stu-id="13996-2095">numéro de sécu</span></span>
- <span data-ttu-id="13996-2096">code sécu</span><span class="sxs-lookup"><span data-stu-id="13996-2096">code sécu</span></span> 
   
## <a name="german-drivers-license-number"></a><span data-ttu-id="13996-2097">Germania - Numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="13996-2097">German Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="13996-2098">Formato</span><span class="sxs-lookup"><span data-stu-id="13996-2098">Format</span></span>

<span data-ttu-id="13996-2099">Combinazione di 11 cifre e lettere</span><span class="sxs-lookup"><span data-stu-id="13996-2099">Combination of 11 digits and letters</span></span>

### <a name="pattern"></a><span data-ttu-id="13996-2100">Modello</span><span class="sxs-lookup"><span data-stu-id="13996-2100">Pattern</span></span>

<span data-ttu-id="13996-2101">11 cifre e lettere (senza distinzione tra maiuscole/minuscole):</span><span class="sxs-lookup"><span data-stu-id="13996-2101">11 digits and letters (not case sensitive):</span></span>
- <span data-ttu-id="13996-2102">Una cifra o una lettera</span><span class="sxs-lookup"><span data-stu-id="13996-2102">A digit or letter</span></span> 
- <span data-ttu-id="13996-2103">Due cifre</span><span class="sxs-lookup"><span data-stu-id="13996-2103">Two digits</span></span> 
- <span data-ttu-id="13996-2104">Sei cifre o lettere</span><span class="sxs-lookup"><span data-stu-id="13996-2104">Six digits or letters</span></span> 
- <span data-ttu-id="13996-2105">Una cifra</span><span class="sxs-lookup"><span data-stu-id="13996-2105">A digit</span></span> 
- <span data-ttu-id="13996-2106">Una cifra o una lettera</span><span class="sxs-lookup"><span data-stu-id="13996-2106">A digit or letter</span></span>

### <a name="checksum"></a><span data-ttu-id="13996-2107">Checksum</span><span class="sxs-lookup"><span data-stu-id="13996-2107">Checksum</span></span>

<span data-ttu-id="13996-2108">Sì</span><span class="sxs-lookup"><span data-stu-id="13996-2108">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="13996-2109">Definizione</span><span class="sxs-lookup"><span data-stu-id="13996-2109">Definition</span></span>

<span data-ttu-id="13996-2110">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="13996-2110">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="13996-2111">La funzione Func_german_drivers_license restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="13996-2111">The function Func_german_drivers_license finds content that matches the pattern.</span></span>
- <span data-ttu-id="13996-2112">Si verifica almeno una delle situazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="13996-2112">At least one of the following is true:</span></span>
    - <span data-ttu-id="13996-2113">Viene trovata una parola chiave da Keyword_german_drivers_license_number.</span><span class="sxs-lookup"><span data-stu-id="13996-2113">A keyword from Keyword_german_drivers_license_number is found.</span></span>
    - <span data-ttu-id="13996-2114">Viene trovata una parola chiave da Keyword_german_drivers_license_collaborative.</span><span class="sxs-lookup"><span data-stu-id="13996-2114">A keyword from Keyword_german_drivers_license_collaborative is found.</span></span>
    - <span data-ttu-id="13996-2115">Viene trovata una parola chiave da Keyword_german_drivers_license.</span><span class="sxs-lookup"><span data-stu-id="13996-2115">A keyword from Keyword_german_drivers_license is found.</span></span>
- <span data-ttu-id="13996-2116">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="13996-2116">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="13996-2117">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="13996-2117">Keywords</span></span>

#### <a name="keywordgermandriverslicensenumber"></a><span data-ttu-id="13996-2118">Keyword_german_drivers_license_number</span><span class="sxs-lookup"><span data-stu-id="13996-2118">Keyword_german_drivers_license_number</span></span>

- <span data-ttu-id="13996-2119">Führerschein</span><span class="sxs-lookup"><span data-stu-id="13996-2119">Führerschein</span></span>
- <span data-ttu-id="13996-2120">Fuhrerschein</span><span class="sxs-lookup"><span data-stu-id="13996-2120">Fuhrerschein</span></span>
- <span data-ttu-id="13996-2121">Fuehrerschein</span><span class="sxs-lookup"><span data-stu-id="13996-2121">Fuehrerschein</span></span>
- <span data-ttu-id="13996-2122">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="13996-2122">Führerscheinnummer</span></span>
- <span data-ttu-id="13996-2123">Fuhrerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="13996-2123">Fuhrerscheinnummer</span></span>
- <span data-ttu-id="13996-2124">Fuehrerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="13996-2124">Fuehrerscheinnummer</span></span>
- <span data-ttu-id="13996-2125">Führerschein-</span><span class="sxs-lookup"><span data-stu-id="13996-2125">Führerschein-</span></span> 
- <span data-ttu-id="13996-2126">Fuhrerschein-</span><span class="sxs-lookup"><span data-stu-id="13996-2126">Fuhrerschein-</span></span> 
- <span data-ttu-id="13996-2127">Fuehrerschein-</span><span class="sxs-lookup"><span data-stu-id="13996-2127">Fuehrerschein-</span></span> 
- <span data-ttu-id="13996-2128">FührerscheinnummerNr</span><span class="sxs-lookup"><span data-stu-id="13996-2128">FührerscheinnummerNr</span></span>
- <span data-ttu-id="13996-2129">FuhrerscheinnummerNr</span><span class="sxs-lookup"><span data-stu-id="13996-2129">FuhrerscheinnummerNr</span></span>
- <span data-ttu-id="13996-2130">FuehrerscheinnummerNr</span><span class="sxs-lookup"><span data-stu-id="13996-2130">FuehrerscheinnummerNr</span></span>
- <span data-ttu-id="13996-2131">FührerscheinnummerKlasse</span><span class="sxs-lookup"><span data-stu-id="13996-2131">FührerscheinnummerKlasse</span></span>
- <span data-ttu-id="13996-2132">FuhrerscheinnummerKlasse</span><span class="sxs-lookup"><span data-stu-id="13996-2132">FuhrerscheinnummerKlasse</span></span>
- <span data-ttu-id="13996-2133">FuehrerscheinnummerKlasse</span><span class="sxs-lookup"><span data-stu-id="13996-2133">FuehrerscheinnummerKlasse</span></span>
- <span data-ttu-id="13996-2134">Führerschein- Nr</span><span class="sxs-lookup"><span data-stu-id="13996-2134">Führerschein- Nr</span></span>
- <span data-ttu-id="13996-2135">Fuhrerschein- Nr</span><span class="sxs-lookup"><span data-stu-id="13996-2135">Fuhrerschein- Nr</span></span>
- <span data-ttu-id="13996-2136">Fuehrerschein- Nr</span><span class="sxs-lookup"><span data-stu-id="13996-2136">Fuehrerschein- Nr</span></span> 
- <span data-ttu-id="13996-2137">Führerschein- Klasse</span><span class="sxs-lookup"><span data-stu-id="13996-2137">Führerschein- Klasse</span></span> 
- <span data-ttu-id="13996-2138">Fuhrerschein- Klasse</span><span class="sxs-lookup"><span data-stu-id="13996-2138">Fuhrerschein- Klasse</span></span> 
- <span data-ttu-id="13996-2139">Fuehrerschein- Klasse</span><span class="sxs-lookup"><span data-stu-id="13996-2139">Fuehrerschein- Klasse</span></span>
- <span data-ttu-id="13996-2140">FührerscheinnummerNr</span><span class="sxs-lookup"><span data-stu-id="13996-2140">FührerscheinnummerNr</span></span> 
- <span data-ttu-id="13996-2141">FuhrerscheinnummerNr</span><span class="sxs-lookup"><span data-stu-id="13996-2141">FuhrerscheinnummerNr</span></span> 
- <span data-ttu-id="13996-2142">FuehrerscheinnummerNr</span><span class="sxs-lookup"><span data-stu-id="13996-2142">FuehrerscheinnummerNr</span></span> 
- <span data-ttu-id="13996-2143">FührerscheinnummerKlasse</span><span class="sxs-lookup"><span data-stu-id="13996-2143">FührerscheinnummerKlasse</span></span> 
- <span data-ttu-id="13996-2144">FuhrerscheinnummerKlasse</span><span class="sxs-lookup"><span data-stu-id="13996-2144">FuhrerscheinnummerKlasse</span></span> 
- <span data-ttu-id="13996-2145">FuehrerscheinnummerKlasse</span><span class="sxs-lookup"><span data-stu-id="13996-2145">FuehrerscheinnummerKlasse</span></span> 
- <span data-ttu-id="13996-2146">Führerschein- Nr</span><span class="sxs-lookup"><span data-stu-id="13996-2146">Führerschein- Nr</span></span> 
- <span data-ttu-id="13996-2147">Fuhrerschein- Nr</span><span class="sxs-lookup"><span data-stu-id="13996-2147">Fuhrerschein- Nr</span></span> 
- <span data-ttu-id="13996-2148">Fuehrerschein- Nr</span><span class="sxs-lookup"><span data-stu-id="13996-2148">Fuehrerschein- Nr</span></span> 
- <span data-ttu-id="13996-2149">Führerschein- Klasse</span><span class="sxs-lookup"><span data-stu-id="13996-2149">Führerschein- Klasse</span></span> 
- <span data-ttu-id="13996-2150">Fuhrerschein- Klasse</span><span class="sxs-lookup"><span data-stu-id="13996-2150">Fuhrerschein- Klasse</span></span> 
- <span data-ttu-id="13996-2151">Fuehrerschein- Klasse</span><span class="sxs-lookup"><span data-stu-id="13996-2151">Fuehrerschein- Klasse</span></span> 
- <span data-ttu-id="13996-2152">DL</span><span class="sxs-lookup"><span data-stu-id="13996-2152">DL</span></span> 
- <span data-ttu-id="13996-2153">DLS</span><span class="sxs-lookup"><span data-stu-id="13996-2153">DLS</span></span>
- <span data-ttu-id="13996-2154">Driv Lic</span><span class="sxs-lookup"><span data-stu-id="13996-2154">Driv Lic</span></span> 
- <span data-ttu-id="13996-2155">Driv Licen</span><span class="sxs-lookup"><span data-stu-id="13996-2155">Driv Licen</span></span> 
- <span data-ttu-id="13996-2156">Driv License</span><span class="sxs-lookup"><span data-stu-id="13996-2156">Driv License</span></span>
- <span data-ttu-id="13996-2157">Driv Licenses</span><span class="sxs-lookup"><span data-stu-id="13996-2157">Driv Licenses</span></span> 
- <span data-ttu-id="13996-2158">Driv Licence</span><span class="sxs-lookup"><span data-stu-id="13996-2158">Driv Licence</span></span> 
- <span data-ttu-id="13996-2159">Driv Licences</span><span class="sxs-lookup"><span data-stu-id="13996-2159">Driv Licences</span></span> 
- <span data-ttu-id="13996-2160">Driv Lic</span><span class="sxs-lookup"><span data-stu-id="13996-2160">Driv Lic</span></span> 
- <span data-ttu-id="13996-2161">Driver Licen</span><span class="sxs-lookup"><span data-stu-id="13996-2161">Driver Licen</span></span> 
- <span data-ttu-id="13996-2162">Driver License</span><span class="sxs-lookup"><span data-stu-id="13996-2162">Driver License</span></span> 
- <span data-ttu-id="13996-2163">Driver Licenses</span><span class="sxs-lookup"><span data-stu-id="13996-2163">Driver Licenses</span></span> 
- <span data-ttu-id="13996-2164">Driver Licence</span><span class="sxs-lookup"><span data-stu-id="13996-2164">Driver Licence</span></span> 
- <span data-ttu-id="13996-2165">Driver Licences</span><span class="sxs-lookup"><span data-stu-id="13996-2165">Driver Licences</span></span> 
- <span data-ttu-id="13996-2166">Drivers Lic</span><span class="sxs-lookup"><span data-stu-id="13996-2166">Drivers Lic</span></span> 
- <span data-ttu-id="13996-2167">Drivers Licen</span><span class="sxs-lookup"><span data-stu-id="13996-2167">Drivers Licen</span></span> 
- <span data-ttu-id="13996-2168">Drivers License</span><span class="sxs-lookup"><span data-stu-id="13996-2168">Drivers License</span></span> 
- <span data-ttu-id="13996-2169">Drivers Licenses</span><span class="sxs-lookup"><span data-stu-id="13996-2169">Drivers Licenses</span></span> 
- <span data-ttu-id="13996-2170">Drivers Licence</span><span class="sxs-lookup"><span data-stu-id="13996-2170">Drivers Licence</span></span> 
- <span data-ttu-id="13996-2171">Drivers Licences</span><span class="sxs-lookup"><span data-stu-id="13996-2171">Drivers Licences</span></span> 
- <span data-ttu-id="13996-2172">Driver's Lic</span><span class="sxs-lookup"><span data-stu-id="13996-2172">Driver's Lic</span></span> 
- <span data-ttu-id="13996-2173">Driver's Licen</span><span class="sxs-lookup"><span data-stu-id="13996-2173">Driver's Licen</span></span> 
- <span data-ttu-id="13996-2174">Driver's License</span><span class="sxs-lookup"><span data-stu-id="13996-2174">Driver's License</span></span> 
- <span data-ttu-id="13996-2175">Driver's Licenses</span><span class="sxs-lookup"><span data-stu-id="13996-2175">Driver's Licenses</span></span> 
- <span data-ttu-id="13996-2176">Driver's Licence</span><span class="sxs-lookup"><span data-stu-id="13996-2176">Driver's Licence</span></span> 
- <span data-ttu-id="13996-2177">Driver's Licences</span><span class="sxs-lookup"><span data-stu-id="13996-2177">Driver's Licences</span></span> 
- <span data-ttu-id="13996-2178">Driving Lic</span><span class="sxs-lookup"><span data-stu-id="13996-2178">Driving Lic</span></span> 
- <span data-ttu-id="13996-2179">Driving Licen</span><span class="sxs-lookup"><span data-stu-id="13996-2179">Driving Licen</span></span> 
- <span data-ttu-id="13996-2180">Driving License</span><span class="sxs-lookup"><span data-stu-id="13996-2180">Driving License</span></span> 
- <span data-ttu-id="13996-2181">Driving Licenses</span><span class="sxs-lookup"><span data-stu-id="13996-2181">Driving Licenses</span></span> 
- <span data-ttu-id="13996-2182">Driving Licence</span><span class="sxs-lookup"><span data-stu-id="13996-2182">Driving Licence</span></span> 
- <span data-ttu-id="13996-2183">Driving Licences</span><span class="sxs-lookup"><span data-stu-id="13996-2183">Driving Licences</span></span>

#### <a name="keywordgermandriverslicensecollaborative"></a><span data-ttu-id="13996-2184">Keyword_german_drivers_license_collaborative</span><span class="sxs-lookup"><span data-stu-id="13996-2184">Keyword_german_drivers_license_collaborative</span></span>

- <span data-ttu-id="13996-2185">Nr-Führerschein</span><span class="sxs-lookup"><span data-stu-id="13996-2185">Nr-Führerschein</span></span> 
- <span data-ttu-id="13996-2186">Nr-Fuhrerschein</span><span class="sxs-lookup"><span data-stu-id="13996-2186">Nr-Fuhrerschein</span></span> 
- <span data-ttu-id="13996-2187">Nr-Fuehrerschein</span><span class="sxs-lookup"><span data-stu-id="13996-2187">Nr-Fuehrerschein</span></span> 
- <span data-ttu-id="13996-2188">No-Führerschein</span><span class="sxs-lookup"><span data-stu-id="13996-2188">No-Führerschein</span></span> 
- <span data-ttu-id="13996-2189">No-Fuhrerschein</span><span class="sxs-lookup"><span data-stu-id="13996-2189">No-Fuhrerschein</span></span> 
- <span data-ttu-id="13996-2190">No-Fuehrerschein</span><span class="sxs-lookup"><span data-stu-id="13996-2190">No-Fuehrerschein</span></span> 
- <span data-ttu-id="13996-2191">N-Führerschein</span><span class="sxs-lookup"><span data-stu-id="13996-2191">N-Führerschein</span></span> 
- <span data-ttu-id="13996-2192">N-Fuhrerschein</span><span class="sxs-lookup"><span data-stu-id="13996-2192">N-Fuhrerschein</span></span> 
- <span data-ttu-id="13996-2193">N-Fuehrerschein</span><span class="sxs-lookup"><span data-stu-id="13996-2193">N-Fuehrerschein</span></span>
- <span data-ttu-id="13996-2194">Nr-Führerschein</span><span class="sxs-lookup"><span data-stu-id="13996-2194">Nr-Führerschein</span></span> 
- <span data-ttu-id="13996-2195">Nr-Fuhrerschein</span><span class="sxs-lookup"><span data-stu-id="13996-2195">Nr-Fuhrerschein</span></span> 
- <span data-ttu-id="13996-2196">Nr-Fuehrerschein</span><span class="sxs-lookup"><span data-stu-id="13996-2196">Nr-Fuehrerschein</span></span> 
- <span data-ttu-id="13996-2197">No-Führerschein</span><span class="sxs-lookup"><span data-stu-id="13996-2197">No-Führerschein</span></span> 
- <span data-ttu-id="13996-2198">No-Fuhrerschein</span><span class="sxs-lookup"><span data-stu-id="13996-2198">No-Fuhrerschein</span></span> 
- <span data-ttu-id="13996-2199">No-Fuehrerschein</span><span class="sxs-lookup"><span data-stu-id="13996-2199">No-Fuehrerschein</span></span> 
- <span data-ttu-id="13996-2200">N-Führerschein</span><span class="sxs-lookup"><span data-stu-id="13996-2200">N-Führerschein</span></span> 
- <span data-ttu-id="13996-2201">N-Fuhrerschein</span><span class="sxs-lookup"><span data-stu-id="13996-2201">N-Fuhrerschein</span></span> 
- <span data-ttu-id="13996-2202">N-Fuehrerschein</span><span class="sxs-lookup"><span data-stu-id="13996-2202">N-Fuehrerschein</span></span> 

#### <a name="keywordgermandriverslicense"></a><span data-ttu-id="13996-2203">Keyword_german_drivers_license</span><span class="sxs-lookup"><span data-stu-id="13996-2203">Keyword_german_drivers_license</span></span>

- <span data-ttu-id="13996-2204">ausstellungsdatum</span><span class="sxs-lookup"><span data-stu-id="13996-2204">ausstellungsdatum</span></span>
- <span data-ttu-id="13996-2205">ausstellungsort</span><span class="sxs-lookup"><span data-stu-id="13996-2205">ausstellungsort</span></span>
- <span data-ttu-id="13996-2206">ausstellende behöde</span><span class="sxs-lookup"><span data-stu-id="13996-2206">ausstellende behöde</span></span>
- <span data-ttu-id="13996-2207">ausstellende behorde</span><span class="sxs-lookup"><span data-stu-id="13996-2207">ausstellende behorde</span></span>
- <span data-ttu-id="13996-2208">ausstellende behoerde</span><span class="sxs-lookup"><span data-stu-id="13996-2208">ausstellende behoerde</span></span>
   
## <a name="german-passport-number"></a><span data-ttu-id="13996-2209">Germania - Numero di passaporto</span><span class="sxs-lookup"><span data-stu-id="13996-2209">German Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="13996-2210">Formato</span><span class="sxs-lookup"><span data-stu-id="13996-2210">Format</span></span>

<span data-ttu-id="13996-2211">10 cifre o lettere</span><span class="sxs-lookup"><span data-stu-id="13996-2211">10 digits or letters</span></span>

### <a name="pattern"></a><span data-ttu-id="13996-2212">Modello</span><span class="sxs-lookup"><span data-stu-id="13996-2212">Pattern</span></span>

<span data-ttu-id="13996-2213">Il modello deve includere tutti gli elementi seguenti:</span><span class="sxs-lookup"><span data-stu-id="13996-2213">Pattern must include all of the following:</span></span>
- <span data-ttu-id="13996-2214">Il primo carattere è una cifra o una lettera del gruppo seguente: C, F, G, H, J, K</span><span class="sxs-lookup"><span data-stu-id="13996-2214">First character is a digit or a letter from this set (C, F, G, H, J, K)</span></span> 
- <span data-ttu-id="13996-2215">Tre cifre</span><span class="sxs-lookup"><span data-stu-id="13996-2215">Three digits</span></span> 
- <span data-ttu-id="13996-2216">Cinque cifre o lettere del gruppo seguente: C, -H, J-N, P, R, T, V-Z</span><span class="sxs-lookup"><span data-stu-id="13996-2216">Five digits or letters from this set (C, -H, J-N, P, R, T, V-Z)</span></span> 
- <span data-ttu-id="13996-2217">Una cifra</span><span class="sxs-lookup"><span data-stu-id="13996-2217">A digit</span></span>

### <a name="checksum"></a><span data-ttu-id="13996-2218">Checksum</span><span class="sxs-lookup"><span data-stu-id="13996-2218">Checksum</span></span>

<span data-ttu-id="13996-2219">Sì</span><span class="sxs-lookup"><span data-stu-id="13996-2219">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="13996-2220">Definizione</span><span class="sxs-lookup"><span data-stu-id="13996-2220">Definition</span></span>

<span data-ttu-id="13996-2221">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="13996-2221">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="13996-2222">La funzione Func_german_passport restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="13996-2222">The function Func_german_passport finds content that matches the pattern.</span></span>
- <span data-ttu-id="13996-2223">Viene trovata una parola chiave fra le cinque elencate.</span><span class="sxs-lookup"><span data-stu-id="13996-2223">A keyword from any of the five keyword lists is found.</span></span>
- <span data-ttu-id="13996-2224">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="13996-2224">The checksum passes.</span></span>

<span data-ttu-id="13996-2225">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="13996-2225">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="13996-2226">La funzione Func_german_passport_data restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="13996-2226">The function Func_german_passport_data finds content that matches the pattern.</span></span>
- <span data-ttu-id="13996-2227">Viene trovata una parola chiave fra le cinque elencate.</span><span class="sxs-lookup"><span data-stu-id="13996-2227">A keyword from any of the five keyword lists is found.</span></span>
- <span data-ttu-id="13996-2228">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="13996-2228">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="13996-2229">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="13996-2229">Keywords</span></span>

#### <a name="keywordgermanpassport"></a><span data-ttu-id="13996-2230">Keyword_german_passport</span><span class="sxs-lookup"><span data-stu-id="13996-2230">Keyword_german_passport</span></span>

- <span data-ttu-id="13996-2231">Reisepass</span><span class="sxs-lookup"><span data-stu-id="13996-2231">reisepass</span></span>
- <span data-ttu-id="13996-2232">reisepasse</span><span class="sxs-lookup"><span data-stu-id="13996-2232">reisepasse</span></span>
- <span data-ttu-id="13996-2233">reisepassnummer</span><span class="sxs-lookup"><span data-stu-id="13996-2233">reisepassnummer</span></span>
- <span data-ttu-id="13996-2234">passaporto</span><span class="sxs-lookup"><span data-stu-id="13996-2234">passport</span></span>
- <span data-ttu-id="13996-2235">passaporti</span><span class="sxs-lookup"><span data-stu-id="13996-2235">passports</span></span>

#### <a name="keywordgermanpassportcollaborative"></a><span data-ttu-id="13996-2236">Keyword_german_passport_collaborative</span><span class="sxs-lookup"><span data-stu-id="13996-2236">Keyword_german_passport_collaborative</span></span>

- <span data-ttu-id="13996-2237">Geburtsdatum</span><span class="sxs-lookup"><span data-stu-id="13996-2237">geburtsdatum</span></span>
- <span data-ttu-id="13996-2238">ausstellungsdatum</span><span class="sxs-lookup"><span data-stu-id="13996-2238">ausstellungsdatum</span></span>
- <span data-ttu-id="13996-2239">ausstellungsort</span><span class="sxs-lookup"><span data-stu-id="13996-2239">ausstellungsort</span></span>

#### <a name="keywordgermanpassportnumber"></a><span data-ttu-id="13996-2240">Keyword_german_passport_number</span><span class="sxs-lookup"><span data-stu-id="13996-2240">Keyword_german_passport_number</span></span>

<span data-ttu-id="13996-2241">No-Reisepass Nr-Reisepass</span><span class="sxs-lookup"><span data-stu-id="13996-2241">No-Reisepass Nr-Reisepass</span></span>

#### <a name="keywordgermanpassport1"></a><span data-ttu-id="13996-2242">Keyword_german_passport1</span><span class="sxs-lookup"><span data-stu-id="13996-2242">Keyword_german_passport1</span></span>

<span data-ttu-id="13996-2243">Reisepass-Nr</span><span class="sxs-lookup"><span data-stu-id="13996-2243">Reisepass-Nr</span></span>

#### <a name="keywordgermanpassport2"></a><span data-ttu-id="13996-2244">Keyword_german_passport2</span><span class="sxs-lookup"><span data-stu-id="13996-2244">Keyword_german_passport2</span></span>

<span data-ttu-id="13996-2245">bnationalit. t</span><span class="sxs-lookup"><span data-stu-id="13996-2245">bnationalit.t</span></span>
   
## <a name="germany-identity-card-number"></a><span data-ttu-id="13996-2246">Germania - Numero carta di identità</span><span class="sxs-lookup"><span data-stu-id="13996-2246">Germany Identity Card Number</span></span>

### <a name="format"></a><span data-ttu-id="13996-2247">Formato</span><span class="sxs-lookup"><span data-stu-id="13996-2247">Format</span></span>

<span data-ttu-id="13996-2248">Dal 1 ° novembre 2010: nove lettere e cifre</span><span class="sxs-lookup"><span data-stu-id="13996-2248">Since 1 November 2010: Nine letters and digits</span></span>

<span data-ttu-id="13996-2249">Dal 1 ° aprile 1987 al 31 ottobre 2010:10 cifre</span><span class="sxs-lookup"><span data-stu-id="13996-2249">From 1 April 1987 until 31 October 2010: 10 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="13996-2250">Modello</span><span class="sxs-lookup"><span data-stu-id="13996-2250">Pattern</span></span>

<span data-ttu-id="13996-2251">A partire dal 1° novembre 2010:</span><span class="sxs-lookup"><span data-stu-id="13996-2251">Since 1 November 2010:</span></span>
- <span data-ttu-id="13996-2252">Una lettera (senza distinzione tra maiuscole/minuscole)</span><span class="sxs-lookup"><span data-stu-id="13996-2252">One letter (not case sensitive)</span></span> 
- <span data-ttu-id="13996-2253">Otto cifre</span><span class="sxs-lookup"><span data-stu-id="13996-2253">Eight digits</span></span>

<span data-ttu-id="13996-2254">Dal 1 ° aprile 1987 al 31 ottobre 2010:</span><span class="sxs-lookup"><span data-stu-id="13996-2254">From 1 April 1987 until 31 October 2010:</span></span>
- <span data-ttu-id="13996-2255">10 cifre</span><span class="sxs-lookup"><span data-stu-id="13996-2255">10 digits</span></span>

### <a name="checksum"></a><span data-ttu-id="13996-2256">Checksum</span><span class="sxs-lookup"><span data-stu-id="13996-2256">Checksum</span></span>

<span data-ttu-id="13996-2257">No</span><span class="sxs-lookup"><span data-stu-id="13996-2257">No</span></span>

### <a name="definition"></a><span data-ttu-id="13996-2258">Definizione</span><span class="sxs-lookup"><span data-stu-id="13996-2258">Definition</span></span>

<span data-ttu-id="13996-2259">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 65%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="13996-2259">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="13996-2260">L'espressione regolare Regex_germany_id_card trova il contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="13996-2260">The regular expression Regex_germany_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="13996-2261">Viene trovata una parola chiave da Keyword_germany_id_card.</span><span class="sxs-lookup"><span data-stu-id="13996-2261">A keyword from Keyword_germany_id_card is found.</span></span>

```
<!-- Germany Identity Card Number -->
<Entity id="e577372f-c42e-47a0-9d85-bebed1c237d4" recommendedConfidence="65" patternsProximity="300">
  <Pattern confidenceLevel="65">
     <IdMatch idRef="Regex_germany_id_card"/>
     <Match idRef="Keyword_germany_id_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="13996-2262">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="13996-2262">Keywords</span></span>

#### <a name="keywordgermanyidcard"></a><span data-ttu-id="13996-2263">Keyword_germany_id_card</span><span class="sxs-lookup"><span data-stu-id="13996-2263">Keyword_germany_id_card</span></span>

- <span data-ttu-id="13996-2264">Carta di identità</span><span class="sxs-lookup"><span data-stu-id="13996-2264">Identity Card</span></span>
- <span data-ttu-id="13996-2265">ID</span><span class="sxs-lookup"><span data-stu-id="13996-2265">ID</span></span>
- <span data-ttu-id="13996-2266">Identificazione</span><span class="sxs-lookup"><span data-stu-id="13996-2266">Identification</span></span>
- <span data-ttu-id="13996-2267">Personalausweis</span><span class="sxs-lookup"><span data-stu-id="13996-2267">Personalausweis</span></span>
- <span data-ttu-id="13996-2268">Identifizierungsnummer</span><span class="sxs-lookup"><span data-stu-id="13996-2268">Identifizierungsnummer</span></span>
- <span data-ttu-id="13996-2269">Ausweis</span><span class="sxs-lookup"><span data-stu-id="13996-2269">Ausweis</span></span>
- <span data-ttu-id="13996-2270">Identifikation</span><span class="sxs-lookup"><span data-stu-id="13996-2270">Identifikation</span></span>
   
## <a name="greece-national-id-card"></a><span data-ttu-id="13996-2271">Carta d'identità (Grecia)</span><span class="sxs-lookup"><span data-stu-id="13996-2271">Greece National ID Card</span></span>

### <a name="format"></a><span data-ttu-id="13996-2272">Formato</span><span class="sxs-lookup"><span data-stu-id="13996-2272">Format</span></span>

<span data-ttu-id="13996-2273">Combinazione di 7-8 lettere e numeri, oltre a un trattino</span><span class="sxs-lookup"><span data-stu-id="13996-2273">Combination of 7-8 letters and numbers plus a dash</span></span>

### <a name="pattern"></a><span data-ttu-id="13996-2274">Modello</span><span class="sxs-lookup"><span data-stu-id="13996-2274">Pattern</span></span>

<span data-ttu-id="13996-2275">Sette lettere e numeri (formato precedente):</span><span class="sxs-lookup"><span data-stu-id="13996-2275">Seven letters and numbers (old format):</span></span>
- <span data-ttu-id="13996-2276">Una lettera (qualsiasi lettera dell'alfabeto greco) </span><span class="sxs-lookup"><span data-stu-id="13996-2276">One letter (any letter of the Greek alphabet)</span></span> 
- <span data-ttu-id="13996-2277">Un trattino</span><span class="sxs-lookup"><span data-stu-id="13996-2277">A dash</span></span> 
- <span data-ttu-id="13996-2278">Sei cifre</span><span class="sxs-lookup"><span data-stu-id="13996-2278">Six digits</span></span>

<span data-ttu-id="13996-2279">Otto lettere e numeri (nuovo formato):</span><span class="sxs-lookup"><span data-stu-id="13996-2279">Eight letters and numbers (new format):</span></span>
- <span data-ttu-id="13996-2280">Due lettere in maiuscolo sia in alfabeto latino che greco (ABEZHIKMNOPTYX) </span><span class="sxs-lookup"><span data-stu-id="13996-2280">Two letters whose uppercase character occurs in both the Greek and Latin alphabets (ABEZHIKMNOPTYX)</span></span> 
- <span data-ttu-id="13996-2281">Un trattino</span><span class="sxs-lookup"><span data-stu-id="13996-2281">A dash</span></span> 
- <span data-ttu-id="13996-2282">Sei cifre</span><span class="sxs-lookup"><span data-stu-id="13996-2282">Six digits</span></span>

### <a name="checksum"></a><span data-ttu-id="13996-2283">Checksum</span><span class="sxs-lookup"><span data-stu-id="13996-2283">Checksum</span></span>

<span data-ttu-id="13996-2284">No</span><span class="sxs-lookup"><span data-stu-id="13996-2284">No</span></span>

### <a name="definition"></a><span data-ttu-id="13996-2285">Definizione</span><span class="sxs-lookup"><span data-stu-id="13996-2285">Definition</span></span>

<span data-ttu-id="13996-2286">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="13996-2286">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="13996-2287">L'espressione regolare Regex_greece_id_card trova il contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="13996-2287">The regular expression Regex_greece_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="13996-2288">Viene trovata una parola chiave da Keyword_greece_id_card.</span><span class="sxs-lookup"><span data-stu-id="13996-2288">A keyword from Keyword_greece_id_card is found.</span></span>

```
<!-- Greece National ID Card -->
<Entity id="82568215-1da1-46d3-874a-d2294d81b5ac" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Regex_greece_id_card"/>
     <Match idRef="Keyword_greece_id_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="13996-2289">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="13996-2289">Keywords</span></span>

#### <a name="keywordgreeceidcard"></a><span data-ttu-id="13996-2290">Keyword_greece_id_card</span><span class="sxs-lookup"><span data-stu-id="13996-2290">Keyword_greece_id_card</span></span>

- <span data-ttu-id="13996-2291">Carta d’identità greca</span><span class="sxs-lookup"><span data-stu-id="13996-2291">Greek identity Card</span></span>
- <span data-ttu-id="13996-2292">Tautotita</span><span class="sxs-lookup"><span data-stu-id="13996-2292">Tautotita</span></span>
- <span data-ttu-id="13996-2293">Δελτίο αστυνομικής ταυτότητας</span><span class="sxs-lookup"><span data-stu-id="13996-2293">Δελτίο αστυνομικής ταυτότητας</span></span>
- <span data-ttu-id="13996-2294">Ταυτότητα</span><span class="sxs-lookup"><span data-stu-id="13996-2294">Ταυτότητα</span></span>
   
## <a name="hong-kong-identity-card-hkid-number"></a><span data-ttu-id="13996-2295">Hong Kong - Numero di carta di identità (HKID)</span><span class="sxs-lookup"><span data-stu-id="13996-2295">Hong Kong Identity Card (HKID) Number</span></span>

### <a name="format"></a><span data-ttu-id="13996-2296">Formato</span><span class="sxs-lookup"><span data-stu-id="13996-2296">Format</span></span>

<span data-ttu-id="13996-2297">Combinazione di 8-9 lettere e numeri. Facoltativamente, l’ultimo carattere può essere racchiuso tra parentesi</span><span class="sxs-lookup"><span data-stu-id="13996-2297">Combination of 8-9 letters and numbers plus optional parentheses around the final character</span></span>

### <a name="pattern"></a><span data-ttu-id="13996-2298">Modello</span><span class="sxs-lookup"><span data-stu-id="13996-2298">Pattern</span></span>

<span data-ttu-id="13996-2299">Combinazione di 8-9 lettere:</span><span class="sxs-lookup"><span data-stu-id="13996-2299">Combination of 8-9 letters:</span></span>
- <span data-ttu-id="13996-2300">1-2 lettere (senza distinzione tra maiuscole e minuscole)</span><span class="sxs-lookup"><span data-stu-id="13996-2300">1-2 letters (not case sensitive)</span></span> 
- <span data-ttu-id="13996-2301">Sei cifre</span><span class="sxs-lookup"><span data-stu-id="13996-2301">Six digits</span></span> 
- <span data-ttu-id="13996-2302">L'ultimo carattere (qualsiasi cifra o la lettera A), è rappresentato dal numero di controllo. Facoltativamente, può essere racchiuso tra parentesi.</span><span class="sxs-lookup"><span data-stu-id="13996-2302">The final character (any digit or the letter A), which is the check digit and is optionally enclosed in parentheses.</span></span>

### <a name="checksum"></a><span data-ttu-id="13996-2303">Checksum</span><span class="sxs-lookup"><span data-stu-id="13996-2303">Checksum</span></span>

<span data-ttu-id="13996-2304">Sì</span><span class="sxs-lookup"><span data-stu-id="13996-2304">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="13996-2305">Definizione</span><span class="sxs-lookup"><span data-stu-id="13996-2305">Definition</span></span>

<span data-ttu-id="13996-2306">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="13996-2306">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="13996-2307">La funzione Func_hong_kong_id_card trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="13996-2307">The function Func_hong_kong_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="13996-2308">Viene trovata una parola chiave da Keyword_hong_kong_id_card.</span><span class="sxs-lookup"><span data-stu-id="13996-2308">A keyword from Keyword_hong_kong_id_card is found.</span></span>
- <span data-ttu-id="13996-2309">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="13996-2309">The checksum passes.</span></span>

<span data-ttu-id="13996-2310">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 65%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="13996-2310">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="13996-2311">La funzione Func_hong_kong_id_card trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="13996-2311">The function Func_hong_kong_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="13996-2312">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="13996-2312">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="13996-2313">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="13996-2313">Keywords</span></span>

#### <a name="keywordhongkongidcard"></a><span data-ttu-id="13996-2314">Keyword_hong_kong_id_card</span><span class="sxs-lookup"><span data-stu-id="13996-2314">Keyword_hong_kong_id_card</span></span>

- <span data-ttu-id="13996-2315">carta di identità di Hong Kong</span><span class="sxs-lookup"><span data-stu-id="13996-2315">hong kong identity card</span></span>
- <span data-ttu-id="13996-2316">HKIDC</span><span class="sxs-lookup"><span data-stu-id="13996-2316">HKIDC</span></span>
- <span data-ttu-id="13996-2317">id card</span><span class="sxs-lookup"><span data-stu-id="13996-2317">id card</span></span>
- <span data-ttu-id="13996-2318">carta di identità</span><span class="sxs-lookup"><span data-stu-id="13996-2318">identity card</span></span>
- <span data-ttu-id="13996-2319">carta di identità HK</span><span class="sxs-lookup"><span data-stu-id="13996-2319">hk identity card</span></span>
- <span data-ttu-id="13996-2320">ID Hong Kong</span><span class="sxs-lookup"><span data-stu-id="13996-2320">hong kong id</span></span>
- <span data-ttu-id="13996-2321">香港身份證</span><span class="sxs-lookup"><span data-stu-id="13996-2321">香港身份證</span></span>
- <span data-ttu-id="13996-2322">香港永久性居民身份證</span><span class="sxs-lookup"><span data-stu-id="13996-2322">香港永久性居民身份證</span></span>
- <span data-ttu-id="13996-2323">身份證</span><span class="sxs-lookup"><span data-stu-id="13996-2323">身份證</span></span>
- <span data-ttu-id="13996-2324">身份証</span><span class="sxs-lookup"><span data-stu-id="13996-2324">身份証</span></span>
- <span data-ttu-id="13996-2325">身分證</span><span class="sxs-lookup"><span data-stu-id="13996-2325">身分證</span></span>
- <span data-ttu-id="13996-2326">身分証</span><span class="sxs-lookup"><span data-stu-id="13996-2326">身分証</span></span>
- <span data-ttu-id="13996-2327">香港身份証</span><span class="sxs-lookup"><span data-stu-id="13996-2327">香港身份証</span></span>
- <span data-ttu-id="13996-2328">香港身分證</span><span class="sxs-lookup"><span data-stu-id="13996-2328">香港身分證</span></span>
- <span data-ttu-id="13996-2329">香港身分証</span><span class="sxs-lookup"><span data-stu-id="13996-2329">香港身分証</span></span>
- <span data-ttu-id="13996-2330">香港身份證</span><span class="sxs-lookup"><span data-stu-id="13996-2330">香港身份證</span></span>
- <span data-ttu-id="13996-2331">香港居民身份證</span><span class="sxs-lookup"><span data-stu-id="13996-2331">香港居民身份證</span></span>
- <span data-ttu-id="13996-2332">香港居民身份証</span><span class="sxs-lookup"><span data-stu-id="13996-2332">香港居民身份証</span></span>
- <span data-ttu-id="13996-2333">香港居民身分證</span><span class="sxs-lookup"><span data-stu-id="13996-2333">香港居民身分證</span></span>
- <span data-ttu-id="13996-2334">香港居民身分証</span><span class="sxs-lookup"><span data-stu-id="13996-2334">香港居民身分証</span></span>
- <span data-ttu-id="13996-2335">香港永久性居民身份証</span><span class="sxs-lookup"><span data-stu-id="13996-2335">香港永久性居民身份証</span></span>
- <span data-ttu-id="13996-2336">香港永久性居民身分證</span><span class="sxs-lookup"><span data-stu-id="13996-2336">香港永久性居民身分證</span></span>
- <span data-ttu-id="13996-2337">香港永久性居民身分証</span><span class="sxs-lookup"><span data-stu-id="13996-2337">香港永久性居民身分証</span></span>
- <span data-ttu-id="13996-2338">香港永久性居民身份證</span><span class="sxs-lookup"><span data-stu-id="13996-2338">香港永久性居民身份證</span></span>
- <span data-ttu-id="13996-2339">香港非永久性居民身份證</span><span class="sxs-lookup"><span data-stu-id="13996-2339">香港非永久性居民身份證</span></span>
- <span data-ttu-id="13996-2340">香港非永久性居民身份証</span><span class="sxs-lookup"><span data-stu-id="13996-2340">香港非永久性居民身份証</span></span>
- <span data-ttu-id="13996-2341">香港非永久性居民身分證</span><span class="sxs-lookup"><span data-stu-id="13996-2341">香港非永久性居民身分證</span></span>
- <span data-ttu-id="13996-2342">香港非永久性居民身分証</span><span class="sxs-lookup"><span data-stu-id="13996-2342">香港非永久性居民身分証</span></span>
- <span data-ttu-id="13996-2343">香港特別行政區永久性居民身份證</span><span class="sxs-lookup"><span data-stu-id="13996-2343">香港特別行政區永久性居民身份證</span></span>
- <span data-ttu-id="13996-2344">香港特別行政區永久性居民身份証</span><span class="sxs-lookup"><span data-stu-id="13996-2344">香港特別行政區永久性居民身份証</span></span>
- <span data-ttu-id="13996-2345">香港特別行政區永久性居民身分證</span><span class="sxs-lookup"><span data-stu-id="13996-2345">香港特別行政區永久性居民身分證</span></span>
- <span data-ttu-id="13996-2346">香港特別行政區永久性居民身分証</span><span class="sxs-lookup"><span data-stu-id="13996-2346">香港特別行政區永久性居民身分証</span></span>
- <span data-ttu-id="13996-2347">香港特別行政區非永久性居民身份證</span><span class="sxs-lookup"><span data-stu-id="13996-2347">香港特別行政區非永久性居民身份證</span></span>
- <span data-ttu-id="13996-2348">香港特別行政區非永久性居民身份証</span><span class="sxs-lookup"><span data-stu-id="13996-2348">香港特別行政區非永久性居民身份証</span></span>
- <span data-ttu-id="13996-2349">香港特別行政區非永久性居民身分證</span><span class="sxs-lookup"><span data-stu-id="13996-2349">香港特別行政區非永久性居民身分證</span></span>
- <span data-ttu-id="13996-2350">香港特別行政區非永久性居民身分証</span><span class="sxs-lookup"><span data-stu-id="13996-2350">香港特別行政區非永久性居民身分証</span></span>
   
## <a name="india-permanent-account-number-pan"></a><span data-ttu-id="13996-2351">India - Numero di conto permanente (PAN)</span><span class="sxs-lookup"><span data-stu-id="13996-2351">India Permanent Account Number (PAN)</span></span>

### <a name="format"></a><span data-ttu-id="13996-2352">Formato</span><span class="sxs-lookup"><span data-stu-id="13996-2352">Format</span></span>

<span data-ttu-id="13996-2353">10 lettere o cifre</span><span class="sxs-lookup"><span data-stu-id="13996-2353">10 letters or digits</span></span>

### <a name="pattern"></a><span data-ttu-id="13996-2354">Modello</span><span class="sxs-lookup"><span data-stu-id="13996-2354">Pattern</span></span>

<span data-ttu-id="13996-2355">10 lettere o cifre:</span><span class="sxs-lookup"><span data-stu-id="13996-2355">10 letters or digits:</span></span>
- <span data-ttu-id="13996-2356">Cinque lettere (senza distinzione tra maiuscole e minuscole)</span><span class="sxs-lookup"><span data-stu-id="13996-2356">Five letters (not case sensitive)</span></span> 
- <span data-ttu-id="13996-2357">Quattro cifre</span><span class="sxs-lookup"><span data-stu-id="13996-2357">Four digits</span></span> 
- <span data-ttu-id="13996-2358">Una lettera, ovvero una cifra di controllo alfabetica</span><span class="sxs-lookup"><span data-stu-id="13996-2358">A letter which is an alphabetic check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="13996-2359">Checksum</span><span class="sxs-lookup"><span data-stu-id="13996-2359">Checksum</span></span>

<span data-ttu-id="13996-2360">Sì</span><span class="sxs-lookup"><span data-stu-id="13996-2360">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="13996-2361">Definizione</span><span class="sxs-lookup"><span data-stu-id="13996-2361">Definition</span></span>

<span data-ttu-id="13996-2362">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="13996-2362">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="13996-2363">L'espressione regolare Regex_india_permanent_account_number trova il contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="13996-2363">The regular expression Regex_india_permanent_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="13996-2364">Viene trovata una parola chiave da Keyword_india_permanent_account_number.</span><span class="sxs-lookup"><span data-stu-id="13996-2364">A keyword from Keyword_india_permanent_account_number is found.</span></span>
- <span data-ttu-id="13996-2365">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="13996-2365">The checksum passes.</span></span>

```
<!-- India Permanent Account Number -->
<Entity id="2602bfee-9bb0-47a5-a7a6-2bf3053e2804" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Regex_india_permanent_account_number"/>
     <Match idRef="Keyword_india_permanent_account_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="13996-2366">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="13996-2366">Keywords</span></span>

#### <a name="keywordindiapermanentaccountnumber"></a><span data-ttu-id="13996-2367">Keyword_india_permanent_account_number</span><span class="sxs-lookup"><span data-stu-id="13996-2367">Keyword_india_permanent_account_number</span></span>

- <span data-ttu-id="13996-2368">Permanent Account Number</span><span class="sxs-lookup"><span data-stu-id="13996-2368">Permanent Account Number</span></span> 
- <span data-ttu-id="13996-2369">PAN</span><span class="sxs-lookup"><span data-stu-id="13996-2369">PAN</span></span> 
   
## <a name="india-unique-identification-aadhaar-number"></a><span data-ttu-id="13996-2370">India - Numero di identificazione univoco (Aadhaar)</span><span class="sxs-lookup"><span data-stu-id="13996-2370">India Unique Identification (Aadhaar) Number</span></span>

### <a name="format"></a><span data-ttu-id="13996-2371">Formato</span><span class="sxs-lookup"><span data-stu-id="13996-2371">Format</span></span>

<span data-ttu-id="13996-2372">12 cifre contenenti spazi o trattini facoltativi </span><span class="sxs-lookup"><span data-stu-id="13996-2372">12 digits containing optional spaces or dashes</span></span>

### <a name="pattern"></a><span data-ttu-id="13996-2373">Modello</span><span class="sxs-lookup"><span data-stu-id="13996-2373">Pattern</span></span>

<span data-ttu-id="13996-2374">12 cifre:</span><span class="sxs-lookup"><span data-stu-id="13996-2374">12 digits:</span></span>
- <span data-ttu-id="13996-2375">Quattro cifre</span><span class="sxs-lookup"><span data-stu-id="13996-2375">Four digits</span></span> 
- <span data-ttu-id="13996-2376">Uno spazio o un trattino facoltativo </span><span class="sxs-lookup"><span data-stu-id="13996-2376">An optional space or dash</span></span> 
- <span data-ttu-id="13996-2377">Quattro cifre</span><span class="sxs-lookup"><span data-stu-id="13996-2377">Four digits</span></span> 
- <span data-ttu-id="13996-2378">Uno spazio o un trattino facoltativo </span><span class="sxs-lookup"><span data-stu-id="13996-2378">An optional space or dash</span></span> 
- <span data-ttu-id="13996-2379">L'ultimo carattere, ovvero il numero di controllo</span><span class="sxs-lookup"><span data-stu-id="13996-2379">The final digit which is the check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="13996-2380">Checksum</span><span class="sxs-lookup"><span data-stu-id="13996-2380">Checksum</span></span>

<span data-ttu-id="13996-2381">Sì</span><span class="sxs-lookup"><span data-stu-id="13996-2381">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="13996-2382">Definizione</span><span class="sxs-lookup"><span data-stu-id="13996-2382">Definition</span></span>

<span data-ttu-id="13996-2383">Un criterio DLP è 85% fiducioso di aver rilevato questo tipo di informazioni riservate se, entro 300 caratteri: la funzione Func_india_aadhaar trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="13996-2383">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The function Func_india_aadhaar finds content that matches the pattern.</span></span>
<span data-ttu-id="13996-2384">Viene trovata una parola chiave da Keyword_india_aadhar.</span><span class="sxs-lookup"><span data-stu-id="13996-2384">A keyword from Keyword_india_aadhar is found.</span></span>
<span data-ttu-id="13996-2385">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="13996-2385">The checksum passes.</span></span>
<span data-ttu-id="13996-2386">Un criterio DLP è 75% fiducioso di aver rilevato questo tipo di informazioni riservate se, entro 300 caratteri: la funzione Func_india_aadhaar trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="13996-2386">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The function Func_india_aadhaar finds content that matches the pattern.</span></span>
<span data-ttu-id="13996-2387">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="13996-2387">The checksum passes.</span></span>
<!-- India Unique Identification (Aadhaar) number -->
<span data-ttu-id="13996-2388"><Entity id="1ca46b29-76f5-4f46-9383-cfa15e91048f" recommendedConfidence="85" patternsProximity="300"> <Pattern confidenceLevel="85"> <IdMatch idRef="Func_india_aadhaar"/> <Match idRef="Keyword_india_aadhar"/> </Pattern> <Pattern confidenceLevel="75"> <IdMatch idRef="Func_india_aadhaar"/> </Pattern>
</Entity></span><span class="sxs-lookup"><span data-stu-id="13996-2388"></span></span>

### <a name="keywords"></a><span data-ttu-id="13996-2389">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="13996-2389">Keywords</span></span>
   
#### <a name="keywordindiaaadhar"></a><span data-ttu-id="13996-2390">Keyword_india_aadhar</span><span class="sxs-lookup"><span data-stu-id="13996-2390">Keyword_india_aadhar</span></span>
- <span data-ttu-id="13996-2391">Aadhar</span><span class="sxs-lookup"><span data-stu-id="13996-2391">Aadhar</span></span>
- <span data-ttu-id="13996-2392">Aadhaar</span><span class="sxs-lookup"><span data-stu-id="13996-2392">Aadhaar</span></span>
- <span data-ttu-id="13996-2393">UID</span><span class="sxs-lookup"><span data-stu-id="13996-2393">UID</span></span>
- <span data-ttu-id="13996-2394">आधार</span><span class="sxs-lookup"><span data-stu-id="13996-2394">आधार</span></span>
   
## <a name="indonesia-identity-card-ktp-number"></a><span data-ttu-id="13996-2395">Indonesia - Numero di carta di identità (KTP)</span><span class="sxs-lookup"><span data-stu-id="13996-2395">Indonesia Identity Card (KTP) Number</span></span>

### <a name="format"></a><span data-ttu-id="13996-2396">Formato</span><span class="sxs-lookup"><span data-stu-id="13996-2396">Format</span></span>

<span data-ttu-id="13996-2397">16 cifre contenenti punti facoltativi </span><span class="sxs-lookup"><span data-stu-id="13996-2397">16 digits containing optional periods</span></span>

### <a name="pattern"></a><span data-ttu-id="13996-2398">Modello</span><span class="sxs-lookup"><span data-stu-id="13996-2398">Pattern</span></span>

<span data-ttu-id="13996-2399">16 cifre:</span><span class="sxs-lookup"><span data-stu-id="13996-2399">16 digits:</span></span>
- <span data-ttu-id="13996-2400">Codice provincia a due cifre </span><span class="sxs-lookup"><span data-stu-id="13996-2400">Two-digit province code</span></span> 
- <span data-ttu-id="13996-2401">Un punto (facoltativo) </span><span class="sxs-lookup"><span data-stu-id="13996-2401">A period (optional)</span></span> 
- <span data-ttu-id="13996-2402">Codice città o area a due cifre </span><span class="sxs-lookup"><span data-stu-id="13996-2402">Two-digit regency or city code</span></span> 
- <span data-ttu-id="13996-2403">Codice sotto-distretto a due cifre </span><span class="sxs-lookup"><span data-stu-id="13996-2403">Two-digit subdistrict code</span></span> 
- <span data-ttu-id="13996-2404">Un punto (facoltativo) </span><span class="sxs-lookup"><span data-stu-id="13996-2404">A period (optional)</span></span> 
- <span data-ttu-id="13996-2405">Sei cifre nel formato GGMMAA, ovvero la data di nascita</span><span class="sxs-lookup"><span data-stu-id="13996-2405">Six digits in the format DDMMYY which are the date of birth</span></span> 
- <span data-ttu-id="13996-2406">Un punto (facoltativo) </span><span class="sxs-lookup"><span data-stu-id="13996-2406">A period (optional)</span></span> 
- <span data-ttu-id="13996-2407">Quattro cifre</span><span class="sxs-lookup"><span data-stu-id="13996-2407">Four digits</span></span>

### <a name="checksum"></a><span data-ttu-id="13996-2408">Checksum</span><span class="sxs-lookup"><span data-stu-id="13996-2408">Checksum</span></span>

<span data-ttu-id="13996-2409">No</span><span class="sxs-lookup"><span data-stu-id="13996-2409">No</span></span>

### <a name="definition"></a><span data-ttu-id="13996-2410">Definizione</span><span class="sxs-lookup"><span data-stu-id="13996-2410">Definition</span></span>

<span data-ttu-id="13996-2411">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="13996-2411">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="13996-2412">L'espressione regolare Regex_indonesia_id_card trova il contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="13996-2412">The regular expression Regex_indonesia_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="13996-2413">Viene trovata una parola chiave da Keyword_indonesia_id_card.</span><span class="sxs-lookup"><span data-stu-id="13996-2413">A keyword from Keyword_indonesia_id_card is found.</span></span>

<span data-ttu-id="13996-2414">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="13996-2414">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="13996-2415">L'espressione regolare Regex_indonesia_id_card trova il contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="13996-2415">The regular expression Regex_indonesia_id_card finds content that matches the pattern.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="13996-2416">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="13996-2416">Keywords</span></span>
   
#### <a name="keywordindonesiaidcard"></a><span data-ttu-id="13996-2417">Keyword_indonesia_id_card</span><span class="sxs-lookup"><span data-stu-id="13996-2417">Keyword_indonesia_id_card</span></span>

- <span data-ttu-id="13996-2418">KTP</span><span class="sxs-lookup"><span data-stu-id="13996-2418">KTP</span></span>
- <span data-ttu-id="13996-2419">Kartu Tanda Penduduk</span><span class="sxs-lookup"><span data-stu-id="13996-2419">Kartu Tanda Penduduk</span></span> 
- <span data-ttu-id="13996-2420">Nomor Induk Kependudukan</span><span class="sxs-lookup"><span data-stu-id="13996-2420">Nomor Induk Kependudukan</span></span> 
   
## <a name="international-banking-account-number-iban"></a><span data-ttu-id="13996-2421">Numero di conto bancario internazionale (IBAN)</span><span class="sxs-lookup"><span data-stu-id="13996-2421">International Banking Account Number (IBAN)</span></span>

### <a name="format"></a><span data-ttu-id="13996-2422">Formato</span><span class="sxs-lookup"><span data-stu-id="13996-2422">Format</span></span>

<span data-ttu-id="13996-2423">Codice paese (due lettere) più cifre di controllo (due cifre) più numero BBAN (fino a 30 caratteri)</span><span class="sxs-lookup"><span data-stu-id="13996-2423">Country code (two letters) plus check digits (two digits) plus bban number (up to 30 characters)</span></span>

### <a name="pattern"></a><span data-ttu-id="13996-2424">Modello</span><span class="sxs-lookup"><span data-stu-id="13996-2424">Pattern</span></span>

<span data-ttu-id="13996-2425">Il modello deve includere tutti gli elementi seguenti:</span><span class="sxs-lookup"><span data-stu-id="13996-2425">Pattern must include all of the following:</span></span>

- <span data-ttu-id="13996-2426">Codice paese a due lettere</span><span class="sxs-lookup"><span data-stu-id="13996-2426">Two-letter country code</span></span>
- <span data-ttu-id="13996-2427">Due cifre di controllo (seguite da uno spazio facoltativo)</span><span class="sxs-lookup"><span data-stu-id="13996-2427">Two check digits (followed by an optional space)</span></span> 
- <span data-ttu-id="13996-2428">1-7 gruppi di quattro lettere o cifre (possono essere separati da spazi)</span><span class="sxs-lookup"><span data-stu-id="13996-2428">1-7 groups of four letters or digits (can be separated by spaces)</span></span>
- <span data-ttu-id="13996-2429">1-3 lettere o cifre</span><span class="sxs-lookup"><span data-stu-id="13996-2429">1-3 letters or digits</span></span>

<span data-ttu-id="13996-2430">Il formato di ogni paese è leggermente diverso.</span><span class="sxs-lookup"><span data-stu-id="13996-2430">The format for each country is slightly different.</span></span> <span data-ttu-id="13996-2431">Il tipo di informazioni riservate IBAN copre questi 60 paesi:</span><span class="sxs-lookup"><span data-stu-id="13996-2431">The IBAN sensitive information type covers these 60 countries:</span></span>

<span data-ttu-id="13996-2432">ad, AE, al, at, AZ, BA, be, BG, BH, ch, CR, CY, CZ, de, DK, do, EE, es, Fi, fo, fr, GB, GE, Gi, GL, gr, HR, HU, IE, il, is, it, kW, KZ, lb, li, LT, Lu, LV, MC, MD, me, MK, Mr, MT, MU , NL, no, pl, PT, ro, RS, SA, se, si, SK, SM, TN, TR, VG</span><span class="sxs-lookup"><span data-stu-id="13996-2432">ad, ae, al, at, az, ba, be, bg, bh, ch, cr, cy, cz, de, dk, do, ee, es, fi, fo, fr, gb, ge, gi, gl, gr, hr, hu, ie, il, is, it, kw, kz, lb, li, lt, lu, lv, mc, md, me, mk, mr, mt, mu, nl, no, pl, pt, ro, rs, sa, se, si, sk, sm, tn, tr, vg</span></span>

### <a name="checksum"></a><span data-ttu-id="13996-2433">Checksum</span><span class="sxs-lookup"><span data-stu-id="13996-2433">Checksum</span></span>

<span data-ttu-id="13996-2434">Sì</span><span class="sxs-lookup"><span data-stu-id="13996-2434">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="13996-2435">Definizione</span><span class="sxs-lookup"><span data-stu-id="13996-2435">Definition</span></span>

<span data-ttu-id="13996-2436">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="13996-2436">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="13996-2437">La funzione Func_iban restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="13996-2437">The function Func_iban finds content that matches the pattern.</span></span>
- <span data-ttu-id="13996-2438">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="13996-2438">The checksum passes.</span></span>

```
<Entity id="e7dc4711-11b7-4cb0-b88b-2c394a771f0e" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_iban" />
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="13996-2439">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="13996-2439">Keywords</span></span>

<span data-ttu-id="13996-2440">Nessuno</span><span class="sxs-lookup"><span data-stu-id="13996-2440">None</span></span>

   
## <a name="ip-address"></a><span data-ttu-id="13996-2441">Indirizzo IP</span><span class="sxs-lookup"><span data-stu-id="13996-2441">IP Address</span></span>

### <a name="format"></a><span data-ttu-id="13996-2442">Formato</span><span class="sxs-lookup"><span data-stu-id="13996-2442">Format</span></span>

#### <a name="ipv4"></a><span data-ttu-id="13996-2443">IPv4</span><span class="sxs-lookup"><span data-stu-id="13996-2443">IPv4:</span></span>
<span data-ttu-id="13996-2444">Modello complesso che rappresenta le versioni formattate (punti) e quelle non formattate (senza punti) degli indirizzi IPv4</span><span class="sxs-lookup"><span data-stu-id="13996-2444">Complex pattern which accounts for formatted (periods) and unformatted (no periods) versions of the IPv4 addresses</span></span>

#### <a name="ipv6"></a><span data-ttu-id="13996-2445">IPv6</span><span class="sxs-lookup"><span data-stu-id="13996-2445">IPv6:</span></span>
<span data-ttu-id="13996-2446">Modello complesso che rappresenta i numeri dell'indirizzo IPv6 non formattati (include i due punti)</span><span class="sxs-lookup"><span data-stu-id="13996-2446">Complex pattern which accounts for formatted IPv6 numbers (which include colons)</span></span>

### <a name="pattern"></a><span data-ttu-id="13996-2447">Modello</span><span class="sxs-lookup"><span data-stu-id="13996-2447">Pattern</span></span>

### <a name="checksum"></a><span data-ttu-id="13996-2448">Checksum</span><span class="sxs-lookup"><span data-stu-id="13996-2448">Checksum</span></span>

<span data-ttu-id="13996-2449">No</span><span class="sxs-lookup"><span data-stu-id="13996-2449">No</span></span>

### <a name="definition"></a><span data-ttu-id="13996-2450">Definizione</span><span class="sxs-lookup"><span data-stu-id="13996-2450">Definition</span></span>

<span data-ttu-id="13996-2451">Nel caso di IPv6, un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="13996-2451">For IPv6, a DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="13996-2452">L'espressione regolare Regex_ipv6_address restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="13996-2452">The regular expression Regex_ipv6_address finds content that matches the pattern.</span></span>
- <span data-ttu-id="13996-2453">Non vengono trovate parole chiave da Keyword_ipaddress.</span><span class="sxs-lookup"><span data-stu-id="13996-2453">No keyword from Keyword_ipaddress is found.</span></span>

<span data-ttu-id="13996-2454">Nel caso di IPv4, un criterio DLP rileva questo tipo di informazioni con una probabilità del 95%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="13996-2454">For IPv4, a DLP policy is 95% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="13996-2455">L'espressione regolare Regex_ipv4_address restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="13996-2455">The regular expression Regex_ipv4_address finds content that matches the pattern.</span></span>
- <span data-ttu-id="13996-2456">Viene trovata una parola chiave da Keyword_ipaddress.</span><span class="sxs-lookup"><span data-stu-id="13996-2456">A keyword from Keyword_ipaddress is found.</span></span>

<span data-ttu-id="13996-2457">Nel caso di IPv6, un criterio DLP rileva questo tipo di informazioni con una probabilità del 95%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="13996-2457">For IPv6, a DLP policy is 95% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="13996-2458">L'espressione regolare Regex_ipv6_address restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="13996-2458">The regular expression Regex_ipv6_address finds content that matches the pattern.</span></span>
- <span data-ttu-id="13996-2459">Non vengono trovate parole chiave da Keyword_ipaddress.</span><span class="sxs-lookup"><span data-stu-id="13996-2459">No keyword from Keyword_ipaddress is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="13996-2460">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="13996-2460">Keywords</span></span>

#### <a name="keywordipaddress"></a><span data-ttu-id="13996-2461">Keyword_ipaddress</span><span class="sxs-lookup"><span data-stu-id="13996-2461">Keyword_ipaddress</span></span>

- <span data-ttu-id="13996-2462">IP (per questa parola chiave viene fatta distinzione tra maiuscole e minuscole)</span><span class="sxs-lookup"><span data-stu-id="13996-2462">IP (this keyword is case sensitive)</span></span>
- <span data-ttu-id="13996-2463">ip address</span><span class="sxs-lookup"><span data-stu-id="13996-2463">ip address</span></span> 
- <span data-ttu-id="13996-2464">Indirizzi IP</span><span class="sxs-lookup"><span data-stu-id="13996-2464">ip addresses</span></span>
- <span data-ttu-id="13996-2465">internet protocol</span><span class="sxs-lookup"><span data-stu-id="13996-2465">internet protocol</span></span>
- <span data-ttu-id="13996-2466">IP-כתובת ה</span><span class="sxs-lookup"><span data-stu-id="13996-2466">IP-כתובת ה</span></span> 
   
## <a name="international-classification-of-diseases-icd-10-cm"></a><span data-ttu-id="13996-2467">Classificazione internazionale delle malattie (ICD-10-CM)</span><span class="sxs-lookup"><span data-stu-id="13996-2467">International Classification of Diseases (ICD-10-CM)</span></span>

### <a name="format"></a><span data-ttu-id="13996-2468">Formato</span><span class="sxs-lookup"><span data-stu-id="13996-2468">Format</span></span>

<span data-ttu-id="13996-2469">Dizionario</span><span class="sxs-lookup"><span data-stu-id="13996-2469">Dictionary</span></span>

### <a name="pattern"></a><span data-ttu-id="13996-2470">Modello</span><span class="sxs-lookup"><span data-stu-id="13996-2470">Pattern</span></span>

<span data-ttu-id="13996-2471">Parola chiave</span><span class="sxs-lookup"><span data-stu-id="13996-2471">Keyword</span></span>

### <a name="checksum"></a><span data-ttu-id="13996-2472">Checksum</span><span class="sxs-lookup"><span data-stu-id="13996-2472">Checksum</span></span>

<span data-ttu-id="13996-2473">No</span><span class="sxs-lookup"><span data-stu-id="13996-2473">No</span></span>

### <a name="definition"></a><span data-ttu-id="13996-2474">Definizione</span><span class="sxs-lookup"><span data-stu-id="13996-2474">Definition</span></span>

<span data-ttu-id="13996-2475">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="13996-2475">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="13996-2476">Viene trovata una parola chiave da Dictionary_icd_10_cm.</span><span class="sxs-lookup"><span data-stu-id="13996-2476">A keyword from Dictionary_icd_10_cm is found.</span></span>

```
      <!-- ICD-10 CM -->
      <Entity id="3356946c-6bb7-449b-b253-6ffa419c0ce7" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Dictionary_icd_10_cm" />
        </Pattern>
      </Entity>
```

<span data-ttu-id="13996-2477">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="13996-2477">Keywords</span></span>

<span data-ttu-id="13996-2478">Qualsiasi termine del dizionario di parole chiave Dictionary_icd_10_cm, basato sulla [classificazione internazionale delle malattie, la decima revisione, la modifica clinica (ICD-10-cm)](https://go.microsoft.com/fwlink/?linkid=852604).</span><span class="sxs-lookup"><span data-stu-id="13996-2478">Any term from the Dictionary_icd_10_cm keyword dictionary, which is based on the [International Classification of Diseases, Tenth Revision, Clinical Modification (ICD-10-CM)](https://go.microsoft.com/fwlink/?linkid=852604).</span></span> <span data-ttu-id="13996-2479">Questo tipo di ricerca viene visualizzato solo per il termine, non per i codici assicurativi.</span><span class="sxs-lookup"><span data-stu-id="13996-2479">This type looks only for the term, not the insurance codes.</span></span>

   
## <a name="international-classification-of-diseases-icd-9-cm"></a><span data-ttu-id="13996-2480">Classificazione internazionale delle malattie (ICD-9-CM)</span><span class="sxs-lookup"><span data-stu-id="13996-2480">International Classification of Diseases (ICD-9-CM)</span></span>

### <a name="format"></a><span data-ttu-id="13996-2481">Formato</span><span class="sxs-lookup"><span data-stu-id="13996-2481">Format</span></span>

<span data-ttu-id="13996-2482">Dizionario</span><span class="sxs-lookup"><span data-stu-id="13996-2482">Dictionary</span></span>

### <a name="pattern"></a><span data-ttu-id="13996-2483">Modello</span><span class="sxs-lookup"><span data-stu-id="13996-2483">Pattern</span></span>

<span data-ttu-id="13996-2484">Parola chiave</span><span class="sxs-lookup"><span data-stu-id="13996-2484">Keyword</span></span>

### <a name="checksum"></a><span data-ttu-id="13996-2485">Checksum</span><span class="sxs-lookup"><span data-stu-id="13996-2485">Checksum</span></span>

<span data-ttu-id="13996-2486">No</span><span class="sxs-lookup"><span data-stu-id="13996-2486">No</span></span>

### <a name="definition"></a><span data-ttu-id="13996-2487">Definizione</span><span class="sxs-lookup"><span data-stu-id="13996-2487">Definition</span></span>

<span data-ttu-id="13996-2488">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="13996-2488">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="13996-2489">Viene trovata una parola chiave da Dictionary_icd_9_cm.</span><span class="sxs-lookup"><span data-stu-id="13996-2489">A keyword from Dictionary_icd_9_cm is found.</span></span>

```
      <Entity id="fa3f9c74-ee07-4c52-b5f2-085d6b2c0ec4" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Dictionary_icd_9_cm" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a><span data-ttu-id="13996-2490">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="13996-2490">Keywords</span></span>

<span data-ttu-id="13996-2491">Qualsiasi termine del dizionario di parole chiave Dictionary_icd_9_cm, basato sulla [classificazione internazionale delle malattie, la nona revisione, la modifica clinica (ICD-9-cm)](https://go.microsoft.com/fwlink/?linkid=852605).</span><span class="sxs-lookup"><span data-stu-id="13996-2491">Any term from the Dictionary_icd_9_cm keyword dictionary, which is based on the [International Classification of Diseases,Ninth Revision, Clinical Modification (ICD-9-CM)](https://go.microsoft.com/fwlink/?linkid=852605).</span></span> <span data-ttu-id="13996-2492">Questo tipo di ricerca viene visualizzato solo per il termine, non per i codici assicurativi.</span><span class="sxs-lookup"><span data-stu-id="13996-2492">This type looks only for the term, not the insurance codes.</span></span>
   
## <a name="ireland-personal-public-service-pps-number"></a><span data-ttu-id="13996-2493">Irlanda - Numero personale di servizio pubblico (PPS)</span><span class="sxs-lookup"><span data-stu-id="13996-2493">Ireland Personal Public Service (PPS) Number</span></span>

### <a name="format"></a><span data-ttu-id="13996-2494">Formato</span><span class="sxs-lookup"><span data-stu-id="13996-2494">Format</span></span>

<span data-ttu-id="13996-2495">Formato precedente (fino al 31 dicembre 2012):</span><span class="sxs-lookup"><span data-stu-id="13996-2495">Old format (until 31 Dec 2012):</span></span>
- <span data-ttu-id="13996-2496">Sette cifre seguite da 1-2 lettere </span><span class="sxs-lookup"><span data-stu-id="13996-2496">Seven digits followed by 1-2 letters</span></span> 

<span data-ttu-id="13996-2497">Nuovo formato (1 gen 2013 e successive):</span><span class="sxs-lookup"><span data-stu-id="13996-2497">New format (1 Jan 2013 and after):</span></span>
- <span data-ttu-id="13996-2498">Sette cifre seguite da due lettere</span><span class="sxs-lookup"><span data-stu-id="13996-2498">Seven digits followed by two letters</span></span>

### <a name="pattern"></a><span data-ttu-id="13996-2499">Modello</span><span class="sxs-lookup"><span data-stu-id="13996-2499">Pattern</span></span>

<span data-ttu-id="13996-2500">Formato precedente (fino al 31 dicembre 2012):</span><span class="sxs-lookup"><span data-stu-id="13996-2500">Old format (until 31 Dec 2012):</span></span>
- <span data-ttu-id="13996-2501">Sette cifre</span><span class="sxs-lookup"><span data-stu-id="13996-2501">Seven digits</span></span> 
- <span data-ttu-id="13996-2502">1-2 lettere (senza distinzione tra maiuscole e minuscole)</span><span class="sxs-lookup"><span data-stu-id="13996-2502">1-2 letters (not case sensitive)</span></span> 

<span data-ttu-id="13996-2503">Nuovo formato (1 gen 2013 e successive):</span><span class="sxs-lookup"><span data-stu-id="13996-2503">New format (1 Jan 2013 and after):</span></span>
- <span data-ttu-id="13996-2504">Sette cifre</span><span class="sxs-lookup"><span data-stu-id="13996-2504">Seven digits</span></span> 
- <span data-ttu-id="13996-2505">Una lettera (senza distinzione tra maiuscole e minuscole) che corrisponde a una cifra di controllo alfabetica </span><span class="sxs-lookup"><span data-stu-id="13996-2505">A letter (not case sensitive) which is an alphabetic check digit</span></span> 
- <span data-ttu-id="13996-2506">La lettera "A" o "H" (senza distinzione tra maiuscole e minuscole)</span><span class="sxs-lookup"><span data-stu-id="13996-2506">The letter "A" or "H" (not case sensitive)</span></span>

### <a name="checksum"></a><span data-ttu-id="13996-2507">Checksum</span><span class="sxs-lookup"><span data-stu-id="13996-2507">Checksum</span></span>

<span data-ttu-id="13996-2508">Sì</span><span class="sxs-lookup"><span data-stu-id="13996-2508">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="13996-2509">Definizione</span><span class="sxs-lookup"><span data-stu-id="13996-2509">Definition</span></span>

<span data-ttu-id="13996-2510">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="13996-2510">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="13996-2511">La funzione Func_ireland_pps trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="13996-2511">The function Func_ireland_pps finds content that matches the pattern.</span></span>
- <span data-ttu-id="13996-2512">Si verifica una delle situazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="13996-2512">One of the following is true:</span></span>
    - <span data-ttu-id="13996-2513">Viene trovata una parola chiave da Keyword_ireland_pps.</span><span class="sxs-lookup"><span data-stu-id="13996-2513">A keyword from Keyword_ireland_pps is found.</span></span>
    - <span data-ttu-id="13996-2514">La funzione Func_eu_date rileva una data nel formato corretto.</span><span class="sxs-lookup"><span data-stu-id="13996-2514">The function Func_eu_date finds a date in the right date format.</span></span>
- <span data-ttu-id="13996-2515">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="13996-2515">The checksum passes.</span></span>

<span data-ttu-id="13996-2516">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 65%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="13996-2516">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="13996-2517">La funzione Func_ireland_pps trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="13996-2517">The function Func_ireland_pps finds content that matches the pattern.</span></span>
- <span data-ttu-id="13996-2518">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="13996-2518">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="13996-2519">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="13996-2519">Keywords</span></span>

#### <a name="keywordirelandpps"></a><span data-ttu-id="13996-2520">Keyword_ireland_pps</span><span class="sxs-lookup"><span data-stu-id="13996-2520">Keyword_ireland_pps</span></span>

- <span data-ttu-id="13996-2521">Numero personale di servizio pubblico</span><span class="sxs-lookup"><span data-stu-id="13996-2521">Personal Public Service Number</span></span> 
- <span data-ttu-id="13996-2522">Numero PPS</span><span class="sxs-lookup"><span data-stu-id="13996-2522">PPS Number</span></span> 
- <span data-ttu-id="13996-2523">Num. PPS
</span><span class="sxs-lookup"><span data-stu-id="13996-2523">PPS Num</span></span> 
- <span data-ttu-id="13996-2524">N° PPS</span><span class="sxs-lookup"><span data-stu-id="13996-2524">PPS No.</span></span> 
- <span data-ttu-id="13996-2525">PPS #</span><span class="sxs-lookup"><span data-stu-id="13996-2525">PPS #</span></span> 
- <span data-ttu-id="13996-2526">PPS</span><span class="sxs-lookup"><span data-stu-id="13996-2526">PPS#</span></span> 
- <span data-ttu-id="13996-2527">PPSN</span><span class="sxs-lookup"><span data-stu-id="13996-2527">PPSN</span></span> 
- <span data-ttu-id="13996-2528">Scheda servizi pubblici</span><span class="sxs-lookup"><span data-stu-id="13996-2528">Public Services Card</span></span> 
- <span data-ttu-id="13996-2529">Uimhir Phearsanta Seirbhíse Poiblí</span><span class="sxs-lookup"><span data-stu-id="13996-2529">Uimhir Phearsanta Seirbhíse Poiblí</span></span> 
- <span data-ttu-id="13996-2530">Uimh.</span><span class="sxs-lookup"><span data-stu-id="13996-2530">Uimh.</span></span> <span data-ttu-id="13996-2531">PSP</span><span class="sxs-lookup"><span data-stu-id="13996-2531">PSP</span></span> 
- <span data-ttu-id="13996-2532">PSP</span><span class="sxs-lookup"><span data-stu-id="13996-2532">PSP</span></span> 
   
## <a name="israel-bank-account-number"></a><span data-ttu-id="13996-2533">Israele - Numero di conto bancario</span><span class="sxs-lookup"><span data-stu-id="13996-2533">Israel Bank Account Number</span></span>

### <a name="format"></a><span data-ttu-id="13996-2534">Formato</span><span class="sxs-lookup"><span data-stu-id="13996-2534">Format</span></span>

<span data-ttu-id="13996-2535">13 cifre</span><span class="sxs-lookup"><span data-stu-id="13996-2535">13 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="13996-2536">Modello</span><span class="sxs-lookup"><span data-stu-id="13996-2536">Pattern</span></span>

<span data-ttu-id="13996-2537">Formattato</span><span class="sxs-lookup"><span data-stu-id="13996-2537">Formatted:</span></span>
- <span data-ttu-id="13996-2538">Due cifre</span><span class="sxs-lookup"><span data-stu-id="13996-2538">Two digits</span></span> 
- <span data-ttu-id="13996-2539">Un trattino</span><span class="sxs-lookup"><span data-stu-id="13996-2539">A dash</span></span> 
- <span data-ttu-id="13996-2540">Tre cifre</span><span class="sxs-lookup"><span data-stu-id="13996-2540">Three digits</span></span> 
- <span data-ttu-id="13996-2541">Un trattino</span><span class="sxs-lookup"><span data-stu-id="13996-2541">A dash</span></span> 
- <span data-ttu-id="13996-2542">Otto cifre</span><span class="sxs-lookup"><span data-stu-id="13996-2542">Eight digits</span></span>

<span data-ttu-id="13996-2543">Formattato</span><span class="sxs-lookup"><span data-stu-id="13996-2543">Unformatted:</span></span>
- <span data-ttu-id="13996-2544">13 cifre consecutive</span><span class="sxs-lookup"><span data-stu-id="13996-2544">13 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="13996-2545">Checksum</span><span class="sxs-lookup"><span data-stu-id="13996-2545">Checksum</span></span>

<span data-ttu-id="13996-2546">No</span><span class="sxs-lookup"><span data-stu-id="13996-2546">No</span></span>

### <a name="definition"></a><span data-ttu-id="13996-2547">Definizione</span><span class="sxs-lookup"><span data-stu-id="13996-2547">Definition</span></span>

<span data-ttu-id="13996-2548">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="13996-2548">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="13996-2549">L'espressione regolare Regex_israel_bank_account_number restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="13996-2549">The regular expression Regex_israel_bank_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="13996-2550">Viene trovata una parola chiave da Keyword_israel_bank_account_number.</span><span class="sxs-lookup"><span data-stu-id="13996-2550">A keyword from Keyword_israel_bank_account_number is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="13996-2551">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="13996-2551">Keywords</span></span>

#### <a name="keywordisraelbankaccountnumber"></a><span data-ttu-id="13996-2552">Keyword_israel_bank_account_number</span><span class="sxs-lookup"><span data-stu-id="13996-2552">Keyword_israel_bank_account_number</span></span>

- <span data-ttu-id="13996-2553">Bank Account Number</span><span class="sxs-lookup"><span data-stu-id="13996-2553">Bank Account Number</span></span> 
- <span data-ttu-id="13996-2554">Bank Account</span><span class="sxs-lookup"><span data-stu-id="13996-2554">Bank Account</span></span> 
- <span data-ttu-id="13996-2555">Account Number</span><span class="sxs-lookup"><span data-stu-id="13996-2555">Account Number</span></span> 
- <span data-ttu-id="13996-2556">מספר חשבון בנק</span><span class="sxs-lookup"><span data-stu-id="13996-2556">מספר חשבון בנק</span></span> 
   
## <a name="israel-national-id"></a><span data-ttu-id="13996-2557">Carta di identità (Israele)</span><span class="sxs-lookup"><span data-stu-id="13996-2557">Israel National ID</span></span>

### <a name="format"></a><span data-ttu-id="13996-2558">Formato</span><span class="sxs-lookup"><span data-stu-id="13996-2558">Format</span></span>

<span data-ttu-id="13996-2559">9 cifre</span><span class="sxs-lookup"><span data-stu-id="13996-2559">Nine digits</span></span>

### <a name="pattern"></a><span data-ttu-id="13996-2560">Modello</span><span class="sxs-lookup"><span data-stu-id="13996-2560">Pattern</span></span>

<span data-ttu-id="13996-2561">9 cifre consecutive</span><span class="sxs-lookup"><span data-stu-id="13996-2561">Nine consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="13996-2562">Checksum</span><span class="sxs-lookup"><span data-stu-id="13996-2562">Checksum</span></span>

<span data-ttu-id="13996-2563">Sì</span><span class="sxs-lookup"><span data-stu-id="13996-2563">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="13996-2564">Definizione</span><span class="sxs-lookup"><span data-stu-id="13996-2564">Definition</span></span>

<span data-ttu-id="13996-2565">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="13996-2565">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="13996-2566">La funzione Func_israeli_national_id_number restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="13996-2566">The function Func_israeli_national_id_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="13996-2567">Viene trovata una parola chiave da Keyword_Israel_National_ID.</span><span class="sxs-lookup"><span data-stu-id="13996-2567">A keyword from Keyword_Israel_National_ID is found.</span></span>
- <span data-ttu-id="13996-2568">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="13996-2568">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="13996-2569">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="13996-2569">Keywords</span></span>

#### <a name="keywordisraelnationalid"></a><span data-ttu-id="13996-2570">Keyword_Israel_National_ID</span><span class="sxs-lookup"><span data-stu-id="13996-2570">Keyword_Israel_National_ID</span></span>

- <span data-ttu-id="13996-2571">מספר זהות</span><span class="sxs-lookup"><span data-stu-id="13996-2571">מספר זהות</span></span> 
- <span data-ttu-id="13996-2572">National ID Number</span><span class="sxs-lookup"><span data-stu-id="13996-2572">National ID Number</span></span>
   
## <a name="italy-drivers-license-number"></a><span data-ttu-id="13996-2573">Italia - Numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="13996-2573">Italy Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="13996-2574">Formato</span><span class="sxs-lookup"><span data-stu-id="13996-2574">Format</span></span>

<span data-ttu-id="13996-2575">Una combinazione di 10 lettere e cifre</span><span class="sxs-lookup"><span data-stu-id="13996-2575">A combination of 10 letters and digits</span></span>

### <a name="pattern"></a><span data-ttu-id="13996-2576">Modello</span><span class="sxs-lookup"><span data-stu-id="13996-2576">Pattern</span></span>

- <span data-ttu-id="13996-2577">Una combinazione di 10 lettere e cifre:</span><span class="sxs-lookup"><span data-stu-id="13996-2577">A combination of 10 letters and digits:</span></span>
- <span data-ttu-id="13996-2578">Una lettera (senza distinzione tra maiuscole/minuscole)</span><span class="sxs-lookup"><span data-stu-id="13996-2578">One letter (not case sensitive)</span></span> 
- <span data-ttu-id="13996-2579">La lettera "A" o "V" (senza distinzione tra maiuscole/minuscole)</span><span class="sxs-lookup"><span data-stu-id="13996-2579">The letter "A" or "V" (not case sensitive)</span></span> 
- <span data-ttu-id="13996-2580">7 lettere (senza distinzione tra maiuscole/minuscole), cifre o carattere di sottolineatura</span><span class="sxs-lookup"><span data-stu-id="13996-2580">Seven letters (not case sensitive), digits, or the underscore character</span></span> 
- <span data-ttu-id="13996-2581">Una lettera (senza distinzione tra maiuscole/minuscole)</span><span class="sxs-lookup"><span data-stu-id="13996-2581">One letter (not case sensitive)</span></span>

### <a name="checksum"></a><span data-ttu-id="13996-2582">Checksum</span><span class="sxs-lookup"><span data-stu-id="13996-2582">Checksum</span></span>

<span data-ttu-id="13996-2583">No</span><span class="sxs-lookup"><span data-stu-id="13996-2583">No</span></span>

### <a name="definition"></a><span data-ttu-id="13996-2584">Definizione</span><span class="sxs-lookup"><span data-stu-id="13996-2584">Definition</span></span>

<span data-ttu-id="13996-2585">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="13996-2585">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="13996-2586">L'espressione regolare Regex_italy_drivers_license_number restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="13996-2586">The regular expression Regex_italy_drivers_license_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="13996-2587">Viene trovata una parola chiave da Keyword_italy_drivers_license_number.</span><span class="sxs-lookup"><span data-stu-id="13996-2587">A keyword from Keyword_italy_drivers_license_number is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="13996-2588">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="13996-2588">Keywords</span></span>

#### <a name="keyworditalydriverslicensenumber"></a><span data-ttu-id="13996-2589">Keyword_italy_drivers_license_number</span><span class="sxs-lookup"><span data-stu-id="13996-2589">Keyword_italy_drivers_license_number</span></span>

- <span data-ttu-id="13996-2590">numero di patente di guida</span><span class="sxs-lookup"><span data-stu-id="13996-2590">numero di patente di guida</span></span> 
- <span data-ttu-id="13996-2591">patente di guida</span><span class="sxs-lookup"><span data-stu-id="13996-2591">patente di guida</span></span> 
   
## <a name="japan-bank-account-number"></a><span data-ttu-id="13996-2592">Giappone - Numero di conto bancario</span><span class="sxs-lookup"><span data-stu-id="13996-2592">Japan Bank Account Number</span></span>

### <a name="format"></a><span data-ttu-id="13996-2593">Formato</span><span class="sxs-lookup"><span data-stu-id="13996-2593">Format</span></span>

<span data-ttu-id="13996-2594">Sette o otto cifre</span><span class="sxs-lookup"><span data-stu-id="13996-2594">Seven or eight digits</span></span>

### <a name="pattern"></a><span data-ttu-id="13996-2595">Modello</span><span class="sxs-lookup"><span data-stu-id="13996-2595">Pattern</span></span>

<span data-ttu-id="13996-2596">Numero di conto corrente:</span><span class="sxs-lookup"><span data-stu-id="13996-2596">Bank account number:</span></span>
- <span data-ttu-id="13996-2597">Sette o otto cifre</span><span class="sxs-lookup"><span data-stu-id="13996-2597">Seven or eight digits</span></span>
- <span data-ttu-id="13996-2598">Codice della filiale del conto corrente:</span><span class="sxs-lookup"><span data-stu-id="13996-2598">Bank account branch code:</span></span>
- <span data-ttu-id="13996-2599">Quattro cifre</span><span class="sxs-lookup"><span data-stu-id="13996-2599">Four digits</span></span> 
- <span data-ttu-id="13996-2600">Uno spazio o un trattino (facoltativo)</span><span class="sxs-lookup"><span data-stu-id="13996-2600">A space or dash (optional)</span></span> 
- <span data-ttu-id="13996-2601">Tre cifre</span><span class="sxs-lookup"><span data-stu-id="13996-2601">Three digits</span></span>

<span data-ttu-id="13996-2602">Checksum</span><span class="sxs-lookup"><span data-stu-id="13996-2602">Checksum</span></span>

<span data-ttu-id="13996-2603">No</span><span class="sxs-lookup"><span data-stu-id="13996-2603">No</span></span>

### <a name="definition"></a><span data-ttu-id="13996-2604">Definizione</span><span class="sxs-lookup"><span data-stu-id="13996-2604">Definition</span></span>

<span data-ttu-id="13996-2605">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="13996-2605">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="13996-2606">La funzione Func_jp_bank_account restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="13996-2606">The function Func_jp_bank_account finds content that matches the pattern.</span></span>
- <span data-ttu-id="13996-2607">Viene trovata una parola chiave da Keyword_jp_bank_account.</span><span class="sxs-lookup"><span data-stu-id="13996-2607">A keyword from Keyword_jp_bank_account is found.</span></span>
- <span data-ttu-id="13996-2608">Si verifica una delle situazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="13996-2608">One of the following is true:</span></span>
- <span data-ttu-id="13996-2609">La funzione Func_jp_bank_account_branch_code restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="13996-2609">The function Func_jp_bank_account_branch_code finds content that matches the pattern.</span></span>
- <span data-ttu-id="13996-2610">Viene trovata una parola chiave da Keyword_jp_bank_branch_code.</span><span class="sxs-lookup"><span data-stu-id="13996-2610">A keyword from Keyword_jp_bank_branch_code is found.</span></span>

<span data-ttu-id="13996-2611">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="13996-2611">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="13996-2612">La funzione Func_jp_bank_account restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="13996-2612">The function Func_jp_bank_account finds content that matches the pattern.</span></span>
- <span data-ttu-id="13996-2613">Viene trovata una parola chiave da Keyword_jp_bank_account.</span><span class="sxs-lookup"><span data-stu-id="13996-2613">A keyword from Keyword_jp_bank_account is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="13996-2614">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="13996-2614">Keywords</span></span>

#### <a name="keywordjpbankaccount"></a><span data-ttu-id="13996-2615">Keyword_jp_bank_account</span><span class="sxs-lookup"><span data-stu-id="13996-2615">Keyword_jp_bank_account</span></span>

- <span data-ttu-id="13996-2616">Checking Account Number</span><span class="sxs-lookup"><span data-stu-id="13996-2616">Checking Account Number</span></span> 
- <span data-ttu-id="13996-2617">Checking Account</span><span class="sxs-lookup"><span data-stu-id="13996-2617">Checking Account</span></span> 
- <span data-ttu-id="13996-2618">Checking Account #</span><span class="sxs-lookup"><span data-stu-id="13996-2618">Checking Account #</span></span> 
- <span data-ttu-id="13996-2619">Checking Acct Number</span><span class="sxs-lookup"><span data-stu-id="13996-2619">Checking Acct Number</span></span> 
- <span data-ttu-id="13996-2620">Checking Acct #</span><span class="sxs-lookup"><span data-stu-id="13996-2620">Checking Acct #</span></span> 
- <span data-ttu-id="13996-2621">Checking Acct No.</span><span class="sxs-lookup"><span data-stu-id="13996-2621">Checking Acct No.</span></span> 
- <span data-ttu-id="13996-2622">Checking Account No.</span><span class="sxs-lookup"><span data-stu-id="13996-2622">Checking Account No.</span></span> 
- <span data-ttu-id="13996-2623">Bank Account Number</span><span class="sxs-lookup"><span data-stu-id="13996-2623">Bank Account Number</span></span> 
- <span data-ttu-id="13996-2624">Bank Account</span><span class="sxs-lookup"><span data-stu-id="13996-2624">Bank Account</span></span> 
- <span data-ttu-id="13996-2625">Bank Account #</span><span class="sxs-lookup"><span data-stu-id="13996-2625">Bank Account #</span></span> 
- <span data-ttu-id="13996-2626">Bank Acct Number</span><span class="sxs-lookup"><span data-stu-id="13996-2626">Bank Acct Number</span></span> 
- <span data-ttu-id="13996-2627">Bank Acct #</span><span class="sxs-lookup"><span data-stu-id="13996-2627">Bank Acct #</span></span> 
- <span data-ttu-id="13996-2628">Bank Acct No.</span><span class="sxs-lookup"><span data-stu-id="13996-2628">Bank Acct No.</span></span> 
- <span data-ttu-id="13996-2629">Bank Account No.</span><span class="sxs-lookup"><span data-stu-id="13996-2629">Bank Account No.</span></span> 
- <span data-ttu-id="13996-2630">Savings Account Number</span><span class="sxs-lookup"><span data-stu-id="13996-2630">Savings Account Number</span></span> 
- <span data-ttu-id="13996-2631">Savings Account</span><span class="sxs-lookup"><span data-stu-id="13996-2631">Savings Account</span></span> 
- <span data-ttu-id="13996-2632">Savings Account #</span><span class="sxs-lookup"><span data-stu-id="13996-2632">Savings Account #</span></span> 
- <span data-ttu-id="13996-2633">Savings Acct Number</span><span class="sxs-lookup"><span data-stu-id="13996-2633">Savings Acct Number</span></span> 
- <span data-ttu-id="13996-2634">Savings Acct #</span><span class="sxs-lookup"><span data-stu-id="13996-2634">Savings Acct #</span></span> 
- <span data-ttu-id="13996-2635">Savings Acct No.</span><span class="sxs-lookup"><span data-stu-id="13996-2635">Savings Acct No.</span></span> 
- <span data-ttu-id="13996-2636">Savings Account No.</span><span class="sxs-lookup"><span data-stu-id="13996-2636">Savings Account No.</span></span> 
- <span data-ttu-id="13996-2637">Debit Account Number</span><span class="sxs-lookup"><span data-stu-id="13996-2637">Debit Account Number</span></span> 
- <span data-ttu-id="13996-2638">Debit Account</span><span class="sxs-lookup"><span data-stu-id="13996-2638">Debit Account</span></span> 
- <span data-ttu-id="13996-2639">Debit Account #</span><span class="sxs-lookup"><span data-stu-id="13996-2639">Debit Account #</span></span> 
- <span data-ttu-id="13996-2640">Debit Acct Number</span><span class="sxs-lookup"><span data-stu-id="13996-2640">Debit Acct Number</span></span> 
- <span data-ttu-id="13996-2641">Debit Acct #</span><span class="sxs-lookup"><span data-stu-id="13996-2641">Debit Acct #</span></span> 
- <span data-ttu-id="13996-2642">Debit Acct No.</span><span class="sxs-lookup"><span data-stu-id="13996-2642">Debit Acct No.</span></span> 
- <span data-ttu-id="13996-2643">Debit Account No.</span><span class="sxs-lookup"><span data-stu-id="13996-2643">Debit Account No.</span></span> 
- <span data-ttu-id="13996-2644">口座番号を当座預金口座の確認</span><span class="sxs-lookup"><span data-stu-id="13996-2644">口座番号を当座預金口座の確認</span></span> 
- <span data-ttu-id="13996-2645">#アカウントの確認 、 勘定番号の確認</span><span class="sxs-lookup"><span data-stu-id="13996-2645">＃アカウントの確認、勘定番号の確認</span></span> 
- <span data-ttu-id="13996-2646">#勘定の確認</span><span class="sxs-lookup"><span data-stu-id="13996-2646">＃勘定の確認</span></span> 
- <span data-ttu-id="13996-2647">勘定番号の確認</span><span class="sxs-lookup"><span data-stu-id="13996-2647">勘定番号の確認</span></span> 
- <span data-ttu-id="13996-2648">口座番号の確認</span><span class="sxs-lookup"><span data-stu-id="13996-2648">口座番号の確認</span></span> 
- <span data-ttu-id="13996-2649">銀行口座番号</span><span class="sxs-lookup"><span data-stu-id="13996-2649">銀行口座番号</span></span> 
- <span data-ttu-id="13996-2650">銀行口座</span><span class="sxs-lookup"><span data-stu-id="13996-2650">銀行口座</span></span> 
- <span data-ttu-id="13996-2651">銀行口座 #</span><span class="sxs-lookup"><span data-stu-id="13996-2651">銀行口座＃</span></span> 
- <span data-ttu-id="13996-2652">銀行の勘定番号</span><span class="sxs-lookup"><span data-stu-id="13996-2652">銀行の勘定番号</span></span> 
- <span data-ttu-id="13996-2653">銀行のacct #</span><span class="sxs-lookup"><span data-stu-id="13996-2653">銀行のacct＃</span></span> 
- <span data-ttu-id="13996-2654">銀行の勘定いいえ</span><span class="sxs-lookup"><span data-stu-id="13996-2654">銀行の勘定いいえ</span></span> 
- <span data-ttu-id="13996-2655">銀行口座番号</span><span class="sxs-lookup"><span data-stu-id="13996-2655">銀行口座番号</span></span>
- <span data-ttu-id="13996-2656">普通預金口座番号</span><span class="sxs-lookup"><span data-stu-id="13996-2656">普通預金口座番号</span></span> 
- <span data-ttu-id="13996-2657">預金口座</span><span class="sxs-lookup"><span data-stu-id="13996-2657">預金口座</span></span> 
- <span data-ttu-id="13996-2658">貯蓄口座 #</span><span class="sxs-lookup"><span data-stu-id="13996-2658">貯蓄口座＃</span></span> 
- <span data-ttu-id="13996-2659">貯蓄勘定の数</span><span class="sxs-lookup"><span data-stu-id="13996-2659">貯蓄勘定の数</span></span> 
- <span data-ttu-id="13996-2660">貯蓄勘定 #</span><span class="sxs-lookup"><span data-stu-id="13996-2660">貯蓄勘定＃</span></span> 
- <span data-ttu-id="13996-2661">貯蓄勘定番号</span><span class="sxs-lookup"><span data-stu-id="13996-2661">貯蓄勘定番号</span></span> 
- <span data-ttu-id="13996-2662">普通預金口座番号</span><span class="sxs-lookup"><span data-stu-id="13996-2662">普通預金口座番号</span></span> 
- <span data-ttu-id="13996-2663">引き落とし口座番号</span><span class="sxs-lookup"><span data-stu-id="13996-2663">引き落とし口座番号</span></span> 
- <span data-ttu-id="13996-2664">口座番号</span><span class="sxs-lookup"><span data-stu-id="13996-2664">口座番号</span></span> 
- <span data-ttu-id="13996-2665">口座番号 #</span><span class="sxs-lookup"><span data-stu-id="13996-2665">口座番号＃</span></span> 
- <span data-ttu-id="13996-2666">デビットのacct番号</span><span class="sxs-lookup"><span data-stu-id="13996-2666">デビットのacct番号</span></span> 
- <span data-ttu-id="13996-2667">デビット勘定 #</span><span class="sxs-lookup"><span data-stu-id="13996-2667">デビット勘定＃</span></span> 
- <span data-ttu-id="13996-2668">デビットACCTの番号</span><span class="sxs-lookup"><span data-stu-id="13996-2668">デビットACCTの番号</span></span> 
- <span data-ttu-id="13996-2669">デビット口座番号</span><span class="sxs-lookup"><span data-stu-id="13996-2669">デビット口座番号</span></span> 

#### <a name="keywordjpbankbranchcode"></a><span data-ttu-id="13996-2670">Keyword_jp_bank_branch_code</span><span class="sxs-lookup"><span data-stu-id="13996-2670">Keyword_jp_bank_branch_code</span></span>

<span data-ttu-id="13996-2671">Otemachi</span><span class="sxs-lookup"><span data-stu-id="13996-2671">Otemachi</span></span>

## <a name="japan-drivers-license-number"></a><span data-ttu-id="13996-2672">Giappone - Numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="13996-2672">Japan Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="13996-2673">Formato</span><span class="sxs-lookup"><span data-stu-id="13996-2673">Format</span></span>

<span data-ttu-id="13996-2674">12 cifre</span><span class="sxs-lookup"><span data-stu-id="13996-2674">12 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="13996-2675">Modello</span><span class="sxs-lookup"><span data-stu-id="13996-2675">Pattern</span></span>

<span data-ttu-id="13996-2676">12 cifre consecutive</span><span class="sxs-lookup"><span data-stu-id="13996-2676">12 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="13996-2677">Checksum</span><span class="sxs-lookup"><span data-stu-id="13996-2677">Checksum</span></span>

<span data-ttu-id="13996-2678">No</span><span class="sxs-lookup"><span data-stu-id="13996-2678">No</span></span>

### <a name="definition"></a><span data-ttu-id="13996-2679">Definizione</span><span class="sxs-lookup"><span data-stu-id="13996-2679">Definition</span></span>

<span data-ttu-id="13996-2680">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="13996-2680">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="13996-2681">La funzione Func_jp_drivers_license_number restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="13996-2681">The function Func_jp_drivers_license_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="13996-2682">Viene trovata una parola chiave da Keyword_jp_drivers_license_number.</span><span class="sxs-lookup"><span data-stu-id="13996-2682">A keyword from Keyword_jp_drivers_license_number is found.</span></span>

```
<!-- Japan Driver's License Number -->
<Entity id="c6011143-d087-451c-8313-7f6d4aed2270" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_jp_drivers_license_number" />
        <Match idRef ="Keyword_jp_drivers_license_number" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="13996-2683">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="13996-2683">Keywords</span></span>

#### <a name="keywordjpdriverslicensenumber"></a><span data-ttu-id="13996-2684">Keyword_jp_drivers_license_number</span><span class="sxs-lookup"><span data-stu-id="13996-2684">Keyword_jp_drivers_license_number</span></span>

- <span data-ttu-id="13996-2685">DL</span><span class="sxs-lookup"><span data-stu-id="13996-2685">dl#</span></span> 
- <span data-ttu-id="13996-2686">DL</span><span class="sxs-lookup"><span data-stu-id="13996-2686">DL＃</span></span> 
- <span data-ttu-id="13996-2687">DLS</span><span class="sxs-lookup"><span data-stu-id="13996-2687">dls#</span></span> 
- <span data-ttu-id="13996-2688">DLS</span><span class="sxs-lookup"><span data-stu-id="13996-2688">DLS＃</span></span> 
- <span data-ttu-id="13996-2689">driver license</span><span class="sxs-lookup"><span data-stu-id="13996-2689">driver license</span></span> 
- <span data-ttu-id="13996-2690">driver licenses</span><span class="sxs-lookup"><span data-stu-id="13996-2690">driver licenses</span></span> 
- <span data-ttu-id="13996-2691">drivers license</span><span class="sxs-lookup"><span data-stu-id="13996-2691">drivers license</span></span> 
- <span data-ttu-id="13996-2692">driver's license</span><span class="sxs-lookup"><span data-stu-id="13996-2692">driver's license</span></span> 
- <span data-ttu-id="13996-2693">drivers licenses</span><span class="sxs-lookup"><span data-stu-id="13996-2693">drivers licenses</span></span> 
- <span data-ttu-id="13996-2694">driver's licenses</span><span class="sxs-lookup"><span data-stu-id="13996-2694">driver's licenses</span></span> 
- <span data-ttu-id="13996-2695">driving licence</span><span class="sxs-lookup"><span data-stu-id="13996-2695">driving licence</span></span> 
- <span data-ttu-id="13996-2696">driver'lic</span><span class="sxs-lookup"><span data-stu-id="13996-2696">lic#</span></span> 
- <span data-ttu-id="13996-2697">DRIVER'LIC</span><span class="sxs-lookup"><span data-stu-id="13996-2697">LIC＃</span></span> 
- <span data-ttu-id="13996-2698">driver'lics</span><span class="sxs-lookup"><span data-stu-id="13996-2698">lics#</span></span> 
- <span data-ttu-id="13996-2699">state id</span><span class="sxs-lookup"><span data-stu-id="13996-2699">state id</span></span> 
- <span data-ttu-id="13996-2700">state identification</span><span class="sxs-lookup"><span data-stu-id="13996-2700">state identification</span></span> 
- <span data-ttu-id="13996-2701">state identification number</span><span class="sxs-lookup"><span data-stu-id="13996-2701">state identification number</span></span> 
- <span data-ttu-id="13996-2702">低所得国 #</span><span class="sxs-lookup"><span data-stu-id="13996-2702">低所得国＃</span></span> 
- <span data-ttu-id="13996-2703">免許証</span><span class="sxs-lookup"><span data-stu-id="13996-2703">免許証</span></span> 
- <span data-ttu-id="13996-2704">状態ID</span><span class="sxs-lookup"><span data-stu-id="13996-2704">状態ID</span></span>
- <span data-ttu-id="13996-2705">状態の識別</span><span class="sxs-lookup"><span data-stu-id="13996-2705">状態の識別</span></span> 
- <span data-ttu-id="13996-2706">状態の識別番号</span><span class="sxs-lookup"><span data-stu-id="13996-2706">状態の識別番号</span></span> 
- <span data-ttu-id="13996-2707">運転免許</span><span class="sxs-lookup"><span data-stu-id="13996-2707">運転免許</span></span> 
- <span data-ttu-id="13996-2708">運転免許証</span><span class="sxs-lookup"><span data-stu-id="13996-2708">運転免許証</span></span> 
- <span data-ttu-id="13996-2709">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="13996-2709">運転免許証番号</span></span> 
   
## <a name="japan-passport-number"></a><span data-ttu-id="13996-2710">Giappone - Numero di passaporto</span><span class="sxs-lookup"><span data-stu-id="13996-2710">Japan Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="13996-2711">Formato</span><span class="sxs-lookup"><span data-stu-id="13996-2711">Format</span></span>

<span data-ttu-id="13996-2712">Due lettere seguite da 7 cifre</span><span class="sxs-lookup"><span data-stu-id="13996-2712">Two letters followed by seven digits</span></span>

### <a name="pattern"></a><span data-ttu-id="13996-2713">Modello</span><span class="sxs-lookup"><span data-stu-id="13996-2713">Pattern</span></span>

<span data-ttu-id="13996-2714">Due lettere (senza distinzione tra maiuscole/minuscole) seguite da sette cifre</span><span class="sxs-lookup"><span data-stu-id="13996-2714">Two letters (not case sensitive) followed by seven digits</span></span>

### <a name="checksum"></a><span data-ttu-id="13996-2715">Checksum</span><span class="sxs-lookup"><span data-stu-id="13996-2715">Checksum</span></span>

<span data-ttu-id="13996-2716">No</span><span class="sxs-lookup"><span data-stu-id="13996-2716">No</span></span>

### <a name="definition"></a><span data-ttu-id="13996-2717">Definizione</span><span class="sxs-lookup"><span data-stu-id="13996-2717">Definition</span></span>

<span data-ttu-id="13996-2718">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="13996-2718">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="13996-2719">La funzione Func_jp_passport restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="13996-2719">The function Func_jp_passport finds content that matches the pattern.</span></span>
- <span data-ttu-id="13996-2720">Viene trovata una parola chiave da Keyword_jp_passport.</span><span class="sxs-lookup"><span data-stu-id="13996-2720">A keyword from Keyword_jp_passport is found.</span></span>

```
<!-- Japan Passport Number -->
<Entity id="75177310-1a09-4613-bf6d-833aae3743f8" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_jp_passport" />
        <Match idRef="Keyword_jp_passport" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="13996-2721">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="13996-2721">Keywords</span></span>

#### <a name="keywordjppassport"></a><span data-ttu-id="13996-2722">Keyword_jp_passport</span><span class="sxs-lookup"><span data-stu-id="13996-2722">Keyword_jp_passport</span></span>

- <span data-ttu-id="13996-2723">パスポート</span><span class="sxs-lookup"><span data-stu-id="13996-2723">パスポート</span></span> 
- <span data-ttu-id="13996-2724">パスポート番号</span><span class="sxs-lookup"><span data-stu-id="13996-2724">パスポート番号</span></span> 
- <span data-ttu-id="13996-2725">パスポートのNum</span><span class="sxs-lookup"><span data-stu-id="13996-2725">パスポートのNum</span></span> 
- <span data-ttu-id="13996-2726">パスポート #</span><span class="sxs-lookup"><span data-stu-id="13996-2726">パスポート＃</span></span> 
   
## <a name="japan-resident-registration-number"></a><span data-ttu-id="13996-2727">Giappone - Numero di registrazione dei residenti</span><span class="sxs-lookup"><span data-stu-id="13996-2727">Japan Resident Registration Number</span></span>

### <a name="format"></a><span data-ttu-id="13996-2728">Formato</span><span class="sxs-lookup"><span data-stu-id="13996-2728">Format</span></span>

<span data-ttu-id="13996-2729">11 cifre</span><span class="sxs-lookup"><span data-stu-id="13996-2729">11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="13996-2730">Modello</span><span class="sxs-lookup"><span data-stu-id="13996-2730">Pattern</span></span>

<span data-ttu-id="13996-2731">11 cifre consecutive</span><span class="sxs-lookup"><span data-stu-id="13996-2731">11 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="13996-2732">Checksum</span><span class="sxs-lookup"><span data-stu-id="13996-2732">Checksum</span></span>

<span data-ttu-id="13996-2733">No</span><span class="sxs-lookup"><span data-stu-id="13996-2733">No</span></span>

### <a name="definition"></a><span data-ttu-id="13996-2734">Definizione</span><span class="sxs-lookup"><span data-stu-id="13996-2734">Definition</span></span>

<span data-ttu-id="13996-2735">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="13996-2735">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="13996-2736">La funzione Func_jp_resident_registration_number restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="13996-2736">The function Func_jp_resident_registration_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="13996-2737">Viene trovata una parola chiave da Keyword_jp_resident_registration_number.</span><span class="sxs-lookup"><span data-stu-id="13996-2737">A keyword from Keyword_jp_resident_registration_number is found.</span></span>

```
<!-- Japan Resident Registration Number -->
<Entity id="01c1209b-6389-4faf-a5f8-3f7e13899652" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_jp_resident_registration_number" />
        <Match idRef ="Keyword_jp_resident_registration_number" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="13996-2738">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="13996-2738">Keywords</span></span>

#### <a name="keywordjpresidentregistrationnumber"></a><span data-ttu-id="13996-2739">Keyword_jp_resident_registration_number</span><span class="sxs-lookup"><span data-stu-id="13996-2739">Keyword_jp_resident_registration_number</span></span>

- <span data-ttu-id="13996-2740">Resident Registration Number</span><span class="sxs-lookup"><span data-stu-id="13996-2740">Resident Registration Number</span></span>
- <span data-ttu-id="13996-2741">Resident Register Number</span><span class="sxs-lookup"><span data-stu-id="13996-2741">Resident Register Number</span></span> 
- <span data-ttu-id="13996-2742">Residents Basic Registry Number</span><span class="sxs-lookup"><span data-stu-id="13996-2742">Residents Basic Registry Number</span></span> 
- <span data-ttu-id="13996-2743">Resident Registration No.</span><span class="sxs-lookup"><span data-stu-id="13996-2743">Resident Registration No.</span></span> 
- <span data-ttu-id="13996-2744">Resident Register No.</span><span class="sxs-lookup"><span data-stu-id="13996-2744">Resident Register No.</span></span> 
- <span data-ttu-id="13996-2745">Residents Basic Registry No.</span><span class="sxs-lookup"><span data-stu-id="13996-2745">Residents Basic Registry No.</span></span> 
- <span data-ttu-id="13996-2746">Basic Resident Register No.</span><span class="sxs-lookup"><span data-stu-id="13996-2746">Basic Resident Register No.</span></span> 
- <span data-ttu-id="13996-2747">住民登録番号 、 登録番号をレジデント</span><span class="sxs-lookup"><span data-stu-id="13996-2747">住民登録番号、登録番号をレジデント</span></span> 
- <span data-ttu-id="13996-2748">住民基本登録番号 、 登録番号</span><span class="sxs-lookup"><span data-stu-id="13996-2748">住民基本登録番号、登録番号</span></span> 
- <span data-ttu-id="13996-2749">住民基本レジストリ番号を常駐</span><span class="sxs-lookup"><span data-stu-id="13996-2749">住民基本レジストリ番号を常駐</span></span> 
- <span data-ttu-id="13996-2750">登録番号を常駐住民基本台帳登録番号</span><span class="sxs-lookup"><span data-stu-id="13996-2750">登録番号を常駐住民基本台帳登録番号</span></span> 

   
## <a name="japan-social-insurance-number-sin"></a><span data-ttu-id="13996-2751">Giappone - Numero di assicurazione sociale (SIN)</span><span class="sxs-lookup"><span data-stu-id="13996-2751">Japan Social Insurance Number (SIN)</span></span>

### <a name="format"></a><span data-ttu-id="13996-2752">Formato</span><span class="sxs-lookup"><span data-stu-id="13996-2752">Format</span></span>

<span data-ttu-id="13996-2753">7-12 cifre</span><span class="sxs-lookup"><span data-stu-id="13996-2753">7-12 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="13996-2754">Modello</span><span class="sxs-lookup"><span data-stu-id="13996-2754">Pattern</span></span>

<span data-ttu-id="13996-2755">7-12 cifre:</span><span class="sxs-lookup"><span data-stu-id="13996-2755">7-12 digits:</span></span>
- <span data-ttu-id="13996-2756">Quattro cifre</span><span class="sxs-lookup"><span data-stu-id="13996-2756">Four digits</span></span> 
- <span data-ttu-id="13996-2757">Una lineetta (facoltativa)</span><span class="sxs-lookup"><span data-stu-id="13996-2757">A hyphen (optional)</span></span> 
- <span data-ttu-id="13996-2758">Sei cifre o</span><span class="sxs-lookup"><span data-stu-id="13996-2758">Six digits OR</span></span>
- <span data-ttu-id="13996-2759">7-12 cifre consecutive</span><span class="sxs-lookup"><span data-stu-id="13996-2759">7-12 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="13996-2760">Checksum</span><span class="sxs-lookup"><span data-stu-id="13996-2760">Checksum</span></span>

<span data-ttu-id="13996-2761">No</span><span class="sxs-lookup"><span data-stu-id="13996-2761">No</span></span>

### <a name="definition"></a><span data-ttu-id="13996-2762">Definizione</span><span class="sxs-lookup"><span data-stu-id="13996-2762">Definition</span></span>

<span data-ttu-id="13996-2763">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="13996-2763">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="13996-2764">La funzione Func_jp_sin restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="13996-2764">The function Func_jp_sin finds content that matches the pattern.</span></span>
- <span data-ttu-id="13996-2765">Viene trovata una parola chiave da Keyword_jp_sin.</span><span class="sxs-lookup"><span data-stu-id="13996-2765">A keyword from Keyword_jp_sin is found.</span></span>

<span data-ttu-id="13996-2766">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="13996-2766">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="13996-2767">La funzione Func_jp_sin_pre_1997 restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="13996-2767">The function Func_jp_sin_pre_1997 finds content that matches the pattern.</span></span>
- <span data-ttu-id="13996-2768">Viene trovata una parola chiave da Keyword_jp_sin.</span><span class="sxs-lookup"><span data-stu-id="13996-2768">A keyword from Keyword_jp_sin is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="13996-2769">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="13996-2769">Keywords</span></span>

#### <a name="keywordjpsin"></a><span data-ttu-id="13996-2770">Keyword_jp_sin</span><span class="sxs-lookup"><span data-stu-id="13996-2770">Keyword_jp_sin</span></span>

- <span data-ttu-id="13996-2771">Social Insurance No.</span><span class="sxs-lookup"><span data-stu-id="13996-2771">Social Insurance No.</span></span> 
- <span data-ttu-id="13996-2772">Social Insurance Num</span><span class="sxs-lookup"><span data-stu-id="13996-2772">Social Insurance Num</span></span> 
- <span data-ttu-id="13996-2773">Social Insurance Number</span><span class="sxs-lookup"><span data-stu-id="13996-2773">Social Insurance Number</span></span> 
- <span data-ttu-id="13996-2774">社会保険のテンキー</span><span class="sxs-lookup"><span data-stu-id="13996-2774">社会保険のテンキー</span></span> 
- <span data-ttu-id="13996-2775">社会保険番号</span><span class="sxs-lookup"><span data-stu-id="13996-2775">社会保険番号</span></span> 

## <a name="japanese-residence-card-number"></a><span data-ttu-id="13996-2776">Numero di carta di soggiorno giapponese</span><span class="sxs-lookup"><span data-stu-id="13996-2776">Japanese Residence Card Number</span></span>

### <a name="format"></a><span data-ttu-id="13996-2777">Formato</span><span class="sxs-lookup"><span data-stu-id="13996-2777">Format</span></span>

<span data-ttu-id="13996-2778">12 lettere e cifre</span><span class="sxs-lookup"><span data-stu-id="13996-2778">12 letters and digits</span></span>

### <a name="pattern"></a><span data-ttu-id="13996-2779">Modello</span><span class="sxs-lookup"><span data-stu-id="13996-2779">Pattern</span></span>

<span data-ttu-id="13996-2780">12 lettere e cifre:</span><span class="sxs-lookup"><span data-stu-id="13996-2780">12 letters and digits:</span></span>
- <span data-ttu-id="13996-2781">Due lettere (senza distinzione tra maiuscole/minuscole)</span><span class="sxs-lookup"><span data-stu-id="13996-2781">Two letters (not case sensitive)</span></span>
- <span data-ttu-id="13996-2782">Otto cifre</span><span class="sxs-lookup"><span data-stu-id="13996-2782">Eight digits</span></span> 
- <span data-ttu-id="13996-2783">Due lettere (senza distinzione tra maiuscole/minuscole)</span><span class="sxs-lookup"><span data-stu-id="13996-2783">Two letters (not case sensitive)</span></span>

### <a name="checksum"></a><span data-ttu-id="13996-2784">Checksum</span><span class="sxs-lookup"><span data-stu-id="13996-2784">Checksum</span></span>

<span data-ttu-id="13996-2785">No</span><span class="sxs-lookup"><span data-stu-id="13996-2785">No</span></span>

### <a name="definition"></a><span data-ttu-id="13996-2786">Definizione</span><span class="sxs-lookup"><span data-stu-id="13996-2786">Definition</span></span>

<span data-ttu-id="13996-2787">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="13996-2787">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="13996-2788">L'espressione regolare Regex_jp_residence_card_number trova il contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="13996-2788">The regular expression Regex_jp_residence_card_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="13996-2789">Viene trovata una parola chiave da Keyword_jp_residence_card_number.</span><span class="sxs-lookup"><span data-stu-id="13996-2789">A keyword from Keyword_jp_residence_card_number is found.</span></span>

```
<!--Japan Residence Card Number-->
-<Entity id="ac36fef2-a289-4e2c-bb48-b02366e89fc0" recommendedConfidence="75" patternsProximity="300">
   -<Pattern confidenceLevel="75">
      <IdMatch idRef="Regex_jp_residence_card_number"/>
      <Match idRef="Keyword_jp_residence_card_number"/>
   </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="13996-2790">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="13996-2790">Keywords</span></span>

#### <a name="keywordjpresidencecardnumber"></a><span data-ttu-id="13996-2791">Keyword_jp_residence_card_number</span><span class="sxs-lookup"><span data-stu-id="13996-2791">Keyword_jp_residence_card_number</span></span>

- <span data-ttu-id="13996-2792">Numero di carta di soggiorno</span><span class="sxs-lookup"><span data-stu-id="13996-2792">Residence card number</span></span>
- <span data-ttu-id="13996-2793">Carta di soggiorno No</span><span class="sxs-lookup"><span data-stu-id="13996-2793">Residence card no</span></span>
- <span data-ttu-id="13996-2794">Carta di soggiorno #</span><span class="sxs-lookup"><span data-stu-id="13996-2794">Residence card #</span></span>
- <span data-ttu-id="13996-2795">在留カード番号</span><span class="sxs-lookup"><span data-stu-id="13996-2795">在留カード番号</span></span>
   
## <a name="malaysia-id-card-number"></a><span data-ttu-id="13996-2796">Malesia - Numero di carta d’identità</span><span class="sxs-lookup"><span data-stu-id="13996-2796">Malaysia ID Card Number</span></span>

### <a name="format"></a><span data-ttu-id="13996-2797">Formato</span><span class="sxs-lookup"><span data-stu-id="13996-2797">Format</span></span>

<span data-ttu-id="13996-2798">12 cifre contenenti lineette facoltative</span><span class="sxs-lookup"><span data-stu-id="13996-2798">12 digits containing optional hyphens</span></span>

### <a name="pattern"></a><span data-ttu-id="13996-2799">Modello</span><span class="sxs-lookup"><span data-stu-id="13996-2799">Pattern</span></span>

<span data-ttu-id="13996-2800">12 cifre:</span><span class="sxs-lookup"><span data-stu-id="13996-2800">12 digits:</span></span>
- <span data-ttu-id="13996-2801">Sei cifre nel formato AAMMGG, ovvero la data di nascita</span><span class="sxs-lookup"><span data-stu-id="13996-2801">Six digits in the format YYMMDD which are the date of birth</span></span> 
- <span data-ttu-id="13996-2802">Un trattino (facoltativo)</span><span class="sxs-lookup"><span data-stu-id="13996-2802">A dash (optional)</span></span> 
- <span data-ttu-id="13996-2803">Codice luogo di nascita a due lettere </span><span class="sxs-lookup"><span data-stu-id="13996-2803">Two-letter place-of-birth code</span></span> 
- <span data-ttu-id="13996-2804">Un trattino (facoltativo)</span><span class="sxs-lookup"><span data-stu-id="13996-2804">A dash (optional)</span></span> 
- <span data-ttu-id="13996-2805">Tre cifre casuali </span><span class="sxs-lookup"><span data-stu-id="13996-2805">Three random digits</span></span> 
- <span data-ttu-id="13996-2806">Codice genere a una cifra singola</span><span class="sxs-lookup"><span data-stu-id="13996-2806">One-digit gender code</span></span>

### <a name="checksum"></a><span data-ttu-id="13996-2807">Checksum</span><span class="sxs-lookup"><span data-stu-id="13996-2807">Checksum</span></span>

<span data-ttu-id="13996-2808">No</span><span class="sxs-lookup"><span data-stu-id="13996-2808">No</span></span>

### <a name="definition"></a><span data-ttu-id="13996-2809">Definizione</span><span class="sxs-lookup"><span data-stu-id="13996-2809">Definition</span></span>

<span data-ttu-id="13996-2810">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="13996-2810">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="13996-2811">L'espressione regolare Regex_malaysia_id_card_number trova il contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="13996-2811">The regular expression Regex_malaysia_id_card_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="13996-2812">Viene trovata una parola chiave da Keyword_malaysia_id_card_number.</span><span class="sxs-lookup"><span data-stu-id="13996-2812">A keyword from Keyword_malaysia_id_card_number is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="13996-2813">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="13996-2813">Keywords</span></span>
   
#### <a name="keywordmalaysiaidcardnumber"></a><span data-ttu-id="13996-2814">Keyword_malaysia_id_card_number</span><span class="sxs-lookup"><span data-stu-id="13996-2814">Keyword_malaysia_id_card_number</span></span>

- <span data-ttu-id="13996-2815">scheda dell'applicazione digitale</span><span class="sxs-lookup"><span data-stu-id="13996-2815">digital application card</span></span>
- <span data-ttu-id="13996-2816">i/c</span><span class="sxs-lookup"><span data-stu-id="13996-2816">i/c</span></span>
- <span data-ttu-id="13996-2817">i/c no</span><span class="sxs-lookup"><span data-stu-id="13996-2817">i/c no</span></span>
- <span data-ttu-id="13996-2818">IC</span><span class="sxs-lookup"><span data-stu-id="13996-2818">ic</span></span>
- <span data-ttu-id="13996-2819">IC No</span><span class="sxs-lookup"><span data-stu-id="13996-2819">ic no</span></span>
- <span data-ttu-id="13996-2820">id card</span><span class="sxs-lookup"><span data-stu-id="13996-2820">id card</span></span>
- <span data-ttu-id="13996-2821">Scheda di identificazione</span><span class="sxs-lookup"><span data-stu-id="13996-2821">identification Card</span></span>
- <span data-ttu-id="13996-2822">carta di identità</span><span class="sxs-lookup"><span data-stu-id="13996-2822">identity card</span></span>
- <span data-ttu-id="13996-2823">k/p</span><span class="sxs-lookup"><span data-stu-id="13996-2823">k/p</span></span>
- <span data-ttu-id="13996-2824">k/p no</span><span class="sxs-lookup"><span data-stu-id="13996-2824">k/p no</span></span>
- <span data-ttu-id="13996-2825">diri akuan Kad</span><span class="sxs-lookup"><span data-stu-id="13996-2825">kad akuan diri</span></span>
- <span data-ttu-id="13996-2826">Kad Aplikasi digitale</span><span class="sxs-lookup"><span data-stu-id="13996-2826">kad aplikasi digital</span></span>
- <span data-ttu-id="13996-2827">Kad Pengenalan Malaysia</span><span class="sxs-lookup"><span data-stu-id="13996-2827">kad pengenalan malaysia</span></span>
- <span data-ttu-id="13996-2828">KP</span><span class="sxs-lookup"><span data-stu-id="13996-2828">kp</span></span>
- <span data-ttu-id="13996-2829">KP No</span><span class="sxs-lookup"><span data-stu-id="13996-2829">kp no</span></span>
- <span data-ttu-id="13996-2830">MyKad</span><span class="sxs-lookup"><span data-stu-id="13996-2830">mykad</span></span>
- <span data-ttu-id="13996-2831">MYKAS</span><span class="sxs-lookup"><span data-stu-id="13996-2831">mykas</span></span>
- <span data-ttu-id="13996-2832">mykid</span><span class="sxs-lookup"><span data-stu-id="13996-2832">mykid</span></span>
- <span data-ttu-id="13996-2833">mypr</span><span class="sxs-lookup"><span data-stu-id="13996-2833">mypr</span></span>
- <span data-ttu-id="13996-2834">mytentera</span><span class="sxs-lookup"><span data-stu-id="13996-2834">mytentera</span></span>
- <span data-ttu-id="13996-2835">carta di identità Malaysia</span><span class="sxs-lookup"><span data-stu-id="13996-2835">malaysia identity card</span></span>
- <span data-ttu-id="13996-2836">carta di identità malaysiana</span><span class="sxs-lookup"><span data-stu-id="13996-2836">malaysian identity card</span></span>
- <span data-ttu-id="13996-2837">NRIC</span><span class="sxs-lookup"><span data-stu-id="13996-2837">nric</span></span>
- <span data-ttu-id="13996-2838">scheda di identificazione personale</span><span class="sxs-lookup"><span data-stu-id="13996-2838">personal identification card</span></span>
   
## <a name="netherlands-citizens-service-bsn-number"></a><span data-ttu-id="13996-2839">Paesi Bassi - Numero di servizio cittadino (BSN)</span><span class="sxs-lookup"><span data-stu-id="13996-2839">Netherlands Citizen's Service (BSN) Number</span></span>

### <a name="format"></a><span data-ttu-id="13996-2840">Formato</span><span class="sxs-lookup"><span data-stu-id="13996-2840">Format</span></span>

<span data-ttu-id="13996-2841">8-9 cifre contenenti spazi facoltativi </span><span class="sxs-lookup"><span data-stu-id="13996-2841">8-9 digits containing optional spaces</span></span>

### <a name="pattern"></a><span data-ttu-id="13996-2842">Modello</span><span class="sxs-lookup"><span data-stu-id="13996-2842">Pattern</span></span>

<span data-ttu-id="13996-2843">8-9 cifre:</span><span class="sxs-lookup"><span data-stu-id="13996-2843">8-9 digits:</span></span>
- <span data-ttu-id="13996-2844">Tre cifre</span><span class="sxs-lookup"><span data-stu-id="13996-2844">Three digits</span></span> 
- <span data-ttu-id="13996-2845">Uno spazio (facoltativo)</span><span class="sxs-lookup"><span data-stu-id="13996-2845">A space (optional)</span></span> 
- <span data-ttu-id="13996-2846">Tre cifre</span><span class="sxs-lookup"><span data-stu-id="13996-2846">Three digits</span></span> 
- <span data-ttu-id="13996-2847">Uno spazio (facoltativo)</span><span class="sxs-lookup"><span data-stu-id="13996-2847">A space (optional)</span></span> 
- <span data-ttu-id="13996-2848">2-3 cifre</span><span class="sxs-lookup"><span data-stu-id="13996-2848">2-3 digits</span></span>

### <a name="checksum"></a><span data-ttu-id="13996-2849">Checksum</span><span class="sxs-lookup"><span data-stu-id="13996-2849">Checksum</span></span>

<span data-ttu-id="13996-2850">Sì</span><span class="sxs-lookup"><span data-stu-id="13996-2850">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="13996-2851">Definizione</span><span class="sxs-lookup"><span data-stu-id="13996-2851">Definition</span></span>

<span data-ttu-id="13996-2852">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="13996-2852">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="13996-2853">La funzione Func_netherlands_bsn trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="13996-2853">The function Func_netherlands_bsn finds content that matches the pattern.</span></span>
- <span data-ttu-id="13996-2854">Viene trovata una parola chiave da Keyword_netherlands_bsn.</span><span class="sxs-lookup"><span data-stu-id="13996-2854">A keyword from Keyword_netherlands_bsn is found.</span></span>
- <span data-ttu-id="13996-2855">La funzione Func_eu_date2 rileva una data nel formato di data appropriato.</span><span class="sxs-lookup"><span data-stu-id="13996-2855">The function Func_eu_date2 finds a date in the right date format.</span></span>
- <span data-ttu-id="13996-2856">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="13996-2856">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="13996-2857">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="13996-2857">Keywords</span></span>

#### <a name="keywordnetherlandsbsn"></a><span data-ttu-id="13996-2858">Keyword_netherlands_bsn</span><span class="sxs-lookup"><span data-stu-id="13996-2858">Keyword_netherlands_bsn</span></span>

- <span data-ttu-id="13996-2859">Numero di servizio cittadino</span><span class="sxs-lookup"><span data-stu-id="13996-2859">Citizen service number</span></span> 
- <span data-ttu-id="13996-2860">BSN</span><span class="sxs-lookup"><span data-stu-id="13996-2860">BSN</span></span> 
- <span data-ttu-id="13996-2861">Burgerservicenummer</span><span class="sxs-lookup"><span data-stu-id="13996-2861">Burgerservicenummer</span></span> 
- <span data-ttu-id="13996-2862">Sofinummer</span><span class="sxs-lookup"><span data-stu-id="13996-2862">Sofinummer</span></span> 
- <span data-ttu-id="13996-2863">Persoonsgebonden nummer</span><span class="sxs-lookup"><span data-stu-id="13996-2863">Persoonsgebonden nummer</span></span> 
- <span data-ttu-id="13996-2864">Persoonsnummer</span><span class="sxs-lookup"><span data-stu-id="13996-2864">Persoonsnummer</span></span>    

   
## <a name="new-zealand-ministry-of-health-number"></a><span data-ttu-id="13996-2865">Nuova Zelanda - Numero del Ministero della Sanità</span><span class="sxs-lookup"><span data-stu-id="13996-2865">New Zealand Ministry of Health Number</span></span>

### <a name="format"></a><span data-ttu-id="13996-2866">Formato</span><span class="sxs-lookup"><span data-stu-id="13996-2866">Format</span></span>

<span data-ttu-id="13996-2867">Tre lettere, uno spazio (facoltativo) e quattro cifre</span><span class="sxs-lookup"><span data-stu-id="13996-2867">Three letters, a space (optional), and four digits</span></span>

### <a name="pattern"></a><span data-ttu-id="13996-2868">Modello</span><span class="sxs-lookup"><span data-stu-id="13996-2868">Pattern</span></span>

<span data-ttu-id="13996-2869">Tre lettere (senza distinzione tra maiuscole/minuscole) uno spazio (facoltativo) quattro cifre</span><span class="sxs-lookup"><span data-stu-id="13996-2869">Three letters (not case sensitive) a space (optional) four digits</span></span>

### <a name="checksum"></a><span data-ttu-id="13996-2870">Checksum</span><span class="sxs-lookup"><span data-stu-id="13996-2870">Checksum</span></span>

<span data-ttu-id="13996-2871">Sì</span><span class="sxs-lookup"><span data-stu-id="13996-2871">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="13996-2872">Definizione</span><span class="sxs-lookup"><span data-stu-id="13996-2872">Definition</span></span>

<span data-ttu-id="13996-2873">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="13996-2873">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="13996-2874">La funzione Func_new_zealand_ministry_of_health_number restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="13996-2874">The function Func_new_zealand_ministry_of_health_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="13996-2875">Viene trovata una parola chiave da Keyword_nz_terms.</span><span class="sxs-lookup"><span data-stu-id="13996-2875">A keyword from Keyword_nz_terms is found.</span></span>
- <span data-ttu-id="13996-2876">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="13996-2876">The checksum passes.</span></span>

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

<span data-ttu-id="13996-2877">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="13996-2877">Keywords</span></span>

<span data-ttu-id="13996-2878">Keyword_nz_terms</span><span class="sxs-lookup"><span data-stu-id="13996-2878">Keyword_nz_terms</span></span>

- <span data-ttu-id="13996-2879">NHI</span><span class="sxs-lookup"><span data-stu-id="13996-2879">NHI</span></span> 
- <span data-ttu-id="13996-2880">New Zealand</span><span class="sxs-lookup"><span data-stu-id="13996-2880">New Zealand</span></span> 
- <span data-ttu-id="13996-2881">Integrità</span><span class="sxs-lookup"><span data-stu-id="13996-2881">Health</span></span> 
- <span data-ttu-id="13996-2882">trattamento</span><span class="sxs-lookup"><span data-stu-id="13996-2882">treatment</span></span> 
   
## <a name="norway-identification-number"></a><span data-ttu-id="13996-2883">Norvegia - Numero di identificazione
</span><span class="sxs-lookup"><span data-stu-id="13996-2883">Norway Identification Number</span></span>

### <a name="format"></a><span data-ttu-id="13996-2884">Formato</span><span class="sxs-lookup"><span data-stu-id="13996-2884">Format</span></span>

<span data-ttu-id="13996-2885">11 cifre</span><span class="sxs-lookup"><span data-stu-id="13996-2885">11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="13996-2886">Modello</span><span class="sxs-lookup"><span data-stu-id="13996-2886">Pattern</span></span>

<span data-ttu-id="13996-2887">11 cifre:</span><span class="sxs-lookup"><span data-stu-id="13996-2887">11 digits:</span></span>
- <span data-ttu-id="13996-2888">Sei cifre nel formato GGMMAA, ovvero la data di nascita</span><span class="sxs-lookup"><span data-stu-id="13996-2888">Six digits in the format DDMMYY which are the date of birth</span></span> 
- <span data-ttu-id="13996-2889">Numero individuale composto da tre cifre </span><span class="sxs-lookup"><span data-stu-id="13996-2889">Three-digit individual number</span></span> 
- <span data-ttu-id="13996-2890">Due cifre di controllo</span><span class="sxs-lookup"><span data-stu-id="13996-2890">Two check digits</span></span>

### <a name="checksum"></a><span data-ttu-id="13996-2891">Checksum</span><span class="sxs-lookup"><span data-stu-id="13996-2891">Checksum</span></span>

<span data-ttu-id="13996-2892">Sì</span><span class="sxs-lookup"><span data-stu-id="13996-2892">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="13996-2893">Definizione</span><span class="sxs-lookup"><span data-stu-id="13996-2893">Definition</span></span>

<span data-ttu-id="13996-2894">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="13996-2894">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="13996-2895">La funzione Func_norway_id_number trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="13996-2895">The function Func_norway_id_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="13996-2896">Viene trovata una parola chiave da Keyword_norway_id_number.</span><span class="sxs-lookup"><span data-stu-id="13996-2896">A keyword from Keyword_norway_id_number is found.</span></span>
- <span data-ttu-id="13996-2897">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="13996-2897">The checksum passes.</span></span>
- <span data-ttu-id="13996-2898">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="13996-2898">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="13996-2899">La funzione Func_norway_id_numbe trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="13996-2899">The function Func_norway_id_numbe finds content that matches the pattern.</span></span>
- <span data-ttu-id="13996-2900">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="13996-2900">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="13996-2901">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="13996-2901">Keywords</span></span>

#### <a name="keywordnorwayidnumber"></a><span data-ttu-id="13996-2902">Keyword_norway_id_number</span><span class="sxs-lookup"><span data-stu-id="13996-2902">Keyword_norway_id_number</span></span>

- <span data-ttu-id="13996-2903">Codice PIN</span><span class="sxs-lookup"><span data-stu-id="13996-2903">Personal identification number</span></span>
- <span data-ttu-id="13996-2904">Numero ID norvegese</span><span class="sxs-lookup"><span data-stu-id="13996-2904">Norwegian ID Number</span></span>
- <span data-ttu-id="13996-2905">Numero ID
</span><span class="sxs-lookup"><span data-stu-id="13996-2905">ID Number</span></span>
- <span data-ttu-id="13996-2906">Identificazione</span><span class="sxs-lookup"><span data-stu-id="13996-2906">Identification</span></span>
- <span data-ttu-id="13996-2907">Personnummer</span><span class="sxs-lookup"><span data-stu-id="13996-2907">Personnummer</span></span>
- <span data-ttu-id="13996-2908">Fødselsnummer</span><span class="sxs-lookup"><span data-stu-id="13996-2908">Fødselsnummer</span></span>

   
## <a name="philippines-unified-multi-purpose-id-number"></a><span data-ttu-id="13996-2909">Filippine - Numero ID multifunzione unificato</span><span class="sxs-lookup"><span data-stu-id="13996-2909">Philippines Unified Multi-Purpose ID Number</span></span>

### <a name="format"></a><span data-ttu-id="13996-2910">Formato</span><span class="sxs-lookup"><span data-stu-id="13996-2910">Format</span></span>

<span data-ttu-id="13996-2911">12 cifre separate da dei segni meno</span><span class="sxs-lookup"><span data-stu-id="13996-2911">12 digits separated by hyphens</span></span>

### <a name="pattern"></a><span data-ttu-id="13996-2912">Modello</span><span class="sxs-lookup"><span data-stu-id="13996-2912">Pattern</span></span>

<span data-ttu-id="13996-2913">12 cifre:</span><span class="sxs-lookup"><span data-stu-id="13996-2913">12 digits:</span></span>
- <span data-ttu-id="13996-2914">Quattro cifre</span><span class="sxs-lookup"><span data-stu-id="13996-2914">Four digits</span></span> 
- <span data-ttu-id="13996-2915">Una lineetta</span><span class="sxs-lookup"><span data-stu-id="13996-2915">A hyphen</span></span> 
- <span data-ttu-id="13996-2916">Sette cifre</span><span class="sxs-lookup"><span data-stu-id="13996-2916">Seven digits</span></span> 
- <span data-ttu-id="13996-2917">Una lineetta</span><span class="sxs-lookup"><span data-stu-id="13996-2917">A hyphen</span></span> 
- <span data-ttu-id="13996-2918">Una cifra</span><span class="sxs-lookup"><span data-stu-id="13996-2918">One digit</span></span>

### <a name="checksum"></a><span data-ttu-id="13996-2919">Checksum</span><span class="sxs-lookup"><span data-stu-id="13996-2919">Checksum</span></span>

<span data-ttu-id="13996-2920">No</span><span class="sxs-lookup"><span data-stu-id="13996-2920">No</span></span>

### <a name="definition"></a><span data-ttu-id="13996-2921">Definizione</span><span class="sxs-lookup"><span data-stu-id="13996-2921">Definition</span></span>

<span data-ttu-id="13996-2922">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="13996-2922">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="13996-2923">L'espressione regolare Regex_philippines_unified_id trova il contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="13996-2923">The regular expression Regex_philippines_unified_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="13996-2924">Viene trovata una parola chiave da Keyword_philippines_id.</span><span class="sxs-lookup"><span data-stu-id="13996-2924">A keyword from Keyword_philippines_id is found.</span></span>

```
<!-- Philippines Unified Multi-Purpose ID number -->
<Entity id="019b39dd-8c25-4765-91a3-d9c6baf3c3b3" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_philippines_unified_id"/>
     <Match idRef="Keyword_philippines_id"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="13996-2925">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="13996-2925">Keywords</span></span>
   
#### <a name="keywordphilippinesid"></a><span data-ttu-id="13996-2926">Keyword_philippines_id</span><span class="sxs-lookup"><span data-stu-id="13996-2926">Keyword_philippines_id</span></span>

- <span data-ttu-id="13996-2927">ID multifunzione unificato</span><span class="sxs-lookup"><span data-stu-id="13996-2927">Unified Multi-Purpose ID</span></span> 
- <span data-ttu-id="13996-2928">UMID</span><span class="sxs-lookup"><span data-stu-id="13996-2928">UMID</span></span> 
- <span data-ttu-id="13996-2929">Carta di identità</span><span class="sxs-lookup"><span data-stu-id="13996-2929">Identity Card</span></span> 
- <span data-ttu-id="13996-2930">Pinag-isang Multi-Layunin ID</span><span class="sxs-lookup"><span data-stu-id="13996-2930">Pinag-isang Multi-Layunin ID</span></span>
   
## <a name="poland-identity-card"></a><span data-ttu-id="13996-2931">Carta di identita - Polonia</span><span class="sxs-lookup"><span data-stu-id="13996-2931">Poland Identity Card</span></span>

### <a name="format"></a><span data-ttu-id="13996-2932">Formato</span><span class="sxs-lookup"><span data-stu-id="13996-2932">Format</span></span>

<span data-ttu-id="13996-2933">Tre lettere e sei cifre</span><span class="sxs-lookup"><span data-stu-id="13996-2933">Three letters and six digits</span></span>

### <a name="pattern"></a><span data-ttu-id="13996-2934">Modello</span><span class="sxs-lookup"><span data-stu-id="13996-2934">Pattern</span></span>

<span data-ttu-id="13996-2935">Tre lettere (senza distinzione tra maiuscole/minuscole) seguite da sei cifre</span><span class="sxs-lookup"><span data-stu-id="13996-2935">Three letters (not case sensitive) followed by six digits</span></span>

### <a name="checksum"></a><span data-ttu-id="13996-2936">Checksum</span><span class="sxs-lookup"><span data-stu-id="13996-2936">Checksum</span></span>

<span data-ttu-id="13996-2937">Sì</span><span class="sxs-lookup"><span data-stu-id="13996-2937">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="13996-2938">Definizione</span><span class="sxs-lookup"><span data-stu-id="13996-2938">Definition</span></span>

<span data-ttu-id="13996-2939">Un criterio DLP è 75% fiducioso di aver rilevato questo tipo di informazioni riservate se, entro 300 caratteri: la funzione Func_polish_national_id trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="13996-2939">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The function Func_polish_national_id finds content that matches the pattern.</span></span>
<span data-ttu-id="13996-2940">Viene trovata una parola chiave da Keyword_polish_national_id_passport_number.</span><span class="sxs-lookup"><span data-stu-id="13996-2940">A keyword from Keyword_polish_national_id_passport_number is found.</span></span>
<span data-ttu-id="13996-2941">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="13996-2941">The checksum passes.</span></span>

```
<!-- Poland Identity Card-->
<Entity id="25E64989-ED5D-40CA-A939-6C14183BB7BF" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_polish_national_id" />
          <Match idRef="Keyword_polish_national_id_passport_number" />
      </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="13996-2942">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="13996-2942">Keywords</span></span>

#### <a name="keywordpolishnationalidpassportnumber"></a><span data-ttu-id="13996-2943">Keyword_polish_national_id_passport_number</span><span class="sxs-lookup"><span data-stu-id="13996-2943">Keyword_polish_national_id_passport_number</span></span>

- <span data-ttu-id="13996-2944">Dowód osobisty</span><span class="sxs-lookup"><span data-stu-id="13996-2944">Dowód osobisty</span></span>
- <span data-ttu-id="13996-2945">Numero dowodu osobistego</span><span class="sxs-lookup"><span data-stu-id="13996-2945">Numer dowodu osobistego</span></span>
- <span data-ttu-id="13996-2946">Nazwa i numeri dowodu osobistego</span><span class="sxs-lookup"><span data-stu-id="13996-2946">Nazwa i numer dowodu osobistego</span></span>
- <span data-ttu-id="13996-2947">Nazwa i Nr dowodu osobistego</span><span class="sxs-lookup"><span data-stu-id="13996-2947">Nazwa i nr dowodu osobistego</span></span>
- <span data-ttu-id="13996-2948">Nazwa i nr dowodu tożsamości</span><span class="sxs-lookup"><span data-stu-id="13996-2948">Nazwa i nr dowodu tożsamości</span></span>
- <span data-ttu-id="13996-2949">Dowód Tożsamości</span><span class="sxs-lookup"><span data-stu-id="13996-2949">Dowód Tożsamości</span></span>
- <span data-ttu-id="13996-2950">Dow.</span><span class="sxs-lookup"><span data-stu-id="13996-2950">dow.</span></span> <span data-ttu-id="13996-2951">OS.</span><span class="sxs-lookup"><span data-stu-id="13996-2951">os.</span></span>

   
## <a name="poland-national-id-pesel"></a><span data-ttu-id="13996-2952">ID nazionale Polonia (PESEL)</span><span class="sxs-lookup"><span data-stu-id="13996-2952">Poland National ID (PESEL)</span></span>

### <a name="format"></a><span data-ttu-id="13996-2953">Formato</span><span class="sxs-lookup"><span data-stu-id="13996-2953">Format</span></span>

<span data-ttu-id="13996-2954">11 cifre</span><span class="sxs-lookup"><span data-stu-id="13996-2954">11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="13996-2955">Modello</span><span class="sxs-lookup"><span data-stu-id="13996-2955">Pattern</span></span>

<span data-ttu-id="13996-2956">11 cifre consecutive</span><span class="sxs-lookup"><span data-stu-id="13996-2956">11 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="13996-2957">Checksum</span><span class="sxs-lookup"><span data-stu-id="13996-2957">Checksum</span></span>

<span data-ttu-id="13996-2958">Sì</span><span class="sxs-lookup"><span data-stu-id="13996-2958">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="13996-2959">Definizione</span><span class="sxs-lookup"><span data-stu-id="13996-2959">Definition</span></span>

<span data-ttu-id="13996-2960">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="13996-2960">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="13996-2961">La funzione Func_pesel_identification_number restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="13996-2961">The function Func_pesel_identification_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="13996-2962">Viene trovata una parola chiave da Keyword_pesel_identification_number.</span><span class="sxs-lookup"><span data-stu-id="13996-2962">A keyword from Keyword_pesel_identification_number is found.</span></span>
- <span data-ttu-id="13996-2963">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="13996-2963">The checksum passes.</span></span>

```
<!-- Poland National ID (PESEL) -->      
<Entity id="E3AAF206-4297-412F-9E06-BA8487E22456" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_pesel_identification_number" />
          <Match idRef="Keyword_pesel_identification_number" />
      </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="13996-2964">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="13996-2964">Keywords</span></span>

#### <a name="keywordpeselidentificationnumber"></a><span data-ttu-id="13996-2965">Keyword_pesel_identification_number</span><span class="sxs-lookup"><span data-stu-id="13996-2965">Keyword_pesel_identification_number</span></span>

- <span data-ttu-id="13996-2966">Nr PESEL</span><span class="sxs-lookup"><span data-stu-id="13996-2966">Nr PESEL</span></span>
- <span data-ttu-id="13996-2967">PESEL</span><span class="sxs-lookup"><span data-stu-id="13996-2967">PESEL</span></span>   

   
## <a name="poland-passport"></a><span data-ttu-id="13996-2968">Passaporto Polonia</span><span class="sxs-lookup"><span data-stu-id="13996-2968">Poland Passport</span></span>

### <a name="format"></a><span data-ttu-id="13996-2969">Formato</span><span class="sxs-lookup"><span data-stu-id="13996-2969">Format</span></span>

<span data-ttu-id="13996-2970">Due lettere e sette cifre</span><span class="sxs-lookup"><span data-stu-id="13996-2970">Two letters and seven digits</span></span>

### <a name="pattern"></a><span data-ttu-id="13996-2971">Modello</span><span class="sxs-lookup"><span data-stu-id="13996-2971">Pattern</span></span>

<span data-ttu-id="13996-2972">Due lettere (senza distinzione tra maiuscole/minuscole) seguite da sette cifre</span><span class="sxs-lookup"><span data-stu-id="13996-2972">Two letters (not case sensitive) followed by seven digits</span></span>

### <a name="checksum"></a><span data-ttu-id="13996-2973">Checksum</span><span class="sxs-lookup"><span data-stu-id="13996-2973">Checksum</span></span>

<span data-ttu-id="13996-2974">Sì</span><span class="sxs-lookup"><span data-stu-id="13996-2974">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="13996-2975">Definizione</span><span class="sxs-lookup"><span data-stu-id="13996-2975">Definition</span></span>

<span data-ttu-id="13996-2976">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="13996-2976">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="13996-2977">La funzione Func_polish_passport_number restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="13996-2977">The function Func_polish_passport_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="13996-2978">Viene trovata una parola chiave da Keyword_polish_national_id_passport_number.</span><span class="sxs-lookup"><span data-stu-id="13996-2978">A keyword from Keyword_polish_national_id_passport_number is found.</span></span>
- <span data-ttu-id="13996-2979">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="13996-2979">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="13996-2980">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="13996-2980">Keywords</span></span>

#### <a name="keywordpolishnationalidpassportnumber"></a><span data-ttu-id="13996-2981">Keyword_polish_national_id_passport_number</span><span class="sxs-lookup"><span data-stu-id="13996-2981">Keyword_polish_national_id_passport_number</span></span>

- <span data-ttu-id="13996-2982">Numero Paszportu</span><span class="sxs-lookup"><span data-stu-id="13996-2982">Numer paszportu</span></span>
- <span data-ttu-id="13996-2983">Nr.</span><span class="sxs-lookup"><span data-stu-id="13996-2983">Nr.</span></span> <span data-ttu-id="13996-2984">Paszportu</span><span class="sxs-lookup"><span data-stu-id="13996-2984">Paszportu</span></span>
- <span data-ttu-id="13996-2985">Paszport</span><span class="sxs-lookup"><span data-stu-id="13996-2985">Paszport</span></span>

   
## <a name="portugal-citizen-card-number"></a><span data-ttu-id="13996-2986">Portogallo - Numero di carta del cittadino</span><span class="sxs-lookup"><span data-stu-id="13996-2986">Portugal Citizen Card Number</span></span>

### <a name="format"></a><span data-ttu-id="13996-2987">Formato</span><span class="sxs-lookup"><span data-stu-id="13996-2987">Format</span></span>

<span data-ttu-id="13996-2988">Otto cifre</span><span class="sxs-lookup"><span data-stu-id="13996-2988">Eight digits</span></span>

### <a name="pattern"></a><span data-ttu-id="13996-2989">Modello</span><span class="sxs-lookup"><span data-stu-id="13996-2989">Pattern</span></span>

<span data-ttu-id="13996-2990">Otto cifre</span><span class="sxs-lookup"><span data-stu-id="13996-2990">Eight digits</span></span>

### <a name="checksum"></a><span data-ttu-id="13996-2991">Checksum</span><span class="sxs-lookup"><span data-stu-id="13996-2991">Checksum</span></span>

<span data-ttu-id="13996-2992">No</span><span class="sxs-lookup"><span data-stu-id="13996-2992">No</span></span>

### <a name="definition"></a><span data-ttu-id="13996-2993">Definizione</span><span class="sxs-lookup"><span data-stu-id="13996-2993">Definition</span></span>

<span data-ttu-id="13996-2994">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="13996-2994">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="13996-2995">L'espressione regolare Regex_portugal_citizen_card trova il contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="13996-2995">The regular expression Regex_portugal_citizen_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="13996-2996">Viene trovata una parola chiave da Keyword_portugal_citizen_card.</span><span class="sxs-lookup"><span data-stu-id="13996-2996">A keyword from Keyword_portugal_citizen_card is found.</span></span>

```
<!-- Portugal Citizen Card Number -->
<Entity id="91a7ece2-add4-4986-9a15-c84544d81ecd" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Regex_portugal_citizen_card"/>
     <Match idRef="Keyword_portugal_citizen_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="13996-2997">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="13996-2997">Keywords</span></span>

#### <a name="keywordportugalcitizencard"></a><span data-ttu-id="13996-2998">Keyword_portugal_citizen_card</span><span class="sxs-lookup"><span data-stu-id="13996-2998">Keyword_portugal_citizen_card</span></span>

- <span data-ttu-id="13996-2999">Scheda cittadino</span><span class="sxs-lookup"><span data-stu-id="13996-2999">Citizen Card</span></span>
- <span data-ttu-id="13996-3000">Carta ID</span><span class="sxs-lookup"><span data-stu-id="13996-3000">National ID Card</span></span>
- <span data-ttu-id="13996-3001">CC</span><span class="sxs-lookup"><span data-stu-id="13996-3001">CC</span></span>
- <span data-ttu-id="13996-3002">Cartão de Cidadão</span><span class="sxs-lookup"><span data-stu-id="13996-3002">Cartão de Cidadão</span></span>
- <span data-ttu-id="13996-3003">Bilhete de Identidade</span><span class="sxs-lookup"><span data-stu-id="13996-3003">Bilhete de Identidade</span></span>
   
## <a name="saudi-arabia-national-id"></a><span data-ttu-id="13996-3004">Arabia Saudita - Identificativo nazionale</span><span class="sxs-lookup"><span data-stu-id="13996-3004">Saudi Arabia National ID</span></span>

### <a name="format"></a><span data-ttu-id="13996-3005">Formato</span><span class="sxs-lookup"><span data-stu-id="13996-3005">Format</span></span>

<span data-ttu-id="13996-3006">10 cifre</span><span class="sxs-lookup"><span data-stu-id="13996-3006">10 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="13996-3007">Modello</span><span class="sxs-lookup"><span data-stu-id="13996-3007">Pattern</span></span>

<span data-ttu-id="13996-3008">10 cifre consecutive</span><span class="sxs-lookup"><span data-stu-id="13996-3008">10 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="13996-3009">Checksum</span><span class="sxs-lookup"><span data-stu-id="13996-3009">Checksum</span></span>

<span data-ttu-id="13996-3010">No</span><span class="sxs-lookup"><span data-stu-id="13996-3010">No</span></span>

### <a name="definition"></a><span data-ttu-id="13996-3011">Definizione</span><span class="sxs-lookup"><span data-stu-id="13996-3011">Definition</span></span>

<span data-ttu-id="13996-3012">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="13996-3012">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="13996-3013">L'espressione regolare Regex_saudi_arabia_national_id restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="13996-3013">The regular expression Regex_saudi_arabia_national_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="13996-3014">Viene trovata una parola chiave da Keyword_saudi_arabia_national_id.</span><span class="sxs-lookup"><span data-stu-id="13996-3014">A keyword from Keyword_saudi_arabia_national_id is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="13996-3015">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="13996-3015">Keywords</span></span>

#### <a name="keywordsaudiarabianationalid"></a><span data-ttu-id="13996-3016">Keyword_saudi_arabia_national_id</span><span class="sxs-lookup"><span data-stu-id="13996-3016">Keyword_saudi_arabia_national_id</span></span>

- <span data-ttu-id="13996-3017">Identification Card</span><span class="sxs-lookup"><span data-stu-id="13996-3017">Identification Card</span></span> 
- <span data-ttu-id="13996-3018">I card number</span><span class="sxs-lookup"><span data-stu-id="13996-3018">I card number</span></span> 
- <span data-ttu-id="13996-3019">ID number</span><span class="sxs-lookup"><span data-stu-id="13996-3019">ID number</span></span> 
- <span data-ttu-id="13996-3020">الوطنية الهوية بطاقة رقم</span><span class="sxs-lookup"><span data-stu-id="13996-3020">الوطنية الهوية بطاقة رقم</span></span> 

   
## <a name="singapore-national-registration-identity-card-nric-number"></a><span data-ttu-id="13996-3021">Singapore - Numero di carta di identità di registrazione nazionale (NRIC)</span><span class="sxs-lookup"><span data-stu-id="13996-3021">Singapore National Registration Identity Card (NRIC) Number</span></span>

### <a name="format"></a><span data-ttu-id="13996-3022">Formato</span><span class="sxs-lookup"><span data-stu-id="13996-3022">Format</span></span>

<span data-ttu-id="13996-3023">Nove lettere e numeri</span><span class="sxs-lookup"><span data-stu-id="13996-3023">Nine letters and digits</span></span>

### <a name="pattern"></a><span data-ttu-id="13996-3024">Modello</span><span class="sxs-lookup"><span data-stu-id="13996-3024">Pattern</span></span>

- <span data-ttu-id="13996-3025">Nove lettere e numeri:</span><span class="sxs-lookup"><span data-stu-id="13996-3025">Nine letters and digits:</span></span>
- <span data-ttu-id="13996-3026">La lettera "F", "G", "S" o "T" (senza distinzione tra maiuscole e minuscole) </span><span class="sxs-lookup"><span data-stu-id="13996-3026">The letter "F", "G", "S", or "T" (not case sensitive)</span></span> 
- <span data-ttu-id="13996-3027">Sette cifre</span><span class="sxs-lookup"><span data-stu-id="13996-3027">Seven digits</span></span> 
- <span data-ttu-id="13996-3028">Una cifra di controllo alfabetica</span><span class="sxs-lookup"><span data-stu-id="13996-3028">An alphabetic check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="13996-3029">Checksum</span><span class="sxs-lookup"><span data-stu-id="13996-3029">Checksum</span></span>

<span data-ttu-id="13996-3030">Sì</span><span class="sxs-lookup"><span data-stu-id="13996-3030">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="13996-3031">Definizione</span><span class="sxs-lookup"><span data-stu-id="13996-3031">Definition</span></span>

<span data-ttu-id="13996-3032">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="13996-3032">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="13996-3033">L'espressione regolare Regex_singapore_nric trova il contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="13996-3033">The regular expression Regex_singapore_nric finds content that matches the pattern.</span></span>
- <span data-ttu-id="13996-3034">Viene trovata una parola chiave da Keyword_singapore_nric.</span><span class="sxs-lookup"><span data-stu-id="13996-3034">A keyword from Keyword_singapore_nric is found.</span></span>
- <span data-ttu-id="13996-3035">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="13996-3035">The checksum passes.</span></span>

<span data-ttu-id="13996-3036">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="13996-3036">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="13996-3037">L'espressione regolare Regex_singapore_nric trova il contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="13996-3037">The regular expression Regex_singapore_nric finds content that matches the pattern.</span></span>
- <span data-ttu-id="13996-3038">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="13996-3038">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="13996-3039">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="13996-3039">Keywords</span></span>
   
#### <a name="keywordsingaporenric"></a><span data-ttu-id="13996-3040">Keyword_singapore_nric</span><span class="sxs-lookup"><span data-stu-id="13996-3040">Keyword_singapore_nric</span></span>

- <span data-ttu-id="13996-3041">Carta di identità di registrazione nazionale</span><span class="sxs-lookup"><span data-stu-id="13996-3041">National Registration Identity Card</span></span> 
- <span data-ttu-id="13996-3042">Numero di carta di identità</span><span class="sxs-lookup"><span data-stu-id="13996-3042">Identity Card Number</span></span> 
- <span data-ttu-id="13996-3043">NRIC</span><span class="sxs-lookup"><span data-stu-id="13996-3043">NRIC</span></span> 
- <span data-ttu-id="13996-3044">IC</span><span class="sxs-lookup"><span data-stu-id="13996-3044">IC</span></span> 
- <span data-ttu-id="13996-3045">Numero di identificazione per stranieri</span><span class="sxs-lookup"><span data-stu-id="13996-3045">Foreign Identification Number</span></span> 
- <span data-ttu-id="13996-3046">FIN</span><span class="sxs-lookup"><span data-stu-id="13996-3046">FIN</span></span> 
- <span data-ttu-id="13996-3047">身份证</span><span class="sxs-lookup"><span data-stu-id="13996-3047">身份证</span></span> 
- <span data-ttu-id="13996-3048">身份證</span><span class="sxs-lookup"><span data-stu-id="13996-3048">身份證</span></span> 
   
## <a name="south-africa-identification-number"></a><span data-ttu-id="13996-3049">Sudafrica - Numero di identificazione
</span><span class="sxs-lookup"><span data-stu-id="13996-3049">South Africa Identification Number</span></span>

### <a name="format"></a><span data-ttu-id="13996-3050">Formato</span><span class="sxs-lookup"><span data-stu-id="13996-3050">Format</span></span>

<span data-ttu-id="13996-3051">13 cifre che possono contenere spazi</span><span class="sxs-lookup"><span data-stu-id="13996-3051">13 digits that may contain spaces</span></span>

### <a name="pattern"></a><span data-ttu-id="13996-3052">Modello</span><span class="sxs-lookup"><span data-stu-id="13996-3052">Pattern</span></span>

<span data-ttu-id="13996-3053">13 cifre:</span><span class="sxs-lookup"><span data-stu-id="13996-3053">13 digits:</span></span>
- <span data-ttu-id="13996-3054">Sei cifre nel formato AAMMGG, ovvero la data di nascita</span><span class="sxs-lookup"><span data-stu-id="13996-3054">Six digits in the format YYMMDD which are the date of birth</span></span> 
- <span data-ttu-id="13996-3055">Quattro cifre</span><span class="sxs-lookup"><span data-stu-id="13996-3055">Four digits</span></span> 
- <span data-ttu-id="13996-3056">Un indicatore di cittadinanza a una cifra </span><span class="sxs-lookup"><span data-stu-id="13996-3056">A single-digit citizenship indicator</span></span> 
- <span data-ttu-id="13996-3057">La cifra "8" o "9" </span><span class="sxs-lookup"><span data-stu-id="13996-3057">The digit "8" or "9"</span></span> 
- <span data-ttu-id="13996-3058">Una cifra, ovvero una cifra di checksum</span><span class="sxs-lookup"><span data-stu-id="13996-3058">One digit which is a checksum digit</span></span>

### <a name="checksum"></a><span data-ttu-id="13996-3059">Checksum</span><span class="sxs-lookup"><span data-stu-id="13996-3059">Checksum</span></span>

<span data-ttu-id="13996-3060">Sì</span><span class="sxs-lookup"><span data-stu-id="13996-3060">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="13996-3061">Definizione</span><span class="sxs-lookup"><span data-stu-id="13996-3061">Definition</span></span>

<span data-ttu-id="13996-3062">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="13996-3062">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="13996-3063">La funzione Func_south_africa_identification_number trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="13996-3063">The function Func_south_africa_identification_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="13996-3064">Viene trovata una parola chiave da Keyword_south_africa_identification_number.</span><span class="sxs-lookup"><span data-stu-id="13996-3064">A keyword from Keyword_south_africa_identification_number is found.</span></span>
- <span data-ttu-id="13996-3065">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="13996-3065">The checksum passes.</span></span>

```
<!-- South Africa Identification Number -->
<Entity id="e2adf7cb-8ea6-4048-a2ed-d89eb65f2780" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_south_africa_identification_number"/>
     <Match idRef="Keyword_south_africa_identification_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="13996-3066">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="13996-3066">Keywords</span></span>
   
#### <a name="keywordsouthafricaidentificationnumber"></a><span data-ttu-id="13996-3067">Keyword_south_africa_identification_number</span><span class="sxs-lookup"><span data-stu-id="13996-3067">Keyword_south_africa_identification_number</span></span>

- <span data-ttu-id="13996-3068">Carta di identità</span><span class="sxs-lookup"><span data-stu-id="13996-3068">Identity card</span></span>
- <span data-ttu-id="13996-3069">ID</span><span class="sxs-lookup"><span data-stu-id="13996-3069">ID</span></span>
- <span data-ttu-id="13996-3070">Identificazione</span><span class="sxs-lookup"><span data-stu-id="13996-3070">Identification</span></span> 
   
## <a name="south-korea-resident-registration-number"></a><span data-ttu-id="13996-3071">Corea del Sud - Numero di registrazione dei residenti</span><span class="sxs-lookup"><span data-stu-id="13996-3071">South Korea Resident Registration Number</span></span>

### <a name="format"></a><span data-ttu-id="13996-3072">Formato</span><span class="sxs-lookup"><span data-stu-id="13996-3072">Format</span></span>

<span data-ttu-id="13996-3073">13 cifre contenenti un segno meno</span><span class="sxs-lookup"><span data-stu-id="13996-3073">13 digits containing a hyphen</span></span>

### <a name="pattern"></a><span data-ttu-id="13996-3074">Modello</span><span class="sxs-lookup"><span data-stu-id="13996-3074">Pattern</span></span>

<span data-ttu-id="13996-3075">13 cifre:</span><span class="sxs-lookup"><span data-stu-id="13996-3075">13 digits:</span></span>
- <span data-ttu-id="13996-3076">Sei cifre nel formato AAMMGG, ovvero la data di nascita</span><span class="sxs-lookup"><span data-stu-id="13996-3076">Six digits in the format YYMMDD which are the date of birth</span></span> 
- <span data-ttu-id="13996-3077">Una lineetta</span><span class="sxs-lookup"><span data-stu-id="13996-3077">A hyphen</span></span> 
- <span data-ttu-id="13996-3078">Una cifra determinata dal secolo e dal sesso </span><span class="sxs-lookup"><span data-stu-id="13996-3078">One digit determined by the century and gender</span></span> 
- <span data-ttu-id="13996-3079">Codice di quattro cifre dell’area geografica di nascita </span><span class="sxs-lookup"><span data-stu-id="13996-3079">Four-digit region-of-birth code</span></span> 
- <span data-ttu-id="13996-3080">Una cifra utilizzata per distinguere persone i cui numeri precedenti sono uguali </span><span class="sxs-lookup"><span data-stu-id="13996-3080">One digit used to differentiate people for whom the preceding numbers are identical</span></span> 
- <span data-ttu-id="13996-3081">Una cifra di controllo.</span><span class="sxs-lookup"><span data-stu-id="13996-3081">A check digit.</span></span>

### <a name="checksum"></a><span data-ttu-id="13996-3082">Checksum</span><span class="sxs-lookup"><span data-stu-id="13996-3082">Checksum</span></span>

<span data-ttu-id="13996-3083">Sì</span><span class="sxs-lookup"><span data-stu-id="13996-3083">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="13996-3084">Definizione</span><span class="sxs-lookup"><span data-stu-id="13996-3084">Definition</span></span>

<span data-ttu-id="13996-3085">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="13996-3085">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="13996-3086">La funzione Func_south_korea_resident_number trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="13996-3086">The function Func_south_korea_resident_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="13996-3087">Viene trovata una parola chiave da Keyword_south_korea_resident_number.</span><span class="sxs-lookup"><span data-stu-id="13996-3087">A keyword from Keyword_south_korea_resident_number is found.</span></span>
- <span data-ttu-id="13996-3088">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="13996-3088">The checksum passes.</span></span>

<span data-ttu-id="13996-3089">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="13996-3089">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="13996-3090">La funzione Func_south_korea_resident_number trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="13996-3090">The function Func_south_korea_resident_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="13996-3091">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="13996-3091">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="13996-3092">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="13996-3092">Keywords</span></span>
   
#### <a name="keywordsouthkorearesidentnumber"></a><span data-ttu-id="13996-3093">Keyword_south_korea_resident_number</span><span class="sxs-lookup"><span data-stu-id="13996-3093">Keyword_south_korea_resident_number</span></span>

- <span data-ttu-id="13996-3094">Carta di identità</span><span class="sxs-lookup"><span data-stu-id="13996-3094">National ID card</span></span> 
- <span data-ttu-id="13996-3095">Numero di registrazione del cittadino</span><span class="sxs-lookup"><span data-stu-id="13996-3095">Citizen's Registration Number</span></span> 
- <span data-ttu-id="13996-3096">Jumin deungnok beonho</span><span class="sxs-lookup"><span data-stu-id="13996-3096">Jumin deungnok beonho</span></span> 
- <span data-ttu-id="13996-3097">RRN</span><span class="sxs-lookup"><span data-stu-id="13996-3097">RRN</span></span> 
- <span data-ttu-id="13996-3098">주민등록번호</span><span class="sxs-lookup"><span data-stu-id="13996-3098">주민등록번호</span></span>
   
## <a name="spain-social-security-number-ssn"></a><span data-ttu-id="13996-3099">Spagna - Numero di previdenza sociale (SSN)</span><span class="sxs-lookup"><span data-stu-id="13996-3099">Spain Social Security Number (SSN)</span></span>

### <a name="format"></a><span data-ttu-id="13996-3100">Formato</span><span class="sxs-lookup"><span data-stu-id="13996-3100">Format</span></span>

<span data-ttu-id="13996-3101">11-12 cifre</span><span class="sxs-lookup"><span data-stu-id="13996-3101">11-12 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="13996-3102">Modello</span><span class="sxs-lookup"><span data-stu-id="13996-3102">Pattern</span></span>

<span data-ttu-id="13996-3103">11-12 cifre:</span><span class="sxs-lookup"><span data-stu-id="13996-3103">11-12 digits:</span></span>
- <span data-ttu-id="13996-3104">Due cifre</span><span class="sxs-lookup"><span data-stu-id="13996-3104">Two digits</span></span> 
- <span data-ttu-id="13996-3105">Una barra (facoltativa)</span><span class="sxs-lookup"><span data-stu-id="13996-3105">A forward slash (optional)</span></span> 
- <span data-ttu-id="13996-3106">7-8 cifre</span><span class="sxs-lookup"><span data-stu-id="13996-3106">7-8 digits</span></span> 
- <span data-ttu-id="13996-3107">Una barra (facoltativa)</span><span class="sxs-lookup"><span data-stu-id="13996-3107">A forward slash (optional)</span></span> 
- <span data-ttu-id="13996-3108">Due cifre</span><span class="sxs-lookup"><span data-stu-id="13996-3108">Two digits</span></span>

### <a name="checksum"></a><span data-ttu-id="13996-3109">Checksum</span><span class="sxs-lookup"><span data-stu-id="13996-3109">Checksum</span></span>

<span data-ttu-id="13996-3110">Sì</span><span class="sxs-lookup"><span data-stu-id="13996-3110">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="13996-3111">Definizione</span><span class="sxs-lookup"><span data-stu-id="13996-3111">Definition</span></span>

<span data-ttu-id="13996-3112">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="13996-3112">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="13996-3113">La funzione Func_spanish_social_security_number restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="13996-3113">The function Func_spanish_social_security_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="13996-3114">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="13996-3114">The checksum passes.</span></span>

```
<!-- Spain SSN -->
<Entity id="5df987c0-8eae-4bce-ace7-b316347f3070" patternsProximity="300" recommendedConfidence="85">
    <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_spanish_social_security_number" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="13996-3115">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="13996-3115">Keywords</span></span>

<span data-ttu-id="13996-3116">Nessuno</span><span class="sxs-lookup"><span data-stu-id="13996-3116">None</span></span>

## <a name="sql-server-connection-string"></a><span data-ttu-id="13996-3117">Stringa di connessione di SQL Server</span><span class="sxs-lookup"><span data-stu-id="13996-3117">SQL Server Connection String</span></span>

### <a name="format"></a><span data-ttu-id="13996-3118">Formato</span><span class="sxs-lookup"><span data-stu-id="13996-3118">Format</span></span>

<span data-ttu-id="13996-3119">Stringa "ID utente", "ID utente", "UID" o "UserId" seguito dai caratteri e dalle stringhe delineati nel modello seguente.</span><span class="sxs-lookup"><span data-stu-id="13996-3119">The string "User Id", "User ID", "uid", or "UserId" followed by the characters and strings outlined in the pattern below.</span></span>

### <a name="pattern"></a><span data-ttu-id="13996-3120">Modello</span><span class="sxs-lookup"><span data-stu-id="13996-3120">Pattern</span></span>

- <span data-ttu-id="13996-3121">Stringa "ID utente", "ID utente", "UID" o "UserId"</span><span class="sxs-lookup"><span data-stu-id="13996-3121">The string "User Id", "User ID", "uid", or "UserId"</span></span>
- <span data-ttu-id="13996-3122">Qualsiasi combinazione tra 1-200 lettere, cifre, simboli, caratteri speciali o spazi in maiuscolo o minuscolo</span><span class="sxs-lookup"><span data-stu-id="13996-3122">Any combination of between 1-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="13996-3123">La stringa "password" o "pwd", dove "pwd" non è preceduta da una lettera minuscola</span><span class="sxs-lookup"><span data-stu-id="13996-3123">The string "Password" or "pwd" where "pwd" is not preceded by a lowercase letter</span></span>
- <span data-ttu-id="13996-3124">Segno di uguale (=)</span><span class="sxs-lookup"><span data-stu-id="13996-3124">An equal sign (=)</span></span>
- <span data-ttu-id="13996-3125">Qualsiasi carattere non costituito da un segno di dollaro ($), un simbolo di percentuale (%), un simbolo maggiore di (>), un simbolo (@), una virgoletta ("), un punto e virgola (;), una parentesi graffa sinistra ([) o una parentesi quadra sinistra ({)</span><span class="sxs-lookup"><span data-stu-id="13996-3125">Any character that is not a dollar sign ($), percent symbol (%), greater than symbol (>), at symbol (@), quotation mark ("), semicolon (;), left brace ([), or left bracket ({)</span></span>
- <span data-ttu-id="13996-3126">Qualsiasi combinazione di 7-128 caratteri che non sono un punto e virgola (;), barra (/) o virgolette (")</span><span class="sxs-lookup"><span data-stu-id="13996-3126">Any combination of 7-128 characters that are not a semicolon (;), forward slash (/), or quotation mark (")</span></span>
- <span data-ttu-id="13996-3127">Un punto e virgola (;) o virgolette (")</span><span class="sxs-lookup"><span data-stu-id="13996-3127">A semicolon (;) or quotation mark (")</span></span>

### <a name="checksum"></a><span data-ttu-id="13996-3128">Checksum</span><span class="sxs-lookup"><span data-stu-id="13996-3128">Checksum</span></span>

<span data-ttu-id="13996-3129">No</span><span class="sxs-lookup"><span data-stu-id="13996-3129">No</span></span>

### <a name="definition"></a><span data-ttu-id="13996-3130">Definizione</span><span class="sxs-lookup"><span data-stu-id="13996-3130">Definition</span></span>

<span data-ttu-id="13996-3131">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="13996-3131">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="13996-3132">L'espressione regolare CEP_Regex_SQLServerConnectionString trova il contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="13996-3132">The regular expression CEP_Regex_SQLServerConnectionString finds content that matches the pattern.</span></span>
- <span data-ttu-id="13996-3133">**Non** viene trovata una parola chiave da CEP_GlobalFilter.</span><span class="sxs-lookup"><span data-stu-id="13996-3133">A keyword from CEP_GlobalFilter is **not** found.</span></span>
- <span data-ttu-id="13996-3134">L'espressione regolare CEP_PasswordPlaceHolder non \*\*\*\* trova contenuto corrispondente al modello.</span><span class="sxs-lookup"><span data-stu-id="13996-3134">The regular expression CEP_PasswordPlaceHolder does **not** find content that matches the pattern.</span></span>
- <span data-ttu-id="13996-3135">L'espressione regolare CEP_CommonExampleKeywords non \*\*\*\* trova contenuto corrispondente al modello.</span><span class="sxs-lookup"><span data-stu-id="13996-3135">The regular expression CEP_CommonExampleKeywords does **not** find content that matches the pattern.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="13996-3136">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="13996-3136">Keywords</span></span>

#### <a name="cepglobalfilter"></a><span data-ttu-id="13996-3137">CEP_GlobalFilter</span><span class="sxs-lookup"><span data-stu-id="13996-3137">CEP_GlobalFilter</span></span>

- <span data-ttu-id="13996-3138">some-password</span><span class="sxs-lookup"><span data-stu-id="13996-3138">some-password</span></span>
- <span data-ttu-id="13996-3139">somepassword</span><span class="sxs-lookup"><span data-stu-id="13996-3139">somepassword</span></span>
- <span data-ttu-id="13996-3140">secretPassword</span><span class="sxs-lookup"><span data-stu-id="13996-3140">secretPassword</span></span>
- <span data-ttu-id="13996-3141">esempio</span><span class="sxs-lookup"><span data-stu-id="13996-3141">sample</span></span>

#### <a name="ceppasswordplaceholder"></a><span data-ttu-id="13996-3142">CEP_PasswordPlaceHolder</span><span class="sxs-lookup"><span data-stu-id="13996-3142">CEP_PasswordPlaceHolder</span></span>

<span data-ttu-id="13996-3143">Si noti che tecnicamente questo tipo di informazioni riservate identifica queste parole chiave utilizzando un'espressione regolare, non un elenco di parola chiave.</span><span class="sxs-lookup"><span data-stu-id="13996-3143">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="13996-3144">Password o pwd seguito da 0-2 spazi, un segno di uguale (=), 0-2 spazi e un asterisco (\*)-----------------</span><span class="sxs-lookup"><span data-stu-id="13996-3144">Password or pwd followed by 0-2 spaces, an equal sign (=), 0-2 spaces, and an asterisk (\*) --OR--</span></span>
- <span data-ttu-id="13996-3145">Password o pwd seguito da:</span><span class="sxs-lookup"><span data-stu-id="13996-3145">Password or pwd followed by:</span></span>
    - <span data-ttu-id="13996-3146">Segno di uguale (=)</span><span class="sxs-lookup"><span data-stu-id="13996-3146">Equal sign (=)</span></span>
    - <span data-ttu-id="13996-3147">Valore minore di (<)</span><span class="sxs-lookup"><span data-stu-id="13996-3147">Less than symbol (<)</span></span>
    - <span data-ttu-id="13996-3148">Qualsiasi combinazione di 1-200 caratteri che sono lettere maiuscole o minuscole, cifre, asterisco (\*), segno meno (-), sottolineatura (_) o carattere dello spazio vuoto</span><span class="sxs-lookup"><span data-stu-id="13996-3148">Any combination of 1-200 characters that are upper- or lowercase letters, digits, an asterisk (\*), hyphen (-), underline (_), or whitespace character</span></span>
    - <span data-ttu-id="13996-3149">Simbolo maggiore di (>)</span><span class="sxs-lookup"><span data-stu-id="13996-3149">Greater than symbol (>)</span></span>

#### <a name="cepcommonexamplekeywords"></a><span data-ttu-id="13996-3150">CEP_CommonExampleKeywords</span><span class="sxs-lookup"><span data-stu-id="13996-3150">CEP_CommonExampleKeywords</span></span>

<span data-ttu-id="13996-3151">Si noti che tecnicamente questo tipo di informazioni riservate identifica queste parole chiave utilizzando un'espressione regolare, non un elenco di parola chiave.</span><span class="sxs-lookup"><span data-stu-id="13996-3151">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="13996-3152">contoso</span><span class="sxs-lookup"><span data-stu-id="13996-3152">contoso</span></span>
- <span data-ttu-id="13996-3153">Fabrikam</span><span class="sxs-lookup"><span data-stu-id="13996-3153">fabrikam</span></span>
- <span data-ttu-id="13996-3154">Northwind</span><span class="sxs-lookup"><span data-stu-id="13996-3154">northwind</span></span>
- <span data-ttu-id="13996-3155">sandbox</span><span class="sxs-lookup"><span data-stu-id="13996-3155">sandbox</span></span>
- <span data-ttu-id="13996-3156">OneBox</span><span class="sxs-lookup"><span data-stu-id="13996-3156">onebox</span></span>
- <span data-ttu-id="13996-3157">localhost</span><span class="sxs-lookup"><span data-stu-id="13996-3157">localhost</span></span>
- <span data-ttu-id="13996-3158">127.0.0.1</span><span class="sxs-lookup"><span data-stu-id="13996-3158">127.0.0.1</span></span>
- <span data-ttu-id="13996-3159">testacs.</span><span class="sxs-lookup"><span data-stu-id="13996-3159">testacs.</span></span><!--no-hyperlink--><span data-ttu-id="13996-3160">com</span><span class="sxs-lookup"><span data-stu-id="13996-3160">com</span></span>
- <span data-ttu-id="13996-3161">s-int.</span><span class="sxs-lookup"><span data-stu-id="13996-3161">s-int.</span></span><!--no-hyperlink--><span data-ttu-id="13996-3162">NET</span><span class="sxs-lookup"><span data-stu-id="13996-3162">net</span></span>

## <a name="sweden-national-id"></a><span data-ttu-id="13996-3163">Svezia - Identificativo nazionale</span><span class="sxs-lookup"><span data-stu-id="13996-3163">Sweden National ID</span></span>

### <a name="format"></a><span data-ttu-id="13996-3164">Formato</span><span class="sxs-lookup"><span data-stu-id="13996-3164">Format</span></span>

<span data-ttu-id="13996-3165">10 o 12 cifre e un delimitatore facoltativo</span><span class="sxs-lookup"><span data-stu-id="13996-3165">10 or 12 digits and an optional delimiter</span></span>

### <a name="pattern"></a><span data-ttu-id="13996-3166">Modello</span><span class="sxs-lookup"><span data-stu-id="13996-3166">Pattern</span></span>

<span data-ttu-id="13996-3167">10 o 12 cifre e un delimitatore facoltativo:</span><span class="sxs-lookup"><span data-stu-id="13996-3167">10 or 12 digits and an optional delimiter:</span></span>
- <span data-ttu-id="13996-3168">2-4 cifre (facoltative)</span><span class="sxs-lookup"><span data-stu-id="13996-3168">2-4 digits (optional)</span></span> 
- <span data-ttu-id="13996-3169">Sei cifre nel formato data AAMMGG</span><span class="sxs-lookup"><span data-stu-id="13996-3169">Six digits in date format YYMMDD</span></span> 
- <span data-ttu-id="13996-3170">Delimitatore di "-" o "+" (facoltativo) più</span><span class="sxs-lookup"><span data-stu-id="13996-3170">Delimiter of "-" or "+" (optional), plus</span></span>
- <span data-ttu-id="13996-3171">Quattro cifre</span><span class="sxs-lookup"><span data-stu-id="13996-3171">Four digits</span></span>

### <a name="checksum"></a><span data-ttu-id="13996-3172">Checksum</span><span class="sxs-lookup"><span data-stu-id="13996-3172">Checksum</span></span>

<span data-ttu-id="13996-3173">Sì</span><span class="sxs-lookup"><span data-stu-id="13996-3173">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="13996-3174">Definizione</span><span class="sxs-lookup"><span data-stu-id="13996-3174">Definition</span></span>

<span data-ttu-id="13996-3175">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="13996-3175">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="13996-3176">La funzione Func_swedish_national_identifier restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="13996-3176">The function Func_swedish_national_identifier finds content that matches the pattern.</span></span>
- <span data-ttu-id="13996-3177">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="13996-3177">The checksum passes.</span></span>

```
<!-- Sweden National ID -->
<Entity id="f69aaf40-79be-4fac-8f05-fd1910d272c8" patternsProximity="300" recommendedConfidence="85">
    <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_swedish_national_identifier" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="13996-3178">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="13996-3178">Keywords</span></span>

<span data-ttu-id="13996-3179">No</span><span class="sxs-lookup"><span data-stu-id="13996-3179">No</span></span>
   
## <a name="sweden-passport-number"></a><span data-ttu-id="13996-3180">Svezia - Numero di passaporto</span><span class="sxs-lookup"><span data-stu-id="13996-3180">Sweden Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="13996-3181">Formato</span><span class="sxs-lookup"><span data-stu-id="13996-3181">Format</span></span>

<span data-ttu-id="13996-3182">Otto cifre</span><span class="sxs-lookup"><span data-stu-id="13996-3182">Eight digits</span></span>

### <a name="pattern"></a><span data-ttu-id="13996-3183">Modello</span><span class="sxs-lookup"><span data-stu-id="13996-3183">Pattern</span></span>

<span data-ttu-id="13996-3184">Otto cifre consecutive</span><span class="sxs-lookup"><span data-stu-id="13996-3184">Eight consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="13996-3185">Checksum</span><span class="sxs-lookup"><span data-stu-id="13996-3185">Checksum</span></span>

<span data-ttu-id="13996-3186">No</span><span class="sxs-lookup"><span data-stu-id="13996-3186">No</span></span>

### <a name="definition"></a><span data-ttu-id="13996-3187">Definizione</span><span class="sxs-lookup"><span data-stu-id="13996-3187">Definition</span></span>

<span data-ttu-id="13996-3188">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="13996-3188">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="13996-3189">L'espressione regolare Regex_sweden_passport_number restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="13996-3189">The regular expression Regex_sweden_passport_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="13996-3190">Si verifica una delle situazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="13996-3190">One of the following is true:</span></span>
    - <span data-ttu-id="13996-3191">Viene trovata una parola chiave da Keyword_passport.</span><span class="sxs-lookup"><span data-stu-id="13996-3191">A keyword from Keyword_passport is found.</span></span>
    - <span data-ttu-id="13996-3192">Viene trovata una parola chiave da Keyword_sweden_passport.</span><span class="sxs-lookup"><span data-stu-id="13996-3192">A keyword from Keyword_sweden_passport is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="13996-3193">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="13996-3193">Keywords</span></span>
   
#### <a name="keywordswedenpassport"></a><span data-ttu-id="13996-3194">Keyword_sweden_passport</span><span class="sxs-lookup"><span data-stu-id="13996-3194">Keyword_sweden_passport</span></span>

- <span data-ttu-id="13996-3195">visa requirements</span><span class="sxs-lookup"><span data-stu-id="13996-3195">visa requirements</span></span> 
- <span data-ttu-id="13996-3196">Alien Registration Card</span><span class="sxs-lookup"><span data-stu-id="13996-3196">Alien Registration Card</span></span> 
- <span data-ttu-id="13996-3197">Schengen visas</span><span class="sxs-lookup"><span data-stu-id="13996-3197">Schengen visas</span></span> 
- <span data-ttu-id="13996-3198">Schengen visa</span><span class="sxs-lookup"><span data-stu-id="13996-3198">Schengen visa</span></span> 
- <span data-ttu-id="13996-3199">Visa Processing</span><span class="sxs-lookup"><span data-stu-id="13996-3199">Visa Processing</span></span> 
- <span data-ttu-id="13996-3200">Visa Type</span><span class="sxs-lookup"><span data-stu-id="13996-3200">Visa Type</span></span> 
- <span data-ttu-id="13996-3201">Single Entry</span><span class="sxs-lookup"><span data-stu-id="13996-3201">Single Entry</span></span> 
- <span data-ttu-id="13996-3202">Multiple Entry</span><span class="sxs-lookup"><span data-stu-id="13996-3202">Multiple Entry</span></span> 
- <span data-ttu-id="13996-3203">G3 Processing Fees</span><span class="sxs-lookup"><span data-stu-id="13996-3203">G3 Processing Fees</span></span> 

#### <a name="keywordpassport"></a><span data-ttu-id="13996-3204">Keyword_passport</span><span class="sxs-lookup"><span data-stu-id="13996-3204">Keyword_passport</span></span>

- <span data-ttu-id="13996-3205">Passport Number</span><span class="sxs-lookup"><span data-stu-id="13996-3205">Passport Number</span></span> 
- <span data-ttu-id="13996-3206">Passport No</span><span class="sxs-lookup"><span data-stu-id="13996-3206">Passport No</span></span> 
- <span data-ttu-id="13996-3207">Passport#</span><span class="sxs-lookup"><span data-stu-id="13996-3207">Passport #</span></span> 
- <span data-ttu-id="13996-3208">Passaporto</span><span class="sxs-lookup"><span data-stu-id="13996-3208">Passport#</span></span> 
- <span data-ttu-id="13996-3209">PassportID</span><span class="sxs-lookup"><span data-stu-id="13996-3209">PassportID</span></span> 
- <span data-ttu-id="13996-3210">Passportno</span><span class="sxs-lookup"><span data-stu-id="13996-3210">Passportno</span></span> 
- <span data-ttu-id="13996-3211">passportnumber</span><span class="sxs-lookup"><span data-stu-id="13996-3211">passportnumber</span></span> 
- <span data-ttu-id="13996-3212">パスポート</span><span class="sxs-lookup"><span data-stu-id="13996-3212">パスポート</span></span> 
- <span data-ttu-id="13996-3213">パスポート番号</span><span class="sxs-lookup"><span data-stu-id="13996-3213">パスポート番号</span></span> 
- <span data-ttu-id="13996-3214">パスポートのNum</span><span class="sxs-lookup"><span data-stu-id="13996-3214">パスポートのNum</span></span> 
- <span data-ttu-id="13996-3215">パスポート #</span><span class="sxs-lookup"><span data-stu-id="13996-3215">パスポート＃</span></span> 
- <span data-ttu-id="13996-3216">Numéro de passeport</span><span class="sxs-lookup"><span data-stu-id="13996-3216">Numéro de passeport</span></span> 
- <span data-ttu-id="13996-3217">Passeport n °</span><span class="sxs-lookup"><span data-stu-id="13996-3217">Passeport n °</span></span> 
- <span data-ttu-id="13996-3218">Passeport Non</span><span class="sxs-lookup"><span data-stu-id="13996-3218">Passeport Non</span></span> 
- <span data-ttu-id="13996-3219">Passeport#</span><span class="sxs-lookup"><span data-stu-id="13996-3219">Passeport #</span></span> 
- <span data-ttu-id="13996-3220">Passeport</span><span class="sxs-lookup"><span data-stu-id="13996-3220">Passeport#</span></span> 
- <span data-ttu-id="13996-3221">PasseportNon</span><span class="sxs-lookup"><span data-stu-id="13996-3221">PasseportNon</span></span> 
- <span data-ttu-id="13996-3222">Passeportn °</span><span class="sxs-lookup"><span data-stu-id="13996-3222">Passeportn °</span></span> 
   
## <a name="swift-code"></a><span data-ttu-id="13996-3223">Codice SWIFT</span><span class="sxs-lookup"><span data-stu-id="13996-3223">SWIFT Code</span></span>

### <a name="format"></a><span data-ttu-id="13996-3224">Formato</span><span class="sxs-lookup"><span data-stu-id="13996-3224">Format</span></span>

<span data-ttu-id="13996-3225">Quattro lettere seguite da 5-31 lettere o cifre</span><span class="sxs-lookup"><span data-stu-id="13996-3225">Four letters followed by 5-31 letters or digits</span></span>

### <a name="pattern"></a><span data-ttu-id="13996-3226">Modello</span><span class="sxs-lookup"><span data-stu-id="13996-3226">Pattern</span></span>

<span data-ttu-id="13996-3227">Quattro lettere seguite da 5-31 lettere o cifre:</span><span class="sxs-lookup"><span data-stu-id="13996-3227">Four letters followed by 5-31 letters or digits:</span></span>
- <span data-ttu-id="13996-3228">Codice ABI di quattro cifre (senza distinzione tra maiuscole/minuscole)</span><span class="sxs-lookup"><span data-stu-id="13996-3228">Four-letter bank code (not case sensitive)</span></span> 
- <span data-ttu-id="13996-3229">Uno spazio facoltativo</span><span class="sxs-lookup"><span data-stu-id="13996-3229">An optional space</span></span> 
- <span data-ttu-id="13996-3230">4-28 lettere o cifre (BBAN)</span><span class="sxs-lookup"><span data-stu-id="13996-3230">4-28 letters or digits (the Basic Bank Account Number (BBAN))</span></span> 
- <span data-ttu-id="13996-3231">Uno spazio facoltativo</span><span class="sxs-lookup"><span data-stu-id="13996-3231">An optional space</span></span> 
- <span data-ttu-id="13996-3232">1-3 lettere o cifre (resto del BBAN)</span><span class="sxs-lookup"><span data-stu-id="13996-3232">1-3 letters or digits (remainder of the BBAN)</span></span>

### <a name="checksum"></a><span data-ttu-id="13996-3233">Checksum</span><span class="sxs-lookup"><span data-stu-id="13996-3233">Checksum</span></span>

<span data-ttu-id="13996-3234">No</span><span class="sxs-lookup"><span data-stu-id="13996-3234">No</span></span>

### <a name="definition"></a><span data-ttu-id="13996-3235">Definizione</span><span class="sxs-lookup"><span data-stu-id="13996-3235">Definition</span></span>

<span data-ttu-id="13996-3236">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="13996-3236">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="13996-3237">L'espressione regolare Regex_swift restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="13996-3237">The regular expression Regex_swift finds content that matches the pattern.</span></span>
- <span data-ttu-id="13996-3238">Viene trovata una parola chiave da Keyword_swift.</span><span class="sxs-lookup"><span data-stu-id="13996-3238">A keyword from Keyword_swift is found.</span></span>

```
<Entity id="cb2ab58c-9cb8-4c81-baf8-a4e106791df4" patternsProximity="300" recommendedConfidence="75">
<Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_swift" />
        <Match idRef="Keyword_swift" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="13996-3239">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="13996-3239">Keywords</span></span>
   
#### <a name="keywordswift"></a><span data-ttu-id="13996-3240">Keyword_swift</span><span class="sxs-lookup"><span data-stu-id="13996-3240">Keyword_swift</span></span>

- <span data-ttu-id="13996-3241">international organization for standardization 9362</span><span class="sxs-lookup"><span data-stu-id="13996-3241">international organization for standardization 9362</span></span> 
- <span data-ttu-id="13996-3242">iso 9362</span><span class="sxs-lookup"><span data-stu-id="13996-3242">iso 9362</span></span> 
- <span data-ttu-id="13996-3243">iso9362</span><span class="sxs-lookup"><span data-stu-id="13996-3243">iso9362</span></span> 
- <span data-ttu-id="13996-3244">Swift\#</span><span class="sxs-lookup"><span data-stu-id="13996-3244">swift\#</span></span> 
- <span data-ttu-id="13996-3245">swiftcode</span><span class="sxs-lookup"><span data-stu-id="13996-3245">swiftcode</span></span> 
- <span data-ttu-id="13996-3246">swiftnumber</span><span class="sxs-lookup"><span data-stu-id="13996-3246">swiftnumber</span></span> 
- <span data-ttu-id="13996-3247">swiftroutingnumber</span><span class="sxs-lookup"><span data-stu-id="13996-3247">swiftroutingnumber</span></span> 
- <span data-ttu-id="13996-3248">swift code</span><span class="sxs-lookup"><span data-stu-id="13996-3248">swift code</span></span> 
- <span data-ttu-id="13996-3249">swift number #</span><span class="sxs-lookup"><span data-stu-id="13996-3249">swift number #</span></span> 
- <span data-ttu-id="13996-3250">swift routing number</span><span class="sxs-lookup"><span data-stu-id="13996-3250">swift routing number</span></span> 
- <span data-ttu-id="13996-3251">bic number</span><span class="sxs-lookup"><span data-stu-id="13996-3251">bic number</span></span> 
- <span data-ttu-id="13996-3252">bic code</span><span class="sxs-lookup"><span data-stu-id="13996-3252">bic code</span></span> 
- <span data-ttu-id="13996-3253">BIC\#</span><span class="sxs-lookup"><span data-stu-id="13996-3253">bic \#</span></span> 
- <span data-ttu-id="13996-3254">BIC\#</span><span class="sxs-lookup"><span data-stu-id="13996-3254">bic\#</span></span> 
- <span data-ttu-id="13996-3255">bank identifier code</span><span class="sxs-lookup"><span data-stu-id="13996-3255">bank identifier code</span></span> 
- <span data-ttu-id="13996-3256">標準化 9362</span><span class="sxs-lookup"><span data-stu-id="13996-3256">標準化9362</span></span> 
- <span data-ttu-id="13996-3257">迅速 #</span><span class="sxs-lookup"><span data-stu-id="13996-3257">迅速＃</span></span> 
- <span data-ttu-id="13996-3258">SWIFTコード</span><span class="sxs-lookup"><span data-stu-id="13996-3258">SWIFTコード</span></span> 
- <span data-ttu-id="13996-3259">SWIFT番号</span><span class="sxs-lookup"><span data-stu-id="13996-3259">SWIFT番号</span></span> 
- <span data-ttu-id="13996-3260">迅速なルーティング番号</span><span class="sxs-lookup"><span data-stu-id="13996-3260">迅速なルーティング番号</span></span> 
- <span data-ttu-id="13996-3261">BIC番号</span><span class="sxs-lookup"><span data-stu-id="13996-3261">BIC番号</span></span> 
- <span data-ttu-id="13996-3262">BICコード</span><span class="sxs-lookup"><span data-stu-id="13996-3262">BICコード</span></span> 
- <span data-ttu-id="13996-3263">銀行識別コードのための国際組織</span><span class="sxs-lookup"><span data-stu-id="13996-3263">銀行識別コードのための国際組織</span></span> 
- <span data-ttu-id="13996-3264">Organisation internationale de normalisation 9362</span><span class="sxs-lookup"><span data-stu-id="13996-3264">Organisation internationale de normalisation 9362</span></span> 
- <span data-ttu-id="13996-3265">rapide\#</span><span class="sxs-lookup"><span data-stu-id="13996-3265">rapide \#</span></span> 
- <span data-ttu-id="13996-3266">code SWIFT</span><span class="sxs-lookup"><span data-stu-id="13996-3266">code SWIFT</span></span> 
- <span data-ttu-id="13996-3267">le numéro de swift</span><span class="sxs-lookup"><span data-stu-id="13996-3267">le numéro de swift</span></span> 
- <span data-ttu-id="13996-3268">swift numéro d'acheminement</span><span class="sxs-lookup"><span data-stu-id="13996-3268">swift numéro d'acheminement</span></span> 
- <span data-ttu-id="13996-3269">le numéro BIC</span><span class="sxs-lookup"><span data-stu-id="13996-3269">le numéro BIC</span></span> 
- <span data-ttu-id="13996-3270">\#BIC</span><span class="sxs-lookup"><span data-stu-id="13996-3270">\# BIC</span></span> 
- <span data-ttu-id="13996-3271">code identificateur de banque</span><span class="sxs-lookup"><span data-stu-id="13996-3271">code identificateur de banque</span></span> 
   
## <a name="taiwan-national-id"></a><span data-ttu-id="13996-3272">Taiwan National ID</span><span class="sxs-lookup"><span data-stu-id="13996-3272">Taiwan National ID</span></span>

### <a name="format"></a><span data-ttu-id="13996-3273">Formato</span><span class="sxs-lookup"><span data-stu-id="13996-3273">Format</span></span>

<span data-ttu-id="13996-3274">Una lettera (in lingua inglese) seguita da nove cifre</span><span class="sxs-lookup"><span data-stu-id="13996-3274">One letter (in English) followed by nine digits</span></span>

### <a name="pattern"></a><span data-ttu-id="13996-3275">Modello</span><span class="sxs-lookup"><span data-stu-id="13996-3275">Pattern</span></span>

<span data-ttu-id="13996-3276">Una lettera (in lingua inglese) seguita da nove cifre:</span><span class="sxs-lookup"><span data-stu-id="13996-3276">One letter (in English) followed by nine digits:</span></span>
- <span data-ttu-id="13996-3277">Una lettera (in inglese, senza distinzione tra tra maiuscole/minuscole)</span><span class="sxs-lookup"><span data-stu-id="13996-3277">One letter (in English, not case sensitive)</span></span> 
- <span data-ttu-id="13996-3278">La cifra "1" o "2"</span><span class="sxs-lookup"><span data-stu-id="13996-3278">The digit "1" or "2"</span></span> 
- <span data-ttu-id="13996-3279">Otto cifre</span><span class="sxs-lookup"><span data-stu-id="13996-3279">Eight digits</span></span>

### <a name="checksum"></a><span data-ttu-id="13996-3280">Checksum</span><span class="sxs-lookup"><span data-stu-id="13996-3280">Checksum</span></span>

<span data-ttu-id="13996-3281">Sì</span><span class="sxs-lookup"><span data-stu-id="13996-3281">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="13996-3282">Definizione</span><span class="sxs-lookup"><span data-stu-id="13996-3282">Definition</span></span>

<span data-ttu-id="13996-3283">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="13996-3283">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="13996-3284">La funzione Func_taiwanese_national_id restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="13996-3284">The function Func_taiwanese_national_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="13996-3285">Viene trovata una parola chiave da Keyword_taiwanese_national_id.</span><span class="sxs-lookup"><span data-stu-id="13996-3285">A keyword from Keyword_taiwanese_national_id is found.</span></span>
- <span data-ttu-id="13996-3286">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="13996-3286">The checksum passes.</span></span>

```
<!-- Taiwanese National ID -->
<Entity id="4C7BFC34-8DD1-421D-8FB7-6C6182C2AF03" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_taiwanese_national_id" />
          <Match idRef="Keyword_taiwanese_national_id" />
      </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="13996-3287">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="13996-3287">Keywords</span></span>

#### <a name="keywordtaiwanesenationalid"></a><span data-ttu-id="13996-3288">Keyword_taiwanese_national_id</span><span class="sxs-lookup"><span data-stu-id="13996-3288">Keyword_taiwanese_national_id</span></span>

- <span data-ttu-id="13996-3289">身份證字號</span><span class="sxs-lookup"><span data-stu-id="13996-3289">身份證字號</span></span> 
- <span data-ttu-id="13996-3290">身份證</span><span class="sxs-lookup"><span data-stu-id="13996-3290">身份證</span></span> 
- <span data-ttu-id="13996-3291">身份證號碼</span><span class="sxs-lookup"><span data-stu-id="13996-3291">身份證號碼</span></span> 
- <span data-ttu-id="13996-3292">身份證號</span><span class="sxs-lookup"><span data-stu-id="13996-3292">身份證號</span></span> 
- <span data-ttu-id="13996-3293">身分證字號</span><span class="sxs-lookup"><span data-stu-id="13996-3293">身分證字號</span></span> 
- <span data-ttu-id="13996-3294">身分證</span><span class="sxs-lookup"><span data-stu-id="13996-3294">身分證</span></span> 
- <span data-ttu-id="13996-3295">身分證號碼</span><span class="sxs-lookup"><span data-stu-id="13996-3295">身分證號碼</span></span> 
- <span data-ttu-id="13996-3296">身份證號</span><span class="sxs-lookup"><span data-stu-id="13996-3296">身份證號</span></span> 
- <span data-ttu-id="13996-3297">身分證統一編號</span><span class="sxs-lookup"><span data-stu-id="13996-3297">身分證統一編號</span></span> 
- <span data-ttu-id="13996-3298">國民身分證統一編號</span><span class="sxs-lookup"><span data-stu-id="13996-3298">國民身分證統一編號</span></span> 
- <span data-ttu-id="13996-3299">簽名</span><span class="sxs-lookup"><span data-stu-id="13996-3299">簽名</span></span> 
- <span data-ttu-id="13996-3300">蓋章</span><span class="sxs-lookup"><span data-stu-id="13996-3300">蓋章</span></span> 
- <span data-ttu-id="13996-3301">簽名或蓋章</span><span class="sxs-lookup"><span data-stu-id="13996-3301">簽名或蓋章</span></span> 
- <span data-ttu-id="13996-3302">簽章</span><span class="sxs-lookup"><span data-stu-id="13996-3302">簽章</span></span>   
   
## <a name="taiwan-passport-number"></a><span data-ttu-id="13996-3303">	Taiwan - Numero di passaporto</span><span class="sxs-lookup"><span data-stu-id="13996-3303">Taiwan Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="13996-3304">Formato</span><span class="sxs-lookup"><span data-stu-id="13996-3304">Format</span></span>

- <span data-ttu-id="13996-3305">Numero di passaporto biometrico: nove cifre</span><span class="sxs-lookup"><span data-stu-id="13996-3305">Biometric passport number: Nine digits</span></span>
- <span data-ttu-id="13996-3306">Numero di passaporto non biometrico: nove cifre</span><span class="sxs-lookup"><span data-stu-id="13996-3306">Non-biometric passport number: Nine digits</span></span>

### <a name="pattern"></a><span data-ttu-id="13996-3307">Modello</span><span class="sxs-lookup"><span data-stu-id="13996-3307">Pattern</span></span>
<span data-ttu-id="13996-3308">Numero di passaporto biometrico:</span><span class="sxs-lookup"><span data-stu-id="13996-3308">Biometric passport number:</span></span>
- <span data-ttu-id="13996-3309">La cifra "3" </span><span class="sxs-lookup"><span data-stu-id="13996-3309">The digit "3"</span></span> 
- <span data-ttu-id="13996-3310">Otto cifre</span><span class="sxs-lookup"><span data-stu-id="13996-3310">Eight digits</span></span>

<span data-ttu-id="13996-3311">Numero di passaporto non biometrico:</span><span class="sxs-lookup"><span data-stu-id="13996-3311">Non-biometric passport number:</span></span>
- <span data-ttu-id="13996-3312">9 cifre</span><span class="sxs-lookup"><span data-stu-id="13996-3312">Nine digits</span></span>

### <a name="checksum"></a><span data-ttu-id="13996-3313">Checksum</span><span class="sxs-lookup"><span data-stu-id="13996-3313">Checksum</span></span>

<span data-ttu-id="13996-3314">No</span><span class="sxs-lookup"><span data-stu-id="13996-3314">No</span></span>

### <a name="definition"></a><span data-ttu-id="13996-3315">Definizione</span><span class="sxs-lookup"><span data-stu-id="13996-3315">Definition</span></span>

<span data-ttu-id="13996-3316">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="13996-3316">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="13996-3317">L'espressione regolare Regex_taiwan_passport trova il contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="13996-3317">The regular expression Regex_taiwan_passport finds content that matches the pattern.</span></span>
- <span data-ttu-id="13996-3318">Viene trovata una parola chiave da Keyword_taiwan_passport.</span><span class="sxs-lookup"><span data-stu-id="13996-3318">A keyword from Keyword_taiwan_passport is found.</span></span>

```
<!-- Taiwan Passport Number -->
<Entity id="e7251cb4-4c2c-41df-963e-924eb3dae04a" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_taiwan_passport"/>
     <Match idRef="Keyword_taiwan_passport"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="13996-3319">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="13996-3319">Keywords</span></span>

#### <a name="keywordtaiwanpassport"></a><span data-ttu-id="13996-3320">Keyword_taiwan_passport</span><span class="sxs-lookup"><span data-stu-id="13996-3320">Keyword_taiwan_passport</span></span>

- <span data-ttu-id="13996-3321">Numero passaporto ROC</span><span class="sxs-lookup"><span data-stu-id="13996-3321">ROC passport number</span></span> 
- <span data-ttu-id="13996-3322">Numero passaporto</span><span class="sxs-lookup"><span data-stu-id="13996-3322">Passport number</span></span> 
- <span data-ttu-id="13996-3323">N° passaporto</span><span class="sxs-lookup"><span data-stu-id="13996-3323">Passport no</span></span> 
- <span data-ttu-id="13996-3324">Num. passaporto
</span><span class="sxs-lookup"><span data-stu-id="13996-3324">Passport Num</span></span> 
- <span data-ttu-id="13996-3325">Passport #</span><span class="sxs-lookup"><span data-stu-id="13996-3325">Passport #</span></span> 
- <span data-ttu-id="13996-3326">护照</span><span class="sxs-lookup"><span data-stu-id="13996-3326">护照</span></span> 
- <span data-ttu-id="13996-3327">中華民國護照</span><span class="sxs-lookup"><span data-stu-id="13996-3327">中華民國護照</span></span> 
- <span data-ttu-id="13996-3328">Zhōnghuá Mínguó hùzhào</span><span class="sxs-lookup"><span data-stu-id="13996-3328">Zhōnghuá Mínguó hùzhào</span></span>
   
## <a name="taiwan-resident-certificate-arctarc-number"></a><span data-ttu-id="13996-3329">Taiwan - Numero certificato di residenza (ARC/TARC)</span><span class="sxs-lookup"><span data-stu-id="13996-3329">Taiwan Resident Certificate (ARC/TARC) Number</span></span>

### <a name="format"></a><span data-ttu-id="13996-3330">Formato</span><span class="sxs-lookup"><span data-stu-id="13996-3330">Format</span></span>

<span data-ttu-id="13996-3331">10 lettere e cifre</span><span class="sxs-lookup"><span data-stu-id="13996-3331">10 letters and digits</span></span>

### <a name="pattern"></a><span data-ttu-id="13996-3332">Modello</span><span class="sxs-lookup"><span data-stu-id="13996-3332">Pattern</span></span>

<span data-ttu-id="13996-3333">10 lettere e cifre:</span><span class="sxs-lookup"><span data-stu-id="13996-3333">10 letters and digits:</span></span>
- <span data-ttu-id="13996-3334">Due lettere (senza distinzione tra maiuscole/minuscole)</span><span class="sxs-lookup"><span data-stu-id="13996-3334">Two letters (not case sensitive)</span></span> 
- <span data-ttu-id="13996-3335">Otto cifre</span><span class="sxs-lookup"><span data-stu-id="13996-3335">Eight digits</span></span>

### <a name="checksum"></a><span data-ttu-id="13996-3336">Checksum</span><span class="sxs-lookup"><span data-stu-id="13996-3336">Checksum</span></span>

<span data-ttu-id="13996-3337">No</span><span class="sxs-lookup"><span data-stu-id="13996-3337">No</span></span>

### <a name="definition"></a><span data-ttu-id="13996-3338">Definizione</span><span class="sxs-lookup"><span data-stu-id="13996-3338">Definition</span></span>

<span data-ttu-id="13996-3339">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="13996-3339">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="13996-3340">L'espressione regolare Regex_taiwan_resident_certificate trova il contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="13996-3340">The regular expression Regex_taiwan_resident_certificate finds content that matches the pattern.</span></span>
- <span data-ttu-id="13996-3341">Viene trovata una parola chiave da Keyword_taiwan_resident_certificate.</span><span class="sxs-lookup"><span data-stu-id="13996-3341">A keyword from Keyword_taiwan_resident_certificate is found.</span></span>

```
<!-- Taiwan Resident Certificate (ARC/TARC) -->
<Entity id="48269fec-05ea-46ea-b326-f5623a58c6e9" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_taiwan_resident_certificate"/>
     <Match idRef="Keyword_taiwan_resident_certificate"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="13996-3342">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="13996-3342">Keywords</span></span>

#### <a name="keywordtaiwanresidentcertificate"></a><span data-ttu-id="13996-3343">Keyword_taiwan_resident_certificate</span><span class="sxs-lookup"><span data-stu-id="13996-3343">Keyword_taiwan_resident_certificate</span></span>

- <span data-ttu-id="13996-3344">Certificato di residenza</span><span class="sxs-lookup"><span data-stu-id="13996-3344">Resident Certificate</span></span> 
- <span data-ttu-id="13996-3345">Cert. di resid
</span><span class="sxs-lookup"><span data-stu-id="13996-3345">Resident Cert</span></span> 
- <span data-ttu-id="13996-3346">Cert. di resid.
</span><span class="sxs-lookup"><span data-stu-id="13996-3346">Resident Cert.</span></span> 
- <span data-ttu-id="13996-3347">Carta d’identità</span><span class="sxs-lookup"><span data-stu-id="13996-3347">Identification card</span></span> 
- <span data-ttu-id="13996-3348">Certificato residente straniero</span><span class="sxs-lookup"><span data-stu-id="13996-3348">Alien Resident Certificate</span></span> 
- <span data-ttu-id="13996-3349">ARCO</span><span class="sxs-lookup"><span data-stu-id="13996-3349">ARC</span></span> 
- <span data-ttu-id="13996-3350">Certificato residente nell’area di Taiwan</span><span class="sxs-lookup"><span data-stu-id="13996-3350">Taiwan Area Resident Certificate</span></span> 
- <span data-ttu-id="13996-3351">TARC Tax</span><span class="sxs-lookup"><span data-stu-id="13996-3351">TARC</span></span> 
- <span data-ttu-id="13996-3352">居留證</span><span class="sxs-lookup"><span data-stu-id="13996-3352">居留證</span></span> 
- <span data-ttu-id="13996-3353">外僑居留證</span><span class="sxs-lookup"><span data-stu-id="13996-3353">外僑居留證</span></span> 
- <span data-ttu-id="13996-3354">台灣地區居留證</span><span class="sxs-lookup"><span data-stu-id="13996-3354">台灣地區居留證</span></span> 

## <a name="thai-population-identification-code"></a><span data-ttu-id="13996-3355">Codice di identificazione della popolazione tailandese</span><span class="sxs-lookup"><span data-stu-id="13996-3355">Thai Population Identification Code</span></span>

### <a name="format"></a><span data-ttu-id="13996-3356">Formato</span><span class="sxs-lookup"><span data-stu-id="13996-3356">Format</span></span>

<span data-ttu-id="13996-3357">13 cifre</span><span class="sxs-lookup"><span data-stu-id="13996-3357">13 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="13996-3358">Modello</span><span class="sxs-lookup"><span data-stu-id="13996-3358">Pattern</span></span>

<span data-ttu-id="13996-3359">13 cifre:</span><span class="sxs-lookup"><span data-stu-id="13996-3359">13 digits:</span></span>
- <span data-ttu-id="13996-3360">La prima cifra non è 0 o 9</span><span class="sxs-lookup"><span data-stu-id="13996-3360">First digit is not 0 or 9</span></span> 
- <span data-ttu-id="13996-3361">12 cifre</span><span class="sxs-lookup"><span data-stu-id="13996-3361">12 digits</span></span>

### <a name="checksum"></a><span data-ttu-id="13996-3362">Checksum</span><span class="sxs-lookup"><span data-stu-id="13996-3362">Checksum</span></span>

<span data-ttu-id="13996-3363">Sì</span><span class="sxs-lookup"><span data-stu-id="13996-3363">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="13996-3364">Definizione</span><span class="sxs-lookup"><span data-stu-id="13996-3364">Definition</span></span>

<span data-ttu-id="13996-3365">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="13996-3365">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="13996-3366">La funzione Func_Thai_Citizen_Id trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="13996-3366">The function Func_Thai_Citizen_Id finds content that matches the pattern.</span></span>
- <span data-ttu-id="13996-3367">Viene trovata una parola chiave da Keyword_Thai_Citizen_Id.</span><span class="sxs-lookup"><span data-stu-id="13996-3367">A keyword from Keyword_Thai_Citizen_Id is found.</span></span>

<span data-ttu-id="13996-3368">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="13996-3368">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="13996-3369">La funzione Func_Thai_Citizen_Id trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="13996-3369">The function Func_Thai_Citizen_Id finds content that matches the pattern.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="13996-3370">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="13996-3370">Keywords</span></span>

#### <a name="keywordthaicitizenid"></a><span data-ttu-id="13996-3371">Keyword_Thai_Citizen_Id</span><span class="sxs-lookup"><span data-stu-id="13996-3371">Keyword_Thai_Citizen_Id</span></span>

- <span data-ttu-id="13996-3372">Numero ID
</span><span class="sxs-lookup"><span data-stu-id="13996-3372">ID Number</span></span>
- <span data-ttu-id="13996-3373">Numero di identificazione</span><span class="sxs-lookup"><span data-stu-id="13996-3373">Identification Number</span></span>
- <span data-ttu-id="13996-3374">บัตรประชาชน</span><span class="sxs-lookup"><span data-stu-id="13996-3374">บัตรประชาชน</span></span>
- <span data-ttu-id="13996-3375">รหัสบัตรประชาชน</span><span class="sxs-lookup"><span data-stu-id="13996-3375">รหัสบัตรประชาชน</span></span>
- <span data-ttu-id="13996-3376">บัตรประชาชน</span><span class="sxs-lookup"><span data-stu-id="13996-3376">บัตรประชาชน</span></span>
- <span data-ttu-id="13996-3377">รหัสบัตรประชาชน</span><span class="sxs-lookup"><span data-stu-id="13996-3377">รหัสบัตรประชาชน</span></span>
  
## <a name="turkish-national-identification-number"></a><span data-ttu-id="13996-3378">Numero di identificazione nazionale turco</span><span class="sxs-lookup"><span data-stu-id="13996-3378">Turkish National Identification Number</span></span>

### <a name="format"></a><span data-ttu-id="13996-3379">Formato</span><span class="sxs-lookup"><span data-stu-id="13996-3379">Format</span></span>

<span data-ttu-id="13996-3380">11 cifre</span><span class="sxs-lookup"><span data-stu-id="13996-3380">11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="13996-3381">Modello</span><span class="sxs-lookup"><span data-stu-id="13996-3381">Pattern</span></span>

<span data-ttu-id="13996-3382">11 cifre</span><span class="sxs-lookup"><span data-stu-id="13996-3382">11 digits</span></span>

### <a name="checksum"></a><span data-ttu-id="13996-3383">Checksum</span><span class="sxs-lookup"><span data-stu-id="13996-3383">Checksum</span></span>

<span data-ttu-id="13996-3384">Sì</span><span class="sxs-lookup"><span data-stu-id="13996-3384">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="13996-3385">Definizione</span><span class="sxs-lookup"><span data-stu-id="13996-3385">Definition</span></span>

<span data-ttu-id="13996-3386">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="13996-3386">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="13996-3387">La funzione Func_Turkish_National_Id trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="13996-3387">The function Func_Turkish_National_Id finds content that matches the pattern.</span></span>
- <span data-ttu-id="13996-3388">Viene trovata una parola chiave da Keyword_Turkish_National_Id.</span><span class="sxs-lookup"><span data-stu-id="13996-3388">A keyword from Keyword_Turkish_National_Id is found.</span></span>

<span data-ttu-id="13996-3389">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="13996-3389">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="13996-3390">La funzione Func_Turkish_National_Id trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="13996-3390">The function Func_Turkish_National_Id finds content that matches the pattern.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="13996-3391">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="13996-3391">Keywords</span></span>

#### <a name="keywordturkishnationalid"></a><span data-ttu-id="13996-3392">Keyword_Turkish_National_Id</span><span class="sxs-lookup"><span data-stu-id="13996-3392">Keyword_Turkish_National_Id</span></span>

- <span data-ttu-id="13996-3393">TC Kimlik No</span><span class="sxs-lookup"><span data-stu-id="13996-3393">TC Kimlik No</span></span>
- <span data-ttu-id="13996-3394">Numarası Kimlik TC</span><span class="sxs-lookup"><span data-stu-id="13996-3394">TC Kimlik numarası</span></span>
- <span data-ttu-id="13996-3395">Vatandaşlık numarası</span><span class="sxs-lookup"><span data-stu-id="13996-3395">Vatandaşlık numarası</span></span>
- <span data-ttu-id="13996-3396">Vatandaşlık No</span><span class="sxs-lookup"><span data-stu-id="13996-3396">Vatandaşlık no</span></span>

## <a name="uk-drivers-license-number"></a><span data-ttu-id="13996-p142">Regno Unito - Numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="13996-p142">U.K. Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="13996-3399">Formato</span><span class="sxs-lookup"><span data-stu-id="13996-3399">Format</span></span>

<span data-ttu-id="13996-3400">Combinazione di 18 lettere e numeri nel formato specificato</span><span class="sxs-lookup"><span data-stu-id="13996-3400">Combination of 18 letters and digits in the specified format</span></span>

### <a name="pattern"></a><span data-ttu-id="13996-3401">Modello</span><span class="sxs-lookup"><span data-stu-id="13996-3401">Pattern</span></span>

<span data-ttu-id="13996-3402">18 lettere e cifre:</span><span class="sxs-lookup"><span data-stu-id="13996-3402">18 letters and digits:</span></span>
- <span data-ttu-id="13996-3403">Cinque lettere (senza distinzione fra maiuscole/minuscole) o la cifra 9 al posto di una lettera</span><span class="sxs-lookup"><span data-stu-id="13996-3403">Five letters (not case sensitive) or the digit "9" in place of a letter</span></span> 
- <span data-ttu-id="13996-3404">Una cifra</span><span class="sxs-lookup"><span data-stu-id="13996-3404">One digit</span></span> 
- <span data-ttu-id="13996-3405">5 cifre nel formato data GGMMA relativo alla data di nascita</span><span class="sxs-lookup"><span data-stu-id="13996-3405">Five digits in the date format DDMMY for date of birth</span></span> 
- <span data-ttu-id="13996-3406">Due lettere (senza distinzione fra maiuscole/minuscole) o la cifra 9 al posto di una lettera</span><span class="sxs-lookup"><span data-stu-id="13996-3406">Two letters (not case sensitive) or the digit "9" in place of a letter</span></span> 
- <span data-ttu-id="13996-3407">Cinque cifre</span><span class="sxs-lookup"><span data-stu-id="13996-3407">Five digits</span></span>

### <a name="checksum"></a><span data-ttu-id="13996-3408">Checksum</span><span class="sxs-lookup"><span data-stu-id="13996-3408">Checksum</span></span>

<span data-ttu-id="13996-3409">Sì</span><span class="sxs-lookup"><span data-stu-id="13996-3409">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="13996-3410">Definizione</span><span class="sxs-lookup"><span data-stu-id="13996-3410">Definition</span></span>

<span data-ttu-id="13996-3411">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="13996-3411">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="13996-3412">La funzione Func_uk_drivers_license restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="13996-3412">The function Func_uk_drivers_license finds content that matches the pattern.</span></span>
- <span data-ttu-id="13996-3413">Viene trovata una parola chiave da Keyword_uk_drivers_license.</span><span class="sxs-lookup"><span data-stu-id="13996-3413">A keyword from Keyword_uk_drivers_license is found.</span></span>
- <span data-ttu-id="13996-3414">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="13996-3414">The checksum passes.</span></span>

```
<!-- U.K. Driver's License Number -->
<Entity id="f93de4be-d94c-40df-a8be-461738047551" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_uk_drivers_license" />
        <Match idRef="Keyword_uk_drivers_license" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="13996-3415">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="13996-3415">Keywords</span></span>

#### <a name="keywordukdriverslicense"></a><span data-ttu-id="13996-3416">Keyword_uk_drivers_license</span><span class="sxs-lookup"><span data-stu-id="13996-3416">Keyword_uk_drivers_license</span></span>

- <span data-ttu-id="13996-3417">DVLA</span><span class="sxs-lookup"><span data-stu-id="13996-3417">DVLA</span></span> 
- <span data-ttu-id="13996-3418">light vans</span><span class="sxs-lookup"><span data-stu-id="13996-3418">light vans</span></span> 
- <span data-ttu-id="13996-3419">quadbikes</span><span class="sxs-lookup"><span data-stu-id="13996-3419">quadbikes</span></span> 
- <span data-ttu-id="13996-3420">motor cars</span><span class="sxs-lookup"><span data-stu-id="13996-3420">motor cars</span></span> 
- <span data-ttu-id="13996-3421">125cc</span><span class="sxs-lookup"><span data-stu-id="13996-3421">125cc</span></span> 
- <span data-ttu-id="13996-3422">sidecar</span><span class="sxs-lookup"><span data-stu-id="13996-3422">sidecar</span></span> 
- <span data-ttu-id="13996-3423">tricicli</span><span class="sxs-lookup"><span data-stu-id="13996-3423">tricycles</span></span> 
- <span data-ttu-id="13996-3424">moto</span><span class="sxs-lookup"><span data-stu-id="13996-3424">motorcycles</span></span> 
- <span data-ttu-id="13996-3425">photocard licence</span><span class="sxs-lookup"><span data-stu-id="13996-3425">photocard licence</span></span> 
- <span data-ttu-id="13996-3426">learner drivers</span><span class="sxs-lookup"><span data-stu-id="13996-3426">learner drivers</span></span> 
- <span data-ttu-id="13996-3427">licence holder</span><span class="sxs-lookup"><span data-stu-id="13996-3427">licence holder</span></span> 
- <span data-ttu-id="13996-3428">licence holders</span><span class="sxs-lookup"><span data-stu-id="13996-3428">licence holders</span></span> 
- <span data-ttu-id="13996-3429">driving licences</span><span class="sxs-lookup"><span data-stu-id="13996-3429">driving licences</span></span> 
- <span data-ttu-id="13996-3430">driving licence</span><span class="sxs-lookup"><span data-stu-id="13996-3430">driving licence</span></span> 
- <span data-ttu-id="13996-3431">dual control car</span><span class="sxs-lookup"><span data-stu-id="13996-3431">dual control car</span></span> 
   
## <a name="uk-electoral-roll-number"></a><span data-ttu-id="13996-p143">Regno Unito - Numero di iscrizione alle liste elettorali</span><span class="sxs-lookup"><span data-stu-id="13996-p143">U.K. Electoral Roll Number</span></span>

### <a name="format"></a><span data-ttu-id="13996-3434">Formato</span><span class="sxs-lookup"><span data-stu-id="13996-3434">Format</span></span>

<span data-ttu-id="13996-3435">Due lettere seguite da 1-4 cifre</span><span class="sxs-lookup"><span data-stu-id="13996-3435">Two letters followed by 1-4 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="13996-3436">Modello</span><span class="sxs-lookup"><span data-stu-id="13996-3436">Pattern</span></span>

<span data-ttu-id="13996-3437">Due lettere (senza distinzione fra maiuscole/minuscole) seguite da 1-4 numeri</span><span class="sxs-lookup"><span data-stu-id="13996-3437">Two letters (not case sensitive) followed by 1-4 numbers</span></span>

### <a name="checksum"></a><span data-ttu-id="13996-3438">Checksum</span><span class="sxs-lookup"><span data-stu-id="13996-3438">Checksum</span></span>

<span data-ttu-id="13996-3439">No</span><span class="sxs-lookup"><span data-stu-id="13996-3439">No</span></span>

### <a name="definition"></a><span data-ttu-id="13996-3440">Definizione</span><span class="sxs-lookup"><span data-stu-id="13996-3440">Definition</span></span>

<span data-ttu-id="13996-3441">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="13996-3441">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="13996-3442">L'espressione regolare Regex_uk_electoral restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="13996-3442">The regular expression Regex_uk_electoral finds content that matches the pattern.</span></span>
- <span data-ttu-id="13996-3443">Viene trovata una parola chiave da Keyword_uk_electoral.</span><span class="sxs-lookup"><span data-stu-id="13996-3443">A keyword from Keyword_uk_electoral is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="13996-3444">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="13996-3444">Keywords</span></span>

#### <a name="keywordukelectoral"></a><span data-ttu-id="13996-3445">Keyword_uk_electoral</span><span class="sxs-lookup"><span data-stu-id="13996-3445">Keyword_uk_electoral</span></span>

- <span data-ttu-id="13996-3446">council nomination</span><span class="sxs-lookup"><span data-stu-id="13996-3446">council nomination</span></span> 
- <span data-ttu-id="13996-3447">nomination form</span><span class="sxs-lookup"><span data-stu-id="13996-3447">nomination form</span></span> 
- <span data-ttu-id="13996-3448">electoral register</span><span class="sxs-lookup"><span data-stu-id="13996-3448">electoral register</span></span> 
- <span data-ttu-id="13996-3449">electoral roll</span><span class="sxs-lookup"><span data-stu-id="13996-3449">electoral roll</span></span>

   
## <a name="uk-national-health-service-number"></a><span data-ttu-id="13996-p144">Regno Unito - Codice del servizio sanitario nazionale</span><span class="sxs-lookup"><span data-stu-id="13996-p144">U.K. National Health Service Number</span></span>

### <a name="format"></a><span data-ttu-id="13996-3452">Formato</span><span class="sxs-lookup"><span data-stu-id="13996-3452">Format</span></span>

<span data-ttu-id="13996-3453">10-17 cifre separate da spazi</span><span class="sxs-lookup"><span data-stu-id="13996-3453">10-17 digits separated by spaces</span></span>

### <a name="pattern"></a><span data-ttu-id="13996-3454">Modello</span><span class="sxs-lookup"><span data-stu-id="13996-3454">Pattern</span></span>

<span data-ttu-id="13996-3455">10-17 cifre:</span><span class="sxs-lookup"><span data-stu-id="13996-3455">10-17 digits:</span></span>
- <span data-ttu-id="13996-3456">3 o 10 cifre</span><span class="sxs-lookup"><span data-stu-id="13996-3456">Either 3 or 10 digits</span></span> 
- <span data-ttu-id="13996-3457">Uno spazio</span><span class="sxs-lookup"><span data-stu-id="13996-3457">A space</span></span> 
- <span data-ttu-id="13996-3458">Tre cifre</span><span class="sxs-lookup"><span data-stu-id="13996-3458">Three digits</span></span> 
- <span data-ttu-id="13996-3459">Uno spazio</span><span class="sxs-lookup"><span data-stu-id="13996-3459">A space</span></span> 
- <span data-ttu-id="13996-3460">Quattro cifre</span><span class="sxs-lookup"><span data-stu-id="13996-3460">Four digits</span></span>

### <a name="checksum"></a><span data-ttu-id="13996-3461">Checksum</span><span class="sxs-lookup"><span data-stu-id="13996-3461">Checksum</span></span>

<span data-ttu-id="13996-3462">Sì</span><span class="sxs-lookup"><span data-stu-id="13996-3462">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="13996-3463">Definizione</span><span class="sxs-lookup"><span data-stu-id="13996-3463">Definition</span></span>

<span data-ttu-id="13996-3464">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="13996-3464">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="13996-3465">La funzione Func_uk_nhs_number restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="13996-3465">The function Func_uk_nhs_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="13996-3466">Si verifica una delle situazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="13996-3466">One of the following is true:</span></span>
    - <span data-ttu-id="13996-3467">Viene trovata una parola chiave da Keyword_uk_nhs_number.</span><span class="sxs-lookup"><span data-stu-id="13996-3467">A keyword from Keyword_uk_nhs_number is found.</span></span>
    - <span data-ttu-id="13996-3468">Viene trovata una parola chiave da Keyword_uk_nhs_number1.</span><span class="sxs-lookup"><span data-stu-id="13996-3468">A keyword from Keyword_uk_nhs_number1 is found.</span></span>
    - <span data-ttu-id="13996-3469">Viene trovata una parola chiave da Keyword_uk_nhs_number_dob.</span><span class="sxs-lookup"><span data-stu-id="13996-3469">A keyword from Keyword_uk_nhs_number_dob is found.</span></span>
- <span data-ttu-id="13996-3470">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="13996-3470">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="13996-3471">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="13996-3471">Keywords</span></span>
   
#### <a name="keyworduknhsnumber"></a><span data-ttu-id="13996-3472">Keyword_uk_nhs_number</span><span class="sxs-lookup"><span data-stu-id="13996-3472">Keyword_uk_nhs_number</span></span>

- <span data-ttu-id="13996-3473">national health service</span><span class="sxs-lookup"><span data-stu-id="13996-3473">national health service</span></span> 
- <span data-ttu-id="13996-3474">NHS</span><span class="sxs-lookup"><span data-stu-id="13996-3474">nhs</span></span> 
- <span data-ttu-id="13996-3475">health services authority</span><span class="sxs-lookup"><span data-stu-id="13996-3475">health services authority</span></span> 
- <span data-ttu-id="13996-3476">health authority</span><span class="sxs-lookup"><span data-stu-id="13996-3476">health authority</span></span>

#### <a name="keyworduknhsnumber1"></a><span data-ttu-id="13996-3477">Keyword_uk_nhs_number1</span><span class="sxs-lookup"><span data-stu-id="13996-3477">Keyword_uk_nhs_number1</span></span>

- <span data-ttu-id="13996-3478">patient id</span><span class="sxs-lookup"><span data-stu-id="13996-3478">patient id</span></span> 
- <span data-ttu-id="13996-3479">patient identification</span><span class="sxs-lookup"><span data-stu-id="13996-3479">patient identification</span></span> 
- <span data-ttu-id="13996-3480">patient no</span><span class="sxs-lookup"><span data-stu-id="13996-3480">patient no</span></span> 
- <span data-ttu-id="13996-3481">patient number</span><span class="sxs-lookup"><span data-stu-id="13996-3481">patient number</span></span>

#### <a name="keyworduknhsnumberdob"></a><span data-ttu-id="13996-3482">Keyword_uk_nhs_number_dob</span><span class="sxs-lookup"><span data-stu-id="13996-3482">Keyword_uk_nhs_number_dob</span></span>

- <span data-ttu-id="13996-3483">GP</span><span class="sxs-lookup"><span data-stu-id="13996-3483">GP</span></span> 
- <span data-ttu-id="13996-3484">DOB</span><span class="sxs-lookup"><span data-stu-id="13996-3484">DOB</span></span> 
- <span data-ttu-id="13996-3485">D. O. B</span><span class="sxs-lookup"><span data-stu-id="13996-3485">D.O.B</span></span> 
- <span data-ttu-id="13996-3486">Date of Birth</span><span class="sxs-lookup"><span data-stu-id="13996-3486">Date of Birth</span></span> 
- <span data-ttu-id="13996-3487">Birth Date</span><span class="sxs-lookup"><span data-stu-id="13996-3487">Birth Date</span></span> 
   
## <a name="uk-national-insurance-number-nino"></a><span data-ttu-id="13996-p145">Regno Unito - Numero di assicurazione nazionale (NINO)</span><span class="sxs-lookup"><span data-stu-id="13996-p145">U.K. National Insurance Number (NINO)</span></span>

### <a name="format"></a><span data-ttu-id="13996-3490">Formato</span><span class="sxs-lookup"><span data-stu-id="13996-3490">Format</span></span>

<span data-ttu-id="13996-3491">7 caratteri o 9 caratteri separati da spazi o trattini</span><span class="sxs-lookup"><span data-stu-id="13996-3491">7 characters or 9 characters separated by spaces or dashes</span></span>

### <a name="pattern"></a><span data-ttu-id="13996-3492">Modello</span><span class="sxs-lookup"><span data-stu-id="13996-3492">Pattern</span></span>

<span data-ttu-id="13996-3493">Due modelli possibili:</span><span class="sxs-lookup"><span data-stu-id="13996-3493">Two possible patterns:</span></span>

- <span data-ttu-id="13996-3494">Due lettere (NINOs valido utilizza solo alcuni caratteri in questo prefisso, che questo modello convalida; senza distinzione tra maiuscole e minuscole)</span><span class="sxs-lookup"><span data-stu-id="13996-3494">Two letters (valid NINOs use only certain characters in this prefix, which this pattern validates; not case sensitive)</span></span>
- <span data-ttu-id="13996-3495">Sei cifre</span><span class="sxs-lookup"><span data-stu-id="13996-3495">Six digits</span></span>
- <span data-ttu-id="13996-3496">' A ',' B ',' c'o ' d'(come il prefisso, solo alcuni caratteri sono consentiti nel suffisso, senza distinzione tra maiuscole e minuscole)</span><span class="sxs-lookup"><span data-stu-id="13996-3496">Either 'A', 'B', 'C', or 'D' (like the prefix, only certain characters are allowed in the suffix; not case sensitive)</span></span>

<span data-ttu-id="13996-3497">O</span><span class="sxs-lookup"><span data-stu-id="13996-3497">OR</span></span>

- <span data-ttu-id="13996-3498">Due lettere</span><span class="sxs-lookup"><span data-stu-id="13996-3498">Two letters</span></span>
- <span data-ttu-id="13996-3499">Uno spazio o un trattino</span><span class="sxs-lookup"><span data-stu-id="13996-3499">A space or dash</span></span>
- <span data-ttu-id="13996-3500">Due cifre</span><span class="sxs-lookup"><span data-stu-id="13996-3500">Two digits</span></span>
- <span data-ttu-id="13996-3501">Uno spazio o un trattino</span><span class="sxs-lookup"><span data-stu-id="13996-3501">A space or dash</span></span>
- <span data-ttu-id="13996-3502">Due cifre</span><span class="sxs-lookup"><span data-stu-id="13996-3502">Two digits</span></span>
- <span data-ttu-id="13996-3503">Uno spazio o un trattino</span><span class="sxs-lookup"><span data-stu-id="13996-3503">A space or dash</span></span>
- <span data-ttu-id="13996-3504">Due cifre</span><span class="sxs-lookup"><span data-stu-id="13996-3504">Two digits</span></span>
- <span data-ttu-id="13996-3505">Uno spazio o un trattino</span><span class="sxs-lookup"><span data-stu-id="13996-3505">A space or dash</span></span>
- <span data-ttu-id="13996-3506">' A ',' B ',' c'o ' d'</span><span class="sxs-lookup"><span data-stu-id="13996-3506">Either 'A', 'B', 'C', or 'D'</span></span>

### <a name="checksum"></a><span data-ttu-id="13996-3507">Checksum</span><span class="sxs-lookup"><span data-stu-id="13996-3507">Checksum</span></span>

<span data-ttu-id="13996-3508">No</span><span class="sxs-lookup"><span data-stu-id="13996-3508">No</span></span>

### <a name="definition"></a><span data-ttu-id="13996-3509">Definizione</span><span class="sxs-lookup"><span data-stu-id="13996-3509">Definition</span></span>

<span data-ttu-id="13996-3510">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="13996-3510">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="13996-3511">La funzione Func_uk_nino restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="13996-3511">The function Func_uk_nino finds content that matches the pattern.</span></span>
- <span data-ttu-id="13996-3512">Viene trovata una parola chiave da Keyword_uk_nino.</span><span class="sxs-lookup"><span data-stu-id="13996-3512">A keyword from Keyword_uk_nino is found.</span></span>

<span data-ttu-id="13996-3513">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="13996-3513">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="13996-3514">La funzione Func_uk_nino restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="13996-3514">The function Func_uk_nino finds content that matches the pattern.</span></span>
- <span data-ttu-id="13996-3515">Non vengono trovate parole chiave da Keyword_uk_nino.</span><span class="sxs-lookup"><span data-stu-id="13996-3515">No keyword from Keyword_uk_nino is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="13996-3516">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="13996-3516">Keywords</span></span>

#### <a name="keyworduknino"></a><span data-ttu-id="13996-3517">Keyword_uk_nino</span><span class="sxs-lookup"><span data-stu-id="13996-3517">Keyword_uk_nino</span></span>

- <span data-ttu-id="13996-3518">national insurance number</span><span class="sxs-lookup"><span data-stu-id="13996-3518">national insurance number</span></span> 
- <span data-ttu-id="13996-3519">national insurance contributions</span><span class="sxs-lookup"><span data-stu-id="13996-3519">national insurance contributions</span></span> 
- <span data-ttu-id="13996-3520">protection act</span><span class="sxs-lookup"><span data-stu-id="13996-3520">protection act</span></span> 
- <span data-ttu-id="13996-3521">Insurance</span><span class="sxs-lookup"><span data-stu-id="13996-3521">insurance</span></span> 
- <span data-ttu-id="13996-3522">social security number</span><span class="sxs-lookup"><span data-stu-id="13996-3522">social security number</span></span> 
- <span data-ttu-id="13996-3523">insurance application</span><span class="sxs-lookup"><span data-stu-id="13996-3523">insurance application</span></span> 
- <span data-ttu-id="13996-3524">medical application</span><span class="sxs-lookup"><span data-stu-id="13996-3524">medical application</span></span> 
- <span data-ttu-id="13996-3525">social insurance</span><span class="sxs-lookup"><span data-stu-id="13996-3525">social insurance</span></span> 
- <span data-ttu-id="13996-3526">medical attention</span><span class="sxs-lookup"><span data-stu-id="13996-3526">medical attention</span></span> 
- <span data-ttu-id="13996-3527">social security</span><span class="sxs-lookup"><span data-stu-id="13996-3527">social security</span></span> 
- <span data-ttu-id="13996-3528">great britain</span><span class="sxs-lookup"><span data-stu-id="13996-3528">great britain</span></span> 
- <span data-ttu-id="13996-3529">Insurance</span><span class="sxs-lookup"><span data-stu-id="13996-3529">insurance</span></span>    
   
## <a name="us--uk-passport-number"></a><span data-ttu-id="13996-p146">Stati Uniti/Regno Unito - Numero di passaporto</span><span class="sxs-lookup"><span data-stu-id="13996-p146">U.S. / U.K. Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="13996-3532">Formato</span><span class="sxs-lookup"><span data-stu-id="13996-3532">Format</span></span>

<span data-ttu-id="13996-3533">9 cifre</span><span class="sxs-lookup"><span data-stu-id="13996-3533">Nine digits</span></span>

### <a name="pattern"></a><span data-ttu-id="13996-3534">Modello</span><span class="sxs-lookup"><span data-stu-id="13996-3534">Pattern</span></span>

<span data-ttu-id="13996-3535">9 cifre consecutive</span><span class="sxs-lookup"><span data-stu-id="13996-3535">Nine consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="13996-3536">Checksum</span><span class="sxs-lookup"><span data-stu-id="13996-3536">Checksum</span></span>

<span data-ttu-id="13996-3537">No</span><span class="sxs-lookup"><span data-stu-id="13996-3537">No</span></span>

### <a name="definition"></a><span data-ttu-id="13996-3538">Definizione</span><span class="sxs-lookup"><span data-stu-id="13996-3538">Definition</span></span>

<span data-ttu-id="13996-3539">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="13996-3539">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="13996-3540">La funzione Func_usa_uk_passport restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="13996-3540">The function Func_usa_uk_passport finds content that matches the pattern.</span></span>
- <span data-ttu-id="13996-3541">Viene trovata una parola chiave da Keyword_passport.</span><span class="sxs-lookup"><span data-stu-id="13996-3541">A keyword from Keyword_passport is found.</span></span>

```
<Entity id="178ec42a-18b4-47cc-85c7-d62c92fd67f8" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_usa_uk_passport" />
        <Match idRef="Keyword_passport" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="13996-3542">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="13996-3542">Keywords</span></span>

#### <a name="keywordpassport"></a><span data-ttu-id="13996-3543">Keyword_passport</span><span class="sxs-lookup"><span data-stu-id="13996-3543">Keyword_passport</span></span>

- <span data-ttu-id="13996-3544">Passport Number</span><span class="sxs-lookup"><span data-stu-id="13996-3544">Passport Number</span></span> 
- <span data-ttu-id="13996-3545">Passport No</span><span class="sxs-lookup"><span data-stu-id="13996-3545">Passport No</span></span> 
- <span data-ttu-id="13996-3546">Passport#</span><span class="sxs-lookup"><span data-stu-id="13996-3546">Passport #</span></span> 
- <span data-ttu-id="13996-3547">Passaporto</span><span class="sxs-lookup"><span data-stu-id="13996-3547">Passport#</span></span> 
- <span data-ttu-id="13996-3548">PassportID</span><span class="sxs-lookup"><span data-stu-id="13996-3548">PassportID</span></span> 
- <span data-ttu-id="13996-3549">Passportno</span><span class="sxs-lookup"><span data-stu-id="13996-3549">Passportno</span></span> 
- <span data-ttu-id="13996-3550">passportnumber</span><span class="sxs-lookup"><span data-stu-id="13996-3550">passportnumber</span></span> 
- <span data-ttu-id="13996-3551">パスポート</span><span class="sxs-lookup"><span data-stu-id="13996-3551">パスポート</span></span> 
- <span data-ttu-id="13996-3552">パスポート番号</span><span class="sxs-lookup"><span data-stu-id="13996-3552">パスポート番号</span></span> 
- <span data-ttu-id="13996-3553">パスポートのNum</span><span class="sxs-lookup"><span data-stu-id="13996-3553">パスポートのNum</span></span> 
- <span data-ttu-id="13996-3554">パスポート #</span><span class="sxs-lookup"><span data-stu-id="13996-3554">パスポート＃</span></span> 
- <span data-ttu-id="13996-3555">Numéro de passeport</span><span class="sxs-lookup"><span data-stu-id="13996-3555">Numéro de passeport</span></span> 
- <span data-ttu-id="13996-3556">Passeport n °</span><span class="sxs-lookup"><span data-stu-id="13996-3556">Passeport n °</span></span> 
- <span data-ttu-id="13996-3557">Passeport Non</span><span class="sxs-lookup"><span data-stu-id="13996-3557">Passeport Non</span></span> 
- <span data-ttu-id="13996-3558">Passeport#</span><span class="sxs-lookup"><span data-stu-id="13996-3558">Passeport #</span></span> 
- <span data-ttu-id="13996-3559">Passeport</span><span class="sxs-lookup"><span data-stu-id="13996-3559">Passeport#</span></span> 
- <span data-ttu-id="13996-3560">PasseportNon</span><span class="sxs-lookup"><span data-stu-id="13996-3560">PasseportNon</span></span> 
- <span data-ttu-id="13996-3561">Passeportn °</span><span class="sxs-lookup"><span data-stu-id="13996-3561">Passeportn °</span></span> 
   
## <a name="us-bank-account-number"></a><span data-ttu-id="13996-3562">Stati Uniti - Numero di conto bancario</span><span class="sxs-lookup"><span data-stu-id="13996-3562">U.S. Bank Account Number</span></span>

### <a name="format"></a><span data-ttu-id="13996-3563">Formato</span><span class="sxs-lookup"><span data-stu-id="13996-3563">Format</span></span>

<span data-ttu-id="13996-3564">8-17 cifre</span><span class="sxs-lookup"><span data-stu-id="13996-3564">8-17 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="13996-3565">Modello</span><span class="sxs-lookup"><span data-stu-id="13996-3565">Pattern</span></span>

<span data-ttu-id="13996-3566">8-17 cifre consecutive</span><span class="sxs-lookup"><span data-stu-id="13996-3566">8-17 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="13996-3567">Checksum</span><span class="sxs-lookup"><span data-stu-id="13996-3567">Checksum</span></span>

<span data-ttu-id="13996-3568">No</span><span class="sxs-lookup"><span data-stu-id="13996-3568">No</span></span>

### <a name="definition"></a><span data-ttu-id="13996-3569">Definizione</span><span class="sxs-lookup"><span data-stu-id="13996-3569">Definition</span></span>

<span data-ttu-id="13996-3570">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="13996-3570">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="13996-3571">L'espressione regolare Regex_usa_bank_account_number restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="13996-3571">The regular expression Regex_usa_bank_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="13996-3572">Viene trovata una parola chiave da Keyword_usa_Bank_Account.</span><span class="sxs-lookup"><span data-stu-id="13996-3572">A keyword from Keyword_usa_Bank_Account is found.</span></span>

```
<!-- U.S. Bank Account Number -->
<Entity id="a2ce32a8-f935-4bb6-8e96-2a5157672e2c" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_usa_bank_account_number" />
        <Match idRef="Keyword_usa_Bank_Account" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="13996-3573">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="13996-3573">Keywords</span></span>

#### <a name="keywordusabankaccount"></a><span data-ttu-id="13996-3574">Keyword_usa_Bank_Account</span><span class="sxs-lookup"><span data-stu-id="13996-3574">Keyword_usa_Bank_Account</span></span>

- <span data-ttu-id="13996-3575">Checking Account Number</span><span class="sxs-lookup"><span data-stu-id="13996-3575">Checking Account Number</span></span> 
- <span data-ttu-id="13996-3576">Checking Account</span><span class="sxs-lookup"><span data-stu-id="13996-3576">Checking Account</span></span> 
- <span data-ttu-id="13996-3577">Checking Account #</span><span class="sxs-lookup"><span data-stu-id="13996-3577">Checking Account #</span></span> 
- <span data-ttu-id="13996-3578">Checking Acct Number</span><span class="sxs-lookup"><span data-stu-id="13996-3578">Checking Acct Number</span></span> 
- <span data-ttu-id="13996-3579">Checking Acct #</span><span class="sxs-lookup"><span data-stu-id="13996-3579">Checking Acct #</span></span> 
- <span data-ttu-id="13996-3580">Checking Acct No.</span><span class="sxs-lookup"><span data-stu-id="13996-3580">Checking Acct No.</span></span> 
- <span data-ttu-id="13996-3581">Checking Account No.</span><span class="sxs-lookup"><span data-stu-id="13996-3581">Checking Account No.</span></span> 
- <span data-ttu-id="13996-3582">Bank Account Number</span><span class="sxs-lookup"><span data-stu-id="13996-3582">Bank Account Number</span></span> 
- <span data-ttu-id="13996-3583">Bank Account #</span><span class="sxs-lookup"><span data-stu-id="13996-3583">Bank Account #</span></span> 
- <span data-ttu-id="13996-3584">Bank Acct Number</span><span class="sxs-lookup"><span data-stu-id="13996-3584">Bank Acct Number</span></span> 
- <span data-ttu-id="13996-3585">Bank Acct #</span><span class="sxs-lookup"><span data-stu-id="13996-3585">Bank Acct #</span></span> 
- <span data-ttu-id="13996-3586">Bank Acct No.</span><span class="sxs-lookup"><span data-stu-id="13996-3586">Bank Acct No.</span></span> 
- <span data-ttu-id="13996-3587">Bank Account No.</span><span class="sxs-lookup"><span data-stu-id="13996-3587">Bank Account No.</span></span> 
- <span data-ttu-id="13996-3588">Savings Account Number</span><span class="sxs-lookup"><span data-stu-id="13996-3588">Savings Account Number</span></span> 
- <span data-ttu-id="13996-3589">Savings Account.</span><span class="sxs-lookup"><span data-stu-id="13996-3589">Savings Account.</span></span> 
- <span data-ttu-id="13996-3590">Savings Account #</span><span class="sxs-lookup"><span data-stu-id="13996-3590">Savings Account #</span></span> 
- <span data-ttu-id="13996-3591">Savings Acct Number</span><span class="sxs-lookup"><span data-stu-id="13996-3591">Savings Acct Number</span></span> 
- <span data-ttu-id="13996-3592">Savings Acct #</span><span class="sxs-lookup"><span data-stu-id="13996-3592">Savings Acct #</span></span> 
- <span data-ttu-id="13996-3593">Savings Acct No.</span><span class="sxs-lookup"><span data-stu-id="13996-3593">Savings Acct No.</span></span> 
- <span data-ttu-id="13996-3594">Savings Account No.</span><span class="sxs-lookup"><span data-stu-id="13996-3594">Savings Account No.</span></span> 
- <span data-ttu-id="13996-3595">Debit Account Number</span><span class="sxs-lookup"><span data-stu-id="13996-3595">Debit Account Number</span></span> 
- <span data-ttu-id="13996-3596">Debit Account</span><span class="sxs-lookup"><span data-stu-id="13996-3596">Debit Account</span></span> 
- <span data-ttu-id="13996-3597">Debit Account #</span><span class="sxs-lookup"><span data-stu-id="13996-3597">Debit Account #</span></span> 
- <span data-ttu-id="13996-3598">Debit Acct Number</span><span class="sxs-lookup"><span data-stu-id="13996-3598">Debit Acct Number</span></span> 
- <span data-ttu-id="13996-3599">Debit Acct #</span><span class="sxs-lookup"><span data-stu-id="13996-3599">Debit Acct #</span></span> 
- <span data-ttu-id="13996-3600">Debit Acct No.</span><span class="sxs-lookup"><span data-stu-id="13996-3600">Debit Acct No.</span></span> 
- <span data-ttu-id="13996-3601">Debit Account No.</span><span class="sxs-lookup"><span data-stu-id="13996-3601">Debit Account No.</span></span> 
   
## <a name="us-drivers-license-number"></a><span data-ttu-id="13996-3602">Stati Uniti - Numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="13996-3602">U.S. Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="13996-3603">Formato</span><span class="sxs-lookup"><span data-stu-id="13996-3603">Format</span></span>

<span data-ttu-id="13996-3604">Varia in base allo stato</span><span class="sxs-lookup"><span data-stu-id="13996-3604">Depends on the state</span></span>

### <a name="pattern"></a><span data-ttu-id="13996-3605">Modello</span><span class="sxs-lookup"><span data-stu-id="13996-3605">Pattern</span></span>

<span data-ttu-id="13996-3606">Varia in base allo stato. Ad esempio, per New York:</span><span class="sxs-lookup"><span data-stu-id="13996-3606">Depends on the state -- for example, New York:</span></span>
- <span data-ttu-id="13996-3607">Nove cifre formattate come ddd ddd ddd corrisponderanno.</span><span class="sxs-lookup"><span data-stu-id="13996-3607">Nine digits formatted like ddd ddd ddd will match.</span></span>
- <span data-ttu-id="13996-3608">Nove cifre come ddddddddd non corrispondono.</span><span class="sxs-lookup"><span data-stu-id="13996-3608">Nine digits like ddddddddd will not match.</span></span>

### <a name="checksum"></a><span data-ttu-id="13996-3609">Checksum</span><span class="sxs-lookup"><span data-stu-id="13996-3609">Checksum</span></span>

<span data-ttu-id="13996-3610">No</span><span class="sxs-lookup"><span data-stu-id="13996-3610">No</span></span>

### <a name="definition"></a><span data-ttu-id="13996-3611">Definizione</span><span class="sxs-lookup"><span data-stu-id="13996-3611">Definition</span></span>

<span data-ttu-id="13996-3612">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="13996-3612">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="13996-3613">La funzione Func_new_york_drivers_license_number restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="13996-3613">The function Func_new_york_drivers_license_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="13996-3614">Viene trovata una parola chiave da Keyword_[state_name]_drivers_license_name.</span><span class="sxs-lookup"><span data-stu-id="13996-3614">A keyword from Keyword_[state_name]_drivers_license_name is found.</span></span>
- <span data-ttu-id="13996-3615">Viene trovata una parola chiave da Keyword_us_drivers_license.</span><span class="sxs-lookup"><span data-stu-id="13996-3615">A keyword from Keyword_us_drivers_license is found.</span></span>

<span data-ttu-id="13996-3616">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 65%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="13996-3616">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="13996-3617">La funzione Func_new_york_drivers_license_number restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="13996-3617">The function Func_new_york_drivers_license_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="13996-3618">Viene trovata una parola chiave da Keyword_[state_name]_drivers_license_name.</span><span class="sxs-lookup"><span data-stu-id="13996-3618">A keyword from Keyword_[state_name]_drivers_license_name is found.</span></span>
- <span data-ttu-id="13996-3619">Viene trovata una parola chiave da Keyword_us_drivers_license_abbreviations.</span><span class="sxs-lookup"><span data-stu-id="13996-3619">A keyword from Keyword_us_drivers_license_abbreviations is found.</span></span>
- <span data-ttu-id="13996-3620">Non vengono trovate parole chiave da Keyword_us_drivers_license.</span><span class="sxs-lookup"><span data-stu-id="13996-3620">No keyword from Keyword_us_drivers_license is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="13996-3621">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="13996-3621">Keywords</span></span>

#### <a name="keywordusdriverslicenseabbreviations"></a><span data-ttu-id="13996-3622">Keyword_us_drivers_license_abbreviations</span><span class="sxs-lookup"><span data-stu-id="13996-3622">Keyword_us_drivers_license_abbreviations</span></span>

- <span data-ttu-id="13996-3623">DL</span><span class="sxs-lookup"><span data-stu-id="13996-3623">DL</span></span> 
- <span data-ttu-id="13996-3624">DLS</span><span class="sxs-lookup"><span data-stu-id="13996-3624">DLS</span></span> 
- <span data-ttu-id="13996-3625">CDL</span><span class="sxs-lookup"><span data-stu-id="13996-3625">CDL</span></span> 
- <span data-ttu-id="13996-3626">CDLS</span><span class="sxs-lookup"><span data-stu-id="13996-3626">CDLS</span></span> 
- <span data-ttu-id="13996-3627">ID</span><span class="sxs-lookup"><span data-stu-id="13996-3627">ID</span></span> 
- <span data-ttu-id="13996-3628">ID</span><span class="sxs-lookup"><span data-stu-id="13996-3628">IDs</span></span> 
- <span data-ttu-id="13996-3629">DL</span><span class="sxs-lookup"><span data-stu-id="13996-3629">DL#</span></span> 
- <span data-ttu-id="13996-3630">DLS</span><span class="sxs-lookup"><span data-stu-id="13996-3630">DLS#</span></span> 
- <span data-ttu-id="13996-3631">CDL</span><span class="sxs-lookup"><span data-stu-id="13996-3631">CDL#</span></span> 
- <span data-ttu-id="13996-3632">CDLS</span><span class="sxs-lookup"><span data-stu-id="13996-3632">CDLS#</span></span> 
- <span data-ttu-id="13996-3633">ID</span><span class="sxs-lookup"><span data-stu-id="13996-3633">ID#</span></span>
- <span data-ttu-id="13996-3634">ID</span><span class="sxs-lookup"><span data-stu-id="13996-3634">IDs#</span></span> 
- <span data-ttu-id="13996-3635">ID number</span><span class="sxs-lookup"><span data-stu-id="13996-3635">ID number</span></span> 
- <span data-ttu-id="13996-3636">ID numbers</span><span class="sxs-lookup"><span data-stu-id="13996-3636">ID numbers</span></span> 
- <span data-ttu-id="13996-3637">DRIVER'LIC</span><span class="sxs-lookup"><span data-stu-id="13996-3637">LIC</span></span> 
- <span data-ttu-id="13996-3638">DRIVER'LIC</span><span class="sxs-lookup"><span data-stu-id="13996-3638">LIC#</span></span> 

#### <a name="keywordusdriverslicense"></a><span data-ttu-id="13996-3639">Keyword_us_drivers_license</span><span class="sxs-lookup"><span data-stu-id="13996-3639">Keyword_us_drivers_license</span></span>

- <span data-ttu-id="13996-3640">DriverLic</span><span class="sxs-lookup"><span data-stu-id="13996-3640">DriverLic</span></span> 
- <span data-ttu-id="13996-3641">DriverLics</span><span class="sxs-lookup"><span data-stu-id="13996-3641">DriverLics</span></span> 
- <span data-ttu-id="13996-3642">DriverLicense</span><span class="sxs-lookup"><span data-stu-id="13996-3642">DriverLicense</span></span> 
- <span data-ttu-id="13996-3643">DriverLicenses</span><span class="sxs-lookup"><span data-stu-id="13996-3643">DriverLicenses</span></span> 
- <span data-ttu-id="13996-3644">Driver Lic</span><span class="sxs-lookup"><span data-stu-id="13996-3644">Driver Lic</span></span> 
- <span data-ttu-id="13996-3645">Driver Lics</span><span class="sxs-lookup"><span data-stu-id="13996-3645">Driver Lics</span></span> 
- <span data-ttu-id="13996-3646">Driver License</span><span class="sxs-lookup"><span data-stu-id="13996-3646">Driver License</span></span> 
- <span data-ttu-id="13996-3647">Driver Licenses</span><span class="sxs-lookup"><span data-stu-id="13996-3647">Driver Licenses</span></span> 
- <span data-ttu-id="13996-3648">DriversLic</span><span class="sxs-lookup"><span data-stu-id="13996-3648">DriversLic</span></span> 
- <span data-ttu-id="13996-3649">DriversLics</span><span class="sxs-lookup"><span data-stu-id="13996-3649">DriversLics</span></span> 
- <span data-ttu-id="13996-3650">DriversLicense</span><span class="sxs-lookup"><span data-stu-id="13996-3650">DriversLicense</span></span> 
- <span data-ttu-id="13996-3651">DriversLicenses</span><span class="sxs-lookup"><span data-stu-id="13996-3651">DriversLicenses</span></span> 
- <span data-ttu-id="13996-3652">Drivers Lic</span><span class="sxs-lookup"><span data-stu-id="13996-3652">Drivers Lic</span></span> 
- <span data-ttu-id="13996-3653">Drivers Lics</span><span class="sxs-lookup"><span data-stu-id="13996-3653">Drivers Lics</span></span> 
- <span data-ttu-id="13996-3654">Drivers License</span><span class="sxs-lookup"><span data-stu-id="13996-3654">Drivers License</span></span> 
- <span data-ttu-id="13996-3655">Drivers Licenses</span><span class="sxs-lookup"><span data-stu-id="13996-3655">Drivers Licenses</span></span> 
- <span data-ttu-id="13996-3656">Driver'Lic</span><span class="sxs-lookup"><span data-stu-id="13996-3656">Driver'Lic</span></span> 
- <span data-ttu-id="13996-3657">Driver ' LiCS</span><span class="sxs-lookup"><span data-stu-id="13996-3657">Driver'Lics</span></span> 
- <span data-ttu-id="13996-3658">Driver ' License</span><span class="sxs-lookup"><span data-stu-id="13996-3658">Driver'License</span></span> 
- <span data-ttu-id="13996-3659">Driver ' licenses</span><span class="sxs-lookup"><span data-stu-id="13996-3659">Driver'Licenses</span></span> 
- <span data-ttu-id="13996-3660">Driver'Lic</span><span class="sxs-lookup"><span data-stu-id="13996-3660">Driver' Lic</span></span> 
- <span data-ttu-id="13996-3661">Driver' Lics</span><span class="sxs-lookup"><span data-stu-id="13996-3661">Driver' Lics</span></span> 
- <span data-ttu-id="13996-3662">Driver' License</span><span class="sxs-lookup"><span data-stu-id="13996-3662">Driver' License</span></span> 
- <span data-ttu-id="13996-3663">Driver' Licenses</span><span class="sxs-lookup"><span data-stu-id="13996-3663">Driver' Licenses</span></span>
- <span data-ttu-id="13996-3664">Driver'sLic</span><span class="sxs-lookup"><span data-stu-id="13996-3664">Driver'sLic</span></span> 
- <span data-ttu-id="13996-3665">Driver'sLics</span><span class="sxs-lookup"><span data-stu-id="13996-3665">Driver'sLics</span></span> 
- <span data-ttu-id="13996-3666">Secondola</span><span class="sxs-lookup"><span data-stu-id="13996-3666">Driver'sLicense</span></span> 
- <span data-ttu-id="13996-3667">Driver'sLicenses</span><span class="sxs-lookup"><span data-stu-id="13996-3667">Driver'sLicenses</span></span> 
- <span data-ttu-id="13996-3668">Driver's Lic</span><span class="sxs-lookup"><span data-stu-id="13996-3668">Driver's Lic</span></span> 
- <span data-ttu-id="13996-3669">Driver's Lics</span><span class="sxs-lookup"><span data-stu-id="13996-3669">Driver's Lics</span></span> 
- <span data-ttu-id="13996-3670">Driver's License</span><span class="sxs-lookup"><span data-stu-id="13996-3670">Driver's License</span></span> 
- <span data-ttu-id="13996-3671">Driver's Licenses</span><span class="sxs-lookup"><span data-stu-id="13996-3671">Driver's Licenses</span></span> 
- <span data-ttu-id="13996-3672">identification number</span><span class="sxs-lookup"><span data-stu-id="13996-3672">identification number</span></span> 
- <span data-ttu-id="13996-3673">identification numbers</span><span class="sxs-lookup"><span data-stu-id="13996-3673">identification numbers</span></span> 
- <span data-ttu-id="13996-3674">identification#</span><span class="sxs-lookup"><span data-stu-id="13996-3674">identification #</span></span> 
- <span data-ttu-id="13996-3675">id card</span><span class="sxs-lookup"><span data-stu-id="13996-3675">id card</span></span> 
- <span data-ttu-id="13996-3676">id cards</span><span class="sxs-lookup"><span data-stu-id="13996-3676">id cards</span></span> 
- <span data-ttu-id="13996-3677">identification card</span><span class="sxs-lookup"><span data-stu-id="13996-3677">identification card</span></span> 
- <span data-ttu-id="13996-3678">identification cards</span><span class="sxs-lookup"><span data-stu-id="13996-3678">identification cards</span></span> 
- <span data-ttu-id="13996-3679">DriverLic #</span><span class="sxs-lookup"><span data-stu-id="13996-3679">DriverLic#</span></span> 
- <span data-ttu-id="13996-3680">DriverLics #</span><span class="sxs-lookup"><span data-stu-id="13996-3680">DriverLics#</span></span> 
- <span data-ttu-id="13996-3681">DriverLicense #</span><span class="sxs-lookup"><span data-stu-id="13996-3681">DriverLicense#</span></span> 
- <span data-ttu-id="13996-3682">DriverLicenses #</span><span class="sxs-lookup"><span data-stu-id="13996-3682">DriverLicenses#</span></span> 
- <span data-ttu-id="13996-3683">Driver Lic#</span><span class="sxs-lookup"><span data-stu-id="13996-3683">Driver Lic#</span></span> 
- <span data-ttu-id="13996-3684">Driver Lics#</span><span class="sxs-lookup"><span data-stu-id="13996-3684">Driver Lics#</span></span> 
- <span data-ttu-id="13996-3685">Driver License#</span><span class="sxs-lookup"><span data-stu-id="13996-3685">Driver License#</span></span> 
- <span data-ttu-id="13996-3686">Driver Licenses#</span><span class="sxs-lookup"><span data-stu-id="13996-3686">Driver Licenses#</span></span> 
- <span data-ttu-id="13996-3687">DriversLic #</span><span class="sxs-lookup"><span data-stu-id="13996-3687">DriversLic#</span></span> 
- <span data-ttu-id="13996-3688">DriversLics #</span><span class="sxs-lookup"><span data-stu-id="13996-3688">DriversLics#</span></span> 
- <span data-ttu-id="13996-3689">DriversLicense #</span><span class="sxs-lookup"><span data-stu-id="13996-3689">DriversLicense#</span></span> 
- <span data-ttu-id="13996-3690">DriversLicenses #</span><span class="sxs-lookup"><span data-stu-id="13996-3690">DriversLicenses#</span></span> 
- <span data-ttu-id="13996-3691">Drivers Lic#</span><span class="sxs-lookup"><span data-stu-id="13996-3691">Drivers Lic#</span></span> 
- <span data-ttu-id="13996-3692">Drivers Lics#</span><span class="sxs-lookup"><span data-stu-id="13996-3692">Drivers Lics#</span></span> 
- <span data-ttu-id="13996-3693">Drivers License#</span><span class="sxs-lookup"><span data-stu-id="13996-3693">Drivers License#</span></span> 
- <span data-ttu-id="13996-3694">Drivers Licenses#</span><span class="sxs-lookup"><span data-stu-id="13996-3694">Drivers Licenses#</span></span> 
- <span data-ttu-id="13996-3695">Driver'Lic #</span><span class="sxs-lookup"><span data-stu-id="13996-3695">Driver'Lic#</span></span> 
- <span data-ttu-id="13996-3696">Driver ' LiCS</span><span class="sxs-lookup"><span data-stu-id="13996-3696">Driver'Lics#</span></span> 
- <span data-ttu-id="13996-3697">Driver ' License</span><span class="sxs-lookup"><span data-stu-id="13996-3697">Driver'License#</span></span> 
- <span data-ttu-id="13996-3698">Driver ' licenses</span><span class="sxs-lookup"><span data-stu-id="13996-3698">Driver'Licenses#</span></span> 
- <span data-ttu-id="13996-3699">Driver' Lic#</span><span class="sxs-lookup"><span data-stu-id="13996-3699">Driver' Lic#</span></span> 
- <span data-ttu-id="13996-3700">Driver' Lics#</span><span class="sxs-lookup"><span data-stu-id="13996-3700">Driver' Lics#</span></span> 
- <span data-ttu-id="13996-3701">Driver' License#</span><span class="sxs-lookup"><span data-stu-id="13996-3701">Driver' License#</span></span> 
- <span data-ttu-id="13996-3702">Driver' Licenses#</span><span class="sxs-lookup"><span data-stu-id="13996-3702">Driver' Licenses#</span></span> 
- <span data-ttu-id="13996-3703">Driver'sLic #</span><span class="sxs-lookup"><span data-stu-id="13996-3703">Driver'sLic#</span></span> 
- <span data-ttu-id="13996-3704">Driver'sLics #</span><span class="sxs-lookup"><span data-stu-id="13996-3704">Driver'sLics#</span></span> 
- <span data-ttu-id="13996-3705">Secondola</span><span class="sxs-lookup"><span data-stu-id="13996-3705">Driver'sLicense#</span></span> 
- <span data-ttu-id="13996-3706">Driver'sLicenses #</span><span class="sxs-lookup"><span data-stu-id="13996-3706">Driver'sLicenses#</span></span> 
- <span data-ttu-id="13996-3707">Driver's Lic#</span><span class="sxs-lookup"><span data-stu-id="13996-3707">Driver's Lic#</span></span> 
- <span data-ttu-id="13996-3708">Driver's Lics#</span><span class="sxs-lookup"><span data-stu-id="13996-3708">Driver's Lics#</span></span> 
- <span data-ttu-id="13996-3709">Driver's License#</span><span class="sxs-lookup"><span data-stu-id="13996-3709">Driver's License#</span></span> 
- <span data-ttu-id="13996-3710">Driver's Licenses#</span><span class="sxs-lookup"><span data-stu-id="13996-3710">Driver's Licenses#</span></span> 
- <span data-ttu-id="13996-3711">id card#</span><span class="sxs-lookup"><span data-stu-id="13996-3711">id card#</span></span> 
- <span data-ttu-id="13996-3712">id cards#</span><span class="sxs-lookup"><span data-stu-id="13996-3712">id cards#</span></span> 
- <span data-ttu-id="13996-3713">identification card#</span><span class="sxs-lookup"><span data-stu-id="13996-3713">identification card#</span></span> 
- <span data-ttu-id="13996-3714">identification cards#</span><span class="sxs-lookup"><span data-stu-id="13996-3714">identification cards#</span></span> 


#### <a name="keywordstatenamedriverslicensename"></a><span data-ttu-id="13996-3715">Keyword_ [state_name] _drivers_license_name</span><span class="sxs-lookup"><span data-stu-id="13996-3715">Keyword_[state_name]_drivers_license_name</span></span>

- <span data-ttu-id="13996-3716">Abbreviazione dello stato (ad esempio, "NY")</span><span class="sxs-lookup"><span data-stu-id="13996-3716">State abbreviation (for example, "NY")</span></span> 
- <span data-ttu-id="13996-3717">Nome dello stato (ad esempio, "New York")</span><span class="sxs-lookup"><span data-stu-id="13996-3717">State name (for example, "New York")</span></span>    
   
## <a name="us-individual-taxpayer-identification-number-itin"></a><span data-ttu-id="13996-3718">Stati Uniti - Codice identificativo del contribuente individuale (ITIN)</span><span class="sxs-lookup"><span data-stu-id="13996-3718">U.S. Individual Taxpayer Identification Number (ITIN)</span></span>

### <a name="format"></a><span data-ttu-id="13996-3719">Formato</span><span class="sxs-lookup"><span data-stu-id="13996-3719">Format</span></span>

<span data-ttu-id="13996-3720">Nove cifre che iniziano con "9" e contengono un "7" o un "8" come quarta cifra. Può essere formattato con spazi e trattini (facoltativo)</span><span class="sxs-lookup"><span data-stu-id="13996-3720">Nine digits that start with a "9" and contain a "7" or "8" as the fourth digit, optionally formatted with spaces or dashes</span></span>

### <a name="pattern"></a><span data-ttu-id="13996-3721">Modello</span><span class="sxs-lookup"><span data-stu-id="13996-3721">Pattern</span></span>

<span data-ttu-id="13996-3722">Formattato</span><span class="sxs-lookup"><span data-stu-id="13996-3722">Formatted:</span></span>
- <span data-ttu-id="13996-3723">La cifra "9"</span><span class="sxs-lookup"><span data-stu-id="13996-3723">The digit "9"</span></span> 
- <span data-ttu-id="13996-3724">Due cifre</span><span class="sxs-lookup"><span data-stu-id="13996-3724">Two digits</span></span> 
- <span data-ttu-id="13996-3725">Uno spazio o un trattino</span><span class="sxs-lookup"><span data-stu-id="13996-3725">A space or dash</span></span> 
- <span data-ttu-id="13996-3726">Un "7" o un "8"</span><span class="sxs-lookup"><span data-stu-id="13996-3726">A "7" or "8"</span></span> 
- <span data-ttu-id="13996-3727">Una cifra</span><span class="sxs-lookup"><span data-stu-id="13996-3727">A digit</span></span> 
- <span data-ttu-id="13996-3728">Uno spazio o un trattino</span><span class="sxs-lookup"><span data-stu-id="13996-3728">A space, or dash</span></span> 
- <span data-ttu-id="13996-3729">Quattro cifre</span><span class="sxs-lookup"><span data-stu-id="13996-3729">Four digits</span></span>

<span data-ttu-id="13996-3730">Formattato</span><span class="sxs-lookup"><span data-stu-id="13996-3730">Unformatted:</span></span>
- <span data-ttu-id="13996-3731">La cifra "9"</span><span class="sxs-lookup"><span data-stu-id="13996-3731">The digit "9"</span></span> 
- <span data-ttu-id="13996-3732">Due cifre</span><span class="sxs-lookup"><span data-stu-id="13996-3732">Two digits</span></span> 
- <span data-ttu-id="13996-3733">Un "7" o un "8"</span><span class="sxs-lookup"><span data-stu-id="13996-3733">A "7" or "8"</span></span> 
- <span data-ttu-id="13996-3734">Cinque cifre</span><span class="sxs-lookup"><span data-stu-id="13996-3734">Five digits</span></span>

### <a name="checksum"></a><span data-ttu-id="13996-3735">Checksum</span><span class="sxs-lookup"><span data-stu-id="13996-3735">Checksum</span></span>

<span data-ttu-id="13996-3736">No</span><span class="sxs-lookup"><span data-stu-id="13996-3736">No</span></span>

### <a name="definition"></a><span data-ttu-id="13996-3737">Definizione</span><span class="sxs-lookup"><span data-stu-id="13996-3737">Definition</span></span>

<span data-ttu-id="13996-3738">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="13996-3738">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="13996-3739">La funzione Func_formatted_itin restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="13996-3739">The function Func_formatted_itin finds content that matches the pattern.</span></span>
- <span data-ttu-id="13996-3740">Si verifica almeno una delle situazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="13996-3740">At least one of the following is true:</span></span>
    - <span data-ttu-id="13996-3741">Viene trovata una parola chiave da Keyword_itin.</span><span class="sxs-lookup"><span data-stu-id="13996-3741">A keyword from Keyword_itin is found.</span></span>
    - <span data-ttu-id="13996-3742">La funzione Func_us_address rileva un indirizzo nel formato di data corretto.</span><span class="sxs-lookup"><span data-stu-id="13996-3742">The function Func_us_address finds an address in the right date format.</span></span>
    - <span data-ttu-id="13996-3743">La funzione Func_us_date rileva una data nel formato corretto.</span><span class="sxs-lookup"><span data-stu-id="13996-3743">The function Func_us_date finds a date in the right date format.</span></span>
    - <span data-ttu-id="13996-3744">Viene trovata una parola chiave da Keyword_itin_collaborative.</span><span class="sxs-lookup"><span data-stu-id="13996-3744">A keyword from Keyword_itin_collaborative is found.</span></span>

<span data-ttu-id="13996-3745">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="13996-3745">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="13996-3746">La funzione Func_unformatted_itin restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="13996-3746">The function Func_unformatted_itin finds content that matches the pattern.</span></span>
- <span data-ttu-id="13996-3747">Si verifica almeno una delle situazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="13996-3747">At least one of the following is true:</span></span>
    - <span data-ttu-id="13996-3748">Viene trovata una parola chiave da Keyword_itin_collaborative.</span><span class="sxs-lookup"><span data-stu-id="13996-3748">A keyword from Keyword_itin_collaborative is found.</span></span>
    - <span data-ttu-id="13996-3749">La funzione Func_us_address rileva un indirizzo nel formato di data corretto.</span><span class="sxs-lookup"><span data-stu-id="13996-3749">The function Func_us_address finds an address in the right date format.</span></span>
    - <span data-ttu-id="13996-3750">La funzione Func_us_date rileva una data nel formato corretto.</span><span class="sxs-lookup"><span data-stu-id="13996-3750">The function Func_us_date finds a date in the right date format.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="13996-3751">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="13996-3751">Keywords</span></span>

#### <a name="keyworditin"></a><span data-ttu-id="13996-3752">Keyword_itin</span><span class="sxs-lookup"><span data-stu-id="13996-3752">Keyword_itin</span></span>

- <span data-ttu-id="13996-3753">contribuente</span><span class="sxs-lookup"><span data-stu-id="13996-3753">taxpayer</span></span> 
- <span data-ttu-id="13996-3754">tax id</span><span class="sxs-lookup"><span data-stu-id="13996-3754">tax id</span></span> 
- <span data-ttu-id="13996-3755">tax identification</span><span class="sxs-lookup"><span data-stu-id="13996-3755">tax identification</span></span> 
- <span data-ttu-id="13996-3756">Itin</span><span class="sxs-lookup"><span data-stu-id="13996-3756">itin</span></span> 
- <span data-ttu-id="13996-3757">SSN</span><span class="sxs-lookup"><span data-stu-id="13996-3757">ssn</span></span> 
- <span data-ttu-id="13996-3758">latta</span><span class="sxs-lookup"><span data-stu-id="13996-3758">tin</span></span> 
- <span data-ttu-id="13996-3759">social security</span><span class="sxs-lookup"><span data-stu-id="13996-3759">social security</span></span> 
- <span data-ttu-id="13996-3760">tax payer</span><span class="sxs-lookup"><span data-stu-id="13996-3760">tax payer</span></span> 
- <span data-ttu-id="13996-3761">itins</span><span class="sxs-lookup"><span data-stu-id="13996-3761">itins</span></span> 
- <span data-ttu-id="13996-3762">taxid</span><span class="sxs-lookup"><span data-stu-id="13996-3762">taxid</span></span> 
- <span data-ttu-id="13996-3763">individual taxpayer</span><span class="sxs-lookup"><span data-stu-id="13996-3763">individual taxpayer</span></span> 

#### <a name="keyworditincollaborative"></a><span data-ttu-id="13996-3764">Keyword_itin_collaborative</span><span class="sxs-lookup"><span data-stu-id="13996-3764">Keyword_itin_collaborative</span></span>

- <span data-ttu-id="13996-3765">License</span><span class="sxs-lookup"><span data-stu-id="13996-3765">License</span></span> 
- <span data-ttu-id="13996-3766">DL</span><span class="sxs-lookup"><span data-stu-id="13996-3766">DL</span></span> 
- <span data-ttu-id="13996-3767">DOB</span><span class="sxs-lookup"><span data-stu-id="13996-3767">DOB</span></span> 
- <span data-ttu-id="13996-3768">Data di nascita</span><span class="sxs-lookup"><span data-stu-id="13996-3768">Birthdate</span></span> 
- <span data-ttu-id="13996-3769">Compleanno</span><span class="sxs-lookup"><span data-stu-id="13996-3769">Birthday</span></span> 
- <span data-ttu-id="13996-3770">Date of Birth</span><span class="sxs-lookup"><span data-stu-id="13996-3770">Date of Birth</span></span> 
   
## <a name="us-social-security-number-ssn"></a><span data-ttu-id="13996-3771">Stati Uniti - Numero di previdenza sociale (SSN)</span><span class="sxs-lookup"><span data-stu-id="13996-3771">U.S. Social Security Number (SSN)</span></span>

### <a name="format"></a><span data-ttu-id="13996-3772">Formato</span><span class="sxs-lookup"><span data-stu-id="13996-3772">Format</span></span>

<span data-ttu-id="13996-3773">9 cifre formattate o meno</span><span class="sxs-lookup"><span data-stu-id="13996-3773">9 digits, which may be in a formatted or unformatted pattern</span></span>

> [!NOTE]
> <span data-ttu-id="13996-3774">Se emesso prima della metà del 2011, un SSN ha una formattazione complessa in cui alcune parti del numero devono rientrare in alcuni intervalli per essere valide (ma non c'è nessun checksum).</span><span class="sxs-lookup"><span data-stu-id="13996-3774">If issued before mid-2011, an SSN has strong formatting where certain parts of the number must fall within certain ranges to be valid (but there's no checksum).</span></span>

### <a name="pattern"></a><span data-ttu-id="13996-3775">Modello</span><span class="sxs-lookup"><span data-stu-id="13996-3775">Pattern</span></span>

<span data-ttu-id="13996-3776">Quattro funzioni cercano SNSS in quattro modelli diversi:</span><span class="sxs-lookup"><span data-stu-id="13996-3776">Four functions look for SSNs in four different patterns:</span></span>
- <span data-ttu-id="13996-3777">Func_ssn trova SNSS con una formattazione complessa pre2011 che è formattata con trattini o spazi (ddd-dd-dddd o ddd dd dddd)</span><span class="sxs-lookup"><span data-stu-id="13996-3777">Func_ssn finds SSNs with pre-2011 strong formatting that are formatted with dashes or spaces (ddd-dd-dddd OR ddd dd dddd)</span></span>
- <span data-ttu-id="13996-3778">Func_unformatted_ssn trova SNSS con una formattazione complessa pre2011 che non è formattata come nove cifre consecutive (ddddddddd)</span><span class="sxs-lookup"><span data-stu-id="13996-3778">Func_unformatted_ssn finds SSNs with pre-2011 strong formatting that are unformatted as nine consecutive digits (ddddddddd)</span></span>
- <span data-ttu-id="13996-3779">Func_randomized_formatted_ssn trova post-2011 SNSS formattati con trattini o spazi (ddd-dd-dddd o ddd dd dddd)</span><span class="sxs-lookup"><span data-stu-id="13996-3779">Func_randomized_formatted_ssn finds post-2011 SSNs that are formatted with dashes or spaces (ddd-dd-dddd OR ddd dd dddd)</span></span>
- <span data-ttu-id="13996-3780">Func_randomized_unformatted_ssn trova post-2011 SNSS che non sono formattati come nove cifre consecutive (ddddddddd)</span><span class="sxs-lookup"><span data-stu-id="13996-3780">Func_randomized_unformatted_ssn finds post-2011 SSNs that are unformatted as nine consecutive digits (ddddddddd)</span></span>

### <a name="checksum"></a><span data-ttu-id="13996-3781">Checksum</span><span class="sxs-lookup"><span data-stu-id="13996-3781">Checksum</span></span>

<span data-ttu-id="13996-3782">No</span><span class="sxs-lookup"><span data-stu-id="13996-3782">No</span></span>


### <a name="definition"></a><span data-ttu-id="13996-3783">Definizione</span><span class="sxs-lookup"><span data-stu-id="13996-3783">Definition</span></span>

<span data-ttu-id="13996-3784">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="13996-3784">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="13996-3785">La funzione Func_ssn restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="13996-3785">The function Func_ssn finds content that matches the pattern.</span></span>
- <span data-ttu-id="13996-3786">Viene trovata una parola chiave da Keyword_ssn.</span><span class="sxs-lookup"><span data-stu-id="13996-3786">A keyword from Keyword_ssn is found.</span></span>

<span data-ttu-id="13996-3787">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="13996-3787">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="13996-3788">La funzione Func_unformatted_ssn trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="13996-3788">The function Func_unformatted_ssn finds content that matches the pattern.</span></span>
- <span data-ttu-id="13996-3789">Viene trovata una parola chiave da Keyword_ssn.</span><span class="sxs-lookup"><span data-stu-id="13996-3789">A keyword from Keyword_ssn is found.</span></span>

<span data-ttu-id="13996-3790">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 65%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="13996-3790">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="13996-3791">La funzione Func_randomized_formatted_ssn restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="13996-3791">The function Func_randomized_formatted_ssn finds content that matches the pattern.</span></span>
- <span data-ttu-id="13996-3792">Viene trovata una parola chiave da Keyword_ssn.</span><span class="sxs-lookup"><span data-stu-id="13996-3792">A keyword from Keyword_ssn is found.</span></span>
- <span data-ttu-id="13996-3793">La funzione Func_ssn non trovare contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="13996-3793">The function Func_ssn does not find content that matches the pattern.</span></span>

<span data-ttu-id="13996-3794">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 55%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="13996-3794">A DLP policy is 55% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="13996-3795">La funzione Func_randomized_unformatted_ssn restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="13996-3795">The function Func_randomized_unformatted_ssn finds content that matches the pattern.</span></span>
- <span data-ttu-id="13996-3796">Viene trovata una parola chiave da Keyword_ssn.</span><span class="sxs-lookup"><span data-stu-id="13996-3796">A keyword from Keyword_ssn is found.</span></span>
- <span data-ttu-id="13996-3797">La funzione Func_unformatted_ssn non trovare contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="13996-3797">The function Func_unformatted_ssn does not find content that matches the pattern.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="13996-3798">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="13996-3798">Keywords</span></span>

#### <a name="keywordssn"></a><span data-ttu-id="13996-3799">Keyword_ssn</span><span class="sxs-lookup"><span data-stu-id="13996-3799">Keyword_ssn</span></span>

- <span data-ttu-id="13996-3800">Social Security</span><span class="sxs-lookup"><span data-stu-id="13996-3800">Social Security</span></span> 
- <span data-ttu-id="13996-3801">Social Security#</span><span class="sxs-lookup"><span data-stu-id="13996-3801">Social Security#</span></span> 
- <span data-ttu-id="13996-3802">Soc Sec</span><span class="sxs-lookup"><span data-stu-id="13996-3802">Soc Sec</span></span> 
- <span data-ttu-id="13996-3803">SSN</span><span class="sxs-lookup"><span data-stu-id="13996-3803">SSN</span></span> 
- <span data-ttu-id="13996-3804">SNSS</span><span class="sxs-lookup"><span data-stu-id="13996-3804">SSNS</span></span> 
- <span data-ttu-id="13996-3805">SSN</span><span class="sxs-lookup"><span data-stu-id="13996-3805">SSN#</span></span> 
- <span data-ttu-id="13996-3806">SS</span><span class="sxs-lookup"><span data-stu-id="13996-3806">SS#</span></span> 
- <span data-ttu-id="13996-3807">SSID</span><span class="sxs-lookup"><span data-stu-id="13996-3807">SSID</span></span> 
   

