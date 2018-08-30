---
title: Coordinate GPS UE
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 8/14/2018
ms.audience: Admin
ms.topic: reference
ms.service: o365-administration
localization_priority: Normal
ms.assetid: fdf2aebc-d5a4-4138-b10f-4a81dd70415a
description: Prevenzione perdita dati (DLP) in Office 365 Security &amp; centro conformità include molti tipi di informazioni riservate che si desidera utilizzare i criteri DLP. In questo argomento viene descritto il tipo di informazioni riservate dell'Unione europea GPS coordina.
ms.openlocfilehash: 89fb8420e479b9f793fc2be9aa3a9a9fd5741691
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/27/2018
ms.locfileid: "22530718"
---
# <a name="eu-gps-coordinates"></a><span data-ttu-id="5ea19-104">Coordinate GPS UE</span><span class="sxs-lookup"><span data-stu-id="5ea19-104">EU GPS Coordinates</span></span>

<span data-ttu-id="5ea19-p102">Prevenzione perdita dati (DLP) in Office 365 Security &amp; centro conformità include molti tipi di informazioni riservate che si desidera utilizzare i criteri DLP. In questo argomento viene descritto il tipo di informazioni riservate dell'Unione europea GPS coordina.</span><span class="sxs-lookup"><span data-stu-id="5ea19-p102">Data loss prevention (DLP) in the Office 365 Security &amp; Compliance Center includes many sensitive information types that are ready for you to use in your DLP policies. This topic describes the EU GPS Coordinates sensitive information type.</span></span>
  
## <a name="austria"></a><span data-ttu-id="5ea19-107">Austria</span><span class="sxs-lookup"><span data-stu-id="5ea19-107">Austria</span></span>

### <a name="format"></a><span data-ttu-id="5ea19-108">Formato</span><span class="sxs-lookup"><span data-stu-id="5ea19-108">Format</span></span>

<span data-ttu-id="5ea19-109">Per le città Austria sono nell'intervallo di coordinate: latitudine da 46.526 48.816 e longitudine da 9.6 a 16.945.</span><span class="sxs-lookup"><span data-stu-id="5ea19-109">Coordinates for cities in Austria are in range: Latitude from 46.526 to 48.816 and longitude from 9.6 to 16.945.</span></span>
  
### <a name="pattern"></a><span data-ttu-id="5ea19-110">Modello</span><span class="sxs-lookup"><span data-stu-id="5ea19-110">Pattern</span></span>

<span data-ttu-id="5ea19-111">Per ogni coordinata, la combinazione di un massimo di 6 cifre e un separatore decimale.</span><span class="sxs-lookup"><span data-stu-id="5ea19-111">For each coordinate, combination of up to 6 digits and a decimal point.</span></span>
  
- <span data-ttu-id="5ea19-112">Fino a 6 cifre</span><span class="sxs-lookup"><span data-stu-id="5ea19-112">Up to 6 digits</span></span>
    
- <span data-ttu-id="5ea19-113">Un separatore decimale dopo la prima o seconda cifre.</span><span class="sxs-lookup"><span data-stu-id="5ea19-113">A decimal point after first or second digit.</span></span>
    
### <a name="checksum"></a><span data-ttu-id="5ea19-114">Checksum</span><span class="sxs-lookup"><span data-stu-id="5ea19-114">Checksum</span></span>

<span data-ttu-id="5ea19-115">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="5ea19-115">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="5ea19-116">Definizione</span><span class="sxs-lookup"><span data-stu-id="5ea19-116">Definition</span></span>

<span data-ttu-id="5ea19-117">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="5ea19-117">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="5ea19-118">L'espressione regolare `Regex_austria_eu_gps_data_1` consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="5ea19-118">The regular expression  `Regex_austria_eu_gps_data_1` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="5ea19-119">Una parola chiave da `Keywords_austria_eu_gps_data` viene trovato.</span><span class="sxs-lookup"><span data-stu-id="5ea19-119">A keyword from  `Keywords_austria_eu_gps_data` is found.</span></span> 
    
<span data-ttu-id="5ea19-120">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 65%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="5ea19-120">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="5ea19-121">L'espressione regolare `Regex_austria_eu_gps_data_1` consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="5ea19-121">The regular expression  `Regex_austria_eu_gps_data_1` finds content that matches the pattern.</span></span> 
    
<span data-ttu-id="5ea19-122">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="5ea19-122">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="5ea19-123">L'espressione regolare `Regex_austria_eu_gps_data_2` consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="5ea19-123">The regular expression  `Regex_austria_eu_gps_data_2` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="5ea19-124">Una parola chiave da `Keywords_austria_eu_gps_data` viene trovato.</span><span class="sxs-lookup"><span data-stu-id="5ea19-124">A keyword from  `Keywords_austria_eu_gps_data` is found.</span></span> 
    
<span data-ttu-id="5ea19-125">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 65%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="5ea19-125">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="5ea19-126">L'espressione regolare `Regex_austria_eu_gps_data_2` consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="5ea19-126">The regular expression  `Regex_austria_eu_gps_data_2` finds content that matches the pattern.</span></span> 
    
```
 
<Entity id="42ac9f40-0912-4ae3-b5e6-08967192dec0" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_austria_eu_gps_data_1" />
          <Match idRef="Keywords_austria_eu_gps_data" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_austria_eu_gps_data_1" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_austria_eu_gps_data_2" />
          <Match idRef="Keywords_austria_eu_gps_data" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_austria_eu_gps_data_2" />
        </Pattern>

```

### <a name="keywords"></a><span data-ttu-id="5ea19-127">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="5ea19-127">Keywords</span></span>

#### <a name="keywordsaustriaeugpsdata"></a><span data-ttu-id="5ea19-128">Keywords_austria_eu_gps_data</span><span class="sxs-lookup"><span data-stu-id="5ea19-128">Keywords_austria_eu_gps_data</span></span>

<span data-ttu-id="5ea19-129">GPS tracker</span><span class="sxs-lookup"><span data-stu-id="5ea19-129">gps tracker</span></span>
  
<span data-ttu-id="5ea19-130">coordinate GPS</span><span class="sxs-lookup"><span data-stu-id="5ea19-130">gps coordinates</span></span>
  
<span data-ttu-id="5ea19-131">posizione</span><span class="sxs-lookup"><span data-stu-id="5ea19-131">location</span></span>
  
<span data-ttu-id="5ea19-132">corrispondenza</span><span class="sxs-lookup"><span data-stu-id="5ea19-132">map</span></span>
  
<span data-ttu-id="5ea19-133">latitudine</span><span class="sxs-lookup"><span data-stu-id="5ea19-133">latitude</span></span>
  
<span data-ttu-id="5ea19-134">longitudine</span><span class="sxs-lookup"><span data-stu-id="5ea19-134">longitude</span></span>
  
<span data-ttu-id="5ea19-135">GPS Tracker</span><span class="sxs-lookup"><span data-stu-id="5ea19-135">GPS-Tracker</span></span>
  
<span data-ttu-id="5ea19-136">GPS Koordinaten</span><span class="sxs-lookup"><span data-stu-id="5ea19-136">GPS-Koordinaten</span></span>
  
<span data-ttu-id="5ea19-137">Standort Karte</span><span class="sxs-lookup"><span data-stu-id="5ea19-137">Standort Karte</span></span>
  
<span data-ttu-id="5ea19-138">Breitengrad</span><span class="sxs-lookup"><span data-stu-id="5ea19-138">Breitengrad</span></span>
  
<span data-ttu-id="5ea19-139">Längengrad</span><span class="sxs-lookup"><span data-stu-id="5ea19-139">Längengrad</span></span>
  
## <a name="belgium"></a><span data-ttu-id="5ea19-140">Belgio</span><span class="sxs-lookup"><span data-stu-id="5ea19-140">Belgium</span></span>

### <a name="pattern"></a><span data-ttu-id="5ea19-141">Modello</span><span class="sxs-lookup"><span data-stu-id="5ea19-141">Pattern</span></span>

-  <span data-ttu-id="5ea19-142">cifre</span><span class="sxs-lookup"><span data-stu-id="5ea19-142">digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="5ea19-143">Checksum</span><span class="sxs-lookup"><span data-stu-id="5ea19-143">Checksum</span></span>

<span data-ttu-id="5ea19-144">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="5ea19-144">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="5ea19-145">Definizione</span><span class="sxs-lookup"><span data-stu-id="5ea19-145">Definition</span></span>

<span data-ttu-id="5ea19-146">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="5ea19-146">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="5ea19-147">L'espressione regolare consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="5ea19-147">The regular expression finds content that matches the pattern.</span></span>
    
- <span data-ttu-id="5ea19-148">È possibile trovare una parola chiave da.</span><span class="sxs-lookup"><span data-stu-id="5ea19-148">A keyword from is found.</span></span>
    
```
 
<Entity id="42ac9f40-0912-4ae3-b5e6-08967192dec0" patternsProximity="300" recommendedConfidence="75>">
<Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_belgium_eu_gps_data_1" />
          <Match idRef="Keywords_belgium_eu_gps_data" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_belgium_eu_gps_data_1" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_belgium_eu_gps_data_2" />
          <Match idRef="Keywords_belgium_eu_gps_data" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_belgium_eu_gps_data_2" />
        </Pattern>
</Entity>
```

## <a name="bulgaria"></a><span data-ttu-id="5ea19-149">Bulgaria</span><span class="sxs-lookup"><span data-stu-id="5ea19-149">Bulgaria</span></span>

### <a name="pattern"></a><span data-ttu-id="5ea19-150">Modello</span><span class="sxs-lookup"><span data-stu-id="5ea19-150">Pattern</span></span>

-  <span data-ttu-id="5ea19-151">cifre</span><span class="sxs-lookup"><span data-stu-id="5ea19-151">digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="5ea19-152">Checksum</span><span class="sxs-lookup"><span data-stu-id="5ea19-152">Checksum</span></span>

<span data-ttu-id="5ea19-153">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="5ea19-153">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="5ea19-154">Definizione</span><span class="sxs-lookup"><span data-stu-id="5ea19-154">Definition</span></span>

<span data-ttu-id="5ea19-155">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="5ea19-155">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="5ea19-156">L'espressione regolare consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="5ea19-156">The regular expression finds content that matches the pattern.</span></span>
    
- <span data-ttu-id="5ea19-157">È possibile trovare una parola chiave da.</span><span class="sxs-lookup"><span data-stu-id="5ea19-157">A keyword from is found.</span></span>
    
```
<Entity id="42ac9f40-0912-4ae3-b5e6-08967192dec0" patternsProximity="300" recommendedConfidence="75>
</Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_belgium_eu_gps_data_2" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_bulgaria_eu_gps_data_1" />
          <Match idRef="Keywords_bulgaria_eu_gps_data" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_bulgaria_eu_gps_data_1" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_bulgaria_eu_gps_data_2" />
          <Match idRef="Keywords_bulgaria_eu_gps_data" />
        </Pattern>
</Entity>
```

## <a name="croatia"></a><span data-ttu-id="5ea19-158">Croazia</span><span class="sxs-lookup"><span data-stu-id="5ea19-158">Croatia</span></span>

### <a name="pattern"></a><span data-ttu-id="5ea19-159">Modello</span><span class="sxs-lookup"><span data-stu-id="5ea19-159">Pattern</span></span>

-  <span data-ttu-id="5ea19-160">cifre</span><span class="sxs-lookup"><span data-stu-id="5ea19-160">digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="5ea19-161">Checksum</span><span class="sxs-lookup"><span data-stu-id="5ea19-161">Checksum</span></span>

<span data-ttu-id="5ea19-162">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="5ea19-162">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="5ea19-163">Definizione</span><span class="sxs-lookup"><span data-stu-id="5ea19-163">Definition</span></span>

<span data-ttu-id="5ea19-164">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="5ea19-164">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="5ea19-165">L'espressione regolare consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="5ea19-165">The regular expression finds content that matches the pattern.</span></span>
    
- <span data-ttu-id="5ea19-166">È possibile trovare una parola chiave da.</span><span class="sxs-lookup"><span data-stu-id="5ea19-166">A keyword from is found.</span></span>
    
```
<Entity id="42ac9f40-0912-4ae3-b5e6-08967192dec0" patternsProximity="300" recommendedConfidence="75">
<Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_croatia_eu_gps_data_1" />
          <Match idRef="Keywords_croatia_eu_gps_data" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_croatia_eu_gps_data_1" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_croatia_eu_gps_data_2" />
          <Match idRef="Keywords_croatia_eu_gps_data" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_croatia_eu_gps_data_2" />
        </Pattern>
</Entity>
```

## <a name="cyprus"></a><span data-ttu-id="5ea19-167">Cipro</span><span class="sxs-lookup"><span data-stu-id="5ea19-167">Cyprus</span></span>

### <a name="pattern"></a><span data-ttu-id="5ea19-168">Modello</span><span class="sxs-lookup"><span data-stu-id="5ea19-168">Pattern</span></span>

-  <span data-ttu-id="5ea19-169">cifre</span><span class="sxs-lookup"><span data-stu-id="5ea19-169">digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="5ea19-170">Checksum</span><span class="sxs-lookup"><span data-stu-id="5ea19-170">Checksum</span></span>

<span data-ttu-id="5ea19-171">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="5ea19-171">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="5ea19-172">Definizione</span><span class="sxs-lookup"><span data-stu-id="5ea19-172">Definition</span></span>

<span data-ttu-id="5ea19-173">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="5ea19-173">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="5ea19-174">L'espressione regolare consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="5ea19-174">The regular expression finds content that matches the pattern.</span></span>
    
- <span data-ttu-id="5ea19-175">È possibile trovare una parola chiave da.</span><span class="sxs-lookup"><span data-stu-id="5ea19-175">A keyword from is found.</span></span>
    
```
 
<Entity id="42ac9f40-0912-4ae3-b5e6-08967192dec0" patternsProximity="300" recommendedConfidence="75">
<Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_cyprus_eu_gps_data_1" />
          <Match idRef="Keywords_cyprus_eu_gps_data" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_cyprus_eu_gps_data_1" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_cyprus_eu_gps_data_2" />
          <Match idRef="Keywords_cyprus_eu_gps_data" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_cyprus_eu_gps_data_2" />
        </Pattern>
</Entity>
```

## <a name="czech-republic"></a><span data-ttu-id="5ea19-176">Repubblica Ceca</span><span class="sxs-lookup"><span data-stu-id="5ea19-176">Czech Republic</span></span>

### <a name="pattern"></a><span data-ttu-id="5ea19-177">Modello</span><span class="sxs-lookup"><span data-stu-id="5ea19-177">Pattern</span></span>

-  <span data-ttu-id="5ea19-178">cifre</span><span class="sxs-lookup"><span data-stu-id="5ea19-178">digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="5ea19-179">Checksum</span><span class="sxs-lookup"><span data-stu-id="5ea19-179">Checksum</span></span>

<span data-ttu-id="5ea19-180">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="5ea19-180">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="5ea19-181">Definizione</span><span class="sxs-lookup"><span data-stu-id="5ea19-181">Definition</span></span>

<span data-ttu-id="5ea19-182">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="5ea19-182">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
<span data-ttu-id="5ea19-183">Un criterio DLP è la certezza che è stato rilevato questo tipo di informazioni riservate % se all'interno di prossimità di caratteri:</span><span class="sxs-lookup"><span data-stu-id="5ea19-183">A DLP policy is % confident that it's detected this type of sensitive information if, within a proximity of characters:</span></span>
  
- <span data-ttu-id="5ea19-184">L'espressione regolare consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="5ea19-184">The regular expression finds content that matches the pattern.</span></span>
    
- <span data-ttu-id="5ea19-185">È possibile trovare una parola chiave da.</span><span class="sxs-lookup"><span data-stu-id="5ea19-185">A keyword from is found.</span></span>
    
```
 
<Entity id="42ac9f40-0912-4ae3-b5e6-08967192dec0" patternsProximity="300" recommendedConfidence="75">
<Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_czech_republic_eu_gps_data_1" />
          <Match idRef="Keywords_czech_republic_eu_gps_data" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_czech_republic_eu_gps_data_1" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_czech_republic_eu_gps_data_2" />
          <Match idRef="Keywords_czech_republic_eu_gps_data" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_czech_republic_eu_gps_data_2" />
        </Pattern>
</Entity>
```

## <a name="denmark"></a><span data-ttu-id="5ea19-186">Danimarca</span><span class="sxs-lookup"><span data-stu-id="5ea19-186">Denmark</span></span>

### <a name="pattern"></a><span data-ttu-id="5ea19-187">Modello</span><span class="sxs-lookup"><span data-stu-id="5ea19-187">Pattern</span></span>

-  <span data-ttu-id="5ea19-188">cifre</span><span class="sxs-lookup"><span data-stu-id="5ea19-188">digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="5ea19-189">Checksum</span><span class="sxs-lookup"><span data-stu-id="5ea19-189">Checksum</span></span>

<span data-ttu-id="5ea19-190">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="5ea19-190">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="5ea19-191">Definizione</span><span class="sxs-lookup"><span data-stu-id="5ea19-191">Definition</span></span>

<span data-ttu-id="5ea19-192">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="5ea19-192">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="5ea19-193">L'espressione regolare consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="5ea19-193">The regular expression finds content that matches the pattern.</span></span>
    
- <span data-ttu-id="5ea19-194">È possibile trovare una parola chiave da.</span><span class="sxs-lookup"><span data-stu-id="5ea19-194">A keyword from is found.</span></span>
    
```
 
<Entity id="42ac9f40-0912-4ae3-b5e6-08967192dec0" patternsProximity="300" recommendedConfidence="75">
<Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_denmark_eu_gps_data_1" />
          <Match idRef="Keywords_denmark_eu_gps_data" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_denmark_eu_gps_data_1" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_denmark_eu_gps_data_2" />
          <Match idRef="Keywords_denmark_eu_gps_data" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_denmark_eu_gps_data_2" />
        </Pattern>
</Entity>
```

## <a name="estonia"></a><span data-ttu-id="5ea19-195">Estonia</span><span class="sxs-lookup"><span data-stu-id="5ea19-195">Estonia</span></span>

### <a name="pattern"></a><span data-ttu-id="5ea19-196">Modello</span><span class="sxs-lookup"><span data-stu-id="5ea19-196">Pattern</span></span>

-  <span data-ttu-id="5ea19-197">cifre</span><span class="sxs-lookup"><span data-stu-id="5ea19-197">digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="5ea19-198">Checksum</span><span class="sxs-lookup"><span data-stu-id="5ea19-198">Checksum</span></span>

<span data-ttu-id="5ea19-199">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="5ea19-199">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="5ea19-200">Definizione</span><span class="sxs-lookup"><span data-stu-id="5ea19-200">Definition</span></span>

<span data-ttu-id="5ea19-201">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="5ea19-201">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="5ea19-202">L'espressione regolare consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="5ea19-202">The regular expression finds content that matches the pattern.</span></span>
    
- <span data-ttu-id="5ea19-203">È possibile trovare una parola chiave da.</span><span class="sxs-lookup"><span data-stu-id="5ea19-203">A keyword from is found.</span></span>
    
```
 
<Entity id="42ac9f40-0912-4ae3-b5e6-08967192dec0" patternsProximity="300" recommendedConfidence="75">
<Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_estonia_eu_gps_data_1" />
          <Match idRef="Keywords_estonia_eu_gps_data" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_estonia_eu_gps_data_1" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_estonia_eu_gps_data_2" />
          <Match idRef="Keywords_estonia_eu_gps_data" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_estonia_eu_gps_data_2" />
        </Pattern>
</Entity>
```

## <a name="finland"></a><span data-ttu-id="5ea19-204">Finlandia</span><span class="sxs-lookup"><span data-stu-id="5ea19-204">Finland</span></span>

### <a name="pattern"></a><span data-ttu-id="5ea19-205">Modello</span><span class="sxs-lookup"><span data-stu-id="5ea19-205">Pattern</span></span>

-  <span data-ttu-id="5ea19-206">cifre</span><span class="sxs-lookup"><span data-stu-id="5ea19-206">digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="5ea19-207">Checksum</span><span class="sxs-lookup"><span data-stu-id="5ea19-207">Checksum</span></span>

<span data-ttu-id="5ea19-208">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="5ea19-208">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="5ea19-209">Definizione</span><span class="sxs-lookup"><span data-stu-id="5ea19-209">Definition</span></span>

<span data-ttu-id="5ea19-210">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="5ea19-210">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="5ea19-211">L'espressione regolare consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="5ea19-211">The regular expression finds content that matches the pattern.</span></span>
    
- <span data-ttu-id="5ea19-212">È possibile trovare una parola chiave da.</span><span class="sxs-lookup"><span data-stu-id="5ea19-212">A keyword from is found.</span></span>
    
```
 
<Entity id="42ac9f40-0912-4ae3-b5e6-08967192dec0" patternsProximity="300" recommendedConfidence="75">
<Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_finland_eu_gps_data_1" />
          <Match idRef="Keywords_finland_eu_gps_data" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_finland_eu_gps_data_1" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_finland_eu_gps_data_2" />
          <Match idRef="Keywords_finland_eu_gps_data" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_finland_eu_gps_data_2" />
        </Pattern>
</Entity>
```

## <a name="france"></a><span data-ttu-id="5ea19-213">Francia</span><span class="sxs-lookup"><span data-stu-id="5ea19-213">France</span></span>

### <a name="pattern"></a><span data-ttu-id="5ea19-214">Modello</span><span class="sxs-lookup"><span data-stu-id="5ea19-214">Pattern</span></span>

-  <span data-ttu-id="5ea19-215">cifre</span><span class="sxs-lookup"><span data-stu-id="5ea19-215">digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="5ea19-216">Checksum</span><span class="sxs-lookup"><span data-stu-id="5ea19-216">Checksum</span></span>

<span data-ttu-id="5ea19-217">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="5ea19-217">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="5ea19-218">Definizione</span><span class="sxs-lookup"><span data-stu-id="5ea19-218">Definition</span></span>

<span data-ttu-id="5ea19-219">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="5ea19-219">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="5ea19-220">L'espressione regolare consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="5ea19-220">The regular expression finds content that matches the pattern.</span></span>
    
- <span data-ttu-id="5ea19-221">È possibile trovare una parola chiave da.</span><span class="sxs-lookup"><span data-stu-id="5ea19-221">A keyword from is found.</span></span>
    
```
 
<Entity id="42ac9f40-0912-4ae3-b5e6-08967192dec0" patternsProximity="300" recommendedConfidence="75">
 <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_france_eu_gps_data_1" />
          <Match idRef="Keywords_france_eu_gps_data" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_france_eu_gps_data_1" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_france_eu_gps_data_2" />
          <Match idRef="Keywords_france_eu_gps_data" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_france_eu_gps_data_2" />
        </Pattern>
</Entity>
```

## <a name="germany"></a><span data-ttu-id="5ea19-222">Germania</span><span class="sxs-lookup"><span data-stu-id="5ea19-222">Germany</span></span>

### <a name="pattern"></a><span data-ttu-id="5ea19-223">Modello</span><span class="sxs-lookup"><span data-stu-id="5ea19-223">Pattern</span></span>

-  <span data-ttu-id="5ea19-224">cifre</span><span class="sxs-lookup"><span data-stu-id="5ea19-224">digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="5ea19-225">Checksum</span><span class="sxs-lookup"><span data-stu-id="5ea19-225">Checksum</span></span>

<span data-ttu-id="5ea19-226">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="5ea19-226">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="5ea19-227">Definizione</span><span class="sxs-lookup"><span data-stu-id="5ea19-227">Definition</span></span>

<span data-ttu-id="5ea19-228">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="5ea19-228">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="5ea19-229">L'espressione regolare consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="5ea19-229">The regular expression finds content that matches the pattern.</span></span>
    
- <span data-ttu-id="5ea19-230">È possibile trovare una parola chiave da.</span><span class="sxs-lookup"><span data-stu-id="5ea19-230">A keyword from is found.</span></span>
    
```
 
<Entity id="42ac9f40-0912-4ae3-b5e6-08967192dec0" patternsProximity="300" recommendedConfidence="75">
<Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_germany_eu_gps_data_1" />
          <Match idRef="Keywords_germany_eu_gps_data" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_germany_eu_gps_data_1" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_germany_eu_gps_data_2" />
          <Match idRef="Keywords_germany_eu_gps_data" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_germany_eu_gps_data_2" />
        </Pattern>
</Entity>
```

## <a name="greece"></a><span data-ttu-id="5ea19-231">Grecia</span><span class="sxs-lookup"><span data-stu-id="5ea19-231">Greece</span></span>

### <a name="pattern"></a><span data-ttu-id="5ea19-232">Modello</span><span class="sxs-lookup"><span data-stu-id="5ea19-232">Pattern</span></span>

-  <span data-ttu-id="5ea19-233">cifre</span><span class="sxs-lookup"><span data-stu-id="5ea19-233">digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="5ea19-234">Checksum</span><span class="sxs-lookup"><span data-stu-id="5ea19-234">Checksum</span></span>

<span data-ttu-id="5ea19-235">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="5ea19-235">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="5ea19-236">Definizione</span><span class="sxs-lookup"><span data-stu-id="5ea19-236">Definition</span></span>

<span data-ttu-id="5ea19-237">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="5ea19-237">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="5ea19-238">L'espressione regolare consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="5ea19-238">The regular expression finds content that matches the pattern.</span></span>
    
- <span data-ttu-id="5ea19-239">È possibile trovare una parola chiave da.</span><span class="sxs-lookup"><span data-stu-id="5ea19-239">A keyword from is found.</span></span>
    
```
 
<Entity id="42ac9f40-0912-4ae3-b5e6-08967192dec0" patternsProximity="300" recommendedConfidence="75">
<Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_greece_eu_gps_data_1" />
          <Match idRef="Keywords_greece_eu_gps_data" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_greece_eu_gps_data_1" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_greece_eu_gps_data_2" />
          <Match idRef="Keywords_greece_eu_gps_data" />
        </Pattern>
</Entity>
```

## <a name="hungary"></a><span data-ttu-id="5ea19-240">Ungheria</span><span class="sxs-lookup"><span data-stu-id="5ea19-240">Hungary</span></span>

### <a name="pattern"></a><span data-ttu-id="5ea19-241">Modello</span><span class="sxs-lookup"><span data-stu-id="5ea19-241">Pattern</span></span>

-  <span data-ttu-id="5ea19-242">cifre</span><span class="sxs-lookup"><span data-stu-id="5ea19-242">digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="5ea19-243">Checksum</span><span class="sxs-lookup"><span data-stu-id="5ea19-243">Checksum</span></span>

<span data-ttu-id="5ea19-244">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="5ea19-244">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="5ea19-245">Definizione</span><span class="sxs-lookup"><span data-stu-id="5ea19-245">Definition</span></span>

<span data-ttu-id="5ea19-246">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="5ea19-246">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="5ea19-247">L'espressione regolare consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="5ea19-247">The regular expression finds content that matches the pattern.</span></span>
    
- <span data-ttu-id="5ea19-248">È possibile trovare una parola chiave da.</span><span class="sxs-lookup"><span data-stu-id="5ea19-248">A keyword from is found.</span></span>
    
```
 
<Entity id="42ac9f40-0912-4ae3-b5e6-08967192dec0" patternsProximity="300" recommendedConfidence="75">
<Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_hungary_eu_gps_data_1" />
          <Match idRef="Keywords_hungary_eu_gps_data" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_hungary_eu_gps_data_1" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_hungary_eu_gps_data_2" />
          <Match idRef="Keywords_hungary_eu_gps_data" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_hungary_eu_gps_data_2" />
        </Pattern>
</Entity>
```

## <a name="ireland"></a><span data-ttu-id="5ea19-249">Irlanda</span><span class="sxs-lookup"><span data-stu-id="5ea19-249">Ireland</span></span>

### <a name="pattern"></a><span data-ttu-id="5ea19-250">Modello</span><span class="sxs-lookup"><span data-stu-id="5ea19-250">Pattern</span></span>

-  <span data-ttu-id="5ea19-251">cifre</span><span class="sxs-lookup"><span data-stu-id="5ea19-251">digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="5ea19-252">Checksum</span><span class="sxs-lookup"><span data-stu-id="5ea19-252">Checksum</span></span>

<span data-ttu-id="5ea19-253">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="5ea19-253">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="5ea19-254">Definizione</span><span class="sxs-lookup"><span data-stu-id="5ea19-254">Definition</span></span>

<span data-ttu-id="5ea19-255">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="5ea19-255">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="5ea19-256">L'espressione regolare consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="5ea19-256">The regular expression finds content that matches the pattern.</span></span>
    
- <span data-ttu-id="5ea19-257">È possibile trovare una parola chiave da.</span><span class="sxs-lookup"><span data-stu-id="5ea19-257">A keyword from is found.</span></span>
    
```
 
<Entity id="42ac9f40-0912-4ae3-b5e6-08967192dec0" patternsProximity="300" recommendedConfidence="75">
<Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_ireland_eu_gps_data_1" />
          <Match idRef="Keywords_ireland_eu_gps_data" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_ireland_eu_gps_data_1" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_ireland_eu_gps_data_2" />
          <Match idRef="Keywords_ireland_eu_gps_data" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_ireland_eu_gps_data_2" />
        </Pattern>
</Entity>
```

## <a name="italy"></a><span data-ttu-id="5ea19-258">Italia</span><span class="sxs-lookup"><span data-stu-id="5ea19-258">Italy</span></span>

### <a name="pattern"></a><span data-ttu-id="5ea19-259">Modello</span><span class="sxs-lookup"><span data-stu-id="5ea19-259">Pattern</span></span>

-  <span data-ttu-id="5ea19-260">cifre</span><span class="sxs-lookup"><span data-stu-id="5ea19-260">digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="5ea19-261">Checksum</span><span class="sxs-lookup"><span data-stu-id="5ea19-261">Checksum</span></span>

<span data-ttu-id="5ea19-262">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="5ea19-262">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="5ea19-263">Definizione</span><span class="sxs-lookup"><span data-stu-id="5ea19-263">Definition</span></span>

<span data-ttu-id="5ea19-264">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="5ea19-264">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="5ea19-265">L'espressione regolare consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="5ea19-265">The regular expression finds content that matches the pattern.</span></span>
    
- <span data-ttu-id="5ea19-266">È possibile trovare una parola chiave da.</span><span class="sxs-lookup"><span data-stu-id="5ea19-266">A keyword from is found.</span></span>
    
```
 <Entity id="42ac9f40-0912-4ae3-b5e6-08967192dec0" patternsProximity="300" recommendedConfidence="75">
<Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_italy_eu_gps_data_1" />
          <Match idRef="Keywords_italy_eu_gps_data" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_italy_eu_gps_data_1" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_italy_eu_gps_data_2" />
          <Match idRef="Keywords_italy_eu_gps_data" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_italy_eu_gps_data_2" />
        </Pattern>
</Entity>
```

## <a name="latvia"></a><span data-ttu-id="5ea19-267">Lettonia</span><span class="sxs-lookup"><span data-stu-id="5ea19-267">Latvia</span></span>

### <a name="pattern"></a><span data-ttu-id="5ea19-268">Modello</span><span class="sxs-lookup"><span data-stu-id="5ea19-268">Pattern</span></span>

-  <span data-ttu-id="5ea19-269">cifre</span><span class="sxs-lookup"><span data-stu-id="5ea19-269">digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="5ea19-270">Checksum</span><span class="sxs-lookup"><span data-stu-id="5ea19-270">Checksum</span></span>

<span data-ttu-id="5ea19-271">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="5ea19-271">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="5ea19-272">Definizione</span><span class="sxs-lookup"><span data-stu-id="5ea19-272">Definition</span></span>

<span data-ttu-id="5ea19-273">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="5ea19-273">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="5ea19-274">L'espressione regolare consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="5ea19-274">The regular expression finds content that matches the pattern.</span></span>
    
- <span data-ttu-id="5ea19-275">È possibile trovare una parola chiave da.</span><span class="sxs-lookup"><span data-stu-id="5ea19-275">A keyword from is found.</span></span>
    
```
 <Entity id="42ac9f40-0912-4ae3-b5e6-08967192dec0" patternsProximity="300" recommendedConfidence="75">
<Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_latvia_eu_gps_data_1" />
          <Match idRef="Keywords_latvia_eu_gps_data" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_latvia_eu_gps_data_1" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_latvia_eu_gps_data_2" />
          <Match idRef="Keywords_latvia_eu_gps_data" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_latvia_eu_gps_data_2" />
        </Pattern>
</Entity>
```

## <a name="lithuania"></a><span data-ttu-id="5ea19-276">Lituania</span><span class="sxs-lookup"><span data-stu-id="5ea19-276">Lithuania</span></span>

### <a name="pattern"></a><span data-ttu-id="5ea19-277">Modello</span><span class="sxs-lookup"><span data-stu-id="5ea19-277">Pattern</span></span>

-  <span data-ttu-id="5ea19-278">cifre</span><span class="sxs-lookup"><span data-stu-id="5ea19-278">digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="5ea19-279">Checksum</span><span class="sxs-lookup"><span data-stu-id="5ea19-279">Checksum</span></span>

<span data-ttu-id="5ea19-280">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="5ea19-280">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="5ea19-281">Definizione</span><span class="sxs-lookup"><span data-stu-id="5ea19-281">Definition</span></span>

<span data-ttu-id="5ea19-282">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="5ea19-282">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="5ea19-283">L'espressione regolare consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="5ea19-283">The regular expression finds content that matches the pattern.</span></span>
    
- <span data-ttu-id="5ea19-284">È possibile trovare una parola chiave da.</span><span class="sxs-lookup"><span data-stu-id="5ea19-284">A keyword from is found.</span></span>
    
```
 <Entity id="42ac9f40-0912-4ae3-b5e6-08967192dec0" patternsProximity="300" recommendedConfidence="75">
<Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_lithuania_eu_gps_data_1" />
          <Match idRef="Keywords_lithuania_eu_gps_data" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_lithuania_eu_gps_data_1" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_lithuania_eu_gps_data_2" />
          <Match idRef="Keywords_lithuania_eu_gps_data" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_lithuania_eu_gps_data_2" />
        </Pattern>
</Entity>
```

## <a name="luxemburg"></a><span data-ttu-id="5ea19-285">Lussemburgo</span><span class="sxs-lookup"><span data-stu-id="5ea19-285">Luxemburg</span></span>

### <a name="pattern"></a><span data-ttu-id="5ea19-286">Modello</span><span class="sxs-lookup"><span data-stu-id="5ea19-286">Pattern</span></span>

-  <span data-ttu-id="5ea19-287">cifre</span><span class="sxs-lookup"><span data-stu-id="5ea19-287">digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="5ea19-288">Checksum</span><span class="sxs-lookup"><span data-stu-id="5ea19-288">Checksum</span></span>

<span data-ttu-id="5ea19-289">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="5ea19-289">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="5ea19-290">Definizione</span><span class="sxs-lookup"><span data-stu-id="5ea19-290">Definition</span></span>

<span data-ttu-id="5ea19-291">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="5ea19-291">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="5ea19-292">L'espressione regolare consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="5ea19-292">The regular expression finds content that matches the pattern.</span></span>
    
- <span data-ttu-id="5ea19-293">È possibile trovare una parola chiave da.</span><span class="sxs-lookup"><span data-stu-id="5ea19-293">A keyword from is found.</span></span>
    
```
 <Entity id="42ac9f40-0912-4ae3-b5e6-08967192dec0" patternsProximity="300" recommendedConfidence="75">
<Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_luxemburg_eu_gps_data_1" />
          <Match idRef="Keywords_luxemburg_eu_gps_data" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_luxemburg_eu_gps_data_1" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_luxemburg_eu_gps_data_2" />
          <Match idRef="Keywords_luxemburg_eu_gps_data" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_luxemburg_eu_gps_data_2" />
        </Pattern>
</Entity>
```

## <a name="malta"></a><span data-ttu-id="5ea19-294">Malta</span><span class="sxs-lookup"><span data-stu-id="5ea19-294">Malta</span></span>

### <a name="pattern"></a><span data-ttu-id="5ea19-295">Modello</span><span class="sxs-lookup"><span data-stu-id="5ea19-295">Pattern</span></span>

-  <span data-ttu-id="5ea19-296">cifre</span><span class="sxs-lookup"><span data-stu-id="5ea19-296">digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="5ea19-297">Checksum</span><span class="sxs-lookup"><span data-stu-id="5ea19-297">Checksum</span></span>

<span data-ttu-id="5ea19-298">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="5ea19-298">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="5ea19-299">Definizione</span><span class="sxs-lookup"><span data-stu-id="5ea19-299">Definition</span></span>

<span data-ttu-id="5ea19-300">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="5ea19-300">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="5ea19-301">L'espressione regolare consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="5ea19-301">The regular expression finds content that matches the pattern.</span></span>
    
- <span data-ttu-id="5ea19-302">È possibile trovare una parola chiave da.</span><span class="sxs-lookup"><span data-stu-id="5ea19-302">A keyword from is found.</span></span>
    
```
<Entity id="42ac9f40-0912-4ae3-b5e6-08967192dec0" patternsProximity="300" recommendedConfidence="75">
<Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_malta_eu_gps_data_1" />
          <Match idRef="Keywords_malta_eu_gps_data" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_malta_eu_gps_data_1" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_malta_eu_gps_data_2" />
          <Match idRef="Keywords_malta_eu_gps_data" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_malta_eu_gps_data_2" />
        </Pattern>
</Entity>
```

## <a name="netherlands"></a><span data-ttu-id="5ea19-303">Paesi Bassi</span><span class="sxs-lookup"><span data-stu-id="5ea19-303">Netherlands</span></span>

### <a name="pattern"></a><span data-ttu-id="5ea19-304">Modello</span><span class="sxs-lookup"><span data-stu-id="5ea19-304">Pattern</span></span>

-  <span data-ttu-id="5ea19-305">cifre</span><span class="sxs-lookup"><span data-stu-id="5ea19-305">digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="5ea19-306">Checksum</span><span class="sxs-lookup"><span data-stu-id="5ea19-306">Checksum</span></span>

<span data-ttu-id="5ea19-307">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="5ea19-307">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="5ea19-308">Definizione</span><span class="sxs-lookup"><span data-stu-id="5ea19-308">Definition</span></span>

<span data-ttu-id="5ea19-309">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="5ea19-309">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="5ea19-310">L'espressione regolare consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="5ea19-310">The regular expression finds content that matches the pattern.</span></span>
    
- <span data-ttu-id="5ea19-311">È possibile trovare una parola chiave da.</span><span class="sxs-lookup"><span data-stu-id="5ea19-311">A keyword from is found.</span></span>
    
```
 <Entity id="42ac9f40-0912-4ae3-b5e6-08967192dec0" patternsProximity="300" recommendedConfidence="75">
<Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_netherlands_eu_gps_data_1" />
          <Match idRef="Keywords_netherlands_eu_gps_data" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_netherlands_eu_gps_data_1" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_netherlands_eu_gps_data_2" />
          <Match idRef="Keywords_netherlands_eu_gps_data" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_netherlands_eu_gps_data_2" />
        </Pattern>
</Entity>
```

## <a name="poland"></a><span data-ttu-id="5ea19-312">Polonia</span><span class="sxs-lookup"><span data-stu-id="5ea19-312">Poland</span></span>

### <a name="pattern"></a><span data-ttu-id="5ea19-313">Modello</span><span class="sxs-lookup"><span data-stu-id="5ea19-313">Pattern</span></span>

-  <span data-ttu-id="5ea19-314">cifre</span><span class="sxs-lookup"><span data-stu-id="5ea19-314">digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="5ea19-315">Checksum</span><span class="sxs-lookup"><span data-stu-id="5ea19-315">Checksum</span></span>

<span data-ttu-id="5ea19-316">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="5ea19-316">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="5ea19-317">Definizione</span><span class="sxs-lookup"><span data-stu-id="5ea19-317">Definition</span></span>

<span data-ttu-id="5ea19-318">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="5ea19-318">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="5ea19-319">L'espressione regolare consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="5ea19-319">The regular expression finds content that matches the pattern.</span></span>
    
- <span data-ttu-id="5ea19-320">È possibile trovare una parola chiave da.</span><span class="sxs-lookup"><span data-stu-id="5ea19-320">A keyword from is found.</span></span>
    
```
 <Entity id="42ac9f40-0912-4ae3-b5e6-08967192dec0" patternsProximity="300" recommendedConfidence="75">
<Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_poland_eu_gps_data_1" />
          <Match idRef="Keywords_poland_eu_gps_data" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_poland_eu_gps_data_1" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_poland_eu_gps_data_2" />
          <Match idRef="Keywords_poland_eu_gps_data" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_poland_eu_gps_data_2" />
        </Pattern>
</Entity>
```

## <a name="portugal"></a><span data-ttu-id="5ea19-321">Portogallo</span><span class="sxs-lookup"><span data-stu-id="5ea19-321">Portugal</span></span>

### <a name="pattern"></a><span data-ttu-id="5ea19-322">Modello</span><span class="sxs-lookup"><span data-stu-id="5ea19-322">Pattern</span></span>

-  <span data-ttu-id="5ea19-323">cifre</span><span class="sxs-lookup"><span data-stu-id="5ea19-323">digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="5ea19-324">Checksum</span><span class="sxs-lookup"><span data-stu-id="5ea19-324">Checksum</span></span>

<span data-ttu-id="5ea19-325">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="5ea19-325">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="5ea19-326">Definizione</span><span class="sxs-lookup"><span data-stu-id="5ea19-326">Definition</span></span>

<span data-ttu-id="5ea19-327">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="5ea19-327">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="5ea19-328">L'espressione regolare consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="5ea19-328">The regular expression finds content that matches the pattern.</span></span>
    
- <span data-ttu-id="5ea19-329">È possibile trovare una parola chiave da.</span><span class="sxs-lookup"><span data-stu-id="5ea19-329">A keyword from is found.</span></span>
    
```
 <Entity id="42ac9f40-0912-4ae3-b5e6-08967192dec0" patternsProximity="300" recommendedConfidence="75">
<Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_portugal_eu_gps_data_1" />
          <Match idRef="Keywords_portugal_eu_gps_data" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_portugal_eu_gps_data_1" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_portugal_eu_gps_data_2" />
          <Match idRef="Keywords_portugal_eu_gps_data" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_portugal_eu_gps_data_2" />
        </Pattern>
</Entity>
```

## <a name="romania"></a><span data-ttu-id="5ea19-330">Romania</span><span class="sxs-lookup"><span data-stu-id="5ea19-330">Romania</span></span>

### <a name="pattern"></a><span data-ttu-id="5ea19-331">Modello</span><span class="sxs-lookup"><span data-stu-id="5ea19-331">Pattern</span></span>

-  <span data-ttu-id="5ea19-332">cifre</span><span class="sxs-lookup"><span data-stu-id="5ea19-332">digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="5ea19-333">Checksum</span><span class="sxs-lookup"><span data-stu-id="5ea19-333">Checksum</span></span>

<span data-ttu-id="5ea19-334">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="5ea19-334">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="5ea19-335">Definizione</span><span class="sxs-lookup"><span data-stu-id="5ea19-335">Definition</span></span>

<span data-ttu-id="5ea19-336">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="5ea19-336">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="5ea19-337">L'espressione regolare consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="5ea19-337">The regular expression finds content that matches the pattern.</span></span>
    
- <span data-ttu-id="5ea19-338">È possibile trovare una parola chiave da.</span><span class="sxs-lookup"><span data-stu-id="5ea19-338">A keyword from is found.</span></span>
    
```
 <Entity id="42ac9f40-0912-4ae3-b5e6-08967192dec0" patternsProximity="300" recommendedConfidence="75">
<Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_romania_eu_gps_data_1" />
          <Match idRef="Keywords_romania_eu_gps_data" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_romania_eu_gps_data_1" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_romania_eu_gps_data_2" />
          <Match idRef="Keywords_romania_eu_gps_data" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_romania_eu_gps_data_2" />
        </Pattern>
</Entity>
```

## <a name="slovakia"></a><span data-ttu-id="5ea19-339">Slovacchia</span><span class="sxs-lookup"><span data-stu-id="5ea19-339">Slovakia</span></span>

### <a name="pattern"></a><span data-ttu-id="5ea19-340">Modello</span><span class="sxs-lookup"><span data-stu-id="5ea19-340">Pattern</span></span>

-  <span data-ttu-id="5ea19-341">cifre</span><span class="sxs-lookup"><span data-stu-id="5ea19-341">digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="5ea19-342">Checksum</span><span class="sxs-lookup"><span data-stu-id="5ea19-342">Checksum</span></span>

<span data-ttu-id="5ea19-343">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="5ea19-343">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="5ea19-344">Definizione</span><span class="sxs-lookup"><span data-stu-id="5ea19-344">Definition</span></span>

<span data-ttu-id="5ea19-345">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="5ea19-345">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="5ea19-346">L'espressione regolare consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="5ea19-346">The regular expression finds content that matches the pattern.</span></span>
    
- <span data-ttu-id="5ea19-347">È possibile trovare una parola chiave da.</span><span class="sxs-lookup"><span data-stu-id="5ea19-347">A keyword from is found.</span></span>
    
```
 <Entity id="42ac9f40-0912-4ae3-b5e6-08967192dec0" patternsProximity="300" recommendedConfidence="75">
<Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovakia_eu_gps_data_1" />
          <Match idRef="Keywords_slovakia_eu_gps_data" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_slovakia_eu_gps_data_1" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovakia_eu_gps_data_2" />
          <Match idRef="Keywords_slovakia_eu_gps_data" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_slovakia_eu_gps_data_2" />
        </Pattern>
</Entity>
```

## <a name="slovenia"></a><span data-ttu-id="5ea19-348">Slovenia</span><span class="sxs-lookup"><span data-stu-id="5ea19-348">Slovenia</span></span>

### <a name="pattern"></a><span data-ttu-id="5ea19-349">Modello</span><span class="sxs-lookup"><span data-stu-id="5ea19-349">Pattern</span></span>

-  <span data-ttu-id="5ea19-350">cifre</span><span class="sxs-lookup"><span data-stu-id="5ea19-350">digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="5ea19-351">Checksum</span><span class="sxs-lookup"><span data-stu-id="5ea19-351">Checksum</span></span>

<span data-ttu-id="5ea19-352">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="5ea19-352">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="5ea19-353">Definizione</span><span class="sxs-lookup"><span data-stu-id="5ea19-353">Definition</span></span>

<span data-ttu-id="5ea19-354">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="5ea19-354">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="5ea19-355">L'espressione regolare consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="5ea19-355">The regular expression finds content that matches the pattern.</span></span>
    
- <span data-ttu-id="5ea19-356">È possibile trovare una parola chiave da.</span><span class="sxs-lookup"><span data-stu-id="5ea19-356">A keyword from is found.</span></span>
    
```
 <Entity id="42ac9f40-0912-4ae3-b5e6-08967192dec0" patternsProximity="300" recommendedConfidence="75">
<Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovenia_eu_gps_data_1" />
          <Match idRef="Keywords_slovenia_eu_gps_data" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_slovenia_eu_gps_data_1" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovenia_eu_gps_data_2" />
          <Match idRef="Keywords_slovenia_eu_gps_data" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_slovenia_eu_gps_data_2" />
        </Pattern>
</Entity>
```

## <a name="spain"></a><span data-ttu-id="5ea19-357">Spagna</span><span class="sxs-lookup"><span data-stu-id="5ea19-357">Spain</span></span>

### <a name="pattern"></a><span data-ttu-id="5ea19-358">Modello</span><span class="sxs-lookup"><span data-stu-id="5ea19-358">Pattern</span></span>

-  <span data-ttu-id="5ea19-359">cifre</span><span class="sxs-lookup"><span data-stu-id="5ea19-359">digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="5ea19-360">Checksum</span><span class="sxs-lookup"><span data-stu-id="5ea19-360">Checksum</span></span>

<span data-ttu-id="5ea19-361">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="5ea19-361">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="5ea19-362">Definizione</span><span class="sxs-lookup"><span data-stu-id="5ea19-362">Definition</span></span>

<span data-ttu-id="5ea19-363">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="5ea19-363">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="5ea19-364">L'espressione regolare consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="5ea19-364">The regular expression finds content that matches the pattern.</span></span>
    
- <span data-ttu-id="5ea19-365">È possibile trovare una parola chiave da.</span><span class="sxs-lookup"><span data-stu-id="5ea19-365">A keyword from is found.</span></span>
    
```
 <Entity id="42ac9f40-0912-4ae3-b5e6-08967192dec0" patternsProximity="300" recommendedConfidence="75">
<Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_spain_eu_gps_data_1" />
          <Match idRef="Keywords_spain_eu_gps_data" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_spain_eu_gps_data_1" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_spain_eu_gps_data_2" />
          <Match idRef="Keywords_spain_eu_gps_data" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_spain_eu_gps_data_2" />
        </Pattern>
</Entity>
```

## <a name="sweden"></a><span data-ttu-id="5ea19-366">Svezia</span><span class="sxs-lookup"><span data-stu-id="5ea19-366">Sweden</span></span>

### <a name="pattern"></a><span data-ttu-id="5ea19-367">Modello</span><span class="sxs-lookup"><span data-stu-id="5ea19-367">Pattern</span></span>

-  <span data-ttu-id="5ea19-368">cifre</span><span class="sxs-lookup"><span data-stu-id="5ea19-368">digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="5ea19-369">Checksum</span><span class="sxs-lookup"><span data-stu-id="5ea19-369">Checksum</span></span>

<span data-ttu-id="5ea19-370">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="5ea19-370">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="5ea19-371">Definizione</span><span class="sxs-lookup"><span data-stu-id="5ea19-371">Definition</span></span>

<span data-ttu-id="5ea19-372">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="5ea19-372">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="5ea19-373">L'espressione regolare consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="5ea19-373">The regular expression finds content that matches the pattern.</span></span>
    
- <span data-ttu-id="5ea19-374">È possibile trovare una parola chiave da.</span><span class="sxs-lookup"><span data-stu-id="5ea19-374">A keyword from is found.</span></span>
    
```
 <Entity id="42ac9f40-0912-4ae3-b5e6-08967192dec0" patternsProximity="300" recommendedConfidence="75">
<Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_sweden_eu_gps_data_1" />
          <Match idRef="Keywords_sweden_eu_gps_data" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_sweden_eu_gps_data_1" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_sweden_eu_gps_data_2" />
          <Match idRef="Keywords_sweden_eu_gps_data" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_sweden_eu_gps_data_2" />
        </Pattern>
</Entity>
```

## <a name="uk"></a><span data-ttu-id="5ea19-375">REGNO UNITO</span><span class="sxs-lookup"><span data-stu-id="5ea19-375">UK</span></span>

### <a name="pattern"></a><span data-ttu-id="5ea19-376">Modello</span><span class="sxs-lookup"><span data-stu-id="5ea19-376">Pattern</span></span>

-  <span data-ttu-id="5ea19-377">cifre</span><span class="sxs-lookup"><span data-stu-id="5ea19-377">digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="5ea19-378">Checksum</span><span class="sxs-lookup"><span data-stu-id="5ea19-378">Checksum</span></span>

<span data-ttu-id="5ea19-379">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="5ea19-379">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="5ea19-380">Definizione</span><span class="sxs-lookup"><span data-stu-id="5ea19-380">Definition</span></span>

<span data-ttu-id="5ea19-381">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="5ea19-381">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="5ea19-382">L'espressione regolare consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="5ea19-382">The regular expression finds content that matches the pattern.</span></span>
    
- <span data-ttu-id="5ea19-383">È possibile trovare una parola chiave da.</span><span class="sxs-lookup"><span data-stu-id="5ea19-383">A keyword from is found.</span></span>
    
```
 <Entity id="42ac9f40-0912-4ae3-b5e6-08967192dec0" patternsProximity="300" recommendedConfidence="75">
<Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_uk_eu_gps_data_1" />
          <Match idRef="Keywords_uk_eu_gps_data" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_uk_eu_gps_data_1" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_uk_eu_gps_data_2" />
          <Match idRef="Keywords_uk_eu_gps_data" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_uk_eu_gps_data_2" />
        </Pattern>
</Entity>
```

## <a name="see-also"></a><span data-ttu-id="5ea19-384">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5ea19-384">See also</span></span>

[<span data-ttu-id="5ea19-385">Cosa individuano i tipi di informazioni riservate</span><span class="sxs-lookup"><span data-stu-id="5ea19-385">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)

