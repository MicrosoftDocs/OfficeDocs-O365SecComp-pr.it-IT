---
title: Numero di telefono dell'Unione europea
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 8/17/2018
ms.audience: Admin
ms.topic: reference
ms.service: o365-administration
localization_priority: Normal
ms.assetid: 1c90ca41-1681-46bf-8ad6-6bf4cec5c426
description: Prevenzione perdita dati (DLP) in Office 365 Security &amp; centro conformità include molti tipi di informazioni riservate che si desidera utilizzare i criteri DLP. In questo argomento viene descritto il tipo di informazioni riservate numero di telefono dell'Unione europea.
ms.openlocfilehash: 9dd878e3385312982f9f3a4927205e3ebb27aabb
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/27/2018
ms.locfileid: "22530873"
---
# <a name="eu-phone-number"></a><span data-ttu-id="e4a19-104">Numero di telefono dell'Unione europea</span><span class="sxs-lookup"><span data-stu-id="e4a19-104">EU Phone Number</span></span>

<span data-ttu-id="e4a19-p102">Prevenzione perdita dati (DLP) in Office 365 Security &amp; centro conformità include molti tipi di informazioni riservate che si desidera utilizzare i criteri DLP. In questo argomento viene descritto il tipo di informazioni riservate numero di telefono dell'Unione europea.</span><span class="sxs-lookup"><span data-stu-id="e4a19-p102">Data loss prevention (DLP) in the Office 365 Security &amp; Compliance Center includes many sensitive information types that are ready for you to use in your DLP policies. This topic describes the EU Phone Number sensitive information type.</span></span> 
  
## <a name="austria"></a><span data-ttu-id="e4a19-107">Austria</span><span class="sxs-lookup"><span data-stu-id="e4a19-107">Austria</span></span>

### <a name="format"></a><span data-ttu-id="e4a19-108">Formato</span><span class="sxs-lookup"><span data-stu-id="e4a19-108">Format</span></span>

<span data-ttu-id="e4a19-109">Lunghezza non standard</span><span class="sxs-lookup"><span data-stu-id="e4a19-109">No standard length</span></span>
  
### <a name="pattern"></a><span data-ttu-id="e4a19-110">Modello</span><span class="sxs-lookup"><span data-stu-id="e4a19-110">Pattern</span></span>

- <span data-ttu-id="e4a19-111">Cifre</span><span class="sxs-lookup"><span data-stu-id="e4a19-111">Digits</span></span> 
    
- <span data-ttu-id="e4a19-112">Solo i numeri di telefono cellulare iniziano con la cifra "6"</span><span class="sxs-lookup"><span data-stu-id="e4a19-112">Only mobile phone numbers begin with the digit "6"</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="e4a19-113">Checksum</span><span class="sxs-lookup"><span data-stu-id="e4a19-113">Checksum</span></span>

<span data-ttu-id="e4a19-114">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="e4a19-114">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="e4a19-115">Definizione</span><span class="sxs-lookup"><span data-stu-id="e4a19-115">Definition</span></span>

<span data-ttu-id="e4a19-116">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="e4a19-116">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e4a19-117">L'espressione regolare `Regex_austria_eu_telephone_number_1` consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="e4a19-117">The regular expression  `Regex_austria_eu_telephone_number_1` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="e4a19-118">Una parola chiave da `Keywords_austria_eu_telephone_number` viene trovato.</span><span class="sxs-lookup"><span data-stu-id="e4a19-118">A keyword from  `Keywords_austria_eu_telephone_number` is found.</span></span> 
    
<span data-ttu-id="e4a19-119">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="e4a19-119">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e4a19-120">L'espressione regolare `Regex_austria_eu_telephone_number_2` consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="e4a19-120">The regular expression  `Regex_austria_eu_telephone_number_2` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="e4a19-121">Una parola chiave da `Keywords_austria_eu_telephone_number` viene trovato.</span><span class="sxs-lookup"><span data-stu-id="e4a19-121">A keyword from  `Keywords_austria_eu_telephone_number` is found.</span></span> 
    
```
 <!-- EU Telephone Number -->
<Entity id="eb367e90-d826-40aa-a338-a1fdb3a4d99b" patternsProximity="300" recommendedConfidence="75">
<!-- Loosely formatted patterns with mandatory corroborative evidence -->
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_austria_eu_telephone_number_1" />
          <Match idRef="Keywords_austria_eu_telephone_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_austria_eu_telephone_number_2" />
          <Match idRef="Keywords_austria_eu_telephone_number" />
<!-- Strictly formatted patterns without mandatory corroborative evidence -->
          <Pattern confidenceLevel="75">
            <IdMatch idRef="Regex_austria_eu_formatted_telephone_number_1" />
          </Pattern>
          <Pattern confidenceLevel="75">
            <IdMatch idRef="Regex_austria_eu_formatted_telephone_number_2" />
          </Pattern>
</Entity>
```

## <a name="belgium"></a><span data-ttu-id="e4a19-122">Belgio</span><span class="sxs-lookup"><span data-stu-id="e4a19-122">Belgium</span></span>

### <a name="definition"></a><span data-ttu-id="e4a19-123">Definizione</span><span class="sxs-lookup"><span data-stu-id="e4a19-123">Definition</span></span>

<span data-ttu-id="e4a19-124">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="e4a19-124">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e4a19-125">L'espressione regolare `Regex_belgium_eu_telephone_number_1` consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="e4a19-125">The regular expression  `Regex_belgium_eu_telephone_number_1` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="e4a19-126">Una parola chiave da `Keywords_belgium_eu_telephone_number` viene trovato.</span><span class="sxs-lookup"><span data-stu-id="e4a19-126">A keyword from  `Keywords_belgium_eu_telephone_number` is found.</span></span> 
    
<span data-ttu-id="e4a19-127">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="e4a19-127">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e4a19-128">L'espressione regolare `Regex_belgium_eu_telephone_number_2` consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="e4a19-128">The regular expression  `Regex_belgium_eu_telephone_number_2` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="e4a19-129">Una parola chiave da `Keywords_belgium_eu_telephone_number` viene trovato.</span><span class="sxs-lookup"><span data-stu-id="e4a19-129">A keyword from  `Keywords_belgium_eu_telephone_number` is found.</span></span> 
    
```
 <!-- EU Telephone Number -->
<Entity id="eb367e90-d826-40aa-a338-a1fdb3a4d99b" patternsProximity="300" recommendedConfidence="75">
<!-- Loosely formatted patterns with mandatory corroborative evidence -->
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_belgium_eu_telephone_number_1" />
          <Match idRef="Keywords_belgium_eu_telephone_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_belgium_eu_telephone_number_2" />
          <Match idRef="Keywords_belgium_eu_telephone_number" />
<!-- Strictly formatted patterns without mandatory corroborative evidence -->
          <Pattern confidenceLevel="75">
            <IdMatch idRef="Regex_belgium_eu_formatted_telephone_number_1" />
          </Pattern>
          <Pattern confidenceLevel="75">
            <IdMatch idRef="Regex_belgium_eu_formatted_telephone_number_2" />
          </Pattern></Entity>
```

## <a name="bulgaria"></a><span data-ttu-id="e4a19-130">Bulgaria</span><span class="sxs-lookup"><span data-stu-id="e4a19-130">Bulgaria</span></span>

### <a name="pattern"></a><span data-ttu-id="e4a19-131">Modello</span><span class="sxs-lookup"><span data-stu-id="e4a19-131">Pattern</span></span>

- <span data-ttu-id="e4a19-132">Cifre</span><span class="sxs-lookup"><span data-stu-id="e4a19-132">Digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="e4a19-133">Checksum</span><span class="sxs-lookup"><span data-stu-id="e4a19-133">Checksum</span></span>

<span data-ttu-id="e4a19-134">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="e4a19-134">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="e4a19-135">Definizione</span><span class="sxs-lookup"><span data-stu-id="e4a19-135">Definition</span></span>

<span data-ttu-id="e4a19-136">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="e4a19-136">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e4a19-137">L'espressione regolare `Regex_bulgaria_eu_telephone_number` consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="e4a19-137">The regular expression  `Regex_bulgaria_eu_telephone_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="e4a19-138">Una parola chiave da `Keywords_bulgaria_eu_telephone_number` viene trovato.</span><span class="sxs-lookup"><span data-stu-id="e4a19-138">A keyword from  `Keywords_bulgaria_eu_telephone_number` is found.</span></span> 
    
<span data-ttu-id="e4a19-139">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="e4a19-139">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e4a19-140">L'espressione regolare `Regex_bulgaria_eu_telephone_number` consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="e4a19-140">The regular expression  `Regex_bulgaria_eu_telephone_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Telephone Number -->
<Entity id="eb367e90-d826-40aa-a338-a1fdb3a4d99b" patternsProximity="300" recommendedConfidence="75">
<!-- Loosely formatted patterns with mandatory corroborative evidence -->
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_bulgaria_eu_telephone_number" />
          <Match idRef="Keywords_bulgaria_eu_telephone_number" />
        </Pattern>
<!-- Strictly formatted patterns without mandatory corroborative evidence -->
          <Pattern confidenceLevel="75">
            <IdMatch idRef="Regex_bulgaria_eu_formatted_telephone_number" />
          </Pattern>
          
</Entity>
```

## <a name="croatia"></a><span data-ttu-id="e4a19-141">Croazia</span><span class="sxs-lookup"><span data-stu-id="e4a19-141">Croatia</span></span>

### <a name="pattern"></a><span data-ttu-id="e4a19-142">Modello</span><span class="sxs-lookup"><span data-stu-id="e4a19-142">Pattern</span></span>

- <span data-ttu-id="e4a19-143">Cifre</span><span class="sxs-lookup"><span data-stu-id="e4a19-143">Digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="e4a19-144">Checksum</span><span class="sxs-lookup"><span data-stu-id="e4a19-144">Checksum</span></span>

<span data-ttu-id="e4a19-145">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="e4a19-145">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="e4a19-146">Definizione</span><span class="sxs-lookup"><span data-stu-id="e4a19-146">Definition</span></span>

<span data-ttu-id="e4a19-147">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="e4a19-147">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e4a19-148">L'espressione regolare `Regex_croatia_eu_telephone_number` consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="e4a19-148">The regular expression  `Regex_croatia_eu_telephone_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="e4a19-149">Una parola chiave da `Keywords_croatia_eu_telephone_number` viene trovato.</span><span class="sxs-lookup"><span data-stu-id="e4a19-149">A keyword from  `Keywords_croatia_eu_telephone_number` is found.</span></span> 
    
<span data-ttu-id="e4a19-150">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="e4a19-150">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e4a19-151">L'espressione regolare `Regex_croatia_eu_telephone_number` consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="e4a19-151">The regular expression  `Regex_croatia_eu_telephone_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Telephone Number -->
<Entity id="eb367e90-d826-40aa-a338-a1fdb3a4d99b" patternsProximity="300" recommendedConfidence="75">
<!-- Loosely formatted patterns with mandatory corroborative evidence -->
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_croatia_eu_telephone_number" />
          <Match idRef="Keywords_croatia_eu_telephone_number" />
        </Pattern>
<!-- Strictly formatted patterns without mandatory corroborative evidence -->
          <Pattern confidenceLevel="75">
            <IdMatch idRef="Regex_croatia_eu_formatted_telephone_number" />
          </Pattern>
         </Entity>
```

## <a name="cyprus"></a><span data-ttu-id="e4a19-152">Cipro</span><span class="sxs-lookup"><span data-stu-id="e4a19-152">Cyprus</span></span>

### <a name="pattern"></a><span data-ttu-id="e4a19-153">Modello</span><span class="sxs-lookup"><span data-stu-id="e4a19-153">Pattern</span></span>

- <span data-ttu-id="e4a19-154">Cifre</span><span class="sxs-lookup"><span data-stu-id="e4a19-154">Digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="e4a19-155">Checksum</span><span class="sxs-lookup"><span data-stu-id="e4a19-155">Checksum</span></span>

<span data-ttu-id="e4a19-156">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="e4a19-156">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="e4a19-157">Definizione</span><span class="sxs-lookup"><span data-stu-id="e4a19-157">Definition</span></span>

<span data-ttu-id="e4a19-158">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="e4a19-158">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e4a19-159">L'espressione regolare `Regex_cyprus_eu_telephone_number` consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="e4a19-159">The regular expression  `Regex_cyprus_eu_telephone_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="e4a19-160">Una parola chiave da `Keywords_cyprus_eu_telephone_number` viene trovato.</span><span class="sxs-lookup"><span data-stu-id="e4a19-160">A keyword from  `Keywords_cyprus_eu_telephone_number` is found.</span></span> 
    
<span data-ttu-id="e4a19-161">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="e4a19-161">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e4a19-162">L'espressione regolare `Regex_cyprus_eu_telephone_number` consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="e4a19-162">The regular expression  `Regex_cyprus_eu_telephone_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Telephone Number -->
<Entity id="eb367e90-d826-40aa-a338-a1fdb3a4d99b" patternsProximity="300" recommendedConfidence="75">
<!-- Loosely formatted patterns with mandatory corroborative evidence -->
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_cyprus_eu_telephone_number" />
          <Match idRef="Keywords_cyprus_eu_telephone_number" />
        </Pattern>
<!-- Strictly formatted patterns without mandatory corroborative evidence -->
          <Pattern confidenceLevel="75">
            <IdMatch idRef="Regex_cyprus_eu_formatted_telephone_number" />
            </Pattern>
</Entity>
```

## <a name="czech-republic"></a><span data-ttu-id="e4a19-163">Repubblica Ceca</span><span class="sxs-lookup"><span data-stu-id="e4a19-163">Czech Republic</span></span>

### <a name="pattern"></a><span data-ttu-id="e4a19-164">Modello</span><span class="sxs-lookup"><span data-stu-id="e4a19-164">Pattern</span></span>

- <span data-ttu-id="e4a19-165">Cifre</span><span class="sxs-lookup"><span data-stu-id="e4a19-165">Digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="e4a19-166">Checksum</span><span class="sxs-lookup"><span data-stu-id="e4a19-166">Checksum</span></span>

<span data-ttu-id="e4a19-167">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="e4a19-167">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="e4a19-168">Definizione</span><span class="sxs-lookup"><span data-stu-id="e4a19-168">Definition</span></span>

<span data-ttu-id="e4a19-169">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="e4a19-169">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e4a19-170">L'espressione regolare `Regex_czech_republic_eu_telephone_number` consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="e4a19-170">The regular expression  `Regex_czech_republic_eu_telephone_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="e4a19-171">Una parola chiave da `Keywords_czech_republic_eu_telephone_number` viene trovato.</span><span class="sxs-lookup"><span data-stu-id="e4a19-171">A keyword from  `Keywords_czech_republic_eu_telephone_number` is found.</span></span> 
    
<span data-ttu-id="e4a19-172">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="e4a19-172">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e4a19-173">L'espressione regolare `Regex_czech_republic_eu_telephone_number` consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="e4a19-173">The regular expression  `Regex_czech_republic_eu_telephone_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Telephone Number -->
<Entity id="eb367e90-d826-40aa-a338-a1fdb3a4d99b" patternsProximity="300" recommendedConfidence="75">
<!-- Loosely formatted patterns with mandatory corroborative evidence -->
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_czech_republic_eu_telephone_number" />
          <Match idRef="Keywords_czech_republic_eu_telephone_number" />
        </Pattern>
<!-- Strictly formatted patterns without mandatory corroborative evidence -->
          <Pattern confidenceLevel="75">
            <IdMatch idRef="Regex_czech_republic_eu_formatted_telephone_number" />
          </Pattern>
        </Entity>
```

## <a name="denmark"></a><span data-ttu-id="e4a19-174">Danimarca</span><span class="sxs-lookup"><span data-stu-id="e4a19-174">Denmark</span></span>

### <a name="pattern"></a><span data-ttu-id="e4a19-175">Modello</span><span class="sxs-lookup"><span data-stu-id="e4a19-175">Pattern</span></span>

- <span data-ttu-id="e4a19-176">Cifre</span><span class="sxs-lookup"><span data-stu-id="e4a19-176">Digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="e4a19-177">Checksum</span><span class="sxs-lookup"><span data-stu-id="e4a19-177">Checksum</span></span>

<span data-ttu-id="e4a19-178">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="e4a19-178">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="e4a19-179">Definizione</span><span class="sxs-lookup"><span data-stu-id="e4a19-179">Definition</span></span>

<span data-ttu-id="e4a19-180">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="e4a19-180">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e4a19-181">L'espressione regolare `Regex_denmark_eu_telephone_number` consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="e4a19-181">The regular expression  `Regex_denmark_eu_telephone_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="e4a19-182">Una parola chiave da `Keywords_denmark_eu_telephone_number` viene trovato.</span><span class="sxs-lookup"><span data-stu-id="e4a19-182">A keyword from  `Keywords_denmark_eu_telephone_number` is found.</span></span> 
    
<span data-ttu-id="e4a19-183">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="e4a19-183">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e4a19-184">L'espressione regolare `Regex_denmark_eu_telephone_number` consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="e4a19-184">The regular expression  `Regex_denmark_eu_telephone_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Telephone Number -->
<Entity id="eb367e90-d826-40aa-a338-a1fdb3a4d99b" patternsProximity="300" recommendedConfidence="75">
<!-- Loosely formatted patterns with mandatory corroborative evidence -->
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_denmark_eu_telephone_number" />
          <Match idRef="Keywords_denmark_eu_telephone_number" />
        </Pattern>
<!-- Strictly formatted patterns without mandatory corroborative evidence -->
          <Pattern confidenceLevel="75">
            <IdMatch idRef="Regex_denmark_eu_formatted_telephone_number" />
          </Pattern>
          </Entity>
```

## <a name="estonia"></a><span data-ttu-id="e4a19-185">Estonia</span><span class="sxs-lookup"><span data-stu-id="e4a19-185">Estonia</span></span>

### <a name="pattern"></a><span data-ttu-id="e4a19-186">Modello</span><span class="sxs-lookup"><span data-stu-id="e4a19-186">Pattern</span></span>

- <span data-ttu-id="e4a19-187">Cifre</span><span class="sxs-lookup"><span data-stu-id="e4a19-187">Digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="e4a19-188">Checksum</span><span class="sxs-lookup"><span data-stu-id="e4a19-188">Checksum</span></span>

<span data-ttu-id="e4a19-189">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="e4a19-189">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="e4a19-190">Definizione</span><span class="sxs-lookup"><span data-stu-id="e4a19-190">Definition</span></span>

<span data-ttu-id="e4a19-191">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="e4a19-191">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e4a19-192">L'espressione regolare `Regex_estonia_eu_telephone_number` consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="e4a19-192">The regular expression  `Regex_estonia_eu_telephone_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="e4a19-193">Una parola chiave da `Keywords_estonia_eu_telephone_number` viene trovato.</span><span class="sxs-lookup"><span data-stu-id="e4a19-193">A keyword from  `Keywords_estonia_eu_telephone_number` is found.</span></span> 
    
<span data-ttu-id="e4a19-194">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="e4a19-194">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e4a19-195">L'espressione regolare `Regex_estonia_eu_telephone_number` consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="e4a19-195">The regular expression  `Regex_estonia_eu_telephone_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Telephone Number -->
<Entity id="eb367e90-d826-40aa-a338-a1fdb3a4d99b" patternsProximity="300" recommendedConfidence="75">
<!-- Loosely formatted patterns with mandatory corroborative evidence -->
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_estonia_eu_telephone_number" />
          <Match idRef="Keywords_estonia_eu_telephone_number" />
        </Pattern>
<!-- Strictly formatted patterns without mandatory corroborative evidence -->
          <Pattern confidenceLevel="75">
            <IdMatch idRef="Regex_estonia_eu_formatted_telephone_number" />
          </Pattern>
       </Entity>
```

## <a name="finland"></a><span data-ttu-id="e4a19-196">Finlandia</span><span class="sxs-lookup"><span data-stu-id="e4a19-196">Finland</span></span>

### <a name="pattern"></a><span data-ttu-id="e4a19-197">Modello</span><span class="sxs-lookup"><span data-stu-id="e4a19-197">Pattern</span></span>

- <span data-ttu-id="e4a19-198">Cifre</span><span class="sxs-lookup"><span data-stu-id="e4a19-198">Digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="e4a19-199">Checksum</span><span class="sxs-lookup"><span data-stu-id="e4a19-199">Checksum</span></span>

<span data-ttu-id="e4a19-200">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="e4a19-200">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="e4a19-201">Definizione</span><span class="sxs-lookup"><span data-stu-id="e4a19-201">Definition</span></span>

<span data-ttu-id="e4a19-202">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="e4a19-202">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e4a19-203">L'espressione regolare `Regex_finland_eu_telephone_number` consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="e4a19-203">The regular expression  `Regex_finland_eu_telephone_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="e4a19-204">Una parola chiave da `Keywords_finland_eu_telephone_number` viene trovato.</span><span class="sxs-lookup"><span data-stu-id="e4a19-204">A keyword from  `Keywords_finland_eu_telephone_number` is found.</span></span> 
    
<span data-ttu-id="e4a19-205">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="e4a19-205">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e4a19-206">L'espressione regolare `Regex_finland_eu_telephone_number` consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="e4a19-206">The regular expression  `Regex_finland_eu_telephone_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Telephone Number -->
<Entity id="eb367e90-d826-40aa-a338-a1fdb3a4d99b" patternsProximity="300" recommendedConfidence="75">
<!-- Loosely formatted patterns with mandatory corroborative evidence -->
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_finland_eu_telephone_number" />
          <Match idRef="Keywords_finland_eu_telephone_number" />
        </Pattern>
<!-- Strictly formatted patterns without mandatory corroborative evidence -->
          <Pattern confidenceLevel="75">
            <IdMatch idRef="Regex_finland_eu_formatted_telephone_number" />
             </Pattern>
</Entity>
```

## <a name="france"></a><span data-ttu-id="e4a19-207">Francia</span><span class="sxs-lookup"><span data-stu-id="e4a19-207">France</span></span>

### <a name="pattern"></a><span data-ttu-id="e4a19-208">Modello</span><span class="sxs-lookup"><span data-stu-id="e4a19-208">Pattern</span></span>

- <span data-ttu-id="e4a19-209">Cifre</span><span class="sxs-lookup"><span data-stu-id="e4a19-209">Digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="e4a19-210">Checksum</span><span class="sxs-lookup"><span data-stu-id="e4a19-210">Checksum</span></span>

<span data-ttu-id="e4a19-211">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="e4a19-211">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="e4a19-212">Definizione</span><span class="sxs-lookup"><span data-stu-id="e4a19-212">Definition</span></span>

<span data-ttu-id="e4a19-213">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="e4a19-213">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e4a19-214">L'espressione regolare `Regex_france_eu_telephone_number` consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="e4a19-214">The regular expression  `Regex_france_eu_telephone_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="e4a19-215">Una parola chiave da `Keywords_france_eu_telephone_number` viene trovato.</span><span class="sxs-lookup"><span data-stu-id="e4a19-215">A keyword from  `Keywords_france_eu_telephone_number` is found.</span></span> 
    
<span data-ttu-id="e4a19-216">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="e4a19-216">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e4a19-217">L'espressione regolare `Regex_france_eu_telephone_number` consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="e4a19-217">The regular expression  `Regex_france_eu_telephone_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Telephone Number -->
<Entity id="eb367e90-d826-40aa-a338-a1fdb3a4d99b" patternsProximity="300" recommendedConfidence="75">
<!-- Loosely formatted patterns with mandatory corroborative evidence -->
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_france_eu_telephone_number" />
          <Match idRef="Keywords_france_eu_telephone_number" />
        </Pattern>
<!-- Strictly formatted patterns without mandatory corroborative evidence -->
          <Pattern confidenceLevel="75">
            <IdMatch idRef="Regex_france_eu_formatted_telephone_number" />
          </Pattern>
          </Entity>
```

## <a name="germany"></a><span data-ttu-id="e4a19-218">Germania</span><span class="sxs-lookup"><span data-stu-id="e4a19-218">Germany</span></span>

### <a name="pattern"></a><span data-ttu-id="e4a19-219">Modello</span><span class="sxs-lookup"><span data-stu-id="e4a19-219">Pattern</span></span>

- <span data-ttu-id="e4a19-220">Cifre</span><span class="sxs-lookup"><span data-stu-id="e4a19-220">Digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="e4a19-221">Checksum</span><span class="sxs-lookup"><span data-stu-id="e4a19-221">Checksum</span></span>

<span data-ttu-id="e4a19-222">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="e4a19-222">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="e4a19-223">Definizione</span><span class="sxs-lookup"><span data-stu-id="e4a19-223">Definition</span></span>

<span data-ttu-id="e4a19-224">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="e4a19-224">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e4a19-225">L'espressione regolare `Regex_germany_eu_telephone_number` consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="e4a19-225">The regular expression  `Regex_germany_eu_telephone_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="e4a19-226">Una parola chiave da `Keywords_germany_eu_telephone_number` viene trovato.</span><span class="sxs-lookup"><span data-stu-id="e4a19-226">A keyword from  `Keywords_germany_eu_telephone_number` is found.</span></span> 
    
<span data-ttu-id="e4a19-227">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="e4a19-227">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e4a19-228">L'espressione regolare `Regex_germany_eu_telephone_number` consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="e4a19-228">The regular expression  `Regex_germany_eu_telephone_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Telephone Number -->
<Entity id="eb367e90-d826-40aa-a338-a1fdb3a4d99b" patternsProximity="300" recommendedConfidence="75">
<!-- Loosely formatted patterns with mandatory corroborative evidence -->
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_germany_eu_telephone_number" />
          <Match idRef="Keywords_germany_eu_telephone_number" />
        </Pattern>
<!-- Strictly formatted patterns without mandatory corroborative evidence -->
          <Pattern confidenceLevel="75">
            <IdMatch idRef="Regex_germany_eu_formatted_telephone_number" />
          </Pattern>
        </Entity>
```

## <a name="greece"></a><span data-ttu-id="e4a19-229">Grecia</span><span class="sxs-lookup"><span data-stu-id="e4a19-229">Greece</span></span>

### <a name="pattern"></a><span data-ttu-id="e4a19-230">Modello</span><span class="sxs-lookup"><span data-stu-id="e4a19-230">Pattern</span></span>

- <span data-ttu-id="e4a19-231">Cifre</span><span class="sxs-lookup"><span data-stu-id="e4a19-231">Digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="e4a19-232">Checksum</span><span class="sxs-lookup"><span data-stu-id="e4a19-232">Checksum</span></span>

<span data-ttu-id="e4a19-233">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="e4a19-233">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="e4a19-234">Definizione</span><span class="sxs-lookup"><span data-stu-id="e4a19-234">Definition</span></span>

<span data-ttu-id="e4a19-235">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="e4a19-235">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e4a19-236">L'espressione regolare `Regex_greece_eu_telephone_number` consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="e4a19-236">The regular expression  `Regex_greece_eu_telephone_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="e4a19-237">Una parola chiave da `Keywords_greece_eu_telephone_number` viene trovato.</span><span class="sxs-lookup"><span data-stu-id="e4a19-237">A keyword from  `Keywords_greece_eu_telephone_number` is found.</span></span> 
    
<span data-ttu-id="e4a19-238">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="e4a19-238">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e4a19-239">L'espressione regolare `Regex_greece_eu_telephone_number` consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="e4a19-239">The regular expression  `Regex_greece_eu_telephone_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Telephone Number -->
<Entity id="eb367e90-d826-40aa-a338-a1fdb3a4d99b" patternsProximity="300" recommendedConfidence="75">
<!-- Loosely formatted patterns with mandatory corroborative evidence -->
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_greece_eu_telephone_number" />
          <Match idRef="Keywords_greece_eu_telephone_number" />
        </Pattern>
<!-- Strictly formatted patterns without mandatory corroborative evidence -->
          <Pattern confidenceLevel="75">
            <IdMatch idRef="Regex_greece_eu_formatted_telephone_number" />
          </Pattern>
        </Entity>
```

## <a name="hungary"></a><span data-ttu-id="e4a19-240">Ungheria</span><span class="sxs-lookup"><span data-stu-id="e4a19-240">Hungary</span></span>

### <a name="pattern"></a><span data-ttu-id="e4a19-241">Modello</span><span class="sxs-lookup"><span data-stu-id="e4a19-241">Pattern</span></span>

- <span data-ttu-id="e4a19-242">Cifre</span><span class="sxs-lookup"><span data-stu-id="e4a19-242">Digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="e4a19-243">Checksum</span><span class="sxs-lookup"><span data-stu-id="e4a19-243">Checksum</span></span>

<span data-ttu-id="e4a19-244">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="e4a19-244">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="e4a19-245">Definizione</span><span class="sxs-lookup"><span data-stu-id="e4a19-245">Definition</span></span>

<span data-ttu-id="e4a19-246">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="e4a19-246">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e4a19-247">L'espressione regolare `Regex_hungary_eu_telephone_number` consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="e4a19-247">The regular expression  `Regex_hungary_eu_telephone_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="e4a19-248">Una parola chiave da `Keywords_hungary_eu_telephone_number` viene trovato.</span><span class="sxs-lookup"><span data-stu-id="e4a19-248">A keyword from  `Keywords_hungary_eu_telephone_number` is found.</span></span> 
    
<span data-ttu-id="e4a19-249">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="e4a19-249">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e4a19-250">L'espressione regolare `Regex_hungary_eu_telephone_number` consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="e4a19-250">The regular expression  `Regex_hungary_eu_telephone_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Telephone Number -->
<Entity id="eb367e90-d826-40aa-a338-a1fdb3a4d99b" patternsProximity="300" recommendedConfidence="75">
<!-- Loosely formatted patterns with mandatory corroborative evidence -->
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_hungary_eu_telephone_number" />
          <Match idRef="Keywords_hungary_eu_telephone_number" />
        </Pattern>
<!-- Strictly formatted patterns without mandatory corroborative evidence -->
          <Pattern confidenceLevel="75">
            <IdMatch idRef="Regex_hungary_eu_formatted_telephone_number" />
          </Pattern>
       </Entity>
```

## <a name="ireland"></a><span data-ttu-id="e4a19-251">Irlanda</span><span class="sxs-lookup"><span data-stu-id="e4a19-251">Ireland</span></span>

### <a name="pattern"></a><span data-ttu-id="e4a19-252">Modello</span><span class="sxs-lookup"><span data-stu-id="e4a19-252">Pattern</span></span>

- <span data-ttu-id="e4a19-253">Cifre</span><span class="sxs-lookup"><span data-stu-id="e4a19-253">Digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="e4a19-254">Checksum</span><span class="sxs-lookup"><span data-stu-id="e4a19-254">Checksum</span></span>

<span data-ttu-id="e4a19-255">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="e4a19-255">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="e4a19-256">Definizione</span><span class="sxs-lookup"><span data-stu-id="e4a19-256">Definition</span></span>

<span data-ttu-id="e4a19-257">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="e4a19-257">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e4a19-258">L'espressione regolare `Regex_ireland_eu_telephone_number` consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="e4a19-258">The regular expression  `Regex_ireland_eu_telephone_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="e4a19-259">Una parola chiave da `Keywords_ireland_eu_telephone_number` viene trovato.</span><span class="sxs-lookup"><span data-stu-id="e4a19-259">A keyword from  `Keywords_ireland_eu_telephone_number` is found.</span></span> 
    
<span data-ttu-id="e4a19-260">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="e4a19-260">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e4a19-261">L'espressione regolare `Regex_ireland_eu_telephone_number` consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="e4a19-261">The regular expression  `Regex_ireland_eu_telephone_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Telephone Number -->
<Entity id="eb367e90-d826-40aa-a338-a1fdb3a4d99b" patternsProximity="300" recommendedConfidence="75">
<!-- Loosely formatted patterns with mandatory corroborative evidence -->
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_ireland_eu_telephone_number" />
          <Match idRef="Keywords_ireland_eu_telephone_number" />
        </Pattern>
<!-- Strictly formatted patterns without mandatory corroborative evidence -->
          <Pattern confidenceLevel="75">
            <IdMatch idRef="Regex_ireland_eu_formatted_telephone_number" />
          </Pattern>
          </Entity>
```

## <a name="italy"></a><span data-ttu-id="e4a19-262">Italia</span><span class="sxs-lookup"><span data-stu-id="e4a19-262">Italy</span></span>

### <a name="pattern"></a><span data-ttu-id="e4a19-263">Modello</span><span class="sxs-lookup"><span data-stu-id="e4a19-263">Pattern</span></span>

- <span data-ttu-id="e4a19-264">Cifre</span><span class="sxs-lookup"><span data-stu-id="e4a19-264">Digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="e4a19-265">Checksum</span><span class="sxs-lookup"><span data-stu-id="e4a19-265">Checksum</span></span>

<span data-ttu-id="e4a19-266">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="e4a19-266">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="e4a19-267">Definizione</span><span class="sxs-lookup"><span data-stu-id="e4a19-267">Definition</span></span>

<span data-ttu-id="e4a19-268">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="e4a19-268">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e4a19-269">L'espressione regolare `Regex_italy_eu_telephone_number` consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="e4a19-269">The regular expression  `Regex_italy_eu_telephone_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="e4a19-270">Una parola chiave da `Keywords_italy_eu_telephone_number` viene trovato.</span><span class="sxs-lookup"><span data-stu-id="e4a19-270">A keyword from  `Keywords_italy_eu_telephone_number` is found.</span></span> 
    
<span data-ttu-id="e4a19-271">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="e4a19-271">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e4a19-272">L'espressione regolare `Regex_italy_eu_telephone_number` consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="e4a19-272">The regular expression  `Regex_italy_eu_telephone_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Telephone Number -->
<Entity id="eb367e90-d826-40aa-a338-a1fdb3a4d99b" patternsProximity="300" recommendedConfidence="75">
<!-- Loosely formatted patterns with mandatory corroborative evidence -->
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_italy_eu_telephone_number" />
          <Match idRef="Keywords_italy_eu_telephone_number" />
        </Pattern>
<!-- Strictly formatted patterns without mandatory corroborative evidence -->
          <Pattern confidenceLevel="75">
            <IdMatch idRef="Regex_italy_eu_formatted_telephone_number" />
          </Pattern>
         </Entity>
```

## <a name="latvia"></a><span data-ttu-id="e4a19-273">Lettonia</span><span class="sxs-lookup"><span data-stu-id="e4a19-273">Latvia</span></span>

### <a name="pattern"></a><span data-ttu-id="e4a19-274">Modello</span><span class="sxs-lookup"><span data-stu-id="e4a19-274">Pattern</span></span>

- <span data-ttu-id="e4a19-275">Cifre</span><span class="sxs-lookup"><span data-stu-id="e4a19-275">Digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="e4a19-276">Checksum</span><span class="sxs-lookup"><span data-stu-id="e4a19-276">Checksum</span></span>

<span data-ttu-id="e4a19-277">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="e4a19-277">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="e4a19-278">Definizione</span><span class="sxs-lookup"><span data-stu-id="e4a19-278">Definition</span></span>

<span data-ttu-id="e4a19-279">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="e4a19-279">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e4a19-280">L'espressione regolare `Regex_latvia_eu_telephone_number` consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="e4a19-280">The regular expression  `Regex_latvia_eu_telephone_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="e4a19-281">Una parola chiave da `Keywords_latvia_eu_telephone_number` viene trovato.</span><span class="sxs-lookup"><span data-stu-id="e4a19-281">A keyword from  `Keywords_latvia_eu_telephone_number` is found.</span></span> 
    
<span data-ttu-id="e4a19-282">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="e4a19-282">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e4a19-283">L'espressione regolare `Regex_latvia_eu_telephone_number` consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="e4a19-283">The regular expression  `Regex_latvia_eu_telephone_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Telephone Number -->
<Entity id="eb367e90-d826-40aa-a338-a1fdb3a4d99b" patternsProximity="300" recommendedConfidence="75">
<!-- Loosely formatted patterns with mandatory corroborative evidence -->
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_latvia_eu_telephone_number" />
          <Match idRef="Keywords_latvia_eu_telephone_number" />
        </Pattern>
<!-- Strictly formatted patterns without mandatory corroborative evidence -->
          <Pattern confidenceLevel="75">
            <IdMatch idRef="Regex_latvia_eu_formatted_telephone_number" />
          </Pattern>
          </Entity>
```

## <a name="lithuania"></a><span data-ttu-id="e4a19-284">Lituania</span><span class="sxs-lookup"><span data-stu-id="e4a19-284">Lithuania</span></span>

### <a name="pattern"></a><span data-ttu-id="e4a19-285">Modello</span><span class="sxs-lookup"><span data-stu-id="e4a19-285">Pattern</span></span>

- <span data-ttu-id="e4a19-286">Cifre</span><span class="sxs-lookup"><span data-stu-id="e4a19-286">Digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="e4a19-287">Checksum</span><span class="sxs-lookup"><span data-stu-id="e4a19-287">Checksum</span></span>

<span data-ttu-id="e4a19-288">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="e4a19-288">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="e4a19-289">Definizione</span><span class="sxs-lookup"><span data-stu-id="e4a19-289">Definition</span></span>

<span data-ttu-id="e4a19-290">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="e4a19-290">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e4a19-291">L'espressione regolare `Regex_lithuania_eu_telephone_number` consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="e4a19-291">The regular expression  `Regex_lithuania_eu_telephone_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="e4a19-292">Una parola chiave da `Keywords_lithuania_eu_telephone_number` viene trovato.</span><span class="sxs-lookup"><span data-stu-id="e4a19-292">A keyword from  `Keywords_lithuania_eu_telephone_number` is found.</span></span> 
    
<span data-ttu-id="e4a19-293">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="e4a19-293">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e4a19-294">L'espressione regolare `Regex_lithuania_eu_telephone_number` consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="e4a19-294">The regular expression  `Regex_lithuania_eu_telephone_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Telephone Number -->
<Entity id="eb367e90-d826-40aa-a338-a1fdb3a4d99b" patternsProximity="300" recommendedConfidence="75">
<!-- Loosely formatted patterns with mandatory corroborative evidence -->
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_lithuania_eu_telephone_number" />
          <Match idRef="Keywords_lithuania_eu_telephone_number" />
        </Pattern>
<!-- Strictly formatted patterns without mandatory corroborative evidence -->
          <Pattern confidenceLevel="75">
            <IdMatch idRef="Regex_lithuania_eu_formatted_telephone_number" />
          </Pattern>
          </Entity>
```

## <a name="luxemburg"></a><span data-ttu-id="e4a19-295">Lussemburgo</span><span class="sxs-lookup"><span data-stu-id="e4a19-295">Luxemburg</span></span>

### <a name="pattern"></a><span data-ttu-id="e4a19-296">Modello</span><span class="sxs-lookup"><span data-stu-id="e4a19-296">Pattern</span></span>

- <span data-ttu-id="e4a19-297">Cifre</span><span class="sxs-lookup"><span data-stu-id="e4a19-297">Digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="e4a19-298">Checksum</span><span class="sxs-lookup"><span data-stu-id="e4a19-298">Checksum</span></span>

<span data-ttu-id="e4a19-299">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="e4a19-299">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="e4a19-300">Definizione</span><span class="sxs-lookup"><span data-stu-id="e4a19-300">Definition</span></span>

<span data-ttu-id="e4a19-301">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="e4a19-301">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e4a19-302">L'espressione regolare `Regex_luxemburg_eu_telephone_number` consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="e4a19-302">The regular expression  `Regex_luxemburg_eu_telephone_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="e4a19-303">Una parola chiave da `Keywords_luxemburg_eu_telephone_number` viene trovato.</span><span class="sxs-lookup"><span data-stu-id="e4a19-303">A keyword from  `Keywords_luxemburg_eu_telephone_number` is found.</span></span> 
    
<span data-ttu-id="e4a19-304">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="e4a19-304">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e4a19-305">L'espressione regolare `Regex_luxemburg_eu_telephone_number` consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="e4a19-305">The regular expression  `Regex_luxemburg_eu_telephone_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Telephone Number -->
<Entity id="eb367e90-d826-40aa-a338-a1fdb3a4d99b" patternsProximity="300" recommendedConfidence="75">
<!-- Loosely formatted patterns with mandatory corroborative evidence -->
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_luxemburg_eu_telephone_number" />
          <Match idRef="Keywords_luxemburg_eu_telephone_number" />
        </Pattern>
<!-- Strictly formatted patterns without mandatory corroborative evidence -->
          <Pattern confidenceLevel="75">
            <IdMatch idRef="Regex_luxemburg_eu_formatted_telephone_number" />
                  </Pattern>
</Entity>
```

## <a name="malta"></a><span data-ttu-id="e4a19-306">Malta</span><span class="sxs-lookup"><span data-stu-id="e4a19-306">Malta</span></span>

### <a name="pattern"></a><span data-ttu-id="e4a19-307">Modello</span><span class="sxs-lookup"><span data-stu-id="e4a19-307">Pattern</span></span>

- <span data-ttu-id="e4a19-308">Cifre</span><span class="sxs-lookup"><span data-stu-id="e4a19-308">Digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="e4a19-309">Checksum</span><span class="sxs-lookup"><span data-stu-id="e4a19-309">Checksum</span></span>

<span data-ttu-id="e4a19-310">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="e4a19-310">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="e4a19-311">Definizione</span><span class="sxs-lookup"><span data-stu-id="e4a19-311">Definition</span></span>

<span data-ttu-id="e4a19-312">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="e4a19-312">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e4a19-313">L'espressione regolare `Regex_malta_eu_telephone_number` consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="e4a19-313">The regular expression  `Regex_malta_eu_telephone_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="e4a19-314">Una parola chiave da `Keywords_malta_eu_telephone_number` viene trovato.</span><span class="sxs-lookup"><span data-stu-id="e4a19-314">A keyword from  `Keywords_malta_eu_telephone_number` is found.</span></span> 
    
<span data-ttu-id="e4a19-315">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="e4a19-315">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e4a19-316">L'espressione regolare `Regex_malta_eu_telephone_number` consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="e4a19-316">The regular expression  `Regex_malta_eu_telephone_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Telephone Number -->
<Entity id="eb367e90-d826-40aa-a338-a1fdb3a4d99b" patternsProximity="300" recommendedConfidence="75">
<!-- Loosely formatted patterns with mandatory corroborative evidence -->
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_malta_eu_telephone_number" />
          <Match idRef="Keywords_malta_eu_telephone_number" />
        </Pattern>
<!-- Strictly formatted patterns without mandatory corroborative evidence -->
          <Pattern confidenceLevel="75">
            <IdMatch idRef="Regex_malta_eu_formatted_telephone_number" />
            </Pattern>
</Entity>
```

## <a name="netherlands"></a><span data-ttu-id="e4a19-317">Paesi Bassi</span><span class="sxs-lookup"><span data-stu-id="e4a19-317">Netherlands</span></span>

### <a name="pattern"></a><span data-ttu-id="e4a19-318">Modello</span><span class="sxs-lookup"><span data-stu-id="e4a19-318">Pattern</span></span>

- <span data-ttu-id="e4a19-319">Cifre</span><span class="sxs-lookup"><span data-stu-id="e4a19-319">Digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="e4a19-320">Checksum</span><span class="sxs-lookup"><span data-stu-id="e4a19-320">Checksum</span></span>

<span data-ttu-id="e4a19-321">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="e4a19-321">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="e4a19-322">Definizione</span><span class="sxs-lookup"><span data-stu-id="e4a19-322">Definition</span></span>

<span data-ttu-id="e4a19-323">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="e4a19-323">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e4a19-324">L'espressione regolare `Regex_netherlands_eu_telephone_number` consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="e4a19-324">The regular expression  `Regex_netherlands_eu_telephone_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="e4a19-325">Una parola chiave da `Keywords_netherlands_eu_telephone_number` viene trovato.</span><span class="sxs-lookup"><span data-stu-id="e4a19-325">A keyword from  `Keywords_netherlands_eu_telephone_number` is found.</span></span> 
    
<span data-ttu-id="e4a19-326">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="e4a19-326">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e4a19-327">L'espressione regolare `Regex_netherlands_eu_telephone_number` consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="e4a19-327">The regular expression  `Regex_netherlands_eu_telephone_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Telephone Number -->
<Entity id="eb367e90-d826-40aa-a338-a1fdb3a4d99b" patternsProximity="300" recommendedConfidence="75">
<!-- Loosely formatted patterns with mandatory corroborative evidence -->
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_netherlands_eu_telephone_number" />
          <Match idRef="Keywords_netherlands_eu_telephone_number" />
        </Pattern>
<!-- Strictly formatted patterns without mandatory corroborative evidence -->
          <Pattern confidenceLevel="75">
            <IdMatch idRef="Regex_netherlands_eu_formatted_telephone_number" />
            </Pattern>
</Entity>
```

## <a name="poland"></a><span data-ttu-id="e4a19-328">Polonia</span><span class="sxs-lookup"><span data-stu-id="e4a19-328">Poland</span></span>

### <a name="pattern"></a><span data-ttu-id="e4a19-329">Modello</span><span class="sxs-lookup"><span data-stu-id="e4a19-329">Pattern</span></span>

- <span data-ttu-id="e4a19-330">Cifre</span><span class="sxs-lookup"><span data-stu-id="e4a19-330">Digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="e4a19-331">Checksum</span><span class="sxs-lookup"><span data-stu-id="e4a19-331">Checksum</span></span>

<span data-ttu-id="e4a19-332">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="e4a19-332">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="e4a19-333">Definizione</span><span class="sxs-lookup"><span data-stu-id="e4a19-333">Definition</span></span>

<span data-ttu-id="e4a19-334">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="e4a19-334">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e4a19-335">L'espressione regolare `Regex_poland_eu_telephone_number` consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="e4a19-335">The regular expression  `Regex_poland_eu_telephone_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="e4a19-336">Una parola chiave da `Keywords_poland_eu_telephone_number` viene trovato.</span><span class="sxs-lookup"><span data-stu-id="e4a19-336">A keyword from  `Keywords_poland_eu_telephone_number` is found.</span></span> 
    
<span data-ttu-id="e4a19-337">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="e4a19-337">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e4a19-338">L'espressione regolare `Regex_poland_eu_telephone_number` consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="e4a19-338">The regular expression  `Regex_poland_eu_telephone_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Telephone Number -->
<Entity id="eb367e90-d826-40aa-a338-a1fdb3a4d99b" patternsProximity="300" recommendedConfidence="75">
<!-- Loosely formatted patterns with mandatory corroborative evidence -->
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_poland_eu_telephone_number" />
          <Match idRef="Keywords_poland_eu_telephone_number" />
        </Pattern>
<!-- Strictly formatted patterns without mandatory corroborative evidence -->
          <Pattern confidenceLevel="75">
            <IdMatch idRef="Regex_poland_eu_formatted_telephone_number" />
             </Pattern>
</Entity>
```

## <a name="portugal"></a><span data-ttu-id="e4a19-339">Portogallo</span><span class="sxs-lookup"><span data-stu-id="e4a19-339">Portugal</span></span>

### <a name="pattern"></a><span data-ttu-id="e4a19-340">Modello</span><span class="sxs-lookup"><span data-stu-id="e4a19-340">Pattern</span></span>

- <span data-ttu-id="e4a19-341">Cifre</span><span class="sxs-lookup"><span data-stu-id="e4a19-341">Digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="e4a19-342">Checksum</span><span class="sxs-lookup"><span data-stu-id="e4a19-342">Checksum</span></span>

<span data-ttu-id="e4a19-343">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="e4a19-343">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="e4a19-344">Definizione</span><span class="sxs-lookup"><span data-stu-id="e4a19-344">Definition</span></span>

<span data-ttu-id="e4a19-345">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="e4a19-345">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e4a19-346">L'espressione regolare `Regex_portugal_eu_telephone_number` consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="e4a19-346">The regular expression  `Regex_portugal_eu_telephone_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="e4a19-347">Una parola chiave da `Keywords_portugal_eu_telephone_number` viene trovato.</span><span class="sxs-lookup"><span data-stu-id="e4a19-347">A keyword from  `Keywords_portugal_eu_telephone_number` is found.</span></span> 
    
<span data-ttu-id="e4a19-348">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="e4a19-348">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e4a19-349">L'espressione regolare `Regex_portugal_eu_telephone_number` consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="e4a19-349">The regular expression  `Regex_portugal_eu_telephone_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Telephone Number -->
<Entity id="eb367e90-d826-40aa-a338-a1fdb3a4d99b" patternsProximity="300" recommendedConfidence="75">
<!-- Loosely formatted patterns with mandatory corroborative evidence -->
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_portugal_eu_telephone_number" />
          <Match idRef="Keywords_portugal_eu_telephone_number" />
        </Pattern>
<!-- Strictly formatted patterns without mandatory corroborative evidence -->
          <Pattern confidenceLevel="75">
            <IdMatch idRef="Regex_portugal_eu_formatted_telephone_number" />
          </Pattern>
        </Entity>
```

## <a name="romania"></a><span data-ttu-id="e4a19-350">Romania</span><span class="sxs-lookup"><span data-stu-id="e4a19-350">Romania</span></span>

### <a name="pattern"></a><span data-ttu-id="e4a19-351">Modello</span><span class="sxs-lookup"><span data-stu-id="e4a19-351">Pattern</span></span>

- <span data-ttu-id="e4a19-352">Cifre</span><span class="sxs-lookup"><span data-stu-id="e4a19-352">Digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="e4a19-353">Checksum</span><span class="sxs-lookup"><span data-stu-id="e4a19-353">Checksum</span></span>

<span data-ttu-id="e4a19-354">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="e4a19-354">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="e4a19-355">Definizione</span><span class="sxs-lookup"><span data-stu-id="e4a19-355">Definition</span></span>

<span data-ttu-id="e4a19-356">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="e4a19-356">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e4a19-357">L'espressione regolare `Regex_romania_eu_telephone_number` consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="e4a19-357">The regular expression  `Regex_romania_eu_telephone_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="e4a19-358">Una parola chiave da `Keywords_romania_eu_telephone_number` viene trovato.</span><span class="sxs-lookup"><span data-stu-id="e4a19-358">A keyword from  `Keywords_romania_eu_telephone_number` is found.</span></span> 
    
<span data-ttu-id="e4a19-359">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="e4a19-359">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e4a19-360">L'espressione regolare `Regex_romania_eu_telephone_number` consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="e4a19-360">The regular expression  `Regex_romania_eu_telephone_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Telephone Number -->
<Entity id="eb367e90-d826-40aa-a338-a1fdb3a4d99b" patternsProximity="300" recommendedConfidence="75">
<!-- Loosely formatted patterns with mandatory corroborative evidence -->
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_romania_eu_telephone_number" />
          <Match idRef="Keywords_romania_eu_telephone_number" />
        </Pattern>
<!-- Strictly formatted patterns without mandatory corroborative evidence -->
          <Pattern confidenceLevel="75">
            <IdMatch idRef="Regex_romania_eu_formatted_telephone_number" />
            </Pattern>
</Entity>
```

## <a name="slovakia"></a><span data-ttu-id="e4a19-361">Slovacchia</span><span class="sxs-lookup"><span data-stu-id="e4a19-361">Slovakia</span></span>

### <a name="pattern"></a><span data-ttu-id="e4a19-362">Modello</span><span class="sxs-lookup"><span data-stu-id="e4a19-362">Pattern</span></span>

- <span data-ttu-id="e4a19-363">Cifre</span><span class="sxs-lookup"><span data-stu-id="e4a19-363">Digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="e4a19-364">Checksum</span><span class="sxs-lookup"><span data-stu-id="e4a19-364">Checksum</span></span>

<span data-ttu-id="e4a19-365">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="e4a19-365">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="e4a19-366">Definizione</span><span class="sxs-lookup"><span data-stu-id="e4a19-366">Definition</span></span>

<span data-ttu-id="e4a19-367">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="e4a19-367">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e4a19-368">L'espressione regolare `Regex_slovakia_eu_telephone_number` consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="e4a19-368">The regular expression  `Regex_slovakia_eu_telephone_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="e4a19-369">Una parola chiave da `Keywords_slovakia_eu_telephone_number` viene trovato.</span><span class="sxs-lookup"><span data-stu-id="e4a19-369">A keyword from  `Keywords_slovakia_eu_telephone_number` is found.</span></span> 
    
<span data-ttu-id="e4a19-370">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="e4a19-370">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e4a19-371">L'espressione regolare `Regex_slovakia_eu_telephone_number` consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="e4a19-371">The regular expression  `Regex_slovakia_eu_telephone_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Telephone Number -->
<Entity id="eb367e90-d826-40aa-a338-a1fdb3a4d99b" patternsProximity="300" recommendedConfidence="75">
<!-- Loosely formatted patterns with mandatory corroborative evidence -->
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovakia_eu_telephone_number" />
          <Match idRef="Keywords_slovakia_eu_telephone_number" />
        </Pattern>
<!-- Strictly formatted patterns without mandatory corroborative evidence -->
          <Pattern confidenceLevel="75">
            <IdMatch idRef="Regex_slovakia_eu_formatted_telephone_number" />
            </Pattern>
</Entity>
```

## <a name="slovenia"></a><span data-ttu-id="e4a19-372">Slovenia</span><span class="sxs-lookup"><span data-stu-id="e4a19-372">Slovenia</span></span>

### <a name="pattern"></a><span data-ttu-id="e4a19-373">Modello</span><span class="sxs-lookup"><span data-stu-id="e4a19-373">Pattern</span></span>

- <span data-ttu-id="e4a19-374">Cifre</span><span class="sxs-lookup"><span data-stu-id="e4a19-374">Digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="e4a19-375">Checksum</span><span class="sxs-lookup"><span data-stu-id="e4a19-375">Checksum</span></span>

<span data-ttu-id="e4a19-376">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="e4a19-376">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="e4a19-377">Definizione</span><span class="sxs-lookup"><span data-stu-id="e4a19-377">Definition</span></span>

<span data-ttu-id="e4a19-378">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="e4a19-378">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e4a19-379">L'espressione regolare `Regex_slovenia_eu_telephone_number` consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="e4a19-379">The regular expression  `Regex_slovenia_eu_telephone_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="e4a19-380">Una parola chiave da `Keywords_slovenia_eu_telephone_number` viene trovato.</span><span class="sxs-lookup"><span data-stu-id="e4a19-380">A keyword from  `Keywords_slovenia_eu_telephone_number` is found.</span></span> 
    
<span data-ttu-id="e4a19-381">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="e4a19-381">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e4a19-382">L'espressione regolare `Regex_slovenia_eu_telephone_number` consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="e4a19-382">The regular expression  `Regex_slovenia_eu_telephone_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Telephone Number -->
<Entity id="eb367e90-d826-40aa-a338-a1fdb3a4d99b" patternsProximity="300" recommendedConfidence="75">
<!-- Loosely formatted patterns with mandatory corroborative evidence -->
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovenia_eu_telephone_number" />
          <Match idRef="Keywords_slovenia_eu_telephone_number" />
        </Pattern>
<!-- Strictly formatted patterns without mandatory corroborative evidence -->
          <Pattern confidenceLevel="75">
            <IdMatch idRef="Regex_slovenia_eu_formatted_telephone_number" />
          </Pattern>
          </Entity>
```

## <a name="spain"></a><span data-ttu-id="e4a19-383">Spagna</span><span class="sxs-lookup"><span data-stu-id="e4a19-383">Spain</span></span>

### <a name="pattern"></a><span data-ttu-id="e4a19-384">Modello</span><span class="sxs-lookup"><span data-stu-id="e4a19-384">Pattern</span></span>

- <span data-ttu-id="e4a19-385">Cifre</span><span class="sxs-lookup"><span data-stu-id="e4a19-385">Digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="e4a19-386">Checksum</span><span class="sxs-lookup"><span data-stu-id="e4a19-386">Checksum</span></span>

<span data-ttu-id="e4a19-387">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="e4a19-387">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="e4a19-388">Definizione</span><span class="sxs-lookup"><span data-stu-id="e4a19-388">Definition</span></span>

<span data-ttu-id="e4a19-389">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="e4a19-389">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e4a19-390">L'espressione regolare `Regex_spain_eu_telephone_number` consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="e4a19-390">The regular expression  `Regex_spain_eu_telephone_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="e4a19-391">Una parola chiave da `Keywords_spain_eu_telephone_number` viene trovato.</span><span class="sxs-lookup"><span data-stu-id="e4a19-391">A keyword from  `Keywords_spain_eu_telephone_number` is found.</span></span> 
    
<span data-ttu-id="e4a19-392">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="e4a19-392">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e4a19-393">L'espressione regolare `Regex_spain_eu_telephone_number` consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="e4a19-393">The regular expression  `Regex_spain_eu_telephone_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Telephone Number -->
<Entity id="eb367e90-d826-40aa-a338-a1fdb3a4d99b" patternsProximity="300" recommendedConfidence="75">
<!-- Loosely formatted patterns with mandatory corroborative evidence -->
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_spain_eu_telephone_number" />
          <Match idRef="Keywords_spain_eu_telephone_number" />
        </Pattern>
<!-- Strictly formatted patterns without mandatory corroborative evidence -->
          <Pattern confidenceLevel="75">
            <IdMatch idRef="Regex_spain_eu_formatted_telephone_number" />
          </Pattern>
          </Entity>
```

## <a name="sweden"></a><span data-ttu-id="e4a19-394">Svezia</span><span class="sxs-lookup"><span data-stu-id="e4a19-394">Sweden</span></span>

### <a name="pattern"></a><span data-ttu-id="e4a19-395">Modello</span><span class="sxs-lookup"><span data-stu-id="e4a19-395">Pattern</span></span>

- <span data-ttu-id="e4a19-396">Cifre</span><span class="sxs-lookup"><span data-stu-id="e4a19-396">Digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="e4a19-397">Checksum</span><span class="sxs-lookup"><span data-stu-id="e4a19-397">Checksum</span></span>

<span data-ttu-id="e4a19-398">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="e4a19-398">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="e4a19-399">Definizione</span><span class="sxs-lookup"><span data-stu-id="e4a19-399">Definition</span></span>

<span data-ttu-id="e4a19-400">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="e4a19-400">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e4a19-401">L'espressione regolare `Regex_sweden_eu_telephone_number` consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="e4a19-401">The regular expression  `Regex_sweden_eu_telephone_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="e4a19-402">Una parola chiave da `Keywords_sweden_eu_telephone_number` viene trovato.</span><span class="sxs-lookup"><span data-stu-id="e4a19-402">A keyword from  `Keywords_sweden_eu_telephone_number` is found.</span></span> 
    
<span data-ttu-id="e4a19-403">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="e4a19-403">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e4a19-404">L'espressione regolare `Regex_sweden_eu_telephone_number` consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="e4a19-404">The regular expression  `Regex_sweden_eu_telephone_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Telephone Number -->
<Entity id="eb367e90-d826-40aa-a338-a1fdb3a4d99b" patternsProximity="300" recommendedConfidence="75">
<!-- Loosely formatted patterns with mandatory corroborative evidence -->
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_sweden_eu_telephone_number" />
          <Match idRef="Keywords_sweden_eu_telephone_number" />
        </Pattern>
<!-- Strictly formatted patterns without mandatory corroborative evidence -->
          <Pattern confidenceLevel="75">
            <IdMatch idRef="Regex_sweden_eu_formatted_telephone_number" />
          </Pattern>
          </Entity>
```

## <a name="uk"></a><span data-ttu-id="e4a19-405">REGNO UNITO</span><span class="sxs-lookup"><span data-stu-id="e4a19-405">UK</span></span>

### <a name="pattern"></a><span data-ttu-id="e4a19-406">Modello</span><span class="sxs-lookup"><span data-stu-id="e4a19-406">Pattern</span></span>

- <span data-ttu-id="e4a19-407">Cifre</span><span class="sxs-lookup"><span data-stu-id="e4a19-407">Digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="e4a19-408">Checksum</span><span class="sxs-lookup"><span data-stu-id="e4a19-408">Checksum</span></span>

<span data-ttu-id="e4a19-409">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="e4a19-409">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="e4a19-410">Definizione</span><span class="sxs-lookup"><span data-stu-id="e4a19-410">Definition</span></span>

<span data-ttu-id="e4a19-411">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="e4a19-411">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e4a19-412">L'espressione regolare `Regex_uk_eu_telephone_number` consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="e4a19-412">The regular expression  `Regex_uk_eu_telephone_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="e4a19-413">Una parola chiave da `Keywords_uk_eu_telephone_number` viene trovato.</span><span class="sxs-lookup"><span data-stu-id="e4a19-413">A keyword from  `Keywords_uk_eu_telephone_number` is found.</span></span> 
    
<span data-ttu-id="e4a19-414">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="e4a19-414">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e4a19-415">L'espressione regolare `Regex_uk_eu_telephone_number` consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="e4a19-415">The regular expression  `Regex_uk_eu_telephone_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Telephone Number -->
<Entity id="eb367e90-d826-40aa-a338-a1fdb3a4d99b" patternsProximity="300" recommendedConfidence="75">
<!-- Loosely formatted patterns with mandatory corroborative evidence -->
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_uk_eu_telephone_number" />
          <Match idRef="Keywords_uk_eu_telephone_number" />
        </Pattern>
<!-- Strictly formatted patterns without mandatory corroborative evidence -->
          <Pattern confidenceLevel="75">
            <IdMatch idRef="Regex_uk_eu_formatted_telephone_number" />
            </Pattern>
</Entity>
```

## <a name="see-also"></a><span data-ttu-id="e4a19-416">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e4a19-416">See also</span></span>

[<span data-ttu-id="e4a19-417">Cosa individuano i tipi di informazioni riservate</span><span class="sxs-lookup"><span data-stu-id="e4a19-417">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)

