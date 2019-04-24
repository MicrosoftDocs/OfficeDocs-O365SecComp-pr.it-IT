---
title: Numero della patente di guida dell'Unione europea
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 8/17/2018
ms.audience: Admin
ms.topic: reference
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
description: In questo argomento viene illustrato l'aspetto di un criterio di prevenzione della perdita di dati (DLP) quando viene rilevato il tipo di informazioni riservate del numero di licenza del driver dell'Unione europea. Questo tipo di informazioni riservate definisce modelli, parole chiave e altre evidenze diverse per ogni paese.
ms.openlocfilehash: be9497c325866a670dff8d82b5170f4ca947c4ad
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "32255774"
---
# <a name="eu-drivers-license-number"></a><span data-ttu-id="dc776-104">Numero della patente di guida dell'Unione europea</span><span class="sxs-lookup"><span data-stu-id="dc776-104">EU Driver's License Number</span></span>

<span data-ttu-id="dc776-105">In questo argomento viene illustrato l'aspetto di un criterio di prevenzione della perdita di dati (DLP) quando viene rilevato il tipo di informazioni riservate del numero di licenza del driver dell'Unione europea.</span><span class="sxs-lookup"><span data-stu-id="dc776-105">This topic shows what a data loss prevention (DLP) policy looks for when it detects the EU Driver's License Number sensitive information type.</span></span> <span data-ttu-id="dc776-106">Questo tipo di informazioni riservate definisce modelli, parole chiave e altre evidenze diverse per ogni paese.</span><span class="sxs-lookup"><span data-stu-id="dc776-106">This sensitive information type defines different patterns, keywords, and other evidence for each country.</span></span>
  
## <a name="austria"></a><span data-ttu-id="dc776-107">Austria</span><span class="sxs-lookup"><span data-stu-id="dc776-107">Austria</span></span>

### <a name="format"></a><span data-ttu-id="dc776-108">Formato</span><span class="sxs-lookup"><span data-stu-id="dc776-108">Format</span></span>

<span data-ttu-id="dc776-109">Otto cifre senza spazi e delimitatori</span><span class="sxs-lookup"><span data-stu-id="dc776-109">Eight digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="dc776-110">Modello</span><span class="sxs-lookup"><span data-stu-id="dc776-110">Pattern</span></span>

<span data-ttu-id="dc776-111">Otto cifre</span><span class="sxs-lookup"><span data-stu-id="dc776-111">Eight digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="dc776-112">Checksum</span><span class="sxs-lookup"><span data-stu-id="dc776-112">Checksum</span></span>

<span data-ttu-id="dc776-113">No</span><span class="sxs-lookup"><span data-stu-id="dc776-113">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="dc776-114">Definizione</span><span class="sxs-lookup"><span data-stu-id="dc776-114">Definition</span></span>

<span data-ttu-id="dc776-115">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="dc776-115">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="dc776-116">L'espressione `Regex_austria_eu_driver's_license_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="dc776-116">The regular expression  `Regex_austria_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="dc776-117">Viene trovata una `Keywords_austria_eu_driver's_license_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="dc776-117">A keyword from  `Keywords_austria_eu_driver's_license_number` is found.</span></span> 
    
```
<!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_austria_eu_driver's_license_number" />
          <Match idRef="Keywords_austria_eu_driver's_license_number" />
        </Pattern>
    </Entity>

```

### <a name="keywords"></a><span data-ttu-id="dc776-118">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="dc776-118">Keywords</span></span>

<span data-ttu-id="dc776-119">| |</span><span class="sxs-lookup"><span data-stu-id="dc776-119"></span></span>
|<span data-ttu-id="dc776-120">**Keywords_austria_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="dc776-120">**Keywords_austria_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="dc776-121">DL</span><span class="sxs-lookup"><span data-stu-id="dc776-121">dl#</span></span>  <br/> <span data-ttu-id="dc776-122">driver license</span><span class="sxs-lookup"><span data-stu-id="dc776-122">driver license</span></span>  <br/> <span data-ttu-id="dc776-123">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="dc776-123">driver license number</span></span>  <br/> <span data-ttu-id="dc776-124">patente di guida</span><span class="sxs-lookup"><span data-stu-id="dc776-124">driver licence</span></span>  <br/> <span data-ttu-id="dc776-125">driver Lic.</span><span class="sxs-lookup"><span data-stu-id="dc776-125">drivers lic.</span></span>  <br/> <span data-ttu-id="dc776-126">drivers license</span><span class="sxs-lookup"><span data-stu-id="dc776-126">drivers license</span></span>  <br/> <span data-ttu-id="dc776-127">driver's licence</span><span class="sxs-lookup"><span data-stu-id="dc776-127">driver's licence</span></span>  <br/> <span data-ttu-id="dc776-128">driver's license</span><span class="sxs-lookup"><span data-stu-id="dc776-128">driver's license</span></span>  <br/> <span data-ttu-id="dc776-129">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="dc776-129">driver's license number</span></span>  <br/> <span data-ttu-id="dc776-130">numero di patente del conducente</span><span class="sxs-lookup"><span data-stu-id="dc776-130">driver's licence number</span></span>  <br/>  <span data-ttu-id="dc776-131">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="dc776-131">driving license number</span></span>  <br/> <span data-ttu-id="dc776-132">dlno #</span><span class="sxs-lookup"><span data-stu-id="dc776-132">dlno#</span></span>  <br/> <span data-ttu-id="dc776-133">fuhrerschein</span><span class="sxs-lookup"><span data-stu-id="dc776-133">fuhrerschein</span></span>  <br/> <span data-ttu-id="dc776-134">fuhrerschein Republik Osterreich</span><span class="sxs-lookup"><span data-stu-id="dc776-134">fuhrerschein republik osterreich</span></span>  <br/> |
   
## <a name="belgium"></a><span data-ttu-id="dc776-135">Belgio</span><span class="sxs-lookup"><span data-stu-id="dc776-135">Belgium</span></span>

### <a name="format"></a><span data-ttu-id="dc776-136">Formato</span><span class="sxs-lookup"><span data-stu-id="dc776-136">Format</span></span>

<span data-ttu-id="dc776-137">10 cifre senza spazi e delimitatori</span><span class="sxs-lookup"><span data-stu-id="dc776-137">10 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="dc776-138">Modello</span><span class="sxs-lookup"><span data-stu-id="dc776-138">Pattern</span></span>

<span data-ttu-id="dc776-139">10 cifre</span><span class="sxs-lookup"><span data-stu-id="dc776-139">10 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="dc776-140">Checksum</span><span class="sxs-lookup"><span data-stu-id="dc776-140">Checksum</span></span>

<span data-ttu-id="dc776-141">No</span><span class="sxs-lookup"><span data-stu-id="dc776-141">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="dc776-142">Definizione</span><span class="sxs-lookup"><span data-stu-id="dc776-142">Definition</span></span>

<span data-ttu-id="dc776-143">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="dc776-143">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="dc776-144">L'espressione `Regex_belgium_eu_driver's_license_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="dc776-144">The regular expression  `Regex_belgium_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="dc776-145">Viene trovata una `Keywords_belgium_eu_driver's_license_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="dc776-145">A keyword from  `Keywords_belgium_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_belgium_eu_driver's_license_number" />
          <Match idRef="Keywords_belgium_eu_driver's_license_number" />
        </Pattern>
</Entity>

```

### <a name="keywords"></a><span data-ttu-id="dc776-146">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="dc776-146">Keywords</span></span>

<span data-ttu-id="dc776-147">| |</span><span class="sxs-lookup"><span data-stu-id="dc776-147"></span></span>
|<span data-ttu-id="dc776-148">**Keywords__belgium_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="dc776-148">**Keywords__belgium_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="dc776-149">DL</span><span class="sxs-lookup"><span data-stu-id="dc776-149">dl#</span></span>  <br/> <span data-ttu-id="dc776-150">driver license</span><span class="sxs-lookup"><span data-stu-id="dc776-150">driver license</span></span>  <br/> <span data-ttu-id="dc776-151">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="dc776-151">driver license number</span></span>  <br/> <span data-ttu-id="dc776-152">patente di guida</span><span class="sxs-lookup"><span data-stu-id="dc776-152">driver licence</span></span>  <br/> <span data-ttu-id="dc776-153">driver Lic.</span><span class="sxs-lookup"><span data-stu-id="dc776-153">drivers lic.</span></span>  <br/> <span data-ttu-id="dc776-154">drivers license</span><span class="sxs-lookup"><span data-stu-id="dc776-154">drivers license</span></span>  <br/> <span data-ttu-id="dc776-155">drivers licence</span><span class="sxs-lookup"><span data-stu-id="dc776-155">drivers licence</span></span>  <br/> <span data-ttu-id="dc776-156">driver's license</span><span class="sxs-lookup"><span data-stu-id="dc776-156">driver's license</span></span>  <br/> <span data-ttu-id="dc776-157">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="dc776-157">driver's license number</span></span>  <br/> <span data-ttu-id="dc776-158">numero di patente del conducente</span><span class="sxs-lookup"><span data-stu-id="dc776-158">driver's licence number</span></span>  <br/> <span data-ttu-id="dc776-159">dlno #</span><span class="sxs-lookup"><span data-stu-id="dc776-159">dlno#</span></span>  <br/> <span data-ttu-id="dc776-160">Rijbewijs</span><span class="sxs-lookup"><span data-stu-id="dc776-160">rijbewijs</span></span>  <br/> <span data-ttu-id="dc776-161">rijbewijsnummer</span><span class="sxs-lookup"><span data-stu-id="dc776-161">rijbewijsnummer</span></span>  <br/> <span data-ttu-id="dc776-162">führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="dc776-162">führerscheinnummer</span></span>  <br/> <span data-ttu-id="dc776-163">fuhrerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="dc776-163">fuhrerscheinnummer</span></span>  <br/> <span data-ttu-id="dc776-164">fuehrerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="dc776-164">fuehrerscheinnummer</span></span>  <br/> <span data-ttu-id="dc776-165">Führerschein-Nr</span><span class="sxs-lookup"><span data-stu-id="dc776-165">führerschein- nr</span></span>  <br/> <span data-ttu-id="dc776-166">fuehrerschein-Nr</span><span class="sxs-lookup"><span data-stu-id="dc776-166">fuehrerschein- Nr</span></span>  <br/> <span data-ttu-id="dc776-167">fuehrerschein-Nr</span><span class="sxs-lookup"><span data-stu-id="dc776-167">fuehrerschein- nr</span></span>  <br/> |
   
## <a name="bulgaria"></a><span data-ttu-id="dc776-168">Bulgaria</span><span class="sxs-lookup"><span data-stu-id="dc776-168">Bulgaria</span></span>

### <a name="format"></a><span data-ttu-id="dc776-169">Formato</span><span class="sxs-lookup"><span data-stu-id="dc776-169">Format</span></span>

<span data-ttu-id="dc776-170">Nove cifre senza spazi e delimitatori</span><span class="sxs-lookup"><span data-stu-id="dc776-170">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="dc776-171">Modello</span><span class="sxs-lookup"><span data-stu-id="dc776-171">Pattern</span></span>

<span data-ttu-id="dc776-172">9 cifre</span><span class="sxs-lookup"><span data-stu-id="dc776-172">Nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="dc776-173">Checksum</span><span class="sxs-lookup"><span data-stu-id="dc776-173">Checksum</span></span>

<span data-ttu-id="dc776-174">No</span><span class="sxs-lookup"><span data-stu-id="dc776-174">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="dc776-175">Definizione</span><span class="sxs-lookup"><span data-stu-id="dc776-175">Definition</span></span>

<span data-ttu-id="dc776-176">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="dc776-176">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="dc776-177">L'espressione `Regex_bulgaria_eu_driver's_license_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="dc776-177">The regular expression  `Regex_bulgaria_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="dc776-178">Viene trovata una `Keywords_bulgaria_eu_driver's_license_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="dc776-178">A keyword from  `Keywords_bulgaria_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
             <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_bulgaria_eu_driver's_license_number" />
          <Match idRef="Keywords_bulgaria_eu_driver's_license_number" />
        </Pattern> 
</Entity>    

```

### <a name="keywords"></a><span data-ttu-id="dc776-179">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="dc776-179">Keywords</span></span>

<span data-ttu-id="dc776-180">| |</span><span class="sxs-lookup"><span data-stu-id="dc776-180"></span></span>
|<span data-ttu-id="dc776-181">**Keywords_bulgaria_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="dc776-181">**Keywords_bulgaria_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="dc776-182">DL</span><span class="sxs-lookup"><span data-stu-id="dc776-182">dl#</span></span>  <br/> <span data-ttu-id="dc776-183">driver license</span><span class="sxs-lookup"><span data-stu-id="dc776-183">driver license</span></span>  <br/> <span data-ttu-id="dc776-184">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="dc776-184">driver license number</span></span>  <br/> <span data-ttu-id="dc776-185">patente di guida</span><span class="sxs-lookup"><span data-stu-id="dc776-185">driver licence</span></span>  <br/> <span data-ttu-id="dc776-186">driver Lic.</span><span class="sxs-lookup"><span data-stu-id="dc776-186">drivers lic.</span></span>  <br/> <span data-ttu-id="dc776-187">drivers license</span><span class="sxs-lookup"><span data-stu-id="dc776-187">drivers license</span></span>  <br/> <span data-ttu-id="dc776-188">drivers licence</span><span class="sxs-lookup"><span data-stu-id="dc776-188">drivers licence</span></span>  <br/> <span data-ttu-id="dc776-189">driver's license</span><span class="sxs-lookup"><span data-stu-id="dc776-189">driver's license</span></span>  <br/> <span data-ttu-id="dc776-190">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="dc776-190">driver's license number</span></span>  <br/> <span data-ttu-id="dc776-191">numero di patente del conducente</span><span class="sxs-lookup"><span data-stu-id="dc776-191">driver's licence number</span></span>  <br/> <span data-ttu-id="dc776-192">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="dc776-192">driving license number</span></span>  <br/> <span data-ttu-id="dc776-193">dlno #</span><span class="sxs-lookup"><span data-stu-id="dc776-193">dlno#</span></span>  <br/> <span data-ttu-id="dc776-194">свидетелство за управление на мпс</span><span class="sxs-lookup"><span data-stu-id="dc776-194">свидетелство за управление на мпс</span></span>  <br/> <span data-ttu-id="dc776-195">свидетелство за управление на моторно превозно d'средство</span><span class="sxs-lookup"><span data-stu-id="dc776-195">свидетелство за управление на моторно превозно средство</span></span>  <br/> <span data-ttu-id="dc776-196">сумпс</span><span class="sxs-lookup"><span data-stu-id="dc776-196">сумпс</span></span>  <br/> <span data-ttu-id="dc776-197">шофьорска книжка</span><span class="sxs-lookup"><span data-stu-id="dc776-197">шофьорска книжка</span></span>  <br/> |
   
## <a name="croatia"></a><span data-ttu-id="dc776-198">Croazia</span><span class="sxs-lookup"><span data-stu-id="dc776-198">Croatia</span></span>

### <a name="format"></a><span data-ttu-id="dc776-199">Formato</span><span class="sxs-lookup"><span data-stu-id="dc776-199">Format</span></span>

<span data-ttu-id="dc776-200">Otto cifre senza spazi e delimitatori</span><span class="sxs-lookup"><span data-stu-id="dc776-200">Eight digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="dc776-201">Modello</span><span class="sxs-lookup"><span data-stu-id="dc776-201">Pattern</span></span>

<span data-ttu-id="dc776-202">Otto cifre</span><span class="sxs-lookup"><span data-stu-id="dc776-202">Eight digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="dc776-203">Checksum</span><span class="sxs-lookup"><span data-stu-id="dc776-203">Checksum</span></span>

<span data-ttu-id="dc776-204">No</span><span class="sxs-lookup"><span data-stu-id="dc776-204">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="dc776-205">Definizione</span><span class="sxs-lookup"><span data-stu-id="dc776-205">Definition</span></span>

<span data-ttu-id="dc776-206">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="dc776-206">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="dc776-207">L'espressione `Regex_croatia_eu_driver's_license_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="dc776-207">The regular expression  `Regex_croatia_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="dc776-208">Viene trovata una `Keywords_croatia_eu_driver's_license_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="dc776-208">A keyword from  `Keywords_croatia_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_croatia_eu_driver's_license_number" />
          <Match idRef="Keywords_croatia_eu_driver's_license_number" />
        </Pattern>
</Entity>

```

### <a name="keywords"></a><span data-ttu-id="dc776-209">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="dc776-209">Keywords</span></span>

<span data-ttu-id="dc776-210">| |</span><span class="sxs-lookup"><span data-stu-id="dc776-210"></span></span>
|<span data-ttu-id="dc776-211">**Keywords_croatia_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="dc776-211">**Keywords_croatia_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="dc776-212">DL</span><span class="sxs-lookup"><span data-stu-id="dc776-212">dl#</span></span>  <br/> <span data-ttu-id="dc776-213">driver license</span><span class="sxs-lookup"><span data-stu-id="dc776-213">driver license</span></span>  <br/> <span data-ttu-id="dc776-214">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="dc776-214">driver license number</span></span>  <br/> <span data-ttu-id="dc776-215">patente di guida</span><span class="sxs-lookup"><span data-stu-id="dc776-215">driver licence</span></span>  <br/> <span data-ttu-id="dc776-216">driver Lic.</span><span class="sxs-lookup"><span data-stu-id="dc776-216">drivers lic.</span></span>  <br/> <span data-ttu-id="dc776-217">drivers license</span><span class="sxs-lookup"><span data-stu-id="dc776-217">drivers license</span></span>  <br/> <span data-ttu-id="dc776-218">drivers licence</span><span class="sxs-lookup"><span data-stu-id="dc776-218">drivers licence</span></span>  <br/> <span data-ttu-id="dc776-219">driver's license</span><span class="sxs-lookup"><span data-stu-id="dc776-219">driver's license</span></span>  <br/> <span data-ttu-id="dc776-220">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="dc776-220">driver's license number</span></span>  <br/> <span data-ttu-id="dc776-221">numero di patente del conducente</span><span class="sxs-lookup"><span data-stu-id="dc776-221">driver's licence number</span></span>  <br/> <span data-ttu-id="dc776-222">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="dc776-222">driving license number</span></span>  <br/> <span data-ttu-id="dc776-223">dlno #</span><span class="sxs-lookup"><span data-stu-id="dc776-223">dlno#</span></span>  <br/> <span data-ttu-id="dc776-224">vozačka Dozvola</span><span class="sxs-lookup"><span data-stu-id="dc776-224">vozačka dozvola</span></span>  <br/> |
   
## <a name="cyprus"></a><span data-ttu-id="dc776-225">Cipro</span><span class="sxs-lookup"><span data-stu-id="dc776-225">Cyprus</span></span>

### <a name="format"></a><span data-ttu-id="dc776-226">Formato</span><span class="sxs-lookup"><span data-stu-id="dc776-226">Format</span></span>

<span data-ttu-id="dc776-227">12 cifre senza spazi e delimitatori</span><span class="sxs-lookup"><span data-stu-id="dc776-227">12 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="dc776-228">Modello</span><span class="sxs-lookup"><span data-stu-id="dc776-228">Pattern</span></span>

<span data-ttu-id="dc776-229">12 cifre</span><span class="sxs-lookup"><span data-stu-id="dc776-229">12 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="dc776-230">Checksum</span><span class="sxs-lookup"><span data-stu-id="dc776-230">Checksum</span></span>

<span data-ttu-id="dc776-231">No</span><span class="sxs-lookup"><span data-stu-id="dc776-231">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="dc776-232">Definizione</span><span class="sxs-lookup"><span data-stu-id="dc776-232">Definition</span></span>

<span data-ttu-id="dc776-233">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="dc776-233">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="dc776-234">L'espressione `Regex_cyprus_eu_driver's_license_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="dc776-234">The regular expression  `Regex_cyprus_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="dc776-235">Viene trovata una `Keywords_cyprus_eu_driver's_license_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="dc776-235">A keyword from  `Keywords_cyprus_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_cyprus_eu_driver's_license_number" />
          <Match idRef="Keywords_cyprus_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="dc776-236">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="dc776-236">Keywords</span></span>

<span data-ttu-id="dc776-237">| |</span><span class="sxs-lookup"><span data-stu-id="dc776-237"></span></span>
|<span data-ttu-id="dc776-238">**Keywords_cyprus_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="dc776-238">**Keywords_cyprus_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="dc776-239">DL</span><span class="sxs-lookup"><span data-stu-id="dc776-239">dl#</span></span>  <br/> <span data-ttu-id="dc776-240">driver license</span><span class="sxs-lookup"><span data-stu-id="dc776-240">driver license</span></span>  <br/> <span data-ttu-id="dc776-241">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="dc776-241">driver license number</span></span>  <br/> <span data-ttu-id="dc776-242">patente di guida</span><span class="sxs-lookup"><span data-stu-id="dc776-242">driver licence</span></span>  <br/> <span data-ttu-id="dc776-243">driver Lic.</span><span class="sxs-lookup"><span data-stu-id="dc776-243">drivers lic.</span></span>  <br/> <span data-ttu-id="dc776-244">drivers license</span><span class="sxs-lookup"><span data-stu-id="dc776-244">drivers license</span></span>  <br/> <span data-ttu-id="dc776-245">drivers licence</span><span class="sxs-lookup"><span data-stu-id="dc776-245">drivers licence</span></span>  <br/> <span data-ttu-id="dc776-246">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="dc776-246">driver's license number</span></span>  <br/> <span data-ttu-id="dc776-247">numero di patente del conducente</span><span class="sxs-lookup"><span data-stu-id="dc776-247">driver's licence number</span></span>  <br/> <span data-ttu-id="dc776-248">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="dc776-248">driving license number</span></span>  <br/> <span data-ttu-id="dc776-249">dlno #</span><span class="sxs-lookup"><span data-stu-id="dc776-249">dlno#</span></span>  <br/> <span data-ttu-id="dc776-250">άδεια οδήγησης</span><span class="sxs-lookup"><span data-stu-id="dc776-250">άδεια οδήγησης</span></span>  <br/> |
   
## <a name="czech-republic"></a><span data-ttu-id="dc776-251">Repubblica Ceca</span><span class="sxs-lookup"><span data-stu-id="dc776-251">Czech Republic</span></span>

### <a name="format"></a><span data-ttu-id="dc776-252">Formato</span><span class="sxs-lookup"><span data-stu-id="dc776-252">Format</span></span>

<span data-ttu-id="dc776-253">Due lettere seguite da sei cifre</span><span class="sxs-lookup"><span data-stu-id="dc776-253">Two letters followed by six digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="dc776-254">Modello</span><span class="sxs-lookup"><span data-stu-id="dc776-254">Pattern</span></span>

<span data-ttu-id="dc776-255">Otto lettere e cifre:</span><span class="sxs-lookup"><span data-stu-id="dc776-255">Eight letters and digits:</span></span>
  
- <span data-ttu-id="dc776-256">Due lettere (senza distinzione tra maiuscole e minuscole)</span><span class="sxs-lookup"><span data-stu-id="dc776-256">Two letters (not case-sensitive)</span></span>
    
- <span data-ttu-id="dc776-257">Uno spazio (facoltativo)</span><span class="sxs-lookup"><span data-stu-id="dc776-257">A space (optional)</span></span>
    
- <span data-ttu-id="dc776-258">Sei cifre</span><span class="sxs-lookup"><span data-stu-id="dc776-258">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="dc776-259">Checksum</span><span class="sxs-lookup"><span data-stu-id="dc776-259">Checksum</span></span>

<span data-ttu-id="dc776-260">No</span><span class="sxs-lookup"><span data-stu-id="dc776-260">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="dc776-261">Definizione</span><span class="sxs-lookup"><span data-stu-id="dc776-261">Definition</span></span>

<span data-ttu-id="dc776-262">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="dc776-262">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="dc776-263">L'espressione `Regex_czech_republic_eu_driver's_license_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="dc776-263">The regular expression  `Regex_czech_republic_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="dc776-264">Viene trovata una `Keywords_czech_republic_eu_driver's_license_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="dc776-264">A keyword from  `Keywords_czech_republic_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_czech_republic_eu_driver's_license_number" />
          <Match idRef="Keywords_czech_republic_eu_driver's_license_number" />
        </Pattern>
</Entity>

```

### <a name="keywords"></a><span data-ttu-id="dc776-265">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="dc776-265">Keywords</span></span>

<span data-ttu-id="dc776-266">| |</span><span class="sxs-lookup"><span data-stu-id="dc776-266"></span></span>
|<span data-ttu-id="dc776-267">**Keywords_czech_republic_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="dc776-267">**Keywords_czech_republic_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="dc776-268">DL</span><span class="sxs-lookup"><span data-stu-id="dc776-268">dl#</span></span>  <br/> <span data-ttu-id="dc776-269">driver license</span><span class="sxs-lookup"><span data-stu-id="dc776-269">driver license</span></span>  <br/> <span data-ttu-id="dc776-270">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="dc776-270">driver license number</span></span>  <br/> <span data-ttu-id="dc776-271">patente di guida</span><span class="sxs-lookup"><span data-stu-id="dc776-271">driver licence</span></span>  <br/> <span data-ttu-id="dc776-272">driver Lic.</span><span class="sxs-lookup"><span data-stu-id="dc776-272">drivers lic.</span></span>  <br/> <span data-ttu-id="dc776-273">drivers license</span><span class="sxs-lookup"><span data-stu-id="dc776-273">drivers license</span></span>  <br/> <span data-ttu-id="dc776-274">drivers licence</span><span class="sxs-lookup"><span data-stu-id="dc776-274">drivers licence</span></span>  <br/> <span data-ttu-id="dc776-275">driver's license</span><span class="sxs-lookup"><span data-stu-id="dc776-275">driver's license</span></span>  <br/> <span data-ttu-id="dc776-276">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="dc776-276">driver's license number</span></span>  <br/> <span data-ttu-id="dc776-277">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="dc776-277">driver's license number</span></span>  <br/> <span data-ttu-id="dc776-278">numero di patente del conducente</span><span class="sxs-lookup"><span data-stu-id="dc776-278">driver's licence number</span></span>  <br/> <span data-ttu-id="dc776-279">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="dc776-279">driving license number</span></span>  <br/> <span data-ttu-id="dc776-280">dlno #</span><span class="sxs-lookup"><span data-stu-id="dc776-280">dlno#</span></span>  <br/> <span data-ttu-id="dc776-281">řidičský prúkaz</span><span class="sxs-lookup"><span data-stu-id="dc776-281">řidičský prúkaz</span></span>  <br/> |
   
## <a name="denmark"></a><span data-ttu-id="dc776-282">Danimarca</span><span class="sxs-lookup"><span data-stu-id="dc776-282">Denmark</span></span>

### <a name="format"></a><span data-ttu-id="dc776-283">Formato</span><span class="sxs-lookup"><span data-stu-id="dc776-283">Format</span></span>

<span data-ttu-id="dc776-284">Otto cifre senza spazi e delimitatori</span><span class="sxs-lookup"><span data-stu-id="dc776-284">Eight digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="dc776-285">Modello</span><span class="sxs-lookup"><span data-stu-id="dc776-285">Pattern</span></span>

<span data-ttu-id="dc776-286">Otto cifre</span><span class="sxs-lookup"><span data-stu-id="dc776-286">Eight digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="dc776-287">Checksum</span><span class="sxs-lookup"><span data-stu-id="dc776-287">Checksum</span></span>

<span data-ttu-id="dc776-288">Sì</span><span class="sxs-lookup"><span data-stu-id="dc776-288">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="dc776-289">Definizione</span><span class="sxs-lookup"><span data-stu-id="dc776-289">Definition</span></span>

<span data-ttu-id="dc776-290">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="dc776-290">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="dc776-291">L'espressione `Regex_denmark_eu_driver's_license_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="dc776-291">The regular expression  `Regex_denmark_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="dc776-292">Viene trovata una `Keywords_denmark_eu_driver's_license_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="dc776-292">A keyword from  `Keywords_denmark_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_denmark_eu_driver's_license_number" />
          <Match idRef="Keywords_denmark_eu_driver's_license_number" />
        </Pattern>
</Entity>

```

### <a name="keywords"></a><span data-ttu-id="dc776-293">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="dc776-293">Keywords</span></span>

<span data-ttu-id="dc776-294">| |</span><span class="sxs-lookup"><span data-stu-id="dc776-294"></span></span>
|<span data-ttu-id="dc776-295">**Keywords_denmark_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="dc776-295">**Keywords_denmark_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="dc776-296">DL</span><span class="sxs-lookup"><span data-stu-id="dc776-296">dl#</span></span>  <br/> <span data-ttu-id="dc776-297">driver license</span><span class="sxs-lookup"><span data-stu-id="dc776-297">driver license</span></span>  <br/> <span data-ttu-id="dc776-298">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="dc776-298">driver license number</span></span>  <br/> <span data-ttu-id="dc776-299">patente di guida</span><span class="sxs-lookup"><span data-stu-id="dc776-299">driver licence</span></span>  <br/> <span data-ttu-id="dc776-300">driver Lic.</span><span class="sxs-lookup"><span data-stu-id="dc776-300">drivers lic.</span></span>  <br/> <span data-ttu-id="dc776-301">drivers license</span><span class="sxs-lookup"><span data-stu-id="dc776-301">drivers license</span></span>  <br/> <span data-ttu-id="dc776-302">drivers licence</span><span class="sxs-lookup"><span data-stu-id="dc776-302">drivers licence</span></span>  <br/> <span data-ttu-id="dc776-303">driver's license</span><span class="sxs-lookup"><span data-stu-id="dc776-303">driver's license</span></span>  <br/> <span data-ttu-id="dc776-304">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="dc776-304">driver's license number</span></span>  <br/> <span data-ttu-id="dc776-305">numero di patente del conducente</span><span class="sxs-lookup"><span data-stu-id="dc776-305">driver's licence number</span></span>  <br/> <span data-ttu-id="dc776-306">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="dc776-306">driving license number</span></span>  <br/> <span data-ttu-id="dc776-307">dlno #</span><span class="sxs-lookup"><span data-stu-id="dc776-307">dlno#</span></span>  <br/> <span data-ttu-id="dc776-308">kørekort</span><span class="sxs-lookup"><span data-stu-id="dc776-308">kørekort</span></span>  <br/> <span data-ttu-id="dc776-309">Kørekortnummer</span><span class="sxs-lookup"><span data-stu-id="dc776-309">kørekortnummer</span></span>  <br/> |
   
## <a name="estonia"></a><span data-ttu-id="dc776-310">Estonia</span><span class="sxs-lookup"><span data-stu-id="dc776-310">Estonia</span></span>

### <a name="format"></a><span data-ttu-id="dc776-311">Formato</span><span class="sxs-lookup"><span data-stu-id="dc776-311">Format</span></span>

<span data-ttu-id="dc776-312">Due lettere seguite da sei cifre</span><span class="sxs-lookup"><span data-stu-id="dc776-312">Two letters followed by six digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="dc776-313">Modello</span><span class="sxs-lookup"><span data-stu-id="dc776-313">Pattern</span></span>

<span data-ttu-id="dc776-314">Due lettere e sei cifre:</span><span class="sxs-lookup"><span data-stu-id="dc776-314">Two letters and six digits:</span></span>
  
-  <span data-ttu-id="dc776-315">Lettere "ET" (senza distinzione tra maiuscole e minuscole)</span><span class="sxs-lookup"><span data-stu-id="dc776-315">The letters "ET" (not case-sensitive)</span></span> 
    
- <span data-ttu-id="dc776-316">Sei cifre</span><span class="sxs-lookup"><span data-stu-id="dc776-316">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="dc776-317">Checksum</span><span class="sxs-lookup"><span data-stu-id="dc776-317">Checksum</span></span>

<span data-ttu-id="dc776-318">No</span><span class="sxs-lookup"><span data-stu-id="dc776-318">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="dc776-319">Definizione</span><span class="sxs-lookup"><span data-stu-id="dc776-319">Definition</span></span>

<span data-ttu-id="dc776-320">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="dc776-320">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="dc776-321">L'espressione `Regex_estonia_eu_driver's_license_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="dc776-321">The regular expression  `Regex_estonia_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="dc776-322">Viene trovata una `Keywords_estonia_eu_driver's_license_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="dc776-322">A keyword from  `Keywords_estonia_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_estonia_eu_driver's_license_number" />
          <Match idRef="Keywords_estonia_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="dc776-323">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="dc776-323">Keywords</span></span>

<span data-ttu-id="dc776-324">| |</span><span class="sxs-lookup"><span data-stu-id="dc776-324"></span></span>
|<span data-ttu-id="dc776-325">**Keywords_estonia_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="dc776-325">**Keywords_estonia_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="dc776-326">DL</span><span class="sxs-lookup"><span data-stu-id="dc776-326">dl#</span></span>  <br/> <span data-ttu-id="dc776-327">driver license</span><span class="sxs-lookup"><span data-stu-id="dc776-327">driver license</span></span>  <br/> <span data-ttu-id="dc776-328">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="dc776-328">driver license number</span></span>  <br/> <span data-ttu-id="dc776-329">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="dc776-329">driver license number</span></span>  <br/> <span data-ttu-id="dc776-330">patente di guida</span><span class="sxs-lookup"><span data-stu-id="dc776-330">driver licence</span></span>  <br/> <span data-ttu-id="dc776-331">driver Lic.</span><span class="sxs-lookup"><span data-stu-id="dc776-331">drivers lic.</span></span>  <br/> <span data-ttu-id="dc776-332">drivers license</span><span class="sxs-lookup"><span data-stu-id="dc776-332">drivers license</span></span>  <br/> <span data-ttu-id="dc776-333">drivers licence</span><span class="sxs-lookup"><span data-stu-id="dc776-333">drivers licence</span></span>  <br/> <span data-ttu-id="dc776-334">driver's license</span><span class="sxs-lookup"><span data-stu-id="dc776-334">driver's license</span></span>  <br/> <span data-ttu-id="dc776-335">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="dc776-335">driver's license number</span></span>  <br/> <span data-ttu-id="dc776-336">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="dc776-336">driving license number</span></span>  <br/> <span data-ttu-id="dc776-337">dlno #</span><span class="sxs-lookup"><span data-stu-id="dc776-337">dlno#</span></span>  <br/> <span data-ttu-id="dc776-338">permis de conduire</span><span class="sxs-lookup"><span data-stu-id="dc776-338">permis de conduire</span></span>  <br/> |
   
## <a name="finland"></a><span data-ttu-id="dc776-339">Finlandia</span><span class="sxs-lookup"><span data-stu-id="dc776-339">Finland</span></span>

### <a name="format"></a><span data-ttu-id="dc776-340">Formato</span><span class="sxs-lookup"><span data-stu-id="dc776-340">Format</span></span>

<span data-ttu-id="dc776-341">10 cifre contenenti una lineetta</span><span class="sxs-lookup"><span data-stu-id="dc776-341">10 digits containing a hyphen</span></span>
  
### <a name="pattern"></a><span data-ttu-id="dc776-342">Modello</span><span class="sxs-lookup"><span data-stu-id="dc776-342">Pattern</span></span>

<span data-ttu-id="dc776-343">10 cifre contenenti un trattino:</span><span class="sxs-lookup"><span data-stu-id="dc776-343">10 digits containing a hyphen:</span></span>
  
-  <span data-ttu-id="dc776-344">Sei cifre</span><span class="sxs-lookup"><span data-stu-id="dc776-344">Six digits</span></span> 
    
- <span data-ttu-id="dc776-345">Una lineetta</span><span class="sxs-lookup"><span data-stu-id="dc776-345">A hyphen</span></span>
    
-  <span data-ttu-id="dc776-346">Quattro cifre</span><span class="sxs-lookup"><span data-stu-id="dc776-346">Four digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="dc776-347">Checksum</span><span class="sxs-lookup"><span data-stu-id="dc776-347">Checksum</span></span>

<span data-ttu-id="dc776-348">No</span><span class="sxs-lookup"><span data-stu-id="dc776-348">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="dc776-349">Definizione</span><span class="sxs-lookup"><span data-stu-id="dc776-349">Definition</span></span>

<span data-ttu-id="dc776-350">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="dc776-350">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="dc776-351">L'espressione `Regex_finland_eu_driver's_license_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="dc776-351">The regular expression  `Regex_finland_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="dc776-352">Viene trovata una `Keywords_finland_eu_driver's_license_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="dc776-352">A keyword from  `Keywords_finland_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_finland_eu_driver's_license_number" />
          <Match idRef="Keywords_finland_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="dc776-353">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="dc776-353">Keywords</span></span>

<span data-ttu-id="dc776-354">| |</span><span class="sxs-lookup"><span data-stu-id="dc776-354"></span></span>
|<span data-ttu-id="dc776-355">**Keywords_finland_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="dc776-355">**Keywords_finland_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="dc776-356">DL</span><span class="sxs-lookup"><span data-stu-id="dc776-356">dl#</span></span>  <br/> <span data-ttu-id="dc776-357">driver license</span><span class="sxs-lookup"><span data-stu-id="dc776-357">driver license</span></span>  <br/> <span data-ttu-id="dc776-358">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="dc776-358">driver license number</span></span>  <br/> <span data-ttu-id="dc776-359">patente di guida</span><span class="sxs-lookup"><span data-stu-id="dc776-359">driver licence</span></span>  <br/> <span data-ttu-id="dc776-360">driver Lic.</span><span class="sxs-lookup"><span data-stu-id="dc776-360">drivers lic.</span></span>  <br/> <span data-ttu-id="dc776-361">drivers license</span><span class="sxs-lookup"><span data-stu-id="dc776-361">drivers license</span></span>  <br/> <span data-ttu-id="dc776-362">drivers licence</span><span class="sxs-lookup"><span data-stu-id="dc776-362">drivers licence</span></span>  <br/> <span data-ttu-id="dc776-363">driver's license</span><span class="sxs-lookup"><span data-stu-id="dc776-363">driver's license</span></span>  <br/> <span data-ttu-id="dc776-364">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="dc776-364">driver's license number</span></span>  <br/> <span data-ttu-id="dc776-365">numero di patente del conducente</span><span class="sxs-lookup"><span data-stu-id="dc776-365">driver's licence number</span></span>  <br/> <span data-ttu-id="dc776-366">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="dc776-366">driving license number</span></span>  <br/> <span data-ttu-id="dc776-367">dlno #</span><span class="sxs-lookup"><span data-stu-id="dc776-367">dlno#</span></span>  <br/> <span data-ttu-id="dc776-368">AJOKORTTI</span><span class="sxs-lookup"><span data-stu-id="dc776-368">ajokortti</span></span>  <br/> |
   
## <a name="france"></a><span data-ttu-id="dc776-369">Francia</span><span class="sxs-lookup"><span data-stu-id="dc776-369">France</span></span>

<span data-ttu-id="dc776-370">Per informazioni dettagliate, vedere la sezione "numero della patente di Francia" in [che cosa cercano i tipi di informazioni riservate](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="dc776-370">For details, see the section "France Driver's License Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="germany"></a><span data-ttu-id="dc776-371">Germania</span><span class="sxs-lookup"><span data-stu-id="dc776-371">Germany</span></span>

<span data-ttu-id="dc776-372">Per informazioni dettagliate, vedere la sezione "numero di patente di guida tedesco" in [che cosa cercano i tipi di informazioni riservate](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="dc776-372">For details, see the section "German Driver's License Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="greece"></a><span data-ttu-id="dc776-373">Grecia</span><span class="sxs-lookup"><span data-stu-id="dc776-373">Greece</span></span>

### <a name="format"></a><span data-ttu-id="dc776-374">Formato</span><span class="sxs-lookup"><span data-stu-id="dc776-374">Format</span></span>

<span data-ttu-id="dc776-375">Nove cifre senza spazi e delimitatori</span><span class="sxs-lookup"><span data-stu-id="dc776-375">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="dc776-376">Modello</span><span class="sxs-lookup"><span data-stu-id="dc776-376">Pattern</span></span>

 <span data-ttu-id="dc776-377">9 cifre</span><span class="sxs-lookup"><span data-stu-id="dc776-377">Nine digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="dc776-378">Checksum</span><span class="sxs-lookup"><span data-stu-id="dc776-378">Checksum</span></span>

<span data-ttu-id="dc776-379">No</span><span class="sxs-lookup"><span data-stu-id="dc776-379">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="dc776-380">Definizione</span><span class="sxs-lookup"><span data-stu-id="dc776-380">Definition</span></span>

<span data-ttu-id="dc776-381">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="dc776-381">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="dc776-382">L'espressione `Regex_greece_eu_driver's_license_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="dc776-382">The regular expression  `Regex_greece_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="dc776-383">Viene trovata una `Keywords_greece_eu_driver's_license_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="dc776-383">A keyword from  `Keywords_greece_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_greece_eu_driver's_license_number" />
          <Match idRef="Keywords_greece_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="dc776-384">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="dc776-384">Keywords</span></span>

<span data-ttu-id="dc776-385">| |</span><span class="sxs-lookup"><span data-stu-id="dc776-385"></span></span>
|<span data-ttu-id="dc776-386">**Keywords_greece_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="dc776-386">**Keywords_greece_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="dc776-387">DlL</span><span class="sxs-lookup"><span data-stu-id="dc776-387">dlL#</span></span>  <br/> <span data-ttu-id="dc776-388">driver license</span><span class="sxs-lookup"><span data-stu-id="dc776-388">driver license</span></span>  <br/> <span data-ttu-id="dc776-389">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="dc776-389">driver license number</span></span>  <br/> <span data-ttu-id="dc776-390">patente di guida</span><span class="sxs-lookup"><span data-stu-id="dc776-390">driver licence</span></span>  <br/> <span data-ttu-id="dc776-391">driver Lic.</span><span class="sxs-lookup"><span data-stu-id="dc776-391">drivers lic.</span></span>  <br/> <span data-ttu-id="dc776-392">drivers license</span><span class="sxs-lookup"><span data-stu-id="dc776-392">drivers license</span></span>  <br/> <span data-ttu-id="dc776-393">drivers licence</span><span class="sxs-lookup"><span data-stu-id="dc776-393">drivers licence</span></span>  <br/> <span data-ttu-id="dc776-394">driver's license</span><span class="sxs-lookup"><span data-stu-id="dc776-394">driver's license</span></span>  <br/> <span data-ttu-id="dc776-395">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="dc776-395">driver's license number</span></span>  <br/> <span data-ttu-id="dc776-396">numero di patente del conducente</span><span class="sxs-lookup"><span data-stu-id="dc776-396">driver's licence number</span></span>  <br/> <span data-ttu-id="dc776-397">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="dc776-397">driving license number</span></span>  <br/> <span data-ttu-id="dc776-398">dlno #</span><span class="sxs-lookup"><span data-stu-id="dc776-398">dlno#</span></span>  <br/> <span data-ttu-id="dc776-399">δεια οδήγησης</span><span class="sxs-lookup"><span data-stu-id="dc776-399">δεια οδήγησης</span></span>  <br/> <span data-ttu-id="dc776-400">Adeia odigisis</span><span class="sxs-lookup"><span data-stu-id="dc776-400">Adeia odigisis</span></span>  <br/> |
   
## <a name="hungary"></a><span data-ttu-id="dc776-401">Ungheria</span><span class="sxs-lookup"><span data-stu-id="dc776-401">Hungary</span></span>

### <a name="format"></a><span data-ttu-id="dc776-402">Formato</span><span class="sxs-lookup"><span data-stu-id="dc776-402">Format</span></span>

<span data-ttu-id="dc776-403">Due lettere seguite da sei cifre</span><span class="sxs-lookup"><span data-stu-id="dc776-403">Two letters followed by six digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="dc776-404">Modello</span><span class="sxs-lookup"><span data-stu-id="dc776-404">Pattern</span></span>

<span data-ttu-id="dc776-405">Due lettere e sei cifre:</span><span class="sxs-lookup"><span data-stu-id="dc776-405">Two letters and six digits:</span></span>
  
-  <span data-ttu-id="dc776-406">Due lettere (senza distinzione tra maiuscole e minuscole)</span><span class="sxs-lookup"><span data-stu-id="dc776-406">Two letters (not case-sensitive)</span></span> 
    
- <span data-ttu-id="dc776-407">Sei cifre</span><span class="sxs-lookup"><span data-stu-id="dc776-407">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="dc776-408">Checksum</span><span class="sxs-lookup"><span data-stu-id="dc776-408">Checksum</span></span>

<span data-ttu-id="dc776-409">No</span><span class="sxs-lookup"><span data-stu-id="dc776-409">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="dc776-410">Definizione</span><span class="sxs-lookup"><span data-stu-id="dc776-410">Definition</span></span>

<span data-ttu-id="dc776-411">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="dc776-411">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="dc776-412">L'espressione `Regex_hungary_eu_driver's_license_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="dc776-412">The regular expression  `Regex_hungary_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="dc776-413">Viene trovata una `Keywords_hungary_eu_driver's_license_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="dc776-413">A keyword from  `Keywords_hungary_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_hungary_eu_driver's_license_number" />
          <Match idRef="Keywords_hungary_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="dc776-414">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="dc776-414">Keywords</span></span>

<span data-ttu-id="dc776-415">| |</span><span class="sxs-lookup"><span data-stu-id="dc776-415"></span></span>
|<span data-ttu-id="dc776-416">**Keywords_hungary_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="dc776-416">**Keywords_hungary_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="dc776-417">DL</span><span class="sxs-lookup"><span data-stu-id="dc776-417">dl#</span></span>  <br/> <span data-ttu-id="dc776-418">driver license</span><span class="sxs-lookup"><span data-stu-id="dc776-418">driver license</span></span>  <br/> <span data-ttu-id="dc776-419">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="dc776-419">driver license number</span></span>  <br/> <span data-ttu-id="dc776-420">patente di guida</span><span class="sxs-lookup"><span data-stu-id="dc776-420">driver licence</span></span>  <br/> <span data-ttu-id="dc776-421">driver Lic.</span><span class="sxs-lookup"><span data-stu-id="dc776-421">drivers lic.</span></span>  <br/> <span data-ttu-id="dc776-422">drivers license</span><span class="sxs-lookup"><span data-stu-id="dc776-422">drivers license</span></span>  <br/> <span data-ttu-id="dc776-423">drivers licence</span><span class="sxs-lookup"><span data-stu-id="dc776-423">drivers licence</span></span>  <br/> <span data-ttu-id="dc776-424">driver's license</span><span class="sxs-lookup"><span data-stu-id="dc776-424">driver's license</span></span>  <br/> <span data-ttu-id="dc776-425">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="dc776-425">driver's license number</span></span>  <br/> <span data-ttu-id="dc776-426">numero di patente del conducente</span><span class="sxs-lookup"><span data-stu-id="dc776-426">driver's licence number</span></span>  <br/> <span data-ttu-id="dc776-427">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="dc776-427">driving license number</span></span>  <br/> <span data-ttu-id="dc776-428">dlno #</span><span class="sxs-lookup"><span data-stu-id="dc776-428">dlno#</span></span>  <br/> <span data-ttu-id="dc776-429">vezetoi engedely</span><span class="sxs-lookup"><span data-stu-id="dc776-429">vezetoi engedely</span></span>  <br/> |
   
## <a name="ireland"></a><span data-ttu-id="dc776-430">Irlanda</span><span class="sxs-lookup"><span data-stu-id="dc776-430">Ireland</span></span>

### <a name="format"></a><span data-ttu-id="dc776-431">Formato</span><span class="sxs-lookup"><span data-stu-id="dc776-431">Format</span></span>

<span data-ttu-id="dc776-432">Sei cifre seguite da quattro lettere</span><span class="sxs-lookup"><span data-stu-id="dc776-432">Six digits followed by four letters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="dc776-433">Modello</span><span class="sxs-lookup"><span data-stu-id="dc776-433">Pattern</span></span>

<span data-ttu-id="dc776-434">Sei cifre e quattro lettere:</span><span class="sxs-lookup"><span data-stu-id="dc776-434">Six digits and four letters:</span></span>
  
- <span data-ttu-id="dc776-435">Sei cifre</span><span class="sxs-lookup"><span data-stu-id="dc776-435">Six digits</span></span>
    
- <span data-ttu-id="dc776-436">Quattro lettere (senza distinzione tra maiuscole e minuscole)</span><span class="sxs-lookup"><span data-stu-id="dc776-436">Four letters (not case-sensitive)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="dc776-437">Checksum</span><span class="sxs-lookup"><span data-stu-id="dc776-437">Checksum</span></span>

<span data-ttu-id="dc776-438">No</span><span class="sxs-lookup"><span data-stu-id="dc776-438">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="dc776-439">Definizione</span><span class="sxs-lookup"><span data-stu-id="dc776-439">Definition</span></span>

<span data-ttu-id="dc776-440">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="dc776-440">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="dc776-441">L'espressione `Regex_ireland_eu_driver's_license_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="dc776-441">The regular expression  `Regex_ireland_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="dc776-442">Viene trovata una `Keywords_ireland_eu_driver's_license_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="dc776-442">A keyword from  `Keywords_ireland_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_ireland_eu_driver's_license_number" />
          <Match idRef="Keywords_ireland_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="dc776-443">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="dc776-443">Keywords</span></span>

<span data-ttu-id="dc776-444">| |</span><span class="sxs-lookup"><span data-stu-id="dc776-444"></span></span>
|<span data-ttu-id="dc776-445">**Keywords_ireland_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="dc776-445">**Keywords_ireland_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="dc776-446">DL</span><span class="sxs-lookup"><span data-stu-id="dc776-446">dl#</span></span>  <br/> <span data-ttu-id="dc776-447">driver license</span><span class="sxs-lookup"><span data-stu-id="dc776-447">driver license</span></span>  <br/> <span data-ttu-id="dc776-448">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="dc776-448">driver license number</span></span>  <br/> <span data-ttu-id="dc776-449">patente di guida</span><span class="sxs-lookup"><span data-stu-id="dc776-449">driver licence</span></span>  <br/> <span data-ttu-id="dc776-450">driver Lic.</span><span class="sxs-lookup"><span data-stu-id="dc776-450">drivers lic.</span></span>  <br/> <span data-ttu-id="dc776-451">drivers license</span><span class="sxs-lookup"><span data-stu-id="dc776-451">drivers license</span></span>  <br/> <span data-ttu-id="dc776-452">drivers licence</span><span class="sxs-lookup"><span data-stu-id="dc776-452">drivers licence</span></span>  <br/> <span data-ttu-id="dc776-453">driver's license</span><span class="sxs-lookup"><span data-stu-id="dc776-453">driver's license</span></span>  <br/> <span data-ttu-id="dc776-454">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="dc776-454">driver's license number</span></span>  <br/> <span data-ttu-id="dc776-455">numero di patente del conducente</span><span class="sxs-lookup"><span data-stu-id="dc776-455">driver's licence number</span></span>  <br/> <span data-ttu-id="dc776-456">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="dc776-456">driving license number</span></span>  <br/> <span data-ttu-id="dc776-457">dlno #</span><span class="sxs-lookup"><span data-stu-id="dc776-457">dlno#</span></span>  <br/> <span data-ttu-id="dc776-458">Ceadúnas Tiomána</span><span class="sxs-lookup"><span data-stu-id="dc776-458">ceadúnas tiomána</span></span>  <br/> |
   
## <a name="italy"></a><span data-ttu-id="dc776-459">Italia</span><span class="sxs-lookup"><span data-stu-id="dc776-459">Italy</span></span>

<span data-ttu-id="dc776-460">Per informazioni dettagliate, vedere la sezione "numero di licenza del conducente italiano" in [che cosa cercano i tipi di informazioni riservate](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="dc776-460">For details, see the section "Italy Driver's License Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="latvia"></a><span data-ttu-id="dc776-461">Lettonia</span><span class="sxs-lookup"><span data-stu-id="dc776-461">Latvia</span></span>

### <a name="format"></a><span data-ttu-id="dc776-462">Formato</span><span class="sxs-lookup"><span data-stu-id="dc776-462">Format</span></span>

<span data-ttu-id="dc776-463">Tre lettere seguite da sei cifre</span><span class="sxs-lookup"><span data-stu-id="dc776-463">Three letters followed by six digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="dc776-464">Modello</span><span class="sxs-lookup"><span data-stu-id="dc776-464">Pattern</span></span>

<span data-ttu-id="dc776-465">Tre lettere e sei cifre:</span><span class="sxs-lookup"><span data-stu-id="dc776-465">Three letters and six digits:</span></span>
  
-  <span data-ttu-id="dc776-466">Tre lettere (senza distinzione tra maiuscole e minuscole)</span><span class="sxs-lookup"><span data-stu-id="dc776-466">Three letters (not case-sensitive)</span></span> 
    
- <span data-ttu-id="dc776-467">Sei cifre</span><span class="sxs-lookup"><span data-stu-id="dc776-467">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="dc776-468">Checksum</span><span class="sxs-lookup"><span data-stu-id="dc776-468">Checksum</span></span>

<span data-ttu-id="dc776-469">No</span><span class="sxs-lookup"><span data-stu-id="dc776-469">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="dc776-470">Definizione</span><span class="sxs-lookup"><span data-stu-id="dc776-470">Definition</span></span>

<span data-ttu-id="dc776-471">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="dc776-471">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="dc776-472">L'espressione `Regex_latvia_eu_driver's_license_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="dc776-472">The regular expression  `Regex_latvia_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="dc776-473">Viene trovata una `Keywords_latvia_eu_driver's_license_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="dc776-473">A keyword from  `Keywords_latvia_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_latvia_eu_driver's_license_number" />
          <Match idRef="Keywords_latvia_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="dc776-474">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="dc776-474">Keywords</span></span>

<span data-ttu-id="dc776-475">| |</span><span class="sxs-lookup"><span data-stu-id="dc776-475"></span></span>
|<span data-ttu-id="dc776-476">**Keywords_latvia_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="dc776-476">**Keywords_latvia_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="dc776-477">DL</span><span class="sxs-lookup"><span data-stu-id="dc776-477">dl#</span></span>  <br/> <span data-ttu-id="dc776-478">driver license</span><span class="sxs-lookup"><span data-stu-id="dc776-478">driver license</span></span>  <br/> <span data-ttu-id="dc776-479">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="dc776-479">driver license number</span></span>  <br/> <span data-ttu-id="dc776-480">patente di guida</span><span class="sxs-lookup"><span data-stu-id="dc776-480">driver licence</span></span>  <br/> <span data-ttu-id="dc776-481">driver Lic.</span><span class="sxs-lookup"><span data-stu-id="dc776-481">drivers lic.</span></span>  <br/> <span data-ttu-id="dc776-482">drivers license</span><span class="sxs-lookup"><span data-stu-id="dc776-482">drivers license</span></span>  <br/> <span data-ttu-id="dc776-483">drivers licence</span><span class="sxs-lookup"><span data-stu-id="dc776-483">drivers licence</span></span>  <br/> <span data-ttu-id="dc776-484">driver's license</span><span class="sxs-lookup"><span data-stu-id="dc776-484">driver's license</span></span>  <br/> <span data-ttu-id="dc776-485">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="dc776-485">driver's license number</span></span>  <br/> <span data-ttu-id="dc776-486">numero di patente del conducente</span><span class="sxs-lookup"><span data-stu-id="dc776-486">driver's licence number</span></span>  <br/> <span data-ttu-id="dc776-487">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="dc776-487">driving license number</span></span>  <br/> <span data-ttu-id="dc776-488">dlno #</span><span class="sxs-lookup"><span data-stu-id="dc776-488">dlno#</span></span>  <br/> <span data-ttu-id="dc776-489">autovadītāja apliecība</span><span class="sxs-lookup"><span data-stu-id="dc776-489">autovadītāja apliecība</span></span>  <br/> |
   
## <a name="lithuania"></a><span data-ttu-id="dc776-490">Lituania</span><span class="sxs-lookup"><span data-stu-id="dc776-490">Lithuania</span></span>

### <a name="format"></a><span data-ttu-id="dc776-491">Formato</span><span class="sxs-lookup"><span data-stu-id="dc776-491">Format</span></span>

<span data-ttu-id="dc776-492">Otto cifre senza spazi e delimitatori</span><span class="sxs-lookup"><span data-stu-id="dc776-492">Eight digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="dc776-493">Modello</span><span class="sxs-lookup"><span data-stu-id="dc776-493">Pattern</span></span>

 <span data-ttu-id="dc776-494">Otto cifre</span><span class="sxs-lookup"><span data-stu-id="dc776-494">Eight digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="dc776-495">Checksum</span><span class="sxs-lookup"><span data-stu-id="dc776-495">Checksum</span></span>

<span data-ttu-id="dc776-496">No</span><span class="sxs-lookup"><span data-stu-id="dc776-496">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="dc776-497">Definizione</span><span class="sxs-lookup"><span data-stu-id="dc776-497">Definition</span></span>

<span data-ttu-id="dc776-498">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="dc776-498">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="dc776-499">L'espressione `Regex_lithuania_eu_driver's_license_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="dc776-499">The regular expression  `Regex_lithuania_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="dc776-500">Viene trovata una `Keywords_lithuania_eu_driver's_license_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="dc776-500">A keyword from  `Keywords_lithuania_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_lithuania_eu_driver's_license_number" />
          <Match idRef="Keywords_lithuania_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="dc776-501">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="dc776-501">Keywords</span></span>

<span data-ttu-id="dc776-502">| |</span><span class="sxs-lookup"><span data-stu-id="dc776-502"></span></span>
|<span data-ttu-id="dc776-503">**Keywords_lithuania_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="dc776-503">**Keywords_lithuania_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="dc776-504">DL</span><span class="sxs-lookup"><span data-stu-id="dc776-504">dl#</span></span>  <br/> <span data-ttu-id="dc776-505">driver license</span><span class="sxs-lookup"><span data-stu-id="dc776-505">driver license</span></span>  <br/> <span data-ttu-id="dc776-506">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="dc776-506">driver license number</span></span>  <br/> <span data-ttu-id="dc776-507">patente di guida</span><span class="sxs-lookup"><span data-stu-id="dc776-507">driver licence</span></span>  <br/> <span data-ttu-id="dc776-508">driver Lic.</span><span class="sxs-lookup"><span data-stu-id="dc776-508">drivers lic.</span></span>  <br/> <span data-ttu-id="dc776-509">drivers license</span><span class="sxs-lookup"><span data-stu-id="dc776-509">drivers license</span></span>  <br/> <span data-ttu-id="dc776-510">drivers licence</span><span class="sxs-lookup"><span data-stu-id="dc776-510">drivers licence</span></span>  <br/> <span data-ttu-id="dc776-511">driver's license</span><span class="sxs-lookup"><span data-stu-id="dc776-511">driver's license</span></span>  <br/> <span data-ttu-id="dc776-512">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="dc776-512">driver's license number</span></span>  <br/> <span data-ttu-id="dc776-513">numero di patente del conducente</span><span class="sxs-lookup"><span data-stu-id="dc776-513">driver's licence number</span></span>  <br/> <span data-ttu-id="dc776-514">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="dc776-514">driving license number</span></span>  <br/> <span data-ttu-id="dc776-515">dlno #</span><span class="sxs-lookup"><span data-stu-id="dc776-515">dlno#</span></span>  <br/> <span data-ttu-id="dc776-516">vairuotojo pažymėjimas</span><span class="sxs-lookup"><span data-stu-id="dc776-516">vairuotojo pažymėjimas</span></span>  <br/> |
   
## <a name="luxemburg"></a><span data-ttu-id="dc776-517">Lussemburgo</span><span class="sxs-lookup"><span data-stu-id="dc776-517">Luxemburg</span></span>

### <a name="format"></a><span data-ttu-id="dc776-518">Formato</span><span class="sxs-lookup"><span data-stu-id="dc776-518">Format</span></span>

<span data-ttu-id="dc776-519">Sei cifre senza spazi e delimitatori</span><span class="sxs-lookup"><span data-stu-id="dc776-519">Six digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="dc776-520">Modello</span><span class="sxs-lookup"><span data-stu-id="dc776-520">Pattern</span></span>

 <span data-ttu-id="dc776-521">Sei cifre</span><span class="sxs-lookup"><span data-stu-id="dc776-521">Six digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="dc776-522">Checksum</span><span class="sxs-lookup"><span data-stu-id="dc776-522">Checksum</span></span>

<span data-ttu-id="dc776-523">No</span><span class="sxs-lookup"><span data-stu-id="dc776-523">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="dc776-524">Definizione</span><span class="sxs-lookup"><span data-stu-id="dc776-524">Definition</span></span>

<span data-ttu-id="dc776-525">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="dc776-525">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="dc776-526">L'espressione `Regex_luxemburg_eu_driver's_license_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="dc776-526">The regular expression  `Regex_luxemburg_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="dc776-527">Viene trovata una `Keywords_luxemburg_eu_driver's_license_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="dc776-527">A keyword from  `Keywords_luxemburg_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_luxemburg_eu_driver's_license_number" />
          <Match idRef="Keywords_luxemburg_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="dc776-528">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="dc776-528">Keywords</span></span>

<span data-ttu-id="dc776-529">| |</span><span class="sxs-lookup"><span data-stu-id="dc776-529"></span></span>
|<span data-ttu-id="dc776-530">**Keywords_luxemburg_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="dc776-530">**Keywords_luxemburg_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="dc776-531">DL</span><span class="sxs-lookup"><span data-stu-id="dc776-531">dl#</span></span>  <br/> <span data-ttu-id="dc776-532">driver license</span><span class="sxs-lookup"><span data-stu-id="dc776-532">driver license</span></span>  <br/> <span data-ttu-id="dc776-533">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="dc776-533">driver license number</span></span>  <br/> <span data-ttu-id="dc776-534">patente di guida</span><span class="sxs-lookup"><span data-stu-id="dc776-534">driver licence</span></span>  <br/> <span data-ttu-id="dc776-535">driver Lic.</span><span class="sxs-lookup"><span data-stu-id="dc776-535">drivers lic.</span></span>  <br/> <span data-ttu-id="dc776-536">drivers license</span><span class="sxs-lookup"><span data-stu-id="dc776-536">drivers license</span></span>  <br/> <span data-ttu-id="dc776-537">drivers licence</span><span class="sxs-lookup"><span data-stu-id="dc776-537">drivers licence</span></span>  <br/> <span data-ttu-id="dc776-538">driver's license</span><span class="sxs-lookup"><span data-stu-id="dc776-538">driver's license</span></span>  <br/> <span data-ttu-id="dc776-539">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="dc776-539">driver's license number</span></span>  <br/> <span data-ttu-id="dc776-540">numero di patente del conducente</span><span class="sxs-lookup"><span data-stu-id="dc776-540">driver's licence number</span></span>  <br/> <span data-ttu-id="dc776-541">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="dc776-541">driving license number</span></span>  <br/> <span data-ttu-id="dc776-542">dlno #</span><span class="sxs-lookup"><span data-stu-id="dc776-542">dlno#</span></span>  <br/> <span data-ttu-id="dc776-543">fahrerlaubnis</span><span class="sxs-lookup"><span data-stu-id="dc776-543">fahrerlaubnis</span></span>  <br/> |
   
## <a name="malta"></a><span data-ttu-id="dc776-544">Malta</span><span class="sxs-lookup"><span data-stu-id="dc776-544">Malta</span></span>

### <a name="format"></a><span data-ttu-id="dc776-545">Formato</span><span class="sxs-lookup"><span data-stu-id="dc776-545">Format</span></span>

<span data-ttu-id="dc776-546">Combinazione di due caratteri e di sei cifre nel modello specificato</span><span class="sxs-lookup"><span data-stu-id="dc776-546">Combination of two characters and six digits in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="dc776-547">Modello</span><span class="sxs-lookup"><span data-stu-id="dc776-547">Pattern</span></span>

<span data-ttu-id="dc776-548">Combinazione di due caratteri e di sei cifre:</span><span class="sxs-lookup"><span data-stu-id="dc776-548">Combination of two characters and six digits:</span></span>
  
- <span data-ttu-id="dc776-549">Due caratteri (cifre o lettere, non con distinzione tra maiuscole e minuscole)</span><span class="sxs-lookup"><span data-stu-id="dc776-549">Two characters (digits or letters, not case-sensitive)</span></span>
    
- <span data-ttu-id="dc776-550">Uno spazio (facoltativo)</span><span class="sxs-lookup"><span data-stu-id="dc776-550">A space (optional)</span></span>
    
- <span data-ttu-id="dc776-551">Tre cifre</span><span class="sxs-lookup"><span data-stu-id="dc776-551">Three digits</span></span>
    
- <span data-ttu-id="dc776-552">Uno spazio (facoltativo)</span><span class="sxs-lookup"><span data-stu-id="dc776-552">A space (optional)</span></span>
    
- <span data-ttu-id="dc776-553">Tre cifre</span><span class="sxs-lookup"><span data-stu-id="dc776-553">Three digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="dc776-554">Checksum</span><span class="sxs-lookup"><span data-stu-id="dc776-554">Checksum</span></span>

<span data-ttu-id="dc776-555">No</span><span class="sxs-lookup"><span data-stu-id="dc776-555">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="dc776-556">Definizione</span><span class="sxs-lookup"><span data-stu-id="dc776-556">Definition</span></span>

<span data-ttu-id="dc776-557">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="dc776-557">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="dc776-558">L'espressione `Regex_malta_eu_driver's_license_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="dc776-558">The regular expression  `Regex_malta_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="dc776-559">Viene trovata una `Keywords_malta_eu_driver's_license_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="dc776-559">A keyword from  `Keywords_malta_eu_driver's_license_number` is found.</span></span> 
    
```
<!-- EU Driver's License Number -->
 <Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_malta_eu_driver's_license_number" />
          <Match idRef="Keywords_malta_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="dc776-560">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="dc776-560">Keywords</span></span>

<span data-ttu-id="dc776-561">| |</span><span class="sxs-lookup"><span data-stu-id="dc776-561"></span></span>
|<span data-ttu-id="dc776-562">**Keywords_malta_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="dc776-562">**Keywords_malta_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="dc776-563">DL</span><span class="sxs-lookup"><span data-stu-id="dc776-563">dl#</span></span>  <br/> <span data-ttu-id="dc776-564">driver license</span><span class="sxs-lookup"><span data-stu-id="dc776-564">driver license</span></span>  <br/> <span data-ttu-id="dc776-565">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="dc776-565">driver license number</span></span>  <br/> <span data-ttu-id="dc776-566">patente di guida</span><span class="sxs-lookup"><span data-stu-id="dc776-566">driver licence</span></span>  <br/> <span data-ttu-id="dc776-567">driver Lic.</span><span class="sxs-lookup"><span data-stu-id="dc776-567">drivers lic.</span></span>  <br/> <span data-ttu-id="dc776-568">drivers license</span><span class="sxs-lookup"><span data-stu-id="dc776-568">drivers license</span></span>  <br/> <span data-ttu-id="dc776-569">drivers licence</span><span class="sxs-lookup"><span data-stu-id="dc776-569">drivers licence</span></span>  <br/> <span data-ttu-id="dc776-570">driver's license</span><span class="sxs-lookup"><span data-stu-id="dc776-570">driver's license</span></span>  <br/> <span data-ttu-id="dc776-571">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="dc776-571">driver's license number</span></span>  <br/> <span data-ttu-id="dc776-572">numero di patente del conducente</span><span class="sxs-lookup"><span data-stu-id="dc776-572">driver's licence number</span></span>  <br/> <span data-ttu-id="dc776-573">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="dc776-573">driving license number</span></span>  <br/> <span data-ttu-id="dc776-574">dlno #</span><span class="sxs-lookup"><span data-stu-id="dc776-574">dlno#</span></span>  <br/> <span data-ttu-id="dc776-575">Liċenzja TAS-sewqan</span><span class="sxs-lookup"><span data-stu-id="dc776-575">liċenzja tas-sewqan</span></span>  <br/> |
   
## <a name="netherlands"></a><span data-ttu-id="dc776-576">Paesi Bassi</span><span class="sxs-lookup"><span data-stu-id="dc776-576">Netherlands</span></span>

### <a name="format"></a><span data-ttu-id="dc776-577">Formato</span><span class="sxs-lookup"><span data-stu-id="dc776-577">Format</span></span>

<span data-ttu-id="dc776-578">10 cifre senza spazi e delimitatori</span><span class="sxs-lookup"><span data-stu-id="dc776-578">10 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="dc776-579">Modello</span><span class="sxs-lookup"><span data-stu-id="dc776-579">Pattern</span></span>

<span data-ttu-id="dc776-580">10 cifre</span><span class="sxs-lookup"><span data-stu-id="dc776-580">10 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="dc776-581">Checksum</span><span class="sxs-lookup"><span data-stu-id="dc776-581">Checksum</span></span>

<span data-ttu-id="dc776-582">No</span><span class="sxs-lookup"><span data-stu-id="dc776-582">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="dc776-583">Definizione</span><span class="sxs-lookup"><span data-stu-id="dc776-583">Definition</span></span>

<span data-ttu-id="dc776-584">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="dc776-584">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="dc776-585">L'espressione `Regex_netherlands_eu_driver's_license_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="dc776-585">The regular expression  `Regex_netherlands_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="dc776-586">Viene trovata una `Keywords_netherlands_eu_driver's_license_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="dc776-586">A keyword from  `Keywords_netherlands_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_netherlands_eu_driver's_license_number" />
          <Match idRef="Keywords_netherlands_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="dc776-587">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="dc776-587">Keywords</span></span>

<span data-ttu-id="dc776-588">| |</span><span class="sxs-lookup"><span data-stu-id="dc776-588"></span></span>
|<span data-ttu-id="dc776-589">**Keywords_netherlands_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="dc776-589">**Keywords_netherlands_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="dc776-590">DL</span><span class="sxs-lookup"><span data-stu-id="dc776-590">dl#</span></span>  <br/> <span data-ttu-id="dc776-591">driver license</span><span class="sxs-lookup"><span data-stu-id="dc776-591">driver license</span></span>  <br/> <span data-ttu-id="dc776-592">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="dc776-592">driver license number</span></span>  <br/> <span data-ttu-id="dc776-593">patente di guida</span><span class="sxs-lookup"><span data-stu-id="dc776-593">driver licence</span></span>  <br/> <span data-ttu-id="dc776-594">driver Lic.</span><span class="sxs-lookup"><span data-stu-id="dc776-594">drivers lic.</span></span>  <br/> <span data-ttu-id="dc776-595">drivers license</span><span class="sxs-lookup"><span data-stu-id="dc776-595">drivers license</span></span>  <br/> <span data-ttu-id="dc776-596">drivers licence</span><span class="sxs-lookup"><span data-stu-id="dc776-596">drivers licence</span></span>  <br/> <span data-ttu-id="dc776-597">driver's license</span><span class="sxs-lookup"><span data-stu-id="dc776-597">driver's license</span></span>  <br/> <span data-ttu-id="dc776-598">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="dc776-598">driver's license number</span></span>  <br/> <span data-ttu-id="dc776-599">numero di patente del conducente</span><span class="sxs-lookup"><span data-stu-id="dc776-599">driver's licence number</span></span>  <br/> <span data-ttu-id="dc776-600">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="dc776-600">driving license number</span></span>  <br/> <span data-ttu-id="dc776-601">dlno #</span><span class="sxs-lookup"><span data-stu-id="dc776-601">dlno#</span></span>  <br/> <span data-ttu-id="dc776-602">permis de conduire</span><span class="sxs-lookup"><span data-stu-id="dc776-602">permis de conduire</span></span>  <br/> <span data-ttu-id="dc776-603">Rijbewijs</span><span class="sxs-lookup"><span data-stu-id="dc776-603">rijbewijs</span></span>  <br/> <span data-ttu-id="dc776-604">rijbewijsnummer</span><span class="sxs-lookup"><span data-stu-id="dc776-604">rijbewijsnummer</span></span>  <br/> |
   
## <a name="poland"></a><span data-ttu-id="dc776-605">Polonia</span><span class="sxs-lookup"><span data-stu-id="dc776-605">Poland</span></span>

### <a name="format"></a><span data-ttu-id="dc776-606">Formato</span><span class="sxs-lookup"><span data-stu-id="dc776-606">Format</span></span>

<span data-ttu-id="dc776-607">14 cifre contenenti 2 barre</span><span class="sxs-lookup"><span data-stu-id="dc776-607">14 digits containing 2 forward slashes</span></span>
  
### <a name="pattern"></a><span data-ttu-id="dc776-608">Modello</span><span class="sxs-lookup"><span data-stu-id="dc776-608">Pattern</span></span>

<span data-ttu-id="dc776-609">14 cifre e 2 barre:</span><span class="sxs-lookup"><span data-stu-id="dc776-609">14 digits and 2 forward slashes:</span></span>
  
-  <span data-ttu-id="dc776-610">Cinque cifre</span><span class="sxs-lookup"><span data-stu-id="dc776-610">Five digits</span></span> 
    
- <span data-ttu-id="dc776-611">Una barra</span><span class="sxs-lookup"><span data-stu-id="dc776-611">A forward slash</span></span>
    
- <span data-ttu-id="dc776-612">Due cifre</span><span class="sxs-lookup"><span data-stu-id="dc776-612">Two digits</span></span>
    
- <span data-ttu-id="dc776-613">Una barra</span><span class="sxs-lookup"><span data-stu-id="dc776-613">A forward slash</span></span>
    
- <span data-ttu-id="dc776-614">Sette cifre</span><span class="sxs-lookup"><span data-stu-id="dc776-614">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="dc776-615">Checksum</span><span class="sxs-lookup"><span data-stu-id="dc776-615">Checksum</span></span>

<span data-ttu-id="dc776-616">No</span><span class="sxs-lookup"><span data-stu-id="dc776-616">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="dc776-617">Definizione</span><span class="sxs-lookup"><span data-stu-id="dc776-617">Definition</span></span>

<span data-ttu-id="dc776-618">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="dc776-618">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="dc776-619">L'espressione `Regex_poland_eu_driver's_license_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="dc776-619">The regular expression  `Regex_poland_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="dc776-620">Viene trovata una `Keywords_poland_eu_driver's_license_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="dc776-620">A keyword from  `Keywords_poland_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_poland_eu_driver's_license_number" />
          <Match idRef="Keywords_poland_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="dc776-621">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="dc776-621">Keywords</span></span>

<span data-ttu-id="dc776-622">| |</span><span class="sxs-lookup"><span data-stu-id="dc776-622"></span></span>
|<span data-ttu-id="dc776-623">**Keywords_poland_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="dc776-623">**Keywords_poland_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="dc776-624">DL</span><span class="sxs-lookup"><span data-stu-id="dc776-624">dl#</span></span>  <br/> <span data-ttu-id="dc776-625">driver license</span><span class="sxs-lookup"><span data-stu-id="dc776-625">driver license</span></span>  <br/> <span data-ttu-id="dc776-626">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="dc776-626">driver license number</span></span>  <br/> <span data-ttu-id="dc776-627">patente di guida</span><span class="sxs-lookup"><span data-stu-id="dc776-627">driver licence</span></span>  <br/> <span data-ttu-id="dc776-628">driver Lic.</span><span class="sxs-lookup"><span data-stu-id="dc776-628">drivers lic.</span></span>  <br/> <span data-ttu-id="dc776-629">drivers license</span><span class="sxs-lookup"><span data-stu-id="dc776-629">drivers license</span></span>  <br/> <span data-ttu-id="dc776-630">drivers licence</span><span class="sxs-lookup"><span data-stu-id="dc776-630">drivers licence</span></span>  <br/> <span data-ttu-id="dc776-631">driver's license</span><span class="sxs-lookup"><span data-stu-id="dc776-631">driver's license</span></span>  <br/> <span data-ttu-id="dc776-632">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="dc776-632">driver's license number</span></span>  <br/> <span data-ttu-id="dc776-633">numero di patente del conducente</span><span class="sxs-lookup"><span data-stu-id="dc776-633">driver's licence number</span></span>  <br/> <span data-ttu-id="dc776-634">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="dc776-634">driving license number</span></span>  <br/> <span data-ttu-id="dc776-635">dlno #</span><span class="sxs-lookup"><span data-stu-id="dc776-635">dlno#</span></span>  <br/> <span data-ttu-id="dc776-636">prawo jazdy</span><span class="sxs-lookup"><span data-stu-id="dc776-636">prawo jazdy</span></span>  <br/> |
   
## <a name="portugal"></a><span data-ttu-id="dc776-637">Portogallo</span><span class="sxs-lookup"><span data-stu-id="dc776-637">Portugal</span></span>

### <a name="format"></a><span data-ttu-id="dc776-638">Formato</span><span class="sxs-lookup"><span data-stu-id="dc776-638">Format</span></span>

<span data-ttu-id="dc776-639">Due lettere seguite da un numero di sette numeri nel modello specificato</span><span class="sxs-lookup"><span data-stu-id="dc776-639">Two letters followed by a seven numbers in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="dc776-640">Modello</span><span class="sxs-lookup"><span data-stu-id="dc776-640">Pattern</span></span>

<span data-ttu-id="dc776-641">Due lettere seguite da sette numeri con caratteri speciali:</span><span class="sxs-lookup"><span data-stu-id="dc776-641">Two letters followed by seven numbers with special characters:</span></span>
  
-  <span data-ttu-id="dc776-642">Due lettere (senza distinzione tra maiuscole e minuscole)</span><span class="sxs-lookup"><span data-stu-id="dc776-642">Two letters (not case-sensitive)</span></span> 
    
- <span data-ttu-id="dc776-643">Una lineetta</span><span class="sxs-lookup"><span data-stu-id="dc776-643">A hyphen</span></span>
    
- <span data-ttu-id="dc776-644">Sei cifre</span><span class="sxs-lookup"><span data-stu-id="dc776-644">Six digits</span></span>
    
- <span data-ttu-id="dc776-645">Uno spazio</span><span class="sxs-lookup"><span data-stu-id="dc776-645">A space</span></span>
    
- <span data-ttu-id="dc776-646">Una cifra</span><span class="sxs-lookup"><span data-stu-id="dc776-646">One digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="dc776-647">Checksum</span><span class="sxs-lookup"><span data-stu-id="dc776-647">Checksum</span></span>

<span data-ttu-id="dc776-648">No</span><span class="sxs-lookup"><span data-stu-id="dc776-648">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="dc776-649">Definizione</span><span class="sxs-lookup"><span data-stu-id="dc776-649">Definition</span></span>

<span data-ttu-id="dc776-650">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="dc776-650">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="dc776-651">L'espressione `Regex_portugal_eu_driver's_license_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="dc776-651">The regular expression  `Regex_portugal_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="dc776-652">Viene trovata una `Keywords_portugal_eu_driver's_license_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="dc776-652">A keyword from  `Keywords_portugal_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_portugal_eu_driver's_license_number" />
          <Match idRef="Keywords_portugal_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="dc776-653">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="dc776-653">Keywords</span></span>

<span data-ttu-id="dc776-654">| |</span><span class="sxs-lookup"><span data-stu-id="dc776-654"></span></span>
|<span data-ttu-id="dc776-655">**Keywords_portugal_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="dc776-655">**Keywords_portugal_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="dc776-656">DL</span><span class="sxs-lookup"><span data-stu-id="dc776-656">dl#</span></span>  <br/> <span data-ttu-id="dc776-657">driver license</span><span class="sxs-lookup"><span data-stu-id="dc776-657">driver license</span></span>  <br/> <span data-ttu-id="dc776-658">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="dc776-658">driver license number</span></span>  <br/> <span data-ttu-id="dc776-659">patente di guida</span><span class="sxs-lookup"><span data-stu-id="dc776-659">driver licence</span></span>  <br/> <span data-ttu-id="dc776-660">driver Lic.</span><span class="sxs-lookup"><span data-stu-id="dc776-660">drivers lic.</span></span>  <br/> <span data-ttu-id="dc776-661">drivers license</span><span class="sxs-lookup"><span data-stu-id="dc776-661">drivers license</span></span>  <br/> <span data-ttu-id="dc776-662">drivers licence</span><span class="sxs-lookup"><span data-stu-id="dc776-662">drivers licence</span></span>  <br/> <span data-ttu-id="dc776-663">driver's license</span><span class="sxs-lookup"><span data-stu-id="dc776-663">driver's license</span></span>  <br/> <span data-ttu-id="dc776-664">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="dc776-664">driver's license number</span></span>  <br/> <span data-ttu-id="dc776-665">numero di patente del conducente</span><span class="sxs-lookup"><span data-stu-id="dc776-665">driver's licence number</span></span>  <br/> <span data-ttu-id="dc776-666">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="dc776-666">driving license number</span></span>  <br/> <span data-ttu-id="dc776-667">dlno #</span><span class="sxs-lookup"><span data-stu-id="dc776-667">dlno#</span></span>  <br/> <span data-ttu-id="dc776-668">carteira de motorista</span><span class="sxs-lookup"><span data-stu-id="dc776-668">carteira de motorista</span></span>  <br/> |
   
## <a name="romania"></a><span data-ttu-id="dc776-669">Romania</span><span class="sxs-lookup"><span data-stu-id="dc776-669">Romania</span></span>

### <a name="format"></a><span data-ttu-id="dc776-670">Formato</span><span class="sxs-lookup"><span data-stu-id="dc776-670">Format</span></span>

<span data-ttu-id="dc776-671">Un carattere seguito da otto cifre</span><span class="sxs-lookup"><span data-stu-id="dc776-671">One character followed by eight digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="dc776-672">Modello</span><span class="sxs-lookup"><span data-stu-id="dc776-672">Pattern</span></span>

<span data-ttu-id="dc776-673">Un carattere seguito da otto cifre:</span><span class="sxs-lookup"><span data-stu-id="dc776-673">One character followed by eight digits:</span></span>
  
-  <span data-ttu-id="dc776-674">Una lettera (senza distinzione tra maiuscole e minuscole) o cifra</span><span class="sxs-lookup"><span data-stu-id="dc776-674">One letter (not case-sensitive) or digit</span></span> 
    
- <span data-ttu-id="dc776-675">Otto cifre</span><span class="sxs-lookup"><span data-stu-id="dc776-675">Eight digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="dc776-676">Checksum</span><span class="sxs-lookup"><span data-stu-id="dc776-676">Checksum</span></span>

<span data-ttu-id="dc776-677">No</span><span class="sxs-lookup"><span data-stu-id="dc776-677">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="dc776-678">Definizione</span><span class="sxs-lookup"><span data-stu-id="dc776-678">Definition</span></span>

<span data-ttu-id="dc776-679">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="dc776-679">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="dc776-680">L'espressione `Regex_romania_eu_driver's_license_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="dc776-680">The regular expression  `Regex_romania_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="dc776-681">Viene trovata una `Keywords_romania_eu_driver's_license_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="dc776-681">A keyword from  `Keywords_romania_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_romania_eu_driver's_license_number" />
          <Match idRef="Keywords_romania_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="dc776-682">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="dc776-682">Keywords</span></span>

<span data-ttu-id="dc776-683">| |</span><span class="sxs-lookup"><span data-stu-id="dc776-683"></span></span>
|<span data-ttu-id="dc776-684">**Keywords_romania_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="dc776-684">**Keywords_romania_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="dc776-685">DL</span><span class="sxs-lookup"><span data-stu-id="dc776-685">dl#</span></span>  <br/> <span data-ttu-id="dc776-686">driver license</span><span class="sxs-lookup"><span data-stu-id="dc776-686">driver license</span></span>  <br/> <span data-ttu-id="dc776-687">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="dc776-687">driver license number</span></span>  <br/> <span data-ttu-id="dc776-688">patente di guida</span><span class="sxs-lookup"><span data-stu-id="dc776-688">driver licence</span></span>  <br/> <span data-ttu-id="dc776-689">driver Lic.</span><span class="sxs-lookup"><span data-stu-id="dc776-689">drivers lic.</span></span>  <br/> <span data-ttu-id="dc776-690">drivers license</span><span class="sxs-lookup"><span data-stu-id="dc776-690">drivers license</span></span>  <br/> <span data-ttu-id="dc776-691">drivers licence</span><span class="sxs-lookup"><span data-stu-id="dc776-691">drivers licence</span></span>  <br/> <span data-ttu-id="dc776-692">driver's license</span><span class="sxs-lookup"><span data-stu-id="dc776-692">driver's license</span></span>  <br/> <span data-ttu-id="dc776-693">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="dc776-693">driver's license number</span></span>  <br/> <span data-ttu-id="dc776-694">numero di patente del conducente</span><span class="sxs-lookup"><span data-stu-id="dc776-694">driver's licence number</span></span>  <br/> <span data-ttu-id="dc776-695">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="dc776-695">driving license number</span></span>  <br/> <span data-ttu-id="dc776-696">dlno #</span><span class="sxs-lookup"><span data-stu-id="dc776-696">dlno#</span></span>  <br/> <span data-ttu-id="dc776-697">Permis de conducere</span><span class="sxs-lookup"><span data-stu-id="dc776-697">permis de conducere</span></span>  <br/> |
   
## <a name="slovakia"></a><span data-ttu-id="dc776-698">Slovacchia</span><span class="sxs-lookup"><span data-stu-id="dc776-698">Slovakia</span></span>

### <a name="format"></a><span data-ttu-id="dc776-699">Formato</span><span class="sxs-lookup"><span data-stu-id="dc776-699">Format</span></span>

<span data-ttu-id="dc776-700">Un carattere seguito da sette cifre</span><span class="sxs-lookup"><span data-stu-id="dc776-700">One character followed by seven digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="dc776-701">Modello</span><span class="sxs-lookup"><span data-stu-id="dc776-701">Pattern</span></span>

<span data-ttu-id="dc776-702">Un carattere seguito da sette cifre</span><span class="sxs-lookup"><span data-stu-id="dc776-702">One character followed by seven digits</span></span>
  
- <span data-ttu-id="dc776-703">Una lettera (senza distinzione tra maiuscole e minuscole) o cifra</span><span class="sxs-lookup"><span data-stu-id="dc776-703">One letter (not case-sensitive) or digit</span></span>
    
-  <span data-ttu-id="dc776-704">Sette cifre</span><span class="sxs-lookup"><span data-stu-id="dc776-704">Seven digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="dc776-705">Checksum</span><span class="sxs-lookup"><span data-stu-id="dc776-705">Checksum</span></span>

<span data-ttu-id="dc776-706">No</span><span class="sxs-lookup"><span data-stu-id="dc776-706">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="dc776-707">Definizione</span><span class="sxs-lookup"><span data-stu-id="dc776-707">Definition</span></span>

<span data-ttu-id="dc776-708">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="dc776-708">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="dc776-709">L'espressione `Regex_slovakia_eu_driver's_license_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="dc776-709">The regular expression  `Regex_slovakia_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="dc776-710">Viene trovata una `Keywords_slovakia_eu_driver's_license_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="dc776-710">A keyword from  `Keywords_slovakia_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovaknia_eu_driver's_license_number" />
          <Match idRef="Keywords_slovakia_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="dc776-711">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="dc776-711">Keywords</span></span>

<span data-ttu-id="dc776-712">| |</span><span class="sxs-lookup"><span data-stu-id="dc776-712"></span></span>
|<span data-ttu-id="dc776-713">**Keywords_slovakia_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="dc776-713">**Keywords_slovakia_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="dc776-714">DL</span><span class="sxs-lookup"><span data-stu-id="dc776-714">dl#</span></span>  <br/> <span data-ttu-id="dc776-715">driver license</span><span class="sxs-lookup"><span data-stu-id="dc776-715">driver license</span></span>  <br/> <span data-ttu-id="dc776-716">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="dc776-716">driver license number</span></span>  <br/> <span data-ttu-id="dc776-717">patente di guida</span><span class="sxs-lookup"><span data-stu-id="dc776-717">driver licence</span></span>  <br/> <span data-ttu-id="dc776-718">driver Lic.</span><span class="sxs-lookup"><span data-stu-id="dc776-718">drivers lic.</span></span>  <br/> <span data-ttu-id="dc776-719">drivers license</span><span class="sxs-lookup"><span data-stu-id="dc776-719">drivers license</span></span>  <br/> <span data-ttu-id="dc776-720">drivers licence</span><span class="sxs-lookup"><span data-stu-id="dc776-720">drivers licence</span></span>  <br/> <span data-ttu-id="dc776-721">driver's license</span><span class="sxs-lookup"><span data-stu-id="dc776-721">driver's license</span></span>  <br/> <span data-ttu-id="dc776-722">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="dc776-722">driver's license number</span></span>  <br/> <span data-ttu-id="dc776-723">numero di patente del conducente</span><span class="sxs-lookup"><span data-stu-id="dc776-723">driver's licence number</span></span>  <br/> <span data-ttu-id="dc776-724">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="dc776-724">driving license number</span></span>  <br/> <span data-ttu-id="dc776-725">dlno #</span><span class="sxs-lookup"><span data-stu-id="dc776-725">dlno#</span></span>  <br/> <span data-ttu-id="dc776-726">vodičský preukaz</span><span class="sxs-lookup"><span data-stu-id="dc776-726">vodičský preukaz</span></span>  <br/> |
   
## <a name="slovenia"></a><span data-ttu-id="dc776-727">Slovenia</span><span class="sxs-lookup"><span data-stu-id="dc776-727">Slovenia</span></span>

### <a name="format"></a><span data-ttu-id="dc776-728">Formato</span><span class="sxs-lookup"><span data-stu-id="dc776-728">Format</span></span>

<span data-ttu-id="dc776-729">Nove cifre senza spazi e delimitatori</span><span class="sxs-lookup"><span data-stu-id="dc776-729">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="dc776-730">Modello</span><span class="sxs-lookup"><span data-stu-id="dc776-730">Pattern</span></span>

<span data-ttu-id="dc776-731">9 cifre</span><span class="sxs-lookup"><span data-stu-id="dc776-731">Nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="dc776-732">Checksum</span><span class="sxs-lookup"><span data-stu-id="dc776-732">Checksum</span></span>

<span data-ttu-id="dc776-733">No</span><span class="sxs-lookup"><span data-stu-id="dc776-733">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="dc776-734">Definizione</span><span class="sxs-lookup"><span data-stu-id="dc776-734">Definition</span></span>

<span data-ttu-id="dc776-735">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="dc776-735">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="dc776-736">L'espressione `Regex_slovenia_eu_driver's_license_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="dc776-736">The regular expression  `Regex_slovenia_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="dc776-737">Viene trovata una `Keywords_slovenia_eu_driver's_license_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="dc776-737">A keyword from  `Keywords_slovenia_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovenia_eu_driver's_license_number" />
          <Match idRef="Keywords_slovenia_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="dc776-738">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="dc776-738">Keywords</span></span>

<span data-ttu-id="dc776-739">| |</span><span class="sxs-lookup"><span data-stu-id="dc776-739"></span></span>
|<span data-ttu-id="dc776-740">**Keywords_slovenia_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="dc776-740">**Keywords_slovenia_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="dc776-741">DL</span><span class="sxs-lookup"><span data-stu-id="dc776-741">dl#</span></span>  <br/> <span data-ttu-id="dc776-742">driver license</span><span class="sxs-lookup"><span data-stu-id="dc776-742">driver license</span></span>  <br/> <span data-ttu-id="dc776-743">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="dc776-743">driver license number</span></span>  <br/> <span data-ttu-id="dc776-744">patente di guida</span><span class="sxs-lookup"><span data-stu-id="dc776-744">driver licence</span></span>  <br/> <span data-ttu-id="dc776-745">driver Lic.</span><span class="sxs-lookup"><span data-stu-id="dc776-745">drivers lic.</span></span>  <br/> <span data-ttu-id="dc776-746">drivers license</span><span class="sxs-lookup"><span data-stu-id="dc776-746">drivers license</span></span>  <br/> <span data-ttu-id="dc776-747">drivers licence</span><span class="sxs-lookup"><span data-stu-id="dc776-747">drivers licence</span></span>  <br/> <span data-ttu-id="dc776-748">driver's license</span><span class="sxs-lookup"><span data-stu-id="dc776-748">driver's license</span></span>  <br/> <span data-ttu-id="dc776-749">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="dc776-749">driver's license number</span></span>  <br/> <span data-ttu-id="dc776-750">numero di patente del conducente</span><span class="sxs-lookup"><span data-stu-id="dc776-750">driver's licence number</span></span>  <br/> <span data-ttu-id="dc776-751">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="dc776-751">driving license number</span></span>  <br/> <span data-ttu-id="dc776-752">dlno #</span><span class="sxs-lookup"><span data-stu-id="dc776-752">dlno#</span></span>  <br/> <span data-ttu-id="dc776-753">vozniško dovoljenje</span><span class="sxs-lookup"><span data-stu-id="dc776-753">vozniško dovoljenje</span></span>  <br/> |
   
## <a name="spain"></a><span data-ttu-id="dc776-754">Spagna</span><span class="sxs-lookup"><span data-stu-id="dc776-754">Spain</span></span>

### <a name="format"></a><span data-ttu-id="dc776-755">Formato</span><span class="sxs-lookup"><span data-stu-id="dc776-755">Format</span></span>

<span data-ttu-id="dc776-756">Otto cifre seguite da un carattere</span><span class="sxs-lookup"><span data-stu-id="dc776-756">Eight digits followed by one character</span></span>
  
### <a name="pattern"></a><span data-ttu-id="dc776-757">Modello</span><span class="sxs-lookup"><span data-stu-id="dc776-757">Pattern</span></span>

<span data-ttu-id="dc776-758">Otto cifre seguite da un carattere:</span><span class="sxs-lookup"><span data-stu-id="dc776-758">Eight digits followed by one character:</span></span>
  
-  <span data-ttu-id="dc776-759">Otto cifre</span><span class="sxs-lookup"><span data-stu-id="dc776-759">Eight digits</span></span> 
    
- <span data-ttu-id="dc776-760">Una cifra o una lettera (senza distinzione tra maiuscole e minuscole)</span><span class="sxs-lookup"><span data-stu-id="dc776-760">One digit or letter (not case-sensitive)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="dc776-761">Checksum</span><span class="sxs-lookup"><span data-stu-id="dc776-761">Checksum</span></span>

<span data-ttu-id="dc776-762">Sì</span><span class="sxs-lookup"><span data-stu-id="dc776-762">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="dc776-763">Definizione</span><span class="sxs-lookup"><span data-stu-id="dc776-763">Definition</span></span>

<span data-ttu-id="dc776-764">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="dc776-764">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="dc776-765">La funzione `Func_spain_eu_driver's_license_number` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="dc776-765">The function  `Func_spain_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="dc776-766">Viene trovata una `Keywords_spain_eu_driver's_license_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="dc776-766">A keyword from  `Keywords_spain_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_spain_eu_driver's_license_number" />
          <Match idRef="Keywords_spain_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="dc776-767">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="dc776-767">Keywords</span></span>

<span data-ttu-id="dc776-768">| |</span><span class="sxs-lookup"><span data-stu-id="dc776-768"></span></span>
|<span data-ttu-id="dc776-769">**Keywords_spain_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="dc776-769">**Keywords_spain_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="dc776-770">dlno #</span><span class="sxs-lookup"><span data-stu-id="dc776-770">dlno#</span></span>  <br/> <span data-ttu-id="dc776-771">DL</span><span class="sxs-lookup"><span data-stu-id="dc776-771">dl#</span></span>  <br/> <span data-ttu-id="dc776-772">driver Lic.</span><span class="sxs-lookup"><span data-stu-id="dc776-772">drivers lic.</span></span>  <br/> <span data-ttu-id="dc776-773">patente di guida</span><span class="sxs-lookup"><span data-stu-id="dc776-773">driver licence</span></span>  <br/> <span data-ttu-id="dc776-774">driver license</span><span class="sxs-lookup"><span data-stu-id="dc776-774">driver license</span></span>  <br/> <span data-ttu-id="dc776-775">drivers licence</span><span class="sxs-lookup"><span data-stu-id="dc776-775">drivers licence</span></span>  <br/> <span data-ttu-id="dc776-776">drivers license</span><span class="sxs-lookup"><span data-stu-id="dc776-776">drivers license</span></span>  <br/> <span data-ttu-id="dc776-777">driver's licence</span><span class="sxs-lookup"><span data-stu-id="dc776-777">driver's licence</span></span>  <br/> <span data-ttu-id="dc776-778">driver's license</span><span class="sxs-lookup"><span data-stu-id="dc776-778">driver's license</span></span>  <br/> <span data-ttu-id="dc776-779">driving licence</span><span class="sxs-lookup"><span data-stu-id="dc776-779">driving licence</span></span>  <br/> <span data-ttu-id="dc776-780">driving license</span><span class="sxs-lookup"><span data-stu-id="dc776-780">driving license</span></span>  <br/> <span data-ttu-id="dc776-781">numero di patente del conducente</span><span class="sxs-lookup"><span data-stu-id="dc776-781">driver licence number</span></span>  <br/> <span data-ttu-id="dc776-782">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="dc776-782">driver license number</span></span>  <br/> <span data-ttu-id="dc776-783">numero di patente del conducente</span><span class="sxs-lookup"><span data-stu-id="dc776-783">drivers licence number</span></span>  <br/> <span data-ttu-id="dc776-784">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="dc776-784">drivers license number</span></span>  <br/> <span data-ttu-id="dc776-785">numero di patente del conducente</span><span class="sxs-lookup"><span data-stu-id="dc776-785">driver's licence number</span></span>  <br/> <span data-ttu-id="dc776-786">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="dc776-786">driver's license number</span></span>  <br/> <span data-ttu-id="dc776-787">numero di patente di guida</span><span class="sxs-lookup"><span data-stu-id="dc776-787">driving licence number</span></span>  <br/> <span data-ttu-id="dc776-788">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="dc776-788">driving license number</span></span>  <br/> <span data-ttu-id="dc776-789">permesso di guida</span><span class="sxs-lookup"><span data-stu-id="dc776-789">driving permit</span></span>  <br/> <span data-ttu-id="dc776-790">numero di licenza di guida</span><span class="sxs-lookup"><span data-stu-id="dc776-790">driving permit number</span></span>  <br/> <span data-ttu-id="dc776-791">Permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="dc776-791">permiso de conducción</span></span>  <br/> <span data-ttu-id="dc776-792">Permiso conducción</span><span class="sxs-lookup"><span data-stu-id="dc776-792">permiso conducción</span></span>  <br/> <span data-ttu-id="dc776-793">número licencia conducir</span><span class="sxs-lookup"><span data-stu-id="dc776-793">número licencia conducir</span></span>  <br/> <span data-ttu-id="dc776-794">número de carnet de conducir</span><span class="sxs-lookup"><span data-stu-id="dc776-794">número de carnet de conducir</span></span>  <br/> <span data-ttu-id="dc776-795">número carnet conducir</span><span class="sxs-lookup"><span data-stu-id="dc776-795">número carnet conducir</span></span>  <br/> <span data-ttu-id="dc776-796">licencia conducir</span><span class="sxs-lookup"><span data-stu-id="dc776-796">licencia conducir</span></span>  <br/> <span data-ttu-id="dc776-797">número de Permiso de conducir</span><span class="sxs-lookup"><span data-stu-id="dc776-797">número de permiso de conducir</span></span>  <br/> <span data-ttu-id="dc776-798">número de permiso conducir</span><span class="sxs-lookup"><span data-stu-id="dc776-798">número de permiso conducir</span></span>  <br/> <span data-ttu-id="dc776-799">número permiso conducir</span><span class="sxs-lookup"><span data-stu-id="dc776-799">número permiso conducir</span></span>  <br/> <span data-ttu-id="dc776-800">Permiso conducir</span><span class="sxs-lookup"><span data-stu-id="dc776-800">permiso conducir</span></span>  <br/> <span data-ttu-id="dc776-801">licencia de manejo</span><span class="sxs-lookup"><span data-stu-id="dc776-801">licencia de manejo</span></span>  <br/> <span data-ttu-id="dc776-802">El carnet de conducir</span><span class="sxs-lookup"><span data-stu-id="dc776-802">el carnet de conducir</span></span>  <br/> <span data-ttu-id="dc776-803">carnet conducir</span><span class="sxs-lookup"><span data-stu-id="dc776-803">carnet conducir</span></span>  <br/> |
   
## <a name="sweden"></a><span data-ttu-id="dc776-804">Svezia</span><span class="sxs-lookup"><span data-stu-id="dc776-804">Sweden</span></span>

### <a name="format"></a><span data-ttu-id="dc776-805">Formato</span><span class="sxs-lookup"><span data-stu-id="dc776-805">Format</span></span>

<span data-ttu-id="dc776-806">Dieci cifre contenenti un segno meno</span><span class="sxs-lookup"><span data-stu-id="dc776-806">Ten digits containing a hyphen</span></span>
  
### <a name="pattern"></a><span data-ttu-id="dc776-807">Modello</span><span class="sxs-lookup"><span data-stu-id="dc776-807">Pattern</span></span>

<span data-ttu-id="dc776-808">Dieci cifre contenenti un trattino:</span><span class="sxs-lookup"><span data-stu-id="dc776-808">Ten digits containing a hyphen:</span></span>
  
-  <span data-ttu-id="dc776-809">Sei cifre</span><span class="sxs-lookup"><span data-stu-id="dc776-809">Six digits</span></span> 
    
- <span data-ttu-id="dc776-810">Una lineetta</span><span class="sxs-lookup"><span data-stu-id="dc776-810">A hyphen</span></span>
    
- <span data-ttu-id="dc776-811">Quattro cifre</span><span class="sxs-lookup"><span data-stu-id="dc776-811">Four digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="dc776-812">Checksum</span><span class="sxs-lookup"><span data-stu-id="dc776-812">Checksum</span></span>

<span data-ttu-id="dc776-813">No</span><span class="sxs-lookup"><span data-stu-id="dc776-813">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="dc776-814">Definizione</span><span class="sxs-lookup"><span data-stu-id="dc776-814">Definition</span></span>

<span data-ttu-id="dc776-815">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="dc776-815">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="dc776-816">L'espressione `Regex_sweden_eu_driver's_license_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="dc776-816">The regular expression  `Regex_sweden_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="dc776-817">Viene trovata una `Keywords_sweden_eu_driver's_license_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="dc776-817">A keyword from  `Keywords_sweden_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_sweden_eu_driver's_license_number" />
          <Match idRef="Keywords_sweden_eu_driver's_license_number" />
        </Pattern>
</Entity> 
```

### <a name="keywords"></a><span data-ttu-id="dc776-818">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="dc776-818">Keywords</span></span>

<span data-ttu-id="dc776-819">| |</span><span class="sxs-lookup"><span data-stu-id="dc776-819"></span></span>
|<span data-ttu-id="dc776-820">**Keywords_sweden_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="dc776-820">**Keywords_sweden_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="dc776-821">DL</span><span class="sxs-lookup"><span data-stu-id="dc776-821">dl#</span></span>  <br/> <span data-ttu-id="dc776-822">driver license</span><span class="sxs-lookup"><span data-stu-id="dc776-822">driver license</span></span>  <br/> <span data-ttu-id="dc776-823">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="dc776-823">driver license number</span></span>  <br/> <span data-ttu-id="dc776-824">patente di guida</span><span class="sxs-lookup"><span data-stu-id="dc776-824">driver licence</span></span>  <br/> <span data-ttu-id="dc776-825">driver Lic.</span><span class="sxs-lookup"><span data-stu-id="dc776-825">drivers lic.</span></span>  <br/> <span data-ttu-id="dc776-826">drivers license</span><span class="sxs-lookup"><span data-stu-id="dc776-826">drivers license</span></span>  <br/> <span data-ttu-id="dc776-827">drivers licence</span><span class="sxs-lookup"><span data-stu-id="dc776-827">drivers licence</span></span>  <br/> <span data-ttu-id="dc776-828">driver's license</span><span class="sxs-lookup"><span data-stu-id="dc776-828">driver's license</span></span>  <br/> <span data-ttu-id="dc776-829">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="dc776-829">driver's license number</span></span>  <br/> <span data-ttu-id="dc776-830">numero di patente del conducente</span><span class="sxs-lookup"><span data-stu-id="dc776-830">driver's licence number</span></span>  <br/> <span data-ttu-id="dc776-831">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="dc776-831">driving license number</span></span>  <br/> <span data-ttu-id="dc776-832">dlno #</span><span class="sxs-lookup"><span data-stu-id="dc776-832">dlno#</span></span>  <br/> <span data-ttu-id="dc776-833">körkort</span><span class="sxs-lookup"><span data-stu-id="dc776-833">körkort</span></span>  <br/> |
   
## <a name="uk"></a><span data-ttu-id="dc776-834">Regno Unito</span><span class="sxs-lookup"><span data-stu-id="dc776-834">UK</span></span>

<span data-ttu-id="dc776-835">Per informazioni dettagliate, vedere la sezione "Regno Unito</span><span class="sxs-lookup"><span data-stu-id="dc776-835">For details, see the section "U.K.</span></span> <span data-ttu-id="dc776-836">Numero della patente di guida "in [quello che cercano i tipi di informazioni riservate](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="dc776-836">Driver's License Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="dc776-837">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="dc776-837">See also</span></span>

[<span data-ttu-id="dc776-838">Cosa individuano le tipologie di informazioni sensibili</span><span class="sxs-lookup"><span data-stu-id="dc776-838">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)

