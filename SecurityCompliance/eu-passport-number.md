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
ms.openlocfilehash: 7a7fc1ff826aab4096c46535686eb0fd68173c6f
ms.sourcegitcommit: 7e2a0185cadea7f3a6afc5ddc445eac2e1ce22eb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/11/2019
ms.locfileid: "25840325"
---
# <a name="eu-passport-number"></a><span data-ttu-id="af424-104">Numero di passaporto UE</span><span class="sxs-lookup"><span data-stu-id="af424-104">EU Passport Number</span></span>

<span data-ttu-id="af424-p102">Questo argomento viene illustrato quali criteri di criterio DLP perdita dei dati Cerca qualora venga rilevato un tipo di informazione sensibile il numero di passaporto UE. Questo tipo di informazioni riservate definisce le diverse combinazioni, parole chiave e altri elementi di prova per ogni paese.</span><span class="sxs-lookup"><span data-stu-id="af424-p102">This topic shows what a data loss prevention (DLP) policy looks for when it detects the EU Passport Number sensitive information type. This sensitive information type defines different patterns, keywords, and other evidence for each country.</span></span>
  
## <a name="austria"></a><span data-ttu-id="af424-107">Austria</span><span class="sxs-lookup"><span data-stu-id="af424-107">Austria</span></span>

### <a name="format"></a><span data-ttu-id="af424-108">Formato</span><span class="sxs-lookup"><span data-stu-id="af424-108">Format</span></span>

<span data-ttu-id="af424-109">Una lettera seguita da sette cifre e da uno spazio facoltativo</span><span class="sxs-lookup"><span data-stu-id="af424-109">One letter followed by an optional space and seven digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="af424-110">Modello</span><span class="sxs-lookup"><span data-stu-id="af424-110">Pattern</span></span>

<span data-ttu-id="af424-111">Una combinazione di una lettera, sette cifre e uno spazio:</span><span class="sxs-lookup"><span data-stu-id="af424-111">A combination of one letter, seven digits, and one space:</span></span>
  
- <span data-ttu-id="af424-112">Una lettera (senza distinzione tra maiuscole/minuscole)</span><span class="sxs-lookup"><span data-stu-id="af424-112">One letter (not case sensitive)</span></span>
    
- <span data-ttu-id="af424-113">Uno spazio (facoltativo)</span><span class="sxs-lookup"><span data-stu-id="af424-113">One space (optional)</span></span>
    
- <span data-ttu-id="af424-114">Sette cifre</span><span class="sxs-lookup"><span data-stu-id="af424-114">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="af424-115">Checksum</span><span class="sxs-lookup"><span data-stu-id="af424-115">Checksum</span></span>

<span data-ttu-id="af424-116">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="af424-116">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="af424-117">Definizione</span><span class="sxs-lookup"><span data-stu-id="af424-117">Definition</span></span>

<span data-ttu-id="af424-118">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="af424-118">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="af424-119">L'espressione regolare `Regex_austria_eu_passport_number` consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="af424-119">The regular expression  `Regex_austria_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="af424-120">Una parola chiave da `Keywords_austria_eu_passport_number` viene trovato.</span><span class="sxs-lookup"><span data-stu-id="af424-120">A keyword from  `Keywords_austria_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_austria_eu_passport_number" />
          <Match idRef="Keywords_austria_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="af424-121">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="af424-121">Keywords</span></span>

<span data-ttu-id="af424-122">| |</span><span class="sxs-lookup"><span data-stu-id="af424-122"></span></span>
|<span data-ttu-id="af424-123">**Keywords_austria_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="af424-123">**Keywords_austria_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="af424-124">numero di passaporto</span><span class="sxs-lookup"><span data-stu-id="af424-124">passport number</span></span>  <br/> <span data-ttu-id="af424-125">numero di passaporto austriaco</span><span class="sxs-lookup"><span data-stu-id="af424-125">austrian passport number</span></span>  <br/> <span data-ttu-id="af424-126">Passport non</span><span class="sxs-lookup"><span data-stu-id="af424-126">passport no</span></span>  <br/> <span data-ttu-id="af424-127">reisepass</span><span class="sxs-lookup"><span data-stu-id="af424-127">reisepass</span></span>  <br/> <span data-ttu-id="af424-128">österreichisch reisepass</span><span class="sxs-lookup"><span data-stu-id="af424-128">österreichisch reisepass</span></span>  <br/> |
   
## <a name="belgium"></a><span data-ttu-id="af424-129">Belgio</span><span class="sxs-lookup"><span data-stu-id="af424-129">Belgium</span></span>

### <a name="format"></a><span data-ttu-id="af424-130">Formato</span><span class="sxs-lookup"><span data-stu-id="af424-130">Format</span></span>

<span data-ttu-id="af424-131">Due lettere seguite da sei cifre senza spazi o delimitatori</span><span class="sxs-lookup"><span data-stu-id="af424-131">Two letters followed by six digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="af424-132">Modello</span><span class="sxs-lookup"><span data-stu-id="af424-132">Pattern</span></span>

<span data-ttu-id="af424-133">Due lettere e seguita da sei cifre</span><span class="sxs-lookup"><span data-stu-id="af424-133">Two letters and followed by six digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="af424-134">Checksum</span><span class="sxs-lookup"><span data-stu-id="af424-134">Checksum</span></span>

<span data-ttu-id="af424-135">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="af424-135">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="af424-136">Definizione</span><span class="sxs-lookup"><span data-stu-id="af424-136">Definition</span></span>

<span data-ttu-id="af424-137">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="af424-137">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="af424-138">L'espressione regolare `Regex_belgium_eu_passport_number` consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="af424-138">The regular expression  `Regex_belgium_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="af424-139">Una parola chiave da `Keywords_belgium_eu_passport_number` viene trovato.</span><span class="sxs-lookup"><span data-stu-id="af424-139">A keyword from  `Keywords_belgium_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_belgium__eu_passport_number" />
          <Match idRef="Keywords_belgium_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="af424-140">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="af424-140">Keywords</span></span>

<span data-ttu-id="af424-141">| |</span><span class="sxs-lookup"><span data-stu-id="af424-141"></span></span>
|<span data-ttu-id="af424-142">**Keywords_belgium_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="af424-142">**Keywords_belgium_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="af424-143">numero di passaporto</span><span class="sxs-lookup"><span data-stu-id="af424-143">passport number</span></span>  <br/> <span data-ttu-id="af424-144">numero di passaporto belga</span><span class="sxs-lookup"><span data-stu-id="af424-144">belgian passport number</span></span>  <br/> <span data-ttu-id="af424-145">Passport non</span><span class="sxs-lookup"><span data-stu-id="af424-145">passport no</span></span>  <br/> <span data-ttu-id="af424-146">paspoort</span><span class="sxs-lookup"><span data-stu-id="af424-146">paspoort</span></span>  <br/> <span data-ttu-id="af424-147">paspoortnummer</span><span class="sxs-lookup"><span data-stu-id="af424-147">paspoortnummer</span></span>  <br/> <span data-ttu-id="af424-148">reisepass kein</span><span class="sxs-lookup"><span data-stu-id="af424-148">reisepass kein</span></span>  <br/> <span data-ttu-id="af424-149">reisepass</span><span class="sxs-lookup"><span data-stu-id="af424-149">reisepass</span></span>  <br/> |
   
## <a name="bulgaria"></a><span data-ttu-id="af424-150">Bulgaria</span><span class="sxs-lookup"><span data-stu-id="af424-150">Bulgaria</span></span>

### <a name="format"></a><span data-ttu-id="af424-151">Formato</span><span class="sxs-lookup"><span data-stu-id="af424-151">Format</span></span>

<span data-ttu-id="af424-152">Nove cifre senza spazi e i delimitatori</span><span class="sxs-lookup"><span data-stu-id="af424-152">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="af424-153">Modello</span><span class="sxs-lookup"><span data-stu-id="af424-153">Pattern</span></span>

 <span data-ttu-id="af424-154">9 cifre</span><span class="sxs-lookup"><span data-stu-id="af424-154">Nine digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="af424-155">Checksum</span><span class="sxs-lookup"><span data-stu-id="af424-155">Checksum</span></span>

<span data-ttu-id="af424-156">No</span><span class="sxs-lookup"><span data-stu-id="af424-156">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="af424-157">Definizione</span><span class="sxs-lookup"><span data-stu-id="af424-157">Definition</span></span>

<span data-ttu-id="af424-158">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="af424-158">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="af424-159">L'espressione regolare `Regex_bulgaria_eu_passport_number` consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="af424-159">The regular expression  `Regex_bulgaria_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="af424-160">Una parola chiave da `Keywords_bulgaria_eu_passport_number` viene trovato.</span><span class="sxs-lookup"><span data-stu-id="af424-160">A keyword from  `Keywords_bulgaria_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_bulgaria_eu_passport_number" />
          <Match idRef="Keywords_bulgaria_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="af424-161">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="af424-161">Keywords</span></span>

<span data-ttu-id="af424-162">| |</span><span class="sxs-lookup"><span data-stu-id="af424-162"></span></span>
|<span data-ttu-id="af424-163">**Keywords_bulgaria_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="af424-163">**Keywords_bulgaria_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="af424-164">numero di passaporto</span><span class="sxs-lookup"><span data-stu-id="af424-164">passport number</span></span>  <br/> <span data-ttu-id="af424-165">numero di passaporto bulgaro</span><span class="sxs-lookup"><span data-stu-id="af424-165">bulgarian passport number</span></span>  <br/> <span data-ttu-id="af424-166">Passport non</span><span class="sxs-lookup"><span data-stu-id="af424-166">passport no</span></span>  <br/> <span data-ttu-id="af424-167">НОМЕР НА ПАСПОРТА</span><span class="sxs-lookup"><span data-stu-id="af424-167">номер на паспорта</span></span>  <br/> |
   
## <a name="croatia"></a><span data-ttu-id="af424-168">Croazia</span><span class="sxs-lookup"><span data-stu-id="af424-168">Croatia</span></span>

### <a name="format"></a><span data-ttu-id="af424-169">Formato</span><span class="sxs-lookup"><span data-stu-id="af424-169">Format</span></span>

<span data-ttu-id="af424-170">Nove cifre senza spazi e i delimitatori</span><span class="sxs-lookup"><span data-stu-id="af424-170">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="af424-171">Modello</span><span class="sxs-lookup"><span data-stu-id="af424-171">Pattern</span></span>

 <span data-ttu-id="af424-172">9 cifre</span><span class="sxs-lookup"><span data-stu-id="af424-172">Nine digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="af424-173">Checksum</span><span class="sxs-lookup"><span data-stu-id="af424-173">Checksum</span></span>

<span data-ttu-id="af424-174">No</span><span class="sxs-lookup"><span data-stu-id="af424-174">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="af424-175">Definizione</span><span class="sxs-lookup"><span data-stu-id="af424-175">Definition</span></span>

<span data-ttu-id="af424-176">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="af424-176">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="af424-177">L'espressione regolare `Regex_croatia_eu_passport_number` consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="af424-177">The regular expression  `Regex_croatia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="af424-178">Una parola chiave da `Keywords_croatia_eu_passport_number` viene trovato.</span><span class="sxs-lookup"><span data-stu-id="af424-178">A keyword from  `Keywords_croatia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_croatia_eu_passport_number" />
          <Match idRef="Keywords_croatia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="af424-179">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="af424-179">Keywords</span></span>

<span data-ttu-id="af424-180">| |</span><span class="sxs-lookup"><span data-stu-id="af424-180"></span></span>
|<span data-ttu-id="af424-181">**Keywords_croatia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="af424-181">**Keywords_croatia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="af424-182">numero di passaporto</span><span class="sxs-lookup"><span data-stu-id="af424-182">passport number</span></span>  <br/> <span data-ttu-id="af424-183">numero di passaporto croato</span><span class="sxs-lookup"><span data-stu-id="af424-183">croatian passport number</span></span>  <br/> <span data-ttu-id="af424-184">Passport non</span><span class="sxs-lookup"><span data-stu-id="af424-184">passport no</span></span>  <br/> <span data-ttu-id="af424-185">broj putovnice</span><span class="sxs-lookup"><span data-stu-id="af424-185">broj putovnice</span></span>  <br/> |
   
## <a name="cyprus"></a><span data-ttu-id="af424-186">Cipro</span><span class="sxs-lookup"><span data-stu-id="af424-186">Cyprus</span></span>

### <a name="format"></a><span data-ttu-id="af424-187">Formato</span><span class="sxs-lookup"><span data-stu-id="af424-187">Format</span></span>

<span data-ttu-id="af424-188">Una lettera seguita da 6 a 8 cifre senza spazi o delimitatori</span><span class="sxs-lookup"><span data-stu-id="af424-188">One letter followed by 6-8 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="af424-189">Modello</span><span class="sxs-lookup"><span data-stu-id="af424-189">Pattern</span></span>

<span data-ttu-id="af424-190">Una lettera seguita da sei a otto cifre</span><span class="sxs-lookup"><span data-stu-id="af424-190">One letter followed by six to eight digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="af424-191">Checksum</span><span class="sxs-lookup"><span data-stu-id="af424-191">Checksum</span></span>

<span data-ttu-id="af424-192">No</span><span class="sxs-lookup"><span data-stu-id="af424-192">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="af424-193">Definizione</span><span class="sxs-lookup"><span data-stu-id="af424-193">Definition</span></span>

<span data-ttu-id="af424-194">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="af424-194">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="af424-195">L'espressione regolare `Regex_cyprus_eu_passport_number` consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="af424-195">The regular expression  `Regex_cyprus_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="af424-196">Una parola chiave da `Keywords_cyprus_eu_passport_number` viene trovato.</span><span class="sxs-lookup"><span data-stu-id="af424-196">A keyword from  `Keywords_cyprus_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_cyprus_eu_passport_number" />
          <Match idRef="Keywords_cyprus_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="af424-197">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="af424-197">Keywords</span></span>

<span data-ttu-id="af424-198">| |</span><span class="sxs-lookup"><span data-stu-id="af424-198"></span></span>
|<span data-ttu-id="af424-199">**Keywords_cyprus_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="af424-199">**Keywords_cyprus_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="af424-200">numero di passaporto</span><span class="sxs-lookup"><span data-stu-id="af424-200">passport number</span></span>  <br/> <span data-ttu-id="af424-201">numero di passaporto Cipro</span><span class="sxs-lookup"><span data-stu-id="af424-201">cyprus passport number</span></span>  <br/> <span data-ttu-id="af424-202">Passport non</span><span class="sxs-lookup"><span data-stu-id="af424-202">passport no</span></span>  <br/> <span data-ttu-id="af424-203">ΑΡΙΘΜΌ ΔΙΑΒΑΤΗΡΊΟΥ</span><span class="sxs-lookup"><span data-stu-id="af424-203">αριθμό διαβατηρίου</span></span>  <br/> |
   
## <a name="czech-republic"></a><span data-ttu-id="af424-204">Repubblica Ceca</span><span class="sxs-lookup"><span data-stu-id="af424-204">Czech Republic</span></span>

### <a name="format"></a><span data-ttu-id="af424-205">Formato</span><span class="sxs-lookup"><span data-stu-id="af424-205">Format</span></span>

<span data-ttu-id="af424-206">Otto cifre senza spazi o delimitatori</span><span class="sxs-lookup"><span data-stu-id="af424-206">Eight digits without spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="af424-207">Modello</span><span class="sxs-lookup"><span data-stu-id="af424-207">Pattern</span></span>

<span data-ttu-id="af424-208">Otto cifre senza spazi o delimitatori</span><span class="sxs-lookup"><span data-stu-id="af424-208">Eight digits without spaces or delimiters</span></span>
  
### <a name="checksum"></a><span data-ttu-id="af424-209">Checksum</span><span class="sxs-lookup"><span data-stu-id="af424-209">Checksum</span></span>

<span data-ttu-id="af424-210">No</span><span class="sxs-lookup"><span data-stu-id="af424-210">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="af424-211">Definizione</span><span class="sxs-lookup"><span data-stu-id="af424-211">Definition</span></span>

<span data-ttu-id="af424-212">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="af424-212">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="af424-213">L'espressione regolare `Regex_czech_republic_eu_passport_number` consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="af424-213">The regular expression  `Regex_czech_republic_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="af424-214">Una parola chiave da `Keywords_czech_republic_eu_passport_number` viene trovato.</span><span class="sxs-lookup"><span data-stu-id="af424-214">A keyword from  `Keywords_czech_republic_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_czech_republic_eu_passport_number" />
          <Match idRef="Keywords_czech_republic_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="af424-215">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="af424-215">Keywords</span></span>

<span data-ttu-id="af424-216">| |</span><span class="sxs-lookup"><span data-stu-id="af424-216"></span></span>
|<span data-ttu-id="af424-217">**Keywords_czech_republic_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="af424-217">**Keywords_czech_republic_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="af424-218">numero di passaporto</span><span class="sxs-lookup"><span data-stu-id="af424-218">passport number</span></span>  <br/> <span data-ttu-id="af424-219">numero di passaporto ceca</span><span class="sxs-lookup"><span data-stu-id="af424-219">czech passport number</span></span>  <br/> <span data-ttu-id="af424-220">Passport non</span><span class="sxs-lookup"><span data-stu-id="af424-220">passport no</span></span>  <br/> <span data-ttu-id="af424-221">pas cestovní</span><span class="sxs-lookup"><span data-stu-id="af424-221">cestovní pas</span></span>  <br/> <span data-ttu-id="af424-222">PAS</span><span class="sxs-lookup"><span data-stu-id="af424-222">pas</span></span>  <br/> |
   
## <a name="denmark"></a><span data-ttu-id="af424-223">Danimarca</span><span class="sxs-lookup"><span data-stu-id="af424-223">Denmark</span></span>

### <a name="format"></a><span data-ttu-id="af424-224">Formato</span><span class="sxs-lookup"><span data-stu-id="af424-224">Format</span></span>

<span data-ttu-id="af424-225">Nove cifre senza spazi e i delimitatori</span><span class="sxs-lookup"><span data-stu-id="af424-225">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="af424-226">Modello</span><span class="sxs-lookup"><span data-stu-id="af424-226">Pattern</span></span>

 <span data-ttu-id="af424-227">9 cifre</span><span class="sxs-lookup"><span data-stu-id="af424-227">Nine digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="af424-228">Checksum</span><span class="sxs-lookup"><span data-stu-id="af424-228">Checksum</span></span>

<span data-ttu-id="af424-229">No</span><span class="sxs-lookup"><span data-stu-id="af424-229">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="af424-230">Definizione</span><span class="sxs-lookup"><span data-stu-id="af424-230">Definition</span></span>

<span data-ttu-id="af424-231">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="af424-231">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="af424-232">L'espressione regolare `Regex_denmark_eu_passport_number` consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="af424-232">The regular expression  `Regex_denmark_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="af424-233">Una parola chiave da `Keywords_denmark_eu_passport_number` viene trovato.</span><span class="sxs-lookup"><span data-stu-id="af424-233">A keyword from  `Keywords_denmark_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_denmark_eu_passport_number" />
          <Match idRef="Keywords_denmark_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="af424-234">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="af424-234">Keywords</span></span>

<span data-ttu-id="af424-235">| |</span><span class="sxs-lookup"><span data-stu-id="af424-235"></span></span>
|<span data-ttu-id="af424-236">**Keywords_denmark_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="af424-236">**Keywords_denmark_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="af424-237">numero di passaporto</span><span class="sxs-lookup"><span data-stu-id="af424-237">passport number</span></span>  <br/> <span data-ttu-id="af424-238">numero di passaporto danese</span><span class="sxs-lookup"><span data-stu-id="af424-238">danish passport number</span></span>  <br/> <span data-ttu-id="af424-239">Passport non</span><span class="sxs-lookup"><span data-stu-id="af424-239">passport no</span></span>  <br/> <span data-ttu-id="af424-240">PAS</span><span class="sxs-lookup"><span data-stu-id="af424-240">pas</span></span>  <br/> <span data-ttu-id="af424-241">pasnummer</span><span class="sxs-lookup"><span data-stu-id="af424-241">pasnummer</span></span>  <br/> |
   
## <a name="estonia"></a><span data-ttu-id="af424-242">Estonia</span><span class="sxs-lookup"><span data-stu-id="af424-242">Estonia</span></span>

### <a name="format"></a><span data-ttu-id="af424-243">Formato</span><span class="sxs-lookup"><span data-stu-id="af424-243">Format</span></span>

<span data-ttu-id="af424-244">Una lettera seguita da sette cifre senza spazi o delimitatori</span><span class="sxs-lookup"><span data-stu-id="af424-244">One letter followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="af424-245">Modello</span><span class="sxs-lookup"><span data-stu-id="af424-245">Pattern</span></span>

<span data-ttu-id="af424-246">Una lettera seguita da sette cifre</span><span class="sxs-lookup"><span data-stu-id="af424-246">One letter followed by seven digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="af424-247">Checksum</span><span class="sxs-lookup"><span data-stu-id="af424-247">Checksum</span></span>

<span data-ttu-id="af424-248">No</span><span class="sxs-lookup"><span data-stu-id="af424-248">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="af424-249">Definizione</span><span class="sxs-lookup"><span data-stu-id="af424-249">Definition</span></span>

<span data-ttu-id="af424-250">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="af424-250">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="af424-251">L'espressione regolare `Regex_estonia_eu_passport_number` consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="af424-251">The regular expression  `Regex_estonia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="af424-252">Una parola chiave da `Keywords_estonia_eu_passport_number` viene trovato.</span><span class="sxs-lookup"><span data-stu-id="af424-252">A keyword from  `Keywords_estonia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_estonia_eu_passport_number" />
          <Match idRef="Keywords_estonia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="af424-253">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="af424-253">Keywords</span></span>

<span data-ttu-id="af424-254">| |</span><span class="sxs-lookup"><span data-stu-id="af424-254"></span></span>
|<span data-ttu-id="af424-255">**Keywords_estonia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="af424-255">**Keywords_estonia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="af424-256">numero di passaporto</span><span class="sxs-lookup"><span data-stu-id="af424-256">passport number</span></span>  <br/> <span data-ttu-id="af424-257">numero di passaporto estone</span><span class="sxs-lookup"><span data-stu-id="af424-257">estonian passport number</span></span>  <br/> <span data-ttu-id="af424-258">Passport non</span><span class="sxs-lookup"><span data-stu-id="af424-258">passport no</span></span>  <br/> <span data-ttu-id="af424-259">eesti kodaniku pass</span><span class="sxs-lookup"><span data-stu-id="af424-259">eesti kodaniku pass</span></span>  <br/> |
   
## <a name="finland"></a><span data-ttu-id="af424-260">Finlandia</span><span class="sxs-lookup"><span data-stu-id="af424-260">Finland</span></span>

<span data-ttu-id="af424-261">Per ulteriori informazioni, vedere la sezione "Numero di passaporto Finlandia" in [cercare il quali i tipi di informazioni riservate](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="af424-261">For details, see the section "Finland Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="france"></a><span data-ttu-id="af424-262">Francia</span><span class="sxs-lookup"><span data-stu-id="af424-262">France</span></span>

<span data-ttu-id="af424-263">Per ulteriori informazioni, vedere la sezione "Numero di passaporto Francia" in [cercare il quali i tipi di informazioni riservate](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="af424-263">For details, see the section "France Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="germany"></a><span data-ttu-id="af424-264">Germania</span><span class="sxs-lookup"><span data-stu-id="af424-264">Germany</span></span>

<span data-ttu-id="af424-265">Per ulteriori informazioni, vedere la sezione "Numero di passaporto Germania" in [cercare il quali i tipi di informazioni riservate](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="af424-265">For details, see the section "Germany Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="greece"></a><span data-ttu-id="af424-266">Grecia</span><span class="sxs-lookup"><span data-stu-id="af424-266">Greece</span></span>

### <a name="format"></a><span data-ttu-id="af424-267">Formato</span><span class="sxs-lookup"><span data-stu-id="af424-267">Format</span></span>

<span data-ttu-id="af424-268">Due lettere seguite da sette cifre senza spazi o delimitatori</span><span class="sxs-lookup"><span data-stu-id="af424-268">Two letters followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="af424-269">Modello</span><span class="sxs-lookup"><span data-stu-id="af424-269">Pattern</span></span>

<span data-ttu-id="af424-270">Due lettere seguite da 7 cifre</span><span class="sxs-lookup"><span data-stu-id="af424-270">Two letters followed by seven digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="af424-271">Checksum</span><span class="sxs-lookup"><span data-stu-id="af424-271">Checksum</span></span>

<span data-ttu-id="af424-272">No</span><span class="sxs-lookup"><span data-stu-id="af424-272">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="af424-273">Definizione</span><span class="sxs-lookup"><span data-stu-id="af424-273">Definition</span></span>

<span data-ttu-id="af424-274">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="af424-274">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="af424-275">L'espressione regolare `Regex_greece_eu_passport_number` consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="af424-275">The regular expression  `Regex_greece_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="af424-276">Una parola chiave da `Keywords_greece_eu_passport_number` viene trovato.</span><span class="sxs-lookup"><span data-stu-id="af424-276">A keyword from  `Keywords_greece_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_greece_eu_passport_number" />
          <Match idRef="Keywords_greece_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="af424-277">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="af424-277">Keywords</span></span>

<span data-ttu-id="af424-278">| |</span><span class="sxs-lookup"><span data-stu-id="af424-278"></span></span>
|<span data-ttu-id="af424-279">**Keywords_greece_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="af424-279">**Keywords_greece_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="af424-280">numero di passaporto</span><span class="sxs-lookup"><span data-stu-id="af424-280">passport number</span></span>  <br/> <span data-ttu-id="af424-281">numero di passaporto greca</span><span class="sxs-lookup"><span data-stu-id="af424-281">greek passport number</span></span>  <br/> <span data-ttu-id="af424-282">Passport non</span><span class="sxs-lookup"><span data-stu-id="af424-282">passport no</span></span>  <br/> <span data-ttu-id="af424-283">ΔΙΑΒΑΤΗΡΙΟ</span><span class="sxs-lookup"><span data-stu-id="af424-283">διαβατηριο</span></span>  <br/> |
   
## <a name="hungary"></a><span data-ttu-id="af424-284">Ungheria</span><span class="sxs-lookup"><span data-stu-id="af424-284">Hungary</span></span>

### <a name="format"></a><span data-ttu-id="af424-285">Formato</span><span class="sxs-lookup"><span data-stu-id="af424-285">Format</span></span>

<span data-ttu-id="af424-286">Due lettere seguite da sei o sette cifre senza spazi o delimitatori</span><span class="sxs-lookup"><span data-stu-id="af424-286">Two letters followed by six or seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="af424-287">Modello</span><span class="sxs-lookup"><span data-stu-id="af424-287">Pattern</span></span>

<span data-ttu-id="af424-288">Due lettere seguite da sei o sette cifre</span><span class="sxs-lookup"><span data-stu-id="af424-288">Two letters followed by six or seven digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="af424-289">Checksum</span><span class="sxs-lookup"><span data-stu-id="af424-289">Checksum</span></span>

<span data-ttu-id="af424-290">No</span><span class="sxs-lookup"><span data-stu-id="af424-290">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="af424-291">Definizione</span><span class="sxs-lookup"><span data-stu-id="af424-291">Definition</span></span>

<span data-ttu-id="af424-292">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="af424-292">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="af424-293">L'espressione regolare `Regex_hungary_eu_passport_number` consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="af424-293">The regular expression  `Regex_hungary_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="af424-294">Una parola chiave da `Keywords_hungary_eu_passport_number` viene trovato.</span><span class="sxs-lookup"><span data-stu-id="af424-294">A keyword from  `Keywords_hungary_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_hungary_eu_passport_number" />
          <Match idRef="Keywords_hungary_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="af424-295">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="af424-295">Keywords</span></span>

<span data-ttu-id="af424-296">| |</span><span class="sxs-lookup"><span data-stu-id="af424-296"></span></span>
|<span data-ttu-id="af424-297">**Keywords_hungary_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="af424-297">**Keywords_hungary_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="af424-298">numero di passaporto</span><span class="sxs-lookup"><span data-stu-id="af424-298">passport number</span></span>  <br/> <span data-ttu-id="af424-299">numero di passaporto ungherese</span><span class="sxs-lookup"><span data-stu-id="af424-299">hungarian passport number</span></span>  <br/> <span data-ttu-id="af424-300">Passport non</span><span class="sxs-lookup"><span data-stu-id="af424-300">passport no</span></span>  <br/> <span data-ttu-id="af424-301">útlevél száma</span><span class="sxs-lookup"><span data-stu-id="af424-301">útlevél száma</span></span>  <br/> |
   
## <a name="ireland"></a><span data-ttu-id="af424-302">Irlanda</span><span class="sxs-lookup"><span data-stu-id="af424-302">Ireland</span></span>

### <a name="format"></a><span data-ttu-id="af424-303">Formato</span><span class="sxs-lookup"><span data-stu-id="af424-303">Format</span></span>

<span data-ttu-id="af424-304">Due lettere o cifre seguiti da sette cifre senza spazi o delimitatori</span><span class="sxs-lookup"><span data-stu-id="af424-304">Two letters or digits followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="af424-305">Modello</span><span class="sxs-lookup"><span data-stu-id="af424-305">Pattern</span></span>

<span data-ttu-id="af424-306">Due lettere o cifre seguiti da sette cifre:</span><span class="sxs-lookup"><span data-stu-id="af424-306">Two letters or digits followed by seven digits:</span></span>
  
- <span data-ttu-id="af424-307">Due cifre o lettere (senza distinzione tra maiuscole/minuscole)</span><span class="sxs-lookup"><span data-stu-id="af424-307">Two digits or letters (not case sensitive)</span></span>
    
- <span data-ttu-id="af424-308">Sette cifre</span><span class="sxs-lookup"><span data-stu-id="af424-308">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="af424-309">Checksum</span><span class="sxs-lookup"><span data-stu-id="af424-309">Checksum</span></span>

<span data-ttu-id="af424-310">No</span><span class="sxs-lookup"><span data-stu-id="af424-310">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="af424-311">Definizione</span><span class="sxs-lookup"><span data-stu-id="af424-311">Definition</span></span>

<span data-ttu-id="af424-312">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="af424-312">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="af424-313">L'espressione regolare `Regex_ireland_eu_passport_number` consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="af424-313">The regular expression  `Regex_ireland_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="af424-314">Una parola chiave da `Keywords_ireland_eu_passport_number` viene trovato.</span><span class="sxs-lookup"><span data-stu-id="af424-314">A keyword from  `Keywords_ireland_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_ireland_eu_passport_number" />
          <Match idRef="Keywords_ireland_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="af424-315">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="af424-315">Keywords</span></span>

<span data-ttu-id="af424-316">| |</span><span class="sxs-lookup"><span data-stu-id="af424-316"></span></span>
|<span data-ttu-id="af424-317">**Keywords_ireland_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="af424-317">**Keywords_ireland_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="af424-318">numero di passaporto</span><span class="sxs-lookup"><span data-stu-id="af424-318">passport number</span></span>  <br/> <span data-ttu-id="af424-319">numero di passaporto irlandese</span><span class="sxs-lookup"><span data-stu-id="af424-319">irish passport number</span></span>  <br/> <span data-ttu-id="af424-320">Passport non</span><span class="sxs-lookup"><span data-stu-id="af424-320">passport no</span></span>  <br/> <span data-ttu-id="af424-321">PAS</span><span class="sxs-lookup"><span data-stu-id="af424-321">pas</span></span>  <br/> <span data-ttu-id="af424-322">passport</span><span class="sxs-lookup"><span data-stu-id="af424-322">passport</span></span>  <br/> <span data-ttu-id="af424-323">passeport</span><span class="sxs-lookup"><span data-stu-id="af424-323">passeport</span></span>  <br/> <span data-ttu-id="af424-324">numero passeport</span><span class="sxs-lookup"><span data-stu-id="af424-324">passeport numero</span></span>  <br/> |
   
## <a name="italy"></a><span data-ttu-id="af424-325">Italia</span><span class="sxs-lookup"><span data-stu-id="af424-325">Italy</span></span>

### <a name="format"></a><span data-ttu-id="af424-326">Formato</span><span class="sxs-lookup"><span data-stu-id="af424-326">Format</span></span>

<span data-ttu-id="af424-327">Due lettere o cifre seguiti da sette cifre senza spazi o delimitatori</span><span class="sxs-lookup"><span data-stu-id="af424-327">Two letters or digits followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="af424-328">Modello</span><span class="sxs-lookup"><span data-stu-id="af424-328">Pattern</span></span>

<span data-ttu-id="af424-329">Due lettere o cifre seguiti da sette cifre:</span><span class="sxs-lookup"><span data-stu-id="af424-329">Two letters or digits followed by seven digits:</span></span>
  
- <span data-ttu-id="af424-330">Due cifre o lettere (senza distinzione tra maiuscole/minuscole)</span><span class="sxs-lookup"><span data-stu-id="af424-330">Two digits or letters (not case sensitive)</span></span>
    
- <span data-ttu-id="af424-331">Sette cifre</span><span class="sxs-lookup"><span data-stu-id="af424-331">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="af424-332">Checksum</span><span class="sxs-lookup"><span data-stu-id="af424-332">Checksum</span></span>

<span data-ttu-id="af424-333">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="af424-333">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="af424-334">Definizione</span><span class="sxs-lookup"><span data-stu-id="af424-334">Definition</span></span>

<span data-ttu-id="af424-335">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="af424-335">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="af424-336">L'espressione regolare `Regex_italy_eu_passport_number` consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="af424-336">The regular expression  `Regex_italy_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="af424-337">Una parola chiave da `Keywords_italy_eu_passport_number` viene trovato.</span><span class="sxs-lookup"><span data-stu-id="af424-337">A keyword from  `Keywords_italy_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_italy_eu_passport_number" />
          <Match idRef="Keywords_italy_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="af424-338">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="af424-338">Keywords</span></span>

<span data-ttu-id="af424-339">| |</span><span class="sxs-lookup"><span data-stu-id="af424-339"></span></span>
|<span data-ttu-id="af424-340">**Keywords_italy_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="af424-340">**Keywords_italy_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="af424-341">numero di passaporto italiano</span><span class="sxs-lookup"><span data-stu-id="af424-341">italian passport number</span></span>  <br/> <span data-ttu-id="af424-342">Repubblica italiana passaporto</span><span class="sxs-lookup"><span data-stu-id="af424-342">repubblica italiana passaporto</span></span>  <br/> <span data-ttu-id="af424-343">passaporto</span><span class="sxs-lookup"><span data-stu-id="af424-343">passaporto</span></span>  <br/> <span data-ttu-id="af424-344">passaporto italiana</span><span class="sxs-lookup"><span data-stu-id="af424-344">passaporto italiana</span></span>  <br/> <span data-ttu-id="af424-345">numero di passaporto</span><span class="sxs-lookup"><span data-stu-id="af424-345">passport number</span></span>  <br/> <span data-ttu-id="af424-346">numero di passaporto italiana</span><span class="sxs-lookup"><span data-stu-id="af424-346">italiana passaporto numero</span></span>  <br/> <span data-ttu-id="af424-347">numero di passaporto</span><span class="sxs-lookup"><span data-stu-id="af424-347">passaporto numero</span></span>  <br/> <span data-ttu-id="af424-348">numéro passeport italien</span><span class="sxs-lookup"><span data-stu-id="af424-348">numéro passeport italien</span></span>  <br/> <span data-ttu-id="af424-349">numéro passeport</span><span class="sxs-lookup"><span data-stu-id="af424-349">numéro passeport</span></span>  <br/> |
   
## <a name="latvia"></a><span data-ttu-id="af424-350">Lettonia</span><span class="sxs-lookup"><span data-stu-id="af424-350">Latvia</span></span>

### <a name="format"></a><span data-ttu-id="af424-351">Formato</span><span class="sxs-lookup"><span data-stu-id="af424-351">Format</span></span>

<span data-ttu-id="af424-352">Due lettere o cifre seguiti da sette cifre senza spazi o delimitatori</span><span class="sxs-lookup"><span data-stu-id="af424-352">Two letters or digits followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="af424-353">Modello</span><span class="sxs-lookup"><span data-stu-id="af424-353">Pattern</span></span>

<span data-ttu-id="af424-354">Due lettere o cifre seguiti da sette cifre:</span><span class="sxs-lookup"><span data-stu-id="af424-354">Two letters or digits followed by seven digits:</span></span>
  
- <span data-ttu-id="af424-355">Due cifre o lettere (senza distinzione tra maiuscole/minuscole)</span><span class="sxs-lookup"><span data-stu-id="af424-355">Two digits or letters (not case sensitive)</span></span>
    
- <span data-ttu-id="af424-356">Sette cifre</span><span class="sxs-lookup"><span data-stu-id="af424-356">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="af424-357">Checksum</span><span class="sxs-lookup"><span data-stu-id="af424-357">Checksum</span></span>

<span data-ttu-id="af424-358">No</span><span class="sxs-lookup"><span data-stu-id="af424-358">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="af424-359">Definizione</span><span class="sxs-lookup"><span data-stu-id="af424-359">Definition</span></span>

<span data-ttu-id="af424-360">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="af424-360">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="af424-361">L'espressione regolare `Regex_latvia_eu_passport_number` consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="af424-361">The regular expression  `Regex_latvia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="af424-362">Una parola chiave da `Keywords_latvia_eu_passport_number` viene trovato.</span><span class="sxs-lookup"><span data-stu-id="af424-362">A keyword from  `Keywords_latvia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_latvia_eu_passport_number" />
          <Match idRef="Keywords_latvia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="af424-363">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="af424-363">Keywords</span></span>

<span data-ttu-id="af424-364">| |</span><span class="sxs-lookup"><span data-stu-id="af424-364"></span></span>
|<span data-ttu-id="af424-365">**Keywords_latvia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="af424-365">**Keywords_latvia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="af424-366">numero di passaporto</span><span class="sxs-lookup"><span data-stu-id="af424-366">passport number</span></span>  <br/> <span data-ttu-id="af424-367">numero di passaporto lettone</span><span class="sxs-lookup"><span data-stu-id="af424-367">latvian passport number</span></span>  <br/> <span data-ttu-id="af424-368">Passport non</span><span class="sxs-lookup"><span data-stu-id="af424-368">passport no</span></span>  <br/> <span data-ttu-id="af424-369">pase numurs</span><span class="sxs-lookup"><span data-stu-id="af424-369">pase numurs</span></span>  <br/> |
   
## <a name="lithuania"></a><span data-ttu-id="af424-370">Lituania</span><span class="sxs-lookup"><span data-stu-id="af424-370">Lithuania</span></span>

### <a name="format"></a><span data-ttu-id="af424-371">Formato</span><span class="sxs-lookup"><span data-stu-id="af424-371">Format</span></span>

<span data-ttu-id="af424-372">Otto cifre o lettere senza spazi o delimitatori</span><span class="sxs-lookup"><span data-stu-id="af424-372">Eight digits or letters with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="af424-373">Modello</span><span class="sxs-lookup"><span data-stu-id="af424-373">Pattern</span></span>

<span data-ttu-id="af424-374">Otto cifre o lettere (non maiuscole/minuscole)</span><span class="sxs-lookup"><span data-stu-id="af424-374">Eight digits or letters (not case sensitive)</span></span>
  
### <a name="checksum"></a><span data-ttu-id="af424-375">Checksum</span><span class="sxs-lookup"><span data-stu-id="af424-375">Checksum</span></span>

<span data-ttu-id="af424-376">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="af424-376">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="af424-377">Definizione</span><span class="sxs-lookup"><span data-stu-id="af424-377">Definition</span></span>

<span data-ttu-id="af424-378">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="af424-378">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="af424-379">L'espressione regolare `Regex_lithuania_eu_passport_number` consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="af424-379">The regular expression  `Regex_lithuania_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="af424-380">Una parola chiave da `Keywords_lithuania_eu_passport_number` viene trovato.</span><span class="sxs-lookup"><span data-stu-id="af424-380">A keyword from  `Keywords_lithuania_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_lithuania_eu_passport_number" />
          <Match idRef="Keywords_lithuania_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="af424-381">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="af424-381">Keywords</span></span>

<span data-ttu-id="af424-382">| |</span><span class="sxs-lookup"><span data-stu-id="af424-382"></span></span>
|<span data-ttu-id="af424-383">**Keywords_lithuania_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="af424-383">**Keywords_lithuania_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="af424-384">numero di passaporto</span><span class="sxs-lookup"><span data-stu-id="af424-384">passport number</span></span>  <br/> <span data-ttu-id="af424-385">numero di passaporto lithunian</span><span class="sxs-lookup"><span data-stu-id="af424-385">lithunian passport number</span></span>  <br/> <span data-ttu-id="af424-386">Passport non</span><span class="sxs-lookup"><span data-stu-id="af424-386">passport no</span></span>  <br/> <span data-ttu-id="af424-387">paso numeris</span><span class="sxs-lookup"><span data-stu-id="af424-387">paso numeris</span></span>  <br/> |
   
## <a name="luxemburg"></a><span data-ttu-id="af424-388">Lussemburgo</span><span class="sxs-lookup"><span data-stu-id="af424-388">Luxemburg</span></span>

### <a name="format"></a><span data-ttu-id="af424-389">Formato</span><span class="sxs-lookup"><span data-stu-id="af424-389">Format</span></span>

<span data-ttu-id="af424-390">Otto cifre o lettere senza spazi o delimitatori</span><span class="sxs-lookup"><span data-stu-id="af424-390">Eight digits or letters with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="af424-391">Modello</span><span class="sxs-lookup"><span data-stu-id="af424-391">Pattern</span></span>

<span data-ttu-id="af424-392">Otto cifre o lettere (non maiuscole/minuscole)</span><span class="sxs-lookup"><span data-stu-id="af424-392">Eight digits or letters (not case sensitive)</span></span>
  
### <a name="checksum"></a><span data-ttu-id="af424-393">Checksum</span><span class="sxs-lookup"><span data-stu-id="af424-393">Checksum</span></span>

<span data-ttu-id="af424-394">No</span><span class="sxs-lookup"><span data-stu-id="af424-394">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="af424-395">Definizione</span><span class="sxs-lookup"><span data-stu-id="af424-395">Definition</span></span>

<span data-ttu-id="af424-396">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="af424-396">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="af424-397">L'espressione regolare `Regex_nation_eu_passport_number` consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="af424-397">The regular expression  `Regex_nation_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="af424-398">Una parola chiave da `Keywords_nation_eu_passport_number` viene trovato.</span><span class="sxs-lookup"><span data-stu-id="af424-398">A keyword from  `Keywords_nation_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_nation_eu_passport_number" />
          <Match idRef="Keywords_nation_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="af424-399">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="af424-399">Keywords</span></span>

<span data-ttu-id="af424-400">| |</span><span class="sxs-lookup"><span data-stu-id="af424-400"></span></span>
|<span data-ttu-id="af424-401">**Keywords_nation_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="af424-401">**Keywords_nation_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="af424-402">numero di passaporto</span><span class="sxs-lookup"><span data-stu-id="af424-402">passport number</span></span>  <br/> <span data-ttu-id="af424-403">numero di passaporto lettone</span><span class="sxs-lookup"><span data-stu-id="af424-403">latvian passport number</span></span>  <br/> <span data-ttu-id="af424-404">Passport non</span><span class="sxs-lookup"><span data-stu-id="af424-404">passport no</span></span>  <br/> <span data-ttu-id="af424-405">passnummer</span><span class="sxs-lookup"><span data-stu-id="af424-405">passnummer</span></span>  <br/> |
   
## <a name="malta"></a><span data-ttu-id="af424-406">Malta</span><span class="sxs-lookup"><span data-stu-id="af424-406">Malta</span></span>

### <a name="format"></a><span data-ttu-id="af424-407">Formato</span><span class="sxs-lookup"><span data-stu-id="af424-407">Format</span></span>

<span data-ttu-id="af424-408">Sette cifre senza spazi o delimitatori</span><span class="sxs-lookup"><span data-stu-id="af424-408">Seven digits without spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="af424-409">Modello</span><span class="sxs-lookup"><span data-stu-id="af424-409">Pattern</span></span>

 <span data-ttu-id="af424-410">Sette cifre</span><span class="sxs-lookup"><span data-stu-id="af424-410">Seven digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="af424-411">Checksum</span><span class="sxs-lookup"><span data-stu-id="af424-411">Checksum</span></span>

<span data-ttu-id="af424-412">No</span><span class="sxs-lookup"><span data-stu-id="af424-412">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="af424-413">Definizione</span><span class="sxs-lookup"><span data-stu-id="af424-413">Definition</span></span>

<span data-ttu-id="af424-414">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="af424-414">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="af424-415">L'espressione regolare `Regex_malta_eu_passport_number` consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="af424-415">The regular expression  `Regex_malta_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="af424-416">Una parola chiave da `Keywords_malta_eu_passport_number` viene trovato.</span><span class="sxs-lookup"><span data-stu-id="af424-416">A keyword from  `Keywords_malta_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_malta_eu_passport_number" />
          <Match idRef="Keywords_malta_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="af424-417">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="af424-417">Keywords</span></span>

<span data-ttu-id="af424-418">| |</span><span class="sxs-lookup"><span data-stu-id="af424-418"></span></span>
|<span data-ttu-id="af424-419">**Keywords_malta_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="af424-419">**Keywords_malta_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="af424-420">numero di passaporto</span><span class="sxs-lookup"><span data-stu-id="af424-420">passport number</span></span>  <br/> <span data-ttu-id="af424-421">numero di passaporto maltese</span><span class="sxs-lookup"><span data-stu-id="af424-421">maltese passport number</span></span>  <br/> <span data-ttu-id="af424-422">Passport non</span><span class="sxs-lookup"><span data-stu-id="af424-422">passport no</span></span>  <br/> <span data-ttu-id="af424-423">numru tal-passaport</span><span class="sxs-lookup"><span data-stu-id="af424-423">numru tal-passaport</span></span>  <br/> |
   
## <a name="netherlands"></a><span data-ttu-id="af424-424">Paesi Bassi</span><span class="sxs-lookup"><span data-stu-id="af424-424">Netherlands</span></span>

### <a name="format"></a><span data-ttu-id="af424-425">Formato</span><span class="sxs-lookup"><span data-stu-id="af424-425">Format</span></span>

<span data-ttu-id="af424-426">Nove lettere o cifre senza spazi o delimitatori</span><span class="sxs-lookup"><span data-stu-id="af424-426">Nine letters or digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="af424-427">Modello</span><span class="sxs-lookup"><span data-stu-id="af424-427">Pattern</span></span>

<span data-ttu-id="af424-428">Nove lettere o cifre</span><span class="sxs-lookup"><span data-stu-id="af424-428">Nine letters or digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="af424-429">Checksum</span><span class="sxs-lookup"><span data-stu-id="af424-429">Checksum</span></span>

<span data-ttu-id="af424-430">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="af424-430">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="af424-431">Definizione</span><span class="sxs-lookup"><span data-stu-id="af424-431">Definition</span></span>

<span data-ttu-id="af424-432">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="af424-432">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="af424-433">L'espressione regolare `Regex_netherlands_eu_passport_number` consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="af424-433">The regular expression  `Regex_netherlands_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="af424-434">Una parola chiave da `Keywords_netherlands_eu_passport_number` viene trovato.</span><span class="sxs-lookup"><span data-stu-id="af424-434">A keyword from  `Keywords_netherlands_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_netherlands_eu_passport_number" />
          <Match idRef="Keywords_netherlands_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="af424-435">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="af424-435">Keywords</span></span>

<span data-ttu-id="af424-436">| |</span><span class="sxs-lookup"><span data-stu-id="af424-436"></span></span>
|<span data-ttu-id="af424-437">**Keywords_netherlands_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="af424-437">**Keywords_netherlands_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="af424-438">numero di passaporto olandese</span><span class="sxs-lookup"><span data-stu-id="af424-438">dutch passport number</span></span>  <br/> <span data-ttu-id="af424-439">numero di passaporto</span><span class="sxs-lookup"><span data-stu-id="af424-439">passport number</span></span>  <br/> <span data-ttu-id="af424-440">numero di passaporto Paesi Bassi</span><span class="sxs-lookup"><span data-stu-id="af424-440">netherlands passport number</span></span>  <br/> <span data-ttu-id="af424-441">nederlanden paspoort nummer</span><span class="sxs-lookup"><span data-stu-id="af424-441">nederlanden paspoort nummer</span></span>  <br/> <span data-ttu-id="af424-442">paspoort</span><span class="sxs-lookup"><span data-stu-id="af424-442">paspoort</span></span>  <br/> <span data-ttu-id="af424-443">nederlanden paspoortnummer</span><span class="sxs-lookup"><span data-stu-id="af424-443">nederlanden paspoortnummer</span></span>  <br/> <span data-ttu-id="af424-444">paspoortnummer</span><span class="sxs-lookup"><span data-stu-id="af424-444">paspoortnummer</span></span>  <br/> |
   
## <a name="poland"></a><span data-ttu-id="af424-445">Polonia</span><span class="sxs-lookup"><span data-stu-id="af424-445">Poland</span></span>

<span data-ttu-id="af424-446">Per ulteriori informazioni, vedere la sezione "Numero di passaporto Polonia" in [cercare il quali i tipi di informazioni riservate](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="af424-446">For details, see the section "Poland Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="portugal"></a><span data-ttu-id="af424-447">Portogallo</span><span class="sxs-lookup"><span data-stu-id="af424-447">Portugal</span></span>

### <a name="format"></a><span data-ttu-id="af424-448">Formato</span><span class="sxs-lookup"><span data-stu-id="af424-448">Format</span></span>

<span data-ttu-id="af424-449">Una lettera seguita da sei cifre senza spazi o delimitatori</span><span class="sxs-lookup"><span data-stu-id="af424-449">One letter followed by six digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="af424-450">Modello</span><span class="sxs-lookup"><span data-stu-id="af424-450">Pattern</span></span>

<span data-ttu-id="af424-451">Una lettera seguita da sei cifre:</span><span class="sxs-lookup"><span data-stu-id="af424-451">One letter followed by six digits:</span></span>
  
- <span data-ttu-id="af424-452">Una lettera (senza distinzione tra maiuscole/minuscole)</span><span class="sxs-lookup"><span data-stu-id="af424-452">One letter (not case sensitive)</span></span>
    
- <span data-ttu-id="af424-453">Sei cifre</span><span class="sxs-lookup"><span data-stu-id="af424-453">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="af424-454">Checksum</span><span class="sxs-lookup"><span data-stu-id="af424-454">Checksum</span></span>

<span data-ttu-id="af424-455">No</span><span class="sxs-lookup"><span data-stu-id="af424-455">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="af424-456">Definizione</span><span class="sxs-lookup"><span data-stu-id="af424-456">Definition</span></span>

<span data-ttu-id="af424-457">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="af424-457">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="af424-458">L'espressione regolare `Regex_portugal_eu_passport_number` consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="af424-458">The regular expression  `Regex_portugal_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="af424-459">Una parola chiave da `Keywords_portugal_eu_passport_number` viene trovato.</span><span class="sxs-lookup"><span data-stu-id="af424-459">A keyword from  `Keywords_portugal_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_portugal_eu_passport_number" />
          <Match idRef="Keywords_portugal_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="af424-460">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="af424-460">Keywords</span></span>

<span data-ttu-id="af424-461">| |</span><span class="sxs-lookup"><span data-stu-id="af424-461"></span></span>
|<span data-ttu-id="af424-462">**Keywords_portugal_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="af424-462">**Keywords_portugal_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="af424-463">numero di passaporto</span><span class="sxs-lookup"><span data-stu-id="af424-463">passport number</span></span>  <br/> <span data-ttu-id="af424-464">numero di passaporto portoghese</span><span class="sxs-lookup"><span data-stu-id="af424-464">portuguese passport number</span></span>  <br/> <span data-ttu-id="af424-465">Passport non</span><span class="sxs-lookup"><span data-stu-id="af424-465">passport no</span></span>  <br/> <span data-ttu-id="af424-466">número passaporte</span><span class="sxs-lookup"><span data-stu-id="af424-466">número do passaporte</span></span>  <br/> |
   
## <a name="romania"></a><span data-ttu-id="af424-467">Romania</span><span class="sxs-lookup"><span data-stu-id="af424-467">Romania</span></span>

### <a name="format"></a><span data-ttu-id="af424-468">Formato</span><span class="sxs-lookup"><span data-stu-id="af424-468">Format</span></span>

<span data-ttu-id="af424-469">Otto o nove cifre senza spazi e i delimitatori</span><span class="sxs-lookup"><span data-stu-id="af424-469">Eight or nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="af424-470">Modello</span><span class="sxs-lookup"><span data-stu-id="af424-470">Pattern</span></span>

<span data-ttu-id="af424-471">Otto o nove cifre</span><span class="sxs-lookup"><span data-stu-id="af424-471">Eight or nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="af424-472">Checksum</span><span class="sxs-lookup"><span data-stu-id="af424-472">Checksum</span></span>

<span data-ttu-id="af424-473">No</span><span class="sxs-lookup"><span data-stu-id="af424-473">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="af424-474">Definizione</span><span class="sxs-lookup"><span data-stu-id="af424-474">Definition</span></span>

<span data-ttu-id="af424-475">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="af424-475">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="af424-476">L'espressione regolare `Regex_romania_eu_passport_number` consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="af424-476">The regular expression  `Regex_romania_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="af424-477">Una parola chiave da `Keywords_romania_eu_passport_number` viene trovato.</span><span class="sxs-lookup"><span data-stu-id="af424-477">A keyword from  `Keywords_romania_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_romania_eu_passport_number" />
          <Match idRef="Keywords_romania_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="af424-478">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="af424-478">Keywords</span></span>

<span data-ttu-id="af424-479">| |</span><span class="sxs-lookup"><span data-stu-id="af424-479"></span></span>
|<span data-ttu-id="af424-480">**Keywords_romania_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="af424-480">**Keywords_romania_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="af424-481">numero di passaporto</span><span class="sxs-lookup"><span data-stu-id="af424-481">passport number</span></span>  <br/> <span data-ttu-id="af424-482">numero di passaporto rumeno</span><span class="sxs-lookup"><span data-stu-id="af424-482">romanian passport number</span></span>  <br/> <span data-ttu-id="af424-483">Passport non</span><span class="sxs-lookup"><span data-stu-id="af424-483">passport no</span></span>  <br/> <span data-ttu-id="af424-484">numărul pașaportului</span><span class="sxs-lookup"><span data-stu-id="af424-484">numărul pașaportului</span></span>  <br/> |
   
## <a name="slovakia"></a><span data-ttu-id="af424-485">Slovacchia</span><span class="sxs-lookup"><span data-stu-id="af424-485">Slovakia</span></span>

### <a name="format"></a><span data-ttu-id="af424-486">Formato</span><span class="sxs-lookup"><span data-stu-id="af424-486">Format</span></span>

<span data-ttu-id="af424-487">Una cifra o una lettera seguito da sette cifre senza spazi o delimitatori</span><span class="sxs-lookup"><span data-stu-id="af424-487">One digit or letter followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="af424-488">Modello</span><span class="sxs-lookup"><span data-stu-id="af424-488">Pattern</span></span>

<span data-ttu-id="af424-489">Una cifra o una lettera (non maiuscole/minuscole) seguito da sette cifre</span><span class="sxs-lookup"><span data-stu-id="af424-489">One digit or letter (not case sensitive) followed by seven digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="af424-490">Checksum</span><span class="sxs-lookup"><span data-stu-id="af424-490">Checksum</span></span>

<span data-ttu-id="af424-491">No</span><span class="sxs-lookup"><span data-stu-id="af424-491">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="af424-492">Definizione</span><span class="sxs-lookup"><span data-stu-id="af424-492">Definition</span></span>

<span data-ttu-id="af424-493">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="af424-493">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="af424-494">L'espressione regolare `Regex_slovakia_eu_passport_number` consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="af424-494">The regular expression  `Regex_slovakia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="af424-495">Una parola chiave da `Keywords_slovakia_eu_passport_number` viene trovato.</span><span class="sxs-lookup"><span data-stu-id="af424-495">A keyword from  `Keywords_slovakia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovakia_eu_passport_number" />
          <Match idRef="Keywords_slovakia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="af424-496">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="af424-496">Keywords</span></span>

<span data-ttu-id="af424-497">| |</span><span class="sxs-lookup"><span data-stu-id="af424-497"></span></span>
|<span data-ttu-id="af424-498">**Keywords_slovakia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="af424-498">**Keywords_slovakia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="af424-499">numero di passaporto</span><span class="sxs-lookup"><span data-stu-id="af424-499">passport number</span></span>  <br/> <span data-ttu-id="af424-500">numero di passaporto slovacco</span><span class="sxs-lookup"><span data-stu-id="af424-500">slovakian passport number</span></span>  <br/> <span data-ttu-id="af424-501">Passport non</span><span class="sxs-lookup"><span data-stu-id="af424-501">passport no</span></span>  <br/> <span data-ttu-id="af424-502">Číslo pasu</span><span class="sxs-lookup"><span data-stu-id="af424-502">číslo pasu</span></span>  <br/> |
   
## <a name="slovenia"></a><span data-ttu-id="af424-503">Slovenia</span><span class="sxs-lookup"><span data-stu-id="af424-503">Slovenia</span></span>

### <a name="format"></a><span data-ttu-id="af424-504">Formato</span><span class="sxs-lookup"><span data-stu-id="af424-504">Format</span></span>

<span data-ttu-id="af424-505">Due lettere seguite da sette cifre senza spazi o delimitatori</span><span class="sxs-lookup"><span data-stu-id="af424-505">Two letters followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="af424-506">Modello</span><span class="sxs-lookup"><span data-stu-id="af424-506">Pattern</span></span>

<span data-ttu-id="af424-507">Due lettere seguite da sette cifre:</span><span class="sxs-lookup"><span data-stu-id="af424-507">Two letters followed by seven digits:</span></span>
  
- <span data-ttu-id="af424-508">La lettera "P"</span><span class="sxs-lookup"><span data-stu-id="af424-508">The letter "P"</span></span>
    
- <span data-ttu-id="af424-509">Una lettera maiuscola</span><span class="sxs-lookup"><span data-stu-id="af424-509">One uppercase letter</span></span>
    
- <span data-ttu-id="af424-510">Sette cifre</span><span class="sxs-lookup"><span data-stu-id="af424-510">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="af424-511">Checksum</span><span class="sxs-lookup"><span data-stu-id="af424-511">Checksum</span></span>

<span data-ttu-id="af424-512">No</span><span class="sxs-lookup"><span data-stu-id="af424-512">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="af424-513">Definizione</span><span class="sxs-lookup"><span data-stu-id="af424-513">Definition</span></span>

<span data-ttu-id="af424-514">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="af424-514">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="af424-515">L'espressione regolare `Regex_slovenia_eu_passport_number` consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="af424-515">The regular expression  `Regex_slovenia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="af424-516">Una parola chiave da `Keywords_slovenia_eu_passport_number` viene trovato.</span><span class="sxs-lookup"><span data-stu-id="af424-516">A keyword from  `Keywords_slovenia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovenia_eu_passport_number" />
          <Match idRef="Keywords_slovenia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="af424-517">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="af424-517">Keywords</span></span>

<span data-ttu-id="af424-518">| |</span><span class="sxs-lookup"><span data-stu-id="af424-518"></span></span>
|<span data-ttu-id="af424-519">**Keywords_slovenia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="af424-519">**Keywords_slovenia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="af424-520">numero di passaporto</span><span class="sxs-lookup"><span data-stu-id="af424-520">passport number</span></span>  <br/> <span data-ttu-id="af424-521">numero di passaporto sloveno</span><span class="sxs-lookup"><span data-stu-id="af424-521">slovenian passport number</span></span>  <br/> <span data-ttu-id="af424-522">Passport non</span><span class="sxs-lookup"><span data-stu-id="af424-522">passport no</span></span>  <br/> <span data-ttu-id="af424-523">Številka potnega lista</span><span class="sxs-lookup"><span data-stu-id="af424-523">številka potnega lista</span></span>  <br/> |
   
## <a name="spain"></a><span data-ttu-id="af424-524">Spagna</span><span class="sxs-lookup"><span data-stu-id="af424-524">Spain</span></span>

### <a name="format"></a><span data-ttu-id="af424-525">Formato</span><span class="sxs-lookup"><span data-stu-id="af424-525">Format</span></span>

<span data-ttu-id="af424-526">Una combinazione di otto o nove caratteri di lettere e numeri senza spazi o delimitatori</span><span class="sxs-lookup"><span data-stu-id="af424-526">An eight- or nine-character combination of letters and numbers with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="af424-527">Modello</span><span class="sxs-lookup"><span data-stu-id="af424-527">Pattern</span></span>

<span data-ttu-id="af424-528">Una combinazione di otto o nove caratteri di numeri e lettere:</span><span class="sxs-lookup"><span data-stu-id="af424-528">An eight- or nine-character combination of letters and numbers:</span></span>
  
-  <span data-ttu-id="af424-529">Due cifre o lettere selezionate</span><span class="sxs-lookup"><span data-stu-id="af424-529">Two digits or letters</span></span> 
    
- <span data-ttu-id="af424-530">Una cifra o una lettera (facoltativo)</span><span class="sxs-lookup"><span data-stu-id="af424-530">One digit or letter (optional)</span></span>
    
- <span data-ttu-id="af424-531">Sei cifre</span><span class="sxs-lookup"><span data-stu-id="af424-531">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="af424-532">Checksum</span><span class="sxs-lookup"><span data-stu-id="af424-532">Checksum</span></span>

<span data-ttu-id="af424-533">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="af424-533">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="af424-534">Definizione</span><span class="sxs-lookup"><span data-stu-id="af424-534">Definition</span></span>

<span data-ttu-id="af424-535">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="af424-535">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="af424-536">L'espressione regolare `Regex_spain_eu_passport_number` consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="af424-536">The regular expression  `Regex_spain_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="af424-537">Una parola chiave da `Keywords_spain_eu_passport_number` viene trovato.</span><span class="sxs-lookup"><span data-stu-id="af424-537">A keyword from  `Keywords_spain_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_spain_eu_passport_number" />
          <Match idRef="Keywords_spain_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="af424-538">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="af424-538">Keywords</span></span>

<span data-ttu-id="af424-539">| |</span><span class="sxs-lookup"><span data-stu-id="af424-539"></span></span>
|<span data-ttu-id="af424-540">**Keywords_spain_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="af424-540">**Keywords_spain_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="af424-541">passport</span><span class="sxs-lookup"><span data-stu-id="af424-541">passport</span></span>  <br/> <span data-ttu-id="af424-542">passport Spagna</span><span class="sxs-lookup"><span data-stu-id="af424-542">spain passport</span></span>  <br/> <span data-ttu-id="af424-543">Rubrica di passaporto</span><span class="sxs-lookup"><span data-stu-id="af424-543">passport book</span></span>  <br/> <span data-ttu-id="af424-544">numero di passaporto</span><span class="sxs-lookup"><span data-stu-id="af424-544">passport number</span></span>  <br/> <span data-ttu-id="af424-545">Passport non</span><span class="sxs-lookup"><span data-stu-id="af424-545">passport no</span></span>  <br/> <span data-ttu-id="af424-546">libreta pasaporte</span><span class="sxs-lookup"><span data-stu-id="af424-546">libreta pasaporte</span></span>  <br/> <span data-ttu-id="af424-547">número pasaporte</span><span class="sxs-lookup"><span data-stu-id="af424-547">número pasaporte</span></span>  <br/> <span data-ttu-id="af424-548">España pasaporte</span><span class="sxs-lookup"><span data-stu-id="af424-548">españa pasaporte</span></span>  <br/> <span data-ttu-id="af424-549">pasaporte</span><span class="sxs-lookup"><span data-stu-id="af424-549">pasaporte</span></span>  <br/> |
   
## <a name="sweden"></a><span data-ttu-id="af424-550">Svezia</span><span class="sxs-lookup"><span data-stu-id="af424-550">Sweden</span></span>

<span data-ttu-id="af424-551">Per ulteriori informazioni, vedere la sezione "Numero di passaporto Svezia" in [cercare il quali i tipi di informazioni riservate](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="af424-551">For details, see the section "Sweden Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="uk"></a><span data-ttu-id="af424-552">REGNO UNITO</span><span class="sxs-lookup"><span data-stu-id="af424-552">UK</span></span>

<span data-ttu-id="af424-p103">Per ulteriori informazioni, vedere la sezione "US / numero di passaporto Regno Unito" in [cercare il quali i tipi di informazioni riservate](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="af424-p103">For details, see the section "U.S. / U.K. Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="af424-555">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="af424-555">See also</span></span>

[<span data-ttu-id="af424-556">Cosa individuano le tipologie di informazioni sensibili</span><span class="sxs-lookup"><span data-stu-id="af424-556">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)

