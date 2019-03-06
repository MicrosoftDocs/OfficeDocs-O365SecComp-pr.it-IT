---
title: Numero di identificazione fiscale dell'Unione europea
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 8/17/2018
ms.audience: Admin
ms.topic: reference
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
description: In questo argomento viene illustrato l'aspetto di un criterio di prevenzione della perdita di dati (DLP) quando viene rilevato il tipo di informazioni riservate del numero di identificazione fiscale dell'Unione europea. Questo tipo di informazioni riservate definisce modelli, parole chiave e altre evidenze diverse per ogni paese.
ms.openlocfilehash: 4914ff078695519c2a298190d82c86a6abebceb9
ms.sourcegitcommit: ed822a776d3419853453583e882f3c61ca26d4b2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/05/2019
ms.locfileid: "30410911"
---
# <a name="eu-tax-identification-number"></a><span data-ttu-id="413a9-104">Numero di identificazione fiscale dell'Unione europea</span><span class="sxs-lookup"><span data-stu-id="413a9-104">EU Tax Identification Number</span></span>

<span data-ttu-id="413a9-105">In questo argomento viene illustrato l'aspetto di un criterio di prevenzione della perdita di dati (DLP) quando viene rilevato il tipo di informazioni riservate del numero di identificazione fiscale (TIN) dell'Unione europea.</span><span class="sxs-lookup"><span data-stu-id="413a9-105">This topic shows what a data loss prevention (DLP) policy looks for when it detects the EU Tax Identification Number (TIN) sensitive information type.</span></span> <span data-ttu-id="413a9-106">Questo tipo di informazioni riservate definisce modelli, parole chiave e altre evidenze diverse per ogni paese.</span><span class="sxs-lookup"><span data-stu-id="413a9-106">This sensitive information type defines different patterns, keywords, and other evidence for each country.</span></span>
  
## <a name="austria"></a><span data-ttu-id="413a9-107">Austria</span><span class="sxs-lookup"><span data-stu-id="413a9-107">Austria</span></span>

### <a name="format"></a><span data-ttu-id="413a9-108">Formato</span><span class="sxs-lookup"><span data-stu-id="413a9-108">Format</span></span>

<span data-ttu-id="413a9-109">Nove cifre con trattino e barra di inoltro opzionali</span><span class="sxs-lookup"><span data-stu-id="413a9-109">Nine digits with optional hyphen and forward slash</span></span>
  
### <a name="pattern"></a><span data-ttu-id="413a9-110">Modello</span><span class="sxs-lookup"><span data-stu-id="413a9-110">Pattern</span></span>

<span data-ttu-id="413a9-111">Nove cifre con trattino e barra di inoltro facoltativi:</span><span class="sxs-lookup"><span data-stu-id="413a9-111">Nine digits with optional hyphen and forward slash:</span></span>
  
-  <span data-ttu-id="413a9-112">Due cifre</span><span class="sxs-lookup"><span data-stu-id="413a9-112">Two digits</span></span> 
    
- <span data-ttu-id="413a9-113">Una lineetta (facoltativa)</span><span class="sxs-lookup"><span data-stu-id="413a9-113">A hyphen (optional)</span></span>
    
- <span data-ttu-id="413a9-114">Tre cifre</span><span class="sxs-lookup"><span data-stu-id="413a9-114">Three digits</span></span>
    
- <span data-ttu-id="413a9-115">Una barra (facoltativa)</span><span class="sxs-lookup"><span data-stu-id="413a9-115">A forward slash (optional)</span></span>
    
- <span data-ttu-id="413a9-116">Quattro cifre</span><span class="sxs-lookup"><span data-stu-id="413a9-116">Four digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="413a9-117">Checksum</span><span class="sxs-lookup"><span data-stu-id="413a9-117">Checksum</span></span>

<span data-ttu-id="413a9-118">Sì</span><span class="sxs-lookup"><span data-stu-id="413a9-118">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="413a9-119">Definizione</span><span class="sxs-lookup"><span data-stu-id="413a9-119">Definition</span></span>

<span data-ttu-id="413a9-120">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="413a9-120">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="413a9-121">La funzione `Func_austria_eu_tax_file_number` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="413a9-121">The function  `Func_austria_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="413a9-122">Viene trovata una `Keywords_austria_eu_tax_file_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="413a9-122">A keyword from  `Keywords_austria_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="413a9-123">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="413a9-123">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="413a9-124">La funzione `Func_austria_eu_tax_file_number` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="413a9-124">The function  `Func_austria_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_austria_eu_tax_file_number" />
          <Match idRef="Keywords_austria_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_austria_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="413a9-125">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="413a9-125">Keywords</span></span>

#### <a name="keywordsaustriaeutaxfilenumber"></a><span data-ttu-id="413a9-126">Keywords_austria_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="413a9-126">Keywords_austria_eu_tax_file_number</span></span>

<span data-ttu-id="413a9-127">codice fiscale</span><span class="sxs-lookup"><span data-stu-id="413a9-127">tax number</span></span>
  
<span data-ttu-id="413a9-128">numero</span><span class="sxs-lookup"><span data-stu-id="413a9-128">number</span></span>
  
<span data-ttu-id="413a9-129">numero di registrazione fiscale</span><span class="sxs-lookup"><span data-stu-id="413a9-129">tax registration number</span></span>
  
<span data-ttu-id="413a9-130">tax id</span><span class="sxs-lookup"><span data-stu-id="413a9-130">tax id</span></span>
  
<span data-ttu-id="413a9-131">St.Nr.</span><span class="sxs-lookup"><span data-stu-id="413a9-131">st.nr.</span></span>
  
<span data-ttu-id="413a9-132">Steuernummer</span><span class="sxs-lookup"><span data-stu-id="413a9-132">steuernummer</span></span>
  
## <a name="belgium"></a><span data-ttu-id="413a9-133">Belgio</span><span class="sxs-lookup"><span data-stu-id="413a9-133">Belgium</span></span>

### <a name="format"></a><span data-ttu-id="413a9-134">Formato</span><span class="sxs-lookup"><span data-stu-id="413a9-134">Format</span></span>

<span data-ttu-id="413a9-135">11 cifre senza spazi e delimitatori</span><span class="sxs-lookup"><span data-stu-id="413a9-135">11 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="413a9-136">Modello</span><span class="sxs-lookup"><span data-stu-id="413a9-136">Pattern</span></span>

<span data-ttu-id="413a9-137">11 cifre:</span><span class="sxs-lookup"><span data-stu-id="413a9-137">11 digits:</span></span>
  
- <span data-ttu-id="413a9-138">Due cifre</span><span class="sxs-lookup"><span data-stu-id="413a9-138">Two digits</span></span>
    
- <span data-ttu-id="413a9-139">"0" o "1"</span><span class="sxs-lookup"><span data-stu-id="413a9-139">A "0" or "1"</span></span>
    
- <span data-ttu-id="413a9-140">Una cifra</span><span class="sxs-lookup"><span data-stu-id="413a9-140">One digit</span></span>
    
- <span data-ttu-id="413a9-141">"0" o "1" o "2" o "3"</span><span class="sxs-lookup"><span data-stu-id="413a9-141">A "0" or "1" or "2" or "3"</span></span> 
    
- <span data-ttu-id="413a9-142">Sei cifre</span><span class="sxs-lookup"><span data-stu-id="413a9-142">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="413a9-143">Checksum</span><span class="sxs-lookup"><span data-stu-id="413a9-143">Checksum</span></span>

<span data-ttu-id="413a9-144">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="413a9-144">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="413a9-145">Definizione</span><span class="sxs-lookup"><span data-stu-id="413a9-145">Definition</span></span>

<span data-ttu-id="413a9-146">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="413a9-146">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="413a9-147">L'espressione `Regex_belgium_eu_tax_file_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="413a9-147">The regular expression  `Regex_belgium_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="413a9-148">Viene trovata una `Keywords_belgium_eu_tax_file_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="413a9-148">A keyword from  `Keywords_belgium_eu_tax_file_number` is found.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_belgium_eu_tax_file_number" />
          <Match idRef="Keywords_belgium_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="413a9-149">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="413a9-149">Keywords</span></span>

#### <a name="keywordsbelgiumeutaxfilenumber"></a><span data-ttu-id="413a9-150">Keywords_belgium_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="413a9-150">Keywords_belgium_eu_tax_file_number</span></span>

<span data-ttu-id="413a9-151">codice fiscale</span><span class="sxs-lookup"><span data-stu-id="413a9-151">tax number</span></span>
  
<span data-ttu-id="413a9-152">numero di registrazione nazionale</span><span class="sxs-lookup"><span data-stu-id="413a9-152">national registration number</span></span>
  
<span data-ttu-id="413a9-153">numero di registrazione fiscale</span><span class="sxs-lookup"><span data-stu-id="413a9-153">tax registration number</span></span>
  
<span data-ttu-id="413a9-154">tax id</span><span class="sxs-lookup"><span data-stu-id="413a9-154">tax id</span></span>
  
<span data-ttu-id="413a9-155">NIF</span><span class="sxs-lookup"><span data-stu-id="413a9-155">nif</span></span>
  
<span data-ttu-id="413a9-156">NIF</span><span class="sxs-lookup"><span data-stu-id="413a9-156">nif#</span></span>
  
<span data-ttu-id="413a9-157">numéro de Registre National</span><span class="sxs-lookup"><span data-stu-id="413a9-157">numéro de registre national</span></span>
  
<span data-ttu-id="413a9-158">numéro d'identification fiscale</span><span class="sxs-lookup"><span data-stu-id="413a9-158">numéro d'identification fiscale</span></span>
  
## <a name="bulgaria"></a><span data-ttu-id="413a9-159">Bulgaria</span><span class="sxs-lookup"><span data-stu-id="413a9-159">Bulgaria</span></span>

### <a name="format"></a><span data-ttu-id="413a9-160">Formato</span><span class="sxs-lookup"><span data-stu-id="413a9-160">Format</span></span>

<span data-ttu-id="413a9-161">Dieci cifre senza spazi e delimitatori</span><span class="sxs-lookup"><span data-stu-id="413a9-161">Ten digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="413a9-162">Modello</span><span class="sxs-lookup"><span data-stu-id="413a9-162">Pattern</span></span>

<span data-ttu-id="413a9-163">10 cifre</span><span class="sxs-lookup"><span data-stu-id="413a9-163">10 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="413a9-164">Checksum</span><span class="sxs-lookup"><span data-stu-id="413a9-164">Checksum</span></span>

<span data-ttu-id="413a9-165">Sì</span><span class="sxs-lookup"><span data-stu-id="413a9-165">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="413a9-166">Definizione</span><span class="sxs-lookup"><span data-stu-id="413a9-166">Definition</span></span>

<span data-ttu-id="413a9-167">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="413a9-167">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="413a9-168">La funzione `Func_bulgaria_eu_tax_file_number` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="413a9-168">The function  `Func_bulgaria_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="413a9-169">Viene trovata una `Keywords_bulgaria_eu_tax_file_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="413a9-169">A keyword from  `Keywords_bulgaria_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="413a9-170">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="413a9-170">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="413a9-171">La funzione `Func_bulgaria_eu_tax_file_number` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="413a9-171">The function  `Func_bulgaria_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_bulgaria_eu_tax_file_number" />
          <Match idRef="Keywords_bulgaria_eu_tax_file_number" />
        </Pattern>
 <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_bulgaria_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="413a9-172">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="413a9-172">Keywords</span></span>

#### <a name="keywordsbulgariaeutaxfilenumber"></a><span data-ttu-id="413a9-173">Keywords_bulgaria_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="413a9-173">Keywords_bulgaria_eu_tax_file_number</span></span>

<span data-ttu-id="413a9-174">bucn</span><span class="sxs-lookup"><span data-stu-id="413a9-174">bucn</span></span>
  
<span data-ttu-id="413a9-175">numero civile uniforme</span><span class="sxs-lookup"><span data-stu-id="413a9-175">uniform civil number</span></span>
  
<span data-ttu-id="413a9-176">bucn #</span><span class="sxs-lookup"><span data-stu-id="413a9-176">bucn#</span></span>
  
<span data-ttu-id="413a9-177">uniformcivilnumber #</span><span class="sxs-lookup"><span data-stu-id="413a9-177">uniformcivilnumber#</span></span>
  
<span data-ttu-id="413a9-178">ID civile uniforme</span><span class="sxs-lookup"><span data-stu-id="413a9-178">uniform civil id</span></span>
  
<span data-ttu-id="413a9-179">uniforme civile No</span><span class="sxs-lookup"><span data-stu-id="413a9-179">uniform civil no</span></span>
  
<span data-ttu-id="413a9-180">EGN</span><span class="sxs-lookup"><span data-stu-id="413a9-180">egn</span></span>
  
<span data-ttu-id="413a9-181">numero civile uniforme bulgaro</span><span class="sxs-lookup"><span data-stu-id="413a9-181">bulgarian uniform civil number</span></span>
  
<span data-ttu-id="413a9-182">uniformcivilno #</span><span class="sxs-lookup"><span data-stu-id="413a9-182">uniformcivilno#</span></span>
  
<span data-ttu-id="413a9-183">EGN</span><span class="sxs-lookup"><span data-stu-id="413a9-183">egn#</span></span>
  
<span data-ttu-id="413a9-184">униформ граждански Номер</span><span class="sxs-lookup"><span data-stu-id="413a9-184">униформ граждански номер</span></span>
  
<span data-ttu-id="413a9-185">ID униформ</span><span class="sxs-lookup"><span data-stu-id="413a9-185">униформ id</span></span>
  
<span data-ttu-id="413a9-186">ID граждански униформ</span><span class="sxs-lookup"><span data-stu-id="413a9-186">униформ граждански id</span></span>
  
<span data-ttu-id="413a9-187">униформ граждански не</span><span class="sxs-lookup"><span data-stu-id="413a9-187">униформ граждански не</span></span>
  
## <a name="croatia"></a><span data-ttu-id="413a9-188">Croazia</span><span class="sxs-lookup"><span data-stu-id="413a9-188">Croatia</span></span>

### <a name="format"></a><span data-ttu-id="413a9-189">Formato</span><span class="sxs-lookup"><span data-stu-id="413a9-189">Format</span></span>

<span data-ttu-id="413a9-190">11 cifre senza spazi o delimitatori</span><span class="sxs-lookup"><span data-stu-id="413a9-190">11 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="413a9-191">Modello</span><span class="sxs-lookup"><span data-stu-id="413a9-191">Pattern</span></span>

<span data-ttu-id="413a9-192">11 cifre:</span><span class="sxs-lookup"><span data-stu-id="413a9-192">11 digits:</span></span>
  
- <span data-ttu-id="413a9-193">Dieci cifre, scelte casualmente</span><span class="sxs-lookup"><span data-stu-id="413a9-193">Ten digits, randomly chosen</span></span>
    
- <span data-ttu-id="413a9-194">Una cifra di controllo</span><span class="sxs-lookup"><span data-stu-id="413a9-194">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="413a9-195">Checksum</span><span class="sxs-lookup"><span data-stu-id="413a9-195">Checksum</span></span>

<span data-ttu-id="413a9-196">Sì</span><span class="sxs-lookup"><span data-stu-id="413a9-196">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="413a9-197">Definizione</span><span class="sxs-lookup"><span data-stu-id="413a9-197">Definition</span></span>

<span data-ttu-id="413a9-198">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="413a9-198">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="413a9-199">La funzione `Func_croatia_eu_tax_file_number` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="413a9-199">The function  `Func_croatia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="413a9-200">Viene trovata una `Keywords_croatia_eu_tax_file_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="413a9-200">A keyword from  `Keywords_croatia_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="413a9-201">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="413a9-201">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="413a9-202">La funzione `Func_croatia_eu_tax_file_number` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="413a9-202">The function  `Func_croatia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_croatia_eu_tax_file_number" />
          <Match idRef="Keywords_croatia_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_croatia_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="413a9-203">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="413a9-203">Keywords</span></span>

#### <a name="keywordscroatiaeutaxfilenumber"></a><span data-ttu-id="413a9-204">Keywords_croatia_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="413a9-204">Keywords_croatia_eu_tax_file_number</span></span>

<span data-ttu-id="413a9-205">codice fiscale</span><span class="sxs-lookup"><span data-stu-id="413a9-205">tax number</span></span>
  
<span data-ttu-id="413a9-206">imposte</span><span class="sxs-lookup"><span data-stu-id="413a9-206">tax</span></span>
  
<span data-ttu-id="413a9-207">tax id</span><span class="sxs-lookup"><span data-stu-id="413a9-207">tax id</span></span>
  
<span data-ttu-id="413a9-208">OID</span><span class="sxs-lookup"><span data-stu-id="413a9-208">oid</span></span>
  
<span data-ttu-id="413a9-209">OID</span><span class="sxs-lookup"><span data-stu-id="413a9-209">oid#</span></span>
  
<span data-ttu-id="413a9-210">Porezni broj</span><span class="sxs-lookup"><span data-stu-id="413a9-210">porezni broj</span></span>
  
## <a name="cyprus"></a><span data-ttu-id="413a9-211">Cipro</span><span class="sxs-lookup"><span data-stu-id="413a9-211">Cyprus</span></span>

### <a name="format"></a><span data-ttu-id="413a9-212">Formato</span><span class="sxs-lookup"><span data-stu-id="413a9-212">Format</span></span>

<span data-ttu-id="413a9-213">Otto cifre e una lettera nel modello specificato</span><span class="sxs-lookup"><span data-stu-id="413a9-213">Eight digits and one letter in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="413a9-214">Modello</span><span class="sxs-lookup"><span data-stu-id="413a9-214">Pattern</span></span>

<span data-ttu-id="413a9-215">Otto cifre e una lettera:</span><span class="sxs-lookup"><span data-stu-id="413a9-215">Eight digits and one letter:</span></span>
  
-  <span data-ttu-id="413a9-216">Un "0"</span><span class="sxs-lookup"><span data-stu-id="413a9-216">A "0"</span></span> 
    
- <span data-ttu-id="413a9-217">Sette cifre</span><span class="sxs-lookup"><span data-stu-id="413a9-217">Seven digits</span></span>
    
- <span data-ttu-id="413a9-218">Una lettera (senza distinzione tra maiuscole e minuscole)</span><span class="sxs-lookup"><span data-stu-id="413a9-218">One letter (not case-sensitive)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="413a9-219">Checksum</span><span class="sxs-lookup"><span data-stu-id="413a9-219">Checksum</span></span>

<span data-ttu-id="413a9-220">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="413a9-220">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="413a9-221">Definizione</span><span class="sxs-lookup"><span data-stu-id="413a9-221">Definition</span></span>

<span data-ttu-id="413a9-222">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="413a9-222">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="413a9-223">La funzione `Func_cyprus_eu_tax_file_number` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="413a9-223">The function  `Func_cyprus_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="413a9-224">Viene trovata una `Keywords_cyprus_eu_tax_file_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="413a9-224">A keyword from  `Keywords_cyprus_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="413a9-225">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="413a9-225">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="413a9-226">La funzione `Func_cyprus_eu_tax_file_number` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="413a9-226">The function  `Func_cyprus_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_cyprus_eu_tax_file_number" />
          <Match idRef="Keywords_cyprus_eu_tax_file_number" />
        </Pattern>
Pattern confidenceLevel="75">
          <IdMatch idRef="Func_cyprus_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="413a9-227">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="413a9-227">Keywords</span></span>

#### <a name="keywordscypruseutaxfilenumber"></a><span data-ttu-id="413a9-228">Keywords_cyprus_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="413a9-228">Keywords_cyprus_eu_tax_file_number</span></span>

<span data-ttu-id="413a9-229">codice fiscale</span><span class="sxs-lookup"><span data-stu-id="413a9-229">tax number</span></span>
  
<span data-ttu-id="413a9-230">imposte</span><span class="sxs-lookup"><span data-stu-id="413a9-230">tax</span></span>
  
<span data-ttu-id="413a9-231">tax id</span><span class="sxs-lookup"><span data-stu-id="413a9-231">tax id</span></span>
  
<span data-ttu-id="413a9-232">codice di identificazione fiscale</span><span class="sxs-lookup"><span data-stu-id="413a9-232">tax identification code</span></span>
  
<span data-ttu-id="413a9-233">TIC</span><span class="sxs-lookup"><span data-stu-id="413a9-233">tic</span></span>
  
<span data-ttu-id="413a9-234">TIC</span><span class="sxs-lookup"><span data-stu-id="413a9-234">tic#</span></span>
  
<span data-ttu-id="413a9-235">Αριθμός φορολογικού Μητρώου</span><span class="sxs-lookup"><span data-stu-id="413a9-235">αριθμός φορολογικού μητρώου</span></span>
  
<span data-ttu-id="413a9-236">φορολογική ταυτότητα</span><span class="sxs-lookup"><span data-stu-id="413a9-236">φορολογική ταυτότητα</span></span>
  
<span data-ttu-id="413a9-237">Κωδικός φορολογικού Μητρώου</span><span class="sxs-lookup"><span data-stu-id="413a9-237">κωδικός φορολογικού μητρώου</span></span>
  
## <a name="czech-republic"></a><span data-ttu-id="413a9-238">Repubblica Ceca</span><span class="sxs-lookup"><span data-stu-id="413a9-238">Czech Republic</span></span>

### <a name="format"></a><span data-ttu-id="413a9-239">Formato</span><span class="sxs-lookup"><span data-stu-id="413a9-239">Format</span></span>

<span data-ttu-id="413a9-240">Nove o dieci cifre con una barra rovesciata facoltativa</span><span class="sxs-lookup"><span data-stu-id="413a9-240">Nine or ten digits with an optional backslash</span></span>
  
### <a name="pattern"></a><span data-ttu-id="413a9-241">Modello</span><span class="sxs-lookup"><span data-stu-id="413a9-241">Pattern</span></span>

<span data-ttu-id="413a9-242">Nove o dieci cifre con un backslash facoltativo:</span><span class="sxs-lookup"><span data-stu-id="413a9-242">Nine or ten digits with an optional backslashl:</span></span>
  
- <span data-ttu-id="413a9-243">Sei cifre</span><span class="sxs-lookup"><span data-stu-id="413a9-243">Six digits</span></span> 
    
- <span data-ttu-id="413a9-244">Una barra rovesciata (facoltativa)</span><span class="sxs-lookup"><span data-stu-id="413a9-244">A backslash (optional)</span></span>
    
- <span data-ttu-id="413a9-245">Tre o quattro cifre</span><span class="sxs-lookup"><span data-stu-id="413a9-245">Three or four digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="413a9-246">Checksum</span><span class="sxs-lookup"><span data-stu-id="413a9-246">Checksum</span></span>

<span data-ttu-id="413a9-247">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="413a9-247">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="413a9-248">Definizione</span><span class="sxs-lookup"><span data-stu-id="413a9-248">Definition</span></span>

<span data-ttu-id="413a9-249">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="413a9-249">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="413a9-250">L'espressione `Regex_czech_republic_eu_tax_file_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="413a9-250">The regular expression  `Regex_czech_republic_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="413a9-251">Viene trovata una `Keywords_czech_republic_eu_tax_file_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="413a9-251">A keyword from  `Keywords_czech_republic_eu_tax_file_number` is found.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_czech_republic_eu_tax_file_number" />
          <Match idRef="Keywords_czech_republic_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="413a9-252">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="413a9-252">Keywords</span></span>

#### <a name="keywordsczechrepubliceutaxfilenumber"></a><span data-ttu-id="413a9-253">Keywords_czech_republic_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="413a9-253">Keywords_czech_republic_eu_tax_file_number</span></span>

<span data-ttu-id="413a9-254">codice fiscale</span><span class="sxs-lookup"><span data-stu-id="413a9-254">tax number</span></span>
  
<span data-ttu-id="413a9-255">imposte</span><span class="sxs-lookup"><span data-stu-id="413a9-255">tax</span></span>
  
<span data-ttu-id="413a9-256">tax id</span><span class="sxs-lookup"><span data-stu-id="413a9-256">tax id</span></span>
  
<span data-ttu-id="413a9-257">numero personale</span><span class="sxs-lookup"><span data-stu-id="413a9-257">personal number</span></span>
  
<span data-ttu-id="413a9-258">daňové číslo</span><span class="sxs-lookup"><span data-stu-id="413a9-258">daňové číslo</span></span>
  
<span data-ttu-id="413a9-259">osobní číslo</span><span class="sxs-lookup"><span data-stu-id="413a9-259">osobní číslo</span></span>
  
## <a name="denmark"></a><span data-ttu-id="413a9-260">Danimarca</span><span class="sxs-lookup"><span data-stu-id="413a9-260">Denmark</span></span>

### <a name="format"></a><span data-ttu-id="413a9-261">Formato</span><span class="sxs-lookup"><span data-stu-id="413a9-261">Format</span></span>

<span data-ttu-id="413a9-262">Dieci cifre contenenti un segno meno</span><span class="sxs-lookup"><span data-stu-id="413a9-262">Ten digits containing a hyphen</span></span>
  
### <a name="pattern"></a><span data-ttu-id="413a9-263">Modello</span><span class="sxs-lookup"><span data-stu-id="413a9-263">Pattern</span></span>

<span data-ttu-id="413a9-264">Dieci cifre contenenti un segno meno:</span><span class="sxs-lookup"><span data-stu-id="413a9-264">Ten digits containing a hyphenl:</span></span>
  
-  <span data-ttu-id="413a9-265">Sei cifre che corrispondono alla data di nascita (GGMMAA)</span><span class="sxs-lookup"><span data-stu-id="413a9-265">Six digits that correspond to the birth date (DDMMYY)</span></span> 
    
- <span data-ttu-id="413a9-266">Una lineetta</span><span class="sxs-lookup"><span data-stu-id="413a9-266">A hyphen</span></span>
    
- <span data-ttu-id="413a9-267">Quattro cifre che corrispondono a un numero di sequenza in cui la prima cifra corrisponde al secolo di nascita e l'ultima cifra corrisponde al sesso dell'individuo (dispari per il maschio e anche per le femmine)</span><span class="sxs-lookup"><span data-stu-id="413a9-267">Four digits that correspond to a sequence number where the first digit corresponds to the century of birth and the last digit corresponds to the individual's gender (odd for male and even for female)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="413a9-268">Checksum</span><span class="sxs-lookup"><span data-stu-id="413a9-268">Checksum</span></span>

<span data-ttu-id="413a9-269">Sì</span><span class="sxs-lookup"><span data-stu-id="413a9-269">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="413a9-270">Definizione</span><span class="sxs-lookup"><span data-stu-id="413a9-270">Definition</span></span>

<span data-ttu-id="413a9-271">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="413a9-271">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="413a9-272">La funzione `Func_denmark_eu_tax_file_number` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="413a9-272">The function  `Func_denmark_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="413a9-273">Viene trovata una `Keywords_denmark_eu_tax_file_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="413a9-273">A keyword from  `Keywords_denmark_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="413a9-274">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="413a9-274">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="413a9-275">La funzione `Func_denmark_eu_tax_file_number` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="413a9-275">The function  `Func_denmark_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_denmark_eu_tax_file_number" />
          <Match idRef="Keywords_denmark_eu_tax_file_number" />
        </Pattern> 
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_denmark_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="413a9-276">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="413a9-276">Keywords</span></span>

#### <a name="keywordsdenmarkeutaxfilenumber"></a><span data-ttu-id="413a9-277">Keywords_denmark_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="413a9-277">Keywords_denmark_eu_tax_file_number</span></span>

<span data-ttu-id="413a9-278">codice fiscale</span><span class="sxs-lookup"><span data-stu-id="413a9-278">tax number</span></span>
  
<span data-ttu-id="413a9-279">imposte</span><span class="sxs-lookup"><span data-stu-id="413a9-279">tax</span></span>
  
<span data-ttu-id="413a9-280">tax id</span><span class="sxs-lookup"><span data-stu-id="413a9-280">tax id</span></span>
  
<span data-ttu-id="413a9-281">numero CPR</span><span class="sxs-lookup"><span data-stu-id="413a9-281">cpr number</span></span>
  
<span data-ttu-id="413a9-282">CPR</span><span class="sxs-lookup"><span data-stu-id="413a9-282">cpr#</span></span>
  
<span data-ttu-id="413a9-283">Nummer di pattinaggio</span><span class="sxs-lookup"><span data-stu-id="413a9-283">skat nummer</span></span>
  
<span data-ttu-id="413a9-284">ID pattina</span><span class="sxs-lookup"><span data-stu-id="413a9-284">skat id</span></span>
  
## <a name="estonia"></a><span data-ttu-id="413a9-285">Estonia</span><span class="sxs-lookup"><span data-stu-id="413a9-285">Estonia</span></span>

### <a name="format"></a><span data-ttu-id="413a9-286">Formato</span><span class="sxs-lookup"><span data-stu-id="413a9-286">Format</span></span>

<span data-ttu-id="413a9-287">11 cifre senza spazi o delimitatori</span><span class="sxs-lookup"><span data-stu-id="413a9-287">11 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="413a9-288">Modello</span><span class="sxs-lookup"><span data-stu-id="413a9-288">Pattern</span></span>

<span data-ttu-id="413a9-289">11 cifre:</span><span class="sxs-lookup"><span data-stu-id="413a9-289">11 digits:</span></span>
  
-  <span data-ttu-id="413a9-290">Una cifra che corrisponde al sesso e al secolo del parto, in cui un numero dispari indica il maschio e il numero pari indica la femmina come segue: 1,2 per il XIX secolo; 3,4 per il XX secolo; e 5,6 per il XXI secolo</span><span class="sxs-lookup"><span data-stu-id="413a9-290">One digit that corresponds to gender and century of birth where an odd number indicates male and the even number indicates female as follows: 1, 2 for the 19th century; 3, 4 for the 20th century; and 5, 6 for the 21st century</span></span> 
    
- <span data-ttu-id="413a9-291">Sei cifre che corrispondono alla data di nascita (AAMMGG)</span><span class="sxs-lookup"><span data-stu-id="413a9-291">Six digits that correspond to birth date (YYMMDD)</span></span>
    
- <span data-ttu-id="413a9-292">Tre cifre che corrispondono a un numero di serie che separa le persone nate nella stessa data</span><span class="sxs-lookup"><span data-stu-id="413a9-292">Three digits that correspond to a serial number separating persons born on the same date</span></span>
    
- <span data-ttu-id="413a9-293">Una cifra di controllo</span><span class="sxs-lookup"><span data-stu-id="413a9-293">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="413a9-294">Checksum</span><span class="sxs-lookup"><span data-stu-id="413a9-294">Checksum</span></span>

<span data-ttu-id="413a9-295">Sì</span><span class="sxs-lookup"><span data-stu-id="413a9-295">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="413a9-296">Definizione</span><span class="sxs-lookup"><span data-stu-id="413a9-296">Definition</span></span>

<span data-ttu-id="413a9-297">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="413a9-297">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="413a9-298">La funzione `Func_estonia_eu_tax_file_number` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="413a9-298">The function  `Func_estonia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="413a9-299">Viene trovata una `Keywords_estonia_eu_tax_file_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="413a9-299">A keyword from  `Keywords_estonia_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="413a9-300">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="413a9-300">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="413a9-301">La funzione `Func_estonia_eu_tax_file_number` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="413a9-301">The function  `Func_estonia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_estonia_eu_tax_file_number" />
          <Match idRef="Keywords_estonia_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_estonia_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="413a9-302">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="413a9-302">Keywords</span></span>

#### <a name="keywordsestoniaeutaxfilenumber"></a><span data-ttu-id="413a9-303">Keywords_estonia_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="413a9-303">Keywords_estonia_eu_tax_file_number</span></span>

<span data-ttu-id="413a9-304">codice fiscale</span><span class="sxs-lookup"><span data-stu-id="413a9-304">tax number</span></span>
  
<span data-ttu-id="413a9-305">imposte</span><span class="sxs-lookup"><span data-stu-id="413a9-305">tax</span></span>
  
<span data-ttu-id="413a9-306">tax id</span><span class="sxs-lookup"><span data-stu-id="413a9-306">tax id</span></span>
  
<span data-ttu-id="413a9-307">codice personale</span><span class="sxs-lookup"><span data-stu-id="413a9-307">personal code</span></span>
  
<span data-ttu-id="413a9-308">maksunumber</span><span class="sxs-lookup"><span data-stu-id="413a9-308">maksunumber</span></span>
  
<span data-ttu-id="413a9-309">ID maksu</span><span class="sxs-lookup"><span data-stu-id="413a9-309">maksu id</span></span>
  
<span data-ttu-id="413a9-310">isikukood</span><span class="sxs-lookup"><span data-stu-id="413a9-310">isikukood</span></span>
  
## <a name="finland"></a><span data-ttu-id="413a9-311">Finlandia</span><span class="sxs-lookup"><span data-stu-id="413a9-311">Finland</span></span>

### <a name="format"></a><span data-ttu-id="413a9-312">Formato</span><span class="sxs-lookup"><span data-stu-id="413a9-312">Format</span></span>

<span data-ttu-id="413a9-313">Una combinazione di 11 caratteri di cifre, lettere e segno più e meno</span><span class="sxs-lookup"><span data-stu-id="413a9-313">An 11-character combination of digits, letters, and plus and minus sign</span></span>
  
### <a name="pattern"></a><span data-ttu-id="413a9-314">Modello</span><span class="sxs-lookup"><span data-stu-id="413a9-314">Pattern</span></span>

<span data-ttu-id="413a9-315">Una combinazione di 11 caratteri di cifre, lettere e segno più e meno:</span><span class="sxs-lookup"><span data-stu-id="413a9-315">An 11-character combination of digits, letters, and plus and minus sign:</span></span>
  
- <span data-ttu-id="413a9-316">Sei cifre</span><span class="sxs-lookup"><span data-stu-id="413a9-316">Six digits</span></span>
    
- <span data-ttu-id="413a9-317">Uno dei seguenti: un segno più, un segno di sottrazione o la lettera "A" (senza distinzione tra maiuscole/minuscole), in cui il segno più significa Nato tra 1800-1899, il segno meno significa Nato tra 1900-1999 e "A" significa Nato 2000 e dopo</span><span class="sxs-lookup"><span data-stu-id="413a9-317">One of the following: a plus sign, a minus sign, or the letter "A" (not case sensitive) where the plus sign means born between 1800-1899, the minus sign means born between 1900-1999, and "A" means born 2000 and after</span></span>
    
- <span data-ttu-id="413a9-318">Tre cifre</span><span class="sxs-lookup"><span data-stu-id="413a9-318">Three digits</span></span>
    
- <span data-ttu-id="413a9-319">Una lettera o un numero</span><span class="sxs-lookup"><span data-stu-id="413a9-319">One letter or one number</span></span>
    
### <a name="checksum"></a><span data-ttu-id="413a9-320">Checksum</span><span class="sxs-lookup"><span data-stu-id="413a9-320">Checksum</span></span>

<span data-ttu-id="413a9-321">Sì</span><span class="sxs-lookup"><span data-stu-id="413a9-321">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="413a9-322">Definizione</span><span class="sxs-lookup"><span data-stu-id="413a9-322">Definition</span></span>

<span data-ttu-id="413a9-323">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="413a9-323">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="413a9-324">La funzione `Func_finland_eu_tax_file_number` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="413a9-324">The function  `Func_finland_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="413a9-325">Viene trovata una `Keywords_finland_eu_tax_file_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="413a9-325">A keyword from  `Keywords_finland_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="413a9-326">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="413a9-326">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="413a9-327">La funzione `Func_finland_eu_tax_file_number` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="413a9-327">The function  `Func_finland_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_finland_eu_tax_file_number" />
          <Match idRef="Keywords_finland_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_finland_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="413a9-328">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="413a9-328">Keywords</span></span>

#### <a name="keywordsfinlandeutaxfilenumber"></a><span data-ttu-id="413a9-329">Keywords_finland_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="413a9-329">Keywords_finland_eu_tax_file_number</span></span>

<span data-ttu-id="413a9-330">identification number</span><span class="sxs-lookup"><span data-stu-id="413a9-330">identification number</span></span>
  
<span data-ttu-id="413a9-331">ID personale</span><span class="sxs-lookup"><span data-stu-id="413a9-331">personal id</span></span>
  
<span data-ttu-id="413a9-332">numero di identità</span><span class="sxs-lookup"><span data-stu-id="413a9-332">identity number</span></span>
  
<span data-ttu-id="413a9-333">numero di identificazione nazionale finlandese</span><span class="sxs-lookup"><span data-stu-id="413a9-333">finnish national id number</span></span>
  
<span data-ttu-id="413a9-334">personalidnumber #</span><span class="sxs-lookup"><span data-stu-id="413a9-334">personalidnumber#</span></span>
  
<span data-ttu-id="413a9-335">national identification number</span><span class="sxs-lookup"><span data-stu-id="413a9-335">national identification number</span></span>
  
<span data-ttu-id="413a9-336">numero ID</span><span class="sxs-lookup"><span data-stu-id="413a9-336">id number</span></span>
  
<span data-ttu-id="413a9-337">ID nazionale No.</span><span class="sxs-lookup"><span data-stu-id="413a9-337">national id no.</span></span>
  
<span data-ttu-id="413a9-338">numero ID nazionale</span><span class="sxs-lookup"><span data-stu-id="413a9-338">national id number</span></span>
  
<span data-ttu-id="413a9-339">ID No</span><span class="sxs-lookup"><span data-stu-id="413a9-339">id no</span></span>
  
<span data-ttu-id="413a9-340">tunnistenumero</span><span class="sxs-lookup"><span data-stu-id="413a9-340">tunnistenumero</span></span>
  
<span data-ttu-id="413a9-341">henkilötunnus</span><span class="sxs-lookup"><span data-stu-id="413a9-341">henkilötunnus</span></span>
  
<span data-ttu-id="413a9-342">yksilöllinen henkilökohtainen tunnistenumero</span><span class="sxs-lookup"><span data-stu-id="413a9-342">yksilöllinen henkilökohtainen tunnistenumero</span></span>
  
<span data-ttu-id="413a9-343">ainutlaatuinen henkilökohtainen tunnus</span><span class="sxs-lookup"><span data-stu-id="413a9-343">ainutlaatuinen henkilökohtainen tunnus</span></span>
  
<span data-ttu-id="413a9-344">numero identiteetti</span><span class="sxs-lookup"><span data-stu-id="413a9-344">identiteetti numero</span></span>
  
<span data-ttu-id="413a9-345">Suomen Kansallinen henkilötunnus</span><span class="sxs-lookup"><span data-stu-id="413a9-345">suomen kansallinen henkilötunnus</span></span>
  
<span data-ttu-id="413a9-346">henkilötunnusnumero #</span><span class="sxs-lookup"><span data-stu-id="413a9-346">henkilötunnusnumero#</span></span>
  
<span data-ttu-id="413a9-347">kansallisen tunnistenumero</span><span class="sxs-lookup"><span data-stu-id="413a9-347">kansallisen tunnistenumero</span></span>
  
<span data-ttu-id="413a9-348">tunnusnumero</span><span class="sxs-lookup"><span data-stu-id="413a9-348">tunnusnumero</span></span>
  
<span data-ttu-id="413a9-349">Kansallinen tunnus numero</span><span class="sxs-lookup"><span data-stu-id="413a9-349">kansallinen tunnus numero</span></span>
  
## <a name="france"></a><span data-ttu-id="413a9-350">Francia</span><span class="sxs-lookup"><span data-stu-id="413a9-350">France</span></span>

### <a name="format"></a><span data-ttu-id="413a9-351">Formato</span><span class="sxs-lookup"><span data-stu-id="413a9-351">Format</span></span>

<span data-ttu-id="413a9-352">13 cifre per gli utenti e nove cifre per le entità</span><span class="sxs-lookup"><span data-stu-id="413a9-352">13 digits for individuals and nine digits for entities</span></span>
  
### <a name="pattern"></a><span data-ttu-id="413a9-353">Modello</span><span class="sxs-lookup"><span data-stu-id="413a9-353">Pattern</span></span>

<span data-ttu-id="413a9-354">13 cifre per gli utenti:</span><span class="sxs-lookup"><span data-stu-id="413a9-354">13 digits for individuals:</span></span>
  
- <span data-ttu-id="413a9-355">Una cifra che deve essere 0, 1, 2 o 3</span><span class="sxs-lookup"><span data-stu-id="413a9-355">One digit that must be 0, 1, 2, or 3</span></span>
    
- <span data-ttu-id="413a9-356">12 cifre</span><span class="sxs-lookup"><span data-stu-id="413a9-356">12 digits</span></span>
    
<span data-ttu-id="413a9-357">Nove cifre per le entità</span><span class="sxs-lookup"><span data-stu-id="413a9-357">Nine digits for entities</span></span>
  
### <a name="checksum"></a><span data-ttu-id="413a9-358">Checksum</span><span class="sxs-lookup"><span data-stu-id="413a9-358">Checksum</span></span>

<span data-ttu-id="413a9-359">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="413a9-359">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="413a9-360">Definizione</span><span class="sxs-lookup"><span data-stu-id="413a9-360">Definition</span></span>

<span data-ttu-id="413a9-361">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="413a9-361">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="413a9-362">La funzione `Func_france_eu_tax_file_number` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="413a9-362">The function  `Func_france_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="413a9-363">Viene trovata una `Keywords_france_eu_tax_file_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="413a9-363">A keyword from  `Keywords_france_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="413a9-364">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="413a9-364">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="413a9-365">La funzione `Func_france_eu_tax_file_number` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="413a9-365">The function  `Func_france_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_france_eu_tax_file_number" />
          <Match idRef="Keywords_france_eu_tax_file_number" />
        </Pattern>
 <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_france_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="413a9-366">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="413a9-366">Keywords</span></span>

#### <a name="keywordsfranceeutaxfilenumber"></a><span data-ttu-id="413a9-367">Keywords_france_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="413a9-367">Keywords_france_eu_tax_file_number</span></span>

<span data-ttu-id="413a9-368">codice di identificazione fiscale</span><span class="sxs-lookup"><span data-stu-id="413a9-368">tax identification number</span></span>
  
<span data-ttu-id="413a9-369">codice fiscale</span><span class="sxs-lookup"><span data-stu-id="413a9-369">tax number</span></span>
  
<span data-ttu-id="413a9-370">tax id</span><span class="sxs-lookup"><span data-stu-id="413a9-370">tax id</span></span>
  
<span data-ttu-id="413a9-371">numéro d'identification fiscale</span><span class="sxs-lookup"><span data-stu-id="413a9-371">numéro d'identification fiscale</span></span>
  
## <a name="germany"></a><span data-ttu-id="413a9-372">Germania</span><span class="sxs-lookup"><span data-stu-id="413a9-372">Germany</span></span>

### <a name="format"></a><span data-ttu-id="413a9-373">Formato</span><span class="sxs-lookup"><span data-stu-id="413a9-373">Format</span></span>

<span data-ttu-id="413a9-374">11 cifre senza spazi e delimitatori</span><span class="sxs-lookup"><span data-stu-id="413a9-374">11 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="413a9-375">Modello</span><span class="sxs-lookup"><span data-stu-id="413a9-375">Pattern</span></span>

<span data-ttu-id="413a9-376">11 cifre:</span><span class="sxs-lookup"><span data-stu-id="413a9-376">11 digits :</span></span>
  
-  <span data-ttu-id="413a9-377">Dieci cifre</span><span class="sxs-lookup"><span data-stu-id="413a9-377">Ten digits</span></span> 
    
- <span data-ttu-id="413a9-378">Una cifra di controllo</span><span class="sxs-lookup"><span data-stu-id="413a9-378">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="413a9-379">Checksum</span><span class="sxs-lookup"><span data-stu-id="413a9-379">Checksum</span></span>

<span data-ttu-id="413a9-380">Sì</span><span class="sxs-lookup"><span data-stu-id="413a9-380">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="413a9-381">Definizione</span><span class="sxs-lookup"><span data-stu-id="413a9-381">Definition</span></span>

<span data-ttu-id="413a9-382">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="413a9-382">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="413a9-383">La funzione `Func_germany_eu_tax_file_number` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="413a9-383">The function  `Func_germany_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="413a9-384">Viene trovata una `Keywords_germany_eu_tax_file_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="413a9-384">A keyword from  `Keywords_germany_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="413a9-385">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="413a9-385">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="413a9-386">La funzione `Func_germany_eu_tax_file_number` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="413a9-386">The function  `Func_germany_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_germany_eu_tax_file_number" />
          <Match idRef="Keywords_germany_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_germany_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="413a9-387">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="413a9-387">Keywords</span></span>

#### <a name="keywordsgermanyeutaxfilenumber"></a><span data-ttu-id="413a9-388">Keywords_germany_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="413a9-388">Keywords_germany_eu_tax_file_number</span></span>

<span data-ttu-id="413a9-389">codice fiscale</span><span class="sxs-lookup"><span data-stu-id="413a9-389">tax number</span></span>
  
<span data-ttu-id="413a9-390">tassa no.</span><span class="sxs-lookup"><span data-stu-id="413a9-390">tax no.</span></span>
  
<span data-ttu-id="413a9-391">taxno #</span><span class="sxs-lookup"><span data-stu-id="413a9-391">taxno#</span></span>
  
<span data-ttu-id="413a9-392">taxnumber #</span><span class="sxs-lookup"><span data-stu-id="413a9-392">taxnumber#</span></span>
  
<span data-ttu-id="413a9-393">taxnumber</span><span class="sxs-lookup"><span data-stu-id="413a9-393">taxnumber</span></span>
  
<span data-ttu-id="413a9-394">tax id</span><span class="sxs-lookup"><span data-stu-id="413a9-394">tax id</span></span>
  
<span data-ttu-id="413a9-395">taxid #</span><span class="sxs-lookup"><span data-stu-id="413a9-395">taxid#</span></span>
  
<span data-ttu-id="413a9-396">codice di identificazione fiscale</span><span class="sxs-lookup"><span data-stu-id="413a9-396">tax identification number</span></span>
  
<span data-ttu-id="413a9-397">codice fiscale n.</span><span class="sxs-lookup"><span data-stu-id="413a9-397">tax identification no.</span></span>
  
<span data-ttu-id="413a9-398">Steuernummer</span><span class="sxs-lookup"><span data-stu-id="413a9-398">steuernummer</span></span>
  
<span data-ttu-id="413a9-399">ID Steuer</span><span class="sxs-lookup"><span data-stu-id="413a9-399">steuer id</span></span>
  
<span data-ttu-id="413a9-400">steueridentifikationsnummer</span><span class="sxs-lookup"><span data-stu-id="413a9-400">steueridentifikationsnummer</span></span>
  
## <a name="greece"></a><span data-ttu-id="413a9-401">Grecia</span><span class="sxs-lookup"><span data-stu-id="413a9-401">Greece</span></span>

### <a name="format"></a><span data-ttu-id="413a9-402">Formato</span><span class="sxs-lookup"><span data-stu-id="413a9-402">Format</span></span>

<span data-ttu-id="413a9-403">Nove cifre senza spazi e delimitatori</span><span class="sxs-lookup"><span data-stu-id="413a9-403">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="413a9-404">Modello</span><span class="sxs-lookup"><span data-stu-id="413a9-404">Pattern</span></span>

<span data-ttu-id="413a9-405">9 cifre</span><span class="sxs-lookup"><span data-stu-id="413a9-405">Nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="413a9-406">Checksum</span><span class="sxs-lookup"><span data-stu-id="413a9-406">Checksum</span></span>

<span data-ttu-id="413a9-407">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="413a9-407">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="413a9-408">Definizione</span><span class="sxs-lookup"><span data-stu-id="413a9-408">Definition</span></span>

<span data-ttu-id="413a9-409">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="413a9-409">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="413a9-410">L'espressione `Regex_greece_eu_tax_file_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="413a9-410">The regular expression  `Regex_greece_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="413a9-411">Viene trovata una `Keywords_greece_eu_tax_file_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="413a9-411">A keyword from  `Keywords_greece_eu_tax_file_number` is found.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_greece_eu_tax_file_number" />
          <Match idRef="Keywords_greece_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="413a9-412">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="413a9-412">Keywords</span></span>

#### <a name="keywordsgreeceeutaxfilenumber"></a><span data-ttu-id="413a9-413">Keywords_greece_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="413a9-413">Keywords_greece_eu_tax_file_number</span></span>

<span data-ttu-id="413a9-414">AFM</span><span class="sxs-lookup"><span data-stu-id="413a9-414">afm</span></span>
  
<span data-ttu-id="413a9-415">latta</span><span class="sxs-lookup"><span data-stu-id="413a9-415">tin</span></span>
  
<span data-ttu-id="413a9-416">ID IVA No.</span><span class="sxs-lookup"><span data-stu-id="413a9-416">tax id no.</span></span>
  
<span data-ttu-id="413a9-417">ID IVA No</span><span class="sxs-lookup"><span data-stu-id="413a9-417">tax id no</span></span>
  
<span data-ttu-id="413a9-418">codice di identificazione fiscale</span><span class="sxs-lookup"><span data-stu-id="413a9-418">tax identification number</span></span>
  
<span data-ttu-id="413a9-419">numero del registro di sistema fiscale</span><span class="sxs-lookup"><span data-stu-id="413a9-419">tax registry number</span></span>
  
<span data-ttu-id="413a9-420">Registro fiscale No.</span><span class="sxs-lookup"><span data-stu-id="413a9-420">tax registry no.</span></span>
  
<span data-ttu-id="413a9-421">AFM</span><span class="sxs-lookup"><span data-stu-id="413a9-421">afm#</span></span>
  
<span data-ttu-id="413a9-422">latta</span><span class="sxs-lookup"><span data-stu-id="413a9-422">tin#</span></span>
  
<span data-ttu-id="413a9-423">taxidno #</span><span class="sxs-lookup"><span data-stu-id="413a9-423">taxidno#</span></span>
  
<span data-ttu-id="413a9-424">taxregistryno #</span><span class="sxs-lookup"><span data-stu-id="413a9-424">taxregistryno#</span></span>
  
<span data-ttu-id="413a9-425">Αριθμός φορολογικού Μητρώου</span><span class="sxs-lookup"><span data-stu-id="413a9-425">αριθμός φορολογικού μητρώου</span></span>
  
<span data-ttu-id="413a9-426">aφμ</span><span class="sxs-lookup"><span data-stu-id="413a9-426">aφμ</span></span>
  
<span data-ttu-id="413a9-427">aφμ Αριθμός</span><span class="sxs-lookup"><span data-stu-id="413a9-427">aφμ αριθμός</span></span>
  
<span data-ttu-id="413a9-428">φορολογικού Μητρώου Νο.</span><span class="sxs-lookup"><span data-stu-id="413a9-428">φορολογικού μητρώου νο.</span></span>
  
<span data-ttu-id="413a9-429">τον αριθμό φορολογικού Μητρώου</span><span class="sxs-lookup"><span data-stu-id="413a9-429">τον αριθμό φορολογικού μητρώου</span></span>
  
## <a name="hungary"></a><span data-ttu-id="413a9-430">Ungheria</span><span class="sxs-lookup"><span data-stu-id="413a9-430">Hungary</span></span>

### <a name="format"></a><span data-ttu-id="413a9-431">Formato</span><span class="sxs-lookup"><span data-stu-id="413a9-431">Format</span></span>

<span data-ttu-id="413a9-432">Dieci cifre senza spazi o delimitatori</span><span class="sxs-lookup"><span data-stu-id="413a9-432">Ten digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="413a9-433">Modello</span><span class="sxs-lookup"><span data-stu-id="413a9-433">Pattern</span></span>

<span data-ttu-id="413a9-434">Dieci cifre:</span><span class="sxs-lookup"><span data-stu-id="413a9-434">Ten digits:</span></span>
  
-  <span data-ttu-id="413a9-435">Una cifra che deve essere "8"</span><span class="sxs-lookup"><span data-stu-id="413a9-435">One digit that must be "8"</span></span> 
    
- <span data-ttu-id="413a9-436">Cinque cifre che corrispondono al numero di giorni compresi tra la data 01/01/1867 e la data di nascita dell'individuo</span><span class="sxs-lookup"><span data-stu-id="413a9-436">Five digits that correspond to the number of days between the date 01/01/1867 and the date of the birth of the individual</span></span>
    
- <span data-ttu-id="413a9-437">Tre cifre che corrispondono al numero generato dalla possibilità di distinguere gli individui nati nello stesso giorno</span><span class="sxs-lookup"><span data-stu-id="413a9-437">Three digits that correspond to the number generated by chance to differentiate individuals born on the same day</span></span>
    
- <span data-ttu-id="413a9-438">Una cifra di controllo</span><span class="sxs-lookup"><span data-stu-id="413a9-438">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="413a9-439">Checksum</span><span class="sxs-lookup"><span data-stu-id="413a9-439">Checksum</span></span>

<span data-ttu-id="413a9-440">Sì</span><span class="sxs-lookup"><span data-stu-id="413a9-440">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="413a9-441">Definizione</span><span class="sxs-lookup"><span data-stu-id="413a9-441">Definition</span></span>

<span data-ttu-id="413a9-442">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="413a9-442">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="413a9-443">La funzione `Func_hungary_eu_tax_file_number` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="413a9-443">The function  `Func_hungary_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="413a9-444">Viene trovata una `Keywords_hungary_eu_tax_file_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="413a9-444">A keyword from  `Keywords_hungary_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="413a9-445">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="413a9-445">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="413a9-446">La funzione `Func_hungary_eu_tax_file_number` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="413a9-446">The function  `Func_hungary_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_hungary_eu_tax_file_number" />
          <Match idRef="Keywords_hungary_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_hungary_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="413a9-447">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="413a9-447">Keywords</span></span>

#### <a name="keywordshungaryeutaxfilenumber"></a><span data-ttu-id="413a9-448">Keywords_hungary_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="413a9-448">Keywords_hungary_eu_tax_file_number</span></span>

<span data-ttu-id="413a9-449">numero di identificazione fiscale ungherese</span><span class="sxs-lookup"><span data-stu-id="413a9-449">hungarian tax identification number</span></span>
  
<span data-ttu-id="413a9-450">Tin ungherese</span><span class="sxs-lookup"><span data-stu-id="413a9-450">hungarian tin</span></span>
  
<span data-ttu-id="413a9-451">numero di ID fiscale</span><span class="sxs-lookup"><span data-stu-id="413a9-451">tax id number</span></span>
  
<span data-ttu-id="413a9-452">numero di partita IVA</span><span class="sxs-lookup"><span data-stu-id="413a9-452">vat number</span></span>
  
<span data-ttu-id="413a9-453">autorità tributaria No</span><span class="sxs-lookup"><span data-stu-id="413a9-453">tax authority no</span></span>
  
<span data-ttu-id="413a9-454">numero dell'identità fiscale dell'ID fiscale</span><span class="sxs-lookup"><span data-stu-id="413a9-454">tax id tax identity number</span></span>
  
<span data-ttu-id="413a9-455">taxidnumber #</span><span class="sxs-lookup"><span data-stu-id="413a9-455">taxidnumber#</span></span>
  
<span data-ttu-id="413a9-456">latta</span><span class="sxs-lookup"><span data-stu-id="413a9-456">tin#</span></span>
  
<span data-ttu-id="413a9-457">hungatiantin #</span><span class="sxs-lookup"><span data-stu-id="413a9-457">hungatiantin#</span></span>
  
<span data-ttu-id="413a9-458">identificazione fiscale No</span><span class="sxs-lookup"><span data-stu-id="413a9-458">tax identification no</span></span>
  
<span data-ttu-id="413a9-459">taxidno #</span><span class="sxs-lookup"><span data-stu-id="413a9-459">taxidno#</span></span>
  
<span data-ttu-id="413a9-460">adóazonosító szám</span><span class="sxs-lookup"><span data-stu-id="413a9-460">adóazonosító szám</span></span>
  
<span data-ttu-id="413a9-461">Adószám</span><span class="sxs-lookup"><span data-stu-id="413a9-461">adószám</span></span>
  
<span data-ttu-id="413a9-462">adóhatóság szám</span><span class="sxs-lookup"><span data-stu-id="413a9-462">adóhatóság szám</span></span>
  
## <a name="ireland"></a><span data-ttu-id="413a9-463">Irlanda</span><span class="sxs-lookup"><span data-stu-id="413a9-463">Ireland</span></span>

### <a name="format"></a><span data-ttu-id="413a9-464">Formato</span><span class="sxs-lookup"><span data-stu-id="413a9-464">Format</span></span>

<span data-ttu-id="413a9-465">Sette cifre seguite da una lettera senza spazi o delimitatori</span><span class="sxs-lookup"><span data-stu-id="413a9-465">Seven digits followed by a letter with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="413a9-466">Modello</span><span class="sxs-lookup"><span data-stu-id="413a9-466">Pattern</span></span>

<span data-ttu-id="413a9-467">Sette cifre seguite da una lettera:</span><span class="sxs-lookup"><span data-stu-id="413a9-467">Seven digits followed by a letter:</span></span>
  
-  <span data-ttu-id="413a9-468">Sette cifre</span><span class="sxs-lookup"><span data-stu-id="413a9-468">Seven digits</span></span> 
    
- <span data-ttu-id="413a9-469">Una lettera (senza distinzione tra maiuscole e minuscole)</span><span class="sxs-lookup"><span data-stu-id="413a9-469">One letter (not case-sensitive)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="413a9-470">Checksum</span><span class="sxs-lookup"><span data-stu-id="413a9-470">Checksum</span></span>

<span data-ttu-id="413a9-471">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="413a9-471">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="413a9-472">Definizione</span><span class="sxs-lookup"><span data-stu-id="413a9-472">Definition</span></span>

<span data-ttu-id="413a9-473">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="413a9-473">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="413a9-474">La funzione `Func_ireland_eu_tax_file_number` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="413a9-474">The function  `Func_ireland_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="413a9-475">Viene trovata una `Keywords_ireland_eu_tax_file_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="413a9-475">A keyword from  `Keywords_ireland_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="413a9-476">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="413a9-476">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="413a9-477">La funzione `Func_ireland_eu_tax_file_number` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="413a9-477">The function  `Func_ireland_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_ireland_eu_tax_file_number" />
          <Match idRef="Keywords_ireland_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_ireland_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="413a9-478">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="413a9-478">Keywords</span></span>

#### <a name="keywordsirelandeutaxfilenumber"></a><span data-ttu-id="413a9-479">Keywords_ireland_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="413a9-479">Keywords_ireland_eu_tax_file_number</span></span>

<span data-ttu-id="413a9-480">servizio pubblico no</span><span class="sxs-lookup"><span data-stu-id="413a9-480">public service no</span></span>
  
<span data-ttu-id="413a9-481">servizio pubblico personale No</span><span class="sxs-lookup"><span data-stu-id="413a9-481">personal public service no</span></span>
  
<span data-ttu-id="413a9-482">PPS No</span><span class="sxs-lookup"><span data-stu-id="413a9-482">pps no</span></span>
  
<span data-ttu-id="413a9-483">servizio personale No</span><span class="sxs-lookup"><span data-stu-id="413a9-483">personal service no</span></span>
  
<span data-ttu-id="413a9-484">servizio PPS No</span><span class="sxs-lookup"><span data-stu-id="413a9-484">pps service no</span></span>
  
<span data-ttu-id="413a9-485">ppsno #</span><span class="sxs-lookup"><span data-stu-id="413a9-485">ppsno#</span></span>
  
<span data-ttu-id="413a9-486">Irish PPS No</span><span class="sxs-lookup"><span data-stu-id="413a9-486">irish pps no</span></span>
  
<span data-ttu-id="413a9-487">publicserviceno #</span><span class="sxs-lookup"><span data-stu-id="413a9-487">publicserviceno#</span></span>
  
<span data-ttu-id="413a9-488">numero di servizio pubblico personale</span><span class="sxs-lookup"><span data-stu-id="413a9-488">personal public service number</span></span>
  
<span data-ttu-id="413a9-489">uimhir phearsanta Seirbhíse poiblí</span><span class="sxs-lookup"><span data-stu-id="413a9-489">uimhir phearsanta seirbhíse poiblí</span></span>
  
<span data-ttu-id="413a9-490">PPS uimh</span><span class="sxs-lookup"><span data-stu-id="413a9-490">pps uimh</span></span>
  
<span data-ttu-id="413a9-491">uimhir aitheantais phearsanta</span><span class="sxs-lookup"><span data-stu-id="413a9-491">uimhir aitheantais phearsanta</span></span>
  
## <a name="italy"></a><span data-ttu-id="413a9-492">Italia</span><span class="sxs-lookup"><span data-stu-id="413a9-492">Italy</span></span>

### <a name="format"></a><span data-ttu-id="413a9-493">Formato</span><span class="sxs-lookup"><span data-stu-id="413a9-493">Format</span></span>

<span data-ttu-id="413a9-494">16 lettere e cifre nel modello specificato</span><span class="sxs-lookup"><span data-stu-id="413a9-494">16 letters and digits in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="413a9-495">Modello</span><span class="sxs-lookup"><span data-stu-id="413a9-495">Pattern</span></span>

<span data-ttu-id="413a9-496">16 lettere e cifre:</span><span class="sxs-lookup"><span data-stu-id="413a9-496">16 letters and digits:</span></span>
  
-  <span data-ttu-id="413a9-497">Tre lettere che corrispondono alle prime tre consonanti del nome di famiglia</span><span class="sxs-lookup"><span data-stu-id="413a9-497">Three letters that correspond to the first three consonants in the family name</span></span> 
    
- <span data-ttu-id="413a9-498">Tre lettere che corrispondono alla prima, terza e quarta consonante del primo nome</span><span class="sxs-lookup"><span data-stu-id="413a9-498">Three letters that correspond to the first, third, and fourth consonants in the first name</span></span>
    
- <span data-ttu-id="413a9-499">Due cifre che corrispondono alle ultime cifre dell'anno di nascita</span><span class="sxs-lookup"><span data-stu-id="413a9-499">Two digits that correspond to the last digits of the birth year</span></span>
    
- <span data-ttu-id="413a9-500">Una cifra corrispondente al mese di nascita: le lettere vengono utilizzate in ordine alfabetico, ma vengono utilizzate solo le lettere da a a E, H, L, M, P, R e T (pertanto, gennaio è A e ottobre è R)</span><span class="sxs-lookup"><span data-stu-id="413a9-500">One digit that corresponds to the month of birth—letters are used in alphabetical order, but only the letters A to E, H, L, M, P, R to T are used (thus, January is A and October is R)</span></span>
    
- <span data-ttu-id="413a9-501">Due cifre che corrispondono al giorno del mese di nascita in cui 40 viene aggiunto al giorno di nascita per le femmine per differenziare dai maschi</span><span class="sxs-lookup"><span data-stu-id="413a9-501">Two digits that correspond to the day of the month of birth where 40 is added to the day of birth for females to differentiate from males</span></span>
    
- <span data-ttu-id="413a9-502">Quattro cifre che corrispondono a un codice di area specifico per il comune in cui è nata la persona: vengono utilizzati codici a livello nazionale per i paesi esteri</span><span class="sxs-lookup"><span data-stu-id="413a9-502">Four digits that correspond to an area code specific to the municipality where the person was born—country-wide codes are used for foreign countries</span></span>
    
- <span data-ttu-id="413a9-503">Una cifra di controllo</span><span class="sxs-lookup"><span data-stu-id="413a9-503">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="413a9-504">Checksum</span><span class="sxs-lookup"><span data-stu-id="413a9-504">Checksum</span></span>

<span data-ttu-id="413a9-505">Sì</span><span class="sxs-lookup"><span data-stu-id="413a9-505">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="413a9-506">Definizione</span><span class="sxs-lookup"><span data-stu-id="413a9-506">Definition</span></span>

<span data-ttu-id="413a9-507">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="413a9-507">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="413a9-508">La funzione `Func_italy_eu_tax_file_number` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="413a9-508">The function  `Func_italy_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="413a9-509">Viene trovata una `Keywords_italy_eu_tax_file_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="413a9-509">A keyword from  `Keywords_italy_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="413a9-510">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="413a9-510">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="413a9-511">La funzione `Func_italy_eu_tax_file_number` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="413a9-511">The function  `Func_italy_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_italy_eu_tax_file_number" />
          <Match idRef="Keywords_italy_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_italy_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="413a9-512">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="413a9-512">Keywords</span></span>

#### <a name="keywordsitalyeutaxfilenumber"></a><span data-ttu-id="413a9-513">Keywords_italy_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="413a9-513">Keywords_italy_eu_tax_file_number</span></span>

<span data-ttu-id="413a9-514">codice fiscale</span><span class="sxs-lookup"><span data-stu-id="413a9-514">tax number</span></span>
  
<span data-ttu-id="413a9-515">tassa no.</span><span class="sxs-lookup"><span data-stu-id="413a9-515">tax no.</span></span>
  
<span data-ttu-id="413a9-516">taxno #</span><span class="sxs-lookup"><span data-stu-id="413a9-516">taxno#</span></span>
  
<span data-ttu-id="413a9-517">taxnumber #</span><span class="sxs-lookup"><span data-stu-id="413a9-517">taxnumber#</span></span>
  
<span data-ttu-id="413a9-518">taxnumber</span><span class="sxs-lookup"><span data-stu-id="413a9-518">taxnumber</span></span>
  
<span data-ttu-id="413a9-519">tax id</span><span class="sxs-lookup"><span data-stu-id="413a9-519">tax id</span></span>
  
<span data-ttu-id="413a9-520">taxid #</span><span class="sxs-lookup"><span data-stu-id="413a9-520">taxid#</span></span>
  
<span data-ttu-id="413a9-521">codice fiscale</span><span class="sxs-lookup"><span data-stu-id="413a9-521">fiscal code</span></span>
  
<span data-ttu-id="413a9-522">codice fiscale</span><span class="sxs-lookup"><span data-stu-id="413a9-522">codice fiscale</span></span>
  
## <a name="latvia"></a><span data-ttu-id="413a9-523">Lettonia</span><span class="sxs-lookup"><span data-stu-id="413a9-523">Latvia</span></span>

### <a name="format"></a><span data-ttu-id="413a9-524">Formato</span><span class="sxs-lookup"><span data-stu-id="413a9-524">Format</span></span>

<span data-ttu-id="413a9-525">11 cifre senza spazi o delimitatori</span><span class="sxs-lookup"><span data-stu-id="413a9-525">11 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="413a9-526">Modello</span><span class="sxs-lookup"><span data-stu-id="413a9-526">Pattern</span></span>

<span data-ttu-id="413a9-527">11 cifre nel modello specificato</span><span class="sxs-lookup"><span data-stu-id="413a9-527">11 digits in the specified pattern</span></span>
  
-  <span data-ttu-id="413a9-528">Sei cifre che corrispondono alla data di nascita (GGMMAA)</span><span class="sxs-lookup"><span data-stu-id="413a9-528">Six digits that correspond to the date of birth (DDMMYY)</span></span> 
    
- <span data-ttu-id="413a9-529">Una cifra che corrisponde al secolo di nascita dove "0" corrisponde al XIX secolo, "1" corrisponde al 20 ° secolo e "2" corrisponde al XXI secolo</span><span class="sxs-lookup"><span data-stu-id="413a9-529">One digit that corresponds to the century of birth where "0" corresponds to 19th century, "1" corresponds to 20th century, and "2"corresponds to 21st century</span></span>
    
- <span data-ttu-id="413a9-530">Quattro cifre</span><span class="sxs-lookup"><span data-stu-id="413a9-530">Four digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="413a9-531">Checksum</span><span class="sxs-lookup"><span data-stu-id="413a9-531">Checksum</span></span>

<span data-ttu-id="413a9-532">Sì</span><span class="sxs-lookup"><span data-stu-id="413a9-532">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="413a9-533">Definizione</span><span class="sxs-lookup"><span data-stu-id="413a9-533">Definition</span></span>

<span data-ttu-id="413a9-534">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="413a9-534">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="413a9-535">La funzione `Func_latvia_eu_tax_file_number` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="413a9-535">The function  `Func_latvia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="413a9-536">Viene trovata una `Keywords_latvia_eu_tax_file_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="413a9-536">A keyword from  `Keywords_latvia_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="413a9-537">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="413a9-537">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="413a9-538">La funzione `Func_latvia_eu_tax_file_number` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="413a9-538">The function  `Func_latvia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_latvia_eu_tax_file_number" />
          <Match idRef="Keywords_latvia_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_latvia_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="413a9-539">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="413a9-539">Keywords</span></span>

#### <a name="keywordslatviaeutaxfilenumber"></a><span data-ttu-id="413a9-540">Keywords_latvia_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="413a9-540">Keywords_latvia_eu_tax_file_number</span></span>

<span data-ttu-id="413a9-541">codice fiscale</span><span class="sxs-lookup"><span data-stu-id="413a9-541">tax number</span></span>
  
<span data-ttu-id="413a9-542">tassa no.</span><span class="sxs-lookup"><span data-stu-id="413a9-542">tax no.</span></span>
  
<span data-ttu-id="413a9-543">taxno #</span><span class="sxs-lookup"><span data-stu-id="413a9-543">taxno#</span></span>
  
<span data-ttu-id="413a9-544">taxnumber #</span><span class="sxs-lookup"><span data-stu-id="413a9-544">taxnumber#</span></span>
  
<span data-ttu-id="413a9-545">taxnumber</span><span class="sxs-lookup"><span data-stu-id="413a9-545">taxnumber</span></span>
  
<span data-ttu-id="413a9-546">tax id</span><span class="sxs-lookup"><span data-stu-id="413a9-546">tax id</span></span>
  
<span data-ttu-id="413a9-547">taxid #</span><span class="sxs-lookup"><span data-stu-id="413a9-547">taxid#</span></span>
  
<span data-ttu-id="413a9-548">codice di identificazione fiscale</span><span class="sxs-lookup"><span data-stu-id="413a9-548">tax identification number</span></span>
  
<span data-ttu-id="413a9-549">codice fiscale n.</span><span class="sxs-lookup"><span data-stu-id="413a9-549">tax identification no.</span></span>
  
<span data-ttu-id="413a9-550">nodokļa numurs</span><span class="sxs-lookup"><span data-stu-id="413a9-550">nodokļa numurs</span></span>
  
<span data-ttu-id="413a9-551">nodokļu identifikācijas numurs</span><span class="sxs-lookup"><span data-stu-id="413a9-551">nodokļu identifikācijas numurs</span></span>
  
<span data-ttu-id="413a9-552">nodokļu identifikācija numurs</span><span class="sxs-lookup"><span data-stu-id="413a9-552">nodokļu identifikācija numurs</span></span>
  
## <a name="lithuania"></a><span data-ttu-id="413a9-553">Lituania</span><span class="sxs-lookup"><span data-stu-id="413a9-553">Lithuania</span></span>

### <a name="format"></a><span data-ttu-id="413a9-554">Formato</span><span class="sxs-lookup"><span data-stu-id="413a9-554">Format</span></span>

<span data-ttu-id="413a9-555">11 cifre senza spazi o delimitatori</span><span class="sxs-lookup"><span data-stu-id="413a9-555">11 digits without spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="413a9-556">Modello</span><span class="sxs-lookup"><span data-stu-id="413a9-556">Pattern</span></span>

<span data-ttu-id="413a9-557">11 cifre</span><span class="sxs-lookup"><span data-stu-id="413a9-557">11 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="413a9-558">Checksum</span><span class="sxs-lookup"><span data-stu-id="413a9-558">Checksum</span></span>

<span data-ttu-id="413a9-559">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="413a9-559">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="413a9-560">Definizione</span><span class="sxs-lookup"><span data-stu-id="413a9-560">Definition</span></span>

<span data-ttu-id="413a9-561">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="413a9-561">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="413a9-562">La funzione `Func_lithuania_eu_tax_file_number` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="413a9-562">The function  `Func_lithuania_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="413a9-563">Viene trovata una `Keywords_lithuania_eu_tax_file_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="413a9-563">A keyword from  `Keywords_lithuania_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="413a9-564">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="413a9-564">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="413a9-565">La funzione `Func_lithuania_eu_tax_file_number` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="413a9-565">The function  `Func_lithuania_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_lithuania_eu_tax_file_number" />
          <Match idRef="Keywords_lithuania_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_lithuania_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="413a9-566">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="413a9-566">Keywords</span></span>

#### <a name="keywordslithuaniaeutaxfilenumber"></a><span data-ttu-id="413a9-567">Keywords_lithuania_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="413a9-567">Keywords_lithuania_eu_tax_file_number</span></span>

<span data-ttu-id="413a9-568">codice fiscale</span><span class="sxs-lookup"><span data-stu-id="413a9-568">tax number</span></span>
  
<span data-ttu-id="413a9-569">tassa no.</span><span class="sxs-lookup"><span data-stu-id="413a9-569">tax no.</span></span>
  
<span data-ttu-id="413a9-570">tax no #</span><span class="sxs-lookup"><span data-stu-id="413a9-570">tax no#</span></span>
  
<span data-ttu-id="413a9-571">taxnumber #</span><span class="sxs-lookup"><span data-stu-id="413a9-571">taxnumber#</span></span>
  
<span data-ttu-id="413a9-572">taxnumber</span><span class="sxs-lookup"><span data-stu-id="413a9-572">taxnumber</span></span>
  
<span data-ttu-id="413a9-573">tax id</span><span class="sxs-lookup"><span data-stu-id="413a9-573">tax id</span></span>
  
<span data-ttu-id="413a9-574">taxid #</span><span class="sxs-lookup"><span data-stu-id="413a9-574">taxid#</span></span>
  
<span data-ttu-id="413a9-575">codice di identificazione fiscale</span><span class="sxs-lookup"><span data-stu-id="413a9-575">tax identification number</span></span>
  
<span data-ttu-id="413a9-576">codice fiscale n.</span><span class="sxs-lookup"><span data-stu-id="413a9-576">tax identification no.</span></span>
  
<span data-ttu-id="413a9-577">ID mokesčių</span><span class="sxs-lookup"><span data-stu-id="413a9-577">mokesčių id</span></span>
  
<span data-ttu-id="413a9-578">numeri mokesčių</span><span class="sxs-lookup"><span data-stu-id="413a9-578">mokesčių numeris</span></span>
  
<span data-ttu-id="413a9-579">mokesčių identifikavimas numeris</span><span class="sxs-lookup"><span data-stu-id="413a9-579">mokesčių identifikavimas numeris</span></span>
  
## <a name="luxemburg"></a><span data-ttu-id="413a9-580">Lussemburgo</span><span class="sxs-lookup"><span data-stu-id="413a9-580">Luxemburg</span></span>

### <a name="format"></a><span data-ttu-id="413a9-581">Formato</span><span class="sxs-lookup"><span data-stu-id="413a9-581">Format</span></span>

<span data-ttu-id="413a9-582">13 cifre senza spazi o delimitatori</span><span class="sxs-lookup"><span data-stu-id="413a9-582">13 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="413a9-583">Modello</span><span class="sxs-lookup"><span data-stu-id="413a9-583">Pattern</span></span>

<span data-ttu-id="413a9-584">13 cifre:</span><span class="sxs-lookup"><span data-stu-id="413a9-584">13 digits:</span></span>
  
-  <span data-ttu-id="413a9-585">11 cifre</span><span class="sxs-lookup"><span data-stu-id="413a9-585">11 digits</span></span> 
    
- <span data-ttu-id="413a9-586">Due cifre di controllo</span><span class="sxs-lookup"><span data-stu-id="413a9-586">Two check digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="413a9-587">Checksum</span><span class="sxs-lookup"><span data-stu-id="413a9-587">Checksum</span></span>

<span data-ttu-id="413a9-588">Sì</span><span class="sxs-lookup"><span data-stu-id="413a9-588">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="413a9-589">Definizione</span><span class="sxs-lookup"><span data-stu-id="413a9-589">Definition</span></span>

<span data-ttu-id="413a9-590">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="413a9-590">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="413a9-591">La funzione `Func_luxemburg_eu_tax_file_number` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="413a9-591">The function  `Func_luxemburg_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="413a9-592">Viene trovata una `Keywords_luxemburg_eu_tax_file_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="413a9-592">A keyword from  `Keywords_luxemburg_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="413a9-593">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="413a9-593">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="413a9-594">La funzione `Func_luxemburg_eu_tax_file_number` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="413a9-594">The function  `Func_luxemburg_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_luxemburg_eu_tax_file_number" />
          <Match idRef="Keywords_luxemburg_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_luxemburg_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="413a9-595">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="413a9-595">Keywords</span></span>

#### <a name="keywordsluxemburgeutaxfilenumber"></a><span data-ttu-id="413a9-596">Keywords_luxemburg_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="413a9-596">Keywords_luxemburg_eu_tax_file_number</span></span>

<span data-ttu-id="413a9-597">codice fiscale</span><span class="sxs-lookup"><span data-stu-id="413a9-597">tax number</span></span>
  
<span data-ttu-id="413a9-598">tassa no.</span><span class="sxs-lookup"><span data-stu-id="413a9-598">tax no.</span></span>
  
<span data-ttu-id="413a9-599">taxno #</span><span class="sxs-lookup"><span data-stu-id="413a9-599">taxno#</span></span>
  
<span data-ttu-id="413a9-600">taxnumber #</span><span class="sxs-lookup"><span data-stu-id="413a9-600">taxnumber#</span></span>
  
<span data-ttu-id="413a9-601">taxnumber</span><span class="sxs-lookup"><span data-stu-id="413a9-601">taxnumber</span></span>
  
<span data-ttu-id="413a9-602">tax id</span><span class="sxs-lookup"><span data-stu-id="413a9-602">tax id</span></span>
  
<span data-ttu-id="413a9-603">taxid #</span><span class="sxs-lookup"><span data-stu-id="413a9-603">taxid#</span></span>
  
<span data-ttu-id="413a9-604">codice di identificazione fiscale</span><span class="sxs-lookup"><span data-stu-id="413a9-604">tax identification number</span></span>
  
<span data-ttu-id="413a9-605">codice fiscale n.</span><span class="sxs-lookup"><span data-stu-id="413a9-605">tax identification no.</span></span>
  
<span data-ttu-id="413a9-606">Steuernummer</span><span class="sxs-lookup"><span data-stu-id="413a9-606">steuernummer</span></span>
  
<span data-ttu-id="413a9-607">ID Steuer</span><span class="sxs-lookup"><span data-stu-id="413a9-607">steuer id</span></span>
  
<span data-ttu-id="413a9-608">steueridentifikationsnummer</span><span class="sxs-lookup"><span data-stu-id="413a9-608">steueridentifikationsnummer</span></span>
  
## <a name="malta"></a><span data-ttu-id="413a9-609">Malta</span><span class="sxs-lookup"><span data-stu-id="413a9-609">Malta</span></span>

### <a name="format"></a><span data-ttu-id="413a9-610">Formato</span><span class="sxs-lookup"><span data-stu-id="413a9-610">Format</span></span>

<span data-ttu-id="413a9-611">Per cittadini malTesi: 7 cifre e una lettera nel modello specificato</span><span class="sxs-lookup"><span data-stu-id="413a9-611">For Maltese nationals: 7 digits and one letter in the specified pattern</span></span>
  
<span data-ttu-id="413a9-612">Nazionali non malTesi e soggetti maltesi: 9 cifre</span><span class="sxs-lookup"><span data-stu-id="413a9-612">Non-Maltese nationals and Maltese entities: 9 digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="413a9-613">Modello</span><span class="sxs-lookup"><span data-stu-id="413a9-613">Pattern</span></span>

<span data-ttu-id="413a9-614">Cittadini malTesi: 7 cifre e una lettera</span><span class="sxs-lookup"><span data-stu-id="413a9-614">Maltese nationals: 7 digits and one letter</span></span>
  
-  <span data-ttu-id="413a9-615">Sette cifre</span><span class="sxs-lookup"><span data-stu-id="413a9-615">Seven digits</span></span> 
    
- <span data-ttu-id="413a9-616">Una lettera (senza distinzione tra maiuscole e minuscole)</span><span class="sxs-lookup"><span data-stu-id="413a9-616">One letter (not case-sensitive)</span></span>
    
<span data-ttu-id="413a9-617">Nazionali non malTesi e soggetti maltesi: 9 cifre</span><span class="sxs-lookup"><span data-stu-id="413a9-617">Non-Maltese nationals and Maltese entities: 9 digits</span></span>
  
-  <span data-ttu-id="413a9-618">9 cifre</span><span class="sxs-lookup"><span data-stu-id="413a9-618">Nine digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="413a9-619">Checksum</span><span class="sxs-lookup"><span data-stu-id="413a9-619">Checksum</span></span>

<span data-ttu-id="413a9-620">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="413a9-620">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="413a9-621">Definizione</span><span class="sxs-lookup"><span data-stu-id="413a9-621">Definition</span></span>

<span data-ttu-id="413a9-622">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="413a9-622">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="413a9-623">La funzione `Func_malta_eu_tax_file_number` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="413a9-623">The function  `Func_malta_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="413a9-624">Viene trovata una `Keywords_malta_eu_tax_file_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="413a9-624">A keyword from  `Keywords_malta_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="413a9-625">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 65%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="413a9-625">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="413a9-626">La funzione `Func_malta_eu_tax_file_number` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="413a9-626">The function  `Func_malta_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_malta_eu_tax_file_number" />
          <Match idRef="Keywords_malta_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_malta_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="413a9-627">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="413a9-627">Keywords</span></span>

#### <a name="keywordsmaltaeutaxfilenumber"></a><span data-ttu-id="413a9-628">Keywords_malta_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="413a9-628">Keywords_malta_eu_tax_file_number</span></span>

<span data-ttu-id="413a9-629">codice fiscale</span><span class="sxs-lookup"><span data-stu-id="413a9-629">tax number</span></span>
  
<span data-ttu-id="413a9-630">tassa no.</span><span class="sxs-lookup"><span data-stu-id="413a9-630">tax no.</span></span>
  
<span data-ttu-id="413a9-631">taxno #</span><span class="sxs-lookup"><span data-stu-id="413a9-631">taxno#</span></span>
  
<span data-ttu-id="413a9-632">taxnumber #</span><span class="sxs-lookup"><span data-stu-id="413a9-632">taxnumber#</span></span>
  
<span data-ttu-id="413a9-633">taxnumber</span><span class="sxs-lookup"><span data-stu-id="413a9-633">taxnumber</span></span>
  
<span data-ttu-id="413a9-634">tax id</span><span class="sxs-lookup"><span data-stu-id="413a9-634">tax id</span></span>
  
<span data-ttu-id="413a9-635">taxid #</span><span class="sxs-lookup"><span data-stu-id="413a9-635">taxid#</span></span>
  
<span data-ttu-id="413a9-636">codice di identificazione fiscale</span><span class="sxs-lookup"><span data-stu-id="413a9-636">tax identification number</span></span>
  
<span data-ttu-id="413a9-637">codice fiscale n.</span><span class="sxs-lookup"><span data-stu-id="413a9-637">tax identification no.</span></span>
  
<span data-ttu-id="413a9-638">numru Tat-Taxxa</span><span class="sxs-lookup"><span data-stu-id="413a9-638">numru tat-taxxa</span></span>
  
<span data-ttu-id="413a9-639">ID Tat-Taxxa</span><span class="sxs-lookup"><span data-stu-id="413a9-639">id tat-taxxa</span></span>
  
<span data-ttu-id="413a9-640">numru ta ' identifikazzjoni Tat-Taxxa</span><span class="sxs-lookup"><span data-stu-id="413a9-640">numru ta 'identifikazzjoni tat-taxxa</span></span>
  
## <a name="netherlands"></a><span data-ttu-id="413a9-641">Paesi Bassi</span><span class="sxs-lookup"><span data-stu-id="413a9-641">Netherlands</span></span>

### <a name="format"></a><span data-ttu-id="413a9-642">Formato</span><span class="sxs-lookup"><span data-stu-id="413a9-642">Format</span></span>

<span data-ttu-id="413a9-643">Nove cifre senza spazi o delimitatori</span><span class="sxs-lookup"><span data-stu-id="413a9-643">Nine digits without spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="413a9-644">Modello</span><span class="sxs-lookup"><span data-stu-id="413a9-644">Pattern</span></span>

<span data-ttu-id="413a9-645">9 cifre</span><span class="sxs-lookup"><span data-stu-id="413a9-645">Nine digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="413a9-646">Checksum</span><span class="sxs-lookup"><span data-stu-id="413a9-646">Checksum</span></span>

<span data-ttu-id="413a9-647">Sì</span><span class="sxs-lookup"><span data-stu-id="413a9-647">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="413a9-648">Definizione</span><span class="sxs-lookup"><span data-stu-id="413a9-648">Definition</span></span>

<span data-ttu-id="413a9-649">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="413a9-649">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="413a9-650">La funzione `Func_netherlands_eu_tax_file_number` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="413a9-650">The function  `Func_netherlands_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="413a9-651">Viene trovata una `Keywords_netherlands_eu_tax_file_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="413a9-651">A keyword from  `Keywords_netherlands_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="413a9-652">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="413a9-652">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="413a9-653">La funzione `Func_netherlands_eu_tax_file_number` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="413a9-653">The function  `Func_netherlands_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_netherlands_eu_tax_file_number" />
          <Match idRef="Keywords_netherlands_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_netherlands_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="413a9-654">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="413a9-654">Keywords</span></span>

#### <a name="keywordsnetherlandseutaxfilenumber"></a><span data-ttu-id="413a9-655">Keywords_netherlands_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="413a9-655">Keywords_netherlands_eu_tax_file_number</span></span>

<span data-ttu-id="413a9-656">numero di identificazione fiscale per i Paesi Bassi</span><span class="sxs-lookup"><span data-stu-id="413a9-656">netherlands tax identification number</span></span>
  
<span data-ttu-id="413a9-657">identificazione fiscale per i Paesi Bassi</span><span class="sxs-lookup"><span data-stu-id="413a9-657">netherlands tax identification</span></span>
  
<span data-ttu-id="413a9-658">numero di identificazione fiscale per i Paesi Bassi</span><span class="sxs-lookup"><span data-stu-id="413a9-658">netherland's tax identification number</span></span>
  
<span data-ttu-id="413a9-659">identificazione fiscale per i Paesi Bassi</span><span class="sxs-lookup"><span data-stu-id="413a9-659">netherland's tax identification</span></span>
  
<span data-ttu-id="413a9-660">codice di identificazione fiscale</span><span class="sxs-lookup"><span data-stu-id="413a9-660">tax identification number</span></span>
  
<span data-ttu-id="413a9-661">ID delle tasse olandesi</span><span class="sxs-lookup"><span data-stu-id="413a9-661">dutch tax id</span></span>
  
<span data-ttu-id="413a9-662">numero di identificazione fiscale olandese</span><span class="sxs-lookup"><span data-stu-id="413a9-662">dutch tax identification number</span></span>
  
<span data-ttu-id="413a9-663">tax id</span><span class="sxs-lookup"><span data-stu-id="413a9-663">tax id</span></span>
  
<span data-ttu-id="413a9-664">ID fiscale #</span><span class="sxs-lookup"><span data-stu-id="413a9-664">tax id#</span></span>
  
<span data-ttu-id="413a9-665">codice fiscale</span><span class="sxs-lookup"><span data-stu-id="413a9-665">tax number</span></span>
  
<span data-ttu-id="413a9-666">tax no #</span><span class="sxs-lookup"><span data-stu-id="413a9-666">tax no#</span></span>
  
<span data-ttu-id="413a9-667">imposte</span><span class="sxs-lookup"><span data-stu-id="413a9-667">tax#</span></span>
  
<span data-ttu-id="413a9-668">latta</span><span class="sxs-lookup"><span data-stu-id="413a9-668">tin</span></span>
  
<span data-ttu-id="413a9-669">latta</span><span class="sxs-lookup"><span data-stu-id="413a9-669">tin#</span></span>
  
<span data-ttu-id="413a9-670">Tin olandesi</span><span class="sxs-lookup"><span data-stu-id="413a9-670">netherlands tin</span></span>
  
<span data-ttu-id="413a9-671">stagno degli olandesi</span><span class="sxs-lookup"><span data-stu-id="413a9-671">netherland's tin</span></span>
  
<span data-ttu-id="413a9-672">Nederlands identificatienummer di recente</span><span class="sxs-lookup"><span data-stu-id="413a9-672">nederlands belasting identificatienummer</span></span>
  
<span data-ttu-id="413a9-673">identificatienummer van delasting</span><span class="sxs-lookup"><span data-stu-id="413a9-673">identificatienummer van belasting</span></span>
  
<span data-ttu-id="413a9-674">identificatienummer che dura</span><span class="sxs-lookup"><span data-stu-id="413a9-674">identificatienummer belasting</span></span>
  
<span data-ttu-id="413a9-675">Nederlands identificatie di recente</span><span class="sxs-lookup"><span data-stu-id="413a9-675">nederlands belasting identificatie</span></span>
  
<span data-ttu-id="413a9-676">l'ID di Nummer del Nederlands</span><span class="sxs-lookup"><span data-stu-id="413a9-676">nederlands belasting id nummer</span></span>
  
<span data-ttu-id="413a9-677">Nederlands belastingnummer</span><span class="sxs-lookup"><span data-stu-id="413a9-677">nederlands belastingnummer</span></span>
  
<span data-ttu-id="413a9-678">BTW nummer</span><span class="sxs-lookup"><span data-stu-id="413a9-678">btw nummer</span></span>
  
<span data-ttu-id="413a9-679">Nederlandse che durerà identificatie</span><span class="sxs-lookup"><span data-stu-id="413a9-679">nederlandse belasting identificatie</span></span>
  
## <a name="poland"></a><span data-ttu-id="413a9-680">Polonia</span><span class="sxs-lookup"><span data-stu-id="413a9-680">Poland</span></span>

### <a name="format"></a><span data-ttu-id="413a9-681">Formato</span><span class="sxs-lookup"><span data-stu-id="413a9-681">Format</span></span>

<span data-ttu-id="413a9-682">Undici cifre senza spazi o delimitatori</span><span class="sxs-lookup"><span data-stu-id="413a9-682">Eleven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="413a9-683">Modello</span><span class="sxs-lookup"><span data-stu-id="413a9-683">Pattern</span></span>

<span data-ttu-id="413a9-684">Undici cifre</span><span class="sxs-lookup"><span data-stu-id="413a9-684">Eleven digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="413a9-685">Checksum</span><span class="sxs-lookup"><span data-stu-id="413a9-685">Checksum</span></span>

<span data-ttu-id="413a9-686">Sì</span><span class="sxs-lookup"><span data-stu-id="413a9-686">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="413a9-687">Definizione</span><span class="sxs-lookup"><span data-stu-id="413a9-687">Definition</span></span>

<span data-ttu-id="413a9-688">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="413a9-688">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="413a9-689">La funzione `Func_poland_eu_tax_file_number` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="413a9-689">The function  `Func_poland_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="413a9-690">Viene trovata una `Keywords_poland_eu_tax_file_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="413a9-690">A keyword from  `Keywords_poland_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="413a9-691">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="413a9-691">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="413a9-692">La funzione `Func_poland_eu_tax_file_number` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="413a9-692">The function  `Func_poland_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_poland_eu_tax_file_number" />
          <Match idRef="Keywords_poland_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_poland_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="413a9-693">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="413a9-693">Keywords</span></span>

#### <a name="keywordspolandeutaxfilenumber"></a><span data-ttu-id="413a9-694">Keywords_poland_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="413a9-694">Keywords_poland_eu_tax_file_number</span></span>

<span data-ttu-id="413a9-695">codice fiscale</span><span class="sxs-lookup"><span data-stu-id="413a9-695">tax number</span></span>
  
<span data-ttu-id="413a9-696">tassa no.</span><span class="sxs-lookup"><span data-stu-id="413a9-696">tax no.</span></span>
  
<span data-ttu-id="413a9-697">taxno #</span><span class="sxs-lookup"><span data-stu-id="413a9-697">taxno#</span></span>
  
<span data-ttu-id="413a9-698">taxnumber #</span><span class="sxs-lookup"><span data-stu-id="413a9-698">taxnumber#</span></span>
  
<span data-ttu-id="413a9-699">taxnumber</span><span class="sxs-lookup"><span data-stu-id="413a9-699">taxnumber</span></span>
  
<span data-ttu-id="413a9-700">NIP</span><span class="sxs-lookup"><span data-stu-id="413a9-700">nip</span></span>
  
<span data-ttu-id="413a9-701">NIP</span><span class="sxs-lookup"><span data-stu-id="413a9-701">nip#</span></span>
  
<span data-ttu-id="413a9-702">tax id</span><span class="sxs-lookup"><span data-stu-id="413a9-702">tax id</span></span>
  
<span data-ttu-id="413a9-703">ID fiscale #</span><span class="sxs-lookup"><span data-stu-id="413a9-703">tax id#</span></span>
  
<span data-ttu-id="413a9-704">ID NIP</span><span class="sxs-lookup"><span data-stu-id="413a9-704">nip id</span></span>
  
<span data-ttu-id="413a9-705">ID NIP #</span><span class="sxs-lookup"><span data-stu-id="413a9-705">nip id#</span></span>
  
<span data-ttu-id="413a9-706">codice di identificazione fiscale</span><span class="sxs-lookup"><span data-stu-id="413a9-706">tax identification number</span></span>
  
<span data-ttu-id="413a9-707">codice fiscale n.</span><span class="sxs-lookup"><span data-stu-id="413a9-707">tax identification no.</span></span>
  
<span data-ttu-id="413a9-708">numero di partita IVA</span><span class="sxs-lookup"><span data-stu-id="413a9-708">vat number</span></span>
  
<span data-ttu-id="413a9-709">IVA No.</span><span class="sxs-lookup"><span data-stu-id="413a9-709">vat no.</span></span>
  
<span data-ttu-id="413a9-710">vatno #</span><span class="sxs-lookup"><span data-stu-id="413a9-710">vatno#</span></span>
  
<span data-ttu-id="413a9-711">ID partita IVA</span><span class="sxs-lookup"><span data-stu-id="413a9-711">vat id</span></span>
  
<span data-ttu-id="413a9-712">ID partita IVA #</span><span class="sxs-lookup"><span data-stu-id="413a9-712">vat id#</span></span>
  
<span data-ttu-id="413a9-713">numero Identyfikacji Podatkowej</span><span class="sxs-lookup"><span data-stu-id="413a9-713">numer identyfikacji podatkowej</span></span>
  
<span data-ttu-id="413a9-714">Polski numero Identyfikacji Podatkowej</span><span class="sxs-lookup"><span data-stu-id="413a9-714">polski numer identyfikacji podatkowej</span></span>
  
<span data-ttu-id="413a9-715">numeridentyfikacjipodatkowej #</span><span class="sxs-lookup"><span data-stu-id="413a9-715">numeridentyfikacjipodatkowej#</span></span>
  
## <a name="portugal"></a><span data-ttu-id="413a9-716">Portogallo</span><span class="sxs-lookup"><span data-stu-id="413a9-716">Portugal</span></span>

### <a name="format"></a><span data-ttu-id="413a9-717">Formato</span><span class="sxs-lookup"><span data-stu-id="413a9-717">Format</span></span>

<span data-ttu-id="413a9-718">Nove cifre senza spazi o delimitatori</span><span class="sxs-lookup"><span data-stu-id="413a9-718">Nine digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="413a9-719">Modello</span><span class="sxs-lookup"><span data-stu-id="413a9-719">Pattern</span></span>

<span data-ttu-id="413a9-720">9 cifre</span><span class="sxs-lookup"><span data-stu-id="413a9-720">Nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="413a9-721">Checksum</span><span class="sxs-lookup"><span data-stu-id="413a9-721">Checksum</span></span>

<span data-ttu-id="413a9-722">Sì</span><span class="sxs-lookup"><span data-stu-id="413a9-722">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="413a9-723">Definizione</span><span class="sxs-lookup"><span data-stu-id="413a9-723">Definition</span></span>

<span data-ttu-id="413a9-724">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="413a9-724">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="413a9-725">La funzione `Func_portugal_eu_tax_file_number` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="413a9-725">The function  `Func_portugal_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="413a9-726">Viene trovata una `Keywords_portugal_eu_tax_file_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="413a9-726">A keyword from  `Keywords_portugal_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="413a9-727">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="413a9-727">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="413a9-728">La funzione `Func_portugal_eu_tax_file_number` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="413a9-728">The function  `Func_portugal_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_portugal_eu_tax_file_number" />
          <Match idRef="Keywords_portugal_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_portugal_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="413a9-729">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="413a9-729">Keywords</span></span>

#### <a name="keywordsportugaleutaxfilenumber"></a><span data-ttu-id="413a9-730">Keywords_portugal_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="413a9-730">Keywords_portugal_eu_tax_file_number</span></span>

<span data-ttu-id="413a9-731">codice fiscale</span><span class="sxs-lookup"><span data-stu-id="413a9-731">tax number</span></span>
  
<span data-ttu-id="413a9-732">tassa no.</span><span class="sxs-lookup"><span data-stu-id="413a9-732">tax no.</span></span>
  
<span data-ttu-id="413a9-733">taxno #</span><span class="sxs-lookup"><span data-stu-id="413a9-733">taxno#</span></span>
  
<span data-ttu-id="413a9-734">taxnumber #</span><span class="sxs-lookup"><span data-stu-id="413a9-734">taxnumber#</span></span>
  
<span data-ttu-id="413a9-735">taxnumber</span><span class="sxs-lookup"><span data-stu-id="413a9-735">taxnumber</span></span>
  
<span data-ttu-id="413a9-736">NIF</span><span class="sxs-lookup"><span data-stu-id="413a9-736">nif</span></span>
  
<span data-ttu-id="413a9-737">NIF</span><span class="sxs-lookup"><span data-stu-id="413a9-737">nif#</span></span>
  
<span data-ttu-id="413a9-738">numero fiscale</span><span class="sxs-lookup"><span data-stu-id="413a9-738">numero fiscal</span></span>
  
<span data-ttu-id="413a9-739">número de identificação Fiscal</span><span class="sxs-lookup"><span data-stu-id="413a9-739">número de identificação fiscal</span></span>
  
## <a name="romania"></a><span data-ttu-id="413a9-740">Romania</span><span class="sxs-lookup"><span data-stu-id="413a9-740">Romania</span></span>

### <a name="format"></a><span data-ttu-id="413a9-741">Formato</span><span class="sxs-lookup"><span data-stu-id="413a9-741">Format</span></span>

<span data-ttu-id="413a9-742">13 cifre senza spazi o delimitatori</span><span class="sxs-lookup"><span data-stu-id="413a9-742">13 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="413a9-743">Modello</span><span class="sxs-lookup"><span data-stu-id="413a9-743">Pattern</span></span>

<span data-ttu-id="413a9-744">13 cifre</span><span class="sxs-lookup"><span data-stu-id="413a9-744">13 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="413a9-745">Checksum</span><span class="sxs-lookup"><span data-stu-id="413a9-745">Checksum</span></span>

<span data-ttu-id="413a9-746">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="413a9-746">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="413a9-747">Definizione</span><span class="sxs-lookup"><span data-stu-id="413a9-747">Definition</span></span>

<span data-ttu-id="413a9-748">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="413a9-748">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="413a9-749">L'espressione `Regex_romania_eu_tax_file_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="413a9-749">The regular expression  `Regex_romania_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="413a9-750">Viene trovata una `Keywords_romania_eu_tax_file_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="413a9-750">A keyword from  `Keywords_romania_eu_tax_file_number` is found.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_romania_eu_tax_file_number" />
          <Match idRef="Keywords_romania_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="413a9-751">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="413a9-751">Keywords</span></span>

#### <a name="keywordsromaniaeutaxfilenumber"></a><span data-ttu-id="413a9-752">Keywords_romania_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="413a9-752">Keywords_romania_eu_tax_file_number</span></span>

<span data-ttu-id="413a9-753">tax id</span><span class="sxs-lookup"><span data-stu-id="413a9-753">tax id</span></span>
  
<span data-ttu-id="413a9-754">numero di ID fiscale</span><span class="sxs-lookup"><span data-stu-id="413a9-754">tax id number</span></span>
  
<span data-ttu-id="413a9-755">Tax File No</span><span class="sxs-lookup"><span data-stu-id="413a9-755">tax file no</span></span>
  
<span data-ttu-id="413a9-756">tax file number</span><span class="sxs-lookup"><span data-stu-id="413a9-756">tax file number</span></span>
  
<span data-ttu-id="413a9-757">tax no</span><span class="sxs-lookup"><span data-stu-id="413a9-757">tax no</span></span>
  
<span data-ttu-id="413a9-758">codice fiscale</span><span class="sxs-lookup"><span data-stu-id="413a9-758">tax number</span></span>
  
<span data-ttu-id="413a9-759">taxid #</span><span class="sxs-lookup"><span data-stu-id="413a9-759">taxid#</span></span>
  
<span data-ttu-id="413a9-760">taxno #</span><span class="sxs-lookup"><span data-stu-id="413a9-760">taxno#</span></span>
  
<span data-ttu-id="413a9-761">ID-ul taxei</span><span class="sxs-lookup"><span data-stu-id="413a9-761">id-ul taxei</span></span>
  
<span data-ttu-id="413a9-762">numărul de identificare fiscală</span><span class="sxs-lookup"><span data-stu-id="413a9-762">numărul de identificare fiscală</span></span>
  
## <a name="slovakia"></a><span data-ttu-id="413a9-763">Slovacchia</span><span class="sxs-lookup"><span data-stu-id="413a9-763">Slovakia</span></span>

### <a name="format"></a><span data-ttu-id="413a9-764">Formato</span><span class="sxs-lookup"><span data-stu-id="413a9-764">Format</span></span>

<span data-ttu-id="413a9-765">10 cifre senza spazi o delimitatori</span><span class="sxs-lookup"><span data-stu-id="413a9-765">10 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="413a9-766">Modello</span><span class="sxs-lookup"><span data-stu-id="413a9-766">Pattern</span></span>

<span data-ttu-id="413a9-767">10 cifre</span><span class="sxs-lookup"><span data-stu-id="413a9-767">10 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="413a9-768">Checksum</span><span class="sxs-lookup"><span data-stu-id="413a9-768">Checksum</span></span>

<span data-ttu-id="413a9-769">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="413a9-769">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="413a9-770">Definizione</span><span class="sxs-lookup"><span data-stu-id="413a9-770">Definition</span></span>

<span data-ttu-id="413a9-771">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="413a9-771">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="413a9-772">L'espressione `Regex_slovakia_eu_tax_file_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="413a9-772">The regular expression  `Regex_slovakia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="413a9-773">Viene trovata una `Keywords_slovakia_eu_tax_file_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="413a9-773">A keyword from  `Keywords_slovakia_eu_tax_file_number` is found.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovakia_eu_tax_file_number" />
          <Match idRef="Keywords_slovakia_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="413a9-774">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="413a9-774">Keywords</span></span>

#### <a name="keywordsslovakiaeutaxfilenumber"></a><span data-ttu-id="413a9-775">Keywords_slovakia_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="413a9-775">Keywords_slovakia_eu_tax_file_number</span></span>

<span data-ttu-id="413a9-776">tax id</span><span class="sxs-lookup"><span data-stu-id="413a9-776">tax id</span></span>
  
<span data-ttu-id="413a9-777">numero di ID fiscale</span><span class="sxs-lookup"><span data-stu-id="413a9-777">tax id number</span></span>
  
<span data-ttu-id="413a9-778">ID Tin</span><span class="sxs-lookup"><span data-stu-id="413a9-778">tin id</span></span>
  
<span data-ttu-id="413a9-779">Tin No</span><span class="sxs-lookup"><span data-stu-id="413a9-779">tin no</span></span>
  
<span data-ttu-id="413a9-780">ID Tin slovacco</span><span class="sxs-lookup"><span data-stu-id="413a9-780">slovakian tin id</span></span>
  
<span data-ttu-id="413a9-781">latta</span><span class="sxs-lookup"><span data-stu-id="413a9-781">tin</span></span>
  
<span data-ttu-id="413a9-782">Tax File No</span><span class="sxs-lookup"><span data-stu-id="413a9-782">tax file no</span></span>
  
<span data-ttu-id="413a9-783">tax file number</span><span class="sxs-lookup"><span data-stu-id="413a9-783">tax file number</span></span>
  
<span data-ttu-id="413a9-784">tax no</span><span class="sxs-lookup"><span data-stu-id="413a9-784">tax no</span></span>
  
<span data-ttu-id="413a9-785">codice fiscale</span><span class="sxs-lookup"><span data-stu-id="413a9-785">tax number</span></span>
  
<span data-ttu-id="413a9-786">taxid #</span><span class="sxs-lookup"><span data-stu-id="413a9-786">taxid#</span></span>
  
<span data-ttu-id="413a9-787">taxno #</span><span class="sxs-lookup"><span data-stu-id="413a9-787">taxno#</span></span>
  
<span data-ttu-id="413a9-788">daňové identifikačné číslo</span><span class="sxs-lookup"><span data-stu-id="413a9-788">daňové identifikačné číslo</span></span>
  
<span data-ttu-id="413a9-789">daňové číslo</span><span class="sxs-lookup"><span data-stu-id="413a9-789">daňové číslo</span></span>
  
<span data-ttu-id="413a9-790">daňové číslo súboru</span><span class="sxs-lookup"><span data-stu-id="413a9-790">daňové číslo súboru</span></span>
  
## <a name="slovenia"></a><span data-ttu-id="413a9-791">Slovenia</span><span class="sxs-lookup"><span data-stu-id="413a9-791">Slovenia</span></span>

### <a name="format"></a><span data-ttu-id="413a9-792">Formato</span><span class="sxs-lookup"><span data-stu-id="413a9-792">Format</span></span>

<span data-ttu-id="413a9-793">Otto cifre senza spazi o delimitatori</span><span class="sxs-lookup"><span data-stu-id="413a9-793">Eight digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="413a9-794">Modello</span><span class="sxs-lookup"><span data-stu-id="413a9-794">Pattern</span></span>

<span data-ttu-id="413a9-795">Otto cifre</span><span class="sxs-lookup"><span data-stu-id="413a9-795">Eight digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="413a9-796">Checksum</span><span class="sxs-lookup"><span data-stu-id="413a9-796">Checksum</span></span>

<span data-ttu-id="413a9-797">Sì</span><span class="sxs-lookup"><span data-stu-id="413a9-797">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="413a9-798">Definizione</span><span class="sxs-lookup"><span data-stu-id="413a9-798">Definition</span></span>

<span data-ttu-id="413a9-799">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="413a9-799">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="413a9-800">La funzione `Func_slovenia_eu_tax_file_number` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="413a9-800">The function  `Func_slovenia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="413a9-801">Viene trovata una `Keywords_slovenia_eu_tax_file_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="413a9-801">A keyword from  `Keywords_slovenia_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="413a9-802">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="413a9-802">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="413a9-803">La funzione `Func_slovenia_eu_tax_file_number` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="413a9-803">The function  `Func_slovenia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_nation_eu_tax_file_number" />
          <Match idRef="Keywords_nation_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_slovenia_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="413a9-804">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="413a9-804">Keywords</span></span>

#### <a name="keywordssloveniaeutaxfilenumber"></a><span data-ttu-id="413a9-805">Keywords_slovenia_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="413a9-805">Keywords_slovenia_eu_tax_file_number</span></span>

<span data-ttu-id="413a9-806">tax id</span><span class="sxs-lookup"><span data-stu-id="413a9-806">tax id</span></span>
  
<span data-ttu-id="413a9-807">numero di ID fiscale</span><span class="sxs-lookup"><span data-stu-id="413a9-807">tax id number</span></span>
  
<span data-ttu-id="413a9-808">ID Tin</span><span class="sxs-lookup"><span data-stu-id="413a9-808">tin id</span></span>
  
<span data-ttu-id="413a9-809">Tin No</span><span class="sxs-lookup"><span data-stu-id="413a9-809">tin no</span></span>
  
<span data-ttu-id="413a9-810">ID Tin sloveno</span><span class="sxs-lookup"><span data-stu-id="413a9-810">slovenian tin id</span></span>
  
<span data-ttu-id="413a9-811">latta</span><span class="sxs-lookup"><span data-stu-id="413a9-811">tin</span></span>
  
<span data-ttu-id="413a9-812">Tax File No</span><span class="sxs-lookup"><span data-stu-id="413a9-812">tax file no</span></span>
  
<span data-ttu-id="413a9-813">tax file number</span><span class="sxs-lookup"><span data-stu-id="413a9-813">tax file number</span></span>
  
<span data-ttu-id="413a9-814">tax no</span><span class="sxs-lookup"><span data-stu-id="413a9-814">tax no</span></span>
  
<span data-ttu-id="413a9-815">codice fiscale</span><span class="sxs-lookup"><span data-stu-id="413a9-815">tax number</span></span>
  
<span data-ttu-id="413a9-816">taxid #</span><span class="sxs-lookup"><span data-stu-id="413a9-816">taxid#</span></span>
  
<span data-ttu-id="413a9-817">taxno #</span><span class="sxs-lookup"><span data-stu-id="413a9-817">taxno#</span></span>
  
<span data-ttu-id="413a9-818">identifikacijska številka davka</span><span class="sxs-lookup"><span data-stu-id="413a9-818">identifikacijska številka davka</span></span>
  
<span data-ttu-id="413a9-819">Davčna številka</span><span class="sxs-lookup"><span data-stu-id="413a9-819">davčna številka</span></span>
  
<span data-ttu-id="413a9-820">številka davčne datoteke</span><span class="sxs-lookup"><span data-stu-id="413a9-820">številka davčne datoteke</span></span>
  
## <a name="spain"></a><span data-ttu-id="413a9-821">Spagna</span><span class="sxs-lookup"><span data-stu-id="413a9-821">Spain</span></span>

### <a name="format"></a><span data-ttu-id="413a9-822">Formato</span><span class="sxs-lookup"><span data-stu-id="413a9-822">Format</span></span>

<span data-ttu-id="413a9-823">Sette o otto cifre e una o due lettere nel modello specificato</span><span class="sxs-lookup"><span data-stu-id="413a9-823">Seven or eight digits and one or two letters in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="413a9-824">Modello</span><span class="sxs-lookup"><span data-stu-id="413a9-824">Pattern</span></span>

<span data-ttu-id="413a9-825">Persone fisiche spagnole con carta d'identità nazionale spagnola:</span><span class="sxs-lookup"><span data-stu-id="413a9-825">Spanish Natural Persons with a Spain National Identity Card:</span></span>
  
-  <span data-ttu-id="413a9-826">Otto cifre</span><span class="sxs-lookup"><span data-stu-id="413a9-826">Eight digits</span></span> 
    
- <span data-ttu-id="413a9-827">Una lettera maiuscola (con distinzione tra maiuscole e minuscole)</span><span class="sxs-lookup"><span data-stu-id="413a9-827">One uppercase letter (case-sensitive)</span></span> 
    
<span data-ttu-id="413a9-828">Spagnoli non residenti senza una carta d'identità nazionale spagnola</span><span class="sxs-lookup"><span data-stu-id="413a9-828">Non-resident Spaniards without a Spain National Identity Card</span></span>
  
- <span data-ttu-id="413a9-829">Una lettera maiuscola "L" (con distinzione tra maiuscole e minuscole)</span><span class="sxs-lookup"><span data-stu-id="413a9-829">One uppercase letter "L" (case-sensitive)</span></span>
    
- <span data-ttu-id="413a9-830">Sette cifre</span><span class="sxs-lookup"><span data-stu-id="413a9-830">Seven digits</span></span>
    
- <span data-ttu-id="413a9-831">Una lettera maiuscola (con distinzione tra maiuscole e minuscole)</span><span class="sxs-lookup"><span data-stu-id="413a9-831">One uppercase letter (case-sensitive)</span></span> 
    
<span data-ttu-id="413a9-832">Spagnoli residenti di età inferiore ai 14 anni senza una carta d'identità nazionale spagnola:</span><span class="sxs-lookup"><span data-stu-id="413a9-832">Resident Spaniards under the age of 14 years without a Spain National Identity Card :</span></span>
  
- <span data-ttu-id="413a9-833">Una lettera maiuscola "K" (con distinzione tra maiuscole e minuscole)</span><span class="sxs-lookup"><span data-stu-id="413a9-833">One uppercase letter"K" (case-sensitive)</span></span>
    
-  <span data-ttu-id="413a9-834">Sette cifre</span><span class="sxs-lookup"><span data-stu-id="413a9-834">Seven digits</span></span> 
    
- <span data-ttu-id="413a9-835">Una lettera maiuscola (con distinzione tra maiuscole e minuscole)</span><span class="sxs-lookup"><span data-stu-id="413a9-835">One uppercase letter (case-sensitive)</span></span>
    
<span data-ttu-id="413a9-836">Stranieri con il numero di identificazione di un forestiero</span><span class="sxs-lookup"><span data-stu-id="413a9-836">Foreigners with a Foreigner's Identification Number</span></span>
  
- <span data-ttu-id="413a9-837">Una lettera maiuscola che è "X", "Y" o "Z" (con distinzione tra maiuscole e minuscole)</span><span class="sxs-lookup"><span data-stu-id="413a9-837">One uppercase letter that is "X", "Y", or "Z" (case-sensitive)</span></span> 
    
- <span data-ttu-id="413a9-838">Sette cifre</span><span class="sxs-lookup"><span data-stu-id="413a9-838">Seven digits</span></span>
    
- <span data-ttu-id="413a9-839">Una lettera maiuscola (con distinzione tra maiuscole e minuscole)</span><span class="sxs-lookup"><span data-stu-id="413a9-839">One uppercase letter (case-sensitive)</span></span> 
    
<span data-ttu-id="413a9-840">Stranieri senza il numero di identificazione di un forestiero</span><span class="sxs-lookup"><span data-stu-id="413a9-840">Foreigners without a Foreigner's Identification Number</span></span>
  
- <span data-ttu-id="413a9-841">Una lettera maiuscola che è "M" (con distinzione tra maiuscole e minuscole)</span><span class="sxs-lookup"><span data-stu-id="413a9-841">One uppercase letter that is "M" (case-sensitive)</span></span> 
    
- <span data-ttu-id="413a9-842">Sette cifre</span><span class="sxs-lookup"><span data-stu-id="413a9-842">Seven digits</span></span>
    
- <span data-ttu-id="413a9-843">Una lettera maiuscola (con distinzione tra maiuscole e minuscole)</span><span class="sxs-lookup"><span data-stu-id="413a9-843">One uppercase letter (case-sensitive)</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="413a9-844">Checksum</span><span class="sxs-lookup"><span data-stu-id="413a9-844">Checksum</span></span>

<span data-ttu-id="413a9-845">Sì</span><span class="sxs-lookup"><span data-stu-id="413a9-845">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="413a9-846">Definizione</span><span class="sxs-lookup"><span data-stu-id="413a9-846">Definition</span></span>

<span data-ttu-id="413a9-847">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="413a9-847">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="413a9-848">La funzione `Func_spain_eu_tax_file_number` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="413a9-848">The function  `Func_spain_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="413a9-849">Viene trovata una `Keywords_spain_eu_tax_file_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="413a9-849">A keyword from  `Keywords_spain_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="413a9-850">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="413a9-850">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="413a9-851">La funzione `Func_spain_eu_tax_file_number` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="413a9-851">The function  `Func_spain_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_spain_eu_tax_file_number" />
          <Match idRef="Keywords_spain_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_spain_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="413a9-852">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="413a9-852">Keywords</span></span>

#### <a name="keywordsspaineutaxfilenumber"></a><span data-ttu-id="413a9-853">Keywords_spain_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="413a9-853">Keywords_spain_eu_tax_file_number</span></span>

<span data-ttu-id="413a9-854">tax id</span><span class="sxs-lookup"><span data-stu-id="413a9-854">tax id</span></span>
  
<span data-ttu-id="413a9-855">numero di ID fiscale</span><span class="sxs-lookup"><span data-stu-id="413a9-855">tax id number</span></span>
  
<span data-ttu-id="413a9-856">ID CIF</span><span class="sxs-lookup"><span data-stu-id="413a9-856">cif id</span></span>
  
<span data-ttu-id="413a9-857">CIF No</span><span class="sxs-lookup"><span data-stu-id="413a9-857">cif no</span></span>
  
<span data-ttu-id="413a9-858">ID CIF spagnolo</span><span class="sxs-lookup"><span data-stu-id="413a9-858">spanish cif id</span></span>
  
<span data-ttu-id="413a9-859">CIF</span><span class="sxs-lookup"><span data-stu-id="413a9-859">cif</span></span>
  
<span data-ttu-id="413a9-860">Tax File No</span><span class="sxs-lookup"><span data-stu-id="413a9-860">tax file no</span></span>
  
<span data-ttu-id="413a9-861">numero CIF spagnolo</span><span class="sxs-lookup"><span data-stu-id="413a9-861">spanish cif number</span></span>
  
<span data-ttu-id="413a9-862">tax file number</span><span class="sxs-lookup"><span data-stu-id="413a9-862">tax file number</span></span>
  
<span data-ttu-id="413a9-863">Spagnolo CIF No</span><span class="sxs-lookup"><span data-stu-id="413a9-863">spanish cif no</span></span>
  
<span data-ttu-id="413a9-864">tax no</span><span class="sxs-lookup"><span data-stu-id="413a9-864">tax no</span></span>
  
<span data-ttu-id="413a9-865">codice fiscale</span><span class="sxs-lookup"><span data-stu-id="413a9-865">tax number</span></span>
  
<span data-ttu-id="413a9-866">taxid #</span><span class="sxs-lookup"><span data-stu-id="413a9-866">taxid#</span></span>
  
<span data-ttu-id="413a9-867">taxno #</span><span class="sxs-lookup"><span data-stu-id="413a9-867">taxno#</span></span>
  
<span data-ttu-id="413a9-868">cifid #</span><span class="sxs-lookup"><span data-stu-id="413a9-868">cifid#</span></span>
  
<span data-ttu-id="413a9-869">spanishcifid #</span><span class="sxs-lookup"><span data-stu-id="413a9-869">spanishcifid#</span></span>
  
<span data-ttu-id="413a9-870">spanishcifno #</span><span class="sxs-lookup"><span data-stu-id="413a9-870">spanishcifno#</span></span>
  
<span data-ttu-id="413a9-871">número de contribuyente</span><span class="sxs-lookup"><span data-stu-id="413a9-871">número de contribuyente</span></span>
  
<span data-ttu-id="413a9-872">número de Impuesto corporativo</span><span class="sxs-lookup"><span data-stu-id="413a9-872">número de impuesto corporativo</span></span>
  
<span data-ttu-id="413a9-873">número de Identificación Fiscal</span><span class="sxs-lookup"><span data-stu-id="413a9-873">número de identificación fiscal</span></span>
  
<span data-ttu-id="413a9-874">número CIF</span><span class="sxs-lookup"><span data-stu-id="413a9-874">cif número</span></span>
  
<span data-ttu-id="413a9-875">cifnúmero #</span><span class="sxs-lookup"><span data-stu-id="413a9-875">cifnúmero#</span></span>
  
## <a name="sweden"></a><span data-ttu-id="413a9-876">Svezia</span><span class="sxs-lookup"><span data-stu-id="413a9-876">Sweden</span></span>

### <a name="format"></a><span data-ttu-id="413a9-877">Formato</span><span class="sxs-lookup"><span data-stu-id="413a9-877">Format</span></span>

<span data-ttu-id="413a9-878">Dieci cifre e un simbolo nel modello specificato</span><span class="sxs-lookup"><span data-stu-id="413a9-878">Ten digits and a symbol in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="413a9-879">Modello</span><span class="sxs-lookup"><span data-stu-id="413a9-879">Pattern</span></span>

<span data-ttu-id="413a9-880">Dieci cifre e un simbolo:</span><span class="sxs-lookup"><span data-stu-id="413a9-880">Ten digits and a symbol:</span></span>
  
-  <span data-ttu-id="413a9-881">Sei cifre che corrispondono alla data di nascita (AAMMGG)</span><span class="sxs-lookup"><span data-stu-id="413a9-881">Six digits that correspond to the birth date (YYMMDD)</span></span> 
    
- <span data-ttu-id="413a9-882">Segno di addizione, segno meno o barra rovesciata</span><span class="sxs-lookup"><span data-stu-id="413a9-882">A plus sign, minus sign, or backslash</span></span>
    
- <span data-ttu-id="413a9-883">Tre cifre che rendono il numero di identificazione univoco dove:</span><span class="sxs-lookup"><span data-stu-id="413a9-883">Three digits that make the identification number unique where:</span></span> 
    
  - <span data-ttu-id="413a9-884">Per i numeri emessi prima del 1990, la settima e la terza cifra identificano la Contea di nascita o gli stranieri nati</span><span class="sxs-lookup"><span data-stu-id="413a9-884">For numbers issued before 1990, the seventh and eighth digit identify the county of birth or foreign-born people</span></span>
    
  - <span data-ttu-id="413a9-885">La cifra nella nona posizione indica il sesso per il maschio o per la femmina.</span><span class="sxs-lookup"><span data-stu-id="413a9-885">The digit in the ninth position indicates gender by either odd for male or even for female</span></span>
    
- <span data-ttu-id="413a9-886">Una cifra di controllo</span><span class="sxs-lookup"><span data-stu-id="413a9-886">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="413a9-887">Checksum</span><span class="sxs-lookup"><span data-stu-id="413a9-887">Checksum</span></span>

<span data-ttu-id="413a9-888">Sì</span><span class="sxs-lookup"><span data-stu-id="413a9-888">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="413a9-889">Definizione</span><span class="sxs-lookup"><span data-stu-id="413a9-889">Definition</span></span>

<span data-ttu-id="413a9-890">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="413a9-890">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="413a9-891">La funzione `Func_sweden_eu_tax_file_number` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="413a9-891">The function  `Func_sweden_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="413a9-892">Viene trovata una `Keywords_sweden_eu_tax_file_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="413a9-892">A keyword from  `Keywords_sweden_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="413a9-893">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="413a9-893">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="413a9-894">La funzione `Func_sweden_eu_tax_file_number` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="413a9-894">The function  `Func_sweden_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_sweden_eu_tax_file_number" />
          <Match idRef="Keywords_sweden_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_sweden_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="413a9-895">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="413a9-895">Keywords</span></span>

#### <a name="keywordsswedeneutaxfilenumber"></a><span data-ttu-id="413a9-896">Keywords_sweden_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="413a9-896">Keywords_sweden_eu_tax_file_number</span></span>

<span data-ttu-id="413a9-897">tax id</span><span class="sxs-lookup"><span data-stu-id="413a9-897">tax id</span></span>
  
<span data-ttu-id="413a9-898">ID IVA No.</span><span class="sxs-lookup"><span data-stu-id="413a9-898">tax id no.</span></span>
  
<span data-ttu-id="413a9-899">numero di ID fiscale</span><span class="sxs-lookup"><span data-stu-id="413a9-899">tax id number</span></span>
  
<span data-ttu-id="413a9-900">tax identification</span><span class="sxs-lookup"><span data-stu-id="413a9-900">tax identification</span></span>
  
<span data-ttu-id="413a9-901">identificazione fiscale #</span><span class="sxs-lookup"><span data-stu-id="413a9-901">tax identification#</span></span>
  
<span data-ttu-id="413a9-902">tassa no.</span><span class="sxs-lookup"><span data-stu-id="413a9-902">tax no.</span></span>
  
<span data-ttu-id="413a9-903">imposte</span><span class="sxs-lookup"><span data-stu-id="413a9-903">tax#</span></span>
  
<span data-ttu-id="413a9-904">taxid #</span><span class="sxs-lookup"><span data-stu-id="413a9-904">taxid#</span></span>
  
<span data-ttu-id="413a9-905">file fiscale</span><span class="sxs-lookup"><span data-stu-id="413a9-905">tax file</span></span>
  
<span data-ttu-id="413a9-906">Tax File No.</span><span class="sxs-lookup"><span data-stu-id="413a9-906">tax file no.</span></span>
  
<span data-ttu-id="413a9-907">numero ID personale</span><span class="sxs-lookup"><span data-stu-id="413a9-907">personal id number</span></span>
  
<span data-ttu-id="413a9-908">ID pattinat Nummer</span><span class="sxs-lookup"><span data-stu-id="413a9-908">skatt id nummer</span></span>
  
<span data-ttu-id="413a9-909">Identifikation skatet</span><span class="sxs-lookup"><span data-stu-id="413a9-909">skatt identifikation</span></span>
  
<span data-ttu-id="413a9-910">personnummer</span><span class="sxs-lookup"><span data-stu-id="413a9-910">personnummer</span></span>
  
## <a name="uk"></a><span data-ttu-id="413a9-911">Regno Unito</span><span class="sxs-lookup"><span data-stu-id="413a9-911">UK</span></span>

### <a name="format"></a><span data-ttu-id="413a9-912">Formato</span><span class="sxs-lookup"><span data-stu-id="413a9-912">Format</span></span>

<span data-ttu-id="413a9-913">Riferimento per i contribuenti unici (UTR): 10 cifre senza spazi e delimitatori</span><span class="sxs-lookup"><span data-stu-id="413a9-913">Unique Taxpayer Reference (UTR): 10 digits without spaces and delimiters</span></span>
  
<span data-ttu-id="413a9-914">Numero di assicurazione nazionale (NINO): per informazioni dettagliate, vedere la sezione "Regno Unito</span><span class="sxs-lookup"><span data-stu-id="413a9-914">National Insurance Number (NINO): For details, see the section "U.K.</span></span> <span data-ttu-id="413a9-915">Numero di assicurazione nazionale (NINO) "in [che cosa cercano i tipi di informazioni riservate](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="413a9-915">National Insurance Number (NINO)" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
### <a name="pattern"></a><span data-ttu-id="413a9-916">Modello</span><span class="sxs-lookup"><span data-stu-id="413a9-916">Pattern</span></span>

<span data-ttu-id="413a9-917">Riferimento per i contribuenti unici (UTR): 10 cifre</span><span class="sxs-lookup"><span data-stu-id="413a9-917">Unique Taxpayer Reference (UTR): 10 digits</span></span>
  
<span data-ttu-id="413a9-918">Numero di assicurazione nazionale (NINO): per informazioni dettagliate, vedere la sezione "Regno Unito</span><span class="sxs-lookup"><span data-stu-id="413a9-918">National Insurance Number (NINO): For details, see the section "U.K.</span></span> <span data-ttu-id="413a9-919">Numero di assicurazione nazionale (NINO) "in [che cosa cercano i tipi di informazioni riservate](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="413a9-919">National Insurance Number (NINO)" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
### <a name="checksum"></a><span data-ttu-id="413a9-920">Checksum</span><span class="sxs-lookup"><span data-stu-id="413a9-920">Checksum</span></span>

<span data-ttu-id="413a9-921">Sì</span><span class="sxs-lookup"><span data-stu-id="413a9-921">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="413a9-922">Definizione</span><span class="sxs-lookup"><span data-stu-id="413a9-922">Definition</span></span>

<span data-ttu-id="413a9-923">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="413a9-923">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="413a9-924">La funzione `Func_uk_eu_tax_file_number` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="413a9-924">The function  `Func_uk_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="413a9-925">Viene trovata una `Keywords_uk_eu_tax_file_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="413a9-925">A keyword from  `Keywords_uk_eu_tax_file_number` is found.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_uk_eu_tax_file_number" />
          <Match idRef="Keywords_uk_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="413a9-926">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="413a9-926">Keywords</span></span>

#### <a name="keywordsukeutaxfilenumber"></a><span data-ttu-id="413a9-927">Keywords_uk_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="413a9-927">Keywords_uk_eu_tax_file_number</span></span>

<span data-ttu-id="413a9-928">tax id</span><span class="sxs-lookup"><span data-stu-id="413a9-928">tax id</span></span>
  
<span data-ttu-id="413a9-929">ID IVA No.</span><span class="sxs-lookup"><span data-stu-id="413a9-929">tax id no.</span></span>
  
<span data-ttu-id="413a9-930">numero di ID fiscale</span><span class="sxs-lookup"><span data-stu-id="413a9-930">tax id number</span></span>
  
<span data-ttu-id="413a9-931">tax identification</span><span class="sxs-lookup"><span data-stu-id="413a9-931">tax identification</span></span>
  
<span data-ttu-id="413a9-932">identificazione fiscale #</span><span class="sxs-lookup"><span data-stu-id="413a9-932">tax identification#</span></span>
  
<span data-ttu-id="413a9-933">tassa no.</span><span class="sxs-lookup"><span data-stu-id="413a9-933">tax no.</span></span>
  
<span data-ttu-id="413a9-934">imposte</span><span class="sxs-lookup"><span data-stu-id="413a9-934">tax#</span></span>
  
<span data-ttu-id="413a9-935">taxid #</span><span class="sxs-lookup"><span data-stu-id="413a9-935">taxid#</span></span>
  
<span data-ttu-id="413a9-936">file fiscale</span><span class="sxs-lookup"><span data-stu-id="413a9-936">tax file</span></span>
  
<span data-ttu-id="413a9-937">Tax File No.</span><span class="sxs-lookup"><span data-stu-id="413a9-937">tax file no.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="413a9-938">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="413a9-938">See also</span></span>

[<span data-ttu-id="413a9-939">Cosa individuano le tipologie di informazioni sensibili</span><span class="sxs-lookup"><span data-stu-id="413a9-939">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)

