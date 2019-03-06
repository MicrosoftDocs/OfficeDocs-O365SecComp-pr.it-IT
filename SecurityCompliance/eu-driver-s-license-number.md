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
ms.sourcegitcommit: ed822a776d3419853453583e882f3c61ca26d4b2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/05/2019
ms.locfileid: "30410751"
---
# <a name="eu-drivers-license-number"></a><span data-ttu-id="8f9b6-104">Numero della patente di guida dell'Unione europea</span><span class="sxs-lookup"><span data-stu-id="8f9b6-104">EU Driver's License Number</span></span>

<span data-ttu-id="8f9b6-105">In questo argomento viene illustrato l'aspetto di un criterio di prevenzione della perdita di dati (DLP) quando viene rilevato il tipo di informazioni riservate del numero di licenza del driver dell'Unione europea.</span><span class="sxs-lookup"><span data-stu-id="8f9b6-105">This topic shows what a data loss prevention (DLP) policy looks for when it detects the EU Driver's License Number sensitive information type.</span></span> <span data-ttu-id="8f9b6-106">Questo tipo di informazioni riservate definisce modelli, parole chiave e altre evidenze diverse per ogni paese.</span><span class="sxs-lookup"><span data-stu-id="8f9b6-106">This sensitive information type defines different patterns, keywords, and other evidence for each country.</span></span>
  
## <a name="austria"></a><span data-ttu-id="8f9b6-107">Austria</span><span class="sxs-lookup"><span data-stu-id="8f9b6-107">Austria</span></span>

### <a name="format"></a><span data-ttu-id="8f9b6-108">Formato</span><span class="sxs-lookup"><span data-stu-id="8f9b6-108">Format</span></span>

<span data-ttu-id="8f9b6-109">Otto cifre senza spazi e delimitatori</span><span class="sxs-lookup"><span data-stu-id="8f9b6-109">Eight digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="8f9b6-110">Modello</span><span class="sxs-lookup"><span data-stu-id="8f9b6-110">Pattern</span></span>

<span data-ttu-id="8f9b6-111">Otto cifre</span><span class="sxs-lookup"><span data-stu-id="8f9b6-111">Eight digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="8f9b6-112">Checksum</span><span class="sxs-lookup"><span data-stu-id="8f9b6-112">Checksum</span></span>

<span data-ttu-id="8f9b6-113">No</span><span class="sxs-lookup"><span data-stu-id="8f9b6-113">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="8f9b6-114">Definizione</span><span class="sxs-lookup"><span data-stu-id="8f9b6-114">Definition</span></span>

<span data-ttu-id="8f9b6-115">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="8f9b6-115">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="8f9b6-116">L'espressione `Regex_austria_eu_driver's_license_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="8f9b6-116">The regular expression  `Regex_austria_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="8f9b6-117">Viene trovata una `Keywords_austria_eu_driver's_license_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="8f9b6-117">A keyword from  `Keywords_austria_eu_driver's_license_number` is found.</span></span> 
    
```
<!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_austria_eu_driver's_license_number" />
          <Match idRef="Keywords_austria_eu_driver's_license_number" />
        </Pattern>
    </Entity>

```

### <a name="keywords"></a><span data-ttu-id="8f9b6-118">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="8f9b6-118">Keywords</span></span>

<span data-ttu-id="8f9b6-119">| |</span><span class="sxs-lookup"><span data-stu-id="8f9b6-119"></span></span>
|<span data-ttu-id="8f9b6-120">**Keywords_austria_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="8f9b6-120">**Keywords_austria_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="8f9b6-121">DL</span><span class="sxs-lookup"><span data-stu-id="8f9b6-121">dl#</span></span>  <br/> <span data-ttu-id="8f9b6-122">driver license</span><span class="sxs-lookup"><span data-stu-id="8f9b6-122">driver license</span></span>  <br/> <span data-ttu-id="8f9b6-123">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="8f9b6-123">driver license number</span></span>  <br/> <span data-ttu-id="8f9b6-124">patente di guida</span><span class="sxs-lookup"><span data-stu-id="8f9b6-124">driver licence</span></span>  <br/> <span data-ttu-id="8f9b6-125">driver Lic.</span><span class="sxs-lookup"><span data-stu-id="8f9b6-125">drivers lic.</span></span>  <br/> <span data-ttu-id="8f9b6-126">drivers license</span><span class="sxs-lookup"><span data-stu-id="8f9b6-126">drivers license</span></span>  <br/> <span data-ttu-id="8f9b6-127">driver's licence</span><span class="sxs-lookup"><span data-stu-id="8f9b6-127">driver's licence</span></span>  <br/> <span data-ttu-id="8f9b6-128">driver's license</span><span class="sxs-lookup"><span data-stu-id="8f9b6-128">driver's license</span></span>  <br/> <span data-ttu-id="8f9b6-129">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="8f9b6-129">driver's license number</span></span>  <br/> <span data-ttu-id="8f9b6-130">numero di patente del conducente</span><span class="sxs-lookup"><span data-stu-id="8f9b6-130">driver's licence number</span></span>  <br/>  <span data-ttu-id="8f9b6-131">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="8f9b6-131">driving license number</span></span>  <br/> <span data-ttu-id="8f9b6-132">dlno #</span><span class="sxs-lookup"><span data-stu-id="8f9b6-132">dlno#</span></span>  <br/> <span data-ttu-id="8f9b6-133">fuhrerschein</span><span class="sxs-lookup"><span data-stu-id="8f9b6-133">fuhrerschein</span></span>  <br/> <span data-ttu-id="8f9b6-134">fuhrerschein Republik Osterreich</span><span class="sxs-lookup"><span data-stu-id="8f9b6-134">fuhrerschein republik osterreich</span></span>  <br/> |
   
## <a name="belgium"></a><span data-ttu-id="8f9b6-135">Belgio</span><span class="sxs-lookup"><span data-stu-id="8f9b6-135">Belgium</span></span>

### <a name="format"></a><span data-ttu-id="8f9b6-136">Formato</span><span class="sxs-lookup"><span data-stu-id="8f9b6-136">Format</span></span>

<span data-ttu-id="8f9b6-137">10 cifre senza spazi e delimitatori</span><span class="sxs-lookup"><span data-stu-id="8f9b6-137">10 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="8f9b6-138">Modello</span><span class="sxs-lookup"><span data-stu-id="8f9b6-138">Pattern</span></span>

<span data-ttu-id="8f9b6-139">10 cifre</span><span class="sxs-lookup"><span data-stu-id="8f9b6-139">10 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="8f9b6-140">Checksum</span><span class="sxs-lookup"><span data-stu-id="8f9b6-140">Checksum</span></span>

<span data-ttu-id="8f9b6-141">No</span><span class="sxs-lookup"><span data-stu-id="8f9b6-141">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="8f9b6-142">Definizione</span><span class="sxs-lookup"><span data-stu-id="8f9b6-142">Definition</span></span>

<span data-ttu-id="8f9b6-143">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="8f9b6-143">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="8f9b6-144">L'espressione `Regex_belgium_eu_driver's_license_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="8f9b6-144">The regular expression  `Regex_belgium_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="8f9b6-145">Viene trovata una `Keywords_belgium_eu_driver's_license_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="8f9b6-145">A keyword from  `Keywords_belgium_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_belgium_eu_driver's_license_number" />
          <Match idRef="Keywords_belgium_eu_driver's_license_number" />
        </Pattern>
</Entity>

```

### <a name="keywords"></a><span data-ttu-id="8f9b6-146">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="8f9b6-146">Keywords</span></span>

<span data-ttu-id="8f9b6-147">| |</span><span class="sxs-lookup"><span data-stu-id="8f9b6-147"></span></span>
|<span data-ttu-id="8f9b6-148">**Keywords__belgium_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="8f9b6-148">**Keywords__belgium_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="8f9b6-149">DL</span><span class="sxs-lookup"><span data-stu-id="8f9b6-149">dl#</span></span>  <br/> <span data-ttu-id="8f9b6-150">driver license</span><span class="sxs-lookup"><span data-stu-id="8f9b6-150">driver license</span></span>  <br/> <span data-ttu-id="8f9b6-151">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="8f9b6-151">driver license number</span></span>  <br/> <span data-ttu-id="8f9b6-152">patente di guida</span><span class="sxs-lookup"><span data-stu-id="8f9b6-152">driver licence</span></span>  <br/> <span data-ttu-id="8f9b6-153">driver Lic.</span><span class="sxs-lookup"><span data-stu-id="8f9b6-153">drivers lic.</span></span>  <br/> <span data-ttu-id="8f9b6-154">drivers license</span><span class="sxs-lookup"><span data-stu-id="8f9b6-154">drivers license</span></span>  <br/> <span data-ttu-id="8f9b6-155">drivers licence</span><span class="sxs-lookup"><span data-stu-id="8f9b6-155">drivers licence</span></span>  <br/> <span data-ttu-id="8f9b6-156">driver's license</span><span class="sxs-lookup"><span data-stu-id="8f9b6-156">driver's license</span></span>  <br/> <span data-ttu-id="8f9b6-157">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="8f9b6-157">driver's license number</span></span>  <br/> <span data-ttu-id="8f9b6-158">numero di patente del conducente</span><span class="sxs-lookup"><span data-stu-id="8f9b6-158">driver's licence number</span></span>  <br/> <span data-ttu-id="8f9b6-159">dlno #</span><span class="sxs-lookup"><span data-stu-id="8f9b6-159">dlno#</span></span>  <br/> <span data-ttu-id="8f9b6-160">Rijbewijs</span><span class="sxs-lookup"><span data-stu-id="8f9b6-160">rijbewijs</span></span>  <br/> <span data-ttu-id="8f9b6-161">rijbewijsnummer</span><span class="sxs-lookup"><span data-stu-id="8f9b6-161">rijbewijsnummer</span></span>  <br/> <span data-ttu-id="8f9b6-162">führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="8f9b6-162">führerscheinnummer</span></span>  <br/> <span data-ttu-id="8f9b6-163">fuhrerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="8f9b6-163">fuhrerscheinnummer</span></span>  <br/> <span data-ttu-id="8f9b6-164">fuehrerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="8f9b6-164">fuehrerscheinnummer</span></span>  <br/> <span data-ttu-id="8f9b6-165">Führerschein-Nr</span><span class="sxs-lookup"><span data-stu-id="8f9b6-165">führerschein- nr</span></span>  <br/> <span data-ttu-id="8f9b6-166">fuehrerschein-Nr</span><span class="sxs-lookup"><span data-stu-id="8f9b6-166">fuehrerschein- Nr</span></span>  <br/> <span data-ttu-id="8f9b6-167">fuehrerschein-Nr</span><span class="sxs-lookup"><span data-stu-id="8f9b6-167">fuehrerschein- nr</span></span>  <br/> |
   
## <a name="bulgaria"></a><span data-ttu-id="8f9b6-168">Bulgaria</span><span class="sxs-lookup"><span data-stu-id="8f9b6-168">Bulgaria</span></span>

### <a name="format"></a><span data-ttu-id="8f9b6-169">Formato</span><span class="sxs-lookup"><span data-stu-id="8f9b6-169">Format</span></span>

<span data-ttu-id="8f9b6-170">Nove cifre senza spazi e delimitatori</span><span class="sxs-lookup"><span data-stu-id="8f9b6-170">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="8f9b6-171">Modello</span><span class="sxs-lookup"><span data-stu-id="8f9b6-171">Pattern</span></span>

<span data-ttu-id="8f9b6-172">9 cifre</span><span class="sxs-lookup"><span data-stu-id="8f9b6-172">Nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="8f9b6-173">Checksum</span><span class="sxs-lookup"><span data-stu-id="8f9b6-173">Checksum</span></span>

<span data-ttu-id="8f9b6-174">No</span><span class="sxs-lookup"><span data-stu-id="8f9b6-174">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="8f9b6-175">Definizione</span><span class="sxs-lookup"><span data-stu-id="8f9b6-175">Definition</span></span>

<span data-ttu-id="8f9b6-176">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="8f9b6-176">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="8f9b6-177">L'espressione `Regex_bulgaria_eu_driver's_license_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="8f9b6-177">The regular expression  `Regex_bulgaria_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="8f9b6-178">Viene trovata una `Keywords_bulgaria_eu_driver's_license_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="8f9b6-178">A keyword from  `Keywords_bulgaria_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
             <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_bulgaria_eu_driver's_license_number" />
          <Match idRef="Keywords_bulgaria_eu_driver's_license_number" />
        </Pattern> 
</Entity>    

```

### <a name="keywords"></a><span data-ttu-id="8f9b6-179">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="8f9b6-179">Keywords</span></span>

<span data-ttu-id="8f9b6-180">| |</span><span class="sxs-lookup"><span data-stu-id="8f9b6-180"></span></span>
|<span data-ttu-id="8f9b6-181">**Keywords_bulgaria_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="8f9b6-181">**Keywords_bulgaria_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="8f9b6-182">DL</span><span class="sxs-lookup"><span data-stu-id="8f9b6-182">dl#</span></span>  <br/> <span data-ttu-id="8f9b6-183">driver license</span><span class="sxs-lookup"><span data-stu-id="8f9b6-183">driver license</span></span>  <br/> <span data-ttu-id="8f9b6-184">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="8f9b6-184">driver license number</span></span>  <br/> <span data-ttu-id="8f9b6-185">patente di guida</span><span class="sxs-lookup"><span data-stu-id="8f9b6-185">driver licence</span></span>  <br/> <span data-ttu-id="8f9b6-186">driver Lic.</span><span class="sxs-lookup"><span data-stu-id="8f9b6-186">drivers lic.</span></span>  <br/> <span data-ttu-id="8f9b6-187">drivers license</span><span class="sxs-lookup"><span data-stu-id="8f9b6-187">drivers license</span></span>  <br/> <span data-ttu-id="8f9b6-188">drivers licence</span><span class="sxs-lookup"><span data-stu-id="8f9b6-188">drivers licence</span></span>  <br/> <span data-ttu-id="8f9b6-189">driver's license</span><span class="sxs-lookup"><span data-stu-id="8f9b6-189">driver's license</span></span>  <br/> <span data-ttu-id="8f9b6-190">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="8f9b6-190">driver's license number</span></span>  <br/> <span data-ttu-id="8f9b6-191">numero di patente del conducente</span><span class="sxs-lookup"><span data-stu-id="8f9b6-191">driver's licence number</span></span>  <br/> <span data-ttu-id="8f9b6-192">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="8f9b6-192">driving license number</span></span>  <br/> <span data-ttu-id="8f9b6-193">dlno #</span><span class="sxs-lookup"><span data-stu-id="8f9b6-193">dlno#</span></span>  <br/> <span data-ttu-id="8f9b6-194">свидетелство за управление на мпс</span><span class="sxs-lookup"><span data-stu-id="8f9b6-194">свидетелство за управление на мпс</span></span>  <br/> <span data-ttu-id="8f9b6-195">свидетелство за управление на моторно превозно d'средство</span><span class="sxs-lookup"><span data-stu-id="8f9b6-195">свидетелство за управление на моторно превозно средство</span></span>  <br/> <span data-ttu-id="8f9b6-196">сумпс</span><span class="sxs-lookup"><span data-stu-id="8f9b6-196">сумпс</span></span>  <br/> <span data-ttu-id="8f9b6-197">шофьорска книжка</span><span class="sxs-lookup"><span data-stu-id="8f9b6-197">шофьорска книжка</span></span>  <br/> |
   
## <a name="croatia"></a><span data-ttu-id="8f9b6-198">Croazia</span><span class="sxs-lookup"><span data-stu-id="8f9b6-198">Croatia</span></span>

### <a name="format"></a><span data-ttu-id="8f9b6-199">Formato</span><span class="sxs-lookup"><span data-stu-id="8f9b6-199">Format</span></span>

<span data-ttu-id="8f9b6-200">Otto cifre senza spazi e delimitatori</span><span class="sxs-lookup"><span data-stu-id="8f9b6-200">Eight digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="8f9b6-201">Modello</span><span class="sxs-lookup"><span data-stu-id="8f9b6-201">Pattern</span></span>

<span data-ttu-id="8f9b6-202">Otto cifre</span><span class="sxs-lookup"><span data-stu-id="8f9b6-202">Eight digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="8f9b6-203">Checksum</span><span class="sxs-lookup"><span data-stu-id="8f9b6-203">Checksum</span></span>

<span data-ttu-id="8f9b6-204">No</span><span class="sxs-lookup"><span data-stu-id="8f9b6-204">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="8f9b6-205">Definizione</span><span class="sxs-lookup"><span data-stu-id="8f9b6-205">Definition</span></span>

<span data-ttu-id="8f9b6-206">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="8f9b6-206">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="8f9b6-207">L'espressione `Regex_croatia_eu_driver's_license_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="8f9b6-207">The regular expression  `Regex_croatia_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="8f9b6-208">Viene trovata una `Keywords_croatia_eu_driver's_license_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="8f9b6-208">A keyword from  `Keywords_croatia_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_croatia_eu_driver's_license_number" />
          <Match idRef="Keywords_croatia_eu_driver's_license_number" />
        </Pattern>
</Entity>

```

### <a name="keywords"></a><span data-ttu-id="8f9b6-209">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="8f9b6-209">Keywords</span></span>

<span data-ttu-id="8f9b6-210">| |</span><span class="sxs-lookup"><span data-stu-id="8f9b6-210"></span></span>
|<span data-ttu-id="8f9b6-211">**Keywords_croatia_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="8f9b6-211">**Keywords_croatia_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="8f9b6-212">DL</span><span class="sxs-lookup"><span data-stu-id="8f9b6-212">dl#</span></span>  <br/> <span data-ttu-id="8f9b6-213">driver license</span><span class="sxs-lookup"><span data-stu-id="8f9b6-213">driver license</span></span>  <br/> <span data-ttu-id="8f9b6-214">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="8f9b6-214">driver license number</span></span>  <br/> <span data-ttu-id="8f9b6-215">patente di guida</span><span class="sxs-lookup"><span data-stu-id="8f9b6-215">driver licence</span></span>  <br/> <span data-ttu-id="8f9b6-216">driver Lic.</span><span class="sxs-lookup"><span data-stu-id="8f9b6-216">drivers lic.</span></span>  <br/> <span data-ttu-id="8f9b6-217">drivers license</span><span class="sxs-lookup"><span data-stu-id="8f9b6-217">drivers license</span></span>  <br/> <span data-ttu-id="8f9b6-218">drivers licence</span><span class="sxs-lookup"><span data-stu-id="8f9b6-218">drivers licence</span></span>  <br/> <span data-ttu-id="8f9b6-219">driver's license</span><span class="sxs-lookup"><span data-stu-id="8f9b6-219">driver's license</span></span>  <br/> <span data-ttu-id="8f9b6-220">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="8f9b6-220">driver's license number</span></span>  <br/> <span data-ttu-id="8f9b6-221">numero di patente del conducente</span><span class="sxs-lookup"><span data-stu-id="8f9b6-221">driver's licence number</span></span>  <br/> <span data-ttu-id="8f9b6-222">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="8f9b6-222">driving license number</span></span>  <br/> <span data-ttu-id="8f9b6-223">dlno #</span><span class="sxs-lookup"><span data-stu-id="8f9b6-223">dlno#</span></span>  <br/> <span data-ttu-id="8f9b6-224">vozačka Dozvola</span><span class="sxs-lookup"><span data-stu-id="8f9b6-224">vozačka dozvola</span></span>  <br/> |
   
## <a name="cyprus"></a><span data-ttu-id="8f9b6-225">Cipro</span><span class="sxs-lookup"><span data-stu-id="8f9b6-225">Cyprus</span></span>

### <a name="format"></a><span data-ttu-id="8f9b6-226">Formato</span><span class="sxs-lookup"><span data-stu-id="8f9b6-226">Format</span></span>

<span data-ttu-id="8f9b6-227">12 cifre senza spazi e delimitatori</span><span class="sxs-lookup"><span data-stu-id="8f9b6-227">12 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="8f9b6-228">Modello</span><span class="sxs-lookup"><span data-stu-id="8f9b6-228">Pattern</span></span>

<span data-ttu-id="8f9b6-229">12 cifre</span><span class="sxs-lookup"><span data-stu-id="8f9b6-229">12 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="8f9b6-230">Checksum</span><span class="sxs-lookup"><span data-stu-id="8f9b6-230">Checksum</span></span>

<span data-ttu-id="8f9b6-231">No</span><span class="sxs-lookup"><span data-stu-id="8f9b6-231">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="8f9b6-232">Definizione</span><span class="sxs-lookup"><span data-stu-id="8f9b6-232">Definition</span></span>

<span data-ttu-id="8f9b6-233">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="8f9b6-233">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="8f9b6-234">L'espressione `Regex_cyprus_eu_driver's_license_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="8f9b6-234">The regular expression  `Regex_cyprus_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="8f9b6-235">Viene trovata una `Keywords_cyprus_eu_driver's_license_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="8f9b6-235">A keyword from  `Keywords_cyprus_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_cyprus_eu_driver's_license_number" />
          <Match idRef="Keywords_cyprus_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8f9b6-236">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="8f9b6-236">Keywords</span></span>

<span data-ttu-id="8f9b6-237">| |</span><span class="sxs-lookup"><span data-stu-id="8f9b6-237"></span></span>
|<span data-ttu-id="8f9b6-238">**Keywords_cyprus_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="8f9b6-238">**Keywords_cyprus_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="8f9b6-239">DL</span><span class="sxs-lookup"><span data-stu-id="8f9b6-239">dl#</span></span>  <br/> <span data-ttu-id="8f9b6-240">driver license</span><span class="sxs-lookup"><span data-stu-id="8f9b6-240">driver license</span></span>  <br/> <span data-ttu-id="8f9b6-241">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="8f9b6-241">driver license number</span></span>  <br/> <span data-ttu-id="8f9b6-242">patente di guida</span><span class="sxs-lookup"><span data-stu-id="8f9b6-242">driver licence</span></span>  <br/> <span data-ttu-id="8f9b6-243">driver Lic.</span><span class="sxs-lookup"><span data-stu-id="8f9b6-243">drivers lic.</span></span>  <br/> <span data-ttu-id="8f9b6-244">drivers license</span><span class="sxs-lookup"><span data-stu-id="8f9b6-244">drivers license</span></span>  <br/> <span data-ttu-id="8f9b6-245">drivers licence</span><span class="sxs-lookup"><span data-stu-id="8f9b6-245">drivers licence</span></span>  <br/> <span data-ttu-id="8f9b6-246">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="8f9b6-246">driver's license number</span></span>  <br/> <span data-ttu-id="8f9b6-247">numero di patente del conducente</span><span class="sxs-lookup"><span data-stu-id="8f9b6-247">driver's licence number</span></span>  <br/> <span data-ttu-id="8f9b6-248">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="8f9b6-248">driving license number</span></span>  <br/> <span data-ttu-id="8f9b6-249">dlno #</span><span class="sxs-lookup"><span data-stu-id="8f9b6-249">dlno#</span></span>  <br/> <span data-ttu-id="8f9b6-250">άδεια οδήγησης</span><span class="sxs-lookup"><span data-stu-id="8f9b6-250">άδεια οδήγησης</span></span>  <br/> |
   
## <a name="czech-republic"></a><span data-ttu-id="8f9b6-251">Repubblica Ceca</span><span class="sxs-lookup"><span data-stu-id="8f9b6-251">Czech Republic</span></span>

### <a name="format"></a><span data-ttu-id="8f9b6-252">Formato</span><span class="sxs-lookup"><span data-stu-id="8f9b6-252">Format</span></span>

<span data-ttu-id="8f9b6-253">Due lettere seguite da sei cifre</span><span class="sxs-lookup"><span data-stu-id="8f9b6-253">Two letters followed by six digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="8f9b6-254">Modello</span><span class="sxs-lookup"><span data-stu-id="8f9b6-254">Pattern</span></span>

<span data-ttu-id="8f9b6-255">Otto lettere e cifre:</span><span class="sxs-lookup"><span data-stu-id="8f9b6-255">Eight letters and digits:</span></span>
  
- <span data-ttu-id="8f9b6-256">Due lettere (senza distinzione tra maiuscole e minuscole)</span><span class="sxs-lookup"><span data-stu-id="8f9b6-256">Two letters (not case-sensitive)</span></span>
    
- <span data-ttu-id="8f9b6-257">Uno spazio (facoltativo)</span><span class="sxs-lookup"><span data-stu-id="8f9b6-257">A space (optional)</span></span>
    
- <span data-ttu-id="8f9b6-258">Sei cifre</span><span class="sxs-lookup"><span data-stu-id="8f9b6-258">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="8f9b6-259">Checksum</span><span class="sxs-lookup"><span data-stu-id="8f9b6-259">Checksum</span></span>

<span data-ttu-id="8f9b6-260">No</span><span class="sxs-lookup"><span data-stu-id="8f9b6-260">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="8f9b6-261">Definizione</span><span class="sxs-lookup"><span data-stu-id="8f9b6-261">Definition</span></span>

<span data-ttu-id="8f9b6-262">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="8f9b6-262">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="8f9b6-263">L'espressione `Regex_czech_republic_eu_driver's_license_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="8f9b6-263">The regular expression  `Regex_czech_republic_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="8f9b6-264">Viene trovata una `Keywords_czech_republic_eu_driver's_license_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="8f9b6-264">A keyword from  `Keywords_czech_republic_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_czech_republic_eu_driver's_license_number" />
          <Match idRef="Keywords_czech_republic_eu_driver's_license_number" />
        </Pattern>
</Entity>

```

### <a name="keywords"></a><span data-ttu-id="8f9b6-265">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="8f9b6-265">Keywords</span></span>

<span data-ttu-id="8f9b6-266">| |</span><span class="sxs-lookup"><span data-stu-id="8f9b6-266"></span></span>
|<span data-ttu-id="8f9b6-267">**Keywords_czech_republic_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="8f9b6-267">**Keywords_czech_republic_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="8f9b6-268">DL</span><span class="sxs-lookup"><span data-stu-id="8f9b6-268">dl#</span></span>  <br/> <span data-ttu-id="8f9b6-269">driver license</span><span class="sxs-lookup"><span data-stu-id="8f9b6-269">driver license</span></span>  <br/> <span data-ttu-id="8f9b6-270">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="8f9b6-270">driver license number</span></span>  <br/> <span data-ttu-id="8f9b6-271">patente di guida</span><span class="sxs-lookup"><span data-stu-id="8f9b6-271">driver licence</span></span>  <br/> <span data-ttu-id="8f9b6-272">driver Lic.</span><span class="sxs-lookup"><span data-stu-id="8f9b6-272">drivers lic.</span></span>  <br/> <span data-ttu-id="8f9b6-273">drivers license</span><span class="sxs-lookup"><span data-stu-id="8f9b6-273">drivers license</span></span>  <br/> <span data-ttu-id="8f9b6-274">drivers licence</span><span class="sxs-lookup"><span data-stu-id="8f9b6-274">drivers licence</span></span>  <br/> <span data-ttu-id="8f9b6-275">driver's license</span><span class="sxs-lookup"><span data-stu-id="8f9b6-275">driver's license</span></span>  <br/> <span data-ttu-id="8f9b6-276">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="8f9b6-276">driver's license number</span></span>  <br/> <span data-ttu-id="8f9b6-277">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="8f9b6-277">driver's license number</span></span>  <br/> <span data-ttu-id="8f9b6-278">numero di patente del conducente</span><span class="sxs-lookup"><span data-stu-id="8f9b6-278">driver's licence number</span></span>  <br/> <span data-ttu-id="8f9b6-279">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="8f9b6-279">driving license number</span></span>  <br/> <span data-ttu-id="8f9b6-280">dlno #</span><span class="sxs-lookup"><span data-stu-id="8f9b6-280">dlno#</span></span>  <br/> <span data-ttu-id="8f9b6-281">řidičský prúkaz</span><span class="sxs-lookup"><span data-stu-id="8f9b6-281">řidičský prúkaz</span></span>  <br/> |
   
## <a name="denmark"></a><span data-ttu-id="8f9b6-282">Danimarca</span><span class="sxs-lookup"><span data-stu-id="8f9b6-282">Denmark</span></span>

### <a name="format"></a><span data-ttu-id="8f9b6-283">Formato</span><span class="sxs-lookup"><span data-stu-id="8f9b6-283">Format</span></span>

<span data-ttu-id="8f9b6-284">Otto cifre senza spazi e delimitatori</span><span class="sxs-lookup"><span data-stu-id="8f9b6-284">Eight digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="8f9b6-285">Modello</span><span class="sxs-lookup"><span data-stu-id="8f9b6-285">Pattern</span></span>

<span data-ttu-id="8f9b6-286">Otto cifre</span><span class="sxs-lookup"><span data-stu-id="8f9b6-286">Eight digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="8f9b6-287">Checksum</span><span class="sxs-lookup"><span data-stu-id="8f9b6-287">Checksum</span></span>

<span data-ttu-id="8f9b6-288">Sì</span><span class="sxs-lookup"><span data-stu-id="8f9b6-288">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="8f9b6-289">Definizione</span><span class="sxs-lookup"><span data-stu-id="8f9b6-289">Definition</span></span>

<span data-ttu-id="8f9b6-290">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="8f9b6-290">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="8f9b6-291">L'espressione `Regex_denmark_eu_driver's_license_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="8f9b6-291">The regular expression  `Regex_denmark_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="8f9b6-292">Viene trovata una `Keywords_denmark_eu_driver's_license_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="8f9b6-292">A keyword from  `Keywords_denmark_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_denmark_eu_driver's_license_number" />
          <Match idRef="Keywords_denmark_eu_driver's_license_number" />
        </Pattern>
</Entity>

```

### <a name="keywords"></a><span data-ttu-id="8f9b6-293">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="8f9b6-293">Keywords</span></span>

<span data-ttu-id="8f9b6-294">| |</span><span class="sxs-lookup"><span data-stu-id="8f9b6-294"></span></span>
|<span data-ttu-id="8f9b6-295">**Keywords_denmark_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="8f9b6-295">**Keywords_denmark_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="8f9b6-296">DL</span><span class="sxs-lookup"><span data-stu-id="8f9b6-296">dl#</span></span>  <br/> <span data-ttu-id="8f9b6-297">driver license</span><span class="sxs-lookup"><span data-stu-id="8f9b6-297">driver license</span></span>  <br/> <span data-ttu-id="8f9b6-298">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="8f9b6-298">driver license number</span></span>  <br/> <span data-ttu-id="8f9b6-299">patente di guida</span><span class="sxs-lookup"><span data-stu-id="8f9b6-299">driver licence</span></span>  <br/> <span data-ttu-id="8f9b6-300">driver Lic.</span><span class="sxs-lookup"><span data-stu-id="8f9b6-300">drivers lic.</span></span>  <br/> <span data-ttu-id="8f9b6-301">drivers license</span><span class="sxs-lookup"><span data-stu-id="8f9b6-301">drivers license</span></span>  <br/> <span data-ttu-id="8f9b6-302">drivers licence</span><span class="sxs-lookup"><span data-stu-id="8f9b6-302">drivers licence</span></span>  <br/> <span data-ttu-id="8f9b6-303">driver's license</span><span class="sxs-lookup"><span data-stu-id="8f9b6-303">driver's license</span></span>  <br/> <span data-ttu-id="8f9b6-304">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="8f9b6-304">driver's license number</span></span>  <br/> <span data-ttu-id="8f9b6-305">numero di patente del conducente</span><span class="sxs-lookup"><span data-stu-id="8f9b6-305">driver's licence number</span></span>  <br/> <span data-ttu-id="8f9b6-306">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="8f9b6-306">driving license number</span></span>  <br/> <span data-ttu-id="8f9b6-307">dlno #</span><span class="sxs-lookup"><span data-stu-id="8f9b6-307">dlno#</span></span>  <br/> <span data-ttu-id="8f9b6-308">kørekort</span><span class="sxs-lookup"><span data-stu-id="8f9b6-308">kørekort</span></span>  <br/> <span data-ttu-id="8f9b6-309">Kørekortnummer</span><span class="sxs-lookup"><span data-stu-id="8f9b6-309">kørekortnummer</span></span>  <br/> |
   
## <a name="estonia"></a><span data-ttu-id="8f9b6-310">Estonia</span><span class="sxs-lookup"><span data-stu-id="8f9b6-310">Estonia</span></span>

### <a name="format"></a><span data-ttu-id="8f9b6-311">Formato</span><span class="sxs-lookup"><span data-stu-id="8f9b6-311">Format</span></span>

<span data-ttu-id="8f9b6-312">Due lettere seguite da sei cifre</span><span class="sxs-lookup"><span data-stu-id="8f9b6-312">Two letters followed by six digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="8f9b6-313">Modello</span><span class="sxs-lookup"><span data-stu-id="8f9b6-313">Pattern</span></span>

<span data-ttu-id="8f9b6-314">Due lettere e sei cifre:</span><span class="sxs-lookup"><span data-stu-id="8f9b6-314">Two letters and six digits:</span></span>
  
-  <span data-ttu-id="8f9b6-315">Lettere "ET" (senza distinzione tra maiuscole e minuscole)</span><span class="sxs-lookup"><span data-stu-id="8f9b6-315">The letters "ET" (not case-sensitive)</span></span> 
    
- <span data-ttu-id="8f9b6-316">Sei cifre</span><span class="sxs-lookup"><span data-stu-id="8f9b6-316">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="8f9b6-317">Checksum</span><span class="sxs-lookup"><span data-stu-id="8f9b6-317">Checksum</span></span>

<span data-ttu-id="8f9b6-318">No</span><span class="sxs-lookup"><span data-stu-id="8f9b6-318">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="8f9b6-319">Definizione</span><span class="sxs-lookup"><span data-stu-id="8f9b6-319">Definition</span></span>

<span data-ttu-id="8f9b6-320">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="8f9b6-320">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="8f9b6-321">L'espressione `Regex_estonia_eu_driver's_license_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="8f9b6-321">The regular expression  `Regex_estonia_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="8f9b6-322">Viene trovata una `Keywords_estonia_eu_driver's_license_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="8f9b6-322">A keyword from  `Keywords_estonia_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_estonia_eu_driver's_license_number" />
          <Match idRef="Keywords_estonia_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8f9b6-323">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="8f9b6-323">Keywords</span></span>

<span data-ttu-id="8f9b6-324">| |</span><span class="sxs-lookup"><span data-stu-id="8f9b6-324"></span></span>
|<span data-ttu-id="8f9b6-325">**Keywords_estonia_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="8f9b6-325">**Keywords_estonia_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="8f9b6-326">DL</span><span class="sxs-lookup"><span data-stu-id="8f9b6-326">dl#</span></span>  <br/> <span data-ttu-id="8f9b6-327">driver license</span><span class="sxs-lookup"><span data-stu-id="8f9b6-327">driver license</span></span>  <br/> <span data-ttu-id="8f9b6-328">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="8f9b6-328">driver license number</span></span>  <br/> <span data-ttu-id="8f9b6-329">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="8f9b6-329">driver license number</span></span>  <br/> <span data-ttu-id="8f9b6-330">patente di guida</span><span class="sxs-lookup"><span data-stu-id="8f9b6-330">driver licence</span></span>  <br/> <span data-ttu-id="8f9b6-331">driver Lic.</span><span class="sxs-lookup"><span data-stu-id="8f9b6-331">drivers lic.</span></span>  <br/> <span data-ttu-id="8f9b6-332">drivers license</span><span class="sxs-lookup"><span data-stu-id="8f9b6-332">drivers license</span></span>  <br/> <span data-ttu-id="8f9b6-333">drivers licence</span><span class="sxs-lookup"><span data-stu-id="8f9b6-333">drivers licence</span></span>  <br/> <span data-ttu-id="8f9b6-334">driver's license</span><span class="sxs-lookup"><span data-stu-id="8f9b6-334">driver's license</span></span>  <br/> <span data-ttu-id="8f9b6-335">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="8f9b6-335">driver's license number</span></span>  <br/> <span data-ttu-id="8f9b6-336">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="8f9b6-336">driving license number</span></span>  <br/> <span data-ttu-id="8f9b6-337">dlno #</span><span class="sxs-lookup"><span data-stu-id="8f9b6-337">dlno#</span></span>  <br/> <span data-ttu-id="8f9b6-338">permis de conduire</span><span class="sxs-lookup"><span data-stu-id="8f9b6-338">permis de conduire</span></span>  <br/> |
   
## <a name="finland"></a><span data-ttu-id="8f9b6-339">Finlandia</span><span class="sxs-lookup"><span data-stu-id="8f9b6-339">Finland</span></span>

### <a name="format"></a><span data-ttu-id="8f9b6-340">Formato</span><span class="sxs-lookup"><span data-stu-id="8f9b6-340">Format</span></span>

<span data-ttu-id="8f9b6-341">10 cifre contenenti una lineetta</span><span class="sxs-lookup"><span data-stu-id="8f9b6-341">10 digits containing a hyphen</span></span>
  
### <a name="pattern"></a><span data-ttu-id="8f9b6-342">Modello</span><span class="sxs-lookup"><span data-stu-id="8f9b6-342">Pattern</span></span>

<span data-ttu-id="8f9b6-343">10 cifre contenenti un trattino:</span><span class="sxs-lookup"><span data-stu-id="8f9b6-343">10 digits containing a hyphen:</span></span>
  
-  <span data-ttu-id="8f9b6-344">Sei cifre</span><span class="sxs-lookup"><span data-stu-id="8f9b6-344">Six digits</span></span> 
    
- <span data-ttu-id="8f9b6-345">Una lineetta</span><span class="sxs-lookup"><span data-stu-id="8f9b6-345">A hyphen</span></span>
    
-  <span data-ttu-id="8f9b6-346">Quattro cifre</span><span class="sxs-lookup"><span data-stu-id="8f9b6-346">Four digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="8f9b6-347">Checksum</span><span class="sxs-lookup"><span data-stu-id="8f9b6-347">Checksum</span></span>

<span data-ttu-id="8f9b6-348">No</span><span class="sxs-lookup"><span data-stu-id="8f9b6-348">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="8f9b6-349">Definizione</span><span class="sxs-lookup"><span data-stu-id="8f9b6-349">Definition</span></span>

<span data-ttu-id="8f9b6-350">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="8f9b6-350">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="8f9b6-351">L'espressione `Regex_finland_eu_driver's_license_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="8f9b6-351">The regular expression  `Regex_finland_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="8f9b6-352">Viene trovata una `Keywords_finland_eu_driver's_license_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="8f9b6-352">A keyword from  `Keywords_finland_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_finland_eu_driver's_license_number" />
          <Match idRef="Keywords_finland_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8f9b6-353">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="8f9b6-353">Keywords</span></span>

<span data-ttu-id="8f9b6-354">| |</span><span class="sxs-lookup"><span data-stu-id="8f9b6-354"></span></span>
|<span data-ttu-id="8f9b6-355">**Keywords_finland_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="8f9b6-355">**Keywords_finland_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="8f9b6-356">DL</span><span class="sxs-lookup"><span data-stu-id="8f9b6-356">dl#</span></span>  <br/> <span data-ttu-id="8f9b6-357">driver license</span><span class="sxs-lookup"><span data-stu-id="8f9b6-357">driver license</span></span>  <br/> <span data-ttu-id="8f9b6-358">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="8f9b6-358">driver license number</span></span>  <br/> <span data-ttu-id="8f9b6-359">patente di guida</span><span class="sxs-lookup"><span data-stu-id="8f9b6-359">driver licence</span></span>  <br/> <span data-ttu-id="8f9b6-360">driver Lic.</span><span class="sxs-lookup"><span data-stu-id="8f9b6-360">drivers lic.</span></span>  <br/> <span data-ttu-id="8f9b6-361">drivers license</span><span class="sxs-lookup"><span data-stu-id="8f9b6-361">drivers license</span></span>  <br/> <span data-ttu-id="8f9b6-362">drivers licence</span><span class="sxs-lookup"><span data-stu-id="8f9b6-362">drivers licence</span></span>  <br/> <span data-ttu-id="8f9b6-363">driver's license</span><span class="sxs-lookup"><span data-stu-id="8f9b6-363">driver's license</span></span>  <br/> <span data-ttu-id="8f9b6-364">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="8f9b6-364">driver's license number</span></span>  <br/> <span data-ttu-id="8f9b6-365">numero di patente del conducente</span><span class="sxs-lookup"><span data-stu-id="8f9b6-365">driver's licence number</span></span>  <br/> <span data-ttu-id="8f9b6-366">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="8f9b6-366">driving license number</span></span>  <br/> <span data-ttu-id="8f9b6-367">dlno #</span><span class="sxs-lookup"><span data-stu-id="8f9b6-367">dlno#</span></span>  <br/> <span data-ttu-id="8f9b6-368">AJOKORTTI</span><span class="sxs-lookup"><span data-stu-id="8f9b6-368">ajokortti</span></span>  <br/> |
   
## <a name="france"></a><span data-ttu-id="8f9b6-369">Francia</span><span class="sxs-lookup"><span data-stu-id="8f9b6-369">France</span></span>

<span data-ttu-id="8f9b6-370">Per informazioni dettagliate, vedere la sezione "numero della patente di Francia" in [che cosa cercano i tipi di informazioni riservate](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="8f9b6-370">For details, see the section "France Driver's License Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="germany"></a><span data-ttu-id="8f9b6-371">Germania</span><span class="sxs-lookup"><span data-stu-id="8f9b6-371">Germany</span></span>

<span data-ttu-id="8f9b6-372">Per informazioni dettagliate, vedere la sezione "numero di patente di guida tedesco" in [che cosa cercano i tipi di informazioni riservate](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="8f9b6-372">For details, see the section "German Driver's License Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="greece"></a><span data-ttu-id="8f9b6-373">Grecia</span><span class="sxs-lookup"><span data-stu-id="8f9b6-373">Greece</span></span>

### <a name="format"></a><span data-ttu-id="8f9b6-374">Formato</span><span class="sxs-lookup"><span data-stu-id="8f9b6-374">Format</span></span>

<span data-ttu-id="8f9b6-375">Nove cifre senza spazi e delimitatori</span><span class="sxs-lookup"><span data-stu-id="8f9b6-375">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="8f9b6-376">Modello</span><span class="sxs-lookup"><span data-stu-id="8f9b6-376">Pattern</span></span>

 <span data-ttu-id="8f9b6-377">9 cifre</span><span class="sxs-lookup"><span data-stu-id="8f9b6-377">Nine digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="8f9b6-378">Checksum</span><span class="sxs-lookup"><span data-stu-id="8f9b6-378">Checksum</span></span>

<span data-ttu-id="8f9b6-379">No</span><span class="sxs-lookup"><span data-stu-id="8f9b6-379">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="8f9b6-380">Definizione</span><span class="sxs-lookup"><span data-stu-id="8f9b6-380">Definition</span></span>

<span data-ttu-id="8f9b6-381">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="8f9b6-381">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="8f9b6-382">L'espressione `Regex_greece_eu_driver's_license_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="8f9b6-382">The regular expression  `Regex_greece_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="8f9b6-383">Viene trovata una `Keywords_greece_eu_driver's_license_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="8f9b6-383">A keyword from  `Keywords_greece_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_greece_eu_driver's_license_number" />
          <Match idRef="Keywords_greece_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8f9b6-384">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="8f9b6-384">Keywords</span></span>

<span data-ttu-id="8f9b6-385">| |</span><span class="sxs-lookup"><span data-stu-id="8f9b6-385"></span></span>
|<span data-ttu-id="8f9b6-386">**Keywords_greece_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="8f9b6-386">**Keywords_greece_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="8f9b6-387">DlL</span><span class="sxs-lookup"><span data-stu-id="8f9b6-387">dlL#</span></span>  <br/> <span data-ttu-id="8f9b6-388">driver license</span><span class="sxs-lookup"><span data-stu-id="8f9b6-388">driver license</span></span>  <br/> <span data-ttu-id="8f9b6-389">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="8f9b6-389">driver license number</span></span>  <br/> <span data-ttu-id="8f9b6-390">patente di guida</span><span class="sxs-lookup"><span data-stu-id="8f9b6-390">driver licence</span></span>  <br/> <span data-ttu-id="8f9b6-391">driver Lic.</span><span class="sxs-lookup"><span data-stu-id="8f9b6-391">drivers lic.</span></span>  <br/> <span data-ttu-id="8f9b6-392">drivers license</span><span class="sxs-lookup"><span data-stu-id="8f9b6-392">drivers license</span></span>  <br/> <span data-ttu-id="8f9b6-393">drivers licence</span><span class="sxs-lookup"><span data-stu-id="8f9b6-393">drivers licence</span></span>  <br/> <span data-ttu-id="8f9b6-394">driver's license</span><span class="sxs-lookup"><span data-stu-id="8f9b6-394">driver's license</span></span>  <br/> <span data-ttu-id="8f9b6-395">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="8f9b6-395">driver's license number</span></span>  <br/> <span data-ttu-id="8f9b6-396">numero di patente del conducente</span><span class="sxs-lookup"><span data-stu-id="8f9b6-396">driver's licence number</span></span>  <br/> <span data-ttu-id="8f9b6-397">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="8f9b6-397">driving license number</span></span>  <br/> <span data-ttu-id="8f9b6-398">dlno #</span><span class="sxs-lookup"><span data-stu-id="8f9b6-398">dlno#</span></span>  <br/> <span data-ttu-id="8f9b6-399">δεια οδήγησης</span><span class="sxs-lookup"><span data-stu-id="8f9b6-399">δεια οδήγησης</span></span>  <br/> <span data-ttu-id="8f9b6-400">Adeia odigisis</span><span class="sxs-lookup"><span data-stu-id="8f9b6-400">Adeia odigisis</span></span>  <br/> |
   
## <a name="hungary"></a><span data-ttu-id="8f9b6-401">Ungheria</span><span class="sxs-lookup"><span data-stu-id="8f9b6-401">Hungary</span></span>

### <a name="format"></a><span data-ttu-id="8f9b6-402">Formato</span><span class="sxs-lookup"><span data-stu-id="8f9b6-402">Format</span></span>

<span data-ttu-id="8f9b6-403">Due lettere seguite da sei cifre</span><span class="sxs-lookup"><span data-stu-id="8f9b6-403">Two letters followed by six digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="8f9b6-404">Modello</span><span class="sxs-lookup"><span data-stu-id="8f9b6-404">Pattern</span></span>

<span data-ttu-id="8f9b6-405">Due lettere e sei cifre:</span><span class="sxs-lookup"><span data-stu-id="8f9b6-405">Two letters and six digits:</span></span>
  
-  <span data-ttu-id="8f9b6-406">Due lettere (senza distinzione tra maiuscole e minuscole)</span><span class="sxs-lookup"><span data-stu-id="8f9b6-406">Two letters (not case-sensitive)</span></span> 
    
- <span data-ttu-id="8f9b6-407">Sei cifre</span><span class="sxs-lookup"><span data-stu-id="8f9b6-407">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="8f9b6-408">Checksum</span><span class="sxs-lookup"><span data-stu-id="8f9b6-408">Checksum</span></span>

<span data-ttu-id="8f9b6-409">No</span><span class="sxs-lookup"><span data-stu-id="8f9b6-409">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="8f9b6-410">Definizione</span><span class="sxs-lookup"><span data-stu-id="8f9b6-410">Definition</span></span>

<span data-ttu-id="8f9b6-411">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="8f9b6-411">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="8f9b6-412">L'espressione `Regex_hungary_eu_driver's_license_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="8f9b6-412">The regular expression  `Regex_hungary_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="8f9b6-413">Viene trovata una `Keywords_hungary_eu_driver's_license_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="8f9b6-413">A keyword from  `Keywords_hungary_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_hungary_eu_driver's_license_number" />
          <Match idRef="Keywords_hungary_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8f9b6-414">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="8f9b6-414">Keywords</span></span>

<span data-ttu-id="8f9b6-415">| |</span><span class="sxs-lookup"><span data-stu-id="8f9b6-415"></span></span>
|<span data-ttu-id="8f9b6-416">**Keywords_hungary_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="8f9b6-416">**Keywords_hungary_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="8f9b6-417">DL</span><span class="sxs-lookup"><span data-stu-id="8f9b6-417">dl#</span></span>  <br/> <span data-ttu-id="8f9b6-418">driver license</span><span class="sxs-lookup"><span data-stu-id="8f9b6-418">driver license</span></span>  <br/> <span data-ttu-id="8f9b6-419">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="8f9b6-419">driver license number</span></span>  <br/> <span data-ttu-id="8f9b6-420">patente di guida</span><span class="sxs-lookup"><span data-stu-id="8f9b6-420">driver licence</span></span>  <br/> <span data-ttu-id="8f9b6-421">driver Lic.</span><span class="sxs-lookup"><span data-stu-id="8f9b6-421">drivers lic.</span></span>  <br/> <span data-ttu-id="8f9b6-422">drivers license</span><span class="sxs-lookup"><span data-stu-id="8f9b6-422">drivers license</span></span>  <br/> <span data-ttu-id="8f9b6-423">drivers licence</span><span class="sxs-lookup"><span data-stu-id="8f9b6-423">drivers licence</span></span>  <br/> <span data-ttu-id="8f9b6-424">driver's license</span><span class="sxs-lookup"><span data-stu-id="8f9b6-424">driver's license</span></span>  <br/> <span data-ttu-id="8f9b6-425">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="8f9b6-425">driver's license number</span></span>  <br/> <span data-ttu-id="8f9b6-426">numero di patente del conducente</span><span class="sxs-lookup"><span data-stu-id="8f9b6-426">driver's licence number</span></span>  <br/> <span data-ttu-id="8f9b6-427">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="8f9b6-427">driving license number</span></span>  <br/> <span data-ttu-id="8f9b6-428">dlno #</span><span class="sxs-lookup"><span data-stu-id="8f9b6-428">dlno#</span></span>  <br/> <span data-ttu-id="8f9b6-429">vezetoi engedely</span><span class="sxs-lookup"><span data-stu-id="8f9b6-429">vezetoi engedely</span></span>  <br/> |
   
## <a name="ireland"></a><span data-ttu-id="8f9b6-430">Irlanda</span><span class="sxs-lookup"><span data-stu-id="8f9b6-430">Ireland</span></span>

### <a name="format"></a><span data-ttu-id="8f9b6-431">Formato</span><span class="sxs-lookup"><span data-stu-id="8f9b6-431">Format</span></span>

<span data-ttu-id="8f9b6-432">Sei cifre seguite da quattro lettere</span><span class="sxs-lookup"><span data-stu-id="8f9b6-432">Six digits followed by four letters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="8f9b6-433">Modello</span><span class="sxs-lookup"><span data-stu-id="8f9b6-433">Pattern</span></span>

<span data-ttu-id="8f9b6-434">Sei cifre e quattro lettere:</span><span class="sxs-lookup"><span data-stu-id="8f9b6-434">Six digits and four letters:</span></span>
  
- <span data-ttu-id="8f9b6-435">Sei cifre</span><span class="sxs-lookup"><span data-stu-id="8f9b6-435">Six digits</span></span>
    
- <span data-ttu-id="8f9b6-436">Quattro lettere (senza distinzione tra maiuscole e minuscole)</span><span class="sxs-lookup"><span data-stu-id="8f9b6-436">Four letters (not case-sensitive)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="8f9b6-437">Checksum</span><span class="sxs-lookup"><span data-stu-id="8f9b6-437">Checksum</span></span>

<span data-ttu-id="8f9b6-438">No</span><span class="sxs-lookup"><span data-stu-id="8f9b6-438">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="8f9b6-439">Definizione</span><span class="sxs-lookup"><span data-stu-id="8f9b6-439">Definition</span></span>

<span data-ttu-id="8f9b6-440">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="8f9b6-440">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="8f9b6-441">L'espressione `Regex_ireland_eu_driver's_license_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="8f9b6-441">The regular expression  `Regex_ireland_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="8f9b6-442">Viene trovata una `Keywords_ireland_eu_driver's_license_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="8f9b6-442">A keyword from  `Keywords_ireland_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_ireland_eu_driver's_license_number" />
          <Match idRef="Keywords_ireland_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8f9b6-443">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="8f9b6-443">Keywords</span></span>

<span data-ttu-id="8f9b6-444">| |</span><span class="sxs-lookup"><span data-stu-id="8f9b6-444"></span></span>
|<span data-ttu-id="8f9b6-445">**Keywords_ireland_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="8f9b6-445">**Keywords_ireland_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="8f9b6-446">DL</span><span class="sxs-lookup"><span data-stu-id="8f9b6-446">dl#</span></span>  <br/> <span data-ttu-id="8f9b6-447">driver license</span><span class="sxs-lookup"><span data-stu-id="8f9b6-447">driver license</span></span>  <br/> <span data-ttu-id="8f9b6-448">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="8f9b6-448">driver license number</span></span>  <br/> <span data-ttu-id="8f9b6-449">patente di guida</span><span class="sxs-lookup"><span data-stu-id="8f9b6-449">driver licence</span></span>  <br/> <span data-ttu-id="8f9b6-450">driver Lic.</span><span class="sxs-lookup"><span data-stu-id="8f9b6-450">drivers lic.</span></span>  <br/> <span data-ttu-id="8f9b6-451">drivers license</span><span class="sxs-lookup"><span data-stu-id="8f9b6-451">drivers license</span></span>  <br/> <span data-ttu-id="8f9b6-452">drivers licence</span><span class="sxs-lookup"><span data-stu-id="8f9b6-452">drivers licence</span></span>  <br/> <span data-ttu-id="8f9b6-453">driver's license</span><span class="sxs-lookup"><span data-stu-id="8f9b6-453">driver's license</span></span>  <br/> <span data-ttu-id="8f9b6-454">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="8f9b6-454">driver's license number</span></span>  <br/> <span data-ttu-id="8f9b6-455">numero di patente del conducente</span><span class="sxs-lookup"><span data-stu-id="8f9b6-455">driver's licence number</span></span>  <br/> <span data-ttu-id="8f9b6-456">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="8f9b6-456">driving license number</span></span>  <br/> <span data-ttu-id="8f9b6-457">dlno #</span><span class="sxs-lookup"><span data-stu-id="8f9b6-457">dlno#</span></span>  <br/> <span data-ttu-id="8f9b6-458">Ceadúnas Tiomána</span><span class="sxs-lookup"><span data-stu-id="8f9b6-458">ceadúnas tiomána</span></span>  <br/> |
   
## <a name="italy"></a><span data-ttu-id="8f9b6-459">Italia</span><span class="sxs-lookup"><span data-stu-id="8f9b6-459">Italy</span></span>

<span data-ttu-id="8f9b6-460">Per informazioni dettagliate, vedere la sezione "numero di licenza del conducente italiano" in [che cosa cercano i tipi di informazioni riservate](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="8f9b6-460">For details, see the section "Italy Driver's License Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="latvia"></a><span data-ttu-id="8f9b6-461">Lettonia</span><span class="sxs-lookup"><span data-stu-id="8f9b6-461">Latvia</span></span>

### <a name="format"></a><span data-ttu-id="8f9b6-462">Formato</span><span class="sxs-lookup"><span data-stu-id="8f9b6-462">Format</span></span>

<span data-ttu-id="8f9b6-463">Tre lettere seguite da sei cifre</span><span class="sxs-lookup"><span data-stu-id="8f9b6-463">Three letters followed by six digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="8f9b6-464">Modello</span><span class="sxs-lookup"><span data-stu-id="8f9b6-464">Pattern</span></span>

<span data-ttu-id="8f9b6-465">Tre lettere e sei cifre:</span><span class="sxs-lookup"><span data-stu-id="8f9b6-465">Three letters and six digits:</span></span>
  
-  <span data-ttu-id="8f9b6-466">Tre lettere (senza distinzione tra maiuscole e minuscole)</span><span class="sxs-lookup"><span data-stu-id="8f9b6-466">Three letters (not case-sensitive)</span></span> 
    
- <span data-ttu-id="8f9b6-467">Sei cifre</span><span class="sxs-lookup"><span data-stu-id="8f9b6-467">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="8f9b6-468">Checksum</span><span class="sxs-lookup"><span data-stu-id="8f9b6-468">Checksum</span></span>

<span data-ttu-id="8f9b6-469">No</span><span class="sxs-lookup"><span data-stu-id="8f9b6-469">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="8f9b6-470">Definizione</span><span class="sxs-lookup"><span data-stu-id="8f9b6-470">Definition</span></span>

<span data-ttu-id="8f9b6-471">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="8f9b6-471">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="8f9b6-472">L'espressione `Regex_latvia_eu_driver's_license_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="8f9b6-472">The regular expression  `Regex_latvia_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="8f9b6-473">Viene trovata una `Keywords_latvia_eu_driver's_license_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="8f9b6-473">A keyword from  `Keywords_latvia_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_latvia_eu_driver's_license_number" />
          <Match idRef="Keywords_latvia_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8f9b6-474">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="8f9b6-474">Keywords</span></span>

<span data-ttu-id="8f9b6-475">| |</span><span class="sxs-lookup"><span data-stu-id="8f9b6-475"></span></span>
|<span data-ttu-id="8f9b6-476">**Keywords_latvia_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="8f9b6-476">**Keywords_latvia_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="8f9b6-477">DL</span><span class="sxs-lookup"><span data-stu-id="8f9b6-477">dl#</span></span>  <br/> <span data-ttu-id="8f9b6-478">driver license</span><span class="sxs-lookup"><span data-stu-id="8f9b6-478">driver license</span></span>  <br/> <span data-ttu-id="8f9b6-479">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="8f9b6-479">driver license number</span></span>  <br/> <span data-ttu-id="8f9b6-480">patente di guida</span><span class="sxs-lookup"><span data-stu-id="8f9b6-480">driver licence</span></span>  <br/> <span data-ttu-id="8f9b6-481">driver Lic.</span><span class="sxs-lookup"><span data-stu-id="8f9b6-481">drivers lic.</span></span>  <br/> <span data-ttu-id="8f9b6-482">drivers license</span><span class="sxs-lookup"><span data-stu-id="8f9b6-482">drivers license</span></span>  <br/> <span data-ttu-id="8f9b6-483">drivers licence</span><span class="sxs-lookup"><span data-stu-id="8f9b6-483">drivers licence</span></span>  <br/> <span data-ttu-id="8f9b6-484">driver's license</span><span class="sxs-lookup"><span data-stu-id="8f9b6-484">driver's license</span></span>  <br/> <span data-ttu-id="8f9b6-485">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="8f9b6-485">driver's license number</span></span>  <br/> <span data-ttu-id="8f9b6-486">numero di patente del conducente</span><span class="sxs-lookup"><span data-stu-id="8f9b6-486">driver's licence number</span></span>  <br/> <span data-ttu-id="8f9b6-487">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="8f9b6-487">driving license number</span></span>  <br/> <span data-ttu-id="8f9b6-488">dlno #</span><span class="sxs-lookup"><span data-stu-id="8f9b6-488">dlno#</span></span>  <br/> <span data-ttu-id="8f9b6-489">autovadītāja apliecība</span><span class="sxs-lookup"><span data-stu-id="8f9b6-489">autovadītāja apliecība</span></span>  <br/> |
   
## <a name="lithuania"></a><span data-ttu-id="8f9b6-490">Lituania</span><span class="sxs-lookup"><span data-stu-id="8f9b6-490">Lithuania</span></span>

### <a name="format"></a><span data-ttu-id="8f9b6-491">Formato</span><span class="sxs-lookup"><span data-stu-id="8f9b6-491">Format</span></span>

<span data-ttu-id="8f9b6-492">Otto cifre senza spazi e delimitatori</span><span class="sxs-lookup"><span data-stu-id="8f9b6-492">Eight digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="8f9b6-493">Modello</span><span class="sxs-lookup"><span data-stu-id="8f9b6-493">Pattern</span></span>

 <span data-ttu-id="8f9b6-494">Otto cifre</span><span class="sxs-lookup"><span data-stu-id="8f9b6-494">Eight digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="8f9b6-495">Checksum</span><span class="sxs-lookup"><span data-stu-id="8f9b6-495">Checksum</span></span>

<span data-ttu-id="8f9b6-496">No</span><span class="sxs-lookup"><span data-stu-id="8f9b6-496">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="8f9b6-497">Definizione</span><span class="sxs-lookup"><span data-stu-id="8f9b6-497">Definition</span></span>

<span data-ttu-id="8f9b6-498">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="8f9b6-498">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="8f9b6-499">L'espressione `Regex_lithuania_eu_driver's_license_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="8f9b6-499">The regular expression  `Regex_lithuania_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="8f9b6-500">Viene trovata una `Keywords_lithuania_eu_driver's_license_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="8f9b6-500">A keyword from  `Keywords_lithuania_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_lithuania_eu_driver's_license_number" />
          <Match idRef="Keywords_lithuania_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8f9b6-501">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="8f9b6-501">Keywords</span></span>

<span data-ttu-id="8f9b6-502">| |</span><span class="sxs-lookup"><span data-stu-id="8f9b6-502"></span></span>
|<span data-ttu-id="8f9b6-503">**Keywords_lithuania_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="8f9b6-503">**Keywords_lithuania_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="8f9b6-504">DL</span><span class="sxs-lookup"><span data-stu-id="8f9b6-504">dl#</span></span>  <br/> <span data-ttu-id="8f9b6-505">driver license</span><span class="sxs-lookup"><span data-stu-id="8f9b6-505">driver license</span></span>  <br/> <span data-ttu-id="8f9b6-506">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="8f9b6-506">driver license number</span></span>  <br/> <span data-ttu-id="8f9b6-507">patente di guida</span><span class="sxs-lookup"><span data-stu-id="8f9b6-507">driver licence</span></span>  <br/> <span data-ttu-id="8f9b6-508">driver Lic.</span><span class="sxs-lookup"><span data-stu-id="8f9b6-508">drivers lic.</span></span>  <br/> <span data-ttu-id="8f9b6-509">drivers license</span><span class="sxs-lookup"><span data-stu-id="8f9b6-509">drivers license</span></span>  <br/> <span data-ttu-id="8f9b6-510">drivers licence</span><span class="sxs-lookup"><span data-stu-id="8f9b6-510">drivers licence</span></span>  <br/> <span data-ttu-id="8f9b6-511">driver's license</span><span class="sxs-lookup"><span data-stu-id="8f9b6-511">driver's license</span></span>  <br/> <span data-ttu-id="8f9b6-512">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="8f9b6-512">driver's license number</span></span>  <br/> <span data-ttu-id="8f9b6-513">numero di patente del conducente</span><span class="sxs-lookup"><span data-stu-id="8f9b6-513">driver's licence number</span></span>  <br/> <span data-ttu-id="8f9b6-514">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="8f9b6-514">driving license number</span></span>  <br/> <span data-ttu-id="8f9b6-515">dlno #</span><span class="sxs-lookup"><span data-stu-id="8f9b6-515">dlno#</span></span>  <br/> <span data-ttu-id="8f9b6-516">vairuotojo pažymėjimas</span><span class="sxs-lookup"><span data-stu-id="8f9b6-516">vairuotojo pažymėjimas</span></span>  <br/> |
   
## <a name="luxemburg"></a><span data-ttu-id="8f9b6-517">Lussemburgo</span><span class="sxs-lookup"><span data-stu-id="8f9b6-517">Luxemburg</span></span>

### <a name="format"></a><span data-ttu-id="8f9b6-518">Formato</span><span class="sxs-lookup"><span data-stu-id="8f9b6-518">Format</span></span>

<span data-ttu-id="8f9b6-519">Sei cifre senza spazi e delimitatori</span><span class="sxs-lookup"><span data-stu-id="8f9b6-519">Six digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="8f9b6-520">Modello</span><span class="sxs-lookup"><span data-stu-id="8f9b6-520">Pattern</span></span>

 <span data-ttu-id="8f9b6-521">Sei cifre</span><span class="sxs-lookup"><span data-stu-id="8f9b6-521">Six digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="8f9b6-522">Checksum</span><span class="sxs-lookup"><span data-stu-id="8f9b6-522">Checksum</span></span>

<span data-ttu-id="8f9b6-523">No</span><span class="sxs-lookup"><span data-stu-id="8f9b6-523">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="8f9b6-524">Definizione</span><span class="sxs-lookup"><span data-stu-id="8f9b6-524">Definition</span></span>

<span data-ttu-id="8f9b6-525">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="8f9b6-525">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="8f9b6-526">L'espressione `Regex_luxemburg_eu_driver's_license_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="8f9b6-526">The regular expression  `Regex_luxemburg_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="8f9b6-527">Viene trovata una `Keywords_luxemburg_eu_driver's_license_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="8f9b6-527">A keyword from  `Keywords_luxemburg_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_luxemburg_eu_driver's_license_number" />
          <Match idRef="Keywords_luxemburg_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8f9b6-528">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="8f9b6-528">Keywords</span></span>

<span data-ttu-id="8f9b6-529">| |</span><span class="sxs-lookup"><span data-stu-id="8f9b6-529"></span></span>
|<span data-ttu-id="8f9b6-530">**Keywords_luxemburg_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="8f9b6-530">**Keywords_luxemburg_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="8f9b6-531">DL</span><span class="sxs-lookup"><span data-stu-id="8f9b6-531">dl#</span></span>  <br/> <span data-ttu-id="8f9b6-532">driver license</span><span class="sxs-lookup"><span data-stu-id="8f9b6-532">driver license</span></span>  <br/> <span data-ttu-id="8f9b6-533">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="8f9b6-533">driver license number</span></span>  <br/> <span data-ttu-id="8f9b6-534">patente di guida</span><span class="sxs-lookup"><span data-stu-id="8f9b6-534">driver licence</span></span>  <br/> <span data-ttu-id="8f9b6-535">driver Lic.</span><span class="sxs-lookup"><span data-stu-id="8f9b6-535">drivers lic.</span></span>  <br/> <span data-ttu-id="8f9b6-536">drivers license</span><span class="sxs-lookup"><span data-stu-id="8f9b6-536">drivers license</span></span>  <br/> <span data-ttu-id="8f9b6-537">drivers licence</span><span class="sxs-lookup"><span data-stu-id="8f9b6-537">drivers licence</span></span>  <br/> <span data-ttu-id="8f9b6-538">driver's license</span><span class="sxs-lookup"><span data-stu-id="8f9b6-538">driver's license</span></span>  <br/> <span data-ttu-id="8f9b6-539">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="8f9b6-539">driver's license number</span></span>  <br/> <span data-ttu-id="8f9b6-540">numero di patente del conducente</span><span class="sxs-lookup"><span data-stu-id="8f9b6-540">driver's licence number</span></span>  <br/> <span data-ttu-id="8f9b6-541">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="8f9b6-541">driving license number</span></span>  <br/> <span data-ttu-id="8f9b6-542">dlno #</span><span class="sxs-lookup"><span data-stu-id="8f9b6-542">dlno#</span></span>  <br/> <span data-ttu-id="8f9b6-543">fahrerlaubnis</span><span class="sxs-lookup"><span data-stu-id="8f9b6-543">fahrerlaubnis</span></span>  <br/> |
   
## <a name="malta"></a><span data-ttu-id="8f9b6-544">Malta</span><span class="sxs-lookup"><span data-stu-id="8f9b6-544">Malta</span></span>

### <a name="format"></a><span data-ttu-id="8f9b6-545">Formato</span><span class="sxs-lookup"><span data-stu-id="8f9b6-545">Format</span></span>

<span data-ttu-id="8f9b6-546">Combinazione di due caratteri e di sei cifre nel modello specificato</span><span class="sxs-lookup"><span data-stu-id="8f9b6-546">Combination of two characters and six digits in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="8f9b6-547">Modello</span><span class="sxs-lookup"><span data-stu-id="8f9b6-547">Pattern</span></span>

<span data-ttu-id="8f9b6-548">Combinazione di due caratteri e di sei cifre:</span><span class="sxs-lookup"><span data-stu-id="8f9b6-548">Combination of two characters and six digits:</span></span>
  
- <span data-ttu-id="8f9b6-549">Due caratteri (cifre o lettere, non con distinzione tra maiuscole e minuscole)</span><span class="sxs-lookup"><span data-stu-id="8f9b6-549">Two characters (digits or letters, not case-sensitive)</span></span>
    
- <span data-ttu-id="8f9b6-550">Uno spazio (facoltativo)</span><span class="sxs-lookup"><span data-stu-id="8f9b6-550">A space (optional)</span></span>
    
- <span data-ttu-id="8f9b6-551">Tre cifre</span><span class="sxs-lookup"><span data-stu-id="8f9b6-551">Three digits</span></span>
    
- <span data-ttu-id="8f9b6-552">Uno spazio (facoltativo)</span><span class="sxs-lookup"><span data-stu-id="8f9b6-552">A space (optional)</span></span>
    
- <span data-ttu-id="8f9b6-553">Tre cifre</span><span class="sxs-lookup"><span data-stu-id="8f9b6-553">Three digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="8f9b6-554">Checksum</span><span class="sxs-lookup"><span data-stu-id="8f9b6-554">Checksum</span></span>

<span data-ttu-id="8f9b6-555">No</span><span class="sxs-lookup"><span data-stu-id="8f9b6-555">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="8f9b6-556">Definizione</span><span class="sxs-lookup"><span data-stu-id="8f9b6-556">Definition</span></span>

<span data-ttu-id="8f9b6-557">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="8f9b6-557">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="8f9b6-558">L'espressione `Regex_malta_eu_driver's_license_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="8f9b6-558">The regular expression  `Regex_malta_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="8f9b6-559">Viene trovata una `Keywords_malta_eu_driver's_license_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="8f9b6-559">A keyword from  `Keywords_malta_eu_driver's_license_number` is found.</span></span> 
    
```
<!-- EU Driver's License Number -->
 <Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_malta_eu_driver's_license_number" />
          <Match idRef="Keywords_malta_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8f9b6-560">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="8f9b6-560">Keywords</span></span>

<span data-ttu-id="8f9b6-561">| |</span><span class="sxs-lookup"><span data-stu-id="8f9b6-561"></span></span>
|<span data-ttu-id="8f9b6-562">**Keywords_malta_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="8f9b6-562">**Keywords_malta_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="8f9b6-563">DL</span><span class="sxs-lookup"><span data-stu-id="8f9b6-563">dl#</span></span>  <br/> <span data-ttu-id="8f9b6-564">driver license</span><span class="sxs-lookup"><span data-stu-id="8f9b6-564">driver license</span></span>  <br/> <span data-ttu-id="8f9b6-565">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="8f9b6-565">driver license number</span></span>  <br/> <span data-ttu-id="8f9b6-566">patente di guida</span><span class="sxs-lookup"><span data-stu-id="8f9b6-566">driver licence</span></span>  <br/> <span data-ttu-id="8f9b6-567">driver Lic.</span><span class="sxs-lookup"><span data-stu-id="8f9b6-567">drivers lic.</span></span>  <br/> <span data-ttu-id="8f9b6-568">drivers license</span><span class="sxs-lookup"><span data-stu-id="8f9b6-568">drivers license</span></span>  <br/> <span data-ttu-id="8f9b6-569">drivers licence</span><span class="sxs-lookup"><span data-stu-id="8f9b6-569">drivers licence</span></span>  <br/> <span data-ttu-id="8f9b6-570">driver's license</span><span class="sxs-lookup"><span data-stu-id="8f9b6-570">driver's license</span></span>  <br/> <span data-ttu-id="8f9b6-571">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="8f9b6-571">driver's license number</span></span>  <br/> <span data-ttu-id="8f9b6-572">numero di patente del conducente</span><span class="sxs-lookup"><span data-stu-id="8f9b6-572">driver's licence number</span></span>  <br/> <span data-ttu-id="8f9b6-573">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="8f9b6-573">driving license number</span></span>  <br/> <span data-ttu-id="8f9b6-574">dlno #</span><span class="sxs-lookup"><span data-stu-id="8f9b6-574">dlno#</span></span>  <br/> <span data-ttu-id="8f9b6-575">Liċenzja TAS-sewqan</span><span class="sxs-lookup"><span data-stu-id="8f9b6-575">liċenzja tas-sewqan</span></span>  <br/> |
   
## <a name="netherlands"></a><span data-ttu-id="8f9b6-576">Paesi Bassi</span><span class="sxs-lookup"><span data-stu-id="8f9b6-576">Netherlands</span></span>

### <a name="format"></a><span data-ttu-id="8f9b6-577">Formato</span><span class="sxs-lookup"><span data-stu-id="8f9b6-577">Format</span></span>

<span data-ttu-id="8f9b6-578">10 cifre senza spazi e delimitatori</span><span class="sxs-lookup"><span data-stu-id="8f9b6-578">10 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="8f9b6-579">Modello</span><span class="sxs-lookup"><span data-stu-id="8f9b6-579">Pattern</span></span>

<span data-ttu-id="8f9b6-580">10 cifre</span><span class="sxs-lookup"><span data-stu-id="8f9b6-580">10 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="8f9b6-581">Checksum</span><span class="sxs-lookup"><span data-stu-id="8f9b6-581">Checksum</span></span>

<span data-ttu-id="8f9b6-582">No</span><span class="sxs-lookup"><span data-stu-id="8f9b6-582">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="8f9b6-583">Definizione</span><span class="sxs-lookup"><span data-stu-id="8f9b6-583">Definition</span></span>

<span data-ttu-id="8f9b6-584">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="8f9b6-584">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="8f9b6-585">L'espressione `Regex_netherlands_eu_driver's_license_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="8f9b6-585">The regular expression  `Regex_netherlands_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="8f9b6-586">Viene trovata una `Keywords_netherlands_eu_driver's_license_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="8f9b6-586">A keyword from  `Keywords_netherlands_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_netherlands_eu_driver's_license_number" />
          <Match idRef="Keywords_netherlands_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8f9b6-587">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="8f9b6-587">Keywords</span></span>

<span data-ttu-id="8f9b6-588">| |</span><span class="sxs-lookup"><span data-stu-id="8f9b6-588"></span></span>
|<span data-ttu-id="8f9b6-589">**Keywords_netherlands_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="8f9b6-589">**Keywords_netherlands_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="8f9b6-590">DL</span><span class="sxs-lookup"><span data-stu-id="8f9b6-590">dl#</span></span>  <br/> <span data-ttu-id="8f9b6-591">driver license</span><span class="sxs-lookup"><span data-stu-id="8f9b6-591">driver license</span></span>  <br/> <span data-ttu-id="8f9b6-592">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="8f9b6-592">driver license number</span></span>  <br/> <span data-ttu-id="8f9b6-593">patente di guida</span><span class="sxs-lookup"><span data-stu-id="8f9b6-593">driver licence</span></span>  <br/> <span data-ttu-id="8f9b6-594">driver Lic.</span><span class="sxs-lookup"><span data-stu-id="8f9b6-594">drivers lic.</span></span>  <br/> <span data-ttu-id="8f9b6-595">drivers license</span><span class="sxs-lookup"><span data-stu-id="8f9b6-595">drivers license</span></span>  <br/> <span data-ttu-id="8f9b6-596">drivers licence</span><span class="sxs-lookup"><span data-stu-id="8f9b6-596">drivers licence</span></span>  <br/> <span data-ttu-id="8f9b6-597">driver's license</span><span class="sxs-lookup"><span data-stu-id="8f9b6-597">driver's license</span></span>  <br/> <span data-ttu-id="8f9b6-598">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="8f9b6-598">driver's license number</span></span>  <br/> <span data-ttu-id="8f9b6-599">numero di patente del conducente</span><span class="sxs-lookup"><span data-stu-id="8f9b6-599">driver's licence number</span></span>  <br/> <span data-ttu-id="8f9b6-600">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="8f9b6-600">driving license number</span></span>  <br/> <span data-ttu-id="8f9b6-601">dlno #</span><span class="sxs-lookup"><span data-stu-id="8f9b6-601">dlno#</span></span>  <br/> <span data-ttu-id="8f9b6-602">permis de conduire</span><span class="sxs-lookup"><span data-stu-id="8f9b6-602">permis de conduire</span></span>  <br/> <span data-ttu-id="8f9b6-603">Rijbewijs</span><span class="sxs-lookup"><span data-stu-id="8f9b6-603">rijbewijs</span></span>  <br/> <span data-ttu-id="8f9b6-604">rijbewijsnummer</span><span class="sxs-lookup"><span data-stu-id="8f9b6-604">rijbewijsnummer</span></span>  <br/> |
   
## <a name="poland"></a><span data-ttu-id="8f9b6-605">Polonia</span><span class="sxs-lookup"><span data-stu-id="8f9b6-605">Poland</span></span>

### <a name="format"></a><span data-ttu-id="8f9b6-606">Formato</span><span class="sxs-lookup"><span data-stu-id="8f9b6-606">Format</span></span>

<span data-ttu-id="8f9b6-607">14 cifre contenenti 2 barre</span><span class="sxs-lookup"><span data-stu-id="8f9b6-607">14 digits containing 2 forward slashes</span></span>
  
### <a name="pattern"></a><span data-ttu-id="8f9b6-608">Modello</span><span class="sxs-lookup"><span data-stu-id="8f9b6-608">Pattern</span></span>

<span data-ttu-id="8f9b6-609">14 cifre e 2 barre:</span><span class="sxs-lookup"><span data-stu-id="8f9b6-609">14 digits and 2 forward slashes:</span></span>
  
-  <span data-ttu-id="8f9b6-610">Cinque cifre</span><span class="sxs-lookup"><span data-stu-id="8f9b6-610">Five digits</span></span> 
    
- <span data-ttu-id="8f9b6-611">Una barra</span><span class="sxs-lookup"><span data-stu-id="8f9b6-611">A forward slash</span></span>
    
- <span data-ttu-id="8f9b6-612">Due cifre</span><span class="sxs-lookup"><span data-stu-id="8f9b6-612">Two digits</span></span>
    
- <span data-ttu-id="8f9b6-613">Una barra</span><span class="sxs-lookup"><span data-stu-id="8f9b6-613">A forward slash</span></span>
    
- <span data-ttu-id="8f9b6-614">Sette cifre</span><span class="sxs-lookup"><span data-stu-id="8f9b6-614">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="8f9b6-615">Checksum</span><span class="sxs-lookup"><span data-stu-id="8f9b6-615">Checksum</span></span>

<span data-ttu-id="8f9b6-616">No</span><span class="sxs-lookup"><span data-stu-id="8f9b6-616">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="8f9b6-617">Definizione</span><span class="sxs-lookup"><span data-stu-id="8f9b6-617">Definition</span></span>

<span data-ttu-id="8f9b6-618">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="8f9b6-618">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="8f9b6-619">L'espressione `Regex_poland_eu_driver's_license_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="8f9b6-619">The regular expression  `Regex_poland_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="8f9b6-620">Viene trovata una `Keywords_poland_eu_driver's_license_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="8f9b6-620">A keyword from  `Keywords_poland_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_poland_eu_driver's_license_number" />
          <Match idRef="Keywords_poland_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8f9b6-621">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="8f9b6-621">Keywords</span></span>

<span data-ttu-id="8f9b6-622">| |</span><span class="sxs-lookup"><span data-stu-id="8f9b6-622"></span></span>
|<span data-ttu-id="8f9b6-623">**Keywords_poland_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="8f9b6-623">**Keywords_poland_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="8f9b6-624">DL</span><span class="sxs-lookup"><span data-stu-id="8f9b6-624">dl#</span></span>  <br/> <span data-ttu-id="8f9b6-625">driver license</span><span class="sxs-lookup"><span data-stu-id="8f9b6-625">driver license</span></span>  <br/> <span data-ttu-id="8f9b6-626">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="8f9b6-626">driver license number</span></span>  <br/> <span data-ttu-id="8f9b6-627">patente di guida</span><span class="sxs-lookup"><span data-stu-id="8f9b6-627">driver licence</span></span>  <br/> <span data-ttu-id="8f9b6-628">driver Lic.</span><span class="sxs-lookup"><span data-stu-id="8f9b6-628">drivers lic.</span></span>  <br/> <span data-ttu-id="8f9b6-629">drivers license</span><span class="sxs-lookup"><span data-stu-id="8f9b6-629">drivers license</span></span>  <br/> <span data-ttu-id="8f9b6-630">drivers licence</span><span class="sxs-lookup"><span data-stu-id="8f9b6-630">drivers licence</span></span>  <br/> <span data-ttu-id="8f9b6-631">driver's license</span><span class="sxs-lookup"><span data-stu-id="8f9b6-631">driver's license</span></span>  <br/> <span data-ttu-id="8f9b6-632">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="8f9b6-632">driver's license number</span></span>  <br/> <span data-ttu-id="8f9b6-633">numero di patente del conducente</span><span class="sxs-lookup"><span data-stu-id="8f9b6-633">driver's licence number</span></span>  <br/> <span data-ttu-id="8f9b6-634">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="8f9b6-634">driving license number</span></span>  <br/> <span data-ttu-id="8f9b6-635">dlno #</span><span class="sxs-lookup"><span data-stu-id="8f9b6-635">dlno#</span></span>  <br/> <span data-ttu-id="8f9b6-636">prawo jazdy</span><span class="sxs-lookup"><span data-stu-id="8f9b6-636">prawo jazdy</span></span>  <br/> |
   
## <a name="portugal"></a><span data-ttu-id="8f9b6-637">Portogallo</span><span class="sxs-lookup"><span data-stu-id="8f9b6-637">Portugal</span></span>

### <a name="format"></a><span data-ttu-id="8f9b6-638">Formato</span><span class="sxs-lookup"><span data-stu-id="8f9b6-638">Format</span></span>

<span data-ttu-id="8f9b6-639">Due lettere seguite da un numero di sette numeri nel modello specificato</span><span class="sxs-lookup"><span data-stu-id="8f9b6-639">Two letters followed by a seven numbers in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="8f9b6-640">Modello</span><span class="sxs-lookup"><span data-stu-id="8f9b6-640">Pattern</span></span>

<span data-ttu-id="8f9b6-641">Due lettere seguite da sette numeri con caratteri speciali:</span><span class="sxs-lookup"><span data-stu-id="8f9b6-641">Two letters followed by seven numbers with special characters:</span></span>
  
-  <span data-ttu-id="8f9b6-642">Due lettere (senza distinzione tra maiuscole e minuscole)</span><span class="sxs-lookup"><span data-stu-id="8f9b6-642">Two letters (not case-sensitive)</span></span> 
    
- <span data-ttu-id="8f9b6-643">Una lineetta</span><span class="sxs-lookup"><span data-stu-id="8f9b6-643">A hyphen</span></span>
    
- <span data-ttu-id="8f9b6-644">Sei cifre</span><span class="sxs-lookup"><span data-stu-id="8f9b6-644">Six digits</span></span>
    
- <span data-ttu-id="8f9b6-645">Uno spazio</span><span class="sxs-lookup"><span data-stu-id="8f9b6-645">A space</span></span>
    
- <span data-ttu-id="8f9b6-646">Una cifra</span><span class="sxs-lookup"><span data-stu-id="8f9b6-646">One digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="8f9b6-647">Checksum</span><span class="sxs-lookup"><span data-stu-id="8f9b6-647">Checksum</span></span>

<span data-ttu-id="8f9b6-648">No</span><span class="sxs-lookup"><span data-stu-id="8f9b6-648">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="8f9b6-649">Definizione</span><span class="sxs-lookup"><span data-stu-id="8f9b6-649">Definition</span></span>

<span data-ttu-id="8f9b6-650">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="8f9b6-650">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="8f9b6-651">L'espressione `Regex_portugal_eu_driver's_license_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="8f9b6-651">The regular expression  `Regex_portugal_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="8f9b6-652">Viene trovata una `Keywords_portugal_eu_driver's_license_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="8f9b6-652">A keyword from  `Keywords_portugal_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_portugal_eu_driver's_license_number" />
          <Match idRef="Keywords_portugal_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8f9b6-653">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="8f9b6-653">Keywords</span></span>

<span data-ttu-id="8f9b6-654">| |</span><span class="sxs-lookup"><span data-stu-id="8f9b6-654"></span></span>
|<span data-ttu-id="8f9b6-655">**Keywords_portugal_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="8f9b6-655">**Keywords_portugal_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="8f9b6-656">DL</span><span class="sxs-lookup"><span data-stu-id="8f9b6-656">dl#</span></span>  <br/> <span data-ttu-id="8f9b6-657">driver license</span><span class="sxs-lookup"><span data-stu-id="8f9b6-657">driver license</span></span>  <br/> <span data-ttu-id="8f9b6-658">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="8f9b6-658">driver license number</span></span>  <br/> <span data-ttu-id="8f9b6-659">patente di guida</span><span class="sxs-lookup"><span data-stu-id="8f9b6-659">driver licence</span></span>  <br/> <span data-ttu-id="8f9b6-660">driver Lic.</span><span class="sxs-lookup"><span data-stu-id="8f9b6-660">drivers lic.</span></span>  <br/> <span data-ttu-id="8f9b6-661">drivers license</span><span class="sxs-lookup"><span data-stu-id="8f9b6-661">drivers license</span></span>  <br/> <span data-ttu-id="8f9b6-662">drivers licence</span><span class="sxs-lookup"><span data-stu-id="8f9b6-662">drivers licence</span></span>  <br/> <span data-ttu-id="8f9b6-663">driver's license</span><span class="sxs-lookup"><span data-stu-id="8f9b6-663">driver's license</span></span>  <br/> <span data-ttu-id="8f9b6-664">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="8f9b6-664">driver's license number</span></span>  <br/> <span data-ttu-id="8f9b6-665">numero di patente del conducente</span><span class="sxs-lookup"><span data-stu-id="8f9b6-665">driver's licence number</span></span>  <br/> <span data-ttu-id="8f9b6-666">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="8f9b6-666">driving license number</span></span>  <br/> <span data-ttu-id="8f9b6-667">dlno #</span><span class="sxs-lookup"><span data-stu-id="8f9b6-667">dlno#</span></span>  <br/> <span data-ttu-id="8f9b6-668">carteira de motorista</span><span class="sxs-lookup"><span data-stu-id="8f9b6-668">carteira de motorista</span></span>  <br/> |
   
## <a name="romania"></a><span data-ttu-id="8f9b6-669">Romania</span><span class="sxs-lookup"><span data-stu-id="8f9b6-669">Romania</span></span>

### <a name="format"></a><span data-ttu-id="8f9b6-670">Formato</span><span class="sxs-lookup"><span data-stu-id="8f9b6-670">Format</span></span>

<span data-ttu-id="8f9b6-671">Un carattere seguito da otto cifre</span><span class="sxs-lookup"><span data-stu-id="8f9b6-671">One character followed by eight digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="8f9b6-672">Modello</span><span class="sxs-lookup"><span data-stu-id="8f9b6-672">Pattern</span></span>

<span data-ttu-id="8f9b6-673">Un carattere seguito da otto cifre:</span><span class="sxs-lookup"><span data-stu-id="8f9b6-673">One character followed by eight digits:</span></span>
  
-  <span data-ttu-id="8f9b6-674">Una lettera (senza distinzione tra maiuscole e minuscole) o cifra</span><span class="sxs-lookup"><span data-stu-id="8f9b6-674">One letter (not case-sensitive) or digit</span></span> 
    
- <span data-ttu-id="8f9b6-675">Otto cifre</span><span class="sxs-lookup"><span data-stu-id="8f9b6-675">Eight digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="8f9b6-676">Checksum</span><span class="sxs-lookup"><span data-stu-id="8f9b6-676">Checksum</span></span>

<span data-ttu-id="8f9b6-677">No</span><span class="sxs-lookup"><span data-stu-id="8f9b6-677">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="8f9b6-678">Definizione</span><span class="sxs-lookup"><span data-stu-id="8f9b6-678">Definition</span></span>

<span data-ttu-id="8f9b6-679">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="8f9b6-679">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="8f9b6-680">L'espressione `Regex_romania_eu_driver's_license_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="8f9b6-680">The regular expression  `Regex_romania_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="8f9b6-681">Viene trovata una `Keywords_romania_eu_driver's_license_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="8f9b6-681">A keyword from  `Keywords_romania_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_romania_eu_driver's_license_number" />
          <Match idRef="Keywords_romania_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8f9b6-682">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="8f9b6-682">Keywords</span></span>

<span data-ttu-id="8f9b6-683">| |</span><span class="sxs-lookup"><span data-stu-id="8f9b6-683"></span></span>
|<span data-ttu-id="8f9b6-684">**Keywords_romania_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="8f9b6-684">**Keywords_romania_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="8f9b6-685">DL</span><span class="sxs-lookup"><span data-stu-id="8f9b6-685">dl#</span></span>  <br/> <span data-ttu-id="8f9b6-686">driver license</span><span class="sxs-lookup"><span data-stu-id="8f9b6-686">driver license</span></span>  <br/> <span data-ttu-id="8f9b6-687">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="8f9b6-687">driver license number</span></span>  <br/> <span data-ttu-id="8f9b6-688">patente di guida</span><span class="sxs-lookup"><span data-stu-id="8f9b6-688">driver licence</span></span>  <br/> <span data-ttu-id="8f9b6-689">driver Lic.</span><span class="sxs-lookup"><span data-stu-id="8f9b6-689">drivers lic.</span></span>  <br/> <span data-ttu-id="8f9b6-690">drivers license</span><span class="sxs-lookup"><span data-stu-id="8f9b6-690">drivers license</span></span>  <br/> <span data-ttu-id="8f9b6-691">drivers licence</span><span class="sxs-lookup"><span data-stu-id="8f9b6-691">drivers licence</span></span>  <br/> <span data-ttu-id="8f9b6-692">driver's license</span><span class="sxs-lookup"><span data-stu-id="8f9b6-692">driver's license</span></span>  <br/> <span data-ttu-id="8f9b6-693">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="8f9b6-693">driver's license number</span></span>  <br/> <span data-ttu-id="8f9b6-694">numero di patente del conducente</span><span class="sxs-lookup"><span data-stu-id="8f9b6-694">driver's licence number</span></span>  <br/> <span data-ttu-id="8f9b6-695">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="8f9b6-695">driving license number</span></span>  <br/> <span data-ttu-id="8f9b6-696">dlno #</span><span class="sxs-lookup"><span data-stu-id="8f9b6-696">dlno#</span></span>  <br/> <span data-ttu-id="8f9b6-697">Permis de conducere</span><span class="sxs-lookup"><span data-stu-id="8f9b6-697">permis de conducere</span></span>  <br/> |
   
## <a name="slovakia"></a><span data-ttu-id="8f9b6-698">Slovacchia</span><span class="sxs-lookup"><span data-stu-id="8f9b6-698">Slovakia</span></span>

### <a name="format"></a><span data-ttu-id="8f9b6-699">Formato</span><span class="sxs-lookup"><span data-stu-id="8f9b6-699">Format</span></span>

<span data-ttu-id="8f9b6-700">Un carattere seguito da sette cifre</span><span class="sxs-lookup"><span data-stu-id="8f9b6-700">One character followed by seven digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="8f9b6-701">Modello</span><span class="sxs-lookup"><span data-stu-id="8f9b6-701">Pattern</span></span>

<span data-ttu-id="8f9b6-702">Un carattere seguito da sette cifre</span><span class="sxs-lookup"><span data-stu-id="8f9b6-702">One character followed by seven digits</span></span>
  
- <span data-ttu-id="8f9b6-703">Una lettera (senza distinzione tra maiuscole e minuscole) o cifra</span><span class="sxs-lookup"><span data-stu-id="8f9b6-703">One letter (not case-sensitive) or digit</span></span>
    
-  <span data-ttu-id="8f9b6-704">Sette cifre</span><span class="sxs-lookup"><span data-stu-id="8f9b6-704">Seven digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="8f9b6-705">Checksum</span><span class="sxs-lookup"><span data-stu-id="8f9b6-705">Checksum</span></span>

<span data-ttu-id="8f9b6-706">No</span><span class="sxs-lookup"><span data-stu-id="8f9b6-706">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="8f9b6-707">Definizione</span><span class="sxs-lookup"><span data-stu-id="8f9b6-707">Definition</span></span>

<span data-ttu-id="8f9b6-708">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="8f9b6-708">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="8f9b6-709">L'espressione `Regex_slovakia_eu_driver's_license_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="8f9b6-709">The regular expression  `Regex_slovakia_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="8f9b6-710">Viene trovata una `Keywords_slovakia_eu_driver's_license_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="8f9b6-710">A keyword from  `Keywords_slovakia_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovaknia_eu_driver's_license_number" />
          <Match idRef="Keywords_slovakia_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8f9b6-711">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="8f9b6-711">Keywords</span></span>

<span data-ttu-id="8f9b6-712">| |</span><span class="sxs-lookup"><span data-stu-id="8f9b6-712"></span></span>
|<span data-ttu-id="8f9b6-713">**Keywords_slovakia_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="8f9b6-713">**Keywords_slovakia_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="8f9b6-714">DL</span><span class="sxs-lookup"><span data-stu-id="8f9b6-714">dl#</span></span>  <br/> <span data-ttu-id="8f9b6-715">driver license</span><span class="sxs-lookup"><span data-stu-id="8f9b6-715">driver license</span></span>  <br/> <span data-ttu-id="8f9b6-716">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="8f9b6-716">driver license number</span></span>  <br/> <span data-ttu-id="8f9b6-717">patente di guida</span><span class="sxs-lookup"><span data-stu-id="8f9b6-717">driver licence</span></span>  <br/> <span data-ttu-id="8f9b6-718">driver Lic.</span><span class="sxs-lookup"><span data-stu-id="8f9b6-718">drivers lic.</span></span>  <br/> <span data-ttu-id="8f9b6-719">drivers license</span><span class="sxs-lookup"><span data-stu-id="8f9b6-719">drivers license</span></span>  <br/> <span data-ttu-id="8f9b6-720">drivers licence</span><span class="sxs-lookup"><span data-stu-id="8f9b6-720">drivers licence</span></span>  <br/> <span data-ttu-id="8f9b6-721">driver's license</span><span class="sxs-lookup"><span data-stu-id="8f9b6-721">driver's license</span></span>  <br/> <span data-ttu-id="8f9b6-722">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="8f9b6-722">driver's license number</span></span>  <br/> <span data-ttu-id="8f9b6-723">numero di patente del conducente</span><span class="sxs-lookup"><span data-stu-id="8f9b6-723">driver's licence number</span></span>  <br/> <span data-ttu-id="8f9b6-724">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="8f9b6-724">driving license number</span></span>  <br/> <span data-ttu-id="8f9b6-725">dlno #</span><span class="sxs-lookup"><span data-stu-id="8f9b6-725">dlno#</span></span>  <br/> <span data-ttu-id="8f9b6-726">vodičský preukaz</span><span class="sxs-lookup"><span data-stu-id="8f9b6-726">vodičský preukaz</span></span>  <br/> |
   
## <a name="slovenia"></a><span data-ttu-id="8f9b6-727">Slovenia</span><span class="sxs-lookup"><span data-stu-id="8f9b6-727">Slovenia</span></span>

### <a name="format"></a><span data-ttu-id="8f9b6-728">Formato</span><span class="sxs-lookup"><span data-stu-id="8f9b6-728">Format</span></span>

<span data-ttu-id="8f9b6-729">Nove cifre senza spazi e delimitatori</span><span class="sxs-lookup"><span data-stu-id="8f9b6-729">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="8f9b6-730">Modello</span><span class="sxs-lookup"><span data-stu-id="8f9b6-730">Pattern</span></span>

<span data-ttu-id="8f9b6-731">9 cifre</span><span class="sxs-lookup"><span data-stu-id="8f9b6-731">Nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="8f9b6-732">Checksum</span><span class="sxs-lookup"><span data-stu-id="8f9b6-732">Checksum</span></span>

<span data-ttu-id="8f9b6-733">No</span><span class="sxs-lookup"><span data-stu-id="8f9b6-733">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="8f9b6-734">Definizione</span><span class="sxs-lookup"><span data-stu-id="8f9b6-734">Definition</span></span>

<span data-ttu-id="8f9b6-735">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="8f9b6-735">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="8f9b6-736">L'espressione `Regex_slovenia_eu_driver's_license_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="8f9b6-736">The regular expression  `Regex_slovenia_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="8f9b6-737">Viene trovata una `Keywords_slovenia_eu_driver's_license_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="8f9b6-737">A keyword from  `Keywords_slovenia_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovenia_eu_driver's_license_number" />
          <Match idRef="Keywords_slovenia_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8f9b6-738">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="8f9b6-738">Keywords</span></span>

<span data-ttu-id="8f9b6-739">| |</span><span class="sxs-lookup"><span data-stu-id="8f9b6-739"></span></span>
|<span data-ttu-id="8f9b6-740">**Keywords_slovenia_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="8f9b6-740">**Keywords_slovenia_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="8f9b6-741">DL</span><span class="sxs-lookup"><span data-stu-id="8f9b6-741">dl#</span></span>  <br/> <span data-ttu-id="8f9b6-742">driver license</span><span class="sxs-lookup"><span data-stu-id="8f9b6-742">driver license</span></span>  <br/> <span data-ttu-id="8f9b6-743">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="8f9b6-743">driver license number</span></span>  <br/> <span data-ttu-id="8f9b6-744">patente di guida</span><span class="sxs-lookup"><span data-stu-id="8f9b6-744">driver licence</span></span>  <br/> <span data-ttu-id="8f9b6-745">driver Lic.</span><span class="sxs-lookup"><span data-stu-id="8f9b6-745">drivers lic.</span></span>  <br/> <span data-ttu-id="8f9b6-746">drivers license</span><span class="sxs-lookup"><span data-stu-id="8f9b6-746">drivers license</span></span>  <br/> <span data-ttu-id="8f9b6-747">drivers licence</span><span class="sxs-lookup"><span data-stu-id="8f9b6-747">drivers licence</span></span>  <br/> <span data-ttu-id="8f9b6-748">driver's license</span><span class="sxs-lookup"><span data-stu-id="8f9b6-748">driver's license</span></span>  <br/> <span data-ttu-id="8f9b6-749">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="8f9b6-749">driver's license number</span></span>  <br/> <span data-ttu-id="8f9b6-750">numero di patente del conducente</span><span class="sxs-lookup"><span data-stu-id="8f9b6-750">driver's licence number</span></span>  <br/> <span data-ttu-id="8f9b6-751">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="8f9b6-751">driving license number</span></span>  <br/> <span data-ttu-id="8f9b6-752">dlno #</span><span class="sxs-lookup"><span data-stu-id="8f9b6-752">dlno#</span></span>  <br/> <span data-ttu-id="8f9b6-753">vozniško dovoljenje</span><span class="sxs-lookup"><span data-stu-id="8f9b6-753">vozniško dovoljenje</span></span>  <br/> |
   
## <a name="spain"></a><span data-ttu-id="8f9b6-754">Spagna</span><span class="sxs-lookup"><span data-stu-id="8f9b6-754">Spain</span></span>

### <a name="format"></a><span data-ttu-id="8f9b6-755">Formato</span><span class="sxs-lookup"><span data-stu-id="8f9b6-755">Format</span></span>

<span data-ttu-id="8f9b6-756">Otto cifre seguite da un carattere</span><span class="sxs-lookup"><span data-stu-id="8f9b6-756">Eight digits followed by one character</span></span>
  
### <a name="pattern"></a><span data-ttu-id="8f9b6-757">Modello</span><span class="sxs-lookup"><span data-stu-id="8f9b6-757">Pattern</span></span>

<span data-ttu-id="8f9b6-758">Otto cifre seguite da un carattere:</span><span class="sxs-lookup"><span data-stu-id="8f9b6-758">Eight digits followed by one character:</span></span>
  
-  <span data-ttu-id="8f9b6-759">Otto cifre</span><span class="sxs-lookup"><span data-stu-id="8f9b6-759">Eight digits</span></span> 
    
- <span data-ttu-id="8f9b6-760">Una cifra o una lettera (senza distinzione tra maiuscole e minuscole)</span><span class="sxs-lookup"><span data-stu-id="8f9b6-760">One digit or letter (not case-sensitive)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="8f9b6-761">Checksum</span><span class="sxs-lookup"><span data-stu-id="8f9b6-761">Checksum</span></span>

<span data-ttu-id="8f9b6-762">Sì</span><span class="sxs-lookup"><span data-stu-id="8f9b6-762">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="8f9b6-763">Definizione</span><span class="sxs-lookup"><span data-stu-id="8f9b6-763">Definition</span></span>

<span data-ttu-id="8f9b6-764">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="8f9b6-764">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="8f9b6-765">La funzione `Func_spain_eu_driver's_license_number` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="8f9b6-765">The function  `Func_spain_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="8f9b6-766">Viene trovata una `Keywords_spain_eu_driver's_license_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="8f9b6-766">A keyword from  `Keywords_spain_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_spain_eu_driver's_license_number" />
          <Match idRef="Keywords_spain_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8f9b6-767">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="8f9b6-767">Keywords</span></span>

<span data-ttu-id="8f9b6-768">| |</span><span class="sxs-lookup"><span data-stu-id="8f9b6-768"></span></span>
|<span data-ttu-id="8f9b6-769">**Keywords_spain_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="8f9b6-769">**Keywords_spain_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="8f9b6-770">dlno #</span><span class="sxs-lookup"><span data-stu-id="8f9b6-770">dlno#</span></span>  <br/> <span data-ttu-id="8f9b6-771">DL</span><span class="sxs-lookup"><span data-stu-id="8f9b6-771">dl#</span></span>  <br/> <span data-ttu-id="8f9b6-772">driver Lic.</span><span class="sxs-lookup"><span data-stu-id="8f9b6-772">drivers lic.</span></span>  <br/> <span data-ttu-id="8f9b6-773">patente di guida</span><span class="sxs-lookup"><span data-stu-id="8f9b6-773">driver licence</span></span>  <br/> <span data-ttu-id="8f9b6-774">driver license</span><span class="sxs-lookup"><span data-stu-id="8f9b6-774">driver license</span></span>  <br/> <span data-ttu-id="8f9b6-775">drivers licence</span><span class="sxs-lookup"><span data-stu-id="8f9b6-775">drivers licence</span></span>  <br/> <span data-ttu-id="8f9b6-776">drivers license</span><span class="sxs-lookup"><span data-stu-id="8f9b6-776">drivers license</span></span>  <br/> <span data-ttu-id="8f9b6-777">driver's licence</span><span class="sxs-lookup"><span data-stu-id="8f9b6-777">driver's licence</span></span>  <br/> <span data-ttu-id="8f9b6-778">driver's license</span><span class="sxs-lookup"><span data-stu-id="8f9b6-778">driver's license</span></span>  <br/> <span data-ttu-id="8f9b6-779">driving licence</span><span class="sxs-lookup"><span data-stu-id="8f9b6-779">driving licence</span></span>  <br/> <span data-ttu-id="8f9b6-780">driving license</span><span class="sxs-lookup"><span data-stu-id="8f9b6-780">driving license</span></span>  <br/> <span data-ttu-id="8f9b6-781">numero di patente del conducente</span><span class="sxs-lookup"><span data-stu-id="8f9b6-781">driver licence number</span></span>  <br/> <span data-ttu-id="8f9b6-782">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="8f9b6-782">driver license number</span></span>  <br/> <span data-ttu-id="8f9b6-783">numero di patente del conducente</span><span class="sxs-lookup"><span data-stu-id="8f9b6-783">drivers licence number</span></span>  <br/> <span data-ttu-id="8f9b6-784">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="8f9b6-784">drivers license number</span></span>  <br/> <span data-ttu-id="8f9b6-785">numero di patente del conducente</span><span class="sxs-lookup"><span data-stu-id="8f9b6-785">driver's licence number</span></span>  <br/> <span data-ttu-id="8f9b6-786">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="8f9b6-786">driver's license number</span></span>  <br/> <span data-ttu-id="8f9b6-787">numero di patente di guida</span><span class="sxs-lookup"><span data-stu-id="8f9b6-787">driving licence number</span></span>  <br/> <span data-ttu-id="8f9b6-788">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="8f9b6-788">driving license number</span></span>  <br/> <span data-ttu-id="8f9b6-789">permesso di guida</span><span class="sxs-lookup"><span data-stu-id="8f9b6-789">driving permit</span></span>  <br/> <span data-ttu-id="8f9b6-790">numero di licenza di guida</span><span class="sxs-lookup"><span data-stu-id="8f9b6-790">driving permit number</span></span>  <br/> <span data-ttu-id="8f9b6-791">Permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="8f9b6-791">permiso de conducción</span></span>  <br/> <span data-ttu-id="8f9b6-792">Permiso conducción</span><span class="sxs-lookup"><span data-stu-id="8f9b6-792">permiso conducción</span></span>  <br/> <span data-ttu-id="8f9b6-793">número licencia conducir</span><span class="sxs-lookup"><span data-stu-id="8f9b6-793">número licencia conducir</span></span>  <br/> <span data-ttu-id="8f9b6-794">número de carnet de conducir</span><span class="sxs-lookup"><span data-stu-id="8f9b6-794">número de carnet de conducir</span></span>  <br/> <span data-ttu-id="8f9b6-795">número carnet conducir</span><span class="sxs-lookup"><span data-stu-id="8f9b6-795">número carnet conducir</span></span>  <br/> <span data-ttu-id="8f9b6-796">licencia conducir</span><span class="sxs-lookup"><span data-stu-id="8f9b6-796">licencia conducir</span></span>  <br/> <span data-ttu-id="8f9b6-797">número de Permiso de conducir</span><span class="sxs-lookup"><span data-stu-id="8f9b6-797">número de permiso de conducir</span></span>  <br/> <span data-ttu-id="8f9b6-798">número de permiso conducir</span><span class="sxs-lookup"><span data-stu-id="8f9b6-798">número de permiso conducir</span></span>  <br/> <span data-ttu-id="8f9b6-799">número permiso conducir</span><span class="sxs-lookup"><span data-stu-id="8f9b6-799">número permiso conducir</span></span>  <br/> <span data-ttu-id="8f9b6-800">Permiso conducir</span><span class="sxs-lookup"><span data-stu-id="8f9b6-800">permiso conducir</span></span>  <br/> <span data-ttu-id="8f9b6-801">licencia de manejo</span><span class="sxs-lookup"><span data-stu-id="8f9b6-801">licencia de manejo</span></span>  <br/> <span data-ttu-id="8f9b6-802">El carnet de conducir</span><span class="sxs-lookup"><span data-stu-id="8f9b6-802">el carnet de conducir</span></span>  <br/> <span data-ttu-id="8f9b6-803">carnet conducir</span><span class="sxs-lookup"><span data-stu-id="8f9b6-803">carnet conducir</span></span>  <br/> |
   
## <a name="sweden"></a><span data-ttu-id="8f9b6-804">Svezia</span><span class="sxs-lookup"><span data-stu-id="8f9b6-804">Sweden</span></span>

### <a name="format"></a><span data-ttu-id="8f9b6-805">Formato</span><span class="sxs-lookup"><span data-stu-id="8f9b6-805">Format</span></span>

<span data-ttu-id="8f9b6-806">Dieci cifre contenenti un segno meno</span><span class="sxs-lookup"><span data-stu-id="8f9b6-806">Ten digits containing a hyphen</span></span>
  
### <a name="pattern"></a><span data-ttu-id="8f9b6-807">Modello</span><span class="sxs-lookup"><span data-stu-id="8f9b6-807">Pattern</span></span>

<span data-ttu-id="8f9b6-808">Dieci cifre contenenti un trattino:</span><span class="sxs-lookup"><span data-stu-id="8f9b6-808">Ten digits containing a hyphen:</span></span>
  
-  <span data-ttu-id="8f9b6-809">Sei cifre</span><span class="sxs-lookup"><span data-stu-id="8f9b6-809">Six digits</span></span> 
    
- <span data-ttu-id="8f9b6-810">Una lineetta</span><span class="sxs-lookup"><span data-stu-id="8f9b6-810">A hyphen</span></span>
    
- <span data-ttu-id="8f9b6-811">Quattro cifre</span><span class="sxs-lookup"><span data-stu-id="8f9b6-811">Four digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="8f9b6-812">Checksum</span><span class="sxs-lookup"><span data-stu-id="8f9b6-812">Checksum</span></span>

<span data-ttu-id="8f9b6-813">No</span><span class="sxs-lookup"><span data-stu-id="8f9b6-813">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="8f9b6-814">Definizione</span><span class="sxs-lookup"><span data-stu-id="8f9b6-814">Definition</span></span>

<span data-ttu-id="8f9b6-815">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="8f9b6-815">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="8f9b6-816">L'espressione `Regex_sweden_eu_driver's_license_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="8f9b6-816">The regular expression  `Regex_sweden_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="8f9b6-817">Viene trovata una `Keywords_sweden_eu_driver's_license_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="8f9b6-817">A keyword from  `Keywords_sweden_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_sweden_eu_driver's_license_number" />
          <Match idRef="Keywords_sweden_eu_driver's_license_number" />
        </Pattern>
</Entity> 
```

### <a name="keywords"></a><span data-ttu-id="8f9b6-818">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="8f9b6-818">Keywords</span></span>

<span data-ttu-id="8f9b6-819">| |</span><span class="sxs-lookup"><span data-stu-id="8f9b6-819"></span></span>
|<span data-ttu-id="8f9b6-820">**Keywords_sweden_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="8f9b6-820">**Keywords_sweden_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="8f9b6-821">DL</span><span class="sxs-lookup"><span data-stu-id="8f9b6-821">dl#</span></span>  <br/> <span data-ttu-id="8f9b6-822">driver license</span><span class="sxs-lookup"><span data-stu-id="8f9b6-822">driver license</span></span>  <br/> <span data-ttu-id="8f9b6-823">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="8f9b6-823">driver license number</span></span>  <br/> <span data-ttu-id="8f9b6-824">patente di guida</span><span class="sxs-lookup"><span data-stu-id="8f9b6-824">driver licence</span></span>  <br/> <span data-ttu-id="8f9b6-825">driver Lic.</span><span class="sxs-lookup"><span data-stu-id="8f9b6-825">drivers lic.</span></span>  <br/> <span data-ttu-id="8f9b6-826">drivers license</span><span class="sxs-lookup"><span data-stu-id="8f9b6-826">drivers license</span></span>  <br/> <span data-ttu-id="8f9b6-827">drivers licence</span><span class="sxs-lookup"><span data-stu-id="8f9b6-827">drivers licence</span></span>  <br/> <span data-ttu-id="8f9b6-828">driver's license</span><span class="sxs-lookup"><span data-stu-id="8f9b6-828">driver's license</span></span>  <br/> <span data-ttu-id="8f9b6-829">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="8f9b6-829">driver's license number</span></span>  <br/> <span data-ttu-id="8f9b6-830">numero di patente del conducente</span><span class="sxs-lookup"><span data-stu-id="8f9b6-830">driver's licence number</span></span>  <br/> <span data-ttu-id="8f9b6-831">numero della patente di guida</span><span class="sxs-lookup"><span data-stu-id="8f9b6-831">driving license number</span></span>  <br/> <span data-ttu-id="8f9b6-832">dlno #</span><span class="sxs-lookup"><span data-stu-id="8f9b6-832">dlno#</span></span>  <br/> <span data-ttu-id="8f9b6-833">körkort</span><span class="sxs-lookup"><span data-stu-id="8f9b6-833">körkort</span></span>  <br/> |
   
## <a name="uk"></a><span data-ttu-id="8f9b6-834">Regno Unito</span><span class="sxs-lookup"><span data-stu-id="8f9b6-834">UK</span></span>

<span data-ttu-id="8f9b6-835">Per informazioni dettagliate, vedere la sezione "Regno Unito</span><span class="sxs-lookup"><span data-stu-id="8f9b6-835">For details, see the section "U.K.</span></span> <span data-ttu-id="8f9b6-836">Numero della patente di guida "in [quello che cercano i tipi di informazioni riservate](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="8f9b6-836">Driver's License Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="8f9b6-837">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8f9b6-837">See also</span></span>

[<span data-ttu-id="8f9b6-838">Cosa individuano le tipologie di informazioni sensibili</span><span class="sxs-lookup"><span data-stu-id="8f9b6-838">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)

