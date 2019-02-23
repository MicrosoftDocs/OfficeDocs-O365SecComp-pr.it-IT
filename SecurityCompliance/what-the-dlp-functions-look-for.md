---
title: Cosa individuano le funzioni DLP
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 6/18/2016
ms.audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MET150
ms.assetid: 94349ed4-5351-4ee2-bbda-70813c9ed693
description: I tipi di informazioni riservate cercano un modello specifico e lo confermano assicurando la corretta formattazione, l'applicazione di checksum e la ricerca di parole chiave rilevanti o altre informazioni. Alcune di queste funzionalità vengono eseguite dalle funzioni interne. In questo argomento vengono illustrate le funzionalità che devono essere cercate per comprendere il funzionamento dei tipi di informazioni riservate predefinite.
ms.openlocfilehash: 55c740e892e92902b368b2dcf7b0999cbc60f3ed
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/23/2019
ms.locfileid: "30219356"
---
# <a name="what-the-dlp-functions-look-for"></a><span data-ttu-id="ee306-105">Cosa individuano le funzioni DLP</span><span class="sxs-lookup"><span data-stu-id="ee306-105">What the DLP functions look for</span></span>

<span data-ttu-id="ee306-p102">Prevenzione della perdita di dati (DLP) include tipi di informazioni riservate, come il numero di carta di credito e il numero di carta di debito EU, pronti per essere utilizzati nei criteri DLP. Questi tipi di informazioni riservate cercano uno schema specifico e lo confermano assicurando la corretta formattazione, applicando checksum e individuando parole chiave specifiche o altre informazioni. Alcune di queste funzionalità vengono eseguite da funzioni interne. Ad esempio, il tipo di informazioni riservate relative al numero di carta di credito utilizza una funzione per cercare le date formattate come una data di scadenza, in modo da confermare che si tratta di un numero di carta di credito.</span><span class="sxs-lookup"><span data-stu-id="ee306-p102">Data loss prevention (DLP) includes sensitive information types, such as Credit Card Number and EU Debit Card Number, which are ready for you to use in your DLP policies. These sensitive information types look for a specific pattern and corroborate it by ensuring proper formatting, enforcing checksums, and looking for relevant keywords or other information. Some of this functionality is performed by internal functions. For example, the Credit Card Number sensitive information type uses a function to look for dates formatted like an expiration date, to help corroborate that a number is a credit card number.</span></span>
  
<span data-ttu-id="ee306-p103">In questo argomento viene descritto cosa viene cercato da queste funzioni per comprendere come funzionano i tipi di informazioni riservate predefiniti. Per ulteriori informazioni, vedere [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="ee306-p103">This topic explains what these functions look for, to help you understand how the predefined sensitive information types work. For more information, see [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="funcusdate"></a><span data-ttu-id="ee306-112">Func_us_date</span><span class="sxs-lookup"><span data-stu-id="ee306-112">Func_us_date</span></span>

<span data-ttu-id="ee306-p104">Questa funzione Cerca una data nel formato comunemente utilizzato negli Stati Uniti. Sono inclusi i formati "month/day/year", "month-day-year" e "month day year". I nomi o le abbreviazioni dei mesi non sono distinzione tra maiuscole e minuscole.</span><span class="sxs-lookup"><span data-stu-id="ee306-p104">This function looks for a date in the format commonly used in the U.S. This includes the formats "month/day/year", "month-day-year", and "month day year ". The names or abbreviations of months are not case sensitive.</span></span> 
  
<span data-ttu-id="ee306-115">Esempi:</span><span class="sxs-lookup"><span data-stu-id="ee306-115">Examples:</span></span>
  
- <span data-ttu-id="ee306-116">2 dicembre 2016</span><span class="sxs-lookup"><span data-stu-id="ee306-116">December 2, 2016</span></span>
    
- <span data-ttu-id="ee306-117">2 dicembre 2016</span><span class="sxs-lookup"><span data-stu-id="ee306-117">Dec 2, 2016</span></span>
    
- <span data-ttu-id="ee306-118">Dec 02 2016</span><span class="sxs-lookup"><span data-stu-id="ee306-118">dec 02 2016</span></span>
    
- <span data-ttu-id="ee306-119">12/2/2016</span><span class="sxs-lookup"><span data-stu-id="ee306-119">12/2/2016</span></span>
    
- <span data-ttu-id="ee306-120">12/02/16</span><span class="sxs-lookup"><span data-stu-id="ee306-120">12/02/16</span></span>
    
- <span data-ttu-id="ee306-121">Dec-2-2016</span><span class="sxs-lookup"><span data-stu-id="ee306-121">Dec-2-2016</span></span>
    
- <span data-ttu-id="ee306-122">12-2-16</span><span class="sxs-lookup"><span data-stu-id="ee306-122">12-2-16</span></span>
    
<span data-ttu-id="ee306-123">Nomi dei mesi accettati:</span><span class="sxs-lookup"><span data-stu-id="ee306-123">Accepted month names:</span></span>
  
- <span data-ttu-id="ee306-124">Inglese</span><span class="sxs-lookup"><span data-stu-id="ee306-124">English</span></span>
    
  - <span data-ttu-id="ee306-125">Gennaio, febbraio, marzo, aprile, maggio, giugno, luglio, agosto, settembre, ottobre, novembre, dicembre</span><span class="sxs-lookup"><span data-stu-id="ee306-125">January, February, march, April, may, June, July, August, September, October, November, December</span></span>
    
  - <span data-ttu-id="ee306-126">Gen febbraio Feb Mar. apr maggio giugno luglio agosto sett. ott. nov. Dec.</span><span class="sxs-lookup"><span data-stu-id="ee306-126">Jan. Feb. Mar. Apr. May June July Aug. Sept. Oct. Nov. Dec.</span></span>
    
## <a name="funceudate"></a><span data-ttu-id="ee306-127">Func_eu_date</span><span class="sxs-lookup"><span data-stu-id="ee306-127">Func_eu_date</span></span>

<span data-ttu-id="ee306-p105">Questa funzione consente di cercare una data nel formato comunemente usato nell'UE e nella maggior parte delle aree geografiche al di fuori degli Stati Uniti. Sono inclusi i formati "giorno/mese/anno", "giorno-mese-anno" e "giorno mese anno". I nomi o le iniziali dei mesi non fanno distinzione tra maiuscole e minuscole.</span><span class="sxs-lookup"><span data-stu-id="ee306-p105">This function looks for a date in the format commonly used in the E.U. (and most places outside the U.S.). This includes the formats "day/month/year", "day-month-year", and "day month year". The names or abbreviations of months are not case sensitive.</span></span>
  
<span data-ttu-id="ee306-132">Esempi:</span><span class="sxs-lookup"><span data-stu-id="ee306-132">Examples:</span></span>
  
- <span data-ttu-id="ee306-133">2 dicembre 2016</span><span class="sxs-lookup"><span data-stu-id="ee306-133">2 Dec 2016</span></span>
    
- <span data-ttu-id="ee306-134">02 dicembre 2016</span><span class="sxs-lookup"><span data-stu-id="ee306-134">02 dec 2016</span></span>
    
- <span data-ttu-id="ee306-135">2 dicembre 16</span><span class="sxs-lookup"><span data-stu-id="ee306-135">2 Dec 16</span></span>
    
- <span data-ttu-id="ee306-136">2/12/2016</span><span class="sxs-lookup"><span data-stu-id="ee306-136">2/12/2016</span></span>
    
- <span data-ttu-id="ee306-137">02/12/16</span><span class="sxs-lookup"><span data-stu-id="ee306-137">02/12/16</span></span>
    
- <span data-ttu-id="ee306-138">2-Dec-2016</span><span class="sxs-lookup"><span data-stu-id="ee306-138">2-Dec-2016</span></span>
    
- <span data-ttu-id="ee306-139">2-12-16</span><span class="sxs-lookup"><span data-stu-id="ee306-139">2-12-16</span></span>
    
<span data-ttu-id="ee306-140">Nomi dei mesi accettati:</span><span class="sxs-lookup"><span data-stu-id="ee306-140">Accepted month names:</span></span>
  
- <span data-ttu-id="ee306-141">Inglese</span><span class="sxs-lookup"><span data-stu-id="ee306-141">English</span></span>
    
  - <span data-ttu-id="ee306-142">Gennaio, febbraio, marzo, aprile, maggio, giugno, luglio, agosto, settembre, ottobre, novembre, dicembre</span><span class="sxs-lookup"><span data-stu-id="ee306-142">January, February, march, April, may, June, July, August, September, October, November, December</span></span>
    
  - <span data-ttu-id="ee306-143">Gen febbraio Feb Mar. apr maggio giugno luglio agosto sett. ott. nov. Dec.</span><span class="sxs-lookup"><span data-stu-id="ee306-143">Jan. Feb. Mar. Apr. May June July Aug. Sept. Oct. Nov. Dec.</span></span>
    
- <span data-ttu-id="ee306-144">Olandese</span><span class="sxs-lookup"><span data-stu-id="ee306-144">Dutch</span></span>
    
  - <span data-ttu-id="ee306-145">januari, februari, maart, April, mei, juni, juli, augustus, September, ocktober, October, November, December</span><span class="sxs-lookup"><span data-stu-id="ee306-145">januari, februari, maart, April, mei, juni, juli, augustus, September, ocktober, October, November, December</span></span>
    
  - <span data-ttu-id="ee306-146">Jan Feb maart apr Mei giu lug Aug Sep set ott Okt Nov Dec</span><span class="sxs-lookup"><span data-stu-id="ee306-146">jan feb maart apr mei jun jul aug sep sept oct okt nov dec</span></span>
    
- <span data-ttu-id="ee306-147">Francese</span><span class="sxs-lookup"><span data-stu-id="ee306-147">French</span></span>
    
  - <span data-ttu-id="ee306-148">Janvier, février, Mars, avril, mai, Juin Juillet, août, septembre, Octobre, novembre, décembre</span><span class="sxs-lookup"><span data-stu-id="ee306-148">janvier, février, mars, avril, mai, juin juillet, août, septembre, octobre, novembre, décembre</span></span>
    
  - <span data-ttu-id="ee306-p106">janv. févr. Mars Avril mai juin juil. août sett. ott. nov. déc.</span><span class="sxs-lookup"><span data-stu-id="ee306-p106">janv. févr. mars avril mai juin juil. août sept. oct. nov. déc.</span></span>
    
- <span data-ttu-id="ee306-156">Tedesco</span><span class="sxs-lookup"><span data-stu-id="ee306-156">German</span></span>
    
  - <span data-ttu-id="ee306-157">jänuar, febbraio, März, April, mai, Juni Juli, August, September, Oktober, November, Dezember</span><span class="sxs-lookup"><span data-stu-id="ee306-157">jänuar, februar, märz, April, mai, juni juli, August, September, oktober, November, dezember</span></span>
    
  - <span data-ttu-id="ee306-p107">Gen./Jän. Feb. März apr. mai Juni luglio Okt. Nov. dic.</span><span class="sxs-lookup"><span data-stu-id="ee306-p107">Jan./Jän. Feb. März Apr. Mai Juni Juli Aug. Sept. Okt. Nov. Dez.</span></span>
    
- <span data-ttu-id="ee306-161">Italiano</span><span class="sxs-lookup"><span data-stu-id="ee306-161">Italian</span></span>
    
  - <span data-ttu-id="ee306-162">gennaio, febbraio, marzo, aprile, maggio, giugno, luglio, agosto, settembre, ottobre, novembre, dicembre</span><span class="sxs-lookup"><span data-stu-id="ee306-162">gennaio, febbraio, marzo, aprile, maggio, giugno, luglio, agosto, settembre, ottobre, novembre, dicembre</span></span>
    
  - <span data-ttu-id="ee306-p108">Genn. febbr. mar. apr. magg. giugno luglio AG. ovvero. ott. novembre. dic.</span><span class="sxs-lookup"><span data-stu-id="ee306-p108">genn. febbr. mar. apr. magg. giugno luglio ag. sett. ott. nov. dic.</span></span>
    
- <span data-ttu-id="ee306-173">Portoghese</span><span class="sxs-lookup"><span data-stu-id="ee306-173">Portuguese</span></span>
    
  - <span data-ttu-id="ee306-174">janeiro, fevereiro, março, marco, abril, maio, junho, julho, agosto, setembro, outubro, novembro, dezembro</span><span class="sxs-lookup"><span data-stu-id="ee306-174">janeiro, fevereiro, março, marco, abril, maio, junho, julho, agosto, setembro, outubro, novembro, dezembro</span></span>
    
  - <span data-ttu-id="ee306-175">Jan FEV Mar ABR mai Jun Jul ago set out nov dic</span><span class="sxs-lookup"><span data-stu-id="ee306-175">jan fev mar abr mai jun jul ago set out nov dez</span></span>
    
- <span data-ttu-id="ee306-176">Spagnolo</span><span class="sxs-lookup"><span data-stu-id="ee306-176">Spanish</span></span>
    
  - <span data-ttu-id="ee306-177">enero, febrero, marzo, Abril, Mayo, Junio, Julio, agosto, Septiembre, Octubre, Noviembre, Diciembre</span><span class="sxs-lookup"><span data-stu-id="ee306-177">enero, febrero, marzo, abril, mayo, junio, julio, agosto, septiembre, octubre, noviembre, diciembre</span></span>
    
  - <span data-ttu-id="ee306-p109">enero feb. marzo ABR. Mayo Jun. Jul. agosto Sept/set. ott. nov. dic.</span><span class="sxs-lookup"><span data-stu-id="ee306-p109">enero feb. marzo abr. mayo jun. jul. agosto sept./set. oct. nov. dic.</span></span>
    
## <a name="funceudate1-deprecated"></a><span data-ttu-id="ee306-186">Func_eu_date1 (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="ee306-186">Func_eu_date1 (deprecated)</span></span>

> [!NOTE]
> <span data-ttu-id="ee306-187">Questa funzione è obsoleta perché supporta solo i nomi dei mesi portoghesi, che ora sono inclusi nella `Func_eu_date` funzione precedente.</span><span class="sxs-lookup"><span data-stu-id="ee306-187">This function is deprecated because it supports only Portuguese month names, which are now included in the  `Func_eu_date` function above.</span></span> 
  
<span data-ttu-id="ee306-p110">Questa funzione consente di ricercare una data nel formato comunemente utilizzato in portoghese. Il formato di questa funzione è lo stesso che `Func_eu_date`differisce solo nella lingua utilizzata.</span><span class="sxs-lookup"><span data-stu-id="ee306-p110">This function looks for a date in the format commonly used in Portuguese. The format for this function is the same as  `Func_eu_date`, differing only in the language used.</span></span>
  
<span data-ttu-id="ee306-190">Esempi:</span><span class="sxs-lookup"><span data-stu-id="ee306-190">Examples:</span></span>
  
- <span data-ttu-id="ee306-191">2 (2016).</span><span class="sxs-lookup"><span data-stu-id="ee306-191">2 Dez 2016</span></span>
    
- <span data-ttu-id="ee306-192">02 (2016).</span><span class="sxs-lookup"><span data-stu-id="ee306-192">02 dez 2016</span></span>
    
- <span data-ttu-id="ee306-193">2 con il 16</span><span class="sxs-lookup"><span data-stu-id="ee306-193">2 Dez 16</span></span>
    
- <span data-ttu-id="ee306-194">2/12/2016</span><span class="sxs-lookup"><span data-stu-id="ee306-194">2/12/2016</span></span>
    
- <span data-ttu-id="ee306-195">02/12/16</span><span class="sxs-lookup"><span data-stu-id="ee306-195">02/12/16</span></span>
    
- <span data-ttu-id="ee306-196">2-------2016</span><span class="sxs-lookup"><span data-stu-id="ee306-196">2-Dez-2016</span></span>
    
- <span data-ttu-id="ee306-197">2-12-16</span><span class="sxs-lookup"><span data-stu-id="ee306-197">2-12-16</span></span>
    
<span data-ttu-id="ee306-198">Nomi dei mesi accettati:</span><span class="sxs-lookup"><span data-stu-id="ee306-198">Accepted month names:</span></span>
  
- <span data-ttu-id="ee306-199">Portoghese</span><span class="sxs-lookup"><span data-stu-id="ee306-199">Portuguese</span></span>
    
  - <span data-ttu-id="ee306-200">janeiro, fevereiro, março, marco, abril, maio, junho, julho, agosto, setembro, outubro, novembro, dezembro</span><span class="sxs-lookup"><span data-stu-id="ee306-200">janeiro, fevereiro, março, marco, abril, maio, junho, julho, agosto, setembro, outubro, novembro, dezembro</span></span>
    
  - <span data-ttu-id="ee306-201">Jan FEV Mar ABR mai Jun Jul ago set out nov dic</span><span class="sxs-lookup"><span data-stu-id="ee306-201">jan fev mar abr mai jun jul ago set out nov dez</span></span>
    
## <a name="funceudate2-deprecated"></a><span data-ttu-id="ee306-202">Func_eu_date2 (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="ee306-202">Func_eu_date2 (deprecated)</span></span>

> [!NOTE]
> <span data-ttu-id="ee306-203">Questa funzione è obsoleta perché supporta solo i nomi dei mesi olandesi, che ora sono inclusi `Func_eu_date` nella funzione precedente.</span><span class="sxs-lookup"><span data-stu-id="ee306-203">This function is deprecated because it supports only Dutch month names, which are now included in the  `Func_eu_date` function above.</span></span> 
  
<span data-ttu-id="ee306-p111">Questa funzione consente di ricercare una data nel formato comunemente utilizzato in Fiammingo. Il formato di questa funzione è lo stesso che `Func_eu_date`differisce solo nella lingua utilizzata.</span><span class="sxs-lookup"><span data-stu-id="ee306-p111">This function looks for a date in the format commonly used in Dutch. The format for this function is the same as  `Func_eu_date`, differing only in the language used.</span></span>
  
<span data-ttu-id="ee306-206">Esempi:</span><span class="sxs-lookup"><span data-stu-id="ee306-206">Examples:</span></span>
  
- <span data-ttu-id="ee306-207">2 Mei 2016</span><span class="sxs-lookup"><span data-stu-id="ee306-207">2 Mei 2016</span></span>
    
- <span data-ttu-id="ee306-208">02 Mei 2016</span><span class="sxs-lookup"><span data-stu-id="ee306-208">02 mei 2016</span></span>
    
- <span data-ttu-id="ee306-209">2 Mei 16</span><span class="sxs-lookup"><span data-stu-id="ee306-209">2 Mei 16</span></span>
    
- <span data-ttu-id="ee306-210">2/12/2016</span><span class="sxs-lookup"><span data-stu-id="ee306-210">2/12/2016</span></span>
    
- <span data-ttu-id="ee306-211">02/12/16</span><span class="sxs-lookup"><span data-stu-id="ee306-211">02/12/16</span></span>
    
- <span data-ttu-id="ee306-212">2-Mei-2016</span><span class="sxs-lookup"><span data-stu-id="ee306-212">2-Mei-2016</span></span>
    
- <span data-ttu-id="ee306-213">2-12-16</span><span class="sxs-lookup"><span data-stu-id="ee306-213">2-12-16</span></span>
    
<span data-ttu-id="ee306-214">Nomi dei mesi accettati:</span><span class="sxs-lookup"><span data-stu-id="ee306-214">Accepted month names:</span></span>
  
- <span data-ttu-id="ee306-215">Olandese</span><span class="sxs-lookup"><span data-stu-id="ee306-215">Dutch</span></span>
    
  - <span data-ttu-id="ee306-216">januari, februari, maart, April, mei, juni, juli, augustus, September, ocktober, October, November, December</span><span class="sxs-lookup"><span data-stu-id="ee306-216">januari, februari, maart, April, mei, juni, juli, augustus, September, ocktober, October, November, December</span></span>
    
  - <span data-ttu-id="ee306-217">Jan Feb maart apr Mei giu lug Aug Sep set ott Okt Nov Dec</span><span class="sxs-lookup"><span data-stu-id="ee306-217">jan feb maart apr mei jun jul aug sep sept oct okt nov dec</span></span>
    
## <a name="funcexpirationdate"></a><span data-ttu-id="ee306-218">Func_expiration_date</span><span class="sxs-lookup"><span data-stu-id="ee306-218">Func_expiration_date</span></span>

<span data-ttu-id="ee306-p112">Questa funzione Cerca una data nei formati comunemente usati dalle carte di credito e di debito, che escludono i giorni a favore dei mesi. Questa funzione corrisponderà alle date nel formato "month/year", "month-year", "[Month Name] Year" e "[month abbreviation] Year". I nomi o le abbreviazioni dei mesi non sono distinzione tra maiuscole e minuscole.</span><span class="sxs-lookup"><span data-stu-id="ee306-p112">This function looks for a date in the formats commonly used by credit and debit cards, which exclude days in favor of months. This function will match dates in format of "month/year", "month-year", "[month name] year", and "[month abbreviation] year". The names or abbreviations of months are not case sensitive.</span></span>
  
<span data-ttu-id="ee306-222">Esempi</span><span class="sxs-lookup"><span data-stu-id="ee306-222">Examples:</span></span>
  
- <span data-ttu-id="ee306-223">MM/AA -- ad esempio, 01/11 o 1/11</span><span class="sxs-lookup"><span data-stu-id="ee306-223">MM/YY -- for example, 01/11 or 1/11</span></span>
    
- <span data-ttu-id="ee306-224">MM/AAAA -- ad esempio, 01/2011 o 1/2011</span><span class="sxs-lookup"><span data-stu-id="ee306-224">MM/YYYY -- for example, 01/2011 or 1/2011</span></span>
    
- <span data-ttu-id="ee306-225">MM-AA -- ad esempio, 01-22 o 1-11</span><span class="sxs-lookup"><span data-stu-id="ee306-225">MM-YY -- for example, 01-22 or 1-11</span></span>
    
- <span data-ttu-id="ee306-226">MM-AAAA-- ad esempio, 01-2000 o 1-2000</span><span class="sxs-lookup"><span data-stu-id="ee306-226">MM-YYYY -- for example, 01-2000 or 1-2000</span></span>
    
<span data-ttu-id="ee306-227">I formati seguenti supportano AA o AAAA:</span><span class="sxs-lookup"><span data-stu-id="ee306-227">The following formats support YY or YYYY:</span></span>
  
- <span data-ttu-id="ee306-228">Mese-AAAA -- ad esempio, .Gen-2010 o gennaio-2010 o Gen-10 o gennaio-10</span><span class="sxs-lookup"><span data-stu-id="ee306-228">Month-YYYY -- for example, .Jan-2010 or january-2010 or Jan-10 or january-10</span></span>
    
- <span data-ttu-id="ee306-229">Mese AAAA -- ad esempio, "gennaio 2010" o "Gen 2010" o" gennaio 10" o "Gen 10"</span><span class="sxs-lookup"><span data-stu-id="ee306-229">Month YYYY -- for example, 'january 2010' or 'Jan 2010' or 'january 10' or 'Jan 10'</span></span>
    
- <span data-ttu-id="ee306-230">MeseAAAA -- ad esempio, "gennaio2010" o "Gen2010" o "gennaio10" o "Gen10"</span><span class="sxs-lookup"><span data-stu-id="ee306-230">MonthYYYY -- for example, 'january2010' or 'Jan2010' or 'january10' or 'Jan10'</span></span>
    
- <span data-ttu-id="ee306-231">Mese/AAAA--ad esempio, "gennaio/2010" o "gen/2010" o "gennaio/10" o "gen/10"</span><span class="sxs-lookup"><span data-stu-id="ee306-231">Month/YYYY -- for example, 'january/2010' or 'Jan/2010' or 'january/10' or 'Jan/10'</span></span>
    
<span data-ttu-id="ee306-232">Nomi dei mesi accettati:</span><span class="sxs-lookup"><span data-stu-id="ee306-232">Accepted month names:</span></span>
  
- <span data-ttu-id="ee306-233">Inglese</span><span class="sxs-lookup"><span data-stu-id="ee306-233">English</span></span>
    
  - <span data-ttu-id="ee306-234">Gennaio, febbraio, marzo, aprile, maggio, giugno, luglio, agosto, settembre, ottobre, novembre, dicembre</span><span class="sxs-lookup"><span data-stu-id="ee306-234">January, February, march, April, may, June, July, August, September, October, November, December</span></span>
    
  - <span data-ttu-id="ee306-235">Gen feb mar apr maggio giugno luglio Aug settembre Ott Nov Dec</span><span class="sxs-lookup"><span data-stu-id="ee306-235">Jan Feb Mar Apr May June July Aug Sept Oct Nov Dec</span></span>
    
## <a name="funcusaddress"></a><span data-ttu-id="ee306-236">Func_us_address</span><span class="sxs-lookup"><span data-stu-id="ee306-236">Func_us_address</span></span>

<span data-ttu-id="ee306-p113">Questa funzione cerca il nome di uno stato membro degli Stati Uniti o un'abbreviazione postale seguita da un CAP valido, esattamente come per gli indirizzi postali. Il CAP deve essere uno dei codici di avviamento postale corretti associati al nome o all'abbreviazione dello stato membro degli Stati Uniti. Il nome dello stato membro degli Stati Uniti e il CAP non possono essere separati da segni di punteggiatura o lettere.</span><span class="sxs-lookup"><span data-stu-id="ee306-p113">This function looks for a U.S. state name or postal abbreviation followed by a valid zip code, just as they are used in postal addresses. The zip code must be one of the correct zip codes associated with the U.S. state name or abbreviation. The U.S. state name and zip code cannot be separated by punctuation or letters.</span></span>
  
<span data-ttu-id="ee306-240">Esempi:</span><span class="sxs-lookup"><span data-stu-id="ee306-240">Examples:</span></span>
  
- <span data-ttu-id="ee306-241">Washington 98052</span><span class="sxs-lookup"><span data-stu-id="ee306-241">Washington 98052</span></span>
    
- <span data-ttu-id="ee306-242">Washington 98052-9998</span><span class="sxs-lookup"><span data-stu-id="ee306-242">Washington 98052-9998</span></span>
    
- <span data-ttu-id="ee306-243">WA 98052</span><span class="sxs-lookup"><span data-stu-id="ee306-243">WA 98052</span></span>
    
- <span data-ttu-id="ee306-244">WA 98052-9998</span><span class="sxs-lookup"><span data-stu-id="ee306-244">WA 98052-9998</span></span>
    

