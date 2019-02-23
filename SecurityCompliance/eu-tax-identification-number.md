---
title: Numero di identificazione fiscale dell'Unione europea
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 8/17/2018
ms.audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: f04919c8-2356-4de2-bb2a-b9f67f339726
description: In questo argomento viene illustrato l'aspetto di un criterio di prevenzione della perdita di dati (DLP) quando viene rilevato il tipo di informazioni riservate del numero di identificazione fiscale dell'Unione europea. Questo tipo di informazioni riservate definisce modelli, parole chiave e altre evidenze diverse per ogni paese.
ms.openlocfilehash: f851cce4be70fd41c24a7876d97c452f0a738eda
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/23/2019
ms.locfileid: "30213826"
---
# <a name="eu-tax-identification-number"></a><span data-ttu-id="ebaa0-104">Numero di identificazione fiscale dell'Unione europea</span><span class="sxs-lookup"><span data-stu-id="ebaa0-104">EU Tax Identification Number</span></span>

<span data-ttu-id="ebaa0-p102">In questo argomento viene illustrato l'aspetto di un criterio di prevenzione della perdita di dati (DLP) quando viene rilevato il tipo di informazioni riservate del numero di identificazione fiscale (TIN) dell'Unione europea. Questo tipo di informazioni riservate definisce modelli, parole chiave e altre evidenze diverse per ogni paese.</span><span class="sxs-lookup"><span data-stu-id="ebaa0-p102">This topic shows what a data loss prevention (DLP) policy looks for when it detects the EU Tax Identification Number (TIN) sensitive information type. This sensitive information type defines different patterns, keywords, and other evidence for each country.</span></span>
  
## <a name="austria"></a><span data-ttu-id="ebaa0-107">Austria</span><span class="sxs-lookup"><span data-stu-id="ebaa0-107">Austria</span></span>

### <a name="format"></a><span data-ttu-id="ebaa0-108">Formato</span><span class="sxs-lookup"><span data-stu-id="ebaa0-108">Format</span></span>

<span data-ttu-id="ebaa0-109">Nove cifre con trattino e barra di inoltro opzionali</span><span class="sxs-lookup"><span data-stu-id="ebaa0-109">Nine digits with optional hyphen and forward slash</span></span>
  
### <a name="pattern"></a><span data-ttu-id="ebaa0-110">Modello</span><span class="sxs-lookup"><span data-stu-id="ebaa0-110">Pattern</span></span>

<span data-ttu-id="ebaa0-111">Nove cifre con trattino e barra di inoltro facoltativi:</span><span class="sxs-lookup"><span data-stu-id="ebaa0-111">Nine digits with optional hyphen and forward slash:</span></span>
  
-  <span data-ttu-id="ebaa0-112">Due cifre</span><span class="sxs-lookup"><span data-stu-id="ebaa0-112">Two digits</span></span> 
    
- <span data-ttu-id="ebaa0-113">Una lineetta (facoltativa)</span><span class="sxs-lookup"><span data-stu-id="ebaa0-113">A hyphen (optional)</span></span>
    
- <span data-ttu-id="ebaa0-114">Tre cifre</span><span class="sxs-lookup"><span data-stu-id="ebaa0-114">Three digits</span></span>
    
- <span data-ttu-id="ebaa0-115">Una barra (facoltativa)</span><span class="sxs-lookup"><span data-stu-id="ebaa0-115">A forward slash (optional)</span></span>
    
- <span data-ttu-id="ebaa0-116">Quattro cifre</span><span class="sxs-lookup"><span data-stu-id="ebaa0-116">Four digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="ebaa0-117">Checksum</span><span class="sxs-lookup"><span data-stu-id="ebaa0-117">Checksum</span></span>

<span data-ttu-id="ebaa0-118">Sì</span><span class="sxs-lookup"><span data-stu-id="ebaa0-118">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="ebaa0-119">Definizione</span><span class="sxs-lookup"><span data-stu-id="ebaa0-119">Definition</span></span>

<span data-ttu-id="ebaa0-120">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="ebaa0-120">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="ebaa0-121">La funzione `Func_austria_eu_tax_file_number` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="ebaa0-121">The function  `Func_austria_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="ebaa0-122">Viene trovata una `Keywords_austria_eu_tax_file_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="ebaa0-122">A keyword from  `Keywords_austria_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="ebaa0-123">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="ebaa0-123">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="ebaa0-124">La funzione `Func_austria_eu_tax_file_number` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="ebaa0-124">The function  `Func_austria_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="ebaa0-125">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="ebaa0-125">Keywords</span></span>

#### <a name="keywordsaustriaeutaxfilenumber"></a><span data-ttu-id="ebaa0-126">Keywords_austria_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="ebaa0-126">Keywords_austria_eu_tax_file_number</span></span>

<span data-ttu-id="ebaa0-127">codice fiscale</span><span class="sxs-lookup"><span data-stu-id="ebaa0-127">tax number</span></span>
  
<span data-ttu-id="ebaa0-128">numero</span><span class="sxs-lookup"><span data-stu-id="ebaa0-128">number</span></span>
  
<span data-ttu-id="ebaa0-129">numero di registrazione fiscale</span><span class="sxs-lookup"><span data-stu-id="ebaa0-129">tax registration number</span></span>
  
<span data-ttu-id="ebaa0-130">tax id
</span><span class="sxs-lookup"><span data-stu-id="ebaa0-130">tax id</span></span>
  
<span data-ttu-id="ebaa0-131">St.Nr.</span><span class="sxs-lookup"><span data-stu-id="ebaa0-131">st.nr.</span></span>
  
<span data-ttu-id="ebaa0-132">Steuernummer</span><span class="sxs-lookup"><span data-stu-id="ebaa0-132">steuernummer</span></span>
  
## <a name="belgium"></a><span data-ttu-id="ebaa0-133">Belgio</span><span class="sxs-lookup"><span data-stu-id="ebaa0-133">Belgium</span></span>

### <a name="format"></a><span data-ttu-id="ebaa0-134">Formato</span><span class="sxs-lookup"><span data-stu-id="ebaa0-134">Format</span></span>

<span data-ttu-id="ebaa0-135">11 cifre senza spazi e delimitatori</span><span class="sxs-lookup"><span data-stu-id="ebaa0-135">11 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="ebaa0-136">Modello</span><span class="sxs-lookup"><span data-stu-id="ebaa0-136">Pattern</span></span>

<span data-ttu-id="ebaa0-137">11 cifre:</span><span class="sxs-lookup"><span data-stu-id="ebaa0-137">11 digits:</span></span>
  
- <span data-ttu-id="ebaa0-138">Due cifre</span><span class="sxs-lookup"><span data-stu-id="ebaa0-138">Two digits</span></span>
    
- <span data-ttu-id="ebaa0-139">"0" o "1"</span><span class="sxs-lookup"><span data-stu-id="ebaa0-139">A "0" or "1"</span></span>
    
- <span data-ttu-id="ebaa0-140">Una cifra</span><span class="sxs-lookup"><span data-stu-id="ebaa0-140">One digit</span></span>
    
- <span data-ttu-id="ebaa0-141">"0" o "1" o "2" o "3"</span><span class="sxs-lookup"><span data-stu-id="ebaa0-141">A "0" or "1" or "2" or "3"</span></span> 
    
- <span data-ttu-id="ebaa0-142">Sei cifre</span><span class="sxs-lookup"><span data-stu-id="ebaa0-142">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="ebaa0-143">Checksum</span><span class="sxs-lookup"><span data-stu-id="ebaa0-143">Checksum</span></span>

<span data-ttu-id="ebaa0-144">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="ebaa0-144">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="ebaa0-145">Definizione</span><span class="sxs-lookup"><span data-stu-id="ebaa0-145">Definition</span></span>

<span data-ttu-id="ebaa0-146">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="ebaa0-146">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="ebaa0-147">L'espressione `Regex_belgium_eu_tax_file_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="ebaa0-147">The regular expression  `Regex_belgium_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="ebaa0-148">Viene trovata una `Keywords_belgium_eu_tax_file_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="ebaa0-148">A keyword from  `Keywords_belgium_eu_tax_file_number` is found.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_belgium_eu_tax_file_number" />
          <Match idRef="Keywords_belgium_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="ebaa0-149">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="ebaa0-149">Keywords</span></span>

#### <a name="keywordsbelgiumeutaxfilenumber"></a><span data-ttu-id="ebaa0-150">Keywords_belgium_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="ebaa0-150">Keywords_belgium_eu_tax_file_number</span></span>

<span data-ttu-id="ebaa0-151">codice fiscale</span><span class="sxs-lookup"><span data-stu-id="ebaa0-151">tax number</span></span>
  
<span data-ttu-id="ebaa0-152">numero di registrazione nazionale</span><span class="sxs-lookup"><span data-stu-id="ebaa0-152">national registration number</span></span>
  
<span data-ttu-id="ebaa0-153">numero di registrazione fiscale</span><span class="sxs-lookup"><span data-stu-id="ebaa0-153">tax registration number</span></span>
  
<span data-ttu-id="ebaa0-154">tax id
</span><span class="sxs-lookup"><span data-stu-id="ebaa0-154">tax id</span></span>
  
<span data-ttu-id="ebaa0-155">NIF</span><span class="sxs-lookup"><span data-stu-id="ebaa0-155">nif</span></span>
  
<span data-ttu-id="ebaa0-156">NIF</span><span class="sxs-lookup"><span data-stu-id="ebaa0-156">nif#</span></span>
  
<span data-ttu-id="ebaa0-157">numéro de Registre National</span><span class="sxs-lookup"><span data-stu-id="ebaa0-157">numéro de registre national</span></span>
  
<span data-ttu-id="ebaa0-158">numéro d'identification fiscale</span><span class="sxs-lookup"><span data-stu-id="ebaa0-158">numéro d'identification fiscale</span></span>
  
## <a name="bulgaria"></a><span data-ttu-id="ebaa0-159">Bulgaria</span><span class="sxs-lookup"><span data-stu-id="ebaa0-159">Bulgaria</span></span>

### <a name="format"></a><span data-ttu-id="ebaa0-160">Formato</span><span class="sxs-lookup"><span data-stu-id="ebaa0-160">Format</span></span>

<span data-ttu-id="ebaa0-161">Dieci cifre senza spazi e delimitatori</span><span class="sxs-lookup"><span data-stu-id="ebaa0-161">Ten digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="ebaa0-162">Modello</span><span class="sxs-lookup"><span data-stu-id="ebaa0-162">Pattern</span></span>

<span data-ttu-id="ebaa0-163">10 cifre</span><span class="sxs-lookup"><span data-stu-id="ebaa0-163">10 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="ebaa0-164">Checksum</span><span class="sxs-lookup"><span data-stu-id="ebaa0-164">Checksum</span></span>

<span data-ttu-id="ebaa0-165">Sì</span><span class="sxs-lookup"><span data-stu-id="ebaa0-165">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="ebaa0-166">Definizione</span><span class="sxs-lookup"><span data-stu-id="ebaa0-166">Definition</span></span>

<span data-ttu-id="ebaa0-167">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="ebaa0-167">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="ebaa0-168">La funzione `Func_bulgaria_eu_tax_file_number` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="ebaa0-168">The function  `Func_bulgaria_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="ebaa0-169">Viene trovata una `Keywords_bulgaria_eu_tax_file_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="ebaa0-169">A keyword from  `Keywords_bulgaria_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="ebaa0-170">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="ebaa0-170">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="ebaa0-171">La funzione `Func_bulgaria_eu_tax_file_number` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="ebaa0-171">The function  `Func_bulgaria_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="ebaa0-172">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="ebaa0-172">Keywords</span></span>

#### <a name="keywordsbulgariaeutaxfilenumber"></a><span data-ttu-id="ebaa0-173">Keywords_bulgaria_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="ebaa0-173">Keywords_bulgaria_eu_tax_file_number</span></span>

<span data-ttu-id="ebaa0-174">bucn</span><span class="sxs-lookup"><span data-stu-id="ebaa0-174">bucn</span></span>
  
<span data-ttu-id="ebaa0-175">numero civile uniforme</span><span class="sxs-lookup"><span data-stu-id="ebaa0-175">uniform civil number</span></span>
  
<span data-ttu-id="ebaa0-176">bucn #</span><span class="sxs-lookup"><span data-stu-id="ebaa0-176">bucn#</span></span>
  
<span data-ttu-id="ebaa0-177">uniformcivilnumber #</span><span class="sxs-lookup"><span data-stu-id="ebaa0-177">uniformcivilnumber#</span></span>
  
<span data-ttu-id="ebaa0-178">ID civile uniforme</span><span class="sxs-lookup"><span data-stu-id="ebaa0-178">uniform civil id</span></span>
  
<span data-ttu-id="ebaa0-179">uniforme civile No</span><span class="sxs-lookup"><span data-stu-id="ebaa0-179">uniform civil no</span></span>
  
<span data-ttu-id="ebaa0-180">EGN</span><span class="sxs-lookup"><span data-stu-id="ebaa0-180">egn</span></span>
  
<span data-ttu-id="ebaa0-181">numero civile uniforme bulgaro</span><span class="sxs-lookup"><span data-stu-id="ebaa0-181">bulgarian uniform civil number</span></span>
  
<span data-ttu-id="ebaa0-182">uniformcivilno #</span><span class="sxs-lookup"><span data-stu-id="ebaa0-182">uniformcivilno#</span></span>
  
<span data-ttu-id="ebaa0-183">EGN</span><span class="sxs-lookup"><span data-stu-id="ebaa0-183">egn#</span></span>
  
<span data-ttu-id="ebaa0-184">униформ граждански Номер</span><span class="sxs-lookup"><span data-stu-id="ebaa0-184">униформ граждански номер</span></span>
  
<span data-ttu-id="ebaa0-185">ID униформ</span><span class="sxs-lookup"><span data-stu-id="ebaa0-185">униформ id</span></span>
  
<span data-ttu-id="ebaa0-186">ID граждански униформ</span><span class="sxs-lookup"><span data-stu-id="ebaa0-186">униформ граждански id</span></span>
  
<span data-ttu-id="ebaa0-187">униформ граждански не</span><span class="sxs-lookup"><span data-stu-id="ebaa0-187">униформ граждански не</span></span>
  
## <a name="croatia"></a><span data-ttu-id="ebaa0-188">Croazia</span><span class="sxs-lookup"><span data-stu-id="ebaa0-188">Croatia</span></span>

### <a name="format"></a><span data-ttu-id="ebaa0-189">Formato</span><span class="sxs-lookup"><span data-stu-id="ebaa0-189">Format</span></span>

<span data-ttu-id="ebaa0-190">11 cifre senza spazi o delimitatori</span><span class="sxs-lookup"><span data-stu-id="ebaa0-190">11 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="ebaa0-191">Modello</span><span class="sxs-lookup"><span data-stu-id="ebaa0-191">Pattern</span></span>

<span data-ttu-id="ebaa0-192">11 cifre:</span><span class="sxs-lookup"><span data-stu-id="ebaa0-192">11 digits:</span></span>
  
- <span data-ttu-id="ebaa0-193">Dieci cifre, scelte casualmente</span><span class="sxs-lookup"><span data-stu-id="ebaa0-193">Ten digits, randomly chosen</span></span>
    
- <span data-ttu-id="ebaa0-194">Una cifra di controllo</span><span class="sxs-lookup"><span data-stu-id="ebaa0-194">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="ebaa0-195">Checksum</span><span class="sxs-lookup"><span data-stu-id="ebaa0-195">Checksum</span></span>

<span data-ttu-id="ebaa0-196">Sì</span><span class="sxs-lookup"><span data-stu-id="ebaa0-196">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="ebaa0-197">Definizione</span><span class="sxs-lookup"><span data-stu-id="ebaa0-197">Definition</span></span>

<span data-ttu-id="ebaa0-198">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="ebaa0-198">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="ebaa0-199">La funzione `Func_croatia_eu_tax_file_number` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="ebaa0-199">The function  `Func_croatia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="ebaa0-200">Viene trovata una `Keywords_croatia_eu_tax_file_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="ebaa0-200">A keyword from  `Keywords_croatia_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="ebaa0-201">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="ebaa0-201">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="ebaa0-202">La funzione `Func_croatia_eu_tax_file_number` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="ebaa0-202">The function  `Func_croatia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="ebaa0-203">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="ebaa0-203">Keywords</span></span>

#### <a name="keywordscroatiaeutaxfilenumber"></a><span data-ttu-id="ebaa0-204">Keywords_croatia_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="ebaa0-204">Keywords_croatia_eu_tax_file_number</span></span>

<span data-ttu-id="ebaa0-205">codice fiscale</span><span class="sxs-lookup"><span data-stu-id="ebaa0-205">tax number</span></span>
  
<span data-ttu-id="ebaa0-206">imposte</span><span class="sxs-lookup"><span data-stu-id="ebaa0-206">tax</span></span>
  
<span data-ttu-id="ebaa0-207">tax id
</span><span class="sxs-lookup"><span data-stu-id="ebaa0-207">tax id</span></span>
  
<span data-ttu-id="ebaa0-208">OID</span><span class="sxs-lookup"><span data-stu-id="ebaa0-208">oid</span></span>
  
<span data-ttu-id="ebaa0-209">OID</span><span class="sxs-lookup"><span data-stu-id="ebaa0-209">oid#</span></span>
  
<span data-ttu-id="ebaa0-210">Porezni broj</span><span class="sxs-lookup"><span data-stu-id="ebaa0-210">porezni broj</span></span>
  
## <a name="cyprus"></a><span data-ttu-id="ebaa0-211">Cipro</span><span class="sxs-lookup"><span data-stu-id="ebaa0-211">Cyprus</span></span>

### <a name="format"></a><span data-ttu-id="ebaa0-212">Formato</span><span class="sxs-lookup"><span data-stu-id="ebaa0-212">Format</span></span>

<span data-ttu-id="ebaa0-213">Otto cifre e una lettera nel modello specificato</span><span class="sxs-lookup"><span data-stu-id="ebaa0-213">Eight digits and one letter in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="ebaa0-214">Modello</span><span class="sxs-lookup"><span data-stu-id="ebaa0-214">Pattern</span></span>

<span data-ttu-id="ebaa0-215">Otto cifre e una lettera:</span><span class="sxs-lookup"><span data-stu-id="ebaa0-215">Eight digits and one letter:</span></span>
  
-  <span data-ttu-id="ebaa0-216">Un "0"</span><span class="sxs-lookup"><span data-stu-id="ebaa0-216">A "0"</span></span> 
    
- <span data-ttu-id="ebaa0-217">Sette cifre</span><span class="sxs-lookup"><span data-stu-id="ebaa0-217">Seven digits</span></span>
    
- <span data-ttu-id="ebaa0-218">Una lettera (senza distinzione tra maiuscole e minuscole)</span><span class="sxs-lookup"><span data-stu-id="ebaa0-218">One letter (not case-sensitive)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="ebaa0-219">Checksum</span><span class="sxs-lookup"><span data-stu-id="ebaa0-219">Checksum</span></span>

<span data-ttu-id="ebaa0-220">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="ebaa0-220">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="ebaa0-221">Definizione</span><span class="sxs-lookup"><span data-stu-id="ebaa0-221">Definition</span></span>

<span data-ttu-id="ebaa0-222">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="ebaa0-222">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="ebaa0-223">La funzione `Func_cyprus_eu_tax_file_number` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="ebaa0-223">The function  `Func_cyprus_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="ebaa0-224">Viene trovata una `Keywords_cyprus_eu_tax_file_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="ebaa0-224">A keyword from  `Keywords_cyprus_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="ebaa0-225">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="ebaa0-225">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="ebaa0-226">La funzione `Func_cyprus_eu_tax_file_number` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="ebaa0-226">The function  `Func_cyprus_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="ebaa0-227">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="ebaa0-227">Keywords</span></span>

#### <a name="keywordscypruseutaxfilenumber"></a><span data-ttu-id="ebaa0-228">Keywords_cyprus_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="ebaa0-228">Keywords_cyprus_eu_tax_file_number</span></span>

<span data-ttu-id="ebaa0-229">codice fiscale</span><span class="sxs-lookup"><span data-stu-id="ebaa0-229">tax number</span></span>
  
<span data-ttu-id="ebaa0-230">imposte</span><span class="sxs-lookup"><span data-stu-id="ebaa0-230">tax</span></span>
  
<span data-ttu-id="ebaa0-231">tax id
</span><span class="sxs-lookup"><span data-stu-id="ebaa0-231">tax id</span></span>
  
<span data-ttu-id="ebaa0-232">codice di identificazione fiscale</span><span class="sxs-lookup"><span data-stu-id="ebaa0-232">tax identification code</span></span>
  
<span data-ttu-id="ebaa0-233">TIC</span><span class="sxs-lookup"><span data-stu-id="ebaa0-233">tic</span></span>
  
<span data-ttu-id="ebaa0-234">TIC</span><span class="sxs-lookup"><span data-stu-id="ebaa0-234">tic#</span></span>
  
<span data-ttu-id="ebaa0-235">Αριθμός φορολογικού Μητρώου</span><span class="sxs-lookup"><span data-stu-id="ebaa0-235">αριθμός φορολογικού μητρώου</span></span>
  
<span data-ttu-id="ebaa0-236">φορολογική ταυτότητα</span><span class="sxs-lookup"><span data-stu-id="ebaa0-236">φορολογική ταυτότητα</span></span>
  
<span data-ttu-id="ebaa0-237">Κωδικός φορολογικού Μητρώου</span><span class="sxs-lookup"><span data-stu-id="ebaa0-237">κωδικός φορολογικού μητρώου</span></span>
  
## <a name="czech-republic"></a><span data-ttu-id="ebaa0-238">Repubblica Ceca</span><span class="sxs-lookup"><span data-stu-id="ebaa0-238">Czech Republic</span></span>

### <a name="format"></a><span data-ttu-id="ebaa0-239">Formato</span><span class="sxs-lookup"><span data-stu-id="ebaa0-239">Format</span></span>

<span data-ttu-id="ebaa0-240">Nove o dieci cifre con una barra rovesciata facoltativa</span><span class="sxs-lookup"><span data-stu-id="ebaa0-240">Nine or ten digits with an optional backslash</span></span>
  
### <a name="pattern"></a><span data-ttu-id="ebaa0-241">Modello</span><span class="sxs-lookup"><span data-stu-id="ebaa0-241">Pattern</span></span>

<span data-ttu-id="ebaa0-242">Nove o dieci cifre con un backslash facoltativo:</span><span class="sxs-lookup"><span data-stu-id="ebaa0-242">Nine or ten digits with an optional backslashl:</span></span>
  
- <span data-ttu-id="ebaa0-243">Sei cifre</span><span class="sxs-lookup"><span data-stu-id="ebaa0-243">Six digits</span></span> 
    
- <span data-ttu-id="ebaa0-244">Una barra rovesciata (facoltativa)</span><span class="sxs-lookup"><span data-stu-id="ebaa0-244">A backslash (optional)</span></span>
    
- <span data-ttu-id="ebaa0-245">Tre o quattro cifre</span><span class="sxs-lookup"><span data-stu-id="ebaa0-245">Three or four digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="ebaa0-246">Checksum</span><span class="sxs-lookup"><span data-stu-id="ebaa0-246">Checksum</span></span>

<span data-ttu-id="ebaa0-247">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="ebaa0-247">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="ebaa0-248">Definizione</span><span class="sxs-lookup"><span data-stu-id="ebaa0-248">Definition</span></span>

<span data-ttu-id="ebaa0-249">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="ebaa0-249">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="ebaa0-250">L'espressione `Regex_czech_republic_eu_tax_file_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="ebaa0-250">The regular expression  `Regex_czech_republic_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="ebaa0-251">Viene trovata una `Keywords_czech_republic_eu_tax_file_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="ebaa0-251">A keyword from  `Keywords_czech_republic_eu_tax_file_number` is found.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_czech_republic_eu_tax_file_number" />
          <Match idRef="Keywords_czech_republic_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="ebaa0-252">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="ebaa0-252">Keywords</span></span>

#### <a name="keywordsczechrepubliceutaxfilenumber"></a><span data-ttu-id="ebaa0-253">Keywords_czech_republic_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="ebaa0-253">Keywords_czech_republic_eu_tax_file_number</span></span>

<span data-ttu-id="ebaa0-254">codice fiscale</span><span class="sxs-lookup"><span data-stu-id="ebaa0-254">tax number</span></span>
  
<span data-ttu-id="ebaa0-255">imposte</span><span class="sxs-lookup"><span data-stu-id="ebaa0-255">tax</span></span>
  
<span data-ttu-id="ebaa0-256">tax id
</span><span class="sxs-lookup"><span data-stu-id="ebaa0-256">tax id</span></span>
  
<span data-ttu-id="ebaa0-257">numero personale</span><span class="sxs-lookup"><span data-stu-id="ebaa0-257">personal number</span></span>
  
<span data-ttu-id="ebaa0-258">daňové číslo</span><span class="sxs-lookup"><span data-stu-id="ebaa0-258">daňové číslo</span></span>
  
<span data-ttu-id="ebaa0-259">osobní číslo</span><span class="sxs-lookup"><span data-stu-id="ebaa0-259">osobní číslo</span></span>
  
## <a name="denmark"></a><span data-ttu-id="ebaa0-260">Danimarca</span><span class="sxs-lookup"><span data-stu-id="ebaa0-260">Denmark</span></span>

### <a name="format"></a><span data-ttu-id="ebaa0-261">Formato</span><span class="sxs-lookup"><span data-stu-id="ebaa0-261">Format</span></span>

<span data-ttu-id="ebaa0-262">Dieci cifre contenenti un segno meno</span><span class="sxs-lookup"><span data-stu-id="ebaa0-262">Ten digits containing a hyphen</span></span>
  
### <a name="pattern"></a><span data-ttu-id="ebaa0-263">Modello</span><span class="sxs-lookup"><span data-stu-id="ebaa0-263">Pattern</span></span>

<span data-ttu-id="ebaa0-264">Dieci cifre contenenti un segno meno:</span><span class="sxs-lookup"><span data-stu-id="ebaa0-264">Ten digits containing a hyphenl:</span></span>
  
-  <span data-ttu-id="ebaa0-265">Sei cifre che corrispondono alla data di nascita (GGMMAA)</span><span class="sxs-lookup"><span data-stu-id="ebaa0-265">Six digits that correspond to the birth date (DDMMYY)</span></span> 
    
- <span data-ttu-id="ebaa0-266">Una lineetta</span><span class="sxs-lookup"><span data-stu-id="ebaa0-266">A hyphen</span></span>
    
- <span data-ttu-id="ebaa0-267">Quattro cifre che corrispondono a un numero di sequenza in cui la prima cifra corrisponde al secolo di nascita e l'ultima cifra corrisponde al sesso dell'individuo (dispari per il maschio e anche per le femmine)</span><span class="sxs-lookup"><span data-stu-id="ebaa0-267">Four digits that correspond to a sequence number where the first digit corresponds to the century of birth and the last digit corresponds to the individual's gender (odd for male and even for female)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="ebaa0-268">Checksum</span><span class="sxs-lookup"><span data-stu-id="ebaa0-268">Checksum</span></span>

<span data-ttu-id="ebaa0-269">Sì</span><span class="sxs-lookup"><span data-stu-id="ebaa0-269">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="ebaa0-270">Definizione</span><span class="sxs-lookup"><span data-stu-id="ebaa0-270">Definition</span></span>

<span data-ttu-id="ebaa0-271">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="ebaa0-271">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="ebaa0-272">La funzione `Func_denmark_eu_tax_file_number` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="ebaa0-272">The function  `Func_denmark_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="ebaa0-273">Viene trovata una `Keywords_denmark_eu_tax_file_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="ebaa0-273">A keyword from  `Keywords_denmark_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="ebaa0-274">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="ebaa0-274">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="ebaa0-275">La funzione `Func_denmark_eu_tax_file_number` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="ebaa0-275">The function  `Func_denmark_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="ebaa0-276">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="ebaa0-276">Keywords</span></span>

#### <a name="keywordsdenmarkeutaxfilenumber"></a><span data-ttu-id="ebaa0-277">Keywords_denmark_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="ebaa0-277">Keywords_denmark_eu_tax_file_number</span></span>

<span data-ttu-id="ebaa0-278">codice fiscale</span><span class="sxs-lookup"><span data-stu-id="ebaa0-278">tax number</span></span>
  
<span data-ttu-id="ebaa0-279">imposte</span><span class="sxs-lookup"><span data-stu-id="ebaa0-279">tax</span></span>
  
<span data-ttu-id="ebaa0-280">tax id
</span><span class="sxs-lookup"><span data-stu-id="ebaa0-280">tax id</span></span>
  
<span data-ttu-id="ebaa0-281">numero CPR</span><span class="sxs-lookup"><span data-stu-id="ebaa0-281">cpr number</span></span>
  
<span data-ttu-id="ebaa0-282">CPR</span><span class="sxs-lookup"><span data-stu-id="ebaa0-282">cpr#</span></span>
  
<span data-ttu-id="ebaa0-283">Nummer di pattinaggio</span><span class="sxs-lookup"><span data-stu-id="ebaa0-283">skat nummer</span></span>
  
<span data-ttu-id="ebaa0-284">ID pattina</span><span class="sxs-lookup"><span data-stu-id="ebaa0-284">skat id</span></span>
  
## <a name="estonia"></a><span data-ttu-id="ebaa0-285">Estonia</span><span class="sxs-lookup"><span data-stu-id="ebaa0-285">Estonia</span></span>

### <a name="format"></a><span data-ttu-id="ebaa0-286">Formato</span><span class="sxs-lookup"><span data-stu-id="ebaa0-286">Format</span></span>

<span data-ttu-id="ebaa0-287">11 cifre senza spazi o delimitatori</span><span class="sxs-lookup"><span data-stu-id="ebaa0-287">11 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="ebaa0-288">Modello</span><span class="sxs-lookup"><span data-stu-id="ebaa0-288">Pattern</span></span>

<span data-ttu-id="ebaa0-289">11 cifre:</span><span class="sxs-lookup"><span data-stu-id="ebaa0-289">11 digits:</span></span>
  
-  <span data-ttu-id="ebaa0-290">Una cifra che corrisponde al sesso e al secolo del parto, in cui un numero dispari indica il maschio e il numero pari indica la femmina come segue: 1,2 per il XIX secolo; 3,4 per il XX secolo; e 5,6 per il XXI secolo</span><span class="sxs-lookup"><span data-stu-id="ebaa0-290">One digit that corresponds to gender and century of birth where an odd number indicates male and the even number indicates female as follows: 1, 2 for the 19th century; 3, 4 for the 20th century; and 5, 6 for the 21st century</span></span> 
    
- <span data-ttu-id="ebaa0-291">Sei cifre che corrispondono alla data di nascita (AAMMGG)</span><span class="sxs-lookup"><span data-stu-id="ebaa0-291">Six digits that correspond to birth date (YYMMDD)</span></span>
    
- <span data-ttu-id="ebaa0-292">Tre cifre che corrispondono a un numero di serie che separa le persone nate nella stessa data</span><span class="sxs-lookup"><span data-stu-id="ebaa0-292">Three digits that correspond to a serial number separating persons born on the same date</span></span>
    
- <span data-ttu-id="ebaa0-293">Una cifra di controllo</span><span class="sxs-lookup"><span data-stu-id="ebaa0-293">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="ebaa0-294">Checksum</span><span class="sxs-lookup"><span data-stu-id="ebaa0-294">Checksum</span></span>

<span data-ttu-id="ebaa0-295">Sì</span><span class="sxs-lookup"><span data-stu-id="ebaa0-295">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="ebaa0-296">Definizione</span><span class="sxs-lookup"><span data-stu-id="ebaa0-296">Definition</span></span>

<span data-ttu-id="ebaa0-297">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="ebaa0-297">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="ebaa0-298">La funzione `Func_estonia_eu_tax_file_number` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="ebaa0-298">The function  `Func_estonia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="ebaa0-299">Viene trovata una `Keywords_estonia_eu_tax_file_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="ebaa0-299">A keyword from  `Keywords_estonia_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="ebaa0-300">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="ebaa0-300">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="ebaa0-301">La funzione `Func_estonia_eu_tax_file_number` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="ebaa0-301">The function  `Func_estonia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="ebaa0-302">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="ebaa0-302">Keywords</span></span>

#### <a name="keywordsestoniaeutaxfilenumber"></a><span data-ttu-id="ebaa0-303">Keywords_estonia_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="ebaa0-303">Keywords_estonia_eu_tax_file_number</span></span>

<span data-ttu-id="ebaa0-304">codice fiscale</span><span class="sxs-lookup"><span data-stu-id="ebaa0-304">tax number</span></span>
  
<span data-ttu-id="ebaa0-305">imposte</span><span class="sxs-lookup"><span data-stu-id="ebaa0-305">tax</span></span>
  
<span data-ttu-id="ebaa0-306">tax id
</span><span class="sxs-lookup"><span data-stu-id="ebaa0-306">tax id</span></span>
  
<span data-ttu-id="ebaa0-307">codice personale</span><span class="sxs-lookup"><span data-stu-id="ebaa0-307">personal code</span></span>
  
<span data-ttu-id="ebaa0-308">maksunumber</span><span class="sxs-lookup"><span data-stu-id="ebaa0-308">maksunumber</span></span>
  
<span data-ttu-id="ebaa0-309">ID maksu</span><span class="sxs-lookup"><span data-stu-id="ebaa0-309">maksu id</span></span>
  
<span data-ttu-id="ebaa0-310">isikukood</span><span class="sxs-lookup"><span data-stu-id="ebaa0-310">isikukood</span></span>
  
## <a name="finland"></a><span data-ttu-id="ebaa0-311">Finlandia</span><span class="sxs-lookup"><span data-stu-id="ebaa0-311">Finland</span></span>

### <a name="format"></a><span data-ttu-id="ebaa0-312">Formato</span><span class="sxs-lookup"><span data-stu-id="ebaa0-312">Format</span></span>

<span data-ttu-id="ebaa0-313">Una combinazione di 11 caratteri di cifre, lettere e segno più e meno</span><span class="sxs-lookup"><span data-stu-id="ebaa0-313">An 11-character combination of digits, letters, and plus and minus sign</span></span>
  
### <a name="pattern"></a><span data-ttu-id="ebaa0-314">Modello</span><span class="sxs-lookup"><span data-stu-id="ebaa0-314">Pattern</span></span>

<span data-ttu-id="ebaa0-315">Una combinazione di 11 caratteri di cifre, lettere e segno più e meno:</span><span class="sxs-lookup"><span data-stu-id="ebaa0-315">An 11-character combination of digits, letters, and plus and minus sign:</span></span>
  
- <span data-ttu-id="ebaa0-316">Sei cifre</span><span class="sxs-lookup"><span data-stu-id="ebaa0-316">Six digits</span></span>
    
- <span data-ttu-id="ebaa0-317">Uno dei seguenti: un segno più, un segno di sottrazione o la lettera "A" (senza distinzione tra maiuscole/minuscole), in cui il segno più significa Nato tra 1800-1899, il segno meno significa Nato tra 1900-1999 e "A" significa Nato 2000 e dopo</span><span class="sxs-lookup"><span data-stu-id="ebaa0-317">One of the following: a plus sign, a minus sign, or the letter "A" (not case sensitive) where the plus sign means born between 1800-1899, the minus sign means born between 1900-1999, and "A" means born 2000 and after</span></span>
    
- <span data-ttu-id="ebaa0-318">Tre cifre</span><span class="sxs-lookup"><span data-stu-id="ebaa0-318">Three digits</span></span>
    
- <span data-ttu-id="ebaa0-319">Una lettera o un numero</span><span class="sxs-lookup"><span data-stu-id="ebaa0-319">One letter or one number</span></span>
    
### <a name="checksum"></a><span data-ttu-id="ebaa0-320">Checksum</span><span class="sxs-lookup"><span data-stu-id="ebaa0-320">Checksum</span></span>

<span data-ttu-id="ebaa0-321">Sì</span><span class="sxs-lookup"><span data-stu-id="ebaa0-321">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="ebaa0-322">Definizione</span><span class="sxs-lookup"><span data-stu-id="ebaa0-322">Definition</span></span>

<span data-ttu-id="ebaa0-323">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="ebaa0-323">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="ebaa0-324">La funzione `Func_finland_eu_tax_file_number` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="ebaa0-324">The function  `Func_finland_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="ebaa0-325">Viene trovata una `Keywords_finland_eu_tax_file_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="ebaa0-325">A keyword from  `Keywords_finland_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="ebaa0-326">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="ebaa0-326">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="ebaa0-327">La funzione `Func_finland_eu_tax_file_number` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="ebaa0-327">The function  `Func_finland_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="ebaa0-328">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="ebaa0-328">Keywords</span></span>

#### <a name="keywordsfinlandeutaxfilenumber"></a><span data-ttu-id="ebaa0-329">Keywords_finland_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="ebaa0-329">Keywords_finland_eu_tax_file_number</span></span>

<span data-ttu-id="ebaa0-330">identification number
</span><span class="sxs-lookup"><span data-stu-id="ebaa0-330">identification number</span></span>
  
<span data-ttu-id="ebaa0-331">ID personale</span><span class="sxs-lookup"><span data-stu-id="ebaa0-331">personal id</span></span>
  
<span data-ttu-id="ebaa0-332">numero di identità</span><span class="sxs-lookup"><span data-stu-id="ebaa0-332">identity number</span></span>
  
<span data-ttu-id="ebaa0-333">numero di identificazione nazionale finlandese</span><span class="sxs-lookup"><span data-stu-id="ebaa0-333">finnish national id number</span></span>
  
<span data-ttu-id="ebaa0-334">personalidnumber #</span><span class="sxs-lookup"><span data-stu-id="ebaa0-334">personalidnumber#</span></span>
  
<span data-ttu-id="ebaa0-335">numero di identificazione nazionale</span><span class="sxs-lookup"><span data-stu-id="ebaa0-335">national identification number</span></span>
  
<span data-ttu-id="ebaa0-336">numero ID</span><span class="sxs-lookup"><span data-stu-id="ebaa0-336">id number</span></span>
  
<span data-ttu-id="ebaa0-337">ID nazionale No.</span><span class="sxs-lookup"><span data-stu-id="ebaa0-337">national id no.</span></span>
  
<span data-ttu-id="ebaa0-338">numero ID nazionale</span><span class="sxs-lookup"><span data-stu-id="ebaa0-338">national id number</span></span>
  
<span data-ttu-id="ebaa0-339">ID No</span><span class="sxs-lookup"><span data-stu-id="ebaa0-339">id no</span></span>
  
<span data-ttu-id="ebaa0-340">tunnistenumero</span><span class="sxs-lookup"><span data-stu-id="ebaa0-340">tunnistenumero</span></span>
  
<span data-ttu-id="ebaa0-341">henkilötunnus</span><span class="sxs-lookup"><span data-stu-id="ebaa0-341">henkilötunnus</span></span>
  
<span data-ttu-id="ebaa0-342">yksilöllinen henkilökohtainen tunnistenumero</span><span class="sxs-lookup"><span data-stu-id="ebaa0-342">yksilöllinen henkilökohtainen tunnistenumero</span></span>
  
<span data-ttu-id="ebaa0-343">ainutlaatuinen henkilökohtainen tunnus</span><span class="sxs-lookup"><span data-stu-id="ebaa0-343">ainutlaatuinen henkilökohtainen tunnus</span></span>
  
<span data-ttu-id="ebaa0-344">numero identiteetti</span><span class="sxs-lookup"><span data-stu-id="ebaa0-344">identiteetti numero</span></span>
  
<span data-ttu-id="ebaa0-345">Suomen Kansallinen henkilötunnus</span><span class="sxs-lookup"><span data-stu-id="ebaa0-345">suomen kansallinen henkilötunnus</span></span>
  
<span data-ttu-id="ebaa0-346">henkilötunnusnumero #</span><span class="sxs-lookup"><span data-stu-id="ebaa0-346">henkilötunnusnumero#</span></span>
  
<span data-ttu-id="ebaa0-347">kansallisen tunnistenumero</span><span class="sxs-lookup"><span data-stu-id="ebaa0-347">kansallisen tunnistenumero</span></span>
  
<span data-ttu-id="ebaa0-348">tunnusnumero</span><span class="sxs-lookup"><span data-stu-id="ebaa0-348">tunnusnumero</span></span>
  
<span data-ttu-id="ebaa0-349">Kansallinen tunnus numero</span><span class="sxs-lookup"><span data-stu-id="ebaa0-349">kansallinen tunnus numero</span></span>
  
## <a name="france"></a><span data-ttu-id="ebaa0-350">Francia</span><span class="sxs-lookup"><span data-stu-id="ebaa0-350">France</span></span>

### <a name="format"></a><span data-ttu-id="ebaa0-351">Formato</span><span class="sxs-lookup"><span data-stu-id="ebaa0-351">Format</span></span>

<span data-ttu-id="ebaa0-352">13 cifre per gli utenti e nove cifre per le entità</span><span class="sxs-lookup"><span data-stu-id="ebaa0-352">13 digits for individuals and nine digits for entities</span></span>
  
### <a name="pattern"></a><span data-ttu-id="ebaa0-353">Modello</span><span class="sxs-lookup"><span data-stu-id="ebaa0-353">Pattern</span></span>

<span data-ttu-id="ebaa0-354">13 cifre per gli utenti:</span><span class="sxs-lookup"><span data-stu-id="ebaa0-354">13 digits for individuals:</span></span>
  
- <span data-ttu-id="ebaa0-355">Una cifra che deve essere 0, 1, 2 o 3</span><span class="sxs-lookup"><span data-stu-id="ebaa0-355">One digit that must be 0, 1, 2, or 3</span></span>
    
- <span data-ttu-id="ebaa0-356">12 cifre</span><span class="sxs-lookup"><span data-stu-id="ebaa0-356">12 digits</span></span>
    
<span data-ttu-id="ebaa0-357">Nove cifre per le entità</span><span class="sxs-lookup"><span data-stu-id="ebaa0-357">Nine digits for entities</span></span>
  
### <a name="checksum"></a><span data-ttu-id="ebaa0-358">Checksum</span><span class="sxs-lookup"><span data-stu-id="ebaa0-358">Checksum</span></span>

<span data-ttu-id="ebaa0-359">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="ebaa0-359">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="ebaa0-360">Definizione</span><span class="sxs-lookup"><span data-stu-id="ebaa0-360">Definition</span></span>

<span data-ttu-id="ebaa0-361">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="ebaa0-361">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="ebaa0-362">La funzione `Func_france_eu_tax_file_number` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="ebaa0-362">The function  `Func_france_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="ebaa0-363">Viene trovata una `Keywords_france_eu_tax_file_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="ebaa0-363">A keyword from  `Keywords_france_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="ebaa0-364">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="ebaa0-364">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="ebaa0-365">La funzione `Func_france_eu_tax_file_number` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="ebaa0-365">The function  `Func_france_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="ebaa0-366">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="ebaa0-366">Keywords</span></span>

#### <a name="keywordsfranceeutaxfilenumber"></a><span data-ttu-id="ebaa0-367">Keywords_france_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="ebaa0-367">Keywords_france_eu_tax_file_number</span></span>

<span data-ttu-id="ebaa0-368">codice di identificazione fiscale</span><span class="sxs-lookup"><span data-stu-id="ebaa0-368">tax identification number</span></span>
  
<span data-ttu-id="ebaa0-369">codice fiscale</span><span class="sxs-lookup"><span data-stu-id="ebaa0-369">tax number</span></span>
  
<span data-ttu-id="ebaa0-370">tax id
</span><span class="sxs-lookup"><span data-stu-id="ebaa0-370">tax id</span></span>
  
<span data-ttu-id="ebaa0-371">numéro d'identification fiscale</span><span class="sxs-lookup"><span data-stu-id="ebaa0-371">numéro d'identification fiscale</span></span>
  
## <a name="germany"></a><span data-ttu-id="ebaa0-372">Germania</span><span class="sxs-lookup"><span data-stu-id="ebaa0-372">Germany</span></span>

### <a name="format"></a><span data-ttu-id="ebaa0-373">Formato</span><span class="sxs-lookup"><span data-stu-id="ebaa0-373">Format</span></span>

<span data-ttu-id="ebaa0-374">11 cifre senza spazi e delimitatori</span><span class="sxs-lookup"><span data-stu-id="ebaa0-374">11 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="ebaa0-375">Modello</span><span class="sxs-lookup"><span data-stu-id="ebaa0-375">Pattern</span></span>

<span data-ttu-id="ebaa0-376">11 cifre:</span><span class="sxs-lookup"><span data-stu-id="ebaa0-376">11 digits :</span></span>
  
-  <span data-ttu-id="ebaa0-377">Dieci cifre</span><span class="sxs-lookup"><span data-stu-id="ebaa0-377">Ten digits</span></span> 
    
- <span data-ttu-id="ebaa0-378">Una cifra di controllo</span><span class="sxs-lookup"><span data-stu-id="ebaa0-378">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="ebaa0-379">Checksum</span><span class="sxs-lookup"><span data-stu-id="ebaa0-379">Checksum</span></span>

<span data-ttu-id="ebaa0-380">Sì</span><span class="sxs-lookup"><span data-stu-id="ebaa0-380">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="ebaa0-381">Definizione</span><span class="sxs-lookup"><span data-stu-id="ebaa0-381">Definition</span></span>

<span data-ttu-id="ebaa0-382">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="ebaa0-382">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="ebaa0-383">La funzione `Func_germany_eu_tax_file_number` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="ebaa0-383">The function  `Func_germany_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="ebaa0-384">Viene trovata una `Keywords_germany_eu_tax_file_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="ebaa0-384">A keyword from  `Keywords_germany_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="ebaa0-385">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="ebaa0-385">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="ebaa0-386">La funzione `Func_germany_eu_tax_file_number` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="ebaa0-386">The function  `Func_germany_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="ebaa0-387">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="ebaa0-387">Keywords</span></span>

#### <a name="keywordsgermanyeutaxfilenumber"></a><span data-ttu-id="ebaa0-388">Keywords_germany_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="ebaa0-388">Keywords_germany_eu_tax_file_number</span></span>

<span data-ttu-id="ebaa0-389">codice fiscale</span><span class="sxs-lookup"><span data-stu-id="ebaa0-389">tax number</span></span>
  
<span data-ttu-id="ebaa0-390">tassa no.</span><span class="sxs-lookup"><span data-stu-id="ebaa0-390">tax no.</span></span>
  
<span data-ttu-id="ebaa0-391">taxno #</span><span class="sxs-lookup"><span data-stu-id="ebaa0-391">taxno#</span></span>
  
<span data-ttu-id="ebaa0-392">taxnumber #</span><span class="sxs-lookup"><span data-stu-id="ebaa0-392">taxnumber#</span></span>
  
<span data-ttu-id="ebaa0-393">taxnumber</span><span class="sxs-lookup"><span data-stu-id="ebaa0-393">taxnumber</span></span>
  
<span data-ttu-id="ebaa0-394">tax id
</span><span class="sxs-lookup"><span data-stu-id="ebaa0-394">tax id</span></span>
  
<span data-ttu-id="ebaa0-395">taxid #</span><span class="sxs-lookup"><span data-stu-id="ebaa0-395">taxid#</span></span>
  
<span data-ttu-id="ebaa0-396">codice di identificazione fiscale</span><span class="sxs-lookup"><span data-stu-id="ebaa0-396">tax identification number</span></span>
  
<span data-ttu-id="ebaa0-397">codice fiscale n.</span><span class="sxs-lookup"><span data-stu-id="ebaa0-397">tax identification no.</span></span>
  
<span data-ttu-id="ebaa0-398">Steuernummer</span><span class="sxs-lookup"><span data-stu-id="ebaa0-398">steuernummer</span></span>
  
<span data-ttu-id="ebaa0-399">ID Steuer</span><span class="sxs-lookup"><span data-stu-id="ebaa0-399">steuer id</span></span>
  
<span data-ttu-id="ebaa0-400">steueridentifikationsnummer</span><span class="sxs-lookup"><span data-stu-id="ebaa0-400">steueridentifikationsnummer</span></span>
  
## <a name="greece"></a><span data-ttu-id="ebaa0-401">Grecia</span><span class="sxs-lookup"><span data-stu-id="ebaa0-401">Greece</span></span>

### <a name="format"></a><span data-ttu-id="ebaa0-402">Formato</span><span class="sxs-lookup"><span data-stu-id="ebaa0-402">Format</span></span>

<span data-ttu-id="ebaa0-403">Nove cifre senza spazi e delimitatori</span><span class="sxs-lookup"><span data-stu-id="ebaa0-403">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="ebaa0-404">Modello</span><span class="sxs-lookup"><span data-stu-id="ebaa0-404">Pattern</span></span>

<span data-ttu-id="ebaa0-405">9 cifre</span><span class="sxs-lookup"><span data-stu-id="ebaa0-405">Nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="ebaa0-406">Checksum</span><span class="sxs-lookup"><span data-stu-id="ebaa0-406">Checksum</span></span>

<span data-ttu-id="ebaa0-407">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="ebaa0-407">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="ebaa0-408">Definizione</span><span class="sxs-lookup"><span data-stu-id="ebaa0-408">Definition</span></span>

<span data-ttu-id="ebaa0-409">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="ebaa0-409">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="ebaa0-410">L'espressione `Regex_greece_eu_tax_file_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="ebaa0-410">The regular expression  `Regex_greece_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="ebaa0-411">Viene trovata una `Keywords_greece_eu_tax_file_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="ebaa0-411">A keyword from  `Keywords_greece_eu_tax_file_number` is found.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_greece_eu_tax_file_number" />
          <Match idRef="Keywords_greece_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="ebaa0-412">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="ebaa0-412">Keywords</span></span>

#### <a name="keywordsgreeceeutaxfilenumber"></a><span data-ttu-id="ebaa0-413">Keywords_greece_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="ebaa0-413">Keywords_greece_eu_tax_file_number</span></span>

<span data-ttu-id="ebaa0-414">AFM</span><span class="sxs-lookup"><span data-stu-id="ebaa0-414">afm</span></span>
  
<span data-ttu-id="ebaa0-415">tin
</span><span class="sxs-lookup"><span data-stu-id="ebaa0-415">tin</span></span>
  
<span data-ttu-id="ebaa0-416">ID IVA No.</span><span class="sxs-lookup"><span data-stu-id="ebaa0-416">tax id no.</span></span>
  
<span data-ttu-id="ebaa0-417">ID IVA No</span><span class="sxs-lookup"><span data-stu-id="ebaa0-417">tax id no</span></span>
  
<span data-ttu-id="ebaa0-418">codice di identificazione fiscale</span><span class="sxs-lookup"><span data-stu-id="ebaa0-418">tax identification number</span></span>
  
<span data-ttu-id="ebaa0-419">numero del registro di sistema fiscale</span><span class="sxs-lookup"><span data-stu-id="ebaa0-419">tax registry number</span></span>
  
<span data-ttu-id="ebaa0-420">Registro fiscale No.</span><span class="sxs-lookup"><span data-stu-id="ebaa0-420">tax registry no.</span></span>
  
<span data-ttu-id="ebaa0-421">AFM</span><span class="sxs-lookup"><span data-stu-id="ebaa0-421">afm#</span></span>
  
<span data-ttu-id="ebaa0-422">latta</span><span class="sxs-lookup"><span data-stu-id="ebaa0-422">tin#</span></span>
  
<span data-ttu-id="ebaa0-423">taxidno #</span><span class="sxs-lookup"><span data-stu-id="ebaa0-423">taxidno#</span></span>
  
<span data-ttu-id="ebaa0-424">taxregistryno #</span><span class="sxs-lookup"><span data-stu-id="ebaa0-424">taxregistryno#</span></span>
  
<span data-ttu-id="ebaa0-425">Αριθμός φορολογικού Μητρώου</span><span class="sxs-lookup"><span data-stu-id="ebaa0-425">αριθμός φορολογικού μητρώου</span></span>
  
<span data-ttu-id="ebaa0-426">aφμ</span><span class="sxs-lookup"><span data-stu-id="ebaa0-426">aφμ</span></span>
  
<span data-ttu-id="ebaa0-427">aφμ Αριθμός</span><span class="sxs-lookup"><span data-stu-id="ebaa0-427">aφμ αριθμός</span></span>
  
<span data-ttu-id="ebaa0-428">φορολογικού Μητρώου Νο.</span><span class="sxs-lookup"><span data-stu-id="ebaa0-428">φορολογικού μητρώου νο.</span></span>
  
<span data-ttu-id="ebaa0-429">τον αριθμό φορολογικού Μητρώου</span><span class="sxs-lookup"><span data-stu-id="ebaa0-429">τον αριθμό φορολογικού μητρώου</span></span>
  
## <a name="hungary"></a><span data-ttu-id="ebaa0-430">Ungheria</span><span class="sxs-lookup"><span data-stu-id="ebaa0-430">Hungary</span></span>

### <a name="format"></a><span data-ttu-id="ebaa0-431">Formato</span><span class="sxs-lookup"><span data-stu-id="ebaa0-431">Format</span></span>

<span data-ttu-id="ebaa0-432">Dieci cifre senza spazi o delimitatori</span><span class="sxs-lookup"><span data-stu-id="ebaa0-432">Ten digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="ebaa0-433">Modello</span><span class="sxs-lookup"><span data-stu-id="ebaa0-433">Pattern</span></span>

<span data-ttu-id="ebaa0-434">Dieci cifre:</span><span class="sxs-lookup"><span data-stu-id="ebaa0-434">Ten digits:</span></span>
  
-  <span data-ttu-id="ebaa0-435">Una cifra che deve essere "8"</span><span class="sxs-lookup"><span data-stu-id="ebaa0-435">One digit that must be "8"</span></span> 
    
- <span data-ttu-id="ebaa0-436">Cinque cifre che corrispondono al numero di giorni compresi tra la data 01/01/1867 e la data di nascita dell'individuo</span><span class="sxs-lookup"><span data-stu-id="ebaa0-436">Five digits that correspond to the number of days between the date 01/01/1867 and the date of the birth of the individual</span></span>
    
- <span data-ttu-id="ebaa0-437">Tre cifre che corrispondono al numero generato dalla possibilità di distinguere gli individui nati nello stesso giorno</span><span class="sxs-lookup"><span data-stu-id="ebaa0-437">Three digits that correspond to the number generated by chance to differentiate individuals born on the same day</span></span>
    
- <span data-ttu-id="ebaa0-438">Una cifra di controllo</span><span class="sxs-lookup"><span data-stu-id="ebaa0-438">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="ebaa0-439">Checksum</span><span class="sxs-lookup"><span data-stu-id="ebaa0-439">Checksum</span></span>

<span data-ttu-id="ebaa0-440">Sì</span><span class="sxs-lookup"><span data-stu-id="ebaa0-440">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="ebaa0-441">Definizione</span><span class="sxs-lookup"><span data-stu-id="ebaa0-441">Definition</span></span>

<span data-ttu-id="ebaa0-442">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="ebaa0-442">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="ebaa0-443">La funzione `Func_hungary_eu_tax_file_number` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="ebaa0-443">The function  `Func_hungary_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="ebaa0-444">Viene trovata una `Keywords_hungary_eu_tax_file_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="ebaa0-444">A keyword from  `Keywords_hungary_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="ebaa0-445">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="ebaa0-445">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="ebaa0-446">La funzione `Func_hungary_eu_tax_file_number` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="ebaa0-446">The function  `Func_hungary_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="ebaa0-447">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="ebaa0-447">Keywords</span></span>

#### <a name="keywordshungaryeutaxfilenumber"></a><span data-ttu-id="ebaa0-448">Keywords_hungary_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="ebaa0-448">Keywords_hungary_eu_tax_file_number</span></span>

<span data-ttu-id="ebaa0-449">numero di identificazione fiscale ungherese</span><span class="sxs-lookup"><span data-stu-id="ebaa0-449">hungarian tax identification number</span></span>
  
<span data-ttu-id="ebaa0-450">Tin ungherese</span><span class="sxs-lookup"><span data-stu-id="ebaa0-450">hungarian tin</span></span>
  
<span data-ttu-id="ebaa0-451">numero di ID fiscale</span><span class="sxs-lookup"><span data-stu-id="ebaa0-451">tax id number</span></span>
  
<span data-ttu-id="ebaa0-452">numero di partita IVA</span><span class="sxs-lookup"><span data-stu-id="ebaa0-452">vat number</span></span>
  
<span data-ttu-id="ebaa0-453">autorità tributaria No</span><span class="sxs-lookup"><span data-stu-id="ebaa0-453">tax authority no</span></span>
  
<span data-ttu-id="ebaa0-454">numero dell'identità fiscale dell'ID fiscale</span><span class="sxs-lookup"><span data-stu-id="ebaa0-454">tax id tax identity number</span></span>
  
<span data-ttu-id="ebaa0-455">taxidnumber #</span><span class="sxs-lookup"><span data-stu-id="ebaa0-455">taxidnumber#</span></span>
  
<span data-ttu-id="ebaa0-456">latta</span><span class="sxs-lookup"><span data-stu-id="ebaa0-456">tin#</span></span>
  
<span data-ttu-id="ebaa0-457">hungatiantin #</span><span class="sxs-lookup"><span data-stu-id="ebaa0-457">hungatiantin#</span></span>
  
<span data-ttu-id="ebaa0-458">identificazione fiscale No</span><span class="sxs-lookup"><span data-stu-id="ebaa0-458">tax identification no</span></span>
  
<span data-ttu-id="ebaa0-459">taxidno #</span><span class="sxs-lookup"><span data-stu-id="ebaa0-459">taxidno#</span></span>
  
<span data-ttu-id="ebaa0-460">adóazonosító szám</span><span class="sxs-lookup"><span data-stu-id="ebaa0-460">adóazonosító szám</span></span>
  
<span data-ttu-id="ebaa0-461">Adószám</span><span class="sxs-lookup"><span data-stu-id="ebaa0-461">adószám</span></span>
  
<span data-ttu-id="ebaa0-462">adóhatóság szám</span><span class="sxs-lookup"><span data-stu-id="ebaa0-462">adóhatóság szám</span></span>
  
## <a name="ireland"></a><span data-ttu-id="ebaa0-463">Irlanda</span><span class="sxs-lookup"><span data-stu-id="ebaa0-463">Ireland</span></span>

### <a name="format"></a><span data-ttu-id="ebaa0-464">Formato</span><span class="sxs-lookup"><span data-stu-id="ebaa0-464">Format</span></span>

<span data-ttu-id="ebaa0-465">Sette cifre seguite da una lettera senza spazi o delimitatori</span><span class="sxs-lookup"><span data-stu-id="ebaa0-465">Seven digits followed by a letter with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="ebaa0-466">Modello</span><span class="sxs-lookup"><span data-stu-id="ebaa0-466">Pattern</span></span>

<span data-ttu-id="ebaa0-467">Sette cifre seguite da una lettera:</span><span class="sxs-lookup"><span data-stu-id="ebaa0-467">Seven digits followed by a letter:</span></span>
  
-  <span data-ttu-id="ebaa0-468">Sette cifre</span><span class="sxs-lookup"><span data-stu-id="ebaa0-468">Seven digits</span></span> 
    
- <span data-ttu-id="ebaa0-469">Una lettera (senza distinzione tra maiuscole e minuscole)</span><span class="sxs-lookup"><span data-stu-id="ebaa0-469">One letter (not case-sensitive)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="ebaa0-470">Checksum</span><span class="sxs-lookup"><span data-stu-id="ebaa0-470">Checksum</span></span>

<span data-ttu-id="ebaa0-471">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="ebaa0-471">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="ebaa0-472">Definizione</span><span class="sxs-lookup"><span data-stu-id="ebaa0-472">Definition</span></span>

<span data-ttu-id="ebaa0-473">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="ebaa0-473">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="ebaa0-474">La funzione `Func_ireland_eu_tax_file_number` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="ebaa0-474">The function  `Func_ireland_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="ebaa0-475">Viene trovata una `Keywords_ireland_eu_tax_file_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="ebaa0-475">A keyword from  `Keywords_ireland_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="ebaa0-476">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="ebaa0-476">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="ebaa0-477">La funzione `Func_ireland_eu_tax_file_number` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="ebaa0-477">The function  `Func_ireland_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="ebaa0-478">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="ebaa0-478">Keywords</span></span>

#### <a name="keywordsirelandeutaxfilenumber"></a><span data-ttu-id="ebaa0-479">Keywords_ireland_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="ebaa0-479">Keywords_ireland_eu_tax_file_number</span></span>

<span data-ttu-id="ebaa0-480">servizio pubblico no</span><span class="sxs-lookup"><span data-stu-id="ebaa0-480">public service no</span></span>
  
<span data-ttu-id="ebaa0-481">servizio pubblico personale No</span><span class="sxs-lookup"><span data-stu-id="ebaa0-481">personal public service no</span></span>
  
<span data-ttu-id="ebaa0-482">PPS No</span><span class="sxs-lookup"><span data-stu-id="ebaa0-482">pps no</span></span>
  
<span data-ttu-id="ebaa0-483">servizio personale No</span><span class="sxs-lookup"><span data-stu-id="ebaa0-483">personal service no</span></span>
  
<span data-ttu-id="ebaa0-484">servizio PPS No</span><span class="sxs-lookup"><span data-stu-id="ebaa0-484">pps service no</span></span>
  
<span data-ttu-id="ebaa0-485">ppsno #</span><span class="sxs-lookup"><span data-stu-id="ebaa0-485">ppsno#</span></span>
  
<span data-ttu-id="ebaa0-486">Irish PPS No</span><span class="sxs-lookup"><span data-stu-id="ebaa0-486">irish pps no</span></span>
  
<span data-ttu-id="ebaa0-487">publicserviceno #</span><span class="sxs-lookup"><span data-stu-id="ebaa0-487">publicserviceno#</span></span>
  
<span data-ttu-id="ebaa0-488">numero di servizio pubblico personale</span><span class="sxs-lookup"><span data-stu-id="ebaa0-488">personal public service number</span></span>
  
<span data-ttu-id="ebaa0-489">uimhir phearsanta Seirbhíse poiblí</span><span class="sxs-lookup"><span data-stu-id="ebaa0-489">uimhir phearsanta seirbhíse poiblí</span></span>
  
<span data-ttu-id="ebaa0-490">PPS uimh</span><span class="sxs-lookup"><span data-stu-id="ebaa0-490">pps uimh</span></span>
  
<span data-ttu-id="ebaa0-491">uimhir aitheantais phearsanta</span><span class="sxs-lookup"><span data-stu-id="ebaa0-491">uimhir aitheantais phearsanta</span></span>
  
## <a name="italy"></a><span data-ttu-id="ebaa0-492">Italia</span><span class="sxs-lookup"><span data-stu-id="ebaa0-492">Italy</span></span>

### <a name="format"></a><span data-ttu-id="ebaa0-493">Formato</span><span class="sxs-lookup"><span data-stu-id="ebaa0-493">Format</span></span>

<span data-ttu-id="ebaa0-494">16 lettere e cifre nel modello specificato</span><span class="sxs-lookup"><span data-stu-id="ebaa0-494">16 letters and digits in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="ebaa0-495">Modello</span><span class="sxs-lookup"><span data-stu-id="ebaa0-495">Pattern</span></span>

<span data-ttu-id="ebaa0-496">16 lettere e cifre:</span><span class="sxs-lookup"><span data-stu-id="ebaa0-496">16 letters and digits:</span></span>
  
-  <span data-ttu-id="ebaa0-497">Tre lettere che corrispondono alle prime tre consonanti del nome di famiglia</span><span class="sxs-lookup"><span data-stu-id="ebaa0-497">Three letters that correspond to the first three consonants in the family name</span></span> 
    
- <span data-ttu-id="ebaa0-498">Tre lettere che corrispondono alla prima, terza e quarta consonante del primo nome</span><span class="sxs-lookup"><span data-stu-id="ebaa0-498">Three letters that correspond to the first, third, and fourth consonants in the first name</span></span>
    
- <span data-ttu-id="ebaa0-499">Due cifre che corrispondono alle ultime cifre dell'anno di nascita</span><span class="sxs-lookup"><span data-stu-id="ebaa0-499">Two digits that correspond to the last digits of the birth year</span></span>
    
- <span data-ttu-id="ebaa0-500">Una cifra corrispondente al mese di nascita: le lettere vengono utilizzate in ordine alfabetico, ma vengono utilizzate solo le lettere da a a E, H, L, M, P, R e T (pertanto, gennaio è A e ottobre è R)</span><span class="sxs-lookup"><span data-stu-id="ebaa0-500">One digit that corresponds to the month of birth—letters are used in alphabetical order, but only the letters A to E, H, L, M, P, R to T are used (thus, January is A and October is R)</span></span>
    
- <span data-ttu-id="ebaa0-501">Due cifre che corrispondono al giorno del mese di nascita in cui 40 viene aggiunto al giorno di nascita per le femmine per differenziare dai maschi</span><span class="sxs-lookup"><span data-stu-id="ebaa0-501">Two digits that correspond to the day of the month of birth where 40 is added to the day of birth for females to differentiate from males</span></span>
    
- <span data-ttu-id="ebaa0-502">Quattro cifre che corrispondono a un codice di area specifico per il comune in cui è nata la persona: vengono utilizzati codici a livello nazionale per i paesi esteri</span><span class="sxs-lookup"><span data-stu-id="ebaa0-502">Four digits that correspond to an area code specific to the municipality where the person was born—country-wide codes are used for foreign countries</span></span>
    
- <span data-ttu-id="ebaa0-503">Una cifra di controllo</span><span class="sxs-lookup"><span data-stu-id="ebaa0-503">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="ebaa0-504">Checksum</span><span class="sxs-lookup"><span data-stu-id="ebaa0-504">Checksum</span></span>

<span data-ttu-id="ebaa0-505">Sì</span><span class="sxs-lookup"><span data-stu-id="ebaa0-505">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="ebaa0-506">Definizione</span><span class="sxs-lookup"><span data-stu-id="ebaa0-506">Definition</span></span>

<span data-ttu-id="ebaa0-507">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="ebaa0-507">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="ebaa0-508">La funzione `Func_italy_eu_tax_file_number` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="ebaa0-508">The function  `Func_italy_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="ebaa0-509">Viene trovata una `Keywords_italy_eu_tax_file_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="ebaa0-509">A keyword from  `Keywords_italy_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="ebaa0-510">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="ebaa0-510">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="ebaa0-511">La funzione `Func_italy_eu_tax_file_number` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="ebaa0-511">The function  `Func_italy_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="ebaa0-512">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="ebaa0-512">Keywords</span></span>

#### <a name="keywordsitalyeutaxfilenumber"></a><span data-ttu-id="ebaa0-513">Keywords_italy_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="ebaa0-513">Keywords_italy_eu_tax_file_number</span></span>

<span data-ttu-id="ebaa0-514">codice fiscale</span><span class="sxs-lookup"><span data-stu-id="ebaa0-514">tax number</span></span>
  
<span data-ttu-id="ebaa0-515">tassa no.</span><span class="sxs-lookup"><span data-stu-id="ebaa0-515">tax no.</span></span>
  
<span data-ttu-id="ebaa0-516">taxno #</span><span class="sxs-lookup"><span data-stu-id="ebaa0-516">taxno#</span></span>
  
<span data-ttu-id="ebaa0-517">taxnumber #</span><span class="sxs-lookup"><span data-stu-id="ebaa0-517">taxnumber#</span></span>
  
<span data-ttu-id="ebaa0-518">taxnumber</span><span class="sxs-lookup"><span data-stu-id="ebaa0-518">taxnumber</span></span>
  
<span data-ttu-id="ebaa0-519">tax id
</span><span class="sxs-lookup"><span data-stu-id="ebaa0-519">tax id</span></span>
  
<span data-ttu-id="ebaa0-520">taxid #</span><span class="sxs-lookup"><span data-stu-id="ebaa0-520">taxid#</span></span>
  
<span data-ttu-id="ebaa0-521">codice fiscale</span><span class="sxs-lookup"><span data-stu-id="ebaa0-521">fiscal code</span></span>
  
<span data-ttu-id="ebaa0-522">codice fiscale</span><span class="sxs-lookup"><span data-stu-id="ebaa0-522">codice fiscale</span></span>
  
## <a name="latvia"></a><span data-ttu-id="ebaa0-523">Lettonia</span><span class="sxs-lookup"><span data-stu-id="ebaa0-523">Latvia</span></span>

### <a name="format"></a><span data-ttu-id="ebaa0-524">Formato</span><span class="sxs-lookup"><span data-stu-id="ebaa0-524">Format</span></span>

<span data-ttu-id="ebaa0-525">11 cifre senza spazi o delimitatori</span><span class="sxs-lookup"><span data-stu-id="ebaa0-525">11 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="ebaa0-526">Modello</span><span class="sxs-lookup"><span data-stu-id="ebaa0-526">Pattern</span></span>

<span data-ttu-id="ebaa0-527">11 cifre nel modello specificato</span><span class="sxs-lookup"><span data-stu-id="ebaa0-527">11 digits in the specified pattern</span></span>
  
-  <span data-ttu-id="ebaa0-528">Sei cifre che corrispondono alla data di nascita (GGMMAA)</span><span class="sxs-lookup"><span data-stu-id="ebaa0-528">Six digits that correspond to the date of birth (DDMMYY)</span></span> 
    
- <span data-ttu-id="ebaa0-529">Una cifra che corrisponde al secolo di nascita dove "0" corrisponde al XIX secolo, "1" corrisponde al 20 ° secolo e "2" corrisponde al XXI secolo</span><span class="sxs-lookup"><span data-stu-id="ebaa0-529">One digit that corresponds to the century of birth where "0" corresponds to 19th century, "1" corresponds to 20th century, and "2"corresponds to 21st century</span></span>
    
- <span data-ttu-id="ebaa0-530">Quattro cifre</span><span class="sxs-lookup"><span data-stu-id="ebaa0-530">Four digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="ebaa0-531">Checksum</span><span class="sxs-lookup"><span data-stu-id="ebaa0-531">Checksum</span></span>

<span data-ttu-id="ebaa0-532">Sì</span><span class="sxs-lookup"><span data-stu-id="ebaa0-532">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="ebaa0-533">Definizione</span><span class="sxs-lookup"><span data-stu-id="ebaa0-533">Definition</span></span>

<span data-ttu-id="ebaa0-534">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="ebaa0-534">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="ebaa0-535">La funzione `Func_latvia_eu_tax_file_number` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="ebaa0-535">The function  `Func_latvia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="ebaa0-536">Viene trovata una `Keywords_latvia_eu_tax_file_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="ebaa0-536">A keyword from  `Keywords_latvia_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="ebaa0-537">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="ebaa0-537">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="ebaa0-538">La funzione `Func_latvia_eu_tax_file_number` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="ebaa0-538">The function  `Func_latvia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="ebaa0-539">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="ebaa0-539">Keywords</span></span>

#### <a name="keywordslatviaeutaxfilenumber"></a><span data-ttu-id="ebaa0-540">Keywords_latvia_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="ebaa0-540">Keywords_latvia_eu_tax_file_number</span></span>

<span data-ttu-id="ebaa0-541">codice fiscale</span><span class="sxs-lookup"><span data-stu-id="ebaa0-541">tax number</span></span>
  
<span data-ttu-id="ebaa0-542">tassa no.</span><span class="sxs-lookup"><span data-stu-id="ebaa0-542">tax no.</span></span>
  
<span data-ttu-id="ebaa0-543">taxno #</span><span class="sxs-lookup"><span data-stu-id="ebaa0-543">taxno#</span></span>
  
<span data-ttu-id="ebaa0-544">taxnumber #</span><span class="sxs-lookup"><span data-stu-id="ebaa0-544">taxnumber#</span></span>
  
<span data-ttu-id="ebaa0-545">taxnumber</span><span class="sxs-lookup"><span data-stu-id="ebaa0-545">taxnumber</span></span>
  
<span data-ttu-id="ebaa0-546">tax id
</span><span class="sxs-lookup"><span data-stu-id="ebaa0-546">tax id</span></span>
  
<span data-ttu-id="ebaa0-547">taxid #</span><span class="sxs-lookup"><span data-stu-id="ebaa0-547">taxid#</span></span>
  
<span data-ttu-id="ebaa0-548">codice di identificazione fiscale</span><span class="sxs-lookup"><span data-stu-id="ebaa0-548">tax identification number</span></span>
  
<span data-ttu-id="ebaa0-549">codice fiscale n.</span><span class="sxs-lookup"><span data-stu-id="ebaa0-549">tax identification no.</span></span>
  
<span data-ttu-id="ebaa0-550">nodokļa numurs</span><span class="sxs-lookup"><span data-stu-id="ebaa0-550">nodokļa numurs</span></span>
  
<span data-ttu-id="ebaa0-551">nodokļu identifikācijas numurs</span><span class="sxs-lookup"><span data-stu-id="ebaa0-551">nodokļu identifikācijas numurs</span></span>
  
<span data-ttu-id="ebaa0-552">nodokļu identifikācija numurs</span><span class="sxs-lookup"><span data-stu-id="ebaa0-552">nodokļu identifikācija numurs</span></span>
  
## <a name="lithuania"></a><span data-ttu-id="ebaa0-553">Lituania</span><span class="sxs-lookup"><span data-stu-id="ebaa0-553">Lithuania</span></span>

### <a name="format"></a><span data-ttu-id="ebaa0-554">Formato</span><span class="sxs-lookup"><span data-stu-id="ebaa0-554">Format</span></span>

<span data-ttu-id="ebaa0-555">11 cifre senza spazi o delimitatori</span><span class="sxs-lookup"><span data-stu-id="ebaa0-555">11 digits without spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="ebaa0-556">Modello</span><span class="sxs-lookup"><span data-stu-id="ebaa0-556">Pattern</span></span>

<span data-ttu-id="ebaa0-557">11 cifre</span><span class="sxs-lookup"><span data-stu-id="ebaa0-557">11 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="ebaa0-558">Checksum</span><span class="sxs-lookup"><span data-stu-id="ebaa0-558">Checksum</span></span>

<span data-ttu-id="ebaa0-559">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="ebaa0-559">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="ebaa0-560">Definizione</span><span class="sxs-lookup"><span data-stu-id="ebaa0-560">Definition</span></span>

<span data-ttu-id="ebaa0-561">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="ebaa0-561">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="ebaa0-562">La funzione `Func_lithuania_eu_tax_file_number` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="ebaa0-562">The function  `Func_lithuania_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="ebaa0-563">Viene trovata una `Keywords_lithuania_eu_tax_file_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="ebaa0-563">A keyword from  `Keywords_lithuania_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="ebaa0-564">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="ebaa0-564">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="ebaa0-565">La funzione `Func_lithuania_eu_tax_file_number` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="ebaa0-565">The function  `Func_lithuania_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="ebaa0-566">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="ebaa0-566">Keywords</span></span>

#### <a name="keywordslithuaniaeutaxfilenumber"></a><span data-ttu-id="ebaa0-567">Keywords_lithuania_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="ebaa0-567">Keywords_lithuania_eu_tax_file_number</span></span>

<span data-ttu-id="ebaa0-568">codice fiscale</span><span class="sxs-lookup"><span data-stu-id="ebaa0-568">tax number</span></span>
  
<span data-ttu-id="ebaa0-569">tassa no.</span><span class="sxs-lookup"><span data-stu-id="ebaa0-569">tax no.</span></span>
  
<span data-ttu-id="ebaa0-570">tax no #</span><span class="sxs-lookup"><span data-stu-id="ebaa0-570">tax no#</span></span>
  
<span data-ttu-id="ebaa0-571">taxnumber #</span><span class="sxs-lookup"><span data-stu-id="ebaa0-571">taxnumber#</span></span>
  
<span data-ttu-id="ebaa0-572">taxnumber</span><span class="sxs-lookup"><span data-stu-id="ebaa0-572">taxnumber</span></span>
  
<span data-ttu-id="ebaa0-573">tax id
</span><span class="sxs-lookup"><span data-stu-id="ebaa0-573">tax id</span></span>
  
<span data-ttu-id="ebaa0-574">taxid #</span><span class="sxs-lookup"><span data-stu-id="ebaa0-574">taxid#</span></span>
  
<span data-ttu-id="ebaa0-575">codice di identificazione fiscale</span><span class="sxs-lookup"><span data-stu-id="ebaa0-575">tax identification number</span></span>
  
<span data-ttu-id="ebaa0-576">codice fiscale n.</span><span class="sxs-lookup"><span data-stu-id="ebaa0-576">tax identification no.</span></span>
  
<span data-ttu-id="ebaa0-577">ID mokesčių</span><span class="sxs-lookup"><span data-stu-id="ebaa0-577">mokesčių id</span></span>
  
<span data-ttu-id="ebaa0-578">numeri mokesčių</span><span class="sxs-lookup"><span data-stu-id="ebaa0-578">mokesčių numeris</span></span>
  
<span data-ttu-id="ebaa0-579">mokesčių identifikavimas numeris</span><span class="sxs-lookup"><span data-stu-id="ebaa0-579">mokesčių identifikavimas numeris</span></span>
  
## <a name="luxemburg"></a><span data-ttu-id="ebaa0-580">Lussemburgo</span><span class="sxs-lookup"><span data-stu-id="ebaa0-580">Luxemburg</span></span>

### <a name="format"></a><span data-ttu-id="ebaa0-581">Formato</span><span class="sxs-lookup"><span data-stu-id="ebaa0-581">Format</span></span>

<span data-ttu-id="ebaa0-582">13 cifre senza spazi o delimitatori</span><span class="sxs-lookup"><span data-stu-id="ebaa0-582">13 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="ebaa0-583">Modello</span><span class="sxs-lookup"><span data-stu-id="ebaa0-583">Pattern</span></span>

<span data-ttu-id="ebaa0-584">13 cifre:</span><span class="sxs-lookup"><span data-stu-id="ebaa0-584">13 digits:</span></span>
  
-  <span data-ttu-id="ebaa0-585">11 cifre</span><span class="sxs-lookup"><span data-stu-id="ebaa0-585">11 digits</span></span> 
    
- <span data-ttu-id="ebaa0-586">Due cifre di controllo</span><span class="sxs-lookup"><span data-stu-id="ebaa0-586">Two check digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="ebaa0-587">Checksum</span><span class="sxs-lookup"><span data-stu-id="ebaa0-587">Checksum</span></span>

<span data-ttu-id="ebaa0-588">Sì</span><span class="sxs-lookup"><span data-stu-id="ebaa0-588">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="ebaa0-589">Definizione</span><span class="sxs-lookup"><span data-stu-id="ebaa0-589">Definition</span></span>

<span data-ttu-id="ebaa0-590">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="ebaa0-590">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="ebaa0-591">La funzione `Func_luxemburg_eu_tax_file_number` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="ebaa0-591">The function  `Func_luxemburg_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="ebaa0-592">Viene trovata una `Keywords_luxemburg_eu_tax_file_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="ebaa0-592">A keyword from  `Keywords_luxemburg_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="ebaa0-593">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="ebaa0-593">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="ebaa0-594">La funzione `Func_luxemburg_eu_tax_file_number` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="ebaa0-594">The function  `Func_luxemburg_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="ebaa0-595">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="ebaa0-595">Keywords</span></span>

#### <a name="keywordsluxemburgeutaxfilenumber"></a><span data-ttu-id="ebaa0-596">Keywords_luxemburg_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="ebaa0-596">Keywords_luxemburg_eu_tax_file_number</span></span>

<span data-ttu-id="ebaa0-597">codice fiscale</span><span class="sxs-lookup"><span data-stu-id="ebaa0-597">tax number</span></span>
  
<span data-ttu-id="ebaa0-598">tassa no.</span><span class="sxs-lookup"><span data-stu-id="ebaa0-598">tax no.</span></span>
  
<span data-ttu-id="ebaa0-599">taxno #</span><span class="sxs-lookup"><span data-stu-id="ebaa0-599">taxno#</span></span>
  
<span data-ttu-id="ebaa0-600">taxnumber #</span><span class="sxs-lookup"><span data-stu-id="ebaa0-600">taxnumber#</span></span>
  
<span data-ttu-id="ebaa0-601">taxnumber</span><span class="sxs-lookup"><span data-stu-id="ebaa0-601">taxnumber</span></span>
  
<span data-ttu-id="ebaa0-602">tax id
</span><span class="sxs-lookup"><span data-stu-id="ebaa0-602">tax id</span></span>
  
<span data-ttu-id="ebaa0-603">taxid #</span><span class="sxs-lookup"><span data-stu-id="ebaa0-603">taxid#</span></span>
  
<span data-ttu-id="ebaa0-604">codice di identificazione fiscale</span><span class="sxs-lookup"><span data-stu-id="ebaa0-604">tax identification number</span></span>
  
<span data-ttu-id="ebaa0-605">codice fiscale n.</span><span class="sxs-lookup"><span data-stu-id="ebaa0-605">tax identification no.</span></span>
  
<span data-ttu-id="ebaa0-606">Steuernummer</span><span class="sxs-lookup"><span data-stu-id="ebaa0-606">steuernummer</span></span>
  
<span data-ttu-id="ebaa0-607">ID Steuer</span><span class="sxs-lookup"><span data-stu-id="ebaa0-607">steuer id</span></span>
  
<span data-ttu-id="ebaa0-608">steueridentifikationsnummer</span><span class="sxs-lookup"><span data-stu-id="ebaa0-608">steueridentifikationsnummer</span></span>
  
## <a name="malta"></a><span data-ttu-id="ebaa0-609">Malta</span><span class="sxs-lookup"><span data-stu-id="ebaa0-609">Malta</span></span>

### <a name="format"></a><span data-ttu-id="ebaa0-610">Formato</span><span class="sxs-lookup"><span data-stu-id="ebaa0-610">Format</span></span>

<span data-ttu-id="ebaa0-611">Per cittadini malTesi: 7 cifre e una lettera nel modello specificato</span><span class="sxs-lookup"><span data-stu-id="ebaa0-611">For Maltese nationals: 7 digits and one letter in the specified pattern</span></span>
  
<span data-ttu-id="ebaa0-612">Nazionali non malTesi e soggetti maltesi: 9 cifre</span><span class="sxs-lookup"><span data-stu-id="ebaa0-612">Non-Maltese nationals and Maltese entities: 9 digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="ebaa0-613">Modello</span><span class="sxs-lookup"><span data-stu-id="ebaa0-613">Pattern</span></span>

<span data-ttu-id="ebaa0-614">Cittadini malTesi: 7 cifre e una lettera</span><span class="sxs-lookup"><span data-stu-id="ebaa0-614">Maltese nationals: 7 digits and one letter</span></span>
  
-  <span data-ttu-id="ebaa0-615">Sette cifre</span><span class="sxs-lookup"><span data-stu-id="ebaa0-615">Seven digits</span></span> 
    
- <span data-ttu-id="ebaa0-616">Una lettera (senza distinzione tra maiuscole e minuscole)</span><span class="sxs-lookup"><span data-stu-id="ebaa0-616">One letter (not case-sensitive)</span></span>
    
<span data-ttu-id="ebaa0-617">Nazionali non malTesi e soggetti maltesi: 9 cifre</span><span class="sxs-lookup"><span data-stu-id="ebaa0-617">Non-Maltese nationals and Maltese entities: 9 digits</span></span>
  
-  <span data-ttu-id="ebaa0-618">9 cifre</span><span class="sxs-lookup"><span data-stu-id="ebaa0-618">Nine digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="ebaa0-619">Checksum</span><span class="sxs-lookup"><span data-stu-id="ebaa0-619">Checksum</span></span>

<span data-ttu-id="ebaa0-620">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="ebaa0-620">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="ebaa0-621">Definizione</span><span class="sxs-lookup"><span data-stu-id="ebaa0-621">Definition</span></span>

<span data-ttu-id="ebaa0-622">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="ebaa0-622">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="ebaa0-623">La funzione `Func_malta_eu_tax_file_number` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="ebaa0-623">The function  `Func_malta_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="ebaa0-624">Viene trovata una `Keywords_malta_eu_tax_file_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="ebaa0-624">A keyword from  `Keywords_malta_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="ebaa0-625">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 65%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="ebaa0-625">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="ebaa0-626">La funzione `Func_malta_eu_tax_file_number` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="ebaa0-626">The function  `Func_malta_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="ebaa0-627">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="ebaa0-627">Keywords</span></span>

#### <a name="keywordsmaltaeutaxfilenumber"></a><span data-ttu-id="ebaa0-628">Keywords_malta_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="ebaa0-628">Keywords_malta_eu_tax_file_number</span></span>

<span data-ttu-id="ebaa0-629">codice fiscale</span><span class="sxs-lookup"><span data-stu-id="ebaa0-629">tax number</span></span>
  
<span data-ttu-id="ebaa0-630">tassa no.</span><span class="sxs-lookup"><span data-stu-id="ebaa0-630">tax no.</span></span>
  
<span data-ttu-id="ebaa0-631">taxno #</span><span class="sxs-lookup"><span data-stu-id="ebaa0-631">taxno#</span></span>
  
<span data-ttu-id="ebaa0-632">taxnumber #</span><span class="sxs-lookup"><span data-stu-id="ebaa0-632">taxnumber#</span></span>
  
<span data-ttu-id="ebaa0-633">taxnumber</span><span class="sxs-lookup"><span data-stu-id="ebaa0-633">taxnumber</span></span>
  
<span data-ttu-id="ebaa0-634">tax id
</span><span class="sxs-lookup"><span data-stu-id="ebaa0-634">tax id</span></span>
  
<span data-ttu-id="ebaa0-635">taxid #</span><span class="sxs-lookup"><span data-stu-id="ebaa0-635">taxid#</span></span>
  
<span data-ttu-id="ebaa0-636">codice di identificazione fiscale</span><span class="sxs-lookup"><span data-stu-id="ebaa0-636">tax identification number</span></span>
  
<span data-ttu-id="ebaa0-637">codice fiscale n.</span><span class="sxs-lookup"><span data-stu-id="ebaa0-637">tax identification no.</span></span>
  
<span data-ttu-id="ebaa0-638">numru Tat-Taxxa</span><span class="sxs-lookup"><span data-stu-id="ebaa0-638">numru tat-taxxa</span></span>
  
<span data-ttu-id="ebaa0-639">ID Tat-Taxxa</span><span class="sxs-lookup"><span data-stu-id="ebaa0-639">id tat-taxxa</span></span>
  
<span data-ttu-id="ebaa0-640">numru ta ' identifikazzjoni Tat-Taxxa</span><span class="sxs-lookup"><span data-stu-id="ebaa0-640">numru ta 'identifikazzjoni tat-taxxa</span></span>
  
## <a name="netherlands"></a><span data-ttu-id="ebaa0-641">Paesi Bassi</span><span class="sxs-lookup"><span data-stu-id="ebaa0-641">Netherlands</span></span>

### <a name="format"></a><span data-ttu-id="ebaa0-642">Formato</span><span class="sxs-lookup"><span data-stu-id="ebaa0-642">Format</span></span>

<span data-ttu-id="ebaa0-643">Nove cifre senza spazi o delimitatori</span><span class="sxs-lookup"><span data-stu-id="ebaa0-643">Nine digits without spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="ebaa0-644">Modello</span><span class="sxs-lookup"><span data-stu-id="ebaa0-644">Pattern</span></span>

<span data-ttu-id="ebaa0-645">9 cifre</span><span class="sxs-lookup"><span data-stu-id="ebaa0-645">Nine digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="ebaa0-646">Checksum</span><span class="sxs-lookup"><span data-stu-id="ebaa0-646">Checksum</span></span>

<span data-ttu-id="ebaa0-647">Sì</span><span class="sxs-lookup"><span data-stu-id="ebaa0-647">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="ebaa0-648">Definizione</span><span class="sxs-lookup"><span data-stu-id="ebaa0-648">Definition</span></span>

<span data-ttu-id="ebaa0-649">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="ebaa0-649">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="ebaa0-650">La funzione `Func_netherlands_eu_tax_file_number` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="ebaa0-650">The function  `Func_netherlands_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="ebaa0-651">Viene trovata una `Keywords_netherlands_eu_tax_file_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="ebaa0-651">A keyword from  `Keywords_netherlands_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="ebaa0-652">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="ebaa0-652">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="ebaa0-653">La funzione `Func_netherlands_eu_tax_file_number` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="ebaa0-653">The function  `Func_netherlands_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="ebaa0-654">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="ebaa0-654">Keywords</span></span>

#### <a name="keywordsnetherlandseutaxfilenumber"></a><span data-ttu-id="ebaa0-655">Keywords_netherlands_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="ebaa0-655">Keywords_netherlands_eu_tax_file_number</span></span>

<span data-ttu-id="ebaa0-656">numero di identificazione fiscale per i Paesi Bassi</span><span class="sxs-lookup"><span data-stu-id="ebaa0-656">netherlands tax identification number</span></span>
  
<span data-ttu-id="ebaa0-657">identificazione fiscale per i Paesi Bassi</span><span class="sxs-lookup"><span data-stu-id="ebaa0-657">netherlands tax identification</span></span>
  
<span data-ttu-id="ebaa0-658">numero di identificazione fiscale per i Paesi Bassi</span><span class="sxs-lookup"><span data-stu-id="ebaa0-658">netherland's tax identification number</span></span>
  
<span data-ttu-id="ebaa0-659">identificazione fiscale per i Paesi Bassi</span><span class="sxs-lookup"><span data-stu-id="ebaa0-659">netherland's tax identification</span></span>
  
<span data-ttu-id="ebaa0-660">codice di identificazione fiscale</span><span class="sxs-lookup"><span data-stu-id="ebaa0-660">tax identification number</span></span>
  
<span data-ttu-id="ebaa0-661">ID delle tasse olandesi</span><span class="sxs-lookup"><span data-stu-id="ebaa0-661">dutch tax id</span></span>
  
<span data-ttu-id="ebaa0-662">numero di identificazione fiscale olandese</span><span class="sxs-lookup"><span data-stu-id="ebaa0-662">dutch tax identification number</span></span>
  
<span data-ttu-id="ebaa0-663">tax id
</span><span class="sxs-lookup"><span data-stu-id="ebaa0-663">tax id</span></span>
  
<span data-ttu-id="ebaa0-664">ID fiscale #</span><span class="sxs-lookup"><span data-stu-id="ebaa0-664">tax id#</span></span>
  
<span data-ttu-id="ebaa0-665">codice fiscale</span><span class="sxs-lookup"><span data-stu-id="ebaa0-665">tax number</span></span>
  
<span data-ttu-id="ebaa0-666">tax no #</span><span class="sxs-lookup"><span data-stu-id="ebaa0-666">tax no#</span></span>
  
<span data-ttu-id="ebaa0-667">imposte</span><span class="sxs-lookup"><span data-stu-id="ebaa0-667">tax#</span></span>
  
<span data-ttu-id="ebaa0-668">tin
</span><span class="sxs-lookup"><span data-stu-id="ebaa0-668">tin</span></span>
  
<span data-ttu-id="ebaa0-669">latta</span><span class="sxs-lookup"><span data-stu-id="ebaa0-669">tin#</span></span>
  
<span data-ttu-id="ebaa0-670">Tin olandesi</span><span class="sxs-lookup"><span data-stu-id="ebaa0-670">netherlands tin</span></span>
  
<span data-ttu-id="ebaa0-671">stagno degli olandesi</span><span class="sxs-lookup"><span data-stu-id="ebaa0-671">netherland's tin</span></span>
  
<span data-ttu-id="ebaa0-672">Nederlands identificatienummer di recente</span><span class="sxs-lookup"><span data-stu-id="ebaa0-672">nederlands belasting identificatienummer</span></span>
  
<span data-ttu-id="ebaa0-673">identificatienummer van delasting</span><span class="sxs-lookup"><span data-stu-id="ebaa0-673">identificatienummer van belasting</span></span>
  
<span data-ttu-id="ebaa0-674">identificatienummer che dura</span><span class="sxs-lookup"><span data-stu-id="ebaa0-674">identificatienummer belasting</span></span>
  
<span data-ttu-id="ebaa0-675">Nederlands identificatie di recente</span><span class="sxs-lookup"><span data-stu-id="ebaa0-675">nederlands belasting identificatie</span></span>
  
<span data-ttu-id="ebaa0-676">l'ID di Nummer del Nederlands</span><span class="sxs-lookup"><span data-stu-id="ebaa0-676">nederlands belasting id nummer</span></span>
  
<span data-ttu-id="ebaa0-677">Nederlands belastingnummer</span><span class="sxs-lookup"><span data-stu-id="ebaa0-677">nederlands belastingnummer</span></span>
  
<span data-ttu-id="ebaa0-678">BTW nummer</span><span class="sxs-lookup"><span data-stu-id="ebaa0-678">btw nummer</span></span>
  
<span data-ttu-id="ebaa0-679">Nederlandse che durerà identificatie</span><span class="sxs-lookup"><span data-stu-id="ebaa0-679">nederlandse belasting identificatie</span></span>
  
## <a name="poland"></a><span data-ttu-id="ebaa0-680">Polonia</span><span class="sxs-lookup"><span data-stu-id="ebaa0-680">Poland</span></span>

### <a name="format"></a><span data-ttu-id="ebaa0-681">Formato</span><span class="sxs-lookup"><span data-stu-id="ebaa0-681">Format</span></span>

<span data-ttu-id="ebaa0-682">Undici cifre senza spazi o delimitatori</span><span class="sxs-lookup"><span data-stu-id="ebaa0-682">Eleven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="ebaa0-683">Modello</span><span class="sxs-lookup"><span data-stu-id="ebaa0-683">Pattern</span></span>

<span data-ttu-id="ebaa0-684">Undici cifre</span><span class="sxs-lookup"><span data-stu-id="ebaa0-684">Eleven digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="ebaa0-685">Checksum</span><span class="sxs-lookup"><span data-stu-id="ebaa0-685">Checksum</span></span>

<span data-ttu-id="ebaa0-686">Sì</span><span class="sxs-lookup"><span data-stu-id="ebaa0-686">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="ebaa0-687">Definizione</span><span class="sxs-lookup"><span data-stu-id="ebaa0-687">Definition</span></span>

<span data-ttu-id="ebaa0-688">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="ebaa0-688">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="ebaa0-689">La funzione `Func_poland_eu_tax_file_number` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="ebaa0-689">The function  `Func_poland_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="ebaa0-690">Viene trovata una `Keywords_poland_eu_tax_file_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="ebaa0-690">A keyword from  `Keywords_poland_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="ebaa0-691">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="ebaa0-691">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="ebaa0-692">La funzione `Func_poland_eu_tax_file_number` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="ebaa0-692">The function  `Func_poland_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="ebaa0-693">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="ebaa0-693">Keywords</span></span>

#### <a name="keywordspolandeutaxfilenumber"></a><span data-ttu-id="ebaa0-694">Keywords_poland_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="ebaa0-694">Keywords_poland_eu_tax_file_number</span></span>

<span data-ttu-id="ebaa0-695">codice fiscale</span><span class="sxs-lookup"><span data-stu-id="ebaa0-695">tax number</span></span>
  
<span data-ttu-id="ebaa0-696">tassa no.</span><span class="sxs-lookup"><span data-stu-id="ebaa0-696">tax no.</span></span>
  
<span data-ttu-id="ebaa0-697">taxno #</span><span class="sxs-lookup"><span data-stu-id="ebaa0-697">taxno#</span></span>
  
<span data-ttu-id="ebaa0-698">taxnumber #</span><span class="sxs-lookup"><span data-stu-id="ebaa0-698">taxnumber#</span></span>
  
<span data-ttu-id="ebaa0-699">taxnumber</span><span class="sxs-lookup"><span data-stu-id="ebaa0-699">taxnumber</span></span>
  
<span data-ttu-id="ebaa0-700">NIP</span><span class="sxs-lookup"><span data-stu-id="ebaa0-700">nip</span></span>
  
<span data-ttu-id="ebaa0-701">NIP</span><span class="sxs-lookup"><span data-stu-id="ebaa0-701">nip#</span></span>
  
<span data-ttu-id="ebaa0-702">tax id
</span><span class="sxs-lookup"><span data-stu-id="ebaa0-702">tax id</span></span>
  
<span data-ttu-id="ebaa0-703">ID fiscale #</span><span class="sxs-lookup"><span data-stu-id="ebaa0-703">tax id#</span></span>
  
<span data-ttu-id="ebaa0-704">ID NIP</span><span class="sxs-lookup"><span data-stu-id="ebaa0-704">nip id</span></span>
  
<span data-ttu-id="ebaa0-705">ID NIP #</span><span class="sxs-lookup"><span data-stu-id="ebaa0-705">nip id#</span></span>
  
<span data-ttu-id="ebaa0-706">codice di identificazione fiscale</span><span class="sxs-lookup"><span data-stu-id="ebaa0-706">tax identification number</span></span>
  
<span data-ttu-id="ebaa0-707">codice fiscale n.</span><span class="sxs-lookup"><span data-stu-id="ebaa0-707">tax identification no.</span></span>
  
<span data-ttu-id="ebaa0-708">numero di partita IVA</span><span class="sxs-lookup"><span data-stu-id="ebaa0-708">vat number</span></span>
  
<span data-ttu-id="ebaa0-709">IVA No.</span><span class="sxs-lookup"><span data-stu-id="ebaa0-709">vat no.</span></span>
  
<span data-ttu-id="ebaa0-710">vatno #</span><span class="sxs-lookup"><span data-stu-id="ebaa0-710">vatno#</span></span>
  
<span data-ttu-id="ebaa0-711">ID partita IVA</span><span class="sxs-lookup"><span data-stu-id="ebaa0-711">vat id</span></span>
  
<span data-ttu-id="ebaa0-712">ID partita IVA #</span><span class="sxs-lookup"><span data-stu-id="ebaa0-712">vat id#</span></span>
  
<span data-ttu-id="ebaa0-713">numero Identyfikacji Podatkowej</span><span class="sxs-lookup"><span data-stu-id="ebaa0-713">numer identyfikacji podatkowej</span></span>
  
<span data-ttu-id="ebaa0-714">Polski numero Identyfikacji Podatkowej</span><span class="sxs-lookup"><span data-stu-id="ebaa0-714">polski numer identyfikacji podatkowej</span></span>
  
<span data-ttu-id="ebaa0-715">numeridentyfikacjipodatkowej #</span><span class="sxs-lookup"><span data-stu-id="ebaa0-715">numeridentyfikacjipodatkowej#</span></span>
  
## <a name="portugal"></a><span data-ttu-id="ebaa0-716">Portogallo</span><span class="sxs-lookup"><span data-stu-id="ebaa0-716">Portugal</span></span>

### <a name="format"></a><span data-ttu-id="ebaa0-717">Formato</span><span class="sxs-lookup"><span data-stu-id="ebaa0-717">Format</span></span>

<span data-ttu-id="ebaa0-718">Nove cifre senza spazi o delimitatori</span><span class="sxs-lookup"><span data-stu-id="ebaa0-718">Nine digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="ebaa0-719">Modello</span><span class="sxs-lookup"><span data-stu-id="ebaa0-719">Pattern</span></span>

<span data-ttu-id="ebaa0-720">9 cifre</span><span class="sxs-lookup"><span data-stu-id="ebaa0-720">Nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="ebaa0-721">Checksum</span><span class="sxs-lookup"><span data-stu-id="ebaa0-721">Checksum</span></span>

<span data-ttu-id="ebaa0-722">Sì</span><span class="sxs-lookup"><span data-stu-id="ebaa0-722">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="ebaa0-723">Definizione</span><span class="sxs-lookup"><span data-stu-id="ebaa0-723">Definition</span></span>

<span data-ttu-id="ebaa0-724">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="ebaa0-724">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="ebaa0-725">La funzione `Func_portugal_eu_tax_file_number` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="ebaa0-725">The function  `Func_portugal_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="ebaa0-726">Viene trovata una `Keywords_portugal_eu_tax_file_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="ebaa0-726">A keyword from  `Keywords_portugal_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="ebaa0-727">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="ebaa0-727">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="ebaa0-728">La funzione `Func_portugal_eu_tax_file_number` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="ebaa0-728">The function  `Func_portugal_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="ebaa0-729">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="ebaa0-729">Keywords</span></span>

#### <a name="keywordsportugaleutaxfilenumber"></a><span data-ttu-id="ebaa0-730">Keywords_portugal_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="ebaa0-730">Keywords_portugal_eu_tax_file_number</span></span>

<span data-ttu-id="ebaa0-731">codice fiscale</span><span class="sxs-lookup"><span data-stu-id="ebaa0-731">tax number</span></span>
  
<span data-ttu-id="ebaa0-732">tassa no.</span><span class="sxs-lookup"><span data-stu-id="ebaa0-732">tax no.</span></span>
  
<span data-ttu-id="ebaa0-733">taxno #</span><span class="sxs-lookup"><span data-stu-id="ebaa0-733">taxno#</span></span>
  
<span data-ttu-id="ebaa0-734">taxnumber #</span><span class="sxs-lookup"><span data-stu-id="ebaa0-734">taxnumber#</span></span>
  
<span data-ttu-id="ebaa0-735">taxnumber</span><span class="sxs-lookup"><span data-stu-id="ebaa0-735">taxnumber</span></span>
  
<span data-ttu-id="ebaa0-736">NIF</span><span class="sxs-lookup"><span data-stu-id="ebaa0-736">nif</span></span>
  
<span data-ttu-id="ebaa0-737">NIF</span><span class="sxs-lookup"><span data-stu-id="ebaa0-737">nif#</span></span>
  
<span data-ttu-id="ebaa0-738">numero fiscale</span><span class="sxs-lookup"><span data-stu-id="ebaa0-738">numero fiscal</span></span>
  
<span data-ttu-id="ebaa0-739">número de identificação Fiscal</span><span class="sxs-lookup"><span data-stu-id="ebaa0-739">número de identificação fiscal</span></span>
  
## <a name="romania"></a><span data-ttu-id="ebaa0-740">Romania</span><span class="sxs-lookup"><span data-stu-id="ebaa0-740">Romania</span></span>

### <a name="format"></a><span data-ttu-id="ebaa0-741">Formato</span><span class="sxs-lookup"><span data-stu-id="ebaa0-741">Format</span></span>

<span data-ttu-id="ebaa0-742">13 cifre senza spazi o delimitatori</span><span class="sxs-lookup"><span data-stu-id="ebaa0-742">13 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="ebaa0-743">Modello</span><span class="sxs-lookup"><span data-stu-id="ebaa0-743">Pattern</span></span>

<span data-ttu-id="ebaa0-744">13 cifre</span><span class="sxs-lookup"><span data-stu-id="ebaa0-744">13 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="ebaa0-745">Checksum</span><span class="sxs-lookup"><span data-stu-id="ebaa0-745">Checksum</span></span>

<span data-ttu-id="ebaa0-746">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="ebaa0-746">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="ebaa0-747">Definizione</span><span class="sxs-lookup"><span data-stu-id="ebaa0-747">Definition</span></span>

<span data-ttu-id="ebaa0-748">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="ebaa0-748">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="ebaa0-749">L'espressione `Regex_romania_eu_tax_file_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="ebaa0-749">The regular expression  `Regex_romania_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="ebaa0-750">Viene trovata una `Keywords_romania_eu_tax_file_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="ebaa0-750">A keyword from  `Keywords_romania_eu_tax_file_number` is found.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_romania_eu_tax_file_number" />
          <Match idRef="Keywords_romania_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="ebaa0-751">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="ebaa0-751">Keywords</span></span>

#### <a name="keywordsromaniaeutaxfilenumber"></a><span data-ttu-id="ebaa0-752">Keywords_romania_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="ebaa0-752">Keywords_romania_eu_tax_file_number</span></span>

<span data-ttu-id="ebaa0-753">tax id
</span><span class="sxs-lookup"><span data-stu-id="ebaa0-753">tax id</span></span>
  
<span data-ttu-id="ebaa0-754">numero di ID fiscale</span><span class="sxs-lookup"><span data-stu-id="ebaa0-754">tax id number</span></span>
  
<span data-ttu-id="ebaa0-755">Tax File No</span><span class="sxs-lookup"><span data-stu-id="ebaa0-755">tax file no</span></span>
  
<span data-ttu-id="ebaa0-756">

tax file number</span><span class="sxs-lookup"><span data-stu-id="ebaa0-756">tax file number</span></span>
  
<span data-ttu-id="ebaa0-757">tax no</span><span class="sxs-lookup"><span data-stu-id="ebaa0-757">tax no</span></span>
  
<span data-ttu-id="ebaa0-758">codice fiscale</span><span class="sxs-lookup"><span data-stu-id="ebaa0-758">tax number</span></span>
  
<span data-ttu-id="ebaa0-759">taxid #</span><span class="sxs-lookup"><span data-stu-id="ebaa0-759">taxid#</span></span>
  
<span data-ttu-id="ebaa0-760">taxno #</span><span class="sxs-lookup"><span data-stu-id="ebaa0-760">taxno#</span></span>
  
<span data-ttu-id="ebaa0-761">ID-ul taxei</span><span class="sxs-lookup"><span data-stu-id="ebaa0-761">id-ul taxei</span></span>
  
<span data-ttu-id="ebaa0-762">numărul de identificare fiscală</span><span class="sxs-lookup"><span data-stu-id="ebaa0-762">numărul de identificare fiscală</span></span>
  
## <a name="slovakia"></a><span data-ttu-id="ebaa0-763">Slovacchia</span><span class="sxs-lookup"><span data-stu-id="ebaa0-763">Slovakia</span></span>

### <a name="format"></a><span data-ttu-id="ebaa0-764">Formato</span><span class="sxs-lookup"><span data-stu-id="ebaa0-764">Format</span></span>

<span data-ttu-id="ebaa0-765">10 cifre senza spazi o delimitatori</span><span class="sxs-lookup"><span data-stu-id="ebaa0-765">10 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="ebaa0-766">Modello</span><span class="sxs-lookup"><span data-stu-id="ebaa0-766">Pattern</span></span>

<span data-ttu-id="ebaa0-767">10 cifre</span><span class="sxs-lookup"><span data-stu-id="ebaa0-767">10 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="ebaa0-768">Checksum</span><span class="sxs-lookup"><span data-stu-id="ebaa0-768">Checksum</span></span>

<span data-ttu-id="ebaa0-769">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="ebaa0-769">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="ebaa0-770">Definizione</span><span class="sxs-lookup"><span data-stu-id="ebaa0-770">Definition</span></span>

<span data-ttu-id="ebaa0-771">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="ebaa0-771">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="ebaa0-772">L'espressione `Regex_slovakia_eu_tax_file_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="ebaa0-772">The regular expression  `Regex_slovakia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="ebaa0-773">Viene trovata una `Keywords_slovakia_eu_tax_file_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="ebaa0-773">A keyword from  `Keywords_slovakia_eu_tax_file_number` is found.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovakia_eu_tax_file_number" />
          <Match idRef="Keywords_slovakia_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="ebaa0-774">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="ebaa0-774">Keywords</span></span>

#### <a name="keywordsslovakiaeutaxfilenumber"></a><span data-ttu-id="ebaa0-775">Keywords_slovakia_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="ebaa0-775">Keywords_slovakia_eu_tax_file_number</span></span>

<span data-ttu-id="ebaa0-776">tax id
</span><span class="sxs-lookup"><span data-stu-id="ebaa0-776">tax id</span></span>
  
<span data-ttu-id="ebaa0-777">numero di ID fiscale</span><span class="sxs-lookup"><span data-stu-id="ebaa0-777">tax id number</span></span>
  
<span data-ttu-id="ebaa0-778">ID Tin</span><span class="sxs-lookup"><span data-stu-id="ebaa0-778">tin id</span></span>
  
<span data-ttu-id="ebaa0-779">Tin No</span><span class="sxs-lookup"><span data-stu-id="ebaa0-779">tin no</span></span>
  
<span data-ttu-id="ebaa0-780">ID Tin slovacco</span><span class="sxs-lookup"><span data-stu-id="ebaa0-780">slovakian tin id</span></span>
  
<span data-ttu-id="ebaa0-781">tin
</span><span class="sxs-lookup"><span data-stu-id="ebaa0-781">tin</span></span>
  
<span data-ttu-id="ebaa0-782">Tax File No</span><span class="sxs-lookup"><span data-stu-id="ebaa0-782">tax file no</span></span>
  
<span data-ttu-id="ebaa0-783">

tax file number</span><span class="sxs-lookup"><span data-stu-id="ebaa0-783">tax file number</span></span>
  
<span data-ttu-id="ebaa0-784">tax no</span><span class="sxs-lookup"><span data-stu-id="ebaa0-784">tax no</span></span>
  
<span data-ttu-id="ebaa0-785">codice fiscale</span><span class="sxs-lookup"><span data-stu-id="ebaa0-785">tax number</span></span>
  
<span data-ttu-id="ebaa0-786">taxid #</span><span class="sxs-lookup"><span data-stu-id="ebaa0-786">taxid#</span></span>
  
<span data-ttu-id="ebaa0-787">taxno #</span><span class="sxs-lookup"><span data-stu-id="ebaa0-787">taxno#</span></span>
  
<span data-ttu-id="ebaa0-788">daňové identifikačné číslo</span><span class="sxs-lookup"><span data-stu-id="ebaa0-788">daňové identifikačné číslo</span></span>
  
<span data-ttu-id="ebaa0-789">daňové číslo</span><span class="sxs-lookup"><span data-stu-id="ebaa0-789">daňové číslo</span></span>
  
<span data-ttu-id="ebaa0-790">daňové číslo súboru</span><span class="sxs-lookup"><span data-stu-id="ebaa0-790">daňové číslo súboru</span></span>
  
## <a name="slovenia"></a><span data-ttu-id="ebaa0-791">Slovenia</span><span class="sxs-lookup"><span data-stu-id="ebaa0-791">Slovenia</span></span>

### <a name="format"></a><span data-ttu-id="ebaa0-792">Formato</span><span class="sxs-lookup"><span data-stu-id="ebaa0-792">Format</span></span>

<span data-ttu-id="ebaa0-793">Otto cifre senza spazi o delimitatori</span><span class="sxs-lookup"><span data-stu-id="ebaa0-793">Eight digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="ebaa0-794">Modello</span><span class="sxs-lookup"><span data-stu-id="ebaa0-794">Pattern</span></span>

<span data-ttu-id="ebaa0-795">Otto cifre</span><span class="sxs-lookup"><span data-stu-id="ebaa0-795">Eight digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="ebaa0-796">Checksum</span><span class="sxs-lookup"><span data-stu-id="ebaa0-796">Checksum</span></span>

<span data-ttu-id="ebaa0-797">Sì</span><span class="sxs-lookup"><span data-stu-id="ebaa0-797">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="ebaa0-798">Definizione</span><span class="sxs-lookup"><span data-stu-id="ebaa0-798">Definition</span></span>

<span data-ttu-id="ebaa0-799">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="ebaa0-799">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="ebaa0-800">La funzione `Func_slovenia_eu_tax_file_number` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="ebaa0-800">The function  `Func_slovenia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="ebaa0-801">Viene trovata una `Keywords_slovenia_eu_tax_file_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="ebaa0-801">A keyword from  `Keywords_slovenia_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="ebaa0-802">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="ebaa0-802">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="ebaa0-803">La funzione `Func_slovenia_eu_tax_file_number` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="ebaa0-803">The function  `Func_slovenia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="ebaa0-804">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="ebaa0-804">Keywords</span></span>

#### <a name="keywordssloveniaeutaxfilenumber"></a><span data-ttu-id="ebaa0-805">Keywords_slovenia_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="ebaa0-805">Keywords_slovenia_eu_tax_file_number</span></span>

<span data-ttu-id="ebaa0-806">tax id
</span><span class="sxs-lookup"><span data-stu-id="ebaa0-806">tax id</span></span>
  
<span data-ttu-id="ebaa0-807">numero di ID fiscale</span><span class="sxs-lookup"><span data-stu-id="ebaa0-807">tax id number</span></span>
  
<span data-ttu-id="ebaa0-808">ID Tin</span><span class="sxs-lookup"><span data-stu-id="ebaa0-808">tin id</span></span>
  
<span data-ttu-id="ebaa0-809">Tin No</span><span class="sxs-lookup"><span data-stu-id="ebaa0-809">tin no</span></span>
  
<span data-ttu-id="ebaa0-810">ID Tin sloveno</span><span class="sxs-lookup"><span data-stu-id="ebaa0-810">slovenian tin id</span></span>
  
<span data-ttu-id="ebaa0-811">tin
</span><span class="sxs-lookup"><span data-stu-id="ebaa0-811">tin</span></span>
  
<span data-ttu-id="ebaa0-812">Tax File No</span><span class="sxs-lookup"><span data-stu-id="ebaa0-812">tax file no</span></span>
  
<span data-ttu-id="ebaa0-813">

tax file number</span><span class="sxs-lookup"><span data-stu-id="ebaa0-813">tax file number</span></span>
  
<span data-ttu-id="ebaa0-814">tax no</span><span class="sxs-lookup"><span data-stu-id="ebaa0-814">tax no</span></span>
  
<span data-ttu-id="ebaa0-815">codice fiscale</span><span class="sxs-lookup"><span data-stu-id="ebaa0-815">tax number</span></span>
  
<span data-ttu-id="ebaa0-816">taxid #</span><span class="sxs-lookup"><span data-stu-id="ebaa0-816">taxid#</span></span>
  
<span data-ttu-id="ebaa0-817">taxno #</span><span class="sxs-lookup"><span data-stu-id="ebaa0-817">taxno#</span></span>
  
<span data-ttu-id="ebaa0-818">identifikacijska številka davka</span><span class="sxs-lookup"><span data-stu-id="ebaa0-818">identifikacijska številka davka</span></span>
  
<span data-ttu-id="ebaa0-819">Davčna številka</span><span class="sxs-lookup"><span data-stu-id="ebaa0-819">davčna številka</span></span>
  
<span data-ttu-id="ebaa0-820">številka davčne datoteke</span><span class="sxs-lookup"><span data-stu-id="ebaa0-820">številka davčne datoteke</span></span>
  
## <a name="spain"></a><span data-ttu-id="ebaa0-821">Spagna</span><span class="sxs-lookup"><span data-stu-id="ebaa0-821">Spain</span></span>

### <a name="format"></a><span data-ttu-id="ebaa0-822">Formato</span><span class="sxs-lookup"><span data-stu-id="ebaa0-822">Format</span></span>

<span data-ttu-id="ebaa0-823">Sette o otto cifre e una o due lettere nel modello specificato</span><span class="sxs-lookup"><span data-stu-id="ebaa0-823">Seven or eight digits and one or two letters in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="ebaa0-824">Modello</span><span class="sxs-lookup"><span data-stu-id="ebaa0-824">Pattern</span></span>

<span data-ttu-id="ebaa0-825">Persone fisiche spagnole con carta d'identità nazionale spagnola:</span><span class="sxs-lookup"><span data-stu-id="ebaa0-825">Spanish Natural Persons with a Spain National Identity Card:</span></span>
  
-  <span data-ttu-id="ebaa0-826">Otto cifre</span><span class="sxs-lookup"><span data-stu-id="ebaa0-826">Eight digits</span></span> 
    
- <span data-ttu-id="ebaa0-827">Una lettera maiuscola (con distinzione tra maiuscole e minuscole)</span><span class="sxs-lookup"><span data-stu-id="ebaa0-827">One uppercase letter (case-sensitive)</span></span> 
    
<span data-ttu-id="ebaa0-828">Spagnoli non residenti senza una carta d'identità nazionale spagnola</span><span class="sxs-lookup"><span data-stu-id="ebaa0-828">Non-resident Spaniards without a Spain National Identity Card</span></span>
  
- <span data-ttu-id="ebaa0-829">Una lettera maiuscola "L" (con distinzione tra maiuscole e minuscole)</span><span class="sxs-lookup"><span data-stu-id="ebaa0-829">One uppercase letter "L" (case-sensitive)</span></span>
    
- <span data-ttu-id="ebaa0-830">Sette cifre</span><span class="sxs-lookup"><span data-stu-id="ebaa0-830">Seven digits</span></span>
    
- <span data-ttu-id="ebaa0-831">Una lettera maiuscola (con distinzione tra maiuscole e minuscole)</span><span class="sxs-lookup"><span data-stu-id="ebaa0-831">One uppercase letter (case-sensitive)</span></span> 
    
<span data-ttu-id="ebaa0-832">Spagnoli residenti di età inferiore ai 14 anni senza una carta d'identità nazionale spagnola:</span><span class="sxs-lookup"><span data-stu-id="ebaa0-832">Resident Spaniards under the age of 14 years without a Spain National Identity Card :</span></span>
  
- <span data-ttu-id="ebaa0-833">Una lettera maiuscola "K" (con distinzione tra maiuscole e minuscole)</span><span class="sxs-lookup"><span data-stu-id="ebaa0-833">One uppercase letter"K" (case-sensitive)</span></span>
    
-  <span data-ttu-id="ebaa0-834">Sette cifre</span><span class="sxs-lookup"><span data-stu-id="ebaa0-834">Seven digits</span></span> 
    
- <span data-ttu-id="ebaa0-835">Una lettera maiuscola (con distinzione tra maiuscole e minuscole)</span><span class="sxs-lookup"><span data-stu-id="ebaa0-835">One uppercase letter (case-sensitive)</span></span>
    
<span data-ttu-id="ebaa0-836">Stranieri con il numero di identificazione di un forestiero</span><span class="sxs-lookup"><span data-stu-id="ebaa0-836">Foreigners with a Foreigner's Identification Number</span></span>
  
- <span data-ttu-id="ebaa0-837">Una lettera maiuscola che è "X", "Y" o "Z" (con distinzione tra maiuscole e minuscole)</span><span class="sxs-lookup"><span data-stu-id="ebaa0-837">One uppercase letter that is "X", "Y", or "Z" (case-sensitive)</span></span> 
    
- <span data-ttu-id="ebaa0-838">Sette cifre</span><span class="sxs-lookup"><span data-stu-id="ebaa0-838">Seven digits</span></span>
    
- <span data-ttu-id="ebaa0-839">Una lettera maiuscola (con distinzione tra maiuscole e minuscole)</span><span class="sxs-lookup"><span data-stu-id="ebaa0-839">One uppercase letter (case-sensitive)</span></span> 
    
<span data-ttu-id="ebaa0-840">Stranieri senza il numero di identificazione di un forestiero</span><span class="sxs-lookup"><span data-stu-id="ebaa0-840">Foreigners without a Foreigner's Identification Number</span></span>
  
- <span data-ttu-id="ebaa0-841">Una lettera maiuscola che è "M" (con distinzione tra maiuscole e minuscole)</span><span class="sxs-lookup"><span data-stu-id="ebaa0-841">One uppercase letter that is "M" (case-sensitive)</span></span> 
    
- <span data-ttu-id="ebaa0-842">Sette cifre</span><span class="sxs-lookup"><span data-stu-id="ebaa0-842">Seven digits</span></span>
    
- <span data-ttu-id="ebaa0-843">Una lettera maiuscola (con distinzione tra maiuscole e minuscole)</span><span class="sxs-lookup"><span data-stu-id="ebaa0-843">One uppercase letter (case-sensitive)</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="ebaa0-844">Checksum</span><span class="sxs-lookup"><span data-stu-id="ebaa0-844">Checksum</span></span>

<span data-ttu-id="ebaa0-845">Sì</span><span class="sxs-lookup"><span data-stu-id="ebaa0-845">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="ebaa0-846">Definizione</span><span class="sxs-lookup"><span data-stu-id="ebaa0-846">Definition</span></span>

<span data-ttu-id="ebaa0-847">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="ebaa0-847">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="ebaa0-848">La funzione `Func_spain_eu_tax_file_number` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="ebaa0-848">The function  `Func_spain_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="ebaa0-849">Viene trovata una `Keywords_spain_eu_tax_file_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="ebaa0-849">A keyword from  `Keywords_spain_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="ebaa0-850">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="ebaa0-850">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="ebaa0-851">La funzione `Func_spain_eu_tax_file_number` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="ebaa0-851">The function  `Func_spain_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="ebaa0-852">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="ebaa0-852">Keywords</span></span>

#### <a name="keywordsspaineutaxfilenumber"></a><span data-ttu-id="ebaa0-853">Keywords_spain_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="ebaa0-853">Keywords_spain_eu_tax_file_number</span></span>

<span data-ttu-id="ebaa0-854">tax id
</span><span class="sxs-lookup"><span data-stu-id="ebaa0-854">tax id</span></span>
  
<span data-ttu-id="ebaa0-855">numero di ID fiscale</span><span class="sxs-lookup"><span data-stu-id="ebaa0-855">tax id number</span></span>
  
<span data-ttu-id="ebaa0-856">ID CIF</span><span class="sxs-lookup"><span data-stu-id="ebaa0-856">cif id</span></span>
  
<span data-ttu-id="ebaa0-857">CIF No</span><span class="sxs-lookup"><span data-stu-id="ebaa0-857">cif no</span></span>
  
<span data-ttu-id="ebaa0-858">ID CIF spagnolo</span><span class="sxs-lookup"><span data-stu-id="ebaa0-858">spanish cif id</span></span>
  
<span data-ttu-id="ebaa0-859">CIF</span><span class="sxs-lookup"><span data-stu-id="ebaa0-859">cif</span></span>
  
<span data-ttu-id="ebaa0-860">Tax File No</span><span class="sxs-lookup"><span data-stu-id="ebaa0-860">tax file no</span></span>
  
<span data-ttu-id="ebaa0-861">numero CIF spagnolo</span><span class="sxs-lookup"><span data-stu-id="ebaa0-861">spanish cif number</span></span>
  
<span data-ttu-id="ebaa0-862">

tax file number</span><span class="sxs-lookup"><span data-stu-id="ebaa0-862">tax file number</span></span>
  
<span data-ttu-id="ebaa0-863">Spagnolo CIF No</span><span class="sxs-lookup"><span data-stu-id="ebaa0-863">spanish cif no</span></span>
  
<span data-ttu-id="ebaa0-864">tax no</span><span class="sxs-lookup"><span data-stu-id="ebaa0-864">tax no</span></span>
  
<span data-ttu-id="ebaa0-865">codice fiscale</span><span class="sxs-lookup"><span data-stu-id="ebaa0-865">tax number</span></span>
  
<span data-ttu-id="ebaa0-866">taxid #</span><span class="sxs-lookup"><span data-stu-id="ebaa0-866">taxid#</span></span>
  
<span data-ttu-id="ebaa0-867">taxno #</span><span class="sxs-lookup"><span data-stu-id="ebaa0-867">taxno#</span></span>
  
<span data-ttu-id="ebaa0-868">cifid #</span><span class="sxs-lookup"><span data-stu-id="ebaa0-868">cifid#</span></span>
  
<span data-ttu-id="ebaa0-869">spanishcifid #</span><span class="sxs-lookup"><span data-stu-id="ebaa0-869">spanishcifid#</span></span>
  
<span data-ttu-id="ebaa0-870">spanishcifno #</span><span class="sxs-lookup"><span data-stu-id="ebaa0-870">spanishcifno#</span></span>
  
<span data-ttu-id="ebaa0-871">número de contribuyente</span><span class="sxs-lookup"><span data-stu-id="ebaa0-871">número de contribuyente</span></span>
  
<span data-ttu-id="ebaa0-872">número de Impuesto corporativo</span><span class="sxs-lookup"><span data-stu-id="ebaa0-872">número de impuesto corporativo</span></span>
  
<span data-ttu-id="ebaa0-873">número de Identificación Fiscal</span><span class="sxs-lookup"><span data-stu-id="ebaa0-873">número de identificación fiscal</span></span>
  
<span data-ttu-id="ebaa0-874">número CIF</span><span class="sxs-lookup"><span data-stu-id="ebaa0-874">cif número</span></span>
  
<span data-ttu-id="ebaa0-875">cifnúmero #</span><span class="sxs-lookup"><span data-stu-id="ebaa0-875">cifnúmero#</span></span>
  
## <a name="sweden"></a><span data-ttu-id="ebaa0-876">Svezia</span><span class="sxs-lookup"><span data-stu-id="ebaa0-876">Sweden</span></span>

### <a name="format"></a><span data-ttu-id="ebaa0-877">Formato</span><span class="sxs-lookup"><span data-stu-id="ebaa0-877">Format</span></span>

<span data-ttu-id="ebaa0-878">Dieci cifre e un simbolo nel modello specificato</span><span class="sxs-lookup"><span data-stu-id="ebaa0-878">Ten digits and a symbol in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="ebaa0-879">Modello</span><span class="sxs-lookup"><span data-stu-id="ebaa0-879">Pattern</span></span>

<span data-ttu-id="ebaa0-880">Dieci cifre e un simbolo:</span><span class="sxs-lookup"><span data-stu-id="ebaa0-880">Ten digits and a symbol:</span></span>
  
-  <span data-ttu-id="ebaa0-881">Sei cifre che corrispondono alla data di nascita (AAMMGG)</span><span class="sxs-lookup"><span data-stu-id="ebaa0-881">Six digits that correspond to the birth date (YYMMDD)</span></span> 
    
- <span data-ttu-id="ebaa0-882">Segno di addizione, segno meno o barra rovesciata</span><span class="sxs-lookup"><span data-stu-id="ebaa0-882">A plus sign, minus sign, or backslash</span></span>
    
- <span data-ttu-id="ebaa0-883">Tre cifre che rendono il numero di identificazione univoco dove:</span><span class="sxs-lookup"><span data-stu-id="ebaa0-883">Three digits that make the identification number unique where:</span></span> 
    
  - <span data-ttu-id="ebaa0-884">Per i numeri emessi prima del 1990, la settima e la terza cifra identificano la Contea di nascita o gli stranieri nati</span><span class="sxs-lookup"><span data-stu-id="ebaa0-884">For numbers issued before 1990, the seventh and eighth digit identify the county of birth or foreign-born people</span></span>
    
  - <span data-ttu-id="ebaa0-885">La cifra nella nona posizione indica il sesso per il maschio o per la femmina.</span><span class="sxs-lookup"><span data-stu-id="ebaa0-885">The digit in the ninth position indicates gender by either odd for male or even for female</span></span>
    
- <span data-ttu-id="ebaa0-886">Una cifra di controllo</span><span class="sxs-lookup"><span data-stu-id="ebaa0-886">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="ebaa0-887">Checksum</span><span class="sxs-lookup"><span data-stu-id="ebaa0-887">Checksum</span></span>

<span data-ttu-id="ebaa0-888">Sì</span><span class="sxs-lookup"><span data-stu-id="ebaa0-888">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="ebaa0-889">Definizione</span><span class="sxs-lookup"><span data-stu-id="ebaa0-889">Definition</span></span>

<span data-ttu-id="ebaa0-890">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="ebaa0-890">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="ebaa0-891">La funzione `Func_sweden_eu_tax_file_number` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="ebaa0-891">The function  `Func_sweden_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="ebaa0-892">Viene trovata una `Keywords_sweden_eu_tax_file_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="ebaa0-892">A keyword from  `Keywords_sweden_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="ebaa0-893">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="ebaa0-893">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="ebaa0-894">La funzione `Func_sweden_eu_tax_file_number` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="ebaa0-894">The function  `Func_sweden_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="ebaa0-895">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="ebaa0-895">Keywords</span></span>

#### <a name="keywordsswedeneutaxfilenumber"></a><span data-ttu-id="ebaa0-896">Keywords_sweden_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="ebaa0-896">Keywords_sweden_eu_tax_file_number</span></span>

<span data-ttu-id="ebaa0-897">tax id
</span><span class="sxs-lookup"><span data-stu-id="ebaa0-897">tax id</span></span>
  
<span data-ttu-id="ebaa0-898">ID IVA No.</span><span class="sxs-lookup"><span data-stu-id="ebaa0-898">tax id no.</span></span>
  
<span data-ttu-id="ebaa0-899">numero di ID fiscale</span><span class="sxs-lookup"><span data-stu-id="ebaa0-899">tax id number</span></span>
  
<span data-ttu-id="ebaa0-900">tax identification
</span><span class="sxs-lookup"><span data-stu-id="ebaa0-900">tax identification</span></span>
  
<span data-ttu-id="ebaa0-901">identificazione fiscale #</span><span class="sxs-lookup"><span data-stu-id="ebaa0-901">tax identification#</span></span>
  
<span data-ttu-id="ebaa0-902">tassa no.</span><span class="sxs-lookup"><span data-stu-id="ebaa0-902">tax no.</span></span>
  
<span data-ttu-id="ebaa0-903">imposte</span><span class="sxs-lookup"><span data-stu-id="ebaa0-903">tax#</span></span>
  
<span data-ttu-id="ebaa0-904">taxid #</span><span class="sxs-lookup"><span data-stu-id="ebaa0-904">taxid#</span></span>
  
<span data-ttu-id="ebaa0-905">file fiscale</span><span class="sxs-lookup"><span data-stu-id="ebaa0-905">tax file</span></span>
  
<span data-ttu-id="ebaa0-906">Tax File No.</span><span class="sxs-lookup"><span data-stu-id="ebaa0-906">tax file no.</span></span>
  
<span data-ttu-id="ebaa0-907">numero ID personale</span><span class="sxs-lookup"><span data-stu-id="ebaa0-907">personal id number</span></span>
  
<span data-ttu-id="ebaa0-908">ID pattinat Nummer</span><span class="sxs-lookup"><span data-stu-id="ebaa0-908">skatt id nummer</span></span>
  
<span data-ttu-id="ebaa0-909">Identifikation skatet</span><span class="sxs-lookup"><span data-stu-id="ebaa0-909">skatt identifikation</span></span>
  
<span data-ttu-id="ebaa0-910">personnummer</span><span class="sxs-lookup"><span data-stu-id="ebaa0-910">personnummer</span></span>
  
## <a name="uk"></a><span data-ttu-id="ebaa0-911">Regno Unito</span><span class="sxs-lookup"><span data-stu-id="ebaa0-911">UK</span></span>

### <a name="format"></a><span data-ttu-id="ebaa0-912">Formato</span><span class="sxs-lookup"><span data-stu-id="ebaa0-912">Format</span></span>

<span data-ttu-id="ebaa0-913">Riferimento per i contribuenti unici (UTR): 10 cifre senza spazi e delimitatori</span><span class="sxs-lookup"><span data-stu-id="ebaa0-913">Unique Taxpayer Reference (UTR): 10 digits without spaces and delimiters</span></span>
  
<span data-ttu-id="ebaa0-p103">Numero di assicurazione nazionale (NINO): per informazioni dettagliate, vedere la sezione "Regno Unito National Insurance Number (NINO)" in [che cosa cercano i tipi di informazioni riservate](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="ebaa0-p103">National Insurance Number (NINO): For details, see the section "U.K. National Insurance Number (NINO)" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
### <a name="pattern"></a><span data-ttu-id="ebaa0-916">Modello</span><span class="sxs-lookup"><span data-stu-id="ebaa0-916">Pattern</span></span>

<span data-ttu-id="ebaa0-917">Riferimento per i contribuenti unici (UTR): 10 cifre</span><span class="sxs-lookup"><span data-stu-id="ebaa0-917">Unique Taxpayer Reference (UTR): 10 digits</span></span>
  
<span data-ttu-id="ebaa0-p104">Numero di assicurazione nazionale (NINO): per informazioni dettagliate, vedere la sezione "Regno Unito National Insurance Number (NINO)" in [che cosa cercano i tipi di informazioni riservate](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="ebaa0-p104">National Insurance Number (NINO): For details, see the section "U.K. National Insurance Number (NINO)" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
### <a name="checksum"></a><span data-ttu-id="ebaa0-920">Checksum</span><span class="sxs-lookup"><span data-stu-id="ebaa0-920">Checksum</span></span>

<span data-ttu-id="ebaa0-921">Sì</span><span class="sxs-lookup"><span data-stu-id="ebaa0-921">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="ebaa0-922">Definizione</span><span class="sxs-lookup"><span data-stu-id="ebaa0-922">Definition</span></span>

<span data-ttu-id="ebaa0-923">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="ebaa0-923">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="ebaa0-924">La funzione `Func_uk_eu_tax_file_number` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="ebaa0-924">The function  `Func_uk_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="ebaa0-925">Viene trovata una `Keywords_uk_eu_tax_file_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="ebaa0-925">A keyword from  `Keywords_uk_eu_tax_file_number` is found.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_uk_eu_tax_file_number" />
          <Match idRef="Keywords_uk_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="ebaa0-926">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="ebaa0-926">Keywords</span></span>

#### <a name="keywordsukeutaxfilenumber"></a><span data-ttu-id="ebaa0-927">Keywords_uk_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="ebaa0-927">Keywords_uk_eu_tax_file_number</span></span>

<span data-ttu-id="ebaa0-928">tax id
</span><span class="sxs-lookup"><span data-stu-id="ebaa0-928">tax id</span></span>
  
<span data-ttu-id="ebaa0-929">ID IVA No.</span><span class="sxs-lookup"><span data-stu-id="ebaa0-929">tax id no.</span></span>
  
<span data-ttu-id="ebaa0-930">numero di ID fiscale</span><span class="sxs-lookup"><span data-stu-id="ebaa0-930">tax id number</span></span>
  
<span data-ttu-id="ebaa0-931">tax identification
</span><span class="sxs-lookup"><span data-stu-id="ebaa0-931">tax identification</span></span>
  
<span data-ttu-id="ebaa0-932">identificazione fiscale #</span><span class="sxs-lookup"><span data-stu-id="ebaa0-932">tax identification#</span></span>
  
<span data-ttu-id="ebaa0-933">tassa no.</span><span class="sxs-lookup"><span data-stu-id="ebaa0-933">tax no.</span></span>
  
<span data-ttu-id="ebaa0-934">imposte</span><span class="sxs-lookup"><span data-stu-id="ebaa0-934">tax#</span></span>
  
<span data-ttu-id="ebaa0-935">taxid #</span><span class="sxs-lookup"><span data-stu-id="ebaa0-935">taxid#</span></span>
  
<span data-ttu-id="ebaa0-936">file fiscale</span><span class="sxs-lookup"><span data-stu-id="ebaa0-936">tax file</span></span>
  
<span data-ttu-id="ebaa0-937">Tax File No.</span><span class="sxs-lookup"><span data-stu-id="ebaa0-937">tax file no.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="ebaa0-938">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ebaa0-938">See also</span></span>

[<span data-ttu-id="ebaa0-939">Cosa individuano le tipologie di informazioni sensibili</span><span class="sxs-lookup"><span data-stu-id="ebaa0-939">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)

