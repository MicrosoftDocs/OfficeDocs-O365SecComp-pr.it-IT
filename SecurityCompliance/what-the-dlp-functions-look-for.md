---
title: Cosa individuano le funzioni DLP
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 6/18/2016
ms.audience: Admin
ms.topic: reference
ms.service: o365-administration
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MET150
ms.assetid: 94349ed4-5351-4ee2-bbda-70813c9ed693
description: I tipi di informazioni riservate cercare un modello specifico e il grado di confermare accertandosi corretto formattazione applicate checksum e cercando pertinenti parole chiave o altre informazioni. Alcune di queste funzionalità viene eseguita da funzioni interne. In questo argomento viene illustrato che queste funzioni aspetto, che consentono di comprendere il funzionano i tipi di informazioni riservate predefiniti.
ms.openlocfilehash: 510f98e2b4e1d2480550f11026cf445be6ffc931
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/27/2018
ms.locfileid: "23013760"
---
# <a name="what-the-dlp-functions-look-for"></a><span data-ttu-id="19bb3-105">Cosa individuano le funzioni DLP</span><span class="sxs-lookup"><span data-stu-id="19bb3-105">What the DLP functions look for</span></span>

<span data-ttu-id="19bb3-p102">Prevenzione della perdita di dati (DLP) include tipi di informazioni riservate, come il numero di carta di credito e il numero di carta di debito EU, pronti per essere utilizzati nei criteri DLP. Questi tipi di informazioni riservate cercano uno schema specifico e lo confermano assicurando la corretta formattazione, applicando checksum e individuando parole chiave specifiche o altre informazioni. Alcune di queste funzionalità vengono eseguite da funzioni interne. Ad esempio, il tipo di informazioni riservate relative al numero di carta di credito utilizza una funzione per cercare le date formattate come una data di scadenza, in modo da confermare che si tratta di un numero di carta di credito.</span><span class="sxs-lookup"><span data-stu-id="19bb3-p102">Data loss prevention (DLP) includes sensitive information types, such as Credit Card Number and EU Debit Card Number, which are ready for you to use in your DLP policies. These sensitive information types look for a specific pattern and corroborate it by ensuring proper formatting, enforcing checksums, and looking for relevant keywords or other information. Some of this functionality is performed by internal functions. For example, the Credit Card Number sensitive information type uses a function to look for dates formatted like an expiration date, to help corroborate that a number is a credit card number.</span></span>
  
<span data-ttu-id="19bb3-p103">In questo argomento viene descritto cosa viene cercato da queste funzioni per comprendere come funzionano i tipi di informazioni riservate predefiniti. Per ulteriori informazioni, vedere [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="19bb3-p103">This topic explains what these functions look for, to help you understand how the predefined sensitive information types work. For more information, see [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="funcusdate"></a><span data-ttu-id="19bb3-112">Func_us_date</span><span class="sxs-lookup"><span data-stu-id="19bb3-112">Func_us_date</span></span>

<span data-ttu-id="19bb3-p104">Questa funzione Cerca una data in formato comunemente utilizzata negli Stati Uniti Sono inclusi i formati "giorno/mese/anno", "mese-giorno-anno" e "mese il giorno anno". I nomi o abbreviazioni mesi non sono distinzione tra maiuscole e minuscole.</span><span class="sxs-lookup"><span data-stu-id="19bb3-p104">This function looks for a date in the format commonly used in the U.S. This includes the formats "month/day/year", "month-day-year", and "month day year ". The names or abbreviations of months are not case sensitive.</span></span> 
  
<span data-ttu-id="19bb3-115">Esempi:</span><span class="sxs-lookup"><span data-stu-id="19bb3-115">Examples:</span></span>
  
- <span data-ttu-id="19bb3-116">2 dicembre 2016</span><span class="sxs-lookup"><span data-stu-id="19bb3-116">December 2, 2016</span></span>
    
- <span data-ttu-id="19bb3-117">2 DEC 2016</span><span class="sxs-lookup"><span data-stu-id="19bb3-117">Dec 2, 2016</span></span>
    
- <span data-ttu-id="19bb3-118">DEC 2016 02</span><span class="sxs-lookup"><span data-stu-id="19bb3-118">dec 02 2016</span></span>
    
- <span data-ttu-id="19bb3-119">2/12/2016</span><span class="sxs-lookup"><span data-stu-id="19bb3-119">12/2/2016</span></span>
    
- <span data-ttu-id="19bb3-120">12/02/16</span><span class="sxs-lookup"><span data-stu-id="19bb3-120">12/02/16</span></span>
    
- <span data-ttu-id="19bb3-121">DEC-2-2016</span><span class="sxs-lookup"><span data-stu-id="19bb3-121">Dec-2-2016</span></span>
    
- <span data-ttu-id="19bb3-122">12-2-16</span><span class="sxs-lookup"><span data-stu-id="19bb3-122">12-2-16</span></span>
    
<span data-ttu-id="19bb3-123">Nomi dei mesi accettati:</span><span class="sxs-lookup"><span data-stu-id="19bb3-123">Accepted month names:</span></span>
  
- <span data-ttu-id="19bb3-124">Inglese</span><span class="sxs-lookup"><span data-stu-id="19bb3-124">English</span></span>
    
  - <span data-ttu-id="19bb3-125">Gennaio, febbraio, marzo, aprile, maggio, giugno, luglio, agosto, settembre, ottobre, novembre, dicembre</span><span class="sxs-lookup"><span data-stu-id="19bb3-125">January, February, march, April, may, June, July, August, September, October, November, December</span></span>
    
  - <span data-ttu-id="19bb3-126">Gennaio febbraio Mar. Apr. maggio giugno luglio agosto settembre ottobre Dec novembre.</span><span class="sxs-lookup"><span data-stu-id="19bb3-126">Jan. Feb. Mar. Apr. May June July Aug. Sept. Oct. Nov. Dec.</span></span>
    
## <a name="funceudate"></a><span data-ttu-id="19bb3-127">Func_eu_date</span><span class="sxs-lookup"><span data-stu-id="19bb3-127">Func_eu_date</span></span>

<span data-ttu-id="19bb3-p105">Questa funzione consente di cercare una data nel formato comunemente usato nell'UE e nella maggior parte delle aree geografiche al di fuori degli Stati Uniti. Sono inclusi i formati "giorno/mese/anno", "giorno-mese-anno" e "giorno mese anno". I nomi o le iniziali dei mesi non fanno distinzione tra maiuscole e minuscole.</span><span class="sxs-lookup"><span data-stu-id="19bb3-p105">This function looks for a date in the format commonly used in the E.U. (and most places outside the U.S.). This includes the formats "day/month/year", "day-month-year", and "day month year". The names or abbreviations of months are not case sensitive.</span></span>
  
<span data-ttu-id="19bb3-132">Esempi:</span><span class="sxs-lookup"><span data-stu-id="19bb3-132">Examples:</span></span>
  
- <span data-ttu-id="19bb3-133">2 Dec 2016</span><span class="sxs-lookup"><span data-stu-id="19bb3-133">2 Dec 2016</span></span>
    
- <span data-ttu-id="19bb3-134">dec 02 2016</span><span class="sxs-lookup"><span data-stu-id="19bb3-134">02 dec 2016</span></span>
    
- <span data-ttu-id="19bb3-135">2 Dec 16</span><span class="sxs-lookup"><span data-stu-id="19bb3-135">2 Dec 16</span></span>
    
- <span data-ttu-id="19bb3-136">2/12/2016</span><span class="sxs-lookup"><span data-stu-id="19bb3-136">2/12/2016</span></span>
    
- <span data-ttu-id="19bb3-137">12/02/16</span><span class="sxs-lookup"><span data-stu-id="19bb3-137">02/12/16</span></span>
    
- <span data-ttu-id="19bb3-138">2-dic-2016</span><span class="sxs-lookup"><span data-stu-id="19bb3-138">2-Dec-2016</span></span>
    
- <span data-ttu-id="19bb3-139">2-12-16</span><span class="sxs-lookup"><span data-stu-id="19bb3-139">2-12-16</span></span>
    
<span data-ttu-id="19bb3-140">Nomi dei mesi accettati:</span><span class="sxs-lookup"><span data-stu-id="19bb3-140">Accepted month names:</span></span>
  
- <span data-ttu-id="19bb3-141">Inglese</span><span class="sxs-lookup"><span data-stu-id="19bb3-141">English</span></span>
    
  - <span data-ttu-id="19bb3-142">Gennaio, febbraio, marzo, aprile, maggio, giugno, luglio, agosto, settembre, ottobre, novembre, dicembre</span><span class="sxs-lookup"><span data-stu-id="19bb3-142">January, February, march, April, may, June, July, August, September, October, November, December</span></span>
    
  - <span data-ttu-id="19bb3-143">Gennaio febbraio Mar. Apr. maggio giugno luglio agosto settembre ottobre Dec novembre.</span><span class="sxs-lookup"><span data-stu-id="19bb3-143">Jan. Feb. Mar. Apr. May June July Aug. Sept. Oct. Nov. Dec.</span></span>
    
- <span data-ttu-id="19bb3-144">Olandese</span><span class="sxs-lookup"><span data-stu-id="19bb3-144">Dutch</span></span>
    
  - <span data-ttu-id="19bb3-145">januari, februari, maart, April, mei, juni, juli, augustus, September, ocktober, October, November, December</span><span class="sxs-lookup"><span data-stu-id="19bb3-145">januari, februari, maart, April, mei, juni, juli, augustus, September, ocktober, October, November, December</span></span>
    
  - <span data-ttu-id="19bb3-146">Jan CTP di febbraio maart apr mei giugno luglio agosto set settembre ottobre okt novembre dicembre</span><span class="sxs-lookup"><span data-stu-id="19bb3-146">jan feb maart apr mei jun jul aug sep sept oct okt nov dec</span></span>
    
- <span data-ttu-id="19bb3-147">Francese</span><span class="sxs-lookup"><span data-stu-id="19bb3-147">French</span></span>
    
  - <span data-ttu-id="19bb3-148">janvier, février, mars, avril, mai, juillet ADR, août, septembre, octobre, novembre, décembre</span><span class="sxs-lookup"><span data-stu-id="19bb3-148">janvier, février, mars, avril, mai, juin juillet, août, septembre, octobre, novembre, décembre</span></span>
    
  - <span data-ttu-id="19bb3-p106">janv. févr. Mar avril mai ADR juil. août settembre. ott novembre. déc.</span><span class="sxs-lookup"><span data-stu-id="19bb3-p106">janv. févr. mars avril mai juin juil. août sept. oct. nov. déc.</span></span>
    
- <span data-ttu-id="19bb3-156">Tedesco</span><span class="sxs-lookup"><span data-stu-id="19bb3-156">German</span></span>
    
  - <span data-ttu-id="19bb3-157">jänuar, februar, märz, aprile, mai, juni juli, agosto, settembre, oktober, novembre, dezember</span><span class="sxs-lookup"><span data-stu-id="19bb3-157">jänuar, februar, märz, April, mai, juni juli, August, September, oktober, November, dezember</span></span>
    
  - <span data-ttu-id="19bb3-p107">Gen. / Jän. Febbraio März Apr. Mai Juni Juli agosto settembre Okt. Dez novembre.</span><span class="sxs-lookup"><span data-stu-id="19bb3-p107">Jan./Jän. Feb. März Apr. Mai Juni Juli Aug. Sept. Okt. Nov. Dez.</span></span>
    
- <span data-ttu-id="19bb3-161">Italiano</span><span class="sxs-lookup"><span data-stu-id="19bb3-161">Italian</span></span>
    
  - <span data-ttu-id="19bb3-162">gennaio, febbraio, marzo, aprile, maggio, giugno, luglio, agosto, settembre, ottobre, novembre, dicembre</span><span class="sxs-lookup"><span data-stu-id="19bb3-162">gennaio, febbraio, marzo, aprile, maggio, giugno, luglio, agosto, settembre, ottobre, novembre, dicembre</span></span>
    
  - <span data-ttu-id="19bb3-p108">Genn. febbr. Mar. APR. magg. giugno luglio ag. sett. ott. novembre. dic.</span><span class="sxs-lookup"><span data-stu-id="19bb3-p108">genn. febbr. mar. apr. magg. giugno luglio ag. sett. ott. nov. dic.</span></span>
    
- <span data-ttu-id="19bb3-173">Portoghese</span><span class="sxs-lookup"><span data-stu-id="19bb3-173">Portuguese</span></span>
    
  - <span data-ttu-id="19bb3-174">janeiro, fevereiro, março, marco, abril, maio, junho, julho, agosto, setembro, outubro, novembro, dezembro</span><span class="sxs-lookup"><span data-stu-id="19bb3-174">janeiro, fevereiro, março, marco, abril, maio, junho, julho, agosto, setembro, outubro, novembro, dezembro</span></span>
    
  - <span data-ttu-id="19bb3-175">Jan fev mar router di confine area mai giugno, luglio fa stabiliti novembre dez</span><span class="sxs-lookup"><span data-stu-id="19bb3-175">jan fev mar abr mai jun jul ago set out nov dez</span></span>
    
- <span data-ttu-id="19bb3-176">Spagnolo</span><span class="sxs-lookup"><span data-stu-id="19bb3-176">Spanish</span></span>
    
  - <span data-ttu-id="19bb3-177">enero, febrero, marzo, abril, mayo, junio, julio, agosto, septiembre, octubre, noviembre, diciembre</span><span class="sxs-lookup"><span data-stu-id="19bb3-177">enero, febrero, marzo, abril, mayo, junio, julio, agosto, septiembre, octubre, noviembre, diciembre</span></span>
    
  - <span data-ttu-id="19bb3-p109">enero CTP di febbraio. marzo abr. mayo Giu luglio. insieme/agosto settembre. ott novembre. dic.</span><span class="sxs-lookup"><span data-stu-id="19bb3-p109">enero feb. marzo abr. mayo jun. jul. agosto sept./set. oct. nov. dic.</span></span>
    
## <a name="funceudate1-deprecated"></a><span data-ttu-id="19bb3-186">Func_eu_date1 (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="19bb3-186">Func_eu_date1 (deprecated)</span></span>

> [!NOTE]
> <span data-ttu-id="19bb3-187">Questa funzione è deprecata perché supporta solo portoghese i nomi dei mesi, che ora sono inclusi nel `Func_eu_date` funzione sopra.</span><span class="sxs-lookup"><span data-stu-id="19bb3-187">This function is deprecated because it supports only Portuguese month names, which are now included in the  `Func_eu_date` function above.</span></span> 
  
<span data-ttu-id="19bb3-p110">Questa funzione Cerca una data in formato comunemente utilizzata nelle portoghese. Il formato per questa funzione è uguale `Func_eu_date`, diverse solo nella lingua utilizzata.</span><span class="sxs-lookup"><span data-stu-id="19bb3-p110">This function looks for a date in the format commonly used in Portuguese. The format for this function is the same as  `Func_eu_date`, differing only in the language used.</span></span>
  
<span data-ttu-id="19bb3-190">Esempi:</span><span class="sxs-lookup"><span data-stu-id="19bb3-190">Examples:</span></span>
  
- <span data-ttu-id="19bb3-191">2 Dez 2016</span><span class="sxs-lookup"><span data-stu-id="19bb3-191">2 Dez 2016</span></span>
    
- <span data-ttu-id="19bb3-192">02 dez 2016</span><span class="sxs-lookup"><span data-stu-id="19bb3-192">02 dez 2016</span></span>
    
- <span data-ttu-id="19bb3-193">2 Dez 16</span><span class="sxs-lookup"><span data-stu-id="19bb3-193">2 Dez 16</span></span>
    
- <span data-ttu-id="19bb3-194">2/12/2016</span><span class="sxs-lookup"><span data-stu-id="19bb3-194">2/12/2016</span></span>
    
- <span data-ttu-id="19bb3-195">12/02/16</span><span class="sxs-lookup"><span data-stu-id="19bb3-195">02/12/16</span></span>
    
- <span data-ttu-id="19bb3-196">2-Dez-2016</span><span class="sxs-lookup"><span data-stu-id="19bb3-196">2-Dez-2016</span></span>
    
- <span data-ttu-id="19bb3-197">2-12-16</span><span class="sxs-lookup"><span data-stu-id="19bb3-197">2-12-16</span></span>
    
<span data-ttu-id="19bb3-198">Nomi dei mesi accettati:</span><span class="sxs-lookup"><span data-stu-id="19bb3-198">Accepted month names:</span></span>
  
- <span data-ttu-id="19bb3-199">Portoghese</span><span class="sxs-lookup"><span data-stu-id="19bb3-199">Portuguese</span></span>
    
  - <span data-ttu-id="19bb3-200">janeiro, fevereiro, março, marco, abril, maio, junho, julho, agosto, setembro, outubro, novembro, dezembro</span><span class="sxs-lookup"><span data-stu-id="19bb3-200">janeiro, fevereiro, março, marco, abril, maio, junho, julho, agosto, setembro, outubro, novembro, dezembro</span></span>
    
  - <span data-ttu-id="19bb3-201">Jan fev mar router di confine area mai giugno, luglio fa stabiliti novembre dez</span><span class="sxs-lookup"><span data-stu-id="19bb3-201">jan fev mar abr mai jun jul ago set out nov dez</span></span>
    
## <a name="funceudate2-deprecated"></a><span data-ttu-id="19bb3-202">Func_eu_date2 (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="19bb3-202">Func_eu_date2 (deprecated)</span></span>

> [!NOTE]
> <span data-ttu-id="19bb3-203">Questa funzione è deprecata perché supporta solo olandese i nomi dei mesi, che ora sono inclusi nel `Func_eu_date` funzione sopra.</span><span class="sxs-lookup"><span data-stu-id="19bb3-203">This function is deprecated because it supports only Dutch month names, which are now included in the  `Func_eu_date` function above.</span></span> 
  
<span data-ttu-id="19bb3-p111">Questa funzione Cerca una data in formato comunemente utilizzata in olandese. Il formato per questa funzione è uguale `Func_eu_date`, diverse solo nella lingua utilizzata.</span><span class="sxs-lookup"><span data-stu-id="19bb3-p111">This function looks for a date in the format commonly used in Dutch. The format for this function is the same as  `Func_eu_date`, differing only in the language used.</span></span>
  
<span data-ttu-id="19bb3-206">Esempi:</span><span class="sxs-lookup"><span data-stu-id="19bb3-206">Examples:</span></span>
  
- <span data-ttu-id="19bb3-207">2 Mei 2016</span><span class="sxs-lookup"><span data-stu-id="19bb3-207">2 Mei 2016</span></span>
    
- <span data-ttu-id="19bb3-208">02 mei 2016</span><span class="sxs-lookup"><span data-stu-id="19bb3-208">02 mei 2016</span></span>
    
- <span data-ttu-id="19bb3-209">2 Mei 16</span><span class="sxs-lookup"><span data-stu-id="19bb3-209">2 Mei 16</span></span>
    
- <span data-ttu-id="19bb3-210">2/12/2016</span><span class="sxs-lookup"><span data-stu-id="19bb3-210">2/12/2016</span></span>
    
- <span data-ttu-id="19bb3-211">12/02/16</span><span class="sxs-lookup"><span data-stu-id="19bb3-211">02/12/16</span></span>
    
- <span data-ttu-id="19bb3-212">2-Mei-2016</span><span class="sxs-lookup"><span data-stu-id="19bb3-212">2-Mei-2016</span></span>
    
- <span data-ttu-id="19bb3-213">2-12-16</span><span class="sxs-lookup"><span data-stu-id="19bb3-213">2-12-16</span></span>
    
<span data-ttu-id="19bb3-214">Nomi dei mesi accettati:</span><span class="sxs-lookup"><span data-stu-id="19bb3-214">Accepted month names:</span></span>
  
- <span data-ttu-id="19bb3-215">Olandese</span><span class="sxs-lookup"><span data-stu-id="19bb3-215">Dutch</span></span>
    
  - <span data-ttu-id="19bb3-216">januari, februari, maart, April, mei, juni, juli, augustus, September, ocktober, October, November, December</span><span class="sxs-lookup"><span data-stu-id="19bb3-216">januari, februari, maart, April, mei, juni, juli, augustus, September, ocktober, October, November, December</span></span>
    
  - <span data-ttu-id="19bb3-217">Jan CTP di febbraio maart apr mei giugno luglio agosto set settembre ottobre okt novembre dicembre</span><span class="sxs-lookup"><span data-stu-id="19bb3-217">jan feb maart apr mei jun jul aug sep sept oct okt nov dec</span></span>
    
## <a name="funcexpirationdate"></a><span data-ttu-id="19bb3-218">Func_expiration_date</span><span class="sxs-lookup"><span data-stu-id="19bb3-218">Func_expiration_date</span></span>

<span data-ttu-id="19bb3-p112">Questa funzione Cerca una data in formati comunemente utilizzata dalle schede di dare e in cui escludere giorni favore dei mesi. Questa funzione corrispondenti date in formato "mese/anno", "mese-anno", "[nome del mese] anno" e "anno [abbreviazione mese]". I nomi o abbreviazioni mesi non sono distinzione tra maiuscole e minuscole.</span><span class="sxs-lookup"><span data-stu-id="19bb3-p112">This function looks for a date in the formats commonly used by credit and debit cards, which exclude days in favor of months. This function will match dates in format of "month/year", "month-year", "[month name] year", and "[month abbreviation] year". The names or abbreviations of months are not case sensitive.</span></span>
  
<span data-ttu-id="19bb3-222">Esempi</span><span class="sxs-lookup"><span data-stu-id="19bb3-222">Examples:</span></span>
  
- <span data-ttu-id="19bb3-223">MM/AA -- ad esempio, 01/11 o 1/11</span><span class="sxs-lookup"><span data-stu-id="19bb3-223">MM/YY -- for example, 01/11 or 1/11</span></span>
    
- <span data-ttu-id="19bb3-224">MM/AAAA -- ad esempio, 01/2011 o 1/2011</span><span class="sxs-lookup"><span data-stu-id="19bb3-224">MM/YYYY -- for example, 01/2011 or 1/2011</span></span>
    
- <span data-ttu-id="19bb3-225">MM-AA -- ad esempio, 01-22 o 1-11</span><span class="sxs-lookup"><span data-stu-id="19bb3-225">MM-YY -- for example, 01-22 or 1-11</span></span>
    
- <span data-ttu-id="19bb3-226">MM-AAAA-- ad esempio, 01-2000 o 1-2000</span><span class="sxs-lookup"><span data-stu-id="19bb3-226">MM-YYYY -- for example, 01-2000 or 1-2000</span></span>
    
<span data-ttu-id="19bb3-227">I formati seguenti supportano AA o AAAA:</span><span class="sxs-lookup"><span data-stu-id="19bb3-227">The following formats support YY or YYYY:</span></span>
  
- <span data-ttu-id="19bb3-228">Mese-AAAA -- ad esempio, .Gen-2010 o gennaio-2010 o Gen-10 o gennaio-10</span><span class="sxs-lookup"><span data-stu-id="19bb3-228">Month-YYYY -- for example, .Jan-2010 or january-2010 or Jan-10 or january-10</span></span>
    
- <span data-ttu-id="19bb3-229">Mese AAAA -- ad esempio, "gennaio 2010" o "Gen 2010" o" gennaio 10" o "Gen 10"</span><span class="sxs-lookup"><span data-stu-id="19bb3-229">Month YYYY -- for example, 'january 2010' or 'Jan 2010' or 'january 10' or 'Jan 10'</span></span>
    
- <span data-ttu-id="19bb3-230">MeseAAAA -- ad esempio, "gennaio2010" o "Gen2010" o "gennaio10" o "Gen10"</span><span class="sxs-lookup"><span data-stu-id="19bb3-230">MonthYYYY -- for example, 'january2010' or 'Jan2010' or 'january10' or 'Jan10'</span></span>
    
- <span data-ttu-id="19bb3-231">Mese/YYYY, ad esempio, "gennaio/2010" o "Gen/2010" o ' gennaio/10' o ' Jan/10'</span><span class="sxs-lookup"><span data-stu-id="19bb3-231">Month/YYYY -- for example, 'january/2010' or 'Jan/2010' or 'january/10' or 'Jan/10'</span></span>
    
<span data-ttu-id="19bb3-232">Nomi dei mesi accettati:</span><span class="sxs-lookup"><span data-stu-id="19bb3-232">Accepted month names:</span></span>
  
- <span data-ttu-id="19bb3-233">Inglese</span><span class="sxs-lookup"><span data-stu-id="19bb3-233">English</span></span>
    
  - <span data-ttu-id="19bb3-234">Gennaio, febbraio, marzo, aprile, maggio, giugno, luglio, agosto, settembre, ottobre, novembre, dicembre</span><span class="sxs-lookup"><span data-stu-id="19bb3-234">January, February, march, April, may, June, July, August, September, October, November, December</span></span>
    
  - <span data-ttu-id="19bb3-235">CTP di febbraio gen Mar Apr maggio giugno luglio agosto settembre Oct Dec novembre</span><span class="sxs-lookup"><span data-stu-id="19bb3-235">Jan Feb Mar Apr May June July Aug Sept Oct Nov Dec</span></span>
    
## <a name="funcusaddress"></a><span data-ttu-id="19bb3-236">Func_us_address</span><span class="sxs-lookup"><span data-stu-id="19bb3-236">Func_us_address</span></span>

<span data-ttu-id="19bb3-p113">Questa funzione cerca il nome di uno stato membro degli Stati Uniti o un'abbreviazione postale seguita da un CAP valido, esattamente come per gli indirizzi postali. Il CAP deve essere uno dei codici di avviamento postale corretti associati al nome o all'abbreviazione dello stato membro degli Stati Uniti. Il nome dello stato membro degli Stati Uniti e il CAP non possono essere separati da segni di punteggiatura o lettere.</span><span class="sxs-lookup"><span data-stu-id="19bb3-p113">This function looks for a U.S. state name or postal abbreviation followed by a valid zip code, just as they are used in postal addresses. The zip code must be one of the correct zip codes associated with the U.S. state name or abbreviation. The U.S. state name and zip code cannot be separated by punctuation or letters.</span></span>
  
<span data-ttu-id="19bb3-240">Esempi:</span><span class="sxs-lookup"><span data-stu-id="19bb3-240">Examples:</span></span>
  
- <span data-ttu-id="19bb3-241">Washington 98052</span><span class="sxs-lookup"><span data-stu-id="19bb3-241">Washington 98052</span></span>
    
- <span data-ttu-id="19bb3-242">Washington 98052-9998</span><span class="sxs-lookup"><span data-stu-id="19bb3-242">Washington 98052-9998</span></span>
    
- <span data-ttu-id="19bb3-243">WA 98052</span><span class="sxs-lookup"><span data-stu-id="19bb3-243">WA 98052</span></span>
    
- <span data-ttu-id="19bb3-244">WA 98052-9998</span><span class="sxs-lookup"><span data-stu-id="19bb3-244">WA 98052-9998</span></span>
    

