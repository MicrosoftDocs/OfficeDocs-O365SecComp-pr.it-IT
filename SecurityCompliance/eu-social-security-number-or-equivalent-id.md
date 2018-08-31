---
title: ID di numero di previdenza sociale UE o equivalente
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 8/17/2018
ms.audience: Admin
ms.topic: reference
ms.service: o365-administration
localization_priority: Normal
ms.assetid: 1fabd341-e594-4bfe-961c-62aa82893f60
description: Questo argomento viene illustrato quali criteri di criterio DLP perdita dei dati Cerca qualora venga rilevato un tipo di informazione sensibile numero di previdenza sociale UE o l'ID equivalenti. Questo tipo di informazioni riservate definisce le diverse combinazioni, parole chiave e altri elementi di prova per ogni paese.
ms.openlocfilehash: 6f1027dcfb648ed937b8180d74d4bc6348dab650
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/27/2018
ms.locfileid: "22530681"
---
# <a name="eu-social-security-number-or-equivalent-id"></a><span data-ttu-id="cdae1-104">ID di numero di previdenza sociale UE o equivalente</span><span class="sxs-lookup"><span data-stu-id="cdae1-104">EU Social Security Number or Equivalent ID</span></span>

<span data-ttu-id="cdae1-p102">Questo argomento viene illustrato quali criteri di criterio DLP perdita dei dati Cerca qualora venga rilevato un tipo di informazione sensibile UE numero di previdenza sociale (SSN) o l'ID equivalenti. Questo tipo di informazioni riservate definisce le diverse combinazioni, parole chiave e altri elementi di prova per ogni paese.</span><span class="sxs-lookup"><span data-stu-id="cdae1-p102">This topic shows what a data loss prevention (DLP) policy looks for when it detects the EU Social Security Number (SSN) or Equivalent ID sensitive information type. This sensitive information type defines different patterns, keywords, and other evidence for each country.</span></span>
  
## <a name="austria"></a><span data-ttu-id="cdae1-107">Austria</span><span class="sxs-lookup"><span data-stu-id="cdae1-107">Austria</span></span>

### <a name="format"></a><span data-ttu-id="cdae1-108">Formato</span><span class="sxs-lookup"><span data-stu-id="cdae1-108">Format</span></span>

<span data-ttu-id="cdae1-109">10 cifre nel formato specificato</span><span class="sxs-lookup"><span data-stu-id="cdae1-109">10 digits in the specified format</span></span>
  
### <a name="pattern"></a><span data-ttu-id="cdae1-110">Modello</span><span class="sxs-lookup"><span data-stu-id="cdae1-110">Pattern</span></span>

<span data-ttu-id="cdae1-111">10 cifre:</span><span class="sxs-lookup"><span data-stu-id="cdae1-111">10 digits:</span></span>
  
-  <span data-ttu-id="cdae1-112">Tre cifre che corrispondono a un numero di serie</span><span class="sxs-lookup"><span data-stu-id="cdae1-112">Three digits that correspond to a serial number</span></span> 
    
- <span data-ttu-id="cdae1-113">Cifra di un controllo</span><span class="sxs-lookup"><span data-stu-id="cdae1-113">One check digit</span></span>
    
- <span data-ttu-id="cdae1-114">Sei cifre che corrispondono alla data di nascita (DDMMYY)</span><span class="sxs-lookup"><span data-stu-id="cdae1-114">Six digits that correspond to the birth date (DDMMYY)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="cdae1-115">Checksum</span><span class="sxs-lookup"><span data-stu-id="cdae1-115">Checksum</span></span>

<span data-ttu-id="cdae1-116">Sì</span><span class="sxs-lookup"><span data-stu-id="cdae1-116">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="cdae1-117">Definizione</span><span class="sxs-lookup"><span data-stu-id="cdae1-117">Definition</span></span>

<span data-ttu-id="cdae1-118">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="cdae1-118">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="cdae1-119">La funzione `Func_austria_eu_ssn_or_equivalent` consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="cdae1-119">The function  `Func_austria_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="cdae1-120">Una parola chiave da `Keywords_austria_eu_ssn_or_equivalent` viene trovato.</span><span class="sxs-lookup"><span data-stu-id="cdae1-120">A keyword from  `Keywords_austria_eu_ssn_or_equivalent` is found.</span></span> 
    
<span data-ttu-id="cdae1-121">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="cdae1-121">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="cdae1-122">La funzione `Func_austria_eu_ssn_or_equivalent` consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="cdae1-122">The function  `Func_austria_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="cdae1-123">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="cdae1-123">Keywords</span></span>

#### <a name="keywordsaustriaeussnorequivalent"></a><span data-ttu-id="cdae1-124">Keywords_austria_eu_ssn_or_equivalent</span><span class="sxs-lookup"><span data-stu-id="cdae1-124">Keywords_austria_eu_ssn_or_equivalent</span></span>

<span data-ttu-id="cdae1-125">sicurezza sociale non</span><span class="sxs-lookup"><span data-stu-id="cdae1-125">social security no</span></span>
  
<span data-ttu-id="cdae1-126">social security number
</span><span class="sxs-lookup"><span data-stu-id="cdae1-126">social security number</span></span>
  
<span data-ttu-id="cdae1-127">
social security code</span><span class="sxs-lookup"><span data-stu-id="cdae1-127">social security code</span></span>
  
<span data-ttu-id="cdae1-128">numero di assicurazione</span><span class="sxs-lookup"><span data-stu-id="cdae1-128">insurance number</span></span>
  
<span data-ttu-id="cdae1-129">ssn austriaco</span><span class="sxs-lookup"><span data-stu-id="cdae1-129">austrian ssn</span></span>
  
<span data-ttu-id="cdae1-130">SSN #</span><span class="sxs-lookup"><span data-stu-id="cdae1-130">ssn#</span></span>
  
<span data-ttu-id="cdae1-131">SSN</span><span class="sxs-lookup"><span data-stu-id="cdae1-131">ssn</span></span>
  
<span data-ttu-id="cdae1-132">codice di assicurazione</span><span class="sxs-lookup"><span data-stu-id="cdae1-132">insurance code</span></span>
  
<span data-ttu-id="cdae1-133">codice di assicurazione #</span><span class="sxs-lookup"><span data-stu-id="cdae1-133">insurance code#</span></span>
  
<span data-ttu-id="cdae1-134">socialsecurityno #</span><span class="sxs-lookup"><span data-stu-id="cdae1-134">socialsecurityno#</span></span>
  
<span data-ttu-id="cdae1-135">sozialversicherungsnummer</span><span class="sxs-lookup"><span data-stu-id="cdae1-135">sozialversicherungsnummer</span></span>
  
<span data-ttu-id="cdae1-136">soziale sicherheit kein</span><span class="sxs-lookup"><span data-stu-id="cdae1-136">soziale sicherheit kein</span></span>
  
<span data-ttu-id="cdae1-137">versicherungsnummer</span><span class="sxs-lookup"><span data-stu-id="cdae1-137">versicherungsnummer</span></span>
  
## <a name="belgium"></a><span data-ttu-id="cdae1-138">Belgio</span><span class="sxs-lookup"><span data-stu-id="cdae1-138">Belgium</span></span>

### <a name="format"></a><span data-ttu-id="cdae1-139">Formato</span><span class="sxs-lookup"><span data-stu-id="cdae1-139">Format</span></span>

<span data-ttu-id="cdae1-140">11 cifre senza spazi o delimitatori</span><span class="sxs-lookup"><span data-stu-id="cdae1-140">11 digits without spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="cdae1-141">Modello</span><span class="sxs-lookup"><span data-stu-id="cdae1-141">Pattern</span></span>

<span data-ttu-id="cdae1-142">11 cifre</span><span class="sxs-lookup"><span data-stu-id="cdae1-142">11 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="cdae1-143">Checksum</span><span class="sxs-lookup"><span data-stu-id="cdae1-143">Checksum</span></span>

<span data-ttu-id="cdae1-144">Sì</span><span class="sxs-lookup"><span data-stu-id="cdae1-144">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="cdae1-145">Definizione</span><span class="sxs-lookup"><span data-stu-id="cdae1-145">Definition</span></span>

<span data-ttu-id="cdae1-146">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="cdae1-146">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="cdae1-147">La funzione `Func_belgium_eu_ssn_or_equivalent` consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="cdae1-147">The function  `Func_belgium_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="cdae1-148">Una parola chiave da `Keywords_belgium_eu_ssn_or_equivalent` viene trovato.</span><span class="sxs-lookup"><span data-stu-id="cdae1-148">A keyword from  `Keywords_belgium_eu_ssn_or_equivalent` is found.</span></span> 
    
<span data-ttu-id="cdae1-149">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="cdae1-149">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="cdae1-150">La funzione `Func_belgium_eu_ssn_or_equivalent` consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="cdae1-150">The function  `Func_belgium_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="cdae1-151">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="cdae1-151">Keywords</span></span>

#### <a name="keywordsbelgiumeussnorequivalent"></a><span data-ttu-id="cdae1-152">Keywords_belgium_eu_ssn_or_equivalent</span><span class="sxs-lookup"><span data-stu-id="cdae1-152">Keywords_belgium_eu_ssn_or_equivalent</span></span>

<span data-ttu-id="cdae1-153">numero nazionale belga</span><span class="sxs-lookup"><span data-stu-id="cdae1-153">belgian national number</span></span>
  
<span data-ttu-id="cdae1-154">numero nazionale</span><span class="sxs-lookup"><span data-stu-id="cdae1-154">national number</span></span>
  
<span data-ttu-id="cdae1-155">social security number
</span><span class="sxs-lookup"><span data-stu-id="cdae1-155">social security number</span></span>
  
<span data-ttu-id="cdae1-156">nationalnumber #</span><span class="sxs-lookup"><span data-stu-id="cdae1-156">nationalnumber#</span></span>
  
<span data-ttu-id="cdae1-157">SSN #</span><span class="sxs-lookup"><span data-stu-id="cdae1-157">ssn#</span></span>
  
<span data-ttu-id="cdae1-158">SSN</span><span class="sxs-lookup"><span data-stu-id="cdae1-158">ssn</span></span>
  
<span data-ttu-id="cdae1-159">nationalnumber</span><span class="sxs-lookup"><span data-stu-id="cdae1-159">nationalnumber</span></span>
  
<span data-ttu-id="cdae1-160">bnn #</span><span class="sxs-lookup"><span data-stu-id="cdae1-160">bnn#</span></span>
  
<span data-ttu-id="cdae1-161">bnn</span><span class="sxs-lookup"><span data-stu-id="cdae1-161">bnn</span></span>
  
<span data-ttu-id="cdae1-162">numero id personale</span><span class="sxs-lookup"><span data-stu-id="cdae1-162">personal id number</span></span>
  
<span data-ttu-id="cdae1-163">personalidnumber #</span><span class="sxs-lookup"><span data-stu-id="cdae1-163">personalidnumber#</span></span>
  
<span data-ttu-id="cdae1-164">numéro nazionale</span><span class="sxs-lookup"><span data-stu-id="cdae1-164">numéro national</span></span>
  
<span data-ttu-id="cdae1-165">numéro de sécurité
</span><span class="sxs-lookup"><span data-stu-id="cdae1-165">numéro de sécurité</span></span>
  
<span data-ttu-id="cdae1-166">g numéro'assuré</span><span class="sxs-lookup"><span data-stu-id="cdae1-166">numéro d'assuré</span></span>
  
<span data-ttu-id="cdae1-167">identifiant nazionale</span><span class="sxs-lookup"><span data-stu-id="cdae1-167">identifiant national</span></span>
  
<span data-ttu-id="cdae1-168">identifiantnational #</span><span class="sxs-lookup"><span data-stu-id="cdae1-168">identifiantnational#</span></span>
  
<span data-ttu-id="cdae1-169">numéronational #</span><span class="sxs-lookup"><span data-stu-id="cdae1-169">numéronational#</span></span>
  
## <a name="croatia"></a><span data-ttu-id="cdae1-170">Croazia</span><span class="sxs-lookup"><span data-stu-id="cdae1-170">Croatia</span></span>

### <a name="format"></a><span data-ttu-id="cdae1-171">Formato</span><span class="sxs-lookup"><span data-stu-id="cdae1-171">Format</span></span>

<span data-ttu-id="cdae1-172">11 cifre senza spazi e i delimitatori</span><span class="sxs-lookup"><span data-stu-id="cdae1-172">11 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="cdae1-173">Modello</span><span class="sxs-lookup"><span data-stu-id="cdae1-173">Pattern</span></span>

 <span data-ttu-id="cdae1-174">11 cifre:</span><span class="sxs-lookup"><span data-stu-id="cdae1-174">11 digits:</span></span> 
  
-  <span data-ttu-id="cdae1-175">Dieci cifre</span><span class="sxs-lookup"><span data-stu-id="cdae1-175">Ten digits</span></span> 
    
- <span data-ttu-id="cdae1-176">Cifra di un controllo</span><span class="sxs-lookup"><span data-stu-id="cdae1-176">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="cdae1-177">Checksum</span><span class="sxs-lookup"><span data-stu-id="cdae1-177">Checksum</span></span>

<span data-ttu-id="cdae1-178">Sì</span><span class="sxs-lookup"><span data-stu-id="cdae1-178">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="cdae1-179">Definizione</span><span class="sxs-lookup"><span data-stu-id="cdae1-179">Definition</span></span>

<span data-ttu-id="cdae1-180">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="cdae1-180">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="cdae1-181">La funzione `Func_croatia_eu_ssn_or_equivalent` consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="cdae1-181">The function  `Func_croatia_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="cdae1-182">Una parola chiave da `Keywords_croatia_eu_ssn_or_equivalent` viene trovato.</span><span class="sxs-lookup"><span data-stu-id="cdae1-182">A keyword from  `Keywords_croatia_eu_ssn_or_equivalent` is found.</span></span> 
    
<span data-ttu-id="cdae1-183">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="cdae1-183">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="cdae1-184">La funzione `Func_croatia_eu_ssn_or_equivalent` consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="cdae1-184">The function  `Func_croatia_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="cdae1-185">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="cdae1-185">Keywords</span></span>

#### <a name="keywordscroatiaeussnorequivalent"></a><span data-ttu-id="cdae1-186">Keywords_croatia_eu_ssn_or_equivalent</span><span class="sxs-lookup"><span data-stu-id="cdae1-186">Keywords_croatia_eu_ssn_or_equivalent</span></span>

<span data-ttu-id="cdae1-187">numero di identificazione personale</span><span class="sxs-lookup"><span data-stu-id="cdae1-187">personal identification number</span></span>
  
<span data-ttu-id="cdae1-188">numero di cittadini master</span><span class="sxs-lookup"><span data-stu-id="cdae1-188">master citizen number</span></span>
  
<span data-ttu-id="cdae1-189">numero identificativo nazionale</span><span class="sxs-lookup"><span data-stu-id="cdae1-189">national identification number</span></span>
  
<span data-ttu-id="cdae1-190">social security number
</span><span class="sxs-lookup"><span data-stu-id="cdae1-190">social security number</span></span>
  
<span data-ttu-id="cdae1-191">nationalnumber #</span><span class="sxs-lookup"><span data-stu-id="cdae1-191">nationalnumber#</span></span>
  
<span data-ttu-id="cdae1-192">SSN #</span><span class="sxs-lookup"><span data-stu-id="cdae1-192">ssn#</span></span>
  
<span data-ttu-id="cdae1-193">SSN</span><span class="sxs-lookup"><span data-stu-id="cdae1-193">ssn</span></span>
  
<span data-ttu-id="cdae1-194">nationalnumber</span><span class="sxs-lookup"><span data-stu-id="cdae1-194">nationalnumber</span></span>
  
<span data-ttu-id="cdae1-195">bnn #</span><span class="sxs-lookup"><span data-stu-id="cdae1-195">bnn#</span></span>
  
<span data-ttu-id="cdae1-196">bnn</span><span class="sxs-lookup"><span data-stu-id="cdae1-196">bnn</span></span>
  
<span data-ttu-id="cdae1-197">numero id personale</span><span class="sxs-lookup"><span data-stu-id="cdae1-197">personal id number</span></span>
  
<span data-ttu-id="cdae1-198">personalidnumber #</span><span class="sxs-lookup"><span data-stu-id="cdae1-198">personalidnumber#</span></span>
  
<span data-ttu-id="cdae1-199">oib</span><span class="sxs-lookup"><span data-stu-id="cdae1-199">oib</span></span>
  
<span data-ttu-id="cdae1-200">osobni identifikacijski broj</span><span class="sxs-lookup"><span data-stu-id="cdae1-200">osobni identifikacijski broj</span></span>
  
## <a name="czech-republic"></a><span data-ttu-id="cdae1-201">Repubblica Ceca</span><span class="sxs-lookup"><span data-stu-id="cdae1-201">Czech Republic</span></span>

### <a name="format"></a><span data-ttu-id="cdae1-202">Formato</span><span class="sxs-lookup"><span data-stu-id="cdae1-202">Format</span></span>

<span data-ttu-id="cdae1-203">Dieci cifre e una barra rovesciata nella serie specificata</span><span class="sxs-lookup"><span data-stu-id="cdae1-203">Ten digits and a backslash in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="cdae1-204">Modello</span><span class="sxs-lookup"><span data-stu-id="cdae1-204">Pattern</span></span>

<span data-ttu-id="cdae1-205">Dieci cifre e una barra rovesciata:</span><span class="sxs-lookup"><span data-stu-id="cdae1-205">Ten digits and a backslash:</span></span>
  
- <span data-ttu-id="cdae1-206">Sei cifre che corrispondono alla data di nascita (AAMMGG):</span><span class="sxs-lookup"><span data-stu-id="cdae1-206">Six digits that correspond to the birth date (YYMMDD):</span></span> 
    
- <span data-ttu-id="cdae1-207">Una barra rovesciata</span><span class="sxs-lookup"><span data-stu-id="cdae1-207">A backslash</span></span>
    
- <span data-ttu-id="cdae1-208">Tre cifre che corrispondono a un numero di serie che separa le persone nati nella stessa data</span><span class="sxs-lookup"><span data-stu-id="cdae1-208">Three digits that correspond to a serial number that separates persons born on the same date</span></span>
    
- <span data-ttu-id="cdae1-209">Cifra di un controllo</span><span class="sxs-lookup"><span data-stu-id="cdae1-209">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="cdae1-210">Checksum</span><span class="sxs-lookup"><span data-stu-id="cdae1-210">Checksum</span></span>

<span data-ttu-id="cdae1-211">Sì</span><span class="sxs-lookup"><span data-stu-id="cdae1-211">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="cdae1-212">Definizione</span><span class="sxs-lookup"><span data-stu-id="cdae1-212">Definition</span></span>

<span data-ttu-id="cdae1-213">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="cdae1-213">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="cdae1-214">La funzione `Func_czech_republic_eu_ssn_or_equivalent` consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="cdae1-214">The function  `Func_czech_republic_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="cdae1-215">Una parola chiave da `Keywords_czech_republic_eu_ssn_or_equivalent` viene trovato.</span><span class="sxs-lookup"><span data-stu-id="cdae1-215">A keyword from  `Keywords_czech_republic_eu_ssn_or_equivalent` is found.</span></span> 
    
<span data-ttu-id="cdae1-216">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="cdae1-216">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="cdae1-217">La funzione `Func_czech_republic_eu_ssn_or_equivalent` consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="cdae1-217">The function  `Func_czech_republic_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="cdae1-218">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="cdae1-218">Keywords</span></span>

#### <a name="keywordsczechrepubliceussnorequivalent"></a><span data-ttu-id="cdae1-219">Keywords_czech_republic_eu_ssn_or_equivalent</span><span class="sxs-lookup"><span data-stu-id="cdae1-219">Keywords_czech_republic_eu_ssn_or_equivalent</span></span>

<span data-ttu-id="cdae1-220">numero di nascita</span><span class="sxs-lookup"><span data-stu-id="cdae1-220">birth number</span></span>
  
<span data-ttu-id="cdae1-221">numero identificativo nazionale</span><span class="sxs-lookup"><span data-stu-id="cdae1-221">national identification number</span></span>
  
<span data-ttu-id="cdae1-222">numero di identificazione personale</span><span class="sxs-lookup"><span data-stu-id="cdae1-222">personal identification number</span></span>
  
<span data-ttu-id="cdae1-223">social security number
</span><span class="sxs-lookup"><span data-stu-id="cdae1-223">social security number</span></span>
  
<span data-ttu-id="cdae1-224">nationalnumber #</span><span class="sxs-lookup"><span data-stu-id="cdae1-224">nationalnumber#</span></span>
  
<span data-ttu-id="cdae1-225">SSN #</span><span class="sxs-lookup"><span data-stu-id="cdae1-225">ssn#</span></span>
  
<span data-ttu-id="cdae1-226">SSN</span><span class="sxs-lookup"><span data-stu-id="cdae1-226">ssn</span></span>
  
<span data-ttu-id="cdae1-227">numero nazionale</span><span class="sxs-lookup"><span data-stu-id="cdae1-227">national number</span></span>
  
<span data-ttu-id="cdae1-228">numero id personale</span><span class="sxs-lookup"><span data-stu-id="cdae1-228">personal id number</span></span>
  
<span data-ttu-id="cdae1-229">personalidnumber #</span><span class="sxs-lookup"><span data-stu-id="cdae1-229">personalidnumber#</span></span>
  
<span data-ttu-id="cdae1-230">rč</span><span class="sxs-lookup"><span data-stu-id="cdae1-230">rč</span></span>
  
<span data-ttu-id="cdae1-231">rodné číslo</span><span class="sxs-lookup"><span data-stu-id="cdae1-231">rodné číslo</span></span>
  
<span data-ttu-id="cdae1-232">rodne cislo</span><span class="sxs-lookup"><span data-stu-id="cdae1-232">rodne cislo</span></span>
  
## <a name="denmark"></a><span data-ttu-id="cdae1-233">Danimarca</span><span class="sxs-lookup"><span data-stu-id="cdae1-233">Denmark</span></span>

### <a name="format"></a><span data-ttu-id="cdae1-234">Formato</span><span class="sxs-lookup"><span data-stu-id="cdae1-234">Format</span></span>

<span data-ttu-id="cdae1-235">Dieci cifre e un segno meno nella serie specificata</span><span class="sxs-lookup"><span data-stu-id="cdae1-235">Ten digits and a hyphen in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="cdae1-236">Modello</span><span class="sxs-lookup"><span data-stu-id="cdae1-236">Pattern</span></span>

<span data-ttu-id="cdae1-237">Dieci cifre e un segno meno:</span><span class="sxs-lookup"><span data-stu-id="cdae1-237">Ten digits and a hyphen:</span></span>
  
- <span data-ttu-id="cdae1-238">Sei cifre che corrispondono alla data di nascita (DDMMYY)</span><span class="sxs-lookup"><span data-stu-id="cdae1-238">Six digits that correspond to the birth date (DDMMYY)</span></span> 
    
- <span data-ttu-id="cdae1-239">Una lineetta</span><span class="sxs-lookup"><span data-stu-id="cdae1-239">A hyphen</span></span>
    
- <span data-ttu-id="cdae1-240">Quattro cifre che corrispondono a un numero di sequenza</span><span class="sxs-lookup"><span data-stu-id="cdae1-240">Four digits that correspond to a sequence number</span></span>
    
### <a name="checksum"></a><span data-ttu-id="cdae1-241">Checksum</span><span class="sxs-lookup"><span data-stu-id="cdae1-241">Checksum</span></span>

<span data-ttu-id="cdae1-242">Sì</span><span class="sxs-lookup"><span data-stu-id="cdae1-242">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="cdae1-243">Definizione</span><span class="sxs-lookup"><span data-stu-id="cdae1-243">Definition</span></span>

<span data-ttu-id="cdae1-244">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="cdae1-244">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="cdae1-245">La funzione `Func_denmark_eu_ssn_or_equivalent` consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="cdae1-245">The function  `Func_denmark_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="cdae1-246">Una parola chiave da `Keywords_denmark_eu_ssn_or_equivalent` viene trovato.</span><span class="sxs-lookup"><span data-stu-id="cdae1-246">A keyword from  `Keywords_denmark_eu_ssn_or_equivalent` is found.</span></span> 
    
<span data-ttu-id="cdae1-247">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="cdae1-247">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="cdae1-248">La funzione `Func_denmark_eu_ssn_or_equivalent` consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="cdae1-248">The function  `Func_denmark_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="cdae1-249">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="cdae1-249">Keywords</span></span>

#### <a name="keywordsdenmarkeussnorequivalent"></a><span data-ttu-id="cdae1-250">Keywords_denmark_eu_ssn_or_equivalent</span><span class="sxs-lookup"><span data-stu-id="cdae1-250">Keywords_denmark_eu_ssn_or_equivalent</span></span>

<span data-ttu-id="cdae1-251">numero di identificazione personale</span><span class="sxs-lookup"><span data-stu-id="cdae1-251">personal identification number</span></span>
  
<span data-ttu-id="cdae1-252">numero identificativo nazionale</span><span class="sxs-lookup"><span data-stu-id="cdae1-252">national identification number</span></span>
  
<span data-ttu-id="cdae1-253">social security number
</span><span class="sxs-lookup"><span data-stu-id="cdae1-253">social security number</span></span>
  
<span data-ttu-id="cdae1-254">nationalnumber #</span><span class="sxs-lookup"><span data-stu-id="cdae1-254">nationalnumber#</span></span>
  
<span data-ttu-id="cdae1-255">SSN #</span><span class="sxs-lookup"><span data-stu-id="cdae1-255">ssn#</span></span>
  
<span data-ttu-id="cdae1-256">SSN</span><span class="sxs-lookup"><span data-stu-id="cdae1-256">ssn</span></span>
  
<span data-ttu-id="cdae1-257">numero nazionale</span><span class="sxs-lookup"><span data-stu-id="cdae1-257">national number</span></span>
  
<span data-ttu-id="cdae1-258">numero id personale</span><span class="sxs-lookup"><span data-stu-id="cdae1-258">personal id number</span></span>
  
<span data-ttu-id="cdae1-259">personalidnumber #</span><span class="sxs-lookup"><span data-stu-id="cdae1-259">personalidnumber#</span></span>
  
<span data-ttu-id="cdae1-260">CPR nummer</span><span class="sxs-lookup"><span data-stu-id="cdae1-260">cpr-nummer</span></span>
  
<span data-ttu-id="cdae1-261">personnummer</span><span class="sxs-lookup"><span data-stu-id="cdae1-261">personnummer</span></span>
  
## <a name="finland"></a><span data-ttu-id="cdae1-262">Finlandia</span><span class="sxs-lookup"><span data-stu-id="cdae1-262">Finland</span></span>

### <a name="format"></a><span data-ttu-id="cdae1-263">Formato</span><span class="sxs-lookup"><span data-stu-id="cdae1-263">Format</span></span>

<span data-ttu-id="cdae1-264">Una combinazione di 11 cifre nel formato specificato</span><span class="sxs-lookup"><span data-stu-id="cdae1-264">An 11-character combination in the specified format</span></span>
  
### <a name="pattern"></a><span data-ttu-id="cdae1-265">Modello</span><span class="sxs-lookup"><span data-stu-id="cdae1-265">Pattern</span></span>

<span data-ttu-id="cdae1-266">Una combinazione di 11 cifre nel formato specificato:</span><span class="sxs-lookup"><span data-stu-id="cdae1-266">An 11-character combination in the specified format:</span></span>
  
-  <span data-ttu-id="cdae1-267">Sei cifre</span><span class="sxs-lookup"><span data-stu-id="cdae1-267">Six digits</span></span> 
    
- <span data-ttu-id="cdae1-268">Un'istanza di uno dei seguenti:</span><span class="sxs-lookup"><span data-stu-id="cdae1-268">One instance of one of the following:</span></span>
    
  - <span data-ttu-id="cdae1-269">Simbolo Plus</span><span class="sxs-lookup"><span data-stu-id="cdae1-269">Plus symbol</span></span>
    
  - <span data-ttu-id="cdae1-270">Meno simbolo</span><span class="sxs-lookup"><span data-stu-id="cdae1-270">Minus symbol</span></span>
    
  - <span data-ttu-id="cdae1-271">La lettera "A" (maiuscole o minuscole)</span><span class="sxs-lookup"><span data-stu-id="cdae1-271">The letter "A" (not case-sensitive)</span></span>
    
- <span data-ttu-id="cdae1-272">Tre cifre</span><span class="sxs-lookup"><span data-stu-id="cdae1-272">Three digits</span></span>
    
- <span data-ttu-id="cdae1-273">Una lettera o una cifra</span><span class="sxs-lookup"><span data-stu-id="cdae1-273">One letter or one digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="cdae1-274">Checksum</span><span class="sxs-lookup"><span data-stu-id="cdae1-274">Checksum</span></span>

<span data-ttu-id="cdae1-275">Sì</span><span class="sxs-lookup"><span data-stu-id="cdae1-275">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="cdae1-276">Definizione</span><span class="sxs-lookup"><span data-stu-id="cdae1-276">Definition</span></span>

<span data-ttu-id="cdae1-277">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="cdae1-277">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="cdae1-278">La funzione `Func_finland_eu_ssn_or_equivalent` consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="cdae1-278">The function  `Func_finland_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="cdae1-279">Una parola chiave da `Keywords_finland_eu_ssn_or_equivalent` viene trovato.</span><span class="sxs-lookup"><span data-stu-id="cdae1-279">A keyword from  `Keywords_finland_eu_ssn_or_equivalent` is found.</span></span> 
    
<span data-ttu-id="cdae1-280">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="cdae1-280">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="cdae1-281">La funzione `Func_finland_eu_ssn_or_equivalent` consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="cdae1-281">The function  `Func_finland_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="cdae1-282">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="cdae1-282">Keywords</span></span>

#### <a name="keywordsfinlandeussnorequivalent"></a><span data-ttu-id="cdae1-283">Keywords_finland_eu_ssn_or_equivalent</span><span class="sxs-lookup"><span data-stu-id="cdae1-283">Keywords_finland_eu_ssn_or_equivalent</span></span>

<span data-ttu-id="cdae1-284">identification number
</span><span class="sxs-lookup"><span data-stu-id="cdae1-284">identification number</span></span>
  
<span data-ttu-id="cdae1-285">id personale</span><span class="sxs-lookup"><span data-stu-id="cdae1-285">personal id</span></span>
  
<span data-ttu-id="cdae1-286">numero di identità</span><span class="sxs-lookup"><span data-stu-id="cdae1-286">identity number</span></span>
  
<span data-ttu-id="cdae1-287">numero id nazionale Finlandia</span><span class="sxs-lookup"><span data-stu-id="cdae1-287">finnish national id number</span></span>
  
<span data-ttu-id="cdae1-288">personalidnumber #</span><span class="sxs-lookup"><span data-stu-id="cdae1-288">personalidnumber#</span></span>
  
<span data-ttu-id="cdae1-289">numero identificativo nazionale</span><span class="sxs-lookup"><span data-stu-id="cdae1-289">national identification number</span></span>
  
<span data-ttu-id="cdae1-290">numero ID</span><span class="sxs-lookup"><span data-stu-id="cdae1-290">id number</span></span>
  
<span data-ttu-id="cdae1-291">id nazionale non.</span><span class="sxs-lookup"><span data-stu-id="cdae1-291">national id no.</span></span>
  
<span data-ttu-id="cdae1-292">numero identificativo nazionale</span><span class="sxs-lookup"><span data-stu-id="cdae1-292">national id number</span></span>
  
<span data-ttu-id="cdae1-293">ID non</span><span class="sxs-lookup"><span data-stu-id="cdae1-293">id no</span></span>
  
<span data-ttu-id="cdae1-294">tunnistenumero</span><span class="sxs-lookup"><span data-stu-id="cdae1-294">tunnistenumero</span></span>
  
<span data-ttu-id="cdae1-295">henkilötunnus</span><span class="sxs-lookup"><span data-stu-id="cdae1-295">henkilötunnus</span></span>
  
<span data-ttu-id="cdae1-296">yksilöllinen henkilökohtainen tunnistenumero</span><span class="sxs-lookup"><span data-stu-id="cdae1-296">yksilöllinen henkilökohtainen tunnistenumero</span></span>
  
<span data-ttu-id="cdae1-297">ainutlaatuinen henkilökohtainen tunnus</span><span class="sxs-lookup"><span data-stu-id="cdae1-297">ainutlaatuinen henkilökohtainen tunnus</span></span>
  
<span data-ttu-id="cdae1-298">numero identiteetti</span><span class="sxs-lookup"><span data-stu-id="cdae1-298">identiteetti numero</span></span>
  
<span data-ttu-id="cdae1-299">suomen kansallinen henkilötunnus</span><span class="sxs-lookup"><span data-stu-id="cdae1-299">suomen kansallinen henkilötunnus</span></span>
  
<span data-ttu-id="cdae1-300">henkilötunnusnumero #</span><span class="sxs-lookup"><span data-stu-id="cdae1-300">henkilötunnusnumero#</span></span>
  
<span data-ttu-id="cdae1-301">kansallisen tunnistenumero</span><span class="sxs-lookup"><span data-stu-id="cdae1-301">kansallisen tunnistenumero</span></span>
  
<span data-ttu-id="cdae1-302">tunnusnumero</span><span class="sxs-lookup"><span data-stu-id="cdae1-302">tunnusnumero</span></span>
  
<span data-ttu-id="cdae1-303">numero di tunnus kansallinen</span><span class="sxs-lookup"><span data-stu-id="cdae1-303">kansallinen tunnus numero</span></span>
  
<span data-ttu-id="cdae1-304">hetu</span><span class="sxs-lookup"><span data-stu-id="cdae1-304">hetu</span></span>
  
## <a name="france"></a><span data-ttu-id="cdae1-305">Francia</span><span class="sxs-lookup"><span data-stu-id="cdae1-305">France</span></span>

<span data-ttu-id="cdae1-306">Per ulteriori informazioni, vedere la sezione "Francia numero di previdenza sociale (INSEE)" in [cercare il quali i tipi di informazioni riservate](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="cdae1-306">For details, see the section "France Social Security Number (INSEE)" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="germany"></a><span data-ttu-id="cdae1-307">Germania</span><span class="sxs-lookup"><span data-stu-id="cdae1-307">Germany</span></span>

<span data-ttu-id="cdae1-308">Per ulteriori informazioni, vedere la sezione "Numero di carta d'identità Germania" in [cercare il quali i tipi di informazioni riservate](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="cdae1-308">For details, see the section "Germany Identity Card Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="greece"></a><span data-ttu-id="cdae1-309">Grecia</span><span class="sxs-lookup"><span data-stu-id="cdae1-309">Greece</span></span>

<span data-ttu-id="cdae1-310">Per ulteriori informazioni, vedere la sezione "Grecia carta d'identità nazionale" in [cercare il quali i tipi di informazioni riservate](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="cdae1-310">For details, see the section "Greece National ID Card" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="hungary"></a><span data-ttu-id="cdae1-311">Ungheria</span><span class="sxs-lookup"><span data-stu-id="cdae1-311">Hungary</span></span>

### <a name="format"></a><span data-ttu-id="cdae1-312">Formato</span><span class="sxs-lookup"><span data-stu-id="cdae1-312">Format</span></span>

<span data-ttu-id="cdae1-313">Nove cifre senza spazi e i delimitatori</span><span class="sxs-lookup"><span data-stu-id="cdae1-313">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="cdae1-314">Modello</span><span class="sxs-lookup"><span data-stu-id="cdae1-314">Pattern</span></span>

<span data-ttu-id="cdae1-315">9 cifre</span><span class="sxs-lookup"><span data-stu-id="cdae1-315">Nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="cdae1-316">Checksum</span><span class="sxs-lookup"><span data-stu-id="cdae1-316">Checksum</span></span>

<span data-ttu-id="cdae1-317">Sì</span><span class="sxs-lookup"><span data-stu-id="cdae1-317">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="cdae1-318">Definizione</span><span class="sxs-lookup"><span data-stu-id="cdae1-318">Definition</span></span>

<span data-ttu-id="cdae1-319">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="cdae1-319">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="cdae1-320">La funzione `Func_hungary_eu_ssn_or_equivalent` consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="cdae1-320">The function  `Func_hungary_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="cdae1-321">Una parola chiave da `Keywords_hungary_eu_ssn_or_equivalent` viene trovato.</span><span class="sxs-lookup"><span data-stu-id="cdae1-321">A keyword from  `Keywords_hungary_eu_ssn_or_equivalent` is found.</span></span> 
    
<span data-ttu-id="cdae1-322">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="cdae1-322">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="cdae1-323">La funzione `Func_hungary_eu_ssn_or_equivalent` consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="cdae1-323">The function  `Func_hungary_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="cdae1-324">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="cdae1-324">Keywords</span></span>

#### <a name="keywordshungaryeussnorequivalent"></a><span data-ttu-id="cdae1-325">Keywords_hungary_eu_ssn_or_equivalent</span><span class="sxs-lookup"><span data-stu-id="cdae1-325">Keywords_hungary_eu_ssn_or_equivalent</span></span>

<span data-ttu-id="cdae1-326">numero di previdenza sociale ungherese</span><span class="sxs-lookup"><span data-stu-id="cdae1-326">hungarian social security number</span></span>
  
<span data-ttu-id="cdae1-327">social security number
</span><span class="sxs-lookup"><span data-stu-id="cdae1-327">social security number</span></span>
  
<span data-ttu-id="cdae1-328">SocialSecurityNumber #</span><span class="sxs-lookup"><span data-stu-id="cdae1-328">socialsecuritynumber#</span></span>
  
<span data-ttu-id="cdae1-329">hssn #</span><span class="sxs-lookup"><span data-stu-id="cdae1-329">hssn#</span></span>
  
<span data-ttu-id="cdae1-330">socialsecuritynno</span><span class="sxs-lookup"><span data-stu-id="cdae1-330">socialsecuritynno</span></span>
  
<span data-ttu-id="cdae1-331">hssn</span><span class="sxs-lookup"><span data-stu-id="cdae1-331">hssn</span></span>
  
<span data-ttu-id="cdae1-332">taj</span><span class="sxs-lookup"><span data-stu-id="cdae1-332">taj</span></span>
  
<span data-ttu-id="cdae1-333">taj #</span><span class="sxs-lookup"><span data-stu-id="cdae1-333">taj#</span></span>
  
<span data-ttu-id="cdae1-334">SSN</span><span class="sxs-lookup"><span data-stu-id="cdae1-334">ssn</span></span>
  
<span data-ttu-id="cdae1-335">SSN #</span><span class="sxs-lookup"><span data-stu-id="cdae1-335">ssn#</span></span>
  
<span data-ttu-id="cdae1-336">sicurezza sociale non</span><span class="sxs-lookup"><span data-stu-id="cdae1-336">social security no</span></span>
  
<span data-ttu-id="cdae1-337">áfa</span><span class="sxs-lookup"><span data-stu-id="cdae1-337">áfa</span></span>
  
<span data-ttu-id="cdae1-338">közösségi adószám</span><span class="sxs-lookup"><span data-stu-id="cdae1-338">közösségi adószám</span></span>
  
<span data-ttu-id="cdae1-339">általános forgalmi adó szám</span><span class="sxs-lookup"><span data-stu-id="cdae1-339">általános forgalmi adó szám</span></span>
  
<span data-ttu-id="cdae1-340">hozzáadottérték adó</span><span class="sxs-lookup"><span data-stu-id="cdae1-340">hozzáadottérték adó</span></span>
  
<span data-ttu-id="cdae1-341">áfa szám</span><span class="sxs-lookup"><span data-stu-id="cdae1-341">áfa szám</span></span>
  
<span data-ttu-id="cdae1-342">áfa magyar szám</span><span class="sxs-lookup"><span data-stu-id="cdae1-342">magyar áfa szám</span></span>
  
## <a name="portugal"></a><span data-ttu-id="cdae1-343">Portogallo</span><span class="sxs-lookup"><span data-stu-id="cdae1-343">Portugal</span></span>

<span data-ttu-id="cdae1-344">Per ulteriori informazioni, vedere la sezione "Portogallo cittadini scheda numero" in [cercare il quali i tipi di informazioni riservate](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="cdae1-344">For details, see the section "Portugal Citizen Card Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="spain"></a><span data-ttu-id="cdae1-345">Spagna</span><span class="sxs-lookup"><span data-stu-id="cdae1-345">Spain</span></span>

<span data-ttu-id="cdae1-346">Per ulteriori informazioni, vedere la sezione "Spagna numero di previdenza sociale (SSN)" in [cercare il quali i tipi di informazioni riservate](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="cdae1-346">For details, see the section "Spain Social Security Number (SSN)" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="sweden"></a><span data-ttu-id="cdae1-347">Svezia</span><span class="sxs-lookup"><span data-stu-id="cdae1-347">Sweden</span></span>

### <a name="format"></a><span data-ttu-id="cdae1-348">Formato</span><span class="sxs-lookup"><span data-stu-id="cdae1-348">Format</span></span>

<span data-ttu-id="cdae1-349">12 cifre senza spazi e i delimitatori</span><span class="sxs-lookup"><span data-stu-id="cdae1-349">12 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="cdae1-350">Modello</span><span class="sxs-lookup"><span data-stu-id="cdae1-350">Pattern</span></span>

<span data-ttu-id="cdae1-351">12 cifre:</span><span class="sxs-lookup"><span data-stu-id="cdae1-351">12 digits:</span></span>
  
-  <span data-ttu-id="cdae1-352">Otto cifre che corrispondono alla data di nascita (AAAAMMGGG)</span><span class="sxs-lookup"><span data-stu-id="cdae1-352">Eight digits that correspond to the birth date (YYYYMMDD)</span></span> 
    
- <span data-ttu-id="cdae1-353">Tre cifre che corrispondono a un numero di serie dove:</span><span class="sxs-lookup"><span data-stu-id="cdae1-353">Three digits that correspond to a serial number where:</span></span> 
    
  - <span data-ttu-id="cdae1-354">L'ultima cifra del numero di serie indica sesso per l'assegnazione di un numero dispari di maschile e un numero pari di femmina</span><span class="sxs-lookup"><span data-stu-id="cdae1-354">The last digit in the serial number indicates gender by the assignment of an odd number for male and an even number for female</span></span>
    
  - <span data-ttu-id="cdae1-355">Fino a 1990, l'assegnazione del numero di serie corrispondeva alla provincia in cui portanti del numero di nascita o (se nati prima 1947) cui ha effettuato con stato vive, in base ai record di imposta su 1 gennaio 1947, con un codice speciale (in genere 9 come 7 cifre) per immigranti</span><span class="sxs-lookup"><span data-stu-id="cdae1-355">Up to 1990, the assignment of serial number corresponded to the county where the bearer of the number was born or (if born before 1947) where he/she had been living, according to tax records, on January 1, 1947, with a special code (usually 9 as the 7th digit) for immigrants</span></span> 
    
- <span data-ttu-id="cdae1-356">Cifra di un controllo</span><span class="sxs-lookup"><span data-stu-id="cdae1-356">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="cdae1-357">Checksum</span><span class="sxs-lookup"><span data-stu-id="cdae1-357">Checksum</span></span>

<span data-ttu-id="cdae1-358">Sì</span><span class="sxs-lookup"><span data-stu-id="cdae1-358">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="cdae1-359">Definizione</span><span class="sxs-lookup"><span data-stu-id="cdae1-359">Definition</span></span>

<span data-ttu-id="cdae1-360">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="cdae1-360">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="cdae1-361">La funzione `Func_sweden_eu_ssn_or_equivalent` consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="cdae1-361">The function  `Func_sweden_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="cdae1-362">Una parola chiave da `Keywords_sweden_eu_ssn_or_equivalent` viene trovato.</span><span class="sxs-lookup"><span data-stu-id="cdae1-362">A keyword from  `Keywords_sweden_eu_ssn_or_equivalent` is found.</span></span> 
    
<span data-ttu-id="cdae1-363">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="cdae1-363">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="cdae1-364">La funzione `Func_sweden_eu_ssn_or_equivalent` consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="cdae1-364">The function  `Func_sweden_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="cdae1-365">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="cdae1-365">Keywords</span></span>

#### <a name="keywordsswedeneussnorequivalent"></a><span data-ttu-id="cdae1-366">Keywords_sweden_eu_ssn_or_equivalent</span><span class="sxs-lookup"><span data-stu-id="cdae1-366">Keywords_sweden_eu_ssn_or_equivalent</span></span>

<span data-ttu-id="cdae1-367">numero id personale</span><span class="sxs-lookup"><span data-stu-id="cdae1-367">personal id number</span></span>
  
<span data-ttu-id="cdae1-368">identification number
</span><span class="sxs-lookup"><span data-stu-id="cdae1-368">identification number</span></span>
  
<span data-ttu-id="cdae1-369">id personale non</span><span class="sxs-lookup"><span data-stu-id="cdae1-369">personal id no</span></span>
  
<span data-ttu-id="cdae1-370">identità non</span><span class="sxs-lookup"><span data-stu-id="cdae1-370">identity no</span></span>
  
<span data-ttu-id="cdae1-371">identificazione non</span><span class="sxs-lookup"><span data-stu-id="cdae1-371">identification no</span></span>
  
<span data-ttu-id="cdae1-372">identificazione personale non</span><span class="sxs-lookup"><span data-stu-id="cdae1-372">personal identification no</span></span>
  
<span data-ttu-id="cdae1-373">id personnummer</span><span class="sxs-lookup"><span data-stu-id="cdae1-373">personnummer id</span></span>
  
<span data-ttu-id="cdae1-374">id personligt-nummer</span><span class="sxs-lookup"><span data-stu-id="cdae1-374">personligt id-nummer</span></span>
  
<span data-ttu-id="cdae1-375">id unikt-nummer</span><span class="sxs-lookup"><span data-stu-id="cdae1-375">unikt id-nummer</span></span>
  
<span data-ttu-id="cdae1-376">personnummer</span><span class="sxs-lookup"><span data-stu-id="cdae1-376">personnummer</span></span>
  
<span data-ttu-id="cdae1-377">identifikationsnumret</span><span class="sxs-lookup"><span data-stu-id="cdae1-377">identifikationsnumret</span></span>
  
<span data-ttu-id="cdae1-378">personnummer #</span><span class="sxs-lookup"><span data-stu-id="cdae1-378">personnummer#</span></span>
  
<span data-ttu-id="cdae1-379">identifikationsnumret #</span><span class="sxs-lookup"><span data-stu-id="cdae1-379">identifikationsnumret#</span></span>
  
## <a name="see-also"></a><span data-ttu-id="cdae1-380">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cdae1-380">See also</span></span>

[<span data-ttu-id="cdae1-381">Cosa individuano i tipi di informazioni riservate</span><span class="sxs-lookup"><span data-stu-id="cdae1-381">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)

