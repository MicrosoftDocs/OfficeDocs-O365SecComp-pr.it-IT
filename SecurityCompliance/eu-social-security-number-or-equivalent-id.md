---
title: Codice di preVidenza sociale dell'Unione europea o ID equivalente
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 8/17/2018
ms.audience: Admin
ms.topic: reference
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
description: In questo argomento viene illustrato l'aspetto di un criterio di prevenzione della perdita di dati (DLP) quando rileva il numero di preVidenza sociale dell'Unione europea o il tipo di informazioni riservate ID equivalente. Questo tipo di informazioni riservate definisce modelli, parole chiave e altre evidenze diverse per ogni paese.
ms.openlocfilehash: c0c808eafa52209c79f3b4e8a2113f587fd8a771
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "32255554"
---
# <a name="eu-social-security-number-or-equivalent-id"></a><span data-ttu-id="758f5-104">Codice di preVidenza sociale dell'Unione europea o ID equivalente</span><span class="sxs-lookup"><span data-stu-id="758f5-104">EU Social Security Number or Equivalent ID</span></span>

<span data-ttu-id="758f5-105">In questo argomento viene illustrato l'aspetto di un criterio di prevenzione della perdita di dati (DLP, Data Loss Prevention), quando viene rilevato il codice fiscale dell'Unione europea (SSN) o il tipo di informazioni sensibili ID equivalente.</span><span class="sxs-lookup"><span data-stu-id="758f5-105">This topic shows what a data loss prevention (DLP) policy looks for when it detects the EU Social Security Number (SSN) or Equivalent ID sensitive information type.</span></span> <span data-ttu-id="758f5-106">Questo tipo di informazioni riservate definisce modelli, parole chiave e altre evidenze diverse per ogni paese.</span><span class="sxs-lookup"><span data-stu-id="758f5-106">This sensitive information type defines different patterns, keywords, and other evidence for each country.</span></span>
  
## <a name="austria"></a><span data-ttu-id="758f5-107">Austria</span><span class="sxs-lookup"><span data-stu-id="758f5-107">Austria</span></span>

### <a name="format"></a><span data-ttu-id="758f5-108">Formato</span><span class="sxs-lookup"><span data-stu-id="758f5-108">Format</span></span>

<span data-ttu-id="758f5-109">10 cifre nel formato specificato</span><span class="sxs-lookup"><span data-stu-id="758f5-109">10 digits in the specified format</span></span>
  
### <a name="pattern"></a><span data-ttu-id="758f5-110">Modello</span><span class="sxs-lookup"><span data-stu-id="758f5-110">Pattern</span></span>

<span data-ttu-id="758f5-111">10 cifre:</span><span class="sxs-lookup"><span data-stu-id="758f5-111">10 digits:</span></span>
  
-  <span data-ttu-id="758f5-112">Tre cifre che corrispondono a un numero di serie</span><span class="sxs-lookup"><span data-stu-id="758f5-112">Three digits that correspond to a serial number</span></span> 
    
- <span data-ttu-id="758f5-113">Una cifra di controllo</span><span class="sxs-lookup"><span data-stu-id="758f5-113">One check digit</span></span>
    
- <span data-ttu-id="758f5-114">Sei cifre che corrispondono alla data di nascita (GGMMAA)</span><span class="sxs-lookup"><span data-stu-id="758f5-114">Six digits that correspond to the birth date (DDMMYY)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="758f5-115">Checksum</span><span class="sxs-lookup"><span data-stu-id="758f5-115">Checksum</span></span>

<span data-ttu-id="758f5-116">Sì</span><span class="sxs-lookup"><span data-stu-id="758f5-116">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="758f5-117">Definizione</span><span class="sxs-lookup"><span data-stu-id="758f5-117">Definition</span></span>

<span data-ttu-id="758f5-118">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="758f5-118">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="758f5-119">La funzione `Func_austria_eu_ssn_or_equivalent` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="758f5-119">The function  `Func_austria_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="758f5-120">Viene trovata una `Keywords_austria_eu_ssn_or_equivalent` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="758f5-120">A keyword from  `Keywords_austria_eu_ssn_or_equivalent` is found.</span></span> 
    
<span data-ttu-id="758f5-121">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="758f5-121">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="758f5-122">La funzione `Func_austria_eu_ssn_or_equivalent` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="758f5-122">The function  `Func_austria_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU SSN or Equivalent Number -->
<Entity id="d24e32a4-c0bb-4ba8-899d-6303b95742d9" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_austria_eu_ssn_or_equivalent" />
          <Match idRef="Keywords_austria_eu_ssn_or_equivalent" />
        </Pattern>
<Pattern confidenceLevel="75">
            <IdMatch idRef="Func_austria_eu_ssn_or_equivalent" />
          </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="758f5-123">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="758f5-123">Keywords</span></span>

#### <a name="keywordsaustriaeussnorequivalent"></a><span data-ttu-id="758f5-124">Keywords_austria_eu_ssn_or_equivalent</span><span class="sxs-lookup"><span data-stu-id="758f5-124">Keywords_austria_eu_ssn_or_equivalent</span></span>

<span data-ttu-id="758f5-125">previdenza sociale No</span><span class="sxs-lookup"><span data-stu-id="758f5-125">social security no</span></span>
  
<span data-ttu-id="758f5-126">social security number</span><span class="sxs-lookup"><span data-stu-id="758f5-126">social security number</span></span>
  
<span data-ttu-id="758f5-127">social security code</span><span class="sxs-lookup"><span data-stu-id="758f5-127">social security code</span></span>
  
<span data-ttu-id="758f5-128">numero assicurativo</span><span class="sxs-lookup"><span data-stu-id="758f5-128">insurance number</span></span>
  
<span data-ttu-id="758f5-129">SSN austriaco</span><span class="sxs-lookup"><span data-stu-id="758f5-129">austrian ssn</span></span>
  
<span data-ttu-id="758f5-130">SSN</span><span class="sxs-lookup"><span data-stu-id="758f5-130">ssn#</span></span>
  
<span data-ttu-id="758f5-131">SSN</span><span class="sxs-lookup"><span data-stu-id="758f5-131">ssn</span></span>
  
<span data-ttu-id="758f5-132">codice assicurativo</span><span class="sxs-lookup"><span data-stu-id="758f5-132">insurance code</span></span>
  
<span data-ttu-id="758f5-133">codice assicurativo #</span><span class="sxs-lookup"><span data-stu-id="758f5-133">insurance code#</span></span>
  
<span data-ttu-id="758f5-134">socialsecurityno #</span><span class="sxs-lookup"><span data-stu-id="758f5-134">socialsecurityno#</span></span>
  
<span data-ttu-id="758f5-135">sozialversicherungsnummer</span><span class="sxs-lookup"><span data-stu-id="758f5-135">sozialversicherungsnummer</span></span>
  
<span data-ttu-id="758f5-136">soziale Sicherheit kein</span><span class="sxs-lookup"><span data-stu-id="758f5-136">soziale sicherheit kein</span></span>
  
<span data-ttu-id="758f5-137">Versicherungsnummer</span><span class="sxs-lookup"><span data-stu-id="758f5-137">versicherungsnummer</span></span>
  
## <a name="belgium"></a><span data-ttu-id="758f5-138">Belgio</span><span class="sxs-lookup"><span data-stu-id="758f5-138">Belgium</span></span>

### <a name="format"></a><span data-ttu-id="758f5-139">Formato</span><span class="sxs-lookup"><span data-stu-id="758f5-139">Format</span></span>

<span data-ttu-id="758f5-140">11 cifre senza spazi o delimitatori</span><span class="sxs-lookup"><span data-stu-id="758f5-140">11 digits without spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="758f5-141">Modello</span><span class="sxs-lookup"><span data-stu-id="758f5-141">Pattern</span></span>

<span data-ttu-id="758f5-142">11 cifre</span><span class="sxs-lookup"><span data-stu-id="758f5-142">11 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="758f5-143">Checksum</span><span class="sxs-lookup"><span data-stu-id="758f5-143">Checksum</span></span>

<span data-ttu-id="758f5-144">Sì</span><span class="sxs-lookup"><span data-stu-id="758f5-144">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="758f5-145">Definizione</span><span class="sxs-lookup"><span data-stu-id="758f5-145">Definition</span></span>

<span data-ttu-id="758f5-146">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="758f5-146">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="758f5-147">La funzione `Func_belgium_eu_ssn_or_equivalent` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="758f5-147">The function  `Func_belgium_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="758f5-148">Viene trovata una `Keywords_belgium_eu_ssn_or_equivalent` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="758f5-148">A keyword from  `Keywords_belgium_eu_ssn_or_equivalent` is found.</span></span> 
    
<span data-ttu-id="758f5-149">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="758f5-149">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="758f5-150">La funzione `Func_belgium_eu_ssn_or_equivalent` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="758f5-150">The function  `Func_belgium_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU SSN or Equivalent Number -->
<Entity id="d24e32a4-c0bb-4ba8-899d-6303b95742d9" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_belgium_eu_ssn_or_equivalent" />
          <Match idRef="Keywords_belgium_eu_ssn_or_equivalent" />
        </Pattern> 
       <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_belgium_eu_ssn_or_equivalent" />
        </Pattern>      
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="758f5-151">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="758f5-151">Keywords</span></span>

#### <a name="keywordsbelgiumeussnorequivalent"></a><span data-ttu-id="758f5-152">Keywords_belgium_eu_ssn_or_equivalent</span><span class="sxs-lookup"><span data-stu-id="758f5-152">Keywords_belgium_eu_ssn_or_equivalent</span></span>

<span data-ttu-id="758f5-153">numero nazionale belga</span><span class="sxs-lookup"><span data-stu-id="758f5-153">belgian national number</span></span>
  
<span data-ttu-id="758f5-154">numero nazionale</span><span class="sxs-lookup"><span data-stu-id="758f5-154">national number</span></span>
  
<span data-ttu-id="758f5-155">social security number</span><span class="sxs-lookup"><span data-stu-id="758f5-155">social security number</span></span>
  
<span data-ttu-id="758f5-156">nationalnumber #</span><span class="sxs-lookup"><span data-stu-id="758f5-156">nationalnumber#</span></span>
  
<span data-ttu-id="758f5-157">SSN</span><span class="sxs-lookup"><span data-stu-id="758f5-157">ssn#</span></span>
  
<span data-ttu-id="758f5-158">SSN</span><span class="sxs-lookup"><span data-stu-id="758f5-158">ssn</span></span>
  
<span data-ttu-id="758f5-159">nationalnumber</span><span class="sxs-lookup"><span data-stu-id="758f5-159">nationalnumber</span></span>
  
<span data-ttu-id="758f5-160">BNN</span><span class="sxs-lookup"><span data-stu-id="758f5-160">bnn#</span></span>
  
<span data-ttu-id="758f5-161">BNN</span><span class="sxs-lookup"><span data-stu-id="758f5-161">bnn</span></span>
  
<span data-ttu-id="758f5-162">numero ID personale</span><span class="sxs-lookup"><span data-stu-id="758f5-162">personal id number</span></span>
  
<span data-ttu-id="758f5-163">personalidnumber #</span><span class="sxs-lookup"><span data-stu-id="758f5-163">personalidnumber#</span></span>
  
<span data-ttu-id="758f5-164">numéro nazionale</span><span class="sxs-lookup"><span data-stu-id="758f5-164">numéro national</span></span>
  
<span data-ttu-id="758f5-165">numéro de sécurité</span><span class="sxs-lookup"><span data-stu-id="758f5-165">numéro de sécurité</span></span>
  
<span data-ttu-id="758f5-166">numéro d'assuré</span><span class="sxs-lookup"><span data-stu-id="758f5-166">numéro d'assuré</span></span>
  
<span data-ttu-id="758f5-167">identificazione nazionale</span><span class="sxs-lookup"><span data-stu-id="758f5-167">identifiant national</span></span>
  
<span data-ttu-id="758f5-168">identifiantnational #</span><span class="sxs-lookup"><span data-stu-id="758f5-168">identifiantnational#</span></span>
  
<span data-ttu-id="758f5-169">numéronational #</span><span class="sxs-lookup"><span data-stu-id="758f5-169">numéronational#</span></span>
  
## <a name="croatia"></a><span data-ttu-id="758f5-170">Croazia</span><span class="sxs-lookup"><span data-stu-id="758f5-170">Croatia</span></span>

### <a name="format"></a><span data-ttu-id="758f5-171">Formato</span><span class="sxs-lookup"><span data-stu-id="758f5-171">Format</span></span>

<span data-ttu-id="758f5-172">11 cifre senza spazi e delimitatori</span><span class="sxs-lookup"><span data-stu-id="758f5-172">11 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="758f5-173">Modello</span><span class="sxs-lookup"><span data-stu-id="758f5-173">Pattern</span></span>

 <span data-ttu-id="758f5-174">11 cifre:</span><span class="sxs-lookup"><span data-stu-id="758f5-174">11 digits:</span></span> 
  
-  <span data-ttu-id="758f5-175">Dieci cifre</span><span class="sxs-lookup"><span data-stu-id="758f5-175">Ten digits</span></span> 
    
- <span data-ttu-id="758f5-176">Una cifra di controllo</span><span class="sxs-lookup"><span data-stu-id="758f5-176">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="758f5-177">Checksum</span><span class="sxs-lookup"><span data-stu-id="758f5-177">Checksum</span></span>

<span data-ttu-id="758f5-178">Sì</span><span class="sxs-lookup"><span data-stu-id="758f5-178">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="758f5-179">Definizione</span><span class="sxs-lookup"><span data-stu-id="758f5-179">Definition</span></span>

<span data-ttu-id="758f5-180">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="758f5-180">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="758f5-181">La funzione `Func_croatia_eu_ssn_or_equivalent` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="758f5-181">The function  `Func_croatia_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="758f5-182">Viene trovata una `Keywords_croatia_eu_ssn_or_equivalent` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="758f5-182">A keyword from  `Keywords_croatia_eu_ssn_or_equivalent` is found.</span></span> 
    
<span data-ttu-id="758f5-183">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="758f5-183">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="758f5-184">La funzione `Func_croatia_eu_ssn_or_equivalent` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="758f5-184">The function  `Func_croatia_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU SSN or Equivalent Number -->
<Entity id="d24e32a4-c0bb-4ba8-899d-6303b95742d9" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_croatia_eu_ssn_or_equivalent" />
          <Match idRef="Keywords_croatia_eu_ssn_or_equivalent" />
        </Pattern> 
       <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_croatia_eu_ssn_or_equivalent" />
        </Pattern>      
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="758f5-185">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="758f5-185">Keywords</span></span>

#### <a name="keywordscroatiaeussnorequivalent"></a><span data-ttu-id="758f5-186">Keywords_croatia_eu_ssn_or_equivalent</span><span class="sxs-lookup"><span data-stu-id="758f5-186">Keywords_croatia_eu_ssn_or_equivalent</span></span>

<span data-ttu-id="758f5-187">numero di identificazione personale</span><span class="sxs-lookup"><span data-stu-id="758f5-187">personal identification number</span></span>
  
<span data-ttu-id="758f5-188">numero di cittadino Master</span><span class="sxs-lookup"><span data-stu-id="758f5-188">master citizen number</span></span>
  
<span data-ttu-id="758f5-189">national identification number</span><span class="sxs-lookup"><span data-stu-id="758f5-189">national identification number</span></span>
  
<span data-ttu-id="758f5-190">social security number</span><span class="sxs-lookup"><span data-stu-id="758f5-190">social security number</span></span>
  
<span data-ttu-id="758f5-191">nationalnumber #</span><span class="sxs-lookup"><span data-stu-id="758f5-191">nationalnumber#</span></span>
  
<span data-ttu-id="758f5-192">SSN</span><span class="sxs-lookup"><span data-stu-id="758f5-192">ssn#</span></span>
  
<span data-ttu-id="758f5-193">SSN</span><span class="sxs-lookup"><span data-stu-id="758f5-193">ssn</span></span>
  
<span data-ttu-id="758f5-194">nationalnumber</span><span class="sxs-lookup"><span data-stu-id="758f5-194">nationalnumber</span></span>
  
<span data-ttu-id="758f5-195">BNN</span><span class="sxs-lookup"><span data-stu-id="758f5-195">bnn#</span></span>
  
<span data-ttu-id="758f5-196">BNN</span><span class="sxs-lookup"><span data-stu-id="758f5-196">bnn</span></span>
  
<span data-ttu-id="758f5-197">numero ID personale</span><span class="sxs-lookup"><span data-stu-id="758f5-197">personal id number</span></span>
  
<span data-ttu-id="758f5-198">personalidnumber #</span><span class="sxs-lookup"><span data-stu-id="758f5-198">personalidnumber#</span></span>
  
<span data-ttu-id="758f5-199">OIB</span><span class="sxs-lookup"><span data-stu-id="758f5-199">oib</span></span>
  
<span data-ttu-id="758f5-200">Osobni identifikacijski broj</span><span class="sxs-lookup"><span data-stu-id="758f5-200">osobni identifikacijski broj</span></span>
  
## <a name="czech-republic"></a><span data-ttu-id="758f5-201">Repubblica Ceca</span><span class="sxs-lookup"><span data-stu-id="758f5-201">Czech Republic</span></span>

### <a name="format"></a><span data-ttu-id="758f5-202">Formato</span><span class="sxs-lookup"><span data-stu-id="758f5-202">Format</span></span>

<span data-ttu-id="758f5-203">Dieci cifre e una barra rovesciata nel modello specificato</span><span class="sxs-lookup"><span data-stu-id="758f5-203">Ten digits and a backslash in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="758f5-204">Modello</span><span class="sxs-lookup"><span data-stu-id="758f5-204">Pattern</span></span>

<span data-ttu-id="758f5-205">Dieci cifre e una barra rovesciata:</span><span class="sxs-lookup"><span data-stu-id="758f5-205">Ten digits and a backslash:</span></span>
  
- <span data-ttu-id="758f5-206">Sei cifre che corrispondono alla data di nascita (AAMMGG):</span><span class="sxs-lookup"><span data-stu-id="758f5-206">Six digits that correspond to the birth date (YYMMDD):</span></span> 
    
- <span data-ttu-id="758f5-207">Una barra rovesciata</span><span class="sxs-lookup"><span data-stu-id="758f5-207">A backslash</span></span>
    
- <span data-ttu-id="758f5-208">Tre cifre che corrispondono a un numero di serie che separa le persone nate nella stessa data</span><span class="sxs-lookup"><span data-stu-id="758f5-208">Three digits that correspond to a serial number that separates persons born on the same date</span></span>
    
- <span data-ttu-id="758f5-209">Una cifra di controllo</span><span class="sxs-lookup"><span data-stu-id="758f5-209">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="758f5-210">Checksum</span><span class="sxs-lookup"><span data-stu-id="758f5-210">Checksum</span></span>

<span data-ttu-id="758f5-211">Sì</span><span class="sxs-lookup"><span data-stu-id="758f5-211">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="758f5-212">Definizione</span><span class="sxs-lookup"><span data-stu-id="758f5-212">Definition</span></span>

<span data-ttu-id="758f5-213">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="758f5-213">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="758f5-214">La funzione `Func_czech_republic_eu_ssn_or_equivalent` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="758f5-214">The function  `Func_czech_republic_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="758f5-215">Viene trovata una `Keywords_czech_republic_eu_ssn_or_equivalent` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="758f5-215">A keyword from  `Keywords_czech_republic_eu_ssn_or_equivalent` is found.</span></span> 
    
<span data-ttu-id="758f5-216">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="758f5-216">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="758f5-217">La funzione `Func_czech_republic_eu_ssn_or_equivalent` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="758f5-217">The function  `Func_czech_republic_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU SSN or Equivalent Number -->
<Entity id="d24e32a4-c0bb-4ba8-899d-6303b95742d9" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_czech_republic_eu_ssn_or_equivalent" />
          <Match idRef="Keywords_czech_republic_eu_ssn_or_equivalent" />
        </Pattern> 
       <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_czech_republic_eu_ssn_or_equivalent" />
        </Pattern>      
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="758f5-218">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="758f5-218">Keywords</span></span>

#### <a name="keywordsczechrepubliceussnorequivalent"></a><span data-ttu-id="758f5-219">Keywords_czech_republic_eu_ssn_or_equivalent</span><span class="sxs-lookup"><span data-stu-id="758f5-219">Keywords_czech_republic_eu_ssn_or_equivalent</span></span>

<span data-ttu-id="758f5-220">numero di nascita</span><span class="sxs-lookup"><span data-stu-id="758f5-220">birth number</span></span>
  
<span data-ttu-id="758f5-221">national identification number</span><span class="sxs-lookup"><span data-stu-id="758f5-221">national identification number</span></span>
  
<span data-ttu-id="758f5-222">numero di identificazione personale</span><span class="sxs-lookup"><span data-stu-id="758f5-222">personal identification number</span></span>
  
<span data-ttu-id="758f5-223">social security number</span><span class="sxs-lookup"><span data-stu-id="758f5-223">social security number</span></span>
  
<span data-ttu-id="758f5-224">nationalnumber #</span><span class="sxs-lookup"><span data-stu-id="758f5-224">nationalnumber#</span></span>
  
<span data-ttu-id="758f5-225">SSN</span><span class="sxs-lookup"><span data-stu-id="758f5-225">ssn#</span></span>
  
<span data-ttu-id="758f5-226">SSN</span><span class="sxs-lookup"><span data-stu-id="758f5-226">ssn</span></span>
  
<span data-ttu-id="758f5-227">numero nazionale</span><span class="sxs-lookup"><span data-stu-id="758f5-227">national number</span></span>
  
<span data-ttu-id="758f5-228">numero ID personale</span><span class="sxs-lookup"><span data-stu-id="758f5-228">personal id number</span></span>
  
<span data-ttu-id="758f5-229">personalidnumber #</span><span class="sxs-lookup"><span data-stu-id="758f5-229">personalidnumber#</span></span>
  
<span data-ttu-id="758f5-230">rč</span><span class="sxs-lookup"><span data-stu-id="758f5-230">rč</span></span>
  
<span data-ttu-id="758f5-231">rodné číslo</span><span class="sxs-lookup"><span data-stu-id="758f5-231">rodné číslo</span></span>
  
<span data-ttu-id="758f5-232">rodne cislo</span><span class="sxs-lookup"><span data-stu-id="758f5-232">rodne cislo</span></span>
  
## <a name="denmark"></a><span data-ttu-id="758f5-233">Danimarca</span><span class="sxs-lookup"><span data-stu-id="758f5-233">Denmark</span></span>

### <a name="format"></a><span data-ttu-id="758f5-234">Formato</span><span class="sxs-lookup"><span data-stu-id="758f5-234">Format</span></span>

<span data-ttu-id="758f5-235">Dieci cifre e un trattino nel modello specificato</span><span class="sxs-lookup"><span data-stu-id="758f5-235">Ten digits and a hyphen in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="758f5-236">Modello</span><span class="sxs-lookup"><span data-stu-id="758f5-236">Pattern</span></span>

<span data-ttu-id="758f5-237">Dieci cifre e un trattino:</span><span class="sxs-lookup"><span data-stu-id="758f5-237">Ten digits and a hyphen:</span></span>
  
- <span data-ttu-id="758f5-238">Sei cifre che corrispondono alla data di nascita (GGMMAA)</span><span class="sxs-lookup"><span data-stu-id="758f5-238">Six digits that correspond to the birth date (DDMMYY)</span></span> 
    
- <span data-ttu-id="758f5-239">Una lineetta</span><span class="sxs-lookup"><span data-stu-id="758f5-239">A hyphen</span></span>
    
- <span data-ttu-id="758f5-240">Quattro cifre che corrispondono a un numero di sequenza</span><span class="sxs-lookup"><span data-stu-id="758f5-240">Four digits that correspond to a sequence number</span></span>
    
### <a name="checksum"></a><span data-ttu-id="758f5-241">Checksum</span><span class="sxs-lookup"><span data-stu-id="758f5-241">Checksum</span></span>

<span data-ttu-id="758f5-242">Sì</span><span class="sxs-lookup"><span data-stu-id="758f5-242">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="758f5-243">Definizione</span><span class="sxs-lookup"><span data-stu-id="758f5-243">Definition</span></span>

<span data-ttu-id="758f5-244">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="758f5-244">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="758f5-245">La funzione `Func_denmark_eu_ssn_or_equivalent` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="758f5-245">The function  `Func_denmark_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="758f5-246">Viene trovata una `Keywords_denmark_eu_ssn_or_equivalent` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="758f5-246">A keyword from  `Keywords_denmark_eu_ssn_or_equivalent` is found.</span></span> 
    
<span data-ttu-id="758f5-247">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="758f5-247">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="758f5-248">La funzione `Func_denmark_eu_ssn_or_equivalent` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="758f5-248">The function  `Func_denmark_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU SSN or Equivalent Number -->
<Entity id="d24e32a4-c0bb-4ba8-899d-6303b95742d9" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_denmark_eu_ssn_or_equivalent" />
          <Match idRef="Keywords_denmark_eu_ssn_or_equivalent" />
        </Pattern> 
       <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_denmark_eu_ssn_or_equivalent" />
        </Pattern>      
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="758f5-249">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="758f5-249">Keywords</span></span>

#### <a name="keywordsdenmarkeussnorequivalent"></a><span data-ttu-id="758f5-250">Keywords_denmark_eu_ssn_or_equivalent</span><span class="sxs-lookup"><span data-stu-id="758f5-250">Keywords_denmark_eu_ssn_or_equivalent</span></span>

<span data-ttu-id="758f5-251">numero di identificazione personale</span><span class="sxs-lookup"><span data-stu-id="758f5-251">personal identification number</span></span>
  
<span data-ttu-id="758f5-252">national identification number</span><span class="sxs-lookup"><span data-stu-id="758f5-252">national identification number</span></span>
  
<span data-ttu-id="758f5-253">social security number</span><span class="sxs-lookup"><span data-stu-id="758f5-253">social security number</span></span>
  
<span data-ttu-id="758f5-254">nationalnumber #</span><span class="sxs-lookup"><span data-stu-id="758f5-254">nationalnumber#</span></span>
  
<span data-ttu-id="758f5-255">SSN</span><span class="sxs-lookup"><span data-stu-id="758f5-255">ssn#</span></span>
  
<span data-ttu-id="758f5-256">SSN</span><span class="sxs-lookup"><span data-stu-id="758f5-256">ssn</span></span>
  
<span data-ttu-id="758f5-257">numero nazionale</span><span class="sxs-lookup"><span data-stu-id="758f5-257">national number</span></span>
  
<span data-ttu-id="758f5-258">numero ID personale</span><span class="sxs-lookup"><span data-stu-id="758f5-258">personal id number</span></span>
  
<span data-ttu-id="758f5-259">personalidnumber #</span><span class="sxs-lookup"><span data-stu-id="758f5-259">personalidnumber#</span></span>
  
<span data-ttu-id="758f5-260">CPR-Nummer</span><span class="sxs-lookup"><span data-stu-id="758f5-260">cpr-nummer</span></span>
  
<span data-ttu-id="758f5-261">personnummer</span><span class="sxs-lookup"><span data-stu-id="758f5-261">personnummer</span></span>
  
## <a name="finland"></a><span data-ttu-id="758f5-262">Finlandia</span><span class="sxs-lookup"><span data-stu-id="758f5-262">Finland</span></span>

### <a name="format"></a><span data-ttu-id="758f5-263">Formato</span><span class="sxs-lookup"><span data-stu-id="758f5-263">Format</span></span>

<span data-ttu-id="758f5-264">Una combinazione di 11 caratteri nel formato specificato</span><span class="sxs-lookup"><span data-stu-id="758f5-264">An 11-character combination in the specified format</span></span>
  
### <a name="pattern"></a><span data-ttu-id="758f5-265">Modello</span><span class="sxs-lookup"><span data-stu-id="758f5-265">Pattern</span></span>

<span data-ttu-id="758f5-266">Una combinazione di 11 caratteri nel formato specificato:</span><span class="sxs-lookup"><span data-stu-id="758f5-266">An 11-character combination in the specified format:</span></span>
  
-  <span data-ttu-id="758f5-267">Sei cifre</span><span class="sxs-lookup"><span data-stu-id="758f5-267">Six digits</span></span> 
    
- <span data-ttu-id="758f5-268">Un'istanza di una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="758f5-268">One instance of one of the following:</span></span>
    
  - <span data-ttu-id="758f5-269">Segno più</span><span class="sxs-lookup"><span data-stu-id="758f5-269">Plus symbol</span></span>
    
  - <span data-ttu-id="758f5-270">Segno meno</span><span class="sxs-lookup"><span data-stu-id="758f5-270">Minus symbol</span></span>
    
  - <span data-ttu-id="758f5-271">La lettera "A" (senza distinzione tra maiuscole e minuscole)</span><span class="sxs-lookup"><span data-stu-id="758f5-271">The letter "A" (not case-sensitive)</span></span>
    
- <span data-ttu-id="758f5-272">Tre cifre</span><span class="sxs-lookup"><span data-stu-id="758f5-272">Three digits</span></span>
    
- <span data-ttu-id="758f5-273">Una lettera o una cifra</span><span class="sxs-lookup"><span data-stu-id="758f5-273">One letter or one digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="758f5-274">Checksum</span><span class="sxs-lookup"><span data-stu-id="758f5-274">Checksum</span></span>

<span data-ttu-id="758f5-275">Sì</span><span class="sxs-lookup"><span data-stu-id="758f5-275">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="758f5-276">Definizione</span><span class="sxs-lookup"><span data-stu-id="758f5-276">Definition</span></span>

<span data-ttu-id="758f5-277">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="758f5-277">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="758f5-278">La funzione `Func_finland_eu_ssn_or_equivalent` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="758f5-278">The function  `Func_finland_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="758f5-279">Viene trovata una `Keywords_finland_eu_ssn_or_equivalent` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="758f5-279">A keyword from  `Keywords_finland_eu_ssn_or_equivalent` is found.</span></span> 
    
<span data-ttu-id="758f5-280">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="758f5-280">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="758f5-281">La funzione `Func_finland_eu_ssn_or_equivalent` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="758f5-281">The function  `Func_finland_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU SSN or Equivalent Number -->
<Entity id="d24e32a4-c0bb-4ba8-899d-6303b95742d9" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_finland_eu_ssn_or_equivalent" />
          <Match idRef="Keywords_finland_eu_ssn_or_equivalent" />
        </Pattern> 
       <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_finland_eu_ssn_or_equivalent" />
        </Pattern>      
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="758f5-282">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="758f5-282">Keywords</span></span>

#### <a name="keywordsfinlandeussnorequivalent"></a><span data-ttu-id="758f5-283">Keywords_finland_eu_ssn_or_equivalent</span><span class="sxs-lookup"><span data-stu-id="758f5-283">Keywords_finland_eu_ssn_or_equivalent</span></span>

<span data-ttu-id="758f5-284">identification number</span><span class="sxs-lookup"><span data-stu-id="758f5-284">identification number</span></span>
  
<span data-ttu-id="758f5-285">ID personale</span><span class="sxs-lookup"><span data-stu-id="758f5-285">personal id</span></span>
  
<span data-ttu-id="758f5-286">numero di identità</span><span class="sxs-lookup"><span data-stu-id="758f5-286">identity number</span></span>
  
<span data-ttu-id="758f5-287">numero di identificazione nazionale finlandese</span><span class="sxs-lookup"><span data-stu-id="758f5-287">finnish national id number</span></span>
  
<span data-ttu-id="758f5-288">personalidnumber #</span><span class="sxs-lookup"><span data-stu-id="758f5-288">personalidnumber#</span></span>
  
<span data-ttu-id="758f5-289">national identification number</span><span class="sxs-lookup"><span data-stu-id="758f5-289">national identification number</span></span>
  
<span data-ttu-id="758f5-290">numero ID</span><span class="sxs-lookup"><span data-stu-id="758f5-290">id number</span></span>
  
<span data-ttu-id="758f5-291">ID nazionale No.</span><span class="sxs-lookup"><span data-stu-id="758f5-291">national id no.</span></span>
  
<span data-ttu-id="758f5-292">numero ID nazionale</span><span class="sxs-lookup"><span data-stu-id="758f5-292">national id number</span></span>
  
<span data-ttu-id="758f5-293">ID No</span><span class="sxs-lookup"><span data-stu-id="758f5-293">id no</span></span>
  
<span data-ttu-id="758f5-294">tunnistenumero</span><span class="sxs-lookup"><span data-stu-id="758f5-294">tunnistenumero</span></span>
  
<span data-ttu-id="758f5-295">henkilötunnus</span><span class="sxs-lookup"><span data-stu-id="758f5-295">henkilötunnus</span></span>
  
<span data-ttu-id="758f5-296">yksilöllinen henkilökohtainen tunnistenumero</span><span class="sxs-lookup"><span data-stu-id="758f5-296">yksilöllinen henkilökohtainen tunnistenumero</span></span>
  
<span data-ttu-id="758f5-297">ainutlaatuinen henkilökohtainen tunnus</span><span class="sxs-lookup"><span data-stu-id="758f5-297">ainutlaatuinen henkilökohtainen tunnus</span></span>
  
<span data-ttu-id="758f5-298">numero identiteetti</span><span class="sxs-lookup"><span data-stu-id="758f5-298">identiteetti numero</span></span>
  
<span data-ttu-id="758f5-299">Suomen Kansallinen henkilötunnus</span><span class="sxs-lookup"><span data-stu-id="758f5-299">suomen kansallinen henkilötunnus</span></span>
  
<span data-ttu-id="758f5-300">henkilötunnusnumero #</span><span class="sxs-lookup"><span data-stu-id="758f5-300">henkilötunnusnumero#</span></span>
  
<span data-ttu-id="758f5-301">kansallisen tunnistenumero</span><span class="sxs-lookup"><span data-stu-id="758f5-301">kansallisen tunnistenumero</span></span>
  
<span data-ttu-id="758f5-302">tunnusnumero</span><span class="sxs-lookup"><span data-stu-id="758f5-302">tunnusnumero</span></span>
  
<span data-ttu-id="758f5-303">Kansallinen tunnus numero</span><span class="sxs-lookup"><span data-stu-id="758f5-303">kansallinen tunnus numero</span></span>
  
<span data-ttu-id="758f5-304">hetu</span><span class="sxs-lookup"><span data-stu-id="758f5-304">hetu</span></span>
  
## <a name="france"></a><span data-ttu-id="758f5-305">Francia</span><span class="sxs-lookup"><span data-stu-id="758f5-305">France</span></span>

<span data-ttu-id="758f5-306">Per informazioni dettagliate, vedere la sezione "Francia social preVidenza (INSEE)" in [che cosa cercano i tipi di informazioni riservate](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="758f5-306">For details, see the section "France Social Security Number (INSEE)" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="germany"></a><span data-ttu-id="758f5-307">Germania</span><span class="sxs-lookup"><span data-stu-id="758f5-307">Germany</span></span>

<span data-ttu-id="758f5-308">Per informazioni dettagliate, vedere la sezione "Germania identità numero di carta" in [che cosa cercano i tipi di informazioni riservate](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="758f5-308">For details, see the section "Germany Identity Card Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="greece"></a><span data-ttu-id="758f5-309">Grecia</span><span class="sxs-lookup"><span data-stu-id="758f5-309">Greece</span></span>

<span data-ttu-id="758f5-310">Per informazioni dettagliate, vedere la sezione "Grecia National ID Card" in [quello che cercano i tipi di informazioni riservate](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="758f5-310">For details, see the section "Greece National ID Card" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="hungary"></a><span data-ttu-id="758f5-311">Ungheria</span><span class="sxs-lookup"><span data-stu-id="758f5-311">Hungary</span></span>

### <a name="format"></a><span data-ttu-id="758f5-312">Formato</span><span class="sxs-lookup"><span data-stu-id="758f5-312">Format</span></span>

<span data-ttu-id="758f5-313">Nove cifre senza spazi e delimitatori</span><span class="sxs-lookup"><span data-stu-id="758f5-313">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="758f5-314">Modello</span><span class="sxs-lookup"><span data-stu-id="758f5-314">Pattern</span></span>

<span data-ttu-id="758f5-315">9 cifre</span><span class="sxs-lookup"><span data-stu-id="758f5-315">Nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="758f5-316">Checksum</span><span class="sxs-lookup"><span data-stu-id="758f5-316">Checksum</span></span>

<span data-ttu-id="758f5-317">Sì</span><span class="sxs-lookup"><span data-stu-id="758f5-317">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="758f5-318">Definizione</span><span class="sxs-lookup"><span data-stu-id="758f5-318">Definition</span></span>

<span data-ttu-id="758f5-319">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="758f5-319">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="758f5-320">La funzione `Func_hungary_eu_ssn_or_equivalent` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="758f5-320">The function  `Func_hungary_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="758f5-321">Viene trovata una `Keywords_hungary_eu_ssn_or_equivalent` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="758f5-321">A keyword from  `Keywords_hungary_eu_ssn_or_equivalent` is found.</span></span> 
    
<span data-ttu-id="758f5-322">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="758f5-322">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="758f5-323">La funzione `Func_hungary_eu_ssn_or_equivalent` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="758f5-323">The function  `Func_hungary_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU SSN or Equivalent Number -->
<Entity id="d24e32a4-c0bb-4ba8-899d-6303b95742d9" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_hungary_eu_ssn_or_equivalent" />
          <Match idRef="Keywords_hungary_eu_ssn_or_equivalent" />
        </Pattern> 
       <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_hungary_eu_ssn_or_equivalent" />
        </Pattern>      
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="758f5-324">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="758f5-324">Keywords</span></span>

#### <a name="keywordshungaryeussnorequivalent"></a><span data-ttu-id="758f5-325">Keywords_hungary_eu_ssn_or_equivalent</span><span class="sxs-lookup"><span data-stu-id="758f5-325">Keywords_hungary_eu_ssn_or_equivalent</span></span>

<span data-ttu-id="758f5-326">codice di previdenza sociale ungherese</span><span class="sxs-lookup"><span data-stu-id="758f5-326">hungarian social security number</span></span>
  
<span data-ttu-id="758f5-327">social security number</span><span class="sxs-lookup"><span data-stu-id="758f5-327">social security number</span></span>
  
<span data-ttu-id="758f5-328">SocialSecurityNumber #</span><span class="sxs-lookup"><span data-stu-id="758f5-328">socialsecuritynumber#</span></span>
  
<span data-ttu-id="758f5-329">hssn #</span><span class="sxs-lookup"><span data-stu-id="758f5-329">hssn#</span></span>
  
<span data-ttu-id="758f5-330">socialsecuritynno</span><span class="sxs-lookup"><span data-stu-id="758f5-330">socialsecuritynno</span></span>
  
<span data-ttu-id="758f5-331">hssn</span><span class="sxs-lookup"><span data-stu-id="758f5-331">hssn</span></span>
  
<span data-ttu-id="758f5-332">Taj</span><span class="sxs-lookup"><span data-stu-id="758f5-332">taj</span></span>
  
<span data-ttu-id="758f5-333">Taj</span><span class="sxs-lookup"><span data-stu-id="758f5-333">taj#</span></span>
  
<span data-ttu-id="758f5-334">SSN</span><span class="sxs-lookup"><span data-stu-id="758f5-334">ssn</span></span>
  
<span data-ttu-id="758f5-335">SSN</span><span class="sxs-lookup"><span data-stu-id="758f5-335">ssn#</span></span>
  
<span data-ttu-id="758f5-336">previdenza sociale No</span><span class="sxs-lookup"><span data-stu-id="758f5-336">social security no</span></span>
  
<span data-ttu-id="758f5-337">ÁFA</span><span class="sxs-lookup"><span data-stu-id="758f5-337">áfa</span></span>
  
<span data-ttu-id="758f5-338">közösségi adószám</span><span class="sxs-lookup"><span data-stu-id="758f5-338">közösségi adószám</span></span>
  
<span data-ttu-id="758f5-339">Általános forgalmi Adó szám</span><span class="sxs-lookup"><span data-stu-id="758f5-339">általános forgalmi adó szám</span></span>
  
<span data-ttu-id="758f5-340">hozzáadottérték Adó</span><span class="sxs-lookup"><span data-stu-id="758f5-340">hozzáadottérték adó</span></span>
  
<span data-ttu-id="758f5-341">ÁFA szám</span><span class="sxs-lookup"><span data-stu-id="758f5-341">áfa szám</span></span>
  
<span data-ttu-id="758f5-342">Magyar ÁFA szám</span><span class="sxs-lookup"><span data-stu-id="758f5-342">magyar áfa szám</span></span>
  
## <a name="portugal"></a><span data-ttu-id="758f5-343">Portogallo</span><span class="sxs-lookup"><span data-stu-id="758f5-343">Portugal</span></span>

<span data-ttu-id="758f5-344">Per informazioni dettagliate, vedere la sezione "Portugal Citizen Card Number" in [quello che i tipi di informazioni riservate cercano](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="758f5-344">For details, see the section "Portugal Citizen Card Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="spain"></a><span data-ttu-id="758f5-345">Spagna</span><span class="sxs-lookup"><span data-stu-id="758f5-345">Spain</span></span>

<span data-ttu-id="758f5-346">Per informazioni dettagliate, vedere la sezione "Spagna Social preVidenza sociale (SSN)" in [che cosa cercano i tipi di informazioni riservate](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="758f5-346">For details, see the section "Spain Social Security Number (SSN)" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="sweden"></a><span data-ttu-id="758f5-347">Svezia</span><span class="sxs-lookup"><span data-stu-id="758f5-347">Sweden</span></span>

### <a name="format"></a><span data-ttu-id="758f5-348">Formato</span><span class="sxs-lookup"><span data-stu-id="758f5-348">Format</span></span>

<span data-ttu-id="758f5-349">12 cifre senza spazi e delimitatori</span><span class="sxs-lookup"><span data-stu-id="758f5-349">12 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="758f5-350">Modello</span><span class="sxs-lookup"><span data-stu-id="758f5-350">Pattern</span></span>

<span data-ttu-id="758f5-351">12 cifre:</span><span class="sxs-lookup"><span data-stu-id="758f5-351">12 digits:</span></span>
  
-  <span data-ttu-id="758f5-352">Otto cifre che corrispondono alla data di nascita (AAAAMMGG)</span><span class="sxs-lookup"><span data-stu-id="758f5-352">Eight digits that correspond to the birth date (YYYYMMDD)</span></span> 
    
- <span data-ttu-id="758f5-353">Tre cifre che corrispondono a un numero di serie in cui:</span><span class="sxs-lookup"><span data-stu-id="758f5-353">Three digits that correspond to a serial number where:</span></span> 
    
  - <span data-ttu-id="758f5-354">L'ultima cifra del numero di serie indica il sesso per l'assegnazione di un numero dispari per il maschio e per un numero pari per la femmina</span><span class="sxs-lookup"><span data-stu-id="758f5-354">The last digit in the serial number indicates gender by the assignment of an odd number for male and an even number for female</span></span>
    
  - <span data-ttu-id="758f5-355">Fino a 1990, l'assegnazione del numero di serie corrispondeva alla contea in cui è Nato il portatore del numero o (se è nato prima del 1947) dove viveva, secondo i registri delle tasse, il 1 ° gennaio 1947, con un codice speciale (solitamente 9 come settima cifra) per immigrati</span><span class="sxs-lookup"><span data-stu-id="758f5-355">Up to 1990, the assignment of serial number corresponded to the county where the bearer of the number was born or (if born before 1947) where he/she had been living, according to tax records, on January 1, 1947, with a special code (usually 9 as the 7th digit) for immigrants</span></span> 
    
- <span data-ttu-id="758f5-356">Una cifra di controllo</span><span class="sxs-lookup"><span data-stu-id="758f5-356">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="758f5-357">Checksum</span><span class="sxs-lookup"><span data-stu-id="758f5-357">Checksum</span></span>

<span data-ttu-id="758f5-358">Sì</span><span class="sxs-lookup"><span data-stu-id="758f5-358">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="758f5-359">Definizione</span><span class="sxs-lookup"><span data-stu-id="758f5-359">Definition</span></span>

<span data-ttu-id="758f5-360">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="758f5-360">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="758f5-361">La funzione `Func_sweden_eu_ssn_or_equivalent` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="758f5-361">The function  `Func_sweden_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="758f5-362">Viene trovata una `Keywords_sweden_eu_ssn_or_equivalent` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="758f5-362">A keyword from  `Keywords_sweden_eu_ssn_or_equivalent` is found.</span></span> 
    
<span data-ttu-id="758f5-363">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="758f5-363">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="758f5-364">La funzione `Func_sweden_eu_ssn_or_equivalent` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="758f5-364">The function  `Func_sweden_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU SSN or Equivalent Number -->
<Entity id="d24e32a4-c0bb-4ba8-899d-6303b95742d9" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_sweden_eu_ssn_or_equivalent" />
          <Match idRef="Keywords_sweden_eu_ssn_or_equivalent" />
        </Pattern> 
       <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_sweden_eu_ssn_or_equivalent" />
        </Pattern>      
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="758f5-365">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="758f5-365">Keywords</span></span>

#### <a name="keywordsswedeneussnorequivalent"></a><span data-ttu-id="758f5-366">Keywords_sweden_eu_ssn_or_equivalent</span><span class="sxs-lookup"><span data-stu-id="758f5-366">Keywords_sweden_eu_ssn_or_equivalent</span></span>

<span data-ttu-id="758f5-367">numero ID personale</span><span class="sxs-lookup"><span data-stu-id="758f5-367">personal id number</span></span>
  
<span data-ttu-id="758f5-368">identification number</span><span class="sxs-lookup"><span data-stu-id="758f5-368">identification number</span></span>
  
<span data-ttu-id="758f5-369">ID personale No</span><span class="sxs-lookup"><span data-stu-id="758f5-369">personal id no</span></span>
  
<span data-ttu-id="758f5-370">identità No</span><span class="sxs-lookup"><span data-stu-id="758f5-370">identity no</span></span>
  
<span data-ttu-id="758f5-371">identificazione no</span><span class="sxs-lookup"><span data-stu-id="758f5-371">identification no</span></span>
  
<span data-ttu-id="758f5-372">identificazione personale No</span><span class="sxs-lookup"><span data-stu-id="758f5-372">personal identification no</span></span>
  
<span data-ttu-id="758f5-373">ID personnummer</span><span class="sxs-lookup"><span data-stu-id="758f5-373">personnummer id</span></span>
  
<span data-ttu-id="758f5-374">ID personligt-Nummer</span><span class="sxs-lookup"><span data-stu-id="758f5-374">personligt id-nummer</span></span>
  
<span data-ttu-id="758f5-375">ID unikt-Nummer</span><span class="sxs-lookup"><span data-stu-id="758f5-375">unikt id-nummer</span></span>
  
<span data-ttu-id="758f5-376">personnummer</span><span class="sxs-lookup"><span data-stu-id="758f5-376">personnummer</span></span>
  
<span data-ttu-id="758f5-377">identifikationsnumret</span><span class="sxs-lookup"><span data-stu-id="758f5-377">identifikationsnumret</span></span>
  
<span data-ttu-id="758f5-378">personnummer</span><span class="sxs-lookup"><span data-stu-id="758f5-378">personnummer#</span></span>
  
<span data-ttu-id="758f5-379">identifikationsnumret #</span><span class="sxs-lookup"><span data-stu-id="758f5-379">identifikationsnumret#</span></span>
  
## <a name="see-also"></a><span data-ttu-id="758f5-380">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="758f5-380">See also</span></span>

[<span data-ttu-id="758f5-381">Cosa individuano le tipologie di informazioni sensibili</span><span class="sxs-lookup"><span data-stu-id="758f5-381">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)

