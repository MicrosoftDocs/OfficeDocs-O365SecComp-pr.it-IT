---
title: Cosa individuano le funzioni DLP
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 6/18/2016
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: I tipi di informazioni riservate cercano un modello specifico e lo confermano assicurando la corretta formattazione, l'applicazione di checksum e la ricerca di parole chiave rilevanti o altre informazioni. Alcune di queste funzionalità vengono eseguite da funzioni interne. In questo argomento viene descritto cosa viene cercato da queste funzioni per comprendere come funzionano i tipi di informazioni riservate predefiniti.
ms.openlocfilehash: 044920a7ff28ffc1c4338a642bc130ee07ef7264
ms.sourcegitcommit: 0d5a863f48914eeaaf29f7d2a2022618de186247
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2019
ms.locfileid: "34078002"
---
# <a name="what-the-dlp-functions-look-for"></a><span data-ttu-id="591c8-105">Elementi cercati dalle funzioni dei criteri di prevenzione della perdita dei dati</span><span class="sxs-lookup"><span data-stu-id="591c8-105">What the DLP functions look for</span></span>

<span data-ttu-id="591c8-p102">Prevenzione della perdita di dati (DLP) include tipi di informazioni riservate, come il numero di carta di credito e il numero di carta di debito EU, pronti per essere utilizzati nei criteri DLP. Questi tipi di informazioni riservate cercano uno schema specifico e lo confermano assicurando la corretta formattazione, applicando checksum e individuando parole chiave specifiche o altre informazioni. Alcune di queste funzionalità vengono eseguite da funzioni interne. Ad esempio, il tipo di informazioni riservate relative al numero di carta di credito utilizza una funzione per cercare le date formattate come una data di scadenza, in modo da confermare che si tratta di un numero di carta di credito.</span><span class="sxs-lookup"><span data-stu-id="591c8-p102">Data loss prevention (DLP) includes sensitive information types, such as Credit Card Number and EU Debit Card Number, which are ready for you to use in your DLP policies. These sensitive information types look for a specific pattern and corroborate it by ensuring proper formatting, enforcing checksums, and looking for relevant keywords or other information. Some of this functionality is performed by internal functions. For example, the Credit Card Number sensitive information type uses a function to look for dates formatted like an expiration date, to help corroborate that a number is a credit card number.</span></span>
  
<span data-ttu-id="591c8-110">In questo argomento viene descritto cosa viene cercato da queste funzioni per comprendere come funzionano i tipi di informazioni riservate predefiniti.</span><span class="sxs-lookup"><span data-stu-id="591c8-110">This topic explains what these functions look for, to help you understand how the predefined sensitive information types work.</span></span> <span data-ttu-id="591c8-111">Per ulteriori informazioni, vedere [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="591c8-111">For more information, see [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="funcusdate"></a><span data-ttu-id="591c8-112">Func_us_date</span><span class="sxs-lookup"><span data-stu-id="591c8-112">Func_us_date</span></span>

<span data-ttu-id="591c8-113">Questa funzione Cerca una data nel formato comunemente utilizzato negli Stati Uniti. Sono inclusi i formati "month/day/year", "month-day-year" e "month day year".</span><span class="sxs-lookup"><span data-stu-id="591c8-113">This function looks for a date in the format commonly used in the U.S. This includes the formats "month/day/year", "month-day-year", and "month day year ".</span></span> <span data-ttu-id="591c8-114">I nomi o le iniziali dei mesi non fanno distinzione tra maiuscole e minuscole.</span><span class="sxs-lookup"><span data-stu-id="591c8-114">The names or abbreviations of months are not case sensitive.</span></span> 
  
<span data-ttu-id="591c8-115">Esempi:</span><span class="sxs-lookup"><span data-stu-id="591c8-115">Examples:</span></span>
  
- <span data-ttu-id="591c8-116">2 dicembre 2016</span><span class="sxs-lookup"><span data-stu-id="591c8-116">December 2, 2016</span></span>
    
- <span data-ttu-id="591c8-117">2 dicembre 2016</span><span class="sxs-lookup"><span data-stu-id="591c8-117">Dec 2, 2016</span></span>
    
- <span data-ttu-id="591c8-118">Dec 02 2016</span><span class="sxs-lookup"><span data-stu-id="591c8-118">dec 02 2016</span></span>
    
- <span data-ttu-id="591c8-119">12/2/2016</span><span class="sxs-lookup"><span data-stu-id="591c8-119">12/2/2016</span></span>
    
- <span data-ttu-id="591c8-120">12/02/16</span><span class="sxs-lookup"><span data-stu-id="591c8-120">12/02/16</span></span>
    
- <span data-ttu-id="591c8-121">Dec-2-2016</span><span class="sxs-lookup"><span data-stu-id="591c8-121">Dec-2-2016</span></span>
    
- <span data-ttu-id="591c8-122">12-2-16</span><span class="sxs-lookup"><span data-stu-id="591c8-122">12-2-16</span></span>
    
<span data-ttu-id="591c8-123">Nomi dei mesi accettati:</span><span class="sxs-lookup"><span data-stu-id="591c8-123">Accepted month names:</span></span>
  
- <span data-ttu-id="591c8-124">Inglese</span><span class="sxs-lookup"><span data-stu-id="591c8-124">English</span></span>
    
  - <span data-ttu-id="591c8-125">Gennaio, febbraio, marzo, aprile, maggio, giugno, luglio, agosto, settembre, ottobre, novembre, dicembre</span><span class="sxs-lookup"><span data-stu-id="591c8-125">January, February, march, April, may, June, July, August, September, October, November, December</span></span>
    
  - <span data-ttu-id="591c8-126">Gen febbraio Feb Mar. apr maggio giugno luglio agosto sett. ott. nov. Dec.</span><span class="sxs-lookup"><span data-stu-id="591c8-126">Jan. Feb. Mar. Apr. May June July Aug. Sept. Oct. Nov. Dec.</span></span>
    
## <a name="funceudate"></a><span data-ttu-id="591c8-127">Func_eu_date</span><span class="sxs-lookup"><span data-stu-id="591c8-127">Func_eu_date</span></span>

<span data-ttu-id="591c8-p105">Questa funzione consente di cercare una data nel formato comunemente usato nell'UE e nella maggior parte delle aree geografiche al di fuori degli Stati Uniti. Sono inclusi i formati "giorno/mese/anno", "giorno-mese-anno" e "giorno mese anno". I nomi o le iniziali dei mesi non fanno distinzione tra maiuscole e minuscole.</span><span class="sxs-lookup"><span data-stu-id="591c8-p105">This function looks for a date in the format commonly used in the E.U. (and most places outside the U.S.). This includes the formats "day/month/year", "day-month-year", and "day month year". The names or abbreviations of months are not case sensitive.</span></span>
  
<span data-ttu-id="591c8-132">Esempi:</span><span class="sxs-lookup"><span data-stu-id="591c8-132">Examples:</span></span>
  
- <span data-ttu-id="591c8-133">2 dicembre 2016</span><span class="sxs-lookup"><span data-stu-id="591c8-133">2 Dec 2016</span></span>
    
- <span data-ttu-id="591c8-134">02 dicembre 2016</span><span class="sxs-lookup"><span data-stu-id="591c8-134">02 dec 2016</span></span>
    
- <span data-ttu-id="591c8-135">2 dicembre 16</span><span class="sxs-lookup"><span data-stu-id="591c8-135">2 Dec 16</span></span>
    
- <span data-ttu-id="591c8-136">2/12/2016</span><span class="sxs-lookup"><span data-stu-id="591c8-136">2/12/2016</span></span>
    
- <span data-ttu-id="591c8-137">02/12/16</span><span class="sxs-lookup"><span data-stu-id="591c8-137">02/12/16</span></span>
    
- <span data-ttu-id="591c8-138">2-Dec-2016</span><span class="sxs-lookup"><span data-stu-id="591c8-138">2-Dec-2016</span></span>
    
- <span data-ttu-id="591c8-139">2-12-16</span><span class="sxs-lookup"><span data-stu-id="591c8-139">2-12-16</span></span>
    
<span data-ttu-id="591c8-140">Nomi dei mesi accettati:</span><span class="sxs-lookup"><span data-stu-id="591c8-140">Accepted month names:</span></span>
  
- <span data-ttu-id="591c8-141">Inglese</span><span class="sxs-lookup"><span data-stu-id="591c8-141">English</span></span>
    
  - <span data-ttu-id="591c8-142">Gennaio, febbraio, marzo, aprile, maggio, giugno, luglio, agosto, settembre, ottobre, novembre, dicembre</span><span class="sxs-lookup"><span data-stu-id="591c8-142">January, February, march, April, may, June, July, August, September, October, November, December</span></span>
    
  - <span data-ttu-id="591c8-143">Gen febbraio Feb Mar. apr maggio giugno luglio agosto sett. ott. nov. Dec.</span><span class="sxs-lookup"><span data-stu-id="591c8-143">Jan. Feb. Mar. Apr. May June July Aug. Sept. Oct. Nov. Dec.</span></span>
    
- <span data-ttu-id="591c8-144">Olandese</span><span class="sxs-lookup"><span data-stu-id="591c8-144">Dutch</span></span>
    
  - <span data-ttu-id="591c8-145">januari, februari, maart, April, mei, juni, juli, augustus, September, ocktober, October, November, December</span><span class="sxs-lookup"><span data-stu-id="591c8-145">januari, februari, maart, April, mei, juni, juli, augustus, September, ocktober, October, November, December</span></span>
    
  - <span data-ttu-id="591c8-146">Jan Feb maart apr Mei giu lug Aug Sep set ott Okt Nov Dec</span><span class="sxs-lookup"><span data-stu-id="591c8-146">jan feb maart apr mei jun jul aug sep sept oct okt nov dec</span></span>
    
- <span data-ttu-id="591c8-147">Francese</span><span class="sxs-lookup"><span data-stu-id="591c8-147">French</span></span>
    
  - <span data-ttu-id="591c8-148">Janvier, février, Mars, avril, mai, Juin Juillet, août, septembre, Octobre, novembre, décembre</span><span class="sxs-lookup"><span data-stu-id="591c8-148">janvier, février, mars, avril, mai, juin juillet, août, septembre, octobre, novembre, décembre</span></span>
    
  - <span data-ttu-id="591c8-149">janv.</span><span class="sxs-lookup"><span data-stu-id="591c8-149">janv.</span></span> <span data-ttu-id="591c8-150">févr.</span><span class="sxs-lookup"><span data-stu-id="591c8-150">févr.</span></span> <span data-ttu-id="591c8-151">Mars Avril mai juin juil.</span><span class="sxs-lookup"><span data-stu-id="591c8-151">mars avril mai juin juil.</span></span> <span data-ttu-id="591c8-152">août sett.</span><span class="sxs-lookup"><span data-stu-id="591c8-152">août sept.</span></span> <span data-ttu-id="591c8-153">personalizzazione.</span><span class="sxs-lookup"><span data-stu-id="591c8-153">oct.</span></span> <span data-ttu-id="591c8-154">novembre.</span><span class="sxs-lookup"><span data-stu-id="591c8-154">nov.</span></span> <span data-ttu-id="591c8-155">déc.</span><span class="sxs-lookup"><span data-stu-id="591c8-155">déc.</span></span>
    
- <span data-ttu-id="591c8-156">Tedesco</span><span class="sxs-lookup"><span data-stu-id="591c8-156">German</span></span>
    
  - <span data-ttu-id="591c8-157">jänuar, febbraio, März, April, mai, Juni Juli, August, September, Oktober, November, Dezember</span><span class="sxs-lookup"><span data-stu-id="591c8-157">jänuar, februar, märz, April, mai, juni juli, August, September, oktober, November, dezember</span></span>
    
  - <span data-ttu-id="591c8-158">Gen./Jän.</span><span class="sxs-lookup"><span data-stu-id="591c8-158">Jan./Jän.</span></span> <span data-ttu-id="591c8-159">Feb. März apr. mai Juni luglio Okt.</span><span class="sxs-lookup"><span data-stu-id="591c8-159">Feb. März Apr. Mai Juni Juli Aug. Sept. Okt.</span></span> <span data-ttu-id="591c8-160">Nov. dic.</span><span class="sxs-lookup"><span data-stu-id="591c8-160">Nov. Dez.</span></span>
    
- <span data-ttu-id="591c8-161">Italiano</span><span class="sxs-lookup"><span data-stu-id="591c8-161">Italian</span></span>
    
  - <span data-ttu-id="591c8-162">gennaio, febbraio, marzo, aprile, maggio, giugno, luglio, agosto, settembre, ottobre, novembre, dicembre</span><span class="sxs-lookup"><span data-stu-id="591c8-162">gennaio, febbraio, marzo, aprile, maggio, giugno, luglio, agosto, settembre, ottobre, novembre, dicembre</span></span>
    
  - <span data-ttu-id="591c8-163">Genn.</span><span class="sxs-lookup"><span data-stu-id="591c8-163">genn.</span></span> <span data-ttu-id="591c8-164">febbr.</span><span class="sxs-lookup"><span data-stu-id="591c8-164">febbr.</span></span> <span data-ttu-id="591c8-165">mar.</span><span class="sxs-lookup"><span data-stu-id="591c8-165">mar.</span></span> <span data-ttu-id="591c8-166">apr.</span><span class="sxs-lookup"><span data-stu-id="591c8-166">apr.</span></span> <span data-ttu-id="591c8-167">magg.</span><span class="sxs-lookup"><span data-stu-id="591c8-167">magg.</span></span> <span data-ttu-id="591c8-168">giugno luglio AG.</span><span class="sxs-lookup"><span data-stu-id="591c8-168">giugno luglio ag.</span></span> <span data-ttu-id="591c8-169">ovvero.</span><span class="sxs-lookup"><span data-stu-id="591c8-169">sett.</span></span> <span data-ttu-id="591c8-170">ott.</span><span class="sxs-lookup"><span data-stu-id="591c8-170">ott.</span></span> <span data-ttu-id="591c8-171">novembre.</span><span class="sxs-lookup"><span data-stu-id="591c8-171">nov.</span></span> <span data-ttu-id="591c8-172">dic.</span><span class="sxs-lookup"><span data-stu-id="591c8-172">dic.</span></span>
    
- <span data-ttu-id="591c8-173">Portoghese</span><span class="sxs-lookup"><span data-stu-id="591c8-173">Portuguese</span></span>
    
  - <span data-ttu-id="591c8-174">janeiro, fevereiro, março, marco, abril, maio, junho, julho, agosto, setembro, outubro, novembro, dezembro</span><span class="sxs-lookup"><span data-stu-id="591c8-174">janeiro, fevereiro, março, marco, abril, maio, junho, julho, agosto, setembro, outubro, novembro, dezembro</span></span>
    
  - <span data-ttu-id="591c8-175">Jan FEV Mar ABR mai Jun Jul ago set out nov dic</span><span class="sxs-lookup"><span data-stu-id="591c8-175">jan fev mar abr mai jun jul ago set out nov dez</span></span>
    
- <span data-ttu-id="591c8-176">Spagnolo</span><span class="sxs-lookup"><span data-stu-id="591c8-176">Spanish</span></span>
    
  - <span data-ttu-id="591c8-177">enero, febrero, marzo, Abril, Mayo, Junio, Julio, agosto, Septiembre, Octubre, Noviembre, Diciembre</span><span class="sxs-lookup"><span data-stu-id="591c8-177">enero, febrero, marzo, abril, mayo, junio, julio, agosto, septiembre, octubre, noviembre, diciembre</span></span>
    
  - <span data-ttu-id="591c8-178">enero feb.</span><span class="sxs-lookup"><span data-stu-id="591c8-178">enero feb.</span></span> <span data-ttu-id="591c8-179">marzo ABR.</span><span class="sxs-lookup"><span data-stu-id="591c8-179">marzo abr.</span></span> <span data-ttu-id="591c8-180">Mayo Jun.</span><span class="sxs-lookup"><span data-stu-id="591c8-180">mayo jun.</span></span> <span data-ttu-id="591c8-181">luglio.</span><span class="sxs-lookup"><span data-stu-id="591c8-181">jul.</span></span> <span data-ttu-id="591c8-182">agosto Sept/set.</span><span class="sxs-lookup"><span data-stu-id="591c8-182">agosto sept./set.</span></span> <span data-ttu-id="591c8-183">personalizzazione.</span><span class="sxs-lookup"><span data-stu-id="591c8-183">oct.</span></span> <span data-ttu-id="591c8-184">novembre.</span><span class="sxs-lookup"><span data-stu-id="591c8-184">nov.</span></span> <span data-ttu-id="591c8-185">dic.</span><span class="sxs-lookup"><span data-stu-id="591c8-185">dic.</span></span>
    
## <a name="funceudate1-deprecated"></a><span data-ttu-id="591c8-186">Func_eu_date1 (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="591c8-186">Func_eu_date1 (deprecated)</span></span>

> [!NOTE]
> <span data-ttu-id="591c8-187">Questa funzione è obsoleta perché supporta solo i nomi dei mesi portoghesi, che ora sono inclusi nella `Func_eu_date` funzione precedente.</span><span class="sxs-lookup"><span data-stu-id="591c8-187">This function is deprecated because it supports only Portuguese month names, which are now included in the  `Func_eu_date` function above.</span></span> 
  
<span data-ttu-id="591c8-188">Questa funzione consente di cercare una data nel formato comunemente utilizzato in portoghese.</span><span class="sxs-lookup"><span data-stu-id="591c8-188">This function looks for a date in the format commonly used in Portuguese.</span></span> <span data-ttu-id="591c8-189">Il formato di questa funzione è lo stesso che `Func_eu_date`differisce solo nella lingua utilizzata.</span><span class="sxs-lookup"><span data-stu-id="591c8-189">The format for this function is the same as  `Func_eu_date`, differing only in the language used.</span></span>
  
<span data-ttu-id="591c8-190">Esempi:</span><span class="sxs-lookup"><span data-stu-id="591c8-190">Examples:</span></span>
  
- <span data-ttu-id="591c8-191">2 (2016).</span><span class="sxs-lookup"><span data-stu-id="591c8-191">2 Dez 2016</span></span>
    
- <span data-ttu-id="591c8-192">02 (2016).</span><span class="sxs-lookup"><span data-stu-id="591c8-192">02 dez 2016</span></span>
    
- <span data-ttu-id="591c8-193">2 con il 16</span><span class="sxs-lookup"><span data-stu-id="591c8-193">2 Dez 16</span></span>
    
- <span data-ttu-id="591c8-194">2/12/2016</span><span class="sxs-lookup"><span data-stu-id="591c8-194">2/12/2016</span></span>
    
- <span data-ttu-id="591c8-195">02/12/16</span><span class="sxs-lookup"><span data-stu-id="591c8-195">02/12/16</span></span>
    
- <span data-ttu-id="591c8-196">2-------2016</span><span class="sxs-lookup"><span data-stu-id="591c8-196">2-Dez-2016</span></span>
    
- <span data-ttu-id="591c8-197">2-12-16</span><span class="sxs-lookup"><span data-stu-id="591c8-197">2-12-16</span></span>
    
<span data-ttu-id="591c8-198">Nomi dei mesi accettati:</span><span class="sxs-lookup"><span data-stu-id="591c8-198">Accepted month names:</span></span>
  
- <span data-ttu-id="591c8-199">Portoghese</span><span class="sxs-lookup"><span data-stu-id="591c8-199">Portuguese</span></span>
    
  - <span data-ttu-id="591c8-200">janeiro, fevereiro, março, marco, abril, maio, junho, julho, agosto, setembro, outubro, novembro, dezembro</span><span class="sxs-lookup"><span data-stu-id="591c8-200">janeiro, fevereiro, março, marco, abril, maio, junho, julho, agosto, setembro, outubro, novembro, dezembro</span></span>
    
  - <span data-ttu-id="591c8-201">Jan FEV Mar ABR mai Jun Jul ago set out nov dic</span><span class="sxs-lookup"><span data-stu-id="591c8-201">jan fev mar abr mai jun jul ago set out nov dez</span></span>
    
## <a name="funceudate2-deprecated"></a><span data-ttu-id="591c8-202">Func_eu_date2 (obsoleto)</span><span class="sxs-lookup"><span data-stu-id="591c8-202">Func_eu_date2 (deprecated)</span></span>

> [!NOTE]
> <span data-ttu-id="591c8-203">Questa funzione è obsoleta perché supporta solo i nomi dei mesi olandesi, che ora sono inclusi `Func_eu_date` nella funzione precedente.</span><span class="sxs-lookup"><span data-stu-id="591c8-203">This function is deprecated because it supports only Dutch month names, which are now included in the  `Func_eu_date` function above.</span></span> 
  
<span data-ttu-id="591c8-204">Questa funzione consente di cercare una data nel formato comunemente utilizzato in olandese.</span><span class="sxs-lookup"><span data-stu-id="591c8-204">This function looks for a date in the format commonly used in Dutch.</span></span> <span data-ttu-id="591c8-205">Il formato di questa funzione è lo stesso che `Func_eu_date`differisce solo nella lingua utilizzata.</span><span class="sxs-lookup"><span data-stu-id="591c8-205">The format for this function is the same as  `Func_eu_date`, differing only in the language used.</span></span>
  
<span data-ttu-id="591c8-206">Esempi:</span><span class="sxs-lookup"><span data-stu-id="591c8-206">Examples:</span></span>
  
- <span data-ttu-id="591c8-207">2 Mei 2016</span><span class="sxs-lookup"><span data-stu-id="591c8-207">2 Mei 2016</span></span>
    
- <span data-ttu-id="591c8-208">02 Mei 2016</span><span class="sxs-lookup"><span data-stu-id="591c8-208">02 mei 2016</span></span>
    
- <span data-ttu-id="591c8-209">2 Mei 16</span><span class="sxs-lookup"><span data-stu-id="591c8-209">2 Mei 16</span></span>
    
- <span data-ttu-id="591c8-210">2/12/2016</span><span class="sxs-lookup"><span data-stu-id="591c8-210">2/12/2016</span></span>
    
- <span data-ttu-id="591c8-211">02/12/16</span><span class="sxs-lookup"><span data-stu-id="591c8-211">02/12/16</span></span>
    
- <span data-ttu-id="591c8-212">2-Mei-2016</span><span class="sxs-lookup"><span data-stu-id="591c8-212">2-Mei-2016</span></span>
    
- <span data-ttu-id="591c8-213">2-12-16</span><span class="sxs-lookup"><span data-stu-id="591c8-213">2-12-16</span></span>
    
<span data-ttu-id="591c8-214">Nomi dei mesi accettati:</span><span class="sxs-lookup"><span data-stu-id="591c8-214">Accepted month names:</span></span>
  
- <span data-ttu-id="591c8-215">Olandese</span><span class="sxs-lookup"><span data-stu-id="591c8-215">Dutch</span></span>
    
  - <span data-ttu-id="591c8-216">januari, februari, maart, April, mei, juni, juli, augustus, September, ocktober, October, November, December</span><span class="sxs-lookup"><span data-stu-id="591c8-216">januari, februari, maart, April, mei, juni, juli, augustus, September, ocktober, October, November, December</span></span>
    
  - <span data-ttu-id="591c8-217">Jan Feb maart apr Mei giu lug Aug Sep set ott Okt Nov Dec</span><span class="sxs-lookup"><span data-stu-id="591c8-217">jan feb maart apr mei jun jul aug sep sept oct okt nov dec</span></span>
    
## <a name="funcexpirationdate"></a><span data-ttu-id="591c8-218">Func_expiration_date</span><span class="sxs-lookup"><span data-stu-id="591c8-218">Func_expiration_date</span></span>

<span data-ttu-id="591c8-219">Questa funzione consente di cercare una data nei formati comunemente utilizzati da carte di credito e di debito, sostituendo i giorni con i mesi.</span><span class="sxs-lookup"><span data-stu-id="591c8-219">This function looks for a date in the formats commonly used by credit and debit cards, which exclude days in favor of months.</span></span> <span data-ttu-id="591c8-220">Questa funzione corrisponderà alle date nel formato "month/year", "month-year", "[Month Name] Year" e "[month abbreviation] Year".</span><span class="sxs-lookup"><span data-stu-id="591c8-220">This function will match dates in format of "month/year", "month-year", "[month name] year", and "[month abbreviation] year".</span></span> <span data-ttu-id="591c8-221">I nomi o le iniziali dei mesi non fanno distinzione tra maiuscole e minuscole.</span><span class="sxs-lookup"><span data-stu-id="591c8-221">The names or abbreviations of months are not case sensitive.</span></span>
  
<span data-ttu-id="591c8-222">Esempi:</span><span class="sxs-lookup"><span data-stu-id="591c8-222">Examples:</span></span>
  
- <span data-ttu-id="591c8-223">MM/AA -- ad esempio, 01/11 o 1/11</span><span class="sxs-lookup"><span data-stu-id="591c8-223">MM/YY -- for example, 01/11 or 1/11</span></span>
    
- <span data-ttu-id="591c8-224">MM/AAAA -- ad esempio, 01/2011 o 1/2011</span><span class="sxs-lookup"><span data-stu-id="591c8-224">MM/YYYY -- for example, 01/2011 or 1/2011</span></span>
    
- <span data-ttu-id="591c8-225">MM-AA -- ad esempio, 01-22 o 1-11</span><span class="sxs-lookup"><span data-stu-id="591c8-225">MM-YY -- for example, 01-22 or 1-11</span></span>
    
- <span data-ttu-id="591c8-226">MM-AAAA-- ad esempio, 01-2000 o 1-2000</span><span class="sxs-lookup"><span data-stu-id="591c8-226">MM-YYYY -- for example, 01-2000 or 1-2000</span></span>
    
<span data-ttu-id="591c8-227">I formati seguenti supportano AA o AAAA:</span><span class="sxs-lookup"><span data-stu-id="591c8-227">The following formats support YY or YYYY:</span></span>
  
- <span data-ttu-id="591c8-228">Mese-AAAA -- ad esempio, .Gen-2010 o gennaio-2010 o Gen-10 o gennaio-10</span><span class="sxs-lookup"><span data-stu-id="591c8-228">Month-YYYY -- for example, .Jan-2010 or january-2010 or Jan-10 or january-10</span></span>
    
- <span data-ttu-id="591c8-229">Mese AAAA -- ad esempio, "gennaio 2010" o "Gen 2010" o" gennaio 10" o "Gen 10"</span><span class="sxs-lookup"><span data-stu-id="591c8-229">Month YYYY -- for example, 'january 2010' or 'Jan 2010' or 'january 10' or 'Jan 10'</span></span>
    
- <span data-ttu-id="591c8-230">MeseAAAA -- ad esempio, "gennaio2010" o "Gen2010" o "gennaio10" o "Gen10"</span><span class="sxs-lookup"><span data-stu-id="591c8-230">MonthYYYY -- for example, 'january2010' or 'Jan2010' or 'january10' or 'Jan10'</span></span>
    
- <span data-ttu-id="591c8-231">Mese/AAAA--ad esempio, "gennaio/2010" o "gen/2010" o "gennaio/10" o "gen/10"</span><span class="sxs-lookup"><span data-stu-id="591c8-231">Month/YYYY -- for example, 'january/2010' or 'Jan/2010' or 'january/10' or 'Jan/10'</span></span>
    
<span data-ttu-id="591c8-232">Nomi dei mesi accettati:</span><span class="sxs-lookup"><span data-stu-id="591c8-232">Accepted month names:</span></span>
  
- <span data-ttu-id="591c8-233">Inglese</span><span class="sxs-lookup"><span data-stu-id="591c8-233">English</span></span>
    
  - <span data-ttu-id="591c8-234">Gennaio, febbraio, marzo, aprile, maggio, giugno, luglio, agosto, settembre, ottobre, novembre, dicembre</span><span class="sxs-lookup"><span data-stu-id="591c8-234">January, February, march, April, may, June, July, August, September, October, November, December</span></span>
    
  - <span data-ttu-id="591c8-235">Gen feb mar apr maggio giugno luglio Aug settembre Ott Nov Dec</span><span class="sxs-lookup"><span data-stu-id="591c8-235">Jan Feb Mar Apr May June July Aug Sept Oct Nov Dec</span></span>
    
## <a name="funcusaddress"></a><span data-ttu-id="591c8-236">Func_us_address</span><span class="sxs-lookup"><span data-stu-id="591c8-236">Func_us_address</span></span>

<span data-ttu-id="591c8-p113">Questa funzione cerca il nome di uno stato membro degli Stati Uniti o un'abbreviazione postale seguita da un CAP valido, esattamente come per gli indirizzi postali. Il CAP deve essere uno dei codici di avviamento postale corretti associati al nome o all'abbreviazione dello stato membro degli Stati Uniti. Il nome dello stato membro degli Stati Uniti e il CAP non possono essere separati da segni di punteggiatura o lettere.</span><span class="sxs-lookup"><span data-stu-id="591c8-p113">This function looks for a U.S. state name or postal abbreviation followed by a valid zip code, just as they are used in postal addresses. The zip code must be one of the correct zip codes associated with the U.S. state name or abbreviation. The U.S. state name and zip code cannot be separated by punctuation or letters.</span></span>
  
<span data-ttu-id="591c8-240">Esempi:</span><span class="sxs-lookup"><span data-stu-id="591c8-240">Examples:</span></span>
  
- <span data-ttu-id="591c8-241">Washington 98052</span><span class="sxs-lookup"><span data-stu-id="591c8-241">Washington 98052</span></span>
    
- <span data-ttu-id="591c8-242">Washington 98052-9998</span><span class="sxs-lookup"><span data-stu-id="591c8-242">Washington 98052-9998</span></span>
    
- <span data-ttu-id="591c8-243">WA 98052</span><span class="sxs-lookup"><span data-stu-id="591c8-243">WA 98052</span></span>
    
- <span data-ttu-id="591c8-244">WA 98052-9998</span><span class="sxs-lookup"><span data-stu-id="591c8-244">WA 98052-9998</span></span>
    

