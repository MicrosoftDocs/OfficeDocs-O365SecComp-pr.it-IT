---
title: Numero della patente di guida dell'Unione europea
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 8/17/2018
ms.audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: c3923cd3-ec84-435f-bf41-cadc37996a4b
description: In questo argomento viene illustrato l'aspetto di un criterio di prevenzione della perdita di dati (DLP) quando viene rilevato il tipo di informazioni riservate del numero di licenza del driver dell'Unione europea. Questo tipo di informazioni riservate definisce modelli, parole chiave e altre evidenze diverse per ogni paese.
ms.openlocfilehash: 86be7b52aed7581fd62ab595ac2c4b63ab33aab3
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/23/2019
ms.locfileid: "30217746"
---
# <a name="eu-drivers-license-number"></a><span data-ttu-id="01619-104">Numero della patente di guida dell'Unione europea</span><span class="sxs-lookup"><span data-stu-id="01619-104">EU Driver's License Number</span></span>

<span data-ttu-id="01619-p102">In questo argomento viene illustrato l'aspetto di un criterio di prevenzione della perdita di dati (DLP) quando viene rilevato il tipo di informazioni riservate del numero di licenza del driver dell'Unione europea. Questo tipo di informazioni riservate definisce modelli, parole chiave e altre evidenze diverse per ogni paese.</span><span class="sxs-lookup"><span data-stu-id="01619-p102">This topic shows what a data loss prevention (DLP) policy looks for when it detects the EU Driver's License Number sensitive information type. This sensitive information type defines different patterns, keywords, and other evidence for each country.</span></span>
  
## <a name="austria"></a><span data-ttu-id="01619-107">Austria</span><span class="sxs-lookup"><span data-stu-id="01619-107">Austria</span></span>

### <a name="format"></a><span data-ttu-id="01619-108">Formato</span><span class="sxs-lookup"><span data-stu-id="01619-108">Format</span></span>

<span data-ttu-id="01619-109">Otto cifre senza spazi e delimitatori</span><span class="sxs-lookup"><span data-stu-id="01619-109">Eight digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="01619-110">Modello</span><span class="sxs-lookup"><span data-stu-id="01619-110">Pattern</span></span>

<span data-ttu-id="01619-111">Otto cifre</span><span class="sxs-lookup"><span data-stu-id="01619-111">Eight digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="01619-112">Checksum</span><span class="sxs-lookup"><span data-stu-id="01619-112">Checksum</span></span>

<span data-ttu-id="01619-113">No</span><span class="sxs-lookup"><span data-stu-id="01619-113">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="01619-114">Definizione</span><span class="sxs-lookup"><span data-stu-id="01619-114">Definition</span></span>

<span data-ttu-id="01619-115">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="01619-115">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="01619-116">L'espressione `Regex_austria_eu_driver's_license_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="01619-116">The regular expression  `Regex_austria_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="01619-117">Viene trovata una `Keywords_austria_eu_driver's_license_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="01619-117">A keyword from  `Keywords_austria_eu_driver's_license_number` is found.</span></span> 
    
```
<!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_austria_eu_driver's_license_number" />
          <Match idRef="Keywords_austria_eu_driver's_license_number" />
        </Pattern>
    </Entity>

```

### <a name="keywords"></a><span data-ttu-id="01619-118">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="01619-118">Keywords</span></span>

<span data-ttu-id="01619-119">| |</span><span class="sxs-lookup"><span data-stu-id="01619-119"></span></span>
|<span data-ttu-id="01619-120">**Keywords_austria_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="01619-120">**Keywords_austria_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="01619-121">DL</span><span class="sxs-lookup"><span data-stu-id="01619-121">dl#</span></span>  <br/> <span data-ttu-id="01619-122">patente di guida</span><span class="sxs-lookup"><span data-stu-id="01619-122">driver license</span></span>  <br/> <span data-ttu-id="01619-123">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="01619-123">driver license number</span></span>  <br/> <span data-ttu-id="01619-124">patente di guida</span><span class="sxs-lookup"><span data-stu-id="01619-124">driver licence</span></span>  <br/> <span data-ttu-id="01619-125">driver Lic.</span><span class="sxs-lookup"><span data-stu-id="01619-125">drivers lic.</span></span>  <br/> <span data-ttu-id="01619-126">patente di guida</span><span class="sxs-lookup"><span data-stu-id="01619-126">drivers license</span></span>  <br/> <span data-ttu-id="01619-127">patente di guida</span><span class="sxs-lookup"><span data-stu-id="01619-127">driver's licence</span></span>  <br/> <span data-ttu-id="01619-128">patente di guida</span><span class="sxs-lookup"><span data-stu-id="01619-128">driver's license</span></span>  <br/> <span data-ttu-id="01619-129">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="01619-129">driver's license number</span></span>  <br/> <span data-ttu-id="01619-130">numero di patente del conducente</span><span class="sxs-lookup"><span data-stu-id="01619-130">driver's licence number</span></span>  <br/>  <span data-ttu-id="01619-131">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="01619-131">driving license number</span></span>  <br/> <span data-ttu-id="01619-132">dlno #</span><span class="sxs-lookup"><span data-stu-id="01619-132">dlno#</span></span>  <br/> <span data-ttu-id="01619-133">fuhrerschein</span><span class="sxs-lookup"><span data-stu-id="01619-133">fuhrerschein</span></span>  <br/> <span data-ttu-id="01619-134">fuhrerschein Republik Osterreich</span><span class="sxs-lookup"><span data-stu-id="01619-134">fuhrerschein republik osterreich</span></span>  <br/> |
   
## <a name="belgium"></a><span data-ttu-id="01619-135">Belgio</span><span class="sxs-lookup"><span data-stu-id="01619-135">Belgium</span></span>

### <a name="format"></a><span data-ttu-id="01619-136">Formato</span><span class="sxs-lookup"><span data-stu-id="01619-136">Format</span></span>

<span data-ttu-id="01619-137">10 cifre senza spazi e delimitatori</span><span class="sxs-lookup"><span data-stu-id="01619-137">10 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="01619-138">Modello</span><span class="sxs-lookup"><span data-stu-id="01619-138">Pattern</span></span>

<span data-ttu-id="01619-139">10 cifre</span><span class="sxs-lookup"><span data-stu-id="01619-139">10 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="01619-140">Checksum</span><span class="sxs-lookup"><span data-stu-id="01619-140">Checksum</span></span>

<span data-ttu-id="01619-141">No</span><span class="sxs-lookup"><span data-stu-id="01619-141">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="01619-142">Definizione</span><span class="sxs-lookup"><span data-stu-id="01619-142">Definition</span></span>

<span data-ttu-id="01619-143">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="01619-143">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="01619-144">L'espressione `Regex_belgium_eu_driver's_license_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="01619-144">The regular expression  `Regex_belgium_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="01619-145">Viene trovata una `Keywords_belgium_eu_driver's_license_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="01619-145">A keyword from  `Keywords_belgium_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_belgium_eu_driver's_license_number" />
          <Match idRef="Keywords_belgium_eu_driver's_license_number" />
        </Pattern>
</Entity>

```

### <a name="keywords"></a><span data-ttu-id="01619-146">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="01619-146">Keywords</span></span>

<span data-ttu-id="01619-147">| |</span><span class="sxs-lookup"><span data-stu-id="01619-147"></span></span>
|<span data-ttu-id="01619-148">**Keywords__belgium_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="01619-148">**Keywords__belgium_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="01619-149">DL</span><span class="sxs-lookup"><span data-stu-id="01619-149">dl#</span></span>  <br/> <span data-ttu-id="01619-150">patente di guida</span><span class="sxs-lookup"><span data-stu-id="01619-150">driver license</span></span>  <br/> <span data-ttu-id="01619-151">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="01619-151">driver license number</span></span>  <br/> <span data-ttu-id="01619-152">patente di guida</span><span class="sxs-lookup"><span data-stu-id="01619-152">driver licence</span></span>  <br/> <span data-ttu-id="01619-153">driver Lic.</span><span class="sxs-lookup"><span data-stu-id="01619-153">drivers lic.</span></span>  <br/> <span data-ttu-id="01619-154">patente di guida</span><span class="sxs-lookup"><span data-stu-id="01619-154">drivers license</span></span>  <br/> <span data-ttu-id="01619-155">drivers licence</span><span class="sxs-lookup"><span data-stu-id="01619-155">drivers licence</span></span>  <br/> <span data-ttu-id="01619-156">patente di guida</span><span class="sxs-lookup"><span data-stu-id="01619-156">driver's license</span></span>  <br/> <span data-ttu-id="01619-157">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="01619-157">driver's license number</span></span>  <br/> <span data-ttu-id="01619-158">numero di patente del conducente</span><span class="sxs-lookup"><span data-stu-id="01619-158">driver's licence number</span></span>  <br/> <span data-ttu-id="01619-159">dlno #</span><span class="sxs-lookup"><span data-stu-id="01619-159">dlno#</span></span>  <br/> <span data-ttu-id="01619-160">Rijbewijs</span><span class="sxs-lookup"><span data-stu-id="01619-160">rijbewijs</span></span>  <br/> <span data-ttu-id="01619-161">rijbewijsnummer</span><span class="sxs-lookup"><span data-stu-id="01619-161">rijbewijsnummer</span></span>  <br/> <span data-ttu-id="01619-162">führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="01619-162">führerscheinnummer</span></span>  <br/> <span data-ttu-id="01619-163">fuhrerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="01619-163">fuhrerscheinnummer</span></span>  <br/> <span data-ttu-id="01619-164">fuehrerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="01619-164">fuehrerscheinnummer</span></span>  <br/> <span data-ttu-id="01619-165">Führerschein-Nr</span><span class="sxs-lookup"><span data-stu-id="01619-165">führerschein- nr</span></span>  <br/> <span data-ttu-id="01619-166">fuehrerschein-Nr</span><span class="sxs-lookup"><span data-stu-id="01619-166">fuehrerschein- Nr</span></span>  <br/> <span data-ttu-id="01619-167">fuehrerschein-Nr</span><span class="sxs-lookup"><span data-stu-id="01619-167">fuehrerschein- nr</span></span>  <br/> |
   
## <a name="bulgaria"></a><span data-ttu-id="01619-168">Bulgaria</span><span class="sxs-lookup"><span data-stu-id="01619-168">Bulgaria</span></span>

### <a name="format"></a><span data-ttu-id="01619-169">Formato</span><span class="sxs-lookup"><span data-stu-id="01619-169">Format</span></span>

<span data-ttu-id="01619-170">Nove cifre senza spazi e delimitatori</span><span class="sxs-lookup"><span data-stu-id="01619-170">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="01619-171">Modello</span><span class="sxs-lookup"><span data-stu-id="01619-171">Pattern</span></span>

<span data-ttu-id="01619-172">9 cifre</span><span class="sxs-lookup"><span data-stu-id="01619-172">Nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="01619-173">Checksum</span><span class="sxs-lookup"><span data-stu-id="01619-173">Checksum</span></span>

<span data-ttu-id="01619-174">No</span><span class="sxs-lookup"><span data-stu-id="01619-174">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="01619-175">Definizione</span><span class="sxs-lookup"><span data-stu-id="01619-175">Definition</span></span>

<span data-ttu-id="01619-176">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="01619-176">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="01619-177">L'espressione `Regex_bulgaria_eu_driver's_license_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="01619-177">The regular expression  `Regex_bulgaria_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="01619-178">Viene trovata una `Keywords_bulgaria_eu_driver's_license_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="01619-178">A keyword from  `Keywords_bulgaria_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
             <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_bulgaria_eu_driver's_license_number" />
          <Match idRef="Keywords_bulgaria_eu_driver's_license_number" />
        </Pattern> 
</Entity>    

```

### <a name="keywords"></a><span data-ttu-id="01619-179">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="01619-179">Keywords</span></span>

<span data-ttu-id="01619-180">| |</span><span class="sxs-lookup"><span data-stu-id="01619-180"></span></span>
|<span data-ttu-id="01619-181">**Keywords_bulgaria_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="01619-181">**Keywords_bulgaria_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="01619-182">DL</span><span class="sxs-lookup"><span data-stu-id="01619-182">dl#</span></span>  <br/> <span data-ttu-id="01619-183">patente di guida</span><span class="sxs-lookup"><span data-stu-id="01619-183">driver license</span></span>  <br/> <span data-ttu-id="01619-184">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="01619-184">driver license number</span></span>  <br/> <span data-ttu-id="01619-185">patente di guida</span><span class="sxs-lookup"><span data-stu-id="01619-185">driver licence</span></span>  <br/> <span data-ttu-id="01619-186">driver Lic.</span><span class="sxs-lookup"><span data-stu-id="01619-186">drivers lic.</span></span>  <br/> <span data-ttu-id="01619-187">patente di guida</span><span class="sxs-lookup"><span data-stu-id="01619-187">drivers license</span></span>  <br/> <span data-ttu-id="01619-188">drivers licence</span><span class="sxs-lookup"><span data-stu-id="01619-188">drivers licence</span></span>  <br/> <span data-ttu-id="01619-189">patente di guida</span><span class="sxs-lookup"><span data-stu-id="01619-189">driver's license</span></span>  <br/> <span data-ttu-id="01619-190">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="01619-190">driver's license number</span></span>  <br/> <span data-ttu-id="01619-191">numero di patente del conducente</span><span class="sxs-lookup"><span data-stu-id="01619-191">driver's licence number</span></span>  <br/> <span data-ttu-id="01619-192">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="01619-192">driving license number</span></span>  <br/> <span data-ttu-id="01619-193">dlno #</span><span class="sxs-lookup"><span data-stu-id="01619-193">dlno#</span></span>  <br/> <span data-ttu-id="01619-194">свидетелство за управление на мпс</span><span class="sxs-lookup"><span data-stu-id="01619-194">свидетелство за управление на мпс</span></span>  <br/> <span data-ttu-id="01619-195">свидетелство за управление на моторно превозно d'средство</span><span class="sxs-lookup"><span data-stu-id="01619-195">свидетелство за управление на моторно превозно средство</span></span>  <br/> <span data-ttu-id="01619-196">сумпс</span><span class="sxs-lookup"><span data-stu-id="01619-196">сумпс</span></span>  <br/> <span data-ttu-id="01619-197">шофьорска книжка</span><span class="sxs-lookup"><span data-stu-id="01619-197">шофьорска книжка</span></span>  <br/> |
   
## <a name="croatia"></a><span data-ttu-id="01619-198">Croazia</span><span class="sxs-lookup"><span data-stu-id="01619-198">Croatia</span></span>

### <a name="format"></a><span data-ttu-id="01619-199">Formato</span><span class="sxs-lookup"><span data-stu-id="01619-199">Format</span></span>

<span data-ttu-id="01619-200">Otto cifre senza spazi e delimitatori</span><span class="sxs-lookup"><span data-stu-id="01619-200">Eight digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="01619-201">Modello</span><span class="sxs-lookup"><span data-stu-id="01619-201">Pattern</span></span>

<span data-ttu-id="01619-202">Otto cifre</span><span class="sxs-lookup"><span data-stu-id="01619-202">Eight digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="01619-203">Checksum</span><span class="sxs-lookup"><span data-stu-id="01619-203">Checksum</span></span>

<span data-ttu-id="01619-204">No</span><span class="sxs-lookup"><span data-stu-id="01619-204">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="01619-205">Definizione</span><span class="sxs-lookup"><span data-stu-id="01619-205">Definition</span></span>

<span data-ttu-id="01619-206">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="01619-206">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="01619-207">L'espressione `Regex_croatia_eu_driver's_license_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="01619-207">The regular expression  `Regex_croatia_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="01619-208">Viene trovata una `Keywords_croatia_eu_driver's_license_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="01619-208">A keyword from  `Keywords_croatia_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_croatia_eu_driver's_license_number" />
          <Match idRef="Keywords_croatia_eu_driver's_license_number" />
        </Pattern>
</Entity>

```

### <a name="keywords"></a><span data-ttu-id="01619-209">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="01619-209">Keywords</span></span>

<span data-ttu-id="01619-210">| |</span><span class="sxs-lookup"><span data-stu-id="01619-210"></span></span>
|<span data-ttu-id="01619-211">**Keywords_croatia_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="01619-211">**Keywords_croatia_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="01619-212">DL</span><span class="sxs-lookup"><span data-stu-id="01619-212">dl#</span></span>  <br/> <span data-ttu-id="01619-213">patente di guida</span><span class="sxs-lookup"><span data-stu-id="01619-213">driver license</span></span>  <br/> <span data-ttu-id="01619-214">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="01619-214">driver license number</span></span>  <br/> <span data-ttu-id="01619-215">patente di guida</span><span class="sxs-lookup"><span data-stu-id="01619-215">driver licence</span></span>  <br/> <span data-ttu-id="01619-216">driver Lic.</span><span class="sxs-lookup"><span data-stu-id="01619-216">drivers lic.</span></span>  <br/> <span data-ttu-id="01619-217">patente di guida</span><span class="sxs-lookup"><span data-stu-id="01619-217">drivers license</span></span>  <br/> <span data-ttu-id="01619-218">drivers licence</span><span class="sxs-lookup"><span data-stu-id="01619-218">drivers licence</span></span>  <br/> <span data-ttu-id="01619-219">patente di guida</span><span class="sxs-lookup"><span data-stu-id="01619-219">driver's license</span></span>  <br/> <span data-ttu-id="01619-220">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="01619-220">driver's license number</span></span>  <br/> <span data-ttu-id="01619-221">numero di patente del conducente</span><span class="sxs-lookup"><span data-stu-id="01619-221">driver's licence number</span></span>  <br/> <span data-ttu-id="01619-222">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="01619-222">driving license number</span></span>  <br/> <span data-ttu-id="01619-223">dlno #</span><span class="sxs-lookup"><span data-stu-id="01619-223">dlno#</span></span>  <br/> <span data-ttu-id="01619-224">vozačka Dozvola</span><span class="sxs-lookup"><span data-stu-id="01619-224">vozačka dozvola</span></span>  <br/> |
   
## <a name="cyprus"></a><span data-ttu-id="01619-225">Cipro</span><span class="sxs-lookup"><span data-stu-id="01619-225">Cyprus</span></span>

### <a name="format"></a><span data-ttu-id="01619-226">Formato</span><span class="sxs-lookup"><span data-stu-id="01619-226">Format</span></span>

<span data-ttu-id="01619-227">12 cifre senza spazi e delimitatori</span><span class="sxs-lookup"><span data-stu-id="01619-227">12 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="01619-228">Modello</span><span class="sxs-lookup"><span data-stu-id="01619-228">Pattern</span></span>

<span data-ttu-id="01619-229">12 cifre</span><span class="sxs-lookup"><span data-stu-id="01619-229">12 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="01619-230">Checksum</span><span class="sxs-lookup"><span data-stu-id="01619-230">Checksum</span></span>

<span data-ttu-id="01619-231">No</span><span class="sxs-lookup"><span data-stu-id="01619-231">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="01619-232">Definizione</span><span class="sxs-lookup"><span data-stu-id="01619-232">Definition</span></span>

<span data-ttu-id="01619-233">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="01619-233">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="01619-234">L'espressione `Regex_cyprus_eu_driver's_license_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="01619-234">The regular expression  `Regex_cyprus_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="01619-235">Viene trovata una `Keywords_cyprus_eu_driver's_license_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="01619-235">A keyword from  `Keywords_cyprus_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_cyprus_eu_driver's_license_number" />
          <Match idRef="Keywords_cyprus_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="01619-236">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="01619-236">Keywords</span></span>

<span data-ttu-id="01619-237">| |</span><span class="sxs-lookup"><span data-stu-id="01619-237"></span></span>
|<span data-ttu-id="01619-238">**Keywords_cyprus_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="01619-238">**Keywords_cyprus_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="01619-239">DL</span><span class="sxs-lookup"><span data-stu-id="01619-239">dl#</span></span>  <br/> <span data-ttu-id="01619-240">patente di guida</span><span class="sxs-lookup"><span data-stu-id="01619-240">driver license</span></span>  <br/> <span data-ttu-id="01619-241">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="01619-241">driver license number</span></span>  <br/> <span data-ttu-id="01619-242">patente di guida</span><span class="sxs-lookup"><span data-stu-id="01619-242">driver licence</span></span>  <br/> <span data-ttu-id="01619-243">driver Lic.</span><span class="sxs-lookup"><span data-stu-id="01619-243">drivers lic.</span></span>  <br/> <span data-ttu-id="01619-244">patente di guida</span><span class="sxs-lookup"><span data-stu-id="01619-244">drivers license</span></span>  <br/> <span data-ttu-id="01619-245">drivers licence</span><span class="sxs-lookup"><span data-stu-id="01619-245">drivers licence</span></span>  <br/> <span data-ttu-id="01619-246">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="01619-246">driver's license number</span></span>  <br/> <span data-ttu-id="01619-247">numero di patente del conducente</span><span class="sxs-lookup"><span data-stu-id="01619-247">driver's licence number</span></span>  <br/> <span data-ttu-id="01619-248">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="01619-248">driving license number</span></span>  <br/> <span data-ttu-id="01619-249">dlno #</span><span class="sxs-lookup"><span data-stu-id="01619-249">dlno#</span></span>  <br/> <span data-ttu-id="01619-250">άδεια οδήγησης</span><span class="sxs-lookup"><span data-stu-id="01619-250">άδεια οδήγησης</span></span>  <br/> |
   
## <a name="czech-republic"></a><span data-ttu-id="01619-251">Repubblica Ceca</span><span class="sxs-lookup"><span data-stu-id="01619-251">Czech Republic</span></span>

### <a name="format"></a><span data-ttu-id="01619-252">Formato</span><span class="sxs-lookup"><span data-stu-id="01619-252">Format</span></span>

<span data-ttu-id="01619-253">Due lettere seguite da sei cifre</span><span class="sxs-lookup"><span data-stu-id="01619-253">Two letters followed by six digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="01619-254">Modello</span><span class="sxs-lookup"><span data-stu-id="01619-254">Pattern</span></span>

<span data-ttu-id="01619-255">Otto lettere e cifre:</span><span class="sxs-lookup"><span data-stu-id="01619-255">Eight letters and digits:</span></span>
  
- <span data-ttu-id="01619-256">Due lettere (senza distinzione tra maiuscole e minuscole)</span><span class="sxs-lookup"><span data-stu-id="01619-256">Two letters (not case-sensitive)</span></span>
    
- <span data-ttu-id="01619-257">Uno spazio (facoltativo)</span><span class="sxs-lookup"><span data-stu-id="01619-257">A space (optional)</span></span>
    
- <span data-ttu-id="01619-258">Sei cifre</span><span class="sxs-lookup"><span data-stu-id="01619-258">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="01619-259">Checksum</span><span class="sxs-lookup"><span data-stu-id="01619-259">Checksum</span></span>

<span data-ttu-id="01619-260">No</span><span class="sxs-lookup"><span data-stu-id="01619-260">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="01619-261">Definizione</span><span class="sxs-lookup"><span data-stu-id="01619-261">Definition</span></span>

<span data-ttu-id="01619-262">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="01619-262">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="01619-263">L'espressione `Regex_czech_republic_eu_driver's_license_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="01619-263">The regular expression  `Regex_czech_republic_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="01619-264">Viene trovata una `Keywords_czech_republic_eu_driver's_license_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="01619-264">A keyword from  `Keywords_czech_republic_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_czech_republic_eu_driver's_license_number" />
          <Match idRef="Keywords_czech_republic_eu_driver's_license_number" />
        </Pattern>
</Entity>

```

### <a name="keywords"></a><span data-ttu-id="01619-265">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="01619-265">Keywords</span></span>

<span data-ttu-id="01619-266">| |</span><span class="sxs-lookup"><span data-stu-id="01619-266"></span></span>
|<span data-ttu-id="01619-267">**Keywords_czech_republic_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="01619-267">**Keywords_czech_republic_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="01619-268">DL</span><span class="sxs-lookup"><span data-stu-id="01619-268">dl#</span></span>  <br/> <span data-ttu-id="01619-269">patente di guida</span><span class="sxs-lookup"><span data-stu-id="01619-269">driver license</span></span>  <br/> <span data-ttu-id="01619-270">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="01619-270">driver license number</span></span>  <br/> <span data-ttu-id="01619-271">patente di guida</span><span class="sxs-lookup"><span data-stu-id="01619-271">driver licence</span></span>  <br/> <span data-ttu-id="01619-272">driver Lic.</span><span class="sxs-lookup"><span data-stu-id="01619-272">drivers lic.</span></span>  <br/> <span data-ttu-id="01619-273">patente di guida</span><span class="sxs-lookup"><span data-stu-id="01619-273">drivers license</span></span>  <br/> <span data-ttu-id="01619-274">drivers licence</span><span class="sxs-lookup"><span data-stu-id="01619-274">drivers licence</span></span>  <br/> <span data-ttu-id="01619-275">patente di guida</span><span class="sxs-lookup"><span data-stu-id="01619-275">driver's license</span></span>  <br/> <span data-ttu-id="01619-276">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="01619-276">driver's license number</span></span>  <br/> <span data-ttu-id="01619-277">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="01619-277">driver's license number</span></span>  <br/> <span data-ttu-id="01619-278">numero di patente del conducente</span><span class="sxs-lookup"><span data-stu-id="01619-278">driver's licence number</span></span>  <br/> <span data-ttu-id="01619-279">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="01619-279">driving license number</span></span>  <br/> <span data-ttu-id="01619-280">dlno #</span><span class="sxs-lookup"><span data-stu-id="01619-280">dlno#</span></span>  <br/> <span data-ttu-id="01619-281">řidičský prúkaz</span><span class="sxs-lookup"><span data-stu-id="01619-281">řidičský prúkaz</span></span>  <br/> |
   
## <a name="denmark"></a><span data-ttu-id="01619-282">Danimarca</span><span class="sxs-lookup"><span data-stu-id="01619-282">Denmark</span></span>

### <a name="format"></a><span data-ttu-id="01619-283">Formato</span><span class="sxs-lookup"><span data-stu-id="01619-283">Format</span></span>

<span data-ttu-id="01619-284">Otto cifre senza spazi e delimitatori</span><span class="sxs-lookup"><span data-stu-id="01619-284">Eight digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="01619-285">Modello</span><span class="sxs-lookup"><span data-stu-id="01619-285">Pattern</span></span>

<span data-ttu-id="01619-286">Otto cifre</span><span class="sxs-lookup"><span data-stu-id="01619-286">Eight digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="01619-287">Checksum</span><span class="sxs-lookup"><span data-stu-id="01619-287">Checksum</span></span>

<span data-ttu-id="01619-288">Sì</span><span class="sxs-lookup"><span data-stu-id="01619-288">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="01619-289">Definizione</span><span class="sxs-lookup"><span data-stu-id="01619-289">Definition</span></span>

<span data-ttu-id="01619-290">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="01619-290">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="01619-291">L'espressione `Regex_denmark_eu_driver's_license_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="01619-291">The regular expression  `Regex_denmark_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="01619-292">Viene trovata una `Keywords_denmark_eu_driver's_license_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="01619-292">A keyword from  `Keywords_denmark_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_denmark_eu_driver's_license_number" />
          <Match idRef="Keywords_denmark_eu_driver's_license_number" />
        </Pattern>
</Entity>

```

### <a name="keywords"></a><span data-ttu-id="01619-293">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="01619-293">Keywords</span></span>

<span data-ttu-id="01619-294">| |</span><span class="sxs-lookup"><span data-stu-id="01619-294"></span></span>
|<span data-ttu-id="01619-295">**Keywords_denmark_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="01619-295">**Keywords_denmark_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="01619-296">DL</span><span class="sxs-lookup"><span data-stu-id="01619-296">dl#</span></span>  <br/> <span data-ttu-id="01619-297">patente di guida</span><span class="sxs-lookup"><span data-stu-id="01619-297">driver license</span></span>  <br/> <span data-ttu-id="01619-298">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="01619-298">driver license number</span></span>  <br/> <span data-ttu-id="01619-299">patente di guida</span><span class="sxs-lookup"><span data-stu-id="01619-299">driver licence</span></span>  <br/> <span data-ttu-id="01619-300">driver Lic.</span><span class="sxs-lookup"><span data-stu-id="01619-300">drivers lic.</span></span>  <br/> <span data-ttu-id="01619-301">patente di guida</span><span class="sxs-lookup"><span data-stu-id="01619-301">drivers license</span></span>  <br/> <span data-ttu-id="01619-302">drivers licence</span><span class="sxs-lookup"><span data-stu-id="01619-302">drivers licence</span></span>  <br/> <span data-ttu-id="01619-303">patente di guida</span><span class="sxs-lookup"><span data-stu-id="01619-303">driver's license</span></span>  <br/> <span data-ttu-id="01619-304">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="01619-304">driver's license number</span></span>  <br/> <span data-ttu-id="01619-305">numero di patente del conducente</span><span class="sxs-lookup"><span data-stu-id="01619-305">driver's licence number</span></span>  <br/> <span data-ttu-id="01619-306">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="01619-306">driving license number</span></span>  <br/> <span data-ttu-id="01619-307">dlno #</span><span class="sxs-lookup"><span data-stu-id="01619-307">dlno#</span></span>  <br/> <span data-ttu-id="01619-308">kørekort</span><span class="sxs-lookup"><span data-stu-id="01619-308">kørekort</span></span>  <br/> <span data-ttu-id="01619-309">Kørekortnummer</span><span class="sxs-lookup"><span data-stu-id="01619-309">kørekortnummer</span></span>  <br/> |
   
## <a name="estonia"></a><span data-ttu-id="01619-310">Estonia</span><span class="sxs-lookup"><span data-stu-id="01619-310">Estonia</span></span>

### <a name="format"></a><span data-ttu-id="01619-311">Formato</span><span class="sxs-lookup"><span data-stu-id="01619-311">Format</span></span>

<span data-ttu-id="01619-312">Due lettere seguite da sei cifre</span><span class="sxs-lookup"><span data-stu-id="01619-312">Two letters followed by six digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="01619-313">Modello</span><span class="sxs-lookup"><span data-stu-id="01619-313">Pattern</span></span>

<span data-ttu-id="01619-314">Due lettere e sei cifre:</span><span class="sxs-lookup"><span data-stu-id="01619-314">Two letters and six digits:</span></span>
  
-  <span data-ttu-id="01619-315">Lettere "ET" (senza distinzione tra maiuscole e minuscole)</span><span class="sxs-lookup"><span data-stu-id="01619-315">The letters "ET" (not case-sensitive)</span></span> 
    
- <span data-ttu-id="01619-316">Sei cifre</span><span class="sxs-lookup"><span data-stu-id="01619-316">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="01619-317">Checksum</span><span class="sxs-lookup"><span data-stu-id="01619-317">Checksum</span></span>

<span data-ttu-id="01619-318">No</span><span class="sxs-lookup"><span data-stu-id="01619-318">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="01619-319">Definizione</span><span class="sxs-lookup"><span data-stu-id="01619-319">Definition</span></span>

<span data-ttu-id="01619-320">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="01619-320">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="01619-321">L'espressione `Regex_estonia_eu_driver's_license_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="01619-321">The regular expression  `Regex_estonia_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="01619-322">Viene trovata una `Keywords_estonia_eu_driver's_license_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="01619-322">A keyword from  `Keywords_estonia_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_estonia_eu_driver's_license_number" />
          <Match idRef="Keywords_estonia_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="01619-323">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="01619-323">Keywords</span></span>

<span data-ttu-id="01619-324">| |</span><span class="sxs-lookup"><span data-stu-id="01619-324"></span></span>
|<span data-ttu-id="01619-325">**Keywords_estonia_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="01619-325">**Keywords_estonia_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="01619-326">DL</span><span class="sxs-lookup"><span data-stu-id="01619-326">dl#</span></span>  <br/> <span data-ttu-id="01619-327">patente di guida</span><span class="sxs-lookup"><span data-stu-id="01619-327">driver license</span></span>  <br/> <span data-ttu-id="01619-328">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="01619-328">driver license number</span></span>  <br/> <span data-ttu-id="01619-329">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="01619-329">driver license number</span></span>  <br/> <span data-ttu-id="01619-330">patente di guida</span><span class="sxs-lookup"><span data-stu-id="01619-330">driver licence</span></span>  <br/> <span data-ttu-id="01619-331">driver Lic.</span><span class="sxs-lookup"><span data-stu-id="01619-331">drivers lic.</span></span>  <br/> <span data-ttu-id="01619-332">patente di guida</span><span class="sxs-lookup"><span data-stu-id="01619-332">drivers license</span></span>  <br/> <span data-ttu-id="01619-333">drivers licence</span><span class="sxs-lookup"><span data-stu-id="01619-333">drivers licence</span></span>  <br/> <span data-ttu-id="01619-334">patente di guida</span><span class="sxs-lookup"><span data-stu-id="01619-334">driver's license</span></span>  <br/> <span data-ttu-id="01619-335">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="01619-335">driver's license number</span></span>  <br/> <span data-ttu-id="01619-336">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="01619-336">driving license number</span></span>  <br/> <span data-ttu-id="01619-337">dlno #</span><span class="sxs-lookup"><span data-stu-id="01619-337">dlno#</span></span>  <br/> <span data-ttu-id="01619-338">
permis de conduire</span><span class="sxs-lookup"><span data-stu-id="01619-338">permis de conduire</span></span>  <br/> |
   
## <a name="finland"></a><span data-ttu-id="01619-339">Finlandia</span><span class="sxs-lookup"><span data-stu-id="01619-339">Finland</span></span>

### <a name="format"></a><span data-ttu-id="01619-340">Formato</span><span class="sxs-lookup"><span data-stu-id="01619-340">Format</span></span>

<span data-ttu-id="01619-341">10 cifre contenenti una lineetta</span><span class="sxs-lookup"><span data-stu-id="01619-341">10 digits containing a hyphen</span></span>
  
### <a name="pattern"></a><span data-ttu-id="01619-342">Modello</span><span class="sxs-lookup"><span data-stu-id="01619-342">Pattern</span></span>

<span data-ttu-id="01619-343">10 cifre contenenti un trattino:</span><span class="sxs-lookup"><span data-stu-id="01619-343">10 digits containing a hyphen:</span></span>
  
-  <span data-ttu-id="01619-344">Sei cifre</span><span class="sxs-lookup"><span data-stu-id="01619-344">Six digits</span></span> 
    
- <span data-ttu-id="01619-345">Una lineetta</span><span class="sxs-lookup"><span data-stu-id="01619-345">A hyphen</span></span>
    
-  <span data-ttu-id="01619-346">Quattro cifre</span><span class="sxs-lookup"><span data-stu-id="01619-346">Four digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="01619-347">Checksum</span><span class="sxs-lookup"><span data-stu-id="01619-347">Checksum</span></span>

<span data-ttu-id="01619-348">No</span><span class="sxs-lookup"><span data-stu-id="01619-348">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="01619-349">Definizione</span><span class="sxs-lookup"><span data-stu-id="01619-349">Definition</span></span>

<span data-ttu-id="01619-350">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="01619-350">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="01619-351">L'espressione `Regex_finland_eu_driver's_license_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="01619-351">The regular expression  `Regex_finland_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="01619-352">Viene trovata una `Keywords_finland_eu_driver's_license_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="01619-352">A keyword from  `Keywords_finland_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_finland_eu_driver's_license_number" />
          <Match idRef="Keywords_finland_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="01619-353">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="01619-353">Keywords</span></span>

<span data-ttu-id="01619-354">| |</span><span class="sxs-lookup"><span data-stu-id="01619-354"></span></span>
|<span data-ttu-id="01619-355">**Keywords_finland_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="01619-355">**Keywords_finland_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="01619-356">DL</span><span class="sxs-lookup"><span data-stu-id="01619-356">dl#</span></span>  <br/> <span data-ttu-id="01619-357">patente di guida</span><span class="sxs-lookup"><span data-stu-id="01619-357">driver license</span></span>  <br/> <span data-ttu-id="01619-358">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="01619-358">driver license number</span></span>  <br/> <span data-ttu-id="01619-359">patente di guida</span><span class="sxs-lookup"><span data-stu-id="01619-359">driver licence</span></span>  <br/> <span data-ttu-id="01619-360">driver Lic.</span><span class="sxs-lookup"><span data-stu-id="01619-360">drivers lic.</span></span>  <br/> <span data-ttu-id="01619-361">patente di guida</span><span class="sxs-lookup"><span data-stu-id="01619-361">drivers license</span></span>  <br/> <span data-ttu-id="01619-362">drivers licence</span><span class="sxs-lookup"><span data-stu-id="01619-362">drivers licence</span></span>  <br/> <span data-ttu-id="01619-363">patente di guida</span><span class="sxs-lookup"><span data-stu-id="01619-363">driver's license</span></span>  <br/> <span data-ttu-id="01619-364">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="01619-364">driver's license number</span></span>  <br/> <span data-ttu-id="01619-365">numero di patente del conducente</span><span class="sxs-lookup"><span data-stu-id="01619-365">driver's licence number</span></span>  <br/> <span data-ttu-id="01619-366">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="01619-366">driving license number</span></span>  <br/> <span data-ttu-id="01619-367">dlno #</span><span class="sxs-lookup"><span data-stu-id="01619-367">dlno#</span></span>  <br/> <span data-ttu-id="01619-368">AJOKORTTI</span><span class="sxs-lookup"><span data-stu-id="01619-368">ajokortti</span></span>  <br/> |
   
## <a name="france"></a><span data-ttu-id="01619-369">Francia</span><span class="sxs-lookup"><span data-stu-id="01619-369">France</span></span>

<span data-ttu-id="01619-370">Per informazioni dettagliate, vedere la sezione "numero della patente di Francia" in [che cosa cercano i tipi di informazioni riservate](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="01619-370">For details, see the section "France Driver's License Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="germany"></a><span data-ttu-id="01619-371">Germania</span><span class="sxs-lookup"><span data-stu-id="01619-371">Germany</span></span>

<span data-ttu-id="01619-372">Per informazioni dettagliate, vedere la sezione "numero di patente di guida tedesco" in [che cosa cercano i tipi di informazioni riservate](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="01619-372">For details, see the section "German Driver's License Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="greece"></a><span data-ttu-id="01619-373">Grecia</span><span class="sxs-lookup"><span data-stu-id="01619-373">Greece</span></span>

### <a name="format"></a><span data-ttu-id="01619-374">Formato</span><span class="sxs-lookup"><span data-stu-id="01619-374">Format</span></span>

<span data-ttu-id="01619-375">Nove cifre senza spazi e delimitatori</span><span class="sxs-lookup"><span data-stu-id="01619-375">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="01619-376">Modello</span><span class="sxs-lookup"><span data-stu-id="01619-376">Pattern</span></span>

 <span data-ttu-id="01619-377">9 cifre</span><span class="sxs-lookup"><span data-stu-id="01619-377">Nine digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="01619-378">Checksum</span><span class="sxs-lookup"><span data-stu-id="01619-378">Checksum</span></span>

<span data-ttu-id="01619-379">No</span><span class="sxs-lookup"><span data-stu-id="01619-379">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="01619-380">Definizione</span><span class="sxs-lookup"><span data-stu-id="01619-380">Definition</span></span>

<span data-ttu-id="01619-381">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="01619-381">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="01619-382">L'espressione `Regex_greece_eu_driver's_license_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="01619-382">The regular expression  `Regex_greece_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="01619-383">Viene trovata una `Keywords_greece_eu_driver's_license_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="01619-383">A keyword from  `Keywords_greece_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_greece_eu_driver's_license_number" />
          <Match idRef="Keywords_greece_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="01619-384">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="01619-384">Keywords</span></span>

<span data-ttu-id="01619-385">| |</span><span class="sxs-lookup"><span data-stu-id="01619-385"></span></span>
|<span data-ttu-id="01619-386">**Keywords_greece_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="01619-386">**Keywords_greece_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="01619-387">DlL</span><span class="sxs-lookup"><span data-stu-id="01619-387">dlL#</span></span>  <br/> <span data-ttu-id="01619-388">patente di guida</span><span class="sxs-lookup"><span data-stu-id="01619-388">driver license</span></span>  <br/> <span data-ttu-id="01619-389">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="01619-389">driver license number</span></span>  <br/> <span data-ttu-id="01619-390">patente di guida</span><span class="sxs-lookup"><span data-stu-id="01619-390">driver licence</span></span>  <br/> <span data-ttu-id="01619-391">driver Lic.</span><span class="sxs-lookup"><span data-stu-id="01619-391">drivers lic.</span></span>  <br/> <span data-ttu-id="01619-392">patente di guida</span><span class="sxs-lookup"><span data-stu-id="01619-392">drivers license</span></span>  <br/> <span data-ttu-id="01619-393">drivers licence</span><span class="sxs-lookup"><span data-stu-id="01619-393">drivers licence</span></span>  <br/> <span data-ttu-id="01619-394">patente di guida</span><span class="sxs-lookup"><span data-stu-id="01619-394">driver's license</span></span>  <br/> <span data-ttu-id="01619-395">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="01619-395">driver's license number</span></span>  <br/> <span data-ttu-id="01619-396">numero di patente del conducente</span><span class="sxs-lookup"><span data-stu-id="01619-396">driver's licence number</span></span>  <br/> <span data-ttu-id="01619-397">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="01619-397">driving license number</span></span>  <br/> <span data-ttu-id="01619-398">dlno #</span><span class="sxs-lookup"><span data-stu-id="01619-398">dlno#</span></span>  <br/> <span data-ttu-id="01619-399">δεια οδήγησης</span><span class="sxs-lookup"><span data-stu-id="01619-399">δεια οδήγησης</span></span>  <br/> <span data-ttu-id="01619-400">Adeia odigisis</span><span class="sxs-lookup"><span data-stu-id="01619-400">Adeia odigisis</span></span>  <br/> |
   
## <a name="hungary"></a><span data-ttu-id="01619-401">Ungheria</span><span class="sxs-lookup"><span data-stu-id="01619-401">Hungary</span></span>

### <a name="format"></a><span data-ttu-id="01619-402">Formato</span><span class="sxs-lookup"><span data-stu-id="01619-402">Format</span></span>

<span data-ttu-id="01619-403">Due lettere seguite da sei cifre</span><span class="sxs-lookup"><span data-stu-id="01619-403">Two letters followed by six digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="01619-404">Modello</span><span class="sxs-lookup"><span data-stu-id="01619-404">Pattern</span></span>

<span data-ttu-id="01619-405">Due lettere e sei cifre:</span><span class="sxs-lookup"><span data-stu-id="01619-405">Two letters and six digits:</span></span>
  
-  <span data-ttu-id="01619-406">Due lettere (senza distinzione tra maiuscole e minuscole)</span><span class="sxs-lookup"><span data-stu-id="01619-406">Two letters (not case-sensitive)</span></span> 
    
- <span data-ttu-id="01619-407">Sei cifre</span><span class="sxs-lookup"><span data-stu-id="01619-407">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="01619-408">Checksum</span><span class="sxs-lookup"><span data-stu-id="01619-408">Checksum</span></span>

<span data-ttu-id="01619-409">No</span><span class="sxs-lookup"><span data-stu-id="01619-409">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="01619-410">Definizione</span><span class="sxs-lookup"><span data-stu-id="01619-410">Definition</span></span>

<span data-ttu-id="01619-411">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="01619-411">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="01619-412">L'espressione `Regex_hungary_eu_driver's_license_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="01619-412">The regular expression  `Regex_hungary_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="01619-413">Viene trovata una `Keywords_hungary_eu_driver's_license_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="01619-413">A keyword from  `Keywords_hungary_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_hungary_eu_driver's_license_number" />
          <Match idRef="Keywords_hungary_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="01619-414">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="01619-414">Keywords</span></span>

<span data-ttu-id="01619-415">| |</span><span class="sxs-lookup"><span data-stu-id="01619-415"></span></span>
|<span data-ttu-id="01619-416">**Keywords_hungary_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="01619-416">**Keywords_hungary_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="01619-417">DL</span><span class="sxs-lookup"><span data-stu-id="01619-417">dl#</span></span>  <br/> <span data-ttu-id="01619-418">patente di guida</span><span class="sxs-lookup"><span data-stu-id="01619-418">driver license</span></span>  <br/> <span data-ttu-id="01619-419">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="01619-419">driver license number</span></span>  <br/> <span data-ttu-id="01619-420">patente di guida</span><span class="sxs-lookup"><span data-stu-id="01619-420">driver licence</span></span>  <br/> <span data-ttu-id="01619-421">driver Lic.</span><span class="sxs-lookup"><span data-stu-id="01619-421">drivers lic.</span></span>  <br/> <span data-ttu-id="01619-422">patente di guida</span><span class="sxs-lookup"><span data-stu-id="01619-422">drivers license</span></span>  <br/> <span data-ttu-id="01619-423">drivers licence</span><span class="sxs-lookup"><span data-stu-id="01619-423">drivers licence</span></span>  <br/> <span data-ttu-id="01619-424">patente di guida</span><span class="sxs-lookup"><span data-stu-id="01619-424">driver's license</span></span>  <br/> <span data-ttu-id="01619-425">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="01619-425">driver's license number</span></span>  <br/> <span data-ttu-id="01619-426">numero di patente del conducente</span><span class="sxs-lookup"><span data-stu-id="01619-426">driver's licence number</span></span>  <br/> <span data-ttu-id="01619-427">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="01619-427">driving license number</span></span>  <br/> <span data-ttu-id="01619-428">dlno #</span><span class="sxs-lookup"><span data-stu-id="01619-428">dlno#</span></span>  <br/> <span data-ttu-id="01619-429">vezetoi engedely</span><span class="sxs-lookup"><span data-stu-id="01619-429">vezetoi engedely</span></span>  <br/> |
   
## <a name="ireland"></a><span data-ttu-id="01619-430">Irlanda</span><span class="sxs-lookup"><span data-stu-id="01619-430">Ireland</span></span>

### <a name="format"></a><span data-ttu-id="01619-431">Formato</span><span class="sxs-lookup"><span data-stu-id="01619-431">Format</span></span>

<span data-ttu-id="01619-432">Sei cifre seguite da quattro lettere</span><span class="sxs-lookup"><span data-stu-id="01619-432">Six digits followed by four letters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="01619-433">Modello</span><span class="sxs-lookup"><span data-stu-id="01619-433">Pattern</span></span>

<span data-ttu-id="01619-434">Sei cifre e quattro lettere:</span><span class="sxs-lookup"><span data-stu-id="01619-434">Six digits and four letters:</span></span>
  
- <span data-ttu-id="01619-435">Sei cifre</span><span class="sxs-lookup"><span data-stu-id="01619-435">Six digits</span></span>
    
- <span data-ttu-id="01619-436">Quattro lettere (senza distinzione tra maiuscole e minuscole)</span><span class="sxs-lookup"><span data-stu-id="01619-436">Four letters (not case-sensitive)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="01619-437">Checksum</span><span class="sxs-lookup"><span data-stu-id="01619-437">Checksum</span></span>

<span data-ttu-id="01619-438">No</span><span class="sxs-lookup"><span data-stu-id="01619-438">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="01619-439">Definizione</span><span class="sxs-lookup"><span data-stu-id="01619-439">Definition</span></span>

<span data-ttu-id="01619-440">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="01619-440">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="01619-441">L'espressione `Regex_ireland_eu_driver's_license_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="01619-441">The regular expression  `Regex_ireland_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="01619-442">Viene trovata una `Keywords_ireland_eu_driver's_license_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="01619-442">A keyword from  `Keywords_ireland_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_ireland_eu_driver's_license_number" />
          <Match idRef="Keywords_ireland_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="01619-443">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="01619-443">Keywords</span></span>

<span data-ttu-id="01619-444">| |</span><span class="sxs-lookup"><span data-stu-id="01619-444"></span></span>
|<span data-ttu-id="01619-445">**Keywords_ireland_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="01619-445">**Keywords_ireland_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="01619-446">DL</span><span class="sxs-lookup"><span data-stu-id="01619-446">dl#</span></span>  <br/> <span data-ttu-id="01619-447">patente di guida</span><span class="sxs-lookup"><span data-stu-id="01619-447">driver license</span></span>  <br/> <span data-ttu-id="01619-448">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="01619-448">driver license number</span></span>  <br/> <span data-ttu-id="01619-449">patente di guida</span><span class="sxs-lookup"><span data-stu-id="01619-449">driver licence</span></span>  <br/> <span data-ttu-id="01619-450">driver Lic.</span><span class="sxs-lookup"><span data-stu-id="01619-450">drivers lic.</span></span>  <br/> <span data-ttu-id="01619-451">patente di guida</span><span class="sxs-lookup"><span data-stu-id="01619-451">drivers license</span></span>  <br/> <span data-ttu-id="01619-452">drivers licence</span><span class="sxs-lookup"><span data-stu-id="01619-452">drivers licence</span></span>  <br/> <span data-ttu-id="01619-453">patente di guida</span><span class="sxs-lookup"><span data-stu-id="01619-453">driver's license</span></span>  <br/> <span data-ttu-id="01619-454">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="01619-454">driver's license number</span></span>  <br/> <span data-ttu-id="01619-455">numero di patente del conducente</span><span class="sxs-lookup"><span data-stu-id="01619-455">driver's licence number</span></span>  <br/> <span data-ttu-id="01619-456">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="01619-456">driving license number</span></span>  <br/> <span data-ttu-id="01619-457">dlno #</span><span class="sxs-lookup"><span data-stu-id="01619-457">dlno#</span></span>  <br/> <span data-ttu-id="01619-458">Ceadúnas Tiomána</span><span class="sxs-lookup"><span data-stu-id="01619-458">ceadúnas tiomána</span></span>  <br/> |
   
## <a name="italy"></a><span data-ttu-id="01619-459">Italia</span><span class="sxs-lookup"><span data-stu-id="01619-459">Italy</span></span>

<span data-ttu-id="01619-460">Per informazioni dettagliate, vedere la sezione "numero di licenza del conducente italiano" in [che cosa cercano i tipi di informazioni riservate](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="01619-460">For details, see the section "Italy Driver's License Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="latvia"></a><span data-ttu-id="01619-461">Lettonia</span><span class="sxs-lookup"><span data-stu-id="01619-461">Latvia</span></span>

### <a name="format"></a><span data-ttu-id="01619-462">Formato</span><span class="sxs-lookup"><span data-stu-id="01619-462">Format</span></span>

<span data-ttu-id="01619-463">Tre lettere seguite da sei cifre</span><span class="sxs-lookup"><span data-stu-id="01619-463">Three letters followed by six digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="01619-464">Modello</span><span class="sxs-lookup"><span data-stu-id="01619-464">Pattern</span></span>

<span data-ttu-id="01619-465">Tre lettere e sei cifre:</span><span class="sxs-lookup"><span data-stu-id="01619-465">Three letters and six digits:</span></span>
  
-  <span data-ttu-id="01619-466">Tre lettere (senza distinzione tra maiuscole e minuscole)</span><span class="sxs-lookup"><span data-stu-id="01619-466">Three letters (not case-sensitive)</span></span> 
    
- <span data-ttu-id="01619-467">Sei cifre</span><span class="sxs-lookup"><span data-stu-id="01619-467">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="01619-468">Checksum</span><span class="sxs-lookup"><span data-stu-id="01619-468">Checksum</span></span>

<span data-ttu-id="01619-469">No</span><span class="sxs-lookup"><span data-stu-id="01619-469">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="01619-470">Definizione</span><span class="sxs-lookup"><span data-stu-id="01619-470">Definition</span></span>

<span data-ttu-id="01619-471">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="01619-471">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="01619-472">L'espressione `Regex_latvia_eu_driver's_license_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="01619-472">The regular expression  `Regex_latvia_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="01619-473">Viene trovata una `Keywords_latvia_eu_driver's_license_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="01619-473">A keyword from  `Keywords_latvia_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_latvia_eu_driver's_license_number" />
          <Match idRef="Keywords_latvia_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="01619-474">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="01619-474">Keywords</span></span>

<span data-ttu-id="01619-475">| |</span><span class="sxs-lookup"><span data-stu-id="01619-475"></span></span>
|<span data-ttu-id="01619-476">**Keywords_latvia_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="01619-476">**Keywords_latvia_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="01619-477">DL</span><span class="sxs-lookup"><span data-stu-id="01619-477">dl#</span></span>  <br/> <span data-ttu-id="01619-478">patente di guida</span><span class="sxs-lookup"><span data-stu-id="01619-478">driver license</span></span>  <br/> <span data-ttu-id="01619-479">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="01619-479">driver license number</span></span>  <br/> <span data-ttu-id="01619-480">patente di guida</span><span class="sxs-lookup"><span data-stu-id="01619-480">driver licence</span></span>  <br/> <span data-ttu-id="01619-481">driver Lic.</span><span class="sxs-lookup"><span data-stu-id="01619-481">drivers lic.</span></span>  <br/> <span data-ttu-id="01619-482">patente di guida</span><span class="sxs-lookup"><span data-stu-id="01619-482">drivers license</span></span>  <br/> <span data-ttu-id="01619-483">drivers licence</span><span class="sxs-lookup"><span data-stu-id="01619-483">drivers licence</span></span>  <br/> <span data-ttu-id="01619-484">patente di guida</span><span class="sxs-lookup"><span data-stu-id="01619-484">driver's license</span></span>  <br/> <span data-ttu-id="01619-485">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="01619-485">driver's license number</span></span>  <br/> <span data-ttu-id="01619-486">numero di patente del conducente</span><span class="sxs-lookup"><span data-stu-id="01619-486">driver's licence number</span></span>  <br/> <span data-ttu-id="01619-487">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="01619-487">driving license number</span></span>  <br/> <span data-ttu-id="01619-488">dlno #</span><span class="sxs-lookup"><span data-stu-id="01619-488">dlno#</span></span>  <br/> <span data-ttu-id="01619-489">autovadītāja apliecība</span><span class="sxs-lookup"><span data-stu-id="01619-489">autovadītāja apliecība</span></span>  <br/> |
   
## <a name="lithuania"></a><span data-ttu-id="01619-490">Lituania</span><span class="sxs-lookup"><span data-stu-id="01619-490">Lithuania</span></span>

### <a name="format"></a><span data-ttu-id="01619-491">Formato</span><span class="sxs-lookup"><span data-stu-id="01619-491">Format</span></span>

<span data-ttu-id="01619-492">Otto cifre senza spazi e delimitatori</span><span class="sxs-lookup"><span data-stu-id="01619-492">Eight digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="01619-493">Modello</span><span class="sxs-lookup"><span data-stu-id="01619-493">Pattern</span></span>

 <span data-ttu-id="01619-494">Otto cifre</span><span class="sxs-lookup"><span data-stu-id="01619-494">Eight digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="01619-495">Checksum</span><span class="sxs-lookup"><span data-stu-id="01619-495">Checksum</span></span>

<span data-ttu-id="01619-496">No</span><span class="sxs-lookup"><span data-stu-id="01619-496">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="01619-497">Definizione</span><span class="sxs-lookup"><span data-stu-id="01619-497">Definition</span></span>

<span data-ttu-id="01619-498">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="01619-498">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="01619-499">L'espressione `Regex_lithuania_eu_driver's_license_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="01619-499">The regular expression  `Regex_lithuania_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="01619-500">Viene trovata una `Keywords_lithuania_eu_driver's_license_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="01619-500">A keyword from  `Keywords_lithuania_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_lithuania_eu_driver's_license_number" />
          <Match idRef="Keywords_lithuania_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="01619-501">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="01619-501">Keywords</span></span>

<span data-ttu-id="01619-502">| |</span><span class="sxs-lookup"><span data-stu-id="01619-502"></span></span>
|<span data-ttu-id="01619-503">**Keywords_lithuania_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="01619-503">**Keywords_lithuania_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="01619-504">DL</span><span class="sxs-lookup"><span data-stu-id="01619-504">dl#</span></span>  <br/> <span data-ttu-id="01619-505">patente di guida</span><span class="sxs-lookup"><span data-stu-id="01619-505">driver license</span></span>  <br/> <span data-ttu-id="01619-506">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="01619-506">driver license number</span></span>  <br/> <span data-ttu-id="01619-507">patente di guida</span><span class="sxs-lookup"><span data-stu-id="01619-507">driver licence</span></span>  <br/> <span data-ttu-id="01619-508">driver Lic.</span><span class="sxs-lookup"><span data-stu-id="01619-508">drivers lic.</span></span>  <br/> <span data-ttu-id="01619-509">patente di guida</span><span class="sxs-lookup"><span data-stu-id="01619-509">drivers license</span></span>  <br/> <span data-ttu-id="01619-510">drivers licence</span><span class="sxs-lookup"><span data-stu-id="01619-510">drivers licence</span></span>  <br/> <span data-ttu-id="01619-511">patente di guida</span><span class="sxs-lookup"><span data-stu-id="01619-511">driver's license</span></span>  <br/> <span data-ttu-id="01619-512">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="01619-512">driver's license number</span></span>  <br/> <span data-ttu-id="01619-513">numero di patente del conducente</span><span class="sxs-lookup"><span data-stu-id="01619-513">driver's licence number</span></span>  <br/> <span data-ttu-id="01619-514">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="01619-514">driving license number</span></span>  <br/> <span data-ttu-id="01619-515">dlno #</span><span class="sxs-lookup"><span data-stu-id="01619-515">dlno#</span></span>  <br/> <span data-ttu-id="01619-516">vairuotojo pažymėjimas</span><span class="sxs-lookup"><span data-stu-id="01619-516">vairuotojo pažymėjimas</span></span>  <br/> |
   
## <a name="luxemburg"></a><span data-ttu-id="01619-517">Lussemburgo</span><span class="sxs-lookup"><span data-stu-id="01619-517">Luxemburg</span></span>

### <a name="format"></a><span data-ttu-id="01619-518">Formato</span><span class="sxs-lookup"><span data-stu-id="01619-518">Format</span></span>

<span data-ttu-id="01619-519">Sei cifre senza spazi e delimitatori</span><span class="sxs-lookup"><span data-stu-id="01619-519">Six digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="01619-520">Modello</span><span class="sxs-lookup"><span data-stu-id="01619-520">Pattern</span></span>

 <span data-ttu-id="01619-521">Sei cifre</span><span class="sxs-lookup"><span data-stu-id="01619-521">Six digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="01619-522">Checksum</span><span class="sxs-lookup"><span data-stu-id="01619-522">Checksum</span></span>

<span data-ttu-id="01619-523">No</span><span class="sxs-lookup"><span data-stu-id="01619-523">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="01619-524">Definizione</span><span class="sxs-lookup"><span data-stu-id="01619-524">Definition</span></span>

<span data-ttu-id="01619-525">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="01619-525">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="01619-526">L'espressione `Regex_luxemburg_eu_driver's_license_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="01619-526">The regular expression  `Regex_luxemburg_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="01619-527">Viene trovata una `Keywords_luxemburg_eu_driver's_license_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="01619-527">A keyword from  `Keywords_luxemburg_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_luxemburg_eu_driver's_license_number" />
          <Match idRef="Keywords_luxemburg_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="01619-528">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="01619-528">Keywords</span></span>

<span data-ttu-id="01619-529">| |</span><span class="sxs-lookup"><span data-stu-id="01619-529"></span></span>
|<span data-ttu-id="01619-530">**Keywords_luxemburg_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="01619-530">**Keywords_luxemburg_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="01619-531">DL</span><span class="sxs-lookup"><span data-stu-id="01619-531">dl#</span></span>  <br/> <span data-ttu-id="01619-532">patente di guida</span><span class="sxs-lookup"><span data-stu-id="01619-532">driver license</span></span>  <br/> <span data-ttu-id="01619-533">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="01619-533">driver license number</span></span>  <br/> <span data-ttu-id="01619-534">patente di guida</span><span class="sxs-lookup"><span data-stu-id="01619-534">driver licence</span></span>  <br/> <span data-ttu-id="01619-535">driver Lic.</span><span class="sxs-lookup"><span data-stu-id="01619-535">drivers lic.</span></span>  <br/> <span data-ttu-id="01619-536">patente di guida</span><span class="sxs-lookup"><span data-stu-id="01619-536">drivers license</span></span>  <br/> <span data-ttu-id="01619-537">drivers licence</span><span class="sxs-lookup"><span data-stu-id="01619-537">drivers licence</span></span>  <br/> <span data-ttu-id="01619-538">patente di guida</span><span class="sxs-lookup"><span data-stu-id="01619-538">driver's license</span></span>  <br/> <span data-ttu-id="01619-539">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="01619-539">driver's license number</span></span>  <br/> <span data-ttu-id="01619-540">numero di patente del conducente</span><span class="sxs-lookup"><span data-stu-id="01619-540">driver's licence number</span></span>  <br/> <span data-ttu-id="01619-541">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="01619-541">driving license number</span></span>  <br/> <span data-ttu-id="01619-542">dlno #</span><span class="sxs-lookup"><span data-stu-id="01619-542">dlno#</span></span>  <br/> <span data-ttu-id="01619-543">fahrerlaubnis</span><span class="sxs-lookup"><span data-stu-id="01619-543">fahrerlaubnis</span></span>  <br/> |
   
## <a name="malta"></a><span data-ttu-id="01619-544">Malta</span><span class="sxs-lookup"><span data-stu-id="01619-544">Malta</span></span>

### <a name="format"></a><span data-ttu-id="01619-545">Formato</span><span class="sxs-lookup"><span data-stu-id="01619-545">Format</span></span>

<span data-ttu-id="01619-546">Combinazione di due caratteri e di sei cifre nel modello specificato</span><span class="sxs-lookup"><span data-stu-id="01619-546">Combination of two characters and six digits in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="01619-547">Modello</span><span class="sxs-lookup"><span data-stu-id="01619-547">Pattern</span></span>

<span data-ttu-id="01619-548">Combinazione di due caratteri e di sei cifre:</span><span class="sxs-lookup"><span data-stu-id="01619-548">Combination of two characters and six digits:</span></span>
  
- <span data-ttu-id="01619-549">Due caratteri (cifre o lettere, non con distinzione tra maiuscole e minuscole)</span><span class="sxs-lookup"><span data-stu-id="01619-549">Two characters (digits or letters, not case-sensitive)</span></span>
    
- <span data-ttu-id="01619-550">Uno spazio (facoltativo)</span><span class="sxs-lookup"><span data-stu-id="01619-550">A space (optional)</span></span>
    
- <span data-ttu-id="01619-551">Tre cifre</span><span class="sxs-lookup"><span data-stu-id="01619-551">Three digits</span></span>
    
- <span data-ttu-id="01619-552">Uno spazio (facoltativo)</span><span class="sxs-lookup"><span data-stu-id="01619-552">A space (optional)</span></span>
    
- <span data-ttu-id="01619-553">Tre cifre</span><span class="sxs-lookup"><span data-stu-id="01619-553">Three digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="01619-554">Checksum</span><span class="sxs-lookup"><span data-stu-id="01619-554">Checksum</span></span>

<span data-ttu-id="01619-555">No</span><span class="sxs-lookup"><span data-stu-id="01619-555">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="01619-556">Definizione</span><span class="sxs-lookup"><span data-stu-id="01619-556">Definition</span></span>

<span data-ttu-id="01619-557">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="01619-557">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="01619-558">L'espressione `Regex_malta_eu_driver's_license_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="01619-558">The regular expression  `Regex_malta_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="01619-559">Viene trovata una `Keywords_malta_eu_driver's_license_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="01619-559">A keyword from  `Keywords_malta_eu_driver's_license_number` is found.</span></span> 
    
```
<!-- EU Driver's License Number -->
 <Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_malta_eu_driver's_license_number" />
          <Match idRef="Keywords_malta_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="01619-560">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="01619-560">Keywords</span></span>

<span data-ttu-id="01619-561">| |</span><span class="sxs-lookup"><span data-stu-id="01619-561"></span></span>
|<span data-ttu-id="01619-562">**Keywords_malta_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="01619-562">**Keywords_malta_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="01619-563">DL</span><span class="sxs-lookup"><span data-stu-id="01619-563">dl#</span></span>  <br/> <span data-ttu-id="01619-564">patente di guida</span><span class="sxs-lookup"><span data-stu-id="01619-564">driver license</span></span>  <br/> <span data-ttu-id="01619-565">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="01619-565">driver license number</span></span>  <br/> <span data-ttu-id="01619-566">patente di guida</span><span class="sxs-lookup"><span data-stu-id="01619-566">driver licence</span></span>  <br/> <span data-ttu-id="01619-567">driver Lic.</span><span class="sxs-lookup"><span data-stu-id="01619-567">drivers lic.</span></span>  <br/> <span data-ttu-id="01619-568">patente di guida</span><span class="sxs-lookup"><span data-stu-id="01619-568">drivers license</span></span>  <br/> <span data-ttu-id="01619-569">drivers licence</span><span class="sxs-lookup"><span data-stu-id="01619-569">drivers licence</span></span>  <br/> <span data-ttu-id="01619-570">patente di guida</span><span class="sxs-lookup"><span data-stu-id="01619-570">driver's license</span></span>  <br/> <span data-ttu-id="01619-571">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="01619-571">driver's license number</span></span>  <br/> <span data-ttu-id="01619-572">numero di patente del conducente</span><span class="sxs-lookup"><span data-stu-id="01619-572">driver's licence number</span></span>  <br/> <span data-ttu-id="01619-573">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="01619-573">driving license number</span></span>  <br/> <span data-ttu-id="01619-574">dlno #</span><span class="sxs-lookup"><span data-stu-id="01619-574">dlno#</span></span>  <br/> <span data-ttu-id="01619-575">Liċenzja TAS-sewqan</span><span class="sxs-lookup"><span data-stu-id="01619-575">liċenzja tas-sewqan</span></span>  <br/> |
   
## <a name="netherlands"></a><span data-ttu-id="01619-576">Paesi Bassi</span><span class="sxs-lookup"><span data-stu-id="01619-576">Netherlands</span></span>

### <a name="format"></a><span data-ttu-id="01619-577">Formato</span><span class="sxs-lookup"><span data-stu-id="01619-577">Format</span></span>

<span data-ttu-id="01619-578">10 cifre senza spazi e delimitatori</span><span class="sxs-lookup"><span data-stu-id="01619-578">10 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="01619-579">Modello</span><span class="sxs-lookup"><span data-stu-id="01619-579">Pattern</span></span>

<span data-ttu-id="01619-580">10 cifre</span><span class="sxs-lookup"><span data-stu-id="01619-580">10 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="01619-581">Checksum</span><span class="sxs-lookup"><span data-stu-id="01619-581">Checksum</span></span>

<span data-ttu-id="01619-582">No</span><span class="sxs-lookup"><span data-stu-id="01619-582">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="01619-583">Definizione</span><span class="sxs-lookup"><span data-stu-id="01619-583">Definition</span></span>

<span data-ttu-id="01619-584">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="01619-584">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="01619-585">L'espressione `Regex_netherlands_eu_driver's_license_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="01619-585">The regular expression  `Regex_netherlands_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="01619-586">Viene trovata una `Keywords_netherlands_eu_driver's_license_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="01619-586">A keyword from  `Keywords_netherlands_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_netherlands_eu_driver's_license_number" />
          <Match idRef="Keywords_netherlands_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="01619-587">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="01619-587">Keywords</span></span>

<span data-ttu-id="01619-588">| |</span><span class="sxs-lookup"><span data-stu-id="01619-588"></span></span>
|<span data-ttu-id="01619-589">**Keywords_netherlands_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="01619-589">**Keywords_netherlands_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="01619-590">DL</span><span class="sxs-lookup"><span data-stu-id="01619-590">dl#</span></span>  <br/> <span data-ttu-id="01619-591">patente di guida</span><span class="sxs-lookup"><span data-stu-id="01619-591">driver license</span></span>  <br/> <span data-ttu-id="01619-592">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="01619-592">driver license number</span></span>  <br/> <span data-ttu-id="01619-593">patente di guida</span><span class="sxs-lookup"><span data-stu-id="01619-593">driver licence</span></span>  <br/> <span data-ttu-id="01619-594">driver Lic.</span><span class="sxs-lookup"><span data-stu-id="01619-594">drivers lic.</span></span>  <br/> <span data-ttu-id="01619-595">patente di guida</span><span class="sxs-lookup"><span data-stu-id="01619-595">drivers license</span></span>  <br/> <span data-ttu-id="01619-596">drivers licence</span><span class="sxs-lookup"><span data-stu-id="01619-596">drivers licence</span></span>  <br/> <span data-ttu-id="01619-597">patente di guida</span><span class="sxs-lookup"><span data-stu-id="01619-597">driver's license</span></span>  <br/> <span data-ttu-id="01619-598">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="01619-598">driver's license number</span></span>  <br/> <span data-ttu-id="01619-599">numero di patente del conducente</span><span class="sxs-lookup"><span data-stu-id="01619-599">driver's licence number</span></span>  <br/> <span data-ttu-id="01619-600">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="01619-600">driving license number</span></span>  <br/> <span data-ttu-id="01619-601">dlno #</span><span class="sxs-lookup"><span data-stu-id="01619-601">dlno#</span></span>  <br/> <span data-ttu-id="01619-602">
permis de conduire</span><span class="sxs-lookup"><span data-stu-id="01619-602">permis de conduire</span></span>  <br/> <span data-ttu-id="01619-603">Rijbewijs</span><span class="sxs-lookup"><span data-stu-id="01619-603">rijbewijs</span></span>  <br/> <span data-ttu-id="01619-604">rijbewijsnummer</span><span class="sxs-lookup"><span data-stu-id="01619-604">rijbewijsnummer</span></span>  <br/> |
   
## <a name="poland"></a><span data-ttu-id="01619-605">Polonia</span><span class="sxs-lookup"><span data-stu-id="01619-605">Poland</span></span>

### <a name="format"></a><span data-ttu-id="01619-606">Formato</span><span class="sxs-lookup"><span data-stu-id="01619-606">Format</span></span>

<span data-ttu-id="01619-607">14 cifre contenenti 2 barre</span><span class="sxs-lookup"><span data-stu-id="01619-607">14 digits containing 2 forward slashes</span></span>
  
### <a name="pattern"></a><span data-ttu-id="01619-608">Modello</span><span class="sxs-lookup"><span data-stu-id="01619-608">Pattern</span></span>

<span data-ttu-id="01619-609">14 cifre e 2 barre:</span><span class="sxs-lookup"><span data-stu-id="01619-609">14 digits and 2 forward slashes:</span></span>
  
-  <span data-ttu-id="01619-610">Cinque cifre</span><span class="sxs-lookup"><span data-stu-id="01619-610">Five digits</span></span> 
    
- <span data-ttu-id="01619-611">Una barra</span><span class="sxs-lookup"><span data-stu-id="01619-611">A forward slash</span></span>
    
- <span data-ttu-id="01619-612">Due cifre</span><span class="sxs-lookup"><span data-stu-id="01619-612">Two digits</span></span>
    
- <span data-ttu-id="01619-613">Una barra</span><span class="sxs-lookup"><span data-stu-id="01619-613">A forward slash</span></span>
    
- <span data-ttu-id="01619-614">Sette cifre</span><span class="sxs-lookup"><span data-stu-id="01619-614">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="01619-615">Checksum</span><span class="sxs-lookup"><span data-stu-id="01619-615">Checksum</span></span>

<span data-ttu-id="01619-616">No</span><span class="sxs-lookup"><span data-stu-id="01619-616">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="01619-617">Definizione</span><span class="sxs-lookup"><span data-stu-id="01619-617">Definition</span></span>

<span data-ttu-id="01619-618">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="01619-618">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="01619-619">L'espressione `Regex_poland_eu_driver's_license_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="01619-619">The regular expression  `Regex_poland_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="01619-620">Viene trovata una `Keywords_poland_eu_driver's_license_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="01619-620">A keyword from  `Keywords_poland_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_poland_eu_driver's_license_number" />
          <Match idRef="Keywords_poland_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="01619-621">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="01619-621">Keywords</span></span>

<span data-ttu-id="01619-622">| |</span><span class="sxs-lookup"><span data-stu-id="01619-622"></span></span>
|<span data-ttu-id="01619-623">**Keywords_poland_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="01619-623">**Keywords_poland_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="01619-624">DL</span><span class="sxs-lookup"><span data-stu-id="01619-624">dl#</span></span>  <br/> <span data-ttu-id="01619-625">patente di guida</span><span class="sxs-lookup"><span data-stu-id="01619-625">driver license</span></span>  <br/> <span data-ttu-id="01619-626">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="01619-626">driver license number</span></span>  <br/> <span data-ttu-id="01619-627">patente di guida</span><span class="sxs-lookup"><span data-stu-id="01619-627">driver licence</span></span>  <br/> <span data-ttu-id="01619-628">driver Lic.</span><span class="sxs-lookup"><span data-stu-id="01619-628">drivers lic.</span></span>  <br/> <span data-ttu-id="01619-629">patente di guida</span><span class="sxs-lookup"><span data-stu-id="01619-629">drivers license</span></span>  <br/> <span data-ttu-id="01619-630">drivers licence</span><span class="sxs-lookup"><span data-stu-id="01619-630">drivers licence</span></span>  <br/> <span data-ttu-id="01619-631">patente di guida</span><span class="sxs-lookup"><span data-stu-id="01619-631">driver's license</span></span>  <br/> <span data-ttu-id="01619-632">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="01619-632">driver's license number</span></span>  <br/> <span data-ttu-id="01619-633">numero di patente del conducente</span><span class="sxs-lookup"><span data-stu-id="01619-633">driver's licence number</span></span>  <br/> <span data-ttu-id="01619-634">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="01619-634">driving license number</span></span>  <br/> <span data-ttu-id="01619-635">dlno #</span><span class="sxs-lookup"><span data-stu-id="01619-635">dlno#</span></span>  <br/> <span data-ttu-id="01619-636">prawo jazdy</span><span class="sxs-lookup"><span data-stu-id="01619-636">prawo jazdy</span></span>  <br/> |
   
## <a name="portugal"></a><span data-ttu-id="01619-637">Portogallo</span><span class="sxs-lookup"><span data-stu-id="01619-637">Portugal</span></span>

### <a name="format"></a><span data-ttu-id="01619-638">Formato</span><span class="sxs-lookup"><span data-stu-id="01619-638">Format</span></span>

<span data-ttu-id="01619-639">Due lettere seguite da un numero di sette numeri nel modello specificato</span><span class="sxs-lookup"><span data-stu-id="01619-639">Two letters followed by a seven numbers in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="01619-640">Modello</span><span class="sxs-lookup"><span data-stu-id="01619-640">Pattern</span></span>

<span data-ttu-id="01619-641">Due lettere seguite da sette numeri con caratteri speciali:</span><span class="sxs-lookup"><span data-stu-id="01619-641">Two letters followed by seven numbers with special characters:</span></span>
  
-  <span data-ttu-id="01619-642">Due lettere (senza distinzione tra maiuscole e minuscole)</span><span class="sxs-lookup"><span data-stu-id="01619-642">Two letters (not case-sensitive)</span></span> 
    
- <span data-ttu-id="01619-643">Una lineetta</span><span class="sxs-lookup"><span data-stu-id="01619-643">A hyphen</span></span>
    
- <span data-ttu-id="01619-644">Sei cifre</span><span class="sxs-lookup"><span data-stu-id="01619-644">Six digits</span></span>
    
- <span data-ttu-id="01619-645">Uno spazio</span><span class="sxs-lookup"><span data-stu-id="01619-645">A space</span></span>
    
- <span data-ttu-id="01619-646">Una cifra</span><span class="sxs-lookup"><span data-stu-id="01619-646">One digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="01619-647">Checksum</span><span class="sxs-lookup"><span data-stu-id="01619-647">Checksum</span></span>

<span data-ttu-id="01619-648">No</span><span class="sxs-lookup"><span data-stu-id="01619-648">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="01619-649">Definizione</span><span class="sxs-lookup"><span data-stu-id="01619-649">Definition</span></span>

<span data-ttu-id="01619-650">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="01619-650">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="01619-651">L'espressione `Regex_portugal_eu_driver's_license_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="01619-651">The regular expression  `Regex_portugal_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="01619-652">Viene trovata una `Keywords_portugal_eu_driver's_license_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="01619-652">A keyword from  `Keywords_portugal_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_portugal_eu_driver's_license_number" />
          <Match idRef="Keywords_portugal_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="01619-653">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="01619-653">Keywords</span></span>

<span data-ttu-id="01619-654">| |</span><span class="sxs-lookup"><span data-stu-id="01619-654"></span></span>
|<span data-ttu-id="01619-655">**Keywords_portugal_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="01619-655">**Keywords_portugal_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="01619-656">DL</span><span class="sxs-lookup"><span data-stu-id="01619-656">dl#</span></span>  <br/> <span data-ttu-id="01619-657">patente di guida</span><span class="sxs-lookup"><span data-stu-id="01619-657">driver license</span></span>  <br/> <span data-ttu-id="01619-658">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="01619-658">driver license number</span></span>  <br/> <span data-ttu-id="01619-659">patente di guida</span><span class="sxs-lookup"><span data-stu-id="01619-659">driver licence</span></span>  <br/> <span data-ttu-id="01619-660">driver Lic.</span><span class="sxs-lookup"><span data-stu-id="01619-660">drivers lic.</span></span>  <br/> <span data-ttu-id="01619-661">patente di guida</span><span class="sxs-lookup"><span data-stu-id="01619-661">drivers license</span></span>  <br/> <span data-ttu-id="01619-662">drivers licence</span><span class="sxs-lookup"><span data-stu-id="01619-662">drivers licence</span></span>  <br/> <span data-ttu-id="01619-663">patente di guida</span><span class="sxs-lookup"><span data-stu-id="01619-663">driver's license</span></span>  <br/> <span data-ttu-id="01619-664">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="01619-664">driver's license number</span></span>  <br/> <span data-ttu-id="01619-665">numero di patente del conducente</span><span class="sxs-lookup"><span data-stu-id="01619-665">driver's licence number</span></span>  <br/> <span data-ttu-id="01619-666">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="01619-666">driving license number</span></span>  <br/> <span data-ttu-id="01619-667">dlno #</span><span class="sxs-lookup"><span data-stu-id="01619-667">dlno#</span></span>  <br/> <span data-ttu-id="01619-668">carteira de motorista</span><span class="sxs-lookup"><span data-stu-id="01619-668">carteira de motorista</span></span>  <br/> |
   
## <a name="romania"></a><span data-ttu-id="01619-669">Romania</span><span class="sxs-lookup"><span data-stu-id="01619-669">Romania</span></span>

### <a name="format"></a><span data-ttu-id="01619-670">Formato</span><span class="sxs-lookup"><span data-stu-id="01619-670">Format</span></span>

<span data-ttu-id="01619-671">Un carattere seguito da otto cifre</span><span class="sxs-lookup"><span data-stu-id="01619-671">One character followed by eight digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="01619-672">Modello</span><span class="sxs-lookup"><span data-stu-id="01619-672">Pattern</span></span>

<span data-ttu-id="01619-673">Un carattere seguito da otto cifre:</span><span class="sxs-lookup"><span data-stu-id="01619-673">One character followed by eight digits:</span></span>
  
-  <span data-ttu-id="01619-674">Una lettera (senza distinzione tra maiuscole e minuscole) o cifra</span><span class="sxs-lookup"><span data-stu-id="01619-674">One letter (not case-sensitive) or digit</span></span> 
    
- <span data-ttu-id="01619-675">Otto cifre</span><span class="sxs-lookup"><span data-stu-id="01619-675">Eight digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="01619-676">Checksum</span><span class="sxs-lookup"><span data-stu-id="01619-676">Checksum</span></span>

<span data-ttu-id="01619-677">No</span><span class="sxs-lookup"><span data-stu-id="01619-677">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="01619-678">Definizione</span><span class="sxs-lookup"><span data-stu-id="01619-678">Definition</span></span>

<span data-ttu-id="01619-679">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="01619-679">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="01619-680">L'espressione `Regex_romania_eu_driver's_license_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="01619-680">The regular expression  `Regex_romania_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="01619-681">Viene trovata una `Keywords_romania_eu_driver's_license_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="01619-681">A keyword from  `Keywords_romania_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_romania_eu_driver's_license_number" />
          <Match idRef="Keywords_romania_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="01619-682">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="01619-682">Keywords</span></span>

<span data-ttu-id="01619-683">| |</span><span class="sxs-lookup"><span data-stu-id="01619-683"></span></span>
|<span data-ttu-id="01619-684">**Keywords_romania_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="01619-684">**Keywords_romania_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="01619-685">DL</span><span class="sxs-lookup"><span data-stu-id="01619-685">dl#</span></span>  <br/> <span data-ttu-id="01619-686">patente di guida</span><span class="sxs-lookup"><span data-stu-id="01619-686">driver license</span></span>  <br/> <span data-ttu-id="01619-687">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="01619-687">driver license number</span></span>  <br/> <span data-ttu-id="01619-688">patente di guida</span><span class="sxs-lookup"><span data-stu-id="01619-688">driver licence</span></span>  <br/> <span data-ttu-id="01619-689">driver Lic.</span><span class="sxs-lookup"><span data-stu-id="01619-689">drivers lic.</span></span>  <br/> <span data-ttu-id="01619-690">patente di guida</span><span class="sxs-lookup"><span data-stu-id="01619-690">drivers license</span></span>  <br/> <span data-ttu-id="01619-691">drivers licence</span><span class="sxs-lookup"><span data-stu-id="01619-691">drivers licence</span></span>  <br/> <span data-ttu-id="01619-692">patente di guida</span><span class="sxs-lookup"><span data-stu-id="01619-692">driver's license</span></span>  <br/> <span data-ttu-id="01619-693">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="01619-693">driver's license number</span></span>  <br/> <span data-ttu-id="01619-694">numero di patente del conducente</span><span class="sxs-lookup"><span data-stu-id="01619-694">driver's licence number</span></span>  <br/> <span data-ttu-id="01619-695">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="01619-695">driving license number</span></span>  <br/> <span data-ttu-id="01619-696">dlno #</span><span class="sxs-lookup"><span data-stu-id="01619-696">dlno#</span></span>  <br/> <span data-ttu-id="01619-697">Permis de conducere</span><span class="sxs-lookup"><span data-stu-id="01619-697">permis de conducere</span></span>  <br/> |
   
## <a name="slovakia"></a><span data-ttu-id="01619-698">Slovacchia</span><span class="sxs-lookup"><span data-stu-id="01619-698">Slovakia</span></span>

### <a name="format"></a><span data-ttu-id="01619-699">Formato</span><span class="sxs-lookup"><span data-stu-id="01619-699">Format</span></span>

<span data-ttu-id="01619-700">Un carattere seguito da sette cifre</span><span class="sxs-lookup"><span data-stu-id="01619-700">One character followed by seven digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="01619-701">Modello</span><span class="sxs-lookup"><span data-stu-id="01619-701">Pattern</span></span>

<span data-ttu-id="01619-702">Un carattere seguito da sette cifre</span><span class="sxs-lookup"><span data-stu-id="01619-702">One character followed by seven digits</span></span>
  
- <span data-ttu-id="01619-703">Una lettera (senza distinzione tra maiuscole e minuscole) o cifra</span><span class="sxs-lookup"><span data-stu-id="01619-703">One letter (not case-sensitive) or digit</span></span>
    
-  <span data-ttu-id="01619-704">Sette cifre</span><span class="sxs-lookup"><span data-stu-id="01619-704">Seven digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="01619-705">Checksum</span><span class="sxs-lookup"><span data-stu-id="01619-705">Checksum</span></span>

<span data-ttu-id="01619-706">No</span><span class="sxs-lookup"><span data-stu-id="01619-706">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="01619-707">Definizione</span><span class="sxs-lookup"><span data-stu-id="01619-707">Definition</span></span>

<span data-ttu-id="01619-708">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="01619-708">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="01619-709">L'espressione `Regex_slovakia_eu_driver's_license_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="01619-709">The regular expression  `Regex_slovakia_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="01619-710">Viene trovata una `Keywords_slovakia_eu_driver's_license_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="01619-710">A keyword from  `Keywords_slovakia_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovaknia_eu_driver's_license_number" />
          <Match idRef="Keywords_slovakia_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="01619-711">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="01619-711">Keywords</span></span>

<span data-ttu-id="01619-712">| |</span><span class="sxs-lookup"><span data-stu-id="01619-712"></span></span>
|<span data-ttu-id="01619-713">**Keywords_slovakia_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="01619-713">**Keywords_slovakia_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="01619-714">DL</span><span class="sxs-lookup"><span data-stu-id="01619-714">dl#</span></span>  <br/> <span data-ttu-id="01619-715">patente di guida</span><span class="sxs-lookup"><span data-stu-id="01619-715">driver license</span></span>  <br/> <span data-ttu-id="01619-716">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="01619-716">driver license number</span></span>  <br/> <span data-ttu-id="01619-717">patente di guida</span><span class="sxs-lookup"><span data-stu-id="01619-717">driver licence</span></span>  <br/> <span data-ttu-id="01619-718">driver Lic.</span><span class="sxs-lookup"><span data-stu-id="01619-718">drivers lic.</span></span>  <br/> <span data-ttu-id="01619-719">patente di guida</span><span class="sxs-lookup"><span data-stu-id="01619-719">drivers license</span></span>  <br/> <span data-ttu-id="01619-720">drivers licence</span><span class="sxs-lookup"><span data-stu-id="01619-720">drivers licence</span></span>  <br/> <span data-ttu-id="01619-721">patente di guida</span><span class="sxs-lookup"><span data-stu-id="01619-721">driver's license</span></span>  <br/> <span data-ttu-id="01619-722">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="01619-722">driver's license number</span></span>  <br/> <span data-ttu-id="01619-723">numero di patente del conducente</span><span class="sxs-lookup"><span data-stu-id="01619-723">driver's licence number</span></span>  <br/> <span data-ttu-id="01619-724">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="01619-724">driving license number</span></span>  <br/> <span data-ttu-id="01619-725">dlno #</span><span class="sxs-lookup"><span data-stu-id="01619-725">dlno#</span></span>  <br/> <span data-ttu-id="01619-726">vodičský preukaz</span><span class="sxs-lookup"><span data-stu-id="01619-726">vodičský preukaz</span></span>  <br/> |
   
## <a name="slovenia"></a><span data-ttu-id="01619-727">Slovenia</span><span class="sxs-lookup"><span data-stu-id="01619-727">Slovenia</span></span>

### <a name="format"></a><span data-ttu-id="01619-728">Formato</span><span class="sxs-lookup"><span data-stu-id="01619-728">Format</span></span>

<span data-ttu-id="01619-729">Nove cifre senza spazi e delimitatori</span><span class="sxs-lookup"><span data-stu-id="01619-729">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="01619-730">Modello</span><span class="sxs-lookup"><span data-stu-id="01619-730">Pattern</span></span>

<span data-ttu-id="01619-731">9 cifre</span><span class="sxs-lookup"><span data-stu-id="01619-731">Nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="01619-732">Checksum</span><span class="sxs-lookup"><span data-stu-id="01619-732">Checksum</span></span>

<span data-ttu-id="01619-733">No</span><span class="sxs-lookup"><span data-stu-id="01619-733">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="01619-734">Definizione</span><span class="sxs-lookup"><span data-stu-id="01619-734">Definition</span></span>

<span data-ttu-id="01619-735">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="01619-735">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="01619-736">L'espressione `Regex_slovenia_eu_driver's_license_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="01619-736">The regular expression  `Regex_slovenia_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="01619-737">Viene trovata una `Keywords_slovenia_eu_driver's_license_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="01619-737">A keyword from  `Keywords_slovenia_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovenia_eu_driver's_license_number" />
          <Match idRef="Keywords_slovenia_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="01619-738">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="01619-738">Keywords</span></span>

<span data-ttu-id="01619-739">| |</span><span class="sxs-lookup"><span data-stu-id="01619-739"></span></span>
|<span data-ttu-id="01619-740">**Keywords_slovenia_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="01619-740">**Keywords_slovenia_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="01619-741">DL</span><span class="sxs-lookup"><span data-stu-id="01619-741">dl#</span></span>  <br/> <span data-ttu-id="01619-742">patente di guida</span><span class="sxs-lookup"><span data-stu-id="01619-742">driver license</span></span>  <br/> <span data-ttu-id="01619-743">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="01619-743">driver license number</span></span>  <br/> <span data-ttu-id="01619-744">patente di guida</span><span class="sxs-lookup"><span data-stu-id="01619-744">driver licence</span></span>  <br/> <span data-ttu-id="01619-745">driver Lic.</span><span class="sxs-lookup"><span data-stu-id="01619-745">drivers lic.</span></span>  <br/> <span data-ttu-id="01619-746">patente di guida</span><span class="sxs-lookup"><span data-stu-id="01619-746">drivers license</span></span>  <br/> <span data-ttu-id="01619-747">drivers licence</span><span class="sxs-lookup"><span data-stu-id="01619-747">drivers licence</span></span>  <br/> <span data-ttu-id="01619-748">patente di guida</span><span class="sxs-lookup"><span data-stu-id="01619-748">driver's license</span></span>  <br/> <span data-ttu-id="01619-749">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="01619-749">driver's license number</span></span>  <br/> <span data-ttu-id="01619-750">numero di patente del conducente</span><span class="sxs-lookup"><span data-stu-id="01619-750">driver's licence number</span></span>  <br/> <span data-ttu-id="01619-751">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="01619-751">driving license number</span></span>  <br/> <span data-ttu-id="01619-752">dlno #</span><span class="sxs-lookup"><span data-stu-id="01619-752">dlno#</span></span>  <br/> <span data-ttu-id="01619-753">vozniško dovoljenje</span><span class="sxs-lookup"><span data-stu-id="01619-753">vozniško dovoljenje</span></span>  <br/> |
   
## <a name="spain"></a><span data-ttu-id="01619-754">Spagna</span><span class="sxs-lookup"><span data-stu-id="01619-754">Spain</span></span>

### <a name="format"></a><span data-ttu-id="01619-755">Formato</span><span class="sxs-lookup"><span data-stu-id="01619-755">Format</span></span>

<span data-ttu-id="01619-756">Otto cifre seguite da un carattere</span><span class="sxs-lookup"><span data-stu-id="01619-756">Eight digits followed by one character</span></span>
  
### <a name="pattern"></a><span data-ttu-id="01619-757">Modello</span><span class="sxs-lookup"><span data-stu-id="01619-757">Pattern</span></span>

<span data-ttu-id="01619-758">Otto cifre seguite da un carattere:</span><span class="sxs-lookup"><span data-stu-id="01619-758">Eight digits followed by one character:</span></span>
  
-  <span data-ttu-id="01619-759">Otto cifre</span><span class="sxs-lookup"><span data-stu-id="01619-759">Eight digits</span></span> 
    
- <span data-ttu-id="01619-760">Una cifra o una lettera (senza distinzione tra maiuscole e minuscole)</span><span class="sxs-lookup"><span data-stu-id="01619-760">One digit or letter (not case-sensitive)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="01619-761">Checksum</span><span class="sxs-lookup"><span data-stu-id="01619-761">Checksum</span></span>

<span data-ttu-id="01619-762">Sì</span><span class="sxs-lookup"><span data-stu-id="01619-762">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="01619-763">Definizione</span><span class="sxs-lookup"><span data-stu-id="01619-763">Definition</span></span>

<span data-ttu-id="01619-764">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="01619-764">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="01619-765">La funzione `Func_spain_eu_driver's_license_number` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="01619-765">The function  `Func_spain_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="01619-766">Viene trovata una `Keywords_spain_eu_driver's_license_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="01619-766">A keyword from  `Keywords_spain_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_spain_eu_driver's_license_number" />
          <Match idRef="Keywords_spain_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="01619-767">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="01619-767">Keywords</span></span>

<span data-ttu-id="01619-768">| |</span><span class="sxs-lookup"><span data-stu-id="01619-768"></span></span>
|<span data-ttu-id="01619-769">**Keywords_spain_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="01619-769">**Keywords_spain_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="01619-770">dlno #</span><span class="sxs-lookup"><span data-stu-id="01619-770">dlno#</span></span>  <br/> <span data-ttu-id="01619-771">DL</span><span class="sxs-lookup"><span data-stu-id="01619-771">dl#</span></span>  <br/> <span data-ttu-id="01619-772">driver Lic.</span><span class="sxs-lookup"><span data-stu-id="01619-772">drivers lic.</span></span>  <br/> <span data-ttu-id="01619-773">patente di guida</span><span class="sxs-lookup"><span data-stu-id="01619-773">driver licence</span></span>  <br/> <span data-ttu-id="01619-774">patente di guida</span><span class="sxs-lookup"><span data-stu-id="01619-774">driver license</span></span>  <br/> <span data-ttu-id="01619-775">drivers licence</span><span class="sxs-lookup"><span data-stu-id="01619-775">drivers licence</span></span>  <br/> <span data-ttu-id="01619-776">
drivers license</span><span class="sxs-lookup"><span data-stu-id="01619-776">drivers license</span></span>  <br/> <span data-ttu-id="01619-777">patente di guida</span><span class="sxs-lookup"><span data-stu-id="01619-777">driver's licence</span></span>  <br/> <span data-ttu-id="01619-778">patente di guida</span><span class="sxs-lookup"><span data-stu-id="01619-778">driver's license</span></span>  <br/> <span data-ttu-id="01619-779">driving licence
</span><span class="sxs-lookup"><span data-stu-id="01619-779">driving licence</span></span>  <br/> <span data-ttu-id="01619-780">patente di guida</span><span class="sxs-lookup"><span data-stu-id="01619-780">driving license</span></span>  <br/> <span data-ttu-id="01619-781">numero di patente del conducente</span><span class="sxs-lookup"><span data-stu-id="01619-781">driver licence number</span></span>  <br/> <span data-ttu-id="01619-782">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="01619-782">driver license number</span></span>  <br/> <span data-ttu-id="01619-783">numero di patente del conducente</span><span class="sxs-lookup"><span data-stu-id="01619-783">drivers licence number</span></span>  <br/> <span data-ttu-id="01619-784">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="01619-784">drivers license number</span></span>  <br/> <span data-ttu-id="01619-785">numero di patente del conducente</span><span class="sxs-lookup"><span data-stu-id="01619-785">driver's licence number</span></span>  <br/> <span data-ttu-id="01619-786">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="01619-786">driver's license number</span></span>  <br/> <span data-ttu-id="01619-787">numero di patente di guida</span><span class="sxs-lookup"><span data-stu-id="01619-787">driving licence number</span></span>  <br/> <span data-ttu-id="01619-788">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="01619-788">driving license number</span></span>  <br/> <span data-ttu-id="01619-789">permesso di guida</span><span class="sxs-lookup"><span data-stu-id="01619-789">driving permit</span></span>  <br/> <span data-ttu-id="01619-790">numero di licenza di guida</span><span class="sxs-lookup"><span data-stu-id="01619-790">driving permit number</span></span>  <br/> <span data-ttu-id="01619-791">Permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="01619-791">permiso de conducción</span></span>  <br/> <span data-ttu-id="01619-792">Permiso conducción</span><span class="sxs-lookup"><span data-stu-id="01619-792">permiso conducción</span></span>  <br/> <span data-ttu-id="01619-793">número licencia conducir</span><span class="sxs-lookup"><span data-stu-id="01619-793">número licencia conducir</span></span>  <br/> <span data-ttu-id="01619-794">número de carnet de conducir</span><span class="sxs-lookup"><span data-stu-id="01619-794">número de carnet de conducir</span></span>  <br/> <span data-ttu-id="01619-795">número carnet conducir</span><span class="sxs-lookup"><span data-stu-id="01619-795">número carnet conducir</span></span>  <br/> <span data-ttu-id="01619-796">licencia conducir</span><span class="sxs-lookup"><span data-stu-id="01619-796">licencia conducir</span></span>  <br/> <span data-ttu-id="01619-797">número de Permiso de conducir</span><span class="sxs-lookup"><span data-stu-id="01619-797">número de permiso de conducir</span></span>  <br/> <span data-ttu-id="01619-798">número de permiso conducir</span><span class="sxs-lookup"><span data-stu-id="01619-798">número de permiso conducir</span></span>  <br/> <span data-ttu-id="01619-799">número permiso conducir</span><span class="sxs-lookup"><span data-stu-id="01619-799">número permiso conducir</span></span>  <br/> <span data-ttu-id="01619-800">Permiso conducir</span><span class="sxs-lookup"><span data-stu-id="01619-800">permiso conducir</span></span>  <br/> <span data-ttu-id="01619-801">licencia de manejo</span><span class="sxs-lookup"><span data-stu-id="01619-801">licencia de manejo</span></span>  <br/> <span data-ttu-id="01619-802">El carnet de conducir</span><span class="sxs-lookup"><span data-stu-id="01619-802">el carnet de conducir</span></span>  <br/> <span data-ttu-id="01619-803">carnet conducir</span><span class="sxs-lookup"><span data-stu-id="01619-803">carnet conducir</span></span>  <br/> |
   
## <a name="sweden"></a><span data-ttu-id="01619-804">Svezia</span><span class="sxs-lookup"><span data-stu-id="01619-804">Sweden</span></span>

### <a name="format"></a><span data-ttu-id="01619-805">Formato</span><span class="sxs-lookup"><span data-stu-id="01619-805">Format</span></span>

<span data-ttu-id="01619-806">Dieci cifre contenenti un segno meno</span><span class="sxs-lookup"><span data-stu-id="01619-806">Ten digits containing a hyphen</span></span>
  
### <a name="pattern"></a><span data-ttu-id="01619-807">Modello</span><span class="sxs-lookup"><span data-stu-id="01619-807">Pattern</span></span>

<span data-ttu-id="01619-808">Dieci cifre contenenti un trattino:</span><span class="sxs-lookup"><span data-stu-id="01619-808">Ten digits containing a hyphen:</span></span>
  
-  <span data-ttu-id="01619-809">Sei cifre</span><span class="sxs-lookup"><span data-stu-id="01619-809">Six digits</span></span> 
    
- <span data-ttu-id="01619-810">Una lineetta</span><span class="sxs-lookup"><span data-stu-id="01619-810">A hyphen</span></span>
    
- <span data-ttu-id="01619-811">Quattro cifre</span><span class="sxs-lookup"><span data-stu-id="01619-811">Four digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="01619-812">Checksum</span><span class="sxs-lookup"><span data-stu-id="01619-812">Checksum</span></span>

<span data-ttu-id="01619-813">No</span><span class="sxs-lookup"><span data-stu-id="01619-813">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="01619-814">Definizione</span><span class="sxs-lookup"><span data-stu-id="01619-814">Definition</span></span>

<span data-ttu-id="01619-815">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="01619-815">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="01619-816">L'espressione `Regex_sweden_eu_driver's_license_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="01619-816">The regular expression  `Regex_sweden_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="01619-817">Viene trovata una `Keywords_sweden_eu_driver's_license_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="01619-817">A keyword from  `Keywords_sweden_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_sweden_eu_driver's_license_number" />
          <Match idRef="Keywords_sweden_eu_driver's_license_number" />
        </Pattern>
</Entity> 
```

### <a name="keywords"></a><span data-ttu-id="01619-818">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="01619-818">Keywords</span></span>

<span data-ttu-id="01619-819">| |</span><span class="sxs-lookup"><span data-stu-id="01619-819"></span></span>
|<span data-ttu-id="01619-820">**Keywords_sweden_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="01619-820">**Keywords_sweden_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="01619-821">DL</span><span class="sxs-lookup"><span data-stu-id="01619-821">dl#</span></span>  <br/> <span data-ttu-id="01619-822">patente di guida</span><span class="sxs-lookup"><span data-stu-id="01619-822">driver license</span></span>  <br/> <span data-ttu-id="01619-823">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="01619-823">driver license number</span></span>  <br/> <span data-ttu-id="01619-824">patente di guida</span><span class="sxs-lookup"><span data-stu-id="01619-824">driver licence</span></span>  <br/> <span data-ttu-id="01619-825">driver Lic.</span><span class="sxs-lookup"><span data-stu-id="01619-825">drivers lic.</span></span>  <br/> <span data-ttu-id="01619-826">patente di guida</span><span class="sxs-lookup"><span data-stu-id="01619-826">drivers license</span></span>  <br/> <span data-ttu-id="01619-827">drivers licence</span><span class="sxs-lookup"><span data-stu-id="01619-827">drivers licence</span></span>  <br/> <span data-ttu-id="01619-828">patente di guida</span><span class="sxs-lookup"><span data-stu-id="01619-828">driver's license</span></span>  <br/> <span data-ttu-id="01619-829">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="01619-829">driver's license number</span></span>  <br/> <span data-ttu-id="01619-830">numero di patente del conducente</span><span class="sxs-lookup"><span data-stu-id="01619-830">driver's licence number</span></span>  <br/> <span data-ttu-id="01619-831">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="01619-831">driving license number</span></span>  <br/> <span data-ttu-id="01619-832">dlno #</span><span class="sxs-lookup"><span data-stu-id="01619-832">dlno#</span></span>  <br/> <span data-ttu-id="01619-833">körkort</span><span class="sxs-lookup"><span data-stu-id="01619-833">körkort</span></span>  <br/> |
   
## <a name="uk"></a><span data-ttu-id="01619-834">Regno Unito</span><span class="sxs-lookup"><span data-stu-id="01619-834">UK</span></span>

<span data-ttu-id="01619-p103">Per informazioni dettagliate, vedere la sezione "numero di patente di guida del Regno Unito" in [che cosa cercano i tipi di informazioni riservate](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="01619-p103">For details, see the section "U.K. Driver's License Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="01619-837">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="01619-837">See also</span></span>

[<span data-ttu-id="01619-838">Cosa individuano le tipologie di informazioni sensibili</span><span class="sxs-lookup"><span data-stu-id="01619-838">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)

