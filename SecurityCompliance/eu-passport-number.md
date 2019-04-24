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
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "32256824"
---
# <a name="eu-passport-number"></a><span data-ttu-id="a9f39-104">Numero di passaporto EU</span><span class="sxs-lookup"><span data-stu-id="a9f39-104">EU Passport Number</span></span>

<span data-ttu-id="a9f39-105">In questo argomento viene illustrato l'aspetto di un criterio di prevenzione della perdita di dati (DLP) quando viene rilevato il tipo di informazioni riservate del numero di passaporto dell'Unione europea.</span><span class="sxs-lookup"><span data-stu-id="a9f39-105">This topic shows what a data loss prevention (DLP) policy looks for when it detects the EU Passport Number sensitive information type.</span></span> <span data-ttu-id="a9f39-106">Questo tipo di informazioni riservate definisce modelli, parole chiave e altre evidenze diverse per ogni paese.</span><span class="sxs-lookup"><span data-stu-id="a9f39-106">This sensitive information type defines different patterns, keywords, and other evidence for each country.</span></span>
  
## <a name="austria"></a><span data-ttu-id="a9f39-107">Austria</span><span class="sxs-lookup"><span data-stu-id="a9f39-107">Austria</span></span>

### <a name="format"></a><span data-ttu-id="a9f39-108">Formato</span><span class="sxs-lookup"><span data-stu-id="a9f39-108">Format</span></span>

<span data-ttu-id="a9f39-109">Una lettera seguita da uno spazio facoltativo e sette cifre</span><span class="sxs-lookup"><span data-stu-id="a9f39-109">One letter followed by an optional space and seven digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="a9f39-110">Modello</span><span class="sxs-lookup"><span data-stu-id="a9f39-110">Pattern</span></span>

<span data-ttu-id="a9f39-111">Combinazione di una lettera, sette cifre e uno spazio:</span><span class="sxs-lookup"><span data-stu-id="a9f39-111">A combination of one letter, seven digits, and one space:</span></span>
  
- <span data-ttu-id="a9f39-112">Una lettera (senza distinzione tra maiuscole/minuscole)</span><span class="sxs-lookup"><span data-stu-id="a9f39-112">One letter (not case sensitive)</span></span>
    
- <span data-ttu-id="a9f39-113">Uno spazio (facoltativo)</span><span class="sxs-lookup"><span data-stu-id="a9f39-113">One space (optional)</span></span>
    
- <span data-ttu-id="a9f39-114">Sette cifre</span><span class="sxs-lookup"><span data-stu-id="a9f39-114">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="a9f39-115">Checksum</span><span class="sxs-lookup"><span data-stu-id="a9f39-115">Checksum</span></span>

<span data-ttu-id="a9f39-116">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="a9f39-116">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="a9f39-117">Definizione</span><span class="sxs-lookup"><span data-stu-id="a9f39-117">Definition</span></span>

<span data-ttu-id="a9f39-118">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="a9f39-118">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="a9f39-119">L'espressione `Regex_austria_eu_passport_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="a9f39-119">The regular expression  `Regex_austria_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="a9f39-120">Viene trovata una `Keywords_austria_eu_passport_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="a9f39-120">A keyword from  `Keywords_austria_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_austria_eu_passport_number" />
          <Match idRef="Keywords_austria_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a9f39-121">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="a9f39-121">Keywords</span></span>

<span data-ttu-id="a9f39-122">| |</span><span class="sxs-lookup"><span data-stu-id="a9f39-122"></span></span>
|<span data-ttu-id="a9f39-123">**Keywords_austria_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="a9f39-123">**Keywords_austria_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="a9f39-124">passport number</span><span class="sxs-lookup"><span data-stu-id="a9f39-124">passport number</span></span>  <br/> <span data-ttu-id="a9f39-125">numero di passaporto austriaco</span><span class="sxs-lookup"><span data-stu-id="a9f39-125">austrian passport number</span></span>  <br/> <span data-ttu-id="a9f39-126">Passport No</span><span class="sxs-lookup"><span data-stu-id="a9f39-126">passport no</span></span>  <br/> <span data-ttu-id="a9f39-127">Reisepass</span><span class="sxs-lookup"><span data-stu-id="a9f39-127">reisepass</span></span>  <br/> <span data-ttu-id="a9f39-128">Österreichisch Reisepass</span><span class="sxs-lookup"><span data-stu-id="a9f39-128">österreichisch reisepass</span></span>  <br/> |
   
## <a name="belgium"></a><span data-ttu-id="a9f39-129">Belgio</span><span class="sxs-lookup"><span data-stu-id="a9f39-129">Belgium</span></span>

### <a name="format"></a><span data-ttu-id="a9f39-130">Formato</span><span class="sxs-lookup"><span data-stu-id="a9f39-130">Format</span></span>

<span data-ttu-id="a9f39-131">Due lettere seguite da sei cifre senza spazi o delimitatori</span><span class="sxs-lookup"><span data-stu-id="a9f39-131">Two letters followed by six digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="a9f39-132">Modello</span><span class="sxs-lookup"><span data-stu-id="a9f39-132">Pattern</span></span>

<span data-ttu-id="a9f39-133">Due lettere e seguite da sei cifre</span><span class="sxs-lookup"><span data-stu-id="a9f39-133">Two letters and followed by six digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="a9f39-134">Checksum</span><span class="sxs-lookup"><span data-stu-id="a9f39-134">Checksum</span></span>

<span data-ttu-id="a9f39-135">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="a9f39-135">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="a9f39-136">Definizione</span><span class="sxs-lookup"><span data-stu-id="a9f39-136">Definition</span></span>

<span data-ttu-id="a9f39-137">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="a9f39-137">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="a9f39-138">L'espressione `Regex_belgium_eu_passport_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="a9f39-138">The regular expression  `Regex_belgium_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="a9f39-139">Viene trovata una `Keywords_belgium_eu_passport_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="a9f39-139">A keyword from  `Keywords_belgium_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_belgium__eu_passport_number" />
          <Match idRef="Keywords_belgium_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a9f39-140">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="a9f39-140">Keywords</span></span>

<span data-ttu-id="a9f39-141">| |</span><span class="sxs-lookup"><span data-stu-id="a9f39-141"></span></span>
|<span data-ttu-id="a9f39-142">**Keywords_belgium_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="a9f39-142">**Keywords_belgium_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="a9f39-143">passport number</span><span class="sxs-lookup"><span data-stu-id="a9f39-143">passport number</span></span>  <br/> <span data-ttu-id="a9f39-144">numero di passaporto belga</span><span class="sxs-lookup"><span data-stu-id="a9f39-144">belgian passport number</span></span>  <br/> <span data-ttu-id="a9f39-145">Passport No</span><span class="sxs-lookup"><span data-stu-id="a9f39-145">passport no</span></span>  <br/> <span data-ttu-id="a9f39-146">PASPOORT</span><span class="sxs-lookup"><span data-stu-id="a9f39-146">paspoort</span></span>  <br/> <span data-ttu-id="a9f39-147">paspoortnummer</span><span class="sxs-lookup"><span data-stu-id="a9f39-147">paspoortnummer</span></span>  <br/> <span data-ttu-id="a9f39-148">Reisepass kein</span><span class="sxs-lookup"><span data-stu-id="a9f39-148">reisepass kein</span></span>  <br/> <span data-ttu-id="a9f39-149">Reisepass</span><span class="sxs-lookup"><span data-stu-id="a9f39-149">reisepass</span></span>  <br/> |
   
## <a name="bulgaria"></a><span data-ttu-id="a9f39-150">Bulgaria</span><span class="sxs-lookup"><span data-stu-id="a9f39-150">Bulgaria</span></span>

### <a name="format"></a><span data-ttu-id="a9f39-151">Formato</span><span class="sxs-lookup"><span data-stu-id="a9f39-151">Format</span></span>

<span data-ttu-id="a9f39-152">Nove cifre senza spazi e delimitatori</span><span class="sxs-lookup"><span data-stu-id="a9f39-152">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="a9f39-153">Modello</span><span class="sxs-lookup"><span data-stu-id="a9f39-153">Pattern</span></span>

 <span data-ttu-id="a9f39-154">9 cifre</span><span class="sxs-lookup"><span data-stu-id="a9f39-154">Nine digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="a9f39-155">Checksum</span><span class="sxs-lookup"><span data-stu-id="a9f39-155">Checksum</span></span>

<span data-ttu-id="a9f39-156">No</span><span class="sxs-lookup"><span data-stu-id="a9f39-156">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="a9f39-157">Definizione</span><span class="sxs-lookup"><span data-stu-id="a9f39-157">Definition</span></span>

<span data-ttu-id="a9f39-158">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="a9f39-158">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="a9f39-159">L'espressione `Regex_bulgaria_eu_passport_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="a9f39-159">The regular expression  `Regex_bulgaria_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="a9f39-160">Viene trovata una `Keywords_bulgaria_eu_passport_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="a9f39-160">A keyword from  `Keywords_bulgaria_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_bulgaria_eu_passport_number" />
          <Match idRef="Keywords_bulgaria_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a9f39-161">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="a9f39-161">Keywords</span></span>

<span data-ttu-id="a9f39-162">| |</span><span class="sxs-lookup"><span data-stu-id="a9f39-162"></span></span>
|<span data-ttu-id="a9f39-163">**Keywords_bulgaria_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="a9f39-163">**Keywords_bulgaria_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="a9f39-164">passport number</span><span class="sxs-lookup"><span data-stu-id="a9f39-164">passport number</span></span>  <br/> <span data-ttu-id="a9f39-165">numero di passaporto bulgaro</span><span class="sxs-lookup"><span data-stu-id="a9f39-165">bulgarian passport number</span></span>  <br/> <span data-ttu-id="a9f39-166">Passport No</span><span class="sxs-lookup"><span data-stu-id="a9f39-166">passport no</span></span>  <br/> <span data-ttu-id="a9f39-167">Номер на паспорта</span><span class="sxs-lookup"><span data-stu-id="a9f39-167">номер на паспорта</span></span>  <br/> |
   
## <a name="croatia"></a><span data-ttu-id="a9f39-168">Croazia</span><span class="sxs-lookup"><span data-stu-id="a9f39-168">Croatia</span></span>

### <a name="format"></a><span data-ttu-id="a9f39-169">Formato</span><span class="sxs-lookup"><span data-stu-id="a9f39-169">Format</span></span>

<span data-ttu-id="a9f39-170">Nove cifre senza spazi e delimitatori</span><span class="sxs-lookup"><span data-stu-id="a9f39-170">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="a9f39-171">Modello</span><span class="sxs-lookup"><span data-stu-id="a9f39-171">Pattern</span></span>

 <span data-ttu-id="a9f39-172">9 cifre</span><span class="sxs-lookup"><span data-stu-id="a9f39-172">Nine digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="a9f39-173">Checksum</span><span class="sxs-lookup"><span data-stu-id="a9f39-173">Checksum</span></span>

<span data-ttu-id="a9f39-174">No</span><span class="sxs-lookup"><span data-stu-id="a9f39-174">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="a9f39-175">Definizione</span><span class="sxs-lookup"><span data-stu-id="a9f39-175">Definition</span></span>

<span data-ttu-id="a9f39-176">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="a9f39-176">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="a9f39-177">L'espressione `Regex_croatia_eu_passport_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="a9f39-177">The regular expression  `Regex_croatia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="a9f39-178">Viene trovata una `Keywords_croatia_eu_passport_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="a9f39-178">A keyword from  `Keywords_croatia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_croatia_eu_passport_number" />
          <Match idRef="Keywords_croatia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a9f39-179">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="a9f39-179">Keywords</span></span>

<span data-ttu-id="a9f39-180">| |</span><span class="sxs-lookup"><span data-stu-id="a9f39-180"></span></span>
|<span data-ttu-id="a9f39-181">**Keywords_croatia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="a9f39-181">**Keywords_croatia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="a9f39-182">passport number</span><span class="sxs-lookup"><span data-stu-id="a9f39-182">passport number</span></span>  <br/> <span data-ttu-id="a9f39-183">numero di passaporto croato</span><span class="sxs-lookup"><span data-stu-id="a9f39-183">croatian passport number</span></span>  <br/> <span data-ttu-id="a9f39-184">Passport No</span><span class="sxs-lookup"><span data-stu-id="a9f39-184">passport no</span></span>  <br/> <span data-ttu-id="a9f39-185">broj putovnice</span><span class="sxs-lookup"><span data-stu-id="a9f39-185">broj putovnice</span></span>  <br/> |
   
## <a name="cyprus"></a><span data-ttu-id="a9f39-186">Cipro</span><span class="sxs-lookup"><span data-stu-id="a9f39-186">Cyprus</span></span>

### <a name="format"></a><span data-ttu-id="a9f39-187">Formato</span><span class="sxs-lookup"><span data-stu-id="a9f39-187">Format</span></span>

<span data-ttu-id="a9f39-188">Una lettera seguita da 6-8 cifre senza spazi o delimitatori</span><span class="sxs-lookup"><span data-stu-id="a9f39-188">One letter followed by 6-8 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="a9f39-189">Modello</span><span class="sxs-lookup"><span data-stu-id="a9f39-189">Pattern</span></span>

<span data-ttu-id="a9f39-190">Una lettera seguita da sei a otto cifre</span><span class="sxs-lookup"><span data-stu-id="a9f39-190">One letter followed by six to eight digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="a9f39-191">Checksum</span><span class="sxs-lookup"><span data-stu-id="a9f39-191">Checksum</span></span>

<span data-ttu-id="a9f39-192">No</span><span class="sxs-lookup"><span data-stu-id="a9f39-192">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="a9f39-193">Definizione</span><span class="sxs-lookup"><span data-stu-id="a9f39-193">Definition</span></span>

<span data-ttu-id="a9f39-194">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="a9f39-194">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="a9f39-195">L'espressione `Regex_cyprus_eu_passport_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="a9f39-195">The regular expression  `Regex_cyprus_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="a9f39-196">Viene trovata una `Keywords_cyprus_eu_passport_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="a9f39-196">A keyword from  `Keywords_cyprus_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_cyprus_eu_passport_number" />
          <Match idRef="Keywords_cyprus_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a9f39-197">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="a9f39-197">Keywords</span></span>

<span data-ttu-id="a9f39-198">| |</span><span class="sxs-lookup"><span data-stu-id="a9f39-198"></span></span>
|<span data-ttu-id="a9f39-199">**Keywords_cyprus_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="a9f39-199">**Keywords_cyprus_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="a9f39-200">passport number</span><span class="sxs-lookup"><span data-stu-id="a9f39-200">passport number</span></span>  <br/> <span data-ttu-id="a9f39-201">numero di passaporto di Cipro</span><span class="sxs-lookup"><span data-stu-id="a9f39-201">cyprus passport number</span></span>  <br/> <span data-ttu-id="a9f39-202">Passport No</span><span class="sxs-lookup"><span data-stu-id="a9f39-202">passport no</span></span>  <br/> <span data-ttu-id="a9f39-203">αριθμό διαβατηρίου</span><span class="sxs-lookup"><span data-stu-id="a9f39-203">αριθμό διαβατηρίου</span></span>  <br/> |
   
## <a name="czech-republic"></a><span data-ttu-id="a9f39-204">Repubblica Ceca</span><span class="sxs-lookup"><span data-stu-id="a9f39-204">Czech Republic</span></span>

### <a name="format"></a><span data-ttu-id="a9f39-205">Formato</span><span class="sxs-lookup"><span data-stu-id="a9f39-205">Format</span></span>

<span data-ttu-id="a9f39-206">Otto cifre senza spazi o delimitatori</span><span class="sxs-lookup"><span data-stu-id="a9f39-206">Eight digits without spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="a9f39-207">Modello</span><span class="sxs-lookup"><span data-stu-id="a9f39-207">Pattern</span></span>

<span data-ttu-id="a9f39-208">Otto cifre senza spazi o delimitatori</span><span class="sxs-lookup"><span data-stu-id="a9f39-208">Eight digits without spaces or delimiters</span></span>
  
### <a name="checksum"></a><span data-ttu-id="a9f39-209">Checksum</span><span class="sxs-lookup"><span data-stu-id="a9f39-209">Checksum</span></span>

<span data-ttu-id="a9f39-210">No</span><span class="sxs-lookup"><span data-stu-id="a9f39-210">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="a9f39-211">Definizione</span><span class="sxs-lookup"><span data-stu-id="a9f39-211">Definition</span></span>

<span data-ttu-id="a9f39-212">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="a9f39-212">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="a9f39-213">L'espressione `Regex_czech_republic_eu_passport_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="a9f39-213">The regular expression  `Regex_czech_republic_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="a9f39-214">Viene trovata una `Keywords_czech_republic_eu_passport_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="a9f39-214">A keyword from  `Keywords_czech_republic_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_czech_republic_eu_passport_number" />
          <Match idRef="Keywords_czech_republic_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a9f39-215">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="a9f39-215">Keywords</span></span>

<span data-ttu-id="a9f39-216">| |</span><span class="sxs-lookup"><span data-stu-id="a9f39-216"></span></span>
|<span data-ttu-id="a9f39-217">**Keywords_czech_republic_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="a9f39-217">**Keywords_czech_republic_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="a9f39-218">passport number</span><span class="sxs-lookup"><span data-stu-id="a9f39-218">passport number</span></span>  <br/> <span data-ttu-id="a9f39-219">numero di passaporto ceco</span><span class="sxs-lookup"><span data-stu-id="a9f39-219">czech passport number</span></span>  <br/> <span data-ttu-id="a9f39-220">Passport No</span><span class="sxs-lookup"><span data-stu-id="a9f39-220">passport no</span></span>  <br/> <span data-ttu-id="a9f39-221">Cestovní pas</span><span class="sxs-lookup"><span data-stu-id="a9f39-221">cestovní pas</span></span>  <br/> <span data-ttu-id="a9f39-222">pas</span><span class="sxs-lookup"><span data-stu-id="a9f39-222">pas</span></span>  <br/> |
   
## <a name="denmark"></a><span data-ttu-id="a9f39-223">Danimarca</span><span class="sxs-lookup"><span data-stu-id="a9f39-223">Denmark</span></span>

### <a name="format"></a><span data-ttu-id="a9f39-224">Formato</span><span class="sxs-lookup"><span data-stu-id="a9f39-224">Format</span></span>

<span data-ttu-id="a9f39-225">Nove cifre senza spazi e delimitatori</span><span class="sxs-lookup"><span data-stu-id="a9f39-225">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="a9f39-226">Modello</span><span class="sxs-lookup"><span data-stu-id="a9f39-226">Pattern</span></span>

 <span data-ttu-id="a9f39-227">9 cifre</span><span class="sxs-lookup"><span data-stu-id="a9f39-227">Nine digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="a9f39-228">Checksum</span><span class="sxs-lookup"><span data-stu-id="a9f39-228">Checksum</span></span>

<span data-ttu-id="a9f39-229">No</span><span class="sxs-lookup"><span data-stu-id="a9f39-229">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="a9f39-230">Definizione</span><span class="sxs-lookup"><span data-stu-id="a9f39-230">Definition</span></span>

<span data-ttu-id="a9f39-231">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="a9f39-231">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="a9f39-232">L'espressione `Regex_denmark_eu_passport_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="a9f39-232">The regular expression  `Regex_denmark_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="a9f39-233">Viene trovata una `Keywords_denmark_eu_passport_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="a9f39-233">A keyword from  `Keywords_denmark_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_denmark_eu_passport_number" />
          <Match idRef="Keywords_denmark_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a9f39-234">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="a9f39-234">Keywords</span></span>

<span data-ttu-id="a9f39-235">| |</span><span class="sxs-lookup"><span data-stu-id="a9f39-235"></span></span>
|<span data-ttu-id="a9f39-236">**Keywords_denmark_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="a9f39-236">**Keywords_denmark_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="a9f39-237">passport number</span><span class="sxs-lookup"><span data-stu-id="a9f39-237">passport number</span></span>  <br/> <span data-ttu-id="a9f39-238">numero di passaporto danese</span><span class="sxs-lookup"><span data-stu-id="a9f39-238">danish passport number</span></span>  <br/> <span data-ttu-id="a9f39-239">Passport No</span><span class="sxs-lookup"><span data-stu-id="a9f39-239">passport no</span></span>  <br/> <span data-ttu-id="a9f39-240">pas</span><span class="sxs-lookup"><span data-stu-id="a9f39-240">pas</span></span>  <br/> <span data-ttu-id="a9f39-241">Pasnummer</span><span class="sxs-lookup"><span data-stu-id="a9f39-241">pasnummer</span></span>  <br/> |
   
## <a name="estonia"></a><span data-ttu-id="a9f39-242">Estonia</span><span class="sxs-lookup"><span data-stu-id="a9f39-242">Estonia</span></span>

### <a name="format"></a><span data-ttu-id="a9f39-243">Formato</span><span class="sxs-lookup"><span data-stu-id="a9f39-243">Format</span></span>

<span data-ttu-id="a9f39-244">Una lettera seguita da sette cifre senza spazi o delimitatori</span><span class="sxs-lookup"><span data-stu-id="a9f39-244">One letter followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="a9f39-245">Modello</span><span class="sxs-lookup"><span data-stu-id="a9f39-245">Pattern</span></span>

<span data-ttu-id="a9f39-246">Una lettera seguita da sette cifre</span><span class="sxs-lookup"><span data-stu-id="a9f39-246">One letter followed by seven digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="a9f39-247">Checksum</span><span class="sxs-lookup"><span data-stu-id="a9f39-247">Checksum</span></span>

<span data-ttu-id="a9f39-248">No</span><span class="sxs-lookup"><span data-stu-id="a9f39-248">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="a9f39-249">Definizione</span><span class="sxs-lookup"><span data-stu-id="a9f39-249">Definition</span></span>

<span data-ttu-id="a9f39-250">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="a9f39-250">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="a9f39-251">L'espressione `Regex_estonia_eu_passport_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="a9f39-251">The regular expression  `Regex_estonia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="a9f39-252">Viene trovata una `Keywords_estonia_eu_passport_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="a9f39-252">A keyword from  `Keywords_estonia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_estonia_eu_passport_number" />
          <Match idRef="Keywords_estonia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a9f39-253">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="a9f39-253">Keywords</span></span>

<span data-ttu-id="a9f39-254">| |</span><span class="sxs-lookup"><span data-stu-id="a9f39-254"></span></span>
|<span data-ttu-id="a9f39-255">**Keywords_estonia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="a9f39-255">**Keywords_estonia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="a9f39-256">passport number</span><span class="sxs-lookup"><span data-stu-id="a9f39-256">passport number</span></span>  <br/> <span data-ttu-id="a9f39-257">numero di passaporto estone</span><span class="sxs-lookup"><span data-stu-id="a9f39-257">estonian passport number</span></span>  <br/> <span data-ttu-id="a9f39-258">Passport No</span><span class="sxs-lookup"><span data-stu-id="a9f39-258">passport no</span></span>  <br/> <span data-ttu-id="a9f39-259">passaggio kodaniku Eesti</span><span class="sxs-lookup"><span data-stu-id="a9f39-259">eesti kodaniku pass</span></span>  <br/> |
   
## <a name="finland"></a><span data-ttu-id="a9f39-260">Finlandia</span><span class="sxs-lookup"><span data-stu-id="a9f39-260">Finland</span></span>

<span data-ttu-id="a9f39-261">Per informazioni dettagliate, vedere la sezione "Finlandia Passport Number" in [che cosa cercano i tipi di informazioni riservate](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="a9f39-261">For details, see the section "Finland Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="france"></a><span data-ttu-id="a9f39-262">Francia</span><span class="sxs-lookup"><span data-stu-id="a9f39-262">France</span></span>

<span data-ttu-id="a9f39-263">Per informazioni dettagliate, vedere la sezione "Francia Passport Number" in [che cosa cercano i tipi di informazioni riservate](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="a9f39-263">For details, see the section "France Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="germany"></a><span data-ttu-id="a9f39-264">Germania</span><span class="sxs-lookup"><span data-stu-id="a9f39-264">Germany</span></span>

<span data-ttu-id="a9f39-265">Per informazioni dettagliate, vedere la sezione "Germania Passport Number" in [che cosa cercano i tipi di informazioni riservate](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="a9f39-265">For details, see the section "Germany Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="greece"></a><span data-ttu-id="a9f39-266">Grecia</span><span class="sxs-lookup"><span data-stu-id="a9f39-266">Greece</span></span>

### <a name="format"></a><span data-ttu-id="a9f39-267">Formato</span><span class="sxs-lookup"><span data-stu-id="a9f39-267">Format</span></span>

<span data-ttu-id="a9f39-268">Due lettere seguite da sette cifre senza spazi o delimitatori</span><span class="sxs-lookup"><span data-stu-id="a9f39-268">Two letters followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="a9f39-269">Modello</span><span class="sxs-lookup"><span data-stu-id="a9f39-269">Pattern</span></span>

<span data-ttu-id="a9f39-270">Due lettere seguite da 7 cifre</span><span class="sxs-lookup"><span data-stu-id="a9f39-270">Two letters followed by seven digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="a9f39-271">Checksum</span><span class="sxs-lookup"><span data-stu-id="a9f39-271">Checksum</span></span>

<span data-ttu-id="a9f39-272">No</span><span class="sxs-lookup"><span data-stu-id="a9f39-272">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="a9f39-273">Definizione</span><span class="sxs-lookup"><span data-stu-id="a9f39-273">Definition</span></span>

<span data-ttu-id="a9f39-274">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="a9f39-274">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="a9f39-275">L'espressione `Regex_greece_eu_passport_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="a9f39-275">The regular expression  `Regex_greece_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="a9f39-276">Viene trovata una `Keywords_greece_eu_passport_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="a9f39-276">A keyword from  `Keywords_greece_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_greece_eu_passport_number" />
          <Match idRef="Keywords_greece_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a9f39-277">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="a9f39-277">Keywords</span></span>

<span data-ttu-id="a9f39-278">| |</span><span class="sxs-lookup"><span data-stu-id="a9f39-278"></span></span>
|<span data-ttu-id="a9f39-279">**Keywords_greece_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="a9f39-279">**Keywords_greece_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="a9f39-280">passport number</span><span class="sxs-lookup"><span data-stu-id="a9f39-280">passport number</span></span>  <br/> <span data-ttu-id="a9f39-281">numero di passaporto greco</span><span class="sxs-lookup"><span data-stu-id="a9f39-281">greek passport number</span></span>  <br/> <span data-ttu-id="a9f39-282">Passport No</span><span class="sxs-lookup"><span data-stu-id="a9f39-282">passport no</span></span>  <br/> <span data-ttu-id="a9f39-283">διαβατηριο</span><span class="sxs-lookup"><span data-stu-id="a9f39-283">διαβατηριο</span></span>  <br/> |
   
## <a name="hungary"></a><span data-ttu-id="a9f39-284">Ungheria</span><span class="sxs-lookup"><span data-stu-id="a9f39-284">Hungary</span></span>

### <a name="format"></a><span data-ttu-id="a9f39-285">Formato</span><span class="sxs-lookup"><span data-stu-id="a9f39-285">Format</span></span>

<span data-ttu-id="a9f39-286">Due lettere seguite da sei o sette cifre senza spazi o delimitatori</span><span class="sxs-lookup"><span data-stu-id="a9f39-286">Two letters followed by six or seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="a9f39-287">Modello</span><span class="sxs-lookup"><span data-stu-id="a9f39-287">Pattern</span></span>

<span data-ttu-id="a9f39-288">Due lettere seguite da sei o sette cifre</span><span class="sxs-lookup"><span data-stu-id="a9f39-288">Two letters followed by six or seven digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="a9f39-289">Checksum</span><span class="sxs-lookup"><span data-stu-id="a9f39-289">Checksum</span></span>

<span data-ttu-id="a9f39-290">No</span><span class="sxs-lookup"><span data-stu-id="a9f39-290">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="a9f39-291">Definizione</span><span class="sxs-lookup"><span data-stu-id="a9f39-291">Definition</span></span>

<span data-ttu-id="a9f39-292">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="a9f39-292">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="a9f39-293">L'espressione `Regex_hungary_eu_passport_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="a9f39-293">The regular expression  `Regex_hungary_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="a9f39-294">Viene trovata una `Keywords_hungary_eu_passport_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="a9f39-294">A keyword from  `Keywords_hungary_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_hungary_eu_passport_number" />
          <Match idRef="Keywords_hungary_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a9f39-295">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="a9f39-295">Keywords</span></span>

<span data-ttu-id="a9f39-296">| |</span><span class="sxs-lookup"><span data-stu-id="a9f39-296"></span></span>
|<span data-ttu-id="a9f39-297">**Keywords_hungary_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="a9f39-297">**Keywords_hungary_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="a9f39-298">passport number</span><span class="sxs-lookup"><span data-stu-id="a9f39-298">passport number</span></span>  <br/> <span data-ttu-id="a9f39-299">numero di passaporto ungherese</span><span class="sxs-lookup"><span data-stu-id="a9f39-299">hungarian passport number</span></span>  <br/> <span data-ttu-id="a9f39-300">Passport No</span><span class="sxs-lookup"><span data-stu-id="a9f39-300">passport no</span></span>  <br/> <span data-ttu-id="a9f39-301">útlevél száma</span><span class="sxs-lookup"><span data-stu-id="a9f39-301">útlevél száma</span></span>  <br/> |
   
## <a name="ireland"></a><span data-ttu-id="a9f39-302">Irlanda</span><span class="sxs-lookup"><span data-stu-id="a9f39-302">Ireland</span></span>

### <a name="format"></a><span data-ttu-id="a9f39-303">Formato</span><span class="sxs-lookup"><span data-stu-id="a9f39-303">Format</span></span>

<span data-ttu-id="a9f39-304">Due lettere o cifre seguite da sette cifre senza spazi o delimitatori</span><span class="sxs-lookup"><span data-stu-id="a9f39-304">Two letters or digits followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="a9f39-305">Modello</span><span class="sxs-lookup"><span data-stu-id="a9f39-305">Pattern</span></span>

<span data-ttu-id="a9f39-306">Due lettere o cifre seguite da sette cifre:</span><span class="sxs-lookup"><span data-stu-id="a9f39-306">Two letters or digits followed by seven digits:</span></span>
  
- <span data-ttu-id="a9f39-307">Due cifre o lettere (senza distinzione tra maiuscole/minuscole)</span><span class="sxs-lookup"><span data-stu-id="a9f39-307">Two digits or letters (not case sensitive)</span></span>
    
- <span data-ttu-id="a9f39-308">Sette cifre</span><span class="sxs-lookup"><span data-stu-id="a9f39-308">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="a9f39-309">Checksum</span><span class="sxs-lookup"><span data-stu-id="a9f39-309">Checksum</span></span>

<span data-ttu-id="a9f39-310">No</span><span class="sxs-lookup"><span data-stu-id="a9f39-310">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="a9f39-311">Definizione</span><span class="sxs-lookup"><span data-stu-id="a9f39-311">Definition</span></span>

<span data-ttu-id="a9f39-312">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="a9f39-312">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="a9f39-313">L'espressione `Regex_ireland_eu_passport_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="a9f39-313">The regular expression  `Regex_ireland_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="a9f39-314">Viene trovata una `Keywords_ireland_eu_passport_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="a9f39-314">A keyword from  `Keywords_ireland_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_ireland_eu_passport_number" />
          <Match idRef="Keywords_ireland_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a9f39-315">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="a9f39-315">Keywords</span></span>

<span data-ttu-id="a9f39-316">| |</span><span class="sxs-lookup"><span data-stu-id="a9f39-316"></span></span>
|<span data-ttu-id="a9f39-317">**Keywords_ireland_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="a9f39-317">**Keywords_ireland_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="a9f39-318">passport number</span><span class="sxs-lookup"><span data-stu-id="a9f39-318">passport number</span></span>  <br/> <span data-ttu-id="a9f39-319">numero di passaporto irlandese</span><span class="sxs-lookup"><span data-stu-id="a9f39-319">irish passport number</span></span>  <br/> <span data-ttu-id="a9f39-320">Passport No</span><span class="sxs-lookup"><span data-stu-id="a9f39-320">passport no</span></span>  <br/> <span data-ttu-id="a9f39-321">pas</span><span class="sxs-lookup"><span data-stu-id="a9f39-321">pas</span></span>  <br/> <span data-ttu-id="a9f39-322">passaporto</span><span class="sxs-lookup"><span data-stu-id="a9f39-322">passport</span></span>  <br/> <span data-ttu-id="a9f39-323">Passeport</span><span class="sxs-lookup"><span data-stu-id="a9f39-323">passeport</span></span>  <br/> <span data-ttu-id="a9f39-324">numero Passeport</span><span class="sxs-lookup"><span data-stu-id="a9f39-324">passeport numero</span></span>  <br/> |
   
## <a name="italy"></a><span data-ttu-id="a9f39-325">Italia</span><span class="sxs-lookup"><span data-stu-id="a9f39-325">Italy</span></span>

### <a name="format"></a><span data-ttu-id="a9f39-326">Formato</span><span class="sxs-lookup"><span data-stu-id="a9f39-326">Format</span></span>

<span data-ttu-id="a9f39-327">Due lettere o cifre seguite da sette cifre senza spazi o delimitatori</span><span class="sxs-lookup"><span data-stu-id="a9f39-327">Two letters or digits followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="a9f39-328">Modello</span><span class="sxs-lookup"><span data-stu-id="a9f39-328">Pattern</span></span>

<span data-ttu-id="a9f39-329">Due lettere o cifre seguite da sette cifre:</span><span class="sxs-lookup"><span data-stu-id="a9f39-329">Two letters or digits followed by seven digits:</span></span>
  
- <span data-ttu-id="a9f39-330">Due cifre o lettere (senza distinzione tra maiuscole/minuscole)</span><span class="sxs-lookup"><span data-stu-id="a9f39-330">Two digits or letters (not case sensitive)</span></span>
    
- <span data-ttu-id="a9f39-331">Sette cifre</span><span class="sxs-lookup"><span data-stu-id="a9f39-331">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="a9f39-332">Checksum</span><span class="sxs-lookup"><span data-stu-id="a9f39-332">Checksum</span></span>

<span data-ttu-id="a9f39-333">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="a9f39-333">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="a9f39-334">Definizione</span><span class="sxs-lookup"><span data-stu-id="a9f39-334">Definition</span></span>

<span data-ttu-id="a9f39-335">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="a9f39-335">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="a9f39-336">L'espressione `Regex_italy_eu_passport_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="a9f39-336">The regular expression  `Regex_italy_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="a9f39-337">Viene trovata una `Keywords_italy_eu_passport_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="a9f39-337">A keyword from  `Keywords_italy_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_italy_eu_passport_number" />
          <Match idRef="Keywords_italy_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a9f39-338">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="a9f39-338">Keywords</span></span>

<span data-ttu-id="a9f39-339">| |</span><span class="sxs-lookup"><span data-stu-id="a9f39-339"></span></span>
|<span data-ttu-id="a9f39-340">**Keywords_italy_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="a9f39-340">**Keywords_italy_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="a9f39-341">numero di passaporto italiano</span><span class="sxs-lookup"><span data-stu-id="a9f39-341">italian passport number</span></span>  <br/> <span data-ttu-id="a9f39-342">Repubblica italiana passaporto</span><span class="sxs-lookup"><span data-stu-id="a9f39-342">repubblica italiana passaporto</span></span>  <br/> <span data-ttu-id="a9f39-343">passaporto</span><span class="sxs-lookup"><span data-stu-id="a9f39-343">passaporto</span></span>  <br/> <span data-ttu-id="a9f39-344">passaporto italiana</span><span class="sxs-lookup"><span data-stu-id="a9f39-344">passaporto italiana</span></span>  <br/> <span data-ttu-id="a9f39-345">passport number</span><span class="sxs-lookup"><span data-stu-id="a9f39-345">passport number</span></span>  <br/> <span data-ttu-id="a9f39-346">italiana passaporto numero</span><span class="sxs-lookup"><span data-stu-id="a9f39-346">italiana passaporto numero</span></span>  <br/> <span data-ttu-id="a9f39-347">Numero passaporto</span><span class="sxs-lookup"><span data-stu-id="a9f39-347">passaporto numero</span></span>  <br/> <span data-ttu-id="a9f39-348">numéro Passeport Italien</span><span class="sxs-lookup"><span data-stu-id="a9f39-348">numéro passeport italien</span></span>  <br/> <span data-ttu-id="a9f39-349">numéro Passeport</span><span class="sxs-lookup"><span data-stu-id="a9f39-349">numéro passeport</span></span>  <br/> |
   
## <a name="latvia"></a><span data-ttu-id="a9f39-350">Lettonia</span><span class="sxs-lookup"><span data-stu-id="a9f39-350">Latvia</span></span>

### <a name="format"></a><span data-ttu-id="a9f39-351">Formato</span><span class="sxs-lookup"><span data-stu-id="a9f39-351">Format</span></span>

<span data-ttu-id="a9f39-352">Due lettere o cifre seguite da sette cifre senza spazi o delimitatori</span><span class="sxs-lookup"><span data-stu-id="a9f39-352">Two letters or digits followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="a9f39-353">Modello</span><span class="sxs-lookup"><span data-stu-id="a9f39-353">Pattern</span></span>

<span data-ttu-id="a9f39-354">Due lettere o cifre seguite da sette cifre:</span><span class="sxs-lookup"><span data-stu-id="a9f39-354">Two letters or digits followed by seven digits:</span></span>
  
- <span data-ttu-id="a9f39-355">Due cifre o lettere (senza distinzione tra maiuscole/minuscole)</span><span class="sxs-lookup"><span data-stu-id="a9f39-355">Two digits or letters (not case sensitive)</span></span>
    
- <span data-ttu-id="a9f39-356">Sette cifre</span><span class="sxs-lookup"><span data-stu-id="a9f39-356">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="a9f39-357">Checksum</span><span class="sxs-lookup"><span data-stu-id="a9f39-357">Checksum</span></span>

<span data-ttu-id="a9f39-358">No</span><span class="sxs-lookup"><span data-stu-id="a9f39-358">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="a9f39-359">Definizione</span><span class="sxs-lookup"><span data-stu-id="a9f39-359">Definition</span></span>

<span data-ttu-id="a9f39-360">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="a9f39-360">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="a9f39-361">L'espressione `Regex_latvia_eu_passport_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="a9f39-361">The regular expression  `Regex_latvia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="a9f39-362">Viene trovata una `Keywords_latvia_eu_passport_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="a9f39-362">A keyword from  `Keywords_latvia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_latvia_eu_passport_number" />
          <Match idRef="Keywords_latvia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a9f39-363">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="a9f39-363">Keywords</span></span>

<span data-ttu-id="a9f39-364">| |</span><span class="sxs-lookup"><span data-stu-id="a9f39-364"></span></span>
|<span data-ttu-id="a9f39-365">**Keywords_latvia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="a9f39-365">**Keywords_latvia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="a9f39-366">passport number</span><span class="sxs-lookup"><span data-stu-id="a9f39-366">passport number</span></span>  <br/> <span data-ttu-id="a9f39-367">numero di passaporto lettone</span><span class="sxs-lookup"><span data-stu-id="a9f39-367">latvian passport number</span></span>  <br/> <span data-ttu-id="a9f39-368">Passport No</span><span class="sxs-lookup"><span data-stu-id="a9f39-368">passport no</span></span>  <br/> <span data-ttu-id="a9f39-369">pase numurs</span><span class="sxs-lookup"><span data-stu-id="a9f39-369">pase numurs</span></span>  <br/> |
   
## <a name="lithuania"></a><span data-ttu-id="a9f39-370">Lituania</span><span class="sxs-lookup"><span data-stu-id="a9f39-370">Lithuania</span></span>

### <a name="format"></a><span data-ttu-id="a9f39-371">Formato</span><span class="sxs-lookup"><span data-stu-id="a9f39-371">Format</span></span>

<span data-ttu-id="a9f39-372">Otto cifre o lettere senza spazi o delimitatori</span><span class="sxs-lookup"><span data-stu-id="a9f39-372">Eight digits or letters with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="a9f39-373">Modello</span><span class="sxs-lookup"><span data-stu-id="a9f39-373">Pattern</span></span>

<span data-ttu-id="a9f39-374">Otto cifre o lettere (senza distinzione tra maiuscole e minuscole)</span><span class="sxs-lookup"><span data-stu-id="a9f39-374">Eight digits or letters (not case sensitive)</span></span>
  
### <a name="checksum"></a><span data-ttu-id="a9f39-375">Checksum</span><span class="sxs-lookup"><span data-stu-id="a9f39-375">Checksum</span></span>

<span data-ttu-id="a9f39-376">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="a9f39-376">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="a9f39-377">Definizione</span><span class="sxs-lookup"><span data-stu-id="a9f39-377">Definition</span></span>

<span data-ttu-id="a9f39-378">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="a9f39-378">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="a9f39-379">L'espressione `Regex_lithuania_eu_passport_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="a9f39-379">The regular expression  `Regex_lithuania_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="a9f39-380">Viene trovata una `Keywords_lithuania_eu_passport_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="a9f39-380">A keyword from  `Keywords_lithuania_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_lithuania_eu_passport_number" />
          <Match idRef="Keywords_lithuania_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a9f39-381">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="a9f39-381">Keywords</span></span>

<span data-ttu-id="a9f39-382">| |</span><span class="sxs-lookup"><span data-stu-id="a9f39-382"></span></span>
|<span data-ttu-id="a9f39-383">**Keywords_lithuania_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="a9f39-383">**Keywords_lithuania_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="a9f39-384">passport number</span><span class="sxs-lookup"><span data-stu-id="a9f39-384">passport number</span></span>  <br/> <span data-ttu-id="a9f39-385">numero di passaporto di lithunian</span><span class="sxs-lookup"><span data-stu-id="a9f39-385">lithunian passport number</span></span>  <br/> <span data-ttu-id="a9f39-386">Passport No</span><span class="sxs-lookup"><span data-stu-id="a9f39-386">passport no</span></span>  <br/> <span data-ttu-id="a9f39-387">numero di Paso</span><span class="sxs-lookup"><span data-stu-id="a9f39-387">paso numeris</span></span>  <br/> |
   
## <a name="luxemburg"></a><span data-ttu-id="a9f39-388">Lussemburgo</span><span class="sxs-lookup"><span data-stu-id="a9f39-388">Luxemburg</span></span>

### <a name="format"></a><span data-ttu-id="a9f39-389">Formato</span><span class="sxs-lookup"><span data-stu-id="a9f39-389">Format</span></span>

<span data-ttu-id="a9f39-390">Otto cifre o lettere senza spazi o delimitatori</span><span class="sxs-lookup"><span data-stu-id="a9f39-390">Eight digits or letters with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="a9f39-391">Modello</span><span class="sxs-lookup"><span data-stu-id="a9f39-391">Pattern</span></span>

<span data-ttu-id="a9f39-392">Otto cifre o lettere (senza distinzione tra maiuscole e minuscole)</span><span class="sxs-lookup"><span data-stu-id="a9f39-392">Eight digits or letters (not case sensitive)</span></span>
  
### <a name="checksum"></a><span data-ttu-id="a9f39-393">Checksum</span><span class="sxs-lookup"><span data-stu-id="a9f39-393">Checksum</span></span>

<span data-ttu-id="a9f39-394">No</span><span class="sxs-lookup"><span data-stu-id="a9f39-394">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="a9f39-395">Definizione</span><span class="sxs-lookup"><span data-stu-id="a9f39-395">Definition</span></span>

<span data-ttu-id="a9f39-396">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="a9f39-396">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="a9f39-397">L'espressione `Regex_nation_eu_passport_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="a9f39-397">The regular expression  `Regex_nation_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="a9f39-398">Viene trovata una `Keywords_nation_eu_passport_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="a9f39-398">A keyword from  `Keywords_nation_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_nation_eu_passport_number" />
          <Match idRef="Keywords_nation_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a9f39-399">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="a9f39-399">Keywords</span></span>

<span data-ttu-id="a9f39-400">| |</span><span class="sxs-lookup"><span data-stu-id="a9f39-400"></span></span>
|<span data-ttu-id="a9f39-401">**Keywords_nation_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="a9f39-401">**Keywords_nation_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="a9f39-402">passport number</span><span class="sxs-lookup"><span data-stu-id="a9f39-402">passport number</span></span>  <br/> <span data-ttu-id="a9f39-403">numero di passaporto lettone</span><span class="sxs-lookup"><span data-stu-id="a9f39-403">latvian passport number</span></span>  <br/> <span data-ttu-id="a9f39-404">Passport No</span><span class="sxs-lookup"><span data-stu-id="a9f39-404">passport no</span></span>  <br/> <span data-ttu-id="a9f39-405">passnummer</span><span class="sxs-lookup"><span data-stu-id="a9f39-405">passnummer</span></span>  <br/> |
   
## <a name="malta"></a><span data-ttu-id="a9f39-406">Malta</span><span class="sxs-lookup"><span data-stu-id="a9f39-406">Malta</span></span>

### <a name="format"></a><span data-ttu-id="a9f39-407">Formato</span><span class="sxs-lookup"><span data-stu-id="a9f39-407">Format</span></span>

<span data-ttu-id="a9f39-408">Sette cifre senza spazi o delimitatori</span><span class="sxs-lookup"><span data-stu-id="a9f39-408">Seven digits without spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="a9f39-409">Modello</span><span class="sxs-lookup"><span data-stu-id="a9f39-409">Pattern</span></span>

 <span data-ttu-id="a9f39-410">Sette cifre</span><span class="sxs-lookup"><span data-stu-id="a9f39-410">Seven digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="a9f39-411">Checksum</span><span class="sxs-lookup"><span data-stu-id="a9f39-411">Checksum</span></span>

<span data-ttu-id="a9f39-412">No</span><span class="sxs-lookup"><span data-stu-id="a9f39-412">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="a9f39-413">Definizione</span><span class="sxs-lookup"><span data-stu-id="a9f39-413">Definition</span></span>

<span data-ttu-id="a9f39-414">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="a9f39-414">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="a9f39-415">L'espressione `Regex_malta_eu_passport_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="a9f39-415">The regular expression  `Regex_malta_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="a9f39-416">Viene trovata una `Keywords_malta_eu_passport_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="a9f39-416">A keyword from  `Keywords_malta_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_malta_eu_passport_number" />
          <Match idRef="Keywords_malta_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a9f39-417">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="a9f39-417">Keywords</span></span>

<span data-ttu-id="a9f39-418">| |</span><span class="sxs-lookup"><span data-stu-id="a9f39-418"></span></span>
|<span data-ttu-id="a9f39-419">**Keywords_malta_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="a9f39-419">**Keywords_malta_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="a9f39-420">passport number</span><span class="sxs-lookup"><span data-stu-id="a9f39-420">passport number</span></span>  <br/> <span data-ttu-id="a9f39-421">numero di passaporto maltese</span><span class="sxs-lookup"><span data-stu-id="a9f39-421">maltese passport number</span></span>  <br/> <span data-ttu-id="a9f39-422">Passport No</span><span class="sxs-lookup"><span data-stu-id="a9f39-422">passport no</span></span>  <br/> <span data-ttu-id="a9f39-423">numru tal-passaport</span><span class="sxs-lookup"><span data-stu-id="a9f39-423">numru tal-passaport</span></span>  <br/> |
   
## <a name="netherlands"></a><span data-ttu-id="a9f39-424">Paesi Bassi</span><span class="sxs-lookup"><span data-stu-id="a9f39-424">Netherlands</span></span>

### <a name="format"></a><span data-ttu-id="a9f39-425">Formato</span><span class="sxs-lookup"><span data-stu-id="a9f39-425">Format</span></span>

<span data-ttu-id="a9f39-426">Nove lettere o cifre senza spazi o delimitatori</span><span class="sxs-lookup"><span data-stu-id="a9f39-426">Nine letters or digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="a9f39-427">Modello</span><span class="sxs-lookup"><span data-stu-id="a9f39-427">Pattern</span></span>

<span data-ttu-id="a9f39-428">Nove lettere o cifre</span><span class="sxs-lookup"><span data-stu-id="a9f39-428">Nine letters or digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="a9f39-429">Checksum</span><span class="sxs-lookup"><span data-stu-id="a9f39-429">Checksum</span></span>

<span data-ttu-id="a9f39-430">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="a9f39-430">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="a9f39-431">Definizione</span><span class="sxs-lookup"><span data-stu-id="a9f39-431">Definition</span></span>

<span data-ttu-id="a9f39-432">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="a9f39-432">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="a9f39-433">L'espressione `Regex_netherlands_eu_passport_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="a9f39-433">The regular expression  `Regex_netherlands_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="a9f39-434">Viene trovata una `Keywords_netherlands_eu_passport_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="a9f39-434">A keyword from  `Keywords_netherlands_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_netherlands_eu_passport_number" />
          <Match idRef="Keywords_netherlands_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a9f39-435">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="a9f39-435">Keywords</span></span>

<span data-ttu-id="a9f39-436">| |</span><span class="sxs-lookup"><span data-stu-id="a9f39-436"></span></span>
|<span data-ttu-id="a9f39-437">**Keywords_netherlands_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="a9f39-437">**Keywords_netherlands_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="a9f39-438">numero di passaporto olandese</span><span class="sxs-lookup"><span data-stu-id="a9f39-438">dutch passport number</span></span>  <br/> <span data-ttu-id="a9f39-439">passport number</span><span class="sxs-lookup"><span data-stu-id="a9f39-439">passport number</span></span>  <br/> <span data-ttu-id="a9f39-440">numero di passaporto per i Paesi Bassi</span><span class="sxs-lookup"><span data-stu-id="a9f39-440">netherlands passport number</span></span>  <br/> <span data-ttu-id="a9f39-441">Nederlanden PASPOORT Nummer</span><span class="sxs-lookup"><span data-stu-id="a9f39-441">nederlanden paspoort nummer</span></span>  <br/> <span data-ttu-id="a9f39-442">PASPOORT</span><span class="sxs-lookup"><span data-stu-id="a9f39-442">paspoort</span></span>  <br/> <span data-ttu-id="a9f39-443">Nederlanden paspoortnummer</span><span class="sxs-lookup"><span data-stu-id="a9f39-443">nederlanden paspoortnummer</span></span>  <br/> <span data-ttu-id="a9f39-444">paspoortnummer</span><span class="sxs-lookup"><span data-stu-id="a9f39-444">paspoortnummer</span></span>  <br/> |
   
## <a name="poland"></a><span data-ttu-id="a9f39-445">Polonia</span><span class="sxs-lookup"><span data-stu-id="a9f39-445">Poland</span></span>

<span data-ttu-id="a9f39-446">Per informazioni dettagliate, vedere la sezione "Poland Passport Number" in [che cosa cercano i tipi di informazioni riservate](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="a9f39-446">For details, see the section "Poland Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="portugal"></a><span data-ttu-id="a9f39-447">Portogallo</span><span class="sxs-lookup"><span data-stu-id="a9f39-447">Portugal</span></span>

### <a name="format"></a><span data-ttu-id="a9f39-448">Formato</span><span class="sxs-lookup"><span data-stu-id="a9f39-448">Format</span></span>

<span data-ttu-id="a9f39-449">Una lettera seguita da sei cifre senza spazi o delimitatori</span><span class="sxs-lookup"><span data-stu-id="a9f39-449">One letter followed by six digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="a9f39-450">Modello</span><span class="sxs-lookup"><span data-stu-id="a9f39-450">Pattern</span></span>

<span data-ttu-id="a9f39-451">Una lettera seguita da sei cifre:</span><span class="sxs-lookup"><span data-stu-id="a9f39-451">One letter followed by six digits:</span></span>
  
- <span data-ttu-id="a9f39-452">Una lettera (senza distinzione tra maiuscole/minuscole)</span><span class="sxs-lookup"><span data-stu-id="a9f39-452">One letter (not case sensitive)</span></span>
    
- <span data-ttu-id="a9f39-453">Sei cifre</span><span class="sxs-lookup"><span data-stu-id="a9f39-453">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="a9f39-454">Checksum</span><span class="sxs-lookup"><span data-stu-id="a9f39-454">Checksum</span></span>

<span data-ttu-id="a9f39-455">No</span><span class="sxs-lookup"><span data-stu-id="a9f39-455">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="a9f39-456">Definizione</span><span class="sxs-lookup"><span data-stu-id="a9f39-456">Definition</span></span>

<span data-ttu-id="a9f39-457">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="a9f39-457">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="a9f39-458">L'espressione `Regex_portugal_eu_passport_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="a9f39-458">The regular expression  `Regex_portugal_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="a9f39-459">Viene trovata una `Keywords_portugal_eu_passport_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="a9f39-459">A keyword from  `Keywords_portugal_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_portugal_eu_passport_number" />
          <Match idRef="Keywords_portugal_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a9f39-460">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="a9f39-460">Keywords</span></span>

<span data-ttu-id="a9f39-461">| |</span><span class="sxs-lookup"><span data-stu-id="a9f39-461"></span></span>
|<span data-ttu-id="a9f39-462">**Keywords_portugal_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="a9f39-462">**Keywords_portugal_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="a9f39-463">passport number</span><span class="sxs-lookup"><span data-stu-id="a9f39-463">passport number</span></span>  <br/> <span data-ttu-id="a9f39-464">numero di passaporto portoghese</span><span class="sxs-lookup"><span data-stu-id="a9f39-464">portuguese passport number</span></span>  <br/> <span data-ttu-id="a9f39-465">Passport No</span><span class="sxs-lookup"><span data-stu-id="a9f39-465">passport no</span></span>  <br/> <span data-ttu-id="a9f39-466">número do passaporte</span><span class="sxs-lookup"><span data-stu-id="a9f39-466">número do passaporte</span></span>  <br/> |
   
## <a name="romania"></a><span data-ttu-id="a9f39-467">Romania</span><span class="sxs-lookup"><span data-stu-id="a9f39-467">Romania</span></span>

### <a name="format"></a><span data-ttu-id="a9f39-468">Formato</span><span class="sxs-lookup"><span data-stu-id="a9f39-468">Format</span></span>

<span data-ttu-id="a9f39-469">Otto o nove cifre senza spazi e delimitatori</span><span class="sxs-lookup"><span data-stu-id="a9f39-469">Eight or nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="a9f39-470">Modello</span><span class="sxs-lookup"><span data-stu-id="a9f39-470">Pattern</span></span>

<span data-ttu-id="a9f39-471">Otto o nove cifre</span><span class="sxs-lookup"><span data-stu-id="a9f39-471">Eight or nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="a9f39-472">Checksum</span><span class="sxs-lookup"><span data-stu-id="a9f39-472">Checksum</span></span>

<span data-ttu-id="a9f39-473">No</span><span class="sxs-lookup"><span data-stu-id="a9f39-473">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="a9f39-474">Definizione</span><span class="sxs-lookup"><span data-stu-id="a9f39-474">Definition</span></span>

<span data-ttu-id="a9f39-475">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="a9f39-475">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="a9f39-476">L'espressione `Regex_romania_eu_passport_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="a9f39-476">The regular expression  `Regex_romania_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="a9f39-477">Viene trovata una `Keywords_romania_eu_passport_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="a9f39-477">A keyword from  `Keywords_romania_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_romania_eu_passport_number" />
          <Match idRef="Keywords_romania_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a9f39-478">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="a9f39-478">Keywords</span></span>

<span data-ttu-id="a9f39-479">| |</span><span class="sxs-lookup"><span data-stu-id="a9f39-479"></span></span>
|<span data-ttu-id="a9f39-480">**Keywords_romania_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="a9f39-480">**Keywords_romania_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="a9f39-481">passport number</span><span class="sxs-lookup"><span data-stu-id="a9f39-481">passport number</span></span>  <br/> <span data-ttu-id="a9f39-482">numero di passaporto rumeno</span><span class="sxs-lookup"><span data-stu-id="a9f39-482">romanian passport number</span></span>  <br/> <span data-ttu-id="a9f39-483">Passport No</span><span class="sxs-lookup"><span data-stu-id="a9f39-483">passport no</span></span>  <br/> <span data-ttu-id="a9f39-484">numărul pașaportului</span><span class="sxs-lookup"><span data-stu-id="a9f39-484">numărul pașaportului</span></span>  <br/> |
   
## <a name="slovakia"></a><span data-ttu-id="a9f39-485">Slovacchia</span><span class="sxs-lookup"><span data-stu-id="a9f39-485">Slovakia</span></span>

### <a name="format"></a><span data-ttu-id="a9f39-486">Formato</span><span class="sxs-lookup"><span data-stu-id="a9f39-486">Format</span></span>

<span data-ttu-id="a9f39-487">Una cifra o una lettera seguita da sette cifre senza spazi o delimitatori</span><span class="sxs-lookup"><span data-stu-id="a9f39-487">One digit or letter followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="a9f39-488">Modello</span><span class="sxs-lookup"><span data-stu-id="a9f39-488">Pattern</span></span>

<span data-ttu-id="a9f39-489">Una cifra o una lettera (senza distinzione tra maiuscole/minuscole) seguita da sette cifre</span><span class="sxs-lookup"><span data-stu-id="a9f39-489">One digit or letter (not case sensitive) followed by seven digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="a9f39-490">Checksum</span><span class="sxs-lookup"><span data-stu-id="a9f39-490">Checksum</span></span>

<span data-ttu-id="a9f39-491">No</span><span class="sxs-lookup"><span data-stu-id="a9f39-491">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="a9f39-492">Definizione</span><span class="sxs-lookup"><span data-stu-id="a9f39-492">Definition</span></span>

<span data-ttu-id="a9f39-493">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="a9f39-493">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="a9f39-494">L'espressione `Regex_slovakia_eu_passport_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="a9f39-494">The regular expression  `Regex_slovakia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="a9f39-495">Viene trovata una `Keywords_slovakia_eu_passport_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="a9f39-495">A keyword from  `Keywords_slovakia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovakia_eu_passport_number" />
          <Match idRef="Keywords_slovakia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a9f39-496">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="a9f39-496">Keywords</span></span>

<span data-ttu-id="a9f39-497">| |</span><span class="sxs-lookup"><span data-stu-id="a9f39-497"></span></span>
|<span data-ttu-id="a9f39-498">**Keywords_slovakia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="a9f39-498">**Keywords_slovakia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="a9f39-499">passport number</span><span class="sxs-lookup"><span data-stu-id="a9f39-499">passport number</span></span>  <br/> <span data-ttu-id="a9f39-500">numero di passaporto slovacco</span><span class="sxs-lookup"><span data-stu-id="a9f39-500">slovakian passport number</span></span>  <br/> <span data-ttu-id="a9f39-501">Passport No</span><span class="sxs-lookup"><span data-stu-id="a9f39-501">passport no</span></span>  <br/> <span data-ttu-id="a9f39-502">číslo Pasu</span><span class="sxs-lookup"><span data-stu-id="a9f39-502">číslo pasu</span></span>  <br/> |
   
## <a name="slovenia"></a><span data-ttu-id="a9f39-503">Slovenia</span><span class="sxs-lookup"><span data-stu-id="a9f39-503">Slovenia</span></span>

### <a name="format"></a><span data-ttu-id="a9f39-504">Formato</span><span class="sxs-lookup"><span data-stu-id="a9f39-504">Format</span></span>

<span data-ttu-id="a9f39-505">Due lettere seguite da sette cifre senza spazi o delimitatori</span><span class="sxs-lookup"><span data-stu-id="a9f39-505">Two letters followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="a9f39-506">Modello</span><span class="sxs-lookup"><span data-stu-id="a9f39-506">Pattern</span></span>

<span data-ttu-id="a9f39-507">Due lettere seguite da sette cifre:</span><span class="sxs-lookup"><span data-stu-id="a9f39-507">Two letters followed by seven digits:</span></span>
  
- <span data-ttu-id="a9f39-508">La lettera "P"</span><span class="sxs-lookup"><span data-stu-id="a9f39-508">The letter "P"</span></span>
    
- <span data-ttu-id="a9f39-509">Una lettera maiuscola</span><span class="sxs-lookup"><span data-stu-id="a9f39-509">One uppercase letter</span></span>
    
- <span data-ttu-id="a9f39-510">Sette cifre</span><span class="sxs-lookup"><span data-stu-id="a9f39-510">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="a9f39-511">Checksum</span><span class="sxs-lookup"><span data-stu-id="a9f39-511">Checksum</span></span>

<span data-ttu-id="a9f39-512">No</span><span class="sxs-lookup"><span data-stu-id="a9f39-512">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="a9f39-513">Definizione</span><span class="sxs-lookup"><span data-stu-id="a9f39-513">Definition</span></span>

<span data-ttu-id="a9f39-514">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="a9f39-514">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="a9f39-515">L'espressione `Regex_slovenia_eu_passport_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="a9f39-515">The regular expression  `Regex_slovenia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="a9f39-516">Viene trovata una `Keywords_slovenia_eu_passport_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="a9f39-516">A keyword from  `Keywords_slovenia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovenia_eu_passport_number" />
          <Match idRef="Keywords_slovenia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a9f39-517">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="a9f39-517">Keywords</span></span>

<span data-ttu-id="a9f39-518">| |</span><span class="sxs-lookup"><span data-stu-id="a9f39-518"></span></span>
|<span data-ttu-id="a9f39-519">**Keywords_slovenia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="a9f39-519">**Keywords_slovenia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="a9f39-520">passport number</span><span class="sxs-lookup"><span data-stu-id="a9f39-520">passport number</span></span>  <br/> <span data-ttu-id="a9f39-521">numero di passaporto sloveno</span><span class="sxs-lookup"><span data-stu-id="a9f39-521">slovenian passport number</span></span>  <br/> <span data-ttu-id="a9f39-522">Passport No</span><span class="sxs-lookup"><span data-stu-id="a9f39-522">passport no</span></span>  <br/> <span data-ttu-id="a9f39-523">številka potnega lista</span><span class="sxs-lookup"><span data-stu-id="a9f39-523">številka potnega lista</span></span>  <br/> |
   
## <a name="spain"></a><span data-ttu-id="a9f39-524">Spagna</span><span class="sxs-lookup"><span data-stu-id="a9f39-524">Spain</span></span>

### <a name="format"></a><span data-ttu-id="a9f39-525">Formato</span><span class="sxs-lookup"><span data-stu-id="a9f39-525">Format</span></span>

<span data-ttu-id="a9f39-526">Combinazione di otto o nove caratteri di lettere e numeri senza spazi o delimitatori</span><span class="sxs-lookup"><span data-stu-id="a9f39-526">An eight- or nine-character combination of letters and numbers with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="a9f39-527">Modello</span><span class="sxs-lookup"><span data-stu-id="a9f39-527">Pattern</span></span>

<span data-ttu-id="a9f39-528">Combinazione di lettere e numeri di otto o nove caratteri:</span><span class="sxs-lookup"><span data-stu-id="a9f39-528">An eight- or nine-character combination of letters and numbers:</span></span>
  
-  <span data-ttu-id="a9f39-529">Due cifre o lettere</span><span class="sxs-lookup"><span data-stu-id="a9f39-529">Two digits or letters</span></span> 
    
- <span data-ttu-id="a9f39-530">Una cifra o una lettera (facoltativa)</span><span class="sxs-lookup"><span data-stu-id="a9f39-530">One digit or letter (optional)</span></span>
    
- <span data-ttu-id="a9f39-531">Sei cifre</span><span class="sxs-lookup"><span data-stu-id="a9f39-531">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="a9f39-532">Checksum</span><span class="sxs-lookup"><span data-stu-id="a9f39-532">Checksum</span></span>

<span data-ttu-id="a9f39-533">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="a9f39-533">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="a9f39-534">Definizione</span><span class="sxs-lookup"><span data-stu-id="a9f39-534">Definition</span></span>

<span data-ttu-id="a9f39-535">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="a9f39-535">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="a9f39-536">L'espressione `Regex_spain_eu_passport_number` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="a9f39-536">The regular expression  `Regex_spain_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="a9f39-537">Viene trovata una `Keywords_spain_eu_passport_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="a9f39-537">A keyword from  `Keywords_spain_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_spain_eu_passport_number" />
          <Match idRef="Keywords_spain_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a9f39-538">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="a9f39-538">Keywords</span></span>

<span data-ttu-id="a9f39-539">| |</span><span class="sxs-lookup"><span data-stu-id="a9f39-539"></span></span>
|<span data-ttu-id="a9f39-540">**Keywords_spain_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="a9f39-540">**Keywords_spain_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="a9f39-541">passaporto</span><span class="sxs-lookup"><span data-stu-id="a9f39-541">passport</span></span>  <br/> <span data-ttu-id="a9f39-542">passaporto della Spagna</span><span class="sxs-lookup"><span data-stu-id="a9f39-542">spain passport</span></span>  <br/> <span data-ttu-id="a9f39-543">libro del passaporto</span><span class="sxs-lookup"><span data-stu-id="a9f39-543">passport book</span></span>  <br/> <span data-ttu-id="a9f39-544">passport number</span><span class="sxs-lookup"><span data-stu-id="a9f39-544">passport number</span></span>  <br/> <span data-ttu-id="a9f39-545">Passport No</span><span class="sxs-lookup"><span data-stu-id="a9f39-545">passport no</span></span>  <br/> <span data-ttu-id="a9f39-546">libreta pasaporte</span><span class="sxs-lookup"><span data-stu-id="a9f39-546">libreta pasaporte</span></span>  <br/> <span data-ttu-id="a9f39-547">número pasaporte</span><span class="sxs-lookup"><span data-stu-id="a9f39-547">número pasaporte</span></span>  <br/> <span data-ttu-id="a9f39-548">pasaporte España</span><span class="sxs-lookup"><span data-stu-id="a9f39-548">españa pasaporte</span></span>  <br/> <span data-ttu-id="a9f39-549">pasaporte</span><span class="sxs-lookup"><span data-stu-id="a9f39-549">pasaporte</span></span>  <br/> |
   
## <a name="sweden"></a><span data-ttu-id="a9f39-550">Svezia</span><span class="sxs-lookup"><span data-stu-id="a9f39-550">Sweden</span></span>

<span data-ttu-id="a9f39-551">Per informazioni dettagliate, vedere la sezione "Sweden Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="a9f39-551">For details, see the section "Sweden Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="uk"></a><span data-ttu-id="a9f39-552">Regno Unito</span><span class="sxs-lookup"><span data-stu-id="a9f39-552">UK</span></span>

<span data-ttu-id="a9f39-553">Per informazioni dettagliate, vedere la sezione "Stati Uniti/Regno Unito</span><span class="sxs-lookup"><span data-stu-id="a9f39-553">For details, see the section "U.S. / U.K.</span></span> <span data-ttu-id="a9f39-554">Numero di passaporto "in [quello che cercano i tipi di informazioni riservate](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="a9f39-554">Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="a9f39-555">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a9f39-555">See also</span></span>

[<span data-ttu-id="a9f39-556">Cosa individuano le tipologie di informazioni sensibili</span><span class="sxs-lookup"><span data-stu-id="a9f39-556">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)

