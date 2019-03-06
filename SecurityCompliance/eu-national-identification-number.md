---
title: Numero di identificazione nazionale dell'Unione europea
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 8/17/2018
ms.audience: Admin
ms.topic: reference
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
description: In questo argomento viene illustrato l'aspetto di un criterio di prevenzione della perdita di dati (DLP) quando viene rilevato il tipo di informazioni riservate del numero di identificazione nazionale dell'Unione europea. Questo tipo di informazioni riservate definisce modelli, parole chiave e altre evidenze diverse per ogni paese.
ms.openlocfilehash: afae2c3fa54fe5fcd93990cdf5797f5517c46202
ms.sourcegitcommit: ed822a776d3419853453583e882f3c61ca26d4b2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/05/2019
ms.locfileid: "30410971"
---
# <a name="eu-national-identification-number"></a><span data-ttu-id="2dfdb-104">Numero di identificazione nazionale dell'Unione europea</span><span class="sxs-lookup"><span data-stu-id="2dfdb-104">EU National Identification Number</span></span>

<span data-ttu-id="2dfdb-105">In questo argomento viene illustrato l'aspetto di un criterio di prevenzione della perdita di dati (DLP) quando viene rilevato il tipo di informazioni riservate del numero di identificazione nazionale dell'Unione europea.</span><span class="sxs-lookup"><span data-stu-id="2dfdb-105">This topic shows what a data loss prevention (DLP) policy looks for when it detects the EU National Identification Number sensitive information type.</span></span> <span data-ttu-id="2dfdb-106">Questo tipo di informazioni riservate definisce modelli, parole chiave e altre evidenze diverse per ogni paese.</span><span class="sxs-lookup"><span data-stu-id="2dfdb-106">This sensitive information type defines different patterns, keywords, and other evidence for each country.</span></span>
  
## <a name="austria"></a><span data-ttu-id="2dfdb-107">Austria</span><span class="sxs-lookup"><span data-stu-id="2dfdb-107">Austria</span></span>

### <a name="format"></a><span data-ttu-id="2dfdb-108">Formato</span><span class="sxs-lookup"><span data-stu-id="2dfdb-108">Format</span></span>

<span data-ttu-id="2dfdb-109">Combinazione A 24 caratteri di lettere, cifre e caratteri speciali</span><span class="sxs-lookup"><span data-stu-id="2dfdb-109">A 24-character combination of letters, digits, and special characters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="2dfdb-110">Modello</span><span class="sxs-lookup"><span data-stu-id="2dfdb-110">Pattern</span></span>

<span data-ttu-id="2dfdb-111">24 caratteri:</span><span class="sxs-lookup"><span data-stu-id="2dfdb-111">24 characters:</span></span>
  
-  <span data-ttu-id="2dfdb-112">22 lettere (senza distinzione tra maiuscole e minuscole), cifre, barre rovesciate, barre o segni più</span><span class="sxs-lookup"><span data-stu-id="2dfdb-112">22 letters (not case-sensitive), digits, backslashes, forward slashes, or plus signs</span></span> 
    
- <span data-ttu-id="2dfdb-113">Due lettere (senza distinzione tra maiuscole e minuscole), cifre, barre rovesciate, barre, segni più o segni uguali</span><span class="sxs-lookup"><span data-stu-id="2dfdb-113">Two letters (not case-sensitive), digits, backslashes, forward slashes, plus signs, or equal signs</span></span>
    
### <a name="checksum"></a><span data-ttu-id="2dfdb-114">Checksum</span><span class="sxs-lookup"><span data-stu-id="2dfdb-114">Checksum</span></span>

<span data-ttu-id="2dfdb-115">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="2dfdb-115">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="2dfdb-116">Definizione</span><span class="sxs-lookup"><span data-stu-id="2dfdb-116">Definition</span></span>

<span data-ttu-id="2dfdb-117">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="2dfdb-117">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="2dfdb-118">L'espressione `Regex_austria_eu_national_id_card` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="2dfdb-118">The regular expression  `Regex_austria_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="2dfdb-119">Viene trovata una `Keywords_austria_eu_national_id_card` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="2dfdb-119">A keyword from  `Keywords_austria_eu_national_id_card` is found.</span></span> 
    
```
 
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_austria_eu_national_id_card" />
          <Match idRef="Keywords_austria_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="2dfdb-120">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="2dfdb-120">Keywords</span></span>

#### <a name="keywordsaustriaeunationalidcard"></a><span data-ttu-id="2dfdb-121">Keywords_austria_eu_national_id_card</span><span class="sxs-lookup"><span data-stu-id="2dfdb-121">Keywords_austria_eu_national_id_card</span></span>

<span data-ttu-id="2dfdb-122">numero d'identità austriaco</span><span class="sxs-lookup"><span data-stu-id="2dfdb-122">austrian identity number</span></span>
  
<span data-ttu-id="2dfdb-123">numero di identità nazionale</span><span class="sxs-lookup"><span data-stu-id="2dfdb-123">national identity number</span></span>
  
<span data-ttu-id="2dfdb-124">numero di identità</span><span class="sxs-lookup"><span data-stu-id="2dfdb-124">identity number</span></span>
  
<span data-ttu-id="2dfdb-125">national id</span><span class="sxs-lookup"><span data-stu-id="2dfdb-125">national id</span></span>
  
<span data-ttu-id="2dfdb-126">Personalausweis Republik Österreich</span><span class="sxs-lookup"><span data-stu-id="2dfdb-126">personalausweis republik österreich</span></span>
  
## <a name="belgium"></a><span data-ttu-id="2dfdb-127">Belgio</span><span class="sxs-lookup"><span data-stu-id="2dfdb-127">Belgium</span></span>

<span data-ttu-id="2dfdb-128">Per informazioni dettagliate, vedere la sezione "numero nazionale belga" in [che cosa cercano i tipi di informazioni riservate](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="2dfdb-128">For details, see the section "Belgium National Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="bulgaria"></a><span data-ttu-id="2dfdb-129">Bulgaria</span><span class="sxs-lookup"><span data-stu-id="2dfdb-129">Bulgaria</span></span>

### <a name="format"></a><span data-ttu-id="2dfdb-130">Formato</span><span class="sxs-lookup"><span data-stu-id="2dfdb-130">Format</span></span>

<span data-ttu-id="2dfdb-131">Dieci cifre senza spazi e delimitatori</span><span class="sxs-lookup"><span data-stu-id="2dfdb-131">Ten digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="2dfdb-132">Modello</span><span class="sxs-lookup"><span data-stu-id="2dfdb-132">Pattern</span></span>

<span data-ttu-id="2dfdb-133">Dieci cifre senza spazi e delimitatori</span><span class="sxs-lookup"><span data-stu-id="2dfdb-133">Ten digits without spaces and delimiters</span></span>
  
-  <span data-ttu-id="2dfdb-134">Sei cifre che corrispondono alla data di nascita (AAMMGG)</span><span class="sxs-lookup"><span data-stu-id="2dfdb-134">Six digits that correspond to the birth date (YYMMDD)</span></span> 
    
- <span data-ttu-id="2dfdb-135">Due cifre che corrispondono all'ordine di nascita</span><span class="sxs-lookup"><span data-stu-id="2dfdb-135">Two digits that correspond to the birth order</span></span>
    
- <span data-ttu-id="2dfdb-136">Una cifra che corrisponde al sesso: una cifra pari per il maschio e una cifra dispari per la femmina</span><span class="sxs-lookup"><span data-stu-id="2dfdb-136">One digit that corresponds to gender: An even digit for male and an odd digit for female</span></span>
    
- <span data-ttu-id="2dfdb-137">Una cifra di controllo</span><span class="sxs-lookup"><span data-stu-id="2dfdb-137">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="2dfdb-138">Checksum</span><span class="sxs-lookup"><span data-stu-id="2dfdb-138">Checksum</span></span>

<span data-ttu-id="2dfdb-139">Sì</span><span class="sxs-lookup"><span data-stu-id="2dfdb-139">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="2dfdb-140">Definizione</span><span class="sxs-lookup"><span data-stu-id="2dfdb-140">Definition</span></span>

<span data-ttu-id="2dfdb-141">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="2dfdb-141">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="2dfdb-142">La funzione `Func_bulgaria_national_number` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="2dfdb-142">The function  `Func_bulgaria_national_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="2dfdb-143">Viene trovata una `Keywords_bulgaria_national_number` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="2dfdb-143">A keyword from  `Keywords_bulgaria_national_number` is found.</span></span> 
    
<span data-ttu-id="2dfdb-144">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="2dfdb-144">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="2dfdb-145">La funzione `Func_bulgaria_national_number` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="2dfdb-145">The function  `Func_bulgaria_national_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="2dfdb-146">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="2dfdb-146">Keywords</span></span>

#### <a name="keywordsbulgarianationalnumber"></a><span data-ttu-id="2dfdb-147">Keywords_bulgaria_national_number</span><span class="sxs-lookup"><span data-stu-id="2dfdb-147">Keywords_bulgaria_national_number</span></span>

<span data-ttu-id="2dfdb-148">EGN</span><span class="sxs-lookup"><span data-stu-id="2dfdb-148">egn</span></span>
  
<span data-ttu-id="2dfdb-149">EGN</span><span class="sxs-lookup"><span data-stu-id="2dfdb-149">egn#</span></span>
  
<span data-ttu-id="2dfdb-150">numero nazionale bulgaro</span><span class="sxs-lookup"><span data-stu-id="2dfdb-150">bulgarian national number</span></span>
  
<span data-ttu-id="2dfdb-151">numero nazionale</span><span class="sxs-lookup"><span data-stu-id="2dfdb-151">national number</span></span>
  
<span data-ttu-id="2dfdb-152">social security number</span><span class="sxs-lookup"><span data-stu-id="2dfdb-152">social security number</span></span>
  
<span data-ttu-id="2dfdb-153">nationalnumber #</span><span class="sxs-lookup"><span data-stu-id="2dfdb-153">nationalnumber#</span></span>
  
<span data-ttu-id="2dfdb-154">SSN</span><span class="sxs-lookup"><span data-stu-id="2dfdb-154">ssn#</span></span>
  
<span data-ttu-id="2dfdb-155">SSN</span><span class="sxs-lookup"><span data-stu-id="2dfdb-155">ssn</span></span>
  
<span data-ttu-id="2dfdb-156">nationalnumber</span><span class="sxs-lookup"><span data-stu-id="2dfdb-156">nationalnumber</span></span>
  
<span data-ttu-id="2dfdb-157">BNN</span><span class="sxs-lookup"><span data-stu-id="2dfdb-157">bnn#</span></span>
  
<span data-ttu-id="2dfdb-158">BNN</span><span class="sxs-lookup"><span data-stu-id="2dfdb-158">bnn</span></span>
  
<span data-ttu-id="2dfdb-159">numero ID personale</span><span class="sxs-lookup"><span data-stu-id="2dfdb-159">personal id number</span></span>
  
<span data-ttu-id="2dfdb-160">personalidnumber #</span><span class="sxs-lookup"><span data-stu-id="2dfdb-160">personalidnumber#</span></span>
  
<span data-ttu-id="2dfdb-161">единен граждански Номер</span><span class="sxs-lookup"><span data-stu-id="2dfdb-161">единен граждански номер</span></span>
  
<span data-ttu-id="2dfdb-162">grazhdanski nomer</span><span class="sxs-lookup"><span data-stu-id="2dfdb-162">edinen grazhdanski nomer</span></span>
  
<span data-ttu-id="2dfdb-163">егн</span><span class="sxs-lookup"><span data-stu-id="2dfdb-163">егн</span></span>
  
<span data-ttu-id="2dfdb-164">егн #</span><span class="sxs-lookup"><span data-stu-id="2dfdb-164">егн#</span></span>
  
## <a name="croatia"></a><span data-ttu-id="2dfdb-165">Croazia</span><span class="sxs-lookup"><span data-stu-id="2dfdb-165">Croatia</span></span>

<span data-ttu-id="2dfdb-166">Per informazioni dettagliate, vedere la sezione "numero di identità della Croazia" in [che cosa cercano i tipi di informazioni riservate](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="2dfdb-166">For details, see the section "Croatia Identity Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="cyprus"></a><span data-ttu-id="2dfdb-167">Cipro</span><span class="sxs-lookup"><span data-stu-id="2dfdb-167">Cyprus</span></span>

### <a name="format"></a><span data-ttu-id="2dfdb-168">Formato</span><span class="sxs-lookup"><span data-stu-id="2dfdb-168">Format</span></span>

<span data-ttu-id="2dfdb-169">Dieci cifre senza spazi e delimitatori</span><span class="sxs-lookup"><span data-stu-id="2dfdb-169">Ten digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="2dfdb-170">Modello</span><span class="sxs-lookup"><span data-stu-id="2dfdb-170">Pattern</span></span>

 <span data-ttu-id="2dfdb-171">Dieci cifre</span><span class="sxs-lookup"><span data-stu-id="2dfdb-171">Ten digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="2dfdb-172">Checksum</span><span class="sxs-lookup"><span data-stu-id="2dfdb-172">Checksum</span></span>

<span data-ttu-id="2dfdb-173">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="2dfdb-173">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="2dfdb-174">Definizione</span><span class="sxs-lookup"><span data-stu-id="2dfdb-174">Definition</span></span>

<span data-ttu-id="2dfdb-175">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="2dfdb-175">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="2dfdb-176">L'espressione `Regex_cyprus_eu_national_id_card` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="2dfdb-176">The regular expression  `Regex_cyprus_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="2dfdb-177">Viene trovata una `Keywords_cyprus_eu_national_id_card` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="2dfdb-177">A keyword from  `Keywords_cyprus_eu_national_id_card` is found.</span></span> 
    
```
 
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_cyprus_eu_national_id_card" />
          <Match idRef="Keywords_cyprus_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="2dfdb-178">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="2dfdb-178">Keywords</span></span>

#### <a name="keywordscypruseunationalidcard"></a><span data-ttu-id="2dfdb-179">Keywords_cyprus_eu_national_id_card</span><span class="sxs-lookup"><span data-stu-id="2dfdb-179">Keywords_cyprus_eu_national_id_card</span></span>

<span data-ttu-id="2dfdb-180">numero di carta di identità</span><span class="sxs-lookup"><span data-stu-id="2dfdb-180">id card number</span></span>
  
<span data-ttu-id="2dfdb-181">national identification number</span><span class="sxs-lookup"><span data-stu-id="2dfdb-181">national identification number</span></span>
  
<span data-ttu-id="2dfdb-182">numero ID personale</span><span class="sxs-lookup"><span data-stu-id="2dfdb-182">personal id number</span></span>
  
<span data-ttu-id="2dfdb-183">numero di carta di identità</span><span class="sxs-lookup"><span data-stu-id="2dfdb-183">identity card number</span></span>
  
<span data-ttu-id="2dfdb-184">ταυτοτητασ</span><span class="sxs-lookup"><span data-stu-id="2dfdb-184">ταυτοτητασ</span></span>
  
## <a name="czech-republic"></a><span data-ttu-id="2dfdb-185">Repubblica Ceca</span><span class="sxs-lookup"><span data-stu-id="2dfdb-185">Czech Republic</span></span>

<span data-ttu-id="2dfdb-186">Per informazioni dettagliate, vedere la sezione "numero di identità nazionale ceco" in [quello che i tipi di informazioni riservate cercano](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="2dfdb-186">For details, see the section "Czech National Identity Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="denmark"></a><span data-ttu-id="2dfdb-187">Danimarca</span><span class="sxs-lookup"><span data-stu-id="2dfdb-187">Denmark</span></span>

<span data-ttu-id="2dfdb-188">Per informazioni dettagliate, vedere la sezione "numero di identificazione personale danese" in [che cosa cercano i tipi di informazioni riservate](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="2dfdb-188">For details, see the section "Denmark Personal Identification Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="estonia"></a><span data-ttu-id="2dfdb-189">Estonia</span><span class="sxs-lookup"><span data-stu-id="2dfdb-189">Estonia</span></span>

### <a name="format"></a><span data-ttu-id="2dfdb-190">Formato</span><span class="sxs-lookup"><span data-stu-id="2dfdb-190">Format</span></span>

<span data-ttu-id="2dfdb-191">11 cifre senza spazi e delimitatori</span><span class="sxs-lookup"><span data-stu-id="2dfdb-191">11 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="2dfdb-192">Modello</span><span class="sxs-lookup"><span data-stu-id="2dfdb-192">Pattern</span></span>

<span data-ttu-id="2dfdb-193">11 cifre:</span><span class="sxs-lookup"><span data-stu-id="2dfdb-193">11 digits:</span></span>
  
- <span data-ttu-id="2dfdb-194">Una cifra che corrisponde al sesso e al secolo di nascita (numero dispari maschio, anche numero femmina; 1-2: XIX secolo; 3-4: XX secolo; 5-6: XXI secolo)</span><span class="sxs-lookup"><span data-stu-id="2dfdb-194">One digit that corresponds to sex and century of birth (odd number male, even number female; 1-2: 19th century; 3-4: 20th century; 5-6: 21st century)</span></span>
    
- <span data-ttu-id="2dfdb-195">Sei cifre che corrispondono alla data di nascita (AAMMGG)</span><span class="sxs-lookup"><span data-stu-id="2dfdb-195">Six digits that correspond to date of birth (YYMMDD)</span></span>
    
- <span data-ttu-id="2dfdb-196">Tre cifre che corrispondono a un numero di serie che separa le persone nate nella stessa data</span><span class="sxs-lookup"><span data-stu-id="2dfdb-196">Three digits that correspond to a serial number separating persons born on the same date</span></span>
    
- <span data-ttu-id="2dfdb-197">Una cifra di controllo</span><span class="sxs-lookup"><span data-stu-id="2dfdb-197">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="2dfdb-198">Checksum</span><span class="sxs-lookup"><span data-stu-id="2dfdb-198">Checksum</span></span>

<span data-ttu-id="2dfdb-199">Sì</span><span class="sxs-lookup"><span data-stu-id="2dfdb-199">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="2dfdb-200">Definizione</span><span class="sxs-lookup"><span data-stu-id="2dfdb-200">Definition</span></span>

<span data-ttu-id="2dfdb-201">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="2dfdb-201">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="2dfdb-202">La funzione `Func_estonia_eu_national_id_card` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="2dfdb-202">The function  `Func_estonia_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="2dfdb-203">Viene trovata una `Keywords_estonia_eu_national_id_card` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="2dfdb-203">A keyword from  `Keywords_estonia_eu_national_id_card` is found.</span></span> 
    
<span data-ttu-id="2dfdb-204">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="2dfdb-204">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="2dfdb-205">La funzione `Func_estonia_eu_national_id_card` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="2dfdb-205">The function  `Func_estonia_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="2dfdb-206">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="2dfdb-206">Keywords</span></span>

#### <a name="keywordsestoniaeunationalidcard"></a><span data-ttu-id="2dfdb-207">Keywords_estonia_eu_national_id_card</span><span class="sxs-lookup"><span data-stu-id="2dfdb-207">Keywords_estonia_eu_national_id_card</span></span>

<span data-ttu-id="2dfdb-208">codice di identificazione personale</span><span class="sxs-lookup"><span data-stu-id="2dfdb-208">personal identification code</span></span>
  
<span data-ttu-id="2dfdb-209">numero di identificazione personale</span><span class="sxs-lookup"><span data-stu-id="2dfdb-209">personal identification number</span></span>
  
<span data-ttu-id="2dfdb-210">national identification number</span><span class="sxs-lookup"><span data-stu-id="2dfdb-210">national identification number</span></span>
  
<span data-ttu-id="2dfdb-211">numero nazionale</span><span class="sxs-lookup"><span data-stu-id="2dfdb-211">national number</span></span>
  
<span data-ttu-id="2dfdb-212">numero ID personale</span><span class="sxs-lookup"><span data-stu-id="2dfdb-212">personal id number</span></span>
  
<span data-ttu-id="2dfdb-213">personalidnumber #</span><span class="sxs-lookup"><span data-stu-id="2dfdb-213">personalidnumber#</span></span>
  
<span data-ttu-id="2dfdb-214">IK</span><span class="sxs-lookup"><span data-stu-id="2dfdb-214">ik</span></span>
  
<span data-ttu-id="2dfdb-215">isikukood</span><span class="sxs-lookup"><span data-stu-id="2dfdb-215">isikukood</span></span>
  
<span data-ttu-id="2dfdb-216">ID-kaart</span><span class="sxs-lookup"><span data-stu-id="2dfdb-216">id-kaart</span></span>
  
## <a name="finland"></a><span data-ttu-id="2dfdb-217">Finlandia</span><span class="sxs-lookup"><span data-stu-id="2dfdb-217">Finland</span></span>

<span data-ttu-id="2dfdb-218">Per informazioni dettagliate, vedere la sezione "Finlandia National ID" in [quello che i tipi di informazioni riservate cercano](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="2dfdb-218">For details, see the section "Finland National ID" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="france"></a><span data-ttu-id="2dfdb-219">Francia</span><span class="sxs-lookup"><span data-stu-id="2dfdb-219">France</span></span>

<span data-ttu-id="2dfdb-220">Per informazioni dettagliate, vedere la sezione "Francia National ID Card (CNI)" in [che cosa cercano i tipi di informazioni riservate](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="2dfdb-220">For details, see the section "France National ID Card (CNI)" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="germany"></a><span data-ttu-id="2dfdb-221">Germania</span><span class="sxs-lookup"><span data-stu-id="2dfdb-221">Germany</span></span>

<span data-ttu-id="2dfdb-222">Per informazioni dettagliate, vedere la sezione "Germania identità numero di carta" in [che cosa cercano i tipi di informazioni riservate](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="2dfdb-222">For details, see the section "Germany Identity Card Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="greece"></a><span data-ttu-id="2dfdb-223">Grecia</span><span class="sxs-lookup"><span data-stu-id="2dfdb-223">Greece</span></span>

<span data-ttu-id="2dfdb-224">Per informazioni dettagliate, vedere la sezione "Grecia National ID Card" in [quello che cercano i tipi di informazioni riservate](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="2dfdb-224">For details, see the section "Greece National ID Card" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="hungary"></a><span data-ttu-id="2dfdb-225">Ungheria</span><span class="sxs-lookup"><span data-stu-id="2dfdb-225">Hungary</span></span>

### <a name="format"></a><span data-ttu-id="2dfdb-226">Formato</span><span class="sxs-lookup"><span data-stu-id="2dfdb-226">Format</span></span>

<span data-ttu-id="2dfdb-227">11 cifre</span><span class="sxs-lookup"><span data-stu-id="2dfdb-227">11 digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="2dfdb-228">Modello</span><span class="sxs-lookup"><span data-stu-id="2dfdb-228">Pattern</span></span>

<span data-ttu-id="2dfdb-229">11 cifre:</span><span class="sxs-lookup"><span data-stu-id="2dfdb-229">11 digits:</span></span>
  
-  <span data-ttu-id="2dfdb-230">Una cifra che corrisponde al sesso (1-maschio, 2-Femmina, altri numeri sono possibili anche per i cittadini nati prima del 1900 o cittadini con doppia cittadinanza)</span><span class="sxs-lookup"><span data-stu-id="2dfdb-230">One digit that corresponds to gender (1-male, 2-female, other numbers are also possible for citizens born before 1900 or citizens with double citizenship)</span></span> 
    
- <span data-ttu-id="2dfdb-231">Sei cifre che corrispondono alla data di nascita (AAMMGG)</span><span class="sxs-lookup"><span data-stu-id="2dfdb-231">Six digits that correspond to birth date (YYMMDD)</span></span>
    
- <span data-ttu-id="2dfdb-232">Tre cifre che corrispondono a un numero di serie</span><span class="sxs-lookup"><span data-stu-id="2dfdb-232">Three digits that correspond to a serial number</span></span>
    
- <span data-ttu-id="2dfdb-233">Una cifra di controllo</span><span class="sxs-lookup"><span data-stu-id="2dfdb-233">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="2dfdb-234">Checksum</span><span class="sxs-lookup"><span data-stu-id="2dfdb-234">Checksum</span></span>

<span data-ttu-id="2dfdb-235">Sì</span><span class="sxs-lookup"><span data-stu-id="2dfdb-235">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="2dfdb-236">Definizione</span><span class="sxs-lookup"><span data-stu-id="2dfdb-236">Definition</span></span>

<span data-ttu-id="2dfdb-237">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="2dfdb-237">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="2dfdb-238">La funzione `Func_hungary_eu_national_id_card` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="2dfdb-238">The function  `Func_hungary_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="2dfdb-239">Viene trovata una `Keywords_hungary_eu_national_id_card` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="2dfdb-239">A keyword from  `Keywords_hungary_eu_national_id_card` is found.</span></span> 
    
<span data-ttu-id="2dfdb-240">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="2dfdb-240">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="2dfdb-241">La funzione `Func_hungary_eu_national_id_card` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="2dfdb-241">The function  `Func_hungary_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="2dfdb-242">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="2dfdb-242">Keywords</span></span>

#### <a name="keywordshungaryeunationalidcard"></a><span data-ttu-id="2dfdb-243">Keywords_hungary_eu_national_id_card</span><span class="sxs-lookup"><span data-stu-id="2dfdb-243">Keywords_hungary_eu_national_id_card</span></span>

<span data-ttu-id="2dfdb-244">numero di identificazione personale</span><span class="sxs-lookup"><span data-stu-id="2dfdb-244">personal identification number</span></span>
  
<span data-ttu-id="2dfdb-245">identification number</span><span class="sxs-lookup"><span data-stu-id="2dfdb-245">identification number</span></span>
  
<span data-ttu-id="2dfdb-246">numero ID personale</span><span class="sxs-lookup"><span data-stu-id="2dfdb-246">personal id number</span></span>
  
<span data-ttu-id="2dfdb-247">személyazonosító igazolvány</span><span class="sxs-lookup"><span data-stu-id="2dfdb-247">személyazonosító igazolvány</span></span>
  
## <a name="ireland"></a><span data-ttu-id="2dfdb-248">Irlanda</span><span class="sxs-lookup"><span data-stu-id="2dfdb-248">Ireland</span></span>

### <a name="format"></a><span data-ttu-id="2dfdb-249">Formato</span><span class="sxs-lookup"><span data-stu-id="2dfdb-249">Format</span></span>

<span data-ttu-id="2dfdb-250">Una combinazione di nove caratteri di lettere, cifre e uno spazio nel modello specificato</span><span class="sxs-lookup"><span data-stu-id="2dfdb-250">A nine-character combination of letters, digits, and a space in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="2dfdb-251">Modello</span><span class="sxs-lookup"><span data-stu-id="2dfdb-251">Pattern</span></span>

<span data-ttu-id="2dfdb-252">Una combinazione di nove caratteri di lettere, cifre e uno spazio nel modello specificato</span><span class="sxs-lookup"><span data-stu-id="2dfdb-252">A nine-character combination of letters, digits, and a space in the specified pattern</span></span>
  
<span data-ttu-id="2dfdb-253">Dal 01 gennaio 2013 a oggi:</span><span class="sxs-lookup"><span data-stu-id="2dfdb-253">From 01 January 2013 to now:</span></span>
  
-  <span data-ttu-id="2dfdb-254">Sette cifre</span><span class="sxs-lookup"><span data-stu-id="2dfdb-254">Seven digits</span></span> 
    
- <span data-ttu-id="2dfdb-255">Una cifra di controllo</span><span class="sxs-lookup"><span data-stu-id="2dfdb-255">One check digit</span></span>
    
- <span data-ttu-id="2dfdb-256">Uno spazio o la lettera maiuscola "W" (distinzione tra maiuscole e minuscole)</span><span class="sxs-lookup"><span data-stu-id="2dfdb-256">One space or the uppercase letter "W" (Case sensitive)</span></span>
    
<span data-ttu-id="2dfdb-257">Prima del 1 ° gennaio 2013:</span><span class="sxs-lookup"><span data-stu-id="2dfdb-257">Prior to 01 January 2013:</span></span>
  
-  <span data-ttu-id="2dfdb-258">Sette cifre</span><span class="sxs-lookup"><span data-stu-id="2dfdb-258">Seven digits</span></span> 
    
- <span data-ttu-id="2dfdb-259">Una cifra di controllo</span><span class="sxs-lookup"><span data-stu-id="2dfdb-259">One check digit</span></span>
    
- <span data-ttu-id="2dfdb-260">Uno spazio o una lettera maiuscola (distinzione tra maiuscole e minuscole)</span><span class="sxs-lookup"><span data-stu-id="2dfdb-260">One space or an uppercase letter (Case sensitive)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="2dfdb-261">Checksum</span><span class="sxs-lookup"><span data-stu-id="2dfdb-261">Checksum</span></span>

<span data-ttu-id="2dfdb-262">Sì</span><span class="sxs-lookup"><span data-stu-id="2dfdb-262">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="2dfdb-263">Definizione</span><span class="sxs-lookup"><span data-stu-id="2dfdb-263">Definition</span></span>

<span data-ttu-id="2dfdb-264">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="2dfdb-264">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="2dfdb-265">La funzione trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="2dfdb-265">The function finds content that matches the pattern.</span></span>
    
- <span data-ttu-id="2dfdb-266">Viene trovata una parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="2dfdb-266">A keyword from is found.</span></span>
    
<span data-ttu-id="2dfdb-267">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="2dfdb-267">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="2dfdb-268">La funzione trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="2dfdb-268">The function finds content that matches the pattern.</span></span>
    
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

### <a name="keywords"></a><span data-ttu-id="2dfdb-269">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="2dfdb-269">Keywords</span></span>

#### <a name="keywordsirelandeunationalidcard"></a><span data-ttu-id="2dfdb-270">Keywords_ireland_eu_national_id_card</span><span class="sxs-lookup"><span data-stu-id="2dfdb-270">Keywords_ireland_eu_national_id_card</span></span>

<span data-ttu-id="2dfdb-271">numero di servizio pubblico personale</span><span class="sxs-lookup"><span data-stu-id="2dfdb-271">personal public service number</span></span>
  
<span data-ttu-id="2dfdb-272">PPS No</span><span class="sxs-lookup"><span data-stu-id="2dfdb-272">pps no</span></span>
  
<span data-ttu-id="2dfdb-273">reddito e numero di previdenza sociale</span><span class="sxs-lookup"><span data-stu-id="2dfdb-273">revenue and social insurance number</span></span>
  
<span data-ttu-id="2dfdb-274">RSI No</span><span class="sxs-lookup"><span data-stu-id="2dfdb-274">rsi no</span></span>
  
<span data-ttu-id="2dfdb-275">numero di identificazione personale</span><span class="sxs-lookup"><span data-stu-id="2dfdb-275">personal identification number</span></span>
  
<span data-ttu-id="2dfdb-276">identification number</span><span class="sxs-lookup"><span data-stu-id="2dfdb-276">identification number</span></span>
  
<span data-ttu-id="2dfdb-277">numero ID personale</span><span class="sxs-lookup"><span data-stu-id="2dfdb-277">personal id number</span></span>
  
<span data-ttu-id="2dfdb-278">uimhir phearsanta Seirbhíse poiblí</span><span class="sxs-lookup"><span data-stu-id="2dfdb-278">uimhir phearsanta seirbhíse poiblí</span></span>
  
<span data-ttu-id="2dfdb-279">uimh.</span><span class="sxs-lookup"><span data-stu-id="2dfdb-279">uimh.</span></span> <span data-ttu-id="2dfdb-280">PSP</span><span class="sxs-lookup"><span data-stu-id="2dfdb-280">psp</span></span>
  
## <a name="italy"></a><span data-ttu-id="2dfdb-281">Italia</span><span class="sxs-lookup"><span data-stu-id="2dfdb-281">Italy</span></span>

### <a name="format"></a><span data-ttu-id="2dfdb-282">Formato</span><span class="sxs-lookup"><span data-stu-id="2dfdb-282">Format</span></span>

<span data-ttu-id="2dfdb-283">Una combinazione di 16 caratteri di lettere e cifre nel modello specificato</span><span class="sxs-lookup"><span data-stu-id="2dfdb-283">A 16-character combination of letters and digits in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="2dfdb-284">Modello</span><span class="sxs-lookup"><span data-stu-id="2dfdb-284">Pattern</span></span>

<span data-ttu-id="2dfdb-285">Combinazione di lettere e cifre di 16 caratteri:</span><span class="sxs-lookup"><span data-stu-id="2dfdb-285">A 16-character combination of letters and digits:</span></span>
  
- <span data-ttu-id="2dfdb-286">Tre lettere che corrispondono alle prime tre consonanti del nome di famiglia</span><span class="sxs-lookup"><span data-stu-id="2dfdb-286">Three letters that correspond to the first three consonants in the family name</span></span>
    
- <span data-ttu-id="2dfdb-287">Tre lettere che corrispondono alla prima, terza e quarta consonante del primo nome</span><span class="sxs-lookup"><span data-stu-id="2dfdb-287">Three letters that correspond to the first, third, and fourth consonants in the first name</span></span>
    
- <span data-ttu-id="2dfdb-288">Due cifre che corrispondono alle ultime cifre dell'anno di nascita</span><span class="sxs-lookup"><span data-stu-id="2dfdb-288">Two digits that correspond to the last digits of the birth year</span></span>
    
- <span data-ttu-id="2dfdb-289">Una lettera che corrisponde alla lettera per il mese di nascita: le lettere vengono utilizzate in ordine alfabetico, ma vengono utilizzate solo le lettere da a a E, H, L, M, P, R e T (pertanto, gennaio è A e ottobre è R)</span><span class="sxs-lookup"><span data-stu-id="2dfdb-289">One letter that corresponds to the letter for the month of birth—letters are used in alphabetical order, but only the letters A to E, H, L, M, P, R to T are used (thus, January is A and October is R)</span></span>
    
- <span data-ttu-id="2dfdb-290">Due cifre che corrispondono al giorno del mese di nascita, al fine di distinguere tra i sessi, 40 viene aggiunto al giorno di nascita per le donne</span><span class="sxs-lookup"><span data-stu-id="2dfdb-290">Two digits that correspond to the day of the month of birth—in order to differentiate between genders, 40 is added to the day of birth for women</span></span>
    
- <span data-ttu-id="2dfdb-291">Quattro cifre che corrispondono al codice di area specifico per il comune in cui è nata la persona (i codici a livello nazionale vengono utilizzati per i paesi esteri)</span><span class="sxs-lookup"><span data-stu-id="2dfdb-291">Four digits that corresponds to the area code specific to the municipality where the person was born (country-wide codes are used for foreign countries)</span></span>
    
- <span data-ttu-id="2dfdb-292">Una cifra di parità</span><span class="sxs-lookup"><span data-stu-id="2dfdb-292">One parity digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="2dfdb-293">Checksum</span><span class="sxs-lookup"><span data-stu-id="2dfdb-293">Checksum</span></span>

<span data-ttu-id="2dfdb-294">Sì</span><span class="sxs-lookup"><span data-stu-id="2dfdb-294">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="2dfdb-295">Definizione</span><span class="sxs-lookup"><span data-stu-id="2dfdb-295">Definition</span></span>

<span data-ttu-id="2dfdb-296">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="2dfdb-296">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="2dfdb-297">La funzione `Func_italy_eu_national_id_card` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="2dfdb-297">The function  `Func_italy_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="2dfdb-298">Viene trovata una `Keywords_italy_eu_national_id_card` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="2dfdb-298">A keyword from  `Keywords_italy_eu_national_id_card` is found.</span></span> 
    
<span data-ttu-id="2dfdb-299">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="2dfdb-299">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="2dfdb-300">La funzione `Func_italy_eu_national_id_card` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="2dfdb-300">The function  `Func_italy_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="2dfdb-301">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="2dfdb-301">Keywords</span></span>

#### <a name="keywordsitalyeunationalidcard"></a><span data-ttu-id="2dfdb-302">Keywords_italy_eu_national_id_card</span><span class="sxs-lookup"><span data-stu-id="2dfdb-302">Keywords_italy_eu_national_id_card</span></span>

<span data-ttu-id="2dfdb-303">codice personale</span><span class="sxs-lookup"><span data-stu-id="2dfdb-303">personal code</span></span>
  
<span data-ttu-id="2dfdb-304">numero di codice personale</span><span class="sxs-lookup"><span data-stu-id="2dfdb-304">personal code number</span></span>
  
<span data-ttu-id="2dfdb-305">numero di certificato personale</span><span class="sxs-lookup"><span data-stu-id="2dfdb-305">personal certificate number</span></span>
  
<span data-ttu-id="2dfdb-306">codice fiscale</span><span class="sxs-lookup"><span data-stu-id="2dfdb-306">fiscal code</span></span>
  
<span data-ttu-id="2dfdb-307">personalcodeno #</span><span class="sxs-lookup"><span data-stu-id="2dfdb-307">personalcodeno#</span></span>
  
<span data-ttu-id="2dfdb-308">numero ID personale</span><span class="sxs-lookup"><span data-stu-id="2dfdb-308">personal id number</span></span>
  
<span data-ttu-id="2dfdb-309">codice ID personale</span><span class="sxs-lookup"><span data-stu-id="2dfdb-309">personal id code</span></span>
  
<span data-ttu-id="2dfdb-310">codice personale</span><span class="sxs-lookup"><span data-stu-id="2dfdb-310">codice personale</span></span>
  
<span data-ttu-id="2dfdb-311">Numero certificato personale</span><span class="sxs-lookup"><span data-stu-id="2dfdb-311">numero certificato personale</span></span>
  
<span data-ttu-id="2dfdb-312">numero personale</span><span class="sxs-lookup"><span data-stu-id="2dfdb-312">numero personale</span></span>
  
<span data-ttu-id="2dfdb-313">numero ID personale</span><span class="sxs-lookup"><span data-stu-id="2dfdb-313">numero id personale</span></span>
  
<span data-ttu-id="2dfdb-314">codice ID personale</span><span class="sxs-lookup"><span data-stu-id="2dfdb-314">codice id personale</span></span>
  
<span data-ttu-id="2dfdb-315">codice fiscale</span><span class="sxs-lookup"><span data-stu-id="2dfdb-315">codice fiscale</span></span>
  
## <a name="italy"></a><span data-ttu-id="2dfdb-316">Italia</span><span class="sxs-lookup"><span data-stu-id="2dfdb-316">Italy</span></span>

### <a name="format"></a><span data-ttu-id="2dfdb-317">Formato</span><span class="sxs-lookup"><span data-stu-id="2dfdb-317">Format</span></span>

<span data-ttu-id="2dfdb-318">11 cifre e un trattino nel formato specificato</span><span class="sxs-lookup"><span data-stu-id="2dfdb-318">11 digits and a hyphen in the specified format</span></span>
  
### <a name="pattern"></a><span data-ttu-id="2dfdb-319">Modello</span><span class="sxs-lookup"><span data-stu-id="2dfdb-319">Pattern</span></span>

<span data-ttu-id="2dfdb-320">11 cifre e un trattino:</span><span class="sxs-lookup"><span data-stu-id="2dfdb-320">11 digits and a hyphen:</span></span>
  
-  <span data-ttu-id="2dfdb-321">Sei cifre che corrispondono alla data di nascita (GGMMAA)</span><span class="sxs-lookup"><span data-stu-id="2dfdb-321">Six digits that correspond to the birth date (DDMMYY)</span></span> 
    
- <span data-ttu-id="2dfdb-322">Una lineetta</span><span class="sxs-lookup"><span data-stu-id="2dfdb-322">A hyphen</span></span>
    
- <span data-ttu-id="2dfdb-323">Una cifra che corrisponde al secolo di nascita ("0" per il XIX secolo, "1" per il XX secolo e "2" per il XXI secolo)</span><span class="sxs-lookup"><span data-stu-id="2dfdb-323">One digit that corresponds to the century of birth ("0" for 19th century, "1" for 20th century, and "2" for 21st century)</span></span>
    
- <span data-ttu-id="2dfdb-324">Quattro cifre, generate in modo casuale</span><span class="sxs-lookup"><span data-stu-id="2dfdb-324">Four digits, randomly generated</span></span>
    
### <a name="checksum"></a><span data-ttu-id="2dfdb-325">Checksum</span><span class="sxs-lookup"><span data-stu-id="2dfdb-325">Checksum</span></span>

<span data-ttu-id="2dfdb-326">Sì</span><span class="sxs-lookup"><span data-stu-id="2dfdb-326">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="2dfdb-327">Definizione</span><span class="sxs-lookup"><span data-stu-id="2dfdb-327">Definition</span></span>

<span data-ttu-id="2dfdb-328">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="2dfdb-328">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="2dfdb-329">La funzione `Func_latvia_eu_national_id_card` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="2dfdb-329">The function  `Func_latvia_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="2dfdb-330">Viene trovata una `Keywords_latvia_eu_national_id_card` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="2dfdb-330">A keyword from  `Keywords_latvia_eu_national_id_card` is found.</span></span> 
    
<span data-ttu-id="2dfdb-331">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="2dfdb-331">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="2dfdb-332">La funzione `Func_latvia_eu_national_id_card` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="2dfdb-332">The function  `Func_latvia_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="2dfdb-333">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="2dfdb-333">Keywords</span></span>

#### <a name="keywordslatviaeunationalidcard"></a><span data-ttu-id="2dfdb-334">Keywords_latvia_eu_national_id_card</span><span class="sxs-lookup"><span data-stu-id="2dfdb-334">Keywords_latvia_eu_national_id_card</span></span>

<span data-ttu-id="2dfdb-335">codice personale</span><span class="sxs-lookup"><span data-stu-id="2dfdb-335">personal code</span></span>
  
<span data-ttu-id="2dfdb-336">numero di codice personale</span><span class="sxs-lookup"><span data-stu-id="2dfdb-336">personal code number</span></span>
  
<span data-ttu-id="2dfdb-337">numero di certificato personale</span><span class="sxs-lookup"><span data-stu-id="2dfdb-337">personal certificate number</span></span>
  
<span data-ttu-id="2dfdb-338">personalcodeno #</span><span class="sxs-lookup"><span data-stu-id="2dfdb-338">personalcodeno#</span></span>
  
<span data-ttu-id="2dfdb-339">numero ID personale</span><span class="sxs-lookup"><span data-stu-id="2dfdb-339">personal id number</span></span>
  
<span data-ttu-id="2dfdb-340">codice ID personale</span><span class="sxs-lookup"><span data-stu-id="2dfdb-340">personal id code</span></span>
  
<span data-ttu-id="2dfdb-341">personas Kods</span><span class="sxs-lookup"><span data-stu-id="2dfdb-341">personas kods</span></span>
  
## <a name="lithuania"></a><span data-ttu-id="2dfdb-342">Lituania</span><span class="sxs-lookup"><span data-stu-id="2dfdb-342">Lithuania</span></span>

### <a name="format"></a><span data-ttu-id="2dfdb-343">Formato</span><span class="sxs-lookup"><span data-stu-id="2dfdb-343">Format</span></span>

<span data-ttu-id="2dfdb-344">11 cifre senza spazi e delimitatori</span><span class="sxs-lookup"><span data-stu-id="2dfdb-344">11 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="2dfdb-345">Modello</span><span class="sxs-lookup"><span data-stu-id="2dfdb-345">Pattern</span></span>

<span data-ttu-id="2dfdb-346">11 cifre senza spazi e delimitatori:</span><span class="sxs-lookup"><span data-stu-id="2dfdb-346">11 digits without spaces and delimiters:</span></span>
  
- <span data-ttu-id="2dfdb-347">Una cifra corrispondente al sesso e al secolo della nascita della persona</span><span class="sxs-lookup"><span data-stu-id="2dfdb-347">One digit that corresponds to the person's gender and century of birth</span></span>
    
-  <span data-ttu-id="2dfdb-348">Sei cifre che corrispondono alla data di nascita (AAMMGG)</span><span class="sxs-lookup"><span data-stu-id="2dfdb-348">Six digits that correspond to birth date (YYMMDD)</span></span> 
    
- <span data-ttu-id="2dfdb-349">Tre cifre che corrispondono al numero di serie della data di nascita</span><span class="sxs-lookup"><span data-stu-id="2dfdb-349">Three digits that correspond to the serial number of the date of birth</span></span>
    
- <span data-ttu-id="2dfdb-350">Una cifra di controllo</span><span class="sxs-lookup"><span data-stu-id="2dfdb-350">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="2dfdb-351">Checksum</span><span class="sxs-lookup"><span data-stu-id="2dfdb-351">Checksum</span></span>

<span data-ttu-id="2dfdb-352">Sì</span><span class="sxs-lookup"><span data-stu-id="2dfdb-352">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="2dfdb-353">Definizione</span><span class="sxs-lookup"><span data-stu-id="2dfdb-353">Definition</span></span>

<span data-ttu-id="2dfdb-354">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="2dfdb-354">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="2dfdb-355">La funzione `Func_lithuania_eu_national_id_card` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="2dfdb-355">The function  `Func_lithuania_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="2dfdb-356">Viene trovata una `Keywords_lithuania_eu_national_id_card` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="2dfdb-356">A keyword from  `Keywords_lithuania_eu_national_id_card` is found.</span></span> 
    
<span data-ttu-id="2dfdb-357">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="2dfdb-357">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="2dfdb-358">La funzione `Func_lithuania_eu_national_id_card` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="2dfdb-358">The function  `Func_lithuania_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="2dfdb-359">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="2dfdb-359">Keywords</span></span>

#### <a name="keywordslithuaniaeunationalidcard"></a><span data-ttu-id="2dfdb-360">Keywords_lithuania_eu_national_id_card</span><span class="sxs-lookup"><span data-stu-id="2dfdb-360">Keywords_lithuania_eu_national_id_card</span></span>

<span data-ttu-id="2dfdb-361">codice numerico personale</span><span class="sxs-lookup"><span data-stu-id="2dfdb-361">personal numeric code</span></span>
  
<span data-ttu-id="2dfdb-362">numero di identificazione univoco</span><span class="sxs-lookup"><span data-stu-id="2dfdb-362">unique identification number</span></span>
  
<span data-ttu-id="2dfdb-363">numero di servizio Citizen</span><span class="sxs-lookup"><span data-stu-id="2dfdb-363">citizen service number</span></span>
  
<span data-ttu-id="2dfdb-364">numero di identità univoco</span><span class="sxs-lookup"><span data-stu-id="2dfdb-364">unique identity number</span></span>
  
<span data-ttu-id="2dfdb-365">uniqueidentityno #</span><span class="sxs-lookup"><span data-stu-id="2dfdb-365">uniqueidentityno#</span></span>
  
<span data-ttu-id="2dfdb-366">codice personale.</span><span class="sxs-lookup"><span data-stu-id="2dfdb-366">personal code.</span></span>
  
<span data-ttu-id="2dfdb-367">Asmeninis skaitmeninis kodas</span><span class="sxs-lookup"><span data-stu-id="2dfdb-367">asmeninis skaitmeninis kodas</span></span>
  
<span data-ttu-id="2dfdb-368">unikalus identifikavimo numeris</span><span class="sxs-lookup"><span data-stu-id="2dfdb-368">unikalus identifikavimo numeris</span></span>
  
<span data-ttu-id="2dfdb-369">piliečio paslaugos numeris</span><span class="sxs-lookup"><span data-stu-id="2dfdb-369">piliečio paslaugos numeris</span></span>
  
<span data-ttu-id="2dfdb-370">unikalus identifikavimo kodas</span><span class="sxs-lookup"><span data-stu-id="2dfdb-370">unikalus identifikavimo kodas</span></span>
  
<span data-ttu-id="2dfdb-371">Asmens kodas.</span><span class="sxs-lookup"><span data-stu-id="2dfdb-371">asmens kodas.</span></span>
  
## <a name="luxemburg"></a><span data-ttu-id="2dfdb-372">Lussemburgo</span><span class="sxs-lookup"><span data-stu-id="2dfdb-372">Luxemburg</span></span>

### <a name="format"></a><span data-ttu-id="2dfdb-373">Formato</span><span class="sxs-lookup"><span data-stu-id="2dfdb-373">Format</span></span>

<span data-ttu-id="2dfdb-374">11 cifre senza spazi e delimitatori</span><span class="sxs-lookup"><span data-stu-id="2dfdb-374">11 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="2dfdb-375">Modello</span><span class="sxs-lookup"><span data-stu-id="2dfdb-375">Pattern</span></span>

<span data-ttu-id="2dfdb-376">11 cifre</span><span class="sxs-lookup"><span data-stu-id="2dfdb-376">11 digits</span></span>
  
- <span data-ttu-id="2dfdb-377">Una cifra corrispondente al sesso e al secolo della nascita della persona</span><span class="sxs-lookup"><span data-stu-id="2dfdb-377">One digit that corresponds to the person's gender and century of birth</span></span>
    
-  <span data-ttu-id="2dfdb-378">Sei cifre che corrispondono alla data di nascita (AAMMGG)</span><span class="sxs-lookup"><span data-stu-id="2dfdb-378">Six digits that correspond to birth date (YYMMDD)</span></span> 
    
- <span data-ttu-id="2dfdb-379">Tre cifre che corrispondono al numero di serie della data di nascita</span><span class="sxs-lookup"><span data-stu-id="2dfdb-379">Three digits that correspond to the serial number of the date of birth</span></span>
    
- <span data-ttu-id="2dfdb-380">Una cifra di controllo</span><span class="sxs-lookup"><span data-stu-id="2dfdb-380">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="2dfdb-381">Checksum</span><span class="sxs-lookup"><span data-stu-id="2dfdb-381">Checksum</span></span>

<span data-ttu-id="2dfdb-382">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="2dfdb-382">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="2dfdb-383">Definizione</span><span class="sxs-lookup"><span data-stu-id="2dfdb-383">Definition</span></span>

<span data-ttu-id="2dfdb-384">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="2dfdb-384">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="2dfdb-385">L'espressione `Regex_luxemburg_eu_national_id_card` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="2dfdb-385">The regular expression  `Regex_luxemburg_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="2dfdb-386">Viene trovata una `Keywords_luxemburg_eu_national_id_card` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="2dfdb-386">A keyword from  `Keywords_luxemburg_eu_national_id_card` is found.</span></span> 
    
```
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_luxemburg_eu_national_id_card" />
          <Match idRef="Keywords_luxemburg_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="2dfdb-387">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="2dfdb-387">Keywords</span></span>

#### <a name="keywordsluxemburgeunationalidcard"></a><span data-ttu-id="2dfdb-388">Keywords_luxemburg_eu_national_id_card</span><span class="sxs-lookup"><span data-stu-id="2dfdb-388">Keywords_luxemburg_eu_national_id_card</span></span>

<span data-ttu-id="2dfdb-389">ID personale</span><span class="sxs-lookup"><span data-stu-id="2dfdb-389">personal id</span></span>
  
<span data-ttu-id="2dfdb-390">numero ID personale</span><span class="sxs-lookup"><span data-stu-id="2dfdb-390">personal id number</span></span>
  
<span data-ttu-id="2dfdb-391">personalidno #</span><span class="sxs-lookup"><span data-stu-id="2dfdb-391">personalidno#</span></span>
  
<span data-ttu-id="2dfdb-392">numero ID univoco</span><span class="sxs-lookup"><span data-stu-id="2dfdb-392">unique id number</span></span>
  
<span data-ttu-id="2dfdb-393">personalidnumber #</span><span class="sxs-lookup"><span data-stu-id="2dfdb-393">personalidnumber#</span></span>
  
<span data-ttu-id="2dfdb-394">chiave ID univoco</span><span class="sxs-lookup"><span data-stu-id="2dfdb-394">unique id key</span></span>
  
<span data-ttu-id="2dfdb-395">codice ID personale</span><span class="sxs-lookup"><span data-stu-id="2dfdb-395">personal id code</span></span>
  
<span data-ttu-id="2dfdb-396">uniqueidkey #</span><span class="sxs-lookup"><span data-stu-id="2dfdb-396">uniqueidkey#</span></span>
  
<span data-ttu-id="2dfdb-397">codice singolo</span><span class="sxs-lookup"><span data-stu-id="2dfdb-397">individual code</span></span>
  
<span data-ttu-id="2dfdb-398">ID individuale</span><span class="sxs-lookup"><span data-stu-id="2dfdb-398">individual id</span></span>
  
<span data-ttu-id="2dfdb-399">ID eindeutige-Nummer</span><span class="sxs-lookup"><span data-stu-id="2dfdb-399">eindeutige id-nummer</span></span>
  
<span data-ttu-id="2dfdb-400">ID eindeutige</span><span class="sxs-lookup"><span data-stu-id="2dfdb-400">eindeutige id</span></span>
  
<span data-ttu-id="2dfdb-401">ID personnelle</span><span class="sxs-lookup"><span data-stu-id="2dfdb-401">id personnelle</span></span>
  
<span data-ttu-id="2dfdb-402">personale di Numéro d'identification</span><span class="sxs-lookup"><span data-stu-id="2dfdb-402">numéro d'identification personnel</span></span>
  
<span data-ttu-id="2dfdb-403">idpersonnelle #</span><span class="sxs-lookup"><span data-stu-id="2dfdb-403">idpersonnelle#</span></span>
  
<span data-ttu-id="2dfdb-404">persönliche Identifikationsnummer</span><span class="sxs-lookup"><span data-stu-id="2dfdb-404">persönliche identifikationsnummer</span></span>
  
<span data-ttu-id="2dfdb-405">eindeutigeid #</span><span class="sxs-lookup"><span data-stu-id="2dfdb-405">eindeutigeid#</span></span>
  
## <a name="malta"></a><span data-ttu-id="2dfdb-406">Malta</span><span class="sxs-lookup"><span data-stu-id="2dfdb-406">Malta</span></span>

### <a name="format"></a><span data-ttu-id="2dfdb-407">Formato</span><span class="sxs-lookup"><span data-stu-id="2dfdb-407">Format</span></span>

<span data-ttu-id="2dfdb-408">Sette cifre seguite da una lettera</span><span class="sxs-lookup"><span data-stu-id="2dfdb-408">Seven digits followed by one letter</span></span>
  
### <a name="pattern"></a><span data-ttu-id="2dfdb-409">Modello</span><span class="sxs-lookup"><span data-stu-id="2dfdb-409">Pattern</span></span>

<span data-ttu-id="2dfdb-410">Sette cifre seguite da una lettera:</span><span class="sxs-lookup"><span data-stu-id="2dfdb-410">Seven digits followed by one letter:</span></span>
  
-  <span data-ttu-id="2dfdb-411">Sette cifre</span><span class="sxs-lookup"><span data-stu-id="2dfdb-411">Seven digits</span></span> 
    
- <span data-ttu-id="2dfdb-412">Una lettera maiuscola (distinzione tra maiuscole e minuscole)</span><span class="sxs-lookup"><span data-stu-id="2dfdb-412">One uppercase letter (case sensitive)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="2dfdb-413">Checksum</span><span class="sxs-lookup"><span data-stu-id="2dfdb-413">Checksum</span></span>

<span data-ttu-id="2dfdb-414">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="2dfdb-414">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="2dfdb-415">Definizione</span><span class="sxs-lookup"><span data-stu-id="2dfdb-415">Definition</span></span>

<span data-ttu-id="2dfdb-416">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="2dfdb-416">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="2dfdb-417">L'espressione `Regex_malta_eu_national_id_card` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="2dfdb-417">The regular expression  `Regex_malta_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="2dfdb-418">Viene trovata una `Keywords_malta_eu_national_id_card` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="2dfdb-418">A keyword from  `Keywords_malta_eu_national_id_card` is found.</span></span> 
    
<span data-ttu-id="2dfdb-419">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 65%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="2dfdb-419">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="2dfdb-420">L'espressione `Regex_malta_eu_national_id_card` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="2dfdb-420">The regular expression  `Regex_malta_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="2dfdb-421">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="2dfdb-421">Keywords</span></span>

#### <a name="keywordsmaltaeunationalidcard"></a><span data-ttu-id="2dfdb-422">Keywords_malta_eu_national_id_card</span><span class="sxs-lookup"><span data-stu-id="2dfdb-422">Keywords_malta_eu_national_id_card</span></span>

<span data-ttu-id="2dfdb-423">codice numerico personale</span><span class="sxs-lookup"><span data-stu-id="2dfdb-423">personal numeric code</span></span>
  
<span data-ttu-id="2dfdb-424">numero di identificazione univoco</span><span class="sxs-lookup"><span data-stu-id="2dfdb-424">unique identification number</span></span>
  
<span data-ttu-id="2dfdb-425">numero di servizio Citizen</span><span class="sxs-lookup"><span data-stu-id="2dfdb-425">citizen service number</span></span>
  
<span data-ttu-id="2dfdb-426">numero di identità univoco</span><span class="sxs-lookup"><span data-stu-id="2dfdb-426">unique identity number</span></span>
  
<span data-ttu-id="2dfdb-427">uniqueidentityno #</span><span class="sxs-lookup"><span data-stu-id="2dfdb-427">uniqueidentityno#</span></span>
  
<span data-ttu-id="2dfdb-428">Kodiċi numerai personali</span><span class="sxs-lookup"><span data-stu-id="2dfdb-428">kodiċi numerali personali</span></span>
  
<span data-ttu-id="2dfdb-429">numru ta ' identifikazzjoni uniku</span><span class="sxs-lookup"><span data-stu-id="2dfdb-429">numru ta 'identifikazzjoni uniku</span></span>
  
<span data-ttu-id="2dfdb-430">numru TAS-Servizz taċ-ċittadin</span><span class="sxs-lookup"><span data-stu-id="2dfdb-430">numru tas-servizz taċ-ċittadin</span></span>
  
<span data-ttu-id="2dfdb-431">numru ta ' identità uniku</span><span class="sxs-lookup"><span data-stu-id="2dfdb-431">numru ta' identità uniku</span></span>
  
## <a name="netherlands"></a><span data-ttu-id="2dfdb-432">Paesi Bassi</span><span class="sxs-lookup"><span data-stu-id="2dfdb-432">Netherlands</span></span>

### <a name="format"></a><span data-ttu-id="2dfdb-433">Formato</span><span class="sxs-lookup"><span data-stu-id="2dfdb-433">Format</span></span>

<span data-ttu-id="2dfdb-434">Nove cifre senza spazi o delimitatori</span><span class="sxs-lookup"><span data-stu-id="2dfdb-434">Nine digits without spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="2dfdb-435">Modello</span><span class="sxs-lookup"><span data-stu-id="2dfdb-435">Pattern</span></span>

<span data-ttu-id="2dfdb-436">9 cifre</span><span class="sxs-lookup"><span data-stu-id="2dfdb-436">Nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="2dfdb-437">Checksum</span><span class="sxs-lookup"><span data-stu-id="2dfdb-437">Checksum</span></span>

<span data-ttu-id="2dfdb-438">Sì</span><span class="sxs-lookup"><span data-stu-id="2dfdb-438">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="2dfdb-439">Definizione</span><span class="sxs-lookup"><span data-stu-id="2dfdb-439">Definition</span></span>

<span data-ttu-id="2dfdb-440">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="2dfdb-440">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="2dfdb-441">La funzione `Func_netherlands_eu_national_id_card` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="2dfdb-441">The function  `Func_netherlands_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="2dfdb-442">Viene trovata una parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="2dfdb-442">A keyword from is found.</span></span>
    
<span data-ttu-id="2dfdb-443">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="2dfdb-443">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="2dfdb-444">La funzione `Func_netherlands_eu_national_id_card` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="2dfdb-444">The function  `Func_netherlands_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="2dfdb-445">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="2dfdb-445">Keywords</span></span>

#### <a name="keywordsnetherlandseunationalidcard"></a><span data-ttu-id="2dfdb-446">Keywords_netherlands_eu_national_id_card</span><span class="sxs-lookup"><span data-stu-id="2dfdb-446">Keywords_netherlands_eu_national_id_card</span></span>

<span data-ttu-id="2dfdb-447">codice numerico personale</span><span class="sxs-lookup"><span data-stu-id="2dfdb-447">personal numeric code</span></span>
  
<span data-ttu-id="2dfdb-448">numero di identificazione univoco</span><span class="sxs-lookup"><span data-stu-id="2dfdb-448">unique identification number</span></span>
  
<span data-ttu-id="2dfdb-449">numero di servizio Citizen</span><span class="sxs-lookup"><span data-stu-id="2dfdb-449">citizen service number</span></span>
  
<span data-ttu-id="2dfdb-450">numero di identità univoco</span><span class="sxs-lookup"><span data-stu-id="2dfdb-450">unique identity number</span></span>
  
<span data-ttu-id="2dfdb-451">uniqueidentityno #</span><span class="sxs-lookup"><span data-stu-id="2dfdb-451">uniqueidentityno#</span></span>
  
<span data-ttu-id="2dfdb-452">BSN</span><span class="sxs-lookup"><span data-stu-id="2dfdb-452">bsn</span></span>
  
<span data-ttu-id="2dfdb-453">BSN</span><span class="sxs-lookup"><span data-stu-id="2dfdb-453">bsn#</span></span>
  
<span data-ttu-id="2dfdb-454">codice Numerieke di persoonlijke</span><span class="sxs-lookup"><span data-stu-id="2dfdb-454">persoonlijke numerieke code</span></span>
  
<span data-ttu-id="2dfdb-455">uniek identificatienummer</span><span class="sxs-lookup"><span data-stu-id="2dfdb-455">uniek identificatienummer</span></span>
  
<span data-ttu-id="2dfdb-456">burgerservicenummer</span><span class="sxs-lookup"><span data-stu-id="2dfdb-456">burgerservicenummer</span></span>
  
<span data-ttu-id="2dfdb-457">uniek identiteitsnummer</span><span class="sxs-lookup"><span data-stu-id="2dfdb-457">uniek identiteitsnummer</span></span>
  
## <a name="poland"></a><span data-ttu-id="2dfdb-458">Polonia</span><span class="sxs-lookup"><span data-stu-id="2dfdb-458">Poland</span></span>

<span data-ttu-id="2dfdb-459">Per informazioni dettagliate, vedere la sezione "Poland National ID (PESEL)" in [che cosa cercano i tipi di informazioni riservate](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="2dfdb-459">For details, see the section "Poland National ID (PESEL)" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="portugal"></a><span data-ttu-id="2dfdb-460">Portogallo</span><span class="sxs-lookup"><span data-stu-id="2dfdb-460">Portugal</span></span>

<span data-ttu-id="2dfdb-461">Per informazioni dettagliate, vedere la sezione "Portugal Citizen Card Number" in [quello che i tipi di informazioni riservate cercano](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="2dfdb-461">For details, see the section "Portugal Citizen Card Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="romania"></a><span data-ttu-id="2dfdb-462">Romania</span><span class="sxs-lookup"><span data-stu-id="2dfdb-462">Romania</span></span>

### <a name="format"></a><span data-ttu-id="2dfdb-463">Formato</span><span class="sxs-lookup"><span data-stu-id="2dfdb-463">Format</span></span>

<span data-ttu-id="2dfdb-464">13 cifre senza spazi e delimitatori</span><span class="sxs-lookup"><span data-stu-id="2dfdb-464">13 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="2dfdb-465">Modello</span><span class="sxs-lookup"><span data-stu-id="2dfdb-465">Pattern</span></span>

<span data-ttu-id="2dfdb-466">13 cifre</span><span class="sxs-lookup"><span data-stu-id="2dfdb-466">13 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="2dfdb-467">Checksum</span><span class="sxs-lookup"><span data-stu-id="2dfdb-467">Checksum</span></span>

<span data-ttu-id="2dfdb-468">Sì</span><span class="sxs-lookup"><span data-stu-id="2dfdb-468">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="2dfdb-469">Definizione</span><span class="sxs-lookup"><span data-stu-id="2dfdb-469">Definition</span></span>

<span data-ttu-id="2dfdb-470">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="2dfdb-470">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="2dfdb-471">La funzione `Func_romania_eu_national_id_card` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="2dfdb-471">The function  `Func_romania_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="2dfdb-472">Viene trovata una `Keywords_romania_eu_national_id_card` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="2dfdb-472">A keyword from  `Keywords_romania_eu_national_id_card` is found.</span></span> 
    
<span data-ttu-id="2dfdb-473">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="2dfdb-473">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="2dfdb-474">La funzione `Func_romania_eu_national_id_card` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="2dfdb-474">The function  `Func_romania_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="2dfdb-475">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="2dfdb-475">Keywords</span></span>

#### <a name="keywordsromaniaeunationalidcard"></a><span data-ttu-id="2dfdb-476">Keywords_romania_eu_national_id_card</span><span class="sxs-lookup"><span data-stu-id="2dfdb-476">Keywords_romania_eu_national_id_card</span></span>

<span data-ttu-id="2dfdb-477">codice numerico personale</span><span class="sxs-lookup"><span data-stu-id="2dfdb-477">personal numeric code</span></span>
  
<span data-ttu-id="2dfdb-478">numero di identificazione univoco</span><span class="sxs-lookup"><span data-stu-id="2dfdb-478">unique identification number</span></span>
  
<span data-ttu-id="2dfdb-479">CNP</span><span class="sxs-lookup"><span data-stu-id="2dfdb-479">cnp</span></span>
  
<span data-ttu-id="2dfdb-480">CNP</span><span class="sxs-lookup"><span data-stu-id="2dfdb-480">cnp#</span></span>
  
<span data-ttu-id="2dfdb-481">pin</span><span class="sxs-lookup"><span data-stu-id="2dfdb-481">pin</span></span>
  
<span data-ttu-id="2dfdb-482">pin</span><span class="sxs-lookup"><span data-stu-id="2dfdb-482">pin#</span></span>
  
<span data-ttu-id="2dfdb-483">numero assicurativo</span><span class="sxs-lookup"><span data-stu-id="2dfdb-483">insurance number</span></span>
  
<span data-ttu-id="2dfdb-484">insurancenumber #</span><span class="sxs-lookup"><span data-stu-id="2dfdb-484">insurancenumber#</span></span>
  
<span data-ttu-id="2dfdb-485">numero di identità univoco</span><span class="sxs-lookup"><span data-stu-id="2dfdb-485">unique identity number</span></span>
  
<span data-ttu-id="2dfdb-486">uniqueidentityno #</span><span class="sxs-lookup"><span data-stu-id="2dfdb-486">uniqueidentityno#</span></span>
  
<span data-ttu-id="2dfdb-487">Cod numerico personale</span><span class="sxs-lookup"><span data-stu-id="2dfdb-487">cod numeric personal</span></span>
  
<span data-ttu-id="2dfdb-488">Cod identificare Personal</span><span class="sxs-lookup"><span data-stu-id="2dfdb-488">cod identificare personal</span></span>
  
<span data-ttu-id="2dfdb-489">Cod Unic identificare</span><span class="sxs-lookup"><span data-stu-id="2dfdb-489">cod unic identificare</span></span>
  
<span data-ttu-id="2dfdb-490">Număr personale Unic</span><span class="sxs-lookup"><span data-stu-id="2dfdb-490">număr personal unic</span></span>
  
<span data-ttu-id="2dfdb-491">Număr identitate</span><span class="sxs-lookup"><span data-stu-id="2dfdb-491">număr identitate</span></span>
  
<span data-ttu-id="2dfdb-492">Număr identificare Personal</span><span class="sxs-lookup"><span data-stu-id="2dfdb-492">număr identificare personal</span></span>
  
<span data-ttu-id="2dfdb-493">număridentitate #</span><span class="sxs-lookup"><span data-stu-id="2dfdb-493">număridentitate#</span></span>
  
<span data-ttu-id="2dfdb-494">codnumericpersonal #</span><span class="sxs-lookup"><span data-stu-id="2dfdb-494">codnumericpersonal#</span></span>
  
<span data-ttu-id="2dfdb-495">numărpersonalunic #</span><span class="sxs-lookup"><span data-stu-id="2dfdb-495">numărpersonalunic#</span></span>
  
## <a name="slovakia"></a><span data-ttu-id="2dfdb-496">Slovacchia</span><span class="sxs-lookup"><span data-stu-id="2dfdb-496">Slovakia</span></span>

### <a name="format"></a><span data-ttu-id="2dfdb-497">Formato</span><span class="sxs-lookup"><span data-stu-id="2dfdb-497">Format</span></span>

<span data-ttu-id="2dfdb-498">Dieci cifre contenenti una barra rovesciata</span><span class="sxs-lookup"><span data-stu-id="2dfdb-498">Ten digits containing one backslash</span></span>
  
### <a name="pattern"></a><span data-ttu-id="2dfdb-499">Modello</span><span class="sxs-lookup"><span data-stu-id="2dfdb-499">Pattern</span></span>

<span data-ttu-id="2dfdb-500">Dieci cifre che contengono una barra rovesciata:</span><span class="sxs-lookup"><span data-stu-id="2dfdb-500">Ten digits containing one backslash:</span></span>
  
### <a name="checksum"></a><span data-ttu-id="2dfdb-501">Checksum</span><span class="sxs-lookup"><span data-stu-id="2dfdb-501">Checksum</span></span>

<span data-ttu-id="2dfdb-502">Sì</span><span class="sxs-lookup"><span data-stu-id="2dfdb-502">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="2dfdb-503">Definizione</span><span class="sxs-lookup"><span data-stu-id="2dfdb-503">Definition</span></span>

<span data-ttu-id="2dfdb-504">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="2dfdb-504">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="2dfdb-505">La funzione `Func_slovakia_eu_national_id_card` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="2dfdb-505">The function  `Func_slovakia_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="2dfdb-506">Viene trovata una `Keywords_slovakia_eu_national_id_card` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="2dfdb-506">A keyword from  `Keywords_slovakia_eu_national_id_card` is found.</span></span> 
    
<span data-ttu-id="2dfdb-507">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="2dfdb-507">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="2dfdb-508">La funzione `Func_slovakia_eu_national_id_card` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="2dfdb-508">The function  `Func_slovakia_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="2dfdb-509">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="2dfdb-509">Keywords</span></span>

#### <a name="keywordsslovakiaeunationalidcard"></a><span data-ttu-id="2dfdb-510">Keywords_slovakia_eu_national_id_card</span><span class="sxs-lookup"><span data-stu-id="2dfdb-510">Keywords_slovakia_eu_national_id_card</span></span>

<span data-ttu-id="2dfdb-511">numero di nascita</span><span class="sxs-lookup"><span data-stu-id="2dfdb-511">birth number</span></span>
  
<span data-ttu-id="2dfdb-512">national identification number</span><span class="sxs-lookup"><span data-stu-id="2dfdb-512">national identification number</span></span>
  
<span data-ttu-id="2dfdb-513">numero di identificazione personale</span><span class="sxs-lookup"><span data-stu-id="2dfdb-513">personal identification number</span></span>
  
<span data-ttu-id="2dfdb-514">social security number</span><span class="sxs-lookup"><span data-stu-id="2dfdb-514">social security number</span></span>
  
<span data-ttu-id="2dfdb-515">nationalnumber #</span><span class="sxs-lookup"><span data-stu-id="2dfdb-515">nationalnumber#</span></span>
  
<span data-ttu-id="2dfdb-516">SSN</span><span class="sxs-lookup"><span data-stu-id="2dfdb-516">ssn#</span></span>
  
<span data-ttu-id="2dfdb-517">SSN</span><span class="sxs-lookup"><span data-stu-id="2dfdb-517">ssn</span></span>
  
<span data-ttu-id="2dfdb-518">numero nazionale</span><span class="sxs-lookup"><span data-stu-id="2dfdb-518">national number</span></span>
  
<span data-ttu-id="2dfdb-519">numero ID personale</span><span class="sxs-lookup"><span data-stu-id="2dfdb-519">personal id number</span></span>
  
<span data-ttu-id="2dfdb-520">personalidnumber #</span><span class="sxs-lookup"><span data-stu-id="2dfdb-520">personalidnumber#</span></span>
  
<span data-ttu-id="2dfdb-521">rč</span><span class="sxs-lookup"><span data-stu-id="2dfdb-521">rč</span></span>
  
<span data-ttu-id="2dfdb-522">rodné číslo</span><span class="sxs-lookup"><span data-stu-id="2dfdb-522">rodné číslo</span></span>
  
<span data-ttu-id="2dfdb-523">rodne cislo</span><span class="sxs-lookup"><span data-stu-id="2dfdb-523">rodne cislo</span></span>
  
## <a name="slovenia"></a><span data-ttu-id="2dfdb-524">Slovenia</span><span class="sxs-lookup"><span data-stu-id="2dfdb-524">Slovenia</span></span>

### <a name="format"></a><span data-ttu-id="2dfdb-525">Formato</span><span class="sxs-lookup"><span data-stu-id="2dfdb-525">Format</span></span>

<span data-ttu-id="2dfdb-526">13 cifre senza spazi o delimitatori</span><span class="sxs-lookup"><span data-stu-id="2dfdb-526">13 digits without spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="2dfdb-527">Modello</span><span class="sxs-lookup"><span data-stu-id="2dfdb-527">Pattern</span></span>

<span data-ttu-id="2dfdb-528">13 cifre nel modello specificato:</span><span class="sxs-lookup"><span data-stu-id="2dfdb-528">13 digits in the specified pattern:</span></span>
  
-  <span data-ttu-id="2dfdb-529">Sette cifre che corrispondono alla data di nascita (DDMMLLL), dove "LLL" corrisponde alle ultime tre cifre dell'anno di nascita</span><span class="sxs-lookup"><span data-stu-id="2dfdb-529">Seven digits that correspond to the birth date (DDMMLLL) where "LLL" corresponds to the last three digits of the birth year</span></span> 
    
- <span data-ttu-id="2dfdb-530">Due cifre che corrispondono all'area di nascita</span><span class="sxs-lookup"><span data-stu-id="2dfdb-530">Two digits that correspond to the area of birth</span></span>
    
- <span data-ttu-id="2dfdb-531">Tre cifre che corrispondono a una combinazione di genere e numero di serie per le persone nate nello stesso giorno (000-499 per il maschio e 500-999 per le femmine)</span><span class="sxs-lookup"><span data-stu-id="2dfdb-531">Three digits that correspond to a combination of gender and serial number for persons born on the same day (000-499 for male and 500-999 for female)</span></span>
    
- <span data-ttu-id="2dfdb-532">Una cifra di controllo</span><span class="sxs-lookup"><span data-stu-id="2dfdb-532">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="2dfdb-533">Checksum</span><span class="sxs-lookup"><span data-stu-id="2dfdb-533">Checksum</span></span>

<span data-ttu-id="2dfdb-534">Sì</span><span class="sxs-lookup"><span data-stu-id="2dfdb-534">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="2dfdb-535">Definizione</span><span class="sxs-lookup"><span data-stu-id="2dfdb-535">Definition</span></span>

<span data-ttu-id="2dfdb-536">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 85%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="2dfdb-536">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="2dfdb-537">La funzione `Func_slovenia_eu_national_id_card` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="2dfdb-537">The function  `Func_slovenia_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="2dfdb-538">Viene trovata una `Keywords_slovenia_eu_national_id_card` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="2dfdb-538">A keyword from  `Keywords_slovenia_eu_national_id_card` is found.</span></span> 
    
<span data-ttu-id="2dfdb-539">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="2dfdb-539">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="2dfdb-540">La funzione `Func_slovenia_eu_national_id_card` trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="2dfdb-540">The function  `Func_slovenia_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="2dfdb-541">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="2dfdb-541">Keywords</span></span>

#### <a name="keywordssloveniaeunationalidcard"></a><span data-ttu-id="2dfdb-542">Keywords_slovenia_eu_national_id_card</span><span class="sxs-lookup"><span data-stu-id="2dfdb-542">Keywords_slovenia_eu_national_id_card</span></span>

<span data-ttu-id="2dfdb-543">codice numerico personale</span><span class="sxs-lookup"><span data-stu-id="2dfdb-543">personal numeric code</span></span>
  
<span data-ttu-id="2dfdb-544">numero di identificazione univoco</span><span class="sxs-lookup"><span data-stu-id="2dfdb-544">unique identification number</span></span>
  
<span data-ttu-id="2dfdb-545">numero di registrazione univoco</span><span class="sxs-lookup"><span data-stu-id="2dfdb-545">unique registration number</span></span>
  
<span data-ttu-id="2dfdb-546">numero di identità univoco</span><span class="sxs-lookup"><span data-stu-id="2dfdb-546">unique identity number</span></span>
  
<span data-ttu-id="2dfdb-547">uniqueidentityno #</span><span class="sxs-lookup"><span data-stu-id="2dfdb-547">uniqueidentityno#</span></span>
  
<span data-ttu-id="2dfdb-548">numero di cittadino Master univoco</span><span class="sxs-lookup"><span data-stu-id="2dfdb-548">unique master citizen number</span></span>
  
<span data-ttu-id="2dfdb-549">edinstvena identifikacijska številka</span><span class="sxs-lookup"><span data-stu-id="2dfdb-549">edinstvena identifikacijska številka</span></span>
  
<span data-ttu-id="2dfdb-550">uniqueidentityno #</span><span class="sxs-lookup"><span data-stu-id="2dfdb-550">uniqueidentityno #</span></span>
  
<span data-ttu-id="2dfdb-551">edinstvena številka glavnega državljana</span><span class="sxs-lookup"><span data-stu-id="2dfdb-551">edinstvena številka glavnega državljana</span></span>
  
<span data-ttu-id="2dfdb-552">emšo</span><span class="sxs-lookup"><span data-stu-id="2dfdb-552">emšo</span></span>
  
## <a name="spain"></a><span data-ttu-id="2dfdb-553">Spagna</span><span class="sxs-lookup"><span data-stu-id="2dfdb-553">Spain</span></span>

### <a name="format"></a><span data-ttu-id="2dfdb-554">Formato</span><span class="sxs-lookup"><span data-stu-id="2dfdb-554">Format</span></span>

<span data-ttu-id="2dfdb-555">Sette cifre seguite da un carattere</span><span class="sxs-lookup"><span data-stu-id="2dfdb-555">Seven digits followed by one character</span></span>
  
### <a name="pattern"></a><span data-ttu-id="2dfdb-556">Modello</span><span class="sxs-lookup"><span data-stu-id="2dfdb-556">Pattern</span></span>

<span data-ttu-id="2dfdb-557">Sette cifre seguite da un carattere</span><span class="sxs-lookup"><span data-stu-id="2dfdb-557">Seven digits followed by one character</span></span>
  
- <span data-ttu-id="2dfdb-558">Sette cifre</span><span class="sxs-lookup"><span data-stu-id="2dfdb-558">Seven digits</span></span>
    
- <span data-ttu-id="2dfdb-559">Una cifra o una lettera (senza distinzione tra maiuscole e minuscole)</span><span class="sxs-lookup"><span data-stu-id="2dfdb-559">One digit or letter (not case-sensitive)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="2dfdb-560">Checksum</span><span class="sxs-lookup"><span data-stu-id="2dfdb-560">Checksum</span></span>

<span data-ttu-id="2dfdb-561">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="2dfdb-561">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="2dfdb-562">Definizione</span><span class="sxs-lookup"><span data-stu-id="2dfdb-562">Definition</span></span>

<span data-ttu-id="2dfdb-563">Un criterio DLP rileva questo tipo di informazioni con una probabilità del 75%, entro 300 caratteri, se:</span><span class="sxs-lookup"><span data-stu-id="2dfdb-563">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="2dfdb-564">L'espressione `Regex_spain_eu_national_id_card` regolare trova contenuto che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="2dfdb-564">The regular expression  `Regex_spain_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="2dfdb-565">Viene trovata una `Keywords_spain_eu_national_id_card"` parola chiave from.</span><span class="sxs-lookup"><span data-stu-id="2dfdb-565">A keyword from  `Keywords_spain_eu_national_id_card"` is found.</span></span> 
    
```
 
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_spain_eu_national_id_card" />
          <Match idRef="Keywords_spain_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="2dfdb-566">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="2dfdb-566">Keywords</span></span>

#### <a name="keywordsspaineunationalidcard"></a><span data-ttu-id="2dfdb-567">Keywords_spain_eu_national_id_card</span><span class="sxs-lookup"><span data-stu-id="2dfdb-567">Keywords_spain_eu_national_id_card</span></span>

<span data-ttu-id="2dfdb-568">DNI</span><span class="sxs-lookup"><span data-stu-id="2dfdb-568">dni</span></span>
  
<span data-ttu-id="2dfdb-569">national identification number</span><span class="sxs-lookup"><span data-stu-id="2dfdb-569">national identification number</span></span>
  
<span data-ttu-id="2dfdb-570">numero di identità nazionale</span><span class="sxs-lookup"><span data-stu-id="2dfdb-570">national identity number</span></span>
  
<span data-ttu-id="2dfdb-571">numero assicurativo</span><span class="sxs-lookup"><span data-stu-id="2dfdb-571">insurance number</span></span>
  
<span data-ttu-id="2dfdb-572">numero di identificazione personale</span><span class="sxs-lookup"><span data-stu-id="2dfdb-572">personal identification number</span></span>
  
<span data-ttu-id="2dfdb-573">identità nazionale</span><span class="sxs-lookup"><span data-stu-id="2dfdb-573">national identity</span></span>
  
<span data-ttu-id="2dfdb-574">identità personale No</span><span class="sxs-lookup"><span data-stu-id="2dfdb-574">personal identity no</span></span>
  
<span data-ttu-id="2dfdb-575">numero di identità univoco</span><span class="sxs-lookup"><span data-stu-id="2dfdb-575">unique identity number</span></span>
  
<span data-ttu-id="2dfdb-576">nationalidno #</span><span class="sxs-lookup"><span data-stu-id="2dfdb-576">nationalidno#</span></span>
  
<span data-ttu-id="2dfdb-577">UniqueId</span><span class="sxs-lookup"><span data-stu-id="2dfdb-577">uniqueid#</span></span>
  
<span data-ttu-id="2dfdb-578">DNI</span><span class="sxs-lookup"><span data-stu-id="2dfdb-578">dni#</span></span>
  
<span data-ttu-id="2dfdb-579">nationalid #</span><span class="sxs-lookup"><span data-stu-id="2dfdb-579">nationalid#</span></span>
  
<span data-ttu-id="2dfdb-580">nie</span><span class="sxs-lookup"><span data-stu-id="2dfdb-580">nie#</span></span>
  
<span data-ttu-id="2dfdb-581">nie</span><span class="sxs-lookup"><span data-stu-id="2dfdb-581">nie</span></span>
  
<span data-ttu-id="2dfdb-582">nienúmero #</span><span class="sxs-lookup"><span data-stu-id="2dfdb-582">nienúmero#</span></span>
  
<span data-ttu-id="2dfdb-583">nie número</span><span class="sxs-lookup"><span data-stu-id="2dfdb-583">nie número</span></span>
  
<span data-ttu-id="2dfdb-584">documento Nacional de Identidad</span><span class="sxs-lookup"><span data-stu-id="2dfdb-584">documento nacional de identidad</span></span>
  
<span data-ttu-id="2dfdb-585">Identidad único</span><span class="sxs-lookup"><span data-stu-id="2dfdb-585">identidad único</span></span>
  
<span data-ttu-id="2dfdb-586">número Nacional Identidad</span><span class="sxs-lookup"><span data-stu-id="2dfdb-586">número nacional identidad</span></span>
  
<span data-ttu-id="2dfdb-587">DNI número</span><span class="sxs-lookup"><span data-stu-id="2dfdb-587">dni número</span></span>
  
<span data-ttu-id="2dfdb-588">dninúmero #</span><span class="sxs-lookup"><span data-stu-id="2dfdb-588">dninúmero#</span></span>
  
<span data-ttu-id="2dfdb-589">identidadúnico #</span><span class="sxs-lookup"><span data-stu-id="2dfdb-589">identidadúnico#</span></span>
  
## <a name="sweden"></a><span data-ttu-id="2dfdb-590">Svezia</span><span class="sxs-lookup"><span data-stu-id="2dfdb-590">Sweden</span></span>

<span data-ttu-id="2dfdb-591">Per informazioni dettagliate, vedere la sezione "Sweden National ID" per [individuare i tipi di informazioni riservate](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="2dfdb-591">For details, see the section "Sweden National ID" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="2dfdb-592">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2dfdb-592">See also</span></span>

[<span data-ttu-id="2dfdb-593">Cosa individuano le tipologie di informazioni sensibili</span><span class="sxs-lookup"><span data-stu-id="2dfdb-593">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)

