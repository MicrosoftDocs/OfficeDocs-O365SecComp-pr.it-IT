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
ms.service: o365-administration
localization_priority: Normal
ms.collection: Strat_O365_IP
ms.assetid: fd505979-76be-4d9f-b459-abef3fc9e86b
description: Prevenzione perdita dati (DLP) in Office 365 Security &amp; centro conformità include 80 tipi di informazioni riservate che si desidera utilizzare i criteri DLP. In questo argomento vengono elencati tutti questi tipi di informazioni riservate di un criterio DLP aspetto quando viene rilevato ogni tipo.
ms.openlocfilehash: 5097227d8efa833f255631febde50b937add48ef
ms.sourcegitcommit: ede6230c2df398dc0a633e8f32ee0bfede0d5142
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/25/2018
ms.locfileid: "25002689"
---
# <a name="what-the-sensitive-information-types-look-for"></a><span data-ttu-id="9d99e-104">Tipi di informazioni riservate disponibili da cercare</span><span class="sxs-lookup"><span data-stu-id="9d99e-104">What the sensitive information types look for</span></span>

<span data-ttu-id="9d99e-p102">Prevenzione perdita dati (DLP) in Office 365 Security &amp; centro conformità include molti tipi di informazioni riservate che si desidera utilizzare i criteri DLP. In questo argomento vengono elencati tutti questi tipi di informazioni riservate di un criterio DLP aspetto quando viene rilevato ogni tipo. Da un criterio che può essere identificato in base a un'espressione regolare o una funzione viene definito un tipo di informazioni riservate. Inoltre, elemento avvalorante, ad esempio parole chiave e checksum utilizzabile per identificare il tipo di informazioni riservate. Livello di probabilità e prossimità vengono inoltre utilizzati nel processo di valutazione.</span><span class="sxs-lookup"><span data-stu-id="9d99e-p102">Data loss prevention (DLP) in the Office 365 Security &amp; Compliance Center includes many sensitive information types that are ready for you to use in your DLP policies. This topic lists all of these sensitive information types and shows what a DLP policy looks for when it detects each type. A sensitive information type is defined by a pattern that can be identified by a regular expression or a function. In addition, corroborative evidence such as keywords and checksums can be used to identify a sensitive information type. Confidence level and proximity are also used in the evaluation process.</span></span>
  
## <a name="aba-routing-number"></a><span data-ttu-id="9d99e-110">Numero di registrazione ABA</span><span class="sxs-lookup"><span data-stu-id="9d99e-110">ABA Routing Number</span></span>

### <a name="format"></a><span data-ttu-id="9d99e-111">Formato</span><span class="sxs-lookup"><span data-stu-id="9d99e-111">Format</span></span>

<span data-ttu-id="9d99e-112">9 cifre formattate o meno</span><span class="sxs-lookup"><span data-stu-id="9d99e-112">9 digits which may be in a formatted or unformatted pattern</span></span>

### <a name="pattern"></a><span data-ttu-id="9d99e-113">Modello</span><span class="sxs-lookup"><span data-stu-id="9d99e-113">Pattern</span></span>

<span data-ttu-id="9d99e-114">Formattato:</span><span class="sxs-lookup"><span data-stu-id="9d99e-114">Formatted:</span></span>
- <span data-ttu-id="9d99e-115">Quattro cifre che iniziano con 0, 1, 2, 3, 6, 7 o 8</span><span class="sxs-lookup"><span data-stu-id="9d99e-115">Four digits beginning with 0, 1, 2, 3, 6, 7, or 8</span></span>
- <span data-ttu-id="9d99e-116">Una lineetta</span><span class="sxs-lookup"><span data-stu-id="9d99e-116">A hyphen</span></span>
- <span data-ttu-id="9d99e-117">Quattro cifre</span><span class="sxs-lookup"><span data-stu-id="9d99e-117">Four digits</span></span>
- <span data-ttu-id="9d99e-118">Una lineetta</span><span class="sxs-lookup"><span data-stu-id="9d99e-118">A hyphen</span></span>
- <span data-ttu-id="9d99e-119">Una cifra</span><span class="sxs-lookup"><span data-stu-id="9d99e-119">A digit</span></span>

<span data-ttu-id="9d99e-120">Non formattata: 9 cifre consecutive a partire da 0, 1, 2, 3, 6, 7 o 8</span><span class="sxs-lookup"><span data-stu-id="9d99e-120">Unformatted: 9 consecutive digits beginning with 0, 1, 2, 3, 6, 7, or 8</span></span> 

### <a name="checksum"></a><span data-ttu-id="9d99e-121">Checksum</span><span class="sxs-lookup"><span data-stu-id="9d99e-121">Checksum</span></span>

<span data-ttu-id="9d99e-122">No</span><span class="sxs-lookup"><span data-stu-id="9d99e-122">No</span></span>

### <a name="definition"></a><span data-ttu-id="9d99e-123">Definizione</span><span class="sxs-lookup"><span data-stu-id="9d99e-123">Definition</span></span>

<span data-ttu-id="9d99e-124">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="9d99e-124">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="9d99e-125">La funzione Func_aba_routing restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="9d99e-125">The function Func_aba_routing finds content that matches the pattern.</span></span>
- <span data-ttu-id="9d99e-126">Viene trovata una parola chiave da Keyword_ABA_Routing.</span><span class="sxs-lookup"><span data-stu-id="9d99e-126">A keyword from Keyword_ABA_Routing is found.</span></span>

```
<!-- ABA Routing Number -->
<Entity id="cb353f78-2b72-4c3c-8827-92ebe4f69fdf" patternsProximity="300" recommendedConfidence="75">
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_aba_routing" />
        <Match idRef="Keyword_ABA_Routing" />
      </Pattern>
 </Entity>
```


### <a name="keywords"></a><span data-ttu-id="9d99e-127">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="9d99e-127">Keywords</span></span>

#### <a name="keywordabarouting"></a><span data-ttu-id="9d99e-128">Keyword_ABA_Routing</span><span class="sxs-lookup"><span data-stu-id="9d99e-128">Keyword_ABA_Routing</span></span>

- <span data-ttu-id="9d99e-129">aba</span><span class="sxs-lookup"><span data-stu-id="9d99e-129">aba</span></span>
- <span data-ttu-id="9d99e-130">
aba #</span><span class="sxs-lookup"><span data-stu-id="9d99e-130">aba #</span></span>
- <span data-ttu-id="9d99e-131">
aba routing #</span><span class="sxs-lookup"><span data-stu-id="9d99e-131">aba routing #</span></span>
- <span data-ttu-id="9d99e-132">
aba routing number</span><span class="sxs-lookup"><span data-stu-id="9d99e-132">aba routing number</span></span>
- <span data-ttu-id="9d99e-133">
aba #</span><span class="sxs-lookup"><span data-stu-id="9d99e-133">aba#</span></span>
- <span data-ttu-id="9d99e-134">
abarouting#</span><span class="sxs-lookup"><span data-stu-id="9d99e-134">abarouting#</span></span>
- <span data-ttu-id="9d99e-135">
aba number</span><span class="sxs-lookup"><span data-stu-id="9d99e-135">aba number</span></span>
- <span data-ttu-id="9d99e-136">
abaroutingnumber</span><span class="sxs-lookup"><span data-stu-id="9d99e-136">abaroutingnumber</span></span>
- <span data-ttu-id="9d99e-137">
american bank association routing #</span><span class="sxs-lookup"><span data-stu-id="9d99e-137">american bank association routing #</span></span>
- <span data-ttu-id="9d99e-138">
american bank association routing number</span><span class="sxs-lookup"><span data-stu-id="9d99e-138">american bank association routing number</span></span>
- <span data-ttu-id="9d99e-139">
americanbankassociationrouting#</span><span class="sxs-lookup"><span data-stu-id="9d99e-139">americanbankassociationrouting#</span></span>
- <span data-ttu-id="9d99e-140">
americanbankassociationroutingnumber</span><span class="sxs-lookup"><span data-stu-id="9d99e-140">americanbankassociationroutingnumber</span></span>
- <span data-ttu-id="9d99e-141">
bank routing number</span><span class="sxs-lookup"><span data-stu-id="9d99e-141">bank routing number</span></span>
- <span data-ttu-id="9d99e-142">
bankrouting#</span><span class="sxs-lookup"><span data-stu-id="9d99e-142">bankrouting#</span></span>
- <span data-ttu-id="9d99e-143">
bankroutingnumber</span><span class="sxs-lookup"><span data-stu-id="9d99e-143">bankroutingnumber</span></span>
- <span data-ttu-id="9d99e-144">
routing transit number</span><span class="sxs-lookup"><span data-stu-id="9d99e-144">routing transit number</span></span>
- <span data-ttu-id="9d99e-145">
RTN
</span><span class="sxs-lookup"><span data-stu-id="9d99e-145">RTN</span></span> 
   
## <a name="argentina-national-identity-dni-number"></a><span data-ttu-id="9d99e-146">Argentina - Numero di identità nazionale (DNI)</span><span class="sxs-lookup"><span data-stu-id="9d99e-146">Argentina National Identity (DNI) Number</span></span>

### <a name="format"></a><span data-ttu-id="9d99e-147">Formato</span><span class="sxs-lookup"><span data-stu-id="9d99e-147">Format</span></span>

<span data-ttu-id="9d99e-148">Otto cifre separate da spazi</span><span class="sxs-lookup"><span data-stu-id="9d99e-148">Eight digits separated by periods</span></span>

### <a name="pattern"></a><span data-ttu-id="9d99e-149">Motivo</span><span class="sxs-lookup"><span data-stu-id="9d99e-149">Pattern</span></span>

<span data-ttu-id="9d99e-150">Otto cifre</span><span class="sxs-lookup"><span data-stu-id="9d99e-150">Eight digits:</span></span>
- <span data-ttu-id="9d99e-151">Due cifre</span><span class="sxs-lookup"><span data-stu-id="9d99e-151">Two digits</span></span>
- <span data-ttu-id="9d99e-152">Un punto </span><span class="sxs-lookup"><span data-stu-id="9d99e-152">A period</span></span>
- <span data-ttu-id="9d99e-153">Tre cifre</span><span class="sxs-lookup"><span data-stu-id="9d99e-153">Three digits</span></span>
- <span data-ttu-id="9d99e-154">Un punto </span><span class="sxs-lookup"><span data-stu-id="9d99e-154">A period</span></span>
- <span data-ttu-id="9d99e-155">Tre cifre</span><span class="sxs-lookup"><span data-stu-id="9d99e-155">Three digits</span></span>

### <a name="checksum"></a><span data-ttu-id="9d99e-156">Checksum</span><span class="sxs-lookup"><span data-stu-id="9d99e-156">Checksum</span></span>

<span data-ttu-id="9d99e-157">No</span><span class="sxs-lookup"><span data-stu-id="9d99e-157">No</span></span>

### <a name="definition"></a><span data-ttu-id="9d99e-158">Definizione</span><span class="sxs-lookup"><span data-stu-id="9d99e-158">Definition</span></span>

<span data-ttu-id="9d99e-159">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="9d99e-159">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="9d99e-160">L'espressione regolare Regex_argentina_national_id consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="9d99e-160">The regular expression Regex_argentina_national_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="9d99e-161">È possibile trovare una parola chiave da Keyword_argentina_national_id.</span><span class="sxs-lookup"><span data-stu-id="9d99e-161">A keyword from Keyword_argentina_national_id is found.</span></span>

```
<!-- Argentina National Identity (DNI) Number -->
<Entity id="eefbb00e-8282-433c-8620-8f1da3bffdb2" recommendedConfidence="75" patternsProximity="300">
   <Pattern confidenceLevel="75">
      <IdMatch idRef="Regex_argentina_national_id"/>
      <Match idRef="Keyword_argentina_national_id"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="9d99e-162">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="9d99e-162">Keywords</span></span>

#### <a name="keywordargentinanationalid"></a><span data-ttu-id="9d99e-163">Keyword_argentina_national_id</span><span class="sxs-lookup"><span data-stu-id="9d99e-163">Keyword_argentina_national_id</span></span>

- <span data-ttu-id="9d99e-164">Argentina - Numero di identità nazionale
</span><span class="sxs-lookup"><span data-stu-id="9d99e-164">Argentina National Identity number</span></span> 
- <span data-ttu-id="9d99e-165">Identità</span><span class="sxs-lookup"><span data-stu-id="9d99e-165">Identity</span></span> 
- <span data-ttu-id="9d99e-166">Identificazione della carta d'identità nazionale</span><span class="sxs-lookup"><span data-stu-id="9d99e-166">Identification National Identity Card</span></span> 
- <span data-ttu-id="9d99e-167">DNI
</span><span class="sxs-lookup"><span data-stu-id="9d99e-167">DNI</span></span> 
- <span data-ttu-id="9d99e-168">Scheda NIC registro nazionale delle persone</span><span class="sxs-lookup"><span data-stu-id="9d99e-168">NIC National Registry of Persons</span></span> 
- <span data-ttu-id="9d99e-169">Documento Nacional de Identidad
</span><span class="sxs-lookup"><span data-stu-id="9d99e-169">Documento Nacional de Identidad</span></span> 
- <span data-ttu-id="9d99e-170">Registro Nacional de las Personas
</span><span class="sxs-lookup"><span data-stu-id="9d99e-170">Registro Nacional de las Personas</span></span> 
- <span data-ttu-id="9d99e-171">Identidad
</span><span class="sxs-lookup"><span data-stu-id="9d99e-171">Identidad</span></span> 
- <span data-ttu-id="9d99e-172">Identificación
</span><span class="sxs-lookup"><span data-stu-id="9d99e-172">Identificación</span></span> 
   
## <a name="australia-bank-account-number"></a><span data-ttu-id="9d99e-173">Australia - Numero di conto bancario</span><span class="sxs-lookup"><span data-stu-id="9d99e-173">Australia Bank Account Number</span></span>

### <a name="format"></a><span data-ttu-id="9d99e-174">Formato</span><span class="sxs-lookup"><span data-stu-id="9d99e-174">Format</span></span>

<span data-ttu-id="9d99e-175">6-10 cifre con o senza un numero BSB (Bank/State/Branch)</span><span class="sxs-lookup"><span data-stu-id="9d99e-175">6-10 digits with or without a bank state branch number</span></span>

### <a name="pattern"></a><span data-ttu-id="9d99e-176">Modello</span><span class="sxs-lookup"><span data-stu-id="9d99e-176">Pattern</span></span>

<span data-ttu-id="9d99e-p103">Numero di conto è 6-10 cifre. Numero della filiale stato bank Australia:</span><span class="sxs-lookup"><span data-stu-id="9d99e-p103">Account number is 6-10 digits. Australia bank state branch number:</span></span>
- <span data-ttu-id="9d99e-179">Tre cifre</span><span class="sxs-lookup"><span data-stu-id="9d99e-179">Three digits</span></span> 
- <span data-ttu-id="9d99e-180">Una lineetta</span><span class="sxs-lookup"><span data-stu-id="9d99e-180">A hyphen</span></span> 
- <span data-ttu-id="9d99e-181">Tre cifre</span><span class="sxs-lookup"><span data-stu-id="9d99e-181">Three digits</span></span>

### <a name="checksum"></a><span data-ttu-id="9d99e-182">Checksum</span><span class="sxs-lookup"><span data-stu-id="9d99e-182">Checksum</span></span>

<span data-ttu-id="9d99e-183">No</span><span class="sxs-lookup"><span data-stu-id="9d99e-183">No</span></span>

### <a name="definition"></a><span data-ttu-id="9d99e-184">Definizione</span><span class="sxs-lookup"><span data-stu-id="9d99e-184">Definition</span></span>

<span data-ttu-id="9d99e-185">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="9d99e-185">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="9d99e-186">L'espressione regolare Regex_australia_bank_account_number restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="9d99e-186">The regular expression Regex_australia_bank_account_number finds content that matches the pattern..</span></span>
- <span data-ttu-id="9d99e-187">Viene trovata una parola chiave da Keyword_australia_bank_account_number.</span><span class="sxs-lookup"><span data-stu-id="9d99e-187">A keyword from Keyword_australia_bank_account_number is found.</span></span>
- <span data-ttu-id="9d99e-188">L'espressione regolare Regex_australia_bank_account_number_bsb restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="9d99e-188">The regular expression Regex_australia_bank_account_number_bsb finds content that matches the pattern.</span></span>

<span data-ttu-id="9d99e-189">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="9d99e-189">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="9d99e-190">L'espressione regolare Regex_australia_bank_account_number restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="9d99e-190">The regular expression Regex_australia_bank_account_number finds content that matches the pattern..</span></span>
- <span data-ttu-id="9d99e-191">Viene trovata una parola chiave da Keyword_australia_bank_account_number.</span><span class="sxs-lookup"><span data-stu-id="9d99e-191">A keyword from Keyword_australia_bank_account_number is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="9d99e-192">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="9d99e-192">Keywords</span></span>

#### <a name="keywordaustraliabankaccountnumber"></a><span data-ttu-id="9d99e-193">Keyword_australia_bank_account_number</span><span class="sxs-lookup"><span data-stu-id="9d99e-193">Keyword_australia_bank_account_number</span></span>

- <span data-ttu-id="9d99e-194">swift bank code</span><span class="sxs-lookup"><span data-stu-id="9d99e-194">swift bank code</span></span>
- <span data-ttu-id="9d99e-195">
correspondent bank</span><span class="sxs-lookup"><span data-stu-id="9d99e-195">correspondent bank</span></span>
- <span data-ttu-id="9d99e-196">
base currency</span><span class="sxs-lookup"><span data-stu-id="9d99e-196">base currency</span></span>
- <span data-ttu-id="9d99e-197">
usa account</span><span class="sxs-lookup"><span data-stu-id="9d99e-197">usa account</span></span>
- <span data-ttu-id="9d99e-198">
holder address</span><span class="sxs-lookup"><span data-stu-id="9d99e-198">holder address</span></span>
- <span data-ttu-id="9d99e-199">
bank address</span><span class="sxs-lookup"><span data-stu-id="9d99e-199">bank address</span></span>
- <span data-ttu-id="9d99e-200">
information account</span><span class="sxs-lookup"><span data-stu-id="9d99e-200">information account</span></span>
- <span data-ttu-id="9d99e-201">
fund transfers</span><span class="sxs-lookup"><span data-stu-id="9d99e-201">fund transfers</span></span>
- <span data-ttu-id="9d99e-202">
bank charges</span><span class="sxs-lookup"><span data-stu-id="9d99e-202">bank charges</span></span>
- <span data-ttu-id="9d99e-203">
bank details</span><span class="sxs-lookup"><span data-stu-id="9d99e-203">bank details</span></span>
- <span data-ttu-id="9d99e-204">
banking information</span><span class="sxs-lookup"><span data-stu-id="9d99e-204">banking information</span></span>
- <span data-ttu-id="9d99e-205">
full names</span><span class="sxs-lookup"><span data-stu-id="9d99e-205">full names</span></span>
- <span data-ttu-id="9d99e-206">

iaea</span><span class="sxs-lookup"><span data-stu-id="9d99e-206">iaea</span></span>

   
## <a name="australia-drivers-license-number"></a><span data-ttu-id="9d99e-207">Australia - Numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="9d99e-207">Australia Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="9d99e-208">Formato</span><span class="sxs-lookup"><span data-stu-id="9d99e-208">Format</span></span>

<span data-ttu-id="9d99e-209">Nove lettere e numeri</span><span class="sxs-lookup"><span data-stu-id="9d99e-209">Nine letters and digits</span></span>

### <a name="pattern"></a><span data-ttu-id="9d99e-210">Modello</span><span class="sxs-lookup"><span data-stu-id="9d99e-210">Pattern</span></span>

<span data-ttu-id="9d99e-211">Nove lettere e numeri:</span><span class="sxs-lookup"><span data-stu-id="9d99e-211">Nine letters and digits:</span></span> 

- <span data-ttu-id="9d99e-212">Due cifre o lettere (senza distinzione tra maiuscole/minuscole)</span><span class="sxs-lookup"><span data-stu-id="9d99e-212">Two digits or letters (not case sensitive)</span></span> 
- <span data-ttu-id="9d99e-213">Due cifre</span><span class="sxs-lookup"><span data-stu-id="9d99e-213">Two digits</span></span> 
- <span data-ttu-id="9d99e-214">Cinque cifre o lettere (senza distinzione tra maiuscole/minuscole)</span><span class="sxs-lookup"><span data-stu-id="9d99e-214">Five digits or letters (not case sensitive)</span></span>

<span data-ttu-id="9d99e-215">OPPURE</span><span class="sxs-lookup"><span data-stu-id="9d99e-215">OR</span></span>

- <span data-ttu-id="9d99e-216">1-2 lettere facoltative (senza distinzione tra maiuscole/minuscole)</span><span class="sxs-lookup"><span data-stu-id="9d99e-216">1-2 optional letters (not case sensitive)</span></span> 
- <span data-ttu-id="9d99e-217">4-9 cifre</span><span class="sxs-lookup"><span data-stu-id="9d99e-217">4-9 digits</span></span>

<span data-ttu-id="9d99e-218">OPPURE</span><span class="sxs-lookup"><span data-stu-id="9d99e-218">OR</span></span>

- <span data-ttu-id="9d99e-219">Nove cifre o lettere (senza distinzione tra maiuscole/minuscole)</span><span class="sxs-lookup"><span data-stu-id="9d99e-219">Nine digits or letters (not case sensitive)</span></span>

### <a name="checksum"></a><span data-ttu-id="9d99e-220">Checksum</span><span class="sxs-lookup"><span data-stu-id="9d99e-220">Checksum</span></span>

<span data-ttu-id="9d99e-221">No</span><span class="sxs-lookup"><span data-stu-id="9d99e-221">No</span></span>

### <a name="definition"></a><span data-ttu-id="9d99e-222">Definizione</span><span class="sxs-lookup"><span data-stu-id="9d99e-222">Definition</span></span>

<span data-ttu-id="9d99e-223">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="9d99e-223">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="9d99e-224">L'espressione regolare Regex_australia_drivers_license_number restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="9d99e-224">The regular expression Regex_australia_drivers_license_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="9d99e-225">Viene trovata una parola chiave da Keyword_australia_drivers_license_number.</span><span class="sxs-lookup"><span data-stu-id="9d99e-225">A keyword from Keyword_australia_drivers_license_number is found.</span></span>
- <span data-ttu-id="9d99e-226">Non vengono trovate parole chiava da Keyword_australia_drivers_license_number_exclusions.</span><span class="sxs-lookup"><span data-stu-id="9d99e-226">No keyword from Keyword_australia_drivers_license_number_exclusions is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="9d99e-227">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="9d99e-227">Keywords</span></span>

#### <a name="keywordaustraliadriverslicensenumber"></a><span data-ttu-id="9d99e-228">Keyword_australia_drivers_license_number</span><span class="sxs-lookup"><span data-stu-id="9d99e-228">Keyword_australia_drivers_license_number</span></span>

- <span data-ttu-id="9d99e-229">international driving permits</span><span class="sxs-lookup"><span data-stu-id="9d99e-229">international driving permits</span></span>
- <span data-ttu-id="9d99e-230">
australian automobile association</span><span class="sxs-lookup"><span data-stu-id="9d99e-230">australian automobile association</span></span>
- <span data-ttu-id="9d99e-231">
sydney nsw</span><span class="sxs-lookup"><span data-stu-id="9d99e-231">sydney nsw</span></span>
- <span data-ttu-id="9d99e-232">
international driving permit</span><span class="sxs-lookup"><span data-stu-id="9d99e-232">international driving permit</span></span>
- <span data-ttu-id="9d99e-233">DriverLicence</span><span class="sxs-lookup"><span data-stu-id="9d99e-233">DriverLicence</span></span>
- <span data-ttu-id="9d99e-234">DriverLicences</span><span class="sxs-lookup"><span data-stu-id="9d99e-234">DriverLicences</span></span>
- <span data-ttu-id="9d99e-235">Driver Lic</span><span class="sxs-lookup"><span data-stu-id="9d99e-235">Driver Lic</span></span>
- <span data-ttu-id="9d99e-236">Driver Licence
</span><span class="sxs-lookup"><span data-stu-id="9d99e-236">Driver Licence</span></span>
- <span data-ttu-id="9d99e-237">Driver Licences
</span><span class="sxs-lookup"><span data-stu-id="9d99e-237">Driver Licences</span></span>
- <span data-ttu-id="9d99e-238">DriversLic</span><span class="sxs-lookup"><span data-stu-id="9d99e-238">DriversLic</span></span>
- <span data-ttu-id="9d99e-239">DriversLicence</span><span class="sxs-lookup"><span data-stu-id="9d99e-239">DriversLicence</span></span>
- <span data-ttu-id="9d99e-240">DriversLicences</span><span class="sxs-lookup"><span data-stu-id="9d99e-240">DriversLicences</span></span>
- <span data-ttu-id="9d99e-241">Driver Lic</span><span class="sxs-lookup"><span data-stu-id="9d99e-241">Drivers Lic</span></span>
- <span data-ttu-id="9d99e-242">Driver conglomerati</span><span class="sxs-lookup"><span data-stu-id="9d99e-242">Drivers Lics</span></span>
- <span data-ttu-id="9d99e-243">Driver della licenza</span><span class="sxs-lookup"><span data-stu-id="9d99e-243">Drivers Licence</span></span>
- <span data-ttu-id="9d99e-244">Driver titoli</span><span class="sxs-lookup"><span data-stu-id="9d99e-244">Drivers Licences</span></span>
- <span data-ttu-id="9d99e-245">Driver'Lic</span><span class="sxs-lookup"><span data-stu-id="9d99e-245">Driver'Lic</span></span>
- <span data-ttu-id="9d99e-246">Driver'Lics</span><span class="sxs-lookup"><span data-stu-id="9d99e-246">Driver'Lics</span></span>
- <span data-ttu-id="9d99e-247">Driver'Licence</span><span class="sxs-lookup"><span data-stu-id="9d99e-247">Driver'Licence</span></span>
- <span data-ttu-id="9d99e-248">Driver'Licences</span><span class="sxs-lookup"><span data-stu-id="9d99e-248">Driver'Licences</span></span>
- <span data-ttu-id="9d99e-249">Driver' Lic</span><span class="sxs-lookup"><span data-stu-id="9d99e-249">Driver' Lic</span></span>
- <span data-ttu-id="9d99e-250">Driver' conglomerati</span><span class="sxs-lookup"><span data-stu-id="9d99e-250">Driver' Lics</span></span>
- <span data-ttu-id="9d99e-251">Driver' licenza</span><span class="sxs-lookup"><span data-stu-id="9d99e-251">Driver' Licence</span></span>
- <span data-ttu-id="9d99e-252">Driver' titoli</span><span class="sxs-lookup"><span data-stu-id="9d99e-252">Driver' Licences</span></span>
- <span data-ttu-id="9d99e-253">Driver'sLic</span><span class="sxs-lookup"><span data-stu-id="9d99e-253">Driver'sLic</span></span>
- <span data-ttu-id="9d99e-254">Driver'sLics</span><span class="sxs-lookup"><span data-stu-id="9d99e-254">Driver'sLics</span></span>
- <span data-ttu-id="9d99e-255">Driver'sLicence</span><span class="sxs-lookup"><span data-stu-id="9d99e-255">Driver'sLicence</span></span>
- <span data-ttu-id="9d99e-256">Driver'sLicences</span><span class="sxs-lookup"><span data-stu-id="9d99e-256">Driver'sLicences</span></span>
- <span data-ttu-id="9d99e-257">Lic della patente di Guida</span><span class="sxs-lookup"><span data-stu-id="9d99e-257">Driver's Lic</span></span>
- <span data-ttu-id="9d99e-258">Conglomerati della patente di Guida</span><span class="sxs-lookup"><span data-stu-id="9d99e-258">Driver's Lics</span></span>
- <span data-ttu-id="9d99e-259">Driver's Licence
</span><span class="sxs-lookup"><span data-stu-id="9d99e-259">Driver's Licence</span></span>
- <span data-ttu-id="9d99e-260">Driver's Licences
</span><span class="sxs-lookup"><span data-stu-id="9d99e-260">Driver's Licences</span></span>
- <span data-ttu-id="9d99e-261">DriverLic #</span><span class="sxs-lookup"><span data-stu-id="9d99e-261">DriverLic#</span></span>
- <span data-ttu-id="9d99e-262">DriverLics #</span><span class="sxs-lookup"><span data-stu-id="9d99e-262">DriverLics#</span></span>
- <span data-ttu-id="9d99e-263">DriverLicence #</span><span class="sxs-lookup"><span data-stu-id="9d99e-263">DriverLicence#</span></span>
- <span data-ttu-id="9d99e-264">DriverLicences #</span><span class="sxs-lookup"><span data-stu-id="9d99e-264">DriverLicences#</span></span>
- <span data-ttu-id="9d99e-265">Driver Lic#</span><span class="sxs-lookup"><span data-stu-id="9d99e-265">Driver Lic#</span></span>
- <span data-ttu-id="9d99e-266">
Driver Lics#
</span><span class="sxs-lookup"><span data-stu-id="9d99e-266">Driver Lics#</span></span>
- <span data-ttu-id="9d99e-267">Driver licenza #</span><span class="sxs-lookup"><span data-stu-id="9d99e-267">Driver Licence#</span></span>
- <span data-ttu-id="9d99e-268">Driver titoli #</span><span class="sxs-lookup"><span data-stu-id="9d99e-268">Driver Licences#</span></span>
- <span data-ttu-id="9d99e-269">DriversLic #</span><span class="sxs-lookup"><span data-stu-id="9d99e-269">DriversLic#</span></span>
- <span data-ttu-id="9d99e-270">DriversLics #</span><span class="sxs-lookup"><span data-stu-id="9d99e-270">DriversLics#</span></span>
- <span data-ttu-id="9d99e-271">DriversLicence #</span><span class="sxs-lookup"><span data-stu-id="9d99e-271">DriversLicence#</span></span>
- <span data-ttu-id="9d99e-272">DriversLicences #</span><span class="sxs-lookup"><span data-stu-id="9d99e-272">DriversLicences#</span></span>
- <span data-ttu-id="9d99e-273">Driver Lic #</span><span class="sxs-lookup"><span data-stu-id="9d99e-273">Drivers Lic#</span></span>
- <span data-ttu-id="9d99e-274">Driver conglomerati #</span><span class="sxs-lookup"><span data-stu-id="9d99e-274">Drivers Lics#</span></span>
- <span data-ttu-id="9d99e-275">Driver della licenza #</span><span class="sxs-lookup"><span data-stu-id="9d99e-275">Drivers Licence#</span></span>
- <span data-ttu-id="9d99e-276">Dipendenze dei titoli #</span><span class="sxs-lookup"><span data-stu-id="9d99e-276">Drivers Licences#</span></span>
- <span data-ttu-id="9d99e-277">Driver' Lic#
</span><span class="sxs-lookup"><span data-stu-id="9d99e-277">Driver'Lic#</span></span>
- <span data-ttu-id="9d99e-278">Driver' Lics#
</span><span class="sxs-lookup"><span data-stu-id="9d99e-278">Driver'Lics#</span></span>
- <span data-ttu-id="9d99e-279">Driver'Licence#
</span><span class="sxs-lookup"><span data-stu-id="9d99e-279">Driver'Licence#</span></span>
- <span data-ttu-id="9d99e-280">Driver'Licences#
</span><span class="sxs-lookup"><span data-stu-id="9d99e-280">Driver'Licences#</span></span>
- <span data-ttu-id="9d99e-281">Driver' Lic#
</span><span class="sxs-lookup"><span data-stu-id="9d99e-281">Driver' Lic#</span></span>
- <span data-ttu-id="9d99e-282">Driver' Lics#
</span><span class="sxs-lookup"><span data-stu-id="9d99e-282">Driver' Lics#</span></span>
- <span data-ttu-id="9d99e-283">Driver' licenza #</span><span class="sxs-lookup"><span data-stu-id="9d99e-283">Driver' Licence#</span></span>
- <span data-ttu-id="9d99e-284">Driver' titoli #</span><span class="sxs-lookup"><span data-stu-id="9d99e-284">Driver' Licences#</span></span>
- <span data-ttu-id="9d99e-285">Driver'sLic #</span><span class="sxs-lookup"><span data-stu-id="9d99e-285">Driver'sLic#</span></span>
- <span data-ttu-id="9d99e-286">Driver'sLics #</span><span class="sxs-lookup"><span data-stu-id="9d99e-286">Driver'sLics#</span></span>
- <span data-ttu-id="9d99e-287">Driver'sLicence #</span><span class="sxs-lookup"><span data-stu-id="9d99e-287">Driver'sLicence#</span></span>
- <span data-ttu-id="9d99e-288">Driver'sLicences #</span><span class="sxs-lookup"><span data-stu-id="9d99e-288">Driver'sLicences#</span></span>
- <span data-ttu-id="9d99e-289">Driver's Lic#
</span><span class="sxs-lookup"><span data-stu-id="9d99e-289">Driver's Lic#</span></span>
- <span data-ttu-id="9d99e-290">Driver's Lics#
</span><span class="sxs-lookup"><span data-stu-id="9d99e-290">Driver's Lics#</span></span>
- <span data-ttu-id="9d99e-291">Titolo # della patente di Guida</span><span class="sxs-lookup"><span data-stu-id="9d99e-291">Driver's Licence#</span></span>
- <span data-ttu-id="9d99e-292">Il titolo # della patente di Guida</span><span class="sxs-lookup"><span data-stu-id="9d99e-292">Driver's Licences#</span></span> 

#### <a name="keywordaustraliadriverslicensenumberexclusions"></a><span data-ttu-id="9d99e-293">Keyword_australia_drivers_license_number_exclusions</span><span class="sxs-lookup"><span data-stu-id="9d99e-293">Keyword_australia_drivers_license_number_exclusions</span></span>

- <span data-ttu-id="9d99e-294">aaa</span><span class="sxs-lookup"><span data-stu-id="9d99e-294">aaa</span></span>
- <span data-ttu-id="9d99e-295">DriverLicense</span><span class="sxs-lookup"><span data-stu-id="9d99e-295">DriverLicense</span></span>
- <span data-ttu-id="9d99e-296">DriverLicenses</span><span class="sxs-lookup"><span data-stu-id="9d99e-296">DriverLicenses</span></span>
- <span data-ttu-id="9d99e-297">Patente</span><span class="sxs-lookup"><span data-stu-id="9d99e-297">Driver License</span></span>
- <span data-ttu-id="9d99e-298">Driver licenze</span><span class="sxs-lookup"><span data-stu-id="9d99e-298">Driver Licenses</span></span>
- <span data-ttu-id="9d99e-299">PatenteGuida</span><span class="sxs-lookup"><span data-stu-id="9d99e-299">DriversLicense</span></span>
- <span data-ttu-id="9d99e-300">DriversLicenses</span><span class="sxs-lookup"><span data-stu-id="9d99e-300">DriversLicenses</span></span>
- <span data-ttu-id="9d99e-301">Patente di Guida</span><span class="sxs-lookup"><span data-stu-id="9d99e-301">Drivers License</span></span>
- <span data-ttu-id="9d99e-302">Driver licenze</span><span class="sxs-lookup"><span data-stu-id="9d99e-302">Drivers Licenses</span></span>
- <span data-ttu-id="9d99e-303">Driver'License</span><span class="sxs-lookup"><span data-stu-id="9d99e-303">Driver'License</span></span>
- <span data-ttu-id="9d99e-304">Driver'Licenses</span><span class="sxs-lookup"><span data-stu-id="9d99e-304">Driver'Licenses</span></span>
- <span data-ttu-id="9d99e-305">Driver' licenza</span><span class="sxs-lookup"><span data-stu-id="9d99e-305">Driver' License</span></span>
- <span data-ttu-id="9d99e-306">Driver' licenze</span><span class="sxs-lookup"><span data-stu-id="9d99e-306">Driver' Licenses</span></span>
- <span data-ttu-id="9d99e-307">Driver'sLicense</span><span class="sxs-lookup"><span data-stu-id="9d99e-307">Driver'sLicense</span></span>
- <span data-ttu-id="9d99e-308">Driver'sLicenses</span><span class="sxs-lookup"><span data-stu-id="9d99e-308">Driver'sLicenses</span></span>
- <span data-ttu-id="9d99e-309">Patente</span><span class="sxs-lookup"><span data-stu-id="9d99e-309">Driver's License</span></span>
- <span data-ttu-id="9d99e-310">Licenze della patente di Guida</span><span class="sxs-lookup"><span data-stu-id="9d99e-310">Driver's Licenses</span></span>
- <span data-ttu-id="9d99e-311">DriverLicense #</span><span class="sxs-lookup"><span data-stu-id="9d99e-311">DriverLicense#</span></span>
- <span data-ttu-id="9d99e-312">DriverLicenses #</span><span class="sxs-lookup"><span data-stu-id="9d99e-312">DriverLicenses#</span></span>
- <span data-ttu-id="9d99e-313">Driver licenza #</span><span class="sxs-lookup"><span data-stu-id="9d99e-313">Driver License#</span></span>
- <span data-ttu-id="9d99e-314">Driver licenze #</span><span class="sxs-lookup"><span data-stu-id="9d99e-314">Driver Licenses#</span></span>
- <span data-ttu-id="9d99e-315">PatenteGuida #</span><span class="sxs-lookup"><span data-stu-id="9d99e-315">DriversLicense#</span></span>
- <span data-ttu-id="9d99e-316">DriversLicenses #</span><span class="sxs-lookup"><span data-stu-id="9d99e-316">DriversLicenses#</span></span>
- <span data-ttu-id="9d99e-317">Driver della licenza #</span><span class="sxs-lookup"><span data-stu-id="9d99e-317">Drivers License#</span></span>
- <span data-ttu-id="9d99e-318">Driver licenze #</span><span class="sxs-lookup"><span data-stu-id="9d99e-318">Drivers Licenses#</span></span>
- <span data-ttu-id="9d99e-319">Driver' License#
</span><span class="sxs-lookup"><span data-stu-id="9d99e-319">Driver'License#</span></span>
- <span data-ttu-id="9d99e-320">Driver' Licenses#
</span><span class="sxs-lookup"><span data-stu-id="9d99e-320">Driver'Licenses#</span></span>
- <span data-ttu-id="9d99e-321">Driver' License#
</span><span class="sxs-lookup"><span data-stu-id="9d99e-321">Driver' License#</span></span>
- <span data-ttu-id="9d99e-322">Driver' Licenses#
</span><span class="sxs-lookup"><span data-stu-id="9d99e-322">Driver' Licenses#</span></span>
- <span data-ttu-id="9d99e-323">Driver'sLicense #</span><span class="sxs-lookup"><span data-stu-id="9d99e-323">Driver'sLicense#</span></span>
- <span data-ttu-id="9d99e-324">Driver'sLicenses #</span><span class="sxs-lookup"><span data-stu-id="9d99e-324">Driver'sLicenses#</span></span>
- <span data-ttu-id="9d99e-325">Driver's License#
</span><span class="sxs-lookup"><span data-stu-id="9d99e-325">Driver's License#</span></span>
- <span data-ttu-id="9d99e-326">

Driver's Licenses#</span><span class="sxs-lookup"><span data-stu-id="9d99e-326">Driver's Licenses#</span></span>
   
## <a name="australia-medical-account-number"></a><span data-ttu-id="9d99e-327">Australia - Numero di tessera sanitaria</span><span class="sxs-lookup"><span data-stu-id="9d99e-327">Australia Medical Account Number</span></span>

### <a name="format"></a><span data-ttu-id="9d99e-328">Formato</span><span class="sxs-lookup"><span data-stu-id="9d99e-328">Format</span></span>

<span data-ttu-id="9d99e-329">10-11 cifre</span><span class="sxs-lookup"><span data-stu-id="9d99e-329">10-11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="9d99e-330">Modello</span><span class="sxs-lookup"><span data-stu-id="9d99e-330">Pattern</span></span>

<span data-ttu-id="9d99e-331">10-11 cifre:</span><span class="sxs-lookup"><span data-stu-id="9d99e-331">10-11 digits:</span></span>
- <span data-ttu-id="9d99e-332">La prima cifra è compresa nell'intervallo 2-6</span><span class="sxs-lookup"><span data-stu-id="9d99e-332">First digit is in the range 2-6</span></span>
- <span data-ttu-id="9d99e-333">La nona cifra è una cifra di controllo</span><span class="sxs-lookup"><span data-stu-id="9d99e-333">Ninth digit is a check digit</span></span>
- <span data-ttu-id="9d99e-334">La decima cifra è la cifra del problema</span><span class="sxs-lookup"><span data-stu-id="9d99e-334">Tenth digit is the issue digit</span></span>
- <span data-ttu-id="9d99e-335">L'undicesima cifra (facoltativa) è il numero singolo</span><span class="sxs-lookup"><span data-stu-id="9d99e-335">Eleventh digit (optional) is the individual number</span></span>

### <a name="checksum"></a><span data-ttu-id="9d99e-336">Checksum</span><span class="sxs-lookup"><span data-stu-id="9d99e-336">Checksum</span></span>

<span data-ttu-id="9d99e-337">Sì</span><span class="sxs-lookup"><span data-stu-id="9d99e-337">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="9d99e-338">Definizione</span><span class="sxs-lookup"><span data-stu-id="9d99e-338">Definition</span></span>

<span data-ttu-id="9d99e-339">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 95%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="9d99e-339">A DLP policy is 95% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="9d99e-340">La funzione Func_australian_medical_account_number restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="9d99e-340">The function Func_australian_medical_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="9d99e-341">Viene trovata una parola chiave da Keyword_Australia_Medical_Account_Number.</span><span class="sxs-lookup"><span data-stu-id="9d99e-341">A keyword from Keyword_Australia_Medical_Account_Number is found.</span></span>
- <span data-ttu-id="9d99e-342">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="9d99e-342">The checksum passes.</span></span>

<span data-ttu-id="9d99e-343">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="9d99e-343">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="9d99e-344">La funzione Func_australian_medical_account_number restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="9d99e-344">The function Func_australian_medical_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="9d99e-345">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="9d99e-345">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="9d99e-346">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="9d99e-346">Keywords</span></span>

#### <a name="keywordaustraliamedicalaccountnumber"></a><span data-ttu-id="9d99e-347">Keyword_Australia_Medical_Account_Number</span><span class="sxs-lookup"><span data-stu-id="9d99e-347">Keyword_Australia_Medical_Account_Number</span></span>

- <span data-ttu-id="9d99e-348">bank account details</span><span class="sxs-lookup"><span data-stu-id="9d99e-348">bank account details</span></span>
- <span data-ttu-id="9d99e-349">
medicare payments</span><span class="sxs-lookup"><span data-stu-id="9d99e-349">medicare payments</span></span>
- <span data-ttu-id="9d99e-350">
mortgage account</span><span class="sxs-lookup"><span data-stu-id="9d99e-350">mortgage account</span></span>
- <span data-ttu-id="9d99e-351">
bank payments</span><span class="sxs-lookup"><span data-stu-id="9d99e-351">bank payments</span></span>
- <span data-ttu-id="9d99e-352">
information branch</span><span class="sxs-lookup"><span data-stu-id="9d99e-352">information branch</span></span>
- <span data-ttu-id="9d99e-353">
credit card loan</span><span class="sxs-lookup"><span data-stu-id="9d99e-353">credit card loan</span></span>
- <span data-ttu-id="9d99e-354">
department of human services</span><span class="sxs-lookup"><span data-stu-id="9d99e-354">department of human services</span></span>
- <span data-ttu-id="9d99e-355">servizio locale</span><span class="sxs-lookup"><span data-stu-id="9d99e-355">local service</span></span>
- <span data-ttu-id="9d99e-356">

medicare</span><span class="sxs-lookup"><span data-stu-id="9d99e-356">medicare</span></span>

   
## <a name="australia-passport-number"></a><span data-ttu-id="9d99e-357">Australia - Numero di passaporto</span><span class="sxs-lookup"><span data-stu-id="9d99e-357">Australia Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="9d99e-358">Formato</span><span class="sxs-lookup"><span data-stu-id="9d99e-358">Format</span></span>

<span data-ttu-id="9d99e-359">Una lettera seguita da sette cifre</span><span class="sxs-lookup"><span data-stu-id="9d99e-359">A letter followed by seven digits</span></span>

### <a name="pattern"></a><span data-ttu-id="9d99e-360">Modello</span><span class="sxs-lookup"><span data-stu-id="9d99e-360">Pattern</span></span>

<span data-ttu-id="9d99e-361">Una lettera (senza distinzione tra maiuscole/minuscole) seguita da sette cifre</span><span class="sxs-lookup"><span data-stu-id="9d99e-361">A letter (not case sensitive) followed by seven digits</span></span>

### <a name="checksum"></a><span data-ttu-id="9d99e-362">Checksum</span><span class="sxs-lookup"><span data-stu-id="9d99e-362">Checksum</span></span>

<span data-ttu-id="9d99e-363">No</span><span class="sxs-lookup"><span data-stu-id="9d99e-363">No</span></span>

### <a name="definition"></a><span data-ttu-id="9d99e-364">Definizione</span><span class="sxs-lookup"><span data-stu-id="9d99e-364">Definition</span></span>

<span data-ttu-id="9d99e-365">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="9d99e-365">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="9d99e-366">L'espressione regolare Regex_australia_passport_number restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="9d99e-366">The regular expression Regex_australia_passport_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="9d99e-367">È possibile trovare una parola chiave da Keyword_passport o Keyword_australia_passport_number.</span><span class="sxs-lookup"><span data-stu-id="9d99e-367">A keyword from Keyword_passport or Keyword_australia_passport_number is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="9d99e-368">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="9d99e-368">Keywords</span></span>

#### <a name="keywordpassport"></a><span data-ttu-id="9d99e-369">Keyword_passport</span><span class="sxs-lookup"><span data-stu-id="9d99e-369">Keyword_passport</span></span>

- <span data-ttu-id="9d99e-370">Passport Number</span><span class="sxs-lookup"><span data-stu-id="9d99e-370">Passport Number</span></span>
- <span data-ttu-id="9d99e-371">
Passport No</span><span class="sxs-lookup"><span data-stu-id="9d99e-371">Passport No</span></span>
- <span data-ttu-id="9d99e-372">Passport#
</span><span class="sxs-lookup"><span data-stu-id="9d99e-372">Passport #</span></span>
- <span data-ttu-id="9d99e-373">Passport#
</span><span class="sxs-lookup"><span data-stu-id="9d99e-373">Passport#</span></span>
- <span data-ttu-id="9d99e-374">PassportID</span><span class="sxs-lookup"><span data-stu-id="9d99e-374">PassportID</span></span>
- <span data-ttu-id="9d99e-375">Passportno
</span><span class="sxs-lookup"><span data-stu-id="9d99e-375">Passportno</span></span>
- <span data-ttu-id="9d99e-376">passportnumber
</span><span class="sxs-lookup"><span data-stu-id="9d99e-376">passportnumber</span></span>
- <span data-ttu-id="9d99e-377">パスポート</span><span class="sxs-lookup"><span data-stu-id="9d99e-377">パスポート</span></span>
- <span data-ttu-id="9d99e-378">パスポート番号
</span><span class="sxs-lookup"><span data-stu-id="9d99e-378">パスポート番号</span></span>
- <span data-ttu-id="9d99e-379">パスポートのNum
</span><span class="sxs-lookup"><span data-stu-id="9d99e-379">パスポートのNum</span></span>
- <span data-ttu-id="9d99e-380">
パスポート ＃
</span><span class="sxs-lookup"><span data-stu-id="9d99e-380">パスポート ＃</span></span> 
- <span data-ttu-id="9d99e-381">Numéro de passeport</span><span class="sxs-lookup"><span data-stu-id="9d99e-381">Numéro de passeport</span></span>
- <span data-ttu-id="9d99e-382">
Passeport n °</span><span class="sxs-lookup"><span data-stu-id="9d99e-382">Passeport n °</span></span>
- <span data-ttu-id="9d99e-383">Passeport Non
</span><span class="sxs-lookup"><span data-stu-id="9d99e-383">Passeport Non</span></span>
- <span data-ttu-id="9d99e-384">Passeport#
</span><span class="sxs-lookup"><span data-stu-id="9d99e-384">Passeport #</span></span>
- <span data-ttu-id="9d99e-385">Passeport#
</span><span class="sxs-lookup"><span data-stu-id="9d99e-385">Passeport#</span></span>
- <span data-ttu-id="9d99e-386">PasseportNon</span><span class="sxs-lookup"><span data-stu-id="9d99e-386">PasseportNon</span></span>
- <span data-ttu-id="9d99e-387">Passeportn °
</span><span class="sxs-lookup"><span data-stu-id="9d99e-387">Passeportn °</span></span>

#### <a name="keywordaustraliapassportnumber"></a><span data-ttu-id="9d99e-388">Keyword_australia_passport_number</span><span class="sxs-lookup"><span data-stu-id="9d99e-388">Keyword_australia_passport_number</span></span>

- <span data-ttu-id="9d99e-389">passport</span><span class="sxs-lookup"><span data-stu-id="9d99e-389">passport</span></span>
- <span data-ttu-id="9d99e-390">
passport details</span><span class="sxs-lookup"><span data-stu-id="9d99e-390">passport details</span></span>
- <span data-ttu-id="9d99e-391">
immigration and citizenship</span><span class="sxs-lookup"><span data-stu-id="9d99e-391">immigration and citizenship</span></span>
- <span data-ttu-id="9d99e-392">
commonwealth of australia</span><span class="sxs-lookup"><span data-stu-id="9d99e-392">commonwealth of australia</span></span>
- <span data-ttu-id="9d99e-393">
department of immigration</span><span class="sxs-lookup"><span data-stu-id="9d99e-393">department of immigration</span></span>
- <span data-ttu-id="9d99e-394">
residential address</span><span class="sxs-lookup"><span data-stu-id="9d99e-394">residential address</span></span>
- <span data-ttu-id="9d99e-395">
department of immigration and citizenship</span><span class="sxs-lookup"><span data-stu-id="9d99e-395">department of immigration and citizenship</span></span>
- <span data-ttu-id="9d99e-396">visa
</span><span class="sxs-lookup"><span data-stu-id="9d99e-396">visa</span></span>
- <span data-ttu-id="9d99e-397">
national identity card</span><span class="sxs-lookup"><span data-stu-id="9d99e-397">national identity card</span></span>
- <span data-ttu-id="9d99e-398">numero di passaporto</span><span class="sxs-lookup"><span data-stu-id="9d99e-398">passport number</span></span>
- <span data-ttu-id="9d99e-399">
travel document</span><span class="sxs-lookup"><span data-stu-id="9d99e-399">travel document</span></span>
- <span data-ttu-id="9d99e-400">

issuing authority</span><span class="sxs-lookup"><span data-stu-id="9d99e-400">issuing authority</span></span>
   
## <a name="australia-tax-file-number"></a><span data-ttu-id="9d99e-401">Australia - Identificativo fiscale</span><span class="sxs-lookup"><span data-stu-id="9d99e-401">Australia Tax File Number</span></span>

### <a name="format"></a><span data-ttu-id="9d99e-402">Formato</span><span class="sxs-lookup"><span data-stu-id="9d99e-402">Format</span></span>

<span data-ttu-id="9d99e-403">8-9 cifre</span><span class="sxs-lookup"><span data-stu-id="9d99e-403">8-9 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="9d99e-404">Modello</span><span class="sxs-lookup"><span data-stu-id="9d99e-404">Pattern</span></span>

<span data-ttu-id="9d99e-405">8-9 cifre in genere presentate con spazi, come mostrato di seguito:</span><span class="sxs-lookup"><span data-stu-id="9d99e-405">8-9 digits typically presented with spaces as follows:</span></span>
- <span data-ttu-id="9d99e-406">Tre cifre</span><span class="sxs-lookup"><span data-stu-id="9d99e-406">Three digits</span></span> 
- <span data-ttu-id="9d99e-407">Uno spazio facoltativo</span><span class="sxs-lookup"><span data-stu-id="9d99e-407">An optional space</span></span> 
- <span data-ttu-id="9d99e-408">Tre cifre</span><span class="sxs-lookup"><span data-stu-id="9d99e-408">Three digits</span></span> 
- <span data-ttu-id="9d99e-409">Uno spazio facoltativo</span><span class="sxs-lookup"><span data-stu-id="9d99e-409">An optional space</span></span> 
- <span data-ttu-id="9d99e-410">2-3 cifre e l'ultima è una cifra di controllo</span><span class="sxs-lookup"><span data-stu-id="9d99e-410">2-3 digits where the last digit is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="9d99e-411">Checksum</span><span class="sxs-lookup"><span data-stu-id="9d99e-411">Checksum</span></span>

<span data-ttu-id="9d99e-412">Sì</span><span class="sxs-lookup"><span data-stu-id="9d99e-412">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="9d99e-413">Definizione</span><span class="sxs-lookup"><span data-stu-id="9d99e-413">Definition</span></span>

<span data-ttu-id="9d99e-414">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="9d99e-414">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="9d99e-415">La funzione Func_australian_tax_file_number restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="9d99e-415">The function Func_australian_tax_file_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="9d99e-416">Non vengono trovate parole chiave da Keyword_Australia_Tax_File_Number o da Keyword_number_exclusions.</span><span class="sxs-lookup"><span data-stu-id="9d99e-416">No keyword from Keyword_Australia_Tax_File_Number or Keyword_number_exclusions is found.</span></span>
- <span data-ttu-id="9d99e-417">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="9d99e-417">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="9d99e-418">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="9d99e-418">Keywords</span></span>

#### <a name="keywordaustraliataxfilenumber"></a><span data-ttu-id="9d99e-419">Keyword_Australia_Tax_File_Number</span><span class="sxs-lookup"><span data-stu-id="9d99e-419">Keyword_Australia_Tax_File_Number</span></span>

- <span data-ttu-id="9d99e-420">australian business number</span><span class="sxs-lookup"><span data-stu-id="9d99e-420">australian business number</span></span>
- <span data-ttu-id="9d99e-421">
marginal tax rate</span><span class="sxs-lookup"><span data-stu-id="9d99e-421">marginal tax rate</span></span>
- <span data-ttu-id="9d99e-422">
medicare levy</span><span class="sxs-lookup"><span data-stu-id="9d99e-422">medicare levy</span></span>
- <span data-ttu-id="9d99e-423">
portfolio number</span><span class="sxs-lookup"><span data-stu-id="9d99e-423">portfolio number</span></span>
- <span data-ttu-id="9d99e-424">
service veterans</span><span class="sxs-lookup"><span data-stu-id="9d99e-424">service veterans</span></span>
- <span data-ttu-id="9d99e-425">
withholding tax</span><span class="sxs-lookup"><span data-stu-id="9d99e-425">withholding tax</span></span>
- <span data-ttu-id="9d99e-426">
individual tax return</span><span class="sxs-lookup"><span data-stu-id="9d99e-426">individual tax return</span></span>
- <span data-ttu-id="9d99e-427">

tax file number</span><span class="sxs-lookup"><span data-stu-id="9d99e-427">tax file number</span></span>

#### <a name="keywordnumberexclusions"></a><span data-ttu-id="9d99e-428">Keyword_number_exclusions</span><span class="sxs-lookup"><span data-stu-id="9d99e-428">Keyword_number_exclusions</span></span>

- <span data-ttu-id="9d99e-429">00000000</span><span class="sxs-lookup"><span data-stu-id="9d99e-429">00000000</span></span>
- <span data-ttu-id="9d99e-430">11111111</span><span class="sxs-lookup"><span data-stu-id="9d99e-430">11111111</span></span>
- <span data-ttu-id="9d99e-431">22222222</span><span class="sxs-lookup"><span data-stu-id="9d99e-431">22222222</span></span>
- <span data-ttu-id="9d99e-432">33333333</span><span class="sxs-lookup"><span data-stu-id="9d99e-432">33333333</span></span>
- <span data-ttu-id="9d99e-433">44444444</span><span class="sxs-lookup"><span data-stu-id="9d99e-433">44444444</span></span>
- <span data-ttu-id="9d99e-434">55555555</span><span class="sxs-lookup"><span data-stu-id="9d99e-434">55555555</span></span>
- <span data-ttu-id="9d99e-435">66666666</span><span class="sxs-lookup"><span data-stu-id="9d99e-435">66666666</span></span>
- <span data-ttu-id="9d99e-436">77777777</span><span class="sxs-lookup"><span data-stu-id="9d99e-436">77777777</span></span>
- <span data-ttu-id="9d99e-437">88888888</span><span class="sxs-lookup"><span data-stu-id="9d99e-437">88888888</span></span>
- <span data-ttu-id="9d99e-438">99999999</span><span class="sxs-lookup"><span data-stu-id="9d99e-438">99999999</span></span>
- <span data-ttu-id="9d99e-439">000000000</span><span class="sxs-lookup"><span data-stu-id="9d99e-439">000000000</span></span>
- <span data-ttu-id="9d99e-440">111111111</span><span class="sxs-lookup"><span data-stu-id="9d99e-440">111111111</span></span>
- <span data-ttu-id="9d99e-441">222222222</span><span class="sxs-lookup"><span data-stu-id="9d99e-441">222222222</span></span>
- <span data-ttu-id="9d99e-442">333333333</span><span class="sxs-lookup"><span data-stu-id="9d99e-442">333333333</span></span>
- <span data-ttu-id="9d99e-443">444444444</span><span class="sxs-lookup"><span data-stu-id="9d99e-443">444444444</span></span>
- <span data-ttu-id="9d99e-444">555555555</span><span class="sxs-lookup"><span data-stu-id="9d99e-444">555555555</span></span>
- <span data-ttu-id="9d99e-445">666666666</span><span class="sxs-lookup"><span data-stu-id="9d99e-445">666666666</span></span>
- <span data-ttu-id="9d99e-446">777777777</span><span class="sxs-lookup"><span data-stu-id="9d99e-446">777777777</span></span>
- <span data-ttu-id="9d99e-447">888888888</span><span class="sxs-lookup"><span data-stu-id="9d99e-447">888888888</span></span>
- <span data-ttu-id="9d99e-448">999999999</span><span class="sxs-lookup"><span data-stu-id="9d99e-448">999999999</span></span>
- <span data-ttu-id="9d99e-449">0000000000</span><span class="sxs-lookup"><span data-stu-id="9d99e-449">0000000000</span></span>
- <span data-ttu-id="9d99e-450">1111111111</span><span class="sxs-lookup"><span data-stu-id="9d99e-450">1111111111</span></span>
- <span data-ttu-id="9d99e-451">2222222222</span><span class="sxs-lookup"><span data-stu-id="9d99e-451">2222222222</span></span>
- <span data-ttu-id="9d99e-452">3333333333</span><span class="sxs-lookup"><span data-stu-id="9d99e-452">3333333333</span></span>
- <span data-ttu-id="9d99e-453">4444444444</span><span class="sxs-lookup"><span data-stu-id="9d99e-453">4444444444</span></span>
- <span data-ttu-id="9d99e-454">5555555555</span><span class="sxs-lookup"><span data-stu-id="9d99e-454">5555555555</span></span>
- <span data-ttu-id="9d99e-455">6666666666</span><span class="sxs-lookup"><span data-stu-id="9d99e-455">6666666666</span></span>
- <span data-ttu-id="9d99e-456">7777777777</span><span class="sxs-lookup"><span data-stu-id="9d99e-456">7777777777</span></span>
- <span data-ttu-id="9d99e-457">8888888888</span><span class="sxs-lookup"><span data-stu-id="9d99e-457">8888888888</span></span>
- <span data-ttu-id="9d99e-458">9999999999</span><span class="sxs-lookup"><span data-stu-id="9d99e-458">9999999999</span></span>
   
## <a name="belgium-national-number"></a><span data-ttu-id="9d99e-459">Belgio - Numero nazionale</span><span class="sxs-lookup"><span data-stu-id="9d99e-459">Belgium National Number</span></span>

### <a name="format"></a><span data-ttu-id="9d99e-460">Formato</span><span class="sxs-lookup"><span data-stu-id="9d99e-460">Format</span></span>

<span data-ttu-id="9d99e-461">11 cifre più delimitatori</span><span class="sxs-lookup"><span data-stu-id="9d99e-461">11 digits plus delimiters</span></span>

### <a name="pattern"></a><span data-ttu-id="9d99e-462">Motivo</span><span class="sxs-lookup"><span data-stu-id="9d99e-462">Pattern</span></span>

<span data-ttu-id="9d99e-463">11 cifre più delimitatori:</span><span class="sxs-lookup"><span data-stu-id="9d99e-463">11 digits plus delimiters:</span></span>
- <span data-ttu-id="9d99e-464">Sei cifre e due punti nel formato AA.MM.GG per data di nascita </span><span class="sxs-lookup"><span data-stu-id="9d99e-464">Six digits and two periods in the format YY.MM.DD for date of birth</span></span> 
- <span data-ttu-id="9d99e-465">Una lineetta</span><span class="sxs-lookup"><span data-stu-id="9d99e-465">A hyphen</span></span> 
- <span data-ttu-id="9d99e-466">Tre cifre sequenziali (dispari sia per uomini che per donne) </span><span class="sxs-lookup"><span data-stu-id="9d99e-466">Three sequential digits (odd for males, even for females)</span></span> 
- <span data-ttu-id="9d99e-467">Un punto </span><span class="sxs-lookup"><span data-stu-id="9d99e-467">A period</span></span> 
- <span data-ttu-id="9d99e-468">Due cifre, ovvero una cifra di controllo</span><span class="sxs-lookup"><span data-stu-id="9d99e-468">Two digits that are a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="9d99e-469">Checksum</span><span class="sxs-lookup"><span data-stu-id="9d99e-469">Checksum</span></span>

<span data-ttu-id="9d99e-470">Sì</span><span class="sxs-lookup"><span data-stu-id="9d99e-470">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="9d99e-471">Definizione</span><span class="sxs-lookup"><span data-stu-id="9d99e-471">Definition</span></span>

<span data-ttu-id="9d99e-472">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="9d99e-472">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="9d99e-473">La funzione Func_belgium_national_number consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="9d99e-473">The function Func_belgium_national_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="9d99e-474">È possibile trovare una parola chiave da Keyword_belgium_national_number.</span><span class="sxs-lookup"><span data-stu-id="9d99e-474">A keyword from Keyword_belgium_national_number is found.</span></span>
- <span data-ttu-id="9d99e-475">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="9d99e-475">The checksum passes.</span></span>

```
<!-- Belgium National Number -->
  <Entity id="fb969c9e-0fd1-4b18-8091-a2123c5e6a54" recommendedConfidence="75" patternsProximity="300">
   <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_belgium_national_number"/>
     <Match idRef="Keyword_belgium_national_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="9d99e-476">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="9d99e-476">Keywords</span></span>

#### <a name="keywordbelgiumnationalnumber"></a><span data-ttu-id="9d99e-477">Keyword_belgium_national_number</span><span class="sxs-lookup"><span data-stu-id="9d99e-477">Keyword_belgium_national_number</span></span>

- <span data-ttu-id="9d99e-478">Identità</span><span class="sxs-lookup"><span data-stu-id="9d99e-478">Identity</span></span>
- <span data-ttu-id="9d99e-479">Registrazione</span><span class="sxs-lookup"><span data-stu-id="9d99e-479">Registration</span></span>
- <span data-ttu-id="9d99e-480">Identificazione</span><span class="sxs-lookup"><span data-stu-id="9d99e-480">Identification</span></span> 
- <span data-ttu-id="9d99e-481">ID</span><span class="sxs-lookup"><span data-stu-id="9d99e-481">ID</span></span> 
- <span data-ttu-id="9d99e-482">Identiteitskaart</span><span class="sxs-lookup"><span data-stu-id="9d99e-482">Identiteitskaart</span></span>
- <span data-ttu-id="9d99e-483">Registratie nummer 
</span><span class="sxs-lookup"><span data-stu-id="9d99e-483">Registratie nummer</span></span> 
- <span data-ttu-id="9d99e-484">Identificatie nummer
</span><span class="sxs-lookup"><span data-stu-id="9d99e-484">Identificatie nummer</span></span> 
- <span data-ttu-id="9d99e-485">Identiteit</span><span class="sxs-lookup"><span data-stu-id="9d99e-485">Identiteit</span></span>
- <span data-ttu-id="9d99e-486">Registratie</span><span class="sxs-lookup"><span data-stu-id="9d99e-486">Registratie</span></span>
- <span data-ttu-id="9d99e-487">Identificatie

</span><span class="sxs-lookup"><span data-stu-id="9d99e-487">Identificatie</span></span> 
- <span data-ttu-id="9d99e-488">Carte d’identité
</span><span class="sxs-lookup"><span data-stu-id="9d99e-488">Carte d’identité</span></span> 
- <span data-ttu-id="9d99e-489">numéro d'immatriculation</span><span class="sxs-lookup"><span data-stu-id="9d99e-489">numéro d'immatriculation</span></span>
- <span data-ttu-id="9d99e-490">numéro d'identification</span><span class="sxs-lookup"><span data-stu-id="9d99e-490">numéro d'identification</span></span>
- <span data-ttu-id="9d99e-491">
identité
</span><span class="sxs-lookup"><span data-stu-id="9d99e-491">identité</span></span> 
- <span data-ttu-id="9d99e-492">iscrizione
</span><span class="sxs-lookup"><span data-stu-id="9d99e-492">inscription</span></span> 
- <span data-ttu-id="9d99e-493">Identifikation</span><span class="sxs-lookup"><span data-stu-id="9d99e-493">Identifikation</span></span>
- <span data-ttu-id="9d99e-494">Identifizierung</span><span class="sxs-lookup"><span data-stu-id="9d99e-494">Identifizierung</span></span>
- <span data-ttu-id="9d99e-495">Identifikationsnummer</span><span class="sxs-lookup"><span data-stu-id="9d99e-495">Identifikationsnummer</span></span>
- <span data-ttu-id="9d99e-496">Personalausweis</span><span class="sxs-lookup"><span data-stu-id="9d99e-496">Personalausweis</span></span>
- <span data-ttu-id="9d99e-497">Registrierung</span><span class="sxs-lookup"><span data-stu-id="9d99e-497">Registrierung</span></span>
- <span data-ttu-id="9d99e-498">Registrationsnummer</span><span class="sxs-lookup"><span data-stu-id="9d99e-498">Registrationsnummer</span></span>

   
## <a name="brazil-cpf-number"></a><span data-ttu-id="9d99e-499">Numero CPF Brasile</span><span class="sxs-lookup"><span data-stu-id="9d99e-499">Brazil CPF Number</span></span>

### <a name="format"></a><span data-ttu-id="9d99e-500">Formato</span><span class="sxs-lookup"><span data-stu-id="9d99e-500">Format</span></span>

<span data-ttu-id="9d99e-501">11 cifre che includono una cifra di controllo e possono essere formattate o non formattate</span><span class="sxs-lookup"><span data-stu-id="9d99e-501">11 digits that include a check digit and can be formatted or unformatted</span></span>

### <a name="pattern"></a><span data-ttu-id="9d99e-502">Modello</span><span class="sxs-lookup"><span data-stu-id="9d99e-502">Pattern</span></span>

<span data-ttu-id="9d99e-503">Formattato:</span><span class="sxs-lookup"><span data-stu-id="9d99e-503">Formatted:</span></span>
- <span data-ttu-id="9d99e-504">Tre cifre</span><span class="sxs-lookup"><span data-stu-id="9d99e-504">Three digits</span></span> 
- <span data-ttu-id="9d99e-505">Un punto </span><span class="sxs-lookup"><span data-stu-id="9d99e-505">A period</span></span> 
- <span data-ttu-id="9d99e-506">Tre cifre</span><span class="sxs-lookup"><span data-stu-id="9d99e-506">Three digits</span></span> 
- <span data-ttu-id="9d99e-507">Un punto </span><span class="sxs-lookup"><span data-stu-id="9d99e-507">A period</span></span> 
- <span data-ttu-id="9d99e-508">Tre cifre</span><span class="sxs-lookup"><span data-stu-id="9d99e-508">Three digits</span></span> 
- <span data-ttu-id="9d99e-509">Una lineetta</span><span class="sxs-lookup"><span data-stu-id="9d99e-509">A hyphen</span></span> 
- <span data-ttu-id="9d99e-510">Due cifre, ovvero le cifre di controllo</span><span class="sxs-lookup"><span data-stu-id="9d99e-510">Two digits which are check digits</span></span>

<span data-ttu-id="9d99e-511">Non formattate:</span><span class="sxs-lookup"><span data-stu-id="9d99e-511">Unformatted:</span></span>
- <span data-ttu-id="9d99e-512">11 cifre dove le ultime due sono cifre di controllo</span><span class="sxs-lookup"><span data-stu-id="9d99e-512">11 digits where the last two digits are check digits</span></span>

### <a name="checksum"></a><span data-ttu-id="9d99e-513">Checksum</span><span class="sxs-lookup"><span data-stu-id="9d99e-513">Checksum</span></span>

<span data-ttu-id="9d99e-514">Sì</span><span class="sxs-lookup"><span data-stu-id="9d99e-514">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="9d99e-515">Definizione</span><span class="sxs-lookup"><span data-stu-id="9d99e-515">Definition</span></span>

<span data-ttu-id="9d99e-516">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="9d99e-516">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="9d99e-517">La funzione Func_brazil_cpf consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="9d99e-517">The function Func_brazil_cpf finds content that matches the pattern.</span></span>
- <span data-ttu-id="9d99e-518">È possibile trovare una parola chiave da Keyword_brazil_cpf.</span><span class="sxs-lookup"><span data-stu-id="9d99e-518">A keyword from Keyword_brazil_cpf is found.</span></span>
- <span data-ttu-id="9d99e-519">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="9d99e-519">The checksum passes.</span></span>

<span data-ttu-id="9d99e-520">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="9d99e-520">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="9d99e-521">La funzione Func_brazil_cpf consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="9d99e-521">The function Func_brazil_cpf finds content that matches the pattern.</span></span>
- <span data-ttu-id="9d99e-522">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="9d99e-522">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="9d99e-523">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="9d99e-523">Keywords</span></span>

#### <a name="keywordbrazilcpf"></a><span data-ttu-id="9d99e-524">Keyword_brazil_cpf</span><span class="sxs-lookup"><span data-stu-id="9d99e-524">Keyword_brazil_cpf</span></span>

- <span data-ttu-id="9d99e-525">CPF</span><span class="sxs-lookup"><span data-stu-id="9d99e-525">CPF</span></span>
- <span data-ttu-id="9d99e-526">Identificazione</span><span class="sxs-lookup"><span data-stu-id="9d99e-526">Identification</span></span>
- <span data-ttu-id="9d99e-527">Registrazione</span><span class="sxs-lookup"><span data-stu-id="9d99e-527">Registration</span></span>
- <span data-ttu-id="9d99e-528">Ricavi</span><span class="sxs-lookup"><span data-stu-id="9d99e-528">Revenue</span></span>
- <span data-ttu-id="9d99e-529">Cadastro de Pessoas Físicas
</span><span class="sxs-lookup"><span data-stu-id="9d99e-529">Cadastro de Pessoas Físicas</span></span> 
- <span data-ttu-id="9d99e-530">Imposto
</span><span class="sxs-lookup"><span data-stu-id="9d99e-530">Imposto</span></span> 
- <span data-ttu-id="9d99e-531">Identificação
</span><span class="sxs-lookup"><span data-stu-id="9d99e-531">Identificação</span></span> 
- <span data-ttu-id="9d99e-532">Inscrição
</span><span class="sxs-lookup"><span data-stu-id="9d99e-532">Inscrição</span></span> 
- <span data-ttu-id="9d99e-533">Receita

</span><span class="sxs-lookup"><span data-stu-id="9d99e-533">Receita</span></span> 
   
## <a name="brazil-legal-entity-number-cnpj"></a><span data-ttu-id="9d99e-534">Brasile - Codice fiscale persone giuridiche (CNPJ)</span><span class="sxs-lookup"><span data-stu-id="9d99e-534">Brazil Legal Entity Number (CNPJ)</span></span>

### <a name="format"></a><span data-ttu-id="9d99e-535">Formato</span><span class="sxs-lookup"><span data-stu-id="9d99e-535">Format</span></span>

<span data-ttu-id="9d99e-536">14 cifre che includono il numero di registrazione, il codice della filiale, le cifre di controllo e i delimitatori</span><span class="sxs-lookup"><span data-stu-id="9d99e-536">14 digits that include a registration number, branch number, and check digits, plus delimiters</span></span>

### <a name="pattern"></a><span data-ttu-id="9d99e-537">Modello</span><span class="sxs-lookup"><span data-stu-id="9d99e-537">Pattern</span></span>
<span data-ttu-id="9d99e-538">14 cifre più delimitatori:</span><span class="sxs-lookup"><span data-stu-id="9d99e-538">14 digits, plus delimiters:</span></span>
- <span data-ttu-id="9d99e-539">Due cifre</span><span class="sxs-lookup"><span data-stu-id="9d99e-539">Two digits</span></span> 
- <span data-ttu-id="9d99e-540">Un punto </span><span class="sxs-lookup"><span data-stu-id="9d99e-540">A period</span></span> 
- <span data-ttu-id="9d99e-541">Tre cifre</span><span class="sxs-lookup"><span data-stu-id="9d99e-541">Three digits</span></span> 
- <span data-ttu-id="9d99e-542">Un punto </span><span class="sxs-lookup"><span data-stu-id="9d99e-542">A period</span></span> 
- <span data-ttu-id="9d99e-543">Tre cifre (le prime otto sono il numero di registrazione) </span><span class="sxs-lookup"><span data-stu-id="9d99e-543">Three digits (these first eight digits are the registration number)</span></span> 
- <span data-ttu-id="9d99e-544">Una barra</span><span class="sxs-lookup"><span data-stu-id="9d99e-544">A forward slash</span></span> 
- <span data-ttu-id="9d99e-545">Numero del ramo a quattro cifre </span><span class="sxs-lookup"><span data-stu-id="9d99e-545">Four-digit branch number</span></span> 
- <span data-ttu-id="9d99e-546">Una lineetta</span><span class="sxs-lookup"><span data-stu-id="9d99e-546">A hyphen</span></span> 
- <span data-ttu-id="9d99e-547">Due cifre, ovvero le cifre di controllo</span><span class="sxs-lookup"><span data-stu-id="9d99e-547">Two digits which are check digits</span></span>

### <a name="checksum"></a><span data-ttu-id="9d99e-548">Checksum</span><span class="sxs-lookup"><span data-stu-id="9d99e-548">Checksum</span></span>

<span data-ttu-id="9d99e-549">Sì</span><span class="sxs-lookup"><span data-stu-id="9d99e-549">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="9d99e-550">Definizione</span><span class="sxs-lookup"><span data-stu-id="9d99e-550">Definition</span></span>

<span data-ttu-id="9d99e-551">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="9d99e-551">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="9d99e-552">La funzione Func_brazil_cnpj consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="9d99e-552">The function Func_brazil_cnpj finds content that matches the pattern.</span></span>
- <span data-ttu-id="9d99e-553">È possibile trovare una parola chiave da Keyword_brazil_cnpj.</span><span class="sxs-lookup"><span data-stu-id="9d99e-553">A keyword from Keyword_brazil_cnpj is found.</span></span>
- <span data-ttu-id="9d99e-554">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="9d99e-554">The checksum passes.</span></span>

<span data-ttu-id="9d99e-555">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="9d99e-555">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="9d99e-556">La funzione Func_brazil_cnpj consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="9d99e-556">The function Func_brazil_cnpj finds content that matches the pattern.</span></span>
- <span data-ttu-id="9d99e-557">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="9d99e-557">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="9d99e-558">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="9d99e-558">Keywords</span></span>

#### <a name="keywordbrazilcnpj"></a><span data-ttu-id="9d99e-559">Keyword_brazil_cnpj</span><span class="sxs-lookup"><span data-stu-id="9d99e-559">Keyword_brazil_cnpj</span></span>

- <span data-ttu-id="9d99e-560">CNPJ
</span><span class="sxs-lookup"><span data-stu-id="9d99e-560">CNPJ</span></span> 
- <span data-ttu-id="9d99e-561">NUMERO CNPJ/MF</span><span class="sxs-lookup"><span data-stu-id="9d99e-561">CNPJ/MF</span></span> 
- <span data-ttu-id="9d99e-562">CNPJ-MF
</span><span class="sxs-lookup"><span data-stu-id="9d99e-562">CNPJ-MF</span></span> 
- <span data-ttu-id="9d99e-563">Codice fiscale persone giuridiche
</span><span class="sxs-lookup"><span data-stu-id="9d99e-563">National Registry of Legal Entities</span></span> 
- <span data-ttu-id="9d99e-564">Registro contribuenti
</span><span class="sxs-lookup"><span data-stu-id="9d99e-564">Taxpayers Registry</span></span> 
- <span data-ttu-id="9d99e-565">Persona giuridica
</span><span class="sxs-lookup"><span data-stu-id="9d99e-565">Legal entity</span></span> 
- <span data-ttu-id="9d99e-566">Persone giuridiche
</span><span class="sxs-lookup"><span data-stu-id="9d99e-566">Legal entities</span></span> 
- <span data-ttu-id="9d99e-567">Stato della registrazione
</span><span class="sxs-lookup"><span data-stu-id="9d99e-567">Registration Status</span></span> 
- <span data-ttu-id="9d99e-568">Ufficio
</span><span class="sxs-lookup"><span data-stu-id="9d99e-568">Business</span></span> 
- <span data-ttu-id="9d99e-569">Company</span><span class="sxs-lookup"><span data-stu-id="9d99e-569">Company</span></span>
- <span data-ttu-id="9d99e-570">CNPJ
</span><span class="sxs-lookup"><span data-stu-id="9d99e-570">CNPJ</span></span> 
- <span data-ttu-id="9d99e-571">Cadastro Nacional da Pessoa Jurídica
</span><span class="sxs-lookup"><span data-stu-id="9d99e-571">Cadastro Nacional da Pessoa Jurídica</span></span> 
- <span data-ttu-id="9d99e-572">Cadastro Geral de Contribuintes
</span><span class="sxs-lookup"><span data-stu-id="9d99e-572">Cadastro Geral de Contribuintes</span></span> 
- <span data-ttu-id="9d99e-573">CGC
</span><span class="sxs-lookup"><span data-stu-id="9d99e-573">CGC</span></span> 
- <span data-ttu-id="9d99e-574">Pessoa jurídica
</span><span class="sxs-lookup"><span data-stu-id="9d99e-574">Pessoa jurídica</span></span> 
- <span data-ttu-id="9d99e-575">Pessoas jurídicas
</span><span class="sxs-lookup"><span data-stu-id="9d99e-575">Pessoas jurídicas</span></span> 
- <span data-ttu-id="9d99e-576">Situação cadastral
</span><span class="sxs-lookup"><span data-stu-id="9d99e-576">Situação cadastral</span></span> 
- <span data-ttu-id="9d99e-577">Inscrição
</span><span class="sxs-lookup"><span data-stu-id="9d99e-577">Inscrição</span></span> 
- <span data-ttu-id="9d99e-578">Empresa
</span><span class="sxs-lookup"><span data-stu-id="9d99e-578">Empresa</span></span> 
   
## <a name="brazil-national-id-card-rg"></a><span data-ttu-id="9d99e-579">	Carta d'identità (Brasile) (RG)</span><span class="sxs-lookup"><span data-stu-id="9d99e-579">Brazil National ID Card (RG)</span></span>

### <a name="format"></a><span data-ttu-id="9d99e-580">Formato</span><span class="sxs-lookup"><span data-stu-id="9d99e-580">Format</span></span>

<span data-ttu-id="9d99e-581">Registro Geral (formato precedente): nove cifre</span><span class="sxs-lookup"><span data-stu-id="9d99e-581">Registro Geral (old format): Nine digits</span></span>

<span data-ttu-id="9d99e-582">Registro de Identidade (batch) (nuovo formato): 11 cifre</span><span class="sxs-lookup"><span data-stu-id="9d99e-582">Registro de Identidade (RIC) (new format): 11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="9d99e-583">Modello</span><span class="sxs-lookup"><span data-stu-id="9d99e-583">Pattern</span></span>

<span data-ttu-id="9d99e-584">Registro Geral (formato precedente):</span><span class="sxs-lookup"><span data-stu-id="9d99e-584">Registro Geral (old format):</span></span>
- <span data-ttu-id="9d99e-585">Due cifre</span><span class="sxs-lookup"><span data-stu-id="9d99e-585">Two digits</span></span> 
- <span data-ttu-id="9d99e-586">Un punto </span><span class="sxs-lookup"><span data-stu-id="9d99e-586">A period</span></span> 
- <span data-ttu-id="9d99e-587">Tre cifre</span><span class="sxs-lookup"><span data-stu-id="9d99e-587">Three digits</span></span> 
- <span data-ttu-id="9d99e-588">Un punto </span><span class="sxs-lookup"><span data-stu-id="9d99e-588">A period</span></span> 
- <span data-ttu-id="9d99e-589">Tre cifre</span><span class="sxs-lookup"><span data-stu-id="9d99e-589">Three digits</span></span> 
- <span data-ttu-id="9d99e-590">Una lineetta</span><span class="sxs-lookup"><span data-stu-id="9d99e-590">A hyphen</span></span> 
- <span data-ttu-id="9d99e-591">Una cifra, ovvero una cifra di controllo</span><span class="sxs-lookup"><span data-stu-id="9d99e-591">One digit which is a check digit</span></span>

<span data-ttu-id="9d99e-592">Registro de Identidade (batch) (nuovo formato):</span><span class="sxs-lookup"><span data-stu-id="9d99e-592">Registro de Identidade (RIC) (new format):</span></span>
- <span data-ttu-id="9d99e-593">10 cifre </span><span class="sxs-lookup"><span data-stu-id="9d99e-593">10 digits</span></span> 
- <span data-ttu-id="9d99e-594">Una lineetta</span><span class="sxs-lookup"><span data-stu-id="9d99e-594">A hyphen</span></span> 
- <span data-ttu-id="9d99e-595">Una cifra, ovvero una cifra di controllo</span><span class="sxs-lookup"><span data-stu-id="9d99e-595">One digit which is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="9d99e-596">Checksum</span><span class="sxs-lookup"><span data-stu-id="9d99e-596">Checksum</span></span>

<span data-ttu-id="9d99e-597">Sì</span><span class="sxs-lookup"><span data-stu-id="9d99e-597">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="9d99e-598">Definizione</span><span class="sxs-lookup"><span data-stu-id="9d99e-598">Definition</span></span>

<span data-ttu-id="9d99e-599">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="9d99e-599">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="9d99e-600">La funzione Func_brazil_rg consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="9d99e-600">The function Func_brazil_rg finds content that matches the pattern.</span></span>
- <span data-ttu-id="9d99e-601">È possibile trovare una parola chiave da Keyword_brazil_rg.</span><span class="sxs-lookup"><span data-stu-id="9d99e-601">A keyword from Keyword_brazil_rg is found.</span></span>
- <span data-ttu-id="9d99e-602">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="9d99e-602">The checksum passes.</span></span>

<span data-ttu-id="9d99e-603">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="9d99e-603">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="9d99e-604">La funzione Func_brazil_rg consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="9d99e-604">The function Func_brazil_rg finds content that matches the pattern.</span></span>
- <span data-ttu-id="9d99e-605">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="9d99e-605">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="9d99e-606">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="9d99e-606">Keywords</span></span>

#### <a name="keywordbrazilrg"></a><span data-ttu-id="9d99e-607">Keyword_brazil_rg</span><span class="sxs-lookup"><span data-stu-id="9d99e-607">Keyword_brazil_rg</span></span>

<span data-ttu-id="9d99e-608">Cédula de identidade carta d'identità nazionale id número de rregistro registro de Iidentidade registro geral RG (la parola chiave viene fatta distinzione tra maiuscole e minuscole) batch (la parola chiave viene fatta distinzione tra maiuscole e minuscole)</span><span class="sxs-lookup"><span data-stu-id="9d99e-608">Cédula de identidade identity card national id número de rregistro registro de Iidentidade registro geral RG (this keyword is case sensitive) RIC (this keyword is case sensitive)</span></span> 
   
## <a name="canada-bank-account-number"></a><span data-ttu-id="9d99e-609">Canada - Numero di conto bancario</span><span class="sxs-lookup"><span data-stu-id="9d99e-609">Canada Bank Account Number</span></span>

### <a name="format"></a><span data-ttu-id="9d99e-610">Formato</span><span class="sxs-lookup"><span data-stu-id="9d99e-610">Format</span></span>

<span data-ttu-id="9d99e-611">7 o 12 cifre</span><span class="sxs-lookup"><span data-stu-id="9d99e-611">Seven or twelve digits</span></span>

### <a name="pattern"></a><span data-ttu-id="9d99e-612">Modello</span><span class="sxs-lookup"><span data-stu-id="9d99e-612">Pattern</span></span>

<span data-ttu-id="9d99e-613">Un numero di conto corrente canadese comprende 7 o 12 cifre.</span><span class="sxs-lookup"><span data-stu-id="9d99e-613">A Canada Bank Account Number is seven or twelve digits.</span></span>

<span data-ttu-id="9d99e-614">Un numero di transito bancario canadese comprende:</span><span class="sxs-lookup"><span data-stu-id="9d99e-614">A Canada bank account transit number is:</span></span>
- <span data-ttu-id="9d99e-615">Cinque cifre</span><span class="sxs-lookup"><span data-stu-id="9d99e-615">Five digits</span></span> 
- <span data-ttu-id="9d99e-616">Una lineetta</span><span class="sxs-lookup"><span data-stu-id="9d99e-616">A hyphen</span></span> 
- <span data-ttu-id="9d99e-617">Tre cifre o</span><span class="sxs-lookup"><span data-stu-id="9d99e-617">Three digits OR</span></span>
- <span data-ttu-id="9d99e-618">Uno zero "0"</span><span class="sxs-lookup"><span data-stu-id="9d99e-618">A zero "0"</span></span> 
- <span data-ttu-id="9d99e-619">Otto cifre</span><span class="sxs-lookup"><span data-stu-id="9d99e-619">Eight digits</span></span>

### <a name="checksum"></a><span data-ttu-id="9d99e-620">Checksum</span><span class="sxs-lookup"><span data-stu-id="9d99e-620">Checksum</span></span>

<span data-ttu-id="9d99e-621">No</span><span class="sxs-lookup"><span data-stu-id="9d99e-621">No</span></span>

### <a name="definition"></a><span data-ttu-id="9d99e-622">Definizione</span><span class="sxs-lookup"><span data-stu-id="9d99e-622">Definition</span></span>

<span data-ttu-id="9d99e-623">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="9d99e-623">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="9d99e-624">L'espressione regolare Regex_canada_bank_account_number restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="9d99e-624">The regular expression Regex_canada_bank_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="9d99e-625">Viene trovata una parola chiave da Keyword_canada_bank_account_number.</span><span class="sxs-lookup"><span data-stu-id="9d99e-625">A keyword from Keyword_canada_bank_account_number is found.</span></span>
- <span data-ttu-id="9d99e-626">L'espressione regolare Regex_canada_bank_account_transit_number restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="9d99e-626">The regular expression Regex_canada_bank_account_transit_number finds content that matches the pattern.</span></span>

<span data-ttu-id="9d99e-627">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="9d99e-627">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="9d99e-628">L'espressione regolare Regex_canada_bank_account_number restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="9d99e-628">The regular expression Regex_canada_bank_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="9d99e-629">Viene trovata una parola chiave da Keyword_canada_bank_account_number.</span><span class="sxs-lookup"><span data-stu-id="9d99e-629">A keyword from Keyword_canada_bank_account_number is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="9d99e-630">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="9d99e-630">Keywords</span></span>

#### <a name="keywordcanadabankaccountnumber"></a><span data-ttu-id="9d99e-631">Keyword_canada_bank_account_number</span><span class="sxs-lookup"><span data-stu-id="9d99e-631">Keyword_canada_bank_account_number</span></span>

- <span data-ttu-id="9d99e-632">canada savings bonds</span><span class="sxs-lookup"><span data-stu-id="9d99e-632">canada savings bonds</span></span>
- <span data-ttu-id="9d99e-633">
canada revenue agency</span><span class="sxs-lookup"><span data-stu-id="9d99e-633">canada revenue agency</span></span>
- <span data-ttu-id="9d99e-634">
canadian financial institution</span><span class="sxs-lookup"><span data-stu-id="9d99e-634">canadian financial institution</span></span>
- <span data-ttu-id="9d99e-635">
direct deposit form</span><span class="sxs-lookup"><span data-stu-id="9d99e-635">direct deposit form</span></span>
- <span data-ttu-id="9d99e-636">
canadian citizen</span><span class="sxs-lookup"><span data-stu-id="9d99e-636">canadian citizen</span></span>
- <span data-ttu-id="9d99e-637">
legal representative</span><span class="sxs-lookup"><span data-stu-id="9d99e-637">legal representative</span></span>
- <span data-ttu-id="9d99e-638">
notary public</span><span class="sxs-lookup"><span data-stu-id="9d99e-638">notary public</span></span>
- <span data-ttu-id="9d99e-639">
commissioner for oaths</span><span class="sxs-lookup"><span data-stu-id="9d99e-639">commissioner for oaths</span></span>
- <span data-ttu-id="9d99e-640">
child care benefit</span><span class="sxs-lookup"><span data-stu-id="9d99e-640">child care benefit</span></span>
- <span data-ttu-id="9d99e-641">
universal child care</span><span class="sxs-lookup"><span data-stu-id="9d99e-641">universal child care</span></span>
- <span data-ttu-id="9d99e-642">
canada child tax benefit</span><span class="sxs-lookup"><span data-stu-id="9d99e-642">canada child tax benefit</span></span>
- <span data-ttu-id="9d99e-643">
income tax benefit</span><span class="sxs-lookup"><span data-stu-id="9d99e-643">income tax benefit</span></span>
- <span data-ttu-id="9d99e-644">
harmonized sales tax</span><span class="sxs-lookup"><span data-stu-id="9d99e-644">harmonized sales tax</span></span>
- <span data-ttu-id="9d99e-645">social insurance number</span><span class="sxs-lookup"><span data-stu-id="9d99e-645">social insurance number</span></span>
- <span data-ttu-id="9d99e-646">
income tax refund</span><span class="sxs-lookup"><span data-stu-id="9d99e-646">income tax refund</span></span>
- <span data-ttu-id="9d99e-647">
child tax benefit</span><span class="sxs-lookup"><span data-stu-id="9d99e-647">child tax benefit</span></span>
- <span data-ttu-id="9d99e-648">
territorial payments</span><span class="sxs-lookup"><span data-stu-id="9d99e-648">territorial payments</span></span>
- <span data-ttu-id="9d99e-649">
institution number</span><span class="sxs-lookup"><span data-stu-id="9d99e-649">institution number</span></span>
- <span data-ttu-id="9d99e-650">
deposit request</span><span class="sxs-lookup"><span data-stu-id="9d99e-650">deposit request</span></span>
- <span data-ttu-id="9d99e-651">
banking information</span><span class="sxs-lookup"><span data-stu-id="9d99e-651">banking information</span></span>
- <span data-ttu-id="9d99e-652">

direct deposit</span><span class="sxs-lookup"><span data-stu-id="9d99e-652">direct deposit</span></span>
   
## <a name="canada-drivers-license-number"></a><span data-ttu-id="9d99e-653">Canada - Numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="9d99e-653">Canada Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="9d99e-654">Formato</span><span class="sxs-lookup"><span data-stu-id="9d99e-654">Format</span></span>

<span data-ttu-id="9d99e-655">Varia in base alla provincia</span><span class="sxs-lookup"><span data-stu-id="9d99e-655">Varies by province</span></span>

### <a name="pattern"></a><span data-ttu-id="9d99e-656">Modello</span><span class="sxs-lookup"><span data-stu-id="9d99e-656">Pattern</span></span>

<span data-ttu-id="9d99e-657">Vari modelli per Alberta, Columbia Britannica, Manitoba, Nuovo Brunswick, Terranova e Labrador, Nuova Scozia, Ontario, Isola del Principe Edoardo, Quebec e Saskatchewan</span><span class="sxs-lookup"><span data-stu-id="9d99e-657">Various patterns covering Alberta, British Columbia, Manitoba, New Brunswick, Newfoundland/Labrador, Nova Scotia, Ontario, Prince Edward Island, Quebec, and Saskatchewan</span></span>

### <a name="checksum"></a><span data-ttu-id="9d99e-658">Checksum</span><span class="sxs-lookup"><span data-stu-id="9d99e-658">Checksum</span></span>

<span data-ttu-id="9d99e-659">No</span><span class="sxs-lookup"><span data-stu-id="9d99e-659">No</span></span>

### <a name="definition"></a><span data-ttu-id="9d99e-660">Definizione</span><span class="sxs-lookup"><span data-stu-id="9d99e-660">Definition</span></span>

<span data-ttu-id="9d99e-661">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="9d99e-661">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="9d99e-662">La funzione Func_[province_name]_drivers_license_number restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="9d99e-662">The function Func_[province_name]_drivers_license_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="9d99e-663">Viene trovata una parola chiave da Keyword_[province_name]_drivers_license_name.</span><span class="sxs-lookup"><span data-stu-id="9d99e-663">A keyword from Keyword_[province_name]_drivers_license_name is found.</span></span>
- <span data-ttu-id="9d99e-664">Viene trovata una parola chiave da Keyword_canada_drivers_license.</span><span class="sxs-lookup"><span data-stu-id="9d99e-664">A keyword from Keyword_canada_drivers_license is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="9d99e-665">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="9d99e-665">Keywords</span></span>

#### <a name="keywordprovincenamedriverslicensename"></a><span data-ttu-id="9d99e-666">Keyword_[province_name]_drivers_license_name</span><span class="sxs-lookup"><span data-stu-id="9d99e-666">Keyword_[province_name]_drivers_license_name</span></span>

- <span data-ttu-id="9d99e-667">L'abbreviazione della provincia, ad esempio, AB</span><span class="sxs-lookup"><span data-stu-id="9d99e-667">The province abbreviation, for example AB</span></span>
- <span data-ttu-id="9d99e-668">
Il nome della provincia, ad esempio, Alberta</span><span class="sxs-lookup"><span data-stu-id="9d99e-668">The province name, for example Alberta</span></span>

#### <a name="keywordcanadadriverslicense"></a><span data-ttu-id="9d99e-669">Keyword_canada_drivers_license</span><span class="sxs-lookup"><span data-stu-id="9d99e-669">Keyword_canada_drivers_license</span></span>

- <span data-ttu-id="9d99e-670">DL</span><span class="sxs-lookup"><span data-stu-id="9d99e-670">DL</span></span>
- <span data-ttu-id="9d99e-671">DLS</span><span class="sxs-lookup"><span data-stu-id="9d99e-671">DLS</span></span>
- <span data-ttu-id="9d99e-672">CDL</span><span class="sxs-lookup"><span data-stu-id="9d99e-672">CDL</span></span>
- <span data-ttu-id="9d99e-673">CDLS</span><span class="sxs-lookup"><span data-stu-id="9d99e-673">CDLS</span></span>
- <span data-ttu-id="9d99e-674">DriverLic</span><span class="sxs-lookup"><span data-stu-id="9d99e-674">DriverLic</span></span>
- <span data-ttu-id="9d99e-675">DriverLics</span><span class="sxs-lookup"><span data-stu-id="9d99e-675">DriverLics</span></span>
- <span data-ttu-id="9d99e-676">DriverLicense</span><span class="sxs-lookup"><span data-stu-id="9d99e-676">DriverLicense</span></span>
- <span data-ttu-id="9d99e-677">DriverLicenses</span><span class="sxs-lookup"><span data-stu-id="9d99e-677">DriverLicenses</span></span>
- <span data-ttu-id="9d99e-678">DriverLicence</span><span class="sxs-lookup"><span data-stu-id="9d99e-678">DriverLicence</span></span>
- <span data-ttu-id="9d99e-679">DriverLicences</span><span class="sxs-lookup"><span data-stu-id="9d99e-679">DriverLicences</span></span>
- <span data-ttu-id="9d99e-680">Driver Lic</span><span class="sxs-lookup"><span data-stu-id="9d99e-680">Driver Lic</span></span>
- <span data-ttu-id="9d99e-681">Driver conglomerati</span><span class="sxs-lookup"><span data-stu-id="9d99e-681">Driver Lics</span></span>
- <span data-ttu-id="9d99e-682">Patente</span><span class="sxs-lookup"><span data-stu-id="9d99e-682">Driver License</span></span>
- <span data-ttu-id="9d99e-683">Driver licenze</span><span class="sxs-lookup"><span data-stu-id="9d99e-683">Driver Licenses</span></span>
- <span data-ttu-id="9d99e-684">Driver Licence
</span><span class="sxs-lookup"><span data-stu-id="9d99e-684">Driver Licence</span></span>
- <span data-ttu-id="9d99e-685">Driver Licences
</span><span class="sxs-lookup"><span data-stu-id="9d99e-685">Driver Licences</span></span>
- <span data-ttu-id="9d99e-686">DriversLic</span><span class="sxs-lookup"><span data-stu-id="9d99e-686">DriversLic</span></span>
- <span data-ttu-id="9d99e-687">DriversLics</span><span class="sxs-lookup"><span data-stu-id="9d99e-687">DriversLics</span></span>
- <span data-ttu-id="9d99e-688">DriversLicence</span><span class="sxs-lookup"><span data-stu-id="9d99e-688">DriversLicence</span></span>
- <span data-ttu-id="9d99e-689">DriversLicences</span><span class="sxs-lookup"><span data-stu-id="9d99e-689">DriversLicences</span></span>
- <span data-ttu-id="9d99e-690">PatenteGuida</span><span class="sxs-lookup"><span data-stu-id="9d99e-690">DriversLicense</span></span>
- <span data-ttu-id="9d99e-691">DriversLicenses</span><span class="sxs-lookup"><span data-stu-id="9d99e-691">DriversLicenses</span></span>
- <span data-ttu-id="9d99e-692">Driver Lic</span><span class="sxs-lookup"><span data-stu-id="9d99e-692">Drivers Lic</span></span>
- <span data-ttu-id="9d99e-693">Driver conglomerati</span><span class="sxs-lookup"><span data-stu-id="9d99e-693">Drivers Lics</span></span>
- <span data-ttu-id="9d99e-694">Patente di Guida</span><span class="sxs-lookup"><span data-stu-id="9d99e-694">Drivers License</span></span>
- <span data-ttu-id="9d99e-695">Driver licenze</span><span class="sxs-lookup"><span data-stu-id="9d99e-695">Drivers Licenses</span></span>
- <span data-ttu-id="9d99e-696">Driver della licenza</span><span class="sxs-lookup"><span data-stu-id="9d99e-696">Drivers Licence</span></span>
- <span data-ttu-id="9d99e-697">Driver titoli</span><span class="sxs-lookup"><span data-stu-id="9d99e-697">Drivers Licences</span></span>
- <span data-ttu-id="9d99e-698">Driver'Lic</span><span class="sxs-lookup"><span data-stu-id="9d99e-698">Driver'Lic</span></span>
- <span data-ttu-id="9d99e-699">Driver'Lics</span><span class="sxs-lookup"><span data-stu-id="9d99e-699">Driver'Lics</span></span>
- <span data-ttu-id="9d99e-700">Driver'License</span><span class="sxs-lookup"><span data-stu-id="9d99e-700">Driver'License</span></span>
- <span data-ttu-id="9d99e-701">Driver'Licenses</span><span class="sxs-lookup"><span data-stu-id="9d99e-701">Driver'Licenses</span></span>
- <span data-ttu-id="9d99e-702">Driver'Licence</span><span class="sxs-lookup"><span data-stu-id="9d99e-702">Driver'Licence</span></span>
- <span data-ttu-id="9d99e-703">Driver'Licences</span><span class="sxs-lookup"><span data-stu-id="9d99e-703">Driver'Licences</span></span>
- <span data-ttu-id="9d99e-704">Driver' Lic</span><span class="sxs-lookup"><span data-stu-id="9d99e-704">Driver' Lic</span></span>
- <span data-ttu-id="9d99e-705">Driver' conglomerati</span><span class="sxs-lookup"><span data-stu-id="9d99e-705">Driver' Lics</span></span>
- <span data-ttu-id="9d99e-706">Driver' licenza</span><span class="sxs-lookup"><span data-stu-id="9d99e-706">Driver' License</span></span>
- <span data-ttu-id="9d99e-707">Driver' licenze</span><span class="sxs-lookup"><span data-stu-id="9d99e-707">Driver' Licenses</span></span>
- <span data-ttu-id="9d99e-708">Driver' licenza</span><span class="sxs-lookup"><span data-stu-id="9d99e-708">Driver' Licence</span></span>
- <span data-ttu-id="9d99e-709">Driver' titoli</span><span class="sxs-lookup"><span data-stu-id="9d99e-709">Driver' Licences</span></span>
- <span data-ttu-id="9d99e-710">Driver'sLic</span><span class="sxs-lookup"><span data-stu-id="9d99e-710">Driver'sLic</span></span>
- <span data-ttu-id="9d99e-711">Driver'sLics</span><span class="sxs-lookup"><span data-stu-id="9d99e-711">Driver'sLics</span></span>
- <span data-ttu-id="9d99e-712">Driver'sLicense</span><span class="sxs-lookup"><span data-stu-id="9d99e-712">Driver'sLicense</span></span>
- <span data-ttu-id="9d99e-713">Driver'sLicenses</span><span class="sxs-lookup"><span data-stu-id="9d99e-713">Driver'sLicenses</span></span>
- <span data-ttu-id="9d99e-714">Driver'sLicence</span><span class="sxs-lookup"><span data-stu-id="9d99e-714">Driver'sLicence</span></span>
- <span data-ttu-id="9d99e-715">Driver'sLicences</span><span class="sxs-lookup"><span data-stu-id="9d99e-715">Driver'sLicences</span></span>
- <span data-ttu-id="9d99e-716">Lic della patente di Guida</span><span class="sxs-lookup"><span data-stu-id="9d99e-716">Driver's Lic</span></span>
- <span data-ttu-id="9d99e-717">Conglomerati della patente di Guida</span><span class="sxs-lookup"><span data-stu-id="9d99e-717">Driver's Lics</span></span>
- <span data-ttu-id="9d99e-718">Patente</span><span class="sxs-lookup"><span data-stu-id="9d99e-718">Driver's License</span></span>
- <span data-ttu-id="9d99e-719">Licenze della patente di Guida</span><span class="sxs-lookup"><span data-stu-id="9d99e-719">Driver's Licenses</span></span>
- <span data-ttu-id="9d99e-720">Driver's Licence
</span><span class="sxs-lookup"><span data-stu-id="9d99e-720">Driver's Licence</span></span>
- <span data-ttu-id="9d99e-721">Driver's Licences
</span><span class="sxs-lookup"><span data-stu-id="9d99e-721">Driver's Licences</span></span>
- <span data-ttu-id="9d99e-722">Permis de Conduire</span><span class="sxs-lookup"><span data-stu-id="9d99e-722">Permis de Conduire</span></span>
- <span data-ttu-id="9d99e-723">id</span><span class="sxs-lookup"><span data-stu-id="9d99e-723">id</span></span>
- <span data-ttu-id="9d99e-724">ID</span><span class="sxs-lookup"><span data-stu-id="9d99e-724">ids</span></span>
- <span data-ttu-id="9d99e-725">
idcard number</span><span class="sxs-lookup"><span data-stu-id="9d99e-725">idcard number</span></span>
- <span data-ttu-id="9d99e-726">
idcard numbers</span><span class="sxs-lookup"><span data-stu-id="9d99e-726">idcard numbers</span></span>
- <span data-ttu-id="9d99e-727">
idcard #</span><span class="sxs-lookup"><span data-stu-id="9d99e-727">idcard #</span></span>
- <span data-ttu-id="9d99e-728">
idcard #s</span><span class="sxs-lookup"><span data-stu-id="9d99e-728">idcard #s</span></span>
- <span data-ttu-id="9d99e-729">scheda idcard</span><span class="sxs-lookup"><span data-stu-id="9d99e-729">idcard card</span></span>
- <span data-ttu-id="9d99e-730">schede idcard</span><span class="sxs-lookup"><span data-stu-id="9d99e-730">idcard cards</span></span>
- <span data-ttu-id="9d99e-731">idcard</span><span class="sxs-lookup"><span data-stu-id="9d99e-731">idcard</span></span>
- <span data-ttu-id="9d99e-732">identification number
</span><span class="sxs-lookup"><span data-stu-id="9d99e-732">identification number</span></span>
- <span data-ttu-id="9d99e-733">identification numbers
</span><span class="sxs-lookup"><span data-stu-id="9d99e-733">identification numbers</span></span>
- <span data-ttu-id="9d99e-734">identification#
</span><span class="sxs-lookup"><span data-stu-id="9d99e-734">identification #</span></span>
- <span data-ttu-id="9d99e-735">
identification #s</span><span class="sxs-lookup"><span data-stu-id="9d99e-735">identification #s</span></span>
- <span data-ttu-id="9d99e-736">scheda di identificazione</span><span class="sxs-lookup"><span data-stu-id="9d99e-736">identification card</span></span>
- <span data-ttu-id="9d99e-737">identificazione schede</span><span class="sxs-lookup"><span data-stu-id="9d99e-737">identification cards</span></span>
- <span data-ttu-id="9d99e-738">
identification
</span><span class="sxs-lookup"><span data-stu-id="9d99e-738">identification</span></span> 
- <span data-ttu-id="9d99e-739">DL#</span><span class="sxs-lookup"><span data-stu-id="9d99e-739">DL#</span></span>
- <span data-ttu-id="9d99e-740">
DLS#
</span><span class="sxs-lookup"><span data-stu-id="9d99e-740">DLS#</span></span> 
- <span data-ttu-id="9d99e-741">CDL#
</span><span class="sxs-lookup"><span data-stu-id="9d99e-741">CDL#</span></span> 
- <span data-ttu-id="9d99e-742">CDLS#
</span><span class="sxs-lookup"><span data-stu-id="9d99e-742">CDLS#</span></span> 
- <span data-ttu-id="9d99e-743">DriverLic #</span><span class="sxs-lookup"><span data-stu-id="9d99e-743">DriverLic#</span></span> 
- <span data-ttu-id="9d99e-744">DriverLics #</span><span class="sxs-lookup"><span data-stu-id="9d99e-744">DriverLics#</span></span> 
- <span data-ttu-id="9d99e-745">DriverLicense #</span><span class="sxs-lookup"><span data-stu-id="9d99e-745">DriverLicense#</span></span> 
- <span data-ttu-id="9d99e-746">DriverLicenses #</span><span class="sxs-lookup"><span data-stu-id="9d99e-746">DriverLicenses#</span></span> 
- <span data-ttu-id="9d99e-747">DriverLicence #</span><span class="sxs-lookup"><span data-stu-id="9d99e-747">DriverLicence#</span></span> 
- <span data-ttu-id="9d99e-748">DriverLicences #</span><span class="sxs-lookup"><span data-stu-id="9d99e-748">DriverLicences#</span></span> 
- <span data-ttu-id="9d99e-749">Driver Lic#</span><span class="sxs-lookup"><span data-stu-id="9d99e-749">Driver Lic#</span></span>
- <span data-ttu-id="9d99e-750">
Driver Lics#
</span><span class="sxs-lookup"><span data-stu-id="9d99e-750">Driver Lics#</span></span> 
- <span data-ttu-id="9d99e-751">Driver licenza #</span><span class="sxs-lookup"><span data-stu-id="9d99e-751">Driver License#</span></span> 
- <span data-ttu-id="9d99e-752">Driver licenze #</span><span class="sxs-lookup"><span data-stu-id="9d99e-752">Driver Licenses#</span></span> 
- <span data-ttu-id="9d99e-753">Driver licenza #</span><span class="sxs-lookup"><span data-stu-id="9d99e-753">Driver License#</span></span> 
- <span data-ttu-id="9d99e-754">Driver titoli #</span><span class="sxs-lookup"><span data-stu-id="9d99e-754">Driver Licences#</span></span> 
- <span data-ttu-id="9d99e-755">DriversLic #</span><span class="sxs-lookup"><span data-stu-id="9d99e-755">DriversLic#</span></span> 
- <span data-ttu-id="9d99e-756">DriversLics #</span><span class="sxs-lookup"><span data-stu-id="9d99e-756">DriversLics#</span></span> 
- <span data-ttu-id="9d99e-757">PatenteGuida #</span><span class="sxs-lookup"><span data-stu-id="9d99e-757">DriversLicense#</span></span> 
- <span data-ttu-id="9d99e-758">DriversLicenses #</span><span class="sxs-lookup"><span data-stu-id="9d99e-758">DriversLicenses#</span></span> 
- <span data-ttu-id="9d99e-759">DriversLicence #</span><span class="sxs-lookup"><span data-stu-id="9d99e-759">DriversLicence#</span></span> 
- <span data-ttu-id="9d99e-760">DriversLicences #</span><span class="sxs-lookup"><span data-stu-id="9d99e-760">DriversLicences#</span></span> 
- <span data-ttu-id="9d99e-761">Driver Lic #</span><span class="sxs-lookup"><span data-stu-id="9d99e-761">Drivers Lic#</span></span> 
- <span data-ttu-id="9d99e-762">Driver conglomerati #</span><span class="sxs-lookup"><span data-stu-id="9d99e-762">Drivers Lics#</span></span> 
- <span data-ttu-id="9d99e-763">Driver della licenza #</span><span class="sxs-lookup"><span data-stu-id="9d99e-763">Drivers License#</span></span> 
- <span data-ttu-id="9d99e-764">Driver licenze #</span><span class="sxs-lookup"><span data-stu-id="9d99e-764">Drivers Licenses#</span></span> 
- <span data-ttu-id="9d99e-765">Driver della licenza #</span><span class="sxs-lookup"><span data-stu-id="9d99e-765">Drivers Licence#</span></span> 
- <span data-ttu-id="9d99e-766">Dipendenze dei titoli #</span><span class="sxs-lookup"><span data-stu-id="9d99e-766">Drivers Licences#</span></span> 
- <span data-ttu-id="9d99e-767">Driver' Lic#
</span><span class="sxs-lookup"><span data-stu-id="9d99e-767">Driver'Lic#</span></span> 
- <span data-ttu-id="9d99e-768">Driver' Lics#
</span><span class="sxs-lookup"><span data-stu-id="9d99e-768">Driver'Lics#</span></span> 
- <span data-ttu-id="9d99e-769">Driver' License#
</span><span class="sxs-lookup"><span data-stu-id="9d99e-769">Driver'License#</span></span> 
- <span data-ttu-id="9d99e-770">Driver' Licenses#
</span><span class="sxs-lookup"><span data-stu-id="9d99e-770">Driver'Licenses#</span></span> 
- <span data-ttu-id="9d99e-771">Driver'Licence#
</span><span class="sxs-lookup"><span data-stu-id="9d99e-771">Driver'Licence#</span></span> 
- <span data-ttu-id="9d99e-772">Driver'Licences#
</span><span class="sxs-lookup"><span data-stu-id="9d99e-772">Driver'Licences#</span></span> 
- <span data-ttu-id="9d99e-773">Driver' Lic#
</span><span class="sxs-lookup"><span data-stu-id="9d99e-773">Driver' Lic#</span></span> 
- <span data-ttu-id="9d99e-774">Driver' Lics#
</span><span class="sxs-lookup"><span data-stu-id="9d99e-774">Driver' Lics#</span></span> 
- <span data-ttu-id="9d99e-775">Driver' License#
</span><span class="sxs-lookup"><span data-stu-id="9d99e-775">Driver' License#</span></span> 
- <span data-ttu-id="9d99e-776">Driver' Licenses#
</span><span class="sxs-lookup"><span data-stu-id="9d99e-776">Driver' Licenses#</span></span> 
- <span data-ttu-id="9d99e-777">Driver' licenza #</span><span class="sxs-lookup"><span data-stu-id="9d99e-777">Driver' Licence#</span></span> 
- <span data-ttu-id="9d99e-778">Driver' titoli #</span><span class="sxs-lookup"><span data-stu-id="9d99e-778">Driver' Licences#</span></span> 
- <span data-ttu-id="9d99e-779">Driver'sLic #</span><span class="sxs-lookup"><span data-stu-id="9d99e-779">Driver'sLic#</span></span> 
- <span data-ttu-id="9d99e-780">Driver'sLics #</span><span class="sxs-lookup"><span data-stu-id="9d99e-780">Driver'sLics#</span></span> 
- <span data-ttu-id="9d99e-781">Driver'sLicense #</span><span class="sxs-lookup"><span data-stu-id="9d99e-781">Driver'sLicense#</span></span> 
- <span data-ttu-id="9d99e-782">Driver'sLicenses #</span><span class="sxs-lookup"><span data-stu-id="9d99e-782">Driver'sLicenses#</span></span> 
- <span data-ttu-id="9d99e-783">Driver'sLicence #</span><span class="sxs-lookup"><span data-stu-id="9d99e-783">Driver'sLicence#</span></span> 
- <span data-ttu-id="9d99e-784">Driver'sLicences #</span><span class="sxs-lookup"><span data-stu-id="9d99e-784">Driver'sLicences#</span></span> 
- <span data-ttu-id="9d99e-785">Driver's Lic#
</span><span class="sxs-lookup"><span data-stu-id="9d99e-785">Driver's Lic#</span></span> 
- <span data-ttu-id="9d99e-786">Driver's Lics#
</span><span class="sxs-lookup"><span data-stu-id="9d99e-786">Driver's Lics#</span></span> 
- <span data-ttu-id="9d99e-787">Driver's License#
</span><span class="sxs-lookup"><span data-stu-id="9d99e-787">Driver's License#</span></span> 
- <span data-ttu-id="9d99e-788">Driver's Licenses#
</span><span class="sxs-lookup"><span data-stu-id="9d99e-788">Driver's Licenses#</span></span> 
- <span data-ttu-id="9d99e-789">Titolo # della patente di Guida</span><span class="sxs-lookup"><span data-stu-id="9d99e-789">Driver's Licence#</span></span> 
- <span data-ttu-id="9d99e-790">Il titolo # della patente di Guida</span><span class="sxs-lookup"><span data-stu-id="9d99e-790">Driver's Licences#</span></span> 
- <span data-ttu-id="9d99e-791">Permis de Conduire #</span><span class="sxs-lookup"><span data-stu-id="9d99e-791">Permis de Conduire#</span></span> 
- <span data-ttu-id="9d99e-792">ID #</span><span class="sxs-lookup"><span data-stu-id="9d99e-792">id#</span></span> 
- <span data-ttu-id="9d99e-793">ID #</span><span class="sxs-lookup"><span data-stu-id="9d99e-793">ids#</span></span> 
- <span data-ttu-id="9d99e-794">idcard card#
</span><span class="sxs-lookup"><span data-stu-id="9d99e-794">idcard card#</span></span> 
- <span data-ttu-id="9d99e-795">idcard cards#
</span><span class="sxs-lookup"><span data-stu-id="9d99e-795">idcard cards#</span></span> 
- <span data-ttu-id="9d99e-796">idcard#
</span><span class="sxs-lookup"><span data-stu-id="9d99e-796">idcard#</span></span> 
- <span data-ttu-id="9d99e-797">identification card#
</span><span class="sxs-lookup"><span data-stu-id="9d99e-797">identification card#</span></span> 
- <span data-ttu-id="9d99e-798">identification cards#
</span><span class="sxs-lookup"><span data-stu-id="9d99e-798">identification cards#</span></span> 
- <span data-ttu-id="9d99e-799">identification#
</span><span class="sxs-lookup"><span data-stu-id="9d99e-799">identification#</span></span> 
   
## <a name="canada-health-service-number"></a><span data-ttu-id="9d99e-800">Canada - Codice del servizio sanitario</span><span class="sxs-lookup"><span data-stu-id="9d99e-800">Canada Health Service Number</span></span>

### <a name="format"></a><span data-ttu-id="9d99e-801">Formato</span><span class="sxs-lookup"><span data-stu-id="9d99e-801">Format</span></span>

<span data-ttu-id="9d99e-802">10 cifre</span><span class="sxs-lookup"><span data-stu-id="9d99e-802">10 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="9d99e-803">Modello</span><span class="sxs-lookup"><span data-stu-id="9d99e-803">Pattern</span></span>

<span data-ttu-id="9d99e-804">10 cifre</span><span class="sxs-lookup"><span data-stu-id="9d99e-804">10 digits</span></span>

### <a name="checksum"></a><span data-ttu-id="9d99e-805">Checksum</span><span class="sxs-lookup"><span data-stu-id="9d99e-805">Checksum</span></span>

<span data-ttu-id="9d99e-806">No</span><span class="sxs-lookup"><span data-stu-id="9d99e-806">No</span></span>

### <a name="definition"></a><span data-ttu-id="9d99e-807">Definizione</span><span class="sxs-lookup"><span data-stu-id="9d99e-807">Definition</span></span>

<span data-ttu-id="9d99e-808">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="9d99e-808">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="9d99e-809">L'espressione regolare Regex_canada_health_service_number restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="9d99e-809">The regular expression Regex_canada_health_service_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="9d99e-810">Viene trovata una parola chiave da Keyword_canada_health_service_number.</span><span class="sxs-lookup"><span data-stu-id="9d99e-810">A keyword from Keyword_canada_health_service_number is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="9d99e-811">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="9d99e-811">Keywords</span></span>

#### <a name="keywordcanadahealthservicenumber"></a><span data-ttu-id="9d99e-812">Keyword_canada_health_service_number</span><span class="sxs-lookup"><span data-stu-id="9d99e-812">Keyword_canada_health_service_number</span></span>

- <span data-ttu-id="9d99e-813">personal health number</span><span class="sxs-lookup"><span data-stu-id="9d99e-813">personal health number</span></span>
- <span data-ttu-id="9d99e-814">
patient information</span><span class="sxs-lookup"><span data-stu-id="9d99e-814">patient information</span></span>
- <span data-ttu-id="9d99e-815">servizi di integrità</span><span class="sxs-lookup"><span data-stu-id="9d99e-815">health services</span></span>
- <span data-ttu-id="9d99e-816">
speciality services</span><span class="sxs-lookup"><span data-stu-id="9d99e-816">speciality services</span></span>
- <span data-ttu-id="9d99e-817">
automobile accident</span><span class="sxs-lookup"><span data-stu-id="9d99e-817">automobile accident</span></span>
- <span data-ttu-id="9d99e-818">
patient hospital</span><span class="sxs-lookup"><span data-stu-id="9d99e-818">patient hospital</span></span>
- <span data-ttu-id="9d99e-819">
psychiatrist</span><span class="sxs-lookup"><span data-stu-id="9d99e-819">psychiatrist</span></span>
- <span data-ttu-id="9d99e-820">
workers compensation</span><span class="sxs-lookup"><span data-stu-id="9d99e-820">workers compensation</span></span>
- <span data-ttu-id="9d99e-821">
disability</span><span class="sxs-lookup"><span data-stu-id="9d99e-821">disability</span></span>
      
## <a name="canada-passport-number"></a><span data-ttu-id="9d99e-822">Canada - Numero di passaporto</span><span class="sxs-lookup"><span data-stu-id="9d99e-822">Canada Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="9d99e-823">Formato</span><span class="sxs-lookup"><span data-stu-id="9d99e-823">Format</span></span>

<span data-ttu-id="9d99e-824">Due lettere maiuscole seguite da 6 cifre</span><span class="sxs-lookup"><span data-stu-id="9d99e-824">Two uppercase letters followed by six digits</span></span>

### <a name="pattern"></a><span data-ttu-id="9d99e-825">Modello</span><span class="sxs-lookup"><span data-stu-id="9d99e-825">Pattern</span></span>

<span data-ttu-id="9d99e-826">Due lettere maiuscole seguite da 6 cifre</span><span class="sxs-lookup"><span data-stu-id="9d99e-826">Two uppercase letters followed by six digits</span></span>

### <a name="checksum"></a><span data-ttu-id="9d99e-827">Checksum</span><span class="sxs-lookup"><span data-stu-id="9d99e-827">Checksum</span></span>

<span data-ttu-id="9d99e-828">No</span><span class="sxs-lookup"><span data-stu-id="9d99e-828">No</span></span>

### <a name="definition"></a><span data-ttu-id="9d99e-829">Definizione</span><span class="sxs-lookup"><span data-stu-id="9d99e-829">Definition</span></span>

<span data-ttu-id="9d99e-830">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="9d99e-830">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="9d99e-831">L'espressione regolare Regex_canada_passport_number restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="9d99e-831">The regular expression Regex_canada_passport_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="9d99e-832">È possibile trovare una parola chiave da Keyword_canada_passport_number o Keyword_passport.</span><span class="sxs-lookup"><span data-stu-id="9d99e-832">A keyword from Keyword_canada_passport_number or Keyword_passport is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="9d99e-833">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="9d99e-833">Keywords</span></span>

#### <a name="keywordcanadapassportnumber"></a><span data-ttu-id="9d99e-834">Keyword_canada_passport_number</span><span class="sxs-lookup"><span data-stu-id="9d99e-834">Keyword_canada_passport_number</span></span>

- <span data-ttu-id="9d99e-835">canadian citizenship</span><span class="sxs-lookup"><span data-stu-id="9d99e-835">canadian citizenship</span></span>
- <span data-ttu-id="9d99e-836">
canadian passport</span><span class="sxs-lookup"><span data-stu-id="9d99e-836">canadian passport</span></span>
- <span data-ttu-id="9d99e-837">
passport application</span><span class="sxs-lookup"><span data-stu-id="9d99e-837">passport application</span></span>
- <span data-ttu-id="9d99e-838">
passport photos</span><span class="sxs-lookup"><span data-stu-id="9d99e-838">passport photos</span></span>
- <span data-ttu-id="9d99e-839">
certified translator</span><span class="sxs-lookup"><span data-stu-id="9d99e-839">certified translator</span></span>
- <span data-ttu-id="9d99e-840">
canadian citizens</span><span class="sxs-lookup"><span data-stu-id="9d99e-840">canadian citizens</span></span>
- <span data-ttu-id="9d99e-841">
processing times</span><span class="sxs-lookup"><span data-stu-id="9d99e-841">processing times</span></span>
- <span data-ttu-id="9d99e-842">

renewal application</span><span class="sxs-lookup"><span data-stu-id="9d99e-842">renewal application</span></span>

#### <a name="keywordpassport"></a><span data-ttu-id="9d99e-843">Keyword_passport</span><span class="sxs-lookup"><span data-stu-id="9d99e-843">Keyword_passport</span></span>

- <span data-ttu-id="9d99e-844">Passport Number</span><span class="sxs-lookup"><span data-stu-id="9d99e-844">Passport Number</span></span>
- <span data-ttu-id="9d99e-845">
Passport No</span><span class="sxs-lookup"><span data-stu-id="9d99e-845">Passport No</span></span>
- <span data-ttu-id="9d99e-846">Passport#
</span><span class="sxs-lookup"><span data-stu-id="9d99e-846">Passport #</span></span>
- <span data-ttu-id="9d99e-847">Passport#
</span><span class="sxs-lookup"><span data-stu-id="9d99e-847">Passport#</span></span>
- <span data-ttu-id="9d99e-848">PassportID</span><span class="sxs-lookup"><span data-stu-id="9d99e-848">PassportID</span></span>
- <span data-ttu-id="9d99e-849">Passportno
</span><span class="sxs-lookup"><span data-stu-id="9d99e-849">Passportno</span></span>
- <span data-ttu-id="9d99e-850">passportnumber
</span><span class="sxs-lookup"><span data-stu-id="9d99e-850">passportnumber</span></span>
- <span data-ttu-id="9d99e-851">パスポート</span><span class="sxs-lookup"><span data-stu-id="9d99e-851">パスポート</span></span>
- <span data-ttu-id="9d99e-852">パスポート番号
</span><span class="sxs-lookup"><span data-stu-id="9d99e-852">パスポート番号</span></span>
- <span data-ttu-id="9d99e-853">パスポートのNum
</span><span class="sxs-lookup"><span data-stu-id="9d99e-853">パスポートのNum</span></span>
- <span data-ttu-id="9d99e-854">パスポート＃
</span><span class="sxs-lookup"><span data-stu-id="9d99e-854">パスポート＃</span></span>
- <span data-ttu-id="9d99e-855">Numéro de passeport</span><span class="sxs-lookup"><span data-stu-id="9d99e-855">Numéro de passeport</span></span>
- <span data-ttu-id="9d99e-856">
Passeport n °</span><span class="sxs-lookup"><span data-stu-id="9d99e-856">Passeport n °</span></span>
- <span data-ttu-id="9d99e-857">Passeport Non
</span><span class="sxs-lookup"><span data-stu-id="9d99e-857">Passeport Non</span></span>
- <span data-ttu-id="9d99e-858">Passeport#
</span><span class="sxs-lookup"><span data-stu-id="9d99e-858">Passeport #</span></span>
- <span data-ttu-id="9d99e-859">Passeport#
</span><span class="sxs-lookup"><span data-stu-id="9d99e-859">Passeport#</span></span>
- <span data-ttu-id="9d99e-860">PasseportNon</span><span class="sxs-lookup"><span data-stu-id="9d99e-860">PasseportNon</span></span>
- <span data-ttu-id="9d99e-861">

Passeportn °</span><span class="sxs-lookup"><span data-stu-id="9d99e-861">Passeportn °</span></span>
   
## <a name="canada-personal-health-identification-number-phin"></a><span data-ttu-id="9d99e-862">Canada - Numero di identificazione sanitaria personale (PHIN)</span><span class="sxs-lookup"><span data-stu-id="9d99e-862">Canada Personal Health Identification Number (PHIN)</span></span>

### <a name="format"></a><span data-ttu-id="9d99e-863">Formato</span><span class="sxs-lookup"><span data-stu-id="9d99e-863">Format</span></span>

<span data-ttu-id="9d99e-864">9 cifre</span><span class="sxs-lookup"><span data-stu-id="9d99e-864">Nine digits</span></span>

### <a name="pattern"></a><span data-ttu-id="9d99e-865">Modello</span><span class="sxs-lookup"><span data-stu-id="9d99e-865">Pattern</span></span>

<span data-ttu-id="9d99e-866">9 cifre</span><span class="sxs-lookup"><span data-stu-id="9d99e-866">Nine digits</span></span>

### <a name="checksum"></a><span data-ttu-id="9d99e-867">Checksum</span><span class="sxs-lookup"><span data-stu-id="9d99e-867">Checksum</span></span>

<span data-ttu-id="9d99e-868">No</span><span class="sxs-lookup"><span data-stu-id="9d99e-868">No</span></span>

### <a name="definition"></a><span data-ttu-id="9d99e-869">Definizione</span><span class="sxs-lookup"><span data-stu-id="9d99e-869">Definition</span></span>

<span data-ttu-id="9d99e-p104">Un criterio DLP è 75% la certezza che è stato rilevato questo tipo di informazioni riservate se all'interno di prossimità di 300 caratteri: l'espressione regolare Regex_canada_phin individua contenuto corrispondente al formato. Sono disponibili almeno due parole chiave Keyword_canada_phin o Keyword_canada_provinces..</span><span class="sxs-lookup"><span data-stu-id="9d99e-p104">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The regular expression Regex_canada_phin finds content that matches the pattern. At least two keywords from Keyword_canada_phin or Keyword_canada_provinces are found..</span></span>

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

### <a name="keywords"></a><span data-ttu-id="9d99e-872">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="9d99e-872">Keywords</span></span>

#### <a name="keywordcanadaphin"></a><span data-ttu-id="9d99e-873">Keyword_canada_phin</span><span class="sxs-lookup"><span data-stu-id="9d99e-873">Keyword_canada_phin</span></span>

- <span data-ttu-id="9d99e-874">social insurance number</span><span class="sxs-lookup"><span data-stu-id="9d99e-874">social insurance number</span></span>
- <span data-ttu-id="9d99e-875">
health information act</span><span class="sxs-lookup"><span data-stu-id="9d99e-875">health information act</span></span>
- <span data-ttu-id="9d99e-876">
income tax information</span><span class="sxs-lookup"><span data-stu-id="9d99e-876">income tax information</span></span>
- <span data-ttu-id="9d99e-877">
manitoba health</span><span class="sxs-lookup"><span data-stu-id="9d99e-877">manitoba health</span></span>
- <span data-ttu-id="9d99e-878">
health registration</span><span class="sxs-lookup"><span data-stu-id="9d99e-878">health registration</span></span>
- <span data-ttu-id="9d99e-879">
prescription purchases</span><span class="sxs-lookup"><span data-stu-id="9d99e-879">prescription purchases</span></span>
- <span data-ttu-id="9d99e-880">
benefit eligibility</span><span class="sxs-lookup"><span data-stu-id="9d99e-880">benefit eligibility</span></span>
- <span data-ttu-id="9d99e-881">
personal health</span><span class="sxs-lookup"><span data-stu-id="9d99e-881">personal health</span></span>
- <span data-ttu-id="9d99e-882">
power of attorney</span><span class="sxs-lookup"><span data-stu-id="9d99e-882">power of attorney</span></span>
- <span data-ttu-id="9d99e-883">
registration number</span><span class="sxs-lookup"><span data-stu-id="9d99e-883">registration number</span></span>
- <span data-ttu-id="9d99e-884">personal health number</span><span class="sxs-lookup"><span data-stu-id="9d99e-884">personal health number</span></span>
- <span data-ttu-id="9d99e-885">
practitioner referral</span><span class="sxs-lookup"><span data-stu-id="9d99e-885">practitioner referral</span></span>
- <span data-ttu-id="9d99e-886">
wellness professional</span><span class="sxs-lookup"><span data-stu-id="9d99e-886">wellness professional</span></span>
- <span data-ttu-id="9d99e-887">
patient referral</span><span class="sxs-lookup"><span data-stu-id="9d99e-887">patient referral</span></span>
- <span data-ttu-id="9d99e-888">

health and wellness</span><span class="sxs-lookup"><span data-stu-id="9d99e-888">health and wellness</span></span>

#### <a name="keywordcanadaprovinces"></a><span data-ttu-id="9d99e-889">Keyword_canada_provinces</span><span class="sxs-lookup"><span data-stu-id="9d99e-889">Keyword_canada_provinces</span></span>

- <span data-ttu-id="9d99e-890">Nunavut</span><span class="sxs-lookup"><span data-stu-id="9d99e-890">Nunavut</span></span>
- <span data-ttu-id="9d99e-891">
Quebec</span><span class="sxs-lookup"><span data-stu-id="9d99e-891">Quebec</span></span>
- <span data-ttu-id="9d99e-892">
Northwest Territories</span><span class="sxs-lookup"><span data-stu-id="9d99e-892">Northwest Territories</span></span>
- <span data-ttu-id="9d99e-893">
Ontario</span><span class="sxs-lookup"><span data-stu-id="9d99e-893">Ontario</span></span>
- <span data-ttu-id="9d99e-894">
British Columbia</span><span class="sxs-lookup"><span data-stu-id="9d99e-894">British Columbia</span></span>
- <span data-ttu-id="9d99e-895">
Alberta</span><span class="sxs-lookup"><span data-stu-id="9d99e-895">Alberta</span></span>
- <span data-ttu-id="9d99e-896">
Saskatchewan</span><span class="sxs-lookup"><span data-stu-id="9d99e-896">Saskatchewan</span></span>
- <span data-ttu-id="9d99e-897">
Manitoba</span><span class="sxs-lookup"><span data-stu-id="9d99e-897">Manitoba</span></span>
- <span data-ttu-id="9d99e-898">
Yukon</span><span class="sxs-lookup"><span data-stu-id="9d99e-898">Yukon</span></span>
- <span data-ttu-id="9d99e-899">
Newfoundland and Labrador</span><span class="sxs-lookup"><span data-stu-id="9d99e-899">Newfoundland and Labrador</span></span>
- <span data-ttu-id="9d99e-900">
New Brunswick</span><span class="sxs-lookup"><span data-stu-id="9d99e-900">New Brunswick</span></span>
- <span data-ttu-id="9d99e-901">
Nova Scotia</span><span class="sxs-lookup"><span data-stu-id="9d99e-901">Nova Scotia</span></span>
- <span data-ttu-id="9d99e-902">
Prince Edward Island</span><span class="sxs-lookup"><span data-stu-id="9d99e-902">Prince Edward Island</span></span>
- <span data-ttu-id="9d99e-903">Canada</span><span class="sxs-lookup"><span data-stu-id="9d99e-903">Canada</span></span>
   
## <a name="canada-social-insurance-number"></a><span data-ttu-id="9d99e-904">Canada - Numero di assicurazione sociale</span><span class="sxs-lookup"><span data-stu-id="9d99e-904">Canada Social Insurance Number</span></span>

### <a name="format"></a><span data-ttu-id="9d99e-905">Formato</span><span class="sxs-lookup"><span data-stu-id="9d99e-905">Format</span></span>

<span data-ttu-id="9d99e-906">9 cifre con spazi o lineette facoltativi</span><span class="sxs-lookup"><span data-stu-id="9d99e-906">Nine digits with optional hyphens or spaces</span></span>

### <a name="pattern"></a><span data-ttu-id="9d99e-907">Modello</span><span class="sxs-lookup"><span data-stu-id="9d99e-907">Pattern</span></span>

<span data-ttu-id="9d99e-908">Formattato:</span><span class="sxs-lookup"><span data-stu-id="9d99e-908">Formatted:</span></span>
- <span data-ttu-id="9d99e-909">Tre cifre</span><span class="sxs-lookup"><span data-stu-id="9d99e-909">Three digits</span></span> 
- <span data-ttu-id="9d99e-910">Una lineetta o uno spazio</span><span class="sxs-lookup"><span data-stu-id="9d99e-910">A hyphen or space</span></span> 
- <span data-ttu-id="9d99e-911">Tre cifre</span><span class="sxs-lookup"><span data-stu-id="9d99e-911">Three digits</span></span> 
- <span data-ttu-id="9d99e-912">Una lineetta o uno spazio</span><span class="sxs-lookup"><span data-stu-id="9d99e-912">A hyphen or space</span></span> 
- <span data-ttu-id="9d99e-913">Tre cifre</span><span class="sxs-lookup"><span data-stu-id="9d99e-913">Three digits</span></span>

<span data-ttu-id="9d99e-914">Non formattata: Nove cifre</span><span class="sxs-lookup"><span data-stu-id="9d99e-914">Unformatted: Nine digits</span></span>

### <a name="checksum"></a><span data-ttu-id="9d99e-915">Checksum</span><span class="sxs-lookup"><span data-stu-id="9d99e-915">Checksum</span></span>

<span data-ttu-id="9d99e-916">Sì</span><span class="sxs-lookup"><span data-stu-id="9d99e-916">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="9d99e-917">Definizione</span><span class="sxs-lookup"><span data-stu-id="9d99e-917">Definition</span></span>

<span data-ttu-id="9d99e-918">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="9d99e-918">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="9d99e-919">La funzione Func_canadian_sin restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="9d99e-919">The function Func_canadian_sin finds content that matches the pattern.</span></span>
- <span data-ttu-id="9d99e-920">Almeno due delle seguenti combinazioni:</span><span class="sxs-lookup"><span data-stu-id="9d99e-920">At least two of any combination of the following:</span></span>
    - <span data-ttu-id="9d99e-921">Viene trovata una parola chiave da Keyword_sin.</span><span class="sxs-lookup"><span data-stu-id="9d99e-921">A keyword from Keyword_sin is found.</span></span>
    - <span data-ttu-id="9d99e-922">Viene trovata una parola chiave da Keyword_sin_collaborative.</span><span class="sxs-lookup"><span data-stu-id="9d99e-922">A keyword from Keyword_sin_collaborative is found.</span></span>
    - <span data-ttu-id="9d99e-923">La funzione Func_eu_date rileva una data nel formato corretto.</span><span class="sxs-lookup"><span data-stu-id="9d99e-923">The function Func_eu_date finds a date in the right date format.</span></span>
- <span data-ttu-id="9d99e-924">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="9d99e-924">The checksum passes.</span></span>

<span data-ttu-id="9d99e-925">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="9d99e-925">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="9d99e-926">La funzione Func_unformatted_canadian_sin restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="9d99e-926">The function Func_unformatted_canadian_sin finds content that matches the pattern.</span></span>
- <span data-ttu-id="9d99e-927">Viene trovata una parola chiave da Keyword_sin.</span><span class="sxs-lookup"><span data-stu-id="9d99e-927">A keyword from Keyword_sin is found.</span></span>
- <span data-ttu-id="9d99e-928">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="9d99e-928">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="9d99e-929">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="9d99e-929">Keywords</span></span>

#### <a name="keywordsin"></a><span data-ttu-id="9d99e-930">Keyword_sin</span><span class="sxs-lookup"><span data-stu-id="9d99e-930">Keyword_sin</span></span>

- <span data-ttu-id="9d99e-931">sin</span><span class="sxs-lookup"><span data-stu-id="9d99e-931">sin</span></span> 
- <span data-ttu-id="9d99e-932">social insurance
</span><span class="sxs-lookup"><span data-stu-id="9d99e-932">social insurance</span></span> 
- <span data-ttu-id="9d99e-933">numero d'assurance sociale
</span><span class="sxs-lookup"><span data-stu-id="9d99e-933">numero d'assurance sociale</span></span> 
- <span data-ttu-id="9d99e-934">sins
</span><span class="sxs-lookup"><span data-stu-id="9d99e-934">sins</span></span> 
- <span data-ttu-id="9d99e-935">SSN</span><span class="sxs-lookup"><span data-stu-id="9d99e-935">ssn</span></span> 
- <span data-ttu-id="9d99e-936">ssns</span><span class="sxs-lookup"><span data-stu-id="9d99e-936">ssns</span></span> 
- <span data-ttu-id="9d99e-937">protezione di social networking</span><span class="sxs-lookup"><span data-stu-id="9d99e-937">social security</span></span> 
- <span data-ttu-id="9d99e-938">numero d'assurance social
</span><span class="sxs-lookup"><span data-stu-id="9d99e-938">numero d'assurance social</span></span> 
- <span data-ttu-id="9d99e-939">numero identificativo nazionale</span><span class="sxs-lookup"><span data-stu-id="9d99e-939">national identification number</span></span> 
- <span data-ttu-id="9d99e-940">
national id</span><span class="sxs-lookup"><span data-stu-id="9d99e-940">national id</span></span> 
- <span data-ttu-id="9d99e-941">sin#
</span><span class="sxs-lookup"><span data-stu-id="9d99e-941">sin#</span></span> 
- <span data-ttu-id="9d99e-942">soc ins
</span><span class="sxs-lookup"><span data-stu-id="9d99e-942">soc ins</span></span> 
- <span data-ttu-id="9d99e-943">social ins
</span><span class="sxs-lookup"><span data-stu-id="9d99e-943">social ins</span></span> 

#### <a name="keywordsincollaborative"></a><span data-ttu-id="9d99e-944">Keyword_sin_collaborative</span><span class="sxs-lookup"><span data-stu-id="9d99e-944">Keyword_sin_collaborative</span></span>

- <span data-ttu-id="9d99e-945">patente</span><span class="sxs-lookup"><span data-stu-id="9d99e-945">driver's license</span></span> 
- <span data-ttu-id="9d99e-946">patente di Guida</span><span class="sxs-lookup"><span data-stu-id="9d99e-946">drivers license</span></span> 
- <span data-ttu-id="9d99e-947">titolo della patente di Guida</span><span class="sxs-lookup"><span data-stu-id="9d99e-947">driver's licence</span></span> 
- <span data-ttu-id="9d99e-948">drivers licence</span><span class="sxs-lookup"><span data-stu-id="9d99e-948">drivers licence</span></span> 
- <span data-ttu-id="9d99e-949">DOB
</span><span class="sxs-lookup"><span data-stu-id="9d99e-949">DOB</span></span> 
- <span data-ttu-id="9d99e-950">Data di nascita</span><span class="sxs-lookup"><span data-stu-id="9d99e-950">Birthdate</span></span> 
- <span data-ttu-id="9d99e-951">Compleanno </span><span class="sxs-lookup"><span data-stu-id="9d99e-951">Birthday</span></span> 
- <span data-ttu-id="9d99e-952">Date of Birth
</span><span class="sxs-lookup"><span data-stu-id="9d99e-952">Date of Birth</span></span> 
   
## <a name="chile-identity-card-number"></a><span data-ttu-id="9d99e-953">	Cile - Numero di carta di identità</span><span class="sxs-lookup"><span data-stu-id="9d99e-953">Chile Identity Card Number</span></span>

### <a name="format"></a><span data-ttu-id="9d99e-954">Formato</span><span class="sxs-lookup"><span data-stu-id="9d99e-954">Format</span></span>

<span data-ttu-id="9d99e-955">7-8 cifre più delimitatori una cifra di controllo o lettera</span><span class="sxs-lookup"><span data-stu-id="9d99e-955">7-8 digits plus delimiters a check digit or letter</span></span>

### <a name="pattern"></a><span data-ttu-id="9d99e-956">Modello</span><span class="sxs-lookup"><span data-stu-id="9d99e-956">Pattern</span></span>

<span data-ttu-id="9d99e-957">7-8 cifre più delimitatori:</span><span class="sxs-lookup"><span data-stu-id="9d99e-957">7-8 digits plus delimiters:</span></span>
- <span data-ttu-id="9d99e-958">1-2 cifre</span><span class="sxs-lookup"><span data-stu-id="9d99e-958">1-2 digits</span></span> 
- <span data-ttu-id="9d99e-959">Un punto </span><span class="sxs-lookup"><span data-stu-id="9d99e-959">A period</span></span> 
- <span data-ttu-id="9d99e-960">Tre cifre</span><span class="sxs-lookup"><span data-stu-id="9d99e-960">Three digits</span></span> 
- <span data-ttu-id="9d99e-961">Un punto </span><span class="sxs-lookup"><span data-stu-id="9d99e-961">A period</span></span> 
- <span data-ttu-id="9d99e-962">Tre cifre</span><span class="sxs-lookup"><span data-stu-id="9d99e-962">Three digits</span></span> 
- <span data-ttu-id="9d99e-963">Un trattino</span><span class="sxs-lookup"><span data-stu-id="9d99e-963">A dash</span></span> 
- <span data-ttu-id="9d99e-964">Una cifra o una lettera (senza distinzione tra maiuscole e minuscole) che corrisponde a una cifra di controllo</span><span class="sxs-lookup"><span data-stu-id="9d99e-964">One digit or letter (not case sensitive) which is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="9d99e-965">Checksum</span><span class="sxs-lookup"><span data-stu-id="9d99e-965">Checksum</span></span>

<span data-ttu-id="9d99e-966">Sì</span><span class="sxs-lookup"><span data-stu-id="9d99e-966">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="9d99e-967">Definizione</span><span class="sxs-lookup"><span data-stu-id="9d99e-967">Definition</span></span>

<span data-ttu-id="9d99e-968">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="9d99e-968">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="9d99e-969">La funzione Func_chile_id_card consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="9d99e-969">The function Func_chile_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="9d99e-970">È possibile trovare una parola chiave da Keyword_chile_id_card.</span><span class="sxs-lookup"><span data-stu-id="9d99e-970">A keyword from Keyword_chile_id_card is found.</span></span>
- <span data-ttu-id="9d99e-971">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="9d99e-971">The checksum passes.</span></span>

<span data-ttu-id="9d99e-972">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="9d99e-972">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="9d99e-973">La funzione Func_chile_id_card consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="9d99e-973">The function Func_chile_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="9d99e-974">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="9d99e-974">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="9d99e-975">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="9d99e-975">Keywords</span></span>

#### <a name="keywordchileidcard"></a><span data-ttu-id="9d99e-976">Keyword_chile_id_card</span><span class="sxs-lookup"><span data-stu-id="9d99e-976">Keyword_chile_id_card</span></span>

- <span data-ttu-id="9d99e-977">Numero di carta d’identità
</span><span class="sxs-lookup"><span data-stu-id="9d99e-977">National Identification Number</span></span> 
- <span data-ttu-id="9d99e-978">Carta di identità</span><span class="sxs-lookup"><span data-stu-id="9d99e-978">Identity card</span></span> 
- <span data-ttu-id="9d99e-979">ID</span><span class="sxs-lookup"><span data-stu-id="9d99e-979">ID</span></span> 
- <span data-ttu-id="9d99e-980">Identificazione</span><span class="sxs-lookup"><span data-stu-id="9d99e-980">Identification</span></span> 
- <span data-ttu-id="9d99e-981">Rol Único Nacional
</span><span class="sxs-lookup"><span data-stu-id="9d99e-981">Rol Único Nacional</span></span> 
- <span data-ttu-id="9d99e-982">Correre</span><span class="sxs-lookup"><span data-stu-id="9d99e-982">RUN</span></span> 
- <span data-ttu-id="9d99e-983">Rol Único Tributario
</span><span class="sxs-lookup"><span data-stu-id="9d99e-983">Rol Único Tributario</span></span> 
- <span data-ttu-id="9d99e-984">RUT
</span><span class="sxs-lookup"><span data-stu-id="9d99e-984">RUT</span></span> 
- <span data-ttu-id="9d99e-985">Cédula de Identidad
</span><span class="sxs-lookup"><span data-stu-id="9d99e-985">Cédula de Identidad</span></span> 
- <span data-ttu-id="9d99e-986">Número De Identificación Nacional
</span><span class="sxs-lookup"><span data-stu-id="9d99e-986">Número De Identificación Nacional</span></span> 
- <span data-ttu-id="9d99e-987">Tarjeta de identificación
</span><span class="sxs-lookup"><span data-stu-id="9d99e-987">Tarjeta de identificación</span></span> 
- <span data-ttu-id="9d99e-988">Identificación
</span><span class="sxs-lookup"><span data-stu-id="9d99e-988">Identificación</span></span> 
   
## <a name="china-resident-identity-card-prc-number"></a><span data-ttu-id="9d99e-989">	Numero carta di identità per residenti in Cina (RPC)</span><span class="sxs-lookup"><span data-stu-id="9d99e-989">China Resident Identity Card (PRC) Number</span></span>

### <a name="format"></a><span data-ttu-id="9d99e-990">Formato</span><span class="sxs-lookup"><span data-stu-id="9d99e-990">Format</span></span>

<span data-ttu-id="9d99e-991">18 cifre</span><span class="sxs-lookup"><span data-stu-id="9d99e-991">18 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="9d99e-992">Modello</span><span class="sxs-lookup"><span data-stu-id="9d99e-992">Pattern</span></span>

<span data-ttu-id="9d99e-993">18 cifre:</span><span class="sxs-lookup"><span data-stu-id="9d99e-993">18 digits:</span></span>
- <span data-ttu-id="9d99e-994">Sei cifre, ovvero un codice indirizzo </span><span class="sxs-lookup"><span data-stu-id="9d99e-994">Six digits which are an address code</span></span> 
- <span data-ttu-id="9d99e-995">Otto cifre nel formato AAAAMMGG, ovvero la data di nascita </span><span class="sxs-lookup"><span data-stu-id="9d99e-995">Eight digits in the form YYYYMMDD which are the date of birth</span></span> 
- <span data-ttu-id="9d99e-996">Tre cifre, ovvero un codice di ordine </span><span class="sxs-lookup"><span data-stu-id="9d99e-996">Three digits which are an order code</span></span> 
- <span data-ttu-id="9d99e-997">Una cifra, ovvero una cifra di controllo</span><span class="sxs-lookup"><span data-stu-id="9d99e-997">One digit which is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="9d99e-998">Checksum</span><span class="sxs-lookup"><span data-stu-id="9d99e-998">Checksum</span></span>

<span data-ttu-id="9d99e-999">Sì</span><span class="sxs-lookup"><span data-stu-id="9d99e-999">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="9d99e-1000">Definizione</span><span class="sxs-lookup"><span data-stu-id="9d99e-1000">Definition</span></span>

<span data-ttu-id="9d99e-1001">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="9d99e-1001">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="9d99e-1002">La funzione Func_china_resident_id consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="9d99e-1002">The function Func_china_resident_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="9d99e-1003">È possibile trovare una parola chiave da Keyword_china_resident_id.</span><span class="sxs-lookup"><span data-stu-id="9d99e-1003">A keyword from Keyword_china_resident_id is found.</span></span>
- <span data-ttu-id="9d99e-1004">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="9d99e-1004">The checksum passes.</span></span>

<span data-ttu-id="9d99e-1005">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="9d99e-1005">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="9d99e-1006">La funzione Func_china_resident_id consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="9d99e-1006">The function Func_china_resident_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="9d99e-1007">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="9d99e-1007">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="9d99e-1008">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="9d99e-1008">Keywords</span></span>

### <a name="keywordchinaresidentid"></a><span data-ttu-id="9d99e-1009">Keyword_china_resident_id</span><span class="sxs-lookup"><span data-stu-id="9d99e-1009">Keyword_china_resident_id</span></span>

- <span data-ttu-id="9d99e-1010">Carta d’identità per residenti
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1010">Resident Identity Card</span></span> 
- <span data-ttu-id="9d99e-1011">RPC
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1011">PRC</span></span> 
- <span data-ttu-id="9d99e-1012">Carta d’identità
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1012">National Identification Card</span></span> 
- <span data-ttu-id="9d99e-1013">身份证 </span><span class="sxs-lookup"><span data-stu-id="9d99e-1013">身份证</span></span> 
- <span data-ttu-id="9d99e-1014">居民 身份证 </span><span class="sxs-lookup"><span data-stu-id="9d99e-1014">居民 身份证</span></span> 
- <span data-ttu-id="9d99e-1015">居民身份证
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1015">居民身份证</span></span> 
- <span data-ttu-id="9d99e-1016">鉴定

</span><span class="sxs-lookup"><span data-stu-id="9d99e-1016">鉴定</span></span> 
- <span data-ttu-id="9d99e-1017">身分證 </span><span class="sxs-lookup"><span data-stu-id="9d99e-1017">身分證</span></span> 
- <span data-ttu-id="9d99e-1018">居民 身份證</span><span class="sxs-lookup"><span data-stu-id="9d99e-1018">居民 身份證</span></span>
- <span data-ttu-id="9d99e-1019">鑑定 </span><span class="sxs-lookup"><span data-stu-id="9d99e-1019">鑑定</span></span> 
   
## <a name="credit-card-number"></a><span data-ttu-id="9d99e-1020">Credit Card Number</span><span class="sxs-lookup"><span data-stu-id="9d99e-1020">Credit Card Number</span></span>

### <a name="format"></a><span data-ttu-id="9d99e-1021">Formato</span><span class="sxs-lookup"><span data-stu-id="9d99e-1021">Format</span></span>

<span data-ttu-id="9d99e-1022">16 cifre che possono essere formattate o non formattato (dddddddddddddddd) e deve superare la verifica Luhn.</span><span class="sxs-lookup"><span data-stu-id="9d99e-1022">16 digits which can be formatted or unformatted (dddddddddddddddd) and must pass the Luhn test.</span></span>

### <a name="pattern"></a><span data-ttu-id="9d99e-1023">Modello</span><span class="sxs-lookup"><span data-stu-id="9d99e-1023">Pattern</span></span>

<span data-ttu-id="9d99e-1024">Modello molto complesso e solido che rileva carte di credito dei maggiori circuiti del mondo, ad esempio, Visa, MasterCard, Discover Card, JCB, American Express, nonché carte regalo e ticket restaurant.</span><span class="sxs-lookup"><span data-stu-id="9d99e-1024">Very complex and robust pattern that detects cards from all major brands worldwide, including Visa, MasterCard, Discover Card, JCB, American Express, gift cards, and diner cards.</span></span>

### <a name="checksum"></a><span data-ttu-id="9d99e-1025">Checksum</span><span class="sxs-lookup"><span data-stu-id="9d99e-1025">Checksum</span></span>

<span data-ttu-id="9d99e-1026">Yes, il checksum Luhn</span><span class="sxs-lookup"><span data-stu-id="9d99e-1026">Yes, the Luhn checksum</span></span>

### <a name="definition"></a><span data-ttu-id="9d99e-1027">Definizione</span><span class="sxs-lookup"><span data-stu-id="9d99e-1027">Definition</span></span>

<span data-ttu-id="9d99e-1028">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="9d99e-1028">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="9d99e-1029">La funzione Func_credit_card restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="9d99e-1029">The function Func_credit_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="9d99e-1030">Si verifica una delle situazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="9d99e-1030">One of the following is true:</span></span>
    - <span data-ttu-id="9d99e-1031">Viene trovata una parola chiave da Keyword_cc_verification.</span><span class="sxs-lookup"><span data-stu-id="9d99e-1031">A keyword from Keyword_cc_verification is found.</span></span>
    - <span data-ttu-id="9d99e-1032">Viene trovata una parola chiave da Keyword_cc_name.</span><span class="sxs-lookup"><span data-stu-id="9d99e-1032">A keyword from Keyword_cc_name is found.</span></span>
    - <span data-ttu-id="9d99e-1033">La funzione Func_expiration_date rileva una data nel formato corretto.</span><span class="sxs-lookup"><span data-stu-id="9d99e-1033">The function Func_expiration_date finds a date in the right date format.</span></span>
- <span data-ttu-id="9d99e-1034">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="9d99e-1034">The checksum passes.</span></span>

<span data-ttu-id="9d99e-1035">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 65%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="9d99e-1035">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="9d99e-1036">La funzione Func_credit_card restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="9d99e-1036">The function Func_credit_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="9d99e-1037">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="9d99e-1037">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="9d99e-1038">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="9d99e-1038">Keywords</span></span>

#### <a name="keywordccverification"></a><span data-ttu-id="9d99e-1039">Keyword_cc_verification</span><span class="sxs-lookup"><span data-stu-id="9d99e-1039">Keyword_cc_verification</span></span>

- <span data-ttu-id="9d99e-1040">card verification</span><span class="sxs-lookup"><span data-stu-id="9d99e-1040">card verification</span></span>
- <span data-ttu-id="9d99e-1041">card identification number</span><span class="sxs-lookup"><span data-stu-id="9d99e-1041">card identification number</span></span>
- <span data-ttu-id="9d99e-1042">cvn
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1042">cvn</span></span>
- <span data-ttu-id="9d99e-1043">cid
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1043">cid</span></span>
- <span data-ttu-id="9d99e-1044">CVC2</span><span class="sxs-lookup"><span data-stu-id="9d99e-1044">cvc2</span></span>
- <span data-ttu-id="9d99e-1045">CVV2</span><span class="sxs-lookup"><span data-stu-id="9d99e-1045">cvv2</span></span>
- <span data-ttu-id="9d99e-1046">pin block
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1046">pin block</span></span>
- <span data-ttu-id="9d99e-1047">security code
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1047">security code</span></span>
- <span data-ttu-id="9d99e-1048">security number
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1048">security number</span></span>
- <span data-ttu-id="9d99e-1049">security no
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1049">security no</span></span>
- <span data-ttu-id="9d99e-1050">issue number
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1050">issue number</span></span>
- <span data-ttu-id="9d99e-1051">issue no
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1051">issue no</span></span>
- <span data-ttu-id="9d99e-1052">cryptogramme
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1052">cryptogramme</span></span>
- <span data-ttu-id="9d99e-1053">numéro de sécurité
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1053">numéro de sécurité</span></span>
- <span data-ttu-id="9d99e-1054">numero de securite
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1054">numero de securite</span></span>
- <span data-ttu-id="9d99e-1055">kreditkartenprüfnummer
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1055">kreditkartenprüfnummer</span></span>
- <span data-ttu-id="9d99e-1056">kreditkartenprufnummer
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1056">kreditkartenprufnummer</span></span>
- <span data-ttu-id="9d99e-1057">prüfziffer
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1057">prüfziffer</span></span>
- <span data-ttu-id="9d99e-1058">prufziffer
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1058">prufziffer</span></span>
- <span data-ttu-id="9d99e-1059">sicherheits Kode</span><span class="sxs-lookup"><span data-stu-id="9d99e-1059">sicherheits Kode</span></span>
- <span data-ttu-id="9d99e-1060">sicherheitscode
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1060">sicherheitscode</span></span>
- <span data-ttu-id="9d99e-1061">sicherheitsnummer
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1061">sicherheitsnummer</span></span>
- <span data-ttu-id="9d99e-1062">verfalldatum
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1062">verfalldatum</span></span>
- <span data-ttu-id="9d99e-1063">codice di verifica
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1063">codice di verifica</span></span>
- <span data-ttu-id="9d99e-p105">cod. sicurezza
</span><span class="sxs-lookup"><span data-stu-id="9d99e-p105">cod. sicurezza</span></span>
- <span data-ttu-id="9d99e-1066">sicurezza Cod</span><span class="sxs-lookup"><span data-stu-id="9d99e-1066">cod sicurezza</span></span>
- <span data-ttu-id="9d99e-1067">
n autorizzazione</span><span class="sxs-lookup"><span data-stu-id="9d99e-1067">n autorizzazione</span></span>
- <span data-ttu-id="9d99e-1068">código
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1068">código</span></span>
- <span data-ttu-id="9d99e-1069">codigo
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1069">codigo</span></span>
- <span data-ttu-id="9d99e-p106">cod. seg
</span><span class="sxs-lookup"><span data-stu-id="9d99e-p106">cod. seg</span></span>
- <span data-ttu-id="9d99e-1072">seg Cod</span><span class="sxs-lookup"><span data-stu-id="9d99e-1072">cod seg</span></span>
- <span data-ttu-id="9d99e-1073">código de segurança
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1073">código de segurança</span></span>
- <span data-ttu-id="9d99e-1074">codigo de seguranca
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1074">codigo de seguranca</span></span>
- <span data-ttu-id="9d99e-1075">codigo de segurança
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1075">codigo de segurança</span></span>
- <span data-ttu-id="9d99e-1076">código de seguranca
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1076">código de seguranca</span></span>
- <span data-ttu-id="9d99e-p107">cód. segurança
</span><span class="sxs-lookup"><span data-stu-id="9d99e-p107">cód. segurança</span></span>
- <span data-ttu-id="9d99e-p108">Cod. seguranca cod. Segurança</span><span class="sxs-lookup"><span data-stu-id="9d99e-p108">cod. seguranca cod. segurança</span></span>
- <span data-ttu-id="9d99e-p109">cód. seguranca
</span><span class="sxs-lookup"><span data-stu-id="9d99e-p109">cód. seguranca</span></span>
- <span data-ttu-id="9d99e-1084">cód segurança</span><span class="sxs-lookup"><span data-stu-id="9d99e-1084">cód segurança</span></span>
- <span data-ttu-id="9d99e-1085">merluzzo bianco seguranca cod segurança</span><span class="sxs-lookup"><span data-stu-id="9d99e-1085">cod seguranca cod segurança</span></span>
- <span data-ttu-id="9d99e-1086">cód seguranca</span><span class="sxs-lookup"><span data-stu-id="9d99e-1086">cód seguranca</span></span>
- <span data-ttu-id="9d99e-1087">número de verificação
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1087">número de verificação</span></span>
- <span data-ttu-id="9d99e-1088">numero de verificacao
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1088">numero de verificacao</span></span>
- <span data-ttu-id="9d99e-1089">ablauf
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1089">ablauf</span></span>
- <span data-ttu-id="9d99e-1090">gültig bis
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1090">gültig bis</span></span>
- <span data-ttu-id="9d99e-1091">gültigkeitsdatum
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1091">gültigkeitsdatum</span></span>
- <span data-ttu-id="9d99e-1092">gultig bis
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1092">gultig bis</span></span>
- <span data-ttu-id="9d99e-1093">gultigkeitsdatum
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1093">gultigkeitsdatum</span></span>
- <span data-ttu-id="9d99e-1094">scadenza
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1094">scadenza</span></span>
- <span data-ttu-id="9d99e-1095">data scad
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1095">data scad</span></span>
- <span data-ttu-id="9d99e-1096">fecha de expiracion
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1096">fecha de expiracion</span></span>
- <span data-ttu-id="9d99e-1097">fecha de venc
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1097">fecha de venc</span></span>
- <span data-ttu-id="9d99e-1098">vencimiento
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1098">vencimiento</span></span>
- <span data-ttu-id="9d99e-1099">válido hasta
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1099">válido hasta</span></span>
- <span data-ttu-id="9d99e-1100">valido hasta
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1100">valido hasta</span></span>
- <span data-ttu-id="9d99e-1101">vto
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1101">vto</span></span>
- <span data-ttu-id="9d99e-1102">data de expiração
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1102">data de expiração</span></span>
- <span data-ttu-id="9d99e-1103">data de expiracao
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1103">data de expiracao</span></span>
- <span data-ttu-id="9d99e-1104">data em que expira
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1104">data em que expira</span></span>
- <span data-ttu-id="9d99e-1105">validade
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1105">validade</span></span>
- <span data-ttu-id="9d99e-1106">valor
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1106">valor</span></span>
- <span data-ttu-id="9d99e-1107">vencimento
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1107">vencimento</span></span>
- <span data-ttu-id="9d99e-1108">Venc</span><span class="sxs-lookup"><span data-stu-id="9d99e-1108">Venc</span></span> 

#### <a name="keywordccname"></a><span data-ttu-id="9d99e-1109">Keyword_cc_name</span><span class="sxs-lookup"><span data-stu-id="9d99e-1109">Keyword_cc_name</span></span>

- <span data-ttu-id="9d99e-1110">amex</span><span class="sxs-lookup"><span data-stu-id="9d99e-1110">amex</span></span>
- <span data-ttu-id="9d99e-1111">
american express</span><span class="sxs-lookup"><span data-stu-id="9d99e-1111">american express</span></span>
- <span data-ttu-id="9d99e-1112">americanexpress
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1112">americanexpress</span></span>
- <span data-ttu-id="9d99e-1113">Visa</span><span class="sxs-lookup"><span data-stu-id="9d99e-1113">Visa</span></span>
- <span data-ttu-id="9d99e-1114">mastercard
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1114">mastercard</span></span>
- <span data-ttu-id="9d99e-1115">master card
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1115">master card</span></span>
- <span data-ttu-id="9d99e-1116">
mc
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1116">mc</span></span> 
- <span data-ttu-id="9d99e-1117">mastercards</span><span class="sxs-lookup"><span data-stu-id="9d99e-1117">mastercards</span></span>
- <span data-ttu-id="9d99e-1118">
master cards</span><span class="sxs-lookup"><span data-stu-id="9d99e-1118">master cards</span></span>
- <span data-ttu-id="9d99e-1119">Associazione di Diner</span><span class="sxs-lookup"><span data-stu-id="9d99e-1119">diner's Club</span></span>
- <span data-ttu-id="9d99e-1120">diners club
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1120">diners club</span></span>
- <span data-ttu-id="9d99e-1121">dinersclub
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1121">dinersclub</span></span>
- <span data-ttu-id="9d99e-1122">discover card
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1122">discover card</span></span>
- <span data-ttu-id="9d99e-1123">discovercard
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1123">discovercard</span></span>
- <span data-ttu-id="9d99e-1124">discover cards
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1124">discover cards</span></span>
- <span data-ttu-id="9d99e-1125">JCB</span><span class="sxs-lookup"><span data-stu-id="9d99e-1125">JCB</span></span>
- <span data-ttu-id="9d99e-1126">japanese card bureau
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1126">japanese card bureau</span></span>
- <span data-ttu-id="9d99e-1127">carte blanche
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1127">carte blanche</span></span>
- <span data-ttu-id="9d99e-1128">carteblanche
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1128">carteblanche</span></span>
- <span data-ttu-id="9d99e-1129">credit card
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1129">credit card</span></span>
- <span data-ttu-id="9d99e-1130">cc #</span><span class="sxs-lookup"><span data-stu-id="9d99e-1130">cc#</span></span>
- <span data-ttu-id="9d99e-1131">cc #:</span><span class="sxs-lookup"><span data-stu-id="9d99e-1131">cc#:</span></span>
- <span data-ttu-id="9d99e-1132">
expiration date</span><span class="sxs-lookup"><span data-stu-id="9d99e-1132">expiration date</span></span>
- <span data-ttu-id="9d99e-1133">exp date
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1133">exp date</span></span>
- <span data-ttu-id="9d99e-1134">
expiry date</span><span class="sxs-lookup"><span data-stu-id="9d99e-1134">expiry date</span></span>
- <span data-ttu-id="9d99e-1135">
date d’expiration</span><span class="sxs-lookup"><span data-stu-id="9d99e-1135">date d’expiration</span></span>
- <span data-ttu-id="9d99e-1136">
date d'exp</span><span class="sxs-lookup"><span data-stu-id="9d99e-1136">date d'exp</span></span>
- <span data-ttu-id="9d99e-1137">
date expiration</span><span class="sxs-lookup"><span data-stu-id="9d99e-1137">date expiration</span></span>
- <span data-ttu-id="9d99e-1138">bank card
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1138">bank card</span></span>
- <span data-ttu-id="9d99e-1139">
bankcard</span><span class="sxs-lookup"><span data-stu-id="9d99e-1139">bankcard</span></span>
- <span data-ttu-id="9d99e-1140">card number
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1140">card number</span></span>
- <span data-ttu-id="9d99e-1141">card num
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1141">card num</span></span>
- <span data-ttu-id="9d99e-1142">cardnumber
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1142">cardnumber</span></span>
- <span data-ttu-id="9d99e-1143">cardnumbers
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1143">cardnumbers</span></span>
- <span data-ttu-id="9d99e-1144">card numbers
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1144">card numbers</span></span>
- <span data-ttu-id="9d99e-1145">creditcard
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1145">creditcard</span></span>
- <span data-ttu-id="9d99e-1146">credit cards
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1146">credit cards</span></span>
- <span data-ttu-id="9d99e-1147">creditcards
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1147">creditcards</span></span>
- <span data-ttu-id="9d99e-1148">ccn
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1148">ccn</span></span>
- <span data-ttu-id="9d99e-1149">card holder
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1149">card holder</span></span>
- <span data-ttu-id="9d99e-1150">cardholder
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1150">cardholder</span></span>
- <span data-ttu-id="9d99e-1151">card holders
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1151">card holders</span></span>
- <span data-ttu-id="9d99e-1152">cardholders
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1152">cardholders</span></span>
- <span data-ttu-id="9d99e-1153">check card
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1153">check card</span></span>
- <span data-ttu-id="9d99e-1154">checkcard
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1154">checkcard</span></span>
- <span data-ttu-id="9d99e-1155">check cards
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1155">check cards</span></span>
- <span data-ttu-id="9d99e-1156">checkcards
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1156">checkcards</span></span>
- <span data-ttu-id="9d99e-1157">debit card
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1157">debit card</span></span>
- <span data-ttu-id="9d99e-1158">debitcard
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1158">debitcard</span></span>
- <span data-ttu-id="9d99e-1159">debit cards
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1159">debit cards</span></span>
- <span data-ttu-id="9d99e-1160">debitcards
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1160">debitcards</span></span>
- <span data-ttu-id="9d99e-1161">atm card
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1161">atm card</span></span>
- <span data-ttu-id="9d99e-1162">atmcard
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1162">atmcard</span></span>
- <span data-ttu-id="9d99e-1163">atm cards
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1163">atm cards</span></span>
- <span data-ttu-id="9d99e-1164">atmcards
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1164">atmcards</span></span>
- <span data-ttu-id="9d99e-1165">
enroute</span><span class="sxs-lookup"><span data-stu-id="9d99e-1165">enroute</span></span>
- <span data-ttu-id="9d99e-1166">
en route</span><span class="sxs-lookup"><span data-stu-id="9d99e-1166">en route</span></span>
- <span data-ttu-id="9d99e-1167">card type
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1167">card type</span></span>
- <span data-ttu-id="9d99e-1168">carte bancaire
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1168">carte bancaire</span></span>
- <span data-ttu-id="9d99e-1169">carte de crédit
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1169">carte de crédit</span></span>
- <span data-ttu-id="9d99e-1170">carte de credit
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1170">carte de credit</span></span>
- <span data-ttu-id="9d99e-1171">numéro de carte
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1171">numéro de carte</span></span>
- <span data-ttu-id="9d99e-1172">numero de carte
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1172">numero de carte</span></span>
- <span data-ttu-id="9d99e-1173">nº de la carte
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1173">nº de la carte</span></span>
- <span data-ttu-id="9d99e-1174">nº de carte
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1174">nº de carte</span></span>
- <span data-ttu-id="9d99e-1175">kreditkarte
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1175">kreditkarte</span></span>
- <span data-ttu-id="9d99e-1176">karte
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1176">karte</span></span>
- <span data-ttu-id="9d99e-1177">karteninhaber
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1177">karteninhaber</span></span>
- <span data-ttu-id="9d99e-1178">karteninhabers</span><span class="sxs-lookup"><span data-stu-id="9d99e-1178">karteninhabers</span></span>
- <span data-ttu-id="9d99e-1179">kreditkarteninhaber
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1179">kreditkarteninhaber</span></span>
- <span data-ttu-id="9d99e-1180">kreditkarteninstitut
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1180">kreditkarteninstitut</span></span>
- <span data-ttu-id="9d99e-1181">kreditkartentyp
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1181">kreditkartentyp</span></span>
- <span data-ttu-id="9d99e-1182">eigentümername
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1182">eigentümername</span></span>
- <span data-ttu-id="9d99e-1183">
kartennr
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1183">kartennr</span></span> 
- <span data-ttu-id="9d99e-1184">kartennummer</span><span class="sxs-lookup"><span data-stu-id="9d99e-1184">kartennummer</span></span>
- <span data-ttu-id="9d99e-1185">
kreditkartennummer</span><span class="sxs-lookup"><span data-stu-id="9d99e-1185">kreditkartennummer</span></span>
- <span data-ttu-id="9d99e-1186">kreditkarten nummer</span><span class="sxs-lookup"><span data-stu-id="9d99e-1186">kreditkarten-nummer</span></span>
- <span data-ttu-id="9d99e-1187">carta di credito
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1187">carta di credito</span></span>
- <span data-ttu-id="9d99e-1188">carta credito
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1188">carta credito</span></span>
- <span data-ttu-id="9d99e-1189">carta</span><span class="sxs-lookup"><span data-stu-id="9d99e-1189">carta</span></span>
- <span data-ttu-id="9d99e-1190">carta n</span><span class="sxs-lookup"><span data-stu-id="9d99e-1190">n carta</span></span>
- <span data-ttu-id="9d99e-p110">nr. carta
</span><span class="sxs-lookup"><span data-stu-id="9d99e-p110">nr. carta</span></span>
- <span data-ttu-id="9d99e-1193">carta Nr</span><span class="sxs-lookup"><span data-stu-id="9d99e-1193">nr carta</span></span>
- <span data-ttu-id="9d99e-1194">numero carta
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1194">numero carta</span></span>
- <span data-ttu-id="9d99e-1195">numero della carta
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1195">numero della carta</span></span>
- <span data-ttu-id="9d99e-1196">numero di carta
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1196">numero di carta</span></span>
- <span data-ttu-id="9d99e-1197">tarjeta credito
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1197">tarjeta credito</span></span>
- <span data-ttu-id="9d99e-1198">tarjeta de credito
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1198">tarjeta de credito</span></span>
- <span data-ttu-id="9d99e-1199">
tarjeta crédito</span><span class="sxs-lookup"><span data-stu-id="9d99e-1199">tarjeta crédito</span></span>
- <span data-ttu-id="9d99e-1200">
tarjeta de crédito</span><span class="sxs-lookup"><span data-stu-id="9d99e-1200">tarjeta de crédito</span></span>
- <span data-ttu-id="9d99e-1201">tarjeta de atm
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1201">tarjeta de atm</span></span>
- <span data-ttu-id="9d99e-1202">tarjeta atm
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1202">tarjeta atm</span></span>
- <span data-ttu-id="9d99e-1203">tarjeta debito
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1203">tarjeta debito</span></span>
- <span data-ttu-id="9d99e-1204">tarjeta de debito
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1204">tarjeta de debito</span></span>
- <span data-ttu-id="9d99e-1205">
tarjeta débito</span><span class="sxs-lookup"><span data-stu-id="9d99e-1205">tarjeta débito</span></span>
- <span data-ttu-id="9d99e-1206">
tarjeta de débito</span><span class="sxs-lookup"><span data-stu-id="9d99e-1206">tarjeta de débito</span></span>
- <span data-ttu-id="9d99e-1207">nº de tarjeta
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1207">nº de tarjeta</span></span>
- <span data-ttu-id="9d99e-p111">no. de tarjeta
</span><span class="sxs-lookup"><span data-stu-id="9d99e-p111">no. de tarjeta</span></span>
- <span data-ttu-id="9d99e-1210">Nessun tarjeta de</span><span class="sxs-lookup"><span data-stu-id="9d99e-1210">no de tarjeta</span></span>
- <span data-ttu-id="9d99e-1211">numero de tarjeta
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1211">numero de tarjeta</span></span>
- <span data-ttu-id="9d99e-1212">número de tarjeta
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1212">número de tarjeta</span></span>
- <span data-ttu-id="9d99e-1213">tarjeta no
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1213">tarjeta no</span></span>
- <span data-ttu-id="9d99e-1214">tarjetahabiente
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1214">tarjetahabiente</span></span>
- <span data-ttu-id="9d99e-1215">cartão de crédito
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1215">cartão de crédito</span></span>
- <span data-ttu-id="9d99e-1216">cartão de credito
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1216">cartão de credito</span></span>
- <span data-ttu-id="9d99e-1217">cartao de crédito
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1217">cartao de crédito</span></span>
- <span data-ttu-id="9d99e-1218">cartao de credito
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1218">cartao de credito</span></span>
- <span data-ttu-id="9d99e-1219">cartão de débito
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1219">cartão de débito</span></span>
- <span data-ttu-id="9d99e-1220">○cartao de débito
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1220">cartao de débito</span></span>
- <span data-ttu-id="9d99e-1221">cartão de debito
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1221">cartão de debito</span></span>
- <span data-ttu-id="9d99e-1222">cartao de debito
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1222">cartao de debito</span></span>
- <span data-ttu-id="9d99e-1223">débito automático</span><span class="sxs-lookup"><span data-stu-id="9d99e-1223">débito automático</span></span>
- <span data-ttu-id="9d99e-1224">debito automatico
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1224">debito automatico</span></span>
- <span data-ttu-id="9d99e-1225">
número do cartão</span><span class="sxs-lookup"><span data-stu-id="9d99e-1225">número do cartão</span></span>
- <span data-ttu-id="9d99e-1226">
numero do cartão
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1226">numero do cartão</span></span> 
- <span data-ttu-id="9d99e-1227">número do cartao</span><span class="sxs-lookup"><span data-stu-id="9d99e-1227">número do cartao</span></span>
- <span data-ttu-id="9d99e-1228">
numero do cartao</span><span class="sxs-lookup"><span data-stu-id="9d99e-1228">numero do cartao</span></span>
- <span data-ttu-id="9d99e-1229">número de cartão
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1229">número de cartão</span></span>
- <span data-ttu-id="9d99e-1230">numero de cartão
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1230">numero de cartão</span></span>
- <span data-ttu-id="9d99e-1231">número de cartao
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1231">número de cartao</span></span>
- <span data-ttu-id="9d99e-1232">numero de cartao
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1232">numero de cartao</span></span>
- <span data-ttu-id="9d99e-1233">nº cartão</span><span class="sxs-lookup"><span data-stu-id="9d99e-1233">nº do cartão</span></span>
- <span data-ttu-id="9d99e-1234">nº do cartao
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1234">nº do cartao</span></span>
- <span data-ttu-id="9d99e-p112">nº. do cartão
</span><span class="sxs-lookup"><span data-stu-id="9d99e-p112">nº. do cartão</span></span>
- <span data-ttu-id="9d99e-1237">Nessun cartão</span><span class="sxs-lookup"><span data-stu-id="9d99e-1237">no do cartão</span></span>
- <span data-ttu-id="9d99e-1238">Nessun cartao</span><span class="sxs-lookup"><span data-stu-id="9d99e-1238">no do cartao</span></span>
- <span data-ttu-id="9d99e-p113">no. do cartão
</span><span class="sxs-lookup"><span data-stu-id="9d99e-p113">no. do cartão</span></span>
- <span data-ttu-id="9d99e-p114">
no. do cartao
</span><span class="sxs-lookup"><span data-stu-id="9d99e-p114">no. do cartao</span></span> 
   
## <a name="croatia-identity-card-number"></a><span data-ttu-id="9d99e-1243">	Numero di carta di identità della Croazia</span><span class="sxs-lookup"><span data-stu-id="9d99e-1243">Croatia Identity Card Number</span></span>

### <a name="format"></a><span data-ttu-id="9d99e-1244">Formato</span><span class="sxs-lookup"><span data-stu-id="9d99e-1244">Format</span></span>

<span data-ttu-id="9d99e-1245">9 cifre</span><span class="sxs-lookup"><span data-stu-id="9d99e-1245">Nine digits</span></span>

### <a name="pattern"></a><span data-ttu-id="9d99e-1246">Modello</span><span class="sxs-lookup"><span data-stu-id="9d99e-1246">Pattern</span></span>

<span data-ttu-id="9d99e-1247">9 cifre consecutive</span><span class="sxs-lookup"><span data-stu-id="9d99e-1247">Nine consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="9d99e-1248">Checksum</span><span class="sxs-lookup"><span data-stu-id="9d99e-1248">Checksum</span></span>

<span data-ttu-id="9d99e-1249">No</span><span class="sxs-lookup"><span data-stu-id="9d99e-1249">No</span></span>

### <a name="definition"></a><span data-ttu-id="9d99e-1250">Definizione</span><span class="sxs-lookup"><span data-stu-id="9d99e-1250">Definition</span></span>

<span data-ttu-id="9d99e-1251">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="9d99e-1251">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="9d99e-1252">La funzione Func_croatia_id_card consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="9d99e-1252">The function Func_croatia_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="9d99e-1253">È possibile trovare una parola chiave da Keyword_croatia_id_card.</span><span class="sxs-lookup"><span data-stu-id="9d99e-1253">A keyword from Keyword_croatia_id_card is found.</span></span>

```
<!--Croatia Identity Card Number-->
<Entity id="ff12f884-c20a-4189-b185-34c8e7258d47" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_croatia_id_card"/>
     <Match idRef="Keyword_croatia_id_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="9d99e-1254">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="9d99e-1254">Keywords</span></span>

#### <a name="keywordcroatiaidcard"></a><span data-ttu-id="9d99e-1255">Keyword_croatia_id_card</span><span class="sxs-lookup"><span data-stu-id="9d99e-1255">Keyword_croatia_id_card</span></span>

- <span data-ttu-id="9d99e-1256">Carta d’identità croata</span><span class="sxs-lookup"><span data-stu-id="9d99e-1256">Croatian identity card</span></span>
- <span data-ttu-id="9d99e-1257">Osobna iskaznica</span><span class="sxs-lookup"><span data-stu-id="9d99e-1257">Osobna iskaznica</span></span>

   
## <a name="croatia-personal-identification-oib-number"></a><span data-ttu-id="9d99e-1258">	Numero di identificazione personale (OIB) - Croazia</span><span class="sxs-lookup"><span data-stu-id="9d99e-1258">Croatia Personal Identification (OIB) Number</span></span>

### <a name="format"></a><span data-ttu-id="9d99e-1259">Formato</span><span class="sxs-lookup"><span data-stu-id="9d99e-1259">Format</span></span>

<span data-ttu-id="9d99e-1260">10 cifre</span><span class="sxs-lookup"><span data-stu-id="9d99e-1260">10 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="9d99e-1261">Modello</span><span class="sxs-lookup"><span data-stu-id="9d99e-1261">Pattern</span></span>

<span data-ttu-id="9d99e-1262">10 cifre:</span><span class="sxs-lookup"><span data-stu-id="9d99e-1262">10 digits:</span></span>
- <span data-ttu-id="9d99e-1263">Sei cifre nel formato GGMMAA, ovvero la data di nascita</span><span class="sxs-lookup"><span data-stu-id="9d99e-1263">Six digits in the form DDMMYY which are the date of birth</span></span> 
- <span data-ttu-id="9d99e-1264">Quattro cifre, dove l'ultima è una cifra di controllo</span><span class="sxs-lookup"><span data-stu-id="9d99e-1264">Four digits where the final digit is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="9d99e-1265">Checksum</span><span class="sxs-lookup"><span data-stu-id="9d99e-1265">Checksum</span></span>

<span data-ttu-id="9d99e-1266">Sì</span><span class="sxs-lookup"><span data-stu-id="9d99e-1266">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="9d99e-1267">Definizione</span><span class="sxs-lookup"><span data-stu-id="9d99e-1267">Definition</span></span>

<span data-ttu-id="9d99e-1268">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="9d99e-1268">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="9d99e-1269">La funzione Func_croatia_oib_number consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="9d99e-1269">The function Func_croatia_oib_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="9d99e-1270">È possibile trovare una parola chiave da Keyword_croatia_oib_number.</span><span class="sxs-lookup"><span data-stu-id="9d99e-1270">A keyword from Keyword_croatia_oib_number is found.</span></span>
- <span data-ttu-id="9d99e-1271">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="9d99e-1271">The checksum passes.</span></span>

<span data-ttu-id="9d99e-1272">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="9d99e-1272">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="9d99e-1273">La funzione Func_croatia_oib_number consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="9d99e-1273">The function Func_croatia_oib_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="9d99e-1274">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="9d99e-1274">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="9d99e-1275">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="9d99e-1275">Keywords</span></span>

#### <a name="keywordcroatiaoibnumber"></a><span data-ttu-id="9d99e-1276">Keyword_croatia_oib_number</span><span class="sxs-lookup"><span data-stu-id="9d99e-1276">Keyword_croatia_oib_number</span></span>

- <span data-ttu-id="9d99e-1277">Codice PIN</span><span class="sxs-lookup"><span data-stu-id="9d99e-1277">Personal Identification Number</span></span>
- <span data-ttu-id="9d99e-1278">Osobni identifikacijski broj
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1278">Osobni identifikacijski broj</span></span> 
- <span data-ttu-id="9d99e-1279">OIB
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1279">OIB</span></span> 

   
## <a name="czech-national-identity-card-number"></a><span data-ttu-id="9d99e-1280">	Numero carta d’identità (Repubblica Ceca)</span><span class="sxs-lookup"><span data-stu-id="9d99e-1280">Czech National Identity Card Number</span></span>

### <a name="format"></a><span data-ttu-id="9d99e-1281">Formato</span><span class="sxs-lookup"><span data-stu-id="9d99e-1281">Format</span></span>

<span data-ttu-id="9d99e-1282">10 cifre contenenti una barra</span><span class="sxs-lookup"><span data-stu-id="9d99e-1282">10 digits containing a forward slash</span></span>

### <a name="pattern"></a><span data-ttu-id="9d99e-1283">Modello</span><span class="sxs-lookup"><span data-stu-id="9d99e-1283">Pattern</span></span>

<span data-ttu-id="9d99e-1284">10 cifre:</span><span class="sxs-lookup"><span data-stu-id="9d99e-1284">10 digits:</span></span>
- <span data-ttu-id="9d99e-1285">Sei cifre, ovvero la data di nascita</span><span class="sxs-lookup"><span data-stu-id="9d99e-1285">Six digits which are the date of birth</span></span> 
- <span data-ttu-id="9d99e-1286">Una barra</span><span class="sxs-lookup"><span data-stu-id="9d99e-1286">A forward slash</span></span> 
- <span data-ttu-id="9d99e-1287">Quattro cifre, dove l'ultima è una cifra di controllo</span><span class="sxs-lookup"><span data-stu-id="9d99e-1287">Four digits where the final digit is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="9d99e-1288">Checksum</span><span class="sxs-lookup"><span data-stu-id="9d99e-1288">Checksum</span></span>

<span data-ttu-id="9d99e-1289">Sì</span><span class="sxs-lookup"><span data-stu-id="9d99e-1289">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="9d99e-1290">Definizione</span><span class="sxs-lookup"><span data-stu-id="9d99e-1290">Definition</span></span>

<span data-ttu-id="9d99e-p115">Un criterio DLP è 85% la certezza che è stato rilevato questo tipo di informazioni riservate se all'interno di prossimità di 300 caratteri: la funzione Func_czech_id_card consente di trovare contenuto corrispondente al formato. È possibile trovare una parola chiave da Keyword_czech_id_card. Passa il valore di checksum.</span><span class="sxs-lookup"><span data-stu-id="9d99e-p115">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The function Func_czech_id_card finds content that matches the pattern. A keyword from Keyword_czech_id_card is found. The checksum passes.</span></span>

```
<!-- Czech National Identity Card Number -->
<Entity id="60c0725a-4eb6-455b-9dda-05d8a7396497" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_czech_id_card"/>
     <Match idRef="Keyword_czech_id_card"/>
  </Pattern>
</Entity>
```


### <a name="keywords"></a><span data-ttu-id="9d99e-1294">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="9d99e-1294">Keywords</span></span>

- <span data-ttu-id="9d99e-1295">Keyword_czech_id_card</span><span class="sxs-lookup"><span data-stu-id="9d99e-1295">Keyword_czech_id_card</span></span>
- <span data-ttu-id="9d99e-1296">Carta d’identità (Repubblica ceca)</span><span class="sxs-lookup"><span data-stu-id="9d99e-1296">Czech national identity card</span></span>
- <span data-ttu-id="9d99e-1297">Občanský průka</span><span class="sxs-lookup"><span data-stu-id="9d99e-1297">Občanský průka</span></span>
   
## <a name="denmark-personal-identification-number"></a><span data-ttu-id="9d99e-1298">	Codice PIN - Danimarca</span><span class="sxs-lookup"><span data-stu-id="9d99e-1298">Denmark Personal Identification Number</span></span>

### <a name="format"></a><span data-ttu-id="9d99e-1299">Formato</span><span class="sxs-lookup"><span data-stu-id="9d99e-1299">Format</span></span>

<span data-ttu-id="9d99e-1300">10 cifre contenenti una lineetta</span><span class="sxs-lookup"><span data-stu-id="9d99e-1300">10 digits containing a hyphen</span></span>

### <a name="pattern"></a><span data-ttu-id="9d99e-1301">Modello</span><span class="sxs-lookup"><span data-stu-id="9d99e-1301">Pattern</span></span>

<span data-ttu-id="9d99e-1302">10 cifre:</span><span class="sxs-lookup"><span data-stu-id="9d99e-1302">10 digits:</span></span>
- <span data-ttu-id="9d99e-1303">Sei cifre nel formato GGMMAA, ovvero la data di nascita</span><span class="sxs-lookup"><span data-stu-id="9d99e-1303">Six digits in the format DDMMYY which are the date of birth</span></span> 
- <span data-ttu-id="9d99e-1304">Una lineetta</span><span class="sxs-lookup"><span data-stu-id="9d99e-1304">A hyphen</span></span> 
- <span data-ttu-id="9d99e-1305">Quattro cifre, dove l'ultima è una cifra di controllo</span><span class="sxs-lookup"><span data-stu-id="9d99e-1305">Four digits where the final digit is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="9d99e-1306">Checksum</span><span class="sxs-lookup"><span data-stu-id="9d99e-1306">Checksum</span></span>

<span data-ttu-id="9d99e-1307">Sì</span><span class="sxs-lookup"><span data-stu-id="9d99e-1307">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="9d99e-1308">Definizione</span><span class="sxs-lookup"><span data-stu-id="9d99e-1308">Definition</span></span>

<span data-ttu-id="9d99e-p116">Un criterio DLP è 75% la certezza che è stato rilevato questo tipo di informazioni riservate se all'interno di prossimità di 300 caratteri: l'espressione regolare Regex_denmark_id individua contenuto corrispondente al formato. È possibile trovare una parola chiave da Keyword_denmark_id. Passa il valore di checksum.</span><span class="sxs-lookup"><span data-stu-id="9d99e-p116">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The regular expression Regex_denmark_id finds content that matches the pattern. A keyword from Keyword_denmark_id is found. The checksum passes.</span></span>

```
<!-- Denmark Personal Identification Number -->
<Entity id="6c4f2fef-56e1-4c00-8093-88d7a01cf460" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_denmark_id"/>
     <Match idRef="Keyword_denmark_id"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="9d99e-1312">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="9d99e-1312">Keywords</span></span>

#### <a name="keyworddenmarkid"></a><span data-ttu-id="9d99e-1313">Keyword_denmark_id</span><span class="sxs-lookup"><span data-stu-id="9d99e-1313">Keyword_denmark_id</span></span>

- <span data-ttu-id="9d99e-1314">Codice PIN</span><span class="sxs-lookup"><span data-stu-id="9d99e-1314">Personal Identification Number</span></span>
- <span data-ttu-id="9d99e-1315">CPR</span><span class="sxs-lookup"><span data-stu-id="9d99e-1315">CPR</span></span>
- <span data-ttu-id="9d99e-1316">Det Centrale Personregister</span><span class="sxs-lookup"><span data-stu-id="9d99e-1316">Det Centrale Personregister</span></span>
- <span data-ttu-id="9d99e-1317">Personnummer</span><span class="sxs-lookup"><span data-stu-id="9d99e-1317">Personnummer</span></span>
   
## <a name="drug-enforcement-agency-dea-number"></a><span data-ttu-id="9d99e-1318">Numero della Drug Enforcement Agency (DEA)</span><span class="sxs-lookup"><span data-stu-id="9d99e-1318">Drug Enforcement Agency (DEA) Number</span></span>

### <a name="format"></a><span data-ttu-id="9d99e-1319">Formato</span><span class="sxs-lookup"><span data-stu-id="9d99e-1319">Format</span></span>

<span data-ttu-id="9d99e-1320">Due lettere seguite da 7 cifre</span><span class="sxs-lookup"><span data-stu-id="9d99e-1320">Two letters followed by seven digits</span></span>

### <a name="pattern"></a><span data-ttu-id="9d99e-1321">Modello</span><span class="sxs-lookup"><span data-stu-id="9d99e-1321">Pattern</span></span>

<span data-ttu-id="9d99e-1322">Il modello deve includere tutti gli elementi seguenti:</span><span class="sxs-lookup"><span data-stu-id="9d99e-1322">Pattern must include all of the following:</span></span>
- <span data-ttu-id="9d99e-1323">Una lettera (senza distinzione tra maiuscole/minuscole) da questo gruppo di lettere: abcdefghjklmnprstux, ovvero un codice registrante</span><span class="sxs-lookup"><span data-stu-id="9d99e-1323">One letter (not case sensitive) from this set of possible letters: abcdefghjklmnprstux, which is a registrant code</span></span> 
- <span data-ttu-id="9d99e-1324">Una lettera (senza distinzione tra maiuscole/minuscole), ovvero la prima lettera del cognome del registrante</span><span class="sxs-lookup"><span data-stu-id="9d99e-1324">One letter (not case sensitive), which is the first letter of the registrant's last name</span></span> 
- <span data-ttu-id="9d99e-1325">7 cifre e l'ultima è quella di controllo</span><span class="sxs-lookup"><span data-stu-id="9d99e-1325">Seven digits, the last of which is the check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="9d99e-1326">Checksum</span><span class="sxs-lookup"><span data-stu-id="9d99e-1326">Checksum</span></span>

<span data-ttu-id="9d99e-1327">Sì</span><span class="sxs-lookup"><span data-stu-id="9d99e-1327">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="9d99e-1328">Definizione</span><span class="sxs-lookup"><span data-stu-id="9d99e-1328">Definition</span></span>

<span data-ttu-id="9d99e-1329">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="9d99e-1329">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="9d99e-1330">La funzione Func_dea_number restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="9d99e-1330">The function Func_dea_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="9d99e-1331">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="9d99e-1331">The checksum passes.</span></span>

```
<!-- DEA Number -->
<Entity id="9a5445ad-406e-43eb-8bd7-cac17ab6d0e4" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_dea_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="9d99e-1332">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="9d99e-1332">Keywords</span></span>

<span data-ttu-id="9d99e-1333">None</span><span class="sxs-lookup"><span data-stu-id="9d99e-1333">None</span></span>

   
## <a name="eu-debit-card-number"></a><span data-ttu-id="9d99e-1334">Unione Europea - Numero di carta di debito</span><span class="sxs-lookup"><span data-stu-id="9d99e-1334">EU Debit Card Number</span></span>

### <a name="format"></a><span data-ttu-id="9d99e-1335">Formato</span><span class="sxs-lookup"><span data-stu-id="9d99e-1335">Format</span></span>

<span data-ttu-id="9d99e-1336">16 cifre</span><span class="sxs-lookup"><span data-stu-id="9d99e-1336">16 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="9d99e-1337">Modello</span><span class="sxs-lookup"><span data-stu-id="9d99e-1337">Pattern</span></span>

<span data-ttu-id="9d99e-1338">Modello molto complesso e solido</span><span class="sxs-lookup"><span data-stu-id="9d99e-1338">Very complex and robust pattern</span></span>

### <a name="checksum"></a><span data-ttu-id="9d99e-1339">Checksum</span><span class="sxs-lookup"><span data-stu-id="9d99e-1339">Checksum</span></span>

<span data-ttu-id="9d99e-1340">Sì</span><span class="sxs-lookup"><span data-stu-id="9d99e-1340">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="9d99e-1341">Definizione</span><span class="sxs-lookup"><span data-stu-id="9d99e-1341">Definition</span></span>

<span data-ttu-id="9d99e-1342">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="9d99e-1342">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="9d99e-1343">La funzione Func_eu_debit_card restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="9d99e-1343">The function Func_eu_debit_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="9d99e-1344">Si verifica almeno una delle situazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="9d99e-1344">At least one of the following is true:</span></span>
    - <span data-ttu-id="9d99e-1345">Viene trovata una parola chiave da Keyword_eu_debit_card.</span><span class="sxs-lookup"><span data-stu-id="9d99e-1345">A keyword from Keyword_eu_debit_card is found.</span></span>
    - <span data-ttu-id="9d99e-1346">Viene trovata una parola chiave da Keyword_card_terms_dict.</span><span class="sxs-lookup"><span data-stu-id="9d99e-1346">A keyword from Keyword_card_terms_dict is found.</span></span>
    - <span data-ttu-id="9d99e-1347">Viene trovata una parola chiave da Keyword_card_security_terms_dict.</span><span class="sxs-lookup"><span data-stu-id="9d99e-1347">A keyword from Keyword_card_security_terms_dict is found.</span></span>
    - <span data-ttu-id="9d99e-1348">Viene trovata una parola chiave da Keyword_card_expiration_terms_dict.</span><span class="sxs-lookup"><span data-stu-id="9d99e-1348">A keyword from Keyword_card_expiration_terms_dict is found.</span></span>
    - <span data-ttu-id="9d99e-1349">La funzione Func_expiration_date rileva una data nel formato corretto.</span><span class="sxs-lookup"><span data-stu-id="9d99e-1349">The function Func_expiration_date finds a date in the right date format.</span></span>
- <span data-ttu-id="9d99e-1350">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="9d99e-1350">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="9d99e-1351">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="9d99e-1351">Keywords</span></span>

#### <a name="keywordeudebitcard"></a><span data-ttu-id="9d99e-1352">Keyword_eu_debit_card</span><span class="sxs-lookup"><span data-stu-id="9d99e-1352">Keyword_eu_debit_card</span></span>

- <span data-ttu-id="9d99e-1353">numero di conto</span><span class="sxs-lookup"><span data-stu-id="9d99e-1353">account number</span></span> 
- <span data-ttu-id="9d99e-1354">card number
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1354">card number</span></span> 
- <span data-ttu-id="9d99e-1355">card no.
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1355">card no.</span></span> 
- <span data-ttu-id="9d99e-1356">security number
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1356">security number</span></span> 
- <span data-ttu-id="9d99e-1357">cc #</span><span class="sxs-lookup"><span data-stu-id="9d99e-1357">cc#</span></span> 

#### <a name="keywordcardtermsdict"></a><span data-ttu-id="9d99e-1358">Keyword_card_terms_dict</span><span class="sxs-lookup"><span data-stu-id="9d99e-1358">Keyword_card_terms_dict</span></span>

- <span data-ttu-id="9d99e-1359">acct nbr
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1359">acct nbr</span></span> 
- <span data-ttu-id="9d99e-1360">acct num
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1360">acct num</span></span> 
- <span data-ttu-id="9d99e-1361">acct no
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1361">acct no</span></span> 
- <span data-ttu-id="9d99e-1362">american express
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1362">american express</span></span> 
- <span data-ttu-id="9d99e-1363">americanexpress
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1363">americanexpress</span></span> 
- <span data-ttu-id="9d99e-1364">americano espresso
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1364">americano espresso</span></span> 
- <span data-ttu-id="9d99e-1365">amex</span><span class="sxs-lookup"><span data-stu-id="9d99e-1365">amex</span></span> 
- <span data-ttu-id="9d99e-1366">atm card
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1366">atm card</span></span> 
- <span data-ttu-id="9d99e-1367">atm cards
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1367">atm cards</span></span> 
- <span data-ttu-id="9d99e-1368">atm kaart
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1368">atm kaart</span></span> 
- <span data-ttu-id="9d99e-1369">atmcard
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1369">atmcard</span></span> 
- <span data-ttu-id="9d99e-1370">atmcards
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1370">atmcards</span></span> 
- <span data-ttu-id="9d99e-1371">atmkaart
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1371">atmkaart</span></span> 
- <span data-ttu-id="9d99e-1372">atmkaarten
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1372">atmkaarten</span></span> 
- <span data-ttu-id="9d99e-1373">bancontact
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1373">bancontact</span></span> 
- <span data-ttu-id="9d99e-1374">bank card
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1374">bank card</span></span> 
- <span data-ttu-id="9d99e-1375">bankkaart
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1375">bankkaart</span></span> 
- <span data-ttu-id="9d99e-1376">card holder
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1376">card holder</span></span> 
- <span data-ttu-id="9d99e-1377">card holders
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1377">card holders</span></span> 
- <span data-ttu-id="9d99e-1378">card num
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1378">card num</span></span> 
- <span data-ttu-id="9d99e-1379">card number
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1379">card number</span></span> 
- <span data-ttu-id="9d99e-1380">card numbers
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1380">card numbers</span></span> 
- <span data-ttu-id="9d99e-1381">card type
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1381">card type</span></span> 
- <span data-ttu-id="9d99e-1382">cardano numerico
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1382">cardano numerico</span></span> 
- <span data-ttu-id="9d99e-1383">cardholder
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1383">cardholder</span></span> 
- <span data-ttu-id="9d99e-1384">cardholders
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1384">cardholders</span></span> 
- <span data-ttu-id="9d99e-1385">cardnumber
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1385">cardnumber</span></span> 
- <span data-ttu-id="9d99e-1386">cardnumbers
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1386">cardnumbers</span></span> 
- <span data-ttu-id="9d99e-1387">carta bianca
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1387">carta bianca</span></span> 
- <span data-ttu-id="9d99e-1388">carta credito
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1388">carta credito</span></span> 
- <span data-ttu-id="9d99e-1389">carta di credito
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1389">carta di credito</span></span> 
- <span data-ttu-id="9d99e-1390">cartao de credito
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1390">cartao de credito</span></span> 
- <span data-ttu-id="9d99e-1391">cartao de crédito
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1391">cartao de crédito</span></span> 
- <span data-ttu-id="9d99e-1392">cartao de debito
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1392">cartao de debito</span></span> 
- <span data-ttu-id="9d99e-1393">○cartao de débito
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1393">cartao de débito</span></span> 
- <span data-ttu-id="9d99e-1394">carte bancaire
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1394">carte bancaire</span></span> 
- <span data-ttu-id="9d99e-1395">carte blanche
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1395">carte blanche</span></span> 
- <span data-ttu-id="9d99e-1396">carte bleue
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1396">carte bleue</span></span> 
- <span data-ttu-id="9d99e-1397">carte de credit
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1397">carte de credit</span></span> 
- <span data-ttu-id="9d99e-1398">carte de crédit
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1398">carte de crédit</span></span> 
- <span data-ttu-id="9d99e-1399">carte di credito
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1399">carte di credito</span></span> 
- <span data-ttu-id="9d99e-1400">carteblanche
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1400">carteblanche</span></span> 
- <span data-ttu-id="9d99e-1401">cartão de credito
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1401">cartão de credito</span></span> 
- <span data-ttu-id="9d99e-1402">cartão de crédito
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1402">cartão de crédito</span></span> 
- <span data-ttu-id="9d99e-1403">cartão de debito
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1403">cartão de debito</span></span> 
- <span data-ttu-id="9d99e-1404">cartão de débito
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1404">cartão de débito</span></span> 
- <span data-ttu-id="9d99e-1405">cb
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1405">cb</span></span> 
- <span data-ttu-id="9d99e-1406">ccn
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1406">ccn</span></span> 
- <span data-ttu-id="9d99e-1407">check card
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1407">check card</span></span> 
- <span data-ttu-id="9d99e-1408">check cards
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1408">check cards</span></span> 
- <span data-ttu-id="9d99e-1409">checkcard
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1409">checkcard</span></span>
- <span data-ttu-id="9d99e-1410">checkcards
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1410">checkcards</span></span> 
- <span data-ttu-id="9d99e-1411">chequekaart
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1411">chequekaart</span></span> 
- <span data-ttu-id="9d99e-1412">cirrus
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1412">cirrus</span></span> 
- <span data-ttu-id="9d99e-1413">cirrus-edc-maestro
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1413">cirrus-edc-maestro</span></span> 
- <span data-ttu-id="9d99e-1414">controlekaart
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1414">controlekaart</span></span> 
- <span data-ttu-id="9d99e-1415">controlekaarten
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1415">controlekaarten</span></span> 
- <span data-ttu-id="9d99e-1416">credit card
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1416">credit card</span></span> 
- <span data-ttu-id="9d99e-1417">credit cards
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1417">credit cards</span></span> 
- <span data-ttu-id="9d99e-1418">creditcard
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1418">creditcard</span></span> 
- <span data-ttu-id="9d99e-1419">creditcards
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1419">creditcards</span></span> 
- <span data-ttu-id="9d99e-1420">debetkaart
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1420">debetkaart</span></span> 
- <span data-ttu-id="9d99e-1421">debetkaarten
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1421">debetkaarten</span></span> 
- <span data-ttu-id="9d99e-1422">debit card
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1422">debit card</span></span> 
- <span data-ttu-id="9d99e-1423">debit cards
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1423">debit cards</span></span> 
- <span data-ttu-id="9d99e-1424">debitcard
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1424">debitcard</span></span> 
- <span data-ttu-id="9d99e-1425">debitcards
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1425">debitcards</span></span> 
- <span data-ttu-id="9d99e-1426">debito automatico
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1426">debito automatico</span></span> 
- <span data-ttu-id="9d99e-1427">diners club
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1427">diners club</span></span> 
- <span data-ttu-id="9d99e-1428">dinersclub
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1428">dinersclub</span></span> 
- <span data-ttu-id="9d99e-1429">Scopri</span><span class="sxs-lookup"><span data-stu-id="9d99e-1429">discover</span></span> 
- <span data-ttu-id="9d99e-1430">discover card
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1430">discover card</span></span> 
- <span data-ttu-id="9d99e-1431">discover cards
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1431">discover cards</span></span> 
- <span data-ttu-id="9d99e-1432">discovercard
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1432">discovercard</span></span> 
- <span data-ttu-id="9d99e-1433">discovercards
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1433">discovercards</span></span> 
- <span data-ttu-id="9d99e-1434">débito automático</span><span class="sxs-lookup"><span data-stu-id="9d99e-1434">débito automático</span></span>
- <span data-ttu-id="9d99e-1435">
edc
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1435">edc</span></span> 
- <span data-ttu-id="9d99e-1436">eigentümername
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1436">eigentümername</span></span> 
- <span data-ttu-id="9d99e-1437">european debit card
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1437">european debit card</span></span> 
- <span data-ttu-id="9d99e-1438">hoofdkaart
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1438">hoofdkaart</span></span> 
- <span data-ttu-id="9d99e-1439">hoofdkaarten
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1439">hoofdkaarten</span></span> 
- <span data-ttu-id="9d99e-1440">in viaggio
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1440">in viaggio</span></span> 
- <span data-ttu-id="9d99e-1441">japanese card bureau
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1441">japanese card bureau</span></span> 
- <span data-ttu-id="9d99e-1442">japanse kaartdienst
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1442">japanse kaartdienst</span></span> 
- <span data-ttu-id="9d99e-1443">jcb
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1443">jcb</span></span> 
- <span data-ttu-id="9d99e-1444">kaart
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1444">kaart</span></span> 
- <span data-ttu-id="9d99e-1445">kaart num
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1445">kaart num</span></span> 
- <span data-ttu-id="9d99e-1446">kaartaantal
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1446">kaartaantal</span></span> 
- <span data-ttu-id="9d99e-1447">kaartaantallen
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1447">kaartaantallen</span></span> 
- <span data-ttu-id="9d99e-1448">kaarthouder
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1448">kaarthouder</span></span> 
- <span data-ttu-id="9d99e-1449">kaarthouders
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1449">kaarthouders</span></span> 
- <span data-ttu-id="9d99e-1450">karte
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1450">karte</span></span>  
- <span data-ttu-id="9d99e-1451">karteninhaber
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1451">karteninhaber</span></span> 
- <span data-ttu-id="9d99e-1452">karteninhabers</span><span class="sxs-lookup"><span data-stu-id="9d99e-1452">karteninhabers</span></span>
- <span data-ttu-id="9d99e-1453">
kartennr
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1453">kartennr</span></span> 
- <span data-ttu-id="9d99e-1454">kartennummer</span><span class="sxs-lookup"><span data-stu-id="9d99e-1454">kartennummer</span></span> 
- <span data-ttu-id="9d99e-1455">kreditkarte
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1455">kreditkarte</span></span> 
- <span data-ttu-id="9d99e-1456">kreditkarten nummer</span><span class="sxs-lookup"><span data-stu-id="9d99e-1456">kreditkarten-nummer</span></span> 
- <span data-ttu-id="9d99e-1457">kreditkarteninhaber
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1457">kreditkarteninhaber</span></span> 
- <span data-ttu-id="9d99e-1458">kreditkarteninstitut
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1458">kreditkarteninstitut</span></span> 
- <span data-ttu-id="9d99e-1459">kreditkartennummer
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1459">kreditkartennummer</span></span> 
- <span data-ttu-id="9d99e-1460">kreditkartentyp
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1460">kreditkartentyp</span></span> 
- <span data-ttu-id="9d99e-1461">maestro
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1461">maestro</span></span> 
- <span data-ttu-id="9d99e-1462">master card
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1462">master card</span></span> 
- <span data-ttu-id="9d99e-1463">master cards
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1463">master cards</span></span> 
- <span data-ttu-id="9d99e-1464">mastercard
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1464">mastercard</span></span> 
- <span data-ttu-id="9d99e-1465">mastercards</span><span class="sxs-lookup"><span data-stu-id="9d99e-1465">mastercards</span></span> 
- <span data-ttu-id="9d99e-1466">MC</span><span class="sxs-lookup"><span data-stu-id="9d99e-1466">mc</span></span> 
- <span data-ttu-id="9d99e-1467">mister cash
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1467">mister cash</span></span> 
- <span data-ttu-id="9d99e-1468">carta n</span><span class="sxs-lookup"><span data-stu-id="9d99e-1468">n carta</span></span> 
- <span data-ttu-id="9d99e-1469">carta</span><span class="sxs-lookup"><span data-stu-id="9d99e-1469">carta</span></span> 
- <span data-ttu-id="9d99e-1470">Nessun tarjeta de</span><span class="sxs-lookup"><span data-stu-id="9d99e-1470">no de tarjeta</span></span> 
- <span data-ttu-id="9d99e-1471">Nessun cartao</span><span class="sxs-lookup"><span data-stu-id="9d99e-1471">no do cartao</span></span> 
- <span data-ttu-id="9d99e-1472">Nessun cartão</span><span class="sxs-lookup"><span data-stu-id="9d99e-1472">no do cartão</span></span> 
- <span data-ttu-id="9d99e-p117">no. de tarjeta
</span><span class="sxs-lookup"><span data-stu-id="9d99e-p117">no. de tarjeta</span></span> 
- <span data-ttu-id="9d99e-p118">no. do cartao
</span><span class="sxs-lookup"><span data-stu-id="9d99e-p118">no. do cartao</span></span> 
- <span data-ttu-id="9d99e-p119">no. do cartão
</span><span class="sxs-lookup"><span data-stu-id="9d99e-p119">no. do cartão</span></span> 
- <span data-ttu-id="9d99e-1479">carta Nr</span><span class="sxs-lookup"><span data-stu-id="9d99e-1479">nr carta</span></span> 
- <span data-ttu-id="9d99e-p120">nr. carta
</span><span class="sxs-lookup"><span data-stu-id="9d99e-p120">nr. carta</span></span> 
- <span data-ttu-id="9d99e-1482">numeri di scheda
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1482">numeri di scheda</span></span> 
- <span data-ttu-id="9d99e-1483">numero carta
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1483">numero carta</span></span> 
- <span data-ttu-id="9d99e-1484">numero de cartao
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1484">numero de cartao</span></span> 
- <span data-ttu-id="9d99e-1485">numero de carte
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1485">numero de carte</span></span> 
- <span data-ttu-id="9d99e-1486">numero de cartão
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1486">numero de cartão</span></span> 
- <span data-ttu-id="9d99e-1487">numero de tarjeta
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1487">numero de tarjeta</span></span>
- <span data-ttu-id="9d99e-1488">numero della carta
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1488">numero della carta</span></span> 
- <span data-ttu-id="9d99e-1489">numero di carta
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1489">numero di carta</span></span> 
- <span data-ttu-id="9d99e-1490">numero di scheda
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1490">numero di scheda</span></span> 
- <span data-ttu-id="9d99e-1491">numero do cartao
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1491">numero do cartao</span></span> 
- <span data-ttu-id="9d99e-1492">numero do cartão
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1492">numero do cartão</span></span> 
- <span data-ttu-id="9d99e-1493">numéro de carte
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1493">numéro de carte</span></span> 
- <span data-ttu-id="9d99e-1494">nº carta
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1494">nº carta</span></span> 
- <span data-ttu-id="9d99e-1495">nº de carte
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1495">nº de carte</span></span> 
- <span data-ttu-id="9d99e-1496">nº de la carte
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1496">nº de la carte</span></span> 
- <span data-ttu-id="9d99e-1497">nº de tarjeta
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1497">nº de tarjeta</span></span> 
- <span data-ttu-id="9d99e-1498">nº do cartao
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1498">nº do cartao</span></span> 
- <span data-ttu-id="9d99e-1499">nº cartão</span><span class="sxs-lookup"><span data-stu-id="9d99e-1499">nº do cartão</span></span> 
- <span data-ttu-id="9d99e-p121">nº. do cartão
</span><span class="sxs-lookup"><span data-stu-id="9d99e-p121">nº. do cartão</span></span> 
- <span data-ttu-id="9d99e-1502">número de cartao
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1502">número de cartao</span></span> 
- <span data-ttu-id="9d99e-1503">número de cartão
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1503">número de cartão</span></span> 
- <span data-ttu-id="9d99e-1504">número de tarjeta
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1504">número de tarjeta</span></span> 
- <span data-ttu-id="9d99e-1505">número do cartao</span><span class="sxs-lookup"><span data-stu-id="9d99e-1505">número do cartao</span></span> 
- <span data-ttu-id="9d99e-1506">scheda dell'assegno
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1506">scheda dell'assegno</span></span> 
- <span data-ttu-id="9d99e-1507">scheda dell'atmosfera
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1507">scheda dell'atmosfera</span></span> 
- <span data-ttu-id="9d99e-1508">scheda dell'atmosfera
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1508">scheda dell'atmosfera</span></span> 
- <span data-ttu-id="9d99e-1509">scheda della banca
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1509">scheda della banca</span></span> 
- <span data-ttu-id="9d99e-1510">scheda di controllo
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1510">scheda di controllo</span></span> 
- <span data-ttu-id="9d99e-1511">scheda di debito
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1511">scheda di debito</span></span> 
- <span data-ttu-id="9d99e-1512">scheda matrice
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1512">scheda matrice</span></span> 
- <span data-ttu-id="9d99e-1513">schede dell'atmosfera
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1513">schede dell'atmosfera</span></span> 
- <span data-ttu-id="9d99e-1514">schede di controllo
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1514">schede di controllo</span></span> 
- <span data-ttu-id="9d99e-1515">schede di debito
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1515">schede di debito</span></span> 
- <span data-ttu-id="9d99e-1516">schede matrici
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1516">schede matrici</span></span> 
- <span data-ttu-id="9d99e-1517">scoprono la scheda
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1517">scoprono la scheda</span></span> 
- <span data-ttu-id="9d99e-1518">scoprono le schede
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1518">scoprono le schede</span></span> 
- <span data-ttu-id="9d99e-1519">solo
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1519">solo</span></span> 
- <span data-ttu-id="9d99e-1520">supporti di scheda
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1520">supporti di scheda</span></span> 
- <span data-ttu-id="9d99e-1521">supporto di scheda
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1521">supporto di scheda</span></span> 
- <span data-ttu-id="9d99e-1522">parametro</span><span class="sxs-lookup"><span data-stu-id="9d99e-1522">switch</span></span> 
- <span data-ttu-id="9d99e-1523">tarjeta atm
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1523">tarjeta atm</span></span> 
- <span data-ttu-id="9d99e-1524">tarjeta credito
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1524">tarjeta credito</span></span> 
- <span data-ttu-id="9d99e-1525">tarjeta de atm
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1525">tarjeta de atm</span></span> 
- <span data-ttu-id="9d99e-1526">tarjeta de credito
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1526">tarjeta de credito</span></span> 
- <span data-ttu-id="9d99e-1527">tarjeta de debito
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1527">tarjeta de debito</span></span> 
- <span data-ttu-id="9d99e-1528">tarjeta debito
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1528">tarjeta debito</span></span> 
- <span data-ttu-id="9d99e-1529">tarjeta no
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1529">tarjeta no</span></span>
- <span data-ttu-id="9d99e-1530">tarjetahabiente
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1530">tarjetahabiente</span></span> 
- <span data-ttu-id="9d99e-1531">tipo della scheda
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1531">tipo della scheda</span></span> 
- <span data-ttu-id="9d99e-1532">ufficio giapponese della</span><span class="sxs-lookup"><span data-stu-id="9d99e-1532">ufficio giapponese della</span></span> 
- <span data-ttu-id="9d99e-1533">scheda
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1533">scheda</span></span> 
- <span data-ttu-id="9d99e-1534">v pay
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1534">v pay</span></span> 
- <span data-ttu-id="9d99e-1535">retribuzione v</span><span class="sxs-lookup"><span data-stu-id="9d99e-1535">v-pay</span></span> 
- <span data-ttu-id="9d99e-1536">visa
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1536">visa</span></span> 
- <span data-ttu-id="9d99e-1537">visa plus
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1537">visa plus</span></span> 
- <span data-ttu-id="9d99e-1538">visa electron
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1538">visa electron</span></span> 
- <span data-ttu-id="9d99e-1539">visto
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1539">visto</span></span> 
- <span data-ttu-id="9d99e-1540">visum
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1540">visum</span></span> 
- <span data-ttu-id="9d99e-1541">vpay
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1541">vpay</span></span>   

#### <a name="keywordcardsecuritytermsdict"></a><span data-ttu-id="9d99e-1542">Keyword_card_security_terms_dict</span><span class="sxs-lookup"><span data-stu-id="9d99e-1542">Keyword_card_security_terms_dict</span></span>

- <span data-ttu-id="9d99e-1543">card identification number</span><span class="sxs-lookup"><span data-stu-id="9d99e-1543">card identification number</span></span>
- <span data-ttu-id="9d99e-1544">card verification</span><span class="sxs-lookup"><span data-stu-id="9d99e-1544">card verification</span></span> 
- <span data-ttu-id="9d99e-1545">cardi la verifica
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1545">cardi la verifica</span></span> 
- <span data-ttu-id="9d99e-1546">cid
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1546">cid</span></span> 
- <span data-ttu-id="9d99e-1547">seg Cod</span><span class="sxs-lookup"><span data-stu-id="9d99e-1547">cod seg</span></span> 
- <span data-ttu-id="9d99e-1548">seguranca Cod</span><span class="sxs-lookup"><span data-stu-id="9d99e-1548">cod seguranca</span></span> 
- <span data-ttu-id="9d99e-1549">segurança Cod</span><span class="sxs-lookup"><span data-stu-id="9d99e-1549">cod segurança</span></span> 
- <span data-ttu-id="9d99e-1550">sicurezza Cod</span><span class="sxs-lookup"><span data-stu-id="9d99e-1550">cod sicurezza</span></span> 
- <span data-ttu-id="9d99e-p122">cod. seg
</span><span class="sxs-lookup"><span data-stu-id="9d99e-p122">cod. seg</span></span> 
- <span data-ttu-id="9d99e-p123">cod. seguranca
</span><span class="sxs-lookup"><span data-stu-id="9d99e-p123">cod. seguranca</span></span> 
- <span data-ttu-id="9d99e-p124">cod. segurança
</span><span class="sxs-lookup"><span data-stu-id="9d99e-p124">cod. segurança</span></span> 
- <span data-ttu-id="9d99e-p125">cod. sicurezza
</span><span class="sxs-lookup"><span data-stu-id="9d99e-p125">cod. sicurezza</span></span> 
- <span data-ttu-id="9d99e-1559">codice di sicurezza
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1559">codice di sicurezza</span></span> 
- <span data-ttu-id="9d99e-1560">codice di verifica
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1560">codice di verifica</span></span> 
- <span data-ttu-id="9d99e-1561">codigo
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1561">codigo</span></span> 
- <span data-ttu-id="9d99e-1562">codigo de seguranca
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1562">codigo de seguranca</span></span> 
- <span data-ttu-id="9d99e-1563">codigo de segurança
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1563">codigo de segurança</span></span> 
- <span data-ttu-id="9d99e-1564">crittogramma
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1564">crittogramma</span></span> 
- <span data-ttu-id="9d99e-1565">cryptogram
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1565">cryptogram</span></span> 
- <span data-ttu-id="9d99e-1566">cryptogramme
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1566">cryptogramme</span></span> 
- <span data-ttu-id="9d99e-1567">cv2</span><span class="sxs-lookup"><span data-stu-id="9d99e-1567">cv2</span></span> 
- <span data-ttu-id="9d99e-1568">cvc
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1568">cvc</span></span> 
- <span data-ttu-id="9d99e-1569">CVC2</span><span class="sxs-lookup"><span data-stu-id="9d99e-1569">cvc2</span></span> 
- <span data-ttu-id="9d99e-1570">cvn
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1570">cvn</span></span> 
- <span data-ttu-id="9d99e-1571">cvv
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1571">cvv</span></span> 
- <span data-ttu-id="9d99e-1572">CVV2</span><span class="sxs-lookup"><span data-stu-id="9d99e-1572">cvv2</span></span> 
- <span data-ttu-id="9d99e-1573">cód seguranca</span><span class="sxs-lookup"><span data-stu-id="9d99e-1573">cód seguranca</span></span> 
- <span data-ttu-id="9d99e-1574">cód segurança</span><span class="sxs-lookup"><span data-stu-id="9d99e-1574">cód segurança</span></span> 
- <span data-ttu-id="9d99e-p126">cód. seguranca
</span><span class="sxs-lookup"><span data-stu-id="9d99e-p126">cód. seguranca</span></span> 
- <span data-ttu-id="9d99e-p127">cód. segurança
</span><span class="sxs-lookup"><span data-stu-id="9d99e-p127">cód. segurança</span></span> 
- <span data-ttu-id="9d99e-1579">código
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1579">código</span></span> 
- <span data-ttu-id="9d99e-1580">código de seguranca
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1580">código de seguranca</span></span> 
- <span data-ttu-id="9d99e-1581">código de segurança
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1581">código de segurança</span></span> 
- <span data-ttu-id="9d99e-1582">de kaart controle
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1582">de kaart controle</span></span> 
- <span data-ttu-id="9d99e-1583">geeft nr uit
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1583">geeft nr uit</span></span> 
- <span data-ttu-id="9d99e-1584">issue no
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1584">issue no</span></span> 
- <span data-ttu-id="9d99e-1585">issue number
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1585">issue number</span></span> 
- <span data-ttu-id="9d99e-1586">kaartidentificatienummer
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1586">kaartidentificatienummer</span></span> 
- <span data-ttu-id="9d99e-1587">kreditkartenprufnummer
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1587">kreditkartenprufnummer</span></span> 
- <span data-ttu-id="9d99e-1588">kreditkartenprüfnummer
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1588">kreditkartenprüfnummer</span></span> 
- <span data-ttu-id="9d99e-1589">kwestieaantal
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1589">kwestieaantal</span></span> 
- <span data-ttu-id="9d99e-p128">no. dell'edizione
</span><span class="sxs-lookup"><span data-stu-id="9d99e-p128">no. dell'edizione</span></span> 
- <span data-ttu-id="9d99e-p129">no. di sicurezza
</span><span class="sxs-lookup"><span data-stu-id="9d99e-p129">no. di sicurezza</span></span> 
- <span data-ttu-id="9d99e-1594">numero de securite
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1594">numero de securite</span></span> 
- <span data-ttu-id="9d99e-1595">numero de verificacao
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1595">numero de verificacao</span></span> 
- <span data-ttu-id="9d99e-1596">numero dell'edizione
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1596">numero dell'edizione</span></span> 
- <span data-ttu-id="9d99e-1597">numero di identificazione della</span><span class="sxs-lookup"><span data-stu-id="9d99e-1597">numero di identificazione della</span></span> 
- <span data-ttu-id="9d99e-1598">scheda
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1598">scheda</span></span> 
- <span data-ttu-id="9d99e-1599">numero di sicurezza
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1599">numero di sicurezza</span></span> 
- <span data-ttu-id="9d99e-1600">numero van veiligheid
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1600">numero van veiligheid</span></span> 
- <span data-ttu-id="9d99e-1601">numéro de sécurité
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1601">numéro de sécurité</span></span> 
- <span data-ttu-id="9d99e-1602">nº autorizzazione
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1602">nº autorizzazione</span></span> 
- <span data-ttu-id="9d99e-1603">número de verificação
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1603">número de verificação</span></span> 
- <span data-ttu-id="9d99e-1604">perno il blocco
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1604">perno il blocco</span></span> 
- <span data-ttu-id="9d99e-1605">pin block
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1605">pin block</span></span> 
- <span data-ttu-id="9d99e-1606">prufziffer
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1606">prufziffer</span></span> 
- <span data-ttu-id="9d99e-1607">prüfziffer
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1607">prüfziffer</span></span> 
- <span data-ttu-id="9d99e-1608">security code
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1608">security code</span></span> 
- <span data-ttu-id="9d99e-1609">security no
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1609">security no</span></span> 
- <span data-ttu-id="9d99e-1610">security number
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1610">security number</span></span> 
- <span data-ttu-id="9d99e-1611">sicherheits kode
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1611">sicherheits kode</span></span> 
- <span data-ttu-id="9d99e-1612">sicherheitscode
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1612">sicherheitscode</span></span> 
- <span data-ttu-id="9d99e-1613">sicherheitsnummer
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1613">sicherheitsnummer</span></span> 
- <span data-ttu-id="9d99e-1614">speldblok
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1614">speldblok</span></span> 
- <span data-ttu-id="9d99e-1615">veiligheid nr
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1615">veiligheid nr</span></span> 
- <span data-ttu-id="9d99e-1616">veiligheidsaantal
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1616">veiligheidsaantal</span></span> 
- <span data-ttu-id="9d99e-1617">veiligheidscode
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1617">veiligheidscode</span></span> 
- <span data-ttu-id="9d99e-1618">veiligheidsnummer
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1618">veiligheidsnummer</span></span> 
- <span data-ttu-id="9d99e-1619">verfalldatum
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1619">verfalldatum</span></span> 

#### <a name="keywordcardexpirationtermsdict"></a><span data-ttu-id="9d99e-1620">Keyword_card_expiration_terms_dict</span><span class="sxs-lookup"><span data-stu-id="9d99e-1620">Keyword_card_expiration_terms_dict</span></span>

- <span data-ttu-id="9d99e-1621">ablauf
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1621">ablauf</span></span> 
- <span data-ttu-id="9d99e-1622">data de expiracao
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1622">data de expiracao</span></span> 
- <span data-ttu-id="9d99e-1623">data de expiração
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1623">data de expiração</span></span> 
- <span data-ttu-id="9d99e-1624">data del exp
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1624">data del exp</span></span> 
- <span data-ttu-id="9d99e-1625">data di exp
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1625">data di exp</span></span> 
- <span data-ttu-id="9d99e-1626">data di scadenza
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1626">data di scadenza</span></span> 
- <span data-ttu-id="9d99e-1627">data em que expira
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1627">data em que expira</span></span> 
- <span data-ttu-id="9d99e-1628">data scad
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1628">data scad</span></span> 
- <span data-ttu-id="9d99e-1629">data scadenza
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1629">data scadenza</span></span> 
- <span data-ttu-id="9d99e-1630">date de validité
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1630">date de validité</span></span> 
- <span data-ttu-id="9d99e-1631">datum afloop
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1631">datum afloop</span></span> 
- <span data-ttu-id="9d99e-1632">datum van exp
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1632">datum van exp</span></span> 
- <span data-ttu-id="9d99e-1633">de afloop
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1633">de afloop</span></span> 
- <span data-ttu-id="9d99e-1634">espira
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1634">espira</span></span> 
- <span data-ttu-id="9d99e-1635">espira
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1635">espira</span></span> 
- <span data-ttu-id="9d99e-1636">exp date
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1636">exp date</span></span> 
- <span data-ttu-id="9d99e-1637">exp datum
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1637">exp datum</span></span> 
- <span data-ttu-id="9d99e-1638">scadenza</span><span class="sxs-lookup"><span data-stu-id="9d99e-1638">expiration</span></span> 
- <span data-ttu-id="9d99e-1639">expire
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1639">expire</span></span> 
- <span data-ttu-id="9d99e-1640">expires
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1640">expires</span></span> 
- <span data-ttu-id="9d99e-1641">expiry
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1641">expiry</span></span> 
- <span data-ttu-id="9d99e-1642">fecha de expiracion
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1642">fecha de expiracion</span></span> 
- <span data-ttu-id="9d99e-1643">fecha de venc
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1643">fecha de venc</span></span> 
- <span data-ttu-id="9d99e-1644">gultig bis
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1644">gultig bis</span></span> 
- <span data-ttu-id="9d99e-1645">gultigkeitsdatum
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1645">gultigkeitsdatum</span></span> 
- <span data-ttu-id="9d99e-1646">gültig bis
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1646">gültig bis</span></span> 
- <span data-ttu-id="9d99e-1647">gültigkeitsdatum
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1647">gültigkeitsdatum</span></span> 
- <span data-ttu-id="9d99e-1648">la scadenza
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1648">la scadenza</span></span> 
- <span data-ttu-id="9d99e-1649">scadenza
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1649">scadenza</span></span> 
- <span data-ttu-id="9d99e-1650">valable
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1650">valable</span></span> 
- <span data-ttu-id="9d99e-1651">validade
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1651">validade</span></span> 
- <span data-ttu-id="9d99e-1652">valido hasta
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1652">valido hasta</span></span> 
- <span data-ttu-id="9d99e-1653">valor
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1653">valor</span></span> 
- <span data-ttu-id="9d99e-1654">venc
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1654">venc</span></span> 
- <span data-ttu-id="9d99e-1655">vencimento
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1655">vencimento</span></span> 
- <span data-ttu-id="9d99e-1656">vencimiento
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1656">vencimiento</span></span> 
- <span data-ttu-id="9d99e-1657">verloopt
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1657">verloopt</span></span> 
- <span data-ttu-id="9d99e-1658">vervaldag
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1658">vervaldag</span></span> 
- <span data-ttu-id="9d99e-1659">vervaldatum
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1659">vervaldatum</span></span> 
- <span data-ttu-id="9d99e-1660">vto
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1660">vto</span></span> 
- <span data-ttu-id="9d99e-1661">válido hasta
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1661">válido hasta</span></span> 
   
## <a name="eu-drivers-license-number"></a><span data-ttu-id="9d99e-1662">Numero della patente di Guida di Unione europea</span><span class="sxs-lookup"><span data-stu-id="9d99e-1662">EU Driver's License Number</span></span>

<span data-ttu-id="9d99e-1663">Per ulteriori informazioni, vedere [tipo di informazione sensibile numero della patente di Guida di Unione europea](eu-driver-s-license-number.md).</span><span class="sxs-lookup"><span data-stu-id="9d99e-1663">To learn more, see [EU Driver's License Number sensitive information type](eu-driver-s-license-number.md).</span></span>
  
## <a name="eu-national-identification-number"></a><span data-ttu-id="9d99e-1664">Numero di identificazione dell'Unione europea nazionale</span><span class="sxs-lookup"><span data-stu-id="9d99e-1664">EU National Identification Number</span></span>

<span data-ttu-id="9d99e-1665">Per ulteriori informazioni, vedere [il tipo di informazione sensibile nazionale numero di identificazione dell'Unione europea](eu-national-identification-number.md).</span><span class="sxs-lookup"><span data-stu-id="9d99e-1665">To learn more, see [EU National Identification Number sensitive information type](eu-national-identification-number.md).</span></span>
  
## <a name="eu-passport-number"></a><span data-ttu-id="9d99e-1666">Numero di passaporto UE</span><span class="sxs-lookup"><span data-stu-id="9d99e-1666">EU Passport Number</span></span>

<span data-ttu-id="9d99e-1667">Per ulteriori informazioni, vedere [il numero di passaporto UE tipo di informazioni sensibili](eu-passport-number.md).</span><span class="sxs-lookup"><span data-stu-id="9d99e-1667">To learn more, see [EU Passport Number sensitive information type](eu-passport-number.md).</span></span>
  
## <a name="eu-social-security-number-or-equivalent-id"></a><span data-ttu-id="9d99e-1668">ID di numero di previdenza sociale UE o equivalente</span><span class="sxs-lookup"><span data-stu-id="9d99e-1668">EU Social Security Number or Equivalent ID</span></span>

<span data-ttu-id="9d99e-1669">Per ulteriori informazioni, vedere [il numero di previdenza sociale UE o tipo di informazioni riservate ID equivalenti](eu-social-security-number-or-equivalent-id.md).</span><span class="sxs-lookup"><span data-stu-id="9d99e-1669">To learn more, see [EU Social Security Number or Equivalent ID sensitive information type](eu-social-security-number-or-equivalent-id.md).</span></span>
  
## <a name="eu-tax-identification-number"></a><span data-ttu-id="9d99e-1670">Numero di identificazione fiscale UE</span><span class="sxs-lookup"><span data-stu-id="9d99e-1670">EU Tax Identification Number</span></span>

<span data-ttu-id="9d99e-1671">Per ulteriori informazioni, vedere [il tipo di informazione sensibile UE imposte Identification Number](eu-tax-identification-number.md).</span><span class="sxs-lookup"><span data-stu-id="9d99e-1671">To learn more, see [EU Tax Identification Number sensitive information type](eu-tax-identification-number.md).</span></span>
  
## <a name="finland-national-id"></a><span data-ttu-id="9d99e-1672">Finland National ID</span><span class="sxs-lookup"><span data-stu-id="9d99e-1672">Finland National ID</span></span>

### <a name="format"></a><span data-ttu-id="9d99e-1673">Formato</span><span class="sxs-lookup"><span data-stu-id="9d99e-1673">Format</span></span>

<span data-ttu-id="9d99e-1674">6 cifre, un carattere di indicazione del secolo, tre cifre più una cifra di controllo</span><span class="sxs-lookup"><span data-stu-id="9d99e-1674">Six digits plus a character indicating a century plus three digits plus a check digit</span></span>

### <a name="pattern"></a><span data-ttu-id="9d99e-1675">Modello</span><span class="sxs-lookup"><span data-stu-id="9d99e-1675">Pattern</span></span>

<span data-ttu-id="9d99e-1676">Il modello deve includere tutti gli elementi seguenti:</span><span class="sxs-lookup"><span data-stu-id="9d99e-1676">Pattern must include all of the following:</span></span>
- <span data-ttu-id="9d99e-1677">Sei cifre nel formato DDMMYY che corrisponde alla data di nascita</span><span class="sxs-lookup"><span data-stu-id="9d99e-1677">Six digits in the format format DDMMYY which are a date of birth</span></span> 
- <span data-ttu-id="9d99e-1678">Indicatore del secolo ("-", "+" o "a")</span><span class="sxs-lookup"><span data-stu-id="9d99e-1678">Century marker (either '-', '+' or 'a')</span></span> 
- <span data-ttu-id="9d99e-1679">Codice PIN di 3 cifre</span><span class="sxs-lookup"><span data-stu-id="9d99e-1679">Three-digit personal identification number</span></span> 
- <span data-ttu-id="9d99e-1680">Una cifra o una lettera (con distinzione tra maiuscole/minuscole) che corrisponde a una cifra di controllo</span><span class="sxs-lookup"><span data-stu-id="9d99e-1680">A digit or letter (case insensitive) which is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="9d99e-1681">Checksum</span><span class="sxs-lookup"><span data-stu-id="9d99e-1681">Checksum</span></span>

<span data-ttu-id="9d99e-1682">Sì</span><span class="sxs-lookup"><span data-stu-id="9d99e-1682">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="9d99e-1683">Definizione</span><span class="sxs-lookup"><span data-stu-id="9d99e-1683">Definition</span></span>

<span data-ttu-id="9d99e-1684">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="9d99e-1684">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="9d99e-1685">La funzione Func_finnish_national_id restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="9d99e-1685">The function Func_finnish_national_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="9d99e-1686">Viene trovata una parola chiave da Keyword_finnish_national_id.</span><span class="sxs-lookup"><span data-stu-id="9d99e-1686">A keyword from Keyword_finnish_national_id is found.</span></span>
- <span data-ttu-id="9d99e-1687">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="9d99e-1687">The checksum passes.</span></span>

```
<!-- Finnish National ID-->
<Entity id="338FD995-4CB5-4F87-AD35-79BD1DD926C1" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_finnish_national_id" />
          <Match idRef="Keyword_finnish_national_id" />
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="9d99e-1688">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="9d99e-1688">Keywords</span></span>

- <span data-ttu-id="9d99e-1689">Keyword_finnish_national_id</span><span class="sxs-lookup"><span data-stu-id="9d99e-1689">Keyword_finnish_national_id</span></span>
- <span data-ttu-id="9d99e-1690">

Sosiaaliturvatunnus</span><span class="sxs-lookup"><span data-stu-id="9d99e-1690">Sosiaaliturvatunnus</span></span>
- <span data-ttu-id="9d99e-1691">SOTU Henkilötunnus HETU</span><span class="sxs-lookup"><span data-stu-id="9d99e-1691">SOTU Henkilötunnus HETU</span></span>
- <span data-ttu-id="9d99e-1692">Personbeteckning</span><span class="sxs-lookup"><span data-stu-id="9d99e-1692">Personbeteckning</span></span>
- <span data-ttu-id="9d99e-1693">Personnummer</span><span class="sxs-lookup"><span data-stu-id="9d99e-1693">Personnummer</span></span>
   
## <a name="finland-passport-number"></a><span data-ttu-id="9d99e-1694">Finlandia - Numero di passaporto</span><span class="sxs-lookup"><span data-stu-id="9d99e-1694">Finland Passport Number</span></span>

<span data-ttu-id="9d99e-p130">Combinazione di nove lettere e cifre motivo combinazione dei nove lettere e numeri in formato: criteri di due lettere (non maiuscole/minuscole) sette cifre Checksum No definizione A DLP sono la certezza che è stato rilevato questo tipo di informazioni riservate se al 75%, compreso tra un prossimità di 300 caratteri: l'espressione regolare Regex_finland_passport_number individua contenuto corrispondente al formato. È possibile trovare una parola chiave da Keyword_finland_passport_number. <!-- Finland Passport Number --> 
 <Entity id="d1685ac3-1d3a-40f8-8198-32ef5669c7a5" recommendedConfidence="75" patternsProximity="300"> <Pattern confidenceLevel="75"> <IdMatch idRef="Regex_finland_passport_number"/> <Match idRef="Keyword_finland_passport_number"/> </Pattern> 
 </Entity> Passi Passport Keyword_finland_passport_number di parole chiave</span><span class="sxs-lookup"><span data-stu-id="9d99e-p130">Format Combination of nine letters and digits Pattern Combination of nine letters and digits: Two letters (not case sensitive) Seven digits Checksum No Definition A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The regular expression Regex_finland_passport_number finds content that matches the pattern. A keyword from Keyword_finland_passport_number is found. <!-- Finland Passport Number -->
<Entity id="d1685ac3-1d3a-40f8-8198-32ef5669c7a5" recommendedConfidence="75" patternsProximity="300"> <Pattern confidenceLevel="75"> <IdMatch idRef="Regex_finland_passport_number"/> <Match idRef="Keyword_finland_passport_number"/> </Pattern>
</Entity> Keywords Keyword_finland_passport_number Passport Passi</span></span>
   
## <a name="france-drivers-license-number"></a><span data-ttu-id="9d99e-1699">Francia - Numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="9d99e-1699">France Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="9d99e-1700">Formato</span><span class="sxs-lookup"><span data-stu-id="9d99e-1700">Format</span></span>

<span data-ttu-id="9d99e-1701">12 cifre</span><span class="sxs-lookup"><span data-stu-id="9d99e-1701">12 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="9d99e-1702">Modello</span><span class="sxs-lookup"><span data-stu-id="9d99e-1702">Pattern</span></span>

<span data-ttu-id="9d99e-1703">12 cifre con convalida per scontare modelli analoghi, ad esempio, quello dei numeri telefonici francesi</span><span class="sxs-lookup"><span data-stu-id="9d99e-1703">12 digits with validation to discount similar patterns such as French telephone numbers</span></span>

### <a name="checksum"></a><span data-ttu-id="9d99e-1704">Checksum</span><span class="sxs-lookup"><span data-stu-id="9d99e-1704">Checksum</span></span>

<span data-ttu-id="9d99e-1705">No</span><span class="sxs-lookup"><span data-stu-id="9d99e-1705">No</span></span>

### <a name="definition"></a><span data-ttu-id="9d99e-1706">Definizione</span><span class="sxs-lookup"><span data-stu-id="9d99e-1706">Definition</span></span>

<span data-ttu-id="9d99e-1707">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="9d99e-1707">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="9d99e-1708">La funzione Func_french_drivers_license restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="9d99e-1708">The function Func_french_drivers_license finds content that matches the pattern.</span></span>
- <span data-ttu-id="9d99e-1709">Si verifica almeno una delle situazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="9d99e-1709">At least one of the following is true:</span></span>
- <span data-ttu-id="9d99e-1710">Viene trovata una parola chiave da Keyword_french_drivers_license.</span><span class="sxs-lookup"><span data-stu-id="9d99e-1710">A keyword from Keyword_french_drivers_license is found.</span></span>
- <span data-ttu-id="9d99e-1711">La funzione Func_eu_date rileva una data nel formato corretto.</span><span class="sxs-lookup"><span data-stu-id="9d99e-1711">The function Func_eu_date finds a date in the right date format.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="9d99e-1712">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="9d99e-1712">Keywords</span></span>

#### <a name="keywordfrenchdriverslicense"></a><span data-ttu-id="9d99e-1713">Keyword_french_drivers_license</span><span class="sxs-lookup"><span data-stu-id="9d99e-1713">Keyword_french_drivers_license</span></span>

- <span data-ttu-id="9d99e-1714">drivers licence</span><span class="sxs-lookup"><span data-stu-id="9d99e-1714">drivers licence</span></span>
- <span data-ttu-id="9d99e-1715">
drivers license</span><span class="sxs-lookup"><span data-stu-id="9d99e-1715">drivers license</span></span>
- <span data-ttu-id="9d99e-1716">driving licence
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1716">driving licence</span></span>
- <span data-ttu-id="9d99e-1717">le licenze</span><span class="sxs-lookup"><span data-stu-id="9d99e-1717">driving license</span></span>
- <span data-ttu-id="9d99e-1718">
permis de conduire</span><span class="sxs-lookup"><span data-stu-id="9d99e-1718">permis de conduire</span></span>
- <span data-ttu-id="9d99e-1719">
licence number</span><span class="sxs-lookup"><span data-stu-id="9d99e-1719">licence number</span></span>
- <span data-ttu-id="9d99e-1720">
license number</span><span class="sxs-lookup"><span data-stu-id="9d99e-1720">license number</span></span>
- <span data-ttu-id="9d99e-1721">
licence numbers</span><span class="sxs-lookup"><span data-stu-id="9d99e-1721">licence numbers</span></span>
- <span data-ttu-id="9d99e-1722">

license numbers</span><span class="sxs-lookup"><span data-stu-id="9d99e-1722">license numbers</span></span>

## <a name="france-national-id-card-cni"></a><span data-ttu-id="9d99e-1723">Francia - Carta d'identità nazionale (CNI)</span><span class="sxs-lookup"><span data-stu-id="9d99e-1723">France National ID Card (CNI)</span></span>

### <a name="format"></a><span data-ttu-id="9d99e-1724">Formato</span><span class="sxs-lookup"><span data-stu-id="9d99e-1724">Format</span></span>

<span data-ttu-id="9d99e-1725">12 cifre</span><span class="sxs-lookup"><span data-stu-id="9d99e-1725">12 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="9d99e-1726">Modello</span><span class="sxs-lookup"><span data-stu-id="9d99e-1726">Pattern</span></span>

<span data-ttu-id="9d99e-1727">12 cifre</span><span class="sxs-lookup"><span data-stu-id="9d99e-1727">12 digits</span></span>

### <a name="checksum"></a><span data-ttu-id="9d99e-1728">Checksum</span><span class="sxs-lookup"><span data-stu-id="9d99e-1728">Checksum</span></span>

<span data-ttu-id="9d99e-1729">No</span><span class="sxs-lookup"><span data-stu-id="9d99e-1729">No</span></span>

### <a name="definition"></a><span data-ttu-id="9d99e-1730">Definizione</span><span class="sxs-lookup"><span data-stu-id="9d99e-1730">Definition</span></span>

<span data-ttu-id="9d99e-1731">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 65%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="9d99e-1731">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="9d99e-1732">L'espressione regolare Regex_france_cni restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="9d99e-1732">The regular expression Regex_france_cni finds content that matches the pattern.</span></span>

```
<!-- France CNI -->
<Entity id="f741ac74-1bc0-4665-b69b-f0c7f927c0c4" patternsProximity="300" recommendedConfidence="65">
  <Pattern confidenceLevel="65">
        <IdMatch idRef="Regex_france_cni" />
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="9d99e-1733">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="9d99e-1733">Keywords</span></span>

<span data-ttu-id="9d99e-1734">None</span><span class="sxs-lookup"><span data-stu-id="9d99e-1734">None</span></span>
   
## <a name="france-passport-number"></a><span data-ttu-id="9d99e-1735">Francia - Numero di passaporto</span><span class="sxs-lookup"><span data-stu-id="9d99e-1735">France Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="9d99e-1736">Formato</span><span class="sxs-lookup"><span data-stu-id="9d99e-1736">Format</span></span>

<span data-ttu-id="9d99e-1737">Nove cifre e lettere</span><span class="sxs-lookup"><span data-stu-id="9d99e-1737">Nine digits and letters</span></span>

### <a name="pattern"></a><span data-ttu-id="9d99e-1738">Modello</span><span class="sxs-lookup"><span data-stu-id="9d99e-1738">Pattern</span></span>

<span data-ttu-id="9d99e-1739">Nove cifre e lettere:</span><span class="sxs-lookup"><span data-stu-id="9d99e-1739">Nine digits and letters:</span></span>
- <span data-ttu-id="9d99e-1740">Due cifre</span><span class="sxs-lookup"><span data-stu-id="9d99e-1740">Two digits</span></span> 
- <span data-ttu-id="9d99e-1741">Due lettere (senza distinzione tra maiuscole/minuscole)</span><span class="sxs-lookup"><span data-stu-id="9d99e-1741">Two letters (not case sensitive)</span></span> 
- <span data-ttu-id="9d99e-1742">Cinque cifre</span><span class="sxs-lookup"><span data-stu-id="9d99e-1742">Five digits</span></span>

### <a name="checksum"></a><span data-ttu-id="9d99e-1743">Checksum</span><span class="sxs-lookup"><span data-stu-id="9d99e-1743">Checksum</span></span>

<span data-ttu-id="9d99e-1744">No</span><span class="sxs-lookup"><span data-stu-id="9d99e-1744">No</span></span>

### <a name="definition"></a><span data-ttu-id="9d99e-1745">Definizione</span><span class="sxs-lookup"><span data-stu-id="9d99e-1745">Definition</span></span>

<span data-ttu-id="9d99e-1746">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="9d99e-1746">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="9d99e-1747">La funzione Func_fr_passport restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="9d99e-1747">The function Func_fr_passport finds content that matches the pattern.</span></span>
- <span data-ttu-id="9d99e-1748">Viene trovata una parola chiave da Keyword_passport.</span><span class="sxs-lookup"><span data-stu-id="9d99e-1748">A keyword from Keyword_passport is found.</span></span>

```
<!-- France Passport Number -->
<Entity id="3008b884-8c8c-4cd8-a289-99f34fc7ff5d" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_fr_passport" />
        <Match idRef="Keyword_passport" />
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="9d99e-1749">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="9d99e-1749">Keywords</span></span>

#### <a name="keywordpassport"></a><span data-ttu-id="9d99e-1750">Keyword_passport</span><span class="sxs-lookup"><span data-stu-id="9d99e-1750">Keyword_passport</span></span>

- <span data-ttu-id="9d99e-1751">Passport Number</span><span class="sxs-lookup"><span data-stu-id="9d99e-1751">Passport Number</span></span>
- <span data-ttu-id="9d99e-1752">
Passport No</span><span class="sxs-lookup"><span data-stu-id="9d99e-1752">Passport No</span></span>
- <span data-ttu-id="9d99e-1753">Passport#
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1753">Passport #</span></span>
- <span data-ttu-id="9d99e-1754">Passport#
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1754">Passport#</span></span>
- <span data-ttu-id="9d99e-1755">PassportID</span><span class="sxs-lookup"><span data-stu-id="9d99e-1755">PassportID</span></span>
- <span data-ttu-id="9d99e-1756">Passportno
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1756">Passportno</span></span>
- <span data-ttu-id="9d99e-1757">passportnumber
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1757">passportnumber</span></span>
- <span data-ttu-id="9d99e-1758">パスポート</span><span class="sxs-lookup"><span data-stu-id="9d99e-1758">パスポート</span></span>
- <span data-ttu-id="9d99e-1759">パスポート番号
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1759">パスポート番号</span></span>
- <span data-ttu-id="9d99e-1760">パスポートのNum
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1760">パスポートのNum</span></span>
- <span data-ttu-id="9d99e-1761">
パスポート ＃
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1761">パスポート ＃</span></span> 
- <span data-ttu-id="9d99e-1762">Numéro de passeport</span><span class="sxs-lookup"><span data-stu-id="9d99e-1762">Numéro de passeport</span></span>
- <span data-ttu-id="9d99e-1763">
Passeport n °</span><span class="sxs-lookup"><span data-stu-id="9d99e-1763">Passeport n °</span></span>
- <span data-ttu-id="9d99e-1764">Passeport Non
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1764">Passeport Non</span></span>
- <span data-ttu-id="9d99e-1765">Passeport#
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1765">Passeport #</span></span>
- <span data-ttu-id="9d99e-1766">Passeport#
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1766">Passeport#</span></span>
- <span data-ttu-id="9d99e-1767">PasseportNon</span><span class="sxs-lookup"><span data-stu-id="9d99e-1767">PasseportNon</span></span>
- <span data-ttu-id="9d99e-1768">

Passeportn °</span><span class="sxs-lookup"><span data-stu-id="9d99e-1768">Passeportn °</span></span>

      
## <a name="france-social-security-number-insee"></a><span data-ttu-id="9d99e-1769">Francia - Numero di previdenza sociale (INSEE)</span><span class="sxs-lookup"><span data-stu-id="9d99e-1769">France Social Security Number (INSEE)</span></span>

### <a name="format"></a><span data-ttu-id="9d99e-1770">Formato</span><span class="sxs-lookup"><span data-stu-id="9d99e-1770">Format</span></span>

<span data-ttu-id="9d99e-1771">15 cifre</span><span class="sxs-lookup"><span data-stu-id="9d99e-1771">15 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="9d99e-1772">Modello</span><span class="sxs-lookup"><span data-stu-id="9d99e-1772">Pattern</span></span>

<span data-ttu-id="9d99e-1773">Deve corrispondere a uno di questi due modelli:</span><span class="sxs-lookup"><span data-stu-id="9d99e-1773">Must match one of two patterns:</span></span>
- <span data-ttu-id="9d99e-1774">13 cifre seguite da uno spazio seguito da due cifre</span><span class="sxs-lookup"><span data-stu-id="9d99e-1774">13 digits followed by a space followed by two digits</span></span><br/>
<span data-ttu-id="9d99e-1775">oppure</span><span class="sxs-lookup"><span data-stu-id="9d99e-1775">or</span></span>
- <span data-ttu-id="9d99e-1776">15 cifre consecutive</span><span class="sxs-lookup"><span data-stu-id="9d99e-1776">15 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="9d99e-1777">Checksum</span><span class="sxs-lookup"><span data-stu-id="9d99e-1777">Checksum</span></span>

<span data-ttu-id="9d99e-1778">Sì</span><span class="sxs-lookup"><span data-stu-id="9d99e-1778">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="9d99e-1779">Definizione</span><span class="sxs-lookup"><span data-stu-id="9d99e-1779">Definition</span></span>

<span data-ttu-id="9d99e-1780">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 95%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="9d99e-1780">A DLP policy is 95% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="9d99e-1781">La funzione Func_french_insee o Func_fr_insee consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="9d99e-1781">The function Func_french_insee or Func_fr_insee finds content that matches the pattern.</span></span>
- <span data-ttu-id="9d99e-1782">Viene trovata una parola chiave da Keyword_fr_insee.</span><span class="sxs-lookup"><span data-stu-id="9d99e-1782">A keyword from Keyword_fr_insee is found.</span></span>
- <span data-ttu-id="9d99e-1783">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="9d99e-1783">The checksum passes.</span></span>

<span data-ttu-id="9d99e-1784">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="9d99e-1784">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="9d99e-1785">La funzione Func_french_insee o Func_fr_insee consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="9d99e-1785">The function Func_french_insee or Func_fr_insee finds content that matches the pattern.</span></span>
- <span data-ttu-id="9d99e-1786">Non vengono trovate parole chiave da Keyword_fr_insee.</span><span class="sxs-lookup"><span data-stu-id="9d99e-1786">No keyword from Keyword_fr_insee is found.</span></span>
- <span data-ttu-id="9d99e-1787">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="9d99e-1787">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="9d99e-1788">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="9d99e-1788">Keywords</span></span>

#### <a name="keywordfrinsee"></a><span data-ttu-id="9d99e-1789">Keyword_fr_insee</span><span class="sxs-lookup"><span data-stu-id="9d99e-1789">Keyword_fr_insee</span></span>

- <span data-ttu-id="9d99e-1790">insee</span><span class="sxs-lookup"><span data-stu-id="9d99e-1790">insee</span></span>
- <span data-ttu-id="9d99e-1791">
securité sociale</span><span class="sxs-lookup"><span data-stu-id="9d99e-1791">securité sociale</span></span>
- <span data-ttu-id="9d99e-1792">
securite sociale</span><span class="sxs-lookup"><span data-stu-id="9d99e-1792">securite sociale</span></span>
- <span data-ttu-id="9d99e-1793">
national id</span><span class="sxs-lookup"><span data-stu-id="9d99e-1793">national id</span></span>
- <span data-ttu-id="9d99e-1794">
national identification</span><span class="sxs-lookup"><span data-stu-id="9d99e-1794">national identification</span></span>
- <span data-ttu-id="9d99e-1795">
numéro d'identité</span><span class="sxs-lookup"><span data-stu-id="9d99e-1795">numéro d'identité</span></span>
- <span data-ttu-id="9d99e-1796">Nessun g ' identité</span><span class="sxs-lookup"><span data-stu-id="9d99e-1796">no d'identité</span></span>
- <span data-ttu-id="9d99e-p131">
no. d'identité</span><span class="sxs-lookup"><span data-stu-id="9d99e-p131">no. d'identité</span></span>
- <span data-ttu-id="9d99e-1799">
numero d'identite</span><span class="sxs-lookup"><span data-stu-id="9d99e-1799">numero d'identite</span></span>
- <span data-ttu-id="9d99e-1800">Nessun d'identite</span><span class="sxs-lookup"><span data-stu-id="9d99e-1800">no d'identite</span></span>
- <span data-ttu-id="9d99e-p132">
no. d'identite</span><span class="sxs-lookup"><span data-stu-id="9d99e-p132">no. d'identite</span></span>
- <span data-ttu-id="9d99e-1803">social security number
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1803">social security number</span></span>
- <span data-ttu-id="9d99e-1804">
social security code</span><span class="sxs-lookup"><span data-stu-id="9d99e-1804">social security code</span></span>
- <span data-ttu-id="9d99e-1805">social insurance number</span><span class="sxs-lookup"><span data-stu-id="9d99e-1805">social insurance number</span></span>
- <span data-ttu-id="9d99e-1806">
le numéro d'identification nationale</span><span class="sxs-lookup"><span data-stu-id="9d99e-1806">le numéro d'identification nationale</span></span>
- <span data-ttu-id="9d99e-1807">
d'identité nationale</span><span class="sxs-lookup"><span data-stu-id="9d99e-1807">d'identité nationale</span></span>
- <span data-ttu-id="9d99e-1808">
numéro de sécurité sociale</span><span class="sxs-lookup"><span data-stu-id="9d99e-1808">numéro de sécurité sociale</span></span>
- <span data-ttu-id="9d99e-1809">
le code de la sécurité sociale</span><span class="sxs-lookup"><span data-stu-id="9d99e-1809">le code de la sécurité sociale</span></span>
- <span data-ttu-id="9d99e-1810">
numéro d'assurance sociale</span><span class="sxs-lookup"><span data-stu-id="9d99e-1810">numéro d'assurance sociale</span></span>
- <span data-ttu-id="9d99e-1811">
numéro de sécu</span><span class="sxs-lookup"><span data-stu-id="9d99e-1811">numéro de sécu</span></span>
- <span data-ttu-id="9d99e-1812">
code sécu
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1812">code sécu</span></span> 
   
## <a name="german-drivers-license-number"></a><span data-ttu-id="9d99e-1813">Germania - Numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="9d99e-1813">German Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="9d99e-1814">Formato</span><span class="sxs-lookup"><span data-stu-id="9d99e-1814">Format</span></span>

<span data-ttu-id="9d99e-1815">Combinazione di 11 cifre e lettere</span><span class="sxs-lookup"><span data-stu-id="9d99e-1815">Combination of 11 digits and letters</span></span>

### <a name="pattern"></a><span data-ttu-id="9d99e-1816">Modello</span><span class="sxs-lookup"><span data-stu-id="9d99e-1816">Pattern</span></span>

<span data-ttu-id="9d99e-1817">11 cifre e lettere (senza distinzione tra maiuscole/minuscole):</span><span class="sxs-lookup"><span data-stu-id="9d99e-1817">11 digits and letters (not case sensitive):</span></span>
- <span data-ttu-id="9d99e-1818">Una cifra o una lettera</span><span class="sxs-lookup"><span data-stu-id="9d99e-1818">A digit or letter</span></span> 
- <span data-ttu-id="9d99e-1819">Due cifre</span><span class="sxs-lookup"><span data-stu-id="9d99e-1819">Two digits</span></span> 
- <span data-ttu-id="9d99e-1820">Sei cifre o lettere</span><span class="sxs-lookup"><span data-stu-id="9d99e-1820">Six digits or letters</span></span> 
- <span data-ttu-id="9d99e-1821">Una cifra</span><span class="sxs-lookup"><span data-stu-id="9d99e-1821">A digit</span></span> 
- <span data-ttu-id="9d99e-1822">Una cifra o una lettera</span><span class="sxs-lookup"><span data-stu-id="9d99e-1822">A digit or letter</span></span>

### <a name="checksum"></a><span data-ttu-id="9d99e-1823">Checksum</span><span class="sxs-lookup"><span data-stu-id="9d99e-1823">Checksum</span></span>

<span data-ttu-id="9d99e-1824">Sì</span><span class="sxs-lookup"><span data-stu-id="9d99e-1824">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="9d99e-1825">Definizione</span><span class="sxs-lookup"><span data-stu-id="9d99e-1825">Definition</span></span>

<span data-ttu-id="9d99e-1826">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="9d99e-1826">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="9d99e-1827">La funzione Func_german_drivers_license restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="9d99e-1827">The function Func_german_drivers_license finds content that matches the pattern.</span></span>
- <span data-ttu-id="9d99e-1828">Si verifica almeno una delle situazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="9d99e-1828">At least one of the following is true:</span></span>
    - <span data-ttu-id="9d99e-1829">Viene trovata una parola chiave da Keyword_german_drivers_license_number.</span><span class="sxs-lookup"><span data-stu-id="9d99e-1829">A keyword from Keyword_german_drivers_license_number is found.</span></span>
    - <span data-ttu-id="9d99e-1830">Viene trovata una parola chiave da Keyword_german_drivers_license_collaborative.</span><span class="sxs-lookup"><span data-stu-id="9d99e-1830">A keyword from Keyword_german_drivers_license_collaborative is found.</span></span>
    - <span data-ttu-id="9d99e-1831">Viene trovata una parola chiave da Keyword_german_drivers_license.</span><span class="sxs-lookup"><span data-stu-id="9d99e-1831">A keyword from Keyword_german_drivers_license is found.</span></span>
- <span data-ttu-id="9d99e-1832">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="9d99e-1832">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="9d99e-1833">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="9d99e-1833">Keywords</span></span>

#### <a name="keywordgermandriverslicensenumber"></a><span data-ttu-id="9d99e-1834">Keyword_german_drivers_license_number</span><span class="sxs-lookup"><span data-stu-id="9d99e-1834">Keyword_german_drivers_license_number</span></span>

- <span data-ttu-id="9d99e-1835">Führerschein</span><span class="sxs-lookup"><span data-stu-id="9d99e-1835">Führerschein</span></span>
- <span data-ttu-id="9d99e-1836">
Fuhrerschein</span><span class="sxs-lookup"><span data-stu-id="9d99e-1836">Fuhrerschein</span></span>
- <span data-ttu-id="9d99e-1837">Fuehrerschein</span><span class="sxs-lookup"><span data-stu-id="9d99e-1837">Fuehrerschein</span></span>
- <span data-ttu-id="9d99e-1838">
Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="9d99e-1838">Führerscheinnummer</span></span>
- <span data-ttu-id="9d99e-1839">
Fuhrerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="9d99e-1839">Fuhrerscheinnummer</span></span>
- <span data-ttu-id="9d99e-1840">
Fuehrerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="9d99e-1840">Fuehrerscheinnummer</span></span>
- <span data-ttu-id="9d99e-1841">
Führerschein-
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1841">Führerschein-</span></span> 
- <span data-ttu-id="9d99e-1842">Fuhrerschein-
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1842">Fuhrerschein-</span></span> 
- <span data-ttu-id="9d99e-1843">Fuehrerschein-
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1843">Fuehrerschein-</span></span> 
- <span data-ttu-id="9d99e-1844">FührerscheinnummerNr</span><span class="sxs-lookup"><span data-stu-id="9d99e-1844">FührerscheinnummerNr</span></span>
- <span data-ttu-id="9d99e-1845">FuhrerscheinnummerNr</span><span class="sxs-lookup"><span data-stu-id="9d99e-1845">FuhrerscheinnummerNr</span></span>
- <span data-ttu-id="9d99e-1846">FuehrerscheinnummerNr</span><span class="sxs-lookup"><span data-stu-id="9d99e-1846">FuehrerscheinnummerNr</span></span>
- <span data-ttu-id="9d99e-1847">FührerscheinnummerKlasse</span><span class="sxs-lookup"><span data-stu-id="9d99e-1847">FührerscheinnummerKlasse</span></span>
- <span data-ttu-id="9d99e-1848">FuhrerscheinnummerKlasse</span><span class="sxs-lookup"><span data-stu-id="9d99e-1848">FuhrerscheinnummerKlasse</span></span>
- <span data-ttu-id="9d99e-1849">FuehrerscheinnummerKlasse</span><span class="sxs-lookup"><span data-stu-id="9d99e-1849">FuehrerscheinnummerKlasse</span></span>
- <span data-ttu-id="9d99e-1850">Führerschein- Nr
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1850">Führerschein- Nr</span></span>
- <span data-ttu-id="9d99e-1851">Fuhrerschein- Nr
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1851">Fuhrerschein- Nr</span></span>
- <span data-ttu-id="9d99e-1852">Fuehrerschein- Nr
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1852">Fuehrerschein- Nr</span></span> 
- <span data-ttu-id="9d99e-1853">Führerschein- Klasse
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1853">Führerschein- Klasse</span></span> 
- <span data-ttu-id="9d99e-1854">Fuhrerschein- Klasse
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1854">Fuhrerschein- Klasse</span></span> 
- <span data-ttu-id="9d99e-1855">Fuehrerschein- Klasse</span><span class="sxs-lookup"><span data-stu-id="9d99e-1855">Fuehrerschein- Klasse</span></span>
- <span data-ttu-id="9d99e-1856">FührerscheinnummerNr</span><span class="sxs-lookup"><span data-stu-id="9d99e-1856">FührerscheinnummerNr</span></span> 
- <span data-ttu-id="9d99e-1857">FuhrerscheinnummerNr</span><span class="sxs-lookup"><span data-stu-id="9d99e-1857">FuhrerscheinnummerNr</span></span> 
- <span data-ttu-id="9d99e-1858">FuehrerscheinnummerNr</span><span class="sxs-lookup"><span data-stu-id="9d99e-1858">FuehrerscheinnummerNr</span></span> 
- <span data-ttu-id="9d99e-1859">FührerscheinnummerKlasse</span><span class="sxs-lookup"><span data-stu-id="9d99e-1859">FührerscheinnummerKlasse</span></span> 
- <span data-ttu-id="9d99e-1860">FuhrerscheinnummerKlasse</span><span class="sxs-lookup"><span data-stu-id="9d99e-1860">FuhrerscheinnummerKlasse</span></span> 
- <span data-ttu-id="9d99e-1861">FuehrerscheinnummerKlasse</span><span class="sxs-lookup"><span data-stu-id="9d99e-1861">FuehrerscheinnummerKlasse</span></span> 
- <span data-ttu-id="9d99e-1862">Führerschein- Nr
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1862">Führerschein- Nr</span></span> 
- <span data-ttu-id="9d99e-1863">Fuhrerschein- Nr
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1863">Fuhrerschein- Nr</span></span> 
- <span data-ttu-id="9d99e-1864">Fuehrerschein- Nr
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1864">Fuehrerschein- Nr</span></span> 
- <span data-ttu-id="9d99e-1865">Führerschein- Klasse
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1865">Führerschein- Klasse</span></span> 
- <span data-ttu-id="9d99e-1866">Fuhrerschein- Klasse
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1866">Fuhrerschein- Klasse</span></span> 
- <span data-ttu-id="9d99e-1867">Fuehrerschein- Klasse</span><span class="sxs-lookup"><span data-stu-id="9d99e-1867">Fuehrerschein- Klasse</span></span> 
- <span data-ttu-id="9d99e-1868">DL</span><span class="sxs-lookup"><span data-stu-id="9d99e-1868">DL</span></span> 
- <span data-ttu-id="9d99e-1869">DLS</span><span class="sxs-lookup"><span data-stu-id="9d99e-1869">DLS</span></span>
- <span data-ttu-id="9d99e-1870">
Driv Lic
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1870">Driv Lic</span></span> 
- <span data-ttu-id="9d99e-1871">Driv Licen
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1871">Driv Licen</span></span> 
- <span data-ttu-id="9d99e-1872">Driv License</span><span class="sxs-lookup"><span data-stu-id="9d99e-1872">Driv License</span></span>
- <span data-ttu-id="9d99e-1873">
Driv Licenses
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1873">Driv Licenses</span></span> 
- <span data-ttu-id="9d99e-1874">Driv Licence
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1874">Driv Licence</span></span> 
- <span data-ttu-id="9d99e-1875">Driv Licences
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1875">Driv Licences</span></span> 
- <span data-ttu-id="9d99e-1876">Driv Lic
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1876">Driv Lic</span></span> 
- <span data-ttu-id="9d99e-1877">Driver Licen
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1877">Driver Licen</span></span> 
- <span data-ttu-id="9d99e-1878">Patente</span><span class="sxs-lookup"><span data-stu-id="9d99e-1878">Driver License</span></span> 
- <span data-ttu-id="9d99e-1879">Driver licenze</span><span class="sxs-lookup"><span data-stu-id="9d99e-1879">Driver Licenses</span></span> 
- <span data-ttu-id="9d99e-1880">Driver Licence
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1880">Driver Licence</span></span> 
- <span data-ttu-id="9d99e-1881">Driver Licences
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1881">Driver Licences</span></span> 
- <span data-ttu-id="9d99e-1882">Driver Lic</span><span class="sxs-lookup"><span data-stu-id="9d99e-1882">Drivers Lic</span></span> 
- <span data-ttu-id="9d99e-1883">Driver Licen</span><span class="sxs-lookup"><span data-stu-id="9d99e-1883">Drivers Licen</span></span> 
- <span data-ttu-id="9d99e-1884">Patente di Guida</span><span class="sxs-lookup"><span data-stu-id="9d99e-1884">Drivers License</span></span> 
- <span data-ttu-id="9d99e-1885">Driver licenze</span><span class="sxs-lookup"><span data-stu-id="9d99e-1885">Drivers Licenses</span></span> 
- <span data-ttu-id="9d99e-1886">Driver della licenza</span><span class="sxs-lookup"><span data-stu-id="9d99e-1886">Drivers Licence</span></span> 
- <span data-ttu-id="9d99e-1887">Driver titoli</span><span class="sxs-lookup"><span data-stu-id="9d99e-1887">Drivers Licences</span></span> 
- <span data-ttu-id="9d99e-1888">Lic della patente di Guida</span><span class="sxs-lookup"><span data-stu-id="9d99e-1888">Driver's Lic</span></span> 
- <span data-ttu-id="9d99e-1889">Driver's Licen
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1889">Driver's Licen</span></span> 
- <span data-ttu-id="9d99e-1890">Patente</span><span class="sxs-lookup"><span data-stu-id="9d99e-1890">Driver's License</span></span> 
- <span data-ttu-id="9d99e-1891">Licenze della patente di Guida</span><span class="sxs-lookup"><span data-stu-id="9d99e-1891">Driver's Licenses</span></span> 
- <span data-ttu-id="9d99e-1892">Driver's Licence
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1892">Driver's Licence</span></span> 
- <span data-ttu-id="9d99e-1893">Driver's Licences
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1893">Driver's Licences</span></span> 
- <span data-ttu-id="9d99e-1894">Driving Lic
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1894">Driving Lic</span></span> 
- <span data-ttu-id="9d99e-1895">Driving Licen
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1895">Driving Licen</span></span> 
- <span data-ttu-id="9d99e-1896">Driving License
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1896">Driving License</span></span> 
- <span data-ttu-id="9d99e-1897">Driving Licenses
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1897">Driving Licenses</span></span> 
- <span data-ttu-id="9d99e-1898">Driving Licence

</span><span class="sxs-lookup"><span data-stu-id="9d99e-1898">Driving Licence</span></span> 
- <span data-ttu-id="9d99e-1899">Driving Licences</span><span class="sxs-lookup"><span data-stu-id="9d99e-1899">Driving Licences</span></span>

#### <a name="keywordgermandriverslicensecollaborative"></a><span data-ttu-id="9d99e-1900">Keyword_german_drivers_license_collaborative</span><span class="sxs-lookup"><span data-stu-id="9d99e-1900">Keyword_german_drivers_license_collaborative</span></span>

- <span data-ttu-id="9d99e-1901">
Nr-Führerschein
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1901">Nr-Führerschein</span></span> 
- <span data-ttu-id="9d99e-1902">Nr-Fuhrerschein
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1902">Nr-Fuhrerschein</span></span> 
- <span data-ttu-id="9d99e-1903">Nr-Fuehrerschein
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1903">Nr-Fuehrerschein</span></span> 
- <span data-ttu-id="9d99e-1904">No-Führerschein
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1904">No-Führerschein</span></span> 
- <span data-ttu-id="9d99e-1905">No-Fuhrerschein
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1905">No-Fuhrerschein</span></span> 
- <span data-ttu-id="9d99e-1906">No-Fuehrerschein
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1906">No-Fuehrerschein</span></span> 
- <span data-ttu-id="9d99e-1907">N-Führerschein
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1907">N-Führerschein</span></span> 
- <span data-ttu-id="9d99e-1908">N-Fuhrerschein
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1908">N-Fuhrerschein</span></span> 
- <span data-ttu-id="9d99e-1909">N-Fuehrerschein</span><span class="sxs-lookup"><span data-stu-id="9d99e-1909">N-Fuehrerschein</span></span>
- <span data-ttu-id="9d99e-1910">
Nr-Führerschein
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1910">Nr-Führerschein</span></span> 
- <span data-ttu-id="9d99e-1911">Nr-Fuhrerschein
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1911">Nr-Fuhrerschein</span></span> 
- <span data-ttu-id="9d99e-1912">Nr-Fuehrerschein
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1912">Nr-Fuehrerschein</span></span> 
- <span data-ttu-id="9d99e-1913">No-Führerschein
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1913">No-Führerschein</span></span> 
- <span data-ttu-id="9d99e-1914">No-Fuhrerschein
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1914">No-Fuhrerschein</span></span> 
- <span data-ttu-id="9d99e-1915">No-Fuehrerschein
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1915">No-Fuehrerschein</span></span> 
- <span data-ttu-id="9d99e-1916">N-Führerschein
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1916">N-Führerschein</span></span> 
- <span data-ttu-id="9d99e-1917">N-Fuhrerschein
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1917">N-Fuhrerschein</span></span> 
- <span data-ttu-id="9d99e-1918">N-Fuehrerschein</span><span class="sxs-lookup"><span data-stu-id="9d99e-1918">N-Fuehrerschein</span></span> 

#### <a name="keywordgermandriverslicense"></a><span data-ttu-id="9d99e-1919">Keyword_german_drivers_license</span><span class="sxs-lookup"><span data-stu-id="9d99e-1919">Keyword_german_drivers_license</span></span>

- <span data-ttu-id="9d99e-1920">ausstellungsdatum</span><span class="sxs-lookup"><span data-stu-id="9d99e-1920">ausstellungsdatum</span></span>
- <span data-ttu-id="9d99e-1921">
ausstellungsort</span><span class="sxs-lookup"><span data-stu-id="9d99e-1921">ausstellungsort</span></span>
- <span data-ttu-id="9d99e-1922">
ausstellende behöde</span><span class="sxs-lookup"><span data-stu-id="9d99e-1922">ausstellende behöde</span></span>
- <span data-ttu-id="9d99e-1923">
ausstellende behorde</span><span class="sxs-lookup"><span data-stu-id="9d99e-1923">ausstellende behorde</span></span>
- <span data-ttu-id="9d99e-1924">

ausstellende behoerde</span><span class="sxs-lookup"><span data-stu-id="9d99e-1924">ausstellende behoerde</span></span>
   
## <a name="german-passport-number"></a><span data-ttu-id="9d99e-1925">Germania - Numero di passaporto</span><span class="sxs-lookup"><span data-stu-id="9d99e-1925">German Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="9d99e-1926">Formato</span><span class="sxs-lookup"><span data-stu-id="9d99e-1926">Format</span></span>

<span data-ttu-id="9d99e-1927">10 cifre o lettere</span><span class="sxs-lookup"><span data-stu-id="9d99e-1927">10 digits or letters</span></span>

### <a name="pattern"></a><span data-ttu-id="9d99e-1928">Modello</span><span class="sxs-lookup"><span data-stu-id="9d99e-1928">Pattern</span></span>

<span data-ttu-id="9d99e-1929">Il modello deve includere tutti gli elementi seguenti:</span><span class="sxs-lookup"><span data-stu-id="9d99e-1929">Pattern must include all of the following:</span></span>
- <span data-ttu-id="9d99e-1930">Il primo carattere è una cifra o una lettera del gruppo seguente: C, F, G, H, J, K</span><span class="sxs-lookup"><span data-stu-id="9d99e-1930">First character is a digit or a letter from this set (C, F, G, H, J, K)</span></span> 
- <span data-ttu-id="9d99e-1931">Tre cifre</span><span class="sxs-lookup"><span data-stu-id="9d99e-1931">Three digits</span></span> 
- <span data-ttu-id="9d99e-1932">Cinque cifre o lettere del gruppo seguente: C, -H, J-N, P, R, T, V-Z</span><span class="sxs-lookup"><span data-stu-id="9d99e-1932">Five digits or letters from this set (C, -H, J-N, P, R, T, V-Z)</span></span> 
- <span data-ttu-id="9d99e-1933">Una cifra</span><span class="sxs-lookup"><span data-stu-id="9d99e-1933">A digit</span></span>

### <a name="checksum"></a><span data-ttu-id="9d99e-1934">Checksum</span><span class="sxs-lookup"><span data-stu-id="9d99e-1934">Checksum</span></span>

<span data-ttu-id="9d99e-1935">Sì</span><span class="sxs-lookup"><span data-stu-id="9d99e-1935">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="9d99e-1936">Definizione</span><span class="sxs-lookup"><span data-stu-id="9d99e-1936">Definition</span></span>

<span data-ttu-id="9d99e-1937">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="9d99e-1937">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="9d99e-1938">La funzione Func_german_passport restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="9d99e-1938">The function Func_german_passport finds content that matches the pattern.</span></span>
- <span data-ttu-id="9d99e-1939">Viene trovata una parola chiave fra le cinque elencate.</span><span class="sxs-lookup"><span data-stu-id="9d99e-1939">A keyword from any of the five keyword lists is found.</span></span>
- <span data-ttu-id="9d99e-1940">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="9d99e-1940">The checksum passes.</span></span>

<span data-ttu-id="9d99e-1941">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="9d99e-1941">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="9d99e-1942">La funzione Func_german_passport_data restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="9d99e-1942">The function Func_german_passport_data finds content that matches the pattern.</span></span>
- <span data-ttu-id="9d99e-1943">Viene trovata una parola chiave fra le cinque elencate.</span><span class="sxs-lookup"><span data-stu-id="9d99e-1943">A keyword from any of the five keyword lists is found.</span></span>
- <span data-ttu-id="9d99e-1944">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="9d99e-1944">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="9d99e-1945">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="9d99e-1945">Keywords</span></span>

#### <a name="keywordgermanpassport"></a><span data-ttu-id="9d99e-1946">Keyword_german_passport</span><span class="sxs-lookup"><span data-stu-id="9d99e-1946">Keyword_german_passport</span></span>

- <span data-ttu-id="9d99e-1947">reisepass</span><span class="sxs-lookup"><span data-stu-id="9d99e-1947">reisepass</span></span>
- <span data-ttu-id="9d99e-1948">
reisepasse</span><span class="sxs-lookup"><span data-stu-id="9d99e-1948">reisepasse</span></span>
- <span data-ttu-id="9d99e-1949">
reisepassnummer</span><span class="sxs-lookup"><span data-stu-id="9d99e-1949">reisepassnummer</span></span>
- <span data-ttu-id="9d99e-1950">passport</span><span class="sxs-lookup"><span data-stu-id="9d99e-1950">passport</span></span>
- <span data-ttu-id="9d99e-1951">

passports</span><span class="sxs-lookup"><span data-stu-id="9d99e-1951">passports</span></span>

#### <a name="keywordgermanpassportcollaborative"></a><span data-ttu-id="9d99e-1952">Keyword_german_passport_collaborative</span><span class="sxs-lookup"><span data-stu-id="9d99e-1952">Keyword_german_passport_collaborative</span></span>

- <span data-ttu-id="9d99e-1953">geburtsdatum</span><span class="sxs-lookup"><span data-stu-id="9d99e-1953">geburtsdatum</span></span>
- <span data-ttu-id="9d99e-1954">ausstellungsdatum</span><span class="sxs-lookup"><span data-stu-id="9d99e-1954">ausstellungsdatum</span></span>
- <span data-ttu-id="9d99e-1955">
ausstellungsort</span><span class="sxs-lookup"><span data-stu-id="9d99e-1955">ausstellungsort</span></span>

#### <a name="keywordgermanpassportnumber"></a><span data-ttu-id="9d99e-1956">Keyword_german_passport_number</span><span class="sxs-lookup"><span data-stu-id="9d99e-1956">Keyword_german_passport_number</span></span>

<span data-ttu-id="9d99e-1957">Non-Reisepass Nr-Reisepass</span><span class="sxs-lookup"><span data-stu-id="9d99e-1957">No-Reisepass Nr-Reisepass</span></span>

#### <a name="keywordgermanpassport1"></a><span data-ttu-id="9d99e-1958">Keyword_german_passport1</span><span class="sxs-lookup"><span data-stu-id="9d99e-1958">Keyword_german_passport1</span></span>

<span data-ttu-id="9d99e-1959">Reisepass-Nr
</span><span class="sxs-lookup"><span data-stu-id="9d99e-1959">Reisepass-Nr</span></span>

#### <a name="keywordgermanpassport2"></a><span data-ttu-id="9d99e-1960">Keyword_german_passport2</span><span class="sxs-lookup"><span data-stu-id="9d99e-1960">Keyword_german_passport2</span></span>

<span data-ttu-id="9d99e-1961">bnationalit.t</span><span class="sxs-lookup"><span data-stu-id="9d99e-1961">bnationalit.t</span></span>
   
## <a name="germany-identity-card-number"></a><span data-ttu-id="9d99e-1962">Germania - Numero carta di identità</span><span class="sxs-lookup"><span data-stu-id="9d99e-1962">Germany Identity Card Number</span></span>

### <a name="format"></a><span data-ttu-id="9d99e-1963">Formato</span><span class="sxs-lookup"><span data-stu-id="9d99e-1963">Format</span></span>

<span data-ttu-id="9d99e-1964">Dopo 1 novembre 2010: nove lettere e cifre</span><span class="sxs-lookup"><span data-stu-id="9d99e-1964">Since 1 November 2010: Nine letters and digits</span></span>

<span data-ttu-id="9d99e-1965">Da 1 aprile 1987 fino a 31 cifre di 2010:10 ottobre</span><span class="sxs-lookup"><span data-stu-id="9d99e-1965">From 1 April 1987 until 31 October 2010: 10 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="9d99e-1966">Modello</span><span class="sxs-lookup"><span data-stu-id="9d99e-1966">Pattern</span></span>

<span data-ttu-id="9d99e-1967">A partire dal 1° novembre 2010:</span><span class="sxs-lookup"><span data-stu-id="9d99e-1967">Since 1 November 2010:</span></span>
- <span data-ttu-id="9d99e-1968">Una lettera (senza distinzione tra maiuscole/minuscole)</span><span class="sxs-lookup"><span data-stu-id="9d99e-1968">One letter (not case sensitive)</span></span> 
- <span data-ttu-id="9d99e-1969">Otto cifre</span><span class="sxs-lookup"><span data-stu-id="9d99e-1969">Eight digits</span></span>

<span data-ttu-id="9d99e-1970">Da 1 aprile 1987 fino a 31 ottobre 2010:</span><span class="sxs-lookup"><span data-stu-id="9d99e-1970">From 1 April 1987 until 31 October 2010:</span></span>
- <span data-ttu-id="9d99e-1971">10 cifre</span><span class="sxs-lookup"><span data-stu-id="9d99e-1971">10 digits</span></span>

### <a name="checksum"></a><span data-ttu-id="9d99e-1972">Checksum</span><span class="sxs-lookup"><span data-stu-id="9d99e-1972">Checksum</span></span>

<span data-ttu-id="9d99e-1973">No</span><span class="sxs-lookup"><span data-stu-id="9d99e-1973">No</span></span>

### <a name="definition"></a><span data-ttu-id="9d99e-1974">Definizione</span><span class="sxs-lookup"><span data-stu-id="9d99e-1974">Definition</span></span>

<span data-ttu-id="9d99e-1975">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 65%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="9d99e-1975">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="9d99e-1976">L'espressione regolare Regex_germany_id_card consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="9d99e-1976">The regular expression Regex_germany_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="9d99e-1977">È possibile trovare una parola chiave da Keyword_germany_id_card.</span><span class="sxs-lookup"><span data-stu-id="9d99e-1977">A keyword from Keyword_germany_id_card is found.</span></span>

```
<!-- Germany Identity Card Number -->
<Entity id="e577372f-c42e-47a0-9d85-bebed1c237d4" recommendedConfidence="65" patternsProximity="300">
  <Pattern confidenceLevel="65">
     <IdMatch idRef="Regex_germany_id_card"/>
     <Match idRef="Keyword_germany_id_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="9d99e-1978">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="9d99e-1978">Keywords</span></span>

#### <a name="keywordgermanyidcard"></a><span data-ttu-id="9d99e-1979">Keyword_germany_id_card</span><span class="sxs-lookup"><span data-stu-id="9d99e-1979">Keyword_germany_id_card</span></span>

- <span data-ttu-id="9d99e-1980">Carta di identità</span><span class="sxs-lookup"><span data-stu-id="9d99e-1980">Identity Card</span></span>
- <span data-ttu-id="9d99e-1981">ID</span><span class="sxs-lookup"><span data-stu-id="9d99e-1981">ID</span></span>
- <span data-ttu-id="9d99e-1982">Identificazione</span><span class="sxs-lookup"><span data-stu-id="9d99e-1982">Identification</span></span>
- <span data-ttu-id="9d99e-1983">Personalausweis</span><span class="sxs-lookup"><span data-stu-id="9d99e-1983">Personalausweis</span></span>
- <span data-ttu-id="9d99e-1984">Identifizierungsnummer</span><span class="sxs-lookup"><span data-stu-id="9d99e-1984">Identifizierungsnummer</span></span>
- <span data-ttu-id="9d99e-1985">Ausweis</span><span class="sxs-lookup"><span data-stu-id="9d99e-1985">Ausweis</span></span>
- <span data-ttu-id="9d99e-1986">Identifikation</span><span class="sxs-lookup"><span data-stu-id="9d99e-1986">Identifikation</span></span>
   
## <a name="greece-national-id-card"></a><span data-ttu-id="9d99e-1987">Carta d'identità (Grecia)</span><span class="sxs-lookup"><span data-stu-id="9d99e-1987">Greece National ID Card</span></span>

### <a name="format"></a><span data-ttu-id="9d99e-1988">Formato</span><span class="sxs-lookup"><span data-stu-id="9d99e-1988">Format</span></span>

<span data-ttu-id="9d99e-1989">Combinazione di 7-8 lettere e numeri, oltre a un trattino</span><span class="sxs-lookup"><span data-stu-id="9d99e-1989">Combination of 7-8 letters and numbers plus a dash</span></span>

### <a name="pattern"></a><span data-ttu-id="9d99e-1990">Modello</span><span class="sxs-lookup"><span data-stu-id="9d99e-1990">Pattern</span></span>

<span data-ttu-id="9d99e-1991">Sette lettere e numeri (formato precedente):</span><span class="sxs-lookup"><span data-stu-id="9d99e-1991">Seven letters and numbers (old format):</span></span>
- <span data-ttu-id="9d99e-1992">Una lettera (qualsiasi lettera dell'alfabeto greco) </span><span class="sxs-lookup"><span data-stu-id="9d99e-1992">One letter (any letter of the Greek alphabet)</span></span> 
- <span data-ttu-id="9d99e-1993">Un trattino</span><span class="sxs-lookup"><span data-stu-id="9d99e-1993">A dash</span></span> 
- <span data-ttu-id="9d99e-1994">Sei cifre</span><span class="sxs-lookup"><span data-stu-id="9d99e-1994">Six digits</span></span>

<span data-ttu-id="9d99e-1995">Otto lettere e numeri (nuovo formato):</span><span class="sxs-lookup"><span data-stu-id="9d99e-1995">Eight letters and numbers (new format):</span></span>
- <span data-ttu-id="9d99e-1996">Due lettere in maiuscolo sia in alfabeto latino che greco (ABEZHIKMNOPTYX) </span><span class="sxs-lookup"><span data-stu-id="9d99e-1996">Two letters whose uppercase character occurs in both the Greek and Latin alphabets (ABEZHIKMNOPTYX)</span></span> 
- <span data-ttu-id="9d99e-1997">Un trattino</span><span class="sxs-lookup"><span data-stu-id="9d99e-1997">A dash</span></span> 
- <span data-ttu-id="9d99e-1998">Sei cifre</span><span class="sxs-lookup"><span data-stu-id="9d99e-1998">Six digits</span></span>

### <a name="checksum"></a><span data-ttu-id="9d99e-1999">Checksum</span><span class="sxs-lookup"><span data-stu-id="9d99e-1999">Checksum</span></span>

<span data-ttu-id="9d99e-2000">No</span><span class="sxs-lookup"><span data-stu-id="9d99e-2000">No</span></span>

### <a name="definition"></a><span data-ttu-id="9d99e-2001">Definizione</span><span class="sxs-lookup"><span data-stu-id="9d99e-2001">Definition</span></span>

<span data-ttu-id="9d99e-2002">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="9d99e-2002">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="9d99e-2003">L'espressione regolare Regex_greece_id_card consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="9d99e-2003">The regular expression Regex_greece_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="9d99e-2004">È possibile trovare una parola chiave da Keyword_greece_id_card.</span><span class="sxs-lookup"><span data-stu-id="9d99e-2004">A keyword from Keyword_greece_id_card is found.</span></span>

```
<!-- Greece National ID Card -->
<Entity id="82568215-1da1-46d3-874a-d2294d81b5ac" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Regex_greece_id_card"/>
     <Match idRef="Keyword_greece_id_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="9d99e-2005">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="9d99e-2005">Keywords</span></span>

#### <a name="keywordgreeceidcard"></a><span data-ttu-id="9d99e-2006">Keyword_greece_id_card</span><span class="sxs-lookup"><span data-stu-id="9d99e-2006">Keyword_greece_id_card</span></span>

- <span data-ttu-id="9d99e-2007">Carta d’identità greca</span><span class="sxs-lookup"><span data-stu-id="9d99e-2007">Greek identity Card</span></span>
- <span data-ttu-id="9d99e-2008">Tautotita</span><span class="sxs-lookup"><span data-stu-id="9d99e-2008">Tautotita</span></span>
- <span data-ttu-id="9d99e-2009">Δελτίο αστυνομικής ταυτότητας</span><span class="sxs-lookup"><span data-stu-id="9d99e-2009">Δελτίο αστυνομικής ταυτότητας</span></span>
- <span data-ttu-id="9d99e-2010">Ταυτότητα</span><span class="sxs-lookup"><span data-stu-id="9d99e-2010">Ταυτότητα</span></span>
   
## <a name="hong-kong-identity-card-hkid-number"></a><span data-ttu-id="9d99e-2011">Hong Kong - Numero di carta di identità (HKID)</span><span class="sxs-lookup"><span data-stu-id="9d99e-2011">Hong Kong Identity Card (HKID) Number</span></span>

### <a name="format"></a><span data-ttu-id="9d99e-2012">Formato</span><span class="sxs-lookup"><span data-stu-id="9d99e-2012">Format</span></span>

<span data-ttu-id="9d99e-2013">Combinazione di 8-9 lettere e numeri. Facoltativamente, l’ultimo carattere può essere racchiuso tra parentesi</span><span class="sxs-lookup"><span data-stu-id="9d99e-2013">Combination of 8-9 letters and numbers plus optional parentheses around the final character</span></span>

### <a name="pattern"></a><span data-ttu-id="9d99e-2014">Modello</span><span class="sxs-lookup"><span data-stu-id="9d99e-2014">Pattern</span></span>

<span data-ttu-id="9d99e-2015">Combinazione di 8-9 lettere:</span><span class="sxs-lookup"><span data-stu-id="9d99e-2015">Combination of 8-9 letters:</span></span>
- <span data-ttu-id="9d99e-2016">1-2 lettere (senza distinzione tra maiuscole e minuscole)</span><span class="sxs-lookup"><span data-stu-id="9d99e-2016">1-2 letters (not case sensitive)</span></span> 
- <span data-ttu-id="9d99e-2017">Sei cifre</span><span class="sxs-lookup"><span data-stu-id="9d99e-2017">Six digits</span></span> 
- <span data-ttu-id="9d99e-2018">L'ultimo carattere (qualsiasi cifra o la lettera A), è rappresentato dal numero di controllo. Facoltativamente, può essere racchiuso tra parentesi.</span><span class="sxs-lookup"><span data-stu-id="9d99e-2018">The final character (any digit or the letter A), which is the check digit and is optionally enclosed in parentheses.</span></span>

### <a name="checksum"></a><span data-ttu-id="9d99e-2019">Checksum</span><span class="sxs-lookup"><span data-stu-id="9d99e-2019">Checksum</span></span>

<span data-ttu-id="9d99e-2020">Sì</span><span class="sxs-lookup"><span data-stu-id="9d99e-2020">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="9d99e-2021">Definizione</span><span class="sxs-lookup"><span data-stu-id="9d99e-2021">Definition</span></span>

<span data-ttu-id="9d99e-2022">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="9d99e-2022">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="9d99e-2023">La funzione Func_hong_kong_id_card consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="9d99e-2023">The function Func_hong_kong_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="9d99e-2024">È possibile trovare una parola chiave da Keyword_hong_kong_id_card.</span><span class="sxs-lookup"><span data-stu-id="9d99e-2024">A keyword from Keyword_hong_kong_id_card is found.</span></span>
- <span data-ttu-id="9d99e-2025">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="9d99e-2025">The checksum passes.</span></span>

<span data-ttu-id="9d99e-2026">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 65%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="9d99e-2026">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="9d99e-2027">La funzione Func_hong_kong_id_card consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="9d99e-2027">The function Func_hong_kong_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="9d99e-2028">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="9d99e-2028">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="9d99e-2029">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="9d99e-2029">Keywords</span></span>

#### <a name="keywordhongkongidcard"></a><span data-ttu-id="9d99e-2030">Keyword_hong_kong_id_card</span><span class="sxs-lookup"><span data-stu-id="9d99e-2030">Keyword_hong_kong_id_card</span></span>

- <span data-ttu-id="9d99e-2031">Carta d’identità (Hong Kong)</span><span class="sxs-lookup"><span data-stu-id="9d99e-2031">Hong Kong Identity Card</span></span>
- <span data-ttu-id="9d99e-2032">HKID</span><span class="sxs-lookup"><span data-stu-id="9d99e-2032">HKID</span></span>
- <span data-ttu-id="9d99e-2033">Carta di identità
</span><span class="sxs-lookup"><span data-stu-id="9d99e-2033">ID card</span></span>
- <span data-ttu-id="9d99e-2034">香港身份證
</span><span class="sxs-lookup"><span data-stu-id="9d99e-2034">香港身份證</span></span> 
- <span data-ttu-id="9d99e-2035">香港永久性居民身份證
</span><span class="sxs-lookup"><span data-stu-id="9d99e-2035">香港永久性居民身份證</span></span> 
   
## <a name="india-permanent-account-number-pan"></a><span data-ttu-id="9d99e-2036">India - Numero di conto permanente (PAN)</span><span class="sxs-lookup"><span data-stu-id="9d99e-2036">India Permanent Account Number (PAN)</span></span>

### <a name="format"></a><span data-ttu-id="9d99e-2037">Formato</span><span class="sxs-lookup"><span data-stu-id="9d99e-2037">Format</span></span>

<span data-ttu-id="9d99e-2038">10 lettere o cifre</span><span class="sxs-lookup"><span data-stu-id="9d99e-2038">10 letters or digits</span></span>

### <a name="pattern"></a><span data-ttu-id="9d99e-2039">Modello</span><span class="sxs-lookup"><span data-stu-id="9d99e-2039">Pattern</span></span>

<span data-ttu-id="9d99e-2040">10 lettere o cifre:</span><span class="sxs-lookup"><span data-stu-id="9d99e-2040">10 letters or digits:</span></span>
- <span data-ttu-id="9d99e-2041">Cinque lettere (senza distinzione tra maiuscole e minuscole)</span><span class="sxs-lookup"><span data-stu-id="9d99e-2041">Five letters (not case sensitive)</span></span> 
- <span data-ttu-id="9d99e-2042">Quattro cifre</span><span class="sxs-lookup"><span data-stu-id="9d99e-2042">Four digits</span></span> 
- <span data-ttu-id="9d99e-2043">Una lettera, ovvero una cifra di controllo alfabetica</span><span class="sxs-lookup"><span data-stu-id="9d99e-2043">A letter which is an alphabetic check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="9d99e-2044">Checksum</span><span class="sxs-lookup"><span data-stu-id="9d99e-2044">Checksum</span></span>

<span data-ttu-id="9d99e-2045">Sì</span><span class="sxs-lookup"><span data-stu-id="9d99e-2045">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="9d99e-2046">Definizione</span><span class="sxs-lookup"><span data-stu-id="9d99e-2046">Definition</span></span>

<span data-ttu-id="9d99e-2047">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="9d99e-2047">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="9d99e-2048">L'espressione regolare Regex_india_permanent_account_number consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="9d99e-2048">The regular expression Regex_india_permanent_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="9d99e-2049">È possibile trovare una parola chiave da Keyword_india_permanent_account_number.</span><span class="sxs-lookup"><span data-stu-id="9d99e-2049">A keyword from Keyword_india_permanent_account_number is found.</span></span>
- <span data-ttu-id="9d99e-2050">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="9d99e-2050">The checksum passes.</span></span>

```
<!-- India Permanent Account Number -->
<Entity id="2602bfee-9bb0-47a5-a7a6-2bf3053e2804" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Regex_india_permanent_account_number"/>
     <Match idRef="Keyword_india_permanent_account_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="9d99e-2051">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="9d99e-2051">Keywords</span></span>

#### <a name="keywordindiapermanentaccountnumber"></a><span data-ttu-id="9d99e-2052">Keyword_india_permanent_account_number</span><span class="sxs-lookup"><span data-stu-id="9d99e-2052">Keyword_india_permanent_account_number</span></span>

- <span data-ttu-id="9d99e-2053">Permanent Account Number
</span><span class="sxs-lookup"><span data-stu-id="9d99e-2053">Permanent Account Number</span></span> 
- <span data-ttu-id="9d99e-2054">PAN
</span><span class="sxs-lookup"><span data-stu-id="9d99e-2054">PAN</span></span> 
   
## <a name="india-unique-identification-aadhaar-number"></a><span data-ttu-id="9d99e-2055">India - Numero di identificazione univoco (Aadhaar)</span><span class="sxs-lookup"><span data-stu-id="9d99e-2055">India Unique Identification (Aadhaar) Number</span></span>

### <a name="format"></a><span data-ttu-id="9d99e-2056">Formato</span><span class="sxs-lookup"><span data-stu-id="9d99e-2056">Format</span></span>

<span data-ttu-id="9d99e-2057">12 cifre contenenti spazi o trattini facoltativi </span><span class="sxs-lookup"><span data-stu-id="9d99e-2057">12 digits containing optional spaces or dashes</span></span>

### <a name="pattern"></a><span data-ttu-id="9d99e-2058">Modello</span><span class="sxs-lookup"><span data-stu-id="9d99e-2058">Pattern</span></span>

<span data-ttu-id="9d99e-2059">12 cifre:</span><span class="sxs-lookup"><span data-stu-id="9d99e-2059">12 digits:</span></span>
- <span data-ttu-id="9d99e-2060">Quattro cifre</span><span class="sxs-lookup"><span data-stu-id="9d99e-2060">Four digits</span></span> 
- <span data-ttu-id="9d99e-2061">Uno spazio o un trattino facoltativo </span><span class="sxs-lookup"><span data-stu-id="9d99e-2061">An optional space or dash</span></span> 
- <span data-ttu-id="9d99e-2062">Quattro cifre</span><span class="sxs-lookup"><span data-stu-id="9d99e-2062">Four digits</span></span> 
- <span data-ttu-id="9d99e-2063">Uno spazio o un trattino facoltativo </span><span class="sxs-lookup"><span data-stu-id="9d99e-2063">An optional space or dash</span></span> 
- <span data-ttu-id="9d99e-2064">L'ultimo carattere, ovvero il numero di controllo</span><span class="sxs-lookup"><span data-stu-id="9d99e-2064">The final digit which is the check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="9d99e-2065">Checksum</span><span class="sxs-lookup"><span data-stu-id="9d99e-2065">Checksum</span></span>

<span data-ttu-id="9d99e-2066">Sì</span><span class="sxs-lookup"><span data-stu-id="9d99e-2066">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="9d99e-2067">Definizione</span><span class="sxs-lookup"><span data-stu-id="9d99e-2067">Definition</span></span>

<span data-ttu-id="9d99e-p133">Un criterio DLP è 85% la certezza che è stato rilevato questo tipo di informazioni riservate se all'interno di prossimità di 300 caratteri: la funzione Func_india_aadhaar consente di trovare contenuto corrispondente al formato. È possibile trovare una parola chiave da Keyword_india_aadhar. Passa il valore di checksum. Un criterio DLP è 75% la certezza che è stato rilevato questo tipo di informazioni riservate se all'interno di prossimità di 300 caratteri: la funzione Func_india_aadhaar consente di trovare contenuto corrispondente al formato. Passa il valore di checksum. <!-- India Unique Identification (Aadhaar) number -->
<Entity id="1ca46b29-76f5-4f46-9383-cfa15e91048f" recommendedConfidence="85" patternsProximity="300"> <Pattern confidenceLevel="85"> <IdMatch idRef="Func_india_aadhaar"/> <Match idRef="Keyword_india_aadhar"/> </Pattern> <Pattern confidenceLevel="75"> <IdMatch idRef="Func_india_aadhaar"/> </Pattern>
</Entity></span><span class="sxs-lookup"><span data-stu-id="9d99e-p133">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The function Func_india_aadhaar finds content that matches the pattern. A keyword from Keyword_india_aadhar is found. The checksum passes. A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The function Func_india_aadhaar finds content that matches the pattern. The checksum passes. <!-- India Unique Identification (Aadhaar) number -->
<Entity id="1ca46b29-76f5-4f46-9383-cfa15e91048f" recommendedConfidence="85" patternsProximity="300"> <Pattern confidenceLevel="85"> <IdMatch idRef="Func_india_aadhaar"/> <Match idRef="Keyword_india_aadhar"/> </Pattern> <Pattern confidenceLevel="75"> <IdMatch idRef="Func_india_aadhaar"/> </Pattern>
</Entity></span></span>

### <a name="keywords"></a><span data-ttu-id="9d99e-2074">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="9d99e-2074">Keywords</span></span>
   
#### <a name="keywordindiaaadhar"></a><span data-ttu-id="9d99e-2075">Keyword_india_aadhar</span><span class="sxs-lookup"><span data-stu-id="9d99e-2075">Keyword_india_aadhar</span></span>
- <span data-ttu-id="9d99e-2076">Aadhar</span><span class="sxs-lookup"><span data-stu-id="9d99e-2076">Aadhar</span></span>
- <span data-ttu-id="9d99e-2077">Aadhaar</span><span class="sxs-lookup"><span data-stu-id="9d99e-2077">Aadhaar</span></span>
- <span data-ttu-id="9d99e-2078">UID</span><span class="sxs-lookup"><span data-stu-id="9d99e-2078">UID</span></span>
- <span data-ttu-id="9d99e-2079">आधार</span><span class="sxs-lookup"><span data-stu-id="9d99e-2079">आधार</span></span>
   
## <a name="indonesia-identity-card-ktp-number"></a><span data-ttu-id="9d99e-2080">Indonesia - Numero di carta di identità (KTP)</span><span class="sxs-lookup"><span data-stu-id="9d99e-2080">Indonesia Identity Card (KTP) Number</span></span>

### <a name="format"></a><span data-ttu-id="9d99e-2081">Formato</span><span class="sxs-lookup"><span data-stu-id="9d99e-2081">Format</span></span>

<span data-ttu-id="9d99e-2082">16 cifre contenenti punti facoltativi </span><span class="sxs-lookup"><span data-stu-id="9d99e-2082">16 digits containing optional periods</span></span>

### <a name="pattern"></a><span data-ttu-id="9d99e-2083">Modello</span><span class="sxs-lookup"><span data-stu-id="9d99e-2083">Pattern</span></span>

<span data-ttu-id="9d99e-2084">16 cifre:</span><span class="sxs-lookup"><span data-stu-id="9d99e-2084">16 digits:</span></span>
- <span data-ttu-id="9d99e-2085">Codice provincia a due cifre </span><span class="sxs-lookup"><span data-stu-id="9d99e-2085">Two-digit province code</span></span> 
- <span data-ttu-id="9d99e-2086">Un punto (facoltativo) </span><span class="sxs-lookup"><span data-stu-id="9d99e-2086">A period (optional)</span></span> 
- <span data-ttu-id="9d99e-2087">Codice città o area a due cifre </span><span class="sxs-lookup"><span data-stu-id="9d99e-2087">Two-digit regency or city code</span></span> 
- <span data-ttu-id="9d99e-2088">Codice sotto-distretto a due cifre </span><span class="sxs-lookup"><span data-stu-id="9d99e-2088">Two-digit subdistrict code</span></span> 
- <span data-ttu-id="9d99e-2089">Un punto (facoltativo) </span><span class="sxs-lookup"><span data-stu-id="9d99e-2089">A period (optional)</span></span> 
- <span data-ttu-id="9d99e-2090">Sei cifre nel formato GGMMAA, ovvero la data di nascita</span><span class="sxs-lookup"><span data-stu-id="9d99e-2090">Six digits in the format DDMMYY which are the date of birth</span></span> 
- <span data-ttu-id="9d99e-2091">Un punto (facoltativo) </span><span class="sxs-lookup"><span data-stu-id="9d99e-2091">A period (optional)</span></span> 
- <span data-ttu-id="9d99e-2092">Quattro cifre</span><span class="sxs-lookup"><span data-stu-id="9d99e-2092">Four digits</span></span>

### <a name="checksum"></a><span data-ttu-id="9d99e-2093">Checksum</span><span class="sxs-lookup"><span data-stu-id="9d99e-2093">Checksum</span></span>

<span data-ttu-id="9d99e-2094">No</span><span class="sxs-lookup"><span data-stu-id="9d99e-2094">No</span></span>

### <a name="definition"></a><span data-ttu-id="9d99e-2095">Definizione</span><span class="sxs-lookup"><span data-stu-id="9d99e-2095">Definition</span></span>

<span data-ttu-id="9d99e-2096">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="9d99e-2096">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="9d99e-2097">L'espressione regolare Regex_indonesia_id_card consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="9d99e-2097">The regular expression Regex_indonesia_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="9d99e-2098">È possibile trovare una parola chiave da Keyword_indonesia_id_card.</span><span class="sxs-lookup"><span data-stu-id="9d99e-2098">A keyword from Keyword_indonesia_id_card is found.</span></span>

<span data-ttu-id="9d99e-2099">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="9d99e-2099">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="9d99e-2100">L'espressione regolare Regex_indonesia_id_card consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="9d99e-2100">The regular expression Regex_indonesia_id_card finds content that matches the pattern.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="9d99e-2101">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="9d99e-2101">Keywords</span></span>
   
#### <a name="keywordindonesiaidcard"></a><span data-ttu-id="9d99e-2102">Keyword_indonesia_id_card</span><span class="sxs-lookup"><span data-stu-id="9d99e-2102">Keyword_indonesia_id_card</span></span>

- <span data-ttu-id="9d99e-2103">KTP</span><span class="sxs-lookup"><span data-stu-id="9d99e-2103">KTP</span></span>
- <span data-ttu-id="9d99e-2104">Kartu Tanda Penduduk
</span><span class="sxs-lookup"><span data-stu-id="9d99e-2104">Kartu Tanda Penduduk</span></span> 
- <span data-ttu-id="9d99e-2105">Nomor Induk Kependudukan
</span><span class="sxs-lookup"><span data-stu-id="9d99e-2105">Nomor Induk Kependudukan</span></span> 
   
## <a name="international-banking-account-number-iban"></a><span data-ttu-id="9d99e-2106">Numero di conto bancario internazionale (IBAN)</span><span class="sxs-lookup"><span data-stu-id="9d99e-2106">International Banking Account Number (IBAN)</span></span>

### <a name="format"></a><span data-ttu-id="9d99e-2107">Formato</span><span class="sxs-lookup"><span data-stu-id="9d99e-2107">Format</span></span>

<span data-ttu-id="9d99e-2108">Codice paese, due lettere, nonché controllare cifre (due cifre) plus bban numero (fino a 30 caratteri)</span><span class="sxs-lookup"><span data-stu-id="9d99e-2108">Country code (two letters) plus check digits (two digits) plus bban number (up to 30 characters)</span></span>

### <a name="pattern"></a><span data-ttu-id="9d99e-2109">Modello</span><span class="sxs-lookup"><span data-stu-id="9d99e-2109">Pattern</span></span>

<span data-ttu-id="9d99e-2110">Il modello deve includere tutti gli elementi seguenti:</span><span class="sxs-lookup"><span data-stu-id="9d99e-2110">Pattern must include all of the following:</span></span>

- <span data-ttu-id="9d99e-2111">Codice di due lettere del paese</span><span class="sxs-lookup"><span data-stu-id="9d99e-2111">Two-letter country code</span></span>
- <span data-ttu-id="9d99e-2112">Due cifre di controllo (seguite da uno spazio facoltativo)</span><span class="sxs-lookup"><span data-stu-id="9d99e-2112">Two check digits (followed by an optional space)</span></span> 
- <span data-ttu-id="9d99e-2113">1 a 7 gruppi di quattro lettere o cifre (possono essere separati da spazi)</span><span class="sxs-lookup"><span data-stu-id="9d99e-2113">1-7 groups of four letters or digits (can be separated by spaces)</span></span>
- <span data-ttu-id="9d99e-2114">1-3 lettere o cifre</span><span class="sxs-lookup"><span data-stu-id="9d99e-2114">1-3 letters or digits</span></span>

<span data-ttu-id="9d99e-p134">Il formato per ogni paese è leggermente diverso. Il tipo di informazioni riservate IBAN vengono trattati questi 60 paesi:</span><span class="sxs-lookup"><span data-stu-id="9d99e-p134">The format for each country is slightly different. The IBAN sensitive information type covers these 60 countries:</span></span>

<span data-ttu-id="9d99e-2117">Active Directory, ae, all'az, ba, essere, bg, orario di ufficio, ch, cr, cy, cz, de, dk, eseguire, ee, es, fi, fo, fr, gb, ge, gi, contabilità generale, gr, risorse umane, hu, vale a dire il, è, viene, kw, kz, kg, li, lt, lu, lv mc, md, me, mk, mr, mt, mu , nl, no pl, pt, RU, rs, sa, se, si, sk, sm, tn, tr, vg</span><span class="sxs-lookup"><span data-stu-id="9d99e-2117">ad, ae, al, at, az, ba, be, bg, bh, ch, cr, cy, cz, de, dk, do, ee, es, fi, fo, fr, gb, ge, gi, gl, gr, hr, hu, ie, il, is, it, kw, kz, lb, li, lt, lu, lv, mc, md, me, mk, mr, mt, mu, nl, no, pl, pt, ro, rs, sa, se, si, sk, sm, tn, tr, vg</span></span>

### <a name="checksum"></a><span data-ttu-id="9d99e-2118">Checksum</span><span class="sxs-lookup"><span data-stu-id="9d99e-2118">Checksum</span></span>

<span data-ttu-id="9d99e-2119">Sì</span><span class="sxs-lookup"><span data-stu-id="9d99e-2119">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="9d99e-2120">Definizione</span><span class="sxs-lookup"><span data-stu-id="9d99e-2120">Definition</span></span>

<span data-ttu-id="9d99e-2121">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="9d99e-2121">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="9d99e-2122">La funzione Func_iban restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="9d99e-2122">The function Func_iban finds content that matches the pattern.</span></span>
- <span data-ttu-id="9d99e-2123">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="9d99e-2123">The checksum passes.</span></span>

```
<Entity id="e7dc4711-11b7-4cb0-b88b-2c394a771f0e" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_iban" />
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="9d99e-2124">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="9d99e-2124">Keywords</span></span>

<span data-ttu-id="9d99e-2125">None</span><span class="sxs-lookup"><span data-stu-id="9d99e-2125">None</span></span>

   
## <a name="ip-address"></a><span data-ttu-id="9d99e-2126">Indirizzo IP</span><span class="sxs-lookup"><span data-stu-id="9d99e-2126">IP Address</span></span>

### <a name="format"></a><span data-ttu-id="9d99e-2127">Formato</span><span class="sxs-lookup"><span data-stu-id="9d99e-2127">Format</span></span>

#### <a name="ipv4"></a><span data-ttu-id="9d99e-2128">IPv4:</span><span class="sxs-lookup"><span data-stu-id="9d99e-2128">IPv4:</span></span>
<span data-ttu-id="9d99e-2129">Modello complesso che rappresenta le versioni formattate (punti) e quelle non formattate (senza punti) degli indirizzi IPv4</span><span class="sxs-lookup"><span data-stu-id="9d99e-2129">Complex pattern which accounts for formatted (periods) and unformatted (no periods) versions of the IPv4 addresses</span></span>

#### <a name="ipv6"></a><span data-ttu-id="9d99e-2130">IPv6:</span><span class="sxs-lookup"><span data-stu-id="9d99e-2130">IPv6:</span></span>
<span data-ttu-id="9d99e-2131">Modello complesso che rappresenta i numeri dell'indirizzo IPv6 non formattati (include i due punti)</span><span class="sxs-lookup"><span data-stu-id="9d99e-2131">Complex pattern which accounts for formatted IPv6 numbers (which include colons)</span></span>

### <a name="pattern"></a><span data-ttu-id="9d99e-2132">Modello</span><span class="sxs-lookup"><span data-stu-id="9d99e-2132">Pattern</span></span>

### <a name="checksum"></a><span data-ttu-id="9d99e-2133">Checksum</span><span class="sxs-lookup"><span data-stu-id="9d99e-2133">Checksum</span></span>

<span data-ttu-id="9d99e-2134">No</span><span class="sxs-lookup"><span data-stu-id="9d99e-2134">No</span></span>

### <a name="definition"></a><span data-ttu-id="9d99e-2135">Definizione</span><span class="sxs-lookup"><span data-stu-id="9d99e-2135">Definition</span></span>

<span data-ttu-id="9d99e-2136">Nel caso di IPv6, un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="9d99e-2136">For IPv6, a DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="9d99e-2137">L'espressione regolare Regex_ipv6_address restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="9d99e-2137">The regular expression Regex_ipv6_address finds content that matches the pattern.</span></span>
- <span data-ttu-id="9d99e-2138">Non vengono trovate parole chiave da Keyword_ipaddress.</span><span class="sxs-lookup"><span data-stu-id="9d99e-2138">No keyword from Keyword_ipaddress is found.</span></span>

<span data-ttu-id="9d99e-2139">Nel caso di IPv4, un criterio DLP rileva questo tipo di informazioni con una probabilità del 95%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="9d99e-2139">For IPv4, a DLP policy is 95% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="9d99e-2140">L'espressione regolare Regex_ipv4_address restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="9d99e-2140">The regular expression Regex_ipv4_address finds content that matches the pattern.</span></span>
- <span data-ttu-id="9d99e-2141">Viene trovata una parola chiave da Keyword_ipaddress.</span><span class="sxs-lookup"><span data-stu-id="9d99e-2141">A keyword from Keyword_ipaddress is found.</span></span>

<span data-ttu-id="9d99e-2142">Nel caso di IPv6, un criterio DLP rileva questo tipo di informazioni con una probabilità del 95%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="9d99e-2142">For IPv6, a DLP policy is 95% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="9d99e-2143">L'espressione regolare Regex_ipv6_address restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="9d99e-2143">The regular expression Regex_ipv6_address finds content that matches the pattern.</span></span>
- <span data-ttu-id="9d99e-2144">Non vengono trovate parole chiave da Keyword_ipaddress.</span><span class="sxs-lookup"><span data-stu-id="9d99e-2144">No keyword from Keyword_ipaddress is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="9d99e-2145">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="9d99e-2145">Keywords</span></span>

#### <a name="keywordipaddress"></a><span data-ttu-id="9d99e-2146">Keyword_ipaddress</span><span class="sxs-lookup"><span data-stu-id="9d99e-2146">Keyword_ipaddress</span></span>

- <span data-ttu-id="9d99e-2147">IP (per questa parola chiave viene fatta distinzione tra maiuscole e minuscole)</span><span class="sxs-lookup"><span data-stu-id="9d99e-2147">IP (this keyword is case sensitive)</span></span>
- <span data-ttu-id="9d99e-2148">ip address
</span><span class="sxs-lookup"><span data-stu-id="9d99e-2148">ip address</span></span> 
- <span data-ttu-id="9d99e-2149">Indirizzi IP</span><span class="sxs-lookup"><span data-stu-id="9d99e-2149">ip addresses</span></span>
- <span data-ttu-id="9d99e-2150">internet protocol</span><span class="sxs-lookup"><span data-stu-id="9d99e-2150">internet protocol</span></span>
- <span data-ttu-id="9d99e-2151">
IP-כתובת ה
</span><span class="sxs-lookup"><span data-stu-id="9d99e-2151">IP-כתובת ה</span></span> 
   
## <a name="international-classification-of-diseases-icd-10-cm"></a><span data-ttu-id="9d99e-2152">Classificazione internazionale di malattie (ICD-10-CM)</span><span class="sxs-lookup"><span data-stu-id="9d99e-2152">International Classification of Diseases (ICD-10-CM)</span></span>

### <a name="format"></a><span data-ttu-id="9d99e-2153">Formato</span><span class="sxs-lookup"><span data-stu-id="9d99e-2153">Format</span></span>

<span data-ttu-id="9d99e-2154">Dizionario</span><span class="sxs-lookup"><span data-stu-id="9d99e-2154">Dictionary</span></span>

### <a name="pattern"></a><span data-ttu-id="9d99e-2155">Modello</span><span class="sxs-lookup"><span data-stu-id="9d99e-2155">Pattern</span></span>

<span data-ttu-id="9d99e-2156">Parola chiave</span><span class="sxs-lookup"><span data-stu-id="9d99e-2156">Keyword</span></span>

### <a name="checksum"></a><span data-ttu-id="9d99e-2157">Checksum</span><span class="sxs-lookup"><span data-stu-id="9d99e-2157">Checksum</span></span>

<span data-ttu-id="9d99e-2158">No</span><span class="sxs-lookup"><span data-stu-id="9d99e-2158">No</span></span>

### <a name="definition"></a><span data-ttu-id="9d99e-2159">Definizione</span><span class="sxs-lookup"><span data-stu-id="9d99e-2159">Definition</span></span>

<span data-ttu-id="9d99e-2160">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="9d99e-2160">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="9d99e-2161">È possibile trovare una parola chiave da Dictionary_icd_10_cm.</span><span class="sxs-lookup"><span data-stu-id="9d99e-2161">A keyword from Dictionary_icd_10_cm is found.</span></span>

```
      <!-- ICD-10 CM -->
      <Entity id="3356946c-6bb7-449b-b253-6ffa419c0ce7" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Dictionary_icd_10_cm" />
        </Pattern>
      </Entity>
```

<span data-ttu-id="9d99e-2162">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="9d99e-2162">Keywords</span></span>

<span data-ttu-id="9d99e-p135">Qualsiasi termini nel dizionario di parola chiave Dictionary_icd_10_cm, che si basa su [International classificazione di malattie, decimo revisione, modifica clinici (ICD-10-CM)](https://go.microsoft.com/fwlink/?linkid=852604). Questo tipo di ricerca solo il termine, non i codici di assicurazioni.</span><span class="sxs-lookup"><span data-stu-id="9d99e-p135">Any term from the Dictionary_icd_10_cm keyword dictionary, which is based on the [International Classification of Diseases, Tenth Revision, Clinical Modification (ICD-10-CM)](https://go.microsoft.com/fwlink/?linkid=852604). This type looks only for the term, not the insurance codes.</span></span>

   
## <a name="international-classification-of-diseases-icd-9-cm"></a><span data-ttu-id="9d99e-2165">Classificazione internazionale di malattie (ICD-9-CM)</span><span class="sxs-lookup"><span data-stu-id="9d99e-2165">International Classification of Diseases (ICD-9-CM)</span></span>

### <a name="format"></a><span data-ttu-id="9d99e-2166">Formato</span><span class="sxs-lookup"><span data-stu-id="9d99e-2166">Format</span></span>

<span data-ttu-id="9d99e-2167">Dizionario</span><span class="sxs-lookup"><span data-stu-id="9d99e-2167">Dictionary</span></span>

### <a name="pattern"></a><span data-ttu-id="9d99e-2168">Modello</span><span class="sxs-lookup"><span data-stu-id="9d99e-2168">Pattern</span></span>

<span data-ttu-id="9d99e-2169">Parola chiave</span><span class="sxs-lookup"><span data-stu-id="9d99e-2169">Keyword</span></span>

### <a name="checksum"></a><span data-ttu-id="9d99e-2170">Checksum</span><span class="sxs-lookup"><span data-stu-id="9d99e-2170">Checksum</span></span>

<span data-ttu-id="9d99e-2171">No</span><span class="sxs-lookup"><span data-stu-id="9d99e-2171">No</span></span>

### <a name="definition"></a><span data-ttu-id="9d99e-2172">Definizione</span><span class="sxs-lookup"><span data-stu-id="9d99e-2172">Definition</span></span>

<span data-ttu-id="9d99e-2173">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="9d99e-2173">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="9d99e-2174">È possibile trovare una parola chiave da Dictionary_icd_9_cm.</span><span class="sxs-lookup"><span data-stu-id="9d99e-2174">A keyword from Dictionary_icd_9_cm is found.</span></span>

```
      <Entity id="fa3f9c74-ee07-4c52-b5f2-085d6b2c0ec4" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Dictionary_icd_9_cm" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a><span data-ttu-id="9d99e-2175">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="9d99e-2175">Keywords</span></span>

<span data-ttu-id="9d99e-p136">Qualsiasi termini nel dizionario di parola chiave Dictionary_icd_9_cm, che si basa su [International classificazione di malattie, nono revisione, modifica clinici (ICD-9-CM)](https://go.microsoft.com/fwlink/?linkid=852605). Questo tipo di ricerca solo il termine, non i codici di assicurazioni.</span><span class="sxs-lookup"><span data-stu-id="9d99e-p136">Any term from the Dictionary_icd_9_cm keyword dictionary, which is based on the [International Classification of Diseases,Ninth Revision, Clinical Modification (ICD-9-CM)](https://go.microsoft.com/fwlink/?linkid=852605). This type looks only for the term, not the insurance codes.</span></span>
   
## <a name="ireland-personal-public-service-pps-number"></a><span data-ttu-id="9d99e-2178">Irlanda - Numero personale di servizio pubblico (PPS)</span><span class="sxs-lookup"><span data-stu-id="9d99e-2178">Ireland Personal Public Service (PPS) Number</span></span>

### <a name="format"></a><span data-ttu-id="9d99e-2179">Formato</span><span class="sxs-lookup"><span data-stu-id="9d99e-2179">Format</span></span>

<span data-ttu-id="9d99e-2180">Formato precedente (fino al 31 dicembre 2012):</span><span class="sxs-lookup"><span data-stu-id="9d99e-2180">Old format (until 31 Dec 2012):</span></span>
- <span data-ttu-id="9d99e-2181">Sette cifre seguite da 1-2 lettere </span><span class="sxs-lookup"><span data-stu-id="9d99e-2181">Seven digits followed by 1-2 letters</span></span> 

<span data-ttu-id="9d99e-2182">Nuovo formato (1 gennaio 2013 e una volta eseguito):</span><span class="sxs-lookup"><span data-stu-id="9d99e-2182">New format (1 Jan 2013 and after):</span></span>
- <span data-ttu-id="9d99e-2183">Sette cifre seguite da due lettere</span><span class="sxs-lookup"><span data-stu-id="9d99e-2183">Seven digits followed by two letters</span></span>

### <a name="pattern"></a><span data-ttu-id="9d99e-2184">Modello</span><span class="sxs-lookup"><span data-stu-id="9d99e-2184">Pattern</span></span>

<span data-ttu-id="9d99e-2185">Formato precedente (fino al 31 dicembre 2012):</span><span class="sxs-lookup"><span data-stu-id="9d99e-2185">Old format (until 31 Dec 2012):</span></span>
- <span data-ttu-id="9d99e-2186">Sette cifre</span><span class="sxs-lookup"><span data-stu-id="9d99e-2186">Seven digits</span></span> 
- <span data-ttu-id="9d99e-2187">1-2 lettere (senza distinzione tra maiuscole e minuscole)</span><span class="sxs-lookup"><span data-stu-id="9d99e-2187">1-2 letters (not case sensitive)</span></span> 

<span data-ttu-id="9d99e-2188">Nuovo formato (1 gennaio 2013 e una volta eseguito):</span><span class="sxs-lookup"><span data-stu-id="9d99e-2188">New format (1 Jan 2013 and after):</span></span>
- <span data-ttu-id="9d99e-2189">Sette cifre</span><span class="sxs-lookup"><span data-stu-id="9d99e-2189">Seven digits</span></span> 
- <span data-ttu-id="9d99e-2190">Una lettera (senza distinzione tra maiuscole e minuscole) che corrisponde a una cifra di controllo alfabetica </span><span class="sxs-lookup"><span data-stu-id="9d99e-2190">A letter (not case sensitive) which is an alphabetic check digit</span></span> 
- <span data-ttu-id="9d99e-2191">La lettera "A" o "H" (senza distinzione tra maiuscole e minuscole)</span><span class="sxs-lookup"><span data-stu-id="9d99e-2191">The letter "A" or "H" (not case sensitive)</span></span>

### <a name="checksum"></a><span data-ttu-id="9d99e-2192">Checksum</span><span class="sxs-lookup"><span data-stu-id="9d99e-2192">Checksum</span></span>

<span data-ttu-id="9d99e-2193">Sì</span><span class="sxs-lookup"><span data-stu-id="9d99e-2193">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="9d99e-2194">Definizione</span><span class="sxs-lookup"><span data-stu-id="9d99e-2194">Definition</span></span>

<span data-ttu-id="9d99e-2195">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="9d99e-2195">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="9d99e-2196">La funzione Func_ireland_pps consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="9d99e-2196">The function Func_ireland_pps finds content that matches the pattern.</span></span>
- <span data-ttu-id="9d99e-2197">Si verifica una delle situazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="9d99e-2197">One of the following is true:</span></span>
    - <span data-ttu-id="9d99e-2198">È possibile trovare una parola chiave da Keyword_ireland_pps.</span><span class="sxs-lookup"><span data-stu-id="9d99e-2198">A keyword from Keyword_ireland_pps is found.</span></span>
    - <span data-ttu-id="9d99e-2199">La funzione Func_eu_date rileva una data nel formato corretto.</span><span class="sxs-lookup"><span data-stu-id="9d99e-2199">The function Func_eu_date finds a date in the right date format.</span></span>
- <span data-ttu-id="9d99e-2200">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="9d99e-2200">The checksum passes.</span></span>

<span data-ttu-id="9d99e-2201">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 65%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="9d99e-2201">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="9d99e-2202">La funzione Func_ireland_pps consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="9d99e-2202">The function Func_ireland_pps finds content that matches the pattern.</span></span>
- <span data-ttu-id="9d99e-2203">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="9d99e-2203">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="9d99e-2204">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="9d99e-2204">Keywords</span></span>

#### <a name="keywordirelandpps"></a><span data-ttu-id="9d99e-2205">Keyword_ireland_pps</span><span class="sxs-lookup"><span data-stu-id="9d99e-2205">Keyword_ireland_pps</span></span>

- <span data-ttu-id="9d99e-2206">Numero personale di servizio pubblico 
</span><span class="sxs-lookup"><span data-stu-id="9d99e-2206">Personal Public Service Number</span></span> 
- <span data-ttu-id="9d99e-2207">Numero PPS
</span><span class="sxs-lookup"><span data-stu-id="9d99e-2207">PPS Number</span></span> 
- <span data-ttu-id="9d99e-2208">Num. PPS
</span><span class="sxs-lookup"><span data-stu-id="9d99e-2208">PPS Num</span></span> 
- <span data-ttu-id="9d99e-2209">N° PPS
</span><span class="sxs-lookup"><span data-stu-id="9d99e-2209">PPS No.</span></span> 
- <span data-ttu-id="9d99e-2210">PPS #
</span><span class="sxs-lookup"><span data-stu-id="9d99e-2210">PPS #</span></span> 
- <span data-ttu-id="9d99e-2211">PPS#
</span><span class="sxs-lookup"><span data-stu-id="9d99e-2211">PPS#</span></span> 
- <span data-ttu-id="9d99e-2212">PPSN
</span><span class="sxs-lookup"><span data-stu-id="9d99e-2212">PPSN</span></span> 
- <span data-ttu-id="9d99e-2213">Scheda servizi pubblici
</span><span class="sxs-lookup"><span data-stu-id="9d99e-2213">Public Services Card</span></span> 
- <span data-ttu-id="9d99e-2214">Uimhir Phearsanta Seirbhíse Poiblí
</span><span class="sxs-lookup"><span data-stu-id="9d99e-2214">Uimhir Phearsanta Seirbhíse Poiblí</span></span> 
- <span data-ttu-id="9d99e-p137">Uimh. PSP
</span><span class="sxs-lookup"><span data-stu-id="9d99e-p137">Uimh. PSP</span></span> 
- <span data-ttu-id="9d99e-2217">PSP
</span><span class="sxs-lookup"><span data-stu-id="9d99e-2217">PSP</span></span> 
   
## <a name="israel-bank-account-number"></a><span data-ttu-id="9d99e-2218">Israele - Numero di conto bancario</span><span class="sxs-lookup"><span data-stu-id="9d99e-2218">Israel Bank Account Number</span></span>

### <a name="format"></a><span data-ttu-id="9d99e-2219">Formato</span><span class="sxs-lookup"><span data-stu-id="9d99e-2219">Format</span></span>

<span data-ttu-id="9d99e-2220">13 cifre</span><span class="sxs-lookup"><span data-stu-id="9d99e-2220">13 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="9d99e-2221">Modello</span><span class="sxs-lookup"><span data-stu-id="9d99e-2221">Pattern</span></span>

<span data-ttu-id="9d99e-2222">Formattato:</span><span class="sxs-lookup"><span data-stu-id="9d99e-2222">Formatted:</span></span>
- <span data-ttu-id="9d99e-2223">Due cifre</span><span class="sxs-lookup"><span data-stu-id="9d99e-2223">Two digits</span></span> 
- <span data-ttu-id="9d99e-2224">Un trattino</span><span class="sxs-lookup"><span data-stu-id="9d99e-2224">A dash</span></span> 
- <span data-ttu-id="9d99e-2225">Tre cifre</span><span class="sxs-lookup"><span data-stu-id="9d99e-2225">Three digits</span></span> 
- <span data-ttu-id="9d99e-2226">Un trattino</span><span class="sxs-lookup"><span data-stu-id="9d99e-2226">A dash</span></span> 
- <span data-ttu-id="9d99e-2227">Otto cifre</span><span class="sxs-lookup"><span data-stu-id="9d99e-2227">Eight digits</span></span>

<span data-ttu-id="9d99e-2228">Non formattato:</span><span class="sxs-lookup"><span data-stu-id="9d99e-2228">Unformatted:</span></span>
- <span data-ttu-id="9d99e-2229">13 cifre consecutive</span><span class="sxs-lookup"><span data-stu-id="9d99e-2229">13 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="9d99e-2230">Checksum</span><span class="sxs-lookup"><span data-stu-id="9d99e-2230">Checksum</span></span>

<span data-ttu-id="9d99e-2231">No</span><span class="sxs-lookup"><span data-stu-id="9d99e-2231">No</span></span>

### <a name="definition"></a><span data-ttu-id="9d99e-2232">Definizione</span><span class="sxs-lookup"><span data-stu-id="9d99e-2232">Definition</span></span>

<span data-ttu-id="9d99e-2233">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="9d99e-2233">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="9d99e-2234">L'espressione regolare Regex_israel_bank_account_number restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="9d99e-2234">The regular expression Regex_israel_bank_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="9d99e-2235">Viene trovata una parola chiave da Keyword_israel_bank_account_number.</span><span class="sxs-lookup"><span data-stu-id="9d99e-2235">A keyword from Keyword_israel_bank_account_number is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="9d99e-2236">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="9d99e-2236">Keywords</span></span>

#### <a name="keywordisraelbankaccountnumber"></a><span data-ttu-id="9d99e-2237">Keyword_israel_bank_account_number</span><span class="sxs-lookup"><span data-stu-id="9d99e-2237">Keyword_israel_bank_account_number</span></span>

- <span data-ttu-id="9d99e-2238">Bank Account Number
</span><span class="sxs-lookup"><span data-stu-id="9d99e-2238">Bank Account Number</span></span> 
- <span data-ttu-id="9d99e-2239">Bank Account
</span><span class="sxs-lookup"><span data-stu-id="9d99e-2239">Bank Account</span></span> 
- <span data-ttu-id="9d99e-2240">Account Number
</span><span class="sxs-lookup"><span data-stu-id="9d99e-2240">Account Number</span></span> 
- <span data-ttu-id="9d99e-2241">מספר חשבון בנק
</span><span class="sxs-lookup"><span data-stu-id="9d99e-2241">מספר חשבון בנק</span></span> 
   
## <a name="israel-national-id"></a><span data-ttu-id="9d99e-2242">Carta di identità (Israele)</span><span class="sxs-lookup"><span data-stu-id="9d99e-2242">Israel National ID</span></span>

### <a name="format"></a><span data-ttu-id="9d99e-2243">Formato</span><span class="sxs-lookup"><span data-stu-id="9d99e-2243">Format</span></span>

<span data-ttu-id="9d99e-2244">9 cifre</span><span class="sxs-lookup"><span data-stu-id="9d99e-2244">Nine digits</span></span>

### <a name="pattern"></a><span data-ttu-id="9d99e-2245">Modello</span><span class="sxs-lookup"><span data-stu-id="9d99e-2245">Pattern</span></span>

<span data-ttu-id="9d99e-2246">9 cifre consecutive</span><span class="sxs-lookup"><span data-stu-id="9d99e-2246">Nine consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="9d99e-2247">Checksum</span><span class="sxs-lookup"><span data-stu-id="9d99e-2247">Checksum</span></span>

<span data-ttu-id="9d99e-2248">Sì</span><span class="sxs-lookup"><span data-stu-id="9d99e-2248">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="9d99e-2249">Definizione</span><span class="sxs-lookup"><span data-stu-id="9d99e-2249">Definition</span></span>

<span data-ttu-id="9d99e-2250">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="9d99e-2250">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="9d99e-2251">La funzione Func_israeli_national_id_number restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="9d99e-2251">The function Func_israeli_national_id_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="9d99e-2252">Viene trovata una parola chiave da Keyword_Israel_National_ID.</span><span class="sxs-lookup"><span data-stu-id="9d99e-2252">A keyword from Keyword_Israel_National_ID is found.</span></span>
- <span data-ttu-id="9d99e-2253">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="9d99e-2253">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="9d99e-2254">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="9d99e-2254">Keywords</span></span>

#### <a name="keywordisraelnationalid"></a><span data-ttu-id="9d99e-2255">Keyword_Israel_National_ID</span><span class="sxs-lookup"><span data-stu-id="9d99e-2255">Keyword_Israel_National_ID</span></span>

- <span data-ttu-id="9d99e-2256">מספר זהות
</span><span class="sxs-lookup"><span data-stu-id="9d99e-2256">מספר זהות</span></span> 
- <span data-ttu-id="9d99e-2257">National ID Number</span><span class="sxs-lookup"><span data-stu-id="9d99e-2257">National ID Number</span></span>
   
## <a name="italy-drivers-license-number"></a><span data-ttu-id="9d99e-2258">Italia - Numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="9d99e-2258">Italy Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="9d99e-2259">Formato</span><span class="sxs-lookup"><span data-stu-id="9d99e-2259">Format</span></span>

<span data-ttu-id="9d99e-2260">Una combinazione di 10 lettere e cifre</span><span class="sxs-lookup"><span data-stu-id="9d99e-2260">A combination of 10 letters and digits</span></span>

### <a name="pattern"></a><span data-ttu-id="9d99e-2261">Modello</span><span class="sxs-lookup"><span data-stu-id="9d99e-2261">Pattern</span></span>

- <span data-ttu-id="9d99e-2262">Una combinazione di 10 lettere e cifre:</span><span class="sxs-lookup"><span data-stu-id="9d99e-2262">A combination of 10 letters and digits:</span></span>
- <span data-ttu-id="9d99e-2263">Una lettera (senza distinzione tra maiuscole/minuscole)</span><span class="sxs-lookup"><span data-stu-id="9d99e-2263">One letter (not case sensitive)</span></span> 
- <span data-ttu-id="9d99e-2264">La lettera "A" o "V" (senza distinzione tra maiuscole/minuscole)</span><span class="sxs-lookup"><span data-stu-id="9d99e-2264">The letter "A" or "V" (not case sensitive)</span></span> 
- <span data-ttu-id="9d99e-2265">7 lettere (senza distinzione tra maiuscole/minuscole), cifre o carattere di sottolineatura</span><span class="sxs-lookup"><span data-stu-id="9d99e-2265">Seven letters (not case sensitive), digits, or the underscore character</span></span> 
- <span data-ttu-id="9d99e-2266">Una lettera (senza distinzione tra maiuscole/minuscole)</span><span class="sxs-lookup"><span data-stu-id="9d99e-2266">One letter (not case sensitive)</span></span>

### <a name="checksum"></a><span data-ttu-id="9d99e-2267">Checksum</span><span class="sxs-lookup"><span data-stu-id="9d99e-2267">Checksum</span></span>

<span data-ttu-id="9d99e-2268">No</span><span class="sxs-lookup"><span data-stu-id="9d99e-2268">No</span></span>

### <a name="definition"></a><span data-ttu-id="9d99e-2269">Definizione</span><span class="sxs-lookup"><span data-stu-id="9d99e-2269">Definition</span></span>

<span data-ttu-id="9d99e-2270">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="9d99e-2270">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="9d99e-2271">L'espressione regolare Regex_italy_drivers_license_number restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="9d99e-2271">The regular expression Regex_italy_drivers_license_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="9d99e-2272">Viene trovata una parola chiave da Keyword_italy_drivers_license_number.</span><span class="sxs-lookup"><span data-stu-id="9d99e-2272">A keyword from Keyword_italy_drivers_license_number is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="9d99e-2273">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="9d99e-2273">Keywords</span></span>

#### <a name="keyworditalydriverslicensenumber"></a><span data-ttu-id="9d99e-2274">Keyword_italy_drivers_license_number</span><span class="sxs-lookup"><span data-stu-id="9d99e-2274">Keyword_italy_drivers_license_number</span></span>

- <span data-ttu-id="9d99e-2275">numero di patente di guida
</span><span class="sxs-lookup"><span data-stu-id="9d99e-2275">numero di patente di guida</span></span> 
- <span data-ttu-id="9d99e-2276">patente di guida
</span><span class="sxs-lookup"><span data-stu-id="9d99e-2276">patente di guida</span></span> 
   
## <a name="japan-bank-account-number"></a><span data-ttu-id="9d99e-2277">Giappone - Numero di conto bancario</span><span class="sxs-lookup"><span data-stu-id="9d99e-2277">Japan Bank Account Number</span></span>

### <a name="format"></a><span data-ttu-id="9d99e-2278">Formato</span><span class="sxs-lookup"><span data-stu-id="9d99e-2278">Format</span></span>

<span data-ttu-id="9d99e-2279">Sette o otto cifre</span><span class="sxs-lookup"><span data-stu-id="9d99e-2279">Seven or eight digits</span></span>

### <a name="pattern"></a><span data-ttu-id="9d99e-2280">Modello</span><span class="sxs-lookup"><span data-stu-id="9d99e-2280">Pattern</span></span>

<span data-ttu-id="9d99e-2281">Numero di conto corrente:</span><span class="sxs-lookup"><span data-stu-id="9d99e-2281">Bank account number:</span></span>
- <span data-ttu-id="9d99e-2282">Sette o otto cifre</span><span class="sxs-lookup"><span data-stu-id="9d99e-2282">Seven or eight digits</span></span>
- <span data-ttu-id="9d99e-2283">Codice della filiale del conto corrente:</span><span class="sxs-lookup"><span data-stu-id="9d99e-2283">Bank account branch code:</span></span>
- <span data-ttu-id="9d99e-2284">Quattro cifre</span><span class="sxs-lookup"><span data-stu-id="9d99e-2284">Four digits</span></span> 
- <span data-ttu-id="9d99e-2285">Uno spazio o un trattino (facoltativo)</span><span class="sxs-lookup"><span data-stu-id="9d99e-2285">A space or dash (optional)</span></span> 
- <span data-ttu-id="9d99e-2286">Tre cifre</span><span class="sxs-lookup"><span data-stu-id="9d99e-2286">Three digits</span></span>

<span data-ttu-id="9d99e-2287">Checksum</span><span class="sxs-lookup"><span data-stu-id="9d99e-2287">Checksum</span></span>

<span data-ttu-id="9d99e-2288">No</span><span class="sxs-lookup"><span data-stu-id="9d99e-2288">No</span></span>

### <a name="definition"></a><span data-ttu-id="9d99e-2289">Definizione</span><span class="sxs-lookup"><span data-stu-id="9d99e-2289">Definition</span></span>

<span data-ttu-id="9d99e-2290">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="9d99e-2290">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="9d99e-2291">La funzione Func_jp_bank_account restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="9d99e-2291">The function Func_jp_bank_account finds content that matches the pattern.</span></span>
- <span data-ttu-id="9d99e-2292">Viene trovata una parola chiave da Keyword_jp_bank_account.</span><span class="sxs-lookup"><span data-stu-id="9d99e-2292">A keyword from Keyword_jp_bank_account is found.</span></span>
- <span data-ttu-id="9d99e-2293">Si verifica una delle situazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="9d99e-2293">One of the following is true:</span></span>
- <span data-ttu-id="9d99e-2294">La funzione Func_jp_bank_account_branch_code restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="9d99e-2294">The function Func_jp_bank_account_branch_code finds content that matches the pattern.</span></span>
- <span data-ttu-id="9d99e-2295">Viene trovata una parola chiave da Keyword_jp_bank_branch_code.</span><span class="sxs-lookup"><span data-stu-id="9d99e-2295">A keyword from Keyword_jp_bank_branch_code is found.</span></span>

<span data-ttu-id="9d99e-2296">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="9d99e-2296">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="9d99e-2297">La funzione Func_jp_bank_account restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="9d99e-2297">The function Func_jp_bank_account finds content that matches the pattern.</span></span>
- <span data-ttu-id="9d99e-2298">Viene trovata una parola chiave da Keyword_jp_bank_account.</span><span class="sxs-lookup"><span data-stu-id="9d99e-2298">A keyword from Keyword_jp_bank_account is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="9d99e-2299">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="9d99e-2299">Keywords</span></span>

#### <a name="keywordjpbankaccount"></a><span data-ttu-id="9d99e-2300">Keyword_jp_bank_account</span><span class="sxs-lookup"><span data-stu-id="9d99e-2300">Keyword_jp_bank_account</span></span>

- <span data-ttu-id="9d99e-2301">Checking Account Number
</span><span class="sxs-lookup"><span data-stu-id="9d99e-2301">Checking Account Number</span></span> 
- <span data-ttu-id="9d99e-2302">Checking Account
</span><span class="sxs-lookup"><span data-stu-id="9d99e-2302">Checking Account</span></span> 
- <span data-ttu-id="9d99e-2303">Checking Account #
</span><span class="sxs-lookup"><span data-stu-id="9d99e-2303">Checking Account #</span></span> 
- <span data-ttu-id="9d99e-2304">Checking Acct Number
</span><span class="sxs-lookup"><span data-stu-id="9d99e-2304">Checking Acct Number</span></span> 
- <span data-ttu-id="9d99e-2305">Checking Acct #
</span><span class="sxs-lookup"><span data-stu-id="9d99e-2305">Checking Acct #</span></span> 
- <span data-ttu-id="9d99e-2306">Checking Acct No.
</span><span class="sxs-lookup"><span data-stu-id="9d99e-2306">Checking Acct No.</span></span> 
- <span data-ttu-id="9d99e-2307">Checking Account No.
</span><span class="sxs-lookup"><span data-stu-id="9d99e-2307">Checking Account No.</span></span> 
- <span data-ttu-id="9d99e-2308">Bank Account Number
</span><span class="sxs-lookup"><span data-stu-id="9d99e-2308">Bank Account Number</span></span> 
- <span data-ttu-id="9d99e-2309">Bank Account
</span><span class="sxs-lookup"><span data-stu-id="9d99e-2309">Bank Account</span></span> 
- <span data-ttu-id="9d99e-2310">Bank Account #
</span><span class="sxs-lookup"><span data-stu-id="9d99e-2310">Bank Account #</span></span> 
- <span data-ttu-id="9d99e-2311">Bank Acct Number
</span><span class="sxs-lookup"><span data-stu-id="9d99e-2311">Bank Acct Number</span></span> 
- <span data-ttu-id="9d99e-2312">Bank Acct #
</span><span class="sxs-lookup"><span data-stu-id="9d99e-2312">Bank Acct #</span></span> 
- <span data-ttu-id="9d99e-2313">Bank Acct No.
</span><span class="sxs-lookup"><span data-stu-id="9d99e-2313">Bank Acct No.</span></span> 
- <span data-ttu-id="9d99e-2314">Bank Account No.
</span><span class="sxs-lookup"><span data-stu-id="9d99e-2314">Bank Account No.</span></span> 
- <span data-ttu-id="9d99e-2315">Savings Account Number
</span><span class="sxs-lookup"><span data-stu-id="9d99e-2315">Savings Account Number</span></span> 
- <span data-ttu-id="9d99e-2316">Account di risparmio</span><span class="sxs-lookup"><span data-stu-id="9d99e-2316">Savings Account</span></span> 
- <span data-ttu-id="9d99e-2317">Savings Account #
</span><span class="sxs-lookup"><span data-stu-id="9d99e-2317">Savings Account #</span></span> 
- <span data-ttu-id="9d99e-2318">Savings Acct Number
</span><span class="sxs-lookup"><span data-stu-id="9d99e-2318">Savings Acct Number</span></span> 
- <span data-ttu-id="9d99e-2319">Savings Acct #
</span><span class="sxs-lookup"><span data-stu-id="9d99e-2319">Savings Acct #</span></span> 
- <span data-ttu-id="9d99e-2320">Savings Acct No.
</span><span class="sxs-lookup"><span data-stu-id="9d99e-2320">Savings Acct No.</span></span> 
- <span data-ttu-id="9d99e-2321">Savings Account No.
</span><span class="sxs-lookup"><span data-stu-id="9d99e-2321">Savings Account No.</span></span> 
- <span data-ttu-id="9d99e-2322">Debit Account Number
</span><span class="sxs-lookup"><span data-stu-id="9d99e-2322">Debit Account Number</span></span> 
- <span data-ttu-id="9d99e-2323">Debit Account
</span><span class="sxs-lookup"><span data-stu-id="9d99e-2323">Debit Account</span></span> 
- <span data-ttu-id="9d99e-2324">Debit Account #
</span><span class="sxs-lookup"><span data-stu-id="9d99e-2324">Debit Account #</span></span> 
- <span data-ttu-id="9d99e-2325">Debit Acct Number
</span><span class="sxs-lookup"><span data-stu-id="9d99e-2325">Debit Acct Number</span></span> 
- <span data-ttu-id="9d99e-2326">Debit Acct #
</span><span class="sxs-lookup"><span data-stu-id="9d99e-2326">Debit Acct #</span></span> 
- <span data-ttu-id="9d99e-2327">Debit Acct No.
</span><span class="sxs-lookup"><span data-stu-id="9d99e-2327">Debit Acct No.</span></span> 
- <span data-ttu-id="9d99e-2328">Debit Account No.
</span><span class="sxs-lookup"><span data-stu-id="9d99e-2328">Debit Account No.</span></span> 
- <span data-ttu-id="9d99e-2329">口座番号を当座預金口座の確認
</span><span class="sxs-lookup"><span data-stu-id="9d99e-2329">口座番号を当座預金口座の確認</span></span> 
- <span data-ttu-id="9d99e-2330">＃アカウントの確認、勘定番号の確認
</span><span class="sxs-lookup"><span data-stu-id="9d99e-2330">＃アカウントの確認、勘定番号の確認</span></span> 
- <span data-ttu-id="9d99e-2331">＃勘定の確認
</span><span class="sxs-lookup"><span data-stu-id="9d99e-2331">＃勘定の確認</span></span> 
- <span data-ttu-id="9d99e-2332">勘定番号の確認
</span><span class="sxs-lookup"><span data-stu-id="9d99e-2332">勘定番号の確認</span></span> 
- <span data-ttu-id="9d99e-2333">口座番号の確認
</span><span class="sxs-lookup"><span data-stu-id="9d99e-2333">口座番号の確認</span></span> 
- <span data-ttu-id="9d99e-2334">銀行口座番号</span><span class="sxs-lookup"><span data-stu-id="9d99e-2334">銀行口座番号</span></span> 
- <span data-ttu-id="9d99e-2335">銀行口座</span><span class="sxs-lookup"><span data-stu-id="9d99e-2335">銀行口座</span></span> 
- <span data-ttu-id="9d99e-2336">銀行口座＃
</span><span class="sxs-lookup"><span data-stu-id="9d99e-2336">銀行口座＃</span></span> 
- <span data-ttu-id="9d99e-2337">銀行の勘定番号
</span><span class="sxs-lookup"><span data-stu-id="9d99e-2337">銀行の勘定番号</span></span> 
- <span data-ttu-id="9d99e-2338">銀行のacct＃
</span><span class="sxs-lookup"><span data-stu-id="9d99e-2338">銀行のacct＃</span></span> 
- <span data-ttu-id="9d99e-2339">銀行の勘定いいえ
</span><span class="sxs-lookup"><span data-stu-id="9d99e-2339">銀行の勘定いいえ</span></span> 
- <span data-ttu-id="9d99e-2340">銀行口座番号</span><span class="sxs-lookup"><span data-stu-id="9d99e-2340">銀行口座番号</span></span>
- <span data-ttu-id="9d99e-2341">
普通預金口座番号
</span><span class="sxs-lookup"><span data-stu-id="9d99e-2341">普通預金口座番号</span></span> 
- <span data-ttu-id="9d99e-2342">預金口座
</span><span class="sxs-lookup"><span data-stu-id="9d99e-2342">預金口座</span></span> 
- <span data-ttu-id="9d99e-2343">貯蓄口座＃
</span><span class="sxs-lookup"><span data-stu-id="9d99e-2343">貯蓄口座＃</span></span> 
- <span data-ttu-id="9d99e-2344">貯蓄勘定の数
</span><span class="sxs-lookup"><span data-stu-id="9d99e-2344">貯蓄勘定の数</span></span> 
- <span data-ttu-id="9d99e-2345">貯蓄勘定＃
</span><span class="sxs-lookup"><span data-stu-id="9d99e-2345">貯蓄勘定＃</span></span> 
- <span data-ttu-id="9d99e-2346">貯蓄勘定番号
</span><span class="sxs-lookup"><span data-stu-id="9d99e-2346">貯蓄勘定番号</span></span> 
- <span data-ttu-id="9d99e-2347">普通預金口座番号
</span><span class="sxs-lookup"><span data-stu-id="9d99e-2347">普通預金口座番号</span></span> 
- <span data-ttu-id="9d99e-2348">引き落とし口座番号
</span><span class="sxs-lookup"><span data-stu-id="9d99e-2348">引き落とし口座番号</span></span> 
- <span data-ttu-id="9d99e-2349">口座番号</span><span class="sxs-lookup"><span data-stu-id="9d99e-2349">口座番号</span></span> 
- <span data-ttu-id="9d99e-2350">口座番号＃
</span><span class="sxs-lookup"><span data-stu-id="9d99e-2350">口座番号＃</span></span> 
- <span data-ttu-id="9d99e-2351">デビットのacct番号
</span><span class="sxs-lookup"><span data-stu-id="9d99e-2351">デビットのacct番号</span></span> 
- <span data-ttu-id="9d99e-2352">デビット勘定＃
</span><span class="sxs-lookup"><span data-stu-id="9d99e-2352">デビット勘定＃</span></span> 
- <span data-ttu-id="9d99e-2353">デビットACCTの番号
</span><span class="sxs-lookup"><span data-stu-id="9d99e-2353">デビットACCTの番号</span></span> 
- <span data-ttu-id="9d99e-2354">デビット口座番号
</span><span class="sxs-lookup"><span data-stu-id="9d99e-2354">デビット口座番号</span></span> 

#### <a name="keywordjpbankbranchcode"></a><span data-ttu-id="9d99e-2355">Keyword_jp_bank_branch_code</span><span class="sxs-lookup"><span data-stu-id="9d99e-2355">Keyword_jp_bank_branch_code</span></span>

<span data-ttu-id="9d99e-2356">Otemachi</span><span class="sxs-lookup"><span data-stu-id="9d99e-2356">Otemachi</span></span>

## <a name="japan-drivers-license-number"></a><span data-ttu-id="9d99e-2357">Giappone - Numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="9d99e-2357">Japan Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="9d99e-2358">Formato</span><span class="sxs-lookup"><span data-stu-id="9d99e-2358">Format</span></span>

<span data-ttu-id="9d99e-2359">12 cifre</span><span class="sxs-lookup"><span data-stu-id="9d99e-2359">12 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="9d99e-2360">Modello</span><span class="sxs-lookup"><span data-stu-id="9d99e-2360">Pattern</span></span>

<span data-ttu-id="9d99e-2361">12 cifre consecutive</span><span class="sxs-lookup"><span data-stu-id="9d99e-2361">12 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="9d99e-2362">Checksum</span><span class="sxs-lookup"><span data-stu-id="9d99e-2362">Checksum</span></span>

<span data-ttu-id="9d99e-2363">No</span><span class="sxs-lookup"><span data-stu-id="9d99e-2363">No</span></span>

### <a name="definition"></a><span data-ttu-id="9d99e-2364">Definizione</span><span class="sxs-lookup"><span data-stu-id="9d99e-2364">Definition</span></span>

<span data-ttu-id="9d99e-2365">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="9d99e-2365">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="9d99e-2366">La funzione Func_jp_drivers_license_number restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="9d99e-2366">The function Func_jp_drivers_license_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="9d99e-2367">Viene trovata una parola chiave da Keyword_jp_drivers_license_number.</span><span class="sxs-lookup"><span data-stu-id="9d99e-2367">A keyword from Keyword_jp_drivers_license_number is found.</span></span>

```
<!-- Japan Driver's License Number -->
<Entity id="c6011143-d087-451c-8313-7f6d4aed2270" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_jp_drivers_license_number" />
        <Match idRef ="Keyword_jp_drivers_license_number" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="9d99e-2368">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="9d99e-2368">Keywords</span></span>

#### <a name="keywordjpdriverslicensenumber"></a><span data-ttu-id="9d99e-2369">Keyword_jp_drivers_license_number</span><span class="sxs-lookup"><span data-stu-id="9d99e-2369">Keyword_jp_drivers_license_number</span></span>

- <span data-ttu-id="9d99e-2370">dl#
</span><span class="sxs-lookup"><span data-stu-id="9d99e-2370">dl#</span></span> 
- <span data-ttu-id="9d99e-2371">DL #</span><span class="sxs-lookup"><span data-stu-id="9d99e-2371">DL＃</span></span> 
- <span data-ttu-id="9d99e-2372">le liste di distribuzione #</span><span class="sxs-lookup"><span data-stu-id="9d99e-2372">dls#</span></span> 
- <span data-ttu-id="9d99e-2373">LE LISTE DI DISTRIBUZIONE #</span><span class="sxs-lookup"><span data-stu-id="9d99e-2373">DLS＃</span></span> 
- <span data-ttu-id="9d99e-2374">patente</span><span class="sxs-lookup"><span data-stu-id="9d99e-2374">driver license</span></span> 
- <span data-ttu-id="9d99e-2375">licenze di driver</span><span class="sxs-lookup"><span data-stu-id="9d99e-2375">driver licenses</span></span> 
- <span data-ttu-id="9d99e-2376">patente di Guida</span><span class="sxs-lookup"><span data-stu-id="9d99e-2376">drivers license</span></span> 
- <span data-ttu-id="9d99e-2377">patente</span><span class="sxs-lookup"><span data-stu-id="9d99e-2377">driver's license</span></span> 
- <span data-ttu-id="9d99e-2378">licenze di driver</span><span class="sxs-lookup"><span data-stu-id="9d99e-2378">drivers licenses</span></span> 
- <span data-ttu-id="9d99e-2379">licenze della patente di Guida</span><span class="sxs-lookup"><span data-stu-id="9d99e-2379">driver's licenses</span></span> 
- <span data-ttu-id="9d99e-2380">driving licence
</span><span class="sxs-lookup"><span data-stu-id="9d99e-2380">driving licence</span></span> 
- <span data-ttu-id="9d99e-2381">LIC #</span><span class="sxs-lookup"><span data-stu-id="9d99e-2381">lic#</span></span> 
- <span data-ttu-id="9d99e-2382">LIC #</span><span class="sxs-lookup"><span data-stu-id="9d99e-2382">LIC＃</span></span> 
- <span data-ttu-id="9d99e-2383">lics#
</span><span class="sxs-lookup"><span data-stu-id="9d99e-2383">lics#</span></span> 
- <span data-ttu-id="9d99e-2384">id dello stato</span><span class="sxs-lookup"><span data-stu-id="9d99e-2384">state id</span></span> 
- <span data-ttu-id="9d99e-2385">state identification
</span><span class="sxs-lookup"><span data-stu-id="9d99e-2385">state identification</span></span> 
- <span data-ttu-id="9d99e-2386">state identification number
</span><span class="sxs-lookup"><span data-stu-id="9d99e-2386">state identification number</span></span> 
- <span data-ttu-id="9d99e-2387">低所得国＃
</span><span class="sxs-lookup"><span data-stu-id="9d99e-2387">低所得国＃</span></span> 
- <span data-ttu-id="9d99e-2388">免許証
</span><span class="sxs-lookup"><span data-stu-id="9d99e-2388">免許証</span></span> 
- <span data-ttu-id="9d99e-2389">状態ID</span><span class="sxs-lookup"><span data-stu-id="9d99e-2389">状態ID</span></span>
- <span data-ttu-id="9d99e-2390">
状態の識別
</span><span class="sxs-lookup"><span data-stu-id="9d99e-2390">状態の識別</span></span> 
- <span data-ttu-id="9d99e-2391">状態の識別番号
</span><span class="sxs-lookup"><span data-stu-id="9d99e-2391">状態の識別番号</span></span> 
- <span data-ttu-id="9d99e-2392">運転免許
</span><span class="sxs-lookup"><span data-stu-id="9d99e-2392">運転免許</span></span> 
- <span data-ttu-id="9d99e-2393">運転免許証
</span><span class="sxs-lookup"><span data-stu-id="9d99e-2393">運転免許証</span></span> 
- <span data-ttu-id="9d99e-2394">運転免許証番号
</span><span class="sxs-lookup"><span data-stu-id="9d99e-2394">運転免許証番号</span></span> 
   
## <a name="japan-passport-number"></a><span data-ttu-id="9d99e-2395">Giappone - Numero di passaporto</span><span class="sxs-lookup"><span data-stu-id="9d99e-2395">Japan Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="9d99e-2396">Formato</span><span class="sxs-lookup"><span data-stu-id="9d99e-2396">Format</span></span>

<span data-ttu-id="9d99e-2397">Due lettere seguite da 7 cifre</span><span class="sxs-lookup"><span data-stu-id="9d99e-2397">Two letters followed by seven digits</span></span>

### <a name="pattern"></a><span data-ttu-id="9d99e-2398">Modello</span><span class="sxs-lookup"><span data-stu-id="9d99e-2398">Pattern</span></span>

<span data-ttu-id="9d99e-2399">Due lettere (senza distinzione tra maiuscole/minuscole) seguite da sette cifre</span><span class="sxs-lookup"><span data-stu-id="9d99e-2399">Two letters (not case sensitive) followed by seven digits</span></span>

### <a name="checksum"></a><span data-ttu-id="9d99e-2400">Checksum</span><span class="sxs-lookup"><span data-stu-id="9d99e-2400">Checksum</span></span>

<span data-ttu-id="9d99e-2401">No</span><span class="sxs-lookup"><span data-stu-id="9d99e-2401">No</span></span>

### <a name="definition"></a><span data-ttu-id="9d99e-2402">Definizione</span><span class="sxs-lookup"><span data-stu-id="9d99e-2402">Definition</span></span>

<span data-ttu-id="9d99e-2403">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="9d99e-2403">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="9d99e-2404">La funzione Func_jp_passport restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="9d99e-2404">The function Func_jp_passport finds content that matches the pattern.</span></span>
- <span data-ttu-id="9d99e-2405">Viene trovata una parola chiave da Keyword_jp_passport.</span><span class="sxs-lookup"><span data-stu-id="9d99e-2405">A keyword from Keyword_jp_passport is found.</span></span>

```
<!-- Japan Passport Number -->
<Entity id="75177310-1a09-4613-bf6d-833aae3743f8" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_jp_passport" />
        <Match idRef="Keyword_jp_passport" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="9d99e-2406">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="9d99e-2406">Keywords</span></span>

#### <a name="keywordjppassport"></a><span data-ttu-id="9d99e-2407">Keyword_jp_passport</span><span class="sxs-lookup"><span data-stu-id="9d99e-2407">Keyword_jp_passport</span></span>

- <span data-ttu-id="9d99e-2408">パスポート
</span><span class="sxs-lookup"><span data-stu-id="9d99e-2408">パスポート</span></span> 
- <span data-ttu-id="9d99e-2409">パスポート番号
</span><span class="sxs-lookup"><span data-stu-id="9d99e-2409">パスポート番号</span></span> 
- <span data-ttu-id="9d99e-2410">パスポートのNum
</span><span class="sxs-lookup"><span data-stu-id="9d99e-2410">パスポートのNum</span></span> 
- <span data-ttu-id="9d99e-2411">パスポート＃
</span><span class="sxs-lookup"><span data-stu-id="9d99e-2411">パスポート＃</span></span> 
   
## <a name="japan-resident-registration-number"></a><span data-ttu-id="9d99e-2412">Giappone - Numero di registrazione dei residenti</span><span class="sxs-lookup"><span data-stu-id="9d99e-2412">Japan Resident Registration Number</span></span>

### <a name="format"></a><span data-ttu-id="9d99e-2413">Formato</span><span class="sxs-lookup"><span data-stu-id="9d99e-2413">Format</span></span>

<span data-ttu-id="9d99e-2414">11 cifre</span><span class="sxs-lookup"><span data-stu-id="9d99e-2414">11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="9d99e-2415">Modello</span><span class="sxs-lookup"><span data-stu-id="9d99e-2415">Pattern</span></span>

<span data-ttu-id="9d99e-2416">11 cifre consecutive</span><span class="sxs-lookup"><span data-stu-id="9d99e-2416">11 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="9d99e-2417">Checksum</span><span class="sxs-lookup"><span data-stu-id="9d99e-2417">Checksum</span></span>

<span data-ttu-id="9d99e-2418">No</span><span class="sxs-lookup"><span data-stu-id="9d99e-2418">No</span></span>

### <a name="definition"></a><span data-ttu-id="9d99e-2419">Definizione</span><span class="sxs-lookup"><span data-stu-id="9d99e-2419">Definition</span></span>

<span data-ttu-id="9d99e-2420">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="9d99e-2420">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="9d99e-2421">La funzione Func_jp_resident_registration_number restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="9d99e-2421">The function Func_jp_resident_registration_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="9d99e-2422">Viene trovata una parola chiave da Keyword_jp_resident_registration_number.</span><span class="sxs-lookup"><span data-stu-id="9d99e-2422">A keyword from Keyword_jp_resident_registration_number is found.</span></span>

```
<!-- Japan Resident Registration Number -->
<Entity id="01c1209b-6389-4faf-a5f8-3f7e13899652" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_jp_resident_registration_number" />
        <Match idRef ="Keyword_jp_resident_registration_number" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="9d99e-2423">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="9d99e-2423">Keywords</span></span>

#### <a name="keywordjpresidentregistrationnumber"></a><span data-ttu-id="9d99e-2424">Keyword_jp_resident_registration_number</span><span class="sxs-lookup"><span data-stu-id="9d99e-2424">Keyword_jp_resident_registration_number</span></span>

- <span data-ttu-id="9d99e-2425">Resident Registration Number</span><span class="sxs-lookup"><span data-stu-id="9d99e-2425">Resident Registration Number</span></span>
- <span data-ttu-id="9d99e-2426">Resident Register Number
</span><span class="sxs-lookup"><span data-stu-id="9d99e-2426">Resident Register Number</span></span> 
- <span data-ttu-id="9d99e-2427">Residents Basic Registry Number
</span><span class="sxs-lookup"><span data-stu-id="9d99e-2427">Residents Basic Registry Number</span></span> 
- <span data-ttu-id="9d99e-2428">Resident Registration No.
</span><span class="sxs-lookup"><span data-stu-id="9d99e-2428">Resident Registration No.</span></span> 
- <span data-ttu-id="9d99e-2429">Resident Register No.
</span><span class="sxs-lookup"><span data-stu-id="9d99e-2429">Resident Register No.</span></span> 
- <span data-ttu-id="9d99e-2430">Residents Basic Registry No.
</span><span class="sxs-lookup"><span data-stu-id="9d99e-2430">Residents Basic Registry No.</span></span> 
- <span data-ttu-id="9d99e-2431">Basic Resident Register No.
</span><span class="sxs-lookup"><span data-stu-id="9d99e-2431">Basic Resident Register No.</span></span> 
- <span data-ttu-id="9d99e-2432">住民登録番号、登録番号をレジデント
</span><span class="sxs-lookup"><span data-stu-id="9d99e-2432">住民登録番号、登録番号をレジデント</span></span> 
- <span data-ttu-id="9d99e-2433">住民基本登録番号、登録番号
</span><span class="sxs-lookup"><span data-stu-id="9d99e-2433">住民基本登録番号、登録番号</span></span> 
- <span data-ttu-id="9d99e-2434">住民基本レジストリ番号を常駐
</span><span class="sxs-lookup"><span data-stu-id="9d99e-2434">住民基本レジストリ番号を常駐</span></span> 
- <span data-ttu-id="9d99e-2435">登録番号を常駐住民基本台帳登録番号
</span><span class="sxs-lookup"><span data-stu-id="9d99e-2435">登録番号を常駐住民基本台帳登録番号</span></span> 

   
## <a name="japan-social-insurance-number-sin"></a><span data-ttu-id="9d99e-2436">Giappone - Numero di assicurazione sociale (SIN)</span><span class="sxs-lookup"><span data-stu-id="9d99e-2436">Japan Social Insurance Number (SIN)</span></span>

### <a name="format"></a><span data-ttu-id="9d99e-2437">Formato</span><span class="sxs-lookup"><span data-stu-id="9d99e-2437">Format</span></span>

<span data-ttu-id="9d99e-2438">7-12 cifre</span><span class="sxs-lookup"><span data-stu-id="9d99e-2438">7-12 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="9d99e-2439">Modello</span><span class="sxs-lookup"><span data-stu-id="9d99e-2439">Pattern</span></span>

<span data-ttu-id="9d99e-2440">7-12 cifre:</span><span class="sxs-lookup"><span data-stu-id="9d99e-2440">7-12 digits:</span></span>
- <span data-ttu-id="9d99e-2441">Quattro cifre</span><span class="sxs-lookup"><span data-stu-id="9d99e-2441">Four digits</span></span> 
- <span data-ttu-id="9d99e-2442">Una lineetta (facoltativa)</span><span class="sxs-lookup"><span data-stu-id="9d99e-2442">A hyphen (optional)</span></span> 
- <span data-ttu-id="9d99e-2443">Sei cifre o</span><span class="sxs-lookup"><span data-stu-id="9d99e-2443">Six digits OR</span></span>
- <span data-ttu-id="9d99e-2444">7-12 cifre consecutive</span><span class="sxs-lookup"><span data-stu-id="9d99e-2444">7-12 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="9d99e-2445">Checksum</span><span class="sxs-lookup"><span data-stu-id="9d99e-2445">Checksum</span></span>

<span data-ttu-id="9d99e-2446">No</span><span class="sxs-lookup"><span data-stu-id="9d99e-2446">No</span></span>

### <a name="definition"></a><span data-ttu-id="9d99e-2447">Definizione</span><span class="sxs-lookup"><span data-stu-id="9d99e-2447">Definition</span></span>

<span data-ttu-id="9d99e-2448">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="9d99e-2448">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="9d99e-2449">La funzione Func_jp_sin restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="9d99e-2449">The function Func_jp_sin finds content that matches the pattern.</span></span>
- <span data-ttu-id="9d99e-2450">Viene trovata una parola chiave da Keyword_jp_sin.</span><span class="sxs-lookup"><span data-stu-id="9d99e-2450">A keyword from Keyword_jp_sin is found.</span></span>

<span data-ttu-id="9d99e-2451">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="9d99e-2451">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="9d99e-2452">La funzione Func_jp_sin_pre_1997 restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="9d99e-2452">The function Func_jp_sin_pre_1997 finds content that matches the pattern.</span></span>
- <span data-ttu-id="9d99e-2453">Viene trovata una parola chiave da Keyword_jp_sin.</span><span class="sxs-lookup"><span data-stu-id="9d99e-2453">A keyword from Keyword_jp_sin is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="9d99e-2454">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="9d99e-2454">Keywords</span></span>

#### <a name="keywordjpsin"></a><span data-ttu-id="9d99e-2455">Keyword_jp_sin</span><span class="sxs-lookup"><span data-stu-id="9d99e-2455">Keyword_jp_sin</span></span>

- <span data-ttu-id="9d99e-2456">Social Insurance No.
</span><span class="sxs-lookup"><span data-stu-id="9d99e-2456">Social Insurance No.</span></span> 
- <span data-ttu-id="9d99e-2457">Social Insurance Num
</span><span class="sxs-lookup"><span data-stu-id="9d99e-2457">Social Insurance Num</span></span> 
- <span data-ttu-id="9d99e-2458">Social Insurance Number
</span><span class="sxs-lookup"><span data-stu-id="9d99e-2458">Social Insurance Number</span></span> 
- <span data-ttu-id="9d99e-2459">社会保険のテンキー
</span><span class="sxs-lookup"><span data-stu-id="9d99e-2459">社会保険のテンキー</span></span> 
- <span data-ttu-id="9d99e-2460">社会保険番号
</span><span class="sxs-lookup"><span data-stu-id="9d99e-2460">社会保険番号</span></span> 
   
## <a name="malaysia-id-card-number"></a><span data-ttu-id="9d99e-2461">Malesia - Numero di carta d’identità</span><span class="sxs-lookup"><span data-stu-id="9d99e-2461">Malaysia ID Card Number</span></span>

### <a name="format"></a><span data-ttu-id="9d99e-2462">Formato</span><span class="sxs-lookup"><span data-stu-id="9d99e-2462">Format</span></span>

<span data-ttu-id="9d99e-2463">12 cifre contenenti lineette facoltative</span><span class="sxs-lookup"><span data-stu-id="9d99e-2463">12 digits containing optional hyphens</span></span>

### <a name="pattern"></a><span data-ttu-id="9d99e-2464">Modello</span><span class="sxs-lookup"><span data-stu-id="9d99e-2464">Pattern</span></span>

<span data-ttu-id="9d99e-2465">12 cifre:</span><span class="sxs-lookup"><span data-stu-id="9d99e-2465">12 digits:</span></span>
- <span data-ttu-id="9d99e-2466">Sei cifre nel formato AAMMGG, ovvero la data di nascita</span><span class="sxs-lookup"><span data-stu-id="9d99e-2466">Six digits in the format YYMMDD which are the date of birth</span></span> 
- <span data-ttu-id="9d99e-2467">Un trattino (facoltativo)</span><span class="sxs-lookup"><span data-stu-id="9d99e-2467">A dash (optional)</span></span> 
- <span data-ttu-id="9d99e-2468">Codice luogo di nascita a due lettere </span><span class="sxs-lookup"><span data-stu-id="9d99e-2468">Two-letter place-of-birth code</span></span> 
- <span data-ttu-id="9d99e-2469">Un trattino (facoltativo)</span><span class="sxs-lookup"><span data-stu-id="9d99e-2469">A dash (optional)</span></span> 
- <span data-ttu-id="9d99e-2470">Tre cifre casuali </span><span class="sxs-lookup"><span data-stu-id="9d99e-2470">Three random digits</span></span> 
- <span data-ttu-id="9d99e-2471">Codice genere a una cifra singola</span><span class="sxs-lookup"><span data-stu-id="9d99e-2471">One-digit gender code</span></span>

### <a name="checksum"></a><span data-ttu-id="9d99e-2472">Checksum</span><span class="sxs-lookup"><span data-stu-id="9d99e-2472">Checksum</span></span>

<span data-ttu-id="9d99e-2473">No</span><span class="sxs-lookup"><span data-stu-id="9d99e-2473">No</span></span>

### <a name="definition"></a><span data-ttu-id="9d99e-2474">Definizione</span><span class="sxs-lookup"><span data-stu-id="9d99e-2474">Definition</span></span>

<span data-ttu-id="9d99e-2475">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="9d99e-2475">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="9d99e-2476">L'espressione regolare Regex_malaysia_id_card_number consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="9d99e-2476">The regular expression Regex_malaysia_id_card_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="9d99e-2477">È possibile trovare una parola chiave da Keyword_malaysia_id_card_number.</span><span class="sxs-lookup"><span data-stu-id="9d99e-2477">A keyword from Keyword_malaysia_id_card_number is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="9d99e-2478">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="9d99e-2478">Keywords</span></span>
   
#### <a name="keywordmalaysiaidcardnumber"></a><span data-ttu-id="9d99e-2479">Keyword_malaysia_id_card_number</span><span class="sxs-lookup"><span data-stu-id="9d99e-2479">Keyword_malaysia_id_card_number</span></span>

- <span data-ttu-id="9d99e-2480">MyKad</span><span class="sxs-lookup"><span data-stu-id="9d99e-2480">MyKad</span></span> 
- <span data-ttu-id="9d99e-2481">Carta di identità</span><span class="sxs-lookup"><span data-stu-id="9d99e-2481">Identity Card</span></span> 
- <span data-ttu-id="9d99e-2482">Carta d'identità</span><span class="sxs-lookup"><span data-stu-id="9d99e-2482">ID Card</span></span> 
- <span data-ttu-id="9d99e-2483">Scheda di identificazione</span><span class="sxs-lookup"><span data-stu-id="9d99e-2483">Identification Card</span></span> 
- <span data-ttu-id="9d99e-2484">Scheda applicazione digitale
</span><span class="sxs-lookup"><span data-stu-id="9d99e-2484">Digital Application Card</span></span> 
- <span data-ttu-id="9d99e-2485">Kad Akuan Diri
</span><span class="sxs-lookup"><span data-stu-id="9d99e-2485">Kad Akuan Diri</span></span> 
- <span data-ttu-id="9d99e-2486">Kad Aplikasi Digital
</span><span class="sxs-lookup"><span data-stu-id="9d99e-2486">Kad Aplikasi Digital</span></span> 
   
## <a name="netherlands-citizens-service-bsn-number"></a><span data-ttu-id="9d99e-2487">Paesi Bassi - Numero di servizio cittadino (BSN)</span><span class="sxs-lookup"><span data-stu-id="9d99e-2487">Netherlands Citizen's Service (BSN) Number</span></span>

### <a name="format"></a><span data-ttu-id="9d99e-2488">Formato</span><span class="sxs-lookup"><span data-stu-id="9d99e-2488">Format</span></span>

<span data-ttu-id="9d99e-2489">8-9 cifre contenenti spazi facoltativi </span><span class="sxs-lookup"><span data-stu-id="9d99e-2489">8-9 digits containing optional spaces</span></span>

### <a name="pattern"></a><span data-ttu-id="9d99e-2490">Modello</span><span class="sxs-lookup"><span data-stu-id="9d99e-2490">Pattern</span></span>

<span data-ttu-id="9d99e-2491">8-9 cifre:</span><span class="sxs-lookup"><span data-stu-id="9d99e-2491">8-9 digits:</span></span>
- <span data-ttu-id="9d99e-2492">Tre cifre</span><span class="sxs-lookup"><span data-stu-id="9d99e-2492">Three digits</span></span> 
- <span data-ttu-id="9d99e-2493">Uno spazio (facoltativo)</span><span class="sxs-lookup"><span data-stu-id="9d99e-2493">A space (optional)</span></span> 
- <span data-ttu-id="9d99e-2494">Tre cifre</span><span class="sxs-lookup"><span data-stu-id="9d99e-2494">Three digits</span></span> 
- <span data-ttu-id="9d99e-2495">Uno spazio (facoltativo)</span><span class="sxs-lookup"><span data-stu-id="9d99e-2495">A space (optional)</span></span> 
- <span data-ttu-id="9d99e-2496">2-3 cifre</span><span class="sxs-lookup"><span data-stu-id="9d99e-2496">2-3 digits</span></span>

### <a name="checksum"></a><span data-ttu-id="9d99e-2497">Checksum</span><span class="sxs-lookup"><span data-stu-id="9d99e-2497">Checksum</span></span>

<span data-ttu-id="9d99e-2498">Sì</span><span class="sxs-lookup"><span data-stu-id="9d99e-2498">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="9d99e-2499">Definizione</span><span class="sxs-lookup"><span data-stu-id="9d99e-2499">Definition</span></span>

<span data-ttu-id="9d99e-2500">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="9d99e-2500">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="9d99e-2501">La funzione Func_netherlands_bsn consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="9d99e-2501">The function Func_netherlands_bsn finds content that matches the pattern.</span></span>
- <span data-ttu-id="9d99e-2502">È possibile trovare una parola chiave da Keyword_netherlands_bsn.</span><span class="sxs-lookup"><span data-stu-id="9d99e-2502">A keyword from Keyword_netherlands_bsn is found.</span></span>
- <span data-ttu-id="9d99e-2503">La funzione Func_eu_date2 rileva una data nel formato corretto.</span><span class="sxs-lookup"><span data-stu-id="9d99e-2503">The function Func_eu_date2 finds a date in the right date format.</span></span>
- <span data-ttu-id="9d99e-2504">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="9d99e-2504">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="9d99e-2505">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="9d99e-2505">Keywords</span></span>

#### <a name="keywordnetherlandsbsn"></a><span data-ttu-id="9d99e-2506">Keyword_netherlands_bsn</span><span class="sxs-lookup"><span data-stu-id="9d99e-2506">Keyword_netherlands_bsn</span></span>

- <span data-ttu-id="9d99e-2507">Numero di servizio cittadino
</span><span class="sxs-lookup"><span data-stu-id="9d99e-2507">Citizen service number</span></span> 
- <span data-ttu-id="9d99e-2508">BSN

</span><span class="sxs-lookup"><span data-stu-id="9d99e-2508">BSN</span></span> 
- <span data-ttu-id="9d99e-2509">Burgerservicenummer
</span><span class="sxs-lookup"><span data-stu-id="9d99e-2509">Burgerservicenummer</span></span> 
- <span data-ttu-id="9d99e-2510">Sofinummer
</span><span class="sxs-lookup"><span data-stu-id="9d99e-2510">Sofinummer</span></span> 
- <span data-ttu-id="9d99e-2511">Persoonsgebonden nummer
</span><span class="sxs-lookup"><span data-stu-id="9d99e-2511">Persoonsgebonden nummer</span></span> 
- <span data-ttu-id="9d99e-2512">Persoonsnummer
</span><span class="sxs-lookup"><span data-stu-id="9d99e-2512">Persoonsnummer</span></span>    

   
## <a name="new-zealand-ministry-of-health-number"></a><span data-ttu-id="9d99e-2513">Nuova Zelanda - Numero del Ministero della Sanità</span><span class="sxs-lookup"><span data-stu-id="9d99e-2513">New Zealand Ministry of Health Number</span></span>

### <a name="format"></a><span data-ttu-id="9d99e-2514">Formato</span><span class="sxs-lookup"><span data-stu-id="9d99e-2514">Format</span></span>

<span data-ttu-id="9d99e-2515">Tre lettere, uno spazio (facoltativo) e quattro cifre</span><span class="sxs-lookup"><span data-stu-id="9d99e-2515">Three letters, a space (optional), and four digits</span></span>

### <a name="pattern"></a><span data-ttu-id="9d99e-2516">Modello</span><span class="sxs-lookup"><span data-stu-id="9d99e-2516">Pattern</span></span>

<span data-ttu-id="9d99e-2517">Tre lettere quattro cifre (facoltativo) un spazio (non maiuscole/minuscole)</span><span class="sxs-lookup"><span data-stu-id="9d99e-2517">Three letters (not case sensitive) a space (optional) four digits</span></span>

### <a name="checksum"></a><span data-ttu-id="9d99e-2518">Checksum</span><span class="sxs-lookup"><span data-stu-id="9d99e-2518">Checksum</span></span>

<span data-ttu-id="9d99e-2519">Sì</span><span class="sxs-lookup"><span data-stu-id="9d99e-2519">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="9d99e-2520">Definizione</span><span class="sxs-lookup"><span data-stu-id="9d99e-2520">Definition</span></span>

<span data-ttu-id="9d99e-2521">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="9d99e-2521">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="9d99e-2522">La funzione Func_new_zealand_ministry_of_health_number restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="9d99e-2522">The function Func_new_zealand_ministry_of_health_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="9d99e-2523">Viene trovata una parola chiave da Keyword_nz_terms.</span><span class="sxs-lookup"><span data-stu-id="9d99e-2523">A keyword from Keyword_nz_terms is found.</span></span>
- <span data-ttu-id="9d99e-2524">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="9d99e-2524">The checksum passes.</span></span>

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

<span data-ttu-id="9d99e-2525">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="9d99e-2525">Keywords</span></span>

<span data-ttu-id="9d99e-2526">Keyword_nz_terms</span><span class="sxs-lookup"><span data-stu-id="9d99e-2526">Keyword_nz_terms</span></span>

- <span data-ttu-id="9d99e-2527">NHI
</span><span class="sxs-lookup"><span data-stu-id="9d99e-2527">NHI</span></span> 
- <span data-ttu-id="9d99e-2528">Nuova Zelanda</span><span class="sxs-lookup"><span data-stu-id="9d99e-2528">New Zealand</span></span> 
- <span data-ttu-id="9d99e-2529">Stato attività</span><span class="sxs-lookup"><span data-stu-id="9d99e-2529">Health</span></span> 
- <span data-ttu-id="9d99e-2530">treatment
</span><span class="sxs-lookup"><span data-stu-id="9d99e-2530">treatment</span></span> 
   
## <a name="norway-identification-number"></a><span data-ttu-id="9d99e-2531">Norvegia - Numero di identificazione
</span><span class="sxs-lookup"><span data-stu-id="9d99e-2531">Norway Identification Number</span></span>

### <a name="format"></a><span data-ttu-id="9d99e-2532">Formato</span><span class="sxs-lookup"><span data-stu-id="9d99e-2532">Format</span></span>

<span data-ttu-id="9d99e-2533">11 cifre</span><span class="sxs-lookup"><span data-stu-id="9d99e-2533">11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="9d99e-2534">Modello</span><span class="sxs-lookup"><span data-stu-id="9d99e-2534">Pattern</span></span>

<span data-ttu-id="9d99e-2535">11 cifre:</span><span class="sxs-lookup"><span data-stu-id="9d99e-2535">11 digits:</span></span>
- <span data-ttu-id="9d99e-2536">Sei cifre nel formato GGMMAA, ovvero la data di nascita</span><span class="sxs-lookup"><span data-stu-id="9d99e-2536">Six digits in the format DDMMYY which are the date of birth</span></span> 
- <span data-ttu-id="9d99e-2537">Numero individuale composto da tre cifre </span><span class="sxs-lookup"><span data-stu-id="9d99e-2537">Three-digit individual number</span></span> 
- <span data-ttu-id="9d99e-2538">Due cifre di controllo</span><span class="sxs-lookup"><span data-stu-id="9d99e-2538">Two check digits</span></span>

### <a name="checksum"></a><span data-ttu-id="9d99e-2539">Checksum</span><span class="sxs-lookup"><span data-stu-id="9d99e-2539">Checksum</span></span>

<span data-ttu-id="9d99e-2540">Sì</span><span class="sxs-lookup"><span data-stu-id="9d99e-2540">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="9d99e-2541">Definizione</span><span class="sxs-lookup"><span data-stu-id="9d99e-2541">Definition</span></span>

<span data-ttu-id="9d99e-2542">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="9d99e-2542">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="9d99e-2543">La funzione Func_norway_id_number consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="9d99e-2543">The function Func_norway_id_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="9d99e-2544">È possibile trovare una parola chiave da Keyword_norway_id_number.</span><span class="sxs-lookup"><span data-stu-id="9d99e-2544">A keyword from Keyword_norway_id_number is found.</span></span>
- <span data-ttu-id="9d99e-2545">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="9d99e-2545">The checksum passes.</span></span>
- <span data-ttu-id="9d99e-2546">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="9d99e-2546">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="9d99e-2547">La funzione Func_norway_id_numbe consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="9d99e-2547">The function Func_norway_id_numbe finds content that matches the pattern.</span></span>
- <span data-ttu-id="9d99e-2548">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="9d99e-2548">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="9d99e-2549">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="9d99e-2549">Keywords</span></span>

#### <a name="keywordnorwayidnumber"></a><span data-ttu-id="9d99e-2550">Keyword_norway_id_number</span><span class="sxs-lookup"><span data-stu-id="9d99e-2550">Keyword_norway_id_number</span></span>

- <span data-ttu-id="9d99e-2551">Codice PIN</span><span class="sxs-lookup"><span data-stu-id="9d99e-2551">Personal identification number</span></span>
- <span data-ttu-id="9d99e-2552">Numero ID norvegese</span><span class="sxs-lookup"><span data-stu-id="9d99e-2552">Norwegian ID Number</span></span>
- <span data-ttu-id="9d99e-2553">Numero ID
</span><span class="sxs-lookup"><span data-stu-id="9d99e-2553">ID Number</span></span>
- <span data-ttu-id="9d99e-2554">Identificazione</span><span class="sxs-lookup"><span data-stu-id="9d99e-2554">Identification</span></span>
- <span data-ttu-id="9d99e-2555">Personnummer</span><span class="sxs-lookup"><span data-stu-id="9d99e-2555">Personnummer</span></span>
- <span data-ttu-id="9d99e-2556">Fødselsnummer</span><span class="sxs-lookup"><span data-stu-id="9d99e-2556">Fødselsnummer</span></span>

   
## <a name="philippines-unified-multi-purpose-id-number"></a><span data-ttu-id="9d99e-2557">Filippine - Numero ID multifunzione unificato</span><span class="sxs-lookup"><span data-stu-id="9d99e-2557">Philippines Unified Multi-Purpose ID Number</span></span>

### <a name="format"></a><span data-ttu-id="9d99e-2558">Formato</span><span class="sxs-lookup"><span data-stu-id="9d99e-2558">Format</span></span>

<span data-ttu-id="9d99e-2559">12 cifre separate da dei segni meno</span><span class="sxs-lookup"><span data-stu-id="9d99e-2559">12 digits separated by hyphens</span></span>

### <a name="pattern"></a><span data-ttu-id="9d99e-2560">Modello</span><span class="sxs-lookup"><span data-stu-id="9d99e-2560">Pattern</span></span>

<span data-ttu-id="9d99e-2561">12 cifre:</span><span class="sxs-lookup"><span data-stu-id="9d99e-2561">12 digits:</span></span>
- <span data-ttu-id="9d99e-2562">Quattro cifre</span><span class="sxs-lookup"><span data-stu-id="9d99e-2562">Four digits</span></span> 
- <span data-ttu-id="9d99e-2563">Una lineetta</span><span class="sxs-lookup"><span data-stu-id="9d99e-2563">A hyphen</span></span> 
- <span data-ttu-id="9d99e-2564">Sette cifre</span><span class="sxs-lookup"><span data-stu-id="9d99e-2564">Seven digits</span></span> 
- <span data-ttu-id="9d99e-2565">Una lineetta</span><span class="sxs-lookup"><span data-stu-id="9d99e-2565">A hyphen</span></span> 
- <span data-ttu-id="9d99e-2566">Una cifra</span><span class="sxs-lookup"><span data-stu-id="9d99e-2566">One digit</span></span>

### <a name="checksum"></a><span data-ttu-id="9d99e-2567">Checksum</span><span class="sxs-lookup"><span data-stu-id="9d99e-2567">Checksum</span></span>

<span data-ttu-id="9d99e-2568">No</span><span class="sxs-lookup"><span data-stu-id="9d99e-2568">No</span></span>

### <a name="definition"></a><span data-ttu-id="9d99e-2569">Definizione</span><span class="sxs-lookup"><span data-stu-id="9d99e-2569">Definition</span></span>

<span data-ttu-id="9d99e-2570">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="9d99e-2570">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="9d99e-2571">L'espressione regolare Regex_philippines_unified_id consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="9d99e-2571">The regular expression Regex_philippines_unified_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="9d99e-2572">È possibile trovare una parola chiave da Keyword_philippines_id.</span><span class="sxs-lookup"><span data-stu-id="9d99e-2572">A keyword from Keyword_philippines_id is found.</span></span>

```
<!-- Philippines Unified Multi-Purpose ID number -->
<Entity id="019b39dd-8c25-4765-91a3-d9c6baf3c3b3" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_philippines_unified_id"/>
     <Match idRef="Keyword_philippines_id"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="9d99e-2573">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="9d99e-2573">Keywords</span></span>
   
#### <a name="keywordphilippinesid"></a><span data-ttu-id="9d99e-2574">Keyword_philippines_id</span><span class="sxs-lookup"><span data-stu-id="9d99e-2574">Keyword_philippines_id</span></span>

- <span data-ttu-id="9d99e-2575">ID multifunzione unificato
</span><span class="sxs-lookup"><span data-stu-id="9d99e-2575">Unified Multi-Purpose ID</span></span> 
- <span data-ttu-id="9d99e-2576">UMID
</span><span class="sxs-lookup"><span data-stu-id="9d99e-2576">UMID</span></span> 
- <span data-ttu-id="9d99e-2577">Carta di identità</span><span class="sxs-lookup"><span data-stu-id="9d99e-2577">Identity Card</span></span> 
- <span data-ttu-id="9d99e-2578">Pinag-isang Multi-Layunin ID</span><span class="sxs-lookup"><span data-stu-id="9d99e-2578">Pinag-isang Multi-Layunin ID</span></span>
   
## <a name="poland-identity-card"></a><span data-ttu-id="9d99e-2579">Carta di identita - Polonia</span><span class="sxs-lookup"><span data-stu-id="9d99e-2579">Poland Identity Card</span></span>

### <a name="format"></a><span data-ttu-id="9d99e-2580">Formato</span><span class="sxs-lookup"><span data-stu-id="9d99e-2580">Format</span></span>

<span data-ttu-id="9d99e-2581">Tre lettere e sei cifre</span><span class="sxs-lookup"><span data-stu-id="9d99e-2581">Three letters and six digits</span></span>

### <a name="pattern"></a><span data-ttu-id="9d99e-2582">Modello</span><span class="sxs-lookup"><span data-stu-id="9d99e-2582">Pattern</span></span>

<span data-ttu-id="9d99e-2583">Tre lettere (senza distinzione tra maiuscole/minuscole) seguite da sei cifre</span><span class="sxs-lookup"><span data-stu-id="9d99e-2583">Three letters (not case sensitive) followed by six digits</span></span>

### <a name="checksum"></a><span data-ttu-id="9d99e-2584">Checksum</span><span class="sxs-lookup"><span data-stu-id="9d99e-2584">Checksum</span></span>

<span data-ttu-id="9d99e-2585">Sì</span><span class="sxs-lookup"><span data-stu-id="9d99e-2585">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="9d99e-2586">Definizione</span><span class="sxs-lookup"><span data-stu-id="9d99e-2586">Definition</span></span>

<span data-ttu-id="9d99e-p138">Un criterio DLP è 75% la certezza che è stato rilevato questo tipo di informazioni riservate se all'interno di prossimità di 300 caratteri: la funzione Func_polish_national_id consente di trovare contenuto corrispondente al formato. È possibile trovare una parola chiave da Keyword_polish_national_id_passport_number. Passa il valore di checksum.</span><span class="sxs-lookup"><span data-stu-id="9d99e-p138">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The function Func_polish_national_id finds content that matches the pattern. A keyword from Keyword_polish_national_id_passport_number is found. The checksum passes.</span></span>

```
<!-- Poland Identity Card-->
<Entity id="25E64989-ED5D-40CA-A939-6C14183BB7BF" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_polish_national_id" />
          <Match idRef="Keyword_polish_national_id_passport_number" />
      </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="9d99e-2590">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="9d99e-2590">Keywords</span></span>

#### <a name="keywordpolishnationalidpassportnumber"></a><span data-ttu-id="9d99e-2591">Keyword_polish_national_id_passport_number</span><span class="sxs-lookup"><span data-stu-id="9d99e-2591">Keyword_polish_national_id_passport_number</span></span>

- <span data-ttu-id="9d99e-2592">Nazwa i nr dowodu tożsamości
</span><span class="sxs-lookup"><span data-stu-id="9d99e-2592">Nazwa i nr dowodu tożsamości</span></span> 
- <span data-ttu-id="9d99e-2593">Dowód Tożsamości
</span><span class="sxs-lookup"><span data-stu-id="9d99e-2593">Dowód Tożsamości</span></span> 
- <span data-ttu-id="9d99e-p139">dow. os.
</span><span class="sxs-lookup"><span data-stu-id="9d99e-p139">dow. os.</span></span> 

   
## <a name="poland-national-id-pesel"></a><span data-ttu-id="9d99e-2596">ID nazionale Polonia (PESEL)</span><span class="sxs-lookup"><span data-stu-id="9d99e-2596">Poland National ID (PESEL)</span></span>

### <a name="format"></a><span data-ttu-id="9d99e-2597">Formato</span><span class="sxs-lookup"><span data-stu-id="9d99e-2597">Format</span></span>

<span data-ttu-id="9d99e-2598">11 cifre</span><span class="sxs-lookup"><span data-stu-id="9d99e-2598">11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="9d99e-2599">Modello</span><span class="sxs-lookup"><span data-stu-id="9d99e-2599">Pattern</span></span>

<span data-ttu-id="9d99e-2600">11 cifre consecutive</span><span class="sxs-lookup"><span data-stu-id="9d99e-2600">11 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="9d99e-2601">Checksum</span><span class="sxs-lookup"><span data-stu-id="9d99e-2601">Checksum</span></span>

<span data-ttu-id="9d99e-2602">Sì</span><span class="sxs-lookup"><span data-stu-id="9d99e-2602">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="9d99e-2603">Definizione</span><span class="sxs-lookup"><span data-stu-id="9d99e-2603">Definition</span></span>

<span data-ttu-id="9d99e-2604">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="9d99e-2604">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="9d99e-2605">La funzione Func_pesel_identification_number restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="9d99e-2605">The function Func_pesel_identification_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="9d99e-2606">Viene trovata una parola chiave da Keyword_pesel_identification_number.</span><span class="sxs-lookup"><span data-stu-id="9d99e-2606">A keyword from Keyword_pesel_identification_number is found.</span></span>
- <span data-ttu-id="9d99e-2607">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="9d99e-2607">The checksum passes.</span></span>

```
<!-- Poland National ID (PESEL) -->      
<Entity id="E3AAF206-4297-412F-9E06-BA8487E22456" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_pesel_identification_number" />
          <Match idRef="Keyword_pesel_identification_number" />
      </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="9d99e-2608">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="9d99e-2608">Keywords</span></span>

#### <a name="keywordpeselidentificationnumber"></a><span data-ttu-id="9d99e-2609">Keyword_pesel_identification_number</span><span class="sxs-lookup"><span data-stu-id="9d99e-2609">Keyword_pesel_identification_number</span></span>

- <span data-ttu-id="9d99e-2610">Nr PESEL</span><span class="sxs-lookup"><span data-stu-id="9d99e-2610">Nr PESEL</span></span>
- <span data-ttu-id="9d99e-2611">PESEL</span><span class="sxs-lookup"><span data-stu-id="9d99e-2611">PESEL</span></span>   

   
## <a name="poland-passport"></a><span data-ttu-id="9d99e-2612">Passaporto Polonia</span><span class="sxs-lookup"><span data-stu-id="9d99e-2612">Poland Passport</span></span>

### <a name="format"></a><span data-ttu-id="9d99e-2613">Formato</span><span class="sxs-lookup"><span data-stu-id="9d99e-2613">Format</span></span>

<span data-ttu-id="9d99e-2614">Due lettere e sette cifre</span><span class="sxs-lookup"><span data-stu-id="9d99e-2614">Two letters and seven digits</span></span>

### <a name="pattern"></a><span data-ttu-id="9d99e-2615">Modello</span><span class="sxs-lookup"><span data-stu-id="9d99e-2615">Pattern</span></span>

<span data-ttu-id="9d99e-2616">Due lettere (senza distinzione tra maiuscole/minuscole) seguite da sette cifre</span><span class="sxs-lookup"><span data-stu-id="9d99e-2616">Two letters (not case sensitive) followed by seven digits</span></span>

### <a name="checksum"></a><span data-ttu-id="9d99e-2617">Checksum</span><span class="sxs-lookup"><span data-stu-id="9d99e-2617">Checksum</span></span>

<span data-ttu-id="9d99e-2618">Sì</span><span class="sxs-lookup"><span data-stu-id="9d99e-2618">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="9d99e-2619">Definizione</span><span class="sxs-lookup"><span data-stu-id="9d99e-2619">Definition</span></span>

<span data-ttu-id="9d99e-2620">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="9d99e-2620">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="9d99e-2621">La funzione Func_polish_passport_number restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="9d99e-2621">The function Func_polish_passport_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="9d99e-2622">Viene trovata una parola chiave da Keyword_polish_national_id_passport_number.</span><span class="sxs-lookup"><span data-stu-id="9d99e-2622">A keyword from Keyword_polish_national_id_passport_number is found.</span></span>
- <span data-ttu-id="9d99e-2623">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="9d99e-2623">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="9d99e-2624">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="9d99e-2624">Keywords</span></span>

#### <a name="keywordpolishnationalidpassportnumber"></a><span data-ttu-id="9d99e-2625">Keyword_polish_national_id_passport_number</span><span class="sxs-lookup"><span data-stu-id="9d99e-2625">Keyword_polish_national_id_passport_number</span></span>

- <span data-ttu-id="9d99e-2626">Nazwa i nr dowodu tożsamości
</span><span class="sxs-lookup"><span data-stu-id="9d99e-2626">Nazwa i nr dowodu tożsamości</span></span> 
- <span data-ttu-id="9d99e-2627">Dowód Tożsamości
</span><span class="sxs-lookup"><span data-stu-id="9d99e-2627">Dowód Tożsamości</span></span> 
- <span data-ttu-id="9d99e-p140">dow. os.
</span><span class="sxs-lookup"><span data-stu-id="9d99e-p140">dow. os.</span></span> 

   
## <a name="portugal-citizen-card-number"></a><span data-ttu-id="9d99e-2630">Portogallo - Numero di carta del cittadino</span><span class="sxs-lookup"><span data-stu-id="9d99e-2630">Portugal Citizen Card Number</span></span>

### <a name="format"></a><span data-ttu-id="9d99e-2631">Formato</span><span class="sxs-lookup"><span data-stu-id="9d99e-2631">Format</span></span>

<span data-ttu-id="9d99e-2632">Otto cifre</span><span class="sxs-lookup"><span data-stu-id="9d99e-2632">Eight digits</span></span>

### <a name="pattern"></a><span data-ttu-id="9d99e-2633">Modello</span><span class="sxs-lookup"><span data-stu-id="9d99e-2633">Pattern</span></span>

<span data-ttu-id="9d99e-2634">Otto cifre</span><span class="sxs-lookup"><span data-stu-id="9d99e-2634">Eight digits</span></span>

### <a name="checksum"></a><span data-ttu-id="9d99e-2635">Checksum</span><span class="sxs-lookup"><span data-stu-id="9d99e-2635">Checksum</span></span>

<span data-ttu-id="9d99e-2636">No</span><span class="sxs-lookup"><span data-stu-id="9d99e-2636">No</span></span>

### <a name="definition"></a><span data-ttu-id="9d99e-2637">Definizione</span><span class="sxs-lookup"><span data-stu-id="9d99e-2637">Definition</span></span>

<span data-ttu-id="9d99e-2638">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="9d99e-2638">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="9d99e-2639">L'espressione regolare Regex_portugal_citizen_card consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="9d99e-2639">The regular expression Regex_portugal_citizen_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="9d99e-2640">È possibile trovare una parola chiave da Keyword_portugal_citizen_card.</span><span class="sxs-lookup"><span data-stu-id="9d99e-2640">A keyword from Keyword_portugal_citizen_card is found.</span></span>

```
<!-- Portugal Citizen Card Number -->
<Entity id="91a7ece2-add4-4986-9a15-c84544d81ecd" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Regex_portugal_citizen_card"/>
     <Match idRef="Keyword_portugal_citizen_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="9d99e-2641">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="9d99e-2641">Keywords</span></span>

#### <a name="keywordportugalcitizencard"></a><span data-ttu-id="9d99e-2642">Keyword_portugal_citizen_card</span><span class="sxs-lookup"><span data-stu-id="9d99e-2642">Keyword_portugal_citizen_card</span></span>

- <span data-ttu-id="9d99e-2643">Scheda cittadino</span><span class="sxs-lookup"><span data-stu-id="9d99e-2643">Citizen Card</span></span>
- <span data-ttu-id="9d99e-2644">Carta ID</span><span class="sxs-lookup"><span data-stu-id="9d99e-2644">National ID Card</span></span>
- <span data-ttu-id="9d99e-2645">CC</span><span class="sxs-lookup"><span data-stu-id="9d99e-2645">CC</span></span>
- <span data-ttu-id="9d99e-2646">Cartão de Cidadão</span><span class="sxs-lookup"><span data-stu-id="9d99e-2646">Cartão de Cidadão</span></span>
- <span data-ttu-id="9d99e-2647">Bilhete de Identidade</span><span class="sxs-lookup"><span data-stu-id="9d99e-2647">Bilhete de Identidade</span></span>
   
## <a name="saudi-arabia-national-id"></a><span data-ttu-id="9d99e-2648">Arabia Saudita - Identificativo nazionale</span><span class="sxs-lookup"><span data-stu-id="9d99e-2648">Saudi Arabia National ID</span></span>

### <a name="format"></a><span data-ttu-id="9d99e-2649">Formato</span><span class="sxs-lookup"><span data-stu-id="9d99e-2649">Format</span></span>

<span data-ttu-id="9d99e-2650">10 cifre</span><span class="sxs-lookup"><span data-stu-id="9d99e-2650">10 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="9d99e-2651">Modello</span><span class="sxs-lookup"><span data-stu-id="9d99e-2651">Pattern</span></span>

<span data-ttu-id="9d99e-2652">10 cifre consecutive</span><span class="sxs-lookup"><span data-stu-id="9d99e-2652">10 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="9d99e-2653">Checksum</span><span class="sxs-lookup"><span data-stu-id="9d99e-2653">Checksum</span></span>

<span data-ttu-id="9d99e-2654">No</span><span class="sxs-lookup"><span data-stu-id="9d99e-2654">No</span></span>

### <a name="definition"></a><span data-ttu-id="9d99e-2655">Definizione</span><span class="sxs-lookup"><span data-stu-id="9d99e-2655">Definition</span></span>

<span data-ttu-id="9d99e-2656">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="9d99e-2656">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="9d99e-2657">L'espressione regolare Regex_saudi_arabia_national_id restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="9d99e-2657">The regular expression Regex_saudi_arabia_national_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="9d99e-2658">Viene trovata una parola chiave da Keyword_saudi_arabia_national_id.</span><span class="sxs-lookup"><span data-stu-id="9d99e-2658">A keyword from Keyword_saudi_arabia_national_id is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="9d99e-2659">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="9d99e-2659">Keywords</span></span>

#### <a name="keywordsaudiarabianationalid"></a><span data-ttu-id="9d99e-2660">Keyword_saudi_arabia_national_id</span><span class="sxs-lookup"><span data-stu-id="9d99e-2660">Keyword_saudi_arabia_national_id</span></span>

- <span data-ttu-id="9d99e-2661">Identification Card
</span><span class="sxs-lookup"><span data-stu-id="9d99e-2661">Identification Card</span></span> 
- <span data-ttu-id="9d99e-2662">I card number
</span><span class="sxs-lookup"><span data-stu-id="9d99e-2662">I card number</span></span> 
- <span data-ttu-id="9d99e-2663">numero ID</span><span class="sxs-lookup"><span data-stu-id="9d99e-2663">ID number</span></span> 
- <span data-ttu-id="9d99e-2664">الوطنية الهوية بطاقة رقم
</span><span class="sxs-lookup"><span data-stu-id="9d99e-2664">الوطنية الهوية بطاقة رقم</span></span> 

   
## <a name="singapore-national-registration-identity-card-nric-number"></a><span data-ttu-id="9d99e-2665">Singapore - Numero di carta di identità di registrazione nazionale (NRIC)</span><span class="sxs-lookup"><span data-stu-id="9d99e-2665">Singapore National Registration Identity Card (NRIC) Number</span></span>

### <a name="format"></a><span data-ttu-id="9d99e-2666">Formato</span><span class="sxs-lookup"><span data-stu-id="9d99e-2666">Format</span></span>

<span data-ttu-id="9d99e-2667">Nove lettere e numeri</span><span class="sxs-lookup"><span data-stu-id="9d99e-2667">Nine letters and digits</span></span>

### <a name="pattern"></a><span data-ttu-id="9d99e-2668">Modello</span><span class="sxs-lookup"><span data-stu-id="9d99e-2668">Pattern</span></span>

- <span data-ttu-id="9d99e-2669">Nove lettere e numeri:</span><span class="sxs-lookup"><span data-stu-id="9d99e-2669">Nine letters and digits:</span></span>
- <span data-ttu-id="9d99e-2670">La lettera "F", "G", "S" o "T" (senza distinzione tra maiuscole e minuscole) </span><span class="sxs-lookup"><span data-stu-id="9d99e-2670">The letter "F", "G", "S", or "T" (not case sensitive)</span></span> 
- <span data-ttu-id="9d99e-2671">Sette cifre</span><span class="sxs-lookup"><span data-stu-id="9d99e-2671">Seven digits</span></span> 
- <span data-ttu-id="9d99e-2672">Una cifra di controllo alfabetica</span><span class="sxs-lookup"><span data-stu-id="9d99e-2672">An alphabetic check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="9d99e-2673">Checksum</span><span class="sxs-lookup"><span data-stu-id="9d99e-2673">Checksum</span></span>

<span data-ttu-id="9d99e-2674">Sì</span><span class="sxs-lookup"><span data-stu-id="9d99e-2674">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="9d99e-2675">Definizione</span><span class="sxs-lookup"><span data-stu-id="9d99e-2675">Definition</span></span>

<span data-ttu-id="9d99e-2676">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="9d99e-2676">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="9d99e-2677">L'espressione regolare Regex_singapore_nric consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="9d99e-2677">The regular expression Regex_singapore_nric finds content that matches the pattern.</span></span>
- <span data-ttu-id="9d99e-2678">È possibile trovare una parola chiave da Keyword_singapore_nric.</span><span class="sxs-lookup"><span data-stu-id="9d99e-2678">A keyword from Keyword_singapore_nric is found.</span></span>
- <span data-ttu-id="9d99e-2679">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="9d99e-2679">The checksum passes.</span></span>

<span data-ttu-id="9d99e-2680">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="9d99e-2680">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="9d99e-2681">L'espressione regolare Regex_singapore_nric consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="9d99e-2681">The regular expression Regex_singapore_nric finds content that matches the pattern.</span></span>
- <span data-ttu-id="9d99e-2682">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="9d99e-2682">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="9d99e-2683">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="9d99e-2683">Keywords</span></span>
   
#### <a name="keywordsingaporenric"></a><span data-ttu-id="9d99e-2684">Keyword_singapore_nric</span><span class="sxs-lookup"><span data-stu-id="9d99e-2684">Keyword_singapore_nric</span></span>

- <span data-ttu-id="9d99e-2685">Carta di identità di registrazione nazionale
</span><span class="sxs-lookup"><span data-stu-id="9d99e-2685">National Registration Identity Card</span></span> 
- <span data-ttu-id="9d99e-2686">Numero di carta di identità
</span><span class="sxs-lookup"><span data-stu-id="9d99e-2686">Identity Card Number</span></span> 
- <span data-ttu-id="9d99e-2687">NRIC
</span><span class="sxs-lookup"><span data-stu-id="9d99e-2687">NRIC</span></span> 
- <span data-ttu-id="9d99e-2688">IC
</span><span class="sxs-lookup"><span data-stu-id="9d99e-2688">IC</span></span> 
- <span data-ttu-id="9d99e-2689">Numero di identificazione per stranieri

</span><span class="sxs-lookup"><span data-stu-id="9d99e-2689">Foreign Identification Number</span></span> 
- <span data-ttu-id="9d99e-2690">FIN
</span><span class="sxs-lookup"><span data-stu-id="9d99e-2690">FIN</span></span> 
- <span data-ttu-id="9d99e-2691">身份证 </span><span class="sxs-lookup"><span data-stu-id="9d99e-2691">身份证</span></span> 
- <span data-ttu-id="9d99e-2692">身份證
</span><span class="sxs-lookup"><span data-stu-id="9d99e-2692">身份證</span></span> 
   
## <a name="south-africa-identification-number"></a><span data-ttu-id="9d99e-2693">Sudafrica - Numero di identificazione
</span><span class="sxs-lookup"><span data-stu-id="9d99e-2693">South Africa Identification Number</span></span>

### <a name="format"></a><span data-ttu-id="9d99e-2694">Formato</span><span class="sxs-lookup"><span data-stu-id="9d99e-2694">Format</span></span>

<span data-ttu-id="9d99e-2695">13 cifre che possono contenere spazi</span><span class="sxs-lookup"><span data-stu-id="9d99e-2695">13 digits that may contain spaces</span></span>

### <a name="pattern"></a><span data-ttu-id="9d99e-2696">Modello</span><span class="sxs-lookup"><span data-stu-id="9d99e-2696">Pattern</span></span>

<span data-ttu-id="9d99e-2697">13 cifre:</span><span class="sxs-lookup"><span data-stu-id="9d99e-2697">13 digits:</span></span>
- <span data-ttu-id="9d99e-2698">Sei cifre nel formato AAMMGG, ovvero la data di nascita</span><span class="sxs-lookup"><span data-stu-id="9d99e-2698">Six digits in the format YYMMDD which are the date of birth</span></span> 
- <span data-ttu-id="9d99e-2699">Quattro cifre</span><span class="sxs-lookup"><span data-stu-id="9d99e-2699">Four digits</span></span> 
- <span data-ttu-id="9d99e-2700">Un indicatore di cittadinanza a una cifra </span><span class="sxs-lookup"><span data-stu-id="9d99e-2700">A single-digit citizenship indicator</span></span> 
- <span data-ttu-id="9d99e-2701">La cifra "8" o "9" </span><span class="sxs-lookup"><span data-stu-id="9d99e-2701">The digit "8" or "9"</span></span> 
- <span data-ttu-id="9d99e-2702">Una cifra, ovvero una cifra di checksum</span><span class="sxs-lookup"><span data-stu-id="9d99e-2702">One digit which is a checksum digit</span></span>

### <a name="checksum"></a><span data-ttu-id="9d99e-2703">Checksum</span><span class="sxs-lookup"><span data-stu-id="9d99e-2703">Checksum</span></span>

<span data-ttu-id="9d99e-2704">Sì</span><span class="sxs-lookup"><span data-stu-id="9d99e-2704">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="9d99e-2705">Definizione</span><span class="sxs-lookup"><span data-stu-id="9d99e-2705">Definition</span></span>

<span data-ttu-id="9d99e-2706">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="9d99e-2706">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="9d99e-2707">La funzione Func_south_africa_identification_number consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="9d99e-2707">The function Func_south_africa_identification_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="9d99e-2708">È possibile trovare una parola chiave da Keyword_south_africa_identification_number.</span><span class="sxs-lookup"><span data-stu-id="9d99e-2708">A keyword from Keyword_south_africa_identification_number is found.</span></span>
- <span data-ttu-id="9d99e-2709">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="9d99e-2709">The checksum passes.</span></span>

```
<!-- South Africa Identification Number -->
<Entity id="e2adf7cb-8ea6-4048-a2ed-d89eb65f2780" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_south_africa_identification_number"/>
     <Match idRef="Keyword_south_africa_identification_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="9d99e-2710">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="9d99e-2710">Keywords</span></span>
   
#### <a name="keywordsouthafricaidentificationnumber"></a><span data-ttu-id="9d99e-2711">Keyword_south_africa_identification_number</span><span class="sxs-lookup"><span data-stu-id="9d99e-2711">Keyword_south_africa_identification_number</span></span>

- <span data-ttu-id="9d99e-2712">Carta di identità</span><span class="sxs-lookup"><span data-stu-id="9d99e-2712">Identity card</span></span>
- <span data-ttu-id="9d99e-2713">ID</span><span class="sxs-lookup"><span data-stu-id="9d99e-2713">ID</span></span>
- <span data-ttu-id="9d99e-2714">Identificazione</span><span class="sxs-lookup"><span data-stu-id="9d99e-2714">Identification</span></span> 
   
## <a name="south-korea-resident-registration-number"></a><span data-ttu-id="9d99e-2715">Corea del Sud - Numero di registrazione dei residenti</span><span class="sxs-lookup"><span data-stu-id="9d99e-2715">South Korea Resident Registration Number</span></span>

### <a name="format"></a><span data-ttu-id="9d99e-2716">Formato</span><span class="sxs-lookup"><span data-stu-id="9d99e-2716">Format</span></span>

<span data-ttu-id="9d99e-2717">13 cifre contenenti un segno meno</span><span class="sxs-lookup"><span data-stu-id="9d99e-2717">13 digits containing a hyphen</span></span>

### <a name="pattern"></a><span data-ttu-id="9d99e-2718">Modello</span><span class="sxs-lookup"><span data-stu-id="9d99e-2718">Pattern</span></span>

<span data-ttu-id="9d99e-2719">13 cifre:</span><span class="sxs-lookup"><span data-stu-id="9d99e-2719">13 digits:</span></span>
- <span data-ttu-id="9d99e-2720">Sei cifre nel formato AAMMGG, ovvero la data di nascita</span><span class="sxs-lookup"><span data-stu-id="9d99e-2720">Six digits in the format YYMMDD which are the date of birth</span></span> 
- <span data-ttu-id="9d99e-2721">Una lineetta</span><span class="sxs-lookup"><span data-stu-id="9d99e-2721">A hyphen</span></span> 
- <span data-ttu-id="9d99e-2722">Una cifra determinata dal secolo e dal sesso </span><span class="sxs-lookup"><span data-stu-id="9d99e-2722">One digit determined by the century and gender</span></span> 
- <span data-ttu-id="9d99e-2723">Codice di quattro cifre dell’area geografica di nascita </span><span class="sxs-lookup"><span data-stu-id="9d99e-2723">Four-digit region-of-birth code</span></span> 
- <span data-ttu-id="9d99e-2724">Una cifra utilizzata per distinguere persone i cui numeri precedenti sono uguali </span><span class="sxs-lookup"><span data-stu-id="9d99e-2724">One digit used to differentiate people for whom the preceding numbers are identical</span></span> 
- <span data-ttu-id="9d99e-2725">Una cifra di controllo.</span><span class="sxs-lookup"><span data-stu-id="9d99e-2725">A check digit.</span></span>

### <a name="checksum"></a><span data-ttu-id="9d99e-2726">Checksum</span><span class="sxs-lookup"><span data-stu-id="9d99e-2726">Checksum</span></span>

<span data-ttu-id="9d99e-2727">Sì</span><span class="sxs-lookup"><span data-stu-id="9d99e-2727">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="9d99e-2728">Definizione</span><span class="sxs-lookup"><span data-stu-id="9d99e-2728">Definition</span></span>

<span data-ttu-id="9d99e-2729">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="9d99e-2729">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="9d99e-2730">La funzione Func_south_korea_resident_number consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="9d99e-2730">The function Func_south_korea_resident_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="9d99e-2731">È possibile trovare una parola chiave da Keyword_south_korea_resident_number.</span><span class="sxs-lookup"><span data-stu-id="9d99e-2731">A keyword from Keyword_south_korea_resident_number is found.</span></span>
- <span data-ttu-id="9d99e-2732">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="9d99e-2732">The checksum passes.</span></span>

<span data-ttu-id="9d99e-2733">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="9d99e-2733">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="9d99e-2734">La funzione Func_south_korea_resident_number consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="9d99e-2734">The function Func_south_korea_resident_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="9d99e-2735">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="9d99e-2735">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="9d99e-2736">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="9d99e-2736">Keywords</span></span>
   
#### <a name="keywordsouthkorearesidentnumber"></a><span data-ttu-id="9d99e-2737">Keyword_south_korea_resident_number</span><span class="sxs-lookup"><span data-stu-id="9d99e-2737">Keyword_south_korea_resident_number</span></span>

- <span data-ttu-id="9d99e-2738">Carta di identità
</span><span class="sxs-lookup"><span data-stu-id="9d99e-2738">National ID card</span></span> 
- <span data-ttu-id="9d99e-2739">Numero di registrazione del cittadino
</span><span class="sxs-lookup"><span data-stu-id="9d99e-2739">Citizen's Registration Number</span></span> 
- <span data-ttu-id="9d99e-2740">Jumin deungnok beonho
</span><span class="sxs-lookup"><span data-stu-id="9d99e-2740">Jumin deungnok beonho</span></span> 
- <span data-ttu-id="9d99e-2741">RRN
</span><span class="sxs-lookup"><span data-stu-id="9d99e-2741">RRN</span></span> 
- <span data-ttu-id="9d99e-2742">주민등록번호</span><span class="sxs-lookup"><span data-stu-id="9d99e-2742">주민등록번호</span></span>
   
## <a name="spain-social-security-number-ssn"></a><span data-ttu-id="9d99e-2743">Spagna - Numero di previdenza sociale (SSN)</span><span class="sxs-lookup"><span data-stu-id="9d99e-2743">Spain Social Security Number (SSN)</span></span>

### <a name="format"></a><span data-ttu-id="9d99e-2744">Formato</span><span class="sxs-lookup"><span data-stu-id="9d99e-2744">Format</span></span>

<span data-ttu-id="9d99e-2745">11-12 cifre</span><span class="sxs-lookup"><span data-stu-id="9d99e-2745">11-12 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="9d99e-2746">Modello</span><span class="sxs-lookup"><span data-stu-id="9d99e-2746">Pattern</span></span>

<span data-ttu-id="9d99e-2747">12 11 cifre:</span><span class="sxs-lookup"><span data-stu-id="9d99e-2747">11-12 digits:</span></span>
- <span data-ttu-id="9d99e-2748">Due cifre</span><span class="sxs-lookup"><span data-stu-id="9d99e-2748">Two digits</span></span> 
- <span data-ttu-id="9d99e-2749">Una barra (facoltativa)</span><span class="sxs-lookup"><span data-stu-id="9d99e-2749">A forward slash (optional)</span></span> 
- <span data-ttu-id="9d99e-2750">7-8 cifre</span><span class="sxs-lookup"><span data-stu-id="9d99e-2750">7-8 digits</span></span> 
- <span data-ttu-id="9d99e-2751">Una barra (facoltativa)</span><span class="sxs-lookup"><span data-stu-id="9d99e-2751">A forward slash (optional)</span></span> 
- <span data-ttu-id="9d99e-2752">Due cifre</span><span class="sxs-lookup"><span data-stu-id="9d99e-2752">Two digits</span></span>

### <a name="checksum"></a><span data-ttu-id="9d99e-2753">Checksum</span><span class="sxs-lookup"><span data-stu-id="9d99e-2753">Checksum</span></span>

<span data-ttu-id="9d99e-2754">Sì</span><span class="sxs-lookup"><span data-stu-id="9d99e-2754">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="9d99e-2755">Definizione</span><span class="sxs-lookup"><span data-stu-id="9d99e-2755">Definition</span></span>

<span data-ttu-id="9d99e-2756">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="9d99e-2756">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="9d99e-2757">La funzione Func_spanish_social_security_number restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="9d99e-2757">The function Func_spanish_social_security_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="9d99e-2758">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="9d99e-2758">The checksum passes.</span></span>

```
<!-- Spain SSN -->
<Entity id="5df987c0-8eae-4bce-ace7-b316347f3070" patternsProximity="300" recommendedConfidence="85">
    <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_spanish_social_security_number" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="9d99e-2759">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="9d99e-2759">Keywords</span></span>

<span data-ttu-id="9d99e-2760">None</span><span class="sxs-lookup"><span data-stu-id="9d99e-2760">None</span></span>
   
## <a name="sweden-national-id"></a><span data-ttu-id="9d99e-2761">Svezia - Identificativo nazionale</span><span class="sxs-lookup"><span data-stu-id="9d99e-2761">Sweden National ID</span></span>

### <a name="format"></a><span data-ttu-id="9d99e-2762">Formato</span><span class="sxs-lookup"><span data-stu-id="9d99e-2762">Format</span></span>

<span data-ttu-id="9d99e-2763">10 o 12 cifre e un delimitatore facoltativo</span><span class="sxs-lookup"><span data-stu-id="9d99e-2763">10 or 12 digits and an optional delimiter</span></span>

### <a name="pattern"></a><span data-ttu-id="9d99e-2764">Modello</span><span class="sxs-lookup"><span data-stu-id="9d99e-2764">Pattern</span></span>

<span data-ttu-id="9d99e-2765">10 o 12 cifre e un delimitatore facoltativo:</span><span class="sxs-lookup"><span data-stu-id="9d99e-2765">10 or 12 digits and an optional delimiter:</span></span>
- <span data-ttu-id="9d99e-2766">2-4 cifre (facoltative)</span><span class="sxs-lookup"><span data-stu-id="9d99e-2766">2-4 digits (optional)</span></span> 
- <span data-ttu-id="9d99e-2767">Sei cifre nel formato data AAMMGG</span><span class="sxs-lookup"><span data-stu-id="9d99e-2767">Six digits in date format YYMMDD</span></span> 
- <span data-ttu-id="9d99e-2768">Delimitatore di "-" o "+" (facoltativo) più</span><span class="sxs-lookup"><span data-stu-id="9d99e-2768">Delimiter of "-" or "+" (optional), plus</span></span>
- <span data-ttu-id="9d99e-2769">Quattro cifre</span><span class="sxs-lookup"><span data-stu-id="9d99e-2769">Four digits</span></span>

### <a name="checksum"></a><span data-ttu-id="9d99e-2770">Checksum</span><span class="sxs-lookup"><span data-stu-id="9d99e-2770">Checksum</span></span>

<span data-ttu-id="9d99e-2771">Sì</span><span class="sxs-lookup"><span data-stu-id="9d99e-2771">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="9d99e-2772">Definizione</span><span class="sxs-lookup"><span data-stu-id="9d99e-2772">Definition</span></span>

<span data-ttu-id="9d99e-2773">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="9d99e-2773">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="9d99e-2774">La funzione Func_swedish_national_identifier restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="9d99e-2774">The function Func_swedish_national_identifier finds content that matches the pattern.</span></span>
- <span data-ttu-id="9d99e-2775">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="9d99e-2775">The checksum passes.</span></span>

```
<!-- Sweden National ID -->
<Entity id="f69aaf40-79be-4fac-8f05-fd1910d272c8" patternsProximity="300" recommendedConfidence="85">
    <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_swedish_national_identifier" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="9d99e-2776">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="9d99e-2776">Keywords</span></span>

<span data-ttu-id="9d99e-2777">No</span><span class="sxs-lookup"><span data-stu-id="9d99e-2777">No</span></span>
   
## <a name="sweden-passport-number"></a><span data-ttu-id="9d99e-2778">Svezia - Numero di passaporto</span><span class="sxs-lookup"><span data-stu-id="9d99e-2778">Sweden Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="9d99e-2779">Formato</span><span class="sxs-lookup"><span data-stu-id="9d99e-2779">Format</span></span>

<span data-ttu-id="9d99e-2780">Otto cifre</span><span class="sxs-lookup"><span data-stu-id="9d99e-2780">Eight digits</span></span>

### <a name="pattern"></a><span data-ttu-id="9d99e-2781">Modello</span><span class="sxs-lookup"><span data-stu-id="9d99e-2781">Pattern</span></span>

<span data-ttu-id="9d99e-2782">Otto cifre consecutive</span><span class="sxs-lookup"><span data-stu-id="9d99e-2782">Eight consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="9d99e-2783">Checksum</span><span class="sxs-lookup"><span data-stu-id="9d99e-2783">Checksum</span></span>

<span data-ttu-id="9d99e-2784">No</span><span class="sxs-lookup"><span data-stu-id="9d99e-2784">No</span></span>

### <a name="definition"></a><span data-ttu-id="9d99e-2785">Definizione</span><span class="sxs-lookup"><span data-stu-id="9d99e-2785">Definition</span></span>

<span data-ttu-id="9d99e-2786">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="9d99e-2786">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="9d99e-2787">L'espressione regolare Regex_sweden_passport_number restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="9d99e-2787">The regular expression Regex_sweden_passport_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="9d99e-2788">Si verifica una delle situazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="9d99e-2788">One of the following is true:</span></span>
    - <span data-ttu-id="9d99e-2789">Viene trovata una parola chiave da Keyword_passport.</span><span class="sxs-lookup"><span data-stu-id="9d99e-2789">A keyword from Keyword_passport is found.</span></span>
    - <span data-ttu-id="9d99e-2790">Viene trovata una parola chiave da Keyword_sweden_passport.</span><span class="sxs-lookup"><span data-stu-id="9d99e-2790">A keyword from Keyword_sweden_passport is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="9d99e-2791">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="9d99e-2791">Keywords</span></span>
   
#### <a name="keywordswedenpassport"></a><span data-ttu-id="9d99e-2792">Keyword_sweden_passport</span><span class="sxs-lookup"><span data-stu-id="9d99e-2792">Keyword_sweden_passport</span></span>

- <span data-ttu-id="9d99e-2793">visa requirements
</span><span class="sxs-lookup"><span data-stu-id="9d99e-2793">visa requirements</span></span> 
- <span data-ttu-id="9d99e-2794">Alien Registration Card
</span><span class="sxs-lookup"><span data-stu-id="9d99e-2794">Alien Registration Card</span></span> 
- <span data-ttu-id="9d99e-2795">Schengen visas
</span><span class="sxs-lookup"><span data-stu-id="9d99e-2795">Schengen visas</span></span> 
- <span data-ttu-id="9d99e-2796">Schengen visa
</span><span class="sxs-lookup"><span data-stu-id="9d99e-2796">Schengen visa</span></span> 
- <span data-ttu-id="9d99e-2797">Visa Processing
</span><span class="sxs-lookup"><span data-stu-id="9d99e-2797">Visa Processing</span></span> 
- <span data-ttu-id="9d99e-2798">Visa Type
</span><span class="sxs-lookup"><span data-stu-id="9d99e-2798">Visa Type</span></span> 
- <span data-ttu-id="9d99e-2799">Single Entry
</span><span class="sxs-lookup"><span data-stu-id="9d99e-2799">Single Entry</span></span> 
- <span data-ttu-id="9d99e-2800">Multiple Entry
</span><span class="sxs-lookup"><span data-stu-id="9d99e-2800">Multiple Entry</span></span> 
- <span data-ttu-id="9d99e-2801">G3 Processing Fees

</span><span class="sxs-lookup"><span data-stu-id="9d99e-2801">G3 Processing Fees</span></span> 

#### <a name="keywordpassport"></a><span data-ttu-id="9d99e-2802">Keyword_passport</span><span class="sxs-lookup"><span data-stu-id="9d99e-2802">Keyword_passport</span></span>

- <span data-ttu-id="9d99e-2803">Passport Number</span><span class="sxs-lookup"><span data-stu-id="9d99e-2803">Passport Number</span></span> 
- <span data-ttu-id="9d99e-2804">
Passport No</span><span class="sxs-lookup"><span data-stu-id="9d99e-2804">Passport No</span></span> 
- <span data-ttu-id="9d99e-2805">Passport#
</span><span class="sxs-lookup"><span data-stu-id="9d99e-2805">Passport #</span></span> 
- <span data-ttu-id="9d99e-2806">Passport#
</span><span class="sxs-lookup"><span data-stu-id="9d99e-2806">Passport#</span></span> 
- <span data-ttu-id="9d99e-2807">PassportID</span><span class="sxs-lookup"><span data-stu-id="9d99e-2807">PassportID</span></span> 
- <span data-ttu-id="9d99e-2808">Passportno
</span><span class="sxs-lookup"><span data-stu-id="9d99e-2808">Passportno</span></span> 
- <span data-ttu-id="9d99e-2809">passportnumber
</span><span class="sxs-lookup"><span data-stu-id="9d99e-2809">passportnumber</span></span> 
- <span data-ttu-id="9d99e-2810">パスポート</span><span class="sxs-lookup"><span data-stu-id="9d99e-2810">パスポート</span></span> 
- <span data-ttu-id="9d99e-2811">パスポート番号
</span><span class="sxs-lookup"><span data-stu-id="9d99e-2811">パスポート番号</span></span> 
- <span data-ttu-id="9d99e-2812">パスポートのNum
</span><span class="sxs-lookup"><span data-stu-id="9d99e-2812">パスポートのNum</span></span> 
- <span data-ttu-id="9d99e-2813">パスポート＃
</span><span class="sxs-lookup"><span data-stu-id="9d99e-2813">パスポート＃</span></span> 
- <span data-ttu-id="9d99e-2814">Numéro de passeport</span><span class="sxs-lookup"><span data-stu-id="9d99e-2814">Numéro de passeport</span></span> 
- <span data-ttu-id="9d99e-2815">
Passeport n °</span><span class="sxs-lookup"><span data-stu-id="9d99e-2815">Passeport n °</span></span> 
- <span data-ttu-id="9d99e-2816">Passeport Non
</span><span class="sxs-lookup"><span data-stu-id="9d99e-2816">Passeport Non</span></span> 
- <span data-ttu-id="9d99e-2817">Passeport#
</span><span class="sxs-lookup"><span data-stu-id="9d99e-2817">Passeport #</span></span> 
- <span data-ttu-id="9d99e-2818">Passeport#
</span><span class="sxs-lookup"><span data-stu-id="9d99e-2818">Passeport#</span></span> 
- <span data-ttu-id="9d99e-2819">PasseportNon</span><span class="sxs-lookup"><span data-stu-id="9d99e-2819">PasseportNon</span></span> 
- <span data-ttu-id="9d99e-2820">Passeportn °
</span><span class="sxs-lookup"><span data-stu-id="9d99e-2820">Passeportn °</span></span> 
   
## <a name="swift-code"></a><span data-ttu-id="9d99e-2821">Codice SWIFT</span><span class="sxs-lookup"><span data-stu-id="9d99e-2821">SWIFT Code</span></span>

### <a name="format"></a><span data-ttu-id="9d99e-2822">Formato</span><span class="sxs-lookup"><span data-stu-id="9d99e-2822">Format</span></span>

<span data-ttu-id="9d99e-2823">Quattro lettere seguite da 5-31 lettere o cifre</span><span class="sxs-lookup"><span data-stu-id="9d99e-2823">Four letters followed by 5-31 letters or digits</span></span>

### <a name="pattern"></a><span data-ttu-id="9d99e-2824">Modello</span><span class="sxs-lookup"><span data-stu-id="9d99e-2824">Pattern</span></span>

<span data-ttu-id="9d99e-2825">Quattro lettere seguite da 5-31 lettere o cifre:</span><span class="sxs-lookup"><span data-stu-id="9d99e-2825">Four letters followed by 5-31 letters or digits:</span></span>
- <span data-ttu-id="9d99e-2826">Codice ABI di quattro cifre (senza distinzione tra maiuscole/minuscole)</span><span class="sxs-lookup"><span data-stu-id="9d99e-2826">Four-letter bank code (not case sensitive)</span></span> 
- <span data-ttu-id="9d99e-2827">Uno spazio facoltativo</span><span class="sxs-lookup"><span data-stu-id="9d99e-2827">An optional space</span></span> 
- <span data-ttu-id="9d99e-2828">4-28 lettere o cifre (BBAN)</span><span class="sxs-lookup"><span data-stu-id="9d99e-2828">4-28 letters or digits (the Basic Bank Account Number (BBAN))</span></span> 
- <span data-ttu-id="9d99e-2829">Uno spazio facoltativo</span><span class="sxs-lookup"><span data-stu-id="9d99e-2829">An optional space</span></span> 
- <span data-ttu-id="9d99e-2830">1-3 lettere o cifre (resto del BBAN)</span><span class="sxs-lookup"><span data-stu-id="9d99e-2830">1-3 letters or digits (remainder of the BBAN)</span></span>

### <a name="checksum"></a><span data-ttu-id="9d99e-2831">Checksum</span><span class="sxs-lookup"><span data-stu-id="9d99e-2831">Checksum</span></span>

<span data-ttu-id="9d99e-2832">No</span><span class="sxs-lookup"><span data-stu-id="9d99e-2832">No</span></span>

### <a name="definition"></a><span data-ttu-id="9d99e-2833">Definizione</span><span class="sxs-lookup"><span data-stu-id="9d99e-2833">Definition</span></span>

<span data-ttu-id="9d99e-2834">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="9d99e-2834">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="9d99e-2835">L'espressione regolare Regex_swift restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="9d99e-2835">The regular expression Regex_swift finds content that matches the pattern.</span></span>
- <span data-ttu-id="9d99e-2836">Viene trovata una parola chiave da Keyword_swift.</span><span class="sxs-lookup"><span data-stu-id="9d99e-2836">A keyword from Keyword_swift is found.</span></span>

```
<Entity id="cb2ab58c-9cb8-4c81-baf8-a4e106791df4" patternsProximity="300" recommendedConfidence="75">
<Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_swift" />
        <Match idRef="Keyword_swift" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="9d99e-2837">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="9d99e-2837">Keywords</span></span>
   
#### <a name="keywordswift"></a><span data-ttu-id="9d99e-2838">Keyword_swift</span><span class="sxs-lookup"><span data-stu-id="9d99e-2838">Keyword_swift</span></span>

- <span data-ttu-id="9d99e-2839">international organization for standardization 9362
</span><span class="sxs-lookup"><span data-stu-id="9d99e-2839">international organization for standardization 9362</span></span> 
- <span data-ttu-id="9d99e-2840">iso 9362
</span><span class="sxs-lookup"><span data-stu-id="9d99e-2840">iso 9362</span></span> 
- <span data-ttu-id="9d99e-2841">iso9362</span><span class="sxs-lookup"><span data-stu-id="9d99e-2841">iso9362</span></span> 
- <span data-ttu-id="9d99e-2842">codice SWIFT\#</span><span class="sxs-lookup"><span data-stu-id="9d99e-2842">swift\#</span></span> 
- <span data-ttu-id="9d99e-2843">swiftcode
</span><span class="sxs-lookup"><span data-stu-id="9d99e-2843">swiftcode</span></span> 
- <span data-ttu-id="9d99e-2844">swiftnumber
</span><span class="sxs-lookup"><span data-stu-id="9d99e-2844">swiftnumber</span></span> 
- <span data-ttu-id="9d99e-2845">swiftroutingnumber
</span><span class="sxs-lookup"><span data-stu-id="9d99e-2845">swiftroutingnumber</span></span> 
- <span data-ttu-id="9d99e-2846">swift code
</span><span class="sxs-lookup"><span data-stu-id="9d99e-2846">swift code</span></span> 
- <span data-ttu-id="9d99e-2847">swift number #
</span><span class="sxs-lookup"><span data-stu-id="9d99e-2847">swift number #</span></span> 
- <span data-ttu-id="9d99e-2848">swift routing number
</span><span class="sxs-lookup"><span data-stu-id="9d99e-2848">swift routing number</span></span> 
- <span data-ttu-id="9d99e-2849">bic number
</span><span class="sxs-lookup"><span data-stu-id="9d99e-2849">bic number</span></span> 
- <span data-ttu-id="9d99e-2850">bic code
</span><span class="sxs-lookup"><span data-stu-id="9d99e-2850">bic code</span></span> 
- <span data-ttu-id="9d99e-2851">BIC\#</span><span class="sxs-lookup"><span data-stu-id="9d99e-2851">bic \#</span></span> 
- <span data-ttu-id="9d99e-2852">BIC\#</span><span class="sxs-lookup"><span data-stu-id="9d99e-2852">bic\#</span></span> 
- <span data-ttu-id="9d99e-2853">bank identifier code
</span><span class="sxs-lookup"><span data-stu-id="9d99e-2853">bank identifier code</span></span> 
- <span data-ttu-id="9d99e-2854">標準化9362</span><span class="sxs-lookup"><span data-stu-id="9d99e-2854">標準化9362</span></span> 
- <span data-ttu-id="9d99e-2855">迅速＃
</span><span class="sxs-lookup"><span data-stu-id="9d99e-2855">迅速＃</span></span> 
- <span data-ttu-id="9d99e-2856">SWIFTコード
</span><span class="sxs-lookup"><span data-stu-id="9d99e-2856">SWIFTコード</span></span> 
- <span data-ttu-id="9d99e-2857">SWIFT番号
</span><span class="sxs-lookup"><span data-stu-id="9d99e-2857">SWIFT番号</span></span> 
- <span data-ttu-id="9d99e-2858">迅速なルーティング番号
</span><span class="sxs-lookup"><span data-stu-id="9d99e-2858">迅速なルーティング番号</span></span> 
- <span data-ttu-id="9d99e-2859">BIC番号
</span><span class="sxs-lookup"><span data-stu-id="9d99e-2859">BIC番号</span></span> 
- <span data-ttu-id="9d99e-2860">BICコード
</span><span class="sxs-lookup"><span data-stu-id="9d99e-2860">BICコード</span></span> 
- <span data-ttu-id="9d99e-2861">銀行識別コードのための国際組織
</span><span class="sxs-lookup"><span data-stu-id="9d99e-2861">銀行識別コードのための国際組織</span></span> 
- <span data-ttu-id="9d99e-2862">Organisation internationale de normalisation 9362
</span><span class="sxs-lookup"><span data-stu-id="9d99e-2862">Organisation internationale de normalisation 9362</span></span> 
- <span data-ttu-id="9d99e-2863">rapide\#</span><span class="sxs-lookup"><span data-stu-id="9d99e-2863">rapide \#</span></span> 
- <span data-ttu-id="9d99e-2864">code SWIFT
</span><span class="sxs-lookup"><span data-stu-id="9d99e-2864">code SWIFT</span></span> 
- <span data-ttu-id="9d99e-2865">le numéro de swift
</span><span class="sxs-lookup"><span data-stu-id="9d99e-2865">le numéro de swift</span></span> 
- <span data-ttu-id="9d99e-2866">swift numéro d'acheminement
</span><span class="sxs-lookup"><span data-stu-id="9d99e-2866">swift numéro d'acheminement</span></span> 
- <span data-ttu-id="9d99e-2867">le numéro BIC
</span><span class="sxs-lookup"><span data-stu-id="9d99e-2867">le numéro BIC</span></span> 
- <span data-ttu-id="9d99e-2868">\#BIC</span><span class="sxs-lookup"><span data-stu-id="9d99e-2868">\# BIC</span></span> 
- <span data-ttu-id="9d99e-2869">code identificateur de banque
</span><span class="sxs-lookup"><span data-stu-id="9d99e-2869">code identificateur de banque</span></span> 
   
## <a name="taiwan-national-id"></a><span data-ttu-id="9d99e-2870">Taiwan National ID</span><span class="sxs-lookup"><span data-stu-id="9d99e-2870">Taiwan National ID</span></span>

### <a name="format"></a><span data-ttu-id="9d99e-2871">Formato</span><span class="sxs-lookup"><span data-stu-id="9d99e-2871">Format</span></span>

<span data-ttu-id="9d99e-2872">Una lettera (in lingua inglese) seguita da nove cifre</span><span class="sxs-lookup"><span data-stu-id="9d99e-2872">One letter (in English) followed by nine digits</span></span>

### <a name="pattern"></a><span data-ttu-id="9d99e-2873">Modello</span><span class="sxs-lookup"><span data-stu-id="9d99e-2873">Pattern</span></span>

<span data-ttu-id="9d99e-2874">Una lettera (in lingua inglese) seguita da nove cifre:</span><span class="sxs-lookup"><span data-stu-id="9d99e-2874">One letter (in English) followed by nine digits:</span></span>
- <span data-ttu-id="9d99e-2875">Una lettera (in inglese, senza distinzione tra tra maiuscole/minuscole)</span><span class="sxs-lookup"><span data-stu-id="9d99e-2875">One letter (in English, not case sensitive)</span></span> 
- <span data-ttu-id="9d99e-2876">La cifra "1" o "2"</span><span class="sxs-lookup"><span data-stu-id="9d99e-2876">The digit "1" or "2"</span></span> 
- <span data-ttu-id="9d99e-2877">Otto cifre</span><span class="sxs-lookup"><span data-stu-id="9d99e-2877">Eight digits</span></span>

### <a name="checksum"></a><span data-ttu-id="9d99e-2878">Checksum</span><span class="sxs-lookup"><span data-stu-id="9d99e-2878">Checksum</span></span>

<span data-ttu-id="9d99e-2879">Sì</span><span class="sxs-lookup"><span data-stu-id="9d99e-2879">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="9d99e-2880">Definizione</span><span class="sxs-lookup"><span data-stu-id="9d99e-2880">Definition</span></span>

<span data-ttu-id="9d99e-2881">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="9d99e-2881">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="9d99e-2882">La funzione Func_taiwanese_national_id restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="9d99e-2882">The function Func_taiwanese_national_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="9d99e-2883">Viene trovata una parola chiave da Keyword_taiwanese_national_id.</span><span class="sxs-lookup"><span data-stu-id="9d99e-2883">A keyword from Keyword_taiwanese_national_id is found.</span></span>
- <span data-ttu-id="9d99e-2884">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="9d99e-2884">The checksum passes.</span></span>

```
<!-- Taiwanese National ID -->
<Entity id="4C7BFC34-8DD1-421D-8FB7-6C6182C2AF03" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_taiwanese_national_id" />
          <Match idRef="Keyword_taiwanese_national_id" />
      </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="9d99e-2885">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="9d99e-2885">Keywords</span></span>

#### <a name="keywordtaiwanesenationalid"></a><span data-ttu-id="9d99e-2886">Keyword_taiwanese_national_id</span><span class="sxs-lookup"><span data-stu-id="9d99e-2886">Keyword_taiwanese_national_id</span></span>

- <span data-ttu-id="9d99e-2887">身份證字號
</span><span class="sxs-lookup"><span data-stu-id="9d99e-2887">身份證字號</span></span> 
- <span data-ttu-id="9d99e-2888">身份證
</span><span class="sxs-lookup"><span data-stu-id="9d99e-2888">身份證</span></span> 
- <span data-ttu-id="9d99e-2889">身份證號碼
</span><span class="sxs-lookup"><span data-stu-id="9d99e-2889">身份證號碼</span></span> 
- <span data-ttu-id="9d99e-2890">身份證號
</span><span class="sxs-lookup"><span data-stu-id="9d99e-2890">身份證號</span></span> 
- <span data-ttu-id="9d99e-2891">身分證字號
</span><span class="sxs-lookup"><span data-stu-id="9d99e-2891">身分證字號</span></span> 
- <span data-ttu-id="9d99e-2892">身分證 </span><span class="sxs-lookup"><span data-stu-id="9d99e-2892">身分證</span></span> 
- <span data-ttu-id="9d99e-2893">身分證號碼
</span><span class="sxs-lookup"><span data-stu-id="9d99e-2893">身分證號碼</span></span> 
- <span data-ttu-id="9d99e-2894">身份證號
</span><span class="sxs-lookup"><span data-stu-id="9d99e-2894">身份證號</span></span> 
- <span data-ttu-id="9d99e-2895">身分證統一編號
</span><span class="sxs-lookup"><span data-stu-id="9d99e-2895">身分證統一編號</span></span> 
- <span data-ttu-id="9d99e-2896">國民身分證統一編號
</span><span class="sxs-lookup"><span data-stu-id="9d99e-2896">國民身分證統一編號</span></span> 
- <span data-ttu-id="9d99e-2897">簽名
</span><span class="sxs-lookup"><span data-stu-id="9d99e-2897">簽名</span></span> 
- <span data-ttu-id="9d99e-2898">蓋章
</span><span class="sxs-lookup"><span data-stu-id="9d99e-2898">蓋章</span></span> 
- <span data-ttu-id="9d99e-2899">簽名或蓋章

</span><span class="sxs-lookup"><span data-stu-id="9d99e-2899">簽名或蓋章</span></span> 
- <span data-ttu-id="9d99e-2900">簽章</span><span class="sxs-lookup"><span data-stu-id="9d99e-2900">簽章</span></span>   
   
## <a name="taiwan-passport-number"></a><span data-ttu-id="9d99e-2901">	Taiwan - Numero di passaporto</span><span class="sxs-lookup"><span data-stu-id="9d99e-2901">Taiwan Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="9d99e-2902">Formato</span><span class="sxs-lookup"><span data-stu-id="9d99e-2902">Format</span></span>

- <span data-ttu-id="9d99e-2903">Numero di passaporto biometrica: nove cifre</span><span class="sxs-lookup"><span data-stu-id="9d99e-2903">Biometric passport number: Nine digits</span></span>
- <span data-ttu-id="9d99e-2904">Numero di passaporto non biometrica: nove cifre</span><span class="sxs-lookup"><span data-stu-id="9d99e-2904">Non-biometric passport number: Nine digits</span></span>

### <a name="pattern"></a><span data-ttu-id="9d99e-2905">Modello</span><span class="sxs-lookup"><span data-stu-id="9d99e-2905">Pattern</span></span>
<span data-ttu-id="9d99e-2906">Numero di passaporto biometrica:</span><span class="sxs-lookup"><span data-stu-id="9d99e-2906">Biometric passport number:</span></span>
- <span data-ttu-id="9d99e-2907">La cifra "3" </span><span class="sxs-lookup"><span data-stu-id="9d99e-2907">The digit "3"</span></span> 
- <span data-ttu-id="9d99e-2908">Otto cifre</span><span class="sxs-lookup"><span data-stu-id="9d99e-2908">Eight digits</span></span>

<span data-ttu-id="9d99e-2909">Numero di passaporto biometrica non:</span><span class="sxs-lookup"><span data-stu-id="9d99e-2909">Non-biometric passport number:</span></span>
- <span data-ttu-id="9d99e-2910">9 cifre</span><span class="sxs-lookup"><span data-stu-id="9d99e-2910">Nine digits</span></span>

### <a name="checksum"></a><span data-ttu-id="9d99e-2911">Checksum</span><span class="sxs-lookup"><span data-stu-id="9d99e-2911">Checksum</span></span>

<span data-ttu-id="9d99e-2912">No</span><span class="sxs-lookup"><span data-stu-id="9d99e-2912">No</span></span>

### <a name="definition"></a><span data-ttu-id="9d99e-2913">Definizione</span><span class="sxs-lookup"><span data-stu-id="9d99e-2913">Definition</span></span>

<span data-ttu-id="9d99e-2914">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="9d99e-2914">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="9d99e-2915">L'espressione regolare Regex_taiwan_passport consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="9d99e-2915">The regular expression Regex_taiwan_passport finds content that matches the pattern.</span></span>
- <span data-ttu-id="9d99e-2916">È possibile trovare una parola chiave da Keyword_taiwan_passport.</span><span class="sxs-lookup"><span data-stu-id="9d99e-2916">A keyword from Keyword_taiwan_passport is found.</span></span>

```
<!-- Taiwan Passport Number -->
<Entity id="e7251cb4-4c2c-41df-963e-924eb3dae04a" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_taiwan_passport"/>
     <Match idRef="Keyword_taiwan_passport"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="9d99e-2917">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="9d99e-2917">Keywords</span></span>

#### <a name="keywordtaiwanpassport"></a><span data-ttu-id="9d99e-2918">Keyword_taiwan_passport</span><span class="sxs-lookup"><span data-stu-id="9d99e-2918">Keyword_taiwan_passport</span></span>

- <span data-ttu-id="9d99e-2919">Numero passaporto ROC

</span><span class="sxs-lookup"><span data-stu-id="9d99e-2919">ROC passport number</span></span> 
- <span data-ttu-id="9d99e-2920">Numero di passaporto</span><span class="sxs-lookup"><span data-stu-id="9d99e-2920">Passport number</span></span> 
- <span data-ttu-id="9d99e-2921">Passport non</span><span class="sxs-lookup"><span data-stu-id="9d99e-2921">Passport no</span></span> 
- <span data-ttu-id="9d99e-2922">Num. passaporto
</span><span class="sxs-lookup"><span data-stu-id="9d99e-2922">Passport Num</span></span> 
- <span data-ttu-id="9d99e-2923">Passport#
</span><span class="sxs-lookup"><span data-stu-id="9d99e-2923">Passport #</span></span> 
- <span data-ttu-id="9d99e-2924">护照
</span><span class="sxs-lookup"><span data-stu-id="9d99e-2924">护照</span></span> 
- <span data-ttu-id="9d99e-2925">中華民國護照
</span><span class="sxs-lookup"><span data-stu-id="9d99e-2925">中華民國護照</span></span> 
- <span data-ttu-id="9d99e-2926">Zhōnghuá Mínguó hùzhào</span><span class="sxs-lookup"><span data-stu-id="9d99e-2926">Zhōnghuá Mínguó hùzhào</span></span>
   
## <a name="taiwan-resident-certificate-arctarc-number"></a><span data-ttu-id="9d99e-2927">Taiwan - Numero certificato di residenza (ARC/TARC)</span><span class="sxs-lookup"><span data-stu-id="9d99e-2927">Taiwan Resident Certificate (ARC/TARC) Number</span></span>

### <a name="format"></a><span data-ttu-id="9d99e-2928">Formato</span><span class="sxs-lookup"><span data-stu-id="9d99e-2928">Format</span></span>

<span data-ttu-id="9d99e-2929">10 lettere e cifre</span><span class="sxs-lookup"><span data-stu-id="9d99e-2929">10 letters and digits</span></span>

### <a name="pattern"></a><span data-ttu-id="9d99e-2930">Modello</span><span class="sxs-lookup"><span data-stu-id="9d99e-2930">Pattern</span></span>

<span data-ttu-id="9d99e-2931">10 lettere e cifre:</span><span class="sxs-lookup"><span data-stu-id="9d99e-2931">10 letters and digits:</span></span>
- <span data-ttu-id="9d99e-2932">Due lettere (senza distinzione tra maiuscole/minuscole)</span><span class="sxs-lookup"><span data-stu-id="9d99e-2932">Two letters (not case sensitive)</span></span> 
- <span data-ttu-id="9d99e-2933">Otto cifre</span><span class="sxs-lookup"><span data-stu-id="9d99e-2933">Eight digits</span></span>

### <a name="checksum"></a><span data-ttu-id="9d99e-2934">Checksum</span><span class="sxs-lookup"><span data-stu-id="9d99e-2934">Checksum</span></span>

<span data-ttu-id="9d99e-2935">No</span><span class="sxs-lookup"><span data-stu-id="9d99e-2935">No</span></span>

### <a name="definition"></a><span data-ttu-id="9d99e-2936">Definizione</span><span class="sxs-lookup"><span data-stu-id="9d99e-2936">Definition</span></span>

<span data-ttu-id="9d99e-2937">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="9d99e-2937">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="9d99e-2938">L'espressione regolare Regex_taiwan_resident_certificate consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="9d99e-2938">The regular expression Regex_taiwan_resident_certificate finds content that matches the pattern.</span></span>
- <span data-ttu-id="9d99e-2939">È possibile trovare una parola chiave da Keyword_taiwan_resident_certificate.</span><span class="sxs-lookup"><span data-stu-id="9d99e-2939">A keyword from Keyword_taiwan_resident_certificate is found.</span></span>

```
<!-- Taiwan Resident Certificate (ARC/TARC) -->
<Entity id="48269fec-05ea-46ea-b326-f5623a58c6e9" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_taiwan_resident_certificate"/>
     <Match idRef="Keyword_taiwan_resident_certificate"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="9d99e-2940">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="9d99e-2940">Keywords</span></span>

#### <a name="keywordtaiwanresidentcertificate"></a><span data-ttu-id="9d99e-2941">Keyword_taiwan_resident_certificate</span><span class="sxs-lookup"><span data-stu-id="9d99e-2941">Keyword_taiwan_resident_certificate</span></span>

- <span data-ttu-id="9d99e-2942">Certificato di residenza
</span><span class="sxs-lookup"><span data-stu-id="9d99e-2942">Resident Certificate</span></span> 
- <span data-ttu-id="9d99e-2943">Cert residenti</span><span class="sxs-lookup"><span data-stu-id="9d99e-2943">Resident Cert</span></span> 
- <span data-ttu-id="9d99e-2944">Cert. di resid.
</span><span class="sxs-lookup"><span data-stu-id="9d99e-2944">Resident Cert.</span></span> 
- <span data-ttu-id="9d99e-2945">Scheda di identificazione</span><span class="sxs-lookup"><span data-stu-id="9d99e-2945">Identification card</span></span> 
- <span data-ttu-id="9d99e-2946">Certificato residente straniero
</span><span class="sxs-lookup"><span data-stu-id="9d99e-2946">Alien Resident Certificate</span></span> 
- <span data-ttu-id="9d99e-2947">ARC
</span><span class="sxs-lookup"><span data-stu-id="9d99e-2947">ARC</span></span> 
- <span data-ttu-id="9d99e-2948">Certificato residente nell’area di Taiwan
</span><span class="sxs-lookup"><span data-stu-id="9d99e-2948">Taiwan Area Resident Certificate</span></span> 
- <span data-ttu-id="9d99e-2949">TARC
</span><span class="sxs-lookup"><span data-stu-id="9d99e-2949">TARC</span></span> 
- <span data-ttu-id="9d99e-2950">居留證
</span><span class="sxs-lookup"><span data-stu-id="9d99e-2950">居留證</span></span> 
- <span data-ttu-id="9d99e-2951">外僑居留證
</span><span class="sxs-lookup"><span data-stu-id="9d99e-2951">外僑居留證</span></span> 
- <span data-ttu-id="9d99e-2952">台灣地區居留證
</span><span class="sxs-lookup"><span data-stu-id="9d99e-2952">台灣地區居留證</span></span> 
   
## <a name="uk-drivers-license-number"></a><span data-ttu-id="9d99e-p141">Regno Unito - Numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="9d99e-p141">U.K. Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="9d99e-2955">Formato</span><span class="sxs-lookup"><span data-stu-id="9d99e-2955">Format</span></span>

<span data-ttu-id="9d99e-2956">Combinazione di 18 lettere e numeri nel formato specificato</span><span class="sxs-lookup"><span data-stu-id="9d99e-2956">Combination of 18 letters and digits in the specified format</span></span>

### <a name="pattern"></a><span data-ttu-id="9d99e-2957">Modello</span><span class="sxs-lookup"><span data-stu-id="9d99e-2957">Pattern</span></span>

<span data-ttu-id="9d99e-2958">18 lettere e cifre:</span><span class="sxs-lookup"><span data-stu-id="9d99e-2958">18 letters and digits:</span></span>
- <span data-ttu-id="9d99e-2959">Cinque lettere (senza distinzione fra maiuscole/minuscole) o la cifra 9 al posto di una lettera</span><span class="sxs-lookup"><span data-stu-id="9d99e-2959">Five letters (not case sensitive) or the digit "9" in place of a letter</span></span> 
- <span data-ttu-id="9d99e-2960">Una cifra</span><span class="sxs-lookup"><span data-stu-id="9d99e-2960">One digit</span></span> 
- <span data-ttu-id="9d99e-2961">5 cifre nel formato data GGMMA relativo alla data di nascita</span><span class="sxs-lookup"><span data-stu-id="9d99e-2961">Five digits in the date format DDMMY for date of birth</span></span> 
- <span data-ttu-id="9d99e-2962">Due lettere (senza distinzione fra maiuscole/minuscole) o la cifra 9 al posto di una lettera</span><span class="sxs-lookup"><span data-stu-id="9d99e-2962">Two letters (not case sensitive) or the digit "9" in place of a letter</span></span> 
- <span data-ttu-id="9d99e-2963">Cinque cifre</span><span class="sxs-lookup"><span data-stu-id="9d99e-2963">Five digits</span></span>

### <a name="checksum"></a><span data-ttu-id="9d99e-2964">Checksum</span><span class="sxs-lookup"><span data-stu-id="9d99e-2964">Checksum</span></span>

<span data-ttu-id="9d99e-2965">Sì</span><span class="sxs-lookup"><span data-stu-id="9d99e-2965">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="9d99e-2966">Definizione</span><span class="sxs-lookup"><span data-stu-id="9d99e-2966">Definition</span></span>

<span data-ttu-id="9d99e-2967">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="9d99e-2967">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="9d99e-2968">La funzione Func_uk_drivers_license restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="9d99e-2968">The function Func_uk_drivers_license finds content that matches the pattern.</span></span>
- <span data-ttu-id="9d99e-2969">Viene trovata una parola chiave da Keyword_uk_drivers_license.</span><span class="sxs-lookup"><span data-stu-id="9d99e-2969">A keyword from Keyword_uk_drivers_license is found.</span></span>
- <span data-ttu-id="9d99e-2970">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="9d99e-2970">The checksum passes.</span></span>

```
<!-- U.K. Driver's License Number -->
<Entity id="f93de4be-d94c-40df-a8be-461738047551" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_uk_drivers_license" />
        <Match idRef="Keyword_uk_drivers_license" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="9d99e-2971">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="9d99e-2971">Keywords</span></span>

#### <a name="keywordukdriverslicense"></a><span data-ttu-id="9d99e-2972">Keyword_uk_drivers_license</span><span class="sxs-lookup"><span data-stu-id="9d99e-2972">Keyword_uk_drivers_license</span></span>

- <span data-ttu-id="9d99e-2973">DVLA
</span><span class="sxs-lookup"><span data-stu-id="9d99e-2973">DVLA</span></span> 
- <span data-ttu-id="9d99e-2974">light vans
</span><span class="sxs-lookup"><span data-stu-id="9d99e-2974">light vans</span></span> 
- <span data-ttu-id="9d99e-2975">quadbikes
</span><span class="sxs-lookup"><span data-stu-id="9d99e-2975">quadbikes</span></span> 
- <span data-ttu-id="9d99e-2976">motor cars
</span><span class="sxs-lookup"><span data-stu-id="9d99e-2976">motor cars</span></span> 
- <span data-ttu-id="9d99e-2977">125cc</span><span class="sxs-lookup"><span data-stu-id="9d99e-2977">125cc</span></span> 
- <span data-ttu-id="9d99e-2978">sidecar
</span><span class="sxs-lookup"><span data-stu-id="9d99e-2978">sidecar</span></span> 
- <span data-ttu-id="9d99e-2979">tricycles
</span><span class="sxs-lookup"><span data-stu-id="9d99e-2979">tricycles</span></span> 
- <span data-ttu-id="9d99e-2980">motorcycles
</span><span class="sxs-lookup"><span data-stu-id="9d99e-2980">motorcycles</span></span> 
- <span data-ttu-id="9d99e-2981">photocard licence
</span><span class="sxs-lookup"><span data-stu-id="9d99e-2981">photocard licence</span></span> 
- <span data-ttu-id="9d99e-2982">learner drivers
</span><span class="sxs-lookup"><span data-stu-id="9d99e-2982">learner drivers</span></span> 
- <span data-ttu-id="9d99e-2983">licence holder
</span><span class="sxs-lookup"><span data-stu-id="9d99e-2983">licence holder</span></span> 
- <span data-ttu-id="9d99e-2984">licence holders
</span><span class="sxs-lookup"><span data-stu-id="9d99e-2984">licence holders</span></span> 
- <span data-ttu-id="9d99e-2985">driving licences
</span><span class="sxs-lookup"><span data-stu-id="9d99e-2985">driving licences</span></span> 
- <span data-ttu-id="9d99e-2986">driving licence
</span><span class="sxs-lookup"><span data-stu-id="9d99e-2986">driving licence</span></span> 
- <span data-ttu-id="9d99e-2987">dual control car
</span><span class="sxs-lookup"><span data-stu-id="9d99e-2987">dual control car</span></span> 
   
## <a name="uk-electoral-roll-number"></a><span data-ttu-id="9d99e-p142">Regno Unito - Numero di iscrizione alle liste elettorali</span><span class="sxs-lookup"><span data-stu-id="9d99e-p142">U.K. Electoral Roll Number</span></span>

### <a name="format"></a><span data-ttu-id="9d99e-2990">Formato</span><span class="sxs-lookup"><span data-stu-id="9d99e-2990">Format</span></span>

<span data-ttu-id="9d99e-2991">Due lettere seguite da 1-4 cifre</span><span class="sxs-lookup"><span data-stu-id="9d99e-2991">Two letters followed by 1-4 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="9d99e-2992">Modello</span><span class="sxs-lookup"><span data-stu-id="9d99e-2992">Pattern</span></span>

<span data-ttu-id="9d99e-2993">Due lettere (senza distinzione fra maiuscole/minuscole) seguite da 1-4 numeri</span><span class="sxs-lookup"><span data-stu-id="9d99e-2993">Two letters (not case sensitive) followed by 1-4 numbers</span></span>

### <a name="checksum"></a><span data-ttu-id="9d99e-2994">Checksum</span><span class="sxs-lookup"><span data-stu-id="9d99e-2994">Checksum</span></span>

<span data-ttu-id="9d99e-2995">No</span><span class="sxs-lookup"><span data-stu-id="9d99e-2995">No</span></span>

### <a name="definition"></a><span data-ttu-id="9d99e-2996">Definizione</span><span class="sxs-lookup"><span data-stu-id="9d99e-2996">Definition</span></span>

<span data-ttu-id="9d99e-2997">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="9d99e-2997">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="9d99e-2998">L'espressione regolare Regex_uk_electoral restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="9d99e-2998">The regular expression Regex_uk_electoral finds content that matches the pattern.</span></span>
- <span data-ttu-id="9d99e-2999">Viene trovata una parola chiave da Keyword_uk_electoral.</span><span class="sxs-lookup"><span data-stu-id="9d99e-2999">A keyword from Keyword_uk_electoral is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="9d99e-3000">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="9d99e-3000">Keywords</span></span>

#### <a name="keywordukelectoral"></a><span data-ttu-id="9d99e-3001">Keyword_uk_electoral</span><span class="sxs-lookup"><span data-stu-id="9d99e-3001">Keyword_uk_electoral</span></span>

- <span data-ttu-id="9d99e-3002">council nomination
</span><span class="sxs-lookup"><span data-stu-id="9d99e-3002">council nomination</span></span> 
- <span data-ttu-id="9d99e-3003">nomination form
</span><span class="sxs-lookup"><span data-stu-id="9d99e-3003">nomination form</span></span> 
- <span data-ttu-id="9d99e-3004">electoral register

</span><span class="sxs-lookup"><span data-stu-id="9d99e-3004">electoral register</span></span> 
- <span data-ttu-id="9d99e-3005">electoral roll</span><span class="sxs-lookup"><span data-stu-id="9d99e-3005">electoral roll</span></span>

   
## <a name="uk-national-health-service-number"></a><span data-ttu-id="9d99e-p143">Regno Unito - Codice del servizio sanitario nazionale</span><span class="sxs-lookup"><span data-stu-id="9d99e-p143">U.K. National Health Service Number</span></span>

### <a name="format"></a><span data-ttu-id="9d99e-3008">Formato</span><span class="sxs-lookup"><span data-stu-id="9d99e-3008">Format</span></span>

<span data-ttu-id="9d99e-3009">10-17 cifre separate da spazi</span><span class="sxs-lookup"><span data-stu-id="9d99e-3009">10-17 digits separated by spaces</span></span>

### <a name="pattern"></a><span data-ttu-id="9d99e-3010">Modello</span><span class="sxs-lookup"><span data-stu-id="9d99e-3010">Pattern</span></span>

<span data-ttu-id="9d99e-3011">10-17 cifre:</span><span class="sxs-lookup"><span data-stu-id="9d99e-3011">10-17 digits:</span></span>
- <span data-ttu-id="9d99e-3012">3 o 10 cifre</span><span class="sxs-lookup"><span data-stu-id="9d99e-3012">Either 3 or 10 digits</span></span> 
- <span data-ttu-id="9d99e-3013">Uno spazio</span><span class="sxs-lookup"><span data-stu-id="9d99e-3013">A space</span></span> 
- <span data-ttu-id="9d99e-3014">Tre cifre</span><span class="sxs-lookup"><span data-stu-id="9d99e-3014">Three digits</span></span> 
- <span data-ttu-id="9d99e-3015">Uno spazio</span><span class="sxs-lookup"><span data-stu-id="9d99e-3015">A space</span></span> 
- <span data-ttu-id="9d99e-3016">Quattro cifre</span><span class="sxs-lookup"><span data-stu-id="9d99e-3016">Four digits</span></span>

### <a name="checksum"></a><span data-ttu-id="9d99e-3017">Checksum</span><span class="sxs-lookup"><span data-stu-id="9d99e-3017">Checksum</span></span>

<span data-ttu-id="9d99e-3018">Sì</span><span class="sxs-lookup"><span data-stu-id="9d99e-3018">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="9d99e-3019">Definizione</span><span class="sxs-lookup"><span data-stu-id="9d99e-3019">Definition</span></span>

<span data-ttu-id="9d99e-3020">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="9d99e-3020">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="9d99e-3021">La funzione Func_uk_nhs_number restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="9d99e-3021">The function Func_uk_nhs_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="9d99e-3022">Si verifica una delle situazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="9d99e-3022">One of the following is true:</span></span>
    - <span data-ttu-id="9d99e-3023">Viene trovata una parola chiave da Keyword_uk_nhs_number.</span><span class="sxs-lookup"><span data-stu-id="9d99e-3023">A keyword from Keyword_uk_nhs_number is found.</span></span>
    - <span data-ttu-id="9d99e-3024">Viene trovata una parola chiave da Keyword_uk_nhs_number1.</span><span class="sxs-lookup"><span data-stu-id="9d99e-3024">A keyword from Keyword_uk_nhs_number1 is found.</span></span>
    - <span data-ttu-id="9d99e-3025">Viene trovata una parola chiave da Keyword_uk_nhs_number_dob.</span><span class="sxs-lookup"><span data-stu-id="9d99e-3025">A keyword from Keyword_uk_nhs_number_dob is found.</span></span>
- <span data-ttu-id="9d99e-3026">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="9d99e-3026">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="9d99e-3027">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="9d99e-3027">Keywords</span></span>
   
#### <a name="keyworduknhsnumber"></a><span data-ttu-id="9d99e-3028">Keyword_uk_nhs_number</span><span class="sxs-lookup"><span data-stu-id="9d99e-3028">Keyword_uk_nhs_number</span></span>

- <span data-ttu-id="9d99e-3029">national health service
</span><span class="sxs-lookup"><span data-stu-id="9d99e-3029">national health service</span></span> 
- <span data-ttu-id="9d99e-3030">nhs
</span><span class="sxs-lookup"><span data-stu-id="9d99e-3030">nhs</span></span> 
- <span data-ttu-id="9d99e-3031">health services authority

</span><span class="sxs-lookup"><span data-stu-id="9d99e-3031">health services authority</span></span> 
- <span data-ttu-id="9d99e-3032">health authority</span><span class="sxs-lookup"><span data-stu-id="9d99e-3032">health authority</span></span>

#### <a name="keyworduknhsnumber1"></a><span data-ttu-id="9d99e-3033">Keyword_uk_nhs_number1</span><span class="sxs-lookup"><span data-stu-id="9d99e-3033">Keyword_uk_nhs_number1</span></span>

- <span data-ttu-id="9d99e-3034">patient id
</span><span class="sxs-lookup"><span data-stu-id="9d99e-3034">patient id</span></span> 
- <span data-ttu-id="9d99e-3035">patient identification
</span><span class="sxs-lookup"><span data-stu-id="9d99e-3035">patient identification</span></span> 
- <span data-ttu-id="9d99e-3036">patient no

</span><span class="sxs-lookup"><span data-stu-id="9d99e-3036">patient no</span></span> 
- <span data-ttu-id="9d99e-3037">patient number</span><span class="sxs-lookup"><span data-stu-id="9d99e-3037">patient number</span></span>

#### <a name="keyworduknhsnumberdob"></a><span data-ttu-id="9d99e-3038">Keyword_uk_nhs_number_dob</span><span class="sxs-lookup"><span data-stu-id="9d99e-3038">Keyword_uk_nhs_number_dob</span></span>

- <span data-ttu-id="9d99e-3039">Criteri di gruppo</span><span class="sxs-lookup"><span data-stu-id="9d99e-3039">GP</span></span> 
- <span data-ttu-id="9d99e-3040">DOB
</span><span class="sxs-lookup"><span data-stu-id="9d99e-3040">DOB</span></span> 
- <span data-ttu-id="9d99e-3041">D.O.B</span><span class="sxs-lookup"><span data-stu-id="9d99e-3041">D.O.B</span></span> 
- <span data-ttu-id="9d99e-3042">Date of Birth
</span><span class="sxs-lookup"><span data-stu-id="9d99e-3042">Date of Birth</span></span> 
- <span data-ttu-id="9d99e-3043">Birth Date
</span><span class="sxs-lookup"><span data-stu-id="9d99e-3043">Birth Date</span></span> 
   
## <a name="uk-national-insurance-number-nino"></a><span data-ttu-id="9d99e-p144">Regno Unito - Numero di assicurazione nazionale (NINO)</span><span class="sxs-lookup"><span data-stu-id="9d99e-p144">U.K. National Insurance Number (NINO)</span></span>

### <a name="format"></a><span data-ttu-id="9d99e-3046">Formato</span><span class="sxs-lookup"><span data-stu-id="9d99e-3046">Format</span></span>

<span data-ttu-id="9d99e-3047">7 cifre o 9 caratteri separati da spazi o trattini</span><span class="sxs-lookup"><span data-stu-id="9d99e-3047">7 characters or 9 characters separated by spaces or dashes</span></span>

### <a name="pattern"></a><span data-ttu-id="9d99e-3048">Modello</span><span class="sxs-lookup"><span data-stu-id="9d99e-3048">Pattern</span></span>

<span data-ttu-id="9d99e-3049">Due possibili motivi:</span><span class="sxs-lookup"><span data-stu-id="9d99e-3049">Two possible patterns:</span></span>

- <span data-ttu-id="9d99e-3050">Due lettere (NINOs valido utilizzare solo alcuni caratteri in questo prefisso, questo modello consente di convalidare; non maiuscole/minuscole)</span><span class="sxs-lookup"><span data-stu-id="9d99e-3050">Two letters (valid NINOs use only certain characters in this prefix, which this pattern validates; not case sensitive)</span></span>
- <span data-ttu-id="9d99e-3051">Sei cifre</span><span class="sxs-lookup"><span data-stu-id="9d99e-3051">Six digits</span></span>
- <span data-ttu-id="9d99e-3052">Entrambi '', "B", "C", oppure con ' (ad esempio il prefisso solo alcuni caratteri sono consentiti in suffisso; non distinzione tra maiuscole e minuscole)</span><span class="sxs-lookup"><span data-stu-id="9d99e-3052">Either 'A', 'B', 'C', or 'D' (like the prefix, only certain characters are allowed in the suffix; not case sensitive)</span></span>

<span data-ttu-id="9d99e-3053">OPPURE</span><span class="sxs-lookup"><span data-stu-id="9d99e-3053">OR</span></span>

- <span data-ttu-id="9d99e-3054">Due lettere</span><span class="sxs-lookup"><span data-stu-id="9d99e-3054">Two letters</span></span>
- <span data-ttu-id="9d99e-3055">Uno spazio o un trattino</span><span class="sxs-lookup"><span data-stu-id="9d99e-3055">A space or dash</span></span>
- <span data-ttu-id="9d99e-3056">Due cifre</span><span class="sxs-lookup"><span data-stu-id="9d99e-3056">Two digits</span></span>
- <span data-ttu-id="9d99e-3057">Uno spazio o un trattino</span><span class="sxs-lookup"><span data-stu-id="9d99e-3057">A space or dash</span></span>
- <span data-ttu-id="9d99e-3058">Due cifre</span><span class="sxs-lookup"><span data-stu-id="9d99e-3058">Two digits</span></span>
- <span data-ttu-id="9d99e-3059">Uno spazio o un trattino</span><span class="sxs-lookup"><span data-stu-id="9d99e-3059">A space or dash</span></span>
- <span data-ttu-id="9d99e-3060">Due cifre</span><span class="sxs-lookup"><span data-stu-id="9d99e-3060">Two digits</span></span>
- <span data-ttu-id="9d99e-3061">Uno spazio o un trattino</span><span class="sxs-lookup"><span data-stu-id="9d99e-3061">A space or dash</span></span>
- <span data-ttu-id="9d99e-3062">Entrambi 'A', "B", "C", oppure con '</span><span class="sxs-lookup"><span data-stu-id="9d99e-3062">Either 'A', 'B', 'C', or 'D'</span></span>

### <a name="checksum"></a><span data-ttu-id="9d99e-3063">Checksum</span><span class="sxs-lookup"><span data-stu-id="9d99e-3063">Checksum</span></span>

<span data-ttu-id="9d99e-3064">No</span><span class="sxs-lookup"><span data-stu-id="9d99e-3064">No</span></span>

### <a name="definition"></a><span data-ttu-id="9d99e-3065">Definizione</span><span class="sxs-lookup"><span data-stu-id="9d99e-3065">Definition</span></span>

<span data-ttu-id="9d99e-3066">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="9d99e-3066">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="9d99e-3067">La funzione Func_uk_nino restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="9d99e-3067">The function Func_uk_nino finds content that matches the pattern.</span></span>
- <span data-ttu-id="9d99e-3068">Viene trovata una parola chiave da Keyword_uk_nino.</span><span class="sxs-lookup"><span data-stu-id="9d99e-3068">A keyword from Keyword_uk_nino is found.</span></span>

<span data-ttu-id="9d99e-3069">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="9d99e-3069">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="9d99e-3070">La funzione Func_uk_nino restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="9d99e-3070">The function Func_uk_nino finds content that matches the pattern.</span></span>
- <span data-ttu-id="9d99e-3071">Non vengono trovate parole chiave da Keyword_uk_nino.</span><span class="sxs-lookup"><span data-stu-id="9d99e-3071">No keyword from Keyword_uk_nino is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="9d99e-3072">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="9d99e-3072">Keywords</span></span>

#### <a name="keyworduknino"></a><span data-ttu-id="9d99e-3073">Keyword_uk_nino</span><span class="sxs-lookup"><span data-stu-id="9d99e-3073">Keyword_uk_nino</span></span>

- <span data-ttu-id="9d99e-3074">national insurance number
</span><span class="sxs-lookup"><span data-stu-id="9d99e-3074">national insurance number</span></span> 
- <span data-ttu-id="9d99e-3075">national insurance contributions
</span><span class="sxs-lookup"><span data-stu-id="9d99e-3075">national insurance contributions</span></span> 
- <span data-ttu-id="9d99e-3076">protection act
</span><span class="sxs-lookup"><span data-stu-id="9d99e-3076">protection act</span></span> 
- <span data-ttu-id="9d99e-3077">insurance
</span><span class="sxs-lookup"><span data-stu-id="9d99e-3077">insurance</span></span> 
- <span data-ttu-id="9d99e-3078">social security number
</span><span class="sxs-lookup"><span data-stu-id="9d99e-3078">social security number</span></span> 
- <span data-ttu-id="9d99e-3079">insurance application
</span><span class="sxs-lookup"><span data-stu-id="9d99e-3079">insurance application</span></span> 
- <span data-ttu-id="9d99e-3080">medical application
</span><span class="sxs-lookup"><span data-stu-id="9d99e-3080">medical application</span></span> 
- <span data-ttu-id="9d99e-3081">social insurance
</span><span class="sxs-lookup"><span data-stu-id="9d99e-3081">social insurance</span></span> 
- <span data-ttu-id="9d99e-3082">medical attention
</span><span class="sxs-lookup"><span data-stu-id="9d99e-3082">medical attention</span></span> 
- <span data-ttu-id="9d99e-3083">protezione di social networking</span><span class="sxs-lookup"><span data-stu-id="9d99e-3083">social security</span></span> 
- <span data-ttu-id="9d99e-3084">great britain
</span><span class="sxs-lookup"><span data-stu-id="9d99e-3084">great britain</span></span> 
- <span data-ttu-id="9d99e-3085">insurance
</span><span class="sxs-lookup"><span data-stu-id="9d99e-3085">insurance</span></span>    
   
## <a name="us--uk-passport-number"></a><span data-ttu-id="9d99e-p145">Stati Uniti/Regno Unito - Numero di passaporto</span><span class="sxs-lookup"><span data-stu-id="9d99e-p145">U.S. / U.K. Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="9d99e-3088">Formato</span><span class="sxs-lookup"><span data-stu-id="9d99e-3088">Format</span></span>

<span data-ttu-id="9d99e-3089">9 cifre</span><span class="sxs-lookup"><span data-stu-id="9d99e-3089">Nine digits</span></span>

### <a name="pattern"></a><span data-ttu-id="9d99e-3090">Modello</span><span class="sxs-lookup"><span data-stu-id="9d99e-3090">Pattern</span></span>

<span data-ttu-id="9d99e-3091">9 cifre consecutive</span><span class="sxs-lookup"><span data-stu-id="9d99e-3091">Nine consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="9d99e-3092">Checksum</span><span class="sxs-lookup"><span data-stu-id="9d99e-3092">Checksum</span></span>

<span data-ttu-id="9d99e-3093">No</span><span class="sxs-lookup"><span data-stu-id="9d99e-3093">No</span></span>

### <a name="definition"></a><span data-ttu-id="9d99e-3094">Definizione</span><span class="sxs-lookup"><span data-stu-id="9d99e-3094">Definition</span></span>

<span data-ttu-id="9d99e-3095">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="9d99e-3095">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="9d99e-3096">La funzione Func_usa_uk_passport restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="9d99e-3096">The function Func_usa_uk_passport finds content that matches the pattern.</span></span>
- <span data-ttu-id="9d99e-3097">Viene trovata una parola chiave da Keyword_passport.</span><span class="sxs-lookup"><span data-stu-id="9d99e-3097">A keyword from Keyword_passport is found.</span></span>

```
<Entity id="178ec42a-18b4-47cc-85c7-d62c92fd67f8" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_usa_uk_passport" />
        <Match idRef="Keyword_passport" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="9d99e-3098">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="9d99e-3098">Keywords</span></span>

#### <a name="keywordpassport"></a><span data-ttu-id="9d99e-3099">Keyword_passport</span><span class="sxs-lookup"><span data-stu-id="9d99e-3099">Keyword_passport</span></span>

- <span data-ttu-id="9d99e-3100">Passport Number</span><span class="sxs-lookup"><span data-stu-id="9d99e-3100">Passport Number</span></span> 
- <span data-ttu-id="9d99e-3101">
Passport No</span><span class="sxs-lookup"><span data-stu-id="9d99e-3101">Passport No</span></span> 
- <span data-ttu-id="9d99e-3102">Passport#
</span><span class="sxs-lookup"><span data-stu-id="9d99e-3102">Passport #</span></span> 
- <span data-ttu-id="9d99e-3103">Passport#
</span><span class="sxs-lookup"><span data-stu-id="9d99e-3103">Passport#</span></span> 
- <span data-ttu-id="9d99e-3104">PassportID</span><span class="sxs-lookup"><span data-stu-id="9d99e-3104">PassportID</span></span> 
- <span data-ttu-id="9d99e-3105">Passportno
</span><span class="sxs-lookup"><span data-stu-id="9d99e-3105">Passportno</span></span> 
- <span data-ttu-id="9d99e-3106">passportnumber
</span><span class="sxs-lookup"><span data-stu-id="9d99e-3106">passportnumber</span></span> 
- <span data-ttu-id="9d99e-3107">パスポート</span><span class="sxs-lookup"><span data-stu-id="9d99e-3107">パスポート</span></span> 
- <span data-ttu-id="9d99e-3108">パスポート番号
</span><span class="sxs-lookup"><span data-stu-id="9d99e-3108">パスポート番号</span></span> 
- <span data-ttu-id="9d99e-3109">パスポートのNum
</span><span class="sxs-lookup"><span data-stu-id="9d99e-3109">パスポートのNum</span></span> 
- <span data-ttu-id="9d99e-3110">パスポート＃
</span><span class="sxs-lookup"><span data-stu-id="9d99e-3110">パスポート＃</span></span> 
- <span data-ttu-id="9d99e-3111">Numéro de passeport</span><span class="sxs-lookup"><span data-stu-id="9d99e-3111">Numéro de passeport</span></span> 
- <span data-ttu-id="9d99e-3112">
Passeport n °</span><span class="sxs-lookup"><span data-stu-id="9d99e-3112">Passeport n °</span></span> 
- <span data-ttu-id="9d99e-3113">Passeport Non
</span><span class="sxs-lookup"><span data-stu-id="9d99e-3113">Passeport Non</span></span> 
- <span data-ttu-id="9d99e-3114">Passeport#
</span><span class="sxs-lookup"><span data-stu-id="9d99e-3114">Passeport #</span></span> 
- <span data-ttu-id="9d99e-3115">Passeport#
</span><span class="sxs-lookup"><span data-stu-id="9d99e-3115">Passeport#</span></span> 
- <span data-ttu-id="9d99e-3116">PasseportNon</span><span class="sxs-lookup"><span data-stu-id="9d99e-3116">PasseportNon</span></span> 
- <span data-ttu-id="9d99e-3117">Passeportn °
</span><span class="sxs-lookup"><span data-stu-id="9d99e-3117">Passeportn °</span></span> 
   
## <a name="us-bank-account-number"></a><span data-ttu-id="9d99e-3118">Stati Uniti - Numero di conto bancario</span><span class="sxs-lookup"><span data-stu-id="9d99e-3118">U.S. Bank Account Number</span></span>

### <a name="format"></a><span data-ttu-id="9d99e-3119">Formato</span><span class="sxs-lookup"><span data-stu-id="9d99e-3119">Format</span></span>

<span data-ttu-id="9d99e-3120">8-17 cifre</span><span class="sxs-lookup"><span data-stu-id="9d99e-3120">8-17 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="9d99e-3121">Modello</span><span class="sxs-lookup"><span data-stu-id="9d99e-3121">Pattern</span></span>

<span data-ttu-id="9d99e-3122">8-17 cifre consecutive</span><span class="sxs-lookup"><span data-stu-id="9d99e-3122">8-17 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="9d99e-3123">Checksum</span><span class="sxs-lookup"><span data-stu-id="9d99e-3123">Checksum</span></span>

<span data-ttu-id="9d99e-3124">No</span><span class="sxs-lookup"><span data-stu-id="9d99e-3124">No</span></span>

### <a name="definition"></a><span data-ttu-id="9d99e-3125">Definizione</span><span class="sxs-lookup"><span data-stu-id="9d99e-3125">Definition</span></span>

<span data-ttu-id="9d99e-3126">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="9d99e-3126">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="9d99e-3127">L'espressione regolare Regex_usa_bank_account_number restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="9d99e-3127">The regular expression Regex_usa_bank_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="9d99e-3128">Viene trovata una parola chiave da Keyword_usa_Bank_Account.</span><span class="sxs-lookup"><span data-stu-id="9d99e-3128">A keyword from Keyword_usa_Bank_Account is found.</span></span>

```
<!-- U.S. Bank Account Number -->
<Entity id="a2ce32a8-f935-4bb6-8e96-2a5157672e2c" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_usa_bank_account_number" />
        <Match idRef="Keyword_usa_Bank_Account" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="9d99e-3129">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="9d99e-3129">Keywords</span></span>

#### <a name="keywordusabankaccount"></a><span data-ttu-id="9d99e-3130">Keyword_usa_Bank_Account</span><span class="sxs-lookup"><span data-stu-id="9d99e-3130">Keyword_usa_Bank_Account</span></span>

- <span data-ttu-id="9d99e-3131">Checking Account Number
</span><span class="sxs-lookup"><span data-stu-id="9d99e-3131">Checking Account Number</span></span> 
- <span data-ttu-id="9d99e-3132">Checking Account
</span><span class="sxs-lookup"><span data-stu-id="9d99e-3132">Checking Account</span></span> 
- <span data-ttu-id="9d99e-3133">Checking Account #
</span><span class="sxs-lookup"><span data-stu-id="9d99e-3133">Checking Account #</span></span> 
- <span data-ttu-id="9d99e-3134">Checking Acct Number
</span><span class="sxs-lookup"><span data-stu-id="9d99e-3134">Checking Acct Number</span></span> 
- <span data-ttu-id="9d99e-3135">Checking Acct #
</span><span class="sxs-lookup"><span data-stu-id="9d99e-3135">Checking Acct #</span></span> 
- <span data-ttu-id="9d99e-3136">Checking Acct No.
</span><span class="sxs-lookup"><span data-stu-id="9d99e-3136">Checking Acct No.</span></span> 
- <span data-ttu-id="9d99e-3137">Checking Account No.
</span><span class="sxs-lookup"><span data-stu-id="9d99e-3137">Checking Account No.</span></span> 
- <span data-ttu-id="9d99e-3138">Bank Account Number
</span><span class="sxs-lookup"><span data-stu-id="9d99e-3138">Bank Account Number</span></span> 
- <span data-ttu-id="9d99e-3139">Bank Account #
</span><span class="sxs-lookup"><span data-stu-id="9d99e-3139">Bank Account #</span></span> 
- <span data-ttu-id="9d99e-3140">Bank Acct Number
</span><span class="sxs-lookup"><span data-stu-id="9d99e-3140">Bank Acct Number</span></span> 
- <span data-ttu-id="9d99e-3141">Bank Acct #
</span><span class="sxs-lookup"><span data-stu-id="9d99e-3141">Bank Acct #</span></span> 
- <span data-ttu-id="9d99e-3142">Bank Acct No.
</span><span class="sxs-lookup"><span data-stu-id="9d99e-3142">Bank Acct No.</span></span> 
- <span data-ttu-id="9d99e-3143">Bank Account No.
</span><span class="sxs-lookup"><span data-stu-id="9d99e-3143">Bank Account No.</span></span> 
- <span data-ttu-id="9d99e-3144">Savings Account Number
</span><span class="sxs-lookup"><span data-stu-id="9d99e-3144">Savings Account Number</span></span> 
- <span data-ttu-id="9d99e-3145">Savings Account.
</span><span class="sxs-lookup"><span data-stu-id="9d99e-3145">Savings Account.</span></span> 
- <span data-ttu-id="9d99e-3146">Savings Account #
</span><span class="sxs-lookup"><span data-stu-id="9d99e-3146">Savings Account #</span></span> 
- <span data-ttu-id="9d99e-3147">Savings Acct Number
</span><span class="sxs-lookup"><span data-stu-id="9d99e-3147">Savings Acct Number</span></span> 
- <span data-ttu-id="9d99e-3148">Savings Acct #
</span><span class="sxs-lookup"><span data-stu-id="9d99e-3148">Savings Acct #</span></span> 
- <span data-ttu-id="9d99e-3149">Savings Acct No.
</span><span class="sxs-lookup"><span data-stu-id="9d99e-3149">Savings Acct No.</span></span> 
- <span data-ttu-id="9d99e-3150">Savings Account No.
</span><span class="sxs-lookup"><span data-stu-id="9d99e-3150">Savings Account No.</span></span> 
- <span data-ttu-id="9d99e-3151">Debit Account Number
</span><span class="sxs-lookup"><span data-stu-id="9d99e-3151">Debit Account Number</span></span> 
- <span data-ttu-id="9d99e-3152">Debit Account
</span><span class="sxs-lookup"><span data-stu-id="9d99e-3152">Debit Account</span></span> 
- <span data-ttu-id="9d99e-3153">Debit Account #
</span><span class="sxs-lookup"><span data-stu-id="9d99e-3153">Debit Account #</span></span> 
- <span data-ttu-id="9d99e-3154">Debit Acct Number
</span><span class="sxs-lookup"><span data-stu-id="9d99e-3154">Debit Acct Number</span></span> 
- <span data-ttu-id="9d99e-3155">Debit Acct #
</span><span class="sxs-lookup"><span data-stu-id="9d99e-3155">Debit Acct #</span></span> 
- <span data-ttu-id="9d99e-3156">Debit Acct No.
</span><span class="sxs-lookup"><span data-stu-id="9d99e-3156">Debit Acct No.</span></span> 
- <span data-ttu-id="9d99e-3157">Debit Account No.
</span><span class="sxs-lookup"><span data-stu-id="9d99e-3157">Debit Account No.</span></span> 
   
## <a name="us-drivers-license-number"></a><span data-ttu-id="9d99e-3158">Stati Uniti - Numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="9d99e-3158">U.S. Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="9d99e-3159">Formato</span><span class="sxs-lookup"><span data-stu-id="9d99e-3159">Format</span></span>

<span data-ttu-id="9d99e-3160">Varia in base allo stato</span><span class="sxs-lookup"><span data-stu-id="9d99e-3160">Depends on the state</span></span>

### <a name="pattern"></a><span data-ttu-id="9d99e-3161">Modello</span><span class="sxs-lookup"><span data-stu-id="9d99e-3161">Pattern</span></span>

<span data-ttu-id="9d99e-3162">Varia in base allo stato. Ad esempio, per New York:</span><span class="sxs-lookup"><span data-stu-id="9d99e-3162">Depends on the state -- for example, New York:</span></span>
- <span data-ttu-id="9d99e-3163">Nove cifre formattato come ggg ggg ggg corrispondenti.</span><span class="sxs-lookup"><span data-stu-id="9d99e-3163">Nine digits formatted like ddd ddd ddd will match.</span></span>
- <span data-ttu-id="9d99e-3164">Nove cifre come ddddddddd non corrispondono.</span><span class="sxs-lookup"><span data-stu-id="9d99e-3164">Nine digits like ddddddddd will not match.</span></span>

### <a name="checksum"></a><span data-ttu-id="9d99e-3165">Checksum</span><span class="sxs-lookup"><span data-stu-id="9d99e-3165">Checksum</span></span>

<span data-ttu-id="9d99e-3166">No</span><span class="sxs-lookup"><span data-stu-id="9d99e-3166">No</span></span>

### <a name="definition"></a><span data-ttu-id="9d99e-3167">Definizione</span><span class="sxs-lookup"><span data-stu-id="9d99e-3167">Definition</span></span>

<span data-ttu-id="9d99e-3168">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="9d99e-3168">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="9d99e-3169">La funzione Func_new_york_drivers_license_number restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="9d99e-3169">The function Func_new_york_drivers_license_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="9d99e-3170">Viene trovata una parola chiave da Keyword_[state_name]_drivers_license_name.</span><span class="sxs-lookup"><span data-stu-id="9d99e-3170">A keyword from Keyword_[state_name]_drivers_license_name is found.</span></span>
- <span data-ttu-id="9d99e-3171">È possibile trovare una parola chiave da Keyword_us_drivers_license.</span><span class="sxs-lookup"><span data-stu-id="9d99e-3171">A keyword from Keyword_us_drivers_license is found.</span></span>

<span data-ttu-id="9d99e-3172">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 65%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="9d99e-3172">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="9d99e-3173">La funzione Func_new_york_drivers_license_number restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="9d99e-3173">The function Func_new_york_drivers_license_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="9d99e-3174">Viene trovata una parola chiave da Keyword_[state_name]_drivers_license_name.</span><span class="sxs-lookup"><span data-stu-id="9d99e-3174">A keyword from Keyword_[state_name]_drivers_license_name is found.</span></span>
- <span data-ttu-id="9d99e-3175">Viene trovata una parola chiave da Keyword_us_drivers_license_abbreviations.</span><span class="sxs-lookup"><span data-stu-id="9d99e-3175">A keyword from Keyword_us_drivers_license_abbreviations is found.</span></span>
- <span data-ttu-id="9d99e-3176">Non vengono trovate parole chiave da Keyword_us_drivers_license.</span><span class="sxs-lookup"><span data-stu-id="9d99e-3176">No keyword from Keyword_us_drivers_license is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="9d99e-3177">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="9d99e-3177">Keywords</span></span>

#### <a name="keywordusdriverslicenseabbreviations"></a><span data-ttu-id="9d99e-3178">Keyword_us_drivers_license_abbreviations</span><span class="sxs-lookup"><span data-stu-id="9d99e-3178">Keyword_us_drivers_license_abbreviations</span></span>

- <span data-ttu-id="9d99e-3179">DL</span><span class="sxs-lookup"><span data-stu-id="9d99e-3179">DL</span></span> 
- <span data-ttu-id="9d99e-3180">DLS</span><span class="sxs-lookup"><span data-stu-id="9d99e-3180">DLS</span></span> 
- <span data-ttu-id="9d99e-3181">CDL</span><span class="sxs-lookup"><span data-stu-id="9d99e-3181">CDL</span></span> 
- <span data-ttu-id="9d99e-3182">CDLS</span><span class="sxs-lookup"><span data-stu-id="9d99e-3182">CDLS</span></span> 
- <span data-ttu-id="9d99e-3183">ID</span><span class="sxs-lookup"><span data-stu-id="9d99e-3183">ID</span></span> 
- <span data-ttu-id="9d99e-3184">ID</span><span class="sxs-lookup"><span data-stu-id="9d99e-3184">IDs</span></span> 
- <span data-ttu-id="9d99e-3185">DL#</span><span class="sxs-lookup"><span data-stu-id="9d99e-3185">DL#</span></span> 
- <span data-ttu-id="9d99e-3186">
DLS#
</span><span class="sxs-lookup"><span data-stu-id="9d99e-3186">DLS#</span></span> 
- <span data-ttu-id="9d99e-3187">CDL#
</span><span class="sxs-lookup"><span data-stu-id="9d99e-3187">CDL#</span></span> 
- <span data-ttu-id="9d99e-3188">CDLS#
</span><span class="sxs-lookup"><span data-stu-id="9d99e-3188">CDLS#</span></span> 
- <span data-ttu-id="9d99e-3189">ID#</span><span class="sxs-lookup"><span data-stu-id="9d99e-3189">ID#</span></span>
- <span data-ttu-id="9d99e-3190">
IDs#
</span><span class="sxs-lookup"><span data-stu-id="9d99e-3190">IDs#</span></span> 
- <span data-ttu-id="9d99e-3191">numero ID</span><span class="sxs-lookup"><span data-stu-id="9d99e-3191">ID number</span></span> 
- <span data-ttu-id="9d99e-3192">ID numbers
</span><span class="sxs-lookup"><span data-stu-id="9d99e-3192">ID numbers</span></span> 
- <span data-ttu-id="9d99e-3193">LIC</span><span class="sxs-lookup"><span data-stu-id="9d99e-3193">LIC</span></span> 
- <span data-ttu-id="9d99e-3194">LIC#
</span><span class="sxs-lookup"><span data-stu-id="9d99e-3194">LIC#</span></span> 

#### <a name="keywordusdriverslicense"></a><span data-ttu-id="9d99e-3195">Keyword_us_drivers_license</span><span class="sxs-lookup"><span data-stu-id="9d99e-3195">Keyword_us_drivers_license</span></span>

- <span data-ttu-id="9d99e-3196">DriverLic</span><span class="sxs-lookup"><span data-stu-id="9d99e-3196">DriverLic</span></span> 
- <span data-ttu-id="9d99e-3197">DriverLics</span><span class="sxs-lookup"><span data-stu-id="9d99e-3197">DriverLics</span></span> 
- <span data-ttu-id="9d99e-3198">DriverLicense</span><span class="sxs-lookup"><span data-stu-id="9d99e-3198">DriverLicense</span></span> 
- <span data-ttu-id="9d99e-3199">DriverLicenses</span><span class="sxs-lookup"><span data-stu-id="9d99e-3199">DriverLicenses</span></span> 
- <span data-ttu-id="9d99e-3200">Driver Lic</span><span class="sxs-lookup"><span data-stu-id="9d99e-3200">Driver Lic</span></span> 
- <span data-ttu-id="9d99e-3201">Driver conglomerati</span><span class="sxs-lookup"><span data-stu-id="9d99e-3201">Driver Lics</span></span> 
- <span data-ttu-id="9d99e-3202">Patente</span><span class="sxs-lookup"><span data-stu-id="9d99e-3202">Driver License</span></span> 
- <span data-ttu-id="9d99e-3203">Driver licenze</span><span class="sxs-lookup"><span data-stu-id="9d99e-3203">Driver Licenses</span></span> 
- <span data-ttu-id="9d99e-3204">DriversLic</span><span class="sxs-lookup"><span data-stu-id="9d99e-3204">DriversLic</span></span> 
- <span data-ttu-id="9d99e-3205">DriversLics</span><span class="sxs-lookup"><span data-stu-id="9d99e-3205">DriversLics</span></span> 
- <span data-ttu-id="9d99e-3206">PatenteGuida</span><span class="sxs-lookup"><span data-stu-id="9d99e-3206">DriversLicense</span></span> 
- <span data-ttu-id="9d99e-3207">DriversLicenses</span><span class="sxs-lookup"><span data-stu-id="9d99e-3207">DriversLicenses</span></span> 
- <span data-ttu-id="9d99e-3208">Driver Lic</span><span class="sxs-lookup"><span data-stu-id="9d99e-3208">Drivers Lic</span></span> 
- <span data-ttu-id="9d99e-3209">Driver conglomerati</span><span class="sxs-lookup"><span data-stu-id="9d99e-3209">Drivers Lics</span></span> 
- <span data-ttu-id="9d99e-3210">Patente di Guida</span><span class="sxs-lookup"><span data-stu-id="9d99e-3210">Drivers License</span></span> 
- <span data-ttu-id="9d99e-3211">Driver licenze</span><span class="sxs-lookup"><span data-stu-id="9d99e-3211">Drivers Licenses</span></span> 
- <span data-ttu-id="9d99e-3212">Driver'Lic</span><span class="sxs-lookup"><span data-stu-id="9d99e-3212">Driver'Lic</span></span> 
- <span data-ttu-id="9d99e-3213">Driver'Lics</span><span class="sxs-lookup"><span data-stu-id="9d99e-3213">Driver'Lics</span></span> 
- <span data-ttu-id="9d99e-3214">Driver'License</span><span class="sxs-lookup"><span data-stu-id="9d99e-3214">Driver'License</span></span> 
- <span data-ttu-id="9d99e-3215">Driver'Licenses</span><span class="sxs-lookup"><span data-stu-id="9d99e-3215">Driver'Licenses</span></span> 
- <span data-ttu-id="9d99e-3216">Driver' Lic</span><span class="sxs-lookup"><span data-stu-id="9d99e-3216">Driver' Lic</span></span> 
- <span data-ttu-id="9d99e-3217">Driver' conglomerati</span><span class="sxs-lookup"><span data-stu-id="9d99e-3217">Driver' Lics</span></span> 
- <span data-ttu-id="9d99e-3218">Driver' licenza</span><span class="sxs-lookup"><span data-stu-id="9d99e-3218">Driver' License</span></span> 
- <span data-ttu-id="9d99e-3219">Driver' licenze</span><span class="sxs-lookup"><span data-stu-id="9d99e-3219">Driver' Licenses</span></span>
- <span data-ttu-id="9d99e-3220">Driver'sLic</span><span class="sxs-lookup"><span data-stu-id="9d99e-3220">Driver'sLic</span></span> 
- <span data-ttu-id="9d99e-3221">Driver'sLics</span><span class="sxs-lookup"><span data-stu-id="9d99e-3221">Driver'sLics</span></span> 
- <span data-ttu-id="9d99e-3222">Driver'sLicense</span><span class="sxs-lookup"><span data-stu-id="9d99e-3222">Driver'sLicense</span></span> 
- <span data-ttu-id="9d99e-3223">Driver'sLicenses</span><span class="sxs-lookup"><span data-stu-id="9d99e-3223">Driver'sLicenses</span></span> 
- <span data-ttu-id="9d99e-3224">Lic della patente di Guida</span><span class="sxs-lookup"><span data-stu-id="9d99e-3224">Driver's Lic</span></span> 
- <span data-ttu-id="9d99e-3225">Conglomerati della patente di Guida</span><span class="sxs-lookup"><span data-stu-id="9d99e-3225">Driver's Lics</span></span> 
- <span data-ttu-id="9d99e-3226">Patente</span><span class="sxs-lookup"><span data-stu-id="9d99e-3226">Driver's License</span></span> 
- <span data-ttu-id="9d99e-3227">Licenze della patente di Guida</span><span class="sxs-lookup"><span data-stu-id="9d99e-3227">Driver's Licenses</span></span> 
- <span data-ttu-id="9d99e-3228">identification number
</span><span class="sxs-lookup"><span data-stu-id="9d99e-3228">identification number</span></span> 
- <span data-ttu-id="9d99e-3229">identification numbers
</span><span class="sxs-lookup"><span data-stu-id="9d99e-3229">identification numbers</span></span> 
- <span data-ttu-id="9d99e-3230">identification#
</span><span class="sxs-lookup"><span data-stu-id="9d99e-3230">identification #</span></span> 
- <span data-ttu-id="9d99e-3231">carta d'identità</span><span class="sxs-lookup"><span data-stu-id="9d99e-3231">id card</span></span> 
- <span data-ttu-id="9d99e-3232">schede ID</span><span class="sxs-lookup"><span data-stu-id="9d99e-3232">id cards</span></span> 
- <span data-ttu-id="9d99e-3233">scheda di identificazione</span><span class="sxs-lookup"><span data-stu-id="9d99e-3233">identification card</span></span> 
- <span data-ttu-id="9d99e-3234">identificazione schede</span><span class="sxs-lookup"><span data-stu-id="9d99e-3234">identification cards</span></span> 
- <span data-ttu-id="9d99e-3235">DriverLic #</span><span class="sxs-lookup"><span data-stu-id="9d99e-3235">DriverLic#</span></span> 
- <span data-ttu-id="9d99e-3236">DriverLics #</span><span class="sxs-lookup"><span data-stu-id="9d99e-3236">DriverLics#</span></span> 
- <span data-ttu-id="9d99e-3237">DriverLicense #</span><span class="sxs-lookup"><span data-stu-id="9d99e-3237">DriverLicense#</span></span> 
- <span data-ttu-id="9d99e-3238">DriverLicenses #</span><span class="sxs-lookup"><span data-stu-id="9d99e-3238">DriverLicenses#</span></span> 
- <span data-ttu-id="9d99e-3239">Driver Lic#</span><span class="sxs-lookup"><span data-stu-id="9d99e-3239">Driver Lic#</span></span> 
- <span data-ttu-id="9d99e-3240">
Driver Lics#
</span><span class="sxs-lookup"><span data-stu-id="9d99e-3240">Driver Lics#</span></span> 
- <span data-ttu-id="9d99e-3241">Driver licenza #</span><span class="sxs-lookup"><span data-stu-id="9d99e-3241">Driver License#</span></span> 
- <span data-ttu-id="9d99e-3242">Driver licenze #</span><span class="sxs-lookup"><span data-stu-id="9d99e-3242">Driver Licenses#</span></span> 
- <span data-ttu-id="9d99e-3243">DriversLic #</span><span class="sxs-lookup"><span data-stu-id="9d99e-3243">DriversLic#</span></span> 
- <span data-ttu-id="9d99e-3244">DriversLics #</span><span class="sxs-lookup"><span data-stu-id="9d99e-3244">DriversLics#</span></span> 
- <span data-ttu-id="9d99e-3245">PatenteGuida #</span><span class="sxs-lookup"><span data-stu-id="9d99e-3245">DriversLicense#</span></span> 
- <span data-ttu-id="9d99e-3246">DriversLicenses #</span><span class="sxs-lookup"><span data-stu-id="9d99e-3246">DriversLicenses#</span></span> 
- <span data-ttu-id="9d99e-3247">Driver Lic #</span><span class="sxs-lookup"><span data-stu-id="9d99e-3247">Drivers Lic#</span></span> 
- <span data-ttu-id="9d99e-3248">Driver conglomerati #</span><span class="sxs-lookup"><span data-stu-id="9d99e-3248">Drivers Lics#</span></span> 
- <span data-ttu-id="9d99e-3249">Driver della licenza #</span><span class="sxs-lookup"><span data-stu-id="9d99e-3249">Drivers License#</span></span> 
- <span data-ttu-id="9d99e-3250">Driver licenze #</span><span class="sxs-lookup"><span data-stu-id="9d99e-3250">Drivers Licenses#</span></span> 
- <span data-ttu-id="9d99e-3251">Driver' Lic#
</span><span class="sxs-lookup"><span data-stu-id="9d99e-3251">Driver'Lic#</span></span> 
- <span data-ttu-id="9d99e-3252">Driver' Lics#
</span><span class="sxs-lookup"><span data-stu-id="9d99e-3252">Driver'Lics#</span></span> 
- <span data-ttu-id="9d99e-3253">Driver' License#
</span><span class="sxs-lookup"><span data-stu-id="9d99e-3253">Driver'License#</span></span> 
- <span data-ttu-id="9d99e-3254">Driver' Licenses#
</span><span class="sxs-lookup"><span data-stu-id="9d99e-3254">Driver'Licenses#</span></span> 
- <span data-ttu-id="9d99e-3255">Driver' Lic#
</span><span class="sxs-lookup"><span data-stu-id="9d99e-3255">Driver' Lic#</span></span> 
- <span data-ttu-id="9d99e-3256">Driver' Lics#
</span><span class="sxs-lookup"><span data-stu-id="9d99e-3256">Driver' Lics#</span></span> 
- <span data-ttu-id="9d99e-3257">Driver' License#
</span><span class="sxs-lookup"><span data-stu-id="9d99e-3257">Driver' License#</span></span> 
- <span data-ttu-id="9d99e-3258">Driver' Licenses#
</span><span class="sxs-lookup"><span data-stu-id="9d99e-3258">Driver' Licenses#</span></span> 
- <span data-ttu-id="9d99e-3259">Driver'sLic #</span><span class="sxs-lookup"><span data-stu-id="9d99e-3259">Driver'sLic#</span></span> 
- <span data-ttu-id="9d99e-3260">Driver'sLics #</span><span class="sxs-lookup"><span data-stu-id="9d99e-3260">Driver'sLics#</span></span> 
- <span data-ttu-id="9d99e-3261">Driver'sLicense #</span><span class="sxs-lookup"><span data-stu-id="9d99e-3261">Driver'sLicense#</span></span> 
- <span data-ttu-id="9d99e-3262">Driver'sLicenses #</span><span class="sxs-lookup"><span data-stu-id="9d99e-3262">Driver'sLicenses#</span></span> 
- <span data-ttu-id="9d99e-3263">Driver's Lic#
</span><span class="sxs-lookup"><span data-stu-id="9d99e-3263">Driver's Lic#</span></span> 
- <span data-ttu-id="9d99e-3264">Driver's Lics#
</span><span class="sxs-lookup"><span data-stu-id="9d99e-3264">Driver's Lics#</span></span> 
- <span data-ttu-id="9d99e-3265">Driver's License#
</span><span class="sxs-lookup"><span data-stu-id="9d99e-3265">Driver's License#</span></span> 
- <span data-ttu-id="9d99e-3266">Driver's Licenses#
</span><span class="sxs-lookup"><span data-stu-id="9d99e-3266">Driver's Licenses#</span></span> 
- <span data-ttu-id="9d99e-3267">carta d'identità #</span><span class="sxs-lookup"><span data-stu-id="9d99e-3267">id card#</span></span> 
- <span data-ttu-id="9d99e-3268">id cards#
</span><span class="sxs-lookup"><span data-stu-id="9d99e-3268">id cards#</span></span> 
- <span data-ttu-id="9d99e-3269">identification card#
</span><span class="sxs-lookup"><span data-stu-id="9d99e-3269">identification card#</span></span> 
- <span data-ttu-id="9d99e-3270">identification cards#
</span><span class="sxs-lookup"><span data-stu-id="9d99e-3270">identification cards#</span></span> 


#### <a name="keywordstatenamedriverslicensename"></a><span data-ttu-id="9d99e-3271">Keyword_[state_name]_drivers_license_name</span><span class="sxs-lookup"><span data-stu-id="9d99e-3271">Keyword_[state_name]_drivers_license_name</span></span>

- <span data-ttu-id="9d99e-3272">Abbreviazione dello stato (ad esempio, "NY")
</span><span class="sxs-lookup"><span data-stu-id="9d99e-3272">State abbreviation (for example, "NY")</span></span> 
- <span data-ttu-id="9d99e-3273">Nome dello stato (ad esempio, "New York")
</span><span class="sxs-lookup"><span data-stu-id="9d99e-3273">State name (for example, "New York")</span></span>    
   
## <a name="us-individual-taxpayer-identification-number-itin"></a><span data-ttu-id="9d99e-3274">Stati Uniti - Codice identificativo del contribuente individuale (ITIN)</span><span class="sxs-lookup"><span data-stu-id="9d99e-3274">U.S. Individual Taxpayer Identification Number (ITIN)</span></span>

### <a name="format"></a><span data-ttu-id="9d99e-3275">Formato</span><span class="sxs-lookup"><span data-stu-id="9d99e-3275">Format</span></span>

<span data-ttu-id="9d99e-3276">Nove cifre che iniziano con "9" e contengono un "7" o un "8" come quarta cifra. Può essere formattato con spazi e trattini (facoltativo)</span><span class="sxs-lookup"><span data-stu-id="9d99e-3276">Nine digits that start with a "9" and contain a "7" or "8" as the fourth digit, optionally formatted with spaces or dashes</span></span>

### <a name="pattern"></a><span data-ttu-id="9d99e-3277">Modello</span><span class="sxs-lookup"><span data-stu-id="9d99e-3277">Pattern</span></span>

<span data-ttu-id="9d99e-3278">Formattato:</span><span class="sxs-lookup"><span data-stu-id="9d99e-3278">Formatted:</span></span>
- <span data-ttu-id="9d99e-3279">La cifra "9"</span><span class="sxs-lookup"><span data-stu-id="9d99e-3279">The digit "9"</span></span> 
- <span data-ttu-id="9d99e-3280">Due cifre</span><span class="sxs-lookup"><span data-stu-id="9d99e-3280">Two digits</span></span> 
- <span data-ttu-id="9d99e-3281">Uno spazio o un trattino</span><span class="sxs-lookup"><span data-stu-id="9d99e-3281">A space or dash</span></span> 
- <span data-ttu-id="9d99e-3282">Un "7" o un "8"</span><span class="sxs-lookup"><span data-stu-id="9d99e-3282">A "7" or "8"</span></span> 
- <span data-ttu-id="9d99e-3283">Una cifra</span><span class="sxs-lookup"><span data-stu-id="9d99e-3283">A digit</span></span> 
- <span data-ttu-id="9d99e-3284">Uno spazio o un trattino</span><span class="sxs-lookup"><span data-stu-id="9d99e-3284">A space, or dash</span></span> 
- <span data-ttu-id="9d99e-3285">Quattro cifre</span><span class="sxs-lookup"><span data-stu-id="9d99e-3285">Four digits</span></span>

<span data-ttu-id="9d99e-3286">Non formattato:</span><span class="sxs-lookup"><span data-stu-id="9d99e-3286">Unformatted:</span></span>
- <span data-ttu-id="9d99e-3287">La cifra "9"</span><span class="sxs-lookup"><span data-stu-id="9d99e-3287">The digit "9"</span></span> 
- <span data-ttu-id="9d99e-3288">Due cifre</span><span class="sxs-lookup"><span data-stu-id="9d99e-3288">Two digits</span></span> 
- <span data-ttu-id="9d99e-3289">Un "7" o un "8"</span><span class="sxs-lookup"><span data-stu-id="9d99e-3289">A "7" or "8"</span></span> 
- <span data-ttu-id="9d99e-3290">Cinque cifre</span><span class="sxs-lookup"><span data-stu-id="9d99e-3290">Five digits</span></span>

### <a name="checksum"></a><span data-ttu-id="9d99e-3291">Checksum</span><span class="sxs-lookup"><span data-stu-id="9d99e-3291">Checksum</span></span>

<span data-ttu-id="9d99e-3292">No</span><span class="sxs-lookup"><span data-stu-id="9d99e-3292">No</span></span>

### <a name="definition"></a><span data-ttu-id="9d99e-3293">Definizione</span><span class="sxs-lookup"><span data-stu-id="9d99e-3293">Definition</span></span>

<span data-ttu-id="9d99e-3294">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="9d99e-3294">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="9d99e-3295">La funzione Func_formatted_itin restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="9d99e-3295">The function Func_formatted_itin finds content that matches the pattern.</span></span>
- <span data-ttu-id="9d99e-3296">Si verifica almeno una delle situazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="9d99e-3296">At least one of the following is true:</span></span>
    - <span data-ttu-id="9d99e-3297">Viene trovata una parola chiave da Keyword_itin.</span><span class="sxs-lookup"><span data-stu-id="9d99e-3297">A keyword from Keyword_itin is found.</span></span>
    - <span data-ttu-id="9d99e-3298">La funzione Func_us_address rileva un indirizzo nel formato di data corretto.</span><span class="sxs-lookup"><span data-stu-id="9d99e-3298">The function Func_us_address finds an address in the right date format.</span></span>
    - <span data-ttu-id="9d99e-3299">La funzione Func_us_date rileva una data nel formato corretto.</span><span class="sxs-lookup"><span data-stu-id="9d99e-3299">The function Func_us_date finds a date in the right date format.</span></span>
    - <span data-ttu-id="9d99e-3300">Viene trovata una parola chiave da Keyword_itin_collaborative.</span><span class="sxs-lookup"><span data-stu-id="9d99e-3300">A keyword from Keyword_itin_collaborative is found.</span></span>

<span data-ttu-id="9d99e-3301">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="9d99e-3301">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="9d99e-3302">La funzione Func_unformatted_itin restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="9d99e-3302">The function Func_unformatted_itin finds content that matches the pattern.</span></span>
- <span data-ttu-id="9d99e-3303">Si verifica almeno una delle situazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="9d99e-3303">At least one of the following is true:</span></span>
    - <span data-ttu-id="9d99e-3304">Viene trovata una parola chiave da Keyword_itin_collaborative.</span><span class="sxs-lookup"><span data-stu-id="9d99e-3304">A keyword from Keyword_itin_collaborative is found.</span></span>
    - <span data-ttu-id="9d99e-3305">La funzione Func_us_address rileva un indirizzo nel formato di data corretto.</span><span class="sxs-lookup"><span data-stu-id="9d99e-3305">The function Func_us_address finds an address in the right date format.</span></span>
    - <span data-ttu-id="9d99e-3306">La funzione Func_us_date rileva una data nel formato corretto.</span><span class="sxs-lookup"><span data-stu-id="9d99e-3306">The function Func_us_date finds a date in the right date format.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="9d99e-3307">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="9d99e-3307">Keywords</span></span>

#### <a name="keyworditin"></a><span data-ttu-id="9d99e-3308">Keyword_itin</span><span class="sxs-lookup"><span data-stu-id="9d99e-3308">Keyword_itin</span></span>

- <span data-ttu-id="9d99e-3309">taxpayer
</span><span class="sxs-lookup"><span data-stu-id="9d99e-3309">taxpayer</span></span> 
- <span data-ttu-id="9d99e-3310">tax id
</span><span class="sxs-lookup"><span data-stu-id="9d99e-3310">tax id</span></span> 
- <span data-ttu-id="9d99e-3311">tax identification
</span><span class="sxs-lookup"><span data-stu-id="9d99e-3311">tax identification</span></span> 
- <span data-ttu-id="9d99e-3312">itin
</span><span class="sxs-lookup"><span data-stu-id="9d99e-3312">itin</span></span> 
- <span data-ttu-id="9d99e-3313">SSN</span><span class="sxs-lookup"><span data-stu-id="9d99e-3313">ssn</span></span> 
- <span data-ttu-id="9d99e-3314">tin
</span><span class="sxs-lookup"><span data-stu-id="9d99e-3314">tin</span></span> 
- <span data-ttu-id="9d99e-3315">protezione di social networking</span><span class="sxs-lookup"><span data-stu-id="9d99e-3315">social security</span></span> 
- <span data-ttu-id="9d99e-3316">tax payer
</span><span class="sxs-lookup"><span data-stu-id="9d99e-3316">tax payer</span></span> 
- <span data-ttu-id="9d99e-3317">itins
</span><span class="sxs-lookup"><span data-stu-id="9d99e-3317">itins</span></span> 
- <span data-ttu-id="9d99e-3318">taxid

</span><span class="sxs-lookup"><span data-stu-id="9d99e-3318">taxid</span></span> 
- <span data-ttu-id="9d99e-3319">individual taxpayer
</span><span class="sxs-lookup"><span data-stu-id="9d99e-3319">individual taxpayer</span></span> 

#### <a name="keyworditincollaborative"></a><span data-ttu-id="9d99e-3320">Keyword_itin_collaborative</span><span class="sxs-lookup"><span data-stu-id="9d99e-3320">Keyword_itin_collaborative</span></span>

- <span data-ttu-id="9d99e-3321">License</span><span class="sxs-lookup"><span data-stu-id="9d99e-3321">License</span></span> 
- <span data-ttu-id="9d99e-3322">DL</span><span class="sxs-lookup"><span data-stu-id="9d99e-3322">DL</span></span> 
- <span data-ttu-id="9d99e-3323">DOB
</span><span class="sxs-lookup"><span data-stu-id="9d99e-3323">DOB</span></span> 
- <span data-ttu-id="9d99e-3324">Data di nascita</span><span class="sxs-lookup"><span data-stu-id="9d99e-3324">Birthdate</span></span> 
- <span data-ttu-id="9d99e-3325">Compleanno </span><span class="sxs-lookup"><span data-stu-id="9d99e-3325">Birthday</span></span> 
- <span data-ttu-id="9d99e-3326">Date of Birth
</span><span class="sxs-lookup"><span data-stu-id="9d99e-3326">Date of Birth</span></span> 
   
## <a name="us-social-security-number-ssn"></a><span data-ttu-id="9d99e-3327">Stati Uniti - Numero di previdenza sociale (SSN)</span><span class="sxs-lookup"><span data-stu-id="9d99e-3327">U.S. Social Security Number (SSN)</span></span>

### <a name="format"></a><span data-ttu-id="9d99e-3328">Formato</span><span class="sxs-lookup"><span data-stu-id="9d99e-3328">Format</span></span>

<span data-ttu-id="9d99e-3329">9 cifre formattate o meno</span><span class="sxs-lookup"><span data-stu-id="9d99e-3329">9 digits, which may be in a formatted or unformatted pattern</span></span>

> [!NOTE]
> <span data-ttu-id="9d99e-3330">Se eseguita prima funzione mid 2011, un SSN è sicuro formattazione cui devono essere compreso alcuni intervalli è valido in alcune parti del numero (ma non esiste alcun checksum).</span><span class="sxs-lookup"><span data-stu-id="9d99e-3330">If issued before mid-2011, an SSN has strong formatting where certain parts of the number must fall within certain ranges to be valid (but there's no checksum).</span></span>

### <a name="pattern"></a><span data-ttu-id="9d99e-3331">Modello</span><span class="sxs-lookup"><span data-stu-id="9d99e-3331">Pattern</span></span>

<span data-ttu-id="9d99e-3332">Quattro funzioni cercare SSNs in quattro formati diversi:</span><span class="sxs-lookup"><span data-stu-id="9d99e-3332">Four functions look for SSNs in four different patterns:</span></span>
- <span data-ttu-id="9d99e-3333">Func_ssn trova SSNs di pre-2011 sicuro formattazione formattati con trattini o spazi (ggg-gg-gggg OR ggg gg gggg)</span><span class="sxs-lookup"><span data-stu-id="9d99e-3333">Func_ssn finds SSNs with pre-2011 strong formatting that are formatted with dashes or spaces (ddd-dd-dddd OR ddd dd dddd)</span></span>
- <span data-ttu-id="9d99e-3334">Func_unformatted_ssn trova SSNs di pre-2011 sicuro la formattazione viene formattato come nove cifre consecutive (ddddddddd)</span><span class="sxs-lookup"><span data-stu-id="9d99e-3334">Func_unformatted_ssn finds SSNs with pre-2011 strong formatting that are unformatted as nine consecutive digits (ddddddddd)</span></span>
- <span data-ttu-id="9d99e-3335">Func_randomized_formatted_ssn trova SSNs post 2011 formattati con trattini o spazi (ggg-gg-gggg OR ggg gg gggg)</span><span class="sxs-lookup"><span data-stu-id="9d99e-3335">Func_randomized_formatted_ssn finds post-2011 SSNs that are formatted with dashes or spaces (ddd-dd-dddd OR ddd dd dddd)</span></span>
- <span data-ttu-id="9d99e-3336">Func_randomized_unformatted_ssn trova SSNs post 2011 che viene formattato come nove cifre consecutive (ddddddddd)</span><span class="sxs-lookup"><span data-stu-id="9d99e-3336">Func_randomized_unformatted_ssn finds post-2011 SSNs that are unformatted as nine consecutive digits (ddddddddd)</span></span>

### <a name="checksum"></a><span data-ttu-id="9d99e-3337">Checksum</span><span class="sxs-lookup"><span data-stu-id="9d99e-3337">Checksum</span></span>

<span data-ttu-id="9d99e-3338">No</span><span class="sxs-lookup"><span data-stu-id="9d99e-3338">No</span></span>


### <a name="definition"></a><span data-ttu-id="9d99e-3339">Definizione</span><span class="sxs-lookup"><span data-stu-id="9d99e-3339">Definition</span></span>

<span data-ttu-id="9d99e-3340">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="9d99e-3340">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="9d99e-3341">La funzione Func_ssn restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="9d99e-3341">The function Func_ssn finds content that matches the pattern.</span></span>
- <span data-ttu-id="9d99e-3342">Viene trovata una parola chiave da Keyword_ssn.</span><span class="sxs-lookup"><span data-stu-id="9d99e-3342">A keyword from Keyword_ssn is found.</span></span>

<span data-ttu-id="9d99e-3343">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="9d99e-3343">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="9d99e-3344">La funzione Func_unformatted_ssn consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="9d99e-3344">The function Func_unformatted_ssn finds content that matches the pattern.</span></span>
- <span data-ttu-id="9d99e-3345">Viene trovata una parola chiave da Keyword_ssn.</span><span class="sxs-lookup"><span data-stu-id="9d99e-3345">A keyword from Keyword_ssn is found.</span></span>

<span data-ttu-id="9d99e-3346">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 65%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="9d99e-3346">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="9d99e-3347">La funzione Func_randomized_formatted_ssn restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="9d99e-3347">The function Func_randomized_formatted_ssn finds content that matches the pattern.</span></span>
- <span data-ttu-id="9d99e-3348">Viene trovata una parola chiave da Keyword_ssn.</span><span class="sxs-lookup"><span data-stu-id="9d99e-3348">A keyword from Keyword_ssn is found.</span></span>
- <span data-ttu-id="9d99e-3349">La funzione Func_ssn non trovare contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="9d99e-3349">The function Func_ssn does not find content that matches the pattern.</span></span>

<span data-ttu-id="9d99e-3350">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 55%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="9d99e-3350">A DLP policy is 55% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="9d99e-3351">La funzione Func_randomized_unformatted_ssn restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="9d99e-3351">The function Func_randomized_unformatted_ssn finds content that matches the pattern.</span></span>
- <span data-ttu-id="9d99e-3352">Viene trovata una parola chiave da Keyword_ssn.</span><span class="sxs-lookup"><span data-stu-id="9d99e-3352">A keyword from Keyword_ssn is found.</span></span>
- <span data-ttu-id="9d99e-3353">La funzione Func_unformatted_ssn non trovare contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="9d99e-3353">The function Func_unformatted_ssn does not find content that matches the pattern.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="9d99e-3354">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="9d99e-3354">Keywords</span></span>

#### <a name="keywordssn"></a><span data-ttu-id="9d99e-3355">Keyword_ssn</span><span class="sxs-lookup"><span data-stu-id="9d99e-3355">Keyword_ssn</span></span>

- <span data-ttu-id="9d99e-3356">Social Security
</span><span class="sxs-lookup"><span data-stu-id="9d99e-3356">Social Security</span></span> 
- <span data-ttu-id="9d99e-3357">Social Security#
</span><span class="sxs-lookup"><span data-stu-id="9d99e-3357">Social Security#</span></span> 
- <span data-ttu-id="9d99e-3358">Soc Sec
</span><span class="sxs-lookup"><span data-stu-id="9d99e-3358">Soc Sec</span></span> 
- <span data-ttu-id="9d99e-3359">SSN</span><span class="sxs-lookup"><span data-stu-id="9d99e-3359">SSN</span></span> 
- <span data-ttu-id="9d99e-3360">SSNS
</span><span class="sxs-lookup"><span data-stu-id="9d99e-3360">SSNS</span></span> 
- <span data-ttu-id="9d99e-3361">SSN#
</span><span class="sxs-lookup"><span data-stu-id="9d99e-3361">SSN#</span></span> 
- <span data-ttu-id="9d99e-3362">SS#
</span><span class="sxs-lookup"><span data-stu-id="9d99e-3362">SS#</span></span> 
- <span data-ttu-id="9d99e-3363">SSID
</span><span class="sxs-lookup"><span data-stu-id="9d99e-3363">SSID</span></span> 
   

