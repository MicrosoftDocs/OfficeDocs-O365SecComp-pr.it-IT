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
ms.sourcegitcommit: ed822a776d3419853453583e882f3c61ca26d4b2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/05/2019
ms.locfileid: "30410801"
---
# <a name="eu-social-security-number-or-equivalent-id"></a><span data-ttu-id="6a794-104">Codice di preVidenza sociale dell'Unione europea o ID equivalente</span><span class="sxs-lookup"><span data-stu-id="6a794-104">EU Social Security Number or Equivalent ID</span></span>

<span data-ttu-id="6a794-105">In questo argomento viene illustrato l'aspetto di un criterio di prevenzione della perdita di dati (DLP, Data Loss Prevention), quando viene rilevato il codice fiscale dell'Unione europea (SSN) o il tipo di informazioni sensibili ID equivalente.</span><span class="sxs-lookup"><span data-stu-id="6a794-105">This topic shows what a data loss prevention (DLP) policy looks for when it detects the EU Social Security Number (SSN) or Equivalent ID sensitive information type.</span></span> <span data-ttu-id="6a794-106">Questo tipo di informazioni riservate definisce modelli, parole chiave e altre evidenze diverse per ogni paese.</span><span class="sxs-lookup"><span data-stu-id="6a794-106">This sensitive information type defines different patterns, keywords, and other evidence for each country.</span></span>
  
## <a name="austria"></a><span data-ttu-id="6a794-107">Austria</span><span class="sxs-lookup"><span data-stu-id="6a794-107">Austria</span></span>

### <a name="format"></a><span data-ttu-id="6a794-108">Formato</span><span class="sxs-lookup"><span data-stu-id="6a794-108">Format</span></span>

<span data-ttu-id="6a794-109">10 cifre nel formato specificato</span><span class="sxs-lookup"><span data-stu-id="6a794-109">10 digits in the specified format</span></span>
  
### <a name="pattern"></a><span data-ttu-id="6a794-110">Modello</span><span class="sxs-lookup"><span data-stu-id="6a794-110">Pattern</span></span>

<span data-ttu-id="6a794-111">10 cifre:</span><span class="sxs-lookup"><span data-stu-id="6a794-111">10 digits:</span></span>
  
-  <span data-ttu-id="6a794-112">Tre cifre che corrispondono a un numero di serie</span><span class="sxs-lookup"><span data-stu-id="6a794-112">Three digits that correspond to a serial number</span></span> 
    
- <span data-ttu-id="6a794-113">Una cifra di controllo</span><span class="sxs-lookup"><span data-stu-id="6a794-113">One check digit</span></span>
    
- <span data-ttu-id="6a794-114">Sei cifre che corrispondono alla data di nascita (GGMMAA)</span><span class="sxs-lookup"><span data-stu-id="6a794-114">Six digits that correspond to the birth date (DDMMYY)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="6a794-115">Checksum</span><span class="sxs-lookup"><span data-stu-id="6a794-115">Checksum</span></span>

<span data-ttu-id="6a794-116">Sì</span><span class="sxs-lookup"><span data-stu-id="6a794-116">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="6a794-117">Definizione</span><span class="sxs-lookup"><span data-stu-id="6a794-117">Definition</span></span>

<span data-ttu-id="6a794-118">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="6a794-118">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="6a794-119">La funzione `Func_austria_eu_ssn_or_equivalent` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="6a794-119">The function  `Func_austria_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="6a794-120">Viene trovata una `Keywords_austria_eu_ssn_or_equivalent` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="6a794-120">A keyword from  `Keywords_austria_eu_ssn_or_equivalent` is found.</span></span> 
    
<span data-ttu-id="6a794-121">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="6a794-121">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="6a794-122">La funzione `Func_austria_eu_ssn_or_equivalent` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="6a794-122">The function  `Func_austria_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="6a794-123">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="6a794-123">Keywords</span></span>

#### <a name="keywordsaustriaeussnorequivalent"></a><span data-ttu-id="6a794-124">Keywords_austria_eu_ssn_or_equivalent</span><span class="sxs-lookup"><span data-stu-id="6a794-124">Keywords_austria_eu_ssn_or_equivalent</span></span>

<span data-ttu-id="6a794-125">previdenza sociale No</span><span class="sxs-lookup"><span data-stu-id="6a794-125">social security no</span></span>
  
<span data-ttu-id="6a794-126">social security number</span><span class="sxs-lookup"><span data-stu-id="6a794-126">social security number</span></span>
  
<span data-ttu-id="6a794-127">social security code</span><span class="sxs-lookup"><span data-stu-id="6a794-127">social security code</span></span>
  
<span data-ttu-id="6a794-128">numero assicurativo</span><span class="sxs-lookup"><span data-stu-id="6a794-128">insurance number</span></span>
  
<span data-ttu-id="6a794-129">SSN austriaco</span><span class="sxs-lookup"><span data-stu-id="6a794-129">austrian ssn</span></span>
  
<span data-ttu-id="6a794-130">SSN</span><span class="sxs-lookup"><span data-stu-id="6a794-130">ssn#</span></span>
  
<span data-ttu-id="6a794-131">SSN</span><span class="sxs-lookup"><span data-stu-id="6a794-131">ssn</span></span>
  
<span data-ttu-id="6a794-132">codice assicurativo</span><span class="sxs-lookup"><span data-stu-id="6a794-132">insurance code</span></span>
  
<span data-ttu-id="6a794-133">codice assicurativo #</span><span class="sxs-lookup"><span data-stu-id="6a794-133">insurance code#</span></span>
  
<span data-ttu-id="6a794-134">socialsecurityno #</span><span class="sxs-lookup"><span data-stu-id="6a794-134">socialsecurityno#</span></span>
  
<span data-ttu-id="6a794-135">sozialversicherungsnummer</span><span class="sxs-lookup"><span data-stu-id="6a794-135">sozialversicherungsnummer</span></span>
  
<span data-ttu-id="6a794-136">soziale Sicherheit kein</span><span class="sxs-lookup"><span data-stu-id="6a794-136">soziale sicherheit kein</span></span>
  
<span data-ttu-id="6a794-137">Versicherungsnummer</span><span class="sxs-lookup"><span data-stu-id="6a794-137">versicherungsnummer</span></span>
  
## <a name="belgium"></a><span data-ttu-id="6a794-138">Belgio</span><span class="sxs-lookup"><span data-stu-id="6a794-138">Belgium</span></span>

### <a name="format"></a><span data-ttu-id="6a794-139">Formato</span><span class="sxs-lookup"><span data-stu-id="6a794-139">Format</span></span>

<span data-ttu-id="6a794-140">11 cifre senza spazi o delimitatori</span><span class="sxs-lookup"><span data-stu-id="6a794-140">11 digits without spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="6a794-141">Modello</span><span class="sxs-lookup"><span data-stu-id="6a794-141">Pattern</span></span>

<span data-ttu-id="6a794-142">11 cifre</span><span class="sxs-lookup"><span data-stu-id="6a794-142">11 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="6a794-143">Checksum</span><span class="sxs-lookup"><span data-stu-id="6a794-143">Checksum</span></span>

<span data-ttu-id="6a794-144">Sì</span><span class="sxs-lookup"><span data-stu-id="6a794-144">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="6a794-145">Definizione</span><span class="sxs-lookup"><span data-stu-id="6a794-145">Definition</span></span>

<span data-ttu-id="6a794-146">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="6a794-146">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="6a794-147">La funzione `Func_belgium_eu_ssn_or_equivalent` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="6a794-147">The function  `Func_belgium_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="6a794-148">Viene trovata una `Keywords_belgium_eu_ssn_or_equivalent` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="6a794-148">A keyword from  `Keywords_belgium_eu_ssn_or_equivalent` is found.</span></span> 
    
<span data-ttu-id="6a794-149">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="6a794-149">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="6a794-150">La funzione `Func_belgium_eu_ssn_or_equivalent` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="6a794-150">The function  `Func_belgium_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="6a794-151">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="6a794-151">Keywords</span></span>

#### <a name="keywordsbelgiumeussnorequivalent"></a><span data-ttu-id="6a794-152">Keywords_belgium_eu_ssn_or_equivalent</span><span class="sxs-lookup"><span data-stu-id="6a794-152">Keywords_belgium_eu_ssn_or_equivalent</span></span>

<span data-ttu-id="6a794-153">numero nazionale belga</span><span class="sxs-lookup"><span data-stu-id="6a794-153">belgian national number</span></span>
  
<span data-ttu-id="6a794-154">numero nazionale</span><span class="sxs-lookup"><span data-stu-id="6a794-154">national number</span></span>
  
<span data-ttu-id="6a794-155">social security number</span><span class="sxs-lookup"><span data-stu-id="6a794-155">social security number</span></span>
  
<span data-ttu-id="6a794-156">nationalnumber #</span><span class="sxs-lookup"><span data-stu-id="6a794-156">nationalnumber#</span></span>
  
<span data-ttu-id="6a794-157">SSN</span><span class="sxs-lookup"><span data-stu-id="6a794-157">ssn#</span></span>
  
<span data-ttu-id="6a794-158">SSN</span><span class="sxs-lookup"><span data-stu-id="6a794-158">ssn</span></span>
  
<span data-ttu-id="6a794-159">nationalnumber</span><span class="sxs-lookup"><span data-stu-id="6a794-159">nationalnumber</span></span>
  
<span data-ttu-id="6a794-160">BNN</span><span class="sxs-lookup"><span data-stu-id="6a794-160">bnn#</span></span>
  
<span data-ttu-id="6a794-161">BNN</span><span class="sxs-lookup"><span data-stu-id="6a794-161">bnn</span></span>
  
<span data-ttu-id="6a794-162">numero ID personale</span><span class="sxs-lookup"><span data-stu-id="6a794-162">personal id number</span></span>
  
<span data-ttu-id="6a794-163">personalidnumber #</span><span class="sxs-lookup"><span data-stu-id="6a794-163">personalidnumber#</span></span>
  
<span data-ttu-id="6a794-164">numéro nazionale</span><span class="sxs-lookup"><span data-stu-id="6a794-164">numéro national</span></span>
  
<span data-ttu-id="6a794-165">numéro de sécurité</span><span class="sxs-lookup"><span data-stu-id="6a794-165">numéro de sécurité</span></span>
  
<span data-ttu-id="6a794-166">numéro d'assuré</span><span class="sxs-lookup"><span data-stu-id="6a794-166">numéro d'assuré</span></span>
  
<span data-ttu-id="6a794-167">identificazione nazionale</span><span class="sxs-lookup"><span data-stu-id="6a794-167">identifiant national</span></span>
  
<span data-ttu-id="6a794-168">identifiantnational #</span><span class="sxs-lookup"><span data-stu-id="6a794-168">identifiantnational#</span></span>
  
<span data-ttu-id="6a794-169">numéronational #</span><span class="sxs-lookup"><span data-stu-id="6a794-169">numéronational#</span></span>
  
## <a name="croatia"></a><span data-ttu-id="6a794-170">Croazia</span><span class="sxs-lookup"><span data-stu-id="6a794-170">Croatia</span></span>

### <a name="format"></a><span data-ttu-id="6a794-171">Formato</span><span class="sxs-lookup"><span data-stu-id="6a794-171">Format</span></span>

<span data-ttu-id="6a794-172">11 cifre senza spazi e delimitatori</span><span class="sxs-lookup"><span data-stu-id="6a794-172">11 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="6a794-173">Modello</span><span class="sxs-lookup"><span data-stu-id="6a794-173">Pattern</span></span>

 <span data-ttu-id="6a794-174">11 cifre:</span><span class="sxs-lookup"><span data-stu-id="6a794-174">11 digits:</span></span> 
  
-  <span data-ttu-id="6a794-175">Dieci cifre</span><span class="sxs-lookup"><span data-stu-id="6a794-175">Ten digits</span></span> 
    
- <span data-ttu-id="6a794-176">Una cifra di controllo</span><span class="sxs-lookup"><span data-stu-id="6a794-176">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="6a794-177">Checksum</span><span class="sxs-lookup"><span data-stu-id="6a794-177">Checksum</span></span>

<span data-ttu-id="6a794-178">Sì</span><span class="sxs-lookup"><span data-stu-id="6a794-178">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="6a794-179">Definizione</span><span class="sxs-lookup"><span data-stu-id="6a794-179">Definition</span></span>

<span data-ttu-id="6a794-180">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="6a794-180">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="6a794-181">La funzione `Func_croatia_eu_ssn_or_equivalent` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="6a794-181">The function  `Func_croatia_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="6a794-182">Viene trovata una `Keywords_croatia_eu_ssn_or_equivalent` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="6a794-182">A keyword from  `Keywords_croatia_eu_ssn_or_equivalent` is found.</span></span> 
    
<span data-ttu-id="6a794-183">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="6a794-183">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="6a794-184">La funzione `Func_croatia_eu_ssn_or_equivalent` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="6a794-184">The function  `Func_croatia_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="6a794-185">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="6a794-185">Keywords</span></span>

#### <a name="keywordscroatiaeussnorequivalent"></a><span data-ttu-id="6a794-186">Keywords_croatia_eu_ssn_or_equivalent</span><span class="sxs-lookup"><span data-stu-id="6a794-186">Keywords_croatia_eu_ssn_or_equivalent</span></span>

<span data-ttu-id="6a794-187">numero di identificazione personale</span><span class="sxs-lookup"><span data-stu-id="6a794-187">personal identification number</span></span>
  
<span data-ttu-id="6a794-188">numero di cittadino Master</span><span class="sxs-lookup"><span data-stu-id="6a794-188">master citizen number</span></span>
  
<span data-ttu-id="6a794-189">national identification number</span><span class="sxs-lookup"><span data-stu-id="6a794-189">national identification number</span></span>
  
<span data-ttu-id="6a794-190">social security number</span><span class="sxs-lookup"><span data-stu-id="6a794-190">social security number</span></span>
  
<span data-ttu-id="6a794-191">nationalnumber #</span><span class="sxs-lookup"><span data-stu-id="6a794-191">nationalnumber#</span></span>
  
<span data-ttu-id="6a794-192">SSN</span><span class="sxs-lookup"><span data-stu-id="6a794-192">ssn#</span></span>
  
<span data-ttu-id="6a794-193">SSN</span><span class="sxs-lookup"><span data-stu-id="6a794-193">ssn</span></span>
  
<span data-ttu-id="6a794-194">nationalnumber</span><span class="sxs-lookup"><span data-stu-id="6a794-194">nationalnumber</span></span>
  
<span data-ttu-id="6a794-195">BNN</span><span class="sxs-lookup"><span data-stu-id="6a794-195">bnn#</span></span>
  
<span data-ttu-id="6a794-196">BNN</span><span class="sxs-lookup"><span data-stu-id="6a794-196">bnn</span></span>
  
<span data-ttu-id="6a794-197">numero ID personale</span><span class="sxs-lookup"><span data-stu-id="6a794-197">personal id number</span></span>
  
<span data-ttu-id="6a794-198">personalidnumber #</span><span class="sxs-lookup"><span data-stu-id="6a794-198">personalidnumber#</span></span>
  
<span data-ttu-id="6a794-199">OIB</span><span class="sxs-lookup"><span data-stu-id="6a794-199">oib</span></span>
  
<span data-ttu-id="6a794-200">Osobni identifikacijski broj</span><span class="sxs-lookup"><span data-stu-id="6a794-200">osobni identifikacijski broj</span></span>
  
## <a name="czech-republic"></a><span data-ttu-id="6a794-201">Repubblica Ceca</span><span class="sxs-lookup"><span data-stu-id="6a794-201">Czech Republic</span></span>

### <a name="format"></a><span data-ttu-id="6a794-202">Formato</span><span class="sxs-lookup"><span data-stu-id="6a794-202">Format</span></span>

<span data-ttu-id="6a794-203">Dieci cifre e una barra rovesciata nel modello specificato</span><span class="sxs-lookup"><span data-stu-id="6a794-203">Ten digits and a backslash in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="6a794-204">Modello</span><span class="sxs-lookup"><span data-stu-id="6a794-204">Pattern</span></span>

<span data-ttu-id="6a794-205">Dieci cifre e una barra rovesciata:</span><span class="sxs-lookup"><span data-stu-id="6a794-205">Ten digits and a backslash:</span></span>
  
- <span data-ttu-id="6a794-206">Sei cifre che corrispondono alla data di nascita (AAMMGG):</span><span class="sxs-lookup"><span data-stu-id="6a794-206">Six digits that correspond to the birth date (YYMMDD):</span></span> 
    
- <span data-ttu-id="6a794-207">Una barra rovesciata</span><span class="sxs-lookup"><span data-stu-id="6a794-207">A backslash</span></span>
    
- <span data-ttu-id="6a794-208">Tre cifre che corrispondono a un numero di serie che separa le persone nate nella stessa data</span><span class="sxs-lookup"><span data-stu-id="6a794-208">Three digits that correspond to a serial number that separates persons born on the same date</span></span>
    
- <span data-ttu-id="6a794-209">Una cifra di controllo</span><span class="sxs-lookup"><span data-stu-id="6a794-209">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="6a794-210">Checksum</span><span class="sxs-lookup"><span data-stu-id="6a794-210">Checksum</span></span>

<span data-ttu-id="6a794-211">Sì</span><span class="sxs-lookup"><span data-stu-id="6a794-211">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="6a794-212">Definizione</span><span class="sxs-lookup"><span data-stu-id="6a794-212">Definition</span></span>

<span data-ttu-id="6a794-213">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="6a794-213">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="6a794-214">La funzione `Func_czech_republic_eu_ssn_or_equivalent` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="6a794-214">The function  `Func_czech_republic_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="6a794-215">Viene trovata una `Keywords_czech_republic_eu_ssn_or_equivalent` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="6a794-215">A keyword from  `Keywords_czech_republic_eu_ssn_or_equivalent` is found.</span></span> 
    
<span data-ttu-id="6a794-216">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="6a794-216">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="6a794-217">La funzione `Func_czech_republic_eu_ssn_or_equivalent` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="6a794-217">The function  `Func_czech_republic_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="6a794-218">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="6a794-218">Keywords</span></span>

#### <a name="keywordsczechrepubliceussnorequivalent"></a><span data-ttu-id="6a794-219">Keywords_czech_republic_eu_ssn_or_equivalent</span><span class="sxs-lookup"><span data-stu-id="6a794-219">Keywords_czech_republic_eu_ssn_or_equivalent</span></span>

<span data-ttu-id="6a794-220">numero di nascita</span><span class="sxs-lookup"><span data-stu-id="6a794-220">birth number</span></span>
  
<span data-ttu-id="6a794-221">national identification number</span><span class="sxs-lookup"><span data-stu-id="6a794-221">national identification number</span></span>
  
<span data-ttu-id="6a794-222">numero di identificazione personale</span><span class="sxs-lookup"><span data-stu-id="6a794-222">personal identification number</span></span>
  
<span data-ttu-id="6a794-223">social security number</span><span class="sxs-lookup"><span data-stu-id="6a794-223">social security number</span></span>
  
<span data-ttu-id="6a794-224">nationalnumber #</span><span class="sxs-lookup"><span data-stu-id="6a794-224">nationalnumber#</span></span>
  
<span data-ttu-id="6a794-225">SSN</span><span class="sxs-lookup"><span data-stu-id="6a794-225">ssn#</span></span>
  
<span data-ttu-id="6a794-226">SSN</span><span class="sxs-lookup"><span data-stu-id="6a794-226">ssn</span></span>
  
<span data-ttu-id="6a794-227">numero nazionale</span><span class="sxs-lookup"><span data-stu-id="6a794-227">national number</span></span>
  
<span data-ttu-id="6a794-228">numero ID personale</span><span class="sxs-lookup"><span data-stu-id="6a794-228">personal id number</span></span>
  
<span data-ttu-id="6a794-229">personalidnumber #</span><span class="sxs-lookup"><span data-stu-id="6a794-229">personalidnumber#</span></span>
  
<span data-ttu-id="6a794-230">rč</span><span class="sxs-lookup"><span data-stu-id="6a794-230">rč</span></span>
  
<span data-ttu-id="6a794-231">rodné číslo</span><span class="sxs-lookup"><span data-stu-id="6a794-231">rodné číslo</span></span>
  
<span data-ttu-id="6a794-232">rodne cislo</span><span class="sxs-lookup"><span data-stu-id="6a794-232">rodne cislo</span></span>
  
## <a name="denmark"></a><span data-ttu-id="6a794-233">Danimarca</span><span class="sxs-lookup"><span data-stu-id="6a794-233">Denmark</span></span>

### <a name="format"></a><span data-ttu-id="6a794-234">Formato</span><span class="sxs-lookup"><span data-stu-id="6a794-234">Format</span></span>

<span data-ttu-id="6a794-235">Dieci cifre e un trattino nel modello specificato</span><span class="sxs-lookup"><span data-stu-id="6a794-235">Ten digits and a hyphen in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="6a794-236">Modello</span><span class="sxs-lookup"><span data-stu-id="6a794-236">Pattern</span></span>

<span data-ttu-id="6a794-237">Dieci cifre e un trattino:</span><span class="sxs-lookup"><span data-stu-id="6a794-237">Ten digits and a hyphen:</span></span>
  
- <span data-ttu-id="6a794-238">Sei cifre che corrispondono alla data di nascita (GGMMAA)</span><span class="sxs-lookup"><span data-stu-id="6a794-238">Six digits that correspond to the birth date (DDMMYY)</span></span> 
    
- <span data-ttu-id="6a794-239">Una lineetta</span><span class="sxs-lookup"><span data-stu-id="6a794-239">A hyphen</span></span>
    
- <span data-ttu-id="6a794-240">Quattro cifre che corrispondono a un numero di sequenza</span><span class="sxs-lookup"><span data-stu-id="6a794-240">Four digits that correspond to a sequence number</span></span>
    
### <a name="checksum"></a><span data-ttu-id="6a794-241">Checksum</span><span class="sxs-lookup"><span data-stu-id="6a794-241">Checksum</span></span>

<span data-ttu-id="6a794-242">Sì</span><span class="sxs-lookup"><span data-stu-id="6a794-242">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="6a794-243">Definizione</span><span class="sxs-lookup"><span data-stu-id="6a794-243">Definition</span></span>

<span data-ttu-id="6a794-244">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="6a794-244">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="6a794-245">La funzione `Func_denmark_eu_ssn_or_equivalent` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="6a794-245">The function  `Func_denmark_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="6a794-246">Viene trovata una `Keywords_denmark_eu_ssn_or_equivalent` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="6a794-246">A keyword from  `Keywords_denmark_eu_ssn_or_equivalent` is found.</span></span> 
    
<span data-ttu-id="6a794-247">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="6a794-247">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="6a794-248">La funzione `Func_denmark_eu_ssn_or_equivalent` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="6a794-248">The function  `Func_denmark_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="6a794-249">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="6a794-249">Keywords</span></span>

#### <a name="keywordsdenmarkeussnorequivalent"></a><span data-ttu-id="6a794-250">Keywords_denmark_eu_ssn_or_equivalent</span><span class="sxs-lookup"><span data-stu-id="6a794-250">Keywords_denmark_eu_ssn_or_equivalent</span></span>

<span data-ttu-id="6a794-251">numero di identificazione personale</span><span class="sxs-lookup"><span data-stu-id="6a794-251">personal identification number</span></span>
  
<span data-ttu-id="6a794-252">national identification number</span><span class="sxs-lookup"><span data-stu-id="6a794-252">national identification number</span></span>
  
<span data-ttu-id="6a794-253">social security number</span><span class="sxs-lookup"><span data-stu-id="6a794-253">social security number</span></span>
  
<span data-ttu-id="6a794-254">nationalnumber #</span><span class="sxs-lookup"><span data-stu-id="6a794-254">nationalnumber#</span></span>
  
<span data-ttu-id="6a794-255">SSN</span><span class="sxs-lookup"><span data-stu-id="6a794-255">ssn#</span></span>
  
<span data-ttu-id="6a794-256">SSN</span><span class="sxs-lookup"><span data-stu-id="6a794-256">ssn</span></span>
  
<span data-ttu-id="6a794-257">numero nazionale</span><span class="sxs-lookup"><span data-stu-id="6a794-257">national number</span></span>
  
<span data-ttu-id="6a794-258">numero ID personale</span><span class="sxs-lookup"><span data-stu-id="6a794-258">personal id number</span></span>
  
<span data-ttu-id="6a794-259">personalidnumber #</span><span class="sxs-lookup"><span data-stu-id="6a794-259">personalidnumber#</span></span>
  
<span data-ttu-id="6a794-260">CPR-Nummer</span><span class="sxs-lookup"><span data-stu-id="6a794-260">cpr-nummer</span></span>
  
<span data-ttu-id="6a794-261">personnummer</span><span class="sxs-lookup"><span data-stu-id="6a794-261">personnummer</span></span>
  
## <a name="finland"></a><span data-ttu-id="6a794-262">Finlandia</span><span class="sxs-lookup"><span data-stu-id="6a794-262">Finland</span></span>

### <a name="format"></a><span data-ttu-id="6a794-263">Formato</span><span class="sxs-lookup"><span data-stu-id="6a794-263">Format</span></span>

<span data-ttu-id="6a794-264">Una combinazione di 11 caratteri nel formato specificato</span><span class="sxs-lookup"><span data-stu-id="6a794-264">An 11-character combination in the specified format</span></span>
  
### <a name="pattern"></a><span data-ttu-id="6a794-265">Modello</span><span class="sxs-lookup"><span data-stu-id="6a794-265">Pattern</span></span>

<span data-ttu-id="6a794-266">Una combinazione di 11 caratteri nel formato specificato:</span><span class="sxs-lookup"><span data-stu-id="6a794-266">An 11-character combination in the specified format:</span></span>
  
-  <span data-ttu-id="6a794-267">Sei cifre</span><span class="sxs-lookup"><span data-stu-id="6a794-267">Six digits</span></span> 
    
- <span data-ttu-id="6a794-268">Un'istanza di una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="6a794-268">One instance of one of the following:</span></span>
    
  - <span data-ttu-id="6a794-269">Segno più</span><span class="sxs-lookup"><span data-stu-id="6a794-269">Plus symbol</span></span>
    
  - <span data-ttu-id="6a794-270">Segno meno</span><span class="sxs-lookup"><span data-stu-id="6a794-270">Minus symbol</span></span>
    
  - <span data-ttu-id="6a794-271">La lettera "A" (senza distinzione tra maiuscole e minuscole)</span><span class="sxs-lookup"><span data-stu-id="6a794-271">The letter "A" (not case-sensitive)</span></span>
    
- <span data-ttu-id="6a794-272">Tre cifre</span><span class="sxs-lookup"><span data-stu-id="6a794-272">Three digits</span></span>
    
- <span data-ttu-id="6a794-273">Una lettera o una cifra</span><span class="sxs-lookup"><span data-stu-id="6a794-273">One letter or one digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="6a794-274">Checksum</span><span class="sxs-lookup"><span data-stu-id="6a794-274">Checksum</span></span>

<span data-ttu-id="6a794-275">Sì</span><span class="sxs-lookup"><span data-stu-id="6a794-275">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="6a794-276">Definizione</span><span class="sxs-lookup"><span data-stu-id="6a794-276">Definition</span></span>

<span data-ttu-id="6a794-277">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="6a794-277">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="6a794-278">La funzione `Func_finland_eu_ssn_or_equivalent` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="6a794-278">The function  `Func_finland_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="6a794-279">Viene trovata una `Keywords_finland_eu_ssn_or_equivalent` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="6a794-279">A keyword from  `Keywords_finland_eu_ssn_or_equivalent` is found.</span></span> 
    
<span data-ttu-id="6a794-280">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="6a794-280">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="6a794-281">La funzione `Func_finland_eu_ssn_or_equivalent` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="6a794-281">The function  `Func_finland_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="6a794-282">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="6a794-282">Keywords</span></span>

#### <a name="keywordsfinlandeussnorequivalent"></a><span data-ttu-id="6a794-283">Keywords_finland_eu_ssn_or_equivalent</span><span class="sxs-lookup"><span data-stu-id="6a794-283">Keywords_finland_eu_ssn_or_equivalent</span></span>

<span data-ttu-id="6a794-284">identification number</span><span class="sxs-lookup"><span data-stu-id="6a794-284">identification number</span></span>
  
<span data-ttu-id="6a794-285">ID personale</span><span class="sxs-lookup"><span data-stu-id="6a794-285">personal id</span></span>
  
<span data-ttu-id="6a794-286">numero di identità</span><span class="sxs-lookup"><span data-stu-id="6a794-286">identity number</span></span>
  
<span data-ttu-id="6a794-287">numero di identificazione nazionale finlandese</span><span class="sxs-lookup"><span data-stu-id="6a794-287">finnish national id number</span></span>
  
<span data-ttu-id="6a794-288">personalidnumber #</span><span class="sxs-lookup"><span data-stu-id="6a794-288">personalidnumber#</span></span>
  
<span data-ttu-id="6a794-289">national identification number</span><span class="sxs-lookup"><span data-stu-id="6a794-289">national identification number</span></span>
  
<span data-ttu-id="6a794-290">numero ID</span><span class="sxs-lookup"><span data-stu-id="6a794-290">id number</span></span>
  
<span data-ttu-id="6a794-291">ID nazionale No.</span><span class="sxs-lookup"><span data-stu-id="6a794-291">national id no.</span></span>
  
<span data-ttu-id="6a794-292">numero ID nazionale</span><span class="sxs-lookup"><span data-stu-id="6a794-292">national id number</span></span>
  
<span data-ttu-id="6a794-293">ID No</span><span class="sxs-lookup"><span data-stu-id="6a794-293">id no</span></span>
  
<span data-ttu-id="6a794-294">tunnistenumero</span><span class="sxs-lookup"><span data-stu-id="6a794-294">tunnistenumero</span></span>
  
<span data-ttu-id="6a794-295">henkilötunnus</span><span class="sxs-lookup"><span data-stu-id="6a794-295">henkilötunnus</span></span>
  
<span data-ttu-id="6a794-296">yksilöllinen henkilökohtainen tunnistenumero</span><span class="sxs-lookup"><span data-stu-id="6a794-296">yksilöllinen henkilökohtainen tunnistenumero</span></span>
  
<span data-ttu-id="6a794-297">ainutlaatuinen henkilökohtainen tunnus</span><span class="sxs-lookup"><span data-stu-id="6a794-297">ainutlaatuinen henkilökohtainen tunnus</span></span>
  
<span data-ttu-id="6a794-298">numero identiteetti</span><span class="sxs-lookup"><span data-stu-id="6a794-298">identiteetti numero</span></span>
  
<span data-ttu-id="6a794-299">Suomen Kansallinen henkilötunnus</span><span class="sxs-lookup"><span data-stu-id="6a794-299">suomen kansallinen henkilötunnus</span></span>
  
<span data-ttu-id="6a794-300">henkilötunnusnumero #</span><span class="sxs-lookup"><span data-stu-id="6a794-300">henkilötunnusnumero#</span></span>
  
<span data-ttu-id="6a794-301">kansallisen tunnistenumero</span><span class="sxs-lookup"><span data-stu-id="6a794-301">kansallisen tunnistenumero</span></span>
  
<span data-ttu-id="6a794-302">tunnusnumero</span><span class="sxs-lookup"><span data-stu-id="6a794-302">tunnusnumero</span></span>
  
<span data-ttu-id="6a794-303">Kansallinen tunnus numero</span><span class="sxs-lookup"><span data-stu-id="6a794-303">kansallinen tunnus numero</span></span>
  
<span data-ttu-id="6a794-304">hetu</span><span class="sxs-lookup"><span data-stu-id="6a794-304">hetu</span></span>
  
## <a name="france"></a><span data-ttu-id="6a794-305">Francia</span><span class="sxs-lookup"><span data-stu-id="6a794-305">France</span></span>

<span data-ttu-id="6a794-306">Per informazioni dettagliate, vedere la sezione "Francia social preVidenza (INSEE)" in [che cosa cercano i tipi di informazioni riservate](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="6a794-306">For details, see the section "France Social Security Number (INSEE)" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="germany"></a><span data-ttu-id="6a794-307">Germania</span><span class="sxs-lookup"><span data-stu-id="6a794-307">Germany</span></span>

<span data-ttu-id="6a794-308">Per informazioni dettagliate, vedere la sezione "Germania identità numero di carta" in [che cosa cercano i tipi di informazioni riservate](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="6a794-308">For details, see the section "Germany Identity Card Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="greece"></a><span data-ttu-id="6a794-309">Grecia</span><span class="sxs-lookup"><span data-stu-id="6a794-309">Greece</span></span>

<span data-ttu-id="6a794-310">Per informazioni dettagliate, vedere la sezione "Grecia National ID Card" in [quello che cercano i tipi di informazioni riservate](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="6a794-310">For details, see the section "Greece National ID Card" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="hungary"></a><span data-ttu-id="6a794-311">Ungheria</span><span class="sxs-lookup"><span data-stu-id="6a794-311">Hungary</span></span>

### <a name="format"></a><span data-ttu-id="6a794-312">Formato</span><span class="sxs-lookup"><span data-stu-id="6a794-312">Format</span></span>

<span data-ttu-id="6a794-313">Nove cifre senza spazi e delimitatori</span><span class="sxs-lookup"><span data-stu-id="6a794-313">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="6a794-314">Modello</span><span class="sxs-lookup"><span data-stu-id="6a794-314">Pattern</span></span>

<span data-ttu-id="6a794-315">9 cifre</span><span class="sxs-lookup"><span data-stu-id="6a794-315">Nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="6a794-316">Checksum</span><span class="sxs-lookup"><span data-stu-id="6a794-316">Checksum</span></span>

<span data-ttu-id="6a794-317">Sì</span><span class="sxs-lookup"><span data-stu-id="6a794-317">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="6a794-318">Definizione</span><span class="sxs-lookup"><span data-stu-id="6a794-318">Definition</span></span>

<span data-ttu-id="6a794-319">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="6a794-319">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="6a794-320">La funzione `Func_hungary_eu_ssn_or_equivalent` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="6a794-320">The function  `Func_hungary_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="6a794-321">Viene trovata una `Keywords_hungary_eu_ssn_or_equivalent` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="6a794-321">A keyword from  `Keywords_hungary_eu_ssn_or_equivalent` is found.</span></span> 
    
<span data-ttu-id="6a794-322">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="6a794-322">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="6a794-323">La funzione `Func_hungary_eu_ssn_or_equivalent` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="6a794-323">The function  `Func_hungary_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="6a794-324">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="6a794-324">Keywords</span></span>

#### <a name="keywordshungaryeussnorequivalent"></a><span data-ttu-id="6a794-325">Keywords_hungary_eu_ssn_or_equivalent</span><span class="sxs-lookup"><span data-stu-id="6a794-325">Keywords_hungary_eu_ssn_or_equivalent</span></span>

<span data-ttu-id="6a794-326">codice di previdenza sociale ungherese</span><span class="sxs-lookup"><span data-stu-id="6a794-326">hungarian social security number</span></span>
  
<span data-ttu-id="6a794-327">social security number</span><span class="sxs-lookup"><span data-stu-id="6a794-327">social security number</span></span>
  
<span data-ttu-id="6a794-328">SocialSecurityNumber #</span><span class="sxs-lookup"><span data-stu-id="6a794-328">socialsecuritynumber#</span></span>
  
<span data-ttu-id="6a794-329">hssn #</span><span class="sxs-lookup"><span data-stu-id="6a794-329">hssn#</span></span>
  
<span data-ttu-id="6a794-330">socialsecuritynno</span><span class="sxs-lookup"><span data-stu-id="6a794-330">socialsecuritynno</span></span>
  
<span data-ttu-id="6a794-331">hssn</span><span class="sxs-lookup"><span data-stu-id="6a794-331">hssn</span></span>
  
<span data-ttu-id="6a794-332">Taj</span><span class="sxs-lookup"><span data-stu-id="6a794-332">taj</span></span>
  
<span data-ttu-id="6a794-333">Taj</span><span class="sxs-lookup"><span data-stu-id="6a794-333">taj#</span></span>
  
<span data-ttu-id="6a794-334">SSN</span><span class="sxs-lookup"><span data-stu-id="6a794-334">ssn</span></span>
  
<span data-ttu-id="6a794-335">SSN</span><span class="sxs-lookup"><span data-stu-id="6a794-335">ssn#</span></span>
  
<span data-ttu-id="6a794-336">previdenza sociale No</span><span class="sxs-lookup"><span data-stu-id="6a794-336">social security no</span></span>
  
<span data-ttu-id="6a794-337">ÁFA</span><span class="sxs-lookup"><span data-stu-id="6a794-337">áfa</span></span>
  
<span data-ttu-id="6a794-338">közösségi adószám</span><span class="sxs-lookup"><span data-stu-id="6a794-338">közösségi adószám</span></span>
  
<span data-ttu-id="6a794-339">Általános forgalmi Adó szám</span><span class="sxs-lookup"><span data-stu-id="6a794-339">általános forgalmi adó szám</span></span>
  
<span data-ttu-id="6a794-340">hozzáadottérték Adó</span><span class="sxs-lookup"><span data-stu-id="6a794-340">hozzáadottérték adó</span></span>
  
<span data-ttu-id="6a794-341">ÁFA szám</span><span class="sxs-lookup"><span data-stu-id="6a794-341">áfa szám</span></span>
  
<span data-ttu-id="6a794-342">Magyar ÁFA szám</span><span class="sxs-lookup"><span data-stu-id="6a794-342">magyar áfa szám</span></span>
  
## <a name="portugal"></a><span data-ttu-id="6a794-343">Portogallo</span><span class="sxs-lookup"><span data-stu-id="6a794-343">Portugal</span></span>

<span data-ttu-id="6a794-344">Per informazioni dettagliate, vedere la sezione "Portugal Citizen Card Number" in [quello che i tipi di informazioni riservate cercano](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="6a794-344">For details, see the section "Portugal Citizen Card Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="spain"></a><span data-ttu-id="6a794-345">Spagna</span><span class="sxs-lookup"><span data-stu-id="6a794-345">Spain</span></span>

<span data-ttu-id="6a794-346">Per informazioni dettagliate, vedere la sezione "Spagna Social preVidenza sociale (SSN)" in [che cosa cercano i tipi di informazioni riservate](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="6a794-346">For details, see the section "Spain Social Security Number (SSN)" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="sweden"></a><span data-ttu-id="6a794-347">Svezia</span><span class="sxs-lookup"><span data-stu-id="6a794-347">Sweden</span></span>

### <a name="format"></a><span data-ttu-id="6a794-348">Formato</span><span class="sxs-lookup"><span data-stu-id="6a794-348">Format</span></span>

<span data-ttu-id="6a794-349">12 cifre senza spazi e delimitatori</span><span class="sxs-lookup"><span data-stu-id="6a794-349">12 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="6a794-350">Modello</span><span class="sxs-lookup"><span data-stu-id="6a794-350">Pattern</span></span>

<span data-ttu-id="6a794-351">12 cifre:</span><span class="sxs-lookup"><span data-stu-id="6a794-351">12 digits:</span></span>
  
-  <span data-ttu-id="6a794-352">Otto cifre che corrispondono alla data di nascita (AAAAMMGG)</span><span class="sxs-lookup"><span data-stu-id="6a794-352">Eight digits that correspond to the birth date (YYYYMMDD)</span></span> 
    
- <span data-ttu-id="6a794-353">Tre cifre che corrispondono a un numero di serie in cui:</span><span class="sxs-lookup"><span data-stu-id="6a794-353">Three digits that correspond to a serial number where:</span></span> 
    
  - <span data-ttu-id="6a794-354">L'ultima cifra del numero di serie indica il sesso per l'assegnazione di un numero dispari per il maschio e per un numero pari per la femmina</span><span class="sxs-lookup"><span data-stu-id="6a794-354">The last digit in the serial number indicates gender by the assignment of an odd number for male and an even number for female</span></span>
    
  - <span data-ttu-id="6a794-355">Fino a 1990, l'assegnazione del numero di serie corrispondeva alla contea in cui è Nato il portatore del numero o (se è nato prima del 1947) dove viveva, secondo i registri delle tasse, il 1 ° gennaio 1947, con un codice speciale (solitamente 9 come settima cifra) per immigrati</span><span class="sxs-lookup"><span data-stu-id="6a794-355">Up to 1990, the assignment of serial number corresponded to the county where the bearer of the number was born or (if born before 1947) where he/she had been living, according to tax records, on January 1, 1947, with a special code (usually 9 as the 7th digit) for immigrants</span></span> 
    
- <span data-ttu-id="6a794-356">Una cifra di controllo</span><span class="sxs-lookup"><span data-stu-id="6a794-356">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="6a794-357">Checksum</span><span class="sxs-lookup"><span data-stu-id="6a794-357">Checksum</span></span>

<span data-ttu-id="6a794-358">Sì</span><span class="sxs-lookup"><span data-stu-id="6a794-358">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="6a794-359">Definizione</span><span class="sxs-lookup"><span data-stu-id="6a794-359">Definition</span></span>

<span data-ttu-id="6a794-360">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="6a794-360">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="6a794-361">La funzione `Func_sweden_eu_ssn_or_equivalent` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="6a794-361">The function  `Func_sweden_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="6a794-362">Viene trovata una `Keywords_sweden_eu_ssn_or_equivalent` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="6a794-362">A keyword from  `Keywords_sweden_eu_ssn_or_equivalent` is found.</span></span> 
    
<span data-ttu-id="6a794-363">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="6a794-363">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="6a794-364">La funzione `Func_sweden_eu_ssn_or_equivalent` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="6a794-364">The function  `Func_sweden_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="6a794-365">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="6a794-365">Keywords</span></span>

#### <a name="keywordsswedeneussnorequivalent"></a><span data-ttu-id="6a794-366">Keywords_sweden_eu_ssn_or_equivalent</span><span class="sxs-lookup"><span data-stu-id="6a794-366">Keywords_sweden_eu_ssn_or_equivalent</span></span>

<span data-ttu-id="6a794-367">numero ID personale</span><span class="sxs-lookup"><span data-stu-id="6a794-367">personal id number</span></span>
  
<span data-ttu-id="6a794-368">identification number</span><span class="sxs-lookup"><span data-stu-id="6a794-368">identification number</span></span>
  
<span data-ttu-id="6a794-369">ID personale No</span><span class="sxs-lookup"><span data-stu-id="6a794-369">personal id no</span></span>
  
<span data-ttu-id="6a794-370">identità No</span><span class="sxs-lookup"><span data-stu-id="6a794-370">identity no</span></span>
  
<span data-ttu-id="6a794-371">identificazione no</span><span class="sxs-lookup"><span data-stu-id="6a794-371">identification no</span></span>
  
<span data-ttu-id="6a794-372">identificazione personale No</span><span class="sxs-lookup"><span data-stu-id="6a794-372">personal identification no</span></span>
  
<span data-ttu-id="6a794-373">ID personnummer</span><span class="sxs-lookup"><span data-stu-id="6a794-373">personnummer id</span></span>
  
<span data-ttu-id="6a794-374">ID personligt-Nummer</span><span class="sxs-lookup"><span data-stu-id="6a794-374">personligt id-nummer</span></span>
  
<span data-ttu-id="6a794-375">ID unikt-Nummer</span><span class="sxs-lookup"><span data-stu-id="6a794-375">unikt id-nummer</span></span>
  
<span data-ttu-id="6a794-376">personnummer</span><span class="sxs-lookup"><span data-stu-id="6a794-376">personnummer</span></span>
  
<span data-ttu-id="6a794-377">identifikationsnumret</span><span class="sxs-lookup"><span data-stu-id="6a794-377">identifikationsnumret</span></span>
  
<span data-ttu-id="6a794-378">personnummer</span><span class="sxs-lookup"><span data-stu-id="6a794-378">personnummer#</span></span>
  
<span data-ttu-id="6a794-379">identifikationsnumret #</span><span class="sxs-lookup"><span data-stu-id="6a794-379">identifikationsnumret#</span></span>
  
## <a name="see-also"></a><span data-ttu-id="6a794-380">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6a794-380">See also</span></span>

[<span data-ttu-id="6a794-381">Cosa individuano le tipologie di informazioni sensibili</span><span class="sxs-lookup"><span data-stu-id="6a794-381">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)

