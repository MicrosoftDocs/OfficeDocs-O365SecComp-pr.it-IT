---
title: Numero di identificazione fiscale UE
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 8/17/2018
ms.audience: Admin
ms.topic: reference
ms.service: o365-administration
localization_priority: Normal
ms.assetid: f04919c8-2356-4de2-bb2a-b9f67f339726
description: Questo argomento viene illustrato quali criteri di criterio DLP perdita dei dati Cerca quando viene rilevato il tipo di informazioni riservate dell'Unione europea imposte Identification Number. Questo tipo di informazioni riservate definisce le diverse combinazioni, parole chiave e altri elementi di prova per ogni paese.
ms.openlocfilehash: 5192496b393d15fd6d063e09c9bfe1cb3dd7e2dd
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/27/2018
ms.locfileid: "22530774"
---
# <a name="eu-tax-identification-number"></a><span data-ttu-id="f4ef9-104">Numero di identificazione fiscale UE</span><span class="sxs-lookup"><span data-stu-id="f4ef9-104">EU Tax Identification Number</span></span>

<span data-ttu-id="f4ef9-p102">In questo argomento viene illustrato quali criteri di criterio DLP perdita dei dati Cerca quando viene rilevato il tipo di informazioni riservate dell'Unione europea imposte identificazione numero (ID). Questo tipo di informazioni riservate definisce le diverse combinazioni, parole chiave e altri elementi di prova per ogni paese.</span><span class="sxs-lookup"><span data-stu-id="f4ef9-p102">This topic shows what a data loss prevention (DLP) policy looks for when it detects the EU Tax Identification Number (TIN) sensitive information type. This sensitive information type defines different patterns, keywords, and other evidence for each country.</span></span>
  
## <a name="austria"></a><span data-ttu-id="f4ef9-107">Austria</span><span class="sxs-lookup"><span data-stu-id="f4ef9-107">Austria</span></span>

### <a name="format"></a><span data-ttu-id="f4ef9-108">Formato</span><span class="sxs-lookup"><span data-stu-id="f4ef9-108">Format</span></span>

<span data-ttu-id="f4ef9-109">Nove cifre con segno meno facoltativo e barra (/)</span><span class="sxs-lookup"><span data-stu-id="f4ef9-109">Nine digits with optional hyphen and forward slash</span></span>
  
### <a name="pattern"></a><span data-ttu-id="f4ef9-110">Modello</span><span class="sxs-lookup"><span data-stu-id="f4ef9-110">Pattern</span></span>

<span data-ttu-id="f4ef9-111">Nove cifre con segno meno facoltativo e barra (/):</span><span class="sxs-lookup"><span data-stu-id="f4ef9-111">Nine digits with optional hyphen and forward slash:</span></span>
  
-  <span data-ttu-id="f4ef9-112">Due cifre</span><span class="sxs-lookup"><span data-stu-id="f4ef9-112">Two digits</span></span> 
    
- <span data-ttu-id="f4ef9-113">Una lineetta (facoltativa)</span><span class="sxs-lookup"><span data-stu-id="f4ef9-113">A hyphen (optional)</span></span>
    
- <span data-ttu-id="f4ef9-114">Tre cifre</span><span class="sxs-lookup"><span data-stu-id="f4ef9-114">Three digits</span></span>
    
- <span data-ttu-id="f4ef9-115">Una barra (facoltativa)</span><span class="sxs-lookup"><span data-stu-id="f4ef9-115">A forward slash (optional)</span></span>
    
- <span data-ttu-id="f4ef9-116">Quattro cifre</span><span class="sxs-lookup"><span data-stu-id="f4ef9-116">Four digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="f4ef9-117">Checksum</span><span class="sxs-lookup"><span data-stu-id="f4ef9-117">Checksum</span></span>

<span data-ttu-id="f4ef9-118">Sì</span><span class="sxs-lookup"><span data-stu-id="f4ef9-118">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="f4ef9-119">Definizione</span><span class="sxs-lookup"><span data-stu-id="f4ef9-119">Definition</span></span>

<span data-ttu-id="f4ef9-120">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="f4ef9-120">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="f4ef9-121">La funzione `Func_austria_eu_tax_file_number` consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="f4ef9-121">The function  `Func_austria_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="f4ef9-122">Una parola chiave da `Keywords_austria_eu_tax_file_number` viene trovato.</span><span class="sxs-lookup"><span data-stu-id="f4ef9-122">A keyword from  `Keywords_austria_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="f4ef9-123">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="f4ef9-123">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="f4ef9-124">La funzione `Func_austria_eu_tax_file_number` consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="f4ef9-124">The function  `Func_austria_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="f4ef9-125">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="f4ef9-125">Keywords</span></span>

#### <a name="keywordsaustriaeutaxfilenumber"></a><span data-ttu-id="f4ef9-126">Keywords_austria_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="f4ef9-126">Keywords_austria_eu_tax_file_number</span></span>

<span data-ttu-id="f4ef9-127">Imposta numero</span><span class="sxs-lookup"><span data-stu-id="f4ef9-127">tax number</span></span>
  
<span data-ttu-id="f4ef9-128">numero</span><span class="sxs-lookup"><span data-stu-id="f4ef9-128">number</span></span>
  
<span data-ttu-id="f4ef9-129">identificativo fiscale</span><span class="sxs-lookup"><span data-stu-id="f4ef9-129">tax registration number</span></span>
  
<span data-ttu-id="f4ef9-130">tax id
</span><span class="sxs-lookup"><span data-stu-id="f4ef9-130">tax id</span></span>
  
<span data-ttu-id="f4ef9-131">ST.Nr.</span><span class="sxs-lookup"><span data-stu-id="f4ef9-131">st.nr.</span></span>
  
<span data-ttu-id="f4ef9-132">steuernummer</span><span class="sxs-lookup"><span data-stu-id="f4ef9-132">steuernummer</span></span>
  
## <a name="belgium"></a><span data-ttu-id="f4ef9-133">Belgio</span><span class="sxs-lookup"><span data-stu-id="f4ef9-133">Belgium</span></span>

### <a name="format"></a><span data-ttu-id="f4ef9-134">Formato</span><span class="sxs-lookup"><span data-stu-id="f4ef9-134">Format</span></span>

<span data-ttu-id="f4ef9-135">11 cifre senza spazi e i delimitatori</span><span class="sxs-lookup"><span data-stu-id="f4ef9-135">11 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="f4ef9-136">Modello</span><span class="sxs-lookup"><span data-stu-id="f4ef9-136">Pattern</span></span>

<span data-ttu-id="f4ef9-137">11 cifre:</span><span class="sxs-lookup"><span data-stu-id="f4ef9-137">11 digits:</span></span>
  
- <span data-ttu-id="f4ef9-138">Due cifre</span><span class="sxs-lookup"><span data-stu-id="f4ef9-138">Two digits</span></span>
    
- <span data-ttu-id="f4ef9-139">"0" o "1"</span><span class="sxs-lookup"><span data-stu-id="f4ef9-139">A "0" or "1"</span></span>
    
- <span data-ttu-id="f4ef9-140">Una cifra</span><span class="sxs-lookup"><span data-stu-id="f4ef9-140">One digit</span></span>
    
- <span data-ttu-id="f4ef9-141">"0" o "1" o "2" o "3"</span><span class="sxs-lookup"><span data-stu-id="f4ef9-141">A "0" or "1" or "2" or "3"</span></span> 
    
- <span data-ttu-id="f4ef9-142">Sei cifre</span><span class="sxs-lookup"><span data-stu-id="f4ef9-142">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="f4ef9-143">Checksum</span><span class="sxs-lookup"><span data-stu-id="f4ef9-143">Checksum</span></span>

<span data-ttu-id="f4ef9-144">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="f4ef9-144">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="f4ef9-145">Definizione</span><span class="sxs-lookup"><span data-stu-id="f4ef9-145">Definition</span></span>

<span data-ttu-id="f4ef9-146">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="f4ef9-146">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="f4ef9-147">L'espressione regolare `Regex_belgium_eu_tax_file_number` consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="f4ef9-147">The regular expression  `Regex_belgium_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="f4ef9-148">Una parola chiave da `Keywords_belgium_eu_tax_file_number` viene trovato.</span><span class="sxs-lookup"><span data-stu-id="f4ef9-148">A keyword from  `Keywords_belgium_eu_tax_file_number` is found.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_belgium_eu_tax_file_number" />
          <Match idRef="Keywords_belgium_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="f4ef9-149">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="f4ef9-149">Keywords</span></span>

#### <a name="keywordsbelgiumeutaxfilenumber"></a><span data-ttu-id="f4ef9-150">Keywords_belgium_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="f4ef9-150">Keywords_belgium_eu_tax_file_number</span></span>

<span data-ttu-id="f4ef9-151">Imposta numero</span><span class="sxs-lookup"><span data-stu-id="f4ef9-151">tax number</span></span>
  
<span data-ttu-id="f4ef9-152">numero di registrazione nazionale</span><span class="sxs-lookup"><span data-stu-id="f4ef9-152">national registration number</span></span>
  
<span data-ttu-id="f4ef9-153">identificativo fiscale</span><span class="sxs-lookup"><span data-stu-id="f4ef9-153">tax registration number</span></span>
  
<span data-ttu-id="f4ef9-154">tax id
</span><span class="sxs-lookup"><span data-stu-id="f4ef9-154">tax id</span></span>
  
<span data-ttu-id="f4ef9-155">NIF</span><span class="sxs-lookup"><span data-stu-id="f4ef9-155">nif</span></span>
  
<span data-ttu-id="f4ef9-156">NIF #</span><span class="sxs-lookup"><span data-stu-id="f4ef9-156">nif#</span></span>
  
<span data-ttu-id="f4ef9-157">registre de numéro nazionale</span><span class="sxs-lookup"><span data-stu-id="f4ef9-157">numéro de registre national</span></span>
  
<span data-ttu-id="f4ef9-158">numéro identificazione fiscale</span><span class="sxs-lookup"><span data-stu-id="f4ef9-158">numéro d'identification fiscale</span></span>
  
## <a name="bulgaria"></a><span data-ttu-id="f4ef9-159">Bulgaria</span><span class="sxs-lookup"><span data-stu-id="f4ef9-159">Bulgaria</span></span>

### <a name="format"></a><span data-ttu-id="f4ef9-160">Formato</span><span class="sxs-lookup"><span data-stu-id="f4ef9-160">Format</span></span>

<span data-ttu-id="f4ef9-161">Dieci cifre senza spazi e i delimitatori</span><span class="sxs-lookup"><span data-stu-id="f4ef9-161">Ten digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="f4ef9-162">Modello</span><span class="sxs-lookup"><span data-stu-id="f4ef9-162">Pattern</span></span>

<span data-ttu-id="f4ef9-163">10 cifre</span><span class="sxs-lookup"><span data-stu-id="f4ef9-163">10 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="f4ef9-164">Checksum</span><span class="sxs-lookup"><span data-stu-id="f4ef9-164">Checksum</span></span>

<span data-ttu-id="f4ef9-165">Sì</span><span class="sxs-lookup"><span data-stu-id="f4ef9-165">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="f4ef9-166">Definizione</span><span class="sxs-lookup"><span data-stu-id="f4ef9-166">Definition</span></span>

<span data-ttu-id="f4ef9-167">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="f4ef9-167">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="f4ef9-168">La funzione `Func_bulgaria_eu_tax_file_number` consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="f4ef9-168">The function  `Func_bulgaria_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="f4ef9-169">Una parola chiave da `Keywords_bulgaria_eu_tax_file_number` viene trovato.</span><span class="sxs-lookup"><span data-stu-id="f4ef9-169">A keyword from  `Keywords_bulgaria_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="f4ef9-170">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="f4ef9-170">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="f4ef9-171">La funzione `Func_bulgaria_eu_tax_file_number` consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="f4ef9-171">The function  `Func_bulgaria_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="f4ef9-172">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="f4ef9-172">Keywords</span></span>

#### <a name="keywordsbulgariaeutaxfilenumber"></a><span data-ttu-id="f4ef9-173">Keywords_bulgaria_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="f4ef9-173">Keywords_bulgaria_eu_tax_file_number</span></span>

<span data-ttu-id="f4ef9-174">bucn</span><span class="sxs-lookup"><span data-stu-id="f4ef9-174">bucn</span></span>
  
<span data-ttu-id="f4ef9-175">Uniform numero civile</span><span class="sxs-lookup"><span data-stu-id="f4ef9-175">uniform civil number</span></span>
  
<span data-ttu-id="f4ef9-176">bucn #</span><span class="sxs-lookup"><span data-stu-id="f4ef9-176">bucn#</span></span>
  
<span data-ttu-id="f4ef9-177">uniformcivilnumber #</span><span class="sxs-lookup"><span data-stu-id="f4ef9-177">uniformcivilnumber#</span></span>
  
<span data-ttu-id="f4ef9-178">Uniform id civile</span><span class="sxs-lookup"><span data-stu-id="f4ef9-178">uniform civil id</span></span>
  
<span data-ttu-id="f4ef9-179">Uniform no civile</span><span class="sxs-lookup"><span data-stu-id="f4ef9-179">uniform civil no</span></span>
  
<span data-ttu-id="f4ef9-180">egn</span><span class="sxs-lookup"><span data-stu-id="f4ef9-180">egn</span></span>
  
<span data-ttu-id="f4ef9-181">Bulgaro uniform numero civile</span><span class="sxs-lookup"><span data-stu-id="f4ef9-181">bulgarian uniform civil number</span></span>
  
<span data-ttu-id="f4ef9-182">uniformcivilno #</span><span class="sxs-lookup"><span data-stu-id="f4ef9-182">uniformcivilno#</span></span>
  
<span data-ttu-id="f4ef9-183">egn #</span><span class="sxs-lookup"><span data-stu-id="f4ef9-183">egn#</span></span>
  
<span data-ttu-id="f4ef9-184">УНИФОРМ ГРАЖДАНСКИ НОМЕР</span><span class="sxs-lookup"><span data-stu-id="f4ef9-184">униформ граждански номер</span></span>
  
<span data-ttu-id="f4ef9-185">Id униформ</span><span class="sxs-lookup"><span data-stu-id="f4ef9-185">униформ id</span></span>
  
<span data-ttu-id="f4ef9-186">Id граждански униформ</span><span class="sxs-lookup"><span data-stu-id="f4ef9-186">униформ граждански id</span></span>
  
<span data-ttu-id="f4ef9-187">УНИФОРМ ГРАЖДАНСКИ НЕ</span><span class="sxs-lookup"><span data-stu-id="f4ef9-187">униформ граждански не</span></span>
  
## <a name="croatia"></a><span data-ttu-id="f4ef9-188">Croazia</span><span class="sxs-lookup"><span data-stu-id="f4ef9-188">Croatia</span></span>

### <a name="format"></a><span data-ttu-id="f4ef9-189">Formato</span><span class="sxs-lookup"><span data-stu-id="f4ef9-189">Format</span></span>

<span data-ttu-id="f4ef9-190">11 cifre senza spazi o delimitatori</span><span class="sxs-lookup"><span data-stu-id="f4ef9-190">11 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="f4ef9-191">Modello</span><span class="sxs-lookup"><span data-stu-id="f4ef9-191">Pattern</span></span>

<span data-ttu-id="f4ef9-192">11 cifre:</span><span class="sxs-lookup"><span data-stu-id="f4ef9-192">11 digits:</span></span>
  
- <span data-ttu-id="f4ef9-193">Dieci cifre, scelte in modo casuale</span><span class="sxs-lookup"><span data-stu-id="f4ef9-193">Ten digits, randomly chosen</span></span>
    
- <span data-ttu-id="f4ef9-194">Cifra di un controllo</span><span class="sxs-lookup"><span data-stu-id="f4ef9-194">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="f4ef9-195">Checksum</span><span class="sxs-lookup"><span data-stu-id="f4ef9-195">Checksum</span></span>

<span data-ttu-id="f4ef9-196">Sì</span><span class="sxs-lookup"><span data-stu-id="f4ef9-196">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="f4ef9-197">Definizione</span><span class="sxs-lookup"><span data-stu-id="f4ef9-197">Definition</span></span>

<span data-ttu-id="f4ef9-198">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="f4ef9-198">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="f4ef9-199">La funzione `Func_croatia_eu_tax_file_number` consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="f4ef9-199">The function  `Func_croatia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="f4ef9-200">Una parola chiave da `Keywords_croatia_eu_tax_file_number` viene trovato.</span><span class="sxs-lookup"><span data-stu-id="f4ef9-200">A keyword from  `Keywords_croatia_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="f4ef9-201">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="f4ef9-201">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="f4ef9-202">La funzione `Func_croatia_eu_tax_file_number` consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="f4ef9-202">The function  `Func_croatia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="f4ef9-203">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="f4ef9-203">Keywords</span></span>

#### <a name="keywordscroatiaeutaxfilenumber"></a><span data-ttu-id="f4ef9-204">Keywords_croatia_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="f4ef9-204">Keywords_croatia_eu_tax_file_number</span></span>

<span data-ttu-id="f4ef9-205">Imposta numero</span><span class="sxs-lookup"><span data-stu-id="f4ef9-205">tax number</span></span>
  
<span data-ttu-id="f4ef9-206">Imposta</span><span class="sxs-lookup"><span data-stu-id="f4ef9-206">tax</span></span>
  
<span data-ttu-id="f4ef9-207">tax id
</span><span class="sxs-lookup"><span data-stu-id="f4ef9-207">tax id</span></span>
  
<span data-ttu-id="f4ef9-208">OID</span><span class="sxs-lookup"><span data-stu-id="f4ef9-208">oid</span></span>
  
<span data-ttu-id="f4ef9-209">OID #</span><span class="sxs-lookup"><span data-stu-id="f4ef9-209">oid#</span></span>
  
<span data-ttu-id="f4ef9-210">porezni broj</span><span class="sxs-lookup"><span data-stu-id="f4ef9-210">porezni broj</span></span>
  
## <a name="cyprus"></a><span data-ttu-id="f4ef9-211">Cipro</span><span class="sxs-lookup"><span data-stu-id="f4ef9-211">Cyprus</span></span>

### <a name="format"></a><span data-ttu-id="f4ef9-212">Formato</span><span class="sxs-lookup"><span data-stu-id="f4ef9-212">Format</span></span>

<span data-ttu-id="f4ef9-213">Otto cifre e una lettera nella serie specificata</span><span class="sxs-lookup"><span data-stu-id="f4ef9-213">Eight digits and one letter in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="f4ef9-214">Modello</span><span class="sxs-lookup"><span data-stu-id="f4ef9-214">Pattern</span></span>

<span data-ttu-id="f4ef9-215">Otto cifre e una lettera:</span><span class="sxs-lookup"><span data-stu-id="f4ef9-215">Eight digits and one letter:</span></span>
  
-  <span data-ttu-id="f4ef9-216">"0"</span><span class="sxs-lookup"><span data-stu-id="f4ef9-216">A "0"</span></span> 
    
- <span data-ttu-id="f4ef9-217">Sette cifre</span><span class="sxs-lookup"><span data-stu-id="f4ef9-217">Seven digits</span></span>
    
- <span data-ttu-id="f4ef9-218">Una lettera (maiuscole o minuscole)</span><span class="sxs-lookup"><span data-stu-id="f4ef9-218">One letter (not case-sensitive)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="f4ef9-219">Checksum</span><span class="sxs-lookup"><span data-stu-id="f4ef9-219">Checksum</span></span>

<span data-ttu-id="f4ef9-220">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="f4ef9-220">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="f4ef9-221">Definizione</span><span class="sxs-lookup"><span data-stu-id="f4ef9-221">Definition</span></span>

<span data-ttu-id="f4ef9-222">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="f4ef9-222">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="f4ef9-223">La funzione `Func_cyprus_eu_tax_file_number` consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="f4ef9-223">The function  `Func_cyprus_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="f4ef9-224">Una parola chiave da `Keywords_cyprus_eu_tax_file_number` viene trovato.</span><span class="sxs-lookup"><span data-stu-id="f4ef9-224">A keyword from  `Keywords_cyprus_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="f4ef9-225">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="f4ef9-225">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="f4ef9-226">La funzione `Func_cyprus_eu_tax_file_number` consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="f4ef9-226">The function  `Func_cyprus_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="f4ef9-227">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="f4ef9-227">Keywords</span></span>

#### <a name="keywordscypruseutaxfilenumber"></a><span data-ttu-id="f4ef9-228">Keywords_cyprus_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="f4ef9-228">Keywords_cyprus_eu_tax_file_number</span></span>

<span data-ttu-id="f4ef9-229">Imposta numero</span><span class="sxs-lookup"><span data-stu-id="f4ef9-229">tax number</span></span>
  
<span data-ttu-id="f4ef9-230">Imposta</span><span class="sxs-lookup"><span data-stu-id="f4ef9-230">tax</span></span>
  
<span data-ttu-id="f4ef9-231">tax id
</span><span class="sxs-lookup"><span data-stu-id="f4ef9-231">tax id</span></span>
  
<span data-ttu-id="f4ef9-232">codice identificativo fiscale</span><span class="sxs-lookup"><span data-stu-id="f4ef9-232">tax identification code</span></span>
  
<span data-ttu-id="f4ef9-233">TIC</span><span class="sxs-lookup"><span data-stu-id="f4ef9-233">tic</span></span>
  
<span data-ttu-id="f4ef9-234">TIC #</span><span class="sxs-lookup"><span data-stu-id="f4ef9-234">tic#</span></span>
  
<span data-ttu-id="f4ef9-235">ΑΡΙΘΜΌΣ ΦΟΡΟΛΟΓΙΚΟΎ ΜΗΤΡΏΟΥ</span><span class="sxs-lookup"><span data-stu-id="f4ef9-235">αριθμός φορολογικού μητρώου</span></span>
  
<span data-ttu-id="f4ef9-236">ΦΟΡΟΛΟΓΙΚΉ ΤΑΥΤΌΤΗΤΑ</span><span class="sxs-lookup"><span data-stu-id="f4ef9-236">φορολογική ταυτότητα</span></span>
  
<span data-ttu-id="f4ef9-237">ΚΩΔΙΚΌΣ ΦΟΡΟΛΟΓΙΚΟΎ ΜΗΤΡΏΟΥ</span><span class="sxs-lookup"><span data-stu-id="f4ef9-237">κωδικός φορολογικού μητρώου</span></span>
  
## <a name="czech-republic"></a><span data-ttu-id="f4ef9-238">Repubblica Ceca</span><span class="sxs-lookup"><span data-stu-id="f4ef9-238">Czech Republic</span></span>

### <a name="format"></a><span data-ttu-id="f4ef9-239">Formato</span><span class="sxs-lookup"><span data-stu-id="f4ef9-239">Format</span></span>

<span data-ttu-id="f4ef9-240">Nove o dieci cifre con una barra rovesciata facoltativa</span><span class="sxs-lookup"><span data-stu-id="f4ef9-240">Nine or ten digits with an optional backslash</span></span>
  
### <a name="pattern"></a><span data-ttu-id="f4ef9-241">Modello</span><span class="sxs-lookup"><span data-stu-id="f4ef9-241">Pattern</span></span>

<span data-ttu-id="f4ef9-242">Nove o dieci cifre con un backslashl facoltativi:</span><span class="sxs-lookup"><span data-stu-id="f4ef9-242">Nine or ten digits with an optional backslashl:</span></span>
  
- <span data-ttu-id="f4ef9-243">Sei cifre</span><span class="sxs-lookup"><span data-stu-id="f4ef9-243">Six digits</span></span> 
    
- <span data-ttu-id="f4ef9-244">Una barra rovesciata (facoltativa)</span><span class="sxs-lookup"><span data-stu-id="f4ef9-244">A backslash (optional)</span></span>
    
- <span data-ttu-id="f4ef9-245">Tre o quattro cifre</span><span class="sxs-lookup"><span data-stu-id="f4ef9-245">Three or four digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="f4ef9-246">Checksum</span><span class="sxs-lookup"><span data-stu-id="f4ef9-246">Checksum</span></span>

<span data-ttu-id="f4ef9-247">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="f4ef9-247">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="f4ef9-248">Definizione</span><span class="sxs-lookup"><span data-stu-id="f4ef9-248">Definition</span></span>

<span data-ttu-id="f4ef9-249">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="f4ef9-249">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="f4ef9-250">L'espressione regolare `Regex_czech_republic_eu_tax_file_number` consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="f4ef9-250">The regular expression  `Regex_czech_republic_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="f4ef9-251">Una parola chiave da `Keywords_czech_republic_eu_tax_file_number` viene trovato.</span><span class="sxs-lookup"><span data-stu-id="f4ef9-251">A keyword from  `Keywords_czech_republic_eu_tax_file_number` is found.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_czech_republic_eu_tax_file_number" />
          <Match idRef="Keywords_czech_republic_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="f4ef9-252">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="f4ef9-252">Keywords</span></span>

#### <a name="keywordsczechrepubliceutaxfilenumber"></a><span data-ttu-id="f4ef9-253">Keywords_czech_republic_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="f4ef9-253">Keywords_czech_republic_eu_tax_file_number</span></span>

<span data-ttu-id="f4ef9-254">Imposta numero</span><span class="sxs-lookup"><span data-stu-id="f4ef9-254">tax number</span></span>
  
<span data-ttu-id="f4ef9-255">Imposta</span><span class="sxs-lookup"><span data-stu-id="f4ef9-255">tax</span></span>
  
<span data-ttu-id="f4ef9-256">tax id
</span><span class="sxs-lookup"><span data-stu-id="f4ef9-256">tax id</span></span>
  
<span data-ttu-id="f4ef9-257">numero personale</span><span class="sxs-lookup"><span data-stu-id="f4ef9-257">personal number</span></span>
  
<span data-ttu-id="f4ef9-258">daňové číslo</span><span class="sxs-lookup"><span data-stu-id="f4ef9-258">daňové číslo</span></span>
  
<span data-ttu-id="f4ef9-259">osobní číslo</span><span class="sxs-lookup"><span data-stu-id="f4ef9-259">osobní číslo</span></span>
  
## <a name="denmark"></a><span data-ttu-id="f4ef9-260">Danimarca</span><span class="sxs-lookup"><span data-stu-id="f4ef9-260">Denmark</span></span>

### <a name="format"></a><span data-ttu-id="f4ef9-261">Formato</span><span class="sxs-lookup"><span data-stu-id="f4ef9-261">Format</span></span>

<span data-ttu-id="f4ef9-262">Dieci cifre che contiene un segno meno</span><span class="sxs-lookup"><span data-stu-id="f4ef9-262">Ten digits containing a hyphen</span></span>
  
### <a name="pattern"></a><span data-ttu-id="f4ef9-263">Modello</span><span class="sxs-lookup"><span data-stu-id="f4ef9-263">Pattern</span></span>

<span data-ttu-id="f4ef9-264">Dieci cifre che contiene un hyphenl:</span><span class="sxs-lookup"><span data-stu-id="f4ef9-264">Ten digits containing a hyphenl:</span></span>
  
-  <span data-ttu-id="f4ef9-265">Sei cifre che corrispondono alla data di nascita (DDMMYY)</span><span class="sxs-lookup"><span data-stu-id="f4ef9-265">Six digits that correspond to the birth date (DDMMYY)</span></span> 
    
- <span data-ttu-id="f4ef9-266">Una lineetta</span><span class="sxs-lookup"><span data-stu-id="f4ef9-266">A hyphen</span></span>
    
- <span data-ttu-id="f4ef9-267">Quattro cifre che corrispondono a un numero di sequenza in cui la prima cifra corrisponde a century di nascita e l'ultima cifra corrisponde in genere dell'individuo (dispari per maschile e anche per femmina)</span><span class="sxs-lookup"><span data-stu-id="f4ef9-267">Four digits that correspond to a sequence number where the first digit corresponds to the century of birth and the last digit corresponds to the individual's gender (odd for male and even for female)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="f4ef9-268">Checksum</span><span class="sxs-lookup"><span data-stu-id="f4ef9-268">Checksum</span></span>

<span data-ttu-id="f4ef9-269">Sì</span><span class="sxs-lookup"><span data-stu-id="f4ef9-269">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="f4ef9-270">Definizione</span><span class="sxs-lookup"><span data-stu-id="f4ef9-270">Definition</span></span>

<span data-ttu-id="f4ef9-271">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="f4ef9-271">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="f4ef9-272">La funzione `Func_denmark_eu_tax_file_number` consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="f4ef9-272">The function  `Func_denmark_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="f4ef9-273">Una parola chiave da `Keywords_denmark_eu_tax_file_number` viene trovato.</span><span class="sxs-lookup"><span data-stu-id="f4ef9-273">A keyword from  `Keywords_denmark_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="f4ef9-274">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="f4ef9-274">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="f4ef9-275">La funzione `Func_denmark_eu_tax_file_number` consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="f4ef9-275">The function  `Func_denmark_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="f4ef9-276">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="f4ef9-276">Keywords</span></span>

#### <a name="keywordsdenmarkeutaxfilenumber"></a><span data-ttu-id="f4ef9-277">Keywords_denmark_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="f4ef9-277">Keywords_denmark_eu_tax_file_number</span></span>

<span data-ttu-id="f4ef9-278">Imposta numero</span><span class="sxs-lookup"><span data-stu-id="f4ef9-278">tax number</span></span>
  
<span data-ttu-id="f4ef9-279">Imposta</span><span class="sxs-lookup"><span data-stu-id="f4ef9-279">tax</span></span>
  
<span data-ttu-id="f4ef9-280">tax id
</span><span class="sxs-lookup"><span data-stu-id="f4ef9-280">tax id</span></span>
  
<span data-ttu-id="f4ef9-281">numero CPR</span><span class="sxs-lookup"><span data-stu-id="f4ef9-281">cpr number</span></span>
  
<span data-ttu-id="f4ef9-282">CPR #</span><span class="sxs-lookup"><span data-stu-id="f4ef9-282">cpr#</span></span>
  
<span data-ttu-id="f4ef9-283">skat nummer</span><span class="sxs-lookup"><span data-stu-id="f4ef9-283">skat nummer</span></span>
  
<span data-ttu-id="f4ef9-284">id skat</span><span class="sxs-lookup"><span data-stu-id="f4ef9-284">skat id</span></span>
  
## <a name="estonia"></a><span data-ttu-id="f4ef9-285">Estonia</span><span class="sxs-lookup"><span data-stu-id="f4ef9-285">Estonia</span></span>

### <a name="format"></a><span data-ttu-id="f4ef9-286">Formato</span><span class="sxs-lookup"><span data-stu-id="f4ef9-286">Format</span></span>

<span data-ttu-id="f4ef9-287">11 cifre senza spazi o delimitatori</span><span class="sxs-lookup"><span data-stu-id="f4ef9-287">11 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="f4ef9-288">Modello</span><span class="sxs-lookup"><span data-stu-id="f4ef9-288">Pattern</span></span>

<span data-ttu-id="f4ef9-289">11 cifre:</span><span class="sxs-lookup"><span data-stu-id="f4ef9-289">11 digits:</span></span>
  
-  <span data-ttu-id="f4ef9-290">Una cifra che corrisponde al sesso e century di nascita in un numero dispari indica maschile e il numero pari femmina nel modo seguente: 1, 2 per century diciannovesimo; 3, 4 per century ventesimo; e 5, 6 per century ventunesimo</span><span class="sxs-lookup"><span data-stu-id="f4ef9-290">One digit that corresponds to gender and century of birth where an odd number indicates male and the even number indicates female as follows: 1, 2 for the 19th century; 3, 4 for the 20th century; and 5, 6 for the 21st century</span></span> 
    
- <span data-ttu-id="f4ef9-291">Sei cifre che corrispondono alla data di nascita (AAMMGG)</span><span class="sxs-lookup"><span data-stu-id="f4ef9-291">Six digits that correspond to birth date (YYMMDD)</span></span>
    
- <span data-ttu-id="f4ef9-292">Tre cifre che corrispondono a un numero di serie che separa le persone nati nella stessa data</span><span class="sxs-lookup"><span data-stu-id="f4ef9-292">Three digits that correspond to a serial number separating persons born on the same date</span></span>
    
- <span data-ttu-id="f4ef9-293">Cifra di un controllo</span><span class="sxs-lookup"><span data-stu-id="f4ef9-293">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="f4ef9-294">Checksum</span><span class="sxs-lookup"><span data-stu-id="f4ef9-294">Checksum</span></span>

<span data-ttu-id="f4ef9-295">Sì</span><span class="sxs-lookup"><span data-stu-id="f4ef9-295">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="f4ef9-296">Definizione</span><span class="sxs-lookup"><span data-stu-id="f4ef9-296">Definition</span></span>

<span data-ttu-id="f4ef9-297">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="f4ef9-297">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="f4ef9-298">La funzione `Func_estonia_eu_tax_file_number` consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="f4ef9-298">The function  `Func_estonia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="f4ef9-299">Una parola chiave da `Keywords_estonia_eu_tax_file_number` viene trovato.</span><span class="sxs-lookup"><span data-stu-id="f4ef9-299">A keyword from  `Keywords_estonia_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="f4ef9-300">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="f4ef9-300">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="f4ef9-301">La funzione `Func_estonia_eu_tax_file_number` consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="f4ef9-301">The function  `Func_estonia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="f4ef9-302">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="f4ef9-302">Keywords</span></span>

#### <a name="keywordsestoniaeutaxfilenumber"></a><span data-ttu-id="f4ef9-303">Keywords_estonia_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="f4ef9-303">Keywords_estonia_eu_tax_file_number</span></span>

<span data-ttu-id="f4ef9-304">Imposta numero</span><span class="sxs-lookup"><span data-stu-id="f4ef9-304">tax number</span></span>
  
<span data-ttu-id="f4ef9-305">Imposta</span><span class="sxs-lookup"><span data-stu-id="f4ef9-305">tax</span></span>
  
<span data-ttu-id="f4ef9-306">tax id
</span><span class="sxs-lookup"><span data-stu-id="f4ef9-306">tax id</span></span>
  
<span data-ttu-id="f4ef9-307">codice personale</span><span class="sxs-lookup"><span data-stu-id="f4ef9-307">personal code</span></span>
  
<span data-ttu-id="f4ef9-308">maksunumber</span><span class="sxs-lookup"><span data-stu-id="f4ef9-308">maksunumber</span></span>
  
<span data-ttu-id="f4ef9-309">id maksu</span><span class="sxs-lookup"><span data-stu-id="f4ef9-309">maksu id</span></span>
  
<span data-ttu-id="f4ef9-310">isikukood</span><span class="sxs-lookup"><span data-stu-id="f4ef9-310">isikukood</span></span>
  
## <a name="finland"></a><span data-ttu-id="f4ef9-311">Finlandia</span><span class="sxs-lookup"><span data-stu-id="f4ef9-311">Finland</span></span>

### <a name="format"></a><span data-ttu-id="f4ef9-312">Formato</span><span class="sxs-lookup"><span data-stu-id="f4ef9-312">Format</span></span>

<span data-ttu-id="f4ef9-313">Una combinazione di caratteri 11 cifre, lettere, e plus e segno meno</span><span class="sxs-lookup"><span data-stu-id="f4ef9-313">An 11-character combination of digits, letters, and plus and minus sign</span></span>
  
### <a name="pattern"></a><span data-ttu-id="f4ef9-314">Modello</span><span class="sxs-lookup"><span data-stu-id="f4ef9-314">Pattern</span></span>

<span data-ttu-id="f4ef9-315">Una combinazione di caratteri 11 cifre, lettere, e plus e segno meno:</span><span class="sxs-lookup"><span data-stu-id="f4ef9-315">An 11-character combination of digits, letters, and plus and minus sign:</span></span>
  
- <span data-ttu-id="f4ef9-316">Sei cifre</span><span class="sxs-lookup"><span data-stu-id="f4ef9-316">Six digits</span></span>
    
- <span data-ttu-id="f4ef9-317">Uno dei seguenti: un segno di addizione, un segno di sottrazione o la lettera "A" (non maiuscole/minuscole) dove si intende il segno di addizione nati tra 1800 1899 meno accedere mezzi nati tra 1900-1999 e "A" indica nati 2000 e dopo</span><span class="sxs-lookup"><span data-stu-id="f4ef9-317">One of the following: a plus sign, a minus sign, or the letter "A" (not case sensitive) where the plus sign means born between 1800-1899, the minus sign means born between 1900-1999, and "A" means born 2000 and after</span></span>
    
- <span data-ttu-id="f4ef9-318">Tre cifre</span><span class="sxs-lookup"><span data-stu-id="f4ef9-318">Three digits</span></span>
    
- <span data-ttu-id="f4ef9-319">Una lettera o un numero</span><span class="sxs-lookup"><span data-stu-id="f4ef9-319">One letter or one number</span></span>
    
### <a name="checksum"></a><span data-ttu-id="f4ef9-320">Checksum</span><span class="sxs-lookup"><span data-stu-id="f4ef9-320">Checksum</span></span>

<span data-ttu-id="f4ef9-321">Sì</span><span class="sxs-lookup"><span data-stu-id="f4ef9-321">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="f4ef9-322">Definizione</span><span class="sxs-lookup"><span data-stu-id="f4ef9-322">Definition</span></span>

<span data-ttu-id="f4ef9-323">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="f4ef9-323">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="f4ef9-324">La funzione `Func_finland_eu_tax_file_number` consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="f4ef9-324">The function  `Func_finland_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="f4ef9-325">Una parola chiave da `Keywords_finland_eu_tax_file_number` viene trovato.</span><span class="sxs-lookup"><span data-stu-id="f4ef9-325">A keyword from  `Keywords_finland_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="f4ef9-326">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="f4ef9-326">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="f4ef9-327">La funzione `Func_finland_eu_tax_file_number` consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="f4ef9-327">The function  `Func_finland_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="f4ef9-328">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="f4ef9-328">Keywords</span></span>

#### <a name="keywordsfinlandeutaxfilenumber"></a><span data-ttu-id="f4ef9-329">Keywords_finland_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="f4ef9-329">Keywords_finland_eu_tax_file_number</span></span>

<span data-ttu-id="f4ef9-330">identification number
</span><span class="sxs-lookup"><span data-stu-id="f4ef9-330">identification number</span></span>
  
<span data-ttu-id="f4ef9-331">id personale</span><span class="sxs-lookup"><span data-stu-id="f4ef9-331">personal id</span></span>
  
<span data-ttu-id="f4ef9-332">numero di identità</span><span class="sxs-lookup"><span data-stu-id="f4ef9-332">identity number</span></span>
  
<span data-ttu-id="f4ef9-333">numero id nazionale Finlandia</span><span class="sxs-lookup"><span data-stu-id="f4ef9-333">finnish national id number</span></span>
  
<span data-ttu-id="f4ef9-334">personalidnumber #</span><span class="sxs-lookup"><span data-stu-id="f4ef9-334">personalidnumber#</span></span>
  
<span data-ttu-id="f4ef9-335">numero identificativo nazionale</span><span class="sxs-lookup"><span data-stu-id="f4ef9-335">national identification number</span></span>
  
<span data-ttu-id="f4ef9-336">numero ID</span><span class="sxs-lookup"><span data-stu-id="f4ef9-336">id number</span></span>
  
<span data-ttu-id="f4ef9-337">id nazionale non.</span><span class="sxs-lookup"><span data-stu-id="f4ef9-337">national id no.</span></span>
  
<span data-ttu-id="f4ef9-338">numero identificativo nazionale</span><span class="sxs-lookup"><span data-stu-id="f4ef9-338">national id number</span></span>
  
<span data-ttu-id="f4ef9-339">ID non</span><span class="sxs-lookup"><span data-stu-id="f4ef9-339">id no</span></span>
  
<span data-ttu-id="f4ef9-340">tunnistenumero</span><span class="sxs-lookup"><span data-stu-id="f4ef9-340">tunnistenumero</span></span>
  
<span data-ttu-id="f4ef9-341">henkilötunnus</span><span class="sxs-lookup"><span data-stu-id="f4ef9-341">henkilötunnus</span></span>
  
<span data-ttu-id="f4ef9-342">yksilöllinen henkilökohtainen tunnistenumero</span><span class="sxs-lookup"><span data-stu-id="f4ef9-342">yksilöllinen henkilökohtainen tunnistenumero</span></span>
  
<span data-ttu-id="f4ef9-343">ainutlaatuinen henkilökohtainen tunnus</span><span class="sxs-lookup"><span data-stu-id="f4ef9-343">ainutlaatuinen henkilökohtainen tunnus</span></span>
  
<span data-ttu-id="f4ef9-344">numero identiteetti</span><span class="sxs-lookup"><span data-stu-id="f4ef9-344">identiteetti numero</span></span>
  
<span data-ttu-id="f4ef9-345">suomen kansallinen henkilötunnus</span><span class="sxs-lookup"><span data-stu-id="f4ef9-345">suomen kansallinen henkilötunnus</span></span>
  
<span data-ttu-id="f4ef9-346">henkilötunnusnumero #</span><span class="sxs-lookup"><span data-stu-id="f4ef9-346">henkilötunnusnumero#</span></span>
  
<span data-ttu-id="f4ef9-347">kansallisen tunnistenumero</span><span class="sxs-lookup"><span data-stu-id="f4ef9-347">kansallisen tunnistenumero</span></span>
  
<span data-ttu-id="f4ef9-348">tunnusnumero</span><span class="sxs-lookup"><span data-stu-id="f4ef9-348">tunnusnumero</span></span>
  
<span data-ttu-id="f4ef9-349">numero di tunnus kansallinen</span><span class="sxs-lookup"><span data-stu-id="f4ef9-349">kansallinen tunnus numero</span></span>
  
## <a name="france"></a><span data-ttu-id="f4ef9-350">Francia</span><span class="sxs-lookup"><span data-stu-id="f4ef9-350">France</span></span>

### <a name="format"></a><span data-ttu-id="f4ef9-351">Formato</span><span class="sxs-lookup"><span data-stu-id="f4ef9-351">Format</span></span>

<span data-ttu-id="f4ef9-352">13 cifre per singoli utenti e i numeri di nove per le entità</span><span class="sxs-lookup"><span data-stu-id="f4ef9-352">13 digits for individuals and nine digits for entities</span></span>
  
### <a name="pattern"></a><span data-ttu-id="f4ef9-353">Modello</span><span class="sxs-lookup"><span data-stu-id="f4ef9-353">Pattern</span></span>

<span data-ttu-id="f4ef9-354">13 cifre per singoli utenti:</span><span class="sxs-lookup"><span data-stu-id="f4ef9-354">13 digits for individuals:</span></span>
  
- <span data-ttu-id="f4ef9-355">Una cifra che deve essere 0, 1, 2 o 3</span><span class="sxs-lookup"><span data-stu-id="f4ef9-355">One digit that must be 0, 1, 2, or 3</span></span>
    
- <span data-ttu-id="f4ef9-356">12 cifre</span><span class="sxs-lookup"><span data-stu-id="f4ef9-356">12 digits</span></span>
    
<span data-ttu-id="f4ef9-357">Nove cifre per le entità</span><span class="sxs-lookup"><span data-stu-id="f4ef9-357">Nine digits for entities</span></span>
  
### <a name="checksum"></a><span data-ttu-id="f4ef9-358">Checksum</span><span class="sxs-lookup"><span data-stu-id="f4ef9-358">Checksum</span></span>

<span data-ttu-id="f4ef9-359">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="f4ef9-359">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="f4ef9-360">Definizione</span><span class="sxs-lookup"><span data-stu-id="f4ef9-360">Definition</span></span>

<span data-ttu-id="f4ef9-361">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="f4ef9-361">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="f4ef9-362">La funzione `Func_france_eu_tax_file_number` consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="f4ef9-362">The function  `Func_france_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="f4ef9-363">Una parola chiave da `Keywords_france_eu_tax_file_number` viene trovato.</span><span class="sxs-lookup"><span data-stu-id="f4ef9-363">A keyword from  `Keywords_france_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="f4ef9-364">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="f4ef9-364">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="f4ef9-365">La funzione `Func_france_eu_tax_file_number` consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="f4ef9-365">The function  `Func_france_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="f4ef9-366">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="f4ef9-366">Keywords</span></span>

#### <a name="keywordsfranceeutaxfilenumber"></a><span data-ttu-id="f4ef9-367">Keywords_france_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="f4ef9-367">Keywords_france_eu_tax_file_number</span></span>

<span data-ttu-id="f4ef9-368">numero di identificazione fiscale</span><span class="sxs-lookup"><span data-stu-id="f4ef9-368">tax identification number</span></span>
  
<span data-ttu-id="f4ef9-369">Imposta numero</span><span class="sxs-lookup"><span data-stu-id="f4ef9-369">tax number</span></span>
  
<span data-ttu-id="f4ef9-370">tax id
</span><span class="sxs-lookup"><span data-stu-id="f4ef9-370">tax id</span></span>
  
<span data-ttu-id="f4ef9-371">numéro identificazione fiscale</span><span class="sxs-lookup"><span data-stu-id="f4ef9-371">numéro d'identification fiscale</span></span>
  
## <a name="germany"></a><span data-ttu-id="f4ef9-372">Germania</span><span class="sxs-lookup"><span data-stu-id="f4ef9-372">Germany</span></span>

### <a name="format"></a><span data-ttu-id="f4ef9-373">Formato</span><span class="sxs-lookup"><span data-stu-id="f4ef9-373">Format</span></span>

<span data-ttu-id="f4ef9-374">11 cifre senza spazi e i delimitatori</span><span class="sxs-lookup"><span data-stu-id="f4ef9-374">11 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="f4ef9-375">Modello</span><span class="sxs-lookup"><span data-stu-id="f4ef9-375">Pattern</span></span>

<span data-ttu-id="f4ef9-376">11 cifre:</span><span class="sxs-lookup"><span data-stu-id="f4ef9-376">11 digits :</span></span>
  
-  <span data-ttu-id="f4ef9-377">Dieci cifre</span><span class="sxs-lookup"><span data-stu-id="f4ef9-377">Ten digits</span></span> 
    
- <span data-ttu-id="f4ef9-378">Cifra di un controllo</span><span class="sxs-lookup"><span data-stu-id="f4ef9-378">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="f4ef9-379">Checksum</span><span class="sxs-lookup"><span data-stu-id="f4ef9-379">Checksum</span></span>

<span data-ttu-id="f4ef9-380">Sì</span><span class="sxs-lookup"><span data-stu-id="f4ef9-380">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="f4ef9-381">Definizione</span><span class="sxs-lookup"><span data-stu-id="f4ef9-381">Definition</span></span>

<span data-ttu-id="f4ef9-382">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="f4ef9-382">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="f4ef9-383">La funzione `Func_germany_eu_tax_file_number` consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="f4ef9-383">The function  `Func_germany_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="f4ef9-384">Una parola chiave da `Keywords_germany_eu_tax_file_number` viene trovato.</span><span class="sxs-lookup"><span data-stu-id="f4ef9-384">A keyword from  `Keywords_germany_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="f4ef9-385">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="f4ef9-385">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="f4ef9-386">La funzione `Func_germany_eu_tax_file_number` consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="f4ef9-386">The function  `Func_germany_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="f4ef9-387">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="f4ef9-387">Keywords</span></span>

#### <a name="keywordsgermanyeutaxfilenumber"></a><span data-ttu-id="f4ef9-388">Keywords_germany_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="f4ef9-388">Keywords_germany_eu_tax_file_number</span></span>

<span data-ttu-id="f4ef9-389">Imposta numero</span><span class="sxs-lookup"><span data-stu-id="f4ef9-389">tax number</span></span>
  
<span data-ttu-id="f4ef9-390">imposte no.</span><span class="sxs-lookup"><span data-stu-id="f4ef9-390">tax no.</span></span>
  
<span data-ttu-id="f4ef9-391">taxno #</span><span class="sxs-lookup"><span data-stu-id="f4ef9-391">taxno#</span></span>
  
<span data-ttu-id="f4ef9-392">Numero imposta #</span><span class="sxs-lookup"><span data-stu-id="f4ef9-392">taxnumber#</span></span>
  
<span data-ttu-id="f4ef9-393">Numero imposta</span><span class="sxs-lookup"><span data-stu-id="f4ef9-393">taxnumber</span></span>
  
<span data-ttu-id="f4ef9-394">tax id
</span><span class="sxs-lookup"><span data-stu-id="f4ef9-394">tax id</span></span>
  
<span data-ttu-id="f4ef9-395">taxid #</span><span class="sxs-lookup"><span data-stu-id="f4ef9-395">taxid#</span></span>
  
<span data-ttu-id="f4ef9-396">numero di identificazione fiscale</span><span class="sxs-lookup"><span data-stu-id="f4ef9-396">tax identification number</span></span>
  
<span data-ttu-id="f4ef9-397">Identificazione delle imposte non.</span><span class="sxs-lookup"><span data-stu-id="f4ef9-397">tax identification no.</span></span>
  
<span data-ttu-id="f4ef9-398">steuernummer</span><span class="sxs-lookup"><span data-stu-id="f4ef9-398">steuernummer</span></span>
  
<span data-ttu-id="f4ef9-399">id steuer</span><span class="sxs-lookup"><span data-stu-id="f4ef9-399">steuer id</span></span>
  
<span data-ttu-id="f4ef9-400">steueridentifikationsnummer</span><span class="sxs-lookup"><span data-stu-id="f4ef9-400">steueridentifikationsnummer</span></span>
  
## <a name="greece"></a><span data-ttu-id="f4ef9-401">Grecia</span><span class="sxs-lookup"><span data-stu-id="f4ef9-401">Greece</span></span>

### <a name="format"></a><span data-ttu-id="f4ef9-402">Formato</span><span class="sxs-lookup"><span data-stu-id="f4ef9-402">Format</span></span>

<span data-ttu-id="f4ef9-403">Nove cifre senza spazi e i delimitatori</span><span class="sxs-lookup"><span data-stu-id="f4ef9-403">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="f4ef9-404">Modello</span><span class="sxs-lookup"><span data-stu-id="f4ef9-404">Pattern</span></span>

<span data-ttu-id="f4ef9-405">9 cifre</span><span class="sxs-lookup"><span data-stu-id="f4ef9-405">Nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="f4ef9-406">Checksum</span><span class="sxs-lookup"><span data-stu-id="f4ef9-406">Checksum</span></span>

<span data-ttu-id="f4ef9-407">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="f4ef9-407">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="f4ef9-408">Definizione</span><span class="sxs-lookup"><span data-stu-id="f4ef9-408">Definition</span></span>

<span data-ttu-id="f4ef9-409">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="f4ef9-409">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="f4ef9-410">L'espressione regolare `Regex_greece_eu_tax_file_number` consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="f4ef9-410">The regular expression  `Regex_greece_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="f4ef9-411">Una parola chiave da `Keywords_greece_eu_tax_file_number` viene trovato.</span><span class="sxs-lookup"><span data-stu-id="f4ef9-411">A keyword from  `Keywords_greece_eu_tax_file_number` is found.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_greece_eu_tax_file_number" />
          <Match idRef="Keywords_greece_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="f4ef9-412">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="f4ef9-412">Keywords</span></span>

#### <a name="keywordsgreeceeutaxfilenumber"></a><span data-ttu-id="f4ef9-413">Keywords_greece_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="f4ef9-413">Keywords_greece_eu_tax_file_number</span></span>

<span data-ttu-id="f4ef9-414">afm</span><span class="sxs-lookup"><span data-stu-id="f4ef9-414">afm</span></span>
  
<span data-ttu-id="f4ef9-415">tin
</span><span class="sxs-lookup"><span data-stu-id="f4ef9-415">tin</span></span>
  
<span data-ttu-id="f4ef9-416">id imposta non.</span><span class="sxs-lookup"><span data-stu-id="f4ef9-416">tax id no.</span></span>
  
<span data-ttu-id="f4ef9-417">id imposta non</span><span class="sxs-lookup"><span data-stu-id="f4ef9-417">tax id no</span></span>
  
<span data-ttu-id="f4ef9-418">numero di identificazione fiscale</span><span class="sxs-lookup"><span data-stu-id="f4ef9-418">tax identification number</span></span>
  
<span data-ttu-id="f4ef9-419">numero del Registro di sistema fiscale</span><span class="sxs-lookup"><span data-stu-id="f4ef9-419">tax registry number</span></span>
  
<span data-ttu-id="f4ef9-420">imposte non del Registro di sistema.</span><span class="sxs-lookup"><span data-stu-id="f4ef9-420">tax registry no.</span></span>
  
<span data-ttu-id="f4ef9-421">afm #</span><span class="sxs-lookup"><span data-stu-id="f4ef9-421">afm#</span></span>
  
<span data-ttu-id="f4ef9-422">ID #</span><span class="sxs-lookup"><span data-stu-id="f4ef9-422">tin#</span></span>
  
<span data-ttu-id="f4ef9-423">taxidno #</span><span class="sxs-lookup"><span data-stu-id="f4ef9-423">taxidno#</span></span>
  
<span data-ttu-id="f4ef9-424">taxregistryno #</span><span class="sxs-lookup"><span data-stu-id="f4ef9-424">taxregistryno#</span></span>
  
<span data-ttu-id="f4ef9-425">ΑΡΙΘΜΌΣ ΦΟΡΟΛΟΓΙΚΟΎ ΜΗΤΡΏΟΥ</span><span class="sxs-lookup"><span data-stu-id="f4ef9-425">αριθμός φορολογικού μητρώου</span></span>
  
<span data-ttu-id="f4ef9-426">aφμ</span><span class="sxs-lookup"><span data-stu-id="f4ef9-426">aφμ</span></span>
  
<span data-ttu-id="f4ef9-427">aφμ αριθμός</span><span class="sxs-lookup"><span data-stu-id="f4ef9-427">aφμ αριθμός</span></span>
  
<span data-ttu-id="f4ef9-428">ΦΟΡΟΛΟΓΙΚΟΎ ΜΗΤΡΏΟΥ ΝΟ.</span><span class="sxs-lookup"><span data-stu-id="f4ef9-428">φορολογικού μητρώου νο.</span></span>
  
<span data-ttu-id="f4ef9-429">ΤΟΝ ΑΡΙΘΜΌ ΦΟΡΟΛΟΓΙΚΟΎ ΜΗΤΡΏΟΥ</span><span class="sxs-lookup"><span data-stu-id="f4ef9-429">τον αριθμό φορολογικού μητρώου</span></span>
  
## <a name="hungary"></a><span data-ttu-id="f4ef9-430">Ungheria</span><span class="sxs-lookup"><span data-stu-id="f4ef9-430">Hungary</span></span>

### <a name="format"></a><span data-ttu-id="f4ef9-431">Formato</span><span class="sxs-lookup"><span data-stu-id="f4ef9-431">Format</span></span>

<span data-ttu-id="f4ef9-432">Dieci cifre senza spazi o delimitatori</span><span class="sxs-lookup"><span data-stu-id="f4ef9-432">Ten digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="f4ef9-433">Modello</span><span class="sxs-lookup"><span data-stu-id="f4ef9-433">Pattern</span></span>

<span data-ttu-id="f4ef9-434">Dieci cifre:</span><span class="sxs-lookup"><span data-stu-id="f4ef9-434">Ten digits:</span></span>
  
-  <span data-ttu-id="f4ef9-435">Una cifra che deve essere "8"</span><span class="sxs-lookup"><span data-stu-id="f4ef9-435">One digit that must be "8"</span></span> 
    
- <span data-ttu-id="f4ef9-436">Cinque cifre che corrispondono al numero di giorni compresi tra la data 01/01/1867 e la data di nascita dei singoli</span><span class="sxs-lookup"><span data-stu-id="f4ef9-436">Five digits that correspond to the number of days between the date 01/01/1867 and the date of the birth of the individual</span></span>
    
- <span data-ttu-id="f4ef9-437">Tre cifre che corrispondono al numero generato casualmente per distinguere i singoli utenti nati nello stesso giorno</span><span class="sxs-lookup"><span data-stu-id="f4ef9-437">Three digits that correspond to the number generated by chance to differentiate individuals born on the same day</span></span>
    
- <span data-ttu-id="f4ef9-438">Cifra di un controllo</span><span class="sxs-lookup"><span data-stu-id="f4ef9-438">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="f4ef9-439">Checksum</span><span class="sxs-lookup"><span data-stu-id="f4ef9-439">Checksum</span></span>

<span data-ttu-id="f4ef9-440">Sì</span><span class="sxs-lookup"><span data-stu-id="f4ef9-440">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="f4ef9-441">Definizione</span><span class="sxs-lookup"><span data-stu-id="f4ef9-441">Definition</span></span>

<span data-ttu-id="f4ef9-442">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="f4ef9-442">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="f4ef9-443">La funzione `Func_hungary_eu_tax_file_number` consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="f4ef9-443">The function  `Func_hungary_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="f4ef9-444">Una parola chiave da `Keywords_hungary_eu_tax_file_number` viene trovato.</span><span class="sxs-lookup"><span data-stu-id="f4ef9-444">A keyword from  `Keywords_hungary_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="f4ef9-445">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="f4ef9-445">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="f4ef9-446">La funzione `Func_hungary_eu_tax_file_number` consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="f4ef9-446">The function  `Func_hungary_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="f4ef9-447">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="f4ef9-447">Keywords</span></span>

#### <a name="keywordshungaryeutaxfilenumber"></a><span data-ttu-id="f4ef9-448">Keywords_hungary_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="f4ef9-448">Keywords_hungary_eu_tax_file_number</span></span>

<span data-ttu-id="f4ef9-449">numero di identificazione fiscale ungherese</span><span class="sxs-lookup"><span data-stu-id="f4ef9-449">hungarian tax identification number</span></span>
  
<span data-ttu-id="f4ef9-450">ID ungherese</span><span class="sxs-lookup"><span data-stu-id="f4ef9-450">hungarian tin</span></span>
  
<span data-ttu-id="f4ef9-451">codice fiscale</span><span class="sxs-lookup"><span data-stu-id="f4ef9-451">tax id number</span></span>
  
<span data-ttu-id="f4ef9-452">numero IVA</span><span class="sxs-lookup"><span data-stu-id="f4ef9-452">vat number</span></span>
  
<span data-ttu-id="f4ef9-453">Imposta autorità non</span><span class="sxs-lookup"><span data-stu-id="f4ef9-453">tax authority no</span></span>
  
<span data-ttu-id="f4ef9-454">codice fiscale identità fiscale</span><span class="sxs-lookup"><span data-stu-id="f4ef9-454">tax id tax identity number</span></span>
  
<span data-ttu-id="f4ef9-455">taxidnumber #</span><span class="sxs-lookup"><span data-stu-id="f4ef9-455">taxidnumber#</span></span>
  
<span data-ttu-id="f4ef9-456">ID #</span><span class="sxs-lookup"><span data-stu-id="f4ef9-456">tin#</span></span>
  
<span data-ttu-id="f4ef9-457">hungatiantin #</span><span class="sxs-lookup"><span data-stu-id="f4ef9-457">hungatiantin#</span></span>
  
<span data-ttu-id="f4ef9-458">Identificazione delle imposte non</span><span class="sxs-lookup"><span data-stu-id="f4ef9-458">tax identification no</span></span>
  
<span data-ttu-id="f4ef9-459">taxidno #</span><span class="sxs-lookup"><span data-stu-id="f4ef9-459">taxidno#</span></span>
  
<span data-ttu-id="f4ef9-460">adóazonosító szám</span><span class="sxs-lookup"><span data-stu-id="f4ef9-460">adóazonosító szám</span></span>
  
<span data-ttu-id="f4ef9-461">adószám</span><span class="sxs-lookup"><span data-stu-id="f4ef9-461">adószám</span></span>
  
<span data-ttu-id="f4ef9-462">adóhatóság szám</span><span class="sxs-lookup"><span data-stu-id="f4ef9-462">adóhatóság szám</span></span>
  
## <a name="ireland"></a><span data-ttu-id="f4ef9-463">Irlanda</span><span class="sxs-lookup"><span data-stu-id="f4ef9-463">Ireland</span></span>

### <a name="format"></a><span data-ttu-id="f4ef9-464">Formato</span><span class="sxs-lookup"><span data-stu-id="f4ef9-464">Format</span></span>

<span data-ttu-id="f4ef9-465">Sette cifre seguite da una lettera senza spazi o delimitatori</span><span class="sxs-lookup"><span data-stu-id="f4ef9-465">Seven digits followed by a letter with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="f4ef9-466">Modello</span><span class="sxs-lookup"><span data-stu-id="f4ef9-466">Pattern</span></span>

<span data-ttu-id="f4ef9-467">Sette cifre seguite da una lettera:</span><span class="sxs-lookup"><span data-stu-id="f4ef9-467">Seven digits followed by a letter:</span></span>
  
-  <span data-ttu-id="f4ef9-468">Sette cifre</span><span class="sxs-lookup"><span data-stu-id="f4ef9-468">Seven digits</span></span> 
    
- <span data-ttu-id="f4ef9-469">Una lettera (maiuscole o minuscole)</span><span class="sxs-lookup"><span data-stu-id="f4ef9-469">One letter (not case-sensitive)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="f4ef9-470">Checksum</span><span class="sxs-lookup"><span data-stu-id="f4ef9-470">Checksum</span></span>

<span data-ttu-id="f4ef9-471">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="f4ef9-471">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="f4ef9-472">Definizione</span><span class="sxs-lookup"><span data-stu-id="f4ef9-472">Definition</span></span>

<span data-ttu-id="f4ef9-473">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="f4ef9-473">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="f4ef9-474">La funzione `Func_ireland_eu_tax_file_number` consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="f4ef9-474">The function  `Func_ireland_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="f4ef9-475">Una parola chiave da `Keywords_ireland_eu_tax_file_number` viene trovato.</span><span class="sxs-lookup"><span data-stu-id="f4ef9-475">A keyword from  `Keywords_ireland_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="f4ef9-476">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="f4ef9-476">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="f4ef9-477">La funzione `Func_ireland_eu_tax_file_number` consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="f4ef9-477">The function  `Func_ireland_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="f4ef9-478">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="f4ef9-478">Keywords</span></span>

#### <a name="keywordsirelandeutaxfilenumber"></a><span data-ttu-id="f4ef9-479">Keywords_ireland_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="f4ef9-479">Keywords_ireland_eu_tax_file_number</span></span>

<span data-ttu-id="f4ef9-480">servizio della pubblica alcun</span><span class="sxs-lookup"><span data-stu-id="f4ef9-480">public service no</span></span>
  
<span data-ttu-id="f4ef9-481">servizio della pubblica personale non</span><span class="sxs-lookup"><span data-stu-id="f4ef9-481">personal public service no</span></span>
  
<span data-ttu-id="f4ef9-482">PPS non</span><span class="sxs-lookup"><span data-stu-id="f4ef9-482">pps no</span></span>
  
<span data-ttu-id="f4ef9-483">personale service n</span><span class="sxs-lookup"><span data-stu-id="f4ef9-483">personal service no</span></span>
  
<span data-ttu-id="f4ef9-484">PPS service n</span><span class="sxs-lookup"><span data-stu-id="f4ef9-484">pps service no</span></span>
  
<span data-ttu-id="f4ef9-485">ppsno #</span><span class="sxs-lookup"><span data-stu-id="f4ef9-485">ppsno#</span></span>
  
<span data-ttu-id="f4ef9-486">irlandese pps non</span><span class="sxs-lookup"><span data-stu-id="f4ef9-486">irish pps no</span></span>
  
<span data-ttu-id="f4ef9-487">publicserviceno #</span><span class="sxs-lookup"><span data-stu-id="f4ef9-487">publicserviceno#</span></span>
  
<span data-ttu-id="f4ef9-488">numero di servizio della pubblica personali</span><span class="sxs-lookup"><span data-stu-id="f4ef9-488">personal public service number</span></span>
  
<span data-ttu-id="f4ef9-489">uimhir phearsanta seirbhíse poiblí</span><span class="sxs-lookup"><span data-stu-id="f4ef9-489">uimhir phearsanta seirbhíse poiblí</span></span>
  
<span data-ttu-id="f4ef9-490">uimh PPS</span><span class="sxs-lookup"><span data-stu-id="f4ef9-490">pps uimh</span></span>
  
<span data-ttu-id="f4ef9-491">uimhir aitheantais phearsanta</span><span class="sxs-lookup"><span data-stu-id="f4ef9-491">uimhir aitheantais phearsanta</span></span>
  
## <a name="italy"></a><span data-ttu-id="f4ef9-492">Italia</span><span class="sxs-lookup"><span data-stu-id="f4ef9-492">Italy</span></span>

### <a name="format"></a><span data-ttu-id="f4ef9-493">Formato</span><span class="sxs-lookup"><span data-stu-id="f4ef9-493">Format</span></span>

<span data-ttu-id="f4ef9-494">16 lettere e cifre nel formato specificato</span><span class="sxs-lookup"><span data-stu-id="f4ef9-494">16 letters and digits in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="f4ef9-495">Modello</span><span class="sxs-lookup"><span data-stu-id="f4ef9-495">Pattern</span></span>

<span data-ttu-id="f4ef9-496">16 lettere e cifre:</span><span class="sxs-lookup"><span data-stu-id="f4ef9-496">16 letters and digits:</span></span>
  
-  <span data-ttu-id="f4ef9-497">Tre lettere che corrispondono ai primi tre consonanti nel nome del gruppo</span><span class="sxs-lookup"><span data-stu-id="f4ef9-497">Three letters that correspond to the first three consonants in the family name</span></span> 
    
- <span data-ttu-id="f4ef9-498">Tre lettere che corrispondono al primo, terza e quarta consonanti in nome</span><span class="sxs-lookup"><span data-stu-id="f4ef9-498">Three letters that correspond to the first, third, and fourth consonants in the first name</span></span>
    
- <span data-ttu-id="f4ef9-499">Due cifre che corrispondono all'ultimo cifre dell'anno di nascita</span><span class="sxs-lookup"><span data-stu-id="f4ef9-499">Two digits that correspond to the last digits of the birth year</span></span>
    
- <span data-ttu-id="f4ef9-500">Una cifra che corrisponde al mese di nascita, ovvero lettere vengono utilizzate in ordine alfabetico, ma vengono utilizzate solo lettere da A F, H, L, M, P, R per T (in questo modo, gennaio corrisponde a un e ottobre è R)</span><span class="sxs-lookup"><span data-stu-id="f4ef9-500">One digit that corresponds to the month of birth—letters are used in alphabetical order, but only the letters A to E, H, L, M, P, R to T are used (thus, January is A and October is R)</span></span>
    
- <span data-ttu-id="f4ef9-501">Due cifre che corrispondono al giorno del mese di nascita dove 40 viene aggiunto al giorno di nascita per capi distinguere dai maschi</span><span class="sxs-lookup"><span data-stu-id="f4ef9-501">Two digits that correspond to the day of the month of birth where 40 is added to the day of birth for females to differentiate from males</span></span>
    
- <span data-ttu-id="f4ef9-502">Quattro cifre che corrispondono all'indicativo di località specifico comune dove nascita della persona, a livello nazionale codici vengono utilizzati per i paesi esterni</span><span class="sxs-lookup"><span data-stu-id="f4ef9-502">Four digits that correspond to an area code specific to the municipality where the person was born—country-wide codes are used for foreign countries</span></span>
    
- <span data-ttu-id="f4ef9-503">Cifra di un controllo</span><span class="sxs-lookup"><span data-stu-id="f4ef9-503">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="f4ef9-504">Checksum</span><span class="sxs-lookup"><span data-stu-id="f4ef9-504">Checksum</span></span>

<span data-ttu-id="f4ef9-505">Sì</span><span class="sxs-lookup"><span data-stu-id="f4ef9-505">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="f4ef9-506">Definizione</span><span class="sxs-lookup"><span data-stu-id="f4ef9-506">Definition</span></span>

<span data-ttu-id="f4ef9-507">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="f4ef9-507">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="f4ef9-508">La funzione `Func_italy_eu_tax_file_number` consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="f4ef9-508">The function  `Func_italy_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="f4ef9-509">Una parola chiave da `Keywords_italy_eu_tax_file_number` viene trovato.</span><span class="sxs-lookup"><span data-stu-id="f4ef9-509">A keyword from  `Keywords_italy_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="f4ef9-510">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="f4ef9-510">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="f4ef9-511">La funzione `Func_italy_eu_tax_file_number` consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="f4ef9-511">The function  `Func_italy_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="f4ef9-512">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="f4ef9-512">Keywords</span></span>

#### <a name="keywordsitalyeutaxfilenumber"></a><span data-ttu-id="f4ef9-513">Keywords_italy_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="f4ef9-513">Keywords_italy_eu_tax_file_number</span></span>

<span data-ttu-id="f4ef9-514">Imposta numero</span><span class="sxs-lookup"><span data-stu-id="f4ef9-514">tax number</span></span>
  
<span data-ttu-id="f4ef9-515">imposte no.</span><span class="sxs-lookup"><span data-stu-id="f4ef9-515">tax no.</span></span>
  
<span data-ttu-id="f4ef9-516">taxno #</span><span class="sxs-lookup"><span data-stu-id="f4ef9-516">taxno#</span></span>
  
<span data-ttu-id="f4ef9-517">Numero imposta #</span><span class="sxs-lookup"><span data-stu-id="f4ef9-517">taxnumber#</span></span>
  
<span data-ttu-id="f4ef9-518">Numero imposta</span><span class="sxs-lookup"><span data-stu-id="f4ef9-518">taxnumber</span></span>
  
<span data-ttu-id="f4ef9-519">tax id
</span><span class="sxs-lookup"><span data-stu-id="f4ef9-519">tax id</span></span>
  
<span data-ttu-id="f4ef9-520">taxid #</span><span class="sxs-lookup"><span data-stu-id="f4ef9-520">taxid#</span></span>
  
<span data-ttu-id="f4ef9-521">codice fiscale</span><span class="sxs-lookup"><span data-stu-id="f4ef9-521">fiscal code</span></span>
  
<span data-ttu-id="f4ef9-522">codice fiscale</span><span class="sxs-lookup"><span data-stu-id="f4ef9-522">codice fiscale</span></span>
  
## <a name="latvia"></a><span data-ttu-id="f4ef9-523">Lettonia</span><span class="sxs-lookup"><span data-stu-id="f4ef9-523">Latvia</span></span>

### <a name="format"></a><span data-ttu-id="f4ef9-524">Formato</span><span class="sxs-lookup"><span data-stu-id="f4ef9-524">Format</span></span>

<span data-ttu-id="f4ef9-525">11 cifre senza spazi o delimitatori</span><span class="sxs-lookup"><span data-stu-id="f4ef9-525">11 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="f4ef9-526">Modello</span><span class="sxs-lookup"><span data-stu-id="f4ef9-526">Pattern</span></span>

<span data-ttu-id="f4ef9-527">11 cifre nel formato specificato</span><span class="sxs-lookup"><span data-stu-id="f4ef9-527">11 digits in the specified pattern</span></span>
  
-  <span data-ttu-id="f4ef9-528">Sei cifre che corrispondono alla data di nascita (DDMMYY)</span><span class="sxs-lookup"><span data-stu-id="f4ef9-528">Six digits that correspond to the date of birth (DDMMYY)</span></span> 
    
- <span data-ttu-id="f4ef9-529">Una cifra che corrisponde al century di nascita dove "0" corrisponde al diciannovesimo century "1" corrisponde al ventesimo century e "2" corrisponde al ventunesimo century</span><span class="sxs-lookup"><span data-stu-id="f4ef9-529">One digit that corresponds to the century of birth where "0" corresponds to 19th century, "1" corresponds to 20th century, and "2"corresponds to 21st century</span></span>
    
- <span data-ttu-id="f4ef9-530">Quattro cifre</span><span class="sxs-lookup"><span data-stu-id="f4ef9-530">Four digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="f4ef9-531">Checksum</span><span class="sxs-lookup"><span data-stu-id="f4ef9-531">Checksum</span></span>

<span data-ttu-id="f4ef9-532">Sì</span><span class="sxs-lookup"><span data-stu-id="f4ef9-532">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="f4ef9-533">Definizione</span><span class="sxs-lookup"><span data-stu-id="f4ef9-533">Definition</span></span>

<span data-ttu-id="f4ef9-534">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="f4ef9-534">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="f4ef9-535">La funzione `Func_latvia_eu_tax_file_number` consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="f4ef9-535">The function  `Func_latvia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="f4ef9-536">Una parola chiave da `Keywords_latvia_eu_tax_file_number` viene trovato.</span><span class="sxs-lookup"><span data-stu-id="f4ef9-536">A keyword from  `Keywords_latvia_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="f4ef9-537">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="f4ef9-537">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="f4ef9-538">La funzione `Func_latvia_eu_tax_file_number` consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="f4ef9-538">The function  `Func_latvia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="f4ef9-539">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="f4ef9-539">Keywords</span></span>

#### <a name="keywordslatviaeutaxfilenumber"></a><span data-ttu-id="f4ef9-540">Keywords_latvia_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="f4ef9-540">Keywords_latvia_eu_tax_file_number</span></span>

<span data-ttu-id="f4ef9-541">Imposta numero</span><span class="sxs-lookup"><span data-stu-id="f4ef9-541">tax number</span></span>
  
<span data-ttu-id="f4ef9-542">imposte no.</span><span class="sxs-lookup"><span data-stu-id="f4ef9-542">tax no.</span></span>
  
<span data-ttu-id="f4ef9-543">taxno #</span><span class="sxs-lookup"><span data-stu-id="f4ef9-543">taxno#</span></span>
  
<span data-ttu-id="f4ef9-544">Numero imposta #</span><span class="sxs-lookup"><span data-stu-id="f4ef9-544">taxnumber#</span></span>
  
<span data-ttu-id="f4ef9-545">Numero imposta</span><span class="sxs-lookup"><span data-stu-id="f4ef9-545">taxnumber</span></span>
  
<span data-ttu-id="f4ef9-546">tax id
</span><span class="sxs-lookup"><span data-stu-id="f4ef9-546">tax id</span></span>
  
<span data-ttu-id="f4ef9-547">taxid #</span><span class="sxs-lookup"><span data-stu-id="f4ef9-547">taxid#</span></span>
  
<span data-ttu-id="f4ef9-548">numero di identificazione fiscale</span><span class="sxs-lookup"><span data-stu-id="f4ef9-548">tax identification number</span></span>
  
<span data-ttu-id="f4ef9-549">Identificazione delle imposte non.</span><span class="sxs-lookup"><span data-stu-id="f4ef9-549">tax identification no.</span></span>
  
<span data-ttu-id="f4ef9-550">nodokļa numurs</span><span class="sxs-lookup"><span data-stu-id="f4ef9-550">nodokļa numurs</span></span>
  
<span data-ttu-id="f4ef9-551">nodokļu identifikācijas numurs</span><span class="sxs-lookup"><span data-stu-id="f4ef9-551">nodokļu identifikācijas numurs</span></span>
  
<span data-ttu-id="f4ef9-552">nodokļu identifikācija numurs</span><span class="sxs-lookup"><span data-stu-id="f4ef9-552">nodokļu identifikācija numurs</span></span>
  
## <a name="lithuania"></a><span data-ttu-id="f4ef9-553">Lituania</span><span class="sxs-lookup"><span data-stu-id="f4ef9-553">Lithuania</span></span>

### <a name="format"></a><span data-ttu-id="f4ef9-554">Formato</span><span class="sxs-lookup"><span data-stu-id="f4ef9-554">Format</span></span>

<span data-ttu-id="f4ef9-555">11 cifre senza spazi o delimitatori</span><span class="sxs-lookup"><span data-stu-id="f4ef9-555">11 digits without spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="f4ef9-556">Modello</span><span class="sxs-lookup"><span data-stu-id="f4ef9-556">Pattern</span></span>

<span data-ttu-id="f4ef9-557">11 cifre</span><span class="sxs-lookup"><span data-stu-id="f4ef9-557">11 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="f4ef9-558">Checksum</span><span class="sxs-lookup"><span data-stu-id="f4ef9-558">Checksum</span></span>

<span data-ttu-id="f4ef9-559">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="f4ef9-559">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="f4ef9-560">Definizione</span><span class="sxs-lookup"><span data-stu-id="f4ef9-560">Definition</span></span>

<span data-ttu-id="f4ef9-561">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="f4ef9-561">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="f4ef9-562">La funzione `Func_lithuania_eu_tax_file_number` consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="f4ef9-562">The function  `Func_lithuania_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="f4ef9-563">Una parola chiave da `Keywords_lithuania_eu_tax_file_number` viene trovato.</span><span class="sxs-lookup"><span data-stu-id="f4ef9-563">A keyword from  `Keywords_lithuania_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="f4ef9-564">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="f4ef9-564">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="f4ef9-565">La funzione `Func_lithuania_eu_tax_file_number` consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="f4ef9-565">The function  `Func_lithuania_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="f4ef9-566">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="f4ef9-566">Keywords</span></span>

#### <a name="keywordslithuaniaeutaxfilenumber"></a><span data-ttu-id="f4ef9-567">Keywords_lithuania_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="f4ef9-567">Keywords_lithuania_eu_tax_file_number</span></span>

<span data-ttu-id="f4ef9-568">Imposta numero</span><span class="sxs-lookup"><span data-stu-id="f4ef9-568">tax number</span></span>
  
<span data-ttu-id="f4ef9-569">imposte no.</span><span class="sxs-lookup"><span data-stu-id="f4ef9-569">tax no.</span></span>
  
<span data-ttu-id="f4ef9-570">Imposta no #</span><span class="sxs-lookup"><span data-stu-id="f4ef9-570">tax no#</span></span>
  
<span data-ttu-id="f4ef9-571">Numero imposta #</span><span class="sxs-lookup"><span data-stu-id="f4ef9-571">taxnumber#</span></span>
  
<span data-ttu-id="f4ef9-572">Numero imposta</span><span class="sxs-lookup"><span data-stu-id="f4ef9-572">taxnumber</span></span>
  
<span data-ttu-id="f4ef9-573">tax id
</span><span class="sxs-lookup"><span data-stu-id="f4ef9-573">tax id</span></span>
  
<span data-ttu-id="f4ef9-574">taxid #</span><span class="sxs-lookup"><span data-stu-id="f4ef9-574">taxid#</span></span>
  
<span data-ttu-id="f4ef9-575">numero di identificazione fiscale</span><span class="sxs-lookup"><span data-stu-id="f4ef9-575">tax identification number</span></span>
  
<span data-ttu-id="f4ef9-576">Identificazione delle imposte non.</span><span class="sxs-lookup"><span data-stu-id="f4ef9-576">tax identification no.</span></span>
  
<span data-ttu-id="f4ef9-577">id mokesčių</span><span class="sxs-lookup"><span data-stu-id="f4ef9-577">mokesčių id</span></span>
  
<span data-ttu-id="f4ef9-578">mokesčių numeris</span><span class="sxs-lookup"><span data-stu-id="f4ef9-578">mokesčių numeris</span></span>
  
<span data-ttu-id="f4ef9-579">mokesčių identifikavimas numeris</span><span class="sxs-lookup"><span data-stu-id="f4ef9-579">mokesčių identifikavimas numeris</span></span>
  
## <a name="luxemburg"></a><span data-ttu-id="f4ef9-580">Lussemburgo</span><span class="sxs-lookup"><span data-stu-id="f4ef9-580">Luxemburg</span></span>

### <a name="format"></a><span data-ttu-id="f4ef9-581">Formato</span><span class="sxs-lookup"><span data-stu-id="f4ef9-581">Format</span></span>

<span data-ttu-id="f4ef9-582">13 cifre senza spazi o delimitatori</span><span class="sxs-lookup"><span data-stu-id="f4ef9-582">13 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="f4ef9-583">Modello</span><span class="sxs-lookup"><span data-stu-id="f4ef9-583">Pattern</span></span>

<span data-ttu-id="f4ef9-584">13 cifre:</span><span class="sxs-lookup"><span data-stu-id="f4ef9-584">13 digits:</span></span>
  
-  <span data-ttu-id="f4ef9-585">11 cifre</span><span class="sxs-lookup"><span data-stu-id="f4ef9-585">11 digits</span></span> 
    
- <span data-ttu-id="f4ef9-586">Due cifre di controllo</span><span class="sxs-lookup"><span data-stu-id="f4ef9-586">Two check digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="f4ef9-587">Checksum</span><span class="sxs-lookup"><span data-stu-id="f4ef9-587">Checksum</span></span>

<span data-ttu-id="f4ef9-588">Sì</span><span class="sxs-lookup"><span data-stu-id="f4ef9-588">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="f4ef9-589">Definizione</span><span class="sxs-lookup"><span data-stu-id="f4ef9-589">Definition</span></span>

<span data-ttu-id="f4ef9-590">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="f4ef9-590">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="f4ef9-591">La funzione `Func_luxemburg_eu_tax_file_number` consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="f4ef9-591">The function  `Func_luxemburg_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="f4ef9-592">Una parola chiave da `Keywords_luxemburg_eu_tax_file_number` viene trovato.</span><span class="sxs-lookup"><span data-stu-id="f4ef9-592">A keyword from  `Keywords_luxemburg_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="f4ef9-593">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="f4ef9-593">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="f4ef9-594">La funzione `Func_luxemburg_eu_tax_file_number` consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="f4ef9-594">The function  `Func_luxemburg_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="f4ef9-595">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="f4ef9-595">Keywords</span></span>

#### <a name="keywordsluxemburgeutaxfilenumber"></a><span data-ttu-id="f4ef9-596">Keywords_luxemburg_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="f4ef9-596">Keywords_luxemburg_eu_tax_file_number</span></span>

<span data-ttu-id="f4ef9-597">Imposta numero</span><span class="sxs-lookup"><span data-stu-id="f4ef9-597">tax number</span></span>
  
<span data-ttu-id="f4ef9-598">imposte no.</span><span class="sxs-lookup"><span data-stu-id="f4ef9-598">tax no.</span></span>
  
<span data-ttu-id="f4ef9-599">taxno #</span><span class="sxs-lookup"><span data-stu-id="f4ef9-599">taxno#</span></span>
  
<span data-ttu-id="f4ef9-600">Numero imposta #</span><span class="sxs-lookup"><span data-stu-id="f4ef9-600">taxnumber#</span></span>
  
<span data-ttu-id="f4ef9-601">Numero imposta</span><span class="sxs-lookup"><span data-stu-id="f4ef9-601">taxnumber</span></span>
  
<span data-ttu-id="f4ef9-602">tax id
</span><span class="sxs-lookup"><span data-stu-id="f4ef9-602">tax id</span></span>
  
<span data-ttu-id="f4ef9-603">taxid #</span><span class="sxs-lookup"><span data-stu-id="f4ef9-603">taxid#</span></span>
  
<span data-ttu-id="f4ef9-604">numero di identificazione fiscale</span><span class="sxs-lookup"><span data-stu-id="f4ef9-604">tax identification number</span></span>
  
<span data-ttu-id="f4ef9-605">Identificazione delle imposte non.</span><span class="sxs-lookup"><span data-stu-id="f4ef9-605">tax identification no.</span></span>
  
<span data-ttu-id="f4ef9-606">steuernummer</span><span class="sxs-lookup"><span data-stu-id="f4ef9-606">steuernummer</span></span>
  
<span data-ttu-id="f4ef9-607">id steuer</span><span class="sxs-lookup"><span data-stu-id="f4ef9-607">steuer id</span></span>
  
<span data-ttu-id="f4ef9-608">steueridentifikationsnummer</span><span class="sxs-lookup"><span data-stu-id="f4ef9-608">steueridentifikationsnummer</span></span>
  
## <a name="malta"></a><span data-ttu-id="f4ef9-609">Malta</span><span class="sxs-lookup"><span data-stu-id="f4ef9-609">Malta</span></span>

### <a name="format"></a><span data-ttu-id="f4ef9-610">Formato</span><span class="sxs-lookup"><span data-stu-id="f4ef9-610">Format</span></span>

<span data-ttu-id="f4ef9-611">Per i cittadini Maltese: 7 cifre e una lettera nella serie specificata</span><span class="sxs-lookup"><span data-stu-id="f4ef9-611">For Maltese nationals: 7 digits and one letter in the specified pattern</span></span>
  
<span data-ttu-id="f4ef9-612">Maltese non cittadini ed entità Maltese: 9 cifre</span><span class="sxs-lookup"><span data-stu-id="f4ef9-612">Non-Maltese nationals and Maltese entities: 9 digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="f4ef9-613">Modello</span><span class="sxs-lookup"><span data-stu-id="f4ef9-613">Pattern</span></span>

<span data-ttu-id="f4ef9-614">Sterlina maltese cittadini: 7 cifre e una lettera</span><span class="sxs-lookup"><span data-stu-id="f4ef9-614">Maltese nationals: 7 digits and one letter</span></span>
  
-  <span data-ttu-id="f4ef9-615">Sette cifre</span><span class="sxs-lookup"><span data-stu-id="f4ef9-615">Seven digits</span></span> 
    
- <span data-ttu-id="f4ef9-616">Una lettera (maiuscole o minuscole)</span><span class="sxs-lookup"><span data-stu-id="f4ef9-616">One letter (not case-sensitive)</span></span>
    
<span data-ttu-id="f4ef9-617">Maltese non cittadini ed entità Maltese: 9 cifre</span><span class="sxs-lookup"><span data-stu-id="f4ef9-617">Non-Maltese nationals and Maltese entities: 9 digits</span></span>
  
-  <span data-ttu-id="f4ef9-618">9 cifre</span><span class="sxs-lookup"><span data-stu-id="f4ef9-618">Nine digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="f4ef9-619">Checksum</span><span class="sxs-lookup"><span data-stu-id="f4ef9-619">Checksum</span></span>

<span data-ttu-id="f4ef9-620">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="f4ef9-620">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="f4ef9-621">Definizione</span><span class="sxs-lookup"><span data-stu-id="f4ef9-621">Definition</span></span>

<span data-ttu-id="f4ef9-622">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="f4ef9-622">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="f4ef9-623">La funzione `Func_malta_eu_tax_file_number` consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="f4ef9-623">The function  `Func_malta_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="f4ef9-624">Una parola chiave da `Keywords_malta_eu_tax_file_number` viene trovato.</span><span class="sxs-lookup"><span data-stu-id="f4ef9-624">A keyword from  `Keywords_malta_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="f4ef9-625">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 65%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="f4ef9-625">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="f4ef9-626">La funzione `Func_malta_eu_tax_file_number` consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="f4ef9-626">The function  `Func_malta_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="f4ef9-627">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="f4ef9-627">Keywords</span></span>

#### <a name="keywordsmaltaeutaxfilenumber"></a><span data-ttu-id="f4ef9-628">Keywords_malta_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="f4ef9-628">Keywords_malta_eu_tax_file_number</span></span>

<span data-ttu-id="f4ef9-629">Imposta numero</span><span class="sxs-lookup"><span data-stu-id="f4ef9-629">tax number</span></span>
  
<span data-ttu-id="f4ef9-630">imposte no.</span><span class="sxs-lookup"><span data-stu-id="f4ef9-630">tax no.</span></span>
  
<span data-ttu-id="f4ef9-631">taxno #</span><span class="sxs-lookup"><span data-stu-id="f4ef9-631">taxno#</span></span>
  
<span data-ttu-id="f4ef9-632">Numero imposta #</span><span class="sxs-lookup"><span data-stu-id="f4ef9-632">taxnumber#</span></span>
  
<span data-ttu-id="f4ef9-633">Numero imposta</span><span class="sxs-lookup"><span data-stu-id="f4ef9-633">taxnumber</span></span>
  
<span data-ttu-id="f4ef9-634">tax id
</span><span class="sxs-lookup"><span data-stu-id="f4ef9-634">tax id</span></span>
  
<span data-ttu-id="f4ef9-635">taxid #</span><span class="sxs-lookup"><span data-stu-id="f4ef9-635">taxid#</span></span>
  
<span data-ttu-id="f4ef9-636">numero di identificazione fiscale</span><span class="sxs-lookup"><span data-stu-id="f4ef9-636">tax identification number</span></span>
  
<span data-ttu-id="f4ef9-637">Identificazione delle imposte non.</span><span class="sxs-lookup"><span data-stu-id="f4ef9-637">tax identification no.</span></span>
  
<span data-ttu-id="f4ef9-638">numru tat-taxxa</span><span class="sxs-lookup"><span data-stu-id="f4ef9-638">numru tat-taxxa</span></span>
  
<span data-ttu-id="f4ef9-639">ID tat-taxxa</span><span class="sxs-lookup"><span data-stu-id="f4ef9-639">id tat-taxxa</span></span>
  
<span data-ttu-id="f4ef9-640">numru ta ' identifikazzjoni tat-taxxa</span><span class="sxs-lookup"><span data-stu-id="f4ef9-640">numru ta 'identifikazzjoni tat-taxxa</span></span>
  
## <a name="netherlands"></a><span data-ttu-id="f4ef9-641">Paesi Bassi</span><span class="sxs-lookup"><span data-stu-id="f4ef9-641">Netherlands</span></span>

### <a name="format"></a><span data-ttu-id="f4ef9-642">Formato</span><span class="sxs-lookup"><span data-stu-id="f4ef9-642">Format</span></span>

<span data-ttu-id="f4ef9-643">Nove cifre senza spazi o delimitatori</span><span class="sxs-lookup"><span data-stu-id="f4ef9-643">Nine digits without spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="f4ef9-644">Modello</span><span class="sxs-lookup"><span data-stu-id="f4ef9-644">Pattern</span></span>

<span data-ttu-id="f4ef9-645">9 cifre</span><span class="sxs-lookup"><span data-stu-id="f4ef9-645">Nine digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="f4ef9-646">Checksum</span><span class="sxs-lookup"><span data-stu-id="f4ef9-646">Checksum</span></span>

<span data-ttu-id="f4ef9-647">Sì</span><span class="sxs-lookup"><span data-stu-id="f4ef9-647">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="f4ef9-648">Definizione</span><span class="sxs-lookup"><span data-stu-id="f4ef9-648">Definition</span></span>

<span data-ttu-id="f4ef9-649">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="f4ef9-649">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="f4ef9-650">La funzione `Func_netherlands_eu_tax_file_number` consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="f4ef9-650">The function  `Func_netherlands_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="f4ef9-651">Una parola chiave da `Keywords_netherlands_eu_tax_file_number` viene trovato.</span><span class="sxs-lookup"><span data-stu-id="f4ef9-651">A keyword from  `Keywords_netherlands_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="f4ef9-652">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="f4ef9-652">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="f4ef9-653">La funzione `Func_netherlands_eu_tax_file_number` consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="f4ef9-653">The function  `Func_netherlands_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="f4ef9-654">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="f4ef9-654">Keywords</span></span>

#### <a name="keywordsnetherlandseutaxfilenumber"></a><span data-ttu-id="f4ef9-655">Keywords_netherlands_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="f4ef9-655">Keywords_netherlands_eu_tax_file_number</span></span>

<span data-ttu-id="f4ef9-656">numero di identificazione fiscale Paesi Bassi</span><span class="sxs-lookup"><span data-stu-id="f4ef9-656">netherlands tax identification number</span></span>
  
<span data-ttu-id="f4ef9-657">identificazione imposte Paesi Bassi</span><span class="sxs-lookup"><span data-stu-id="f4ef9-657">netherlands tax identification</span></span>
  
<span data-ttu-id="f4ef9-658">numero di identificazione fiscale Olanda</span><span class="sxs-lookup"><span data-stu-id="f4ef9-658">netherland's tax identification number</span></span>
  
<span data-ttu-id="f4ef9-659">identificazione imposte Olanda</span><span class="sxs-lookup"><span data-stu-id="f4ef9-659">netherland's tax identification</span></span>
  
<span data-ttu-id="f4ef9-660">numero di identificazione fiscale</span><span class="sxs-lookup"><span data-stu-id="f4ef9-660">tax identification number</span></span>
  
<span data-ttu-id="f4ef9-661">id imposta olandese</span><span class="sxs-lookup"><span data-stu-id="f4ef9-661">dutch tax id</span></span>
  
<span data-ttu-id="f4ef9-662">numero di identificazione olandese</span><span class="sxs-lookup"><span data-stu-id="f4ef9-662">dutch tax identification number</span></span>
  
<span data-ttu-id="f4ef9-663">tax id
</span><span class="sxs-lookup"><span data-stu-id="f4ef9-663">tax id</span></span>
  
<span data-ttu-id="f4ef9-664">Imposta id #</span><span class="sxs-lookup"><span data-stu-id="f4ef9-664">tax id#</span></span>
  
<span data-ttu-id="f4ef9-665">Imposta numero</span><span class="sxs-lookup"><span data-stu-id="f4ef9-665">tax number</span></span>
  
<span data-ttu-id="f4ef9-666">Imposta no #</span><span class="sxs-lookup"><span data-stu-id="f4ef9-666">tax no#</span></span>
  
<span data-ttu-id="f4ef9-667">Imposta #</span><span class="sxs-lookup"><span data-stu-id="f4ef9-667">tax#</span></span>
  
<span data-ttu-id="f4ef9-668">tin
</span><span class="sxs-lookup"><span data-stu-id="f4ef9-668">tin</span></span>
  
<span data-ttu-id="f4ef9-669">ID #</span><span class="sxs-lookup"><span data-stu-id="f4ef9-669">tin#</span></span>
  
<span data-ttu-id="f4ef9-670">ID Paesi Bassi</span><span class="sxs-lookup"><span data-stu-id="f4ef9-670">netherlands tin</span></span>
  
<span data-ttu-id="f4ef9-671">ID Olanda</span><span class="sxs-lookup"><span data-stu-id="f4ef9-671">netherland's tin</span></span>
  
<span data-ttu-id="f4ef9-672">Paesi Bassi belasting identificatienummer</span><span class="sxs-lookup"><span data-stu-id="f4ef9-672">nederlands belasting identificatienummer</span></span>
  
<span data-ttu-id="f4ef9-673">identificatienummer van belasting</span><span class="sxs-lookup"><span data-stu-id="f4ef9-673">identificatienummer van belasting</span></span>
  
<span data-ttu-id="f4ef9-674">belasting identificatienummer</span><span class="sxs-lookup"><span data-stu-id="f4ef9-674">identificatienummer belasting</span></span>
  
<span data-ttu-id="f4ef9-675">Paesi Bassi belasting identificatie</span><span class="sxs-lookup"><span data-stu-id="f4ef9-675">nederlands belasting identificatie</span></span>
  
<span data-ttu-id="f4ef9-676">Paesi Bassi belasting id nummer</span><span class="sxs-lookup"><span data-stu-id="f4ef9-676">nederlands belasting id nummer</span></span>
  
<span data-ttu-id="f4ef9-677">Paesi Bassi belastingnummer</span><span class="sxs-lookup"><span data-stu-id="f4ef9-677">nederlands belastingnummer</span></span>
  
<span data-ttu-id="f4ef9-678">BTW nummer</span><span class="sxs-lookup"><span data-stu-id="f4ef9-678">btw nummer</span></span>
  
<span data-ttu-id="f4ef9-679">Nederlandse belasting identificatie</span><span class="sxs-lookup"><span data-stu-id="f4ef9-679">nederlandse belasting identificatie</span></span>
  
## <a name="poland"></a><span data-ttu-id="f4ef9-680">Polonia</span><span class="sxs-lookup"><span data-stu-id="f4ef9-680">Poland</span></span>

### <a name="format"></a><span data-ttu-id="f4ef9-681">Formato</span><span class="sxs-lookup"><span data-stu-id="f4ef9-681">Format</span></span>

<span data-ttu-id="f4ef9-682">Undici cifre senza spazi o delimitatori</span><span class="sxs-lookup"><span data-stu-id="f4ef9-682">Eleven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="f4ef9-683">Modello</span><span class="sxs-lookup"><span data-stu-id="f4ef9-683">Pattern</span></span>

<span data-ttu-id="f4ef9-684">Undici cifre</span><span class="sxs-lookup"><span data-stu-id="f4ef9-684">Eleven digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="f4ef9-685">Checksum</span><span class="sxs-lookup"><span data-stu-id="f4ef9-685">Checksum</span></span>

<span data-ttu-id="f4ef9-686">Sì</span><span class="sxs-lookup"><span data-stu-id="f4ef9-686">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="f4ef9-687">Definizione</span><span class="sxs-lookup"><span data-stu-id="f4ef9-687">Definition</span></span>

<span data-ttu-id="f4ef9-688">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="f4ef9-688">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="f4ef9-689">La funzione `Func_poland_eu_tax_file_number` consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="f4ef9-689">The function  `Func_poland_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="f4ef9-690">Una parola chiave da `Keywords_poland_eu_tax_file_number` viene trovato.</span><span class="sxs-lookup"><span data-stu-id="f4ef9-690">A keyword from  `Keywords_poland_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="f4ef9-691">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="f4ef9-691">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="f4ef9-692">La funzione `Func_poland_eu_tax_file_number` consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="f4ef9-692">The function  `Func_poland_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="f4ef9-693">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="f4ef9-693">Keywords</span></span>

#### <a name="keywordspolandeutaxfilenumber"></a><span data-ttu-id="f4ef9-694">Keywords_poland_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="f4ef9-694">Keywords_poland_eu_tax_file_number</span></span>

<span data-ttu-id="f4ef9-695">Imposta numero</span><span class="sxs-lookup"><span data-stu-id="f4ef9-695">tax number</span></span>
  
<span data-ttu-id="f4ef9-696">imposte no.</span><span class="sxs-lookup"><span data-stu-id="f4ef9-696">tax no.</span></span>
  
<span data-ttu-id="f4ef9-697">taxno #</span><span class="sxs-lookup"><span data-stu-id="f4ef9-697">taxno#</span></span>
  
<span data-ttu-id="f4ef9-698">Numero imposta #</span><span class="sxs-lookup"><span data-stu-id="f4ef9-698">taxnumber#</span></span>
  
<span data-ttu-id="f4ef9-699">Numero imposta</span><span class="sxs-lookup"><span data-stu-id="f4ef9-699">taxnumber</span></span>
  
<span data-ttu-id="f4ef9-700">nip</span><span class="sxs-lookup"><span data-stu-id="f4ef9-700">nip</span></span>
  
<span data-ttu-id="f4ef9-701">da nip #</span><span class="sxs-lookup"><span data-stu-id="f4ef9-701">nip#</span></span>
  
<span data-ttu-id="f4ef9-702">tax id
</span><span class="sxs-lookup"><span data-stu-id="f4ef9-702">tax id</span></span>
  
<span data-ttu-id="f4ef9-703">Imposta id #</span><span class="sxs-lookup"><span data-stu-id="f4ef9-703">tax id#</span></span>
  
<span data-ttu-id="f4ef9-704">id da nip</span><span class="sxs-lookup"><span data-stu-id="f4ef9-704">nip id</span></span>
  
<span data-ttu-id="f4ef9-705">da nip id #</span><span class="sxs-lookup"><span data-stu-id="f4ef9-705">nip id#</span></span>
  
<span data-ttu-id="f4ef9-706">numero di identificazione fiscale</span><span class="sxs-lookup"><span data-stu-id="f4ef9-706">tax identification number</span></span>
  
<span data-ttu-id="f4ef9-707">Identificazione delle imposte non.</span><span class="sxs-lookup"><span data-stu-id="f4ef9-707">tax identification no.</span></span>
  
<span data-ttu-id="f4ef9-708">numero IVA</span><span class="sxs-lookup"><span data-stu-id="f4ef9-708">vat number</span></span>
  
<span data-ttu-id="f4ef9-709">IVA no.</span><span class="sxs-lookup"><span data-stu-id="f4ef9-709">vat no.</span></span>
  
<span data-ttu-id="f4ef9-710">vatno #</span><span class="sxs-lookup"><span data-stu-id="f4ef9-710">vatno#</span></span>
  
<span data-ttu-id="f4ef9-711">id IVA</span><span class="sxs-lookup"><span data-stu-id="f4ef9-711">vat id</span></span>
  
<span data-ttu-id="f4ef9-712">id IVA #</span><span class="sxs-lookup"><span data-stu-id="f4ef9-712">vat id#</span></span>
  
<span data-ttu-id="f4ef9-713">numero identyfikacji podatkowej</span><span class="sxs-lookup"><span data-stu-id="f4ef9-713">numer identyfikacji podatkowej</span></span>
  
<span data-ttu-id="f4ef9-714">polski numero identyfikacji podatkowej</span><span class="sxs-lookup"><span data-stu-id="f4ef9-714">polski numer identyfikacji podatkowej</span></span>
  
<span data-ttu-id="f4ef9-715">numeridentyfikacjipodatkowej #</span><span class="sxs-lookup"><span data-stu-id="f4ef9-715">numeridentyfikacjipodatkowej#</span></span>
  
## <a name="portugal"></a><span data-ttu-id="f4ef9-716">Portogallo</span><span class="sxs-lookup"><span data-stu-id="f4ef9-716">Portugal</span></span>

### <a name="format"></a><span data-ttu-id="f4ef9-717">Formato</span><span class="sxs-lookup"><span data-stu-id="f4ef9-717">Format</span></span>

<span data-ttu-id="f4ef9-718">Nove cifre senza spazi o delimitatori</span><span class="sxs-lookup"><span data-stu-id="f4ef9-718">Nine digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="f4ef9-719">Modello</span><span class="sxs-lookup"><span data-stu-id="f4ef9-719">Pattern</span></span>

<span data-ttu-id="f4ef9-720">9 cifre</span><span class="sxs-lookup"><span data-stu-id="f4ef9-720">Nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="f4ef9-721">Checksum</span><span class="sxs-lookup"><span data-stu-id="f4ef9-721">Checksum</span></span>

<span data-ttu-id="f4ef9-722">Sì</span><span class="sxs-lookup"><span data-stu-id="f4ef9-722">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="f4ef9-723">Definizione</span><span class="sxs-lookup"><span data-stu-id="f4ef9-723">Definition</span></span>

<span data-ttu-id="f4ef9-724">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="f4ef9-724">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="f4ef9-725">La funzione `Func_portugal_eu_tax_file_number` consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="f4ef9-725">The function  `Func_portugal_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="f4ef9-726">Una parola chiave da `Keywords_portugal_eu_tax_file_number` viene trovato.</span><span class="sxs-lookup"><span data-stu-id="f4ef9-726">A keyword from  `Keywords_portugal_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="f4ef9-727">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="f4ef9-727">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="f4ef9-728">La funzione `Func_portugal_eu_tax_file_number` consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="f4ef9-728">The function  `Func_portugal_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="f4ef9-729">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="f4ef9-729">Keywords</span></span>

#### <a name="keywordsportugaleutaxfilenumber"></a><span data-ttu-id="f4ef9-730">Keywords_portugal_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="f4ef9-730">Keywords_portugal_eu_tax_file_number</span></span>

<span data-ttu-id="f4ef9-731">Imposta numero</span><span class="sxs-lookup"><span data-stu-id="f4ef9-731">tax number</span></span>
  
<span data-ttu-id="f4ef9-732">imposte no.</span><span class="sxs-lookup"><span data-stu-id="f4ef9-732">tax no.</span></span>
  
<span data-ttu-id="f4ef9-733">taxno #</span><span class="sxs-lookup"><span data-stu-id="f4ef9-733">taxno#</span></span>
  
<span data-ttu-id="f4ef9-734">Numero imposta #</span><span class="sxs-lookup"><span data-stu-id="f4ef9-734">taxnumber#</span></span>
  
<span data-ttu-id="f4ef9-735">Numero imposta</span><span class="sxs-lookup"><span data-stu-id="f4ef9-735">taxnumber</span></span>
  
<span data-ttu-id="f4ef9-736">NIF</span><span class="sxs-lookup"><span data-stu-id="f4ef9-736">nif</span></span>
  
<span data-ttu-id="f4ef9-737">NIF #</span><span class="sxs-lookup"><span data-stu-id="f4ef9-737">nif#</span></span>
  
<span data-ttu-id="f4ef9-738">numero fiscale</span><span class="sxs-lookup"><span data-stu-id="f4ef9-738">numero fiscal</span></span>
  
<span data-ttu-id="f4ef9-739">número de identificação fiscale</span><span class="sxs-lookup"><span data-stu-id="f4ef9-739">número de identificação fiscal</span></span>
  
## <a name="romania"></a><span data-ttu-id="f4ef9-740">Romania</span><span class="sxs-lookup"><span data-stu-id="f4ef9-740">Romania</span></span>

### <a name="format"></a><span data-ttu-id="f4ef9-741">Formato</span><span class="sxs-lookup"><span data-stu-id="f4ef9-741">Format</span></span>

<span data-ttu-id="f4ef9-742">13 cifre senza spazi o delimitatori</span><span class="sxs-lookup"><span data-stu-id="f4ef9-742">13 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="f4ef9-743">Modello</span><span class="sxs-lookup"><span data-stu-id="f4ef9-743">Pattern</span></span>

<span data-ttu-id="f4ef9-744">13 cifre</span><span class="sxs-lookup"><span data-stu-id="f4ef9-744">13 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="f4ef9-745">Checksum</span><span class="sxs-lookup"><span data-stu-id="f4ef9-745">Checksum</span></span>

<span data-ttu-id="f4ef9-746">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="f4ef9-746">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="f4ef9-747">Definizione</span><span class="sxs-lookup"><span data-stu-id="f4ef9-747">Definition</span></span>

<span data-ttu-id="f4ef9-748">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="f4ef9-748">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="f4ef9-749">L'espressione regolare `Regex_romania_eu_tax_file_number` consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="f4ef9-749">The regular expression  `Regex_romania_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="f4ef9-750">Una parola chiave da `Keywords_romania_eu_tax_file_number` viene trovato.</span><span class="sxs-lookup"><span data-stu-id="f4ef9-750">A keyword from  `Keywords_romania_eu_tax_file_number` is found.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_romania_eu_tax_file_number" />
          <Match idRef="Keywords_romania_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="f4ef9-751">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="f4ef9-751">Keywords</span></span>

#### <a name="keywordsromaniaeutaxfilenumber"></a><span data-ttu-id="f4ef9-752">Keywords_romania_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="f4ef9-752">Keywords_romania_eu_tax_file_number</span></span>

<span data-ttu-id="f4ef9-753">tax id
</span><span class="sxs-lookup"><span data-stu-id="f4ef9-753">tax id</span></span>
  
<span data-ttu-id="f4ef9-754">codice fiscale</span><span class="sxs-lookup"><span data-stu-id="f4ef9-754">tax id number</span></span>
  
<span data-ttu-id="f4ef9-755">Imposta i file non</span><span class="sxs-lookup"><span data-stu-id="f4ef9-755">tax file no</span></span>
  
<span data-ttu-id="f4ef9-756">

tax file number</span><span class="sxs-lookup"><span data-stu-id="f4ef9-756">tax file number</span></span>
  
<span data-ttu-id="f4ef9-757">Imposta n</span><span class="sxs-lookup"><span data-stu-id="f4ef9-757">tax no</span></span>
  
<span data-ttu-id="f4ef9-758">Imposta numero</span><span class="sxs-lookup"><span data-stu-id="f4ef9-758">tax number</span></span>
  
<span data-ttu-id="f4ef9-759">taxid #</span><span class="sxs-lookup"><span data-stu-id="f4ef9-759">taxid#</span></span>
  
<span data-ttu-id="f4ef9-760">taxno #</span><span class="sxs-lookup"><span data-stu-id="f4ef9-760">taxno#</span></span>
  
<span data-ttu-id="f4ef9-761">ID ul taxei</span><span class="sxs-lookup"><span data-stu-id="f4ef9-761">id-ul taxei</span></span>
  
<span data-ttu-id="f4ef9-762">numărul de identificare fiscală</span><span class="sxs-lookup"><span data-stu-id="f4ef9-762">numărul de identificare fiscală</span></span>
  
## <a name="slovakia"></a><span data-ttu-id="f4ef9-763">Slovacchia</span><span class="sxs-lookup"><span data-stu-id="f4ef9-763">Slovakia</span></span>

### <a name="format"></a><span data-ttu-id="f4ef9-764">Formato</span><span class="sxs-lookup"><span data-stu-id="f4ef9-764">Format</span></span>

<span data-ttu-id="f4ef9-765">10 cifre senza spazi o delimitatori</span><span class="sxs-lookup"><span data-stu-id="f4ef9-765">10 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="f4ef9-766">Modello</span><span class="sxs-lookup"><span data-stu-id="f4ef9-766">Pattern</span></span>

<span data-ttu-id="f4ef9-767">10 cifre</span><span class="sxs-lookup"><span data-stu-id="f4ef9-767">10 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="f4ef9-768">Checksum</span><span class="sxs-lookup"><span data-stu-id="f4ef9-768">Checksum</span></span>

<span data-ttu-id="f4ef9-769">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="f4ef9-769">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="f4ef9-770">Definizione</span><span class="sxs-lookup"><span data-stu-id="f4ef9-770">Definition</span></span>

<span data-ttu-id="f4ef9-771">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="f4ef9-771">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="f4ef9-772">L'espressione regolare `Regex_slovakia_eu_tax_file_number` consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="f4ef9-772">The regular expression  `Regex_slovakia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="f4ef9-773">Una parola chiave da `Keywords_slovakia_eu_tax_file_number` viene trovato.</span><span class="sxs-lookup"><span data-stu-id="f4ef9-773">A keyword from  `Keywords_slovakia_eu_tax_file_number` is found.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovakia_eu_tax_file_number" />
          <Match idRef="Keywords_slovakia_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="f4ef9-774">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="f4ef9-774">Keywords</span></span>

#### <a name="keywordsslovakiaeutaxfilenumber"></a><span data-ttu-id="f4ef9-775">Keywords_slovakia_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="f4ef9-775">Keywords_slovakia_eu_tax_file_number</span></span>

<span data-ttu-id="f4ef9-776">tax id
</span><span class="sxs-lookup"><span data-stu-id="f4ef9-776">tax id</span></span>
  
<span data-ttu-id="f4ef9-777">codice fiscale</span><span class="sxs-lookup"><span data-stu-id="f4ef9-777">tax id number</span></span>
  
<span data-ttu-id="f4ef9-778">id stagno</span><span class="sxs-lookup"><span data-stu-id="f4ef9-778">tin id</span></span>
  
<span data-ttu-id="f4ef9-779">no stagno</span><span class="sxs-lookup"><span data-stu-id="f4ef9-779">tin no</span></span>
  
<span data-ttu-id="f4ef9-780">id stagno slovacco</span><span class="sxs-lookup"><span data-stu-id="f4ef9-780">slovakian tin id</span></span>
  
<span data-ttu-id="f4ef9-781">tin
</span><span class="sxs-lookup"><span data-stu-id="f4ef9-781">tin</span></span>
  
<span data-ttu-id="f4ef9-782">Imposta i file non</span><span class="sxs-lookup"><span data-stu-id="f4ef9-782">tax file no</span></span>
  
<span data-ttu-id="f4ef9-783">

tax file number</span><span class="sxs-lookup"><span data-stu-id="f4ef9-783">tax file number</span></span>
  
<span data-ttu-id="f4ef9-784">Imposta n</span><span class="sxs-lookup"><span data-stu-id="f4ef9-784">tax no</span></span>
  
<span data-ttu-id="f4ef9-785">Imposta numero</span><span class="sxs-lookup"><span data-stu-id="f4ef9-785">tax number</span></span>
  
<span data-ttu-id="f4ef9-786">taxid #</span><span class="sxs-lookup"><span data-stu-id="f4ef9-786">taxid#</span></span>
  
<span data-ttu-id="f4ef9-787">taxno #</span><span class="sxs-lookup"><span data-stu-id="f4ef9-787">taxno#</span></span>
  
<span data-ttu-id="f4ef9-788">daňové identifikačné číslo</span><span class="sxs-lookup"><span data-stu-id="f4ef9-788">daňové identifikačné číslo</span></span>
  
<span data-ttu-id="f4ef9-789">daňové číslo</span><span class="sxs-lookup"><span data-stu-id="f4ef9-789">daňové číslo</span></span>
  
<span data-ttu-id="f4ef9-790">daňové číslo súboru</span><span class="sxs-lookup"><span data-stu-id="f4ef9-790">daňové číslo súboru</span></span>
  
## <a name="slovenia"></a><span data-ttu-id="f4ef9-791">Slovenia</span><span class="sxs-lookup"><span data-stu-id="f4ef9-791">Slovenia</span></span>

### <a name="format"></a><span data-ttu-id="f4ef9-792">Formato</span><span class="sxs-lookup"><span data-stu-id="f4ef9-792">Format</span></span>

<span data-ttu-id="f4ef9-793">Otto cifre senza spazi o delimitatori</span><span class="sxs-lookup"><span data-stu-id="f4ef9-793">Eight digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="f4ef9-794">Modello</span><span class="sxs-lookup"><span data-stu-id="f4ef9-794">Pattern</span></span>

<span data-ttu-id="f4ef9-795">Otto cifre</span><span class="sxs-lookup"><span data-stu-id="f4ef9-795">Eight digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="f4ef9-796">Checksum</span><span class="sxs-lookup"><span data-stu-id="f4ef9-796">Checksum</span></span>

<span data-ttu-id="f4ef9-797">Sì</span><span class="sxs-lookup"><span data-stu-id="f4ef9-797">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="f4ef9-798">Definizione</span><span class="sxs-lookup"><span data-stu-id="f4ef9-798">Definition</span></span>

<span data-ttu-id="f4ef9-799">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="f4ef9-799">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="f4ef9-800">La funzione `Func_slovenia_eu_tax_file_number` consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="f4ef9-800">The function  `Func_slovenia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="f4ef9-801">Una parola chiave da `Keywords_slovenia_eu_tax_file_number` viene trovato.</span><span class="sxs-lookup"><span data-stu-id="f4ef9-801">A keyword from  `Keywords_slovenia_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="f4ef9-802">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="f4ef9-802">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="f4ef9-803">La funzione `Func_slovenia_eu_tax_file_number` consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="f4ef9-803">The function  `Func_slovenia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="f4ef9-804">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="f4ef9-804">Keywords</span></span>

#### <a name="keywordssloveniaeutaxfilenumber"></a><span data-ttu-id="f4ef9-805">Keywords_slovenia_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="f4ef9-805">Keywords_slovenia_eu_tax_file_number</span></span>

<span data-ttu-id="f4ef9-806">tax id
</span><span class="sxs-lookup"><span data-stu-id="f4ef9-806">tax id</span></span>
  
<span data-ttu-id="f4ef9-807">codice fiscale</span><span class="sxs-lookup"><span data-stu-id="f4ef9-807">tax id number</span></span>
  
<span data-ttu-id="f4ef9-808">id stagno</span><span class="sxs-lookup"><span data-stu-id="f4ef9-808">tin id</span></span>
  
<span data-ttu-id="f4ef9-809">no stagno</span><span class="sxs-lookup"><span data-stu-id="f4ef9-809">tin no</span></span>
  
<span data-ttu-id="f4ef9-810">id stagno sloveno</span><span class="sxs-lookup"><span data-stu-id="f4ef9-810">slovenian tin id</span></span>
  
<span data-ttu-id="f4ef9-811">tin
</span><span class="sxs-lookup"><span data-stu-id="f4ef9-811">tin</span></span>
  
<span data-ttu-id="f4ef9-812">Imposta i file non</span><span class="sxs-lookup"><span data-stu-id="f4ef9-812">tax file no</span></span>
  
<span data-ttu-id="f4ef9-813">

tax file number</span><span class="sxs-lookup"><span data-stu-id="f4ef9-813">tax file number</span></span>
  
<span data-ttu-id="f4ef9-814">Imposta n</span><span class="sxs-lookup"><span data-stu-id="f4ef9-814">tax no</span></span>
  
<span data-ttu-id="f4ef9-815">Imposta numero</span><span class="sxs-lookup"><span data-stu-id="f4ef9-815">tax number</span></span>
  
<span data-ttu-id="f4ef9-816">taxid #</span><span class="sxs-lookup"><span data-stu-id="f4ef9-816">taxid#</span></span>
  
<span data-ttu-id="f4ef9-817">taxno #</span><span class="sxs-lookup"><span data-stu-id="f4ef9-817">taxno#</span></span>
  
<span data-ttu-id="f4ef9-818">identifikacijska številka davka</span><span class="sxs-lookup"><span data-stu-id="f4ef9-818">identifikacijska številka davka</span></span>
  
<span data-ttu-id="f4ef9-819">davčna številka</span><span class="sxs-lookup"><span data-stu-id="f4ef9-819">davčna številka</span></span>
  
<span data-ttu-id="f4ef9-820">Številka davčne datoteke</span><span class="sxs-lookup"><span data-stu-id="f4ef9-820">številka davčne datoteke</span></span>
  
## <a name="spain"></a><span data-ttu-id="f4ef9-821">Spagna</span><span class="sxs-lookup"><span data-stu-id="f4ef9-821">Spain</span></span>

### <a name="format"></a><span data-ttu-id="f4ef9-822">Formato</span><span class="sxs-lookup"><span data-stu-id="f4ef9-822">Format</span></span>

<span data-ttu-id="f4ef9-823">Otto o sette cifre e uno o due lettere nella serie specificata</span><span class="sxs-lookup"><span data-stu-id="f4ef9-823">Seven or eight digits and one or two letters in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="f4ef9-824">Modello</span><span class="sxs-lookup"><span data-stu-id="f4ef9-824">Pattern</span></span>

<span data-ttu-id="f4ef9-825">Spagnolo persone con una carta d'identità nazionale Spagna:</span><span class="sxs-lookup"><span data-stu-id="f4ef9-825">Spanish Natural Persons with a Spain National Identity Card:</span></span>
  
-  <span data-ttu-id="f4ef9-826">Otto cifre</span><span class="sxs-lookup"><span data-stu-id="f4ef9-826">Eight digits</span></span> 
    
- <span data-ttu-id="f4ef9-827">Una lettera maiuscola (maiuscole/minuscole)</span><span class="sxs-lookup"><span data-stu-id="f4ef9-827">One uppercase letter (case-sensitive)</span></span> 
    
<span data-ttu-id="f4ef9-828">Non residenti Spaniards senza un carta d'identità nazionale Spagna</span><span class="sxs-lookup"><span data-stu-id="f4ef9-828">Non-resident Spaniards without a Spain National Identity Card</span></span>
  
- <span data-ttu-id="f4ef9-829">Una lettera maiuscola "L" (maiuscole/minuscole)</span><span class="sxs-lookup"><span data-stu-id="f4ef9-829">One uppercase letter "L" (case-sensitive)</span></span>
    
- <span data-ttu-id="f4ef9-830">Sette cifre</span><span class="sxs-lookup"><span data-stu-id="f4ef9-830">Seven digits</span></span>
    
- <span data-ttu-id="f4ef9-831">Una lettera maiuscola (maiuscole/minuscole)</span><span class="sxs-lookup"><span data-stu-id="f4ef9-831">One uppercase letter (case-sensitive)</span></span> 
    
<span data-ttu-id="f4ef9-832">Spaniards residenti minori di 14 anni senza un Spagna nazionale carta d'identità:</span><span class="sxs-lookup"><span data-stu-id="f4ef9-832">Resident Spaniards under the age of 14 years without a Spain National Identity Card :</span></span>
  
- <span data-ttu-id="f4ef9-833">Una lettera maiuscola "K" (maiuscole/minuscole)</span><span class="sxs-lookup"><span data-stu-id="f4ef9-833">One uppercase letter"K" (case-sensitive)</span></span>
    
-  <span data-ttu-id="f4ef9-834">Sette cifre</span><span class="sxs-lookup"><span data-stu-id="f4ef9-834">Seven digits</span></span> 
    
- <span data-ttu-id="f4ef9-835">Una lettera maiuscola (maiuscole/minuscole)</span><span class="sxs-lookup"><span data-stu-id="f4ef9-835">One uppercase letter (case-sensitive)</span></span>
    
<span data-ttu-id="f4ef9-836">Stranieri con numero di identificazione del Foreigner</span><span class="sxs-lookup"><span data-stu-id="f4ef9-836">Foreigners with a Foreigner's Identification Number</span></span>
  
- <span data-ttu-id="f4ef9-837">Vale a dire maiuscoli una lettera "X", "Y" o "Z" (maiuscole/minuscole)</span><span class="sxs-lookup"><span data-stu-id="f4ef9-837">One uppercase letter that is "X", "Y", or "Z" (case-sensitive)</span></span> 
    
- <span data-ttu-id="f4ef9-838">Sette cifre</span><span class="sxs-lookup"><span data-stu-id="f4ef9-838">Seven digits</span></span>
    
- <span data-ttu-id="f4ef9-839">Una lettera maiuscola (maiuscole/minuscole)</span><span class="sxs-lookup"><span data-stu-id="f4ef9-839">One uppercase letter (case-sensitive)</span></span> 
    
<span data-ttu-id="f4ef9-840">Stranieri senza numero di identificazione del Foreigner</span><span class="sxs-lookup"><span data-stu-id="f4ef9-840">Foreigners without a Foreigner's Identification Number</span></span>
  
- <span data-ttu-id="f4ef9-841">Una lettera maiuscola che è "M" (maiuscole/minuscole)</span><span class="sxs-lookup"><span data-stu-id="f4ef9-841">One uppercase letter that is "M" (case-sensitive)</span></span> 
    
- <span data-ttu-id="f4ef9-842">Sette cifre</span><span class="sxs-lookup"><span data-stu-id="f4ef9-842">Seven digits</span></span>
    
- <span data-ttu-id="f4ef9-843">Una lettera maiuscola (maiuscole/minuscole)</span><span class="sxs-lookup"><span data-stu-id="f4ef9-843">One uppercase letter (case-sensitive)</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="f4ef9-844">Checksum</span><span class="sxs-lookup"><span data-stu-id="f4ef9-844">Checksum</span></span>

<span data-ttu-id="f4ef9-845">Sì</span><span class="sxs-lookup"><span data-stu-id="f4ef9-845">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="f4ef9-846">Definizione</span><span class="sxs-lookup"><span data-stu-id="f4ef9-846">Definition</span></span>

<span data-ttu-id="f4ef9-847">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="f4ef9-847">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="f4ef9-848">La funzione `Func_spain_eu_tax_file_number` consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="f4ef9-848">The function  `Func_spain_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="f4ef9-849">Una parola chiave da `Keywords_spain_eu_tax_file_number` viene trovato.</span><span class="sxs-lookup"><span data-stu-id="f4ef9-849">A keyword from  `Keywords_spain_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="f4ef9-850">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="f4ef9-850">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="f4ef9-851">La funzione `Func_spain_eu_tax_file_number` consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="f4ef9-851">The function  `Func_spain_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="f4ef9-852">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="f4ef9-852">Keywords</span></span>

#### <a name="keywordsspaineutaxfilenumber"></a><span data-ttu-id="f4ef9-853">Keywords_spain_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="f4ef9-853">Keywords_spain_eu_tax_file_number</span></span>

<span data-ttu-id="f4ef9-854">tax id
</span><span class="sxs-lookup"><span data-stu-id="f4ef9-854">tax id</span></span>
  
<span data-ttu-id="f4ef9-855">codice fiscale</span><span class="sxs-lookup"><span data-stu-id="f4ef9-855">tax id number</span></span>
  
<span data-ttu-id="f4ef9-856">id cif</span><span class="sxs-lookup"><span data-stu-id="f4ef9-856">cif id</span></span>
  
<span data-ttu-id="f4ef9-857">cif non</span><span class="sxs-lookup"><span data-stu-id="f4ef9-857">cif no</span></span>
  
<span data-ttu-id="f4ef9-858">id lingua spagnola cif</span><span class="sxs-lookup"><span data-stu-id="f4ef9-858">spanish cif id</span></span>
  
<span data-ttu-id="f4ef9-859">cif</span><span class="sxs-lookup"><span data-stu-id="f4ef9-859">cif</span></span>
  
<span data-ttu-id="f4ef9-860">Imposta i file non</span><span class="sxs-lookup"><span data-stu-id="f4ef9-860">tax file no</span></span>
  
<span data-ttu-id="f4ef9-861">numero cif spagnolo</span><span class="sxs-lookup"><span data-stu-id="f4ef9-861">spanish cif number</span></span>
  
<span data-ttu-id="f4ef9-862">

tax file number</span><span class="sxs-lookup"><span data-stu-id="f4ef9-862">tax file number</span></span>
  
<span data-ttu-id="f4ef9-863">Spagnolo cif non</span><span class="sxs-lookup"><span data-stu-id="f4ef9-863">spanish cif no</span></span>
  
<span data-ttu-id="f4ef9-864">Imposta n</span><span class="sxs-lookup"><span data-stu-id="f4ef9-864">tax no</span></span>
  
<span data-ttu-id="f4ef9-865">Imposta numero</span><span class="sxs-lookup"><span data-stu-id="f4ef9-865">tax number</span></span>
  
<span data-ttu-id="f4ef9-866">taxid #</span><span class="sxs-lookup"><span data-stu-id="f4ef9-866">taxid#</span></span>
  
<span data-ttu-id="f4ef9-867">taxno #</span><span class="sxs-lookup"><span data-stu-id="f4ef9-867">taxno#</span></span>
  
<span data-ttu-id="f4ef9-868">cifid #</span><span class="sxs-lookup"><span data-stu-id="f4ef9-868">cifid#</span></span>
  
<span data-ttu-id="f4ef9-869">spanishcifid #</span><span class="sxs-lookup"><span data-stu-id="f4ef9-869">spanishcifid#</span></span>
  
<span data-ttu-id="f4ef9-870">spanishcifno #</span><span class="sxs-lookup"><span data-stu-id="f4ef9-870">spanishcifno#</span></span>
  
<span data-ttu-id="f4ef9-871">número de contribuyente</span><span class="sxs-lookup"><span data-stu-id="f4ef9-871">número de contribuyente</span></span>
  
<span data-ttu-id="f4ef9-872">número de impuesto corporativo</span><span class="sxs-lookup"><span data-stu-id="f4ef9-872">número de impuesto corporativo</span></span>
  
<span data-ttu-id="f4ef9-873">número de identificación fiscali</span><span class="sxs-lookup"><span data-stu-id="f4ef9-873">número de identificación fiscal</span></span>
  
<span data-ttu-id="f4ef9-874">cif número</span><span class="sxs-lookup"><span data-stu-id="f4ef9-874">cif número</span></span>
  
<span data-ttu-id="f4ef9-875">cifnúmero #</span><span class="sxs-lookup"><span data-stu-id="f4ef9-875">cifnúmero#</span></span>
  
## <a name="sweden"></a><span data-ttu-id="f4ef9-876">Svezia</span><span class="sxs-lookup"><span data-stu-id="f4ef9-876">Sweden</span></span>

### <a name="format"></a><span data-ttu-id="f4ef9-877">Formato</span><span class="sxs-lookup"><span data-stu-id="f4ef9-877">Format</span></span>

<span data-ttu-id="f4ef9-878">Dieci cifre e un simbolo nella serie specificata</span><span class="sxs-lookup"><span data-stu-id="f4ef9-878">Ten digits and a symbol in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="f4ef9-879">Modello</span><span class="sxs-lookup"><span data-stu-id="f4ef9-879">Pattern</span></span>

<span data-ttu-id="f4ef9-880">Dieci cifre e un simbolo:</span><span class="sxs-lookup"><span data-stu-id="f4ef9-880">Ten digits and a symbol:</span></span>
  
-  <span data-ttu-id="f4ef9-881">Sei cifre che corrispondono alla data di nascita (AAMMGG)</span><span class="sxs-lookup"><span data-stu-id="f4ef9-881">Six digits that correspond to the birth date (YYMMDD)</span></span> 
    
- <span data-ttu-id="f4ef9-882">Un segno di addizione, segno di sottrazione o barra rovesciata</span><span class="sxs-lookup"><span data-stu-id="f4ef9-882">A plus sign, minus sign, or backslash</span></span>
    
- <span data-ttu-id="f4ef9-883">Tre cifre che rendono l'identificazione dei numeri univoco where:</span><span class="sxs-lookup"><span data-stu-id="f4ef9-883">Three digits that make the identification number unique where:</span></span> 
    
  - <span data-ttu-id="f4ef9-884">Per i numeri rilasciati prima 1990, la cifra settima e ottava identificare la provincia di nascita o utenti foreign-born</span><span class="sxs-lookup"><span data-stu-id="f4ef9-884">For numbers issued before 1990, the seventh and eighth digit identify the county of birth or foreign-born people</span></span>
    
  - <span data-ttu-id="f4ef9-885">La cifra nella posizione nona indica sesso per entrambi dispari per maschile o persino femmina</span><span class="sxs-lookup"><span data-stu-id="f4ef9-885">The digit in the ninth position indicates gender by either odd for male or even for female</span></span>
    
- <span data-ttu-id="f4ef9-886">Cifra di un controllo</span><span class="sxs-lookup"><span data-stu-id="f4ef9-886">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="f4ef9-887">Checksum</span><span class="sxs-lookup"><span data-stu-id="f4ef9-887">Checksum</span></span>

<span data-ttu-id="f4ef9-888">Sì</span><span class="sxs-lookup"><span data-stu-id="f4ef9-888">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="f4ef9-889">Definizione</span><span class="sxs-lookup"><span data-stu-id="f4ef9-889">Definition</span></span>

<span data-ttu-id="f4ef9-890">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="f4ef9-890">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="f4ef9-891">La funzione `Func_sweden_eu_tax_file_number` consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="f4ef9-891">The function  `Func_sweden_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="f4ef9-892">Una parola chiave da `Keywords_sweden_eu_tax_file_number` viene trovato.</span><span class="sxs-lookup"><span data-stu-id="f4ef9-892">A keyword from  `Keywords_sweden_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="f4ef9-893">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="f4ef9-893">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="f4ef9-894">La funzione `Func_sweden_eu_tax_file_number` consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="f4ef9-894">The function  `Func_sweden_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="f4ef9-895">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="f4ef9-895">Keywords</span></span>

#### <a name="keywordsswedeneutaxfilenumber"></a><span data-ttu-id="f4ef9-896">Keywords_sweden_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="f4ef9-896">Keywords_sweden_eu_tax_file_number</span></span>

<span data-ttu-id="f4ef9-897">tax id
</span><span class="sxs-lookup"><span data-stu-id="f4ef9-897">tax id</span></span>
  
<span data-ttu-id="f4ef9-898">id imposta non.</span><span class="sxs-lookup"><span data-stu-id="f4ef9-898">tax id no.</span></span>
  
<span data-ttu-id="f4ef9-899">codice fiscale</span><span class="sxs-lookup"><span data-stu-id="f4ef9-899">tax id number</span></span>
  
<span data-ttu-id="f4ef9-900">tax identification
</span><span class="sxs-lookup"><span data-stu-id="f4ef9-900">tax identification</span></span>
  
<span data-ttu-id="f4ef9-901">Imposta identificazione #</span><span class="sxs-lookup"><span data-stu-id="f4ef9-901">tax identification#</span></span>
  
<span data-ttu-id="f4ef9-902">imposte no.</span><span class="sxs-lookup"><span data-stu-id="f4ef9-902">tax no.</span></span>
  
<span data-ttu-id="f4ef9-903">Imposta #</span><span class="sxs-lookup"><span data-stu-id="f4ef9-903">tax#</span></span>
  
<span data-ttu-id="f4ef9-904">taxid #</span><span class="sxs-lookup"><span data-stu-id="f4ef9-904">taxid#</span></span>
  
<span data-ttu-id="f4ef9-905">file fiscali</span><span class="sxs-lookup"><span data-stu-id="f4ef9-905">tax file</span></span>
  
<span data-ttu-id="f4ef9-906">imposte non file.</span><span class="sxs-lookup"><span data-stu-id="f4ef9-906">tax file no.</span></span>
  
<span data-ttu-id="f4ef9-907">numero id personale</span><span class="sxs-lookup"><span data-stu-id="f4ef9-907">personal id number</span></span>
  
<span data-ttu-id="f4ef9-908">skatt id nummer</span><span class="sxs-lookup"><span data-stu-id="f4ef9-908">skatt id nummer</span></span>
  
<span data-ttu-id="f4ef9-909">skatt identifikation</span><span class="sxs-lookup"><span data-stu-id="f4ef9-909">skatt identifikation</span></span>
  
<span data-ttu-id="f4ef9-910">personnummer</span><span class="sxs-lookup"><span data-stu-id="f4ef9-910">personnummer</span></span>
  
## <a name="uk"></a><span data-ttu-id="f4ef9-911">REGNO UNITO</span><span class="sxs-lookup"><span data-stu-id="f4ef9-911">UK</span></span>

### <a name="format"></a><span data-ttu-id="f4ef9-912">Formato</span><span class="sxs-lookup"><span data-stu-id="f4ef9-912">Format</span></span>

<span data-ttu-id="f4ef9-913">Riferimento fiscale univoco (UTR): 10 cifre senza spazi e i delimitatori</span><span class="sxs-lookup"><span data-stu-id="f4ef9-913">Unique Taxpayer Reference (UTR): 10 digits without spaces and delimiters</span></span>
  
<span data-ttu-id="f4ef9-p103">Numero di assicurazione nazionale (NINO): Per ulteriori informazioni, vedere la sezione "Regno Unito di numero di assicurazione nazionale (NINO)" in [cercare il quali i tipi di informazioni riservate](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="f4ef9-p103">National Insurance Number (NINO): For details, see the section "U.K. National Insurance Number (NINO)" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
### <a name="pattern"></a><span data-ttu-id="f4ef9-916">Modello</span><span class="sxs-lookup"><span data-stu-id="f4ef9-916">Pattern</span></span>

<span data-ttu-id="f4ef9-917">Riferimento fiscale univoco (UTR): 10 cifre</span><span class="sxs-lookup"><span data-stu-id="f4ef9-917">Unique Taxpayer Reference (UTR): 10 digits</span></span>
  
<span data-ttu-id="f4ef9-p104">Numero di assicurazione nazionale (NINO): Per ulteriori informazioni, vedere la sezione "Regno Unito di numero di assicurazione nazionale (NINO)" in [cercare il quali i tipi di informazioni riservate](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="f4ef9-p104">National Insurance Number (NINO): For details, see the section "U.K. National Insurance Number (NINO)" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
### <a name="checksum"></a><span data-ttu-id="f4ef9-920">Checksum</span><span class="sxs-lookup"><span data-stu-id="f4ef9-920">Checksum</span></span>

<span data-ttu-id="f4ef9-921">Sì</span><span class="sxs-lookup"><span data-stu-id="f4ef9-921">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="f4ef9-922">Definizione</span><span class="sxs-lookup"><span data-stu-id="f4ef9-922">Definition</span></span>

<span data-ttu-id="f4ef9-923">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="f4ef9-923">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="f4ef9-924">La funzione `Func_uk_eu_tax_file_number` consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="f4ef9-924">The function  `Func_uk_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="f4ef9-925">Una parola chiave da `Keywords_uk_eu_tax_file_number` viene trovato.</span><span class="sxs-lookup"><span data-stu-id="f4ef9-925">A keyword from  `Keywords_uk_eu_tax_file_number` is found.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_uk_eu_tax_file_number" />
          <Match idRef="Keywords_uk_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="f4ef9-926">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="f4ef9-926">Keywords</span></span>

#### <a name="keywordsukeutaxfilenumber"></a><span data-ttu-id="f4ef9-927">Keywords_uk_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="f4ef9-927">Keywords_uk_eu_tax_file_number</span></span>

<span data-ttu-id="f4ef9-928">tax id
</span><span class="sxs-lookup"><span data-stu-id="f4ef9-928">tax id</span></span>
  
<span data-ttu-id="f4ef9-929">id imposta non.</span><span class="sxs-lookup"><span data-stu-id="f4ef9-929">tax id no.</span></span>
  
<span data-ttu-id="f4ef9-930">codice fiscale</span><span class="sxs-lookup"><span data-stu-id="f4ef9-930">tax id number</span></span>
  
<span data-ttu-id="f4ef9-931">tax identification
</span><span class="sxs-lookup"><span data-stu-id="f4ef9-931">tax identification</span></span>
  
<span data-ttu-id="f4ef9-932">Imposta identificazione #</span><span class="sxs-lookup"><span data-stu-id="f4ef9-932">tax identification#</span></span>
  
<span data-ttu-id="f4ef9-933">imposte no.</span><span class="sxs-lookup"><span data-stu-id="f4ef9-933">tax no.</span></span>
  
<span data-ttu-id="f4ef9-934">Imposta #</span><span class="sxs-lookup"><span data-stu-id="f4ef9-934">tax#</span></span>
  
<span data-ttu-id="f4ef9-935">taxid #</span><span class="sxs-lookup"><span data-stu-id="f4ef9-935">taxid#</span></span>
  
<span data-ttu-id="f4ef9-936">file fiscali</span><span class="sxs-lookup"><span data-stu-id="f4ef9-936">tax file</span></span>
  
<span data-ttu-id="f4ef9-937">imposte non file.</span><span class="sxs-lookup"><span data-stu-id="f4ef9-937">tax file no.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="f4ef9-938">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f4ef9-938">See also</span></span>

[<span data-ttu-id="f4ef9-939">Cosa individuano i tipi di informazioni riservate</span><span class="sxs-lookup"><span data-stu-id="f4ef9-939">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)

