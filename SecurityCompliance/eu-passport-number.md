---
title: Numero di passaporto EU
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 8/16/2018
ms.audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 8c00df57-9fb3-459c-ba87-40480c87bd55
description: In questo argomento viene illustrato l'aspetto di un criterio di prevenzione della perdita di dati (DLP) quando viene rilevato il tipo di informazioni riservate del numero di passaporto dell'Unione europea. Questo tipo di informazioni riservate definisce modelli, parole chiave e altre evidenze diverse per ogni paese.
ms.openlocfilehash: c46f683bd1baf651bcf13c1766dfff3cb953b341
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/23/2019
ms.locfileid: "30218266"
---
# <a name="eu-passport-number"></a><span data-ttu-id="86cd8-104">Numero di passaporto EU</span><span class="sxs-lookup"><span data-stu-id="86cd8-104">EU Passport Number</span></span>

<span data-ttu-id="86cd8-p102">In questo argomento viene illustrato l'aspetto di un criterio di prevenzione della perdita di dati (DLP) quando viene rilevato il tipo di informazioni riservate del numero di passaporto dell'Unione europea. Questo tipo di informazioni riservate definisce modelli, parole chiave e altre evidenze diverse per ogni paese.</span><span class="sxs-lookup"><span data-stu-id="86cd8-p102">This topic shows what a data loss prevention (DLP) policy looks for when it detects the EU Passport Number sensitive information type. This sensitive information type defines different patterns, keywords, and other evidence for each country.</span></span>
  
## <a name="austria"></a><span data-ttu-id="86cd8-107">Austria</span><span class="sxs-lookup"><span data-stu-id="86cd8-107">Austria</span></span>

### <a name="format"></a><span data-ttu-id="86cd8-108">Formato</span><span class="sxs-lookup"><span data-stu-id="86cd8-108">Format</span></span>

<span data-ttu-id="86cd8-109">Una lettera seguita da uno spazio facoltativo e sette cifre</span><span class="sxs-lookup"><span data-stu-id="86cd8-109">One letter followed by an optional space and seven digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="86cd8-110">Modello</span><span class="sxs-lookup"><span data-stu-id="86cd8-110">Pattern</span></span>

<span data-ttu-id="86cd8-111">Combinazione di una lettera, sette cifre e uno spazio:</span><span class="sxs-lookup"><span data-stu-id="86cd8-111">A combination of one letter, seven digits, and one space:</span></span>
  
- <span data-ttu-id="86cd8-112">Una lettera (senza distinzione tra maiuscole/minuscole)</span><span class="sxs-lookup"><span data-stu-id="86cd8-112">One letter (not case sensitive)</span></span>
    
- <span data-ttu-id="86cd8-113">Uno spazio (facoltativo)</span><span class="sxs-lookup"><span data-stu-id="86cd8-113">One space (optional)</span></span>
    
- <span data-ttu-id="86cd8-114">Sette cifre</span><span class="sxs-lookup"><span data-stu-id="86cd8-114">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="86cd8-115">Checksum</span><span class="sxs-lookup"><span data-stu-id="86cd8-115">Checksum</span></span>

<span data-ttu-id="86cd8-116">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="86cd8-116">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="86cd8-117">Definizione</span><span class="sxs-lookup"><span data-stu-id="86cd8-117">Definition</span></span>

<span data-ttu-id="86cd8-118">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="86cd8-118">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="86cd8-119">L'espressione `Regex_austria_eu_passport_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="86cd8-119">The regular expression  `Regex_austria_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="86cd8-120">Viene trovata una `Keywords_austria_eu_passport_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="86cd8-120">A keyword from  `Keywords_austria_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_austria_eu_passport_number" />
          <Match idRef="Keywords_austria_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="86cd8-121">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="86cd8-121">Keywords</span></span>

<span data-ttu-id="86cd8-122">| |</span><span class="sxs-lookup"><span data-stu-id="86cd8-122"></span></span>
|<span data-ttu-id="86cd8-123">**Keywords_austria_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="86cd8-123">**Keywords_austria_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="86cd8-124">numero di passaporto</span><span class="sxs-lookup"><span data-stu-id="86cd8-124">passport number</span></span>  <br/> <span data-ttu-id="86cd8-125">numero di passaporto austriaco</span><span class="sxs-lookup"><span data-stu-id="86cd8-125">austrian passport number</span></span>  <br/> <span data-ttu-id="86cd8-126">Passport No</span><span class="sxs-lookup"><span data-stu-id="86cd8-126">passport no</span></span>  <br/> <span data-ttu-id="86cd8-127">reisepass</span><span class="sxs-lookup"><span data-stu-id="86cd8-127">reisepass</span></span>  <br/> <span data-ttu-id="86cd8-128">Österreichisch Reisepass</span><span class="sxs-lookup"><span data-stu-id="86cd8-128">österreichisch reisepass</span></span>  <br/> |
   
## <a name="belgium"></a><span data-ttu-id="86cd8-129">Belgio</span><span class="sxs-lookup"><span data-stu-id="86cd8-129">Belgium</span></span>

### <a name="format"></a><span data-ttu-id="86cd8-130">Formato</span><span class="sxs-lookup"><span data-stu-id="86cd8-130">Format</span></span>

<span data-ttu-id="86cd8-131">Due lettere seguite da sei cifre senza spazi o delimitatori</span><span class="sxs-lookup"><span data-stu-id="86cd8-131">Two letters followed by six digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="86cd8-132">Modello</span><span class="sxs-lookup"><span data-stu-id="86cd8-132">Pattern</span></span>

<span data-ttu-id="86cd8-133">Due lettere e seguite da sei cifre</span><span class="sxs-lookup"><span data-stu-id="86cd8-133">Two letters and followed by six digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="86cd8-134">Checksum</span><span class="sxs-lookup"><span data-stu-id="86cd8-134">Checksum</span></span>

<span data-ttu-id="86cd8-135">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="86cd8-135">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="86cd8-136">Definizione</span><span class="sxs-lookup"><span data-stu-id="86cd8-136">Definition</span></span>

<span data-ttu-id="86cd8-137">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="86cd8-137">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="86cd8-138">L'espressione `Regex_belgium_eu_passport_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="86cd8-138">The regular expression  `Regex_belgium_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="86cd8-139">Viene trovata una `Keywords_belgium_eu_passport_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="86cd8-139">A keyword from  `Keywords_belgium_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_belgium__eu_passport_number" />
          <Match idRef="Keywords_belgium_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="86cd8-140">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="86cd8-140">Keywords</span></span>

<span data-ttu-id="86cd8-141">| |</span><span class="sxs-lookup"><span data-stu-id="86cd8-141"></span></span>
|<span data-ttu-id="86cd8-142">**Keywords_belgium_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="86cd8-142">**Keywords_belgium_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="86cd8-143">numero di passaporto</span><span class="sxs-lookup"><span data-stu-id="86cd8-143">passport number</span></span>  <br/> <span data-ttu-id="86cd8-144">numero di passaporto belga</span><span class="sxs-lookup"><span data-stu-id="86cd8-144">belgian passport number</span></span>  <br/> <span data-ttu-id="86cd8-145">Passport No</span><span class="sxs-lookup"><span data-stu-id="86cd8-145">passport no</span></span>  <br/> <span data-ttu-id="86cd8-146">PASPOORT</span><span class="sxs-lookup"><span data-stu-id="86cd8-146">paspoort</span></span>  <br/> <span data-ttu-id="86cd8-147">paspoortnummer</span><span class="sxs-lookup"><span data-stu-id="86cd8-147">paspoortnummer</span></span>  <br/> <span data-ttu-id="86cd8-148">Reisepass kein</span><span class="sxs-lookup"><span data-stu-id="86cd8-148">reisepass kein</span></span>  <br/> <span data-ttu-id="86cd8-149">reisepass</span><span class="sxs-lookup"><span data-stu-id="86cd8-149">reisepass</span></span>  <br/> |
   
## <a name="bulgaria"></a><span data-ttu-id="86cd8-150">Bulgaria</span><span class="sxs-lookup"><span data-stu-id="86cd8-150">Bulgaria</span></span>

### <a name="format"></a><span data-ttu-id="86cd8-151">Formato</span><span class="sxs-lookup"><span data-stu-id="86cd8-151">Format</span></span>

<span data-ttu-id="86cd8-152">Nove cifre senza spazi e delimitatori</span><span class="sxs-lookup"><span data-stu-id="86cd8-152">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="86cd8-153">Modello</span><span class="sxs-lookup"><span data-stu-id="86cd8-153">Pattern</span></span>

 <span data-ttu-id="86cd8-154">9 cifre</span><span class="sxs-lookup"><span data-stu-id="86cd8-154">Nine digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="86cd8-155">Checksum</span><span class="sxs-lookup"><span data-stu-id="86cd8-155">Checksum</span></span>

<span data-ttu-id="86cd8-156">No</span><span class="sxs-lookup"><span data-stu-id="86cd8-156">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="86cd8-157">Definizione</span><span class="sxs-lookup"><span data-stu-id="86cd8-157">Definition</span></span>

<span data-ttu-id="86cd8-158">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="86cd8-158">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="86cd8-159">L'espressione `Regex_bulgaria_eu_passport_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="86cd8-159">The regular expression  `Regex_bulgaria_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="86cd8-160">Viene trovata una `Keywords_bulgaria_eu_passport_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="86cd8-160">A keyword from  `Keywords_bulgaria_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_bulgaria_eu_passport_number" />
          <Match idRef="Keywords_bulgaria_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="86cd8-161">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="86cd8-161">Keywords</span></span>

<span data-ttu-id="86cd8-162">| |</span><span class="sxs-lookup"><span data-stu-id="86cd8-162"></span></span>
|<span data-ttu-id="86cd8-163">**Keywords_bulgaria_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="86cd8-163">**Keywords_bulgaria_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="86cd8-164">numero di passaporto</span><span class="sxs-lookup"><span data-stu-id="86cd8-164">passport number</span></span>  <br/> <span data-ttu-id="86cd8-165">numero di passaporto bulgaro</span><span class="sxs-lookup"><span data-stu-id="86cd8-165">bulgarian passport number</span></span>  <br/> <span data-ttu-id="86cd8-166">Passport No</span><span class="sxs-lookup"><span data-stu-id="86cd8-166">passport no</span></span>  <br/> <span data-ttu-id="86cd8-167">Номер на паспорта</span><span class="sxs-lookup"><span data-stu-id="86cd8-167">номер на паспорта</span></span>  <br/> |
   
## <a name="croatia"></a><span data-ttu-id="86cd8-168">Croazia</span><span class="sxs-lookup"><span data-stu-id="86cd8-168">Croatia</span></span>

### <a name="format"></a><span data-ttu-id="86cd8-169">Formato</span><span class="sxs-lookup"><span data-stu-id="86cd8-169">Format</span></span>

<span data-ttu-id="86cd8-170">Nove cifre senza spazi e delimitatori</span><span class="sxs-lookup"><span data-stu-id="86cd8-170">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="86cd8-171">Modello</span><span class="sxs-lookup"><span data-stu-id="86cd8-171">Pattern</span></span>

 <span data-ttu-id="86cd8-172">9 cifre</span><span class="sxs-lookup"><span data-stu-id="86cd8-172">Nine digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="86cd8-173">Checksum</span><span class="sxs-lookup"><span data-stu-id="86cd8-173">Checksum</span></span>

<span data-ttu-id="86cd8-174">No</span><span class="sxs-lookup"><span data-stu-id="86cd8-174">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="86cd8-175">Definizione</span><span class="sxs-lookup"><span data-stu-id="86cd8-175">Definition</span></span>

<span data-ttu-id="86cd8-176">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="86cd8-176">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="86cd8-177">L'espressione `Regex_croatia_eu_passport_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="86cd8-177">The regular expression  `Regex_croatia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="86cd8-178">Viene trovata una `Keywords_croatia_eu_passport_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="86cd8-178">A keyword from  `Keywords_croatia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_croatia_eu_passport_number" />
          <Match idRef="Keywords_croatia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="86cd8-179">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="86cd8-179">Keywords</span></span>

<span data-ttu-id="86cd8-180">| |</span><span class="sxs-lookup"><span data-stu-id="86cd8-180"></span></span>
|<span data-ttu-id="86cd8-181">**Keywords_croatia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="86cd8-181">**Keywords_croatia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="86cd8-182">numero di passaporto</span><span class="sxs-lookup"><span data-stu-id="86cd8-182">passport number</span></span>  <br/> <span data-ttu-id="86cd8-183">numero di passaporto croato</span><span class="sxs-lookup"><span data-stu-id="86cd8-183">croatian passport number</span></span>  <br/> <span data-ttu-id="86cd8-184">Passport No</span><span class="sxs-lookup"><span data-stu-id="86cd8-184">passport no</span></span>  <br/> <span data-ttu-id="86cd8-185">broj putovnice</span><span class="sxs-lookup"><span data-stu-id="86cd8-185">broj putovnice</span></span>  <br/> |
   
## <a name="cyprus"></a><span data-ttu-id="86cd8-186">Cipro</span><span class="sxs-lookup"><span data-stu-id="86cd8-186">Cyprus</span></span>

### <a name="format"></a><span data-ttu-id="86cd8-187">Formato</span><span class="sxs-lookup"><span data-stu-id="86cd8-187">Format</span></span>

<span data-ttu-id="86cd8-188">Una lettera seguita da 6-8 cifre senza spazi o delimitatori</span><span class="sxs-lookup"><span data-stu-id="86cd8-188">One letter followed by 6-8 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="86cd8-189">Modello</span><span class="sxs-lookup"><span data-stu-id="86cd8-189">Pattern</span></span>

<span data-ttu-id="86cd8-190">Una lettera seguita da sei a otto cifre</span><span class="sxs-lookup"><span data-stu-id="86cd8-190">One letter followed by six to eight digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="86cd8-191">Checksum</span><span class="sxs-lookup"><span data-stu-id="86cd8-191">Checksum</span></span>

<span data-ttu-id="86cd8-192">No</span><span class="sxs-lookup"><span data-stu-id="86cd8-192">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="86cd8-193">Definizione</span><span class="sxs-lookup"><span data-stu-id="86cd8-193">Definition</span></span>

<span data-ttu-id="86cd8-194">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="86cd8-194">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="86cd8-195">L'espressione `Regex_cyprus_eu_passport_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="86cd8-195">The regular expression  `Regex_cyprus_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="86cd8-196">Viene trovata una `Keywords_cyprus_eu_passport_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="86cd8-196">A keyword from  `Keywords_cyprus_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_cyprus_eu_passport_number" />
          <Match idRef="Keywords_cyprus_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="86cd8-197">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="86cd8-197">Keywords</span></span>

<span data-ttu-id="86cd8-198">| |</span><span class="sxs-lookup"><span data-stu-id="86cd8-198"></span></span>
|<span data-ttu-id="86cd8-199">**Keywords_cyprus_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="86cd8-199">**Keywords_cyprus_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="86cd8-200">numero di passaporto</span><span class="sxs-lookup"><span data-stu-id="86cd8-200">passport number</span></span>  <br/> <span data-ttu-id="86cd8-201">numero di passaporto di Cipro</span><span class="sxs-lookup"><span data-stu-id="86cd8-201">cyprus passport number</span></span>  <br/> <span data-ttu-id="86cd8-202">Passport No</span><span class="sxs-lookup"><span data-stu-id="86cd8-202">passport no</span></span>  <br/> <span data-ttu-id="86cd8-203">αριθμό διαβατηρίου</span><span class="sxs-lookup"><span data-stu-id="86cd8-203">αριθμό διαβατηρίου</span></span>  <br/> |
   
## <a name="czech-republic"></a><span data-ttu-id="86cd8-204">Repubblica Ceca</span><span class="sxs-lookup"><span data-stu-id="86cd8-204">Czech Republic</span></span>

### <a name="format"></a><span data-ttu-id="86cd8-205">Formato</span><span class="sxs-lookup"><span data-stu-id="86cd8-205">Format</span></span>

<span data-ttu-id="86cd8-206">Otto cifre senza spazi o delimitatori</span><span class="sxs-lookup"><span data-stu-id="86cd8-206">Eight digits without spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="86cd8-207">Modello</span><span class="sxs-lookup"><span data-stu-id="86cd8-207">Pattern</span></span>

<span data-ttu-id="86cd8-208">Otto cifre senza spazi o delimitatori</span><span class="sxs-lookup"><span data-stu-id="86cd8-208">Eight digits without spaces or delimiters</span></span>
  
### <a name="checksum"></a><span data-ttu-id="86cd8-209">Checksum</span><span class="sxs-lookup"><span data-stu-id="86cd8-209">Checksum</span></span>

<span data-ttu-id="86cd8-210">No</span><span class="sxs-lookup"><span data-stu-id="86cd8-210">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="86cd8-211">Definizione</span><span class="sxs-lookup"><span data-stu-id="86cd8-211">Definition</span></span>

<span data-ttu-id="86cd8-212">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="86cd8-212">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="86cd8-213">L'espressione `Regex_czech_republic_eu_passport_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="86cd8-213">The regular expression  `Regex_czech_republic_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="86cd8-214">Viene trovata una `Keywords_czech_republic_eu_passport_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="86cd8-214">A keyword from  `Keywords_czech_republic_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_czech_republic_eu_passport_number" />
          <Match idRef="Keywords_czech_republic_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="86cd8-215">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="86cd8-215">Keywords</span></span>

<span data-ttu-id="86cd8-216">| |</span><span class="sxs-lookup"><span data-stu-id="86cd8-216"></span></span>
|<span data-ttu-id="86cd8-217">**Keywords_czech_republic_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="86cd8-217">**Keywords_czech_republic_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="86cd8-218">numero di passaporto</span><span class="sxs-lookup"><span data-stu-id="86cd8-218">passport number</span></span>  <br/> <span data-ttu-id="86cd8-219">numero di passaporto ceco</span><span class="sxs-lookup"><span data-stu-id="86cd8-219">czech passport number</span></span>  <br/> <span data-ttu-id="86cd8-220">Passport No</span><span class="sxs-lookup"><span data-stu-id="86cd8-220">passport no</span></span>  <br/> <span data-ttu-id="86cd8-221">Cestovní pas</span><span class="sxs-lookup"><span data-stu-id="86cd8-221">cestovní pas</span></span>  <br/> <span data-ttu-id="86cd8-222">pas</span><span class="sxs-lookup"><span data-stu-id="86cd8-222">pas</span></span>  <br/> |
   
## <a name="denmark"></a><span data-ttu-id="86cd8-223">Danimarca</span><span class="sxs-lookup"><span data-stu-id="86cd8-223">Denmark</span></span>

### <a name="format"></a><span data-ttu-id="86cd8-224">Formato</span><span class="sxs-lookup"><span data-stu-id="86cd8-224">Format</span></span>

<span data-ttu-id="86cd8-225">Nove cifre senza spazi e delimitatori</span><span class="sxs-lookup"><span data-stu-id="86cd8-225">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="86cd8-226">Modello</span><span class="sxs-lookup"><span data-stu-id="86cd8-226">Pattern</span></span>

 <span data-ttu-id="86cd8-227">9 cifre</span><span class="sxs-lookup"><span data-stu-id="86cd8-227">Nine digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="86cd8-228">Checksum</span><span class="sxs-lookup"><span data-stu-id="86cd8-228">Checksum</span></span>

<span data-ttu-id="86cd8-229">No</span><span class="sxs-lookup"><span data-stu-id="86cd8-229">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="86cd8-230">Definizione</span><span class="sxs-lookup"><span data-stu-id="86cd8-230">Definition</span></span>

<span data-ttu-id="86cd8-231">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="86cd8-231">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="86cd8-232">L'espressione `Regex_denmark_eu_passport_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="86cd8-232">The regular expression  `Regex_denmark_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="86cd8-233">Viene trovata una `Keywords_denmark_eu_passport_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="86cd8-233">A keyword from  `Keywords_denmark_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_denmark_eu_passport_number" />
          <Match idRef="Keywords_denmark_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="86cd8-234">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="86cd8-234">Keywords</span></span>

<span data-ttu-id="86cd8-235">| |</span><span class="sxs-lookup"><span data-stu-id="86cd8-235"></span></span>
|<span data-ttu-id="86cd8-236">**Keywords_denmark_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="86cd8-236">**Keywords_denmark_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="86cd8-237">numero di passaporto</span><span class="sxs-lookup"><span data-stu-id="86cd8-237">passport number</span></span>  <br/> <span data-ttu-id="86cd8-238">numero di passaporto danese</span><span class="sxs-lookup"><span data-stu-id="86cd8-238">danish passport number</span></span>  <br/> <span data-ttu-id="86cd8-239">Passport No</span><span class="sxs-lookup"><span data-stu-id="86cd8-239">passport no</span></span>  <br/> <span data-ttu-id="86cd8-240">pas</span><span class="sxs-lookup"><span data-stu-id="86cd8-240">pas</span></span>  <br/> <span data-ttu-id="86cd8-241">Pasnummer</span><span class="sxs-lookup"><span data-stu-id="86cd8-241">pasnummer</span></span>  <br/> |
   
## <a name="estonia"></a><span data-ttu-id="86cd8-242">Estonia</span><span class="sxs-lookup"><span data-stu-id="86cd8-242">Estonia</span></span>

### <a name="format"></a><span data-ttu-id="86cd8-243">Formato</span><span class="sxs-lookup"><span data-stu-id="86cd8-243">Format</span></span>

<span data-ttu-id="86cd8-244">Una lettera seguita da sette cifre senza spazi o delimitatori</span><span class="sxs-lookup"><span data-stu-id="86cd8-244">One letter followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="86cd8-245">Modello</span><span class="sxs-lookup"><span data-stu-id="86cd8-245">Pattern</span></span>

<span data-ttu-id="86cd8-246">Una lettera seguita da sette cifre</span><span class="sxs-lookup"><span data-stu-id="86cd8-246">One letter followed by seven digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="86cd8-247">Checksum</span><span class="sxs-lookup"><span data-stu-id="86cd8-247">Checksum</span></span>

<span data-ttu-id="86cd8-248">No</span><span class="sxs-lookup"><span data-stu-id="86cd8-248">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="86cd8-249">Definizione</span><span class="sxs-lookup"><span data-stu-id="86cd8-249">Definition</span></span>

<span data-ttu-id="86cd8-250">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="86cd8-250">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="86cd8-251">L'espressione `Regex_estonia_eu_passport_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="86cd8-251">The regular expression  `Regex_estonia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="86cd8-252">Viene trovata una `Keywords_estonia_eu_passport_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="86cd8-252">A keyword from  `Keywords_estonia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_estonia_eu_passport_number" />
          <Match idRef="Keywords_estonia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="86cd8-253">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="86cd8-253">Keywords</span></span>

<span data-ttu-id="86cd8-254">| |</span><span class="sxs-lookup"><span data-stu-id="86cd8-254"></span></span>
|<span data-ttu-id="86cd8-255">**Keywords_estonia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="86cd8-255">**Keywords_estonia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="86cd8-256">numero di passaporto</span><span class="sxs-lookup"><span data-stu-id="86cd8-256">passport number</span></span>  <br/> <span data-ttu-id="86cd8-257">numero di passaporto estone</span><span class="sxs-lookup"><span data-stu-id="86cd8-257">estonian passport number</span></span>  <br/> <span data-ttu-id="86cd8-258">Passport No</span><span class="sxs-lookup"><span data-stu-id="86cd8-258">passport no</span></span>  <br/> <span data-ttu-id="86cd8-259">passaggio kodaniku Eesti</span><span class="sxs-lookup"><span data-stu-id="86cd8-259">eesti kodaniku pass</span></span>  <br/> |
   
## <a name="finland"></a><span data-ttu-id="86cd8-260">Finlandia</span><span class="sxs-lookup"><span data-stu-id="86cd8-260">Finland</span></span>

<span data-ttu-id="86cd8-261">Per informazioni dettagliate, vedere la sezione "Finlandia Passport Number" in [che cosa cercano i tipi di informazioni riservate](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="86cd8-261">For details, see the section "Finland Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="france"></a><span data-ttu-id="86cd8-262">Francia</span><span class="sxs-lookup"><span data-stu-id="86cd8-262">France</span></span>

<span data-ttu-id="86cd8-263">Per informazioni dettagliate, vedere la sezione "Francia Passport Number" in [che cosa cercano i tipi di informazioni riservate](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="86cd8-263">For details, see the section "France Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="germany"></a><span data-ttu-id="86cd8-264">Germania</span><span class="sxs-lookup"><span data-stu-id="86cd8-264">Germany</span></span>

<span data-ttu-id="86cd8-265">Per informazioni dettagliate, vedere la sezione "Germania Passport Number" in [che cosa cercano i tipi di informazioni riservate](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="86cd8-265">For details, see the section "Germany Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="greece"></a><span data-ttu-id="86cd8-266">Grecia</span><span class="sxs-lookup"><span data-stu-id="86cd8-266">Greece</span></span>

### <a name="format"></a><span data-ttu-id="86cd8-267">Formato</span><span class="sxs-lookup"><span data-stu-id="86cd8-267">Format</span></span>

<span data-ttu-id="86cd8-268">Due lettere seguite da sette cifre senza spazi o delimitatori</span><span class="sxs-lookup"><span data-stu-id="86cd8-268">Two letters followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="86cd8-269">Modello</span><span class="sxs-lookup"><span data-stu-id="86cd8-269">Pattern</span></span>

<span data-ttu-id="86cd8-270">Due lettere seguite da 7 cifre</span><span class="sxs-lookup"><span data-stu-id="86cd8-270">Two letters followed by seven digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="86cd8-271">Checksum</span><span class="sxs-lookup"><span data-stu-id="86cd8-271">Checksum</span></span>

<span data-ttu-id="86cd8-272">No</span><span class="sxs-lookup"><span data-stu-id="86cd8-272">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="86cd8-273">Definizione</span><span class="sxs-lookup"><span data-stu-id="86cd8-273">Definition</span></span>

<span data-ttu-id="86cd8-274">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="86cd8-274">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="86cd8-275">L'espressione `Regex_greece_eu_passport_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="86cd8-275">The regular expression  `Regex_greece_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="86cd8-276">Viene trovata una `Keywords_greece_eu_passport_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="86cd8-276">A keyword from  `Keywords_greece_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_greece_eu_passport_number" />
          <Match idRef="Keywords_greece_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="86cd8-277">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="86cd8-277">Keywords</span></span>

<span data-ttu-id="86cd8-278">| |</span><span class="sxs-lookup"><span data-stu-id="86cd8-278"></span></span>
|<span data-ttu-id="86cd8-279">**Keywords_greece_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="86cd8-279">**Keywords_greece_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="86cd8-280">numero di passaporto</span><span class="sxs-lookup"><span data-stu-id="86cd8-280">passport number</span></span>  <br/> <span data-ttu-id="86cd8-281">numero di passaporto greco</span><span class="sxs-lookup"><span data-stu-id="86cd8-281">greek passport number</span></span>  <br/> <span data-ttu-id="86cd8-282">Passport No</span><span class="sxs-lookup"><span data-stu-id="86cd8-282">passport no</span></span>  <br/> <span data-ttu-id="86cd8-283">διαβατηριο</span><span class="sxs-lookup"><span data-stu-id="86cd8-283">διαβατηριο</span></span>  <br/> |
   
## <a name="hungary"></a><span data-ttu-id="86cd8-284">Ungheria</span><span class="sxs-lookup"><span data-stu-id="86cd8-284">Hungary</span></span>

### <a name="format"></a><span data-ttu-id="86cd8-285">Formato</span><span class="sxs-lookup"><span data-stu-id="86cd8-285">Format</span></span>

<span data-ttu-id="86cd8-286">Due lettere seguite da sei o sette cifre senza spazi o delimitatori</span><span class="sxs-lookup"><span data-stu-id="86cd8-286">Two letters followed by six or seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="86cd8-287">Modello</span><span class="sxs-lookup"><span data-stu-id="86cd8-287">Pattern</span></span>

<span data-ttu-id="86cd8-288">Due lettere seguite da sei o sette cifre</span><span class="sxs-lookup"><span data-stu-id="86cd8-288">Two letters followed by six or seven digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="86cd8-289">Checksum</span><span class="sxs-lookup"><span data-stu-id="86cd8-289">Checksum</span></span>

<span data-ttu-id="86cd8-290">No</span><span class="sxs-lookup"><span data-stu-id="86cd8-290">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="86cd8-291">Definizione</span><span class="sxs-lookup"><span data-stu-id="86cd8-291">Definition</span></span>

<span data-ttu-id="86cd8-292">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="86cd8-292">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="86cd8-293">L'espressione `Regex_hungary_eu_passport_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="86cd8-293">The regular expression  `Regex_hungary_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="86cd8-294">Viene trovata una `Keywords_hungary_eu_passport_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="86cd8-294">A keyword from  `Keywords_hungary_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_hungary_eu_passport_number" />
          <Match idRef="Keywords_hungary_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="86cd8-295">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="86cd8-295">Keywords</span></span>

<span data-ttu-id="86cd8-296">| |</span><span class="sxs-lookup"><span data-stu-id="86cd8-296"></span></span>
|<span data-ttu-id="86cd8-297">**Keywords_hungary_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="86cd8-297">**Keywords_hungary_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="86cd8-298">numero di passaporto</span><span class="sxs-lookup"><span data-stu-id="86cd8-298">passport number</span></span>  <br/> <span data-ttu-id="86cd8-299">numero di passaporto ungherese</span><span class="sxs-lookup"><span data-stu-id="86cd8-299">hungarian passport number</span></span>  <br/> <span data-ttu-id="86cd8-300">Passport No</span><span class="sxs-lookup"><span data-stu-id="86cd8-300">passport no</span></span>  <br/> <span data-ttu-id="86cd8-301">útlevél száma</span><span class="sxs-lookup"><span data-stu-id="86cd8-301">útlevél száma</span></span>  <br/> |
   
## <a name="ireland"></a><span data-ttu-id="86cd8-302">Irlanda</span><span class="sxs-lookup"><span data-stu-id="86cd8-302">Ireland</span></span>

### <a name="format"></a><span data-ttu-id="86cd8-303">Formato</span><span class="sxs-lookup"><span data-stu-id="86cd8-303">Format</span></span>

<span data-ttu-id="86cd8-304">Due lettere o cifre seguite da sette cifre senza spazi o delimitatori</span><span class="sxs-lookup"><span data-stu-id="86cd8-304">Two letters or digits followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="86cd8-305">Modello</span><span class="sxs-lookup"><span data-stu-id="86cd8-305">Pattern</span></span>

<span data-ttu-id="86cd8-306">Due lettere o cifre seguite da sette cifre:</span><span class="sxs-lookup"><span data-stu-id="86cd8-306">Two letters or digits followed by seven digits:</span></span>
  
- <span data-ttu-id="86cd8-307">Due cifre o lettere (senza distinzione tra maiuscole/minuscole)</span><span class="sxs-lookup"><span data-stu-id="86cd8-307">Two digits or letters (not case sensitive)</span></span>
    
- <span data-ttu-id="86cd8-308">Sette cifre</span><span class="sxs-lookup"><span data-stu-id="86cd8-308">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="86cd8-309">Checksum</span><span class="sxs-lookup"><span data-stu-id="86cd8-309">Checksum</span></span>

<span data-ttu-id="86cd8-310">No</span><span class="sxs-lookup"><span data-stu-id="86cd8-310">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="86cd8-311">Definizione</span><span class="sxs-lookup"><span data-stu-id="86cd8-311">Definition</span></span>

<span data-ttu-id="86cd8-312">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="86cd8-312">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="86cd8-313">L'espressione `Regex_ireland_eu_passport_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="86cd8-313">The regular expression  `Regex_ireland_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="86cd8-314">Viene trovata una `Keywords_ireland_eu_passport_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="86cd8-314">A keyword from  `Keywords_ireland_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_ireland_eu_passport_number" />
          <Match idRef="Keywords_ireland_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="86cd8-315">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="86cd8-315">Keywords</span></span>

<span data-ttu-id="86cd8-316">| |</span><span class="sxs-lookup"><span data-stu-id="86cd8-316"></span></span>
|<span data-ttu-id="86cd8-317">**Keywords_ireland_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="86cd8-317">**Keywords_ireland_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="86cd8-318">numero di passaporto</span><span class="sxs-lookup"><span data-stu-id="86cd8-318">passport number</span></span>  <br/> <span data-ttu-id="86cd8-319">numero di passaporto irlandese</span><span class="sxs-lookup"><span data-stu-id="86cd8-319">irish passport number</span></span>  <br/> <span data-ttu-id="86cd8-320">Passport No</span><span class="sxs-lookup"><span data-stu-id="86cd8-320">passport no</span></span>  <br/> <span data-ttu-id="86cd8-321">pas</span><span class="sxs-lookup"><span data-stu-id="86cd8-321">pas</span></span>  <br/> <span data-ttu-id="86cd8-322">passport</span><span class="sxs-lookup"><span data-stu-id="86cd8-322">passport</span></span>  <br/> <span data-ttu-id="86cd8-323">Passeport</span><span class="sxs-lookup"><span data-stu-id="86cd8-323">passeport</span></span>  <br/> <span data-ttu-id="86cd8-324">numero Passeport</span><span class="sxs-lookup"><span data-stu-id="86cd8-324">passeport numero</span></span>  <br/> |
   
## <a name="italy"></a><span data-ttu-id="86cd8-325">Italia</span><span class="sxs-lookup"><span data-stu-id="86cd8-325">Italy</span></span>

### <a name="format"></a><span data-ttu-id="86cd8-326">Formato</span><span class="sxs-lookup"><span data-stu-id="86cd8-326">Format</span></span>

<span data-ttu-id="86cd8-327">Due lettere o cifre seguite da sette cifre senza spazi o delimitatori</span><span class="sxs-lookup"><span data-stu-id="86cd8-327">Two letters or digits followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="86cd8-328">Modello</span><span class="sxs-lookup"><span data-stu-id="86cd8-328">Pattern</span></span>

<span data-ttu-id="86cd8-329">Due lettere o cifre seguite da sette cifre:</span><span class="sxs-lookup"><span data-stu-id="86cd8-329">Two letters or digits followed by seven digits:</span></span>
  
- <span data-ttu-id="86cd8-330">Due cifre o lettere (senza distinzione tra maiuscole/minuscole)</span><span class="sxs-lookup"><span data-stu-id="86cd8-330">Two digits or letters (not case sensitive)</span></span>
    
- <span data-ttu-id="86cd8-331">Sette cifre</span><span class="sxs-lookup"><span data-stu-id="86cd8-331">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="86cd8-332">Checksum</span><span class="sxs-lookup"><span data-stu-id="86cd8-332">Checksum</span></span>

<span data-ttu-id="86cd8-333">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="86cd8-333">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="86cd8-334">Definizione</span><span class="sxs-lookup"><span data-stu-id="86cd8-334">Definition</span></span>

<span data-ttu-id="86cd8-335">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="86cd8-335">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="86cd8-336">L'espressione `Regex_italy_eu_passport_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="86cd8-336">The regular expression  `Regex_italy_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="86cd8-337">Viene trovata una `Keywords_italy_eu_passport_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="86cd8-337">A keyword from  `Keywords_italy_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_italy_eu_passport_number" />
          <Match idRef="Keywords_italy_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="86cd8-338">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="86cd8-338">Keywords</span></span>

<span data-ttu-id="86cd8-339">| |</span><span class="sxs-lookup"><span data-stu-id="86cd8-339"></span></span>
|<span data-ttu-id="86cd8-340">**Keywords_italy_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="86cd8-340">**Keywords_italy_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="86cd8-341">numero di passaporto italiano</span><span class="sxs-lookup"><span data-stu-id="86cd8-341">italian passport number</span></span>  <br/> <span data-ttu-id="86cd8-342">Repubblica italiana passaporto</span><span class="sxs-lookup"><span data-stu-id="86cd8-342">repubblica italiana passaporto</span></span>  <br/> <span data-ttu-id="86cd8-343">passaporto</span><span class="sxs-lookup"><span data-stu-id="86cd8-343">passaporto</span></span>  <br/> <span data-ttu-id="86cd8-344">passaporto italiana</span><span class="sxs-lookup"><span data-stu-id="86cd8-344">passaporto italiana</span></span>  <br/> <span data-ttu-id="86cd8-345">numero di passaporto</span><span class="sxs-lookup"><span data-stu-id="86cd8-345">passport number</span></span>  <br/> <span data-ttu-id="86cd8-346">italiana passaporto numero</span><span class="sxs-lookup"><span data-stu-id="86cd8-346">italiana passaporto numero</span></span>  <br/> <span data-ttu-id="86cd8-347">Numero passaporto</span><span class="sxs-lookup"><span data-stu-id="86cd8-347">passaporto numero</span></span>  <br/> <span data-ttu-id="86cd8-348">numéro Passeport Italien</span><span class="sxs-lookup"><span data-stu-id="86cd8-348">numéro passeport italien</span></span>  <br/> <span data-ttu-id="86cd8-349">numéro Passeport</span><span class="sxs-lookup"><span data-stu-id="86cd8-349">numéro passeport</span></span>  <br/> |
   
## <a name="latvia"></a><span data-ttu-id="86cd8-350">Lettonia</span><span class="sxs-lookup"><span data-stu-id="86cd8-350">Latvia</span></span>

### <a name="format"></a><span data-ttu-id="86cd8-351">Formato</span><span class="sxs-lookup"><span data-stu-id="86cd8-351">Format</span></span>

<span data-ttu-id="86cd8-352">Due lettere o cifre seguite da sette cifre senza spazi o delimitatori</span><span class="sxs-lookup"><span data-stu-id="86cd8-352">Two letters or digits followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="86cd8-353">Modello</span><span class="sxs-lookup"><span data-stu-id="86cd8-353">Pattern</span></span>

<span data-ttu-id="86cd8-354">Due lettere o cifre seguite da sette cifre:</span><span class="sxs-lookup"><span data-stu-id="86cd8-354">Two letters or digits followed by seven digits:</span></span>
  
- <span data-ttu-id="86cd8-355">Due cifre o lettere (senza distinzione tra maiuscole/minuscole)</span><span class="sxs-lookup"><span data-stu-id="86cd8-355">Two digits or letters (not case sensitive)</span></span>
    
- <span data-ttu-id="86cd8-356">Sette cifre</span><span class="sxs-lookup"><span data-stu-id="86cd8-356">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="86cd8-357">Checksum</span><span class="sxs-lookup"><span data-stu-id="86cd8-357">Checksum</span></span>

<span data-ttu-id="86cd8-358">No</span><span class="sxs-lookup"><span data-stu-id="86cd8-358">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="86cd8-359">Definizione</span><span class="sxs-lookup"><span data-stu-id="86cd8-359">Definition</span></span>

<span data-ttu-id="86cd8-360">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="86cd8-360">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="86cd8-361">L'espressione `Regex_latvia_eu_passport_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="86cd8-361">The regular expression  `Regex_latvia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="86cd8-362">Viene trovata una `Keywords_latvia_eu_passport_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="86cd8-362">A keyword from  `Keywords_latvia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_latvia_eu_passport_number" />
          <Match idRef="Keywords_latvia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="86cd8-363">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="86cd8-363">Keywords</span></span>

<span data-ttu-id="86cd8-364">| |</span><span class="sxs-lookup"><span data-stu-id="86cd8-364"></span></span>
|<span data-ttu-id="86cd8-365">**Keywords_latvia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="86cd8-365">**Keywords_latvia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="86cd8-366">numero di passaporto</span><span class="sxs-lookup"><span data-stu-id="86cd8-366">passport number</span></span>  <br/> <span data-ttu-id="86cd8-367">numero di passaporto lettone</span><span class="sxs-lookup"><span data-stu-id="86cd8-367">latvian passport number</span></span>  <br/> <span data-ttu-id="86cd8-368">Passport No</span><span class="sxs-lookup"><span data-stu-id="86cd8-368">passport no</span></span>  <br/> <span data-ttu-id="86cd8-369">pase numurs</span><span class="sxs-lookup"><span data-stu-id="86cd8-369">pase numurs</span></span>  <br/> |
   
## <a name="lithuania"></a><span data-ttu-id="86cd8-370">Lituania</span><span class="sxs-lookup"><span data-stu-id="86cd8-370">Lithuania</span></span>

### <a name="format"></a><span data-ttu-id="86cd8-371">Formato</span><span class="sxs-lookup"><span data-stu-id="86cd8-371">Format</span></span>

<span data-ttu-id="86cd8-372">Otto cifre o lettere senza spazi o delimitatori</span><span class="sxs-lookup"><span data-stu-id="86cd8-372">Eight digits or letters with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="86cd8-373">Modello</span><span class="sxs-lookup"><span data-stu-id="86cd8-373">Pattern</span></span>

<span data-ttu-id="86cd8-374">Otto cifre o lettere (senza distinzione tra maiuscole e minuscole)</span><span class="sxs-lookup"><span data-stu-id="86cd8-374">Eight digits or letters (not case sensitive)</span></span>
  
### <a name="checksum"></a><span data-ttu-id="86cd8-375">Checksum</span><span class="sxs-lookup"><span data-stu-id="86cd8-375">Checksum</span></span>

<span data-ttu-id="86cd8-376">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="86cd8-376">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="86cd8-377">Definizione</span><span class="sxs-lookup"><span data-stu-id="86cd8-377">Definition</span></span>

<span data-ttu-id="86cd8-378">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="86cd8-378">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="86cd8-379">L'espressione `Regex_lithuania_eu_passport_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="86cd8-379">The regular expression  `Regex_lithuania_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="86cd8-380">Viene trovata una `Keywords_lithuania_eu_passport_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="86cd8-380">A keyword from  `Keywords_lithuania_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_lithuania_eu_passport_number" />
          <Match idRef="Keywords_lithuania_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="86cd8-381">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="86cd8-381">Keywords</span></span>

<span data-ttu-id="86cd8-382">| |</span><span class="sxs-lookup"><span data-stu-id="86cd8-382"></span></span>
|<span data-ttu-id="86cd8-383">**Keywords_lithuania_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="86cd8-383">**Keywords_lithuania_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="86cd8-384">numero di passaporto</span><span class="sxs-lookup"><span data-stu-id="86cd8-384">passport number</span></span>  <br/> <span data-ttu-id="86cd8-385">numero di passaporto di lithunian</span><span class="sxs-lookup"><span data-stu-id="86cd8-385">lithunian passport number</span></span>  <br/> <span data-ttu-id="86cd8-386">Passport No</span><span class="sxs-lookup"><span data-stu-id="86cd8-386">passport no</span></span>  <br/> <span data-ttu-id="86cd8-387">numero di Paso</span><span class="sxs-lookup"><span data-stu-id="86cd8-387">paso numeris</span></span>  <br/> |
   
## <a name="luxemburg"></a><span data-ttu-id="86cd8-388">Lussemburgo</span><span class="sxs-lookup"><span data-stu-id="86cd8-388">Luxemburg</span></span>

### <a name="format"></a><span data-ttu-id="86cd8-389">Formato</span><span class="sxs-lookup"><span data-stu-id="86cd8-389">Format</span></span>

<span data-ttu-id="86cd8-390">Otto cifre o lettere senza spazi o delimitatori</span><span class="sxs-lookup"><span data-stu-id="86cd8-390">Eight digits or letters with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="86cd8-391">Modello</span><span class="sxs-lookup"><span data-stu-id="86cd8-391">Pattern</span></span>

<span data-ttu-id="86cd8-392">Otto cifre o lettere (senza distinzione tra maiuscole e minuscole)</span><span class="sxs-lookup"><span data-stu-id="86cd8-392">Eight digits or letters (not case sensitive)</span></span>
  
### <a name="checksum"></a><span data-ttu-id="86cd8-393">Checksum</span><span class="sxs-lookup"><span data-stu-id="86cd8-393">Checksum</span></span>

<span data-ttu-id="86cd8-394">No</span><span class="sxs-lookup"><span data-stu-id="86cd8-394">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="86cd8-395">Definizione</span><span class="sxs-lookup"><span data-stu-id="86cd8-395">Definition</span></span>

<span data-ttu-id="86cd8-396">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="86cd8-396">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="86cd8-397">L'espressione `Regex_nation_eu_passport_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="86cd8-397">The regular expression  `Regex_nation_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="86cd8-398">Viene trovata una `Keywords_nation_eu_passport_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="86cd8-398">A keyword from  `Keywords_nation_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_nation_eu_passport_number" />
          <Match idRef="Keywords_nation_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="86cd8-399">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="86cd8-399">Keywords</span></span>

<span data-ttu-id="86cd8-400">| |</span><span class="sxs-lookup"><span data-stu-id="86cd8-400"></span></span>
|<span data-ttu-id="86cd8-401">**Keywords_nation_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="86cd8-401">**Keywords_nation_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="86cd8-402">numero di passaporto</span><span class="sxs-lookup"><span data-stu-id="86cd8-402">passport number</span></span>  <br/> <span data-ttu-id="86cd8-403">numero di passaporto lettone</span><span class="sxs-lookup"><span data-stu-id="86cd8-403">latvian passport number</span></span>  <br/> <span data-ttu-id="86cd8-404">Passport No</span><span class="sxs-lookup"><span data-stu-id="86cd8-404">passport no</span></span>  <br/> <span data-ttu-id="86cd8-405">passnummer</span><span class="sxs-lookup"><span data-stu-id="86cd8-405">passnummer</span></span>  <br/> |
   
## <a name="malta"></a><span data-ttu-id="86cd8-406">Malta</span><span class="sxs-lookup"><span data-stu-id="86cd8-406">Malta</span></span>

### <a name="format"></a><span data-ttu-id="86cd8-407">Formato</span><span class="sxs-lookup"><span data-stu-id="86cd8-407">Format</span></span>

<span data-ttu-id="86cd8-408">Sette cifre senza spazi o delimitatori</span><span class="sxs-lookup"><span data-stu-id="86cd8-408">Seven digits without spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="86cd8-409">Modello</span><span class="sxs-lookup"><span data-stu-id="86cd8-409">Pattern</span></span>

 <span data-ttu-id="86cd8-410">Sette cifre</span><span class="sxs-lookup"><span data-stu-id="86cd8-410">Seven digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="86cd8-411">Checksum</span><span class="sxs-lookup"><span data-stu-id="86cd8-411">Checksum</span></span>

<span data-ttu-id="86cd8-412">No</span><span class="sxs-lookup"><span data-stu-id="86cd8-412">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="86cd8-413">Definizione</span><span class="sxs-lookup"><span data-stu-id="86cd8-413">Definition</span></span>

<span data-ttu-id="86cd8-414">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="86cd8-414">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="86cd8-415">L'espressione `Regex_malta_eu_passport_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="86cd8-415">The regular expression  `Regex_malta_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="86cd8-416">Viene trovata una `Keywords_malta_eu_passport_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="86cd8-416">A keyword from  `Keywords_malta_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_malta_eu_passport_number" />
          <Match idRef="Keywords_malta_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="86cd8-417">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="86cd8-417">Keywords</span></span>

<span data-ttu-id="86cd8-418">| |</span><span class="sxs-lookup"><span data-stu-id="86cd8-418"></span></span>
|<span data-ttu-id="86cd8-419">**Keywords_malta_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="86cd8-419">**Keywords_malta_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="86cd8-420">numero di passaporto</span><span class="sxs-lookup"><span data-stu-id="86cd8-420">passport number</span></span>  <br/> <span data-ttu-id="86cd8-421">numero di passaporto maltese</span><span class="sxs-lookup"><span data-stu-id="86cd8-421">maltese passport number</span></span>  <br/> <span data-ttu-id="86cd8-422">Passport No</span><span class="sxs-lookup"><span data-stu-id="86cd8-422">passport no</span></span>  <br/> <span data-ttu-id="86cd8-423">numru tal-passaport</span><span class="sxs-lookup"><span data-stu-id="86cd8-423">numru tal-passaport</span></span>  <br/> |
   
## <a name="netherlands"></a><span data-ttu-id="86cd8-424">Paesi Bassi</span><span class="sxs-lookup"><span data-stu-id="86cd8-424">Netherlands</span></span>

### <a name="format"></a><span data-ttu-id="86cd8-425">Formato</span><span class="sxs-lookup"><span data-stu-id="86cd8-425">Format</span></span>

<span data-ttu-id="86cd8-426">Nove lettere o cifre senza spazi o delimitatori</span><span class="sxs-lookup"><span data-stu-id="86cd8-426">Nine letters or digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="86cd8-427">Modello</span><span class="sxs-lookup"><span data-stu-id="86cd8-427">Pattern</span></span>

<span data-ttu-id="86cd8-428">Nove lettere o cifre</span><span class="sxs-lookup"><span data-stu-id="86cd8-428">Nine letters or digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="86cd8-429">Checksum</span><span class="sxs-lookup"><span data-stu-id="86cd8-429">Checksum</span></span>

<span data-ttu-id="86cd8-430">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="86cd8-430">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="86cd8-431">Definizione</span><span class="sxs-lookup"><span data-stu-id="86cd8-431">Definition</span></span>

<span data-ttu-id="86cd8-432">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="86cd8-432">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="86cd8-433">L'espressione `Regex_netherlands_eu_passport_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="86cd8-433">The regular expression  `Regex_netherlands_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="86cd8-434">Viene trovata una `Keywords_netherlands_eu_passport_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="86cd8-434">A keyword from  `Keywords_netherlands_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_netherlands_eu_passport_number" />
          <Match idRef="Keywords_netherlands_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="86cd8-435">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="86cd8-435">Keywords</span></span>

<span data-ttu-id="86cd8-436">| |</span><span class="sxs-lookup"><span data-stu-id="86cd8-436"></span></span>
|<span data-ttu-id="86cd8-437">**Keywords_netherlands_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="86cd8-437">**Keywords_netherlands_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="86cd8-438">numero di passaporto olandese</span><span class="sxs-lookup"><span data-stu-id="86cd8-438">dutch passport number</span></span>  <br/> <span data-ttu-id="86cd8-439">numero di passaporto</span><span class="sxs-lookup"><span data-stu-id="86cd8-439">passport number</span></span>  <br/> <span data-ttu-id="86cd8-440">numero di passaporto per i Paesi Bassi</span><span class="sxs-lookup"><span data-stu-id="86cd8-440">netherlands passport number</span></span>  <br/> <span data-ttu-id="86cd8-441">Nederlanden PASPOORT Nummer</span><span class="sxs-lookup"><span data-stu-id="86cd8-441">nederlanden paspoort nummer</span></span>  <br/> <span data-ttu-id="86cd8-442">PASPOORT</span><span class="sxs-lookup"><span data-stu-id="86cd8-442">paspoort</span></span>  <br/> <span data-ttu-id="86cd8-443">Nederlanden paspoortnummer</span><span class="sxs-lookup"><span data-stu-id="86cd8-443">nederlanden paspoortnummer</span></span>  <br/> <span data-ttu-id="86cd8-444">paspoortnummer</span><span class="sxs-lookup"><span data-stu-id="86cd8-444">paspoortnummer</span></span>  <br/> |
   
## <a name="poland"></a><span data-ttu-id="86cd8-445">Polonia</span><span class="sxs-lookup"><span data-stu-id="86cd8-445">Poland</span></span>

<span data-ttu-id="86cd8-446">Per informazioni dettagliate, vedere la sezione "Poland Passport Number" in [che cosa cercano i tipi di informazioni riservate](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="86cd8-446">For details, see the section "Poland Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="portugal"></a><span data-ttu-id="86cd8-447">Portogallo</span><span class="sxs-lookup"><span data-stu-id="86cd8-447">Portugal</span></span>

### <a name="format"></a><span data-ttu-id="86cd8-448">Formato</span><span class="sxs-lookup"><span data-stu-id="86cd8-448">Format</span></span>

<span data-ttu-id="86cd8-449">Una lettera seguita da sei cifre senza spazi o delimitatori</span><span class="sxs-lookup"><span data-stu-id="86cd8-449">One letter followed by six digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="86cd8-450">Modello</span><span class="sxs-lookup"><span data-stu-id="86cd8-450">Pattern</span></span>

<span data-ttu-id="86cd8-451">Una lettera seguita da sei cifre:</span><span class="sxs-lookup"><span data-stu-id="86cd8-451">One letter followed by six digits:</span></span>
  
- <span data-ttu-id="86cd8-452">Una lettera (senza distinzione tra maiuscole/minuscole)</span><span class="sxs-lookup"><span data-stu-id="86cd8-452">One letter (not case sensitive)</span></span>
    
- <span data-ttu-id="86cd8-453">Sei cifre</span><span class="sxs-lookup"><span data-stu-id="86cd8-453">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="86cd8-454">Checksum</span><span class="sxs-lookup"><span data-stu-id="86cd8-454">Checksum</span></span>

<span data-ttu-id="86cd8-455">No</span><span class="sxs-lookup"><span data-stu-id="86cd8-455">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="86cd8-456">Definizione</span><span class="sxs-lookup"><span data-stu-id="86cd8-456">Definition</span></span>

<span data-ttu-id="86cd8-457">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="86cd8-457">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="86cd8-458">L'espressione `Regex_portugal_eu_passport_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="86cd8-458">The regular expression  `Regex_portugal_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="86cd8-459">Viene trovata una `Keywords_portugal_eu_passport_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="86cd8-459">A keyword from  `Keywords_portugal_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_portugal_eu_passport_number" />
          <Match idRef="Keywords_portugal_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="86cd8-460">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="86cd8-460">Keywords</span></span>

<span data-ttu-id="86cd8-461">| |</span><span class="sxs-lookup"><span data-stu-id="86cd8-461"></span></span>
|<span data-ttu-id="86cd8-462">**Keywords_portugal_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="86cd8-462">**Keywords_portugal_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="86cd8-463">numero di passaporto</span><span class="sxs-lookup"><span data-stu-id="86cd8-463">passport number</span></span>  <br/> <span data-ttu-id="86cd8-464">numero di passaporto portoghese</span><span class="sxs-lookup"><span data-stu-id="86cd8-464">portuguese passport number</span></span>  <br/> <span data-ttu-id="86cd8-465">Passport No</span><span class="sxs-lookup"><span data-stu-id="86cd8-465">passport no</span></span>  <br/> <span data-ttu-id="86cd8-466">número do passaporte</span><span class="sxs-lookup"><span data-stu-id="86cd8-466">número do passaporte</span></span>  <br/> |
   
## <a name="romania"></a><span data-ttu-id="86cd8-467">Romania</span><span class="sxs-lookup"><span data-stu-id="86cd8-467">Romania</span></span>

### <a name="format"></a><span data-ttu-id="86cd8-468">Formato</span><span class="sxs-lookup"><span data-stu-id="86cd8-468">Format</span></span>

<span data-ttu-id="86cd8-469">Otto o nove cifre senza spazi e delimitatori</span><span class="sxs-lookup"><span data-stu-id="86cd8-469">Eight or nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="86cd8-470">Modello</span><span class="sxs-lookup"><span data-stu-id="86cd8-470">Pattern</span></span>

<span data-ttu-id="86cd8-471">Otto o nove cifre</span><span class="sxs-lookup"><span data-stu-id="86cd8-471">Eight or nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="86cd8-472">Checksum</span><span class="sxs-lookup"><span data-stu-id="86cd8-472">Checksum</span></span>

<span data-ttu-id="86cd8-473">No</span><span class="sxs-lookup"><span data-stu-id="86cd8-473">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="86cd8-474">Definizione</span><span class="sxs-lookup"><span data-stu-id="86cd8-474">Definition</span></span>

<span data-ttu-id="86cd8-475">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="86cd8-475">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="86cd8-476">L'espressione `Regex_romania_eu_passport_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="86cd8-476">The regular expression  `Regex_romania_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="86cd8-477">Viene trovata una `Keywords_romania_eu_passport_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="86cd8-477">A keyword from  `Keywords_romania_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_romania_eu_passport_number" />
          <Match idRef="Keywords_romania_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="86cd8-478">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="86cd8-478">Keywords</span></span>

<span data-ttu-id="86cd8-479">| |</span><span class="sxs-lookup"><span data-stu-id="86cd8-479"></span></span>
|<span data-ttu-id="86cd8-480">**Keywords_romania_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="86cd8-480">**Keywords_romania_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="86cd8-481">numero di passaporto</span><span class="sxs-lookup"><span data-stu-id="86cd8-481">passport number</span></span>  <br/> <span data-ttu-id="86cd8-482">numero di passaporto rumeno</span><span class="sxs-lookup"><span data-stu-id="86cd8-482">romanian passport number</span></span>  <br/> <span data-ttu-id="86cd8-483">Passport No</span><span class="sxs-lookup"><span data-stu-id="86cd8-483">passport no</span></span>  <br/> <span data-ttu-id="86cd8-484">numărul pașaportului</span><span class="sxs-lookup"><span data-stu-id="86cd8-484">numărul pașaportului</span></span>  <br/> |
   
## <a name="slovakia"></a><span data-ttu-id="86cd8-485">Slovacchia</span><span class="sxs-lookup"><span data-stu-id="86cd8-485">Slovakia</span></span>

### <a name="format"></a><span data-ttu-id="86cd8-486">Formato</span><span class="sxs-lookup"><span data-stu-id="86cd8-486">Format</span></span>

<span data-ttu-id="86cd8-487">Una cifra o una lettera seguita da sette cifre senza spazi o delimitatori</span><span class="sxs-lookup"><span data-stu-id="86cd8-487">One digit or letter followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="86cd8-488">Modello</span><span class="sxs-lookup"><span data-stu-id="86cd8-488">Pattern</span></span>

<span data-ttu-id="86cd8-489">Una cifra o una lettera (senza distinzione tra maiuscole/minuscole) seguita da sette cifre</span><span class="sxs-lookup"><span data-stu-id="86cd8-489">One digit or letter (not case sensitive) followed by seven digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="86cd8-490">Checksum</span><span class="sxs-lookup"><span data-stu-id="86cd8-490">Checksum</span></span>

<span data-ttu-id="86cd8-491">No</span><span class="sxs-lookup"><span data-stu-id="86cd8-491">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="86cd8-492">Definizione</span><span class="sxs-lookup"><span data-stu-id="86cd8-492">Definition</span></span>

<span data-ttu-id="86cd8-493">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="86cd8-493">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="86cd8-494">L'espressione `Regex_slovakia_eu_passport_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="86cd8-494">The regular expression  `Regex_slovakia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="86cd8-495">Viene trovata una `Keywords_slovakia_eu_passport_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="86cd8-495">A keyword from  `Keywords_slovakia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovakia_eu_passport_number" />
          <Match idRef="Keywords_slovakia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="86cd8-496">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="86cd8-496">Keywords</span></span>

<span data-ttu-id="86cd8-497">| |</span><span class="sxs-lookup"><span data-stu-id="86cd8-497"></span></span>
|<span data-ttu-id="86cd8-498">**Keywords_slovakia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="86cd8-498">**Keywords_slovakia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="86cd8-499">numero di passaporto</span><span class="sxs-lookup"><span data-stu-id="86cd8-499">passport number</span></span>  <br/> <span data-ttu-id="86cd8-500">numero di passaporto slovacco</span><span class="sxs-lookup"><span data-stu-id="86cd8-500">slovakian passport number</span></span>  <br/> <span data-ttu-id="86cd8-501">Passport No</span><span class="sxs-lookup"><span data-stu-id="86cd8-501">passport no</span></span>  <br/> <span data-ttu-id="86cd8-502">číslo Pasu</span><span class="sxs-lookup"><span data-stu-id="86cd8-502">číslo pasu</span></span>  <br/> |
   
## <a name="slovenia"></a><span data-ttu-id="86cd8-503">Slovenia</span><span class="sxs-lookup"><span data-stu-id="86cd8-503">Slovenia</span></span>

### <a name="format"></a><span data-ttu-id="86cd8-504">Formato</span><span class="sxs-lookup"><span data-stu-id="86cd8-504">Format</span></span>

<span data-ttu-id="86cd8-505">Due lettere seguite da sette cifre senza spazi o delimitatori</span><span class="sxs-lookup"><span data-stu-id="86cd8-505">Two letters followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="86cd8-506">Modello</span><span class="sxs-lookup"><span data-stu-id="86cd8-506">Pattern</span></span>

<span data-ttu-id="86cd8-507">Due lettere seguite da sette cifre:</span><span class="sxs-lookup"><span data-stu-id="86cd8-507">Two letters followed by seven digits:</span></span>
  
- <span data-ttu-id="86cd8-508">La lettera "P"</span><span class="sxs-lookup"><span data-stu-id="86cd8-508">The letter "P"</span></span>
    
- <span data-ttu-id="86cd8-509">Una lettera maiuscola</span><span class="sxs-lookup"><span data-stu-id="86cd8-509">One uppercase letter</span></span>
    
- <span data-ttu-id="86cd8-510">Sette cifre</span><span class="sxs-lookup"><span data-stu-id="86cd8-510">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="86cd8-511">Checksum</span><span class="sxs-lookup"><span data-stu-id="86cd8-511">Checksum</span></span>

<span data-ttu-id="86cd8-512">No</span><span class="sxs-lookup"><span data-stu-id="86cd8-512">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="86cd8-513">Definizione</span><span class="sxs-lookup"><span data-stu-id="86cd8-513">Definition</span></span>

<span data-ttu-id="86cd8-514">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="86cd8-514">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="86cd8-515">L'espressione `Regex_slovenia_eu_passport_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="86cd8-515">The regular expression  `Regex_slovenia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="86cd8-516">Viene trovata una `Keywords_slovenia_eu_passport_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="86cd8-516">A keyword from  `Keywords_slovenia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovenia_eu_passport_number" />
          <Match idRef="Keywords_slovenia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="86cd8-517">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="86cd8-517">Keywords</span></span>

<span data-ttu-id="86cd8-518">| |</span><span class="sxs-lookup"><span data-stu-id="86cd8-518"></span></span>
|<span data-ttu-id="86cd8-519">**Keywords_slovenia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="86cd8-519">**Keywords_slovenia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="86cd8-520">numero di passaporto</span><span class="sxs-lookup"><span data-stu-id="86cd8-520">passport number</span></span>  <br/> <span data-ttu-id="86cd8-521">numero di passaporto sloveno</span><span class="sxs-lookup"><span data-stu-id="86cd8-521">slovenian passport number</span></span>  <br/> <span data-ttu-id="86cd8-522">Passport No</span><span class="sxs-lookup"><span data-stu-id="86cd8-522">passport no</span></span>  <br/> <span data-ttu-id="86cd8-523">številka potnega lista</span><span class="sxs-lookup"><span data-stu-id="86cd8-523">številka potnega lista</span></span>  <br/> |
   
## <a name="spain"></a><span data-ttu-id="86cd8-524">Spagna</span><span class="sxs-lookup"><span data-stu-id="86cd8-524">Spain</span></span>

### <a name="format"></a><span data-ttu-id="86cd8-525">Formato</span><span class="sxs-lookup"><span data-stu-id="86cd8-525">Format</span></span>

<span data-ttu-id="86cd8-526">Combinazione di otto o nove caratteri di lettere e numeri senza spazi o delimitatori</span><span class="sxs-lookup"><span data-stu-id="86cd8-526">An eight- or nine-character combination of letters and numbers with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="86cd8-527">Modello</span><span class="sxs-lookup"><span data-stu-id="86cd8-527">Pattern</span></span>

<span data-ttu-id="86cd8-528">Combinazione di lettere e numeri di otto o nove caratteri:</span><span class="sxs-lookup"><span data-stu-id="86cd8-528">An eight- or nine-character combination of letters and numbers:</span></span>
  
-  <span data-ttu-id="86cd8-529">Due cifre o lettere</span><span class="sxs-lookup"><span data-stu-id="86cd8-529">Two digits or letters</span></span> 
    
- <span data-ttu-id="86cd8-530">Una cifra o una lettera (facoltativa)</span><span class="sxs-lookup"><span data-stu-id="86cd8-530">One digit or letter (optional)</span></span>
    
- <span data-ttu-id="86cd8-531">Sei cifre</span><span class="sxs-lookup"><span data-stu-id="86cd8-531">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="86cd8-532">Checksum</span><span class="sxs-lookup"><span data-stu-id="86cd8-532">Checksum</span></span>

<span data-ttu-id="86cd8-533">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="86cd8-533">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="86cd8-534">Definizione</span><span class="sxs-lookup"><span data-stu-id="86cd8-534">Definition</span></span>

<span data-ttu-id="86cd8-535">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="86cd8-535">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="86cd8-536">L'espressione `Regex_spain_eu_passport_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="86cd8-536">The regular expression  `Regex_spain_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="86cd8-537">Viene trovata una `Keywords_spain_eu_passport_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="86cd8-537">A keyword from  `Keywords_spain_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_spain_eu_passport_number" />
          <Match idRef="Keywords_spain_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="86cd8-538">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="86cd8-538">Keywords</span></span>

<span data-ttu-id="86cd8-539">| |</span><span class="sxs-lookup"><span data-stu-id="86cd8-539"></span></span>
|<span data-ttu-id="86cd8-540">**Keywords_spain_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="86cd8-540">**Keywords_spain_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="86cd8-541">passport</span><span class="sxs-lookup"><span data-stu-id="86cd8-541">passport</span></span>  <br/> <span data-ttu-id="86cd8-542">passaporto della Spagna</span><span class="sxs-lookup"><span data-stu-id="86cd8-542">spain passport</span></span>  <br/> <span data-ttu-id="86cd8-543">libro del passaporto</span><span class="sxs-lookup"><span data-stu-id="86cd8-543">passport book</span></span>  <br/> <span data-ttu-id="86cd8-544">numero di passaporto</span><span class="sxs-lookup"><span data-stu-id="86cd8-544">passport number</span></span>  <br/> <span data-ttu-id="86cd8-545">Passport No</span><span class="sxs-lookup"><span data-stu-id="86cd8-545">passport no</span></span>  <br/> <span data-ttu-id="86cd8-546">libreta pasaporte</span><span class="sxs-lookup"><span data-stu-id="86cd8-546">libreta pasaporte</span></span>  <br/> <span data-ttu-id="86cd8-547">número pasaporte</span><span class="sxs-lookup"><span data-stu-id="86cd8-547">número pasaporte</span></span>  <br/> <span data-ttu-id="86cd8-548">pasaporte España</span><span class="sxs-lookup"><span data-stu-id="86cd8-548">españa pasaporte</span></span>  <br/> <span data-ttu-id="86cd8-549">pasaporte</span><span class="sxs-lookup"><span data-stu-id="86cd8-549">pasaporte</span></span>  <br/> |
   
## <a name="sweden"></a><span data-ttu-id="86cd8-550">Svezia</span><span class="sxs-lookup"><span data-stu-id="86cd8-550">Sweden</span></span>

<span data-ttu-id="86cd8-551">Per informazioni dettagliate, vedere la sezione "Sweden Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="86cd8-551">For details, see the section "Sweden Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="uk"></a><span data-ttu-id="86cd8-552">Regno Unito</span><span class="sxs-lookup"><span data-stu-id="86cd8-552">UK</span></span>

<span data-ttu-id="86cd8-p103">Per informazioni dettagliate, vedere la sezione "numero di passaporto degli Stati Uniti/Regno Unito" in [che cosa cercano i tipi di informazioni riservate](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="86cd8-p103">For details, see the section "U.S. / U.K. Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="86cd8-555">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="86cd8-555">See also</span></span>

[<span data-ttu-id="86cd8-556">Cosa individuano le tipologie di informazioni sensibili</span><span class="sxs-lookup"><span data-stu-id="86cd8-556">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)

