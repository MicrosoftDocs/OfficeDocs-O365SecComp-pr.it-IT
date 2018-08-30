---
title: Numero della patente di Guida di Unione europea
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 8/17/2018
ms.audience: Admin
ms.topic: reference
ms.service: o365-administration
localization_priority: Normal
ms.assetid: c3923cd3-ec84-435f-bf41-cadc37996a4b
description: Questo argomento viene illustrato quali criteri di criterio DLP perdita dei dati Cerca qualora venga rilevato un tipo di informazione sensibile numero della patente di Guida dell'Unione europea. Questo tipo di informazioni riservate definisce le diverse combinazioni, parole chiave e altri elementi di prova per ogni paese.
ms.openlocfilehash: 065684249f9766d567c63e6b8170d36f56692e45
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/27/2018
ms.locfileid: "22530763"
---
# <a name="eu-drivers-license-number"></a><span data-ttu-id="51ea7-104">Numero della patente di Guida di Unione europea</span><span class="sxs-lookup"><span data-stu-id="51ea7-104">EU Driver's License Number</span></span>

<span data-ttu-id="51ea7-p102">Questo argomento viene illustrato quali criteri di criterio DLP perdita dei dati Cerca qualora venga rilevato un tipo di informazione sensibile numero della patente di Guida dell'Unione europea. Questo tipo di informazioni riservate definisce le diverse combinazioni, parole chiave e altri elementi di prova per ogni paese.</span><span class="sxs-lookup"><span data-stu-id="51ea7-p102">This topic shows what a data loss prevention (DLP) policy looks for when it detects the EU Driver's License Number sensitive information type. This sensitive information type defines different patterns, keywords, and other evidence for each country.</span></span>
  
## <a name="austria"></a><span data-ttu-id="51ea7-107">Austria</span><span class="sxs-lookup"><span data-stu-id="51ea7-107">Austria</span></span>

### <a name="format"></a><span data-ttu-id="51ea7-108">Formato</span><span class="sxs-lookup"><span data-stu-id="51ea7-108">Format</span></span>

<span data-ttu-id="51ea7-109">Otto cifre senza spazi e i delimitatori</span><span class="sxs-lookup"><span data-stu-id="51ea7-109">Eight digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="51ea7-110">Modello</span><span class="sxs-lookup"><span data-stu-id="51ea7-110">Pattern</span></span>

<span data-ttu-id="51ea7-111">Otto cifre</span><span class="sxs-lookup"><span data-stu-id="51ea7-111">Eight digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="51ea7-112">Checksum</span><span class="sxs-lookup"><span data-stu-id="51ea7-112">Checksum</span></span>

<span data-ttu-id="51ea7-113">No</span><span class="sxs-lookup"><span data-stu-id="51ea7-113">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="51ea7-114">Definizione</span><span class="sxs-lookup"><span data-stu-id="51ea7-114">Definition</span></span>

<span data-ttu-id="51ea7-115">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="51ea7-115">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="51ea7-116">L'espressione regolare `Regex_austria_eu_driver's_license_number` consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="51ea7-116">The regular expression  `Regex_austria_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="51ea7-117">Una parola chiave da `Keywords_austria_eu_driver's_license_number` viene trovato.</span><span class="sxs-lookup"><span data-stu-id="51ea7-117">A keyword from  `Keywords_austria_eu_driver's_license_number` is found.</span></span> 
    
```
<!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_austria_eu_driver's_license_number" />
          <Match idRef="Keywords_austria_eu_driver's_license_number" />
        </Pattern>
    </Entity>

```

### <a name="keywords"></a><span data-ttu-id="51ea7-118">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="51ea7-118">Keywords</span></span>

<span data-ttu-id="51ea7-119">| |</span><span class="sxs-lookup"><span data-stu-id="51ea7-119"></span></span>
|<span data-ttu-id="51ea7-120">**Keywords_austria_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="51ea7-120">**Keywords_austria_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="51ea7-121">DL #</span><span class="sxs-lookup"><span data-stu-id="51ea7-121">dl#</span></span>  <br/> <span data-ttu-id="51ea7-122">patente</span><span class="sxs-lookup"><span data-stu-id="51ea7-122">driver license</span></span>  <br/> <span data-ttu-id="51ea7-123">Numero patente di Guida</span><span class="sxs-lookup"><span data-stu-id="51ea7-123">driver license number</span></span>  <br/> <span data-ttu-id="51ea7-124">titolo driver</span><span class="sxs-lookup"><span data-stu-id="51ea7-124">driver licence</span></span>  <br/> <span data-ttu-id="51ea7-125">driver lic.</span><span class="sxs-lookup"><span data-stu-id="51ea7-125">drivers lic.</span></span>  <br/> <span data-ttu-id="51ea7-126">patente di Guida</span><span class="sxs-lookup"><span data-stu-id="51ea7-126">drivers license</span></span>  <br/> <span data-ttu-id="51ea7-127">titolo della patente di Guida</span><span class="sxs-lookup"><span data-stu-id="51ea7-127">driver's licence</span></span>  <br/> <span data-ttu-id="51ea7-128">patente</span><span class="sxs-lookup"><span data-stu-id="51ea7-128">driver's license</span></span>  <br/> <span data-ttu-id="51ea7-129">numero della patente di Guida</span><span class="sxs-lookup"><span data-stu-id="51ea7-129">driver's license number</span></span>  <br/> <span data-ttu-id="51ea7-130">numero della patente di Guida</span><span class="sxs-lookup"><span data-stu-id="51ea7-130">driver's licence number</span></span>  <br/>  <span data-ttu-id="51ea7-131">che influisce sul numero di licenza</span><span class="sxs-lookup"><span data-stu-id="51ea7-131">driving license number</span></span>  <br/> <span data-ttu-id="51ea7-132">dlno #</span><span class="sxs-lookup"><span data-stu-id="51ea7-132">dlno#</span></span>  <br/> <span data-ttu-id="51ea7-133">fuhrerschein</span><span class="sxs-lookup"><span data-stu-id="51ea7-133">fuhrerschein</span></span>  <br/> <span data-ttu-id="51ea7-134">fuhrerschein italiana osterreich</span><span class="sxs-lookup"><span data-stu-id="51ea7-134">fuhrerschein republik osterreich</span></span>  <br/> |
   
## <a name="belgium"></a><span data-ttu-id="51ea7-135">Belgio</span><span class="sxs-lookup"><span data-stu-id="51ea7-135">Belgium</span></span>

### <a name="format"></a><span data-ttu-id="51ea7-136">Formato</span><span class="sxs-lookup"><span data-stu-id="51ea7-136">Format</span></span>

<span data-ttu-id="51ea7-137">10 cifre senza spazi e i delimitatori</span><span class="sxs-lookup"><span data-stu-id="51ea7-137">10 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="51ea7-138">Modello</span><span class="sxs-lookup"><span data-stu-id="51ea7-138">Pattern</span></span>

<span data-ttu-id="51ea7-139">10 cifre</span><span class="sxs-lookup"><span data-stu-id="51ea7-139">10 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="51ea7-140">Checksum</span><span class="sxs-lookup"><span data-stu-id="51ea7-140">Checksum</span></span>

<span data-ttu-id="51ea7-141">No</span><span class="sxs-lookup"><span data-stu-id="51ea7-141">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="51ea7-142">Definizione</span><span class="sxs-lookup"><span data-stu-id="51ea7-142">Definition</span></span>

<span data-ttu-id="51ea7-143">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="51ea7-143">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="51ea7-144">L'espressione regolare `Regex_belgium_eu_driver's_license_number` consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="51ea7-144">The regular expression  `Regex_belgium_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="51ea7-145">Una parola chiave da `Keywords_belgium_eu_driver's_license_number` viene trovato.</span><span class="sxs-lookup"><span data-stu-id="51ea7-145">A keyword from  `Keywords_belgium_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_belgium_eu_driver's_license_number" />
          <Match idRef="Keywords_belgium_eu_driver's_license_number" />
        </Pattern>
</Entity>

```

### <a name="keywords"></a><span data-ttu-id="51ea7-146">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="51ea7-146">Keywords</span></span>

<span data-ttu-id="51ea7-147">| |</span><span class="sxs-lookup"><span data-stu-id="51ea7-147"></span></span>
|<span data-ttu-id="51ea7-148">**Keywords__belgium_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="51ea7-148">**Keywords__belgium_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="51ea7-149">DL #</span><span class="sxs-lookup"><span data-stu-id="51ea7-149">dl#</span></span>  <br/> <span data-ttu-id="51ea7-150">patente</span><span class="sxs-lookup"><span data-stu-id="51ea7-150">driver license</span></span>  <br/> <span data-ttu-id="51ea7-151">Numero patente di Guida</span><span class="sxs-lookup"><span data-stu-id="51ea7-151">driver license number</span></span>  <br/> <span data-ttu-id="51ea7-152">titolo driver</span><span class="sxs-lookup"><span data-stu-id="51ea7-152">driver licence</span></span>  <br/> <span data-ttu-id="51ea7-153">driver lic.</span><span class="sxs-lookup"><span data-stu-id="51ea7-153">drivers lic.</span></span>  <br/> <span data-ttu-id="51ea7-154">patente di Guida</span><span class="sxs-lookup"><span data-stu-id="51ea7-154">drivers license</span></span>  <br/> <span data-ttu-id="51ea7-155">drivers licence</span><span class="sxs-lookup"><span data-stu-id="51ea7-155">drivers licence</span></span>  <br/> <span data-ttu-id="51ea7-156">patente</span><span class="sxs-lookup"><span data-stu-id="51ea7-156">driver's license</span></span>  <br/> <span data-ttu-id="51ea7-157">numero della patente di Guida</span><span class="sxs-lookup"><span data-stu-id="51ea7-157">driver's license number</span></span>  <br/> <span data-ttu-id="51ea7-158">numero della patente di Guida</span><span class="sxs-lookup"><span data-stu-id="51ea7-158">driver's licence number</span></span>  <br/> <span data-ttu-id="51ea7-159">dlno #</span><span class="sxs-lookup"><span data-stu-id="51ea7-159">dlno#</span></span>  <br/> <span data-ttu-id="51ea7-160">rijbewijs</span><span class="sxs-lookup"><span data-stu-id="51ea7-160">rijbewijs</span></span>  <br/> <span data-ttu-id="51ea7-161">rijbewijsnummer</span><span class="sxs-lookup"><span data-stu-id="51ea7-161">rijbewijsnummer</span></span>  <br/> <span data-ttu-id="51ea7-162">führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="51ea7-162">führerscheinnummer</span></span>  <br/> <span data-ttu-id="51ea7-163">fuhrerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="51ea7-163">fuhrerscheinnummer</span></span>  <br/> <span data-ttu-id="51ea7-164">fuehrerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="51ea7-164">fuehrerscheinnummer</span></span>  <br/> <span data-ttu-id="51ea7-165">führerschein nr</span><span class="sxs-lookup"><span data-stu-id="51ea7-165">führerschein- nr</span></span>  <br/> <span data-ttu-id="51ea7-166">fuehrerschein Nr</span><span class="sxs-lookup"><span data-stu-id="51ea7-166">fuehrerschein- Nr</span></span>  <br/> <span data-ttu-id="51ea7-167">fuehrerschein nr</span><span class="sxs-lookup"><span data-stu-id="51ea7-167">fuehrerschein- nr</span></span>  <br/> |
   
## <a name="bulgaria"></a><span data-ttu-id="51ea7-168">Bulgaria</span><span class="sxs-lookup"><span data-stu-id="51ea7-168">Bulgaria</span></span>

### <a name="format"></a><span data-ttu-id="51ea7-169">Formato</span><span class="sxs-lookup"><span data-stu-id="51ea7-169">Format</span></span>

<span data-ttu-id="51ea7-170">Nove cifre senza spazi e i delimitatori</span><span class="sxs-lookup"><span data-stu-id="51ea7-170">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="51ea7-171">Modello</span><span class="sxs-lookup"><span data-stu-id="51ea7-171">Pattern</span></span>

<span data-ttu-id="51ea7-172">9 cifre</span><span class="sxs-lookup"><span data-stu-id="51ea7-172">Nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="51ea7-173">Checksum</span><span class="sxs-lookup"><span data-stu-id="51ea7-173">Checksum</span></span>

<span data-ttu-id="51ea7-174">No</span><span class="sxs-lookup"><span data-stu-id="51ea7-174">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="51ea7-175">Definizione</span><span class="sxs-lookup"><span data-stu-id="51ea7-175">Definition</span></span>

<span data-ttu-id="51ea7-176">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="51ea7-176">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="51ea7-177">L'espressione regolare `Regex_bulgaria_eu_driver's_license_number` consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="51ea7-177">The regular expression  `Regex_bulgaria_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="51ea7-178">Una parola chiave da `Keywords_bulgaria_eu_driver's_license_number` viene trovato.</span><span class="sxs-lookup"><span data-stu-id="51ea7-178">A keyword from  `Keywords_bulgaria_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
             <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_bulgaria_eu_driver's_license_number" />
          <Match idRef="Keywords_bulgaria_eu_driver's_license_number" />
        </Pattern> 
</Entity>    

```

### <a name="keywords"></a><span data-ttu-id="51ea7-179">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="51ea7-179">Keywords</span></span>

<span data-ttu-id="51ea7-180">| |</span><span class="sxs-lookup"><span data-stu-id="51ea7-180"></span></span>
|<span data-ttu-id="51ea7-181">**Keywords_bulgaria_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="51ea7-181">**Keywords_bulgaria_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="51ea7-182">DL #</span><span class="sxs-lookup"><span data-stu-id="51ea7-182">dl#</span></span>  <br/> <span data-ttu-id="51ea7-183">patente</span><span class="sxs-lookup"><span data-stu-id="51ea7-183">driver license</span></span>  <br/> <span data-ttu-id="51ea7-184">Numero patente di Guida</span><span class="sxs-lookup"><span data-stu-id="51ea7-184">driver license number</span></span>  <br/> <span data-ttu-id="51ea7-185">titolo driver</span><span class="sxs-lookup"><span data-stu-id="51ea7-185">driver licence</span></span>  <br/> <span data-ttu-id="51ea7-186">driver lic.</span><span class="sxs-lookup"><span data-stu-id="51ea7-186">drivers lic.</span></span>  <br/> <span data-ttu-id="51ea7-187">patente di Guida</span><span class="sxs-lookup"><span data-stu-id="51ea7-187">drivers license</span></span>  <br/> <span data-ttu-id="51ea7-188">drivers licence</span><span class="sxs-lookup"><span data-stu-id="51ea7-188">drivers licence</span></span>  <br/> <span data-ttu-id="51ea7-189">patente</span><span class="sxs-lookup"><span data-stu-id="51ea7-189">driver's license</span></span>  <br/> <span data-ttu-id="51ea7-190">numero della patente di Guida</span><span class="sxs-lookup"><span data-stu-id="51ea7-190">driver's license number</span></span>  <br/> <span data-ttu-id="51ea7-191">numero della patente di Guida</span><span class="sxs-lookup"><span data-stu-id="51ea7-191">driver's licence number</span></span>  <br/> <span data-ttu-id="51ea7-192">che influisce sul numero di licenza</span><span class="sxs-lookup"><span data-stu-id="51ea7-192">driving license number</span></span>  <br/> <span data-ttu-id="51ea7-193">dlno #</span><span class="sxs-lookup"><span data-stu-id="51ea7-193">dlno#</span></span>  <br/> <span data-ttu-id="51ea7-194">СВИДЕТЕЛСТВО ЗА УПРАВЛЕНИЕ НА МПС</span><span class="sxs-lookup"><span data-stu-id="51ea7-194">свидетелство за управление на мпс</span></span>  <br/> <span data-ttu-id="51ea7-195">СВИДЕТЕЛСТВО ЗА УПРАВЛЕНИЕ НА МОТОРНО ПРЕВОЗНО СРЕДСТВО</span><span class="sxs-lookup"><span data-stu-id="51ea7-195">свидетелство за управление на моторно превозно средство</span></span>  <br/> <span data-ttu-id="51ea7-196">СУМПС</span><span class="sxs-lookup"><span data-stu-id="51ea7-196">сумпс</span></span>  <br/> <span data-ttu-id="51ea7-197">ШОФЬОРСКА КНИЖКА</span><span class="sxs-lookup"><span data-stu-id="51ea7-197">шофьорска книжка</span></span>  <br/> |
   
## <a name="croatia"></a><span data-ttu-id="51ea7-198">Croazia</span><span class="sxs-lookup"><span data-stu-id="51ea7-198">Croatia</span></span>

### <a name="format"></a><span data-ttu-id="51ea7-199">Formato</span><span class="sxs-lookup"><span data-stu-id="51ea7-199">Format</span></span>

<span data-ttu-id="51ea7-200">Otto cifre senza spazi e i delimitatori</span><span class="sxs-lookup"><span data-stu-id="51ea7-200">Eight digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="51ea7-201">Modello</span><span class="sxs-lookup"><span data-stu-id="51ea7-201">Pattern</span></span>

<span data-ttu-id="51ea7-202">Otto cifre</span><span class="sxs-lookup"><span data-stu-id="51ea7-202">Eight digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="51ea7-203">Checksum</span><span class="sxs-lookup"><span data-stu-id="51ea7-203">Checksum</span></span>

<span data-ttu-id="51ea7-204">No</span><span class="sxs-lookup"><span data-stu-id="51ea7-204">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="51ea7-205">Definizione</span><span class="sxs-lookup"><span data-stu-id="51ea7-205">Definition</span></span>

<span data-ttu-id="51ea7-206">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="51ea7-206">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="51ea7-207">L'espressione regolare `Regex_croatia_eu_driver's_license_number` consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="51ea7-207">The regular expression  `Regex_croatia_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="51ea7-208">Una parola chiave da `Keywords_croatia_eu_driver's_license_number` viene trovato.</span><span class="sxs-lookup"><span data-stu-id="51ea7-208">A keyword from  `Keywords_croatia_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_croatia_eu_driver's_license_number" />
          <Match idRef="Keywords_croatia_eu_driver's_license_number" />
        </Pattern>
</Entity>

```

### <a name="keywords"></a><span data-ttu-id="51ea7-209">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="51ea7-209">Keywords</span></span>

<span data-ttu-id="51ea7-210">| |</span><span class="sxs-lookup"><span data-stu-id="51ea7-210"></span></span>
|<span data-ttu-id="51ea7-211">**Keywords_croatia_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="51ea7-211">**Keywords_croatia_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="51ea7-212">DL #</span><span class="sxs-lookup"><span data-stu-id="51ea7-212">dl#</span></span>  <br/> <span data-ttu-id="51ea7-213">patente</span><span class="sxs-lookup"><span data-stu-id="51ea7-213">driver license</span></span>  <br/> <span data-ttu-id="51ea7-214">Numero patente di Guida</span><span class="sxs-lookup"><span data-stu-id="51ea7-214">driver license number</span></span>  <br/> <span data-ttu-id="51ea7-215">titolo driver</span><span class="sxs-lookup"><span data-stu-id="51ea7-215">driver licence</span></span>  <br/> <span data-ttu-id="51ea7-216">driver lic.</span><span class="sxs-lookup"><span data-stu-id="51ea7-216">drivers lic.</span></span>  <br/> <span data-ttu-id="51ea7-217">patente di Guida</span><span class="sxs-lookup"><span data-stu-id="51ea7-217">drivers license</span></span>  <br/> <span data-ttu-id="51ea7-218">drivers licence</span><span class="sxs-lookup"><span data-stu-id="51ea7-218">drivers licence</span></span>  <br/> <span data-ttu-id="51ea7-219">patente</span><span class="sxs-lookup"><span data-stu-id="51ea7-219">driver's license</span></span>  <br/> <span data-ttu-id="51ea7-220">numero della patente di Guida</span><span class="sxs-lookup"><span data-stu-id="51ea7-220">driver's license number</span></span>  <br/> <span data-ttu-id="51ea7-221">numero della patente di Guida</span><span class="sxs-lookup"><span data-stu-id="51ea7-221">driver's licence number</span></span>  <br/> <span data-ttu-id="51ea7-222">che influisce sul numero di licenza</span><span class="sxs-lookup"><span data-stu-id="51ea7-222">driving license number</span></span>  <br/> <span data-ttu-id="51ea7-223">dlno #</span><span class="sxs-lookup"><span data-stu-id="51ea7-223">dlno#</span></span>  <br/> <span data-ttu-id="51ea7-224">vozačka dozvola</span><span class="sxs-lookup"><span data-stu-id="51ea7-224">vozačka dozvola</span></span>  <br/> |
   
## <a name="cyprus"></a><span data-ttu-id="51ea7-225">Cipro</span><span class="sxs-lookup"><span data-stu-id="51ea7-225">Cyprus</span></span>

### <a name="format"></a><span data-ttu-id="51ea7-226">Formato</span><span class="sxs-lookup"><span data-stu-id="51ea7-226">Format</span></span>

<span data-ttu-id="51ea7-227">12 cifre senza spazi e i delimitatori</span><span class="sxs-lookup"><span data-stu-id="51ea7-227">12 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="51ea7-228">Modello</span><span class="sxs-lookup"><span data-stu-id="51ea7-228">Pattern</span></span>

<span data-ttu-id="51ea7-229">12 cifre</span><span class="sxs-lookup"><span data-stu-id="51ea7-229">12 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="51ea7-230">Checksum</span><span class="sxs-lookup"><span data-stu-id="51ea7-230">Checksum</span></span>

<span data-ttu-id="51ea7-231">No</span><span class="sxs-lookup"><span data-stu-id="51ea7-231">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="51ea7-232">Definizione</span><span class="sxs-lookup"><span data-stu-id="51ea7-232">Definition</span></span>

<span data-ttu-id="51ea7-233">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="51ea7-233">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="51ea7-234">L'espressione regolare `Regex_cyprus_eu_driver's_license_number` consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="51ea7-234">The regular expression  `Regex_cyprus_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="51ea7-235">Una parola chiave da `Keywords_cyprus_eu_driver's_license_number` viene trovato.</span><span class="sxs-lookup"><span data-stu-id="51ea7-235">A keyword from  `Keywords_cyprus_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_cyprus_eu_driver's_license_number" />
          <Match idRef="Keywords_cyprus_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="51ea7-236">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="51ea7-236">Keywords</span></span>

<span data-ttu-id="51ea7-237">| |</span><span class="sxs-lookup"><span data-stu-id="51ea7-237"></span></span>
|<span data-ttu-id="51ea7-238">**Keywords_cyprus_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="51ea7-238">**Keywords_cyprus_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="51ea7-239">DL #</span><span class="sxs-lookup"><span data-stu-id="51ea7-239">dl#</span></span>  <br/> <span data-ttu-id="51ea7-240">patente</span><span class="sxs-lookup"><span data-stu-id="51ea7-240">driver license</span></span>  <br/> <span data-ttu-id="51ea7-241">Numero patente di Guida</span><span class="sxs-lookup"><span data-stu-id="51ea7-241">driver license number</span></span>  <br/> <span data-ttu-id="51ea7-242">titolo driver</span><span class="sxs-lookup"><span data-stu-id="51ea7-242">driver licence</span></span>  <br/> <span data-ttu-id="51ea7-243">driver lic.</span><span class="sxs-lookup"><span data-stu-id="51ea7-243">drivers lic.</span></span>  <br/> <span data-ttu-id="51ea7-244">patente di Guida</span><span class="sxs-lookup"><span data-stu-id="51ea7-244">drivers license</span></span>  <br/> <span data-ttu-id="51ea7-245">drivers licence</span><span class="sxs-lookup"><span data-stu-id="51ea7-245">drivers licence</span></span>  <br/> <span data-ttu-id="51ea7-246">numero della patente di Guida</span><span class="sxs-lookup"><span data-stu-id="51ea7-246">driver's license number</span></span>  <br/> <span data-ttu-id="51ea7-247">numero della patente di Guida</span><span class="sxs-lookup"><span data-stu-id="51ea7-247">driver's licence number</span></span>  <br/> <span data-ttu-id="51ea7-248">che influisce sul numero di licenza</span><span class="sxs-lookup"><span data-stu-id="51ea7-248">driving license number</span></span>  <br/> <span data-ttu-id="51ea7-249">dlno #</span><span class="sxs-lookup"><span data-stu-id="51ea7-249">dlno#</span></span>  <br/> <span data-ttu-id="51ea7-250">ΆΔΕΙΑ ΟΔΉΓΗΣΗΣ</span><span class="sxs-lookup"><span data-stu-id="51ea7-250">άδεια οδήγησης</span></span>  <br/> |
   
## <a name="czech-republic"></a><span data-ttu-id="51ea7-251">Repubblica Ceca</span><span class="sxs-lookup"><span data-stu-id="51ea7-251">Czech Republic</span></span>

### <a name="format"></a><span data-ttu-id="51ea7-252">Formato</span><span class="sxs-lookup"><span data-stu-id="51ea7-252">Format</span></span>

<span data-ttu-id="51ea7-253">Due lettere seguite da sei cifre</span><span class="sxs-lookup"><span data-stu-id="51ea7-253">Two letters followed by six digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="51ea7-254">Modello</span><span class="sxs-lookup"><span data-stu-id="51ea7-254">Pattern</span></span>

<span data-ttu-id="51ea7-255">Otto lettere e cifre:</span><span class="sxs-lookup"><span data-stu-id="51ea7-255">Eight letters and digits:</span></span>
  
- <span data-ttu-id="51ea7-256">Due lettere (maiuscole o minuscole)</span><span class="sxs-lookup"><span data-stu-id="51ea7-256">Two letters (not case-sensitive)</span></span>
    
- <span data-ttu-id="51ea7-257">Uno spazio (facoltativo)</span><span class="sxs-lookup"><span data-stu-id="51ea7-257">A space (optional)</span></span>
    
- <span data-ttu-id="51ea7-258">Sei cifre</span><span class="sxs-lookup"><span data-stu-id="51ea7-258">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="51ea7-259">Checksum</span><span class="sxs-lookup"><span data-stu-id="51ea7-259">Checksum</span></span>

<span data-ttu-id="51ea7-260">No</span><span class="sxs-lookup"><span data-stu-id="51ea7-260">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="51ea7-261">Definizione</span><span class="sxs-lookup"><span data-stu-id="51ea7-261">Definition</span></span>

<span data-ttu-id="51ea7-262">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="51ea7-262">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="51ea7-263">L'espressione regolare `Regex_czech_republic_eu_driver's_license_number` consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="51ea7-263">The regular expression  `Regex_czech_republic_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="51ea7-264">Una parola chiave da `Keywords_czech_republic_eu_driver's_license_number` viene trovato.</span><span class="sxs-lookup"><span data-stu-id="51ea7-264">A keyword from  `Keywords_czech_republic_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_czech_republic_eu_driver's_license_number" />
          <Match idRef="Keywords_czech_republic_eu_driver's_license_number" />
        </Pattern>
</Entity>

```

### <a name="keywords"></a><span data-ttu-id="51ea7-265">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="51ea7-265">Keywords</span></span>

<span data-ttu-id="51ea7-266">| |</span><span class="sxs-lookup"><span data-stu-id="51ea7-266"></span></span>
|<span data-ttu-id="51ea7-267">**Keywords_czech_republic_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="51ea7-267">**Keywords_czech_republic_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="51ea7-268">DL #</span><span class="sxs-lookup"><span data-stu-id="51ea7-268">dl#</span></span>  <br/> <span data-ttu-id="51ea7-269">patente</span><span class="sxs-lookup"><span data-stu-id="51ea7-269">driver license</span></span>  <br/> <span data-ttu-id="51ea7-270">Numero patente di Guida</span><span class="sxs-lookup"><span data-stu-id="51ea7-270">driver license number</span></span>  <br/> <span data-ttu-id="51ea7-271">titolo driver</span><span class="sxs-lookup"><span data-stu-id="51ea7-271">driver licence</span></span>  <br/> <span data-ttu-id="51ea7-272">driver lic.</span><span class="sxs-lookup"><span data-stu-id="51ea7-272">drivers lic.</span></span>  <br/> <span data-ttu-id="51ea7-273">patente di Guida</span><span class="sxs-lookup"><span data-stu-id="51ea7-273">drivers license</span></span>  <br/> <span data-ttu-id="51ea7-274">drivers licence</span><span class="sxs-lookup"><span data-stu-id="51ea7-274">drivers licence</span></span>  <br/> <span data-ttu-id="51ea7-275">patente</span><span class="sxs-lookup"><span data-stu-id="51ea7-275">driver's license</span></span>  <br/> <span data-ttu-id="51ea7-276">numero della patente di Guida</span><span class="sxs-lookup"><span data-stu-id="51ea7-276">driver's license number</span></span>  <br/> <span data-ttu-id="51ea7-277">numero della patente di Guida</span><span class="sxs-lookup"><span data-stu-id="51ea7-277">driver's license number</span></span>  <br/> <span data-ttu-id="51ea7-278">numero della patente di Guida</span><span class="sxs-lookup"><span data-stu-id="51ea7-278">driver's licence number</span></span>  <br/> <span data-ttu-id="51ea7-279">che influisce sul numero di licenza</span><span class="sxs-lookup"><span data-stu-id="51ea7-279">driving license number</span></span>  <br/> <span data-ttu-id="51ea7-280">dlno #</span><span class="sxs-lookup"><span data-stu-id="51ea7-280">dlno#</span></span>  <br/> <span data-ttu-id="51ea7-281">Řidičský prúkaz</span><span class="sxs-lookup"><span data-stu-id="51ea7-281">řidičský prúkaz</span></span>  <br/> |
   
## <a name="denmark"></a><span data-ttu-id="51ea7-282">Danimarca</span><span class="sxs-lookup"><span data-stu-id="51ea7-282">Denmark</span></span>

### <a name="format"></a><span data-ttu-id="51ea7-283">Formato</span><span class="sxs-lookup"><span data-stu-id="51ea7-283">Format</span></span>

<span data-ttu-id="51ea7-284">Otto cifre senza spazi e i delimitatori</span><span class="sxs-lookup"><span data-stu-id="51ea7-284">Eight digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="51ea7-285">Modello</span><span class="sxs-lookup"><span data-stu-id="51ea7-285">Pattern</span></span>

<span data-ttu-id="51ea7-286">Otto cifre</span><span class="sxs-lookup"><span data-stu-id="51ea7-286">Eight digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="51ea7-287">Checksum</span><span class="sxs-lookup"><span data-stu-id="51ea7-287">Checksum</span></span>

<span data-ttu-id="51ea7-288">Sì</span><span class="sxs-lookup"><span data-stu-id="51ea7-288">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="51ea7-289">Definizione</span><span class="sxs-lookup"><span data-stu-id="51ea7-289">Definition</span></span>

<span data-ttu-id="51ea7-290">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="51ea7-290">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="51ea7-291">L'espressione regolare `Regex_denmark_eu_driver's_license_number` consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="51ea7-291">The regular expression  `Regex_denmark_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="51ea7-292">Una parola chiave da `Keywords_denmark_eu_driver's_license_number` viene trovato.</span><span class="sxs-lookup"><span data-stu-id="51ea7-292">A keyword from  `Keywords_denmark_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_denmark_eu_driver's_license_number" />
          <Match idRef="Keywords_denmark_eu_driver's_license_number" />
        </Pattern>
</Entity>

```

### <a name="keywords"></a><span data-ttu-id="51ea7-293">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="51ea7-293">Keywords</span></span>

<span data-ttu-id="51ea7-294">| |</span><span class="sxs-lookup"><span data-stu-id="51ea7-294"></span></span>
|<span data-ttu-id="51ea7-295">**Keywords_denmark_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="51ea7-295">**Keywords_denmark_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="51ea7-296">DL #</span><span class="sxs-lookup"><span data-stu-id="51ea7-296">dl#</span></span>  <br/> <span data-ttu-id="51ea7-297">patente</span><span class="sxs-lookup"><span data-stu-id="51ea7-297">driver license</span></span>  <br/> <span data-ttu-id="51ea7-298">Numero patente di Guida</span><span class="sxs-lookup"><span data-stu-id="51ea7-298">driver license number</span></span>  <br/> <span data-ttu-id="51ea7-299">titolo driver</span><span class="sxs-lookup"><span data-stu-id="51ea7-299">driver licence</span></span>  <br/> <span data-ttu-id="51ea7-300">driver lic.</span><span class="sxs-lookup"><span data-stu-id="51ea7-300">drivers lic.</span></span>  <br/> <span data-ttu-id="51ea7-301">patente di Guida</span><span class="sxs-lookup"><span data-stu-id="51ea7-301">drivers license</span></span>  <br/> <span data-ttu-id="51ea7-302">drivers licence</span><span class="sxs-lookup"><span data-stu-id="51ea7-302">drivers licence</span></span>  <br/> <span data-ttu-id="51ea7-303">patente</span><span class="sxs-lookup"><span data-stu-id="51ea7-303">driver's license</span></span>  <br/> <span data-ttu-id="51ea7-304">numero della patente di Guida</span><span class="sxs-lookup"><span data-stu-id="51ea7-304">driver's license number</span></span>  <br/> <span data-ttu-id="51ea7-305">numero della patente di Guida</span><span class="sxs-lookup"><span data-stu-id="51ea7-305">driver's licence number</span></span>  <br/> <span data-ttu-id="51ea7-306">che influisce sul numero di licenza</span><span class="sxs-lookup"><span data-stu-id="51ea7-306">driving license number</span></span>  <br/> <span data-ttu-id="51ea7-307">dlno #</span><span class="sxs-lookup"><span data-stu-id="51ea7-307">dlno#</span></span>  <br/> <span data-ttu-id="51ea7-308">kørekort</span><span class="sxs-lookup"><span data-stu-id="51ea7-308">kørekort</span></span>  <br/> <span data-ttu-id="51ea7-309">kørekortnummer</span><span class="sxs-lookup"><span data-stu-id="51ea7-309">kørekortnummer</span></span>  <br/> |
   
## <a name="estonia"></a><span data-ttu-id="51ea7-310">Estonia</span><span class="sxs-lookup"><span data-stu-id="51ea7-310">Estonia</span></span>

### <a name="format"></a><span data-ttu-id="51ea7-311">Formato</span><span class="sxs-lookup"><span data-stu-id="51ea7-311">Format</span></span>

<span data-ttu-id="51ea7-312">Due lettere seguite da sei cifre</span><span class="sxs-lookup"><span data-stu-id="51ea7-312">Two letters followed by six digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="51ea7-313">Modello</span><span class="sxs-lookup"><span data-stu-id="51ea7-313">Pattern</span></span>

<span data-ttu-id="51ea7-314">Due lettere e sei cifre:</span><span class="sxs-lookup"><span data-stu-id="51ea7-314">Two letters and six digits:</span></span>
  
-  <span data-ttu-id="51ea7-315">Le lettere "ET" (maiuscole o minuscole)</span><span class="sxs-lookup"><span data-stu-id="51ea7-315">The letters "ET" (not case-sensitive)</span></span> 
    
- <span data-ttu-id="51ea7-316">Sei cifre</span><span class="sxs-lookup"><span data-stu-id="51ea7-316">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="51ea7-317">Checksum</span><span class="sxs-lookup"><span data-stu-id="51ea7-317">Checksum</span></span>

<span data-ttu-id="51ea7-318">No</span><span class="sxs-lookup"><span data-stu-id="51ea7-318">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="51ea7-319">Definizione</span><span class="sxs-lookup"><span data-stu-id="51ea7-319">Definition</span></span>

<span data-ttu-id="51ea7-320">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="51ea7-320">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="51ea7-321">L'espressione regolare `Regex_estonia_eu_driver's_license_number` consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="51ea7-321">The regular expression  `Regex_estonia_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="51ea7-322">Una parola chiave da `Keywords_estonia_eu_driver's_license_number` viene trovato.</span><span class="sxs-lookup"><span data-stu-id="51ea7-322">A keyword from  `Keywords_estonia_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_estonia_eu_driver's_license_number" />
          <Match idRef="Keywords_estonia_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="51ea7-323">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="51ea7-323">Keywords</span></span>

<span data-ttu-id="51ea7-324">| |</span><span class="sxs-lookup"><span data-stu-id="51ea7-324"></span></span>
|<span data-ttu-id="51ea7-325">**Keywords_estonia_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="51ea7-325">**Keywords_estonia_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="51ea7-326">DL #</span><span class="sxs-lookup"><span data-stu-id="51ea7-326">dl#</span></span>  <br/> <span data-ttu-id="51ea7-327">patente</span><span class="sxs-lookup"><span data-stu-id="51ea7-327">driver license</span></span>  <br/> <span data-ttu-id="51ea7-328">Numero patente di Guida</span><span class="sxs-lookup"><span data-stu-id="51ea7-328">driver license number</span></span>  <br/> <span data-ttu-id="51ea7-329">Numero patente di Guida</span><span class="sxs-lookup"><span data-stu-id="51ea7-329">driver license number</span></span>  <br/> <span data-ttu-id="51ea7-330">titolo driver</span><span class="sxs-lookup"><span data-stu-id="51ea7-330">driver licence</span></span>  <br/> <span data-ttu-id="51ea7-331">driver lic.</span><span class="sxs-lookup"><span data-stu-id="51ea7-331">drivers lic.</span></span>  <br/> <span data-ttu-id="51ea7-332">patente di Guida</span><span class="sxs-lookup"><span data-stu-id="51ea7-332">drivers license</span></span>  <br/> <span data-ttu-id="51ea7-333">drivers licence</span><span class="sxs-lookup"><span data-stu-id="51ea7-333">drivers licence</span></span>  <br/> <span data-ttu-id="51ea7-334">patente</span><span class="sxs-lookup"><span data-stu-id="51ea7-334">driver's license</span></span>  <br/> <span data-ttu-id="51ea7-335">numero della patente di Guida</span><span class="sxs-lookup"><span data-stu-id="51ea7-335">driver's license number</span></span>  <br/> <span data-ttu-id="51ea7-336">che influisce sul numero di licenza</span><span class="sxs-lookup"><span data-stu-id="51ea7-336">driving license number</span></span>  <br/> <span data-ttu-id="51ea7-337">dlno #</span><span class="sxs-lookup"><span data-stu-id="51ea7-337">dlno#</span></span>  <br/> <span data-ttu-id="51ea7-338">
permis de conduire</span><span class="sxs-lookup"><span data-stu-id="51ea7-338">permis de conduire</span></span>  <br/> |
   
## <a name="finland"></a><span data-ttu-id="51ea7-339">Finlandia</span><span class="sxs-lookup"><span data-stu-id="51ea7-339">Finland</span></span>

### <a name="format"></a><span data-ttu-id="51ea7-340">Formato</span><span class="sxs-lookup"><span data-stu-id="51ea7-340">Format</span></span>

<span data-ttu-id="51ea7-341">10 cifre contenenti una lineetta</span><span class="sxs-lookup"><span data-stu-id="51ea7-341">10 digits containing a hyphen</span></span>
  
### <a name="pattern"></a><span data-ttu-id="51ea7-342">Modello</span><span class="sxs-lookup"><span data-stu-id="51ea7-342">Pattern</span></span>

<span data-ttu-id="51ea7-343">10 cifre che contiene un segno meno:</span><span class="sxs-lookup"><span data-stu-id="51ea7-343">10 digits containing a hyphen:</span></span>
  
-  <span data-ttu-id="51ea7-344">Sei cifre</span><span class="sxs-lookup"><span data-stu-id="51ea7-344">Six digits</span></span> 
    
- <span data-ttu-id="51ea7-345">Una lineetta</span><span class="sxs-lookup"><span data-stu-id="51ea7-345">A hyphen</span></span>
    
-  <span data-ttu-id="51ea7-346">Quattro cifre</span><span class="sxs-lookup"><span data-stu-id="51ea7-346">Four digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="51ea7-347">Checksum</span><span class="sxs-lookup"><span data-stu-id="51ea7-347">Checksum</span></span>

<span data-ttu-id="51ea7-348">No</span><span class="sxs-lookup"><span data-stu-id="51ea7-348">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="51ea7-349">Definizione</span><span class="sxs-lookup"><span data-stu-id="51ea7-349">Definition</span></span>

<span data-ttu-id="51ea7-350">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="51ea7-350">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="51ea7-351">L'espressione regolare `Regex_finland_eu_driver's_license_number` consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="51ea7-351">The regular expression  `Regex_finland_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="51ea7-352">Una parola chiave da `Keywords_finland_eu_driver's_license_number` viene trovato.</span><span class="sxs-lookup"><span data-stu-id="51ea7-352">A keyword from  `Keywords_finland_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_finland_eu_driver's_license_number" />
          <Match idRef="Keywords_finland_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="51ea7-353">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="51ea7-353">Keywords</span></span>

<span data-ttu-id="51ea7-354">| |</span><span class="sxs-lookup"><span data-stu-id="51ea7-354"></span></span>
|<span data-ttu-id="51ea7-355">**Keywords_finland_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="51ea7-355">**Keywords_finland_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="51ea7-356">DL #</span><span class="sxs-lookup"><span data-stu-id="51ea7-356">dl#</span></span>  <br/> <span data-ttu-id="51ea7-357">patente</span><span class="sxs-lookup"><span data-stu-id="51ea7-357">driver license</span></span>  <br/> <span data-ttu-id="51ea7-358">Numero patente di Guida</span><span class="sxs-lookup"><span data-stu-id="51ea7-358">driver license number</span></span>  <br/> <span data-ttu-id="51ea7-359">titolo driver</span><span class="sxs-lookup"><span data-stu-id="51ea7-359">driver licence</span></span>  <br/> <span data-ttu-id="51ea7-360">driver lic.</span><span class="sxs-lookup"><span data-stu-id="51ea7-360">drivers lic.</span></span>  <br/> <span data-ttu-id="51ea7-361">patente di Guida</span><span class="sxs-lookup"><span data-stu-id="51ea7-361">drivers license</span></span>  <br/> <span data-ttu-id="51ea7-362">drivers licence</span><span class="sxs-lookup"><span data-stu-id="51ea7-362">drivers licence</span></span>  <br/> <span data-ttu-id="51ea7-363">patente</span><span class="sxs-lookup"><span data-stu-id="51ea7-363">driver's license</span></span>  <br/> <span data-ttu-id="51ea7-364">numero della patente di Guida</span><span class="sxs-lookup"><span data-stu-id="51ea7-364">driver's license number</span></span>  <br/> <span data-ttu-id="51ea7-365">numero della patente di Guida</span><span class="sxs-lookup"><span data-stu-id="51ea7-365">driver's licence number</span></span>  <br/> <span data-ttu-id="51ea7-366">che influisce sul numero di licenza</span><span class="sxs-lookup"><span data-stu-id="51ea7-366">driving license number</span></span>  <br/> <span data-ttu-id="51ea7-367">dlno #</span><span class="sxs-lookup"><span data-stu-id="51ea7-367">dlno#</span></span>  <br/> <span data-ttu-id="51ea7-368">ajokortti</span><span class="sxs-lookup"><span data-stu-id="51ea7-368">ajokortti</span></span>  <br/> |
   
## <a name="france"></a><span data-ttu-id="51ea7-369">Francia</span><span class="sxs-lookup"><span data-stu-id="51ea7-369">France</span></span>

<span data-ttu-id="51ea7-370">Per ulteriori informazioni, vedere la sezione "Numero della patente di Guida di Francia" in [cercare il quali i tipi di informazioni riservate](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="51ea7-370">For details, see the section "France Driver's License Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="germany"></a><span data-ttu-id="51ea7-371">Germania</span><span class="sxs-lookup"><span data-stu-id="51ea7-371">Germany</span></span>

<span data-ttu-id="51ea7-372">Per ulteriori informazioni, vedere la sezione "Numero della patente di Guida tedesca" in [cercare il quali i tipi di informazioni riservate](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="51ea7-372">For details, see the section "German Driver's License Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="greece"></a><span data-ttu-id="51ea7-373">Grecia</span><span class="sxs-lookup"><span data-stu-id="51ea7-373">Greece</span></span>

### <a name="format"></a><span data-ttu-id="51ea7-374">Formato</span><span class="sxs-lookup"><span data-stu-id="51ea7-374">Format</span></span>

<span data-ttu-id="51ea7-375">Nove cifre senza spazi e i delimitatori</span><span class="sxs-lookup"><span data-stu-id="51ea7-375">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="51ea7-376">Modello</span><span class="sxs-lookup"><span data-stu-id="51ea7-376">Pattern</span></span>

 <span data-ttu-id="51ea7-377">9 cifre</span><span class="sxs-lookup"><span data-stu-id="51ea7-377">Nine digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="51ea7-378">Checksum</span><span class="sxs-lookup"><span data-stu-id="51ea7-378">Checksum</span></span>

<span data-ttu-id="51ea7-379">No</span><span class="sxs-lookup"><span data-stu-id="51ea7-379">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="51ea7-380">Definizione</span><span class="sxs-lookup"><span data-stu-id="51ea7-380">Definition</span></span>

<span data-ttu-id="51ea7-381">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="51ea7-381">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="51ea7-382">L'espressione regolare `Regex_greece_eu_driver's_license_number` consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="51ea7-382">The regular expression  `Regex_greece_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="51ea7-383">Una parola chiave da `Keywords_greece_eu_driver's_license_number` viene trovato.</span><span class="sxs-lookup"><span data-stu-id="51ea7-383">A keyword from  `Keywords_greece_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_greece_eu_driver's_license_number" />
          <Match idRef="Keywords_greece_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="51ea7-384">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="51ea7-384">Keywords</span></span>

<span data-ttu-id="51ea7-385">| |</span><span class="sxs-lookup"><span data-stu-id="51ea7-385"></span></span>
|<span data-ttu-id="51ea7-386">**Keywords_greece_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="51ea7-386">**Keywords_greece_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="51ea7-387">dlL #</span><span class="sxs-lookup"><span data-stu-id="51ea7-387">dlL#</span></span>  <br/> <span data-ttu-id="51ea7-388">patente</span><span class="sxs-lookup"><span data-stu-id="51ea7-388">driver license</span></span>  <br/> <span data-ttu-id="51ea7-389">Numero patente di Guida</span><span class="sxs-lookup"><span data-stu-id="51ea7-389">driver license number</span></span>  <br/> <span data-ttu-id="51ea7-390">titolo driver</span><span class="sxs-lookup"><span data-stu-id="51ea7-390">driver licence</span></span>  <br/> <span data-ttu-id="51ea7-391">driver lic.</span><span class="sxs-lookup"><span data-stu-id="51ea7-391">drivers lic.</span></span>  <br/> <span data-ttu-id="51ea7-392">patente di Guida</span><span class="sxs-lookup"><span data-stu-id="51ea7-392">drivers license</span></span>  <br/> <span data-ttu-id="51ea7-393">drivers licence</span><span class="sxs-lookup"><span data-stu-id="51ea7-393">drivers licence</span></span>  <br/> <span data-ttu-id="51ea7-394">patente</span><span class="sxs-lookup"><span data-stu-id="51ea7-394">driver's license</span></span>  <br/> <span data-ttu-id="51ea7-395">numero della patente di Guida</span><span class="sxs-lookup"><span data-stu-id="51ea7-395">driver's license number</span></span>  <br/> <span data-ttu-id="51ea7-396">numero della patente di Guida</span><span class="sxs-lookup"><span data-stu-id="51ea7-396">driver's licence number</span></span>  <br/> <span data-ttu-id="51ea7-397">che influisce sul numero di licenza</span><span class="sxs-lookup"><span data-stu-id="51ea7-397">driving license number</span></span>  <br/> <span data-ttu-id="51ea7-398">dlno #</span><span class="sxs-lookup"><span data-stu-id="51ea7-398">dlno#</span></span>  <br/> <span data-ttu-id="51ea7-399">ΔΕΙΑ ΟΔΉΓΗΣΗΣ</span><span class="sxs-lookup"><span data-stu-id="51ea7-399">δεια οδήγησης</span></span>  <br/> <span data-ttu-id="51ea7-400">Adeia odigisis</span><span class="sxs-lookup"><span data-stu-id="51ea7-400">Adeia odigisis</span></span>  <br/> |
   
## <a name="hungary"></a><span data-ttu-id="51ea7-401">Ungheria</span><span class="sxs-lookup"><span data-stu-id="51ea7-401">Hungary</span></span>

### <a name="format"></a><span data-ttu-id="51ea7-402">Formato</span><span class="sxs-lookup"><span data-stu-id="51ea7-402">Format</span></span>

<span data-ttu-id="51ea7-403">Due lettere seguite da sei cifre</span><span class="sxs-lookup"><span data-stu-id="51ea7-403">Two letters followed by six digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="51ea7-404">Modello</span><span class="sxs-lookup"><span data-stu-id="51ea7-404">Pattern</span></span>

<span data-ttu-id="51ea7-405">Due lettere e sei cifre:</span><span class="sxs-lookup"><span data-stu-id="51ea7-405">Two letters and six digits:</span></span>
  
-  <span data-ttu-id="51ea7-406">Due lettere (maiuscole o minuscole)</span><span class="sxs-lookup"><span data-stu-id="51ea7-406">Two letters (not case-sensitive)</span></span> 
    
- <span data-ttu-id="51ea7-407">Sei cifre</span><span class="sxs-lookup"><span data-stu-id="51ea7-407">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="51ea7-408">Checksum</span><span class="sxs-lookup"><span data-stu-id="51ea7-408">Checksum</span></span>

<span data-ttu-id="51ea7-409">No</span><span class="sxs-lookup"><span data-stu-id="51ea7-409">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="51ea7-410">Definizione</span><span class="sxs-lookup"><span data-stu-id="51ea7-410">Definition</span></span>

<span data-ttu-id="51ea7-411">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="51ea7-411">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="51ea7-412">L'espressione regolare `Regex_hungary_eu_driver's_license_number` consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="51ea7-412">The regular expression  `Regex_hungary_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="51ea7-413">Una parola chiave da `Keywords_hungary_eu_driver's_license_number` viene trovato.</span><span class="sxs-lookup"><span data-stu-id="51ea7-413">A keyword from  `Keywords_hungary_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_hungary_eu_driver's_license_number" />
          <Match idRef="Keywords_hungary_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="51ea7-414">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="51ea7-414">Keywords</span></span>

<span data-ttu-id="51ea7-415">| |</span><span class="sxs-lookup"><span data-stu-id="51ea7-415"></span></span>
|<span data-ttu-id="51ea7-416">**Keywords_hungary_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="51ea7-416">**Keywords_hungary_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="51ea7-417">DL #</span><span class="sxs-lookup"><span data-stu-id="51ea7-417">dl#</span></span>  <br/> <span data-ttu-id="51ea7-418">patente</span><span class="sxs-lookup"><span data-stu-id="51ea7-418">driver license</span></span>  <br/> <span data-ttu-id="51ea7-419">Numero patente di Guida</span><span class="sxs-lookup"><span data-stu-id="51ea7-419">driver license number</span></span>  <br/> <span data-ttu-id="51ea7-420">titolo driver</span><span class="sxs-lookup"><span data-stu-id="51ea7-420">driver licence</span></span>  <br/> <span data-ttu-id="51ea7-421">driver lic.</span><span class="sxs-lookup"><span data-stu-id="51ea7-421">drivers lic.</span></span>  <br/> <span data-ttu-id="51ea7-422">patente di Guida</span><span class="sxs-lookup"><span data-stu-id="51ea7-422">drivers license</span></span>  <br/> <span data-ttu-id="51ea7-423">drivers licence</span><span class="sxs-lookup"><span data-stu-id="51ea7-423">drivers licence</span></span>  <br/> <span data-ttu-id="51ea7-424">patente</span><span class="sxs-lookup"><span data-stu-id="51ea7-424">driver's license</span></span>  <br/> <span data-ttu-id="51ea7-425">numero della patente di Guida</span><span class="sxs-lookup"><span data-stu-id="51ea7-425">driver's license number</span></span>  <br/> <span data-ttu-id="51ea7-426">numero della patente di Guida</span><span class="sxs-lookup"><span data-stu-id="51ea7-426">driver's licence number</span></span>  <br/> <span data-ttu-id="51ea7-427">che influisce sul numero di licenza</span><span class="sxs-lookup"><span data-stu-id="51ea7-427">driving license number</span></span>  <br/> <span data-ttu-id="51ea7-428">dlno #</span><span class="sxs-lookup"><span data-stu-id="51ea7-428">dlno#</span></span>  <br/> <span data-ttu-id="51ea7-429">vezetoi engedely</span><span class="sxs-lookup"><span data-stu-id="51ea7-429">vezetoi engedely</span></span>  <br/> |
   
## <a name="ireland"></a><span data-ttu-id="51ea7-430">Irlanda</span><span class="sxs-lookup"><span data-stu-id="51ea7-430">Ireland</span></span>

### <a name="format"></a><span data-ttu-id="51ea7-431">Formato</span><span class="sxs-lookup"><span data-stu-id="51ea7-431">Format</span></span>

<span data-ttu-id="51ea7-432">Sei cifre seguite da quattro lettere</span><span class="sxs-lookup"><span data-stu-id="51ea7-432">Six digits followed by four letters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="51ea7-433">Modello</span><span class="sxs-lookup"><span data-stu-id="51ea7-433">Pattern</span></span>

<span data-ttu-id="51ea7-434">Sei cifre e quattro lettere:</span><span class="sxs-lookup"><span data-stu-id="51ea7-434">Six digits and four letters:</span></span>
  
- <span data-ttu-id="51ea7-435">Sei cifre</span><span class="sxs-lookup"><span data-stu-id="51ea7-435">Six digits</span></span>
    
- <span data-ttu-id="51ea7-436">Quattro lettere (maiuscole o minuscole)</span><span class="sxs-lookup"><span data-stu-id="51ea7-436">Four letters (not case-sensitive)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="51ea7-437">Checksum</span><span class="sxs-lookup"><span data-stu-id="51ea7-437">Checksum</span></span>

<span data-ttu-id="51ea7-438">No</span><span class="sxs-lookup"><span data-stu-id="51ea7-438">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="51ea7-439">Definizione</span><span class="sxs-lookup"><span data-stu-id="51ea7-439">Definition</span></span>

<span data-ttu-id="51ea7-440">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="51ea7-440">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="51ea7-441">L'espressione regolare `Regex_ireland_eu_driver's_license_number` consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="51ea7-441">The regular expression  `Regex_ireland_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="51ea7-442">Una parola chiave da `Keywords_ireland_eu_driver's_license_number` viene trovato.</span><span class="sxs-lookup"><span data-stu-id="51ea7-442">A keyword from  `Keywords_ireland_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_ireland_eu_driver's_license_number" />
          <Match idRef="Keywords_ireland_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="51ea7-443">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="51ea7-443">Keywords</span></span>

<span data-ttu-id="51ea7-444">| |</span><span class="sxs-lookup"><span data-stu-id="51ea7-444"></span></span>
|<span data-ttu-id="51ea7-445">**Keywords_ireland_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="51ea7-445">**Keywords_ireland_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="51ea7-446">DL #</span><span class="sxs-lookup"><span data-stu-id="51ea7-446">dl#</span></span>  <br/> <span data-ttu-id="51ea7-447">patente</span><span class="sxs-lookup"><span data-stu-id="51ea7-447">driver license</span></span>  <br/> <span data-ttu-id="51ea7-448">Numero patente di Guida</span><span class="sxs-lookup"><span data-stu-id="51ea7-448">driver license number</span></span>  <br/> <span data-ttu-id="51ea7-449">titolo driver</span><span class="sxs-lookup"><span data-stu-id="51ea7-449">driver licence</span></span>  <br/> <span data-ttu-id="51ea7-450">driver lic.</span><span class="sxs-lookup"><span data-stu-id="51ea7-450">drivers lic.</span></span>  <br/> <span data-ttu-id="51ea7-451">patente di Guida</span><span class="sxs-lookup"><span data-stu-id="51ea7-451">drivers license</span></span>  <br/> <span data-ttu-id="51ea7-452">drivers licence</span><span class="sxs-lookup"><span data-stu-id="51ea7-452">drivers licence</span></span>  <br/> <span data-ttu-id="51ea7-453">patente</span><span class="sxs-lookup"><span data-stu-id="51ea7-453">driver's license</span></span>  <br/> <span data-ttu-id="51ea7-454">numero della patente di Guida</span><span class="sxs-lookup"><span data-stu-id="51ea7-454">driver's license number</span></span>  <br/> <span data-ttu-id="51ea7-455">numero della patente di Guida</span><span class="sxs-lookup"><span data-stu-id="51ea7-455">driver's licence number</span></span>  <br/> <span data-ttu-id="51ea7-456">che influisce sul numero di licenza</span><span class="sxs-lookup"><span data-stu-id="51ea7-456">driving license number</span></span>  <br/> <span data-ttu-id="51ea7-457">dlno #</span><span class="sxs-lookup"><span data-stu-id="51ea7-457">dlno#</span></span>  <br/> <span data-ttu-id="51ea7-458">ceadúnas tiomána</span><span class="sxs-lookup"><span data-stu-id="51ea7-458">ceadúnas tiomána</span></span>  <br/> |
   
## <a name="italy"></a><span data-ttu-id="51ea7-459">Italia</span><span class="sxs-lookup"><span data-stu-id="51ea7-459">Italy</span></span>

<span data-ttu-id="51ea7-460">Per ulteriori informazioni, vedere la sezione "Numero della patente di Guida di Italia" in [cercare il quali i tipi di informazioni riservate](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="51ea7-460">For details, see the section "Italy Driver's License Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="latvia"></a><span data-ttu-id="51ea7-461">Lettonia</span><span class="sxs-lookup"><span data-stu-id="51ea7-461">Latvia</span></span>

### <a name="format"></a><span data-ttu-id="51ea7-462">Formato</span><span class="sxs-lookup"><span data-stu-id="51ea7-462">Format</span></span>

<span data-ttu-id="51ea7-463">Tre lettere seguite da sei cifre</span><span class="sxs-lookup"><span data-stu-id="51ea7-463">Three letters followed by six digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="51ea7-464">Modello</span><span class="sxs-lookup"><span data-stu-id="51ea7-464">Pattern</span></span>

<span data-ttu-id="51ea7-465">Tre lettere e sei cifre:</span><span class="sxs-lookup"><span data-stu-id="51ea7-465">Three letters and six digits:</span></span>
  
-  <span data-ttu-id="51ea7-466">Tre lettere (maiuscole o minuscole)</span><span class="sxs-lookup"><span data-stu-id="51ea7-466">Three letters (not case-sensitive)</span></span> 
    
- <span data-ttu-id="51ea7-467">Sei cifre</span><span class="sxs-lookup"><span data-stu-id="51ea7-467">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="51ea7-468">Checksum</span><span class="sxs-lookup"><span data-stu-id="51ea7-468">Checksum</span></span>

<span data-ttu-id="51ea7-469">No</span><span class="sxs-lookup"><span data-stu-id="51ea7-469">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="51ea7-470">Definizione</span><span class="sxs-lookup"><span data-stu-id="51ea7-470">Definition</span></span>

<span data-ttu-id="51ea7-471">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="51ea7-471">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="51ea7-472">L'espressione regolare `Regex_latvia_eu_driver's_license_number` consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="51ea7-472">The regular expression  `Regex_latvia_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="51ea7-473">Una parola chiave da `Keywords_latvia_eu_driver's_license_number` viene trovato.</span><span class="sxs-lookup"><span data-stu-id="51ea7-473">A keyword from  `Keywords_latvia_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_latvia_eu_driver's_license_number" />
          <Match idRef="Keywords_latvia_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="51ea7-474">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="51ea7-474">Keywords</span></span>

<span data-ttu-id="51ea7-475">| |</span><span class="sxs-lookup"><span data-stu-id="51ea7-475"></span></span>
|<span data-ttu-id="51ea7-476">**Keywords_latvia_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="51ea7-476">**Keywords_latvia_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="51ea7-477">DL #</span><span class="sxs-lookup"><span data-stu-id="51ea7-477">dl#</span></span>  <br/> <span data-ttu-id="51ea7-478">patente</span><span class="sxs-lookup"><span data-stu-id="51ea7-478">driver license</span></span>  <br/> <span data-ttu-id="51ea7-479">Numero patente di Guida</span><span class="sxs-lookup"><span data-stu-id="51ea7-479">driver license number</span></span>  <br/> <span data-ttu-id="51ea7-480">titolo driver</span><span class="sxs-lookup"><span data-stu-id="51ea7-480">driver licence</span></span>  <br/> <span data-ttu-id="51ea7-481">driver lic.</span><span class="sxs-lookup"><span data-stu-id="51ea7-481">drivers lic.</span></span>  <br/> <span data-ttu-id="51ea7-482">patente di Guida</span><span class="sxs-lookup"><span data-stu-id="51ea7-482">drivers license</span></span>  <br/> <span data-ttu-id="51ea7-483">drivers licence</span><span class="sxs-lookup"><span data-stu-id="51ea7-483">drivers licence</span></span>  <br/> <span data-ttu-id="51ea7-484">patente</span><span class="sxs-lookup"><span data-stu-id="51ea7-484">driver's license</span></span>  <br/> <span data-ttu-id="51ea7-485">numero della patente di Guida</span><span class="sxs-lookup"><span data-stu-id="51ea7-485">driver's license number</span></span>  <br/> <span data-ttu-id="51ea7-486">numero della patente di Guida</span><span class="sxs-lookup"><span data-stu-id="51ea7-486">driver's licence number</span></span>  <br/> <span data-ttu-id="51ea7-487">che influisce sul numero di licenza</span><span class="sxs-lookup"><span data-stu-id="51ea7-487">driving license number</span></span>  <br/> <span data-ttu-id="51ea7-488">dlno #</span><span class="sxs-lookup"><span data-stu-id="51ea7-488">dlno#</span></span>  <br/> <span data-ttu-id="51ea7-489">autovadītāja apliecība</span><span class="sxs-lookup"><span data-stu-id="51ea7-489">autovadītāja apliecība</span></span>  <br/> |
   
## <a name="lithuania"></a><span data-ttu-id="51ea7-490">Lituania</span><span class="sxs-lookup"><span data-stu-id="51ea7-490">Lithuania</span></span>

### <a name="format"></a><span data-ttu-id="51ea7-491">Formato</span><span class="sxs-lookup"><span data-stu-id="51ea7-491">Format</span></span>

<span data-ttu-id="51ea7-492">Otto cifre senza spazi e i delimitatori</span><span class="sxs-lookup"><span data-stu-id="51ea7-492">Eight digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="51ea7-493">Modello</span><span class="sxs-lookup"><span data-stu-id="51ea7-493">Pattern</span></span>

 <span data-ttu-id="51ea7-494">Otto cifre</span><span class="sxs-lookup"><span data-stu-id="51ea7-494">Eight digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="51ea7-495">Checksum</span><span class="sxs-lookup"><span data-stu-id="51ea7-495">Checksum</span></span>

<span data-ttu-id="51ea7-496">No</span><span class="sxs-lookup"><span data-stu-id="51ea7-496">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="51ea7-497">Definizione</span><span class="sxs-lookup"><span data-stu-id="51ea7-497">Definition</span></span>

<span data-ttu-id="51ea7-498">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="51ea7-498">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="51ea7-499">L'espressione regolare `Regex_lithuania_eu_driver's_license_number` consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="51ea7-499">The regular expression  `Regex_lithuania_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="51ea7-500">Una parola chiave da `Keywords_lithuania_eu_driver's_license_number` viene trovato.</span><span class="sxs-lookup"><span data-stu-id="51ea7-500">A keyword from  `Keywords_lithuania_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_lithuania_eu_driver's_license_number" />
          <Match idRef="Keywords_lithuania_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="51ea7-501">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="51ea7-501">Keywords</span></span>

<span data-ttu-id="51ea7-502">| |</span><span class="sxs-lookup"><span data-stu-id="51ea7-502"></span></span>
|<span data-ttu-id="51ea7-503">**Keywords_lithuania_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="51ea7-503">**Keywords_lithuania_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="51ea7-504">DL #</span><span class="sxs-lookup"><span data-stu-id="51ea7-504">dl#</span></span>  <br/> <span data-ttu-id="51ea7-505">patente</span><span class="sxs-lookup"><span data-stu-id="51ea7-505">driver license</span></span>  <br/> <span data-ttu-id="51ea7-506">Numero patente di Guida</span><span class="sxs-lookup"><span data-stu-id="51ea7-506">driver license number</span></span>  <br/> <span data-ttu-id="51ea7-507">titolo driver</span><span class="sxs-lookup"><span data-stu-id="51ea7-507">driver licence</span></span>  <br/> <span data-ttu-id="51ea7-508">driver lic.</span><span class="sxs-lookup"><span data-stu-id="51ea7-508">drivers lic.</span></span>  <br/> <span data-ttu-id="51ea7-509">patente di Guida</span><span class="sxs-lookup"><span data-stu-id="51ea7-509">drivers license</span></span>  <br/> <span data-ttu-id="51ea7-510">drivers licence</span><span class="sxs-lookup"><span data-stu-id="51ea7-510">drivers licence</span></span>  <br/> <span data-ttu-id="51ea7-511">patente</span><span class="sxs-lookup"><span data-stu-id="51ea7-511">driver's license</span></span>  <br/> <span data-ttu-id="51ea7-512">numero della patente di Guida</span><span class="sxs-lookup"><span data-stu-id="51ea7-512">driver's license number</span></span>  <br/> <span data-ttu-id="51ea7-513">numero della patente di Guida</span><span class="sxs-lookup"><span data-stu-id="51ea7-513">driver's licence number</span></span>  <br/> <span data-ttu-id="51ea7-514">che influisce sul numero di licenza</span><span class="sxs-lookup"><span data-stu-id="51ea7-514">driving license number</span></span>  <br/> <span data-ttu-id="51ea7-515">dlno #</span><span class="sxs-lookup"><span data-stu-id="51ea7-515">dlno#</span></span>  <br/> <span data-ttu-id="51ea7-516">vairuotojo pažymėjimas</span><span class="sxs-lookup"><span data-stu-id="51ea7-516">vairuotojo pažymėjimas</span></span>  <br/> |
   
## <a name="luxemburg"></a><span data-ttu-id="51ea7-517">Lussemburgo</span><span class="sxs-lookup"><span data-stu-id="51ea7-517">Luxemburg</span></span>

### <a name="format"></a><span data-ttu-id="51ea7-518">Formato</span><span class="sxs-lookup"><span data-stu-id="51ea7-518">Format</span></span>

<span data-ttu-id="51ea7-519">Sei cifre senza spazi e i delimitatori</span><span class="sxs-lookup"><span data-stu-id="51ea7-519">Six digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="51ea7-520">Modello</span><span class="sxs-lookup"><span data-stu-id="51ea7-520">Pattern</span></span>

 <span data-ttu-id="51ea7-521">Sei cifre</span><span class="sxs-lookup"><span data-stu-id="51ea7-521">Six digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="51ea7-522">Checksum</span><span class="sxs-lookup"><span data-stu-id="51ea7-522">Checksum</span></span>

<span data-ttu-id="51ea7-523">No</span><span class="sxs-lookup"><span data-stu-id="51ea7-523">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="51ea7-524">Definizione</span><span class="sxs-lookup"><span data-stu-id="51ea7-524">Definition</span></span>

<span data-ttu-id="51ea7-525">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="51ea7-525">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="51ea7-526">L'espressione regolare `Regex_luxemburg_eu_driver's_license_number` consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="51ea7-526">The regular expression  `Regex_luxemburg_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="51ea7-527">Una parola chiave da `Keywords_luxemburg_eu_driver's_license_number` viene trovato.</span><span class="sxs-lookup"><span data-stu-id="51ea7-527">A keyword from  `Keywords_luxemburg_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_luxemburg_eu_driver's_license_number" />
          <Match idRef="Keywords_luxemburg_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="51ea7-528">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="51ea7-528">Keywords</span></span>

<span data-ttu-id="51ea7-529">| |</span><span class="sxs-lookup"><span data-stu-id="51ea7-529"></span></span>
|<span data-ttu-id="51ea7-530">**Keywords_luxemburg_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="51ea7-530">**Keywords_luxemburg_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="51ea7-531">DL #</span><span class="sxs-lookup"><span data-stu-id="51ea7-531">dl#</span></span>  <br/> <span data-ttu-id="51ea7-532">patente</span><span class="sxs-lookup"><span data-stu-id="51ea7-532">driver license</span></span>  <br/> <span data-ttu-id="51ea7-533">Numero patente di Guida</span><span class="sxs-lookup"><span data-stu-id="51ea7-533">driver license number</span></span>  <br/> <span data-ttu-id="51ea7-534">titolo driver</span><span class="sxs-lookup"><span data-stu-id="51ea7-534">driver licence</span></span>  <br/> <span data-ttu-id="51ea7-535">driver lic.</span><span class="sxs-lookup"><span data-stu-id="51ea7-535">drivers lic.</span></span>  <br/> <span data-ttu-id="51ea7-536">patente di Guida</span><span class="sxs-lookup"><span data-stu-id="51ea7-536">drivers license</span></span>  <br/> <span data-ttu-id="51ea7-537">drivers licence</span><span class="sxs-lookup"><span data-stu-id="51ea7-537">drivers licence</span></span>  <br/> <span data-ttu-id="51ea7-538">patente</span><span class="sxs-lookup"><span data-stu-id="51ea7-538">driver's license</span></span>  <br/> <span data-ttu-id="51ea7-539">numero della patente di Guida</span><span class="sxs-lookup"><span data-stu-id="51ea7-539">driver's license number</span></span>  <br/> <span data-ttu-id="51ea7-540">numero della patente di Guida</span><span class="sxs-lookup"><span data-stu-id="51ea7-540">driver's licence number</span></span>  <br/> <span data-ttu-id="51ea7-541">che influisce sul numero di licenza</span><span class="sxs-lookup"><span data-stu-id="51ea7-541">driving license number</span></span>  <br/> <span data-ttu-id="51ea7-542">dlno #</span><span class="sxs-lookup"><span data-stu-id="51ea7-542">dlno#</span></span>  <br/> <span data-ttu-id="51ea7-543">fahrerlaubnis</span><span class="sxs-lookup"><span data-stu-id="51ea7-543">fahrerlaubnis</span></span>  <br/> |
   
## <a name="malta"></a><span data-ttu-id="51ea7-544">Malta</span><span class="sxs-lookup"><span data-stu-id="51ea7-544">Malta</span></span>

### <a name="format"></a><span data-ttu-id="51ea7-545">Formato</span><span class="sxs-lookup"><span data-stu-id="51ea7-545">Format</span></span>

<span data-ttu-id="51ea7-546">Combinazione di due caratteri e sei cifre nella serie specificata</span><span class="sxs-lookup"><span data-stu-id="51ea7-546">Combination of two characters and six digits in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="51ea7-547">Modello</span><span class="sxs-lookup"><span data-stu-id="51ea7-547">Pattern</span></span>

<span data-ttu-id="51ea7-548">Combinazione di due caratteri e sei cifre:</span><span class="sxs-lookup"><span data-stu-id="51ea7-548">Combination of two characters and six digits:</span></span>
  
- <span data-ttu-id="51ea7-549">Due caratteri (cifre o lettere maiuscole o minuscole)</span><span class="sxs-lookup"><span data-stu-id="51ea7-549">Two characters (digits or letters, not case-sensitive)</span></span>
    
- <span data-ttu-id="51ea7-550">Uno spazio (facoltativo)</span><span class="sxs-lookup"><span data-stu-id="51ea7-550">A space (optional)</span></span>
    
- <span data-ttu-id="51ea7-551">Tre cifre</span><span class="sxs-lookup"><span data-stu-id="51ea7-551">Three digits</span></span>
    
- <span data-ttu-id="51ea7-552">Uno spazio (facoltativo)</span><span class="sxs-lookup"><span data-stu-id="51ea7-552">A space (optional)</span></span>
    
- <span data-ttu-id="51ea7-553">Tre cifre</span><span class="sxs-lookup"><span data-stu-id="51ea7-553">Three digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="51ea7-554">Checksum</span><span class="sxs-lookup"><span data-stu-id="51ea7-554">Checksum</span></span>

<span data-ttu-id="51ea7-555">No</span><span class="sxs-lookup"><span data-stu-id="51ea7-555">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="51ea7-556">Definizione</span><span class="sxs-lookup"><span data-stu-id="51ea7-556">Definition</span></span>

<span data-ttu-id="51ea7-557">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="51ea7-557">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="51ea7-558">L'espressione regolare `Regex_malta_eu_driver's_license_number` consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="51ea7-558">The regular expression  `Regex_malta_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="51ea7-559">Una parola chiave da `Keywords_malta_eu_driver's_license_number` viene trovato.</span><span class="sxs-lookup"><span data-stu-id="51ea7-559">A keyword from  `Keywords_malta_eu_driver's_license_number` is found.</span></span> 
    
```
<!-- EU Driver's License Number -->
 <Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_malta_eu_driver's_license_number" />
          <Match idRef="Keywords_malta_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="51ea7-560">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="51ea7-560">Keywords</span></span>

<span data-ttu-id="51ea7-561">| |</span><span class="sxs-lookup"><span data-stu-id="51ea7-561"></span></span>
|<span data-ttu-id="51ea7-562">**Keywords_malta_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="51ea7-562">**Keywords_malta_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="51ea7-563">DL #</span><span class="sxs-lookup"><span data-stu-id="51ea7-563">dl#</span></span>  <br/> <span data-ttu-id="51ea7-564">patente</span><span class="sxs-lookup"><span data-stu-id="51ea7-564">driver license</span></span>  <br/> <span data-ttu-id="51ea7-565">Numero patente di Guida</span><span class="sxs-lookup"><span data-stu-id="51ea7-565">driver license number</span></span>  <br/> <span data-ttu-id="51ea7-566">titolo driver</span><span class="sxs-lookup"><span data-stu-id="51ea7-566">driver licence</span></span>  <br/> <span data-ttu-id="51ea7-567">driver lic.</span><span class="sxs-lookup"><span data-stu-id="51ea7-567">drivers lic.</span></span>  <br/> <span data-ttu-id="51ea7-568">patente di Guida</span><span class="sxs-lookup"><span data-stu-id="51ea7-568">drivers license</span></span>  <br/> <span data-ttu-id="51ea7-569">drivers licence</span><span class="sxs-lookup"><span data-stu-id="51ea7-569">drivers licence</span></span>  <br/> <span data-ttu-id="51ea7-570">patente</span><span class="sxs-lookup"><span data-stu-id="51ea7-570">driver's license</span></span>  <br/> <span data-ttu-id="51ea7-571">numero della patente di Guida</span><span class="sxs-lookup"><span data-stu-id="51ea7-571">driver's license number</span></span>  <br/> <span data-ttu-id="51ea7-572">numero della patente di Guida</span><span class="sxs-lookup"><span data-stu-id="51ea7-572">driver's licence number</span></span>  <br/> <span data-ttu-id="51ea7-573">che influisce sul numero di licenza</span><span class="sxs-lookup"><span data-stu-id="51ea7-573">driving license number</span></span>  <br/> <span data-ttu-id="51ea7-574">dlno #</span><span class="sxs-lookup"><span data-stu-id="51ea7-574">dlno#</span></span>  <br/> <span data-ttu-id="51ea7-575">attività liċenzja-sewqan</span><span class="sxs-lookup"><span data-stu-id="51ea7-575">liċenzja tas-sewqan</span></span>  <br/> |
   
## <a name="netherlands"></a><span data-ttu-id="51ea7-576">Paesi Bassi</span><span class="sxs-lookup"><span data-stu-id="51ea7-576">Netherlands</span></span>

### <a name="format"></a><span data-ttu-id="51ea7-577">Formato</span><span class="sxs-lookup"><span data-stu-id="51ea7-577">Format</span></span>

<span data-ttu-id="51ea7-578">10 cifre senza spazi e i delimitatori</span><span class="sxs-lookup"><span data-stu-id="51ea7-578">10 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="51ea7-579">Modello</span><span class="sxs-lookup"><span data-stu-id="51ea7-579">Pattern</span></span>

<span data-ttu-id="51ea7-580">10 cifre</span><span class="sxs-lookup"><span data-stu-id="51ea7-580">10 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="51ea7-581">Checksum</span><span class="sxs-lookup"><span data-stu-id="51ea7-581">Checksum</span></span>

<span data-ttu-id="51ea7-582">No</span><span class="sxs-lookup"><span data-stu-id="51ea7-582">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="51ea7-583">Definizione</span><span class="sxs-lookup"><span data-stu-id="51ea7-583">Definition</span></span>

<span data-ttu-id="51ea7-584">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="51ea7-584">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="51ea7-585">L'espressione regolare `Regex_netherlands_eu_driver's_license_number` consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="51ea7-585">The regular expression  `Regex_netherlands_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="51ea7-586">Una parola chiave da `Keywords_netherlands_eu_driver's_license_number` viene trovato.</span><span class="sxs-lookup"><span data-stu-id="51ea7-586">A keyword from  `Keywords_netherlands_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_netherlands_eu_driver's_license_number" />
          <Match idRef="Keywords_netherlands_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="51ea7-587">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="51ea7-587">Keywords</span></span>

<span data-ttu-id="51ea7-588">| |</span><span class="sxs-lookup"><span data-stu-id="51ea7-588"></span></span>
|<span data-ttu-id="51ea7-589">**Keywords_netherlands_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="51ea7-589">**Keywords_netherlands_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="51ea7-590">DL #</span><span class="sxs-lookup"><span data-stu-id="51ea7-590">dl#</span></span>  <br/> <span data-ttu-id="51ea7-591">patente</span><span class="sxs-lookup"><span data-stu-id="51ea7-591">driver license</span></span>  <br/> <span data-ttu-id="51ea7-592">Numero patente di Guida</span><span class="sxs-lookup"><span data-stu-id="51ea7-592">driver license number</span></span>  <br/> <span data-ttu-id="51ea7-593">titolo driver</span><span class="sxs-lookup"><span data-stu-id="51ea7-593">driver licence</span></span>  <br/> <span data-ttu-id="51ea7-594">driver lic.</span><span class="sxs-lookup"><span data-stu-id="51ea7-594">drivers lic.</span></span>  <br/> <span data-ttu-id="51ea7-595">patente di Guida</span><span class="sxs-lookup"><span data-stu-id="51ea7-595">drivers license</span></span>  <br/> <span data-ttu-id="51ea7-596">drivers licence</span><span class="sxs-lookup"><span data-stu-id="51ea7-596">drivers licence</span></span>  <br/> <span data-ttu-id="51ea7-597">patente</span><span class="sxs-lookup"><span data-stu-id="51ea7-597">driver's license</span></span>  <br/> <span data-ttu-id="51ea7-598">numero della patente di Guida</span><span class="sxs-lookup"><span data-stu-id="51ea7-598">driver's license number</span></span>  <br/> <span data-ttu-id="51ea7-599">numero della patente di Guida</span><span class="sxs-lookup"><span data-stu-id="51ea7-599">driver's licence number</span></span>  <br/> <span data-ttu-id="51ea7-600">che influisce sul numero di licenza</span><span class="sxs-lookup"><span data-stu-id="51ea7-600">driving license number</span></span>  <br/> <span data-ttu-id="51ea7-601">dlno #</span><span class="sxs-lookup"><span data-stu-id="51ea7-601">dlno#</span></span>  <br/> <span data-ttu-id="51ea7-602">
permis de conduire</span><span class="sxs-lookup"><span data-stu-id="51ea7-602">permis de conduire</span></span>  <br/> <span data-ttu-id="51ea7-603">rijbewijs</span><span class="sxs-lookup"><span data-stu-id="51ea7-603">rijbewijs</span></span>  <br/> <span data-ttu-id="51ea7-604">rijbewijsnummer</span><span class="sxs-lookup"><span data-stu-id="51ea7-604">rijbewijsnummer</span></span>  <br/> |
   
## <a name="poland"></a><span data-ttu-id="51ea7-605">Polonia</span><span class="sxs-lookup"><span data-stu-id="51ea7-605">Poland</span></span>

### <a name="format"></a><span data-ttu-id="51ea7-606">Formato</span><span class="sxs-lookup"><span data-stu-id="51ea7-606">Format</span></span>

<span data-ttu-id="51ea7-607">14 cifre che contiene 2 barre</span><span class="sxs-lookup"><span data-stu-id="51ea7-607">14 digits containing 2 forward slashes</span></span>
  
### <a name="pattern"></a><span data-ttu-id="51ea7-608">Modello</span><span class="sxs-lookup"><span data-stu-id="51ea7-608">Pattern</span></span>

<span data-ttu-id="51ea7-609">14 cifre e 2 barre:</span><span class="sxs-lookup"><span data-stu-id="51ea7-609">14 digits and 2 forward slashes:</span></span>
  
-  <span data-ttu-id="51ea7-610">Cinque cifre</span><span class="sxs-lookup"><span data-stu-id="51ea7-610">Five digits</span></span> 
    
- <span data-ttu-id="51ea7-611">Una barra</span><span class="sxs-lookup"><span data-stu-id="51ea7-611">A forward slash</span></span>
    
- <span data-ttu-id="51ea7-612">Due cifre</span><span class="sxs-lookup"><span data-stu-id="51ea7-612">Two digits</span></span>
    
- <span data-ttu-id="51ea7-613">Una barra</span><span class="sxs-lookup"><span data-stu-id="51ea7-613">A forward slash</span></span>
    
- <span data-ttu-id="51ea7-614">Sette cifre</span><span class="sxs-lookup"><span data-stu-id="51ea7-614">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="51ea7-615">Checksum</span><span class="sxs-lookup"><span data-stu-id="51ea7-615">Checksum</span></span>

<span data-ttu-id="51ea7-616">No</span><span class="sxs-lookup"><span data-stu-id="51ea7-616">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="51ea7-617">Definizione</span><span class="sxs-lookup"><span data-stu-id="51ea7-617">Definition</span></span>

<span data-ttu-id="51ea7-618">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="51ea7-618">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="51ea7-619">L'espressione regolare `Regex_poland_eu_driver's_license_number` consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="51ea7-619">The regular expression  `Regex_poland_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="51ea7-620">Una parola chiave da `Keywords_poland_eu_driver's_license_number` viene trovato.</span><span class="sxs-lookup"><span data-stu-id="51ea7-620">A keyword from  `Keywords_poland_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_poland_eu_driver's_license_number" />
          <Match idRef="Keywords_poland_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="51ea7-621">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="51ea7-621">Keywords</span></span>

<span data-ttu-id="51ea7-622">| |</span><span class="sxs-lookup"><span data-stu-id="51ea7-622"></span></span>
|<span data-ttu-id="51ea7-623">**Keywords_poland_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="51ea7-623">**Keywords_poland_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="51ea7-624">DL #</span><span class="sxs-lookup"><span data-stu-id="51ea7-624">dl#</span></span>  <br/> <span data-ttu-id="51ea7-625">patente</span><span class="sxs-lookup"><span data-stu-id="51ea7-625">driver license</span></span>  <br/> <span data-ttu-id="51ea7-626">Numero patente di Guida</span><span class="sxs-lookup"><span data-stu-id="51ea7-626">driver license number</span></span>  <br/> <span data-ttu-id="51ea7-627">titolo driver</span><span class="sxs-lookup"><span data-stu-id="51ea7-627">driver licence</span></span>  <br/> <span data-ttu-id="51ea7-628">driver lic.</span><span class="sxs-lookup"><span data-stu-id="51ea7-628">drivers lic.</span></span>  <br/> <span data-ttu-id="51ea7-629">patente di Guida</span><span class="sxs-lookup"><span data-stu-id="51ea7-629">drivers license</span></span>  <br/> <span data-ttu-id="51ea7-630">drivers licence</span><span class="sxs-lookup"><span data-stu-id="51ea7-630">drivers licence</span></span>  <br/> <span data-ttu-id="51ea7-631">patente</span><span class="sxs-lookup"><span data-stu-id="51ea7-631">driver's license</span></span>  <br/> <span data-ttu-id="51ea7-632">numero della patente di Guida</span><span class="sxs-lookup"><span data-stu-id="51ea7-632">driver's license number</span></span>  <br/> <span data-ttu-id="51ea7-633">numero della patente di Guida</span><span class="sxs-lookup"><span data-stu-id="51ea7-633">driver's licence number</span></span>  <br/> <span data-ttu-id="51ea7-634">che influisce sul numero di licenza</span><span class="sxs-lookup"><span data-stu-id="51ea7-634">driving license number</span></span>  <br/> <span data-ttu-id="51ea7-635">dlno #</span><span class="sxs-lookup"><span data-stu-id="51ea7-635">dlno#</span></span>  <br/> <span data-ttu-id="51ea7-636">prawo jazdy</span><span class="sxs-lookup"><span data-stu-id="51ea7-636">prawo jazdy</span></span>  <br/> |
   
## <a name="portugal"></a><span data-ttu-id="51ea7-637">Portogallo</span><span class="sxs-lookup"><span data-stu-id="51ea7-637">Portugal</span></span>

### <a name="format"></a><span data-ttu-id="51ea7-638">Formato</span><span class="sxs-lookup"><span data-stu-id="51ea7-638">Format</span></span>

<span data-ttu-id="51ea7-639">Due lettere seguite da un sette i numeri in formato specificato</span><span class="sxs-lookup"><span data-stu-id="51ea7-639">Two letters followed by a seven numbers in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="51ea7-640">Modello</span><span class="sxs-lookup"><span data-stu-id="51ea7-640">Pattern</span></span>

<span data-ttu-id="51ea7-641">Due lettere seguite da sette numeri con caratteri speciali:</span><span class="sxs-lookup"><span data-stu-id="51ea7-641">Two letters followed by seven numbers with special characters:</span></span>
  
-  <span data-ttu-id="51ea7-642">Due lettere (maiuscole o minuscole)</span><span class="sxs-lookup"><span data-stu-id="51ea7-642">Two letters (not case-sensitive)</span></span> 
    
- <span data-ttu-id="51ea7-643">Una lineetta</span><span class="sxs-lookup"><span data-stu-id="51ea7-643">A hyphen</span></span>
    
- <span data-ttu-id="51ea7-644">Sei cifre</span><span class="sxs-lookup"><span data-stu-id="51ea7-644">Six digits</span></span>
    
- <span data-ttu-id="51ea7-645">Uno spazio</span><span class="sxs-lookup"><span data-stu-id="51ea7-645">A space</span></span>
    
- <span data-ttu-id="51ea7-646">Una cifra</span><span class="sxs-lookup"><span data-stu-id="51ea7-646">One digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="51ea7-647">Checksum</span><span class="sxs-lookup"><span data-stu-id="51ea7-647">Checksum</span></span>

<span data-ttu-id="51ea7-648">No</span><span class="sxs-lookup"><span data-stu-id="51ea7-648">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="51ea7-649">Definizione</span><span class="sxs-lookup"><span data-stu-id="51ea7-649">Definition</span></span>

<span data-ttu-id="51ea7-650">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="51ea7-650">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="51ea7-651">L'espressione regolare `Regex_portugal_eu_driver's_license_number` consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="51ea7-651">The regular expression  `Regex_portugal_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="51ea7-652">Una parola chiave da `Keywords_portugal_eu_driver's_license_number` viene trovato.</span><span class="sxs-lookup"><span data-stu-id="51ea7-652">A keyword from  `Keywords_portugal_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_portugal_eu_driver's_license_number" />
          <Match idRef="Keywords_portugal_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="51ea7-653">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="51ea7-653">Keywords</span></span>

<span data-ttu-id="51ea7-654">| |</span><span class="sxs-lookup"><span data-stu-id="51ea7-654"></span></span>
|<span data-ttu-id="51ea7-655">**Keywords_portugal_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="51ea7-655">**Keywords_portugal_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="51ea7-656">DL #</span><span class="sxs-lookup"><span data-stu-id="51ea7-656">dl#</span></span>  <br/> <span data-ttu-id="51ea7-657">patente</span><span class="sxs-lookup"><span data-stu-id="51ea7-657">driver license</span></span>  <br/> <span data-ttu-id="51ea7-658">Numero patente di Guida</span><span class="sxs-lookup"><span data-stu-id="51ea7-658">driver license number</span></span>  <br/> <span data-ttu-id="51ea7-659">titolo driver</span><span class="sxs-lookup"><span data-stu-id="51ea7-659">driver licence</span></span>  <br/> <span data-ttu-id="51ea7-660">driver lic.</span><span class="sxs-lookup"><span data-stu-id="51ea7-660">drivers lic.</span></span>  <br/> <span data-ttu-id="51ea7-661">patente di Guida</span><span class="sxs-lookup"><span data-stu-id="51ea7-661">drivers license</span></span>  <br/> <span data-ttu-id="51ea7-662">drivers licence</span><span class="sxs-lookup"><span data-stu-id="51ea7-662">drivers licence</span></span>  <br/> <span data-ttu-id="51ea7-663">patente</span><span class="sxs-lookup"><span data-stu-id="51ea7-663">driver's license</span></span>  <br/> <span data-ttu-id="51ea7-664">numero della patente di Guida</span><span class="sxs-lookup"><span data-stu-id="51ea7-664">driver's license number</span></span>  <br/> <span data-ttu-id="51ea7-665">numero della patente di Guida</span><span class="sxs-lookup"><span data-stu-id="51ea7-665">driver's licence number</span></span>  <br/> <span data-ttu-id="51ea7-666">che influisce sul numero di licenza</span><span class="sxs-lookup"><span data-stu-id="51ea7-666">driving license number</span></span>  <br/> <span data-ttu-id="51ea7-667">dlno #</span><span class="sxs-lookup"><span data-stu-id="51ea7-667">dlno#</span></span>  <br/> <span data-ttu-id="51ea7-668">carteira de motorista</span><span class="sxs-lookup"><span data-stu-id="51ea7-668">carteira de motorista</span></span>  <br/> |
   
## <a name="romania"></a><span data-ttu-id="51ea7-669">Romania</span><span class="sxs-lookup"><span data-stu-id="51ea7-669">Romania</span></span>

### <a name="format"></a><span data-ttu-id="51ea7-670">Formato</span><span class="sxs-lookup"><span data-stu-id="51ea7-670">Format</span></span>

<span data-ttu-id="51ea7-671">Un carattere seguito da 8 cifre</span><span class="sxs-lookup"><span data-stu-id="51ea7-671">One character followed by eight digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="51ea7-672">Modello</span><span class="sxs-lookup"><span data-stu-id="51ea7-672">Pattern</span></span>

<span data-ttu-id="51ea7-673">Un carattere seguito da 8 cifre:</span><span class="sxs-lookup"><span data-stu-id="51ea7-673">One character followed by eight digits:</span></span>
  
-  <span data-ttu-id="51ea7-674">Una lettera (maiuscole o minuscole) o cifre</span><span class="sxs-lookup"><span data-stu-id="51ea7-674">One letter (not case-sensitive) or digit</span></span> 
    
- <span data-ttu-id="51ea7-675">Otto cifre</span><span class="sxs-lookup"><span data-stu-id="51ea7-675">Eight digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="51ea7-676">Checksum</span><span class="sxs-lookup"><span data-stu-id="51ea7-676">Checksum</span></span>

<span data-ttu-id="51ea7-677">No</span><span class="sxs-lookup"><span data-stu-id="51ea7-677">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="51ea7-678">Definizione</span><span class="sxs-lookup"><span data-stu-id="51ea7-678">Definition</span></span>

<span data-ttu-id="51ea7-679">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="51ea7-679">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="51ea7-680">L'espressione regolare `Regex_romania_eu_driver's_license_number` consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="51ea7-680">The regular expression  `Regex_romania_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="51ea7-681">Una parola chiave da `Keywords_romania_eu_driver's_license_number` viene trovato.</span><span class="sxs-lookup"><span data-stu-id="51ea7-681">A keyword from  `Keywords_romania_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_romania_eu_driver's_license_number" />
          <Match idRef="Keywords_romania_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="51ea7-682">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="51ea7-682">Keywords</span></span>

<span data-ttu-id="51ea7-683">| |</span><span class="sxs-lookup"><span data-stu-id="51ea7-683"></span></span>
|<span data-ttu-id="51ea7-684">**Keywords_romania_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="51ea7-684">**Keywords_romania_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="51ea7-685">DL #</span><span class="sxs-lookup"><span data-stu-id="51ea7-685">dl#</span></span>  <br/> <span data-ttu-id="51ea7-686">patente</span><span class="sxs-lookup"><span data-stu-id="51ea7-686">driver license</span></span>  <br/> <span data-ttu-id="51ea7-687">Numero patente di Guida</span><span class="sxs-lookup"><span data-stu-id="51ea7-687">driver license number</span></span>  <br/> <span data-ttu-id="51ea7-688">titolo driver</span><span class="sxs-lookup"><span data-stu-id="51ea7-688">driver licence</span></span>  <br/> <span data-ttu-id="51ea7-689">driver lic.</span><span class="sxs-lookup"><span data-stu-id="51ea7-689">drivers lic.</span></span>  <br/> <span data-ttu-id="51ea7-690">patente di Guida</span><span class="sxs-lookup"><span data-stu-id="51ea7-690">drivers license</span></span>  <br/> <span data-ttu-id="51ea7-691">drivers licence</span><span class="sxs-lookup"><span data-stu-id="51ea7-691">drivers licence</span></span>  <br/> <span data-ttu-id="51ea7-692">patente</span><span class="sxs-lookup"><span data-stu-id="51ea7-692">driver's license</span></span>  <br/> <span data-ttu-id="51ea7-693">numero della patente di Guida</span><span class="sxs-lookup"><span data-stu-id="51ea7-693">driver's license number</span></span>  <br/> <span data-ttu-id="51ea7-694">numero della patente di Guida</span><span class="sxs-lookup"><span data-stu-id="51ea7-694">driver's licence number</span></span>  <br/> <span data-ttu-id="51ea7-695">che influisce sul numero di licenza</span><span class="sxs-lookup"><span data-stu-id="51ea7-695">driving license number</span></span>  <br/> <span data-ttu-id="51ea7-696">dlno #</span><span class="sxs-lookup"><span data-stu-id="51ea7-696">dlno#</span></span>  <br/> <span data-ttu-id="51ea7-697">permis de conducere</span><span class="sxs-lookup"><span data-stu-id="51ea7-697">permis de conducere</span></span>  <br/> |
   
## <a name="slovakia"></a><span data-ttu-id="51ea7-698">Slovacchia</span><span class="sxs-lookup"><span data-stu-id="51ea7-698">Slovakia</span></span>

### <a name="format"></a><span data-ttu-id="51ea7-699">Formato</span><span class="sxs-lookup"><span data-stu-id="51ea7-699">Format</span></span>

<span data-ttu-id="51ea7-700">Un carattere seguito da sette cifre</span><span class="sxs-lookup"><span data-stu-id="51ea7-700">One character followed by seven digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="51ea7-701">Modello</span><span class="sxs-lookup"><span data-stu-id="51ea7-701">Pattern</span></span>

<span data-ttu-id="51ea7-702">Un carattere seguito da sette cifre</span><span class="sxs-lookup"><span data-stu-id="51ea7-702">One character followed by seven digits</span></span>
  
- <span data-ttu-id="51ea7-703">Una lettera (maiuscole o minuscole) o cifre</span><span class="sxs-lookup"><span data-stu-id="51ea7-703">One letter (not case-sensitive) or digit</span></span>
    
-  <span data-ttu-id="51ea7-704">Sette cifre</span><span class="sxs-lookup"><span data-stu-id="51ea7-704">Seven digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="51ea7-705">Checksum</span><span class="sxs-lookup"><span data-stu-id="51ea7-705">Checksum</span></span>

<span data-ttu-id="51ea7-706">No</span><span class="sxs-lookup"><span data-stu-id="51ea7-706">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="51ea7-707">Definizione</span><span class="sxs-lookup"><span data-stu-id="51ea7-707">Definition</span></span>

<span data-ttu-id="51ea7-708">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="51ea7-708">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="51ea7-709">L'espressione regolare `Regex_slovakia_eu_driver's_license_number` consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="51ea7-709">The regular expression  `Regex_slovakia_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="51ea7-710">Una parola chiave da `Keywords_slovakia_eu_driver's_license_number` viene trovato.</span><span class="sxs-lookup"><span data-stu-id="51ea7-710">A keyword from  `Keywords_slovakia_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovaknia_eu_driver's_license_number" />
          <Match idRef="Keywords_slovakia_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="51ea7-711">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="51ea7-711">Keywords</span></span>

<span data-ttu-id="51ea7-712">| |</span><span class="sxs-lookup"><span data-stu-id="51ea7-712"></span></span>
|<span data-ttu-id="51ea7-713">**Keywords_slovakia_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="51ea7-713">**Keywords_slovakia_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="51ea7-714">DL #</span><span class="sxs-lookup"><span data-stu-id="51ea7-714">dl#</span></span>  <br/> <span data-ttu-id="51ea7-715">patente</span><span class="sxs-lookup"><span data-stu-id="51ea7-715">driver license</span></span>  <br/> <span data-ttu-id="51ea7-716">Numero patente di Guida</span><span class="sxs-lookup"><span data-stu-id="51ea7-716">driver license number</span></span>  <br/> <span data-ttu-id="51ea7-717">titolo driver</span><span class="sxs-lookup"><span data-stu-id="51ea7-717">driver licence</span></span>  <br/> <span data-ttu-id="51ea7-718">driver lic.</span><span class="sxs-lookup"><span data-stu-id="51ea7-718">drivers lic.</span></span>  <br/> <span data-ttu-id="51ea7-719">patente di Guida</span><span class="sxs-lookup"><span data-stu-id="51ea7-719">drivers license</span></span>  <br/> <span data-ttu-id="51ea7-720">drivers licence</span><span class="sxs-lookup"><span data-stu-id="51ea7-720">drivers licence</span></span>  <br/> <span data-ttu-id="51ea7-721">patente</span><span class="sxs-lookup"><span data-stu-id="51ea7-721">driver's license</span></span>  <br/> <span data-ttu-id="51ea7-722">numero della patente di Guida</span><span class="sxs-lookup"><span data-stu-id="51ea7-722">driver's license number</span></span>  <br/> <span data-ttu-id="51ea7-723">numero della patente di Guida</span><span class="sxs-lookup"><span data-stu-id="51ea7-723">driver's licence number</span></span>  <br/> <span data-ttu-id="51ea7-724">che influisce sul numero di licenza</span><span class="sxs-lookup"><span data-stu-id="51ea7-724">driving license number</span></span>  <br/> <span data-ttu-id="51ea7-725">dlno #</span><span class="sxs-lookup"><span data-stu-id="51ea7-725">dlno#</span></span>  <br/> <span data-ttu-id="51ea7-726">vodičský preukaz</span><span class="sxs-lookup"><span data-stu-id="51ea7-726">vodičský preukaz</span></span>  <br/> |
   
## <a name="slovenia"></a><span data-ttu-id="51ea7-727">Slovenia</span><span class="sxs-lookup"><span data-stu-id="51ea7-727">Slovenia</span></span>

### <a name="format"></a><span data-ttu-id="51ea7-728">Formato</span><span class="sxs-lookup"><span data-stu-id="51ea7-728">Format</span></span>

<span data-ttu-id="51ea7-729">Nove cifre senza spazi e i delimitatori</span><span class="sxs-lookup"><span data-stu-id="51ea7-729">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="51ea7-730">Modello</span><span class="sxs-lookup"><span data-stu-id="51ea7-730">Pattern</span></span>

<span data-ttu-id="51ea7-731">9 cifre</span><span class="sxs-lookup"><span data-stu-id="51ea7-731">Nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="51ea7-732">Checksum</span><span class="sxs-lookup"><span data-stu-id="51ea7-732">Checksum</span></span>

<span data-ttu-id="51ea7-733">No</span><span class="sxs-lookup"><span data-stu-id="51ea7-733">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="51ea7-734">Definizione</span><span class="sxs-lookup"><span data-stu-id="51ea7-734">Definition</span></span>

<span data-ttu-id="51ea7-735">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="51ea7-735">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="51ea7-736">L'espressione regolare `Regex_slovenia_eu_driver's_license_number` consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="51ea7-736">The regular expression  `Regex_slovenia_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="51ea7-737">Una parola chiave da `Keywords_slovenia_eu_driver's_license_number` viene trovato.</span><span class="sxs-lookup"><span data-stu-id="51ea7-737">A keyword from  `Keywords_slovenia_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovenia_eu_driver's_license_number" />
          <Match idRef="Keywords_slovenia_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="51ea7-738">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="51ea7-738">Keywords</span></span>

<span data-ttu-id="51ea7-739">| |</span><span class="sxs-lookup"><span data-stu-id="51ea7-739"></span></span>
|<span data-ttu-id="51ea7-740">**Keywords_slovenia_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="51ea7-740">**Keywords_slovenia_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="51ea7-741">DL #</span><span class="sxs-lookup"><span data-stu-id="51ea7-741">dl#</span></span>  <br/> <span data-ttu-id="51ea7-742">patente</span><span class="sxs-lookup"><span data-stu-id="51ea7-742">driver license</span></span>  <br/> <span data-ttu-id="51ea7-743">Numero patente di Guida</span><span class="sxs-lookup"><span data-stu-id="51ea7-743">driver license number</span></span>  <br/> <span data-ttu-id="51ea7-744">titolo driver</span><span class="sxs-lookup"><span data-stu-id="51ea7-744">driver licence</span></span>  <br/> <span data-ttu-id="51ea7-745">driver lic.</span><span class="sxs-lookup"><span data-stu-id="51ea7-745">drivers lic.</span></span>  <br/> <span data-ttu-id="51ea7-746">patente di Guida</span><span class="sxs-lookup"><span data-stu-id="51ea7-746">drivers license</span></span>  <br/> <span data-ttu-id="51ea7-747">drivers licence</span><span class="sxs-lookup"><span data-stu-id="51ea7-747">drivers licence</span></span>  <br/> <span data-ttu-id="51ea7-748">patente</span><span class="sxs-lookup"><span data-stu-id="51ea7-748">driver's license</span></span>  <br/> <span data-ttu-id="51ea7-749">numero della patente di Guida</span><span class="sxs-lookup"><span data-stu-id="51ea7-749">driver's license number</span></span>  <br/> <span data-ttu-id="51ea7-750">numero della patente di Guida</span><span class="sxs-lookup"><span data-stu-id="51ea7-750">driver's licence number</span></span>  <br/> <span data-ttu-id="51ea7-751">che influisce sul numero di licenza</span><span class="sxs-lookup"><span data-stu-id="51ea7-751">driving license number</span></span>  <br/> <span data-ttu-id="51ea7-752">dlno #</span><span class="sxs-lookup"><span data-stu-id="51ea7-752">dlno#</span></span>  <br/> <span data-ttu-id="51ea7-753">vozniško dovoljenje</span><span class="sxs-lookup"><span data-stu-id="51ea7-753">vozniško dovoljenje</span></span>  <br/> |
   
## <a name="spain"></a><span data-ttu-id="51ea7-754">Spagna</span><span class="sxs-lookup"><span data-stu-id="51ea7-754">Spain</span></span>

### <a name="format"></a><span data-ttu-id="51ea7-755">Formato</span><span class="sxs-lookup"><span data-stu-id="51ea7-755">Format</span></span>

<span data-ttu-id="51ea7-756">Otto cifre seguite da un carattere</span><span class="sxs-lookup"><span data-stu-id="51ea7-756">Eight digits followed by one character</span></span>
  
### <a name="pattern"></a><span data-ttu-id="51ea7-757">Modello</span><span class="sxs-lookup"><span data-stu-id="51ea7-757">Pattern</span></span>

<span data-ttu-id="51ea7-758">Otto cifre seguite da un carattere:</span><span class="sxs-lookup"><span data-stu-id="51ea7-758">Eight digits followed by one character:</span></span>
  
-  <span data-ttu-id="51ea7-759">Otto cifre</span><span class="sxs-lookup"><span data-stu-id="51ea7-759">Eight digits</span></span> 
    
- <span data-ttu-id="51ea7-760">Una cifra o lettere (maiuscole o minuscole)</span><span class="sxs-lookup"><span data-stu-id="51ea7-760">One digit or letter (not case-sensitive)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="51ea7-761">Checksum</span><span class="sxs-lookup"><span data-stu-id="51ea7-761">Checksum</span></span>

<span data-ttu-id="51ea7-762">Sì</span><span class="sxs-lookup"><span data-stu-id="51ea7-762">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="51ea7-763">Definizione</span><span class="sxs-lookup"><span data-stu-id="51ea7-763">Definition</span></span>

<span data-ttu-id="51ea7-764">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="51ea7-764">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="51ea7-765">La funzione `Func_spain_eu_driver's_license_number` consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="51ea7-765">The function  `Func_spain_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="51ea7-766">Una parola chiave da `Keywords_spain_eu_driver's_license_number` viene trovato.</span><span class="sxs-lookup"><span data-stu-id="51ea7-766">A keyword from  `Keywords_spain_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_spain_eu_driver's_license_number" />
          <Match idRef="Keywords_spain_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="51ea7-767">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="51ea7-767">Keywords</span></span>

<span data-ttu-id="51ea7-768">| |</span><span class="sxs-lookup"><span data-stu-id="51ea7-768"></span></span>
|<span data-ttu-id="51ea7-769">**Keywords_spain_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="51ea7-769">**Keywords_spain_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="51ea7-770">dlno #</span><span class="sxs-lookup"><span data-stu-id="51ea7-770">dlno#</span></span>  <br/> <span data-ttu-id="51ea7-771">DL #</span><span class="sxs-lookup"><span data-stu-id="51ea7-771">dl#</span></span>  <br/> <span data-ttu-id="51ea7-772">driver lic.</span><span class="sxs-lookup"><span data-stu-id="51ea7-772">drivers lic.</span></span>  <br/> <span data-ttu-id="51ea7-773">titolo driver</span><span class="sxs-lookup"><span data-stu-id="51ea7-773">driver licence</span></span>  <br/> <span data-ttu-id="51ea7-774">patente</span><span class="sxs-lookup"><span data-stu-id="51ea7-774">driver license</span></span>  <br/> <span data-ttu-id="51ea7-775">drivers licence</span><span class="sxs-lookup"><span data-stu-id="51ea7-775">drivers licence</span></span>  <br/> <span data-ttu-id="51ea7-776">
drivers license</span><span class="sxs-lookup"><span data-stu-id="51ea7-776">drivers license</span></span>  <br/> <span data-ttu-id="51ea7-777">titolo della patente di Guida</span><span class="sxs-lookup"><span data-stu-id="51ea7-777">driver's licence</span></span>  <br/> <span data-ttu-id="51ea7-778">patente</span><span class="sxs-lookup"><span data-stu-id="51ea7-778">driver's license</span></span>  <br/> <span data-ttu-id="51ea7-779">driving licence
</span><span class="sxs-lookup"><span data-stu-id="51ea7-779">driving licence</span></span>  <br/> <span data-ttu-id="51ea7-780">le licenze</span><span class="sxs-lookup"><span data-stu-id="51ea7-780">driving license</span></span>  <br/> <span data-ttu-id="51ea7-781">numero della patente del driver</span><span class="sxs-lookup"><span data-stu-id="51ea7-781">driver licence number</span></span>  <br/> <span data-ttu-id="51ea7-782">Numero patente di Guida</span><span class="sxs-lookup"><span data-stu-id="51ea7-782">driver license number</span></span>  <br/> <span data-ttu-id="51ea7-783">numero di driver di licenza</span><span class="sxs-lookup"><span data-stu-id="51ea7-783">drivers licence number</span></span>  <br/> <span data-ttu-id="51ea7-784">Numero patente</span><span class="sxs-lookup"><span data-stu-id="51ea7-784">drivers license number</span></span>  <br/> <span data-ttu-id="51ea7-785">numero della patente di Guida</span><span class="sxs-lookup"><span data-stu-id="51ea7-785">driver's licence number</span></span>  <br/> <span data-ttu-id="51ea7-786">numero della patente di Guida</span><span class="sxs-lookup"><span data-stu-id="51ea7-786">driver's license number</span></span>  <br/> <span data-ttu-id="51ea7-787">Numero patente di Guida</span><span class="sxs-lookup"><span data-stu-id="51ea7-787">driving licence number</span></span>  <br/> <span data-ttu-id="51ea7-788">che influisce sul numero di licenza</span><span class="sxs-lookup"><span data-stu-id="51ea7-788">driving license number</span></span>  <br/> <span data-ttu-id="51ea7-789">Guida autorizza</span><span class="sxs-lookup"><span data-stu-id="51ea7-789">driving permit</span></span>  <br/> <span data-ttu-id="51ea7-790">che influisce sul numero permesso</span><span class="sxs-lookup"><span data-stu-id="51ea7-790">driving permit number</span></span>  <br/> <span data-ttu-id="51ea7-791">permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="51ea7-791">permiso de conducción</span></span>  <br/> <span data-ttu-id="51ea7-792">permiso conducción</span><span class="sxs-lookup"><span data-stu-id="51ea7-792">permiso conducción</span></span>  <br/> <span data-ttu-id="51ea7-793">número licencia conducir</span><span class="sxs-lookup"><span data-stu-id="51ea7-793">número licencia conducir</span></span>  <br/> <span data-ttu-id="51ea7-794">número de carnet de conducir</span><span class="sxs-lookup"><span data-stu-id="51ea7-794">número de carnet de conducir</span></span>  <br/> <span data-ttu-id="51ea7-795">número carnet conducir</span><span class="sxs-lookup"><span data-stu-id="51ea7-795">número carnet conducir</span></span>  <br/> <span data-ttu-id="51ea7-796">licencia conducir</span><span class="sxs-lookup"><span data-stu-id="51ea7-796">licencia conducir</span></span>  <br/> <span data-ttu-id="51ea7-797">número de permiso de conducir</span><span class="sxs-lookup"><span data-stu-id="51ea7-797">número de permiso de conducir</span></span>  <br/> <span data-ttu-id="51ea7-798">número de permiso conducir</span><span class="sxs-lookup"><span data-stu-id="51ea7-798">número de permiso conducir</span></span>  <br/> <span data-ttu-id="51ea7-799">número permiso conducir</span><span class="sxs-lookup"><span data-stu-id="51ea7-799">número permiso conducir</span></span>  <br/> <span data-ttu-id="51ea7-800">permiso conducir</span><span class="sxs-lookup"><span data-stu-id="51ea7-800">permiso conducir</span></span>  <br/> <span data-ttu-id="51ea7-801">licencia de manejo</span><span class="sxs-lookup"><span data-stu-id="51ea7-801">licencia de manejo</span></span>  <br/> <span data-ttu-id="51ea7-802">EL carnet de conducir</span><span class="sxs-lookup"><span data-stu-id="51ea7-802">el carnet de conducir</span></span>  <br/> <span data-ttu-id="51ea7-803">carnet conducir</span><span class="sxs-lookup"><span data-stu-id="51ea7-803">carnet conducir</span></span>  <br/> |
   
## <a name="sweden"></a><span data-ttu-id="51ea7-804">Svezia</span><span class="sxs-lookup"><span data-stu-id="51ea7-804">Sweden</span></span>

### <a name="format"></a><span data-ttu-id="51ea7-805">Formato</span><span class="sxs-lookup"><span data-stu-id="51ea7-805">Format</span></span>

<span data-ttu-id="51ea7-806">Dieci cifre che contiene un segno meno</span><span class="sxs-lookup"><span data-stu-id="51ea7-806">Ten digits containing a hyphen</span></span>
  
### <a name="pattern"></a><span data-ttu-id="51ea7-807">Modello</span><span class="sxs-lookup"><span data-stu-id="51ea7-807">Pattern</span></span>

<span data-ttu-id="51ea7-808">Dieci cifre che contiene un segno meno:</span><span class="sxs-lookup"><span data-stu-id="51ea7-808">Ten digits containing a hyphen:</span></span>
  
-  <span data-ttu-id="51ea7-809">Sei cifre</span><span class="sxs-lookup"><span data-stu-id="51ea7-809">Six digits</span></span> 
    
- <span data-ttu-id="51ea7-810">Una lineetta</span><span class="sxs-lookup"><span data-stu-id="51ea7-810">A hyphen</span></span>
    
- <span data-ttu-id="51ea7-811">Quattro cifre</span><span class="sxs-lookup"><span data-stu-id="51ea7-811">Four digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="51ea7-812">Checksum</span><span class="sxs-lookup"><span data-stu-id="51ea7-812">Checksum</span></span>

<span data-ttu-id="51ea7-813">No</span><span class="sxs-lookup"><span data-stu-id="51ea7-813">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="51ea7-814">Definizione</span><span class="sxs-lookup"><span data-stu-id="51ea7-814">Definition</span></span>

<span data-ttu-id="51ea7-815">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="51ea7-815">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="51ea7-816">L'espressione regolare `Regex_sweden_eu_driver's_license_number` consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="51ea7-816">The regular expression  `Regex_sweden_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="51ea7-817">Una parola chiave da `Keywords_sweden_eu_driver's_license_number` viene trovato.</span><span class="sxs-lookup"><span data-stu-id="51ea7-817">A keyword from  `Keywords_sweden_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_sweden_eu_driver's_license_number" />
          <Match idRef="Keywords_sweden_eu_driver's_license_number" />
        </Pattern>
</Entity> 
```

### <a name="keywords"></a><span data-ttu-id="51ea7-818">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="51ea7-818">Keywords</span></span>

<span data-ttu-id="51ea7-819">| |</span><span class="sxs-lookup"><span data-stu-id="51ea7-819"></span></span>
|<span data-ttu-id="51ea7-820">**Keywords_sweden_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="51ea7-820">**Keywords_sweden_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="51ea7-821">DL #</span><span class="sxs-lookup"><span data-stu-id="51ea7-821">dl#</span></span>  <br/> <span data-ttu-id="51ea7-822">patente</span><span class="sxs-lookup"><span data-stu-id="51ea7-822">driver license</span></span>  <br/> <span data-ttu-id="51ea7-823">Numero patente di Guida</span><span class="sxs-lookup"><span data-stu-id="51ea7-823">driver license number</span></span>  <br/> <span data-ttu-id="51ea7-824">titolo driver</span><span class="sxs-lookup"><span data-stu-id="51ea7-824">driver licence</span></span>  <br/> <span data-ttu-id="51ea7-825">driver lic.</span><span class="sxs-lookup"><span data-stu-id="51ea7-825">drivers lic.</span></span>  <br/> <span data-ttu-id="51ea7-826">patente di Guida</span><span class="sxs-lookup"><span data-stu-id="51ea7-826">drivers license</span></span>  <br/> <span data-ttu-id="51ea7-827">drivers licence</span><span class="sxs-lookup"><span data-stu-id="51ea7-827">drivers licence</span></span>  <br/> <span data-ttu-id="51ea7-828">patente</span><span class="sxs-lookup"><span data-stu-id="51ea7-828">driver's license</span></span>  <br/> <span data-ttu-id="51ea7-829">numero della patente di Guida</span><span class="sxs-lookup"><span data-stu-id="51ea7-829">driver's license number</span></span>  <br/> <span data-ttu-id="51ea7-830">numero della patente di Guida</span><span class="sxs-lookup"><span data-stu-id="51ea7-830">driver's licence number</span></span>  <br/> <span data-ttu-id="51ea7-831">che influisce sul numero di licenza</span><span class="sxs-lookup"><span data-stu-id="51ea7-831">driving license number</span></span>  <br/> <span data-ttu-id="51ea7-832">dlno #</span><span class="sxs-lookup"><span data-stu-id="51ea7-832">dlno#</span></span>  <br/> <span data-ttu-id="51ea7-833">körkort</span><span class="sxs-lookup"><span data-stu-id="51ea7-833">körkort</span></span>  <br/> |
   
## <a name="uk"></a><span data-ttu-id="51ea7-834">REGNO UNITO</span><span class="sxs-lookup"><span data-stu-id="51ea7-834">UK</span></span>

<span data-ttu-id="51ea7-p103">Per ulteriori informazioni, vedere la sezione "Numero della patente di Guida di Regno Unito" in [cercare il quali i tipi di informazioni riservate](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="51ea7-p103">For details, see the section "U.K. Driver's License Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="51ea7-837">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="51ea7-837">See also</span></span>

[<span data-ttu-id="51ea7-838">Cosa individuano i tipi di informazioni riservate</span><span class="sxs-lookup"><span data-stu-id="51ea7-838">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)

