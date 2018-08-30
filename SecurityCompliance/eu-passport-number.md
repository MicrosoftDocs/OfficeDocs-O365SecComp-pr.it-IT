---
title: Numero di passaporto UE
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 8/16/2018
ms.audience: Admin
ms.topic: reference
ms.service: o365-administration
localization_priority: Normal
ms.assetid: 8c00df57-9fb3-459c-ba87-40480c87bd55
description: Questo argomento viene illustrato quali criteri di criterio DLP perdita dei dati Cerca qualora venga rilevato un tipo di informazione sensibile il numero di passaporto UE. Questo tipo di informazioni riservate definisce le diverse combinazioni, parole chiave e altri elementi di prova per ogni paese.
ms.openlocfilehash: 71acc39b885c057e1771ec13b2f3c25017ac1bb6
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/27/2018
ms.locfileid: "22530884"
---
# <a name="eu-passport-number"></a><span data-ttu-id="99878-104">Numero di passaporto UE</span><span class="sxs-lookup"><span data-stu-id="99878-104">EU Passport Number</span></span>

<span data-ttu-id="99878-p102">Questo argomento viene illustrato quali criteri di criterio DLP perdita dei dati Cerca qualora venga rilevato un tipo di informazione sensibile il numero di passaporto UE. Questo tipo di informazioni riservate definisce le diverse combinazioni, parole chiave e altri elementi di prova per ogni paese.</span><span class="sxs-lookup"><span data-stu-id="99878-p102">This topic shows what a data loss prevention (DLP) policy looks for when it detects the EU Passport Number sensitive information type. This sensitive information type defines different patterns, keywords, and other evidence for each country.</span></span>
  
## <a name="austria"></a><span data-ttu-id="99878-107">Austria</span><span class="sxs-lookup"><span data-stu-id="99878-107">Austria</span></span>

### <a name="format"></a><span data-ttu-id="99878-108">Formato</span><span class="sxs-lookup"><span data-stu-id="99878-108">Format</span></span>

<span data-ttu-id="99878-109">Una lettera seguita da sette cifre e da uno spazio facoltativo</span><span class="sxs-lookup"><span data-stu-id="99878-109">One letter followed by an optional space and seven digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="99878-110">Modello</span><span class="sxs-lookup"><span data-stu-id="99878-110">Pattern</span></span>

<span data-ttu-id="99878-111">Una combinazione di una lettera, sette cifre e uno spazio:</span><span class="sxs-lookup"><span data-stu-id="99878-111">A combination of one letter, seven digits, and one space:</span></span>
  
- <span data-ttu-id="99878-112">Una lettera (senza distinzione tra maiuscole/minuscole)</span><span class="sxs-lookup"><span data-stu-id="99878-112">One letter (not case sensitive)</span></span>
    
- <span data-ttu-id="99878-113">Uno spazio (facoltativo)</span><span class="sxs-lookup"><span data-stu-id="99878-113">One space (optional)</span></span>
    
- <span data-ttu-id="99878-114">Sette cifre</span><span class="sxs-lookup"><span data-stu-id="99878-114">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="99878-115">Checksum</span><span class="sxs-lookup"><span data-stu-id="99878-115">Checksum</span></span>

<span data-ttu-id="99878-116">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="99878-116">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="99878-117">Definizione</span><span class="sxs-lookup"><span data-stu-id="99878-117">Definition</span></span>

<span data-ttu-id="99878-118">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="99878-118">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="99878-119">L'espressione regolare `Regex_austria_eu_passport_number` consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="99878-119">The regular expression  `Regex_austria_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="99878-120">Una parola chiave da `Keywords_austria_eu_passport_number` viene trovato.</span><span class="sxs-lookup"><span data-stu-id="99878-120">A keyword from  `Keywords_austria_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_austria_eu_passport_number" />
          <Match idRef="Keywords_austria_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="99878-121">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="99878-121">Keywords</span></span>

<span data-ttu-id="99878-122">| |</span><span class="sxs-lookup"><span data-stu-id="99878-122"></span></span>
|<span data-ttu-id="99878-123">**Keywords_austria_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="99878-123">**Keywords_austria_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="99878-124">numero di passaporto</span><span class="sxs-lookup"><span data-stu-id="99878-124">passport number</span></span>  <br/> <span data-ttu-id="99878-125">numero di passaporto austriaco</span><span class="sxs-lookup"><span data-stu-id="99878-125">austrian passport number</span></span>  <br/> <span data-ttu-id="99878-126">Passport non</span><span class="sxs-lookup"><span data-stu-id="99878-126">passport no</span></span>  <br/> <span data-ttu-id="99878-127">reisepass</span><span class="sxs-lookup"><span data-stu-id="99878-127">reisepass</span></span>  <br/> <span data-ttu-id="99878-128">österreichisch reisepass</span><span class="sxs-lookup"><span data-stu-id="99878-128">österreichisch reisepass</span></span>  <br/> |
   
## <a name="belgium"></a><span data-ttu-id="99878-129">Belgio</span><span class="sxs-lookup"><span data-stu-id="99878-129">Belgium</span></span>

### <a name="format"></a><span data-ttu-id="99878-130">Formato</span><span class="sxs-lookup"><span data-stu-id="99878-130">Format</span></span>

<span data-ttu-id="99878-131">Due lettere seguite da sei cifre senza spazi o delimitatori</span><span class="sxs-lookup"><span data-stu-id="99878-131">Two letters followed by six digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="99878-132">Modello</span><span class="sxs-lookup"><span data-stu-id="99878-132">Pattern</span></span>

<span data-ttu-id="99878-133">Due lettere e seguita da sei cifre</span><span class="sxs-lookup"><span data-stu-id="99878-133">Two letters and followed by six digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="99878-134">Checksum</span><span class="sxs-lookup"><span data-stu-id="99878-134">Checksum</span></span>

<span data-ttu-id="99878-135">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="99878-135">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="99878-136">Definizione</span><span class="sxs-lookup"><span data-stu-id="99878-136">Definition</span></span>

<span data-ttu-id="99878-137">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="99878-137">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="99878-138">L'espressione regolare `Regex_belgium_eu_passport_number` consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="99878-138">The regular expression  `Regex_belgium_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="99878-139">Una parola chiave da `Keywords_belgium_eu_passport_number` viene trovato.</span><span class="sxs-lookup"><span data-stu-id="99878-139">A keyword from  `Keywords_belgium_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_belgium__eu_passport_number" />
          <Match idRef="Keywords_belgium_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="99878-140">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="99878-140">Keywords</span></span>

<span data-ttu-id="99878-141">| |</span><span class="sxs-lookup"><span data-stu-id="99878-141"></span></span>
|<span data-ttu-id="99878-142">**Keywords_belgium_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="99878-142">**Keywords_belgium_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="99878-143">numero di passaporto</span><span class="sxs-lookup"><span data-stu-id="99878-143">passport number</span></span>  <br/> <span data-ttu-id="99878-144">numero di passaporto belga</span><span class="sxs-lookup"><span data-stu-id="99878-144">belgian passport number</span></span>  <br/> <span data-ttu-id="99878-145">Passport non</span><span class="sxs-lookup"><span data-stu-id="99878-145">passport no</span></span>  <br/> <span data-ttu-id="99878-146">paspoort</span><span class="sxs-lookup"><span data-stu-id="99878-146">paspoort</span></span>  <br/> <span data-ttu-id="99878-147">paspoortnummer</span><span class="sxs-lookup"><span data-stu-id="99878-147">paspoortnummer</span></span>  <br/> <span data-ttu-id="99878-148">reisepass kein</span><span class="sxs-lookup"><span data-stu-id="99878-148">reisepass kein</span></span>  <br/> <span data-ttu-id="99878-149">reisepass</span><span class="sxs-lookup"><span data-stu-id="99878-149">reisepass</span></span>  <br/> |
   
## <a name="bulgaria"></a><span data-ttu-id="99878-150">Bulgaria</span><span class="sxs-lookup"><span data-stu-id="99878-150">Bulgaria</span></span>

### <a name="format"></a><span data-ttu-id="99878-151">Formato</span><span class="sxs-lookup"><span data-stu-id="99878-151">Format</span></span>

<span data-ttu-id="99878-152">Nove cifre senza spazi e i delimitatori</span><span class="sxs-lookup"><span data-stu-id="99878-152">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="99878-153">Modello</span><span class="sxs-lookup"><span data-stu-id="99878-153">Pattern</span></span>

 <span data-ttu-id="99878-154">9 cifre</span><span class="sxs-lookup"><span data-stu-id="99878-154">Nine digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="99878-155">Checksum</span><span class="sxs-lookup"><span data-stu-id="99878-155">Checksum</span></span>

<span data-ttu-id="99878-156">No</span><span class="sxs-lookup"><span data-stu-id="99878-156">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="99878-157">Definizione</span><span class="sxs-lookup"><span data-stu-id="99878-157">Definition</span></span>

<span data-ttu-id="99878-158">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="99878-158">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="99878-159">L'espressione regolare `Regex_bulgaria_eu_passport_number` consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="99878-159">The regular expression  `Regex_bulgaria_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="99878-160">Una parola chiave da `Keywords_bulgaria_eu_passport_number` viene trovato.</span><span class="sxs-lookup"><span data-stu-id="99878-160">A keyword from  `Keywords_bulgaria_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_bulgaria_eu_passport_number" />
          <Match idRef="Keywords_bulgaria_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="99878-161">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="99878-161">Keywords</span></span>

<span data-ttu-id="99878-162">| |</span><span class="sxs-lookup"><span data-stu-id="99878-162"></span></span>
|<span data-ttu-id="99878-163">**Keywords_bulgaria_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="99878-163">**Keywords_bulgaria_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="99878-164">numero di passaporto</span><span class="sxs-lookup"><span data-stu-id="99878-164">passport number</span></span>  <br/> <span data-ttu-id="99878-165">numero di passaporto bulgaro</span><span class="sxs-lookup"><span data-stu-id="99878-165">bulgarian passport number</span></span>  <br/> <span data-ttu-id="99878-166">Passport non</span><span class="sxs-lookup"><span data-stu-id="99878-166">passport no</span></span>  <br/> <span data-ttu-id="99878-167">НОМЕР НА ПАСПОРТА</span><span class="sxs-lookup"><span data-stu-id="99878-167">номер на паспорта</span></span>  <br/> |
   
## <a name="croatia"></a><span data-ttu-id="99878-168">Croazia</span><span class="sxs-lookup"><span data-stu-id="99878-168">Croatia</span></span>

### <a name="format"></a><span data-ttu-id="99878-169">Formato</span><span class="sxs-lookup"><span data-stu-id="99878-169">Format</span></span>

<span data-ttu-id="99878-170">Nove cifre senza spazi e i delimitatori</span><span class="sxs-lookup"><span data-stu-id="99878-170">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="99878-171">Modello</span><span class="sxs-lookup"><span data-stu-id="99878-171">Pattern</span></span>

 <span data-ttu-id="99878-172">9 cifre</span><span class="sxs-lookup"><span data-stu-id="99878-172">Nine digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="99878-173">Checksum</span><span class="sxs-lookup"><span data-stu-id="99878-173">Checksum</span></span>

<span data-ttu-id="99878-174">No</span><span class="sxs-lookup"><span data-stu-id="99878-174">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="99878-175">Definizione</span><span class="sxs-lookup"><span data-stu-id="99878-175">Definition</span></span>

<span data-ttu-id="99878-176">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="99878-176">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="99878-177">L'espressione regolare `Regex_croatia_eu_passport_number` consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="99878-177">The regular expression  `Regex_croatia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="99878-178">Una parola chiave da `Keywords_croatia_eu_passport_number` viene trovato.</span><span class="sxs-lookup"><span data-stu-id="99878-178">A keyword from  `Keywords_croatia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_croatia_eu_passport_number" />
          <Match idRef="Keywords_croatia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="99878-179">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="99878-179">Keywords</span></span>

<span data-ttu-id="99878-180">| |</span><span class="sxs-lookup"><span data-stu-id="99878-180"></span></span>
|<span data-ttu-id="99878-181">**Keywords_croatia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="99878-181">**Keywords_croatia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="99878-182">numero di passaporto</span><span class="sxs-lookup"><span data-stu-id="99878-182">passport number</span></span>  <br/> <span data-ttu-id="99878-183">numero di passaporto croato</span><span class="sxs-lookup"><span data-stu-id="99878-183">croatian passport number</span></span>  <br/> <span data-ttu-id="99878-184">Passport non</span><span class="sxs-lookup"><span data-stu-id="99878-184">passport no</span></span>  <br/> <span data-ttu-id="99878-185">broj putovnice</span><span class="sxs-lookup"><span data-stu-id="99878-185">broj putovnice</span></span>  <br/> |
   
## <a name="cyprus"></a><span data-ttu-id="99878-186">Cipro</span><span class="sxs-lookup"><span data-stu-id="99878-186">Cyprus</span></span>

### <a name="format"></a><span data-ttu-id="99878-187">Formato</span><span class="sxs-lookup"><span data-stu-id="99878-187">Format</span></span>

<span data-ttu-id="99878-188">Una lettera seguita da 6 a 8 cifre senza spazi o delimitatori</span><span class="sxs-lookup"><span data-stu-id="99878-188">One letter followed by 6-8 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="99878-189">Modello</span><span class="sxs-lookup"><span data-stu-id="99878-189">Pattern</span></span>

<span data-ttu-id="99878-190">Una lettera seguita da sei a otto cifre</span><span class="sxs-lookup"><span data-stu-id="99878-190">One letter followed by six to eight digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="99878-191">Checksum</span><span class="sxs-lookup"><span data-stu-id="99878-191">Checksum</span></span>

<span data-ttu-id="99878-192">No</span><span class="sxs-lookup"><span data-stu-id="99878-192">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="99878-193">Definizione</span><span class="sxs-lookup"><span data-stu-id="99878-193">Definition</span></span>

<span data-ttu-id="99878-194">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="99878-194">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="99878-195">L'espressione regolare `Regex_cyprus_eu_passport_number` consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="99878-195">The regular expression  `Regex_cyprus_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="99878-196">Una parola chiave da `Keywords_cyprus_eu_passport_number` viene trovato.</span><span class="sxs-lookup"><span data-stu-id="99878-196">A keyword from  `Keywords_cyprus_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_cyprus_eu_passport_number" />
          <Match idRef="Keywords_cyprus_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="99878-197">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="99878-197">Keywords</span></span>

<span data-ttu-id="99878-198">| |</span><span class="sxs-lookup"><span data-stu-id="99878-198"></span></span>
|<span data-ttu-id="99878-199">**Keywords_cyprus_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="99878-199">**Keywords_cyprus_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="99878-200">numero di passaporto</span><span class="sxs-lookup"><span data-stu-id="99878-200">passport number</span></span>  <br/> <span data-ttu-id="99878-201">numero di passaporto Cipro</span><span class="sxs-lookup"><span data-stu-id="99878-201">cyprus passport number</span></span>  <br/> <span data-ttu-id="99878-202">Passport non</span><span class="sxs-lookup"><span data-stu-id="99878-202">passport no</span></span>  <br/> <span data-ttu-id="99878-203">ΑΡΙΘΜΌ ΔΙΑΒΑΤΗΡΊΟΥ</span><span class="sxs-lookup"><span data-stu-id="99878-203">αριθμό διαβατηρίου</span></span>  <br/> |
   
## <a name="czech-republic"></a><span data-ttu-id="99878-204">Repubblica Ceca</span><span class="sxs-lookup"><span data-stu-id="99878-204">Czech Republic</span></span>

### <a name="format"></a><span data-ttu-id="99878-205">Formato</span><span class="sxs-lookup"><span data-stu-id="99878-205">Format</span></span>

<span data-ttu-id="99878-206">Otto cifre senza spazi o delimitatori</span><span class="sxs-lookup"><span data-stu-id="99878-206">Eight digits without spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="99878-207">Modello</span><span class="sxs-lookup"><span data-stu-id="99878-207">Pattern</span></span>

<span data-ttu-id="99878-208">Otto cifre senza spazi o delimitatori</span><span class="sxs-lookup"><span data-stu-id="99878-208">Eight digits without spaces or delimiters</span></span>
  
### <a name="checksum"></a><span data-ttu-id="99878-209">Checksum</span><span class="sxs-lookup"><span data-stu-id="99878-209">Checksum</span></span>

<span data-ttu-id="99878-210">No</span><span class="sxs-lookup"><span data-stu-id="99878-210">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="99878-211">Definizione</span><span class="sxs-lookup"><span data-stu-id="99878-211">Definition</span></span>

<span data-ttu-id="99878-212">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="99878-212">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="99878-213">L'espressione regolare `Regex_czech_republic_eu_passport_number` consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="99878-213">The regular expression  `Regex_czech_republic_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="99878-214">Una parola chiave da `Keywords_czech_republic_eu_passport_number` viene trovato.</span><span class="sxs-lookup"><span data-stu-id="99878-214">A keyword from  `Keywords_czech_republic_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_czech_republic_eu_passport_number" />
          <Match idRef="Keywords_czech_republic_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="99878-215">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="99878-215">Keywords</span></span>

<span data-ttu-id="99878-216">| |</span><span class="sxs-lookup"><span data-stu-id="99878-216"></span></span>
|<span data-ttu-id="99878-217">**Keywords_czech_republic_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="99878-217">**Keywords_czech_republic_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="99878-218">numero di passaporto</span><span class="sxs-lookup"><span data-stu-id="99878-218">passport number</span></span>  <br/> <span data-ttu-id="99878-219">numero di passaporto ceca</span><span class="sxs-lookup"><span data-stu-id="99878-219">czech passport number</span></span>  <br/> <span data-ttu-id="99878-220">Passport non</span><span class="sxs-lookup"><span data-stu-id="99878-220">passport no</span></span>  <br/> <span data-ttu-id="99878-221">pas cestovní</span><span class="sxs-lookup"><span data-stu-id="99878-221">cestovní pas</span></span>  <br/> <span data-ttu-id="99878-222">PAS</span><span class="sxs-lookup"><span data-stu-id="99878-222">pas</span></span>  <br/> |
   
## <a name="denmark"></a><span data-ttu-id="99878-223">Danimarca</span><span class="sxs-lookup"><span data-stu-id="99878-223">Denmark</span></span>

### <a name="format"></a><span data-ttu-id="99878-224">Formato</span><span class="sxs-lookup"><span data-stu-id="99878-224">Format</span></span>

<span data-ttu-id="99878-225">Nove cifre senza spazi e i delimitatori</span><span class="sxs-lookup"><span data-stu-id="99878-225">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="99878-226">Modello</span><span class="sxs-lookup"><span data-stu-id="99878-226">Pattern</span></span>

 <span data-ttu-id="99878-227">9 cifre</span><span class="sxs-lookup"><span data-stu-id="99878-227">Nine digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="99878-228">Checksum</span><span class="sxs-lookup"><span data-stu-id="99878-228">Checksum</span></span>

<span data-ttu-id="99878-229">No</span><span class="sxs-lookup"><span data-stu-id="99878-229">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="99878-230">Definizione</span><span class="sxs-lookup"><span data-stu-id="99878-230">Definition</span></span>

<span data-ttu-id="99878-231">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="99878-231">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="99878-232">L'espressione regolare `Regex_denmark_eu_passport_number` consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="99878-232">The regular expression  `Regex_denmark_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="99878-233">Una parola chiave da `Keywords_denmark_eu_passport_number` viene trovato.</span><span class="sxs-lookup"><span data-stu-id="99878-233">A keyword from  `Keywords_denmark_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_denmark_eu_passport_number" />
          <Match idRef="Keywords_denmark_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="99878-234">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="99878-234">Keywords</span></span>

<span data-ttu-id="99878-235">| |</span><span class="sxs-lookup"><span data-stu-id="99878-235"></span></span>
|<span data-ttu-id="99878-236">**Keywords_denmark_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="99878-236">**Keywords_denmark_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="99878-237">numero di passaporto</span><span class="sxs-lookup"><span data-stu-id="99878-237">passport number</span></span>  <br/> <span data-ttu-id="99878-238">numero di passaporto danese</span><span class="sxs-lookup"><span data-stu-id="99878-238">danish passport number</span></span>  <br/> <span data-ttu-id="99878-239">Passport non</span><span class="sxs-lookup"><span data-stu-id="99878-239">passport no</span></span>  <br/> <span data-ttu-id="99878-240">PAS</span><span class="sxs-lookup"><span data-stu-id="99878-240">pas</span></span>  <br/> <span data-ttu-id="99878-241">pasnummer</span><span class="sxs-lookup"><span data-stu-id="99878-241">pasnummer</span></span>  <br/> |
   
## <a name="estonia"></a><span data-ttu-id="99878-242">Estonia</span><span class="sxs-lookup"><span data-stu-id="99878-242">Estonia</span></span>

### <a name="format"></a><span data-ttu-id="99878-243">Formato</span><span class="sxs-lookup"><span data-stu-id="99878-243">Format</span></span>

<span data-ttu-id="99878-244">Una lettera seguita da sette cifre senza spazi o delimitatori</span><span class="sxs-lookup"><span data-stu-id="99878-244">One letter followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="99878-245">Modello</span><span class="sxs-lookup"><span data-stu-id="99878-245">Pattern</span></span>

<span data-ttu-id="99878-246">Una lettera seguita da sette cifre</span><span class="sxs-lookup"><span data-stu-id="99878-246">One letter followed by seven digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="99878-247">Checksum</span><span class="sxs-lookup"><span data-stu-id="99878-247">Checksum</span></span>

<span data-ttu-id="99878-248">No</span><span class="sxs-lookup"><span data-stu-id="99878-248">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="99878-249">Definizione</span><span class="sxs-lookup"><span data-stu-id="99878-249">Definition</span></span>

<span data-ttu-id="99878-250">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="99878-250">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="99878-251">L'espressione regolare `Regex_estonia_eu_passport_number` consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="99878-251">The regular expression  `Regex_estonia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="99878-252">Una parola chiave da `Keywords_estonia_eu_passport_number` viene trovato.</span><span class="sxs-lookup"><span data-stu-id="99878-252">A keyword from  `Keywords_estonia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_estonia_eu_passport_number" />
          <Match idRef="Keywords_estonia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="99878-253">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="99878-253">Keywords</span></span>

<span data-ttu-id="99878-254">| |</span><span class="sxs-lookup"><span data-stu-id="99878-254"></span></span>
|<span data-ttu-id="99878-255">**Keywords_estonia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="99878-255">**Keywords_estonia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="99878-256">numero di passaporto</span><span class="sxs-lookup"><span data-stu-id="99878-256">passport number</span></span>  <br/> <span data-ttu-id="99878-257">numero di passaporto estone</span><span class="sxs-lookup"><span data-stu-id="99878-257">estonian passport number</span></span>  <br/> <span data-ttu-id="99878-258">Passport non</span><span class="sxs-lookup"><span data-stu-id="99878-258">passport no</span></span>  <br/> <span data-ttu-id="99878-259">eesti kodaniku pass</span><span class="sxs-lookup"><span data-stu-id="99878-259">eesti kodaniku pass</span></span>  <br/> |
   
## <a name="finland"></a><span data-ttu-id="99878-260">Finlandia</span><span class="sxs-lookup"><span data-stu-id="99878-260">Finland</span></span>

<span data-ttu-id="99878-261">Per ulteriori informazioni, vedere la sezione "Numero di passaporto Finlandia" in [cercare il quali i tipi di informazioni riservate](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="99878-261">For details, see the section "Finland Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="france"></a><span data-ttu-id="99878-262">Francia</span><span class="sxs-lookup"><span data-stu-id="99878-262">France</span></span>

<span data-ttu-id="99878-263">Per ulteriori informazioni, vedere la sezione "Numero di passaporto Francia" in [cercare il quali i tipi di informazioni riservate](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="99878-263">For details, see the section "France Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="germany"></a><span data-ttu-id="99878-264">Germania</span><span class="sxs-lookup"><span data-stu-id="99878-264">Germany</span></span>

<span data-ttu-id="99878-265">Per ulteriori informazioni, vedere la sezione "Numero di passaporto Germania" in [cercare il quali i tipi di informazioni riservate](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="99878-265">For details, see the section "Germany Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="greece"></a><span data-ttu-id="99878-266">Grecia</span><span class="sxs-lookup"><span data-stu-id="99878-266">Greece</span></span>

### <a name="format"></a><span data-ttu-id="99878-267">Formato</span><span class="sxs-lookup"><span data-stu-id="99878-267">Format</span></span>

<span data-ttu-id="99878-268">Due lettere seguite da sette cifre senza spazi o delimitatori</span><span class="sxs-lookup"><span data-stu-id="99878-268">Two letters followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="99878-269">Modello</span><span class="sxs-lookup"><span data-stu-id="99878-269">Pattern</span></span>

<span data-ttu-id="99878-270">Due lettere seguite da 7 cifre</span><span class="sxs-lookup"><span data-stu-id="99878-270">Two letters followed by seven digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="99878-271">Checksum</span><span class="sxs-lookup"><span data-stu-id="99878-271">Checksum</span></span>

<span data-ttu-id="99878-272">No</span><span class="sxs-lookup"><span data-stu-id="99878-272">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="99878-273">Definizione</span><span class="sxs-lookup"><span data-stu-id="99878-273">Definition</span></span>

<span data-ttu-id="99878-274">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="99878-274">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="99878-275">L'espressione regolare `Regex_greece_eu_passport_number` consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="99878-275">The regular expression  `Regex_greece_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="99878-276">Una parola chiave da `Keywords_greece_eu_passport_number` viene trovato.</span><span class="sxs-lookup"><span data-stu-id="99878-276">A keyword from  `Keywords_greece_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_greece_eu_passport_number" />
          <Match idRef="Keywords_greece_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="99878-277">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="99878-277">Keywords</span></span>

<span data-ttu-id="99878-278">| |</span><span class="sxs-lookup"><span data-stu-id="99878-278"></span></span>
|<span data-ttu-id="99878-279">**Keywords_greece_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="99878-279">**Keywords_greece_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="99878-280">numero di passaporto</span><span class="sxs-lookup"><span data-stu-id="99878-280">passport number</span></span>  <br/> <span data-ttu-id="99878-281">numero di passaporto greca</span><span class="sxs-lookup"><span data-stu-id="99878-281">greek passport number</span></span>  <br/> <span data-ttu-id="99878-282">Passport non</span><span class="sxs-lookup"><span data-stu-id="99878-282">passport no</span></span>  <br/> <span data-ttu-id="99878-283">ΔΙΑΒΑΤΗΡΙΟ</span><span class="sxs-lookup"><span data-stu-id="99878-283">διαβατηριο</span></span>  <br/> |
   
## <a name="hungary"></a><span data-ttu-id="99878-284">Ungheria</span><span class="sxs-lookup"><span data-stu-id="99878-284">Hungary</span></span>

### <a name="format"></a><span data-ttu-id="99878-285">Formato</span><span class="sxs-lookup"><span data-stu-id="99878-285">Format</span></span>

<span data-ttu-id="99878-286">Due lettere seguite da sei o sette cifre senza spazi o delimitatori</span><span class="sxs-lookup"><span data-stu-id="99878-286">Two letters followed by six or seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="99878-287">Modello</span><span class="sxs-lookup"><span data-stu-id="99878-287">Pattern</span></span>

<span data-ttu-id="99878-288">Due lettere seguite da sei o sette cifre</span><span class="sxs-lookup"><span data-stu-id="99878-288">Two letters followed by six or seven digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="99878-289">Checksum</span><span class="sxs-lookup"><span data-stu-id="99878-289">Checksum</span></span>

<span data-ttu-id="99878-290">No</span><span class="sxs-lookup"><span data-stu-id="99878-290">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="99878-291">Definizione</span><span class="sxs-lookup"><span data-stu-id="99878-291">Definition</span></span>

<span data-ttu-id="99878-292">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="99878-292">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="99878-293">L'espressione regolare `Regex_hungary_eu_passport_number` consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="99878-293">The regular expression  `Regex_hungary_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="99878-294">Una parola chiave da `Keywords_hungary_eu_passport_number` viene trovato.</span><span class="sxs-lookup"><span data-stu-id="99878-294">A keyword from  `Keywords_hungary_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_hungary_eu_passport_number" />
          <Match idRef="Keywords_hungary_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="99878-295">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="99878-295">Keywords</span></span>

<span data-ttu-id="99878-296">| |</span><span class="sxs-lookup"><span data-stu-id="99878-296"></span></span>
|<span data-ttu-id="99878-297">**Keywords_hungary_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="99878-297">**Keywords_hungary_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="99878-298">numero di passaporto</span><span class="sxs-lookup"><span data-stu-id="99878-298">passport number</span></span>  <br/> <span data-ttu-id="99878-299">numero di passaporto ungherese</span><span class="sxs-lookup"><span data-stu-id="99878-299">hungarian passport number</span></span>  <br/> <span data-ttu-id="99878-300">Passport non</span><span class="sxs-lookup"><span data-stu-id="99878-300">passport no</span></span>  <br/> <span data-ttu-id="99878-301">útlevél száma</span><span class="sxs-lookup"><span data-stu-id="99878-301">útlevél száma</span></span>  <br/> |
   
## <a name="ireland"></a><span data-ttu-id="99878-302">Irlanda</span><span class="sxs-lookup"><span data-stu-id="99878-302">Ireland</span></span>

### <a name="format"></a><span data-ttu-id="99878-303">Formato</span><span class="sxs-lookup"><span data-stu-id="99878-303">Format</span></span>

<span data-ttu-id="99878-304">Due lettere o cifre seguiti da sette cifre senza spazi o delimitatori</span><span class="sxs-lookup"><span data-stu-id="99878-304">Two letters or digits followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="99878-305">Modello</span><span class="sxs-lookup"><span data-stu-id="99878-305">Pattern</span></span>

<span data-ttu-id="99878-306">Due lettere o cifre seguiti da sette cifre:</span><span class="sxs-lookup"><span data-stu-id="99878-306">Two letters or digits followed by seven digits:</span></span>
  
- <span data-ttu-id="99878-307">Due cifre o lettere (senza distinzione tra maiuscole/minuscole)</span><span class="sxs-lookup"><span data-stu-id="99878-307">Two digits or letters (not case sensitive)</span></span>
    
- <span data-ttu-id="99878-308">Sette cifre</span><span class="sxs-lookup"><span data-stu-id="99878-308">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="99878-309">Checksum</span><span class="sxs-lookup"><span data-stu-id="99878-309">Checksum</span></span>

<span data-ttu-id="99878-310">No</span><span class="sxs-lookup"><span data-stu-id="99878-310">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="99878-311">Definizione</span><span class="sxs-lookup"><span data-stu-id="99878-311">Definition</span></span>

<span data-ttu-id="99878-312">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="99878-312">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="99878-313">L'espressione regolare `Regex_ireland_eu_passport_number` consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="99878-313">The regular expression  `Regex_ireland_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="99878-314">Una parola chiave da `Keywords_ireland_eu_passport_number` viene trovato.</span><span class="sxs-lookup"><span data-stu-id="99878-314">A keyword from  `Keywords_ireland_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_ireland_eu_passport_number" />
          <Match idRef="Keywords_ireland_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="99878-315">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="99878-315">Keywords</span></span>

<span data-ttu-id="99878-316">| |</span><span class="sxs-lookup"><span data-stu-id="99878-316"></span></span>
|<span data-ttu-id="99878-317">**Keywords_ireland_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="99878-317">**Keywords_ireland_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="99878-318">numero di passaporto</span><span class="sxs-lookup"><span data-stu-id="99878-318">passport number</span></span>  <br/> <span data-ttu-id="99878-319">numero di passaporto irlandese</span><span class="sxs-lookup"><span data-stu-id="99878-319">irish passport number</span></span>  <br/> <span data-ttu-id="99878-320">Passport non</span><span class="sxs-lookup"><span data-stu-id="99878-320">passport no</span></span>  <br/> <span data-ttu-id="99878-321">PAS</span><span class="sxs-lookup"><span data-stu-id="99878-321">pas</span></span>  <br/> <span data-ttu-id="99878-322">passport</span><span class="sxs-lookup"><span data-stu-id="99878-322">passport</span></span>  <br/> <span data-ttu-id="99878-323">passeport</span><span class="sxs-lookup"><span data-stu-id="99878-323">passeport</span></span>  <br/> <span data-ttu-id="99878-324">numero passeport</span><span class="sxs-lookup"><span data-stu-id="99878-324">passeport numero</span></span>  <br/> |
   
## <a name="italy"></a><span data-ttu-id="99878-325">Italia</span><span class="sxs-lookup"><span data-stu-id="99878-325">Italy</span></span>

### <a name="format"></a><span data-ttu-id="99878-326">Formato</span><span class="sxs-lookup"><span data-stu-id="99878-326">Format</span></span>

<span data-ttu-id="99878-327">Due lettere o cifre seguiti da sette cifre senza spazi o delimitatori</span><span class="sxs-lookup"><span data-stu-id="99878-327">Two letters or digits followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="99878-328">Modello</span><span class="sxs-lookup"><span data-stu-id="99878-328">Pattern</span></span>

<span data-ttu-id="99878-329">Due lettere o cifre seguiti da sette cifre:</span><span class="sxs-lookup"><span data-stu-id="99878-329">Two letters or digits followed by seven digits:</span></span>
  
- <span data-ttu-id="99878-330">Due cifre o lettere (senza distinzione tra maiuscole/minuscole)</span><span class="sxs-lookup"><span data-stu-id="99878-330">Two digits or letters (not case sensitive)</span></span>
    
- <span data-ttu-id="99878-331">Sette cifre</span><span class="sxs-lookup"><span data-stu-id="99878-331">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="99878-332">Checksum</span><span class="sxs-lookup"><span data-stu-id="99878-332">Checksum</span></span>

<span data-ttu-id="99878-333">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="99878-333">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="99878-334">Definizione</span><span class="sxs-lookup"><span data-stu-id="99878-334">Definition</span></span>

<span data-ttu-id="99878-335">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="99878-335">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="99878-336">L'espressione regolare `Regex_italy_eu_passport_number` consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="99878-336">The regular expression  `Regex_italy_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="99878-337">Una parola chiave da `Keywords_italy_eu_passport_number` viene trovato.</span><span class="sxs-lookup"><span data-stu-id="99878-337">A keyword from  `Keywords_italy_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_italy_eu_passport_number" />
          <Match idRef="Keywords_italy_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="99878-338">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="99878-338">Keywords</span></span>

<span data-ttu-id="99878-339">| |</span><span class="sxs-lookup"><span data-stu-id="99878-339"></span></span>
|<span data-ttu-id="99878-340">**Keywords_italy_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="99878-340">**Keywords_italy_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="99878-341">numero di passaporto italiano</span><span class="sxs-lookup"><span data-stu-id="99878-341">italian passport number</span></span>  <br/> <span data-ttu-id="99878-342">Repubblica italiana passaporto</span><span class="sxs-lookup"><span data-stu-id="99878-342">repubblica italiana passaporto</span></span>  <br/> <span data-ttu-id="99878-343">passaporto</span><span class="sxs-lookup"><span data-stu-id="99878-343">passaporto</span></span>  <br/> <span data-ttu-id="99878-344">passaporto italiana</span><span class="sxs-lookup"><span data-stu-id="99878-344">passaporto italiana</span></span>  <br/> <span data-ttu-id="99878-345">numero di passaporto</span><span class="sxs-lookup"><span data-stu-id="99878-345">passport number</span></span>  <br/> <span data-ttu-id="99878-346">numero di passaporto italiana</span><span class="sxs-lookup"><span data-stu-id="99878-346">italiana passaporto numero</span></span>  <br/> <span data-ttu-id="99878-347">numero di passaporto</span><span class="sxs-lookup"><span data-stu-id="99878-347">passaporto numero</span></span>  <br/> <span data-ttu-id="99878-348">numéro passeport italien</span><span class="sxs-lookup"><span data-stu-id="99878-348">numéro passeport italien</span></span>  <br/> <span data-ttu-id="99878-349">numéro passeport</span><span class="sxs-lookup"><span data-stu-id="99878-349">numéro passeport</span></span>  <br/> |
   
## <a name="latvia"></a><span data-ttu-id="99878-350">Lettonia</span><span class="sxs-lookup"><span data-stu-id="99878-350">Latvia</span></span>

### <a name="format"></a><span data-ttu-id="99878-351">Formato</span><span class="sxs-lookup"><span data-stu-id="99878-351">Format</span></span>

<span data-ttu-id="99878-352">Due lettere o cifre seguiti da sette cifre senza spazi o delimitatori</span><span class="sxs-lookup"><span data-stu-id="99878-352">Two letters or digits followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="99878-353">Modello</span><span class="sxs-lookup"><span data-stu-id="99878-353">Pattern</span></span>

<span data-ttu-id="99878-354">Due lettere o cifre seguiti da sette cifre:</span><span class="sxs-lookup"><span data-stu-id="99878-354">Two letters or digits followed by seven digits:</span></span>
  
- <span data-ttu-id="99878-355">Due cifre o lettere (senza distinzione tra maiuscole/minuscole)</span><span class="sxs-lookup"><span data-stu-id="99878-355">Two digits or letters (not case sensitive)</span></span>
    
- <span data-ttu-id="99878-356">Sette cifre</span><span class="sxs-lookup"><span data-stu-id="99878-356">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="99878-357">Checksum</span><span class="sxs-lookup"><span data-stu-id="99878-357">Checksum</span></span>

<span data-ttu-id="99878-358">No</span><span class="sxs-lookup"><span data-stu-id="99878-358">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="99878-359">Definizione</span><span class="sxs-lookup"><span data-stu-id="99878-359">Definition</span></span>

<span data-ttu-id="99878-360">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="99878-360">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="99878-361">L'espressione regolare `Regex_latvia_eu_passport_number` consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="99878-361">The regular expression  `Regex_latvia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="99878-362">Una parola chiave da `Keywords_latvia_eu_passport_number` viene trovato.</span><span class="sxs-lookup"><span data-stu-id="99878-362">A keyword from  `Keywords_latvia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_latvia_eu_passport_number" />
          <Match idRef="Keywords_latvia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="99878-363">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="99878-363">Keywords</span></span>

<span data-ttu-id="99878-364">| |</span><span class="sxs-lookup"><span data-stu-id="99878-364"></span></span>
|<span data-ttu-id="99878-365">**Keywords_latvia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="99878-365">**Keywords_latvia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="99878-366">numero di passaporto</span><span class="sxs-lookup"><span data-stu-id="99878-366">passport number</span></span>  <br/> <span data-ttu-id="99878-367">numero di passaporto lettone</span><span class="sxs-lookup"><span data-stu-id="99878-367">latvian passport number</span></span>  <br/> <span data-ttu-id="99878-368">Passport non</span><span class="sxs-lookup"><span data-stu-id="99878-368">passport no</span></span>  <br/> <span data-ttu-id="99878-369">pase numurs</span><span class="sxs-lookup"><span data-stu-id="99878-369">pase numurs</span></span>  <br/> |
   
## <a name="lithuania"></a><span data-ttu-id="99878-370">Lituania</span><span class="sxs-lookup"><span data-stu-id="99878-370">Lithuania</span></span>

### <a name="format"></a><span data-ttu-id="99878-371">Formato</span><span class="sxs-lookup"><span data-stu-id="99878-371">Format</span></span>

<span data-ttu-id="99878-372">Otto cifre o lettere senza spazi o delimitatori</span><span class="sxs-lookup"><span data-stu-id="99878-372">Eight digits or letters with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="99878-373">Modello</span><span class="sxs-lookup"><span data-stu-id="99878-373">Pattern</span></span>

<span data-ttu-id="99878-374">Otto cifre o lettere (non maiuscole/minuscole)</span><span class="sxs-lookup"><span data-stu-id="99878-374">Eight digits or letters (not case sensitive)</span></span>
  
### <a name="checksum"></a><span data-ttu-id="99878-375">Checksum</span><span class="sxs-lookup"><span data-stu-id="99878-375">Checksum</span></span>

<span data-ttu-id="99878-376">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="99878-376">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="99878-377">Definizione</span><span class="sxs-lookup"><span data-stu-id="99878-377">Definition</span></span>

<span data-ttu-id="99878-378">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="99878-378">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="99878-379">L'espressione regolare `Regex_lithuania_eu_passport_number` consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="99878-379">The regular expression  `Regex_lithuania_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="99878-380">Una parola chiave da `Keywords_lithuania_eu_passport_number` viene trovato.</span><span class="sxs-lookup"><span data-stu-id="99878-380">A keyword from  `Keywords_lithuania_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_lithuania_eu_passport_number" />
          <Match idRef="Keywords_lithuania_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="99878-381">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="99878-381">Keywords</span></span>

<span data-ttu-id="99878-382">| |</span><span class="sxs-lookup"><span data-stu-id="99878-382"></span></span>
|<span data-ttu-id="99878-383">**Keywords_lithuania_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="99878-383">**Keywords_lithuania_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="99878-384">numero di passaporto</span><span class="sxs-lookup"><span data-stu-id="99878-384">passport number</span></span>  <br/> <span data-ttu-id="99878-385">numero di passaporto lithunian</span><span class="sxs-lookup"><span data-stu-id="99878-385">lithunian passport number</span></span>  <br/> <span data-ttu-id="99878-386">Passport non</span><span class="sxs-lookup"><span data-stu-id="99878-386">passport no</span></span>  <br/> <span data-ttu-id="99878-387">paso numeris</span><span class="sxs-lookup"><span data-stu-id="99878-387">paso numeris</span></span>  <br/> |
   
## <a name="luxemburg"></a><span data-ttu-id="99878-388">Lussemburgo</span><span class="sxs-lookup"><span data-stu-id="99878-388">Luxemburg</span></span>

### <a name="format"></a><span data-ttu-id="99878-389">Formato</span><span class="sxs-lookup"><span data-stu-id="99878-389">Format</span></span>

<span data-ttu-id="99878-390">Otto cifre o lettere senza spazi o delimitatori</span><span class="sxs-lookup"><span data-stu-id="99878-390">Eight digits or letters with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="99878-391">Modello</span><span class="sxs-lookup"><span data-stu-id="99878-391">Pattern</span></span>

<span data-ttu-id="99878-392">Otto cifre o lettere (non maiuscole/minuscole)</span><span class="sxs-lookup"><span data-stu-id="99878-392">Eight digits or letters (not case sensitive)</span></span>
  
### <a name="checksum"></a><span data-ttu-id="99878-393">Checksum</span><span class="sxs-lookup"><span data-stu-id="99878-393">Checksum</span></span>

<span data-ttu-id="99878-394">No</span><span class="sxs-lookup"><span data-stu-id="99878-394">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="99878-395">Definizione</span><span class="sxs-lookup"><span data-stu-id="99878-395">Definition</span></span>

<span data-ttu-id="99878-396">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="99878-396">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="99878-397">L'espressione regolare `Regex_nation_eu_passport_number` consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="99878-397">The regular expression  `Regex_nation_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="99878-398">Una parola chiave da `Keywords_nation_eu_passport_number` viene trovato.</span><span class="sxs-lookup"><span data-stu-id="99878-398">A keyword from  `Keywords_nation_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_nation_eu_passport_number" />
          <Match idRef="Keywords_nation_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="99878-399">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="99878-399">Keywords</span></span>

<span data-ttu-id="99878-400">| |</span><span class="sxs-lookup"><span data-stu-id="99878-400"></span></span>
|<span data-ttu-id="99878-401">**Keywords_nation_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="99878-401">**Keywords_nation_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="99878-402">numero di passaporto</span><span class="sxs-lookup"><span data-stu-id="99878-402">passport number</span></span>  <br/> <span data-ttu-id="99878-403">numero di passaporto lettone</span><span class="sxs-lookup"><span data-stu-id="99878-403">latvian passport number</span></span>  <br/> <span data-ttu-id="99878-404">Passport non</span><span class="sxs-lookup"><span data-stu-id="99878-404">passport no</span></span>  <br/> <span data-ttu-id="99878-405">passnummer</span><span class="sxs-lookup"><span data-stu-id="99878-405">passnummer</span></span>  <br/> |
   
## <a name="malta"></a><span data-ttu-id="99878-406">Malta</span><span class="sxs-lookup"><span data-stu-id="99878-406">Malta</span></span>

### <a name="format"></a><span data-ttu-id="99878-407">Formato</span><span class="sxs-lookup"><span data-stu-id="99878-407">Format</span></span>

<span data-ttu-id="99878-408">Sette cifre senza spazi o delimitatori</span><span class="sxs-lookup"><span data-stu-id="99878-408">Seven digits without spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="99878-409">Modello</span><span class="sxs-lookup"><span data-stu-id="99878-409">Pattern</span></span>

 <span data-ttu-id="99878-410">Sette cifre</span><span class="sxs-lookup"><span data-stu-id="99878-410">Seven digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="99878-411">Checksum</span><span class="sxs-lookup"><span data-stu-id="99878-411">Checksum</span></span>

<span data-ttu-id="99878-412">No</span><span class="sxs-lookup"><span data-stu-id="99878-412">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="99878-413">Definizione</span><span class="sxs-lookup"><span data-stu-id="99878-413">Definition</span></span>

<span data-ttu-id="99878-414">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="99878-414">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="99878-415">L'espressione regolare `Regex_malta_eu_passport_number` consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="99878-415">The regular expression  `Regex_malta_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="99878-416">Una parola chiave da `Keywords_malta_eu_passport_number` viene trovato.</span><span class="sxs-lookup"><span data-stu-id="99878-416">A keyword from  `Keywords_malta_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_malta_eu_passport_number" />
          <Match idRef="Keywords_malta_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="99878-417">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="99878-417">Keywords</span></span>

<span data-ttu-id="99878-418">| |</span><span class="sxs-lookup"><span data-stu-id="99878-418"></span></span>
|<span data-ttu-id="99878-419">**Keywords_malta_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="99878-419">**Keywords_malta_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="99878-420">numero di passaporto</span><span class="sxs-lookup"><span data-stu-id="99878-420">passport number</span></span>  <br/> <span data-ttu-id="99878-421">numero di passaporto maltese</span><span class="sxs-lookup"><span data-stu-id="99878-421">maltese passport number</span></span>  <br/> <span data-ttu-id="99878-422">Passport non</span><span class="sxs-lookup"><span data-stu-id="99878-422">passport no</span></span>  <br/> <span data-ttu-id="99878-423">numru tal-passaport</span><span class="sxs-lookup"><span data-stu-id="99878-423">numru tal-passaport</span></span>  <br/> |
   
## <a name="netherlands"></a><span data-ttu-id="99878-424">Paesi Bassi</span><span class="sxs-lookup"><span data-stu-id="99878-424">Netherlands</span></span>

### <a name="format"></a><span data-ttu-id="99878-425">Formato</span><span class="sxs-lookup"><span data-stu-id="99878-425">Format</span></span>

<span data-ttu-id="99878-426">Nove lettere o cifre senza spazi o delimitatori</span><span class="sxs-lookup"><span data-stu-id="99878-426">Nine letters or digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="99878-427">Modello</span><span class="sxs-lookup"><span data-stu-id="99878-427">Pattern</span></span>

<span data-ttu-id="99878-428">Nove lettere o cifre</span><span class="sxs-lookup"><span data-stu-id="99878-428">Nine letters or digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="99878-429">Checksum</span><span class="sxs-lookup"><span data-stu-id="99878-429">Checksum</span></span>

<span data-ttu-id="99878-430">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="99878-430">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="99878-431">Definizione</span><span class="sxs-lookup"><span data-stu-id="99878-431">Definition</span></span>

<span data-ttu-id="99878-432">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="99878-432">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="99878-433">L'espressione regolare `Regex_netherlands_eu_passport_number` consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="99878-433">The regular expression  `Regex_netherlands_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="99878-434">Una parola chiave da `Keywords_netherlands_eu_passport_number` viene trovato.</span><span class="sxs-lookup"><span data-stu-id="99878-434">A keyword from  `Keywords_netherlands_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_netherlands_eu_passport_number" />
          <Match idRef="Keywords_netherlands_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="99878-435">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="99878-435">Keywords</span></span>

<span data-ttu-id="99878-436">| |</span><span class="sxs-lookup"><span data-stu-id="99878-436"></span></span>
|<span data-ttu-id="99878-437">**Keywords_netherlands_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="99878-437">**Keywords_netherlands_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="99878-438">numero di passaporto olandese</span><span class="sxs-lookup"><span data-stu-id="99878-438">dutch passport number</span></span>  <br/> <span data-ttu-id="99878-439">numero di passaporto</span><span class="sxs-lookup"><span data-stu-id="99878-439">passport number</span></span>  <br/> <span data-ttu-id="99878-440">numero di passaporto Paesi Bassi</span><span class="sxs-lookup"><span data-stu-id="99878-440">netherlands passport number</span></span>  <br/> <span data-ttu-id="99878-441">nederlanden paspoort nummer</span><span class="sxs-lookup"><span data-stu-id="99878-441">nederlanden paspoort nummer</span></span>  <br/> <span data-ttu-id="99878-442">paspoort</span><span class="sxs-lookup"><span data-stu-id="99878-442">paspoort</span></span>  <br/> <span data-ttu-id="99878-443">nederlanden paspoortnummer</span><span class="sxs-lookup"><span data-stu-id="99878-443">nederlanden paspoortnummer</span></span>  <br/> <span data-ttu-id="99878-444">paspoortnummer</span><span class="sxs-lookup"><span data-stu-id="99878-444">paspoortnummer</span></span>  <br/> |
   
## <a name="poland"></a><span data-ttu-id="99878-445">Polonia</span><span class="sxs-lookup"><span data-stu-id="99878-445">Poland</span></span>

<span data-ttu-id="99878-446">Per ulteriori informazioni, vedere la sezione "Numero di passaporto Polonia" in [cercare il quali i tipi di informazioni riservate](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="99878-446">For details, see the section "Poland Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="portugal"></a><span data-ttu-id="99878-447">Portogallo</span><span class="sxs-lookup"><span data-stu-id="99878-447">Portugal</span></span>

### <a name="format"></a><span data-ttu-id="99878-448">Formato</span><span class="sxs-lookup"><span data-stu-id="99878-448">Format</span></span>

<span data-ttu-id="99878-449">Una lettera seguita da sei cifre senza spazi o delimitatori</span><span class="sxs-lookup"><span data-stu-id="99878-449">One letter followed by six digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="99878-450">Modello</span><span class="sxs-lookup"><span data-stu-id="99878-450">Pattern</span></span>

<span data-ttu-id="99878-451">Una lettera seguita da sei cifre:</span><span class="sxs-lookup"><span data-stu-id="99878-451">One letter followed by six digits:</span></span>
  
- <span data-ttu-id="99878-452">Una lettera (senza distinzione tra maiuscole/minuscole)</span><span class="sxs-lookup"><span data-stu-id="99878-452">One letter (not case sensitive)</span></span>
    
- <span data-ttu-id="99878-453">Sei cifre</span><span class="sxs-lookup"><span data-stu-id="99878-453">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="99878-454">Checksum</span><span class="sxs-lookup"><span data-stu-id="99878-454">Checksum</span></span>

<span data-ttu-id="99878-455">No</span><span class="sxs-lookup"><span data-stu-id="99878-455">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="99878-456">Definizione</span><span class="sxs-lookup"><span data-stu-id="99878-456">Definition</span></span>

<span data-ttu-id="99878-457">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="99878-457">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="99878-458">L'espressione regolare `Regex_portugal_eu_passport_number` consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="99878-458">The regular expression  `Regex_portugal_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="99878-459">Una parola chiave da `Keywords_portugal_eu_passport_number` viene trovato.</span><span class="sxs-lookup"><span data-stu-id="99878-459">A keyword from  `Keywords_portugal_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_portugal_eu_passport_number" />
          <Match idRef="Keywords_portugal_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="99878-460">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="99878-460">Keywords</span></span>

<span data-ttu-id="99878-461">| |</span><span class="sxs-lookup"><span data-stu-id="99878-461"></span></span>
|<span data-ttu-id="99878-462">**Keywords_portugal_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="99878-462">**Keywords_portugal_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="99878-463">numero di passaporto</span><span class="sxs-lookup"><span data-stu-id="99878-463">passport number</span></span>  <br/> <span data-ttu-id="99878-464">numero di passaporto portoghese</span><span class="sxs-lookup"><span data-stu-id="99878-464">portugese passport number</span></span>  <br/> <span data-ttu-id="99878-465">Passport non</span><span class="sxs-lookup"><span data-stu-id="99878-465">passport no</span></span>  <br/> <span data-ttu-id="99878-466">número passaporte</span><span class="sxs-lookup"><span data-stu-id="99878-466">número do passaporte</span></span>  <br/> |
   
## <a name="romania"></a><span data-ttu-id="99878-467">Romania</span><span class="sxs-lookup"><span data-stu-id="99878-467">Romania</span></span>

### <a name="format"></a><span data-ttu-id="99878-468">Formato</span><span class="sxs-lookup"><span data-stu-id="99878-468">Format</span></span>

<span data-ttu-id="99878-469">Otto o nove cifre senza spazi e i delimitatori</span><span class="sxs-lookup"><span data-stu-id="99878-469">Eight or nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="99878-470">Modello</span><span class="sxs-lookup"><span data-stu-id="99878-470">Pattern</span></span>

<span data-ttu-id="99878-471">Otto o nove cifre</span><span class="sxs-lookup"><span data-stu-id="99878-471">Eight or nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="99878-472">Checksum</span><span class="sxs-lookup"><span data-stu-id="99878-472">Checksum</span></span>

<span data-ttu-id="99878-473">No</span><span class="sxs-lookup"><span data-stu-id="99878-473">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="99878-474">Definizione</span><span class="sxs-lookup"><span data-stu-id="99878-474">Definition</span></span>

<span data-ttu-id="99878-475">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="99878-475">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="99878-476">L'espressione regolare `Regex_romania_eu_passport_number` consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="99878-476">The regular expression  `Regex_romania_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="99878-477">Una parola chiave da `Keywords_romania_eu_passport_number` viene trovato.</span><span class="sxs-lookup"><span data-stu-id="99878-477">A keyword from  `Keywords_romania_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_romania_eu_passport_number" />
          <Match idRef="Keywords_romania_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="99878-478">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="99878-478">Keywords</span></span>

<span data-ttu-id="99878-479">| |</span><span class="sxs-lookup"><span data-stu-id="99878-479"></span></span>
|<span data-ttu-id="99878-480">**Keywords_romania_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="99878-480">**Keywords_romania_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="99878-481">numero di passaporto</span><span class="sxs-lookup"><span data-stu-id="99878-481">passport number</span></span>  <br/> <span data-ttu-id="99878-482">numero di passaporto rumeno</span><span class="sxs-lookup"><span data-stu-id="99878-482">romanian passport number</span></span>  <br/> <span data-ttu-id="99878-483">Passport non</span><span class="sxs-lookup"><span data-stu-id="99878-483">passport no</span></span>  <br/> <span data-ttu-id="99878-484">numărul pașaportului</span><span class="sxs-lookup"><span data-stu-id="99878-484">numărul pașaportului</span></span>  <br/> |
   
## <a name="slovakia"></a><span data-ttu-id="99878-485">Slovacchia</span><span class="sxs-lookup"><span data-stu-id="99878-485">Slovakia</span></span>

### <a name="format"></a><span data-ttu-id="99878-486">Formato</span><span class="sxs-lookup"><span data-stu-id="99878-486">Format</span></span>

<span data-ttu-id="99878-487">Una cifra o una lettera seguito da sette cifre senza spazi o delimitatori</span><span class="sxs-lookup"><span data-stu-id="99878-487">One digit or letter followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="99878-488">Modello</span><span class="sxs-lookup"><span data-stu-id="99878-488">Pattern</span></span>

<span data-ttu-id="99878-489">Una cifra o una lettera (non maiuscole/minuscole) seguito da sette cifre</span><span class="sxs-lookup"><span data-stu-id="99878-489">One digit or letter (not case sensitive) followed by seven digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="99878-490">Checksum</span><span class="sxs-lookup"><span data-stu-id="99878-490">Checksum</span></span>

<span data-ttu-id="99878-491">No</span><span class="sxs-lookup"><span data-stu-id="99878-491">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="99878-492">Definizione</span><span class="sxs-lookup"><span data-stu-id="99878-492">Definition</span></span>

<span data-ttu-id="99878-493">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="99878-493">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="99878-494">L'espressione regolare `Regex_slovakia_eu_passport_number` consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="99878-494">The regular expression  `Regex_slovakia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="99878-495">Una parola chiave da `Keywords_slovakia_eu_passport_number` viene trovato.</span><span class="sxs-lookup"><span data-stu-id="99878-495">A keyword from  `Keywords_slovakia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovakia_eu_passport_number" />
          <Match idRef="Keywords_slovakia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="99878-496">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="99878-496">Keywords</span></span>

<span data-ttu-id="99878-497">| |</span><span class="sxs-lookup"><span data-stu-id="99878-497"></span></span>
|<span data-ttu-id="99878-498">**Keywords_slovakia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="99878-498">**Keywords_slovakia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="99878-499">numero di passaporto</span><span class="sxs-lookup"><span data-stu-id="99878-499">passport number</span></span>  <br/> <span data-ttu-id="99878-500">numero di passaporto slovacco</span><span class="sxs-lookup"><span data-stu-id="99878-500">slovakian passport number</span></span>  <br/> <span data-ttu-id="99878-501">Passport non</span><span class="sxs-lookup"><span data-stu-id="99878-501">passport no</span></span>  <br/> <span data-ttu-id="99878-502">Číslo pasu</span><span class="sxs-lookup"><span data-stu-id="99878-502">číslo pasu</span></span>  <br/> |
   
## <a name="slovenia"></a><span data-ttu-id="99878-503">Slovenia</span><span class="sxs-lookup"><span data-stu-id="99878-503">Slovenia</span></span>

### <a name="format"></a><span data-ttu-id="99878-504">Formato</span><span class="sxs-lookup"><span data-stu-id="99878-504">Format</span></span>

<span data-ttu-id="99878-505">Due lettere seguite da sette cifre senza spazi o delimitatori</span><span class="sxs-lookup"><span data-stu-id="99878-505">Two letters followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="99878-506">Modello</span><span class="sxs-lookup"><span data-stu-id="99878-506">Pattern</span></span>

<span data-ttu-id="99878-507">Due lettere seguite da sette cifre:</span><span class="sxs-lookup"><span data-stu-id="99878-507">Two letters followed by seven digits:</span></span>
  
- <span data-ttu-id="99878-508">La lettera "P"</span><span class="sxs-lookup"><span data-stu-id="99878-508">The letter "P"</span></span>
    
- <span data-ttu-id="99878-509">Una lettera maiuscola</span><span class="sxs-lookup"><span data-stu-id="99878-509">One uppercase letter</span></span>
    
- <span data-ttu-id="99878-510">Sette cifre</span><span class="sxs-lookup"><span data-stu-id="99878-510">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="99878-511">Checksum</span><span class="sxs-lookup"><span data-stu-id="99878-511">Checksum</span></span>

<span data-ttu-id="99878-512">No</span><span class="sxs-lookup"><span data-stu-id="99878-512">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="99878-513">Definizione</span><span class="sxs-lookup"><span data-stu-id="99878-513">Definition</span></span>

<span data-ttu-id="99878-514">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="99878-514">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="99878-515">L'espressione regolare `Regex_slovenia_eu_passport_number` consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="99878-515">The regular expression  `Regex_slovenia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="99878-516">Una parola chiave da `Keywords_slovenia_eu_passport_number` viene trovato.</span><span class="sxs-lookup"><span data-stu-id="99878-516">A keyword from  `Keywords_slovenia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovenia_eu_passport_number" />
          <Match idRef="Keywords_slovenia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="99878-517">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="99878-517">Keywords</span></span>

<span data-ttu-id="99878-518">| |</span><span class="sxs-lookup"><span data-stu-id="99878-518"></span></span>
|<span data-ttu-id="99878-519">**Keywords_slovenia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="99878-519">**Keywords_slovenia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="99878-520">numero di passaporto</span><span class="sxs-lookup"><span data-stu-id="99878-520">passport number</span></span>  <br/> <span data-ttu-id="99878-521">numero di passaporto sloveno</span><span class="sxs-lookup"><span data-stu-id="99878-521">slovenian passport number</span></span>  <br/> <span data-ttu-id="99878-522">Passport non</span><span class="sxs-lookup"><span data-stu-id="99878-522">passport no</span></span>  <br/> <span data-ttu-id="99878-523">Številka potnega lista</span><span class="sxs-lookup"><span data-stu-id="99878-523">številka potnega lista</span></span>  <br/> |
   
## <a name="spain"></a><span data-ttu-id="99878-524">Spagna</span><span class="sxs-lookup"><span data-stu-id="99878-524">Spain</span></span>

### <a name="format"></a><span data-ttu-id="99878-525">Formato</span><span class="sxs-lookup"><span data-stu-id="99878-525">Format</span></span>

<span data-ttu-id="99878-526">Una combinazione di otto o nove caratteri di lettere e numeri senza spazi o delimitatori</span><span class="sxs-lookup"><span data-stu-id="99878-526">An eight- or nine-character combination of letters and numbers with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="99878-527">Modello</span><span class="sxs-lookup"><span data-stu-id="99878-527">Pattern</span></span>

<span data-ttu-id="99878-528">Una combinazione di otto o nove caratteri di numeri e lettere:</span><span class="sxs-lookup"><span data-stu-id="99878-528">An eight- or nine-character combination of letters and numbers:</span></span>
  
-  <span data-ttu-id="99878-529">Due cifre o lettere selezionate</span><span class="sxs-lookup"><span data-stu-id="99878-529">Two digits or letters</span></span> 
    
- <span data-ttu-id="99878-530">Una cifra o una lettera (facoltativo)</span><span class="sxs-lookup"><span data-stu-id="99878-530">One digit or letter (optional)</span></span>
    
- <span data-ttu-id="99878-531">Sei cifre</span><span class="sxs-lookup"><span data-stu-id="99878-531">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="99878-532">Checksum</span><span class="sxs-lookup"><span data-stu-id="99878-532">Checksum</span></span>

<span data-ttu-id="99878-533">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="99878-533">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="99878-534">Definizione</span><span class="sxs-lookup"><span data-stu-id="99878-534">Definition</span></span>

<span data-ttu-id="99878-535">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="99878-535">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="99878-536">L'espressione regolare `Regex_spain_eu_passport_number` consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="99878-536">The regular expression  `Regex_spain_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="99878-537">Una parola chiave da `Keywords_spain_eu_passport_number` viene trovato.</span><span class="sxs-lookup"><span data-stu-id="99878-537">A keyword from  `Keywords_spain_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_spain_eu_passport_number" />
          <Match idRef="Keywords_spain_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="99878-538">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="99878-538">Keywords</span></span>

<span data-ttu-id="99878-539">| |</span><span class="sxs-lookup"><span data-stu-id="99878-539"></span></span>
|<span data-ttu-id="99878-540">**Keywords_spain_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="99878-540">**Keywords_spain_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="99878-541">passport</span><span class="sxs-lookup"><span data-stu-id="99878-541">passport</span></span>  <br/> <span data-ttu-id="99878-542">passport Spagna</span><span class="sxs-lookup"><span data-stu-id="99878-542">spain passport</span></span>  <br/> <span data-ttu-id="99878-543">Rubrica di passaporto</span><span class="sxs-lookup"><span data-stu-id="99878-543">passport book</span></span>  <br/> <span data-ttu-id="99878-544">numero di passaporto</span><span class="sxs-lookup"><span data-stu-id="99878-544">passport number</span></span>  <br/> <span data-ttu-id="99878-545">Passport non</span><span class="sxs-lookup"><span data-stu-id="99878-545">passport no</span></span>  <br/> <span data-ttu-id="99878-546">libreta pasaporte</span><span class="sxs-lookup"><span data-stu-id="99878-546">libreta pasaporte</span></span>  <br/> <span data-ttu-id="99878-547">número pasaporte</span><span class="sxs-lookup"><span data-stu-id="99878-547">número pasaporte</span></span>  <br/> <span data-ttu-id="99878-548">España pasaporte</span><span class="sxs-lookup"><span data-stu-id="99878-548">españa pasaporte</span></span>  <br/> <span data-ttu-id="99878-549">pasaporte</span><span class="sxs-lookup"><span data-stu-id="99878-549">pasaporte</span></span>  <br/> |
   
## <a name="sweden"></a><span data-ttu-id="99878-550">Svezia</span><span class="sxs-lookup"><span data-stu-id="99878-550">Sweden</span></span>

<span data-ttu-id="99878-551">Per ulteriori informazioni, vedere la sezione "Numero di passaporto Svezia" in [cercare il quali i tipi di informazioni riservate](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="99878-551">For details, see the section "Sweden Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="uk"></a><span data-ttu-id="99878-552">REGNO UNITO</span><span class="sxs-lookup"><span data-stu-id="99878-552">UK</span></span>

<span data-ttu-id="99878-p103">Per ulteriori informazioni, vedere la sezione "US / numero di passaporto Regno Unito" in [cercare il quali i tipi di informazioni riservate](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="99878-p103">For details, see the section "U.S. / U.K. Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="99878-555">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="99878-555">See also</span></span>

[<span data-ttu-id="99878-556">Cosa individuano i tipi di informazioni riservate</span><span class="sxs-lookup"><span data-stu-id="99878-556">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)

