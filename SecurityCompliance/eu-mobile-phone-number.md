---
title: Numero di cellulare UE
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 8/16/2018
ms.audience: Admin
ms.topic: reference
ms.service: o365-administration
localization_priority: Normal
ms.assetid: 555e7675-2ae8-42d1-9b8e-2c8f8cd21337
description: Prevenzione perdita dati (DLP) in Office 365 Security &amp; centro conformità include molti tipi di informazioni riservate che si desidera utilizzare i criteri DLP. In questo argomento viene descritto il tipo di informazioni riservate dell'Unione europea numero di cellulare.
ms.openlocfilehash: d0818759dae8ed86cc9aef6f7fad48cbd2acf24f
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/27/2018
ms.locfileid: "22530705"
---
# <a name="eu-mobile-phone-number"></a><span data-ttu-id="c51fa-104">Numero di cellulare UE</span><span class="sxs-lookup"><span data-stu-id="c51fa-104">EU Mobile Phone Number</span></span>

<span data-ttu-id="c51fa-p102">Prevenzione perdita dati (DLP) in Office 365 Security &amp; centro conformità include molti tipi di informazioni riservate che si desidera utilizzare i criteri DLP. In questo argomento viene descritto il tipo di informazioni riservate dell'Unione europea numero di cellulare.</span><span class="sxs-lookup"><span data-stu-id="c51fa-p102">Data loss prevention (DLP) in the Office 365 Security &amp; Compliance Center includes many sensitive information types that are ready for you to use in your DLP policies. This topic describes the EU Mobile Phone Number sensitive information type.</span></span> 
  
## <a name="austria"></a><span data-ttu-id="c51fa-107">Austria</span><span class="sxs-lookup"><span data-stu-id="c51fa-107">Austria</span></span>

### <a name="format"></a><span data-ttu-id="c51fa-108">Formato</span><span class="sxs-lookup"><span data-stu-id="c51fa-108">Format</span></span>

<span data-ttu-id="c51fa-109">Cifre senza le lunghezze standard</span><span class="sxs-lookup"><span data-stu-id="c51fa-109">Digits without standard lengths</span></span>
  
### <a name="pattern"></a><span data-ttu-id="c51fa-110">Modello</span><span class="sxs-lookup"><span data-stu-id="c51fa-110">Pattern</span></span>

-  <span data-ttu-id="c51fa-111">Cifre</span><span class="sxs-lookup"><span data-stu-id="c51fa-111">Digits</span></span> 
    
### <a name="definition"></a><span data-ttu-id="c51fa-112">Definizione</span><span class="sxs-lookup"><span data-stu-id="c51fa-112">Definition</span></span>

<span data-ttu-id="c51fa-113">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="c51fa-113">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="c51fa-114">L'espressione regolare `Regex_austria_eu_mobile_number` consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="c51fa-114">The regular expression  `Regex_austria_eu_mobile_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="c51fa-115">L'espressione regolare `Regex_austria_eu_formatted_mobile_number` consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="c51fa-115">The regular expression  `Regex_austria_eu_formatted_mobile_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="c51fa-116">Una parola chiave da `Keywords_austria_eu_mobile_number` viene trovato.</span><span class="sxs-lookup"><span data-stu-id="c51fa-116">A keyword from  `Keywords_austria_eu_mobile_number` is found.</span></span> 
    
```
 
<Entity id="a56a0418-136a-41ea-a337-4d0388b28e69" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_austria_eu_mobile_number"/>
          <Match idRef="Keywords_austria_eu_mobile_number" />
        </Pattern>
<Pattern confidenceLevel="75">
<IdMatch idRef="Regex_austria_eu_formatted_mobile_number" />
          </Pattern>
</Entity>
```

## <a name="belgium"></a><span data-ttu-id="c51fa-117">Belgio</span><span class="sxs-lookup"><span data-stu-id="c51fa-117">Belgium</span></span>

### <a name="pattern"></a><span data-ttu-id="c51fa-118">Modello</span><span class="sxs-lookup"><span data-stu-id="c51fa-118">Pattern</span></span>

-  <span data-ttu-id="c51fa-119">Cifre</span><span class="sxs-lookup"><span data-stu-id="c51fa-119">Digits</span></span> 
    
### <a name="definition"></a><span data-ttu-id="c51fa-120">Definizione</span><span class="sxs-lookup"><span data-stu-id="c51fa-120">Definition</span></span>

<span data-ttu-id="c51fa-121">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="c51fa-121">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="c51fa-122">L'espressione regolare `Regex_belgium_eu_mobile_number` consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="c51fa-122">The regular expression  `Regex_belgium_eu_mobile_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="c51fa-123">L'espressione regolare `Regex_belgium_eu_formatted_mobile_number` consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="c51fa-123">The regular expression  `Regex_belgium_eu_formatted_mobile_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="c51fa-124">Una parola chiave da `Keywords_belgium_eu_mobile_number` viene trovato.</span><span class="sxs-lookup"><span data-stu-id="c51fa-124">A keyword from  `Keywords_belgium_eu_mobile_number` is found.</span></span> 
    
```
 
<Entity id="a56a0418-136a-41ea-a337-4d0388b28e69" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_belgium_eu_mobile_number"/>
          <Match idRef="Keywords_belgium_eu_mobile_number" />
        </Pattern>
<Pattern confidenceLevel="75">
<IdMatch idRef="Regex_belgium_eu_formatted_mobile_number" />
          </Pattern>
</Entity>
```

## <a name="bulgaria"></a><span data-ttu-id="c51fa-125">Bulgaria</span><span class="sxs-lookup"><span data-stu-id="c51fa-125">Bulgaria</span></span>

### <a name="pattern"></a><span data-ttu-id="c51fa-126">Modello</span><span class="sxs-lookup"><span data-stu-id="c51fa-126">Pattern</span></span>

-  <span data-ttu-id="c51fa-127">Cifre</span><span class="sxs-lookup"><span data-stu-id="c51fa-127">Digits</span></span> 
    
### <a name="definition"></a><span data-ttu-id="c51fa-128">Definizione</span><span class="sxs-lookup"><span data-stu-id="c51fa-128">Definition</span></span>

<span data-ttu-id="c51fa-129">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="c51fa-129">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="c51fa-130">L'espressione regolare `Regex_bulgaria_eu_mobile_number` consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="c51fa-130">The regular expression  `Regex_bulgaria_eu_mobile_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="c51fa-131">L'espressione regolare `Regex_bulgaria_eu_formatted_mobile_number` consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="c51fa-131">The regular expression  `Regex_bulgaria_eu_formatted_mobile_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="c51fa-132">Una parola chiave da `Keywords_bulgaria_eu_mobile_number` viene trovato.</span><span class="sxs-lookup"><span data-stu-id="c51fa-132">A keyword from  `Keywords_bulgaria_eu_mobile_number` is found.</span></span> 
    
```
 
<Entity id="a56a0418-136a-41ea-a337-4d0388b28e69" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_bulgaria_eu_mobile_number"/>
          <Match idRef="Keywords_bulgaria_eu_mobile_number" />
        </Pattern>
<Pattern confidenceLevel="75">
<IdMatch idRef="Regex_bulgaria_eu_formatted_mobile_number" />
          </Pattern>
</Entity>
```

## <a name="croatia"></a><span data-ttu-id="c51fa-133">Croazia</span><span class="sxs-lookup"><span data-stu-id="c51fa-133">Croatia</span></span>

### <a name="pattern"></a><span data-ttu-id="c51fa-134">Modello</span><span class="sxs-lookup"><span data-stu-id="c51fa-134">Pattern</span></span>

-  <span data-ttu-id="c51fa-135">Cifre</span><span class="sxs-lookup"><span data-stu-id="c51fa-135">Digits</span></span> 
    
### <a name="definition"></a><span data-ttu-id="c51fa-136">Definizione</span><span class="sxs-lookup"><span data-stu-id="c51fa-136">Definition</span></span>

<span data-ttu-id="c51fa-137">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="c51fa-137">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="c51fa-138">L'espressione regolare `Regex_croatia_eu_mobile_number` consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="c51fa-138">The regular expression  `Regex_croatia_eu_mobile_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="c51fa-139">L'espressione regolare `Regex_croatia_eu_formatted_mobile_number` consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="c51fa-139">The regular expression  `Regex_croatia_eu_formatted_mobile_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="c51fa-140">Una parola chiave da `Keywords_croatia_eu_mobile_number` viene trovato.</span><span class="sxs-lookup"><span data-stu-id="c51fa-140">A keyword from  `Keywords_croatia_eu_mobile_number` is found.</span></span> 
    
```
<Entity id="a56a0418-136a-41ea-a337-4d0388b28e69" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_croatia_eu_mobile_number"/>
          <Match idRef="Keywords_croatia_eu_mobile_number" />
        </Pattern>
<Pattern confidenceLevel="75">
<IdMatch idRef="Regex_croatia_eu_formatted_mobile_number" />
          </Pattern>
</Entity>
```

## <a name="cyprus"></a><span data-ttu-id="c51fa-141">Cipro</span><span class="sxs-lookup"><span data-stu-id="c51fa-141">Cyprus</span></span>

### <a name="pattern"></a><span data-ttu-id="c51fa-142">Modello</span><span class="sxs-lookup"><span data-stu-id="c51fa-142">Pattern</span></span>

-  <span data-ttu-id="c51fa-143">Cifre</span><span class="sxs-lookup"><span data-stu-id="c51fa-143">Digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="c51fa-144">Checksum</span><span class="sxs-lookup"><span data-stu-id="c51fa-144">Checksum</span></span>

<span data-ttu-id="c51fa-145">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="c51fa-145">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="c51fa-146">Definizione</span><span class="sxs-lookup"><span data-stu-id="c51fa-146">Definition</span></span>

<span data-ttu-id="c51fa-147">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="c51fa-147">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="c51fa-148">L'espressione regolare `Regex_cyprus_eu_mobile_number` consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="c51fa-148">The regular expression  `Regex_cyprus_eu_mobile_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="c51fa-149">L'espressione regolare `Regex_cyprus_eu_formatted_mobile_number` consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="c51fa-149">The regular expression  `Regex_cyprus_eu_formatted_mobile_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="c51fa-150">Una parola chiave da `Keywords_cyprus_eu_mobile_number` viene trovato.</span><span class="sxs-lookup"><span data-stu-id="c51fa-150">A keyword from  `Keywords_cyprus_eu_mobile_number` is found.</span></span> 
    
```
 
<Entity id="a56a0418-136a-41ea-a337-4d0388b28e69" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_cyprus_eu_mobile_number"/>
          <Match idRef="Keywords_cyprus_eu_mobile_number" />
        </Pattern>
<Pattern confidenceLevel="75">
<IdMatch idRef="Regex_cyprus_eu_formatted_mobile_number" />
          </Pattern>
</Entity>
```

## <a name="czech-republic"></a><span data-ttu-id="c51fa-151">Repubblica Ceca</span><span class="sxs-lookup"><span data-stu-id="c51fa-151">Czech Republic</span></span>

### <a name="pattern"></a><span data-ttu-id="c51fa-152">Modello</span><span class="sxs-lookup"><span data-stu-id="c51fa-152">Pattern</span></span>

-  <span data-ttu-id="c51fa-153">Cifre</span><span class="sxs-lookup"><span data-stu-id="c51fa-153">Digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="c51fa-154">Checksum</span><span class="sxs-lookup"><span data-stu-id="c51fa-154">Checksum</span></span>

<span data-ttu-id="c51fa-155">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="c51fa-155">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="c51fa-156">Definizione</span><span class="sxs-lookup"><span data-stu-id="c51fa-156">Definition</span></span>

<span data-ttu-id="c51fa-157">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="c51fa-157">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="c51fa-158">L'espressione regolare `Regex_czech_republic_eu_mobile_number` consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="c51fa-158">The regular expression  `Regex_czech_republic_eu_mobile_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="c51fa-159">L'espressione regolare `Regex_czech_republic_eu_formatted_mobile_number` consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="c51fa-159">The regular expression  `Regex_czech_republic_eu_formatted_mobile_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="c51fa-160">Una parola chiave da `Keywords_czech_republic_eu_mobile_number` viene trovato.</span><span class="sxs-lookup"><span data-stu-id="c51fa-160">A keyword from  `Keywords_czech_republic_eu_mobile_number` is found.</span></span> 
    
```
 
<Entity id="a56a0418-136a-41ea-a337-4d0388b28e69" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_czech_republic_eu_mobile_number"/>
          <Match idRef="Keywords_czech_republic_eu_mobile_number" />
        </Pattern>
<Pattern confidenceLevel="75">
<IdMatch idRef="Regex_czech_republic_eu_formatted_mobile_number" />
          </Pattern>
</Entity>
```

## <a name="denmark"></a><span data-ttu-id="c51fa-161">Danimarca</span><span class="sxs-lookup"><span data-stu-id="c51fa-161">Denmark</span></span>

### <a name="pattern"></a><span data-ttu-id="c51fa-162">Modello</span><span class="sxs-lookup"><span data-stu-id="c51fa-162">Pattern</span></span>

-  <span data-ttu-id="c51fa-163">Cifre</span><span class="sxs-lookup"><span data-stu-id="c51fa-163">Digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="c51fa-164">Checksum</span><span class="sxs-lookup"><span data-stu-id="c51fa-164">Checksum</span></span>

<span data-ttu-id="c51fa-165">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="c51fa-165">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="c51fa-166">Definizione</span><span class="sxs-lookup"><span data-stu-id="c51fa-166">Definition</span></span>

<span data-ttu-id="c51fa-167">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="c51fa-167">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="c51fa-168">L'espressione regolare `Regex_denmark_eu_mobile_number` consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="c51fa-168">The regular expression  `Regex_denmark_eu_mobile_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="c51fa-169">L'espressione regolare `Regex_denmark_eu_formatted_mobile_number` consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="c51fa-169">The regular expression  `Regex_denmark_eu_formatted_mobile_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="c51fa-170">Una parola chiave da `Keywords_denmark_eu_mobile_number` viene trovato.</span><span class="sxs-lookup"><span data-stu-id="c51fa-170">A keyword from  `Keywords_denmark_eu_mobile_number` is found.</span></span> 
    
```
 
<Entity id="a56a0418-136a-41ea-a337-4d0388b28e69" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_denmark_eu_mobile_number"/>
          <Match idRef="Keywords_denmark_eu_mobile_number" />
        </Pattern>
<Pattern confidenceLevel="75">
<IdMatch idRef="Regex_denmark_eu_formatted_mobile_number" />
          </Pattern>
</Entity>
```

## <a name="estonia"></a><span data-ttu-id="c51fa-171">Estonia</span><span class="sxs-lookup"><span data-stu-id="c51fa-171">Estonia</span></span>

### <a name="pattern"></a><span data-ttu-id="c51fa-172">Modello</span><span class="sxs-lookup"><span data-stu-id="c51fa-172">Pattern</span></span>

-  <span data-ttu-id="c51fa-173">Cifre</span><span class="sxs-lookup"><span data-stu-id="c51fa-173">Digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="c51fa-174">Checksum</span><span class="sxs-lookup"><span data-stu-id="c51fa-174">Checksum</span></span>

<span data-ttu-id="c51fa-175">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="c51fa-175">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="c51fa-176">Definizione</span><span class="sxs-lookup"><span data-stu-id="c51fa-176">Definition</span></span>

<span data-ttu-id="c51fa-177">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="c51fa-177">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="c51fa-178">L'espressione regolare `Regex_estonia_eu_mobile_number` consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="c51fa-178">The regular expression  `Regex_estonia_eu_mobile_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="c51fa-179">L'espressione regolare `Regex_estonia_eu_formatted_mobile_number` consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="c51fa-179">The regular expression  `Regex_estonia_eu_formatted_mobile_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="c51fa-180">Una parola chiave da `Keywords_estonia_eu_mobile_number` viene trovato.</span><span class="sxs-lookup"><span data-stu-id="c51fa-180">A keyword from  `Keywords_estonia_eu_mobile_number` is found.</span></span> 
    
```
<Entity id="a56a0418-136a-41ea-a337-4d0388b28e69" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_estonia_eu_mobile_number"/>
          <Match idRef="Keywords_estonia_eu_mobile_number" />
        </Pattern>
<Pattern confidenceLevel="75">
<IdMatch idRef="Regex_estonia_eu_formatted_mobile_number" />
          </Pattern>
</Entity>
```

## <a name="finland"></a><span data-ttu-id="c51fa-181">Finlandia</span><span class="sxs-lookup"><span data-stu-id="c51fa-181">Finland</span></span>

### <a name="pattern"></a><span data-ttu-id="c51fa-182">Modello</span><span class="sxs-lookup"><span data-stu-id="c51fa-182">Pattern</span></span>

-  <span data-ttu-id="c51fa-183">Cifre</span><span class="sxs-lookup"><span data-stu-id="c51fa-183">Digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="c51fa-184">Checksum</span><span class="sxs-lookup"><span data-stu-id="c51fa-184">Checksum</span></span>

<span data-ttu-id="c51fa-185">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="c51fa-185">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="c51fa-186">Definizione</span><span class="sxs-lookup"><span data-stu-id="c51fa-186">Definition</span></span>

<span data-ttu-id="c51fa-187">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="c51fa-187">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="c51fa-188">L'espressione regolare `Regex_finland_eu_mobile_number` consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="c51fa-188">The regular expression  `Regex_finland_eu_mobile_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="c51fa-189">L'espressione regolare `Regex_finland_eu_formatted_mobile_number` consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="c51fa-189">The regular expression  `Regex_finland_eu_formatted_mobile_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="c51fa-190">Una parola chiave da `Keywords_finland_eu_mobile_number` viene trovato.</span><span class="sxs-lookup"><span data-stu-id="c51fa-190">A keyword from  `Keywords_finland_eu_mobile_number` is found.</span></span> 
    
```
 
<Entity id="a56a0418-136a-41ea-a337-4d0388b28e69" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_finland_eu_mobile_number"/>
          <Match idRef="Keywords_finland_eu_mobile_number" />
        </Pattern>
<Pattern confidenceLevel="75">
<IdMatch idRef="Regex_finland_eu_formatted_mobile_number" />
          </Pattern>
</Entity>
```

## <a name="france"></a><span data-ttu-id="c51fa-191">Francia</span><span class="sxs-lookup"><span data-stu-id="c51fa-191">France</span></span>

### <a name="pattern"></a><span data-ttu-id="c51fa-192">Modello</span><span class="sxs-lookup"><span data-stu-id="c51fa-192">Pattern</span></span>

-  <span data-ttu-id="c51fa-193">Cifre</span><span class="sxs-lookup"><span data-stu-id="c51fa-193">Digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="c51fa-194">Checksum</span><span class="sxs-lookup"><span data-stu-id="c51fa-194">Checksum</span></span>

<span data-ttu-id="c51fa-195">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="c51fa-195">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="c51fa-196">Definizione</span><span class="sxs-lookup"><span data-stu-id="c51fa-196">Definition</span></span>

<span data-ttu-id="c51fa-197">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="c51fa-197">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="c51fa-198">L'espressione regolare `Regex_france_eu_mobile_number` consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="c51fa-198">The regular expression  `Regex_france_eu_mobile_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="c51fa-199">L'espressione regolare `Regex_france_eu_formatted_mobile_number` consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="c51fa-199">The regular expression  `Regex_france_eu_formatted_mobile_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="c51fa-200">Una parola chiave da `Keywords_france_eu_mobile_number` viene trovato.</span><span class="sxs-lookup"><span data-stu-id="c51fa-200">A keyword from  `Keywords_france_eu_mobile_number` is found.</span></span> 
    
```
 
<Entity id="a56a0418-136a-41ea-a337-4d0388b28e69" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_france_eu_mobile_number"/>
          <Match idRef="Keywords_france_eu_mobile_number" />
        </Pattern>
<Pattern confidenceLevel="75">
<IdMatch idRef="Regex_france_eu_formatted_mobile_number" />
          </Pattern>
</Entity>
```

## <a name="germany"></a><span data-ttu-id="c51fa-201">Germania</span><span class="sxs-lookup"><span data-stu-id="c51fa-201">Germany</span></span>

### <a name="pattern"></a><span data-ttu-id="c51fa-202">Modello</span><span class="sxs-lookup"><span data-stu-id="c51fa-202">Pattern</span></span>

-  <span data-ttu-id="c51fa-203">Cifre</span><span class="sxs-lookup"><span data-stu-id="c51fa-203">Digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="c51fa-204">Checksum</span><span class="sxs-lookup"><span data-stu-id="c51fa-204">Checksum</span></span>

<span data-ttu-id="c51fa-205">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="c51fa-205">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="c51fa-206">Definizione</span><span class="sxs-lookup"><span data-stu-id="c51fa-206">Definition</span></span>

<span data-ttu-id="c51fa-207">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="c51fa-207">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="c51fa-208">L'espressione regolare `Regex_germany_eu_mobile_number` consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="c51fa-208">The regular expression  `Regex_germany_eu_mobile_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="c51fa-209">L'espressione regolare `Regex_germany_eu_formatted_mobile_number` consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="c51fa-209">The regular expression  `Regex_germany_eu_formatted_mobile_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="c51fa-210">Una parola chiave da `Keywords_germany_eu_mobile_number` viene trovato.</span><span class="sxs-lookup"><span data-stu-id="c51fa-210">A keyword from  `Keywords_germany_eu_mobile_number` is found.</span></span> 
    
```
 
<Entity id="a56a0418-136a-41ea-a337-4d0388b28e69" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_germany_eu_mobile_number"/>
          <Match idRef="Keywords_germany_eu_mobile_number" />
        </Pattern>
<Pattern confidenceLevel="75">
<IdMatch idRef="Regex_germany_eu_formatted_mobile_number" />
          </Pattern>
</Entity>
```

## <a name="greece"></a><span data-ttu-id="c51fa-211">Grecia</span><span class="sxs-lookup"><span data-stu-id="c51fa-211">Greece</span></span>

### <a name="pattern"></a><span data-ttu-id="c51fa-212">Modello</span><span class="sxs-lookup"><span data-stu-id="c51fa-212">Pattern</span></span>

-  <span data-ttu-id="c51fa-213">Cifre</span><span class="sxs-lookup"><span data-stu-id="c51fa-213">Digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="c51fa-214">Checksum</span><span class="sxs-lookup"><span data-stu-id="c51fa-214">Checksum</span></span>

<span data-ttu-id="c51fa-215">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="c51fa-215">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="c51fa-216">Definizione</span><span class="sxs-lookup"><span data-stu-id="c51fa-216">Definition</span></span>

<span data-ttu-id="c51fa-217">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="c51fa-217">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="c51fa-218">L'espressione regolare `Regex_greece_eu_mobile_number` consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="c51fa-218">The regular expression  `Regex_greece_eu_mobile_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="c51fa-219">L'espressione regolare `Regex_greece_eu_formatted_mobile_number` consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="c51fa-219">The regular expression  `Regex_greece_eu_formatted_mobile_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="c51fa-220">Una parola chiave da `Keywords_greece_eu_mobile_number` viene trovato.</span><span class="sxs-lookup"><span data-stu-id="c51fa-220">A keyword from  `Keywords_greece_eu_mobile_number` is found.</span></span> 
    
```
 
<Entity id="a56a0418-136a-41ea-a337-4d0388b28e69" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_greece_eu_mobile_number"/>
          <Match idRef="Keywords_greece_eu_mobile_number" />
        </Pattern>
<Pattern confidenceLevel="75">
<IdMatch idRef="Regex_greece_eu_formatted_mobile_number" />
          </Pattern>
</Entity>
```

## <a name="hungary"></a><span data-ttu-id="c51fa-221">Ungheria</span><span class="sxs-lookup"><span data-stu-id="c51fa-221">Hungary</span></span>

### <a name="pattern"></a><span data-ttu-id="c51fa-222">Modello</span><span class="sxs-lookup"><span data-stu-id="c51fa-222">Pattern</span></span>

-  <span data-ttu-id="c51fa-223">Cifre</span><span class="sxs-lookup"><span data-stu-id="c51fa-223">Digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="c51fa-224">Checksum</span><span class="sxs-lookup"><span data-stu-id="c51fa-224">Checksum</span></span>

<span data-ttu-id="c51fa-225">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="c51fa-225">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="c51fa-226">Definizione</span><span class="sxs-lookup"><span data-stu-id="c51fa-226">Definition</span></span>

<span data-ttu-id="c51fa-227">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="c51fa-227">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="c51fa-228">L'espressione regolare `Regex_hungary_eu_mobile_number` consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="c51fa-228">The regular expression  `Regex_hungary_eu_mobile_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="c51fa-229">L'espressione regolare `Regex_hungary_eu_formatted_mobile_number` consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="c51fa-229">The regular expression  `Regex_hungary_eu_formatted_mobile_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="c51fa-230">Una parola chiave da `Keywords_hungary_eu_mobile_number` viene trovato.</span><span class="sxs-lookup"><span data-stu-id="c51fa-230">A keyword from  `Keywords_hungary_eu_mobile_number` is found.</span></span> 
    
```
<Entity id="a56a0418-136a-41ea-a337-4d0388b28e69" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_hungary_eu_mobile_number"/>
          <Match idRef="Keywords_hungary_eu_mobile_number" />
        </Pattern>
<Pattern confidenceLevel="75">
<IdMatch idRef="Regex_hungary_eu_formatted_mobile_number" />
          </Pattern>
</Entity>
```

## <a name="ireland"></a><span data-ttu-id="c51fa-231">Irlanda</span><span class="sxs-lookup"><span data-stu-id="c51fa-231">Ireland</span></span>

### <a name="pattern"></a><span data-ttu-id="c51fa-232">Modello</span><span class="sxs-lookup"><span data-stu-id="c51fa-232">Pattern</span></span>

-  <span data-ttu-id="c51fa-233">Cifre</span><span class="sxs-lookup"><span data-stu-id="c51fa-233">Digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="c51fa-234">Checksum</span><span class="sxs-lookup"><span data-stu-id="c51fa-234">Checksum</span></span>

<span data-ttu-id="c51fa-235">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="c51fa-235">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="c51fa-236">Definizione</span><span class="sxs-lookup"><span data-stu-id="c51fa-236">Definition</span></span>

<span data-ttu-id="c51fa-237">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="c51fa-237">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="c51fa-238">L'espressione regolare `Regex_ireland_eu_mobile_number` consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="c51fa-238">The regular expression  `Regex_ireland_eu_mobile_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="c51fa-239">L'espressione regolare `Regex_ireland_eu_formatted_mobile_number` consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="c51fa-239">The regular expression  `Regex_ireland_eu_formatted_mobile_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="c51fa-240">Una parola chiave da `Keywords_ireland_eu_mobile_number` viene trovato.</span><span class="sxs-lookup"><span data-stu-id="c51fa-240">A keyword from  `Keywords_ireland_eu_mobile_number` is found.</span></span> 
    
```
 
<Entity id="a56a0418-136a-41ea-a337-4d0388b28e69" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_ireland_eu_mobile_number"/>
          <Match idRef="Keywords_ireland_eu_mobile_number" />
        </Pattern>
<!-- Strictly formatted patterns without mandatory corroborative evidence -->
<Pattern confidenceLevel="75">
<IdMatch idRef="Regex_ireland_eu_formatted_mobile_number" />
          </Pattern>
</Entity>
```

## <a name="italy"></a><span data-ttu-id="c51fa-241">Italia</span><span class="sxs-lookup"><span data-stu-id="c51fa-241">Italy</span></span>

### <a name="pattern"></a><span data-ttu-id="c51fa-242">Modello</span><span class="sxs-lookup"><span data-stu-id="c51fa-242">Pattern</span></span>

-  <span data-ttu-id="c51fa-243">Cifre</span><span class="sxs-lookup"><span data-stu-id="c51fa-243">Digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="c51fa-244">Checksum</span><span class="sxs-lookup"><span data-stu-id="c51fa-244">Checksum</span></span>

<span data-ttu-id="c51fa-245">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="c51fa-245">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="c51fa-246">Definizione</span><span class="sxs-lookup"><span data-stu-id="c51fa-246">Definition</span></span>

<span data-ttu-id="c51fa-247">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="c51fa-247">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="c51fa-248">L'espressione regolare `Regex_italy_eu_mobile_number` consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="c51fa-248">The regular expression  `Regex_italy_eu_mobile_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="c51fa-249">L'espressione regolare `Regex_italy_eu_formatted_mobile_number` consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="c51fa-249">The regular expression  `Regex_italy_eu_formatted_mobile_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="c51fa-250">Una parola chiave da `Keywords_italy_eu_mobile_number` viene trovato.</span><span class="sxs-lookup"><span data-stu-id="c51fa-250">A keyword from  `Keywords_italy_eu_mobile_number` is found.</span></span> 
    
```
 
<Entity id="a56a0418-136a-41ea-a337-4d0388b28e69" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_italy_eu_mobile_number"/>
          <Match idRef="Keywords_italy_eu_mobile_number" />
        </Pattern>
<!-- Strictly formatted patterns without mandatory corroborative evidence -->
<Pattern confidenceLevel="75">
<IdMatch idRef="Regex_italy_eu_formatted_mobile_number" />
          </Pattern>
</Entity>
```

## <a name="latvia"></a><span data-ttu-id="c51fa-251">Lettonia</span><span class="sxs-lookup"><span data-stu-id="c51fa-251">Latvia</span></span>

### <a name="pattern"></a><span data-ttu-id="c51fa-252">Modello</span><span class="sxs-lookup"><span data-stu-id="c51fa-252">Pattern</span></span>

-  <span data-ttu-id="c51fa-253">Cifre</span><span class="sxs-lookup"><span data-stu-id="c51fa-253">Digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="c51fa-254">Checksum</span><span class="sxs-lookup"><span data-stu-id="c51fa-254">Checksum</span></span>

<span data-ttu-id="c51fa-255">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="c51fa-255">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="c51fa-256">Definizione</span><span class="sxs-lookup"><span data-stu-id="c51fa-256">Definition</span></span>

<span data-ttu-id="c51fa-257">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="c51fa-257">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="c51fa-258">L'espressione regolare `Regex_latvia_eu_mobile_number` consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="c51fa-258">The regular expression  `Regex_latvia_eu_mobile_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="c51fa-259">L'espressione regolare `Regex_latvia_eu_formatted_mobile_number` consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="c51fa-259">The regular expression  `Regex_latvia_eu_formatted_mobile_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="c51fa-260">Una parola chiave da `Keywords_latvia_eu_mobile_number` viene trovato.</span><span class="sxs-lookup"><span data-stu-id="c51fa-260">A keyword from  `Keywords_latvia_eu_mobile_number` is found.</span></span> 
    
```
 
<Entity id="a56a0418-136a-41ea-a337-4d0388b28e69" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_latvia_eu_mobile_number"/>
          <Match idRef="Keywords_latvia_eu_mobile_number" />
        </Pattern>
<Pattern confidenceLevel="75">
<IdMatch idRef="Regex_latvia_eu_formatted_mobile_number" />
          </Pattern>
</Entity>
```

## <a name="lithuania"></a><span data-ttu-id="c51fa-261">Lituania</span><span class="sxs-lookup"><span data-stu-id="c51fa-261">Lithuania</span></span>

### <a name="pattern"></a><span data-ttu-id="c51fa-262">Modello</span><span class="sxs-lookup"><span data-stu-id="c51fa-262">Pattern</span></span>

-  <span data-ttu-id="c51fa-263">Cifre</span><span class="sxs-lookup"><span data-stu-id="c51fa-263">Digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="c51fa-264">Checksum</span><span class="sxs-lookup"><span data-stu-id="c51fa-264">Checksum</span></span>

<span data-ttu-id="c51fa-265">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="c51fa-265">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="c51fa-266">Definizione</span><span class="sxs-lookup"><span data-stu-id="c51fa-266">Definition</span></span>

<span data-ttu-id="c51fa-267">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="c51fa-267">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="c51fa-268">L'espressione regolare `Regex_lithuania_eu_mobile_number` consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="c51fa-268">The regular expression  `Regex_lithuania_eu_mobile_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="c51fa-269">L'espressione regolare `Regex_lithuania_eu_formatted_mobile_number` consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="c51fa-269">The regular expression  `Regex_lithuania_eu_formatted_mobile_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="c51fa-270">Una parola chiave da `Keywords_lithuania_eu_mobile_number` viene trovato.</span><span class="sxs-lookup"><span data-stu-id="c51fa-270">A keyword from  `Keywords_lithuania_eu_mobile_number` is found.</span></span> 
    
```
 
<Entity id="a56a0418-136a-41ea-a337-4d0388b28e69" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_lithuania_eu_mobile_number"/>
          <Match idRef="Keywords_lithuania_eu_mobile_number" />
        </Pattern>
<Pattern confidenceLevel="75">
<IdMatch idRef="Regex_lithuania_eu_formatted_mobile_number" />
          </Pattern>
</Entity>
```

## <a name="luxemburg"></a><span data-ttu-id="c51fa-271">Lussemburgo</span><span class="sxs-lookup"><span data-stu-id="c51fa-271">Luxemburg</span></span>

### <a name="pattern"></a><span data-ttu-id="c51fa-272">Modello</span><span class="sxs-lookup"><span data-stu-id="c51fa-272">Pattern</span></span>

-  <span data-ttu-id="c51fa-273">Cifre</span><span class="sxs-lookup"><span data-stu-id="c51fa-273">Digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="c51fa-274">Checksum</span><span class="sxs-lookup"><span data-stu-id="c51fa-274">Checksum</span></span>

<span data-ttu-id="c51fa-275">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="c51fa-275">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="c51fa-276">Definizione</span><span class="sxs-lookup"><span data-stu-id="c51fa-276">Definition</span></span>

<span data-ttu-id="c51fa-277">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="c51fa-277">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="c51fa-278">L'espressione regolare `Regex_luxumburg_eu_mobile_number` consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="c51fa-278">The regular expression  `Regex_luxumburg_eu_mobile_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="c51fa-279">L'espressione regolare `Regex_luxumburg_eu_formatted_mobile_number` consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="c51fa-279">The regular expression  `Regex_luxumburg_eu_formatted_mobile_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="c51fa-280">Una parola chiave da `Keywords_luxumburg_eu_mobile_number` viene trovato.</span><span class="sxs-lookup"><span data-stu-id="c51fa-280">A keyword from  `Keywords_luxumburg_eu_mobile_number` is found.</span></span> 
    
```
 
<Entity id="a56a0418-136a-41ea-a337-4d0388b28e69" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_luxumburg_eu_mobile_number"/>
          <Match idRef="Keywords_luxumburg_eu_mobile_number" />
        </Pattern>
<Pattern confidenceLevel="75">
<IdMatch idRef="Regex_luxumburg_eu_formatted_mobile_number" />
          </Pattern>
</Entity>
```

## <a name="malta"></a><span data-ttu-id="c51fa-281">Malta</span><span class="sxs-lookup"><span data-stu-id="c51fa-281">Malta</span></span>

### <a name="pattern"></a><span data-ttu-id="c51fa-282">Modello</span><span class="sxs-lookup"><span data-stu-id="c51fa-282">Pattern</span></span>

-  <span data-ttu-id="c51fa-283">Cifre</span><span class="sxs-lookup"><span data-stu-id="c51fa-283">Digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="c51fa-284">Checksum</span><span class="sxs-lookup"><span data-stu-id="c51fa-284">Checksum</span></span>

<span data-ttu-id="c51fa-285">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="c51fa-285">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="c51fa-286">Definizione</span><span class="sxs-lookup"><span data-stu-id="c51fa-286">Definition</span></span>

<span data-ttu-id="c51fa-287">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="c51fa-287">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="c51fa-288">L'espressione regolare `Regex_malta_eu_mobile_number` consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="c51fa-288">The regular expression  `Regex_malta_eu_mobile_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="c51fa-289">L'espressione regolare `Regex_malta_eu_formatted_mobile_number` consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="c51fa-289">The regular expression  `Regex_malta_eu_formatted_mobile_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="c51fa-290">Una parola chiave da `Keywords_malta_eu_mobile_number` viene trovato.</span><span class="sxs-lookup"><span data-stu-id="c51fa-290">A keyword from  `Keywords_malta_eu_mobile_number` is found.</span></span> 
    
```
 
<Entity id="a56a0418-136a-41ea-a337-4d0388b28e69" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_malta_eu_mobile_number"/>
          <Match idRef="Keywords_malta_eu_mobile_number" />
        </Pattern>
<!-- Strictly formatted patterns without mandatory corroborative evidence -->
<Pattern confidenceLevel="75">
<IdMatch idRef="Regex_malta_eu_formatted_mobile_number" />
          </Pattern>
</Entity>
```

## <a name="netherlands"></a><span data-ttu-id="c51fa-291">Paesi Bassi</span><span class="sxs-lookup"><span data-stu-id="c51fa-291">Netherlands</span></span>

### <a name="pattern"></a><span data-ttu-id="c51fa-292">Modello</span><span class="sxs-lookup"><span data-stu-id="c51fa-292">Pattern</span></span>

-  <span data-ttu-id="c51fa-293">Cifre</span><span class="sxs-lookup"><span data-stu-id="c51fa-293">Digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="c51fa-294">Checksum</span><span class="sxs-lookup"><span data-stu-id="c51fa-294">Checksum</span></span>

<span data-ttu-id="c51fa-295">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="c51fa-295">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="c51fa-296">Definizione</span><span class="sxs-lookup"><span data-stu-id="c51fa-296">Definition</span></span>

<span data-ttu-id="c51fa-297">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="c51fa-297">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="c51fa-298">L'espressione regolare `Regex_netherlands_eu_mobile_number` consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="c51fa-298">The regular expression  `Regex_netherlands_eu_mobile_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="c51fa-299">L'espressione regolare `Regex_netherlands_eu_formatted_mobile_number` consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="c51fa-299">The regular expression  `Regex_netherlands_eu_formatted_mobile_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="c51fa-300">Una parola chiave da `Keywords_netherlands_eu_mobile_number` viene trovato.</span><span class="sxs-lookup"><span data-stu-id="c51fa-300">A keyword from  `Keywords_netherlands_eu_mobile_number` is found.</span></span> 
    
```
<Entity id="a56a0418-136a-41ea-a337-4d0388b28e69" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_netherlands_eu_mobile_number"/>
          <Match idRef="Keywords_netherlands_eu_mobile_number" />
        </Pattern>
<!-- Strictly formatted patterns without mandatory corroborative evidence -->
<Pattern confidenceLevel="75">
<IdMatch idRef="Regex_netherlands_eu_formatted_mobile_number" />
          </Pattern>
</Entity>
```

## <a name="poland"></a><span data-ttu-id="c51fa-301">Polonia</span><span class="sxs-lookup"><span data-stu-id="c51fa-301">Poland</span></span>

### <a name="pattern"></a><span data-ttu-id="c51fa-302">Modello</span><span class="sxs-lookup"><span data-stu-id="c51fa-302">Pattern</span></span>

-  <span data-ttu-id="c51fa-303">Cifre</span><span class="sxs-lookup"><span data-stu-id="c51fa-303">Digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="c51fa-304">Checksum</span><span class="sxs-lookup"><span data-stu-id="c51fa-304">Checksum</span></span>

<span data-ttu-id="c51fa-305">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="c51fa-305">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="c51fa-306">Definizione</span><span class="sxs-lookup"><span data-stu-id="c51fa-306">Definition</span></span>

<span data-ttu-id="c51fa-307">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="c51fa-307">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="c51fa-308">L'espressione regolare `Regex_poland_eu_mobile_number` consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="c51fa-308">The regular expression  `Regex_poland_eu_mobile_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="c51fa-309">L'espressione regolare `Regex_poland_eu_formatted_mobile_number` consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="c51fa-309">The regular expression  `Regex_poland_eu_formatted_mobile_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="c51fa-310">Una parola chiave da `Keywords_poland_eu_mobile_number` viene trovato.</span><span class="sxs-lookup"><span data-stu-id="c51fa-310">A keyword from  `Keywords_poland_eu_mobile_number` is found.</span></span> 
    
```
 
<Entity id="a56a0418-136a-41ea-a337-4d0388b28e69" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_poland_eu_mobile_number"/>
          <Match idRef="Keywords_poland_eu_mobile_number" />
        </Pattern>
<!-- Strictly formatted patterns without mandatory corroborative evidence -->
<Pattern confidenceLevel="75">
<IdMatch idRef="Regex_poland_eu_formatted_mobile_number" />
          </Pattern>
</Entity>
```

## <a name="portugal"></a><span data-ttu-id="c51fa-311">Portogallo</span><span class="sxs-lookup"><span data-stu-id="c51fa-311">Portugal</span></span>

### <a name="pattern"></a><span data-ttu-id="c51fa-312">Modello</span><span class="sxs-lookup"><span data-stu-id="c51fa-312">Pattern</span></span>

-  <span data-ttu-id="c51fa-313">Cifre</span><span class="sxs-lookup"><span data-stu-id="c51fa-313">Digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="c51fa-314">Checksum</span><span class="sxs-lookup"><span data-stu-id="c51fa-314">Checksum</span></span>

<span data-ttu-id="c51fa-315">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="c51fa-315">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="c51fa-316">Definizione</span><span class="sxs-lookup"><span data-stu-id="c51fa-316">Definition</span></span>

<span data-ttu-id="c51fa-317">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="c51fa-317">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="c51fa-318">L'espressione regolare `Regex_portugal_eu_mobile_number` consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="c51fa-318">The regular expression  `Regex_portugal_eu_mobile_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="c51fa-319">L'espressione regolare `Regex_portugal_eu_formatted_mobile_number` consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="c51fa-319">The regular expression  `Regex_portugal_eu_formatted_mobile_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="c51fa-320">Una parola chiave da `Keywords_portugal_eu_mobile_number` viene trovato.</span><span class="sxs-lookup"><span data-stu-id="c51fa-320">A keyword from  `Keywords_portugal_eu_mobile_number` is found.</span></span> 
    
```
 
<Entity id="a56a0418-136a-41ea-a337-4d0388b28e69" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_portugal_eu_mobile_number"/>
          <Match idRef="Keywords_portugal_eu_mobile_number" />
        </Pattern>
<Pattern confidenceLevel="75">
<IdMatch idRef="Regex_portugal_eu_formatted_mobile_number" />
          </Pattern>
</Entity>
```

## <a name="romania"></a><span data-ttu-id="c51fa-321">Romania</span><span class="sxs-lookup"><span data-stu-id="c51fa-321">Romania</span></span>

### <a name="pattern"></a><span data-ttu-id="c51fa-322">Modello</span><span class="sxs-lookup"><span data-stu-id="c51fa-322">Pattern</span></span>

-  <span data-ttu-id="c51fa-323">Cifre</span><span class="sxs-lookup"><span data-stu-id="c51fa-323">Digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="c51fa-324">Checksum</span><span class="sxs-lookup"><span data-stu-id="c51fa-324">Checksum</span></span>

<span data-ttu-id="c51fa-325">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="c51fa-325">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="c51fa-326">Definizione</span><span class="sxs-lookup"><span data-stu-id="c51fa-326">Definition</span></span>

<span data-ttu-id="c51fa-327">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="c51fa-327">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="c51fa-328">L'espressione regolare `Regex_romania_eu_mobile_number` consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="c51fa-328">The regular expression  `Regex_romania_eu_mobile_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="c51fa-329">L'espressione regolare `Regex_romania_eu_formatted_mobile_number` consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="c51fa-329">The regular expression  `Regex_romania_eu_formatted_mobile_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="c51fa-330">Una parola chiave da `Keywords_romania_eu_mobile_number` viene trovato.</span><span class="sxs-lookup"><span data-stu-id="c51fa-330">A keyword from  `Keywords_romania_eu_mobile_number` is found.</span></span> 
    
```
 
<Entity id="a56a0418-136a-41ea-a337-4d0388b28e69" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_romania_eu_mobile_number"/>
          <Match idRef="Keywords_romania_eu_mobile_number" />
        </Pattern>
<Pattern confidenceLevel="75">
<IdMatch idRef="Regex_romania_eu_formatted_mobile_number" />
          </Pattern>
</Entity>
```

## <a name="slovakia"></a><span data-ttu-id="c51fa-331">Slovacchia</span><span class="sxs-lookup"><span data-stu-id="c51fa-331">Slovakia</span></span>

### <a name="pattern"></a><span data-ttu-id="c51fa-332">Modello</span><span class="sxs-lookup"><span data-stu-id="c51fa-332">Pattern</span></span>

-  <span data-ttu-id="c51fa-333">Cifre</span><span class="sxs-lookup"><span data-stu-id="c51fa-333">Digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="c51fa-334">Checksum</span><span class="sxs-lookup"><span data-stu-id="c51fa-334">Checksum</span></span>

<span data-ttu-id="c51fa-335">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="c51fa-335">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="c51fa-336">Definizione</span><span class="sxs-lookup"><span data-stu-id="c51fa-336">Definition</span></span>

<span data-ttu-id="c51fa-337">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="c51fa-337">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="c51fa-338">L'espressione regolare `Regex_slovakia_eu_mobile_number` consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="c51fa-338">The regular expression  `Regex_slovakia_eu_mobile_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="c51fa-339">L'espressione regolare `Regex_slovakia_eu_formatted_mobile_number` consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="c51fa-339">The regular expression  `Regex_slovakia_eu_formatted_mobile_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="c51fa-340">Una parola chiave da `Keywords_slovakia_eu_mobile_number` viene trovato.</span><span class="sxs-lookup"><span data-stu-id="c51fa-340">A keyword from  `Keywords_slovakia_eu_mobile_number` is found.</span></span> 
    
```
 
<Entity id="a56a0418-136a-41ea-a337-4d0388b28e69" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovakia_eu_mobile_number"/>
          <Match idRef="Keywords_slovakia_eu_mobile_number" />
        </Pattern>
<Pattern confidenceLevel="75">
<IdMatch idRef="Regex_slovakia_eu_formatted_mobile_number" />
          </Pattern>
</Entity>
```

## <a name="slovenia"></a><span data-ttu-id="c51fa-341">Slovenia</span><span class="sxs-lookup"><span data-stu-id="c51fa-341">Slovenia</span></span>

### <a name="pattern"></a><span data-ttu-id="c51fa-342">Modello</span><span class="sxs-lookup"><span data-stu-id="c51fa-342">Pattern</span></span>

-  <span data-ttu-id="c51fa-343">Cifre</span><span class="sxs-lookup"><span data-stu-id="c51fa-343">Digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="c51fa-344">Checksum</span><span class="sxs-lookup"><span data-stu-id="c51fa-344">Checksum</span></span>

<span data-ttu-id="c51fa-345">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="c51fa-345">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="c51fa-346">Definizione</span><span class="sxs-lookup"><span data-stu-id="c51fa-346">Definition</span></span>

<span data-ttu-id="c51fa-347">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="c51fa-347">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="c51fa-348">L'espressione regolare `Regex_slovenia_eu_mobile_number` consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="c51fa-348">The regular expression  `Regex_slovenia_eu_mobile_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="c51fa-349">L'espressione regolare `Regex_slovenia_eu_formatted_mobile_number` consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="c51fa-349">The regular expression  `Regex_slovenia_eu_formatted_mobile_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="c51fa-350">Una parola chiave da `Keywords_slovenia_eu_mobile_number` viene trovato.</span><span class="sxs-lookup"><span data-stu-id="c51fa-350">A keyword from  `Keywords_slovenia_eu_mobile_number` is found.</span></span> 
    
```
<Entity id="a56a0418-136a-41ea-a337-4d0388b28e69" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovenia_eu_mobile_number"/>
          <Match idRef="Keywords_slovenia_eu_mobile_number" />
        </Pattern>
<Pattern confidenceLevel="75">
<IdMatch idRef="Regex_slovenia_eu_formatted_mobile_number" />
          </Pattern>
</Entity>
```

## <a name="spain"></a><span data-ttu-id="c51fa-351">Spagna</span><span class="sxs-lookup"><span data-stu-id="c51fa-351">Spain</span></span>

### <a name="pattern"></a><span data-ttu-id="c51fa-352">Modello</span><span class="sxs-lookup"><span data-stu-id="c51fa-352">Pattern</span></span>

-  <span data-ttu-id="c51fa-353">Cifre</span><span class="sxs-lookup"><span data-stu-id="c51fa-353">Digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="c51fa-354">Checksum</span><span class="sxs-lookup"><span data-stu-id="c51fa-354">Checksum</span></span>

<span data-ttu-id="c51fa-355">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="c51fa-355">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="c51fa-356">Definizione</span><span class="sxs-lookup"><span data-stu-id="c51fa-356">Definition</span></span>

<span data-ttu-id="c51fa-357">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="c51fa-357">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="c51fa-358">L'espressione regolare `Regex_spain_eu_mobile_number` consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="c51fa-358">The regular expression  `Regex_spain_eu_mobile_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="c51fa-359">L'espressione regolare `Regex_spain_eu_formatted_mobile_number` consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="c51fa-359">The regular expression  `Regex_spain_eu_formatted_mobile_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="c51fa-360">Una parola chiave da `Keywords_spain_eu_mobile_number` viene trovato.</span><span class="sxs-lookup"><span data-stu-id="c51fa-360">A keyword from  `Keywords_spain_eu_mobile_number` is found.</span></span> 
    
```
 
<Entity id="a56a0418-136a-41ea-a337-4d0388b28e69" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_spain_eu_mobile_number"/>
          <Match idRef="Keywords_spain_eu_mobile_number" />
        </Pattern>
<Pattern confidenceLevel="75">
<IdMatch idRef="Regex_spain_eu_formatted_mobile_number" />
          </Pattern>
</Entity>
```

## <a name="sweden"></a><span data-ttu-id="c51fa-361">Svezia</span><span class="sxs-lookup"><span data-stu-id="c51fa-361">Sweden</span></span>

### <a name="pattern"></a><span data-ttu-id="c51fa-362">Modello</span><span class="sxs-lookup"><span data-stu-id="c51fa-362">Pattern</span></span>

-  <span data-ttu-id="c51fa-363">Cifre</span><span class="sxs-lookup"><span data-stu-id="c51fa-363">Digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="c51fa-364">Checksum</span><span class="sxs-lookup"><span data-stu-id="c51fa-364">Checksum</span></span>

<span data-ttu-id="c51fa-365">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="c51fa-365">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="c51fa-366">Definizione</span><span class="sxs-lookup"><span data-stu-id="c51fa-366">Definition</span></span>

<span data-ttu-id="c51fa-367">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="c51fa-367">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="c51fa-368">L'espressione regolare `Regex_sweden_eu_mobile_number` consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="c51fa-368">The regular expression  `Regex_sweden_eu_mobile_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="c51fa-369">L'espressione regolare `Regex_sweden_eu_formatted_mobile_number` consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="c51fa-369">The regular expression  `Regex_sweden_eu_formatted_mobile_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="c51fa-370">Una parola chiave da `Keywords_sweden_eu_mobile_number` viene trovato.</span><span class="sxs-lookup"><span data-stu-id="c51fa-370">A keyword from  `Keywords_sweden_eu_mobile_number` is found.</span></span> 
    
```
 
<Entity id="a56a0418-136a-41ea-a337-4d0388b28e69" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_sweden_eu_mobile_number"/>
          <Match idRef="Keywords_sweden_eu_mobile_number" />
        </Pattern>
<Pattern confidenceLevel="75">
<IdMatch idRef="Regex_sweden_eu_formatted_mobile_number" />
          </Pattern>
</Entity>
```

## <a name="uk"></a><span data-ttu-id="c51fa-371">REGNO UNITO</span><span class="sxs-lookup"><span data-stu-id="c51fa-371">UK</span></span>

### <a name="pattern"></a><span data-ttu-id="c51fa-372">Modello</span><span class="sxs-lookup"><span data-stu-id="c51fa-372">Pattern</span></span>

-  <span data-ttu-id="c51fa-373">Cifre</span><span class="sxs-lookup"><span data-stu-id="c51fa-373">Digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="c51fa-374">Checksum</span><span class="sxs-lookup"><span data-stu-id="c51fa-374">Checksum</span></span>

<span data-ttu-id="c51fa-375">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="c51fa-375">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="c51fa-376">Definizione</span><span class="sxs-lookup"><span data-stu-id="c51fa-376">Definition</span></span>

<span data-ttu-id="c51fa-377">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="c51fa-377">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="c51fa-378">L'espressione regolare `Regex_uk_eu_mobile_number` consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="c51fa-378">The regular expression  `Regex_uk_eu_mobile_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="c51fa-379">L'espressione regolare `Regex_uk_eu_formatted_mobile_number` consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="c51fa-379">The regular expression  `Regex_uk_eu_formatted_mobile_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="c51fa-380">Una parola chiave da `Keywords_uk_eu_mobile_number` viene trovato.</span><span class="sxs-lookup"><span data-stu-id="c51fa-380">A keyword from  `Keywords_uk_eu_mobile_number` is found.</span></span> 
    
```
 
<Entity id="a56a0418-136a-41ea-a337-4d0388b28e69" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_uk_eu_mobile_number"/>
          <Match idRef="Keywords_uk_eu_mobile_number" />
        </Pattern>
<Pattern confidenceLevel="75">
<IdMatch idRef="Regex_uk_eu_formatted_mobile_number" />
          </Pattern>
</Entity>
```

## <a name="see-also"></a><span data-ttu-id="c51fa-381">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c51fa-381">See also</span></span>

[<span data-ttu-id="c51fa-382">Cosa individuano i tipi di informazioni riservate</span><span class="sxs-lookup"><span data-stu-id="c51fa-382">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)

