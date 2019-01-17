---
title: Come viene identificato il contenuto per i consigli sulla governance dei dati
ms.author: brendonb
author: stephow-MSFT
manager: laurawi
ms.date: 1/15/2019
ms.audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Priority
search.appverid:
- MOE150
- MET150
ROBOTS: NOINDEX, NOFOLLOW
description: Il Centro sicurezza e conformità di Office 365 fornisce consigli per la governance dei dati in base alla configurazione corrente dell'organizzazione e consente di impostare le opzioni necessarie con pochi clic. Alcuni di questi consigli rilevano specifici contenuti nell'organizzazione e propongono le azioni consigliate per gestirli. Ad esempio, un consiglio potrebbe rilevare elementi che includono contenuti di importanza strategica, come informazioni sul privilegio avvocato-cliente o su un accordo di riservatezza, e quindi consentire l'applicazione automatica di un'etichetta di conservazione a tali elementi per assicurare che vengano opportunamente classificati e conservati. Questo argomento fornisce un elenco dei consigli sulla governance dei dati che possono essere visualizzati e descrive il contenuto che viene rilevato per attivare ciascuno di essi.
ms.openlocfilehash: a3f803105ea5c2626c8c2a26ad898df5f45af2f0
ms.sourcegitcommit: c7737903ff2e1d047682ee61f7ac21b0bdd1c6fd
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/16/2019
ms.locfileid: "28263944"
---
# <a name="how-content-is-identified-for-data-governance-recommendations"></a><span data-ttu-id="325a5-106">Come viene identificato il contenuto per i consigli sulla governance dei dati</span><span class="sxs-lookup"><span data-stu-id="325a5-106">How content is identified for data-governance recommendations</span></span>

<span data-ttu-id="325a5-p102">Il Centro sicurezza e conformità di Office 365 fornisce consigli per la governance dei dati in base alla configurazione corrente dell'organizzazione e consente di impostare le opzioni necessarie con pochi clic. Alcuni di questi consigli rilevano specifici contenuti nell'organizzazione e propongono le azioni consigliate per gestirli. Ad esempio, un consiglio potrebbe rilevare elementi che includono contenuti di importanza strategica, come informazioni sul privilegio avvocato-cliente o su un accordo di riservatezza, e quindi consentire l'applicazione automatica di un'etichetta di conservazione a tali elementi per assicurare che vengano opportunamente classificati e conservati.</span><span class="sxs-lookup"><span data-stu-id="325a5-p102">The Office 365 Security & Compliance Center provides recommendations for data governance based on your org's current setup and lets you set things up in a couple clicks. Some of these recommendations detect specific content in your organization and then provide recommended steps for managing that content. For example, a recommendation might detect items that contain business-critical content (such as attorney-client privilege or NDA info), and then let you automatically apply a retention label to those items to ensure that they’re classified and retained as needed.</span></span>

<span data-ttu-id="325a5-110">Questo argomento fornisce un elenco dei consigli sulla governance dei dati che possono essere visualizzati e descrive il contenuto che viene rilevato per attivare ciascuno di essi.</span><span class="sxs-lookup"><span data-stu-id="325a5-110">This topic lists the data-governance recommendations you might see and describes what content is detected to trigger each one.</span></span>

## <a name="clean-up-voicemail"></a><span data-ttu-id="325a5-111">Pulisci la segreteria telefonica</span><span class="sxs-lookup"><span data-stu-id="325a5-111">Clean up voicemail</span></span>

<span data-ttu-id="325a5-p103">Questo consiglio viene visualizzato quando nelle cassette postali degli utenti vengono rilevati messaggi di posta elettronica identificati come messaggi di tipo ‘postavocale’. Per saperne di più, vedere l'argomento relativo alle [proprietà dei messaggi in Exchange](https://docs.microsoft.com/en-us/exchange/policy-and-compliance/ediscovery/message-properties-and-search-operators?view=exchserver-2019#searchable-properties-in-exchange).</span><span class="sxs-lookup"><span data-stu-id="325a5-p103">This recommendation appears when email messages identified as the message type ‘voicemail’ are detected in users’ mailboxes. Learn more about [message properties in Exchange](https://docs.microsoft.com/en-us/exchange/policy-and-compliance/ediscovery/message-properties-and-search-operators?view=exchserver-2019#searchable-properties-in-exchange).</span></span>

## <a name="label-attorney-client-privilege-content"></a><span data-ttu-id="325a5-114">Applica etichetta ai contenuti coperti da privilegio avvocato-cliente</span><span class="sxs-lookup"><span data-stu-id="325a5-114">Label attorney-client privilege content</span></span> 

<span data-ttu-id="325a5-115">Questo consiglio viene visualizzato quando è soddisfatto uno dei criteri seguenti.</span><span class="sxs-lookup"><span data-stu-id="325a5-115">This recommendation appears when either of the following criteria are met.</span></span>

- <span data-ttu-id="325a5-116">Nel corpo del messaggio di posta elettronica viene rilevata una qualsiasi combinazione di queste parole chiave:</span><span class="sxs-lookup"><span data-stu-id="325a5-116">Any of combination of these keywords is detected in the body of an email message:</span></span>
    - <span data-ttu-id="325a5-117">PAC</span><span class="sxs-lookup"><span data-stu-id="325a5-117">ACP</span></span>
    - <span data-ttu-id="325a5-118">Privilegio avvocato cliente</span><span class="sxs-lookup"><span data-stu-id="325a5-118">Attorney Client Privilege</span></span>
    - <span data-ttu-id="325a5-119">Privilegio avvocato-cliente</span><span class="sxs-lookup"><span data-stu-id="325a5-119">Attorney-Client Privilege</span></span>
    - <span data-ttu-id="325a5-120">Coperto dal privilegio avvocato-cliente</span><span class="sxs-lookup"><span data-stu-id="325a5-120">Attorney-Client Privileged</span></span>

- <span data-ttu-id="325a5-121">Nei file di SharePoint o OneDrive viene rilevata una qualsiasi combinazione di queste parole chiave:</span><span class="sxs-lookup"><span data-stu-id="325a5-121">Any combination of these keywords are detected in SharePoint or OneDrive files:</span></span>
    - <span data-ttu-id="325a5-122">PAC</span><span class="sxs-lookup"><span data-stu-id="325a5-122">ACP</span></span>
    - <span data-ttu-id="325a5-123">Privilegio avvocato-cliente\*</span><span class="sxs-lookup"><span data-stu-id="325a5-123">Attorney Client Privilege\*</span></span>
    - <span data-ttu-id="325a5-124">Privilegio AC</span><span class="sxs-lookup"><span data-stu-id="325a5-124">AC Privilege</span></span>

## <a name="retain-audio-files"></a><span data-ttu-id="325a5-125">Conserva file audio</span><span class="sxs-lookup"><span data-stu-id="325a5-125">Retain audio files</span></span>

<span data-ttu-id="325a5-126">Questo consiglio viene visualizzato quando viene rilevato uno qualsiasi dei seguenti tipi di file in SharePoint o OneDrive.</span><span class="sxs-lookup"><span data-stu-id="325a5-126">This recommendation appears when any of the following file types are detected in SharePoint or OneDrive.</span></span>

- <span data-ttu-id="325a5-127">.MP3</span><span class="sxs-lookup"><span data-stu-id="325a5-127">MP3</span></span>
- <span data-ttu-id="325a5-128">.WMA</span><span class="sxs-lookup"><span data-stu-id="325a5-128">WMA</span></span>
- <span data-ttu-id="325a5-129">.WAV</span><span class="sxs-lookup"><span data-stu-id="325a5-129">WAV</span></span>
- <span data-ttu-id="325a5-130">.RA</span><span class="sxs-lookup"><span data-stu-id="325a5-130">.RA</span></span>
- <span data-ttu-id="325a5-131">.RAM</span><span class="sxs-lookup"><span data-stu-id="325a5-131">RAM</span></span>
- <span data-ttu-id="325a5-132">.RM</span><span class="sxs-lookup"><span data-stu-id="325a5-132">rm</span></span>
- <span data-ttu-id="325a5-133">.MID</span><span class="sxs-lookup"><span data-stu-id="325a5-133">.MID</span></span>
- <span data-ttu-id="325a5-134">.OGG</span><span class="sxs-lookup"><span data-stu-id="325a5-134">.OGG</span></span>
- <span data-ttu-id="325a5-135">.AIFF</span><span class="sxs-lookup"><span data-stu-id="325a5-135">.AIFF</span></span>
- <span data-ttu-id="325a5-136">.PCM</span><span class="sxs-lookup"><span data-stu-id="325a5-136">.PCM</span></span>
- <span data-ttu-id="325a5-137">.AAC</span><span class="sxs-lookup"><span data-stu-id="325a5-137">.AAC</span></span>
- <span data-ttu-id="325a5-138">.FLAC</span><span class="sxs-lookup"><span data-stu-id="325a5-138">.FLAC</span></span>
- <span data-ttu-id="325a5-139">.ALAC</span><span class="sxs-lookup"><span data-stu-id="325a5-139">.ALAC</span></span>

## <a name="retain-cad-files"></a><span data-ttu-id="325a5-140">Conserva file CAD</span><span class="sxs-lookup"><span data-stu-id="325a5-140">Retain CAD files</span></span>

<span data-ttu-id="325a5-141">Questo consiglio viene visualizzato quando viene rilevato uno qualsiasi dei seguenti tipi di file in SharePoint o OneDrive.</span><span class="sxs-lookup"><span data-stu-id="325a5-141">This recommendation appears when any of the following file types are detected in SharePoint or OneDrive.</span></span>

- <span data-ttu-id="325a5-142">.3DXML</span><span class="sxs-lookup"><span data-stu-id="325a5-142">.3DXML</span></span>
- <span data-ttu-id="325a5-143">.ACIS</span><span class="sxs-lookup"><span data-stu-id="325a5-143">.ACIS</span></span>
- <span data-ttu-id="325a5-144">.ARC</span><span class="sxs-lookup"><span data-stu-id="325a5-144">ARC
</span></span>
- <span data-ttu-id="325a5-145">.ASM</span><span class="sxs-lookup"><span data-stu-id="325a5-145">asm</span></span>
- <span data-ttu-id="325a5-146">.CAT\*</span><span class="sxs-lookup"><span data-stu-id="325a5-146">cat\*</span></span>
- <span data-ttu-id="325a5-147">.CGR</span><span class="sxs-lookup"><span data-stu-id="325a5-147">.CGR</span></span>
- <span data-ttu-id="325a5-148">.DW\*</span><span class="sxs-lookup"><span data-stu-id="325a5-148">DW</span></span>
- <span data-ttu-id="325a5-149">.DX\*</span><span class="sxs-lookup"><span data-stu-id="325a5-149">.DX\*</span></span>
- <span data-ttu-id="325a5-150">.EDRW</span><span class="sxs-lookup"><span data-stu-id="325a5-150">.EDRW</span></span>
- <span data-ttu-id="325a5-151">.IAM</span><span class="sxs-lookup"><span data-stu-id="325a5-151">.IAM</span></span>
- <span data-ttu-id="325a5-152">.IGES</span><span class="sxs-lookup"><span data-stu-id="325a5-152">.IGES</span></span>
- <span data-ttu-id="325a5-153">.IGS</span><span class="sxs-lookup"><span data-stu-id="325a5-153">.IGS</span></span>
- <span data-ttu-id="325a5-154">.IPT</span><span class="sxs-lookup"><span data-stu-id="325a5-154">.IPT</span></span>
- <span data-ttu-id="325a5-155">.JT</span><span class="sxs-lookup"><span data-stu-id="325a5-155">.JT</span></span>
- <span data-ttu-id="325a5-156">.MF1</span><span class="sxs-lookup"><span data-stu-id="325a5-156">.MF1</span></span>
- <span data-ttu-id="325a5-157">.NEU</span><span class="sxs-lookup"><span data-stu-id="325a5-157">.NEU</span></span>
- <span data-ttu-id="325a5-158">.PAR</span><span class="sxs-lookup"><span data-stu-id="325a5-158">.PAR</span></span>
- <span data-ttu-id="325a5-159">.PKG</span><span class="sxs-lookup"><span data-stu-id="325a5-159">.PKG</span></span>
- <span data-ttu-id="325a5-160">.PRC</span><span class="sxs-lookup"><span data-stu-id="325a5-160">PRC
</span></span>
- <span data-ttu-id="325a5-161">.PRT</span><span class="sxs-lookup"><span data-stu-id="325a5-161">.PRT</span></span>
- <span data-ttu-id="325a5-162">.PSM</span><span class="sxs-lookup"><span data-stu-id="325a5-162">.PSM</span></span>
- <span data-ttu-id="325a5-163">.PWD</span><span class="sxs-lookup"><span data-stu-id="325a5-163">.PWD</span></span>
- <span data-ttu-id="325a5-164">.SLD\*</span><span class="sxs-lookup"><span data-stu-id="325a5-164">.SLD\*</span></span>
- <span data-ttu-id="325a5-165">.STEP</span><span class="sxs-lookup"><span data-stu-id="325a5-165">Step</span></span>
- <span data-ttu-id="325a5-166">.STL</span><span class="sxs-lookup"><span data-stu-id="325a5-166">.STL</span></span>
- <span data-ttu-id="325a5-167">.STP</span><span class="sxs-lookup"><span data-stu-id="325a5-167">.STP</span></span>
- <span data-ttu-id="325a5-168">.U3D</span><span class="sxs-lookup"><span data-stu-id="325a5-168">.U3D</span></span>
- <span data-ttu-id="325a5-169">.UNV</span><span class="sxs-lookup"><span data-stu-id="325a5-169">.UNV</span></span>
- <span data-ttu-id="325a5-170">.VRML</span><span class="sxs-lookup"><span data-stu-id="325a5-170">.VRML</span></span>
- <span data-ttu-id="325a5-171">.WRL</span><span class="sxs-lookup"><span data-stu-id="325a5-171">.WRL</span></span>
- <span data-ttu-id="325a5-172">.X_\*</span><span class="sxs-lookup"><span data-stu-id="325a5-172">X</span></span>
- <span data-ttu-id="325a5-173">.XAS</span><span class="sxs-lookup"><span data-stu-id="325a5-173">.XAS</span></span>
- <span data-ttu-id="325a5-174">.XMT\*</span><span class="sxs-lookup"><span data-stu-id="325a5-174">.XMT\*</span></span>
- <span data-ttu-id="325a5-175">.XPR</span><span class="sxs-lookup"><span data-stu-id="325a5-175">.XPR</span></span>

## <a name="retain-image-files"></a><span data-ttu-id="325a5-176">Conserva file di immagine</span><span class="sxs-lookup"><span data-stu-id="325a5-176">Retain image files</span></span>

<span data-ttu-id="325a5-177">Questo consiglio viene visualizzato quando viene rilevato uno qualsiasi dei seguenti tipi di file in SharePoint o OneDrive.</span><span class="sxs-lookup"><span data-stu-id="325a5-177">This recommendation appears when any of the following file types are detected in SharePoint or OneDrive.</span></span>

- <span data-ttu-id="325a5-178">.JPEG</span><span class="sxs-lookup"><span data-stu-id="325a5-178">JPEG</span></span>
- <span data-ttu-id="325a5-179">.GIF</span><span class="sxs-lookup"><span data-stu-id="325a5-179">GIF</span></span>
- <span data-ttu-id="325a5-180">.TIF\*</span><span class="sxs-lookup"><span data-stu-id="325a5-180">tif</span></span>
- <span data-ttu-id="325a5-181">.BMP</span><span class="sxs-lookup"><span data-stu-id="325a5-181">.bmp</span></span>
- <span data-ttu-id="325a5-182">.PNG</span><span class="sxs-lookup"><span data-stu-id="325a5-182">PNG</span></span>
- <span data-ttu-id="325a5-183">.RAW</span><span class="sxs-lookup"><span data-stu-id="325a5-183">.RAW</span></span>
- <span data-ttu-id="325a5-184">.PSD</span><span class="sxs-lookup"><span data-stu-id="325a5-184">.PSD</span></span>
- <span data-ttu-id="325a5-185">.PSP</span><span class="sxs-lookup"><span data-stu-id="325a5-185">PSP
</span></span>
- <span data-ttu-id="325a5-186">.JPG</span><span class="sxs-lookup"><span data-stu-id="325a5-186">.jpg</span></span>
- <span data-ttu-id="325a5-187">.EXIF</span><span class="sxs-lookup"><span data-stu-id="325a5-187">.EXIF</span></span>
- <span data-ttu-id="325a5-188">.PPM</span><span class="sxs-lookup"><span data-stu-id="325a5-188">PPM capabilities</span></span>
- <span data-ttu-id="325a5-189">.PGM</span><span class="sxs-lookup"><span data-stu-id="325a5-189">.PGM</span></span>
- <span data-ttu-id="325a5-190">.PBM</span><span class="sxs-lookup"><span data-stu-id="325a5-190">.PBM</span></span>
- <span data-ttu-id="325a5-191">.PNM</span><span class="sxs-lookup"><span data-stu-id="325a5-191">.PNM</span></span>
- <span data-ttu-id="325a5-192">.WEBP</span><span class="sxs-lookup"><span data-stu-id="325a5-192">.WEBP</span></span>

## <a name="retain-nda-content"></a><span data-ttu-id="325a5-193">Conserva i contenuti con accordo di riservatezza</span><span class="sxs-lookup"><span data-stu-id="325a5-193">Retain NDA content</span></span> 

<span data-ttu-id="325a5-194">Questo consiglio viene visualizzato quando è soddisfatto uno dei criteri seguenti.</span><span class="sxs-lookup"><span data-stu-id="325a5-194">This recommendation appears when either of the following criteria are met.</span></span>

- <span data-ttu-id="325a5-195">Nel corpo del messaggio di posta elettronica viene rilevata una qualsiasi combinazione di queste parole chiave:</span><span class="sxs-lookup"><span data-stu-id="325a5-195">Any of combination of these keywords is detected in the body of an email message:</span></span>
    - <span data-ttu-id="325a5-196">Accordo di riservatezza</span><span class="sxs-lookup"><span data-stu-id="325a5-196">NDA</span></span>
    - <span data-ttu-id="325a5-197">"Accordo di riservatezza"</span><span class="sxs-lookup"><span data-stu-id="325a5-197">“Non-Disclosure Agreement”</span></span>
    - <span data-ttu-id="325a5-198">"Accordo riservatezza"</span><span class="sxs-lookup"><span data-stu-id="325a5-198">“Non Disclosure Agreement”</span></span>

- <span data-ttu-id="325a5-199">Nei file PDF o DOC in SharePoint o OneDrive viene rilevata una qualsiasi combinazione di queste parole chiave:</span><span class="sxs-lookup"><span data-stu-id="325a5-199">Any combination of these keywords are detected in .PDF or .DOC files in SharePoint or OneDrive:</span></span>
    - <span data-ttu-id="325a5-200">Accordo di riservatezza</span><span class="sxs-lookup"><span data-stu-id="325a5-200">NDA</span></span>
    - <span data-ttu-id="325a5-201">Accordo riservatezza</span><span class="sxs-lookup"><span data-stu-id="325a5-201">Non Disclosure Agreement</span></span>

## <a name="retain-software-development-files"></a><span data-ttu-id="325a5-202">Conserva i file di sviluppo software</span><span class="sxs-lookup"><span data-stu-id="325a5-202">Retain software development files</span></span>

<span data-ttu-id="325a5-203">Questo consiglio viene visualizzato quando viene rilevato uno qualsiasi dei seguenti tipi di file in SharePoint o OneDrive.</span><span class="sxs-lookup"><span data-stu-id="325a5-203">This recommendation appears when any of the following file types are detected in SharePoint or OneDrive.</span></span>

- <span data-ttu-id="325a5-204">.ASAX</span><span class="sxs-lookup"><span data-stu-id="325a5-204">.ASAX</span></span>
- <span data-ttu-id="325a5-205">.ASM</span><span class="sxs-lookup"><span data-stu-id="325a5-205">asm</span></span>
- <span data-ttu-id="325a5-206">.ASP\*</span><span class="sxs-lookup"><span data-stu-id="325a5-206">asp</span></span>
- <span data-ttu-id="325a5-207">.BAT</span><span class="sxs-lookup"><span data-stu-id="325a5-207">bat</span></span>
- <span data-ttu-id="325a5-208">.CONFIG</span><span class="sxs-lookup"><span data-stu-id="325a5-208">.config</span></span>
- <span data-ttu-id="325a5-209">.CS</span><span class="sxs-lookup"><span data-stu-id="325a5-209">cs</span></span>
- <span data-ttu-id="325a5-210">.CSS</span><span class="sxs-lookup"><span data-stu-id="325a5-210">CSS</span></span>
- <span data-ttu-id="325a5-211">.DISCO</span><span class="sxs-lookup"><span data-stu-id="325a5-211">.DISCO</span></span>
- <span data-ttu-id="325a5-212">.HTM\*</span><span class="sxs-lookup"><span data-stu-id="325a5-212">htm</span></span>
- <span data-ttu-id="325a5-213">.INC</span><span class="sxs-lookup"><span data-stu-id="325a5-213">.INC</span></span>
- <span data-ttu-id="325a5-214">.JAD</span><span class="sxs-lookup"><span data-stu-id="325a5-214">.JAD</span></span>
- <span data-ttu-id="325a5-215">.JAVA</span><span class="sxs-lookup"><span data-stu-id="325a5-215">Java</span></span>
- <span data-ttu-id="325a5-216">.JS\*</span><span class="sxs-lookup"><span data-stu-id="325a5-216">.js</span></span>
- <span data-ttu-id="325a5-217">.LIB</span><span class="sxs-lookup"><span data-stu-id="325a5-217">.LIB</span></span>
- <span data-ttu-id="325a5-218">.O</span><span class="sxs-lookup"><span data-stu-id="325a5-218">O</span></span>
- <span data-ttu-id="325a5-219">.PHP</span><span class="sxs-lookup"><span data-stu-id="325a5-219">PHP</span></span>
- <span data-ttu-id="325a5-220">.RC</span><span class="sxs-lookup"><span data-stu-id="325a5-220">.RC</span></span>
- <span data-ttu-id="325a5-221">.RESX</span><span class="sxs-lookup"><span data-stu-id="325a5-221">\*.resx</span></span>
- <span data-ttu-id="325a5-222">.RPT</span><span class="sxs-lookup"><span data-stu-id="325a5-222">.RPT</span></span>
- <span data-ttu-id="325a5-223">.RSS</span><span class="sxs-lookup"><span data-stu-id="325a5-223">RSS</span></span>
- <span data-ttu-id="325a5-224">.SCPT</span><span class="sxs-lookup"><span data-stu-id="325a5-224">.SCPT</span></span>
- <span data-ttu-id="325a5-225">.SRC</span><span class="sxs-lookup"><span data-stu-id="325a5-225">.SRC</span></span>
- <span data-ttu-id="325a5-226">.VB\*</span><span class="sxs-lookup"><span data-stu-id="325a5-226">.vb</span></span>
- <span data-ttu-id="325a5-227">.WSF</span><span class="sxs-lookup"><span data-stu-id="325a5-227">.wsf</span></span>
- <span data-ttu-id="325a5-228">.XCODEPROJ</span><span class="sxs-lookup"><span data-stu-id="325a5-228">.XCODEPROJ</span></span>
- <span data-ttu-id="325a5-229">.XML</span><span class="sxs-lookup"><span data-stu-id="325a5-229">XML</span></span>
- <span data-ttu-id="325a5-230">.XSD</span><span class="sxs-lookup"><span data-stu-id="325a5-230">.XSD</span></span>
- <span data-ttu-id="325a5-231">.XSL\*</span><span class="sxs-lookup"><span data-stu-id="325a5-231">XSL</span></span>

## <a name="retain-video-files"></a><span data-ttu-id="325a5-232">Conserva i file video</span><span class="sxs-lookup"><span data-stu-id="325a5-232">Retain video files</span></span>

<span data-ttu-id="325a5-233">Questo consiglio viene visualizzato quando viene rilevato uno qualsiasi dei seguenti tipi di file in SharePoint o OneDrive.</span><span class="sxs-lookup"><span data-stu-id="325a5-233">This recommendation appears when any of the following file types are detected in SharePoint or OneDrive.</span></span>

- <span data-ttu-id="325a5-234">.AVCHD</span><span class="sxs-lookup"><span data-stu-id="325a5-234">.AVCHD</span></span>
- <span data-ttu-id="325a5-235">.AVI</span><span class="sxs-lookup"><span data-stu-id="325a5-235">avi</span></span>
- <span data-ttu-id="325a5-236">.FLV</span><span class="sxs-lookup"><span data-stu-id="325a5-236">.FLV</span></span>
- <span data-ttu-id="325a5-237">.MOV</span><span class="sxs-lookup"><span data-stu-id="325a5-237">.MOV</span></span>
- <span data-ttu-id="325a5-238">.MP2V</span><span class="sxs-lookup"><span data-stu-id="325a5-238">.MP2V</span></span>
- <span data-ttu-id="325a5-239">.MP4</span><span class="sxs-lookup"><span data-stu-id="325a5-239">.MP4</span></span>
- <span data-ttu-id="325a5-240">.MP4V</span><span class="sxs-lookup"><span data-stu-id="325a5-240">.MP4V</span></span>
- <span data-ttu-id="325a5-241">.MPE</span><span class="sxs-lookup"><span data-stu-id="325a5-241">.MPE</span></span>
- <span data-ttu-id="325a5-242">.MPEG</span><span class="sxs-lookup"><span data-stu-id="325a5-242">MPEG</span></span>
- <span data-ttu-id="325a5-243">.MPEG1</span><span class="sxs-lookup"><span data-stu-id="325a5-243">.MPEG1</span></span>
- <span data-ttu-id="325a5-244">.MPEG2</span><span class="sxs-lookup"><span data-stu-id="325a5-244">.MPEG2</span></span>
- <span data-ttu-id="325a5-245">.MPEG4</span><span class="sxs-lookup"><span data-stu-id="325a5-245">.MPEG4</span></span>
- <span data-ttu-id="325a5-246">.MPG</span><span class="sxs-lookup"><span data-stu-id="325a5-246">.MPG</span></span>
- <span data-ttu-id="325a5-247">.MPG2</span><span class="sxs-lookup"><span data-stu-id="325a5-247">.MPG2</span></span>
- <span data-ttu-id="325a5-248">.MPG4</span><span class="sxs-lookup"><span data-stu-id="325a5-248">.MPG4</span></span>
- <span data-ttu-id="325a5-249">.WMV</span><span class="sxs-lookup"><span data-stu-id="325a5-249">.WMV</span></span>
- <span data-ttu-id="325a5-250">.XMV</span><span class="sxs-lookup"><span data-stu-id="325a5-250">.XMV</span></span>
