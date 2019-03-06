---
title: Numero di passaporto EU
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 8/16/2018
ms.audience: Admin
ms.topic: reference
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
description: In questo argomento viene illustrato l'aspetto di un criterio di prevenzione della perdita di dati (DLP) quando viene rilevato il tipo di informazioni riservate del numero di passaporto dell'Unione europea. Questo tipo di informazioni riservate definisce modelli, parole chiave e altre evidenze diverse per ogni paese.
ms.openlocfilehash: 3ab92e87607f41cffa8c15f1179a4eef5369cb29
ms.sourcegitcommit: ed822a776d3419853453583e882f3c61ca26d4b2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/05/2019
ms.locfileid: "30410931"
---
# <a name="eu-passport-number"></a><span data-ttu-id="151cf-104">Numero di passaporto EU</span><span class="sxs-lookup"><span data-stu-id="151cf-104">EU Passport Number</span></span>

<span data-ttu-id="151cf-105">In questo argomento viene illustrato l'aspetto di un criterio di prevenzione della perdita di dati (DLP) quando viene rilevato il tipo di informazioni riservate del numero di passaporto dell'Unione europea.</span><span class="sxs-lookup"><span data-stu-id="151cf-105">This topic shows what a data loss prevention (DLP) policy looks for when it detects the EU Passport Number sensitive information type.</span></span> <span data-ttu-id="151cf-106">Questo tipo di informazioni riservate definisce modelli, parole chiave e altre evidenze diverse per ogni paese.</span><span class="sxs-lookup"><span data-stu-id="151cf-106">This sensitive information type defines different patterns, keywords, and other evidence for each country.</span></span>
  
## <a name="austria"></a><span data-ttu-id="151cf-107">Austria</span><span class="sxs-lookup"><span data-stu-id="151cf-107">Austria</span></span>

### <a name="format"></a><span data-ttu-id="151cf-108">Formato</span><span class="sxs-lookup"><span data-stu-id="151cf-108">Format</span></span>

<span data-ttu-id="151cf-109">Una lettera seguita da uno spazio facoltativo e sette cifre</span><span class="sxs-lookup"><span data-stu-id="151cf-109">One letter followed by an optional space and seven digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="151cf-110">Modello</span><span class="sxs-lookup"><span data-stu-id="151cf-110">Pattern</span></span>

<span data-ttu-id="151cf-111">Combinazione di una lettera, sette cifre e uno spazio:</span><span class="sxs-lookup"><span data-stu-id="151cf-111">A combination of one letter, seven digits, and one space:</span></span>
  
- <span data-ttu-id="151cf-112">Una lettera (senza distinzione tra maiuscole/minuscole)</span><span class="sxs-lookup"><span data-stu-id="151cf-112">One letter (not case sensitive)</span></span>
    
- <span data-ttu-id="151cf-113">Uno spazio (facoltativo)</span><span class="sxs-lookup"><span data-stu-id="151cf-113">One space (optional)</span></span>
    
- <span data-ttu-id="151cf-114">Sette cifre</span><span class="sxs-lookup"><span data-stu-id="151cf-114">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="151cf-115">Checksum</span><span class="sxs-lookup"><span data-stu-id="151cf-115">Checksum</span></span>

<span data-ttu-id="151cf-116">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="151cf-116">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="151cf-117">Definizione</span><span class="sxs-lookup"><span data-stu-id="151cf-117">Definition</span></span>

<span data-ttu-id="151cf-118">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="151cf-118">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="151cf-119">L'espressione `Regex_austria_eu_passport_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="151cf-119">The regular expression  `Regex_austria_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="151cf-120">Viene trovata una `Keywords_austria_eu_passport_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="151cf-120">A keyword from  `Keywords_austria_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_austria_eu_passport_number" />
          <Match idRef="Keywords_austria_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="151cf-121">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="151cf-121">Keywords</span></span>

<span data-ttu-id="151cf-122">| |</span><span class="sxs-lookup"><span data-stu-id="151cf-122"></span></span>
|<span data-ttu-id="151cf-123">**Keywords_austria_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="151cf-123">**Keywords_austria_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="151cf-124">passport number</span><span class="sxs-lookup"><span data-stu-id="151cf-124">passport number</span></span>  <br/> <span data-ttu-id="151cf-125">numero di passaporto austriaco</span><span class="sxs-lookup"><span data-stu-id="151cf-125">austrian passport number</span></span>  <br/> <span data-ttu-id="151cf-126">Passport No</span><span class="sxs-lookup"><span data-stu-id="151cf-126">passport no</span></span>  <br/> <span data-ttu-id="151cf-127">Reisepass</span><span class="sxs-lookup"><span data-stu-id="151cf-127">reisepass</span></span>  <br/> <span data-ttu-id="151cf-128">Österreichisch Reisepass</span><span class="sxs-lookup"><span data-stu-id="151cf-128">österreichisch reisepass</span></span>  <br/> |
   
## <a name="belgium"></a><span data-ttu-id="151cf-129">Belgio</span><span class="sxs-lookup"><span data-stu-id="151cf-129">Belgium</span></span>

### <a name="format"></a><span data-ttu-id="151cf-130">Formato</span><span class="sxs-lookup"><span data-stu-id="151cf-130">Format</span></span>

<span data-ttu-id="151cf-131">Due lettere seguite da sei cifre senza spazi o delimitatori</span><span class="sxs-lookup"><span data-stu-id="151cf-131">Two letters followed by six digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="151cf-132">Modello</span><span class="sxs-lookup"><span data-stu-id="151cf-132">Pattern</span></span>

<span data-ttu-id="151cf-133">Due lettere e seguite da sei cifre</span><span class="sxs-lookup"><span data-stu-id="151cf-133">Two letters and followed by six digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="151cf-134">Checksum</span><span class="sxs-lookup"><span data-stu-id="151cf-134">Checksum</span></span>

<span data-ttu-id="151cf-135">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="151cf-135">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="151cf-136">Definizione</span><span class="sxs-lookup"><span data-stu-id="151cf-136">Definition</span></span>

<span data-ttu-id="151cf-137">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="151cf-137">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="151cf-138">L'espressione `Regex_belgium_eu_passport_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="151cf-138">The regular expression  `Regex_belgium_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="151cf-139">Viene trovata una `Keywords_belgium_eu_passport_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="151cf-139">A keyword from  `Keywords_belgium_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_belgium__eu_passport_number" />
          <Match idRef="Keywords_belgium_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="151cf-140">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="151cf-140">Keywords</span></span>

<span data-ttu-id="151cf-141">| |</span><span class="sxs-lookup"><span data-stu-id="151cf-141"></span></span>
|<span data-ttu-id="151cf-142">**Keywords_belgium_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="151cf-142">**Keywords_belgium_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="151cf-143">passport number</span><span class="sxs-lookup"><span data-stu-id="151cf-143">passport number</span></span>  <br/> <span data-ttu-id="151cf-144">numero di passaporto belga</span><span class="sxs-lookup"><span data-stu-id="151cf-144">belgian passport number</span></span>  <br/> <span data-ttu-id="151cf-145">Passport No</span><span class="sxs-lookup"><span data-stu-id="151cf-145">passport no</span></span>  <br/> <span data-ttu-id="151cf-146">PASPOORT</span><span class="sxs-lookup"><span data-stu-id="151cf-146">paspoort</span></span>  <br/> <span data-ttu-id="151cf-147">paspoortnummer</span><span class="sxs-lookup"><span data-stu-id="151cf-147">paspoortnummer</span></span>  <br/> <span data-ttu-id="151cf-148">Reisepass kein</span><span class="sxs-lookup"><span data-stu-id="151cf-148">reisepass kein</span></span>  <br/> <span data-ttu-id="151cf-149">Reisepass</span><span class="sxs-lookup"><span data-stu-id="151cf-149">reisepass</span></span>  <br/> |
   
## <a name="bulgaria"></a><span data-ttu-id="151cf-150">Bulgaria</span><span class="sxs-lookup"><span data-stu-id="151cf-150">Bulgaria</span></span>

### <a name="format"></a><span data-ttu-id="151cf-151">Formato</span><span class="sxs-lookup"><span data-stu-id="151cf-151">Format</span></span>

<span data-ttu-id="151cf-152">Nove cifre senza spazi e delimitatori</span><span class="sxs-lookup"><span data-stu-id="151cf-152">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="151cf-153">Modello</span><span class="sxs-lookup"><span data-stu-id="151cf-153">Pattern</span></span>

 <span data-ttu-id="151cf-154">9 cifre</span><span class="sxs-lookup"><span data-stu-id="151cf-154">Nine digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="151cf-155">Checksum</span><span class="sxs-lookup"><span data-stu-id="151cf-155">Checksum</span></span>

<span data-ttu-id="151cf-156">No</span><span class="sxs-lookup"><span data-stu-id="151cf-156">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="151cf-157">Definizione</span><span class="sxs-lookup"><span data-stu-id="151cf-157">Definition</span></span>

<span data-ttu-id="151cf-158">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="151cf-158">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="151cf-159">L'espressione `Regex_bulgaria_eu_passport_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="151cf-159">The regular expression  `Regex_bulgaria_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="151cf-160">Viene trovata una `Keywords_bulgaria_eu_passport_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="151cf-160">A keyword from  `Keywords_bulgaria_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_bulgaria_eu_passport_number" />
          <Match idRef="Keywords_bulgaria_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="151cf-161">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="151cf-161">Keywords</span></span>

<span data-ttu-id="151cf-162">| |</span><span class="sxs-lookup"><span data-stu-id="151cf-162"></span></span>
|<span data-ttu-id="151cf-163">**Keywords_bulgaria_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="151cf-163">**Keywords_bulgaria_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="151cf-164">passport number</span><span class="sxs-lookup"><span data-stu-id="151cf-164">passport number</span></span>  <br/> <span data-ttu-id="151cf-165">numero di passaporto bulgaro</span><span class="sxs-lookup"><span data-stu-id="151cf-165">bulgarian passport number</span></span>  <br/> <span data-ttu-id="151cf-166">Passport No</span><span class="sxs-lookup"><span data-stu-id="151cf-166">passport no</span></span>  <br/> <span data-ttu-id="151cf-167">Номер на паспорта</span><span class="sxs-lookup"><span data-stu-id="151cf-167">номер на паспорта</span></span>  <br/> |
   
## <a name="croatia"></a><span data-ttu-id="151cf-168">Croazia</span><span class="sxs-lookup"><span data-stu-id="151cf-168">Croatia</span></span>

### <a name="format"></a><span data-ttu-id="151cf-169">Formato</span><span class="sxs-lookup"><span data-stu-id="151cf-169">Format</span></span>

<span data-ttu-id="151cf-170">Nove cifre senza spazi e delimitatori</span><span class="sxs-lookup"><span data-stu-id="151cf-170">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="151cf-171">Modello</span><span class="sxs-lookup"><span data-stu-id="151cf-171">Pattern</span></span>

 <span data-ttu-id="151cf-172">9 cifre</span><span class="sxs-lookup"><span data-stu-id="151cf-172">Nine digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="151cf-173">Checksum</span><span class="sxs-lookup"><span data-stu-id="151cf-173">Checksum</span></span>

<span data-ttu-id="151cf-174">No</span><span class="sxs-lookup"><span data-stu-id="151cf-174">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="151cf-175">Definizione</span><span class="sxs-lookup"><span data-stu-id="151cf-175">Definition</span></span>

<span data-ttu-id="151cf-176">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="151cf-176">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="151cf-177">L'espressione `Regex_croatia_eu_passport_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="151cf-177">The regular expression  `Regex_croatia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="151cf-178">Viene trovata una `Keywords_croatia_eu_passport_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="151cf-178">A keyword from  `Keywords_croatia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_croatia_eu_passport_number" />
          <Match idRef="Keywords_croatia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="151cf-179">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="151cf-179">Keywords</span></span>

<span data-ttu-id="151cf-180">| |</span><span class="sxs-lookup"><span data-stu-id="151cf-180"></span></span>
|<span data-ttu-id="151cf-181">**Keywords_croatia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="151cf-181">**Keywords_croatia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="151cf-182">passport number</span><span class="sxs-lookup"><span data-stu-id="151cf-182">passport number</span></span>  <br/> <span data-ttu-id="151cf-183">numero di passaporto croato</span><span class="sxs-lookup"><span data-stu-id="151cf-183">croatian passport number</span></span>  <br/> <span data-ttu-id="151cf-184">Passport No</span><span class="sxs-lookup"><span data-stu-id="151cf-184">passport no</span></span>  <br/> <span data-ttu-id="151cf-185">broj putovnice</span><span class="sxs-lookup"><span data-stu-id="151cf-185">broj putovnice</span></span>  <br/> |
   
## <a name="cyprus"></a><span data-ttu-id="151cf-186">Cipro</span><span class="sxs-lookup"><span data-stu-id="151cf-186">Cyprus</span></span>

### <a name="format"></a><span data-ttu-id="151cf-187">Formato</span><span class="sxs-lookup"><span data-stu-id="151cf-187">Format</span></span>

<span data-ttu-id="151cf-188">Una lettera seguita da 6-8 cifre senza spazi o delimitatori</span><span class="sxs-lookup"><span data-stu-id="151cf-188">One letter followed by 6-8 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="151cf-189">Modello</span><span class="sxs-lookup"><span data-stu-id="151cf-189">Pattern</span></span>

<span data-ttu-id="151cf-190">Una lettera seguita da sei a otto cifre</span><span class="sxs-lookup"><span data-stu-id="151cf-190">One letter followed by six to eight digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="151cf-191">Checksum</span><span class="sxs-lookup"><span data-stu-id="151cf-191">Checksum</span></span>

<span data-ttu-id="151cf-192">No</span><span class="sxs-lookup"><span data-stu-id="151cf-192">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="151cf-193">Definizione</span><span class="sxs-lookup"><span data-stu-id="151cf-193">Definition</span></span>

<span data-ttu-id="151cf-194">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="151cf-194">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="151cf-195">L'espressione `Regex_cyprus_eu_passport_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="151cf-195">The regular expression  `Regex_cyprus_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="151cf-196">Viene trovata una `Keywords_cyprus_eu_passport_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="151cf-196">A keyword from  `Keywords_cyprus_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_cyprus_eu_passport_number" />
          <Match idRef="Keywords_cyprus_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="151cf-197">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="151cf-197">Keywords</span></span>

<span data-ttu-id="151cf-198">| |</span><span class="sxs-lookup"><span data-stu-id="151cf-198"></span></span>
|<span data-ttu-id="151cf-199">**Keywords_cyprus_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="151cf-199">**Keywords_cyprus_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="151cf-200">passport number</span><span class="sxs-lookup"><span data-stu-id="151cf-200">passport number</span></span>  <br/> <span data-ttu-id="151cf-201">numero di passaporto di Cipro</span><span class="sxs-lookup"><span data-stu-id="151cf-201">cyprus passport number</span></span>  <br/> <span data-ttu-id="151cf-202">Passport No</span><span class="sxs-lookup"><span data-stu-id="151cf-202">passport no</span></span>  <br/> <span data-ttu-id="151cf-203">αριθμό διαβατηρίου</span><span class="sxs-lookup"><span data-stu-id="151cf-203">αριθμό διαβατηρίου</span></span>  <br/> |
   
## <a name="czech-republic"></a><span data-ttu-id="151cf-204">Repubblica Ceca</span><span class="sxs-lookup"><span data-stu-id="151cf-204">Czech Republic</span></span>

### <a name="format"></a><span data-ttu-id="151cf-205">Formato</span><span class="sxs-lookup"><span data-stu-id="151cf-205">Format</span></span>

<span data-ttu-id="151cf-206">Otto cifre senza spazi o delimitatori</span><span class="sxs-lookup"><span data-stu-id="151cf-206">Eight digits without spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="151cf-207">Modello</span><span class="sxs-lookup"><span data-stu-id="151cf-207">Pattern</span></span>

<span data-ttu-id="151cf-208">Otto cifre senza spazi o delimitatori</span><span class="sxs-lookup"><span data-stu-id="151cf-208">Eight digits without spaces or delimiters</span></span>
  
### <a name="checksum"></a><span data-ttu-id="151cf-209">Checksum</span><span class="sxs-lookup"><span data-stu-id="151cf-209">Checksum</span></span>

<span data-ttu-id="151cf-210">No</span><span class="sxs-lookup"><span data-stu-id="151cf-210">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="151cf-211">Definizione</span><span class="sxs-lookup"><span data-stu-id="151cf-211">Definition</span></span>

<span data-ttu-id="151cf-212">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="151cf-212">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="151cf-213">L'espressione `Regex_czech_republic_eu_passport_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="151cf-213">The regular expression  `Regex_czech_republic_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="151cf-214">Viene trovata una `Keywords_czech_republic_eu_passport_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="151cf-214">A keyword from  `Keywords_czech_republic_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_czech_republic_eu_passport_number" />
          <Match idRef="Keywords_czech_republic_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="151cf-215">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="151cf-215">Keywords</span></span>

<span data-ttu-id="151cf-216">| |</span><span class="sxs-lookup"><span data-stu-id="151cf-216"></span></span>
|<span data-ttu-id="151cf-217">**Keywords_czech_republic_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="151cf-217">**Keywords_czech_republic_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="151cf-218">passport number</span><span class="sxs-lookup"><span data-stu-id="151cf-218">passport number</span></span>  <br/> <span data-ttu-id="151cf-219">numero di passaporto ceco</span><span class="sxs-lookup"><span data-stu-id="151cf-219">czech passport number</span></span>  <br/> <span data-ttu-id="151cf-220">Passport No</span><span class="sxs-lookup"><span data-stu-id="151cf-220">passport no</span></span>  <br/> <span data-ttu-id="151cf-221">Cestovní pas</span><span class="sxs-lookup"><span data-stu-id="151cf-221">cestovní pas</span></span>  <br/> <span data-ttu-id="151cf-222">pas</span><span class="sxs-lookup"><span data-stu-id="151cf-222">pas</span></span>  <br/> |
   
## <a name="denmark"></a><span data-ttu-id="151cf-223">Danimarca</span><span class="sxs-lookup"><span data-stu-id="151cf-223">Denmark</span></span>

### <a name="format"></a><span data-ttu-id="151cf-224">Formato</span><span class="sxs-lookup"><span data-stu-id="151cf-224">Format</span></span>

<span data-ttu-id="151cf-225">Nove cifre senza spazi e delimitatori</span><span class="sxs-lookup"><span data-stu-id="151cf-225">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="151cf-226">Modello</span><span class="sxs-lookup"><span data-stu-id="151cf-226">Pattern</span></span>

 <span data-ttu-id="151cf-227">9 cifre</span><span class="sxs-lookup"><span data-stu-id="151cf-227">Nine digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="151cf-228">Checksum</span><span class="sxs-lookup"><span data-stu-id="151cf-228">Checksum</span></span>

<span data-ttu-id="151cf-229">No</span><span class="sxs-lookup"><span data-stu-id="151cf-229">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="151cf-230">Definizione</span><span class="sxs-lookup"><span data-stu-id="151cf-230">Definition</span></span>

<span data-ttu-id="151cf-231">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="151cf-231">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="151cf-232">L'espressione `Regex_denmark_eu_passport_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="151cf-232">The regular expression  `Regex_denmark_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="151cf-233">Viene trovata una `Keywords_denmark_eu_passport_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="151cf-233">A keyword from  `Keywords_denmark_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_denmark_eu_passport_number" />
          <Match idRef="Keywords_denmark_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="151cf-234">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="151cf-234">Keywords</span></span>

<span data-ttu-id="151cf-235">| |</span><span class="sxs-lookup"><span data-stu-id="151cf-235"></span></span>
|<span data-ttu-id="151cf-236">**Keywords_denmark_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="151cf-236">**Keywords_denmark_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="151cf-237">passport number</span><span class="sxs-lookup"><span data-stu-id="151cf-237">passport number</span></span>  <br/> <span data-ttu-id="151cf-238">numero di passaporto danese</span><span class="sxs-lookup"><span data-stu-id="151cf-238">danish passport number</span></span>  <br/> <span data-ttu-id="151cf-239">Passport No</span><span class="sxs-lookup"><span data-stu-id="151cf-239">passport no</span></span>  <br/> <span data-ttu-id="151cf-240">pas</span><span class="sxs-lookup"><span data-stu-id="151cf-240">pas</span></span>  <br/> <span data-ttu-id="151cf-241">Pasnummer</span><span class="sxs-lookup"><span data-stu-id="151cf-241">pasnummer</span></span>  <br/> |
   
## <a name="estonia"></a><span data-ttu-id="151cf-242">Estonia</span><span class="sxs-lookup"><span data-stu-id="151cf-242">Estonia</span></span>

### <a name="format"></a><span data-ttu-id="151cf-243">Formato</span><span class="sxs-lookup"><span data-stu-id="151cf-243">Format</span></span>

<span data-ttu-id="151cf-244">Una lettera seguita da sette cifre senza spazi o delimitatori</span><span class="sxs-lookup"><span data-stu-id="151cf-244">One letter followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="151cf-245">Modello</span><span class="sxs-lookup"><span data-stu-id="151cf-245">Pattern</span></span>

<span data-ttu-id="151cf-246">Una lettera seguita da sette cifre</span><span class="sxs-lookup"><span data-stu-id="151cf-246">One letter followed by seven digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="151cf-247">Checksum</span><span class="sxs-lookup"><span data-stu-id="151cf-247">Checksum</span></span>

<span data-ttu-id="151cf-248">No</span><span class="sxs-lookup"><span data-stu-id="151cf-248">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="151cf-249">Definizione</span><span class="sxs-lookup"><span data-stu-id="151cf-249">Definition</span></span>

<span data-ttu-id="151cf-250">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="151cf-250">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="151cf-251">L'espressione `Regex_estonia_eu_passport_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="151cf-251">The regular expression  `Regex_estonia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="151cf-252">Viene trovata una `Keywords_estonia_eu_passport_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="151cf-252">A keyword from  `Keywords_estonia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_estonia_eu_passport_number" />
          <Match idRef="Keywords_estonia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="151cf-253">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="151cf-253">Keywords</span></span>

<span data-ttu-id="151cf-254">| |</span><span class="sxs-lookup"><span data-stu-id="151cf-254"></span></span>
|<span data-ttu-id="151cf-255">**Keywords_estonia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="151cf-255">**Keywords_estonia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="151cf-256">passport number</span><span class="sxs-lookup"><span data-stu-id="151cf-256">passport number</span></span>  <br/> <span data-ttu-id="151cf-257">numero di passaporto estone</span><span class="sxs-lookup"><span data-stu-id="151cf-257">estonian passport number</span></span>  <br/> <span data-ttu-id="151cf-258">Passport No</span><span class="sxs-lookup"><span data-stu-id="151cf-258">passport no</span></span>  <br/> <span data-ttu-id="151cf-259">passaggio kodaniku Eesti</span><span class="sxs-lookup"><span data-stu-id="151cf-259">eesti kodaniku pass</span></span>  <br/> |
   
## <a name="finland"></a><span data-ttu-id="151cf-260">Finlandia</span><span class="sxs-lookup"><span data-stu-id="151cf-260">Finland</span></span>

<span data-ttu-id="151cf-261">Per informazioni dettagliate, vedere la sezione "Finlandia Passport Number" in [che cosa cercano i tipi di informazioni riservate](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="151cf-261">For details, see the section "Finland Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="france"></a><span data-ttu-id="151cf-262">Francia</span><span class="sxs-lookup"><span data-stu-id="151cf-262">France</span></span>

<span data-ttu-id="151cf-263">Per informazioni dettagliate, vedere la sezione "Francia Passport Number" in [che cosa cercano i tipi di informazioni riservate](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="151cf-263">For details, see the section "France Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="germany"></a><span data-ttu-id="151cf-264">Germania</span><span class="sxs-lookup"><span data-stu-id="151cf-264">Germany</span></span>

<span data-ttu-id="151cf-265">Per informazioni dettagliate, vedere la sezione "Germania Passport Number" in [che cosa cercano i tipi di informazioni riservate](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="151cf-265">For details, see the section "Germany Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="greece"></a><span data-ttu-id="151cf-266">Grecia</span><span class="sxs-lookup"><span data-stu-id="151cf-266">Greece</span></span>

### <a name="format"></a><span data-ttu-id="151cf-267">Formato</span><span class="sxs-lookup"><span data-stu-id="151cf-267">Format</span></span>

<span data-ttu-id="151cf-268">Due lettere seguite da sette cifre senza spazi o delimitatori</span><span class="sxs-lookup"><span data-stu-id="151cf-268">Two letters followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="151cf-269">Modello</span><span class="sxs-lookup"><span data-stu-id="151cf-269">Pattern</span></span>

<span data-ttu-id="151cf-270">Due lettere seguite da 7 cifre</span><span class="sxs-lookup"><span data-stu-id="151cf-270">Two letters followed by seven digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="151cf-271">Checksum</span><span class="sxs-lookup"><span data-stu-id="151cf-271">Checksum</span></span>

<span data-ttu-id="151cf-272">No</span><span class="sxs-lookup"><span data-stu-id="151cf-272">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="151cf-273">Definizione</span><span class="sxs-lookup"><span data-stu-id="151cf-273">Definition</span></span>

<span data-ttu-id="151cf-274">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="151cf-274">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="151cf-275">L'espressione `Regex_greece_eu_passport_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="151cf-275">The regular expression  `Regex_greece_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="151cf-276">Viene trovata una `Keywords_greece_eu_passport_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="151cf-276">A keyword from  `Keywords_greece_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_greece_eu_passport_number" />
          <Match idRef="Keywords_greece_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="151cf-277">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="151cf-277">Keywords</span></span>

<span data-ttu-id="151cf-278">| |</span><span class="sxs-lookup"><span data-stu-id="151cf-278"></span></span>
|<span data-ttu-id="151cf-279">**Keywords_greece_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="151cf-279">**Keywords_greece_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="151cf-280">passport number</span><span class="sxs-lookup"><span data-stu-id="151cf-280">passport number</span></span>  <br/> <span data-ttu-id="151cf-281">numero di passaporto greco</span><span class="sxs-lookup"><span data-stu-id="151cf-281">greek passport number</span></span>  <br/> <span data-ttu-id="151cf-282">Passport No</span><span class="sxs-lookup"><span data-stu-id="151cf-282">passport no</span></span>  <br/> <span data-ttu-id="151cf-283">διαβατηριο</span><span class="sxs-lookup"><span data-stu-id="151cf-283">διαβατηριο</span></span>  <br/> |
   
## <a name="hungary"></a><span data-ttu-id="151cf-284">Ungheria</span><span class="sxs-lookup"><span data-stu-id="151cf-284">Hungary</span></span>

### <a name="format"></a><span data-ttu-id="151cf-285">Formato</span><span class="sxs-lookup"><span data-stu-id="151cf-285">Format</span></span>

<span data-ttu-id="151cf-286">Due lettere seguite da sei o sette cifre senza spazi o delimitatori</span><span class="sxs-lookup"><span data-stu-id="151cf-286">Two letters followed by six or seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="151cf-287">Modello</span><span class="sxs-lookup"><span data-stu-id="151cf-287">Pattern</span></span>

<span data-ttu-id="151cf-288">Due lettere seguite da sei o sette cifre</span><span class="sxs-lookup"><span data-stu-id="151cf-288">Two letters followed by six or seven digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="151cf-289">Checksum</span><span class="sxs-lookup"><span data-stu-id="151cf-289">Checksum</span></span>

<span data-ttu-id="151cf-290">No</span><span class="sxs-lookup"><span data-stu-id="151cf-290">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="151cf-291">Definizione</span><span class="sxs-lookup"><span data-stu-id="151cf-291">Definition</span></span>

<span data-ttu-id="151cf-292">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="151cf-292">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="151cf-293">L'espressione `Regex_hungary_eu_passport_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="151cf-293">The regular expression  `Regex_hungary_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="151cf-294">Viene trovata una `Keywords_hungary_eu_passport_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="151cf-294">A keyword from  `Keywords_hungary_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_hungary_eu_passport_number" />
          <Match idRef="Keywords_hungary_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="151cf-295">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="151cf-295">Keywords</span></span>

<span data-ttu-id="151cf-296">| |</span><span class="sxs-lookup"><span data-stu-id="151cf-296"></span></span>
|<span data-ttu-id="151cf-297">**Keywords_hungary_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="151cf-297">**Keywords_hungary_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="151cf-298">passport number</span><span class="sxs-lookup"><span data-stu-id="151cf-298">passport number</span></span>  <br/> <span data-ttu-id="151cf-299">numero di passaporto ungherese</span><span class="sxs-lookup"><span data-stu-id="151cf-299">hungarian passport number</span></span>  <br/> <span data-ttu-id="151cf-300">Passport No</span><span class="sxs-lookup"><span data-stu-id="151cf-300">passport no</span></span>  <br/> <span data-ttu-id="151cf-301">útlevél száma</span><span class="sxs-lookup"><span data-stu-id="151cf-301">útlevél száma</span></span>  <br/> |
   
## <a name="ireland"></a><span data-ttu-id="151cf-302">Irlanda</span><span class="sxs-lookup"><span data-stu-id="151cf-302">Ireland</span></span>

### <a name="format"></a><span data-ttu-id="151cf-303">Formato</span><span class="sxs-lookup"><span data-stu-id="151cf-303">Format</span></span>

<span data-ttu-id="151cf-304">Due lettere o cifre seguite da sette cifre senza spazi o delimitatori</span><span class="sxs-lookup"><span data-stu-id="151cf-304">Two letters or digits followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="151cf-305">Modello</span><span class="sxs-lookup"><span data-stu-id="151cf-305">Pattern</span></span>

<span data-ttu-id="151cf-306">Due lettere o cifre seguite da sette cifre:</span><span class="sxs-lookup"><span data-stu-id="151cf-306">Two letters or digits followed by seven digits:</span></span>
  
- <span data-ttu-id="151cf-307">Due cifre o lettere (senza distinzione tra maiuscole/minuscole)</span><span class="sxs-lookup"><span data-stu-id="151cf-307">Two digits or letters (not case sensitive)</span></span>
    
- <span data-ttu-id="151cf-308">Sette cifre</span><span class="sxs-lookup"><span data-stu-id="151cf-308">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="151cf-309">Checksum</span><span class="sxs-lookup"><span data-stu-id="151cf-309">Checksum</span></span>

<span data-ttu-id="151cf-310">No</span><span class="sxs-lookup"><span data-stu-id="151cf-310">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="151cf-311">Definizione</span><span class="sxs-lookup"><span data-stu-id="151cf-311">Definition</span></span>

<span data-ttu-id="151cf-312">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="151cf-312">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="151cf-313">L'espressione `Regex_ireland_eu_passport_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="151cf-313">The regular expression  `Regex_ireland_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="151cf-314">Viene trovata una `Keywords_ireland_eu_passport_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="151cf-314">A keyword from  `Keywords_ireland_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_ireland_eu_passport_number" />
          <Match idRef="Keywords_ireland_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="151cf-315">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="151cf-315">Keywords</span></span>

<span data-ttu-id="151cf-316">| |</span><span class="sxs-lookup"><span data-stu-id="151cf-316"></span></span>
|<span data-ttu-id="151cf-317">**Keywords_ireland_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="151cf-317">**Keywords_ireland_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="151cf-318">passport number</span><span class="sxs-lookup"><span data-stu-id="151cf-318">passport number</span></span>  <br/> <span data-ttu-id="151cf-319">numero di passaporto irlandese</span><span class="sxs-lookup"><span data-stu-id="151cf-319">irish passport number</span></span>  <br/> <span data-ttu-id="151cf-320">Passport No</span><span class="sxs-lookup"><span data-stu-id="151cf-320">passport no</span></span>  <br/> <span data-ttu-id="151cf-321">pas</span><span class="sxs-lookup"><span data-stu-id="151cf-321">pas</span></span>  <br/> <span data-ttu-id="151cf-322">passaporto</span><span class="sxs-lookup"><span data-stu-id="151cf-322">passport</span></span>  <br/> <span data-ttu-id="151cf-323">Passeport</span><span class="sxs-lookup"><span data-stu-id="151cf-323">passeport</span></span>  <br/> <span data-ttu-id="151cf-324">numero Passeport</span><span class="sxs-lookup"><span data-stu-id="151cf-324">passeport numero</span></span>  <br/> |
   
## <a name="italy"></a><span data-ttu-id="151cf-325">Italia</span><span class="sxs-lookup"><span data-stu-id="151cf-325">Italy</span></span>

### <a name="format"></a><span data-ttu-id="151cf-326">Formato</span><span class="sxs-lookup"><span data-stu-id="151cf-326">Format</span></span>

<span data-ttu-id="151cf-327">Due lettere o cifre seguite da sette cifre senza spazi o delimitatori</span><span class="sxs-lookup"><span data-stu-id="151cf-327">Two letters or digits followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="151cf-328">Modello</span><span class="sxs-lookup"><span data-stu-id="151cf-328">Pattern</span></span>

<span data-ttu-id="151cf-329">Due lettere o cifre seguite da sette cifre:</span><span class="sxs-lookup"><span data-stu-id="151cf-329">Two letters or digits followed by seven digits:</span></span>
  
- <span data-ttu-id="151cf-330">Due cifre o lettere (senza distinzione tra maiuscole/minuscole)</span><span class="sxs-lookup"><span data-stu-id="151cf-330">Two digits or letters (not case sensitive)</span></span>
    
- <span data-ttu-id="151cf-331">Sette cifre</span><span class="sxs-lookup"><span data-stu-id="151cf-331">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="151cf-332">Checksum</span><span class="sxs-lookup"><span data-stu-id="151cf-332">Checksum</span></span>

<span data-ttu-id="151cf-333">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="151cf-333">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="151cf-334">Definizione</span><span class="sxs-lookup"><span data-stu-id="151cf-334">Definition</span></span>

<span data-ttu-id="151cf-335">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="151cf-335">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="151cf-336">L'espressione `Regex_italy_eu_passport_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="151cf-336">The regular expression  `Regex_italy_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="151cf-337">Viene trovata una `Keywords_italy_eu_passport_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="151cf-337">A keyword from  `Keywords_italy_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_italy_eu_passport_number" />
          <Match idRef="Keywords_italy_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="151cf-338">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="151cf-338">Keywords</span></span>

<span data-ttu-id="151cf-339">| |</span><span class="sxs-lookup"><span data-stu-id="151cf-339"></span></span>
|<span data-ttu-id="151cf-340">**Keywords_italy_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="151cf-340">**Keywords_italy_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="151cf-341">numero di passaporto italiano</span><span class="sxs-lookup"><span data-stu-id="151cf-341">italian passport number</span></span>  <br/> <span data-ttu-id="151cf-342">Repubblica italiana passaporto</span><span class="sxs-lookup"><span data-stu-id="151cf-342">repubblica italiana passaporto</span></span>  <br/> <span data-ttu-id="151cf-343">passaporto</span><span class="sxs-lookup"><span data-stu-id="151cf-343">passaporto</span></span>  <br/> <span data-ttu-id="151cf-344">passaporto italiana</span><span class="sxs-lookup"><span data-stu-id="151cf-344">passaporto italiana</span></span>  <br/> <span data-ttu-id="151cf-345">passport number</span><span class="sxs-lookup"><span data-stu-id="151cf-345">passport number</span></span>  <br/> <span data-ttu-id="151cf-346">italiana passaporto numero</span><span class="sxs-lookup"><span data-stu-id="151cf-346">italiana passaporto numero</span></span>  <br/> <span data-ttu-id="151cf-347">Numero passaporto</span><span class="sxs-lookup"><span data-stu-id="151cf-347">passaporto numero</span></span>  <br/> <span data-ttu-id="151cf-348">numéro Passeport Italien</span><span class="sxs-lookup"><span data-stu-id="151cf-348">numéro passeport italien</span></span>  <br/> <span data-ttu-id="151cf-349">numéro Passeport</span><span class="sxs-lookup"><span data-stu-id="151cf-349">numéro passeport</span></span>  <br/> |
   
## <a name="latvia"></a><span data-ttu-id="151cf-350">Lettonia</span><span class="sxs-lookup"><span data-stu-id="151cf-350">Latvia</span></span>

### <a name="format"></a><span data-ttu-id="151cf-351">Formato</span><span class="sxs-lookup"><span data-stu-id="151cf-351">Format</span></span>

<span data-ttu-id="151cf-352">Due lettere o cifre seguite da sette cifre senza spazi o delimitatori</span><span class="sxs-lookup"><span data-stu-id="151cf-352">Two letters or digits followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="151cf-353">Modello</span><span class="sxs-lookup"><span data-stu-id="151cf-353">Pattern</span></span>

<span data-ttu-id="151cf-354">Due lettere o cifre seguite da sette cifre:</span><span class="sxs-lookup"><span data-stu-id="151cf-354">Two letters or digits followed by seven digits:</span></span>
  
- <span data-ttu-id="151cf-355">Due cifre o lettere (senza distinzione tra maiuscole/minuscole)</span><span class="sxs-lookup"><span data-stu-id="151cf-355">Two digits or letters (not case sensitive)</span></span>
    
- <span data-ttu-id="151cf-356">Sette cifre</span><span class="sxs-lookup"><span data-stu-id="151cf-356">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="151cf-357">Checksum</span><span class="sxs-lookup"><span data-stu-id="151cf-357">Checksum</span></span>

<span data-ttu-id="151cf-358">No</span><span class="sxs-lookup"><span data-stu-id="151cf-358">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="151cf-359">Definizione</span><span class="sxs-lookup"><span data-stu-id="151cf-359">Definition</span></span>

<span data-ttu-id="151cf-360">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="151cf-360">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="151cf-361">L'espressione `Regex_latvia_eu_passport_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="151cf-361">The regular expression  `Regex_latvia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="151cf-362">Viene trovata una `Keywords_latvia_eu_passport_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="151cf-362">A keyword from  `Keywords_latvia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_latvia_eu_passport_number" />
          <Match idRef="Keywords_latvia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="151cf-363">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="151cf-363">Keywords</span></span>

<span data-ttu-id="151cf-364">| |</span><span class="sxs-lookup"><span data-stu-id="151cf-364"></span></span>
|<span data-ttu-id="151cf-365">**Keywords_latvia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="151cf-365">**Keywords_latvia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="151cf-366">passport number</span><span class="sxs-lookup"><span data-stu-id="151cf-366">passport number</span></span>  <br/> <span data-ttu-id="151cf-367">numero di passaporto lettone</span><span class="sxs-lookup"><span data-stu-id="151cf-367">latvian passport number</span></span>  <br/> <span data-ttu-id="151cf-368">Passport No</span><span class="sxs-lookup"><span data-stu-id="151cf-368">passport no</span></span>  <br/> <span data-ttu-id="151cf-369">pase numurs</span><span class="sxs-lookup"><span data-stu-id="151cf-369">pase numurs</span></span>  <br/> |
   
## <a name="lithuania"></a><span data-ttu-id="151cf-370">Lituania</span><span class="sxs-lookup"><span data-stu-id="151cf-370">Lithuania</span></span>

### <a name="format"></a><span data-ttu-id="151cf-371">Formato</span><span class="sxs-lookup"><span data-stu-id="151cf-371">Format</span></span>

<span data-ttu-id="151cf-372">Otto cifre o lettere senza spazi o delimitatori</span><span class="sxs-lookup"><span data-stu-id="151cf-372">Eight digits or letters with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="151cf-373">Modello</span><span class="sxs-lookup"><span data-stu-id="151cf-373">Pattern</span></span>

<span data-ttu-id="151cf-374">Otto cifre o lettere (senza distinzione tra maiuscole e minuscole)</span><span class="sxs-lookup"><span data-stu-id="151cf-374">Eight digits or letters (not case sensitive)</span></span>
  
### <a name="checksum"></a><span data-ttu-id="151cf-375">Checksum</span><span class="sxs-lookup"><span data-stu-id="151cf-375">Checksum</span></span>

<span data-ttu-id="151cf-376">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="151cf-376">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="151cf-377">Definizione</span><span class="sxs-lookup"><span data-stu-id="151cf-377">Definition</span></span>

<span data-ttu-id="151cf-378">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="151cf-378">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="151cf-379">L'espressione `Regex_lithuania_eu_passport_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="151cf-379">The regular expression  `Regex_lithuania_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="151cf-380">Viene trovata una `Keywords_lithuania_eu_passport_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="151cf-380">A keyword from  `Keywords_lithuania_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_lithuania_eu_passport_number" />
          <Match idRef="Keywords_lithuania_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="151cf-381">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="151cf-381">Keywords</span></span>

<span data-ttu-id="151cf-382">| |</span><span class="sxs-lookup"><span data-stu-id="151cf-382"></span></span>
|<span data-ttu-id="151cf-383">**Keywords_lithuania_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="151cf-383">**Keywords_lithuania_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="151cf-384">passport number</span><span class="sxs-lookup"><span data-stu-id="151cf-384">passport number</span></span>  <br/> <span data-ttu-id="151cf-385">numero di passaporto di lithunian</span><span class="sxs-lookup"><span data-stu-id="151cf-385">lithunian passport number</span></span>  <br/> <span data-ttu-id="151cf-386">Passport No</span><span class="sxs-lookup"><span data-stu-id="151cf-386">passport no</span></span>  <br/> <span data-ttu-id="151cf-387">numero di Paso</span><span class="sxs-lookup"><span data-stu-id="151cf-387">paso numeris</span></span>  <br/> |
   
## <a name="luxemburg"></a><span data-ttu-id="151cf-388">Lussemburgo</span><span class="sxs-lookup"><span data-stu-id="151cf-388">Luxemburg</span></span>

### <a name="format"></a><span data-ttu-id="151cf-389">Formato</span><span class="sxs-lookup"><span data-stu-id="151cf-389">Format</span></span>

<span data-ttu-id="151cf-390">Otto cifre o lettere senza spazi o delimitatori</span><span class="sxs-lookup"><span data-stu-id="151cf-390">Eight digits or letters with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="151cf-391">Modello</span><span class="sxs-lookup"><span data-stu-id="151cf-391">Pattern</span></span>

<span data-ttu-id="151cf-392">Otto cifre o lettere (senza distinzione tra maiuscole e minuscole)</span><span class="sxs-lookup"><span data-stu-id="151cf-392">Eight digits or letters (not case sensitive)</span></span>
  
### <a name="checksum"></a><span data-ttu-id="151cf-393">Checksum</span><span class="sxs-lookup"><span data-stu-id="151cf-393">Checksum</span></span>

<span data-ttu-id="151cf-394">No</span><span class="sxs-lookup"><span data-stu-id="151cf-394">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="151cf-395">Definizione</span><span class="sxs-lookup"><span data-stu-id="151cf-395">Definition</span></span>

<span data-ttu-id="151cf-396">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="151cf-396">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="151cf-397">L'espressione `Regex_nation_eu_passport_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="151cf-397">The regular expression  `Regex_nation_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="151cf-398">Viene trovata una `Keywords_nation_eu_passport_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="151cf-398">A keyword from  `Keywords_nation_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_nation_eu_passport_number" />
          <Match idRef="Keywords_nation_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="151cf-399">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="151cf-399">Keywords</span></span>

<span data-ttu-id="151cf-400">| |</span><span class="sxs-lookup"><span data-stu-id="151cf-400"></span></span>
|<span data-ttu-id="151cf-401">**Keywords_nation_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="151cf-401">**Keywords_nation_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="151cf-402">passport number</span><span class="sxs-lookup"><span data-stu-id="151cf-402">passport number</span></span>  <br/> <span data-ttu-id="151cf-403">numero di passaporto lettone</span><span class="sxs-lookup"><span data-stu-id="151cf-403">latvian passport number</span></span>  <br/> <span data-ttu-id="151cf-404">Passport No</span><span class="sxs-lookup"><span data-stu-id="151cf-404">passport no</span></span>  <br/> <span data-ttu-id="151cf-405">passnummer</span><span class="sxs-lookup"><span data-stu-id="151cf-405">passnummer</span></span>  <br/> |
   
## <a name="malta"></a><span data-ttu-id="151cf-406">Malta</span><span class="sxs-lookup"><span data-stu-id="151cf-406">Malta</span></span>

### <a name="format"></a><span data-ttu-id="151cf-407">Formato</span><span class="sxs-lookup"><span data-stu-id="151cf-407">Format</span></span>

<span data-ttu-id="151cf-408">Sette cifre senza spazi o delimitatori</span><span class="sxs-lookup"><span data-stu-id="151cf-408">Seven digits without spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="151cf-409">Modello</span><span class="sxs-lookup"><span data-stu-id="151cf-409">Pattern</span></span>

 <span data-ttu-id="151cf-410">Sette cifre</span><span class="sxs-lookup"><span data-stu-id="151cf-410">Seven digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="151cf-411">Checksum</span><span class="sxs-lookup"><span data-stu-id="151cf-411">Checksum</span></span>

<span data-ttu-id="151cf-412">No</span><span class="sxs-lookup"><span data-stu-id="151cf-412">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="151cf-413">Definizione</span><span class="sxs-lookup"><span data-stu-id="151cf-413">Definition</span></span>

<span data-ttu-id="151cf-414">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="151cf-414">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="151cf-415">L'espressione `Regex_malta_eu_passport_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="151cf-415">The regular expression  `Regex_malta_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="151cf-416">Viene trovata una `Keywords_malta_eu_passport_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="151cf-416">A keyword from  `Keywords_malta_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_malta_eu_passport_number" />
          <Match idRef="Keywords_malta_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="151cf-417">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="151cf-417">Keywords</span></span>

<span data-ttu-id="151cf-418">| |</span><span class="sxs-lookup"><span data-stu-id="151cf-418"></span></span>
|<span data-ttu-id="151cf-419">**Keywords_malta_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="151cf-419">**Keywords_malta_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="151cf-420">passport number</span><span class="sxs-lookup"><span data-stu-id="151cf-420">passport number</span></span>  <br/> <span data-ttu-id="151cf-421">numero di passaporto maltese</span><span class="sxs-lookup"><span data-stu-id="151cf-421">maltese passport number</span></span>  <br/> <span data-ttu-id="151cf-422">Passport No</span><span class="sxs-lookup"><span data-stu-id="151cf-422">passport no</span></span>  <br/> <span data-ttu-id="151cf-423">numru tal-passaport</span><span class="sxs-lookup"><span data-stu-id="151cf-423">numru tal-passaport</span></span>  <br/> |
   
## <a name="netherlands"></a><span data-ttu-id="151cf-424">Paesi Bassi</span><span class="sxs-lookup"><span data-stu-id="151cf-424">Netherlands</span></span>

### <a name="format"></a><span data-ttu-id="151cf-425">Formato</span><span class="sxs-lookup"><span data-stu-id="151cf-425">Format</span></span>

<span data-ttu-id="151cf-426">Nove lettere o cifre senza spazi o delimitatori</span><span class="sxs-lookup"><span data-stu-id="151cf-426">Nine letters or digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="151cf-427">Modello</span><span class="sxs-lookup"><span data-stu-id="151cf-427">Pattern</span></span>

<span data-ttu-id="151cf-428">Nove lettere o cifre</span><span class="sxs-lookup"><span data-stu-id="151cf-428">Nine letters or digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="151cf-429">Checksum</span><span class="sxs-lookup"><span data-stu-id="151cf-429">Checksum</span></span>

<span data-ttu-id="151cf-430">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="151cf-430">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="151cf-431">Definizione</span><span class="sxs-lookup"><span data-stu-id="151cf-431">Definition</span></span>

<span data-ttu-id="151cf-432">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="151cf-432">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="151cf-433">L'espressione `Regex_netherlands_eu_passport_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="151cf-433">The regular expression  `Regex_netherlands_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="151cf-434">Viene trovata una `Keywords_netherlands_eu_passport_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="151cf-434">A keyword from  `Keywords_netherlands_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_netherlands_eu_passport_number" />
          <Match idRef="Keywords_netherlands_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="151cf-435">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="151cf-435">Keywords</span></span>

<span data-ttu-id="151cf-436">| |</span><span class="sxs-lookup"><span data-stu-id="151cf-436"></span></span>
|<span data-ttu-id="151cf-437">**Keywords_netherlands_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="151cf-437">**Keywords_netherlands_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="151cf-438">numero di passaporto olandese</span><span class="sxs-lookup"><span data-stu-id="151cf-438">dutch passport number</span></span>  <br/> <span data-ttu-id="151cf-439">passport number</span><span class="sxs-lookup"><span data-stu-id="151cf-439">passport number</span></span>  <br/> <span data-ttu-id="151cf-440">numero di passaporto per i Paesi Bassi</span><span class="sxs-lookup"><span data-stu-id="151cf-440">netherlands passport number</span></span>  <br/> <span data-ttu-id="151cf-441">Nederlanden PASPOORT Nummer</span><span class="sxs-lookup"><span data-stu-id="151cf-441">nederlanden paspoort nummer</span></span>  <br/> <span data-ttu-id="151cf-442">PASPOORT</span><span class="sxs-lookup"><span data-stu-id="151cf-442">paspoort</span></span>  <br/> <span data-ttu-id="151cf-443">Nederlanden paspoortnummer</span><span class="sxs-lookup"><span data-stu-id="151cf-443">nederlanden paspoortnummer</span></span>  <br/> <span data-ttu-id="151cf-444">paspoortnummer</span><span class="sxs-lookup"><span data-stu-id="151cf-444">paspoortnummer</span></span>  <br/> |
   
## <a name="poland"></a><span data-ttu-id="151cf-445">Polonia</span><span class="sxs-lookup"><span data-stu-id="151cf-445">Poland</span></span>

<span data-ttu-id="151cf-446">Per informazioni dettagliate, vedere la sezione "Poland Passport Number" in [che cosa cercano i tipi di informazioni riservate](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="151cf-446">For details, see the section "Poland Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="portugal"></a><span data-ttu-id="151cf-447">Portogallo</span><span class="sxs-lookup"><span data-stu-id="151cf-447">Portugal</span></span>

### <a name="format"></a><span data-ttu-id="151cf-448">Formato</span><span class="sxs-lookup"><span data-stu-id="151cf-448">Format</span></span>

<span data-ttu-id="151cf-449">Una lettera seguita da sei cifre senza spazi o delimitatori</span><span class="sxs-lookup"><span data-stu-id="151cf-449">One letter followed by six digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="151cf-450">Modello</span><span class="sxs-lookup"><span data-stu-id="151cf-450">Pattern</span></span>

<span data-ttu-id="151cf-451">Una lettera seguita da sei cifre:</span><span class="sxs-lookup"><span data-stu-id="151cf-451">One letter followed by six digits:</span></span>
  
- <span data-ttu-id="151cf-452">Una lettera (senza distinzione tra maiuscole/minuscole)</span><span class="sxs-lookup"><span data-stu-id="151cf-452">One letter (not case sensitive)</span></span>
    
- <span data-ttu-id="151cf-453">Sei cifre</span><span class="sxs-lookup"><span data-stu-id="151cf-453">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="151cf-454">Checksum</span><span class="sxs-lookup"><span data-stu-id="151cf-454">Checksum</span></span>

<span data-ttu-id="151cf-455">No</span><span class="sxs-lookup"><span data-stu-id="151cf-455">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="151cf-456">Definizione</span><span class="sxs-lookup"><span data-stu-id="151cf-456">Definition</span></span>

<span data-ttu-id="151cf-457">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="151cf-457">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="151cf-458">L'espressione `Regex_portugal_eu_passport_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="151cf-458">The regular expression  `Regex_portugal_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="151cf-459">Viene trovata una `Keywords_portugal_eu_passport_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="151cf-459">A keyword from  `Keywords_portugal_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_portugal_eu_passport_number" />
          <Match idRef="Keywords_portugal_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="151cf-460">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="151cf-460">Keywords</span></span>

<span data-ttu-id="151cf-461">| |</span><span class="sxs-lookup"><span data-stu-id="151cf-461"></span></span>
|<span data-ttu-id="151cf-462">**Keywords_portugal_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="151cf-462">**Keywords_portugal_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="151cf-463">passport number</span><span class="sxs-lookup"><span data-stu-id="151cf-463">passport number</span></span>  <br/> <span data-ttu-id="151cf-464">numero di passaporto portoghese</span><span class="sxs-lookup"><span data-stu-id="151cf-464">portuguese passport number</span></span>  <br/> <span data-ttu-id="151cf-465">Passport No</span><span class="sxs-lookup"><span data-stu-id="151cf-465">passport no</span></span>  <br/> <span data-ttu-id="151cf-466">número do passaporte</span><span class="sxs-lookup"><span data-stu-id="151cf-466">número do passaporte</span></span>  <br/> |
   
## <a name="romania"></a><span data-ttu-id="151cf-467">Romania</span><span class="sxs-lookup"><span data-stu-id="151cf-467">Romania</span></span>

### <a name="format"></a><span data-ttu-id="151cf-468">Formato</span><span class="sxs-lookup"><span data-stu-id="151cf-468">Format</span></span>

<span data-ttu-id="151cf-469">Otto o nove cifre senza spazi e delimitatori</span><span class="sxs-lookup"><span data-stu-id="151cf-469">Eight or nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="151cf-470">Modello</span><span class="sxs-lookup"><span data-stu-id="151cf-470">Pattern</span></span>

<span data-ttu-id="151cf-471">Otto o nove cifre</span><span class="sxs-lookup"><span data-stu-id="151cf-471">Eight or nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="151cf-472">Checksum</span><span class="sxs-lookup"><span data-stu-id="151cf-472">Checksum</span></span>

<span data-ttu-id="151cf-473">No</span><span class="sxs-lookup"><span data-stu-id="151cf-473">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="151cf-474">Definizione</span><span class="sxs-lookup"><span data-stu-id="151cf-474">Definition</span></span>

<span data-ttu-id="151cf-475">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="151cf-475">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="151cf-476">L'espressione `Regex_romania_eu_passport_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="151cf-476">The regular expression  `Regex_romania_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="151cf-477">Viene trovata una `Keywords_romania_eu_passport_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="151cf-477">A keyword from  `Keywords_romania_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_romania_eu_passport_number" />
          <Match idRef="Keywords_romania_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="151cf-478">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="151cf-478">Keywords</span></span>

<span data-ttu-id="151cf-479">| |</span><span class="sxs-lookup"><span data-stu-id="151cf-479"></span></span>
|<span data-ttu-id="151cf-480">**Keywords_romania_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="151cf-480">**Keywords_romania_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="151cf-481">passport number</span><span class="sxs-lookup"><span data-stu-id="151cf-481">passport number</span></span>  <br/> <span data-ttu-id="151cf-482">numero di passaporto rumeno</span><span class="sxs-lookup"><span data-stu-id="151cf-482">romanian passport number</span></span>  <br/> <span data-ttu-id="151cf-483">Passport No</span><span class="sxs-lookup"><span data-stu-id="151cf-483">passport no</span></span>  <br/> <span data-ttu-id="151cf-484">numărul pașaportului</span><span class="sxs-lookup"><span data-stu-id="151cf-484">numărul pașaportului</span></span>  <br/> |
   
## <a name="slovakia"></a><span data-ttu-id="151cf-485">Slovacchia</span><span class="sxs-lookup"><span data-stu-id="151cf-485">Slovakia</span></span>

### <a name="format"></a><span data-ttu-id="151cf-486">Formato</span><span class="sxs-lookup"><span data-stu-id="151cf-486">Format</span></span>

<span data-ttu-id="151cf-487">Una cifra o una lettera seguita da sette cifre senza spazi o delimitatori</span><span class="sxs-lookup"><span data-stu-id="151cf-487">One digit or letter followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="151cf-488">Modello</span><span class="sxs-lookup"><span data-stu-id="151cf-488">Pattern</span></span>

<span data-ttu-id="151cf-489">Una cifra o una lettera (senza distinzione tra maiuscole/minuscole) seguita da sette cifre</span><span class="sxs-lookup"><span data-stu-id="151cf-489">One digit or letter (not case sensitive) followed by seven digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="151cf-490">Checksum</span><span class="sxs-lookup"><span data-stu-id="151cf-490">Checksum</span></span>

<span data-ttu-id="151cf-491">No</span><span class="sxs-lookup"><span data-stu-id="151cf-491">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="151cf-492">Definizione</span><span class="sxs-lookup"><span data-stu-id="151cf-492">Definition</span></span>

<span data-ttu-id="151cf-493">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="151cf-493">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="151cf-494">L'espressione `Regex_slovakia_eu_passport_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="151cf-494">The regular expression  `Regex_slovakia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="151cf-495">Viene trovata una `Keywords_slovakia_eu_passport_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="151cf-495">A keyword from  `Keywords_slovakia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovakia_eu_passport_number" />
          <Match idRef="Keywords_slovakia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="151cf-496">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="151cf-496">Keywords</span></span>

<span data-ttu-id="151cf-497">| |</span><span class="sxs-lookup"><span data-stu-id="151cf-497"></span></span>
|<span data-ttu-id="151cf-498">**Keywords_slovakia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="151cf-498">**Keywords_slovakia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="151cf-499">passport number</span><span class="sxs-lookup"><span data-stu-id="151cf-499">passport number</span></span>  <br/> <span data-ttu-id="151cf-500">numero di passaporto slovacco</span><span class="sxs-lookup"><span data-stu-id="151cf-500">slovakian passport number</span></span>  <br/> <span data-ttu-id="151cf-501">Passport No</span><span class="sxs-lookup"><span data-stu-id="151cf-501">passport no</span></span>  <br/> <span data-ttu-id="151cf-502">číslo Pasu</span><span class="sxs-lookup"><span data-stu-id="151cf-502">číslo pasu</span></span>  <br/> |
   
## <a name="slovenia"></a><span data-ttu-id="151cf-503">Slovenia</span><span class="sxs-lookup"><span data-stu-id="151cf-503">Slovenia</span></span>

### <a name="format"></a><span data-ttu-id="151cf-504">Formato</span><span class="sxs-lookup"><span data-stu-id="151cf-504">Format</span></span>

<span data-ttu-id="151cf-505">Due lettere seguite da sette cifre senza spazi o delimitatori</span><span class="sxs-lookup"><span data-stu-id="151cf-505">Two letters followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="151cf-506">Modello</span><span class="sxs-lookup"><span data-stu-id="151cf-506">Pattern</span></span>

<span data-ttu-id="151cf-507">Due lettere seguite da sette cifre:</span><span class="sxs-lookup"><span data-stu-id="151cf-507">Two letters followed by seven digits:</span></span>
  
- <span data-ttu-id="151cf-508">La lettera "P"</span><span class="sxs-lookup"><span data-stu-id="151cf-508">The letter "P"</span></span>
    
- <span data-ttu-id="151cf-509">Una lettera maiuscola</span><span class="sxs-lookup"><span data-stu-id="151cf-509">One uppercase letter</span></span>
    
- <span data-ttu-id="151cf-510">Sette cifre</span><span class="sxs-lookup"><span data-stu-id="151cf-510">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="151cf-511">Checksum</span><span class="sxs-lookup"><span data-stu-id="151cf-511">Checksum</span></span>

<span data-ttu-id="151cf-512">No</span><span class="sxs-lookup"><span data-stu-id="151cf-512">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="151cf-513">Definizione</span><span class="sxs-lookup"><span data-stu-id="151cf-513">Definition</span></span>

<span data-ttu-id="151cf-514">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="151cf-514">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="151cf-515">L'espressione `Regex_slovenia_eu_passport_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="151cf-515">The regular expression  `Regex_slovenia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="151cf-516">Viene trovata una `Keywords_slovenia_eu_passport_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="151cf-516">A keyword from  `Keywords_slovenia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovenia_eu_passport_number" />
          <Match idRef="Keywords_slovenia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="151cf-517">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="151cf-517">Keywords</span></span>

<span data-ttu-id="151cf-518">| |</span><span class="sxs-lookup"><span data-stu-id="151cf-518"></span></span>
|<span data-ttu-id="151cf-519">**Keywords_slovenia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="151cf-519">**Keywords_slovenia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="151cf-520">passport number</span><span class="sxs-lookup"><span data-stu-id="151cf-520">passport number</span></span>  <br/> <span data-ttu-id="151cf-521">numero di passaporto sloveno</span><span class="sxs-lookup"><span data-stu-id="151cf-521">slovenian passport number</span></span>  <br/> <span data-ttu-id="151cf-522">Passport No</span><span class="sxs-lookup"><span data-stu-id="151cf-522">passport no</span></span>  <br/> <span data-ttu-id="151cf-523">številka potnega lista</span><span class="sxs-lookup"><span data-stu-id="151cf-523">številka potnega lista</span></span>  <br/> |
   
## <a name="spain"></a><span data-ttu-id="151cf-524">Spagna</span><span class="sxs-lookup"><span data-stu-id="151cf-524">Spain</span></span>

### <a name="format"></a><span data-ttu-id="151cf-525">Formato</span><span class="sxs-lookup"><span data-stu-id="151cf-525">Format</span></span>

<span data-ttu-id="151cf-526">Combinazione di otto o nove caratteri di lettere e numeri senza spazi o delimitatori</span><span class="sxs-lookup"><span data-stu-id="151cf-526">An eight- or nine-character combination of letters and numbers with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="151cf-527">Modello</span><span class="sxs-lookup"><span data-stu-id="151cf-527">Pattern</span></span>

<span data-ttu-id="151cf-528">Combinazione di lettere e numeri di otto o nove caratteri:</span><span class="sxs-lookup"><span data-stu-id="151cf-528">An eight- or nine-character combination of letters and numbers:</span></span>
  
-  <span data-ttu-id="151cf-529">Due cifre o lettere</span><span class="sxs-lookup"><span data-stu-id="151cf-529">Two digits or letters</span></span> 
    
- <span data-ttu-id="151cf-530">Una cifra o una lettera (facoltativa)</span><span class="sxs-lookup"><span data-stu-id="151cf-530">One digit or letter (optional)</span></span>
    
- <span data-ttu-id="151cf-531">Sei cifre</span><span class="sxs-lookup"><span data-stu-id="151cf-531">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="151cf-532">Checksum</span><span class="sxs-lookup"><span data-stu-id="151cf-532">Checksum</span></span>

<span data-ttu-id="151cf-533">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="151cf-533">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="151cf-534">Definizione</span><span class="sxs-lookup"><span data-stu-id="151cf-534">Definition</span></span>

<span data-ttu-id="151cf-535">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="151cf-535">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="151cf-536">L'espressione `Regex_spain_eu_passport_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="151cf-536">The regular expression  `Regex_spain_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="151cf-537">Viene trovata una `Keywords_spain_eu_passport_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="151cf-537">A keyword from  `Keywords_spain_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_spain_eu_passport_number" />
          <Match idRef="Keywords_spain_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="151cf-538">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="151cf-538">Keywords</span></span>

<span data-ttu-id="151cf-539">| |</span><span class="sxs-lookup"><span data-stu-id="151cf-539"></span></span>
|<span data-ttu-id="151cf-540">**Keywords_spain_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="151cf-540">**Keywords_spain_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="151cf-541">passaporto</span><span class="sxs-lookup"><span data-stu-id="151cf-541">passport</span></span>  <br/> <span data-ttu-id="151cf-542">passaporto della Spagna</span><span class="sxs-lookup"><span data-stu-id="151cf-542">spain passport</span></span>  <br/> <span data-ttu-id="151cf-543">libro del passaporto</span><span class="sxs-lookup"><span data-stu-id="151cf-543">passport book</span></span>  <br/> <span data-ttu-id="151cf-544">passport number</span><span class="sxs-lookup"><span data-stu-id="151cf-544">passport number</span></span>  <br/> <span data-ttu-id="151cf-545">Passport No</span><span class="sxs-lookup"><span data-stu-id="151cf-545">passport no</span></span>  <br/> <span data-ttu-id="151cf-546">libreta pasaporte</span><span class="sxs-lookup"><span data-stu-id="151cf-546">libreta pasaporte</span></span>  <br/> <span data-ttu-id="151cf-547">número pasaporte</span><span class="sxs-lookup"><span data-stu-id="151cf-547">número pasaporte</span></span>  <br/> <span data-ttu-id="151cf-548">pasaporte España</span><span class="sxs-lookup"><span data-stu-id="151cf-548">españa pasaporte</span></span>  <br/> <span data-ttu-id="151cf-549">pasaporte</span><span class="sxs-lookup"><span data-stu-id="151cf-549">pasaporte</span></span>  <br/> |
   
## <a name="sweden"></a><span data-ttu-id="151cf-550">Svezia</span><span class="sxs-lookup"><span data-stu-id="151cf-550">Sweden</span></span>

<span data-ttu-id="151cf-551">Per informazioni dettagliate, vedere la sezione "Sweden Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="151cf-551">For details, see the section "Sweden Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="uk"></a><span data-ttu-id="151cf-552">Regno Unito</span><span class="sxs-lookup"><span data-stu-id="151cf-552">UK</span></span>

<span data-ttu-id="151cf-553">Per informazioni dettagliate, vedere la sezione "Stati Uniti/Regno Unito</span><span class="sxs-lookup"><span data-stu-id="151cf-553">For details, see the section "U.S. / U.K.</span></span> <span data-ttu-id="151cf-554">Numero di passaporto "in [quello che cercano i tipi di informazioni riservate](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="151cf-554">Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="151cf-555">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="151cf-555">See also</span></span>

[<span data-ttu-id="151cf-556">Cosa individuano le tipologie di informazioni sensibili</span><span class="sxs-lookup"><span data-stu-id="151cf-556">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)

