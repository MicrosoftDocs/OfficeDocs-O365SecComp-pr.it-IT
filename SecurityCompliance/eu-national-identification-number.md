---
title: Numero di identificazione nazionale dell'Unione europea
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 8/17/2018
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
description: In questo argomento viene illustrato l'aspetto di un criterio di prevenzione della perdita di dati (DLP) quando viene rilevato il tipo di informazioni riservate del numero di identificazione nazionale dell'Unione europea. Questo tipo di informazioni riservate definisce modelli, parole chiave e altre evidenze diverse per ogni paese.
ms.openlocfilehash: 205019d040648f0600f3dbf4403063edf9f31c41
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/17/2019
ms.locfileid: "34154460"
---
# <a name="eu-national-identification-number"></a><span data-ttu-id="9cf52-104">Numero di identificazione nazionale dell'Unione europea</span><span class="sxs-lookup"><span data-stu-id="9cf52-104">EU National Identification Number</span></span>

<span data-ttu-id="9cf52-105">In questo argomento viene illustrato l'aspetto di un criterio di prevenzione della perdita di dati (DLP) quando viene rilevato il tipo di informazioni riservate del numero di identificazione nazionale dell'Unione europea.</span><span class="sxs-lookup"><span data-stu-id="9cf52-105">This topic shows what a data loss prevention (DLP) policy looks for when it detects the EU National Identification Number sensitive information type.</span></span> <span data-ttu-id="9cf52-106">Questo tipo di informazioni riservate definisce modelli, parole chiave e altre evidenze diverse per ogni paese.</span><span class="sxs-lookup"><span data-stu-id="9cf52-106">This sensitive information type defines different patterns, keywords, and other evidence for each country.</span></span>
  
## <a name="austria"></a><span data-ttu-id="9cf52-107">Austria</span><span class="sxs-lookup"><span data-stu-id="9cf52-107">Austria</span></span>

### <a name="format"></a><span data-ttu-id="9cf52-108">Formato</span><span class="sxs-lookup"><span data-stu-id="9cf52-108">Format</span></span>

<span data-ttu-id="9cf52-109">Combinazione a 24 caratteri di lettere, cifre e caratteri speciali</span><span class="sxs-lookup"><span data-stu-id="9cf52-109">A 24-character combination of letters, digits, and special characters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="9cf52-110">Modello</span><span class="sxs-lookup"><span data-stu-id="9cf52-110">Pattern</span></span>

<span data-ttu-id="9cf52-111">24 caratteri:</span><span class="sxs-lookup"><span data-stu-id="9cf52-111">24 characters:</span></span>
  
-  <span data-ttu-id="9cf52-112">22 lettere (senza distinzione tra maiuscole e minuscole), cifre, barre rovesciate, barre o segni più</span><span class="sxs-lookup"><span data-stu-id="9cf52-112">22 letters (not case-sensitive), digits, backslashes, forward slashes, or plus signs</span></span> 
    
- <span data-ttu-id="9cf52-113">Due lettere (senza distinzione tra maiuscole e minuscole), cifre, barre rovesciate, barre, segni più o segni uguali</span><span class="sxs-lookup"><span data-stu-id="9cf52-113">Two letters (not case-sensitive), digits, backslashes, forward slashes, plus signs, or equal signs</span></span>
    
### <a name="checksum"></a><span data-ttu-id="9cf52-114">Checksum</span><span class="sxs-lookup"><span data-stu-id="9cf52-114">Checksum</span></span>

<span data-ttu-id="9cf52-115">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="9cf52-115">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="9cf52-116">Definizione</span><span class="sxs-lookup"><span data-stu-id="9cf52-116">Definition</span></span>

<span data-ttu-id="9cf52-117">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="9cf52-117">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="9cf52-118">L'espressione `Regex_austria_eu_national_id_card` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="9cf52-118">The regular expression  `Regex_austria_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="9cf52-119">Viene trovata una `Keywords_austria_eu_national_id_card` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="9cf52-119">A keyword from  `Keywords_austria_eu_national_id_card` is found.</span></span> 
    
```
 
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_austria_eu_national_id_card" />
          <Match idRef="Keywords_austria_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="9cf52-120">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="9cf52-120">Keywords</span></span>

#### <a name="keywordsaustriaeunationalidcard"></a><span data-ttu-id="9cf52-121">Keywords_austria_eu_national_id_card</span><span class="sxs-lookup"><span data-stu-id="9cf52-121">Keywords_austria_eu_national_id_card</span></span>

<span data-ttu-id="9cf52-122">numero d'identità austriaco</span><span class="sxs-lookup"><span data-stu-id="9cf52-122">austrian identity number</span></span>
  
<span data-ttu-id="9cf52-123">numero di identità nazionale</span><span class="sxs-lookup"><span data-stu-id="9cf52-123">national identity number</span></span>
  
<span data-ttu-id="9cf52-124">numero di identità</span><span class="sxs-lookup"><span data-stu-id="9cf52-124">identity number</span></span>
  
<span data-ttu-id="9cf52-125">national id</span><span class="sxs-lookup"><span data-stu-id="9cf52-125">national id</span></span>
  
<span data-ttu-id="9cf52-126">Personalausweis Republik Österreich</span><span class="sxs-lookup"><span data-stu-id="9cf52-126">personalausweis republik österreich</span></span>
  
## <a name="belgium"></a><span data-ttu-id="9cf52-127">Belgio</span><span class="sxs-lookup"><span data-stu-id="9cf52-127">Belgium</span></span>

<span data-ttu-id="9cf52-128">Per informazioni dettagliate, vedere la sezione "numero nazionale belga" in [che cosa cercano i tipi di informazioni riservate](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="9cf52-128">For details, see the section "Belgium National Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="bulgaria"></a><span data-ttu-id="9cf52-129">Bulgaria</span><span class="sxs-lookup"><span data-stu-id="9cf52-129">Bulgaria</span></span>

### <a name="format"></a><span data-ttu-id="9cf52-130">Formato</span><span class="sxs-lookup"><span data-stu-id="9cf52-130">Format</span></span>

<span data-ttu-id="9cf52-131">Dieci cifre senza spazi e delimitatori</span><span class="sxs-lookup"><span data-stu-id="9cf52-131">Ten digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="9cf52-132">Modello</span><span class="sxs-lookup"><span data-stu-id="9cf52-132">Pattern</span></span>

<span data-ttu-id="9cf52-133">Dieci cifre senza spazi e delimitatori</span><span class="sxs-lookup"><span data-stu-id="9cf52-133">Ten digits without spaces and delimiters</span></span>
  
-  <span data-ttu-id="9cf52-134">Sei cifre che corrispondono alla data di nascita (AAMMGG)</span><span class="sxs-lookup"><span data-stu-id="9cf52-134">Six digits that correspond to the birth date (YYMMDD)</span></span> 
    
- <span data-ttu-id="9cf52-135">Due cifre che corrispondono all'ordine di nascita</span><span class="sxs-lookup"><span data-stu-id="9cf52-135">Two digits that correspond to the birth order</span></span>
    
- <span data-ttu-id="9cf52-136">Una cifra che corrisponde al sesso: una cifra pari per il maschio e una cifra dispari per la femmina</span><span class="sxs-lookup"><span data-stu-id="9cf52-136">One digit that corresponds to gender: An even digit for male and an odd digit for female</span></span>
    
- <span data-ttu-id="9cf52-137">Una cifra di controllo</span><span class="sxs-lookup"><span data-stu-id="9cf52-137">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="9cf52-138">Checksum</span><span class="sxs-lookup"><span data-stu-id="9cf52-138">Checksum</span></span>

<span data-ttu-id="9cf52-139">Sì</span><span class="sxs-lookup"><span data-stu-id="9cf52-139">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="9cf52-140">Definizione</span><span class="sxs-lookup"><span data-stu-id="9cf52-140">Definition</span></span>

<span data-ttu-id="9cf52-141">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="9cf52-141">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="9cf52-142">La funzione `Func_bulgaria_national_number` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="9cf52-142">The function  `Func_bulgaria_national_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="9cf52-143">Viene trovata una `Keywords_bulgaria_national_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="9cf52-143">A keyword from  `Keywords_bulgaria_national_number` is found.</span></span> 
    
<span data-ttu-id="9cf52-144">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="9cf52-144">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="9cf52-145">La funzione `Func_bulgaria_national_number` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="9cf52-145">The function  `Func_bulgaria_national_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="9cf52-146">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="9cf52-146">Keywords</span></span>

#### <a name="keywordsbulgarianationalnumber"></a><span data-ttu-id="9cf52-147">Keywords_bulgaria_national_number</span><span class="sxs-lookup"><span data-stu-id="9cf52-147">Keywords_bulgaria_national_number</span></span>

<span data-ttu-id="9cf52-148">EGN</span><span class="sxs-lookup"><span data-stu-id="9cf52-148">egn</span></span>
  
<span data-ttu-id="9cf52-149">EGN</span><span class="sxs-lookup"><span data-stu-id="9cf52-149">egn#</span></span>
  
<span data-ttu-id="9cf52-150">numero nazionale bulgaro</span><span class="sxs-lookup"><span data-stu-id="9cf52-150">bulgarian national number</span></span>
  
<span data-ttu-id="9cf52-151">numero nazionale</span><span class="sxs-lookup"><span data-stu-id="9cf52-151">national number</span></span>
  
<span data-ttu-id="9cf52-152">social security number</span><span class="sxs-lookup"><span data-stu-id="9cf52-152">social security number</span></span>
  
<span data-ttu-id="9cf52-153">nationalnumber#</span><span class="sxs-lookup"><span data-stu-id="9cf52-153">nationalnumber#</span></span>
  
<span data-ttu-id="9cf52-154">SSN</span><span class="sxs-lookup"><span data-stu-id="9cf52-154">ssn#</span></span>
  
<span data-ttu-id="9cf52-155">SSN</span><span class="sxs-lookup"><span data-stu-id="9cf52-155">ssn</span></span>
  
<span data-ttu-id="9cf52-156">nationalnumber</span><span class="sxs-lookup"><span data-stu-id="9cf52-156">nationalnumber</span></span>
  
<span data-ttu-id="9cf52-157">BNN</span><span class="sxs-lookup"><span data-stu-id="9cf52-157">bnn#</span></span>
  
<span data-ttu-id="9cf52-158">BNN</span><span class="sxs-lookup"><span data-stu-id="9cf52-158">bnn</span></span>
  
<span data-ttu-id="9cf52-159">numero ID personale</span><span class="sxs-lookup"><span data-stu-id="9cf52-159">personal id number</span></span>
  
<span data-ttu-id="9cf52-160">personalidnumber#</span><span class="sxs-lookup"><span data-stu-id="9cf52-160">personalidnumber#</span></span>
  
<span data-ttu-id="9cf52-161">единен граждански номер</span><span class="sxs-lookup"><span data-stu-id="9cf52-161">единен граждански номер</span></span>
  
<span data-ttu-id="9cf52-162">grazhdanski nomer</span><span class="sxs-lookup"><span data-stu-id="9cf52-162">edinen grazhdanski nomer</span></span>
  
<span data-ttu-id="9cf52-163">егн</span><span class="sxs-lookup"><span data-stu-id="9cf52-163">егн</span></span>
  
<span data-ttu-id="9cf52-164">егн#</span><span class="sxs-lookup"><span data-stu-id="9cf52-164">егн#</span></span>
  
## <a name="croatia"></a><span data-ttu-id="9cf52-165">Croazia</span><span class="sxs-lookup"><span data-stu-id="9cf52-165">Croatia</span></span>

<span data-ttu-id="9cf52-166">Per informazioni dettagliate, vedere la sezione "numero di identità della Croazia" in [che cosa cercano i tipi di informazioni riservate](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="9cf52-166">For details, see the section "Croatia Identity Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="cyprus"></a><span data-ttu-id="9cf52-167">Cipro</span><span class="sxs-lookup"><span data-stu-id="9cf52-167">Cyprus</span></span>

### <a name="format"></a><span data-ttu-id="9cf52-168">Formato</span><span class="sxs-lookup"><span data-stu-id="9cf52-168">Format</span></span>

<span data-ttu-id="9cf52-169">Dieci cifre senza spazi e delimitatori</span><span class="sxs-lookup"><span data-stu-id="9cf52-169">Ten digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="9cf52-170">Modello</span><span class="sxs-lookup"><span data-stu-id="9cf52-170">Pattern</span></span>

 <span data-ttu-id="9cf52-171">Dieci cifre</span><span class="sxs-lookup"><span data-stu-id="9cf52-171">Ten digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="9cf52-172">Checksum</span><span class="sxs-lookup"><span data-stu-id="9cf52-172">Checksum</span></span>

<span data-ttu-id="9cf52-173">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="9cf52-173">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="9cf52-174">Definizione</span><span class="sxs-lookup"><span data-stu-id="9cf52-174">Definition</span></span>

<span data-ttu-id="9cf52-175">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="9cf52-175">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="9cf52-176">L'espressione `Regex_cyprus_eu_national_id_card` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="9cf52-176">The regular expression  `Regex_cyprus_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="9cf52-177">Viene trovata una `Keywords_cyprus_eu_national_id_card` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="9cf52-177">A keyword from  `Keywords_cyprus_eu_national_id_card` is found.</span></span> 
    
```
 
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_cyprus_eu_national_id_card" />
          <Match idRef="Keywords_cyprus_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="9cf52-178">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="9cf52-178">Keywords</span></span>

#### <a name="keywordscypruseunationalidcard"></a><span data-ttu-id="9cf52-179">Keywords_cyprus_eu_national_id_card</span><span class="sxs-lookup"><span data-stu-id="9cf52-179">Keywords_cyprus_eu_national_id_card</span></span>

<span data-ttu-id="9cf52-180">numero di carta di identità</span><span class="sxs-lookup"><span data-stu-id="9cf52-180">id card number</span></span>
  
<span data-ttu-id="9cf52-181">national identification number</span><span class="sxs-lookup"><span data-stu-id="9cf52-181">national identification number</span></span>
  
<span data-ttu-id="9cf52-182">numero ID personale</span><span class="sxs-lookup"><span data-stu-id="9cf52-182">personal id number</span></span>
  
<span data-ttu-id="9cf52-183">numero di carta di identità</span><span class="sxs-lookup"><span data-stu-id="9cf52-183">identity card number</span></span>
  
<span data-ttu-id="9cf52-184">ταυτοτητασ</span><span class="sxs-lookup"><span data-stu-id="9cf52-184">ταυτοτητασ</span></span>
  
## <a name="czech-republic"></a><span data-ttu-id="9cf52-185">Repubblica Ceca</span><span class="sxs-lookup"><span data-stu-id="9cf52-185">Czech Republic</span></span>

<span data-ttu-id="9cf52-186">Per informazioni dettagliate, vedere la sezione "numero di identità nazionale ceco" in [quello che i tipi di informazioni riservate cercano](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="9cf52-186">For details, see the section "Czech National Identity Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="denmark"></a><span data-ttu-id="9cf52-187">Danimarca</span><span class="sxs-lookup"><span data-stu-id="9cf52-187">Denmark</span></span>

<span data-ttu-id="9cf52-188">Per informazioni dettagliate, vedere la sezione "numero di identificazione personale danese" in [che cosa cercano i tipi di informazioni riservate](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="9cf52-188">For details, see the section "Denmark Personal Identification Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="estonia"></a><span data-ttu-id="9cf52-189">Estonia</span><span class="sxs-lookup"><span data-stu-id="9cf52-189">Estonia</span></span>

### <a name="format"></a><span data-ttu-id="9cf52-190">Formato</span><span class="sxs-lookup"><span data-stu-id="9cf52-190">Format</span></span>

<span data-ttu-id="9cf52-191">11 cifre senza spazi e delimitatori</span><span class="sxs-lookup"><span data-stu-id="9cf52-191">11 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="9cf52-192">Modello</span><span class="sxs-lookup"><span data-stu-id="9cf52-192">Pattern</span></span>

<span data-ttu-id="9cf52-193">11 cifre:</span><span class="sxs-lookup"><span data-stu-id="9cf52-193">11 digits:</span></span>
  
- <span data-ttu-id="9cf52-194">Una cifra che corrisponde al sesso e al secolo di nascita (numero dispari maschio, anche numero femmina; 1-2: XIX secolo; 3-4: XX secolo; 5-6: XXI secolo)</span><span class="sxs-lookup"><span data-stu-id="9cf52-194">One digit that corresponds to sex and century of birth (odd number male, even number female; 1-2: 19th century; 3-4: 20th century; 5-6: 21st century)</span></span>
    
- <span data-ttu-id="9cf52-195">Sei cifre che corrispondono alla data di nascita (AAMMGG)</span><span class="sxs-lookup"><span data-stu-id="9cf52-195">Six digits that correspond to date of birth (YYMMDD)</span></span>
    
- <span data-ttu-id="9cf52-196">Tre cifre che corrispondono a un numero di serie che separa le persone nate nella stessa data</span><span class="sxs-lookup"><span data-stu-id="9cf52-196">Three digits that correspond to a serial number separating persons born on the same date</span></span>
    
- <span data-ttu-id="9cf52-197">Una cifra di controllo</span><span class="sxs-lookup"><span data-stu-id="9cf52-197">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="9cf52-198">Checksum</span><span class="sxs-lookup"><span data-stu-id="9cf52-198">Checksum</span></span>

<span data-ttu-id="9cf52-199">Sì</span><span class="sxs-lookup"><span data-stu-id="9cf52-199">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="9cf52-200">Definizione</span><span class="sxs-lookup"><span data-stu-id="9cf52-200">Definition</span></span>

<span data-ttu-id="9cf52-201">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="9cf52-201">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="9cf52-202">La funzione `Func_estonia_eu_national_id_card` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="9cf52-202">The function  `Func_estonia_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="9cf52-203">Viene trovata una `Keywords_estonia_eu_national_id_card` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="9cf52-203">A keyword from  `Keywords_estonia_eu_national_id_card` is found.</span></span> 
    
<span data-ttu-id="9cf52-204">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="9cf52-204">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="9cf52-205">La funzione `Func_estonia_eu_national_id_card` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="9cf52-205">The function  `Func_estonia_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="9cf52-206">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="9cf52-206">Keywords</span></span>

#### <a name="keywordsestoniaeunationalidcard"></a><span data-ttu-id="9cf52-207">Keywords_estonia_eu_national_id_card</span><span class="sxs-lookup"><span data-stu-id="9cf52-207">Keywords_estonia_eu_national_id_card</span></span>

<span data-ttu-id="9cf52-208">codice di identificazione personale</span><span class="sxs-lookup"><span data-stu-id="9cf52-208">personal identification code</span></span>
  
<span data-ttu-id="9cf52-209">numero di identificazione personale</span><span class="sxs-lookup"><span data-stu-id="9cf52-209">personal identification number</span></span>
  
<span data-ttu-id="9cf52-210">national identification number</span><span class="sxs-lookup"><span data-stu-id="9cf52-210">national identification number</span></span>
  
<span data-ttu-id="9cf52-211">numero nazionale</span><span class="sxs-lookup"><span data-stu-id="9cf52-211">national number</span></span>
  
<span data-ttu-id="9cf52-212">numero ID personale</span><span class="sxs-lookup"><span data-stu-id="9cf52-212">personal id number</span></span>
  
<span data-ttu-id="9cf52-213">personalidnumber#</span><span class="sxs-lookup"><span data-stu-id="9cf52-213">personalidnumber#</span></span>
  
<span data-ttu-id="9cf52-214">IK</span><span class="sxs-lookup"><span data-stu-id="9cf52-214">ik</span></span>
  
<span data-ttu-id="9cf52-215">isikukood</span><span class="sxs-lookup"><span data-stu-id="9cf52-215">isikukood</span></span>
  
<span data-ttu-id="9cf52-216">ID-kaart</span><span class="sxs-lookup"><span data-stu-id="9cf52-216">id-kaart</span></span>
  
## <a name="finland"></a><span data-ttu-id="9cf52-217">Finlandia</span><span class="sxs-lookup"><span data-stu-id="9cf52-217">Finland</span></span>

<span data-ttu-id="9cf52-218">Per informazioni dettagliate, vedere la sezione "Finlandia National ID" in [quello che i tipi di informazioni riservate cercano](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="9cf52-218">For details, see the section "Finland National ID" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="france"></a><span data-ttu-id="9cf52-219">Francia</span><span class="sxs-lookup"><span data-stu-id="9cf52-219">France</span></span>

<span data-ttu-id="9cf52-220">Per informazioni dettagliate, vedere la sezione "Francia National ID Card (CNI)" in [che cosa cercano i tipi di informazioni riservate](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="9cf52-220">For details, see the section "France National ID Card (CNI)" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="germany"></a><span data-ttu-id="9cf52-221">Germania</span><span class="sxs-lookup"><span data-stu-id="9cf52-221">Germany</span></span>

<span data-ttu-id="9cf52-222">Per informazioni dettagliate, vedere la sezione "Germania identità numero di carta" in [che cosa cercano i tipi di informazioni riservate](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="9cf52-222">For details, see the section "Germany Identity Card Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="greece"></a><span data-ttu-id="9cf52-223">Grecia</span><span class="sxs-lookup"><span data-stu-id="9cf52-223">Greece</span></span>

<span data-ttu-id="9cf52-224">Per informazioni dettagliate, vedere la sezione "Grecia National ID Card" in [quello che cercano i tipi di informazioni riservate](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="9cf52-224">For details, see the section "Greece National ID Card" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="hungary"></a><span data-ttu-id="9cf52-225">Ungheria</span><span class="sxs-lookup"><span data-stu-id="9cf52-225">Hungary</span></span>

### <a name="format"></a><span data-ttu-id="9cf52-226">Formato</span><span class="sxs-lookup"><span data-stu-id="9cf52-226">Format</span></span>

<span data-ttu-id="9cf52-227">11 cifre</span><span class="sxs-lookup"><span data-stu-id="9cf52-227">11 digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="9cf52-228">Modello</span><span class="sxs-lookup"><span data-stu-id="9cf52-228">Pattern</span></span>

<span data-ttu-id="9cf52-229">11 cifre:</span><span class="sxs-lookup"><span data-stu-id="9cf52-229">11 digits:</span></span>
  
-  <span data-ttu-id="9cf52-230">Una cifra che corrisponde al sesso (1-maschio, 2-Femmina, altri numeri sono possibili anche per i cittadini nati prima del 1900 o cittadini con doppia cittadinanza)</span><span class="sxs-lookup"><span data-stu-id="9cf52-230">One digit that corresponds to gender (1-male, 2-female, other numbers are also possible for citizens born before 1900 or citizens with double citizenship)</span></span> 
    
- <span data-ttu-id="9cf52-231">Sei cifre che corrispondono alla data di nascita (AAMMGG)</span><span class="sxs-lookup"><span data-stu-id="9cf52-231">Six digits that correspond to birth date (YYMMDD)</span></span>
    
- <span data-ttu-id="9cf52-232">Tre cifre che corrispondono a un numero di serie</span><span class="sxs-lookup"><span data-stu-id="9cf52-232">Three digits that correspond to a serial number</span></span>
    
- <span data-ttu-id="9cf52-233">Una cifra di controllo</span><span class="sxs-lookup"><span data-stu-id="9cf52-233">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="9cf52-234">Checksum</span><span class="sxs-lookup"><span data-stu-id="9cf52-234">Checksum</span></span>

<span data-ttu-id="9cf52-235">Sì</span><span class="sxs-lookup"><span data-stu-id="9cf52-235">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="9cf52-236">Definizione</span><span class="sxs-lookup"><span data-stu-id="9cf52-236">Definition</span></span>

<span data-ttu-id="9cf52-237">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="9cf52-237">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="9cf52-238">La funzione `Func_hungary_eu_national_id_card` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="9cf52-238">The function  `Func_hungary_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="9cf52-239">Viene trovata una `Keywords_hungary_eu_national_id_card` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="9cf52-239">A keyword from  `Keywords_hungary_eu_national_id_card` is found.</span></span> 
    
<span data-ttu-id="9cf52-240">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="9cf52-240">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="9cf52-241">La funzione `Func_hungary_eu_national_id_card` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="9cf52-241">The function  `Func_hungary_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="9cf52-242">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="9cf52-242">Keywords</span></span>

#### <a name="keywordshungaryeunationalidcard"></a><span data-ttu-id="9cf52-243">Keywords_hungary_eu_national_id_card</span><span class="sxs-lookup"><span data-stu-id="9cf52-243">Keywords_hungary_eu_national_id_card</span></span>

<span data-ttu-id="9cf52-244">numero di identificazione personale</span><span class="sxs-lookup"><span data-stu-id="9cf52-244">personal identification number</span></span>
  
<span data-ttu-id="9cf52-245">identification number</span><span class="sxs-lookup"><span data-stu-id="9cf52-245">identification number</span></span>
  
<span data-ttu-id="9cf52-246">numero ID personale</span><span class="sxs-lookup"><span data-stu-id="9cf52-246">personal id number</span></span>
  
<span data-ttu-id="9cf52-247">személyazonosító igazolvány</span><span class="sxs-lookup"><span data-stu-id="9cf52-247">személyazonosító igazolvány</span></span>
  
## <a name="ireland"></a><span data-ttu-id="9cf52-248">Irlanda</span><span class="sxs-lookup"><span data-stu-id="9cf52-248">Ireland</span></span>

### <a name="format"></a><span data-ttu-id="9cf52-249">Formato</span><span class="sxs-lookup"><span data-stu-id="9cf52-249">Format</span></span>

<span data-ttu-id="9cf52-250">Una combinazione di nove caratteri di lettere, cifre e uno spazio nel modello specificato</span><span class="sxs-lookup"><span data-stu-id="9cf52-250">A nine-character combination of letters, digits, and a space in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="9cf52-251">Modello</span><span class="sxs-lookup"><span data-stu-id="9cf52-251">Pattern</span></span>

<span data-ttu-id="9cf52-252">Una combinazione di nove caratteri di lettere, cifre e uno spazio nel modello specificato</span><span class="sxs-lookup"><span data-stu-id="9cf52-252">A nine-character combination of letters, digits, and a space in the specified pattern</span></span>
  
<span data-ttu-id="9cf52-253">Dal 01 gennaio 2013 a oggi:</span><span class="sxs-lookup"><span data-stu-id="9cf52-253">From 01 January 2013 to now:</span></span>
  
-  <span data-ttu-id="9cf52-254">Sette cifre</span><span class="sxs-lookup"><span data-stu-id="9cf52-254">Seven digits</span></span> 
    
- <span data-ttu-id="9cf52-255">Una cifra di controllo</span><span class="sxs-lookup"><span data-stu-id="9cf52-255">One check digit</span></span>
    
- <span data-ttu-id="9cf52-256">Uno spazio o la lettera maiuscola "W" (distinzione tra maiuscole e minuscole)</span><span class="sxs-lookup"><span data-stu-id="9cf52-256">One space or the uppercase letter "W" (Case sensitive)</span></span>
    
<span data-ttu-id="9cf52-257">Prima del 1 ° gennaio 2013:</span><span class="sxs-lookup"><span data-stu-id="9cf52-257">Prior to 01 January 2013:</span></span>
  
-  <span data-ttu-id="9cf52-258">Sette cifre</span><span class="sxs-lookup"><span data-stu-id="9cf52-258">Seven digits</span></span> 
    
- <span data-ttu-id="9cf52-259">Una cifra di controllo</span><span class="sxs-lookup"><span data-stu-id="9cf52-259">One check digit</span></span>
    
- <span data-ttu-id="9cf52-260">Uno spazio o una lettera maiuscola (distinzione tra maiuscole e minuscole)</span><span class="sxs-lookup"><span data-stu-id="9cf52-260">One space or an uppercase letter (Case sensitive)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="9cf52-261">Checksum</span><span class="sxs-lookup"><span data-stu-id="9cf52-261">Checksum</span></span>

<span data-ttu-id="9cf52-262">Sì</span><span class="sxs-lookup"><span data-stu-id="9cf52-262">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="9cf52-263">Definizione</span><span class="sxs-lookup"><span data-stu-id="9cf52-263">Definition</span></span>

<span data-ttu-id="9cf52-264">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="9cf52-264">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="9cf52-265">La funzione trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="9cf52-265">The function finds content that matches the pattern.</span></span>
    
- <span data-ttu-id="9cf52-266">Viene trovata una parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="9cf52-266">A keyword from is found.</span></span>
    
<span data-ttu-id="9cf52-267">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="9cf52-267">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="9cf52-268">La funzione trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="9cf52-268">The function finds content that matches the pattern.</span></span>
    
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

### <a name="keywords"></a><span data-ttu-id="9cf52-269">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="9cf52-269">Keywords</span></span>

#### <a name="keywordsirelandeunationalidcard"></a><span data-ttu-id="9cf52-270">Keywords_ireland_eu_national_id_card</span><span class="sxs-lookup"><span data-stu-id="9cf52-270">Keywords_ireland_eu_national_id_card</span></span>

<span data-ttu-id="9cf52-271">numero di servizio pubblico personale</span><span class="sxs-lookup"><span data-stu-id="9cf52-271">personal public service number</span></span>
  
<span data-ttu-id="9cf52-272">PPS No</span><span class="sxs-lookup"><span data-stu-id="9cf52-272">pps no</span></span>
  
<span data-ttu-id="9cf52-273">reddito e numero di previdenza sociale</span><span class="sxs-lookup"><span data-stu-id="9cf52-273">revenue and social insurance number</span></span>
  
<span data-ttu-id="9cf52-274">RSI No</span><span class="sxs-lookup"><span data-stu-id="9cf52-274">rsi no</span></span>
  
<span data-ttu-id="9cf52-275">numero di identificazione personale</span><span class="sxs-lookup"><span data-stu-id="9cf52-275">personal identification number</span></span>
  
<span data-ttu-id="9cf52-276">identification number</span><span class="sxs-lookup"><span data-stu-id="9cf52-276">identification number</span></span>
  
<span data-ttu-id="9cf52-277">numero ID personale</span><span class="sxs-lookup"><span data-stu-id="9cf52-277">personal id number</span></span>
  
<span data-ttu-id="9cf52-278">uimhir phearsanta seirbhíse poiblí</span><span class="sxs-lookup"><span data-stu-id="9cf52-278">uimhir phearsanta seirbhíse poiblí</span></span>
  
<span data-ttu-id="9cf52-279">uimh.</span><span class="sxs-lookup"><span data-stu-id="9cf52-279">uimh.</span></span> <span data-ttu-id="9cf52-280">PSP</span><span class="sxs-lookup"><span data-stu-id="9cf52-280">psp</span></span>
  
## <a name="italy"></a><span data-ttu-id="9cf52-281">Italia</span><span class="sxs-lookup"><span data-stu-id="9cf52-281">Italy</span></span>

### <a name="format"></a><span data-ttu-id="9cf52-282">Formato</span><span class="sxs-lookup"><span data-stu-id="9cf52-282">Format</span></span>

<span data-ttu-id="9cf52-283">Una combinazione di 16 caratteri di lettere e cifre nel modello specificato</span><span class="sxs-lookup"><span data-stu-id="9cf52-283">A 16-character combination of letters and digits in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="9cf52-284">Modello</span><span class="sxs-lookup"><span data-stu-id="9cf52-284">Pattern</span></span>

<span data-ttu-id="9cf52-285">Combinazione di lettere e cifre di 16 caratteri:</span><span class="sxs-lookup"><span data-stu-id="9cf52-285">A 16-character combination of letters and digits:</span></span>
  
- <span data-ttu-id="9cf52-286">Tre lettere che corrispondono alle prime tre consonanti del nome di famiglia</span><span class="sxs-lookup"><span data-stu-id="9cf52-286">Three letters that correspond to the first three consonants in the family name</span></span>
    
- <span data-ttu-id="9cf52-287">Tre lettere che corrispondono alla prima, terza e quarta consonante del primo nome</span><span class="sxs-lookup"><span data-stu-id="9cf52-287">Three letters that correspond to the first, third, and fourth consonants in the first name</span></span>
    
- <span data-ttu-id="9cf52-288">Due cifre che corrispondono alle ultime cifre dell'anno di nascita</span><span class="sxs-lookup"><span data-stu-id="9cf52-288">Two digits that correspond to the last digits of the birth year</span></span>
    
- <span data-ttu-id="9cf52-289">Una lettera che corrisponde alla lettera per il mese di nascita: le lettere vengono utilizzate in ordine alfabetico, ma vengono utilizzate solo le lettere da a a E, H, L, M, P, R e T (pertanto, gennaio è A e ottobre è R)</span><span class="sxs-lookup"><span data-stu-id="9cf52-289">One letter that corresponds to the letter for the month of birth—letters are used in alphabetical order, but only the letters A to E, H, L, M, P, R to T are used (thus, January is A and October is R)</span></span>
    
- <span data-ttu-id="9cf52-290">Due cifre che corrispondono al giorno del mese di nascita, al fine di distinguere tra i sessi, 40 viene aggiunto al giorno di nascita per le donne</span><span class="sxs-lookup"><span data-stu-id="9cf52-290">Two digits that correspond to the day of the month of birth—in order to differentiate between genders, 40 is added to the day of birth for women</span></span>
    
- <span data-ttu-id="9cf52-291">Quattro cifre che corrispondono al codice di area specifico per il comune in cui è nata la persona (i codici a livello nazionale vengono utilizzati per i paesi esteri)</span><span class="sxs-lookup"><span data-stu-id="9cf52-291">Four digits that corresponds to the area code specific to the municipality where the person was born (country-wide codes are used for foreign countries)</span></span>
    
- <span data-ttu-id="9cf52-292">Una cifra di parità</span><span class="sxs-lookup"><span data-stu-id="9cf52-292">One parity digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="9cf52-293">Checksum</span><span class="sxs-lookup"><span data-stu-id="9cf52-293">Checksum</span></span>

<span data-ttu-id="9cf52-294">Sì</span><span class="sxs-lookup"><span data-stu-id="9cf52-294">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="9cf52-295">Definizione</span><span class="sxs-lookup"><span data-stu-id="9cf52-295">Definition</span></span>

<span data-ttu-id="9cf52-296">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="9cf52-296">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="9cf52-297">La funzione `Func_italy_eu_national_id_card` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="9cf52-297">The function  `Func_italy_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="9cf52-298">Viene trovata una `Keywords_italy_eu_national_id_card` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="9cf52-298">A keyword from  `Keywords_italy_eu_national_id_card` is found.</span></span> 
    
<span data-ttu-id="9cf52-299">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="9cf52-299">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="9cf52-300">La funzione `Func_italy_eu_national_id_card` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="9cf52-300">The function  `Func_italy_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="9cf52-301">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="9cf52-301">Keywords</span></span>

#### <a name="keywordsitalyeunationalidcard"></a><span data-ttu-id="9cf52-302">Keywords_italy_eu_national_id_card</span><span class="sxs-lookup"><span data-stu-id="9cf52-302">Keywords_italy_eu_national_id_card</span></span>

<span data-ttu-id="9cf52-303">codice personale</span><span class="sxs-lookup"><span data-stu-id="9cf52-303">personal code</span></span>
  
<span data-ttu-id="9cf52-304">numero di codice personale</span><span class="sxs-lookup"><span data-stu-id="9cf52-304">personal code number</span></span>
  
<span data-ttu-id="9cf52-305">numero di certificato personale</span><span class="sxs-lookup"><span data-stu-id="9cf52-305">personal certificate number</span></span>
  
<span data-ttu-id="9cf52-306">codice fiscale</span><span class="sxs-lookup"><span data-stu-id="9cf52-306">fiscal code</span></span>
  
<span data-ttu-id="9cf52-307">personalcodeno#</span><span class="sxs-lookup"><span data-stu-id="9cf52-307">personalcodeno#</span></span>
  
<span data-ttu-id="9cf52-308">numero ID personale</span><span class="sxs-lookup"><span data-stu-id="9cf52-308">personal id number</span></span>
  
<span data-ttu-id="9cf52-309">codice ID personale</span><span class="sxs-lookup"><span data-stu-id="9cf52-309">personal id code</span></span>
  
<span data-ttu-id="9cf52-310">codice personale</span><span class="sxs-lookup"><span data-stu-id="9cf52-310">codice personale</span></span>
  
<span data-ttu-id="9cf52-311">Numero certificato personale</span><span class="sxs-lookup"><span data-stu-id="9cf52-311">numero certificato personale</span></span>
  
<span data-ttu-id="9cf52-312">numero personale</span><span class="sxs-lookup"><span data-stu-id="9cf52-312">numero personale</span></span>
  
<span data-ttu-id="9cf52-313">numero ID personale</span><span class="sxs-lookup"><span data-stu-id="9cf52-313">numero id personale</span></span>
  
<span data-ttu-id="9cf52-314">codice ID personale</span><span class="sxs-lookup"><span data-stu-id="9cf52-314">codice id personale</span></span>
  
<span data-ttu-id="9cf52-315">codice fiscale</span><span class="sxs-lookup"><span data-stu-id="9cf52-315">codice fiscale</span></span>
  
## <a name="italy"></a><span data-ttu-id="9cf52-316">Italia</span><span class="sxs-lookup"><span data-stu-id="9cf52-316">Italy</span></span>

### <a name="format"></a><span data-ttu-id="9cf52-317">Formato</span><span class="sxs-lookup"><span data-stu-id="9cf52-317">Format</span></span>

<span data-ttu-id="9cf52-318">11 cifre e un trattino nel formato specificato</span><span class="sxs-lookup"><span data-stu-id="9cf52-318">11 digits and a hyphen in the specified format</span></span>
  
### <a name="pattern"></a><span data-ttu-id="9cf52-319">Modello</span><span class="sxs-lookup"><span data-stu-id="9cf52-319">Pattern</span></span>

<span data-ttu-id="9cf52-320">11 cifre e un trattino:</span><span class="sxs-lookup"><span data-stu-id="9cf52-320">11 digits and a hyphen:</span></span>
  
-  <span data-ttu-id="9cf52-321">Sei cifre che corrispondono alla data di nascita (GGMMAA)</span><span class="sxs-lookup"><span data-stu-id="9cf52-321">Six digits that correspond to the birth date (DDMMYY)</span></span> 
    
- <span data-ttu-id="9cf52-322">Una lineetta</span><span class="sxs-lookup"><span data-stu-id="9cf52-322">A hyphen</span></span>
    
- <span data-ttu-id="9cf52-323">Una cifra che corrisponde al secolo di nascita ("0" per il XIX secolo, "1" per il XX secolo e "2" per il XXI secolo)</span><span class="sxs-lookup"><span data-stu-id="9cf52-323">One digit that corresponds to the century of birth ("0" for 19th century, "1" for 20th century, and "2" for 21st century)</span></span>
    
- <span data-ttu-id="9cf52-324">Quattro cifre, generate in modo casuale</span><span class="sxs-lookup"><span data-stu-id="9cf52-324">Four digits, randomly generated</span></span>
    
### <a name="checksum"></a><span data-ttu-id="9cf52-325">Checksum</span><span class="sxs-lookup"><span data-stu-id="9cf52-325">Checksum</span></span>

<span data-ttu-id="9cf52-326">Sì</span><span class="sxs-lookup"><span data-stu-id="9cf52-326">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="9cf52-327">Definizione</span><span class="sxs-lookup"><span data-stu-id="9cf52-327">Definition</span></span>

<span data-ttu-id="9cf52-328">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="9cf52-328">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="9cf52-329">La funzione `Func_latvia_eu_national_id_card` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="9cf52-329">The function  `Func_latvia_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="9cf52-330">Viene trovata una `Keywords_latvia_eu_national_id_card` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="9cf52-330">A keyword from  `Keywords_latvia_eu_national_id_card` is found.</span></span> 
    
<span data-ttu-id="9cf52-331">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="9cf52-331">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="9cf52-332">La funzione `Func_latvia_eu_national_id_card` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="9cf52-332">The function  `Func_latvia_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="9cf52-333">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="9cf52-333">Keywords</span></span>

#### <a name="keywordslatviaeunationalidcard"></a><span data-ttu-id="9cf52-334">Keywords_latvia_eu_national_id_card</span><span class="sxs-lookup"><span data-stu-id="9cf52-334">Keywords_latvia_eu_national_id_card</span></span>

<span data-ttu-id="9cf52-335">codice personale</span><span class="sxs-lookup"><span data-stu-id="9cf52-335">personal code</span></span>
  
<span data-ttu-id="9cf52-336">numero di codice personale</span><span class="sxs-lookup"><span data-stu-id="9cf52-336">personal code number</span></span>
  
<span data-ttu-id="9cf52-337">numero di certificato personale</span><span class="sxs-lookup"><span data-stu-id="9cf52-337">personal certificate number</span></span>
  
<span data-ttu-id="9cf52-338">personalcodeno#</span><span class="sxs-lookup"><span data-stu-id="9cf52-338">personalcodeno#</span></span>
  
<span data-ttu-id="9cf52-339">numero ID personale</span><span class="sxs-lookup"><span data-stu-id="9cf52-339">personal id number</span></span>
  
<span data-ttu-id="9cf52-340">codice ID personale</span><span class="sxs-lookup"><span data-stu-id="9cf52-340">personal id code</span></span>
  
<span data-ttu-id="9cf52-341">personas Kods</span><span class="sxs-lookup"><span data-stu-id="9cf52-341">personas kods</span></span>
  
## <a name="lithuania"></a><span data-ttu-id="9cf52-342">Lituania</span><span class="sxs-lookup"><span data-stu-id="9cf52-342">Lithuania</span></span>

### <a name="format"></a><span data-ttu-id="9cf52-343">Formato</span><span class="sxs-lookup"><span data-stu-id="9cf52-343">Format</span></span>

<span data-ttu-id="9cf52-344">11 cifre senza spazi e delimitatori</span><span class="sxs-lookup"><span data-stu-id="9cf52-344">11 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="9cf52-345">Modello</span><span class="sxs-lookup"><span data-stu-id="9cf52-345">Pattern</span></span>

<span data-ttu-id="9cf52-346">11 cifre senza spazi e delimitatori:</span><span class="sxs-lookup"><span data-stu-id="9cf52-346">11 digits without spaces and delimiters:</span></span>
  
- <span data-ttu-id="9cf52-347">Una cifra corrispondente al sesso e al secolo della nascita della persona</span><span class="sxs-lookup"><span data-stu-id="9cf52-347">One digit that corresponds to the person's gender and century of birth</span></span>
    
-  <span data-ttu-id="9cf52-348">Sei cifre che corrispondono alla data di nascita (AAMMGG)</span><span class="sxs-lookup"><span data-stu-id="9cf52-348">Six digits that correspond to birth date (YYMMDD)</span></span> 
    
- <span data-ttu-id="9cf52-349">Tre cifre che corrispondono al numero di serie della data di nascita</span><span class="sxs-lookup"><span data-stu-id="9cf52-349">Three digits that correspond to the serial number of the date of birth</span></span>
    
- <span data-ttu-id="9cf52-350">Una cifra di controllo</span><span class="sxs-lookup"><span data-stu-id="9cf52-350">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="9cf52-351">Checksum</span><span class="sxs-lookup"><span data-stu-id="9cf52-351">Checksum</span></span>

<span data-ttu-id="9cf52-352">Sì</span><span class="sxs-lookup"><span data-stu-id="9cf52-352">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="9cf52-353">Definizione</span><span class="sxs-lookup"><span data-stu-id="9cf52-353">Definition</span></span>

<span data-ttu-id="9cf52-354">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="9cf52-354">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="9cf52-355">La funzione `Func_lithuania_eu_national_id_card` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="9cf52-355">The function  `Func_lithuania_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="9cf52-356">Viene trovata una `Keywords_lithuania_eu_national_id_card` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="9cf52-356">A keyword from  `Keywords_lithuania_eu_national_id_card` is found.</span></span> 
    
<span data-ttu-id="9cf52-357">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="9cf52-357">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="9cf52-358">La funzione `Func_lithuania_eu_national_id_card` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="9cf52-358">The function  `Func_lithuania_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="9cf52-359">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="9cf52-359">Keywords</span></span>

#### <a name="keywordslithuaniaeunationalidcard"></a><span data-ttu-id="9cf52-360">Keywords_lithuania_eu_national_id_card</span><span class="sxs-lookup"><span data-stu-id="9cf52-360">Keywords_lithuania_eu_national_id_card</span></span>

<span data-ttu-id="9cf52-361">codice numerico personale</span><span class="sxs-lookup"><span data-stu-id="9cf52-361">personal numeric code</span></span>
  
<span data-ttu-id="9cf52-362">numero di identificazione univoco</span><span class="sxs-lookup"><span data-stu-id="9cf52-362">unique identification number</span></span>
  
<span data-ttu-id="9cf52-363">numero di servizio Citizen</span><span class="sxs-lookup"><span data-stu-id="9cf52-363">citizen service number</span></span>
  
<span data-ttu-id="9cf52-364">numero di identità univoco</span><span class="sxs-lookup"><span data-stu-id="9cf52-364">unique identity number</span></span>
  
<span data-ttu-id="9cf52-365">uniqueidentityno#</span><span class="sxs-lookup"><span data-stu-id="9cf52-365">uniqueidentityno#</span></span>
  
<span data-ttu-id="9cf52-366">codice personale.</span><span class="sxs-lookup"><span data-stu-id="9cf52-366">personal code.</span></span>
  
<span data-ttu-id="9cf52-367">asmeninis skaitmeninis kodas</span><span class="sxs-lookup"><span data-stu-id="9cf52-367">asmeninis skaitmeninis kodas</span></span>
  
<span data-ttu-id="9cf52-368">unikalus identifikavimo numeris</span><span class="sxs-lookup"><span data-stu-id="9cf52-368">unikalus identifikavimo numeris</span></span>
  
<span data-ttu-id="9cf52-369">piliečio paslaugos numeris</span><span class="sxs-lookup"><span data-stu-id="9cf52-369">piliečio paslaugos numeris</span></span>
  
<span data-ttu-id="9cf52-370">unikalus identifikavimo kodas</span><span class="sxs-lookup"><span data-stu-id="9cf52-370">unikalus identifikavimo kodas</span></span>
  
<span data-ttu-id="9cf52-371">asmens kodas.</span><span class="sxs-lookup"><span data-stu-id="9cf52-371">asmens kodas.</span></span>
  
## <a name="luxemburg"></a><span data-ttu-id="9cf52-372">Lussemburgo</span><span class="sxs-lookup"><span data-stu-id="9cf52-372">Luxemburg</span></span>

### <a name="format"></a><span data-ttu-id="9cf52-373">Formato</span><span class="sxs-lookup"><span data-stu-id="9cf52-373">Format</span></span>

<span data-ttu-id="9cf52-374">11 cifre senza spazi e delimitatori</span><span class="sxs-lookup"><span data-stu-id="9cf52-374">11 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="9cf52-375">Modello</span><span class="sxs-lookup"><span data-stu-id="9cf52-375">Pattern</span></span>

<span data-ttu-id="9cf52-376">11 cifre</span><span class="sxs-lookup"><span data-stu-id="9cf52-376">11 digits</span></span>
  
- <span data-ttu-id="9cf52-377">Una cifra corrispondente al sesso e al secolo della nascita della persona</span><span class="sxs-lookup"><span data-stu-id="9cf52-377">One digit that corresponds to the person's gender and century of birth</span></span>
    
-  <span data-ttu-id="9cf52-378">Sei cifre che corrispondono alla data di nascita (AAMMGG)</span><span class="sxs-lookup"><span data-stu-id="9cf52-378">Six digits that correspond to birth date (YYMMDD)</span></span> 
    
- <span data-ttu-id="9cf52-379">Tre cifre che corrispondono al numero di serie della data di nascita</span><span class="sxs-lookup"><span data-stu-id="9cf52-379">Three digits that correspond to the serial number of the date of birth</span></span>
    
- <span data-ttu-id="9cf52-380">Una cifra di controllo</span><span class="sxs-lookup"><span data-stu-id="9cf52-380">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="9cf52-381">Checksum</span><span class="sxs-lookup"><span data-stu-id="9cf52-381">Checksum</span></span>

<span data-ttu-id="9cf52-382">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="9cf52-382">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="9cf52-383">Definizione</span><span class="sxs-lookup"><span data-stu-id="9cf52-383">Definition</span></span>

<span data-ttu-id="9cf52-384">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="9cf52-384">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="9cf52-385">L'espressione `Regex_luxemburg_eu_national_id_card` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="9cf52-385">The regular expression  `Regex_luxemburg_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="9cf52-386">Viene trovata una `Keywords_luxemburg_eu_national_id_card` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="9cf52-386">A keyword from  `Keywords_luxemburg_eu_national_id_card` is found.</span></span> 
    
```
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_luxemburg_eu_national_id_card" />
          <Match idRef="Keywords_luxemburg_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="9cf52-387">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="9cf52-387">Keywords</span></span>

#### <a name="keywordsluxemburgeunationalidcard"></a><span data-ttu-id="9cf52-388">Keywords_luxemburg_eu_national_id_card</span><span class="sxs-lookup"><span data-stu-id="9cf52-388">Keywords_luxemburg_eu_national_id_card</span></span>

<span data-ttu-id="9cf52-389">ID personale</span><span class="sxs-lookup"><span data-stu-id="9cf52-389">personal id</span></span>
  
<span data-ttu-id="9cf52-390">numero ID personale</span><span class="sxs-lookup"><span data-stu-id="9cf52-390">personal id number</span></span>
  
<span data-ttu-id="9cf52-391">personalidno#</span><span class="sxs-lookup"><span data-stu-id="9cf52-391">personalidno#</span></span>
  
<span data-ttu-id="9cf52-392">numero ID univoco</span><span class="sxs-lookup"><span data-stu-id="9cf52-392">unique id number</span></span>
  
<span data-ttu-id="9cf52-393">personalidnumber#</span><span class="sxs-lookup"><span data-stu-id="9cf52-393">personalidnumber#</span></span>
  
<span data-ttu-id="9cf52-394">chiave ID univoco</span><span class="sxs-lookup"><span data-stu-id="9cf52-394">unique id key</span></span>
  
<span data-ttu-id="9cf52-395">codice ID personale</span><span class="sxs-lookup"><span data-stu-id="9cf52-395">personal id code</span></span>
  
<span data-ttu-id="9cf52-396">uniqueidkey#</span><span class="sxs-lookup"><span data-stu-id="9cf52-396">uniqueidkey#</span></span>
  
<span data-ttu-id="9cf52-397">codice singolo</span><span class="sxs-lookup"><span data-stu-id="9cf52-397">individual code</span></span>
  
<span data-ttu-id="9cf52-398">ID individuale</span><span class="sxs-lookup"><span data-stu-id="9cf52-398">individual id</span></span>
  
<span data-ttu-id="9cf52-399">ID eindeutige-Nummer</span><span class="sxs-lookup"><span data-stu-id="9cf52-399">eindeutige id-nummer</span></span>
  
<span data-ttu-id="9cf52-400">ID eindeutige</span><span class="sxs-lookup"><span data-stu-id="9cf52-400">eindeutige id</span></span>
  
<span data-ttu-id="9cf52-401">ID personnelle</span><span class="sxs-lookup"><span data-stu-id="9cf52-401">id personnelle</span></span>
  
<span data-ttu-id="9cf52-402">personale di Numéro d'identification</span><span class="sxs-lookup"><span data-stu-id="9cf52-402">numéro d'identification personnel</span></span>
  
<span data-ttu-id="9cf52-403">idpersonnelle#</span><span class="sxs-lookup"><span data-stu-id="9cf52-403">idpersonnelle#</span></span>
  
<span data-ttu-id="9cf52-404">persönliche identifikationsnummer</span><span class="sxs-lookup"><span data-stu-id="9cf52-404">persönliche identifikationsnummer</span></span>
  
<span data-ttu-id="9cf52-405">eindeutigeid#</span><span class="sxs-lookup"><span data-stu-id="9cf52-405">eindeutigeid#</span></span>
  
## <a name="malta"></a><span data-ttu-id="9cf52-406">Malta</span><span class="sxs-lookup"><span data-stu-id="9cf52-406">Malta</span></span>

### <a name="format"></a><span data-ttu-id="9cf52-407">Formato</span><span class="sxs-lookup"><span data-stu-id="9cf52-407">Format</span></span>

<span data-ttu-id="9cf52-408">Sette cifre seguite da una lettera</span><span class="sxs-lookup"><span data-stu-id="9cf52-408">Seven digits followed by one letter</span></span>
  
### <a name="pattern"></a><span data-ttu-id="9cf52-409">Modello</span><span class="sxs-lookup"><span data-stu-id="9cf52-409">Pattern</span></span>

<span data-ttu-id="9cf52-410">Sette cifre seguite da una lettera:</span><span class="sxs-lookup"><span data-stu-id="9cf52-410">Seven digits followed by one letter:</span></span>
  
-  <span data-ttu-id="9cf52-411">Sette cifre</span><span class="sxs-lookup"><span data-stu-id="9cf52-411">Seven digits</span></span> 
    
- <span data-ttu-id="9cf52-412">Una lettera maiuscola (distinzione tra maiuscole e minuscole)</span><span class="sxs-lookup"><span data-stu-id="9cf52-412">One uppercase letter (case sensitive)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="9cf52-413">Checksum</span><span class="sxs-lookup"><span data-stu-id="9cf52-413">Checksum</span></span>

<span data-ttu-id="9cf52-414">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="9cf52-414">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="9cf52-415">Definizione</span><span class="sxs-lookup"><span data-stu-id="9cf52-415">Definition</span></span>

<span data-ttu-id="9cf52-416">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="9cf52-416">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="9cf52-417">L'espressione `Regex_malta_eu_national_id_card` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="9cf52-417">The regular expression  `Regex_malta_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="9cf52-418">Viene trovata una `Keywords_malta_eu_national_id_card` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="9cf52-418">A keyword from  `Keywords_malta_eu_national_id_card` is found.</span></span> 
    
<span data-ttu-id="9cf52-419">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 65%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="9cf52-419">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="9cf52-420">L'espressione `Regex_malta_eu_national_id_card` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="9cf52-420">The regular expression  `Regex_malta_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="9cf52-421">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="9cf52-421">Keywords</span></span>

#### <a name="keywordsmaltaeunationalidcard"></a><span data-ttu-id="9cf52-422">Keywords_malta_eu_national_id_card</span><span class="sxs-lookup"><span data-stu-id="9cf52-422">Keywords_malta_eu_national_id_card</span></span>

<span data-ttu-id="9cf52-423">codice numerico personale</span><span class="sxs-lookup"><span data-stu-id="9cf52-423">personal numeric code</span></span>
  
<span data-ttu-id="9cf52-424">numero di identificazione univoco</span><span class="sxs-lookup"><span data-stu-id="9cf52-424">unique identification number</span></span>
  
<span data-ttu-id="9cf52-425">numero di servizio Citizen</span><span class="sxs-lookup"><span data-stu-id="9cf52-425">citizen service number</span></span>
  
<span data-ttu-id="9cf52-426">numero di identità univoco</span><span class="sxs-lookup"><span data-stu-id="9cf52-426">unique identity number</span></span>
  
<span data-ttu-id="9cf52-427">uniqueidentityno#</span><span class="sxs-lookup"><span data-stu-id="9cf52-427">uniqueidentityno#</span></span>
  
<span data-ttu-id="9cf52-428">Kodiċi numerai personali</span><span class="sxs-lookup"><span data-stu-id="9cf52-428">kodiċi numerali personali</span></span>
  
<span data-ttu-id="9cf52-429">numru ta ' identifikazzjoni uniku</span><span class="sxs-lookup"><span data-stu-id="9cf52-429">numru ta 'identifikazzjoni uniku</span></span>
  
<span data-ttu-id="9cf52-430">numru TAS-Servizz taċ-ċittadin</span><span class="sxs-lookup"><span data-stu-id="9cf52-430">numru tas-servizz taċ-ċittadin</span></span>
  
<span data-ttu-id="9cf52-431">numru ta ' identità uniku</span><span class="sxs-lookup"><span data-stu-id="9cf52-431">numru ta' identità uniku</span></span>
  
## <a name="netherlands"></a><span data-ttu-id="9cf52-432">Paesi Bassi</span><span class="sxs-lookup"><span data-stu-id="9cf52-432">Netherlands</span></span>

### <a name="format"></a><span data-ttu-id="9cf52-433">Formato</span><span class="sxs-lookup"><span data-stu-id="9cf52-433">Format</span></span>

<span data-ttu-id="9cf52-434">Nove cifre senza spazi o delimitatori</span><span class="sxs-lookup"><span data-stu-id="9cf52-434">Nine digits without spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="9cf52-435">Modello</span><span class="sxs-lookup"><span data-stu-id="9cf52-435">Pattern</span></span>

<span data-ttu-id="9cf52-436">9 cifre</span><span class="sxs-lookup"><span data-stu-id="9cf52-436">Nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="9cf52-437">Checksum</span><span class="sxs-lookup"><span data-stu-id="9cf52-437">Checksum</span></span>

<span data-ttu-id="9cf52-438">Sì</span><span class="sxs-lookup"><span data-stu-id="9cf52-438">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="9cf52-439">Definizione</span><span class="sxs-lookup"><span data-stu-id="9cf52-439">Definition</span></span>

<span data-ttu-id="9cf52-440">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="9cf52-440">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="9cf52-441">La funzione `Func_netherlands_eu_national_id_card` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="9cf52-441">The function  `Func_netherlands_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="9cf52-442">Viene trovata una parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="9cf52-442">A keyword from is found.</span></span>
    
<span data-ttu-id="9cf52-443">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="9cf52-443">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="9cf52-444">La funzione `Func_netherlands_eu_national_id_card` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="9cf52-444">The function  `Func_netherlands_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="9cf52-445">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="9cf52-445">Keywords</span></span>

#### <a name="keywordsnetherlandseunationalidcard"></a><span data-ttu-id="9cf52-446">Keywords_netherlands_eu_national_id_card</span><span class="sxs-lookup"><span data-stu-id="9cf52-446">Keywords_netherlands_eu_national_id_card</span></span>

<span data-ttu-id="9cf52-447">codice numerico personale</span><span class="sxs-lookup"><span data-stu-id="9cf52-447">personal numeric code</span></span>
  
<span data-ttu-id="9cf52-448">numero di identificazione univoco</span><span class="sxs-lookup"><span data-stu-id="9cf52-448">unique identification number</span></span>
  
<span data-ttu-id="9cf52-449">numero di servizio Citizen</span><span class="sxs-lookup"><span data-stu-id="9cf52-449">citizen service number</span></span>
  
<span data-ttu-id="9cf52-450">numero di identità univoco</span><span class="sxs-lookup"><span data-stu-id="9cf52-450">unique identity number</span></span>
  
<span data-ttu-id="9cf52-451">uniqueidentityno#</span><span class="sxs-lookup"><span data-stu-id="9cf52-451">uniqueidentityno#</span></span>
  
<span data-ttu-id="9cf52-452">BSN</span><span class="sxs-lookup"><span data-stu-id="9cf52-452">bsn</span></span>
  
<span data-ttu-id="9cf52-453">BSN</span><span class="sxs-lookup"><span data-stu-id="9cf52-453">bsn#</span></span>
  
<span data-ttu-id="9cf52-454">codice Numerieke di persoonlijke</span><span class="sxs-lookup"><span data-stu-id="9cf52-454">persoonlijke numerieke code</span></span>
  
<span data-ttu-id="9cf52-455">uniek identificatienummer</span><span class="sxs-lookup"><span data-stu-id="9cf52-455">uniek identificatienummer</span></span>
  
<span data-ttu-id="9cf52-456">burgerservicenummer</span><span class="sxs-lookup"><span data-stu-id="9cf52-456">burgerservicenummer</span></span>
  
<span data-ttu-id="9cf52-457">uniek identiteitsnummer</span><span class="sxs-lookup"><span data-stu-id="9cf52-457">uniek identiteitsnummer</span></span>
  
## <a name="poland"></a><span data-ttu-id="9cf52-458">Polonia</span><span class="sxs-lookup"><span data-stu-id="9cf52-458">Poland</span></span>

<span data-ttu-id="9cf52-459">Per informazioni dettagliate, vedere la sezione "Poland National ID (PESEL)" in [che cosa cercano i tipi di informazioni riservate](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="9cf52-459">For details, see the section "Poland National ID (PESEL)" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="portugal"></a><span data-ttu-id="9cf52-460">Portogallo</span><span class="sxs-lookup"><span data-stu-id="9cf52-460">Portugal</span></span>

<span data-ttu-id="9cf52-461">Per informazioni dettagliate, vedere la sezione "Portugal Citizen Card Number" in [quello che i tipi di informazioni riservate cercano](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="9cf52-461">For details, see the section "Portugal Citizen Card Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="romania"></a><span data-ttu-id="9cf52-462">Romania</span><span class="sxs-lookup"><span data-stu-id="9cf52-462">Romania</span></span>

### <a name="format"></a><span data-ttu-id="9cf52-463">Formato</span><span class="sxs-lookup"><span data-stu-id="9cf52-463">Format</span></span>

<span data-ttu-id="9cf52-464">13 cifre senza spazi e delimitatori</span><span class="sxs-lookup"><span data-stu-id="9cf52-464">13 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="9cf52-465">Modello</span><span class="sxs-lookup"><span data-stu-id="9cf52-465">Pattern</span></span>

<span data-ttu-id="9cf52-466">13 cifre</span><span class="sxs-lookup"><span data-stu-id="9cf52-466">13 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="9cf52-467">Checksum</span><span class="sxs-lookup"><span data-stu-id="9cf52-467">Checksum</span></span>

<span data-ttu-id="9cf52-468">Sì</span><span class="sxs-lookup"><span data-stu-id="9cf52-468">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="9cf52-469">Definizione</span><span class="sxs-lookup"><span data-stu-id="9cf52-469">Definition</span></span>

<span data-ttu-id="9cf52-470">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="9cf52-470">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="9cf52-471">La funzione `Func_romania_eu_national_id_card` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="9cf52-471">The function  `Func_romania_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="9cf52-472">Viene trovata una `Keywords_romania_eu_national_id_card` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="9cf52-472">A keyword from  `Keywords_romania_eu_national_id_card` is found.</span></span> 
    
<span data-ttu-id="9cf52-473">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="9cf52-473">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="9cf52-474">La funzione `Func_romania_eu_national_id_card` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="9cf52-474">The function  `Func_romania_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="9cf52-475">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="9cf52-475">Keywords</span></span>

#### <a name="keywordsromaniaeunationalidcard"></a><span data-ttu-id="9cf52-476">Keywords_romania_eu_national_id_card</span><span class="sxs-lookup"><span data-stu-id="9cf52-476">Keywords_romania_eu_national_id_card</span></span>

<span data-ttu-id="9cf52-477">codice numerico personale</span><span class="sxs-lookup"><span data-stu-id="9cf52-477">personal numeric code</span></span>
  
<span data-ttu-id="9cf52-478">numero di identificazione univoco</span><span class="sxs-lookup"><span data-stu-id="9cf52-478">unique identification number</span></span>
  
<span data-ttu-id="9cf52-479">CNP</span><span class="sxs-lookup"><span data-stu-id="9cf52-479">cnp</span></span>
  
<span data-ttu-id="9cf52-480">CNP</span><span class="sxs-lookup"><span data-stu-id="9cf52-480">cnp#</span></span>
  
<span data-ttu-id="9cf52-481">pin</span><span class="sxs-lookup"><span data-stu-id="9cf52-481">pin</span></span>
  
<span data-ttu-id="9cf52-482">pin</span><span class="sxs-lookup"><span data-stu-id="9cf52-482">pin#</span></span>
  
<span data-ttu-id="9cf52-483">numero assicurativo</span><span class="sxs-lookup"><span data-stu-id="9cf52-483">insurance number</span></span>
  
<span data-ttu-id="9cf52-484">insurancenumber#</span><span class="sxs-lookup"><span data-stu-id="9cf52-484">insurancenumber#</span></span>
  
<span data-ttu-id="9cf52-485">numero di identità univoco</span><span class="sxs-lookup"><span data-stu-id="9cf52-485">unique identity number</span></span>
  
<span data-ttu-id="9cf52-486">uniqueidentityno#</span><span class="sxs-lookup"><span data-stu-id="9cf52-486">uniqueidentityno#</span></span>
  
<span data-ttu-id="9cf52-487">Cod numerico personale</span><span class="sxs-lookup"><span data-stu-id="9cf52-487">cod numeric personal</span></span>
  
<span data-ttu-id="9cf52-488">Cod identificare Personal</span><span class="sxs-lookup"><span data-stu-id="9cf52-488">cod identificare personal</span></span>
  
<span data-ttu-id="9cf52-489">Cod Unic identificare</span><span class="sxs-lookup"><span data-stu-id="9cf52-489">cod unic identificare</span></span>
  
<span data-ttu-id="9cf52-490">Număr personale Unic</span><span class="sxs-lookup"><span data-stu-id="9cf52-490">număr personal unic</span></span>
  
<span data-ttu-id="9cf52-491">număr identitate</span><span class="sxs-lookup"><span data-stu-id="9cf52-491">număr identitate</span></span>
  
<span data-ttu-id="9cf52-492">Număr identificare Personal</span><span class="sxs-lookup"><span data-stu-id="9cf52-492">număr identificare personal</span></span>
  
<span data-ttu-id="9cf52-493">număridentitate#</span><span class="sxs-lookup"><span data-stu-id="9cf52-493">număridentitate#</span></span>
  
<span data-ttu-id="9cf52-494">codnumericpersonal#</span><span class="sxs-lookup"><span data-stu-id="9cf52-494">codnumericpersonal#</span></span>
  
<span data-ttu-id="9cf52-495">numărpersonalunic#</span><span class="sxs-lookup"><span data-stu-id="9cf52-495">numărpersonalunic#</span></span>
  
## <a name="slovakia"></a><span data-ttu-id="9cf52-496">Slovacchia</span><span class="sxs-lookup"><span data-stu-id="9cf52-496">Slovakia</span></span>

### <a name="format"></a><span data-ttu-id="9cf52-497">Formato</span><span class="sxs-lookup"><span data-stu-id="9cf52-497">Format</span></span>

<span data-ttu-id="9cf52-498">Dieci cifre contenenti una barra rovesciata</span><span class="sxs-lookup"><span data-stu-id="9cf52-498">Ten digits containing one backslash</span></span>
  
### <a name="pattern"></a><span data-ttu-id="9cf52-499">Modello</span><span class="sxs-lookup"><span data-stu-id="9cf52-499">Pattern</span></span>

<span data-ttu-id="9cf52-500">Dieci cifre che contengono una barra rovesciata:</span><span class="sxs-lookup"><span data-stu-id="9cf52-500">Ten digits containing one backslash:</span></span>
  
### <a name="checksum"></a><span data-ttu-id="9cf52-501">Checksum</span><span class="sxs-lookup"><span data-stu-id="9cf52-501">Checksum</span></span>

<span data-ttu-id="9cf52-502">Sì</span><span class="sxs-lookup"><span data-stu-id="9cf52-502">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="9cf52-503">Definizione</span><span class="sxs-lookup"><span data-stu-id="9cf52-503">Definition</span></span>

<span data-ttu-id="9cf52-504">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="9cf52-504">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="9cf52-505">La funzione `Func_slovakia_eu_national_id_card` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="9cf52-505">The function  `Func_slovakia_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="9cf52-506">Viene trovata una `Keywords_slovakia_eu_national_id_card` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="9cf52-506">A keyword from  `Keywords_slovakia_eu_national_id_card` is found.</span></span> 
    
<span data-ttu-id="9cf52-507">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="9cf52-507">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="9cf52-508">La funzione `Func_slovakia_eu_national_id_card` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="9cf52-508">The function  `Func_slovakia_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="9cf52-509">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="9cf52-509">Keywords</span></span>

#### <a name="keywordsslovakiaeunationalidcard"></a><span data-ttu-id="9cf52-510">Keywords_slovakia_eu_national_id_card</span><span class="sxs-lookup"><span data-stu-id="9cf52-510">Keywords_slovakia_eu_national_id_card</span></span>

<span data-ttu-id="9cf52-511">numero di nascita</span><span class="sxs-lookup"><span data-stu-id="9cf52-511">birth number</span></span>
  
<span data-ttu-id="9cf52-512">national identification number</span><span class="sxs-lookup"><span data-stu-id="9cf52-512">national identification number</span></span>
  
<span data-ttu-id="9cf52-513">numero di identificazione personale</span><span class="sxs-lookup"><span data-stu-id="9cf52-513">personal identification number</span></span>
  
<span data-ttu-id="9cf52-514">social security number</span><span class="sxs-lookup"><span data-stu-id="9cf52-514">social security number</span></span>
  
<span data-ttu-id="9cf52-515">nationalnumber#</span><span class="sxs-lookup"><span data-stu-id="9cf52-515">nationalnumber#</span></span>
  
<span data-ttu-id="9cf52-516">SSN</span><span class="sxs-lookup"><span data-stu-id="9cf52-516">ssn#</span></span>
  
<span data-ttu-id="9cf52-517">SSN</span><span class="sxs-lookup"><span data-stu-id="9cf52-517">ssn</span></span>
  
<span data-ttu-id="9cf52-518">numero nazionale</span><span class="sxs-lookup"><span data-stu-id="9cf52-518">national number</span></span>
  
<span data-ttu-id="9cf52-519">numero ID personale</span><span class="sxs-lookup"><span data-stu-id="9cf52-519">personal id number</span></span>
  
<span data-ttu-id="9cf52-520">personalidnumber#</span><span class="sxs-lookup"><span data-stu-id="9cf52-520">personalidnumber#</span></span>
  
<span data-ttu-id="9cf52-521">rč</span><span class="sxs-lookup"><span data-stu-id="9cf52-521">rč</span></span>
  
<span data-ttu-id="9cf52-522">rodné číslo</span><span class="sxs-lookup"><span data-stu-id="9cf52-522">rodné číslo</span></span>
  
<span data-ttu-id="9cf52-523">rodne cislo</span><span class="sxs-lookup"><span data-stu-id="9cf52-523">rodne cislo</span></span>
  
## <a name="slovenia"></a><span data-ttu-id="9cf52-524">Slovenia</span><span class="sxs-lookup"><span data-stu-id="9cf52-524">Slovenia</span></span>

### <a name="format"></a><span data-ttu-id="9cf52-525">Formato</span><span class="sxs-lookup"><span data-stu-id="9cf52-525">Format</span></span>

<span data-ttu-id="9cf52-526">13 cifre senza spazi o delimitatori</span><span class="sxs-lookup"><span data-stu-id="9cf52-526">13 digits without spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="9cf52-527">Modello</span><span class="sxs-lookup"><span data-stu-id="9cf52-527">Pattern</span></span>

<span data-ttu-id="9cf52-528">13 cifre nel modello specificato:</span><span class="sxs-lookup"><span data-stu-id="9cf52-528">13 digits in the specified pattern:</span></span>
  
-  <span data-ttu-id="9cf52-529">Sette cifre che corrispondono alla data di nascita (DDMMLLL), dove "LLL" corrisponde alle ultime tre cifre dell'anno di nascita</span><span class="sxs-lookup"><span data-stu-id="9cf52-529">Seven digits that correspond to the birth date (DDMMLLL) where "LLL" corresponds to the last three digits of the birth year</span></span> 
    
- <span data-ttu-id="9cf52-530">Due cifre che corrispondono all'area di nascita</span><span class="sxs-lookup"><span data-stu-id="9cf52-530">Two digits that correspond to the area of birth</span></span>
    
- <span data-ttu-id="9cf52-531">Tre cifre che corrispondono a una combinazione di genere e numero di serie per le persone nate nello stesso giorno (000-499 per il maschio e 500-999 per le femmine)</span><span class="sxs-lookup"><span data-stu-id="9cf52-531">Three digits that correspond to a combination of gender and serial number for persons born on the same day (000-499 for male and 500-999 for female)</span></span>
    
- <span data-ttu-id="9cf52-532">Una cifra di controllo</span><span class="sxs-lookup"><span data-stu-id="9cf52-532">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="9cf52-533">Checksum</span><span class="sxs-lookup"><span data-stu-id="9cf52-533">Checksum</span></span>

<span data-ttu-id="9cf52-534">Sì</span><span class="sxs-lookup"><span data-stu-id="9cf52-534">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="9cf52-535">Definizione</span><span class="sxs-lookup"><span data-stu-id="9cf52-535">Definition</span></span>

<span data-ttu-id="9cf52-536">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="9cf52-536">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="9cf52-537">La funzione `Func_slovenia_eu_national_id_card` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="9cf52-537">The function  `Func_slovenia_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="9cf52-538">Viene trovata una `Keywords_slovenia_eu_national_id_card` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="9cf52-538">A keyword from  `Keywords_slovenia_eu_national_id_card` is found.</span></span> 
    
<span data-ttu-id="9cf52-539">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="9cf52-539">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="9cf52-540">La funzione `Func_slovenia_eu_national_id_card` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="9cf52-540">The function  `Func_slovenia_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="9cf52-541">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="9cf52-541">Keywords</span></span>

#### <a name="keywordssloveniaeunationalidcard"></a><span data-ttu-id="9cf52-542">Keywords_slovenia_eu_national_id_card</span><span class="sxs-lookup"><span data-stu-id="9cf52-542">Keywords_slovenia_eu_national_id_card</span></span>

<span data-ttu-id="9cf52-543">codice numerico personale</span><span class="sxs-lookup"><span data-stu-id="9cf52-543">personal numeric code</span></span>
  
<span data-ttu-id="9cf52-544">numero di identificazione univoco</span><span class="sxs-lookup"><span data-stu-id="9cf52-544">unique identification number</span></span>
  
<span data-ttu-id="9cf52-545">numero di registrazione univoco</span><span class="sxs-lookup"><span data-stu-id="9cf52-545">unique registration number</span></span>
  
<span data-ttu-id="9cf52-546">numero di identità univoco</span><span class="sxs-lookup"><span data-stu-id="9cf52-546">unique identity number</span></span>
  
<span data-ttu-id="9cf52-547">uniqueidentityno#</span><span class="sxs-lookup"><span data-stu-id="9cf52-547">uniqueidentityno#</span></span>
  
<span data-ttu-id="9cf52-548">numero di cittadino Master univoco</span><span class="sxs-lookup"><span data-stu-id="9cf52-548">unique master citizen number</span></span>
  
<span data-ttu-id="9cf52-549">edinstvena identifikacijska številka</span><span class="sxs-lookup"><span data-stu-id="9cf52-549">edinstvena identifikacijska številka</span></span>
  
<span data-ttu-id="9cf52-550">uniqueidentityno #</span><span class="sxs-lookup"><span data-stu-id="9cf52-550">uniqueidentityno #</span></span>
  
<span data-ttu-id="9cf52-551">edinstvena številka glavnega državljana</span><span class="sxs-lookup"><span data-stu-id="9cf52-551">edinstvena številka glavnega državljana</span></span>
  
<span data-ttu-id="9cf52-552">emšo</span><span class="sxs-lookup"><span data-stu-id="9cf52-552">emšo</span></span>
  
## <a name="spain"></a><span data-ttu-id="9cf52-553">Spagna</span><span class="sxs-lookup"><span data-stu-id="9cf52-553">Spain</span></span>

### <a name="format"></a><span data-ttu-id="9cf52-554">Formato</span><span class="sxs-lookup"><span data-stu-id="9cf52-554">Format</span></span>

<span data-ttu-id="9cf52-555">Sette cifre seguite da un carattere</span><span class="sxs-lookup"><span data-stu-id="9cf52-555">Seven digits followed by one character</span></span>
  
### <a name="pattern"></a><span data-ttu-id="9cf52-556">Modello</span><span class="sxs-lookup"><span data-stu-id="9cf52-556">Pattern</span></span>

<span data-ttu-id="9cf52-557">Sette cifre seguite da un carattere</span><span class="sxs-lookup"><span data-stu-id="9cf52-557">Seven digits followed by one character</span></span>
  
- <span data-ttu-id="9cf52-558">Sette cifre</span><span class="sxs-lookup"><span data-stu-id="9cf52-558">Seven digits</span></span>
    
- <span data-ttu-id="9cf52-559">Una cifra o una lettera (senza distinzione tra maiuscole e minuscole)</span><span class="sxs-lookup"><span data-stu-id="9cf52-559">One digit or letter (not case-sensitive)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="9cf52-560">Checksum</span><span class="sxs-lookup"><span data-stu-id="9cf52-560">Checksum</span></span>

<span data-ttu-id="9cf52-561">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="9cf52-561">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="9cf52-562">Definizione</span><span class="sxs-lookup"><span data-stu-id="9cf52-562">Definition</span></span>

<span data-ttu-id="9cf52-563">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="9cf52-563">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="9cf52-564">L'espressione `Regex_spain_eu_national_id_card` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="9cf52-564">The regular expression  `Regex_spain_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="9cf52-565">Viene trovata una `Keywords_spain_eu_national_id_card"` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="9cf52-565">A keyword from  `Keywords_spain_eu_national_id_card"` is found.</span></span> 
    
```
 
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_spain_eu_national_id_card" />
          <Match idRef="Keywords_spain_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="9cf52-566">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="9cf52-566">Keywords</span></span>

#### <a name="keywordsspaineunationalidcard"></a><span data-ttu-id="9cf52-567">Keywords_spain_eu_national_id_card</span><span class="sxs-lookup"><span data-stu-id="9cf52-567">Keywords_spain_eu_national_id_card</span></span>

<span data-ttu-id="9cf52-568">DNI</span><span class="sxs-lookup"><span data-stu-id="9cf52-568">dni</span></span>
  
<span data-ttu-id="9cf52-569">national identification number</span><span class="sxs-lookup"><span data-stu-id="9cf52-569">national identification number</span></span>
  
<span data-ttu-id="9cf52-570">numero di identità nazionale</span><span class="sxs-lookup"><span data-stu-id="9cf52-570">national identity number</span></span>
  
<span data-ttu-id="9cf52-571">numero assicurativo</span><span class="sxs-lookup"><span data-stu-id="9cf52-571">insurance number</span></span>
  
<span data-ttu-id="9cf52-572">numero di identificazione personale</span><span class="sxs-lookup"><span data-stu-id="9cf52-572">personal identification number</span></span>
  
<span data-ttu-id="9cf52-573">identità nazionale</span><span class="sxs-lookup"><span data-stu-id="9cf52-573">national identity</span></span>
  
<span data-ttu-id="9cf52-574">identità personale No</span><span class="sxs-lookup"><span data-stu-id="9cf52-574">personal identity no</span></span>
  
<span data-ttu-id="9cf52-575">numero di identità univoco</span><span class="sxs-lookup"><span data-stu-id="9cf52-575">unique identity number</span></span>
  
<span data-ttu-id="9cf52-576">nationalidno#</span><span class="sxs-lookup"><span data-stu-id="9cf52-576">nationalidno#</span></span>
  
<span data-ttu-id="9cf52-577">UniqueId</span><span class="sxs-lookup"><span data-stu-id="9cf52-577">uniqueid#</span></span>
  
<span data-ttu-id="9cf52-578">DNI</span><span class="sxs-lookup"><span data-stu-id="9cf52-578">dni#</span></span>
  
<span data-ttu-id="9cf52-579">nationalid#</span><span class="sxs-lookup"><span data-stu-id="9cf52-579">nationalid#</span></span>
  
<span data-ttu-id="9cf52-580">nie</span><span class="sxs-lookup"><span data-stu-id="9cf52-580">nie#</span></span>
  
<span data-ttu-id="9cf52-581">nie</span><span class="sxs-lookup"><span data-stu-id="9cf52-581">nie</span></span>
  
<span data-ttu-id="9cf52-582">nienúmero#</span><span class="sxs-lookup"><span data-stu-id="9cf52-582">nienúmero#</span></span>
  
<span data-ttu-id="9cf52-583">nie número</span><span class="sxs-lookup"><span data-stu-id="9cf52-583">nie número</span></span>
  
<span data-ttu-id="9cf52-584">documento Nacional de Identidad</span><span class="sxs-lookup"><span data-stu-id="9cf52-584">documento nacional de identidad</span></span>
  
<span data-ttu-id="9cf52-585">Identidad único</span><span class="sxs-lookup"><span data-stu-id="9cf52-585">identidad único</span></span>
  
<span data-ttu-id="9cf52-586">número Nacional Identidad</span><span class="sxs-lookup"><span data-stu-id="9cf52-586">número nacional identidad</span></span>
  
<span data-ttu-id="9cf52-587">DNI número</span><span class="sxs-lookup"><span data-stu-id="9cf52-587">dni número</span></span>
  
<span data-ttu-id="9cf52-588">dninúmero#</span><span class="sxs-lookup"><span data-stu-id="9cf52-588">dninúmero#</span></span>
  
<span data-ttu-id="9cf52-589">identidadúnico#</span><span class="sxs-lookup"><span data-stu-id="9cf52-589">identidadúnico#</span></span>
  
## <a name="sweden"></a><span data-ttu-id="9cf52-590">Svezia</span><span class="sxs-lookup"><span data-stu-id="9cf52-590">Sweden</span></span>

<span data-ttu-id="9cf52-591">Per informazioni dettagliate, vedere la sezione "Sweden National ID" per [individuare i tipi di informazioni riservate](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="9cf52-591">For details, see the section "Sweden National ID" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="9cf52-592">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9cf52-592">See also</span></span>

[<span data-ttu-id="9cf52-593">Cosa individuano le tipologie di informazioni sensibili</span><span class="sxs-lookup"><span data-stu-id="9cf52-593">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)

