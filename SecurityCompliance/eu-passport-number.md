---
title: Numero di passaporto EU
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 8/16/2018
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
description: In questo argomento viene illustrato l'aspetto di un criterio di prevenzione della perdita di dati (DLP) quando viene rilevato il tipo di informazioni riservate del numero di passaporto dell'Unione europea. Questo tipo di informazioni riservate definisce modelli, parole chiave e altre evidenze diverse per ogni paese.
ms.openlocfilehash: fa3be04dec0f71a2568e046abd6b0af3e20181c5
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/17/2019
ms.locfileid: "34152968"
---
# <a name="eu-passport-number"></a><span data-ttu-id="d2ffb-104">Numero di passaporto EU</span><span class="sxs-lookup"><span data-stu-id="d2ffb-104">EU Passport Number</span></span>

<span data-ttu-id="d2ffb-105">In questo argomento viene illustrato l'aspetto di un criterio di prevenzione della perdita di dati (DLP) quando viene rilevato il tipo di informazioni riservate del numero di passaporto dell'Unione europea.</span><span class="sxs-lookup"><span data-stu-id="d2ffb-105">This topic shows what a data loss prevention (DLP) policy looks for when it detects the EU Passport Number sensitive information type.</span></span> <span data-ttu-id="d2ffb-106">Questo tipo di informazioni riservate definisce modelli, parole chiave e altre evidenze diverse per ogni paese.</span><span class="sxs-lookup"><span data-stu-id="d2ffb-106">This sensitive information type defines different patterns, keywords, and other evidence for each country.</span></span>
  
## <a name="austria"></a><span data-ttu-id="d2ffb-107">Austria</span><span class="sxs-lookup"><span data-stu-id="d2ffb-107">Austria</span></span>

### <a name="format"></a><span data-ttu-id="d2ffb-108">Formato</span><span class="sxs-lookup"><span data-stu-id="d2ffb-108">Format</span></span>

<span data-ttu-id="d2ffb-109">Una lettera seguita da uno spazio facoltativo e sette cifre</span><span class="sxs-lookup"><span data-stu-id="d2ffb-109">One letter followed by an optional space and seven digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="d2ffb-110">Modello</span><span class="sxs-lookup"><span data-stu-id="d2ffb-110">Pattern</span></span>

<span data-ttu-id="d2ffb-111">Combinazione di una lettera, sette cifre e uno spazio:</span><span class="sxs-lookup"><span data-stu-id="d2ffb-111">A combination of one letter, seven digits, and one space:</span></span>
  
- <span data-ttu-id="d2ffb-112">Una lettera (senza distinzione tra maiuscole/minuscole)</span><span class="sxs-lookup"><span data-stu-id="d2ffb-112">One letter (not case sensitive)</span></span>
    
- <span data-ttu-id="d2ffb-113">Uno spazio (facoltativo)</span><span class="sxs-lookup"><span data-stu-id="d2ffb-113">One space (optional)</span></span>
    
- <span data-ttu-id="d2ffb-114">Sette cifre</span><span class="sxs-lookup"><span data-stu-id="d2ffb-114">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="d2ffb-115">Checksum</span><span class="sxs-lookup"><span data-stu-id="d2ffb-115">Checksum</span></span>

<span data-ttu-id="d2ffb-116">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="d2ffb-116">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="d2ffb-117">Definizione</span><span class="sxs-lookup"><span data-stu-id="d2ffb-117">Definition</span></span>

<span data-ttu-id="d2ffb-118">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="d2ffb-118">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="d2ffb-119">L'espressione `Regex_austria_eu_passport_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="d2ffb-119">The regular expression  `Regex_austria_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="d2ffb-120">Viene trovata una `Keywords_austria_eu_passport_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="d2ffb-120">A keyword from  `Keywords_austria_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_austria_eu_passport_number" />
          <Match idRef="Keywords_austria_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="d2ffb-121">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="d2ffb-121">Keywords</span></span>

<span data-ttu-id="d2ffb-122">| |</span><span class="sxs-lookup"><span data-stu-id="d2ffb-122"></span></span>
|<span data-ttu-id="d2ffb-123">**Keywords_austria_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="d2ffb-123">**Keywords_austria_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="d2ffb-124">passport number</span><span class="sxs-lookup"><span data-stu-id="d2ffb-124">passport number</span></span>  <br/> <span data-ttu-id="d2ffb-125">numero di passaporto austriaco</span><span class="sxs-lookup"><span data-stu-id="d2ffb-125">austrian passport number</span></span>  <br/> <span data-ttu-id="d2ffb-126">Passport No</span><span class="sxs-lookup"><span data-stu-id="d2ffb-126">passport no</span></span>  <br/> <span data-ttu-id="d2ffb-127">reisepass</span><span class="sxs-lookup"><span data-stu-id="d2ffb-127">reisepass</span></span>  <br/> <span data-ttu-id="d2ffb-128">österreichisch reisepass</span><span class="sxs-lookup"><span data-stu-id="d2ffb-128">österreichisch reisepass</span></span>  <br/> |
   
## <a name="belgium"></a><span data-ttu-id="d2ffb-129">Belgio</span><span class="sxs-lookup"><span data-stu-id="d2ffb-129">Belgium</span></span>

### <a name="format"></a><span data-ttu-id="d2ffb-130">Formato</span><span class="sxs-lookup"><span data-stu-id="d2ffb-130">Format</span></span>

<span data-ttu-id="d2ffb-131">Due lettere seguite da sei cifre senza spazi o delimitatori</span><span class="sxs-lookup"><span data-stu-id="d2ffb-131">Two letters followed by six digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="d2ffb-132">Modello</span><span class="sxs-lookup"><span data-stu-id="d2ffb-132">Pattern</span></span>

<span data-ttu-id="d2ffb-133">Due lettere e seguite da sei cifre</span><span class="sxs-lookup"><span data-stu-id="d2ffb-133">Two letters and followed by six digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="d2ffb-134">Checksum</span><span class="sxs-lookup"><span data-stu-id="d2ffb-134">Checksum</span></span>

<span data-ttu-id="d2ffb-135">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="d2ffb-135">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="d2ffb-136">Definizione</span><span class="sxs-lookup"><span data-stu-id="d2ffb-136">Definition</span></span>

<span data-ttu-id="d2ffb-137">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="d2ffb-137">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="d2ffb-138">L'espressione `Regex_belgium_eu_passport_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="d2ffb-138">The regular expression  `Regex_belgium_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="d2ffb-139">Viene trovata una `Keywords_belgium_eu_passport_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="d2ffb-139">A keyword from  `Keywords_belgium_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_belgium__eu_passport_number" />
          <Match idRef="Keywords_belgium_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="d2ffb-140">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="d2ffb-140">Keywords</span></span>

<span data-ttu-id="d2ffb-141">| |</span><span class="sxs-lookup"><span data-stu-id="d2ffb-141"></span></span>
|<span data-ttu-id="d2ffb-142">**Keywords_belgium_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="d2ffb-142">**Keywords_belgium_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="d2ffb-143">passport number</span><span class="sxs-lookup"><span data-stu-id="d2ffb-143">passport number</span></span>  <br/> <span data-ttu-id="d2ffb-144">numero di passaporto belga</span><span class="sxs-lookup"><span data-stu-id="d2ffb-144">belgian passport number</span></span>  <br/> <span data-ttu-id="d2ffb-145">Passport No</span><span class="sxs-lookup"><span data-stu-id="d2ffb-145">passport no</span></span>  <br/> <span data-ttu-id="d2ffb-146">paspoort</span><span class="sxs-lookup"><span data-stu-id="d2ffb-146">paspoort</span></span>  <br/> <span data-ttu-id="d2ffb-147">paspoortnummer</span><span class="sxs-lookup"><span data-stu-id="d2ffb-147">paspoortnummer</span></span>  <br/> <span data-ttu-id="d2ffb-148">Reisepass kein</span><span class="sxs-lookup"><span data-stu-id="d2ffb-148">reisepass kein</span></span>  <br/> <span data-ttu-id="d2ffb-149">reisepass</span><span class="sxs-lookup"><span data-stu-id="d2ffb-149">reisepass</span></span>  <br/> |
   
## <a name="bulgaria"></a><span data-ttu-id="d2ffb-150">Bulgaria</span><span class="sxs-lookup"><span data-stu-id="d2ffb-150">Bulgaria</span></span>

### <a name="format"></a><span data-ttu-id="d2ffb-151">Formato</span><span class="sxs-lookup"><span data-stu-id="d2ffb-151">Format</span></span>

<span data-ttu-id="d2ffb-152">Nove cifre senza spazi e delimitatori</span><span class="sxs-lookup"><span data-stu-id="d2ffb-152">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="d2ffb-153">Modello</span><span class="sxs-lookup"><span data-stu-id="d2ffb-153">Pattern</span></span>

 <span data-ttu-id="d2ffb-154">9 cifre</span><span class="sxs-lookup"><span data-stu-id="d2ffb-154">Nine digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="d2ffb-155">Checksum</span><span class="sxs-lookup"><span data-stu-id="d2ffb-155">Checksum</span></span>

<span data-ttu-id="d2ffb-156">No</span><span class="sxs-lookup"><span data-stu-id="d2ffb-156">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="d2ffb-157">Definizione</span><span class="sxs-lookup"><span data-stu-id="d2ffb-157">Definition</span></span>

<span data-ttu-id="d2ffb-158">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="d2ffb-158">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="d2ffb-159">L'espressione `Regex_bulgaria_eu_passport_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="d2ffb-159">The regular expression  `Regex_bulgaria_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="d2ffb-160">Viene trovata una `Keywords_bulgaria_eu_passport_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="d2ffb-160">A keyword from  `Keywords_bulgaria_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_bulgaria_eu_passport_number" />
          <Match idRef="Keywords_bulgaria_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="d2ffb-161">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="d2ffb-161">Keywords</span></span>

<span data-ttu-id="d2ffb-162">| |</span><span class="sxs-lookup"><span data-stu-id="d2ffb-162"></span></span>
|<span data-ttu-id="d2ffb-163">**Keywords_bulgaria_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="d2ffb-163">**Keywords_bulgaria_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="d2ffb-164">passport number</span><span class="sxs-lookup"><span data-stu-id="d2ffb-164">passport number</span></span>  <br/> <span data-ttu-id="d2ffb-165">numero di passaporto bulgaro</span><span class="sxs-lookup"><span data-stu-id="d2ffb-165">bulgarian passport number</span></span>  <br/> <span data-ttu-id="d2ffb-166">Passport No</span><span class="sxs-lookup"><span data-stu-id="d2ffb-166">passport no</span></span>  <br/> <span data-ttu-id="d2ffb-167">Номер на паспорта</span><span class="sxs-lookup"><span data-stu-id="d2ffb-167">номер на паспорта</span></span>  <br/> |
   
## <a name="croatia"></a><span data-ttu-id="d2ffb-168">Croazia</span><span class="sxs-lookup"><span data-stu-id="d2ffb-168">Croatia</span></span>

### <a name="format"></a><span data-ttu-id="d2ffb-169">Formato</span><span class="sxs-lookup"><span data-stu-id="d2ffb-169">Format</span></span>

<span data-ttu-id="d2ffb-170">Nove cifre senza spazi e delimitatori</span><span class="sxs-lookup"><span data-stu-id="d2ffb-170">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="d2ffb-171">Modello</span><span class="sxs-lookup"><span data-stu-id="d2ffb-171">Pattern</span></span>

 <span data-ttu-id="d2ffb-172">9 cifre</span><span class="sxs-lookup"><span data-stu-id="d2ffb-172">Nine digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="d2ffb-173">Checksum</span><span class="sxs-lookup"><span data-stu-id="d2ffb-173">Checksum</span></span>

<span data-ttu-id="d2ffb-174">No</span><span class="sxs-lookup"><span data-stu-id="d2ffb-174">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="d2ffb-175">Definizione</span><span class="sxs-lookup"><span data-stu-id="d2ffb-175">Definition</span></span>

<span data-ttu-id="d2ffb-176">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="d2ffb-176">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="d2ffb-177">L'espressione `Regex_croatia_eu_passport_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="d2ffb-177">The regular expression  `Regex_croatia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="d2ffb-178">Viene trovata una `Keywords_croatia_eu_passport_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="d2ffb-178">A keyword from  `Keywords_croatia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_croatia_eu_passport_number" />
          <Match idRef="Keywords_croatia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="d2ffb-179">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="d2ffb-179">Keywords</span></span>

<span data-ttu-id="d2ffb-180">| |</span><span class="sxs-lookup"><span data-stu-id="d2ffb-180"></span></span>
|<span data-ttu-id="d2ffb-181">**Keywords_croatia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="d2ffb-181">**Keywords_croatia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="d2ffb-182">passport number</span><span class="sxs-lookup"><span data-stu-id="d2ffb-182">passport number</span></span>  <br/> <span data-ttu-id="d2ffb-183">numero di passaporto croato</span><span class="sxs-lookup"><span data-stu-id="d2ffb-183">croatian passport number</span></span>  <br/> <span data-ttu-id="d2ffb-184">Passport No</span><span class="sxs-lookup"><span data-stu-id="d2ffb-184">passport no</span></span>  <br/> <span data-ttu-id="d2ffb-185">broj putovnice</span><span class="sxs-lookup"><span data-stu-id="d2ffb-185">broj putovnice</span></span>  <br/> |
   
## <a name="cyprus"></a><span data-ttu-id="d2ffb-186">Cipro</span><span class="sxs-lookup"><span data-stu-id="d2ffb-186">Cyprus</span></span>

### <a name="format"></a><span data-ttu-id="d2ffb-187">Formato</span><span class="sxs-lookup"><span data-stu-id="d2ffb-187">Format</span></span>

<span data-ttu-id="d2ffb-188">Una lettera seguita da 6-8 cifre senza spazi o delimitatori</span><span class="sxs-lookup"><span data-stu-id="d2ffb-188">One letter followed by 6-8 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="d2ffb-189">Modello</span><span class="sxs-lookup"><span data-stu-id="d2ffb-189">Pattern</span></span>

<span data-ttu-id="d2ffb-190">Una lettera seguita da sei a otto cifre</span><span class="sxs-lookup"><span data-stu-id="d2ffb-190">One letter followed by six to eight digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="d2ffb-191">Checksum</span><span class="sxs-lookup"><span data-stu-id="d2ffb-191">Checksum</span></span>

<span data-ttu-id="d2ffb-192">No</span><span class="sxs-lookup"><span data-stu-id="d2ffb-192">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="d2ffb-193">Definizione</span><span class="sxs-lookup"><span data-stu-id="d2ffb-193">Definition</span></span>

<span data-ttu-id="d2ffb-194">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="d2ffb-194">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="d2ffb-195">L'espressione `Regex_cyprus_eu_passport_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="d2ffb-195">The regular expression  `Regex_cyprus_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="d2ffb-196">Viene trovata una `Keywords_cyprus_eu_passport_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="d2ffb-196">A keyword from  `Keywords_cyprus_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_cyprus_eu_passport_number" />
          <Match idRef="Keywords_cyprus_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="d2ffb-197">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="d2ffb-197">Keywords</span></span>

<span data-ttu-id="d2ffb-198">| |</span><span class="sxs-lookup"><span data-stu-id="d2ffb-198"></span></span>
|<span data-ttu-id="d2ffb-199">**Keywords_cyprus_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="d2ffb-199">**Keywords_cyprus_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="d2ffb-200">passport number</span><span class="sxs-lookup"><span data-stu-id="d2ffb-200">passport number</span></span>  <br/> <span data-ttu-id="d2ffb-201">numero di passaporto di Cipro</span><span class="sxs-lookup"><span data-stu-id="d2ffb-201">cyprus passport number</span></span>  <br/> <span data-ttu-id="d2ffb-202">Passport No</span><span class="sxs-lookup"><span data-stu-id="d2ffb-202">passport no</span></span>  <br/> <span data-ttu-id="d2ffb-203">αριθμό διαβατηρίου</span><span class="sxs-lookup"><span data-stu-id="d2ffb-203">αριθμό διαβατηρίου</span></span>  <br/> |
   
## <a name="czech-republic"></a><span data-ttu-id="d2ffb-204">Repubblica Ceca</span><span class="sxs-lookup"><span data-stu-id="d2ffb-204">Czech Republic</span></span>

### <a name="format"></a><span data-ttu-id="d2ffb-205">Formato</span><span class="sxs-lookup"><span data-stu-id="d2ffb-205">Format</span></span>

<span data-ttu-id="d2ffb-206">Otto cifre senza spazi o delimitatori</span><span class="sxs-lookup"><span data-stu-id="d2ffb-206">Eight digits without spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="d2ffb-207">Modello</span><span class="sxs-lookup"><span data-stu-id="d2ffb-207">Pattern</span></span>

<span data-ttu-id="d2ffb-208">Otto cifre senza spazi o delimitatori</span><span class="sxs-lookup"><span data-stu-id="d2ffb-208">Eight digits without spaces or delimiters</span></span>
  
### <a name="checksum"></a><span data-ttu-id="d2ffb-209">Checksum</span><span class="sxs-lookup"><span data-stu-id="d2ffb-209">Checksum</span></span>

<span data-ttu-id="d2ffb-210">No</span><span class="sxs-lookup"><span data-stu-id="d2ffb-210">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="d2ffb-211">Definizione</span><span class="sxs-lookup"><span data-stu-id="d2ffb-211">Definition</span></span>

<span data-ttu-id="d2ffb-212">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="d2ffb-212">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="d2ffb-213">L'espressione `Regex_czech_republic_eu_passport_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="d2ffb-213">The regular expression  `Regex_czech_republic_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="d2ffb-214">Viene trovata una `Keywords_czech_republic_eu_passport_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="d2ffb-214">A keyword from  `Keywords_czech_republic_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_czech_republic_eu_passport_number" />
          <Match idRef="Keywords_czech_republic_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="d2ffb-215">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="d2ffb-215">Keywords</span></span>

<span data-ttu-id="d2ffb-216">| |</span><span class="sxs-lookup"><span data-stu-id="d2ffb-216"></span></span>
|<span data-ttu-id="d2ffb-217">**Keywords_czech_republic_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="d2ffb-217">**Keywords_czech_republic_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="d2ffb-218">passport number</span><span class="sxs-lookup"><span data-stu-id="d2ffb-218">passport number</span></span>  <br/> <span data-ttu-id="d2ffb-219">numero di passaporto ceco</span><span class="sxs-lookup"><span data-stu-id="d2ffb-219">czech passport number</span></span>  <br/> <span data-ttu-id="d2ffb-220">Passport No</span><span class="sxs-lookup"><span data-stu-id="d2ffb-220">passport no</span></span>  <br/> <span data-ttu-id="d2ffb-221">Cestovní pas</span><span class="sxs-lookup"><span data-stu-id="d2ffb-221">cestovní pas</span></span>  <br/> <span data-ttu-id="d2ffb-222">pas</span><span class="sxs-lookup"><span data-stu-id="d2ffb-222">pas</span></span>  <br/> |
   
## <a name="denmark"></a><span data-ttu-id="d2ffb-223">Danimarca</span><span class="sxs-lookup"><span data-stu-id="d2ffb-223">Denmark</span></span>

### <a name="format"></a><span data-ttu-id="d2ffb-224">Formato</span><span class="sxs-lookup"><span data-stu-id="d2ffb-224">Format</span></span>

<span data-ttu-id="d2ffb-225">Nove cifre senza spazi e delimitatori</span><span class="sxs-lookup"><span data-stu-id="d2ffb-225">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="d2ffb-226">Modello</span><span class="sxs-lookup"><span data-stu-id="d2ffb-226">Pattern</span></span>

 <span data-ttu-id="d2ffb-227">9 cifre</span><span class="sxs-lookup"><span data-stu-id="d2ffb-227">Nine digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="d2ffb-228">Checksum</span><span class="sxs-lookup"><span data-stu-id="d2ffb-228">Checksum</span></span>

<span data-ttu-id="d2ffb-229">No</span><span class="sxs-lookup"><span data-stu-id="d2ffb-229">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="d2ffb-230">Definizione</span><span class="sxs-lookup"><span data-stu-id="d2ffb-230">Definition</span></span>

<span data-ttu-id="d2ffb-231">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="d2ffb-231">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="d2ffb-232">L'espressione `Regex_denmark_eu_passport_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="d2ffb-232">The regular expression  `Regex_denmark_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="d2ffb-233">Viene trovata una `Keywords_denmark_eu_passport_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="d2ffb-233">A keyword from  `Keywords_denmark_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_denmark_eu_passport_number" />
          <Match idRef="Keywords_denmark_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="d2ffb-234">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="d2ffb-234">Keywords</span></span>

<span data-ttu-id="d2ffb-235">| |</span><span class="sxs-lookup"><span data-stu-id="d2ffb-235"></span></span>
|<span data-ttu-id="d2ffb-236">**Keywords_denmark_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="d2ffb-236">**Keywords_denmark_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="d2ffb-237">passport number</span><span class="sxs-lookup"><span data-stu-id="d2ffb-237">passport number</span></span>  <br/> <span data-ttu-id="d2ffb-238">numero di passaporto danese</span><span class="sxs-lookup"><span data-stu-id="d2ffb-238">danish passport number</span></span>  <br/> <span data-ttu-id="d2ffb-239">Passport No</span><span class="sxs-lookup"><span data-stu-id="d2ffb-239">passport no</span></span>  <br/> <span data-ttu-id="d2ffb-240">pas</span><span class="sxs-lookup"><span data-stu-id="d2ffb-240">pas</span></span>  <br/> <span data-ttu-id="d2ffb-241">Pasnummer</span><span class="sxs-lookup"><span data-stu-id="d2ffb-241">pasnummer</span></span>  <br/> |
   
## <a name="estonia"></a><span data-ttu-id="d2ffb-242">Estonia</span><span class="sxs-lookup"><span data-stu-id="d2ffb-242">Estonia</span></span>

### <a name="format"></a><span data-ttu-id="d2ffb-243">Formato</span><span class="sxs-lookup"><span data-stu-id="d2ffb-243">Format</span></span>

<span data-ttu-id="d2ffb-244">Una lettera seguita da sette cifre senza spazi o delimitatori</span><span class="sxs-lookup"><span data-stu-id="d2ffb-244">One letter followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="d2ffb-245">Modello</span><span class="sxs-lookup"><span data-stu-id="d2ffb-245">Pattern</span></span>

<span data-ttu-id="d2ffb-246">Una lettera seguita da sette cifre</span><span class="sxs-lookup"><span data-stu-id="d2ffb-246">One letter followed by seven digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="d2ffb-247">Checksum</span><span class="sxs-lookup"><span data-stu-id="d2ffb-247">Checksum</span></span>

<span data-ttu-id="d2ffb-248">No</span><span class="sxs-lookup"><span data-stu-id="d2ffb-248">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="d2ffb-249">Definizione</span><span class="sxs-lookup"><span data-stu-id="d2ffb-249">Definition</span></span>

<span data-ttu-id="d2ffb-250">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="d2ffb-250">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="d2ffb-251">L'espressione `Regex_estonia_eu_passport_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="d2ffb-251">The regular expression  `Regex_estonia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="d2ffb-252">Viene trovata una `Keywords_estonia_eu_passport_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="d2ffb-252">A keyword from  `Keywords_estonia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_estonia_eu_passport_number" />
          <Match idRef="Keywords_estonia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="d2ffb-253">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="d2ffb-253">Keywords</span></span>

<span data-ttu-id="d2ffb-254">| |</span><span class="sxs-lookup"><span data-stu-id="d2ffb-254"></span></span>
|<span data-ttu-id="d2ffb-255">**Keywords_estonia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="d2ffb-255">**Keywords_estonia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="d2ffb-256">passport number</span><span class="sxs-lookup"><span data-stu-id="d2ffb-256">passport number</span></span>  <br/> <span data-ttu-id="d2ffb-257">numero di passaporto estone</span><span class="sxs-lookup"><span data-stu-id="d2ffb-257">estonian passport number</span></span>  <br/> <span data-ttu-id="d2ffb-258">Passport No</span><span class="sxs-lookup"><span data-stu-id="d2ffb-258">passport no</span></span>  <br/> <span data-ttu-id="d2ffb-259">passaggio kodaniku Eesti</span><span class="sxs-lookup"><span data-stu-id="d2ffb-259">eesti kodaniku pass</span></span>  <br/> |
   
## <a name="finland"></a><span data-ttu-id="d2ffb-260">Finlandia</span><span class="sxs-lookup"><span data-stu-id="d2ffb-260">Finland</span></span>

<span data-ttu-id="d2ffb-261">Per informazioni dettagliate, vedere la sezione "Finlandia Passport Number" in [che cosa cercano i tipi di informazioni riservate](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="d2ffb-261">For details, see the section "Finland Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="france"></a><span data-ttu-id="d2ffb-262">Francia</span><span class="sxs-lookup"><span data-stu-id="d2ffb-262">France</span></span>

<span data-ttu-id="d2ffb-263">Per informazioni dettagliate, vedere la sezione "Francia Passport Number" in [che cosa cercano i tipi di informazioni riservate](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="d2ffb-263">For details, see the section "France Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="germany"></a><span data-ttu-id="d2ffb-264">Germania</span><span class="sxs-lookup"><span data-stu-id="d2ffb-264">Germany</span></span>

<span data-ttu-id="d2ffb-265">Per informazioni dettagliate, vedere la sezione "Germania Passport Number" in [che cosa cercano i tipi di informazioni riservate](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="d2ffb-265">For details, see the section "Germany Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="greece"></a><span data-ttu-id="d2ffb-266">Grecia</span><span class="sxs-lookup"><span data-stu-id="d2ffb-266">Greece</span></span>

### <a name="format"></a><span data-ttu-id="d2ffb-267">Formato</span><span class="sxs-lookup"><span data-stu-id="d2ffb-267">Format</span></span>

<span data-ttu-id="d2ffb-268">Due lettere seguite da sette cifre senza spazi o delimitatori</span><span class="sxs-lookup"><span data-stu-id="d2ffb-268">Two letters followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="d2ffb-269">Modello</span><span class="sxs-lookup"><span data-stu-id="d2ffb-269">Pattern</span></span>

<span data-ttu-id="d2ffb-270">Due lettere seguite da 7 cifre</span><span class="sxs-lookup"><span data-stu-id="d2ffb-270">Two letters followed by seven digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="d2ffb-271">Checksum</span><span class="sxs-lookup"><span data-stu-id="d2ffb-271">Checksum</span></span>

<span data-ttu-id="d2ffb-272">No</span><span class="sxs-lookup"><span data-stu-id="d2ffb-272">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="d2ffb-273">Definizione</span><span class="sxs-lookup"><span data-stu-id="d2ffb-273">Definition</span></span>

<span data-ttu-id="d2ffb-274">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="d2ffb-274">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="d2ffb-275">L'espressione `Regex_greece_eu_passport_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="d2ffb-275">The regular expression  `Regex_greece_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="d2ffb-276">Viene trovata una `Keywords_greece_eu_passport_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="d2ffb-276">A keyword from  `Keywords_greece_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_greece_eu_passport_number" />
          <Match idRef="Keywords_greece_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="d2ffb-277">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="d2ffb-277">Keywords</span></span>

<span data-ttu-id="d2ffb-278">| |</span><span class="sxs-lookup"><span data-stu-id="d2ffb-278"></span></span>
|<span data-ttu-id="d2ffb-279">**Keywords_greece_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="d2ffb-279">**Keywords_greece_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="d2ffb-280">passport number</span><span class="sxs-lookup"><span data-stu-id="d2ffb-280">passport number</span></span>  <br/> <span data-ttu-id="d2ffb-281">numero di passaporto greco</span><span class="sxs-lookup"><span data-stu-id="d2ffb-281">greek passport number</span></span>  <br/> <span data-ttu-id="d2ffb-282">Passport No</span><span class="sxs-lookup"><span data-stu-id="d2ffb-282">passport no</span></span>  <br/> <span data-ttu-id="d2ffb-283">διαβατηριο</span><span class="sxs-lookup"><span data-stu-id="d2ffb-283">διαβατηριο</span></span>  <br/> |
   
## <a name="hungary"></a><span data-ttu-id="d2ffb-284">Ungheria</span><span class="sxs-lookup"><span data-stu-id="d2ffb-284">Hungary</span></span>

### <a name="format"></a><span data-ttu-id="d2ffb-285">Formato</span><span class="sxs-lookup"><span data-stu-id="d2ffb-285">Format</span></span>

<span data-ttu-id="d2ffb-286">Due lettere seguite da sei o sette cifre senza spazi o delimitatori</span><span class="sxs-lookup"><span data-stu-id="d2ffb-286">Two letters followed by six or seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="d2ffb-287">Modello</span><span class="sxs-lookup"><span data-stu-id="d2ffb-287">Pattern</span></span>

<span data-ttu-id="d2ffb-288">Due lettere seguite da sei o sette cifre</span><span class="sxs-lookup"><span data-stu-id="d2ffb-288">Two letters followed by six or seven digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="d2ffb-289">Checksum</span><span class="sxs-lookup"><span data-stu-id="d2ffb-289">Checksum</span></span>

<span data-ttu-id="d2ffb-290">No</span><span class="sxs-lookup"><span data-stu-id="d2ffb-290">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="d2ffb-291">Definizione</span><span class="sxs-lookup"><span data-stu-id="d2ffb-291">Definition</span></span>

<span data-ttu-id="d2ffb-292">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="d2ffb-292">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="d2ffb-293">L'espressione `Regex_hungary_eu_passport_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="d2ffb-293">The regular expression  `Regex_hungary_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="d2ffb-294">Viene trovata una `Keywords_hungary_eu_passport_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="d2ffb-294">A keyword from  `Keywords_hungary_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_hungary_eu_passport_number" />
          <Match idRef="Keywords_hungary_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="d2ffb-295">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="d2ffb-295">Keywords</span></span>

<span data-ttu-id="d2ffb-296">| |</span><span class="sxs-lookup"><span data-stu-id="d2ffb-296"></span></span>
|<span data-ttu-id="d2ffb-297">**Keywords_hungary_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="d2ffb-297">**Keywords_hungary_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="d2ffb-298">passport number</span><span class="sxs-lookup"><span data-stu-id="d2ffb-298">passport number</span></span>  <br/> <span data-ttu-id="d2ffb-299">numero di passaporto ungherese</span><span class="sxs-lookup"><span data-stu-id="d2ffb-299">hungarian passport number</span></span>  <br/> <span data-ttu-id="d2ffb-300">Passport No</span><span class="sxs-lookup"><span data-stu-id="d2ffb-300">passport no</span></span>  <br/> <span data-ttu-id="d2ffb-301">útlevél száma</span><span class="sxs-lookup"><span data-stu-id="d2ffb-301">útlevél száma</span></span>  <br/> |
   
## <a name="ireland"></a><span data-ttu-id="d2ffb-302">Irlanda</span><span class="sxs-lookup"><span data-stu-id="d2ffb-302">Ireland</span></span>

### <a name="format"></a><span data-ttu-id="d2ffb-303">Formato</span><span class="sxs-lookup"><span data-stu-id="d2ffb-303">Format</span></span>

<span data-ttu-id="d2ffb-304">Due lettere o cifre seguite da sette cifre senza spazi o delimitatori</span><span class="sxs-lookup"><span data-stu-id="d2ffb-304">Two letters or digits followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="d2ffb-305">Modello</span><span class="sxs-lookup"><span data-stu-id="d2ffb-305">Pattern</span></span>

<span data-ttu-id="d2ffb-306">Due lettere o cifre seguite da sette cifre:</span><span class="sxs-lookup"><span data-stu-id="d2ffb-306">Two letters or digits followed by seven digits:</span></span>
  
- <span data-ttu-id="d2ffb-307">Due cifre o lettere (senza distinzione tra maiuscole/minuscole)</span><span class="sxs-lookup"><span data-stu-id="d2ffb-307">Two digits or letters (not case sensitive)</span></span>
    
- <span data-ttu-id="d2ffb-308">Sette cifre</span><span class="sxs-lookup"><span data-stu-id="d2ffb-308">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="d2ffb-309">Checksum</span><span class="sxs-lookup"><span data-stu-id="d2ffb-309">Checksum</span></span>

<span data-ttu-id="d2ffb-310">No</span><span class="sxs-lookup"><span data-stu-id="d2ffb-310">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="d2ffb-311">Definizione</span><span class="sxs-lookup"><span data-stu-id="d2ffb-311">Definition</span></span>

<span data-ttu-id="d2ffb-312">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="d2ffb-312">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="d2ffb-313">L'espressione `Regex_ireland_eu_passport_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="d2ffb-313">The regular expression  `Regex_ireland_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="d2ffb-314">Viene trovata una `Keywords_ireland_eu_passport_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="d2ffb-314">A keyword from  `Keywords_ireland_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_ireland_eu_passport_number" />
          <Match idRef="Keywords_ireland_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="d2ffb-315">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="d2ffb-315">Keywords</span></span>

<span data-ttu-id="d2ffb-316">| |</span><span class="sxs-lookup"><span data-stu-id="d2ffb-316"></span></span>
|<span data-ttu-id="d2ffb-317">**Keywords_ireland_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="d2ffb-317">**Keywords_ireland_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="d2ffb-318">passport number</span><span class="sxs-lookup"><span data-stu-id="d2ffb-318">passport number</span></span>  <br/> <span data-ttu-id="d2ffb-319">numero di passaporto irlandese</span><span class="sxs-lookup"><span data-stu-id="d2ffb-319">irish passport number</span></span>  <br/> <span data-ttu-id="d2ffb-320">Passport No</span><span class="sxs-lookup"><span data-stu-id="d2ffb-320">passport no</span></span>  <br/> <span data-ttu-id="d2ffb-321">pas</span><span class="sxs-lookup"><span data-stu-id="d2ffb-321">pas</span></span>  <br/> <span data-ttu-id="d2ffb-322">passaporto</span><span class="sxs-lookup"><span data-stu-id="d2ffb-322">passport</span></span>  <br/> <span data-ttu-id="d2ffb-323">Passeport</span><span class="sxs-lookup"><span data-stu-id="d2ffb-323">passeport</span></span>  <br/> <span data-ttu-id="d2ffb-324">numero Passeport</span><span class="sxs-lookup"><span data-stu-id="d2ffb-324">passeport numero</span></span>  <br/> |
   
## <a name="italy"></a><span data-ttu-id="d2ffb-325">Italia</span><span class="sxs-lookup"><span data-stu-id="d2ffb-325">Italy</span></span>

### <a name="format"></a><span data-ttu-id="d2ffb-326">Formato</span><span class="sxs-lookup"><span data-stu-id="d2ffb-326">Format</span></span>

<span data-ttu-id="d2ffb-327">Due lettere o cifre seguite da sette cifre senza spazi o delimitatori</span><span class="sxs-lookup"><span data-stu-id="d2ffb-327">Two letters or digits followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="d2ffb-328">Modello</span><span class="sxs-lookup"><span data-stu-id="d2ffb-328">Pattern</span></span>

<span data-ttu-id="d2ffb-329">Due lettere o cifre seguite da sette cifre:</span><span class="sxs-lookup"><span data-stu-id="d2ffb-329">Two letters or digits followed by seven digits:</span></span>
  
- <span data-ttu-id="d2ffb-330">Due cifre o lettere (senza distinzione tra maiuscole/minuscole)</span><span class="sxs-lookup"><span data-stu-id="d2ffb-330">Two digits or letters (not case sensitive)</span></span>
    
- <span data-ttu-id="d2ffb-331">Sette cifre</span><span class="sxs-lookup"><span data-stu-id="d2ffb-331">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="d2ffb-332">Checksum</span><span class="sxs-lookup"><span data-stu-id="d2ffb-332">Checksum</span></span>

<span data-ttu-id="d2ffb-333">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="d2ffb-333">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="d2ffb-334">Definizione</span><span class="sxs-lookup"><span data-stu-id="d2ffb-334">Definition</span></span>

<span data-ttu-id="d2ffb-335">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="d2ffb-335">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="d2ffb-336">L'espressione `Regex_italy_eu_passport_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="d2ffb-336">The regular expression  `Regex_italy_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="d2ffb-337">Viene trovata una `Keywords_italy_eu_passport_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="d2ffb-337">A keyword from  `Keywords_italy_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_italy_eu_passport_number" />
          <Match idRef="Keywords_italy_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="d2ffb-338">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="d2ffb-338">Keywords</span></span>

<span data-ttu-id="d2ffb-339">| |</span><span class="sxs-lookup"><span data-stu-id="d2ffb-339"></span></span>
|<span data-ttu-id="d2ffb-340">**Keywords_italy_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="d2ffb-340">**Keywords_italy_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="d2ffb-341">numero di passaporto italiano</span><span class="sxs-lookup"><span data-stu-id="d2ffb-341">italian passport number</span></span>  <br/> <span data-ttu-id="d2ffb-342">Repubblica italiana passaporto</span><span class="sxs-lookup"><span data-stu-id="d2ffb-342">repubblica italiana passaporto</span></span>  <br/> <span data-ttu-id="d2ffb-343">passaporto</span><span class="sxs-lookup"><span data-stu-id="d2ffb-343">passaporto</span></span>  <br/> <span data-ttu-id="d2ffb-344">passaporto italiana</span><span class="sxs-lookup"><span data-stu-id="d2ffb-344">passaporto italiana</span></span>  <br/> <span data-ttu-id="d2ffb-345">passport number</span><span class="sxs-lookup"><span data-stu-id="d2ffb-345">passport number</span></span>  <br/> <span data-ttu-id="d2ffb-346">italiana passaporto numero</span><span class="sxs-lookup"><span data-stu-id="d2ffb-346">italiana passaporto numero</span></span>  <br/> <span data-ttu-id="d2ffb-347">Numero passaporto</span><span class="sxs-lookup"><span data-stu-id="d2ffb-347">passaporto numero</span></span>  <br/> <span data-ttu-id="d2ffb-348">numéro Passeport Italien</span><span class="sxs-lookup"><span data-stu-id="d2ffb-348">numéro passeport italien</span></span>  <br/> <span data-ttu-id="d2ffb-349">numéro Passeport</span><span class="sxs-lookup"><span data-stu-id="d2ffb-349">numéro passeport</span></span>  <br/> |
   
## <a name="latvia"></a><span data-ttu-id="d2ffb-350">Lettonia</span><span class="sxs-lookup"><span data-stu-id="d2ffb-350">Latvia</span></span>

### <a name="format"></a><span data-ttu-id="d2ffb-351">Formato</span><span class="sxs-lookup"><span data-stu-id="d2ffb-351">Format</span></span>

<span data-ttu-id="d2ffb-352">Due lettere o cifre seguite da sette cifre senza spazi o delimitatori</span><span class="sxs-lookup"><span data-stu-id="d2ffb-352">Two letters or digits followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="d2ffb-353">Modello</span><span class="sxs-lookup"><span data-stu-id="d2ffb-353">Pattern</span></span>

<span data-ttu-id="d2ffb-354">Due lettere o cifre seguite da sette cifre:</span><span class="sxs-lookup"><span data-stu-id="d2ffb-354">Two letters or digits followed by seven digits:</span></span>
  
- <span data-ttu-id="d2ffb-355">Due cifre o lettere (senza distinzione tra maiuscole/minuscole)</span><span class="sxs-lookup"><span data-stu-id="d2ffb-355">Two digits or letters (not case sensitive)</span></span>
    
- <span data-ttu-id="d2ffb-356">Sette cifre</span><span class="sxs-lookup"><span data-stu-id="d2ffb-356">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="d2ffb-357">Checksum</span><span class="sxs-lookup"><span data-stu-id="d2ffb-357">Checksum</span></span>

<span data-ttu-id="d2ffb-358">No</span><span class="sxs-lookup"><span data-stu-id="d2ffb-358">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="d2ffb-359">Definizione</span><span class="sxs-lookup"><span data-stu-id="d2ffb-359">Definition</span></span>

<span data-ttu-id="d2ffb-360">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="d2ffb-360">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="d2ffb-361">L'espressione `Regex_latvia_eu_passport_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="d2ffb-361">The regular expression  `Regex_latvia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="d2ffb-362">Viene trovata una `Keywords_latvia_eu_passport_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="d2ffb-362">A keyword from  `Keywords_latvia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_latvia_eu_passport_number" />
          <Match idRef="Keywords_latvia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="d2ffb-363">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="d2ffb-363">Keywords</span></span>

<span data-ttu-id="d2ffb-364">| |</span><span class="sxs-lookup"><span data-stu-id="d2ffb-364"></span></span>
|<span data-ttu-id="d2ffb-365">**Keywords_latvia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="d2ffb-365">**Keywords_latvia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="d2ffb-366">passport number</span><span class="sxs-lookup"><span data-stu-id="d2ffb-366">passport number</span></span>  <br/> <span data-ttu-id="d2ffb-367">numero di passaporto lettone</span><span class="sxs-lookup"><span data-stu-id="d2ffb-367">latvian passport number</span></span>  <br/> <span data-ttu-id="d2ffb-368">Passport No</span><span class="sxs-lookup"><span data-stu-id="d2ffb-368">passport no</span></span>  <br/> <span data-ttu-id="d2ffb-369">pase numurs</span><span class="sxs-lookup"><span data-stu-id="d2ffb-369">pase numurs</span></span>  <br/> |
   
## <a name="lithuania"></a><span data-ttu-id="d2ffb-370">Lituania</span><span class="sxs-lookup"><span data-stu-id="d2ffb-370">Lithuania</span></span>

### <a name="format"></a><span data-ttu-id="d2ffb-371">Formato</span><span class="sxs-lookup"><span data-stu-id="d2ffb-371">Format</span></span>

<span data-ttu-id="d2ffb-372">Otto cifre o lettere senza spazi o delimitatori</span><span class="sxs-lookup"><span data-stu-id="d2ffb-372">Eight digits or letters with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="d2ffb-373">Modello</span><span class="sxs-lookup"><span data-stu-id="d2ffb-373">Pattern</span></span>

<span data-ttu-id="d2ffb-374">Otto cifre o lettere (senza distinzione tra maiuscole e minuscole)</span><span class="sxs-lookup"><span data-stu-id="d2ffb-374">Eight digits or letters (not case sensitive)</span></span>
  
### <a name="checksum"></a><span data-ttu-id="d2ffb-375">Checksum</span><span class="sxs-lookup"><span data-stu-id="d2ffb-375">Checksum</span></span>

<span data-ttu-id="d2ffb-376">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="d2ffb-376">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="d2ffb-377">Definizione</span><span class="sxs-lookup"><span data-stu-id="d2ffb-377">Definition</span></span>

<span data-ttu-id="d2ffb-378">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="d2ffb-378">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="d2ffb-379">L'espressione `Regex_lithuania_eu_passport_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="d2ffb-379">The regular expression  `Regex_lithuania_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="d2ffb-380">Viene trovata una `Keywords_lithuania_eu_passport_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="d2ffb-380">A keyword from  `Keywords_lithuania_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_lithuania_eu_passport_number" />
          <Match idRef="Keywords_lithuania_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="d2ffb-381">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="d2ffb-381">Keywords</span></span>

<span data-ttu-id="d2ffb-382">| |</span><span class="sxs-lookup"><span data-stu-id="d2ffb-382"></span></span>
|<span data-ttu-id="d2ffb-383">**Keywords_lithuania_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="d2ffb-383">**Keywords_lithuania_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="d2ffb-384">passport number</span><span class="sxs-lookup"><span data-stu-id="d2ffb-384">passport number</span></span>  <br/> <span data-ttu-id="d2ffb-385">numero di passaporto di lithunian</span><span class="sxs-lookup"><span data-stu-id="d2ffb-385">lithunian passport number</span></span>  <br/> <span data-ttu-id="d2ffb-386">Passport No</span><span class="sxs-lookup"><span data-stu-id="d2ffb-386">passport no</span></span>  <br/> <span data-ttu-id="d2ffb-387">numero di Paso</span><span class="sxs-lookup"><span data-stu-id="d2ffb-387">paso numeris</span></span>  <br/> |
   
## <a name="luxemburg"></a><span data-ttu-id="d2ffb-388">Lussemburgo</span><span class="sxs-lookup"><span data-stu-id="d2ffb-388">Luxemburg</span></span>

### <a name="format"></a><span data-ttu-id="d2ffb-389">Formato</span><span class="sxs-lookup"><span data-stu-id="d2ffb-389">Format</span></span>

<span data-ttu-id="d2ffb-390">Otto cifre o lettere senza spazi o delimitatori</span><span class="sxs-lookup"><span data-stu-id="d2ffb-390">Eight digits or letters with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="d2ffb-391">Modello</span><span class="sxs-lookup"><span data-stu-id="d2ffb-391">Pattern</span></span>

<span data-ttu-id="d2ffb-392">Otto cifre o lettere (senza distinzione tra maiuscole e minuscole)</span><span class="sxs-lookup"><span data-stu-id="d2ffb-392">Eight digits or letters (not case sensitive)</span></span>
  
### <a name="checksum"></a><span data-ttu-id="d2ffb-393">Checksum</span><span class="sxs-lookup"><span data-stu-id="d2ffb-393">Checksum</span></span>

<span data-ttu-id="d2ffb-394">No</span><span class="sxs-lookup"><span data-stu-id="d2ffb-394">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="d2ffb-395">Definizione</span><span class="sxs-lookup"><span data-stu-id="d2ffb-395">Definition</span></span>

<span data-ttu-id="d2ffb-396">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="d2ffb-396">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="d2ffb-397">L'espressione `Regex_nation_eu_passport_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="d2ffb-397">The regular expression  `Regex_nation_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="d2ffb-398">Viene trovata una `Keywords_nation_eu_passport_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="d2ffb-398">A keyword from  `Keywords_nation_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_nation_eu_passport_number" />
          <Match idRef="Keywords_nation_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="d2ffb-399">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="d2ffb-399">Keywords</span></span>

<span data-ttu-id="d2ffb-400">| |</span><span class="sxs-lookup"><span data-stu-id="d2ffb-400"></span></span>
|<span data-ttu-id="d2ffb-401">**Keywords_nation_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="d2ffb-401">**Keywords_nation_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="d2ffb-402">passport number</span><span class="sxs-lookup"><span data-stu-id="d2ffb-402">passport number</span></span>  <br/> <span data-ttu-id="d2ffb-403">numero di passaporto lettone</span><span class="sxs-lookup"><span data-stu-id="d2ffb-403">latvian passport number</span></span>  <br/> <span data-ttu-id="d2ffb-404">Passport No</span><span class="sxs-lookup"><span data-stu-id="d2ffb-404">passport no</span></span>  <br/> <span data-ttu-id="d2ffb-405">passnummer</span><span class="sxs-lookup"><span data-stu-id="d2ffb-405">passnummer</span></span>  <br/> |
   
## <a name="malta"></a><span data-ttu-id="d2ffb-406">Malta</span><span class="sxs-lookup"><span data-stu-id="d2ffb-406">Malta</span></span>

### <a name="format"></a><span data-ttu-id="d2ffb-407">Formato</span><span class="sxs-lookup"><span data-stu-id="d2ffb-407">Format</span></span>

<span data-ttu-id="d2ffb-408">Sette cifre senza spazi o delimitatori</span><span class="sxs-lookup"><span data-stu-id="d2ffb-408">Seven digits without spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="d2ffb-409">Modello</span><span class="sxs-lookup"><span data-stu-id="d2ffb-409">Pattern</span></span>

 <span data-ttu-id="d2ffb-410">Sette cifre</span><span class="sxs-lookup"><span data-stu-id="d2ffb-410">Seven digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="d2ffb-411">Checksum</span><span class="sxs-lookup"><span data-stu-id="d2ffb-411">Checksum</span></span>

<span data-ttu-id="d2ffb-412">No</span><span class="sxs-lookup"><span data-stu-id="d2ffb-412">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="d2ffb-413">Definizione</span><span class="sxs-lookup"><span data-stu-id="d2ffb-413">Definition</span></span>

<span data-ttu-id="d2ffb-414">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="d2ffb-414">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="d2ffb-415">L'espressione `Regex_malta_eu_passport_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="d2ffb-415">The regular expression  `Regex_malta_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="d2ffb-416">Viene trovata una `Keywords_malta_eu_passport_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="d2ffb-416">A keyword from  `Keywords_malta_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_malta_eu_passport_number" />
          <Match idRef="Keywords_malta_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="d2ffb-417">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="d2ffb-417">Keywords</span></span>

<span data-ttu-id="d2ffb-418">| |</span><span class="sxs-lookup"><span data-stu-id="d2ffb-418"></span></span>
|<span data-ttu-id="d2ffb-419">**Keywords_malta_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="d2ffb-419">**Keywords_malta_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="d2ffb-420">passport number</span><span class="sxs-lookup"><span data-stu-id="d2ffb-420">passport number</span></span>  <br/> <span data-ttu-id="d2ffb-421">numero di passaporto maltese</span><span class="sxs-lookup"><span data-stu-id="d2ffb-421">maltese passport number</span></span>  <br/> <span data-ttu-id="d2ffb-422">Passport No</span><span class="sxs-lookup"><span data-stu-id="d2ffb-422">passport no</span></span>  <br/> <span data-ttu-id="d2ffb-423">numru tal-passaport</span><span class="sxs-lookup"><span data-stu-id="d2ffb-423">numru tal-passaport</span></span>  <br/> |
   
## <a name="netherlands"></a><span data-ttu-id="d2ffb-424">Paesi Bassi</span><span class="sxs-lookup"><span data-stu-id="d2ffb-424">Netherlands</span></span>

### <a name="format"></a><span data-ttu-id="d2ffb-425">Formato</span><span class="sxs-lookup"><span data-stu-id="d2ffb-425">Format</span></span>

<span data-ttu-id="d2ffb-426">Nove lettere o cifre senza spazi o delimitatori</span><span class="sxs-lookup"><span data-stu-id="d2ffb-426">Nine letters or digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="d2ffb-427">Modello</span><span class="sxs-lookup"><span data-stu-id="d2ffb-427">Pattern</span></span>

<span data-ttu-id="d2ffb-428">Nove lettere o cifre</span><span class="sxs-lookup"><span data-stu-id="d2ffb-428">Nine letters or digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="d2ffb-429">Checksum</span><span class="sxs-lookup"><span data-stu-id="d2ffb-429">Checksum</span></span>

<span data-ttu-id="d2ffb-430">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="d2ffb-430">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="d2ffb-431">Definizione</span><span class="sxs-lookup"><span data-stu-id="d2ffb-431">Definition</span></span>

<span data-ttu-id="d2ffb-432">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="d2ffb-432">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="d2ffb-433">L'espressione `Regex_netherlands_eu_passport_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="d2ffb-433">The regular expression  `Regex_netherlands_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="d2ffb-434">Viene trovata una `Keywords_netherlands_eu_passport_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="d2ffb-434">A keyword from  `Keywords_netherlands_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_netherlands_eu_passport_number" />
          <Match idRef="Keywords_netherlands_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="d2ffb-435">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="d2ffb-435">Keywords</span></span>

<span data-ttu-id="d2ffb-436">| |</span><span class="sxs-lookup"><span data-stu-id="d2ffb-436"></span></span>
|<span data-ttu-id="d2ffb-437">**Keywords_netherlands_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="d2ffb-437">**Keywords_netherlands_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="d2ffb-438">numero di passaporto olandese</span><span class="sxs-lookup"><span data-stu-id="d2ffb-438">dutch passport number</span></span>  <br/> <span data-ttu-id="d2ffb-439">passport number</span><span class="sxs-lookup"><span data-stu-id="d2ffb-439">passport number</span></span>  <br/> <span data-ttu-id="d2ffb-440">numero di passaporto per i Paesi Bassi</span><span class="sxs-lookup"><span data-stu-id="d2ffb-440">netherlands passport number</span></span>  <br/> <span data-ttu-id="d2ffb-441">Nederlanden PASPOORT Nummer</span><span class="sxs-lookup"><span data-stu-id="d2ffb-441">nederlanden paspoort nummer</span></span>  <br/> <span data-ttu-id="d2ffb-442">paspoort</span><span class="sxs-lookup"><span data-stu-id="d2ffb-442">paspoort</span></span>  <br/> <span data-ttu-id="d2ffb-443">Nederlanden paspoortnummer</span><span class="sxs-lookup"><span data-stu-id="d2ffb-443">nederlanden paspoortnummer</span></span>  <br/> <span data-ttu-id="d2ffb-444">paspoortnummer</span><span class="sxs-lookup"><span data-stu-id="d2ffb-444">paspoortnummer</span></span>  <br/> |
   
## <a name="poland"></a><span data-ttu-id="d2ffb-445">Polonia</span><span class="sxs-lookup"><span data-stu-id="d2ffb-445">Poland</span></span>

<span data-ttu-id="d2ffb-446">Per informazioni dettagliate, vedere la sezione "Poland Passport Number" in [che cosa cercano i tipi di informazioni riservate](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="d2ffb-446">For details, see the section "Poland Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="portugal"></a><span data-ttu-id="d2ffb-447">Portogallo</span><span class="sxs-lookup"><span data-stu-id="d2ffb-447">Portugal</span></span>

### <a name="format"></a><span data-ttu-id="d2ffb-448">Formato</span><span class="sxs-lookup"><span data-stu-id="d2ffb-448">Format</span></span>

<span data-ttu-id="d2ffb-449">Una lettera seguita da sei cifre senza spazi o delimitatori</span><span class="sxs-lookup"><span data-stu-id="d2ffb-449">One letter followed by six digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="d2ffb-450">Modello</span><span class="sxs-lookup"><span data-stu-id="d2ffb-450">Pattern</span></span>

<span data-ttu-id="d2ffb-451">Una lettera seguita da sei cifre:</span><span class="sxs-lookup"><span data-stu-id="d2ffb-451">One letter followed by six digits:</span></span>
  
- <span data-ttu-id="d2ffb-452">Una lettera (senza distinzione tra maiuscole/minuscole)</span><span class="sxs-lookup"><span data-stu-id="d2ffb-452">One letter (not case sensitive)</span></span>
    
- <span data-ttu-id="d2ffb-453">Sei cifre</span><span class="sxs-lookup"><span data-stu-id="d2ffb-453">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="d2ffb-454">Checksum</span><span class="sxs-lookup"><span data-stu-id="d2ffb-454">Checksum</span></span>

<span data-ttu-id="d2ffb-455">No</span><span class="sxs-lookup"><span data-stu-id="d2ffb-455">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="d2ffb-456">Definizione</span><span class="sxs-lookup"><span data-stu-id="d2ffb-456">Definition</span></span>

<span data-ttu-id="d2ffb-457">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="d2ffb-457">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="d2ffb-458">L'espressione `Regex_portugal_eu_passport_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="d2ffb-458">The regular expression  `Regex_portugal_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="d2ffb-459">Viene trovata una `Keywords_portugal_eu_passport_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="d2ffb-459">A keyword from  `Keywords_portugal_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_portugal_eu_passport_number" />
          <Match idRef="Keywords_portugal_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="d2ffb-460">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="d2ffb-460">Keywords</span></span>

<span data-ttu-id="d2ffb-461">| |</span><span class="sxs-lookup"><span data-stu-id="d2ffb-461"></span></span>
|<span data-ttu-id="d2ffb-462">**Keywords_portugal_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="d2ffb-462">**Keywords_portugal_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="d2ffb-463">passport number</span><span class="sxs-lookup"><span data-stu-id="d2ffb-463">passport number</span></span>  <br/> <span data-ttu-id="d2ffb-464">numero di passaporto portoghese</span><span class="sxs-lookup"><span data-stu-id="d2ffb-464">portuguese passport number</span></span>  <br/> <span data-ttu-id="d2ffb-465">Passport No</span><span class="sxs-lookup"><span data-stu-id="d2ffb-465">passport no</span></span>  <br/> <span data-ttu-id="d2ffb-466">número do passaporte</span><span class="sxs-lookup"><span data-stu-id="d2ffb-466">número do passaporte</span></span>  <br/> |
   
## <a name="romania"></a><span data-ttu-id="d2ffb-467">Romania</span><span class="sxs-lookup"><span data-stu-id="d2ffb-467">Romania</span></span>

### <a name="format"></a><span data-ttu-id="d2ffb-468">Formato</span><span class="sxs-lookup"><span data-stu-id="d2ffb-468">Format</span></span>

<span data-ttu-id="d2ffb-469">Otto o nove cifre senza spazi e delimitatori</span><span class="sxs-lookup"><span data-stu-id="d2ffb-469">Eight or nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="d2ffb-470">Modello</span><span class="sxs-lookup"><span data-stu-id="d2ffb-470">Pattern</span></span>

<span data-ttu-id="d2ffb-471">Otto o nove cifre</span><span class="sxs-lookup"><span data-stu-id="d2ffb-471">Eight or nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="d2ffb-472">Checksum</span><span class="sxs-lookup"><span data-stu-id="d2ffb-472">Checksum</span></span>

<span data-ttu-id="d2ffb-473">No</span><span class="sxs-lookup"><span data-stu-id="d2ffb-473">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="d2ffb-474">Definizione</span><span class="sxs-lookup"><span data-stu-id="d2ffb-474">Definition</span></span>

<span data-ttu-id="d2ffb-475">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="d2ffb-475">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="d2ffb-476">L'espressione `Regex_romania_eu_passport_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="d2ffb-476">The regular expression  `Regex_romania_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="d2ffb-477">Viene trovata una `Keywords_romania_eu_passport_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="d2ffb-477">A keyword from  `Keywords_romania_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_romania_eu_passport_number" />
          <Match idRef="Keywords_romania_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="d2ffb-478">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="d2ffb-478">Keywords</span></span>

<span data-ttu-id="d2ffb-479">| |</span><span class="sxs-lookup"><span data-stu-id="d2ffb-479"></span></span>
|<span data-ttu-id="d2ffb-480">**Keywords_romania_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="d2ffb-480">**Keywords_romania_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="d2ffb-481">passport number</span><span class="sxs-lookup"><span data-stu-id="d2ffb-481">passport number</span></span>  <br/> <span data-ttu-id="d2ffb-482">numero di passaporto rumeno</span><span class="sxs-lookup"><span data-stu-id="d2ffb-482">romanian passport number</span></span>  <br/> <span data-ttu-id="d2ffb-483">Passport No</span><span class="sxs-lookup"><span data-stu-id="d2ffb-483">passport no</span></span>  <br/> <span data-ttu-id="d2ffb-484">numărul pașaportului</span><span class="sxs-lookup"><span data-stu-id="d2ffb-484">numărul pașaportului</span></span>  <br/> |
   
## <a name="slovakia"></a><span data-ttu-id="d2ffb-485">Slovacchia</span><span class="sxs-lookup"><span data-stu-id="d2ffb-485">Slovakia</span></span>

### <a name="format"></a><span data-ttu-id="d2ffb-486">Formato</span><span class="sxs-lookup"><span data-stu-id="d2ffb-486">Format</span></span>

<span data-ttu-id="d2ffb-487">Una cifra o una lettera seguita da sette cifre senza spazi o delimitatori</span><span class="sxs-lookup"><span data-stu-id="d2ffb-487">One digit or letter followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="d2ffb-488">Modello</span><span class="sxs-lookup"><span data-stu-id="d2ffb-488">Pattern</span></span>

<span data-ttu-id="d2ffb-489">Una cifra o una lettera (senza distinzione tra maiuscole/minuscole) seguita da sette cifre</span><span class="sxs-lookup"><span data-stu-id="d2ffb-489">One digit or letter (not case sensitive) followed by seven digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="d2ffb-490">Checksum</span><span class="sxs-lookup"><span data-stu-id="d2ffb-490">Checksum</span></span>

<span data-ttu-id="d2ffb-491">No</span><span class="sxs-lookup"><span data-stu-id="d2ffb-491">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="d2ffb-492">Definizione</span><span class="sxs-lookup"><span data-stu-id="d2ffb-492">Definition</span></span>

<span data-ttu-id="d2ffb-493">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="d2ffb-493">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="d2ffb-494">L'espressione `Regex_slovakia_eu_passport_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="d2ffb-494">The regular expression  `Regex_slovakia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="d2ffb-495">Viene trovata una `Keywords_slovakia_eu_passport_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="d2ffb-495">A keyword from  `Keywords_slovakia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovakia_eu_passport_number" />
          <Match idRef="Keywords_slovakia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="d2ffb-496">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="d2ffb-496">Keywords</span></span>

<span data-ttu-id="d2ffb-497">| |</span><span class="sxs-lookup"><span data-stu-id="d2ffb-497"></span></span>
|<span data-ttu-id="d2ffb-498">**Keywords_slovakia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="d2ffb-498">**Keywords_slovakia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="d2ffb-499">passport number</span><span class="sxs-lookup"><span data-stu-id="d2ffb-499">passport number</span></span>  <br/> <span data-ttu-id="d2ffb-500">numero di passaporto slovacco</span><span class="sxs-lookup"><span data-stu-id="d2ffb-500">slovakian passport number</span></span>  <br/> <span data-ttu-id="d2ffb-501">Passport No</span><span class="sxs-lookup"><span data-stu-id="d2ffb-501">passport no</span></span>  <br/> <span data-ttu-id="d2ffb-502">číslo Pasu</span><span class="sxs-lookup"><span data-stu-id="d2ffb-502">číslo pasu</span></span>  <br/> |
   
## <a name="slovenia"></a><span data-ttu-id="d2ffb-503">Slovenia</span><span class="sxs-lookup"><span data-stu-id="d2ffb-503">Slovenia</span></span>

### <a name="format"></a><span data-ttu-id="d2ffb-504">Formato</span><span class="sxs-lookup"><span data-stu-id="d2ffb-504">Format</span></span>

<span data-ttu-id="d2ffb-505">Due lettere seguite da sette cifre senza spazi o delimitatori</span><span class="sxs-lookup"><span data-stu-id="d2ffb-505">Two letters followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="d2ffb-506">Modello</span><span class="sxs-lookup"><span data-stu-id="d2ffb-506">Pattern</span></span>

<span data-ttu-id="d2ffb-507">Due lettere seguite da sette cifre:</span><span class="sxs-lookup"><span data-stu-id="d2ffb-507">Two letters followed by seven digits:</span></span>
  
- <span data-ttu-id="d2ffb-508">La lettera "P"</span><span class="sxs-lookup"><span data-stu-id="d2ffb-508">The letter "P"</span></span>
    
- <span data-ttu-id="d2ffb-509">Una lettera maiuscola</span><span class="sxs-lookup"><span data-stu-id="d2ffb-509">One uppercase letter</span></span>
    
- <span data-ttu-id="d2ffb-510">Sette cifre</span><span class="sxs-lookup"><span data-stu-id="d2ffb-510">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="d2ffb-511">Checksum</span><span class="sxs-lookup"><span data-stu-id="d2ffb-511">Checksum</span></span>

<span data-ttu-id="d2ffb-512">No</span><span class="sxs-lookup"><span data-stu-id="d2ffb-512">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="d2ffb-513">Definizione</span><span class="sxs-lookup"><span data-stu-id="d2ffb-513">Definition</span></span>

<span data-ttu-id="d2ffb-514">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="d2ffb-514">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="d2ffb-515">L'espressione `Regex_slovenia_eu_passport_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="d2ffb-515">The regular expression  `Regex_slovenia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="d2ffb-516">Viene trovata una `Keywords_slovenia_eu_passport_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="d2ffb-516">A keyword from  `Keywords_slovenia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovenia_eu_passport_number" />
          <Match idRef="Keywords_slovenia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="d2ffb-517">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="d2ffb-517">Keywords</span></span>

<span data-ttu-id="d2ffb-518">| |</span><span class="sxs-lookup"><span data-stu-id="d2ffb-518"></span></span>
|<span data-ttu-id="d2ffb-519">**Keywords_slovenia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="d2ffb-519">**Keywords_slovenia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="d2ffb-520">passport number</span><span class="sxs-lookup"><span data-stu-id="d2ffb-520">passport number</span></span>  <br/> <span data-ttu-id="d2ffb-521">numero di passaporto sloveno</span><span class="sxs-lookup"><span data-stu-id="d2ffb-521">slovenian passport number</span></span>  <br/> <span data-ttu-id="d2ffb-522">Passport No</span><span class="sxs-lookup"><span data-stu-id="d2ffb-522">passport no</span></span>  <br/> <span data-ttu-id="d2ffb-523">številka potnega lista</span><span class="sxs-lookup"><span data-stu-id="d2ffb-523">številka potnega lista</span></span>  <br/> |
   
## <a name="spain"></a><span data-ttu-id="d2ffb-524">Spagna</span><span class="sxs-lookup"><span data-stu-id="d2ffb-524">Spain</span></span>

### <a name="format"></a><span data-ttu-id="d2ffb-525">Formato</span><span class="sxs-lookup"><span data-stu-id="d2ffb-525">Format</span></span>

<span data-ttu-id="d2ffb-526">Combinazione di otto o nove caratteri di lettere e numeri senza spazi o delimitatori</span><span class="sxs-lookup"><span data-stu-id="d2ffb-526">An eight- or nine-character combination of letters and numbers with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="d2ffb-527">Modello</span><span class="sxs-lookup"><span data-stu-id="d2ffb-527">Pattern</span></span>

<span data-ttu-id="d2ffb-528">Combinazione di lettere e numeri di otto o nove caratteri:</span><span class="sxs-lookup"><span data-stu-id="d2ffb-528">An eight- or nine-character combination of letters and numbers:</span></span>
  
-  <span data-ttu-id="d2ffb-529">Due cifre o lettere</span><span class="sxs-lookup"><span data-stu-id="d2ffb-529">Two digits or letters</span></span> 
    
- <span data-ttu-id="d2ffb-530">Una cifra o una lettera (facoltativa)</span><span class="sxs-lookup"><span data-stu-id="d2ffb-530">One digit or letter (optional)</span></span>
    
- <span data-ttu-id="d2ffb-531">Sei cifre</span><span class="sxs-lookup"><span data-stu-id="d2ffb-531">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="d2ffb-532">Checksum</span><span class="sxs-lookup"><span data-stu-id="d2ffb-532">Checksum</span></span>

<span data-ttu-id="d2ffb-533">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="d2ffb-533">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="d2ffb-534">Definizione</span><span class="sxs-lookup"><span data-stu-id="d2ffb-534">Definition</span></span>

<span data-ttu-id="d2ffb-535">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="d2ffb-535">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="d2ffb-536">L'espressione `Regex_spain_eu_passport_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="d2ffb-536">The regular expression  `Regex_spain_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="d2ffb-537">Viene trovata una `Keywords_spain_eu_passport_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="d2ffb-537">A keyword from  `Keywords_spain_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_spain_eu_passport_number" />
          <Match idRef="Keywords_spain_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="d2ffb-538">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="d2ffb-538">Keywords</span></span>

<span data-ttu-id="d2ffb-539">| |</span><span class="sxs-lookup"><span data-stu-id="d2ffb-539"></span></span>
|<span data-ttu-id="d2ffb-540">**Keywords_spain_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="d2ffb-540">**Keywords_spain_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="d2ffb-541">passaporto</span><span class="sxs-lookup"><span data-stu-id="d2ffb-541">passport</span></span>  <br/> <span data-ttu-id="d2ffb-542">passaporto della Spagna</span><span class="sxs-lookup"><span data-stu-id="d2ffb-542">spain passport</span></span>  <br/> <span data-ttu-id="d2ffb-543">libro del passaporto</span><span class="sxs-lookup"><span data-stu-id="d2ffb-543">passport book</span></span>  <br/> <span data-ttu-id="d2ffb-544">passport number</span><span class="sxs-lookup"><span data-stu-id="d2ffb-544">passport number</span></span>  <br/> <span data-ttu-id="d2ffb-545">Passport No</span><span class="sxs-lookup"><span data-stu-id="d2ffb-545">passport no</span></span>  <br/> <span data-ttu-id="d2ffb-546">libreta pasaporte</span><span class="sxs-lookup"><span data-stu-id="d2ffb-546">libreta pasaporte</span></span>  <br/> <span data-ttu-id="d2ffb-547">número pasaporte</span><span class="sxs-lookup"><span data-stu-id="d2ffb-547">número pasaporte</span></span>  <br/> <span data-ttu-id="d2ffb-548">pasaporte España</span><span class="sxs-lookup"><span data-stu-id="d2ffb-548">españa pasaporte</span></span>  <br/> <span data-ttu-id="d2ffb-549">pasaporte</span><span class="sxs-lookup"><span data-stu-id="d2ffb-549">pasaporte</span></span>  <br/> |
   
## <a name="sweden"></a><span data-ttu-id="d2ffb-550">Svezia</span><span class="sxs-lookup"><span data-stu-id="d2ffb-550">Sweden</span></span>

<span data-ttu-id="d2ffb-551">Per informazioni dettagliate, vedere la sezione "Sweden Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="d2ffb-551">For details, see the section "Sweden Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="uk"></a><span data-ttu-id="d2ffb-552">Regno Unito</span><span class="sxs-lookup"><span data-stu-id="d2ffb-552">UK</span></span>

<span data-ttu-id="d2ffb-553">Per informazioni dettagliate, vedere la sezione "Stati Uniti/Regno Unito</span><span class="sxs-lookup"><span data-stu-id="d2ffb-553">For details, see the section "U.S. / U.K.</span></span> <span data-ttu-id="d2ffb-554">Numero di passaporto "in [quello che cercano i tipi di informazioni riservate](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="d2ffb-554">Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="d2ffb-555">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d2ffb-555">See also</span></span>

[<span data-ttu-id="d2ffb-556">Cosa individuano le tipologie di informazioni sensibili</span><span class="sxs-lookup"><span data-stu-id="d2ffb-556">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)

