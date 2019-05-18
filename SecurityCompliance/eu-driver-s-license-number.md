---
title: Numero della patente di guida dell'Unione europea
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 8/17/2018
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
description: In questo argomento viene illustrato l'aspetto di un criterio di prevenzione della perdita di dati (DLP) quando viene rilevato il tipo di informazioni riservate del numero di licenza del driver dell'Unione europea. Questo tipo di informazioni riservate definisce modelli, parole chiave e altre evidenze diverse per ogni paese.
ms.openlocfilehash: f1a95ecbaf6b6d1ac189290dd6d076cfd91ab30f
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/17/2019
ms.locfileid: "34152978"
---
# <a name="eu-drivers-license-number"></a><span data-ttu-id="c85ce-104">Numero della patente di guida dell'Unione europea</span><span class="sxs-lookup"><span data-stu-id="c85ce-104">EU Driver's License Number</span></span>

<span data-ttu-id="c85ce-105">In questo argomento viene illustrato l'aspetto di un criterio di prevenzione della perdita di dati (DLP) quando viene rilevato il tipo di informazioni riservate del numero di licenza del driver dell'Unione europea.</span><span class="sxs-lookup"><span data-stu-id="c85ce-105">This topic shows what a data loss prevention (DLP) policy looks for when it detects the EU Driver's License Number sensitive information type.</span></span> <span data-ttu-id="c85ce-106">Questo tipo di informazioni riservate definisce modelli, parole chiave e altre evidenze diverse per ogni paese.</span><span class="sxs-lookup"><span data-stu-id="c85ce-106">This sensitive information type defines different patterns, keywords, and other evidence for each country.</span></span>
  
## <a name="austria"></a><span data-ttu-id="c85ce-107">Austria</span><span class="sxs-lookup"><span data-stu-id="c85ce-107">Austria</span></span>

### <a name="format"></a><span data-ttu-id="c85ce-108">Formato</span><span class="sxs-lookup"><span data-stu-id="c85ce-108">Format</span></span>

<span data-ttu-id="c85ce-109">Otto cifre senza spazi e delimitatori</span><span class="sxs-lookup"><span data-stu-id="c85ce-109">Eight digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="c85ce-110">Modello</span><span class="sxs-lookup"><span data-stu-id="c85ce-110">Pattern</span></span>

<span data-ttu-id="c85ce-111">Otto cifre</span><span class="sxs-lookup"><span data-stu-id="c85ce-111">Eight digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="c85ce-112">Checksum</span><span class="sxs-lookup"><span data-stu-id="c85ce-112">Checksum</span></span>

<span data-ttu-id="c85ce-113">No</span><span class="sxs-lookup"><span data-stu-id="c85ce-113">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="c85ce-114">Definizione</span><span class="sxs-lookup"><span data-stu-id="c85ce-114">Definition</span></span>

<span data-ttu-id="c85ce-115">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="c85ce-115">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="c85ce-116">L'espressione `Regex_austria_eu_driver's_license_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="c85ce-116">The regular expression  `Regex_austria_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="c85ce-117">Viene trovata una `Keywords_austria_eu_driver's_license_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="c85ce-117">A keyword from  `Keywords_austria_eu_driver's_license_number` is found.</span></span> 
    
```
<!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_austria_eu_driver's_license_number" />
          <Match idRef="Keywords_austria_eu_driver's_license_number" />
        </Pattern>
    </Entity>

```

### <a name="keywords"></a><span data-ttu-id="c85ce-118">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="c85ce-118">Keywords</span></span>

<span data-ttu-id="c85ce-119">| |</span><span class="sxs-lookup"><span data-stu-id="c85ce-119"></span></span>
|<span data-ttu-id="c85ce-120">**Keywords_austria_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="c85ce-120">**Keywords_austria_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="c85ce-121">DL</span><span class="sxs-lookup"><span data-stu-id="c85ce-121">dl#</span></span>  <br/> <span data-ttu-id="c85ce-122">driver license</span><span class="sxs-lookup"><span data-stu-id="c85ce-122">driver license</span></span>  <br/> <span data-ttu-id="c85ce-123">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="c85ce-123">driver license number</span></span>  <br/> <span data-ttu-id="c85ce-124">patente di guida</span><span class="sxs-lookup"><span data-stu-id="c85ce-124">driver licence</span></span>  <br/> <span data-ttu-id="c85ce-125">driver Lic.</span><span class="sxs-lookup"><span data-stu-id="c85ce-125">drivers lic.</span></span>  <br/> <span data-ttu-id="c85ce-126">drivers license</span><span class="sxs-lookup"><span data-stu-id="c85ce-126">drivers license</span></span>  <br/> <span data-ttu-id="c85ce-127">driver's licence</span><span class="sxs-lookup"><span data-stu-id="c85ce-127">driver's licence</span></span>  <br/> <span data-ttu-id="c85ce-128">driver's license</span><span class="sxs-lookup"><span data-stu-id="c85ce-128">driver's license</span></span>  <br/> <span data-ttu-id="c85ce-129">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="c85ce-129">driver's license number</span></span>  <br/> <span data-ttu-id="c85ce-130">numero di patente del conducente</span><span class="sxs-lookup"><span data-stu-id="c85ce-130">driver's licence number</span></span>  <br/>  <span data-ttu-id="c85ce-131">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="c85ce-131">driving license number</span></span>  <br/> <span data-ttu-id="c85ce-132">dlno#</span><span class="sxs-lookup"><span data-stu-id="c85ce-132">dlno#</span></span>  <br/> <span data-ttu-id="c85ce-133">fuhrerschein</span><span class="sxs-lookup"><span data-stu-id="c85ce-133">fuhrerschein</span></span>  <br/> <span data-ttu-id="c85ce-134">fuhrerschein Republik Osterreich</span><span class="sxs-lookup"><span data-stu-id="c85ce-134">fuhrerschein republik osterreich</span></span>  <br/> |
   
## <a name="belgium"></a><span data-ttu-id="c85ce-135">Belgio</span><span class="sxs-lookup"><span data-stu-id="c85ce-135">Belgium</span></span>

### <a name="format"></a><span data-ttu-id="c85ce-136">Formato</span><span class="sxs-lookup"><span data-stu-id="c85ce-136">Format</span></span>

<span data-ttu-id="c85ce-137">10 cifre senza spazi e delimitatori</span><span class="sxs-lookup"><span data-stu-id="c85ce-137">10 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="c85ce-138">Modello</span><span class="sxs-lookup"><span data-stu-id="c85ce-138">Pattern</span></span>

<span data-ttu-id="c85ce-139">10 cifre</span><span class="sxs-lookup"><span data-stu-id="c85ce-139">10 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="c85ce-140">Checksum</span><span class="sxs-lookup"><span data-stu-id="c85ce-140">Checksum</span></span>

<span data-ttu-id="c85ce-141">No</span><span class="sxs-lookup"><span data-stu-id="c85ce-141">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="c85ce-142">Definizione</span><span class="sxs-lookup"><span data-stu-id="c85ce-142">Definition</span></span>

<span data-ttu-id="c85ce-143">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="c85ce-143">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="c85ce-144">L'espressione `Regex_belgium_eu_driver's_license_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="c85ce-144">The regular expression  `Regex_belgium_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="c85ce-145">Viene trovata una `Keywords_belgium_eu_driver's_license_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="c85ce-145">A keyword from  `Keywords_belgium_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_belgium_eu_driver's_license_number" />
          <Match idRef="Keywords_belgium_eu_driver's_license_number" />
        </Pattern>
</Entity>

```

### <a name="keywords"></a><span data-ttu-id="c85ce-146">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="c85ce-146">Keywords</span></span>

<span data-ttu-id="c85ce-147">| |</span><span class="sxs-lookup"><span data-stu-id="c85ce-147"></span></span>
|<span data-ttu-id="c85ce-148">**Keywords__belgium_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="c85ce-148">**Keywords__belgium_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="c85ce-149">DL</span><span class="sxs-lookup"><span data-stu-id="c85ce-149">dl#</span></span>  <br/> <span data-ttu-id="c85ce-150">driver license</span><span class="sxs-lookup"><span data-stu-id="c85ce-150">driver license</span></span>  <br/> <span data-ttu-id="c85ce-151">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="c85ce-151">driver license number</span></span>  <br/> <span data-ttu-id="c85ce-152">patente di guida</span><span class="sxs-lookup"><span data-stu-id="c85ce-152">driver licence</span></span>  <br/> <span data-ttu-id="c85ce-153">driver Lic.</span><span class="sxs-lookup"><span data-stu-id="c85ce-153">drivers lic.</span></span>  <br/> <span data-ttu-id="c85ce-154">drivers license</span><span class="sxs-lookup"><span data-stu-id="c85ce-154">drivers license</span></span>  <br/> <span data-ttu-id="c85ce-155">drivers licence</span><span class="sxs-lookup"><span data-stu-id="c85ce-155">drivers licence</span></span>  <br/> <span data-ttu-id="c85ce-156">driver's license</span><span class="sxs-lookup"><span data-stu-id="c85ce-156">driver's license</span></span>  <br/> <span data-ttu-id="c85ce-157">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="c85ce-157">driver's license number</span></span>  <br/> <span data-ttu-id="c85ce-158">numero di patente del conducente</span><span class="sxs-lookup"><span data-stu-id="c85ce-158">driver's licence number</span></span>  <br/> <span data-ttu-id="c85ce-159">dlno#</span><span class="sxs-lookup"><span data-stu-id="c85ce-159">dlno#</span></span>  <br/> <span data-ttu-id="c85ce-160">rijbewijs</span><span class="sxs-lookup"><span data-stu-id="c85ce-160">rijbewijs</span></span>  <br/> <span data-ttu-id="c85ce-161">rijbewijsnummer</span><span class="sxs-lookup"><span data-stu-id="c85ce-161">rijbewijsnummer</span></span>  <br/> <span data-ttu-id="c85ce-162">führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="c85ce-162">führerscheinnummer</span></span>  <br/> <span data-ttu-id="c85ce-163">fuhrerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="c85ce-163">fuhrerscheinnummer</span></span>  <br/> <span data-ttu-id="c85ce-164">fuehrerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="c85ce-164">fuehrerscheinnummer</span></span>  <br/> <span data-ttu-id="c85ce-165">Führerschein-Nr</span><span class="sxs-lookup"><span data-stu-id="c85ce-165">führerschein- nr</span></span>  <br/> <span data-ttu-id="c85ce-166">fuehrerschein-Nr</span><span class="sxs-lookup"><span data-stu-id="c85ce-166">fuehrerschein- Nr</span></span>  <br/> <span data-ttu-id="c85ce-167">fuehrerschein-Nr</span><span class="sxs-lookup"><span data-stu-id="c85ce-167">fuehrerschein- nr</span></span>  <br/> |
   
## <a name="bulgaria"></a><span data-ttu-id="c85ce-168">Bulgaria</span><span class="sxs-lookup"><span data-stu-id="c85ce-168">Bulgaria</span></span>

### <a name="format"></a><span data-ttu-id="c85ce-169">Formato</span><span class="sxs-lookup"><span data-stu-id="c85ce-169">Format</span></span>

<span data-ttu-id="c85ce-170">Nove cifre senza spazi e delimitatori</span><span class="sxs-lookup"><span data-stu-id="c85ce-170">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="c85ce-171">Modello</span><span class="sxs-lookup"><span data-stu-id="c85ce-171">Pattern</span></span>

<span data-ttu-id="c85ce-172">9 cifre</span><span class="sxs-lookup"><span data-stu-id="c85ce-172">Nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="c85ce-173">Checksum</span><span class="sxs-lookup"><span data-stu-id="c85ce-173">Checksum</span></span>

<span data-ttu-id="c85ce-174">No</span><span class="sxs-lookup"><span data-stu-id="c85ce-174">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="c85ce-175">Definizione</span><span class="sxs-lookup"><span data-stu-id="c85ce-175">Definition</span></span>

<span data-ttu-id="c85ce-176">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="c85ce-176">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="c85ce-177">L'espressione `Regex_bulgaria_eu_driver's_license_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="c85ce-177">The regular expression  `Regex_bulgaria_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="c85ce-178">Viene trovata una `Keywords_bulgaria_eu_driver's_license_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="c85ce-178">A keyword from  `Keywords_bulgaria_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
             <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_bulgaria_eu_driver's_license_number" />
          <Match idRef="Keywords_bulgaria_eu_driver's_license_number" />
        </Pattern> 
</Entity>    

```

### <a name="keywords"></a><span data-ttu-id="c85ce-179">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="c85ce-179">Keywords</span></span>

<span data-ttu-id="c85ce-180">| |</span><span class="sxs-lookup"><span data-stu-id="c85ce-180"></span></span>
|<span data-ttu-id="c85ce-181">**Keywords_bulgaria_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="c85ce-181">**Keywords_bulgaria_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="c85ce-182">DL</span><span class="sxs-lookup"><span data-stu-id="c85ce-182">dl#</span></span>  <br/> <span data-ttu-id="c85ce-183">driver license</span><span class="sxs-lookup"><span data-stu-id="c85ce-183">driver license</span></span>  <br/> <span data-ttu-id="c85ce-184">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="c85ce-184">driver license number</span></span>  <br/> <span data-ttu-id="c85ce-185">patente di guida</span><span class="sxs-lookup"><span data-stu-id="c85ce-185">driver licence</span></span>  <br/> <span data-ttu-id="c85ce-186">driver Lic.</span><span class="sxs-lookup"><span data-stu-id="c85ce-186">drivers lic.</span></span>  <br/> <span data-ttu-id="c85ce-187">drivers license</span><span class="sxs-lookup"><span data-stu-id="c85ce-187">drivers license</span></span>  <br/> <span data-ttu-id="c85ce-188">drivers licence</span><span class="sxs-lookup"><span data-stu-id="c85ce-188">drivers licence</span></span>  <br/> <span data-ttu-id="c85ce-189">driver's license</span><span class="sxs-lookup"><span data-stu-id="c85ce-189">driver's license</span></span>  <br/> <span data-ttu-id="c85ce-190">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="c85ce-190">driver's license number</span></span>  <br/> <span data-ttu-id="c85ce-191">numero di patente del conducente</span><span class="sxs-lookup"><span data-stu-id="c85ce-191">driver's licence number</span></span>  <br/> <span data-ttu-id="c85ce-192">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="c85ce-192">driving license number</span></span>  <br/> <span data-ttu-id="c85ce-193">dlno#</span><span class="sxs-lookup"><span data-stu-id="c85ce-193">dlno#</span></span>  <br/> <span data-ttu-id="c85ce-194">свидетелство за управление на мпс</span><span class="sxs-lookup"><span data-stu-id="c85ce-194">свидетелство за управление на мпс</span></span>  <br/> <span data-ttu-id="c85ce-195">свидетелство за управление на моторно превозно d'средство</span><span class="sxs-lookup"><span data-stu-id="c85ce-195">свидетелство за управление на моторно превозно средство</span></span>  <br/> <span data-ttu-id="c85ce-196">сумпс</span><span class="sxs-lookup"><span data-stu-id="c85ce-196">сумпс</span></span>  <br/> <span data-ttu-id="c85ce-197">шофьорска книжка</span><span class="sxs-lookup"><span data-stu-id="c85ce-197">шофьорска книжка</span></span>  <br/> |
   
## <a name="croatia"></a><span data-ttu-id="c85ce-198">Croazia</span><span class="sxs-lookup"><span data-stu-id="c85ce-198">Croatia</span></span>

### <a name="format"></a><span data-ttu-id="c85ce-199">Formato</span><span class="sxs-lookup"><span data-stu-id="c85ce-199">Format</span></span>

<span data-ttu-id="c85ce-200">Otto cifre senza spazi e delimitatori</span><span class="sxs-lookup"><span data-stu-id="c85ce-200">Eight digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="c85ce-201">Modello</span><span class="sxs-lookup"><span data-stu-id="c85ce-201">Pattern</span></span>

<span data-ttu-id="c85ce-202">Otto cifre</span><span class="sxs-lookup"><span data-stu-id="c85ce-202">Eight digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="c85ce-203">Checksum</span><span class="sxs-lookup"><span data-stu-id="c85ce-203">Checksum</span></span>

<span data-ttu-id="c85ce-204">No</span><span class="sxs-lookup"><span data-stu-id="c85ce-204">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="c85ce-205">Definizione</span><span class="sxs-lookup"><span data-stu-id="c85ce-205">Definition</span></span>

<span data-ttu-id="c85ce-206">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="c85ce-206">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="c85ce-207">L'espressione `Regex_croatia_eu_driver's_license_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="c85ce-207">The regular expression  `Regex_croatia_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="c85ce-208">Viene trovata una `Keywords_croatia_eu_driver's_license_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="c85ce-208">A keyword from  `Keywords_croatia_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_croatia_eu_driver's_license_number" />
          <Match idRef="Keywords_croatia_eu_driver's_license_number" />
        </Pattern>
</Entity>

```

### <a name="keywords"></a><span data-ttu-id="c85ce-209">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="c85ce-209">Keywords</span></span>

<span data-ttu-id="c85ce-210">| |</span><span class="sxs-lookup"><span data-stu-id="c85ce-210"></span></span>
|<span data-ttu-id="c85ce-211">**Keywords_croatia_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="c85ce-211">**Keywords_croatia_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="c85ce-212">DL</span><span class="sxs-lookup"><span data-stu-id="c85ce-212">dl#</span></span>  <br/> <span data-ttu-id="c85ce-213">driver license</span><span class="sxs-lookup"><span data-stu-id="c85ce-213">driver license</span></span>  <br/> <span data-ttu-id="c85ce-214">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="c85ce-214">driver license number</span></span>  <br/> <span data-ttu-id="c85ce-215">patente di guida</span><span class="sxs-lookup"><span data-stu-id="c85ce-215">driver licence</span></span>  <br/> <span data-ttu-id="c85ce-216">driver Lic.</span><span class="sxs-lookup"><span data-stu-id="c85ce-216">drivers lic.</span></span>  <br/> <span data-ttu-id="c85ce-217">drivers license</span><span class="sxs-lookup"><span data-stu-id="c85ce-217">drivers license</span></span>  <br/> <span data-ttu-id="c85ce-218">drivers licence</span><span class="sxs-lookup"><span data-stu-id="c85ce-218">drivers licence</span></span>  <br/> <span data-ttu-id="c85ce-219">driver's license</span><span class="sxs-lookup"><span data-stu-id="c85ce-219">driver's license</span></span>  <br/> <span data-ttu-id="c85ce-220">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="c85ce-220">driver's license number</span></span>  <br/> <span data-ttu-id="c85ce-221">numero di patente del conducente</span><span class="sxs-lookup"><span data-stu-id="c85ce-221">driver's licence number</span></span>  <br/> <span data-ttu-id="c85ce-222">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="c85ce-222">driving license number</span></span>  <br/> <span data-ttu-id="c85ce-223">dlno#</span><span class="sxs-lookup"><span data-stu-id="c85ce-223">dlno#</span></span>  <br/> <span data-ttu-id="c85ce-224">vozačka dozvola</span><span class="sxs-lookup"><span data-stu-id="c85ce-224">vozačka dozvola</span></span>  <br/> |
   
## <a name="cyprus"></a><span data-ttu-id="c85ce-225">Cipro</span><span class="sxs-lookup"><span data-stu-id="c85ce-225">Cyprus</span></span>

### <a name="format"></a><span data-ttu-id="c85ce-226">Formato</span><span class="sxs-lookup"><span data-stu-id="c85ce-226">Format</span></span>

<span data-ttu-id="c85ce-227">12 cifre senza spazi e delimitatori</span><span class="sxs-lookup"><span data-stu-id="c85ce-227">12 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="c85ce-228">Modello</span><span class="sxs-lookup"><span data-stu-id="c85ce-228">Pattern</span></span>

<span data-ttu-id="c85ce-229">12 cifre</span><span class="sxs-lookup"><span data-stu-id="c85ce-229">12 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="c85ce-230">Checksum</span><span class="sxs-lookup"><span data-stu-id="c85ce-230">Checksum</span></span>

<span data-ttu-id="c85ce-231">No</span><span class="sxs-lookup"><span data-stu-id="c85ce-231">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="c85ce-232">Definizione</span><span class="sxs-lookup"><span data-stu-id="c85ce-232">Definition</span></span>

<span data-ttu-id="c85ce-233">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="c85ce-233">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="c85ce-234">L'espressione `Regex_cyprus_eu_driver's_license_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="c85ce-234">The regular expression  `Regex_cyprus_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="c85ce-235">Viene trovata una `Keywords_cyprus_eu_driver's_license_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="c85ce-235">A keyword from  `Keywords_cyprus_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_cyprus_eu_driver's_license_number" />
          <Match idRef="Keywords_cyprus_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="c85ce-236">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="c85ce-236">Keywords</span></span>

<span data-ttu-id="c85ce-237">| |</span><span class="sxs-lookup"><span data-stu-id="c85ce-237"></span></span>
|<span data-ttu-id="c85ce-238">**Keywords_cyprus_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="c85ce-238">**Keywords_cyprus_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="c85ce-239">DL</span><span class="sxs-lookup"><span data-stu-id="c85ce-239">dl#</span></span>  <br/> <span data-ttu-id="c85ce-240">driver license</span><span class="sxs-lookup"><span data-stu-id="c85ce-240">driver license</span></span>  <br/> <span data-ttu-id="c85ce-241">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="c85ce-241">driver license number</span></span>  <br/> <span data-ttu-id="c85ce-242">patente di guida</span><span class="sxs-lookup"><span data-stu-id="c85ce-242">driver licence</span></span>  <br/> <span data-ttu-id="c85ce-243">driver Lic.</span><span class="sxs-lookup"><span data-stu-id="c85ce-243">drivers lic.</span></span>  <br/> <span data-ttu-id="c85ce-244">drivers license</span><span class="sxs-lookup"><span data-stu-id="c85ce-244">drivers license</span></span>  <br/> <span data-ttu-id="c85ce-245">drivers licence</span><span class="sxs-lookup"><span data-stu-id="c85ce-245">drivers licence</span></span>  <br/> <span data-ttu-id="c85ce-246">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="c85ce-246">driver's license number</span></span>  <br/> <span data-ttu-id="c85ce-247">numero di patente del conducente</span><span class="sxs-lookup"><span data-stu-id="c85ce-247">driver's licence number</span></span>  <br/> <span data-ttu-id="c85ce-248">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="c85ce-248">driving license number</span></span>  <br/> <span data-ttu-id="c85ce-249">dlno#</span><span class="sxs-lookup"><span data-stu-id="c85ce-249">dlno#</span></span>  <br/> <span data-ttu-id="c85ce-250">άδεια οδήγησης</span><span class="sxs-lookup"><span data-stu-id="c85ce-250">άδεια οδήγησης</span></span>  <br/> |
   
## <a name="czech-republic"></a><span data-ttu-id="c85ce-251">Repubblica Ceca</span><span class="sxs-lookup"><span data-stu-id="c85ce-251">Czech Republic</span></span>

### <a name="format"></a><span data-ttu-id="c85ce-252">Formato</span><span class="sxs-lookup"><span data-stu-id="c85ce-252">Format</span></span>

<span data-ttu-id="c85ce-253">Due lettere seguite da sei cifre</span><span class="sxs-lookup"><span data-stu-id="c85ce-253">Two letters followed by six digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="c85ce-254">Modello</span><span class="sxs-lookup"><span data-stu-id="c85ce-254">Pattern</span></span>

<span data-ttu-id="c85ce-255">Otto lettere e cifre:</span><span class="sxs-lookup"><span data-stu-id="c85ce-255">Eight letters and digits:</span></span>
  
- <span data-ttu-id="c85ce-256">Due lettere (senza distinzione tra maiuscole e minuscole)</span><span class="sxs-lookup"><span data-stu-id="c85ce-256">Two letters (not case-sensitive)</span></span>
    
- <span data-ttu-id="c85ce-257">Uno spazio (facoltativo)</span><span class="sxs-lookup"><span data-stu-id="c85ce-257">A space (optional)</span></span>
    
- <span data-ttu-id="c85ce-258">Sei cifre</span><span class="sxs-lookup"><span data-stu-id="c85ce-258">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="c85ce-259">Checksum</span><span class="sxs-lookup"><span data-stu-id="c85ce-259">Checksum</span></span>

<span data-ttu-id="c85ce-260">No</span><span class="sxs-lookup"><span data-stu-id="c85ce-260">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="c85ce-261">Definizione</span><span class="sxs-lookup"><span data-stu-id="c85ce-261">Definition</span></span>

<span data-ttu-id="c85ce-262">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="c85ce-262">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="c85ce-263">L'espressione `Regex_czech_republic_eu_driver's_license_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="c85ce-263">The regular expression  `Regex_czech_republic_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="c85ce-264">Viene trovata una `Keywords_czech_republic_eu_driver's_license_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="c85ce-264">A keyword from  `Keywords_czech_republic_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_czech_republic_eu_driver's_license_number" />
          <Match idRef="Keywords_czech_republic_eu_driver's_license_number" />
        </Pattern>
</Entity>

```

### <a name="keywords"></a><span data-ttu-id="c85ce-265">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="c85ce-265">Keywords</span></span>

<span data-ttu-id="c85ce-266">| |</span><span class="sxs-lookup"><span data-stu-id="c85ce-266"></span></span>
|<span data-ttu-id="c85ce-267">**Keywords_czech_republic_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="c85ce-267">**Keywords_czech_republic_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="c85ce-268">DL</span><span class="sxs-lookup"><span data-stu-id="c85ce-268">dl#</span></span>  <br/> <span data-ttu-id="c85ce-269">driver license</span><span class="sxs-lookup"><span data-stu-id="c85ce-269">driver license</span></span>  <br/> <span data-ttu-id="c85ce-270">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="c85ce-270">driver license number</span></span>  <br/> <span data-ttu-id="c85ce-271">patente di guida</span><span class="sxs-lookup"><span data-stu-id="c85ce-271">driver licence</span></span>  <br/> <span data-ttu-id="c85ce-272">driver Lic.</span><span class="sxs-lookup"><span data-stu-id="c85ce-272">drivers lic.</span></span>  <br/> <span data-ttu-id="c85ce-273">drivers license</span><span class="sxs-lookup"><span data-stu-id="c85ce-273">drivers license</span></span>  <br/> <span data-ttu-id="c85ce-274">drivers licence</span><span class="sxs-lookup"><span data-stu-id="c85ce-274">drivers licence</span></span>  <br/> <span data-ttu-id="c85ce-275">driver's license</span><span class="sxs-lookup"><span data-stu-id="c85ce-275">driver's license</span></span>  <br/> <span data-ttu-id="c85ce-276">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="c85ce-276">driver's license number</span></span>  <br/> <span data-ttu-id="c85ce-277">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="c85ce-277">driver's license number</span></span>  <br/> <span data-ttu-id="c85ce-278">numero di patente del conducente</span><span class="sxs-lookup"><span data-stu-id="c85ce-278">driver's licence number</span></span>  <br/> <span data-ttu-id="c85ce-279">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="c85ce-279">driving license number</span></span>  <br/> <span data-ttu-id="c85ce-280">dlno#</span><span class="sxs-lookup"><span data-stu-id="c85ce-280">dlno#</span></span>  <br/> <span data-ttu-id="c85ce-281">řidičský prúkaz</span><span class="sxs-lookup"><span data-stu-id="c85ce-281">řidičský prúkaz</span></span>  <br/> |
   
## <a name="denmark"></a><span data-ttu-id="c85ce-282">Danimarca</span><span class="sxs-lookup"><span data-stu-id="c85ce-282">Denmark</span></span>

### <a name="format"></a><span data-ttu-id="c85ce-283">Formato</span><span class="sxs-lookup"><span data-stu-id="c85ce-283">Format</span></span>

<span data-ttu-id="c85ce-284">Otto cifre senza spazi e delimitatori</span><span class="sxs-lookup"><span data-stu-id="c85ce-284">Eight digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="c85ce-285">Modello</span><span class="sxs-lookup"><span data-stu-id="c85ce-285">Pattern</span></span>

<span data-ttu-id="c85ce-286">Otto cifre</span><span class="sxs-lookup"><span data-stu-id="c85ce-286">Eight digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="c85ce-287">Checksum</span><span class="sxs-lookup"><span data-stu-id="c85ce-287">Checksum</span></span>

<span data-ttu-id="c85ce-288">Sì</span><span class="sxs-lookup"><span data-stu-id="c85ce-288">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="c85ce-289">Definizione</span><span class="sxs-lookup"><span data-stu-id="c85ce-289">Definition</span></span>

<span data-ttu-id="c85ce-290">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="c85ce-290">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="c85ce-291">L'espressione `Regex_denmark_eu_driver's_license_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="c85ce-291">The regular expression  `Regex_denmark_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="c85ce-292">Viene trovata una `Keywords_denmark_eu_driver's_license_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="c85ce-292">A keyword from  `Keywords_denmark_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_denmark_eu_driver's_license_number" />
          <Match idRef="Keywords_denmark_eu_driver's_license_number" />
        </Pattern>
</Entity>

```

### <a name="keywords"></a><span data-ttu-id="c85ce-293">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="c85ce-293">Keywords</span></span>

<span data-ttu-id="c85ce-294">| |</span><span class="sxs-lookup"><span data-stu-id="c85ce-294"></span></span>
|<span data-ttu-id="c85ce-295">**Keywords_denmark_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="c85ce-295">**Keywords_denmark_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="c85ce-296">DL</span><span class="sxs-lookup"><span data-stu-id="c85ce-296">dl#</span></span>  <br/> <span data-ttu-id="c85ce-297">driver license</span><span class="sxs-lookup"><span data-stu-id="c85ce-297">driver license</span></span>  <br/> <span data-ttu-id="c85ce-298">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="c85ce-298">driver license number</span></span>  <br/> <span data-ttu-id="c85ce-299">patente di guida</span><span class="sxs-lookup"><span data-stu-id="c85ce-299">driver licence</span></span>  <br/> <span data-ttu-id="c85ce-300">driver Lic.</span><span class="sxs-lookup"><span data-stu-id="c85ce-300">drivers lic.</span></span>  <br/> <span data-ttu-id="c85ce-301">drivers license</span><span class="sxs-lookup"><span data-stu-id="c85ce-301">drivers license</span></span>  <br/> <span data-ttu-id="c85ce-302">drivers licence</span><span class="sxs-lookup"><span data-stu-id="c85ce-302">drivers licence</span></span>  <br/> <span data-ttu-id="c85ce-303">driver's license</span><span class="sxs-lookup"><span data-stu-id="c85ce-303">driver's license</span></span>  <br/> <span data-ttu-id="c85ce-304">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="c85ce-304">driver's license number</span></span>  <br/> <span data-ttu-id="c85ce-305">numero di patente del conducente</span><span class="sxs-lookup"><span data-stu-id="c85ce-305">driver's licence number</span></span>  <br/> <span data-ttu-id="c85ce-306">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="c85ce-306">driving license number</span></span>  <br/> <span data-ttu-id="c85ce-307">dlno#</span><span class="sxs-lookup"><span data-stu-id="c85ce-307">dlno#</span></span>  <br/> <span data-ttu-id="c85ce-308">kørekort</span><span class="sxs-lookup"><span data-stu-id="c85ce-308">kørekort</span></span>  <br/> <span data-ttu-id="c85ce-309">Kørekortnummer</span><span class="sxs-lookup"><span data-stu-id="c85ce-309">kørekortnummer</span></span>  <br/> |
   
## <a name="estonia"></a><span data-ttu-id="c85ce-310">Estonia</span><span class="sxs-lookup"><span data-stu-id="c85ce-310">Estonia</span></span>

### <a name="format"></a><span data-ttu-id="c85ce-311">Formato</span><span class="sxs-lookup"><span data-stu-id="c85ce-311">Format</span></span>

<span data-ttu-id="c85ce-312">Due lettere seguite da sei cifre</span><span class="sxs-lookup"><span data-stu-id="c85ce-312">Two letters followed by six digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="c85ce-313">Modello</span><span class="sxs-lookup"><span data-stu-id="c85ce-313">Pattern</span></span>

<span data-ttu-id="c85ce-314">Due lettere e sei cifre:</span><span class="sxs-lookup"><span data-stu-id="c85ce-314">Two letters and six digits:</span></span>
  
-  <span data-ttu-id="c85ce-315">Lettere "ET" (senza distinzione tra maiuscole e minuscole)</span><span class="sxs-lookup"><span data-stu-id="c85ce-315">The letters "ET" (not case-sensitive)</span></span> 
    
- <span data-ttu-id="c85ce-316">Sei cifre</span><span class="sxs-lookup"><span data-stu-id="c85ce-316">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="c85ce-317">Checksum</span><span class="sxs-lookup"><span data-stu-id="c85ce-317">Checksum</span></span>

<span data-ttu-id="c85ce-318">No</span><span class="sxs-lookup"><span data-stu-id="c85ce-318">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="c85ce-319">Definizione</span><span class="sxs-lookup"><span data-stu-id="c85ce-319">Definition</span></span>

<span data-ttu-id="c85ce-320">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="c85ce-320">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="c85ce-321">L'espressione `Regex_estonia_eu_driver's_license_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="c85ce-321">The regular expression  `Regex_estonia_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="c85ce-322">Viene trovata una `Keywords_estonia_eu_driver's_license_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="c85ce-322">A keyword from  `Keywords_estonia_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_estonia_eu_driver's_license_number" />
          <Match idRef="Keywords_estonia_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="c85ce-323">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="c85ce-323">Keywords</span></span>

<span data-ttu-id="c85ce-324">| |</span><span class="sxs-lookup"><span data-stu-id="c85ce-324"></span></span>
|<span data-ttu-id="c85ce-325">**Keywords_estonia_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="c85ce-325">**Keywords_estonia_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="c85ce-326">DL</span><span class="sxs-lookup"><span data-stu-id="c85ce-326">dl#</span></span>  <br/> <span data-ttu-id="c85ce-327">driver license</span><span class="sxs-lookup"><span data-stu-id="c85ce-327">driver license</span></span>  <br/> <span data-ttu-id="c85ce-328">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="c85ce-328">driver license number</span></span>  <br/> <span data-ttu-id="c85ce-329">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="c85ce-329">driver license number</span></span>  <br/> <span data-ttu-id="c85ce-330">patente di guida</span><span class="sxs-lookup"><span data-stu-id="c85ce-330">driver licence</span></span>  <br/> <span data-ttu-id="c85ce-331">driver Lic.</span><span class="sxs-lookup"><span data-stu-id="c85ce-331">drivers lic.</span></span>  <br/> <span data-ttu-id="c85ce-332">drivers license</span><span class="sxs-lookup"><span data-stu-id="c85ce-332">drivers license</span></span>  <br/> <span data-ttu-id="c85ce-333">drivers licence</span><span class="sxs-lookup"><span data-stu-id="c85ce-333">drivers licence</span></span>  <br/> <span data-ttu-id="c85ce-334">driver's license</span><span class="sxs-lookup"><span data-stu-id="c85ce-334">driver's license</span></span>  <br/> <span data-ttu-id="c85ce-335">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="c85ce-335">driver's license number</span></span>  <br/> <span data-ttu-id="c85ce-336">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="c85ce-336">driving license number</span></span>  <br/> <span data-ttu-id="c85ce-337">dlno#</span><span class="sxs-lookup"><span data-stu-id="c85ce-337">dlno#</span></span>  <br/> <span data-ttu-id="c85ce-338">permis de conduire</span><span class="sxs-lookup"><span data-stu-id="c85ce-338">permis de conduire</span></span>  <br/> |
   
## <a name="finland"></a><span data-ttu-id="c85ce-339">Finlandia</span><span class="sxs-lookup"><span data-stu-id="c85ce-339">Finland</span></span>

### <a name="format"></a><span data-ttu-id="c85ce-340">Formato</span><span class="sxs-lookup"><span data-stu-id="c85ce-340">Format</span></span>

<span data-ttu-id="c85ce-341">10 cifre contenenti una lineetta</span><span class="sxs-lookup"><span data-stu-id="c85ce-341">10 digits containing a hyphen</span></span>
  
### <a name="pattern"></a><span data-ttu-id="c85ce-342">Modello</span><span class="sxs-lookup"><span data-stu-id="c85ce-342">Pattern</span></span>

<span data-ttu-id="c85ce-343">10 cifre contenenti un trattino:</span><span class="sxs-lookup"><span data-stu-id="c85ce-343">10 digits containing a hyphen:</span></span>
  
-  <span data-ttu-id="c85ce-344">Sei cifre</span><span class="sxs-lookup"><span data-stu-id="c85ce-344">Six digits</span></span> 
    
- <span data-ttu-id="c85ce-345">Una lineetta</span><span class="sxs-lookup"><span data-stu-id="c85ce-345">A hyphen</span></span>
    
-  <span data-ttu-id="c85ce-346">Quattro cifre</span><span class="sxs-lookup"><span data-stu-id="c85ce-346">Four digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="c85ce-347">Checksum</span><span class="sxs-lookup"><span data-stu-id="c85ce-347">Checksum</span></span>

<span data-ttu-id="c85ce-348">No</span><span class="sxs-lookup"><span data-stu-id="c85ce-348">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="c85ce-349">Definizione</span><span class="sxs-lookup"><span data-stu-id="c85ce-349">Definition</span></span>

<span data-ttu-id="c85ce-350">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="c85ce-350">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="c85ce-351">L'espressione `Regex_finland_eu_driver's_license_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="c85ce-351">The regular expression  `Regex_finland_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="c85ce-352">Viene trovata una `Keywords_finland_eu_driver's_license_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="c85ce-352">A keyword from  `Keywords_finland_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_finland_eu_driver's_license_number" />
          <Match idRef="Keywords_finland_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="c85ce-353">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="c85ce-353">Keywords</span></span>

<span data-ttu-id="c85ce-354">| |</span><span class="sxs-lookup"><span data-stu-id="c85ce-354"></span></span>
|<span data-ttu-id="c85ce-355">**Keywords_finland_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="c85ce-355">**Keywords_finland_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="c85ce-356">DL</span><span class="sxs-lookup"><span data-stu-id="c85ce-356">dl#</span></span>  <br/> <span data-ttu-id="c85ce-357">driver license</span><span class="sxs-lookup"><span data-stu-id="c85ce-357">driver license</span></span>  <br/> <span data-ttu-id="c85ce-358">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="c85ce-358">driver license number</span></span>  <br/> <span data-ttu-id="c85ce-359">patente di guida</span><span class="sxs-lookup"><span data-stu-id="c85ce-359">driver licence</span></span>  <br/> <span data-ttu-id="c85ce-360">driver Lic.</span><span class="sxs-lookup"><span data-stu-id="c85ce-360">drivers lic.</span></span>  <br/> <span data-ttu-id="c85ce-361">drivers license</span><span class="sxs-lookup"><span data-stu-id="c85ce-361">drivers license</span></span>  <br/> <span data-ttu-id="c85ce-362">drivers licence</span><span class="sxs-lookup"><span data-stu-id="c85ce-362">drivers licence</span></span>  <br/> <span data-ttu-id="c85ce-363">driver's license</span><span class="sxs-lookup"><span data-stu-id="c85ce-363">driver's license</span></span>  <br/> <span data-ttu-id="c85ce-364">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="c85ce-364">driver's license number</span></span>  <br/> <span data-ttu-id="c85ce-365">numero di patente del conducente</span><span class="sxs-lookup"><span data-stu-id="c85ce-365">driver's licence number</span></span>  <br/> <span data-ttu-id="c85ce-366">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="c85ce-366">driving license number</span></span>  <br/> <span data-ttu-id="c85ce-367">dlno#</span><span class="sxs-lookup"><span data-stu-id="c85ce-367">dlno#</span></span>  <br/> <span data-ttu-id="c85ce-368">ajokortti</span><span class="sxs-lookup"><span data-stu-id="c85ce-368">ajokortti</span></span>  <br/> |
   
## <a name="france"></a><span data-ttu-id="c85ce-369">Francia</span><span class="sxs-lookup"><span data-stu-id="c85ce-369">France</span></span>

<span data-ttu-id="c85ce-370">Per informazioni dettagliate, vedere la sezione "numero della patente di Francia" in [che cosa cercano i tipi di informazioni riservate](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="c85ce-370">For details, see the section "France Driver's License Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="germany"></a><span data-ttu-id="c85ce-371">Germania</span><span class="sxs-lookup"><span data-stu-id="c85ce-371">Germany</span></span>

<span data-ttu-id="c85ce-372">Per informazioni dettagliate, vedere la sezione "numero di patente di guida tedesco" in [che cosa cercano i tipi di informazioni riservate](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="c85ce-372">For details, see the section "German Driver's License Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="greece"></a><span data-ttu-id="c85ce-373">Grecia</span><span class="sxs-lookup"><span data-stu-id="c85ce-373">Greece</span></span>

### <a name="format"></a><span data-ttu-id="c85ce-374">Formato</span><span class="sxs-lookup"><span data-stu-id="c85ce-374">Format</span></span>

<span data-ttu-id="c85ce-375">Nove cifre senza spazi e delimitatori</span><span class="sxs-lookup"><span data-stu-id="c85ce-375">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="c85ce-376">Modello</span><span class="sxs-lookup"><span data-stu-id="c85ce-376">Pattern</span></span>

 <span data-ttu-id="c85ce-377">9 cifre</span><span class="sxs-lookup"><span data-stu-id="c85ce-377">Nine digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="c85ce-378">Checksum</span><span class="sxs-lookup"><span data-stu-id="c85ce-378">Checksum</span></span>

<span data-ttu-id="c85ce-379">No</span><span class="sxs-lookup"><span data-stu-id="c85ce-379">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="c85ce-380">Definizione</span><span class="sxs-lookup"><span data-stu-id="c85ce-380">Definition</span></span>

<span data-ttu-id="c85ce-381">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="c85ce-381">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="c85ce-382">L'espressione `Regex_greece_eu_driver's_license_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="c85ce-382">The regular expression  `Regex_greece_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="c85ce-383">Viene trovata una `Keywords_greece_eu_driver's_license_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="c85ce-383">A keyword from  `Keywords_greece_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_greece_eu_driver's_license_number" />
          <Match idRef="Keywords_greece_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="c85ce-384">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="c85ce-384">Keywords</span></span>

<span data-ttu-id="c85ce-385">| |</span><span class="sxs-lookup"><span data-stu-id="c85ce-385"></span></span>
|<span data-ttu-id="c85ce-386">**Keywords_greece_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="c85ce-386">**Keywords_greece_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="c85ce-387">DlL</span><span class="sxs-lookup"><span data-stu-id="c85ce-387">dlL#</span></span>  <br/> <span data-ttu-id="c85ce-388">driver license</span><span class="sxs-lookup"><span data-stu-id="c85ce-388">driver license</span></span>  <br/> <span data-ttu-id="c85ce-389">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="c85ce-389">driver license number</span></span>  <br/> <span data-ttu-id="c85ce-390">patente di guida</span><span class="sxs-lookup"><span data-stu-id="c85ce-390">driver licence</span></span>  <br/> <span data-ttu-id="c85ce-391">driver Lic.</span><span class="sxs-lookup"><span data-stu-id="c85ce-391">drivers lic.</span></span>  <br/> <span data-ttu-id="c85ce-392">drivers license</span><span class="sxs-lookup"><span data-stu-id="c85ce-392">drivers license</span></span>  <br/> <span data-ttu-id="c85ce-393">drivers licence</span><span class="sxs-lookup"><span data-stu-id="c85ce-393">drivers licence</span></span>  <br/> <span data-ttu-id="c85ce-394">driver's license</span><span class="sxs-lookup"><span data-stu-id="c85ce-394">driver's license</span></span>  <br/> <span data-ttu-id="c85ce-395">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="c85ce-395">driver's license number</span></span>  <br/> <span data-ttu-id="c85ce-396">numero di patente del conducente</span><span class="sxs-lookup"><span data-stu-id="c85ce-396">driver's licence number</span></span>  <br/> <span data-ttu-id="c85ce-397">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="c85ce-397">driving license number</span></span>  <br/> <span data-ttu-id="c85ce-398">dlno#</span><span class="sxs-lookup"><span data-stu-id="c85ce-398">dlno#</span></span>  <br/> <span data-ttu-id="c85ce-399">δεια οδήγησης</span><span class="sxs-lookup"><span data-stu-id="c85ce-399">δεια οδήγησης</span></span>  <br/> <span data-ttu-id="c85ce-400">Adeia odigisis</span><span class="sxs-lookup"><span data-stu-id="c85ce-400">Adeia odigisis</span></span>  <br/> |
   
## <a name="hungary"></a><span data-ttu-id="c85ce-401">Ungheria</span><span class="sxs-lookup"><span data-stu-id="c85ce-401">Hungary</span></span>

### <a name="format"></a><span data-ttu-id="c85ce-402">Formato</span><span class="sxs-lookup"><span data-stu-id="c85ce-402">Format</span></span>

<span data-ttu-id="c85ce-403">Due lettere seguite da sei cifre</span><span class="sxs-lookup"><span data-stu-id="c85ce-403">Two letters followed by six digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="c85ce-404">Modello</span><span class="sxs-lookup"><span data-stu-id="c85ce-404">Pattern</span></span>

<span data-ttu-id="c85ce-405">Due lettere e sei cifre:</span><span class="sxs-lookup"><span data-stu-id="c85ce-405">Two letters and six digits:</span></span>
  
-  <span data-ttu-id="c85ce-406">Due lettere (senza distinzione tra maiuscole e minuscole)</span><span class="sxs-lookup"><span data-stu-id="c85ce-406">Two letters (not case-sensitive)</span></span> 
    
- <span data-ttu-id="c85ce-407">Sei cifre</span><span class="sxs-lookup"><span data-stu-id="c85ce-407">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="c85ce-408">Checksum</span><span class="sxs-lookup"><span data-stu-id="c85ce-408">Checksum</span></span>

<span data-ttu-id="c85ce-409">No</span><span class="sxs-lookup"><span data-stu-id="c85ce-409">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="c85ce-410">Definizione</span><span class="sxs-lookup"><span data-stu-id="c85ce-410">Definition</span></span>

<span data-ttu-id="c85ce-411">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="c85ce-411">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="c85ce-412">L'espressione `Regex_hungary_eu_driver's_license_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="c85ce-412">The regular expression  `Regex_hungary_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="c85ce-413">Viene trovata una `Keywords_hungary_eu_driver's_license_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="c85ce-413">A keyword from  `Keywords_hungary_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_hungary_eu_driver's_license_number" />
          <Match idRef="Keywords_hungary_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="c85ce-414">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="c85ce-414">Keywords</span></span>

<span data-ttu-id="c85ce-415">| |</span><span class="sxs-lookup"><span data-stu-id="c85ce-415"></span></span>
|<span data-ttu-id="c85ce-416">**Keywords_hungary_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="c85ce-416">**Keywords_hungary_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="c85ce-417">DL</span><span class="sxs-lookup"><span data-stu-id="c85ce-417">dl#</span></span>  <br/> <span data-ttu-id="c85ce-418">driver license</span><span class="sxs-lookup"><span data-stu-id="c85ce-418">driver license</span></span>  <br/> <span data-ttu-id="c85ce-419">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="c85ce-419">driver license number</span></span>  <br/> <span data-ttu-id="c85ce-420">patente di guida</span><span class="sxs-lookup"><span data-stu-id="c85ce-420">driver licence</span></span>  <br/> <span data-ttu-id="c85ce-421">driver Lic.</span><span class="sxs-lookup"><span data-stu-id="c85ce-421">drivers lic.</span></span>  <br/> <span data-ttu-id="c85ce-422">drivers license</span><span class="sxs-lookup"><span data-stu-id="c85ce-422">drivers license</span></span>  <br/> <span data-ttu-id="c85ce-423">drivers licence</span><span class="sxs-lookup"><span data-stu-id="c85ce-423">drivers licence</span></span>  <br/> <span data-ttu-id="c85ce-424">driver's license</span><span class="sxs-lookup"><span data-stu-id="c85ce-424">driver's license</span></span>  <br/> <span data-ttu-id="c85ce-425">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="c85ce-425">driver's license number</span></span>  <br/> <span data-ttu-id="c85ce-426">numero di patente del conducente</span><span class="sxs-lookup"><span data-stu-id="c85ce-426">driver's licence number</span></span>  <br/> <span data-ttu-id="c85ce-427">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="c85ce-427">driving license number</span></span>  <br/> <span data-ttu-id="c85ce-428">dlno#</span><span class="sxs-lookup"><span data-stu-id="c85ce-428">dlno#</span></span>  <br/> <span data-ttu-id="c85ce-429">vezetoi engedely</span><span class="sxs-lookup"><span data-stu-id="c85ce-429">vezetoi engedely</span></span>  <br/> |
   
## <a name="ireland"></a><span data-ttu-id="c85ce-430">Irlanda</span><span class="sxs-lookup"><span data-stu-id="c85ce-430">Ireland</span></span>

### <a name="format"></a><span data-ttu-id="c85ce-431">Formato</span><span class="sxs-lookup"><span data-stu-id="c85ce-431">Format</span></span>

<span data-ttu-id="c85ce-432">Sei cifre seguite da quattro lettere</span><span class="sxs-lookup"><span data-stu-id="c85ce-432">Six digits followed by four letters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="c85ce-433">Modello</span><span class="sxs-lookup"><span data-stu-id="c85ce-433">Pattern</span></span>

<span data-ttu-id="c85ce-434">Sei cifre e quattro lettere:</span><span class="sxs-lookup"><span data-stu-id="c85ce-434">Six digits and four letters:</span></span>
  
- <span data-ttu-id="c85ce-435">Sei cifre</span><span class="sxs-lookup"><span data-stu-id="c85ce-435">Six digits</span></span>
    
- <span data-ttu-id="c85ce-436">Quattro lettere (senza distinzione tra maiuscole e minuscole)</span><span class="sxs-lookup"><span data-stu-id="c85ce-436">Four letters (not case-sensitive)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="c85ce-437">Checksum</span><span class="sxs-lookup"><span data-stu-id="c85ce-437">Checksum</span></span>

<span data-ttu-id="c85ce-438">No</span><span class="sxs-lookup"><span data-stu-id="c85ce-438">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="c85ce-439">Definizione</span><span class="sxs-lookup"><span data-stu-id="c85ce-439">Definition</span></span>

<span data-ttu-id="c85ce-440">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="c85ce-440">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="c85ce-441">L'espressione `Regex_ireland_eu_driver's_license_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="c85ce-441">The regular expression  `Regex_ireland_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="c85ce-442">Viene trovata una `Keywords_ireland_eu_driver's_license_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="c85ce-442">A keyword from  `Keywords_ireland_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_ireland_eu_driver's_license_number" />
          <Match idRef="Keywords_ireland_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="c85ce-443">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="c85ce-443">Keywords</span></span>

<span data-ttu-id="c85ce-444">| |</span><span class="sxs-lookup"><span data-stu-id="c85ce-444"></span></span>
|<span data-ttu-id="c85ce-445">**Keywords_ireland_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="c85ce-445">**Keywords_ireland_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="c85ce-446">DL</span><span class="sxs-lookup"><span data-stu-id="c85ce-446">dl#</span></span>  <br/> <span data-ttu-id="c85ce-447">driver license</span><span class="sxs-lookup"><span data-stu-id="c85ce-447">driver license</span></span>  <br/> <span data-ttu-id="c85ce-448">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="c85ce-448">driver license number</span></span>  <br/> <span data-ttu-id="c85ce-449">patente di guida</span><span class="sxs-lookup"><span data-stu-id="c85ce-449">driver licence</span></span>  <br/> <span data-ttu-id="c85ce-450">driver Lic.</span><span class="sxs-lookup"><span data-stu-id="c85ce-450">drivers lic.</span></span>  <br/> <span data-ttu-id="c85ce-451">drivers license</span><span class="sxs-lookup"><span data-stu-id="c85ce-451">drivers license</span></span>  <br/> <span data-ttu-id="c85ce-452">drivers licence</span><span class="sxs-lookup"><span data-stu-id="c85ce-452">drivers licence</span></span>  <br/> <span data-ttu-id="c85ce-453">driver's license</span><span class="sxs-lookup"><span data-stu-id="c85ce-453">driver's license</span></span>  <br/> <span data-ttu-id="c85ce-454">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="c85ce-454">driver's license number</span></span>  <br/> <span data-ttu-id="c85ce-455">numero di patente del conducente</span><span class="sxs-lookup"><span data-stu-id="c85ce-455">driver's licence number</span></span>  <br/> <span data-ttu-id="c85ce-456">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="c85ce-456">driving license number</span></span>  <br/> <span data-ttu-id="c85ce-457">dlno#</span><span class="sxs-lookup"><span data-stu-id="c85ce-457">dlno#</span></span>  <br/> <span data-ttu-id="c85ce-458">ceadúnas tiomána</span><span class="sxs-lookup"><span data-stu-id="c85ce-458">ceadúnas tiomána</span></span>  <br/> |
   
## <a name="italy"></a><span data-ttu-id="c85ce-459">Italia</span><span class="sxs-lookup"><span data-stu-id="c85ce-459">Italy</span></span>

<span data-ttu-id="c85ce-460">Per informazioni dettagliate, vedere la sezione "numero di licenza del conducente italiano" in [che cosa cercano i tipi di informazioni riservate](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="c85ce-460">For details, see the section "Italy Driver's License Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="latvia"></a><span data-ttu-id="c85ce-461">Lettonia</span><span class="sxs-lookup"><span data-stu-id="c85ce-461">Latvia</span></span>

### <a name="format"></a><span data-ttu-id="c85ce-462">Formato</span><span class="sxs-lookup"><span data-stu-id="c85ce-462">Format</span></span>

<span data-ttu-id="c85ce-463">Tre lettere seguite da sei cifre</span><span class="sxs-lookup"><span data-stu-id="c85ce-463">Three letters followed by six digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="c85ce-464">Modello</span><span class="sxs-lookup"><span data-stu-id="c85ce-464">Pattern</span></span>

<span data-ttu-id="c85ce-465">Tre lettere e sei cifre:</span><span class="sxs-lookup"><span data-stu-id="c85ce-465">Three letters and six digits:</span></span>
  
-  <span data-ttu-id="c85ce-466">Tre lettere (senza distinzione tra maiuscole e minuscole)</span><span class="sxs-lookup"><span data-stu-id="c85ce-466">Three letters (not case-sensitive)</span></span> 
    
- <span data-ttu-id="c85ce-467">Sei cifre</span><span class="sxs-lookup"><span data-stu-id="c85ce-467">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="c85ce-468">Checksum</span><span class="sxs-lookup"><span data-stu-id="c85ce-468">Checksum</span></span>

<span data-ttu-id="c85ce-469">No</span><span class="sxs-lookup"><span data-stu-id="c85ce-469">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="c85ce-470">Definizione</span><span class="sxs-lookup"><span data-stu-id="c85ce-470">Definition</span></span>

<span data-ttu-id="c85ce-471">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="c85ce-471">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="c85ce-472">L'espressione `Regex_latvia_eu_driver's_license_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="c85ce-472">The regular expression  `Regex_latvia_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="c85ce-473">Viene trovata una `Keywords_latvia_eu_driver's_license_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="c85ce-473">A keyword from  `Keywords_latvia_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_latvia_eu_driver's_license_number" />
          <Match idRef="Keywords_latvia_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="c85ce-474">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="c85ce-474">Keywords</span></span>

<span data-ttu-id="c85ce-475">| |</span><span class="sxs-lookup"><span data-stu-id="c85ce-475"></span></span>
|<span data-ttu-id="c85ce-476">**Keywords_latvia_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="c85ce-476">**Keywords_latvia_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="c85ce-477">DL</span><span class="sxs-lookup"><span data-stu-id="c85ce-477">dl#</span></span>  <br/> <span data-ttu-id="c85ce-478">driver license</span><span class="sxs-lookup"><span data-stu-id="c85ce-478">driver license</span></span>  <br/> <span data-ttu-id="c85ce-479">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="c85ce-479">driver license number</span></span>  <br/> <span data-ttu-id="c85ce-480">patente di guida</span><span class="sxs-lookup"><span data-stu-id="c85ce-480">driver licence</span></span>  <br/> <span data-ttu-id="c85ce-481">driver Lic.</span><span class="sxs-lookup"><span data-stu-id="c85ce-481">drivers lic.</span></span>  <br/> <span data-ttu-id="c85ce-482">drivers license</span><span class="sxs-lookup"><span data-stu-id="c85ce-482">drivers license</span></span>  <br/> <span data-ttu-id="c85ce-483">drivers licence</span><span class="sxs-lookup"><span data-stu-id="c85ce-483">drivers licence</span></span>  <br/> <span data-ttu-id="c85ce-484">driver's license</span><span class="sxs-lookup"><span data-stu-id="c85ce-484">driver's license</span></span>  <br/> <span data-ttu-id="c85ce-485">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="c85ce-485">driver's license number</span></span>  <br/> <span data-ttu-id="c85ce-486">numero di patente del conducente</span><span class="sxs-lookup"><span data-stu-id="c85ce-486">driver's licence number</span></span>  <br/> <span data-ttu-id="c85ce-487">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="c85ce-487">driving license number</span></span>  <br/> <span data-ttu-id="c85ce-488">dlno#</span><span class="sxs-lookup"><span data-stu-id="c85ce-488">dlno#</span></span>  <br/> <span data-ttu-id="c85ce-489">autovadītāja apliecība</span><span class="sxs-lookup"><span data-stu-id="c85ce-489">autovadītāja apliecība</span></span>  <br/> |
   
## <a name="lithuania"></a><span data-ttu-id="c85ce-490">Lituania</span><span class="sxs-lookup"><span data-stu-id="c85ce-490">Lithuania</span></span>

### <a name="format"></a><span data-ttu-id="c85ce-491">Formato</span><span class="sxs-lookup"><span data-stu-id="c85ce-491">Format</span></span>

<span data-ttu-id="c85ce-492">Otto cifre senza spazi e delimitatori</span><span class="sxs-lookup"><span data-stu-id="c85ce-492">Eight digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="c85ce-493">Modello</span><span class="sxs-lookup"><span data-stu-id="c85ce-493">Pattern</span></span>

 <span data-ttu-id="c85ce-494">Otto cifre</span><span class="sxs-lookup"><span data-stu-id="c85ce-494">Eight digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="c85ce-495">Checksum</span><span class="sxs-lookup"><span data-stu-id="c85ce-495">Checksum</span></span>

<span data-ttu-id="c85ce-496">No</span><span class="sxs-lookup"><span data-stu-id="c85ce-496">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="c85ce-497">Definizione</span><span class="sxs-lookup"><span data-stu-id="c85ce-497">Definition</span></span>

<span data-ttu-id="c85ce-498">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="c85ce-498">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="c85ce-499">L'espressione `Regex_lithuania_eu_driver's_license_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="c85ce-499">The regular expression  `Regex_lithuania_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="c85ce-500">Viene trovata una `Keywords_lithuania_eu_driver's_license_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="c85ce-500">A keyword from  `Keywords_lithuania_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_lithuania_eu_driver's_license_number" />
          <Match idRef="Keywords_lithuania_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="c85ce-501">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="c85ce-501">Keywords</span></span>

<span data-ttu-id="c85ce-502">| |</span><span class="sxs-lookup"><span data-stu-id="c85ce-502"></span></span>
|<span data-ttu-id="c85ce-503">**Keywords_lithuania_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="c85ce-503">**Keywords_lithuania_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="c85ce-504">DL</span><span class="sxs-lookup"><span data-stu-id="c85ce-504">dl#</span></span>  <br/> <span data-ttu-id="c85ce-505">driver license</span><span class="sxs-lookup"><span data-stu-id="c85ce-505">driver license</span></span>  <br/> <span data-ttu-id="c85ce-506">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="c85ce-506">driver license number</span></span>  <br/> <span data-ttu-id="c85ce-507">patente di guida</span><span class="sxs-lookup"><span data-stu-id="c85ce-507">driver licence</span></span>  <br/> <span data-ttu-id="c85ce-508">driver Lic.</span><span class="sxs-lookup"><span data-stu-id="c85ce-508">drivers lic.</span></span>  <br/> <span data-ttu-id="c85ce-509">drivers license</span><span class="sxs-lookup"><span data-stu-id="c85ce-509">drivers license</span></span>  <br/> <span data-ttu-id="c85ce-510">drivers licence</span><span class="sxs-lookup"><span data-stu-id="c85ce-510">drivers licence</span></span>  <br/> <span data-ttu-id="c85ce-511">driver's license</span><span class="sxs-lookup"><span data-stu-id="c85ce-511">driver's license</span></span>  <br/> <span data-ttu-id="c85ce-512">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="c85ce-512">driver's license number</span></span>  <br/> <span data-ttu-id="c85ce-513">numero di patente del conducente</span><span class="sxs-lookup"><span data-stu-id="c85ce-513">driver's licence number</span></span>  <br/> <span data-ttu-id="c85ce-514">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="c85ce-514">driving license number</span></span>  <br/> <span data-ttu-id="c85ce-515">dlno#</span><span class="sxs-lookup"><span data-stu-id="c85ce-515">dlno#</span></span>  <br/> <span data-ttu-id="c85ce-516">vairuotojo pažymėjimas</span><span class="sxs-lookup"><span data-stu-id="c85ce-516">vairuotojo pažymėjimas</span></span>  <br/> |
   
## <a name="luxemburg"></a><span data-ttu-id="c85ce-517">Lussemburgo</span><span class="sxs-lookup"><span data-stu-id="c85ce-517">Luxemburg</span></span>

### <a name="format"></a><span data-ttu-id="c85ce-518">Formato</span><span class="sxs-lookup"><span data-stu-id="c85ce-518">Format</span></span>

<span data-ttu-id="c85ce-519">Sei cifre senza spazi e delimitatori</span><span class="sxs-lookup"><span data-stu-id="c85ce-519">Six digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="c85ce-520">Modello</span><span class="sxs-lookup"><span data-stu-id="c85ce-520">Pattern</span></span>

 <span data-ttu-id="c85ce-521">Sei cifre</span><span class="sxs-lookup"><span data-stu-id="c85ce-521">Six digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="c85ce-522">Checksum</span><span class="sxs-lookup"><span data-stu-id="c85ce-522">Checksum</span></span>

<span data-ttu-id="c85ce-523">No</span><span class="sxs-lookup"><span data-stu-id="c85ce-523">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="c85ce-524">Definizione</span><span class="sxs-lookup"><span data-stu-id="c85ce-524">Definition</span></span>

<span data-ttu-id="c85ce-525">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="c85ce-525">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="c85ce-526">L'espressione `Regex_luxemburg_eu_driver's_license_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="c85ce-526">The regular expression  `Regex_luxemburg_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="c85ce-527">Viene trovata una `Keywords_luxemburg_eu_driver's_license_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="c85ce-527">A keyword from  `Keywords_luxemburg_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_luxemburg_eu_driver's_license_number" />
          <Match idRef="Keywords_luxemburg_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="c85ce-528">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="c85ce-528">Keywords</span></span>

<span data-ttu-id="c85ce-529">| |</span><span class="sxs-lookup"><span data-stu-id="c85ce-529"></span></span>
|<span data-ttu-id="c85ce-530">**Keywords_luxemburg_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="c85ce-530">**Keywords_luxemburg_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="c85ce-531">DL</span><span class="sxs-lookup"><span data-stu-id="c85ce-531">dl#</span></span>  <br/> <span data-ttu-id="c85ce-532">driver license</span><span class="sxs-lookup"><span data-stu-id="c85ce-532">driver license</span></span>  <br/> <span data-ttu-id="c85ce-533">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="c85ce-533">driver license number</span></span>  <br/> <span data-ttu-id="c85ce-534">patente di guida</span><span class="sxs-lookup"><span data-stu-id="c85ce-534">driver licence</span></span>  <br/> <span data-ttu-id="c85ce-535">driver Lic.</span><span class="sxs-lookup"><span data-stu-id="c85ce-535">drivers lic.</span></span>  <br/> <span data-ttu-id="c85ce-536">drivers license</span><span class="sxs-lookup"><span data-stu-id="c85ce-536">drivers license</span></span>  <br/> <span data-ttu-id="c85ce-537">drivers licence</span><span class="sxs-lookup"><span data-stu-id="c85ce-537">drivers licence</span></span>  <br/> <span data-ttu-id="c85ce-538">driver's license</span><span class="sxs-lookup"><span data-stu-id="c85ce-538">driver's license</span></span>  <br/> <span data-ttu-id="c85ce-539">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="c85ce-539">driver's license number</span></span>  <br/> <span data-ttu-id="c85ce-540">numero di patente del conducente</span><span class="sxs-lookup"><span data-stu-id="c85ce-540">driver's licence number</span></span>  <br/> <span data-ttu-id="c85ce-541">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="c85ce-541">driving license number</span></span>  <br/> <span data-ttu-id="c85ce-542">dlno#</span><span class="sxs-lookup"><span data-stu-id="c85ce-542">dlno#</span></span>  <br/> <span data-ttu-id="c85ce-543">fahrerlaubnis</span><span class="sxs-lookup"><span data-stu-id="c85ce-543">fahrerlaubnis</span></span>  <br/> |
   
## <a name="malta"></a><span data-ttu-id="c85ce-544">Malta</span><span class="sxs-lookup"><span data-stu-id="c85ce-544">Malta</span></span>

### <a name="format"></a><span data-ttu-id="c85ce-545">Formato</span><span class="sxs-lookup"><span data-stu-id="c85ce-545">Format</span></span>

<span data-ttu-id="c85ce-546">Combinazione di due caratteri e di sei cifre nel modello specificato</span><span class="sxs-lookup"><span data-stu-id="c85ce-546">Combination of two characters and six digits in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="c85ce-547">Modello</span><span class="sxs-lookup"><span data-stu-id="c85ce-547">Pattern</span></span>

<span data-ttu-id="c85ce-548">Combinazione di due caratteri e di sei cifre:</span><span class="sxs-lookup"><span data-stu-id="c85ce-548">Combination of two characters and six digits:</span></span>
  
- <span data-ttu-id="c85ce-549">Due caratteri (cifre o lettere, non con distinzione tra maiuscole e minuscole)</span><span class="sxs-lookup"><span data-stu-id="c85ce-549">Two characters (digits or letters, not case-sensitive)</span></span>
    
- <span data-ttu-id="c85ce-550">Uno spazio (facoltativo)</span><span class="sxs-lookup"><span data-stu-id="c85ce-550">A space (optional)</span></span>
    
- <span data-ttu-id="c85ce-551">Tre cifre</span><span class="sxs-lookup"><span data-stu-id="c85ce-551">Three digits</span></span>
    
- <span data-ttu-id="c85ce-552">Uno spazio (facoltativo)</span><span class="sxs-lookup"><span data-stu-id="c85ce-552">A space (optional)</span></span>
    
- <span data-ttu-id="c85ce-553">Tre cifre</span><span class="sxs-lookup"><span data-stu-id="c85ce-553">Three digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="c85ce-554">Checksum</span><span class="sxs-lookup"><span data-stu-id="c85ce-554">Checksum</span></span>

<span data-ttu-id="c85ce-555">No</span><span class="sxs-lookup"><span data-stu-id="c85ce-555">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="c85ce-556">Definizione</span><span class="sxs-lookup"><span data-stu-id="c85ce-556">Definition</span></span>

<span data-ttu-id="c85ce-557">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="c85ce-557">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="c85ce-558">L'espressione `Regex_malta_eu_driver's_license_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="c85ce-558">The regular expression  `Regex_malta_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="c85ce-559">Viene trovata una `Keywords_malta_eu_driver's_license_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="c85ce-559">A keyword from  `Keywords_malta_eu_driver's_license_number` is found.</span></span> 
    
```
<!-- EU Driver's License Number -->
 <Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_malta_eu_driver's_license_number" />
          <Match idRef="Keywords_malta_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="c85ce-560">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="c85ce-560">Keywords</span></span>

<span data-ttu-id="c85ce-561">| |</span><span class="sxs-lookup"><span data-stu-id="c85ce-561"></span></span>
|<span data-ttu-id="c85ce-562">**Keywords_malta_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="c85ce-562">**Keywords_malta_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="c85ce-563">DL</span><span class="sxs-lookup"><span data-stu-id="c85ce-563">dl#</span></span>  <br/> <span data-ttu-id="c85ce-564">driver license</span><span class="sxs-lookup"><span data-stu-id="c85ce-564">driver license</span></span>  <br/> <span data-ttu-id="c85ce-565">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="c85ce-565">driver license number</span></span>  <br/> <span data-ttu-id="c85ce-566">patente di guida</span><span class="sxs-lookup"><span data-stu-id="c85ce-566">driver licence</span></span>  <br/> <span data-ttu-id="c85ce-567">driver Lic.</span><span class="sxs-lookup"><span data-stu-id="c85ce-567">drivers lic.</span></span>  <br/> <span data-ttu-id="c85ce-568">drivers license</span><span class="sxs-lookup"><span data-stu-id="c85ce-568">drivers license</span></span>  <br/> <span data-ttu-id="c85ce-569">drivers licence</span><span class="sxs-lookup"><span data-stu-id="c85ce-569">drivers licence</span></span>  <br/> <span data-ttu-id="c85ce-570">driver's license</span><span class="sxs-lookup"><span data-stu-id="c85ce-570">driver's license</span></span>  <br/> <span data-ttu-id="c85ce-571">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="c85ce-571">driver's license number</span></span>  <br/> <span data-ttu-id="c85ce-572">numero di patente del conducente</span><span class="sxs-lookup"><span data-stu-id="c85ce-572">driver's licence number</span></span>  <br/> <span data-ttu-id="c85ce-573">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="c85ce-573">driving license number</span></span>  <br/> <span data-ttu-id="c85ce-574">dlno#</span><span class="sxs-lookup"><span data-stu-id="c85ce-574">dlno#</span></span>  <br/> <span data-ttu-id="c85ce-575">Liċenzja TAS-sewqan</span><span class="sxs-lookup"><span data-stu-id="c85ce-575">liċenzja tas-sewqan</span></span>  <br/> |
   
## <a name="netherlands"></a><span data-ttu-id="c85ce-576">Paesi Bassi</span><span class="sxs-lookup"><span data-stu-id="c85ce-576">Netherlands</span></span>

### <a name="format"></a><span data-ttu-id="c85ce-577">Formato</span><span class="sxs-lookup"><span data-stu-id="c85ce-577">Format</span></span>

<span data-ttu-id="c85ce-578">10 cifre senza spazi e delimitatori</span><span class="sxs-lookup"><span data-stu-id="c85ce-578">10 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="c85ce-579">Modello</span><span class="sxs-lookup"><span data-stu-id="c85ce-579">Pattern</span></span>

<span data-ttu-id="c85ce-580">10 cifre</span><span class="sxs-lookup"><span data-stu-id="c85ce-580">10 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="c85ce-581">Checksum</span><span class="sxs-lookup"><span data-stu-id="c85ce-581">Checksum</span></span>

<span data-ttu-id="c85ce-582">No</span><span class="sxs-lookup"><span data-stu-id="c85ce-582">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="c85ce-583">Definizione</span><span class="sxs-lookup"><span data-stu-id="c85ce-583">Definition</span></span>

<span data-ttu-id="c85ce-584">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="c85ce-584">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="c85ce-585">L'espressione `Regex_netherlands_eu_driver's_license_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="c85ce-585">The regular expression  `Regex_netherlands_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="c85ce-586">Viene trovata una `Keywords_netherlands_eu_driver's_license_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="c85ce-586">A keyword from  `Keywords_netherlands_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_netherlands_eu_driver's_license_number" />
          <Match idRef="Keywords_netherlands_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="c85ce-587">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="c85ce-587">Keywords</span></span>

<span data-ttu-id="c85ce-588">| |</span><span class="sxs-lookup"><span data-stu-id="c85ce-588"></span></span>
|<span data-ttu-id="c85ce-589">**Keywords_netherlands_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="c85ce-589">**Keywords_netherlands_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="c85ce-590">DL</span><span class="sxs-lookup"><span data-stu-id="c85ce-590">dl#</span></span>  <br/> <span data-ttu-id="c85ce-591">driver license</span><span class="sxs-lookup"><span data-stu-id="c85ce-591">driver license</span></span>  <br/> <span data-ttu-id="c85ce-592">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="c85ce-592">driver license number</span></span>  <br/> <span data-ttu-id="c85ce-593">patente di guida</span><span class="sxs-lookup"><span data-stu-id="c85ce-593">driver licence</span></span>  <br/> <span data-ttu-id="c85ce-594">driver Lic.</span><span class="sxs-lookup"><span data-stu-id="c85ce-594">drivers lic.</span></span>  <br/> <span data-ttu-id="c85ce-595">drivers license</span><span class="sxs-lookup"><span data-stu-id="c85ce-595">drivers license</span></span>  <br/> <span data-ttu-id="c85ce-596">drivers licence</span><span class="sxs-lookup"><span data-stu-id="c85ce-596">drivers licence</span></span>  <br/> <span data-ttu-id="c85ce-597">driver's license</span><span class="sxs-lookup"><span data-stu-id="c85ce-597">driver's license</span></span>  <br/> <span data-ttu-id="c85ce-598">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="c85ce-598">driver's license number</span></span>  <br/> <span data-ttu-id="c85ce-599">numero di patente del conducente</span><span class="sxs-lookup"><span data-stu-id="c85ce-599">driver's licence number</span></span>  <br/> <span data-ttu-id="c85ce-600">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="c85ce-600">driving license number</span></span>  <br/> <span data-ttu-id="c85ce-601">dlno#</span><span class="sxs-lookup"><span data-stu-id="c85ce-601">dlno#</span></span>  <br/> <span data-ttu-id="c85ce-602">permis de conduire</span><span class="sxs-lookup"><span data-stu-id="c85ce-602">permis de conduire</span></span>  <br/> <span data-ttu-id="c85ce-603">rijbewijs</span><span class="sxs-lookup"><span data-stu-id="c85ce-603">rijbewijs</span></span>  <br/> <span data-ttu-id="c85ce-604">rijbewijsnummer</span><span class="sxs-lookup"><span data-stu-id="c85ce-604">rijbewijsnummer</span></span>  <br/> |
   
## <a name="poland"></a><span data-ttu-id="c85ce-605">Polonia</span><span class="sxs-lookup"><span data-stu-id="c85ce-605">Poland</span></span>

### <a name="format"></a><span data-ttu-id="c85ce-606">Formato</span><span class="sxs-lookup"><span data-stu-id="c85ce-606">Format</span></span>

<span data-ttu-id="c85ce-607">14 cifre contenenti 2 barre</span><span class="sxs-lookup"><span data-stu-id="c85ce-607">14 digits containing 2 forward slashes</span></span>
  
### <a name="pattern"></a><span data-ttu-id="c85ce-608">Modello</span><span class="sxs-lookup"><span data-stu-id="c85ce-608">Pattern</span></span>

<span data-ttu-id="c85ce-609">14 cifre e 2 barre:</span><span class="sxs-lookup"><span data-stu-id="c85ce-609">14 digits and 2 forward slashes:</span></span>
  
-  <span data-ttu-id="c85ce-610">Cinque cifre</span><span class="sxs-lookup"><span data-stu-id="c85ce-610">Five digits</span></span> 
    
- <span data-ttu-id="c85ce-611">Una barra</span><span class="sxs-lookup"><span data-stu-id="c85ce-611">A forward slash</span></span>
    
- <span data-ttu-id="c85ce-612">Due cifre</span><span class="sxs-lookup"><span data-stu-id="c85ce-612">Two digits</span></span>
    
- <span data-ttu-id="c85ce-613">Una barra</span><span class="sxs-lookup"><span data-stu-id="c85ce-613">A forward slash</span></span>
    
- <span data-ttu-id="c85ce-614">Sette cifre</span><span class="sxs-lookup"><span data-stu-id="c85ce-614">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="c85ce-615">Checksum</span><span class="sxs-lookup"><span data-stu-id="c85ce-615">Checksum</span></span>

<span data-ttu-id="c85ce-616">No</span><span class="sxs-lookup"><span data-stu-id="c85ce-616">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="c85ce-617">Definizione</span><span class="sxs-lookup"><span data-stu-id="c85ce-617">Definition</span></span>

<span data-ttu-id="c85ce-618">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="c85ce-618">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="c85ce-619">L'espressione `Regex_poland_eu_driver's_license_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="c85ce-619">The regular expression  `Regex_poland_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="c85ce-620">Viene trovata una `Keywords_poland_eu_driver's_license_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="c85ce-620">A keyword from  `Keywords_poland_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_poland_eu_driver's_license_number" />
          <Match idRef="Keywords_poland_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="c85ce-621">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="c85ce-621">Keywords</span></span>

<span data-ttu-id="c85ce-622">| |</span><span class="sxs-lookup"><span data-stu-id="c85ce-622"></span></span>
|<span data-ttu-id="c85ce-623">**Keywords_poland_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="c85ce-623">**Keywords_poland_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="c85ce-624">DL</span><span class="sxs-lookup"><span data-stu-id="c85ce-624">dl#</span></span>  <br/> <span data-ttu-id="c85ce-625">driver license</span><span class="sxs-lookup"><span data-stu-id="c85ce-625">driver license</span></span>  <br/> <span data-ttu-id="c85ce-626">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="c85ce-626">driver license number</span></span>  <br/> <span data-ttu-id="c85ce-627">patente di guida</span><span class="sxs-lookup"><span data-stu-id="c85ce-627">driver licence</span></span>  <br/> <span data-ttu-id="c85ce-628">driver Lic.</span><span class="sxs-lookup"><span data-stu-id="c85ce-628">drivers lic.</span></span>  <br/> <span data-ttu-id="c85ce-629">drivers license</span><span class="sxs-lookup"><span data-stu-id="c85ce-629">drivers license</span></span>  <br/> <span data-ttu-id="c85ce-630">drivers licence</span><span class="sxs-lookup"><span data-stu-id="c85ce-630">drivers licence</span></span>  <br/> <span data-ttu-id="c85ce-631">driver's license</span><span class="sxs-lookup"><span data-stu-id="c85ce-631">driver's license</span></span>  <br/> <span data-ttu-id="c85ce-632">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="c85ce-632">driver's license number</span></span>  <br/> <span data-ttu-id="c85ce-633">numero di patente del conducente</span><span class="sxs-lookup"><span data-stu-id="c85ce-633">driver's licence number</span></span>  <br/> <span data-ttu-id="c85ce-634">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="c85ce-634">driving license number</span></span>  <br/> <span data-ttu-id="c85ce-635">dlno#</span><span class="sxs-lookup"><span data-stu-id="c85ce-635">dlno#</span></span>  <br/> <span data-ttu-id="c85ce-636">prawo jazdy</span><span class="sxs-lookup"><span data-stu-id="c85ce-636">prawo jazdy</span></span>  <br/> |
   
## <a name="portugal"></a><span data-ttu-id="c85ce-637">Portogallo</span><span class="sxs-lookup"><span data-stu-id="c85ce-637">Portugal</span></span>

### <a name="format"></a><span data-ttu-id="c85ce-638">Formato</span><span class="sxs-lookup"><span data-stu-id="c85ce-638">Format</span></span>

<span data-ttu-id="c85ce-639">Due lettere seguite da un numero di sette numeri nel modello specificato</span><span class="sxs-lookup"><span data-stu-id="c85ce-639">Two letters followed by a seven numbers in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="c85ce-640">Modello</span><span class="sxs-lookup"><span data-stu-id="c85ce-640">Pattern</span></span>

<span data-ttu-id="c85ce-641">Due lettere seguite da sette numeri con caratteri speciali:</span><span class="sxs-lookup"><span data-stu-id="c85ce-641">Two letters followed by seven numbers with special characters:</span></span>
  
-  <span data-ttu-id="c85ce-642">Due lettere (senza distinzione tra maiuscole e minuscole)</span><span class="sxs-lookup"><span data-stu-id="c85ce-642">Two letters (not case-sensitive)</span></span> 
    
- <span data-ttu-id="c85ce-643">Una lineetta</span><span class="sxs-lookup"><span data-stu-id="c85ce-643">A hyphen</span></span>
    
- <span data-ttu-id="c85ce-644">Sei cifre</span><span class="sxs-lookup"><span data-stu-id="c85ce-644">Six digits</span></span>
    
- <span data-ttu-id="c85ce-645">Uno spazio</span><span class="sxs-lookup"><span data-stu-id="c85ce-645">A space</span></span>
    
- <span data-ttu-id="c85ce-646">Una cifra</span><span class="sxs-lookup"><span data-stu-id="c85ce-646">One digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="c85ce-647">Checksum</span><span class="sxs-lookup"><span data-stu-id="c85ce-647">Checksum</span></span>

<span data-ttu-id="c85ce-648">No</span><span class="sxs-lookup"><span data-stu-id="c85ce-648">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="c85ce-649">Definizione</span><span class="sxs-lookup"><span data-stu-id="c85ce-649">Definition</span></span>

<span data-ttu-id="c85ce-650">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="c85ce-650">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="c85ce-651">L'espressione `Regex_portugal_eu_driver's_license_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="c85ce-651">The regular expression  `Regex_portugal_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="c85ce-652">Viene trovata una `Keywords_portugal_eu_driver's_license_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="c85ce-652">A keyword from  `Keywords_portugal_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_portugal_eu_driver's_license_number" />
          <Match idRef="Keywords_portugal_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="c85ce-653">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="c85ce-653">Keywords</span></span>

<span data-ttu-id="c85ce-654">| |</span><span class="sxs-lookup"><span data-stu-id="c85ce-654"></span></span>
|<span data-ttu-id="c85ce-655">**Keywords_portugal_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="c85ce-655">**Keywords_portugal_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="c85ce-656">DL</span><span class="sxs-lookup"><span data-stu-id="c85ce-656">dl#</span></span>  <br/> <span data-ttu-id="c85ce-657">driver license</span><span class="sxs-lookup"><span data-stu-id="c85ce-657">driver license</span></span>  <br/> <span data-ttu-id="c85ce-658">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="c85ce-658">driver license number</span></span>  <br/> <span data-ttu-id="c85ce-659">patente di guida</span><span class="sxs-lookup"><span data-stu-id="c85ce-659">driver licence</span></span>  <br/> <span data-ttu-id="c85ce-660">driver Lic.</span><span class="sxs-lookup"><span data-stu-id="c85ce-660">drivers lic.</span></span>  <br/> <span data-ttu-id="c85ce-661">drivers license</span><span class="sxs-lookup"><span data-stu-id="c85ce-661">drivers license</span></span>  <br/> <span data-ttu-id="c85ce-662">drivers licence</span><span class="sxs-lookup"><span data-stu-id="c85ce-662">drivers licence</span></span>  <br/> <span data-ttu-id="c85ce-663">driver's license</span><span class="sxs-lookup"><span data-stu-id="c85ce-663">driver's license</span></span>  <br/> <span data-ttu-id="c85ce-664">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="c85ce-664">driver's license number</span></span>  <br/> <span data-ttu-id="c85ce-665">numero di patente del conducente</span><span class="sxs-lookup"><span data-stu-id="c85ce-665">driver's licence number</span></span>  <br/> <span data-ttu-id="c85ce-666">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="c85ce-666">driving license number</span></span>  <br/> <span data-ttu-id="c85ce-667">dlno#</span><span class="sxs-lookup"><span data-stu-id="c85ce-667">dlno#</span></span>  <br/> <span data-ttu-id="c85ce-668">carteira de motorista</span><span class="sxs-lookup"><span data-stu-id="c85ce-668">carteira de motorista</span></span>  <br/> |
   
## <a name="romania"></a><span data-ttu-id="c85ce-669">Romania</span><span class="sxs-lookup"><span data-stu-id="c85ce-669">Romania</span></span>

### <a name="format"></a><span data-ttu-id="c85ce-670">Formato</span><span class="sxs-lookup"><span data-stu-id="c85ce-670">Format</span></span>

<span data-ttu-id="c85ce-671">Un carattere seguito da otto cifre</span><span class="sxs-lookup"><span data-stu-id="c85ce-671">One character followed by eight digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="c85ce-672">Modello</span><span class="sxs-lookup"><span data-stu-id="c85ce-672">Pattern</span></span>

<span data-ttu-id="c85ce-673">Un carattere seguito da otto cifre:</span><span class="sxs-lookup"><span data-stu-id="c85ce-673">One character followed by eight digits:</span></span>
  
-  <span data-ttu-id="c85ce-674">Una lettera (senza distinzione tra maiuscole e minuscole) o cifra</span><span class="sxs-lookup"><span data-stu-id="c85ce-674">One letter (not case-sensitive) or digit</span></span> 
    
- <span data-ttu-id="c85ce-675">Otto cifre</span><span class="sxs-lookup"><span data-stu-id="c85ce-675">Eight digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="c85ce-676">Checksum</span><span class="sxs-lookup"><span data-stu-id="c85ce-676">Checksum</span></span>

<span data-ttu-id="c85ce-677">No</span><span class="sxs-lookup"><span data-stu-id="c85ce-677">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="c85ce-678">Definizione</span><span class="sxs-lookup"><span data-stu-id="c85ce-678">Definition</span></span>

<span data-ttu-id="c85ce-679">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="c85ce-679">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="c85ce-680">L'espressione `Regex_romania_eu_driver's_license_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="c85ce-680">The regular expression  `Regex_romania_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="c85ce-681">Viene trovata una `Keywords_romania_eu_driver's_license_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="c85ce-681">A keyword from  `Keywords_romania_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_romania_eu_driver's_license_number" />
          <Match idRef="Keywords_romania_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="c85ce-682">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="c85ce-682">Keywords</span></span>

<span data-ttu-id="c85ce-683">| |</span><span class="sxs-lookup"><span data-stu-id="c85ce-683"></span></span>
|<span data-ttu-id="c85ce-684">**Keywords_romania_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="c85ce-684">**Keywords_romania_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="c85ce-685">DL</span><span class="sxs-lookup"><span data-stu-id="c85ce-685">dl#</span></span>  <br/> <span data-ttu-id="c85ce-686">driver license</span><span class="sxs-lookup"><span data-stu-id="c85ce-686">driver license</span></span>  <br/> <span data-ttu-id="c85ce-687">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="c85ce-687">driver license number</span></span>  <br/> <span data-ttu-id="c85ce-688">patente di guida</span><span class="sxs-lookup"><span data-stu-id="c85ce-688">driver licence</span></span>  <br/> <span data-ttu-id="c85ce-689">driver Lic.</span><span class="sxs-lookup"><span data-stu-id="c85ce-689">drivers lic.</span></span>  <br/> <span data-ttu-id="c85ce-690">drivers license</span><span class="sxs-lookup"><span data-stu-id="c85ce-690">drivers license</span></span>  <br/> <span data-ttu-id="c85ce-691">drivers licence</span><span class="sxs-lookup"><span data-stu-id="c85ce-691">drivers licence</span></span>  <br/> <span data-ttu-id="c85ce-692">driver's license</span><span class="sxs-lookup"><span data-stu-id="c85ce-692">driver's license</span></span>  <br/> <span data-ttu-id="c85ce-693">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="c85ce-693">driver's license number</span></span>  <br/> <span data-ttu-id="c85ce-694">numero di patente del conducente</span><span class="sxs-lookup"><span data-stu-id="c85ce-694">driver's licence number</span></span>  <br/> <span data-ttu-id="c85ce-695">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="c85ce-695">driving license number</span></span>  <br/> <span data-ttu-id="c85ce-696">dlno#</span><span class="sxs-lookup"><span data-stu-id="c85ce-696">dlno#</span></span>  <br/> <span data-ttu-id="c85ce-697">Permis de conducere</span><span class="sxs-lookup"><span data-stu-id="c85ce-697">permis de conducere</span></span>  <br/> |
   
## <a name="slovakia"></a><span data-ttu-id="c85ce-698">Slovacchia</span><span class="sxs-lookup"><span data-stu-id="c85ce-698">Slovakia</span></span>

### <a name="format"></a><span data-ttu-id="c85ce-699">Formato</span><span class="sxs-lookup"><span data-stu-id="c85ce-699">Format</span></span>

<span data-ttu-id="c85ce-700">Un carattere seguito da sette cifre</span><span class="sxs-lookup"><span data-stu-id="c85ce-700">One character followed by seven digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="c85ce-701">Modello</span><span class="sxs-lookup"><span data-stu-id="c85ce-701">Pattern</span></span>

<span data-ttu-id="c85ce-702">Un carattere seguito da sette cifre</span><span class="sxs-lookup"><span data-stu-id="c85ce-702">One character followed by seven digits</span></span>
  
- <span data-ttu-id="c85ce-703">Una lettera (senza distinzione tra maiuscole e minuscole) o cifra</span><span class="sxs-lookup"><span data-stu-id="c85ce-703">One letter (not case-sensitive) or digit</span></span>
    
-  <span data-ttu-id="c85ce-704">Sette cifre</span><span class="sxs-lookup"><span data-stu-id="c85ce-704">Seven digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="c85ce-705">Checksum</span><span class="sxs-lookup"><span data-stu-id="c85ce-705">Checksum</span></span>

<span data-ttu-id="c85ce-706">No</span><span class="sxs-lookup"><span data-stu-id="c85ce-706">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="c85ce-707">Definizione</span><span class="sxs-lookup"><span data-stu-id="c85ce-707">Definition</span></span>

<span data-ttu-id="c85ce-708">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="c85ce-708">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="c85ce-709">L'espressione `Regex_slovakia_eu_driver's_license_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="c85ce-709">The regular expression  `Regex_slovakia_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="c85ce-710">Viene trovata una `Keywords_slovakia_eu_driver's_license_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="c85ce-710">A keyword from  `Keywords_slovakia_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovaknia_eu_driver's_license_number" />
          <Match idRef="Keywords_slovakia_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="c85ce-711">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="c85ce-711">Keywords</span></span>

<span data-ttu-id="c85ce-712">| |</span><span class="sxs-lookup"><span data-stu-id="c85ce-712"></span></span>
|<span data-ttu-id="c85ce-713">**Keywords_slovakia_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="c85ce-713">**Keywords_slovakia_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="c85ce-714">DL</span><span class="sxs-lookup"><span data-stu-id="c85ce-714">dl#</span></span>  <br/> <span data-ttu-id="c85ce-715">driver license</span><span class="sxs-lookup"><span data-stu-id="c85ce-715">driver license</span></span>  <br/> <span data-ttu-id="c85ce-716">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="c85ce-716">driver license number</span></span>  <br/> <span data-ttu-id="c85ce-717">patente di guida</span><span class="sxs-lookup"><span data-stu-id="c85ce-717">driver licence</span></span>  <br/> <span data-ttu-id="c85ce-718">driver Lic.</span><span class="sxs-lookup"><span data-stu-id="c85ce-718">drivers lic.</span></span>  <br/> <span data-ttu-id="c85ce-719">drivers license</span><span class="sxs-lookup"><span data-stu-id="c85ce-719">drivers license</span></span>  <br/> <span data-ttu-id="c85ce-720">drivers licence</span><span class="sxs-lookup"><span data-stu-id="c85ce-720">drivers licence</span></span>  <br/> <span data-ttu-id="c85ce-721">driver's license</span><span class="sxs-lookup"><span data-stu-id="c85ce-721">driver's license</span></span>  <br/> <span data-ttu-id="c85ce-722">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="c85ce-722">driver's license number</span></span>  <br/> <span data-ttu-id="c85ce-723">numero di patente del conducente</span><span class="sxs-lookup"><span data-stu-id="c85ce-723">driver's licence number</span></span>  <br/> <span data-ttu-id="c85ce-724">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="c85ce-724">driving license number</span></span>  <br/> <span data-ttu-id="c85ce-725">dlno#</span><span class="sxs-lookup"><span data-stu-id="c85ce-725">dlno#</span></span>  <br/> <span data-ttu-id="c85ce-726">vodičský preukaz</span><span class="sxs-lookup"><span data-stu-id="c85ce-726">vodičský preukaz</span></span>  <br/> |
   
## <a name="slovenia"></a><span data-ttu-id="c85ce-727">Slovenia</span><span class="sxs-lookup"><span data-stu-id="c85ce-727">Slovenia</span></span>

### <a name="format"></a><span data-ttu-id="c85ce-728">Formato</span><span class="sxs-lookup"><span data-stu-id="c85ce-728">Format</span></span>

<span data-ttu-id="c85ce-729">Nove cifre senza spazi e delimitatori</span><span class="sxs-lookup"><span data-stu-id="c85ce-729">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="c85ce-730">Modello</span><span class="sxs-lookup"><span data-stu-id="c85ce-730">Pattern</span></span>

<span data-ttu-id="c85ce-731">9 cifre</span><span class="sxs-lookup"><span data-stu-id="c85ce-731">Nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="c85ce-732">Checksum</span><span class="sxs-lookup"><span data-stu-id="c85ce-732">Checksum</span></span>

<span data-ttu-id="c85ce-733">No</span><span class="sxs-lookup"><span data-stu-id="c85ce-733">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="c85ce-734">Definizione</span><span class="sxs-lookup"><span data-stu-id="c85ce-734">Definition</span></span>

<span data-ttu-id="c85ce-735">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="c85ce-735">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="c85ce-736">L'espressione `Regex_slovenia_eu_driver's_license_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="c85ce-736">The regular expression  `Regex_slovenia_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="c85ce-737">Viene trovata una `Keywords_slovenia_eu_driver's_license_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="c85ce-737">A keyword from  `Keywords_slovenia_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovenia_eu_driver's_license_number" />
          <Match idRef="Keywords_slovenia_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="c85ce-738">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="c85ce-738">Keywords</span></span>

<span data-ttu-id="c85ce-739">| |</span><span class="sxs-lookup"><span data-stu-id="c85ce-739"></span></span>
|<span data-ttu-id="c85ce-740">**Keywords_slovenia_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="c85ce-740">**Keywords_slovenia_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="c85ce-741">DL</span><span class="sxs-lookup"><span data-stu-id="c85ce-741">dl#</span></span>  <br/> <span data-ttu-id="c85ce-742">driver license</span><span class="sxs-lookup"><span data-stu-id="c85ce-742">driver license</span></span>  <br/> <span data-ttu-id="c85ce-743">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="c85ce-743">driver license number</span></span>  <br/> <span data-ttu-id="c85ce-744">patente di guida</span><span class="sxs-lookup"><span data-stu-id="c85ce-744">driver licence</span></span>  <br/> <span data-ttu-id="c85ce-745">driver Lic.</span><span class="sxs-lookup"><span data-stu-id="c85ce-745">drivers lic.</span></span>  <br/> <span data-ttu-id="c85ce-746">drivers license</span><span class="sxs-lookup"><span data-stu-id="c85ce-746">drivers license</span></span>  <br/> <span data-ttu-id="c85ce-747">drivers licence</span><span class="sxs-lookup"><span data-stu-id="c85ce-747">drivers licence</span></span>  <br/> <span data-ttu-id="c85ce-748">driver's license</span><span class="sxs-lookup"><span data-stu-id="c85ce-748">driver's license</span></span>  <br/> <span data-ttu-id="c85ce-749">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="c85ce-749">driver's license number</span></span>  <br/> <span data-ttu-id="c85ce-750">numero di patente del conducente</span><span class="sxs-lookup"><span data-stu-id="c85ce-750">driver's licence number</span></span>  <br/> <span data-ttu-id="c85ce-751">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="c85ce-751">driving license number</span></span>  <br/> <span data-ttu-id="c85ce-752">dlno#</span><span class="sxs-lookup"><span data-stu-id="c85ce-752">dlno#</span></span>  <br/> <span data-ttu-id="c85ce-753">vozniško dovoljenje</span><span class="sxs-lookup"><span data-stu-id="c85ce-753">vozniško dovoljenje</span></span>  <br/> |
   
## <a name="spain"></a><span data-ttu-id="c85ce-754">Spagna</span><span class="sxs-lookup"><span data-stu-id="c85ce-754">Spain</span></span>

### <a name="format"></a><span data-ttu-id="c85ce-755">Formato</span><span class="sxs-lookup"><span data-stu-id="c85ce-755">Format</span></span>

<span data-ttu-id="c85ce-756">Otto cifre seguite da un carattere</span><span class="sxs-lookup"><span data-stu-id="c85ce-756">Eight digits followed by one character</span></span>
  
### <a name="pattern"></a><span data-ttu-id="c85ce-757">Modello</span><span class="sxs-lookup"><span data-stu-id="c85ce-757">Pattern</span></span>

<span data-ttu-id="c85ce-758">Otto cifre seguite da un carattere:</span><span class="sxs-lookup"><span data-stu-id="c85ce-758">Eight digits followed by one character:</span></span>
  
-  <span data-ttu-id="c85ce-759">Otto cifre</span><span class="sxs-lookup"><span data-stu-id="c85ce-759">Eight digits</span></span> 
    
- <span data-ttu-id="c85ce-760">Una cifra o una lettera (senza distinzione tra maiuscole e minuscole)</span><span class="sxs-lookup"><span data-stu-id="c85ce-760">One digit or letter (not case-sensitive)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="c85ce-761">Checksum</span><span class="sxs-lookup"><span data-stu-id="c85ce-761">Checksum</span></span>

<span data-ttu-id="c85ce-762">Sì</span><span class="sxs-lookup"><span data-stu-id="c85ce-762">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="c85ce-763">Definizione</span><span class="sxs-lookup"><span data-stu-id="c85ce-763">Definition</span></span>

<span data-ttu-id="c85ce-764">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="c85ce-764">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="c85ce-765">La funzione `Func_spain_eu_driver's_license_number` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="c85ce-765">The function  `Func_spain_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="c85ce-766">Viene trovata una `Keywords_spain_eu_driver's_license_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="c85ce-766">A keyword from  `Keywords_spain_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_spain_eu_driver's_license_number" />
          <Match idRef="Keywords_spain_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="c85ce-767">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="c85ce-767">Keywords</span></span>

<span data-ttu-id="c85ce-768">| |</span><span class="sxs-lookup"><span data-stu-id="c85ce-768"></span></span>
|<span data-ttu-id="c85ce-769">**Keywords_spain_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="c85ce-769">**Keywords_spain_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="c85ce-770">dlno#</span><span class="sxs-lookup"><span data-stu-id="c85ce-770">dlno#</span></span>  <br/> <span data-ttu-id="c85ce-771">DL</span><span class="sxs-lookup"><span data-stu-id="c85ce-771">dl#</span></span>  <br/> <span data-ttu-id="c85ce-772">driver Lic.</span><span class="sxs-lookup"><span data-stu-id="c85ce-772">drivers lic.</span></span>  <br/> <span data-ttu-id="c85ce-773">patente di guida</span><span class="sxs-lookup"><span data-stu-id="c85ce-773">driver licence</span></span>  <br/> <span data-ttu-id="c85ce-774">driver license</span><span class="sxs-lookup"><span data-stu-id="c85ce-774">driver license</span></span>  <br/> <span data-ttu-id="c85ce-775">drivers licence</span><span class="sxs-lookup"><span data-stu-id="c85ce-775">drivers licence</span></span>  <br/> <span data-ttu-id="c85ce-776">drivers license</span><span class="sxs-lookup"><span data-stu-id="c85ce-776">drivers license</span></span>  <br/> <span data-ttu-id="c85ce-777">driver's licence</span><span class="sxs-lookup"><span data-stu-id="c85ce-777">driver's licence</span></span>  <br/> <span data-ttu-id="c85ce-778">driver's license</span><span class="sxs-lookup"><span data-stu-id="c85ce-778">driver's license</span></span>  <br/> <span data-ttu-id="c85ce-779">driving licence</span><span class="sxs-lookup"><span data-stu-id="c85ce-779">driving licence</span></span>  <br/> <span data-ttu-id="c85ce-780">driving license</span><span class="sxs-lookup"><span data-stu-id="c85ce-780">driving license</span></span>  <br/> <span data-ttu-id="c85ce-781">numero di patente del conducente</span><span class="sxs-lookup"><span data-stu-id="c85ce-781">driver licence number</span></span>  <br/> <span data-ttu-id="c85ce-782">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="c85ce-782">driver license number</span></span>  <br/> <span data-ttu-id="c85ce-783">numero di patente del conducente</span><span class="sxs-lookup"><span data-stu-id="c85ce-783">drivers licence number</span></span>  <br/> <span data-ttu-id="c85ce-784">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="c85ce-784">drivers license number</span></span>  <br/> <span data-ttu-id="c85ce-785">numero di patente del conducente</span><span class="sxs-lookup"><span data-stu-id="c85ce-785">driver's licence number</span></span>  <br/> <span data-ttu-id="c85ce-786">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="c85ce-786">driver's license number</span></span>  <br/> <span data-ttu-id="c85ce-787">numero di patente di guida</span><span class="sxs-lookup"><span data-stu-id="c85ce-787">driving licence number</span></span>  <br/> <span data-ttu-id="c85ce-788">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="c85ce-788">driving license number</span></span>  <br/> <span data-ttu-id="c85ce-789">permesso di guida</span><span class="sxs-lookup"><span data-stu-id="c85ce-789">driving permit</span></span>  <br/> <span data-ttu-id="c85ce-790">numero di licenza di guida</span><span class="sxs-lookup"><span data-stu-id="c85ce-790">driving permit number</span></span>  <br/> <span data-ttu-id="c85ce-791">Permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="c85ce-791">permiso de conducción</span></span>  <br/> <span data-ttu-id="c85ce-792">Permiso conducción</span><span class="sxs-lookup"><span data-stu-id="c85ce-792">permiso conducción</span></span>  <br/> <span data-ttu-id="c85ce-793">número licencia conducir</span><span class="sxs-lookup"><span data-stu-id="c85ce-793">número licencia conducir</span></span>  <br/> <span data-ttu-id="c85ce-794">número de carnet de conducir</span><span class="sxs-lookup"><span data-stu-id="c85ce-794">número de carnet de conducir</span></span>  <br/> <span data-ttu-id="c85ce-795">número carnet conducir</span><span class="sxs-lookup"><span data-stu-id="c85ce-795">número carnet conducir</span></span>  <br/> <span data-ttu-id="c85ce-796">licencia conducir</span><span class="sxs-lookup"><span data-stu-id="c85ce-796">licencia conducir</span></span>  <br/> <span data-ttu-id="c85ce-797">número de Permiso de conducir</span><span class="sxs-lookup"><span data-stu-id="c85ce-797">número de permiso de conducir</span></span>  <br/> <span data-ttu-id="c85ce-798">número de permiso conducir</span><span class="sxs-lookup"><span data-stu-id="c85ce-798">número de permiso conducir</span></span>  <br/> <span data-ttu-id="c85ce-799">número permiso conducir</span><span class="sxs-lookup"><span data-stu-id="c85ce-799">número permiso conducir</span></span>  <br/> <span data-ttu-id="c85ce-800">permiso conducir</span><span class="sxs-lookup"><span data-stu-id="c85ce-800">permiso conducir</span></span>  <br/> <span data-ttu-id="c85ce-801">licencia de manejo</span><span class="sxs-lookup"><span data-stu-id="c85ce-801">licencia de manejo</span></span>  <br/> <span data-ttu-id="c85ce-802">El carnet de conducir</span><span class="sxs-lookup"><span data-stu-id="c85ce-802">el carnet de conducir</span></span>  <br/> <span data-ttu-id="c85ce-803">carnet conducir</span><span class="sxs-lookup"><span data-stu-id="c85ce-803">carnet conducir</span></span>  <br/> |
   
## <a name="sweden"></a><span data-ttu-id="c85ce-804">Svezia</span><span class="sxs-lookup"><span data-stu-id="c85ce-804">Sweden</span></span>

### <a name="format"></a><span data-ttu-id="c85ce-805">Formato</span><span class="sxs-lookup"><span data-stu-id="c85ce-805">Format</span></span>

<span data-ttu-id="c85ce-806">Dieci cifre contenenti un segno meno</span><span class="sxs-lookup"><span data-stu-id="c85ce-806">Ten digits containing a hyphen</span></span>
  
### <a name="pattern"></a><span data-ttu-id="c85ce-807">Modello</span><span class="sxs-lookup"><span data-stu-id="c85ce-807">Pattern</span></span>

<span data-ttu-id="c85ce-808">Dieci cifre contenenti un trattino:</span><span class="sxs-lookup"><span data-stu-id="c85ce-808">Ten digits containing a hyphen:</span></span>
  
-  <span data-ttu-id="c85ce-809">Sei cifre</span><span class="sxs-lookup"><span data-stu-id="c85ce-809">Six digits</span></span> 
    
- <span data-ttu-id="c85ce-810">Una lineetta</span><span class="sxs-lookup"><span data-stu-id="c85ce-810">A hyphen</span></span>
    
- <span data-ttu-id="c85ce-811">Quattro cifre</span><span class="sxs-lookup"><span data-stu-id="c85ce-811">Four digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="c85ce-812">Checksum</span><span class="sxs-lookup"><span data-stu-id="c85ce-812">Checksum</span></span>

<span data-ttu-id="c85ce-813">No</span><span class="sxs-lookup"><span data-stu-id="c85ce-813">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="c85ce-814">Definizione</span><span class="sxs-lookup"><span data-stu-id="c85ce-814">Definition</span></span>

<span data-ttu-id="c85ce-815">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="c85ce-815">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="c85ce-816">L'espressione `Regex_sweden_eu_driver's_license_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="c85ce-816">The regular expression  `Regex_sweden_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="c85ce-817">Viene trovata una `Keywords_sweden_eu_driver's_license_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="c85ce-817">A keyword from  `Keywords_sweden_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_sweden_eu_driver's_license_number" />
          <Match idRef="Keywords_sweden_eu_driver's_license_number" />
        </Pattern>
</Entity> 
```

### <a name="keywords"></a><span data-ttu-id="c85ce-818">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="c85ce-818">Keywords</span></span>

<span data-ttu-id="c85ce-819">| |</span><span class="sxs-lookup"><span data-stu-id="c85ce-819"></span></span>
|<span data-ttu-id="c85ce-820">**Keywords_sweden_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="c85ce-820">**Keywords_sweden_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="c85ce-821">DL</span><span class="sxs-lookup"><span data-stu-id="c85ce-821">dl#</span></span>  <br/> <span data-ttu-id="c85ce-822">driver license</span><span class="sxs-lookup"><span data-stu-id="c85ce-822">driver license</span></span>  <br/> <span data-ttu-id="c85ce-823">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="c85ce-823">driver license number</span></span>  <br/> <span data-ttu-id="c85ce-824">patente di guida</span><span class="sxs-lookup"><span data-stu-id="c85ce-824">driver licence</span></span>  <br/> <span data-ttu-id="c85ce-825">driver Lic.</span><span class="sxs-lookup"><span data-stu-id="c85ce-825">drivers lic.</span></span>  <br/> <span data-ttu-id="c85ce-826">drivers license</span><span class="sxs-lookup"><span data-stu-id="c85ce-826">drivers license</span></span>  <br/> <span data-ttu-id="c85ce-827">drivers licence</span><span class="sxs-lookup"><span data-stu-id="c85ce-827">drivers licence</span></span>  <br/> <span data-ttu-id="c85ce-828">driver's license</span><span class="sxs-lookup"><span data-stu-id="c85ce-828">driver's license</span></span>  <br/> <span data-ttu-id="c85ce-829">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="c85ce-829">driver's license number</span></span>  <br/> <span data-ttu-id="c85ce-830">numero di patente del conducente</span><span class="sxs-lookup"><span data-stu-id="c85ce-830">driver's licence number</span></span>  <br/> <span data-ttu-id="c85ce-831">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="c85ce-831">driving license number</span></span>  <br/> <span data-ttu-id="c85ce-832">dlno#</span><span class="sxs-lookup"><span data-stu-id="c85ce-832">dlno#</span></span>  <br/> <span data-ttu-id="c85ce-833">körkort</span><span class="sxs-lookup"><span data-stu-id="c85ce-833">körkort</span></span>  <br/> |
   
## <a name="uk"></a><span data-ttu-id="c85ce-834">Regno Unito</span><span class="sxs-lookup"><span data-stu-id="c85ce-834">UK</span></span>

<span data-ttu-id="c85ce-835">Per informazioni dettagliate, vedere la sezione "Regno Unito</span><span class="sxs-lookup"><span data-stu-id="c85ce-835">For details, see the section "U.K.</span></span> <span data-ttu-id="c85ce-836">Numero della patente di guida "in [quello che cercano i tipi di informazioni riservate](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="c85ce-836">Driver's License Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="c85ce-837">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c85ce-837">See also</span></span>

[<span data-ttu-id="c85ce-838">Cosa individuano le tipologie di informazioni sensibili</span><span class="sxs-lookup"><span data-stu-id="c85ce-838">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)

