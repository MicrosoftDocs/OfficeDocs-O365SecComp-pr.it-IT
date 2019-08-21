---
title: Tipi di informazioni riservate disponibili da cercare
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 05/20/2019
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
ms.openlocfilehash: d486510c35aaf147e6d63e28d1df36ef689e3975
ms.sourcegitcommit: a5a7e43822336ed18d8f5879167766686cf6b2a3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/20/2019
ms.locfileid: "36478255"
---
# <a name="what-the-sensitive-information-types-look-for"></a><span data-ttu-id="7e12d-104">Tipi di informazioni riservate disponibili da cercare</span><span class="sxs-lookup"><span data-stu-id="7e12d-104">What the sensitive information types look for</span></span>

<span data-ttu-id="7e12d-105">La prevenzione della perdita di dati (DLP) nel centro &amp; sicurezza e conformità di Office 365 include numerosi tipi di informazioni riservate pronte per l'uso nei criteri DLP.</span><span class="sxs-lookup"><span data-stu-id="7e12d-105">Data loss prevention (DLP) in the Office 365 Security &amp; Compliance Center includes many sensitive information types that are ready for you to use in your DLP policies.</span></span> <span data-ttu-id="7e12d-106">In questo argomento vengono elencati tutti questi tipi di informazioni riservate e illustrata la ricerca eseguita dal criterio DLP quando rileva ciascun tipo di informazioni.</span><span class="sxs-lookup"><span data-stu-id="7e12d-106">This topic lists all of these sensitive information types and shows what a DLP policy looks for when it detects each type.</span></span> <span data-ttu-id="7e12d-107">Una tipologia di informazioni riservate viene definita da un modello identificato da un'espressione regolare o da una funzione.</span><span class="sxs-lookup"><span data-stu-id="7e12d-107">A sensitive information type is defined by a pattern that can be identified by a regular expression or a function.</span></span> <span data-ttu-id="7e12d-108">Inoltre, è possibile utilizzare elementi probatori, ad esempio, parole chiave e checksum per identificare una tipologia di informazioni riservate.</span><span class="sxs-lookup"><span data-stu-id="7e12d-108">In addition, corroborative evidence such as keywords and checksums can be used to identify a sensitive information type.</span></span> <span data-ttu-id="7e12d-109">In questa procedura di valutazione vengono usati anche il livello di probabilità e la prossimità.</span><span class="sxs-lookup"><span data-stu-id="7e12d-109">Confidence level and proximity are also used in the evaluation process.</span></span>
  
## <a name="aba-routing-number"></a><span data-ttu-id="7e12d-110">Numero di registrazione ABA</span><span class="sxs-lookup"><span data-stu-id="7e12d-110">ABA Routing Number</span></span>

### <a name="format"></a><span data-ttu-id="7e12d-111">Formato</span><span class="sxs-lookup"><span data-stu-id="7e12d-111">Format</span></span>

<span data-ttu-id="7e12d-112">9 cifre formattate o meno</span><span class="sxs-lookup"><span data-stu-id="7e12d-112">9 digits which may be in a formatted or unformatted pattern</span></span>

### <a name="pattern"></a><span data-ttu-id="7e12d-113">Modello</span><span class="sxs-lookup"><span data-stu-id="7e12d-113">Pattern</span></span>

<span data-ttu-id="7e12d-114">Formattato</span><span class="sxs-lookup"><span data-stu-id="7e12d-114">Formatted:</span></span>
- <span data-ttu-id="7e12d-115">Quattro cifre che iniziano con 0, 1, 2, 3, 6, 7 o 8</span><span class="sxs-lookup"><span data-stu-id="7e12d-115">Four digits beginning with 0, 1, 2, 3, 6, 7, or 8</span></span>
- <span data-ttu-id="7e12d-116">Una lineetta</span><span class="sxs-lookup"><span data-stu-id="7e12d-116">A hyphen</span></span>
- <span data-ttu-id="7e12d-117">Quattro cifre</span><span class="sxs-lookup"><span data-stu-id="7e12d-117">Four digits</span></span>
- <span data-ttu-id="7e12d-118">Una lineetta</span><span class="sxs-lookup"><span data-stu-id="7e12d-118">A hyphen</span></span>
- <span data-ttu-id="7e12d-119">Una cifra</span><span class="sxs-lookup"><span data-stu-id="7e12d-119">A digit</span></span>

<span data-ttu-id="7e12d-120">Non formattato: 9 cifre consecutive che iniziano con 0, 1, 2, 3, 6, 7 o 8</span><span class="sxs-lookup"><span data-stu-id="7e12d-120">Unformatted: 9 consecutive digits beginning with 0, 1, 2, 3, 6, 7, or 8</span></span> 

### <a name="checksum"></a><span data-ttu-id="7e12d-121">Checksum</span><span class="sxs-lookup"><span data-stu-id="7e12d-121">Checksum</span></span>

<span data-ttu-id="7e12d-122">No</span><span class="sxs-lookup"><span data-stu-id="7e12d-122">No</span></span>

### <a name="definition"></a><span data-ttu-id="7e12d-123">Definizione</span><span class="sxs-lookup"><span data-stu-id="7e12d-123">Definition</span></span>

<span data-ttu-id="7e12d-124">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="7e12d-124">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="7e12d-125">La funzione Func_aba_routing restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="7e12d-125">The function Func_aba_routing finds content that matches the pattern.</span></span>
- <span data-ttu-id="7e12d-126">Viene trovata una parola chiave da Keyword_ABA_Routing.</span><span class="sxs-lookup"><span data-stu-id="7e12d-126">A keyword from Keyword_ABA_Routing is found.</span></span>

```xml
<!-- ABA Routing Number -->
<Entity id="cb353f78-2b72-4c3c-8827-92ebe4f69fdf" patternsProximity="300" recommendedConfidence="75">
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_aba_routing" />
        <Match idRef="Keyword_ABA_Routing" />
      </Pattern>
 </Entity>
```


### <a name="keywords"></a><span data-ttu-id="7e12d-127">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="7e12d-127">Keywords</span></span>

#### <a name="keyword_aba_routing"></a><span data-ttu-id="7e12d-128">Keyword_ABA_Routing</span><span class="sxs-lookup"><span data-stu-id="7e12d-128">Keyword_ABA_Routing</span></span>

- <span data-ttu-id="7e12d-129">ABA</span><span class="sxs-lookup"><span data-stu-id="7e12d-129">aba</span></span>
- <span data-ttu-id="7e12d-130">aba #</span><span class="sxs-lookup"><span data-stu-id="7e12d-130">aba #</span></span>
- <span data-ttu-id="7e12d-131">aba routing #</span><span class="sxs-lookup"><span data-stu-id="7e12d-131">aba routing #</span></span>
- <span data-ttu-id="7e12d-132">aba routing number</span><span class="sxs-lookup"><span data-stu-id="7e12d-132">aba routing number</span></span>
- <span data-ttu-id="7e12d-133">ABA #</span><span class="sxs-lookup"><span data-stu-id="7e12d-133">aba#</span></span>
- <span data-ttu-id="7e12d-134">abarouting #</span><span class="sxs-lookup"><span data-stu-id="7e12d-134">abarouting#</span></span>
- <span data-ttu-id="7e12d-135">aba number</span><span class="sxs-lookup"><span data-stu-id="7e12d-135">aba number</span></span>
- <span data-ttu-id="7e12d-136">abaroutingnumber</span><span class="sxs-lookup"><span data-stu-id="7e12d-136">abaroutingnumber</span></span>
- <span data-ttu-id="7e12d-137">american bank association routing #</span><span class="sxs-lookup"><span data-stu-id="7e12d-137">american bank association routing #</span></span>
- <span data-ttu-id="7e12d-138">american bank association routing number</span><span class="sxs-lookup"><span data-stu-id="7e12d-138">american bank association routing number</span></span>
- <span data-ttu-id="7e12d-139">americanbankassociationrouting #</span><span class="sxs-lookup"><span data-stu-id="7e12d-139">americanbankassociationrouting#</span></span>
- <span data-ttu-id="7e12d-140">americanbankassociationroutingnumber</span><span class="sxs-lookup"><span data-stu-id="7e12d-140">americanbankassociationroutingnumber</span></span>
- <span data-ttu-id="7e12d-141">bank routing number</span><span class="sxs-lookup"><span data-stu-id="7e12d-141">bank routing number</span></span>
- <span data-ttu-id="7e12d-142">bankrouting #</span><span class="sxs-lookup"><span data-stu-id="7e12d-142">bankrouting#</span></span>
- <span data-ttu-id="7e12d-143">bankroutingnumber</span><span class="sxs-lookup"><span data-stu-id="7e12d-143">bankroutingnumber</span></span>
- <span data-ttu-id="7e12d-144">routing transit number</span><span class="sxs-lookup"><span data-stu-id="7e12d-144">routing transit number</span></span>
- <span data-ttu-id="7e12d-145">RTN</span><span class="sxs-lookup"><span data-stu-id="7e12d-145">RTN</span></span> 
   
## <a name="argentina-national-identity-dni-number"></a><span data-ttu-id="7e12d-146">Argentina - Numero di identità nazionale (DNI)</span><span class="sxs-lookup"><span data-stu-id="7e12d-146">Argentina National Identity (DNI) Number</span></span>

### <a name="format"></a><span data-ttu-id="7e12d-147">Formato</span><span class="sxs-lookup"><span data-stu-id="7e12d-147">Format</span></span>

<span data-ttu-id="7e12d-148">Otto cifre separate da spazi</span><span class="sxs-lookup"><span data-stu-id="7e12d-148">Eight digits separated by periods</span></span>

### <a name="pattern"></a><span data-ttu-id="7e12d-149">Modello</span><span class="sxs-lookup"><span data-stu-id="7e12d-149">Pattern</span></span>

<span data-ttu-id="7e12d-150">Otto cifre</span><span class="sxs-lookup"><span data-stu-id="7e12d-150">Eight digits:</span></span>
- <span data-ttu-id="7e12d-151">Due cifre</span><span class="sxs-lookup"><span data-stu-id="7e12d-151">Two digits</span></span>
- <span data-ttu-id="7e12d-152">Un punto </span><span class="sxs-lookup"><span data-stu-id="7e12d-152">A period</span></span>
- <span data-ttu-id="7e12d-153">Tre cifre</span><span class="sxs-lookup"><span data-stu-id="7e12d-153">Three digits</span></span>
- <span data-ttu-id="7e12d-154">Un punto </span><span class="sxs-lookup"><span data-stu-id="7e12d-154">A period</span></span>
- <span data-ttu-id="7e12d-155">Tre cifre</span><span class="sxs-lookup"><span data-stu-id="7e12d-155">Three digits</span></span>

### <a name="checksum"></a><span data-ttu-id="7e12d-156">Checksum</span><span class="sxs-lookup"><span data-stu-id="7e12d-156">Checksum</span></span>

<span data-ttu-id="7e12d-157">No</span><span class="sxs-lookup"><span data-stu-id="7e12d-157">No</span></span>

### <a name="definition"></a><span data-ttu-id="7e12d-158">Definizione</span><span class="sxs-lookup"><span data-stu-id="7e12d-158">Definition</span></span>

<span data-ttu-id="7e12d-159">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="7e12d-159">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="7e12d-160">L'espressione regolare Regex_argentina_national_id trova il contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="7e12d-160">The regular expression Regex_argentina_national_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="7e12d-161">Viene trovata una parola chiave da Keyword_argentina_national_id.</span><span class="sxs-lookup"><span data-stu-id="7e12d-161">A keyword from Keyword_argentina_national_id is found.</span></span>

```xml
<!-- Argentina National Identity (DNI) Number -->
<Entity id="eefbb00e-8282-433c-8620-8f1da3bffdb2" recommendedConfidence="75" patternsProximity="300">
   <Pattern confidenceLevel="75">
      <IdMatch idRef="Regex_argentina_national_id"/>
      <Match idRef="Keyword_argentina_national_id"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="7e12d-162">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="7e12d-162">Keywords</span></span>

#### <a name="keyword_argentina_national_id"></a><span data-ttu-id="7e12d-163">Keyword_argentina_national_id</span><span class="sxs-lookup"><span data-stu-id="7e12d-163">Keyword_argentina_national_id</span></span>

- <span data-ttu-id="7e12d-164">Argentina - Numero di identità nazionale</span><span class="sxs-lookup"><span data-stu-id="7e12d-164">Argentina National Identity number</span></span> 
- <span data-ttu-id="7e12d-165">Identità</span><span class="sxs-lookup"><span data-stu-id="7e12d-165">Identity</span></span> 
- <span data-ttu-id="7e12d-166">Carta di identità nazionale di identificazione</span><span class="sxs-lookup"><span data-stu-id="7e12d-166">Identification National Identity Card</span></span> 
- <span data-ttu-id="7e12d-167">DNI</span><span class="sxs-lookup"><span data-stu-id="7e12d-167">DNI</span></span> 
- <span data-ttu-id="7e12d-168">Registro nazionale delle persone di NIC</span><span class="sxs-lookup"><span data-stu-id="7e12d-168">NIC National Registry of Persons</span></span> 
- <span data-ttu-id="7e12d-169">Documento Nacional de Identidad</span><span class="sxs-lookup"><span data-stu-id="7e12d-169">Documento Nacional de Identidad</span></span> 
- <span data-ttu-id="7e12d-170">Registro Nacional de las Personas</span><span class="sxs-lookup"><span data-stu-id="7e12d-170">Registro Nacional de las Personas</span></span> 
- <span data-ttu-id="7e12d-171">Identidad</span><span class="sxs-lookup"><span data-stu-id="7e12d-171">Identidad</span></span> 
- <span data-ttu-id="7e12d-172">Identificación</span><span class="sxs-lookup"><span data-stu-id="7e12d-172">Identificación</span></span> 
   
## <a name="australia-bank-account-number"></a><span data-ttu-id="7e12d-173">Australia - Numero di conto bancario</span><span class="sxs-lookup"><span data-stu-id="7e12d-173">Australia Bank Account Number</span></span>

### <a name="format"></a><span data-ttu-id="7e12d-174">Formato</span><span class="sxs-lookup"><span data-stu-id="7e12d-174">Format</span></span>

<span data-ttu-id="7e12d-175">6-10 cifre con o senza un numero BSB (Bank/State/Branch)</span><span class="sxs-lookup"><span data-stu-id="7e12d-175">6-10 digits with or without a bank state branch number</span></span>

### <a name="pattern"></a><span data-ttu-id="7e12d-176">Modello</span><span class="sxs-lookup"><span data-stu-id="7e12d-176">Pattern</span></span>

<span data-ttu-id="7e12d-177">Il numero di conto comprende 6-10 cifre.</span><span class="sxs-lookup"><span data-stu-id="7e12d-177">Account number is 6-10 digits.</span></span>
<span data-ttu-id="7e12d-178">Numero BSB australiano:</span><span class="sxs-lookup"><span data-stu-id="7e12d-178">Australia bank state branch number:</span></span>
- <span data-ttu-id="7e12d-179">Tre cifre</span><span class="sxs-lookup"><span data-stu-id="7e12d-179">Three digits</span></span> 
- <span data-ttu-id="7e12d-180">Una lineetta</span><span class="sxs-lookup"><span data-stu-id="7e12d-180">A hyphen</span></span> 
- <span data-ttu-id="7e12d-181">Tre cifre</span><span class="sxs-lookup"><span data-stu-id="7e12d-181">Three digits</span></span>

### <a name="checksum"></a><span data-ttu-id="7e12d-182">Checksum</span><span class="sxs-lookup"><span data-stu-id="7e12d-182">Checksum</span></span>

<span data-ttu-id="7e12d-183">No</span><span class="sxs-lookup"><span data-stu-id="7e12d-183">No</span></span>

### <a name="definition"></a><span data-ttu-id="7e12d-184">Definizione</span><span class="sxs-lookup"><span data-stu-id="7e12d-184">Definition</span></span>

<span data-ttu-id="7e12d-185">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="7e12d-185">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="7e12d-186">L'espressione regolare Regex_australia_bank_account_number restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="7e12d-186">The regular expression Regex_australia_bank_account_number finds content that matches the pattern..</span></span>
- <span data-ttu-id="7e12d-187">Viene trovata una parola chiave da Keyword_australia_bank_account_number.</span><span class="sxs-lookup"><span data-stu-id="7e12d-187">A keyword from Keyword_australia_bank_account_number is found.</span></span>
- <span data-ttu-id="7e12d-188">L'espressione regolare Regex_australia_bank_account_number_bsb restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="7e12d-188">The regular expression Regex_australia_bank_account_number_bsb finds content that matches the pattern.</span></span>

<span data-ttu-id="7e12d-189">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="7e12d-189">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="7e12d-190">L'espressione regolare Regex_australia_bank_account_number restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="7e12d-190">The regular expression Regex_australia_bank_account_number finds content that matches the pattern..</span></span>
- <span data-ttu-id="7e12d-191">Viene trovata una parola chiave da Keyword_australia_bank_account_number.</span><span class="sxs-lookup"><span data-stu-id="7e12d-191">A keyword from Keyword_australia_bank_account_number is found.</span></span>

```xml
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

### <a name="keywords"></a><span data-ttu-id="7e12d-192">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="7e12d-192">Keywords</span></span>

#### <a name="keyword_australia_bank_account_number"></a><span data-ttu-id="7e12d-193">Keyword_australia_bank_account_number</span><span class="sxs-lookup"><span data-stu-id="7e12d-193">Keyword_australia_bank_account_number</span></span>

- <span data-ttu-id="7e12d-194">swift bank code</span><span class="sxs-lookup"><span data-stu-id="7e12d-194">swift bank code</span></span>
- <span data-ttu-id="7e12d-195">correspondent bank</span><span class="sxs-lookup"><span data-stu-id="7e12d-195">correspondent bank</span></span>
- <span data-ttu-id="7e12d-196">base currency</span><span class="sxs-lookup"><span data-stu-id="7e12d-196">base currency</span></span>
- <span data-ttu-id="7e12d-197">usa account</span><span class="sxs-lookup"><span data-stu-id="7e12d-197">usa account</span></span>
- <span data-ttu-id="7e12d-198">holder address</span><span class="sxs-lookup"><span data-stu-id="7e12d-198">holder address</span></span>
- <span data-ttu-id="7e12d-199">bank address</span><span class="sxs-lookup"><span data-stu-id="7e12d-199">bank address</span></span>
- <span data-ttu-id="7e12d-200">information account</span><span class="sxs-lookup"><span data-stu-id="7e12d-200">information account</span></span>
- <span data-ttu-id="7e12d-201">fund transfers</span><span class="sxs-lookup"><span data-stu-id="7e12d-201">fund transfers</span></span>
- <span data-ttu-id="7e12d-202">bank charges</span><span class="sxs-lookup"><span data-stu-id="7e12d-202">bank charges</span></span>
- <span data-ttu-id="7e12d-203">bank details</span><span class="sxs-lookup"><span data-stu-id="7e12d-203">bank details</span></span>
- <span data-ttu-id="7e12d-204">banking information</span><span class="sxs-lookup"><span data-stu-id="7e12d-204">banking information</span></span>
- <span data-ttu-id="7e12d-205">full names</span><span class="sxs-lookup"><span data-stu-id="7e12d-205">full names</span></span>
- <span data-ttu-id="7e12d-206">AIEA</span><span class="sxs-lookup"><span data-stu-id="7e12d-206">iaea</span></span>

   
## <a name="australia-drivers-license-number"></a><span data-ttu-id="7e12d-207">Australia - Numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="7e12d-207">Australia Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="7e12d-208">Formato</span><span class="sxs-lookup"><span data-stu-id="7e12d-208">Format</span></span>

<span data-ttu-id="7e12d-209">Nove lettere e numeri</span><span class="sxs-lookup"><span data-stu-id="7e12d-209">Nine letters and digits</span></span>

### <a name="pattern"></a><span data-ttu-id="7e12d-210">Modello</span><span class="sxs-lookup"><span data-stu-id="7e12d-210">Pattern</span></span>

<span data-ttu-id="7e12d-211">Nove lettere e numeri:</span><span class="sxs-lookup"><span data-stu-id="7e12d-211">Nine letters and digits:</span></span> 

- <span data-ttu-id="7e12d-212">Due cifre o lettere (senza distinzione tra maiuscole/minuscole)</span><span class="sxs-lookup"><span data-stu-id="7e12d-212">Two digits or letters (not case sensitive)</span></span> 
- <span data-ttu-id="7e12d-213">Due cifre</span><span class="sxs-lookup"><span data-stu-id="7e12d-213">Two digits</span></span> 
- <span data-ttu-id="7e12d-214">Cinque cifre o lettere (senza distinzione tra maiuscole/minuscole)</span><span class="sxs-lookup"><span data-stu-id="7e12d-214">Five digits or letters (not case sensitive)</span></span>

<span data-ttu-id="7e12d-215">O</span><span class="sxs-lookup"><span data-stu-id="7e12d-215">OR</span></span>

- <span data-ttu-id="7e12d-216">1-2 lettere facoltative (senza distinzione tra maiuscole/minuscole)</span><span class="sxs-lookup"><span data-stu-id="7e12d-216">1-2 optional letters (not case sensitive)</span></span> 
- <span data-ttu-id="7e12d-217">4-9 cifre</span><span class="sxs-lookup"><span data-stu-id="7e12d-217">4-9 digits</span></span>

<span data-ttu-id="7e12d-218">O</span><span class="sxs-lookup"><span data-stu-id="7e12d-218">OR</span></span>

- <span data-ttu-id="7e12d-219">Nove cifre o lettere (senza distinzione tra maiuscole/minuscole)</span><span class="sxs-lookup"><span data-stu-id="7e12d-219">Nine digits or letters (not case sensitive)</span></span>

### <a name="checksum"></a><span data-ttu-id="7e12d-220">Checksum</span><span class="sxs-lookup"><span data-stu-id="7e12d-220">Checksum</span></span>

<span data-ttu-id="7e12d-221">No</span><span class="sxs-lookup"><span data-stu-id="7e12d-221">No</span></span>

### <a name="definition"></a><span data-ttu-id="7e12d-222">Definizione</span><span class="sxs-lookup"><span data-stu-id="7e12d-222">Definition</span></span>

<span data-ttu-id="7e12d-223">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="7e12d-223">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="7e12d-224">L'espressione regolare Regex_australia_drivers_license_number restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="7e12d-224">The regular expression Regex_australia_drivers_license_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="7e12d-225">Viene trovata una parola chiave da Keyword_australia_drivers_license_number.</span><span class="sxs-lookup"><span data-stu-id="7e12d-225">A keyword from Keyword_australia_drivers_license_number is found.</span></span>
- <span data-ttu-id="7e12d-226">Non vengono trovate parole chiava da Keyword_australia_drivers_license_number_exclusions.</span><span class="sxs-lookup"><span data-stu-id="7e12d-226">No keyword from Keyword_australia_drivers_license_number_exclusions is found.</span></span>

```xml
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

### <a name="keywords"></a><span data-ttu-id="7e12d-227">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="7e12d-227">Keywords</span></span>

#### <a name="keyword_australia_drivers_license_number"></a><span data-ttu-id="7e12d-228">Keyword_australia_drivers_license_number</span><span class="sxs-lookup"><span data-stu-id="7e12d-228">Keyword_australia_drivers_license_number</span></span>

- <span data-ttu-id="7e12d-229">international driving permits</span><span class="sxs-lookup"><span data-stu-id="7e12d-229">international driving permits</span></span>
- <span data-ttu-id="7e12d-230">australian automobile association</span><span class="sxs-lookup"><span data-stu-id="7e12d-230">australian automobile association</span></span>
- <span data-ttu-id="7e12d-231">international driving permit</span><span class="sxs-lookup"><span data-stu-id="7e12d-231">international driving permit</span></span>
- <span data-ttu-id="7e12d-232">DriverLicence</span><span class="sxs-lookup"><span data-stu-id="7e12d-232">DriverLicence</span></span>
- <span data-ttu-id="7e12d-233">DriverLicences</span><span class="sxs-lookup"><span data-stu-id="7e12d-233">DriverLicences</span></span>
- <span data-ttu-id="7e12d-234">Driver Lic</span><span class="sxs-lookup"><span data-stu-id="7e12d-234">Driver Lic</span></span>
- <span data-ttu-id="7e12d-235">Driver Licence</span><span class="sxs-lookup"><span data-stu-id="7e12d-235">Driver Licence</span></span>
- <span data-ttu-id="7e12d-236">Driver Licences</span><span class="sxs-lookup"><span data-stu-id="7e12d-236">Driver Licences</span></span>
- <span data-ttu-id="7e12d-237">DriversLic</span><span class="sxs-lookup"><span data-stu-id="7e12d-237">DriversLic</span></span>
- <span data-ttu-id="7e12d-238">DriversLicence</span><span class="sxs-lookup"><span data-stu-id="7e12d-238">DriversLicence</span></span>
- <span data-ttu-id="7e12d-239">DriversLicences</span><span class="sxs-lookup"><span data-stu-id="7e12d-239">DriversLicences</span></span>
- <span data-ttu-id="7e12d-240">Drivers Lic</span><span class="sxs-lookup"><span data-stu-id="7e12d-240">Drivers Lic</span></span>
- <span data-ttu-id="7e12d-241">Drivers Lics</span><span class="sxs-lookup"><span data-stu-id="7e12d-241">Drivers Lics</span></span>
- <span data-ttu-id="7e12d-242">Drivers Licence</span><span class="sxs-lookup"><span data-stu-id="7e12d-242">Drivers Licence</span></span>
- <span data-ttu-id="7e12d-243">Drivers Licences</span><span class="sxs-lookup"><span data-stu-id="7e12d-243">Drivers Licences</span></span>
- <span data-ttu-id="7e12d-244">Driver'Lic</span><span class="sxs-lookup"><span data-stu-id="7e12d-244">Driver'Lic</span></span>
- <span data-ttu-id="7e12d-245">Driver ' LiCS</span><span class="sxs-lookup"><span data-stu-id="7e12d-245">Driver'Lics</span></span>
- <span data-ttu-id="7e12d-246">Driver'Licence</span><span class="sxs-lookup"><span data-stu-id="7e12d-246">Driver'Licence</span></span>
- <span data-ttu-id="7e12d-247">Driver'Licences</span><span class="sxs-lookup"><span data-stu-id="7e12d-247">Driver'Licences</span></span>
- <span data-ttu-id="7e12d-248">Driver'Lic</span><span class="sxs-lookup"><span data-stu-id="7e12d-248">Driver' Lic</span></span>
- <span data-ttu-id="7e12d-249">Driver'Lics</span><span class="sxs-lookup"><span data-stu-id="7e12d-249">Driver' Lics</span></span>
- <span data-ttu-id="7e12d-250">Driver'Licence</span><span class="sxs-lookup"><span data-stu-id="7e12d-250">Driver' Licence</span></span>
- <span data-ttu-id="7e12d-251">Driver' Licences</span><span class="sxs-lookup"><span data-stu-id="7e12d-251">Driver' Licences</span></span>
- <span data-ttu-id="7e12d-252">Driver'sLic</span><span class="sxs-lookup"><span data-stu-id="7e12d-252">Driver'sLic</span></span>
- <span data-ttu-id="7e12d-253">Driver'sLics</span><span class="sxs-lookup"><span data-stu-id="7e12d-253">Driver'sLics</span></span>
- <span data-ttu-id="7e12d-254">Driver'sLicence</span><span class="sxs-lookup"><span data-stu-id="7e12d-254">Driver'sLicence</span></span>
- <span data-ttu-id="7e12d-255">Driver'sLicences</span><span class="sxs-lookup"><span data-stu-id="7e12d-255">Driver'sLicences</span></span>
- <span data-ttu-id="7e12d-256">Driver's Lic</span><span class="sxs-lookup"><span data-stu-id="7e12d-256">Driver's Lic</span></span>
- <span data-ttu-id="7e12d-257">Driver's Lics</span><span class="sxs-lookup"><span data-stu-id="7e12d-257">Driver's Lics</span></span>
- <span data-ttu-id="7e12d-258">Driver's Licence</span><span class="sxs-lookup"><span data-stu-id="7e12d-258">Driver's Licence</span></span>
- <span data-ttu-id="7e12d-259">Driver's Licences</span><span class="sxs-lookup"><span data-stu-id="7e12d-259">Driver's Licences</span></span>
- <span data-ttu-id="7e12d-260">DriverLic #</span><span class="sxs-lookup"><span data-stu-id="7e12d-260">DriverLic#</span></span>
- <span data-ttu-id="7e12d-261">DriverLics #</span><span class="sxs-lookup"><span data-stu-id="7e12d-261">DriverLics#</span></span>
- <span data-ttu-id="7e12d-262">DriverLicence #</span><span class="sxs-lookup"><span data-stu-id="7e12d-262">DriverLicence#</span></span>
- <span data-ttu-id="7e12d-263">DriverLicences #</span><span class="sxs-lookup"><span data-stu-id="7e12d-263">DriverLicences#</span></span>
- <span data-ttu-id="7e12d-264">Driver Lic#</span><span class="sxs-lookup"><span data-stu-id="7e12d-264">Driver Lic#</span></span>
- <span data-ttu-id="7e12d-265">Driver Lics#</span><span class="sxs-lookup"><span data-stu-id="7e12d-265">Driver Lics#</span></span>
- <span data-ttu-id="7e12d-266">Driver Licence#</span><span class="sxs-lookup"><span data-stu-id="7e12d-266">Driver Licence#</span></span>
- <span data-ttu-id="7e12d-267">Driver Licences#</span><span class="sxs-lookup"><span data-stu-id="7e12d-267">Driver Licences#</span></span>
- <span data-ttu-id="7e12d-268">DriversLic #</span><span class="sxs-lookup"><span data-stu-id="7e12d-268">DriversLic#</span></span>
- <span data-ttu-id="7e12d-269">DriversLics #</span><span class="sxs-lookup"><span data-stu-id="7e12d-269">DriversLics#</span></span>
- <span data-ttu-id="7e12d-270">DriversLicence #</span><span class="sxs-lookup"><span data-stu-id="7e12d-270">DriversLicence#</span></span>
- <span data-ttu-id="7e12d-271">DriversLicences #</span><span class="sxs-lookup"><span data-stu-id="7e12d-271">DriversLicences#</span></span>
- <span data-ttu-id="7e12d-272">Drivers Lic#</span><span class="sxs-lookup"><span data-stu-id="7e12d-272">Drivers Lic#</span></span>
- <span data-ttu-id="7e12d-273">Drivers Lics#</span><span class="sxs-lookup"><span data-stu-id="7e12d-273">Drivers Lics#</span></span>
- <span data-ttu-id="7e12d-274">Drivers Licence#</span><span class="sxs-lookup"><span data-stu-id="7e12d-274">Drivers Licence#</span></span>
- <span data-ttu-id="7e12d-275">Drivers Licences#</span><span class="sxs-lookup"><span data-stu-id="7e12d-275">Drivers Licences#</span></span>
- <span data-ttu-id="7e12d-276">Driver'Lic #</span><span class="sxs-lookup"><span data-stu-id="7e12d-276">Driver'Lic#</span></span>
- <span data-ttu-id="7e12d-277">Driver ' LiCS #</span><span class="sxs-lookup"><span data-stu-id="7e12d-277">Driver'Lics#</span></span>
- <span data-ttu-id="7e12d-278">Driver'Licence #</span><span class="sxs-lookup"><span data-stu-id="7e12d-278">Driver'Licence#</span></span>
- <span data-ttu-id="7e12d-279">Driver'Licences #</span><span class="sxs-lookup"><span data-stu-id="7e12d-279">Driver'Licences#</span></span>
- <span data-ttu-id="7e12d-280">Driver' Lic#</span><span class="sxs-lookup"><span data-stu-id="7e12d-280">Driver' Lic#</span></span>
- <span data-ttu-id="7e12d-281">Driver'Lics#</span><span class="sxs-lookup"><span data-stu-id="7e12d-281">Driver' Lics#</span></span>
- <span data-ttu-id="7e12d-282">Driver'Licence#</span><span class="sxs-lookup"><span data-stu-id="7e12d-282">Driver' Licence#</span></span>
- <span data-ttu-id="7e12d-283">Driver' Licences#</span><span class="sxs-lookup"><span data-stu-id="7e12d-283">Driver' Licences#</span></span>
- <span data-ttu-id="7e12d-284">Driver'sLic #</span><span class="sxs-lookup"><span data-stu-id="7e12d-284">Driver'sLic#</span></span>
- <span data-ttu-id="7e12d-285">Driver'sLics #</span><span class="sxs-lookup"><span data-stu-id="7e12d-285">Driver'sLics#</span></span>
- <span data-ttu-id="7e12d-286">Driver'sLicence #</span><span class="sxs-lookup"><span data-stu-id="7e12d-286">Driver'sLicence#</span></span>
- <span data-ttu-id="7e12d-287">Driver'sLicences #</span><span class="sxs-lookup"><span data-stu-id="7e12d-287">Driver'sLicences#</span></span>
- <span data-ttu-id="7e12d-288">Driver's Lic#</span><span class="sxs-lookup"><span data-stu-id="7e12d-288">Driver's Lic#</span></span>
- <span data-ttu-id="7e12d-289">Driver's Lics#</span><span class="sxs-lookup"><span data-stu-id="7e12d-289">Driver's Lics#</span></span>
- <span data-ttu-id="7e12d-290">Driver's Licence#</span><span class="sxs-lookup"><span data-stu-id="7e12d-290">Driver's Licence#</span></span>
- <span data-ttu-id="7e12d-291">Driver's Licences#</span><span class="sxs-lookup"><span data-stu-id="7e12d-291">Driver's Licences#</span></span> 

#### <a name="keyword_australia_drivers_license_number_exclusions"></a><span data-ttu-id="7e12d-292">Keyword_australia_drivers_license_number_exclusions</span><span class="sxs-lookup"><span data-stu-id="7e12d-292">Keyword_australia_drivers_license_number_exclusions</span></span>

- <span data-ttu-id="7e12d-293">AAA</span><span class="sxs-lookup"><span data-stu-id="7e12d-293">aaa</span></span>
- <span data-ttu-id="7e12d-294">DriverLicense</span><span class="sxs-lookup"><span data-stu-id="7e12d-294">DriverLicense</span></span>
- <span data-ttu-id="7e12d-295">DriverLicenses</span><span class="sxs-lookup"><span data-stu-id="7e12d-295">DriverLicenses</span></span>
- <span data-ttu-id="7e12d-296">Driver License</span><span class="sxs-lookup"><span data-stu-id="7e12d-296">Driver License</span></span>
- <span data-ttu-id="7e12d-297">Driver Licenses</span><span class="sxs-lookup"><span data-stu-id="7e12d-297">Driver Licenses</span></span>
- <span data-ttu-id="7e12d-298">DriversLicense</span><span class="sxs-lookup"><span data-stu-id="7e12d-298">DriversLicense</span></span>
- <span data-ttu-id="7e12d-299">DriversLicenses</span><span class="sxs-lookup"><span data-stu-id="7e12d-299">DriversLicenses</span></span>
- <span data-ttu-id="7e12d-300">Drivers License</span><span class="sxs-lookup"><span data-stu-id="7e12d-300">Drivers License</span></span>
- <span data-ttu-id="7e12d-301">Drivers Licenses</span><span class="sxs-lookup"><span data-stu-id="7e12d-301">Drivers Licenses</span></span>
- <span data-ttu-id="7e12d-302">Driver ' License</span><span class="sxs-lookup"><span data-stu-id="7e12d-302">Driver'License</span></span>
- <span data-ttu-id="7e12d-303">Driver ' licenses</span><span class="sxs-lookup"><span data-stu-id="7e12d-303">Driver'Licenses</span></span>
- <span data-ttu-id="7e12d-304">Driver' License</span><span class="sxs-lookup"><span data-stu-id="7e12d-304">Driver' License</span></span>
- <span data-ttu-id="7e12d-305">Driver' Licenses</span><span class="sxs-lookup"><span data-stu-id="7e12d-305">Driver' Licenses</span></span>
- <span data-ttu-id="7e12d-306">Secondola</span><span class="sxs-lookup"><span data-stu-id="7e12d-306">Driver'sLicense</span></span>
- <span data-ttu-id="7e12d-307">Driver'sLicenses</span><span class="sxs-lookup"><span data-stu-id="7e12d-307">Driver'sLicenses</span></span>
- <span data-ttu-id="7e12d-308">Driver's License</span><span class="sxs-lookup"><span data-stu-id="7e12d-308">Driver's License</span></span>
- <span data-ttu-id="7e12d-309">Driver's Licenses</span><span class="sxs-lookup"><span data-stu-id="7e12d-309">Driver's Licenses</span></span>
- <span data-ttu-id="7e12d-310">DriverLicense #</span><span class="sxs-lookup"><span data-stu-id="7e12d-310">DriverLicense#</span></span>
- <span data-ttu-id="7e12d-311">DriverLicenses #</span><span class="sxs-lookup"><span data-stu-id="7e12d-311">DriverLicenses#</span></span>
- <span data-ttu-id="7e12d-312">Driver License#</span><span class="sxs-lookup"><span data-stu-id="7e12d-312">Driver License#</span></span>
- <span data-ttu-id="7e12d-313">Driver Licenses#</span><span class="sxs-lookup"><span data-stu-id="7e12d-313">Driver Licenses#</span></span>
- <span data-ttu-id="7e12d-314">DriversLicense #</span><span class="sxs-lookup"><span data-stu-id="7e12d-314">DriversLicense#</span></span>
- <span data-ttu-id="7e12d-315">DriversLicenses #</span><span class="sxs-lookup"><span data-stu-id="7e12d-315">DriversLicenses#</span></span>
- <span data-ttu-id="7e12d-316">Drivers License#</span><span class="sxs-lookup"><span data-stu-id="7e12d-316">Drivers License#</span></span>
- <span data-ttu-id="7e12d-317">Drivers Licenses#</span><span class="sxs-lookup"><span data-stu-id="7e12d-317">Drivers Licenses#</span></span>
- <span data-ttu-id="7e12d-318">Driver ' License #</span><span class="sxs-lookup"><span data-stu-id="7e12d-318">Driver'License#</span></span>
- <span data-ttu-id="7e12d-319">Driver ' licenses #</span><span class="sxs-lookup"><span data-stu-id="7e12d-319">Driver'Licenses#</span></span>
- <span data-ttu-id="7e12d-320">Driver' License#</span><span class="sxs-lookup"><span data-stu-id="7e12d-320">Driver' License#</span></span>
- <span data-ttu-id="7e12d-321">Driver' Licenses#</span><span class="sxs-lookup"><span data-stu-id="7e12d-321">Driver' Licenses#</span></span>
- <span data-ttu-id="7e12d-322">Secondola #</span><span class="sxs-lookup"><span data-stu-id="7e12d-322">Driver'sLicense#</span></span>
- <span data-ttu-id="7e12d-323">Driver'sLicenses #</span><span class="sxs-lookup"><span data-stu-id="7e12d-323">Driver'sLicenses#</span></span>
- <span data-ttu-id="7e12d-324">Driver's License#</span><span class="sxs-lookup"><span data-stu-id="7e12d-324">Driver's License#</span></span>
- <span data-ttu-id="7e12d-325">Driver's Licenses#</span><span class="sxs-lookup"><span data-stu-id="7e12d-325">Driver's Licenses#</span></span>
   
## <a name="australia-medical-account-number"></a><span data-ttu-id="7e12d-326">Australia - Numero di tessera sanitaria</span><span class="sxs-lookup"><span data-stu-id="7e12d-326">Australia Medical Account Number</span></span>

### <a name="format"></a><span data-ttu-id="7e12d-327">Formato</span><span class="sxs-lookup"><span data-stu-id="7e12d-327">Format</span></span>

<span data-ttu-id="7e12d-328">10-11 cifre</span><span class="sxs-lookup"><span data-stu-id="7e12d-328">10-11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="7e12d-329">Modello</span><span class="sxs-lookup"><span data-stu-id="7e12d-329">Pattern</span></span>

<span data-ttu-id="7e12d-330">10-11 cifre:</span><span class="sxs-lookup"><span data-stu-id="7e12d-330">10-11 digits:</span></span>
- <span data-ttu-id="7e12d-331">La prima cifra è compresa nell'intervallo 2-6</span><span class="sxs-lookup"><span data-stu-id="7e12d-331">First digit is in the range 2-6</span></span>
- <span data-ttu-id="7e12d-332">La nona cifra è una cifra di controllo</span><span class="sxs-lookup"><span data-stu-id="7e12d-332">Ninth digit is a check digit</span></span>
- <span data-ttu-id="7e12d-333">La decima cifra è la cifra del problema</span><span class="sxs-lookup"><span data-stu-id="7e12d-333">Tenth digit is the issue digit</span></span>
- <span data-ttu-id="7e12d-334">L'undicesima cifra (facoltativa) è il numero singolo</span><span class="sxs-lookup"><span data-stu-id="7e12d-334">Eleventh digit (optional) is the individual number</span></span>

### <a name="checksum"></a><span data-ttu-id="7e12d-335">Checksum</span><span class="sxs-lookup"><span data-stu-id="7e12d-335">Checksum</span></span>

<span data-ttu-id="7e12d-336">Sì</span><span class="sxs-lookup"><span data-stu-id="7e12d-336">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="7e12d-337">Definizione</span><span class="sxs-lookup"><span data-stu-id="7e12d-337">Definition</span></span>

<span data-ttu-id="7e12d-338">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 95%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="7e12d-338">A DLP policy is 95% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="7e12d-339">La funzione Func_australian_medical_account_number restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="7e12d-339">The function Func_australian_medical_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="7e12d-340">Viene trovata una parola chiave da Keyword_Australia_Medical_Account_Number.</span><span class="sxs-lookup"><span data-stu-id="7e12d-340">A keyword from Keyword_Australia_Medical_Account_Number is found.</span></span>
- <span data-ttu-id="7e12d-341">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="7e12d-341">The checksum passes.</span></span>

<span data-ttu-id="7e12d-342">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="7e12d-342">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="7e12d-343">La funzione Func_australian_medical_account_number restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="7e12d-343">The function Func_australian_medical_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="7e12d-344">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="7e12d-344">The checksum passes.</span></span>

```xml
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

### <a name="keywords"></a><span data-ttu-id="7e12d-345">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="7e12d-345">Keywords</span></span>

#### <a name="keyword_australia_medical_account_number"></a><span data-ttu-id="7e12d-346">Keyword_Australia_Medical_Account_Number</span><span class="sxs-lookup"><span data-stu-id="7e12d-346">Keyword_Australia_Medical_Account_Number</span></span>

- <span data-ttu-id="7e12d-347">bank account details</span><span class="sxs-lookup"><span data-stu-id="7e12d-347">bank account details</span></span>
- <span data-ttu-id="7e12d-348">medicare payments</span><span class="sxs-lookup"><span data-stu-id="7e12d-348">medicare payments</span></span>
- <span data-ttu-id="7e12d-349">mortgage account</span><span class="sxs-lookup"><span data-stu-id="7e12d-349">mortgage account</span></span>
- <span data-ttu-id="7e12d-350">bank payments</span><span class="sxs-lookup"><span data-stu-id="7e12d-350">bank payments</span></span>
- <span data-ttu-id="7e12d-351">information branch</span><span class="sxs-lookup"><span data-stu-id="7e12d-351">information branch</span></span>
- <span data-ttu-id="7e12d-352">credit card loan</span><span class="sxs-lookup"><span data-stu-id="7e12d-352">credit card loan</span></span>
- <span data-ttu-id="7e12d-353">department of human services</span><span class="sxs-lookup"><span data-stu-id="7e12d-353">department of human services</span></span>
- <span data-ttu-id="7e12d-354">local service</span><span class="sxs-lookup"><span data-stu-id="7e12d-354">local service</span></span>
- <span data-ttu-id="7e12d-355">Medicare</span><span class="sxs-lookup"><span data-stu-id="7e12d-355">medicare</span></span>

   
## <a name="australia-passport-number"></a><span data-ttu-id="7e12d-356">Australia - Numero di passaporto</span><span class="sxs-lookup"><span data-stu-id="7e12d-356">Australia Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="7e12d-357">Formato</span><span class="sxs-lookup"><span data-stu-id="7e12d-357">Format</span></span>

<span data-ttu-id="7e12d-358">Una lettera seguita da sette cifre</span><span class="sxs-lookup"><span data-stu-id="7e12d-358">A letter followed by seven digits</span></span>

### <a name="pattern"></a><span data-ttu-id="7e12d-359">Modello</span><span class="sxs-lookup"><span data-stu-id="7e12d-359">Pattern</span></span>

<span data-ttu-id="7e12d-360">Una lettera (senza distinzione tra maiuscole/minuscole) seguita da sette cifre</span><span class="sxs-lookup"><span data-stu-id="7e12d-360">A letter (not case sensitive) followed by seven digits</span></span>

### <a name="checksum"></a><span data-ttu-id="7e12d-361">Checksum</span><span class="sxs-lookup"><span data-stu-id="7e12d-361">Checksum</span></span>

<span data-ttu-id="7e12d-362">No</span><span class="sxs-lookup"><span data-stu-id="7e12d-362">No</span></span>

### <a name="definition"></a><span data-ttu-id="7e12d-363">Definizione</span><span class="sxs-lookup"><span data-stu-id="7e12d-363">Definition</span></span>

<span data-ttu-id="7e12d-364">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="7e12d-364">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="7e12d-365">L'espressione regolare Regex_australia_passport_number restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="7e12d-365">The regular expression Regex_australia_passport_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="7e12d-366">Viene trovata una parola chiave da Keyword_passport o Keyword_australia_passport_number.</span><span class="sxs-lookup"><span data-stu-id="7e12d-366">A keyword from Keyword_passport or Keyword_australia_passport_number is found.</span></span>

```xml
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

### <a name="keywords"></a><span data-ttu-id="7e12d-367">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="7e12d-367">Keywords</span></span>

#### <a name="keyword_passport"></a><span data-ttu-id="7e12d-368">Keyword_passport</span><span class="sxs-lookup"><span data-stu-id="7e12d-368">Keyword_passport</span></span>

- <span data-ttu-id="7e12d-369">Passport Number</span><span class="sxs-lookup"><span data-stu-id="7e12d-369">Passport Number</span></span>
- <span data-ttu-id="7e12d-370">Passport No</span><span class="sxs-lookup"><span data-stu-id="7e12d-370">Passport No</span></span>
- <span data-ttu-id="7e12d-371">Passport#</span><span class="sxs-lookup"><span data-stu-id="7e12d-371">Passport #</span></span>
- <span data-ttu-id="7e12d-372">Passaporto #</span><span class="sxs-lookup"><span data-stu-id="7e12d-372">Passport#</span></span>
- <span data-ttu-id="7e12d-373">PassportID</span><span class="sxs-lookup"><span data-stu-id="7e12d-373">PassportID</span></span>
- <span data-ttu-id="7e12d-374">Passportno</span><span class="sxs-lookup"><span data-stu-id="7e12d-374">Passportno</span></span>
- <span data-ttu-id="7e12d-375">passportnumber</span><span class="sxs-lookup"><span data-stu-id="7e12d-375">passportnumber</span></span>
- <span data-ttu-id="7e12d-376">パスポート</span><span class="sxs-lookup"><span data-stu-id="7e12d-376">パスポート</span></span>
- <span data-ttu-id="7e12d-377">パスポート番号</span><span class="sxs-lookup"><span data-stu-id="7e12d-377">パスポート番号</span></span>
- <span data-ttu-id="7e12d-378">パスポートのNum</span><span class="sxs-lookup"><span data-stu-id="7e12d-378">パスポートのNum</span></span>
- <span data-ttu-id="7e12d-379">パスポート ＃</span><span class="sxs-lookup"><span data-stu-id="7e12d-379">パスポート ＃</span></span> 
- <span data-ttu-id="7e12d-380">Numéro de passeport</span><span class="sxs-lookup"><span data-stu-id="7e12d-380">Numéro de passeport</span></span>
- <span data-ttu-id="7e12d-381">Passeport n °</span><span class="sxs-lookup"><span data-stu-id="7e12d-381">Passeport n °</span></span>
- <span data-ttu-id="7e12d-382">Passeport Non</span><span class="sxs-lookup"><span data-stu-id="7e12d-382">Passeport Non</span></span>
- <span data-ttu-id="7e12d-383">Passeport#</span><span class="sxs-lookup"><span data-stu-id="7e12d-383">Passeport #</span></span>
- <span data-ttu-id="7e12d-384">Passeport #</span><span class="sxs-lookup"><span data-stu-id="7e12d-384">Passeport#</span></span>
- <span data-ttu-id="7e12d-385">PasseportNon</span><span class="sxs-lookup"><span data-stu-id="7e12d-385">PasseportNon</span></span>
- <span data-ttu-id="7e12d-386">Passeportn °</span><span class="sxs-lookup"><span data-stu-id="7e12d-386">Passeportn °</span></span>

#### <a name="keyword_australia_passport_number"></a><span data-ttu-id="7e12d-387">Keyword_australia_passport_number</span><span class="sxs-lookup"><span data-stu-id="7e12d-387">Keyword_australia_passport_number</span></span>

- <span data-ttu-id="7e12d-388">passaporto</span><span class="sxs-lookup"><span data-stu-id="7e12d-388">passport</span></span>
- <span data-ttu-id="7e12d-389">passport details</span><span class="sxs-lookup"><span data-stu-id="7e12d-389">passport details</span></span>
- <span data-ttu-id="7e12d-390">immigration and citizenship</span><span class="sxs-lookup"><span data-stu-id="7e12d-390">immigration and citizenship</span></span>
- <span data-ttu-id="7e12d-391">commonwealth of australia</span><span class="sxs-lookup"><span data-stu-id="7e12d-391">commonwealth of australia</span></span>
- <span data-ttu-id="7e12d-392">department of immigration</span><span class="sxs-lookup"><span data-stu-id="7e12d-392">department of immigration</span></span>
- <span data-ttu-id="7e12d-393">residential address</span><span class="sxs-lookup"><span data-stu-id="7e12d-393">residential address</span></span>
- <span data-ttu-id="7e12d-394">department of immigration and citizenship</span><span class="sxs-lookup"><span data-stu-id="7e12d-394">department of immigration and citizenship</span></span>
- <span data-ttu-id="7e12d-395">esempio</span><span class="sxs-lookup"><span data-stu-id="7e12d-395">visa</span></span>
- <span data-ttu-id="7e12d-396">national identity card</span><span class="sxs-lookup"><span data-stu-id="7e12d-396">national identity card</span></span>
- <span data-ttu-id="7e12d-397">passport number</span><span class="sxs-lookup"><span data-stu-id="7e12d-397">passport number</span></span>
- <span data-ttu-id="7e12d-398">travel document</span><span class="sxs-lookup"><span data-stu-id="7e12d-398">travel document</span></span>
- <span data-ttu-id="7e12d-399">issuing authority</span><span class="sxs-lookup"><span data-stu-id="7e12d-399">issuing authority</span></span>
   
## <a name="australia-tax-file-number"></a><span data-ttu-id="7e12d-400">Australia - Identificativo fiscale</span><span class="sxs-lookup"><span data-stu-id="7e12d-400">Australia Tax File Number</span></span>

### <a name="format"></a><span data-ttu-id="7e12d-401">Formato</span><span class="sxs-lookup"><span data-stu-id="7e12d-401">Format</span></span>

<span data-ttu-id="7e12d-402">8-9 cifre</span><span class="sxs-lookup"><span data-stu-id="7e12d-402">8-9 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="7e12d-403">Modello</span><span class="sxs-lookup"><span data-stu-id="7e12d-403">Pattern</span></span>

<span data-ttu-id="7e12d-404">8-9 cifre in genere presentate con spazi, come mostrato di seguito:</span><span class="sxs-lookup"><span data-stu-id="7e12d-404">8-9 digits typically presented with spaces as follows:</span></span>
- <span data-ttu-id="7e12d-405">Tre cifre</span><span class="sxs-lookup"><span data-stu-id="7e12d-405">Three digits</span></span> 
- <span data-ttu-id="7e12d-406">Uno spazio facoltativo</span><span class="sxs-lookup"><span data-stu-id="7e12d-406">An optional space</span></span> 
- <span data-ttu-id="7e12d-407">Tre cifre</span><span class="sxs-lookup"><span data-stu-id="7e12d-407">Three digits</span></span> 
- <span data-ttu-id="7e12d-408">Uno spazio facoltativo</span><span class="sxs-lookup"><span data-stu-id="7e12d-408">An optional space</span></span> 
- <span data-ttu-id="7e12d-409">2-3 cifre e l'ultima è una cifra di controllo</span><span class="sxs-lookup"><span data-stu-id="7e12d-409">2-3 digits where the last digit is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="7e12d-410">Checksum</span><span class="sxs-lookup"><span data-stu-id="7e12d-410">Checksum</span></span>

<span data-ttu-id="7e12d-411">Sì</span><span class="sxs-lookup"><span data-stu-id="7e12d-411">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="7e12d-412">Definizione</span><span class="sxs-lookup"><span data-stu-id="7e12d-412">Definition</span></span>

<span data-ttu-id="7e12d-413">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="7e12d-413">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="7e12d-414">La funzione Func_australian_tax_file_number restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="7e12d-414">The function Func_australian_tax_file_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="7e12d-415">Non vengono trovate parole chiave da Keyword_Australia_Tax_File_Number o da Keyword_number_exclusions.</span><span class="sxs-lookup"><span data-stu-id="7e12d-415">No keyword from Keyword_Australia_Tax_File_Number or Keyword_number_exclusions is found.</span></span>
- <span data-ttu-id="7e12d-416">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="7e12d-416">The checksum passes.</span></span>

```xml
   <!-- Australia Tax File Number -->
    <Entity id="e29bc95f-ff70-4a37-aa01-04d17360a4c5" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_australian_tax_file_number" />
        <Match idRef="Keyword_Australia_Tax_File_Number" />
        <Any minMatches="0" maxMatches="0">
          <Match idRef="Keyword_number_exclusions" />
        </Any>
      </Pattern>
    </Entity>
```

### <a name="keywords"></a><span data-ttu-id="7e12d-417">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="7e12d-417">Keywords</span></span>

#### <a name="keyword_australia_tax_file_number"></a><span data-ttu-id="7e12d-418">Keyword_Australia_Tax_File_Number</span><span class="sxs-lookup"><span data-stu-id="7e12d-418">Keyword_Australia_Tax_File_Number</span></span>

- <span data-ttu-id="7e12d-419">australian business number</span><span class="sxs-lookup"><span data-stu-id="7e12d-419">australian business number</span></span>
- <span data-ttu-id="7e12d-420">marginal tax rate</span><span class="sxs-lookup"><span data-stu-id="7e12d-420">marginal tax rate</span></span>
- <span data-ttu-id="7e12d-421">medicare levy</span><span class="sxs-lookup"><span data-stu-id="7e12d-421">medicare levy</span></span>
- <span data-ttu-id="7e12d-422">portfolio number</span><span class="sxs-lookup"><span data-stu-id="7e12d-422">portfolio number</span></span>
- <span data-ttu-id="7e12d-423">service veterans</span><span class="sxs-lookup"><span data-stu-id="7e12d-423">service veterans</span></span>
- <span data-ttu-id="7e12d-424">withholding tax</span><span class="sxs-lookup"><span data-stu-id="7e12d-424">withholding tax</span></span>
- <span data-ttu-id="7e12d-425">individual tax return</span><span class="sxs-lookup"><span data-stu-id="7e12d-425">individual tax return</span></span>
- <span data-ttu-id="7e12d-426">tax file number</span><span class="sxs-lookup"><span data-stu-id="7e12d-426">tax file number</span></span>

#### <a name="keyword_number_exclusions"></a><span data-ttu-id="7e12d-427">Keyword_number_exclusions</span><span class="sxs-lookup"><span data-stu-id="7e12d-427">Keyword_number_exclusions</span></span>

- <span data-ttu-id="7e12d-428">00000000</span><span class="sxs-lookup"><span data-stu-id="7e12d-428">00000000</span></span>
- <span data-ttu-id="7e12d-429">11111111</span><span class="sxs-lookup"><span data-stu-id="7e12d-429">11111111</span></span>
- <span data-ttu-id="7e12d-430">22222222</span><span class="sxs-lookup"><span data-stu-id="7e12d-430">22222222</span></span>
- <span data-ttu-id="7e12d-431">33333333</span><span class="sxs-lookup"><span data-stu-id="7e12d-431">33333333</span></span>
- <span data-ttu-id="7e12d-432">44444444</span><span class="sxs-lookup"><span data-stu-id="7e12d-432">44444444</span></span>
- <span data-ttu-id="7e12d-433">55555555</span><span class="sxs-lookup"><span data-stu-id="7e12d-433">55555555</span></span>
- <span data-ttu-id="7e12d-434">66666666</span><span class="sxs-lookup"><span data-stu-id="7e12d-434">66666666</span></span>
- <span data-ttu-id="7e12d-435">77777777</span><span class="sxs-lookup"><span data-stu-id="7e12d-435">77777777</span></span>
- <span data-ttu-id="7e12d-436">88888888</span><span class="sxs-lookup"><span data-stu-id="7e12d-436">88888888</span></span>
- <span data-ttu-id="7e12d-437">99999999</span><span class="sxs-lookup"><span data-stu-id="7e12d-437">99999999</span></span>
- <span data-ttu-id="7e12d-438">000000000</span><span class="sxs-lookup"><span data-stu-id="7e12d-438">000000000</span></span>
- <span data-ttu-id="7e12d-439">111111111</span><span class="sxs-lookup"><span data-stu-id="7e12d-439">111111111</span></span>
- <span data-ttu-id="7e12d-440">222222222</span><span class="sxs-lookup"><span data-stu-id="7e12d-440">222222222</span></span>
- <span data-ttu-id="7e12d-441">333333333</span><span class="sxs-lookup"><span data-stu-id="7e12d-441">333333333</span></span>
- <span data-ttu-id="7e12d-442">444444444</span><span class="sxs-lookup"><span data-stu-id="7e12d-442">444444444</span></span>
- <span data-ttu-id="7e12d-443">555555555</span><span class="sxs-lookup"><span data-stu-id="7e12d-443">555555555</span></span>
- <span data-ttu-id="7e12d-444">666666666</span><span class="sxs-lookup"><span data-stu-id="7e12d-444">666666666</span></span>
- <span data-ttu-id="7e12d-445">777777777</span><span class="sxs-lookup"><span data-stu-id="7e12d-445">777777777</span></span>
- <span data-ttu-id="7e12d-446">888888888</span><span class="sxs-lookup"><span data-stu-id="7e12d-446">888888888</span></span>
- <span data-ttu-id="7e12d-447">999999999</span><span class="sxs-lookup"><span data-stu-id="7e12d-447">999999999</span></span>
- <span data-ttu-id="7e12d-448">0000000000</span><span class="sxs-lookup"><span data-stu-id="7e12d-448">0000000000</span></span>
- <span data-ttu-id="7e12d-449">1111111111</span><span class="sxs-lookup"><span data-stu-id="7e12d-449">1111111111</span></span>
- <span data-ttu-id="7e12d-450">2222222222</span><span class="sxs-lookup"><span data-stu-id="7e12d-450">2222222222</span></span>
- <span data-ttu-id="7e12d-451">3333333333</span><span class="sxs-lookup"><span data-stu-id="7e12d-451">3333333333</span></span>
- <span data-ttu-id="7e12d-452">4444444444</span><span class="sxs-lookup"><span data-stu-id="7e12d-452">4444444444</span></span>
- <span data-ttu-id="7e12d-453">5555555555</span><span class="sxs-lookup"><span data-stu-id="7e12d-453">5555555555</span></span>
- <span data-ttu-id="7e12d-454">6666666666</span><span class="sxs-lookup"><span data-stu-id="7e12d-454">6666666666</span></span>
- <span data-ttu-id="7e12d-455">7777777777</span><span class="sxs-lookup"><span data-stu-id="7e12d-455">7777777777</span></span>
- <span data-ttu-id="7e12d-456">8888888888</span><span class="sxs-lookup"><span data-stu-id="7e12d-456">8888888888</span></span>
- <span data-ttu-id="7e12d-457">9999999999</span><span class="sxs-lookup"><span data-stu-id="7e12d-457">9999999999</span></span>

## <a name="azure-documentdb-auth-key"></a><span data-ttu-id="7e12d-458">Chiave di autenticazione di DocumentDB di Azure</span><span class="sxs-lookup"><span data-stu-id="7e12d-458">Azure DocumentDB Auth Key</span></span>

### <a name="format"></a><span data-ttu-id="7e12d-459">Formato</span><span class="sxs-lookup"><span data-stu-id="7e12d-459">Format</span></span>

<span data-ttu-id="7e12d-460">La stringa "DocumentDb" seguita dai caratteri e dalle stringhe delineate nel modello seguente.</span><span class="sxs-lookup"><span data-stu-id="7e12d-460">The string "DocumentDb" followed by the characters and strings outlined in the pattern below.</span></span>

### <a name="pattern"></a><span data-ttu-id="7e12d-461">Modello</span><span class="sxs-lookup"><span data-stu-id="7e12d-461">Pattern</span></span>

- <span data-ttu-id="7e12d-462">La stringa "DocumentDb"</span><span class="sxs-lookup"><span data-stu-id="7e12d-462">The string "DocumentDb"</span></span>
- <span data-ttu-id="7e12d-463">Qualsiasi combinazione tra 3-200 lettere, cifre, simboli, caratteri speciali o spazi in maiuscolo o minuscolo</span><span class="sxs-lookup"><span data-stu-id="7e12d-463">Any combination of between 3-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="7e12d-464">Un simbolo maggiore di (>), un segno di uguale (=), un segno di virgolette (") oppure un apostrofo (')</span><span class="sxs-lookup"><span data-stu-id="7e12d-464">A greater than symbol (>), an equal sign (=), a quotation mark ("), or an apostrophe (')</span></span>
- <span data-ttu-id="7e12d-465">Qualsiasi combinazione di 86 lettere maiuscole e minuscole, cifre, barra (/) o segno più (+)</span><span class="sxs-lookup"><span data-stu-id="7e12d-465">Any combination of 86 lower- or uppercase letters, digits, forward slash (/), or plus sign (+)</span></span>
- <span data-ttu-id="7e12d-466">Due segni uguali (=)</span><span class="sxs-lookup"><span data-stu-id="7e12d-466">Two equal signs (=)</span></span>

### <a name="checksum"></a><span data-ttu-id="7e12d-467">Checksum</span><span class="sxs-lookup"><span data-stu-id="7e12d-467">Checksum</span></span>

<span data-ttu-id="7e12d-468">No</span><span class="sxs-lookup"><span data-stu-id="7e12d-468">No</span></span>

### <a name="definition"></a><span data-ttu-id="7e12d-469">Definizione</span><span class="sxs-lookup"><span data-stu-id="7e12d-469">Definition</span></span>

<span data-ttu-id="7e12d-470">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="7e12d-470">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="7e12d-471">L'espressione regolare CEP_Regex_AzureDocumentDBAuthKey trova il contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="7e12d-471">The regular expression CEP_Regex_AzureDocumentDBAuthKey finds content that matches the pattern.</span></span>
- <span data-ttu-id="7e12d-472">L'espressione regolare CEP_CommonExampleKeywords non \*\*\*\* trova contenuto corrispondente al modello.</span><span class="sxs-lookup"><span data-stu-id="7e12d-472">The regular expression CEP_CommonExampleKeywords does **not** find content that matches the pattern.</span></span>

```xml
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

### <a name="keywords"></a><span data-ttu-id="7e12d-473">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="7e12d-473">Keywords</span></span>

#### <a name="cep_commonexamplekeywords"></a><span data-ttu-id="7e12d-474">CEP_CommonExampleKeywords</span><span class="sxs-lookup"><span data-stu-id="7e12d-474">CEP_CommonExampleKeywords</span></span>

<span data-ttu-id="7e12d-475">Si noti che tecnicamente questo tipo di informazioni riservate identifica queste parole chiave utilizzando un'espressione regolare, non un elenco di parola chiave.</span><span class="sxs-lookup"><span data-stu-id="7e12d-475">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="7e12d-476">contoso</span><span class="sxs-lookup"><span data-stu-id="7e12d-476">contoso</span></span>
- <span data-ttu-id="7e12d-477">Fabrikam</span><span class="sxs-lookup"><span data-stu-id="7e12d-477">fabrikam</span></span>
- <span data-ttu-id="7e12d-478">Northwind</span><span class="sxs-lookup"><span data-stu-id="7e12d-478">northwind</span></span>
- <span data-ttu-id="7e12d-479">sandbox</span><span class="sxs-lookup"><span data-stu-id="7e12d-479">sandbox</span></span>
- <span data-ttu-id="7e12d-480">OneBox</span><span class="sxs-lookup"><span data-stu-id="7e12d-480">onebox</span></span>
- <span data-ttu-id="7e12d-481">localhost</span><span class="sxs-lookup"><span data-stu-id="7e12d-481">localhost</span></span>
- <span data-ttu-id="7e12d-482">127.0.0.1</span><span class="sxs-lookup"><span data-stu-id="7e12d-482">127.0.0.1</span></span>
- <span data-ttu-id="7e12d-483">testacs.</span><span class="sxs-lookup"><span data-stu-id="7e12d-483">testacs.</span></span><!--no-hyperlink--><span data-ttu-id="7e12d-484">com</span><span class="sxs-lookup"><span data-stu-id="7e12d-484">com</span></span>
- <span data-ttu-id="7e12d-485">s-int.</span><span class="sxs-lookup"><span data-stu-id="7e12d-485">s-int.</span></span><!--no-hyperlink--><span data-ttu-id="7e12d-486">NET</span><span class="sxs-lookup"><span data-stu-id="7e12d-486">net</span></span>

## <a name="azure-iaas-database-connection-string-and-azure-sql-connection-string"></a><span data-ttu-id="7e12d-487">Stringa di connessione del database di Azure IAAS e stringa di connessione SQL di Azure</span><span class="sxs-lookup"><span data-stu-id="7e12d-487">Azure IAAS Database Connection String and Azure SQL Connection String</span></span>

### <a name="format"></a><span data-ttu-id="7e12d-488">Formato</span><span class="sxs-lookup"><span data-stu-id="7e12d-488">Format</span></span>

<span data-ttu-id="7e12d-489">Stringa "Server", "Server" o "Data Source" seguito dai caratteri e dalle stringhe delineati nel modello seguente, inclusa la stringa "cloudapp. Azure.</span><span class="sxs-lookup"><span data-stu-id="7e12d-489">The string "Server", "server", or "data source" followed by the characters and strings outlined in the pattern below, including the string "cloudapp.azure.</span></span><!--no-hyperlink--><span data-ttu-id="7e12d-490">com "o" cloudapp. Azure.</span><span class="sxs-lookup"><span data-stu-id="7e12d-490">com" or "cloudapp.azure.</span></span><!--no-hyperlink--><span data-ttu-id="7e12d-491">NET "o" database. Windows.</span><span class="sxs-lookup"><span data-stu-id="7e12d-491">net" or "database.windows.</span></span><!--no-hyperlink--><span data-ttu-id="7e12d-492">NET "e la stringa" password "o" password "o" pwd ".</span><span class="sxs-lookup"><span data-stu-id="7e12d-492">net", and the string "Password" or "password" or "pwd".</span></span>

### <a name="pattern"></a><span data-ttu-id="7e12d-493">Modello</span><span class="sxs-lookup"><span data-stu-id="7e12d-493">Pattern</span></span>

- <span data-ttu-id="7e12d-494">La stringa "Server", "Server" o "Data Source"</span><span class="sxs-lookup"><span data-stu-id="7e12d-494">The string "Server", "server", or "data source"</span></span>
- <span data-ttu-id="7e12d-495">0-2 caratteri dello spazio vuoto</span><span class="sxs-lookup"><span data-stu-id="7e12d-495">0-2 whitespace characters</span></span>
- <span data-ttu-id="7e12d-496">Segno di uguale (=)</span><span class="sxs-lookup"><span data-stu-id="7e12d-496">An equal sign (=)</span></span>
- <span data-ttu-id="7e12d-497">0-2 caratteri dello spazio vuoto</span><span class="sxs-lookup"><span data-stu-id="7e12d-497">0-2 whitespace characters</span></span>
- <span data-ttu-id="7e12d-498">Qualsiasi combinazione tra 1-200 lettere, cifre, simboli, caratteri speciali o spazi in maiuscolo o minuscolo</span><span class="sxs-lookup"><span data-stu-id="7e12d-498">Any combination of between 1-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="7e12d-499">La stringa "cloudapp. Azure.</span><span class="sxs-lookup"><span data-stu-id="7e12d-499">The string "cloudapp.azure.</span></span><!--no-hyperlink--><span data-ttu-id="7e12d-500">com "," cloudapp. Azure.</span><span class="sxs-lookup"><span data-stu-id="7e12d-500">com", "cloudapp.azure.</span></span><!--no-hyperlink--><span data-ttu-id="7e12d-501">NET "o" database. Windows.</span><span class="sxs-lookup"><span data-stu-id="7e12d-501">net", or "database.windows.</span></span><!--no-hyperlink--><span data-ttu-id="7e12d-502">NET</span><span class="sxs-lookup"><span data-stu-id="7e12d-502">net"</span></span>
- <span data-ttu-id="7e12d-503">Qualsiasi combinazione tra 1-300 lettere, cifre, simboli, caratteri speciali o spazi in maiuscolo o minuscolo</span><span class="sxs-lookup"><span data-stu-id="7e12d-503">Any combination of between 1-300 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="7e12d-504">La stringa "password", "password" o "pwd"</span><span class="sxs-lookup"><span data-stu-id="7e12d-504">The string "Password", "password", or "pwd"</span></span>
- <span data-ttu-id="7e12d-505">0-2 caratteri dello spazio vuoto</span><span class="sxs-lookup"><span data-stu-id="7e12d-505">0-2 whitespace characters</span></span>
- <span data-ttu-id="7e12d-506">Segno di uguale (=)</span><span class="sxs-lookup"><span data-stu-id="7e12d-506">An equal sign (=)</span></span>
- <span data-ttu-id="7e12d-507">0-2 caratteri dello spazio vuoto</span><span class="sxs-lookup"><span data-stu-id="7e12d-507">0-2 whitespace characters</span></span>
- <span data-ttu-id="7e12d-508">Uno o più caratteri non costituiti da un punto e virgola (;), virgolette (") o apostrofo (')</span><span class="sxs-lookup"><span data-stu-id="7e12d-508">One or more characters that is not a semicolon (;), quotation mark ("), or apostrophe (')</span></span>
- <span data-ttu-id="7e12d-509">Un punto e virgola (;), virgolette (") o apostrofo (')</span><span class="sxs-lookup"><span data-stu-id="7e12d-509">A semicolon (;), quotation mark ("), or apostrophe (')</span></span>

### <a name="checksum"></a><span data-ttu-id="7e12d-510">Checksum</span><span class="sxs-lookup"><span data-stu-id="7e12d-510">Checksum</span></span>

<span data-ttu-id="7e12d-511">No</span><span class="sxs-lookup"><span data-stu-id="7e12d-511">No</span></span>

### <a name="definition"></a><span data-ttu-id="7e12d-512">Definizione</span><span class="sxs-lookup"><span data-stu-id="7e12d-512">Definition</span></span>

<span data-ttu-id="7e12d-513">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="7e12d-513">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="7e12d-514">L'espressione regolare CEP_Regex_AzureConnectionString trova il contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="7e12d-514">The regular expression CEP_Regex_AzureConnectionString finds content that matches the pattern.</span></span>
- <span data-ttu-id="7e12d-515">L'espressione regolare CEP_CommonExampleKeywords non \*\*\*\* trova contenuto corrispondente al modello.</span><span class="sxs-lookup"><span data-stu-id="7e12d-515">The regular expression CEP_CommonExampleKeywords does **not** find content that matches the pattern.</span></span>

```xml
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

### <a name="keywords"></a><span data-ttu-id="7e12d-516">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="7e12d-516">Keywords</span></span>

#### <a name="cep_commonexamplekeywords"></a><span data-ttu-id="7e12d-517">CEP_CommonExampleKeywords</span><span class="sxs-lookup"><span data-stu-id="7e12d-517">CEP_CommonExampleKeywords</span></span>

<span data-ttu-id="7e12d-518">Si noti che tecnicamente questo tipo di informazioni riservate identifica queste parole chiave utilizzando un'espressione regolare, non un elenco di parola chiave.</span><span class="sxs-lookup"><span data-stu-id="7e12d-518">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="7e12d-519">contoso</span><span class="sxs-lookup"><span data-stu-id="7e12d-519">contoso</span></span>
- <span data-ttu-id="7e12d-520">Fabrikam</span><span class="sxs-lookup"><span data-stu-id="7e12d-520">fabrikam</span></span>
- <span data-ttu-id="7e12d-521">Northwind</span><span class="sxs-lookup"><span data-stu-id="7e12d-521">northwind</span></span>
- <span data-ttu-id="7e12d-522">sandbox</span><span class="sxs-lookup"><span data-stu-id="7e12d-522">sandbox</span></span>
- <span data-ttu-id="7e12d-523">OneBox</span><span class="sxs-lookup"><span data-stu-id="7e12d-523">onebox</span></span>
- <span data-ttu-id="7e12d-524">localhost</span><span class="sxs-lookup"><span data-stu-id="7e12d-524">localhost</span></span>
- <span data-ttu-id="7e12d-525">127.0.0.1</span><span class="sxs-lookup"><span data-stu-id="7e12d-525">127.0.0.1</span></span>
- <span data-ttu-id="7e12d-526">testacs.</span><span class="sxs-lookup"><span data-stu-id="7e12d-526">testacs.</span></span><!--no-hyperlink--><span data-ttu-id="7e12d-527">com</span><span class="sxs-lookup"><span data-stu-id="7e12d-527">com</span></span>
- <span data-ttu-id="7e12d-528">s-int.</span><span class="sxs-lookup"><span data-stu-id="7e12d-528">s-int.</span></span><!--no-hyperlink--><span data-ttu-id="7e12d-529">NET</span><span class="sxs-lookup"><span data-stu-id="7e12d-529">net</span></span>

## <a name="azure-iot-connection-string"></a><span data-ttu-id="7e12d-530">Stringa di connessione di Azure.</span><span class="sxs-lookup"><span data-stu-id="7e12d-530">Azure IoT Connection String</span></span>

### <a name="format"></a><span data-ttu-id="7e12d-531">Formato</span><span class="sxs-lookup"><span data-stu-id="7e12d-531">Format</span></span>

<span data-ttu-id="7e12d-532">La stringa "HostName" seguita dai caratteri e dalle stringhe delineati nel modello seguente, incluse le stringhe "Azure-Devices.</span><span class="sxs-lookup"><span data-stu-id="7e12d-532">The string "HostName" followed by the characters and strings outlined in the pattern below, including the strings "azure-devices.</span></span><!--no-hyperlink--><span data-ttu-id="7e12d-533">NET "e" SharedAccessKey ".</span><span class="sxs-lookup"><span data-stu-id="7e12d-533">net" and "SharedAccessKey".</span></span>

### <a name="pattern"></a><span data-ttu-id="7e12d-534">Modello</span><span class="sxs-lookup"><span data-stu-id="7e12d-534">Pattern</span></span>

- <span data-ttu-id="7e12d-535">La stringa "HostName"</span><span class="sxs-lookup"><span data-stu-id="7e12d-535">The string "HostName"</span></span>
- <span data-ttu-id="7e12d-536">0-2 caratteri dello spazio vuoto</span><span class="sxs-lookup"><span data-stu-id="7e12d-536">0-2 whitespace characters</span></span>
- <span data-ttu-id="7e12d-537">Segno di uguale (=)</span><span class="sxs-lookup"><span data-stu-id="7e12d-537">An equal sign (=)</span></span>
- <span data-ttu-id="7e12d-538">0-2 caratteri dello spazio vuoto</span><span class="sxs-lookup"><span data-stu-id="7e12d-538">0-2 whitespace characters</span></span>
- <span data-ttu-id="7e12d-539">Qualsiasi combinazione tra 1-200 lettere, cifre, simboli, caratteri speciali o spazi in maiuscolo o minuscolo</span><span class="sxs-lookup"><span data-stu-id="7e12d-539">Any combination of between 1-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="7e12d-540">La stringa "Azure-Devices.</span><span class="sxs-lookup"><span data-stu-id="7e12d-540">The string "azure-devices.</span></span><!--no-hyperlink--><span data-ttu-id="7e12d-541">NET</span><span class="sxs-lookup"><span data-stu-id="7e12d-541">net"</span></span>
- <span data-ttu-id="7e12d-542">Qualsiasi combinazione tra 1-200 lettere, cifre, simboli, caratteri speciali o spazi in maiuscolo o minuscolo</span><span class="sxs-lookup"><span data-stu-id="7e12d-542">Any combination of between 1-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="7e12d-543">La stringa "SharedAccessKey"</span><span class="sxs-lookup"><span data-stu-id="7e12d-543">The string "SharedAccessKey"</span></span>
- <span data-ttu-id="7e12d-544">0-2 caratteri dello spazio vuoto</span><span class="sxs-lookup"><span data-stu-id="7e12d-544">0-2 whitespace characters</span></span>
- <span data-ttu-id="7e12d-545">Segno di uguale (=)</span><span class="sxs-lookup"><span data-stu-id="7e12d-545">An equal sign (=)</span></span>
- <span data-ttu-id="7e12d-546">0-2 caratteri dello spazio vuoto</span><span class="sxs-lookup"><span data-stu-id="7e12d-546">0-2 whitespace characters</span></span>
- <span data-ttu-id="7e12d-547">Qualsiasi combinazione di 43 lettere maiuscole e minuscole, cifre, barra (/) o segno più (+)</span><span class="sxs-lookup"><span data-stu-id="7e12d-547">Any combination of 43 lower- or uppercase letters, digits, forward slash (/), or plus sign (+)</span></span>
- <span data-ttu-id="7e12d-548">Segno di uguale (=)</span><span class="sxs-lookup"><span data-stu-id="7e12d-548">An equal sign (=)</span></span>

### <a name="checksum"></a><span data-ttu-id="7e12d-549">Checksum</span><span class="sxs-lookup"><span data-stu-id="7e12d-549">Checksum</span></span>

<span data-ttu-id="7e12d-550">No</span><span class="sxs-lookup"><span data-stu-id="7e12d-550">No</span></span>

### <a name="definition"></a><span data-ttu-id="7e12d-551">Definizione</span><span class="sxs-lookup"><span data-stu-id="7e12d-551">Definition</span></span>

<span data-ttu-id="7e12d-552">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="7e12d-552">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="7e12d-553">L'espressione regolare CEP_Regex_AzureIoTConnectionString trova il contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="7e12d-553">The regular expression CEP_Regex_AzureIoTConnectionString finds content that matches the pattern.</span></span>
- <span data-ttu-id="7e12d-554">L'espressione regolare CEP_CommonExampleKeywords non \*\*\*\* trova contenuto corrispondente al modello.</span><span class="sxs-lookup"><span data-stu-id="7e12d-554">The regular expression CEP_CommonExampleKeywords does **not** find content that matches the pattern.</span></span>

```xml
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

### <a name="keywords"></a><span data-ttu-id="7e12d-555">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="7e12d-555">Keywords</span></span>

#### <a name="cep_commonexamplekeywords"></a><span data-ttu-id="7e12d-556">CEP_CommonExampleKeywords</span><span class="sxs-lookup"><span data-stu-id="7e12d-556">CEP_CommonExampleKeywords</span></span>

<span data-ttu-id="7e12d-557">Si noti che tecnicamente questo tipo di informazioni riservate identifica queste parole chiave utilizzando un'espressione regolare, non un elenco di parola chiave.</span><span class="sxs-lookup"><span data-stu-id="7e12d-557">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="7e12d-558">contoso</span><span class="sxs-lookup"><span data-stu-id="7e12d-558">contoso</span></span>
- <span data-ttu-id="7e12d-559">Fabrikam</span><span class="sxs-lookup"><span data-stu-id="7e12d-559">fabrikam</span></span>
- <span data-ttu-id="7e12d-560">Northwind</span><span class="sxs-lookup"><span data-stu-id="7e12d-560">northwind</span></span>
- <span data-ttu-id="7e12d-561">sandbox</span><span class="sxs-lookup"><span data-stu-id="7e12d-561">sandbox</span></span>
- <span data-ttu-id="7e12d-562">OneBox</span><span class="sxs-lookup"><span data-stu-id="7e12d-562">onebox</span></span>
- <span data-ttu-id="7e12d-563">localhost</span><span class="sxs-lookup"><span data-stu-id="7e12d-563">localhost</span></span>
- <span data-ttu-id="7e12d-564">127.0.0.1</span><span class="sxs-lookup"><span data-stu-id="7e12d-564">127.0.0.1</span></span>
- <span data-ttu-id="7e12d-565">testacs.</span><span class="sxs-lookup"><span data-stu-id="7e12d-565">testacs.</span></span><!--no-hyperlink--><span data-ttu-id="7e12d-566">com</span><span class="sxs-lookup"><span data-stu-id="7e12d-566">com</span></span>
- <span data-ttu-id="7e12d-567">s-int.</span><span class="sxs-lookup"><span data-stu-id="7e12d-567">s-int.</span></span><!--no-hyperlink--><span data-ttu-id="7e12d-568">NET</span><span class="sxs-lookup"><span data-stu-id="7e12d-568">net</span></span>

## <a name="azure-publish-setting-password"></a><span data-ttu-id="7e12d-569">Password per l'impostazione di pubblicazione di Azure</span><span class="sxs-lookup"><span data-stu-id="7e12d-569">Azure Publish Setting Password</span></span>

### <a name="format"></a><span data-ttu-id="7e12d-570">Formato</span><span class="sxs-lookup"><span data-stu-id="7e12d-570">Format</span></span>

<span data-ttu-id="7e12d-571">La stringa "UserPwd =" seguita da una stringa alfanumerica.</span><span class="sxs-lookup"><span data-stu-id="7e12d-571">The string "userpwd=" followed by an alphanumeric string.</span></span>

### <a name="pattern"></a><span data-ttu-id="7e12d-572">Modello</span><span class="sxs-lookup"><span data-stu-id="7e12d-572">Pattern</span></span>

- <span data-ttu-id="7e12d-573">La stringa "UserPwd ="</span><span class="sxs-lookup"><span data-stu-id="7e12d-573">The string "userpwd="</span></span>
- <span data-ttu-id="7e12d-574">Qualsiasi combinazione di lettere o cifre minuscole di 60</span><span class="sxs-lookup"><span data-stu-id="7e12d-574">Any combination of 60 lowercase letters or digits</span></span>
- <span data-ttu-id="7e12d-575">Virgolette (")</span><span class="sxs-lookup"><span data-stu-id="7e12d-575">A quotation mark (")</span></span>

### <a name="checksum"></a><span data-ttu-id="7e12d-576">Checksum</span><span class="sxs-lookup"><span data-stu-id="7e12d-576">Checksum</span></span>

<span data-ttu-id="7e12d-577">No</span><span class="sxs-lookup"><span data-stu-id="7e12d-577">No</span></span>

### <a name="definition"></a><span data-ttu-id="7e12d-578">Definizione</span><span class="sxs-lookup"><span data-stu-id="7e12d-578">Definition</span></span>

<span data-ttu-id="7e12d-579">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="7e12d-579">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="7e12d-580">L'espressione regolare CEP_Regex_AzurePublishSettingPasswords trova il contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="7e12d-580">The regular expression CEP_Regex_AzurePublishSettingPasswords finds content that matches the pattern.</span></span>
- <span data-ttu-id="7e12d-581">L'espressione regolare CEP_CommonExampleKeywords non \*\*\*\* trova contenuto corrispondente al modello.</span><span class="sxs-lookup"><span data-stu-id="7e12d-581">The regular expression CEP_CommonExampleKeywords does **not** find content that matches the pattern.</span></span>


```xml
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

### <a name="keywords"></a><span data-ttu-id="7e12d-582">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="7e12d-582">Keywords</span></span>

#### <a name="cep_commonexamplekeywords"></a><span data-ttu-id="7e12d-583">CEP_CommonExampleKeywords</span><span class="sxs-lookup"><span data-stu-id="7e12d-583">CEP_CommonExampleKeywords</span></span>

<span data-ttu-id="7e12d-584">Si noti che tecnicamente questo tipo di informazioni riservate identifica queste parole chiave utilizzando un'espressione regolare, non un elenco di parola chiave.</span><span class="sxs-lookup"><span data-stu-id="7e12d-584">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="7e12d-585">contoso</span><span class="sxs-lookup"><span data-stu-id="7e12d-585">contoso</span></span>
- <span data-ttu-id="7e12d-586">Fabrikam</span><span class="sxs-lookup"><span data-stu-id="7e12d-586">fabrikam</span></span>
- <span data-ttu-id="7e12d-587">Northwind</span><span class="sxs-lookup"><span data-stu-id="7e12d-587">northwind</span></span>
- <span data-ttu-id="7e12d-588">sandbox</span><span class="sxs-lookup"><span data-stu-id="7e12d-588">sandbox</span></span>
- <span data-ttu-id="7e12d-589">OneBox</span><span class="sxs-lookup"><span data-stu-id="7e12d-589">onebox</span></span>
- <span data-ttu-id="7e12d-590">localhost</span><span class="sxs-lookup"><span data-stu-id="7e12d-590">localhost</span></span>
- <span data-ttu-id="7e12d-591">127.0.0.1</span><span class="sxs-lookup"><span data-stu-id="7e12d-591">127.0.0.1</span></span>
- <span data-ttu-id="7e12d-592">testacs.</span><span class="sxs-lookup"><span data-stu-id="7e12d-592">testacs.</span></span><!--no-hyperlink--><span data-ttu-id="7e12d-593">com</span><span class="sxs-lookup"><span data-stu-id="7e12d-593">com</span></span>
- <span data-ttu-id="7e12d-594">s-int.</span><span class="sxs-lookup"><span data-stu-id="7e12d-594">s-int.</span></span><!--no-hyperlink--><span data-ttu-id="7e12d-595">NET</span><span class="sxs-lookup"><span data-stu-id="7e12d-595">net</span></span>

## <a name="azure-redis-cache-connection-string"></a><span data-ttu-id="7e12d-596">Stringa di connessione della cache di Azure Redis</span><span class="sxs-lookup"><span data-stu-id="7e12d-596">Azure Redis Cache Connection String</span></span>

### <a name="format"></a><span data-ttu-id="7e12d-597">Formato</span><span class="sxs-lookup"><span data-stu-id="7e12d-597">Format</span></span>

<span data-ttu-id="7e12d-598">La stringa "Redis. cache. Windows.</span><span class="sxs-lookup"><span data-stu-id="7e12d-598">The string "redis.cache.windows.</span></span><!--no-hyperlink--><span data-ttu-id="7e12d-599">NET "seguito dai caratteri e dalle stringhe delineati nel modello seguente, inclusa la stringa" password "o" pwd ".</span><span class="sxs-lookup"><span data-stu-id="7e12d-599">net" followed by the characters and strings outlined in the pattern below, including the string "password" or "pwd".</span></span>

### <a name="pattern"></a><span data-ttu-id="7e12d-600">Modello</span><span class="sxs-lookup"><span data-stu-id="7e12d-600">Pattern</span></span>

- <span data-ttu-id="7e12d-601">La stringa "Redis. cache. Windows.</span><span class="sxs-lookup"><span data-stu-id="7e12d-601">The string "redis.cache.windows.</span></span><!--no-hyperlink--><span data-ttu-id="7e12d-602">NET</span><span class="sxs-lookup"><span data-stu-id="7e12d-602">net"</span></span>
- <span data-ttu-id="7e12d-603">Qualsiasi combinazione tra 1-200 lettere, cifre, simboli, caratteri speciali o spazi in maiuscolo o minuscolo</span><span class="sxs-lookup"><span data-stu-id="7e12d-603">Any combination of between 1-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="7e12d-604">La stringa "password" o "pwd"</span><span class="sxs-lookup"><span data-stu-id="7e12d-604">The string "password" or "pwd"</span></span>
- <span data-ttu-id="7e12d-605">0-2 caratteri dello spazio vuoto</span><span class="sxs-lookup"><span data-stu-id="7e12d-605">0-2 whitespace characters</span></span>
- <span data-ttu-id="7e12d-606">Segno di uguale (=)</span><span class="sxs-lookup"><span data-stu-id="7e12d-606">An equal sign (=)</span></span>
- <span data-ttu-id="7e12d-607">0-2 caratteri dello spazio vuoto</span><span class="sxs-lookup"><span data-stu-id="7e12d-607">0-2 whitespace characters</span></span>
- <span data-ttu-id="7e12d-608">Qualsiasi combinazione di 43 caratteri che sono lettere maiuscole o minuscole, cifre, barra (/) o segno più (+)</span><span class="sxs-lookup"><span data-stu-id="7e12d-608">Any combination of 43 characters that are lower- or uppercase letters, digits, forward slash (/), or plus sign (+)</span></span>
- <span data-ttu-id="7e12d-609">Segno di uguale (=)</span><span class="sxs-lookup"><span data-stu-id="7e12d-609">An equal sign (=)</span></span>

### <a name="checksum"></a><span data-ttu-id="7e12d-610">Checksum</span><span class="sxs-lookup"><span data-stu-id="7e12d-610">Checksum</span></span>

<span data-ttu-id="7e12d-611">No</span><span class="sxs-lookup"><span data-stu-id="7e12d-611">No</span></span>

### <a name="definition"></a><span data-ttu-id="7e12d-612">Definizione</span><span class="sxs-lookup"><span data-stu-id="7e12d-612">Definition</span></span>

<span data-ttu-id="7e12d-613">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="7e12d-613">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="7e12d-614">L'espressione regolare CEP_Regex_AzureRedisCacheConnectionString trova il contenuto corrispondente al modello.</span><span class="sxs-lookup"><span data-stu-id="7e12d-614">The regular expression CEP_Regex_AzureRedisCacheConnectionString finds content that matches the pattern..</span></span>
- <span data-ttu-id="7e12d-615">L'espressione regolare CEP_CommonExampleKeywords non \*\*\*\* trova contenuto corrispondente al modello.</span><span class="sxs-lookup"><span data-stu-id="7e12d-615">The regular expression CEP_CommonExampleKeywords does **not** find content that matches the pattern.</span></span>

```xml
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

### <a name="keywords"></a><span data-ttu-id="7e12d-616">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="7e12d-616">Keywords</span></span>

#### <a name="cep_commonexamplekeywords"></a><span data-ttu-id="7e12d-617">CEP_CommonExampleKeywords</span><span class="sxs-lookup"><span data-stu-id="7e12d-617">CEP_CommonExampleKeywords</span></span>

<span data-ttu-id="7e12d-618">Si noti che tecnicamente questo tipo di informazioni riservate identifica queste parole chiave utilizzando un'espressione regolare, non un elenco di parola chiave.</span><span class="sxs-lookup"><span data-stu-id="7e12d-618">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="7e12d-619">contoso</span><span class="sxs-lookup"><span data-stu-id="7e12d-619">contoso</span></span>
- <span data-ttu-id="7e12d-620">Fabrikam</span><span class="sxs-lookup"><span data-stu-id="7e12d-620">fabrikam</span></span>
- <span data-ttu-id="7e12d-621">Northwind</span><span class="sxs-lookup"><span data-stu-id="7e12d-621">northwind</span></span>
- <span data-ttu-id="7e12d-622">sandbox</span><span class="sxs-lookup"><span data-stu-id="7e12d-622">sandbox</span></span>
- <span data-ttu-id="7e12d-623">OneBox</span><span class="sxs-lookup"><span data-stu-id="7e12d-623">onebox</span></span>
- <span data-ttu-id="7e12d-624">localhost</span><span class="sxs-lookup"><span data-stu-id="7e12d-624">localhost</span></span>
- <span data-ttu-id="7e12d-625">127.0.0.1</span><span class="sxs-lookup"><span data-stu-id="7e12d-625">127.0.0.1</span></span>
- <span data-ttu-id="7e12d-626">testacs.</span><span class="sxs-lookup"><span data-stu-id="7e12d-626">testacs.</span></span><!--no-hyperlink--><span data-ttu-id="7e12d-627">com</span><span class="sxs-lookup"><span data-stu-id="7e12d-627">com</span></span>
- <span data-ttu-id="7e12d-628">s-int.</span><span class="sxs-lookup"><span data-stu-id="7e12d-628">s-int.</span></span><!--no-hyperlink--><span data-ttu-id="7e12d-629">NET</span><span class="sxs-lookup"><span data-stu-id="7e12d-629">net</span></span>

## <a name="azure-sas"></a><span data-ttu-id="7e12d-630">SAS di Azure</span><span class="sxs-lookup"><span data-stu-id="7e12d-630">Azure SAS</span></span>

### <a name="format"></a><span data-ttu-id="7e12d-631">Formato</span><span class="sxs-lookup"><span data-stu-id="7e12d-631">Format</span></span>

<span data-ttu-id="7e12d-632">La stringa "sig" seguita dai caratteri e dalle stringhe delineate nel modello seguente.</span><span class="sxs-lookup"><span data-stu-id="7e12d-632">The string "sig" followed by the characters and strings outlined in the pattern below.</span></span>

### <a name="pattern"></a><span data-ttu-id="7e12d-633">Modello</span><span class="sxs-lookup"><span data-stu-id="7e12d-633">Pattern</span></span>

- <span data-ttu-id="7e12d-634">La stringa "sig"</span><span class="sxs-lookup"><span data-stu-id="7e12d-634">The string "sig"</span></span>
- <span data-ttu-id="7e12d-635">0-2 caratteri dello spazio vuoto</span><span class="sxs-lookup"><span data-stu-id="7e12d-635">0-2 whitespace characters</span></span>
- <span data-ttu-id="7e12d-636">Segno di uguale (=)</span><span class="sxs-lookup"><span data-stu-id="7e12d-636">An equal sign (=)</span></span>
- <span data-ttu-id="7e12d-637">0-2 caratteri dello spazio vuoto</span><span class="sxs-lookup"><span data-stu-id="7e12d-637">0-2 whitespace characters</span></span>
- <span data-ttu-id="7e12d-638">Qualsiasi combinazione tra 43-53 caratteri che sono minuscoli o maiuscoli, cifre o il segno di percentuale (%)</span><span class="sxs-lookup"><span data-stu-id="7e12d-638">Any combination of between 43-53 characters that are lower- or uppercase letters, digits, or the percent sign (%)</span></span>
- <span data-ttu-id="7e12d-639">La stringa "% 3D"</span><span class="sxs-lookup"><span data-stu-id="7e12d-639">The string "%3d"</span></span>
- <span data-ttu-id="7e12d-640">Qualsiasi carattere che non sia una lettera, una cifra o un segno di percentuale inferiore o maiuscolo (%)</span><span class="sxs-lookup"><span data-stu-id="7e12d-640">Any character that is not a lower- or uppercase letter, digit, or percent sign (%)</span></span>

### <a name="checksum"></a><span data-ttu-id="7e12d-641">Checksum</span><span class="sxs-lookup"><span data-stu-id="7e12d-641">Checksum</span></span>

<span data-ttu-id="7e12d-642">No</span><span class="sxs-lookup"><span data-stu-id="7e12d-642">No</span></span>

### <a name="definition"></a><span data-ttu-id="7e12d-643">Definizione</span><span class="sxs-lookup"><span data-stu-id="7e12d-643">Definition</span></span>

<span data-ttu-id="7e12d-644">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="7e12d-644">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="7e12d-645">L'espressione regolare CEP_Regex_AzureSAS trova il contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="7e12d-645">The regular expression CEP_Regex_AzureSAS finds content that matches the pattern.</span></span>

```xml
<!--Azure SAS-->
<Entity id="4d235014-e564-47f4-a6fb-6ebb4a826834" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_AzureSAS" />
  </Pattern>
</Entity>
```

## <a name="azure-service-bus-connection-string"></a><span data-ttu-id="7e12d-646">Stringa di connessione bus di servizio di Azure</span><span class="sxs-lookup"><span data-stu-id="7e12d-646">Azure Service Bus Connection String</span></span>

### <a name="format"></a><span data-ttu-id="7e12d-647">Formato</span><span class="sxs-lookup"><span data-stu-id="7e12d-647">Format</span></span>

<span data-ttu-id="7e12d-648">Stringa "EndPoint" seguita dai caratteri e dalle stringhe delineati nel modello seguente, incluse le stringhe "ServiceBus. Windows.</span><span class="sxs-lookup"><span data-stu-id="7e12d-648">The string "EndPoint" followed by the characters and strings outlined in the pattern below, including the strings "servicebus.windows.</span></span><!--no-hyperlink--><span data-ttu-id="7e12d-649">NET "e" SharedAccesKey ".</span><span class="sxs-lookup"><span data-stu-id="7e12d-649">net" and "SharedAccesKey".</span></span>

### <a name="pattern"></a><span data-ttu-id="7e12d-650">Modello</span><span class="sxs-lookup"><span data-stu-id="7e12d-650">Pattern</span></span>

- <span data-ttu-id="7e12d-651">La stringa "EndPoint"</span><span class="sxs-lookup"><span data-stu-id="7e12d-651">The string "EndPoint"</span></span>
- <span data-ttu-id="7e12d-652">0-2 caratteri dello spazio vuoto</span><span class="sxs-lookup"><span data-stu-id="7e12d-652">0-2 whitespace characters</span></span>
- <span data-ttu-id="7e12d-653">Segno di uguale (=)</span><span class="sxs-lookup"><span data-stu-id="7e12d-653">An equal sign (=)</span></span>
- <span data-ttu-id="7e12d-654">0-2 caratteri dello spazio vuoto</span><span class="sxs-lookup"><span data-stu-id="7e12d-654">0-2 whitespace characters</span></span>
- <span data-ttu-id="7e12d-655">Qualsiasi combinazione tra 1-200 lettere, cifre, simboli, caratteri speciali o spazi in maiuscolo o minuscolo</span><span class="sxs-lookup"><span data-stu-id="7e12d-655">Any combination of between 1-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="7e12d-656">La stringa "ServiceBus. Windows.</span><span class="sxs-lookup"><span data-stu-id="7e12d-656">The string "servicebus.windows.</span></span><!--no-hyperlink--><span data-ttu-id="7e12d-657">NET</span><span class="sxs-lookup"><span data-stu-id="7e12d-657">net"</span></span>
- <span data-ttu-id="7e12d-658">Qualsiasi combinazione tra 1-200 lettere, cifre, simboli, caratteri speciali o spazi in maiuscolo o minuscolo</span><span class="sxs-lookup"><span data-stu-id="7e12d-658">Any combination of between 1-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="7e12d-659">La stringa "SharedAccessKey"</span><span class="sxs-lookup"><span data-stu-id="7e12d-659">The string "SharedAccessKey"</span></span>
- <span data-ttu-id="7e12d-660">0-2 caratteri dello spazio vuoto</span><span class="sxs-lookup"><span data-stu-id="7e12d-660">0-2 whitespace characters</span></span>
- <span data-ttu-id="7e12d-661">Segno di uguale (=)</span><span class="sxs-lookup"><span data-stu-id="7e12d-661">An equal sign (=)</span></span>
- <span data-ttu-id="7e12d-662">0-2 caratteri dello spazio vuoto</span><span class="sxs-lookup"><span data-stu-id="7e12d-662">0-2 whitespace characters</span></span>
- <span data-ttu-id="7e12d-663">Qualsiasi combinazione di 43 caratteri che sono lettere maiuscole o minuscole, cifre, barra (/) o segno più (+)</span><span class="sxs-lookup"><span data-stu-id="7e12d-663">Any combination of 43 characters that are lower- or uppercase letters, digits, forward slash (/), or plus sign (+)</span></span>
- <span data-ttu-id="7e12d-664">Segno di uguale (=)</span><span class="sxs-lookup"><span data-stu-id="7e12d-664">An equal sign (=)</span></span>

### <a name="checksum"></a><span data-ttu-id="7e12d-665">Checksum</span><span class="sxs-lookup"><span data-stu-id="7e12d-665">Checksum</span></span>

<span data-ttu-id="7e12d-666">No</span><span class="sxs-lookup"><span data-stu-id="7e12d-666">No</span></span>

### <a name="definition"></a><span data-ttu-id="7e12d-667">Definizione</span><span class="sxs-lookup"><span data-stu-id="7e12d-667">Definition</span></span>

<span data-ttu-id="7e12d-668">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="7e12d-668">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="7e12d-669">L'espressione regolare CEP_Regex_AzureServiceBusConnectionString trova il contenuto corrispondente al modello.</span><span class="sxs-lookup"><span data-stu-id="7e12d-669">The regular expression CEP_Regex_AzureServiceBusConnectionString finds content that matches the pattern..</span></span>
- <span data-ttu-id="7e12d-670">L'espressione regolare CEP_CommonExampleKeywords non \*\*\*\* trova contenuto corrispondente al modello.</span><span class="sxs-lookup"><span data-stu-id="7e12d-670">The regular expression CEP_CommonExampleKeywords does **not** find content that matches the pattern.</span></span>

```xml
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

### <a name="keywords"></a><span data-ttu-id="7e12d-671">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="7e12d-671">Keywords</span></span>

#### <a name="cep_commonexamplekeywords"></a><span data-ttu-id="7e12d-672">CEP_CommonExampleKeywords</span><span class="sxs-lookup"><span data-stu-id="7e12d-672">CEP_CommonExampleKeywords</span></span>

<span data-ttu-id="7e12d-673">Si noti che tecnicamente questo tipo di informazioni riservate identifica queste parole chiave utilizzando un'espressione regolare, non un elenco di parola chiave.</span><span class="sxs-lookup"><span data-stu-id="7e12d-673">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="7e12d-674">contoso</span><span class="sxs-lookup"><span data-stu-id="7e12d-674">contoso</span></span>
- <span data-ttu-id="7e12d-675">Fabrikam</span><span class="sxs-lookup"><span data-stu-id="7e12d-675">fabrikam</span></span>
- <span data-ttu-id="7e12d-676">Northwind</span><span class="sxs-lookup"><span data-stu-id="7e12d-676">northwind</span></span>
- <span data-ttu-id="7e12d-677">sandbox</span><span class="sxs-lookup"><span data-stu-id="7e12d-677">sandbox</span></span>
- <span data-ttu-id="7e12d-678">OneBox</span><span class="sxs-lookup"><span data-stu-id="7e12d-678">onebox</span></span>
- <span data-ttu-id="7e12d-679">localhost</span><span class="sxs-lookup"><span data-stu-id="7e12d-679">localhost</span></span>
- <span data-ttu-id="7e12d-680">127.0.0.1</span><span class="sxs-lookup"><span data-stu-id="7e12d-680">127.0.0.1</span></span>
- <span data-ttu-id="7e12d-681">testacs.</span><span class="sxs-lookup"><span data-stu-id="7e12d-681">testacs.</span></span><!--no-hyperlink--><span data-ttu-id="7e12d-682">com</span><span class="sxs-lookup"><span data-stu-id="7e12d-682">com</span></span>
- <span data-ttu-id="7e12d-683">s-int.</span><span class="sxs-lookup"><span data-stu-id="7e12d-683">s-int.</span></span><!--no-hyperlink--><span data-ttu-id="7e12d-684">NET</span><span class="sxs-lookup"><span data-stu-id="7e12d-684">net</span></span>

## <a name="azure-storage-account-key"></a><span data-ttu-id="7e12d-685">Chiave dell'account di archiviazione di Azure</span><span class="sxs-lookup"><span data-stu-id="7e12d-685">Azure Storage Account Key</span></span>

### <a name="format"></a><span data-ttu-id="7e12d-686">Formato</span><span class="sxs-lookup"><span data-stu-id="7e12d-686">Format</span></span>

<span data-ttu-id="7e12d-687">La stringa "DefaultEndpointsProtocol" seguita dai caratteri e dalle stringhe delineate nel modello seguente, inclusa la stringa "AccountKey".</span><span class="sxs-lookup"><span data-stu-id="7e12d-687">The string "DefaultEndpointsProtocol" followed by the characters and strings outlined in the pattern below, including the string "AccountKey".</span></span>

### <a name="pattern"></a><span data-ttu-id="7e12d-688">Modello</span><span class="sxs-lookup"><span data-stu-id="7e12d-688">Pattern</span></span>

- <span data-ttu-id="7e12d-689">La stringa "DefaultEndpointsProtocol"</span><span class="sxs-lookup"><span data-stu-id="7e12d-689">The string "DefaultEndpointsProtocol"</span></span>
- <span data-ttu-id="7e12d-690">0-2 caratteri dello spazio vuoto</span><span class="sxs-lookup"><span data-stu-id="7e12d-690">0-2 whitespace characters</span></span>
- <span data-ttu-id="7e12d-691">Segno di uguale (=)</span><span class="sxs-lookup"><span data-stu-id="7e12d-691">An equal sign (=)</span></span>
- <span data-ttu-id="7e12d-692">0-2 caratteri dello spazio vuoto</span><span class="sxs-lookup"><span data-stu-id="7e12d-692">0-2 whitespace characters</span></span>
- <span data-ttu-id="7e12d-693">Qualsiasi combinazione tra 1-200 lettere, cifre, simboli, caratteri speciali o spazi in maiuscolo o minuscolo</span><span class="sxs-lookup"><span data-stu-id="7e12d-693">Any combination of between 1-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="7e12d-694">La stringa "AccountKey"</span><span class="sxs-lookup"><span data-stu-id="7e12d-694">The string "AccountKey"</span></span>
- <span data-ttu-id="7e12d-695">0-2 caratteri dello spazio vuoto</span><span class="sxs-lookup"><span data-stu-id="7e12d-695">0-2 whitespace characters</span></span>
- <span data-ttu-id="7e12d-696">Segno di uguale (=)</span><span class="sxs-lookup"><span data-stu-id="7e12d-696">An equal sign (=)</span></span>
- <span data-ttu-id="7e12d-697">0-2 caratteri dello spazio vuoto</span><span class="sxs-lookup"><span data-stu-id="7e12d-697">0-2 whitespace characters</span></span>
- <span data-ttu-id="7e12d-698">Qualsiasi combinazione di 86 caratteri che sono lettere maiuscole o minuscole, cifre, barra (/) o segno più (+)</span><span class="sxs-lookup"><span data-stu-id="7e12d-698">Any combination of 86 characters that are lower- or uppercase letters, digits, forward slash (/), or plus sign (+)</span></span>
- <span data-ttu-id="7e12d-699">Due segni uguali (=)</span><span class="sxs-lookup"><span data-stu-id="7e12d-699">Two equal signs (=)</span></span>

### <a name="checksum"></a><span data-ttu-id="7e12d-700">Checksum</span><span class="sxs-lookup"><span data-stu-id="7e12d-700">Checksum</span></span>

<span data-ttu-id="7e12d-701">No</span><span class="sxs-lookup"><span data-stu-id="7e12d-701">No</span></span>

### <a name="definition"></a><span data-ttu-id="7e12d-702">Definizione</span><span class="sxs-lookup"><span data-stu-id="7e12d-702">Definition</span></span>

<span data-ttu-id="7e12d-703">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="7e12d-703">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="7e12d-704">L'espressione regolare CEP_Regex_AzureStorageAccountKey trova il contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="7e12d-704">The regular expression CEP_Regex_AzureStorageAccountKey finds content that matches the pattern.</span></span>
- <span data-ttu-id="7e12d-705">L'espressione regolare CEP_AzureEmulatorStorageAccountFilter non \*\*\*\* trova contenuto corrispondente al modello.</span><span class="sxs-lookup"><span data-stu-id="7e12d-705">The regular expression CEP_AzureEmulatorStorageAccountFilter does **not** find content that matches the pattern.</span></span>
- <span data-ttu-id="7e12d-706">L'espressione regolare CEP_CommonExampleKeywords non \*\*\*\* trova contenuto corrispondente al modello.</span><span class="sxs-lookup"><span data-stu-id="7e12d-706">The regular expression CEP_CommonExampleKeywords does **not** find content that matches the pattern.</span></span>

```xml
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

### <a name="keywords"></a><span data-ttu-id="7e12d-707">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="7e12d-707">Keywords</span></span>

#### <a name="cep_azureemulatorstorageaccountfilter"></a><span data-ttu-id="7e12d-708">CEP_AzureEmulatorStorageAccountFilter</span><span class="sxs-lookup"><span data-stu-id="7e12d-708">CEP_AzureEmulatorStorageAccountFilter</span></span>

<span data-ttu-id="7e12d-709">Si noti che tecnicamente questo tipo di informazioni riservate identifica queste parole chiave utilizzando un'espressione regolare, non un elenco di parola chiave.</span><span class="sxs-lookup"><span data-stu-id="7e12d-709">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="7e12d-710">Eby8vdM02xNOcqFlqUwJPLlmEtlCDXJ1OUzFT50uSRZ6IFsuFq2UVErCz4I6tq/K1SZFPTOtr/KBHBeksoGMGw = =</span><span class="sxs-lookup"><span data-stu-id="7e12d-710">Eby8vdM02xNOcqFlqUwJPLlmEtlCDXJ1OUzFT50uSRZ6IFsuFq2UVErCz4I6tq/K1SZFPTOtr/KBHBeksoGMGw==</span></span>

#### <a name="cep_commonexamplekeywords"></a><span data-ttu-id="7e12d-711">CEP_CommonExampleKeywords</span><span class="sxs-lookup"><span data-stu-id="7e12d-711">CEP_CommonExampleKeywords</span></span>

<span data-ttu-id="7e12d-712">Si noti che tecnicamente questo tipo di informazioni riservate identifica queste parole chiave utilizzando un'espressione regolare, non un elenco di parola chiave.</span><span class="sxs-lookup"><span data-stu-id="7e12d-712">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="7e12d-713">contoso</span><span class="sxs-lookup"><span data-stu-id="7e12d-713">contoso</span></span>
- <span data-ttu-id="7e12d-714">Fabrikam</span><span class="sxs-lookup"><span data-stu-id="7e12d-714">fabrikam</span></span>
- <span data-ttu-id="7e12d-715">Northwind</span><span class="sxs-lookup"><span data-stu-id="7e12d-715">northwind</span></span>
- <span data-ttu-id="7e12d-716">sandbox</span><span class="sxs-lookup"><span data-stu-id="7e12d-716">sandbox</span></span>
- <span data-ttu-id="7e12d-717">OneBox</span><span class="sxs-lookup"><span data-stu-id="7e12d-717">onebox</span></span>
- <span data-ttu-id="7e12d-718">localhost</span><span class="sxs-lookup"><span data-stu-id="7e12d-718">localhost</span></span>
- <span data-ttu-id="7e12d-719">127.0.0.1</span><span class="sxs-lookup"><span data-stu-id="7e12d-719">127.0.0.1</span></span>
- <span data-ttu-id="7e12d-720">testacs.</span><span class="sxs-lookup"><span data-stu-id="7e12d-720">testacs.</span></span><!--no-hyperlink--><span data-ttu-id="7e12d-721">com</span><span class="sxs-lookup"><span data-stu-id="7e12d-721">com</span></span>
- <span data-ttu-id="7e12d-722">s-int.</span><span class="sxs-lookup"><span data-stu-id="7e12d-722">s-int.</span></span><!--no-hyperlink--><span data-ttu-id="7e12d-723">NET</span><span class="sxs-lookup"><span data-stu-id="7e12d-723">net</span></span>

## <a name="azure-storage-account-key-generic"></a><span data-ttu-id="7e12d-724">Chiave dell'account di archiviazione di Azure (generico)</span><span class="sxs-lookup"><span data-stu-id="7e12d-724">Azure Storage Account Key (Generic)</span></span>

### <a name="format"></a><span data-ttu-id="7e12d-725">Formato</span><span class="sxs-lookup"><span data-stu-id="7e12d-725">Format</span></span>

<span data-ttu-id="7e12d-726">Qualsiasi combinazione di 86 lettere maiuscole e minuscole, cifre, barra (/) o segno più (+), preceduto o seguito dai caratteri delineati nel modello seguente.</span><span class="sxs-lookup"><span data-stu-id="7e12d-726">Any combination of 86 lower- or uppercase letters, digits, the forward slash (/), or plus sign (+), preceded or followed by the characters outlined in the pattern below.</span></span>

### <a name="pattern"></a><span data-ttu-id="7e12d-727">Modello</span><span class="sxs-lookup"><span data-stu-id="7e12d-727">Pattern</span></span>

- <span data-ttu-id="7e12d-728">0-1 del simbolo maggiore di (>), apostrofo ('), segno di uguale (=), virgolette (") o segno numerico (#)</span><span class="sxs-lookup"><span data-stu-id="7e12d-728">0-1 of the greater than symbol (>), apostrophe ('), equal sign (=), quotation mark ("), or number sign (#)</span></span>
- <span data-ttu-id="7e12d-729">Qualsiasi combinazione di 86 caratteri che sono lettere maiuscole o minuscole, cifre, barra (/) o segno più (+)</span><span class="sxs-lookup"><span data-stu-id="7e12d-729">Any combination of 86 characters that are lower- or uppercase letters, digits, the forward slash (/), or plus sign (+)</span></span>
- <span data-ttu-id="7e12d-730">Due segni uguali (=)</span><span class="sxs-lookup"><span data-stu-id="7e12d-730">Two equal signs (=)</span></span>


### <a name="checksum"></a><span data-ttu-id="7e12d-731">Checksum</span><span class="sxs-lookup"><span data-stu-id="7e12d-731">Checksum</span></span>

<span data-ttu-id="7e12d-732">No</span><span class="sxs-lookup"><span data-stu-id="7e12d-732">No</span></span>

### <a name="definition"></a><span data-ttu-id="7e12d-733">Definizione</span><span class="sxs-lookup"><span data-stu-id="7e12d-733">Definition</span></span>

<span data-ttu-id="7e12d-734">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="7e12d-734">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="7e12d-735">L'espressione regolare CEP_Regex_AzureStorageAccountKeyGeneric trova il contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="7e12d-735">The regular expression CEP_Regex_AzureStorageAccountKeyGeneric finds content that matches the pattern.</span></span>

```xml
<!--Azure Storage Account Key (Generic)-->
<Entity id="7ff41bd0-5419-4523-91d6-383b3a37f084" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_AzureStorageAccountKeyGeneric" />
  </Pattern>
</Entity>
```

## <a name="belgium-national-number"></a><span data-ttu-id="7e12d-736">Belgio - Numero nazionale</span><span class="sxs-lookup"><span data-stu-id="7e12d-736">Belgium National Number</span></span>

### <a name="format"></a><span data-ttu-id="7e12d-737">Formato</span><span class="sxs-lookup"><span data-stu-id="7e12d-737">Format</span></span>

<span data-ttu-id="7e12d-738">11 cifre più delimitatori</span><span class="sxs-lookup"><span data-stu-id="7e12d-738">11 digits plus delimiters</span></span>

### <a name="pattern"></a><span data-ttu-id="7e12d-739">Modello</span><span class="sxs-lookup"><span data-stu-id="7e12d-739">Pattern</span></span>

<span data-ttu-id="7e12d-740">11 cifre più delimitatori:</span><span class="sxs-lookup"><span data-stu-id="7e12d-740">11 digits plus delimiters:</span></span>
- <span data-ttu-id="7e12d-741">Sei cifre e due punti nel formato AA.MM.GG per data di nascita </span><span class="sxs-lookup"><span data-stu-id="7e12d-741">Six digits and two periods in the format YY.MM.DD for date of birth</span></span> 
- <span data-ttu-id="7e12d-742">Una lineetta</span><span class="sxs-lookup"><span data-stu-id="7e12d-742">A hyphen</span></span> 
- <span data-ttu-id="7e12d-743">Tre cifre sequenziali (dispari sia per uomini che per donne) </span><span class="sxs-lookup"><span data-stu-id="7e12d-743">Three sequential digits (odd for males, even for females)</span></span> 
- <span data-ttu-id="7e12d-744">Un punto</span><span class="sxs-lookup"><span data-stu-id="7e12d-744">A period</span></span> 
- <span data-ttu-id="7e12d-745">Due cifre, ovvero una cifra di controllo</span><span class="sxs-lookup"><span data-stu-id="7e12d-745">Two digits that are a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="7e12d-746">Checksum</span><span class="sxs-lookup"><span data-stu-id="7e12d-746">Checksum</span></span>

<span data-ttu-id="7e12d-747">Sì</span><span class="sxs-lookup"><span data-stu-id="7e12d-747">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="7e12d-748">Definizione</span><span class="sxs-lookup"><span data-stu-id="7e12d-748">Definition</span></span>

<span data-ttu-id="7e12d-749">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="7e12d-749">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="7e12d-750">La funzione Func_belgium_national_number trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="7e12d-750">The function Func_belgium_national_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="7e12d-751">Viene trovata una parola chiave da Keyword_belgium_national_number.</span><span class="sxs-lookup"><span data-stu-id="7e12d-751">A keyword from Keyword_belgium_national_number is found.</span></span>
- <span data-ttu-id="7e12d-752">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="7e12d-752">The checksum passes.</span></span>

```xml
<!-- Belgium National Number -->
  <Entity id="fb969c9e-0fd1-4b18-8091-a2123c5e6a54" recommendedConfidence="75" patternsProximity="300">
   <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_belgium_national_number"/>
     <Match idRef="Keyword_belgium_national_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="7e12d-753">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="7e12d-753">Keywords</span></span>

#### <a name="keyword_belgium_national_number"></a><span data-ttu-id="7e12d-754">Keyword_belgium_national_number</span><span class="sxs-lookup"><span data-stu-id="7e12d-754">Keyword_belgium_national_number</span></span>

- <span data-ttu-id="7e12d-755">Identità</span><span class="sxs-lookup"><span data-stu-id="7e12d-755">Identity</span></span>
- <span data-ttu-id="7e12d-756">Registrazione</span><span class="sxs-lookup"><span data-stu-id="7e12d-756">Registration</span></span>
- <span data-ttu-id="7e12d-757">Identificazione</span><span class="sxs-lookup"><span data-stu-id="7e12d-757">Identification</span></span> 
- <span data-ttu-id="7e12d-758">ID</span><span class="sxs-lookup"><span data-stu-id="7e12d-758">ID</span></span> 
- <span data-ttu-id="7e12d-759">Identiteitskaart</span><span class="sxs-lookup"><span data-stu-id="7e12d-759">Identiteitskaart</span></span>
- <span data-ttu-id="7e12d-760">Registratie nummer</span><span class="sxs-lookup"><span data-stu-id="7e12d-760">Registratie nummer</span></span> 
- <span data-ttu-id="7e12d-761">Identificatie nummer</span><span class="sxs-lookup"><span data-stu-id="7e12d-761">Identificatie nummer</span></span> 
- <span data-ttu-id="7e12d-762">Identiteit</span><span class="sxs-lookup"><span data-stu-id="7e12d-762">Identiteit</span></span>
- <span data-ttu-id="7e12d-763">Registratie</span><span class="sxs-lookup"><span data-stu-id="7e12d-763">Registratie</span></span>
- <span data-ttu-id="7e12d-764">Identificatie</span><span class="sxs-lookup"><span data-stu-id="7e12d-764">Identificatie</span></span> 
- <span data-ttu-id="7e12d-765">Carte d’identité</span><span class="sxs-lookup"><span data-stu-id="7e12d-765">Carte d’identité</span></span> 
- <span data-ttu-id="7e12d-766">numéro d'immatriculation</span><span class="sxs-lookup"><span data-stu-id="7e12d-766">numéro d'immatriculation</span></span>
- <span data-ttu-id="7e12d-767">numéro d'identification</span><span class="sxs-lookup"><span data-stu-id="7e12d-767">numéro d'identification</span></span>
- <span data-ttu-id="7e12d-768">identité</span><span class="sxs-lookup"><span data-stu-id="7e12d-768">identité</span></span> 
- <span data-ttu-id="7e12d-769">iscrizione</span><span class="sxs-lookup"><span data-stu-id="7e12d-769">inscription</span></span> 
- <span data-ttu-id="7e12d-770">Identifikation</span><span class="sxs-lookup"><span data-stu-id="7e12d-770">Identifikation</span></span>
- <span data-ttu-id="7e12d-771">Identifizierung</span><span class="sxs-lookup"><span data-stu-id="7e12d-771">Identifizierung</span></span>
- <span data-ttu-id="7e12d-772">Identifikationsnummer</span><span class="sxs-lookup"><span data-stu-id="7e12d-772">Identifikationsnummer</span></span>
- <span data-ttu-id="7e12d-773">Personalausweis</span><span class="sxs-lookup"><span data-stu-id="7e12d-773">Personalausweis</span></span>
- <span data-ttu-id="7e12d-774">Registrierung</span><span class="sxs-lookup"><span data-stu-id="7e12d-774">Registrierung</span></span>
- <span data-ttu-id="7e12d-775">Registrationsnummer</span><span class="sxs-lookup"><span data-stu-id="7e12d-775">Registrationsnummer</span></span>

   
## <a name="brazil-cpf-number"></a><span data-ttu-id="7e12d-776">Numero CPF Brasile</span><span class="sxs-lookup"><span data-stu-id="7e12d-776">Brazil CPF Number</span></span>

### <a name="format"></a><span data-ttu-id="7e12d-777">Formato</span><span class="sxs-lookup"><span data-stu-id="7e12d-777">Format</span></span>

<span data-ttu-id="7e12d-778">11 cifre che includono una cifra di controllo e possono essere formattate o non formattate</span><span class="sxs-lookup"><span data-stu-id="7e12d-778">11 digits that include a check digit and can be formatted or unformatted</span></span>

### <a name="pattern"></a><span data-ttu-id="7e12d-779">Modello</span><span class="sxs-lookup"><span data-stu-id="7e12d-779">Pattern</span></span>

<span data-ttu-id="7e12d-780">Formattato</span><span class="sxs-lookup"><span data-stu-id="7e12d-780">Formatted:</span></span>
- <span data-ttu-id="7e12d-781">Tre cifre</span><span class="sxs-lookup"><span data-stu-id="7e12d-781">Three digits</span></span> 
- <span data-ttu-id="7e12d-782">Un punto </span><span class="sxs-lookup"><span data-stu-id="7e12d-782">A period</span></span> 
- <span data-ttu-id="7e12d-783">Tre cifre</span><span class="sxs-lookup"><span data-stu-id="7e12d-783">Three digits</span></span> 
- <span data-ttu-id="7e12d-784">Un punto </span><span class="sxs-lookup"><span data-stu-id="7e12d-784">A period</span></span> 
- <span data-ttu-id="7e12d-785">Tre cifre</span><span class="sxs-lookup"><span data-stu-id="7e12d-785">Three digits</span></span> 
- <span data-ttu-id="7e12d-786">Una lineetta</span><span class="sxs-lookup"><span data-stu-id="7e12d-786">A hyphen</span></span> 
- <span data-ttu-id="7e12d-787">Due cifre, ovvero le cifre di controllo</span><span class="sxs-lookup"><span data-stu-id="7e12d-787">Two digits which are check digits</span></span>

<span data-ttu-id="7e12d-788">Formattato</span><span class="sxs-lookup"><span data-stu-id="7e12d-788">Unformatted:</span></span>
- <span data-ttu-id="7e12d-789">11 cifre dove le ultime due sono cifre di controllo</span><span class="sxs-lookup"><span data-stu-id="7e12d-789">11 digits where the last two digits are check digits</span></span>

### <a name="checksum"></a><span data-ttu-id="7e12d-790">Checksum</span><span class="sxs-lookup"><span data-stu-id="7e12d-790">Checksum</span></span>

<span data-ttu-id="7e12d-791">Sì</span><span class="sxs-lookup"><span data-stu-id="7e12d-791">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="7e12d-792">Definizione</span><span class="sxs-lookup"><span data-stu-id="7e12d-792">Definition</span></span>

<span data-ttu-id="7e12d-793">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="7e12d-793">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="7e12d-794">La funzione Func_brazil_cpf trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="7e12d-794">The function Func_brazil_cpf finds content that matches the pattern.</span></span>
- <span data-ttu-id="7e12d-795">Viene trovata una parola chiave da Keyword_brazil_cpf.</span><span class="sxs-lookup"><span data-stu-id="7e12d-795">A keyword from Keyword_brazil_cpf is found.</span></span>
- <span data-ttu-id="7e12d-796">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="7e12d-796">The checksum passes.</span></span>

<span data-ttu-id="7e12d-797">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="7e12d-797">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="7e12d-798">La funzione Func_brazil_cpf trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="7e12d-798">The function Func_brazil_cpf finds content that matches the pattern.</span></span>
- <span data-ttu-id="7e12d-799">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="7e12d-799">The checksum passes.</span></span>

```xml
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

### <a name="keywords"></a><span data-ttu-id="7e12d-800">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="7e12d-800">Keywords</span></span>

#### <a name="keyword_brazil_cpf"></a><span data-ttu-id="7e12d-801">Keyword_brazil_cpf</span><span class="sxs-lookup"><span data-stu-id="7e12d-801">Keyword_brazil_cpf</span></span>

- <span data-ttu-id="7e12d-802">CPF</span><span class="sxs-lookup"><span data-stu-id="7e12d-802">CPF</span></span>
- <span data-ttu-id="7e12d-803">Identificazione</span><span class="sxs-lookup"><span data-stu-id="7e12d-803">Identification</span></span>
- <span data-ttu-id="7e12d-804">Registrazione</span><span class="sxs-lookup"><span data-stu-id="7e12d-804">Registration</span></span>
- <span data-ttu-id="7e12d-805">Entrate</span><span class="sxs-lookup"><span data-stu-id="7e12d-805">Revenue</span></span>
- <span data-ttu-id="7e12d-806">Cadastro de Pessoas Físicas</span><span class="sxs-lookup"><span data-stu-id="7e12d-806">Cadastro de Pessoas Físicas</span></span> 
- <span data-ttu-id="7e12d-807">Imposto</span><span class="sxs-lookup"><span data-stu-id="7e12d-807">Imposto</span></span> 
- <span data-ttu-id="7e12d-808">Identificação</span><span class="sxs-lookup"><span data-stu-id="7e12d-808">Identificação</span></span> 
- <span data-ttu-id="7e12d-809">Inscrição</span><span class="sxs-lookup"><span data-stu-id="7e12d-809">Inscrição</span></span> 
- <span data-ttu-id="7e12d-810">Receita</span><span class="sxs-lookup"><span data-stu-id="7e12d-810">Receita</span></span> 
   
## <a name="brazil-legal-entity-number-cnpj"></a><span data-ttu-id="7e12d-811">Brasile - Codice fiscale persone giuridiche (CNPJ)</span><span class="sxs-lookup"><span data-stu-id="7e12d-811">Brazil Legal Entity Number (CNPJ)</span></span>

### <a name="format"></a><span data-ttu-id="7e12d-812">Formato</span><span class="sxs-lookup"><span data-stu-id="7e12d-812">Format</span></span>

<span data-ttu-id="7e12d-813">14 cifre che includono il numero di registrazione, il codice della filiale, le cifre di controllo e i delimitatori</span><span class="sxs-lookup"><span data-stu-id="7e12d-813">14 digits that include a registration number, branch number, and check digits, plus delimiters</span></span>

### <a name="pattern"></a><span data-ttu-id="7e12d-814">Modello</span><span class="sxs-lookup"><span data-stu-id="7e12d-814">Pattern</span></span>
<span data-ttu-id="7e12d-815">14 cifre più delimitatori:</span><span class="sxs-lookup"><span data-stu-id="7e12d-815">14 digits, plus delimiters:</span></span>
- <span data-ttu-id="7e12d-816">Due cifre</span><span class="sxs-lookup"><span data-stu-id="7e12d-816">Two digits</span></span> 
- <span data-ttu-id="7e12d-817">Un punto </span><span class="sxs-lookup"><span data-stu-id="7e12d-817">A period</span></span> 
- <span data-ttu-id="7e12d-818">Tre cifre</span><span class="sxs-lookup"><span data-stu-id="7e12d-818">Three digits</span></span> 
- <span data-ttu-id="7e12d-819">Un punto </span><span class="sxs-lookup"><span data-stu-id="7e12d-819">A period</span></span> 
- <span data-ttu-id="7e12d-820">Tre cifre (le prime otto sono il numero di registrazione) </span><span class="sxs-lookup"><span data-stu-id="7e12d-820">Three digits (these first eight digits are the registration number)</span></span> 
- <span data-ttu-id="7e12d-821">Una barra</span><span class="sxs-lookup"><span data-stu-id="7e12d-821">A forward slash</span></span> 
- <span data-ttu-id="7e12d-822">Numero del ramo a quattro cifre </span><span class="sxs-lookup"><span data-stu-id="7e12d-822">Four-digit branch number</span></span> 
- <span data-ttu-id="7e12d-823">Una lineetta</span><span class="sxs-lookup"><span data-stu-id="7e12d-823">A hyphen</span></span> 
- <span data-ttu-id="7e12d-824">Due cifre, ovvero le cifre di controllo</span><span class="sxs-lookup"><span data-stu-id="7e12d-824">Two digits which are check digits</span></span>

### <a name="checksum"></a><span data-ttu-id="7e12d-825">Checksum</span><span class="sxs-lookup"><span data-stu-id="7e12d-825">Checksum</span></span>

<span data-ttu-id="7e12d-826">Sì</span><span class="sxs-lookup"><span data-stu-id="7e12d-826">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="7e12d-827">Definizione</span><span class="sxs-lookup"><span data-stu-id="7e12d-827">Definition</span></span>

<span data-ttu-id="7e12d-828">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="7e12d-828">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="7e12d-829">La funzione Func_brazil_cnpj trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="7e12d-829">The function Func_brazil_cnpj finds content that matches the pattern.</span></span>
- <span data-ttu-id="7e12d-830">Viene trovata una parola chiave da Keyword_brazil_cnpj.</span><span class="sxs-lookup"><span data-stu-id="7e12d-830">A keyword from Keyword_brazil_cnpj is found.</span></span>
- <span data-ttu-id="7e12d-831">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="7e12d-831">The checksum passes.</span></span>

<span data-ttu-id="7e12d-832">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="7e12d-832">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="7e12d-833">La funzione Func_brazil_cnpj trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="7e12d-833">The function Func_brazil_cnpj finds content that matches the pattern.</span></span>
- <span data-ttu-id="7e12d-834">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="7e12d-834">The checksum passes.</span></span>

```xml
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

### <a name="keywords"></a><span data-ttu-id="7e12d-835">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="7e12d-835">Keywords</span></span>

#### <a name="keyword_brazil_cnpj"></a><span data-ttu-id="7e12d-836">Keyword_brazil_cnpj</span><span class="sxs-lookup"><span data-stu-id="7e12d-836">Keyword_brazil_cnpj</span></span>

- <span data-ttu-id="7e12d-837">CNPJ</span><span class="sxs-lookup"><span data-stu-id="7e12d-837">CNPJ</span></span> 
- <span data-ttu-id="7e12d-838">CNPJ/MF</span><span class="sxs-lookup"><span data-stu-id="7e12d-838">CNPJ/MF</span></span> 
- <span data-ttu-id="7e12d-839">CNPJ-MF</span><span class="sxs-lookup"><span data-stu-id="7e12d-839">CNPJ-MF</span></span> 
- <span data-ttu-id="7e12d-840">Codice fiscale persone giuridiche</span><span class="sxs-lookup"><span data-stu-id="7e12d-840">National Registry of Legal Entities</span></span> 
- <span data-ttu-id="7e12d-841">Registro contribuenti</span><span class="sxs-lookup"><span data-stu-id="7e12d-841">Taxpayers Registry</span></span> 
- <span data-ttu-id="7e12d-842">Persona giuridica</span><span class="sxs-lookup"><span data-stu-id="7e12d-842">Legal entity</span></span> 
- <span data-ttu-id="7e12d-843">Persone giuridiche</span><span class="sxs-lookup"><span data-stu-id="7e12d-843">Legal entities</span></span> 
- <span data-ttu-id="7e12d-844">Stato della registrazione</span><span class="sxs-lookup"><span data-stu-id="7e12d-844">Registration Status</span></span> 
- <span data-ttu-id="7e12d-845">Business</span><span class="sxs-lookup"><span data-stu-id="7e12d-845">Business</span></span> 
- <span data-ttu-id="7e12d-846">Company</span><span class="sxs-lookup"><span data-stu-id="7e12d-846">Company</span></span>
- <span data-ttu-id="7e12d-847">CNPJ</span><span class="sxs-lookup"><span data-stu-id="7e12d-847">CNPJ</span></span> 
- <span data-ttu-id="7e12d-848">Cadastro Nacional da Pessoa Jurídica</span><span class="sxs-lookup"><span data-stu-id="7e12d-848">Cadastro Nacional da Pessoa Jurídica</span></span> 
- <span data-ttu-id="7e12d-849">Cadastro Geral de Contribuintes</span><span class="sxs-lookup"><span data-stu-id="7e12d-849">Cadastro Geral de Contribuintes</span></span> 
- <span data-ttu-id="7e12d-850">CGC</span><span class="sxs-lookup"><span data-stu-id="7e12d-850">CGC</span></span> 
- <span data-ttu-id="7e12d-851">Pessoa jurídica</span><span class="sxs-lookup"><span data-stu-id="7e12d-851">Pessoa jurídica</span></span> 
- <span data-ttu-id="7e12d-852">Pessoas jurídicas</span><span class="sxs-lookup"><span data-stu-id="7e12d-852">Pessoas jurídicas</span></span> 
- <span data-ttu-id="7e12d-853">Situação cadastral</span><span class="sxs-lookup"><span data-stu-id="7e12d-853">Situação cadastral</span></span> 
- <span data-ttu-id="7e12d-854">Inscrição</span><span class="sxs-lookup"><span data-stu-id="7e12d-854">Inscrição</span></span> 
- <span data-ttu-id="7e12d-855">Empresa</span><span class="sxs-lookup"><span data-stu-id="7e12d-855">Empresa</span></span> 
   
## <a name="brazil-national-id-card-rg"></a><span data-ttu-id="7e12d-856">	Carta d'identità (Brasile) (RG)</span><span class="sxs-lookup"><span data-stu-id="7e12d-856">Brazil National ID Card (RG)</span></span>

### <a name="format"></a><span data-ttu-id="7e12d-857">Formato</span><span class="sxs-lookup"><span data-stu-id="7e12d-857">Format</span></span>

<span data-ttu-id="7e12d-858">Registro Geral (formato precedente): nove cifre</span><span class="sxs-lookup"><span data-stu-id="7e12d-858">Registro Geral (old format): Nine digits</span></span>

<span data-ttu-id="7e12d-859">Registro de Identidade (RIC) (nuovo formato): 11 cifre</span><span class="sxs-lookup"><span data-stu-id="7e12d-859">Registro de Identidade (RIC) (new format): 11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="7e12d-860">Modello</span><span class="sxs-lookup"><span data-stu-id="7e12d-860">Pattern</span></span>

<span data-ttu-id="7e12d-861">Registro Geral (formato precedente):</span><span class="sxs-lookup"><span data-stu-id="7e12d-861">Registro Geral (old format):</span></span>
- <span data-ttu-id="7e12d-862">Due cifre</span><span class="sxs-lookup"><span data-stu-id="7e12d-862">Two digits</span></span> 
- <span data-ttu-id="7e12d-863">Un punto </span><span class="sxs-lookup"><span data-stu-id="7e12d-863">A period</span></span> 
- <span data-ttu-id="7e12d-864">Tre cifre</span><span class="sxs-lookup"><span data-stu-id="7e12d-864">Three digits</span></span> 
- <span data-ttu-id="7e12d-865">Un punto </span><span class="sxs-lookup"><span data-stu-id="7e12d-865">A period</span></span> 
- <span data-ttu-id="7e12d-866">Tre cifre</span><span class="sxs-lookup"><span data-stu-id="7e12d-866">Three digits</span></span> 
- <span data-ttu-id="7e12d-867">Una lineetta</span><span class="sxs-lookup"><span data-stu-id="7e12d-867">A hyphen</span></span> 
- <span data-ttu-id="7e12d-868">Una cifra, ovvero una cifra di controllo</span><span class="sxs-lookup"><span data-stu-id="7e12d-868">One digit which is a check digit</span></span>

<span data-ttu-id="7e12d-869">Registro de Identidade (RIC) (nuovo formato):</span><span class="sxs-lookup"><span data-stu-id="7e12d-869">Registro de Identidade (RIC) (new format):</span></span>
- <span data-ttu-id="7e12d-870">10 cifre</span><span class="sxs-lookup"><span data-stu-id="7e12d-870">10 digits</span></span> 
- <span data-ttu-id="7e12d-871">Una lineetta</span><span class="sxs-lookup"><span data-stu-id="7e12d-871">A hyphen</span></span> 
- <span data-ttu-id="7e12d-872">Una cifra, ovvero una cifra di controllo</span><span class="sxs-lookup"><span data-stu-id="7e12d-872">One digit which is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="7e12d-873">Checksum</span><span class="sxs-lookup"><span data-stu-id="7e12d-873">Checksum</span></span>

<span data-ttu-id="7e12d-874">Sì</span><span class="sxs-lookup"><span data-stu-id="7e12d-874">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="7e12d-875">Definizione</span><span class="sxs-lookup"><span data-stu-id="7e12d-875">Definition</span></span>

<span data-ttu-id="7e12d-876">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="7e12d-876">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="7e12d-877">La funzione Func_brazil_rg trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="7e12d-877">The function Func_brazil_rg finds content that matches the pattern.</span></span>
- <span data-ttu-id="7e12d-878">Viene trovata una parola chiave da Keyword_brazil_rg.</span><span class="sxs-lookup"><span data-stu-id="7e12d-878">A keyword from Keyword_brazil_rg is found.</span></span>
- <span data-ttu-id="7e12d-879">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="7e12d-879">The checksum passes.</span></span>

<span data-ttu-id="7e12d-880">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="7e12d-880">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="7e12d-881">La funzione Func_brazil_rg trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="7e12d-881">The function Func_brazil_rg finds content that matches the pattern.</span></span>
- <span data-ttu-id="7e12d-882">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="7e12d-882">The checksum passes.</span></span>

```xml
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

### <a name="keywords"></a><span data-ttu-id="7e12d-883">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="7e12d-883">Keywords</span></span>

#### <a name="keyword_brazil_rg"></a><span data-ttu-id="7e12d-884">Keyword_brazil_rg</span><span class="sxs-lookup"><span data-stu-id="7e12d-884">Keyword_brazil_rg</span></span>

<span data-ttu-id="7e12d-885">Cédula de Identidade identità Card National ID número de rregistro Registro de Iidentidade registro Geral RG (questa parola chiave è distinzione tra maiuscole e minuscole) RIC (questa parola chiave è distinzione tra maiuscole e minuscole)</span><span class="sxs-lookup"><span data-stu-id="7e12d-885">Cédula de identidade identity card national id número de rregistro registro de Iidentidade registro geral RG (this keyword is case sensitive) RIC (this keyword is case sensitive)</span></span> 
   
## <a name="canada-bank-account-number"></a><span data-ttu-id="7e12d-886">Canada - Numero di conto bancario</span><span class="sxs-lookup"><span data-stu-id="7e12d-886">Canada Bank Account Number</span></span>

### <a name="format"></a><span data-ttu-id="7e12d-887">Formato</span><span class="sxs-lookup"><span data-stu-id="7e12d-887">Format</span></span>

<span data-ttu-id="7e12d-888">7 o 12 cifre</span><span class="sxs-lookup"><span data-stu-id="7e12d-888">Seven or twelve digits</span></span>

### <a name="pattern"></a><span data-ttu-id="7e12d-889">Modello</span><span class="sxs-lookup"><span data-stu-id="7e12d-889">Pattern</span></span>

<span data-ttu-id="7e12d-890">Un numero di conto corrente canadese comprende 7 o 12 cifre.</span><span class="sxs-lookup"><span data-stu-id="7e12d-890">A Canada Bank Account Number is seven or twelve digits.</span></span>

<span data-ttu-id="7e12d-891">Un numero di transito bancario canadese comprende:</span><span class="sxs-lookup"><span data-stu-id="7e12d-891">A Canada bank account transit number is:</span></span>
- <span data-ttu-id="7e12d-892">Cinque cifre</span><span class="sxs-lookup"><span data-stu-id="7e12d-892">Five digits</span></span> 
- <span data-ttu-id="7e12d-893">Una lineetta</span><span class="sxs-lookup"><span data-stu-id="7e12d-893">A hyphen</span></span> 
- <span data-ttu-id="7e12d-894">Tre cifre o</span><span class="sxs-lookup"><span data-stu-id="7e12d-894">Three digits OR</span></span>
- <span data-ttu-id="7e12d-895">Uno zero "0"</span><span class="sxs-lookup"><span data-stu-id="7e12d-895">A zero "0"</span></span> 
- <span data-ttu-id="7e12d-896">Otto cifre</span><span class="sxs-lookup"><span data-stu-id="7e12d-896">Eight digits</span></span>

### <a name="checksum"></a><span data-ttu-id="7e12d-897">Checksum</span><span class="sxs-lookup"><span data-stu-id="7e12d-897">Checksum</span></span>

<span data-ttu-id="7e12d-898">No</span><span class="sxs-lookup"><span data-stu-id="7e12d-898">No</span></span>

### <a name="definition"></a><span data-ttu-id="7e12d-899">Definizione</span><span class="sxs-lookup"><span data-stu-id="7e12d-899">Definition</span></span>

<span data-ttu-id="7e12d-900">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="7e12d-900">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="7e12d-901">L'espressione regolare Regex_canada_bank_account_number restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="7e12d-901">The regular expression Regex_canada_bank_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="7e12d-902">Viene trovata una parola chiave da Keyword_canada_bank_account_number.</span><span class="sxs-lookup"><span data-stu-id="7e12d-902">A keyword from Keyword_canada_bank_account_number is found.</span></span>
- <span data-ttu-id="7e12d-903">L'espressione regolare Regex_canada_bank_account_transit_number restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="7e12d-903">The regular expression Regex_canada_bank_account_transit_number finds content that matches the pattern.</span></span>

<span data-ttu-id="7e12d-904">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="7e12d-904">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="7e12d-905">L'espressione regolare Regex_canada_bank_account_number restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="7e12d-905">The regular expression Regex_canada_bank_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="7e12d-906">Viene trovata una parola chiave da Keyword_canada_bank_account_number.</span><span class="sxs-lookup"><span data-stu-id="7e12d-906">A keyword from Keyword_canada_bank_account_number is found.</span></span>

```xml
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

### <a name="keywords"></a><span data-ttu-id="7e12d-907">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="7e12d-907">Keywords</span></span>

#### <a name="keyword_canada_bank_account_number"></a><span data-ttu-id="7e12d-908">Keyword_canada_bank_account_number</span><span class="sxs-lookup"><span data-stu-id="7e12d-908">Keyword_canada_bank_account_number</span></span>

- <span data-ttu-id="7e12d-909">canada savings bonds</span><span class="sxs-lookup"><span data-stu-id="7e12d-909">canada savings bonds</span></span>
- <span data-ttu-id="7e12d-910">canada revenue agency</span><span class="sxs-lookup"><span data-stu-id="7e12d-910">canada revenue agency</span></span>
- <span data-ttu-id="7e12d-911">canadian financial institution</span><span class="sxs-lookup"><span data-stu-id="7e12d-911">canadian financial institution</span></span>
- <span data-ttu-id="7e12d-912">direct deposit form</span><span class="sxs-lookup"><span data-stu-id="7e12d-912">direct deposit form</span></span>
- <span data-ttu-id="7e12d-913">canadian citizen</span><span class="sxs-lookup"><span data-stu-id="7e12d-913">canadian citizen</span></span>
- <span data-ttu-id="7e12d-914">legal representative</span><span class="sxs-lookup"><span data-stu-id="7e12d-914">legal representative</span></span>
- <span data-ttu-id="7e12d-915">notary public</span><span class="sxs-lookup"><span data-stu-id="7e12d-915">notary public</span></span>
- <span data-ttu-id="7e12d-916">commissioner for oaths</span><span class="sxs-lookup"><span data-stu-id="7e12d-916">commissioner for oaths</span></span>
- <span data-ttu-id="7e12d-917">child care benefit</span><span class="sxs-lookup"><span data-stu-id="7e12d-917">child care benefit</span></span>
- <span data-ttu-id="7e12d-918">universal child care</span><span class="sxs-lookup"><span data-stu-id="7e12d-918">universal child care</span></span>
- <span data-ttu-id="7e12d-919">canada child tax benefit</span><span class="sxs-lookup"><span data-stu-id="7e12d-919">canada child tax benefit</span></span>
- <span data-ttu-id="7e12d-920">income tax benefit</span><span class="sxs-lookup"><span data-stu-id="7e12d-920">income tax benefit</span></span>
- <span data-ttu-id="7e12d-921">harmonized sales tax</span><span class="sxs-lookup"><span data-stu-id="7e12d-921">harmonized sales tax</span></span>
- <span data-ttu-id="7e12d-922">social insurance number</span><span class="sxs-lookup"><span data-stu-id="7e12d-922">social insurance number</span></span>
- <span data-ttu-id="7e12d-923">income tax refund</span><span class="sxs-lookup"><span data-stu-id="7e12d-923">income tax refund</span></span>
- <span data-ttu-id="7e12d-924">child tax benefit</span><span class="sxs-lookup"><span data-stu-id="7e12d-924">child tax benefit</span></span>
- <span data-ttu-id="7e12d-925">territorial payments</span><span class="sxs-lookup"><span data-stu-id="7e12d-925">territorial payments</span></span>
- <span data-ttu-id="7e12d-926">institution number</span><span class="sxs-lookup"><span data-stu-id="7e12d-926">institution number</span></span>
- <span data-ttu-id="7e12d-927">deposit request</span><span class="sxs-lookup"><span data-stu-id="7e12d-927">deposit request</span></span>
- <span data-ttu-id="7e12d-928">banking information</span><span class="sxs-lookup"><span data-stu-id="7e12d-928">banking information</span></span>
- <span data-ttu-id="7e12d-929">direct deposit</span><span class="sxs-lookup"><span data-stu-id="7e12d-929">direct deposit</span></span>
   
## <a name="canada-drivers-license-number"></a><span data-ttu-id="7e12d-930">Canada - Numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="7e12d-930">Canada Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="7e12d-931">Formato</span><span class="sxs-lookup"><span data-stu-id="7e12d-931">Format</span></span>

<span data-ttu-id="7e12d-932">Varia in base alla provincia</span><span class="sxs-lookup"><span data-stu-id="7e12d-932">Varies by province</span></span>

### <a name="pattern"></a><span data-ttu-id="7e12d-933">Modello</span><span class="sxs-lookup"><span data-stu-id="7e12d-933">Pattern</span></span>

<span data-ttu-id="7e12d-934">Vari modelli per Alberta, Columbia Britannica, Manitoba, Nuovo Brunswick, Terranova e Labrador, Nuova Scozia, Ontario, Isola del Principe Edoardo, Quebec e Saskatchewan</span><span class="sxs-lookup"><span data-stu-id="7e12d-934">Various patterns covering Alberta, British Columbia, Manitoba, New Brunswick, Newfoundland/Labrador, Nova Scotia, Ontario, Prince Edward Island, Quebec, and Saskatchewan</span></span>

### <a name="checksum"></a><span data-ttu-id="7e12d-935">Checksum</span><span class="sxs-lookup"><span data-stu-id="7e12d-935">Checksum</span></span>

<span data-ttu-id="7e12d-936">No</span><span class="sxs-lookup"><span data-stu-id="7e12d-936">No</span></span>

### <a name="definition"></a><span data-ttu-id="7e12d-937">Definizione</span><span class="sxs-lookup"><span data-stu-id="7e12d-937">Definition</span></span>

<span data-ttu-id="7e12d-938">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="7e12d-938">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="7e12d-939">La funzione Func_[province_name]_drivers_license_number restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="7e12d-939">The function Func_[province_name]_drivers_license_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="7e12d-940">Viene trovata una parola chiave da Keyword_[province_name]_drivers_license_name.</span><span class="sxs-lookup"><span data-stu-id="7e12d-940">A keyword from Keyword_[province_name]_drivers_license_name is found.</span></span>
- <span data-ttu-id="7e12d-941">Viene trovata una parola chiave da Keyword_canada_drivers_license.</span><span class="sxs-lookup"><span data-stu-id="7e12d-941">A keyword from Keyword_canada_drivers_license is found.</span></span>

```xml
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

### <a name="keywords"></a><span data-ttu-id="7e12d-942">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="7e12d-942">Keywords</span></span>

#### <a name="keyword_province_name_drivers_license_name"></a><span data-ttu-id="7e12d-943">Keyword_[province_name]_drivers_license_name</span><span class="sxs-lookup"><span data-stu-id="7e12d-943">Keyword_[province_name]_drivers_license_name</span></span>

- <span data-ttu-id="7e12d-944">L'abbreviazione della provincia, ad esempio, AB</span><span class="sxs-lookup"><span data-stu-id="7e12d-944">The province abbreviation, for example AB</span></span>
- <span data-ttu-id="7e12d-945">Il nome della provincia, ad esempio, Alberta</span><span class="sxs-lookup"><span data-stu-id="7e12d-945">The province name, for example Alberta</span></span>

#### <a name="keyword_canada_drivers_license"></a><span data-ttu-id="7e12d-946">Keyword_canada_drivers_license</span><span class="sxs-lookup"><span data-stu-id="7e12d-946">Keyword_canada_drivers_license</span></span>

- <span data-ttu-id="7e12d-947">DL</span><span class="sxs-lookup"><span data-stu-id="7e12d-947">DL</span></span>
- <span data-ttu-id="7e12d-948">DLS</span><span class="sxs-lookup"><span data-stu-id="7e12d-948">DLS</span></span>
- <span data-ttu-id="7e12d-949">CDL</span><span class="sxs-lookup"><span data-stu-id="7e12d-949">CDL</span></span>
- <span data-ttu-id="7e12d-950">CDLS</span><span class="sxs-lookup"><span data-stu-id="7e12d-950">CDLS</span></span>
- <span data-ttu-id="7e12d-951">DriverLic</span><span class="sxs-lookup"><span data-stu-id="7e12d-951">DriverLic</span></span>
- <span data-ttu-id="7e12d-952">DriverLics</span><span class="sxs-lookup"><span data-stu-id="7e12d-952">DriverLics</span></span>
- <span data-ttu-id="7e12d-953">DriverLicense</span><span class="sxs-lookup"><span data-stu-id="7e12d-953">DriverLicense</span></span>
- <span data-ttu-id="7e12d-954">DriverLicenses</span><span class="sxs-lookup"><span data-stu-id="7e12d-954">DriverLicenses</span></span>
- <span data-ttu-id="7e12d-955">DriverLicence</span><span class="sxs-lookup"><span data-stu-id="7e12d-955">DriverLicence</span></span>
- <span data-ttu-id="7e12d-956">DriverLicences</span><span class="sxs-lookup"><span data-stu-id="7e12d-956">DriverLicences</span></span>
- <span data-ttu-id="7e12d-957">Driver Lic</span><span class="sxs-lookup"><span data-stu-id="7e12d-957">Driver Lic</span></span>
- <span data-ttu-id="7e12d-958">Driver Lics</span><span class="sxs-lookup"><span data-stu-id="7e12d-958">Driver Lics</span></span>
- <span data-ttu-id="7e12d-959">Driver License</span><span class="sxs-lookup"><span data-stu-id="7e12d-959">Driver License</span></span>
- <span data-ttu-id="7e12d-960">Driver Licenses</span><span class="sxs-lookup"><span data-stu-id="7e12d-960">Driver Licenses</span></span>
- <span data-ttu-id="7e12d-961">Driver Licence</span><span class="sxs-lookup"><span data-stu-id="7e12d-961">Driver Licence</span></span>
- <span data-ttu-id="7e12d-962">Driver Licences</span><span class="sxs-lookup"><span data-stu-id="7e12d-962">Driver Licences</span></span>
- <span data-ttu-id="7e12d-963">DriversLic</span><span class="sxs-lookup"><span data-stu-id="7e12d-963">DriversLic</span></span>
- <span data-ttu-id="7e12d-964">DriversLics</span><span class="sxs-lookup"><span data-stu-id="7e12d-964">DriversLics</span></span>
- <span data-ttu-id="7e12d-965">DriversLicence</span><span class="sxs-lookup"><span data-stu-id="7e12d-965">DriversLicence</span></span>
- <span data-ttu-id="7e12d-966">DriversLicences</span><span class="sxs-lookup"><span data-stu-id="7e12d-966">DriversLicences</span></span>
- <span data-ttu-id="7e12d-967">DriversLicense</span><span class="sxs-lookup"><span data-stu-id="7e12d-967">DriversLicense</span></span>
- <span data-ttu-id="7e12d-968">DriversLicenses</span><span class="sxs-lookup"><span data-stu-id="7e12d-968">DriversLicenses</span></span>
- <span data-ttu-id="7e12d-969">Drivers Lic</span><span class="sxs-lookup"><span data-stu-id="7e12d-969">Drivers Lic</span></span>
- <span data-ttu-id="7e12d-970">Drivers Lics</span><span class="sxs-lookup"><span data-stu-id="7e12d-970">Drivers Lics</span></span>
- <span data-ttu-id="7e12d-971">Drivers License</span><span class="sxs-lookup"><span data-stu-id="7e12d-971">Drivers License</span></span>
- <span data-ttu-id="7e12d-972">Drivers Licenses</span><span class="sxs-lookup"><span data-stu-id="7e12d-972">Drivers Licenses</span></span>
- <span data-ttu-id="7e12d-973">Drivers Licence</span><span class="sxs-lookup"><span data-stu-id="7e12d-973">Drivers Licence</span></span>
- <span data-ttu-id="7e12d-974">Drivers Licences</span><span class="sxs-lookup"><span data-stu-id="7e12d-974">Drivers Licences</span></span>
- <span data-ttu-id="7e12d-975">Driver'Lic</span><span class="sxs-lookup"><span data-stu-id="7e12d-975">Driver'Lic</span></span>
- <span data-ttu-id="7e12d-976">Driver ' LiCS</span><span class="sxs-lookup"><span data-stu-id="7e12d-976">Driver'Lics</span></span>
- <span data-ttu-id="7e12d-977">Driver ' License</span><span class="sxs-lookup"><span data-stu-id="7e12d-977">Driver'License</span></span>
- <span data-ttu-id="7e12d-978">Driver ' licenses</span><span class="sxs-lookup"><span data-stu-id="7e12d-978">Driver'Licenses</span></span>
- <span data-ttu-id="7e12d-979">Driver'Licence</span><span class="sxs-lookup"><span data-stu-id="7e12d-979">Driver'Licence</span></span>
- <span data-ttu-id="7e12d-980">Driver'Licences</span><span class="sxs-lookup"><span data-stu-id="7e12d-980">Driver'Licences</span></span>
- <span data-ttu-id="7e12d-981">Driver'Lic</span><span class="sxs-lookup"><span data-stu-id="7e12d-981">Driver' Lic</span></span>
- <span data-ttu-id="7e12d-982">Driver' Lics</span><span class="sxs-lookup"><span data-stu-id="7e12d-982">Driver' Lics</span></span>
- <span data-ttu-id="7e12d-983">Driver' License</span><span class="sxs-lookup"><span data-stu-id="7e12d-983">Driver' License</span></span>
- <span data-ttu-id="7e12d-984">Driver' Licenses</span><span class="sxs-lookup"><span data-stu-id="7e12d-984">Driver' Licenses</span></span>
- <span data-ttu-id="7e12d-985">Driver' Licence</span><span class="sxs-lookup"><span data-stu-id="7e12d-985">Driver' Licence</span></span>
- <span data-ttu-id="7e12d-986">Driver' Licences</span><span class="sxs-lookup"><span data-stu-id="7e12d-986">Driver' Licences</span></span>
- <span data-ttu-id="7e12d-987">Driver'sLic</span><span class="sxs-lookup"><span data-stu-id="7e12d-987">Driver'sLic</span></span>
- <span data-ttu-id="7e12d-988">Driver'sLics</span><span class="sxs-lookup"><span data-stu-id="7e12d-988">Driver'sLics</span></span>
- <span data-ttu-id="7e12d-989">Secondola</span><span class="sxs-lookup"><span data-stu-id="7e12d-989">Driver'sLicense</span></span>
- <span data-ttu-id="7e12d-990">Driver'sLicenses</span><span class="sxs-lookup"><span data-stu-id="7e12d-990">Driver'sLicenses</span></span>
- <span data-ttu-id="7e12d-991">Driver'sLicence</span><span class="sxs-lookup"><span data-stu-id="7e12d-991">Driver'sLicence</span></span>
- <span data-ttu-id="7e12d-992">Driver'sLicences</span><span class="sxs-lookup"><span data-stu-id="7e12d-992">Driver'sLicences</span></span>
- <span data-ttu-id="7e12d-993">Driver's Lic</span><span class="sxs-lookup"><span data-stu-id="7e12d-993">Driver's Lic</span></span>
- <span data-ttu-id="7e12d-994">Driver's Lics</span><span class="sxs-lookup"><span data-stu-id="7e12d-994">Driver's Lics</span></span>
- <span data-ttu-id="7e12d-995">Driver's License</span><span class="sxs-lookup"><span data-stu-id="7e12d-995">Driver's License</span></span>
- <span data-ttu-id="7e12d-996">Driver's Licenses</span><span class="sxs-lookup"><span data-stu-id="7e12d-996">Driver's Licenses</span></span>
- <span data-ttu-id="7e12d-997">Driver's Licence</span><span class="sxs-lookup"><span data-stu-id="7e12d-997">Driver's Licence</span></span>
- <span data-ttu-id="7e12d-998">Driver's Licences</span><span class="sxs-lookup"><span data-stu-id="7e12d-998">Driver's Licences</span></span>
- <span data-ttu-id="7e12d-999">Permis de Conduire</span><span class="sxs-lookup"><span data-stu-id="7e12d-999">Permis de Conduire</span></span>
- <span data-ttu-id="7e12d-1000">id</span><span class="sxs-lookup"><span data-stu-id="7e12d-1000">id</span></span>
- <span data-ttu-id="7e12d-1001">ID</span><span class="sxs-lookup"><span data-stu-id="7e12d-1001">ids</span></span>
- <span data-ttu-id="7e12d-1002">idcard number</span><span class="sxs-lookup"><span data-stu-id="7e12d-1002">idcard number</span></span>
- <span data-ttu-id="7e12d-1003">idcard numbers</span><span class="sxs-lookup"><span data-stu-id="7e12d-1003">idcard numbers</span></span>
- <span data-ttu-id="7e12d-1004">idcard #</span><span class="sxs-lookup"><span data-stu-id="7e12d-1004">idcard #</span></span>
- <span data-ttu-id="7e12d-1005">idcard #s</span><span class="sxs-lookup"><span data-stu-id="7e12d-1005">idcard #s</span></span>
- <span data-ttu-id="7e12d-1006">idcard card</span><span class="sxs-lookup"><span data-stu-id="7e12d-1006">idcard card</span></span>
- <span data-ttu-id="7e12d-1007">idcard cards</span><span class="sxs-lookup"><span data-stu-id="7e12d-1007">idcard cards</span></span>
- <span data-ttu-id="7e12d-1008">idcard</span><span class="sxs-lookup"><span data-stu-id="7e12d-1008">idcard</span></span>
- <span data-ttu-id="7e12d-1009">identification number</span><span class="sxs-lookup"><span data-stu-id="7e12d-1009">identification number</span></span>
- <span data-ttu-id="7e12d-1010">identification numbers</span><span class="sxs-lookup"><span data-stu-id="7e12d-1010">identification numbers</span></span>
- <span data-ttu-id="7e12d-1011">identification #</span><span class="sxs-lookup"><span data-stu-id="7e12d-1011">identification #</span></span>
- <span data-ttu-id="7e12d-1012">identification #s</span><span class="sxs-lookup"><span data-stu-id="7e12d-1012">identification #s</span></span>
- <span data-ttu-id="7e12d-1013">identification card</span><span class="sxs-lookup"><span data-stu-id="7e12d-1013">identification card</span></span>
- <span data-ttu-id="7e12d-1014">identification cards</span><span class="sxs-lookup"><span data-stu-id="7e12d-1014">identification cards</span></span>
- <span data-ttu-id="7e12d-1015">identificazione</span><span class="sxs-lookup"><span data-stu-id="7e12d-1015">identification</span></span> 
- <span data-ttu-id="7e12d-1016">DL #</span><span class="sxs-lookup"><span data-stu-id="7e12d-1016">DL#</span></span>
- <span data-ttu-id="7e12d-1017">DLS #</span><span class="sxs-lookup"><span data-stu-id="7e12d-1017">DLS#</span></span> 
- <span data-ttu-id="7e12d-1018">CDL #</span><span class="sxs-lookup"><span data-stu-id="7e12d-1018">CDL#</span></span> 
- <span data-ttu-id="7e12d-1019">CDLS #</span><span class="sxs-lookup"><span data-stu-id="7e12d-1019">CDLS#</span></span> 
- <span data-ttu-id="7e12d-1020">DriverLic #</span><span class="sxs-lookup"><span data-stu-id="7e12d-1020">DriverLic#</span></span> 
- <span data-ttu-id="7e12d-1021">DriverLics #</span><span class="sxs-lookup"><span data-stu-id="7e12d-1021">DriverLics#</span></span> 
- <span data-ttu-id="7e12d-1022">DriverLicense #</span><span class="sxs-lookup"><span data-stu-id="7e12d-1022">DriverLicense#</span></span> 
- <span data-ttu-id="7e12d-1023">DriverLicenses #</span><span class="sxs-lookup"><span data-stu-id="7e12d-1023">DriverLicenses#</span></span> 
- <span data-ttu-id="7e12d-1024">DriverLicence #</span><span class="sxs-lookup"><span data-stu-id="7e12d-1024">DriverLicence#</span></span> 
- <span data-ttu-id="7e12d-1025">DriverLicences #</span><span class="sxs-lookup"><span data-stu-id="7e12d-1025">DriverLicences#</span></span> 
- <span data-ttu-id="7e12d-1026">Driver Lic#</span><span class="sxs-lookup"><span data-stu-id="7e12d-1026">Driver Lic#</span></span>
- <span data-ttu-id="7e12d-1027">Driver Lics#</span><span class="sxs-lookup"><span data-stu-id="7e12d-1027">Driver Lics#</span></span> 
- <span data-ttu-id="7e12d-1028">Driver License#</span><span class="sxs-lookup"><span data-stu-id="7e12d-1028">Driver License#</span></span> 
- <span data-ttu-id="7e12d-1029">Driver Licenses#</span><span class="sxs-lookup"><span data-stu-id="7e12d-1029">Driver Licenses#</span></span> 
- <span data-ttu-id="7e12d-1030">Driver License#</span><span class="sxs-lookup"><span data-stu-id="7e12d-1030">Driver License#</span></span> 
- <span data-ttu-id="7e12d-1031">Driver Licences#</span><span class="sxs-lookup"><span data-stu-id="7e12d-1031">Driver Licences#</span></span> 
- <span data-ttu-id="7e12d-1032">DriversLic #</span><span class="sxs-lookup"><span data-stu-id="7e12d-1032">DriversLic#</span></span> 
- <span data-ttu-id="7e12d-1033">DriversLics #</span><span class="sxs-lookup"><span data-stu-id="7e12d-1033">DriversLics#</span></span> 
- <span data-ttu-id="7e12d-1034">DriversLicense #</span><span class="sxs-lookup"><span data-stu-id="7e12d-1034">DriversLicense#</span></span> 
- <span data-ttu-id="7e12d-1035">DriversLicenses #</span><span class="sxs-lookup"><span data-stu-id="7e12d-1035">DriversLicenses#</span></span> 
- <span data-ttu-id="7e12d-1036">DriversLicence #</span><span class="sxs-lookup"><span data-stu-id="7e12d-1036">DriversLicence#</span></span> 
- <span data-ttu-id="7e12d-1037">DriversLicences #</span><span class="sxs-lookup"><span data-stu-id="7e12d-1037">DriversLicences#</span></span> 
- <span data-ttu-id="7e12d-1038">Drivers Lic#</span><span class="sxs-lookup"><span data-stu-id="7e12d-1038">Drivers Lic#</span></span> 
- <span data-ttu-id="7e12d-1039">Drivers Lics#</span><span class="sxs-lookup"><span data-stu-id="7e12d-1039">Drivers Lics#</span></span> 
- <span data-ttu-id="7e12d-1040">Drivers License#</span><span class="sxs-lookup"><span data-stu-id="7e12d-1040">Drivers License#</span></span> 
- <span data-ttu-id="7e12d-1041">Drivers Licenses#</span><span class="sxs-lookup"><span data-stu-id="7e12d-1041">Drivers Licenses#</span></span> 
- <span data-ttu-id="7e12d-1042">Drivers Licence#</span><span class="sxs-lookup"><span data-stu-id="7e12d-1042">Drivers Licence#</span></span> 
- <span data-ttu-id="7e12d-1043">Drivers Licences#</span><span class="sxs-lookup"><span data-stu-id="7e12d-1043">Drivers Licences#</span></span> 
- <span data-ttu-id="7e12d-1044">Driver'Lic #</span><span class="sxs-lookup"><span data-stu-id="7e12d-1044">Driver'Lic#</span></span> 
- <span data-ttu-id="7e12d-1045">Driver ' LiCS #</span><span class="sxs-lookup"><span data-stu-id="7e12d-1045">Driver'Lics#</span></span> 
- <span data-ttu-id="7e12d-1046">Driver ' License #</span><span class="sxs-lookup"><span data-stu-id="7e12d-1046">Driver'License#</span></span> 
- <span data-ttu-id="7e12d-1047">Driver ' licenses #</span><span class="sxs-lookup"><span data-stu-id="7e12d-1047">Driver'Licenses#</span></span> 
- <span data-ttu-id="7e12d-1048">Driver'Licence #</span><span class="sxs-lookup"><span data-stu-id="7e12d-1048">Driver'Licence#</span></span> 
- <span data-ttu-id="7e12d-1049">Driver'Licences #</span><span class="sxs-lookup"><span data-stu-id="7e12d-1049">Driver'Licences#</span></span> 
- <span data-ttu-id="7e12d-1050">Driver' Lic#</span><span class="sxs-lookup"><span data-stu-id="7e12d-1050">Driver' Lic#</span></span> 
- <span data-ttu-id="7e12d-1051">Driver' Lics#</span><span class="sxs-lookup"><span data-stu-id="7e12d-1051">Driver' Lics#</span></span> 
- <span data-ttu-id="7e12d-1052">Driver' License#</span><span class="sxs-lookup"><span data-stu-id="7e12d-1052">Driver' License#</span></span> 
- <span data-ttu-id="7e12d-1053">Driver' Licenses#</span><span class="sxs-lookup"><span data-stu-id="7e12d-1053">Driver' Licenses#</span></span> 
- <span data-ttu-id="7e12d-1054">Driver' Licence#</span><span class="sxs-lookup"><span data-stu-id="7e12d-1054">Driver' Licence#</span></span> 
- <span data-ttu-id="7e12d-1055">Driver' Licences#</span><span class="sxs-lookup"><span data-stu-id="7e12d-1055">Driver' Licences#</span></span> 
- <span data-ttu-id="7e12d-1056">Driver'sLic #</span><span class="sxs-lookup"><span data-stu-id="7e12d-1056">Driver'sLic#</span></span> 
- <span data-ttu-id="7e12d-1057">Driver'sLics #</span><span class="sxs-lookup"><span data-stu-id="7e12d-1057">Driver'sLics#</span></span> 
- <span data-ttu-id="7e12d-1058">Secondola #</span><span class="sxs-lookup"><span data-stu-id="7e12d-1058">Driver'sLicense#</span></span> 
- <span data-ttu-id="7e12d-1059">Driver'sLicenses #</span><span class="sxs-lookup"><span data-stu-id="7e12d-1059">Driver'sLicenses#</span></span> 
- <span data-ttu-id="7e12d-1060">Driver'sLicence #</span><span class="sxs-lookup"><span data-stu-id="7e12d-1060">Driver'sLicence#</span></span> 
- <span data-ttu-id="7e12d-1061">Driver'sLicences #</span><span class="sxs-lookup"><span data-stu-id="7e12d-1061">Driver'sLicences#</span></span> 
- <span data-ttu-id="7e12d-1062">Driver's Lic#</span><span class="sxs-lookup"><span data-stu-id="7e12d-1062">Driver's Lic#</span></span> 
- <span data-ttu-id="7e12d-1063">Driver's Lics#</span><span class="sxs-lookup"><span data-stu-id="7e12d-1063">Driver's Lics#</span></span> 
- <span data-ttu-id="7e12d-1064">Driver's License#</span><span class="sxs-lookup"><span data-stu-id="7e12d-1064">Driver's License#</span></span> 
- <span data-ttu-id="7e12d-1065">Driver's Licenses#</span><span class="sxs-lookup"><span data-stu-id="7e12d-1065">Driver's Licenses#</span></span> 
- <span data-ttu-id="7e12d-1066">Driver's Licence#</span><span class="sxs-lookup"><span data-stu-id="7e12d-1066">Driver's Licence#</span></span> 
- <span data-ttu-id="7e12d-1067">Driver's Licences#</span><span class="sxs-lookup"><span data-stu-id="7e12d-1067">Driver's Licences#</span></span> 
- <span data-ttu-id="7e12d-1068">Permis de Conduire#</span><span class="sxs-lookup"><span data-stu-id="7e12d-1068">Permis de Conduire#</span></span> 
- <span data-ttu-id="7e12d-1069">ID #</span><span class="sxs-lookup"><span data-stu-id="7e12d-1069">id#</span></span> 
- <span data-ttu-id="7e12d-1070">ID #</span><span class="sxs-lookup"><span data-stu-id="7e12d-1070">ids#</span></span> 
- <span data-ttu-id="7e12d-1071">idcard card#</span><span class="sxs-lookup"><span data-stu-id="7e12d-1071">idcard card#</span></span> 
- <span data-ttu-id="7e12d-1072">idcard cards#</span><span class="sxs-lookup"><span data-stu-id="7e12d-1072">idcard cards#</span></span> 
- <span data-ttu-id="7e12d-1073">idcard #</span><span class="sxs-lookup"><span data-stu-id="7e12d-1073">idcard#</span></span> 
- <span data-ttu-id="7e12d-1074">identification card#</span><span class="sxs-lookup"><span data-stu-id="7e12d-1074">identification card#</span></span> 
- <span data-ttu-id="7e12d-1075">identification cards#</span><span class="sxs-lookup"><span data-stu-id="7e12d-1075">identification cards#</span></span> 
- <span data-ttu-id="7e12d-1076">identificazione #</span><span class="sxs-lookup"><span data-stu-id="7e12d-1076">identification#</span></span> 
   
## <a name="canada-health-service-number"></a><span data-ttu-id="7e12d-1077">Canada - Codice del servizio sanitario</span><span class="sxs-lookup"><span data-stu-id="7e12d-1077">Canada Health Service Number</span></span>

### <a name="format"></a><span data-ttu-id="7e12d-1078">Formato</span><span class="sxs-lookup"><span data-stu-id="7e12d-1078">Format</span></span>

<span data-ttu-id="7e12d-1079">10 cifre</span><span class="sxs-lookup"><span data-stu-id="7e12d-1079">10 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="7e12d-1080">Modello</span><span class="sxs-lookup"><span data-stu-id="7e12d-1080">Pattern</span></span>

<span data-ttu-id="7e12d-1081">10 cifre</span><span class="sxs-lookup"><span data-stu-id="7e12d-1081">10 digits</span></span>

### <a name="checksum"></a><span data-ttu-id="7e12d-1082">Checksum</span><span class="sxs-lookup"><span data-stu-id="7e12d-1082">Checksum</span></span>

<span data-ttu-id="7e12d-1083">No</span><span class="sxs-lookup"><span data-stu-id="7e12d-1083">No</span></span>

### <a name="definition"></a><span data-ttu-id="7e12d-1084">Definizione</span><span class="sxs-lookup"><span data-stu-id="7e12d-1084">Definition</span></span>

<span data-ttu-id="7e12d-1085">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="7e12d-1085">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="7e12d-1086">L'espressione regolare Regex_canada_health_service_number restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="7e12d-1086">The regular expression Regex_canada_health_service_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="7e12d-1087">Viene trovata una parola chiave da Keyword_canada_health_service_number.</span><span class="sxs-lookup"><span data-stu-id="7e12d-1087">A keyword from Keyword_canada_health_service_number is found.</span></span>

```xml
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

### <a name="keywords"></a><span data-ttu-id="7e12d-1088">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="7e12d-1088">Keywords</span></span>

#### <a name="keyword_canada_health_service_number"></a><span data-ttu-id="7e12d-1089">Keyword_canada_health_service_number</span><span class="sxs-lookup"><span data-stu-id="7e12d-1089">Keyword_canada_health_service_number</span></span>

- <span data-ttu-id="7e12d-1090">personal health number</span><span class="sxs-lookup"><span data-stu-id="7e12d-1090">personal health number</span></span>
- <span data-ttu-id="7e12d-1091">patient information</span><span class="sxs-lookup"><span data-stu-id="7e12d-1091">patient information</span></span>
- <span data-ttu-id="7e12d-1092">health services</span><span class="sxs-lookup"><span data-stu-id="7e12d-1092">health services</span></span>
- <span data-ttu-id="7e12d-1093">speciality services</span><span class="sxs-lookup"><span data-stu-id="7e12d-1093">speciality services</span></span>
- <span data-ttu-id="7e12d-1094">automobile accident</span><span class="sxs-lookup"><span data-stu-id="7e12d-1094">automobile accident</span></span>
- <span data-ttu-id="7e12d-1095">patient hospital</span><span class="sxs-lookup"><span data-stu-id="7e12d-1095">patient hospital</span></span>
- <span data-ttu-id="7e12d-1096">psichiatra</span><span class="sxs-lookup"><span data-stu-id="7e12d-1096">psychiatrist</span></span>
- <span data-ttu-id="7e12d-1097">workers compensation</span><span class="sxs-lookup"><span data-stu-id="7e12d-1097">workers compensation</span></span>
- <span data-ttu-id="7e12d-1098">Disability</span><span class="sxs-lookup"><span data-stu-id="7e12d-1098">disability</span></span>
      
## <a name="canada-passport-number"></a><span data-ttu-id="7e12d-1099">Canada - Numero di passaporto</span><span class="sxs-lookup"><span data-stu-id="7e12d-1099">Canada Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="7e12d-1100">Formato</span><span class="sxs-lookup"><span data-stu-id="7e12d-1100">Format</span></span>

<span data-ttu-id="7e12d-1101">Due lettere maiuscole seguite da 6 cifre</span><span class="sxs-lookup"><span data-stu-id="7e12d-1101">Two uppercase letters followed by six digits</span></span>

### <a name="pattern"></a><span data-ttu-id="7e12d-1102">Modello</span><span class="sxs-lookup"><span data-stu-id="7e12d-1102">Pattern</span></span>

<span data-ttu-id="7e12d-1103">Due lettere maiuscole seguite da 6 cifre</span><span class="sxs-lookup"><span data-stu-id="7e12d-1103">Two uppercase letters followed by six digits</span></span>

### <a name="checksum"></a><span data-ttu-id="7e12d-1104">Checksum</span><span class="sxs-lookup"><span data-stu-id="7e12d-1104">Checksum</span></span>

<span data-ttu-id="7e12d-1105">No</span><span class="sxs-lookup"><span data-stu-id="7e12d-1105">No</span></span>

### <a name="definition"></a><span data-ttu-id="7e12d-1106">Definizione</span><span class="sxs-lookup"><span data-stu-id="7e12d-1106">Definition</span></span>

<span data-ttu-id="7e12d-1107">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="7e12d-1107">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="7e12d-1108">L'espressione regolare Regex_canada_passport_number restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="7e12d-1108">The regular expression Regex_canada_passport_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="7e12d-1109">Viene trovata una parola chiave da Keyword_canada_passport_number o Keyword_passport.</span><span class="sxs-lookup"><span data-stu-id="7e12d-1109">A keyword from Keyword_canada_passport_number or Keyword_passport is found.</span></span>

```xml 
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

### <a name="keywords"></a><span data-ttu-id="7e12d-1110">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="7e12d-1110">Keywords</span></span>

#### <a name="keyword_canada_passport_number"></a><span data-ttu-id="7e12d-1111">Keyword_canada_passport_number</span><span class="sxs-lookup"><span data-stu-id="7e12d-1111">Keyword_canada_passport_number</span></span>

- <span data-ttu-id="7e12d-1112">canadian citizenship</span><span class="sxs-lookup"><span data-stu-id="7e12d-1112">canadian citizenship</span></span>
- <span data-ttu-id="7e12d-1113">canadian passport</span><span class="sxs-lookup"><span data-stu-id="7e12d-1113">canadian passport</span></span>
- <span data-ttu-id="7e12d-1114">passport application</span><span class="sxs-lookup"><span data-stu-id="7e12d-1114">passport application</span></span>
- <span data-ttu-id="7e12d-1115">passport photos</span><span class="sxs-lookup"><span data-stu-id="7e12d-1115">passport photos</span></span>
- <span data-ttu-id="7e12d-1116">certified translator</span><span class="sxs-lookup"><span data-stu-id="7e12d-1116">certified translator</span></span>
- <span data-ttu-id="7e12d-1117">canadian citizens</span><span class="sxs-lookup"><span data-stu-id="7e12d-1117">canadian citizens</span></span>
- <span data-ttu-id="7e12d-1118">processing times</span><span class="sxs-lookup"><span data-stu-id="7e12d-1118">processing times</span></span>
- <span data-ttu-id="7e12d-1119">renewal application</span><span class="sxs-lookup"><span data-stu-id="7e12d-1119">renewal application</span></span>

#### <a name="keyword_passport"></a><span data-ttu-id="7e12d-1120">Keyword_passport</span><span class="sxs-lookup"><span data-stu-id="7e12d-1120">Keyword_passport</span></span>

- <span data-ttu-id="7e12d-1121">Passport Number</span><span class="sxs-lookup"><span data-stu-id="7e12d-1121">Passport Number</span></span>
- <span data-ttu-id="7e12d-1122">Passport No</span><span class="sxs-lookup"><span data-stu-id="7e12d-1122">Passport No</span></span>
- <span data-ttu-id="7e12d-1123">Passport#</span><span class="sxs-lookup"><span data-stu-id="7e12d-1123">Passport #</span></span>
- <span data-ttu-id="7e12d-1124">Passaporto #</span><span class="sxs-lookup"><span data-stu-id="7e12d-1124">Passport#</span></span>
- <span data-ttu-id="7e12d-1125">PassportID</span><span class="sxs-lookup"><span data-stu-id="7e12d-1125">PassportID</span></span>
- <span data-ttu-id="7e12d-1126">Passportno</span><span class="sxs-lookup"><span data-stu-id="7e12d-1126">Passportno</span></span>
- <span data-ttu-id="7e12d-1127">passportnumber</span><span class="sxs-lookup"><span data-stu-id="7e12d-1127">passportnumber</span></span>
- <span data-ttu-id="7e12d-1128">パスポート</span><span class="sxs-lookup"><span data-stu-id="7e12d-1128">パスポート</span></span>
- <span data-ttu-id="7e12d-1129">パスポート番号</span><span class="sxs-lookup"><span data-stu-id="7e12d-1129">パスポート番号</span></span>
- <span data-ttu-id="7e12d-1130">パスポートのNum</span><span class="sxs-lookup"><span data-stu-id="7e12d-1130">パスポートのNum</span></span>
- <span data-ttu-id="7e12d-1131">パスポート＃</span><span class="sxs-lookup"><span data-stu-id="7e12d-1131">パスポート＃</span></span>
- <span data-ttu-id="7e12d-1132">Numéro de passeport</span><span class="sxs-lookup"><span data-stu-id="7e12d-1132">Numéro de passeport</span></span>
- <span data-ttu-id="7e12d-1133">Passeport n °</span><span class="sxs-lookup"><span data-stu-id="7e12d-1133">Passeport n °</span></span>
- <span data-ttu-id="7e12d-1134">Passeport Non</span><span class="sxs-lookup"><span data-stu-id="7e12d-1134">Passeport Non</span></span>
- <span data-ttu-id="7e12d-1135">Passeport#</span><span class="sxs-lookup"><span data-stu-id="7e12d-1135">Passeport #</span></span>
- <span data-ttu-id="7e12d-1136">Passeport #</span><span class="sxs-lookup"><span data-stu-id="7e12d-1136">Passeport#</span></span>
- <span data-ttu-id="7e12d-1137">PasseportNon</span><span class="sxs-lookup"><span data-stu-id="7e12d-1137">PasseportNon</span></span>
- <span data-ttu-id="7e12d-1138">Passeportn °</span><span class="sxs-lookup"><span data-stu-id="7e12d-1138">Passeportn °</span></span>
   
## <a name="canada-personal-health-identification-number-phin"></a><span data-ttu-id="7e12d-1139">Canada - Numero di identificazione sanitaria personale (PHIN)</span><span class="sxs-lookup"><span data-stu-id="7e12d-1139">Canada Personal Health Identification Number (PHIN)</span></span>

### <a name="format"></a><span data-ttu-id="7e12d-1140">Formato</span><span class="sxs-lookup"><span data-stu-id="7e12d-1140">Format</span></span>

<span data-ttu-id="7e12d-1141">9 cifre</span><span class="sxs-lookup"><span data-stu-id="7e12d-1141">Nine digits</span></span>

### <a name="pattern"></a><span data-ttu-id="7e12d-1142">Modello</span><span class="sxs-lookup"><span data-stu-id="7e12d-1142">Pattern</span></span>

<span data-ttu-id="7e12d-1143">9 cifre</span><span class="sxs-lookup"><span data-stu-id="7e12d-1143">Nine digits</span></span>

### <a name="checksum"></a><span data-ttu-id="7e12d-1144">Checksum</span><span class="sxs-lookup"><span data-stu-id="7e12d-1144">Checksum</span></span>

<span data-ttu-id="7e12d-1145">No</span><span class="sxs-lookup"><span data-stu-id="7e12d-1145">No</span></span>

### <a name="definition"></a><span data-ttu-id="7e12d-1146">Definizione</span><span class="sxs-lookup"><span data-stu-id="7e12d-1146">Definition</span></span>

<span data-ttu-id="7e12d-1147">Un criterio DLP è 75% fiducioso di aver rilevato questo tipo di informazioni riservate se, entro 300 caratteri: l'espressione regolare Regex_canada_phin trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="7e12d-1147">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The regular expression Regex_canada_phin finds content that matches the pattern.</span></span>
<span data-ttu-id="7e12d-1148">Sono state trovate almeno due parole chiave di Keyword_canada_phin o Keyword_canada_provinces..</span><span class="sxs-lookup"><span data-stu-id="7e12d-1148">At least two keywords from Keyword_canada_phin or Keyword_canada_provinces are found..</span></span>

```xml
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

### <a name="keywords"></a><span data-ttu-id="7e12d-1149">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="7e12d-1149">Keywords</span></span>

#### <a name="keyword_canada_phin"></a><span data-ttu-id="7e12d-1150">Keyword_canada_phin</span><span class="sxs-lookup"><span data-stu-id="7e12d-1150">Keyword_canada_phin</span></span>

- <span data-ttu-id="7e12d-1151">social insurance number</span><span class="sxs-lookup"><span data-stu-id="7e12d-1151">social insurance number</span></span>
- <span data-ttu-id="7e12d-1152">health information act</span><span class="sxs-lookup"><span data-stu-id="7e12d-1152">health information act</span></span>
- <span data-ttu-id="7e12d-1153">income tax information</span><span class="sxs-lookup"><span data-stu-id="7e12d-1153">income tax information</span></span>
- <span data-ttu-id="7e12d-1154">manitoba health</span><span class="sxs-lookup"><span data-stu-id="7e12d-1154">manitoba health</span></span>
- <span data-ttu-id="7e12d-1155">health registration</span><span class="sxs-lookup"><span data-stu-id="7e12d-1155">health registration</span></span>
- <span data-ttu-id="7e12d-1156">prescription purchases</span><span class="sxs-lookup"><span data-stu-id="7e12d-1156">prescription purchases</span></span>
- <span data-ttu-id="7e12d-1157">benefit eligibility</span><span class="sxs-lookup"><span data-stu-id="7e12d-1157">benefit eligibility</span></span>
- <span data-ttu-id="7e12d-1158">personal health</span><span class="sxs-lookup"><span data-stu-id="7e12d-1158">personal health</span></span>
- <span data-ttu-id="7e12d-1159">power of attorney</span><span class="sxs-lookup"><span data-stu-id="7e12d-1159">power of attorney</span></span>
- <span data-ttu-id="7e12d-1160">registration number</span><span class="sxs-lookup"><span data-stu-id="7e12d-1160">registration number</span></span>
- <span data-ttu-id="7e12d-1161">personal health number</span><span class="sxs-lookup"><span data-stu-id="7e12d-1161">personal health number</span></span>
- <span data-ttu-id="7e12d-1162">practitioner referral</span><span class="sxs-lookup"><span data-stu-id="7e12d-1162">practitioner referral</span></span>
- <span data-ttu-id="7e12d-1163">wellness professional</span><span class="sxs-lookup"><span data-stu-id="7e12d-1163">wellness professional</span></span>
- <span data-ttu-id="7e12d-1164">patient referral</span><span class="sxs-lookup"><span data-stu-id="7e12d-1164">patient referral</span></span>
- <span data-ttu-id="7e12d-1165">health and wellness</span><span class="sxs-lookup"><span data-stu-id="7e12d-1165">health and wellness</span></span>

#### <a name="keyword_canada_provinces"></a><span data-ttu-id="7e12d-1166">Keyword_canada_provinces</span><span class="sxs-lookup"><span data-stu-id="7e12d-1166">Keyword_canada_provinces</span></span>

- <span data-ttu-id="7e12d-1167">Nunavut</span><span class="sxs-lookup"><span data-stu-id="7e12d-1167">Nunavut</span></span>
- <span data-ttu-id="7e12d-1168">Quebec</span><span class="sxs-lookup"><span data-stu-id="7e12d-1168">Quebec</span></span>
- <span data-ttu-id="7e12d-1169">Northwest Territories</span><span class="sxs-lookup"><span data-stu-id="7e12d-1169">Northwest Territories</span></span>
- <span data-ttu-id="7e12d-1170">Ontario</span><span class="sxs-lookup"><span data-stu-id="7e12d-1170">Ontario</span></span>
- <span data-ttu-id="7e12d-1171">British Columbia</span><span class="sxs-lookup"><span data-stu-id="7e12d-1171">British Columbia</span></span>
- <span data-ttu-id="7e12d-1172">Filippa</span><span class="sxs-lookup"><span data-stu-id="7e12d-1172">Alberta</span></span>
- <span data-ttu-id="7e12d-1173">Saskatchewan</span><span class="sxs-lookup"><span data-stu-id="7e12d-1173">Saskatchewan</span></span>
- <span data-ttu-id="7e12d-1174">Manitoba</span><span class="sxs-lookup"><span data-stu-id="7e12d-1174">Manitoba</span></span>
- <span data-ttu-id="7e12d-1175">Yukon</span><span class="sxs-lookup"><span data-stu-id="7e12d-1175">Yukon</span></span>
- <span data-ttu-id="7e12d-1176">Newfoundland and Labrador</span><span class="sxs-lookup"><span data-stu-id="7e12d-1176">Newfoundland and Labrador</span></span>
- <span data-ttu-id="7e12d-1177">New Brunswick</span><span class="sxs-lookup"><span data-stu-id="7e12d-1177">New Brunswick</span></span>
- <span data-ttu-id="7e12d-1178">Nova Scotia</span><span class="sxs-lookup"><span data-stu-id="7e12d-1178">Nova Scotia</span></span>
- <span data-ttu-id="7e12d-1179">Prince Edward Island</span><span class="sxs-lookup"><span data-stu-id="7e12d-1179">Prince Edward Island</span></span>
- <span data-ttu-id="7e12d-1180">Canada</span><span class="sxs-lookup"><span data-stu-id="7e12d-1180">Canada</span></span>
   
## <a name="canada-social-insurance-number"></a><span data-ttu-id="7e12d-1181">Canada - Numero di assicurazione sociale</span><span class="sxs-lookup"><span data-stu-id="7e12d-1181">Canada Social Insurance Number</span></span>

### <a name="format"></a><span data-ttu-id="7e12d-1182">Formato</span><span class="sxs-lookup"><span data-stu-id="7e12d-1182">Format</span></span>

<span data-ttu-id="7e12d-1183">9 cifre con spazi o lineette facoltativi</span><span class="sxs-lookup"><span data-stu-id="7e12d-1183">Nine digits with optional hyphens or spaces</span></span>

### <a name="pattern"></a><span data-ttu-id="7e12d-1184">Modello</span><span class="sxs-lookup"><span data-stu-id="7e12d-1184">Pattern</span></span>

<span data-ttu-id="7e12d-1185">Formattato</span><span class="sxs-lookup"><span data-stu-id="7e12d-1185">Formatted:</span></span>
- <span data-ttu-id="7e12d-1186">Tre cifre</span><span class="sxs-lookup"><span data-stu-id="7e12d-1186">Three digits</span></span> 
- <span data-ttu-id="7e12d-1187">Una lineetta o uno spazio</span><span class="sxs-lookup"><span data-stu-id="7e12d-1187">A hyphen or space</span></span> 
- <span data-ttu-id="7e12d-1188">Tre cifre</span><span class="sxs-lookup"><span data-stu-id="7e12d-1188">Three digits</span></span> 
- <span data-ttu-id="7e12d-1189">Una lineetta o uno spazio</span><span class="sxs-lookup"><span data-stu-id="7e12d-1189">A hyphen or space</span></span> 
- <span data-ttu-id="7e12d-1190">Tre cifre</span><span class="sxs-lookup"><span data-stu-id="7e12d-1190">Three digits</span></span>

<span data-ttu-id="7e12d-1191">Non formattato: nove cifre</span><span class="sxs-lookup"><span data-stu-id="7e12d-1191">Unformatted: Nine digits</span></span>

### <a name="checksum"></a><span data-ttu-id="7e12d-1192">Checksum</span><span class="sxs-lookup"><span data-stu-id="7e12d-1192">Checksum</span></span>

<span data-ttu-id="7e12d-1193">Sì</span><span class="sxs-lookup"><span data-stu-id="7e12d-1193">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="7e12d-1194">Definizione</span><span class="sxs-lookup"><span data-stu-id="7e12d-1194">Definition</span></span>

<span data-ttu-id="7e12d-1195">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="7e12d-1195">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="7e12d-1196">La funzione Func_canadian_sin restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="7e12d-1196">The function Func_canadian_sin finds content that matches the pattern.</span></span>
- <span data-ttu-id="7e12d-1197">Almeno due delle seguenti combinazioni:</span><span class="sxs-lookup"><span data-stu-id="7e12d-1197">At least two of any combination of the following:</span></span>
    - <span data-ttu-id="7e12d-1198">Viene trovata una parola chiave da Keyword_sin.</span><span class="sxs-lookup"><span data-stu-id="7e12d-1198">A keyword from Keyword_sin is found.</span></span>
    - <span data-ttu-id="7e12d-1199">Viene trovata una parola chiave da Keyword_sin_collaborative.</span><span class="sxs-lookup"><span data-stu-id="7e12d-1199">A keyword from Keyword_sin_collaborative is found.</span></span>
    - <span data-ttu-id="7e12d-1200">La funzione Func_eu_date rileva una data nel formato corretto.</span><span class="sxs-lookup"><span data-stu-id="7e12d-1200">The function Func_eu_date finds a date in the right date format.</span></span>
- <span data-ttu-id="7e12d-1201">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="7e12d-1201">The checksum passes.</span></span>

<span data-ttu-id="7e12d-1202">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="7e12d-1202">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="7e12d-1203">La funzione Func_unformatted_canadian_sin restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="7e12d-1203">The function Func_unformatted_canadian_sin finds content that matches the pattern.</span></span>
- <span data-ttu-id="7e12d-1204">Viene trovata una parola chiave da Keyword_sin.</span><span class="sxs-lookup"><span data-stu-id="7e12d-1204">A keyword from Keyword_sin is found.</span></span>
- <span data-ttu-id="7e12d-1205">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="7e12d-1205">The checksum passes.</span></span>

```xml
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

### <a name="keywords"></a><span data-ttu-id="7e12d-1206">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="7e12d-1206">Keywords</span></span>

#### <a name="keyword_sin"></a><span data-ttu-id="7e12d-1207">Keyword_sin</span><span class="sxs-lookup"><span data-stu-id="7e12d-1207">Keyword_sin</span></span>

- <span data-ttu-id="7e12d-1208">sin</span><span class="sxs-lookup"><span data-stu-id="7e12d-1208">sin</span></span> 
- <span data-ttu-id="7e12d-1209">social insurance</span><span class="sxs-lookup"><span data-stu-id="7e12d-1209">social insurance</span></span> 
- <span data-ttu-id="7e12d-1210">numero d'assurance sociale</span><span class="sxs-lookup"><span data-stu-id="7e12d-1210">numero d'assurance sociale</span></span> 
- <span data-ttu-id="7e12d-1211">peccati</span><span class="sxs-lookup"><span data-stu-id="7e12d-1211">sins</span></span> 
- <span data-ttu-id="7e12d-1212">SSN</span><span class="sxs-lookup"><span data-stu-id="7e12d-1212">ssn</span></span> 
- <span data-ttu-id="7e12d-1213">SNSS</span><span class="sxs-lookup"><span data-stu-id="7e12d-1213">ssns</span></span> 
- <span data-ttu-id="7e12d-1214">social security</span><span class="sxs-lookup"><span data-stu-id="7e12d-1214">social security</span></span> 
- <span data-ttu-id="7e12d-1215">numero d'assurance social</span><span class="sxs-lookup"><span data-stu-id="7e12d-1215">numero d'assurance social</span></span> 
- <span data-ttu-id="7e12d-1216">national identification number</span><span class="sxs-lookup"><span data-stu-id="7e12d-1216">national identification number</span></span> 
- <span data-ttu-id="7e12d-1217">national id</span><span class="sxs-lookup"><span data-stu-id="7e12d-1217">national id</span></span> 
- <span data-ttu-id="7e12d-1218">sin #</span><span class="sxs-lookup"><span data-stu-id="7e12d-1218">sin#</span></span> 
- <span data-ttu-id="7e12d-1219">soc ins</span><span class="sxs-lookup"><span data-stu-id="7e12d-1219">soc ins</span></span> 
- <span data-ttu-id="7e12d-1220">social ins</span><span class="sxs-lookup"><span data-stu-id="7e12d-1220">social ins</span></span> 

#### <a name="keyword_sin_collaborative"></a><span data-ttu-id="7e12d-1221">Keyword_sin_collaborative</span><span class="sxs-lookup"><span data-stu-id="7e12d-1221">Keyword_sin_collaborative</span></span>

- <span data-ttu-id="7e12d-1222">driver's license</span><span class="sxs-lookup"><span data-stu-id="7e12d-1222">driver's license</span></span> 
- <span data-ttu-id="7e12d-1223">drivers license</span><span class="sxs-lookup"><span data-stu-id="7e12d-1223">drivers license</span></span> 
- <span data-ttu-id="7e12d-1224">driver's licence</span><span class="sxs-lookup"><span data-stu-id="7e12d-1224">driver's licence</span></span> 
- <span data-ttu-id="7e12d-1225">drivers licence</span><span class="sxs-lookup"><span data-stu-id="7e12d-1225">drivers licence</span></span> 
- <span data-ttu-id="7e12d-1226">DOB</span><span class="sxs-lookup"><span data-stu-id="7e12d-1226">DOB</span></span> 
- <span data-ttu-id="7e12d-1227">Data di nascita</span><span class="sxs-lookup"><span data-stu-id="7e12d-1227">Birthdate</span></span> 
- <span data-ttu-id="7e12d-1228">Compleanno</span><span class="sxs-lookup"><span data-stu-id="7e12d-1228">Birthday</span></span> 
- <span data-ttu-id="7e12d-1229">Date of Birth</span><span class="sxs-lookup"><span data-stu-id="7e12d-1229">Date of Birth</span></span> 
   
## <a name="chile-identity-card-number"></a><span data-ttu-id="7e12d-1230">	Cile - Numero di carta di identità</span><span class="sxs-lookup"><span data-stu-id="7e12d-1230">Chile Identity Card Number</span></span>

### <a name="format"></a><span data-ttu-id="7e12d-1231">Formato</span><span class="sxs-lookup"><span data-stu-id="7e12d-1231">Format</span></span>

<span data-ttu-id="7e12d-1232">7-8 cifre più delimitatori una cifra di controllo o una lettera</span><span class="sxs-lookup"><span data-stu-id="7e12d-1232">7-8 digits plus delimiters a check digit or letter</span></span>

### <a name="pattern"></a><span data-ttu-id="7e12d-1233">Modello</span><span class="sxs-lookup"><span data-stu-id="7e12d-1233">Pattern</span></span>

<span data-ttu-id="7e12d-1234">7-8 cifre più delimitatori:</span><span class="sxs-lookup"><span data-stu-id="7e12d-1234">7-8 digits plus delimiters:</span></span>
- <span data-ttu-id="7e12d-1235">1-2 cifre</span><span class="sxs-lookup"><span data-stu-id="7e12d-1235">1-2 digits</span></span> 
- <span data-ttu-id="7e12d-1236">Un punto </span><span class="sxs-lookup"><span data-stu-id="7e12d-1236">A period</span></span> 
- <span data-ttu-id="7e12d-1237">Tre cifre</span><span class="sxs-lookup"><span data-stu-id="7e12d-1237">Three digits</span></span> 
- <span data-ttu-id="7e12d-1238">Un punto </span><span class="sxs-lookup"><span data-stu-id="7e12d-1238">A period</span></span> 
- <span data-ttu-id="7e12d-1239">Tre cifre</span><span class="sxs-lookup"><span data-stu-id="7e12d-1239">Three digits</span></span> 
- <span data-ttu-id="7e12d-1240">Un trattino</span><span class="sxs-lookup"><span data-stu-id="7e12d-1240">A dash</span></span> 
- <span data-ttu-id="7e12d-1241">Una cifra o una lettera (senza distinzione tra maiuscole e minuscole) che corrisponde a una cifra di controllo</span><span class="sxs-lookup"><span data-stu-id="7e12d-1241">One digit or letter (not case sensitive) which is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="7e12d-1242">Checksum</span><span class="sxs-lookup"><span data-stu-id="7e12d-1242">Checksum</span></span>

<span data-ttu-id="7e12d-1243">Sì</span><span class="sxs-lookup"><span data-stu-id="7e12d-1243">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="7e12d-1244">Definizione</span><span class="sxs-lookup"><span data-stu-id="7e12d-1244">Definition</span></span>

<span data-ttu-id="7e12d-1245">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="7e12d-1245">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="7e12d-1246">La funzione Func_chile_id_card trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="7e12d-1246">The function Func_chile_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="7e12d-1247">Viene trovata una parola chiave da Keyword_chile_id_card.</span><span class="sxs-lookup"><span data-stu-id="7e12d-1247">A keyword from Keyword_chile_id_card is found.</span></span>
- <span data-ttu-id="7e12d-1248">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="7e12d-1248">The checksum passes.</span></span>

<span data-ttu-id="7e12d-1249">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="7e12d-1249">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="7e12d-1250">La funzione Func_chile_id_card trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="7e12d-1250">The function Func_chile_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="7e12d-1251">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="7e12d-1251">The checksum passes.</span></span>

```xml
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

### <a name="keywords"></a><span data-ttu-id="7e12d-1252">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="7e12d-1252">Keywords</span></span>

#### <a name="keyword_chile_id_card"></a><span data-ttu-id="7e12d-1253">Keyword_chile_id_card</span><span class="sxs-lookup"><span data-stu-id="7e12d-1253">Keyword_chile_id_card</span></span>

- <span data-ttu-id="7e12d-1254">Numero di carta d’identità</span><span class="sxs-lookup"><span data-stu-id="7e12d-1254">National Identification Number</span></span> 
- <span data-ttu-id="7e12d-1255">Carta di identità</span><span class="sxs-lookup"><span data-stu-id="7e12d-1255">Identity card</span></span> 
- <span data-ttu-id="7e12d-1256">ID</span><span class="sxs-lookup"><span data-stu-id="7e12d-1256">ID</span></span> 
- <span data-ttu-id="7e12d-1257">Identificazione</span><span class="sxs-lookup"><span data-stu-id="7e12d-1257">Identification</span></span> 
- <span data-ttu-id="7e12d-1258">Rol Único Nacional</span><span class="sxs-lookup"><span data-stu-id="7e12d-1258">Rol Único Nacional</span></span> 
- <span data-ttu-id="7e12d-1259">Correre</span><span class="sxs-lookup"><span data-stu-id="7e12d-1259">RUN</span></span> 
- <span data-ttu-id="7e12d-1260">Rol Único Tributario</span><span class="sxs-lookup"><span data-stu-id="7e12d-1260">Rol Único Tributario</span></span> 
- <span data-ttu-id="7e12d-1261">CARREGGIATA</span><span class="sxs-lookup"><span data-stu-id="7e12d-1261">RUT</span></span> 
- <span data-ttu-id="7e12d-1262">Cédula de Identidad</span><span class="sxs-lookup"><span data-stu-id="7e12d-1262">Cédula de Identidad</span></span> 
- <span data-ttu-id="7e12d-1263">Número De Identificación Nacional</span><span class="sxs-lookup"><span data-stu-id="7e12d-1263">Número De Identificación Nacional</span></span> 
- <span data-ttu-id="7e12d-1264">Tarjeta de identificación</span><span class="sxs-lookup"><span data-stu-id="7e12d-1264">Tarjeta de identificación</span></span> 
- <span data-ttu-id="7e12d-1265">Identificación</span><span class="sxs-lookup"><span data-stu-id="7e12d-1265">Identificación</span></span> 
   
## <a name="china-resident-identity-card-prc-number"></a><span data-ttu-id="7e12d-1266">	Numero carta di identità per residenti in Cina (RPC)</span><span class="sxs-lookup"><span data-stu-id="7e12d-1266">China Resident Identity Card (PRC) Number</span></span>

### <a name="format"></a><span data-ttu-id="7e12d-1267">Formato</span><span class="sxs-lookup"><span data-stu-id="7e12d-1267">Format</span></span>

<span data-ttu-id="7e12d-1268">18 cifre</span><span class="sxs-lookup"><span data-stu-id="7e12d-1268">18 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="7e12d-1269">Modello</span><span class="sxs-lookup"><span data-stu-id="7e12d-1269">Pattern</span></span>

<span data-ttu-id="7e12d-1270">18 cifre:</span><span class="sxs-lookup"><span data-stu-id="7e12d-1270">18 digits:</span></span>
- <span data-ttu-id="7e12d-1271">Sei cifre, ovvero un codice indirizzo </span><span class="sxs-lookup"><span data-stu-id="7e12d-1271">Six digits which are an address code</span></span> 
- <span data-ttu-id="7e12d-1272">Otto cifre nel formato AAAAMMGG, ovvero la data di nascita </span><span class="sxs-lookup"><span data-stu-id="7e12d-1272">Eight digits in the form YYYYMMDD which are the date of birth</span></span> 
- <span data-ttu-id="7e12d-1273">Tre cifre, ovvero un codice di ordine </span><span class="sxs-lookup"><span data-stu-id="7e12d-1273">Three digits which are an order code</span></span> 
- <span data-ttu-id="7e12d-1274">Una cifra, ovvero una cifra di controllo</span><span class="sxs-lookup"><span data-stu-id="7e12d-1274">One digit which is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="7e12d-1275">Checksum</span><span class="sxs-lookup"><span data-stu-id="7e12d-1275">Checksum</span></span>

<span data-ttu-id="7e12d-1276">Sì</span><span class="sxs-lookup"><span data-stu-id="7e12d-1276">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="7e12d-1277">Definizione</span><span class="sxs-lookup"><span data-stu-id="7e12d-1277">Definition</span></span>

<span data-ttu-id="7e12d-1278">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="7e12d-1278">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="7e12d-1279">La funzione Func_china_resident_id trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="7e12d-1279">The function Func_china_resident_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="7e12d-1280">Viene trovata una parola chiave da Keyword_china_resident_id.</span><span class="sxs-lookup"><span data-stu-id="7e12d-1280">A keyword from Keyword_china_resident_id is found.</span></span>
- <span data-ttu-id="7e12d-1281">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="7e12d-1281">The checksum passes.</span></span>

<span data-ttu-id="7e12d-1282">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="7e12d-1282">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="7e12d-1283">La funzione Func_china_resident_id trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="7e12d-1283">The function Func_china_resident_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="7e12d-1284">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="7e12d-1284">The checksum passes.</span></span>

```xml
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

### <a name="keywords"></a><span data-ttu-id="7e12d-1285">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="7e12d-1285">Keywords</span></span>

### <a name="keyword_china_resident_id"></a><span data-ttu-id="7e12d-1286">Keyword_china_resident_id</span><span class="sxs-lookup"><span data-stu-id="7e12d-1286">Keyword_china_resident_id</span></span>

- <span data-ttu-id="7e12d-1287">Carta d’identità per residenti</span><span class="sxs-lookup"><span data-stu-id="7e12d-1287">Resident Identity Card</span></span> 
- <span data-ttu-id="7e12d-1288">RPC</span><span class="sxs-lookup"><span data-stu-id="7e12d-1288">PRC</span></span> 
- <span data-ttu-id="7e12d-1289">Carta d’identità</span><span class="sxs-lookup"><span data-stu-id="7e12d-1289">National Identification Card</span></span> 
- <span data-ttu-id="7e12d-1290">身份证</span><span class="sxs-lookup"><span data-stu-id="7e12d-1290">身份证</span></span> 
- <span data-ttu-id="7e12d-1291">居民 身份证</span><span class="sxs-lookup"><span data-stu-id="7e12d-1291">居民 身份证</span></span> 
- <span data-ttu-id="7e12d-1292">居民身份证</span><span class="sxs-lookup"><span data-stu-id="7e12d-1292">居民身份证</span></span> 
- <span data-ttu-id="7e12d-1293">鉴定</span><span class="sxs-lookup"><span data-stu-id="7e12d-1293">鉴定</span></span> 
- <span data-ttu-id="7e12d-1294">身分證</span><span class="sxs-lookup"><span data-stu-id="7e12d-1294">身分證</span></span> 
- <span data-ttu-id="7e12d-1295">居民 身份證</span><span class="sxs-lookup"><span data-stu-id="7e12d-1295">居民 身份證</span></span>
- <span data-ttu-id="7e12d-1296">鑑定</span><span class="sxs-lookup"><span data-stu-id="7e12d-1296">鑑定</span></span> 
   
## <a name="credit-card-number"></a><span data-ttu-id="7e12d-1297">Credit Card Number</span><span class="sxs-lookup"><span data-stu-id="7e12d-1297">Credit Card Number</span></span>

### <a name="format"></a><span data-ttu-id="7e12d-1298">Formato</span><span class="sxs-lookup"><span data-stu-id="7e12d-1298">Format</span></span>

<span data-ttu-id="7e12d-1299">16 cifre che possono essere formattate o non formattate (dddddddddddddddd) e devono superare il test di Luhn.</span><span class="sxs-lookup"><span data-stu-id="7e12d-1299">16 digits which can be formatted or unformatted (dddddddddddddddd) and must pass the Luhn test.</span></span>

### <a name="pattern"></a><span data-ttu-id="7e12d-1300">Modello</span><span class="sxs-lookup"><span data-stu-id="7e12d-1300">Pattern</span></span>

<span data-ttu-id="7e12d-1301">Modello molto complesso e solido che rileva carte di credito dei maggiori circuiti del mondo, ad esempio, Visa, MasterCard, Discover Card, JCB, American Express, nonché carte regalo e ticket restaurant.</span><span class="sxs-lookup"><span data-stu-id="7e12d-1301">Very complex and robust pattern that detects cards from all major brands worldwide, including Visa, MasterCard, Discover Card, JCB, American Express, gift cards, and diner cards.</span></span>

### <a name="checksum"></a><span data-ttu-id="7e12d-1302">Checksum</span><span class="sxs-lookup"><span data-stu-id="7e12d-1302">Checksum</span></span>

<span data-ttu-id="7e12d-1303">Yes, il checksum Luhn</span><span class="sxs-lookup"><span data-stu-id="7e12d-1303">Yes, the Luhn checksum</span></span>

### <a name="definition"></a><span data-ttu-id="7e12d-1304">Definizione</span><span class="sxs-lookup"><span data-stu-id="7e12d-1304">Definition</span></span>

<span data-ttu-id="7e12d-1305">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="7e12d-1305">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="7e12d-1306">La funzione Func_credit_card restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="7e12d-1306">The function Func_credit_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="7e12d-1307">Si verifica una delle situazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="7e12d-1307">One of the following is true:</span></span>
    - <span data-ttu-id="7e12d-1308">Viene trovata una parola chiave da Keyword_cc_verification.</span><span class="sxs-lookup"><span data-stu-id="7e12d-1308">A keyword from Keyword_cc_verification is found.</span></span>
    - <span data-ttu-id="7e12d-1309">Viene trovata una parola chiave da Keyword_cc_name.</span><span class="sxs-lookup"><span data-stu-id="7e12d-1309">A keyword from Keyword_cc_name is found.</span></span>
    - <span data-ttu-id="7e12d-1310">La funzione Func_expiration_date rileva una data nel formato corretto.</span><span class="sxs-lookup"><span data-stu-id="7e12d-1310">The function Func_expiration_date finds a date in the right date format.</span></span>
- <span data-ttu-id="7e12d-1311">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="7e12d-1311">The checksum passes.</span></span>

<span data-ttu-id="7e12d-1312">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 65%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="7e12d-1312">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="7e12d-1313">La funzione Func_credit_card restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="7e12d-1313">The function Func_credit_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="7e12d-1314">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="7e12d-1314">The checksum passes.</span></span>

```xml
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

### <a name="keywords"></a><span data-ttu-id="7e12d-1315">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="7e12d-1315">Keywords</span></span>

#### <a name="keyword_cc_verification"></a><span data-ttu-id="7e12d-1316">Keyword_cc_verification</span><span class="sxs-lookup"><span data-stu-id="7e12d-1316">Keyword_cc_verification</span></span>

- <span data-ttu-id="7e12d-1317">card verification</span><span class="sxs-lookup"><span data-stu-id="7e12d-1317">card verification</span></span>
- <span data-ttu-id="7e12d-1318">card identification number</span><span class="sxs-lookup"><span data-stu-id="7e12d-1318">card identification number</span></span>
- <span data-ttu-id="7e12d-1319">CVN</span><span class="sxs-lookup"><span data-stu-id="7e12d-1319">cvn</span></span>
- <span data-ttu-id="7e12d-1320">ID</span><span class="sxs-lookup"><span data-stu-id="7e12d-1320">cid</span></span>
- <span data-ttu-id="7e12d-1321">CVC2</span><span class="sxs-lookup"><span data-stu-id="7e12d-1321">cvc2</span></span>
- <span data-ttu-id="7e12d-1322">CVV2</span><span class="sxs-lookup"><span data-stu-id="7e12d-1322">cvv2</span></span>
- <span data-ttu-id="7e12d-1323">pin block</span><span class="sxs-lookup"><span data-stu-id="7e12d-1323">pin block</span></span>
- <span data-ttu-id="7e12d-1324">security code</span><span class="sxs-lookup"><span data-stu-id="7e12d-1324">security code</span></span>
- <span data-ttu-id="7e12d-1325">security number</span><span class="sxs-lookup"><span data-stu-id="7e12d-1325">security number</span></span>
- <span data-ttu-id="7e12d-1326">security no</span><span class="sxs-lookup"><span data-stu-id="7e12d-1326">security no</span></span>
- <span data-ttu-id="7e12d-1327">issue number</span><span class="sxs-lookup"><span data-stu-id="7e12d-1327">issue number</span></span>
- <span data-ttu-id="7e12d-1328">issue no</span><span class="sxs-lookup"><span data-stu-id="7e12d-1328">issue no</span></span>
- <span data-ttu-id="7e12d-1329">cryptogramme</span><span class="sxs-lookup"><span data-stu-id="7e12d-1329">cryptogramme</span></span>
- <span data-ttu-id="7e12d-1330">numéro de sécurité</span><span class="sxs-lookup"><span data-stu-id="7e12d-1330">numéro de sécurité</span></span>
- <span data-ttu-id="7e12d-1331">numero de securite</span><span class="sxs-lookup"><span data-stu-id="7e12d-1331">numero de securite</span></span>
- <span data-ttu-id="7e12d-1332">kreditkartenprüfnummer</span><span class="sxs-lookup"><span data-stu-id="7e12d-1332">kreditkartenprüfnummer</span></span>
- <span data-ttu-id="7e12d-1333">kreditkartenprufnummer</span><span class="sxs-lookup"><span data-stu-id="7e12d-1333">kreditkartenprufnummer</span></span>
- <span data-ttu-id="7e12d-1334">prüfziffer</span><span class="sxs-lookup"><span data-stu-id="7e12d-1334">prüfziffer</span></span>
- <span data-ttu-id="7e12d-1335">Prufziffer</span><span class="sxs-lookup"><span data-stu-id="7e12d-1335">prufziffer</span></span>
- <span data-ttu-id="7e12d-1336">sicherheits Kode</span><span class="sxs-lookup"><span data-stu-id="7e12d-1336">sicherheits Kode</span></span>
- <span data-ttu-id="7e12d-1337">sicherheitscode</span><span class="sxs-lookup"><span data-stu-id="7e12d-1337">sicherheitscode</span></span>
- <span data-ttu-id="7e12d-1338">sicherheitsnummer</span><span class="sxs-lookup"><span data-stu-id="7e12d-1338">sicherheitsnummer</span></span>
- <span data-ttu-id="7e12d-1339">verfalldatum</span><span class="sxs-lookup"><span data-stu-id="7e12d-1339">verfalldatum</span></span>
- <span data-ttu-id="7e12d-1340">codice di verifica</span><span class="sxs-lookup"><span data-stu-id="7e12d-1340">codice di verifica</span></span>
- <span data-ttu-id="7e12d-1341">Cod.</span><span class="sxs-lookup"><span data-stu-id="7e12d-1341">cod.</span></span> <span data-ttu-id="7e12d-1342">sicurezza</span><span class="sxs-lookup"><span data-stu-id="7e12d-1342">sicurezza</span></span>
- <span data-ttu-id="7e12d-1343">cod sicurezza</span><span class="sxs-lookup"><span data-stu-id="7e12d-1343">cod sicurezza</span></span>
- <span data-ttu-id="7e12d-1344">n autorizzazione</span><span class="sxs-lookup"><span data-stu-id="7e12d-1344">n autorizzazione</span></span>
- <span data-ttu-id="7e12d-1345">Código</span><span class="sxs-lookup"><span data-stu-id="7e12d-1345">código</span></span>
- <span data-ttu-id="7e12d-1346">Codigo</span><span class="sxs-lookup"><span data-stu-id="7e12d-1346">codigo</span></span>
- <span data-ttu-id="7e12d-1347">Cod.</span><span class="sxs-lookup"><span data-stu-id="7e12d-1347">cod.</span></span> <span data-ttu-id="7e12d-1348">SEG</span><span class="sxs-lookup"><span data-stu-id="7e12d-1348">seg</span></span>
- <span data-ttu-id="7e12d-1349">cod seg</span><span class="sxs-lookup"><span data-stu-id="7e12d-1349">cod seg</span></span>
- <span data-ttu-id="7e12d-1350">código de segurança</span><span class="sxs-lookup"><span data-stu-id="7e12d-1350">código de segurança</span></span>
- <span data-ttu-id="7e12d-1351">codigo de seguranca</span><span class="sxs-lookup"><span data-stu-id="7e12d-1351">codigo de seguranca</span></span>
- <span data-ttu-id="7e12d-1352">codigo de segurança</span><span class="sxs-lookup"><span data-stu-id="7e12d-1352">codigo de segurança</span></span>
- <span data-ttu-id="7e12d-1353">código de seguranca</span><span class="sxs-lookup"><span data-stu-id="7e12d-1353">código de seguranca</span></span>
- <span data-ttu-id="7e12d-1354">cód.</span><span class="sxs-lookup"><span data-stu-id="7e12d-1354">cód.</span></span> <span data-ttu-id="7e12d-1355">Segurança</span><span class="sxs-lookup"><span data-stu-id="7e12d-1355">segurança</span></span>
- <span data-ttu-id="7e12d-1356">Cod.</span><span class="sxs-lookup"><span data-stu-id="7e12d-1356">cod.</span></span> <span data-ttu-id="7e12d-1357">SEGURANCA Cod.</span><span class="sxs-lookup"><span data-stu-id="7e12d-1357">seguranca cod.</span></span> <span data-ttu-id="7e12d-1358">Segurança</span><span class="sxs-lookup"><span data-stu-id="7e12d-1358">segurança</span></span>
- <span data-ttu-id="7e12d-1359">cód.</span><span class="sxs-lookup"><span data-stu-id="7e12d-1359">cód.</span></span> <span data-ttu-id="7e12d-1360">seguranca</span><span class="sxs-lookup"><span data-stu-id="7e12d-1360">seguranca</span></span>
- <span data-ttu-id="7e12d-1361">cód segurança</span><span class="sxs-lookup"><span data-stu-id="7e12d-1361">cód segurança</span></span>
- <span data-ttu-id="7e12d-1362">Cod SEGURANCA Cod Segurança</span><span class="sxs-lookup"><span data-stu-id="7e12d-1362">cod seguranca cod segurança</span></span>
- <span data-ttu-id="7e12d-1363">cód seguranca</span><span class="sxs-lookup"><span data-stu-id="7e12d-1363">cód seguranca</span></span>
- <span data-ttu-id="7e12d-1364">número de verificação</span><span class="sxs-lookup"><span data-stu-id="7e12d-1364">número de verificação</span></span>
- <span data-ttu-id="7e12d-1365">numero de verificacao</span><span class="sxs-lookup"><span data-stu-id="7e12d-1365">numero de verificacao</span></span>
- <span data-ttu-id="7e12d-1366">ablauf</span><span class="sxs-lookup"><span data-stu-id="7e12d-1366">ablauf</span></span>
- <span data-ttu-id="7e12d-1367">gültig bis</span><span class="sxs-lookup"><span data-stu-id="7e12d-1367">gültig bis</span></span>
- <span data-ttu-id="7e12d-1368">gültigkeitsdatum</span><span class="sxs-lookup"><span data-stu-id="7e12d-1368">gültigkeitsdatum</span></span>
- <span data-ttu-id="7e12d-1369">gultig bis</span><span class="sxs-lookup"><span data-stu-id="7e12d-1369">gultig bis</span></span>
- <span data-ttu-id="7e12d-1370">gultigkeitsdatum</span><span class="sxs-lookup"><span data-stu-id="7e12d-1370">gultigkeitsdatum</span></span>
- <span data-ttu-id="7e12d-1371">scadenza</span><span class="sxs-lookup"><span data-stu-id="7e12d-1371">scadenza</span></span>
- <span data-ttu-id="7e12d-1372">data scad</span><span class="sxs-lookup"><span data-stu-id="7e12d-1372">data scad</span></span>
- <span data-ttu-id="7e12d-1373">fecha de expiracion</span><span class="sxs-lookup"><span data-stu-id="7e12d-1373">fecha de expiracion</span></span>
- <span data-ttu-id="7e12d-1374">fecha de venc</span><span class="sxs-lookup"><span data-stu-id="7e12d-1374">fecha de venc</span></span>
- <span data-ttu-id="7e12d-1375">vencimiento</span><span class="sxs-lookup"><span data-stu-id="7e12d-1375">vencimiento</span></span>
- <span data-ttu-id="7e12d-1376">válido hasta</span><span class="sxs-lookup"><span data-stu-id="7e12d-1376">válido hasta</span></span>
- <span data-ttu-id="7e12d-1377">valido hasta</span><span class="sxs-lookup"><span data-stu-id="7e12d-1377">valido hasta</span></span>
- <span data-ttu-id="7e12d-1378">VTO</span><span class="sxs-lookup"><span data-stu-id="7e12d-1378">vto</span></span>
- <span data-ttu-id="7e12d-1379">data de expiração</span><span class="sxs-lookup"><span data-stu-id="7e12d-1379">data de expiração</span></span>
- <span data-ttu-id="7e12d-1380">data de expiracao</span><span class="sxs-lookup"><span data-stu-id="7e12d-1380">data de expiracao</span></span>
- <span data-ttu-id="7e12d-1381">data em que expira</span><span class="sxs-lookup"><span data-stu-id="7e12d-1381">data em que expira</span></span>
- <span data-ttu-id="7e12d-1382">validade</span><span class="sxs-lookup"><span data-stu-id="7e12d-1382">validade</span></span>
- <span data-ttu-id="7e12d-1383">Valor</span><span class="sxs-lookup"><span data-stu-id="7e12d-1383">valor</span></span>
- <span data-ttu-id="7e12d-1384">vencimento</span><span class="sxs-lookup"><span data-stu-id="7e12d-1384">vencimento</span></span>
- <span data-ttu-id="7e12d-1385">Venc</span><span class="sxs-lookup"><span data-stu-id="7e12d-1385">Venc</span></span> 

#### <a name="keyword_cc_name"></a><span data-ttu-id="7e12d-1386">Keyword_cc_name</span><span class="sxs-lookup"><span data-stu-id="7e12d-1386">Keyword_cc_name</span></span>

- <span data-ttu-id="7e12d-1387">Amex</span><span class="sxs-lookup"><span data-stu-id="7e12d-1387">amex</span></span>
- <span data-ttu-id="7e12d-1388">american express</span><span class="sxs-lookup"><span data-stu-id="7e12d-1388">american express</span></span>
- <span data-ttu-id="7e12d-1389">AmericanExpress</span><span class="sxs-lookup"><span data-stu-id="7e12d-1389">americanexpress</span></span>
- <span data-ttu-id="7e12d-1390">Esempio</span><span class="sxs-lookup"><span data-stu-id="7e12d-1390">Visa</span></span>
- <span data-ttu-id="7e12d-1391">Mastercard</span><span class="sxs-lookup"><span data-stu-id="7e12d-1391">mastercard</span></span>
- <span data-ttu-id="7e12d-1392">master card</span><span class="sxs-lookup"><span data-stu-id="7e12d-1392">master card</span></span>
- <span data-ttu-id="7e12d-1393">MC</span><span class="sxs-lookup"><span data-stu-id="7e12d-1393">mc</span></span> 
- <span data-ttu-id="7e12d-1394">Mastercard</span><span class="sxs-lookup"><span data-stu-id="7e12d-1394">mastercards</span></span>
- <span data-ttu-id="7e12d-1395">master cards</span><span class="sxs-lookup"><span data-stu-id="7e12d-1395">master cards</span></span>
- <span data-ttu-id="7e12d-1396">diner's Club</span><span class="sxs-lookup"><span data-stu-id="7e12d-1396">diner's Club</span></span>
- <span data-ttu-id="7e12d-1397">diners club</span><span class="sxs-lookup"><span data-stu-id="7e12d-1397">diners club</span></span>
- <span data-ttu-id="7e12d-1398">DinersClub</span><span class="sxs-lookup"><span data-stu-id="7e12d-1398">dinersclub</span></span>
- <span data-ttu-id="7e12d-1399">discover card</span><span class="sxs-lookup"><span data-stu-id="7e12d-1399">discover card</span></span>
- <span data-ttu-id="7e12d-1400">discovercard</span><span class="sxs-lookup"><span data-stu-id="7e12d-1400">discovercard</span></span>
- <span data-ttu-id="7e12d-1401">discover cards</span><span class="sxs-lookup"><span data-stu-id="7e12d-1401">discover cards</span></span>
- <span data-ttu-id="7e12d-1402">JCB</span><span class="sxs-lookup"><span data-stu-id="7e12d-1402">JCB</span></span>
- <span data-ttu-id="7e12d-1403">japanese card bureau</span><span class="sxs-lookup"><span data-stu-id="7e12d-1403">japanese card bureau</span></span>
- <span data-ttu-id="7e12d-1404">carte blanche</span><span class="sxs-lookup"><span data-stu-id="7e12d-1404">carte blanche</span></span>
- <span data-ttu-id="7e12d-1405">carteblanche</span><span class="sxs-lookup"><span data-stu-id="7e12d-1405">carteblanche</span></span>
- <span data-ttu-id="7e12d-1406">credit card</span><span class="sxs-lookup"><span data-stu-id="7e12d-1406">credit card</span></span>
- <span data-ttu-id="7e12d-1407">CC #</span><span class="sxs-lookup"><span data-stu-id="7e12d-1407">cc#</span></span>
- <span data-ttu-id="7e12d-1408">CC #:</span><span class="sxs-lookup"><span data-stu-id="7e12d-1408">cc#:</span></span>
- <span data-ttu-id="7e12d-1409">expiration date</span><span class="sxs-lookup"><span data-stu-id="7e12d-1409">expiration date</span></span>
- <span data-ttu-id="7e12d-1410">exp date</span><span class="sxs-lookup"><span data-stu-id="7e12d-1410">exp date</span></span>
- <span data-ttu-id="7e12d-1411">expiry date</span><span class="sxs-lookup"><span data-stu-id="7e12d-1411">expiry date</span></span>
- <span data-ttu-id="7e12d-1412">date d’expiration</span><span class="sxs-lookup"><span data-stu-id="7e12d-1412">date d’expiration</span></span>
- <span data-ttu-id="7e12d-1413">date d'exp</span><span class="sxs-lookup"><span data-stu-id="7e12d-1413">date d'exp</span></span>
- <span data-ttu-id="7e12d-1414">date expiration</span><span class="sxs-lookup"><span data-stu-id="7e12d-1414">date expiration</span></span>
- <span data-ttu-id="7e12d-1415">bank card</span><span class="sxs-lookup"><span data-stu-id="7e12d-1415">bank card</span></span>
- <span data-ttu-id="7e12d-1416">Bankcard</span><span class="sxs-lookup"><span data-stu-id="7e12d-1416">bankcard</span></span>
- <span data-ttu-id="7e12d-1417">card number</span><span class="sxs-lookup"><span data-stu-id="7e12d-1417">card number</span></span>
- <span data-ttu-id="7e12d-1418">card num</span><span class="sxs-lookup"><span data-stu-id="7e12d-1418">card num</span></span>
- <span data-ttu-id="7e12d-1419">cardnumber</span><span class="sxs-lookup"><span data-stu-id="7e12d-1419">cardnumber</span></span>
- <span data-ttu-id="7e12d-1420">cardnumbers</span><span class="sxs-lookup"><span data-stu-id="7e12d-1420">cardnumbers</span></span>
- <span data-ttu-id="7e12d-1421">card numbers</span><span class="sxs-lookup"><span data-stu-id="7e12d-1421">card numbers</span></span>
- <span data-ttu-id="7e12d-1422">CreditCard</span><span class="sxs-lookup"><span data-stu-id="7e12d-1422">creditcard</span></span>
- <span data-ttu-id="7e12d-1423">credit cards</span><span class="sxs-lookup"><span data-stu-id="7e12d-1423">credit cards</span></span>
- <span data-ttu-id="7e12d-1424">creditcards.com</span><span class="sxs-lookup"><span data-stu-id="7e12d-1424">creditcards</span></span>
- <span data-ttu-id="7e12d-1425">Ccn</span><span class="sxs-lookup"><span data-stu-id="7e12d-1425">ccn</span></span>
- <span data-ttu-id="7e12d-1426">card holder</span><span class="sxs-lookup"><span data-stu-id="7e12d-1426">card holder</span></span>
- <span data-ttu-id="7e12d-1427">titolare</span><span class="sxs-lookup"><span data-stu-id="7e12d-1427">cardholder</span></span>
- <span data-ttu-id="7e12d-1428">card holders</span><span class="sxs-lookup"><span data-stu-id="7e12d-1428">card holders</span></span>
- <span data-ttu-id="7e12d-1429">titolari</span><span class="sxs-lookup"><span data-stu-id="7e12d-1429">cardholders</span></span>
- <span data-ttu-id="7e12d-1430">check card</span><span class="sxs-lookup"><span data-stu-id="7e12d-1430">check card</span></span>
- <span data-ttu-id="7e12d-1431">checkcard</span><span class="sxs-lookup"><span data-stu-id="7e12d-1431">checkcard</span></span>
- <span data-ttu-id="7e12d-1432">check cards</span><span class="sxs-lookup"><span data-stu-id="7e12d-1432">check cards</span></span>
- <span data-ttu-id="7e12d-1433">checkcards</span><span class="sxs-lookup"><span data-stu-id="7e12d-1433">checkcards</span></span>
- <span data-ttu-id="7e12d-1434">debit card</span><span class="sxs-lookup"><span data-stu-id="7e12d-1434">debit card</span></span>
- <span data-ttu-id="7e12d-1435">debitcard</span><span class="sxs-lookup"><span data-stu-id="7e12d-1435">debitcard</span></span>
- <span data-ttu-id="7e12d-1436">debit cards</span><span class="sxs-lookup"><span data-stu-id="7e12d-1436">debit cards</span></span>
- <span data-ttu-id="7e12d-1437">debitcards</span><span class="sxs-lookup"><span data-stu-id="7e12d-1437">debitcards</span></span>
- <span data-ttu-id="7e12d-1438">atm card</span><span class="sxs-lookup"><span data-stu-id="7e12d-1438">atm card</span></span>
- <span data-ttu-id="7e12d-1439">atmcard</span><span class="sxs-lookup"><span data-stu-id="7e12d-1439">atmcard</span></span>
- <span data-ttu-id="7e12d-1440">atm cards</span><span class="sxs-lookup"><span data-stu-id="7e12d-1440">atm cards</span></span>
- <span data-ttu-id="7e12d-1441">atmcards</span><span class="sxs-lookup"><span data-stu-id="7e12d-1441">atmcards</span></span>
- <span data-ttu-id="7e12d-1442">Enroute</span><span class="sxs-lookup"><span data-stu-id="7e12d-1442">enroute</span></span>
- <span data-ttu-id="7e12d-1443">en route</span><span class="sxs-lookup"><span data-stu-id="7e12d-1443">en route</span></span>
- <span data-ttu-id="7e12d-1444">card type</span><span class="sxs-lookup"><span data-stu-id="7e12d-1444">card type</span></span>
- <span data-ttu-id="7e12d-1445">carte bancaire</span><span class="sxs-lookup"><span data-stu-id="7e12d-1445">carte bancaire</span></span>
- <span data-ttu-id="7e12d-1446">carte de crédit</span><span class="sxs-lookup"><span data-stu-id="7e12d-1446">carte de crédit</span></span>
- <span data-ttu-id="7e12d-1447">carte de credit</span><span class="sxs-lookup"><span data-stu-id="7e12d-1447">carte de credit</span></span>
- <span data-ttu-id="7e12d-1448">numéro de carte</span><span class="sxs-lookup"><span data-stu-id="7e12d-1448">numéro de carte</span></span>
- <span data-ttu-id="7e12d-1449">numero de carte</span><span class="sxs-lookup"><span data-stu-id="7e12d-1449">numero de carte</span></span>
- <span data-ttu-id="7e12d-1450">nº de la carte</span><span class="sxs-lookup"><span data-stu-id="7e12d-1450">nº de la carte</span></span>
- <span data-ttu-id="7e12d-1451">nº de carte</span><span class="sxs-lookup"><span data-stu-id="7e12d-1451">nº de carte</span></span>
- <span data-ttu-id="7e12d-1452">kreditkarte</span><span class="sxs-lookup"><span data-stu-id="7e12d-1452">kreditkarte</span></span>
- <span data-ttu-id="7e12d-1453">Karte</span><span class="sxs-lookup"><span data-stu-id="7e12d-1453">karte</span></span>
- <span data-ttu-id="7e12d-1454">karteninhaber</span><span class="sxs-lookup"><span data-stu-id="7e12d-1454">karteninhaber</span></span>
- <span data-ttu-id="7e12d-1455">karteninhabers</span><span class="sxs-lookup"><span data-stu-id="7e12d-1455">karteninhabers</span></span>
- <span data-ttu-id="7e12d-1456">kreditkarteninhaber</span><span class="sxs-lookup"><span data-stu-id="7e12d-1456">kreditkarteninhaber</span></span>
- <span data-ttu-id="7e12d-1457">kreditkarteninstitut</span><span class="sxs-lookup"><span data-stu-id="7e12d-1457">kreditkarteninstitut</span></span>
- <span data-ttu-id="7e12d-1458">kreditkartentyp</span><span class="sxs-lookup"><span data-stu-id="7e12d-1458">kreditkartentyp</span></span>
- <span data-ttu-id="7e12d-1459">eigentümername</span><span class="sxs-lookup"><span data-stu-id="7e12d-1459">eigentümername</span></span>
- <span data-ttu-id="7e12d-1460">kartennr</span><span class="sxs-lookup"><span data-stu-id="7e12d-1460">kartennr</span></span> 
- <span data-ttu-id="7e12d-1461">kartennummer</span><span class="sxs-lookup"><span data-stu-id="7e12d-1461">kartennummer</span></span>
- <span data-ttu-id="7e12d-1462">kreditkartennummer</span><span class="sxs-lookup"><span data-stu-id="7e12d-1462">kreditkartennummer</span></span>
- <span data-ttu-id="7e12d-1463">Kreditkarten-Nummer</span><span class="sxs-lookup"><span data-stu-id="7e12d-1463">kreditkarten-nummer</span></span>
- <span data-ttu-id="7e12d-1464">carta di credito</span><span class="sxs-lookup"><span data-stu-id="7e12d-1464">carta di credito</span></span>
- <span data-ttu-id="7e12d-1465">carta credito</span><span class="sxs-lookup"><span data-stu-id="7e12d-1465">carta credito</span></span>
- <span data-ttu-id="7e12d-1466">carta</span><span class="sxs-lookup"><span data-stu-id="7e12d-1466">carta</span></span>
- <span data-ttu-id="7e12d-1467">n carta</span><span class="sxs-lookup"><span data-stu-id="7e12d-1467">n carta</span></span>
- <span data-ttu-id="7e12d-1468">Nr.</span><span class="sxs-lookup"><span data-stu-id="7e12d-1468">nr.</span></span> <span data-ttu-id="7e12d-1469">carta</span><span class="sxs-lookup"><span data-stu-id="7e12d-1469">carta</span></span>
- <span data-ttu-id="7e12d-1470">nr carta</span><span class="sxs-lookup"><span data-stu-id="7e12d-1470">nr carta</span></span>
- <span data-ttu-id="7e12d-1471">numero carta</span><span class="sxs-lookup"><span data-stu-id="7e12d-1471">numero carta</span></span>
- <span data-ttu-id="7e12d-1472">numero della carta</span><span class="sxs-lookup"><span data-stu-id="7e12d-1472">numero della carta</span></span>
- <span data-ttu-id="7e12d-1473">numero di carta</span><span class="sxs-lookup"><span data-stu-id="7e12d-1473">numero di carta</span></span>
- <span data-ttu-id="7e12d-1474">tarjeta credito</span><span class="sxs-lookup"><span data-stu-id="7e12d-1474">tarjeta credito</span></span>
- <span data-ttu-id="7e12d-1475">tarjeta de credito</span><span class="sxs-lookup"><span data-stu-id="7e12d-1475">tarjeta de credito</span></span>
- <span data-ttu-id="7e12d-1476">tarjeta crédito</span><span class="sxs-lookup"><span data-stu-id="7e12d-1476">tarjeta crédito</span></span>
- <span data-ttu-id="7e12d-1477">tarjeta de crédito</span><span class="sxs-lookup"><span data-stu-id="7e12d-1477">tarjeta de crédito</span></span>
- <span data-ttu-id="7e12d-1478">tarjeta de atm</span><span class="sxs-lookup"><span data-stu-id="7e12d-1478">tarjeta de atm</span></span>
- <span data-ttu-id="7e12d-1479">tarjeta atm</span><span class="sxs-lookup"><span data-stu-id="7e12d-1479">tarjeta atm</span></span>
- <span data-ttu-id="7e12d-1480">tarjeta debito</span><span class="sxs-lookup"><span data-stu-id="7e12d-1480">tarjeta debito</span></span>
- <span data-ttu-id="7e12d-1481">tarjeta de debito</span><span class="sxs-lookup"><span data-stu-id="7e12d-1481">tarjeta de debito</span></span>
- <span data-ttu-id="7e12d-1482">tarjeta débito</span><span class="sxs-lookup"><span data-stu-id="7e12d-1482">tarjeta débito</span></span>
- <span data-ttu-id="7e12d-1483">tarjeta de débito</span><span class="sxs-lookup"><span data-stu-id="7e12d-1483">tarjeta de débito</span></span>
- <span data-ttu-id="7e12d-1484">nº de tarjeta</span><span class="sxs-lookup"><span data-stu-id="7e12d-1484">nº de tarjeta</span></span>
- <span data-ttu-id="7e12d-1485">No.</span><span class="sxs-lookup"><span data-stu-id="7e12d-1485">no.</span></span> <span data-ttu-id="7e12d-1486">de tarjeta</span><span class="sxs-lookup"><span data-stu-id="7e12d-1486">de tarjeta</span></span>
- <span data-ttu-id="7e12d-1487">no de tarjeta</span><span class="sxs-lookup"><span data-stu-id="7e12d-1487">no de tarjeta</span></span>
- <span data-ttu-id="7e12d-1488">numero de tarjeta</span><span class="sxs-lookup"><span data-stu-id="7e12d-1488">numero de tarjeta</span></span>
- <span data-ttu-id="7e12d-1489">número de tarjeta</span><span class="sxs-lookup"><span data-stu-id="7e12d-1489">número de tarjeta</span></span>
- <span data-ttu-id="7e12d-1490">tarjeta no</span><span class="sxs-lookup"><span data-stu-id="7e12d-1490">tarjeta no</span></span>
- <span data-ttu-id="7e12d-1491">tarjetahabiente</span><span class="sxs-lookup"><span data-stu-id="7e12d-1491">tarjetahabiente</span></span>
- <span data-ttu-id="7e12d-1492">cartão de crédito</span><span class="sxs-lookup"><span data-stu-id="7e12d-1492">cartão de crédito</span></span>
- <span data-ttu-id="7e12d-1493">cartão de credito</span><span class="sxs-lookup"><span data-stu-id="7e12d-1493">cartão de credito</span></span>
- <span data-ttu-id="7e12d-1494">cartao de crédito</span><span class="sxs-lookup"><span data-stu-id="7e12d-1494">cartao de crédito</span></span>
- <span data-ttu-id="7e12d-1495">cartao de credito</span><span class="sxs-lookup"><span data-stu-id="7e12d-1495">cartao de credito</span></span>
- <span data-ttu-id="7e12d-1496">cartão de débito</span><span class="sxs-lookup"><span data-stu-id="7e12d-1496">cartão de débito</span></span>
- <span data-ttu-id="7e12d-1497">cartao de débito</span><span class="sxs-lookup"><span data-stu-id="7e12d-1497">cartao de débito</span></span>
- <span data-ttu-id="7e12d-1498">cartão de debito</span><span class="sxs-lookup"><span data-stu-id="7e12d-1498">cartão de debito</span></span>
- <span data-ttu-id="7e12d-1499">cartao de debito</span><span class="sxs-lookup"><span data-stu-id="7e12d-1499">cartao de debito</span></span>
- <span data-ttu-id="7e12d-1500">débito automático</span><span class="sxs-lookup"><span data-stu-id="7e12d-1500">débito automático</span></span>
- <span data-ttu-id="7e12d-1501">debito automatico</span><span class="sxs-lookup"><span data-stu-id="7e12d-1501">debito automatico</span></span>
- <span data-ttu-id="7e12d-1502">número do cartão</span><span class="sxs-lookup"><span data-stu-id="7e12d-1502">número do cartão</span></span>
- <span data-ttu-id="7e12d-1503">numero do cartão</span><span class="sxs-lookup"><span data-stu-id="7e12d-1503">numero do cartão</span></span> 
- <span data-ttu-id="7e12d-1504">número do cartao</span><span class="sxs-lookup"><span data-stu-id="7e12d-1504">número do cartao</span></span>
- <span data-ttu-id="7e12d-1505">numero do cartao</span><span class="sxs-lookup"><span data-stu-id="7e12d-1505">numero do cartao</span></span>
- <span data-ttu-id="7e12d-1506">número de cartão</span><span class="sxs-lookup"><span data-stu-id="7e12d-1506">número de cartão</span></span>
- <span data-ttu-id="7e12d-1507">numero de cartão</span><span class="sxs-lookup"><span data-stu-id="7e12d-1507">numero de cartão</span></span>
- <span data-ttu-id="7e12d-1508">número de cartao</span><span class="sxs-lookup"><span data-stu-id="7e12d-1508">número de cartao</span></span>
- <span data-ttu-id="7e12d-1509">numero de cartao</span><span class="sxs-lookup"><span data-stu-id="7e12d-1509">numero de cartao</span></span>
- <span data-ttu-id="7e12d-1510">nº do cartão</span><span class="sxs-lookup"><span data-stu-id="7e12d-1510">nº do cartão</span></span>
- <span data-ttu-id="7e12d-1511">nº do cartao</span><span class="sxs-lookup"><span data-stu-id="7e12d-1511">nº do cartao</span></span>
- <span data-ttu-id="7e12d-1512">n º.</span><span class="sxs-lookup"><span data-stu-id="7e12d-1512">nº.</span></span> <span data-ttu-id="7e12d-1513">do cartão</span><span class="sxs-lookup"><span data-stu-id="7e12d-1513">do cartão</span></span>
- <span data-ttu-id="7e12d-1514">no do cartão</span><span class="sxs-lookup"><span data-stu-id="7e12d-1514">no do cartão</span></span>
- <span data-ttu-id="7e12d-1515">no do cartao</span><span class="sxs-lookup"><span data-stu-id="7e12d-1515">no do cartao</span></span>
- <span data-ttu-id="7e12d-1516">No.</span><span class="sxs-lookup"><span data-stu-id="7e12d-1516">no.</span></span> <span data-ttu-id="7e12d-1517">do cartão</span><span class="sxs-lookup"><span data-stu-id="7e12d-1517">do cartão</span></span>
- <span data-ttu-id="7e12d-1518">No.</span><span class="sxs-lookup"><span data-stu-id="7e12d-1518">no.</span></span> <span data-ttu-id="7e12d-1519">do cartao</span><span class="sxs-lookup"><span data-stu-id="7e12d-1519">do cartao</span></span> 
   
## <a name="croatia-identity-card-number"></a><span data-ttu-id="7e12d-1520">Numero di carta di identità della Croazia</span><span class="sxs-lookup"><span data-stu-id="7e12d-1520">Croatia Identity Card Number</span></span>

### <a name="format"></a><span data-ttu-id="7e12d-1521">Formato</span><span class="sxs-lookup"><span data-stu-id="7e12d-1521">Format</span></span>

<span data-ttu-id="7e12d-1522">9 cifre</span><span class="sxs-lookup"><span data-stu-id="7e12d-1522">Nine digits</span></span>

### <a name="pattern"></a><span data-ttu-id="7e12d-1523">Modello</span><span class="sxs-lookup"><span data-stu-id="7e12d-1523">Pattern</span></span>

<span data-ttu-id="7e12d-1524">9 cifre consecutive</span><span class="sxs-lookup"><span data-stu-id="7e12d-1524">Nine consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="7e12d-1525">Checksum</span><span class="sxs-lookup"><span data-stu-id="7e12d-1525">Checksum</span></span>

<span data-ttu-id="7e12d-1526">No</span><span class="sxs-lookup"><span data-stu-id="7e12d-1526">No</span></span>

### <a name="definition"></a><span data-ttu-id="7e12d-1527">Definizione</span><span class="sxs-lookup"><span data-stu-id="7e12d-1527">Definition</span></span>

<span data-ttu-id="7e12d-1528">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="7e12d-1528">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="7e12d-1529">La funzione Func_croatia_id_card trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="7e12d-1529">The function Func_croatia_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="7e12d-1530">Viene trovata una parola chiave da Keyword_croatia_id_card.</span><span class="sxs-lookup"><span data-stu-id="7e12d-1530">A keyword from Keyword_croatia_id_card is found.</span></span>

```xml
<!--Croatia Identity Card Number-->
<Entity id="ff12f884-c20a-4189-b185-34c8e7258d47" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_croatia_id_card"/>
     <Match idRef="Keyword_croatia_id_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="7e12d-1531">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="7e12d-1531">Keywords</span></span>

#### <a name="keyword_croatia_id_card"></a><span data-ttu-id="7e12d-1532">Keyword_croatia_id_card</span><span class="sxs-lookup"><span data-stu-id="7e12d-1532">Keyword_croatia_id_card</span></span>

- <span data-ttu-id="7e12d-1533">Carta d’identità croata</span><span class="sxs-lookup"><span data-stu-id="7e12d-1533">Croatian identity card</span></span>
- <span data-ttu-id="7e12d-1534">Osobna iskaznica</span><span class="sxs-lookup"><span data-stu-id="7e12d-1534">Osobna iskaznica</span></span>

   
## <a name="croatia-personal-identification-oib-number"></a><span data-ttu-id="7e12d-1535">Numero di identificazione personale (OIB) - Croazia</span><span class="sxs-lookup"><span data-stu-id="7e12d-1535">Croatia Personal Identification (OIB) Number</span></span>

### <a name="format"></a><span data-ttu-id="7e12d-1536">Formato</span><span class="sxs-lookup"><span data-stu-id="7e12d-1536">Format</span></span>

<span data-ttu-id="7e12d-1537">11 cifre</span><span class="sxs-lookup"><span data-stu-id="7e12d-1537">11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="7e12d-1538">Modello</span><span class="sxs-lookup"><span data-stu-id="7e12d-1538">Pattern</span></span>

<span data-ttu-id="7e12d-1539">11 cifre:</span><span class="sxs-lookup"><span data-stu-id="7e12d-1539">11 digits:</span></span>
- <span data-ttu-id="7e12d-1540">10 cifre</span><span class="sxs-lookup"><span data-stu-id="7e12d-1540">10 digits</span></span> 
- <span data-ttu-id="7e12d-1541">La cifra finale è una cifra di controllo ai fini dello scambio di dati internazionali, le lettere HR vengono aggiunte prima delle undici cifre.</span><span class="sxs-lookup"><span data-stu-id="7e12d-1541">Final digit is a check digit For the purposes of international data exchange, the letters HR are added preceding the eleven digits.</span></span>

### <a name="checksum"></a><span data-ttu-id="7e12d-1542">Checksum</span><span class="sxs-lookup"><span data-stu-id="7e12d-1542">Checksum</span></span>

<span data-ttu-id="7e12d-1543">Sì</span><span class="sxs-lookup"><span data-stu-id="7e12d-1543">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="7e12d-1544">Definizione</span><span class="sxs-lookup"><span data-stu-id="7e12d-1544">Definition</span></span>

<span data-ttu-id="7e12d-1545">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="7e12d-1545">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="7e12d-1546">La funzione Func_croatia_oib_number trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="7e12d-1546">The function Func_croatia_oib_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="7e12d-1547">Viene trovata una parola chiave da Keyword_croatia_oib_number.</span><span class="sxs-lookup"><span data-stu-id="7e12d-1547">A keyword from Keyword_croatia_oib_number is found.</span></span>
- <span data-ttu-id="7e12d-1548">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="7e12d-1548">The checksum passes.</span></span>

<span data-ttu-id="7e12d-1549">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="7e12d-1549">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="7e12d-1550">La funzione Func_croatia_oib_number trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="7e12d-1550">The function Func_croatia_oib_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="7e12d-1551">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="7e12d-1551">The checksum passes.</span></span>

```xml
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

### <a name="keywords"></a><span data-ttu-id="7e12d-1552">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="7e12d-1552">Keywords</span></span>

#### <a name="keyword_croatia_oib_number"></a><span data-ttu-id="7e12d-1553">Keyword_croatia_oib_number</span><span class="sxs-lookup"><span data-stu-id="7e12d-1553">Keyword_croatia_oib_number</span></span>

- <span data-ttu-id="7e12d-1554">Codice PIN</span><span class="sxs-lookup"><span data-stu-id="7e12d-1554">Personal Identification Number</span></span>
- <span data-ttu-id="7e12d-1555">Osobni identifikacijski broj</span><span class="sxs-lookup"><span data-stu-id="7e12d-1555">Osobni identifikacijski broj</span></span> 
- <span data-ttu-id="7e12d-1556">OIB</span><span class="sxs-lookup"><span data-stu-id="7e12d-1556">OIB</span></span> 

   
## <a name="czech-personal-identity-number"></a><span data-ttu-id="7e12d-1557">Numero di identità personale ceco</span><span class="sxs-lookup"><span data-stu-id="7e12d-1557">Czech Personal Identity Number</span></span>

### <a name="format"></a><span data-ttu-id="7e12d-1558">Formato</span><span class="sxs-lookup"><span data-stu-id="7e12d-1558">Format</span></span>

<span data-ttu-id="7e12d-1559">Nove cifre con Slash opzionale (formato precedente) 10 cifre con barra di inoltro facoltativa (nuovo formato)</span><span class="sxs-lookup"><span data-stu-id="7e12d-1559">Nine digits with optional forward slash (old format) 10 digits with optional forward slash (new format)</span></span>

### <a name="pattern"></a><span data-ttu-id="7e12d-1560">Modello</span><span class="sxs-lookup"><span data-stu-id="7e12d-1560">Pattern</span></span>

<span data-ttu-id="7e12d-1561">Nove cifre (formato obsoleto):</span><span class="sxs-lookup"><span data-stu-id="7e12d-1561">Nine digits (old format):</span></span>
- <span data-ttu-id="7e12d-1562">9 cifre</span><span class="sxs-lookup"><span data-stu-id="7e12d-1562">Nine digits</span></span>

<span data-ttu-id="7e12d-1563">O</span><span class="sxs-lookup"><span data-stu-id="7e12d-1563">OR</span></span>

- <span data-ttu-id="7e12d-1564">Sei cifre che rappresentano la data di nascita</span><span class="sxs-lookup"><span data-stu-id="7e12d-1564">Six digits that represent date of birth</span></span>
- <span data-ttu-id="7e12d-1565">Una barra</span><span class="sxs-lookup"><span data-stu-id="7e12d-1565">A forward slash</span></span>
- <span data-ttu-id="7e12d-1566">Tre cifre</span><span class="sxs-lookup"><span data-stu-id="7e12d-1566">Three digits</span></span>

<span data-ttu-id="7e12d-1567">10 cifre (nuovo formato):</span><span class="sxs-lookup"><span data-stu-id="7e12d-1567">10 digits (new format):</span></span>
- <span data-ttu-id="7e12d-1568">10 cifre</span><span class="sxs-lookup"><span data-stu-id="7e12d-1568">10 digits</span></span>

<span data-ttu-id="7e12d-1569">O</span><span class="sxs-lookup"><span data-stu-id="7e12d-1569">OR</span></span>

- <span data-ttu-id="7e12d-1570">Sei cifre che rappresentano la data di nascita</span><span class="sxs-lookup"><span data-stu-id="7e12d-1570">Six digits that represent date of birth</span></span>
- <span data-ttu-id="7e12d-1571">Una barra</span><span class="sxs-lookup"><span data-stu-id="7e12d-1571">A forward slash</span></span> 
- <span data-ttu-id="7e12d-1572">Quattro cifre in cui l'ultima cifra è una cifra di controllo</span><span class="sxs-lookup"><span data-stu-id="7e12d-1572">Four digits where last digit is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="7e12d-1573">Checksum</span><span class="sxs-lookup"><span data-stu-id="7e12d-1573">Checksum</span></span>

<span data-ttu-id="7e12d-1574">Sì</span><span class="sxs-lookup"><span data-stu-id="7e12d-1574">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="7e12d-1575">Definizione</span><span class="sxs-lookup"><span data-stu-id="7e12d-1575">Definition</span></span>

<span data-ttu-id="7e12d-1576">Un criterio DLP è 85% fiducioso di aver rilevato questo tipo di informazioni riservate se, entro 300 caratteri: la funzione Func_czech_id_card trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="7e12d-1576">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The function Func_czech_id_card finds content that matches the pattern.</span></span>
<span data-ttu-id="7e12d-1577">Viene trovata una parola chiave da Keyword_czech_id_card.</span><span class="sxs-lookup"><span data-stu-id="7e12d-1577">A keyword from Keyword_czech_id_card is found.</span></span>
<span data-ttu-id="7e12d-1578">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="7e12d-1578">The checksum passes.</span></span>

```xml
<!-- Czech Personal Identity Number -->
<Entity id="60c0725a-4eb6-455b-9dda-05d8a7396497"      patternsProximity="300" recommendedConfidence="85">
   <Pattern confidenceLevel="85">
      <IdMatch idRef="Func_czech_id_card" />
      <Match idRef="Keyword_czech_id_card" />
   </Pattern>
</Entity>
```
### <a name="keywords"></a><span data-ttu-id="7e12d-1579">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="7e12d-1579">Keywords</span></span>

- <span data-ttu-id="7e12d-1580">numero di identità personale ceco</span><span class="sxs-lookup"><span data-stu-id="7e12d-1580">czech personal identity number</span></span>
- <span data-ttu-id="7e12d-1581">Rodné číslo</span><span class="sxs-lookup"><span data-stu-id="7e12d-1581">Rodné číslo</span></span>
   
## <a name="denmark-personal-identification-number"></a><span data-ttu-id="7e12d-1582">Codice PIN - Danimarca</span><span class="sxs-lookup"><span data-stu-id="7e12d-1582">Denmark Personal Identification Number</span></span>

### <a name="format"></a><span data-ttu-id="7e12d-1583">Formato</span><span class="sxs-lookup"><span data-stu-id="7e12d-1583">Format</span></span>

<span data-ttu-id="7e12d-1584">10 cifre contenenti una lineetta</span><span class="sxs-lookup"><span data-stu-id="7e12d-1584">10 digits containing a hyphen</span></span>

### <a name="pattern"></a><span data-ttu-id="7e12d-1585">Modello</span><span class="sxs-lookup"><span data-stu-id="7e12d-1585">Pattern</span></span>

<span data-ttu-id="7e12d-1586">10 cifre:</span><span class="sxs-lookup"><span data-stu-id="7e12d-1586">10 digits:</span></span>
- <span data-ttu-id="7e12d-1587">Sei cifre nel formato GGMMAA, ovvero la data di nascita</span><span class="sxs-lookup"><span data-stu-id="7e12d-1587">Six digits in the format DDMMYY which are the date of birth</span></span> 
- <span data-ttu-id="7e12d-1588">Una lineetta</span><span class="sxs-lookup"><span data-stu-id="7e12d-1588">A hyphen</span></span> 
- <span data-ttu-id="7e12d-1589">Quattro cifre, dove l'ultima è una cifra di controllo</span><span class="sxs-lookup"><span data-stu-id="7e12d-1589">Four digits where the final digit is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="7e12d-1590">Checksum</span><span class="sxs-lookup"><span data-stu-id="7e12d-1590">Checksum</span></span>

<span data-ttu-id="7e12d-1591">Sì</span><span class="sxs-lookup"><span data-stu-id="7e12d-1591">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="7e12d-1592">Definizione</span><span class="sxs-lookup"><span data-stu-id="7e12d-1592">Definition</span></span>

<span data-ttu-id="7e12d-1593">Un criterio DLP è 75% fiducioso di aver rilevato questo tipo di informazioni riservate se, entro 300 caratteri: l'espressione regolare Regex_denmark_id trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="7e12d-1593">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The regular expression Regex_denmark_id finds content that matches the pattern.</span></span>
<span data-ttu-id="7e12d-1594">Viene trovata una parola chiave da Keyword_denmark_id.</span><span class="sxs-lookup"><span data-stu-id="7e12d-1594">A keyword from Keyword_denmark_id is found.</span></span>
<span data-ttu-id="7e12d-1595">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="7e12d-1595">The checksum passes.</span></span>

```xml
<!-- Denmark Personal Identification Number -->
<Entity id="6c4f2fef-56e1-4c00-8093-88d7a01cf460" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_denmark_id"/>
     <Match idRef="Keyword_denmark_id"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="7e12d-1596">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="7e12d-1596">Keywords</span></span>

#### <a name="keyword_denmark_id"></a><span data-ttu-id="7e12d-1597">Keyword_denmark_id</span><span class="sxs-lookup"><span data-stu-id="7e12d-1597">Keyword_denmark_id</span></span>

- <span data-ttu-id="7e12d-1598">Codice PIN</span><span class="sxs-lookup"><span data-stu-id="7e12d-1598">Personal Identification Number</span></span>
- <span data-ttu-id="7e12d-1599">CPR</span><span class="sxs-lookup"><span data-stu-id="7e12d-1599">CPR</span></span>
- <span data-ttu-id="7e12d-1600">Det Centrale Personregister</span><span class="sxs-lookup"><span data-stu-id="7e12d-1600">Det Centrale Personregister</span></span>
- <span data-ttu-id="7e12d-1601">Personnummer</span><span class="sxs-lookup"><span data-stu-id="7e12d-1601">Personnummer</span></span>
   
## <a name="drug-enforcement-agency-dea-number"></a><span data-ttu-id="7e12d-1602">Numero della Drug Enforcement Agency (DEA)</span><span class="sxs-lookup"><span data-stu-id="7e12d-1602">Drug Enforcement Agency (DEA) Number</span></span>

### <a name="format"></a><span data-ttu-id="7e12d-1603">Formato</span><span class="sxs-lookup"><span data-stu-id="7e12d-1603">Format</span></span>

<span data-ttu-id="7e12d-1604">Due lettere seguite da 7 cifre</span><span class="sxs-lookup"><span data-stu-id="7e12d-1604">Two letters followed by seven digits</span></span>

### <a name="pattern"></a><span data-ttu-id="7e12d-1605">Modello</span><span class="sxs-lookup"><span data-stu-id="7e12d-1605">Pattern</span></span>

<span data-ttu-id="7e12d-1606">Il modello deve includere tutti gli elementi seguenti:</span><span class="sxs-lookup"><span data-stu-id="7e12d-1606">Pattern must include all of the following:</span></span>
- <span data-ttu-id="7e12d-1607">Una lettera (senza distinzione tra maiuscole/minuscole) da questo gruppo di lettere: abcdefghjklmnprstux, ovvero un codice registrante</span><span class="sxs-lookup"><span data-stu-id="7e12d-1607">One letter (not case sensitive) from this set of possible letters: abcdefghjklmnprstux, which is a registrant code</span></span> 
- <span data-ttu-id="7e12d-1608">Una lettera (senza distinzione tra maiuscole/minuscole), ovvero la prima lettera del cognome del registrante</span><span class="sxs-lookup"><span data-stu-id="7e12d-1608">One letter (not case sensitive), which is the first letter of the registrant's last name</span></span> 
- <span data-ttu-id="7e12d-1609">7 cifre e l'ultima è quella di controllo</span><span class="sxs-lookup"><span data-stu-id="7e12d-1609">Seven digits, the last of which is the check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="7e12d-1610">Checksum</span><span class="sxs-lookup"><span data-stu-id="7e12d-1610">Checksum</span></span>

<span data-ttu-id="7e12d-1611">Sì</span><span class="sxs-lookup"><span data-stu-id="7e12d-1611">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="7e12d-1612">Definizione</span><span class="sxs-lookup"><span data-stu-id="7e12d-1612">Definition</span></span>

<span data-ttu-id="7e12d-1613">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="7e12d-1613">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="7e12d-1614">La funzione Func_dea_number restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="7e12d-1614">The function Func_dea_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="7e12d-1615">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="7e12d-1615">The checksum passes.</span></span>

```xml
<!-- DEA Number -->
<Entity id="9a5445ad-406e-43eb-8bd7-cac17ab6d0e4" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_dea_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="7e12d-1616">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="7e12d-1616">Keywords</span></span>

<span data-ttu-id="7e12d-1617">Nessuno</span><span class="sxs-lookup"><span data-stu-id="7e12d-1617">None</span></span>

   
## <a name="eu-debit-card-number"></a><span data-ttu-id="7e12d-1618">Unione Europea - Numero di carta di debito</span><span class="sxs-lookup"><span data-stu-id="7e12d-1618">EU Debit Card Number</span></span>

### <a name="format"></a><span data-ttu-id="7e12d-1619">Formato</span><span class="sxs-lookup"><span data-stu-id="7e12d-1619">Format</span></span>

<span data-ttu-id="7e12d-1620">16 cifre</span><span class="sxs-lookup"><span data-stu-id="7e12d-1620">16 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="7e12d-1621">Modello</span><span class="sxs-lookup"><span data-stu-id="7e12d-1621">Pattern</span></span>

<span data-ttu-id="7e12d-1622">Modello molto complesso e solido</span><span class="sxs-lookup"><span data-stu-id="7e12d-1622">Very complex and robust pattern</span></span>

### <a name="checksum"></a><span data-ttu-id="7e12d-1623">Checksum</span><span class="sxs-lookup"><span data-stu-id="7e12d-1623">Checksum</span></span>

<span data-ttu-id="7e12d-1624">Sì</span><span class="sxs-lookup"><span data-stu-id="7e12d-1624">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="7e12d-1625">Definizione</span><span class="sxs-lookup"><span data-stu-id="7e12d-1625">Definition</span></span>

<span data-ttu-id="7e12d-1626">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="7e12d-1626">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="7e12d-1627">La funzione Func_eu_debit_card restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="7e12d-1627">The function Func_eu_debit_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="7e12d-1628">Si verifica almeno una delle situazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="7e12d-1628">At least one of the following is true:</span></span>
    - <span data-ttu-id="7e12d-1629">Viene trovata una parola chiave da Keyword_eu_debit_card.</span><span class="sxs-lookup"><span data-stu-id="7e12d-1629">A keyword from Keyword_eu_debit_card is found.</span></span>
    - <span data-ttu-id="7e12d-1630">Viene trovata una parola chiave da Keyword_card_terms_dict.</span><span class="sxs-lookup"><span data-stu-id="7e12d-1630">A keyword from Keyword_card_terms_dict is found.</span></span>
    - <span data-ttu-id="7e12d-1631">Viene trovata una parola chiave da Keyword_card_security_terms_dict.</span><span class="sxs-lookup"><span data-stu-id="7e12d-1631">A keyword from Keyword_card_security_terms_dict is found.</span></span>
    - <span data-ttu-id="7e12d-1632">Viene trovata una parola chiave da Keyword_card_expiration_terms_dict.</span><span class="sxs-lookup"><span data-stu-id="7e12d-1632">A keyword from Keyword_card_expiration_terms_dict is found.</span></span>
    - <span data-ttu-id="7e12d-1633">La funzione Func_expiration_date rileva una data nel formato corretto.</span><span class="sxs-lookup"><span data-stu-id="7e12d-1633">The function Func_expiration_date finds a date in the right date format.</span></span>
- <span data-ttu-id="7e12d-1634">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="7e12d-1634">The checksum passes.</span></span>

```xml
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

### <a name="keywords"></a><span data-ttu-id="7e12d-1635">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="7e12d-1635">Keywords</span></span>

#### <a name="keyword_eu_debit_card"></a><span data-ttu-id="7e12d-1636">Keyword_eu_debit_card</span><span class="sxs-lookup"><span data-stu-id="7e12d-1636">Keyword_eu_debit_card</span></span>

- <span data-ttu-id="7e12d-1637">account number</span><span class="sxs-lookup"><span data-stu-id="7e12d-1637">account number</span></span> 
- <span data-ttu-id="7e12d-1638">card number</span><span class="sxs-lookup"><span data-stu-id="7e12d-1638">card number</span></span> 
- <span data-ttu-id="7e12d-1639">card no.</span><span class="sxs-lookup"><span data-stu-id="7e12d-1639">card no.</span></span> 
- <span data-ttu-id="7e12d-1640">security number</span><span class="sxs-lookup"><span data-stu-id="7e12d-1640">security number</span></span> 
- <span data-ttu-id="7e12d-1641">CC #</span><span class="sxs-lookup"><span data-stu-id="7e12d-1641">cc#</span></span> 

#### <a name="keyword_card_terms_dict"></a><span data-ttu-id="7e12d-1642">Keyword_card_terms_dict</span><span class="sxs-lookup"><span data-stu-id="7e12d-1642">Keyword_card_terms_dict</span></span>

- <span data-ttu-id="7e12d-1643">acct nbr</span><span class="sxs-lookup"><span data-stu-id="7e12d-1643">acct nbr</span></span> 
- <span data-ttu-id="7e12d-1644">acct num</span><span class="sxs-lookup"><span data-stu-id="7e12d-1644">acct num</span></span> 
- <span data-ttu-id="7e12d-1645">acct no</span><span class="sxs-lookup"><span data-stu-id="7e12d-1645">acct no</span></span> 
- <span data-ttu-id="7e12d-1646">american express</span><span class="sxs-lookup"><span data-stu-id="7e12d-1646">american express</span></span> 
- <span data-ttu-id="7e12d-1647">AmericanExpress</span><span class="sxs-lookup"><span data-stu-id="7e12d-1647">americanexpress</span></span> 
- <span data-ttu-id="7e12d-1648">americano espresso</span><span class="sxs-lookup"><span data-stu-id="7e12d-1648">americano espresso</span></span> 
- <span data-ttu-id="7e12d-1649">Amex</span><span class="sxs-lookup"><span data-stu-id="7e12d-1649">amex</span></span> 
- <span data-ttu-id="7e12d-1650">atm card</span><span class="sxs-lookup"><span data-stu-id="7e12d-1650">atm card</span></span> 
- <span data-ttu-id="7e12d-1651">atm cards</span><span class="sxs-lookup"><span data-stu-id="7e12d-1651">atm cards</span></span> 
- <span data-ttu-id="7e12d-1652">atm kaart</span><span class="sxs-lookup"><span data-stu-id="7e12d-1652">atm kaart</span></span> 
- <span data-ttu-id="7e12d-1653">atmcard</span><span class="sxs-lookup"><span data-stu-id="7e12d-1653">atmcard</span></span> 
- <span data-ttu-id="7e12d-1654">atmcards</span><span class="sxs-lookup"><span data-stu-id="7e12d-1654">atmcards</span></span> 
- <span data-ttu-id="7e12d-1655">atmkaart</span><span class="sxs-lookup"><span data-stu-id="7e12d-1655">atmkaart</span></span> 
- <span data-ttu-id="7e12d-1656">atmkaarten</span><span class="sxs-lookup"><span data-stu-id="7e12d-1656">atmkaarten</span></span> 
- <span data-ttu-id="7e12d-1657">Bancontact</span><span class="sxs-lookup"><span data-stu-id="7e12d-1657">bancontact</span></span> 
- <span data-ttu-id="7e12d-1658">bank card</span><span class="sxs-lookup"><span data-stu-id="7e12d-1658">bank card</span></span> 
- <span data-ttu-id="7e12d-1659">bankkaart</span><span class="sxs-lookup"><span data-stu-id="7e12d-1659">bankkaart</span></span> 
- <span data-ttu-id="7e12d-1660">card holder</span><span class="sxs-lookup"><span data-stu-id="7e12d-1660">card holder</span></span> 
- <span data-ttu-id="7e12d-1661">card holders</span><span class="sxs-lookup"><span data-stu-id="7e12d-1661">card holders</span></span> 
- <span data-ttu-id="7e12d-1662">card num</span><span class="sxs-lookup"><span data-stu-id="7e12d-1662">card num</span></span> 
- <span data-ttu-id="7e12d-1663">card number</span><span class="sxs-lookup"><span data-stu-id="7e12d-1663">card number</span></span> 
- <span data-ttu-id="7e12d-1664">card numbers</span><span class="sxs-lookup"><span data-stu-id="7e12d-1664">card numbers</span></span> 
- <span data-ttu-id="7e12d-1665">card type</span><span class="sxs-lookup"><span data-stu-id="7e12d-1665">card type</span></span> 
- <span data-ttu-id="7e12d-1666">cardano numerico</span><span class="sxs-lookup"><span data-stu-id="7e12d-1666">cardano numerico</span></span> 
- <span data-ttu-id="7e12d-1667">titolare</span><span class="sxs-lookup"><span data-stu-id="7e12d-1667">cardholder</span></span> 
- <span data-ttu-id="7e12d-1668">titolari</span><span class="sxs-lookup"><span data-stu-id="7e12d-1668">cardholders</span></span> 
- <span data-ttu-id="7e12d-1669">cardnumber</span><span class="sxs-lookup"><span data-stu-id="7e12d-1669">cardnumber</span></span> 
- <span data-ttu-id="7e12d-1670">cardnumbers</span><span class="sxs-lookup"><span data-stu-id="7e12d-1670">cardnumbers</span></span> 
- <span data-ttu-id="7e12d-1671">carta bianca</span><span class="sxs-lookup"><span data-stu-id="7e12d-1671">carta bianca</span></span> 
- <span data-ttu-id="7e12d-1672">carta credito</span><span class="sxs-lookup"><span data-stu-id="7e12d-1672">carta credito</span></span> 
- <span data-ttu-id="7e12d-1673">carta di credito</span><span class="sxs-lookup"><span data-stu-id="7e12d-1673">carta di credito</span></span> 
- <span data-ttu-id="7e12d-1674">cartao de credito</span><span class="sxs-lookup"><span data-stu-id="7e12d-1674">cartao de credito</span></span> 
- <span data-ttu-id="7e12d-1675">cartao de crédito</span><span class="sxs-lookup"><span data-stu-id="7e12d-1675">cartao de crédito</span></span> 
- <span data-ttu-id="7e12d-1676">cartao de debito</span><span class="sxs-lookup"><span data-stu-id="7e12d-1676">cartao de debito</span></span> 
- <span data-ttu-id="7e12d-1677">○cartao de débito</span><span class="sxs-lookup"><span data-stu-id="7e12d-1677">cartao de débito</span></span> 
- <span data-ttu-id="7e12d-1678">carte bancaire</span><span class="sxs-lookup"><span data-stu-id="7e12d-1678">carte bancaire</span></span> 
- <span data-ttu-id="7e12d-1679">carte blanche</span><span class="sxs-lookup"><span data-stu-id="7e12d-1679">carte blanche</span></span> 
- <span data-ttu-id="7e12d-1680">carte bleue</span><span class="sxs-lookup"><span data-stu-id="7e12d-1680">carte bleue</span></span> 
- <span data-ttu-id="7e12d-1681">carte de credit</span><span class="sxs-lookup"><span data-stu-id="7e12d-1681">carte de credit</span></span> 
- <span data-ttu-id="7e12d-1682">carte de crédit</span><span class="sxs-lookup"><span data-stu-id="7e12d-1682">carte de crédit</span></span> 
- <span data-ttu-id="7e12d-1683">carte di credito</span><span class="sxs-lookup"><span data-stu-id="7e12d-1683">carte di credito</span></span> 
- <span data-ttu-id="7e12d-1684">carteblanche</span><span class="sxs-lookup"><span data-stu-id="7e12d-1684">carteblanche</span></span> 
- <span data-ttu-id="7e12d-1685">cartão de credito</span><span class="sxs-lookup"><span data-stu-id="7e12d-1685">cartão de credito</span></span> 
- <span data-ttu-id="7e12d-1686">cartão de crédito</span><span class="sxs-lookup"><span data-stu-id="7e12d-1686">cartão de crédito</span></span> 
- <span data-ttu-id="7e12d-1687">cartão de debito</span><span class="sxs-lookup"><span data-stu-id="7e12d-1687">cartão de debito</span></span> 
- <span data-ttu-id="7e12d-1688">cartão de débito</span><span class="sxs-lookup"><span data-stu-id="7e12d-1688">cartão de débito</span></span> 
- <span data-ttu-id="7e12d-1689">CB</span><span class="sxs-lookup"><span data-stu-id="7e12d-1689">cb</span></span> 
- <span data-ttu-id="7e12d-1690">Ccn</span><span class="sxs-lookup"><span data-stu-id="7e12d-1690">ccn</span></span> 
- <span data-ttu-id="7e12d-1691">check card</span><span class="sxs-lookup"><span data-stu-id="7e12d-1691">check card</span></span> 
- <span data-ttu-id="7e12d-1692">check cards</span><span class="sxs-lookup"><span data-stu-id="7e12d-1692">check cards</span></span> 
- <span data-ttu-id="7e12d-1693">checkcard</span><span class="sxs-lookup"><span data-stu-id="7e12d-1693">checkcard</span></span>
- <span data-ttu-id="7e12d-1694">checkcards</span><span class="sxs-lookup"><span data-stu-id="7e12d-1694">checkcards</span></span> 
- <span data-ttu-id="7e12d-1695">chequekaart</span><span class="sxs-lookup"><span data-stu-id="7e12d-1695">chequekaart</span></span> 
- <span data-ttu-id="7e12d-1696">Cirrus</span><span class="sxs-lookup"><span data-stu-id="7e12d-1696">cirrus</span></span> 
- <span data-ttu-id="7e12d-1697">Cirrus-Edc-Maestro</span><span class="sxs-lookup"><span data-stu-id="7e12d-1697">cirrus-edc-maestro</span></span> 
- <span data-ttu-id="7e12d-1698">controlekaart</span><span class="sxs-lookup"><span data-stu-id="7e12d-1698">controlekaart</span></span> 
- <span data-ttu-id="7e12d-1699">controlekaarten</span><span class="sxs-lookup"><span data-stu-id="7e12d-1699">controlekaarten</span></span> 
- <span data-ttu-id="7e12d-1700">credit card</span><span class="sxs-lookup"><span data-stu-id="7e12d-1700">credit card</span></span> 
- <span data-ttu-id="7e12d-1701">credit cards</span><span class="sxs-lookup"><span data-stu-id="7e12d-1701">credit cards</span></span> 
- <span data-ttu-id="7e12d-1702">CreditCard</span><span class="sxs-lookup"><span data-stu-id="7e12d-1702">creditcard</span></span> 
- <span data-ttu-id="7e12d-1703">creditcards.com</span><span class="sxs-lookup"><span data-stu-id="7e12d-1703">creditcards</span></span> 
- <span data-ttu-id="7e12d-1704">debetkaart</span><span class="sxs-lookup"><span data-stu-id="7e12d-1704">debetkaart</span></span> 
- <span data-ttu-id="7e12d-1705">carte</span><span class="sxs-lookup"><span data-stu-id="7e12d-1705">debetkaarten</span></span> 
- <span data-ttu-id="7e12d-1706">debit card</span><span class="sxs-lookup"><span data-stu-id="7e12d-1706">debit card</span></span> 
- <span data-ttu-id="7e12d-1707">debit cards</span><span class="sxs-lookup"><span data-stu-id="7e12d-1707">debit cards</span></span> 
- <span data-ttu-id="7e12d-1708">debitcard</span><span class="sxs-lookup"><span data-stu-id="7e12d-1708">debitcard</span></span> 
- <span data-ttu-id="7e12d-1709">debitcards</span><span class="sxs-lookup"><span data-stu-id="7e12d-1709">debitcards</span></span> 
- <span data-ttu-id="7e12d-1710">debito automatico</span><span class="sxs-lookup"><span data-stu-id="7e12d-1710">debito automatico</span></span> 
- <span data-ttu-id="7e12d-1711">diners club</span><span class="sxs-lookup"><span data-stu-id="7e12d-1711">diners club</span></span> 
- <span data-ttu-id="7e12d-1712">DinersClub</span><span class="sxs-lookup"><span data-stu-id="7e12d-1712">dinersclub</span></span> 
- <span data-ttu-id="7e12d-1713">individuare</span><span class="sxs-lookup"><span data-stu-id="7e12d-1713">discover</span></span> 
- <span data-ttu-id="7e12d-1714">discover card</span><span class="sxs-lookup"><span data-stu-id="7e12d-1714">discover card</span></span> 
- <span data-ttu-id="7e12d-1715">discover cards</span><span class="sxs-lookup"><span data-stu-id="7e12d-1715">discover cards</span></span> 
- <span data-ttu-id="7e12d-1716">discovercard</span><span class="sxs-lookup"><span data-stu-id="7e12d-1716">discovercard</span></span> 
- <span data-ttu-id="7e12d-1717">discovercards</span><span class="sxs-lookup"><span data-stu-id="7e12d-1717">discovercards</span></span> 
- <span data-ttu-id="7e12d-1718">débito automático</span><span class="sxs-lookup"><span data-stu-id="7e12d-1718">débito automático</span></span>
- <span data-ttu-id="7e12d-1719">EDC</span><span class="sxs-lookup"><span data-stu-id="7e12d-1719">edc</span></span> 
- <span data-ttu-id="7e12d-1720">eigentümername</span><span class="sxs-lookup"><span data-stu-id="7e12d-1720">eigentümername</span></span> 
- <span data-ttu-id="7e12d-1721">european debit card</span><span class="sxs-lookup"><span data-stu-id="7e12d-1721">european debit card</span></span> 
- <span data-ttu-id="7e12d-1722">hoofdkaart</span><span class="sxs-lookup"><span data-stu-id="7e12d-1722">hoofdkaart</span></span> 
- <span data-ttu-id="7e12d-1723">hoofdkaarten</span><span class="sxs-lookup"><span data-stu-id="7e12d-1723">hoofdkaarten</span></span> 
- <span data-ttu-id="7e12d-1724">in viaggio</span><span class="sxs-lookup"><span data-stu-id="7e12d-1724">in viaggio</span></span> 
- <span data-ttu-id="7e12d-1725">japanese card bureau</span><span class="sxs-lookup"><span data-stu-id="7e12d-1725">japanese card bureau</span></span> 
- <span data-ttu-id="7e12d-1726">japanse kaartdienst</span><span class="sxs-lookup"><span data-stu-id="7e12d-1726">japanse kaartdienst</span></span> 
- <span data-ttu-id="7e12d-1727">JCB</span><span class="sxs-lookup"><span data-stu-id="7e12d-1727">jcb</span></span> 
- <span data-ttu-id="7e12d-1728">kaart</span><span class="sxs-lookup"><span data-stu-id="7e12d-1728">kaart</span></span> 
- <span data-ttu-id="7e12d-1729">kaart num</span><span class="sxs-lookup"><span data-stu-id="7e12d-1729">kaart num</span></span> 
- <span data-ttu-id="7e12d-1730">kaartaantal</span><span class="sxs-lookup"><span data-stu-id="7e12d-1730">kaartaantal</span></span> 
- <span data-ttu-id="7e12d-1731">kaartaantallen</span><span class="sxs-lookup"><span data-stu-id="7e12d-1731">kaartaantallen</span></span> 
- <span data-ttu-id="7e12d-1732">kaarthouder</span><span class="sxs-lookup"><span data-stu-id="7e12d-1732">kaarthouder</span></span> 
- <span data-ttu-id="7e12d-1733">kaarthouders</span><span class="sxs-lookup"><span data-stu-id="7e12d-1733">kaarthouders</span></span> 
- <span data-ttu-id="7e12d-1734">Karte</span><span class="sxs-lookup"><span data-stu-id="7e12d-1734">karte</span></span>  
- <span data-ttu-id="7e12d-1735">karteninhaber</span><span class="sxs-lookup"><span data-stu-id="7e12d-1735">karteninhaber</span></span> 
- <span data-ttu-id="7e12d-1736">karteninhabers</span><span class="sxs-lookup"><span data-stu-id="7e12d-1736">karteninhabers</span></span>
- <span data-ttu-id="7e12d-1737">kartennr</span><span class="sxs-lookup"><span data-stu-id="7e12d-1737">kartennr</span></span> 
- <span data-ttu-id="7e12d-1738">kartennummer</span><span class="sxs-lookup"><span data-stu-id="7e12d-1738">kartennummer</span></span> 
- <span data-ttu-id="7e12d-1739">kreditkarte</span><span class="sxs-lookup"><span data-stu-id="7e12d-1739">kreditkarte</span></span> 
- <span data-ttu-id="7e12d-1740">Kreditkarten-Nummer</span><span class="sxs-lookup"><span data-stu-id="7e12d-1740">kreditkarten-nummer</span></span> 
- <span data-ttu-id="7e12d-1741">kreditkarteninhaber</span><span class="sxs-lookup"><span data-stu-id="7e12d-1741">kreditkarteninhaber</span></span> 
- <span data-ttu-id="7e12d-1742">kreditkarteninstitut</span><span class="sxs-lookup"><span data-stu-id="7e12d-1742">kreditkarteninstitut</span></span> 
- <span data-ttu-id="7e12d-1743">kreditkartennummer</span><span class="sxs-lookup"><span data-stu-id="7e12d-1743">kreditkartennummer</span></span> 
- <span data-ttu-id="7e12d-1744">kreditkartentyp</span><span class="sxs-lookup"><span data-stu-id="7e12d-1744">kreditkartentyp</span></span> 
- <span data-ttu-id="7e12d-1745">Maestro</span><span class="sxs-lookup"><span data-stu-id="7e12d-1745">maestro</span></span> 
- <span data-ttu-id="7e12d-1746">master card</span><span class="sxs-lookup"><span data-stu-id="7e12d-1746">master card</span></span> 
- <span data-ttu-id="7e12d-1747">master cards</span><span class="sxs-lookup"><span data-stu-id="7e12d-1747">master cards</span></span> 
- <span data-ttu-id="7e12d-1748">Mastercard</span><span class="sxs-lookup"><span data-stu-id="7e12d-1748">mastercard</span></span> 
- <span data-ttu-id="7e12d-1749">Mastercard</span><span class="sxs-lookup"><span data-stu-id="7e12d-1749">mastercards</span></span> 
- <span data-ttu-id="7e12d-1750">MC</span><span class="sxs-lookup"><span data-stu-id="7e12d-1750">mc</span></span> 
- <span data-ttu-id="7e12d-1751">mister cash</span><span class="sxs-lookup"><span data-stu-id="7e12d-1751">mister cash</span></span> 
- <span data-ttu-id="7e12d-1752">n carta</span><span class="sxs-lookup"><span data-stu-id="7e12d-1752">n carta</span></span> 
- <span data-ttu-id="7e12d-1753">carta</span><span class="sxs-lookup"><span data-stu-id="7e12d-1753">carta</span></span> 
- <span data-ttu-id="7e12d-1754">no de tarjeta</span><span class="sxs-lookup"><span data-stu-id="7e12d-1754">no de tarjeta</span></span> 
- <span data-ttu-id="7e12d-1755">no do cartao</span><span class="sxs-lookup"><span data-stu-id="7e12d-1755">no do cartao</span></span> 
- <span data-ttu-id="7e12d-1756">no do cartão</span><span class="sxs-lookup"><span data-stu-id="7e12d-1756">no do cartão</span></span> 
- <span data-ttu-id="7e12d-1757">No.</span><span class="sxs-lookup"><span data-stu-id="7e12d-1757">no.</span></span> <span data-ttu-id="7e12d-1758">de tarjeta</span><span class="sxs-lookup"><span data-stu-id="7e12d-1758">de tarjeta</span></span> 
- <span data-ttu-id="7e12d-1759">No.</span><span class="sxs-lookup"><span data-stu-id="7e12d-1759">no.</span></span> <span data-ttu-id="7e12d-1760">do cartao</span><span class="sxs-lookup"><span data-stu-id="7e12d-1760">do cartao</span></span> 
- <span data-ttu-id="7e12d-1761">No.</span><span class="sxs-lookup"><span data-stu-id="7e12d-1761">no.</span></span> <span data-ttu-id="7e12d-1762">do cartão</span><span class="sxs-lookup"><span data-stu-id="7e12d-1762">do cartão</span></span> 
- <span data-ttu-id="7e12d-1763">nr carta</span><span class="sxs-lookup"><span data-stu-id="7e12d-1763">nr carta</span></span> 
- <span data-ttu-id="7e12d-1764">Nr.</span><span class="sxs-lookup"><span data-stu-id="7e12d-1764">nr.</span></span> <span data-ttu-id="7e12d-1765">carta</span><span class="sxs-lookup"><span data-stu-id="7e12d-1765">carta</span></span> 
- <span data-ttu-id="7e12d-1766">numeri di scheda</span><span class="sxs-lookup"><span data-stu-id="7e12d-1766">numeri di scheda</span></span> 
- <span data-ttu-id="7e12d-1767">numero carta</span><span class="sxs-lookup"><span data-stu-id="7e12d-1767">numero carta</span></span> 
- <span data-ttu-id="7e12d-1768">numero de cartao</span><span class="sxs-lookup"><span data-stu-id="7e12d-1768">numero de cartao</span></span> 
- <span data-ttu-id="7e12d-1769">numero de carte</span><span class="sxs-lookup"><span data-stu-id="7e12d-1769">numero de carte</span></span> 
- <span data-ttu-id="7e12d-1770">numero de cartão</span><span class="sxs-lookup"><span data-stu-id="7e12d-1770">numero de cartão</span></span> 
- <span data-ttu-id="7e12d-1771">numero de tarjeta</span><span class="sxs-lookup"><span data-stu-id="7e12d-1771">numero de tarjeta</span></span>
- <span data-ttu-id="7e12d-1772">numero della carta</span><span class="sxs-lookup"><span data-stu-id="7e12d-1772">numero della carta</span></span> 
- <span data-ttu-id="7e12d-1773">numero di carta</span><span class="sxs-lookup"><span data-stu-id="7e12d-1773">numero di carta</span></span> 
- <span data-ttu-id="7e12d-1774">numero di scheda</span><span class="sxs-lookup"><span data-stu-id="7e12d-1774">numero di scheda</span></span> 
- <span data-ttu-id="7e12d-1775">numero do cartao</span><span class="sxs-lookup"><span data-stu-id="7e12d-1775">numero do cartao</span></span> 
- <span data-ttu-id="7e12d-1776">numero do cartão</span><span class="sxs-lookup"><span data-stu-id="7e12d-1776">numero do cartão</span></span> 
- <span data-ttu-id="7e12d-1777">numéro de carte</span><span class="sxs-lookup"><span data-stu-id="7e12d-1777">numéro de carte</span></span> 
- <span data-ttu-id="7e12d-1778">nº carta</span><span class="sxs-lookup"><span data-stu-id="7e12d-1778">nº carta</span></span> 
- <span data-ttu-id="7e12d-1779">nº de carte</span><span class="sxs-lookup"><span data-stu-id="7e12d-1779">nº de carte</span></span> 
- <span data-ttu-id="7e12d-1780">nº de la carte</span><span class="sxs-lookup"><span data-stu-id="7e12d-1780">nº de la carte</span></span> 
- <span data-ttu-id="7e12d-1781">nº de tarjeta</span><span class="sxs-lookup"><span data-stu-id="7e12d-1781">nº de tarjeta</span></span> 
- <span data-ttu-id="7e12d-1782">nº do cartao</span><span class="sxs-lookup"><span data-stu-id="7e12d-1782">nº do cartao</span></span> 
- <span data-ttu-id="7e12d-1783">nº do cartão</span><span class="sxs-lookup"><span data-stu-id="7e12d-1783">nº do cartão</span></span> 
- <span data-ttu-id="7e12d-1784">n º.</span><span class="sxs-lookup"><span data-stu-id="7e12d-1784">nº.</span></span> <span data-ttu-id="7e12d-1785">do cartão</span><span class="sxs-lookup"><span data-stu-id="7e12d-1785">do cartão</span></span> 
- <span data-ttu-id="7e12d-1786">número de cartao</span><span class="sxs-lookup"><span data-stu-id="7e12d-1786">número de cartao</span></span> 
- <span data-ttu-id="7e12d-1787">número de cartão</span><span class="sxs-lookup"><span data-stu-id="7e12d-1787">número de cartão</span></span> 
- <span data-ttu-id="7e12d-1788">número de tarjeta</span><span class="sxs-lookup"><span data-stu-id="7e12d-1788">número de tarjeta</span></span> 
- <span data-ttu-id="7e12d-1789">número do cartao</span><span class="sxs-lookup"><span data-stu-id="7e12d-1789">número do cartao</span></span> 
- <span data-ttu-id="7e12d-1790">scheda dell'assegno</span><span class="sxs-lookup"><span data-stu-id="7e12d-1790">scheda dell'assegno</span></span> 
- <span data-ttu-id="7e12d-1791">scheda dell'atmosfera</span><span class="sxs-lookup"><span data-stu-id="7e12d-1791">scheda dell'atmosfera</span></span> 
- <span data-ttu-id="7e12d-1792">scheda dell'atmosfera</span><span class="sxs-lookup"><span data-stu-id="7e12d-1792">scheda dell'atmosfera</span></span> 
- <span data-ttu-id="7e12d-1793">scheda della banca</span><span class="sxs-lookup"><span data-stu-id="7e12d-1793">scheda della banca</span></span> 
- <span data-ttu-id="7e12d-1794">scheda di controllo</span><span class="sxs-lookup"><span data-stu-id="7e12d-1794">scheda di controllo</span></span> 
- <span data-ttu-id="7e12d-1795">scheda di debito</span><span class="sxs-lookup"><span data-stu-id="7e12d-1795">scheda di debito</span></span> 
- <span data-ttu-id="7e12d-1796">scheda matrice</span><span class="sxs-lookup"><span data-stu-id="7e12d-1796">scheda matrice</span></span> 
- <span data-ttu-id="7e12d-1797">schede dell'atmosfera</span><span class="sxs-lookup"><span data-stu-id="7e12d-1797">schede dell'atmosfera</span></span> 
- <span data-ttu-id="7e12d-1798">schede di controllo</span><span class="sxs-lookup"><span data-stu-id="7e12d-1798">schede di controllo</span></span> 
- <span data-ttu-id="7e12d-1799">schede di debito</span><span class="sxs-lookup"><span data-stu-id="7e12d-1799">schede di debito</span></span> 
- <span data-ttu-id="7e12d-1800">schede matrici</span><span class="sxs-lookup"><span data-stu-id="7e12d-1800">schede matrici</span></span> 
- <span data-ttu-id="7e12d-1801">scoprono la scheda</span><span class="sxs-lookup"><span data-stu-id="7e12d-1801">scoprono la scheda</span></span> 
- <span data-ttu-id="7e12d-1802">scoprono le schede</span><span class="sxs-lookup"><span data-stu-id="7e12d-1802">scoprono le schede</span></span> 
- <span data-ttu-id="7e12d-1803">solo</span><span class="sxs-lookup"><span data-stu-id="7e12d-1803">solo</span></span> 
- <span data-ttu-id="7e12d-1804">supporti di scheda</span><span class="sxs-lookup"><span data-stu-id="7e12d-1804">supporti di scheda</span></span> 
- <span data-ttu-id="7e12d-1805">supporto di scheda</span><span class="sxs-lookup"><span data-stu-id="7e12d-1805">supporto di scheda</span></span> 
- <span data-ttu-id="7e12d-1806">opzione</span><span class="sxs-lookup"><span data-stu-id="7e12d-1806">switch</span></span> 
- <span data-ttu-id="7e12d-1807">tarjeta atm</span><span class="sxs-lookup"><span data-stu-id="7e12d-1807">tarjeta atm</span></span> 
- <span data-ttu-id="7e12d-1808">tarjeta credito</span><span class="sxs-lookup"><span data-stu-id="7e12d-1808">tarjeta credito</span></span> 
- <span data-ttu-id="7e12d-1809">tarjeta de atm</span><span class="sxs-lookup"><span data-stu-id="7e12d-1809">tarjeta de atm</span></span> 
- <span data-ttu-id="7e12d-1810">tarjeta de credito</span><span class="sxs-lookup"><span data-stu-id="7e12d-1810">tarjeta de credito</span></span> 
- <span data-ttu-id="7e12d-1811">tarjeta de debito</span><span class="sxs-lookup"><span data-stu-id="7e12d-1811">tarjeta de debito</span></span> 
- <span data-ttu-id="7e12d-1812">tarjeta debito</span><span class="sxs-lookup"><span data-stu-id="7e12d-1812">tarjeta debito</span></span> 
- <span data-ttu-id="7e12d-1813">tarjeta no</span><span class="sxs-lookup"><span data-stu-id="7e12d-1813">tarjeta no</span></span>
- <span data-ttu-id="7e12d-1814">tarjetahabiente</span><span class="sxs-lookup"><span data-stu-id="7e12d-1814">tarjetahabiente</span></span> 
- <span data-ttu-id="7e12d-1815">tipo della scheda</span><span class="sxs-lookup"><span data-stu-id="7e12d-1815">tipo della scheda</span></span> 
- <span data-ttu-id="7e12d-1816">ufficio giapponese della</span><span class="sxs-lookup"><span data-stu-id="7e12d-1816">ufficio giapponese della</span></span> 
- <span data-ttu-id="7e12d-1817">scheda</span><span class="sxs-lookup"><span data-stu-id="7e12d-1817">scheda</span></span> 
- <span data-ttu-id="7e12d-1818">v pay</span><span class="sxs-lookup"><span data-stu-id="7e12d-1818">v pay</span></span> 
- <span data-ttu-id="7e12d-1819">v-pay</span><span class="sxs-lookup"><span data-stu-id="7e12d-1819">v-pay</span></span> 
- <span data-ttu-id="7e12d-1820">esempio</span><span class="sxs-lookup"><span data-stu-id="7e12d-1820">visa</span></span> 
- <span data-ttu-id="7e12d-1821">visa plus</span><span class="sxs-lookup"><span data-stu-id="7e12d-1821">visa plus</span></span> 
- <span data-ttu-id="7e12d-1822">visa electron</span><span class="sxs-lookup"><span data-stu-id="7e12d-1822">visa electron</span></span> 
- <span data-ttu-id="7e12d-1823">visto</span><span class="sxs-lookup"><span data-stu-id="7e12d-1823">visto</span></span> 
- <span data-ttu-id="7e12d-1824">Visum</span><span class="sxs-lookup"><span data-stu-id="7e12d-1824">visum</span></span> 
- <span data-ttu-id="7e12d-1825">vpay</span><span class="sxs-lookup"><span data-stu-id="7e12d-1825">vpay</span></span>   

#### <a name="keyword_card_security_terms_dict"></a><span data-ttu-id="7e12d-1826">Keyword_card_security_terms_dict</span><span class="sxs-lookup"><span data-stu-id="7e12d-1826">Keyword_card_security_terms_dict</span></span>

- <span data-ttu-id="7e12d-1827">card identification number</span><span class="sxs-lookup"><span data-stu-id="7e12d-1827">card identification number</span></span>
- <span data-ttu-id="7e12d-1828">card verification</span><span class="sxs-lookup"><span data-stu-id="7e12d-1828">card verification</span></span> 
- <span data-ttu-id="7e12d-1829">cardi la verifica</span><span class="sxs-lookup"><span data-stu-id="7e12d-1829">cardi la verifica</span></span> 
- <span data-ttu-id="7e12d-1830">ID</span><span class="sxs-lookup"><span data-stu-id="7e12d-1830">cid</span></span> 
- <span data-ttu-id="7e12d-1831">cod seg</span><span class="sxs-lookup"><span data-stu-id="7e12d-1831">cod seg</span></span> 
- <span data-ttu-id="7e12d-1832">cod seguranca</span><span class="sxs-lookup"><span data-stu-id="7e12d-1832">cod seguranca</span></span> 
- <span data-ttu-id="7e12d-1833">cod segurança</span><span class="sxs-lookup"><span data-stu-id="7e12d-1833">cod segurança</span></span> 
- <span data-ttu-id="7e12d-1834">cod sicurezza</span><span class="sxs-lookup"><span data-stu-id="7e12d-1834">cod sicurezza</span></span> 
- <span data-ttu-id="7e12d-1835">Cod.</span><span class="sxs-lookup"><span data-stu-id="7e12d-1835">cod.</span></span> <span data-ttu-id="7e12d-1836">SEG</span><span class="sxs-lookup"><span data-stu-id="7e12d-1836">seg</span></span> 
- <span data-ttu-id="7e12d-1837">Cod.</span><span class="sxs-lookup"><span data-stu-id="7e12d-1837">cod.</span></span> <span data-ttu-id="7e12d-1838">seguranca</span><span class="sxs-lookup"><span data-stu-id="7e12d-1838">seguranca</span></span> 
- <span data-ttu-id="7e12d-1839">Cod.</span><span class="sxs-lookup"><span data-stu-id="7e12d-1839">cod.</span></span> <span data-ttu-id="7e12d-1840">Segurança</span><span class="sxs-lookup"><span data-stu-id="7e12d-1840">segurança</span></span> 
- <span data-ttu-id="7e12d-1841">Cod.</span><span class="sxs-lookup"><span data-stu-id="7e12d-1841">cod.</span></span> <span data-ttu-id="7e12d-1842">sicurezza</span><span class="sxs-lookup"><span data-stu-id="7e12d-1842">sicurezza</span></span> 
- <span data-ttu-id="7e12d-1843">codice di sicurezza</span><span class="sxs-lookup"><span data-stu-id="7e12d-1843">codice di sicurezza</span></span> 
- <span data-ttu-id="7e12d-1844">codice di verifica</span><span class="sxs-lookup"><span data-stu-id="7e12d-1844">codice di verifica</span></span> 
- <span data-ttu-id="7e12d-1845">Codigo</span><span class="sxs-lookup"><span data-stu-id="7e12d-1845">codigo</span></span> 
- <span data-ttu-id="7e12d-1846">codigo de seguranca</span><span class="sxs-lookup"><span data-stu-id="7e12d-1846">codigo de seguranca</span></span> 
- <span data-ttu-id="7e12d-1847">codigo de segurança</span><span class="sxs-lookup"><span data-stu-id="7e12d-1847">codigo de segurança</span></span> 
- <span data-ttu-id="7e12d-1848">crittogramma</span><span class="sxs-lookup"><span data-stu-id="7e12d-1848">crittogramma</span></span> 
- <span data-ttu-id="7e12d-1849">crittogramma</span><span class="sxs-lookup"><span data-stu-id="7e12d-1849">cryptogram</span></span> 
- <span data-ttu-id="7e12d-1850">cryptogramme</span><span class="sxs-lookup"><span data-stu-id="7e12d-1850">cryptogramme</span></span> 
- <span data-ttu-id="7e12d-1851">CV2</span><span class="sxs-lookup"><span data-stu-id="7e12d-1851">cv2</span></span> 
- <span data-ttu-id="7e12d-1852">CVC</span><span class="sxs-lookup"><span data-stu-id="7e12d-1852">cvc</span></span> 
- <span data-ttu-id="7e12d-1853">CVC2</span><span class="sxs-lookup"><span data-stu-id="7e12d-1853">cvc2</span></span> 
- <span data-ttu-id="7e12d-1854">CVN</span><span class="sxs-lookup"><span data-stu-id="7e12d-1854">cvn</span></span> 
- <span data-ttu-id="7e12d-1855">CVV</span><span class="sxs-lookup"><span data-stu-id="7e12d-1855">cvv</span></span> 
- <span data-ttu-id="7e12d-1856">CVV2</span><span class="sxs-lookup"><span data-stu-id="7e12d-1856">cvv2</span></span> 
- <span data-ttu-id="7e12d-1857">cód seguranca</span><span class="sxs-lookup"><span data-stu-id="7e12d-1857">cód seguranca</span></span> 
- <span data-ttu-id="7e12d-1858">cód segurança</span><span class="sxs-lookup"><span data-stu-id="7e12d-1858">cód segurança</span></span> 
- <span data-ttu-id="7e12d-1859">cód.</span><span class="sxs-lookup"><span data-stu-id="7e12d-1859">cód.</span></span> <span data-ttu-id="7e12d-1860">seguranca</span><span class="sxs-lookup"><span data-stu-id="7e12d-1860">seguranca</span></span> 
- <span data-ttu-id="7e12d-1861">cód.</span><span class="sxs-lookup"><span data-stu-id="7e12d-1861">cód.</span></span> <span data-ttu-id="7e12d-1862">Segurança</span><span class="sxs-lookup"><span data-stu-id="7e12d-1862">segurança</span></span> 
- <span data-ttu-id="7e12d-1863">Código</span><span class="sxs-lookup"><span data-stu-id="7e12d-1863">código</span></span> 
- <span data-ttu-id="7e12d-1864">código de seguranca</span><span class="sxs-lookup"><span data-stu-id="7e12d-1864">código de seguranca</span></span> 
- <span data-ttu-id="7e12d-1865">código de segurança</span><span class="sxs-lookup"><span data-stu-id="7e12d-1865">código de segurança</span></span> 
- <span data-ttu-id="7e12d-1866">de kaart controle</span><span class="sxs-lookup"><span data-stu-id="7e12d-1866">de kaart controle</span></span> 
- <span data-ttu-id="7e12d-1867">geeft nr uit</span><span class="sxs-lookup"><span data-stu-id="7e12d-1867">geeft nr uit</span></span> 
- <span data-ttu-id="7e12d-1868">issue no</span><span class="sxs-lookup"><span data-stu-id="7e12d-1868">issue no</span></span> 
- <span data-ttu-id="7e12d-1869">issue number</span><span class="sxs-lookup"><span data-stu-id="7e12d-1869">issue number</span></span> 
- <span data-ttu-id="7e12d-1870">kaartidentificatienummer</span><span class="sxs-lookup"><span data-stu-id="7e12d-1870">kaartidentificatienummer</span></span> 
- <span data-ttu-id="7e12d-1871">kreditkartenprufnummer</span><span class="sxs-lookup"><span data-stu-id="7e12d-1871">kreditkartenprufnummer</span></span> 
- <span data-ttu-id="7e12d-1872">kreditkartenprüfnummer</span><span class="sxs-lookup"><span data-stu-id="7e12d-1872">kreditkartenprüfnummer</span></span> 
- <span data-ttu-id="7e12d-1873">kwestieaantal</span><span class="sxs-lookup"><span data-stu-id="7e12d-1873">kwestieaantal</span></span> 
- <span data-ttu-id="7e12d-1874">No.</span><span class="sxs-lookup"><span data-stu-id="7e12d-1874">no.</span></span> <span data-ttu-id="7e12d-1875">dell'edizione</span><span class="sxs-lookup"><span data-stu-id="7e12d-1875">dell'edizione</span></span> 
- <span data-ttu-id="7e12d-1876">No.</span><span class="sxs-lookup"><span data-stu-id="7e12d-1876">no.</span></span> <span data-ttu-id="7e12d-1877">di sicurezza</span><span class="sxs-lookup"><span data-stu-id="7e12d-1877">di sicurezza</span></span> 
- <span data-ttu-id="7e12d-1878">numero de securite</span><span class="sxs-lookup"><span data-stu-id="7e12d-1878">numero de securite</span></span> 
- <span data-ttu-id="7e12d-1879">numero de verificacao</span><span class="sxs-lookup"><span data-stu-id="7e12d-1879">numero de verificacao</span></span> 
- <span data-ttu-id="7e12d-1880">numero dell'edizione</span><span class="sxs-lookup"><span data-stu-id="7e12d-1880">numero dell'edizione</span></span> 
- <span data-ttu-id="7e12d-1881">numero di identificazione della</span><span class="sxs-lookup"><span data-stu-id="7e12d-1881">numero di identificazione della</span></span> 
- <span data-ttu-id="7e12d-1882">scheda</span><span class="sxs-lookup"><span data-stu-id="7e12d-1882">scheda</span></span> 
- <span data-ttu-id="7e12d-1883">numero di sicurezza</span><span class="sxs-lookup"><span data-stu-id="7e12d-1883">numero di sicurezza</span></span> 
- <span data-ttu-id="7e12d-1884">numero van veiligheid</span><span class="sxs-lookup"><span data-stu-id="7e12d-1884">numero van veiligheid</span></span> 
- <span data-ttu-id="7e12d-1885">numéro de sécurité</span><span class="sxs-lookup"><span data-stu-id="7e12d-1885">numéro de sécurité</span></span> 
- <span data-ttu-id="7e12d-1886">nº autorizzazione</span><span class="sxs-lookup"><span data-stu-id="7e12d-1886">nº autorizzazione</span></span> 
- <span data-ttu-id="7e12d-1887">número de verificação</span><span class="sxs-lookup"><span data-stu-id="7e12d-1887">número de verificação</span></span> 
- <span data-ttu-id="7e12d-1888">perno il blocco</span><span class="sxs-lookup"><span data-stu-id="7e12d-1888">perno il blocco</span></span> 
- <span data-ttu-id="7e12d-1889">pin block</span><span class="sxs-lookup"><span data-stu-id="7e12d-1889">pin block</span></span> 
- <span data-ttu-id="7e12d-1890">Prufziffer</span><span class="sxs-lookup"><span data-stu-id="7e12d-1890">prufziffer</span></span> 
- <span data-ttu-id="7e12d-1891">prüfziffer</span><span class="sxs-lookup"><span data-stu-id="7e12d-1891">prüfziffer</span></span> 
- <span data-ttu-id="7e12d-1892">security code</span><span class="sxs-lookup"><span data-stu-id="7e12d-1892">security code</span></span> 
- <span data-ttu-id="7e12d-1893">security no</span><span class="sxs-lookup"><span data-stu-id="7e12d-1893">security no</span></span> 
- <span data-ttu-id="7e12d-1894">security number</span><span class="sxs-lookup"><span data-stu-id="7e12d-1894">security number</span></span> 
- <span data-ttu-id="7e12d-1895">sicherheits kode</span><span class="sxs-lookup"><span data-stu-id="7e12d-1895">sicherheits kode</span></span> 
- <span data-ttu-id="7e12d-1896">sicherheitscode</span><span class="sxs-lookup"><span data-stu-id="7e12d-1896">sicherheitscode</span></span> 
- <span data-ttu-id="7e12d-1897">sicherheitsnummer</span><span class="sxs-lookup"><span data-stu-id="7e12d-1897">sicherheitsnummer</span></span> 
- <span data-ttu-id="7e12d-1898">speldblok</span><span class="sxs-lookup"><span data-stu-id="7e12d-1898">speldblok</span></span> 
- <span data-ttu-id="7e12d-1899">veiligheid nr</span><span class="sxs-lookup"><span data-stu-id="7e12d-1899">veiligheid nr</span></span> 
- <span data-ttu-id="7e12d-1900">veiligheidsaantal</span><span class="sxs-lookup"><span data-stu-id="7e12d-1900">veiligheidsaantal</span></span> 
- <span data-ttu-id="7e12d-1901">veiligheidscode</span><span class="sxs-lookup"><span data-stu-id="7e12d-1901">veiligheidscode</span></span> 
- <span data-ttu-id="7e12d-1902">veiligheidsnummer</span><span class="sxs-lookup"><span data-stu-id="7e12d-1902">veiligheidsnummer</span></span> 
- <span data-ttu-id="7e12d-1903">verfalldatum</span><span class="sxs-lookup"><span data-stu-id="7e12d-1903">verfalldatum</span></span> 

#### <a name="keyword_card_expiration_terms_dict"></a><span data-ttu-id="7e12d-1904">Keyword_card_expiration_terms_dict</span><span class="sxs-lookup"><span data-stu-id="7e12d-1904">Keyword_card_expiration_terms_dict</span></span>

- <span data-ttu-id="7e12d-1905">ablauf</span><span class="sxs-lookup"><span data-stu-id="7e12d-1905">ablauf</span></span> 
- <span data-ttu-id="7e12d-1906">data de expiracao</span><span class="sxs-lookup"><span data-stu-id="7e12d-1906">data de expiracao</span></span> 
- <span data-ttu-id="7e12d-1907">data de expiração</span><span class="sxs-lookup"><span data-stu-id="7e12d-1907">data de expiração</span></span> 
- <span data-ttu-id="7e12d-1908">data del exp</span><span class="sxs-lookup"><span data-stu-id="7e12d-1908">data del exp</span></span> 
- <span data-ttu-id="7e12d-1909">data di exp</span><span class="sxs-lookup"><span data-stu-id="7e12d-1909">data di exp</span></span> 
- <span data-ttu-id="7e12d-1910">data di scadenza</span><span class="sxs-lookup"><span data-stu-id="7e12d-1910">data di scadenza</span></span> 
- <span data-ttu-id="7e12d-1911">data em que expira</span><span class="sxs-lookup"><span data-stu-id="7e12d-1911">data em que expira</span></span> 
- <span data-ttu-id="7e12d-1912">data scad</span><span class="sxs-lookup"><span data-stu-id="7e12d-1912">data scad</span></span> 
- <span data-ttu-id="7e12d-1913">data scadenza</span><span class="sxs-lookup"><span data-stu-id="7e12d-1913">data scadenza</span></span> 
- <span data-ttu-id="7e12d-1914">date de validité</span><span class="sxs-lookup"><span data-stu-id="7e12d-1914">date de validité</span></span> 
- <span data-ttu-id="7e12d-1915">datum afloop</span><span class="sxs-lookup"><span data-stu-id="7e12d-1915">datum afloop</span></span> 
- <span data-ttu-id="7e12d-1916">datum van exp</span><span class="sxs-lookup"><span data-stu-id="7e12d-1916">datum van exp</span></span> 
- <span data-ttu-id="7e12d-1917">de afloop</span><span class="sxs-lookup"><span data-stu-id="7e12d-1917">de afloop</span></span> 
- <span data-ttu-id="7e12d-1918">espira</span><span class="sxs-lookup"><span data-stu-id="7e12d-1918">espira</span></span> 
- <span data-ttu-id="7e12d-1919">espira</span><span class="sxs-lookup"><span data-stu-id="7e12d-1919">espira</span></span> 
- <span data-ttu-id="7e12d-1920">exp date</span><span class="sxs-lookup"><span data-stu-id="7e12d-1920">exp date</span></span> 
- <span data-ttu-id="7e12d-1921">exp datum</span><span class="sxs-lookup"><span data-stu-id="7e12d-1921">exp datum</span></span> 
- <span data-ttu-id="7e12d-1922">scadenza</span><span class="sxs-lookup"><span data-stu-id="7e12d-1922">expiration</span></span> 
- <span data-ttu-id="7e12d-1923">scadenza</span><span class="sxs-lookup"><span data-stu-id="7e12d-1923">expire</span></span> 
- <span data-ttu-id="7e12d-1924">scade</span><span class="sxs-lookup"><span data-stu-id="7e12d-1924">expires</span></span> 
- <span data-ttu-id="7e12d-1925">scadenza</span><span class="sxs-lookup"><span data-stu-id="7e12d-1925">expiry</span></span> 
- <span data-ttu-id="7e12d-1926">fecha de expiracion</span><span class="sxs-lookup"><span data-stu-id="7e12d-1926">fecha de expiracion</span></span> 
- <span data-ttu-id="7e12d-1927">fecha de venc</span><span class="sxs-lookup"><span data-stu-id="7e12d-1927">fecha de venc</span></span> 
- <span data-ttu-id="7e12d-1928">gultig bis</span><span class="sxs-lookup"><span data-stu-id="7e12d-1928">gultig bis</span></span> 
- <span data-ttu-id="7e12d-1929">gultigkeitsdatum</span><span class="sxs-lookup"><span data-stu-id="7e12d-1929">gultigkeitsdatum</span></span> 
- <span data-ttu-id="7e12d-1930">gültig bis</span><span class="sxs-lookup"><span data-stu-id="7e12d-1930">gültig bis</span></span> 
- <span data-ttu-id="7e12d-1931">gültigkeitsdatum</span><span class="sxs-lookup"><span data-stu-id="7e12d-1931">gültigkeitsdatum</span></span> 
- <span data-ttu-id="7e12d-1932">la scadenza</span><span class="sxs-lookup"><span data-stu-id="7e12d-1932">la scadenza</span></span> 
- <span data-ttu-id="7e12d-1933">scadenza</span><span class="sxs-lookup"><span data-stu-id="7e12d-1933">scadenza</span></span> 
- <span data-ttu-id="7e12d-1934">valable</span><span class="sxs-lookup"><span data-stu-id="7e12d-1934">valable</span></span> 
- <span data-ttu-id="7e12d-1935">validade</span><span class="sxs-lookup"><span data-stu-id="7e12d-1935">validade</span></span> 
- <span data-ttu-id="7e12d-1936">valido hasta</span><span class="sxs-lookup"><span data-stu-id="7e12d-1936">valido hasta</span></span> 
- <span data-ttu-id="7e12d-1937">Valor</span><span class="sxs-lookup"><span data-stu-id="7e12d-1937">valor</span></span> 
- <span data-ttu-id="7e12d-1938">venc</span><span class="sxs-lookup"><span data-stu-id="7e12d-1938">venc</span></span> 
- <span data-ttu-id="7e12d-1939">vencimento</span><span class="sxs-lookup"><span data-stu-id="7e12d-1939">vencimento</span></span> 
- <span data-ttu-id="7e12d-1940">vencimiento</span><span class="sxs-lookup"><span data-stu-id="7e12d-1940">vencimiento</span></span> 
- <span data-ttu-id="7e12d-1941">verloopt</span><span class="sxs-lookup"><span data-stu-id="7e12d-1941">verloopt</span></span> 
- <span data-ttu-id="7e12d-1942">vervaldag</span><span class="sxs-lookup"><span data-stu-id="7e12d-1942">vervaldag</span></span> 
- <span data-ttu-id="7e12d-1943">vervaldatum</span><span class="sxs-lookup"><span data-stu-id="7e12d-1943">vervaldatum</span></span> 
- <span data-ttu-id="7e12d-1944">VTO</span><span class="sxs-lookup"><span data-stu-id="7e12d-1944">vto</span></span> 
- <span data-ttu-id="7e12d-1945">válido hasta</span><span class="sxs-lookup"><span data-stu-id="7e12d-1945">válido hasta</span></span> 
   
## <a name="eu-drivers-license-number"></a><span data-ttu-id="7e12d-1946">Numero della patente di guida dell'Unione europea</span><span class="sxs-lookup"><span data-stu-id="7e12d-1946">EU Driver's License Number</span></span>

<span data-ttu-id="7e12d-1947">Per ulteriori informazioni, vedere [tipo di informazione sensibile al numero di patente dell'Unione europea](eu-driver-s-license-number.md).</span><span class="sxs-lookup"><span data-stu-id="7e12d-1947">To learn more, see [EU Driver's License Number sensitive information type](eu-driver-s-license-number.md).</span></span>
  
## <a name="eu-national-identification-number"></a><span data-ttu-id="7e12d-1948">Numero di identificazione nazionale dell'Unione europea</span><span class="sxs-lookup"><span data-stu-id="7e12d-1948">EU National Identification Number</span></span>

<span data-ttu-id="7e12d-1949">Per ulteriori informazioni, vedere [tipo di informazione riservata del numero di identificazione nazionale dell'Unione europea](eu-national-identification-number.md).</span><span class="sxs-lookup"><span data-stu-id="7e12d-1949">To learn more, see [EU National Identification Number sensitive information type](eu-national-identification-number.md).</span></span>
  
## <a name="eu-passport-number"></a><span data-ttu-id="7e12d-1950">Numero di passaporto EU</span><span class="sxs-lookup"><span data-stu-id="7e12d-1950">EU Passport Number</span></span>

<span data-ttu-id="7e12d-1951">Per ulteriori informazioni, vedere [tipo di informazione sensibile al numero di passaporto dell'Unione europea](eu-passport-number.md).</span><span class="sxs-lookup"><span data-stu-id="7e12d-1951">To learn more, see [EU Passport Number sensitive information type](eu-passport-number.md).</span></span>
  
## <a name="eu-social-security-number-or-equivalent-id"></a><span data-ttu-id="7e12d-1952">Codice di previdenza sociale dell'Unione europea o ID equivalente</span><span class="sxs-lookup"><span data-stu-id="7e12d-1952">EU Social Security Number or Equivalent ID</span></span>

<span data-ttu-id="7e12d-1953">Per ulteriori informazioni, vedere [codice di previdenza sociale dell'Unione europea o tipo di dati sensibili ID equivalente](eu-social-security-number-or-equivalent-id.md).</span><span class="sxs-lookup"><span data-stu-id="7e12d-1953">To learn more, see [EU Social Security Number or Equivalent ID sensitive information type](eu-social-security-number-or-equivalent-id.md).</span></span>
  
## <a name="eu-tax-identification-number"></a><span data-ttu-id="7e12d-1954">Numero di identificazione fiscale dell'Unione europea</span><span class="sxs-lookup"><span data-stu-id="7e12d-1954">EU Tax Identification Number</span></span>

<span data-ttu-id="7e12d-1955">Per ulteriori informazioni, vedere [tipo di informazione riservata del numero di identificazione fiscale dell'Unione europea](eu-tax-identification-number.md).</span><span class="sxs-lookup"><span data-stu-id="7e12d-1955">To learn more, see [EU Tax Identification Number sensitive information type](eu-tax-identification-number.md).</span></span>
  
## <a name="finland-national-id"></a><span data-ttu-id="7e12d-1956">Finland National ID</span><span class="sxs-lookup"><span data-stu-id="7e12d-1956">Finland National ID</span></span>

### <a name="format"></a><span data-ttu-id="7e12d-1957">Formato</span><span class="sxs-lookup"><span data-stu-id="7e12d-1957">Format</span></span>

<span data-ttu-id="7e12d-1958">6 cifre, un carattere di indicazione del secolo, tre cifre più una cifra di controllo</span><span class="sxs-lookup"><span data-stu-id="7e12d-1958">Six digits plus a character indicating a century plus three digits plus a check digit</span></span>

### <a name="pattern"></a><span data-ttu-id="7e12d-1959">Modello</span><span class="sxs-lookup"><span data-stu-id="7e12d-1959">Pattern</span></span>

<span data-ttu-id="7e12d-1960">Il modello deve includere tutti gli elementi seguenti:</span><span class="sxs-lookup"><span data-stu-id="7e12d-1960">Pattern must include all of the following:</span></span>
- <span data-ttu-id="7e12d-1961">Sei cifre nel formato DDMMYY che corrisponde alla data di nascita</span><span class="sxs-lookup"><span data-stu-id="7e12d-1961">Six digits in the format format DDMMYY which are a date of birth</span></span> 
- <span data-ttu-id="7e12d-1962">Indicatore del secolo ("-", "+" o "a")</span><span class="sxs-lookup"><span data-stu-id="7e12d-1962">Century marker (either '-', '+' or 'a')</span></span> 
- <span data-ttu-id="7e12d-1963">Codice PIN di 3 cifre</span><span class="sxs-lookup"><span data-stu-id="7e12d-1963">Three-digit personal identification number</span></span> 
- <span data-ttu-id="7e12d-1964">Una cifra o una lettera (con distinzione tra maiuscole/minuscole) che corrisponde a una cifra di controllo</span><span class="sxs-lookup"><span data-stu-id="7e12d-1964">A digit or letter (case insensitive) which is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="7e12d-1965">Checksum</span><span class="sxs-lookup"><span data-stu-id="7e12d-1965">Checksum</span></span>

<span data-ttu-id="7e12d-1966">Sì</span><span class="sxs-lookup"><span data-stu-id="7e12d-1966">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="7e12d-1967">Definizione</span><span class="sxs-lookup"><span data-stu-id="7e12d-1967">Definition</span></span>

<span data-ttu-id="7e12d-1968">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="7e12d-1968">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="7e12d-1969">La funzione Func_finnish_national_id restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="7e12d-1969">The function Func_finnish_national_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="7e12d-1970">Viene trovata una parola chiave da Keyword_finnish_national_id.</span><span class="sxs-lookup"><span data-stu-id="7e12d-1970">A keyword from Keyword_finnish_national_id is found.</span></span>
- <span data-ttu-id="7e12d-1971">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="7e12d-1971">The checksum passes.</span></span>

```xml
<!-- Finnish National ID-->
<Entity id="338FD995-4CB5-4F87-AD35-79BD1DD926C1" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_finnish_national_id" />
          <Match idRef="Keyword_finnish_national_id" />
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="7e12d-1972">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="7e12d-1972">Keywords</span></span>

- <span data-ttu-id="7e12d-1973">Keyword_finnish_national_id</span><span class="sxs-lookup"><span data-stu-id="7e12d-1973">Keyword_finnish_national_id</span></span>
- <span data-ttu-id="7e12d-1974">Sosiaaliturvatunnus</span><span class="sxs-lookup"><span data-stu-id="7e12d-1974">Sosiaaliturvatunnus</span></span>
- <span data-ttu-id="7e12d-1975">SOTU Henkilötunnus HETU</span><span class="sxs-lookup"><span data-stu-id="7e12d-1975">SOTU Henkilötunnus HETU</span></span>
- <span data-ttu-id="7e12d-1976">Personbeteckning</span><span class="sxs-lookup"><span data-stu-id="7e12d-1976">Personbeteckning</span></span>
- <span data-ttu-id="7e12d-1977">Personnummer</span><span class="sxs-lookup"><span data-stu-id="7e12d-1977">Personnummer</span></span>
   
## <a name="finland-passport-number"></a><span data-ttu-id="7e12d-1978">Finlandia - Numero di passaporto</span><span class="sxs-lookup"><span data-stu-id="7e12d-1978">Finland Passport Number</span></span>

<span data-ttu-id="7e12d-1979">Combinazione di formato di nove lettere e combinazioni di caratteri di nove lettere e cifre: due lettere (senza distinzione tra maiuscole/minuscole) sette cifre checksum nessuna definizione un criterio DLP è 75% sicuro che sia stato rilevato questo tipo di informazioni riservate se, all'interno di un prossimità di 300 caratteri: l'espressione regolare Regex_finland_passport_number trova il contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="7e12d-1979">Format Combination of nine letters and digits Pattern Combination of nine letters and digits: Two letters (not case sensitive) Seven digits Checksum No Definition A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The regular expression Regex_finland_passport_number finds content that matches the pattern.</span></span>
<span data-ttu-id="7e12d-1980">Viene trovata una parola chiave da Keyword_finland_passport_number.</span><span class="sxs-lookup"><span data-stu-id="7e12d-1980">A keyword from Keyword_finland_passport_number is found.</span></span>
<!-- Finland Passport Number -->
<span data-ttu-id="7e12d-1981"><Entity id="d1685ac3-1d3a-40f8-8198-32ef5669c7a5" recommendedConfidence="75" patternsProximity="300"> <Pattern confidenceLevel="75"> <IdMatch idRef="Regex_finland_passport_number"/> <Match idRef="Keyword_finland_passport_number"/> </Pattern>
</Entity></span><span class="sxs-lookup"><span data-stu-id="7e12d-1981"></span></span>
<span data-ttu-id="7e12d-1982">Parole chiave Keyword_finland_passport_number passaporto passi</span><span class="sxs-lookup"><span data-stu-id="7e12d-1982">Keywords Keyword_finland_passport_number Passport Passi</span></span>
   
## <a name="france-drivers-license-number"></a><span data-ttu-id="7e12d-1983">Francia - Numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="7e12d-1983">France Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="7e12d-1984">Formato</span><span class="sxs-lookup"><span data-stu-id="7e12d-1984">Format</span></span>

<span data-ttu-id="7e12d-1985">12 cifre</span><span class="sxs-lookup"><span data-stu-id="7e12d-1985">12 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="7e12d-1986">Modello</span><span class="sxs-lookup"><span data-stu-id="7e12d-1986">Pattern</span></span>

<span data-ttu-id="7e12d-1987">12 cifre con convalida per scontare modelli analoghi, ad esempio, quello dei numeri telefonici francesi</span><span class="sxs-lookup"><span data-stu-id="7e12d-1987">12 digits with validation to discount similar patterns such as French telephone numbers</span></span>

### <a name="checksum"></a><span data-ttu-id="7e12d-1988">Checksum</span><span class="sxs-lookup"><span data-stu-id="7e12d-1988">Checksum</span></span>

<span data-ttu-id="7e12d-1989">No</span><span class="sxs-lookup"><span data-stu-id="7e12d-1989">No</span></span>

### <a name="definition"></a><span data-ttu-id="7e12d-1990">Definizione</span><span class="sxs-lookup"><span data-stu-id="7e12d-1990">Definition</span></span>

<span data-ttu-id="7e12d-1991">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="7e12d-1991">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="7e12d-1992">La funzione Func_french_drivers_license restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="7e12d-1992">The function Func_french_drivers_license finds content that matches the pattern.</span></span>
- <span data-ttu-id="7e12d-1993">Si verifica almeno una delle situazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="7e12d-1993">At least one of the following is true:</span></span>
- <span data-ttu-id="7e12d-1994">Viene trovata una parola chiave da Keyword_french_drivers_license.</span><span class="sxs-lookup"><span data-stu-id="7e12d-1994">A keyword from Keyword_french_drivers_license is found.</span></span>
- <span data-ttu-id="7e12d-1995">La funzione Func_eu_date rileva una data nel formato corretto.</span><span class="sxs-lookup"><span data-stu-id="7e12d-1995">The function Func_eu_date finds a date in the right date format.</span></span>

```xml
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

### <a name="keywords"></a><span data-ttu-id="7e12d-1996">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="7e12d-1996">Keywords</span></span>

#### <a name="keyword_french_drivers_license"></a><span data-ttu-id="7e12d-1997">Keyword_french_drivers_license</span><span class="sxs-lookup"><span data-stu-id="7e12d-1997">Keyword_french_drivers_license</span></span>

- <span data-ttu-id="7e12d-1998">drivers licence</span><span class="sxs-lookup"><span data-stu-id="7e12d-1998">drivers licence</span></span>
- <span data-ttu-id="7e12d-1999">drivers license</span><span class="sxs-lookup"><span data-stu-id="7e12d-1999">drivers license</span></span>
- <span data-ttu-id="7e12d-2000">driving licence</span><span class="sxs-lookup"><span data-stu-id="7e12d-2000">driving licence</span></span>
- <span data-ttu-id="7e12d-2001">driving license</span><span class="sxs-lookup"><span data-stu-id="7e12d-2001">driving license</span></span>
- <span data-ttu-id="7e12d-2002">permis de conduire</span><span class="sxs-lookup"><span data-stu-id="7e12d-2002">permis de conduire</span></span>
- <span data-ttu-id="7e12d-2003">licence number</span><span class="sxs-lookup"><span data-stu-id="7e12d-2003">licence number</span></span>
- <span data-ttu-id="7e12d-2004">license number</span><span class="sxs-lookup"><span data-stu-id="7e12d-2004">license number</span></span>
- <span data-ttu-id="7e12d-2005">licence numbers</span><span class="sxs-lookup"><span data-stu-id="7e12d-2005">licence numbers</span></span>
- <span data-ttu-id="7e12d-2006">license numbers</span><span class="sxs-lookup"><span data-stu-id="7e12d-2006">license numbers</span></span>

## <a name="france-national-id-card-cni"></a><span data-ttu-id="7e12d-2007">Francia - Carta d'identità nazionale (CNI)</span><span class="sxs-lookup"><span data-stu-id="7e12d-2007">France National ID Card (CNI)</span></span>

### <a name="format"></a><span data-ttu-id="7e12d-2008">Formato</span><span class="sxs-lookup"><span data-stu-id="7e12d-2008">Format</span></span>

<span data-ttu-id="7e12d-2009">12 cifre</span><span class="sxs-lookup"><span data-stu-id="7e12d-2009">12 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="7e12d-2010">Modello</span><span class="sxs-lookup"><span data-stu-id="7e12d-2010">Pattern</span></span>

<span data-ttu-id="7e12d-2011">12 cifre</span><span class="sxs-lookup"><span data-stu-id="7e12d-2011">12 digits</span></span>

### <a name="checksum"></a><span data-ttu-id="7e12d-2012">Checksum</span><span class="sxs-lookup"><span data-stu-id="7e12d-2012">Checksum</span></span>

<span data-ttu-id="7e12d-2013">No</span><span class="sxs-lookup"><span data-stu-id="7e12d-2013">No</span></span>

### <a name="definition"></a><span data-ttu-id="7e12d-2014">Definizione</span><span class="sxs-lookup"><span data-stu-id="7e12d-2014">Definition</span></span>

<span data-ttu-id="7e12d-2015">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 65%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="7e12d-2015">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="7e12d-2016">L'espressione regolare Regex_france_cni restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="7e12d-2016">The regular expression Regex_france_cni finds content that matches the pattern.</span></span>

```xml
<!-- France CNI -->
<Entity id="f741ac74-1bc0-4665-b69b-f0c7f927c0c4" patternsProximity="300" recommendedConfidence="65">
  <Pattern confidenceLevel="65">
        <IdMatch idRef="Regex_france_cni" />
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="7e12d-2017">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="7e12d-2017">Keywords</span></span>

<span data-ttu-id="7e12d-2018">Nessuno</span><span class="sxs-lookup"><span data-stu-id="7e12d-2018">None</span></span>
   
## <a name="france-passport-number"></a><span data-ttu-id="7e12d-2019">Francia - Numero di passaporto</span><span class="sxs-lookup"><span data-stu-id="7e12d-2019">France Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="7e12d-2020">Formato</span><span class="sxs-lookup"><span data-stu-id="7e12d-2020">Format</span></span>

<span data-ttu-id="7e12d-2021">Nove cifre e lettere</span><span class="sxs-lookup"><span data-stu-id="7e12d-2021">Nine digits and letters</span></span>

### <a name="pattern"></a><span data-ttu-id="7e12d-2022">Modello</span><span class="sxs-lookup"><span data-stu-id="7e12d-2022">Pattern</span></span>

<span data-ttu-id="7e12d-2023">Nove cifre e lettere:</span><span class="sxs-lookup"><span data-stu-id="7e12d-2023">Nine digits and letters:</span></span>
- <span data-ttu-id="7e12d-2024">Due cifre</span><span class="sxs-lookup"><span data-stu-id="7e12d-2024">Two digits</span></span> 
- <span data-ttu-id="7e12d-2025">Due lettere (senza distinzione tra maiuscole/minuscole)</span><span class="sxs-lookup"><span data-stu-id="7e12d-2025">Two letters (not case sensitive)</span></span> 
- <span data-ttu-id="7e12d-2026">Cinque cifre</span><span class="sxs-lookup"><span data-stu-id="7e12d-2026">Five digits</span></span>

### <a name="checksum"></a><span data-ttu-id="7e12d-2027">Checksum</span><span class="sxs-lookup"><span data-stu-id="7e12d-2027">Checksum</span></span>

<span data-ttu-id="7e12d-2028">No</span><span class="sxs-lookup"><span data-stu-id="7e12d-2028">No</span></span>

### <a name="definition"></a><span data-ttu-id="7e12d-2029">Definizione</span><span class="sxs-lookup"><span data-stu-id="7e12d-2029">Definition</span></span>

<span data-ttu-id="7e12d-2030">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="7e12d-2030">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="7e12d-2031">La funzione Func_fr_passport restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="7e12d-2031">The function Func_fr_passport finds content that matches the pattern.</span></span>
- <span data-ttu-id="7e12d-2032">Viene trovata una parola chiave da Keyword_passport.</span><span class="sxs-lookup"><span data-stu-id="7e12d-2032">A keyword from Keyword_passport is found.</span></span>

```xml
<!-- France Passport Number -->
<Entity id="3008b884-8c8c-4cd8-a289-99f34fc7ff5d" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_fr_passport" />
        <Match idRef="Keyword_passport" />
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="7e12d-2033">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="7e12d-2033">Keywords</span></span>

#### <a name="keyword_passport"></a><span data-ttu-id="7e12d-2034">Keyword_passport</span><span class="sxs-lookup"><span data-stu-id="7e12d-2034">Keyword_passport</span></span>

- <span data-ttu-id="7e12d-2035">Passport Number</span><span class="sxs-lookup"><span data-stu-id="7e12d-2035">Passport Number</span></span>
- <span data-ttu-id="7e12d-2036">Passport No</span><span class="sxs-lookup"><span data-stu-id="7e12d-2036">Passport No</span></span>
- <span data-ttu-id="7e12d-2037">Passport#</span><span class="sxs-lookup"><span data-stu-id="7e12d-2037">Passport #</span></span>
- <span data-ttu-id="7e12d-2038">Passaporto #</span><span class="sxs-lookup"><span data-stu-id="7e12d-2038">Passport#</span></span>
- <span data-ttu-id="7e12d-2039">PassportID</span><span class="sxs-lookup"><span data-stu-id="7e12d-2039">PassportID</span></span>
- <span data-ttu-id="7e12d-2040">Passportno</span><span class="sxs-lookup"><span data-stu-id="7e12d-2040">Passportno</span></span>
- <span data-ttu-id="7e12d-2041">passportnumber</span><span class="sxs-lookup"><span data-stu-id="7e12d-2041">passportnumber</span></span>
- <span data-ttu-id="7e12d-2042">パスポート</span><span class="sxs-lookup"><span data-stu-id="7e12d-2042">パスポート</span></span>
- <span data-ttu-id="7e12d-2043">パスポート番号</span><span class="sxs-lookup"><span data-stu-id="7e12d-2043">パスポート番号</span></span>
- <span data-ttu-id="7e12d-2044">パスポートのNum</span><span class="sxs-lookup"><span data-stu-id="7e12d-2044">パスポートのNum</span></span>
- <span data-ttu-id="7e12d-2045">パスポート ＃</span><span class="sxs-lookup"><span data-stu-id="7e12d-2045">パスポート ＃</span></span> 
- <span data-ttu-id="7e12d-2046">Numéro de passeport</span><span class="sxs-lookup"><span data-stu-id="7e12d-2046">Numéro de passeport</span></span>
- <span data-ttu-id="7e12d-2047">Passeport n °</span><span class="sxs-lookup"><span data-stu-id="7e12d-2047">Passeport n °</span></span>
- <span data-ttu-id="7e12d-2048">Passeport Non</span><span class="sxs-lookup"><span data-stu-id="7e12d-2048">Passeport Non</span></span>
- <span data-ttu-id="7e12d-2049">Passeport#</span><span class="sxs-lookup"><span data-stu-id="7e12d-2049">Passeport #</span></span>
- <span data-ttu-id="7e12d-2050">Passeport #</span><span class="sxs-lookup"><span data-stu-id="7e12d-2050">Passeport#</span></span>
- <span data-ttu-id="7e12d-2051">PasseportNon</span><span class="sxs-lookup"><span data-stu-id="7e12d-2051">PasseportNon</span></span>
- <span data-ttu-id="7e12d-2052">Passeportn °</span><span class="sxs-lookup"><span data-stu-id="7e12d-2052">Passeportn °</span></span>

      
## <a name="france-social-security-number-insee"></a><span data-ttu-id="7e12d-2053">Francia - Numero di previdenza sociale (INSEE)</span><span class="sxs-lookup"><span data-stu-id="7e12d-2053">France Social Security Number (INSEE)</span></span>

### <a name="format"></a><span data-ttu-id="7e12d-2054">Formato</span><span class="sxs-lookup"><span data-stu-id="7e12d-2054">Format</span></span>

<span data-ttu-id="7e12d-2055">15 cifre</span><span class="sxs-lookup"><span data-stu-id="7e12d-2055">15 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="7e12d-2056">Modello</span><span class="sxs-lookup"><span data-stu-id="7e12d-2056">Pattern</span></span>

<span data-ttu-id="7e12d-2057">Deve corrispondere a uno di questi due modelli:</span><span class="sxs-lookup"><span data-stu-id="7e12d-2057">Must match one of two patterns:</span></span>
- <span data-ttu-id="7e12d-2058">13 cifre seguite da uno spazio seguito da due cifre</span><span class="sxs-lookup"><span data-stu-id="7e12d-2058">13 digits followed by a space followed by two digits</span></span><br/>
<span data-ttu-id="7e12d-2059">oppure</span><span class="sxs-lookup"><span data-stu-id="7e12d-2059">or</span></span>
- <span data-ttu-id="7e12d-2060">15 cifre consecutive</span><span class="sxs-lookup"><span data-stu-id="7e12d-2060">15 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="7e12d-2061">Checksum</span><span class="sxs-lookup"><span data-stu-id="7e12d-2061">Checksum</span></span>

<span data-ttu-id="7e12d-2062">Sì</span><span class="sxs-lookup"><span data-stu-id="7e12d-2062">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="7e12d-2063">Definizione</span><span class="sxs-lookup"><span data-stu-id="7e12d-2063">Definition</span></span>

<span data-ttu-id="7e12d-2064">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 95%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="7e12d-2064">A DLP policy is 95% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="7e12d-2065">La funzione Func_french_insee o Func_fr_insee trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="7e12d-2065">The function Func_french_insee or Func_fr_insee finds content that matches the pattern.</span></span>
- <span data-ttu-id="7e12d-2066">Viene trovata una parola chiave da Keyword_fr_insee.</span><span class="sxs-lookup"><span data-stu-id="7e12d-2066">A keyword from Keyword_fr_insee is found.</span></span>
- <span data-ttu-id="7e12d-2067">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="7e12d-2067">The checksum passes.</span></span>

<span data-ttu-id="7e12d-2068">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="7e12d-2068">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="7e12d-2069">La funzione Func_french_insee o Func_fr_insee trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="7e12d-2069">The function Func_french_insee or Func_fr_insee finds content that matches the pattern.</span></span>
- <span data-ttu-id="7e12d-2070">Non vengono trovate parole chiave da Keyword_fr_insee.</span><span class="sxs-lookup"><span data-stu-id="7e12d-2070">No keyword from Keyword_fr_insee is found.</span></span>
- <span data-ttu-id="7e12d-2071">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="7e12d-2071">The checksum passes.</span></span>

```xml
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

### <a name="keywords"></a><span data-ttu-id="7e12d-2072">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="7e12d-2072">Keywords</span></span>

#### <a name="keyword_fr_insee"></a><span data-ttu-id="7e12d-2073">Keyword_fr_insee</span><span class="sxs-lookup"><span data-stu-id="7e12d-2073">Keyword_fr_insee</span></span>

- <span data-ttu-id="7e12d-2074">INSEE</span><span class="sxs-lookup"><span data-stu-id="7e12d-2074">insee</span></span>
- <span data-ttu-id="7e12d-2075">securité sociale</span><span class="sxs-lookup"><span data-stu-id="7e12d-2075">securité sociale</span></span>
- <span data-ttu-id="7e12d-2076">securite sociale</span><span class="sxs-lookup"><span data-stu-id="7e12d-2076">securite sociale</span></span>
- <span data-ttu-id="7e12d-2077">national id</span><span class="sxs-lookup"><span data-stu-id="7e12d-2077">national id</span></span>
- <span data-ttu-id="7e12d-2078">national identification</span><span class="sxs-lookup"><span data-stu-id="7e12d-2078">national identification</span></span>
- <span data-ttu-id="7e12d-2079">numéro d'identité</span><span class="sxs-lookup"><span data-stu-id="7e12d-2079">numéro d'identité</span></span>
- <span data-ttu-id="7e12d-2080">no d'identité</span><span class="sxs-lookup"><span data-stu-id="7e12d-2080">no d'identité</span></span>
- <span data-ttu-id="7e12d-2081">No.</span><span class="sxs-lookup"><span data-stu-id="7e12d-2081">no.</span></span> <span data-ttu-id="7e12d-2082">d'identité</span><span class="sxs-lookup"><span data-stu-id="7e12d-2082">d'identité</span></span>
- <span data-ttu-id="7e12d-2083">numero d'identite</span><span class="sxs-lookup"><span data-stu-id="7e12d-2083">numero d'identite</span></span>
- <span data-ttu-id="7e12d-2084">no d'identite</span><span class="sxs-lookup"><span data-stu-id="7e12d-2084">no d'identite</span></span>
- <span data-ttu-id="7e12d-2085">No.</span><span class="sxs-lookup"><span data-stu-id="7e12d-2085">no.</span></span> <span data-ttu-id="7e12d-2086">d'identite</span><span class="sxs-lookup"><span data-stu-id="7e12d-2086">d'identite</span></span>
- <span data-ttu-id="7e12d-2087">social security number</span><span class="sxs-lookup"><span data-stu-id="7e12d-2087">social security number</span></span>
- <span data-ttu-id="7e12d-2088">social security code</span><span class="sxs-lookup"><span data-stu-id="7e12d-2088">social security code</span></span>
- <span data-ttu-id="7e12d-2089">social insurance number</span><span class="sxs-lookup"><span data-stu-id="7e12d-2089">social insurance number</span></span>
- <span data-ttu-id="7e12d-2090">le numéro d'identification nationale</span><span class="sxs-lookup"><span data-stu-id="7e12d-2090">le numéro d'identification nationale</span></span>
- <span data-ttu-id="7e12d-2091">d'identité nationale</span><span class="sxs-lookup"><span data-stu-id="7e12d-2091">d'identité nationale</span></span>
- <span data-ttu-id="7e12d-2092">numéro de sécurité sociale</span><span class="sxs-lookup"><span data-stu-id="7e12d-2092">numéro de sécurité sociale</span></span>
- <span data-ttu-id="7e12d-2093">le code de la sécurité sociale</span><span class="sxs-lookup"><span data-stu-id="7e12d-2093">le code de la sécurité sociale</span></span>
- <span data-ttu-id="7e12d-2094">numéro d'assurance sociale</span><span class="sxs-lookup"><span data-stu-id="7e12d-2094">numéro d'assurance sociale</span></span>
- <span data-ttu-id="7e12d-2095">numéro de sécu</span><span class="sxs-lookup"><span data-stu-id="7e12d-2095">numéro de sécu</span></span>
- <span data-ttu-id="7e12d-2096">code sécu</span><span class="sxs-lookup"><span data-stu-id="7e12d-2096">code sécu</span></span> 
   
## <a name="german-drivers-license-number"></a><span data-ttu-id="7e12d-2097">Germania - Numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="7e12d-2097">German Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="7e12d-2098">Formato</span><span class="sxs-lookup"><span data-stu-id="7e12d-2098">Format</span></span>

<span data-ttu-id="7e12d-2099">Combinazione di 11 cifre e lettere</span><span class="sxs-lookup"><span data-stu-id="7e12d-2099">Combination of 11 digits and letters</span></span>

### <a name="pattern"></a><span data-ttu-id="7e12d-2100">Modello</span><span class="sxs-lookup"><span data-stu-id="7e12d-2100">Pattern</span></span>

<span data-ttu-id="7e12d-2101">11 cifre e lettere (senza distinzione tra maiuscole/minuscole):</span><span class="sxs-lookup"><span data-stu-id="7e12d-2101">11 digits and letters (not case sensitive):</span></span>
- <span data-ttu-id="7e12d-2102">Una cifra o una lettera</span><span class="sxs-lookup"><span data-stu-id="7e12d-2102">A digit or letter</span></span> 
- <span data-ttu-id="7e12d-2103">Due cifre</span><span class="sxs-lookup"><span data-stu-id="7e12d-2103">Two digits</span></span> 
- <span data-ttu-id="7e12d-2104">Sei cifre o lettere</span><span class="sxs-lookup"><span data-stu-id="7e12d-2104">Six digits or letters</span></span> 
- <span data-ttu-id="7e12d-2105">Una cifra</span><span class="sxs-lookup"><span data-stu-id="7e12d-2105">A digit</span></span> 
- <span data-ttu-id="7e12d-2106">Una cifra o una lettera</span><span class="sxs-lookup"><span data-stu-id="7e12d-2106">A digit or letter</span></span>

### <a name="checksum"></a><span data-ttu-id="7e12d-2107">Checksum</span><span class="sxs-lookup"><span data-stu-id="7e12d-2107">Checksum</span></span>

<span data-ttu-id="7e12d-2108">Sì</span><span class="sxs-lookup"><span data-stu-id="7e12d-2108">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="7e12d-2109">Definizione</span><span class="sxs-lookup"><span data-stu-id="7e12d-2109">Definition</span></span>

<span data-ttu-id="7e12d-2110">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="7e12d-2110">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="7e12d-2111">La funzione Func_german_drivers_license restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="7e12d-2111">The function Func_german_drivers_license finds content that matches the pattern.</span></span>
- <span data-ttu-id="7e12d-2112">Si verifica almeno una delle situazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="7e12d-2112">At least one of the following is true:</span></span>
    - <span data-ttu-id="7e12d-2113">Viene trovata una parola chiave da Keyword_german_drivers_license_number.</span><span class="sxs-lookup"><span data-stu-id="7e12d-2113">A keyword from Keyword_german_drivers_license_number is found.</span></span>
    - <span data-ttu-id="7e12d-2114">Viene trovata una parola chiave da Keyword_german_drivers_license_collaborative.</span><span class="sxs-lookup"><span data-stu-id="7e12d-2114">A keyword from Keyword_german_drivers_license_collaborative is found.</span></span>
    - <span data-ttu-id="7e12d-2115">Viene trovata una parola chiave da Keyword_german_drivers_license.</span><span class="sxs-lookup"><span data-stu-id="7e12d-2115">A keyword from Keyword_german_drivers_license is found.</span></span>
- <span data-ttu-id="7e12d-2116">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="7e12d-2116">The checksum passes.</span></span>

```xml
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

### <a name="keywords"></a><span data-ttu-id="7e12d-2117">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="7e12d-2117">Keywords</span></span>

#### <a name="keyword_german_drivers_license_number"></a><span data-ttu-id="7e12d-2118">Keyword_german_drivers_license_number</span><span class="sxs-lookup"><span data-stu-id="7e12d-2118">Keyword_german_drivers_license_number</span></span>

- <span data-ttu-id="7e12d-2119">Führerschein</span><span class="sxs-lookup"><span data-stu-id="7e12d-2119">Führerschein</span></span>
- <span data-ttu-id="7e12d-2120">Fuhrerschein</span><span class="sxs-lookup"><span data-stu-id="7e12d-2120">Fuhrerschein</span></span>
- <span data-ttu-id="7e12d-2121">Fuehrerschein</span><span class="sxs-lookup"><span data-stu-id="7e12d-2121">Fuehrerschein</span></span>
- <span data-ttu-id="7e12d-2122">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="7e12d-2122">Führerscheinnummer</span></span>
- <span data-ttu-id="7e12d-2123">Fuhrerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="7e12d-2123">Fuhrerscheinnummer</span></span>
- <span data-ttu-id="7e12d-2124">Fuehrerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="7e12d-2124">Fuehrerscheinnummer</span></span>
- <span data-ttu-id="7e12d-2125">Führerschein-</span><span class="sxs-lookup"><span data-stu-id="7e12d-2125">Führerschein-</span></span> 
- <span data-ttu-id="7e12d-2126">Fuhrerschein-</span><span class="sxs-lookup"><span data-stu-id="7e12d-2126">Fuhrerschein-</span></span> 
- <span data-ttu-id="7e12d-2127">Fuehrerschein-</span><span class="sxs-lookup"><span data-stu-id="7e12d-2127">Fuehrerschein-</span></span> 
- <span data-ttu-id="7e12d-2128">FührerscheinnummerNr</span><span class="sxs-lookup"><span data-stu-id="7e12d-2128">FührerscheinnummerNr</span></span>
- <span data-ttu-id="7e12d-2129">FuhrerscheinnummerNr</span><span class="sxs-lookup"><span data-stu-id="7e12d-2129">FuhrerscheinnummerNr</span></span>
- <span data-ttu-id="7e12d-2130">FuehrerscheinnummerNr</span><span class="sxs-lookup"><span data-stu-id="7e12d-2130">FuehrerscheinnummerNr</span></span>
- <span data-ttu-id="7e12d-2131">FührerscheinnummerKlasse</span><span class="sxs-lookup"><span data-stu-id="7e12d-2131">FührerscheinnummerKlasse</span></span>
- <span data-ttu-id="7e12d-2132">FuhrerscheinnummerKlasse</span><span class="sxs-lookup"><span data-stu-id="7e12d-2132">FuhrerscheinnummerKlasse</span></span>
- <span data-ttu-id="7e12d-2133">FuehrerscheinnummerKlasse</span><span class="sxs-lookup"><span data-stu-id="7e12d-2133">FuehrerscheinnummerKlasse</span></span>
- <span data-ttu-id="7e12d-2134">Führerschein- Nr</span><span class="sxs-lookup"><span data-stu-id="7e12d-2134">Führerschein- Nr</span></span>
- <span data-ttu-id="7e12d-2135">Fuhrerschein- Nr</span><span class="sxs-lookup"><span data-stu-id="7e12d-2135">Fuhrerschein- Nr</span></span>
- <span data-ttu-id="7e12d-2136">Fuehrerschein- Nr</span><span class="sxs-lookup"><span data-stu-id="7e12d-2136">Fuehrerschein- Nr</span></span> 
- <span data-ttu-id="7e12d-2137">Führerschein- Klasse</span><span class="sxs-lookup"><span data-stu-id="7e12d-2137">Führerschein- Klasse</span></span> 
- <span data-ttu-id="7e12d-2138">Fuhrerschein- Klasse</span><span class="sxs-lookup"><span data-stu-id="7e12d-2138">Fuhrerschein- Klasse</span></span> 
- <span data-ttu-id="7e12d-2139">Fuehrerschein- Klasse</span><span class="sxs-lookup"><span data-stu-id="7e12d-2139">Fuehrerschein- Klasse</span></span>
- <span data-ttu-id="7e12d-2140">FührerscheinnummerNr</span><span class="sxs-lookup"><span data-stu-id="7e12d-2140">FührerscheinnummerNr</span></span> 
- <span data-ttu-id="7e12d-2141">FuhrerscheinnummerNr</span><span class="sxs-lookup"><span data-stu-id="7e12d-2141">FuhrerscheinnummerNr</span></span> 
- <span data-ttu-id="7e12d-2142">FuehrerscheinnummerNr</span><span class="sxs-lookup"><span data-stu-id="7e12d-2142">FuehrerscheinnummerNr</span></span> 
- <span data-ttu-id="7e12d-2143">FührerscheinnummerKlasse</span><span class="sxs-lookup"><span data-stu-id="7e12d-2143">FührerscheinnummerKlasse</span></span> 
- <span data-ttu-id="7e12d-2144">FuhrerscheinnummerKlasse</span><span class="sxs-lookup"><span data-stu-id="7e12d-2144">FuhrerscheinnummerKlasse</span></span> 
- <span data-ttu-id="7e12d-2145">FuehrerscheinnummerKlasse</span><span class="sxs-lookup"><span data-stu-id="7e12d-2145">FuehrerscheinnummerKlasse</span></span> 
- <span data-ttu-id="7e12d-2146">Führerschein- Nr</span><span class="sxs-lookup"><span data-stu-id="7e12d-2146">Führerschein- Nr</span></span> 
- <span data-ttu-id="7e12d-2147">Fuhrerschein- Nr</span><span class="sxs-lookup"><span data-stu-id="7e12d-2147">Fuhrerschein- Nr</span></span> 
- <span data-ttu-id="7e12d-2148">Fuehrerschein- Nr</span><span class="sxs-lookup"><span data-stu-id="7e12d-2148">Fuehrerschein- Nr</span></span> 
- <span data-ttu-id="7e12d-2149">Führerschein- Klasse</span><span class="sxs-lookup"><span data-stu-id="7e12d-2149">Führerschein- Klasse</span></span> 
- <span data-ttu-id="7e12d-2150">Fuhrerschein- Klasse</span><span class="sxs-lookup"><span data-stu-id="7e12d-2150">Fuhrerschein- Klasse</span></span> 
- <span data-ttu-id="7e12d-2151">Fuehrerschein- Klasse</span><span class="sxs-lookup"><span data-stu-id="7e12d-2151">Fuehrerschein- Klasse</span></span> 
- <span data-ttu-id="7e12d-2152">DL</span><span class="sxs-lookup"><span data-stu-id="7e12d-2152">DL</span></span> 
- <span data-ttu-id="7e12d-2153">DLS</span><span class="sxs-lookup"><span data-stu-id="7e12d-2153">DLS</span></span>
- <span data-ttu-id="7e12d-2154">Driv Lic</span><span class="sxs-lookup"><span data-stu-id="7e12d-2154">Driv Lic</span></span> 
- <span data-ttu-id="7e12d-2155">Driv Licen</span><span class="sxs-lookup"><span data-stu-id="7e12d-2155">Driv Licen</span></span> 
- <span data-ttu-id="7e12d-2156">Driv License</span><span class="sxs-lookup"><span data-stu-id="7e12d-2156">Driv License</span></span>
- <span data-ttu-id="7e12d-2157">Driv Licenses</span><span class="sxs-lookup"><span data-stu-id="7e12d-2157">Driv Licenses</span></span> 
- <span data-ttu-id="7e12d-2158">Driv Licence</span><span class="sxs-lookup"><span data-stu-id="7e12d-2158">Driv Licence</span></span> 
- <span data-ttu-id="7e12d-2159">Driv Licences</span><span class="sxs-lookup"><span data-stu-id="7e12d-2159">Driv Licences</span></span> 
- <span data-ttu-id="7e12d-2160">Driv Lic</span><span class="sxs-lookup"><span data-stu-id="7e12d-2160">Driv Lic</span></span> 
- <span data-ttu-id="7e12d-2161">Driver Licen</span><span class="sxs-lookup"><span data-stu-id="7e12d-2161">Driver Licen</span></span> 
- <span data-ttu-id="7e12d-2162">Driver License</span><span class="sxs-lookup"><span data-stu-id="7e12d-2162">Driver License</span></span> 
- <span data-ttu-id="7e12d-2163">Driver Licenses</span><span class="sxs-lookup"><span data-stu-id="7e12d-2163">Driver Licenses</span></span> 
- <span data-ttu-id="7e12d-2164">Driver Licence</span><span class="sxs-lookup"><span data-stu-id="7e12d-2164">Driver Licence</span></span> 
- <span data-ttu-id="7e12d-2165">Driver Licences</span><span class="sxs-lookup"><span data-stu-id="7e12d-2165">Driver Licences</span></span> 
- <span data-ttu-id="7e12d-2166">Drivers Lic</span><span class="sxs-lookup"><span data-stu-id="7e12d-2166">Drivers Lic</span></span> 
- <span data-ttu-id="7e12d-2167">Drivers Licen</span><span class="sxs-lookup"><span data-stu-id="7e12d-2167">Drivers Licen</span></span> 
- <span data-ttu-id="7e12d-2168">Drivers License</span><span class="sxs-lookup"><span data-stu-id="7e12d-2168">Drivers License</span></span> 
- <span data-ttu-id="7e12d-2169">Drivers Licenses</span><span class="sxs-lookup"><span data-stu-id="7e12d-2169">Drivers Licenses</span></span> 
- <span data-ttu-id="7e12d-2170">Drivers Licence</span><span class="sxs-lookup"><span data-stu-id="7e12d-2170">Drivers Licence</span></span> 
- <span data-ttu-id="7e12d-2171">Drivers Licences</span><span class="sxs-lookup"><span data-stu-id="7e12d-2171">Drivers Licences</span></span> 
- <span data-ttu-id="7e12d-2172">Driver's Lic</span><span class="sxs-lookup"><span data-stu-id="7e12d-2172">Driver's Lic</span></span> 
- <span data-ttu-id="7e12d-2173">Driver's Licen</span><span class="sxs-lookup"><span data-stu-id="7e12d-2173">Driver's Licen</span></span> 
- <span data-ttu-id="7e12d-2174">Driver's License</span><span class="sxs-lookup"><span data-stu-id="7e12d-2174">Driver's License</span></span> 
- <span data-ttu-id="7e12d-2175">Driver's Licenses</span><span class="sxs-lookup"><span data-stu-id="7e12d-2175">Driver's Licenses</span></span> 
- <span data-ttu-id="7e12d-2176">Driver's Licence</span><span class="sxs-lookup"><span data-stu-id="7e12d-2176">Driver's Licence</span></span> 
- <span data-ttu-id="7e12d-2177">Driver's Licences</span><span class="sxs-lookup"><span data-stu-id="7e12d-2177">Driver's Licences</span></span> 
- <span data-ttu-id="7e12d-2178">Driving Lic</span><span class="sxs-lookup"><span data-stu-id="7e12d-2178">Driving Lic</span></span> 
- <span data-ttu-id="7e12d-2179">Driving Licen</span><span class="sxs-lookup"><span data-stu-id="7e12d-2179">Driving Licen</span></span> 
- <span data-ttu-id="7e12d-2180">Driving License</span><span class="sxs-lookup"><span data-stu-id="7e12d-2180">Driving License</span></span> 
- <span data-ttu-id="7e12d-2181">Driving Licenses</span><span class="sxs-lookup"><span data-stu-id="7e12d-2181">Driving Licenses</span></span> 
- <span data-ttu-id="7e12d-2182">Driving Licence</span><span class="sxs-lookup"><span data-stu-id="7e12d-2182">Driving Licence</span></span> 
- <span data-ttu-id="7e12d-2183">Driving Licences</span><span class="sxs-lookup"><span data-stu-id="7e12d-2183">Driving Licences</span></span>

#### <a name="keyword_german_drivers_license_collaborative"></a><span data-ttu-id="7e12d-2184">Keyword_german_drivers_license_collaborative</span><span class="sxs-lookup"><span data-stu-id="7e12d-2184">Keyword_german_drivers_license_collaborative</span></span>

- <span data-ttu-id="7e12d-2185">Nr-Führerschein</span><span class="sxs-lookup"><span data-stu-id="7e12d-2185">Nr-Führerschein</span></span> 
- <span data-ttu-id="7e12d-2186">Nr-Fuhrerschein</span><span class="sxs-lookup"><span data-stu-id="7e12d-2186">Nr-Fuhrerschein</span></span> 
- <span data-ttu-id="7e12d-2187">Nr-Fuehrerschein</span><span class="sxs-lookup"><span data-stu-id="7e12d-2187">Nr-Fuehrerschein</span></span> 
- <span data-ttu-id="7e12d-2188">No-Führerschein</span><span class="sxs-lookup"><span data-stu-id="7e12d-2188">No-Führerschein</span></span> 
- <span data-ttu-id="7e12d-2189">No-Fuhrerschein</span><span class="sxs-lookup"><span data-stu-id="7e12d-2189">No-Fuhrerschein</span></span> 
- <span data-ttu-id="7e12d-2190">No-Fuehrerschein</span><span class="sxs-lookup"><span data-stu-id="7e12d-2190">No-Fuehrerschein</span></span> 
- <span data-ttu-id="7e12d-2191">N-Führerschein</span><span class="sxs-lookup"><span data-stu-id="7e12d-2191">N-Führerschein</span></span> 
- <span data-ttu-id="7e12d-2192">N-Fuhrerschein</span><span class="sxs-lookup"><span data-stu-id="7e12d-2192">N-Fuhrerschein</span></span> 
- <span data-ttu-id="7e12d-2193">N-Fuehrerschein</span><span class="sxs-lookup"><span data-stu-id="7e12d-2193">N-Fuehrerschein</span></span>
- <span data-ttu-id="7e12d-2194">Nr-Führerschein</span><span class="sxs-lookup"><span data-stu-id="7e12d-2194">Nr-Führerschein</span></span> 
- <span data-ttu-id="7e12d-2195">Nr-Fuhrerschein</span><span class="sxs-lookup"><span data-stu-id="7e12d-2195">Nr-Fuhrerschein</span></span> 
- <span data-ttu-id="7e12d-2196">Nr-Fuehrerschein</span><span class="sxs-lookup"><span data-stu-id="7e12d-2196">Nr-Fuehrerschein</span></span> 
- <span data-ttu-id="7e12d-2197">No-Führerschein</span><span class="sxs-lookup"><span data-stu-id="7e12d-2197">No-Führerschein</span></span> 
- <span data-ttu-id="7e12d-2198">No-Fuhrerschein</span><span class="sxs-lookup"><span data-stu-id="7e12d-2198">No-Fuhrerschein</span></span> 
- <span data-ttu-id="7e12d-2199">No-Fuehrerschein</span><span class="sxs-lookup"><span data-stu-id="7e12d-2199">No-Fuehrerschein</span></span> 
- <span data-ttu-id="7e12d-2200">N-Führerschein</span><span class="sxs-lookup"><span data-stu-id="7e12d-2200">N-Führerschein</span></span> 
- <span data-ttu-id="7e12d-2201">N-Fuhrerschein</span><span class="sxs-lookup"><span data-stu-id="7e12d-2201">N-Fuhrerschein</span></span> 
- <span data-ttu-id="7e12d-2202">N-Fuehrerschein</span><span class="sxs-lookup"><span data-stu-id="7e12d-2202">N-Fuehrerschein</span></span> 

#### <a name="keyword_german_drivers_license"></a><span data-ttu-id="7e12d-2203">Keyword_german_drivers_license</span><span class="sxs-lookup"><span data-stu-id="7e12d-2203">Keyword_german_drivers_license</span></span>

- <span data-ttu-id="7e12d-2204">ausstellungsdatum</span><span class="sxs-lookup"><span data-stu-id="7e12d-2204">ausstellungsdatum</span></span>
- <span data-ttu-id="7e12d-2205">ausstellungsort</span><span class="sxs-lookup"><span data-stu-id="7e12d-2205">ausstellungsort</span></span>
- <span data-ttu-id="7e12d-2206">ausstellende behöde</span><span class="sxs-lookup"><span data-stu-id="7e12d-2206">ausstellende behöde</span></span>
- <span data-ttu-id="7e12d-2207">ausstellende behorde</span><span class="sxs-lookup"><span data-stu-id="7e12d-2207">ausstellende behorde</span></span>
- <span data-ttu-id="7e12d-2208">ausstellende behoerde</span><span class="sxs-lookup"><span data-stu-id="7e12d-2208">ausstellende behoerde</span></span>
   
## <a name="german-passport-number"></a><span data-ttu-id="7e12d-2209">Germania - Numero di passaporto</span><span class="sxs-lookup"><span data-stu-id="7e12d-2209">German Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="7e12d-2210">Formato</span><span class="sxs-lookup"><span data-stu-id="7e12d-2210">Format</span></span>

<span data-ttu-id="7e12d-2211">10 cifre o lettere</span><span class="sxs-lookup"><span data-stu-id="7e12d-2211">10 digits or letters</span></span>

### <a name="pattern"></a><span data-ttu-id="7e12d-2212">Modello</span><span class="sxs-lookup"><span data-stu-id="7e12d-2212">Pattern</span></span>

<span data-ttu-id="7e12d-2213">Il modello deve includere tutti gli elementi seguenti:</span><span class="sxs-lookup"><span data-stu-id="7e12d-2213">Pattern must include all of the following:</span></span>
- <span data-ttu-id="7e12d-2214">Il primo carattere è una cifra o una lettera del gruppo seguente: C, F, G, H, J, K</span><span class="sxs-lookup"><span data-stu-id="7e12d-2214">First character is a digit or a letter from this set (C, F, G, H, J, K)</span></span> 
- <span data-ttu-id="7e12d-2215">Tre cifre</span><span class="sxs-lookup"><span data-stu-id="7e12d-2215">Three digits</span></span> 
- <span data-ttu-id="7e12d-2216">Cinque cifre o lettere del gruppo seguente: C, -H, J-N, P, R, T, V-Z</span><span class="sxs-lookup"><span data-stu-id="7e12d-2216">Five digits or letters from this set (C, -H, J-N, P, R, T, V-Z)</span></span> 
- <span data-ttu-id="7e12d-2217">Una cifra</span><span class="sxs-lookup"><span data-stu-id="7e12d-2217">A digit</span></span>

### <a name="checksum"></a><span data-ttu-id="7e12d-2218">Checksum</span><span class="sxs-lookup"><span data-stu-id="7e12d-2218">Checksum</span></span>

<span data-ttu-id="7e12d-2219">Sì</span><span class="sxs-lookup"><span data-stu-id="7e12d-2219">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="7e12d-2220">Definizione</span><span class="sxs-lookup"><span data-stu-id="7e12d-2220">Definition</span></span>

<span data-ttu-id="7e12d-2221">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="7e12d-2221">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="7e12d-2222">La funzione Func_german_passport restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="7e12d-2222">The function Func_german_passport finds content that matches the pattern.</span></span>
- <span data-ttu-id="7e12d-2223">Viene trovata una parola chiave fra le cinque elencate.</span><span class="sxs-lookup"><span data-stu-id="7e12d-2223">A keyword from any of the five keyword lists is found.</span></span>
- <span data-ttu-id="7e12d-2224">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="7e12d-2224">The checksum passes.</span></span>

<span data-ttu-id="7e12d-2225">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="7e12d-2225">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="7e12d-2226">La funzione Func_german_passport_data restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="7e12d-2226">The function Func_german_passport_data finds content that matches the pattern.</span></span>
- <span data-ttu-id="7e12d-2227">Viene trovata una parola chiave fra le cinque elencate.</span><span class="sxs-lookup"><span data-stu-id="7e12d-2227">A keyword from any of the five keyword lists is found.</span></span>
- <span data-ttu-id="7e12d-2228">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="7e12d-2228">The checksum passes.</span></span>

```xml
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

### <a name="keywords"></a><span data-ttu-id="7e12d-2229">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="7e12d-2229">Keywords</span></span>

#### <a name="keyword_german_passport"></a><span data-ttu-id="7e12d-2230">Keyword_german_passport</span><span class="sxs-lookup"><span data-stu-id="7e12d-2230">Keyword_german_passport</span></span>

- <span data-ttu-id="7e12d-2231">reisepass</span><span class="sxs-lookup"><span data-stu-id="7e12d-2231">reisepass</span></span>
- <span data-ttu-id="7e12d-2232">reisepasse</span><span class="sxs-lookup"><span data-stu-id="7e12d-2232">reisepasse</span></span>
- <span data-ttu-id="7e12d-2233">reisepassnummer</span><span class="sxs-lookup"><span data-stu-id="7e12d-2233">reisepassnummer</span></span>
- <span data-ttu-id="7e12d-2234">passaporto</span><span class="sxs-lookup"><span data-stu-id="7e12d-2234">passport</span></span>
- <span data-ttu-id="7e12d-2235">passaporti</span><span class="sxs-lookup"><span data-stu-id="7e12d-2235">passports</span></span>

#### <a name="keyword_german_passport_collaborative"></a><span data-ttu-id="7e12d-2236">Keyword_german_passport_collaborative</span><span class="sxs-lookup"><span data-stu-id="7e12d-2236">Keyword_german_passport_collaborative</span></span>

- <span data-ttu-id="7e12d-2237">geburtsdatum</span><span class="sxs-lookup"><span data-stu-id="7e12d-2237">geburtsdatum</span></span>
- <span data-ttu-id="7e12d-2238">ausstellungsdatum</span><span class="sxs-lookup"><span data-stu-id="7e12d-2238">ausstellungsdatum</span></span>
- <span data-ttu-id="7e12d-2239">ausstellungsort</span><span class="sxs-lookup"><span data-stu-id="7e12d-2239">ausstellungsort</span></span>

#### <a name="keyword_german_passport_number"></a><span data-ttu-id="7e12d-2240">Keyword_german_passport_number</span><span class="sxs-lookup"><span data-stu-id="7e12d-2240">Keyword_german_passport_number</span></span>

<span data-ttu-id="7e12d-2241">No-Reisepass Nr-Reisepass</span><span class="sxs-lookup"><span data-stu-id="7e12d-2241">No-Reisepass Nr-Reisepass</span></span>

#### <a name="keyword_german_passport1"></a><span data-ttu-id="7e12d-2242">Keyword_german_passport1</span><span class="sxs-lookup"><span data-stu-id="7e12d-2242">Keyword_german_passport1</span></span>

<span data-ttu-id="7e12d-2243">Reisepass-Nr</span><span class="sxs-lookup"><span data-stu-id="7e12d-2243">Reisepass-Nr</span></span>

#### <a name="keyword_german_passport2"></a><span data-ttu-id="7e12d-2244">Keyword_german_passport2</span><span class="sxs-lookup"><span data-stu-id="7e12d-2244">Keyword_german_passport2</span></span>

<span data-ttu-id="7e12d-2245">bnationalit. t</span><span class="sxs-lookup"><span data-stu-id="7e12d-2245">bnationalit.t</span></span>
   
## <a name="germany-identity-card-number"></a><span data-ttu-id="7e12d-2246">Germania - Numero carta di identità</span><span class="sxs-lookup"><span data-stu-id="7e12d-2246">Germany Identity Card Number</span></span>

### <a name="format"></a><span data-ttu-id="7e12d-2247">Formato</span><span class="sxs-lookup"><span data-stu-id="7e12d-2247">Format</span></span>

<span data-ttu-id="7e12d-2248">Dal 1 ° novembre 2010: nove lettere e cifre</span><span class="sxs-lookup"><span data-stu-id="7e12d-2248">Since 1 November 2010: Nine letters and digits</span></span>

<span data-ttu-id="7e12d-2249">Dal 1 ° aprile 1987 al 31 ottobre 2010:10 cifre</span><span class="sxs-lookup"><span data-stu-id="7e12d-2249">From 1 April 1987 until 31 October 2010: 10 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="7e12d-2250">Modello</span><span class="sxs-lookup"><span data-stu-id="7e12d-2250">Pattern</span></span>

<span data-ttu-id="7e12d-2251">A partire dal 1° novembre 2010:</span><span class="sxs-lookup"><span data-stu-id="7e12d-2251">Since 1 November 2010:</span></span>
- <span data-ttu-id="7e12d-2252">Una lettera (senza distinzione tra maiuscole/minuscole)</span><span class="sxs-lookup"><span data-stu-id="7e12d-2252">One letter (not case sensitive)</span></span> 
- <span data-ttu-id="7e12d-2253">Otto cifre</span><span class="sxs-lookup"><span data-stu-id="7e12d-2253">Eight digits</span></span>

<span data-ttu-id="7e12d-2254">Dal 1 ° aprile 1987 al 31 ottobre 2010:</span><span class="sxs-lookup"><span data-stu-id="7e12d-2254">From 1 April 1987 until 31 October 2010:</span></span>
- <span data-ttu-id="7e12d-2255">10 cifre</span><span class="sxs-lookup"><span data-stu-id="7e12d-2255">10 digits</span></span>

### <a name="checksum"></a><span data-ttu-id="7e12d-2256">Checksum</span><span class="sxs-lookup"><span data-stu-id="7e12d-2256">Checksum</span></span>

<span data-ttu-id="7e12d-2257">No</span><span class="sxs-lookup"><span data-stu-id="7e12d-2257">No</span></span>

### <a name="definition"></a><span data-ttu-id="7e12d-2258">Definizione</span><span class="sxs-lookup"><span data-stu-id="7e12d-2258">Definition</span></span>

<span data-ttu-id="7e12d-2259">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 65%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="7e12d-2259">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="7e12d-2260">L'espressione regolare Regex_germany_id_card trova il contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="7e12d-2260">The regular expression Regex_germany_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="7e12d-2261">Viene trovata una parola chiave da Keyword_germany_id_card.</span><span class="sxs-lookup"><span data-stu-id="7e12d-2261">A keyword from Keyword_germany_id_card is found.</span></span>

```xml
<!-- Germany Identity Card Number -->
<Entity id="e577372f-c42e-47a0-9d85-bebed1c237d4" recommendedConfidence="65" patternsProximity="300">
  <Pattern confidenceLevel="65">
     <IdMatch idRef="Regex_germany_id_card"/>
     <Match idRef="Keyword_germany_id_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="7e12d-2262">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="7e12d-2262">Keywords</span></span>

#### <a name="keyword_germany_id_card"></a><span data-ttu-id="7e12d-2263">Keyword_germany_id_card</span><span class="sxs-lookup"><span data-stu-id="7e12d-2263">Keyword_germany_id_card</span></span>

- <span data-ttu-id="7e12d-2264">Carta di identità</span><span class="sxs-lookup"><span data-stu-id="7e12d-2264">Identity Card</span></span>
- <span data-ttu-id="7e12d-2265">ID</span><span class="sxs-lookup"><span data-stu-id="7e12d-2265">ID</span></span>
- <span data-ttu-id="7e12d-2266">Identificazione</span><span class="sxs-lookup"><span data-stu-id="7e12d-2266">Identification</span></span>
- <span data-ttu-id="7e12d-2267">Personalausweis</span><span class="sxs-lookup"><span data-stu-id="7e12d-2267">Personalausweis</span></span>
- <span data-ttu-id="7e12d-2268">Identifizierungsnummer</span><span class="sxs-lookup"><span data-stu-id="7e12d-2268">Identifizierungsnummer</span></span>
- <span data-ttu-id="7e12d-2269">Ausweis</span><span class="sxs-lookup"><span data-stu-id="7e12d-2269">Ausweis</span></span>
- <span data-ttu-id="7e12d-2270">Identifikation</span><span class="sxs-lookup"><span data-stu-id="7e12d-2270">Identifikation</span></span>
   
## <a name="greece-national-id-card"></a><span data-ttu-id="7e12d-2271">Carta d'identità (Grecia)</span><span class="sxs-lookup"><span data-stu-id="7e12d-2271">Greece National ID Card</span></span>

### <a name="format"></a><span data-ttu-id="7e12d-2272">Formato</span><span class="sxs-lookup"><span data-stu-id="7e12d-2272">Format</span></span>

<span data-ttu-id="7e12d-2273">Combinazione di 7-8 lettere e numeri, oltre a un trattino</span><span class="sxs-lookup"><span data-stu-id="7e12d-2273">Combination of 7-8 letters and numbers plus a dash</span></span>

### <a name="pattern"></a><span data-ttu-id="7e12d-2274">Modello</span><span class="sxs-lookup"><span data-stu-id="7e12d-2274">Pattern</span></span>

<span data-ttu-id="7e12d-2275">Sette lettere e numeri (formato precedente):</span><span class="sxs-lookup"><span data-stu-id="7e12d-2275">Seven letters and numbers (old format):</span></span>
- <span data-ttu-id="7e12d-2276">Una lettera (qualsiasi lettera dell'alfabeto greco) </span><span class="sxs-lookup"><span data-stu-id="7e12d-2276">One letter (any letter of the Greek alphabet)</span></span> 
- <span data-ttu-id="7e12d-2277">Un trattino</span><span class="sxs-lookup"><span data-stu-id="7e12d-2277">A dash</span></span> 
- <span data-ttu-id="7e12d-2278">Sei cifre</span><span class="sxs-lookup"><span data-stu-id="7e12d-2278">Six digits</span></span>

<span data-ttu-id="7e12d-2279">Otto lettere e numeri (nuovo formato):</span><span class="sxs-lookup"><span data-stu-id="7e12d-2279">Eight letters and numbers (new format):</span></span>
- <span data-ttu-id="7e12d-2280">Due lettere in maiuscolo sia in alfabeto latino che greco (ABEZHIKMNOPTYX) </span><span class="sxs-lookup"><span data-stu-id="7e12d-2280">Two letters whose uppercase character occurs in both the Greek and Latin alphabets (ABEZHIKMNOPTYX)</span></span> 
- <span data-ttu-id="7e12d-2281">Un trattino</span><span class="sxs-lookup"><span data-stu-id="7e12d-2281">A dash</span></span> 
- <span data-ttu-id="7e12d-2282">Sei cifre</span><span class="sxs-lookup"><span data-stu-id="7e12d-2282">Six digits</span></span>

### <a name="checksum"></a><span data-ttu-id="7e12d-2283">Checksum</span><span class="sxs-lookup"><span data-stu-id="7e12d-2283">Checksum</span></span>

<span data-ttu-id="7e12d-2284">No</span><span class="sxs-lookup"><span data-stu-id="7e12d-2284">No</span></span>

### <a name="definition"></a><span data-ttu-id="7e12d-2285">Definizione</span><span class="sxs-lookup"><span data-stu-id="7e12d-2285">Definition</span></span>

<span data-ttu-id="7e12d-2286">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="7e12d-2286">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="7e12d-2287">L'espressione regolare Regex_greece_id_card trova il contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="7e12d-2287">The regular expression Regex_greece_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="7e12d-2288">Viene trovata una parola chiave da Keyword_greece_id_card.</span><span class="sxs-lookup"><span data-stu-id="7e12d-2288">A keyword from Keyword_greece_id_card is found.</span></span>

```xml
<!-- Greece National ID Card -->
<Entity id="82568215-1da1-46d3-874a-d2294d81b5ac" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Regex_greece_id_card"/>
     <Match idRef="Keyword_greece_id_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="7e12d-2289">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="7e12d-2289">Keywords</span></span>

#### <a name="keyword_greece_id_card"></a><span data-ttu-id="7e12d-2290">Keyword_greece_id_card</span><span class="sxs-lookup"><span data-stu-id="7e12d-2290">Keyword_greece_id_card</span></span>

- <span data-ttu-id="7e12d-2291">Carta d’identità greca</span><span class="sxs-lookup"><span data-stu-id="7e12d-2291">Greek identity Card</span></span>
- <span data-ttu-id="7e12d-2292">Tautotita</span><span class="sxs-lookup"><span data-stu-id="7e12d-2292">Tautotita</span></span>
- <span data-ttu-id="7e12d-2293">Δελτίο αστυνομικής ταυτότητας</span><span class="sxs-lookup"><span data-stu-id="7e12d-2293">Δελτίο αστυνομικής ταυτότητας</span></span>
- <span data-ttu-id="7e12d-2294">Ταυτότητα</span><span class="sxs-lookup"><span data-stu-id="7e12d-2294">Ταυτότητα</span></span>
   
## <a name="hong-kong-identity-card-hkid-number"></a><span data-ttu-id="7e12d-2295">Hong Kong - Numero di carta di identità (HKID)</span><span class="sxs-lookup"><span data-stu-id="7e12d-2295">Hong Kong Identity Card (HKID) Number</span></span>

### <a name="format"></a><span data-ttu-id="7e12d-2296">Formato</span><span class="sxs-lookup"><span data-stu-id="7e12d-2296">Format</span></span>

<span data-ttu-id="7e12d-2297">Combinazione di 8-9 lettere e numeri. Facoltativamente, l’ultimo carattere può essere racchiuso tra parentesi</span><span class="sxs-lookup"><span data-stu-id="7e12d-2297">Combination of 8-9 letters and numbers plus optional parentheses around the final character</span></span>

### <a name="pattern"></a><span data-ttu-id="7e12d-2298">Modello</span><span class="sxs-lookup"><span data-stu-id="7e12d-2298">Pattern</span></span>

<span data-ttu-id="7e12d-2299">Combinazione di 8-9 lettere:</span><span class="sxs-lookup"><span data-stu-id="7e12d-2299">Combination of 8-9 letters:</span></span>
- <span data-ttu-id="7e12d-2300">1-2 lettere (senza distinzione tra maiuscole e minuscole)</span><span class="sxs-lookup"><span data-stu-id="7e12d-2300">1-2 letters (not case sensitive)</span></span> 
- <span data-ttu-id="7e12d-2301">Sei cifre</span><span class="sxs-lookup"><span data-stu-id="7e12d-2301">Six digits</span></span> 
- <span data-ttu-id="7e12d-2302">L'ultimo carattere (qualsiasi cifra o la lettera A), è rappresentato dal numero di controllo. Facoltativamente, può essere racchiuso tra parentesi.</span><span class="sxs-lookup"><span data-stu-id="7e12d-2302">The final character (any digit or the letter A), which is the check digit and is optionally enclosed in parentheses.</span></span>

### <a name="checksum"></a><span data-ttu-id="7e12d-2303">Checksum</span><span class="sxs-lookup"><span data-stu-id="7e12d-2303">Checksum</span></span>

<span data-ttu-id="7e12d-2304">Sì</span><span class="sxs-lookup"><span data-stu-id="7e12d-2304">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="7e12d-2305">Definizione</span><span class="sxs-lookup"><span data-stu-id="7e12d-2305">Definition</span></span>

<span data-ttu-id="7e12d-2306">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="7e12d-2306">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="7e12d-2307">La funzione Func_hong_kong_id_card trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="7e12d-2307">The function Func_hong_kong_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="7e12d-2308">Viene trovata una parola chiave da Keyword_hong_kong_id_card.</span><span class="sxs-lookup"><span data-stu-id="7e12d-2308">A keyword from Keyword_hong_kong_id_card is found.</span></span>
- <span data-ttu-id="7e12d-2309">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="7e12d-2309">The checksum passes.</span></span>

<span data-ttu-id="7e12d-2310">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 65%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="7e12d-2310">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="7e12d-2311">La funzione Func_hong_kong_id_card trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="7e12d-2311">The function Func_hong_kong_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="7e12d-2312">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="7e12d-2312">The checksum passes.</span></span>

```xml
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

### <a name="keywords"></a><span data-ttu-id="7e12d-2313">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="7e12d-2313">Keywords</span></span>

#### <a name="keyword_hong_kong_id_card"></a><span data-ttu-id="7e12d-2314">Keyword_hong_kong_id_card</span><span class="sxs-lookup"><span data-stu-id="7e12d-2314">Keyword_hong_kong_id_card</span></span>

- <span data-ttu-id="7e12d-2315">carta di identità di Hong Kong</span><span class="sxs-lookup"><span data-stu-id="7e12d-2315">hong kong identity card</span></span>
- <span data-ttu-id="7e12d-2316">HKIDC</span><span class="sxs-lookup"><span data-stu-id="7e12d-2316">HKIDC</span></span>
- <span data-ttu-id="7e12d-2317">id card</span><span class="sxs-lookup"><span data-stu-id="7e12d-2317">id card</span></span>
- <span data-ttu-id="7e12d-2318">carta di identità</span><span class="sxs-lookup"><span data-stu-id="7e12d-2318">identity card</span></span>
- <span data-ttu-id="7e12d-2319">carta di identità HK</span><span class="sxs-lookup"><span data-stu-id="7e12d-2319">hk identity card</span></span>
- <span data-ttu-id="7e12d-2320">ID Hong Kong</span><span class="sxs-lookup"><span data-stu-id="7e12d-2320">hong kong id</span></span>
- <span data-ttu-id="7e12d-2321">香港身份證</span><span class="sxs-lookup"><span data-stu-id="7e12d-2321">香港身份證</span></span>
- <span data-ttu-id="7e12d-2322">香港永久性居民身份證</span><span class="sxs-lookup"><span data-stu-id="7e12d-2322">香港永久性居民身份證</span></span>
- <span data-ttu-id="7e12d-2323">身份證</span><span class="sxs-lookup"><span data-stu-id="7e12d-2323">身份證</span></span>
- <span data-ttu-id="7e12d-2324">身份証</span><span class="sxs-lookup"><span data-stu-id="7e12d-2324">身份証</span></span>
- <span data-ttu-id="7e12d-2325">身分證</span><span class="sxs-lookup"><span data-stu-id="7e12d-2325">身分證</span></span>
- <span data-ttu-id="7e12d-2326">身分証</span><span class="sxs-lookup"><span data-stu-id="7e12d-2326">身分証</span></span>
- <span data-ttu-id="7e12d-2327">香港身份証</span><span class="sxs-lookup"><span data-stu-id="7e12d-2327">香港身份証</span></span>
- <span data-ttu-id="7e12d-2328">香港身分證</span><span class="sxs-lookup"><span data-stu-id="7e12d-2328">香港身分證</span></span>
- <span data-ttu-id="7e12d-2329">香港身分証</span><span class="sxs-lookup"><span data-stu-id="7e12d-2329">香港身分証</span></span>
- <span data-ttu-id="7e12d-2330">香港身份證</span><span class="sxs-lookup"><span data-stu-id="7e12d-2330">香港身份證</span></span>
- <span data-ttu-id="7e12d-2331">香港居民身份證</span><span class="sxs-lookup"><span data-stu-id="7e12d-2331">香港居民身份證</span></span>
- <span data-ttu-id="7e12d-2332">香港居民身份証</span><span class="sxs-lookup"><span data-stu-id="7e12d-2332">香港居民身份証</span></span>
- <span data-ttu-id="7e12d-2333">香港居民身分證</span><span class="sxs-lookup"><span data-stu-id="7e12d-2333">香港居民身分證</span></span>
- <span data-ttu-id="7e12d-2334">香港居民身分証</span><span class="sxs-lookup"><span data-stu-id="7e12d-2334">香港居民身分証</span></span>
- <span data-ttu-id="7e12d-2335">香港永久性居民身份証</span><span class="sxs-lookup"><span data-stu-id="7e12d-2335">香港永久性居民身份証</span></span>
- <span data-ttu-id="7e12d-2336">香港永久性居民身分證</span><span class="sxs-lookup"><span data-stu-id="7e12d-2336">香港永久性居民身分證</span></span>
- <span data-ttu-id="7e12d-2337">香港永久性居民身分証</span><span class="sxs-lookup"><span data-stu-id="7e12d-2337">香港永久性居民身分証</span></span>
- <span data-ttu-id="7e12d-2338">香港永久性居民身份證</span><span class="sxs-lookup"><span data-stu-id="7e12d-2338">香港永久性居民身份證</span></span>
- <span data-ttu-id="7e12d-2339">香港非永久性居民身份證</span><span class="sxs-lookup"><span data-stu-id="7e12d-2339">香港非永久性居民身份證</span></span>
- <span data-ttu-id="7e12d-2340">香港非永久性居民身份証</span><span class="sxs-lookup"><span data-stu-id="7e12d-2340">香港非永久性居民身份証</span></span>
- <span data-ttu-id="7e12d-2341">香港非永久性居民身分證</span><span class="sxs-lookup"><span data-stu-id="7e12d-2341">香港非永久性居民身分證</span></span>
- <span data-ttu-id="7e12d-2342">香港非永久性居民身分証</span><span class="sxs-lookup"><span data-stu-id="7e12d-2342">香港非永久性居民身分証</span></span>
- <span data-ttu-id="7e12d-2343">香港特別行政區永久性居民身份證</span><span class="sxs-lookup"><span data-stu-id="7e12d-2343">香港特別行政區永久性居民身份證</span></span>
- <span data-ttu-id="7e12d-2344">香港特別行政區永久性居民身份証</span><span class="sxs-lookup"><span data-stu-id="7e12d-2344">香港特別行政區永久性居民身份証</span></span>
- <span data-ttu-id="7e12d-2345">香港特別行政區永久性居民身分證</span><span class="sxs-lookup"><span data-stu-id="7e12d-2345">香港特別行政區永久性居民身分證</span></span>
- <span data-ttu-id="7e12d-2346">香港特別行政區永久性居民身分証</span><span class="sxs-lookup"><span data-stu-id="7e12d-2346">香港特別行政區永久性居民身分証</span></span>
- <span data-ttu-id="7e12d-2347">香港特別行政區非永久性居民身份證</span><span class="sxs-lookup"><span data-stu-id="7e12d-2347">香港特別行政區非永久性居民身份證</span></span>
- <span data-ttu-id="7e12d-2348">香港特別行政區非永久性居民身份証</span><span class="sxs-lookup"><span data-stu-id="7e12d-2348">香港特別行政區非永久性居民身份証</span></span>
- <span data-ttu-id="7e12d-2349">香港特別行政區非永久性居民身分證</span><span class="sxs-lookup"><span data-stu-id="7e12d-2349">香港特別行政區非永久性居民身分證</span></span>
- <span data-ttu-id="7e12d-2350">香港特別行政區非永久性居民身分証</span><span class="sxs-lookup"><span data-stu-id="7e12d-2350">香港特別行政區非永久性居民身分証</span></span>
   
## <a name="india-permanent-account-number-pan"></a><span data-ttu-id="7e12d-2351">India - Numero di conto permanente (PAN)</span><span class="sxs-lookup"><span data-stu-id="7e12d-2351">India Permanent Account Number (PAN)</span></span>

### <a name="format"></a><span data-ttu-id="7e12d-2352">Formato</span><span class="sxs-lookup"><span data-stu-id="7e12d-2352">Format</span></span>

<span data-ttu-id="7e12d-2353">10 lettere o cifre</span><span class="sxs-lookup"><span data-stu-id="7e12d-2353">10 letters or digits</span></span>

### <a name="pattern"></a><span data-ttu-id="7e12d-2354">Modello</span><span class="sxs-lookup"><span data-stu-id="7e12d-2354">Pattern</span></span>

<span data-ttu-id="7e12d-2355">10 lettere o cifre:</span><span class="sxs-lookup"><span data-stu-id="7e12d-2355">10 letters or digits:</span></span>
- <span data-ttu-id="7e12d-2356">Cinque lettere (senza distinzione tra maiuscole e minuscole)</span><span class="sxs-lookup"><span data-stu-id="7e12d-2356">Five letters (not case sensitive)</span></span> 
- <span data-ttu-id="7e12d-2357">Quattro cifre</span><span class="sxs-lookup"><span data-stu-id="7e12d-2357">Four digits</span></span> 
- <span data-ttu-id="7e12d-2358">Una lettera, ovvero una cifra di controllo alfabetica</span><span class="sxs-lookup"><span data-stu-id="7e12d-2358">A letter which is an alphabetic check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="7e12d-2359">Checksum</span><span class="sxs-lookup"><span data-stu-id="7e12d-2359">Checksum</span></span>

<span data-ttu-id="7e12d-2360">Sì</span><span class="sxs-lookup"><span data-stu-id="7e12d-2360">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="7e12d-2361">Definizione</span><span class="sxs-lookup"><span data-stu-id="7e12d-2361">Definition</span></span>

<span data-ttu-id="7e12d-2362">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="7e12d-2362">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="7e12d-2363">L'espressione regolare Regex_india_permanent_account_number trova il contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="7e12d-2363">The regular expression Regex_india_permanent_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="7e12d-2364">Viene trovata una parola chiave da Keyword_india_permanent_account_number.</span><span class="sxs-lookup"><span data-stu-id="7e12d-2364">A keyword from Keyword_india_permanent_account_number is found.</span></span>
- <span data-ttu-id="7e12d-2365">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="7e12d-2365">The checksum passes.</span></span>

```xml
<!-- India Permanent Account Number -->
<Entity id="2602bfee-9bb0-47a5-a7a6-2bf3053e2804" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Regex_india_permanent_account_number"/>
     <Match idRef="Keyword_india_permanent_account_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="7e12d-2366">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="7e12d-2366">Keywords</span></span>

#### <a name="keyword_india_permanent_account_number"></a><span data-ttu-id="7e12d-2367">Keyword_india_permanent_account_number</span><span class="sxs-lookup"><span data-stu-id="7e12d-2367">Keyword_india_permanent_account_number</span></span>

- <span data-ttu-id="7e12d-2368">Permanent Account Number</span><span class="sxs-lookup"><span data-stu-id="7e12d-2368">Permanent Account Number</span></span> 
- <span data-ttu-id="7e12d-2369">PAN</span><span class="sxs-lookup"><span data-stu-id="7e12d-2369">PAN</span></span> 
   
## <a name="india-unique-identification-aadhaar-number"></a><span data-ttu-id="7e12d-2370">India - Numero di identificazione univoco (Aadhaar)</span><span class="sxs-lookup"><span data-stu-id="7e12d-2370">India Unique Identification (Aadhaar) Number</span></span>

### <a name="format"></a><span data-ttu-id="7e12d-2371">Formato</span><span class="sxs-lookup"><span data-stu-id="7e12d-2371">Format</span></span>

<span data-ttu-id="7e12d-2372">12 cifre contenenti spazi o trattini facoltativi </span><span class="sxs-lookup"><span data-stu-id="7e12d-2372">12 digits containing optional spaces or dashes</span></span>

### <a name="pattern"></a><span data-ttu-id="7e12d-2373">Modello</span><span class="sxs-lookup"><span data-stu-id="7e12d-2373">Pattern</span></span>

<span data-ttu-id="7e12d-2374">12 cifre:</span><span class="sxs-lookup"><span data-stu-id="7e12d-2374">12 digits:</span></span>
- <span data-ttu-id="7e12d-2375">Quattro cifre</span><span class="sxs-lookup"><span data-stu-id="7e12d-2375">Four digits</span></span> 
- <span data-ttu-id="7e12d-2376">Uno spazio o un trattino facoltativo </span><span class="sxs-lookup"><span data-stu-id="7e12d-2376">An optional space or dash</span></span> 
- <span data-ttu-id="7e12d-2377">Quattro cifre</span><span class="sxs-lookup"><span data-stu-id="7e12d-2377">Four digits</span></span> 
- <span data-ttu-id="7e12d-2378">Uno spazio o un trattino facoltativo </span><span class="sxs-lookup"><span data-stu-id="7e12d-2378">An optional space or dash</span></span> 
- <span data-ttu-id="7e12d-2379">L'ultimo carattere, ovvero il numero di controllo</span><span class="sxs-lookup"><span data-stu-id="7e12d-2379">The final digit which is the check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="7e12d-2380">Checksum</span><span class="sxs-lookup"><span data-stu-id="7e12d-2380">Checksum</span></span>

<span data-ttu-id="7e12d-2381">Sì</span><span class="sxs-lookup"><span data-stu-id="7e12d-2381">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="7e12d-2382">Definizione</span><span class="sxs-lookup"><span data-stu-id="7e12d-2382">Definition</span></span>

<span data-ttu-id="7e12d-2383">Un criterio DLP è 85% fiducioso di aver rilevato questo tipo di informazioni riservate se, entro 300 caratteri: la funzione Func_india_aadhaar trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="7e12d-2383">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The function Func_india_aadhaar finds content that matches the pattern.</span></span>
<span data-ttu-id="7e12d-2384">Viene trovata una parola chiave da Keyword_india_aadhar.</span><span class="sxs-lookup"><span data-stu-id="7e12d-2384">A keyword from Keyword_india_aadhar is found.</span></span>
<span data-ttu-id="7e12d-2385">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="7e12d-2385">The checksum passes.</span></span>
<span data-ttu-id="7e12d-2386">Un criterio DLP è 75% fiducioso di aver rilevato questo tipo di informazioni riservate se, entro 300 caratteri: la funzione Func_india_aadhaar trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="7e12d-2386">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The function Func_india_aadhaar finds content that matches the pattern.</span></span>
<span data-ttu-id="7e12d-2387">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="7e12d-2387">The checksum passes.</span></span>
```xml
<!-- India Unique Identification (Aadhaar) number -->
<Entity id="1ca46b29-76f5-4f46-9383-cfa15e91048f" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_india_aadhaar"/>
     <Match idRef="Keyword_india_aadhar"/>
  </Pattern>
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_india_aadhaar"/>
  </Pattern>
</Entity>

### Keywords
   
#### Keyword_india_aadhar
- Aadhar
- Aadhaar
- UID
- आधार
   
## Indonesia Identity Card (KTP) Number

### Format

16 digits containing optional periods

### Pattern

16 digits:
- Two-digit province code 
- A period (optional) 
- Two-digit regency or city code 
- Two-digit subdistrict code 
- A period (optional) 
- Six digits in the format DDMMYY which are the date of birth 
- A period (optional) 
- Four digits

### Checksum

No

### Definition

A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:
- The regular expression Regex_indonesia_id_card finds content that matches the pattern.
- A keyword from Keyword_indonesia_id_card is found.

A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:
- The regular expression Regex_indonesia_id_card finds content that matches the pattern.

```
<!-- Indonesia Identity Card (KTP) Number -->
<span data-ttu-id="7e12d-2388"><Entity id="da68fdb0-f383-4981-8c86-82689d3b7d55" recommendedConfidence="85" patternsProximity="300"> <Pattern confidenceLevel="85"> <IdMatch idRef="Regex_indonesia_id_card"/> <Match idRef="Keyword_indonesia_id_card"/> </Pattern> <Pattern confidenceLevel="75"> <IdMatch idRef="Regex_indonesia_id_card"/> </Pattern>
</Entity></span><span class="sxs-lookup"><span data-stu-id="7e12d-2388"></span></span>
```

### Keywords
   
#### Keyword_indonesia_id_card

- KTP
- Kartu Tanda Penduduk 
- Nomor Induk Kependudukan 
   
## International Banking Account Number (IBAN)

### Format

Country code (two letters) plus check digits (two digits) plus bban number (up to 30 characters)

### Pattern

Pattern must include all of the following:

- Two-letter country code
- Two check digits (followed by an optional space) 
- 1-7 groups of four letters or digits (can be separated by spaces)
- 1-3 letters or digits

The format for each country is slightly different. The IBAN sensitive information type covers these 60 countries:

ad, ae, al, at, az, ba, be, bg, bh, ch, cr, cy, cz, de, dk, do, ee, es, fi, fo, fr, gb, ge, gi, gl, gr, hr, hu, ie, il, is, it, kw, kz, lb, li, lt, lu, lv, mc, md, me, mk, mr, mt, mu, nl, no, pl, pt, ro, rs, sa, se, si, sk, sm, tn, tr, vg

### Checksum

Yes

### Definition

A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:
- The function Func_iban finds content that matches the pattern.
- The checksum passes.

```xml
<Entity id="e7dc4711-11b7-4cb0-b88b-2c394a771f0e" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_iban" />
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="7e12d-2389">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="7e12d-2389">Keywords</span></span>

<span data-ttu-id="7e12d-2390">Nessuno</span><span class="sxs-lookup"><span data-stu-id="7e12d-2390">None</span></span>

   
## <a name="ip-address"></a><span data-ttu-id="7e12d-2391">Indirizzo IP</span><span class="sxs-lookup"><span data-stu-id="7e12d-2391">IP Address</span></span>

### <a name="format"></a><span data-ttu-id="7e12d-2392">Formato</span><span class="sxs-lookup"><span data-stu-id="7e12d-2392">Format</span></span>

#### <a name="ipv4"></a><span data-ttu-id="7e12d-2393">IPv4</span><span class="sxs-lookup"><span data-stu-id="7e12d-2393">IPv4:</span></span>
<span data-ttu-id="7e12d-2394">Modello complesso che rappresenta le versioni formattate (punti) e quelle non formattate (senza punti) degli indirizzi IPv4</span><span class="sxs-lookup"><span data-stu-id="7e12d-2394">Complex pattern which accounts for formatted (periods) and unformatted (no periods) versions of the IPv4 addresses</span></span>

#### <a name="ipv6"></a><span data-ttu-id="7e12d-2395">IPv6</span><span class="sxs-lookup"><span data-stu-id="7e12d-2395">IPv6:</span></span>
<span data-ttu-id="7e12d-2396">Modello complesso che rappresenta i numeri dell'indirizzo IPv6 non formattati (include i due punti)</span><span class="sxs-lookup"><span data-stu-id="7e12d-2396">Complex pattern which accounts for formatted IPv6 numbers (which include colons)</span></span>

### <a name="pattern"></a><span data-ttu-id="7e12d-2397">Modello</span><span class="sxs-lookup"><span data-stu-id="7e12d-2397">Pattern</span></span>

### <a name="checksum"></a><span data-ttu-id="7e12d-2398">Checksum</span><span class="sxs-lookup"><span data-stu-id="7e12d-2398">Checksum</span></span>

<span data-ttu-id="7e12d-2399">No</span><span class="sxs-lookup"><span data-stu-id="7e12d-2399">No</span></span>

### <a name="definition"></a><span data-ttu-id="7e12d-2400">Definizione</span><span class="sxs-lookup"><span data-stu-id="7e12d-2400">Definition</span></span>

<span data-ttu-id="7e12d-2401">Nel caso di IPv6, un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="7e12d-2401">For IPv6, a DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="7e12d-2402">L'espressione regolare Regex_ipv6_address restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="7e12d-2402">The regular expression Regex_ipv6_address finds content that matches the pattern.</span></span>
- <span data-ttu-id="7e12d-2403">Non vengono trovate parole chiave da Keyword_ipaddress.</span><span class="sxs-lookup"><span data-stu-id="7e12d-2403">No keyword from Keyword_ipaddress is found.</span></span>

<span data-ttu-id="7e12d-2404">Nel caso di IPv4, un criterio DLP rileva questo tipo di informazioni con una probabilità del 95%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="7e12d-2404">For IPv4, a DLP policy is 95% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="7e12d-2405">L'espressione regolare Regex_ipv4_address restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="7e12d-2405">The regular expression Regex_ipv4_address finds content that matches the pattern.</span></span>
- <span data-ttu-id="7e12d-2406">Viene trovata una parola chiave da Keyword_ipaddress.</span><span class="sxs-lookup"><span data-stu-id="7e12d-2406">A keyword from Keyword_ipaddress is found.</span></span>

<span data-ttu-id="7e12d-2407">Nel caso di IPv6, un criterio DLP rileva questo tipo di informazioni con una probabilità del 95%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="7e12d-2407">For IPv6, a DLP policy is 95% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="7e12d-2408">L'espressione regolare Regex_ipv6_address restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="7e12d-2408">The regular expression Regex_ipv6_address finds content that matches the pattern.</span></span>
- <span data-ttu-id="7e12d-2409">Non vengono trovate parole chiave da Keyword_ipaddress.</span><span class="sxs-lookup"><span data-stu-id="7e12d-2409">No keyword from Keyword_ipaddress is found.</span></span>

```xml
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

### <a name="keywords"></a><span data-ttu-id="7e12d-2410">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="7e12d-2410">Keywords</span></span>

#### <a name="keyword_ipaddress"></a><span data-ttu-id="7e12d-2411">Keyword_ipaddress</span><span class="sxs-lookup"><span data-stu-id="7e12d-2411">Keyword_ipaddress</span></span>

- <span data-ttu-id="7e12d-2412">IP (per questa parola chiave viene fatta distinzione tra maiuscole e minuscole)</span><span class="sxs-lookup"><span data-stu-id="7e12d-2412">IP (this keyword is case sensitive)</span></span>
- <span data-ttu-id="7e12d-2413">ip address</span><span class="sxs-lookup"><span data-stu-id="7e12d-2413">ip address</span></span> 
- <span data-ttu-id="7e12d-2414">Indirizzi IP</span><span class="sxs-lookup"><span data-stu-id="7e12d-2414">ip addresses</span></span>
- <span data-ttu-id="7e12d-2415">internet protocol</span><span class="sxs-lookup"><span data-stu-id="7e12d-2415">internet protocol</span></span>
- <span data-ttu-id="7e12d-2416">IP-כתובת ה</span><span class="sxs-lookup"><span data-stu-id="7e12d-2416">IP-כתובת ה</span></span> 
   
## <a name="international-classification-of-diseases-icd-10-cm"></a><span data-ttu-id="7e12d-2417">Classificazione internazionale delle malattie (ICD-10-CM)</span><span class="sxs-lookup"><span data-stu-id="7e12d-2417">International Classification of Diseases (ICD-10-CM)</span></span>

### <a name="format"></a><span data-ttu-id="7e12d-2418">Formato</span><span class="sxs-lookup"><span data-stu-id="7e12d-2418">Format</span></span>

<span data-ttu-id="7e12d-2419">Dizionario</span><span class="sxs-lookup"><span data-stu-id="7e12d-2419">Dictionary</span></span>

### <a name="pattern"></a><span data-ttu-id="7e12d-2420">Modello</span><span class="sxs-lookup"><span data-stu-id="7e12d-2420">Pattern</span></span>

<span data-ttu-id="7e12d-2421">Parola chiave</span><span class="sxs-lookup"><span data-stu-id="7e12d-2421">Keyword</span></span>

### <a name="checksum"></a><span data-ttu-id="7e12d-2422">Checksum</span><span class="sxs-lookup"><span data-stu-id="7e12d-2422">Checksum</span></span>

<span data-ttu-id="7e12d-2423">No</span><span class="sxs-lookup"><span data-stu-id="7e12d-2423">No</span></span>

### <a name="definition"></a><span data-ttu-id="7e12d-2424">Definizione</span><span class="sxs-lookup"><span data-stu-id="7e12d-2424">Definition</span></span>

<span data-ttu-id="7e12d-2425">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="7e12d-2425">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="7e12d-2426">Viene trovata una parola chiave da Dictionary_icd_10_cm.</span><span class="sxs-lookup"><span data-stu-id="7e12d-2426">A keyword from Dictionary_icd_10_cm is found.</span></span>

```xml
      <!-- ICD-10 CM -->
      <Entity id="3356946c-6bb7-449b-b253-6ffa419c0ce7" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Dictionary_icd_10_cm" />
        </Pattern>
      </Entity>
```

<span data-ttu-id="7e12d-2427">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="7e12d-2427">Keywords</span></span>

<span data-ttu-id="7e12d-2428">Qualsiasi termine del dizionario di parole chiave Dictionary_icd_10_cm, basato sulla [classificazione internazionale delle malattie, la decima revisione, la modifica clinica (ICD-10-cm)](https://go.microsoft.com/fwlink/?linkid=852604).</span><span class="sxs-lookup"><span data-stu-id="7e12d-2428">Any term from the Dictionary_icd_10_cm keyword dictionary, which is based on the [International Classification of Diseases, Tenth Revision, Clinical Modification (ICD-10-CM)](https://go.microsoft.com/fwlink/?linkid=852604).</span></span> <span data-ttu-id="7e12d-2429">Questo tipo di ricerca viene visualizzato solo per il termine, non per i codici assicurativi.</span><span class="sxs-lookup"><span data-stu-id="7e12d-2429">This type looks only for the term, not the insurance codes.</span></span>

   
## <a name="international-classification-of-diseases-icd-9-cm"></a><span data-ttu-id="7e12d-2430">Classificazione internazionale delle malattie (ICD-9-CM)</span><span class="sxs-lookup"><span data-stu-id="7e12d-2430">International Classification of Diseases (ICD-9-CM)</span></span>

### <a name="format"></a><span data-ttu-id="7e12d-2431">Formato</span><span class="sxs-lookup"><span data-stu-id="7e12d-2431">Format</span></span>

<span data-ttu-id="7e12d-2432">Dizionario</span><span class="sxs-lookup"><span data-stu-id="7e12d-2432">Dictionary</span></span>

### <a name="pattern"></a><span data-ttu-id="7e12d-2433">Modello</span><span class="sxs-lookup"><span data-stu-id="7e12d-2433">Pattern</span></span>

<span data-ttu-id="7e12d-2434">Parola chiave</span><span class="sxs-lookup"><span data-stu-id="7e12d-2434">Keyword</span></span>

### <a name="checksum"></a><span data-ttu-id="7e12d-2435">Checksum</span><span class="sxs-lookup"><span data-stu-id="7e12d-2435">Checksum</span></span>

<span data-ttu-id="7e12d-2436">No</span><span class="sxs-lookup"><span data-stu-id="7e12d-2436">No</span></span>

### <a name="definition"></a><span data-ttu-id="7e12d-2437">Definizione</span><span class="sxs-lookup"><span data-stu-id="7e12d-2437">Definition</span></span>

<span data-ttu-id="7e12d-2438">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="7e12d-2438">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="7e12d-2439">Viene trovata una parola chiave da Dictionary_icd_9_cm.</span><span class="sxs-lookup"><span data-stu-id="7e12d-2439">A keyword from Dictionary_icd_9_cm is found.</span></span>

```xml
      <Entity id="fa3f9c74-ee07-4c52-b5f2-085d6b2c0ec4" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Dictionary_icd_9_cm" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a><span data-ttu-id="7e12d-2440">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="7e12d-2440">Keywords</span></span>

<span data-ttu-id="7e12d-2441">Qualsiasi termine del dizionario di parole chiave Dictionary_icd_9_cm, basato sulla [classificazione internazionale delle malattie, la nona revisione, la modifica clinica (ICD-9-cm)](https://go.microsoft.com/fwlink/?linkid=852605).</span><span class="sxs-lookup"><span data-stu-id="7e12d-2441">Any term from the Dictionary_icd_9_cm keyword dictionary, which is based on the [International Classification of Diseases,Ninth Revision, Clinical Modification (ICD-9-CM)](https://go.microsoft.com/fwlink/?linkid=852605).</span></span> <span data-ttu-id="7e12d-2442">Questo tipo di ricerca viene visualizzato solo per il termine, non per i codici assicurativi.</span><span class="sxs-lookup"><span data-stu-id="7e12d-2442">This type looks only for the term, not the insurance codes.</span></span>
   
## <a name="ireland-personal-public-service-pps-number"></a><span data-ttu-id="7e12d-2443">Irlanda - Numero personale di servizio pubblico (PPS)</span><span class="sxs-lookup"><span data-stu-id="7e12d-2443">Ireland Personal Public Service (PPS) Number</span></span>

### <a name="format"></a><span data-ttu-id="7e12d-2444">Formato</span><span class="sxs-lookup"><span data-stu-id="7e12d-2444">Format</span></span>

<span data-ttu-id="7e12d-2445">Formato precedente (fino al 31 dicembre 2012):</span><span class="sxs-lookup"><span data-stu-id="7e12d-2445">Old format (until 31 Dec 2012):</span></span>
- <span data-ttu-id="7e12d-2446">Sette cifre seguite da 1-2 lettere </span><span class="sxs-lookup"><span data-stu-id="7e12d-2446">Seven digits followed by 1-2 letters</span></span> 

<span data-ttu-id="7e12d-2447">Nuovo formato (1 gen 2013 e successive):</span><span class="sxs-lookup"><span data-stu-id="7e12d-2447">New format (1 Jan 2013 and after):</span></span>
- <span data-ttu-id="7e12d-2448">Sette cifre seguite da due lettere</span><span class="sxs-lookup"><span data-stu-id="7e12d-2448">Seven digits followed by two letters</span></span>

### <a name="pattern"></a><span data-ttu-id="7e12d-2449">Modello</span><span class="sxs-lookup"><span data-stu-id="7e12d-2449">Pattern</span></span>

<span data-ttu-id="7e12d-2450">Formato precedente (fino al 31 dicembre 2012):</span><span class="sxs-lookup"><span data-stu-id="7e12d-2450">Old format (until 31 Dec 2012):</span></span>
- <span data-ttu-id="7e12d-2451">Sette cifre</span><span class="sxs-lookup"><span data-stu-id="7e12d-2451">Seven digits</span></span> 
- <span data-ttu-id="7e12d-2452">1-2 lettere (senza distinzione tra maiuscole e minuscole)</span><span class="sxs-lookup"><span data-stu-id="7e12d-2452">1-2 letters (not case sensitive)</span></span> 

<span data-ttu-id="7e12d-2453">Nuovo formato (1 gen 2013 e successive):</span><span class="sxs-lookup"><span data-stu-id="7e12d-2453">New format (1 Jan 2013 and after):</span></span>
- <span data-ttu-id="7e12d-2454">Sette cifre</span><span class="sxs-lookup"><span data-stu-id="7e12d-2454">Seven digits</span></span> 
- <span data-ttu-id="7e12d-2455">Una lettera (senza distinzione tra maiuscole e minuscole) che corrisponde a una cifra di controllo alfabetica </span><span class="sxs-lookup"><span data-stu-id="7e12d-2455">A letter (not case sensitive) which is an alphabetic check digit</span></span> 
- <span data-ttu-id="7e12d-2456">La lettera "A" o "H" (senza distinzione tra maiuscole e minuscole)</span><span class="sxs-lookup"><span data-stu-id="7e12d-2456">The letter "A" or "H" (not case sensitive)</span></span>

### <a name="checksum"></a><span data-ttu-id="7e12d-2457">Checksum</span><span class="sxs-lookup"><span data-stu-id="7e12d-2457">Checksum</span></span>

<span data-ttu-id="7e12d-2458">Sì</span><span class="sxs-lookup"><span data-stu-id="7e12d-2458">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="7e12d-2459">Definizione</span><span class="sxs-lookup"><span data-stu-id="7e12d-2459">Definition</span></span>

<span data-ttu-id="7e12d-2460">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="7e12d-2460">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="7e12d-2461">La funzione Func_ireland_pps trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="7e12d-2461">The function Func_ireland_pps finds content that matches the pattern.</span></span>
- <span data-ttu-id="7e12d-2462">Si verifica una delle situazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="7e12d-2462">One of the following is true:</span></span>
    - <span data-ttu-id="7e12d-2463">Viene trovata una parola chiave da Keyword_ireland_pps.</span><span class="sxs-lookup"><span data-stu-id="7e12d-2463">A keyword from Keyword_ireland_pps is found.</span></span>
    - <span data-ttu-id="7e12d-2464">La funzione Func_eu_date rileva una data nel formato corretto.</span><span class="sxs-lookup"><span data-stu-id="7e12d-2464">The function Func_eu_date finds a date in the right date format.</span></span>
- <span data-ttu-id="7e12d-2465">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="7e12d-2465">The checksum passes.</span></span>

<span data-ttu-id="7e12d-2466">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 65%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="7e12d-2466">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="7e12d-2467">La funzione Func_ireland_pps trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="7e12d-2467">The function Func_ireland_pps finds content that matches the pattern.</span></span>
- <span data-ttu-id="7e12d-2468">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="7e12d-2468">The checksum passes.</span></span>

```xml
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

### <a name="keywords"></a><span data-ttu-id="7e12d-2469">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="7e12d-2469">Keywords</span></span>

#### <a name="keyword_ireland_pps"></a><span data-ttu-id="7e12d-2470">Keyword_ireland_pps</span><span class="sxs-lookup"><span data-stu-id="7e12d-2470">Keyword_ireland_pps</span></span>

- <span data-ttu-id="7e12d-2471">Numero personale di servizio pubblico</span><span class="sxs-lookup"><span data-stu-id="7e12d-2471">Personal Public Service Number</span></span> 
- <span data-ttu-id="7e12d-2472">Numero PPS</span><span class="sxs-lookup"><span data-stu-id="7e12d-2472">PPS Number</span></span> 
- <span data-ttu-id="7e12d-2473">Num. PPS
</span><span class="sxs-lookup"><span data-stu-id="7e12d-2473">PPS Num</span></span> 
- <span data-ttu-id="7e12d-2474">N° PPS</span><span class="sxs-lookup"><span data-stu-id="7e12d-2474">PPS No.</span></span> 
- <span data-ttu-id="7e12d-2475">PPS #</span><span class="sxs-lookup"><span data-stu-id="7e12d-2475">PPS #</span></span> 
- <span data-ttu-id="7e12d-2476">PPS #</span><span class="sxs-lookup"><span data-stu-id="7e12d-2476">PPS#</span></span> 
- <span data-ttu-id="7e12d-2477">PPSN</span><span class="sxs-lookup"><span data-stu-id="7e12d-2477">PPSN</span></span> 
- <span data-ttu-id="7e12d-2478">Scheda servizi pubblici</span><span class="sxs-lookup"><span data-stu-id="7e12d-2478">Public Services Card</span></span> 
- <span data-ttu-id="7e12d-2479">Uimhir Phearsanta Seirbhíse Poiblí</span><span class="sxs-lookup"><span data-stu-id="7e12d-2479">Uimhir Phearsanta Seirbhíse Poiblí</span></span> 
- <span data-ttu-id="7e12d-2480">Uimh.</span><span class="sxs-lookup"><span data-stu-id="7e12d-2480">Uimh.</span></span> <span data-ttu-id="7e12d-2481">PSP</span><span class="sxs-lookup"><span data-stu-id="7e12d-2481">PSP</span></span> 
- <span data-ttu-id="7e12d-2482">PSP</span><span class="sxs-lookup"><span data-stu-id="7e12d-2482">PSP</span></span> 
   
## <a name="israel-bank-account-number"></a><span data-ttu-id="7e12d-2483">Israele - Numero di conto bancario</span><span class="sxs-lookup"><span data-stu-id="7e12d-2483">Israel Bank Account Number</span></span>

### <a name="format"></a><span data-ttu-id="7e12d-2484">Formato</span><span class="sxs-lookup"><span data-stu-id="7e12d-2484">Format</span></span>

<span data-ttu-id="7e12d-2485">13 cifre</span><span class="sxs-lookup"><span data-stu-id="7e12d-2485">13 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="7e12d-2486">Modello</span><span class="sxs-lookup"><span data-stu-id="7e12d-2486">Pattern</span></span>

<span data-ttu-id="7e12d-2487">Formattato</span><span class="sxs-lookup"><span data-stu-id="7e12d-2487">Formatted:</span></span>
- <span data-ttu-id="7e12d-2488">Due cifre</span><span class="sxs-lookup"><span data-stu-id="7e12d-2488">Two digits</span></span> 
- <span data-ttu-id="7e12d-2489">Un trattino</span><span class="sxs-lookup"><span data-stu-id="7e12d-2489">A dash</span></span> 
- <span data-ttu-id="7e12d-2490">Tre cifre</span><span class="sxs-lookup"><span data-stu-id="7e12d-2490">Three digits</span></span> 
- <span data-ttu-id="7e12d-2491">Un trattino</span><span class="sxs-lookup"><span data-stu-id="7e12d-2491">A dash</span></span> 
- <span data-ttu-id="7e12d-2492">Otto cifre</span><span class="sxs-lookup"><span data-stu-id="7e12d-2492">Eight digits</span></span>

<span data-ttu-id="7e12d-2493">Formattato</span><span class="sxs-lookup"><span data-stu-id="7e12d-2493">Unformatted:</span></span>
- <span data-ttu-id="7e12d-2494">13 cifre consecutive</span><span class="sxs-lookup"><span data-stu-id="7e12d-2494">13 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="7e12d-2495">Checksum</span><span class="sxs-lookup"><span data-stu-id="7e12d-2495">Checksum</span></span>

<span data-ttu-id="7e12d-2496">No</span><span class="sxs-lookup"><span data-stu-id="7e12d-2496">No</span></span>

### <a name="definition"></a><span data-ttu-id="7e12d-2497">Definizione</span><span class="sxs-lookup"><span data-stu-id="7e12d-2497">Definition</span></span>

<span data-ttu-id="7e12d-2498">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="7e12d-2498">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="7e12d-2499">L'espressione regolare Regex_israel_bank_account_number restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="7e12d-2499">The regular expression Regex_israel_bank_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="7e12d-2500">Viene trovata una parola chiave da Keyword_israel_bank_account_number.</span><span class="sxs-lookup"><span data-stu-id="7e12d-2500">A keyword from Keyword_israel_bank_account_number is found.</span></span>

```xml
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

### <a name="keywords"></a><span data-ttu-id="7e12d-2501">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="7e12d-2501">Keywords</span></span>

#### <a name="keyword_israel_bank_account_number"></a><span data-ttu-id="7e12d-2502">Keyword_israel_bank_account_number</span><span class="sxs-lookup"><span data-stu-id="7e12d-2502">Keyword_israel_bank_account_number</span></span>

- <span data-ttu-id="7e12d-2503">Bank Account Number</span><span class="sxs-lookup"><span data-stu-id="7e12d-2503">Bank Account Number</span></span> 
- <span data-ttu-id="7e12d-2504">Bank Account</span><span class="sxs-lookup"><span data-stu-id="7e12d-2504">Bank Account</span></span> 
- <span data-ttu-id="7e12d-2505">Account Number</span><span class="sxs-lookup"><span data-stu-id="7e12d-2505">Account Number</span></span> 
- <span data-ttu-id="7e12d-2506">מספר חשבון בנק</span><span class="sxs-lookup"><span data-stu-id="7e12d-2506">מספר חשבון בנק</span></span> 
   
## <a name="israel-national-id"></a><span data-ttu-id="7e12d-2507">Carta di identità (Israele)</span><span class="sxs-lookup"><span data-stu-id="7e12d-2507">Israel National ID</span></span>

### <a name="format"></a><span data-ttu-id="7e12d-2508">Formato</span><span class="sxs-lookup"><span data-stu-id="7e12d-2508">Format</span></span>

<span data-ttu-id="7e12d-2509">9 cifre</span><span class="sxs-lookup"><span data-stu-id="7e12d-2509">Nine digits</span></span>

### <a name="pattern"></a><span data-ttu-id="7e12d-2510">Modello</span><span class="sxs-lookup"><span data-stu-id="7e12d-2510">Pattern</span></span>

<span data-ttu-id="7e12d-2511">9 cifre consecutive</span><span class="sxs-lookup"><span data-stu-id="7e12d-2511">Nine consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="7e12d-2512">Checksum</span><span class="sxs-lookup"><span data-stu-id="7e12d-2512">Checksum</span></span>

<span data-ttu-id="7e12d-2513">Sì</span><span class="sxs-lookup"><span data-stu-id="7e12d-2513">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="7e12d-2514">Definizione</span><span class="sxs-lookup"><span data-stu-id="7e12d-2514">Definition</span></span>

<span data-ttu-id="7e12d-2515">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="7e12d-2515">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="7e12d-2516">La funzione Func_israeli_national_id_number restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="7e12d-2516">The function Func_israeli_national_id_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="7e12d-2517">Viene trovata una parola chiave da Keyword_Israel_National_ID.</span><span class="sxs-lookup"><span data-stu-id="7e12d-2517">A keyword from Keyword_Israel_National_ID is found.</span></span>
- <span data-ttu-id="7e12d-2518">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="7e12d-2518">The checksum passes.</span></span>

```xml
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

### <a name="keywords"></a><span data-ttu-id="7e12d-2519">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="7e12d-2519">Keywords</span></span>

#### <a name="keyword_israel_national_id"></a><span data-ttu-id="7e12d-2520">Keyword_Israel_National_ID</span><span class="sxs-lookup"><span data-stu-id="7e12d-2520">Keyword_Israel_National_ID</span></span>

- <span data-ttu-id="7e12d-2521">מספר זהות</span><span class="sxs-lookup"><span data-stu-id="7e12d-2521">מספר זהות</span></span> 
- <span data-ttu-id="7e12d-2522">National ID Number</span><span class="sxs-lookup"><span data-stu-id="7e12d-2522">National ID Number</span></span>
   
## <a name="italy-drivers-license-number"></a><span data-ttu-id="7e12d-2523">Italia - Numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="7e12d-2523">Italy Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="7e12d-2524">Formato</span><span class="sxs-lookup"><span data-stu-id="7e12d-2524">Format</span></span>

<span data-ttu-id="7e12d-2525">Una combinazione di 10 lettere e cifre</span><span class="sxs-lookup"><span data-stu-id="7e12d-2525">A combination of 10 letters and digits</span></span>

### <a name="pattern"></a><span data-ttu-id="7e12d-2526">Modello</span><span class="sxs-lookup"><span data-stu-id="7e12d-2526">Pattern</span></span>

- <span data-ttu-id="7e12d-2527">Una combinazione di 10 lettere e cifre:</span><span class="sxs-lookup"><span data-stu-id="7e12d-2527">A combination of 10 letters and digits:</span></span>
- <span data-ttu-id="7e12d-2528">Una lettera (senza distinzione tra maiuscole/minuscole)</span><span class="sxs-lookup"><span data-stu-id="7e12d-2528">One letter (not case sensitive)</span></span> 
- <span data-ttu-id="7e12d-2529">La lettera "A" o "V" (senza distinzione tra maiuscole/minuscole)</span><span class="sxs-lookup"><span data-stu-id="7e12d-2529">The letter "A" or "V" (not case sensitive)</span></span> 
- <span data-ttu-id="7e12d-2530">7 lettere (senza distinzione tra maiuscole/minuscole), cifre o carattere di sottolineatura</span><span class="sxs-lookup"><span data-stu-id="7e12d-2530">Seven letters (not case sensitive), digits, or the underscore character</span></span> 
- <span data-ttu-id="7e12d-2531">Una lettera (senza distinzione tra maiuscole/minuscole)</span><span class="sxs-lookup"><span data-stu-id="7e12d-2531">One letter (not case sensitive)</span></span>

### <a name="checksum"></a><span data-ttu-id="7e12d-2532">Checksum</span><span class="sxs-lookup"><span data-stu-id="7e12d-2532">Checksum</span></span>

<span data-ttu-id="7e12d-2533">No</span><span class="sxs-lookup"><span data-stu-id="7e12d-2533">No</span></span>

### <a name="definition"></a><span data-ttu-id="7e12d-2534">Definizione</span><span class="sxs-lookup"><span data-stu-id="7e12d-2534">Definition</span></span>

<span data-ttu-id="7e12d-2535">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="7e12d-2535">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="7e12d-2536">L'espressione regolare Regex_italy_drivers_license_number restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="7e12d-2536">The regular expression Regex_italy_drivers_license_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="7e12d-2537">Viene trovata una parola chiave da Keyword_italy_drivers_license_number.</span><span class="sxs-lookup"><span data-stu-id="7e12d-2537">A keyword from Keyword_italy_drivers_license_number is found.</span></span>

```xml
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

### <a name="keywords"></a><span data-ttu-id="7e12d-2538">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="7e12d-2538">Keywords</span></span>

#### <a name="keyword_italy_drivers_license_number"></a><span data-ttu-id="7e12d-2539">Keyword_italy_drivers_license_number</span><span class="sxs-lookup"><span data-stu-id="7e12d-2539">Keyword_italy_drivers_license_number</span></span>

- <span data-ttu-id="7e12d-2540">numero di patente di guida</span><span class="sxs-lookup"><span data-stu-id="7e12d-2540">numero di patente di guida</span></span> 
- <span data-ttu-id="7e12d-2541">patente di guida</span><span class="sxs-lookup"><span data-stu-id="7e12d-2541">patente di guida</span></span> 
   
## <a name="japan-bank-account-number"></a><span data-ttu-id="7e12d-2542">Giappone - Numero di conto bancario</span><span class="sxs-lookup"><span data-stu-id="7e12d-2542">Japan Bank Account Number</span></span>

### <a name="format"></a><span data-ttu-id="7e12d-2543">Formato</span><span class="sxs-lookup"><span data-stu-id="7e12d-2543">Format</span></span>

<span data-ttu-id="7e12d-2544">Sette o otto cifre</span><span class="sxs-lookup"><span data-stu-id="7e12d-2544">Seven or eight digits</span></span>

### <a name="pattern"></a><span data-ttu-id="7e12d-2545">Modello</span><span class="sxs-lookup"><span data-stu-id="7e12d-2545">Pattern</span></span>

<span data-ttu-id="7e12d-2546">Numero di conto corrente:</span><span class="sxs-lookup"><span data-stu-id="7e12d-2546">Bank account number:</span></span>
- <span data-ttu-id="7e12d-2547">Sette o otto cifre</span><span class="sxs-lookup"><span data-stu-id="7e12d-2547">Seven or eight digits</span></span>
- <span data-ttu-id="7e12d-2548">Codice della filiale del conto corrente:</span><span class="sxs-lookup"><span data-stu-id="7e12d-2548">Bank account branch code:</span></span>
- <span data-ttu-id="7e12d-2549">Quattro cifre</span><span class="sxs-lookup"><span data-stu-id="7e12d-2549">Four digits</span></span> 
- <span data-ttu-id="7e12d-2550">Uno spazio o un trattino (facoltativo)</span><span class="sxs-lookup"><span data-stu-id="7e12d-2550">A space or dash (optional)</span></span> 
- <span data-ttu-id="7e12d-2551">Tre cifre</span><span class="sxs-lookup"><span data-stu-id="7e12d-2551">Three digits</span></span>

<span data-ttu-id="7e12d-2552">Checksum</span><span class="sxs-lookup"><span data-stu-id="7e12d-2552">Checksum</span></span>

<span data-ttu-id="7e12d-2553">No</span><span class="sxs-lookup"><span data-stu-id="7e12d-2553">No</span></span>

### <a name="definition"></a><span data-ttu-id="7e12d-2554">Definizione</span><span class="sxs-lookup"><span data-stu-id="7e12d-2554">Definition</span></span>

<span data-ttu-id="7e12d-2555">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="7e12d-2555">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="7e12d-2556">La funzione Func_jp_bank_account restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="7e12d-2556">The function Func_jp_bank_account finds content that matches the pattern.</span></span>
- <span data-ttu-id="7e12d-2557">Viene trovata una parola chiave da Keyword_jp_bank_account.</span><span class="sxs-lookup"><span data-stu-id="7e12d-2557">A keyword from Keyword_jp_bank_account is found.</span></span>
- <span data-ttu-id="7e12d-2558">Si verifica una delle situazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="7e12d-2558">One of the following is true:</span></span>
- <span data-ttu-id="7e12d-2559">La funzione Func_jp_bank_account_branch_code restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="7e12d-2559">The function Func_jp_bank_account_branch_code finds content that matches the pattern.</span></span>
- <span data-ttu-id="7e12d-2560">Viene trovata una parola chiave da Keyword_jp_bank_branch_code.</span><span class="sxs-lookup"><span data-stu-id="7e12d-2560">A keyword from Keyword_jp_bank_branch_code is found.</span></span>

<span data-ttu-id="7e12d-2561">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="7e12d-2561">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="7e12d-2562">La funzione Func_jp_bank_account restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="7e12d-2562">The function Func_jp_bank_account finds content that matches the pattern.</span></span>
- <span data-ttu-id="7e12d-2563">Viene trovata una parola chiave da Keyword_jp_bank_account.</span><span class="sxs-lookup"><span data-stu-id="7e12d-2563">A keyword from Keyword_jp_bank_account is found.</span></span>

```xml
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

### <a name="keywords"></a><span data-ttu-id="7e12d-2564">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="7e12d-2564">Keywords</span></span>

#### <a name="keyword_jp_bank_account"></a><span data-ttu-id="7e12d-2565">Keyword_jp_bank_account</span><span class="sxs-lookup"><span data-stu-id="7e12d-2565">Keyword_jp_bank_account</span></span>

- <span data-ttu-id="7e12d-2566">Checking Account Number</span><span class="sxs-lookup"><span data-stu-id="7e12d-2566">Checking Account Number</span></span> 
- <span data-ttu-id="7e12d-2567">Checking Account</span><span class="sxs-lookup"><span data-stu-id="7e12d-2567">Checking Account</span></span> 
- <span data-ttu-id="7e12d-2568">Checking Account #</span><span class="sxs-lookup"><span data-stu-id="7e12d-2568">Checking Account #</span></span> 
- <span data-ttu-id="7e12d-2569">Checking Acct Number</span><span class="sxs-lookup"><span data-stu-id="7e12d-2569">Checking Acct Number</span></span> 
- <span data-ttu-id="7e12d-2570">Checking Acct #</span><span class="sxs-lookup"><span data-stu-id="7e12d-2570">Checking Acct #</span></span> 
- <span data-ttu-id="7e12d-2571">Checking Acct No.</span><span class="sxs-lookup"><span data-stu-id="7e12d-2571">Checking Acct No.</span></span> 
- <span data-ttu-id="7e12d-2572">Checking Account No.</span><span class="sxs-lookup"><span data-stu-id="7e12d-2572">Checking Account No.</span></span> 
- <span data-ttu-id="7e12d-2573">Bank Account Number</span><span class="sxs-lookup"><span data-stu-id="7e12d-2573">Bank Account Number</span></span> 
- <span data-ttu-id="7e12d-2574">Bank Account</span><span class="sxs-lookup"><span data-stu-id="7e12d-2574">Bank Account</span></span> 
- <span data-ttu-id="7e12d-2575">Bank Account #</span><span class="sxs-lookup"><span data-stu-id="7e12d-2575">Bank Account #</span></span> 
- <span data-ttu-id="7e12d-2576">Bank Acct Number</span><span class="sxs-lookup"><span data-stu-id="7e12d-2576">Bank Acct Number</span></span> 
- <span data-ttu-id="7e12d-2577">Bank Acct #</span><span class="sxs-lookup"><span data-stu-id="7e12d-2577">Bank Acct #</span></span> 
- <span data-ttu-id="7e12d-2578">Bank Acct No.</span><span class="sxs-lookup"><span data-stu-id="7e12d-2578">Bank Acct No.</span></span> 
- <span data-ttu-id="7e12d-2579">Bank Account No.</span><span class="sxs-lookup"><span data-stu-id="7e12d-2579">Bank Account No.</span></span> 
- <span data-ttu-id="7e12d-2580">Savings Account Number</span><span class="sxs-lookup"><span data-stu-id="7e12d-2580">Savings Account Number</span></span> 
- <span data-ttu-id="7e12d-2581">Savings Account</span><span class="sxs-lookup"><span data-stu-id="7e12d-2581">Savings Account</span></span> 
- <span data-ttu-id="7e12d-2582">Savings Account #</span><span class="sxs-lookup"><span data-stu-id="7e12d-2582">Savings Account #</span></span> 
- <span data-ttu-id="7e12d-2583">Savings Acct Number</span><span class="sxs-lookup"><span data-stu-id="7e12d-2583">Savings Acct Number</span></span> 
- <span data-ttu-id="7e12d-2584">Savings Acct #</span><span class="sxs-lookup"><span data-stu-id="7e12d-2584">Savings Acct #</span></span> 
- <span data-ttu-id="7e12d-2585">Savings Acct No.</span><span class="sxs-lookup"><span data-stu-id="7e12d-2585">Savings Acct No.</span></span> 
- <span data-ttu-id="7e12d-2586">Savings Account No.</span><span class="sxs-lookup"><span data-stu-id="7e12d-2586">Savings Account No.</span></span> 
- <span data-ttu-id="7e12d-2587">Debit Account Number</span><span class="sxs-lookup"><span data-stu-id="7e12d-2587">Debit Account Number</span></span> 
- <span data-ttu-id="7e12d-2588">Debit Account</span><span class="sxs-lookup"><span data-stu-id="7e12d-2588">Debit Account</span></span> 
- <span data-ttu-id="7e12d-2589">Debit Account #</span><span class="sxs-lookup"><span data-stu-id="7e12d-2589">Debit Account #</span></span> 
- <span data-ttu-id="7e12d-2590">Debit Acct Number</span><span class="sxs-lookup"><span data-stu-id="7e12d-2590">Debit Acct Number</span></span> 
- <span data-ttu-id="7e12d-2591">Debit Acct #</span><span class="sxs-lookup"><span data-stu-id="7e12d-2591">Debit Acct #</span></span> 
- <span data-ttu-id="7e12d-2592">Debit Acct No.</span><span class="sxs-lookup"><span data-stu-id="7e12d-2592">Debit Acct No.</span></span> 
- <span data-ttu-id="7e12d-2593">Debit Account No.</span><span class="sxs-lookup"><span data-stu-id="7e12d-2593">Debit Account No.</span></span> 
- <span data-ttu-id="7e12d-2594">口座番号を当座預金口座の確認</span><span class="sxs-lookup"><span data-stu-id="7e12d-2594">口座番号を当座預金口座の確認</span></span> 
- <span data-ttu-id="7e12d-2595">#アカウントの確認 、 勘定番号の確認</span><span class="sxs-lookup"><span data-stu-id="7e12d-2595">＃アカウントの確認、勘定番号の確認</span></span> 
- <span data-ttu-id="7e12d-2596">#勘定の確認</span><span class="sxs-lookup"><span data-stu-id="7e12d-2596">＃勘定の確認</span></span> 
- <span data-ttu-id="7e12d-2597">勘定番号の確認</span><span class="sxs-lookup"><span data-stu-id="7e12d-2597">勘定番号の確認</span></span> 
- <span data-ttu-id="7e12d-2598">口座番号の確認</span><span class="sxs-lookup"><span data-stu-id="7e12d-2598">口座番号の確認</span></span> 
- <span data-ttu-id="7e12d-2599">銀行口座番号</span><span class="sxs-lookup"><span data-stu-id="7e12d-2599">銀行口座番号</span></span> 
- <span data-ttu-id="7e12d-2600">銀行口座</span><span class="sxs-lookup"><span data-stu-id="7e12d-2600">銀行口座</span></span> 
- <span data-ttu-id="7e12d-2601">銀行口座＃</span><span class="sxs-lookup"><span data-stu-id="7e12d-2601">銀行口座＃</span></span> 
- <span data-ttu-id="7e12d-2602">銀行の勘定番号</span><span class="sxs-lookup"><span data-stu-id="7e12d-2602">銀行の勘定番号</span></span> 
- <span data-ttu-id="7e12d-2603">銀行のacct＃</span><span class="sxs-lookup"><span data-stu-id="7e12d-2603">銀行のacct＃</span></span> 
- <span data-ttu-id="7e12d-2604">銀行の勘定いいえ</span><span class="sxs-lookup"><span data-stu-id="7e12d-2604">銀行の勘定いいえ</span></span> 
- <span data-ttu-id="7e12d-2605">銀行口座番号</span><span class="sxs-lookup"><span data-stu-id="7e12d-2605">銀行口座番号</span></span>
- <span data-ttu-id="7e12d-2606">普通預金口座番号</span><span class="sxs-lookup"><span data-stu-id="7e12d-2606">普通預金口座番号</span></span> 
- <span data-ttu-id="7e12d-2607">預金口座</span><span class="sxs-lookup"><span data-stu-id="7e12d-2607">預金口座</span></span> 
- <span data-ttu-id="7e12d-2608">貯蓄口座＃</span><span class="sxs-lookup"><span data-stu-id="7e12d-2608">貯蓄口座＃</span></span> 
- <span data-ttu-id="7e12d-2609">貯蓄勘定の数</span><span class="sxs-lookup"><span data-stu-id="7e12d-2609">貯蓄勘定の数</span></span> 
- <span data-ttu-id="7e12d-2610">貯蓄勘定＃</span><span class="sxs-lookup"><span data-stu-id="7e12d-2610">貯蓄勘定＃</span></span> 
- <span data-ttu-id="7e12d-2611">貯蓄勘定番号</span><span class="sxs-lookup"><span data-stu-id="7e12d-2611">貯蓄勘定番号</span></span> 
- <span data-ttu-id="7e12d-2612">普通預金口座番号</span><span class="sxs-lookup"><span data-stu-id="7e12d-2612">普通預金口座番号</span></span> 
- <span data-ttu-id="7e12d-2613">引き落とし口座番号</span><span class="sxs-lookup"><span data-stu-id="7e12d-2613">引き落とし口座番号</span></span> 
- <span data-ttu-id="7e12d-2614">口座番号</span><span class="sxs-lookup"><span data-stu-id="7e12d-2614">口座番号</span></span> 
- <span data-ttu-id="7e12d-2615">口座番号＃</span><span class="sxs-lookup"><span data-stu-id="7e12d-2615">口座番号＃</span></span> 
- <span data-ttu-id="7e12d-2616">デビットのacct番号</span><span class="sxs-lookup"><span data-stu-id="7e12d-2616">デビットのacct番号</span></span> 
- <span data-ttu-id="7e12d-2617">デビット勘定＃</span><span class="sxs-lookup"><span data-stu-id="7e12d-2617">デビット勘定＃</span></span> 
- <span data-ttu-id="7e12d-2618">デビットACCTの番号</span><span class="sxs-lookup"><span data-stu-id="7e12d-2618">デビットACCTの番号</span></span> 
- <span data-ttu-id="7e12d-2619">デビット口座番号</span><span class="sxs-lookup"><span data-stu-id="7e12d-2619">デビット口座番号</span></span> 

#### <a name="keyword_jp_bank_branch_code"></a><span data-ttu-id="7e12d-2620">Keyword_jp_bank_branch_code</span><span class="sxs-lookup"><span data-stu-id="7e12d-2620">Keyword_jp_bank_branch_code</span></span>

<span data-ttu-id="7e12d-2621">Otemachi</span><span class="sxs-lookup"><span data-stu-id="7e12d-2621">Otemachi</span></span>

## <a name="japan-drivers-license-number"></a><span data-ttu-id="7e12d-2622">Giappone - Numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="7e12d-2622">Japan Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="7e12d-2623">Formato</span><span class="sxs-lookup"><span data-stu-id="7e12d-2623">Format</span></span>

<span data-ttu-id="7e12d-2624">12 cifre</span><span class="sxs-lookup"><span data-stu-id="7e12d-2624">12 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="7e12d-2625">Modello</span><span class="sxs-lookup"><span data-stu-id="7e12d-2625">Pattern</span></span>

<span data-ttu-id="7e12d-2626">12 cifre consecutive</span><span class="sxs-lookup"><span data-stu-id="7e12d-2626">12 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="7e12d-2627">Checksum</span><span class="sxs-lookup"><span data-stu-id="7e12d-2627">Checksum</span></span>

<span data-ttu-id="7e12d-2628">No</span><span class="sxs-lookup"><span data-stu-id="7e12d-2628">No</span></span>

### <a name="definition"></a><span data-ttu-id="7e12d-2629">Definizione</span><span class="sxs-lookup"><span data-stu-id="7e12d-2629">Definition</span></span>

<span data-ttu-id="7e12d-2630">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="7e12d-2630">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="7e12d-2631">La funzione Func_jp_drivers_license_number restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="7e12d-2631">The function Func_jp_drivers_license_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="7e12d-2632">Viene trovata una parola chiave da Keyword_jp_drivers_license_number.</span><span class="sxs-lookup"><span data-stu-id="7e12d-2632">A keyword from Keyword_jp_drivers_license_number is found.</span></span>

```xml
<!-- Japan Driver's License Number -->
<Entity id="c6011143-d087-451c-8313-7f6d4aed2270" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_jp_drivers_license_number" />
        <Match idRef ="Keyword_jp_drivers_license_number" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="7e12d-2633">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="7e12d-2633">Keywords</span></span>

#### <a name="keyword_jp_drivers_license_number"></a><span data-ttu-id="7e12d-2634">Keyword_jp_drivers_license_number</span><span class="sxs-lookup"><span data-stu-id="7e12d-2634">Keyword_jp_drivers_license_number</span></span>

- <span data-ttu-id="7e12d-2635">DL #</span><span class="sxs-lookup"><span data-stu-id="7e12d-2635">dl#</span></span> 
- <span data-ttu-id="7e12d-2636">DL</span><span class="sxs-lookup"><span data-stu-id="7e12d-2636">DL＃</span></span> 
- <span data-ttu-id="7e12d-2637">DLS #</span><span class="sxs-lookup"><span data-stu-id="7e12d-2637">dls#</span></span> 
- <span data-ttu-id="7e12d-2638">DLS</span><span class="sxs-lookup"><span data-stu-id="7e12d-2638">DLS＃</span></span> 
- <span data-ttu-id="7e12d-2639">driver license</span><span class="sxs-lookup"><span data-stu-id="7e12d-2639">driver license</span></span> 
- <span data-ttu-id="7e12d-2640">driver licenses</span><span class="sxs-lookup"><span data-stu-id="7e12d-2640">driver licenses</span></span> 
- <span data-ttu-id="7e12d-2641">drivers license</span><span class="sxs-lookup"><span data-stu-id="7e12d-2641">drivers license</span></span> 
- <span data-ttu-id="7e12d-2642">driver's license</span><span class="sxs-lookup"><span data-stu-id="7e12d-2642">driver's license</span></span> 
- <span data-ttu-id="7e12d-2643">drivers licenses</span><span class="sxs-lookup"><span data-stu-id="7e12d-2643">drivers licenses</span></span> 
- <span data-ttu-id="7e12d-2644">driver's licenses</span><span class="sxs-lookup"><span data-stu-id="7e12d-2644">driver's licenses</span></span> 
- <span data-ttu-id="7e12d-2645">driving licence</span><span class="sxs-lookup"><span data-stu-id="7e12d-2645">driving licence</span></span> 
- <span data-ttu-id="7e12d-2646">driver'lic #</span><span class="sxs-lookup"><span data-stu-id="7e12d-2646">lic#</span></span> 
- <span data-ttu-id="7e12d-2647">DRIVER'LIC</span><span class="sxs-lookup"><span data-stu-id="7e12d-2647">LIC＃</span></span> 
- <span data-ttu-id="7e12d-2648">driver'lics #</span><span class="sxs-lookup"><span data-stu-id="7e12d-2648">lics#</span></span> 
- <span data-ttu-id="7e12d-2649">state id</span><span class="sxs-lookup"><span data-stu-id="7e12d-2649">state id</span></span> 
- <span data-ttu-id="7e12d-2650">state identification</span><span class="sxs-lookup"><span data-stu-id="7e12d-2650">state identification</span></span> 
- <span data-ttu-id="7e12d-2651">state identification number</span><span class="sxs-lookup"><span data-stu-id="7e12d-2651">state identification number</span></span> 
- <span data-ttu-id="7e12d-2652">低所得国＃</span><span class="sxs-lookup"><span data-stu-id="7e12d-2652">低所得国＃</span></span> 
- <span data-ttu-id="7e12d-2653">免許証</span><span class="sxs-lookup"><span data-stu-id="7e12d-2653">免許証</span></span> 
- <span data-ttu-id="7e12d-2654">状態ID</span><span class="sxs-lookup"><span data-stu-id="7e12d-2654">状態ID</span></span>
- <span data-ttu-id="7e12d-2655">状態の識別</span><span class="sxs-lookup"><span data-stu-id="7e12d-2655">状態の識別</span></span> 
- <span data-ttu-id="7e12d-2656">状態の識別番号</span><span class="sxs-lookup"><span data-stu-id="7e12d-2656">状態の識別番号</span></span> 
- <span data-ttu-id="7e12d-2657">運転免許</span><span class="sxs-lookup"><span data-stu-id="7e12d-2657">運転免許</span></span> 
- <span data-ttu-id="7e12d-2658">運転免許証</span><span class="sxs-lookup"><span data-stu-id="7e12d-2658">運転免許証</span></span> 
- <span data-ttu-id="7e12d-2659">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="7e12d-2659">運転免許証番号</span></span> 
   
## <a name="japan-passport-number"></a><span data-ttu-id="7e12d-2660">Giappone - Numero di passaporto</span><span class="sxs-lookup"><span data-stu-id="7e12d-2660">Japan Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="7e12d-2661">Formato</span><span class="sxs-lookup"><span data-stu-id="7e12d-2661">Format</span></span>

<span data-ttu-id="7e12d-2662">Due lettere seguite da 7 cifre</span><span class="sxs-lookup"><span data-stu-id="7e12d-2662">Two letters followed by seven digits</span></span>

### <a name="pattern"></a><span data-ttu-id="7e12d-2663">Modello</span><span class="sxs-lookup"><span data-stu-id="7e12d-2663">Pattern</span></span>

<span data-ttu-id="7e12d-2664">Due lettere (senza distinzione tra maiuscole/minuscole) seguite da sette cifre</span><span class="sxs-lookup"><span data-stu-id="7e12d-2664">Two letters (not case sensitive) followed by seven digits</span></span>

### <a name="checksum"></a><span data-ttu-id="7e12d-2665">Checksum</span><span class="sxs-lookup"><span data-stu-id="7e12d-2665">Checksum</span></span>

<span data-ttu-id="7e12d-2666">No</span><span class="sxs-lookup"><span data-stu-id="7e12d-2666">No</span></span>

### <a name="definition"></a><span data-ttu-id="7e12d-2667">Definizione</span><span class="sxs-lookup"><span data-stu-id="7e12d-2667">Definition</span></span>

<span data-ttu-id="7e12d-2668">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="7e12d-2668">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="7e12d-2669">La funzione Func_jp_passport restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="7e12d-2669">The function Func_jp_passport finds content that matches the pattern.</span></span>
- <span data-ttu-id="7e12d-2670">Viene trovata una parola chiave da Keyword_jp_passport.</span><span class="sxs-lookup"><span data-stu-id="7e12d-2670">A keyword from Keyword_jp_passport is found.</span></span>

```xml
<!-- Japan Passport Number -->
<Entity id="75177310-1a09-4613-bf6d-833aae3743f8" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_jp_passport" />
        <Match idRef="Keyword_jp_passport" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="7e12d-2671">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="7e12d-2671">Keywords</span></span>

#### <a name="keyword_jp_passport"></a><span data-ttu-id="7e12d-2672">Keyword_jp_passport</span><span class="sxs-lookup"><span data-stu-id="7e12d-2672">Keyword_jp_passport</span></span>

- <span data-ttu-id="7e12d-2673">パスポート</span><span class="sxs-lookup"><span data-stu-id="7e12d-2673">パスポート</span></span> 
- <span data-ttu-id="7e12d-2674">パスポート番号</span><span class="sxs-lookup"><span data-stu-id="7e12d-2674">パスポート番号</span></span> 
- <span data-ttu-id="7e12d-2675">パスポートのNum</span><span class="sxs-lookup"><span data-stu-id="7e12d-2675">パスポートのNum</span></span> 
- <span data-ttu-id="7e12d-2676">パスポート＃</span><span class="sxs-lookup"><span data-stu-id="7e12d-2676">パスポート＃</span></span> 
   
## <a name="japan-resident-registration-number"></a><span data-ttu-id="7e12d-2677">Giappone - Numero di registrazione dei residenti</span><span class="sxs-lookup"><span data-stu-id="7e12d-2677">Japan Resident Registration Number</span></span>

### <a name="format"></a><span data-ttu-id="7e12d-2678">Formato</span><span class="sxs-lookup"><span data-stu-id="7e12d-2678">Format</span></span>

<span data-ttu-id="7e12d-2679">11 cifre</span><span class="sxs-lookup"><span data-stu-id="7e12d-2679">11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="7e12d-2680">Modello</span><span class="sxs-lookup"><span data-stu-id="7e12d-2680">Pattern</span></span>

<span data-ttu-id="7e12d-2681">11 cifre consecutive</span><span class="sxs-lookup"><span data-stu-id="7e12d-2681">11 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="7e12d-2682">Checksum</span><span class="sxs-lookup"><span data-stu-id="7e12d-2682">Checksum</span></span>

<span data-ttu-id="7e12d-2683">No</span><span class="sxs-lookup"><span data-stu-id="7e12d-2683">No</span></span>

### <a name="definition"></a><span data-ttu-id="7e12d-2684">Definizione</span><span class="sxs-lookup"><span data-stu-id="7e12d-2684">Definition</span></span>

<span data-ttu-id="7e12d-2685">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="7e12d-2685">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="7e12d-2686">La funzione Func_jp_resident_registration_number restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="7e12d-2686">The function Func_jp_resident_registration_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="7e12d-2687">Viene trovata una parola chiave da Keyword_jp_resident_registration_number.</span><span class="sxs-lookup"><span data-stu-id="7e12d-2687">A keyword from Keyword_jp_resident_registration_number is found.</span></span>

```xml
<!-- Japan Resident Registration Number -->
<Entity id="01c1209b-6389-4faf-a5f8-3f7e13899652" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_jp_resident_registration_number" />
        <Match idRef ="Keyword_jp_resident_registration_number" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="7e12d-2688">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="7e12d-2688">Keywords</span></span>

#### <a name="keyword_jp_resident_registration_number"></a><span data-ttu-id="7e12d-2689">Keyword_jp_resident_registration_number</span><span class="sxs-lookup"><span data-stu-id="7e12d-2689">Keyword_jp_resident_registration_number</span></span>

- <span data-ttu-id="7e12d-2690">Resident Registration Number</span><span class="sxs-lookup"><span data-stu-id="7e12d-2690">Resident Registration Number</span></span>
- <span data-ttu-id="7e12d-2691">Resident Register Number</span><span class="sxs-lookup"><span data-stu-id="7e12d-2691">Resident Register Number</span></span> 
- <span data-ttu-id="7e12d-2692">Residents Basic Registry Number</span><span class="sxs-lookup"><span data-stu-id="7e12d-2692">Residents Basic Registry Number</span></span> 
- <span data-ttu-id="7e12d-2693">Resident Registration No.</span><span class="sxs-lookup"><span data-stu-id="7e12d-2693">Resident Registration No.</span></span> 
- <span data-ttu-id="7e12d-2694">Resident Register No.</span><span class="sxs-lookup"><span data-stu-id="7e12d-2694">Resident Register No.</span></span> 
- <span data-ttu-id="7e12d-2695">Residents Basic Registry No.</span><span class="sxs-lookup"><span data-stu-id="7e12d-2695">Residents Basic Registry No.</span></span> 
- <span data-ttu-id="7e12d-2696">Basic Resident Register No.</span><span class="sxs-lookup"><span data-stu-id="7e12d-2696">Basic Resident Register No.</span></span> 
- <span data-ttu-id="7e12d-2697">住民登録番号、登録番号をレジデント</span><span class="sxs-lookup"><span data-stu-id="7e12d-2697">住民登録番号、登録番号をレジデント</span></span> 
- <span data-ttu-id="7e12d-2698">住民基本登録番号、登録番号</span><span class="sxs-lookup"><span data-stu-id="7e12d-2698">住民基本登録番号、登録番号</span></span> 
- <span data-ttu-id="7e12d-2699">住民基本レジストリ番号を常駐</span><span class="sxs-lookup"><span data-stu-id="7e12d-2699">住民基本レジストリ番号を常駐</span></span> 
- <span data-ttu-id="7e12d-2700">登録番号を常駐住民基本台帳登録番号</span><span class="sxs-lookup"><span data-stu-id="7e12d-2700">登録番号を常駐住民基本台帳登録番号</span></span> 

   
## <a name="japan-social-insurance-number-sin"></a><span data-ttu-id="7e12d-2701">Giappone - Numero di assicurazione sociale (SIN)</span><span class="sxs-lookup"><span data-stu-id="7e12d-2701">Japan Social Insurance Number (SIN)</span></span>

### <a name="format"></a><span data-ttu-id="7e12d-2702">Formato</span><span class="sxs-lookup"><span data-stu-id="7e12d-2702">Format</span></span>

<span data-ttu-id="7e12d-2703">7-12 cifre</span><span class="sxs-lookup"><span data-stu-id="7e12d-2703">7-12 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="7e12d-2704">Modello</span><span class="sxs-lookup"><span data-stu-id="7e12d-2704">Pattern</span></span>

<span data-ttu-id="7e12d-2705">7-12 cifre:</span><span class="sxs-lookup"><span data-stu-id="7e12d-2705">7-12 digits:</span></span>
- <span data-ttu-id="7e12d-2706">Quattro cifre</span><span class="sxs-lookup"><span data-stu-id="7e12d-2706">Four digits</span></span> 
- <span data-ttu-id="7e12d-2707">Una lineetta (facoltativa)</span><span class="sxs-lookup"><span data-stu-id="7e12d-2707">A hyphen (optional)</span></span> 
- <span data-ttu-id="7e12d-2708">Sei cifre o</span><span class="sxs-lookup"><span data-stu-id="7e12d-2708">Six digits OR</span></span>
- <span data-ttu-id="7e12d-2709">7-12 cifre consecutive</span><span class="sxs-lookup"><span data-stu-id="7e12d-2709">7-12 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="7e12d-2710">Checksum</span><span class="sxs-lookup"><span data-stu-id="7e12d-2710">Checksum</span></span>

<span data-ttu-id="7e12d-2711">No</span><span class="sxs-lookup"><span data-stu-id="7e12d-2711">No</span></span>

### <a name="definition"></a><span data-ttu-id="7e12d-2712">Definizione</span><span class="sxs-lookup"><span data-stu-id="7e12d-2712">Definition</span></span>

<span data-ttu-id="7e12d-2713">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="7e12d-2713">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="7e12d-2714">La funzione Func_jp_sin restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="7e12d-2714">The function Func_jp_sin finds content that matches the pattern.</span></span>
- <span data-ttu-id="7e12d-2715">Viene trovata una parola chiave da Keyword_jp_sin.</span><span class="sxs-lookup"><span data-stu-id="7e12d-2715">A keyword from Keyword_jp_sin is found.</span></span>

<span data-ttu-id="7e12d-2716">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="7e12d-2716">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="7e12d-2717">La funzione Func_jp_sin_pre_1997 restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="7e12d-2717">The function Func_jp_sin_pre_1997 finds content that matches the pattern.</span></span>
- <span data-ttu-id="7e12d-2718">Viene trovata una parola chiave da Keyword_jp_sin.</span><span class="sxs-lookup"><span data-stu-id="7e12d-2718">A keyword from Keyword_jp_sin is found.</span></span>

```xml
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

### <a name="keywords"></a><span data-ttu-id="7e12d-2719">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="7e12d-2719">Keywords</span></span>

#### <a name="keyword_jp_sin"></a><span data-ttu-id="7e12d-2720">Keyword_jp_sin</span><span class="sxs-lookup"><span data-stu-id="7e12d-2720">Keyword_jp_sin</span></span>

- <span data-ttu-id="7e12d-2721">Social Insurance No.</span><span class="sxs-lookup"><span data-stu-id="7e12d-2721">Social Insurance No.</span></span> 
- <span data-ttu-id="7e12d-2722">Social Insurance Num</span><span class="sxs-lookup"><span data-stu-id="7e12d-2722">Social Insurance Num</span></span> 
- <span data-ttu-id="7e12d-2723">Social Insurance Number</span><span class="sxs-lookup"><span data-stu-id="7e12d-2723">Social Insurance Number</span></span> 
- <span data-ttu-id="7e12d-2724">社会保険のテンキー</span><span class="sxs-lookup"><span data-stu-id="7e12d-2724">社会保険のテンキー</span></span> 
- <span data-ttu-id="7e12d-2725">社会保険番号</span><span class="sxs-lookup"><span data-stu-id="7e12d-2725">社会保険番号</span></span> 

## <a name="japanese-residence-card-number"></a><span data-ttu-id="7e12d-2726">Numero di carta di soggiorno giapponese</span><span class="sxs-lookup"><span data-stu-id="7e12d-2726">Japanese Residence Card Number</span></span>

### <a name="format"></a><span data-ttu-id="7e12d-2727">Formato</span><span class="sxs-lookup"><span data-stu-id="7e12d-2727">Format</span></span>

<span data-ttu-id="7e12d-2728">12 lettere e cifre</span><span class="sxs-lookup"><span data-stu-id="7e12d-2728">12 letters and digits</span></span>

### <a name="pattern"></a><span data-ttu-id="7e12d-2729">Modello</span><span class="sxs-lookup"><span data-stu-id="7e12d-2729">Pattern</span></span>

<span data-ttu-id="7e12d-2730">12 lettere e cifre:</span><span class="sxs-lookup"><span data-stu-id="7e12d-2730">12 letters and digits:</span></span>
- <span data-ttu-id="7e12d-2731">Due lettere (senza distinzione tra maiuscole/minuscole)</span><span class="sxs-lookup"><span data-stu-id="7e12d-2731">Two letters (not case sensitive)</span></span>
- <span data-ttu-id="7e12d-2732">Otto cifre</span><span class="sxs-lookup"><span data-stu-id="7e12d-2732">Eight digits</span></span> 
- <span data-ttu-id="7e12d-2733">Due lettere (senza distinzione tra maiuscole/minuscole)</span><span class="sxs-lookup"><span data-stu-id="7e12d-2733">Two letters (not case sensitive)</span></span>

### <a name="checksum"></a><span data-ttu-id="7e12d-2734">Checksum</span><span class="sxs-lookup"><span data-stu-id="7e12d-2734">Checksum</span></span>

<span data-ttu-id="7e12d-2735">No</span><span class="sxs-lookup"><span data-stu-id="7e12d-2735">No</span></span>

### <a name="definition"></a><span data-ttu-id="7e12d-2736">Definizione</span><span class="sxs-lookup"><span data-stu-id="7e12d-2736">Definition</span></span>

<span data-ttu-id="7e12d-2737">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="7e12d-2737">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="7e12d-2738">L'espressione regolare Regex_jp_residence_card_number trova il contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="7e12d-2738">The regular expression Regex_jp_residence_card_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="7e12d-2739">Viene trovata una parola chiave da Keyword_jp_residence_card_number.</span><span class="sxs-lookup"><span data-stu-id="7e12d-2739">A keyword from Keyword_jp_residence_card_number is found.</span></span>

```xml
<!--Japan Residence Card Number-->
-<Entity id="ac36fef2-a289-4e2c-bb48-b02366e89fc0" recommendedConfidence="75" patternsProximity="300">
   -<Pattern confidenceLevel="75">
      <IdMatch idRef="Regex_jp_residence_card_number"/>
      <Match idRef="Keyword_jp_residence_card_number"/>
   </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="7e12d-2740">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="7e12d-2740">Keywords</span></span>

#### <a name="keyword_jp_residence_card_number"></a><span data-ttu-id="7e12d-2741">Keyword_jp_residence_card_number</span><span class="sxs-lookup"><span data-stu-id="7e12d-2741">Keyword_jp_residence_card_number</span></span>

- <span data-ttu-id="7e12d-2742">Numero di carta di soggiorno</span><span class="sxs-lookup"><span data-stu-id="7e12d-2742">Residence card number</span></span>
- <span data-ttu-id="7e12d-2743">Carta di soggiorno No</span><span class="sxs-lookup"><span data-stu-id="7e12d-2743">Residence card no</span></span>
- <span data-ttu-id="7e12d-2744">Carta di soggiorno #</span><span class="sxs-lookup"><span data-stu-id="7e12d-2744">Residence card #</span></span>
- <span data-ttu-id="7e12d-2745">在留カード番号</span><span class="sxs-lookup"><span data-stu-id="7e12d-2745">在留カード番号</span></span>
   
## <a name="malaysia-id-card-number"></a><span data-ttu-id="7e12d-2746">Malesia - Numero di carta d’identità</span><span class="sxs-lookup"><span data-stu-id="7e12d-2746">Malaysia ID Card Number</span></span>

### <a name="format"></a><span data-ttu-id="7e12d-2747">Formato</span><span class="sxs-lookup"><span data-stu-id="7e12d-2747">Format</span></span>

<span data-ttu-id="7e12d-2748">12 cifre contenenti lineette facoltative</span><span class="sxs-lookup"><span data-stu-id="7e12d-2748">12 digits containing optional hyphens</span></span>

### <a name="pattern"></a><span data-ttu-id="7e12d-2749">Modello</span><span class="sxs-lookup"><span data-stu-id="7e12d-2749">Pattern</span></span>

<span data-ttu-id="7e12d-2750">12 cifre:</span><span class="sxs-lookup"><span data-stu-id="7e12d-2750">12 digits:</span></span>
- <span data-ttu-id="7e12d-2751">Sei cifre nel formato AAMMGG, ovvero la data di nascita</span><span class="sxs-lookup"><span data-stu-id="7e12d-2751">Six digits in the format YYMMDD which are the date of birth</span></span> 
- <span data-ttu-id="7e12d-2752">Un trattino (facoltativo)</span><span class="sxs-lookup"><span data-stu-id="7e12d-2752">A dash (optional)</span></span> 
- <span data-ttu-id="7e12d-2753">Codice luogo di nascita a due lettere </span><span class="sxs-lookup"><span data-stu-id="7e12d-2753">Two-letter place-of-birth code</span></span> 
- <span data-ttu-id="7e12d-2754">Un trattino (facoltativo)</span><span class="sxs-lookup"><span data-stu-id="7e12d-2754">A dash (optional)</span></span> 
- <span data-ttu-id="7e12d-2755">Tre cifre casuali </span><span class="sxs-lookup"><span data-stu-id="7e12d-2755">Three random digits</span></span> 
- <span data-ttu-id="7e12d-2756">Codice genere a una cifra singola</span><span class="sxs-lookup"><span data-stu-id="7e12d-2756">One-digit gender code</span></span>

### <a name="checksum"></a><span data-ttu-id="7e12d-2757">Checksum</span><span class="sxs-lookup"><span data-stu-id="7e12d-2757">Checksum</span></span>

<span data-ttu-id="7e12d-2758">No</span><span class="sxs-lookup"><span data-stu-id="7e12d-2758">No</span></span>

### <a name="definition"></a><span data-ttu-id="7e12d-2759">Definizione</span><span class="sxs-lookup"><span data-stu-id="7e12d-2759">Definition</span></span>

<span data-ttu-id="7e12d-2760">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="7e12d-2760">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="7e12d-2761">L'espressione regolare Regex_malaysia_id_card_number trova il contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="7e12d-2761">The regular expression Regex_malaysia_id_card_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="7e12d-2762">Viene trovata una parola chiave da Keyword_malaysia_id_card_number.</span><span class="sxs-lookup"><span data-stu-id="7e12d-2762">A keyword from Keyword_malaysia_id_card_number is found.</span></span>

```xml
<!-- Malaysia ID Card Number -->
</Entity>
      <Entity id="7f0e921c-9677-435b-aba2-bb8f1013c749" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
            <IdMatch idRef="Regex_malaysia_id_card_number" />
            <Match idRef="Keyword_malaysia_id_card_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="7e12d-2763">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="7e12d-2763">Keywords</span></span>
   
#### <a name="keyword_malaysia_id_card_number"></a><span data-ttu-id="7e12d-2764">Keyword_malaysia_id_card_number</span><span class="sxs-lookup"><span data-stu-id="7e12d-2764">Keyword_malaysia_id_card_number</span></span>

- <span data-ttu-id="7e12d-2765">scheda dell'applicazione digitale</span><span class="sxs-lookup"><span data-stu-id="7e12d-2765">digital application card</span></span>
- <span data-ttu-id="7e12d-2766">i/c</span><span class="sxs-lookup"><span data-stu-id="7e12d-2766">i/c</span></span>
- <span data-ttu-id="7e12d-2767">i/c no</span><span class="sxs-lookup"><span data-stu-id="7e12d-2767">i/c no</span></span>
- <span data-ttu-id="7e12d-2768">IC</span><span class="sxs-lookup"><span data-stu-id="7e12d-2768">ic</span></span>
- <span data-ttu-id="7e12d-2769">IC No</span><span class="sxs-lookup"><span data-stu-id="7e12d-2769">ic no</span></span>
- <span data-ttu-id="7e12d-2770">id card</span><span class="sxs-lookup"><span data-stu-id="7e12d-2770">id card</span></span>
- <span data-ttu-id="7e12d-2771">Scheda di identificazione</span><span class="sxs-lookup"><span data-stu-id="7e12d-2771">identification Card</span></span>
- <span data-ttu-id="7e12d-2772">carta di identità</span><span class="sxs-lookup"><span data-stu-id="7e12d-2772">identity card</span></span>
- <span data-ttu-id="7e12d-2773">k/p</span><span class="sxs-lookup"><span data-stu-id="7e12d-2773">k/p</span></span>
- <span data-ttu-id="7e12d-2774">k/p no</span><span class="sxs-lookup"><span data-stu-id="7e12d-2774">k/p no</span></span>
- <span data-ttu-id="7e12d-2775">diri akuan Kad</span><span class="sxs-lookup"><span data-stu-id="7e12d-2775">kad akuan diri</span></span>
- <span data-ttu-id="7e12d-2776">Kad Aplikasi digitale</span><span class="sxs-lookup"><span data-stu-id="7e12d-2776">kad aplikasi digital</span></span>
- <span data-ttu-id="7e12d-2777">Kad Pengenalan Malaysia</span><span class="sxs-lookup"><span data-stu-id="7e12d-2777">kad pengenalan malaysia</span></span>
- <span data-ttu-id="7e12d-2778">KP</span><span class="sxs-lookup"><span data-stu-id="7e12d-2778">kp</span></span>
- <span data-ttu-id="7e12d-2779">KP No</span><span class="sxs-lookup"><span data-stu-id="7e12d-2779">kp no</span></span>
- <span data-ttu-id="7e12d-2780">MyKad</span><span class="sxs-lookup"><span data-stu-id="7e12d-2780">mykad</span></span>
- <span data-ttu-id="7e12d-2781">MYKAS</span><span class="sxs-lookup"><span data-stu-id="7e12d-2781">mykas</span></span>
- <span data-ttu-id="7e12d-2782">mykid</span><span class="sxs-lookup"><span data-stu-id="7e12d-2782">mykid</span></span>
- <span data-ttu-id="7e12d-2783">mypr</span><span class="sxs-lookup"><span data-stu-id="7e12d-2783">mypr</span></span>
- <span data-ttu-id="7e12d-2784">mytentera</span><span class="sxs-lookup"><span data-stu-id="7e12d-2784">mytentera</span></span>
- <span data-ttu-id="7e12d-2785">carta di identità Malaysia</span><span class="sxs-lookup"><span data-stu-id="7e12d-2785">malaysia identity card</span></span>
- <span data-ttu-id="7e12d-2786">carta di identità malaysiana</span><span class="sxs-lookup"><span data-stu-id="7e12d-2786">malaysian identity card</span></span>
- <span data-ttu-id="7e12d-2787">NRIC</span><span class="sxs-lookup"><span data-stu-id="7e12d-2787">nric</span></span>
- <span data-ttu-id="7e12d-2788">scheda di identificazione personale</span><span class="sxs-lookup"><span data-stu-id="7e12d-2788">personal identification card</span></span>
   
## <a name="netherlands-citizens-service-bsn-number"></a><span data-ttu-id="7e12d-2789">Paesi Bassi - Numero di servizio cittadino (BSN)</span><span class="sxs-lookup"><span data-stu-id="7e12d-2789">Netherlands Citizen's Service (BSN) Number</span></span>

### <a name="format"></a><span data-ttu-id="7e12d-2790">Formato</span><span class="sxs-lookup"><span data-stu-id="7e12d-2790">Format</span></span>

<span data-ttu-id="7e12d-2791">8-9 cifre contenenti spazi facoltativi </span><span class="sxs-lookup"><span data-stu-id="7e12d-2791">8-9 digits containing optional spaces</span></span>

### <a name="pattern"></a><span data-ttu-id="7e12d-2792">Modello</span><span class="sxs-lookup"><span data-stu-id="7e12d-2792">Pattern</span></span>

<span data-ttu-id="7e12d-2793">8-9 cifre:</span><span class="sxs-lookup"><span data-stu-id="7e12d-2793">8-9 digits:</span></span>
- <span data-ttu-id="7e12d-2794">Tre cifre</span><span class="sxs-lookup"><span data-stu-id="7e12d-2794">Three digits</span></span> 
- <span data-ttu-id="7e12d-2795">Uno spazio (facoltativo)</span><span class="sxs-lookup"><span data-stu-id="7e12d-2795">A space (optional)</span></span> 
- <span data-ttu-id="7e12d-2796">Tre cifre</span><span class="sxs-lookup"><span data-stu-id="7e12d-2796">Three digits</span></span> 
- <span data-ttu-id="7e12d-2797">Uno spazio (facoltativo)</span><span class="sxs-lookup"><span data-stu-id="7e12d-2797">A space (optional)</span></span> 
- <span data-ttu-id="7e12d-2798">2-3 cifre</span><span class="sxs-lookup"><span data-stu-id="7e12d-2798">2-3 digits</span></span>

### <a name="checksum"></a><span data-ttu-id="7e12d-2799">Checksum</span><span class="sxs-lookup"><span data-stu-id="7e12d-2799">Checksum</span></span>

<span data-ttu-id="7e12d-2800">Sì</span><span class="sxs-lookup"><span data-stu-id="7e12d-2800">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="7e12d-2801">Definizione</span><span class="sxs-lookup"><span data-stu-id="7e12d-2801">Definition</span></span>

<span data-ttu-id="7e12d-2802">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="7e12d-2802">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="7e12d-2803">La funzione Func_netherlands_bsn trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="7e12d-2803">The function Func_netherlands_bsn finds content that matches the pattern.</span></span>
- <span data-ttu-id="7e12d-2804">Viene trovata una parola chiave da Keyword_netherlands_bsn.</span><span class="sxs-lookup"><span data-stu-id="7e12d-2804">A keyword from Keyword_netherlands_bsn is found.</span></span>
- <span data-ttu-id="7e12d-2805">La funzione Func_eu_date2 rileva una data nel formato di data appropriato.</span><span class="sxs-lookup"><span data-stu-id="7e12d-2805">The function Func_eu_date2 finds a date in the right date format.</span></span>
- <span data-ttu-id="7e12d-2806">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="7e12d-2806">The checksum passes.</span></span>

```xml
<!-- Netherlands Citizen's Service (BSN) Number -->
<Entity id="c5f54253-ef7e-44f6-a578-440ed67e946d" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
       <IdMatch idRef="Func_netherlands_bsn" /> 
       <Match idRef="Keyword_netherlands_bsn" /> 
       <Match idRef="Func_eu_date2" /> 
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="7e12d-2807">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="7e12d-2807">Keywords</span></span>

#### <a name="keyword_netherlands_bsn"></a><span data-ttu-id="7e12d-2808">Keyword_netherlands_bsn</span><span class="sxs-lookup"><span data-stu-id="7e12d-2808">Keyword_netherlands_bsn</span></span>

- <span data-ttu-id="7e12d-2809">Numero di servizio cittadino</span><span class="sxs-lookup"><span data-stu-id="7e12d-2809">Citizen service number</span></span> 
- <span data-ttu-id="7e12d-2810">BSN</span><span class="sxs-lookup"><span data-stu-id="7e12d-2810">BSN</span></span> 
- <span data-ttu-id="7e12d-2811">Burgerservicenummer</span><span class="sxs-lookup"><span data-stu-id="7e12d-2811">Burgerservicenummer</span></span> 
- <span data-ttu-id="7e12d-2812">Sofinummer</span><span class="sxs-lookup"><span data-stu-id="7e12d-2812">Sofinummer</span></span> 
- <span data-ttu-id="7e12d-2813">Persoonsgebonden nummer</span><span class="sxs-lookup"><span data-stu-id="7e12d-2813">Persoonsgebonden nummer</span></span> 
- <span data-ttu-id="7e12d-2814">Persoonsnummer</span><span class="sxs-lookup"><span data-stu-id="7e12d-2814">Persoonsnummer</span></span>    

   
## <a name="new-zealand-ministry-of-health-number"></a><span data-ttu-id="7e12d-2815">Nuova Zelanda - Numero del Ministero della Sanità</span><span class="sxs-lookup"><span data-stu-id="7e12d-2815">New Zealand Ministry of Health Number</span></span>

### <a name="format"></a><span data-ttu-id="7e12d-2816">Formato</span><span class="sxs-lookup"><span data-stu-id="7e12d-2816">Format</span></span>

<span data-ttu-id="7e12d-2817">Tre lettere, uno spazio (facoltativo) e quattro cifre</span><span class="sxs-lookup"><span data-stu-id="7e12d-2817">Three letters, a space (optional), and four digits</span></span>

### <a name="pattern"></a><span data-ttu-id="7e12d-2818">Modello</span><span class="sxs-lookup"><span data-stu-id="7e12d-2818">Pattern</span></span>

<span data-ttu-id="7e12d-2819">Tre lettere (senza distinzione tra maiuscole/minuscole) uno spazio (facoltativo) quattro cifre</span><span class="sxs-lookup"><span data-stu-id="7e12d-2819">Three letters (not case sensitive) a space (optional) four digits</span></span>

### <a name="checksum"></a><span data-ttu-id="7e12d-2820">Checksum</span><span class="sxs-lookup"><span data-stu-id="7e12d-2820">Checksum</span></span>

<span data-ttu-id="7e12d-2821">Sì</span><span class="sxs-lookup"><span data-stu-id="7e12d-2821">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="7e12d-2822">Definizione</span><span class="sxs-lookup"><span data-stu-id="7e12d-2822">Definition</span></span>

<span data-ttu-id="7e12d-2823">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="7e12d-2823">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="7e12d-2824">La funzione Func_new_zealand_ministry_of_health_number restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="7e12d-2824">The function Func_new_zealand_ministry_of_health_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="7e12d-2825">Viene trovata una parola chiave da Keyword_nz_terms.</span><span class="sxs-lookup"><span data-stu-id="7e12d-2825">A keyword from Keyword_nz_terms is found.</span></span>
- <span data-ttu-id="7e12d-2826">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="7e12d-2826">The checksum passes.</span></span>

```xml
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

<span data-ttu-id="7e12d-2827">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="7e12d-2827">Keywords</span></span>

<span data-ttu-id="7e12d-2828">Keyword_nz_terms</span><span class="sxs-lookup"><span data-stu-id="7e12d-2828">Keyword_nz_terms</span></span>

- <span data-ttu-id="7e12d-2829">NHI</span><span class="sxs-lookup"><span data-stu-id="7e12d-2829">NHI</span></span> 
- <span data-ttu-id="7e12d-2830">New Zealand</span><span class="sxs-lookup"><span data-stu-id="7e12d-2830">New Zealand</span></span> 
- <span data-ttu-id="7e12d-2831">Integrità</span><span class="sxs-lookup"><span data-stu-id="7e12d-2831">Health</span></span> 
- <span data-ttu-id="7e12d-2832">trattamento</span><span class="sxs-lookup"><span data-stu-id="7e12d-2832">treatment</span></span> 
   
## <a name="norway-identification-number"></a><span data-ttu-id="7e12d-2833">Norvegia - Numero di identificazione
</span><span class="sxs-lookup"><span data-stu-id="7e12d-2833">Norway Identification Number</span></span>

### <a name="format"></a><span data-ttu-id="7e12d-2834">Formato</span><span class="sxs-lookup"><span data-stu-id="7e12d-2834">Format</span></span>

<span data-ttu-id="7e12d-2835">11 cifre</span><span class="sxs-lookup"><span data-stu-id="7e12d-2835">11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="7e12d-2836">Modello</span><span class="sxs-lookup"><span data-stu-id="7e12d-2836">Pattern</span></span>

<span data-ttu-id="7e12d-2837">11 cifre:</span><span class="sxs-lookup"><span data-stu-id="7e12d-2837">11 digits:</span></span>
- <span data-ttu-id="7e12d-2838">Sei cifre nel formato GGMMAA, ovvero la data di nascita</span><span class="sxs-lookup"><span data-stu-id="7e12d-2838">Six digits in the format DDMMYY which are the date of birth</span></span> 
- <span data-ttu-id="7e12d-2839">Numero individuale composto da tre cifre </span><span class="sxs-lookup"><span data-stu-id="7e12d-2839">Three-digit individual number</span></span> 
- <span data-ttu-id="7e12d-2840">Due cifre di controllo</span><span class="sxs-lookup"><span data-stu-id="7e12d-2840">Two check digits</span></span>

### <a name="checksum"></a><span data-ttu-id="7e12d-2841">Checksum</span><span class="sxs-lookup"><span data-stu-id="7e12d-2841">Checksum</span></span>

<span data-ttu-id="7e12d-2842">Sì</span><span class="sxs-lookup"><span data-stu-id="7e12d-2842">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="7e12d-2843">Definizione</span><span class="sxs-lookup"><span data-stu-id="7e12d-2843">Definition</span></span>

<span data-ttu-id="7e12d-2844">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="7e12d-2844">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="7e12d-2845">La funzione Func_norway_id_number trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="7e12d-2845">The function Func_norway_id_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="7e12d-2846">Viene trovata una parola chiave da Keyword_norway_id_number.</span><span class="sxs-lookup"><span data-stu-id="7e12d-2846">A keyword from Keyword_norway_id_number is found.</span></span>
- <span data-ttu-id="7e12d-2847">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="7e12d-2847">The checksum passes.</span></span>
- <span data-ttu-id="7e12d-2848">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="7e12d-2848">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="7e12d-2849">La funzione Func_norway_id_numbe trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="7e12d-2849">The function Func_norway_id_numbe finds content that matches the pattern.</span></span>
- <span data-ttu-id="7e12d-2850">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="7e12d-2850">The checksum passes.</span></span>

```xml
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

### <a name="keywords"></a><span data-ttu-id="7e12d-2851">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="7e12d-2851">Keywords</span></span>

#### <a name="keyword_norway_id_number"></a><span data-ttu-id="7e12d-2852">Keyword_norway_id_number</span><span class="sxs-lookup"><span data-stu-id="7e12d-2852">Keyword_norway_id_number</span></span>

- <span data-ttu-id="7e12d-2853">Codice PIN</span><span class="sxs-lookup"><span data-stu-id="7e12d-2853">Personal identification number</span></span>
- <span data-ttu-id="7e12d-2854">Numero ID norvegese</span><span class="sxs-lookup"><span data-stu-id="7e12d-2854">Norwegian ID Number</span></span>
- <span data-ttu-id="7e12d-2855">Numero ID
</span><span class="sxs-lookup"><span data-stu-id="7e12d-2855">ID Number</span></span>
- <span data-ttu-id="7e12d-2856">Identificazione</span><span class="sxs-lookup"><span data-stu-id="7e12d-2856">Identification</span></span>
- <span data-ttu-id="7e12d-2857">Personnummer</span><span class="sxs-lookup"><span data-stu-id="7e12d-2857">Personnummer</span></span>
- <span data-ttu-id="7e12d-2858">Fødselsnummer</span><span class="sxs-lookup"><span data-stu-id="7e12d-2858">Fødselsnummer</span></span>

   
## <a name="philippines-unified-multi-purpose-id-number"></a><span data-ttu-id="7e12d-2859">Filippine - Numero ID multifunzione unificato</span><span class="sxs-lookup"><span data-stu-id="7e12d-2859">Philippines Unified Multi-Purpose ID Number</span></span>

### <a name="format"></a><span data-ttu-id="7e12d-2860">Formato</span><span class="sxs-lookup"><span data-stu-id="7e12d-2860">Format</span></span>

<span data-ttu-id="7e12d-2861">12 cifre separate da dei segni meno</span><span class="sxs-lookup"><span data-stu-id="7e12d-2861">12 digits separated by hyphens</span></span>

### <a name="pattern"></a><span data-ttu-id="7e12d-2862">Modello</span><span class="sxs-lookup"><span data-stu-id="7e12d-2862">Pattern</span></span>

<span data-ttu-id="7e12d-2863">12 cifre:</span><span class="sxs-lookup"><span data-stu-id="7e12d-2863">12 digits:</span></span>
- <span data-ttu-id="7e12d-2864">Quattro cifre</span><span class="sxs-lookup"><span data-stu-id="7e12d-2864">Four digits</span></span> 
- <span data-ttu-id="7e12d-2865">Una lineetta</span><span class="sxs-lookup"><span data-stu-id="7e12d-2865">A hyphen</span></span> 
- <span data-ttu-id="7e12d-2866">Sette cifre</span><span class="sxs-lookup"><span data-stu-id="7e12d-2866">Seven digits</span></span> 
- <span data-ttu-id="7e12d-2867">Una lineetta</span><span class="sxs-lookup"><span data-stu-id="7e12d-2867">A hyphen</span></span> 
- <span data-ttu-id="7e12d-2868">Una cifra</span><span class="sxs-lookup"><span data-stu-id="7e12d-2868">One digit</span></span>

### <a name="checksum"></a><span data-ttu-id="7e12d-2869">Checksum</span><span class="sxs-lookup"><span data-stu-id="7e12d-2869">Checksum</span></span>

<span data-ttu-id="7e12d-2870">No</span><span class="sxs-lookup"><span data-stu-id="7e12d-2870">No</span></span>

### <a name="definition"></a><span data-ttu-id="7e12d-2871">Definizione</span><span class="sxs-lookup"><span data-stu-id="7e12d-2871">Definition</span></span>

<span data-ttu-id="7e12d-2872">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="7e12d-2872">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="7e12d-2873">L'espressione regolare Regex_philippines_unified_id trova il contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="7e12d-2873">The regular expression Regex_philippines_unified_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="7e12d-2874">Viene trovata una parola chiave da Keyword_philippines_id.</span><span class="sxs-lookup"><span data-stu-id="7e12d-2874">A keyword from Keyword_philippines_id is found.</span></span>

```xml
<!-- Philippines Unified Multi-Purpose ID number -->
<Entity id="019b39dd-8c25-4765-91a3-d9c6baf3c3b3" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_philippines_unified_id"/>
     <Match idRef="Keyword_philippines_id"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="7e12d-2875">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="7e12d-2875">Keywords</span></span>
   
#### <a name="keyword_philippines_id"></a><span data-ttu-id="7e12d-2876">Keyword_philippines_id</span><span class="sxs-lookup"><span data-stu-id="7e12d-2876">Keyword_philippines_id</span></span>

- <span data-ttu-id="7e12d-2877">ID multifunzione unificato</span><span class="sxs-lookup"><span data-stu-id="7e12d-2877">Unified Multi-Purpose ID</span></span> 
- <span data-ttu-id="7e12d-2878">UMID</span><span class="sxs-lookup"><span data-stu-id="7e12d-2878">UMID</span></span> 
- <span data-ttu-id="7e12d-2879">Carta di identità</span><span class="sxs-lookup"><span data-stu-id="7e12d-2879">Identity Card</span></span> 
- <span data-ttu-id="7e12d-2880">Pinag-isang Multi-Layunin ID</span><span class="sxs-lookup"><span data-stu-id="7e12d-2880">Pinag-isang Multi-Layunin ID</span></span>
   
## <a name="poland-identity-card"></a><span data-ttu-id="7e12d-2881">Carta di identita - Polonia</span><span class="sxs-lookup"><span data-stu-id="7e12d-2881">Poland Identity Card</span></span>

### <a name="format"></a><span data-ttu-id="7e12d-2882">Formato</span><span class="sxs-lookup"><span data-stu-id="7e12d-2882">Format</span></span>

<span data-ttu-id="7e12d-2883">Tre lettere e sei cifre</span><span class="sxs-lookup"><span data-stu-id="7e12d-2883">Three letters and six digits</span></span>

### <a name="pattern"></a><span data-ttu-id="7e12d-2884">Modello</span><span class="sxs-lookup"><span data-stu-id="7e12d-2884">Pattern</span></span>

<span data-ttu-id="7e12d-2885">Tre lettere (senza distinzione tra maiuscole/minuscole) seguite da sei cifre</span><span class="sxs-lookup"><span data-stu-id="7e12d-2885">Three letters (not case sensitive) followed by six digits</span></span>

### <a name="checksum"></a><span data-ttu-id="7e12d-2886">Checksum</span><span class="sxs-lookup"><span data-stu-id="7e12d-2886">Checksum</span></span>

<span data-ttu-id="7e12d-2887">Sì</span><span class="sxs-lookup"><span data-stu-id="7e12d-2887">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="7e12d-2888">Definizione</span><span class="sxs-lookup"><span data-stu-id="7e12d-2888">Definition</span></span>

<span data-ttu-id="7e12d-2889">Un criterio DLP è 75% fiducioso di aver rilevato questo tipo di informazioni riservate se, entro 300 caratteri: la funzione Func_polish_national_id trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="7e12d-2889">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The function Func_polish_national_id finds content that matches the pattern.</span></span>
<span data-ttu-id="7e12d-2890">Viene trovata una parola chiave da Keyword_polish_national_id_passport_number.</span><span class="sxs-lookup"><span data-stu-id="7e12d-2890">A keyword from Keyword_polish_national_id_passport_number is found.</span></span>
<span data-ttu-id="7e12d-2891">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="7e12d-2891">The checksum passes.</span></span>

```xml
<!-- Poland Identity Card-->
<Entity id="25E64989-ED5D-40CA-A939-6C14183BB7BF" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_polish_national_id" />
          <Match idRef="Keyword_polish_national_id_passport_number" />
      </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="7e12d-2892">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="7e12d-2892">Keywords</span></span>

#### <a name="keyword_polish_national_id_passport_number"></a><span data-ttu-id="7e12d-2893">Keyword_polish_national_id_passport_number</span><span class="sxs-lookup"><span data-stu-id="7e12d-2893">Keyword_polish_national_id_passport_number</span></span>

- <span data-ttu-id="7e12d-2894">Dowód osobisty</span><span class="sxs-lookup"><span data-stu-id="7e12d-2894">Dowód osobisty</span></span>
- <span data-ttu-id="7e12d-2895">Numero dowodu osobistego</span><span class="sxs-lookup"><span data-stu-id="7e12d-2895">Numer dowodu osobistego</span></span>
- <span data-ttu-id="7e12d-2896">Nazwa i numeri dowodu osobistego</span><span class="sxs-lookup"><span data-stu-id="7e12d-2896">Nazwa i numer dowodu osobistego</span></span>
- <span data-ttu-id="7e12d-2897">Nazwa i Nr dowodu osobistego</span><span class="sxs-lookup"><span data-stu-id="7e12d-2897">Nazwa i nr dowodu osobistego</span></span>
- <span data-ttu-id="7e12d-2898">Nazwa i nr dowodu tożsamości</span><span class="sxs-lookup"><span data-stu-id="7e12d-2898">Nazwa i nr dowodu tożsamości</span></span>
- <span data-ttu-id="7e12d-2899">Dowód Tożsamości</span><span class="sxs-lookup"><span data-stu-id="7e12d-2899">Dowód Tożsamości</span></span>
- <span data-ttu-id="7e12d-2900">Dow.</span><span class="sxs-lookup"><span data-stu-id="7e12d-2900">dow.</span></span> <span data-ttu-id="7e12d-2901">OS.</span><span class="sxs-lookup"><span data-stu-id="7e12d-2901">os.</span></span>

   
## <a name="poland-national-id-pesel"></a><span data-ttu-id="7e12d-2902">ID nazionale Polonia (PESEL)</span><span class="sxs-lookup"><span data-stu-id="7e12d-2902">Poland National ID (PESEL)</span></span>

### <a name="format"></a><span data-ttu-id="7e12d-2903">Formato</span><span class="sxs-lookup"><span data-stu-id="7e12d-2903">Format</span></span>

<span data-ttu-id="7e12d-2904">11 cifre</span><span class="sxs-lookup"><span data-stu-id="7e12d-2904">11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="7e12d-2905">Modello</span><span class="sxs-lookup"><span data-stu-id="7e12d-2905">Pattern</span></span>

<span data-ttu-id="7e12d-2906">11 cifre consecutive</span><span class="sxs-lookup"><span data-stu-id="7e12d-2906">11 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="7e12d-2907">Checksum</span><span class="sxs-lookup"><span data-stu-id="7e12d-2907">Checksum</span></span>

<span data-ttu-id="7e12d-2908">Sì</span><span class="sxs-lookup"><span data-stu-id="7e12d-2908">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="7e12d-2909">Definizione</span><span class="sxs-lookup"><span data-stu-id="7e12d-2909">Definition</span></span>

<span data-ttu-id="7e12d-2910">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="7e12d-2910">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="7e12d-2911">La funzione Func_pesel_identification_number restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="7e12d-2911">The function Func_pesel_identification_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="7e12d-2912">Viene trovata una parola chiave da Keyword_pesel_identification_number.</span><span class="sxs-lookup"><span data-stu-id="7e12d-2912">A keyword from Keyword_pesel_identification_number is found.</span></span>
- <span data-ttu-id="7e12d-2913">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="7e12d-2913">The checksum passes.</span></span>

```xml
<!-- Poland National ID (PESEL) -->      
<Entity id="E3AAF206-4297-412F-9E06-BA8487E22456" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_pesel_identification_number" />
          <Match idRef="Keyword_pesel_identification_number" />
      </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="7e12d-2914">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="7e12d-2914">Keywords</span></span>

#### <a name="keyword_pesel_identification_number"></a><span data-ttu-id="7e12d-2915">Keyword_pesel_identification_number</span><span class="sxs-lookup"><span data-stu-id="7e12d-2915">Keyword_pesel_identification_number</span></span>

- <span data-ttu-id="7e12d-2916">Nr PESEL</span><span class="sxs-lookup"><span data-stu-id="7e12d-2916">Nr PESEL</span></span>
- <span data-ttu-id="7e12d-2917">PESEL</span><span class="sxs-lookup"><span data-stu-id="7e12d-2917">PESEL</span></span>   

   
## <a name="poland-passport"></a><span data-ttu-id="7e12d-2918">Passaporto Polonia</span><span class="sxs-lookup"><span data-stu-id="7e12d-2918">Poland Passport</span></span>

### <a name="format"></a><span data-ttu-id="7e12d-2919">Formato</span><span class="sxs-lookup"><span data-stu-id="7e12d-2919">Format</span></span>

<span data-ttu-id="7e12d-2920">Due lettere e sette cifre</span><span class="sxs-lookup"><span data-stu-id="7e12d-2920">Two letters and seven digits</span></span>

### <a name="pattern"></a><span data-ttu-id="7e12d-2921">Modello</span><span class="sxs-lookup"><span data-stu-id="7e12d-2921">Pattern</span></span>

<span data-ttu-id="7e12d-2922">Due lettere (senza distinzione tra maiuscole/minuscole) seguite da sette cifre</span><span class="sxs-lookup"><span data-stu-id="7e12d-2922">Two letters (not case sensitive) followed by seven digits</span></span>

### <a name="checksum"></a><span data-ttu-id="7e12d-2923">Checksum</span><span class="sxs-lookup"><span data-stu-id="7e12d-2923">Checksum</span></span>

<span data-ttu-id="7e12d-2924">Sì</span><span class="sxs-lookup"><span data-stu-id="7e12d-2924">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="7e12d-2925">Definizione</span><span class="sxs-lookup"><span data-stu-id="7e12d-2925">Definition</span></span>

<span data-ttu-id="7e12d-2926">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="7e12d-2926">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="7e12d-2927">La funzione Func_polish_passport_number restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="7e12d-2927">The function Func_polish_passport_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="7e12d-2928">Viene trovata una parola chiave da Keyword_polish_national_id_passport_number.</span><span class="sxs-lookup"><span data-stu-id="7e12d-2928">A keyword from Keyword_polish_national_id_passport_number is found.</span></span>
- <span data-ttu-id="7e12d-2929">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="7e12d-2929">The checksum passes.</span></span>

```xml
<!-- Poland Passport Number -->
<Entity id="03937FB5-D2B6-4487-B61F-0F8BFF7C3517" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_polish_passport_number" />
          <Match idRef="Keyword_polish_national_id_passport_number" />
      </Pattern>
</Entity>
</Version>
```

### <a name="keywords"></a><span data-ttu-id="7e12d-2930">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="7e12d-2930">Keywords</span></span>

#### <a name="keyword_polish_national_id_passport_number"></a><span data-ttu-id="7e12d-2931">Keyword_polish_national_id_passport_number</span><span class="sxs-lookup"><span data-stu-id="7e12d-2931">Keyword_polish_national_id_passport_number</span></span>

- <span data-ttu-id="7e12d-2932">Numero Paszportu</span><span class="sxs-lookup"><span data-stu-id="7e12d-2932">Numer paszportu</span></span>
- <span data-ttu-id="7e12d-2933">Nr.</span><span class="sxs-lookup"><span data-stu-id="7e12d-2933">Nr.</span></span> <span data-ttu-id="7e12d-2934">Paszportu</span><span class="sxs-lookup"><span data-stu-id="7e12d-2934">Paszportu</span></span>
- <span data-ttu-id="7e12d-2935">Paszport</span><span class="sxs-lookup"><span data-stu-id="7e12d-2935">Paszport</span></span>

   
## <a name="portugal-citizen-card-number"></a><span data-ttu-id="7e12d-2936">Portogallo - Numero di carta del cittadino</span><span class="sxs-lookup"><span data-stu-id="7e12d-2936">Portugal Citizen Card Number</span></span>

### <a name="format"></a><span data-ttu-id="7e12d-2937">Formato</span><span class="sxs-lookup"><span data-stu-id="7e12d-2937">Format</span></span>

<span data-ttu-id="7e12d-2938">Otto cifre</span><span class="sxs-lookup"><span data-stu-id="7e12d-2938">Eight digits</span></span>

### <a name="pattern"></a><span data-ttu-id="7e12d-2939">Modello</span><span class="sxs-lookup"><span data-stu-id="7e12d-2939">Pattern</span></span>

<span data-ttu-id="7e12d-2940">Otto cifre</span><span class="sxs-lookup"><span data-stu-id="7e12d-2940">Eight digits</span></span>

### <a name="checksum"></a><span data-ttu-id="7e12d-2941">Checksum</span><span class="sxs-lookup"><span data-stu-id="7e12d-2941">Checksum</span></span>

<span data-ttu-id="7e12d-2942">No</span><span class="sxs-lookup"><span data-stu-id="7e12d-2942">No</span></span>

### <a name="definition"></a><span data-ttu-id="7e12d-2943">Definizione</span><span class="sxs-lookup"><span data-stu-id="7e12d-2943">Definition</span></span>

<span data-ttu-id="7e12d-2944">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="7e12d-2944">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="7e12d-2945">L'espressione regolare Regex_portugal_citizen_card trova il contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="7e12d-2945">The regular expression Regex_portugal_citizen_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="7e12d-2946">Viene trovata una parola chiave da Keyword_portugal_citizen_card.</span><span class="sxs-lookup"><span data-stu-id="7e12d-2946">A keyword from Keyword_portugal_citizen_card is found.</span></span>

```xml
<!-- Portugal Citizen Card Number -->
<Entity id="91a7ece2-add4-4986-9a15-c84544d81ecd" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Regex_portugal_citizen_card"/>
     <Match idRef="Keyword_portugal_citizen_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="7e12d-2947">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="7e12d-2947">Keywords</span></span>

#### <a name="keyword_portugal_citizen_card"></a><span data-ttu-id="7e12d-2948">Keyword_portugal_citizen_card</span><span class="sxs-lookup"><span data-stu-id="7e12d-2948">Keyword_portugal_citizen_card</span></span>

- <span data-ttu-id="7e12d-2949">Scheda cittadino</span><span class="sxs-lookup"><span data-stu-id="7e12d-2949">Citizen Card</span></span>
- <span data-ttu-id="7e12d-2950">Carta ID</span><span class="sxs-lookup"><span data-stu-id="7e12d-2950">National ID Card</span></span>
- <span data-ttu-id="7e12d-2951">CC</span><span class="sxs-lookup"><span data-stu-id="7e12d-2951">CC</span></span>
- <span data-ttu-id="7e12d-2952">Cartão de Cidadão</span><span class="sxs-lookup"><span data-stu-id="7e12d-2952">Cartão de Cidadão</span></span>
- <span data-ttu-id="7e12d-2953">Bilhete de Identidade</span><span class="sxs-lookup"><span data-stu-id="7e12d-2953">Bilhete de Identidade</span></span>
   
## <a name="saudi-arabia-national-id"></a><span data-ttu-id="7e12d-2954">Arabia Saudita - Identificativo nazionale</span><span class="sxs-lookup"><span data-stu-id="7e12d-2954">Saudi Arabia National ID</span></span>

### <a name="format"></a><span data-ttu-id="7e12d-2955">Formato</span><span class="sxs-lookup"><span data-stu-id="7e12d-2955">Format</span></span>

<span data-ttu-id="7e12d-2956">10 cifre</span><span class="sxs-lookup"><span data-stu-id="7e12d-2956">10 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="7e12d-2957">Modello</span><span class="sxs-lookup"><span data-stu-id="7e12d-2957">Pattern</span></span>

<span data-ttu-id="7e12d-2958">10 cifre consecutive</span><span class="sxs-lookup"><span data-stu-id="7e12d-2958">10 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="7e12d-2959">Checksum</span><span class="sxs-lookup"><span data-stu-id="7e12d-2959">Checksum</span></span>

<span data-ttu-id="7e12d-2960">No</span><span class="sxs-lookup"><span data-stu-id="7e12d-2960">No</span></span>

### <a name="definition"></a><span data-ttu-id="7e12d-2961">Definizione</span><span class="sxs-lookup"><span data-stu-id="7e12d-2961">Definition</span></span>

<span data-ttu-id="7e12d-2962">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="7e12d-2962">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="7e12d-2963">L'espressione regolare Regex_saudi_arabia_national_id restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="7e12d-2963">The regular expression Regex_saudi_arabia_national_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="7e12d-2964">Viene trovata una parola chiave da Keyword_saudi_arabia_national_id.</span><span class="sxs-lookup"><span data-stu-id="7e12d-2964">A keyword from Keyword_saudi_arabia_national_id is found.</span></span>

```xml
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

### <a name="keywords"></a><span data-ttu-id="7e12d-2965">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="7e12d-2965">Keywords</span></span>

#### <a name="keyword_saudi_arabia_national_id"></a><span data-ttu-id="7e12d-2966">Keyword_saudi_arabia_national_id</span><span class="sxs-lookup"><span data-stu-id="7e12d-2966">Keyword_saudi_arabia_national_id</span></span>

- <span data-ttu-id="7e12d-2967">Identification Card</span><span class="sxs-lookup"><span data-stu-id="7e12d-2967">Identification Card</span></span> 
- <span data-ttu-id="7e12d-2968">I card number</span><span class="sxs-lookup"><span data-stu-id="7e12d-2968">I card number</span></span> 
- <span data-ttu-id="7e12d-2969">ID number</span><span class="sxs-lookup"><span data-stu-id="7e12d-2969">ID number</span></span> 
- <span data-ttu-id="7e12d-2970">الوطنية الهوية بطاقة رقم</span><span class="sxs-lookup"><span data-stu-id="7e12d-2970">الوطنية الهوية بطاقة رقم</span></span> 

   
## <a name="singapore-national-registration-identity-card-nric-number"></a><span data-ttu-id="7e12d-2971">Singapore - Numero di carta di identità di registrazione nazionale (NRIC)</span><span class="sxs-lookup"><span data-stu-id="7e12d-2971">Singapore National Registration Identity Card (NRIC) Number</span></span>

### <a name="format"></a><span data-ttu-id="7e12d-2972">Formato</span><span class="sxs-lookup"><span data-stu-id="7e12d-2972">Format</span></span>

<span data-ttu-id="7e12d-2973">Nove lettere e numeri</span><span class="sxs-lookup"><span data-stu-id="7e12d-2973">Nine letters and digits</span></span>

### <a name="pattern"></a><span data-ttu-id="7e12d-2974">Modello</span><span class="sxs-lookup"><span data-stu-id="7e12d-2974">Pattern</span></span>

- <span data-ttu-id="7e12d-2975">Nove lettere e numeri:</span><span class="sxs-lookup"><span data-stu-id="7e12d-2975">Nine letters and digits:</span></span>
- <span data-ttu-id="7e12d-2976">La lettera "F", "G", "S" o "T" (senza distinzione tra maiuscole e minuscole) </span><span class="sxs-lookup"><span data-stu-id="7e12d-2976">The letter "F", "G", "S", or "T" (not case sensitive)</span></span> 
- <span data-ttu-id="7e12d-2977">Sette cifre</span><span class="sxs-lookup"><span data-stu-id="7e12d-2977">Seven digits</span></span> 
- <span data-ttu-id="7e12d-2978">Una cifra di controllo alfabetica</span><span class="sxs-lookup"><span data-stu-id="7e12d-2978">An alphabetic check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="7e12d-2979">Checksum</span><span class="sxs-lookup"><span data-stu-id="7e12d-2979">Checksum</span></span>

<span data-ttu-id="7e12d-2980">Sì</span><span class="sxs-lookup"><span data-stu-id="7e12d-2980">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="7e12d-2981">Definizione</span><span class="sxs-lookup"><span data-stu-id="7e12d-2981">Definition</span></span>

<span data-ttu-id="7e12d-2982">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="7e12d-2982">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="7e12d-2983">L'espressione regolare Regex_singapore_nric trova il contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="7e12d-2983">The regular expression Regex_singapore_nric finds content that matches the pattern.</span></span>
- <span data-ttu-id="7e12d-2984">Viene trovata una parola chiave da Keyword_singapore_nric.</span><span class="sxs-lookup"><span data-stu-id="7e12d-2984">A keyword from Keyword_singapore_nric is found.</span></span>
- <span data-ttu-id="7e12d-2985">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="7e12d-2985">The checksum passes.</span></span>

<span data-ttu-id="7e12d-2986">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="7e12d-2986">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="7e12d-2987">L'espressione regolare Regex_singapore_nric trova il contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="7e12d-2987">The regular expression Regex_singapore_nric finds content that matches the pattern.</span></span>
- <span data-ttu-id="7e12d-2988">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="7e12d-2988">The checksum passes.</span></span>

```xml
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

### <a name="keywords"></a><span data-ttu-id="7e12d-2989">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="7e12d-2989">Keywords</span></span>
   
#### <a name="keyword_singapore_nric"></a><span data-ttu-id="7e12d-2990">Keyword_singapore_nric</span><span class="sxs-lookup"><span data-stu-id="7e12d-2990">Keyword_singapore_nric</span></span>

- <span data-ttu-id="7e12d-2991">Carta di identità di registrazione nazionale</span><span class="sxs-lookup"><span data-stu-id="7e12d-2991">National Registration Identity Card</span></span> 
- <span data-ttu-id="7e12d-2992">Numero di carta di identità</span><span class="sxs-lookup"><span data-stu-id="7e12d-2992">Identity Card Number</span></span> 
- <span data-ttu-id="7e12d-2993">NRIC</span><span class="sxs-lookup"><span data-stu-id="7e12d-2993">NRIC</span></span> 
- <span data-ttu-id="7e12d-2994">IC</span><span class="sxs-lookup"><span data-stu-id="7e12d-2994">IC</span></span> 
- <span data-ttu-id="7e12d-2995">Numero di identificazione per stranieri</span><span class="sxs-lookup"><span data-stu-id="7e12d-2995">Foreign Identification Number</span></span> 
- <span data-ttu-id="7e12d-2996">FIN</span><span class="sxs-lookup"><span data-stu-id="7e12d-2996">FIN</span></span> 
- <span data-ttu-id="7e12d-2997">身份证</span><span class="sxs-lookup"><span data-stu-id="7e12d-2997">身份证</span></span> 
- <span data-ttu-id="7e12d-2998">身份證</span><span class="sxs-lookup"><span data-stu-id="7e12d-2998">身份證</span></span> 
   
## <a name="south-africa-identification-number"></a><span data-ttu-id="7e12d-2999">Sudafrica - Numero di identificazione
</span><span class="sxs-lookup"><span data-stu-id="7e12d-2999">South Africa Identification Number</span></span>

### <a name="format"></a><span data-ttu-id="7e12d-3000">Formato</span><span class="sxs-lookup"><span data-stu-id="7e12d-3000">Format</span></span>

<span data-ttu-id="7e12d-3001">13 cifre che possono contenere spazi</span><span class="sxs-lookup"><span data-stu-id="7e12d-3001">13 digits that may contain spaces</span></span>

### <a name="pattern"></a><span data-ttu-id="7e12d-3002">Modello</span><span class="sxs-lookup"><span data-stu-id="7e12d-3002">Pattern</span></span>

<span data-ttu-id="7e12d-3003">13 cifre:</span><span class="sxs-lookup"><span data-stu-id="7e12d-3003">13 digits:</span></span>
- <span data-ttu-id="7e12d-3004">Sei cifre nel formato AAMMGG, ovvero la data di nascita</span><span class="sxs-lookup"><span data-stu-id="7e12d-3004">Six digits in the format YYMMDD which are the date of birth</span></span> 
- <span data-ttu-id="7e12d-3005">Quattro cifre</span><span class="sxs-lookup"><span data-stu-id="7e12d-3005">Four digits</span></span> 
- <span data-ttu-id="7e12d-3006">Un indicatore di cittadinanza a una cifra </span><span class="sxs-lookup"><span data-stu-id="7e12d-3006">A single-digit citizenship indicator</span></span> 
- <span data-ttu-id="7e12d-3007">La cifra "8" o "9" </span><span class="sxs-lookup"><span data-stu-id="7e12d-3007">The digit "8" or "9"</span></span> 
- <span data-ttu-id="7e12d-3008">Una cifra, ovvero una cifra di checksum</span><span class="sxs-lookup"><span data-stu-id="7e12d-3008">One digit which is a checksum digit</span></span>

### <a name="checksum"></a><span data-ttu-id="7e12d-3009">Checksum</span><span class="sxs-lookup"><span data-stu-id="7e12d-3009">Checksum</span></span>

<span data-ttu-id="7e12d-3010">Sì</span><span class="sxs-lookup"><span data-stu-id="7e12d-3010">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="7e12d-3011">Definizione</span><span class="sxs-lookup"><span data-stu-id="7e12d-3011">Definition</span></span>

<span data-ttu-id="7e12d-3012">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="7e12d-3012">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="7e12d-3013">La funzione Func_south_africa_identification_number trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="7e12d-3013">The function Func_south_africa_identification_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="7e12d-3014">Viene trovata una parola chiave da Keyword_south_africa_identification_number.</span><span class="sxs-lookup"><span data-stu-id="7e12d-3014">A keyword from Keyword_south_africa_identification_number is found.</span></span>
- <span data-ttu-id="7e12d-3015">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="7e12d-3015">The checksum passes.</span></span>

```xml
<!-- South Africa Identification Number -->
<Entity id="e2adf7cb-8ea6-4048-a2ed-d89eb65f2780" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_south_africa_identification_number"/>
     <Match idRef="Keyword_south_africa_identification_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="7e12d-3016">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="7e12d-3016">Keywords</span></span>
   
#### <a name="keyword_south_africa_identification_number"></a><span data-ttu-id="7e12d-3017">Keyword_south_africa_identification_number</span><span class="sxs-lookup"><span data-stu-id="7e12d-3017">Keyword_south_africa_identification_number</span></span>

- <span data-ttu-id="7e12d-3018">Carta di identità</span><span class="sxs-lookup"><span data-stu-id="7e12d-3018">Identity card</span></span>
- <span data-ttu-id="7e12d-3019">ID</span><span class="sxs-lookup"><span data-stu-id="7e12d-3019">ID</span></span>
- <span data-ttu-id="7e12d-3020">Identificazione</span><span class="sxs-lookup"><span data-stu-id="7e12d-3020">Identification</span></span> 
   
## <a name="south-korea-resident-registration-number"></a><span data-ttu-id="7e12d-3021">Corea del Sud - Numero di registrazione dei residenti</span><span class="sxs-lookup"><span data-stu-id="7e12d-3021">South Korea Resident Registration Number</span></span>

### <a name="format"></a><span data-ttu-id="7e12d-3022">Formato</span><span class="sxs-lookup"><span data-stu-id="7e12d-3022">Format</span></span>

<span data-ttu-id="7e12d-3023">13 cifre contenenti un segno meno</span><span class="sxs-lookup"><span data-stu-id="7e12d-3023">13 digits containing a hyphen</span></span>

### <a name="pattern"></a><span data-ttu-id="7e12d-3024">Modello</span><span class="sxs-lookup"><span data-stu-id="7e12d-3024">Pattern</span></span>

<span data-ttu-id="7e12d-3025">13 cifre:</span><span class="sxs-lookup"><span data-stu-id="7e12d-3025">13 digits:</span></span>
- <span data-ttu-id="7e12d-3026">Sei cifre nel formato AAMMGG, ovvero la data di nascita</span><span class="sxs-lookup"><span data-stu-id="7e12d-3026">Six digits in the format YYMMDD which are the date of birth</span></span> 
- <span data-ttu-id="7e12d-3027">Una lineetta</span><span class="sxs-lookup"><span data-stu-id="7e12d-3027">A hyphen</span></span> 
- <span data-ttu-id="7e12d-3028">Una cifra determinata dal secolo e dal sesso </span><span class="sxs-lookup"><span data-stu-id="7e12d-3028">One digit determined by the century and gender</span></span> 
- <span data-ttu-id="7e12d-3029">Codice di quattro cifre dell’area geografica di nascita </span><span class="sxs-lookup"><span data-stu-id="7e12d-3029">Four-digit region-of-birth code</span></span> 
- <span data-ttu-id="7e12d-3030">Una cifra utilizzata per distinguere persone i cui numeri precedenti sono uguali </span><span class="sxs-lookup"><span data-stu-id="7e12d-3030">One digit used to differentiate people for whom the preceding numbers are identical</span></span> 
- <span data-ttu-id="7e12d-3031">Una cifra di controllo.</span><span class="sxs-lookup"><span data-stu-id="7e12d-3031">A check digit.</span></span>

### <a name="checksum"></a><span data-ttu-id="7e12d-3032">Checksum</span><span class="sxs-lookup"><span data-stu-id="7e12d-3032">Checksum</span></span>

<span data-ttu-id="7e12d-3033">Sì</span><span class="sxs-lookup"><span data-stu-id="7e12d-3033">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="7e12d-3034">Definizione</span><span class="sxs-lookup"><span data-stu-id="7e12d-3034">Definition</span></span>

<span data-ttu-id="7e12d-3035">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="7e12d-3035">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="7e12d-3036">La funzione Func_south_korea_resident_number trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="7e12d-3036">The function Func_south_korea_resident_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="7e12d-3037">Viene trovata una parola chiave da Keyword_south_korea_resident_number.</span><span class="sxs-lookup"><span data-stu-id="7e12d-3037">A keyword from Keyword_south_korea_resident_number is found.</span></span>
- <span data-ttu-id="7e12d-3038">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="7e12d-3038">The checksum passes.</span></span>

<span data-ttu-id="7e12d-3039">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="7e12d-3039">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="7e12d-3040">La funzione Func_south_korea_resident_number trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="7e12d-3040">The function Func_south_korea_resident_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="7e12d-3041">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="7e12d-3041">The checksum passes.</span></span>

```xml
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

### <a name="keywords"></a><span data-ttu-id="7e12d-3042">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="7e12d-3042">Keywords</span></span>
   
#### <a name="keyword_south_korea_resident_number"></a><span data-ttu-id="7e12d-3043">Keyword_south_korea_resident_number</span><span class="sxs-lookup"><span data-stu-id="7e12d-3043">Keyword_south_korea_resident_number</span></span>

- <span data-ttu-id="7e12d-3044">Carta di identità</span><span class="sxs-lookup"><span data-stu-id="7e12d-3044">National ID card</span></span> 
- <span data-ttu-id="7e12d-3045">Numero di registrazione del cittadino</span><span class="sxs-lookup"><span data-stu-id="7e12d-3045">Citizen's Registration Number</span></span> 
- <span data-ttu-id="7e12d-3046">Jumin deungnok beonho</span><span class="sxs-lookup"><span data-stu-id="7e12d-3046">Jumin deungnok beonho</span></span> 
- <span data-ttu-id="7e12d-3047">RRN</span><span class="sxs-lookup"><span data-stu-id="7e12d-3047">RRN</span></span> 
- <span data-ttu-id="7e12d-3048">주민등록번호</span><span class="sxs-lookup"><span data-stu-id="7e12d-3048">주민등록번호</span></span>
   
## <a name="spain-social-security-number-ssn"></a><span data-ttu-id="7e12d-3049">Spagna - Numero di previdenza sociale (SSN)</span><span class="sxs-lookup"><span data-stu-id="7e12d-3049">Spain Social Security Number (SSN)</span></span>

### <a name="format"></a><span data-ttu-id="7e12d-3050">Formato</span><span class="sxs-lookup"><span data-stu-id="7e12d-3050">Format</span></span>

<span data-ttu-id="7e12d-3051">11-12 cifre</span><span class="sxs-lookup"><span data-stu-id="7e12d-3051">11-12 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="7e12d-3052">Modello</span><span class="sxs-lookup"><span data-stu-id="7e12d-3052">Pattern</span></span>

<span data-ttu-id="7e12d-3053">11-12 cifre:</span><span class="sxs-lookup"><span data-stu-id="7e12d-3053">11-12 digits:</span></span>
- <span data-ttu-id="7e12d-3054">Due cifre</span><span class="sxs-lookup"><span data-stu-id="7e12d-3054">Two digits</span></span> 
- <span data-ttu-id="7e12d-3055">Una barra (facoltativa)</span><span class="sxs-lookup"><span data-stu-id="7e12d-3055">A forward slash (optional)</span></span> 
- <span data-ttu-id="7e12d-3056">7-8 cifre</span><span class="sxs-lookup"><span data-stu-id="7e12d-3056">7-8 digits</span></span> 
- <span data-ttu-id="7e12d-3057">Una barra (facoltativa)</span><span class="sxs-lookup"><span data-stu-id="7e12d-3057">A forward slash (optional)</span></span> 
- <span data-ttu-id="7e12d-3058">Due cifre</span><span class="sxs-lookup"><span data-stu-id="7e12d-3058">Two digits</span></span>

### <a name="checksum"></a><span data-ttu-id="7e12d-3059">Checksum</span><span class="sxs-lookup"><span data-stu-id="7e12d-3059">Checksum</span></span>

<span data-ttu-id="7e12d-3060">Sì</span><span class="sxs-lookup"><span data-stu-id="7e12d-3060">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="7e12d-3061">Definizione</span><span class="sxs-lookup"><span data-stu-id="7e12d-3061">Definition</span></span>

<span data-ttu-id="7e12d-3062">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="7e12d-3062">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="7e12d-3063">La funzione Func_spanish_social_security_number restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="7e12d-3063">The function Func_spanish_social_security_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="7e12d-3064">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="7e12d-3064">The checksum passes.</span></span>

```xml
<!-- Spain SSN -->
<Entity id="5df987c0-8eae-4bce-ace7-b316347f3070" patternsProximity="300" recommendedConfidence="85">
    <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_spanish_social_security_number" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="7e12d-3065">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="7e12d-3065">Keywords</span></span>

<span data-ttu-id="7e12d-3066">Nessuno</span><span class="sxs-lookup"><span data-stu-id="7e12d-3066">None</span></span>

## <a name="sql-server-connection-string"></a><span data-ttu-id="7e12d-3067">Stringa di connessione di SQL Server</span><span class="sxs-lookup"><span data-stu-id="7e12d-3067">SQL Server Connection String</span></span>

### <a name="format"></a><span data-ttu-id="7e12d-3068">Formato</span><span class="sxs-lookup"><span data-stu-id="7e12d-3068">Format</span></span>

<span data-ttu-id="7e12d-3069">Stringa "ID utente", "ID utente", "UID" o "UserId" seguito dai caratteri e dalle stringhe delineati nel modello seguente.</span><span class="sxs-lookup"><span data-stu-id="7e12d-3069">The string "User Id", "User ID", "uid", or "UserId" followed by the characters and strings outlined in the pattern below.</span></span>

### <a name="pattern"></a><span data-ttu-id="7e12d-3070">Modello</span><span class="sxs-lookup"><span data-stu-id="7e12d-3070">Pattern</span></span>

- <span data-ttu-id="7e12d-3071">Stringa "ID utente", "ID utente", "UID" o "UserId"</span><span class="sxs-lookup"><span data-stu-id="7e12d-3071">The string "User Id", "User ID", "uid", or "UserId"</span></span>
- <span data-ttu-id="7e12d-3072">Qualsiasi combinazione tra 1-200 lettere, cifre, simboli, caratteri speciali o spazi in maiuscolo o minuscolo</span><span class="sxs-lookup"><span data-stu-id="7e12d-3072">Any combination of between 1-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="7e12d-3073">La stringa "password" o "pwd", dove "pwd" non è preceduta da una lettera minuscola</span><span class="sxs-lookup"><span data-stu-id="7e12d-3073">The string "Password" or "pwd" where "pwd" is not preceded by a lowercase letter</span></span>
- <span data-ttu-id="7e12d-3074">Segno di uguale (=)</span><span class="sxs-lookup"><span data-stu-id="7e12d-3074">An equal sign (=)</span></span>
- <span data-ttu-id="7e12d-3075">Qualsiasi carattere che non sia un segno di dollaro ($), un simbolo di percentuale (%), un simbolo maggiore di (>), il simbolo (@), le virgolette ("), il punto e virgola (;), parentesi graffa sinistra ([) o parentesi quadra sinistra ({)</span><span class="sxs-lookup"><span data-stu-id="7e12d-3075">Any character that is not a dollar sign ($), percent symbol (%), greater than symbol (>), at symbol (@), quotation mark ("), semicolon (;), left brace ([), or left bracket ({)</span></span>
- <span data-ttu-id="7e12d-3076">Qualsiasi combinazione di 7-128 caratteri che non sono un punto e virgola (;), barra (/) o virgolette (")</span><span class="sxs-lookup"><span data-stu-id="7e12d-3076">Any combination of 7-128 characters that are not a semicolon (;), forward slash (/), or quotation mark (")</span></span>
- <span data-ttu-id="7e12d-3077">Un punto e virgola (;) o virgolette (")</span><span class="sxs-lookup"><span data-stu-id="7e12d-3077">A semicolon (;) or quotation mark (")</span></span>

### <a name="checksum"></a><span data-ttu-id="7e12d-3078">Checksum</span><span class="sxs-lookup"><span data-stu-id="7e12d-3078">Checksum</span></span>

<span data-ttu-id="7e12d-3079">No</span><span class="sxs-lookup"><span data-stu-id="7e12d-3079">No</span></span>

### <a name="definition"></a><span data-ttu-id="7e12d-3080">Definizione</span><span class="sxs-lookup"><span data-stu-id="7e12d-3080">Definition</span></span>

<span data-ttu-id="7e12d-3081">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="7e12d-3081">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="7e12d-3082">L'espressione regolare CEP_Regex_SQLServerConnectionString trova il contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="7e12d-3082">The regular expression CEP_Regex_SQLServerConnectionString finds content that matches the pattern.</span></span>
- <span data-ttu-id="7e12d-3083">**Non** viene trovata una parola chiave da CEP_GlobalFilter.</span><span class="sxs-lookup"><span data-stu-id="7e12d-3083">A keyword from CEP_GlobalFilter is **not** found.</span></span>
- <span data-ttu-id="7e12d-3084">L'espressione regolare CEP_PasswordPlaceHolder non \*\*\*\* trova contenuto corrispondente al modello.</span><span class="sxs-lookup"><span data-stu-id="7e12d-3084">The regular expression CEP_PasswordPlaceHolder does **not** find content that matches the pattern.</span></span>
- <span data-ttu-id="7e12d-3085">L'espressione regolare CEP_CommonExampleKeywords non \*\*\*\* trova contenuto corrispondente al modello.</span><span class="sxs-lookup"><span data-stu-id="7e12d-3085">The regular expression CEP_CommonExampleKeywords does **not** find content that matches the pattern.</span></span>

```sql
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

### <a name="keywords"></a><span data-ttu-id="7e12d-3086">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="7e12d-3086">Keywords</span></span>

#### <a name="cep_globalfilter"></a><span data-ttu-id="7e12d-3087">CEP_GlobalFilter</span><span class="sxs-lookup"><span data-stu-id="7e12d-3087">CEP_GlobalFilter</span></span>

- <span data-ttu-id="7e12d-3088">some-password</span><span class="sxs-lookup"><span data-stu-id="7e12d-3088">some-password</span></span>
- <span data-ttu-id="7e12d-3089">somepassword</span><span class="sxs-lookup"><span data-stu-id="7e12d-3089">somepassword</span></span>
- <span data-ttu-id="7e12d-3090">secretPassword</span><span class="sxs-lookup"><span data-stu-id="7e12d-3090">secretPassword</span></span>
- <span data-ttu-id="7e12d-3091">esempio</span><span class="sxs-lookup"><span data-stu-id="7e12d-3091">sample</span></span>

#### <a name="cep_passwordplaceholder"></a><span data-ttu-id="7e12d-3092">CEP_PasswordPlaceHolder</span><span class="sxs-lookup"><span data-stu-id="7e12d-3092">CEP_PasswordPlaceHolder</span></span>

<span data-ttu-id="7e12d-3093">Si noti che tecnicamente questo tipo di informazioni riservate identifica queste parole chiave utilizzando un'espressione regolare, non un elenco di parola chiave.</span><span class="sxs-lookup"><span data-stu-id="7e12d-3093">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="7e12d-3094">Password o pwd seguito da 0-2 spazi, un segno di uguale (=), 0-2 spazi e un asterisco (\*)-----------------</span><span class="sxs-lookup"><span data-stu-id="7e12d-3094">Password or pwd followed by 0-2 spaces, an equal sign (=), 0-2 spaces, and an asterisk (\*) --OR--</span></span>
- <span data-ttu-id="7e12d-3095">Password o pwd seguito da:</span><span class="sxs-lookup"><span data-stu-id="7e12d-3095">Password or pwd followed by:</span></span>
    - <span data-ttu-id="7e12d-3096">Segno di uguale (=)</span><span class="sxs-lookup"><span data-stu-id="7e12d-3096">Equal sign (=)</span></span>
    - <span data-ttu-id="7e12d-3097">Meno di simbolo (<)</span><span class="sxs-lookup"><span data-stu-id="7e12d-3097">Less than symbol (<)</span></span>
    - <span data-ttu-id="7e12d-3098">Qualsiasi combinazione di 1-200 caratteri che sono lettere maiuscole o minuscole, cifre, asterisco (\*), segno meno (-), sottolineatura (_) o carattere dello spazio vuoto</span><span class="sxs-lookup"><span data-stu-id="7e12d-3098">Any combination of 1-200 characters that are upper- or lowercase letters, digits, an asterisk (\*), hyphen (-), underline (_), or whitespace character</span></span>
    - <span data-ttu-id="7e12d-3099">Valore maggiore di Symbol (>)</span><span class="sxs-lookup"><span data-stu-id="7e12d-3099">Greater than symbol (>)</span></span>

#### <a name="cep_commonexamplekeywords"></a><span data-ttu-id="7e12d-3100">CEP_CommonExampleKeywords</span><span class="sxs-lookup"><span data-stu-id="7e12d-3100">CEP_CommonExampleKeywords</span></span>

<span data-ttu-id="7e12d-3101">Si noti che tecnicamente questo tipo di informazioni riservate identifica queste parole chiave utilizzando un'espressione regolare, non un elenco di parola chiave.</span><span class="sxs-lookup"><span data-stu-id="7e12d-3101">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="7e12d-3102">contoso</span><span class="sxs-lookup"><span data-stu-id="7e12d-3102">contoso</span></span>
- <span data-ttu-id="7e12d-3103">Fabrikam</span><span class="sxs-lookup"><span data-stu-id="7e12d-3103">fabrikam</span></span>
- <span data-ttu-id="7e12d-3104">Northwind</span><span class="sxs-lookup"><span data-stu-id="7e12d-3104">northwind</span></span>
- <span data-ttu-id="7e12d-3105">sandbox</span><span class="sxs-lookup"><span data-stu-id="7e12d-3105">sandbox</span></span>
- <span data-ttu-id="7e12d-3106">OneBox</span><span class="sxs-lookup"><span data-stu-id="7e12d-3106">onebox</span></span>
- <span data-ttu-id="7e12d-3107">localhost</span><span class="sxs-lookup"><span data-stu-id="7e12d-3107">localhost</span></span>
- <span data-ttu-id="7e12d-3108">127.0.0.1</span><span class="sxs-lookup"><span data-stu-id="7e12d-3108">127.0.0.1</span></span>
- <span data-ttu-id="7e12d-3109">testacs.</span><span class="sxs-lookup"><span data-stu-id="7e12d-3109">testacs.</span></span><!--no-hyperlink--><span data-ttu-id="7e12d-3110">com</span><span class="sxs-lookup"><span data-stu-id="7e12d-3110">com</span></span>
- <span data-ttu-id="7e12d-3111">s-int.</span><span class="sxs-lookup"><span data-stu-id="7e12d-3111">s-int.</span></span><!--no-hyperlink--><span data-ttu-id="7e12d-3112">NET</span><span class="sxs-lookup"><span data-stu-id="7e12d-3112">net</span></span>

## <a name="sweden-national-id"></a><span data-ttu-id="7e12d-3113">Svezia - Identificativo nazionale</span><span class="sxs-lookup"><span data-stu-id="7e12d-3113">Sweden National ID</span></span>

### <a name="format"></a><span data-ttu-id="7e12d-3114">Formato</span><span class="sxs-lookup"><span data-stu-id="7e12d-3114">Format</span></span>

<span data-ttu-id="7e12d-3115">10 o 12 cifre e un delimitatore facoltativo</span><span class="sxs-lookup"><span data-stu-id="7e12d-3115">10 or 12 digits and an optional delimiter</span></span>

### <a name="pattern"></a><span data-ttu-id="7e12d-3116">Modello</span><span class="sxs-lookup"><span data-stu-id="7e12d-3116">Pattern</span></span>

<span data-ttu-id="7e12d-3117">10 o 12 cifre e un delimitatore facoltativo:</span><span class="sxs-lookup"><span data-stu-id="7e12d-3117">10 or 12 digits and an optional delimiter:</span></span>
- <span data-ttu-id="7e12d-3118">2-4 cifre (facoltative)</span><span class="sxs-lookup"><span data-stu-id="7e12d-3118">2-4 digits (optional)</span></span> 
- <span data-ttu-id="7e12d-3119">Sei cifre nel formato data AAMMGG</span><span class="sxs-lookup"><span data-stu-id="7e12d-3119">Six digits in date format YYMMDD</span></span> 
- <span data-ttu-id="7e12d-3120">Delimitatore di "-" o "+" (facoltativo) più</span><span class="sxs-lookup"><span data-stu-id="7e12d-3120">Delimiter of "-" or "+" (optional), plus</span></span>
- <span data-ttu-id="7e12d-3121">Quattro cifre</span><span class="sxs-lookup"><span data-stu-id="7e12d-3121">Four digits</span></span>

### <a name="checksum"></a><span data-ttu-id="7e12d-3122">Checksum</span><span class="sxs-lookup"><span data-stu-id="7e12d-3122">Checksum</span></span>

<span data-ttu-id="7e12d-3123">Sì</span><span class="sxs-lookup"><span data-stu-id="7e12d-3123">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="7e12d-3124">Definizione</span><span class="sxs-lookup"><span data-stu-id="7e12d-3124">Definition</span></span>

<span data-ttu-id="7e12d-3125">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="7e12d-3125">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="7e12d-3126">La funzione Func_swedish_national_identifier restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="7e12d-3126">The function Func_swedish_national_identifier finds content that matches the pattern.</span></span>
- <span data-ttu-id="7e12d-3127">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="7e12d-3127">The checksum passes.</span></span>

```xml
<!-- Sweden National ID -->
<Entity id="f69aaf40-79be-4fac-8f05-fd1910d272c8" patternsProximity="300" recommendedConfidence="85">
    <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_swedish_national_identifier" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="7e12d-3128">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="7e12d-3128">Keywords</span></span>

<span data-ttu-id="7e12d-3129">No</span><span class="sxs-lookup"><span data-stu-id="7e12d-3129">No</span></span>
   
## <a name="sweden-passport-number"></a><span data-ttu-id="7e12d-3130">Svezia - Numero di passaporto</span><span class="sxs-lookup"><span data-stu-id="7e12d-3130">Sweden Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="7e12d-3131">Formato</span><span class="sxs-lookup"><span data-stu-id="7e12d-3131">Format</span></span>

<span data-ttu-id="7e12d-3132">Otto cifre</span><span class="sxs-lookup"><span data-stu-id="7e12d-3132">Eight digits</span></span>

### <a name="pattern"></a><span data-ttu-id="7e12d-3133">Modello</span><span class="sxs-lookup"><span data-stu-id="7e12d-3133">Pattern</span></span>

<span data-ttu-id="7e12d-3134">Otto cifre consecutive</span><span class="sxs-lookup"><span data-stu-id="7e12d-3134">Eight consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="7e12d-3135">Checksum</span><span class="sxs-lookup"><span data-stu-id="7e12d-3135">Checksum</span></span>

<span data-ttu-id="7e12d-3136">No</span><span class="sxs-lookup"><span data-stu-id="7e12d-3136">No</span></span>

### <a name="definition"></a><span data-ttu-id="7e12d-3137">Definizione</span><span class="sxs-lookup"><span data-stu-id="7e12d-3137">Definition</span></span>

<span data-ttu-id="7e12d-3138">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="7e12d-3138">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="7e12d-3139">L'espressione regolare Regex_sweden_passport_number restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="7e12d-3139">The regular expression Regex_sweden_passport_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="7e12d-3140">Si verifica una delle situazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="7e12d-3140">One of the following is true:</span></span>
    - <span data-ttu-id="7e12d-3141">Viene trovata una parola chiave da Keyword_passport.</span><span class="sxs-lookup"><span data-stu-id="7e12d-3141">A keyword from Keyword_passport is found.</span></span>
    - <span data-ttu-id="7e12d-3142">Viene trovata una parola chiave da Keyword_sweden_passport.</span><span class="sxs-lookup"><span data-stu-id="7e12d-3142">A keyword from Keyword_sweden_passport is found.</span></span>

```xml
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

### <a name="keywords"></a><span data-ttu-id="7e12d-3143">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="7e12d-3143">Keywords</span></span>
   
#### <a name="keyword_sweden_passport"></a><span data-ttu-id="7e12d-3144">Keyword_sweden_passport</span><span class="sxs-lookup"><span data-stu-id="7e12d-3144">Keyword_sweden_passport</span></span>

- <span data-ttu-id="7e12d-3145">visa requirements</span><span class="sxs-lookup"><span data-stu-id="7e12d-3145">visa requirements</span></span> 
- <span data-ttu-id="7e12d-3146">Alien Registration Card</span><span class="sxs-lookup"><span data-stu-id="7e12d-3146">Alien Registration Card</span></span> 
- <span data-ttu-id="7e12d-3147">Schengen visas</span><span class="sxs-lookup"><span data-stu-id="7e12d-3147">Schengen visas</span></span> 
- <span data-ttu-id="7e12d-3148">Schengen visa</span><span class="sxs-lookup"><span data-stu-id="7e12d-3148">Schengen visa</span></span> 
- <span data-ttu-id="7e12d-3149">Visa Processing</span><span class="sxs-lookup"><span data-stu-id="7e12d-3149">Visa Processing</span></span> 
- <span data-ttu-id="7e12d-3150">Visa Type</span><span class="sxs-lookup"><span data-stu-id="7e12d-3150">Visa Type</span></span> 
- <span data-ttu-id="7e12d-3151">Single Entry</span><span class="sxs-lookup"><span data-stu-id="7e12d-3151">Single Entry</span></span> 
- <span data-ttu-id="7e12d-3152">Multiple Entry</span><span class="sxs-lookup"><span data-stu-id="7e12d-3152">Multiple Entry</span></span> 
- <span data-ttu-id="7e12d-3153">G3 Processing Fees</span><span class="sxs-lookup"><span data-stu-id="7e12d-3153">G3 Processing Fees</span></span> 

#### <a name="keyword_passport"></a><span data-ttu-id="7e12d-3154">Keyword_passport</span><span class="sxs-lookup"><span data-stu-id="7e12d-3154">Keyword_passport</span></span>

- <span data-ttu-id="7e12d-3155">Passport Number</span><span class="sxs-lookup"><span data-stu-id="7e12d-3155">Passport Number</span></span> 
- <span data-ttu-id="7e12d-3156">Passport No</span><span class="sxs-lookup"><span data-stu-id="7e12d-3156">Passport No</span></span> 
- <span data-ttu-id="7e12d-3157">Passport#</span><span class="sxs-lookup"><span data-stu-id="7e12d-3157">Passport #</span></span> 
- <span data-ttu-id="7e12d-3158">Passaporto #</span><span class="sxs-lookup"><span data-stu-id="7e12d-3158">Passport#</span></span> 
- <span data-ttu-id="7e12d-3159">PassportID</span><span class="sxs-lookup"><span data-stu-id="7e12d-3159">PassportID</span></span> 
- <span data-ttu-id="7e12d-3160">Passportno</span><span class="sxs-lookup"><span data-stu-id="7e12d-3160">Passportno</span></span> 
- <span data-ttu-id="7e12d-3161">passportnumber</span><span class="sxs-lookup"><span data-stu-id="7e12d-3161">passportnumber</span></span> 
- <span data-ttu-id="7e12d-3162">パスポート</span><span class="sxs-lookup"><span data-stu-id="7e12d-3162">パスポート</span></span> 
- <span data-ttu-id="7e12d-3163">パスポート番号</span><span class="sxs-lookup"><span data-stu-id="7e12d-3163">パスポート番号</span></span> 
- <span data-ttu-id="7e12d-3164">パスポートのNum</span><span class="sxs-lookup"><span data-stu-id="7e12d-3164">パスポートのNum</span></span> 
- <span data-ttu-id="7e12d-3165">パスポート＃</span><span class="sxs-lookup"><span data-stu-id="7e12d-3165">パスポート＃</span></span> 
- <span data-ttu-id="7e12d-3166">Numéro de passeport</span><span class="sxs-lookup"><span data-stu-id="7e12d-3166">Numéro de passeport</span></span> 
- <span data-ttu-id="7e12d-3167">Passeport n °</span><span class="sxs-lookup"><span data-stu-id="7e12d-3167">Passeport n °</span></span> 
- <span data-ttu-id="7e12d-3168">Passeport Non</span><span class="sxs-lookup"><span data-stu-id="7e12d-3168">Passeport Non</span></span> 
- <span data-ttu-id="7e12d-3169">Passeport#</span><span class="sxs-lookup"><span data-stu-id="7e12d-3169">Passeport #</span></span> 
- <span data-ttu-id="7e12d-3170">Passeport #</span><span class="sxs-lookup"><span data-stu-id="7e12d-3170">Passeport#</span></span> 
- <span data-ttu-id="7e12d-3171">PasseportNon</span><span class="sxs-lookup"><span data-stu-id="7e12d-3171">PasseportNon</span></span> 
- <span data-ttu-id="7e12d-3172">Passeportn °</span><span class="sxs-lookup"><span data-stu-id="7e12d-3172">Passeportn °</span></span> 
   
## <a name="swift-code"></a><span data-ttu-id="7e12d-3173">Codice SWIFT</span><span class="sxs-lookup"><span data-stu-id="7e12d-3173">SWIFT Code</span></span>

### <a name="format"></a><span data-ttu-id="7e12d-3174">Formato</span><span class="sxs-lookup"><span data-stu-id="7e12d-3174">Format</span></span>

<span data-ttu-id="7e12d-3175">Quattro lettere seguite da 5-31 lettere o cifre</span><span class="sxs-lookup"><span data-stu-id="7e12d-3175">Four letters followed by 5-31 letters or digits</span></span>

### <a name="pattern"></a><span data-ttu-id="7e12d-3176">Modello</span><span class="sxs-lookup"><span data-stu-id="7e12d-3176">Pattern</span></span>

<span data-ttu-id="7e12d-3177">Quattro lettere seguite da 5-31 lettere o cifre:</span><span class="sxs-lookup"><span data-stu-id="7e12d-3177">Four letters followed by 5-31 letters or digits:</span></span>
- <span data-ttu-id="7e12d-3178">Codice ABI di quattro cifre (senza distinzione tra maiuscole/minuscole)</span><span class="sxs-lookup"><span data-stu-id="7e12d-3178">Four-letter bank code (not case sensitive)</span></span> 
- <span data-ttu-id="7e12d-3179">Uno spazio facoltativo</span><span class="sxs-lookup"><span data-stu-id="7e12d-3179">An optional space</span></span> 
- <span data-ttu-id="7e12d-3180">4-28 lettere o cifre (BBAN)</span><span class="sxs-lookup"><span data-stu-id="7e12d-3180">4-28 letters or digits (the Basic Bank Account Number (BBAN))</span></span> 
- <span data-ttu-id="7e12d-3181">Uno spazio facoltativo</span><span class="sxs-lookup"><span data-stu-id="7e12d-3181">An optional space</span></span> 
- <span data-ttu-id="7e12d-3182">1-3 lettere o cifre (resto del BBAN)</span><span class="sxs-lookup"><span data-stu-id="7e12d-3182">1-3 letters or digits (remainder of the BBAN)</span></span>

### <a name="checksum"></a><span data-ttu-id="7e12d-3183">Checksum</span><span class="sxs-lookup"><span data-stu-id="7e12d-3183">Checksum</span></span>

<span data-ttu-id="7e12d-3184">No</span><span class="sxs-lookup"><span data-stu-id="7e12d-3184">No</span></span>

### <a name="definition"></a><span data-ttu-id="7e12d-3185">Definizione</span><span class="sxs-lookup"><span data-stu-id="7e12d-3185">Definition</span></span>

<span data-ttu-id="7e12d-3186">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="7e12d-3186">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="7e12d-3187">L'espressione regolare Regex_swift restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="7e12d-3187">The regular expression Regex_swift finds content that matches the pattern.</span></span>
- <span data-ttu-id="7e12d-3188">Viene trovata una parola chiave da Keyword_swift.</span><span class="sxs-lookup"><span data-stu-id="7e12d-3188">A keyword from Keyword_swift is found.</span></span>

```xml
<Entity id="cb2ab58c-9cb8-4c81-baf8-a4e106791df4" patternsProximity="300" recommendedConfidence="75">
<Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_swift" />
        <Match idRef="Keyword_swift" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="7e12d-3189">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="7e12d-3189">Keywords</span></span>
   
#### <a name="keyword_swift"></a><span data-ttu-id="7e12d-3190">Keyword_swift</span><span class="sxs-lookup"><span data-stu-id="7e12d-3190">Keyword_swift</span></span>

- <span data-ttu-id="7e12d-3191">international organization for standardization 9362</span><span class="sxs-lookup"><span data-stu-id="7e12d-3191">international organization for standardization 9362</span></span> 
- <span data-ttu-id="7e12d-3192">iso 9362</span><span class="sxs-lookup"><span data-stu-id="7e12d-3192">iso 9362</span></span> 
- <span data-ttu-id="7e12d-3193">iso9362</span><span class="sxs-lookup"><span data-stu-id="7e12d-3193">iso9362</span></span> 
- <span data-ttu-id="7e12d-3194">Swift\#</span><span class="sxs-lookup"><span data-stu-id="7e12d-3194">swift\#</span></span> 
- <span data-ttu-id="7e12d-3195">swiftcode</span><span class="sxs-lookup"><span data-stu-id="7e12d-3195">swiftcode</span></span> 
- <span data-ttu-id="7e12d-3196">swiftnumber</span><span class="sxs-lookup"><span data-stu-id="7e12d-3196">swiftnumber</span></span> 
- <span data-ttu-id="7e12d-3197">swiftroutingnumber</span><span class="sxs-lookup"><span data-stu-id="7e12d-3197">swiftroutingnumber</span></span> 
- <span data-ttu-id="7e12d-3198">swift code</span><span class="sxs-lookup"><span data-stu-id="7e12d-3198">swift code</span></span> 
- <span data-ttu-id="7e12d-3199">swift number #</span><span class="sxs-lookup"><span data-stu-id="7e12d-3199">swift number #</span></span> 
- <span data-ttu-id="7e12d-3200">swift routing number</span><span class="sxs-lookup"><span data-stu-id="7e12d-3200">swift routing number</span></span> 
- <span data-ttu-id="7e12d-3201">bic number</span><span class="sxs-lookup"><span data-stu-id="7e12d-3201">bic number</span></span> 
- <span data-ttu-id="7e12d-3202">bic code</span><span class="sxs-lookup"><span data-stu-id="7e12d-3202">bic code</span></span> 
- <span data-ttu-id="7e12d-3203">BIC\#</span><span class="sxs-lookup"><span data-stu-id="7e12d-3203">bic \#</span></span> 
- <span data-ttu-id="7e12d-3204">BIC\#</span><span class="sxs-lookup"><span data-stu-id="7e12d-3204">bic\#</span></span> 
- <span data-ttu-id="7e12d-3205">bank identifier code</span><span class="sxs-lookup"><span data-stu-id="7e12d-3205">bank identifier code</span></span> 
- <span data-ttu-id="7e12d-3206">標準化 9362</span><span class="sxs-lookup"><span data-stu-id="7e12d-3206">標準化9362</span></span> 
- <span data-ttu-id="7e12d-3207">迅速＃</span><span class="sxs-lookup"><span data-stu-id="7e12d-3207">迅速＃</span></span> 
- <span data-ttu-id="7e12d-3208">SWIFTコード</span><span class="sxs-lookup"><span data-stu-id="7e12d-3208">SWIFTコード</span></span> 
- <span data-ttu-id="7e12d-3209">SWIFT番号</span><span class="sxs-lookup"><span data-stu-id="7e12d-3209">SWIFT番号</span></span> 
- <span data-ttu-id="7e12d-3210">迅速なルーティング番号</span><span class="sxs-lookup"><span data-stu-id="7e12d-3210">迅速なルーティング番号</span></span> 
- <span data-ttu-id="7e12d-3211">BIC番号</span><span class="sxs-lookup"><span data-stu-id="7e12d-3211">BIC番号</span></span> 
- <span data-ttu-id="7e12d-3212">BICコード</span><span class="sxs-lookup"><span data-stu-id="7e12d-3212">BICコード</span></span> 
- <span data-ttu-id="7e12d-3213">銀行識別コードのための国際組織</span><span class="sxs-lookup"><span data-stu-id="7e12d-3213">銀行識別コードのための国際組織</span></span> 
- <span data-ttu-id="7e12d-3214">Organisation internationale de normalisation 9362</span><span class="sxs-lookup"><span data-stu-id="7e12d-3214">Organisation internationale de normalisation 9362</span></span> 
- <span data-ttu-id="7e12d-3215">rapide\#</span><span class="sxs-lookup"><span data-stu-id="7e12d-3215">rapide \#</span></span> 
- <span data-ttu-id="7e12d-3216">code SWIFT</span><span class="sxs-lookup"><span data-stu-id="7e12d-3216">code SWIFT</span></span> 
- <span data-ttu-id="7e12d-3217">le numéro de swift</span><span class="sxs-lookup"><span data-stu-id="7e12d-3217">le numéro de swift</span></span> 
- <span data-ttu-id="7e12d-3218">swift numéro d'acheminement</span><span class="sxs-lookup"><span data-stu-id="7e12d-3218">swift numéro d'acheminement</span></span> 
- <span data-ttu-id="7e12d-3219">le numéro BIC</span><span class="sxs-lookup"><span data-stu-id="7e12d-3219">le numéro BIC</span></span> 
- <span data-ttu-id="7e12d-3220">\#BIC</span><span class="sxs-lookup"><span data-stu-id="7e12d-3220">\# BIC</span></span> 
- <span data-ttu-id="7e12d-3221">code identificateur de banque</span><span class="sxs-lookup"><span data-stu-id="7e12d-3221">code identificateur de banque</span></span> 
   
## <a name="taiwan-national-id"></a><span data-ttu-id="7e12d-3222">Taiwan National ID</span><span class="sxs-lookup"><span data-stu-id="7e12d-3222">Taiwan National ID</span></span>

### <a name="format"></a><span data-ttu-id="7e12d-3223">Formato</span><span class="sxs-lookup"><span data-stu-id="7e12d-3223">Format</span></span>

<span data-ttu-id="7e12d-3224">Una lettera (in lingua inglese) seguita da nove cifre</span><span class="sxs-lookup"><span data-stu-id="7e12d-3224">One letter (in English) followed by nine digits</span></span>

### <a name="pattern"></a><span data-ttu-id="7e12d-3225">Modello</span><span class="sxs-lookup"><span data-stu-id="7e12d-3225">Pattern</span></span>

<span data-ttu-id="7e12d-3226">Una lettera (in lingua inglese) seguita da nove cifre:</span><span class="sxs-lookup"><span data-stu-id="7e12d-3226">One letter (in English) followed by nine digits:</span></span>
- <span data-ttu-id="7e12d-3227">Una lettera (in inglese, senza distinzione tra tra maiuscole/minuscole)</span><span class="sxs-lookup"><span data-stu-id="7e12d-3227">One letter (in English, not case sensitive)</span></span> 
- <span data-ttu-id="7e12d-3228">La cifra "1" o "2"</span><span class="sxs-lookup"><span data-stu-id="7e12d-3228">The digit "1" or "2"</span></span> 
- <span data-ttu-id="7e12d-3229">Otto cifre</span><span class="sxs-lookup"><span data-stu-id="7e12d-3229">Eight digits</span></span>

### <a name="checksum"></a><span data-ttu-id="7e12d-3230">Checksum</span><span class="sxs-lookup"><span data-stu-id="7e12d-3230">Checksum</span></span>

<span data-ttu-id="7e12d-3231">Sì</span><span class="sxs-lookup"><span data-stu-id="7e12d-3231">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="7e12d-3232">Definizione</span><span class="sxs-lookup"><span data-stu-id="7e12d-3232">Definition</span></span>

<span data-ttu-id="7e12d-3233">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="7e12d-3233">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="7e12d-3234">La funzione Func_taiwanese_national_id restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="7e12d-3234">The function Func_taiwanese_national_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="7e12d-3235">Viene trovata una parola chiave da Keyword_taiwanese_national_id.</span><span class="sxs-lookup"><span data-stu-id="7e12d-3235">A keyword from Keyword_taiwanese_national_id is found.</span></span>
- <span data-ttu-id="7e12d-3236">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="7e12d-3236">The checksum passes.</span></span>

```xml
<!-- Taiwanese National ID -->
<Entity id="4C7BFC34-8DD1-421D-8FB7-6C6182C2AF03" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_taiwanese_national_id" />
          <Match idRef="Keyword_taiwanese_national_id" />
      </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="7e12d-3237">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="7e12d-3237">Keywords</span></span>

#### <a name="keyword_taiwanese_national_id"></a><span data-ttu-id="7e12d-3238">Keyword_taiwanese_national_id</span><span class="sxs-lookup"><span data-stu-id="7e12d-3238">Keyword_taiwanese_national_id</span></span>

- <span data-ttu-id="7e12d-3239">身份證字號</span><span class="sxs-lookup"><span data-stu-id="7e12d-3239">身份證字號</span></span> 
- <span data-ttu-id="7e12d-3240">身份證</span><span class="sxs-lookup"><span data-stu-id="7e12d-3240">身份證</span></span> 
- <span data-ttu-id="7e12d-3241">身份證號碼</span><span class="sxs-lookup"><span data-stu-id="7e12d-3241">身份證號碼</span></span> 
- <span data-ttu-id="7e12d-3242">身份證號</span><span class="sxs-lookup"><span data-stu-id="7e12d-3242">身份證號</span></span> 
- <span data-ttu-id="7e12d-3243">身分證字號</span><span class="sxs-lookup"><span data-stu-id="7e12d-3243">身分證字號</span></span> 
- <span data-ttu-id="7e12d-3244">身分證</span><span class="sxs-lookup"><span data-stu-id="7e12d-3244">身分證</span></span> 
- <span data-ttu-id="7e12d-3245">身分證號碼</span><span class="sxs-lookup"><span data-stu-id="7e12d-3245">身分證號碼</span></span> 
- <span data-ttu-id="7e12d-3246">身份證號</span><span class="sxs-lookup"><span data-stu-id="7e12d-3246">身份證號</span></span> 
- <span data-ttu-id="7e12d-3247">身分證統一編號</span><span class="sxs-lookup"><span data-stu-id="7e12d-3247">身分證統一編號</span></span> 
- <span data-ttu-id="7e12d-3248">國民身分證統一編號</span><span class="sxs-lookup"><span data-stu-id="7e12d-3248">國民身分證統一編號</span></span> 
- <span data-ttu-id="7e12d-3249">簽名</span><span class="sxs-lookup"><span data-stu-id="7e12d-3249">簽名</span></span> 
- <span data-ttu-id="7e12d-3250">蓋章</span><span class="sxs-lookup"><span data-stu-id="7e12d-3250">蓋章</span></span> 
- <span data-ttu-id="7e12d-3251">簽名或蓋章</span><span class="sxs-lookup"><span data-stu-id="7e12d-3251">簽名或蓋章</span></span> 
- <span data-ttu-id="7e12d-3252">簽章</span><span class="sxs-lookup"><span data-stu-id="7e12d-3252">簽章</span></span>   
   
## <a name="taiwan-passport-number"></a><span data-ttu-id="7e12d-3253">	Taiwan - Numero di passaporto</span><span class="sxs-lookup"><span data-stu-id="7e12d-3253">Taiwan Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="7e12d-3254">Formato</span><span class="sxs-lookup"><span data-stu-id="7e12d-3254">Format</span></span>

- <span data-ttu-id="7e12d-3255">Numero di passaporto biometrico: nove cifre</span><span class="sxs-lookup"><span data-stu-id="7e12d-3255">Biometric passport number: Nine digits</span></span>
- <span data-ttu-id="7e12d-3256">Numero di passaporto non biometrico: nove cifre</span><span class="sxs-lookup"><span data-stu-id="7e12d-3256">Non-biometric passport number: Nine digits</span></span>

### <a name="pattern"></a><span data-ttu-id="7e12d-3257">Modello</span><span class="sxs-lookup"><span data-stu-id="7e12d-3257">Pattern</span></span>
<span data-ttu-id="7e12d-3258">Numero di passaporto biometrico:</span><span class="sxs-lookup"><span data-stu-id="7e12d-3258">Biometric passport number:</span></span>
- <span data-ttu-id="7e12d-3259">La cifra "3" </span><span class="sxs-lookup"><span data-stu-id="7e12d-3259">The digit "3"</span></span> 
- <span data-ttu-id="7e12d-3260">Otto cifre</span><span class="sxs-lookup"><span data-stu-id="7e12d-3260">Eight digits</span></span>

<span data-ttu-id="7e12d-3261">Numero di passaporto non biometrico:</span><span class="sxs-lookup"><span data-stu-id="7e12d-3261">Non-biometric passport number:</span></span>
- <span data-ttu-id="7e12d-3262">9 cifre</span><span class="sxs-lookup"><span data-stu-id="7e12d-3262">Nine digits</span></span>

### <a name="checksum"></a><span data-ttu-id="7e12d-3263">Checksum</span><span class="sxs-lookup"><span data-stu-id="7e12d-3263">Checksum</span></span>

<span data-ttu-id="7e12d-3264">No</span><span class="sxs-lookup"><span data-stu-id="7e12d-3264">No</span></span>

### <a name="definition"></a><span data-ttu-id="7e12d-3265">Definizione</span><span class="sxs-lookup"><span data-stu-id="7e12d-3265">Definition</span></span>

<span data-ttu-id="7e12d-3266">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="7e12d-3266">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="7e12d-3267">L'espressione regolare Regex_taiwan_passport trova il contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="7e12d-3267">The regular expression Regex_taiwan_passport finds content that matches the pattern.</span></span>
- <span data-ttu-id="7e12d-3268">Viene trovata una parola chiave da Keyword_taiwan_passport.</span><span class="sxs-lookup"><span data-stu-id="7e12d-3268">A keyword from Keyword_taiwan_passport is found.</span></span>

```xml
<!-- Taiwan Passport Number -->
<Entity id="e7251cb4-4c2c-41df-963e-924eb3dae04a" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_taiwan_passport"/>
     <Match idRef="Keyword_taiwan_passport"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="7e12d-3269">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="7e12d-3269">Keywords</span></span>

#### <a name="keyword_taiwan_passport"></a><span data-ttu-id="7e12d-3270">Keyword_taiwan_passport</span><span class="sxs-lookup"><span data-stu-id="7e12d-3270">Keyword_taiwan_passport</span></span>

- <span data-ttu-id="7e12d-3271">Numero passaporto ROC</span><span class="sxs-lookup"><span data-stu-id="7e12d-3271">ROC passport number</span></span> 
- <span data-ttu-id="7e12d-3272">Numero passaporto</span><span class="sxs-lookup"><span data-stu-id="7e12d-3272">Passport number</span></span> 
- <span data-ttu-id="7e12d-3273">N° passaporto</span><span class="sxs-lookup"><span data-stu-id="7e12d-3273">Passport no</span></span> 
- <span data-ttu-id="7e12d-3274">Num. passaporto
</span><span class="sxs-lookup"><span data-stu-id="7e12d-3274">Passport Num</span></span> 
- <span data-ttu-id="7e12d-3275">Passport #</span><span class="sxs-lookup"><span data-stu-id="7e12d-3275">Passport #</span></span> 
- <span data-ttu-id="7e12d-3276">护照</span><span class="sxs-lookup"><span data-stu-id="7e12d-3276">护照</span></span> 
- <span data-ttu-id="7e12d-3277">中華民國護照</span><span class="sxs-lookup"><span data-stu-id="7e12d-3277">中華民國護照</span></span> 
- <span data-ttu-id="7e12d-3278">Zhōnghuá Mínguó hùzhào</span><span class="sxs-lookup"><span data-stu-id="7e12d-3278">Zhōnghuá Mínguó hùzhào</span></span>
   
## <a name="taiwan-resident-certificate-arctarc-number"></a><span data-ttu-id="7e12d-3279">Taiwan - Numero certificato di residenza (ARC/TARC)</span><span class="sxs-lookup"><span data-stu-id="7e12d-3279">Taiwan Resident Certificate (ARC/TARC) Number</span></span>

### <a name="format"></a><span data-ttu-id="7e12d-3280">Formato</span><span class="sxs-lookup"><span data-stu-id="7e12d-3280">Format</span></span>

<span data-ttu-id="7e12d-3281">10 lettere e cifre</span><span class="sxs-lookup"><span data-stu-id="7e12d-3281">10 letters and digits</span></span>

### <a name="pattern"></a><span data-ttu-id="7e12d-3282">Modello</span><span class="sxs-lookup"><span data-stu-id="7e12d-3282">Pattern</span></span>

<span data-ttu-id="7e12d-3283">10 lettere e cifre:</span><span class="sxs-lookup"><span data-stu-id="7e12d-3283">10 letters and digits:</span></span>
- <span data-ttu-id="7e12d-3284">Due lettere (senza distinzione tra maiuscole/minuscole)</span><span class="sxs-lookup"><span data-stu-id="7e12d-3284">Two letters (not case sensitive)</span></span> 
- <span data-ttu-id="7e12d-3285">Otto cifre</span><span class="sxs-lookup"><span data-stu-id="7e12d-3285">Eight digits</span></span>

### <a name="checksum"></a><span data-ttu-id="7e12d-3286">Checksum</span><span class="sxs-lookup"><span data-stu-id="7e12d-3286">Checksum</span></span>

<span data-ttu-id="7e12d-3287">No</span><span class="sxs-lookup"><span data-stu-id="7e12d-3287">No</span></span>

### <a name="definition"></a><span data-ttu-id="7e12d-3288">Definizione</span><span class="sxs-lookup"><span data-stu-id="7e12d-3288">Definition</span></span>

<span data-ttu-id="7e12d-3289">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="7e12d-3289">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="7e12d-3290">L'espressione regolare Regex_taiwan_resident_certificate trova il contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="7e12d-3290">The regular expression Regex_taiwan_resident_certificate finds content that matches the pattern.</span></span>
- <span data-ttu-id="7e12d-3291">Viene trovata una parola chiave da Keyword_taiwan_resident_certificate.</span><span class="sxs-lookup"><span data-stu-id="7e12d-3291">A keyword from Keyword_taiwan_resident_certificate is found.</span></span>

```xml
<!-- Taiwan Resident Certificate (ARC/TARC) -->
<Entity id="48269fec-05ea-46ea-b326-f5623a58c6e9" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_taiwan_resident_certificate"/>
     <Match idRef="Keyword_taiwan_resident_certificate"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="7e12d-3292">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="7e12d-3292">Keywords</span></span>

#### <a name="keyword_taiwan_resident_certificate"></a><span data-ttu-id="7e12d-3293">Keyword_taiwan_resident_certificate</span><span class="sxs-lookup"><span data-stu-id="7e12d-3293">Keyword_taiwan_resident_certificate</span></span>

- <span data-ttu-id="7e12d-3294">Certificato di residenza</span><span class="sxs-lookup"><span data-stu-id="7e12d-3294">Resident Certificate</span></span> 
- <span data-ttu-id="7e12d-3295">Cert. di resid
</span><span class="sxs-lookup"><span data-stu-id="7e12d-3295">Resident Cert</span></span> 
- <span data-ttu-id="7e12d-3296">Cert. di resid.
</span><span class="sxs-lookup"><span data-stu-id="7e12d-3296">Resident Cert.</span></span> 
- <span data-ttu-id="7e12d-3297">Carta d’identità</span><span class="sxs-lookup"><span data-stu-id="7e12d-3297">Identification card</span></span> 
- <span data-ttu-id="7e12d-3298">Certificato residente straniero</span><span class="sxs-lookup"><span data-stu-id="7e12d-3298">Alien Resident Certificate</span></span> 
- <span data-ttu-id="7e12d-3299">ARCO</span><span class="sxs-lookup"><span data-stu-id="7e12d-3299">ARC</span></span> 
- <span data-ttu-id="7e12d-3300">Certificato residente nell’area di Taiwan</span><span class="sxs-lookup"><span data-stu-id="7e12d-3300">Taiwan Area Resident Certificate</span></span> 
- <span data-ttu-id="7e12d-3301">TARC Tax</span><span class="sxs-lookup"><span data-stu-id="7e12d-3301">TARC</span></span> 
- <span data-ttu-id="7e12d-3302">居留證</span><span class="sxs-lookup"><span data-stu-id="7e12d-3302">居留證</span></span> 
- <span data-ttu-id="7e12d-3303">外僑居留證</span><span class="sxs-lookup"><span data-stu-id="7e12d-3303">外僑居留證</span></span> 
- <span data-ttu-id="7e12d-3304">台灣地區居留證</span><span class="sxs-lookup"><span data-stu-id="7e12d-3304">台灣地區居留證</span></span> 

## <a name="thai-population-identification-code"></a><span data-ttu-id="7e12d-3305">Codice di identificazione della popolazione tailandese</span><span class="sxs-lookup"><span data-stu-id="7e12d-3305">Thai Population Identification Code</span></span>

### <a name="format"></a><span data-ttu-id="7e12d-3306">Formato</span><span class="sxs-lookup"><span data-stu-id="7e12d-3306">Format</span></span>

<span data-ttu-id="7e12d-3307">13 cifre</span><span class="sxs-lookup"><span data-stu-id="7e12d-3307">13 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="7e12d-3308">Modello</span><span class="sxs-lookup"><span data-stu-id="7e12d-3308">Pattern</span></span>

<span data-ttu-id="7e12d-3309">13 cifre:</span><span class="sxs-lookup"><span data-stu-id="7e12d-3309">13 digits:</span></span>
- <span data-ttu-id="7e12d-3310">La prima cifra non è 0 o 9</span><span class="sxs-lookup"><span data-stu-id="7e12d-3310">First digit is not 0 or 9</span></span> 
- <span data-ttu-id="7e12d-3311">12 cifre</span><span class="sxs-lookup"><span data-stu-id="7e12d-3311">12 digits</span></span>

### <a name="checksum"></a><span data-ttu-id="7e12d-3312">Checksum</span><span class="sxs-lookup"><span data-stu-id="7e12d-3312">Checksum</span></span>

<span data-ttu-id="7e12d-3313">Sì</span><span class="sxs-lookup"><span data-stu-id="7e12d-3313">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="7e12d-3314">Definizione</span><span class="sxs-lookup"><span data-stu-id="7e12d-3314">Definition</span></span>

<span data-ttu-id="7e12d-3315">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="7e12d-3315">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="7e12d-3316">La funzione Func_Thai_Citizen_Id trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="7e12d-3316">The function Func_Thai_Citizen_Id finds content that matches the pattern.</span></span>
- <span data-ttu-id="7e12d-3317">Viene trovata una parola chiave da Keyword_Thai_Citizen_Id.</span><span class="sxs-lookup"><span data-stu-id="7e12d-3317">A keyword from Keyword_Thai_Citizen_Id is found.</span></span>

<span data-ttu-id="7e12d-3318">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="7e12d-3318">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="7e12d-3319">La funzione Func_Thai_Citizen_Id trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="7e12d-3319">The function Func_Thai_Citizen_Id finds content that matches the pattern.</span></span>

```xml
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

### <a name="keywords"></a><span data-ttu-id="7e12d-3320">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="7e12d-3320">Keywords</span></span>

#### <a name="keyword_thai_citizen_id"></a><span data-ttu-id="7e12d-3321">Keyword_Thai_Citizen_Id</span><span class="sxs-lookup"><span data-stu-id="7e12d-3321">Keyword_Thai_Citizen_Id</span></span>

- <span data-ttu-id="7e12d-3322">Numero ID
</span><span class="sxs-lookup"><span data-stu-id="7e12d-3322">ID Number</span></span>
- <span data-ttu-id="7e12d-3323">Numero di identificazione</span><span class="sxs-lookup"><span data-stu-id="7e12d-3323">Identification Number</span></span>
- <span data-ttu-id="7e12d-3324">บัตรประชาชน</span><span class="sxs-lookup"><span data-stu-id="7e12d-3324">บัตรประชาชน</span></span>
- <span data-ttu-id="7e12d-3325">รหัสบัตรประชาชน</span><span class="sxs-lookup"><span data-stu-id="7e12d-3325">รหัสบัตรประชาชน</span></span>
- <span data-ttu-id="7e12d-3326">บัตรประชาชน</span><span class="sxs-lookup"><span data-stu-id="7e12d-3326">บัตรประชาชน</span></span>
- <span data-ttu-id="7e12d-3327">รหัสบัตรประชาชน</span><span class="sxs-lookup"><span data-stu-id="7e12d-3327">รหัสบัตรประชาชน</span></span>
  
## <a name="turkish-national-identification-number"></a><span data-ttu-id="7e12d-3328">Numero di identificazione nazionale turco</span><span class="sxs-lookup"><span data-stu-id="7e12d-3328">Turkish National Identification Number</span></span>

### <a name="format"></a><span data-ttu-id="7e12d-3329">Formato</span><span class="sxs-lookup"><span data-stu-id="7e12d-3329">Format</span></span>

<span data-ttu-id="7e12d-3330">11 cifre</span><span class="sxs-lookup"><span data-stu-id="7e12d-3330">11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="7e12d-3331">Modello</span><span class="sxs-lookup"><span data-stu-id="7e12d-3331">Pattern</span></span>

<span data-ttu-id="7e12d-3332">11 cifre</span><span class="sxs-lookup"><span data-stu-id="7e12d-3332">11 digits</span></span>

### <a name="checksum"></a><span data-ttu-id="7e12d-3333">Checksum</span><span class="sxs-lookup"><span data-stu-id="7e12d-3333">Checksum</span></span>

<span data-ttu-id="7e12d-3334">Sì</span><span class="sxs-lookup"><span data-stu-id="7e12d-3334">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="7e12d-3335">Definizione</span><span class="sxs-lookup"><span data-stu-id="7e12d-3335">Definition</span></span>

<span data-ttu-id="7e12d-3336">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="7e12d-3336">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="7e12d-3337">La funzione Func_Turkish_National_Id trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="7e12d-3337">The function Func_Turkish_National_Id finds content that matches the pattern.</span></span>
- <span data-ttu-id="7e12d-3338">Viene trovata una parola chiave da Keyword_Turkish_National_Id.</span><span class="sxs-lookup"><span data-stu-id="7e12d-3338">A keyword from Keyword_Turkish_National_Id is found.</span></span>

<span data-ttu-id="7e12d-3339">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="7e12d-3339">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="7e12d-3340">La funzione Func_Turkish_National_Id trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="7e12d-3340">The function Func_Turkish_National_Id finds content that matches the pattern.</span></span>

```xml
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

### <a name="keywords"></a><span data-ttu-id="7e12d-3341">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="7e12d-3341">Keywords</span></span>

#### <a name="keyword_turkish_national_id"></a><span data-ttu-id="7e12d-3342">Keyword_Turkish_National_Id</span><span class="sxs-lookup"><span data-stu-id="7e12d-3342">Keyword_Turkish_National_Id</span></span>

- <span data-ttu-id="7e12d-3343">TC Kimlik No</span><span class="sxs-lookup"><span data-stu-id="7e12d-3343">TC Kimlik No</span></span>
- <span data-ttu-id="7e12d-3344">Numarası Kimlik TC</span><span class="sxs-lookup"><span data-stu-id="7e12d-3344">TC Kimlik numarası</span></span>
- <span data-ttu-id="7e12d-3345">Vatandaşlık numarası</span><span class="sxs-lookup"><span data-stu-id="7e12d-3345">Vatandaşlık numarası</span></span>
- <span data-ttu-id="7e12d-3346">Vatandaşlık No</span><span class="sxs-lookup"><span data-stu-id="7e12d-3346">Vatandaşlık no</span></span>

## <a name="uk-drivers-license-number"></a><span data-ttu-id="7e12d-p141">Regno Unito - Numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="7e12d-p141">U.K. Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="7e12d-3349">Formato</span><span class="sxs-lookup"><span data-stu-id="7e12d-3349">Format</span></span>

<span data-ttu-id="7e12d-3350">Combinazione di 18 lettere e numeri nel formato specificato</span><span class="sxs-lookup"><span data-stu-id="7e12d-3350">Combination of 18 letters and digits in the specified format</span></span>

### <a name="pattern"></a><span data-ttu-id="7e12d-3351">Modello</span><span class="sxs-lookup"><span data-stu-id="7e12d-3351">Pattern</span></span>

<span data-ttu-id="7e12d-3352">18 lettere e cifre:</span><span class="sxs-lookup"><span data-stu-id="7e12d-3352">18 letters and digits:</span></span>
- <span data-ttu-id="7e12d-3353">Cinque lettere (senza distinzione fra maiuscole/minuscole) o la cifra 9 al posto di una lettera</span><span class="sxs-lookup"><span data-stu-id="7e12d-3353">Five letters (not case sensitive) or the digit "9" in place of a letter</span></span> 
- <span data-ttu-id="7e12d-3354">Una cifra</span><span class="sxs-lookup"><span data-stu-id="7e12d-3354">One digit</span></span> 
- <span data-ttu-id="7e12d-3355">5 cifre nel formato data GGMMA relativo alla data di nascita</span><span class="sxs-lookup"><span data-stu-id="7e12d-3355">Five digits in the date format DDMMY for date of birth</span></span> 
- <span data-ttu-id="7e12d-3356">Due lettere (senza distinzione fra maiuscole/minuscole) o la cifra 9 al posto di una lettera</span><span class="sxs-lookup"><span data-stu-id="7e12d-3356">Two letters (not case sensitive) or the digit "9" in place of a letter</span></span> 
- <span data-ttu-id="7e12d-3357">Cinque cifre</span><span class="sxs-lookup"><span data-stu-id="7e12d-3357">Five digits</span></span>

### <a name="checksum"></a><span data-ttu-id="7e12d-3358">Checksum</span><span class="sxs-lookup"><span data-stu-id="7e12d-3358">Checksum</span></span>

<span data-ttu-id="7e12d-3359">Sì</span><span class="sxs-lookup"><span data-stu-id="7e12d-3359">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="7e12d-3360">Definizione</span><span class="sxs-lookup"><span data-stu-id="7e12d-3360">Definition</span></span>

<span data-ttu-id="7e12d-3361">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="7e12d-3361">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="7e12d-3362">La funzione Func_uk_drivers_license restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="7e12d-3362">The function Func_uk_drivers_license finds content that matches the pattern.</span></span>
- <span data-ttu-id="7e12d-3363">Viene trovata una parola chiave da Keyword_uk_drivers_license.</span><span class="sxs-lookup"><span data-stu-id="7e12d-3363">A keyword from Keyword_uk_drivers_license is found.</span></span>
- <span data-ttu-id="7e12d-3364">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="7e12d-3364">The checksum passes.</span></span>

```xml
<!-- U.K. Driver's License Number -->
<Entity id="f93de4be-d94c-40df-a8be-461738047551" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_uk_drivers_license" />
        <Match idRef="Keyword_uk_drivers_license" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="7e12d-3365">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="7e12d-3365">Keywords</span></span>

#### <a name="keyword_uk_drivers_license"></a><span data-ttu-id="7e12d-3366">Keyword_uk_drivers_license</span><span class="sxs-lookup"><span data-stu-id="7e12d-3366">Keyword_uk_drivers_license</span></span>

- <span data-ttu-id="7e12d-3367">DVLA</span><span class="sxs-lookup"><span data-stu-id="7e12d-3367">DVLA</span></span> 
- <span data-ttu-id="7e12d-3368">light vans</span><span class="sxs-lookup"><span data-stu-id="7e12d-3368">light vans</span></span> 
- <span data-ttu-id="7e12d-3369">quadbikes</span><span class="sxs-lookup"><span data-stu-id="7e12d-3369">quadbikes</span></span> 
- <span data-ttu-id="7e12d-3370">motor cars</span><span class="sxs-lookup"><span data-stu-id="7e12d-3370">motor cars</span></span> 
- <span data-ttu-id="7e12d-3371">125cc</span><span class="sxs-lookup"><span data-stu-id="7e12d-3371">125cc</span></span> 
- <span data-ttu-id="7e12d-3372">sidecar</span><span class="sxs-lookup"><span data-stu-id="7e12d-3372">sidecar</span></span> 
- <span data-ttu-id="7e12d-3373">tricicli</span><span class="sxs-lookup"><span data-stu-id="7e12d-3373">tricycles</span></span> 
- <span data-ttu-id="7e12d-3374">moto</span><span class="sxs-lookup"><span data-stu-id="7e12d-3374">motorcycles</span></span> 
- <span data-ttu-id="7e12d-3375">photocard licence</span><span class="sxs-lookup"><span data-stu-id="7e12d-3375">photocard licence</span></span> 
- <span data-ttu-id="7e12d-3376">learner drivers</span><span class="sxs-lookup"><span data-stu-id="7e12d-3376">learner drivers</span></span> 
- <span data-ttu-id="7e12d-3377">licence holder</span><span class="sxs-lookup"><span data-stu-id="7e12d-3377">licence holder</span></span> 
- <span data-ttu-id="7e12d-3378">licence holders</span><span class="sxs-lookup"><span data-stu-id="7e12d-3378">licence holders</span></span> 
- <span data-ttu-id="7e12d-3379">driving licences</span><span class="sxs-lookup"><span data-stu-id="7e12d-3379">driving licences</span></span> 
- <span data-ttu-id="7e12d-3380">driving licence</span><span class="sxs-lookup"><span data-stu-id="7e12d-3380">driving licence</span></span> 
- <span data-ttu-id="7e12d-3381">dual control car</span><span class="sxs-lookup"><span data-stu-id="7e12d-3381">dual control car</span></span> 
   
## <a name="uk-electoral-roll-number"></a><span data-ttu-id="7e12d-p142">Regno Unito - Numero di iscrizione alle liste elettorali</span><span class="sxs-lookup"><span data-stu-id="7e12d-p142">U.K. Electoral Roll Number</span></span>

### <a name="format"></a><span data-ttu-id="7e12d-3384">Formato</span><span class="sxs-lookup"><span data-stu-id="7e12d-3384">Format</span></span>

<span data-ttu-id="7e12d-3385">Due lettere seguite da 1-4 cifre</span><span class="sxs-lookup"><span data-stu-id="7e12d-3385">Two letters followed by 1-4 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="7e12d-3386">Modello</span><span class="sxs-lookup"><span data-stu-id="7e12d-3386">Pattern</span></span>

<span data-ttu-id="7e12d-3387">Due lettere (senza distinzione fra maiuscole/minuscole) seguite da 1-4 numeri</span><span class="sxs-lookup"><span data-stu-id="7e12d-3387">Two letters (not case sensitive) followed by 1-4 numbers</span></span>

### <a name="checksum"></a><span data-ttu-id="7e12d-3388">Checksum</span><span class="sxs-lookup"><span data-stu-id="7e12d-3388">Checksum</span></span>

<span data-ttu-id="7e12d-3389">No</span><span class="sxs-lookup"><span data-stu-id="7e12d-3389">No</span></span>

### <a name="definition"></a><span data-ttu-id="7e12d-3390">Definizione</span><span class="sxs-lookup"><span data-stu-id="7e12d-3390">Definition</span></span>

<span data-ttu-id="7e12d-3391">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="7e12d-3391">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="7e12d-3392">L'espressione regolare Regex_uk_electoral restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="7e12d-3392">The regular expression Regex_uk_electoral finds content that matches the pattern.</span></span>
- <span data-ttu-id="7e12d-3393">Viene trovata una parola chiave da Keyword_uk_electoral.</span><span class="sxs-lookup"><span data-stu-id="7e12d-3393">A keyword from Keyword_uk_electoral is found.</span></span>

```xml
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

### <a name="keywords"></a><span data-ttu-id="7e12d-3394">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="7e12d-3394">Keywords</span></span>

#### <a name="keyword_uk_electoral"></a><span data-ttu-id="7e12d-3395">Keyword_uk_electoral</span><span class="sxs-lookup"><span data-stu-id="7e12d-3395">Keyword_uk_electoral</span></span>

- <span data-ttu-id="7e12d-3396">council nomination</span><span class="sxs-lookup"><span data-stu-id="7e12d-3396">council nomination</span></span> 
- <span data-ttu-id="7e12d-3397">nomination form</span><span class="sxs-lookup"><span data-stu-id="7e12d-3397">nomination form</span></span> 
- <span data-ttu-id="7e12d-3398">electoral register</span><span class="sxs-lookup"><span data-stu-id="7e12d-3398">electoral register</span></span> 
- <span data-ttu-id="7e12d-3399">electoral roll</span><span class="sxs-lookup"><span data-stu-id="7e12d-3399">electoral roll</span></span>

   
## <a name="uk-national-health-service-number"></a><span data-ttu-id="7e12d-p143">Regno Unito - Codice del servizio sanitario nazionale</span><span class="sxs-lookup"><span data-stu-id="7e12d-p143">U.K. National Health Service Number</span></span>

### <a name="format"></a><span data-ttu-id="7e12d-3402">Formato</span><span class="sxs-lookup"><span data-stu-id="7e12d-3402">Format</span></span>

<span data-ttu-id="7e12d-3403">10-17 cifre separate da spazi</span><span class="sxs-lookup"><span data-stu-id="7e12d-3403">10-17 digits separated by spaces</span></span>

### <a name="pattern"></a><span data-ttu-id="7e12d-3404">Modello</span><span class="sxs-lookup"><span data-stu-id="7e12d-3404">Pattern</span></span>

<span data-ttu-id="7e12d-3405">10-17 cifre:</span><span class="sxs-lookup"><span data-stu-id="7e12d-3405">10-17 digits:</span></span>
- <span data-ttu-id="7e12d-3406">3 o 10 cifre</span><span class="sxs-lookup"><span data-stu-id="7e12d-3406">Either 3 or 10 digits</span></span> 
- <span data-ttu-id="7e12d-3407">Uno spazio</span><span class="sxs-lookup"><span data-stu-id="7e12d-3407">A space</span></span> 
- <span data-ttu-id="7e12d-3408">Tre cifre</span><span class="sxs-lookup"><span data-stu-id="7e12d-3408">Three digits</span></span> 
- <span data-ttu-id="7e12d-3409">Uno spazio</span><span class="sxs-lookup"><span data-stu-id="7e12d-3409">A space</span></span> 
- <span data-ttu-id="7e12d-3410">Quattro cifre</span><span class="sxs-lookup"><span data-stu-id="7e12d-3410">Four digits</span></span>

### <a name="checksum"></a><span data-ttu-id="7e12d-3411">Checksum</span><span class="sxs-lookup"><span data-stu-id="7e12d-3411">Checksum</span></span>

<span data-ttu-id="7e12d-3412">Sì</span><span class="sxs-lookup"><span data-stu-id="7e12d-3412">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="7e12d-3413">Definizione</span><span class="sxs-lookup"><span data-stu-id="7e12d-3413">Definition</span></span>

<span data-ttu-id="7e12d-3414">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="7e12d-3414">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="7e12d-3415">La funzione Func_uk_nhs_number restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="7e12d-3415">The function Func_uk_nhs_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="7e12d-3416">Si verifica una delle situazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="7e12d-3416">One of the following is true:</span></span>
    - <span data-ttu-id="7e12d-3417">Viene trovata una parola chiave da Keyword_uk_nhs_number.</span><span class="sxs-lookup"><span data-stu-id="7e12d-3417">A keyword from Keyword_uk_nhs_number is found.</span></span>
    - <span data-ttu-id="7e12d-3418">Viene trovata una parola chiave da Keyword_uk_nhs_number1.</span><span class="sxs-lookup"><span data-stu-id="7e12d-3418">A keyword from Keyword_uk_nhs_number1 is found.</span></span>
    - <span data-ttu-id="7e12d-3419">Viene trovata una parola chiave da Keyword_uk_nhs_number_dob.</span><span class="sxs-lookup"><span data-stu-id="7e12d-3419">A keyword from Keyword_uk_nhs_number_dob is found.</span></span>
- <span data-ttu-id="7e12d-3420">Il checksum ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="7e12d-3420">The checksum passes.</span></span>

```xml
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

### <a name="keywords"></a><span data-ttu-id="7e12d-3421">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="7e12d-3421">Keywords</span></span>
   
#### <a name="keyword_uk_nhs_number"></a><span data-ttu-id="7e12d-3422">Keyword_uk_nhs_number</span><span class="sxs-lookup"><span data-stu-id="7e12d-3422">Keyword_uk_nhs_number</span></span>

- <span data-ttu-id="7e12d-3423">national health service</span><span class="sxs-lookup"><span data-stu-id="7e12d-3423">national health service</span></span> 
- <span data-ttu-id="7e12d-3424">NHS</span><span class="sxs-lookup"><span data-stu-id="7e12d-3424">nhs</span></span> 
- <span data-ttu-id="7e12d-3425">health services authority</span><span class="sxs-lookup"><span data-stu-id="7e12d-3425">health services authority</span></span> 
- <span data-ttu-id="7e12d-3426">health authority</span><span class="sxs-lookup"><span data-stu-id="7e12d-3426">health authority</span></span>

#### <a name="keyword_uk_nhs_number1"></a><span data-ttu-id="7e12d-3427">Keyword_uk_nhs_number1</span><span class="sxs-lookup"><span data-stu-id="7e12d-3427">Keyword_uk_nhs_number1</span></span>

- <span data-ttu-id="7e12d-3428">patient id</span><span class="sxs-lookup"><span data-stu-id="7e12d-3428">patient id</span></span> 
- <span data-ttu-id="7e12d-3429">patient identification</span><span class="sxs-lookup"><span data-stu-id="7e12d-3429">patient identification</span></span> 
- <span data-ttu-id="7e12d-3430">patient no</span><span class="sxs-lookup"><span data-stu-id="7e12d-3430">patient no</span></span> 
- <span data-ttu-id="7e12d-3431">patient number</span><span class="sxs-lookup"><span data-stu-id="7e12d-3431">patient number</span></span>

#### <a name="keyword_uk_nhs_number_dob"></a><span data-ttu-id="7e12d-3432">Keyword_uk_nhs_number_dob</span><span class="sxs-lookup"><span data-stu-id="7e12d-3432">Keyword_uk_nhs_number_dob</span></span>

- <span data-ttu-id="7e12d-3433">GP</span><span class="sxs-lookup"><span data-stu-id="7e12d-3433">GP</span></span> 
- <span data-ttu-id="7e12d-3434">DOB</span><span class="sxs-lookup"><span data-stu-id="7e12d-3434">DOB</span></span> 
- <span data-ttu-id="7e12d-3435">D. O. B</span><span class="sxs-lookup"><span data-stu-id="7e12d-3435">D.O.B</span></span> 
- <span data-ttu-id="7e12d-3436">Date of Birth</span><span class="sxs-lookup"><span data-stu-id="7e12d-3436">Date of Birth</span></span> 
- <span data-ttu-id="7e12d-3437">Birth Date</span><span class="sxs-lookup"><span data-stu-id="7e12d-3437">Birth Date</span></span> 
   
## <a name="uk-national-insurance-number-nino"></a><span data-ttu-id="7e12d-p144">Regno Unito - Numero di assicurazione nazionale (NINO)</span><span class="sxs-lookup"><span data-stu-id="7e12d-p144">U.K. National Insurance Number (NINO)</span></span>

### <a name="format"></a><span data-ttu-id="7e12d-3440">Formato</span><span class="sxs-lookup"><span data-stu-id="7e12d-3440">Format</span></span>

<span data-ttu-id="7e12d-3441">7 caratteri o 9 caratteri separati da spazi o trattini</span><span class="sxs-lookup"><span data-stu-id="7e12d-3441">7 characters or 9 characters separated by spaces or dashes</span></span>

### <a name="pattern"></a><span data-ttu-id="7e12d-3442">Modello</span><span class="sxs-lookup"><span data-stu-id="7e12d-3442">Pattern</span></span>

<span data-ttu-id="7e12d-3443">Due modelli possibili:</span><span class="sxs-lookup"><span data-stu-id="7e12d-3443">Two possible patterns:</span></span>

- <span data-ttu-id="7e12d-3444">Due lettere (NINOs valido utilizza solo alcuni caratteri in questo prefisso, che questo modello convalida; senza distinzione tra maiuscole e minuscole)</span><span class="sxs-lookup"><span data-stu-id="7e12d-3444">Two letters (valid NINOs use only certain characters in this prefix, which this pattern validates; not case sensitive)</span></span>
- <span data-ttu-id="7e12d-3445">Sei cifre</span><span class="sxs-lookup"><span data-stu-id="7e12d-3445">Six digits</span></span>
- <span data-ttu-id="7e12d-3446">' A ',' B ',' c'o ' d'(come il prefisso, solo alcuni caratteri sono consentiti nel suffisso, senza distinzione tra maiuscole e minuscole)</span><span class="sxs-lookup"><span data-stu-id="7e12d-3446">Either 'A', 'B', 'C', or 'D' (like the prefix, only certain characters are allowed in the suffix; not case sensitive)</span></span>

<span data-ttu-id="7e12d-3447">O</span><span class="sxs-lookup"><span data-stu-id="7e12d-3447">OR</span></span>

- <span data-ttu-id="7e12d-3448">Due lettere</span><span class="sxs-lookup"><span data-stu-id="7e12d-3448">Two letters</span></span>
- <span data-ttu-id="7e12d-3449">Uno spazio o un trattino</span><span class="sxs-lookup"><span data-stu-id="7e12d-3449">A space or dash</span></span>
- <span data-ttu-id="7e12d-3450">Due cifre</span><span class="sxs-lookup"><span data-stu-id="7e12d-3450">Two digits</span></span>
- <span data-ttu-id="7e12d-3451">Uno spazio o un trattino</span><span class="sxs-lookup"><span data-stu-id="7e12d-3451">A space or dash</span></span>
- <span data-ttu-id="7e12d-3452">Due cifre</span><span class="sxs-lookup"><span data-stu-id="7e12d-3452">Two digits</span></span>
- <span data-ttu-id="7e12d-3453">Uno spazio o un trattino</span><span class="sxs-lookup"><span data-stu-id="7e12d-3453">A space or dash</span></span>
- <span data-ttu-id="7e12d-3454">Due cifre</span><span class="sxs-lookup"><span data-stu-id="7e12d-3454">Two digits</span></span>
- <span data-ttu-id="7e12d-3455">Uno spazio o un trattino</span><span class="sxs-lookup"><span data-stu-id="7e12d-3455">A space or dash</span></span>
- <span data-ttu-id="7e12d-3456">' A ',' B ',' c'o ' d'</span><span class="sxs-lookup"><span data-stu-id="7e12d-3456">Either 'A', 'B', 'C', or 'D'</span></span>

### <a name="checksum"></a><span data-ttu-id="7e12d-3457">Checksum</span><span class="sxs-lookup"><span data-stu-id="7e12d-3457">Checksum</span></span>

<span data-ttu-id="7e12d-3458">No</span><span class="sxs-lookup"><span data-stu-id="7e12d-3458">No</span></span>

### <a name="definition"></a><span data-ttu-id="7e12d-3459">Definizione</span><span class="sxs-lookup"><span data-stu-id="7e12d-3459">Definition</span></span>

<span data-ttu-id="7e12d-3460">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="7e12d-3460">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="7e12d-3461">La funzione Func_uk_nino restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="7e12d-3461">The function Func_uk_nino finds content that matches the pattern.</span></span>
- <span data-ttu-id="7e12d-3462">Viene trovata una parola chiave da Keyword_uk_nino.</span><span class="sxs-lookup"><span data-stu-id="7e12d-3462">A keyword from Keyword_uk_nino is found.</span></span>

<span data-ttu-id="7e12d-3463">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="7e12d-3463">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="7e12d-3464">La funzione Func_uk_nino restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="7e12d-3464">The function Func_uk_nino finds content that matches the pattern.</span></span>
- <span data-ttu-id="7e12d-3465">Non vengono trovate parole chiave da Keyword_uk_nino.</span><span class="sxs-lookup"><span data-stu-id="7e12d-3465">No keyword from Keyword_uk_nino is found.</span></span>

```xml
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

### <a name="keywords"></a><span data-ttu-id="7e12d-3466">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="7e12d-3466">Keywords</span></span>

#### <a name="keyword_uk_nino"></a><span data-ttu-id="7e12d-3467">Keyword_uk_nino</span><span class="sxs-lookup"><span data-stu-id="7e12d-3467">Keyword_uk_nino</span></span>

- <span data-ttu-id="7e12d-3468">national insurance number</span><span class="sxs-lookup"><span data-stu-id="7e12d-3468">national insurance number</span></span> 
- <span data-ttu-id="7e12d-3469">national insurance contributions</span><span class="sxs-lookup"><span data-stu-id="7e12d-3469">national insurance contributions</span></span> 
- <span data-ttu-id="7e12d-3470">protection act</span><span class="sxs-lookup"><span data-stu-id="7e12d-3470">protection act</span></span> 
- <span data-ttu-id="7e12d-3471">Insurance</span><span class="sxs-lookup"><span data-stu-id="7e12d-3471">insurance</span></span> 
- <span data-ttu-id="7e12d-3472">social security number</span><span class="sxs-lookup"><span data-stu-id="7e12d-3472">social security number</span></span> 
- <span data-ttu-id="7e12d-3473">insurance application</span><span class="sxs-lookup"><span data-stu-id="7e12d-3473">insurance application</span></span> 
- <span data-ttu-id="7e12d-3474">medical application</span><span class="sxs-lookup"><span data-stu-id="7e12d-3474">medical application</span></span> 
- <span data-ttu-id="7e12d-3475">social insurance</span><span class="sxs-lookup"><span data-stu-id="7e12d-3475">social insurance</span></span> 
- <span data-ttu-id="7e12d-3476">medical attention</span><span class="sxs-lookup"><span data-stu-id="7e12d-3476">medical attention</span></span> 
- <span data-ttu-id="7e12d-3477">social security</span><span class="sxs-lookup"><span data-stu-id="7e12d-3477">social security</span></span> 
- <span data-ttu-id="7e12d-3478">great britain</span><span class="sxs-lookup"><span data-stu-id="7e12d-3478">great britain</span></span> 
- <span data-ttu-id="7e12d-3479">Insurance</span><span class="sxs-lookup"><span data-stu-id="7e12d-3479">insurance</span></span>    
   
## <a name="us--uk-passport-number"></a><span data-ttu-id="7e12d-p145">Stati Uniti/Regno Unito - Numero di passaporto</span><span class="sxs-lookup"><span data-stu-id="7e12d-p145">U.S. / U.K. Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="7e12d-3482">Formato</span><span class="sxs-lookup"><span data-stu-id="7e12d-3482">Format</span></span>

<span data-ttu-id="7e12d-3483">9 cifre</span><span class="sxs-lookup"><span data-stu-id="7e12d-3483">Nine digits</span></span>

### <a name="pattern"></a><span data-ttu-id="7e12d-3484">Modello</span><span class="sxs-lookup"><span data-stu-id="7e12d-3484">Pattern</span></span>

<span data-ttu-id="7e12d-3485">9 cifre consecutive</span><span class="sxs-lookup"><span data-stu-id="7e12d-3485">Nine consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="7e12d-3486">Checksum</span><span class="sxs-lookup"><span data-stu-id="7e12d-3486">Checksum</span></span>

<span data-ttu-id="7e12d-3487">No</span><span class="sxs-lookup"><span data-stu-id="7e12d-3487">No</span></span>

### <a name="definition"></a><span data-ttu-id="7e12d-3488">Definizione</span><span class="sxs-lookup"><span data-stu-id="7e12d-3488">Definition</span></span>

<span data-ttu-id="7e12d-3489">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="7e12d-3489">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="7e12d-3490">La funzione Func_usa_uk_passport restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="7e12d-3490">The function Func_usa_uk_passport finds content that matches the pattern.</span></span>
- <span data-ttu-id="7e12d-3491">Viene trovata una parola chiave da Keyword_passport.</span><span class="sxs-lookup"><span data-stu-id="7e12d-3491">A keyword from Keyword_passport is found.</span></span>

```xml
<Entity id="178ec42a-18b4-47cc-85c7-d62c92fd67f8" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_usa_uk_passport" />
        <Match idRef="Keyword_passport" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="7e12d-3492">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="7e12d-3492">Keywords</span></span>

#### <a name="keyword_passport"></a><span data-ttu-id="7e12d-3493">Keyword_passport</span><span class="sxs-lookup"><span data-stu-id="7e12d-3493">Keyword_passport</span></span>

- <span data-ttu-id="7e12d-3494">Passport Number</span><span class="sxs-lookup"><span data-stu-id="7e12d-3494">Passport Number</span></span> 
- <span data-ttu-id="7e12d-3495">Passport No</span><span class="sxs-lookup"><span data-stu-id="7e12d-3495">Passport No</span></span> 
- <span data-ttu-id="7e12d-3496">Passport#</span><span class="sxs-lookup"><span data-stu-id="7e12d-3496">Passport #</span></span> 
- <span data-ttu-id="7e12d-3497">Passaporto #</span><span class="sxs-lookup"><span data-stu-id="7e12d-3497">Passport#</span></span> 
- <span data-ttu-id="7e12d-3498">PassportID</span><span class="sxs-lookup"><span data-stu-id="7e12d-3498">PassportID</span></span> 
- <span data-ttu-id="7e12d-3499">Passportno</span><span class="sxs-lookup"><span data-stu-id="7e12d-3499">Passportno</span></span> 
- <span data-ttu-id="7e12d-3500">passportnumber</span><span class="sxs-lookup"><span data-stu-id="7e12d-3500">passportnumber</span></span> 
- <span data-ttu-id="7e12d-3501">パスポート</span><span class="sxs-lookup"><span data-stu-id="7e12d-3501">パスポート</span></span> 
- <span data-ttu-id="7e12d-3502">パスポート番号</span><span class="sxs-lookup"><span data-stu-id="7e12d-3502">パスポート番号</span></span> 
- <span data-ttu-id="7e12d-3503">パスポートのNum</span><span class="sxs-lookup"><span data-stu-id="7e12d-3503">パスポートのNum</span></span> 
- <span data-ttu-id="7e12d-3504">パスポート＃</span><span class="sxs-lookup"><span data-stu-id="7e12d-3504">パスポート＃</span></span> 
- <span data-ttu-id="7e12d-3505">Numéro de passeport</span><span class="sxs-lookup"><span data-stu-id="7e12d-3505">Numéro de passeport</span></span> 
- <span data-ttu-id="7e12d-3506">Passeport n °</span><span class="sxs-lookup"><span data-stu-id="7e12d-3506">Passeport n °</span></span> 
- <span data-ttu-id="7e12d-3507">Passeport Non</span><span class="sxs-lookup"><span data-stu-id="7e12d-3507">Passeport Non</span></span> 
- <span data-ttu-id="7e12d-3508">Passeport#</span><span class="sxs-lookup"><span data-stu-id="7e12d-3508">Passeport #</span></span> 
- <span data-ttu-id="7e12d-3509">Passeport #</span><span class="sxs-lookup"><span data-stu-id="7e12d-3509">Passeport#</span></span> 
- <span data-ttu-id="7e12d-3510">PasseportNon</span><span class="sxs-lookup"><span data-stu-id="7e12d-3510">PasseportNon</span></span> 
- <span data-ttu-id="7e12d-3511">Passeportn °</span><span class="sxs-lookup"><span data-stu-id="7e12d-3511">Passeportn °</span></span> 
   
## <a name="us-bank-account-number"></a><span data-ttu-id="7e12d-3512">Stati Uniti - Numero di conto bancario</span><span class="sxs-lookup"><span data-stu-id="7e12d-3512">U.S. Bank Account Number</span></span>

### <a name="format"></a><span data-ttu-id="7e12d-3513">Formato</span><span class="sxs-lookup"><span data-stu-id="7e12d-3513">Format</span></span>

<span data-ttu-id="7e12d-3514">8-17 cifre</span><span class="sxs-lookup"><span data-stu-id="7e12d-3514">8-17 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="7e12d-3515">Modello</span><span class="sxs-lookup"><span data-stu-id="7e12d-3515">Pattern</span></span>

<span data-ttu-id="7e12d-3516">8-17 cifre consecutive</span><span class="sxs-lookup"><span data-stu-id="7e12d-3516">8-17 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="7e12d-3517">Checksum</span><span class="sxs-lookup"><span data-stu-id="7e12d-3517">Checksum</span></span>

<span data-ttu-id="7e12d-3518">No</span><span class="sxs-lookup"><span data-stu-id="7e12d-3518">No</span></span>

### <a name="definition"></a><span data-ttu-id="7e12d-3519">Definizione</span><span class="sxs-lookup"><span data-stu-id="7e12d-3519">Definition</span></span>

<span data-ttu-id="7e12d-3520">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="7e12d-3520">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="7e12d-3521">L'espressione regolare Regex_usa_bank_account_number restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="7e12d-3521">The regular expression Regex_usa_bank_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="7e12d-3522">Viene trovata una parola chiave da Keyword_usa_Bank_Account.</span><span class="sxs-lookup"><span data-stu-id="7e12d-3522">A keyword from Keyword_usa_Bank_Account is found.</span></span>

```xml
<!-- U.S. Bank Account Number -->
<Entity id="a2ce32a8-f935-4bb6-8e96-2a5157672e2c" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_usa_bank_account_number" />
        <Match idRef="Keyword_usa_Bank_Account" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="7e12d-3523">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="7e12d-3523">Keywords</span></span>

#### <a name="keyword_usa_bank_account"></a><span data-ttu-id="7e12d-3524">Keyword_usa_Bank_Account</span><span class="sxs-lookup"><span data-stu-id="7e12d-3524">Keyword_usa_Bank_Account</span></span>

- <span data-ttu-id="7e12d-3525">Checking Account Number</span><span class="sxs-lookup"><span data-stu-id="7e12d-3525">Checking Account Number</span></span> 
- <span data-ttu-id="7e12d-3526">Checking Account</span><span class="sxs-lookup"><span data-stu-id="7e12d-3526">Checking Account</span></span> 
- <span data-ttu-id="7e12d-3527">Checking Account #</span><span class="sxs-lookup"><span data-stu-id="7e12d-3527">Checking Account #</span></span> 
- <span data-ttu-id="7e12d-3528">Checking Acct Number</span><span class="sxs-lookup"><span data-stu-id="7e12d-3528">Checking Acct Number</span></span> 
- <span data-ttu-id="7e12d-3529">Checking Acct #</span><span class="sxs-lookup"><span data-stu-id="7e12d-3529">Checking Acct #</span></span> 
- <span data-ttu-id="7e12d-3530">Checking Acct No.</span><span class="sxs-lookup"><span data-stu-id="7e12d-3530">Checking Acct No.</span></span> 
- <span data-ttu-id="7e12d-3531">Checking Account No.</span><span class="sxs-lookup"><span data-stu-id="7e12d-3531">Checking Account No.</span></span> 
- <span data-ttu-id="7e12d-3532">Bank Account Number</span><span class="sxs-lookup"><span data-stu-id="7e12d-3532">Bank Account Number</span></span> 
- <span data-ttu-id="7e12d-3533">Bank Account #</span><span class="sxs-lookup"><span data-stu-id="7e12d-3533">Bank Account #</span></span> 
- <span data-ttu-id="7e12d-3534">Bank Acct Number</span><span class="sxs-lookup"><span data-stu-id="7e12d-3534">Bank Acct Number</span></span> 
- <span data-ttu-id="7e12d-3535">Bank Acct #</span><span class="sxs-lookup"><span data-stu-id="7e12d-3535">Bank Acct #</span></span> 
- <span data-ttu-id="7e12d-3536">Bank Acct No.</span><span class="sxs-lookup"><span data-stu-id="7e12d-3536">Bank Acct No.</span></span> 
- <span data-ttu-id="7e12d-3537">Bank Account No.</span><span class="sxs-lookup"><span data-stu-id="7e12d-3537">Bank Account No.</span></span> 
- <span data-ttu-id="7e12d-3538">Savings Account Number</span><span class="sxs-lookup"><span data-stu-id="7e12d-3538">Savings Account Number</span></span> 
- <span data-ttu-id="7e12d-3539">Savings Account.</span><span class="sxs-lookup"><span data-stu-id="7e12d-3539">Savings Account.</span></span> 
- <span data-ttu-id="7e12d-3540">Savings Account #</span><span class="sxs-lookup"><span data-stu-id="7e12d-3540">Savings Account #</span></span> 
- <span data-ttu-id="7e12d-3541">Savings Acct Number</span><span class="sxs-lookup"><span data-stu-id="7e12d-3541">Savings Acct Number</span></span> 
- <span data-ttu-id="7e12d-3542">Savings Acct #</span><span class="sxs-lookup"><span data-stu-id="7e12d-3542">Savings Acct #</span></span> 
- <span data-ttu-id="7e12d-3543">Savings Acct No.</span><span class="sxs-lookup"><span data-stu-id="7e12d-3543">Savings Acct No.</span></span> 
- <span data-ttu-id="7e12d-3544">Savings Account No.</span><span class="sxs-lookup"><span data-stu-id="7e12d-3544">Savings Account No.</span></span> 
- <span data-ttu-id="7e12d-3545">Debit Account Number</span><span class="sxs-lookup"><span data-stu-id="7e12d-3545">Debit Account Number</span></span> 
- <span data-ttu-id="7e12d-3546">Debit Account</span><span class="sxs-lookup"><span data-stu-id="7e12d-3546">Debit Account</span></span> 
- <span data-ttu-id="7e12d-3547">Debit Account #</span><span class="sxs-lookup"><span data-stu-id="7e12d-3547">Debit Account #</span></span> 
- <span data-ttu-id="7e12d-3548">Debit Acct Number</span><span class="sxs-lookup"><span data-stu-id="7e12d-3548">Debit Acct Number</span></span> 
- <span data-ttu-id="7e12d-3549">Debit Acct #</span><span class="sxs-lookup"><span data-stu-id="7e12d-3549">Debit Acct #</span></span> 
- <span data-ttu-id="7e12d-3550">Debit Acct No.</span><span class="sxs-lookup"><span data-stu-id="7e12d-3550">Debit Acct No.</span></span> 
- <span data-ttu-id="7e12d-3551">Debit Account No.</span><span class="sxs-lookup"><span data-stu-id="7e12d-3551">Debit Account No.</span></span> 
   
## <a name="us-drivers-license-number"></a><span data-ttu-id="7e12d-3552">Stati Uniti - Numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="7e12d-3552">U.S. Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="7e12d-3553">Formato</span><span class="sxs-lookup"><span data-stu-id="7e12d-3553">Format</span></span>

<span data-ttu-id="7e12d-3554">Varia in base allo stato</span><span class="sxs-lookup"><span data-stu-id="7e12d-3554">Depends on the state</span></span>

### <a name="pattern"></a><span data-ttu-id="7e12d-3555">Modello</span><span class="sxs-lookup"><span data-stu-id="7e12d-3555">Pattern</span></span>

<span data-ttu-id="7e12d-3556">Varia in base allo stato. Ad esempio, per New York:</span><span class="sxs-lookup"><span data-stu-id="7e12d-3556">Depends on the state -- for example, New York:</span></span>
- <span data-ttu-id="7e12d-3557">Nove cifre formattate come ddd ddd ddd corrisponderanno.</span><span class="sxs-lookup"><span data-stu-id="7e12d-3557">Nine digits formatted like ddd ddd ddd will match.</span></span>
- <span data-ttu-id="7e12d-3558">Nove cifre come ddddddddd non corrispondono.</span><span class="sxs-lookup"><span data-stu-id="7e12d-3558">Nine digits like ddddddddd will not match.</span></span>

### <a name="checksum"></a><span data-ttu-id="7e12d-3559">Checksum</span><span class="sxs-lookup"><span data-stu-id="7e12d-3559">Checksum</span></span>

<span data-ttu-id="7e12d-3560">No</span><span class="sxs-lookup"><span data-stu-id="7e12d-3560">No</span></span>

### <a name="definition"></a><span data-ttu-id="7e12d-3561">Definizione</span><span class="sxs-lookup"><span data-stu-id="7e12d-3561">Definition</span></span>

<span data-ttu-id="7e12d-3562">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="7e12d-3562">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="7e12d-3563">La funzione Func_new_york_drivers_license_number restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="7e12d-3563">The function Func_new_york_drivers_license_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="7e12d-3564">Viene trovata una parola chiave da Keyword_[state_name]_drivers_license_name.</span><span class="sxs-lookup"><span data-stu-id="7e12d-3564">A keyword from Keyword_[state_name]_drivers_license_name is found.</span></span>
- <span data-ttu-id="7e12d-3565">Viene trovata una parola chiave da Keyword_us_drivers_license.</span><span class="sxs-lookup"><span data-stu-id="7e12d-3565">A keyword from Keyword_us_drivers_license is found.</span></span>

<span data-ttu-id="7e12d-3566">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 65%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="7e12d-3566">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="7e12d-3567">La funzione Func_new_york_drivers_license_number restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="7e12d-3567">The function Func_new_york_drivers_license_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="7e12d-3568">Viene trovata una parola chiave da Keyword_[state_name]_drivers_license_name.</span><span class="sxs-lookup"><span data-stu-id="7e12d-3568">A keyword from Keyword_[state_name]_drivers_license_name is found.</span></span>
- <span data-ttu-id="7e12d-3569">Viene trovata una parola chiave da Keyword_us_drivers_license_abbreviations.</span><span class="sxs-lookup"><span data-stu-id="7e12d-3569">A keyword from Keyword_us_drivers_license_abbreviations is found.</span></span>
- <span data-ttu-id="7e12d-3570">Non vengono trovate parole chiave da Keyword_us_drivers_license.</span><span class="sxs-lookup"><span data-stu-id="7e12d-3570">No keyword from Keyword_us_drivers_license is found.</span></span>

```xml
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

### <a name="keywords"></a><span data-ttu-id="7e12d-3571">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="7e12d-3571">Keywords</span></span>

#### <a name="keyword_us_drivers_license_abbreviations"></a><span data-ttu-id="7e12d-3572">Keyword_us_drivers_license_abbreviations</span><span class="sxs-lookup"><span data-stu-id="7e12d-3572">Keyword_us_drivers_license_abbreviations</span></span>

- <span data-ttu-id="7e12d-3573">DL</span><span class="sxs-lookup"><span data-stu-id="7e12d-3573">DL</span></span> 
- <span data-ttu-id="7e12d-3574">DLS</span><span class="sxs-lookup"><span data-stu-id="7e12d-3574">DLS</span></span> 
- <span data-ttu-id="7e12d-3575">CDL</span><span class="sxs-lookup"><span data-stu-id="7e12d-3575">CDL</span></span> 
- <span data-ttu-id="7e12d-3576">CDLS</span><span class="sxs-lookup"><span data-stu-id="7e12d-3576">CDLS</span></span> 
- <span data-ttu-id="7e12d-3577">ID</span><span class="sxs-lookup"><span data-stu-id="7e12d-3577">ID</span></span> 
- <span data-ttu-id="7e12d-3578">ID</span><span class="sxs-lookup"><span data-stu-id="7e12d-3578">IDs</span></span> 
- <span data-ttu-id="7e12d-3579">DL #</span><span class="sxs-lookup"><span data-stu-id="7e12d-3579">DL#</span></span> 
- <span data-ttu-id="7e12d-3580">DLS #</span><span class="sxs-lookup"><span data-stu-id="7e12d-3580">DLS#</span></span> 
- <span data-ttu-id="7e12d-3581">CDL #</span><span class="sxs-lookup"><span data-stu-id="7e12d-3581">CDL#</span></span> 
- <span data-ttu-id="7e12d-3582">CDLS #</span><span class="sxs-lookup"><span data-stu-id="7e12d-3582">CDLS#</span></span> 
- <span data-ttu-id="7e12d-3583">ID #</span><span class="sxs-lookup"><span data-stu-id="7e12d-3583">ID#</span></span>
- <span data-ttu-id="7e12d-3584">ID #</span><span class="sxs-lookup"><span data-stu-id="7e12d-3584">IDs#</span></span> 
- <span data-ttu-id="7e12d-3585">ID number</span><span class="sxs-lookup"><span data-stu-id="7e12d-3585">ID number</span></span> 
- <span data-ttu-id="7e12d-3586">ID numbers</span><span class="sxs-lookup"><span data-stu-id="7e12d-3586">ID numbers</span></span> 
- <span data-ttu-id="7e12d-3587">DRIVER'LIC</span><span class="sxs-lookup"><span data-stu-id="7e12d-3587">LIC</span></span> 
- <span data-ttu-id="7e12d-3588">DRIVER'LIC #</span><span class="sxs-lookup"><span data-stu-id="7e12d-3588">LIC#</span></span> 

#### <a name="keyword_us_drivers_license"></a><span data-ttu-id="7e12d-3589">Keyword_us_drivers_license</span><span class="sxs-lookup"><span data-stu-id="7e12d-3589">Keyword_us_drivers_license</span></span>

- <span data-ttu-id="7e12d-3590">DriverLic</span><span class="sxs-lookup"><span data-stu-id="7e12d-3590">DriverLic</span></span> 
- <span data-ttu-id="7e12d-3591">DriverLics</span><span class="sxs-lookup"><span data-stu-id="7e12d-3591">DriverLics</span></span> 
- <span data-ttu-id="7e12d-3592">DriverLicense</span><span class="sxs-lookup"><span data-stu-id="7e12d-3592">DriverLicense</span></span> 
- <span data-ttu-id="7e12d-3593">DriverLicenses</span><span class="sxs-lookup"><span data-stu-id="7e12d-3593">DriverLicenses</span></span> 
- <span data-ttu-id="7e12d-3594">Driver Lic</span><span class="sxs-lookup"><span data-stu-id="7e12d-3594">Driver Lic</span></span> 
- <span data-ttu-id="7e12d-3595">Driver Lics</span><span class="sxs-lookup"><span data-stu-id="7e12d-3595">Driver Lics</span></span> 
- <span data-ttu-id="7e12d-3596">Driver License</span><span class="sxs-lookup"><span data-stu-id="7e12d-3596">Driver License</span></span> 
- <span data-ttu-id="7e12d-3597">Driver Licenses</span><span class="sxs-lookup"><span data-stu-id="7e12d-3597">Driver Licenses</span></span> 
- <span data-ttu-id="7e12d-3598">DriversLic</span><span class="sxs-lookup"><span data-stu-id="7e12d-3598">DriversLic</span></span> 
- <span data-ttu-id="7e12d-3599">DriversLics</span><span class="sxs-lookup"><span data-stu-id="7e12d-3599">DriversLics</span></span> 
- <span data-ttu-id="7e12d-3600">DriversLicense</span><span class="sxs-lookup"><span data-stu-id="7e12d-3600">DriversLicense</span></span> 
- <span data-ttu-id="7e12d-3601">DriversLicenses</span><span class="sxs-lookup"><span data-stu-id="7e12d-3601">DriversLicenses</span></span> 
- <span data-ttu-id="7e12d-3602">Drivers Lic</span><span class="sxs-lookup"><span data-stu-id="7e12d-3602">Drivers Lic</span></span> 
- <span data-ttu-id="7e12d-3603">Drivers Lics</span><span class="sxs-lookup"><span data-stu-id="7e12d-3603">Drivers Lics</span></span> 
- <span data-ttu-id="7e12d-3604">Drivers License</span><span class="sxs-lookup"><span data-stu-id="7e12d-3604">Drivers License</span></span> 
- <span data-ttu-id="7e12d-3605">Drivers Licenses</span><span class="sxs-lookup"><span data-stu-id="7e12d-3605">Drivers Licenses</span></span> 
- <span data-ttu-id="7e12d-3606">Driver'Lic</span><span class="sxs-lookup"><span data-stu-id="7e12d-3606">Driver'Lic</span></span> 
- <span data-ttu-id="7e12d-3607">Driver ' LiCS</span><span class="sxs-lookup"><span data-stu-id="7e12d-3607">Driver'Lics</span></span> 
- <span data-ttu-id="7e12d-3608">Driver ' License</span><span class="sxs-lookup"><span data-stu-id="7e12d-3608">Driver'License</span></span> 
- <span data-ttu-id="7e12d-3609">Driver ' licenses</span><span class="sxs-lookup"><span data-stu-id="7e12d-3609">Driver'Licenses</span></span> 
- <span data-ttu-id="7e12d-3610">Driver'Lic</span><span class="sxs-lookup"><span data-stu-id="7e12d-3610">Driver' Lic</span></span> 
- <span data-ttu-id="7e12d-3611">Driver' Lics</span><span class="sxs-lookup"><span data-stu-id="7e12d-3611">Driver' Lics</span></span> 
- <span data-ttu-id="7e12d-3612">Driver' License</span><span class="sxs-lookup"><span data-stu-id="7e12d-3612">Driver' License</span></span> 
- <span data-ttu-id="7e12d-3613">Driver' Licenses</span><span class="sxs-lookup"><span data-stu-id="7e12d-3613">Driver' Licenses</span></span>
- <span data-ttu-id="7e12d-3614">Driver'sLic</span><span class="sxs-lookup"><span data-stu-id="7e12d-3614">Driver'sLic</span></span> 
- <span data-ttu-id="7e12d-3615">Driver'sLics</span><span class="sxs-lookup"><span data-stu-id="7e12d-3615">Driver'sLics</span></span> 
- <span data-ttu-id="7e12d-3616">Secondola</span><span class="sxs-lookup"><span data-stu-id="7e12d-3616">Driver'sLicense</span></span> 
- <span data-ttu-id="7e12d-3617">Driver'sLicenses</span><span class="sxs-lookup"><span data-stu-id="7e12d-3617">Driver'sLicenses</span></span> 
- <span data-ttu-id="7e12d-3618">Driver's Lic</span><span class="sxs-lookup"><span data-stu-id="7e12d-3618">Driver's Lic</span></span> 
- <span data-ttu-id="7e12d-3619">Driver's Lics</span><span class="sxs-lookup"><span data-stu-id="7e12d-3619">Driver's Lics</span></span> 
- <span data-ttu-id="7e12d-3620">Driver's License</span><span class="sxs-lookup"><span data-stu-id="7e12d-3620">Driver's License</span></span> 
- <span data-ttu-id="7e12d-3621">Driver's Licenses</span><span class="sxs-lookup"><span data-stu-id="7e12d-3621">Driver's Licenses</span></span> 
- <span data-ttu-id="7e12d-3622">identification number</span><span class="sxs-lookup"><span data-stu-id="7e12d-3622">identification number</span></span> 
- <span data-ttu-id="7e12d-3623">identification numbers</span><span class="sxs-lookup"><span data-stu-id="7e12d-3623">identification numbers</span></span> 
- <span data-ttu-id="7e12d-3624">identification#</span><span class="sxs-lookup"><span data-stu-id="7e12d-3624">identification #</span></span> 
- <span data-ttu-id="7e12d-3625">id card</span><span class="sxs-lookup"><span data-stu-id="7e12d-3625">id card</span></span> 
- <span data-ttu-id="7e12d-3626">id cards</span><span class="sxs-lookup"><span data-stu-id="7e12d-3626">id cards</span></span> 
- <span data-ttu-id="7e12d-3627">identification card</span><span class="sxs-lookup"><span data-stu-id="7e12d-3627">identification card</span></span> 
- <span data-ttu-id="7e12d-3628">identification cards</span><span class="sxs-lookup"><span data-stu-id="7e12d-3628">identification cards</span></span> 
- <span data-ttu-id="7e12d-3629">DriverLic #</span><span class="sxs-lookup"><span data-stu-id="7e12d-3629">DriverLic#</span></span> 
- <span data-ttu-id="7e12d-3630">DriverLics #</span><span class="sxs-lookup"><span data-stu-id="7e12d-3630">DriverLics#</span></span> 
- <span data-ttu-id="7e12d-3631">DriverLicense #</span><span class="sxs-lookup"><span data-stu-id="7e12d-3631">DriverLicense#</span></span> 
- <span data-ttu-id="7e12d-3632">DriverLicenses #</span><span class="sxs-lookup"><span data-stu-id="7e12d-3632">DriverLicenses#</span></span> 
- <span data-ttu-id="7e12d-3633">Driver Lic#</span><span class="sxs-lookup"><span data-stu-id="7e12d-3633">Driver Lic#</span></span> 
- <span data-ttu-id="7e12d-3634">Driver Lics#</span><span class="sxs-lookup"><span data-stu-id="7e12d-3634">Driver Lics#</span></span> 
- <span data-ttu-id="7e12d-3635">Driver License#</span><span class="sxs-lookup"><span data-stu-id="7e12d-3635">Driver License#</span></span> 
- <span data-ttu-id="7e12d-3636">Driver Licenses#</span><span class="sxs-lookup"><span data-stu-id="7e12d-3636">Driver Licenses#</span></span> 
- <span data-ttu-id="7e12d-3637">DriversLic #</span><span class="sxs-lookup"><span data-stu-id="7e12d-3637">DriversLic#</span></span> 
- <span data-ttu-id="7e12d-3638">DriversLics #</span><span class="sxs-lookup"><span data-stu-id="7e12d-3638">DriversLics#</span></span> 
- <span data-ttu-id="7e12d-3639">DriversLicense #</span><span class="sxs-lookup"><span data-stu-id="7e12d-3639">DriversLicense#</span></span> 
- <span data-ttu-id="7e12d-3640">DriversLicenses #</span><span class="sxs-lookup"><span data-stu-id="7e12d-3640">DriversLicenses#</span></span> 
- <span data-ttu-id="7e12d-3641">Drivers Lic#</span><span class="sxs-lookup"><span data-stu-id="7e12d-3641">Drivers Lic#</span></span> 
- <span data-ttu-id="7e12d-3642">Drivers Lics#</span><span class="sxs-lookup"><span data-stu-id="7e12d-3642">Drivers Lics#</span></span> 
- <span data-ttu-id="7e12d-3643">Drivers License#</span><span class="sxs-lookup"><span data-stu-id="7e12d-3643">Drivers License#</span></span> 
- <span data-ttu-id="7e12d-3644">Drivers Licenses#</span><span class="sxs-lookup"><span data-stu-id="7e12d-3644">Drivers Licenses#</span></span> 
- <span data-ttu-id="7e12d-3645">Driver'Lic #</span><span class="sxs-lookup"><span data-stu-id="7e12d-3645">Driver'Lic#</span></span> 
- <span data-ttu-id="7e12d-3646">Driver ' LiCS #</span><span class="sxs-lookup"><span data-stu-id="7e12d-3646">Driver'Lics#</span></span> 
- <span data-ttu-id="7e12d-3647">Driver ' License #</span><span class="sxs-lookup"><span data-stu-id="7e12d-3647">Driver'License#</span></span> 
- <span data-ttu-id="7e12d-3648">Driver ' licenses #</span><span class="sxs-lookup"><span data-stu-id="7e12d-3648">Driver'Licenses#</span></span> 
- <span data-ttu-id="7e12d-3649">Driver' Lic#</span><span class="sxs-lookup"><span data-stu-id="7e12d-3649">Driver' Lic#</span></span> 
- <span data-ttu-id="7e12d-3650">Driver' Lics#</span><span class="sxs-lookup"><span data-stu-id="7e12d-3650">Driver' Lics#</span></span> 
- <span data-ttu-id="7e12d-3651">Driver' License#</span><span class="sxs-lookup"><span data-stu-id="7e12d-3651">Driver' License#</span></span> 
- <span data-ttu-id="7e12d-3652">Driver' Licenses#</span><span class="sxs-lookup"><span data-stu-id="7e12d-3652">Driver' Licenses#</span></span> 
- <span data-ttu-id="7e12d-3653">Driver'sLic #</span><span class="sxs-lookup"><span data-stu-id="7e12d-3653">Driver'sLic#</span></span> 
- <span data-ttu-id="7e12d-3654">Driver'sLics #</span><span class="sxs-lookup"><span data-stu-id="7e12d-3654">Driver'sLics#</span></span> 
- <span data-ttu-id="7e12d-3655">Secondola #</span><span class="sxs-lookup"><span data-stu-id="7e12d-3655">Driver'sLicense#</span></span> 
- <span data-ttu-id="7e12d-3656">Driver'sLicenses #</span><span class="sxs-lookup"><span data-stu-id="7e12d-3656">Driver'sLicenses#</span></span> 
- <span data-ttu-id="7e12d-3657">Driver's Lic#</span><span class="sxs-lookup"><span data-stu-id="7e12d-3657">Driver's Lic#</span></span> 
- <span data-ttu-id="7e12d-3658">Driver's Lics#</span><span class="sxs-lookup"><span data-stu-id="7e12d-3658">Driver's Lics#</span></span> 
- <span data-ttu-id="7e12d-3659">Driver's License#</span><span class="sxs-lookup"><span data-stu-id="7e12d-3659">Driver's License#</span></span> 
- <span data-ttu-id="7e12d-3660">Driver's Licenses#</span><span class="sxs-lookup"><span data-stu-id="7e12d-3660">Driver's Licenses#</span></span> 
- <span data-ttu-id="7e12d-3661">id card#</span><span class="sxs-lookup"><span data-stu-id="7e12d-3661">id card#</span></span> 
- <span data-ttu-id="7e12d-3662">id cards#</span><span class="sxs-lookup"><span data-stu-id="7e12d-3662">id cards#</span></span> 
- <span data-ttu-id="7e12d-3663">identification card#</span><span class="sxs-lookup"><span data-stu-id="7e12d-3663">identification card#</span></span> 
- <span data-ttu-id="7e12d-3664">identification cards#</span><span class="sxs-lookup"><span data-stu-id="7e12d-3664">identification cards#</span></span> 


#### <a name="keyword_state_name_drivers_license_name"></a><span data-ttu-id="7e12d-3665">Keyword_[state_name]_drivers_license_name</span><span class="sxs-lookup"><span data-stu-id="7e12d-3665">Keyword_[state_name]_drivers_license_name</span></span>

- <span data-ttu-id="7e12d-3666">Abbreviazione dello stato (ad esempio, "NY")</span><span class="sxs-lookup"><span data-stu-id="7e12d-3666">State abbreviation (for example, "NY")</span></span> 
- <span data-ttu-id="7e12d-3667">Nome dello stato (ad esempio, "New York")</span><span class="sxs-lookup"><span data-stu-id="7e12d-3667">State name (for example, "New York")</span></span>    
   
## <a name="us-individual-taxpayer-identification-number-itin"></a><span data-ttu-id="7e12d-3668">Stati Uniti - Codice identificativo del contribuente individuale (ITIN)</span><span class="sxs-lookup"><span data-stu-id="7e12d-3668">U.S. Individual Taxpayer Identification Number (ITIN)</span></span>

### <a name="format"></a><span data-ttu-id="7e12d-3669">Formato</span><span class="sxs-lookup"><span data-stu-id="7e12d-3669">Format</span></span>

<span data-ttu-id="7e12d-3670">Nove cifre che iniziano con "9" e contengono un "7" o un "8" come quarta cifra. Può essere formattato con spazi e trattini (facoltativo)</span><span class="sxs-lookup"><span data-stu-id="7e12d-3670">Nine digits that start with a "9" and contain a "7" or "8" as the fourth digit, optionally formatted with spaces or dashes</span></span>

### <a name="pattern"></a><span data-ttu-id="7e12d-3671">Modello</span><span class="sxs-lookup"><span data-stu-id="7e12d-3671">Pattern</span></span>

<span data-ttu-id="7e12d-3672">Formattato</span><span class="sxs-lookup"><span data-stu-id="7e12d-3672">Formatted:</span></span>
- <span data-ttu-id="7e12d-3673">La cifra "9"</span><span class="sxs-lookup"><span data-stu-id="7e12d-3673">The digit "9"</span></span> 
- <span data-ttu-id="7e12d-3674">Due cifre</span><span class="sxs-lookup"><span data-stu-id="7e12d-3674">Two digits</span></span> 
- <span data-ttu-id="7e12d-3675">Uno spazio o un trattino</span><span class="sxs-lookup"><span data-stu-id="7e12d-3675">A space or dash</span></span> 
- <span data-ttu-id="7e12d-3676">Un "7" o un "8"</span><span class="sxs-lookup"><span data-stu-id="7e12d-3676">A "7" or "8"</span></span> 
- <span data-ttu-id="7e12d-3677">Una cifra</span><span class="sxs-lookup"><span data-stu-id="7e12d-3677">A digit</span></span> 
- <span data-ttu-id="7e12d-3678">Uno spazio o un trattino</span><span class="sxs-lookup"><span data-stu-id="7e12d-3678">A space, or dash</span></span> 
- <span data-ttu-id="7e12d-3679">Quattro cifre</span><span class="sxs-lookup"><span data-stu-id="7e12d-3679">Four digits</span></span>

<span data-ttu-id="7e12d-3680">Formattato</span><span class="sxs-lookup"><span data-stu-id="7e12d-3680">Unformatted:</span></span>
- <span data-ttu-id="7e12d-3681">La cifra "9"</span><span class="sxs-lookup"><span data-stu-id="7e12d-3681">The digit "9"</span></span> 
- <span data-ttu-id="7e12d-3682">Due cifre</span><span class="sxs-lookup"><span data-stu-id="7e12d-3682">Two digits</span></span> 
- <span data-ttu-id="7e12d-3683">Un "7" o un "8"</span><span class="sxs-lookup"><span data-stu-id="7e12d-3683">A "7" or "8"</span></span> 
- <span data-ttu-id="7e12d-3684">Cinque cifre</span><span class="sxs-lookup"><span data-stu-id="7e12d-3684">Five digits</span></span>

### <a name="checksum"></a><span data-ttu-id="7e12d-3685">Checksum</span><span class="sxs-lookup"><span data-stu-id="7e12d-3685">Checksum</span></span>

<span data-ttu-id="7e12d-3686">No</span><span class="sxs-lookup"><span data-stu-id="7e12d-3686">No</span></span>

### <a name="definition"></a><span data-ttu-id="7e12d-3687">Definizione</span><span class="sxs-lookup"><span data-stu-id="7e12d-3687">Definition</span></span>

<span data-ttu-id="7e12d-3688">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="7e12d-3688">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="7e12d-3689">La funzione Func_formatted_itin restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="7e12d-3689">The function Func_formatted_itin finds content that matches the pattern.</span></span>
- <span data-ttu-id="7e12d-3690">Si verifica almeno una delle situazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="7e12d-3690">At least one of the following is true:</span></span>
    - <span data-ttu-id="7e12d-3691">Viene trovata una parola chiave da Keyword_itin.</span><span class="sxs-lookup"><span data-stu-id="7e12d-3691">A keyword from Keyword_itin is found.</span></span>
    - <span data-ttu-id="7e12d-3692">La funzione Func_us_address rileva un indirizzo nel formato di data corretto.</span><span class="sxs-lookup"><span data-stu-id="7e12d-3692">The function Func_us_address finds an address in the right date format.</span></span>
    - <span data-ttu-id="7e12d-3693">La funzione Func_us_date rileva una data nel formato corretto.</span><span class="sxs-lookup"><span data-stu-id="7e12d-3693">The function Func_us_date finds a date in the right date format.</span></span>
    - <span data-ttu-id="7e12d-3694">Viene trovata una parola chiave da Keyword_itin_collaborative.</span><span class="sxs-lookup"><span data-stu-id="7e12d-3694">A keyword from Keyword_itin_collaborative is found.</span></span>

<span data-ttu-id="7e12d-3695">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="7e12d-3695">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="7e12d-3696">La funzione Func_unformatted_itin restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="7e12d-3696">The function Func_unformatted_itin finds content that matches the pattern.</span></span>
- <span data-ttu-id="7e12d-3697">Si verifica almeno una delle situazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="7e12d-3697">At least one of the following is true:</span></span>
    - <span data-ttu-id="7e12d-3698">Viene trovata una parola chiave da Keyword_itin_collaborative.</span><span class="sxs-lookup"><span data-stu-id="7e12d-3698">A keyword from Keyword_itin_collaborative is found.</span></span>
    - <span data-ttu-id="7e12d-3699">La funzione Func_us_address rileva un indirizzo nel formato di data corretto.</span><span class="sxs-lookup"><span data-stu-id="7e12d-3699">The function Func_us_address finds an address in the right date format.</span></span>
    - <span data-ttu-id="7e12d-3700">La funzione Func_us_date rileva una data nel formato corretto.</span><span class="sxs-lookup"><span data-stu-id="7e12d-3700">The function Func_us_date finds a date in the right date format.</span></span>

```xml
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

### <a name="keywords"></a><span data-ttu-id="7e12d-3701">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="7e12d-3701">Keywords</span></span>

#### <a name="keyword_itin"></a><span data-ttu-id="7e12d-3702">Keyword_itin</span><span class="sxs-lookup"><span data-stu-id="7e12d-3702">Keyword_itin</span></span>

- <span data-ttu-id="7e12d-3703">contribuente</span><span class="sxs-lookup"><span data-stu-id="7e12d-3703">taxpayer</span></span> 
- <span data-ttu-id="7e12d-3704">tax id</span><span class="sxs-lookup"><span data-stu-id="7e12d-3704">tax id</span></span> 
- <span data-ttu-id="7e12d-3705">tax identification</span><span class="sxs-lookup"><span data-stu-id="7e12d-3705">tax identification</span></span> 
- <span data-ttu-id="7e12d-3706">Itin</span><span class="sxs-lookup"><span data-stu-id="7e12d-3706">itin</span></span> 
- <span data-ttu-id="7e12d-3707">SSN</span><span class="sxs-lookup"><span data-stu-id="7e12d-3707">ssn</span></span> 
- <span data-ttu-id="7e12d-3708">latta</span><span class="sxs-lookup"><span data-stu-id="7e12d-3708">tin</span></span> 
- <span data-ttu-id="7e12d-3709">social security</span><span class="sxs-lookup"><span data-stu-id="7e12d-3709">social security</span></span> 
- <span data-ttu-id="7e12d-3710">tax payer</span><span class="sxs-lookup"><span data-stu-id="7e12d-3710">tax payer</span></span> 
- <span data-ttu-id="7e12d-3711">itins</span><span class="sxs-lookup"><span data-stu-id="7e12d-3711">itins</span></span> 
- <span data-ttu-id="7e12d-3712">taxid</span><span class="sxs-lookup"><span data-stu-id="7e12d-3712">taxid</span></span> 
- <span data-ttu-id="7e12d-3713">individual taxpayer</span><span class="sxs-lookup"><span data-stu-id="7e12d-3713">individual taxpayer</span></span> 

#### <a name="keyword_itin_collaborative"></a><span data-ttu-id="7e12d-3714">Keyword_itin_collaborative</span><span class="sxs-lookup"><span data-stu-id="7e12d-3714">Keyword_itin_collaborative</span></span>

- <span data-ttu-id="7e12d-3715">License</span><span class="sxs-lookup"><span data-stu-id="7e12d-3715">License</span></span> 
- <span data-ttu-id="7e12d-3716">DL</span><span class="sxs-lookup"><span data-stu-id="7e12d-3716">DL</span></span> 
- <span data-ttu-id="7e12d-3717">DOB</span><span class="sxs-lookup"><span data-stu-id="7e12d-3717">DOB</span></span> 
- <span data-ttu-id="7e12d-3718">Data di nascita</span><span class="sxs-lookup"><span data-stu-id="7e12d-3718">Birthdate</span></span> 
- <span data-ttu-id="7e12d-3719">Compleanno</span><span class="sxs-lookup"><span data-stu-id="7e12d-3719">Birthday</span></span> 
- <span data-ttu-id="7e12d-3720">Date of Birth</span><span class="sxs-lookup"><span data-stu-id="7e12d-3720">Date of Birth</span></span> 
   
## <a name="us-social-security-number-ssn"></a><span data-ttu-id="7e12d-3721">Stati Uniti - Numero di previdenza sociale (SSN)</span><span class="sxs-lookup"><span data-stu-id="7e12d-3721">U.S. Social Security Number (SSN)</span></span>

### <a name="format"></a><span data-ttu-id="7e12d-3722">Formato</span><span class="sxs-lookup"><span data-stu-id="7e12d-3722">Format</span></span>

<span data-ttu-id="7e12d-3723">9 cifre formattate o meno</span><span class="sxs-lookup"><span data-stu-id="7e12d-3723">9 digits, which may be in a formatted or unformatted pattern</span></span>

> [!NOTE]
> <span data-ttu-id="7e12d-3724">Se emesso prima della metà del 2011, un SSN ha una formattazione complessa in cui alcune parti del numero devono rientrare in alcuni intervalli per essere valide (ma non c'è nessun checksum).</span><span class="sxs-lookup"><span data-stu-id="7e12d-3724">If issued before mid-2011, an SSN has strong formatting where certain parts of the number must fall within certain ranges to be valid (but there's no checksum).</span></span>

### <a name="pattern"></a><span data-ttu-id="7e12d-3725">Modello</span><span class="sxs-lookup"><span data-stu-id="7e12d-3725">Pattern</span></span>

<span data-ttu-id="7e12d-3726">Quattro funzioni cercano SNSS in quattro modelli diversi:</span><span class="sxs-lookup"><span data-stu-id="7e12d-3726">Four functions look for SSNs in four different patterns:</span></span>
- <span data-ttu-id="7e12d-3727">Func_ssn trova SNSS con una formattazione complessa pre2011 che è formattata con trattini o spazi (ddd-dd-dddd o ddd dd dddd)</span><span class="sxs-lookup"><span data-stu-id="7e12d-3727">Func_ssn finds SSNs with pre-2011 strong formatting that are formatted with dashes or spaces (ddd-dd-dddd OR ddd dd dddd)</span></span>
- <span data-ttu-id="7e12d-3728">Func_unformatted_ssn trova SNSS con una formattazione complessa pre2011 che non è formattata come nove cifre consecutive (ddddddddd)</span><span class="sxs-lookup"><span data-stu-id="7e12d-3728">Func_unformatted_ssn finds SSNs with pre-2011 strong formatting that are unformatted as nine consecutive digits (ddddddddd)</span></span>
- <span data-ttu-id="7e12d-3729">Func_randomized_formatted_ssn trova post-2011 SNSS formattati con trattini o spazi (ddd-dd-dddd o ddd dd dddd)</span><span class="sxs-lookup"><span data-stu-id="7e12d-3729">Func_randomized_formatted_ssn finds post-2011 SSNs that are formatted with dashes or spaces (ddd-dd-dddd OR ddd dd dddd)</span></span>
- <span data-ttu-id="7e12d-3730">Func_randomized_unformatted_ssn trova post-2011 SNSS che non sono formattati come nove cifre consecutive (ddddddddd)</span><span class="sxs-lookup"><span data-stu-id="7e12d-3730">Func_randomized_unformatted_ssn finds post-2011 SSNs that are unformatted as nine consecutive digits (ddddddddd)</span></span>

### <a name="checksum"></a><span data-ttu-id="7e12d-3731">Checksum</span><span class="sxs-lookup"><span data-stu-id="7e12d-3731">Checksum</span></span>

<span data-ttu-id="7e12d-3732">No</span><span class="sxs-lookup"><span data-stu-id="7e12d-3732">No</span></span>


### <a name="definition"></a><span data-ttu-id="7e12d-3733">Definizione</span><span class="sxs-lookup"><span data-stu-id="7e12d-3733">Definition</span></span>

<span data-ttu-id="7e12d-3734">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="7e12d-3734">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="7e12d-3735">La funzione Func_ssn restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="7e12d-3735">The function Func_ssn finds content that matches the pattern.</span></span>
- <span data-ttu-id="7e12d-3736">Viene trovata una parola chiave da Keyword_ssn.</span><span class="sxs-lookup"><span data-stu-id="7e12d-3736">A keyword from Keyword_ssn is found.</span></span>
- <span data-ttu-id="7e12d-3737">La funzione Func_us_date rileva una data nel formato corretto.</span><span class="sxs-lookup"><span data-stu-id="7e12d-3737">The function Func_us_date finds a date in the right date format.</span></span>
- <span data-ttu-id="7e12d-3738">La funzione Func_us_address trova un indirizzo nel formato corretto.</span><span class="sxs-lookup"><span data-stu-id="7e12d-3738">The function Func_us_address finds an address in the right format.</span></span>

<span data-ttu-id="7e12d-3739">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="7e12d-3739">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="7e12d-3740">La funzione Func_unformatted_ssn trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="7e12d-3740">The function Func_unformatted_ssn finds content that matches the pattern.</span></span>
- <span data-ttu-id="7e12d-3741">Viene trovata una parola chiave da Keyword_ssn.</span><span class="sxs-lookup"><span data-stu-id="7e12d-3741">A keyword from Keyword_ssn is found.</span></span>
- <span data-ttu-id="7e12d-3742">La funzione Func_us_date rileva una data nel formato corretto.</span><span class="sxs-lookup"><span data-stu-id="7e12d-3742">The function Func_us_date finds a date in the right date format.</span></span>
- <span data-ttu-id="7e12d-3743">La funzione Func_us_address trova un indirizzo nel formato corretto.</span><span class="sxs-lookup"><span data-stu-id="7e12d-3743">The function Func_us_address finds an address in the right format.</span></span>

<span data-ttu-id="7e12d-3744">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 65%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="7e12d-3744">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="7e12d-3745">La funzione Func_randomized_formatted_ssn restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="7e12d-3745">The function Func_randomized_formatted_ssn finds content that matches the pattern.</span></span>
- <span data-ttu-id="7e12d-3746">Viene trovata una parola chiave da Keyword_ssn.</span><span class="sxs-lookup"><span data-stu-id="7e12d-3746">A keyword from Keyword_ssn is found.</span></span>
- <span data-ttu-id="7e12d-3747">La funzione Func_us_date rileva una data nel formato corretto.</span><span class="sxs-lookup"><span data-stu-id="7e12d-3747">The function Func_us_date finds a date in the right date format.</span></span>
- <span data-ttu-id="7e12d-3748">La funzione Func_us_address trova un indirizzo nel formato corretto.</span><span class="sxs-lookup"><span data-stu-id="7e12d-3748">The function Func_us_address finds an address in the right format.</span></span>

<span data-ttu-id="7e12d-3749">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 55%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="7e12d-3749">A DLP policy is 55% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="7e12d-3750">La funzione Func_randomized_unformatted_ssn restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="7e12d-3750">The function Func_randomized_unformatted_ssn finds content that matches the pattern.</span></span>
- <span data-ttu-id="7e12d-3751">Viene trovata una parola chiave da Keyword_ssn.</span><span class="sxs-lookup"><span data-stu-id="7e12d-3751">A keyword from Keyword_ssn is found.</span></span>
- <span data-ttu-id="7e12d-3752">La funzione Func_us_date rileva una data nel formato corretto.</span><span class="sxs-lookup"><span data-stu-id="7e12d-3752">The function Func_us_date finds a date in the right date format.</span></span>
- <span data-ttu-id="7e12d-3753">La funzione Func_us_address trova un indirizzo nel formato corretto.</span><span class="sxs-lookup"><span data-stu-id="7e12d-3753">The function Func_us_address finds an address in the right format.</span></span>

<span data-ttu-id="7e12d-3754">Un criterio DLP è 40% fiducioso di aver rilevato questo tipo di informazioni riservate se, entro 300 caratteri:</span><span class="sxs-lookup"><span data-stu-id="7e12d-3754">A DLP policy is 40% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="7e12d-3755">La funzione Func_ssn restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="7e12d-3755">The function Func_ssn finds content that matches the pattern.</span></span>
- <span data-ttu-id="7e12d-3756">La funzione Func_unformatted_ssn non trovare contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="7e12d-3756">The function Func_unformatted_ssn does not find content that matches the pattern.</span></span>
- <span data-ttu-id="7e12d-3757">La funzione Func_randomized_unformatted_ssn non trova contenuto corrispondente al modello.</span><span class="sxs-lookup"><span data-stu-id="7e12d-3757">The function Func_randomized_unformatted_ssn does not find content that matches the pattern.</span></span>
- <span data-ttu-id="7e12d-3758">Non viene trovata una parola chiave da Keyword_ssn.</span><span class="sxs-lookup"><span data-stu-id="7e12d-3758">A keyword from Keyword_ssn is not found.</span></span>
 
<span data-ttu-id="7e12d-3759">Oppure</span><span class="sxs-lookup"><span data-stu-id="7e12d-3759">Or</span></span>

- <span data-ttu-id="7e12d-3760">La funzione Func_randomized_formatted_ssn restituisce contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="7e12d-3760">The function Func_randomized_formatted_ssn finds content that matches the pattern.</span></span>
- <span data-ttu-id="7e12d-3761">La funzione Func_unformatted_ssn non trovare contenuti che corrispondono al modello.</span><span class="sxs-lookup"><span data-stu-id="7e12d-3761">The function Func_unformatted_ssn does not find content that matches the pattern.</span></span>
- <span data-ttu-id="7e12d-3762">La funzione Func_randomized_unformatted_ssn non trova contenuto corrispondente al modello.</span><span class="sxs-lookup"><span data-stu-id="7e12d-3762">The function Func_randomized_unformatted_ssn does not find content that matches the pattern.</span></span>
- <span data-ttu-id="7e12d-3763">Non viene trovata una parola chiave da Keyword_ssn.</span><span class="sxs-lookup"><span data-stu-id="7e12d-3763">A keyword from Keyword_ssn is not found.</span></span>

```xml
<!-- U.S. Social Security Number (SSN) -->
  <Entity id="a44669fe-0d48-453d-a9b1-2cc83f2cba77" patternsProximity="300" recommendedConfidence="75">
      <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_ssn" />
        <Any minMatches="1">
          <Match idRef="Keyword_ssn" />
          <Match idRef="Func_us_date" />
          <Match idRef="Func_us_address" />
        </Any>
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_unformatted_ssn" />
        <Match idRef="Keyword_ssn" />
        <Any minMatches="1">
          <Match idRef="Func_us_date" />
          <Match idRef="Func_us_address" />
        </Any>
      </Pattern>
      <Pattern confidenceLevel="65">
        <IdMatch idRef="Func_randomized_formatted_ssn" />
        <Any minMatches="1">
          <Match idRef="Keyword_ssn" />
          <Match idRef="Func_us_date" />
          <Match idRef="Func_us_address" />
        </Any>
      </Pattern>
      <Pattern confidenceLevel="55">
        <IdMatch idRef="Func_randomized_unformatted_ssn" />
        <Match idRef="Keyword_ssn" />
        <Any minMatches="1">
          <Match idRef="Func_us_date" />
          <Match idRef="Func_us_address" />
        </Any>
      </Pattern>
      <Pattern confidenceLevel="40">
        <IdMatch idRef="Func_ssn" />
        <Any minMatches="0" maxMatches="0">
          <Match idRef="Func_unformatted_ssn" />
          <Match idRef="Func_randomized_unformatted_ssn" />
          <Match idRef="Keyword_ssn" />
        </Any>
      </Pattern>
      <Pattern confidenceLevel="40">
        <IdMatch idRef="Func_randomized_formatted_ssn" />
        <Any minMatches="0" maxMatches="0">
          <Match idRef="Func_unformatted_ssn" />
          <Match idRef="Func_randomized_unformatted_ssn" />
          <Match idRef="Keyword_ssn" />
        </Any>
      </Pattern>
    </Entity>
```

### <a name="keywords"></a><span data-ttu-id="7e12d-3764">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="7e12d-3764">Keywords</span></span>

#### <a name="keyword_ssn"></a><span data-ttu-id="7e12d-3765">Keyword_ssn</span><span class="sxs-lookup"><span data-stu-id="7e12d-3765">Keyword_ssn</span></span>

- <span data-ttu-id="7e12d-3766">Social Security</span><span class="sxs-lookup"><span data-stu-id="7e12d-3766">Social Security</span></span> 
- <span data-ttu-id="7e12d-3767">Social Security#</span><span class="sxs-lookup"><span data-stu-id="7e12d-3767">Social Security#</span></span> 
- <span data-ttu-id="7e12d-3768">Soc Sec</span><span class="sxs-lookup"><span data-stu-id="7e12d-3768">Soc Sec</span></span> 
- <span data-ttu-id="7e12d-3769">SSN</span><span class="sxs-lookup"><span data-stu-id="7e12d-3769">SSN</span></span> 
- <span data-ttu-id="7e12d-3770">SNSS</span><span class="sxs-lookup"><span data-stu-id="7e12d-3770">SSNS</span></span> 
- <span data-ttu-id="7e12d-3771">SSN #</span><span class="sxs-lookup"><span data-stu-id="7e12d-3771">SSN#</span></span> 
- <span data-ttu-id="7e12d-3772">SS #</span><span class="sxs-lookup"><span data-stu-id="7e12d-3772">SS#</span></span> 
- <span data-ttu-id="7e12d-3773">SSID</span><span class="sxs-lookup"><span data-stu-id="7e12d-3773">SSID</span></span> 
   

