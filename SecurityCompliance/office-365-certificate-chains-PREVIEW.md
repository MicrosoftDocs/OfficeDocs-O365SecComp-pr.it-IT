---
title: Catena di certificati di Office 365
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 6/26/2018
ms.audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection: Ent_O365
ms.assetid: 0c03e6b3-e73f-4316-9e2b-bf4091ae96bb
description: Office 365 si avvale di un numero di provider di certificati differenti. Di seguito vengono descritti l'elenco completo dei certificati radice di Office 365 noti che i clienti possono verificarsi quando si accede a Office 365. Per informazioni sui certificati potrebbe essere necessario installare un'infrastruttura, vedere Plan for dei certificati SSL di terze parti per Office 365. Le seguenti informazioni sul certificato si applica a tutte le istanze di tutto il mondo e nazionali cloud di Office 365.
ms.openlocfilehash: 1dcc2dc38bb8e3239a3be3983791b0c60917dc5e
ms.sourcegitcommit: 13f40ff7c1799152bf45af2d8110f4f3235b770a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/12/2018
ms.locfileid: "25549757"
---
# <a name="office-365-certificate-chains"></a><span data-ttu-id="6a61a-106">Catena di certificati di Office 365</span><span class="sxs-lookup"><span data-stu-id="6a61a-106">Office 365 Certificate Chains</span></span>

<span data-ttu-id="6a61a-p102">Office 365 si avvale di un numero di provider di certificati differenti. Di seguito vengono descritti l'elenco completo dei certificati radice di Office 365 noti che i clienti possono verificarsi quando si accede a Office 365. Per informazioni sui certificati potrebbe essere necessario installare un'infrastruttura, vedere [pianificare i certificati SSL di terze parti per Office 365](https://support.office.com/article/b48cdf63-07e0-4cda-8c12-4871590f59ce). Le seguenti informazioni sul certificato si applica a tutte le istanze di tutto il mondo e nazionali cloud di Office 365.</span><span class="sxs-lookup"><span data-stu-id="6a61a-p102">Office 365 leverages a number of different certificate providers. The following describes the complete list of known Office 365 root certificates that customers may encounter when accessing Office 365. For information on the certificates you may need to install in your own infrastructure, see [Plan for third-party SSL certificates for Office 365](https://support.office.com/article/b48cdf63-07e0-4cda-8c12-4871590f59ce). The following certificate information applies to all worldwide and national cloud instances of Office 365.</span></span>
  

|<span data-ttu-id="6a61a-111">**Tipo di certificato**</span><span class="sxs-lookup"><span data-stu-id="6a61a-111">**Certificate type**</span></span>|<span data-ttu-id="6a61a-112">**Download P7b**</span><span class="sxs-lookup"><span data-stu-id="6a61a-112">**P7b download**</span></span>|<span data-ttu-id="6a61a-113">**Endpoint di revoche di certificati**</span><span class="sxs-lookup"><span data-stu-id="6a61a-113">**CRL Endpoints**</span></span>|<span data-ttu-id="6a61a-114">**Endpoint OCSP**</span><span class="sxs-lookup"><span data-stu-id="6a61a-114">**OCSP Endpoints**</span></span>|<span data-ttu-id="6a61a-115">**Endpoint AIA**</span><span class="sxs-lookup"><span data-stu-id="6a61a-115">**AIA Endpoints**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|[<span data-ttu-id="6a61a-116">Pubblicamente attendibili i certificati radice</span><span class="sxs-lookup"><span data-stu-id="6a61a-116">Publicly Trusted Root Certificates</span></span>](https://support.office.com/article/0c03e6b3-e73f-4316-9e2b-bf4091ae96bb#rootcerts) <br/> |[<span data-ttu-id="6a61a-117">Bundle di certificati radice di Office 365 (P7B)</span><span class="sxs-lookup"><span data-stu-id="6a61a-117">Office 365 Root Certificate Bundle (P7B)</span></span>](http://download.microsoft.com/download/A/5/A/A5AE01F3-D19B-4A11-9407-801263CEF72C/O365_Root_Certs_20170321.p7b) <br/> |<span data-ttu-id="6a61a-118">CRL.GlobalSign.NET</span><span class="sxs-lookup"><span data-stu-id="6a61a-118">crl.globalsign.net</span></span>  <br/> <span data-ttu-id="6a61a-119">www.d-trust.NET</span><span class="sxs-lookup"><span data-stu-id="6a61a-119">www.d-trust.net</span></span>  <br/> |<span data-ttu-id="6a61a-120">N/D</span><span class="sxs-lookup"><span data-stu-id="6a61a-120">N/A</span></span>  <br/> |<span data-ttu-id="6a61a-121">N/D</span><span class="sxs-lookup"><span data-stu-id="6a61a-121">N/A</span></span>  <br/> |
|[<span data-ttu-id="6a61a-122">Livello intermedi certificati pubblicamente attendibili</span><span class="sxs-lookup"><span data-stu-id="6a61a-122">Publicly Trusted Intermediate Certificates</span></span>](https://support.office.com/article/0c03e6b3-e73f-4316-9e2b-bf4091ae96bb#IntermediateCerts) <br/> |[<span data-ttu-id="6a61a-123">Office 365 certificato intermedio Bundle (P7B)</span><span class="sxs-lookup"><span data-stu-id="6a61a-123">Office 365 Intermediate Certificate Bundle (P7B)</span></span>](http://download.microsoft.com/download/4/D/5/4D5339A4-0A4A-46AB-AE52-B179DEDA4BEC/O365_Intermediate_Certs_20170321.p7b)  <br/> |<span data-ttu-id="6a61a-124">cdp1.Public trust.com</span><span class="sxs-lookup"><span data-stu-id="6a61a-124">cdp1.public-trust.com</span></span>  <br/> <span data-ttu-id="6a61a-125">CRL.cnnic.CN</span><span class="sxs-lookup"><span data-stu-id="6a61a-125">crl.cnnic.cn</span></span>  <br/> <span data-ttu-id="6a61a-126">CRL.Entrust.NET</span><span class="sxs-lookup"><span data-stu-id="6a61a-126">crl.entrust.net</span></span>  <br/> <span data-ttu-id="6a61a-127">CRL.GlobalSign.com</span><span class="sxs-lookup"><span data-stu-id="6a61a-127">crl.globalsign.com</span></span>  <br/> <span data-ttu-id="6a61a-128">CRL.GlobalSign.NET</span><span class="sxs-lookup"><span data-stu-id="6a61a-128">crl.globalsign.net</span></span>  <br/> <span data-ttu-id="6a61a-129">CRL.identrust.com</span><span class="sxs-lookup"><span data-stu-id="6a61a-129">crl.identrust.com</span></span>  <br/> <span data-ttu-id="6a61a-130">CRL.Thawte.com</span><span class="sxs-lookup"><span data-stu-id="6a61a-130">crl.thawte.com</span></span>  <br/> <span data-ttu-id="6a61a-131">crl3.DigiCert.com</span><span class="sxs-lookup"><span data-stu-id="6a61a-131">crl3.digicert.com</span></span>  <br/> <span data-ttu-id="6a61a-132">crl4.DigiCert.com</span><span class="sxs-lookup"><span data-stu-id="6a61a-132">crl4.digicert.com</span></span>  <br/> <span data-ttu-id="6a61a-133">s1.symcb.com</span><span class="sxs-lookup"><span data-stu-id="6a61a-133">s1.symcb.com</span></span>  <br/> <span data-ttu-id="6a61a-134">www.d-trust.NET</span><span class="sxs-lookup"><span data-stu-id="6a61a-134">www.d-trust.net</span></span>  <br/> |<span data-ttu-id="6a61a-135">isrg.trustid.OCSP.identrust.com</span><span class="sxs-lookup"><span data-stu-id="6a61a-135">isrg.trustid.ocsp.identrust.com</span></span>  <br/> <span data-ttu-id="6a61a-136">OCSP.DigiCert.com</span><span class="sxs-lookup"><span data-stu-id="6a61a-136">ocsp.digicert.com</span></span>  <br/> <span data-ttu-id="6a61a-137">OCSP.Entrust.NET</span><span class="sxs-lookup"><span data-stu-id="6a61a-137">ocsp.entrust.net</span></span>  <br/> <span data-ttu-id="6a61a-138">OCSP.GlobalSign.com</span><span class="sxs-lookup"><span data-stu-id="6a61a-138">ocsp.globalsign.com</span></span>  <br/> <span data-ttu-id="6a61a-139">OCSP.omniroot.com</span><span class="sxs-lookup"><span data-stu-id="6a61a-139">ocsp.omniroot.com</span></span>  <br/> <span data-ttu-id="6a61a-140">OCSP.startssl.com</span><span class="sxs-lookup"><span data-stu-id="6a61a-140">ocsp.startssl.com</span></span>  <br/> <span data-ttu-id="6a61a-141">OCSP.Thawte.com</span><span class="sxs-lookup"><span data-stu-id="6a61a-141">ocsp.thawte.com</span></span>  <br/> <span data-ttu-id="6a61a-142">ocsp2.GlobalSign.com</span><span class="sxs-lookup"><span data-stu-id="6a61a-142">ocsp2.globalsign.com</span></span>  <br/> <span data-ttu-id="6a61a-143">ocspcnnicroot.cnnic.CN</span><span class="sxs-lookup"><span data-stu-id="6a61a-143">ocspcnnicroot.cnnic.cn</span></span>  <br/> <span data-ttu-id="6a61a-144">radice-c3-ca2-2009.ocsp.d-trust.net</span><span class="sxs-lookup"><span data-stu-id="6a61a-144">root-c3-ca2-2009.ocsp.d-trust.net</span></span>  <br/> <span data-ttu-id="6a61a-145">Root-C3-CA2-EV-2009.OCSP.d-trust.NET</span><span class="sxs-lookup"><span data-stu-id="6a61a-145">root-c3-ca2-ev-2009.ocsp.d-trust.net</span></span>  <br/> <span data-ttu-id="6a61a-146">s2.symcb.com</span><span class="sxs-lookup"><span data-stu-id="6a61a-146">s2.symcb.com</span></span>  <br/> |<span data-ttu-id="6a61a-147">AIA.startssl.com</span><span class="sxs-lookup"><span data-stu-id="6a61a-147">aia.startssl.com</span></span>  <br/> <span data-ttu-id="6a61a-148">Apps.identrust.com</span><span class="sxs-lookup"><span data-stu-id="6a61a-148">apps.identrust.com</span></span>  <br/> <span data-ttu-id="6a61a-149">cacert.omniroot.com</span><span class="sxs-lookup"><span data-stu-id="6a61a-149">cacert.omniroot.com</span></span>  <br/> <span data-ttu-id="6a61a-150">www.cnnic.CN</span><span class="sxs-lookup"><span data-stu-id="6a61a-150">www.cnnic.cn</span></span>  <br/> |
   
<span data-ttu-id="6a61a-151">Espandere il nodo radice e intermedio nelle sezioni seguenti per visualizzare ulteriori informazioni sui provider di certificati.</span><span class="sxs-lookup"><span data-stu-id="6a61a-151">Expand the root and intermediate sections below to see additional details about the certificate providers.</span></span>
  
## <a name="office-365-root-certificate-details"></a><span data-ttu-id="6a61a-152">Dettagli del certificato radice di Office 365</span><span class="sxs-lookup"><span data-stu-id="6a61a-152">Office 365 Root Certificate Details</span></span>
<span data-ttu-id="6a61a-153"><a name="RootCerts"> </a></span><span class="sxs-lookup"><span data-stu-id="6a61a-153"></span></span>

 <span data-ttu-id="6a61a-154">**Baltimore CyberTrust Root**</span><span class="sxs-lookup"><span data-stu-id="6a61a-154">**Baltimore CyberTrust Root**</span></span>
  
<span data-ttu-id="6a61a-155">|:-----|</span><span class="sxs-lookup"><span data-stu-id="6a61a-155">|:-----|</span></span>
|<span data-ttu-id="6a61a-156">**Oggetto**</span><span class="sxs-lookup"><span data-stu-id="6a61a-156">**Subject**</span></span>|
|:-----|
|<span data-ttu-id="6a61a-157">**Numero di serie**</span><span class="sxs-lookup"><span data-stu-id="6a61a-157">**Serial Number**</span></span>|
|<span data-ttu-id="6a61a-158">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-158"></span></span>|
|<span data-ttu-id="6a61a-159">**Lunghezza chiave pubblica**</span><span class="sxs-lookup"><span data-stu-id="6a61a-159">**Public Key Length**</span></span>|
|<span data-ttu-id="6a61a-160">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-160"></span></span>|
|<span data-ttu-id="6a61a-161">**Algoritmo di firma**</span><span class="sxs-lookup"><span data-stu-id="6a61a-161">**Signature Algorithm**</span></span>|
|<span data-ttu-id="6a61a-162">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-162"></span></span>|
|<span data-ttu-id="6a61a-163">**Validità non prima**</span><span class="sxs-lookup"><span data-stu-id="6a61a-163">**Validity Not Before**</span></span>|
|<span data-ttu-id="6a61a-164">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-164"></span></span>|
|<span data-ttu-id="6a61a-165">**Validità non dopo**</span><span class="sxs-lookup"><span data-stu-id="6a61a-165">**Validity Not After**</span></span>|
|<span data-ttu-id="6a61a-166">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-166"></span></span>|
|<span data-ttu-id="6a61a-167">**Identificatore chiave del soggetto**</span><span class="sxs-lookup"><span data-stu-id="6a61a-167">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="6a61a-168">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-168"></span></span>|
|<span data-ttu-id="6a61a-169">**Identificazione personale (SHA-1)**</span><span class="sxs-lookup"><span data-stu-id="6a61a-169">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="6a61a-170">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-170"></span></span>|
|<span data-ttu-id="6a61a-171">**Identificazione personale (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="6a61a-171">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="6a61a-172">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-172"></span></span>|
|<span data-ttu-id="6a61a-173">**PIN (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="6a61a-173">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="6a61a-174">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-174"></span></span>|
   
 <span data-ttu-id="6a61a-175">**RADICE CNNIC**</span><span class="sxs-lookup"><span data-stu-id="6a61a-175">**CNNIC ROOT**</span></span>
  
||
|:-----|
|<span data-ttu-id="6a61a-176">**Oggetto**</span><span class="sxs-lookup"><span data-stu-id="6a61a-176">**Subject**</span></span>|
|<span data-ttu-id="6a61a-177">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-177"></span></span>|
|<span data-ttu-id="6a61a-178">**Numero di serie**</span><span class="sxs-lookup"><span data-stu-id="6a61a-178">**Serial Number**</span></span>|
|<span data-ttu-id="6a61a-179">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-179"></span></span>|
|<span data-ttu-id="6a61a-180">**Lunghezza chiave pubblica**</span><span class="sxs-lookup"><span data-stu-id="6a61a-180">**Public Key Length**</span></span>|
|<span data-ttu-id="6a61a-181">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-181"></span></span>|
|<span data-ttu-id="6a61a-182">**Algoritmo di firma**</span><span class="sxs-lookup"><span data-stu-id="6a61a-182">**Signature Algorithm**</span></span>|
|<span data-ttu-id="6a61a-183">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-183"></span></span>|
|<span data-ttu-id="6a61a-184">**Validità non prima**</span><span class="sxs-lookup"><span data-stu-id="6a61a-184">**Validity Not Before**</span></span>|
|<span data-ttu-id="6a61a-185">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-185"></span></span>|
|<span data-ttu-id="6a61a-186">**Validità non dopo**</span><span class="sxs-lookup"><span data-stu-id="6a61a-186">**Validity Not After**</span></span>|
|<span data-ttu-id="6a61a-187">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-187"></span></span>|
|<span data-ttu-id="6a61a-188">**Identificatore chiave del soggetto**</span><span class="sxs-lookup"><span data-stu-id="6a61a-188">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="6a61a-189">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-189"></span></span>|
|<span data-ttu-id="6a61a-190">**Identificatore chiave dell'autorità**</span><span class="sxs-lookup"><span data-stu-id="6a61a-190">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="6a61a-191">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-191"></span></span>|
|<span data-ttu-id="6a61a-192">**Identificazione personale (SHA-1)**</span><span class="sxs-lookup"><span data-stu-id="6a61a-192">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="6a61a-193">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-193"></span></span>|
|<span data-ttu-id="6a61a-194">**Identificazione personale (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="6a61a-194">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="6a61a-195">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-195"></span></span>|
|<span data-ttu-id="6a61a-196">**PIN (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="6a61a-196">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="6a61a-197">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-197"></span></span>|
   
 <span data-ttu-id="6a61a-198">**Autorità di certificazione radice globale DigiCert**</span><span class="sxs-lookup"><span data-stu-id="6a61a-198">**DigiCert Global Root CA**</span></span>
  
||
|:-----|
|<span data-ttu-id="6a61a-199">**Oggetto**</span><span class="sxs-lookup"><span data-stu-id="6a61a-199">**Subject**</span></span>|
|<span data-ttu-id="6a61a-200">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-200"></span></span>|
|<span data-ttu-id="6a61a-201">**Numero di serie**</span><span class="sxs-lookup"><span data-stu-id="6a61a-201">**Serial Number**</span></span>|
|<span data-ttu-id="6a61a-202">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-202"></span></span>|
|<span data-ttu-id="6a61a-203">**Lunghezza chiave pubblica**</span><span class="sxs-lookup"><span data-stu-id="6a61a-203">**Public Key Length**</span></span>|
|<span data-ttu-id="6a61a-204">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-204"></span></span>|
|<span data-ttu-id="6a61a-205">**Algoritmo di firma**</span><span class="sxs-lookup"><span data-stu-id="6a61a-205">**Signature Algorithm**</span></span>|
|<span data-ttu-id="6a61a-206">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-206"></span></span>|
|<span data-ttu-id="6a61a-207">**Validità non prima**</span><span class="sxs-lookup"><span data-stu-id="6a61a-207">**Validity Not Before**</span></span>|
|<span data-ttu-id="6a61a-208">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-208"></span></span>|
|<span data-ttu-id="6a61a-209">**Validità non dopo**</span><span class="sxs-lookup"><span data-stu-id="6a61a-209">**Validity Not After**</span></span>|
|<span data-ttu-id="6a61a-210">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-210"></span></span>|
|<span data-ttu-id="6a61a-211">**Identificatore chiave del soggetto**</span><span class="sxs-lookup"><span data-stu-id="6a61a-211">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="6a61a-212">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-212"></span></span>|
|<span data-ttu-id="6a61a-213">**Identificatore chiave dell'autorità**</span><span class="sxs-lookup"><span data-stu-id="6a61a-213">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="6a61a-214">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-214"></span></span>|
|<span data-ttu-id="6a61a-215">**Identificazione personale (SHA-1)**</span><span class="sxs-lookup"><span data-stu-id="6a61a-215">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="6a61a-216">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-216"></span></span>|
|<span data-ttu-id="6a61a-217">**Identificazione personale (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="6a61a-217">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="6a61a-218">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-218"></span></span>|
|<span data-ttu-id="6a61a-219">**PIN (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="6a61a-219">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="6a61a-220">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-220"></span></span>|
   
 <span data-ttu-id="6a61a-221">**Autorità di certificazione radice convalida estesa con garanzia elevata DigiCert**</span><span class="sxs-lookup"><span data-stu-id="6a61a-221">**DigiCert High Assurance EV Root CA**</span></span>
  
||
|:-----|
|<span data-ttu-id="6a61a-222">**Oggetto**</span><span class="sxs-lookup"><span data-stu-id="6a61a-222">**Subject**</span></span>|
|<span data-ttu-id="6a61a-223">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-223"></span></span>|
|<span data-ttu-id="6a61a-224">**Numero di serie**</span><span class="sxs-lookup"><span data-stu-id="6a61a-224">**Serial Number**</span></span>|
|<span data-ttu-id="6a61a-225">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-225"></span></span>|
|<span data-ttu-id="6a61a-226">**Lunghezza chiave pubblica**</span><span class="sxs-lookup"><span data-stu-id="6a61a-226">**Public Key Length**</span></span>|
|<span data-ttu-id="6a61a-227">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-227"></span></span>|
|<span data-ttu-id="6a61a-228">**Algoritmo di firma**</span><span class="sxs-lookup"><span data-stu-id="6a61a-228">**Signature Algorithm**</span></span>|
|<span data-ttu-id="6a61a-229">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-229"></span></span>|
|<span data-ttu-id="6a61a-230">**Validità non prima**</span><span class="sxs-lookup"><span data-stu-id="6a61a-230">**Validity Not Before**</span></span>|
|<span data-ttu-id="6a61a-231">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-231"></span></span>|
|<span data-ttu-id="6a61a-232">**Validità non dopo**</span><span class="sxs-lookup"><span data-stu-id="6a61a-232">**Validity Not After**</span></span>|
|<span data-ttu-id="6a61a-233">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-233"></span></span>|
|<span data-ttu-id="6a61a-234">**Identificatore chiave del soggetto**</span><span class="sxs-lookup"><span data-stu-id="6a61a-234">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="6a61a-235">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-235"></span></span>|
|<span data-ttu-id="6a61a-236">**Identificatore chiave dell'autorità**</span><span class="sxs-lookup"><span data-stu-id="6a61a-236">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="6a61a-237">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-237"></span></span>|
|<span data-ttu-id="6a61a-238">**Identificazione personale (SHA-1)**</span><span class="sxs-lookup"><span data-stu-id="6a61a-238">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="6a61a-239">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-239"></span></span>|
|<span data-ttu-id="6a61a-240">**Identificazione personale (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="6a61a-240">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="6a61a-241">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-241"></span></span>|
|<span data-ttu-id="6a61a-242">**PIN (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="6a61a-242">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="6a61a-243">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-243"></span></span>|
   
 <span data-ttu-id="6a61a-244">**Autorità di certificazione radice D protezione classe 3 2 2009**</span><span class="sxs-lookup"><span data-stu-id="6a61a-244">**D-TRUST Root Class 3 CA 2 2009**</span></span>
  
||
|:-----|
|<span data-ttu-id="6a61a-245">**Oggetto**</span><span class="sxs-lookup"><span data-stu-id="6a61a-245">**Subject**</span></span>|
|<span data-ttu-id="6a61a-246">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-246"></span></span>|
|<span data-ttu-id="6a61a-247">**Numero di serie**</span><span class="sxs-lookup"><span data-stu-id="6a61a-247">**Serial Number**</span></span>|
|<span data-ttu-id="6a61a-248">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-248"></span></span>|
|<span data-ttu-id="6a61a-249">**Lunghezza chiave pubblica**</span><span class="sxs-lookup"><span data-stu-id="6a61a-249">**Public Key Length**</span></span>|
|<span data-ttu-id="6a61a-250">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-250"></span></span>|
|<span data-ttu-id="6a61a-251">**Algoritmo di firma**</span><span class="sxs-lookup"><span data-stu-id="6a61a-251">**Signature Algorithm**</span></span>|
|<span data-ttu-id="6a61a-252">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-252"></span></span>|
|<span data-ttu-id="6a61a-253">**Validità non prima**</span><span class="sxs-lookup"><span data-stu-id="6a61a-253">**Validity Not Before**</span></span>|
|<span data-ttu-id="6a61a-254">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-254"></span></span>|
|<span data-ttu-id="6a61a-255">**Validità non dopo**</span><span class="sxs-lookup"><span data-stu-id="6a61a-255">**Validity Not After**</span></span>|
|<span data-ttu-id="6a61a-256">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-256"></span></span>|
|<span data-ttu-id="6a61a-257">**Identificatore chiave del soggetto**</span><span class="sxs-lookup"><span data-stu-id="6a61a-257">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="6a61a-258">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-258"></span></span>|
|<span data-ttu-id="6a61a-259">**Identificazione personale (SHA-1)**</span><span class="sxs-lookup"><span data-stu-id="6a61a-259">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="6a61a-260">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-260"></span></span>|
|<span data-ttu-id="6a61a-261">**Identificazione personale (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="6a61a-261">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="6a61a-262">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-262"></span></span>|
|<span data-ttu-id="6a61a-263">**PIN (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="6a61a-263">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="6a61a-264">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-264"></span></span>|
|<span data-ttu-id="6a61a-265">**URL di revoche di certificati**</span><span class="sxs-lookup"><span data-stu-id="6a61a-265">**CRL URLs**</span></span>|
|<span data-ttu-id="6a61a-266">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-266"></span></span>|
   
 <span data-ttu-id="6a61a-267">**D-TRUST radice classe 3 CA 2 EV 2009**</span><span class="sxs-lookup"><span data-stu-id="6a61a-267">**D-TRUST Root Class 3 CA 2 EV 2009**</span></span>
  
||
|:-----|
|<span data-ttu-id="6a61a-268">**Oggetto**</span><span class="sxs-lookup"><span data-stu-id="6a61a-268">**Subject**</span></span>|
|<span data-ttu-id="6a61a-269">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-269"></span></span>|
|<span data-ttu-id="6a61a-270">**Numero di serie**</span><span class="sxs-lookup"><span data-stu-id="6a61a-270">**Serial Number**</span></span>|
|<span data-ttu-id="6a61a-271">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-271"></span></span>|
|<span data-ttu-id="6a61a-272">**Lunghezza chiave pubblica**</span><span class="sxs-lookup"><span data-stu-id="6a61a-272">**Public Key Length**</span></span>|
|<span data-ttu-id="6a61a-273">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-273"></span></span>|
|<span data-ttu-id="6a61a-274">**Algoritmo di firma**</span><span class="sxs-lookup"><span data-stu-id="6a61a-274">**Signature Algorithm**</span></span>|
|<span data-ttu-id="6a61a-275">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-275"></span></span>|
|<span data-ttu-id="6a61a-276">**Validità non prima**</span><span class="sxs-lookup"><span data-stu-id="6a61a-276">**Validity Not Before**</span></span>|
|<span data-ttu-id="6a61a-277">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-277"></span></span>|
|<span data-ttu-id="6a61a-278">**Validità non dopo**</span><span class="sxs-lookup"><span data-stu-id="6a61a-278">**Validity Not After**</span></span>|
|<span data-ttu-id="6a61a-279">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-279"></span></span>|
|<span data-ttu-id="6a61a-280">**Identificatore chiave del soggetto**</span><span class="sxs-lookup"><span data-stu-id="6a61a-280">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="6a61a-281">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-281"></span></span>|
|<span data-ttu-id="6a61a-282">**Identificazione personale (SHA-1)**</span><span class="sxs-lookup"><span data-stu-id="6a61a-282">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="6a61a-283">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-283"></span></span>|
|<span data-ttu-id="6a61a-284">**Identificazione personale (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="6a61a-284">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="6a61a-285">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-285"></span></span>|
|<span data-ttu-id="6a61a-286">**PIN (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="6a61a-286">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="6a61a-287">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-287"></span></span>|
|<span data-ttu-id="6a61a-288">**URL di revoche di certificati**</span><span class="sxs-lookup"><span data-stu-id="6a61a-288">**CRL URLs**</span></span>|
|<span data-ttu-id="6a61a-289">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-289"></span></span>|
   
 <span data-ttu-id="6a61a-290">**LEGALE rootca X3**</span><span class="sxs-lookup"><span data-stu-id="6a61a-290">**DST Root CA X3**</span></span>
  
||
|:-----|
|<span data-ttu-id="6a61a-291">**Oggetto**</span><span class="sxs-lookup"><span data-stu-id="6a61a-291">**Subject**</span></span>|
|<span data-ttu-id="6a61a-292">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-292"></span></span>|
|<span data-ttu-id="6a61a-293">**Numero di serie**</span><span class="sxs-lookup"><span data-stu-id="6a61a-293">**Serial Number**</span></span>|
|<span data-ttu-id="6a61a-294">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-294"></span></span>|
|<span data-ttu-id="6a61a-295">**Lunghezza chiave pubblica**</span><span class="sxs-lookup"><span data-stu-id="6a61a-295">**Public Key Length**</span></span>|
|<span data-ttu-id="6a61a-296">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-296"></span></span>|
|<span data-ttu-id="6a61a-297">**Algoritmo di firma**</span><span class="sxs-lookup"><span data-stu-id="6a61a-297">**Signature Algorithm**</span></span>|
|<span data-ttu-id="6a61a-298">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-298"></span></span>|
|<span data-ttu-id="6a61a-299">**Validità non prima**</span><span class="sxs-lookup"><span data-stu-id="6a61a-299">**Validity Not Before**</span></span>|
|<span data-ttu-id="6a61a-300">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-300"></span></span>|
|<span data-ttu-id="6a61a-301">**Validità non dopo**</span><span class="sxs-lookup"><span data-stu-id="6a61a-301">**Validity Not After**</span></span>|
|<span data-ttu-id="6a61a-302">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-302"></span></span>|
|<span data-ttu-id="6a61a-303">**Identificatore chiave del soggetto**</span><span class="sxs-lookup"><span data-stu-id="6a61a-303">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="6a61a-304">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-304"></span></span>|
|<span data-ttu-id="6a61a-305">**Identificazione personale (SHA-1)**</span><span class="sxs-lookup"><span data-stu-id="6a61a-305">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="6a61a-306">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-306"></span></span>|
|<span data-ttu-id="6a61a-307">**Identificazione personale (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="6a61a-307">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="6a61a-308">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-308"></span></span>|
|<span data-ttu-id="6a61a-309">**PIN (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="6a61a-309">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="6a61a-310">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-310"></span></span>|
   
 <span data-ttu-id="6a61a-311">**Affidare autorità di certificazione radice - G2**</span><span class="sxs-lookup"><span data-stu-id="6a61a-311">**Entrust Root Certification Authority - G2**</span></span>
  
||
|:-----|
|<span data-ttu-id="6a61a-312">**Oggetto**</span><span class="sxs-lookup"><span data-stu-id="6a61a-312">**Subject**</span></span>|
|<span data-ttu-id="6a61a-313">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-313"></span></span>|
|<span data-ttu-id="6a61a-314">**Numero di serie**</span><span class="sxs-lookup"><span data-stu-id="6a61a-314">**Serial Number**</span></span>|
|<span data-ttu-id="6a61a-315">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-315"></span></span>|
|<span data-ttu-id="6a61a-316">**Lunghezza chiave pubblica**</span><span class="sxs-lookup"><span data-stu-id="6a61a-316">**Public Key Length**</span></span>|
|<span data-ttu-id="6a61a-317">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-317"></span></span>|
|<span data-ttu-id="6a61a-318">**Algoritmo di firma**</span><span class="sxs-lookup"><span data-stu-id="6a61a-318">**Signature Algorithm**</span></span>|
|<span data-ttu-id="6a61a-319">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-319"></span></span>|
|<span data-ttu-id="6a61a-320">**Validità non prima**</span><span class="sxs-lookup"><span data-stu-id="6a61a-320">**Validity Not Before**</span></span>|
|<span data-ttu-id="6a61a-321">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-321"></span></span>|
|<span data-ttu-id="6a61a-322">**Validità non dopo**</span><span class="sxs-lookup"><span data-stu-id="6a61a-322">**Validity Not After**</span></span>|
|<span data-ttu-id="6a61a-323">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-323"></span></span>|
|<span data-ttu-id="6a61a-324">**Identificatore chiave del soggetto**</span><span class="sxs-lookup"><span data-stu-id="6a61a-324">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="6a61a-325">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-325"></span></span>|
|<span data-ttu-id="6a61a-326">**Identificazione personale (SHA-1)**</span><span class="sxs-lookup"><span data-stu-id="6a61a-326">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="6a61a-327">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-327"></span></span>|
|<span data-ttu-id="6a61a-328">**Identificazione personale (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="6a61a-328">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="6a61a-329">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-329"></span></span>|
|<span data-ttu-id="6a61a-330">**PIN (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="6a61a-330">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="6a61a-331">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-331"></span></span>|
   
 <span data-ttu-id="6a61a-332">**Entrust.net Certification Authority (2048)**</span><span class="sxs-lookup"><span data-stu-id="6a61a-332">**Entrust.net Certification Authority (2048)**</span></span>
  
||
|:-----|
|<span data-ttu-id="6a61a-333">**Oggetto**</span><span class="sxs-lookup"><span data-stu-id="6a61a-333">**Subject**</span></span>|
|<span data-ttu-id="6a61a-334">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-334"></span></span>|
|<span data-ttu-id="6a61a-335">**Numero di serie**</span><span class="sxs-lookup"><span data-stu-id="6a61a-335">**Serial Number**</span></span>|
|<span data-ttu-id="6a61a-336">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-336"></span></span>|
|<span data-ttu-id="6a61a-337">**Lunghezza chiave pubblica**</span><span class="sxs-lookup"><span data-stu-id="6a61a-337">**Public Key Length**</span></span>|
|<span data-ttu-id="6a61a-338">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-338"></span></span>|
|<span data-ttu-id="6a61a-339">**Algoritmo di firma**</span><span class="sxs-lookup"><span data-stu-id="6a61a-339">**Signature Algorithm**</span></span>|
|<span data-ttu-id="6a61a-340">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-340"></span></span>|
|<span data-ttu-id="6a61a-341">**Validità non prima**</span><span class="sxs-lookup"><span data-stu-id="6a61a-341">**Validity Not Before**</span></span>|
|<span data-ttu-id="6a61a-342">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-342"></span></span>|
|<span data-ttu-id="6a61a-343">**Validità non dopo**</span><span class="sxs-lookup"><span data-stu-id="6a61a-343">**Validity Not After**</span></span>|
|<span data-ttu-id="6a61a-344">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-344"></span></span>|
|<span data-ttu-id="6a61a-345">**Identificatore chiave del soggetto**</span><span class="sxs-lookup"><span data-stu-id="6a61a-345">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="6a61a-346">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-346"></span></span>|
|<span data-ttu-id="6a61a-347">**Identificazione personale (SHA-1)**</span><span class="sxs-lookup"><span data-stu-id="6a61a-347">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="6a61a-348">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-348"></span></span>|
|<span data-ttu-id="6a61a-349">**Identificazione personale (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="6a61a-349">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="6a61a-350">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-350"></span></span>|
|<span data-ttu-id="6a61a-351">**PIN (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="6a61a-351">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="6a61a-352">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-352"></span></span>|
   
 <span data-ttu-id="6a61a-353">**GlobalSign**</span><span class="sxs-lookup"><span data-stu-id="6a61a-353">**GlobalSign**</span></span>
  
||
|:-----|
|<span data-ttu-id="6a61a-354">**Oggetto**</span><span class="sxs-lookup"><span data-stu-id="6a61a-354">**Subject**</span></span>|
|<span data-ttu-id="6a61a-355">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-355"></span></span>|
|<span data-ttu-id="6a61a-356">**Numero di serie**</span><span class="sxs-lookup"><span data-stu-id="6a61a-356">**Serial Number**</span></span>|
|<span data-ttu-id="6a61a-357">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-357"></span></span>|
|<span data-ttu-id="6a61a-358">**Lunghezza chiave pubblica**</span><span class="sxs-lookup"><span data-stu-id="6a61a-358">**Public Key Length**</span></span>|
|<span data-ttu-id="6a61a-359">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-359"></span></span>|
|<span data-ttu-id="6a61a-360">**Algoritmo di firma**</span><span class="sxs-lookup"><span data-stu-id="6a61a-360">**Signature Algorithm**</span></span>|
|<span data-ttu-id="6a61a-361">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-361"></span></span>|
|<span data-ttu-id="6a61a-362">**Validità non prima**</span><span class="sxs-lookup"><span data-stu-id="6a61a-362">**Validity Not Before**</span></span>|
|<span data-ttu-id="6a61a-363">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-363"></span></span>|
|<span data-ttu-id="6a61a-364">**Validità non dopo**</span><span class="sxs-lookup"><span data-stu-id="6a61a-364">**Validity Not After**</span></span>|
|<span data-ttu-id="6a61a-365">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-365"></span></span>|
|<span data-ttu-id="6a61a-366">**Identificatore chiave del soggetto**</span><span class="sxs-lookup"><span data-stu-id="6a61a-366">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="6a61a-367">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-367"></span></span>|
|<span data-ttu-id="6a61a-368">**Identificatore chiave dell'autorità**</span><span class="sxs-lookup"><span data-stu-id="6a61a-368">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="6a61a-369">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-369"></span></span>|
|<span data-ttu-id="6a61a-370">**Identificazione personale (SHA-1)**</span><span class="sxs-lookup"><span data-stu-id="6a61a-370">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="6a61a-371">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-371"></span></span>|
|<span data-ttu-id="6a61a-372">**Identificazione personale (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="6a61a-372">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="6a61a-373">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-373"></span></span>|
|<span data-ttu-id="6a61a-374">**PIN (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="6a61a-374">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="6a61a-375">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-375"></span></span>|
|<span data-ttu-id="6a61a-376">**URL di revoche di certificati**</span><span class="sxs-lookup"><span data-stu-id="6a61a-376">**CRL URLs**</span></span>|
|<span data-ttu-id="6a61a-377">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-377"></span></span>|
   
 <span data-ttu-id="6a61a-378">**GlobalSign Root CA**</span><span class="sxs-lookup"><span data-stu-id="6a61a-378">**GlobalSign Root CA**</span></span>
  
||
|:-----|
|<span data-ttu-id="6a61a-379">**Oggetto**</span><span class="sxs-lookup"><span data-stu-id="6a61a-379">**Subject**</span></span>|
|<span data-ttu-id="6a61a-380">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-380"></span></span>|
|<span data-ttu-id="6a61a-381">**Numero di serie**</span><span class="sxs-lookup"><span data-stu-id="6a61a-381">**Serial Number**</span></span>|
|<span data-ttu-id="6a61a-382">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-382"></span></span>|
|<span data-ttu-id="6a61a-383">**Lunghezza chiave pubblica**</span><span class="sxs-lookup"><span data-stu-id="6a61a-383">**Public Key Length**</span></span>|
|<span data-ttu-id="6a61a-384">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-384"></span></span>|
|<span data-ttu-id="6a61a-385">**Algoritmo di firma**</span><span class="sxs-lookup"><span data-stu-id="6a61a-385">**Signature Algorithm**</span></span>|
|<span data-ttu-id="6a61a-386">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-386"></span></span>|
|<span data-ttu-id="6a61a-387">**Validità non prima**</span><span class="sxs-lookup"><span data-stu-id="6a61a-387">**Validity Not Before**</span></span>|
|<span data-ttu-id="6a61a-388">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-388"></span></span>|
|<span data-ttu-id="6a61a-389">**Validità non dopo**</span><span class="sxs-lookup"><span data-stu-id="6a61a-389">**Validity Not After**</span></span>|
|<span data-ttu-id="6a61a-390">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-390"></span></span>|
|<span data-ttu-id="6a61a-391">**Identificatore chiave del soggetto**</span><span class="sxs-lookup"><span data-stu-id="6a61a-391">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="6a61a-392">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-392"></span></span>|
|<span data-ttu-id="6a61a-393">**Identificazione personale (SHA-1)**</span><span class="sxs-lookup"><span data-stu-id="6a61a-393">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="6a61a-394">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-394"></span></span>|
|<span data-ttu-id="6a61a-395">**Identificazione personale (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="6a61a-395">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="6a61a-396">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-396"></span></span>|
|<span data-ttu-id="6a61a-397">**PIN (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="6a61a-397">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="6a61a-398">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-398"></span></span>|
   
 <span data-ttu-id="6a61a-399">**Thawte CA radice principale - G3**</span><span class="sxs-lookup"><span data-stu-id="6a61a-399">**thawte Primary Root CA - G3**</span></span>
  
||
|:-----|
|<span data-ttu-id="6a61a-400">**Oggetto**</span><span class="sxs-lookup"><span data-stu-id="6a61a-400">**Subject**</span></span>|
|<span data-ttu-id="6a61a-401">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-401"></span></span>|
|<span data-ttu-id="6a61a-402">**Numero di serie**</span><span class="sxs-lookup"><span data-stu-id="6a61a-402">**Serial Number**</span></span>|
|<span data-ttu-id="6a61a-403">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-403"></span></span>|
|<span data-ttu-id="6a61a-404">**Lunghezza chiave pubblica**</span><span class="sxs-lookup"><span data-stu-id="6a61a-404">**Public Key Length**</span></span>|
|<span data-ttu-id="6a61a-405">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-405"></span></span>|
|<span data-ttu-id="6a61a-406">**Algoritmo di firma**</span><span class="sxs-lookup"><span data-stu-id="6a61a-406">**Signature Algorithm**</span></span>|
|<span data-ttu-id="6a61a-407">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-407"></span></span>|
|<span data-ttu-id="6a61a-408">**Validità non prima**</span><span class="sxs-lookup"><span data-stu-id="6a61a-408">**Validity Not Before**</span></span>|
|<span data-ttu-id="6a61a-409">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-409"></span></span>|
|<span data-ttu-id="6a61a-410">**Validità non dopo**</span><span class="sxs-lookup"><span data-stu-id="6a61a-410">**Validity Not After**</span></span>|
|<span data-ttu-id="6a61a-411">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-411"></span></span>|
|<span data-ttu-id="6a61a-412">**Identificatore chiave del soggetto**</span><span class="sxs-lookup"><span data-stu-id="6a61a-412">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="6a61a-413">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-413"></span></span>|
|<span data-ttu-id="6a61a-414">**Identificazione personale (SHA-1)**</span><span class="sxs-lookup"><span data-stu-id="6a61a-414">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="6a61a-415">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-415"></span></span>|
|<span data-ttu-id="6a61a-416">**Identificazione personale (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="6a61a-416">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="6a61a-417">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-417"></span></span>|
|<span data-ttu-id="6a61a-418">**PIN (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="6a61a-418">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="6a61a-419">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-419"></span></span>|
   
 <span data-ttu-id="6a61a-420">**Autorità di certificazione principale pubblica VeriSign classe 3 - G5**</span><span class="sxs-lookup"><span data-stu-id="6a61a-420">**VeriSign Class 3 Public Primary Certification Authority - G5**</span></span>
  
||
|:-----|
|<span data-ttu-id="6a61a-421">**Oggetto**</span><span class="sxs-lookup"><span data-stu-id="6a61a-421">**Subject**</span></span>|
|<span data-ttu-id="6a61a-422">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-422"></span></span>|
|<span data-ttu-id="6a61a-423">**Numero di serie**</span><span class="sxs-lookup"><span data-stu-id="6a61a-423">**Serial Number**</span></span>|
|<span data-ttu-id="6a61a-424">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-424"></span></span>|
|<span data-ttu-id="6a61a-425">**Lunghezza chiave pubblica**</span><span class="sxs-lookup"><span data-stu-id="6a61a-425">**Public Key Length**</span></span>|
|<span data-ttu-id="6a61a-426">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-426"></span></span>|
|<span data-ttu-id="6a61a-427">**Algoritmo di firma**</span><span class="sxs-lookup"><span data-stu-id="6a61a-427">**Signature Algorithm**</span></span>|
|<span data-ttu-id="6a61a-428">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-428"></span></span>|
|<span data-ttu-id="6a61a-429">**Validità non prima**</span><span class="sxs-lookup"><span data-stu-id="6a61a-429">**Validity Not Before**</span></span>|
|<span data-ttu-id="6a61a-430">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-430"></span></span>|
|<span data-ttu-id="6a61a-431">**Validità non dopo**</span><span class="sxs-lookup"><span data-stu-id="6a61a-431">**Validity Not After**</span></span>|
|<span data-ttu-id="6a61a-432">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-432"></span></span>|
|<span data-ttu-id="6a61a-433">**Identificatore chiave del soggetto**</span><span class="sxs-lookup"><span data-stu-id="6a61a-433">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="6a61a-434">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-434"></span></span>|
|<span data-ttu-id="6a61a-435">**Identificazione personale (SHA-1)**</span><span class="sxs-lookup"><span data-stu-id="6a61a-435">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="6a61a-436">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-436"></span></span>|
|<span data-ttu-id="6a61a-437">**Identificazione personale (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="6a61a-437">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="6a61a-438">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-438"></span></span>|
|<span data-ttu-id="6a61a-439">**PIN (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="6a61a-439">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="6a61a-440">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-440"></span></span>|
   
## <a name="office-365-intermediate-certificate-details"></a><span data-ttu-id="6a61a-441">Informazioni relative al certificato intermedio Office 365</span><span class="sxs-lookup"><span data-stu-id="6a61a-441">Office 365 Intermediate Certificate Details</span></span>
<span data-ttu-id="6a61a-442"><a name="IntermediateCerts"> </a></span><span class="sxs-lookup"><span data-stu-id="6a61a-442"></span></span>

 <span data-ttu-id="6a61a-443">**CNNIC SHA256 SSL**</span><span class="sxs-lookup"><span data-stu-id="6a61a-443">**CNNIC SHA256 SSL**</span></span>
  
||
|:-----|
|<span data-ttu-id="6a61a-444">**Oggetto**</span><span class="sxs-lookup"><span data-stu-id="6a61a-444">**Subject**</span></span>|
|<span data-ttu-id="6a61a-445">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-445"></span></span>|
|<span data-ttu-id="6a61a-446">**Autorità di certificazione**</span><span class="sxs-lookup"><span data-stu-id="6a61a-446">**Issuer**</span></span>|
|<span data-ttu-id="6a61a-447">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-447"></span></span>|
|<span data-ttu-id="6a61a-448">**Numero di serie**</span><span class="sxs-lookup"><span data-stu-id="6a61a-448">**Serial Number**</span></span>|
|<span data-ttu-id="6a61a-449">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-449"></span></span>|
|<span data-ttu-id="6a61a-450">**Lunghezza chiave pubblica**</span><span class="sxs-lookup"><span data-stu-id="6a61a-450">**Public Key Length**</span></span>|
|<span data-ttu-id="6a61a-451">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-451"></span></span>|
|<span data-ttu-id="6a61a-452">**Algoritmo di firma**</span><span class="sxs-lookup"><span data-stu-id="6a61a-452">**Signature Algorithm**</span></span>|
|<span data-ttu-id="6a61a-453">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-453"></span></span>|
|<span data-ttu-id="6a61a-454">**Validità non prima**</span><span class="sxs-lookup"><span data-stu-id="6a61a-454">**Validity Not Before**</span></span>|
|<span data-ttu-id="6a61a-455">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-455"></span></span>|
|<span data-ttu-id="6a61a-456">**Validità non dopo**</span><span class="sxs-lookup"><span data-stu-id="6a61a-456">**Validity Not After**</span></span>|
|<span data-ttu-id="6a61a-457">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-457"></span></span>|
|<span data-ttu-id="6a61a-458">**Identificatore chiave del soggetto**</span><span class="sxs-lookup"><span data-stu-id="6a61a-458">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="6a61a-459">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-459"></span></span>|
|<span data-ttu-id="6a61a-460">**Identificatore chiave dell'autorità**</span><span class="sxs-lookup"><span data-stu-id="6a61a-460">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="6a61a-461">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-461"></span></span>|
|<span data-ttu-id="6a61a-462">**Identificazione personale (SHA-1)**</span><span class="sxs-lookup"><span data-stu-id="6a61a-462">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="6a61a-463">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-463"></span></span>|
|<span data-ttu-id="6a61a-464">**Identificazione personale (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="6a61a-464">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="6a61a-465">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-465"></span></span>|
|<span data-ttu-id="6a61a-466">**PIN (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="6a61a-466">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="6a61a-467">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-467"></span></span>|
|<span data-ttu-id="6a61a-468">**URL AIA**</span><span class="sxs-lookup"><span data-stu-id="6a61a-468">**AIA URLs**</span></span>|
|<span data-ttu-id="6a61a-469">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-469"></span></span>|
|<span data-ttu-id="6a61a-470">**URL di revoche di certificati**</span><span class="sxs-lookup"><span data-stu-id="6a61a-470">**CRL URLs**</span></span>|
|<span data-ttu-id="6a61a-471">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-471"></span></span>|
|<span data-ttu-id="6a61a-472">**URL OCSP**</span><span class="sxs-lookup"><span data-stu-id="6a61a-472">**OCSP URLs**</span></span>|
|<span data-ttu-id="6a61a-473">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-473"></span></span>|
   
 <span data-ttu-id="6a61a-474">**Autorità di certificazione classe 3 D protezione SSL 1 2009**</span><span class="sxs-lookup"><span data-stu-id="6a61a-474">**D-TRUST SSL Class 3 CA 1 2009**</span></span>
  
||
|:-----|
|<span data-ttu-id="6a61a-475">**Oggetto**</span><span class="sxs-lookup"><span data-stu-id="6a61a-475">**Subject**</span></span>|
|<span data-ttu-id="6a61a-476">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-476"></span></span>|
|<span data-ttu-id="6a61a-477">**Autorità di certificazione**</span><span class="sxs-lookup"><span data-stu-id="6a61a-477">**Issuer**</span></span>|
|<span data-ttu-id="6a61a-478">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-478"></span></span>|
|<span data-ttu-id="6a61a-479">**Nome alternativo soggetto**</span><span class="sxs-lookup"><span data-stu-id="6a61a-479">**Subject Alternative Name**</span></span>|
|<span data-ttu-id="6a61a-480">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-480"></span></span>|
|<span data-ttu-id="6a61a-481">**Numero di serie**</span><span class="sxs-lookup"><span data-stu-id="6a61a-481">**Serial Number**</span></span>|
|<span data-ttu-id="6a61a-482">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-482"></span></span>|
|<span data-ttu-id="6a61a-483">**Lunghezza chiave pubblica**</span><span class="sxs-lookup"><span data-stu-id="6a61a-483">**Public Key Length**</span></span>|
|<span data-ttu-id="6a61a-484">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-484"></span></span>|
|<span data-ttu-id="6a61a-485">**Algoritmo di firma**</span><span class="sxs-lookup"><span data-stu-id="6a61a-485">**Signature Algorithm**</span></span>|
|<span data-ttu-id="6a61a-486">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-486"></span></span>|
|<span data-ttu-id="6a61a-487">**Validità non prima**</span><span class="sxs-lookup"><span data-stu-id="6a61a-487">**Validity Not Before**</span></span>|
|<span data-ttu-id="6a61a-488">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-488"></span></span>|
|<span data-ttu-id="6a61a-489">**Validità non dopo**</span><span class="sxs-lookup"><span data-stu-id="6a61a-489">**Validity Not After**</span></span>|
|<span data-ttu-id="6a61a-490">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-490"></span></span>|
|<span data-ttu-id="6a61a-491">**Identificatore chiave del soggetto**</span><span class="sxs-lookup"><span data-stu-id="6a61a-491">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="6a61a-492">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-492"></span></span>|
|<span data-ttu-id="6a61a-493">**Identificatore chiave dell'autorità**</span><span class="sxs-lookup"><span data-stu-id="6a61a-493">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="6a61a-494">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-494"></span></span>|
|<span data-ttu-id="6a61a-495">**Identificazione personale (SHA-1)**</span><span class="sxs-lookup"><span data-stu-id="6a61a-495">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="6a61a-496">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-496"></span></span>|
|<span data-ttu-id="6a61a-497">**Identificazione personale (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="6a61a-497">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="6a61a-498">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-498"></span></span>|
|<span data-ttu-id="6a61a-499">**PIN (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="6a61a-499">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="6a61a-500">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-500"></span></span>|
|<span data-ttu-id="6a61a-501">**URL di revoche di certificati**</span><span class="sxs-lookup"><span data-stu-id="6a61a-501">**CRL URLs**</span></span>|
|<span data-ttu-id="6a61a-502">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-502"></span></span>|
|<span data-ttu-id="6a61a-503">**URL OCSP**</span><span class="sxs-lookup"><span data-stu-id="6a61a-503">**OCSP URLs**</span></span>|
|<span data-ttu-id="6a61a-504">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-504"></span></span>|
   
 <span data-ttu-id="6a61a-505">**Autorità di certificazione classe 3 D protezione SSL 1 EV 2009**</span><span class="sxs-lookup"><span data-stu-id="6a61a-505">**D-TRUST SSL Class 3 CA 1 EV 2009**</span></span>
  
||
|:-----|
|<span data-ttu-id="6a61a-506">**Oggetto**</span><span class="sxs-lookup"><span data-stu-id="6a61a-506">**Subject**</span></span>|
|<span data-ttu-id="6a61a-507">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-507"></span></span>|
|<span data-ttu-id="6a61a-508">**Autorità di certificazione**</span><span class="sxs-lookup"><span data-stu-id="6a61a-508">**Issuer**</span></span>|
|<span data-ttu-id="6a61a-509">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-509"></span></span>|
|<span data-ttu-id="6a61a-510">**Nome alternativo soggetto**</span><span class="sxs-lookup"><span data-stu-id="6a61a-510">**Subject Alternative Name**</span></span>|
|<span data-ttu-id="6a61a-511">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-511"></span></span>|
|<span data-ttu-id="6a61a-512">**Numero di serie**</span><span class="sxs-lookup"><span data-stu-id="6a61a-512">**Serial Number**</span></span>|
|<span data-ttu-id="6a61a-513">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-513"></span></span>|
|<span data-ttu-id="6a61a-514">**Lunghezza chiave pubblica**</span><span class="sxs-lookup"><span data-stu-id="6a61a-514">**Public Key Length**</span></span>|
|<span data-ttu-id="6a61a-515">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-515"></span></span>|
|<span data-ttu-id="6a61a-516">**Algoritmo di firma**</span><span class="sxs-lookup"><span data-stu-id="6a61a-516">**Signature Algorithm**</span></span>|
|<span data-ttu-id="6a61a-517">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-517"></span></span>|
|<span data-ttu-id="6a61a-518">**Validità non prima**</span><span class="sxs-lookup"><span data-stu-id="6a61a-518">**Validity Not Before**</span></span>|
|<span data-ttu-id="6a61a-519">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-519"></span></span>|
|<span data-ttu-id="6a61a-520">**Validità non dopo**</span><span class="sxs-lookup"><span data-stu-id="6a61a-520">**Validity Not After**</span></span>|
|<span data-ttu-id="6a61a-521">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-521"></span></span>|
|<span data-ttu-id="6a61a-522">**Identificatore chiave del soggetto**</span><span class="sxs-lookup"><span data-stu-id="6a61a-522">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="6a61a-523">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-523"></span></span>|
|<span data-ttu-id="6a61a-524">**Identificatore chiave dell'autorità**</span><span class="sxs-lookup"><span data-stu-id="6a61a-524">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="6a61a-525">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-525"></span></span>|
|<span data-ttu-id="6a61a-526">**Identificazione personale (SHA-1)**</span><span class="sxs-lookup"><span data-stu-id="6a61a-526">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="6a61a-527">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-527"></span></span>|
|<span data-ttu-id="6a61a-528">**Identificazione personale (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="6a61a-528">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="6a61a-529">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-529"></span></span>|
|<span data-ttu-id="6a61a-530">**PIN (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="6a61a-530">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="6a61a-531">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-531"></span></span>|
|<span data-ttu-id="6a61a-532">**URL di revoche di certificati**</span><span class="sxs-lookup"><span data-stu-id="6a61a-532">**CRL URLs**</span></span>|
|<span data-ttu-id="6a61a-533">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-533"></span></span>|
|<span data-ttu-id="6a61a-534">**URL OCSP**</span><span class="sxs-lookup"><span data-stu-id="6a61a-534">**OCSP URLs**</span></span>|
|<span data-ttu-id="6a61a-535">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-535"></span></span>|
   
 <span data-ttu-id="6a61a-536">**CA-1 di servizi Cloud DigiCert**</span><span class="sxs-lookup"><span data-stu-id="6a61a-536">**DigiCert Cloud Services CA-1**</span></span>
  
||
|:-----|
|<span data-ttu-id="6a61a-537">**Oggetto**</span><span class="sxs-lookup"><span data-stu-id="6a61a-537">**Subject**</span></span>|
|<span data-ttu-id="6a61a-538">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-538"></span></span>|
|<span data-ttu-id="6a61a-539">**Autorità di certificazione**</span><span class="sxs-lookup"><span data-stu-id="6a61a-539">**Issuer**</span></span>|
|<span data-ttu-id="6a61a-540">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-540"></span></span>|
|<span data-ttu-id="6a61a-541">**Numero di serie**</span><span class="sxs-lookup"><span data-stu-id="6a61a-541">**Serial Number**</span></span>|
|<span data-ttu-id="6a61a-542">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-542"></span></span>|
|<span data-ttu-id="6a61a-543">**Lunghezza chiave pubblica**</span><span class="sxs-lookup"><span data-stu-id="6a61a-543">**Public Key Length**</span></span>|
|<span data-ttu-id="6a61a-544">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-544"></span></span>|
|<span data-ttu-id="6a61a-545">**Algoritmo di firma**</span><span class="sxs-lookup"><span data-stu-id="6a61a-545">**Signature Algorithm**</span></span>|
|<span data-ttu-id="6a61a-546">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-546"></span></span>|
|<span data-ttu-id="6a61a-547">**Validità non prima**</span><span class="sxs-lookup"><span data-stu-id="6a61a-547">**Validity Not Before**</span></span>|
|<span data-ttu-id="6a61a-548">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-548"></span></span>|
|<span data-ttu-id="6a61a-549">**Validità non dopo**</span><span class="sxs-lookup"><span data-stu-id="6a61a-549">**Validity Not After**</span></span>|
|<span data-ttu-id="6a61a-550">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-550"></span></span>|
|<span data-ttu-id="6a61a-551">**Identificatore chiave del soggetto**</span><span class="sxs-lookup"><span data-stu-id="6a61a-551">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="6a61a-552">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-552"></span></span>|
|<span data-ttu-id="6a61a-553">**Identificatore chiave dell'autorità**</span><span class="sxs-lookup"><span data-stu-id="6a61a-553">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="6a61a-554">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-554"></span></span>|
|<span data-ttu-id="6a61a-555">**Identificazione personale (SHA-1)**</span><span class="sxs-lookup"><span data-stu-id="6a61a-555">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="6a61a-556">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-556"></span></span>|
|<span data-ttu-id="6a61a-557">**Identificazione personale (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="6a61a-557">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="6a61a-558">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-558"></span></span>|
|<span data-ttu-id="6a61a-559">**PIN (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="6a61a-559">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="6a61a-560">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-560"></span></span>|
|<span data-ttu-id="6a61a-561">**URL di revoche di certificati**</span><span class="sxs-lookup"><span data-stu-id="6a61a-561">**CRL URLs**</span></span>|
|<span data-ttu-id="6a61a-562">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-562"></span></span>|
|<span data-ttu-id="6a61a-563">**URL OCSP**</span><span class="sxs-lookup"><span data-stu-id="6a61a-563">**OCSP URLs**</span></span>|
|<span data-ttu-id="6a61a-564">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-564"></span></span>|
   
 <span data-ttu-id="6a61a-565">**Server di garanzia elevata DigiCert SHA2 autorità di certificazione**</span><span class="sxs-lookup"><span data-stu-id="6a61a-565">**DigiCert SHA2 High Assurance Server CA**</span></span>
  
||
|:-----|
|<span data-ttu-id="6a61a-566">**Oggetto**</span><span class="sxs-lookup"><span data-stu-id="6a61a-566">**Subject**</span></span>|
|<span data-ttu-id="6a61a-567">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-567"></span></span>|
|<span data-ttu-id="6a61a-568">**Autorità di certificazione**</span><span class="sxs-lookup"><span data-stu-id="6a61a-568">**Issuer**</span></span>|
|<span data-ttu-id="6a61a-569">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-569"></span></span>|
|<span data-ttu-id="6a61a-570">**Numero di serie**</span><span class="sxs-lookup"><span data-stu-id="6a61a-570">**Serial Number**</span></span>|
|<span data-ttu-id="6a61a-571">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-571"></span></span>|
|<span data-ttu-id="6a61a-572">**Lunghezza chiave pubblica**</span><span class="sxs-lookup"><span data-stu-id="6a61a-572">**Public Key Length**</span></span>|
|<span data-ttu-id="6a61a-573">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-573"></span></span>|
|<span data-ttu-id="6a61a-574">**Algoritmo di firma**</span><span class="sxs-lookup"><span data-stu-id="6a61a-574">**Signature Algorithm**</span></span>|
|<span data-ttu-id="6a61a-575">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-575"></span></span>|
|<span data-ttu-id="6a61a-576">**Validità non prima**</span><span class="sxs-lookup"><span data-stu-id="6a61a-576">**Validity Not Before**</span></span>|
|<span data-ttu-id="6a61a-577">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-577"></span></span>|
|<span data-ttu-id="6a61a-578">**Validità non dopo**</span><span class="sxs-lookup"><span data-stu-id="6a61a-578">**Validity Not After**</span></span>|
|<span data-ttu-id="6a61a-579">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-579"></span></span>|
|<span data-ttu-id="6a61a-580">**Identificatore chiave del soggetto**</span><span class="sxs-lookup"><span data-stu-id="6a61a-580">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="6a61a-581">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-581"></span></span>|
|<span data-ttu-id="6a61a-582">**Identificatore chiave dell'autorità**</span><span class="sxs-lookup"><span data-stu-id="6a61a-582">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="6a61a-583">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-583"></span></span>|
|<span data-ttu-id="6a61a-584">**Identificazione personale (SHA-1)**</span><span class="sxs-lookup"><span data-stu-id="6a61a-584">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="6a61a-585">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-585"></span></span>|
|<span data-ttu-id="6a61a-586">**Identificazione personale (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="6a61a-586">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="6a61a-587">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-587"></span></span>|
|<span data-ttu-id="6a61a-588">**PIN (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="6a61a-588">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="6a61a-589">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-589"></span></span>|
|<span data-ttu-id="6a61a-590">**URL di revoche di certificati**</span><span class="sxs-lookup"><span data-stu-id="6a61a-590">**CRL URLs**</span></span>|
|<span data-ttu-id="6a61a-591">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-591"></span></span>|
|<span data-ttu-id="6a61a-592">**URL OCSP**</span><span class="sxs-lookup"><span data-stu-id="6a61a-592">**OCSP URLs**</span></span>|
|<span data-ttu-id="6a61a-593">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-593"></span></span>|
   
 <span data-ttu-id="6a61a-594">**Server protetto DigiCert SHA2 autorità di certificazione**</span><span class="sxs-lookup"><span data-stu-id="6a61a-594">**DigiCert SHA2 Secure Server CA**</span></span>
  
||
|:-----|
|<span data-ttu-id="6a61a-595">**Oggetto**</span><span class="sxs-lookup"><span data-stu-id="6a61a-595">**Subject**</span></span>|
|<span data-ttu-id="6a61a-596">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-596"></span></span>|
|<span data-ttu-id="6a61a-597">**Autorità di certificazione**</span><span class="sxs-lookup"><span data-stu-id="6a61a-597">**Issuer**</span></span>|
|<span data-ttu-id="6a61a-598">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-598"></span></span>|
|<span data-ttu-id="6a61a-599">**Numero di serie**</span><span class="sxs-lookup"><span data-stu-id="6a61a-599">**Serial Number**</span></span>|
|<span data-ttu-id="6a61a-600">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-600"></span></span>|
|<span data-ttu-id="6a61a-601">**Lunghezza chiave pubblica**</span><span class="sxs-lookup"><span data-stu-id="6a61a-601">**Public Key Length**</span></span>|
|<span data-ttu-id="6a61a-602">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-602"></span></span>|
|<span data-ttu-id="6a61a-603">**Algoritmo di firma**</span><span class="sxs-lookup"><span data-stu-id="6a61a-603">**Signature Algorithm**</span></span>|
|<span data-ttu-id="6a61a-604">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-604"></span></span>|
|<span data-ttu-id="6a61a-605">**Validità non prima**</span><span class="sxs-lookup"><span data-stu-id="6a61a-605">**Validity Not Before**</span></span>|
|<span data-ttu-id="6a61a-606">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-606"></span></span>|
|<span data-ttu-id="6a61a-607">**Validità non dopo**</span><span class="sxs-lookup"><span data-stu-id="6a61a-607">**Validity Not After**</span></span>|
|<span data-ttu-id="6a61a-608">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-608"></span></span>|
|<span data-ttu-id="6a61a-609">**Identificatore chiave del soggetto**</span><span class="sxs-lookup"><span data-stu-id="6a61a-609">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="6a61a-610">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-610"></span></span>|
|<span data-ttu-id="6a61a-611">**Identificatore chiave dell'autorità**</span><span class="sxs-lookup"><span data-stu-id="6a61a-611">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="6a61a-612">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-612"></span></span>|
|<span data-ttu-id="6a61a-613">**Identificazione personale (SHA-1)**</span><span class="sxs-lookup"><span data-stu-id="6a61a-613">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="6a61a-614">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-614"></span></span>|
|<span data-ttu-id="6a61a-615">**Identificazione personale (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="6a61a-615">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="6a61a-616">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-616"></span></span>|
|<span data-ttu-id="6a61a-617">**PIN (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="6a61a-617">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="6a61a-618">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-618"></span></span>|
|<span data-ttu-id="6a61a-619">**URL di revoche di certificati**</span><span class="sxs-lookup"><span data-stu-id="6a61a-619">**CRL URLs**</span></span>|
|<span data-ttu-id="6a61a-620">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-620"></span></span>|
|<span data-ttu-id="6a61a-621">**URL OCSP**</span><span class="sxs-lookup"><span data-stu-id="6a61a-621">**OCSP URLs**</span></span>|
|<span data-ttu-id="6a61a-622">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-622"></span></span>|
   
 <span data-ttu-id="6a61a-623">**Affidare autorità di certificazione - L1C**</span><span class="sxs-lookup"><span data-stu-id="6a61a-623">**Entrust Certification Authority - L1C**</span></span>
  
||
|:-----|
|<span data-ttu-id="6a61a-624">**Oggetto**</span><span class="sxs-lookup"><span data-stu-id="6a61a-624">**Subject**</span></span>|
|<span data-ttu-id="6a61a-625">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-625"></span></span>|
|<span data-ttu-id="6a61a-626">**Autorità di certificazione**</span><span class="sxs-lookup"><span data-stu-id="6a61a-626">**Issuer**</span></span>|
|<span data-ttu-id="6a61a-627">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-627"></span></span>|
|<span data-ttu-id="6a61a-628">**Numero di serie**</span><span class="sxs-lookup"><span data-stu-id="6a61a-628">**Serial Number**</span></span>|
|<span data-ttu-id="6a61a-629">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-629"></span></span>|
|<span data-ttu-id="6a61a-630">**Lunghezza chiave pubblica**</span><span class="sxs-lookup"><span data-stu-id="6a61a-630">**Public Key Length**</span></span>|
|<span data-ttu-id="6a61a-631">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-631"></span></span>|
|<span data-ttu-id="6a61a-632">**Algoritmo di firma**</span><span class="sxs-lookup"><span data-stu-id="6a61a-632">**Signature Algorithm**</span></span>|
|<span data-ttu-id="6a61a-633">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-633"></span></span>|
|<span data-ttu-id="6a61a-634">**Validità non prima**</span><span class="sxs-lookup"><span data-stu-id="6a61a-634">**Validity Not Before**</span></span>|
|<span data-ttu-id="6a61a-635">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-635"></span></span>|
|<span data-ttu-id="6a61a-636">**Validità non dopo**</span><span class="sxs-lookup"><span data-stu-id="6a61a-636">**Validity Not After**</span></span>|
|<span data-ttu-id="6a61a-637">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-637"></span></span>|
|<span data-ttu-id="6a61a-638">**Identificatore chiave del soggetto**</span><span class="sxs-lookup"><span data-stu-id="6a61a-638">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="6a61a-639">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-639"></span></span>|
|<span data-ttu-id="6a61a-640">**Identificatore chiave dell'autorità**</span><span class="sxs-lookup"><span data-stu-id="6a61a-640">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="6a61a-641">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-641"></span></span>|
|<span data-ttu-id="6a61a-642">**Identificazione personale (SHA-1)**</span><span class="sxs-lookup"><span data-stu-id="6a61a-642">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="6a61a-643">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-643"></span></span>|
|<span data-ttu-id="6a61a-644">**Identificazione personale (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="6a61a-644">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="6a61a-645">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-645"></span></span>|
|<span data-ttu-id="6a61a-646">**PIN (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="6a61a-646">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="6a61a-647">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-647"></span></span>|
|<span data-ttu-id="6a61a-648">**URL di revoche di certificati**</span><span class="sxs-lookup"><span data-stu-id="6a61a-648">**CRL URLs**</span></span>|
|<span data-ttu-id="6a61a-649">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-649"></span></span>|
|<span data-ttu-id="6a61a-650">**URL OCSP**</span><span class="sxs-lookup"><span data-stu-id="6a61a-650">**OCSP URLs**</span></span>|
|<span data-ttu-id="6a61a-651">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-651"></span></span>|
   
 <span data-ttu-id="6a61a-652">**Affidare autorità di certificazione - L1K**</span><span class="sxs-lookup"><span data-stu-id="6a61a-652">**Entrust Certification Authority - L1K**</span></span>
  
||
|:-----|
|<span data-ttu-id="6a61a-653">**Oggetto**</span><span class="sxs-lookup"><span data-stu-id="6a61a-653">**Subject**</span></span>|
|<span data-ttu-id="6a61a-654">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-654"></span></span>|
|<span data-ttu-id="6a61a-655">**Autorità di certificazione**</span><span class="sxs-lookup"><span data-stu-id="6a61a-655">**Issuer**</span></span>|
|<span data-ttu-id="6a61a-656">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-656"></span></span>|
|<span data-ttu-id="6a61a-657">**Numero di serie**</span><span class="sxs-lookup"><span data-stu-id="6a61a-657">**Serial Number**</span></span>|
|<span data-ttu-id="6a61a-658">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-658"></span></span>|
|<span data-ttu-id="6a61a-659">**Lunghezza chiave pubblica**</span><span class="sxs-lookup"><span data-stu-id="6a61a-659">**Public Key Length**</span></span>|
|<span data-ttu-id="6a61a-660">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-660"></span></span>|
|<span data-ttu-id="6a61a-661">**Algoritmo di firma**</span><span class="sxs-lookup"><span data-stu-id="6a61a-661">**Signature Algorithm**</span></span>|
|<span data-ttu-id="6a61a-662">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-662"></span></span>|
|<span data-ttu-id="6a61a-663">**Validità non prima**</span><span class="sxs-lookup"><span data-stu-id="6a61a-663">**Validity Not Before**</span></span>|
|<span data-ttu-id="6a61a-664">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-664"></span></span>|
|<span data-ttu-id="6a61a-665">**Validità non dopo**</span><span class="sxs-lookup"><span data-stu-id="6a61a-665">**Validity Not After**</span></span>|
|<span data-ttu-id="6a61a-666">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-666"></span></span>|
|<span data-ttu-id="6a61a-667">**Identificatore chiave del soggetto**</span><span class="sxs-lookup"><span data-stu-id="6a61a-667">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="6a61a-668">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-668"></span></span>|
|<span data-ttu-id="6a61a-669">**Identificatore chiave dell'autorità**</span><span class="sxs-lookup"><span data-stu-id="6a61a-669">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="6a61a-670">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-670"></span></span>|
|<span data-ttu-id="6a61a-671">**Identificazione personale (SHA-1)**</span><span class="sxs-lookup"><span data-stu-id="6a61a-671">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="6a61a-672">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-672"></span></span>|
|<span data-ttu-id="6a61a-673">**Identificazione personale (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="6a61a-673">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="6a61a-674">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-674"></span></span>|
|<span data-ttu-id="6a61a-675">**PIN (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="6a61a-675">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="6a61a-676">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-676"></span></span>|
|<span data-ttu-id="6a61a-677">**URL di revoche di certificati**</span><span class="sxs-lookup"><span data-stu-id="6a61a-677">**CRL URLs**</span></span>|
|<span data-ttu-id="6a61a-678">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-678"></span></span>|
|<span data-ttu-id="6a61a-679">**URL OCSP**</span><span class="sxs-lookup"><span data-stu-id="6a61a-679">**OCSP URLs**</span></span>|
|<span data-ttu-id="6a61a-680">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-680"></span></span>|
   
 <span data-ttu-id="6a61a-681">**GlobalSign**</span><span class="sxs-lookup"><span data-stu-id="6a61a-681">**GlobalSign**</span></span>
  
||
|:-----|
|<span data-ttu-id="6a61a-682">**Oggetto**</span><span class="sxs-lookup"><span data-stu-id="6a61a-682">**Subject**</span></span>|
|<span data-ttu-id="6a61a-683">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-683"></span></span>|
|<span data-ttu-id="6a61a-684">**Autorità di certificazione**</span><span class="sxs-lookup"><span data-stu-id="6a61a-684">**Issuer**</span></span>|
|<span data-ttu-id="6a61a-685">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-685"></span></span>|
|<span data-ttu-id="6a61a-686">**Numero di serie**</span><span class="sxs-lookup"><span data-stu-id="6a61a-686">**Serial Number**</span></span>|
|<span data-ttu-id="6a61a-687">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-687"></span></span>|
|<span data-ttu-id="6a61a-688">**Lunghezza chiave pubblica**</span><span class="sxs-lookup"><span data-stu-id="6a61a-688">**Public Key Length**</span></span>|
|<span data-ttu-id="6a61a-689">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-689"></span></span>|
|<span data-ttu-id="6a61a-690">**Algoritmo di firma**</span><span class="sxs-lookup"><span data-stu-id="6a61a-690">**Signature Algorithm**</span></span>|
|<span data-ttu-id="6a61a-691">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-691"></span></span>|
|<span data-ttu-id="6a61a-692">**Validità non prima**</span><span class="sxs-lookup"><span data-stu-id="6a61a-692">**Validity Not Before**</span></span>|
|<span data-ttu-id="6a61a-693">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-693"></span></span>|
|<span data-ttu-id="6a61a-694">**Validità non dopo**</span><span class="sxs-lookup"><span data-stu-id="6a61a-694">**Validity Not After**</span></span>|
|<span data-ttu-id="6a61a-695">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-695"></span></span>|
|<span data-ttu-id="6a61a-696">**Identificatore chiave del soggetto**</span><span class="sxs-lookup"><span data-stu-id="6a61a-696">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="6a61a-697">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-697"></span></span>|
|<span data-ttu-id="6a61a-698">**Identificatore chiave dell'autorità**</span><span class="sxs-lookup"><span data-stu-id="6a61a-698">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="6a61a-699">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-699"></span></span>|
|<span data-ttu-id="6a61a-700">**Identificazione personale (SHA-1)**</span><span class="sxs-lookup"><span data-stu-id="6a61a-700">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="6a61a-701">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-701"></span></span>|
|<span data-ttu-id="6a61a-702">**Identificazione personale (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="6a61a-702">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="6a61a-703">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-703"></span></span>|
|<span data-ttu-id="6a61a-704">**PIN (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="6a61a-704">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="6a61a-705">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-705"></span></span>|
|<span data-ttu-id="6a61a-706">**URL di revoche di certificati**</span><span class="sxs-lookup"><span data-stu-id="6a61a-706">**CRL URLs**</span></span>|
|<span data-ttu-id="6a61a-707">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-707"></span></span>|
|<span data-ttu-id="6a61a-708">**URL OCSP**</span><span class="sxs-lookup"><span data-stu-id="6a61a-708">**OCSP URLs**</span></span>|
|<span data-ttu-id="6a61a-709">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-709"></span></span>|
   
 <span data-ttu-id="6a61a-710">**Versione estesa di convalida CA - SHA256 - G2 GlobalSign**</span><span class="sxs-lookup"><span data-stu-id="6a61a-710">**GlobalSign Extended Validation CA - SHA256 - G2**</span></span>
  
||
|:-----|
|<span data-ttu-id="6a61a-711">**Oggetto**</span><span class="sxs-lookup"><span data-stu-id="6a61a-711">**Subject**</span></span>|
|<span data-ttu-id="6a61a-712">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-712"></span></span>|
|<span data-ttu-id="6a61a-713">**Autorità di certificazione**</span><span class="sxs-lookup"><span data-stu-id="6a61a-713">**Issuer**</span></span>|
|<span data-ttu-id="6a61a-714">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-714"></span></span>|
|<span data-ttu-id="6a61a-715">**Numero di serie**</span><span class="sxs-lookup"><span data-stu-id="6a61a-715">**Serial Number**</span></span>|
|<span data-ttu-id="6a61a-716">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-716"></span></span>|
|<span data-ttu-id="6a61a-717">**Lunghezza chiave pubblica**</span><span class="sxs-lookup"><span data-stu-id="6a61a-717">**Public Key Length**</span></span>|
|<span data-ttu-id="6a61a-718">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-718"></span></span>|
|<span data-ttu-id="6a61a-719">**Algoritmo di firma**</span><span class="sxs-lookup"><span data-stu-id="6a61a-719">**Signature Algorithm**</span></span>|
|<span data-ttu-id="6a61a-720">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-720"></span></span>|
|<span data-ttu-id="6a61a-721">**Validità non prima**</span><span class="sxs-lookup"><span data-stu-id="6a61a-721">**Validity Not Before**</span></span>|
|<span data-ttu-id="6a61a-722">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-722"></span></span>|
|<span data-ttu-id="6a61a-723">**Validità non dopo**</span><span class="sxs-lookup"><span data-stu-id="6a61a-723">**Validity Not After**</span></span>|
|<span data-ttu-id="6a61a-724">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-724"></span></span>|
|<span data-ttu-id="6a61a-725">**Identificatore chiave del soggetto**</span><span class="sxs-lookup"><span data-stu-id="6a61a-725">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="6a61a-726">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-726"></span></span>|
|<span data-ttu-id="6a61a-727">**Identificatore chiave dell'autorità**</span><span class="sxs-lookup"><span data-stu-id="6a61a-727">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="6a61a-728">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-728"></span></span>|
|<span data-ttu-id="6a61a-729">**Identificazione personale (SHA-1)**</span><span class="sxs-lookup"><span data-stu-id="6a61a-729">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="6a61a-730">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-730"></span></span>|
|<span data-ttu-id="6a61a-731">**Identificazione personale (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="6a61a-731">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="6a61a-732">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-732"></span></span>|
|<span data-ttu-id="6a61a-733">**PIN (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="6a61a-733">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="6a61a-734">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-734"></span></span>|
|<span data-ttu-id="6a61a-735">**URL di revoche di certificati**</span><span class="sxs-lookup"><span data-stu-id="6a61a-735">**CRL URLs**</span></span>|
|<span data-ttu-id="6a61a-736">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-736"></span></span>|
|<span data-ttu-id="6a61a-737">**URL OCSP**</span><span class="sxs-lookup"><span data-stu-id="6a61a-737">**OCSP URLs**</span></span>|
|<span data-ttu-id="6a61a-738">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-738"></span></span>|
   
 <span data-ttu-id="6a61a-739">**Versione estesa di convalida CA - SHA256 - G3 GlobalSign**</span><span class="sxs-lookup"><span data-stu-id="6a61a-739">**GlobalSign Extended Validation CA - SHA256 - G3**</span></span>
  
||
|:-----|
|<span data-ttu-id="6a61a-740">**Oggetto**</span><span class="sxs-lookup"><span data-stu-id="6a61a-740">**Subject**</span></span>|
|<span data-ttu-id="6a61a-741">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-741"></span></span>|
|<span data-ttu-id="6a61a-742">**Autorità di certificazione**</span><span class="sxs-lookup"><span data-stu-id="6a61a-742">**Issuer**</span></span>|
|<span data-ttu-id="6a61a-743">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-743"></span></span>|
|<span data-ttu-id="6a61a-744">**Numero di serie**</span><span class="sxs-lookup"><span data-stu-id="6a61a-744">**Serial Number**</span></span>|
|<span data-ttu-id="6a61a-745">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-745"></span></span>|
|<span data-ttu-id="6a61a-746">**Lunghezza chiave pubblica**</span><span class="sxs-lookup"><span data-stu-id="6a61a-746">**Public Key Length**</span></span>|
|<span data-ttu-id="6a61a-747">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-747"></span></span>|
|<span data-ttu-id="6a61a-748">**Algoritmo di firma**</span><span class="sxs-lookup"><span data-stu-id="6a61a-748">**Signature Algorithm**</span></span>|
|<span data-ttu-id="6a61a-749">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-749"></span></span>|
|<span data-ttu-id="6a61a-750">**Validità non prima**</span><span class="sxs-lookup"><span data-stu-id="6a61a-750">**Validity Not Before**</span></span>|
|<span data-ttu-id="6a61a-751">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-751"></span></span>|
|<span data-ttu-id="6a61a-752">**Validità non dopo**</span><span class="sxs-lookup"><span data-stu-id="6a61a-752">**Validity Not After**</span></span>|
|<span data-ttu-id="6a61a-753">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-753"></span></span>|
|<span data-ttu-id="6a61a-754">**Identificatore chiave del soggetto**</span><span class="sxs-lookup"><span data-stu-id="6a61a-754">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="6a61a-755">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-755"></span></span>|
|<span data-ttu-id="6a61a-756">**Identificatore chiave dell'autorità**</span><span class="sxs-lookup"><span data-stu-id="6a61a-756">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="6a61a-757">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-757"></span></span>|
|<span data-ttu-id="6a61a-758">**Identificazione personale (SHA-1)**</span><span class="sxs-lookup"><span data-stu-id="6a61a-758">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="6a61a-759">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-759"></span></span>|
|<span data-ttu-id="6a61a-760">**Identificazione personale (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="6a61a-760">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="6a61a-761">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-761"></span></span>|
|<span data-ttu-id="6a61a-762">**PIN (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="6a61a-762">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="6a61a-763">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-763"></span></span>|
|<span data-ttu-id="6a61a-764">**URL di revoche di certificati**</span><span class="sxs-lookup"><span data-stu-id="6a61a-764">**CRL URLs**</span></span>|
|<span data-ttu-id="6a61a-765">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-765"></span></span>|
|<span data-ttu-id="6a61a-766">**URL OCSP**</span><span class="sxs-lookup"><span data-stu-id="6a61a-766">**OCSP URLs**</span></span>|
|<span data-ttu-id="6a61a-767">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-767"></span></span>|
   
 <span data-ttu-id="6a61a-768">**GlobalSign organizzazione convalida CA - SHA256 - G2**</span><span class="sxs-lookup"><span data-stu-id="6a61a-768">**GlobalSign Organization Validation CA - SHA256 - G2**</span></span>
  
||
|:-----|
|<span data-ttu-id="6a61a-769">**Oggetto**</span><span class="sxs-lookup"><span data-stu-id="6a61a-769">**Subject**</span></span>|
|<span data-ttu-id="6a61a-770">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-770"></span></span>|
|<span data-ttu-id="6a61a-771">**Autorità di certificazione**</span><span class="sxs-lookup"><span data-stu-id="6a61a-771">**Issuer**</span></span>|
|<span data-ttu-id="6a61a-772">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-772"></span></span>|
|<span data-ttu-id="6a61a-773">**Numero di serie**</span><span class="sxs-lookup"><span data-stu-id="6a61a-773">**Serial Number**</span></span>|
|<span data-ttu-id="6a61a-774">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-774"></span></span>|
|<span data-ttu-id="6a61a-775">**Lunghezza chiave pubblica**</span><span class="sxs-lookup"><span data-stu-id="6a61a-775">**Public Key Length**</span></span>|
|<span data-ttu-id="6a61a-776">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-776"></span></span>|
|<span data-ttu-id="6a61a-777">**Algoritmo di firma**</span><span class="sxs-lookup"><span data-stu-id="6a61a-777">**Signature Algorithm**</span></span>|
|<span data-ttu-id="6a61a-778">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-778"></span></span>|
|<span data-ttu-id="6a61a-779">**Validità non prima**</span><span class="sxs-lookup"><span data-stu-id="6a61a-779">**Validity Not Before**</span></span>|
|<span data-ttu-id="6a61a-780">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-780"></span></span>|
|<span data-ttu-id="6a61a-781">**Validità non dopo**</span><span class="sxs-lookup"><span data-stu-id="6a61a-781">**Validity Not After**</span></span>|
|<span data-ttu-id="6a61a-782">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-782"></span></span>|
|<span data-ttu-id="6a61a-783">**Identificatore chiave del soggetto**</span><span class="sxs-lookup"><span data-stu-id="6a61a-783">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="6a61a-784">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-784"></span></span>|
|<span data-ttu-id="6a61a-785">**Identificatore chiave dell'autorità**</span><span class="sxs-lookup"><span data-stu-id="6a61a-785">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="6a61a-786">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-786"></span></span>|
|<span data-ttu-id="6a61a-787">**Identificazione personale (SHA-1)**</span><span class="sxs-lookup"><span data-stu-id="6a61a-787">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="6a61a-788">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-788"></span></span>|
|<span data-ttu-id="6a61a-789">**Identificazione personale (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="6a61a-789">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="6a61a-790">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-790"></span></span>|
|<span data-ttu-id="6a61a-791">**PIN (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="6a61a-791">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="6a61a-792">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-792"></span></span>|
|<span data-ttu-id="6a61a-793">**URL di revoche di certificati**</span><span class="sxs-lookup"><span data-stu-id="6a61a-793">**CRL URLs**</span></span>|
|<span data-ttu-id="6a61a-794">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-794"></span></span>|
|<span data-ttu-id="6a61a-795">**URL OCSP**</span><span class="sxs-lookup"><span data-stu-id="6a61a-795">**OCSP URLs**</span></span>|
|<span data-ttu-id="6a61a-796">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-796"></span></span>|
   
 <span data-ttu-id="6a61a-797">**GlobalSign organizzazione convalida CA - SHA256 - G2**</span><span class="sxs-lookup"><span data-stu-id="6a61a-797">**GlobalSign Organization Validation CA - SHA256 - G2**</span></span>
  
||
|:-----|
|<span data-ttu-id="6a61a-798">**Oggetto**</span><span class="sxs-lookup"><span data-stu-id="6a61a-798">**Subject**</span></span>|
|<span data-ttu-id="6a61a-799">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-799"></span></span>|
|<span data-ttu-id="6a61a-800">**Autorità di certificazione**</span><span class="sxs-lookup"><span data-stu-id="6a61a-800">**Issuer**</span></span>|
|<span data-ttu-id="6a61a-801">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-801"></span></span>|
|<span data-ttu-id="6a61a-802">**Numero di serie**</span><span class="sxs-lookup"><span data-stu-id="6a61a-802">**Serial Number**</span></span>|
|<span data-ttu-id="6a61a-803">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-803"></span></span>|
|<span data-ttu-id="6a61a-804">**Lunghezza chiave pubblica**</span><span class="sxs-lookup"><span data-stu-id="6a61a-804">**Public Key Length**</span></span>|
|<span data-ttu-id="6a61a-805">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-805"></span></span>|
|<span data-ttu-id="6a61a-806">**Algoritmo di firma**</span><span class="sxs-lookup"><span data-stu-id="6a61a-806">**Signature Algorithm**</span></span>|
|<span data-ttu-id="6a61a-807">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-807"></span></span>|
|<span data-ttu-id="6a61a-808">**Validità non prima**</span><span class="sxs-lookup"><span data-stu-id="6a61a-808">**Validity Not Before**</span></span>|
|<span data-ttu-id="6a61a-809">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-809"></span></span>|
|<span data-ttu-id="6a61a-810">**Validità non dopo**</span><span class="sxs-lookup"><span data-stu-id="6a61a-810">**Validity Not After**</span></span>|
|<span data-ttu-id="6a61a-811">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-811"></span></span>|
|<span data-ttu-id="6a61a-812">**Identificatore chiave del soggetto**</span><span class="sxs-lookup"><span data-stu-id="6a61a-812">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="6a61a-813">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-813"></span></span>|
|<span data-ttu-id="6a61a-814">**Identificatore chiave dell'autorità**</span><span class="sxs-lookup"><span data-stu-id="6a61a-814">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="6a61a-815">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-815"></span></span>|
|<span data-ttu-id="6a61a-816">**Identificazione personale (SHA-1)**</span><span class="sxs-lookup"><span data-stu-id="6a61a-816">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="6a61a-817">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-817"></span></span>|
|<span data-ttu-id="6a61a-818">**Identificazione personale (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="6a61a-818">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="6a61a-819">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-819"></span></span>|
|<span data-ttu-id="6a61a-820">**PIN (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="6a61a-820">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="6a61a-821">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-821"></span></span>|
|<span data-ttu-id="6a61a-822">**URL di revoche di certificati**</span><span class="sxs-lookup"><span data-stu-id="6a61a-822">**CRL URLs**</span></span>|
|<span data-ttu-id="6a61a-823">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-823"></span></span>|
|<span data-ttu-id="6a61a-824">**URL OCSP**</span><span class="sxs-lookup"><span data-stu-id="6a61a-824">**OCSP URLs**</span></span>|
|<span data-ttu-id="6a61a-825">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-825"></span></span>|
   
 <span data-ttu-id="6a61a-826">**Crittografare possiamo autorità X3**</span><span class="sxs-lookup"><span data-stu-id="6a61a-826">**Let's Encrypt Authority X3**</span></span>
  
||
|:-----|
|<span data-ttu-id="6a61a-827">**Oggetto**</span><span class="sxs-lookup"><span data-stu-id="6a61a-827">**Subject**</span></span>|
|<span data-ttu-id="6a61a-828">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-828"></span></span>|
|<span data-ttu-id="6a61a-829">**Autorità di certificazione**</span><span class="sxs-lookup"><span data-stu-id="6a61a-829">**Issuer**</span></span>|
|<span data-ttu-id="6a61a-830">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-830"></span></span>|
|<span data-ttu-id="6a61a-831">**Numero di serie**</span><span class="sxs-lookup"><span data-stu-id="6a61a-831">**Serial Number**</span></span>|
|<span data-ttu-id="6a61a-832">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-832"></span></span>|
|<span data-ttu-id="6a61a-833">**Lunghezza chiave pubblica**</span><span class="sxs-lookup"><span data-stu-id="6a61a-833">**Public Key Length**</span></span>|
|<span data-ttu-id="6a61a-834">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-834"></span></span>|
|<span data-ttu-id="6a61a-835">**Algoritmo di firma**</span><span class="sxs-lookup"><span data-stu-id="6a61a-835">**Signature Algorithm**</span></span>|
|<span data-ttu-id="6a61a-836">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-836"></span></span>|
|<span data-ttu-id="6a61a-837">**Validità non prima**</span><span class="sxs-lookup"><span data-stu-id="6a61a-837">**Validity Not Before**</span></span>|
|<span data-ttu-id="6a61a-838">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-838"></span></span>|
|<span data-ttu-id="6a61a-839">**Validità non dopo**</span><span class="sxs-lookup"><span data-stu-id="6a61a-839">**Validity Not After**</span></span>|
|<span data-ttu-id="6a61a-840">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-840"></span></span>|
|<span data-ttu-id="6a61a-841">**Identificatore chiave del soggetto**</span><span class="sxs-lookup"><span data-stu-id="6a61a-841">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="6a61a-842">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-842"></span></span>|
|<span data-ttu-id="6a61a-843">**Identificatore chiave dell'autorità**</span><span class="sxs-lookup"><span data-stu-id="6a61a-843">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="6a61a-844">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-844"></span></span>|
|<span data-ttu-id="6a61a-845">**Identificazione personale (SHA-1)**</span><span class="sxs-lookup"><span data-stu-id="6a61a-845">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="6a61a-846">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-846"></span></span>|
|<span data-ttu-id="6a61a-847">**Identificazione personale (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="6a61a-847">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="6a61a-848">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-848"></span></span>|
|<span data-ttu-id="6a61a-849">**PIN (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="6a61a-849">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="6a61a-850">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-850"></span></span>|
|<span data-ttu-id="6a61a-851">**URL AIA**</span><span class="sxs-lookup"><span data-stu-id="6a61a-851">**AIA URLs**</span></span>|
|<span data-ttu-id="6a61a-852">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-852"></span></span>|
|<span data-ttu-id="6a61a-853">**URL di revoche di certificati**</span><span class="sxs-lookup"><span data-stu-id="6a61a-853">**CRL URLs**</span></span>|
|<span data-ttu-id="6a61a-854">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-854"></span></span>|
|<span data-ttu-id="6a61a-855">**URL OCSP**</span><span class="sxs-lookup"><span data-stu-id="6a61a-855">**OCSP URLs**</span></span>|
|<span data-ttu-id="6a61a-856">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-856"></span></span>|
   
 <span data-ttu-id="6a61a-857">**Microsoft IT SSL SHA2**</span><span class="sxs-lookup"><span data-stu-id="6a61a-857">**Microsoft IT SSL SHA2**</span></span>
  
||
|:-----|
|<span data-ttu-id="6a61a-858">**Oggetto**</span><span class="sxs-lookup"><span data-stu-id="6a61a-858">**Subject**</span></span>|
|<span data-ttu-id="6a61a-859">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-859"></span></span>|
|<span data-ttu-id="6a61a-860">**Autorità di certificazione**</span><span class="sxs-lookup"><span data-stu-id="6a61a-860">**Issuer**</span></span>|
|<span data-ttu-id="6a61a-861">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-861"></span></span>|
|<span data-ttu-id="6a61a-862">**Numero di serie**</span><span class="sxs-lookup"><span data-stu-id="6a61a-862">**Serial Number**</span></span>|
|<span data-ttu-id="6a61a-863">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-863"></span></span>|
|<span data-ttu-id="6a61a-864">**Lunghezza chiave pubblica**</span><span class="sxs-lookup"><span data-stu-id="6a61a-864">**Public Key Length**</span></span>|
|<span data-ttu-id="6a61a-865">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-865"></span></span>|
|<span data-ttu-id="6a61a-866">**Algoritmo di firma**</span><span class="sxs-lookup"><span data-stu-id="6a61a-866">**Signature Algorithm**</span></span>|
|<span data-ttu-id="6a61a-867">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-867"></span></span>|
|<span data-ttu-id="6a61a-868">**Validità non prima**</span><span class="sxs-lookup"><span data-stu-id="6a61a-868">**Validity Not Before**</span></span>|
|<span data-ttu-id="6a61a-869">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-869"></span></span>|
|<span data-ttu-id="6a61a-870">**Validità non dopo**</span><span class="sxs-lookup"><span data-stu-id="6a61a-870">**Validity Not After**</span></span>|
|<span data-ttu-id="6a61a-871">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-871"></span></span>|
|<span data-ttu-id="6a61a-872">**Identificatore chiave del soggetto**</span><span class="sxs-lookup"><span data-stu-id="6a61a-872">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="6a61a-873">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-873"></span></span>|
|<span data-ttu-id="6a61a-874">**Identificatore chiave dell'autorità**</span><span class="sxs-lookup"><span data-stu-id="6a61a-874">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="6a61a-875">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-875"></span></span>|
|<span data-ttu-id="6a61a-876">**Identificazione personale (SHA-1)**</span><span class="sxs-lookup"><span data-stu-id="6a61a-876">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="6a61a-877">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-877"></span></span>|
|<span data-ttu-id="6a61a-878">**Identificazione personale (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="6a61a-878">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="6a61a-879">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-879"></span></span>|
|<span data-ttu-id="6a61a-880">**PIN (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="6a61a-880">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="6a61a-881">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-881"></span></span>|
|<span data-ttu-id="6a61a-882">**URL di revoche di certificati**</span><span class="sxs-lookup"><span data-stu-id="6a61a-882">**CRL URLs**</span></span>|
|<span data-ttu-id="6a61a-883">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-883"></span></span>|
   
 <span data-ttu-id="6a61a-884">**Microsoft IT SSL SHA2**</span><span class="sxs-lookup"><span data-stu-id="6a61a-884">**Microsoft IT SSL SHA2**</span></span>
  
||
|:-----|
|<span data-ttu-id="6a61a-885">**Oggetto**</span><span class="sxs-lookup"><span data-stu-id="6a61a-885">**Subject**</span></span>|
|<span data-ttu-id="6a61a-886">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-886"></span></span>|
|<span data-ttu-id="6a61a-887">**Autorità di certificazione**</span><span class="sxs-lookup"><span data-stu-id="6a61a-887">**Issuer**</span></span>|
|<span data-ttu-id="6a61a-888">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-888"></span></span>|
|<span data-ttu-id="6a61a-889">**Numero di serie**</span><span class="sxs-lookup"><span data-stu-id="6a61a-889">**Serial Number**</span></span>|
|<span data-ttu-id="6a61a-890">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-890"></span></span>|
|<span data-ttu-id="6a61a-891">**Lunghezza chiave pubblica**</span><span class="sxs-lookup"><span data-stu-id="6a61a-891">**Public Key Length**</span></span>|
|<span data-ttu-id="6a61a-892">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-892"></span></span>|
|<span data-ttu-id="6a61a-893">**Algoritmo di firma**</span><span class="sxs-lookup"><span data-stu-id="6a61a-893">**Signature Algorithm**</span></span>|
|<span data-ttu-id="6a61a-894">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-894"></span></span>|
|<span data-ttu-id="6a61a-895">**Validità non prima**</span><span class="sxs-lookup"><span data-stu-id="6a61a-895">**Validity Not Before**</span></span>|
|<span data-ttu-id="6a61a-896">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-896"></span></span>|
|<span data-ttu-id="6a61a-897">**Validità non dopo**</span><span class="sxs-lookup"><span data-stu-id="6a61a-897">**Validity Not After**</span></span>|
|<span data-ttu-id="6a61a-898">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-898"></span></span>|
|<span data-ttu-id="6a61a-899">**Identificatore chiave del soggetto**</span><span class="sxs-lookup"><span data-stu-id="6a61a-899">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="6a61a-900">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-900"></span></span>|
|<span data-ttu-id="6a61a-901">**Identificatore chiave dell'autorità**</span><span class="sxs-lookup"><span data-stu-id="6a61a-901">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="6a61a-902">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-902"></span></span>|
|<span data-ttu-id="6a61a-903">**Identificazione personale (SHA-1)**</span><span class="sxs-lookup"><span data-stu-id="6a61a-903">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="6a61a-904">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-904"></span></span>|
|<span data-ttu-id="6a61a-905">**Identificazione personale (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="6a61a-905">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="6a61a-906">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-906"></span></span>|
|<span data-ttu-id="6a61a-907">**PIN (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="6a61a-907">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="6a61a-908">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-908"></span></span>|
|<span data-ttu-id="6a61a-909">**URL di revoche di certificati**</span><span class="sxs-lookup"><span data-stu-id="6a61a-909">**CRL URLs**</span></span>|
|<span data-ttu-id="6a61a-910">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-910"></span></span>|
|<span data-ttu-id="6a61a-911">**URL OCSP**</span><span class="sxs-lookup"><span data-stu-id="6a61a-911">**OCSP URLs**</span></span>|
|<span data-ttu-id="6a61a-912">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-912"></span></span>|
   
 <span data-ttu-id="6a61a-913">**Microsoft IT TLS CA 1**</span><span class="sxs-lookup"><span data-stu-id="6a61a-913">**Microsoft IT TLS CA 1**</span></span>
  
||
|:-----|
|<span data-ttu-id="6a61a-914">**Oggetto**</span><span class="sxs-lookup"><span data-stu-id="6a61a-914">**Subject**</span></span>|
|<span data-ttu-id="6a61a-915">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-915"></span></span>|
|<span data-ttu-id="6a61a-916">**Autorità di certificazione**</span><span class="sxs-lookup"><span data-stu-id="6a61a-916">**Issuer**</span></span>|
|<span data-ttu-id="6a61a-917">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-917"></span></span>|
|<span data-ttu-id="6a61a-918">**Numero di serie**</span><span class="sxs-lookup"><span data-stu-id="6a61a-918">**Serial Number**</span></span>|
|<span data-ttu-id="6a61a-919">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-919"></span></span>|
|<span data-ttu-id="6a61a-920">**Lunghezza chiave pubblica**</span><span class="sxs-lookup"><span data-stu-id="6a61a-920">**Public Key Length**</span></span>|
|<span data-ttu-id="6a61a-921">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-921"></span></span>|
|<span data-ttu-id="6a61a-922">**Algoritmo di firma**</span><span class="sxs-lookup"><span data-stu-id="6a61a-922">**Signature Algorithm**</span></span>|
|<span data-ttu-id="6a61a-923">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-923"></span></span>|
|<span data-ttu-id="6a61a-924">**Validità non prima**</span><span class="sxs-lookup"><span data-stu-id="6a61a-924">**Validity Not Before**</span></span>|
|<span data-ttu-id="6a61a-925">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-925"></span></span>|
|<span data-ttu-id="6a61a-926">**Validità non dopo**</span><span class="sxs-lookup"><span data-stu-id="6a61a-926">**Validity Not After**</span></span>|
|<span data-ttu-id="6a61a-927">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-927"></span></span>|
|<span data-ttu-id="6a61a-928">**Identificatore chiave del soggetto**</span><span class="sxs-lookup"><span data-stu-id="6a61a-928">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="6a61a-929">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-929"></span></span>|
|<span data-ttu-id="6a61a-930">**Identificatore chiave dell'autorità**</span><span class="sxs-lookup"><span data-stu-id="6a61a-930">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="6a61a-931">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-931"></span></span>|
|<span data-ttu-id="6a61a-932">**Identificazione personale (SHA-1)**</span><span class="sxs-lookup"><span data-stu-id="6a61a-932">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="6a61a-933">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-933"></span></span>|
|<span data-ttu-id="6a61a-934">**Identificazione personale (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="6a61a-934">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="6a61a-935">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-935"></span></span>|
|<span data-ttu-id="6a61a-936">**PIN (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="6a61a-936">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="6a61a-937">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-937"></span></span>|
|<span data-ttu-id="6a61a-938">**URL di revoche di certificati**</span><span class="sxs-lookup"><span data-stu-id="6a61a-938">**CRL URLs**</span></span>|
|<span data-ttu-id="6a61a-939">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-939"></span></span>|
|<span data-ttu-id="6a61a-940">**URL OCSP**</span><span class="sxs-lookup"><span data-stu-id="6a61a-940">**OCSP URLs**</span></span>|
|<span data-ttu-id="6a61a-941">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-941"></span></span>|
   
 <span data-ttu-id="6a61a-942">**Microsoft IT TLS CA 2**</span><span class="sxs-lookup"><span data-stu-id="6a61a-942">**Microsoft IT TLS CA 2**</span></span>
  
||
|:-----|
|<span data-ttu-id="6a61a-943">**Oggetto**</span><span class="sxs-lookup"><span data-stu-id="6a61a-943">**Subject**</span></span>|
|<span data-ttu-id="6a61a-944">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-944"></span></span>|
|<span data-ttu-id="6a61a-945">**Autorità di certificazione**</span><span class="sxs-lookup"><span data-stu-id="6a61a-945">**Issuer**</span></span>|
|<span data-ttu-id="6a61a-946">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-946"></span></span>|
|<span data-ttu-id="6a61a-947">**Numero di serie**</span><span class="sxs-lookup"><span data-stu-id="6a61a-947">**Serial Number**</span></span>|
|<span data-ttu-id="6a61a-948">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-948"></span></span>|
|<span data-ttu-id="6a61a-949">**Lunghezza chiave pubblica**</span><span class="sxs-lookup"><span data-stu-id="6a61a-949">**Public Key Length**</span></span>|
|<span data-ttu-id="6a61a-950">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-950"></span></span>|
|<span data-ttu-id="6a61a-951">**Algoritmo di firma**</span><span class="sxs-lookup"><span data-stu-id="6a61a-951">**Signature Algorithm**</span></span>|
|<span data-ttu-id="6a61a-952">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-952"></span></span>|
|<span data-ttu-id="6a61a-953">**Validità non prima**</span><span class="sxs-lookup"><span data-stu-id="6a61a-953">**Validity Not Before**</span></span>|
|<span data-ttu-id="6a61a-954">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-954"></span></span>|
|<span data-ttu-id="6a61a-955">**Validità non dopo**</span><span class="sxs-lookup"><span data-stu-id="6a61a-955">**Validity Not After**</span></span>|
|<span data-ttu-id="6a61a-956">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-956"></span></span>|
|<span data-ttu-id="6a61a-957">**Identificatore chiave del soggetto**</span><span class="sxs-lookup"><span data-stu-id="6a61a-957">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="6a61a-958">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-958"></span></span>|
|<span data-ttu-id="6a61a-959">**Identificatore chiave dell'autorità**</span><span class="sxs-lookup"><span data-stu-id="6a61a-959">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="6a61a-960">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-960"></span></span>|
|<span data-ttu-id="6a61a-961">**Identificazione personale (SHA-1)**</span><span class="sxs-lookup"><span data-stu-id="6a61a-961">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="6a61a-962">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-962"></span></span>|
|<span data-ttu-id="6a61a-963">**Identificazione personale (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="6a61a-963">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="6a61a-964">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-964"></span></span>|
|<span data-ttu-id="6a61a-965">**PIN (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="6a61a-965">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="6a61a-966">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-966"></span></span>|
|<span data-ttu-id="6a61a-967">**URL di revoche di certificati**</span><span class="sxs-lookup"><span data-stu-id="6a61a-967">**CRL URLs**</span></span>|
|<span data-ttu-id="6a61a-968">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-968"></span></span>|
|<span data-ttu-id="6a61a-969">**URL OCSP**</span><span class="sxs-lookup"><span data-stu-id="6a61a-969">**OCSP URLs**</span></span>|
|<span data-ttu-id="6a61a-970">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-970"></span></span>|
   
 <span data-ttu-id="6a61a-971">**Microsoft IT TLS CA 4**</span><span class="sxs-lookup"><span data-stu-id="6a61a-971">**Microsoft IT TLS CA 4**</span></span>
  
||
|:-----|
|<span data-ttu-id="6a61a-972">**Oggetto**</span><span class="sxs-lookup"><span data-stu-id="6a61a-972">**Subject**</span></span>|
|<span data-ttu-id="6a61a-973">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-973"></span></span>|
|<span data-ttu-id="6a61a-974">**Autorità di certificazione**</span><span class="sxs-lookup"><span data-stu-id="6a61a-974">**Issuer**</span></span>|
|<span data-ttu-id="6a61a-975">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-975"></span></span>|
|<span data-ttu-id="6a61a-976">**Numero di serie**</span><span class="sxs-lookup"><span data-stu-id="6a61a-976">**Serial Number**</span></span>|
|<span data-ttu-id="6a61a-977">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-977"></span></span>|
|<span data-ttu-id="6a61a-978">**Lunghezza chiave pubblica**</span><span class="sxs-lookup"><span data-stu-id="6a61a-978">**Public Key Length**</span></span>|
|<span data-ttu-id="6a61a-979">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-979"></span></span>|
|<span data-ttu-id="6a61a-980">**Algoritmo di firma**</span><span class="sxs-lookup"><span data-stu-id="6a61a-980">**Signature Algorithm**</span></span>|
|<span data-ttu-id="6a61a-981">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-981"></span></span>|
|<span data-ttu-id="6a61a-982">**Validità non prima**</span><span class="sxs-lookup"><span data-stu-id="6a61a-982">**Validity Not Before**</span></span>|
|<span data-ttu-id="6a61a-983">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-983"></span></span>|
|<span data-ttu-id="6a61a-984">**Validità non dopo**</span><span class="sxs-lookup"><span data-stu-id="6a61a-984">**Validity Not After**</span></span>|
|<span data-ttu-id="6a61a-985">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-985"></span></span>|
|<span data-ttu-id="6a61a-986">**Identificatore chiave del soggetto**</span><span class="sxs-lookup"><span data-stu-id="6a61a-986">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="6a61a-987">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-987"></span></span>|
|<span data-ttu-id="6a61a-988">**Identificatore chiave dell'autorità**</span><span class="sxs-lookup"><span data-stu-id="6a61a-988">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="6a61a-989">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-989"></span></span>|
|<span data-ttu-id="6a61a-990">**Identificazione personale (SHA-1)**</span><span class="sxs-lookup"><span data-stu-id="6a61a-990">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="6a61a-991">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-991"></span></span>|
|<span data-ttu-id="6a61a-992">**Identificazione personale (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="6a61a-992">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="6a61a-993">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-993"></span></span>|
|<span data-ttu-id="6a61a-994">**PIN (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="6a61a-994">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="6a61a-995">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-995"></span></span>|
|<span data-ttu-id="6a61a-996">**URL di revoche di certificati**</span><span class="sxs-lookup"><span data-stu-id="6a61a-996">**CRL URLs**</span></span>|
|<span data-ttu-id="6a61a-997">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-997"></span></span>|
|<span data-ttu-id="6a61a-998">**URL OCSP**</span><span class="sxs-lookup"><span data-stu-id="6a61a-998">**OCSP URLs**</span></span>|
|<span data-ttu-id="6a61a-999">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-999"></span></span>|
   
 <span data-ttu-id="6a61a-1000">**Microsoft IT TLS CA 5**</span><span class="sxs-lookup"><span data-stu-id="6a61a-1000">**Microsoft IT TLS CA 5**</span></span>
  
||
|:-----|
|<span data-ttu-id="6a61a-1001">**Oggetto**</span><span class="sxs-lookup"><span data-stu-id="6a61a-1001">**Subject**</span></span>|
|<span data-ttu-id="6a61a-1002">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-1002"></span></span>|
|<span data-ttu-id="6a61a-1003">**Autorità di certificazione**</span><span class="sxs-lookup"><span data-stu-id="6a61a-1003">**Issuer**</span></span>|
|<span data-ttu-id="6a61a-1004">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-1004"></span></span>|
|<span data-ttu-id="6a61a-1005">**Numero di serie**</span><span class="sxs-lookup"><span data-stu-id="6a61a-1005">**Serial Number**</span></span>|
|<span data-ttu-id="6a61a-1006">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-1006"></span></span>|
|<span data-ttu-id="6a61a-1007">**Lunghezza chiave pubblica**</span><span class="sxs-lookup"><span data-stu-id="6a61a-1007">**Public Key Length**</span></span>|
|<span data-ttu-id="6a61a-1008">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-1008"></span></span>|
|<span data-ttu-id="6a61a-1009">**Algoritmo di firma**</span><span class="sxs-lookup"><span data-stu-id="6a61a-1009">**Signature Algorithm**</span></span>|
|<span data-ttu-id="6a61a-1010">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-1010"></span></span>|
|<span data-ttu-id="6a61a-1011">**Validità non prima**</span><span class="sxs-lookup"><span data-stu-id="6a61a-1011">**Validity Not Before**</span></span>|
|<span data-ttu-id="6a61a-1012">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-1012"></span></span>|
|<span data-ttu-id="6a61a-1013">**Validità non dopo**</span><span class="sxs-lookup"><span data-stu-id="6a61a-1013">**Validity Not After**</span></span>|
|<span data-ttu-id="6a61a-1014">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-1014"></span></span>|
|<span data-ttu-id="6a61a-1015">**Identificatore chiave del soggetto**</span><span class="sxs-lookup"><span data-stu-id="6a61a-1015">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="6a61a-1016">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-1016"></span></span>|
|<span data-ttu-id="6a61a-1017">**Identificatore chiave dell'autorità**</span><span class="sxs-lookup"><span data-stu-id="6a61a-1017">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="6a61a-1018">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-1018"></span></span>|
|<span data-ttu-id="6a61a-1019">**Identificazione personale (SHA-1)**</span><span class="sxs-lookup"><span data-stu-id="6a61a-1019">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="6a61a-1020">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-1020"></span></span>|
|<span data-ttu-id="6a61a-1021">**Identificazione personale (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="6a61a-1021">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="6a61a-1022">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-1022"></span></span>|
|<span data-ttu-id="6a61a-1023">**PIN (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="6a61a-1023">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="6a61a-1024">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-1024"></span></span>|
|<span data-ttu-id="6a61a-1025">**URL di revoche di certificati**</span><span class="sxs-lookup"><span data-stu-id="6a61a-1025">**CRL URLs**</span></span>|
|<span data-ttu-id="6a61a-1026">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-1026"></span></span>|
|<span data-ttu-id="6a61a-1027">**URL OCSP**</span><span class="sxs-lookup"><span data-stu-id="6a61a-1027">**OCSP URLs**</span></span>|
|<span data-ttu-id="6a61a-1028">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-1028"></span></span>|
   
 <span data-ttu-id="6a61a-1029">**Classe Symantec EV 3 SSL CA - G3**</span><span class="sxs-lookup"><span data-stu-id="6a61a-1029">**Symantec Class 3 EV SSL CA - G3**</span></span>
  
||
|:-----|
|<span data-ttu-id="6a61a-1030">**Oggetto**</span><span class="sxs-lookup"><span data-stu-id="6a61a-1030">**Subject**</span></span>|
|<span data-ttu-id="6a61a-1031">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-1031"></span></span>|
|<span data-ttu-id="6a61a-1032">**Autorità di certificazione**</span><span class="sxs-lookup"><span data-stu-id="6a61a-1032">**Issuer**</span></span>|
|<span data-ttu-id="6a61a-1033">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-1033"></span></span>|
|<span data-ttu-id="6a61a-1034">**Nome alternativo soggetto**</span><span class="sxs-lookup"><span data-stu-id="6a61a-1034">**Subject Alternative Name**</span></span>|
|<span data-ttu-id="6a61a-1035">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-1035"></span></span>|
|<span data-ttu-id="6a61a-1036">**Numero di serie**</span><span class="sxs-lookup"><span data-stu-id="6a61a-1036">**Serial Number**</span></span>|
|<span data-ttu-id="6a61a-1037">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-1037"></span></span>|
|<span data-ttu-id="6a61a-1038">**Lunghezza chiave pubblica**</span><span class="sxs-lookup"><span data-stu-id="6a61a-1038">**Public Key Length**</span></span>|
|<span data-ttu-id="6a61a-1039">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-1039"></span></span>|
|<span data-ttu-id="6a61a-1040">**Algoritmo di firma**</span><span class="sxs-lookup"><span data-stu-id="6a61a-1040">**Signature Algorithm**</span></span>|
|<span data-ttu-id="6a61a-1041">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-1041"></span></span>|
|<span data-ttu-id="6a61a-1042">**Validità non prima**</span><span class="sxs-lookup"><span data-stu-id="6a61a-1042">**Validity Not Before**</span></span>|
|<span data-ttu-id="6a61a-1043">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-1043"></span></span>|
|<span data-ttu-id="6a61a-1044">**Validità non dopo**</span><span class="sxs-lookup"><span data-stu-id="6a61a-1044">**Validity Not After**</span></span>|
|<span data-ttu-id="6a61a-1045">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-1045"></span></span>|
|<span data-ttu-id="6a61a-1046">**Identificatore chiave del soggetto**</span><span class="sxs-lookup"><span data-stu-id="6a61a-1046">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="6a61a-1047">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-1047"></span></span>|
|<span data-ttu-id="6a61a-1048">**Identificatore chiave dell'autorità**</span><span class="sxs-lookup"><span data-stu-id="6a61a-1048">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="6a61a-1049">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-1049"></span></span>|
|<span data-ttu-id="6a61a-1050">**Identificazione personale (SHA-1)**</span><span class="sxs-lookup"><span data-stu-id="6a61a-1050">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="6a61a-1051">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-1051"></span></span>|
|<span data-ttu-id="6a61a-1052">**Identificazione personale (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="6a61a-1052">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="6a61a-1053">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-1053"></span></span>|
|<span data-ttu-id="6a61a-1054">**PIN (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="6a61a-1054">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="6a61a-1055">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-1055"></span></span>|
|<span data-ttu-id="6a61a-1056">**URL di revoche di certificati**</span><span class="sxs-lookup"><span data-stu-id="6a61a-1056">**CRL URLs**</span></span>|
|<span data-ttu-id="6a61a-1057">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-1057"></span></span>|
|<span data-ttu-id="6a61a-1058">**URL OCSP**</span><span class="sxs-lookup"><span data-stu-id="6a61a-1058">**OCSP URLs**</span></span>|
|<span data-ttu-id="6a61a-1059">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-1059"></span></span>|
   
 <span data-ttu-id="6a61a-1060">**Classe Symantec 3 Server protetta CA - G4**</span><span class="sxs-lookup"><span data-stu-id="6a61a-1060">**Symantec Class 3 Secure Server CA - G4**</span></span>
  
||
|:-----|
|<span data-ttu-id="6a61a-1061">**Oggetto**</span><span class="sxs-lookup"><span data-stu-id="6a61a-1061">**Subject**</span></span>|
|<span data-ttu-id="6a61a-1062">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-1062"></span></span>|
|<span data-ttu-id="6a61a-1063">**Autorità di certificazione**</span><span class="sxs-lookup"><span data-stu-id="6a61a-1063">**Issuer**</span></span>|
|<span data-ttu-id="6a61a-1064">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-1064"></span></span>|
|<span data-ttu-id="6a61a-1065">**Nome alternativo soggetto**</span><span class="sxs-lookup"><span data-stu-id="6a61a-1065">**Subject Alternative Name**</span></span>|
|<span data-ttu-id="6a61a-1066">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-1066"></span></span>|
|<span data-ttu-id="6a61a-1067">**Numero di serie**</span><span class="sxs-lookup"><span data-stu-id="6a61a-1067">**Serial Number**</span></span>|
|<span data-ttu-id="6a61a-1068">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-1068"></span></span>|
|<span data-ttu-id="6a61a-1069">**Lunghezza chiave pubblica**</span><span class="sxs-lookup"><span data-stu-id="6a61a-1069">**Public Key Length**</span></span>|
|<span data-ttu-id="6a61a-1070">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-1070"></span></span>|
|<span data-ttu-id="6a61a-1071">**Algoritmo di firma**</span><span class="sxs-lookup"><span data-stu-id="6a61a-1071">**Signature Algorithm**</span></span>|
|<span data-ttu-id="6a61a-1072">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-1072"></span></span>|
|<span data-ttu-id="6a61a-1073">**Validità non prima**</span><span class="sxs-lookup"><span data-stu-id="6a61a-1073">**Validity Not Before**</span></span>|
|<span data-ttu-id="6a61a-1074">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-1074"></span></span>|
|<span data-ttu-id="6a61a-1075">**Validità non dopo**</span><span class="sxs-lookup"><span data-stu-id="6a61a-1075">**Validity Not After**</span></span>|
|<span data-ttu-id="6a61a-1076">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-1076"></span></span>|
|<span data-ttu-id="6a61a-1077">**Identificatore chiave del soggetto**</span><span class="sxs-lookup"><span data-stu-id="6a61a-1077">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="6a61a-1078">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-1078"></span></span>|
|<span data-ttu-id="6a61a-1079">**Identificatore chiave dell'autorità**</span><span class="sxs-lookup"><span data-stu-id="6a61a-1079">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="6a61a-1080">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-1080"></span></span>|
|<span data-ttu-id="6a61a-1081">**Identificazione personale (SHA-1)**</span><span class="sxs-lookup"><span data-stu-id="6a61a-1081">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="6a61a-1082">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-1082"></span></span>|
|<span data-ttu-id="6a61a-1083">**Identificazione personale (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="6a61a-1083">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="6a61a-1084">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-1084"></span></span>|
|<span data-ttu-id="6a61a-1085">**PIN (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="6a61a-1085">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="6a61a-1086">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-1086"></span></span>|
|<span data-ttu-id="6a61a-1087">**URL di revoche di certificati**</span><span class="sxs-lookup"><span data-stu-id="6a61a-1087">**CRL URLs**</span></span>|
|<span data-ttu-id="6a61a-1088">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-1088"></span></span>|
|<span data-ttu-id="6a61a-1089">**URL OCSP**</span><span class="sxs-lookup"><span data-stu-id="6a61a-1089">**OCSP URLs**</span></span>|
|<span data-ttu-id="6a61a-1090">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-1090"></span></span>|
   
 <span data-ttu-id="6a61a-1091">**Thawte SHA256 SSL autorità di certificazione**</span><span class="sxs-lookup"><span data-stu-id="6a61a-1091">**thawte SHA256 SSL CA**</span></span>
  
||
|:-----|
|<span data-ttu-id="6a61a-1092">**Oggetto**</span><span class="sxs-lookup"><span data-stu-id="6a61a-1092">**Subject**</span></span>|
|<span data-ttu-id="6a61a-1093">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-1093"></span></span>|
|<span data-ttu-id="6a61a-1094">**Autorità di certificazione**</span><span class="sxs-lookup"><span data-stu-id="6a61a-1094">**Issuer**</span></span>|
|<span data-ttu-id="6a61a-1095">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-1095"></span></span>|
|<span data-ttu-id="6a61a-1096">**Nome alternativo soggetto**</span><span class="sxs-lookup"><span data-stu-id="6a61a-1096">**Subject Alternative Name**</span></span>|
|<span data-ttu-id="6a61a-1097">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-1097"></span></span>|
|<span data-ttu-id="6a61a-1098">**Numero di serie**</span><span class="sxs-lookup"><span data-stu-id="6a61a-1098">**Serial Number**</span></span>|
|<span data-ttu-id="6a61a-1099">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-1099"></span></span>|
|<span data-ttu-id="6a61a-1100">**Lunghezza chiave pubblica**</span><span class="sxs-lookup"><span data-stu-id="6a61a-1100">**Public Key Length**</span></span>|
|<span data-ttu-id="6a61a-1101">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-1101"></span></span>|
|<span data-ttu-id="6a61a-1102">**Algoritmo di firma**</span><span class="sxs-lookup"><span data-stu-id="6a61a-1102">**Signature Algorithm**</span></span>|
|<span data-ttu-id="6a61a-1103">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-1103"></span></span>|
|<span data-ttu-id="6a61a-1104">**Validità non prima**</span><span class="sxs-lookup"><span data-stu-id="6a61a-1104">**Validity Not Before**</span></span>|
|<span data-ttu-id="6a61a-1105">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-1105"></span></span>|
|<span data-ttu-id="6a61a-1106">**Validità non dopo**</span><span class="sxs-lookup"><span data-stu-id="6a61a-1106">**Validity Not After**</span></span>|
|<span data-ttu-id="6a61a-1107">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-1107"></span></span>|
|<span data-ttu-id="6a61a-1108">**Identificatore chiave del soggetto**</span><span class="sxs-lookup"><span data-stu-id="6a61a-1108">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="6a61a-1109">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-1109"></span></span>|
|<span data-ttu-id="6a61a-1110">**Identificatore chiave dell'autorità**</span><span class="sxs-lookup"><span data-stu-id="6a61a-1110">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="6a61a-1111">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-1111"></span></span>|
|<span data-ttu-id="6a61a-1112">**Identificazione personale (SHA-1)**</span><span class="sxs-lookup"><span data-stu-id="6a61a-1112">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="6a61a-1113">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-1113"></span></span>|
|<span data-ttu-id="6a61a-1114">**Identificazione personale (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="6a61a-1114">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="6a61a-1115">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-1115"></span></span>|
|<span data-ttu-id="6a61a-1116">**PIN (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="6a61a-1116">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="6a61a-1117">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-1117"></span></span>|
|<span data-ttu-id="6a61a-1118">**URL di revoche di certificati**</span><span class="sxs-lookup"><span data-stu-id="6a61a-1118">**CRL URLs**</span></span>|
|<span data-ttu-id="6a61a-1119">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-1119"></span></span>|
|<span data-ttu-id="6a61a-1120">**URL OCSP**</span><span class="sxs-lookup"><span data-stu-id="6a61a-1120">**OCSP URLs**</span></span>|
|<span data-ttu-id="6a61a-1121">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-1121"></span></span>|
   
 <span data-ttu-id="6a61a-1122">**Autorità di certificazione SureServer Verizon Akamai G14-SHA2**</span><span class="sxs-lookup"><span data-stu-id="6a61a-1122">**Verizon Akamai SureServer CA G14-SHA2**</span></span>
  
||
|:-----|
|<span data-ttu-id="6a61a-1123">**Oggetto**</span><span class="sxs-lookup"><span data-stu-id="6a61a-1123">**Subject**</span></span>|
|<span data-ttu-id="6a61a-1124">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-1124"></span></span>|
|<span data-ttu-id="6a61a-1125">**Autorità di certificazione**</span><span class="sxs-lookup"><span data-stu-id="6a61a-1125">**Issuer**</span></span>|
|<span data-ttu-id="6a61a-1126">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-1126"></span></span>|
|<span data-ttu-id="6a61a-1127">**Numero di serie**</span><span class="sxs-lookup"><span data-stu-id="6a61a-1127">**Serial Number**</span></span>|
|<span data-ttu-id="6a61a-1128">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-1128"></span></span>|
|<span data-ttu-id="6a61a-1129">**Lunghezza chiave pubblica**</span><span class="sxs-lookup"><span data-stu-id="6a61a-1129">**Public Key Length**</span></span>|
|<span data-ttu-id="6a61a-1130">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-1130"></span></span>|
|<span data-ttu-id="6a61a-1131">**Algoritmo di firma**</span><span class="sxs-lookup"><span data-stu-id="6a61a-1131">**Signature Algorithm**</span></span>|
|<span data-ttu-id="6a61a-1132">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-1132"></span></span>|
|<span data-ttu-id="6a61a-1133">**Validità non prima**</span><span class="sxs-lookup"><span data-stu-id="6a61a-1133">**Validity Not Before**</span></span>|
|<span data-ttu-id="6a61a-1134">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-1134"></span></span>|
|<span data-ttu-id="6a61a-1135">**Validità non dopo**</span><span class="sxs-lookup"><span data-stu-id="6a61a-1135">**Validity Not After**</span></span>|
|<span data-ttu-id="6a61a-1136">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-1136"></span></span>|
|<span data-ttu-id="6a61a-1137">**Identificatore chiave del soggetto**</span><span class="sxs-lookup"><span data-stu-id="6a61a-1137">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="6a61a-1138">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-1138"></span></span>|
|<span data-ttu-id="6a61a-1139">**Identificatore chiave dell'autorità**</span><span class="sxs-lookup"><span data-stu-id="6a61a-1139">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="6a61a-1140">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-1140"></span></span>|
|<span data-ttu-id="6a61a-1141">**Identificazione personale (SHA-1)**</span><span class="sxs-lookup"><span data-stu-id="6a61a-1141">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="6a61a-1142">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-1142"></span></span>|
|<span data-ttu-id="6a61a-1143">**Identificazione personale (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="6a61a-1143">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="6a61a-1144">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-1144"></span></span>|
|<span data-ttu-id="6a61a-1145">**PIN (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="6a61a-1145">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="6a61a-1146">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-1146"></span></span>|
|<span data-ttu-id="6a61a-1147">**URL AIA**</span><span class="sxs-lookup"><span data-stu-id="6a61a-1147">**AIA URLs**</span></span>|
|<span data-ttu-id="6a61a-1148">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-1148"></span></span>|
|<span data-ttu-id="6a61a-1149">**URL di revoche di certificati**</span><span class="sxs-lookup"><span data-stu-id="6a61a-1149">**CRL URLs**</span></span>|
|<span data-ttu-id="6a61a-1150">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-1150"></span></span>|
|<span data-ttu-id="6a61a-1151">**URL OCSP**</span><span class="sxs-lookup"><span data-stu-id="6a61a-1151">**OCSP URLs**</span></span>|
|<span data-ttu-id="6a61a-1152">:-----</span><span class="sxs-lookup"><span data-stu-id="6a61a-1152"></span></span>|
   
## <a name="additional-certificate-paths"></a><span data-ttu-id="6a61a-1153">Percorsi aggiuntivi certificato</span><span class="sxs-lookup"><span data-stu-id="6a61a-1153">Additional certificate paths</span></span>
<span data-ttu-id="6a61a-1154"><a name="IntermediateCerts"> </a></span><span class="sxs-lookup"><span data-stu-id="6a61a-1154"></span></span>

<span data-ttu-id="6a61a-1155">Le operazioni seguenti includono i certificati legacy non vengono inclusi in precedenza e verranno uniti con l'elenco precedente nel tempo.</span><span class="sxs-lookup"><span data-stu-id="6a61a-1155">The following include legacy certificates that aren't included above and will be merged with the list above over time.</span></span>
  
```
evsecure-aia.verisign.com
sa.symcb.com
sd.symcb.com
*.omniroot.com
*.verisign.com
*.symcb.com
*.symcd.com
*.verisign.net
*.geotrust.com
*.entrust.net
*.public-trust.com
EVIntl-ocsp.verisign.com
EVSecure-ocsp.verisign.com
isrg.trustid.ocsp.identrust.com
ocsp.digicert.com
ocsp.entrust.net
ocsp.globalsign.com/ExtendedSSLSHA256CACross
ocsp.globalsign.com/rootr1
ocsp.globalsign.com/rootr2
ocsp2.globalsign.com/rootr3
ocsp.int-x3.letsencrypt.org/
ocsp.msocsp.com
ocsp.omniroot.com/baltimoreroot
ocsp2.globalsign.com/gsextendvalsha2g3r3
ocsp2.globalsign.com/gsorganizationvalsha2g2
ocsp2.globalsign.com/gsorganizationvalsha2g3
ocsp2.globalsign.com/rootr3
ocspx.digicert.com
s2.symcb.com
sr.symcd.com
su.symcd.com
vassg142.ocsp.omniroot.com
cdp1.public-trust.com/CRL/Omniroot2025.crl
crl.entrust.net/2048ca.crl
crl.entrust.net/g2ca.crl
crl.entrust.net/level1k.crl
crl.entrust.net/rootca1.crl
crl.globalsign.com/gs/gsextendvalsha2g3r3.crl
crl.globalsign.com/gs/gsorganizationvalsha2g2.crl
crl.globalsign.com/gsorganizationvalsha2g3.crl
crl.globalsign.com/root.crl
crl.globalsign.net/root-r2.crl
crl.globalsign.com/root-r3.crl
crl.globalsign.net/root.crl
crl.identrust.com/DSTROOTCAX3CRL.crl
crl.microsoft.com/pki/mscorp/crl/msitwww1.crl
crl.microsoft.com/pki/mscorp/crl/msitwww2.crl
crl3.digicert.com/DigiCertCloudServicesCA-1-g1.crl
crl3.digicert.com/DigiCertGlobalRootCA.crl
crl3.digicert.com/sha2-ev-server-g1.crl
crl3.digicert.com/sha2-ha-server-g5.crl
crl3.digicert.com/ssca-sha2-g5.crl
crl4.digicert.com/DigiCertCloudServicesCA-1-g1.crl
crl4.digicert.com/DigiCertGlobalRootCA.crl
crl4.digicert.com/DigiCertHighAssuranceEVRootCA.crl
crl4.digicert.com/sha2-ev-server-g1.crl
crl4.digicert.com/sha2-ha-server-g5.crl
crl4.digicert.com/ssca-sha2-g5.crl
EVIntl-crl.verisign.com/EVIntl2006.crl
EVSecure-crl.verisign.com/pca3-g5.crl
mscrl.microsoft.com/pki/mscorp/crl/msitwww1.crl
mscrl.microsoft.com/pki/mscorp/crl/msitwww2.crl
s1.symcb.com/pca3-g5.crl
sr.symcb.com/sr.crl
su.symcb.com/su.crl
vassg142.crl.omniroot.com/vassg142.crl
aia.entrust.net/l1k-chain256.cer
apps.identrust.com/roots/dstrootcax3.p7c
https://cacert.a.omniroot.com/vassg142.crt
https://cacert.a.omniroot.com/vassg142.der
https://cacert.omniroot.com/baltimoreroot.crt
https://cacert.omniroot.com/baltimoreroot.der
cacerts.digicert.com/DigiCertCloudServicesCA-1.crt
cacerts.digicert.com/DigiCertSHA2ExtendedValidationServerCA.crt
cacerts.digicert.com/DigiCertSHA2HighAssuranceServerCA.crt
cacerts.digicert.com/DigiCertSHA2SecureServerCA.crt
cert.int-x3.letsencrypt.org/
EVIntl-aia.verisign.com/EVIntl2006.cer
secure.globalsign.com/cacert/gsextendvalsha2g2r2.crt
secure.globalsign.com/cacert/gsextendvalsha2g3r3.crt
secure.globalsign.com/cacert/gsorganizationvalsha2g2r1.crt
secure.globalsign.com/cacert/gsorganizationvalsha2g3.crt
sr.symcb.com/sr.crt
su.symcb.com/su.crt
https://www.digicert.com/CACerts/DigiCertGlobalRootCA.crt
https://www.digicert.com/CACerts/DigiCertHighAssuranceEVRootCA.crt
www.microsoft.com/pki/mscorp/msitwww1.crt
www.microsoft.com/pki/mscorp/msitwww2.crt

```


