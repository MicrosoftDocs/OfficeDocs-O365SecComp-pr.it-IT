---
title: Numero di identificazione dell'Unione europea nazionale
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 8/17/2018
ms.audience: Admin
ms.topic: reference
ms.service: o365-administration
localization_priority: Normal
ms.assetid: 2ea971bf-9434-4b61-b825-2bbd28ae6064
description: Questo argomento viene illustrato quali un criterio di criterio DLP perdita di dati Cerca qualora venga rilevato un tipo di informazione sensibile numero identificativo nazionale dell'Unione europea. Questo tipo di informazioni riservate definisce le diverse combinazioni, parole chiave e altri elementi di prova per ogni paese.
ms.openlocfilehash: 29d2126b937ff46039284a74eb2a84f2ebbacb41
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/27/2018
ms.locfileid: "22530741"
---
# <a name="eu-national-identification-number"></a><span data-ttu-id="2d230-104">Numero di identificazione dell'Unione europea nazionale</span><span class="sxs-lookup"><span data-stu-id="2d230-104">EU National Identification Number</span></span>

<span data-ttu-id="2d230-p102">Questo argomento viene illustrato quali un criterio di criterio DLP perdita di dati Cerca qualora venga rilevato un tipo di informazione sensibile numero identificativo nazionale dell'Unione europea. Questo tipo di informazioni riservate definisce le diverse combinazioni, parole chiave e altri elementi di prova per ogni paese.</span><span class="sxs-lookup"><span data-stu-id="2d230-p102">This topic shows what a data loss prevention (DLP) policy looks for when it detects the EU National Identification Number sensitive information type. This sensitive information type defines different patterns, keywords, and other evidence for each country.</span></span>
  
## <a name="austria"></a><span data-ttu-id="2d230-107">Austria</span><span class="sxs-lookup"><span data-stu-id="2d230-107">Austria</span></span>

### <a name="format"></a><span data-ttu-id="2d230-108">Formato</span><span class="sxs-lookup"><span data-stu-id="2d230-108">Format</span></span>

<span data-ttu-id="2d230-109">Una combinazione di lettere, cifre e caratteri speciali 24</span><span class="sxs-lookup"><span data-stu-id="2d230-109">A 24-character combination of letters, digits, and special characters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="2d230-110">Modello</span><span class="sxs-lookup"><span data-stu-id="2d230-110">Pattern</span></span>

<span data-ttu-id="2d230-111">24 caratteri:</span><span class="sxs-lookup"><span data-stu-id="2d230-111">24 characters:</span></span>
  
-  <span data-ttu-id="2d230-112">22 lettere (maiuscole o minuscole), cifre, barre rovesciate, barre o segni più</span><span class="sxs-lookup"><span data-stu-id="2d230-112">22 letters (not case-sensitive), digits, backslashes, forward slashes, or plus signs</span></span> 
    
- <span data-ttu-id="2d230-113">Due lettere (maiuscole o minuscole), cifre, barre rovesciate, barre, segni più o segni di uguale</span><span class="sxs-lookup"><span data-stu-id="2d230-113">Two letters (not case-sensitive), digits, backslashes, forward slashes, plus signs, or equal signs</span></span>
    
### <a name="checksum"></a><span data-ttu-id="2d230-114">Checksum</span><span class="sxs-lookup"><span data-stu-id="2d230-114">Checksum</span></span>

<span data-ttu-id="2d230-115">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="2d230-115">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="2d230-116">Definizione</span><span class="sxs-lookup"><span data-stu-id="2d230-116">Definition</span></span>

<span data-ttu-id="2d230-117">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="2d230-117">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="2d230-118">L'espressione regolare `Regex_austria_eu_national_id_card` consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="2d230-118">The regular expression  `Regex_austria_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="2d230-119">Una parola chiave da `Keywords_austria_eu_national_id_card` viene trovato.</span><span class="sxs-lookup"><span data-stu-id="2d230-119">A keyword from  `Keywords_austria_eu_national_id_card` is found.</span></span> 
    
```
 
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_austria_eu_national_id_card" />
          <Match idRef="Keywords_austria_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="2d230-120">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="2d230-120">Keywords</span></span>

#### <a name="keywordsaustriaeunationalidcard"></a><span data-ttu-id="2d230-121">Keywords_austria_eu_national_id_card</span><span class="sxs-lookup"><span data-stu-id="2d230-121">Keywords_austria_eu_national_id_card</span></span>

<span data-ttu-id="2d230-122">numero di identificazione austriaco</span><span class="sxs-lookup"><span data-stu-id="2d230-122">austrian identity number</span></span>
  
<span data-ttu-id="2d230-123">numero di identità nazionale</span><span class="sxs-lookup"><span data-stu-id="2d230-123">national identity number</span></span>
  
<span data-ttu-id="2d230-124">numero di identità</span><span class="sxs-lookup"><span data-stu-id="2d230-124">identity number</span></span>
  
<span data-ttu-id="2d230-125">
national id</span><span class="sxs-lookup"><span data-stu-id="2d230-125">national id</span></span>
  
<span data-ttu-id="2d230-126">personalausweis italiana österreich</span><span class="sxs-lookup"><span data-stu-id="2d230-126">personalausweis republik österreich</span></span>
  
## <a name="belgium"></a><span data-ttu-id="2d230-127">Belgio</span><span class="sxs-lookup"><span data-stu-id="2d230-127">Belgium</span></span>

<span data-ttu-id="2d230-128">Per ulteriori informazioni, vedere la sezione "Belgio nazionale Number" in [cercare il quali i tipi di informazioni riservate](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="2d230-128">For details, see the section "Belgium National Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="bulgaria"></a><span data-ttu-id="2d230-129">Bulgaria</span><span class="sxs-lookup"><span data-stu-id="2d230-129">Bulgaria</span></span>

### <a name="format"></a><span data-ttu-id="2d230-130">Formato</span><span class="sxs-lookup"><span data-stu-id="2d230-130">Format</span></span>

<span data-ttu-id="2d230-131">Dieci cifre senza spazi e i delimitatori</span><span class="sxs-lookup"><span data-stu-id="2d230-131">Ten digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="2d230-132">Modello</span><span class="sxs-lookup"><span data-stu-id="2d230-132">Pattern</span></span>

<span data-ttu-id="2d230-133">Dieci cifre senza spazi e i delimitatori</span><span class="sxs-lookup"><span data-stu-id="2d230-133">Ten digits without spaces and delimiters</span></span>
  
-  <span data-ttu-id="2d230-134">Sei cifre che corrispondono alla data di nascita (AAMMGG)</span><span class="sxs-lookup"><span data-stu-id="2d230-134">Six digits that correspond to the birth date (YYMMDD)</span></span> 
    
- <span data-ttu-id="2d230-135">Due cifre che corrispondano all'ordine di nascita</span><span class="sxs-lookup"><span data-stu-id="2d230-135">Two digits that correspond to the birth order</span></span>
    
- <span data-ttu-id="2d230-136">Una cifra che corrisponde al sesso: un numero pari di maschile e una cifra dispari per femmina</span><span class="sxs-lookup"><span data-stu-id="2d230-136">One digit that corresponds to gender: An even digit for male and an odd digit for female</span></span>
    
- <span data-ttu-id="2d230-137">Cifra di un controllo</span><span class="sxs-lookup"><span data-stu-id="2d230-137">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="2d230-138">Checksum</span><span class="sxs-lookup"><span data-stu-id="2d230-138">Checksum</span></span>

<span data-ttu-id="2d230-139">Sì</span><span class="sxs-lookup"><span data-stu-id="2d230-139">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="2d230-140">Definizione</span><span class="sxs-lookup"><span data-stu-id="2d230-140">Definition</span></span>

<span data-ttu-id="2d230-141">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="2d230-141">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="2d230-142">La funzione `Func_bulgaria_national_number` consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="2d230-142">The function  `Func_bulgaria_national_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="2d230-143">Una parola chiave da `Keywords_bulgaria_national_number` viene trovato.</span><span class="sxs-lookup"><span data-stu-id="2d230-143">A keyword from  `Keywords_bulgaria_national_number` is found.</span></span> 
    
<span data-ttu-id="2d230-144">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="2d230-144">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="2d230-145">La funzione `Func_bulgaria_national_number` consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="2d230-145">The function  `Func_bulgaria_national_number` finds content that matches the pattern.</span></span> 
    
```
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_bulgaria_national_number" />
          <Match idRef="Keywords_bulgaria_national_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_bulgaria_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="2d230-146">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="2d230-146">Keywords</span></span>

#### <a name="keywordsbulgarianationalnumber"></a><span data-ttu-id="2d230-147">Keywords_bulgaria_national_number</span><span class="sxs-lookup"><span data-stu-id="2d230-147">Keywords_bulgaria_national_number</span></span>

<span data-ttu-id="2d230-148">egn</span><span class="sxs-lookup"><span data-stu-id="2d230-148">egn</span></span>
  
<span data-ttu-id="2d230-149">egn #</span><span class="sxs-lookup"><span data-stu-id="2d230-149">egn#</span></span>
  
<span data-ttu-id="2d230-150">Bulgaro numero nazionale</span><span class="sxs-lookup"><span data-stu-id="2d230-150">bulgarian national number</span></span>
  
<span data-ttu-id="2d230-151">numero nazionale</span><span class="sxs-lookup"><span data-stu-id="2d230-151">national number</span></span>
  
<span data-ttu-id="2d230-152">social security number
</span><span class="sxs-lookup"><span data-stu-id="2d230-152">social security number</span></span>
  
<span data-ttu-id="2d230-153">nationalnumber #</span><span class="sxs-lookup"><span data-stu-id="2d230-153">nationalnumber#</span></span>
  
<span data-ttu-id="2d230-154">SSN #</span><span class="sxs-lookup"><span data-stu-id="2d230-154">ssn#</span></span>
  
<span data-ttu-id="2d230-155">SSN</span><span class="sxs-lookup"><span data-stu-id="2d230-155">ssn</span></span>
  
<span data-ttu-id="2d230-156">nationalnumber</span><span class="sxs-lookup"><span data-stu-id="2d230-156">nationalnumber</span></span>
  
<span data-ttu-id="2d230-157">bnn #</span><span class="sxs-lookup"><span data-stu-id="2d230-157">bnn#</span></span>
  
<span data-ttu-id="2d230-158">bnn</span><span class="sxs-lookup"><span data-stu-id="2d230-158">bnn</span></span>
  
<span data-ttu-id="2d230-159">numero id personale</span><span class="sxs-lookup"><span data-stu-id="2d230-159">personal id number</span></span>
  
<span data-ttu-id="2d230-160">personalidnumber #</span><span class="sxs-lookup"><span data-stu-id="2d230-160">personalidnumber#</span></span>
  
<span data-ttu-id="2d230-161">ЕДИНЕН ГРАЖДАНСКИ НОМЕР</span><span class="sxs-lookup"><span data-stu-id="2d230-161">единен граждански номер</span></span>
  
<span data-ttu-id="2d230-162">edinen grazhdanski nomer</span><span class="sxs-lookup"><span data-stu-id="2d230-162">edinen grazhdanski nomer</span></span>
  
<span data-ttu-id="2d230-163">ЕГН</span><span class="sxs-lookup"><span data-stu-id="2d230-163">егн</span></span>
  
<span data-ttu-id="2d230-164">ЕГН #</span><span class="sxs-lookup"><span data-stu-id="2d230-164">егн#</span></span>
  
## <a name="croatia"></a><span data-ttu-id="2d230-165">Croazia</span><span class="sxs-lookup"><span data-stu-id="2d230-165">Croatia</span></span>

<span data-ttu-id="2d230-166">Per ulteriori informazioni, vedere la sezione "Croazia identità Number" in [cercare il quali i tipi di informazioni riservate](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="2d230-166">For details, see the section "Croatia Identity Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="cyprus"></a><span data-ttu-id="2d230-167">Cipro</span><span class="sxs-lookup"><span data-stu-id="2d230-167">Cyprus</span></span>

### <a name="format"></a><span data-ttu-id="2d230-168">Formato</span><span class="sxs-lookup"><span data-stu-id="2d230-168">Format</span></span>

<span data-ttu-id="2d230-169">Dieci cifre senza spazi e i delimitatori</span><span class="sxs-lookup"><span data-stu-id="2d230-169">Ten digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="2d230-170">Modello</span><span class="sxs-lookup"><span data-stu-id="2d230-170">Pattern</span></span>

 <span data-ttu-id="2d230-171">Dieci cifre</span><span class="sxs-lookup"><span data-stu-id="2d230-171">Ten digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="2d230-172">Checksum</span><span class="sxs-lookup"><span data-stu-id="2d230-172">Checksum</span></span>

<span data-ttu-id="2d230-173">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="2d230-173">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="2d230-174">Definizione</span><span class="sxs-lookup"><span data-stu-id="2d230-174">Definition</span></span>

<span data-ttu-id="2d230-175">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="2d230-175">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="2d230-176">L'espressione regolare `Regex_cyprus_eu_national_id_card` consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="2d230-176">The regular expression  `Regex_cyprus_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="2d230-177">Una parola chiave da `Keywords_cyprus_eu_national_id_card` viene trovato.</span><span class="sxs-lookup"><span data-stu-id="2d230-177">A keyword from  `Keywords_cyprus_eu_national_id_card` is found.</span></span> 
    
```
 
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_cyprus_eu_national_id_card" />
          <Match idRef="Keywords_cyprus_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="2d230-178">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="2d230-178">Keywords</span></span>

#### <a name="keywordscypruseunationalidcard"></a><span data-ttu-id="2d230-179">Keywords_cyprus_eu_national_id_card</span><span class="sxs-lookup"><span data-stu-id="2d230-179">Keywords_cyprus_eu_national_id_card</span></span>

<span data-ttu-id="2d230-180">numero di carta d'identità</span><span class="sxs-lookup"><span data-stu-id="2d230-180">id card number</span></span>
  
<span data-ttu-id="2d230-181">numero identificativo nazionale</span><span class="sxs-lookup"><span data-stu-id="2d230-181">national identification number</span></span>
  
<span data-ttu-id="2d230-182">numero id personale</span><span class="sxs-lookup"><span data-stu-id="2d230-182">personal id number</span></span>
  
<span data-ttu-id="2d230-183">numero di carta d'identità</span><span class="sxs-lookup"><span data-stu-id="2d230-183">identity card number</span></span>
  
<span data-ttu-id="2d230-184">ΤΑΥΤΟΤΗΤΑΣ</span><span class="sxs-lookup"><span data-stu-id="2d230-184">ταυτοτητασ</span></span>
  
## <a name="czech-republic"></a><span data-ttu-id="2d230-185">Repubblica Ceca</span><span class="sxs-lookup"><span data-stu-id="2d230-185">Czech Republic</span></span>

<span data-ttu-id="2d230-186">Per ulteriori informazioni, vedere la sezione "Numero identità nazionale ceco" in [cercare il quali i tipi di informazioni riservate](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="2d230-186">For details, see the section "Czech National Identity Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="denmark"></a><span data-ttu-id="2d230-187">Danimarca</span><span class="sxs-lookup"><span data-stu-id="2d230-187">Denmark</span></span>

<span data-ttu-id="2d230-188">Per ulteriori informazioni, vedere la sezione "Danimarca Personal Identification Number" in [cercare il quali i tipi di informazioni riservate](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="2d230-188">For details, see the section "Denmark Personal Identification Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="estonia"></a><span data-ttu-id="2d230-189">Estonia</span><span class="sxs-lookup"><span data-stu-id="2d230-189">Estonia</span></span>

### <a name="format"></a><span data-ttu-id="2d230-190">Formato</span><span class="sxs-lookup"><span data-stu-id="2d230-190">Format</span></span>

<span data-ttu-id="2d230-191">11 cifre senza spazi e i delimitatori</span><span class="sxs-lookup"><span data-stu-id="2d230-191">11 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="2d230-192">Modello</span><span class="sxs-lookup"><span data-stu-id="2d230-192">Pattern</span></span>

<span data-ttu-id="2d230-193">11 cifre:</span><span class="sxs-lookup"><span data-stu-id="2d230-193">11 digits:</span></span>
  
- <span data-ttu-id="2d230-194">Una cifra che corrisponde al sesso e century di nascita (maschile numero dispari, numero pari femmina; 1-2: 19 century; 3 e 4: 20 century; 5-6: century ventunesimo)</span><span class="sxs-lookup"><span data-stu-id="2d230-194">One digit that corresponds to sex and century of birth (odd number male, even number female; 1-2: 19th century; 3-4: 20th century; 5-6: 21st century)</span></span>
    
- <span data-ttu-id="2d230-195">Sei cifre che corrispondono alla data di nascita (AAMMGG)</span><span class="sxs-lookup"><span data-stu-id="2d230-195">Six digits that correspond to date of birth (YYMMDD)</span></span>
    
- <span data-ttu-id="2d230-196">Tre cifre che corrispondono a un numero di serie che separa le persone nati nella stessa data</span><span class="sxs-lookup"><span data-stu-id="2d230-196">Three digits that correspond to a serial number separating persons born on the same date</span></span>
    
- <span data-ttu-id="2d230-197">Cifra di un controllo</span><span class="sxs-lookup"><span data-stu-id="2d230-197">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="2d230-198">Checksum</span><span class="sxs-lookup"><span data-stu-id="2d230-198">Checksum</span></span>

<span data-ttu-id="2d230-199">Sì</span><span class="sxs-lookup"><span data-stu-id="2d230-199">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="2d230-200">Definizione</span><span class="sxs-lookup"><span data-stu-id="2d230-200">Definition</span></span>

<span data-ttu-id="2d230-201">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="2d230-201">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="2d230-202">La funzione `Func_estonia_eu_national_id_card` consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="2d230-202">The function  `Func_estonia_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="2d230-203">Una parola chiave da `Keywords_estonia_eu_national_id_card` viene trovato.</span><span class="sxs-lookup"><span data-stu-id="2d230-203">A keyword from  `Keywords_estonia_eu_national_id_card` is found.</span></span> 
    
<span data-ttu-id="2d230-204">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="2d230-204">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="2d230-205">La funzione `Func_estonia_eu_national_id_card` consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="2d230-205">The function  `Func_estonia_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
```
 
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_estonia_eu_national_id_card" />
          <Match idRef="Keywords_estonia_eu_national_id_card" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_estonia_eu_national_id_card" />
</Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="2d230-206">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="2d230-206">Keywords</span></span>

#### <a name="keywordsestoniaeunationalidcard"></a><span data-ttu-id="2d230-207">Keywords_estonia_eu_national_id_card</span><span class="sxs-lookup"><span data-stu-id="2d230-207">Keywords_estonia_eu_national_id_card</span></span>

<span data-ttu-id="2d230-208">codice di identificazione personale</span><span class="sxs-lookup"><span data-stu-id="2d230-208">personal identification code</span></span>
  
<span data-ttu-id="2d230-209">numero di identificazione personale</span><span class="sxs-lookup"><span data-stu-id="2d230-209">personal identification number</span></span>
  
<span data-ttu-id="2d230-210">numero identificativo nazionale</span><span class="sxs-lookup"><span data-stu-id="2d230-210">national identification number</span></span>
  
<span data-ttu-id="2d230-211">numero nazionale</span><span class="sxs-lookup"><span data-stu-id="2d230-211">national number</span></span>
  
<span data-ttu-id="2d230-212">numero id personale</span><span class="sxs-lookup"><span data-stu-id="2d230-212">personal id number</span></span>
  
<span data-ttu-id="2d230-213">personalidnumber #</span><span class="sxs-lookup"><span data-stu-id="2d230-213">personalidnumber#</span></span>
  
<span data-ttu-id="2d230-214">IK</span><span class="sxs-lookup"><span data-stu-id="2d230-214">ik</span></span>
  
<span data-ttu-id="2d230-215">isikukood</span><span class="sxs-lookup"><span data-stu-id="2d230-215">isikukood</span></span>
  
<span data-ttu-id="2d230-216">ID kaart</span><span class="sxs-lookup"><span data-stu-id="2d230-216">id-kaart</span></span>
  
## <a name="finland"></a><span data-ttu-id="2d230-217">Finlandia</span><span class="sxs-lookup"><span data-stu-id="2d230-217">Finland</span></span>

<span data-ttu-id="2d230-218">Per ulteriori informazioni, vedere la sezione "ID nazionale Finlandia" in [cercare il quali i tipi di informazioni riservate](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="2d230-218">For details, see the section "Finland National ID" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="france"></a><span data-ttu-id="2d230-219">Francia</span><span class="sxs-lookup"><span data-stu-id="2d230-219">France</span></span>

<span data-ttu-id="2d230-220">Per ulteriori informazioni, vedere la sezione "Francia nazionale carta d'identità (CNI)" in [cercare il quali i tipi di informazioni riservate](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="2d230-220">For details, see the section "France National ID Card (CNI)" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="germany"></a><span data-ttu-id="2d230-221">Germania</span><span class="sxs-lookup"><span data-stu-id="2d230-221">Germany</span></span>

<span data-ttu-id="2d230-222">Per ulteriori informazioni, vedere la sezione "Numero di carta d'identità Germania" in [cercare il quali i tipi di informazioni riservate](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="2d230-222">For details, see the section "Germany Identity Card Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="greece"></a><span data-ttu-id="2d230-223">Grecia</span><span class="sxs-lookup"><span data-stu-id="2d230-223">Greece</span></span>

<span data-ttu-id="2d230-224">Per ulteriori informazioni, vedere la sezione "Grecia carta d'identità nazionale" in [cercare il quali i tipi di informazioni riservate](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="2d230-224">For details, see the section "Greece National ID Card" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="hungary"></a><span data-ttu-id="2d230-225">Ungheria</span><span class="sxs-lookup"><span data-stu-id="2d230-225">Hungary</span></span>

### <a name="format"></a><span data-ttu-id="2d230-226">Formato</span><span class="sxs-lookup"><span data-stu-id="2d230-226">Format</span></span>

<span data-ttu-id="2d230-227">11 cifre</span><span class="sxs-lookup"><span data-stu-id="2d230-227">11 digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="2d230-228">Modello</span><span class="sxs-lookup"><span data-stu-id="2d230-228">Pattern</span></span>

<span data-ttu-id="2d230-229">11 cifre:</span><span class="sxs-lookup"><span data-stu-id="2d230-229">11 digits:</span></span>
  
-  <span data-ttu-id="2d230-230">Una cifra che corrisponde al sesso (maschile 1, 2 femmina, altri numeri sono inoltre disponibili per i cittadini nati prima di 1900 o cittadini con cittadinanza double)</span><span class="sxs-lookup"><span data-stu-id="2d230-230">One digit that corresponds to gender (1-male, 2-female, other numbers are also possible for citizens born before 1900 or citizens with double citizenship)</span></span> 
    
- <span data-ttu-id="2d230-231">Sei cifre che corrispondono alla data di nascita (AAMMGG)</span><span class="sxs-lookup"><span data-stu-id="2d230-231">Six digits that correspond to birth date (YYMMDD)</span></span>
    
- <span data-ttu-id="2d230-232">Tre cifre che corrispondono a un numero di serie</span><span class="sxs-lookup"><span data-stu-id="2d230-232">Three digits that correspond to a serial number</span></span>
    
- <span data-ttu-id="2d230-233">Cifra di un controllo</span><span class="sxs-lookup"><span data-stu-id="2d230-233">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="2d230-234">Checksum</span><span class="sxs-lookup"><span data-stu-id="2d230-234">Checksum</span></span>

<span data-ttu-id="2d230-235">Sì</span><span class="sxs-lookup"><span data-stu-id="2d230-235">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="2d230-236">Definizione</span><span class="sxs-lookup"><span data-stu-id="2d230-236">Definition</span></span>

<span data-ttu-id="2d230-237">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="2d230-237">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="2d230-238">La funzione `Func_hungary_eu_national_id_card` consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="2d230-238">The function  `Func_hungary_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="2d230-239">Una parola chiave da `Keywords_hungary_eu_national_id_card` viene trovato.</span><span class="sxs-lookup"><span data-stu-id="2d230-239">A keyword from  `Keywords_hungary_eu_national_id_card` is found.</span></span> 
    
<span data-ttu-id="2d230-240">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="2d230-240">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="2d230-241">La funzione `Func_hungary_eu_national_id_card` consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="2d230-241">The function  `Func_hungary_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
```
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_hungary_eu_national_id_card" />
          <Match idRef="Keywords_hungary_eu_national_id_card" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_hungary_eu_national_id_card" />
</Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="2d230-242">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="2d230-242">Keywords</span></span>

#### <a name="keywordshungaryeunationalidcard"></a><span data-ttu-id="2d230-243">Keywords_hungary_eu_national_id_card</span><span class="sxs-lookup"><span data-stu-id="2d230-243">Keywords_hungary_eu_national_id_card</span></span>

<span data-ttu-id="2d230-244">numero di identificazione personale</span><span class="sxs-lookup"><span data-stu-id="2d230-244">personal identification number</span></span>
  
<span data-ttu-id="2d230-245">identification number
</span><span class="sxs-lookup"><span data-stu-id="2d230-245">identification number</span></span>
  
<span data-ttu-id="2d230-246">numero id personale</span><span class="sxs-lookup"><span data-stu-id="2d230-246">personal id number</span></span>
  
<span data-ttu-id="2d230-247">személyazonosító igazolvány</span><span class="sxs-lookup"><span data-stu-id="2d230-247">személyazonosító igazolvány</span></span>
  
## <a name="ireland"></a><span data-ttu-id="2d230-248">Irlanda</span><span class="sxs-lookup"><span data-stu-id="2d230-248">Ireland</span></span>

### <a name="format"></a><span data-ttu-id="2d230-249">Formato</span><span class="sxs-lookup"><span data-stu-id="2d230-249">Format</span></span>

<span data-ttu-id="2d230-250">Una combinazione di nove caratteri di lettere, cifre e uno spazio nel modello specificato</span><span class="sxs-lookup"><span data-stu-id="2d230-250">A nine-character combination of letters, digits, and a space in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="2d230-251">Modello</span><span class="sxs-lookup"><span data-stu-id="2d230-251">Pattern</span></span>

<span data-ttu-id="2d230-252">Una combinazione di nove caratteri di lettere, cifre e uno spazio nel modello specificato</span><span class="sxs-lookup"><span data-stu-id="2d230-252">A nine-character combination of letters, digits, and a space in the specified pattern</span></span>
  
<span data-ttu-id="2d230-253">Dal 01 gennaio 2013 per il momento:</span><span class="sxs-lookup"><span data-stu-id="2d230-253">From 01 January 2013 to now:</span></span>
  
-  <span data-ttu-id="2d230-254">Sette cifre</span><span class="sxs-lookup"><span data-stu-id="2d230-254">Seven digits</span></span> 
    
- <span data-ttu-id="2d230-255">Cifra di un controllo</span><span class="sxs-lookup"><span data-stu-id="2d230-255">One check digit</span></span>
    
- <span data-ttu-id="2d230-256">Uno spazio o la lettera maiuscola "W" (distinzione tra maiuscole e minuscole)</span><span class="sxs-lookup"><span data-stu-id="2d230-256">One space or the uppercase letter "W" (Case sensitive)</span></span>
    
<span data-ttu-id="2d230-257">Prima di 01 gennaio 2013:</span><span class="sxs-lookup"><span data-stu-id="2d230-257">Prior to 01 January 2013:</span></span>
  
-  <span data-ttu-id="2d230-258">Sette cifre</span><span class="sxs-lookup"><span data-stu-id="2d230-258">Seven digits</span></span> 
    
- <span data-ttu-id="2d230-259">Cifra di un controllo</span><span class="sxs-lookup"><span data-stu-id="2d230-259">One check digit</span></span>
    
- <span data-ttu-id="2d230-260">Uno spazio o una lettera maiuscola (maiuscole/minuscole)</span><span class="sxs-lookup"><span data-stu-id="2d230-260">One space or an uppercase letter (Case sensitive)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="2d230-261">Checksum</span><span class="sxs-lookup"><span data-stu-id="2d230-261">Checksum</span></span>

<span data-ttu-id="2d230-262">Sì</span><span class="sxs-lookup"><span data-stu-id="2d230-262">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="2d230-263">Definizione</span><span class="sxs-lookup"><span data-stu-id="2d230-263">Definition</span></span>

<span data-ttu-id="2d230-264">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="2d230-264">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="2d230-265">La funzione Trova contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="2d230-265">The function finds content that matches the pattern.</span></span>
    
- <span data-ttu-id="2d230-266">È possibile trovare una parola chiave da.</span><span class="sxs-lookup"><span data-stu-id="2d230-266">A keyword from is found.</span></span>
    
<span data-ttu-id="2d230-267">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="2d230-267">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="2d230-268">La funzione Trova contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="2d230-268">The function finds content that matches the pattern.</span></span>
    
```
 
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_ireland_eu_national_id_card" />
          <Match idRef="Keywords_ireland_eu_national_id_card" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_ireland_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="2d230-269">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="2d230-269">Keywords</span></span>

#### <a name="keywordsirelandeunationalidcard"></a><span data-ttu-id="2d230-270">Keywords_ireland_eu_national_id_card</span><span class="sxs-lookup"><span data-stu-id="2d230-270">Keywords_ireland_eu_national_id_card</span></span>

<span data-ttu-id="2d230-271">numero di servizio della pubblica personali</span><span class="sxs-lookup"><span data-stu-id="2d230-271">personal public service number</span></span>
  
<span data-ttu-id="2d230-272">PPS non</span><span class="sxs-lookup"><span data-stu-id="2d230-272">pps no</span></span>
  
<span data-ttu-id="2d230-273">numero di assicurazione sociale e dei ricavi</span><span class="sxs-lookup"><span data-stu-id="2d230-273">revenue and social insurance number</span></span>
  
<span data-ttu-id="2d230-274">RSI non</span><span class="sxs-lookup"><span data-stu-id="2d230-274">rsi no</span></span>
  
<span data-ttu-id="2d230-275">numero di identificazione personale</span><span class="sxs-lookup"><span data-stu-id="2d230-275">personal identification number</span></span>
  
<span data-ttu-id="2d230-276">identification number
</span><span class="sxs-lookup"><span data-stu-id="2d230-276">identification number</span></span>
  
<span data-ttu-id="2d230-277">numero id personale</span><span class="sxs-lookup"><span data-stu-id="2d230-277">personal id number</span></span>
  
<span data-ttu-id="2d230-278">uimhir phearsanta seirbhíse poiblí</span><span class="sxs-lookup"><span data-stu-id="2d230-278">uimhir phearsanta seirbhíse poiblí</span></span>
  
<span data-ttu-id="2d230-p103">uimh. PSP</span><span class="sxs-lookup"><span data-stu-id="2d230-p103">uimh. psp</span></span>
  
## <a name="italy"></a><span data-ttu-id="2d230-281">Italia</span><span class="sxs-lookup"><span data-stu-id="2d230-281">Italy</span></span>

### <a name="format"></a><span data-ttu-id="2d230-282">Formato</span><span class="sxs-lookup"><span data-stu-id="2d230-282">Format</span></span>

<span data-ttu-id="2d230-283">Una combinazione di 16 caratteri di lettere e cifre nel formato specificato</span><span class="sxs-lookup"><span data-stu-id="2d230-283">A 16-character combination of letters and digits in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="2d230-284">Modello</span><span class="sxs-lookup"><span data-stu-id="2d230-284">Pattern</span></span>

<span data-ttu-id="2d230-285">Una combinazione di 16 caratteri di lettere e cifre:</span><span class="sxs-lookup"><span data-stu-id="2d230-285">A 16-character combination of letters and digits:</span></span>
  
- <span data-ttu-id="2d230-286">Tre lettere che corrispondono ai primi tre consonanti nel nome del gruppo</span><span class="sxs-lookup"><span data-stu-id="2d230-286">Three letters that correspond to the first three consonants in the family name</span></span>
    
- <span data-ttu-id="2d230-287">Tre lettere che corrispondono al primo, terza e quarta consonanti in nome</span><span class="sxs-lookup"><span data-stu-id="2d230-287">Three letters that correspond to the first, third, and fourth consonants in the first name</span></span>
    
- <span data-ttu-id="2d230-288">Due cifre che corrispondono all'ultimo cifre dell'anno di nascita</span><span class="sxs-lookup"><span data-stu-id="2d230-288">Two digits that correspond to the last digits of the birth year</span></span>
    
- <span data-ttu-id="2d230-289">Una lettera corrispondente per la lettera per il mese di nascita, ovvero lettere vengono utilizzate in ordine alfabetico, ma vengono utilizzate solo lettere da A F, H, L, M, P, R per T (in questo modo, gennaio corrisponde a un e ottobre è R)</span><span class="sxs-lookup"><span data-stu-id="2d230-289">One letter that corresponds to the letter for the month of birth—letters are used in alphabetical order, but only the letters A to E, H, L, M, P, R to T are used (thus, January is A and October is R)</span></span>
    
- <span data-ttu-id="2d230-290">Due cifre che corrispondono al giorno del mese di nascita, per poter distinguere tra i due sessi, 40 viene aggiunto al giorno di nascita donne</span><span class="sxs-lookup"><span data-stu-id="2d230-290">Two digits that correspond to the day of the month of birth—in order to differentiate between genders, 40 is added to the day of birth for women</span></span>
    
- <span data-ttu-id="2d230-291">Quattro cifre che corrisponde all'indicativo di località specifico comune dove nascita della persona (livello nazionale codici vengono utilizzati per i paesi esterni)</span><span class="sxs-lookup"><span data-stu-id="2d230-291">Four digits that corresponds to the area code specific to the municipality where the person was born (country-wide codes are used for foreign countries)</span></span>
    
- <span data-ttu-id="2d230-292">Una cifra parità</span><span class="sxs-lookup"><span data-stu-id="2d230-292">One parity digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="2d230-293">Checksum</span><span class="sxs-lookup"><span data-stu-id="2d230-293">Checksum</span></span>

<span data-ttu-id="2d230-294">Sì</span><span class="sxs-lookup"><span data-stu-id="2d230-294">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="2d230-295">Definizione</span><span class="sxs-lookup"><span data-stu-id="2d230-295">Definition</span></span>

<span data-ttu-id="2d230-296">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="2d230-296">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="2d230-297">La funzione `Func_italy_eu_national_id_card` consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="2d230-297">The function  `Func_italy_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="2d230-298">Una parola chiave da `Keywords_italy_eu_national_id_card` viene trovato.</span><span class="sxs-lookup"><span data-stu-id="2d230-298">A keyword from  `Keywords_italy_eu_national_id_card` is found.</span></span> 
    
<span data-ttu-id="2d230-299">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="2d230-299">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="2d230-300">La funzione `Func_italy_eu_national_id_card` consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="2d230-300">The function  `Func_italy_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
```
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_italy_eu_national_id_card" />
          <Match idRef="Keywords_italy_eu_national_id_card" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_italy_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="2d230-301">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="2d230-301">Keywords</span></span>

#### <a name="keywordsitalyeunationalidcard"></a><span data-ttu-id="2d230-302">Keywords_italy_eu_national_id_card</span><span class="sxs-lookup"><span data-stu-id="2d230-302">Keywords_italy_eu_national_id_card</span></span>

<span data-ttu-id="2d230-303">codice personale</span><span class="sxs-lookup"><span data-stu-id="2d230-303">personal code</span></span>
  
<span data-ttu-id="2d230-304">numero di codice personale</span><span class="sxs-lookup"><span data-stu-id="2d230-304">personal code number</span></span>
  
<span data-ttu-id="2d230-305">numero dei certificati personali</span><span class="sxs-lookup"><span data-stu-id="2d230-305">personal certificate number</span></span>
  
<span data-ttu-id="2d230-306">codice fiscale</span><span class="sxs-lookup"><span data-stu-id="2d230-306">fiscal code</span></span>
  
<span data-ttu-id="2d230-307">personalcodeno #</span><span class="sxs-lookup"><span data-stu-id="2d230-307">personalcodeno#</span></span>
  
<span data-ttu-id="2d230-308">numero id personale</span><span class="sxs-lookup"><span data-stu-id="2d230-308">personal id number</span></span>
  
<span data-ttu-id="2d230-309">codice id personale</span><span class="sxs-lookup"><span data-stu-id="2d230-309">personal id code</span></span>
  
<span data-ttu-id="2d230-310">codice personale</span><span class="sxs-lookup"><span data-stu-id="2d230-310">codice personale</span></span>
  
<span data-ttu-id="2d230-311">Numero certificato personale</span><span class="sxs-lookup"><span data-stu-id="2d230-311">numero certificato personale</span></span>
  
<span data-ttu-id="2d230-312">numero personale</span><span class="sxs-lookup"><span data-stu-id="2d230-312">numero personale</span></span>
  
<span data-ttu-id="2d230-313">numero id personale</span><span class="sxs-lookup"><span data-stu-id="2d230-313">numero id personale</span></span>
  
<span data-ttu-id="2d230-314">codice id personale</span><span class="sxs-lookup"><span data-stu-id="2d230-314">codice id personale</span></span>
  
<span data-ttu-id="2d230-315">codice fiscale</span><span class="sxs-lookup"><span data-stu-id="2d230-315">codice fiscale</span></span>
  
## <a name="italy"></a><span data-ttu-id="2d230-316">Italia</span><span class="sxs-lookup"><span data-stu-id="2d230-316">Italy</span></span>

### <a name="format"></a><span data-ttu-id="2d230-317">Formato</span><span class="sxs-lookup"><span data-stu-id="2d230-317">Format</span></span>

<span data-ttu-id="2d230-318">11 cifre e un segno meno nel formato specificato</span><span class="sxs-lookup"><span data-stu-id="2d230-318">11 digits and a hyphen in the specified format</span></span>
  
### <a name="pattern"></a><span data-ttu-id="2d230-319">Modello</span><span class="sxs-lookup"><span data-stu-id="2d230-319">Pattern</span></span>

<span data-ttu-id="2d230-320">11 cifre e un segno meno:</span><span class="sxs-lookup"><span data-stu-id="2d230-320">11 digits and a hyphen:</span></span>
  
-  <span data-ttu-id="2d230-321">Sei cifre che corrispondono alla data di nascita (DDMMYY)</span><span class="sxs-lookup"><span data-stu-id="2d230-321">Six digits that correspond to the birth date (DDMMYY)</span></span> 
    
- <span data-ttu-id="2d230-322">Una lineetta</span><span class="sxs-lookup"><span data-stu-id="2d230-322">A hyphen</span></span>
    
- <span data-ttu-id="2d230-323">Una cifra che corrisponde al century di nascita ("0" per century diciannovesimo, per century ventesimo "1" e "2" per century ventunesimo)</span><span class="sxs-lookup"><span data-stu-id="2d230-323">One digit that corresponds to the century of birth ("0" for 19th century, "1" for 20th century, and "2" for 21st century)</span></span>
    
- <span data-ttu-id="2d230-324">Quattro cifre, generati in modo casuale</span><span class="sxs-lookup"><span data-stu-id="2d230-324">Four digits, randomly generated</span></span>
    
### <a name="checksum"></a><span data-ttu-id="2d230-325">Checksum</span><span class="sxs-lookup"><span data-stu-id="2d230-325">Checksum</span></span>

<span data-ttu-id="2d230-326">Sì</span><span class="sxs-lookup"><span data-stu-id="2d230-326">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="2d230-327">Definizione</span><span class="sxs-lookup"><span data-stu-id="2d230-327">Definition</span></span>

<span data-ttu-id="2d230-328">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="2d230-328">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="2d230-329">La funzione `Func_latvia_eu_national_id_card` consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="2d230-329">The function  `Func_latvia_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="2d230-330">Una parola chiave da `Keywords_latvia_eu_national_id_card` viene trovato.</span><span class="sxs-lookup"><span data-stu-id="2d230-330">A keyword from  `Keywords_latvia_eu_national_id_card` is found.</span></span> 
    
<span data-ttu-id="2d230-331">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="2d230-331">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="2d230-332">La funzione `Func_latvia_eu_national_id_card` consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="2d230-332">The function  `Func_latvia_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
```
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_latvia_eu_national_id_card" />
          <Match idRef="Keywords_latvia_eu_national_id_card" />
        </Pattern>
 <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_latvia_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="2d230-333">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="2d230-333">Keywords</span></span>

#### <a name="keywordslatviaeunationalidcard"></a><span data-ttu-id="2d230-334">Keywords_latvia_eu_national_id_card</span><span class="sxs-lookup"><span data-stu-id="2d230-334">Keywords_latvia_eu_national_id_card</span></span>

<span data-ttu-id="2d230-335">codice personale</span><span class="sxs-lookup"><span data-stu-id="2d230-335">personal code</span></span>
  
<span data-ttu-id="2d230-336">numero di codice personale</span><span class="sxs-lookup"><span data-stu-id="2d230-336">personal code number</span></span>
  
<span data-ttu-id="2d230-337">numero dei certificati personali</span><span class="sxs-lookup"><span data-stu-id="2d230-337">personal certificate number</span></span>
  
<span data-ttu-id="2d230-338">personalcodeno #</span><span class="sxs-lookup"><span data-stu-id="2d230-338">personalcodeno#</span></span>
  
<span data-ttu-id="2d230-339">numero id personale</span><span class="sxs-lookup"><span data-stu-id="2d230-339">personal id number</span></span>
  
<span data-ttu-id="2d230-340">codice id personale</span><span class="sxs-lookup"><span data-stu-id="2d230-340">personal id code</span></span>
  
<span data-ttu-id="2d230-341">persone kods</span><span class="sxs-lookup"><span data-stu-id="2d230-341">personas kods</span></span>
  
## <a name="lithuania"></a><span data-ttu-id="2d230-342">Lituania</span><span class="sxs-lookup"><span data-stu-id="2d230-342">Lithuania</span></span>

### <a name="format"></a><span data-ttu-id="2d230-343">Formato</span><span class="sxs-lookup"><span data-stu-id="2d230-343">Format</span></span>

<span data-ttu-id="2d230-344">11 cifre senza spazi e i delimitatori</span><span class="sxs-lookup"><span data-stu-id="2d230-344">11 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="2d230-345">Modello</span><span class="sxs-lookup"><span data-stu-id="2d230-345">Pattern</span></span>

<span data-ttu-id="2d230-346">11 cifre senza spazi e i delimitatori:</span><span class="sxs-lookup"><span data-stu-id="2d230-346">11 digits without spaces and delimiters:</span></span>
  
- <span data-ttu-id="2d230-347">Una cifra che corrisponde al sesso della persona e century di nascita</span><span class="sxs-lookup"><span data-stu-id="2d230-347">One digit that corresponds to the person's gender and century of birth</span></span>
    
-  <span data-ttu-id="2d230-348">Sei cifre che corrispondono alla data di nascita (AAMMGG)</span><span class="sxs-lookup"><span data-stu-id="2d230-348">Six digits that correspond to birth date (YYMMDD)</span></span> 
    
- <span data-ttu-id="2d230-349">Tre cifre che corrispondono al numero di serie della data di nascita</span><span class="sxs-lookup"><span data-stu-id="2d230-349">Three digits that correspond to the serial number of the date of birth</span></span>
    
- <span data-ttu-id="2d230-350">Cifra di un controllo</span><span class="sxs-lookup"><span data-stu-id="2d230-350">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="2d230-351">Checksum</span><span class="sxs-lookup"><span data-stu-id="2d230-351">Checksum</span></span>

<span data-ttu-id="2d230-352">Sì</span><span class="sxs-lookup"><span data-stu-id="2d230-352">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="2d230-353">Definizione</span><span class="sxs-lookup"><span data-stu-id="2d230-353">Definition</span></span>

<span data-ttu-id="2d230-354">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="2d230-354">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="2d230-355">La funzione `Func_lithuania_eu_national_id_card` consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="2d230-355">The function  `Func_lithuania_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="2d230-356">Una parola chiave da `Keywords_lithuania_eu_national_id_card` viene trovato.</span><span class="sxs-lookup"><span data-stu-id="2d230-356">A keyword from  `Keywords_lithuania_eu_national_id_card` is found.</span></span> 
    
<span data-ttu-id="2d230-357">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="2d230-357">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="2d230-358">La funzione `Func_lithuania_eu_national_id_card` consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="2d230-358">The function  `Func_lithuania_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
```
 
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_lithuania_eu_national_id_card" />
          <Match idRef="Keywords_lithuania_eu_national_id_card" />
        </Pattern> 
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_lithuania_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="2d230-359">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="2d230-359">Keywords</span></span>

#### <a name="keywordslithuaniaeunationalidcard"></a><span data-ttu-id="2d230-360">Keywords_lithuania_eu_national_id_card</span><span class="sxs-lookup"><span data-stu-id="2d230-360">Keywords_lithuania_eu_national_id_card</span></span>

<span data-ttu-id="2d230-361">codice numerico personali</span><span class="sxs-lookup"><span data-stu-id="2d230-361">personal numeric code</span></span>
  
<span data-ttu-id="2d230-362">numero di identificazione univoco</span><span class="sxs-lookup"><span data-stu-id="2d230-362">unique identification number</span></span>
  
<span data-ttu-id="2d230-363">numero del servizio cittadini</span><span class="sxs-lookup"><span data-stu-id="2d230-363">citizen service number</span></span>
  
<span data-ttu-id="2d230-364">numero di identificazione univoco</span><span class="sxs-lookup"><span data-stu-id="2d230-364">unique identity number</span></span>
  
<span data-ttu-id="2d230-365">uniqueidentityno #</span><span class="sxs-lookup"><span data-stu-id="2d230-365">uniqueidentityno#</span></span>
  
<span data-ttu-id="2d230-366">codice personale.</span><span class="sxs-lookup"><span data-stu-id="2d230-366">personal code.</span></span>
  
<span data-ttu-id="2d230-367">asmeninis skaitmeninis kodas</span><span class="sxs-lookup"><span data-stu-id="2d230-367">asmeninis skaitmeninis kodas</span></span>
  
<span data-ttu-id="2d230-368">unikalus identifikavimo numeris</span><span class="sxs-lookup"><span data-stu-id="2d230-368">unikalus identifikavimo numeris</span></span>
  
<span data-ttu-id="2d230-369">piliečio paslaugos numeris</span><span class="sxs-lookup"><span data-stu-id="2d230-369">piliečio paslaugos numeris</span></span>
  
<span data-ttu-id="2d230-370">unikalus identifikavimo kodas</span><span class="sxs-lookup"><span data-stu-id="2d230-370">unikalus identifikavimo kodas</span></span>
  
<span data-ttu-id="2d230-371">kodas asmens.</span><span class="sxs-lookup"><span data-stu-id="2d230-371">asmens kodas.</span></span>
  
## <a name="luxemburg"></a><span data-ttu-id="2d230-372">Lussemburgo</span><span class="sxs-lookup"><span data-stu-id="2d230-372">Luxemburg</span></span>

### <a name="format"></a><span data-ttu-id="2d230-373">Formato</span><span class="sxs-lookup"><span data-stu-id="2d230-373">Format</span></span>

<span data-ttu-id="2d230-374">11 cifre senza spazi e i delimitatori</span><span class="sxs-lookup"><span data-stu-id="2d230-374">11 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="2d230-375">Modello</span><span class="sxs-lookup"><span data-stu-id="2d230-375">Pattern</span></span>

<span data-ttu-id="2d230-376">11 cifre</span><span class="sxs-lookup"><span data-stu-id="2d230-376">11 digits</span></span>
  
- <span data-ttu-id="2d230-377">Una cifra che corrisponde al sesso della persona e century di nascita</span><span class="sxs-lookup"><span data-stu-id="2d230-377">One digit that corresponds to the person's gender and century of birth</span></span>
    
-  <span data-ttu-id="2d230-378">Sei cifre che corrispondono alla data di nascita (AAMMGG)</span><span class="sxs-lookup"><span data-stu-id="2d230-378">Six digits that correspond to birth date (YYMMDD)</span></span> 
    
- <span data-ttu-id="2d230-379">Tre cifre che corrispondono al numero di serie della data di nascita</span><span class="sxs-lookup"><span data-stu-id="2d230-379">Three digits that correspond to the serial number of the date of birth</span></span>
    
- <span data-ttu-id="2d230-380">Cifra di un controllo</span><span class="sxs-lookup"><span data-stu-id="2d230-380">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="2d230-381">Checksum</span><span class="sxs-lookup"><span data-stu-id="2d230-381">Checksum</span></span>

<span data-ttu-id="2d230-382">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="2d230-382">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="2d230-383">Definizione</span><span class="sxs-lookup"><span data-stu-id="2d230-383">Definition</span></span>

<span data-ttu-id="2d230-384">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="2d230-384">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="2d230-385">L'espressione regolare `Regex_luxemburg_eu_national_id_card` consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="2d230-385">The regular expression  `Regex_luxemburg_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="2d230-386">Una parola chiave da `Keywords_luxemburg_eu_national_id_card` viene trovato.</span><span class="sxs-lookup"><span data-stu-id="2d230-386">A keyword from  `Keywords_luxemburg_eu_national_id_card` is found.</span></span> 
    
```
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_luxemburg_eu_national_id_card" />
          <Match idRef="Keywords_luxemburg_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="2d230-387">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="2d230-387">Keywords</span></span>

#### <a name="keywordsluxemburgeunationalidcard"></a><span data-ttu-id="2d230-388">Keywords_luxemburg_eu_national_id_card</span><span class="sxs-lookup"><span data-stu-id="2d230-388">Keywords_luxemburg_eu_national_id_card</span></span>

<span data-ttu-id="2d230-389">id personale</span><span class="sxs-lookup"><span data-stu-id="2d230-389">personal id</span></span>
  
<span data-ttu-id="2d230-390">numero id personale</span><span class="sxs-lookup"><span data-stu-id="2d230-390">personal id number</span></span>
  
<span data-ttu-id="2d230-391">personalidno #</span><span class="sxs-lookup"><span data-stu-id="2d230-391">personalidno#</span></span>
  
<span data-ttu-id="2d230-392">numero id univoco</span><span class="sxs-lookup"><span data-stu-id="2d230-392">unique id number</span></span>
  
<span data-ttu-id="2d230-393">personalidnumber #</span><span class="sxs-lookup"><span data-stu-id="2d230-393">personalidnumber#</span></span>
  
<span data-ttu-id="2d230-394">chiave id univoci</span><span class="sxs-lookup"><span data-stu-id="2d230-394">unique id key</span></span>
  
<span data-ttu-id="2d230-395">codice id personale</span><span class="sxs-lookup"><span data-stu-id="2d230-395">personal id code</span></span>
  
<span data-ttu-id="2d230-396">uniqueidkey #</span><span class="sxs-lookup"><span data-stu-id="2d230-396">uniqueidkey#</span></span>
  
<span data-ttu-id="2d230-397">singolo codice</span><span class="sxs-lookup"><span data-stu-id="2d230-397">individual code</span></span>
  
<span data-ttu-id="2d230-398">id singoli</span><span class="sxs-lookup"><span data-stu-id="2d230-398">individual id</span></span>
  
<span data-ttu-id="2d230-399">id eindeutige-nummer</span><span class="sxs-lookup"><span data-stu-id="2d230-399">eindeutige id-nummer</span></span>
  
<span data-ttu-id="2d230-400">id eindeutige</span><span class="sxs-lookup"><span data-stu-id="2d230-400">eindeutige id</span></span>
  
<span data-ttu-id="2d230-401">ID personnelle</span><span class="sxs-lookup"><span data-stu-id="2d230-401">id personnelle</span></span>
  
<span data-ttu-id="2d230-402">numéro identificazione personale</span><span class="sxs-lookup"><span data-stu-id="2d230-402">numéro d'identification personnel</span></span>
  
<span data-ttu-id="2d230-403">idpersonnelle #</span><span class="sxs-lookup"><span data-stu-id="2d230-403">idpersonnelle#</span></span>
  
<span data-ttu-id="2d230-404">persönliche identifikationsnummer</span><span class="sxs-lookup"><span data-stu-id="2d230-404">persönliche identifikationsnummer</span></span>
  
<span data-ttu-id="2d230-405">eindeutigeid #</span><span class="sxs-lookup"><span data-stu-id="2d230-405">eindeutigeid#</span></span>
  
## <a name="malta"></a><span data-ttu-id="2d230-406">Malta</span><span class="sxs-lookup"><span data-stu-id="2d230-406">Malta</span></span>

### <a name="format"></a><span data-ttu-id="2d230-407">Formato</span><span class="sxs-lookup"><span data-stu-id="2d230-407">Format</span></span>

<span data-ttu-id="2d230-408">Sette cifre seguite da una lettera</span><span class="sxs-lookup"><span data-stu-id="2d230-408">Seven digits followed by one letter</span></span>
  
### <a name="pattern"></a><span data-ttu-id="2d230-409">Modello</span><span class="sxs-lookup"><span data-stu-id="2d230-409">Pattern</span></span>

<span data-ttu-id="2d230-410">Sette cifre seguite da una lettera:</span><span class="sxs-lookup"><span data-stu-id="2d230-410">Seven digits followed by one letter:</span></span>
  
-  <span data-ttu-id="2d230-411">Sette cifre</span><span class="sxs-lookup"><span data-stu-id="2d230-411">Seven digits</span></span> 
    
- <span data-ttu-id="2d230-412">Una lettera maiuscola (distinzione tra maiuscole e minuscole)</span><span class="sxs-lookup"><span data-stu-id="2d230-412">One uppercase letter (case sensitive)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="2d230-413">Checksum</span><span class="sxs-lookup"><span data-stu-id="2d230-413">Checksum</span></span>

<span data-ttu-id="2d230-414">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="2d230-414">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="2d230-415">Definizione</span><span class="sxs-lookup"><span data-stu-id="2d230-415">Definition</span></span>

<span data-ttu-id="2d230-416">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="2d230-416">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="2d230-417">L'espressione regolare `Regex_malta_eu_national_id_card` consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="2d230-417">The regular expression  `Regex_malta_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="2d230-418">Una parola chiave da `Keywords_malta_eu_national_id_card` viene trovato.</span><span class="sxs-lookup"><span data-stu-id="2d230-418">A keyword from  `Keywords_malta_eu_national_id_card` is found.</span></span> 
    
<span data-ttu-id="2d230-419">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 65%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="2d230-419">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="2d230-420">L'espressione regolare `Regex_malta_eu_national_id_card` consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="2d230-420">The regular expression  `Regex_malta_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
```
 
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_malta_eu_national_id_card" />
          <Match idRef="Keywords_malta_eu_national_id_card" />
        </Pattern>
<Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_malta_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="2d230-421">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="2d230-421">Keywords</span></span>

#### <a name="keywordsmaltaeunationalidcard"></a><span data-ttu-id="2d230-422">Keywords_malta_eu_national_id_card</span><span class="sxs-lookup"><span data-stu-id="2d230-422">Keywords_malta_eu_national_id_card</span></span>

<span data-ttu-id="2d230-423">codice numerico personali</span><span class="sxs-lookup"><span data-stu-id="2d230-423">personal numeric code</span></span>
  
<span data-ttu-id="2d230-424">numero di identificazione univoco</span><span class="sxs-lookup"><span data-stu-id="2d230-424">unique identification number</span></span>
  
<span data-ttu-id="2d230-425">numero del servizio cittadini</span><span class="sxs-lookup"><span data-stu-id="2d230-425">citizen service number</span></span>
  
<span data-ttu-id="2d230-426">numero di identificazione univoco</span><span class="sxs-lookup"><span data-stu-id="2d230-426">unique identity number</span></span>
  
<span data-ttu-id="2d230-427">uniqueidentityno #</span><span class="sxs-lookup"><span data-stu-id="2d230-427">uniqueidentityno#</span></span>
  
<span data-ttu-id="2d230-428">kodiċi numerali personali</span><span class="sxs-lookup"><span data-stu-id="2d230-428">kodiċi numerali personali</span></span>
  
<span data-ttu-id="2d230-429">numru ta ' identifikazzjoni uniku</span><span class="sxs-lookup"><span data-stu-id="2d230-429">numru ta 'identifikazzjoni uniku</span></span>
  
<span data-ttu-id="2d230-430">numru attività servizz taċ-ċittadin</span><span class="sxs-lookup"><span data-stu-id="2d230-430">numru tas-servizz taċ-ċittadin</span></span>
  
<span data-ttu-id="2d230-431">numru ta' identità uniku</span><span class="sxs-lookup"><span data-stu-id="2d230-431">numru ta' identità uniku</span></span>
  
## <a name="netherlands"></a><span data-ttu-id="2d230-432">Paesi Bassi</span><span class="sxs-lookup"><span data-stu-id="2d230-432">Netherlands</span></span>

### <a name="format"></a><span data-ttu-id="2d230-433">Formato</span><span class="sxs-lookup"><span data-stu-id="2d230-433">Format</span></span>

<span data-ttu-id="2d230-434">Nove cifre senza spazi o delimitatori</span><span class="sxs-lookup"><span data-stu-id="2d230-434">Nine digits without spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="2d230-435">Modello</span><span class="sxs-lookup"><span data-stu-id="2d230-435">Pattern</span></span>

<span data-ttu-id="2d230-436">9 cifre</span><span class="sxs-lookup"><span data-stu-id="2d230-436">Nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="2d230-437">Checksum</span><span class="sxs-lookup"><span data-stu-id="2d230-437">Checksum</span></span>

<span data-ttu-id="2d230-438">Sì</span><span class="sxs-lookup"><span data-stu-id="2d230-438">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="2d230-439">Definizione</span><span class="sxs-lookup"><span data-stu-id="2d230-439">Definition</span></span>

<span data-ttu-id="2d230-440">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="2d230-440">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="2d230-441">La funzione `Func_netherlands_eu_national_id_card` consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="2d230-441">The function  `Func_netherlands_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="2d230-442">È possibile trovare una parola chiave da.</span><span class="sxs-lookup"><span data-stu-id="2d230-442">A keyword from is found.</span></span>
    
<span data-ttu-id="2d230-443">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="2d230-443">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="2d230-444">La funzione `Func_netherlands_eu_national_id_card` consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="2d230-444">The function  `Func_netherlands_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
```
 
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_netherlands_eu_national_id_card" />
          <Match idRef="Keywords_netherlands_eu_national_id_card" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_netherlands_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="2d230-445">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="2d230-445">Keywords</span></span>

#### <a name="keywordsnetherlandseunationalidcard"></a><span data-ttu-id="2d230-446">Keywords_netherlands_eu_national_id_card</span><span class="sxs-lookup"><span data-stu-id="2d230-446">Keywords_netherlands_eu_national_id_card</span></span>

<span data-ttu-id="2d230-447">codice numerico personali</span><span class="sxs-lookup"><span data-stu-id="2d230-447">personal numeric code</span></span>
  
<span data-ttu-id="2d230-448">numero di identificazione univoco</span><span class="sxs-lookup"><span data-stu-id="2d230-448">unique identification number</span></span>
  
<span data-ttu-id="2d230-449">numero del servizio cittadini</span><span class="sxs-lookup"><span data-stu-id="2d230-449">citizen service number</span></span>
  
<span data-ttu-id="2d230-450">numero di identificazione univoco</span><span class="sxs-lookup"><span data-stu-id="2d230-450">unique identity number</span></span>
  
<span data-ttu-id="2d230-451">uniqueidentityno #</span><span class="sxs-lookup"><span data-stu-id="2d230-451">uniqueidentityno#</span></span>
  
<span data-ttu-id="2d230-452">bsn</span><span class="sxs-lookup"><span data-stu-id="2d230-452">bsn</span></span>
  
<span data-ttu-id="2d230-453">bsn #</span><span class="sxs-lookup"><span data-stu-id="2d230-453">bsn#</span></span>
  
<span data-ttu-id="2d230-454">codice numerieke persoonlijke</span><span class="sxs-lookup"><span data-stu-id="2d230-454">persoonlijke numerieke code</span></span>
  
<span data-ttu-id="2d230-455">uniek identificatienummer</span><span class="sxs-lookup"><span data-stu-id="2d230-455">uniek identificatienummer</span></span>
  
<span data-ttu-id="2d230-456">burgerservicenummer</span><span class="sxs-lookup"><span data-stu-id="2d230-456">burgerservicenummer</span></span>
  
<span data-ttu-id="2d230-457">uniek identiteitsnummer</span><span class="sxs-lookup"><span data-stu-id="2d230-457">uniek identiteitsnummer</span></span>
  
## <a name="poland"></a><span data-ttu-id="2d230-458">Polonia</span><span class="sxs-lookup"><span data-stu-id="2d230-458">Poland</span></span>

<span data-ttu-id="2d230-459">Per ulteriori informazioni, vedere la sezione "Polonia nazionale ID (PESEL)" in [cercare il quali i tipi di informazioni riservate](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="2d230-459">For details, see the section "Poland National ID (PESEL)" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="portugal"></a><span data-ttu-id="2d230-460">Portogallo</span><span class="sxs-lookup"><span data-stu-id="2d230-460">Portugal</span></span>

<span data-ttu-id="2d230-461">Per ulteriori informazioni, vedere la sezione "Portogallo cittadini scheda numero" in [cercare il quali i tipi di informazioni riservate](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="2d230-461">For details, see the section "Portugal Citizen Card Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="romania"></a><span data-ttu-id="2d230-462">Romania</span><span class="sxs-lookup"><span data-stu-id="2d230-462">Romania</span></span>

### <a name="format"></a><span data-ttu-id="2d230-463">Formato</span><span class="sxs-lookup"><span data-stu-id="2d230-463">Format</span></span>

<span data-ttu-id="2d230-464">13 cifre senza spazi e i delimitatori</span><span class="sxs-lookup"><span data-stu-id="2d230-464">13 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="2d230-465">Modello</span><span class="sxs-lookup"><span data-stu-id="2d230-465">Pattern</span></span>

<span data-ttu-id="2d230-466">13 cifre</span><span class="sxs-lookup"><span data-stu-id="2d230-466">13 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="2d230-467">Checksum</span><span class="sxs-lookup"><span data-stu-id="2d230-467">Checksum</span></span>

<span data-ttu-id="2d230-468">Sì</span><span class="sxs-lookup"><span data-stu-id="2d230-468">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="2d230-469">Definizione</span><span class="sxs-lookup"><span data-stu-id="2d230-469">Definition</span></span>

<span data-ttu-id="2d230-470">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="2d230-470">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="2d230-471">La funzione `Func_romania_eu_national_id_card` consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="2d230-471">The function  `Func_romania_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="2d230-472">Una parola chiave da `Keywords_romania_eu_national_id_card` viene trovato.</span><span class="sxs-lookup"><span data-stu-id="2d230-472">A keyword from  `Keywords_romania_eu_national_id_card` is found.</span></span> 
    
<span data-ttu-id="2d230-473">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="2d230-473">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="2d230-474">La funzione `Func_romania_eu_national_id_card` consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="2d230-474">The function  `Func_romania_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
```
 
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_romania_eu_national_id_card" />
          <Match idRef="Keywords_romania_eu_national_id_card" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_romania_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="2d230-475">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="2d230-475">Keywords</span></span>

#### <a name="keywordsromaniaeunationalidcard"></a><span data-ttu-id="2d230-476">Keywords_romania_eu_national_id_card</span><span class="sxs-lookup"><span data-stu-id="2d230-476">Keywords_romania_eu_national_id_card</span></span>

<span data-ttu-id="2d230-477">codice numerico personali</span><span class="sxs-lookup"><span data-stu-id="2d230-477">personal numeric code</span></span>
  
<span data-ttu-id="2d230-478">numero di identificazione univoco</span><span class="sxs-lookup"><span data-stu-id="2d230-478">unique identification number</span></span>
  
<span data-ttu-id="2d230-479">cnp</span><span class="sxs-lookup"><span data-stu-id="2d230-479">cnp</span></span>
  
<span data-ttu-id="2d230-480">cnp #</span><span class="sxs-lookup"><span data-stu-id="2d230-480">cnp#</span></span>
  
<span data-ttu-id="2d230-481">aggiungere</span><span class="sxs-lookup"><span data-stu-id="2d230-481">pin</span></span>
  
<span data-ttu-id="2d230-482">PIN #</span><span class="sxs-lookup"><span data-stu-id="2d230-482">pin#</span></span>
  
<span data-ttu-id="2d230-483">numero di assicurazione</span><span class="sxs-lookup"><span data-stu-id="2d230-483">insurance number</span></span>
  
<span data-ttu-id="2d230-484">insurancenumber #</span><span class="sxs-lookup"><span data-stu-id="2d230-484">insurancenumber#</span></span>
  
<span data-ttu-id="2d230-485">numero di identificazione univoco</span><span class="sxs-lookup"><span data-stu-id="2d230-485">unique identity number</span></span>
  
<span data-ttu-id="2d230-486">uniqueidentityno #</span><span class="sxs-lookup"><span data-stu-id="2d230-486">uniqueidentityno#</span></span>
  
<span data-ttu-id="2d230-487">Cod numerico personale</span><span class="sxs-lookup"><span data-stu-id="2d230-487">cod numeric personal</span></span>
  
<span data-ttu-id="2d230-488">Cod identificare personali</span><span class="sxs-lookup"><span data-stu-id="2d230-488">cod identificare personal</span></span>
  
<span data-ttu-id="2d230-489">identificare unic Cod</span><span class="sxs-lookup"><span data-stu-id="2d230-489">cod unic identificare</span></span>
  
<span data-ttu-id="2d230-490">număr unic personali</span><span class="sxs-lookup"><span data-stu-id="2d230-490">număr personal unic</span></span>
  
<span data-ttu-id="2d230-491">număr identitate</span><span class="sxs-lookup"><span data-stu-id="2d230-491">număr identitate</span></span>
  
<span data-ttu-id="2d230-492">identificare număr personali</span><span class="sxs-lookup"><span data-stu-id="2d230-492">număr identificare personal</span></span>
  
<span data-ttu-id="2d230-493">număridentitate #</span><span class="sxs-lookup"><span data-stu-id="2d230-493">număridentitate#</span></span>
  
<span data-ttu-id="2d230-494">codnumericpersonal #</span><span class="sxs-lookup"><span data-stu-id="2d230-494">codnumericpersonal#</span></span>
  
<span data-ttu-id="2d230-495">numărpersonalunic #</span><span class="sxs-lookup"><span data-stu-id="2d230-495">numărpersonalunic#</span></span>
  
## <a name="slovakia"></a><span data-ttu-id="2d230-496">Slovacchia</span><span class="sxs-lookup"><span data-stu-id="2d230-496">Slovakia</span></span>

### <a name="format"></a><span data-ttu-id="2d230-497">Formato</span><span class="sxs-lookup"><span data-stu-id="2d230-497">Format</span></span>

<span data-ttu-id="2d230-498">Dieci cifre che contiene una barra rovesciata</span><span class="sxs-lookup"><span data-stu-id="2d230-498">Ten digits containing one backslash</span></span>
  
### <a name="pattern"></a><span data-ttu-id="2d230-499">Modello</span><span class="sxs-lookup"><span data-stu-id="2d230-499">Pattern</span></span>

<span data-ttu-id="2d230-500">Dieci cifre che contiene una barra rovesciata:</span><span class="sxs-lookup"><span data-stu-id="2d230-500">Ten digits containing one backslash:</span></span>
  
### <a name="checksum"></a><span data-ttu-id="2d230-501">Checksum</span><span class="sxs-lookup"><span data-stu-id="2d230-501">Checksum</span></span>

<span data-ttu-id="2d230-502">Sì</span><span class="sxs-lookup"><span data-stu-id="2d230-502">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="2d230-503">Definizione</span><span class="sxs-lookup"><span data-stu-id="2d230-503">Definition</span></span>

<span data-ttu-id="2d230-504">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="2d230-504">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="2d230-505">La funzione `Func_slovakia_eu_national_id_card` consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="2d230-505">The function  `Func_slovakia_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="2d230-506">Una parola chiave da `Keywords_slovakia_eu_national_id_card` viene trovato.</span><span class="sxs-lookup"><span data-stu-id="2d230-506">A keyword from  `Keywords_slovakia_eu_national_id_card` is found.</span></span> 
    
<span data-ttu-id="2d230-507">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="2d230-507">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="2d230-508">La funzione `Func_slovakia_eu_national_id_card` consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="2d230-508">The function  `Func_slovakia_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
```
 
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_slovakia_eu_national_id_card" />
          <Match idRef="Keywords_slovakia_eu_national_id_card" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_slovakia_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="2d230-509">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="2d230-509">Keywords</span></span>

#### <a name="keywordsslovakiaeunationalidcard"></a><span data-ttu-id="2d230-510">Keywords_slovakia_eu_national_id_card</span><span class="sxs-lookup"><span data-stu-id="2d230-510">Keywords_slovakia_eu_national_id_card</span></span>

<span data-ttu-id="2d230-511">numero di nascita</span><span class="sxs-lookup"><span data-stu-id="2d230-511">birth number</span></span>
  
<span data-ttu-id="2d230-512">numero identificativo nazionale</span><span class="sxs-lookup"><span data-stu-id="2d230-512">national identification number</span></span>
  
<span data-ttu-id="2d230-513">numero di identificazione personale</span><span class="sxs-lookup"><span data-stu-id="2d230-513">personal identification number</span></span>
  
<span data-ttu-id="2d230-514">social security number
</span><span class="sxs-lookup"><span data-stu-id="2d230-514">social security number</span></span>
  
<span data-ttu-id="2d230-515">nationalnumber #</span><span class="sxs-lookup"><span data-stu-id="2d230-515">nationalnumber#</span></span>
  
<span data-ttu-id="2d230-516">SSN #</span><span class="sxs-lookup"><span data-stu-id="2d230-516">ssn#</span></span>
  
<span data-ttu-id="2d230-517">SSN</span><span class="sxs-lookup"><span data-stu-id="2d230-517">ssn</span></span>
  
<span data-ttu-id="2d230-518">numero nazionale</span><span class="sxs-lookup"><span data-stu-id="2d230-518">national number</span></span>
  
<span data-ttu-id="2d230-519">numero id personale</span><span class="sxs-lookup"><span data-stu-id="2d230-519">personal id number</span></span>
  
<span data-ttu-id="2d230-520">personalidnumber #</span><span class="sxs-lookup"><span data-stu-id="2d230-520">personalidnumber#</span></span>
  
<span data-ttu-id="2d230-521">rč</span><span class="sxs-lookup"><span data-stu-id="2d230-521">rč</span></span>
  
<span data-ttu-id="2d230-522">rodné číslo</span><span class="sxs-lookup"><span data-stu-id="2d230-522">rodné číslo</span></span>
  
<span data-ttu-id="2d230-523">rodne cislo</span><span class="sxs-lookup"><span data-stu-id="2d230-523">rodne cislo</span></span>
  
## <a name="slovenia"></a><span data-ttu-id="2d230-524">Slovenia</span><span class="sxs-lookup"><span data-stu-id="2d230-524">Slovenia</span></span>

### <a name="format"></a><span data-ttu-id="2d230-525">Formato</span><span class="sxs-lookup"><span data-stu-id="2d230-525">Format</span></span>

<span data-ttu-id="2d230-526">13 cifre senza spazi o delimitatori</span><span class="sxs-lookup"><span data-stu-id="2d230-526">13 digits without spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="2d230-527">Modello</span><span class="sxs-lookup"><span data-stu-id="2d230-527">Pattern</span></span>

<span data-ttu-id="2d230-528">13 cifre nel formato specificato:</span><span class="sxs-lookup"><span data-stu-id="2d230-528">13 digits in the specified pattern:</span></span>
  
-  <span data-ttu-id="2d230-529">Sette cifre che corrispondono alla data di nascita (DDMMLLL) dove "LLL" corrisponde all'ultima tre cifre dell'anno di nascita</span><span class="sxs-lookup"><span data-stu-id="2d230-529">Seven digits that correspond to the birth date (DDMMLLL) where "LLL" corresponds to the last three digits of the birth year</span></span> 
    
- <span data-ttu-id="2d230-530">Due cifre che corrispondono all'area di nascita</span><span class="sxs-lookup"><span data-stu-id="2d230-530">Two digits that correspond to the area of birth</span></span>
    
- <span data-ttu-id="2d230-531">Tre cifre che corrispondono a una combinazione di sesso e il numero di serie per le persone nati nello stesso giorno (000-499 per maschile) e 500 e 999 per femmina</span><span class="sxs-lookup"><span data-stu-id="2d230-531">Three digits that correspond to a combination of gender and serial number for persons born on the same day (000-499 for male and 500-999 for female)</span></span>
    
- <span data-ttu-id="2d230-532">Cifra di un controllo</span><span class="sxs-lookup"><span data-stu-id="2d230-532">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="2d230-533">Checksum</span><span class="sxs-lookup"><span data-stu-id="2d230-533">Checksum</span></span>

<span data-ttu-id="2d230-534">Sì</span><span class="sxs-lookup"><span data-stu-id="2d230-534">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="2d230-535">Definizione</span><span class="sxs-lookup"><span data-stu-id="2d230-535">Definition</span></span>

<span data-ttu-id="2d230-536">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="2d230-536">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="2d230-537">La funzione `Func_slovenia_eu_national_id_card` consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="2d230-537">The function  `Func_slovenia_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="2d230-538">Una parola chiave da `Keywords_slovenia_eu_national_id_card` viene trovato.</span><span class="sxs-lookup"><span data-stu-id="2d230-538">A keyword from  `Keywords_slovenia_eu_national_id_card` is found.</span></span> 
    
<span data-ttu-id="2d230-539">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="2d230-539">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="2d230-540">La funzione `Func_slovenia_eu_national_id_card` consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="2d230-540">The function  `Func_slovenia_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
```
 
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_slovenia_eu_national_id_card" />
          <Match idRef="Keywords_slovenia_eu_national_id_card" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_slovenia_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="2d230-541">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="2d230-541">Keywords</span></span>

#### <a name="keywordssloveniaeunationalidcard"></a><span data-ttu-id="2d230-542">Keywords_slovenia_eu_national_id_card</span><span class="sxs-lookup"><span data-stu-id="2d230-542">Keywords_slovenia_eu_national_id_card</span></span>

<span data-ttu-id="2d230-543">codice numerico personali</span><span class="sxs-lookup"><span data-stu-id="2d230-543">personal numeric code</span></span>
  
<span data-ttu-id="2d230-544">numero di identificazione univoco</span><span class="sxs-lookup"><span data-stu-id="2d230-544">unique identification number</span></span>
  
<span data-ttu-id="2d230-545">numero univoco di registrazione</span><span class="sxs-lookup"><span data-stu-id="2d230-545">unique registration number</span></span>
  
<span data-ttu-id="2d230-546">numero di identificazione univoco</span><span class="sxs-lookup"><span data-stu-id="2d230-546">unique identity number</span></span>
  
<span data-ttu-id="2d230-547">uniqueidentityno #</span><span class="sxs-lookup"><span data-stu-id="2d230-547">uniqueidentityno#</span></span>
  
<span data-ttu-id="2d230-548">numero univoco cittadini master</span><span class="sxs-lookup"><span data-stu-id="2d230-548">unique master citizen number</span></span>
  
<span data-ttu-id="2d230-549">edinstvena identifikacijska številka</span><span class="sxs-lookup"><span data-stu-id="2d230-549">edinstvena identifikacijska številka</span></span>
  
<span data-ttu-id="2d230-550">uniqueidentityno #</span><span class="sxs-lookup"><span data-stu-id="2d230-550">uniqueidentityno #</span></span>
  
<span data-ttu-id="2d230-551">edinstvena številka glavnega državljana</span><span class="sxs-lookup"><span data-stu-id="2d230-551">edinstvena številka glavnega državljana</span></span>
  
<span data-ttu-id="2d230-552">emšo</span><span class="sxs-lookup"><span data-stu-id="2d230-552">emšo</span></span>
  
## <a name="spain"></a><span data-ttu-id="2d230-553">Spagna</span><span class="sxs-lookup"><span data-stu-id="2d230-553">Spain</span></span>

### <a name="format"></a><span data-ttu-id="2d230-554">Formato</span><span class="sxs-lookup"><span data-stu-id="2d230-554">Format</span></span>

<span data-ttu-id="2d230-555">Sette cifre seguite da un carattere</span><span class="sxs-lookup"><span data-stu-id="2d230-555">Seven digits followed by one character</span></span>
  
### <a name="pattern"></a><span data-ttu-id="2d230-556">Modello</span><span class="sxs-lookup"><span data-stu-id="2d230-556">Pattern</span></span>

<span data-ttu-id="2d230-557">Sette cifre seguite da un carattere</span><span class="sxs-lookup"><span data-stu-id="2d230-557">Seven digits followed by one character</span></span>
  
- <span data-ttu-id="2d230-558">Sette cifre</span><span class="sxs-lookup"><span data-stu-id="2d230-558">Seven digits</span></span>
    
- <span data-ttu-id="2d230-559">Una cifra o lettere (maiuscole o minuscole)</span><span class="sxs-lookup"><span data-stu-id="2d230-559">One digit or letter (not case-sensitive)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="2d230-560">Checksum</span><span class="sxs-lookup"><span data-stu-id="2d230-560">Checksum</span></span>

<span data-ttu-id="2d230-561">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="2d230-561">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="2d230-562">Definizione</span><span class="sxs-lookup"><span data-stu-id="2d230-562">Definition</span></span>

<span data-ttu-id="2d230-563">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="2d230-563">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="2d230-564">L'espressione regolare `Regex_spain_eu_national_id_card` consente di trovare contenuto corrispondente al formato.</span><span class="sxs-lookup"><span data-stu-id="2d230-564">The regular expression  `Regex_spain_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="2d230-565">Una parola chiave da `Keywords_spain_eu_national_id_card"` viene trovato.</span><span class="sxs-lookup"><span data-stu-id="2d230-565">A keyword from  `Keywords_spain_eu_national_id_card"` is found.</span></span> 
    
```
 
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_spain_eu_national_id_card" />
          <Match idRef="Keywords_spain_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="2d230-566">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="2d230-566">Keywords</span></span>

#### <a name="keywordsspaineunationalidcard"></a><span data-ttu-id="2d230-567">Keywords_spain_eu_national_id_card</span><span class="sxs-lookup"><span data-stu-id="2d230-567">Keywords_spain_eu_national_id_card</span></span>

<span data-ttu-id="2d230-568">DNI</span><span class="sxs-lookup"><span data-stu-id="2d230-568">dni</span></span>
  
<span data-ttu-id="2d230-569">numero identificativo nazionale</span><span class="sxs-lookup"><span data-stu-id="2d230-569">national identification number</span></span>
  
<span data-ttu-id="2d230-570">numero di identità nazionale</span><span class="sxs-lookup"><span data-stu-id="2d230-570">national identity number</span></span>
  
<span data-ttu-id="2d230-571">numero di assicurazione</span><span class="sxs-lookup"><span data-stu-id="2d230-571">insurance number</span></span>
  
<span data-ttu-id="2d230-572">numero di identificazione personale</span><span class="sxs-lookup"><span data-stu-id="2d230-572">personal identification number</span></span>
  
<span data-ttu-id="2d230-573">identità nazionale</span><span class="sxs-lookup"><span data-stu-id="2d230-573">national identity</span></span>
  
<span data-ttu-id="2d230-574">identità personale non</span><span class="sxs-lookup"><span data-stu-id="2d230-574">personal identity no</span></span>
  
<span data-ttu-id="2d230-575">numero di identificazione univoco</span><span class="sxs-lookup"><span data-stu-id="2d230-575">unique identity number</span></span>
  
<span data-ttu-id="2d230-576">nationalidno #</span><span class="sxs-lookup"><span data-stu-id="2d230-576">nationalidno#</span></span>
  
<span data-ttu-id="2d230-577">UniqueID #</span><span class="sxs-lookup"><span data-stu-id="2d230-577">uniqueid#</span></span>
  
<span data-ttu-id="2d230-578">DNI #</span><span class="sxs-lookup"><span data-stu-id="2d230-578">dni#</span></span>
  
<span data-ttu-id="2d230-579">nationalid #</span><span class="sxs-lookup"><span data-stu-id="2d230-579">nationalid#</span></span>
  
<span data-ttu-id="2d230-580">NIE #</span><span class="sxs-lookup"><span data-stu-id="2d230-580">nie#</span></span>
  
<span data-ttu-id="2d230-581">NIE</span><span class="sxs-lookup"><span data-stu-id="2d230-581">nie</span></span>
  
<span data-ttu-id="2d230-582">nienúmero #</span><span class="sxs-lookup"><span data-stu-id="2d230-582">nienúmero#</span></span>
  
<span data-ttu-id="2d230-583">número NIE</span><span class="sxs-lookup"><span data-stu-id="2d230-583">nie número</span></span>
  
<span data-ttu-id="2d230-584">documento nacional de identidad</span><span class="sxs-lookup"><span data-stu-id="2d230-584">documento nacional de identidad</span></span>
  
<span data-ttu-id="2d230-585">identidad único</span><span class="sxs-lookup"><span data-stu-id="2d230-585">identidad único</span></span>
  
<span data-ttu-id="2d230-586">número nacional identidad</span><span class="sxs-lookup"><span data-stu-id="2d230-586">número nacional identidad</span></span>
  
<span data-ttu-id="2d230-587">DNI número</span><span class="sxs-lookup"><span data-stu-id="2d230-587">dni número</span></span>
  
<span data-ttu-id="2d230-588">dninúmero #</span><span class="sxs-lookup"><span data-stu-id="2d230-588">dninúmero#</span></span>
  
<span data-ttu-id="2d230-589">identidadúnico #</span><span class="sxs-lookup"><span data-stu-id="2d230-589">identidadúnico#</span></span>
  
## <a name="sweden"></a><span data-ttu-id="2d230-590">Svezia</span><span class="sxs-lookup"><span data-stu-id="2d230-590">Sweden</span></span>

<span data-ttu-id="2d230-591">Per ulteriori informazioni, vedere la sezione "Svezia-identificativo nazionale" in [cercare il quali i tipi di informazioni riservate](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="2d230-591">For details, see the section "Sweden National ID" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="2d230-592">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2d230-592">See also</span></span>

[<span data-ttu-id="2d230-593">Cosa individuano i tipi di informazioni riservate</span><span class="sxs-lookup"><span data-stu-id="2d230-593">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)

