---
title: Numero di identificazione fiscale dell'Unione europea
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 8/17/2018
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
description: In questo argomento viene illustrato l'aspetto di un criterio di prevenzione della perdita di dati (DLP) quando viene rilevato il tipo di informazioni riservate del numero di identificazione fiscale dell'Unione europea. Questo tipo di informazioni riservate definisce modelli, parole chiave e altre evidenze diverse per ogni paese.
ms.openlocfilehash: adcd9be9b5f8775ad39010d771ff2ac214df1e17
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/17/2019
ms.locfileid: "34152958"
---
# <a name="eu-tax-identification-number"></a><span data-ttu-id="f03f6-104">Numero di identificazione fiscale dell'Unione europea</span><span class="sxs-lookup"><span data-stu-id="f03f6-104">EU Tax Identification Number</span></span>

<span data-ttu-id="f03f6-105">In questo argomento viene illustrato l'aspetto di un criterio di prevenzione della perdita di dati (DLP) quando viene rilevato il tipo di informazioni riservate del numero di identificazione fiscale (TIN) dell'Unione europea.</span><span class="sxs-lookup"><span data-stu-id="f03f6-105">This topic shows what a data loss prevention (DLP) policy looks for when it detects the EU Tax Identification Number (TIN) sensitive information type.</span></span> <span data-ttu-id="f03f6-106">Questo tipo di informazioni riservate definisce modelli, parole chiave e altre evidenze diverse per ogni paese.</span><span class="sxs-lookup"><span data-stu-id="f03f6-106">This sensitive information type defines different patterns, keywords, and other evidence for each country.</span></span>
  
## <a name="austria"></a><span data-ttu-id="f03f6-107">Austria</span><span class="sxs-lookup"><span data-stu-id="f03f6-107">Austria</span></span>

### <a name="format"></a><span data-ttu-id="f03f6-108">Formato</span><span class="sxs-lookup"><span data-stu-id="f03f6-108">Format</span></span>

<span data-ttu-id="f03f6-109">Nove cifre con trattino e barra di inoltro opzionali</span><span class="sxs-lookup"><span data-stu-id="f03f6-109">Nine digits with optional hyphen and forward slash</span></span>
  
### <a name="pattern"></a><span data-ttu-id="f03f6-110">Modello</span><span class="sxs-lookup"><span data-stu-id="f03f6-110">Pattern</span></span>

<span data-ttu-id="f03f6-111">Nove cifre con trattino e barra di inoltro facoltativi:</span><span class="sxs-lookup"><span data-stu-id="f03f6-111">Nine digits with optional hyphen and forward slash:</span></span>
  
-  <span data-ttu-id="f03f6-112">Due cifre</span><span class="sxs-lookup"><span data-stu-id="f03f6-112">Two digits</span></span> 
    
- <span data-ttu-id="f03f6-113">Una lineetta (facoltativa)</span><span class="sxs-lookup"><span data-stu-id="f03f6-113">A hyphen (optional)</span></span>
    
- <span data-ttu-id="f03f6-114">Tre cifre</span><span class="sxs-lookup"><span data-stu-id="f03f6-114">Three digits</span></span>
    
- <span data-ttu-id="f03f6-115">Una barra (facoltativa)</span><span class="sxs-lookup"><span data-stu-id="f03f6-115">A forward slash (optional)</span></span>
    
- <span data-ttu-id="f03f6-116">Quattro cifre</span><span class="sxs-lookup"><span data-stu-id="f03f6-116">Four digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="f03f6-117">Checksum</span><span class="sxs-lookup"><span data-stu-id="f03f6-117">Checksum</span></span>

<span data-ttu-id="f03f6-118">Sì</span><span class="sxs-lookup"><span data-stu-id="f03f6-118">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="f03f6-119">Definizione</span><span class="sxs-lookup"><span data-stu-id="f03f6-119">Definition</span></span>

<span data-ttu-id="f03f6-120">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="f03f6-120">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="f03f6-121">La funzione `Func_austria_eu_tax_file_number` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="f03f6-121">The function  `Func_austria_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="f03f6-122">Viene trovata una `Keywords_austria_eu_tax_file_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="f03f6-122">A keyword from  `Keywords_austria_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="f03f6-123">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="f03f6-123">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="f03f6-124">La funzione `Func_austria_eu_tax_file_number` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="f03f6-124">The function  `Func_austria_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="f03f6-125">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="f03f6-125">Keywords</span></span>

#### <a name="keywordsaustriaeutaxfilenumber"></a><span data-ttu-id="f03f6-126">Keywords_austria_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="f03f6-126">Keywords_austria_eu_tax_file_number</span></span>

<span data-ttu-id="f03f6-127">codice fiscale</span><span class="sxs-lookup"><span data-stu-id="f03f6-127">tax number</span></span>
  
<span data-ttu-id="f03f6-128">numero</span><span class="sxs-lookup"><span data-stu-id="f03f6-128">number</span></span>
  
<span data-ttu-id="f03f6-129">numero di registrazione fiscale</span><span class="sxs-lookup"><span data-stu-id="f03f6-129">tax registration number</span></span>
  
<span data-ttu-id="f03f6-130">tax id</span><span class="sxs-lookup"><span data-stu-id="f03f6-130">tax id</span></span>
  
<span data-ttu-id="f03f6-131">st.nr.</span><span class="sxs-lookup"><span data-stu-id="f03f6-131">st.nr.</span></span>
  
<span data-ttu-id="f03f6-132">steuernummer</span><span class="sxs-lookup"><span data-stu-id="f03f6-132">steuernummer</span></span>
  
## <a name="belgium"></a><span data-ttu-id="f03f6-133">Belgio</span><span class="sxs-lookup"><span data-stu-id="f03f6-133">Belgium</span></span>

### <a name="format"></a><span data-ttu-id="f03f6-134">Formato</span><span class="sxs-lookup"><span data-stu-id="f03f6-134">Format</span></span>

<span data-ttu-id="f03f6-135">11 cifre senza spazi e delimitatori</span><span class="sxs-lookup"><span data-stu-id="f03f6-135">11 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="f03f6-136">Modello</span><span class="sxs-lookup"><span data-stu-id="f03f6-136">Pattern</span></span>

<span data-ttu-id="f03f6-137">11 cifre:</span><span class="sxs-lookup"><span data-stu-id="f03f6-137">11 digits:</span></span>
  
- <span data-ttu-id="f03f6-138">Due cifre</span><span class="sxs-lookup"><span data-stu-id="f03f6-138">Two digits</span></span>
    
- <span data-ttu-id="f03f6-139">"0" o "1"</span><span class="sxs-lookup"><span data-stu-id="f03f6-139">A "0" or "1"</span></span>
    
- <span data-ttu-id="f03f6-140">Una cifra</span><span class="sxs-lookup"><span data-stu-id="f03f6-140">One digit</span></span>
    
- <span data-ttu-id="f03f6-141">"0" o "1" o "2" o "3"</span><span class="sxs-lookup"><span data-stu-id="f03f6-141">A "0" or "1" or "2" or "3"</span></span> 
    
- <span data-ttu-id="f03f6-142">Sei cifre</span><span class="sxs-lookup"><span data-stu-id="f03f6-142">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="f03f6-143">Checksum</span><span class="sxs-lookup"><span data-stu-id="f03f6-143">Checksum</span></span>

<span data-ttu-id="f03f6-144">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="f03f6-144">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="f03f6-145">Definizione</span><span class="sxs-lookup"><span data-stu-id="f03f6-145">Definition</span></span>

<span data-ttu-id="f03f6-146">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="f03f6-146">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="f03f6-147">L'espressione `Regex_belgium_eu_tax_file_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="f03f6-147">The regular expression  `Regex_belgium_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="f03f6-148">Viene trovata una `Keywords_belgium_eu_tax_file_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="f03f6-148">A keyword from  `Keywords_belgium_eu_tax_file_number` is found.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_belgium_eu_tax_file_number" />
          <Match idRef="Keywords_belgium_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="f03f6-149">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="f03f6-149">Keywords</span></span>

#### <a name="keywordsbelgiumeutaxfilenumber"></a><span data-ttu-id="f03f6-150">Keywords_belgium_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="f03f6-150">Keywords_belgium_eu_tax_file_number</span></span>

<span data-ttu-id="f03f6-151">codice fiscale</span><span class="sxs-lookup"><span data-stu-id="f03f6-151">tax number</span></span>
  
<span data-ttu-id="f03f6-152">numero di registrazione nazionale</span><span class="sxs-lookup"><span data-stu-id="f03f6-152">national registration number</span></span>
  
<span data-ttu-id="f03f6-153">numero di registrazione fiscale</span><span class="sxs-lookup"><span data-stu-id="f03f6-153">tax registration number</span></span>
  
<span data-ttu-id="f03f6-154">tax id</span><span class="sxs-lookup"><span data-stu-id="f03f6-154">tax id</span></span>
  
<span data-ttu-id="f03f6-155">NIF</span><span class="sxs-lookup"><span data-stu-id="f03f6-155">nif</span></span>
  
<span data-ttu-id="f03f6-156">NIF</span><span class="sxs-lookup"><span data-stu-id="f03f6-156">nif#</span></span>
  
<span data-ttu-id="f03f6-157">numéro de Registre National</span><span class="sxs-lookup"><span data-stu-id="f03f6-157">numéro de registre national</span></span>
  
<span data-ttu-id="f03f6-158">numéro d'identification fiscale</span><span class="sxs-lookup"><span data-stu-id="f03f6-158">numéro d'identification fiscale</span></span>
  
## <a name="bulgaria"></a><span data-ttu-id="f03f6-159">Bulgaria</span><span class="sxs-lookup"><span data-stu-id="f03f6-159">Bulgaria</span></span>

### <a name="format"></a><span data-ttu-id="f03f6-160">Formato</span><span class="sxs-lookup"><span data-stu-id="f03f6-160">Format</span></span>

<span data-ttu-id="f03f6-161">Dieci cifre senza spazi e delimitatori</span><span class="sxs-lookup"><span data-stu-id="f03f6-161">Ten digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="f03f6-162">Modello</span><span class="sxs-lookup"><span data-stu-id="f03f6-162">Pattern</span></span>

<span data-ttu-id="f03f6-163">10 cifre</span><span class="sxs-lookup"><span data-stu-id="f03f6-163">10 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="f03f6-164">Checksum</span><span class="sxs-lookup"><span data-stu-id="f03f6-164">Checksum</span></span>

<span data-ttu-id="f03f6-165">Sì</span><span class="sxs-lookup"><span data-stu-id="f03f6-165">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="f03f6-166">Definizione</span><span class="sxs-lookup"><span data-stu-id="f03f6-166">Definition</span></span>

<span data-ttu-id="f03f6-167">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="f03f6-167">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="f03f6-168">La funzione `Func_bulgaria_eu_tax_file_number` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="f03f6-168">The function  `Func_bulgaria_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="f03f6-169">Viene trovata una `Keywords_bulgaria_eu_tax_file_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="f03f6-169">A keyword from  `Keywords_bulgaria_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="f03f6-170">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="f03f6-170">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="f03f6-171">La funzione `Func_bulgaria_eu_tax_file_number` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="f03f6-171">The function  `Func_bulgaria_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="f03f6-172">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="f03f6-172">Keywords</span></span>

#### <a name="keywordsbulgariaeutaxfilenumber"></a><span data-ttu-id="f03f6-173">Keywords_bulgaria_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="f03f6-173">Keywords_bulgaria_eu_tax_file_number</span></span>

<span data-ttu-id="f03f6-174">bucn</span><span class="sxs-lookup"><span data-stu-id="f03f6-174">bucn</span></span>
  
<span data-ttu-id="f03f6-175">numero civile uniforme</span><span class="sxs-lookup"><span data-stu-id="f03f6-175">uniform civil number</span></span>
  
<span data-ttu-id="f03f6-176">bucn#</span><span class="sxs-lookup"><span data-stu-id="f03f6-176">bucn#</span></span>
  
<span data-ttu-id="f03f6-177">uniformcivilnumber#</span><span class="sxs-lookup"><span data-stu-id="f03f6-177">uniformcivilnumber#</span></span>
  
<span data-ttu-id="f03f6-178">ID civile uniforme</span><span class="sxs-lookup"><span data-stu-id="f03f6-178">uniform civil id</span></span>
  
<span data-ttu-id="f03f6-179">uniforme civile No</span><span class="sxs-lookup"><span data-stu-id="f03f6-179">uniform civil no</span></span>
  
<span data-ttu-id="f03f6-180">EGN</span><span class="sxs-lookup"><span data-stu-id="f03f6-180">egn</span></span>
  
<span data-ttu-id="f03f6-181">numero civile uniforme bulgaro</span><span class="sxs-lookup"><span data-stu-id="f03f6-181">bulgarian uniform civil number</span></span>
  
<span data-ttu-id="f03f6-182">uniformcivilno#</span><span class="sxs-lookup"><span data-stu-id="f03f6-182">uniformcivilno#</span></span>
  
<span data-ttu-id="f03f6-183">EGN</span><span class="sxs-lookup"><span data-stu-id="f03f6-183">egn#</span></span>
  
<span data-ttu-id="f03f6-184">униформ граждански номер</span><span class="sxs-lookup"><span data-stu-id="f03f6-184">униформ граждански номер</span></span>
  
<span data-ttu-id="f03f6-185">ID униформ</span><span class="sxs-lookup"><span data-stu-id="f03f6-185">униформ id</span></span>
  
<span data-ttu-id="f03f6-186">ID граждански униформ</span><span class="sxs-lookup"><span data-stu-id="f03f6-186">униформ граждански id</span></span>
  
<span data-ttu-id="f03f6-187">униформ граждански не</span><span class="sxs-lookup"><span data-stu-id="f03f6-187">униформ граждански не</span></span>
  
## <a name="croatia"></a><span data-ttu-id="f03f6-188">Croazia</span><span class="sxs-lookup"><span data-stu-id="f03f6-188">Croatia</span></span>

### <a name="format"></a><span data-ttu-id="f03f6-189">Formato</span><span class="sxs-lookup"><span data-stu-id="f03f6-189">Format</span></span>

<span data-ttu-id="f03f6-190">11 cifre senza spazi o delimitatori</span><span class="sxs-lookup"><span data-stu-id="f03f6-190">11 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="f03f6-191">Modello</span><span class="sxs-lookup"><span data-stu-id="f03f6-191">Pattern</span></span>

<span data-ttu-id="f03f6-192">11 cifre:</span><span class="sxs-lookup"><span data-stu-id="f03f6-192">11 digits:</span></span>
  
- <span data-ttu-id="f03f6-193">Dieci cifre, scelte casualmente</span><span class="sxs-lookup"><span data-stu-id="f03f6-193">Ten digits, randomly chosen</span></span>
    
- <span data-ttu-id="f03f6-194">Una cifra di controllo</span><span class="sxs-lookup"><span data-stu-id="f03f6-194">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="f03f6-195">Checksum</span><span class="sxs-lookup"><span data-stu-id="f03f6-195">Checksum</span></span>

<span data-ttu-id="f03f6-196">Sì</span><span class="sxs-lookup"><span data-stu-id="f03f6-196">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="f03f6-197">Definizione</span><span class="sxs-lookup"><span data-stu-id="f03f6-197">Definition</span></span>

<span data-ttu-id="f03f6-198">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="f03f6-198">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="f03f6-199">La funzione `Func_croatia_eu_tax_file_number` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="f03f6-199">The function  `Func_croatia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="f03f6-200">Viene trovata una `Keywords_croatia_eu_tax_file_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="f03f6-200">A keyword from  `Keywords_croatia_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="f03f6-201">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="f03f6-201">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="f03f6-202">La funzione `Func_croatia_eu_tax_file_number` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="f03f6-202">The function  `Func_croatia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="f03f6-203">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="f03f6-203">Keywords</span></span>

#### <a name="keywordscroatiaeutaxfilenumber"></a><span data-ttu-id="f03f6-204">Keywords_croatia_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="f03f6-204">Keywords_croatia_eu_tax_file_number</span></span>

<span data-ttu-id="f03f6-205">codice fiscale</span><span class="sxs-lookup"><span data-stu-id="f03f6-205">tax number</span></span>
  
<span data-ttu-id="f03f6-206">imposte</span><span class="sxs-lookup"><span data-stu-id="f03f6-206">tax</span></span>
  
<span data-ttu-id="f03f6-207">tax id</span><span class="sxs-lookup"><span data-stu-id="f03f6-207">tax id</span></span>
  
<span data-ttu-id="f03f6-208">OID</span><span class="sxs-lookup"><span data-stu-id="f03f6-208">oid</span></span>
  
<span data-ttu-id="f03f6-209">OID</span><span class="sxs-lookup"><span data-stu-id="f03f6-209">oid#</span></span>
  
<span data-ttu-id="f03f6-210">Porezni broj</span><span class="sxs-lookup"><span data-stu-id="f03f6-210">porezni broj</span></span>
  
## <a name="cyprus"></a><span data-ttu-id="f03f6-211">Cipro</span><span class="sxs-lookup"><span data-stu-id="f03f6-211">Cyprus</span></span>

### <a name="format"></a><span data-ttu-id="f03f6-212">Formato</span><span class="sxs-lookup"><span data-stu-id="f03f6-212">Format</span></span>

<span data-ttu-id="f03f6-213">Otto cifre e una lettera nel modello specificato</span><span class="sxs-lookup"><span data-stu-id="f03f6-213">Eight digits and one letter in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="f03f6-214">Modello</span><span class="sxs-lookup"><span data-stu-id="f03f6-214">Pattern</span></span>

<span data-ttu-id="f03f6-215">Otto cifre e una lettera:</span><span class="sxs-lookup"><span data-stu-id="f03f6-215">Eight digits and one letter:</span></span>
  
-  <span data-ttu-id="f03f6-216">Un "0"</span><span class="sxs-lookup"><span data-stu-id="f03f6-216">A "0"</span></span> 
    
- <span data-ttu-id="f03f6-217">Sette cifre</span><span class="sxs-lookup"><span data-stu-id="f03f6-217">Seven digits</span></span>
    
- <span data-ttu-id="f03f6-218">Una lettera (senza distinzione tra maiuscole e minuscole)</span><span class="sxs-lookup"><span data-stu-id="f03f6-218">One letter (not case-sensitive)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="f03f6-219">Checksum</span><span class="sxs-lookup"><span data-stu-id="f03f6-219">Checksum</span></span>

<span data-ttu-id="f03f6-220">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="f03f6-220">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="f03f6-221">Definizione</span><span class="sxs-lookup"><span data-stu-id="f03f6-221">Definition</span></span>

<span data-ttu-id="f03f6-222">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="f03f6-222">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="f03f6-223">La funzione `Func_cyprus_eu_tax_file_number` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="f03f6-223">The function  `Func_cyprus_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="f03f6-224">Viene trovata una `Keywords_cyprus_eu_tax_file_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="f03f6-224">A keyword from  `Keywords_cyprus_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="f03f6-225">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="f03f6-225">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="f03f6-226">La funzione `Func_cyprus_eu_tax_file_number` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="f03f6-226">The function  `Func_cyprus_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="f03f6-227">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="f03f6-227">Keywords</span></span>

#### <a name="keywordscypruseutaxfilenumber"></a><span data-ttu-id="f03f6-228">Keywords_cyprus_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="f03f6-228">Keywords_cyprus_eu_tax_file_number</span></span>

<span data-ttu-id="f03f6-229">codice fiscale</span><span class="sxs-lookup"><span data-stu-id="f03f6-229">tax number</span></span>
  
<span data-ttu-id="f03f6-230">imposte</span><span class="sxs-lookup"><span data-stu-id="f03f6-230">tax</span></span>
  
<span data-ttu-id="f03f6-231">tax id</span><span class="sxs-lookup"><span data-stu-id="f03f6-231">tax id</span></span>
  
<span data-ttu-id="f03f6-232">codice di identificazione fiscale</span><span class="sxs-lookup"><span data-stu-id="f03f6-232">tax identification code</span></span>
  
<span data-ttu-id="f03f6-233">TIC</span><span class="sxs-lookup"><span data-stu-id="f03f6-233">tic</span></span>
  
<span data-ttu-id="f03f6-234">TIC</span><span class="sxs-lookup"><span data-stu-id="f03f6-234">tic#</span></span>
  
<span data-ttu-id="f03f6-235">αριθμός φορολογικού μητρώου</span><span class="sxs-lookup"><span data-stu-id="f03f6-235">αριθμός φορολογικού μητρώου</span></span>
  
<span data-ttu-id="f03f6-236">φορολογική ταυτότητα</span><span class="sxs-lookup"><span data-stu-id="f03f6-236">φορολογική ταυτότητα</span></span>
  
<span data-ttu-id="f03f6-237">κωδικός φορολογικού μητρώου</span><span class="sxs-lookup"><span data-stu-id="f03f6-237">κωδικός φορολογικού μητρώου</span></span>
  
## <a name="czech-republic"></a><span data-ttu-id="f03f6-238">Repubblica Ceca</span><span class="sxs-lookup"><span data-stu-id="f03f6-238">Czech Republic</span></span>

### <a name="format"></a><span data-ttu-id="f03f6-239">Formato</span><span class="sxs-lookup"><span data-stu-id="f03f6-239">Format</span></span>

<span data-ttu-id="f03f6-240">Nove o dieci cifre con una barra rovesciata facoltativa</span><span class="sxs-lookup"><span data-stu-id="f03f6-240">Nine or ten digits with an optional backslash</span></span>
  
### <a name="pattern"></a><span data-ttu-id="f03f6-241">Modello</span><span class="sxs-lookup"><span data-stu-id="f03f6-241">Pattern</span></span>

<span data-ttu-id="f03f6-242">Nove o dieci cifre con un backslash facoltativo:</span><span class="sxs-lookup"><span data-stu-id="f03f6-242">Nine or ten digits with an optional backslashl:</span></span>
  
- <span data-ttu-id="f03f6-243">Sei cifre</span><span class="sxs-lookup"><span data-stu-id="f03f6-243">Six digits</span></span> 
    
- <span data-ttu-id="f03f6-244">Una barra rovesciata (facoltativa)</span><span class="sxs-lookup"><span data-stu-id="f03f6-244">A backslash (optional)</span></span>
    
- <span data-ttu-id="f03f6-245">Tre o quattro cifre</span><span class="sxs-lookup"><span data-stu-id="f03f6-245">Three or four digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="f03f6-246">Checksum</span><span class="sxs-lookup"><span data-stu-id="f03f6-246">Checksum</span></span>

<span data-ttu-id="f03f6-247">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="f03f6-247">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="f03f6-248">Definizione</span><span class="sxs-lookup"><span data-stu-id="f03f6-248">Definition</span></span>

<span data-ttu-id="f03f6-249">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="f03f6-249">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="f03f6-250">L'espressione `Regex_czech_republic_eu_tax_file_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="f03f6-250">The regular expression  `Regex_czech_republic_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="f03f6-251">Viene trovata una `Keywords_czech_republic_eu_tax_file_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="f03f6-251">A keyword from  `Keywords_czech_republic_eu_tax_file_number` is found.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_czech_republic_eu_tax_file_number" />
          <Match idRef="Keywords_czech_republic_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="f03f6-252">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="f03f6-252">Keywords</span></span>

#### <a name="keywordsczechrepubliceutaxfilenumber"></a><span data-ttu-id="f03f6-253">Keywords_czech_republic_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="f03f6-253">Keywords_czech_republic_eu_tax_file_number</span></span>

<span data-ttu-id="f03f6-254">codice fiscale</span><span class="sxs-lookup"><span data-stu-id="f03f6-254">tax number</span></span>
  
<span data-ttu-id="f03f6-255">imposte</span><span class="sxs-lookup"><span data-stu-id="f03f6-255">tax</span></span>
  
<span data-ttu-id="f03f6-256">tax id</span><span class="sxs-lookup"><span data-stu-id="f03f6-256">tax id</span></span>
  
<span data-ttu-id="f03f6-257">numero personale</span><span class="sxs-lookup"><span data-stu-id="f03f6-257">personal number</span></span>
  
<span data-ttu-id="f03f6-258">daňové číslo</span><span class="sxs-lookup"><span data-stu-id="f03f6-258">daňové číslo</span></span>
  
<span data-ttu-id="f03f6-259">osobní číslo</span><span class="sxs-lookup"><span data-stu-id="f03f6-259">osobní číslo</span></span>
  
## <a name="denmark"></a><span data-ttu-id="f03f6-260">Danimarca</span><span class="sxs-lookup"><span data-stu-id="f03f6-260">Denmark</span></span>

### <a name="format"></a><span data-ttu-id="f03f6-261">Formato</span><span class="sxs-lookup"><span data-stu-id="f03f6-261">Format</span></span>

<span data-ttu-id="f03f6-262">Dieci cifre contenenti un segno meno</span><span class="sxs-lookup"><span data-stu-id="f03f6-262">Ten digits containing a hyphen</span></span>
  
### <a name="pattern"></a><span data-ttu-id="f03f6-263">Modello</span><span class="sxs-lookup"><span data-stu-id="f03f6-263">Pattern</span></span>

<span data-ttu-id="f03f6-264">Dieci cifre contenenti un segno meno:</span><span class="sxs-lookup"><span data-stu-id="f03f6-264">Ten digits containing a hyphenl:</span></span>
  
-  <span data-ttu-id="f03f6-265">Sei cifre che corrispondono alla data di nascita (GGMMAA)</span><span class="sxs-lookup"><span data-stu-id="f03f6-265">Six digits that correspond to the birth date (DDMMYY)</span></span> 
    
- <span data-ttu-id="f03f6-266">Una lineetta</span><span class="sxs-lookup"><span data-stu-id="f03f6-266">A hyphen</span></span>
    
- <span data-ttu-id="f03f6-267">Quattro cifre che corrispondono a un numero di sequenza in cui la prima cifra corrisponde al secolo di nascita e l'ultima cifra corrisponde al sesso dell'individuo (dispari per il maschio e anche per le femmine)</span><span class="sxs-lookup"><span data-stu-id="f03f6-267">Four digits that correspond to a sequence number where the first digit corresponds to the century of birth and the last digit corresponds to the individual's gender (odd for male and even for female)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="f03f6-268">Checksum</span><span class="sxs-lookup"><span data-stu-id="f03f6-268">Checksum</span></span>

<span data-ttu-id="f03f6-269">Sì</span><span class="sxs-lookup"><span data-stu-id="f03f6-269">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="f03f6-270">Definizione</span><span class="sxs-lookup"><span data-stu-id="f03f6-270">Definition</span></span>

<span data-ttu-id="f03f6-271">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="f03f6-271">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="f03f6-272">La funzione `Func_denmark_eu_tax_file_number` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="f03f6-272">The function  `Func_denmark_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="f03f6-273">Viene trovata una `Keywords_denmark_eu_tax_file_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="f03f6-273">A keyword from  `Keywords_denmark_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="f03f6-274">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="f03f6-274">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="f03f6-275">La funzione `Func_denmark_eu_tax_file_number` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="f03f6-275">The function  `Func_denmark_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="f03f6-276">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="f03f6-276">Keywords</span></span>

#### <a name="keywordsdenmarkeutaxfilenumber"></a><span data-ttu-id="f03f6-277">Keywords_denmark_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="f03f6-277">Keywords_denmark_eu_tax_file_number</span></span>

<span data-ttu-id="f03f6-278">codice fiscale</span><span class="sxs-lookup"><span data-stu-id="f03f6-278">tax number</span></span>
  
<span data-ttu-id="f03f6-279">imposte</span><span class="sxs-lookup"><span data-stu-id="f03f6-279">tax</span></span>
  
<span data-ttu-id="f03f6-280">tax id</span><span class="sxs-lookup"><span data-stu-id="f03f6-280">tax id</span></span>
  
<span data-ttu-id="f03f6-281">numero CPR</span><span class="sxs-lookup"><span data-stu-id="f03f6-281">cpr number</span></span>
  
<span data-ttu-id="f03f6-282">CPR</span><span class="sxs-lookup"><span data-stu-id="f03f6-282">cpr#</span></span>
  
<span data-ttu-id="f03f6-283">Nummer di pattinaggio</span><span class="sxs-lookup"><span data-stu-id="f03f6-283">skat nummer</span></span>
  
<span data-ttu-id="f03f6-284">ID pattina</span><span class="sxs-lookup"><span data-stu-id="f03f6-284">skat id</span></span>
  
## <a name="estonia"></a><span data-ttu-id="f03f6-285">Estonia</span><span class="sxs-lookup"><span data-stu-id="f03f6-285">Estonia</span></span>

### <a name="format"></a><span data-ttu-id="f03f6-286">Formato</span><span class="sxs-lookup"><span data-stu-id="f03f6-286">Format</span></span>

<span data-ttu-id="f03f6-287">11 cifre senza spazi o delimitatori</span><span class="sxs-lookup"><span data-stu-id="f03f6-287">11 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="f03f6-288">Modello</span><span class="sxs-lookup"><span data-stu-id="f03f6-288">Pattern</span></span>

<span data-ttu-id="f03f6-289">11 cifre:</span><span class="sxs-lookup"><span data-stu-id="f03f6-289">11 digits:</span></span>
  
-  <span data-ttu-id="f03f6-290">Una cifra che corrisponde al sesso e al secolo del parto, in cui un numero dispari indica il maschio e il numero pari indica la femmina come segue: 1,2 per il XIX secolo; 3,4 per il XX secolo; e 5,6 per il XXI secolo</span><span class="sxs-lookup"><span data-stu-id="f03f6-290">One digit that corresponds to gender and century of birth where an odd number indicates male and the even number indicates female as follows: 1, 2 for the 19th century; 3, 4 for the 20th century; and 5, 6 for the 21st century</span></span> 
    
- <span data-ttu-id="f03f6-291">Sei cifre che corrispondono alla data di nascita (AAMMGG)</span><span class="sxs-lookup"><span data-stu-id="f03f6-291">Six digits that correspond to birth date (YYMMDD)</span></span>
    
- <span data-ttu-id="f03f6-292">Tre cifre che corrispondono a un numero di serie che separa le persone nate nella stessa data</span><span class="sxs-lookup"><span data-stu-id="f03f6-292">Three digits that correspond to a serial number separating persons born on the same date</span></span>
    
- <span data-ttu-id="f03f6-293">Una cifra di controllo</span><span class="sxs-lookup"><span data-stu-id="f03f6-293">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="f03f6-294">Checksum</span><span class="sxs-lookup"><span data-stu-id="f03f6-294">Checksum</span></span>

<span data-ttu-id="f03f6-295">Sì</span><span class="sxs-lookup"><span data-stu-id="f03f6-295">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="f03f6-296">Definizione</span><span class="sxs-lookup"><span data-stu-id="f03f6-296">Definition</span></span>

<span data-ttu-id="f03f6-297">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="f03f6-297">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="f03f6-298">La funzione `Func_estonia_eu_tax_file_number` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="f03f6-298">The function  `Func_estonia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="f03f6-299">Viene trovata una `Keywords_estonia_eu_tax_file_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="f03f6-299">A keyword from  `Keywords_estonia_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="f03f6-300">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="f03f6-300">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="f03f6-301">La funzione `Func_estonia_eu_tax_file_number` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="f03f6-301">The function  `Func_estonia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="f03f6-302">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="f03f6-302">Keywords</span></span>

#### <a name="keywordsestoniaeutaxfilenumber"></a><span data-ttu-id="f03f6-303">Keywords_estonia_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="f03f6-303">Keywords_estonia_eu_tax_file_number</span></span>

<span data-ttu-id="f03f6-304">codice fiscale</span><span class="sxs-lookup"><span data-stu-id="f03f6-304">tax number</span></span>
  
<span data-ttu-id="f03f6-305">imposte</span><span class="sxs-lookup"><span data-stu-id="f03f6-305">tax</span></span>
  
<span data-ttu-id="f03f6-306">tax id</span><span class="sxs-lookup"><span data-stu-id="f03f6-306">tax id</span></span>
  
<span data-ttu-id="f03f6-307">codice personale</span><span class="sxs-lookup"><span data-stu-id="f03f6-307">personal code</span></span>
  
<span data-ttu-id="f03f6-308">maksunumber</span><span class="sxs-lookup"><span data-stu-id="f03f6-308">maksunumber</span></span>
  
<span data-ttu-id="f03f6-309">ID maksu</span><span class="sxs-lookup"><span data-stu-id="f03f6-309">maksu id</span></span>
  
<span data-ttu-id="f03f6-310">isikukood</span><span class="sxs-lookup"><span data-stu-id="f03f6-310">isikukood</span></span>
  
## <a name="finland"></a><span data-ttu-id="f03f6-311">Finlandia</span><span class="sxs-lookup"><span data-stu-id="f03f6-311">Finland</span></span>

### <a name="format"></a><span data-ttu-id="f03f6-312">Formato</span><span class="sxs-lookup"><span data-stu-id="f03f6-312">Format</span></span>

<span data-ttu-id="f03f6-313">Una combinazione di 11 caratteri di cifre, lettere e segno più e meno</span><span class="sxs-lookup"><span data-stu-id="f03f6-313">An 11-character combination of digits, letters, and plus and minus sign</span></span>
  
### <a name="pattern"></a><span data-ttu-id="f03f6-314">Modello</span><span class="sxs-lookup"><span data-stu-id="f03f6-314">Pattern</span></span>

<span data-ttu-id="f03f6-315">Una combinazione di 11 caratteri di cifre, lettere e segno più e meno:</span><span class="sxs-lookup"><span data-stu-id="f03f6-315">An 11-character combination of digits, letters, and plus and minus sign:</span></span>
  
- <span data-ttu-id="f03f6-316">Sei cifre</span><span class="sxs-lookup"><span data-stu-id="f03f6-316">Six digits</span></span>
    
- <span data-ttu-id="f03f6-317">Uno dei seguenti: un segno più, un segno di sottrazione o la lettera "A" (senza distinzione tra maiuscole/minuscole), in cui il segno più significa Nato tra 1800-1899, il segno meno significa Nato tra 1900-1999 e "A" significa Nato 2000 e dopo</span><span class="sxs-lookup"><span data-stu-id="f03f6-317">One of the following: a plus sign, a minus sign, or the letter "A" (not case sensitive) where the plus sign means born between 1800-1899, the minus sign means born between 1900-1999, and "A" means born 2000 and after</span></span>
    
- <span data-ttu-id="f03f6-318">Tre cifre</span><span class="sxs-lookup"><span data-stu-id="f03f6-318">Three digits</span></span>
    
- <span data-ttu-id="f03f6-319">Una lettera o un numero</span><span class="sxs-lookup"><span data-stu-id="f03f6-319">One letter or one number</span></span>
    
### <a name="checksum"></a><span data-ttu-id="f03f6-320">Checksum</span><span class="sxs-lookup"><span data-stu-id="f03f6-320">Checksum</span></span>

<span data-ttu-id="f03f6-321">Sì</span><span class="sxs-lookup"><span data-stu-id="f03f6-321">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="f03f6-322">Definizione</span><span class="sxs-lookup"><span data-stu-id="f03f6-322">Definition</span></span>

<span data-ttu-id="f03f6-323">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="f03f6-323">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="f03f6-324">La funzione `Func_finland_eu_tax_file_number` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="f03f6-324">The function  `Func_finland_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="f03f6-325">Viene trovata una `Keywords_finland_eu_tax_file_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="f03f6-325">A keyword from  `Keywords_finland_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="f03f6-326">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="f03f6-326">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="f03f6-327">La funzione `Func_finland_eu_tax_file_number` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="f03f6-327">The function  `Func_finland_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="f03f6-328">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="f03f6-328">Keywords</span></span>

#### <a name="keywordsfinlandeutaxfilenumber"></a><span data-ttu-id="f03f6-329">Keywords_finland_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="f03f6-329">Keywords_finland_eu_tax_file_number</span></span>

<span data-ttu-id="f03f6-330">identification number</span><span class="sxs-lookup"><span data-stu-id="f03f6-330">identification number</span></span>
  
<span data-ttu-id="f03f6-331">ID personale</span><span class="sxs-lookup"><span data-stu-id="f03f6-331">personal id</span></span>
  
<span data-ttu-id="f03f6-332">numero di identità</span><span class="sxs-lookup"><span data-stu-id="f03f6-332">identity number</span></span>
  
<span data-ttu-id="f03f6-333">numero di identificazione nazionale finlandese</span><span class="sxs-lookup"><span data-stu-id="f03f6-333">finnish national id number</span></span>
  
<span data-ttu-id="f03f6-334">personalidnumber#</span><span class="sxs-lookup"><span data-stu-id="f03f6-334">personalidnumber#</span></span>
  
<span data-ttu-id="f03f6-335">national identification number</span><span class="sxs-lookup"><span data-stu-id="f03f6-335">national identification number</span></span>
  
<span data-ttu-id="f03f6-336">numero ID</span><span class="sxs-lookup"><span data-stu-id="f03f6-336">id number</span></span>
  
<span data-ttu-id="f03f6-337">ID nazionale No.</span><span class="sxs-lookup"><span data-stu-id="f03f6-337">national id no.</span></span>
  
<span data-ttu-id="f03f6-338">numero ID nazionale</span><span class="sxs-lookup"><span data-stu-id="f03f6-338">national id number</span></span>
  
<span data-ttu-id="f03f6-339">ID No</span><span class="sxs-lookup"><span data-stu-id="f03f6-339">id no</span></span>
  
<span data-ttu-id="f03f6-340">tunnistenumero</span><span class="sxs-lookup"><span data-stu-id="f03f6-340">tunnistenumero</span></span>
  
<span data-ttu-id="f03f6-341">henkilötunnus</span><span class="sxs-lookup"><span data-stu-id="f03f6-341">henkilötunnus</span></span>
  
<span data-ttu-id="f03f6-342">yksilöllinen henkilökohtainen tunnistenumero</span><span class="sxs-lookup"><span data-stu-id="f03f6-342">yksilöllinen henkilökohtainen tunnistenumero</span></span>
  
<span data-ttu-id="f03f6-343">ainutlaatuinen henkilökohtainen tunnus</span><span class="sxs-lookup"><span data-stu-id="f03f6-343">ainutlaatuinen henkilökohtainen tunnus</span></span>
  
<span data-ttu-id="f03f6-344">numero identiteetti</span><span class="sxs-lookup"><span data-stu-id="f03f6-344">identiteetti numero</span></span>
  
<span data-ttu-id="f03f6-345">Suomen Kansallinen henkilötunnus</span><span class="sxs-lookup"><span data-stu-id="f03f6-345">suomen kansallinen henkilötunnus</span></span>
  
<span data-ttu-id="f03f6-346">henkilötunnusnumero#</span><span class="sxs-lookup"><span data-stu-id="f03f6-346">henkilötunnusnumero#</span></span>
  
<span data-ttu-id="f03f6-347">kansallisen tunnistenumero</span><span class="sxs-lookup"><span data-stu-id="f03f6-347">kansallisen tunnistenumero</span></span>
  
<span data-ttu-id="f03f6-348">tunnusnumero</span><span class="sxs-lookup"><span data-stu-id="f03f6-348">tunnusnumero</span></span>
  
<span data-ttu-id="f03f6-349">Kansallinen tunnus numero</span><span class="sxs-lookup"><span data-stu-id="f03f6-349">kansallinen tunnus numero</span></span>
  
## <a name="france"></a><span data-ttu-id="f03f6-350">Francia</span><span class="sxs-lookup"><span data-stu-id="f03f6-350">France</span></span>

### <a name="format"></a><span data-ttu-id="f03f6-351">Formato</span><span class="sxs-lookup"><span data-stu-id="f03f6-351">Format</span></span>

<span data-ttu-id="f03f6-352">13 cifre per gli utenti e nove cifre per le entità</span><span class="sxs-lookup"><span data-stu-id="f03f6-352">13 digits for individuals and nine digits for entities</span></span>
  
### <a name="pattern"></a><span data-ttu-id="f03f6-353">Modello</span><span class="sxs-lookup"><span data-stu-id="f03f6-353">Pattern</span></span>

<span data-ttu-id="f03f6-354">13 cifre per gli utenti:</span><span class="sxs-lookup"><span data-stu-id="f03f6-354">13 digits for individuals:</span></span>
  
- <span data-ttu-id="f03f6-355">Una cifra che deve essere 0, 1, 2 o 3</span><span class="sxs-lookup"><span data-stu-id="f03f6-355">One digit that must be 0, 1, 2, or 3</span></span>
    
- <span data-ttu-id="f03f6-356">12 cifre</span><span class="sxs-lookup"><span data-stu-id="f03f6-356">12 digits</span></span>
    
<span data-ttu-id="f03f6-357">Nove cifre per le entità</span><span class="sxs-lookup"><span data-stu-id="f03f6-357">Nine digits for entities</span></span>
  
### <a name="checksum"></a><span data-ttu-id="f03f6-358">Checksum</span><span class="sxs-lookup"><span data-stu-id="f03f6-358">Checksum</span></span>

<span data-ttu-id="f03f6-359">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="f03f6-359">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="f03f6-360">Definizione</span><span class="sxs-lookup"><span data-stu-id="f03f6-360">Definition</span></span>

<span data-ttu-id="f03f6-361">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="f03f6-361">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="f03f6-362">La funzione `Func_france_eu_tax_file_number` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="f03f6-362">The function  `Func_france_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="f03f6-363">Viene trovata una `Keywords_france_eu_tax_file_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="f03f6-363">A keyword from  `Keywords_france_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="f03f6-364">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="f03f6-364">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="f03f6-365">La funzione `Func_france_eu_tax_file_number` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="f03f6-365">The function  `Func_france_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="f03f6-366">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="f03f6-366">Keywords</span></span>

#### <a name="keywordsfranceeutaxfilenumber"></a><span data-ttu-id="f03f6-367">Keywords_france_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="f03f6-367">Keywords_france_eu_tax_file_number</span></span>

<span data-ttu-id="f03f6-368">codice di identificazione fiscale</span><span class="sxs-lookup"><span data-stu-id="f03f6-368">tax identification number</span></span>
  
<span data-ttu-id="f03f6-369">codice fiscale</span><span class="sxs-lookup"><span data-stu-id="f03f6-369">tax number</span></span>
  
<span data-ttu-id="f03f6-370">tax id</span><span class="sxs-lookup"><span data-stu-id="f03f6-370">tax id</span></span>
  
<span data-ttu-id="f03f6-371">numéro d'identification fiscale</span><span class="sxs-lookup"><span data-stu-id="f03f6-371">numéro d'identification fiscale</span></span>
  
## <a name="germany"></a><span data-ttu-id="f03f6-372">Germania</span><span class="sxs-lookup"><span data-stu-id="f03f6-372">Germany</span></span>

### <a name="format"></a><span data-ttu-id="f03f6-373">Formato</span><span class="sxs-lookup"><span data-stu-id="f03f6-373">Format</span></span>

<span data-ttu-id="f03f6-374">11 cifre senza spazi e delimitatori</span><span class="sxs-lookup"><span data-stu-id="f03f6-374">11 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="f03f6-375">Modello</span><span class="sxs-lookup"><span data-stu-id="f03f6-375">Pattern</span></span>

<span data-ttu-id="f03f6-376">11 cifre:</span><span class="sxs-lookup"><span data-stu-id="f03f6-376">11 digits :</span></span>
  
-  <span data-ttu-id="f03f6-377">Dieci cifre</span><span class="sxs-lookup"><span data-stu-id="f03f6-377">Ten digits</span></span> 
    
- <span data-ttu-id="f03f6-378">Una cifra di controllo</span><span class="sxs-lookup"><span data-stu-id="f03f6-378">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="f03f6-379">Checksum</span><span class="sxs-lookup"><span data-stu-id="f03f6-379">Checksum</span></span>

<span data-ttu-id="f03f6-380">Sì</span><span class="sxs-lookup"><span data-stu-id="f03f6-380">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="f03f6-381">Definizione</span><span class="sxs-lookup"><span data-stu-id="f03f6-381">Definition</span></span>

<span data-ttu-id="f03f6-382">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="f03f6-382">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="f03f6-383">La funzione `Func_germany_eu_tax_file_number` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="f03f6-383">The function  `Func_germany_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="f03f6-384">Viene trovata una `Keywords_germany_eu_tax_file_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="f03f6-384">A keyword from  `Keywords_germany_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="f03f6-385">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="f03f6-385">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="f03f6-386">La funzione `Func_germany_eu_tax_file_number` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="f03f6-386">The function  `Func_germany_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="f03f6-387">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="f03f6-387">Keywords</span></span>

#### <a name="keywordsgermanyeutaxfilenumber"></a><span data-ttu-id="f03f6-388">Keywords_germany_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="f03f6-388">Keywords_germany_eu_tax_file_number</span></span>

<span data-ttu-id="f03f6-389">codice fiscale</span><span class="sxs-lookup"><span data-stu-id="f03f6-389">tax number</span></span>
  
<span data-ttu-id="f03f6-390">tassa no.</span><span class="sxs-lookup"><span data-stu-id="f03f6-390">tax no.</span></span>
  
<span data-ttu-id="f03f6-391">taxno#</span><span class="sxs-lookup"><span data-stu-id="f03f6-391">taxno#</span></span>
  
<span data-ttu-id="f03f6-392">taxnumber#</span><span class="sxs-lookup"><span data-stu-id="f03f6-392">taxnumber#</span></span>
  
<span data-ttu-id="f03f6-393">taxnumber</span><span class="sxs-lookup"><span data-stu-id="f03f6-393">taxnumber</span></span>
  
<span data-ttu-id="f03f6-394">tax id</span><span class="sxs-lookup"><span data-stu-id="f03f6-394">tax id</span></span>
  
<span data-ttu-id="f03f6-395">taxid #</span><span class="sxs-lookup"><span data-stu-id="f03f6-395">taxid#</span></span>
  
<span data-ttu-id="f03f6-396">codice di identificazione fiscale</span><span class="sxs-lookup"><span data-stu-id="f03f6-396">tax identification number</span></span>
  
<span data-ttu-id="f03f6-397">codice fiscale n.</span><span class="sxs-lookup"><span data-stu-id="f03f6-397">tax identification no.</span></span>
  
<span data-ttu-id="f03f6-398">steuernummer</span><span class="sxs-lookup"><span data-stu-id="f03f6-398">steuernummer</span></span>
  
<span data-ttu-id="f03f6-399">ID Steuer</span><span class="sxs-lookup"><span data-stu-id="f03f6-399">steuer id</span></span>
  
<span data-ttu-id="f03f6-400">steueridentifikationsnummer</span><span class="sxs-lookup"><span data-stu-id="f03f6-400">steueridentifikationsnummer</span></span>
  
## <a name="greece"></a><span data-ttu-id="f03f6-401">Grecia</span><span class="sxs-lookup"><span data-stu-id="f03f6-401">Greece</span></span>

### <a name="format"></a><span data-ttu-id="f03f6-402">Formato</span><span class="sxs-lookup"><span data-stu-id="f03f6-402">Format</span></span>

<span data-ttu-id="f03f6-403">Nove cifre senza spazi e delimitatori</span><span class="sxs-lookup"><span data-stu-id="f03f6-403">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="f03f6-404">Modello</span><span class="sxs-lookup"><span data-stu-id="f03f6-404">Pattern</span></span>

<span data-ttu-id="f03f6-405">9 cifre</span><span class="sxs-lookup"><span data-stu-id="f03f6-405">Nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="f03f6-406">Checksum</span><span class="sxs-lookup"><span data-stu-id="f03f6-406">Checksum</span></span>

<span data-ttu-id="f03f6-407">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="f03f6-407">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="f03f6-408">Definizione</span><span class="sxs-lookup"><span data-stu-id="f03f6-408">Definition</span></span>

<span data-ttu-id="f03f6-409">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="f03f6-409">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="f03f6-410">L'espressione `Regex_greece_eu_tax_file_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="f03f6-410">The regular expression  `Regex_greece_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="f03f6-411">Viene trovata una `Keywords_greece_eu_tax_file_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="f03f6-411">A keyword from  `Keywords_greece_eu_tax_file_number` is found.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_greece_eu_tax_file_number" />
          <Match idRef="Keywords_greece_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="f03f6-412">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="f03f6-412">Keywords</span></span>

#### <a name="keywordsgreeceeutaxfilenumber"></a><span data-ttu-id="f03f6-413">Keywords_greece_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="f03f6-413">Keywords_greece_eu_tax_file_number</span></span>

<span data-ttu-id="f03f6-414">AFM</span><span class="sxs-lookup"><span data-stu-id="f03f6-414">afm</span></span>
  
<span data-ttu-id="f03f6-415">latta</span><span class="sxs-lookup"><span data-stu-id="f03f6-415">tin</span></span>
  
<span data-ttu-id="f03f6-416">ID IVA No.</span><span class="sxs-lookup"><span data-stu-id="f03f6-416">tax id no.</span></span>
  
<span data-ttu-id="f03f6-417">ID IVA No</span><span class="sxs-lookup"><span data-stu-id="f03f6-417">tax id no</span></span>
  
<span data-ttu-id="f03f6-418">codice di identificazione fiscale</span><span class="sxs-lookup"><span data-stu-id="f03f6-418">tax identification number</span></span>
  
<span data-ttu-id="f03f6-419">numero del registro di sistema fiscale</span><span class="sxs-lookup"><span data-stu-id="f03f6-419">tax registry number</span></span>
  
<span data-ttu-id="f03f6-420">Registro fiscale No.</span><span class="sxs-lookup"><span data-stu-id="f03f6-420">tax registry no.</span></span>
  
<span data-ttu-id="f03f6-421">AFM</span><span class="sxs-lookup"><span data-stu-id="f03f6-421">afm#</span></span>
  
<span data-ttu-id="f03f6-422">latta</span><span class="sxs-lookup"><span data-stu-id="f03f6-422">tin#</span></span>
  
<span data-ttu-id="f03f6-423">taxidno#</span><span class="sxs-lookup"><span data-stu-id="f03f6-423">taxidno#</span></span>
  
<span data-ttu-id="f03f6-424">taxregistryno#</span><span class="sxs-lookup"><span data-stu-id="f03f6-424">taxregistryno#</span></span>
  
<span data-ttu-id="f03f6-425">αριθμός φορολογικού μητρώου</span><span class="sxs-lookup"><span data-stu-id="f03f6-425">αριθμός φορολογικού μητρώου</span></span>
  
<span data-ttu-id="f03f6-426">aφμ</span><span class="sxs-lookup"><span data-stu-id="f03f6-426">aφμ</span></span>
  
<span data-ttu-id="f03f6-427">aφμ αριθμός</span><span class="sxs-lookup"><span data-stu-id="f03f6-427">aφμ αριθμός</span></span>
  
<span data-ttu-id="f03f6-428">φορολογικού μητρώου νο.</span><span class="sxs-lookup"><span data-stu-id="f03f6-428">φορολογικού μητρώου νο.</span></span>
  
<span data-ttu-id="f03f6-429">τον αριθμό φορολογικού μητρώου</span><span class="sxs-lookup"><span data-stu-id="f03f6-429">τον αριθμό φορολογικού μητρώου</span></span>
  
## <a name="hungary"></a><span data-ttu-id="f03f6-430">Ungheria</span><span class="sxs-lookup"><span data-stu-id="f03f6-430">Hungary</span></span>

### <a name="format"></a><span data-ttu-id="f03f6-431">Formato</span><span class="sxs-lookup"><span data-stu-id="f03f6-431">Format</span></span>

<span data-ttu-id="f03f6-432">Dieci cifre senza spazi o delimitatori</span><span class="sxs-lookup"><span data-stu-id="f03f6-432">Ten digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="f03f6-433">Modello</span><span class="sxs-lookup"><span data-stu-id="f03f6-433">Pattern</span></span>

<span data-ttu-id="f03f6-434">Dieci cifre:</span><span class="sxs-lookup"><span data-stu-id="f03f6-434">Ten digits:</span></span>
  
-  <span data-ttu-id="f03f6-435">Una cifra che deve essere "8"</span><span class="sxs-lookup"><span data-stu-id="f03f6-435">One digit that must be "8"</span></span> 
    
- <span data-ttu-id="f03f6-436">Cinque cifre che corrispondono al numero di giorni compresi tra la data 01/01/1867 e la data di nascita dell'individuo</span><span class="sxs-lookup"><span data-stu-id="f03f6-436">Five digits that correspond to the number of days between the date 01/01/1867 and the date of the birth of the individual</span></span>
    
- <span data-ttu-id="f03f6-437">Tre cifre che corrispondono al numero generato dalla possibilità di distinguere gli individui nati nello stesso giorno</span><span class="sxs-lookup"><span data-stu-id="f03f6-437">Three digits that correspond to the number generated by chance to differentiate individuals born on the same day</span></span>
    
- <span data-ttu-id="f03f6-438">Una cifra di controllo</span><span class="sxs-lookup"><span data-stu-id="f03f6-438">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="f03f6-439">Checksum</span><span class="sxs-lookup"><span data-stu-id="f03f6-439">Checksum</span></span>

<span data-ttu-id="f03f6-440">Sì</span><span class="sxs-lookup"><span data-stu-id="f03f6-440">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="f03f6-441">Definizione</span><span class="sxs-lookup"><span data-stu-id="f03f6-441">Definition</span></span>

<span data-ttu-id="f03f6-442">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="f03f6-442">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="f03f6-443">La funzione `Func_hungary_eu_tax_file_number` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="f03f6-443">The function  `Func_hungary_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="f03f6-444">Viene trovata una `Keywords_hungary_eu_tax_file_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="f03f6-444">A keyword from  `Keywords_hungary_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="f03f6-445">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="f03f6-445">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="f03f6-446">La funzione `Func_hungary_eu_tax_file_number` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="f03f6-446">The function  `Func_hungary_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="f03f6-447">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="f03f6-447">Keywords</span></span>

#### <a name="keywordshungaryeutaxfilenumber"></a><span data-ttu-id="f03f6-448">Keywords_hungary_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="f03f6-448">Keywords_hungary_eu_tax_file_number</span></span>

<span data-ttu-id="f03f6-449">numero di identificazione fiscale ungherese</span><span class="sxs-lookup"><span data-stu-id="f03f6-449">hungarian tax identification number</span></span>
  
<span data-ttu-id="f03f6-450">Tin ungherese</span><span class="sxs-lookup"><span data-stu-id="f03f6-450">hungarian tin</span></span>
  
<span data-ttu-id="f03f6-451">numero di ID fiscale</span><span class="sxs-lookup"><span data-stu-id="f03f6-451">tax id number</span></span>
  
<span data-ttu-id="f03f6-452">numero di partita IVA</span><span class="sxs-lookup"><span data-stu-id="f03f6-452">vat number</span></span>
  
<span data-ttu-id="f03f6-453">autorità tributaria No</span><span class="sxs-lookup"><span data-stu-id="f03f6-453">tax authority no</span></span>
  
<span data-ttu-id="f03f6-454">numero dell'identità fiscale dell'ID fiscale</span><span class="sxs-lookup"><span data-stu-id="f03f6-454">tax id tax identity number</span></span>
  
<span data-ttu-id="f03f6-455">taxidnumber#</span><span class="sxs-lookup"><span data-stu-id="f03f6-455">taxidnumber#</span></span>
  
<span data-ttu-id="f03f6-456">latta</span><span class="sxs-lookup"><span data-stu-id="f03f6-456">tin#</span></span>
  
<span data-ttu-id="f03f6-457">hungatiantin#</span><span class="sxs-lookup"><span data-stu-id="f03f6-457">hungatiantin#</span></span>
  
<span data-ttu-id="f03f6-458">identificazione fiscale No</span><span class="sxs-lookup"><span data-stu-id="f03f6-458">tax identification no</span></span>
  
<span data-ttu-id="f03f6-459">taxidno#</span><span class="sxs-lookup"><span data-stu-id="f03f6-459">taxidno#</span></span>
  
<span data-ttu-id="f03f6-460">adóazonosító szám</span><span class="sxs-lookup"><span data-stu-id="f03f6-460">adóazonosító szám</span></span>
  
<span data-ttu-id="f03f6-461">adószám</span><span class="sxs-lookup"><span data-stu-id="f03f6-461">adószám</span></span>
  
<span data-ttu-id="f03f6-462">adóhatóság szám</span><span class="sxs-lookup"><span data-stu-id="f03f6-462">adóhatóság szám</span></span>
  
## <a name="ireland"></a><span data-ttu-id="f03f6-463">Irlanda</span><span class="sxs-lookup"><span data-stu-id="f03f6-463">Ireland</span></span>

### <a name="format"></a><span data-ttu-id="f03f6-464">Formato</span><span class="sxs-lookup"><span data-stu-id="f03f6-464">Format</span></span>

<span data-ttu-id="f03f6-465">Sette cifre seguite da una lettera senza spazi o delimitatori</span><span class="sxs-lookup"><span data-stu-id="f03f6-465">Seven digits followed by a letter with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="f03f6-466">Modello</span><span class="sxs-lookup"><span data-stu-id="f03f6-466">Pattern</span></span>

<span data-ttu-id="f03f6-467">Sette cifre seguite da una lettera:</span><span class="sxs-lookup"><span data-stu-id="f03f6-467">Seven digits followed by a letter:</span></span>
  
-  <span data-ttu-id="f03f6-468">Sette cifre</span><span class="sxs-lookup"><span data-stu-id="f03f6-468">Seven digits</span></span> 
    
- <span data-ttu-id="f03f6-469">Una lettera (senza distinzione tra maiuscole e minuscole)</span><span class="sxs-lookup"><span data-stu-id="f03f6-469">One letter (not case-sensitive)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="f03f6-470">Checksum</span><span class="sxs-lookup"><span data-stu-id="f03f6-470">Checksum</span></span>

<span data-ttu-id="f03f6-471">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="f03f6-471">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="f03f6-472">Definizione</span><span class="sxs-lookup"><span data-stu-id="f03f6-472">Definition</span></span>

<span data-ttu-id="f03f6-473">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="f03f6-473">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="f03f6-474">La funzione `Func_ireland_eu_tax_file_number` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="f03f6-474">The function  `Func_ireland_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="f03f6-475">Viene trovata una `Keywords_ireland_eu_tax_file_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="f03f6-475">A keyword from  `Keywords_ireland_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="f03f6-476">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="f03f6-476">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="f03f6-477">La funzione `Func_ireland_eu_tax_file_number` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="f03f6-477">The function  `Func_ireland_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="f03f6-478">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="f03f6-478">Keywords</span></span>

#### <a name="keywordsirelandeutaxfilenumber"></a><span data-ttu-id="f03f6-479">Keywords_ireland_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="f03f6-479">Keywords_ireland_eu_tax_file_number</span></span>

<span data-ttu-id="f03f6-480">servizio pubblico no</span><span class="sxs-lookup"><span data-stu-id="f03f6-480">public service no</span></span>
  
<span data-ttu-id="f03f6-481">servizio pubblico personale No</span><span class="sxs-lookup"><span data-stu-id="f03f6-481">personal public service no</span></span>
  
<span data-ttu-id="f03f6-482">PPS No</span><span class="sxs-lookup"><span data-stu-id="f03f6-482">pps no</span></span>
  
<span data-ttu-id="f03f6-483">servizio personale No</span><span class="sxs-lookup"><span data-stu-id="f03f6-483">personal service no</span></span>
  
<span data-ttu-id="f03f6-484">servizio PPS No</span><span class="sxs-lookup"><span data-stu-id="f03f6-484">pps service no</span></span>
  
<span data-ttu-id="f03f6-485">ppsno#</span><span class="sxs-lookup"><span data-stu-id="f03f6-485">ppsno#</span></span>
  
<span data-ttu-id="f03f6-486">Irish PPS No</span><span class="sxs-lookup"><span data-stu-id="f03f6-486">irish pps no</span></span>
  
<span data-ttu-id="f03f6-487">publicserviceno#</span><span class="sxs-lookup"><span data-stu-id="f03f6-487">publicserviceno#</span></span>
  
<span data-ttu-id="f03f6-488">numero di servizio pubblico personale</span><span class="sxs-lookup"><span data-stu-id="f03f6-488">personal public service number</span></span>
  
<span data-ttu-id="f03f6-489">uimhir phearsanta seirbhíse poiblí</span><span class="sxs-lookup"><span data-stu-id="f03f6-489">uimhir phearsanta seirbhíse poiblí</span></span>
  
<span data-ttu-id="f03f6-490">PPS uimh</span><span class="sxs-lookup"><span data-stu-id="f03f6-490">pps uimh</span></span>
  
<span data-ttu-id="f03f6-491">uimhir aitheantais phearsanta</span><span class="sxs-lookup"><span data-stu-id="f03f6-491">uimhir aitheantais phearsanta</span></span>
  
## <a name="italy"></a><span data-ttu-id="f03f6-492">Italia</span><span class="sxs-lookup"><span data-stu-id="f03f6-492">Italy</span></span>

### <a name="format"></a><span data-ttu-id="f03f6-493">Formato</span><span class="sxs-lookup"><span data-stu-id="f03f6-493">Format</span></span>

<span data-ttu-id="f03f6-494">16 lettere e cifre nel modello specificato</span><span class="sxs-lookup"><span data-stu-id="f03f6-494">16 letters and digits in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="f03f6-495">Modello</span><span class="sxs-lookup"><span data-stu-id="f03f6-495">Pattern</span></span>

<span data-ttu-id="f03f6-496">16 lettere e cifre:</span><span class="sxs-lookup"><span data-stu-id="f03f6-496">16 letters and digits:</span></span>
  
-  <span data-ttu-id="f03f6-497">Tre lettere che corrispondono alle prime tre consonanti del nome di famiglia</span><span class="sxs-lookup"><span data-stu-id="f03f6-497">Three letters that correspond to the first three consonants in the family name</span></span> 
    
- <span data-ttu-id="f03f6-498">Tre lettere che corrispondono alla prima, terza e quarta consonante del primo nome</span><span class="sxs-lookup"><span data-stu-id="f03f6-498">Three letters that correspond to the first, third, and fourth consonants in the first name</span></span>
    
- <span data-ttu-id="f03f6-499">Due cifre che corrispondono alle ultime cifre dell'anno di nascita</span><span class="sxs-lookup"><span data-stu-id="f03f6-499">Two digits that correspond to the last digits of the birth year</span></span>
    
- <span data-ttu-id="f03f6-500">Una cifra corrispondente al mese di nascita: le lettere vengono utilizzate in ordine alfabetico, ma vengono utilizzate solo le lettere da a a E, H, L, M, P, R e T (pertanto, gennaio è A e ottobre è R)</span><span class="sxs-lookup"><span data-stu-id="f03f6-500">One digit that corresponds to the month of birth—letters are used in alphabetical order, but only the letters A to E, H, L, M, P, R to T are used (thus, January is A and October is R)</span></span>
    
- <span data-ttu-id="f03f6-501">Due cifre che corrispondono al giorno del mese di nascita in cui 40 viene aggiunto al giorno di nascita per le femmine per differenziare dai maschi</span><span class="sxs-lookup"><span data-stu-id="f03f6-501">Two digits that correspond to the day of the month of birth where 40 is added to the day of birth for females to differentiate from males</span></span>
    
- <span data-ttu-id="f03f6-502">Quattro cifre che corrispondono a un codice di area specifico per il comune in cui è nata la persona: vengono utilizzati codici a livello nazionale per i paesi esteri</span><span class="sxs-lookup"><span data-stu-id="f03f6-502">Four digits that correspond to an area code specific to the municipality where the person was born—country-wide codes are used for foreign countries</span></span>
    
- <span data-ttu-id="f03f6-503">Una cifra di controllo</span><span class="sxs-lookup"><span data-stu-id="f03f6-503">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="f03f6-504">Checksum</span><span class="sxs-lookup"><span data-stu-id="f03f6-504">Checksum</span></span>

<span data-ttu-id="f03f6-505">Sì</span><span class="sxs-lookup"><span data-stu-id="f03f6-505">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="f03f6-506">Definizione</span><span class="sxs-lookup"><span data-stu-id="f03f6-506">Definition</span></span>

<span data-ttu-id="f03f6-507">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="f03f6-507">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="f03f6-508">La funzione `Func_italy_eu_tax_file_number` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="f03f6-508">The function  `Func_italy_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="f03f6-509">Viene trovata una `Keywords_italy_eu_tax_file_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="f03f6-509">A keyword from  `Keywords_italy_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="f03f6-510">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="f03f6-510">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="f03f6-511">La funzione `Func_italy_eu_tax_file_number` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="f03f6-511">The function  `Func_italy_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="f03f6-512">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="f03f6-512">Keywords</span></span>

#### <a name="keywordsitalyeutaxfilenumber"></a><span data-ttu-id="f03f6-513">Keywords_italy_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="f03f6-513">Keywords_italy_eu_tax_file_number</span></span>

<span data-ttu-id="f03f6-514">codice fiscale</span><span class="sxs-lookup"><span data-stu-id="f03f6-514">tax number</span></span>
  
<span data-ttu-id="f03f6-515">tassa no.</span><span class="sxs-lookup"><span data-stu-id="f03f6-515">tax no.</span></span>
  
<span data-ttu-id="f03f6-516">taxno#</span><span class="sxs-lookup"><span data-stu-id="f03f6-516">taxno#</span></span>
  
<span data-ttu-id="f03f6-517">taxnumber#</span><span class="sxs-lookup"><span data-stu-id="f03f6-517">taxnumber#</span></span>
  
<span data-ttu-id="f03f6-518">taxnumber</span><span class="sxs-lookup"><span data-stu-id="f03f6-518">taxnumber</span></span>
  
<span data-ttu-id="f03f6-519">tax id</span><span class="sxs-lookup"><span data-stu-id="f03f6-519">tax id</span></span>
  
<span data-ttu-id="f03f6-520">taxid #</span><span class="sxs-lookup"><span data-stu-id="f03f6-520">taxid#</span></span>
  
<span data-ttu-id="f03f6-521">codice fiscale</span><span class="sxs-lookup"><span data-stu-id="f03f6-521">fiscal code</span></span>
  
<span data-ttu-id="f03f6-522">codice fiscale</span><span class="sxs-lookup"><span data-stu-id="f03f6-522">codice fiscale</span></span>
  
## <a name="latvia"></a><span data-ttu-id="f03f6-523">Lettonia</span><span class="sxs-lookup"><span data-stu-id="f03f6-523">Latvia</span></span>

### <a name="format"></a><span data-ttu-id="f03f6-524">Formato</span><span class="sxs-lookup"><span data-stu-id="f03f6-524">Format</span></span>

<span data-ttu-id="f03f6-525">11 cifre senza spazi o delimitatori</span><span class="sxs-lookup"><span data-stu-id="f03f6-525">11 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="f03f6-526">Modello</span><span class="sxs-lookup"><span data-stu-id="f03f6-526">Pattern</span></span>

<span data-ttu-id="f03f6-527">11 cifre nel modello specificato</span><span class="sxs-lookup"><span data-stu-id="f03f6-527">11 digits in the specified pattern</span></span>
  
-  <span data-ttu-id="f03f6-528">Sei cifre che corrispondono alla data di nascita (GGMMAA)</span><span class="sxs-lookup"><span data-stu-id="f03f6-528">Six digits that correspond to the date of birth (DDMMYY)</span></span> 
    
- <span data-ttu-id="f03f6-529">Una cifra che corrisponde al secolo di nascita dove "0" corrisponde al XIX secolo, "1" corrisponde al 20 ° secolo e "2" corrisponde al XXI secolo</span><span class="sxs-lookup"><span data-stu-id="f03f6-529">One digit that corresponds to the century of birth where "0" corresponds to 19th century, "1" corresponds to 20th century, and "2"corresponds to 21st century</span></span>
    
- <span data-ttu-id="f03f6-530">Quattro cifre</span><span class="sxs-lookup"><span data-stu-id="f03f6-530">Four digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="f03f6-531">Checksum</span><span class="sxs-lookup"><span data-stu-id="f03f6-531">Checksum</span></span>

<span data-ttu-id="f03f6-532">Sì</span><span class="sxs-lookup"><span data-stu-id="f03f6-532">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="f03f6-533">Definizione</span><span class="sxs-lookup"><span data-stu-id="f03f6-533">Definition</span></span>

<span data-ttu-id="f03f6-534">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="f03f6-534">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="f03f6-535">La funzione `Func_latvia_eu_tax_file_number` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="f03f6-535">The function  `Func_latvia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="f03f6-536">Viene trovata una `Keywords_latvia_eu_tax_file_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="f03f6-536">A keyword from  `Keywords_latvia_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="f03f6-537">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="f03f6-537">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="f03f6-538">La funzione `Func_latvia_eu_tax_file_number` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="f03f6-538">The function  `Func_latvia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="f03f6-539">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="f03f6-539">Keywords</span></span>

#### <a name="keywordslatviaeutaxfilenumber"></a><span data-ttu-id="f03f6-540">Keywords_latvia_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="f03f6-540">Keywords_latvia_eu_tax_file_number</span></span>

<span data-ttu-id="f03f6-541">codice fiscale</span><span class="sxs-lookup"><span data-stu-id="f03f6-541">tax number</span></span>
  
<span data-ttu-id="f03f6-542">tassa no.</span><span class="sxs-lookup"><span data-stu-id="f03f6-542">tax no.</span></span>
  
<span data-ttu-id="f03f6-543">taxno#</span><span class="sxs-lookup"><span data-stu-id="f03f6-543">taxno#</span></span>
  
<span data-ttu-id="f03f6-544">taxnumber#</span><span class="sxs-lookup"><span data-stu-id="f03f6-544">taxnumber#</span></span>
  
<span data-ttu-id="f03f6-545">taxnumber</span><span class="sxs-lookup"><span data-stu-id="f03f6-545">taxnumber</span></span>
  
<span data-ttu-id="f03f6-546">tax id</span><span class="sxs-lookup"><span data-stu-id="f03f6-546">tax id</span></span>
  
<span data-ttu-id="f03f6-547">taxid #</span><span class="sxs-lookup"><span data-stu-id="f03f6-547">taxid#</span></span>
  
<span data-ttu-id="f03f6-548">codice di identificazione fiscale</span><span class="sxs-lookup"><span data-stu-id="f03f6-548">tax identification number</span></span>
  
<span data-ttu-id="f03f6-549">codice fiscale n.</span><span class="sxs-lookup"><span data-stu-id="f03f6-549">tax identification no.</span></span>
  
<span data-ttu-id="f03f6-550">nodokļa numurs</span><span class="sxs-lookup"><span data-stu-id="f03f6-550">nodokļa numurs</span></span>
  
<span data-ttu-id="f03f6-551">nodokļu identifikācijas numurs</span><span class="sxs-lookup"><span data-stu-id="f03f6-551">nodokļu identifikācijas numurs</span></span>
  
<span data-ttu-id="f03f6-552">nodokļu identifikācija numurs</span><span class="sxs-lookup"><span data-stu-id="f03f6-552">nodokļu identifikācija numurs</span></span>
  
## <a name="lithuania"></a><span data-ttu-id="f03f6-553">Lituania</span><span class="sxs-lookup"><span data-stu-id="f03f6-553">Lithuania</span></span>

### <a name="format"></a><span data-ttu-id="f03f6-554">Formato</span><span class="sxs-lookup"><span data-stu-id="f03f6-554">Format</span></span>

<span data-ttu-id="f03f6-555">11 cifre senza spazi o delimitatori</span><span class="sxs-lookup"><span data-stu-id="f03f6-555">11 digits without spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="f03f6-556">Modello</span><span class="sxs-lookup"><span data-stu-id="f03f6-556">Pattern</span></span>

<span data-ttu-id="f03f6-557">11 cifre</span><span class="sxs-lookup"><span data-stu-id="f03f6-557">11 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="f03f6-558">Checksum</span><span class="sxs-lookup"><span data-stu-id="f03f6-558">Checksum</span></span>

<span data-ttu-id="f03f6-559">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="f03f6-559">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="f03f6-560">Definizione</span><span class="sxs-lookup"><span data-stu-id="f03f6-560">Definition</span></span>

<span data-ttu-id="f03f6-561">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="f03f6-561">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="f03f6-562">La funzione `Func_lithuania_eu_tax_file_number` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="f03f6-562">The function  `Func_lithuania_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="f03f6-563">Viene trovata una `Keywords_lithuania_eu_tax_file_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="f03f6-563">A keyword from  `Keywords_lithuania_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="f03f6-564">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="f03f6-564">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="f03f6-565">La funzione `Func_lithuania_eu_tax_file_number` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="f03f6-565">The function  `Func_lithuania_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="f03f6-566">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="f03f6-566">Keywords</span></span>

#### <a name="keywordslithuaniaeutaxfilenumber"></a><span data-ttu-id="f03f6-567">Keywords_lithuania_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="f03f6-567">Keywords_lithuania_eu_tax_file_number</span></span>

<span data-ttu-id="f03f6-568">codice fiscale</span><span class="sxs-lookup"><span data-stu-id="f03f6-568">tax number</span></span>
  
<span data-ttu-id="f03f6-569">tassa no.</span><span class="sxs-lookup"><span data-stu-id="f03f6-569">tax no.</span></span>
  
<span data-ttu-id="f03f6-570">tax no #</span><span class="sxs-lookup"><span data-stu-id="f03f6-570">tax no#</span></span>
  
<span data-ttu-id="f03f6-571">taxnumber#</span><span class="sxs-lookup"><span data-stu-id="f03f6-571">taxnumber#</span></span>
  
<span data-ttu-id="f03f6-572">taxnumber</span><span class="sxs-lookup"><span data-stu-id="f03f6-572">taxnumber</span></span>
  
<span data-ttu-id="f03f6-573">tax id</span><span class="sxs-lookup"><span data-stu-id="f03f6-573">tax id</span></span>
  
<span data-ttu-id="f03f6-574">taxid #</span><span class="sxs-lookup"><span data-stu-id="f03f6-574">taxid#</span></span>
  
<span data-ttu-id="f03f6-575">codice di identificazione fiscale</span><span class="sxs-lookup"><span data-stu-id="f03f6-575">tax identification number</span></span>
  
<span data-ttu-id="f03f6-576">codice fiscale n.</span><span class="sxs-lookup"><span data-stu-id="f03f6-576">tax identification no.</span></span>
  
<span data-ttu-id="f03f6-577">ID mokesčių</span><span class="sxs-lookup"><span data-stu-id="f03f6-577">mokesčių id</span></span>
  
<span data-ttu-id="f03f6-578">numeri mokesčių</span><span class="sxs-lookup"><span data-stu-id="f03f6-578">mokesčių numeris</span></span>
  
<span data-ttu-id="f03f6-579">mokesčių identifikavimas numeris</span><span class="sxs-lookup"><span data-stu-id="f03f6-579">mokesčių identifikavimas numeris</span></span>
  
## <a name="luxemburg"></a><span data-ttu-id="f03f6-580">Lussemburgo</span><span class="sxs-lookup"><span data-stu-id="f03f6-580">Luxemburg</span></span>

### <a name="format"></a><span data-ttu-id="f03f6-581">Formato</span><span class="sxs-lookup"><span data-stu-id="f03f6-581">Format</span></span>

<span data-ttu-id="f03f6-582">13 cifre senza spazi o delimitatori</span><span class="sxs-lookup"><span data-stu-id="f03f6-582">13 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="f03f6-583">Modello</span><span class="sxs-lookup"><span data-stu-id="f03f6-583">Pattern</span></span>

<span data-ttu-id="f03f6-584">13 cifre:</span><span class="sxs-lookup"><span data-stu-id="f03f6-584">13 digits:</span></span>
  
-  <span data-ttu-id="f03f6-585">11 cifre</span><span class="sxs-lookup"><span data-stu-id="f03f6-585">11 digits</span></span> 
    
- <span data-ttu-id="f03f6-586">Due cifre di controllo</span><span class="sxs-lookup"><span data-stu-id="f03f6-586">Two check digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="f03f6-587">Checksum</span><span class="sxs-lookup"><span data-stu-id="f03f6-587">Checksum</span></span>

<span data-ttu-id="f03f6-588">Sì</span><span class="sxs-lookup"><span data-stu-id="f03f6-588">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="f03f6-589">Definizione</span><span class="sxs-lookup"><span data-stu-id="f03f6-589">Definition</span></span>

<span data-ttu-id="f03f6-590">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="f03f6-590">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="f03f6-591">La funzione `Func_luxemburg_eu_tax_file_number` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="f03f6-591">The function  `Func_luxemburg_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="f03f6-592">Viene trovata una `Keywords_luxemburg_eu_tax_file_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="f03f6-592">A keyword from  `Keywords_luxemburg_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="f03f6-593">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="f03f6-593">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="f03f6-594">La funzione `Func_luxemburg_eu_tax_file_number` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="f03f6-594">The function  `Func_luxemburg_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="f03f6-595">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="f03f6-595">Keywords</span></span>

#### <a name="keywordsluxemburgeutaxfilenumber"></a><span data-ttu-id="f03f6-596">Keywords_luxemburg_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="f03f6-596">Keywords_luxemburg_eu_tax_file_number</span></span>

<span data-ttu-id="f03f6-597">codice fiscale</span><span class="sxs-lookup"><span data-stu-id="f03f6-597">tax number</span></span>
  
<span data-ttu-id="f03f6-598">tassa no.</span><span class="sxs-lookup"><span data-stu-id="f03f6-598">tax no.</span></span>
  
<span data-ttu-id="f03f6-599">taxno#</span><span class="sxs-lookup"><span data-stu-id="f03f6-599">taxno#</span></span>
  
<span data-ttu-id="f03f6-600">taxnumber#</span><span class="sxs-lookup"><span data-stu-id="f03f6-600">taxnumber#</span></span>
  
<span data-ttu-id="f03f6-601">taxnumber</span><span class="sxs-lookup"><span data-stu-id="f03f6-601">taxnumber</span></span>
  
<span data-ttu-id="f03f6-602">tax id</span><span class="sxs-lookup"><span data-stu-id="f03f6-602">tax id</span></span>
  
<span data-ttu-id="f03f6-603">taxid #</span><span class="sxs-lookup"><span data-stu-id="f03f6-603">taxid#</span></span>
  
<span data-ttu-id="f03f6-604">codice di identificazione fiscale</span><span class="sxs-lookup"><span data-stu-id="f03f6-604">tax identification number</span></span>
  
<span data-ttu-id="f03f6-605">codice fiscale n.</span><span class="sxs-lookup"><span data-stu-id="f03f6-605">tax identification no.</span></span>
  
<span data-ttu-id="f03f6-606">steuernummer</span><span class="sxs-lookup"><span data-stu-id="f03f6-606">steuernummer</span></span>
  
<span data-ttu-id="f03f6-607">ID Steuer</span><span class="sxs-lookup"><span data-stu-id="f03f6-607">steuer id</span></span>
  
<span data-ttu-id="f03f6-608">steueridentifikationsnummer</span><span class="sxs-lookup"><span data-stu-id="f03f6-608">steueridentifikationsnummer</span></span>
  
## <a name="malta"></a><span data-ttu-id="f03f6-609">Malta</span><span class="sxs-lookup"><span data-stu-id="f03f6-609">Malta</span></span>

### <a name="format"></a><span data-ttu-id="f03f6-610">Formato</span><span class="sxs-lookup"><span data-stu-id="f03f6-610">Format</span></span>

<span data-ttu-id="f03f6-611">Per cittadini maltesi: 7 cifre e una lettera nel modello specificato</span><span class="sxs-lookup"><span data-stu-id="f03f6-611">For Maltese nationals: 7 digits and one letter in the specified pattern</span></span>
  
<span data-ttu-id="f03f6-612">Nazionali non maltesi e soggetti maltesi: 9 cifre</span><span class="sxs-lookup"><span data-stu-id="f03f6-612">Non-Maltese nationals and Maltese entities: 9 digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="f03f6-613">Modello</span><span class="sxs-lookup"><span data-stu-id="f03f6-613">Pattern</span></span>

<span data-ttu-id="f03f6-614">Cittadini maltesi: 7 cifre e una lettera</span><span class="sxs-lookup"><span data-stu-id="f03f6-614">Maltese nationals: 7 digits and one letter</span></span>
  
-  <span data-ttu-id="f03f6-615">Sette cifre</span><span class="sxs-lookup"><span data-stu-id="f03f6-615">Seven digits</span></span> 
    
- <span data-ttu-id="f03f6-616">Una lettera (senza distinzione tra maiuscole e minuscole)</span><span class="sxs-lookup"><span data-stu-id="f03f6-616">One letter (not case-sensitive)</span></span>
    
<span data-ttu-id="f03f6-617">Nazionali non maltesi e soggetti maltesi: 9 cifre</span><span class="sxs-lookup"><span data-stu-id="f03f6-617">Non-Maltese nationals and Maltese entities: 9 digits</span></span>
  
-  <span data-ttu-id="f03f6-618">9 cifre</span><span class="sxs-lookup"><span data-stu-id="f03f6-618">Nine digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="f03f6-619">Checksum</span><span class="sxs-lookup"><span data-stu-id="f03f6-619">Checksum</span></span>

<span data-ttu-id="f03f6-620">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="f03f6-620">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="f03f6-621">Definizione</span><span class="sxs-lookup"><span data-stu-id="f03f6-621">Definition</span></span>

<span data-ttu-id="f03f6-622">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="f03f6-622">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="f03f6-623">La funzione `Func_malta_eu_tax_file_number` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="f03f6-623">The function  `Func_malta_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="f03f6-624">Viene trovata una `Keywords_malta_eu_tax_file_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="f03f6-624">A keyword from  `Keywords_malta_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="f03f6-625">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 65%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="f03f6-625">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="f03f6-626">La funzione `Func_malta_eu_tax_file_number` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="f03f6-626">The function  `Func_malta_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="f03f6-627">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="f03f6-627">Keywords</span></span>

#### <a name="keywordsmaltaeutaxfilenumber"></a><span data-ttu-id="f03f6-628">Keywords_malta_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="f03f6-628">Keywords_malta_eu_tax_file_number</span></span>

<span data-ttu-id="f03f6-629">codice fiscale</span><span class="sxs-lookup"><span data-stu-id="f03f6-629">tax number</span></span>
  
<span data-ttu-id="f03f6-630">tassa no.</span><span class="sxs-lookup"><span data-stu-id="f03f6-630">tax no.</span></span>
  
<span data-ttu-id="f03f6-631">taxno#</span><span class="sxs-lookup"><span data-stu-id="f03f6-631">taxno#</span></span>
  
<span data-ttu-id="f03f6-632">taxnumber#</span><span class="sxs-lookup"><span data-stu-id="f03f6-632">taxnumber#</span></span>
  
<span data-ttu-id="f03f6-633">taxnumber</span><span class="sxs-lookup"><span data-stu-id="f03f6-633">taxnumber</span></span>
  
<span data-ttu-id="f03f6-634">tax id</span><span class="sxs-lookup"><span data-stu-id="f03f6-634">tax id</span></span>
  
<span data-ttu-id="f03f6-635">taxid #</span><span class="sxs-lookup"><span data-stu-id="f03f6-635">taxid#</span></span>
  
<span data-ttu-id="f03f6-636">codice di identificazione fiscale</span><span class="sxs-lookup"><span data-stu-id="f03f6-636">tax identification number</span></span>
  
<span data-ttu-id="f03f6-637">codice fiscale n.</span><span class="sxs-lookup"><span data-stu-id="f03f6-637">tax identification no.</span></span>
  
<span data-ttu-id="f03f6-638">numru Tat-Taxxa</span><span class="sxs-lookup"><span data-stu-id="f03f6-638">numru tat-taxxa</span></span>
  
<span data-ttu-id="f03f6-639">ID Tat-Taxxa</span><span class="sxs-lookup"><span data-stu-id="f03f6-639">id tat-taxxa</span></span>
  
<span data-ttu-id="f03f6-640">numru ta ' identifikazzjoni Tat-Taxxa</span><span class="sxs-lookup"><span data-stu-id="f03f6-640">numru ta 'identifikazzjoni tat-taxxa</span></span>
  
## <a name="netherlands"></a><span data-ttu-id="f03f6-641">Paesi Bassi</span><span class="sxs-lookup"><span data-stu-id="f03f6-641">Netherlands</span></span>

### <a name="format"></a><span data-ttu-id="f03f6-642">Formato</span><span class="sxs-lookup"><span data-stu-id="f03f6-642">Format</span></span>

<span data-ttu-id="f03f6-643">Nove cifre senza spazi o delimitatori</span><span class="sxs-lookup"><span data-stu-id="f03f6-643">Nine digits without spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="f03f6-644">Modello</span><span class="sxs-lookup"><span data-stu-id="f03f6-644">Pattern</span></span>

<span data-ttu-id="f03f6-645">9 cifre</span><span class="sxs-lookup"><span data-stu-id="f03f6-645">Nine digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="f03f6-646">Checksum</span><span class="sxs-lookup"><span data-stu-id="f03f6-646">Checksum</span></span>

<span data-ttu-id="f03f6-647">Sì</span><span class="sxs-lookup"><span data-stu-id="f03f6-647">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="f03f6-648">Definizione</span><span class="sxs-lookup"><span data-stu-id="f03f6-648">Definition</span></span>

<span data-ttu-id="f03f6-649">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="f03f6-649">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="f03f6-650">La funzione `Func_netherlands_eu_tax_file_number` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="f03f6-650">The function  `Func_netherlands_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="f03f6-651">Viene trovata una `Keywords_netherlands_eu_tax_file_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="f03f6-651">A keyword from  `Keywords_netherlands_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="f03f6-652">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="f03f6-652">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="f03f6-653">La funzione `Func_netherlands_eu_tax_file_number` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="f03f6-653">The function  `Func_netherlands_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="f03f6-654">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="f03f6-654">Keywords</span></span>

#### <a name="keywordsnetherlandseutaxfilenumber"></a><span data-ttu-id="f03f6-655">Keywords_netherlands_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="f03f6-655">Keywords_netherlands_eu_tax_file_number</span></span>

<span data-ttu-id="f03f6-656">numero di identificazione fiscale per i Paesi Bassi</span><span class="sxs-lookup"><span data-stu-id="f03f6-656">netherlands tax identification number</span></span>
  
<span data-ttu-id="f03f6-657">identificazione fiscale per i Paesi Bassi</span><span class="sxs-lookup"><span data-stu-id="f03f6-657">netherlands tax identification</span></span>
  
<span data-ttu-id="f03f6-658">numero di identificazione fiscale per i Paesi Bassi</span><span class="sxs-lookup"><span data-stu-id="f03f6-658">netherland's tax identification number</span></span>
  
<span data-ttu-id="f03f6-659">identificazione fiscale per i Paesi Bassi</span><span class="sxs-lookup"><span data-stu-id="f03f6-659">netherland's tax identification</span></span>
  
<span data-ttu-id="f03f6-660">codice di identificazione fiscale</span><span class="sxs-lookup"><span data-stu-id="f03f6-660">tax identification number</span></span>
  
<span data-ttu-id="f03f6-661">ID delle tasse olandesi</span><span class="sxs-lookup"><span data-stu-id="f03f6-661">dutch tax id</span></span>
  
<span data-ttu-id="f03f6-662">numero di identificazione fiscale olandese</span><span class="sxs-lookup"><span data-stu-id="f03f6-662">dutch tax identification number</span></span>
  
<span data-ttu-id="f03f6-663">tax id</span><span class="sxs-lookup"><span data-stu-id="f03f6-663">tax id</span></span>
  
<span data-ttu-id="f03f6-664">ID fiscale #</span><span class="sxs-lookup"><span data-stu-id="f03f6-664">tax id#</span></span>
  
<span data-ttu-id="f03f6-665">codice fiscale</span><span class="sxs-lookup"><span data-stu-id="f03f6-665">tax number</span></span>
  
<span data-ttu-id="f03f6-666">tax no #</span><span class="sxs-lookup"><span data-stu-id="f03f6-666">tax no#</span></span>
  
<span data-ttu-id="f03f6-667">imposte</span><span class="sxs-lookup"><span data-stu-id="f03f6-667">tax#</span></span>
  
<span data-ttu-id="f03f6-668">latta</span><span class="sxs-lookup"><span data-stu-id="f03f6-668">tin</span></span>
  
<span data-ttu-id="f03f6-669">latta</span><span class="sxs-lookup"><span data-stu-id="f03f6-669">tin#</span></span>
  
<span data-ttu-id="f03f6-670">Tin olandesi</span><span class="sxs-lookup"><span data-stu-id="f03f6-670">netherlands tin</span></span>
  
<span data-ttu-id="f03f6-671">stagno degli olandesi</span><span class="sxs-lookup"><span data-stu-id="f03f6-671">netherland's tin</span></span>
  
<span data-ttu-id="f03f6-672">Nederlands identificatienummer di recente</span><span class="sxs-lookup"><span data-stu-id="f03f6-672">nederlands belasting identificatienummer</span></span>
  
<span data-ttu-id="f03f6-673">identificatienummer van delasting</span><span class="sxs-lookup"><span data-stu-id="f03f6-673">identificatienummer van belasting</span></span>
  
<span data-ttu-id="f03f6-674">identificatienummer che dura</span><span class="sxs-lookup"><span data-stu-id="f03f6-674">identificatienummer belasting</span></span>
  
<span data-ttu-id="f03f6-675">Nederlands identificatie di recente</span><span class="sxs-lookup"><span data-stu-id="f03f6-675">nederlands belasting identificatie</span></span>
  
<span data-ttu-id="f03f6-676">l'ID di Nummer del Nederlands</span><span class="sxs-lookup"><span data-stu-id="f03f6-676">nederlands belasting id nummer</span></span>
  
<span data-ttu-id="f03f6-677">Nederlands belastingnummer</span><span class="sxs-lookup"><span data-stu-id="f03f6-677">nederlands belastingnummer</span></span>
  
<span data-ttu-id="f03f6-678">BTW nummer</span><span class="sxs-lookup"><span data-stu-id="f03f6-678">btw nummer</span></span>
  
<span data-ttu-id="f03f6-679">Nederlandse che durerà identificatie</span><span class="sxs-lookup"><span data-stu-id="f03f6-679">nederlandse belasting identificatie</span></span>
  
## <a name="poland"></a><span data-ttu-id="f03f6-680">Polonia</span><span class="sxs-lookup"><span data-stu-id="f03f6-680">Poland</span></span>

### <a name="format"></a><span data-ttu-id="f03f6-681">Formato</span><span class="sxs-lookup"><span data-stu-id="f03f6-681">Format</span></span>

<span data-ttu-id="f03f6-682">Undici cifre senza spazi o delimitatori</span><span class="sxs-lookup"><span data-stu-id="f03f6-682">Eleven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="f03f6-683">Modello</span><span class="sxs-lookup"><span data-stu-id="f03f6-683">Pattern</span></span>

<span data-ttu-id="f03f6-684">Undici cifre</span><span class="sxs-lookup"><span data-stu-id="f03f6-684">Eleven digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="f03f6-685">Checksum</span><span class="sxs-lookup"><span data-stu-id="f03f6-685">Checksum</span></span>

<span data-ttu-id="f03f6-686">Sì</span><span class="sxs-lookup"><span data-stu-id="f03f6-686">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="f03f6-687">Definizione</span><span class="sxs-lookup"><span data-stu-id="f03f6-687">Definition</span></span>

<span data-ttu-id="f03f6-688">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="f03f6-688">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="f03f6-689">La funzione `Func_poland_eu_tax_file_number` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="f03f6-689">The function  `Func_poland_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="f03f6-690">Viene trovata una `Keywords_poland_eu_tax_file_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="f03f6-690">A keyword from  `Keywords_poland_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="f03f6-691">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="f03f6-691">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="f03f6-692">La funzione `Func_poland_eu_tax_file_number` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="f03f6-692">The function  `Func_poland_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="f03f6-693">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="f03f6-693">Keywords</span></span>

#### <a name="keywordspolandeutaxfilenumber"></a><span data-ttu-id="f03f6-694">Keywords_poland_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="f03f6-694">Keywords_poland_eu_tax_file_number</span></span>

<span data-ttu-id="f03f6-695">codice fiscale</span><span class="sxs-lookup"><span data-stu-id="f03f6-695">tax number</span></span>
  
<span data-ttu-id="f03f6-696">tassa no.</span><span class="sxs-lookup"><span data-stu-id="f03f6-696">tax no.</span></span>
  
<span data-ttu-id="f03f6-697">taxno#</span><span class="sxs-lookup"><span data-stu-id="f03f6-697">taxno#</span></span>
  
<span data-ttu-id="f03f6-698">taxnumber#</span><span class="sxs-lookup"><span data-stu-id="f03f6-698">taxnumber#</span></span>
  
<span data-ttu-id="f03f6-699">taxnumber</span><span class="sxs-lookup"><span data-stu-id="f03f6-699">taxnumber</span></span>
  
<span data-ttu-id="f03f6-700">NIP</span><span class="sxs-lookup"><span data-stu-id="f03f6-700">nip</span></span>
  
<span data-ttu-id="f03f6-701">NIP</span><span class="sxs-lookup"><span data-stu-id="f03f6-701">nip#</span></span>
  
<span data-ttu-id="f03f6-702">tax id</span><span class="sxs-lookup"><span data-stu-id="f03f6-702">tax id</span></span>
  
<span data-ttu-id="f03f6-703">ID fiscale #</span><span class="sxs-lookup"><span data-stu-id="f03f6-703">tax id#</span></span>
  
<span data-ttu-id="f03f6-704">ID NIP</span><span class="sxs-lookup"><span data-stu-id="f03f6-704">nip id</span></span>
  
<span data-ttu-id="f03f6-705">ID NIP #</span><span class="sxs-lookup"><span data-stu-id="f03f6-705">nip id#</span></span>
  
<span data-ttu-id="f03f6-706">codice di identificazione fiscale</span><span class="sxs-lookup"><span data-stu-id="f03f6-706">tax identification number</span></span>
  
<span data-ttu-id="f03f6-707">codice fiscale n.</span><span class="sxs-lookup"><span data-stu-id="f03f6-707">tax identification no.</span></span>
  
<span data-ttu-id="f03f6-708">numero di partita IVA</span><span class="sxs-lookup"><span data-stu-id="f03f6-708">vat number</span></span>
  
<span data-ttu-id="f03f6-709">IVA No.</span><span class="sxs-lookup"><span data-stu-id="f03f6-709">vat no.</span></span>
  
<span data-ttu-id="f03f6-710">vatno#</span><span class="sxs-lookup"><span data-stu-id="f03f6-710">vatno#</span></span>
  
<span data-ttu-id="f03f6-711">ID partita IVA</span><span class="sxs-lookup"><span data-stu-id="f03f6-711">vat id</span></span>
  
<span data-ttu-id="f03f6-712">ID partita IVA #</span><span class="sxs-lookup"><span data-stu-id="f03f6-712">vat id#</span></span>
  
<span data-ttu-id="f03f6-713">numero Identyfikacji Podatkowej</span><span class="sxs-lookup"><span data-stu-id="f03f6-713">numer identyfikacji podatkowej</span></span>
  
<span data-ttu-id="f03f6-714">Polski numero Identyfikacji Podatkowej</span><span class="sxs-lookup"><span data-stu-id="f03f6-714">polski numer identyfikacji podatkowej</span></span>
  
<span data-ttu-id="f03f6-715">numeridentyfikacjipodatkowej#</span><span class="sxs-lookup"><span data-stu-id="f03f6-715">numeridentyfikacjipodatkowej#</span></span>
  
## <a name="portugal"></a><span data-ttu-id="f03f6-716">Portogallo</span><span class="sxs-lookup"><span data-stu-id="f03f6-716">Portugal</span></span>

### <a name="format"></a><span data-ttu-id="f03f6-717">Formato</span><span class="sxs-lookup"><span data-stu-id="f03f6-717">Format</span></span>

<span data-ttu-id="f03f6-718">Nove cifre senza spazi o delimitatori</span><span class="sxs-lookup"><span data-stu-id="f03f6-718">Nine digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="f03f6-719">Modello</span><span class="sxs-lookup"><span data-stu-id="f03f6-719">Pattern</span></span>

<span data-ttu-id="f03f6-720">9 cifre</span><span class="sxs-lookup"><span data-stu-id="f03f6-720">Nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="f03f6-721">Checksum</span><span class="sxs-lookup"><span data-stu-id="f03f6-721">Checksum</span></span>

<span data-ttu-id="f03f6-722">Sì</span><span class="sxs-lookup"><span data-stu-id="f03f6-722">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="f03f6-723">Definizione</span><span class="sxs-lookup"><span data-stu-id="f03f6-723">Definition</span></span>

<span data-ttu-id="f03f6-724">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="f03f6-724">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="f03f6-725">La funzione `Func_portugal_eu_tax_file_number` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="f03f6-725">The function  `Func_portugal_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="f03f6-726">Viene trovata una `Keywords_portugal_eu_tax_file_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="f03f6-726">A keyword from  `Keywords_portugal_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="f03f6-727">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="f03f6-727">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="f03f6-728">La funzione `Func_portugal_eu_tax_file_number` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="f03f6-728">The function  `Func_portugal_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="f03f6-729">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="f03f6-729">Keywords</span></span>

#### <a name="keywordsportugaleutaxfilenumber"></a><span data-ttu-id="f03f6-730">Keywords_portugal_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="f03f6-730">Keywords_portugal_eu_tax_file_number</span></span>

<span data-ttu-id="f03f6-731">codice fiscale</span><span class="sxs-lookup"><span data-stu-id="f03f6-731">tax number</span></span>
  
<span data-ttu-id="f03f6-732">tassa no.</span><span class="sxs-lookup"><span data-stu-id="f03f6-732">tax no.</span></span>
  
<span data-ttu-id="f03f6-733">taxno#</span><span class="sxs-lookup"><span data-stu-id="f03f6-733">taxno#</span></span>
  
<span data-ttu-id="f03f6-734">taxnumber#</span><span class="sxs-lookup"><span data-stu-id="f03f6-734">taxnumber#</span></span>
  
<span data-ttu-id="f03f6-735">taxnumber</span><span class="sxs-lookup"><span data-stu-id="f03f6-735">taxnumber</span></span>
  
<span data-ttu-id="f03f6-736">NIF</span><span class="sxs-lookup"><span data-stu-id="f03f6-736">nif</span></span>
  
<span data-ttu-id="f03f6-737">NIF</span><span class="sxs-lookup"><span data-stu-id="f03f6-737">nif#</span></span>
  
<span data-ttu-id="f03f6-738">numero fiscale</span><span class="sxs-lookup"><span data-stu-id="f03f6-738">numero fiscal</span></span>
  
<span data-ttu-id="f03f6-739">número de identificação Fiscal</span><span class="sxs-lookup"><span data-stu-id="f03f6-739">número de identificação fiscal</span></span>
  
## <a name="romania"></a><span data-ttu-id="f03f6-740">Romania</span><span class="sxs-lookup"><span data-stu-id="f03f6-740">Romania</span></span>

### <a name="format"></a><span data-ttu-id="f03f6-741">Formato</span><span class="sxs-lookup"><span data-stu-id="f03f6-741">Format</span></span>

<span data-ttu-id="f03f6-742">13 cifre senza spazi o delimitatori</span><span class="sxs-lookup"><span data-stu-id="f03f6-742">13 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="f03f6-743">Modello</span><span class="sxs-lookup"><span data-stu-id="f03f6-743">Pattern</span></span>

<span data-ttu-id="f03f6-744">13 cifre</span><span class="sxs-lookup"><span data-stu-id="f03f6-744">13 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="f03f6-745">Checksum</span><span class="sxs-lookup"><span data-stu-id="f03f6-745">Checksum</span></span>

<span data-ttu-id="f03f6-746">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="f03f6-746">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="f03f6-747">Definizione</span><span class="sxs-lookup"><span data-stu-id="f03f6-747">Definition</span></span>

<span data-ttu-id="f03f6-748">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="f03f6-748">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="f03f6-749">L'espressione `Regex_romania_eu_tax_file_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="f03f6-749">The regular expression  `Regex_romania_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="f03f6-750">Viene trovata una `Keywords_romania_eu_tax_file_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="f03f6-750">A keyword from  `Keywords_romania_eu_tax_file_number` is found.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_romania_eu_tax_file_number" />
          <Match idRef="Keywords_romania_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="f03f6-751">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="f03f6-751">Keywords</span></span>

#### <a name="keywordsromaniaeutaxfilenumber"></a><span data-ttu-id="f03f6-752">Keywords_romania_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="f03f6-752">Keywords_romania_eu_tax_file_number</span></span>

<span data-ttu-id="f03f6-753">tax id</span><span class="sxs-lookup"><span data-stu-id="f03f6-753">tax id</span></span>
  
<span data-ttu-id="f03f6-754">numero di ID fiscale</span><span class="sxs-lookup"><span data-stu-id="f03f6-754">tax id number</span></span>
  
<span data-ttu-id="f03f6-755">Tax File No</span><span class="sxs-lookup"><span data-stu-id="f03f6-755">tax file no</span></span>
  
<span data-ttu-id="f03f6-756">tax file number</span><span class="sxs-lookup"><span data-stu-id="f03f6-756">tax file number</span></span>
  
<span data-ttu-id="f03f6-757">tax no</span><span class="sxs-lookup"><span data-stu-id="f03f6-757">tax no</span></span>
  
<span data-ttu-id="f03f6-758">codice fiscale</span><span class="sxs-lookup"><span data-stu-id="f03f6-758">tax number</span></span>
  
<span data-ttu-id="f03f6-759">taxid #</span><span class="sxs-lookup"><span data-stu-id="f03f6-759">taxid#</span></span>
  
<span data-ttu-id="f03f6-760">taxno#</span><span class="sxs-lookup"><span data-stu-id="f03f6-760">taxno#</span></span>
  
<span data-ttu-id="f03f6-761">ID-ul taxei</span><span class="sxs-lookup"><span data-stu-id="f03f6-761">id-ul taxei</span></span>
  
<span data-ttu-id="f03f6-762">numărul de identificare fiscală</span><span class="sxs-lookup"><span data-stu-id="f03f6-762">numărul de identificare fiscală</span></span>
  
## <a name="slovakia"></a><span data-ttu-id="f03f6-763">Slovacchia</span><span class="sxs-lookup"><span data-stu-id="f03f6-763">Slovakia</span></span>

### <a name="format"></a><span data-ttu-id="f03f6-764">Formato</span><span class="sxs-lookup"><span data-stu-id="f03f6-764">Format</span></span>

<span data-ttu-id="f03f6-765">10 cifre senza spazi o delimitatori</span><span class="sxs-lookup"><span data-stu-id="f03f6-765">10 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="f03f6-766">Modello</span><span class="sxs-lookup"><span data-stu-id="f03f6-766">Pattern</span></span>

<span data-ttu-id="f03f6-767">10 cifre</span><span class="sxs-lookup"><span data-stu-id="f03f6-767">10 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="f03f6-768">Checksum</span><span class="sxs-lookup"><span data-stu-id="f03f6-768">Checksum</span></span>

<span data-ttu-id="f03f6-769">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="f03f6-769">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="f03f6-770">Definizione</span><span class="sxs-lookup"><span data-stu-id="f03f6-770">Definition</span></span>

<span data-ttu-id="f03f6-771">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="f03f6-771">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="f03f6-772">L'espressione `Regex_slovakia_eu_tax_file_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="f03f6-772">The regular expression  `Regex_slovakia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="f03f6-773">Viene trovata una `Keywords_slovakia_eu_tax_file_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="f03f6-773">A keyword from  `Keywords_slovakia_eu_tax_file_number` is found.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovakia_eu_tax_file_number" />
          <Match idRef="Keywords_slovakia_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="f03f6-774">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="f03f6-774">Keywords</span></span>

#### <a name="keywordsslovakiaeutaxfilenumber"></a><span data-ttu-id="f03f6-775">Keywords_slovakia_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="f03f6-775">Keywords_slovakia_eu_tax_file_number</span></span>

<span data-ttu-id="f03f6-776">tax id</span><span class="sxs-lookup"><span data-stu-id="f03f6-776">tax id</span></span>
  
<span data-ttu-id="f03f6-777">numero di ID fiscale</span><span class="sxs-lookup"><span data-stu-id="f03f6-777">tax id number</span></span>
  
<span data-ttu-id="f03f6-778">ID Tin</span><span class="sxs-lookup"><span data-stu-id="f03f6-778">tin id</span></span>
  
<span data-ttu-id="f03f6-779">Tin No</span><span class="sxs-lookup"><span data-stu-id="f03f6-779">tin no</span></span>
  
<span data-ttu-id="f03f6-780">ID Tin slovacco</span><span class="sxs-lookup"><span data-stu-id="f03f6-780">slovakian tin id</span></span>
  
<span data-ttu-id="f03f6-781">latta</span><span class="sxs-lookup"><span data-stu-id="f03f6-781">tin</span></span>
  
<span data-ttu-id="f03f6-782">Tax File No</span><span class="sxs-lookup"><span data-stu-id="f03f6-782">tax file no</span></span>
  
<span data-ttu-id="f03f6-783">tax file number</span><span class="sxs-lookup"><span data-stu-id="f03f6-783">tax file number</span></span>
  
<span data-ttu-id="f03f6-784">tax no</span><span class="sxs-lookup"><span data-stu-id="f03f6-784">tax no</span></span>
  
<span data-ttu-id="f03f6-785">codice fiscale</span><span class="sxs-lookup"><span data-stu-id="f03f6-785">tax number</span></span>
  
<span data-ttu-id="f03f6-786">taxid #</span><span class="sxs-lookup"><span data-stu-id="f03f6-786">taxid#</span></span>
  
<span data-ttu-id="f03f6-787">taxno#</span><span class="sxs-lookup"><span data-stu-id="f03f6-787">taxno#</span></span>
  
<span data-ttu-id="f03f6-788">daňové identifikačné číslo</span><span class="sxs-lookup"><span data-stu-id="f03f6-788">daňové identifikačné číslo</span></span>
  
<span data-ttu-id="f03f6-789">daňové číslo</span><span class="sxs-lookup"><span data-stu-id="f03f6-789">daňové číslo</span></span>
  
<span data-ttu-id="f03f6-790">daňové číslo súboru</span><span class="sxs-lookup"><span data-stu-id="f03f6-790">daňové číslo súboru</span></span>
  
## <a name="slovenia"></a><span data-ttu-id="f03f6-791">Slovenia</span><span class="sxs-lookup"><span data-stu-id="f03f6-791">Slovenia</span></span>

### <a name="format"></a><span data-ttu-id="f03f6-792">Formato</span><span class="sxs-lookup"><span data-stu-id="f03f6-792">Format</span></span>

<span data-ttu-id="f03f6-793">Otto cifre senza spazi o delimitatori</span><span class="sxs-lookup"><span data-stu-id="f03f6-793">Eight digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="f03f6-794">Modello</span><span class="sxs-lookup"><span data-stu-id="f03f6-794">Pattern</span></span>

<span data-ttu-id="f03f6-795">Otto cifre</span><span class="sxs-lookup"><span data-stu-id="f03f6-795">Eight digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="f03f6-796">Checksum</span><span class="sxs-lookup"><span data-stu-id="f03f6-796">Checksum</span></span>

<span data-ttu-id="f03f6-797">Sì</span><span class="sxs-lookup"><span data-stu-id="f03f6-797">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="f03f6-798">Definizione</span><span class="sxs-lookup"><span data-stu-id="f03f6-798">Definition</span></span>

<span data-ttu-id="f03f6-799">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="f03f6-799">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="f03f6-800">La funzione `Func_slovenia_eu_tax_file_number` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="f03f6-800">The function  `Func_slovenia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="f03f6-801">Viene trovata una `Keywords_slovenia_eu_tax_file_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="f03f6-801">A keyword from  `Keywords_slovenia_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="f03f6-802">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="f03f6-802">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="f03f6-803">La funzione `Func_slovenia_eu_tax_file_number` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="f03f6-803">The function  `Func_slovenia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="f03f6-804">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="f03f6-804">Keywords</span></span>

#### <a name="keywordssloveniaeutaxfilenumber"></a><span data-ttu-id="f03f6-805">Keywords_slovenia_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="f03f6-805">Keywords_slovenia_eu_tax_file_number</span></span>

<span data-ttu-id="f03f6-806">tax id</span><span class="sxs-lookup"><span data-stu-id="f03f6-806">tax id</span></span>
  
<span data-ttu-id="f03f6-807">numero di ID fiscale</span><span class="sxs-lookup"><span data-stu-id="f03f6-807">tax id number</span></span>
  
<span data-ttu-id="f03f6-808">ID Tin</span><span class="sxs-lookup"><span data-stu-id="f03f6-808">tin id</span></span>
  
<span data-ttu-id="f03f6-809">Tin No</span><span class="sxs-lookup"><span data-stu-id="f03f6-809">tin no</span></span>
  
<span data-ttu-id="f03f6-810">ID Tin sloveno</span><span class="sxs-lookup"><span data-stu-id="f03f6-810">slovenian tin id</span></span>
  
<span data-ttu-id="f03f6-811">latta</span><span class="sxs-lookup"><span data-stu-id="f03f6-811">tin</span></span>
  
<span data-ttu-id="f03f6-812">Tax File No</span><span class="sxs-lookup"><span data-stu-id="f03f6-812">tax file no</span></span>
  
<span data-ttu-id="f03f6-813">tax file number</span><span class="sxs-lookup"><span data-stu-id="f03f6-813">tax file number</span></span>
  
<span data-ttu-id="f03f6-814">tax no</span><span class="sxs-lookup"><span data-stu-id="f03f6-814">tax no</span></span>
  
<span data-ttu-id="f03f6-815">codice fiscale</span><span class="sxs-lookup"><span data-stu-id="f03f6-815">tax number</span></span>
  
<span data-ttu-id="f03f6-816">taxid #</span><span class="sxs-lookup"><span data-stu-id="f03f6-816">taxid#</span></span>
  
<span data-ttu-id="f03f6-817">taxno#</span><span class="sxs-lookup"><span data-stu-id="f03f6-817">taxno#</span></span>
  
<span data-ttu-id="f03f6-818">identifikacijska številka davka</span><span class="sxs-lookup"><span data-stu-id="f03f6-818">identifikacijska številka davka</span></span>
  
<span data-ttu-id="f03f6-819">davčna številka</span><span class="sxs-lookup"><span data-stu-id="f03f6-819">davčna številka</span></span>
  
<span data-ttu-id="f03f6-820">številka davčne datoteke</span><span class="sxs-lookup"><span data-stu-id="f03f6-820">številka davčne datoteke</span></span>
  
## <a name="spain"></a><span data-ttu-id="f03f6-821">Spagna</span><span class="sxs-lookup"><span data-stu-id="f03f6-821">Spain</span></span>

### <a name="format"></a><span data-ttu-id="f03f6-822">Formato</span><span class="sxs-lookup"><span data-stu-id="f03f6-822">Format</span></span>

<span data-ttu-id="f03f6-823">Sette o otto cifre e una o due lettere nel modello specificato</span><span class="sxs-lookup"><span data-stu-id="f03f6-823">Seven or eight digits and one or two letters in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="f03f6-824">Modello</span><span class="sxs-lookup"><span data-stu-id="f03f6-824">Pattern</span></span>

<span data-ttu-id="f03f6-825">Persone fisiche spagnole con carta d'identità nazionale spagnola:</span><span class="sxs-lookup"><span data-stu-id="f03f6-825">Spanish Natural Persons with a Spain National Identity Card:</span></span>
  
-  <span data-ttu-id="f03f6-826">Otto cifre</span><span class="sxs-lookup"><span data-stu-id="f03f6-826">Eight digits</span></span> 
    
- <span data-ttu-id="f03f6-827">Una lettera maiuscola (con distinzione tra maiuscole e minuscole)</span><span class="sxs-lookup"><span data-stu-id="f03f6-827">One uppercase letter (case-sensitive)</span></span> 
    
<span data-ttu-id="f03f6-828">Spagnoli non residenti senza una carta d'identità nazionale spagnola</span><span class="sxs-lookup"><span data-stu-id="f03f6-828">Non-resident Spaniards without a Spain National Identity Card</span></span>
  
- <span data-ttu-id="f03f6-829">Una lettera maiuscola "L" (con distinzione tra maiuscole e minuscole)</span><span class="sxs-lookup"><span data-stu-id="f03f6-829">One uppercase letter "L" (case-sensitive)</span></span>
    
- <span data-ttu-id="f03f6-830">Sette cifre</span><span class="sxs-lookup"><span data-stu-id="f03f6-830">Seven digits</span></span>
    
- <span data-ttu-id="f03f6-831">Una lettera maiuscola (con distinzione tra maiuscole e minuscole)</span><span class="sxs-lookup"><span data-stu-id="f03f6-831">One uppercase letter (case-sensitive)</span></span> 
    
<span data-ttu-id="f03f6-832">Spagnoli residenti di età inferiore ai 14 anni senza una carta d'identità nazionale spagnola:</span><span class="sxs-lookup"><span data-stu-id="f03f6-832">Resident Spaniards under the age of 14 years without a Spain National Identity Card :</span></span>
  
- <span data-ttu-id="f03f6-833">Una lettera maiuscola "K" (con distinzione tra maiuscole e minuscole)</span><span class="sxs-lookup"><span data-stu-id="f03f6-833">One uppercase letter"K" (case-sensitive)</span></span>
    
-  <span data-ttu-id="f03f6-834">Sette cifre</span><span class="sxs-lookup"><span data-stu-id="f03f6-834">Seven digits</span></span> 
    
- <span data-ttu-id="f03f6-835">Una lettera maiuscola (con distinzione tra maiuscole e minuscole)</span><span class="sxs-lookup"><span data-stu-id="f03f6-835">One uppercase letter (case-sensitive)</span></span>
    
<span data-ttu-id="f03f6-836">Stranieri con il numero di identificazione di un forestiero</span><span class="sxs-lookup"><span data-stu-id="f03f6-836">Foreigners with a Foreigner's Identification Number</span></span>
  
- <span data-ttu-id="f03f6-837">Una lettera maiuscola che è "X", "Y" o "Z" (con distinzione tra maiuscole e minuscole)</span><span class="sxs-lookup"><span data-stu-id="f03f6-837">One uppercase letter that is "X", "Y", or "Z" (case-sensitive)</span></span> 
    
- <span data-ttu-id="f03f6-838">Sette cifre</span><span class="sxs-lookup"><span data-stu-id="f03f6-838">Seven digits</span></span>
    
- <span data-ttu-id="f03f6-839">Una lettera maiuscola (con distinzione tra maiuscole e minuscole)</span><span class="sxs-lookup"><span data-stu-id="f03f6-839">One uppercase letter (case-sensitive)</span></span> 
    
<span data-ttu-id="f03f6-840">Stranieri senza il numero di identificazione di un forestiero</span><span class="sxs-lookup"><span data-stu-id="f03f6-840">Foreigners without a Foreigner's Identification Number</span></span>
  
- <span data-ttu-id="f03f6-841">Una lettera maiuscola che è "M" (con distinzione tra maiuscole e minuscole)</span><span class="sxs-lookup"><span data-stu-id="f03f6-841">One uppercase letter that is "M" (case-sensitive)</span></span> 
    
- <span data-ttu-id="f03f6-842">Sette cifre</span><span class="sxs-lookup"><span data-stu-id="f03f6-842">Seven digits</span></span>
    
- <span data-ttu-id="f03f6-843">Una lettera maiuscola (con distinzione tra maiuscole e minuscole)</span><span class="sxs-lookup"><span data-stu-id="f03f6-843">One uppercase letter (case-sensitive)</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="f03f6-844">Checksum</span><span class="sxs-lookup"><span data-stu-id="f03f6-844">Checksum</span></span>

<span data-ttu-id="f03f6-845">Sì</span><span class="sxs-lookup"><span data-stu-id="f03f6-845">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="f03f6-846">Definizione</span><span class="sxs-lookup"><span data-stu-id="f03f6-846">Definition</span></span>

<span data-ttu-id="f03f6-847">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="f03f6-847">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="f03f6-848">La funzione `Func_spain_eu_tax_file_number` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="f03f6-848">The function  `Func_spain_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="f03f6-849">Viene trovata una `Keywords_spain_eu_tax_file_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="f03f6-849">A keyword from  `Keywords_spain_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="f03f6-850">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="f03f6-850">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="f03f6-851">La funzione `Func_spain_eu_tax_file_number` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="f03f6-851">The function  `Func_spain_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="f03f6-852">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="f03f6-852">Keywords</span></span>

#### <a name="keywordsspaineutaxfilenumber"></a><span data-ttu-id="f03f6-853">Keywords_spain_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="f03f6-853">Keywords_spain_eu_tax_file_number</span></span>

<span data-ttu-id="f03f6-854">tax id</span><span class="sxs-lookup"><span data-stu-id="f03f6-854">tax id</span></span>
  
<span data-ttu-id="f03f6-855">numero di ID fiscale</span><span class="sxs-lookup"><span data-stu-id="f03f6-855">tax id number</span></span>
  
<span data-ttu-id="f03f6-856">ID CIF</span><span class="sxs-lookup"><span data-stu-id="f03f6-856">cif id</span></span>
  
<span data-ttu-id="f03f6-857">CIF No</span><span class="sxs-lookup"><span data-stu-id="f03f6-857">cif no</span></span>
  
<span data-ttu-id="f03f6-858">ID CIF spagnolo</span><span class="sxs-lookup"><span data-stu-id="f03f6-858">spanish cif id</span></span>
  
<span data-ttu-id="f03f6-859">CIF</span><span class="sxs-lookup"><span data-stu-id="f03f6-859">cif</span></span>
  
<span data-ttu-id="f03f6-860">Tax File No</span><span class="sxs-lookup"><span data-stu-id="f03f6-860">tax file no</span></span>
  
<span data-ttu-id="f03f6-861">numero CIF spagnolo</span><span class="sxs-lookup"><span data-stu-id="f03f6-861">spanish cif number</span></span>
  
<span data-ttu-id="f03f6-862">tax file number</span><span class="sxs-lookup"><span data-stu-id="f03f6-862">tax file number</span></span>
  
<span data-ttu-id="f03f6-863">Spagnolo CIF No</span><span class="sxs-lookup"><span data-stu-id="f03f6-863">spanish cif no</span></span>
  
<span data-ttu-id="f03f6-864">tax no</span><span class="sxs-lookup"><span data-stu-id="f03f6-864">tax no</span></span>
  
<span data-ttu-id="f03f6-865">codice fiscale</span><span class="sxs-lookup"><span data-stu-id="f03f6-865">tax number</span></span>
  
<span data-ttu-id="f03f6-866">taxid #</span><span class="sxs-lookup"><span data-stu-id="f03f6-866">taxid#</span></span>
  
<span data-ttu-id="f03f6-867">taxno#</span><span class="sxs-lookup"><span data-stu-id="f03f6-867">taxno#</span></span>
  
<span data-ttu-id="f03f6-868">cifid#</span><span class="sxs-lookup"><span data-stu-id="f03f6-868">cifid#</span></span>
  
<span data-ttu-id="f03f6-869">spanishcifid#</span><span class="sxs-lookup"><span data-stu-id="f03f6-869">spanishcifid#</span></span>
  
<span data-ttu-id="f03f6-870">spanishcifno#</span><span class="sxs-lookup"><span data-stu-id="f03f6-870">spanishcifno#</span></span>
  
<span data-ttu-id="f03f6-871">número de contribuyente</span><span class="sxs-lookup"><span data-stu-id="f03f6-871">número de contribuyente</span></span>
  
<span data-ttu-id="f03f6-872">número de Impuesto corporativo</span><span class="sxs-lookup"><span data-stu-id="f03f6-872">número de impuesto corporativo</span></span>
  
<span data-ttu-id="f03f6-873">número de Identificación Fiscal</span><span class="sxs-lookup"><span data-stu-id="f03f6-873">número de identificación fiscal</span></span>
  
<span data-ttu-id="f03f6-874">número CIF</span><span class="sxs-lookup"><span data-stu-id="f03f6-874">cif número</span></span>
  
<span data-ttu-id="f03f6-875">cifnúmero#</span><span class="sxs-lookup"><span data-stu-id="f03f6-875">cifnúmero#</span></span>
  
## <a name="sweden"></a><span data-ttu-id="f03f6-876">Svezia</span><span class="sxs-lookup"><span data-stu-id="f03f6-876">Sweden</span></span>

### <a name="format"></a><span data-ttu-id="f03f6-877">Formato</span><span class="sxs-lookup"><span data-stu-id="f03f6-877">Format</span></span>

<span data-ttu-id="f03f6-878">Dieci cifre e un simbolo nel modello specificato</span><span class="sxs-lookup"><span data-stu-id="f03f6-878">Ten digits and a symbol in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="f03f6-879">Modello</span><span class="sxs-lookup"><span data-stu-id="f03f6-879">Pattern</span></span>

<span data-ttu-id="f03f6-880">Dieci cifre e un simbolo:</span><span class="sxs-lookup"><span data-stu-id="f03f6-880">Ten digits and a symbol:</span></span>
  
-  <span data-ttu-id="f03f6-881">Sei cifre che corrispondono alla data di nascita (AAMMGG)</span><span class="sxs-lookup"><span data-stu-id="f03f6-881">Six digits that correspond to the birth date (YYMMDD)</span></span> 
    
- <span data-ttu-id="f03f6-882">Segno di addizione, segno meno o barra rovesciata</span><span class="sxs-lookup"><span data-stu-id="f03f6-882">A plus sign, minus sign, or backslash</span></span>
    
- <span data-ttu-id="f03f6-883">Tre cifre che rendono il numero di identificazione univoco dove:</span><span class="sxs-lookup"><span data-stu-id="f03f6-883">Three digits that make the identification number unique where:</span></span> 
    
  - <span data-ttu-id="f03f6-884">Per i numeri emessi prima del 1990, la settima e la terza cifra identificano la Contea di nascita o gli stranieri nati</span><span class="sxs-lookup"><span data-stu-id="f03f6-884">For numbers issued before 1990, the seventh and eighth digit identify the county of birth or foreign-born people</span></span>
    
  - <span data-ttu-id="f03f6-885">La cifra nella nona posizione indica il sesso per il maschio o per la femmina.</span><span class="sxs-lookup"><span data-stu-id="f03f6-885">The digit in the ninth position indicates gender by either odd for male or even for female</span></span>
    
- <span data-ttu-id="f03f6-886">Una cifra di controllo</span><span class="sxs-lookup"><span data-stu-id="f03f6-886">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="f03f6-887">Checksum</span><span class="sxs-lookup"><span data-stu-id="f03f6-887">Checksum</span></span>

<span data-ttu-id="f03f6-888">Sì</span><span class="sxs-lookup"><span data-stu-id="f03f6-888">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="f03f6-889">Definizione</span><span class="sxs-lookup"><span data-stu-id="f03f6-889">Definition</span></span>

<span data-ttu-id="f03f6-890">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="f03f6-890">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="f03f6-891">La funzione `Func_sweden_eu_tax_file_number` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="f03f6-891">The function  `Func_sweden_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="f03f6-892">Viene trovata una `Keywords_sweden_eu_tax_file_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="f03f6-892">A keyword from  `Keywords_sweden_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="f03f6-893">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="f03f6-893">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="f03f6-894">La funzione `Func_sweden_eu_tax_file_number` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="f03f6-894">The function  `Func_sweden_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="f03f6-895">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="f03f6-895">Keywords</span></span>

#### <a name="keywordsswedeneutaxfilenumber"></a><span data-ttu-id="f03f6-896">Keywords_sweden_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="f03f6-896">Keywords_sweden_eu_tax_file_number</span></span>

<span data-ttu-id="f03f6-897">tax id</span><span class="sxs-lookup"><span data-stu-id="f03f6-897">tax id</span></span>
  
<span data-ttu-id="f03f6-898">ID IVA No.</span><span class="sxs-lookup"><span data-stu-id="f03f6-898">tax id no.</span></span>
  
<span data-ttu-id="f03f6-899">numero di ID fiscale</span><span class="sxs-lookup"><span data-stu-id="f03f6-899">tax id number</span></span>
  
<span data-ttu-id="f03f6-900">tax identification</span><span class="sxs-lookup"><span data-stu-id="f03f6-900">tax identification</span></span>
  
<span data-ttu-id="f03f6-901">identificazione fiscale #</span><span class="sxs-lookup"><span data-stu-id="f03f6-901">tax identification#</span></span>
  
<span data-ttu-id="f03f6-902">tassa no.</span><span class="sxs-lookup"><span data-stu-id="f03f6-902">tax no.</span></span>
  
<span data-ttu-id="f03f6-903">imposte</span><span class="sxs-lookup"><span data-stu-id="f03f6-903">tax#</span></span>
  
<span data-ttu-id="f03f6-904">taxid #</span><span class="sxs-lookup"><span data-stu-id="f03f6-904">taxid#</span></span>
  
<span data-ttu-id="f03f6-905">file fiscale</span><span class="sxs-lookup"><span data-stu-id="f03f6-905">tax file</span></span>
  
<span data-ttu-id="f03f6-906">Tax File No.</span><span class="sxs-lookup"><span data-stu-id="f03f6-906">tax file no.</span></span>
  
<span data-ttu-id="f03f6-907">numero ID personale</span><span class="sxs-lookup"><span data-stu-id="f03f6-907">personal id number</span></span>
  
<span data-ttu-id="f03f6-908">ID pattinat Nummer</span><span class="sxs-lookup"><span data-stu-id="f03f6-908">skatt id nummer</span></span>
  
<span data-ttu-id="f03f6-909">Identifikation skatet</span><span class="sxs-lookup"><span data-stu-id="f03f6-909">skatt identifikation</span></span>
  
<span data-ttu-id="f03f6-910">personnummer</span><span class="sxs-lookup"><span data-stu-id="f03f6-910">personnummer</span></span>
  
## <a name="uk"></a><span data-ttu-id="f03f6-911">Regno Unito</span><span class="sxs-lookup"><span data-stu-id="f03f6-911">UK</span></span>

### <a name="format"></a><span data-ttu-id="f03f6-912">Formato</span><span class="sxs-lookup"><span data-stu-id="f03f6-912">Format</span></span>

<span data-ttu-id="f03f6-913">Riferimento per i contribuenti unici (UTR): 10 cifre senza spazi e delimitatori</span><span class="sxs-lookup"><span data-stu-id="f03f6-913">Unique Taxpayer Reference (UTR): 10 digits without spaces and delimiters</span></span>
  
<span data-ttu-id="f03f6-914">Numero di assicurazione nazionale (NINO): per informazioni dettagliate, vedere la sezione "Regno Unito</span><span class="sxs-lookup"><span data-stu-id="f03f6-914">National Insurance Number (NINO): For details, see the section "U.K.</span></span> <span data-ttu-id="f03f6-915">Numero di assicurazione nazionale (NINO) "in [che cosa cercano i tipi di informazioni riservate](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="f03f6-915">National Insurance Number (NINO)" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
### <a name="pattern"></a><span data-ttu-id="f03f6-916">Modello</span><span class="sxs-lookup"><span data-stu-id="f03f6-916">Pattern</span></span>

<span data-ttu-id="f03f6-917">Riferimento per i contribuenti unici (UTR): 10 cifre</span><span class="sxs-lookup"><span data-stu-id="f03f6-917">Unique Taxpayer Reference (UTR): 10 digits</span></span>
  
<span data-ttu-id="f03f6-918">Numero di assicurazione nazionale (NINO): per informazioni dettagliate, vedere la sezione "Regno Unito</span><span class="sxs-lookup"><span data-stu-id="f03f6-918">National Insurance Number (NINO): For details, see the section "U.K.</span></span> <span data-ttu-id="f03f6-919">Numero di assicurazione nazionale (NINO) "in [che cosa cercano i tipi di informazioni riservate](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="f03f6-919">National Insurance Number (NINO)" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
### <a name="checksum"></a><span data-ttu-id="f03f6-920">Checksum</span><span class="sxs-lookup"><span data-stu-id="f03f6-920">Checksum</span></span>

<span data-ttu-id="f03f6-921">Sì</span><span class="sxs-lookup"><span data-stu-id="f03f6-921">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="f03f6-922">Definizione</span><span class="sxs-lookup"><span data-stu-id="f03f6-922">Definition</span></span>

<span data-ttu-id="f03f6-923">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="f03f6-923">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="f03f6-924">La funzione `Func_uk_eu_tax_file_number` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="f03f6-924">The function  `Func_uk_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="f03f6-925">Viene trovata una `Keywords_uk_eu_tax_file_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="f03f6-925">A keyword from  `Keywords_uk_eu_tax_file_number` is found.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_uk_eu_tax_file_number" />
          <Match idRef="Keywords_uk_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="f03f6-926">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="f03f6-926">Keywords</span></span>

#### <a name="keywordsukeutaxfilenumber"></a><span data-ttu-id="f03f6-927">Keywords_uk_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="f03f6-927">Keywords_uk_eu_tax_file_number</span></span>

<span data-ttu-id="f03f6-928">tax id</span><span class="sxs-lookup"><span data-stu-id="f03f6-928">tax id</span></span>
  
<span data-ttu-id="f03f6-929">ID IVA No.</span><span class="sxs-lookup"><span data-stu-id="f03f6-929">tax id no.</span></span>
  
<span data-ttu-id="f03f6-930">numero di ID fiscale</span><span class="sxs-lookup"><span data-stu-id="f03f6-930">tax id number</span></span>
  
<span data-ttu-id="f03f6-931">tax identification</span><span class="sxs-lookup"><span data-stu-id="f03f6-931">tax identification</span></span>
  
<span data-ttu-id="f03f6-932">identificazione fiscale #</span><span class="sxs-lookup"><span data-stu-id="f03f6-932">tax identification#</span></span>
  
<span data-ttu-id="f03f6-933">tassa no.</span><span class="sxs-lookup"><span data-stu-id="f03f6-933">tax no.</span></span>
  
<span data-ttu-id="f03f6-934">imposte</span><span class="sxs-lookup"><span data-stu-id="f03f6-934">tax#</span></span>
  
<span data-ttu-id="f03f6-935">taxid #</span><span class="sxs-lookup"><span data-stu-id="f03f6-935">taxid#</span></span>
  
<span data-ttu-id="f03f6-936">file fiscale</span><span class="sxs-lookup"><span data-stu-id="f03f6-936">tax file</span></span>
  
<span data-ttu-id="f03f6-937">Tax File No.</span><span class="sxs-lookup"><span data-stu-id="f03f6-937">tax file no.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="f03f6-938">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f03f6-938">See also</span></span>

[<span data-ttu-id="f03f6-939">Cosa individuano le tipologie di informazioni sensibili</span><span class="sxs-lookup"><span data-stu-id="f03f6-939">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)

