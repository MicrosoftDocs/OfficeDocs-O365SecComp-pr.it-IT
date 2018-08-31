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
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/27/2018
ms.locfileid: "22530683"
---
# <a name="office-365-certificate-chains"></a><span data-ttu-id="bd140-106">Catena di certificati di Office 365</span><span class="sxs-lookup"><span data-stu-id="bd140-106">Office 365 Certificate Chains</span></span>

<span data-ttu-id="bd140-p102">Office 365 si avvale di un numero di provider di certificati differenti. Di seguito vengono descritti l'elenco completo dei certificati radice di Office 365 noti che i clienti possono verificarsi quando si accede a Office 365. Per informazioni sui certificati potrebbe essere necessario installare un'infrastruttura, vedere [pianificare i certificati SSL di terze parti per Office 365](https://support.office.com/article/b48cdf63-07e0-4cda-8c12-4871590f59ce). Le seguenti informazioni sul certificato si applica a tutte le istanze di tutto il mondo e nazionali cloud di Office 365.</span><span class="sxs-lookup"><span data-stu-id="bd140-p102">Office 365 leverages a number of different certificate providers. The following describes the complete list of known Office 365 root certificates that customers may encounter when accessing Office 365. For information on the certificates you may need to install in your own infrastructure, see [Plan for third-party SSL certificates for Office 365](https://support.office.com/article/b48cdf63-07e0-4cda-8c12-4871590f59ce). The following certificate information applies to all worldwide and national cloud instances of Office 365.</span></span>
  

|<span data-ttu-id="bd140-111">**Tipo di certificato**</span><span class="sxs-lookup"><span data-stu-id="bd140-111">**Certificate type**</span></span>|<span data-ttu-id="bd140-112">**Download P7b**</span><span class="sxs-lookup"><span data-stu-id="bd140-112">**P7b download**</span></span>|<span data-ttu-id="bd140-113">**Endpoint di revoche di certificati**</span><span class="sxs-lookup"><span data-stu-id="bd140-113">**CRL Endpoints**</span></span>|<span data-ttu-id="bd140-114">**Endpoint OCSP**</span><span class="sxs-lookup"><span data-stu-id="bd140-114">**OCSP Endpoints**</span></span>|<span data-ttu-id="bd140-115">**Endpoint AIA**</span><span class="sxs-lookup"><span data-stu-id="bd140-115">**AIA Endpoints**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|[<span data-ttu-id="bd140-116">Pubblicamente attendibili i certificati radice</span><span class="sxs-lookup"><span data-stu-id="bd140-116">Publicly Trusted Root Certificates</span></span>](https://support.office.com/article/0c03e6b3-e73f-4316-9e2b-bf4091ae96bb#rootcerts) <br/> |[<span data-ttu-id="bd140-117">Bundle di certificati radice di Office 365 (P7B)</span><span class="sxs-lookup"><span data-stu-id="bd140-117">Office 365 Root Certificate Bundle (P7B)</span></span>](http://download.microsoft.com/download/A/5/A/A5AE01F3-D19B-4A11-9407-801263CEF72C/O365_Root_Certs_20170321.p7b) <br/> |<span data-ttu-id="bd140-118">CRL.GlobalSign.NET</span><span class="sxs-lookup"><span data-stu-id="bd140-118">crl.globalsign.net</span></span>  <br/> <span data-ttu-id="bd140-119">www.d-trust.NET</span><span class="sxs-lookup"><span data-stu-id="bd140-119">www.d-trust.net</span></span>  <br/> |<span data-ttu-id="bd140-120">N/D</span><span class="sxs-lookup"><span data-stu-id="bd140-120">N/A</span></span>  <br/> |<span data-ttu-id="bd140-121">N/D</span><span class="sxs-lookup"><span data-stu-id="bd140-121">N/A</span></span>  <br/> |
|[<span data-ttu-id="bd140-122">Livello intermedi certificati pubblicamente attendibili</span><span class="sxs-lookup"><span data-stu-id="bd140-122">Publicly Trusted Intermediate Certificates</span></span>](https://support.office.com/article/0c03e6b3-e73f-4316-9e2b-bf4091ae96bb#IntermediateCerts) <br/> |[<span data-ttu-id="bd140-123">Office 365 certificato intermedio Bundle (P7B)</span><span class="sxs-lookup"><span data-stu-id="bd140-123">Office 365 Intermediate Certificate Bundle (P7B)</span></span>](http://download.microsoft.com/download/4/D/5/4D5339A4-0A4A-46AB-AE52-B179DEDA4BEC/O365_Intermediate_Certs_20170321.p7b)  <br/> |<span data-ttu-id="bd140-124">cdp1.Public trust.com</span><span class="sxs-lookup"><span data-stu-id="bd140-124">cdp1.public-trust.com</span></span>  <br/> <span data-ttu-id="bd140-125">CRL.cnnic.CN</span><span class="sxs-lookup"><span data-stu-id="bd140-125">crl.cnnic.cn</span></span>  <br/> <span data-ttu-id="bd140-126">CRL.Entrust.NET</span><span class="sxs-lookup"><span data-stu-id="bd140-126">crl.entrust.net</span></span>  <br/> <span data-ttu-id="bd140-127">CRL.GlobalSign.com</span><span class="sxs-lookup"><span data-stu-id="bd140-127">crl.globalsign.com</span></span>  <br/> <span data-ttu-id="bd140-128">CRL.GlobalSign.NET</span><span class="sxs-lookup"><span data-stu-id="bd140-128">crl.globalsign.net</span></span>  <br/> <span data-ttu-id="bd140-129">CRL.identrust.com</span><span class="sxs-lookup"><span data-stu-id="bd140-129">crl.identrust.com</span></span>  <br/> <span data-ttu-id="bd140-130">CRL.Thawte.com</span><span class="sxs-lookup"><span data-stu-id="bd140-130">crl.thawte.com</span></span>  <br/> <span data-ttu-id="bd140-131">crl3.DigiCert.com</span><span class="sxs-lookup"><span data-stu-id="bd140-131">crl3.digicert.com</span></span>  <br/> <span data-ttu-id="bd140-132">crl4.DigiCert.com</span><span class="sxs-lookup"><span data-stu-id="bd140-132">crl4.digicert.com</span></span>  <br/> <span data-ttu-id="bd140-133">s1.symcb.com</span><span class="sxs-lookup"><span data-stu-id="bd140-133">s1.symcb.com</span></span>  <br/> <span data-ttu-id="bd140-134">www.d-trust.NET</span><span class="sxs-lookup"><span data-stu-id="bd140-134">www.d-trust.net</span></span>  <br/> |<span data-ttu-id="bd140-135">isrg.trustid.OCSP.identrust.com</span><span class="sxs-lookup"><span data-stu-id="bd140-135">isrg.trustid.ocsp.identrust.com</span></span>  <br/> <span data-ttu-id="bd140-136">OCSP.DigiCert.com</span><span class="sxs-lookup"><span data-stu-id="bd140-136">ocsp.digicert.com</span></span>  <br/> <span data-ttu-id="bd140-137">OCSP.Entrust.NET</span><span class="sxs-lookup"><span data-stu-id="bd140-137">ocsp.entrust.net</span></span>  <br/> <span data-ttu-id="bd140-138">OCSP.GlobalSign.com</span><span class="sxs-lookup"><span data-stu-id="bd140-138">ocsp.globalsign.com</span></span>  <br/> <span data-ttu-id="bd140-139">OCSP.omniroot.com</span><span class="sxs-lookup"><span data-stu-id="bd140-139">ocsp.omniroot.com</span></span>  <br/> <span data-ttu-id="bd140-140">OCSP.startssl.com</span><span class="sxs-lookup"><span data-stu-id="bd140-140">ocsp.startssl.com</span></span>  <br/> <span data-ttu-id="bd140-141">OCSP.Thawte.com</span><span class="sxs-lookup"><span data-stu-id="bd140-141">ocsp.thawte.com</span></span>  <br/> <span data-ttu-id="bd140-142">ocsp2.GlobalSign.com</span><span class="sxs-lookup"><span data-stu-id="bd140-142">ocsp2.globalsign.com</span></span>  <br/> <span data-ttu-id="bd140-143">ocspcnnicroot.cnnic.CN</span><span class="sxs-lookup"><span data-stu-id="bd140-143">ocspcnnicroot.cnnic.cn</span></span>  <br/> <span data-ttu-id="bd140-144">radice-c3-ca2-2009.ocsp.d-trust.net</span><span class="sxs-lookup"><span data-stu-id="bd140-144">root-c3-ca2-2009.ocsp.d-trust.net</span></span>  <br/> <span data-ttu-id="bd140-145">Root-C3-CA2-EV-2009.OCSP.d-trust.NET</span><span class="sxs-lookup"><span data-stu-id="bd140-145">root-c3-ca2-ev-2009.ocsp.d-trust.net</span></span>  <br/> <span data-ttu-id="bd140-146">s2.symcb.com</span><span class="sxs-lookup"><span data-stu-id="bd140-146">s2.symcb.com</span></span>  <br/> |<span data-ttu-id="bd140-147">AIA.startssl.com</span><span class="sxs-lookup"><span data-stu-id="bd140-147">aia.startssl.com</span></span>  <br/> <span data-ttu-id="bd140-148">Apps.identrust.com</span><span class="sxs-lookup"><span data-stu-id="bd140-148">apps.identrust.com</span></span>  <br/> <span data-ttu-id="bd140-149">cacert.omniroot.com</span><span class="sxs-lookup"><span data-stu-id="bd140-149">cacert.omniroot.com</span></span>  <br/> <span data-ttu-id="bd140-150">www.cnnic.CN</span><span class="sxs-lookup"><span data-stu-id="bd140-150">www.cnnic.cn</span></span>  <br/> |
   
<span data-ttu-id="bd140-151">Espandere il nodo radice e intermedio nelle sezioni seguenti per visualizzare ulteriori informazioni sui provider di certificati.</span><span class="sxs-lookup"><span data-stu-id="bd140-151">Expand the root and intermediate sections below to see additional details about the certificate providers.</span></span>
  
## <a name="office-365-root-certificate-details"></a><span data-ttu-id="bd140-152">Dettagli del certificato radice di Office 365</span><span class="sxs-lookup"><span data-stu-id="bd140-152">Office 365 Root Certificate Details</span></span>
<span data-ttu-id="bd140-153"><a name="RootCerts"> </a></span><span class="sxs-lookup"><span data-stu-id="bd140-153"></span></span>

 <span data-ttu-id="bd140-154">**Baltimore CyberTrust Root**</span><span class="sxs-lookup"><span data-stu-id="bd140-154">**Baltimore CyberTrust Root**</span></span>
  
<span data-ttu-id="bd140-155">|:-----|</span><span class="sxs-lookup"><span data-stu-id="bd140-155">|:-----|</span></span>
|<span data-ttu-id="bd140-156">**Oggetto**</span><span class="sxs-lookup"><span data-stu-id="bd140-156">**Subject**</span></span>|
|:-----|
|<span data-ttu-id="bd140-157">**Numero di serie**</span><span class="sxs-lookup"><span data-stu-id="bd140-157">**Serial Number**</span></span>|
|<span data-ttu-id="bd140-158">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-158"></span></span>|
|<span data-ttu-id="bd140-159">**Lunghezza chiave pubblica**</span><span class="sxs-lookup"><span data-stu-id="bd140-159">**Public Key Length**</span></span>|
|<span data-ttu-id="bd140-160">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-160"></span></span>|
|<span data-ttu-id="bd140-161">**Algoritmo di firma**</span><span class="sxs-lookup"><span data-stu-id="bd140-161">**Signature Algorithm**</span></span>|
|<span data-ttu-id="bd140-162">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-162"></span></span>|
|<span data-ttu-id="bd140-163">**Validità non prima**</span><span class="sxs-lookup"><span data-stu-id="bd140-163">**Validity Not Before**</span></span>|
|<span data-ttu-id="bd140-164">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-164"></span></span>|
|<span data-ttu-id="bd140-165">**Validità non dopo**</span><span class="sxs-lookup"><span data-stu-id="bd140-165">**Validity Not After**</span></span>|
|<span data-ttu-id="bd140-166">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-166"></span></span>|
|<span data-ttu-id="bd140-167">**Identificatore chiave del soggetto**</span><span class="sxs-lookup"><span data-stu-id="bd140-167">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="bd140-168">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-168"></span></span>|
|<span data-ttu-id="bd140-169">**Identificazione personale (SHA-1)**</span><span class="sxs-lookup"><span data-stu-id="bd140-169">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="bd140-170">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-170"></span></span>|
|<span data-ttu-id="bd140-171">**Identificazione personale (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="bd140-171">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="bd140-172">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-172"></span></span>|
|<span data-ttu-id="bd140-173">**PIN (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="bd140-173">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="bd140-174">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-174"></span></span>|
   
 <span data-ttu-id="bd140-175">**RADICE CNNIC**</span><span class="sxs-lookup"><span data-stu-id="bd140-175">**CNNIC ROOT**</span></span>
  
||
|:-----|
|<span data-ttu-id="bd140-176">**Oggetto**</span><span class="sxs-lookup"><span data-stu-id="bd140-176">**Subject**</span></span>|
|<span data-ttu-id="bd140-177">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-177"></span></span>|
|<span data-ttu-id="bd140-178">**Numero di serie**</span><span class="sxs-lookup"><span data-stu-id="bd140-178">**Serial Number**</span></span>|
|<span data-ttu-id="bd140-179">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-179"></span></span>|
|<span data-ttu-id="bd140-180">**Lunghezza chiave pubblica**</span><span class="sxs-lookup"><span data-stu-id="bd140-180">**Public Key Length**</span></span>|
|<span data-ttu-id="bd140-181">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-181"></span></span>|
|<span data-ttu-id="bd140-182">**Algoritmo di firma**</span><span class="sxs-lookup"><span data-stu-id="bd140-182">**Signature Algorithm**</span></span>|
|<span data-ttu-id="bd140-183">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-183"></span></span>|
|<span data-ttu-id="bd140-184">**Validità non prima**</span><span class="sxs-lookup"><span data-stu-id="bd140-184">**Validity Not Before**</span></span>|
|<span data-ttu-id="bd140-185">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-185"></span></span>|
|<span data-ttu-id="bd140-186">**Validità non dopo**</span><span class="sxs-lookup"><span data-stu-id="bd140-186">**Validity Not After**</span></span>|
|<span data-ttu-id="bd140-187">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-187"></span></span>|
|<span data-ttu-id="bd140-188">**Identificatore chiave del soggetto**</span><span class="sxs-lookup"><span data-stu-id="bd140-188">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="bd140-189">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-189"></span></span>|
|<span data-ttu-id="bd140-190">**Identificatore chiave dell'autorità**</span><span class="sxs-lookup"><span data-stu-id="bd140-190">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="bd140-191">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-191"></span></span>|
|<span data-ttu-id="bd140-192">**Identificazione personale (SHA-1)**</span><span class="sxs-lookup"><span data-stu-id="bd140-192">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="bd140-193">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-193"></span></span>|
|<span data-ttu-id="bd140-194">**Identificazione personale (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="bd140-194">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="bd140-195">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-195"></span></span>|
|<span data-ttu-id="bd140-196">**PIN (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="bd140-196">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="bd140-197">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-197"></span></span>|
   
 <span data-ttu-id="bd140-198">**Autorità di certificazione radice globale DigiCert**</span><span class="sxs-lookup"><span data-stu-id="bd140-198">**DigiCert Global Root CA**</span></span>
  
||
|:-----|
|<span data-ttu-id="bd140-199">**Oggetto**</span><span class="sxs-lookup"><span data-stu-id="bd140-199">**Subject**</span></span>|
|<span data-ttu-id="bd140-200">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-200"></span></span>|
|<span data-ttu-id="bd140-201">**Numero di serie**</span><span class="sxs-lookup"><span data-stu-id="bd140-201">**Serial Number**</span></span>|
|<span data-ttu-id="bd140-202">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-202"></span></span>|
|<span data-ttu-id="bd140-203">**Lunghezza chiave pubblica**</span><span class="sxs-lookup"><span data-stu-id="bd140-203">**Public Key Length**</span></span>|
|<span data-ttu-id="bd140-204">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-204"></span></span>|
|<span data-ttu-id="bd140-205">**Algoritmo di firma**</span><span class="sxs-lookup"><span data-stu-id="bd140-205">**Signature Algorithm**</span></span>|
|<span data-ttu-id="bd140-206">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-206"></span></span>|
|<span data-ttu-id="bd140-207">**Validità non prima**</span><span class="sxs-lookup"><span data-stu-id="bd140-207">**Validity Not Before**</span></span>|
|<span data-ttu-id="bd140-208">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-208"></span></span>|
|<span data-ttu-id="bd140-209">**Validità non dopo**</span><span class="sxs-lookup"><span data-stu-id="bd140-209">**Validity Not After**</span></span>|
|<span data-ttu-id="bd140-210">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-210"></span></span>|
|<span data-ttu-id="bd140-211">**Identificatore chiave del soggetto**</span><span class="sxs-lookup"><span data-stu-id="bd140-211">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="bd140-212">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-212"></span></span>|
|<span data-ttu-id="bd140-213">**Identificatore chiave dell'autorità**</span><span class="sxs-lookup"><span data-stu-id="bd140-213">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="bd140-214">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-214"></span></span>|
|<span data-ttu-id="bd140-215">**Identificazione personale (SHA-1)**</span><span class="sxs-lookup"><span data-stu-id="bd140-215">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="bd140-216">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-216"></span></span>|
|<span data-ttu-id="bd140-217">**Identificazione personale (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="bd140-217">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="bd140-218">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-218"></span></span>|
|<span data-ttu-id="bd140-219">**PIN (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="bd140-219">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="bd140-220">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-220"></span></span>|
   
 <span data-ttu-id="bd140-221">**Autorità di certificazione radice convalida estesa con garanzia elevata DigiCert**</span><span class="sxs-lookup"><span data-stu-id="bd140-221">**DigiCert High Assurance EV Root CA**</span></span>
  
||
|:-----|
|<span data-ttu-id="bd140-222">**Oggetto**</span><span class="sxs-lookup"><span data-stu-id="bd140-222">**Subject**</span></span>|
|<span data-ttu-id="bd140-223">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-223"></span></span>|
|<span data-ttu-id="bd140-224">**Numero di serie**</span><span class="sxs-lookup"><span data-stu-id="bd140-224">**Serial Number**</span></span>|
|<span data-ttu-id="bd140-225">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-225"></span></span>|
|<span data-ttu-id="bd140-226">**Lunghezza chiave pubblica**</span><span class="sxs-lookup"><span data-stu-id="bd140-226">**Public Key Length**</span></span>|
|<span data-ttu-id="bd140-227">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-227"></span></span>|
|<span data-ttu-id="bd140-228">**Algoritmo di firma**</span><span class="sxs-lookup"><span data-stu-id="bd140-228">**Signature Algorithm**</span></span>|
|<span data-ttu-id="bd140-229">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-229"></span></span>|
|<span data-ttu-id="bd140-230">**Validità non prima**</span><span class="sxs-lookup"><span data-stu-id="bd140-230">**Validity Not Before**</span></span>|
|<span data-ttu-id="bd140-231">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-231"></span></span>|
|<span data-ttu-id="bd140-232">**Validità non dopo**</span><span class="sxs-lookup"><span data-stu-id="bd140-232">**Validity Not After**</span></span>|
|<span data-ttu-id="bd140-233">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-233"></span></span>|
|<span data-ttu-id="bd140-234">**Identificatore chiave del soggetto**</span><span class="sxs-lookup"><span data-stu-id="bd140-234">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="bd140-235">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-235"></span></span>|
|<span data-ttu-id="bd140-236">**Identificatore chiave dell'autorità**</span><span class="sxs-lookup"><span data-stu-id="bd140-236">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="bd140-237">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-237"></span></span>|
|<span data-ttu-id="bd140-238">**Identificazione personale (SHA-1)**</span><span class="sxs-lookup"><span data-stu-id="bd140-238">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="bd140-239">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-239"></span></span>|
|<span data-ttu-id="bd140-240">**Identificazione personale (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="bd140-240">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="bd140-241">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-241"></span></span>|
|<span data-ttu-id="bd140-242">**PIN (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="bd140-242">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="bd140-243">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-243"></span></span>|
   
 <span data-ttu-id="bd140-244">**Autorità di certificazione radice D protezione classe 3 2 2009**</span><span class="sxs-lookup"><span data-stu-id="bd140-244">**D-TRUST Root Class 3 CA 2 2009**</span></span>
  
||
|:-----|
|<span data-ttu-id="bd140-245">**Oggetto**</span><span class="sxs-lookup"><span data-stu-id="bd140-245">**Subject**</span></span>|
|<span data-ttu-id="bd140-246">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-246"></span></span>|
|<span data-ttu-id="bd140-247">**Numero di serie**</span><span class="sxs-lookup"><span data-stu-id="bd140-247">**Serial Number**</span></span>|
|<span data-ttu-id="bd140-248">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-248"></span></span>|
|<span data-ttu-id="bd140-249">**Lunghezza chiave pubblica**</span><span class="sxs-lookup"><span data-stu-id="bd140-249">**Public Key Length**</span></span>|
|<span data-ttu-id="bd140-250">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-250"></span></span>|
|<span data-ttu-id="bd140-251">**Algoritmo di firma**</span><span class="sxs-lookup"><span data-stu-id="bd140-251">**Signature Algorithm**</span></span>|
|<span data-ttu-id="bd140-252">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-252"></span></span>|
|<span data-ttu-id="bd140-253">**Validità non prima**</span><span class="sxs-lookup"><span data-stu-id="bd140-253">**Validity Not Before**</span></span>|
|<span data-ttu-id="bd140-254">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-254"></span></span>|
|<span data-ttu-id="bd140-255">**Validità non dopo**</span><span class="sxs-lookup"><span data-stu-id="bd140-255">**Validity Not After**</span></span>|
|<span data-ttu-id="bd140-256">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-256"></span></span>|
|<span data-ttu-id="bd140-257">**Identificatore chiave del soggetto**</span><span class="sxs-lookup"><span data-stu-id="bd140-257">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="bd140-258">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-258"></span></span>|
|<span data-ttu-id="bd140-259">**Identificazione personale (SHA-1)**</span><span class="sxs-lookup"><span data-stu-id="bd140-259">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="bd140-260">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-260"></span></span>|
|<span data-ttu-id="bd140-261">**Identificazione personale (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="bd140-261">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="bd140-262">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-262"></span></span>|
|<span data-ttu-id="bd140-263">**PIN (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="bd140-263">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="bd140-264">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-264"></span></span>|
|<span data-ttu-id="bd140-265">**URL di revoche di certificati**</span><span class="sxs-lookup"><span data-stu-id="bd140-265">**CRL URLs**</span></span>|
|<span data-ttu-id="bd140-266">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-266"></span></span>|
   
 <span data-ttu-id="bd140-267">**D-TRUST radice classe 3 CA 2 EV 2009**</span><span class="sxs-lookup"><span data-stu-id="bd140-267">**D-TRUST Root Class 3 CA 2 EV 2009**</span></span>
  
||
|:-----|
|<span data-ttu-id="bd140-268">**Oggetto**</span><span class="sxs-lookup"><span data-stu-id="bd140-268">**Subject**</span></span>|
|<span data-ttu-id="bd140-269">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-269"></span></span>|
|<span data-ttu-id="bd140-270">**Numero di serie**</span><span class="sxs-lookup"><span data-stu-id="bd140-270">**Serial Number**</span></span>|
|<span data-ttu-id="bd140-271">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-271"></span></span>|
|<span data-ttu-id="bd140-272">**Lunghezza chiave pubblica**</span><span class="sxs-lookup"><span data-stu-id="bd140-272">**Public Key Length**</span></span>|
|<span data-ttu-id="bd140-273">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-273"></span></span>|
|<span data-ttu-id="bd140-274">**Algoritmo di firma**</span><span class="sxs-lookup"><span data-stu-id="bd140-274">**Signature Algorithm**</span></span>|
|<span data-ttu-id="bd140-275">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-275"></span></span>|
|<span data-ttu-id="bd140-276">**Validità non prima**</span><span class="sxs-lookup"><span data-stu-id="bd140-276">**Validity Not Before**</span></span>|
|<span data-ttu-id="bd140-277">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-277"></span></span>|
|<span data-ttu-id="bd140-278">**Validità non dopo**</span><span class="sxs-lookup"><span data-stu-id="bd140-278">**Validity Not After**</span></span>|
|<span data-ttu-id="bd140-279">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-279"></span></span>|
|<span data-ttu-id="bd140-280">**Identificatore chiave del soggetto**</span><span class="sxs-lookup"><span data-stu-id="bd140-280">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="bd140-281">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-281"></span></span>|
|<span data-ttu-id="bd140-282">**Identificazione personale (SHA-1)**</span><span class="sxs-lookup"><span data-stu-id="bd140-282">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="bd140-283">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-283"></span></span>|
|<span data-ttu-id="bd140-284">**Identificazione personale (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="bd140-284">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="bd140-285">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-285"></span></span>|
|<span data-ttu-id="bd140-286">**PIN (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="bd140-286">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="bd140-287">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-287"></span></span>|
|<span data-ttu-id="bd140-288">**URL di revoche di certificati**</span><span class="sxs-lookup"><span data-stu-id="bd140-288">**CRL URLs**</span></span>|
|<span data-ttu-id="bd140-289">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-289"></span></span>|
   
 <span data-ttu-id="bd140-290">**LEGALE rootca X3**</span><span class="sxs-lookup"><span data-stu-id="bd140-290">**DST Root CA X3**</span></span>
  
||
|:-----|
|<span data-ttu-id="bd140-291">**Oggetto**</span><span class="sxs-lookup"><span data-stu-id="bd140-291">**Subject**</span></span>|
|<span data-ttu-id="bd140-292">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-292"></span></span>|
|<span data-ttu-id="bd140-293">**Numero di serie**</span><span class="sxs-lookup"><span data-stu-id="bd140-293">**Serial Number**</span></span>|
|<span data-ttu-id="bd140-294">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-294"></span></span>|
|<span data-ttu-id="bd140-295">**Lunghezza chiave pubblica**</span><span class="sxs-lookup"><span data-stu-id="bd140-295">**Public Key Length**</span></span>|
|<span data-ttu-id="bd140-296">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-296"></span></span>|
|<span data-ttu-id="bd140-297">**Algoritmo di firma**</span><span class="sxs-lookup"><span data-stu-id="bd140-297">**Signature Algorithm**</span></span>|
|<span data-ttu-id="bd140-298">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-298"></span></span>|
|<span data-ttu-id="bd140-299">**Validità non prima**</span><span class="sxs-lookup"><span data-stu-id="bd140-299">**Validity Not Before**</span></span>|
|<span data-ttu-id="bd140-300">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-300"></span></span>|
|<span data-ttu-id="bd140-301">**Validità non dopo**</span><span class="sxs-lookup"><span data-stu-id="bd140-301">**Validity Not After**</span></span>|
|<span data-ttu-id="bd140-302">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-302"></span></span>|
|<span data-ttu-id="bd140-303">**Identificatore chiave del soggetto**</span><span class="sxs-lookup"><span data-stu-id="bd140-303">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="bd140-304">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-304"></span></span>|
|<span data-ttu-id="bd140-305">**Identificazione personale (SHA-1)**</span><span class="sxs-lookup"><span data-stu-id="bd140-305">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="bd140-306">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-306"></span></span>|
|<span data-ttu-id="bd140-307">**Identificazione personale (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="bd140-307">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="bd140-308">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-308"></span></span>|
|<span data-ttu-id="bd140-309">**PIN (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="bd140-309">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="bd140-310">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-310"></span></span>|
   
 <span data-ttu-id="bd140-311">**Affidare autorità di certificazione radice - G2**</span><span class="sxs-lookup"><span data-stu-id="bd140-311">**Entrust Root Certification Authority - G2**</span></span>
  
||
|:-----|
|<span data-ttu-id="bd140-312">**Oggetto**</span><span class="sxs-lookup"><span data-stu-id="bd140-312">**Subject**</span></span>|
|<span data-ttu-id="bd140-313">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-313"></span></span>|
|<span data-ttu-id="bd140-314">**Numero di serie**</span><span class="sxs-lookup"><span data-stu-id="bd140-314">**Serial Number**</span></span>|
|<span data-ttu-id="bd140-315">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-315"></span></span>|
|<span data-ttu-id="bd140-316">**Lunghezza chiave pubblica**</span><span class="sxs-lookup"><span data-stu-id="bd140-316">**Public Key Length**</span></span>|
|<span data-ttu-id="bd140-317">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-317"></span></span>|
|<span data-ttu-id="bd140-318">**Algoritmo di firma**</span><span class="sxs-lookup"><span data-stu-id="bd140-318">**Signature Algorithm**</span></span>|
|<span data-ttu-id="bd140-319">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-319"></span></span>|
|<span data-ttu-id="bd140-320">**Validità non prima**</span><span class="sxs-lookup"><span data-stu-id="bd140-320">**Validity Not Before**</span></span>|
|<span data-ttu-id="bd140-321">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-321"></span></span>|
|<span data-ttu-id="bd140-322">**Validità non dopo**</span><span class="sxs-lookup"><span data-stu-id="bd140-322">**Validity Not After**</span></span>|
|<span data-ttu-id="bd140-323">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-323"></span></span>|
|<span data-ttu-id="bd140-324">**Identificatore chiave del soggetto**</span><span class="sxs-lookup"><span data-stu-id="bd140-324">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="bd140-325">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-325"></span></span>|
|<span data-ttu-id="bd140-326">**Identificazione personale (SHA-1)**</span><span class="sxs-lookup"><span data-stu-id="bd140-326">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="bd140-327">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-327"></span></span>|
|<span data-ttu-id="bd140-328">**Identificazione personale (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="bd140-328">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="bd140-329">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-329"></span></span>|
|<span data-ttu-id="bd140-330">**PIN (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="bd140-330">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="bd140-331">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-331"></span></span>|
   
 <span data-ttu-id="bd140-332">**Entrust.net Certification Authority (2048)**</span><span class="sxs-lookup"><span data-stu-id="bd140-332">**Entrust.net Certification Authority (2048)**</span></span>
  
||
|:-----|
|<span data-ttu-id="bd140-333">**Oggetto**</span><span class="sxs-lookup"><span data-stu-id="bd140-333">**Subject**</span></span>|
|<span data-ttu-id="bd140-334">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-334"></span></span>|
|<span data-ttu-id="bd140-335">**Numero di serie**</span><span class="sxs-lookup"><span data-stu-id="bd140-335">**Serial Number**</span></span>|
|<span data-ttu-id="bd140-336">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-336"></span></span>|
|<span data-ttu-id="bd140-337">**Lunghezza chiave pubblica**</span><span class="sxs-lookup"><span data-stu-id="bd140-337">**Public Key Length**</span></span>|
|<span data-ttu-id="bd140-338">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-338"></span></span>|
|<span data-ttu-id="bd140-339">**Algoritmo di firma**</span><span class="sxs-lookup"><span data-stu-id="bd140-339">**Signature Algorithm**</span></span>|
|<span data-ttu-id="bd140-340">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-340"></span></span>|
|<span data-ttu-id="bd140-341">**Validità non prima**</span><span class="sxs-lookup"><span data-stu-id="bd140-341">**Validity Not Before**</span></span>|
|<span data-ttu-id="bd140-342">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-342"></span></span>|
|<span data-ttu-id="bd140-343">**Validità non dopo**</span><span class="sxs-lookup"><span data-stu-id="bd140-343">**Validity Not After**</span></span>|
|<span data-ttu-id="bd140-344">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-344"></span></span>|
|<span data-ttu-id="bd140-345">**Identificatore chiave del soggetto**</span><span class="sxs-lookup"><span data-stu-id="bd140-345">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="bd140-346">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-346"></span></span>|
|<span data-ttu-id="bd140-347">**Identificazione personale (SHA-1)**</span><span class="sxs-lookup"><span data-stu-id="bd140-347">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="bd140-348">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-348"></span></span>|
|<span data-ttu-id="bd140-349">**Identificazione personale (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="bd140-349">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="bd140-350">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-350"></span></span>|
|<span data-ttu-id="bd140-351">**PIN (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="bd140-351">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="bd140-352">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-352"></span></span>|
   
 <span data-ttu-id="bd140-353">**GlobalSign**</span><span class="sxs-lookup"><span data-stu-id="bd140-353">**GlobalSign**</span></span>
  
||
|:-----|
|<span data-ttu-id="bd140-354">**Oggetto**</span><span class="sxs-lookup"><span data-stu-id="bd140-354">**Subject**</span></span>|
|<span data-ttu-id="bd140-355">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-355"></span></span>|
|<span data-ttu-id="bd140-356">**Numero di serie**</span><span class="sxs-lookup"><span data-stu-id="bd140-356">**Serial Number**</span></span>|
|<span data-ttu-id="bd140-357">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-357"></span></span>|
|<span data-ttu-id="bd140-358">**Lunghezza chiave pubblica**</span><span class="sxs-lookup"><span data-stu-id="bd140-358">**Public Key Length**</span></span>|
|<span data-ttu-id="bd140-359">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-359"></span></span>|
|<span data-ttu-id="bd140-360">**Algoritmo di firma**</span><span class="sxs-lookup"><span data-stu-id="bd140-360">**Signature Algorithm**</span></span>|
|<span data-ttu-id="bd140-361">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-361"></span></span>|
|<span data-ttu-id="bd140-362">**Validità non prima**</span><span class="sxs-lookup"><span data-stu-id="bd140-362">**Validity Not Before**</span></span>|
|<span data-ttu-id="bd140-363">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-363"></span></span>|
|<span data-ttu-id="bd140-364">**Validità non dopo**</span><span class="sxs-lookup"><span data-stu-id="bd140-364">**Validity Not After**</span></span>|
|<span data-ttu-id="bd140-365">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-365"></span></span>|
|<span data-ttu-id="bd140-366">**Identificatore chiave del soggetto**</span><span class="sxs-lookup"><span data-stu-id="bd140-366">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="bd140-367">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-367"></span></span>|
|<span data-ttu-id="bd140-368">**Identificatore chiave dell'autorità**</span><span class="sxs-lookup"><span data-stu-id="bd140-368">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="bd140-369">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-369"></span></span>|
|<span data-ttu-id="bd140-370">**Identificazione personale (SHA-1)**</span><span class="sxs-lookup"><span data-stu-id="bd140-370">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="bd140-371">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-371"></span></span>|
|<span data-ttu-id="bd140-372">**Identificazione personale (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="bd140-372">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="bd140-373">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-373"></span></span>|
|<span data-ttu-id="bd140-374">**PIN (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="bd140-374">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="bd140-375">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-375"></span></span>|
|<span data-ttu-id="bd140-376">**URL di revoche di certificati**</span><span class="sxs-lookup"><span data-stu-id="bd140-376">**CRL URLs**</span></span>|
|<span data-ttu-id="bd140-377">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-377"></span></span>|
   
 <span data-ttu-id="bd140-378">**GlobalSign Root CA**</span><span class="sxs-lookup"><span data-stu-id="bd140-378">**GlobalSign Root CA**</span></span>
  
||
|:-----|
|<span data-ttu-id="bd140-379">**Oggetto**</span><span class="sxs-lookup"><span data-stu-id="bd140-379">**Subject**</span></span>|
|<span data-ttu-id="bd140-380">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-380"></span></span>|
|<span data-ttu-id="bd140-381">**Numero di serie**</span><span class="sxs-lookup"><span data-stu-id="bd140-381">**Serial Number**</span></span>|
|<span data-ttu-id="bd140-382">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-382"></span></span>|
|<span data-ttu-id="bd140-383">**Lunghezza chiave pubblica**</span><span class="sxs-lookup"><span data-stu-id="bd140-383">**Public Key Length**</span></span>|
|<span data-ttu-id="bd140-384">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-384"></span></span>|
|<span data-ttu-id="bd140-385">**Algoritmo di firma**</span><span class="sxs-lookup"><span data-stu-id="bd140-385">**Signature Algorithm**</span></span>|
|<span data-ttu-id="bd140-386">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-386"></span></span>|
|<span data-ttu-id="bd140-387">**Validità non prima**</span><span class="sxs-lookup"><span data-stu-id="bd140-387">**Validity Not Before**</span></span>|
|<span data-ttu-id="bd140-388">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-388"></span></span>|
|<span data-ttu-id="bd140-389">**Validità non dopo**</span><span class="sxs-lookup"><span data-stu-id="bd140-389">**Validity Not After**</span></span>|
|<span data-ttu-id="bd140-390">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-390"></span></span>|
|<span data-ttu-id="bd140-391">**Identificatore chiave del soggetto**</span><span class="sxs-lookup"><span data-stu-id="bd140-391">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="bd140-392">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-392"></span></span>|
|<span data-ttu-id="bd140-393">**Identificazione personale (SHA-1)**</span><span class="sxs-lookup"><span data-stu-id="bd140-393">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="bd140-394">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-394"></span></span>|
|<span data-ttu-id="bd140-395">**Identificazione personale (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="bd140-395">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="bd140-396">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-396"></span></span>|
|<span data-ttu-id="bd140-397">**PIN (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="bd140-397">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="bd140-398">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-398"></span></span>|
   
 <span data-ttu-id="bd140-399">**Thawte CA radice principale - G3**</span><span class="sxs-lookup"><span data-stu-id="bd140-399">**thawte Primary Root CA - G3**</span></span>
  
||
|:-----|
|<span data-ttu-id="bd140-400">**Oggetto**</span><span class="sxs-lookup"><span data-stu-id="bd140-400">**Subject**</span></span>|
|<span data-ttu-id="bd140-401">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-401"></span></span>|
|<span data-ttu-id="bd140-402">**Numero di serie**</span><span class="sxs-lookup"><span data-stu-id="bd140-402">**Serial Number**</span></span>|
|<span data-ttu-id="bd140-403">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-403"></span></span>|
|<span data-ttu-id="bd140-404">**Lunghezza chiave pubblica**</span><span class="sxs-lookup"><span data-stu-id="bd140-404">**Public Key Length**</span></span>|
|<span data-ttu-id="bd140-405">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-405"></span></span>|
|<span data-ttu-id="bd140-406">**Algoritmo di firma**</span><span class="sxs-lookup"><span data-stu-id="bd140-406">**Signature Algorithm**</span></span>|
|<span data-ttu-id="bd140-407">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-407"></span></span>|
|<span data-ttu-id="bd140-408">**Validità non prima**</span><span class="sxs-lookup"><span data-stu-id="bd140-408">**Validity Not Before**</span></span>|
|<span data-ttu-id="bd140-409">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-409"></span></span>|
|<span data-ttu-id="bd140-410">**Validità non dopo**</span><span class="sxs-lookup"><span data-stu-id="bd140-410">**Validity Not After**</span></span>|
|<span data-ttu-id="bd140-411">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-411"></span></span>|
|<span data-ttu-id="bd140-412">**Identificatore chiave del soggetto**</span><span class="sxs-lookup"><span data-stu-id="bd140-412">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="bd140-413">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-413"></span></span>|
|<span data-ttu-id="bd140-414">**Identificazione personale (SHA-1)**</span><span class="sxs-lookup"><span data-stu-id="bd140-414">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="bd140-415">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-415"></span></span>|
|<span data-ttu-id="bd140-416">**Identificazione personale (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="bd140-416">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="bd140-417">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-417"></span></span>|
|<span data-ttu-id="bd140-418">**PIN (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="bd140-418">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="bd140-419">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-419"></span></span>|
   
 <span data-ttu-id="bd140-420">**Autorità di certificazione principale pubblica VeriSign classe 3 - G5**</span><span class="sxs-lookup"><span data-stu-id="bd140-420">**VeriSign Class 3 Public Primary Certification Authority - G5**</span></span>
  
||
|:-----|
|<span data-ttu-id="bd140-421">**Oggetto**</span><span class="sxs-lookup"><span data-stu-id="bd140-421">**Subject**</span></span>|
|<span data-ttu-id="bd140-422">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-422"></span></span>|
|<span data-ttu-id="bd140-423">**Numero di serie**</span><span class="sxs-lookup"><span data-stu-id="bd140-423">**Serial Number**</span></span>|
|<span data-ttu-id="bd140-424">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-424"></span></span>|
|<span data-ttu-id="bd140-425">**Lunghezza chiave pubblica**</span><span class="sxs-lookup"><span data-stu-id="bd140-425">**Public Key Length**</span></span>|
|<span data-ttu-id="bd140-426">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-426"></span></span>|
|<span data-ttu-id="bd140-427">**Algoritmo di firma**</span><span class="sxs-lookup"><span data-stu-id="bd140-427">**Signature Algorithm**</span></span>|
|<span data-ttu-id="bd140-428">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-428"></span></span>|
|<span data-ttu-id="bd140-429">**Validità non prima**</span><span class="sxs-lookup"><span data-stu-id="bd140-429">**Validity Not Before**</span></span>|
|<span data-ttu-id="bd140-430">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-430"></span></span>|
|<span data-ttu-id="bd140-431">**Validità non dopo**</span><span class="sxs-lookup"><span data-stu-id="bd140-431">**Validity Not After**</span></span>|
|<span data-ttu-id="bd140-432">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-432"></span></span>|
|<span data-ttu-id="bd140-433">**Identificatore chiave del soggetto**</span><span class="sxs-lookup"><span data-stu-id="bd140-433">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="bd140-434">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-434"></span></span>|
|<span data-ttu-id="bd140-435">**Identificazione personale (SHA-1)**</span><span class="sxs-lookup"><span data-stu-id="bd140-435">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="bd140-436">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-436"></span></span>|
|<span data-ttu-id="bd140-437">**Identificazione personale (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="bd140-437">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="bd140-438">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-438"></span></span>|
|<span data-ttu-id="bd140-439">**PIN (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="bd140-439">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="bd140-440">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-440"></span></span>|
   
## <a name="office-365-intermediate-certificate-details"></a><span data-ttu-id="bd140-441">Informazioni relative al certificato intermedio Office 365</span><span class="sxs-lookup"><span data-stu-id="bd140-441">Office 365 Intermediate Certificate Details</span></span>
<span data-ttu-id="bd140-442"><a name="IntermediateCerts"> </a></span><span class="sxs-lookup"><span data-stu-id="bd140-442"></span></span>

 <span data-ttu-id="bd140-443">**CNNIC SHA256 SSL**</span><span class="sxs-lookup"><span data-stu-id="bd140-443">**CNNIC SHA256 SSL**</span></span>
  
||
|:-----|
|<span data-ttu-id="bd140-444">**Oggetto**</span><span class="sxs-lookup"><span data-stu-id="bd140-444">**Subject**</span></span>|
|<span data-ttu-id="bd140-445">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-445"></span></span>|
|<span data-ttu-id="bd140-446">**Autorità di certificazione**</span><span class="sxs-lookup"><span data-stu-id="bd140-446">**Issuer**</span></span>|
|<span data-ttu-id="bd140-447">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-447"></span></span>|
|<span data-ttu-id="bd140-448">**Numero di serie**</span><span class="sxs-lookup"><span data-stu-id="bd140-448">**Serial Number**</span></span>|
|<span data-ttu-id="bd140-449">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-449"></span></span>|
|<span data-ttu-id="bd140-450">**Lunghezza chiave pubblica**</span><span class="sxs-lookup"><span data-stu-id="bd140-450">**Public Key Length**</span></span>|
|<span data-ttu-id="bd140-451">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-451"></span></span>|
|<span data-ttu-id="bd140-452">**Algoritmo di firma**</span><span class="sxs-lookup"><span data-stu-id="bd140-452">**Signature Algorithm**</span></span>|
|<span data-ttu-id="bd140-453">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-453"></span></span>|
|<span data-ttu-id="bd140-454">**Validità non prima**</span><span class="sxs-lookup"><span data-stu-id="bd140-454">**Validity Not Before**</span></span>|
|<span data-ttu-id="bd140-455">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-455"></span></span>|
|<span data-ttu-id="bd140-456">**Validità non dopo**</span><span class="sxs-lookup"><span data-stu-id="bd140-456">**Validity Not After**</span></span>|
|<span data-ttu-id="bd140-457">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-457"></span></span>|
|<span data-ttu-id="bd140-458">**Identificatore chiave del soggetto**</span><span class="sxs-lookup"><span data-stu-id="bd140-458">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="bd140-459">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-459"></span></span>|
|<span data-ttu-id="bd140-460">**Identificatore chiave dell'autorità**</span><span class="sxs-lookup"><span data-stu-id="bd140-460">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="bd140-461">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-461"></span></span>|
|<span data-ttu-id="bd140-462">**Identificazione personale (SHA-1)**</span><span class="sxs-lookup"><span data-stu-id="bd140-462">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="bd140-463">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-463"></span></span>|
|<span data-ttu-id="bd140-464">**Identificazione personale (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="bd140-464">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="bd140-465">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-465"></span></span>|
|<span data-ttu-id="bd140-466">**PIN (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="bd140-466">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="bd140-467">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-467"></span></span>|
|<span data-ttu-id="bd140-468">**URL AIA**</span><span class="sxs-lookup"><span data-stu-id="bd140-468">**AIA URLs**</span></span>|
|<span data-ttu-id="bd140-469">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-469"></span></span>|
|<span data-ttu-id="bd140-470">**URL di revoche di certificati**</span><span class="sxs-lookup"><span data-stu-id="bd140-470">**CRL URLs**</span></span>|
|<span data-ttu-id="bd140-471">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-471"></span></span>|
|<span data-ttu-id="bd140-472">**URL OCSP**</span><span class="sxs-lookup"><span data-stu-id="bd140-472">**OCSP URLs**</span></span>|
|<span data-ttu-id="bd140-473">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-473"></span></span>|
   
 <span data-ttu-id="bd140-474">**Autorità di certificazione classe 3 D protezione SSL 1 2009**</span><span class="sxs-lookup"><span data-stu-id="bd140-474">**D-TRUST SSL Class 3 CA 1 2009**</span></span>
  
||
|:-----|
|<span data-ttu-id="bd140-475">**Oggetto**</span><span class="sxs-lookup"><span data-stu-id="bd140-475">**Subject**</span></span>|
|<span data-ttu-id="bd140-476">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-476"></span></span>|
|<span data-ttu-id="bd140-477">**Autorità di certificazione**</span><span class="sxs-lookup"><span data-stu-id="bd140-477">**Issuer**</span></span>|
|<span data-ttu-id="bd140-478">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-478"></span></span>|
|<span data-ttu-id="bd140-479">**Nome alternativo soggetto**</span><span class="sxs-lookup"><span data-stu-id="bd140-479">**Subject Alternative Name**</span></span>|
|<span data-ttu-id="bd140-480">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-480"></span></span>|
|<span data-ttu-id="bd140-481">**Numero di serie**</span><span class="sxs-lookup"><span data-stu-id="bd140-481">**Serial Number**</span></span>|
|<span data-ttu-id="bd140-482">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-482"></span></span>|
|<span data-ttu-id="bd140-483">**Lunghezza chiave pubblica**</span><span class="sxs-lookup"><span data-stu-id="bd140-483">**Public Key Length**</span></span>|
|<span data-ttu-id="bd140-484">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-484"></span></span>|
|<span data-ttu-id="bd140-485">**Algoritmo di firma**</span><span class="sxs-lookup"><span data-stu-id="bd140-485">**Signature Algorithm**</span></span>|
|<span data-ttu-id="bd140-486">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-486"></span></span>|
|<span data-ttu-id="bd140-487">**Validità non prima**</span><span class="sxs-lookup"><span data-stu-id="bd140-487">**Validity Not Before**</span></span>|
|<span data-ttu-id="bd140-488">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-488"></span></span>|
|<span data-ttu-id="bd140-489">**Validità non dopo**</span><span class="sxs-lookup"><span data-stu-id="bd140-489">**Validity Not After**</span></span>|
|<span data-ttu-id="bd140-490">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-490"></span></span>|
|<span data-ttu-id="bd140-491">**Identificatore chiave del soggetto**</span><span class="sxs-lookup"><span data-stu-id="bd140-491">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="bd140-492">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-492"></span></span>|
|<span data-ttu-id="bd140-493">**Identificatore chiave dell'autorità**</span><span class="sxs-lookup"><span data-stu-id="bd140-493">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="bd140-494">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-494"></span></span>|
|<span data-ttu-id="bd140-495">**Identificazione personale (SHA-1)**</span><span class="sxs-lookup"><span data-stu-id="bd140-495">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="bd140-496">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-496"></span></span>|
|<span data-ttu-id="bd140-497">**Identificazione personale (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="bd140-497">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="bd140-498">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-498"></span></span>|
|<span data-ttu-id="bd140-499">**PIN (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="bd140-499">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="bd140-500">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-500"></span></span>|
|<span data-ttu-id="bd140-501">**URL di revoche di certificati**</span><span class="sxs-lookup"><span data-stu-id="bd140-501">**CRL URLs**</span></span>|
|<span data-ttu-id="bd140-502">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-502"></span></span>|
|<span data-ttu-id="bd140-503">**URL OCSP**</span><span class="sxs-lookup"><span data-stu-id="bd140-503">**OCSP URLs**</span></span>|
|<span data-ttu-id="bd140-504">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-504"></span></span>|
   
 <span data-ttu-id="bd140-505">**Autorità di certificazione classe 3 D protezione SSL 1 EV 2009**</span><span class="sxs-lookup"><span data-stu-id="bd140-505">**D-TRUST SSL Class 3 CA 1 EV 2009**</span></span>
  
||
|:-----|
|<span data-ttu-id="bd140-506">**Oggetto**</span><span class="sxs-lookup"><span data-stu-id="bd140-506">**Subject**</span></span>|
|<span data-ttu-id="bd140-507">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-507"></span></span>|
|<span data-ttu-id="bd140-508">**Autorità di certificazione**</span><span class="sxs-lookup"><span data-stu-id="bd140-508">**Issuer**</span></span>|
|<span data-ttu-id="bd140-509">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-509"></span></span>|
|<span data-ttu-id="bd140-510">**Nome alternativo soggetto**</span><span class="sxs-lookup"><span data-stu-id="bd140-510">**Subject Alternative Name**</span></span>|
|<span data-ttu-id="bd140-511">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-511"></span></span>|
|<span data-ttu-id="bd140-512">**Numero di serie**</span><span class="sxs-lookup"><span data-stu-id="bd140-512">**Serial Number**</span></span>|
|<span data-ttu-id="bd140-513">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-513"></span></span>|
|<span data-ttu-id="bd140-514">**Lunghezza chiave pubblica**</span><span class="sxs-lookup"><span data-stu-id="bd140-514">**Public Key Length**</span></span>|
|<span data-ttu-id="bd140-515">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-515"></span></span>|
|<span data-ttu-id="bd140-516">**Algoritmo di firma**</span><span class="sxs-lookup"><span data-stu-id="bd140-516">**Signature Algorithm**</span></span>|
|<span data-ttu-id="bd140-517">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-517"></span></span>|
|<span data-ttu-id="bd140-518">**Validità non prima**</span><span class="sxs-lookup"><span data-stu-id="bd140-518">**Validity Not Before**</span></span>|
|<span data-ttu-id="bd140-519">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-519"></span></span>|
|<span data-ttu-id="bd140-520">**Validità non dopo**</span><span class="sxs-lookup"><span data-stu-id="bd140-520">**Validity Not After**</span></span>|
|<span data-ttu-id="bd140-521">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-521"></span></span>|
|<span data-ttu-id="bd140-522">**Identificatore chiave del soggetto**</span><span class="sxs-lookup"><span data-stu-id="bd140-522">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="bd140-523">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-523"></span></span>|
|<span data-ttu-id="bd140-524">**Identificatore chiave dell'autorità**</span><span class="sxs-lookup"><span data-stu-id="bd140-524">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="bd140-525">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-525"></span></span>|
|<span data-ttu-id="bd140-526">**Identificazione personale (SHA-1)**</span><span class="sxs-lookup"><span data-stu-id="bd140-526">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="bd140-527">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-527"></span></span>|
|<span data-ttu-id="bd140-528">**Identificazione personale (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="bd140-528">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="bd140-529">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-529"></span></span>|
|<span data-ttu-id="bd140-530">**PIN (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="bd140-530">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="bd140-531">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-531"></span></span>|
|<span data-ttu-id="bd140-532">**URL di revoche di certificati**</span><span class="sxs-lookup"><span data-stu-id="bd140-532">**CRL URLs**</span></span>|
|<span data-ttu-id="bd140-533">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-533"></span></span>|
|<span data-ttu-id="bd140-534">**URL OCSP**</span><span class="sxs-lookup"><span data-stu-id="bd140-534">**OCSP URLs**</span></span>|
|<span data-ttu-id="bd140-535">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-535"></span></span>|
   
 <span data-ttu-id="bd140-536">**CA-1 di servizi Cloud DigiCert**</span><span class="sxs-lookup"><span data-stu-id="bd140-536">**DigiCert Cloud Services CA-1**</span></span>
  
||
|:-----|
|<span data-ttu-id="bd140-537">**Oggetto**</span><span class="sxs-lookup"><span data-stu-id="bd140-537">**Subject**</span></span>|
|<span data-ttu-id="bd140-538">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-538"></span></span>|
|<span data-ttu-id="bd140-539">**Autorità di certificazione**</span><span class="sxs-lookup"><span data-stu-id="bd140-539">**Issuer**</span></span>|
|<span data-ttu-id="bd140-540">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-540"></span></span>|
|<span data-ttu-id="bd140-541">**Numero di serie**</span><span class="sxs-lookup"><span data-stu-id="bd140-541">**Serial Number**</span></span>|
|<span data-ttu-id="bd140-542">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-542"></span></span>|
|<span data-ttu-id="bd140-543">**Lunghezza chiave pubblica**</span><span class="sxs-lookup"><span data-stu-id="bd140-543">**Public Key Length**</span></span>|
|<span data-ttu-id="bd140-544">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-544"></span></span>|
|<span data-ttu-id="bd140-545">**Algoritmo di firma**</span><span class="sxs-lookup"><span data-stu-id="bd140-545">**Signature Algorithm**</span></span>|
|<span data-ttu-id="bd140-546">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-546"></span></span>|
|<span data-ttu-id="bd140-547">**Validità non prima**</span><span class="sxs-lookup"><span data-stu-id="bd140-547">**Validity Not Before**</span></span>|
|<span data-ttu-id="bd140-548">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-548"></span></span>|
|<span data-ttu-id="bd140-549">**Validità non dopo**</span><span class="sxs-lookup"><span data-stu-id="bd140-549">**Validity Not After**</span></span>|
|<span data-ttu-id="bd140-550">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-550"></span></span>|
|<span data-ttu-id="bd140-551">**Identificatore chiave del soggetto**</span><span class="sxs-lookup"><span data-stu-id="bd140-551">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="bd140-552">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-552"></span></span>|
|<span data-ttu-id="bd140-553">**Identificatore chiave dell'autorità**</span><span class="sxs-lookup"><span data-stu-id="bd140-553">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="bd140-554">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-554"></span></span>|
|<span data-ttu-id="bd140-555">**Identificazione personale (SHA-1)**</span><span class="sxs-lookup"><span data-stu-id="bd140-555">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="bd140-556">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-556"></span></span>|
|<span data-ttu-id="bd140-557">**Identificazione personale (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="bd140-557">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="bd140-558">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-558"></span></span>|
|<span data-ttu-id="bd140-559">**PIN (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="bd140-559">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="bd140-560">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-560"></span></span>|
|<span data-ttu-id="bd140-561">**URL di revoche di certificati**</span><span class="sxs-lookup"><span data-stu-id="bd140-561">**CRL URLs**</span></span>|
|<span data-ttu-id="bd140-562">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-562"></span></span>|
|<span data-ttu-id="bd140-563">**URL OCSP**</span><span class="sxs-lookup"><span data-stu-id="bd140-563">**OCSP URLs**</span></span>|
|<span data-ttu-id="bd140-564">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-564"></span></span>|
   
 <span data-ttu-id="bd140-565">**Server di garanzia elevata DigiCert SHA2 autorità di certificazione**</span><span class="sxs-lookup"><span data-stu-id="bd140-565">**DigiCert SHA2 High Assurance Server CA**</span></span>
  
||
|:-----|
|<span data-ttu-id="bd140-566">**Oggetto**</span><span class="sxs-lookup"><span data-stu-id="bd140-566">**Subject**</span></span>|
|<span data-ttu-id="bd140-567">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-567"></span></span>|
|<span data-ttu-id="bd140-568">**Autorità di certificazione**</span><span class="sxs-lookup"><span data-stu-id="bd140-568">**Issuer**</span></span>|
|<span data-ttu-id="bd140-569">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-569"></span></span>|
|<span data-ttu-id="bd140-570">**Numero di serie**</span><span class="sxs-lookup"><span data-stu-id="bd140-570">**Serial Number**</span></span>|
|<span data-ttu-id="bd140-571">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-571"></span></span>|
|<span data-ttu-id="bd140-572">**Lunghezza chiave pubblica**</span><span class="sxs-lookup"><span data-stu-id="bd140-572">**Public Key Length**</span></span>|
|<span data-ttu-id="bd140-573">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-573"></span></span>|
|<span data-ttu-id="bd140-574">**Algoritmo di firma**</span><span class="sxs-lookup"><span data-stu-id="bd140-574">**Signature Algorithm**</span></span>|
|<span data-ttu-id="bd140-575">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-575"></span></span>|
|<span data-ttu-id="bd140-576">**Validità non prima**</span><span class="sxs-lookup"><span data-stu-id="bd140-576">**Validity Not Before**</span></span>|
|<span data-ttu-id="bd140-577">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-577"></span></span>|
|<span data-ttu-id="bd140-578">**Validità non dopo**</span><span class="sxs-lookup"><span data-stu-id="bd140-578">**Validity Not After**</span></span>|
|<span data-ttu-id="bd140-579">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-579"></span></span>|
|<span data-ttu-id="bd140-580">**Identificatore chiave del soggetto**</span><span class="sxs-lookup"><span data-stu-id="bd140-580">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="bd140-581">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-581"></span></span>|
|<span data-ttu-id="bd140-582">**Identificatore chiave dell'autorità**</span><span class="sxs-lookup"><span data-stu-id="bd140-582">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="bd140-583">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-583"></span></span>|
|<span data-ttu-id="bd140-584">**Identificazione personale (SHA-1)**</span><span class="sxs-lookup"><span data-stu-id="bd140-584">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="bd140-585">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-585"></span></span>|
|<span data-ttu-id="bd140-586">**Identificazione personale (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="bd140-586">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="bd140-587">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-587"></span></span>|
|<span data-ttu-id="bd140-588">**PIN (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="bd140-588">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="bd140-589">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-589"></span></span>|
|<span data-ttu-id="bd140-590">**URL di revoche di certificati**</span><span class="sxs-lookup"><span data-stu-id="bd140-590">**CRL URLs**</span></span>|
|<span data-ttu-id="bd140-591">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-591"></span></span>|
|<span data-ttu-id="bd140-592">**URL OCSP**</span><span class="sxs-lookup"><span data-stu-id="bd140-592">**OCSP URLs**</span></span>|
|<span data-ttu-id="bd140-593">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-593"></span></span>|
   
 <span data-ttu-id="bd140-594">**Server protetto DigiCert SHA2 autorità di certificazione**</span><span class="sxs-lookup"><span data-stu-id="bd140-594">**DigiCert SHA2 Secure Server CA**</span></span>
  
||
|:-----|
|<span data-ttu-id="bd140-595">**Oggetto**</span><span class="sxs-lookup"><span data-stu-id="bd140-595">**Subject**</span></span>|
|<span data-ttu-id="bd140-596">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-596"></span></span>|
|<span data-ttu-id="bd140-597">**Autorità di certificazione**</span><span class="sxs-lookup"><span data-stu-id="bd140-597">**Issuer**</span></span>|
|<span data-ttu-id="bd140-598">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-598"></span></span>|
|<span data-ttu-id="bd140-599">**Numero di serie**</span><span class="sxs-lookup"><span data-stu-id="bd140-599">**Serial Number**</span></span>|
|<span data-ttu-id="bd140-600">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-600"></span></span>|
|<span data-ttu-id="bd140-601">**Lunghezza chiave pubblica**</span><span class="sxs-lookup"><span data-stu-id="bd140-601">**Public Key Length**</span></span>|
|<span data-ttu-id="bd140-602">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-602"></span></span>|
|<span data-ttu-id="bd140-603">**Algoritmo di firma**</span><span class="sxs-lookup"><span data-stu-id="bd140-603">**Signature Algorithm**</span></span>|
|<span data-ttu-id="bd140-604">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-604"></span></span>|
|<span data-ttu-id="bd140-605">**Validità non prima**</span><span class="sxs-lookup"><span data-stu-id="bd140-605">**Validity Not Before**</span></span>|
|<span data-ttu-id="bd140-606">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-606"></span></span>|
|<span data-ttu-id="bd140-607">**Validità non dopo**</span><span class="sxs-lookup"><span data-stu-id="bd140-607">**Validity Not After**</span></span>|
|<span data-ttu-id="bd140-608">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-608"></span></span>|
|<span data-ttu-id="bd140-609">**Identificatore chiave del soggetto**</span><span class="sxs-lookup"><span data-stu-id="bd140-609">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="bd140-610">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-610"></span></span>|
|<span data-ttu-id="bd140-611">**Identificatore chiave dell'autorità**</span><span class="sxs-lookup"><span data-stu-id="bd140-611">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="bd140-612">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-612"></span></span>|
|<span data-ttu-id="bd140-613">**Identificazione personale (SHA-1)**</span><span class="sxs-lookup"><span data-stu-id="bd140-613">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="bd140-614">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-614"></span></span>|
|<span data-ttu-id="bd140-615">**Identificazione personale (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="bd140-615">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="bd140-616">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-616"></span></span>|
|<span data-ttu-id="bd140-617">**PIN (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="bd140-617">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="bd140-618">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-618"></span></span>|
|<span data-ttu-id="bd140-619">**URL di revoche di certificati**</span><span class="sxs-lookup"><span data-stu-id="bd140-619">**CRL URLs**</span></span>|
|<span data-ttu-id="bd140-620">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-620"></span></span>|
|<span data-ttu-id="bd140-621">**URL OCSP**</span><span class="sxs-lookup"><span data-stu-id="bd140-621">**OCSP URLs**</span></span>|
|<span data-ttu-id="bd140-622">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-622"></span></span>|
   
 <span data-ttu-id="bd140-623">**Affidare autorità di certificazione - L1C**</span><span class="sxs-lookup"><span data-stu-id="bd140-623">**Entrust Certification Authority - L1C**</span></span>
  
||
|:-----|
|<span data-ttu-id="bd140-624">**Oggetto**</span><span class="sxs-lookup"><span data-stu-id="bd140-624">**Subject**</span></span>|
|<span data-ttu-id="bd140-625">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-625"></span></span>|
|<span data-ttu-id="bd140-626">**Autorità di certificazione**</span><span class="sxs-lookup"><span data-stu-id="bd140-626">**Issuer**</span></span>|
|<span data-ttu-id="bd140-627">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-627"></span></span>|
|<span data-ttu-id="bd140-628">**Numero di serie**</span><span class="sxs-lookup"><span data-stu-id="bd140-628">**Serial Number**</span></span>|
|<span data-ttu-id="bd140-629">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-629"></span></span>|
|<span data-ttu-id="bd140-630">**Lunghezza chiave pubblica**</span><span class="sxs-lookup"><span data-stu-id="bd140-630">**Public Key Length**</span></span>|
|<span data-ttu-id="bd140-631">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-631"></span></span>|
|<span data-ttu-id="bd140-632">**Algoritmo di firma**</span><span class="sxs-lookup"><span data-stu-id="bd140-632">**Signature Algorithm**</span></span>|
|<span data-ttu-id="bd140-633">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-633"></span></span>|
|<span data-ttu-id="bd140-634">**Validità non prima**</span><span class="sxs-lookup"><span data-stu-id="bd140-634">**Validity Not Before**</span></span>|
|<span data-ttu-id="bd140-635">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-635"></span></span>|
|<span data-ttu-id="bd140-636">**Validità non dopo**</span><span class="sxs-lookup"><span data-stu-id="bd140-636">**Validity Not After**</span></span>|
|<span data-ttu-id="bd140-637">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-637"></span></span>|
|<span data-ttu-id="bd140-638">**Identificatore chiave del soggetto**</span><span class="sxs-lookup"><span data-stu-id="bd140-638">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="bd140-639">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-639"></span></span>|
|<span data-ttu-id="bd140-640">**Identificatore chiave dell'autorità**</span><span class="sxs-lookup"><span data-stu-id="bd140-640">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="bd140-641">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-641"></span></span>|
|<span data-ttu-id="bd140-642">**Identificazione personale (SHA-1)**</span><span class="sxs-lookup"><span data-stu-id="bd140-642">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="bd140-643">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-643"></span></span>|
|<span data-ttu-id="bd140-644">**Identificazione personale (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="bd140-644">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="bd140-645">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-645"></span></span>|
|<span data-ttu-id="bd140-646">**PIN (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="bd140-646">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="bd140-647">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-647"></span></span>|
|<span data-ttu-id="bd140-648">**URL di revoche di certificati**</span><span class="sxs-lookup"><span data-stu-id="bd140-648">**CRL URLs**</span></span>|
|<span data-ttu-id="bd140-649">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-649"></span></span>|
|<span data-ttu-id="bd140-650">**URL OCSP**</span><span class="sxs-lookup"><span data-stu-id="bd140-650">**OCSP URLs**</span></span>|
|<span data-ttu-id="bd140-651">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-651"></span></span>|
   
 <span data-ttu-id="bd140-652">**Affidare autorità di certificazione - L1K**</span><span class="sxs-lookup"><span data-stu-id="bd140-652">**Entrust Certification Authority - L1K**</span></span>
  
||
|:-----|
|<span data-ttu-id="bd140-653">**Oggetto**</span><span class="sxs-lookup"><span data-stu-id="bd140-653">**Subject**</span></span>|
|<span data-ttu-id="bd140-654">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-654"></span></span>|
|<span data-ttu-id="bd140-655">**Autorità di certificazione**</span><span class="sxs-lookup"><span data-stu-id="bd140-655">**Issuer**</span></span>|
|<span data-ttu-id="bd140-656">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-656"></span></span>|
|<span data-ttu-id="bd140-657">**Numero di serie**</span><span class="sxs-lookup"><span data-stu-id="bd140-657">**Serial Number**</span></span>|
|<span data-ttu-id="bd140-658">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-658"></span></span>|
|<span data-ttu-id="bd140-659">**Lunghezza chiave pubblica**</span><span class="sxs-lookup"><span data-stu-id="bd140-659">**Public Key Length**</span></span>|
|<span data-ttu-id="bd140-660">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-660"></span></span>|
|<span data-ttu-id="bd140-661">**Algoritmo di firma**</span><span class="sxs-lookup"><span data-stu-id="bd140-661">**Signature Algorithm**</span></span>|
|<span data-ttu-id="bd140-662">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-662"></span></span>|
|<span data-ttu-id="bd140-663">**Validità non prima**</span><span class="sxs-lookup"><span data-stu-id="bd140-663">**Validity Not Before**</span></span>|
|<span data-ttu-id="bd140-664">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-664"></span></span>|
|<span data-ttu-id="bd140-665">**Validità non dopo**</span><span class="sxs-lookup"><span data-stu-id="bd140-665">**Validity Not After**</span></span>|
|<span data-ttu-id="bd140-666">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-666"></span></span>|
|<span data-ttu-id="bd140-667">**Identificatore chiave del soggetto**</span><span class="sxs-lookup"><span data-stu-id="bd140-667">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="bd140-668">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-668"></span></span>|
|<span data-ttu-id="bd140-669">**Identificatore chiave dell'autorità**</span><span class="sxs-lookup"><span data-stu-id="bd140-669">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="bd140-670">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-670"></span></span>|
|<span data-ttu-id="bd140-671">**Identificazione personale (SHA-1)**</span><span class="sxs-lookup"><span data-stu-id="bd140-671">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="bd140-672">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-672"></span></span>|
|<span data-ttu-id="bd140-673">**Identificazione personale (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="bd140-673">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="bd140-674">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-674"></span></span>|
|<span data-ttu-id="bd140-675">**PIN (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="bd140-675">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="bd140-676">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-676"></span></span>|
|<span data-ttu-id="bd140-677">**URL di revoche di certificati**</span><span class="sxs-lookup"><span data-stu-id="bd140-677">**CRL URLs**</span></span>|
|<span data-ttu-id="bd140-678">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-678"></span></span>|
|<span data-ttu-id="bd140-679">**URL OCSP**</span><span class="sxs-lookup"><span data-stu-id="bd140-679">**OCSP URLs**</span></span>|
|<span data-ttu-id="bd140-680">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-680"></span></span>|
   
 <span data-ttu-id="bd140-681">**GlobalSign**</span><span class="sxs-lookup"><span data-stu-id="bd140-681">**GlobalSign**</span></span>
  
||
|:-----|
|<span data-ttu-id="bd140-682">**Oggetto**</span><span class="sxs-lookup"><span data-stu-id="bd140-682">**Subject**</span></span>|
|<span data-ttu-id="bd140-683">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-683"></span></span>|
|<span data-ttu-id="bd140-684">**Autorità di certificazione**</span><span class="sxs-lookup"><span data-stu-id="bd140-684">**Issuer**</span></span>|
|<span data-ttu-id="bd140-685">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-685"></span></span>|
|<span data-ttu-id="bd140-686">**Numero di serie**</span><span class="sxs-lookup"><span data-stu-id="bd140-686">**Serial Number**</span></span>|
|<span data-ttu-id="bd140-687">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-687"></span></span>|
|<span data-ttu-id="bd140-688">**Lunghezza chiave pubblica**</span><span class="sxs-lookup"><span data-stu-id="bd140-688">**Public Key Length**</span></span>|
|<span data-ttu-id="bd140-689">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-689"></span></span>|
|<span data-ttu-id="bd140-690">**Algoritmo di firma**</span><span class="sxs-lookup"><span data-stu-id="bd140-690">**Signature Algorithm**</span></span>|
|<span data-ttu-id="bd140-691">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-691"></span></span>|
|<span data-ttu-id="bd140-692">**Validità non prima**</span><span class="sxs-lookup"><span data-stu-id="bd140-692">**Validity Not Before**</span></span>|
|<span data-ttu-id="bd140-693">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-693"></span></span>|
|<span data-ttu-id="bd140-694">**Validità non dopo**</span><span class="sxs-lookup"><span data-stu-id="bd140-694">**Validity Not After**</span></span>|
|<span data-ttu-id="bd140-695">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-695"></span></span>|
|<span data-ttu-id="bd140-696">**Identificatore chiave del soggetto**</span><span class="sxs-lookup"><span data-stu-id="bd140-696">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="bd140-697">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-697"></span></span>|
|<span data-ttu-id="bd140-698">**Identificatore chiave dell'autorità**</span><span class="sxs-lookup"><span data-stu-id="bd140-698">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="bd140-699">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-699"></span></span>|
|<span data-ttu-id="bd140-700">**Identificazione personale (SHA-1)**</span><span class="sxs-lookup"><span data-stu-id="bd140-700">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="bd140-701">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-701"></span></span>|
|<span data-ttu-id="bd140-702">**Identificazione personale (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="bd140-702">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="bd140-703">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-703"></span></span>|
|<span data-ttu-id="bd140-704">**PIN (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="bd140-704">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="bd140-705">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-705"></span></span>|
|<span data-ttu-id="bd140-706">**URL di revoche di certificati**</span><span class="sxs-lookup"><span data-stu-id="bd140-706">**CRL URLs**</span></span>|
|<span data-ttu-id="bd140-707">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-707"></span></span>|
|<span data-ttu-id="bd140-708">**URL OCSP**</span><span class="sxs-lookup"><span data-stu-id="bd140-708">**OCSP URLs**</span></span>|
|<span data-ttu-id="bd140-709">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-709"></span></span>|
   
 <span data-ttu-id="bd140-710">**Versione estesa di convalida CA - SHA256 - G2 GlobalSign**</span><span class="sxs-lookup"><span data-stu-id="bd140-710">**GlobalSign Extended Validation CA - SHA256 - G2**</span></span>
  
||
|:-----|
|<span data-ttu-id="bd140-711">**Oggetto**</span><span class="sxs-lookup"><span data-stu-id="bd140-711">**Subject**</span></span>|
|<span data-ttu-id="bd140-712">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-712"></span></span>|
|<span data-ttu-id="bd140-713">**Autorità di certificazione**</span><span class="sxs-lookup"><span data-stu-id="bd140-713">**Issuer**</span></span>|
|<span data-ttu-id="bd140-714">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-714"></span></span>|
|<span data-ttu-id="bd140-715">**Numero di serie**</span><span class="sxs-lookup"><span data-stu-id="bd140-715">**Serial Number**</span></span>|
|<span data-ttu-id="bd140-716">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-716"></span></span>|
|<span data-ttu-id="bd140-717">**Lunghezza chiave pubblica**</span><span class="sxs-lookup"><span data-stu-id="bd140-717">**Public Key Length**</span></span>|
|<span data-ttu-id="bd140-718">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-718"></span></span>|
|<span data-ttu-id="bd140-719">**Algoritmo di firma**</span><span class="sxs-lookup"><span data-stu-id="bd140-719">**Signature Algorithm**</span></span>|
|<span data-ttu-id="bd140-720">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-720"></span></span>|
|<span data-ttu-id="bd140-721">**Validità non prima**</span><span class="sxs-lookup"><span data-stu-id="bd140-721">**Validity Not Before**</span></span>|
|<span data-ttu-id="bd140-722">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-722"></span></span>|
|<span data-ttu-id="bd140-723">**Validità non dopo**</span><span class="sxs-lookup"><span data-stu-id="bd140-723">**Validity Not After**</span></span>|
|<span data-ttu-id="bd140-724">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-724"></span></span>|
|<span data-ttu-id="bd140-725">**Identificatore chiave del soggetto**</span><span class="sxs-lookup"><span data-stu-id="bd140-725">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="bd140-726">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-726"></span></span>|
|<span data-ttu-id="bd140-727">**Identificatore chiave dell'autorità**</span><span class="sxs-lookup"><span data-stu-id="bd140-727">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="bd140-728">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-728"></span></span>|
|<span data-ttu-id="bd140-729">**Identificazione personale (SHA-1)**</span><span class="sxs-lookup"><span data-stu-id="bd140-729">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="bd140-730">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-730"></span></span>|
|<span data-ttu-id="bd140-731">**Identificazione personale (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="bd140-731">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="bd140-732">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-732"></span></span>|
|<span data-ttu-id="bd140-733">**PIN (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="bd140-733">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="bd140-734">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-734"></span></span>|
|<span data-ttu-id="bd140-735">**URL di revoche di certificati**</span><span class="sxs-lookup"><span data-stu-id="bd140-735">**CRL URLs**</span></span>|
|<span data-ttu-id="bd140-736">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-736"></span></span>|
|<span data-ttu-id="bd140-737">**URL OCSP**</span><span class="sxs-lookup"><span data-stu-id="bd140-737">**OCSP URLs**</span></span>|
|<span data-ttu-id="bd140-738">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-738"></span></span>|
   
 <span data-ttu-id="bd140-739">**Versione estesa di convalida CA - SHA256 - G3 GlobalSign**</span><span class="sxs-lookup"><span data-stu-id="bd140-739">**GlobalSign Extended Validation CA - SHA256 - G3**</span></span>
  
||
|:-----|
|<span data-ttu-id="bd140-740">**Oggetto**</span><span class="sxs-lookup"><span data-stu-id="bd140-740">**Subject**</span></span>|
|<span data-ttu-id="bd140-741">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-741"></span></span>|
|<span data-ttu-id="bd140-742">**Autorità di certificazione**</span><span class="sxs-lookup"><span data-stu-id="bd140-742">**Issuer**</span></span>|
|<span data-ttu-id="bd140-743">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-743"></span></span>|
|<span data-ttu-id="bd140-744">**Numero di serie**</span><span class="sxs-lookup"><span data-stu-id="bd140-744">**Serial Number**</span></span>|
|<span data-ttu-id="bd140-745">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-745"></span></span>|
|<span data-ttu-id="bd140-746">**Lunghezza chiave pubblica**</span><span class="sxs-lookup"><span data-stu-id="bd140-746">**Public Key Length**</span></span>|
|<span data-ttu-id="bd140-747">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-747"></span></span>|
|<span data-ttu-id="bd140-748">**Algoritmo di firma**</span><span class="sxs-lookup"><span data-stu-id="bd140-748">**Signature Algorithm**</span></span>|
|<span data-ttu-id="bd140-749">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-749"></span></span>|
|<span data-ttu-id="bd140-750">**Validità non prima**</span><span class="sxs-lookup"><span data-stu-id="bd140-750">**Validity Not Before**</span></span>|
|<span data-ttu-id="bd140-751">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-751"></span></span>|
|<span data-ttu-id="bd140-752">**Validità non dopo**</span><span class="sxs-lookup"><span data-stu-id="bd140-752">**Validity Not After**</span></span>|
|<span data-ttu-id="bd140-753">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-753"></span></span>|
|<span data-ttu-id="bd140-754">**Identificatore chiave del soggetto**</span><span class="sxs-lookup"><span data-stu-id="bd140-754">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="bd140-755">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-755"></span></span>|
|<span data-ttu-id="bd140-756">**Identificatore chiave dell'autorità**</span><span class="sxs-lookup"><span data-stu-id="bd140-756">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="bd140-757">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-757"></span></span>|
|<span data-ttu-id="bd140-758">**Identificazione personale (SHA-1)**</span><span class="sxs-lookup"><span data-stu-id="bd140-758">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="bd140-759">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-759"></span></span>|
|<span data-ttu-id="bd140-760">**Identificazione personale (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="bd140-760">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="bd140-761">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-761"></span></span>|
|<span data-ttu-id="bd140-762">**PIN (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="bd140-762">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="bd140-763">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-763"></span></span>|
|<span data-ttu-id="bd140-764">**URL di revoche di certificati**</span><span class="sxs-lookup"><span data-stu-id="bd140-764">**CRL URLs**</span></span>|
|<span data-ttu-id="bd140-765">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-765"></span></span>|
|<span data-ttu-id="bd140-766">**URL OCSP**</span><span class="sxs-lookup"><span data-stu-id="bd140-766">**OCSP URLs**</span></span>|
|<span data-ttu-id="bd140-767">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-767"></span></span>|
   
 <span data-ttu-id="bd140-768">**GlobalSign organizzazione convalida CA - SHA256 - G2**</span><span class="sxs-lookup"><span data-stu-id="bd140-768">**GlobalSign Organization Validation CA - SHA256 - G2**</span></span>
  
||
|:-----|
|<span data-ttu-id="bd140-769">**Oggetto**</span><span class="sxs-lookup"><span data-stu-id="bd140-769">**Subject**</span></span>|
|<span data-ttu-id="bd140-770">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-770"></span></span>|
|<span data-ttu-id="bd140-771">**Autorità di certificazione**</span><span class="sxs-lookup"><span data-stu-id="bd140-771">**Issuer**</span></span>|
|<span data-ttu-id="bd140-772">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-772"></span></span>|
|<span data-ttu-id="bd140-773">**Numero di serie**</span><span class="sxs-lookup"><span data-stu-id="bd140-773">**Serial Number**</span></span>|
|<span data-ttu-id="bd140-774">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-774"></span></span>|
|<span data-ttu-id="bd140-775">**Lunghezza chiave pubblica**</span><span class="sxs-lookup"><span data-stu-id="bd140-775">**Public Key Length**</span></span>|
|<span data-ttu-id="bd140-776">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-776"></span></span>|
|<span data-ttu-id="bd140-777">**Algoritmo di firma**</span><span class="sxs-lookup"><span data-stu-id="bd140-777">**Signature Algorithm**</span></span>|
|<span data-ttu-id="bd140-778">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-778"></span></span>|
|<span data-ttu-id="bd140-779">**Validità non prima**</span><span class="sxs-lookup"><span data-stu-id="bd140-779">**Validity Not Before**</span></span>|
|<span data-ttu-id="bd140-780">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-780"></span></span>|
|<span data-ttu-id="bd140-781">**Validità non dopo**</span><span class="sxs-lookup"><span data-stu-id="bd140-781">**Validity Not After**</span></span>|
|<span data-ttu-id="bd140-782">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-782"></span></span>|
|<span data-ttu-id="bd140-783">**Identificatore chiave del soggetto**</span><span class="sxs-lookup"><span data-stu-id="bd140-783">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="bd140-784">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-784"></span></span>|
|<span data-ttu-id="bd140-785">**Identificatore chiave dell'autorità**</span><span class="sxs-lookup"><span data-stu-id="bd140-785">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="bd140-786">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-786"></span></span>|
|<span data-ttu-id="bd140-787">**Identificazione personale (SHA-1)**</span><span class="sxs-lookup"><span data-stu-id="bd140-787">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="bd140-788">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-788"></span></span>|
|<span data-ttu-id="bd140-789">**Identificazione personale (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="bd140-789">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="bd140-790">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-790"></span></span>|
|<span data-ttu-id="bd140-791">**PIN (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="bd140-791">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="bd140-792">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-792"></span></span>|
|<span data-ttu-id="bd140-793">**URL di revoche di certificati**</span><span class="sxs-lookup"><span data-stu-id="bd140-793">**CRL URLs**</span></span>|
|<span data-ttu-id="bd140-794">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-794"></span></span>|
|<span data-ttu-id="bd140-795">**URL OCSP**</span><span class="sxs-lookup"><span data-stu-id="bd140-795">**OCSP URLs**</span></span>|
|<span data-ttu-id="bd140-796">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-796"></span></span>|
   
 <span data-ttu-id="bd140-797">**GlobalSign organizzazione convalida CA - SHA256 - G2**</span><span class="sxs-lookup"><span data-stu-id="bd140-797">**GlobalSign Organization Validation CA - SHA256 - G2**</span></span>
  
||
|:-----|
|<span data-ttu-id="bd140-798">**Oggetto**</span><span class="sxs-lookup"><span data-stu-id="bd140-798">**Subject**</span></span>|
|<span data-ttu-id="bd140-799">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-799"></span></span>|
|<span data-ttu-id="bd140-800">**Autorità di certificazione**</span><span class="sxs-lookup"><span data-stu-id="bd140-800">**Issuer**</span></span>|
|<span data-ttu-id="bd140-801">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-801"></span></span>|
|<span data-ttu-id="bd140-802">**Numero di serie**</span><span class="sxs-lookup"><span data-stu-id="bd140-802">**Serial Number**</span></span>|
|<span data-ttu-id="bd140-803">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-803"></span></span>|
|<span data-ttu-id="bd140-804">**Lunghezza chiave pubblica**</span><span class="sxs-lookup"><span data-stu-id="bd140-804">**Public Key Length**</span></span>|
|<span data-ttu-id="bd140-805">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-805"></span></span>|
|<span data-ttu-id="bd140-806">**Algoritmo di firma**</span><span class="sxs-lookup"><span data-stu-id="bd140-806">**Signature Algorithm**</span></span>|
|<span data-ttu-id="bd140-807">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-807"></span></span>|
|<span data-ttu-id="bd140-808">**Validità non prima**</span><span class="sxs-lookup"><span data-stu-id="bd140-808">**Validity Not Before**</span></span>|
|<span data-ttu-id="bd140-809">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-809"></span></span>|
|<span data-ttu-id="bd140-810">**Validità non dopo**</span><span class="sxs-lookup"><span data-stu-id="bd140-810">**Validity Not After**</span></span>|
|<span data-ttu-id="bd140-811">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-811"></span></span>|
|<span data-ttu-id="bd140-812">**Identificatore chiave del soggetto**</span><span class="sxs-lookup"><span data-stu-id="bd140-812">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="bd140-813">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-813"></span></span>|
|<span data-ttu-id="bd140-814">**Identificatore chiave dell'autorità**</span><span class="sxs-lookup"><span data-stu-id="bd140-814">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="bd140-815">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-815"></span></span>|
|<span data-ttu-id="bd140-816">**Identificazione personale (SHA-1)**</span><span class="sxs-lookup"><span data-stu-id="bd140-816">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="bd140-817">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-817"></span></span>|
|<span data-ttu-id="bd140-818">**Identificazione personale (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="bd140-818">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="bd140-819">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-819"></span></span>|
|<span data-ttu-id="bd140-820">**PIN (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="bd140-820">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="bd140-821">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-821"></span></span>|
|<span data-ttu-id="bd140-822">**URL di revoche di certificati**</span><span class="sxs-lookup"><span data-stu-id="bd140-822">**CRL URLs**</span></span>|
|<span data-ttu-id="bd140-823">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-823"></span></span>|
|<span data-ttu-id="bd140-824">**URL OCSP**</span><span class="sxs-lookup"><span data-stu-id="bd140-824">**OCSP URLs**</span></span>|
|<span data-ttu-id="bd140-825">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-825"></span></span>|
   
 <span data-ttu-id="bd140-826">**Crittografare possiamo autorità X3**</span><span class="sxs-lookup"><span data-stu-id="bd140-826">**Let's Encrypt Authority X3**</span></span>
  
||
|:-----|
|<span data-ttu-id="bd140-827">**Oggetto**</span><span class="sxs-lookup"><span data-stu-id="bd140-827">**Subject**</span></span>|
|<span data-ttu-id="bd140-828">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-828"></span></span>|
|<span data-ttu-id="bd140-829">**Autorità di certificazione**</span><span class="sxs-lookup"><span data-stu-id="bd140-829">**Issuer**</span></span>|
|<span data-ttu-id="bd140-830">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-830"></span></span>|
|<span data-ttu-id="bd140-831">**Numero di serie**</span><span class="sxs-lookup"><span data-stu-id="bd140-831">**Serial Number**</span></span>|
|<span data-ttu-id="bd140-832">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-832"></span></span>|
|<span data-ttu-id="bd140-833">**Lunghezza chiave pubblica**</span><span class="sxs-lookup"><span data-stu-id="bd140-833">**Public Key Length**</span></span>|
|<span data-ttu-id="bd140-834">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-834"></span></span>|
|<span data-ttu-id="bd140-835">**Algoritmo di firma**</span><span class="sxs-lookup"><span data-stu-id="bd140-835">**Signature Algorithm**</span></span>|
|<span data-ttu-id="bd140-836">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-836"></span></span>|
|<span data-ttu-id="bd140-837">**Validità non prima**</span><span class="sxs-lookup"><span data-stu-id="bd140-837">**Validity Not Before**</span></span>|
|<span data-ttu-id="bd140-838">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-838"></span></span>|
|<span data-ttu-id="bd140-839">**Validità non dopo**</span><span class="sxs-lookup"><span data-stu-id="bd140-839">**Validity Not After**</span></span>|
|<span data-ttu-id="bd140-840">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-840"></span></span>|
|<span data-ttu-id="bd140-841">**Identificatore chiave del soggetto**</span><span class="sxs-lookup"><span data-stu-id="bd140-841">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="bd140-842">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-842"></span></span>|
|<span data-ttu-id="bd140-843">**Identificatore chiave dell'autorità**</span><span class="sxs-lookup"><span data-stu-id="bd140-843">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="bd140-844">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-844"></span></span>|
|<span data-ttu-id="bd140-845">**Identificazione personale (SHA-1)**</span><span class="sxs-lookup"><span data-stu-id="bd140-845">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="bd140-846">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-846"></span></span>|
|<span data-ttu-id="bd140-847">**Identificazione personale (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="bd140-847">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="bd140-848">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-848"></span></span>|
|<span data-ttu-id="bd140-849">**PIN (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="bd140-849">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="bd140-850">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-850"></span></span>|
|<span data-ttu-id="bd140-851">**URL AIA**</span><span class="sxs-lookup"><span data-stu-id="bd140-851">**AIA URLs**</span></span>|
|<span data-ttu-id="bd140-852">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-852"></span></span>|
|<span data-ttu-id="bd140-853">**URL di revoche di certificati**</span><span class="sxs-lookup"><span data-stu-id="bd140-853">**CRL URLs**</span></span>|
|<span data-ttu-id="bd140-854">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-854"></span></span>|
|<span data-ttu-id="bd140-855">**URL OCSP**</span><span class="sxs-lookup"><span data-stu-id="bd140-855">**OCSP URLs**</span></span>|
|<span data-ttu-id="bd140-856">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-856"></span></span>|
   
 <span data-ttu-id="bd140-857">**Microsoft IT SSL SHA2**</span><span class="sxs-lookup"><span data-stu-id="bd140-857">**Microsoft IT SSL SHA2**</span></span>
  
||
|:-----|
|<span data-ttu-id="bd140-858">**Oggetto**</span><span class="sxs-lookup"><span data-stu-id="bd140-858">**Subject**</span></span>|
|<span data-ttu-id="bd140-859">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-859"></span></span>|
|<span data-ttu-id="bd140-860">**Autorità di certificazione**</span><span class="sxs-lookup"><span data-stu-id="bd140-860">**Issuer**</span></span>|
|<span data-ttu-id="bd140-861">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-861"></span></span>|
|<span data-ttu-id="bd140-862">**Numero di serie**</span><span class="sxs-lookup"><span data-stu-id="bd140-862">**Serial Number**</span></span>|
|<span data-ttu-id="bd140-863">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-863"></span></span>|
|<span data-ttu-id="bd140-864">**Lunghezza chiave pubblica**</span><span class="sxs-lookup"><span data-stu-id="bd140-864">**Public Key Length**</span></span>|
|<span data-ttu-id="bd140-865">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-865"></span></span>|
|<span data-ttu-id="bd140-866">**Algoritmo di firma**</span><span class="sxs-lookup"><span data-stu-id="bd140-866">**Signature Algorithm**</span></span>|
|<span data-ttu-id="bd140-867">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-867"></span></span>|
|<span data-ttu-id="bd140-868">**Validità non prima**</span><span class="sxs-lookup"><span data-stu-id="bd140-868">**Validity Not Before**</span></span>|
|<span data-ttu-id="bd140-869">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-869"></span></span>|
|<span data-ttu-id="bd140-870">**Validità non dopo**</span><span class="sxs-lookup"><span data-stu-id="bd140-870">**Validity Not After**</span></span>|
|<span data-ttu-id="bd140-871">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-871"></span></span>|
|<span data-ttu-id="bd140-872">**Identificatore chiave del soggetto**</span><span class="sxs-lookup"><span data-stu-id="bd140-872">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="bd140-873">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-873"></span></span>|
|<span data-ttu-id="bd140-874">**Identificatore chiave dell'autorità**</span><span class="sxs-lookup"><span data-stu-id="bd140-874">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="bd140-875">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-875"></span></span>|
|<span data-ttu-id="bd140-876">**Identificazione personale (SHA-1)**</span><span class="sxs-lookup"><span data-stu-id="bd140-876">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="bd140-877">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-877"></span></span>|
|<span data-ttu-id="bd140-878">**Identificazione personale (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="bd140-878">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="bd140-879">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-879"></span></span>|
|<span data-ttu-id="bd140-880">**PIN (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="bd140-880">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="bd140-881">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-881"></span></span>|
|<span data-ttu-id="bd140-882">**URL di revoche di certificati**</span><span class="sxs-lookup"><span data-stu-id="bd140-882">**CRL URLs**</span></span>|
|<span data-ttu-id="bd140-883">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-883"></span></span>|
   
 <span data-ttu-id="bd140-884">**Microsoft IT SSL SHA2**</span><span class="sxs-lookup"><span data-stu-id="bd140-884">**Microsoft IT SSL SHA2**</span></span>
  
||
|:-----|
|<span data-ttu-id="bd140-885">**Oggetto**</span><span class="sxs-lookup"><span data-stu-id="bd140-885">**Subject**</span></span>|
|<span data-ttu-id="bd140-886">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-886"></span></span>|
|<span data-ttu-id="bd140-887">**Autorità di certificazione**</span><span class="sxs-lookup"><span data-stu-id="bd140-887">**Issuer**</span></span>|
|<span data-ttu-id="bd140-888">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-888"></span></span>|
|<span data-ttu-id="bd140-889">**Numero di serie**</span><span class="sxs-lookup"><span data-stu-id="bd140-889">**Serial Number**</span></span>|
|<span data-ttu-id="bd140-890">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-890"></span></span>|
|<span data-ttu-id="bd140-891">**Lunghezza chiave pubblica**</span><span class="sxs-lookup"><span data-stu-id="bd140-891">**Public Key Length**</span></span>|
|<span data-ttu-id="bd140-892">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-892"></span></span>|
|<span data-ttu-id="bd140-893">**Algoritmo di firma**</span><span class="sxs-lookup"><span data-stu-id="bd140-893">**Signature Algorithm**</span></span>|
|<span data-ttu-id="bd140-894">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-894"></span></span>|
|<span data-ttu-id="bd140-895">**Validità non prima**</span><span class="sxs-lookup"><span data-stu-id="bd140-895">**Validity Not Before**</span></span>|
|<span data-ttu-id="bd140-896">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-896"></span></span>|
|<span data-ttu-id="bd140-897">**Validità non dopo**</span><span class="sxs-lookup"><span data-stu-id="bd140-897">**Validity Not After**</span></span>|
|<span data-ttu-id="bd140-898">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-898"></span></span>|
|<span data-ttu-id="bd140-899">**Identificatore chiave del soggetto**</span><span class="sxs-lookup"><span data-stu-id="bd140-899">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="bd140-900">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-900"></span></span>|
|<span data-ttu-id="bd140-901">**Identificatore chiave dell'autorità**</span><span class="sxs-lookup"><span data-stu-id="bd140-901">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="bd140-902">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-902"></span></span>|
|<span data-ttu-id="bd140-903">**Identificazione personale (SHA-1)**</span><span class="sxs-lookup"><span data-stu-id="bd140-903">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="bd140-904">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-904"></span></span>|
|<span data-ttu-id="bd140-905">**Identificazione personale (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="bd140-905">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="bd140-906">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-906"></span></span>|
|<span data-ttu-id="bd140-907">**PIN (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="bd140-907">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="bd140-908">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-908"></span></span>|
|<span data-ttu-id="bd140-909">**URL di revoche di certificati**</span><span class="sxs-lookup"><span data-stu-id="bd140-909">**CRL URLs**</span></span>|
|<span data-ttu-id="bd140-910">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-910"></span></span>|
|<span data-ttu-id="bd140-911">**URL OCSP**</span><span class="sxs-lookup"><span data-stu-id="bd140-911">**OCSP URLs**</span></span>|
|<span data-ttu-id="bd140-912">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-912"></span></span>|
   
 <span data-ttu-id="bd140-913">**Microsoft IT TLS CA 1**</span><span class="sxs-lookup"><span data-stu-id="bd140-913">**Microsoft IT TLS CA 1**</span></span>
  
||
|:-----|
|<span data-ttu-id="bd140-914">**Oggetto**</span><span class="sxs-lookup"><span data-stu-id="bd140-914">**Subject**</span></span>|
|<span data-ttu-id="bd140-915">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-915"></span></span>|
|<span data-ttu-id="bd140-916">**Autorità di certificazione**</span><span class="sxs-lookup"><span data-stu-id="bd140-916">**Issuer**</span></span>|
|<span data-ttu-id="bd140-917">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-917"></span></span>|
|<span data-ttu-id="bd140-918">**Numero di serie**</span><span class="sxs-lookup"><span data-stu-id="bd140-918">**Serial Number**</span></span>|
|<span data-ttu-id="bd140-919">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-919"></span></span>|
|<span data-ttu-id="bd140-920">**Lunghezza chiave pubblica**</span><span class="sxs-lookup"><span data-stu-id="bd140-920">**Public Key Length**</span></span>|
|<span data-ttu-id="bd140-921">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-921"></span></span>|
|<span data-ttu-id="bd140-922">**Algoritmo di firma**</span><span class="sxs-lookup"><span data-stu-id="bd140-922">**Signature Algorithm**</span></span>|
|<span data-ttu-id="bd140-923">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-923"></span></span>|
|<span data-ttu-id="bd140-924">**Validità non prima**</span><span class="sxs-lookup"><span data-stu-id="bd140-924">**Validity Not Before**</span></span>|
|<span data-ttu-id="bd140-925">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-925"></span></span>|
|<span data-ttu-id="bd140-926">**Validità non dopo**</span><span class="sxs-lookup"><span data-stu-id="bd140-926">**Validity Not After**</span></span>|
|<span data-ttu-id="bd140-927">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-927"></span></span>|
|<span data-ttu-id="bd140-928">**Identificatore chiave del soggetto**</span><span class="sxs-lookup"><span data-stu-id="bd140-928">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="bd140-929">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-929"></span></span>|
|<span data-ttu-id="bd140-930">**Identificatore chiave dell'autorità**</span><span class="sxs-lookup"><span data-stu-id="bd140-930">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="bd140-931">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-931"></span></span>|
|<span data-ttu-id="bd140-932">**Identificazione personale (SHA-1)**</span><span class="sxs-lookup"><span data-stu-id="bd140-932">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="bd140-933">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-933"></span></span>|
|<span data-ttu-id="bd140-934">**Identificazione personale (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="bd140-934">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="bd140-935">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-935"></span></span>|
|<span data-ttu-id="bd140-936">**PIN (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="bd140-936">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="bd140-937">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-937"></span></span>|
|<span data-ttu-id="bd140-938">**URL di revoche di certificati**</span><span class="sxs-lookup"><span data-stu-id="bd140-938">**CRL URLs**</span></span>|
|<span data-ttu-id="bd140-939">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-939"></span></span>|
|<span data-ttu-id="bd140-940">**URL OCSP**</span><span class="sxs-lookup"><span data-stu-id="bd140-940">**OCSP URLs**</span></span>|
|<span data-ttu-id="bd140-941">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-941"></span></span>|
   
 <span data-ttu-id="bd140-942">**Microsoft IT TLS CA 2**</span><span class="sxs-lookup"><span data-stu-id="bd140-942">**Microsoft IT TLS CA 2**</span></span>
  
||
|:-----|
|<span data-ttu-id="bd140-943">**Oggetto**</span><span class="sxs-lookup"><span data-stu-id="bd140-943">**Subject**</span></span>|
|<span data-ttu-id="bd140-944">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-944"></span></span>|
|<span data-ttu-id="bd140-945">**Autorità di certificazione**</span><span class="sxs-lookup"><span data-stu-id="bd140-945">**Issuer**</span></span>|
|<span data-ttu-id="bd140-946">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-946"></span></span>|
|<span data-ttu-id="bd140-947">**Numero di serie**</span><span class="sxs-lookup"><span data-stu-id="bd140-947">**Serial Number**</span></span>|
|<span data-ttu-id="bd140-948">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-948"></span></span>|
|<span data-ttu-id="bd140-949">**Lunghezza chiave pubblica**</span><span class="sxs-lookup"><span data-stu-id="bd140-949">**Public Key Length**</span></span>|
|<span data-ttu-id="bd140-950">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-950"></span></span>|
|<span data-ttu-id="bd140-951">**Algoritmo di firma**</span><span class="sxs-lookup"><span data-stu-id="bd140-951">**Signature Algorithm**</span></span>|
|<span data-ttu-id="bd140-952">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-952"></span></span>|
|<span data-ttu-id="bd140-953">**Validità non prima**</span><span class="sxs-lookup"><span data-stu-id="bd140-953">**Validity Not Before**</span></span>|
|<span data-ttu-id="bd140-954">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-954"></span></span>|
|<span data-ttu-id="bd140-955">**Validità non dopo**</span><span class="sxs-lookup"><span data-stu-id="bd140-955">**Validity Not After**</span></span>|
|<span data-ttu-id="bd140-956">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-956"></span></span>|
|<span data-ttu-id="bd140-957">**Identificatore chiave del soggetto**</span><span class="sxs-lookup"><span data-stu-id="bd140-957">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="bd140-958">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-958"></span></span>|
|<span data-ttu-id="bd140-959">**Identificatore chiave dell'autorità**</span><span class="sxs-lookup"><span data-stu-id="bd140-959">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="bd140-960">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-960"></span></span>|
|<span data-ttu-id="bd140-961">**Identificazione personale (SHA-1)**</span><span class="sxs-lookup"><span data-stu-id="bd140-961">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="bd140-962">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-962"></span></span>|
|<span data-ttu-id="bd140-963">**Identificazione personale (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="bd140-963">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="bd140-964">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-964"></span></span>|
|<span data-ttu-id="bd140-965">**PIN (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="bd140-965">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="bd140-966">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-966"></span></span>|
|<span data-ttu-id="bd140-967">**URL di revoche di certificati**</span><span class="sxs-lookup"><span data-stu-id="bd140-967">**CRL URLs**</span></span>|
|<span data-ttu-id="bd140-968">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-968"></span></span>|
|<span data-ttu-id="bd140-969">**URL OCSP**</span><span class="sxs-lookup"><span data-stu-id="bd140-969">**OCSP URLs**</span></span>|
|<span data-ttu-id="bd140-970">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-970"></span></span>|
   
 <span data-ttu-id="bd140-971">**Microsoft IT TLS CA 4**</span><span class="sxs-lookup"><span data-stu-id="bd140-971">**Microsoft IT TLS CA 4**</span></span>
  
||
|:-----|
|<span data-ttu-id="bd140-972">**Oggetto**</span><span class="sxs-lookup"><span data-stu-id="bd140-972">**Subject**</span></span>|
|<span data-ttu-id="bd140-973">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-973"></span></span>|
|<span data-ttu-id="bd140-974">**Autorità di certificazione**</span><span class="sxs-lookup"><span data-stu-id="bd140-974">**Issuer**</span></span>|
|<span data-ttu-id="bd140-975">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-975"></span></span>|
|<span data-ttu-id="bd140-976">**Numero di serie**</span><span class="sxs-lookup"><span data-stu-id="bd140-976">**Serial Number**</span></span>|
|<span data-ttu-id="bd140-977">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-977"></span></span>|
|<span data-ttu-id="bd140-978">**Lunghezza chiave pubblica**</span><span class="sxs-lookup"><span data-stu-id="bd140-978">**Public Key Length**</span></span>|
|<span data-ttu-id="bd140-979">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-979"></span></span>|
|<span data-ttu-id="bd140-980">**Algoritmo di firma**</span><span class="sxs-lookup"><span data-stu-id="bd140-980">**Signature Algorithm**</span></span>|
|<span data-ttu-id="bd140-981">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-981"></span></span>|
|<span data-ttu-id="bd140-982">**Validità non prima**</span><span class="sxs-lookup"><span data-stu-id="bd140-982">**Validity Not Before**</span></span>|
|<span data-ttu-id="bd140-983">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-983"></span></span>|
|<span data-ttu-id="bd140-984">**Validità non dopo**</span><span class="sxs-lookup"><span data-stu-id="bd140-984">**Validity Not After**</span></span>|
|<span data-ttu-id="bd140-985">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-985"></span></span>|
|<span data-ttu-id="bd140-986">**Identificatore chiave del soggetto**</span><span class="sxs-lookup"><span data-stu-id="bd140-986">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="bd140-987">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-987"></span></span>|
|<span data-ttu-id="bd140-988">**Identificatore chiave dell'autorità**</span><span class="sxs-lookup"><span data-stu-id="bd140-988">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="bd140-989">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-989"></span></span>|
|<span data-ttu-id="bd140-990">**Identificazione personale (SHA-1)**</span><span class="sxs-lookup"><span data-stu-id="bd140-990">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="bd140-991">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-991"></span></span>|
|<span data-ttu-id="bd140-992">**Identificazione personale (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="bd140-992">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="bd140-993">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-993"></span></span>|
|<span data-ttu-id="bd140-994">**PIN (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="bd140-994">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="bd140-995">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-995"></span></span>|
|<span data-ttu-id="bd140-996">**URL di revoche di certificati**</span><span class="sxs-lookup"><span data-stu-id="bd140-996">**CRL URLs**</span></span>|
|<span data-ttu-id="bd140-997">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-997"></span></span>|
|<span data-ttu-id="bd140-998">**URL OCSP**</span><span class="sxs-lookup"><span data-stu-id="bd140-998">**OCSP URLs**</span></span>|
|<span data-ttu-id="bd140-999">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-999"></span></span>|
   
 <span data-ttu-id="bd140-1000">**Microsoft IT TLS CA 5**</span><span class="sxs-lookup"><span data-stu-id="bd140-1000">**Microsoft IT TLS CA 5**</span></span>
  
||
|:-----|
|<span data-ttu-id="bd140-1001">**Oggetto**</span><span class="sxs-lookup"><span data-stu-id="bd140-1001">**Subject**</span></span>|
|<span data-ttu-id="bd140-1002">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-1002"></span></span>|
|<span data-ttu-id="bd140-1003">**Autorità di certificazione**</span><span class="sxs-lookup"><span data-stu-id="bd140-1003">**Issuer**</span></span>|
|<span data-ttu-id="bd140-1004">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-1004"></span></span>|
|<span data-ttu-id="bd140-1005">**Numero di serie**</span><span class="sxs-lookup"><span data-stu-id="bd140-1005">**Serial Number**</span></span>|
|<span data-ttu-id="bd140-1006">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-1006"></span></span>|
|<span data-ttu-id="bd140-1007">**Lunghezza chiave pubblica**</span><span class="sxs-lookup"><span data-stu-id="bd140-1007">**Public Key Length**</span></span>|
|<span data-ttu-id="bd140-1008">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-1008"></span></span>|
|<span data-ttu-id="bd140-1009">**Algoritmo di firma**</span><span class="sxs-lookup"><span data-stu-id="bd140-1009">**Signature Algorithm**</span></span>|
|<span data-ttu-id="bd140-1010">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-1010"></span></span>|
|<span data-ttu-id="bd140-1011">**Validità non prima**</span><span class="sxs-lookup"><span data-stu-id="bd140-1011">**Validity Not Before**</span></span>|
|<span data-ttu-id="bd140-1012">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-1012"></span></span>|
|<span data-ttu-id="bd140-1013">**Validità non dopo**</span><span class="sxs-lookup"><span data-stu-id="bd140-1013">**Validity Not After**</span></span>|
|<span data-ttu-id="bd140-1014">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-1014"></span></span>|
|<span data-ttu-id="bd140-1015">**Identificatore chiave del soggetto**</span><span class="sxs-lookup"><span data-stu-id="bd140-1015">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="bd140-1016">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-1016"></span></span>|
|<span data-ttu-id="bd140-1017">**Identificatore chiave dell'autorità**</span><span class="sxs-lookup"><span data-stu-id="bd140-1017">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="bd140-1018">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-1018"></span></span>|
|<span data-ttu-id="bd140-1019">**Identificazione personale (SHA-1)**</span><span class="sxs-lookup"><span data-stu-id="bd140-1019">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="bd140-1020">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-1020"></span></span>|
|<span data-ttu-id="bd140-1021">**Identificazione personale (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="bd140-1021">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="bd140-1022">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-1022"></span></span>|
|<span data-ttu-id="bd140-1023">**PIN (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="bd140-1023">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="bd140-1024">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-1024"></span></span>|
|<span data-ttu-id="bd140-1025">**URL di revoche di certificati**</span><span class="sxs-lookup"><span data-stu-id="bd140-1025">**CRL URLs**</span></span>|
|<span data-ttu-id="bd140-1026">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-1026"></span></span>|
|<span data-ttu-id="bd140-1027">**URL OCSP**</span><span class="sxs-lookup"><span data-stu-id="bd140-1027">**OCSP URLs**</span></span>|
|<span data-ttu-id="bd140-1028">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-1028"></span></span>|
   
 <span data-ttu-id="bd140-1029">**Classe Symantec EV 3 SSL CA - G3**</span><span class="sxs-lookup"><span data-stu-id="bd140-1029">**Symantec Class 3 EV SSL CA - G3**</span></span>
  
||
|:-----|
|<span data-ttu-id="bd140-1030">**Oggetto**</span><span class="sxs-lookup"><span data-stu-id="bd140-1030">**Subject**</span></span>|
|<span data-ttu-id="bd140-1031">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-1031"></span></span>|
|<span data-ttu-id="bd140-1032">**Autorità di certificazione**</span><span class="sxs-lookup"><span data-stu-id="bd140-1032">**Issuer**</span></span>|
|<span data-ttu-id="bd140-1033">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-1033"></span></span>|
|<span data-ttu-id="bd140-1034">**Nome alternativo soggetto**</span><span class="sxs-lookup"><span data-stu-id="bd140-1034">**Subject Alternative Name**</span></span>|
|<span data-ttu-id="bd140-1035">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-1035"></span></span>|
|<span data-ttu-id="bd140-1036">**Numero di serie**</span><span class="sxs-lookup"><span data-stu-id="bd140-1036">**Serial Number**</span></span>|
|<span data-ttu-id="bd140-1037">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-1037"></span></span>|
|<span data-ttu-id="bd140-1038">**Lunghezza chiave pubblica**</span><span class="sxs-lookup"><span data-stu-id="bd140-1038">**Public Key Length**</span></span>|
|<span data-ttu-id="bd140-1039">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-1039"></span></span>|
|<span data-ttu-id="bd140-1040">**Algoritmo di firma**</span><span class="sxs-lookup"><span data-stu-id="bd140-1040">**Signature Algorithm**</span></span>|
|<span data-ttu-id="bd140-1041">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-1041"></span></span>|
|<span data-ttu-id="bd140-1042">**Validità non prima**</span><span class="sxs-lookup"><span data-stu-id="bd140-1042">**Validity Not Before**</span></span>|
|<span data-ttu-id="bd140-1043">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-1043"></span></span>|
|<span data-ttu-id="bd140-1044">**Validità non dopo**</span><span class="sxs-lookup"><span data-stu-id="bd140-1044">**Validity Not After**</span></span>|
|<span data-ttu-id="bd140-1045">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-1045"></span></span>|
|<span data-ttu-id="bd140-1046">**Identificatore chiave del soggetto**</span><span class="sxs-lookup"><span data-stu-id="bd140-1046">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="bd140-1047">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-1047"></span></span>|
|<span data-ttu-id="bd140-1048">**Identificatore chiave dell'autorità**</span><span class="sxs-lookup"><span data-stu-id="bd140-1048">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="bd140-1049">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-1049"></span></span>|
|<span data-ttu-id="bd140-1050">**Identificazione personale (SHA-1)**</span><span class="sxs-lookup"><span data-stu-id="bd140-1050">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="bd140-1051">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-1051"></span></span>|
|<span data-ttu-id="bd140-1052">**Identificazione personale (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="bd140-1052">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="bd140-1053">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-1053"></span></span>|
|<span data-ttu-id="bd140-1054">**PIN (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="bd140-1054">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="bd140-1055">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-1055"></span></span>|
|<span data-ttu-id="bd140-1056">**URL di revoche di certificati**</span><span class="sxs-lookup"><span data-stu-id="bd140-1056">**CRL URLs**</span></span>|
|<span data-ttu-id="bd140-1057">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-1057"></span></span>|
|<span data-ttu-id="bd140-1058">**URL OCSP**</span><span class="sxs-lookup"><span data-stu-id="bd140-1058">**OCSP URLs**</span></span>|
|<span data-ttu-id="bd140-1059">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-1059"></span></span>|
   
 <span data-ttu-id="bd140-1060">**Classe Symantec 3 Server protetta CA - G4**</span><span class="sxs-lookup"><span data-stu-id="bd140-1060">**Symantec Class 3 Secure Server CA - G4**</span></span>
  
||
|:-----|
|<span data-ttu-id="bd140-1061">**Oggetto**</span><span class="sxs-lookup"><span data-stu-id="bd140-1061">**Subject**</span></span>|
|<span data-ttu-id="bd140-1062">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-1062"></span></span>|
|<span data-ttu-id="bd140-1063">**Autorità di certificazione**</span><span class="sxs-lookup"><span data-stu-id="bd140-1063">**Issuer**</span></span>|
|<span data-ttu-id="bd140-1064">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-1064"></span></span>|
|<span data-ttu-id="bd140-1065">**Nome alternativo soggetto**</span><span class="sxs-lookup"><span data-stu-id="bd140-1065">**Subject Alternative Name**</span></span>|
|<span data-ttu-id="bd140-1066">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-1066"></span></span>|
|<span data-ttu-id="bd140-1067">**Numero di serie**</span><span class="sxs-lookup"><span data-stu-id="bd140-1067">**Serial Number**</span></span>|
|<span data-ttu-id="bd140-1068">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-1068"></span></span>|
|<span data-ttu-id="bd140-1069">**Lunghezza chiave pubblica**</span><span class="sxs-lookup"><span data-stu-id="bd140-1069">**Public Key Length**</span></span>|
|<span data-ttu-id="bd140-1070">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-1070"></span></span>|
|<span data-ttu-id="bd140-1071">**Algoritmo di firma**</span><span class="sxs-lookup"><span data-stu-id="bd140-1071">**Signature Algorithm**</span></span>|
|<span data-ttu-id="bd140-1072">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-1072"></span></span>|
|<span data-ttu-id="bd140-1073">**Validità non prima**</span><span class="sxs-lookup"><span data-stu-id="bd140-1073">**Validity Not Before**</span></span>|
|<span data-ttu-id="bd140-1074">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-1074"></span></span>|
|<span data-ttu-id="bd140-1075">**Validità non dopo**</span><span class="sxs-lookup"><span data-stu-id="bd140-1075">**Validity Not After**</span></span>|
|<span data-ttu-id="bd140-1076">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-1076"></span></span>|
|<span data-ttu-id="bd140-1077">**Identificatore chiave del soggetto**</span><span class="sxs-lookup"><span data-stu-id="bd140-1077">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="bd140-1078">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-1078"></span></span>|
|<span data-ttu-id="bd140-1079">**Identificatore chiave dell'autorità**</span><span class="sxs-lookup"><span data-stu-id="bd140-1079">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="bd140-1080">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-1080"></span></span>|
|<span data-ttu-id="bd140-1081">**Identificazione personale (SHA-1)**</span><span class="sxs-lookup"><span data-stu-id="bd140-1081">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="bd140-1082">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-1082"></span></span>|
|<span data-ttu-id="bd140-1083">**Identificazione personale (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="bd140-1083">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="bd140-1084">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-1084"></span></span>|
|<span data-ttu-id="bd140-1085">**PIN (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="bd140-1085">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="bd140-1086">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-1086"></span></span>|
|<span data-ttu-id="bd140-1087">**URL di revoche di certificati**</span><span class="sxs-lookup"><span data-stu-id="bd140-1087">**CRL URLs**</span></span>|
|<span data-ttu-id="bd140-1088">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-1088"></span></span>|
|<span data-ttu-id="bd140-1089">**URL OCSP**</span><span class="sxs-lookup"><span data-stu-id="bd140-1089">**OCSP URLs**</span></span>|
|<span data-ttu-id="bd140-1090">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-1090"></span></span>|
   
 <span data-ttu-id="bd140-1091">**Thawte SHA256 SSL autorità di certificazione**</span><span class="sxs-lookup"><span data-stu-id="bd140-1091">**thawte SHA256 SSL CA**</span></span>
  
||
|:-----|
|<span data-ttu-id="bd140-1092">**Oggetto**</span><span class="sxs-lookup"><span data-stu-id="bd140-1092">**Subject**</span></span>|
|<span data-ttu-id="bd140-1093">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-1093"></span></span>|
|<span data-ttu-id="bd140-1094">**Autorità di certificazione**</span><span class="sxs-lookup"><span data-stu-id="bd140-1094">**Issuer**</span></span>|
|<span data-ttu-id="bd140-1095">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-1095"></span></span>|
|<span data-ttu-id="bd140-1096">**Nome alternativo soggetto**</span><span class="sxs-lookup"><span data-stu-id="bd140-1096">**Subject Alternative Name**</span></span>|
|<span data-ttu-id="bd140-1097">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-1097"></span></span>|
|<span data-ttu-id="bd140-1098">**Numero di serie**</span><span class="sxs-lookup"><span data-stu-id="bd140-1098">**Serial Number**</span></span>|
|<span data-ttu-id="bd140-1099">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-1099"></span></span>|
|<span data-ttu-id="bd140-1100">**Lunghezza chiave pubblica**</span><span class="sxs-lookup"><span data-stu-id="bd140-1100">**Public Key Length**</span></span>|
|<span data-ttu-id="bd140-1101">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-1101"></span></span>|
|<span data-ttu-id="bd140-1102">**Algoritmo di firma**</span><span class="sxs-lookup"><span data-stu-id="bd140-1102">**Signature Algorithm**</span></span>|
|<span data-ttu-id="bd140-1103">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-1103"></span></span>|
|<span data-ttu-id="bd140-1104">**Validità non prima**</span><span class="sxs-lookup"><span data-stu-id="bd140-1104">**Validity Not Before**</span></span>|
|<span data-ttu-id="bd140-1105">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-1105"></span></span>|
|<span data-ttu-id="bd140-1106">**Validità non dopo**</span><span class="sxs-lookup"><span data-stu-id="bd140-1106">**Validity Not After**</span></span>|
|<span data-ttu-id="bd140-1107">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-1107"></span></span>|
|<span data-ttu-id="bd140-1108">**Identificatore chiave del soggetto**</span><span class="sxs-lookup"><span data-stu-id="bd140-1108">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="bd140-1109">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-1109"></span></span>|
|<span data-ttu-id="bd140-1110">**Identificatore chiave dell'autorità**</span><span class="sxs-lookup"><span data-stu-id="bd140-1110">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="bd140-1111">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-1111"></span></span>|
|<span data-ttu-id="bd140-1112">**Identificazione personale (SHA-1)**</span><span class="sxs-lookup"><span data-stu-id="bd140-1112">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="bd140-1113">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-1113"></span></span>|
|<span data-ttu-id="bd140-1114">**Identificazione personale (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="bd140-1114">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="bd140-1115">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-1115"></span></span>|
|<span data-ttu-id="bd140-1116">**PIN (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="bd140-1116">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="bd140-1117">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-1117"></span></span>|
|<span data-ttu-id="bd140-1118">**URL di revoche di certificati**</span><span class="sxs-lookup"><span data-stu-id="bd140-1118">**CRL URLs**</span></span>|
|<span data-ttu-id="bd140-1119">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-1119"></span></span>|
|<span data-ttu-id="bd140-1120">**URL OCSP**</span><span class="sxs-lookup"><span data-stu-id="bd140-1120">**OCSP URLs**</span></span>|
|<span data-ttu-id="bd140-1121">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-1121"></span></span>|
   
 <span data-ttu-id="bd140-1122">**Autorità di certificazione SureServer Verizon Akamai G14-SHA2**</span><span class="sxs-lookup"><span data-stu-id="bd140-1122">**Verizon Akamai SureServer CA G14-SHA2**</span></span>
  
||
|:-----|
|<span data-ttu-id="bd140-1123">**Oggetto**</span><span class="sxs-lookup"><span data-stu-id="bd140-1123">**Subject**</span></span>|
|<span data-ttu-id="bd140-1124">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-1124"></span></span>|
|<span data-ttu-id="bd140-1125">**Autorità di certificazione**</span><span class="sxs-lookup"><span data-stu-id="bd140-1125">**Issuer**</span></span>|
|<span data-ttu-id="bd140-1126">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-1126"></span></span>|
|<span data-ttu-id="bd140-1127">**Numero di serie**</span><span class="sxs-lookup"><span data-stu-id="bd140-1127">**Serial Number**</span></span>|
|<span data-ttu-id="bd140-1128">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-1128"></span></span>|
|<span data-ttu-id="bd140-1129">**Lunghezza chiave pubblica**</span><span class="sxs-lookup"><span data-stu-id="bd140-1129">**Public Key Length**</span></span>|
|<span data-ttu-id="bd140-1130">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-1130"></span></span>|
|<span data-ttu-id="bd140-1131">**Algoritmo di firma**</span><span class="sxs-lookup"><span data-stu-id="bd140-1131">**Signature Algorithm**</span></span>|
|<span data-ttu-id="bd140-1132">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-1132"></span></span>|
|<span data-ttu-id="bd140-1133">**Validità non prima**</span><span class="sxs-lookup"><span data-stu-id="bd140-1133">**Validity Not Before**</span></span>|
|<span data-ttu-id="bd140-1134">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-1134"></span></span>|
|<span data-ttu-id="bd140-1135">**Validità non dopo**</span><span class="sxs-lookup"><span data-stu-id="bd140-1135">**Validity Not After**</span></span>|
|<span data-ttu-id="bd140-1136">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-1136"></span></span>|
|<span data-ttu-id="bd140-1137">**Identificatore chiave del soggetto**</span><span class="sxs-lookup"><span data-stu-id="bd140-1137">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="bd140-1138">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-1138"></span></span>|
|<span data-ttu-id="bd140-1139">**Identificatore chiave dell'autorità**</span><span class="sxs-lookup"><span data-stu-id="bd140-1139">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="bd140-1140">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-1140"></span></span>|
|<span data-ttu-id="bd140-1141">**Identificazione personale (SHA-1)**</span><span class="sxs-lookup"><span data-stu-id="bd140-1141">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="bd140-1142">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-1142"></span></span>|
|<span data-ttu-id="bd140-1143">**Identificazione personale (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="bd140-1143">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="bd140-1144">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-1144"></span></span>|
|<span data-ttu-id="bd140-1145">**PIN (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="bd140-1145">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="bd140-1146">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-1146"></span></span>|
|<span data-ttu-id="bd140-1147">**URL AIA**</span><span class="sxs-lookup"><span data-stu-id="bd140-1147">**AIA URLs**</span></span>|
|<span data-ttu-id="bd140-1148">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-1148"></span></span>|
|<span data-ttu-id="bd140-1149">**URL di revoche di certificati**</span><span class="sxs-lookup"><span data-stu-id="bd140-1149">**CRL URLs**</span></span>|
|<span data-ttu-id="bd140-1150">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-1150"></span></span>|
|<span data-ttu-id="bd140-1151">**URL OCSP**</span><span class="sxs-lookup"><span data-stu-id="bd140-1151">**OCSP URLs**</span></span>|
|<span data-ttu-id="bd140-1152">:-----</span><span class="sxs-lookup"><span data-stu-id="bd140-1152"></span></span>|
   
## <a name="additional-certificate-paths"></a><span data-ttu-id="bd140-1153">Percorsi aggiuntivi certificato</span><span class="sxs-lookup"><span data-stu-id="bd140-1153">Additional certificate paths</span></span>
<span data-ttu-id="bd140-1154"><a name="IntermediateCerts"> </a></span><span class="sxs-lookup"><span data-stu-id="bd140-1154"></span></span>

<span data-ttu-id="bd140-1155">Le operazioni seguenti includono i certificati legacy non vengono inclusi in precedenza e verranno uniti con l'elenco precedente nel tempo.</span><span class="sxs-lookup"><span data-stu-id="bd140-1155">The following include legacy certificates that aren't included above and will be merged with the list above over time.</span></span>
  
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


