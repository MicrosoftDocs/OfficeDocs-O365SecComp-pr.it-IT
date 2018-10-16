---
title: Catena di certificati di Office 365
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 6/26/2018
ms.audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
ROBOTS: NOINDEX, NOFOLLOW
localization_priority: Normal
search.appverid:
- MET150
ms.collection: Ent_O365
ms.assetid: 0c03e6b3-e73f-4316-9e2b-bf4091ae96bb
description: Office 365 si avvale di un numero di provider di certificati differenti. Di seguito vengono descritti l'elenco completo dei certificati radice di Office 365 noti che i clienti possono verificarsi quando si accede a Office 365. Per informazioni sui certificati potrebbe essere necessario installare un'infrastruttura, vedere Plan for dei certificati SSL di terze parti per Office 365. Le seguenti informazioni sul certificato si applica a tutte le istanze di tutto il mondo e nazionali cloud di Office 365.
ms.openlocfilehash: 97e00833e57f8f6b7352650b0efdef51ddba77fa
ms.sourcegitcommit: 659b5f5b38ef7e838cdb44eaa38c18e48d922768
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2018
ms.locfileid: "25575360"
---
# <a name="office-365-certificate-chains"></a><span data-ttu-id="687dd-106">Catena di certificati di Office 365</span><span class="sxs-lookup"><span data-stu-id="687dd-106">Office 365 Certificate Chains</span></span>

<span data-ttu-id="687dd-p102">Office 365 si avvale di un numero di provider di certificati differenti. Di seguito vengono descritti l'elenco completo dei certificati radice di Office 365 noti che i clienti possono verificarsi quando si accede a Office 365. Per informazioni sui certificati potrebbe essere necessario installare un'infrastruttura, vedere [pianificare i certificati SSL di terze parti per Office 365](https://support.office.com/article/b48cdf63-07e0-4cda-8c12-4871590f59ce). Le seguenti informazioni sul certificato si applica a tutte le istanze di tutto il mondo e nazionali cloud di Office 365.</span><span class="sxs-lookup"><span data-stu-id="687dd-p102">Office 365 leverages a number of different certificate providers. The following describes the complete list of known Office 365 root certificates that customers may encounter when accessing Office 365. For information on the certificates you may need to install in your own infrastructure, see [Plan for third-party SSL certificates for Office 365](https://support.office.com/article/b48cdf63-07e0-4cda-8c12-4871590f59ce). The following certificate information applies to all worldwide and national cloud instances of Office 365.</span></span>
  

|<span data-ttu-id="687dd-111">**Tipo di certificato**</span><span class="sxs-lookup"><span data-stu-id="687dd-111">**Certificate type**</span></span>|<span data-ttu-id="687dd-112">**Download P7b**</span><span class="sxs-lookup"><span data-stu-id="687dd-112">**P7b download**</span></span>|<span data-ttu-id="687dd-113">**Endpoint di revoche di certificati**</span><span class="sxs-lookup"><span data-stu-id="687dd-113">**CRL Endpoints**</span></span>|<span data-ttu-id="687dd-114">**Endpoint OCSP**</span><span class="sxs-lookup"><span data-stu-id="687dd-114">**OCSP Endpoints**</span></span>|<span data-ttu-id="687dd-115">**Endpoint AIA**</span><span class="sxs-lookup"><span data-stu-id="687dd-115">**AIA Endpoints**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|[<span data-ttu-id="687dd-116">Pubblicamente attendibili i certificati radice</span><span class="sxs-lookup"><span data-stu-id="687dd-116">Publicly Trusted Root Certificates</span></span>](https://support.office.com/article/0c03e6b3-e73f-4316-9e2b-bf4091ae96bb#rootcerts) <br/> |[<span data-ttu-id="687dd-117">Bundle di certificati radice di Office 365 (P7B)</span><span class="sxs-lookup"><span data-stu-id="687dd-117">Office 365 Root Certificate Bundle (P7B)</span></span>](http://download.microsoft.com/download/A/5/A/A5AE01F3-D19B-4A11-9407-801263CEF72C/O365_Root_Certs_20170321.p7b) <br/> |<span data-ttu-id="687dd-118">CRL.GlobalSign.NET</span><span class="sxs-lookup"><span data-stu-id="687dd-118">crl.globalsign.net</span></span>  <br/> <span data-ttu-id="687dd-119">www.d-trust.NET</span><span class="sxs-lookup"><span data-stu-id="687dd-119">www.d-trust.net</span></span>  <br/> |<span data-ttu-id="687dd-120">N/D</span><span class="sxs-lookup"><span data-stu-id="687dd-120">N/A</span></span>  <br/> |<span data-ttu-id="687dd-121">N/D</span><span class="sxs-lookup"><span data-stu-id="687dd-121">N/A</span></span>  <br/> |
|[<span data-ttu-id="687dd-122">Livello intermedi certificati pubblicamente attendibili</span><span class="sxs-lookup"><span data-stu-id="687dd-122">Publicly Trusted Intermediate Certificates</span></span>](https://support.office.com/article/0c03e6b3-e73f-4316-9e2b-bf4091ae96bb#IntermediateCerts) <br/> |[<span data-ttu-id="687dd-123">Office 365 certificato intermedio Bundle (P7B)</span><span class="sxs-lookup"><span data-stu-id="687dd-123">Office 365 Intermediate Certificate Bundle (P7B)</span></span>](http://download.microsoft.com/download/4/D/5/4D5339A4-0A4A-46AB-AE52-B179DEDA4BEC/O365_Intermediate_Certs_20170321.p7b)  <br/> |<span data-ttu-id="687dd-124">cdp1.Public trust.com</span><span class="sxs-lookup"><span data-stu-id="687dd-124">cdp1.public-trust.com</span></span>  <br/> <span data-ttu-id="687dd-125">CRL.cnnic.CN</span><span class="sxs-lookup"><span data-stu-id="687dd-125">crl.cnnic.cn</span></span>  <br/> <span data-ttu-id="687dd-126">CRL.Entrust.NET</span><span class="sxs-lookup"><span data-stu-id="687dd-126">crl.entrust.net</span></span>  <br/> <span data-ttu-id="687dd-127">CRL.GlobalSign.com</span><span class="sxs-lookup"><span data-stu-id="687dd-127">crl.globalsign.com</span></span>  <br/> <span data-ttu-id="687dd-128">CRL.GlobalSign.NET</span><span class="sxs-lookup"><span data-stu-id="687dd-128">crl.globalsign.net</span></span>  <br/> <span data-ttu-id="687dd-129">CRL.identrust.com</span><span class="sxs-lookup"><span data-stu-id="687dd-129">crl.identrust.com</span></span>  <br/> <span data-ttu-id="687dd-130">CRL.Thawte.com</span><span class="sxs-lookup"><span data-stu-id="687dd-130">crl.thawte.com</span></span>  <br/> <span data-ttu-id="687dd-131">crl3.DigiCert.com</span><span class="sxs-lookup"><span data-stu-id="687dd-131">crl3.digicert.com</span></span>  <br/> <span data-ttu-id="687dd-132">crl4.DigiCert.com</span><span class="sxs-lookup"><span data-stu-id="687dd-132">crl4.digicert.com</span></span>  <br/> <span data-ttu-id="687dd-133">s1.symcb.com</span><span class="sxs-lookup"><span data-stu-id="687dd-133">s1.symcb.com</span></span>  <br/> <span data-ttu-id="687dd-134">www.d-trust.NET</span><span class="sxs-lookup"><span data-stu-id="687dd-134">www.d-trust.net</span></span>  <br/> |<span data-ttu-id="687dd-135">isrg.trustid.OCSP.identrust.com</span><span class="sxs-lookup"><span data-stu-id="687dd-135">isrg.trustid.ocsp.identrust.com</span></span>  <br/> <span data-ttu-id="687dd-136">OCSP.DigiCert.com</span><span class="sxs-lookup"><span data-stu-id="687dd-136">ocsp.digicert.com</span></span>  <br/> <span data-ttu-id="687dd-137">OCSP.Entrust.NET</span><span class="sxs-lookup"><span data-stu-id="687dd-137">ocsp.entrust.net</span></span>  <br/> <span data-ttu-id="687dd-138">OCSP.GlobalSign.com</span><span class="sxs-lookup"><span data-stu-id="687dd-138">ocsp.globalsign.com</span></span>  <br/> <span data-ttu-id="687dd-139">OCSP.omniroot.com</span><span class="sxs-lookup"><span data-stu-id="687dd-139">ocsp.omniroot.com</span></span>  <br/> <span data-ttu-id="687dd-140">OCSP.startssl.com</span><span class="sxs-lookup"><span data-stu-id="687dd-140">ocsp.startssl.com</span></span>  <br/> <span data-ttu-id="687dd-141">OCSP.Thawte.com</span><span class="sxs-lookup"><span data-stu-id="687dd-141">ocsp.thawte.com</span></span>  <br/> <span data-ttu-id="687dd-142">ocsp2.GlobalSign.com</span><span class="sxs-lookup"><span data-stu-id="687dd-142">ocsp2.globalsign.com</span></span>  <br/> <span data-ttu-id="687dd-143">ocspcnnicroot.cnnic.CN</span><span class="sxs-lookup"><span data-stu-id="687dd-143">ocspcnnicroot.cnnic.cn</span></span>  <br/> <span data-ttu-id="687dd-144">radice-c3-ca2-2009.ocsp.d-trust.net</span><span class="sxs-lookup"><span data-stu-id="687dd-144">root-c3-ca2-2009.ocsp.d-trust.net</span></span>  <br/> <span data-ttu-id="687dd-145">Root-C3-CA2-EV-2009.OCSP.d-trust.NET</span><span class="sxs-lookup"><span data-stu-id="687dd-145">root-c3-ca2-ev-2009.ocsp.d-trust.net</span></span>  <br/> <span data-ttu-id="687dd-146">s2.symcb.com</span><span class="sxs-lookup"><span data-stu-id="687dd-146">s2.symcb.com</span></span>  <br/> |<span data-ttu-id="687dd-147">AIA.startssl.com</span><span class="sxs-lookup"><span data-stu-id="687dd-147">aia.startssl.com</span></span>  <br/> <span data-ttu-id="687dd-148">Apps.identrust.com</span><span class="sxs-lookup"><span data-stu-id="687dd-148">apps.identrust.com</span></span>  <br/> <span data-ttu-id="687dd-149">cacert.omniroot.com</span><span class="sxs-lookup"><span data-stu-id="687dd-149">cacert.omniroot.com</span></span>  <br/> <span data-ttu-id="687dd-150">www.cnnic.CN</span><span class="sxs-lookup"><span data-stu-id="687dd-150">www.cnnic.cn</span></span>  <br/> |
   
<span data-ttu-id="687dd-151">Espandere il nodo radice e intermedio nelle sezioni seguenti per visualizzare ulteriori informazioni sui provider di certificati.</span><span class="sxs-lookup"><span data-stu-id="687dd-151">Expand the root and intermediate sections below to see additional details about the certificate providers.</span></span>
  
## <a name="office-365-root-certificate-details"></a><span data-ttu-id="687dd-152">Dettagli del certificato radice di Office 365</span><span class="sxs-lookup"><span data-stu-id="687dd-152">Office 365 Root Certificate Details</span></span>
<span data-ttu-id="687dd-153"><a name="RootCerts"> </a></span><span class="sxs-lookup"><span data-stu-id="687dd-153"></span></span>

 <span data-ttu-id="687dd-154">**Baltimore CyberTrust Root**</span><span class="sxs-lookup"><span data-stu-id="687dd-154">**Baltimore CyberTrust Root**</span></span>
  
<span data-ttu-id="687dd-155">|:-----|</span><span class="sxs-lookup"><span data-stu-id="687dd-155">|:-----|</span></span>
|<span data-ttu-id="687dd-156">**Oggetto**</span><span class="sxs-lookup"><span data-stu-id="687dd-156">**Subject**</span></span>|
|:-----|
|<span data-ttu-id="687dd-157">**Numero di serie**</span><span class="sxs-lookup"><span data-stu-id="687dd-157">**Serial Number**</span></span>|
|<span data-ttu-id="687dd-158">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-158"></span></span>|
|<span data-ttu-id="687dd-159">**Lunghezza chiave pubblica**</span><span class="sxs-lookup"><span data-stu-id="687dd-159">**Public Key Length**</span></span>|
|<span data-ttu-id="687dd-160">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-160"></span></span>|
|<span data-ttu-id="687dd-161">**Algoritmo di firma**</span><span class="sxs-lookup"><span data-stu-id="687dd-161">**Signature Algorithm**</span></span>|
|<span data-ttu-id="687dd-162">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-162"></span></span>|
|<span data-ttu-id="687dd-163">**Validità non prima**</span><span class="sxs-lookup"><span data-stu-id="687dd-163">**Validity Not Before**</span></span>|
|<span data-ttu-id="687dd-164">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-164"></span></span>|
|<span data-ttu-id="687dd-165">**Validità non dopo**</span><span class="sxs-lookup"><span data-stu-id="687dd-165">**Validity Not After**</span></span>|
|<span data-ttu-id="687dd-166">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-166"></span></span>|
|<span data-ttu-id="687dd-167">**Identificatore chiave del soggetto**</span><span class="sxs-lookup"><span data-stu-id="687dd-167">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="687dd-168">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-168"></span></span>|
|<span data-ttu-id="687dd-169">**Identificazione personale (SHA-1)**</span><span class="sxs-lookup"><span data-stu-id="687dd-169">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="687dd-170">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-170"></span></span>|
|<span data-ttu-id="687dd-171">**Identificazione personale (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="687dd-171">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="687dd-172">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-172"></span></span>|
|<span data-ttu-id="687dd-173">**PIN (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="687dd-173">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="687dd-174">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-174"></span></span>|
   
 <span data-ttu-id="687dd-175">**RADICE CNNIC**</span><span class="sxs-lookup"><span data-stu-id="687dd-175">**CNNIC ROOT**</span></span>
  
||
|:-----|
|<span data-ttu-id="687dd-176">**Oggetto**</span><span class="sxs-lookup"><span data-stu-id="687dd-176">**Subject**</span></span>|
|<span data-ttu-id="687dd-177">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-177"></span></span>|
|<span data-ttu-id="687dd-178">**Numero di serie**</span><span class="sxs-lookup"><span data-stu-id="687dd-178">**Serial Number**</span></span>|
|<span data-ttu-id="687dd-179">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-179"></span></span>|
|<span data-ttu-id="687dd-180">**Lunghezza chiave pubblica**</span><span class="sxs-lookup"><span data-stu-id="687dd-180">**Public Key Length**</span></span>|
|<span data-ttu-id="687dd-181">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-181"></span></span>|
|<span data-ttu-id="687dd-182">**Algoritmo di firma**</span><span class="sxs-lookup"><span data-stu-id="687dd-182">**Signature Algorithm**</span></span>|
|<span data-ttu-id="687dd-183">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-183"></span></span>|
|<span data-ttu-id="687dd-184">**Validità non prima**</span><span class="sxs-lookup"><span data-stu-id="687dd-184">**Validity Not Before**</span></span>|
|<span data-ttu-id="687dd-185">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-185"></span></span>|
|<span data-ttu-id="687dd-186">**Validità non dopo**</span><span class="sxs-lookup"><span data-stu-id="687dd-186">**Validity Not After**</span></span>|
|<span data-ttu-id="687dd-187">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-187"></span></span>|
|<span data-ttu-id="687dd-188">**Identificatore chiave del soggetto**</span><span class="sxs-lookup"><span data-stu-id="687dd-188">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="687dd-189">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-189"></span></span>|
|<span data-ttu-id="687dd-190">**Identificatore chiave dell'autorità**</span><span class="sxs-lookup"><span data-stu-id="687dd-190">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="687dd-191">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-191"></span></span>|
|<span data-ttu-id="687dd-192">**Identificazione personale (SHA-1)**</span><span class="sxs-lookup"><span data-stu-id="687dd-192">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="687dd-193">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-193"></span></span>|
|<span data-ttu-id="687dd-194">**Identificazione personale (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="687dd-194">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="687dd-195">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-195"></span></span>|
|<span data-ttu-id="687dd-196">**PIN (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="687dd-196">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="687dd-197">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-197"></span></span>|
   
 <span data-ttu-id="687dd-198">**Autorità di certificazione radice globale DigiCert**</span><span class="sxs-lookup"><span data-stu-id="687dd-198">**DigiCert Global Root CA**</span></span>
  
||
|:-----|
|<span data-ttu-id="687dd-199">**Oggetto**</span><span class="sxs-lookup"><span data-stu-id="687dd-199">**Subject**</span></span>|
|<span data-ttu-id="687dd-200">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-200"></span></span>|
|<span data-ttu-id="687dd-201">**Numero di serie**</span><span class="sxs-lookup"><span data-stu-id="687dd-201">**Serial Number**</span></span>|
|<span data-ttu-id="687dd-202">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-202"></span></span>|
|<span data-ttu-id="687dd-203">**Lunghezza chiave pubblica**</span><span class="sxs-lookup"><span data-stu-id="687dd-203">**Public Key Length**</span></span>|
|<span data-ttu-id="687dd-204">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-204"></span></span>|
|<span data-ttu-id="687dd-205">**Algoritmo di firma**</span><span class="sxs-lookup"><span data-stu-id="687dd-205">**Signature Algorithm**</span></span>|
|<span data-ttu-id="687dd-206">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-206"></span></span>|
|<span data-ttu-id="687dd-207">**Validità non prima**</span><span class="sxs-lookup"><span data-stu-id="687dd-207">**Validity Not Before**</span></span>|
|<span data-ttu-id="687dd-208">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-208"></span></span>|
|<span data-ttu-id="687dd-209">**Validità non dopo**</span><span class="sxs-lookup"><span data-stu-id="687dd-209">**Validity Not After**</span></span>|
|<span data-ttu-id="687dd-210">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-210"></span></span>|
|<span data-ttu-id="687dd-211">**Identificatore chiave del soggetto**</span><span class="sxs-lookup"><span data-stu-id="687dd-211">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="687dd-212">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-212"></span></span>|
|<span data-ttu-id="687dd-213">**Identificatore chiave dell'autorità**</span><span class="sxs-lookup"><span data-stu-id="687dd-213">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="687dd-214">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-214"></span></span>|
|<span data-ttu-id="687dd-215">**Identificazione personale (SHA-1)**</span><span class="sxs-lookup"><span data-stu-id="687dd-215">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="687dd-216">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-216"></span></span>|
|<span data-ttu-id="687dd-217">**Identificazione personale (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="687dd-217">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="687dd-218">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-218"></span></span>|
|<span data-ttu-id="687dd-219">**PIN (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="687dd-219">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="687dd-220">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-220"></span></span>|
   
 <span data-ttu-id="687dd-221">**Autorità di certificazione radice convalida estesa con garanzia elevata DigiCert**</span><span class="sxs-lookup"><span data-stu-id="687dd-221">**DigiCert High Assurance EV Root CA**</span></span>
  
||
|:-----|
|<span data-ttu-id="687dd-222">**Oggetto**</span><span class="sxs-lookup"><span data-stu-id="687dd-222">**Subject**</span></span>|
|<span data-ttu-id="687dd-223">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-223"></span></span>|
|<span data-ttu-id="687dd-224">**Numero di serie**</span><span class="sxs-lookup"><span data-stu-id="687dd-224">**Serial Number**</span></span>|
|<span data-ttu-id="687dd-225">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-225"></span></span>|
|<span data-ttu-id="687dd-226">**Lunghezza chiave pubblica**</span><span class="sxs-lookup"><span data-stu-id="687dd-226">**Public Key Length**</span></span>|
|<span data-ttu-id="687dd-227">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-227"></span></span>|
|<span data-ttu-id="687dd-228">**Algoritmo di firma**</span><span class="sxs-lookup"><span data-stu-id="687dd-228">**Signature Algorithm**</span></span>|
|<span data-ttu-id="687dd-229">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-229"></span></span>|
|<span data-ttu-id="687dd-230">**Validità non prima**</span><span class="sxs-lookup"><span data-stu-id="687dd-230">**Validity Not Before**</span></span>|
|<span data-ttu-id="687dd-231">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-231"></span></span>|
|<span data-ttu-id="687dd-232">**Validità non dopo**</span><span class="sxs-lookup"><span data-stu-id="687dd-232">**Validity Not After**</span></span>|
|<span data-ttu-id="687dd-233">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-233"></span></span>|
|<span data-ttu-id="687dd-234">**Identificatore chiave del soggetto**</span><span class="sxs-lookup"><span data-stu-id="687dd-234">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="687dd-235">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-235"></span></span>|
|<span data-ttu-id="687dd-236">**Identificatore chiave dell'autorità**</span><span class="sxs-lookup"><span data-stu-id="687dd-236">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="687dd-237">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-237"></span></span>|
|<span data-ttu-id="687dd-238">**Identificazione personale (SHA-1)**</span><span class="sxs-lookup"><span data-stu-id="687dd-238">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="687dd-239">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-239"></span></span>|
|<span data-ttu-id="687dd-240">**Identificazione personale (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="687dd-240">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="687dd-241">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-241"></span></span>|
|<span data-ttu-id="687dd-242">**PIN (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="687dd-242">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="687dd-243">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-243"></span></span>|
   
 <span data-ttu-id="687dd-244">**Autorità di certificazione radice D protezione classe 3 2 2009**</span><span class="sxs-lookup"><span data-stu-id="687dd-244">**D-TRUST Root Class 3 CA 2 2009**</span></span>
  
||
|:-----|
|<span data-ttu-id="687dd-245">**Oggetto**</span><span class="sxs-lookup"><span data-stu-id="687dd-245">**Subject**</span></span>|
|<span data-ttu-id="687dd-246">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-246"></span></span>|
|<span data-ttu-id="687dd-247">**Numero di serie**</span><span class="sxs-lookup"><span data-stu-id="687dd-247">**Serial Number**</span></span>|
|<span data-ttu-id="687dd-248">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-248"></span></span>|
|<span data-ttu-id="687dd-249">**Lunghezza chiave pubblica**</span><span class="sxs-lookup"><span data-stu-id="687dd-249">**Public Key Length**</span></span>|
|<span data-ttu-id="687dd-250">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-250"></span></span>|
|<span data-ttu-id="687dd-251">**Algoritmo di firma**</span><span class="sxs-lookup"><span data-stu-id="687dd-251">**Signature Algorithm**</span></span>|
|<span data-ttu-id="687dd-252">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-252"></span></span>|
|<span data-ttu-id="687dd-253">**Validità non prima**</span><span class="sxs-lookup"><span data-stu-id="687dd-253">**Validity Not Before**</span></span>|
|<span data-ttu-id="687dd-254">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-254"></span></span>|
|<span data-ttu-id="687dd-255">**Validità non dopo**</span><span class="sxs-lookup"><span data-stu-id="687dd-255">**Validity Not After**</span></span>|
|<span data-ttu-id="687dd-256">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-256"></span></span>|
|<span data-ttu-id="687dd-257">**Identificatore chiave del soggetto**</span><span class="sxs-lookup"><span data-stu-id="687dd-257">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="687dd-258">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-258"></span></span>|
|<span data-ttu-id="687dd-259">**Identificazione personale (SHA-1)**</span><span class="sxs-lookup"><span data-stu-id="687dd-259">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="687dd-260">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-260"></span></span>|
|<span data-ttu-id="687dd-261">**Identificazione personale (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="687dd-261">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="687dd-262">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-262"></span></span>|
|<span data-ttu-id="687dd-263">**PIN (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="687dd-263">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="687dd-264">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-264"></span></span>|
|<span data-ttu-id="687dd-265">**URL di revoche di certificati**</span><span class="sxs-lookup"><span data-stu-id="687dd-265">**CRL URLs**</span></span>|
|<span data-ttu-id="687dd-266">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-266"></span></span>|
   
 <span data-ttu-id="687dd-267">**D-TRUST radice classe 3 CA 2 EV 2009**</span><span class="sxs-lookup"><span data-stu-id="687dd-267">**D-TRUST Root Class 3 CA 2 EV 2009**</span></span>
  
||
|:-----|
|<span data-ttu-id="687dd-268">**Oggetto**</span><span class="sxs-lookup"><span data-stu-id="687dd-268">**Subject**</span></span>|
|<span data-ttu-id="687dd-269">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-269"></span></span>|
|<span data-ttu-id="687dd-270">**Numero di serie**</span><span class="sxs-lookup"><span data-stu-id="687dd-270">**Serial Number**</span></span>|
|<span data-ttu-id="687dd-271">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-271"></span></span>|
|<span data-ttu-id="687dd-272">**Lunghezza chiave pubblica**</span><span class="sxs-lookup"><span data-stu-id="687dd-272">**Public Key Length**</span></span>|
|<span data-ttu-id="687dd-273">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-273"></span></span>|
|<span data-ttu-id="687dd-274">**Algoritmo di firma**</span><span class="sxs-lookup"><span data-stu-id="687dd-274">**Signature Algorithm**</span></span>|
|<span data-ttu-id="687dd-275">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-275"></span></span>|
|<span data-ttu-id="687dd-276">**Validità non prima**</span><span class="sxs-lookup"><span data-stu-id="687dd-276">**Validity Not Before**</span></span>|
|<span data-ttu-id="687dd-277">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-277"></span></span>|
|<span data-ttu-id="687dd-278">**Validità non dopo**</span><span class="sxs-lookup"><span data-stu-id="687dd-278">**Validity Not After**</span></span>|
|<span data-ttu-id="687dd-279">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-279"></span></span>|
|<span data-ttu-id="687dd-280">**Identificatore chiave del soggetto**</span><span class="sxs-lookup"><span data-stu-id="687dd-280">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="687dd-281">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-281"></span></span>|
|<span data-ttu-id="687dd-282">**Identificazione personale (SHA-1)**</span><span class="sxs-lookup"><span data-stu-id="687dd-282">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="687dd-283">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-283"></span></span>|
|<span data-ttu-id="687dd-284">**Identificazione personale (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="687dd-284">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="687dd-285">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-285"></span></span>|
|<span data-ttu-id="687dd-286">**PIN (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="687dd-286">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="687dd-287">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-287"></span></span>|
|<span data-ttu-id="687dd-288">**URL di revoche di certificati**</span><span class="sxs-lookup"><span data-stu-id="687dd-288">**CRL URLs**</span></span>|
|<span data-ttu-id="687dd-289">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-289"></span></span>|
   
 <span data-ttu-id="687dd-290">**LEGALE rootca X3**</span><span class="sxs-lookup"><span data-stu-id="687dd-290">**DST Root CA X3**</span></span>
  
||
|:-----|
|<span data-ttu-id="687dd-291">**Oggetto**</span><span class="sxs-lookup"><span data-stu-id="687dd-291">**Subject**</span></span>|
|<span data-ttu-id="687dd-292">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-292"></span></span>|
|<span data-ttu-id="687dd-293">**Numero di serie**</span><span class="sxs-lookup"><span data-stu-id="687dd-293">**Serial Number**</span></span>|
|<span data-ttu-id="687dd-294">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-294"></span></span>|
|<span data-ttu-id="687dd-295">**Lunghezza chiave pubblica**</span><span class="sxs-lookup"><span data-stu-id="687dd-295">**Public Key Length**</span></span>|
|<span data-ttu-id="687dd-296">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-296"></span></span>|
|<span data-ttu-id="687dd-297">**Algoritmo di firma**</span><span class="sxs-lookup"><span data-stu-id="687dd-297">**Signature Algorithm**</span></span>|
|<span data-ttu-id="687dd-298">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-298"></span></span>|
|<span data-ttu-id="687dd-299">**Validità non prima**</span><span class="sxs-lookup"><span data-stu-id="687dd-299">**Validity Not Before**</span></span>|
|<span data-ttu-id="687dd-300">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-300"></span></span>|
|<span data-ttu-id="687dd-301">**Validità non dopo**</span><span class="sxs-lookup"><span data-stu-id="687dd-301">**Validity Not After**</span></span>|
|<span data-ttu-id="687dd-302">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-302"></span></span>|
|<span data-ttu-id="687dd-303">**Identificatore chiave del soggetto**</span><span class="sxs-lookup"><span data-stu-id="687dd-303">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="687dd-304">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-304"></span></span>|
|<span data-ttu-id="687dd-305">**Identificazione personale (SHA-1)**</span><span class="sxs-lookup"><span data-stu-id="687dd-305">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="687dd-306">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-306"></span></span>|
|<span data-ttu-id="687dd-307">**Identificazione personale (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="687dd-307">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="687dd-308">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-308"></span></span>|
|<span data-ttu-id="687dd-309">**PIN (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="687dd-309">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="687dd-310">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-310"></span></span>|
   
 <span data-ttu-id="687dd-311">**Affidare autorità di certificazione radice - G2**</span><span class="sxs-lookup"><span data-stu-id="687dd-311">**Entrust Root Certification Authority - G2**</span></span>
  
||
|:-----|
|<span data-ttu-id="687dd-312">**Oggetto**</span><span class="sxs-lookup"><span data-stu-id="687dd-312">**Subject**</span></span>|
|<span data-ttu-id="687dd-313">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-313"></span></span>|
|<span data-ttu-id="687dd-314">**Numero di serie**</span><span class="sxs-lookup"><span data-stu-id="687dd-314">**Serial Number**</span></span>|
|<span data-ttu-id="687dd-315">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-315"></span></span>|
|<span data-ttu-id="687dd-316">**Lunghezza chiave pubblica**</span><span class="sxs-lookup"><span data-stu-id="687dd-316">**Public Key Length**</span></span>|
|<span data-ttu-id="687dd-317">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-317"></span></span>|
|<span data-ttu-id="687dd-318">**Algoritmo di firma**</span><span class="sxs-lookup"><span data-stu-id="687dd-318">**Signature Algorithm**</span></span>|
|<span data-ttu-id="687dd-319">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-319"></span></span>|
|<span data-ttu-id="687dd-320">**Validità non prima**</span><span class="sxs-lookup"><span data-stu-id="687dd-320">**Validity Not Before**</span></span>|
|<span data-ttu-id="687dd-321">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-321"></span></span>|
|<span data-ttu-id="687dd-322">**Validità non dopo**</span><span class="sxs-lookup"><span data-stu-id="687dd-322">**Validity Not After**</span></span>|
|<span data-ttu-id="687dd-323">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-323"></span></span>|
|<span data-ttu-id="687dd-324">**Identificatore chiave del soggetto**</span><span class="sxs-lookup"><span data-stu-id="687dd-324">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="687dd-325">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-325"></span></span>|
|<span data-ttu-id="687dd-326">**Identificazione personale (SHA-1)**</span><span class="sxs-lookup"><span data-stu-id="687dd-326">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="687dd-327">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-327"></span></span>|
|<span data-ttu-id="687dd-328">**Identificazione personale (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="687dd-328">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="687dd-329">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-329"></span></span>|
|<span data-ttu-id="687dd-330">**PIN (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="687dd-330">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="687dd-331">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-331"></span></span>|
   
 <span data-ttu-id="687dd-332">**Entrust.net Certification Authority (2048)**</span><span class="sxs-lookup"><span data-stu-id="687dd-332">**Entrust.net Certification Authority (2048)**</span></span>
  
||
|:-----|
|<span data-ttu-id="687dd-333">**Oggetto**</span><span class="sxs-lookup"><span data-stu-id="687dd-333">**Subject**</span></span>|
|<span data-ttu-id="687dd-334">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-334"></span></span>|
|<span data-ttu-id="687dd-335">**Numero di serie**</span><span class="sxs-lookup"><span data-stu-id="687dd-335">**Serial Number**</span></span>|
|<span data-ttu-id="687dd-336">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-336"></span></span>|
|<span data-ttu-id="687dd-337">**Lunghezza chiave pubblica**</span><span class="sxs-lookup"><span data-stu-id="687dd-337">**Public Key Length**</span></span>|
|<span data-ttu-id="687dd-338">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-338"></span></span>|
|<span data-ttu-id="687dd-339">**Algoritmo di firma**</span><span class="sxs-lookup"><span data-stu-id="687dd-339">**Signature Algorithm**</span></span>|
|<span data-ttu-id="687dd-340">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-340"></span></span>|
|<span data-ttu-id="687dd-341">**Validità non prima**</span><span class="sxs-lookup"><span data-stu-id="687dd-341">**Validity Not Before**</span></span>|
|<span data-ttu-id="687dd-342">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-342"></span></span>|
|<span data-ttu-id="687dd-343">**Validità non dopo**</span><span class="sxs-lookup"><span data-stu-id="687dd-343">**Validity Not After**</span></span>|
|<span data-ttu-id="687dd-344">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-344"></span></span>|
|<span data-ttu-id="687dd-345">**Identificatore chiave del soggetto**</span><span class="sxs-lookup"><span data-stu-id="687dd-345">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="687dd-346">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-346"></span></span>|
|<span data-ttu-id="687dd-347">**Identificazione personale (SHA-1)**</span><span class="sxs-lookup"><span data-stu-id="687dd-347">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="687dd-348">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-348"></span></span>|
|<span data-ttu-id="687dd-349">**Identificazione personale (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="687dd-349">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="687dd-350">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-350"></span></span>|
|<span data-ttu-id="687dd-351">**PIN (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="687dd-351">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="687dd-352">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-352"></span></span>|
   
 <span data-ttu-id="687dd-353">**GlobalSign**</span><span class="sxs-lookup"><span data-stu-id="687dd-353">**GlobalSign**</span></span>
  
||
|:-----|
|<span data-ttu-id="687dd-354">**Oggetto**</span><span class="sxs-lookup"><span data-stu-id="687dd-354">**Subject**</span></span>|
|<span data-ttu-id="687dd-355">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-355"></span></span>|
|<span data-ttu-id="687dd-356">**Numero di serie**</span><span class="sxs-lookup"><span data-stu-id="687dd-356">**Serial Number**</span></span>|
|<span data-ttu-id="687dd-357">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-357"></span></span>|
|<span data-ttu-id="687dd-358">**Lunghezza chiave pubblica**</span><span class="sxs-lookup"><span data-stu-id="687dd-358">**Public Key Length**</span></span>|
|<span data-ttu-id="687dd-359">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-359"></span></span>|
|<span data-ttu-id="687dd-360">**Algoritmo di firma**</span><span class="sxs-lookup"><span data-stu-id="687dd-360">**Signature Algorithm**</span></span>|
|<span data-ttu-id="687dd-361">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-361"></span></span>|
|<span data-ttu-id="687dd-362">**Validità non prima**</span><span class="sxs-lookup"><span data-stu-id="687dd-362">**Validity Not Before**</span></span>|
|<span data-ttu-id="687dd-363">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-363"></span></span>|
|<span data-ttu-id="687dd-364">**Validità non dopo**</span><span class="sxs-lookup"><span data-stu-id="687dd-364">**Validity Not After**</span></span>|
|<span data-ttu-id="687dd-365">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-365"></span></span>|
|<span data-ttu-id="687dd-366">**Identificatore chiave del soggetto**</span><span class="sxs-lookup"><span data-stu-id="687dd-366">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="687dd-367">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-367"></span></span>|
|<span data-ttu-id="687dd-368">**Identificatore chiave dell'autorità**</span><span class="sxs-lookup"><span data-stu-id="687dd-368">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="687dd-369">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-369"></span></span>|
|<span data-ttu-id="687dd-370">**Identificazione personale (SHA-1)**</span><span class="sxs-lookup"><span data-stu-id="687dd-370">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="687dd-371">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-371"></span></span>|
|<span data-ttu-id="687dd-372">**Identificazione personale (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="687dd-372">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="687dd-373">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-373"></span></span>|
|<span data-ttu-id="687dd-374">**PIN (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="687dd-374">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="687dd-375">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-375"></span></span>|
|<span data-ttu-id="687dd-376">**URL di revoche di certificati**</span><span class="sxs-lookup"><span data-stu-id="687dd-376">**CRL URLs**</span></span>|
|<span data-ttu-id="687dd-377">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-377"></span></span>|
   
 <span data-ttu-id="687dd-378">**GlobalSign Root CA**</span><span class="sxs-lookup"><span data-stu-id="687dd-378">**GlobalSign Root CA**</span></span>
  
||
|:-----|
|<span data-ttu-id="687dd-379">**Oggetto**</span><span class="sxs-lookup"><span data-stu-id="687dd-379">**Subject**</span></span>|
|<span data-ttu-id="687dd-380">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-380"></span></span>|
|<span data-ttu-id="687dd-381">**Numero di serie**</span><span class="sxs-lookup"><span data-stu-id="687dd-381">**Serial Number**</span></span>|
|<span data-ttu-id="687dd-382">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-382"></span></span>|
|<span data-ttu-id="687dd-383">**Lunghezza chiave pubblica**</span><span class="sxs-lookup"><span data-stu-id="687dd-383">**Public Key Length**</span></span>|
|<span data-ttu-id="687dd-384">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-384"></span></span>|
|<span data-ttu-id="687dd-385">**Algoritmo di firma**</span><span class="sxs-lookup"><span data-stu-id="687dd-385">**Signature Algorithm**</span></span>|
|<span data-ttu-id="687dd-386">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-386"></span></span>|
|<span data-ttu-id="687dd-387">**Validità non prima**</span><span class="sxs-lookup"><span data-stu-id="687dd-387">**Validity Not Before**</span></span>|
|<span data-ttu-id="687dd-388">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-388"></span></span>|
|<span data-ttu-id="687dd-389">**Validità non dopo**</span><span class="sxs-lookup"><span data-stu-id="687dd-389">**Validity Not After**</span></span>|
|<span data-ttu-id="687dd-390">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-390"></span></span>|
|<span data-ttu-id="687dd-391">**Identificatore chiave del soggetto**</span><span class="sxs-lookup"><span data-stu-id="687dd-391">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="687dd-392">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-392"></span></span>|
|<span data-ttu-id="687dd-393">**Identificazione personale (SHA-1)**</span><span class="sxs-lookup"><span data-stu-id="687dd-393">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="687dd-394">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-394"></span></span>|
|<span data-ttu-id="687dd-395">**Identificazione personale (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="687dd-395">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="687dd-396">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-396"></span></span>|
|<span data-ttu-id="687dd-397">**PIN (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="687dd-397">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="687dd-398">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-398"></span></span>|
   
 <span data-ttu-id="687dd-399">**Thawte CA radice principale - G3**</span><span class="sxs-lookup"><span data-stu-id="687dd-399">**thawte Primary Root CA - G3**</span></span>
  
||
|:-----|
|<span data-ttu-id="687dd-400">**Oggetto**</span><span class="sxs-lookup"><span data-stu-id="687dd-400">**Subject**</span></span>|
|<span data-ttu-id="687dd-401">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-401"></span></span>|
|<span data-ttu-id="687dd-402">**Numero di serie**</span><span class="sxs-lookup"><span data-stu-id="687dd-402">**Serial Number**</span></span>|
|<span data-ttu-id="687dd-403">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-403"></span></span>|
|<span data-ttu-id="687dd-404">**Lunghezza chiave pubblica**</span><span class="sxs-lookup"><span data-stu-id="687dd-404">**Public Key Length**</span></span>|
|<span data-ttu-id="687dd-405">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-405"></span></span>|
|<span data-ttu-id="687dd-406">**Algoritmo di firma**</span><span class="sxs-lookup"><span data-stu-id="687dd-406">**Signature Algorithm**</span></span>|
|<span data-ttu-id="687dd-407">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-407"></span></span>|
|<span data-ttu-id="687dd-408">**Validità non prima**</span><span class="sxs-lookup"><span data-stu-id="687dd-408">**Validity Not Before**</span></span>|
|<span data-ttu-id="687dd-409">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-409"></span></span>|
|<span data-ttu-id="687dd-410">**Validità non dopo**</span><span class="sxs-lookup"><span data-stu-id="687dd-410">**Validity Not After**</span></span>|
|<span data-ttu-id="687dd-411">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-411"></span></span>|
|<span data-ttu-id="687dd-412">**Identificatore chiave del soggetto**</span><span class="sxs-lookup"><span data-stu-id="687dd-412">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="687dd-413">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-413"></span></span>|
|<span data-ttu-id="687dd-414">**Identificazione personale (SHA-1)**</span><span class="sxs-lookup"><span data-stu-id="687dd-414">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="687dd-415">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-415"></span></span>|
|<span data-ttu-id="687dd-416">**Identificazione personale (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="687dd-416">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="687dd-417">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-417"></span></span>|
|<span data-ttu-id="687dd-418">**PIN (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="687dd-418">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="687dd-419">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-419"></span></span>|
   
 <span data-ttu-id="687dd-420">**Autorità di certificazione principale pubblica VeriSign classe 3 - G5**</span><span class="sxs-lookup"><span data-stu-id="687dd-420">**VeriSign Class 3 Public Primary Certification Authority - G5**</span></span>
  
||
|:-----|
|<span data-ttu-id="687dd-421">**Oggetto**</span><span class="sxs-lookup"><span data-stu-id="687dd-421">**Subject**</span></span>|
|<span data-ttu-id="687dd-422">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-422"></span></span>|
|<span data-ttu-id="687dd-423">**Numero di serie**</span><span class="sxs-lookup"><span data-stu-id="687dd-423">**Serial Number**</span></span>|
|<span data-ttu-id="687dd-424">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-424"></span></span>|
|<span data-ttu-id="687dd-425">**Lunghezza chiave pubblica**</span><span class="sxs-lookup"><span data-stu-id="687dd-425">**Public Key Length**</span></span>|
|<span data-ttu-id="687dd-426">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-426"></span></span>|
|<span data-ttu-id="687dd-427">**Algoritmo di firma**</span><span class="sxs-lookup"><span data-stu-id="687dd-427">**Signature Algorithm**</span></span>|
|<span data-ttu-id="687dd-428">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-428"></span></span>|
|<span data-ttu-id="687dd-429">**Validità non prima**</span><span class="sxs-lookup"><span data-stu-id="687dd-429">**Validity Not Before**</span></span>|
|<span data-ttu-id="687dd-430">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-430"></span></span>|
|<span data-ttu-id="687dd-431">**Validità non dopo**</span><span class="sxs-lookup"><span data-stu-id="687dd-431">**Validity Not After**</span></span>|
|<span data-ttu-id="687dd-432">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-432"></span></span>|
|<span data-ttu-id="687dd-433">**Identificatore chiave del soggetto**</span><span class="sxs-lookup"><span data-stu-id="687dd-433">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="687dd-434">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-434"></span></span>|
|<span data-ttu-id="687dd-435">**Identificazione personale (SHA-1)**</span><span class="sxs-lookup"><span data-stu-id="687dd-435">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="687dd-436">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-436"></span></span>|
|<span data-ttu-id="687dd-437">**Identificazione personale (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="687dd-437">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="687dd-438">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-438"></span></span>|
|<span data-ttu-id="687dd-439">**PIN (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="687dd-439">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="687dd-440">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-440"></span></span>|
   
## <a name="office-365-intermediate-certificate-details"></a><span data-ttu-id="687dd-441">Informazioni relative al certificato intermedio Office 365</span><span class="sxs-lookup"><span data-stu-id="687dd-441">Office 365 Intermediate Certificate Details</span></span>
<span data-ttu-id="687dd-442"><a name="IntermediateCerts"> </a></span><span class="sxs-lookup"><span data-stu-id="687dd-442"></span></span>

 <span data-ttu-id="687dd-443">**CNNIC SHA256 SSL**</span><span class="sxs-lookup"><span data-stu-id="687dd-443">**CNNIC SHA256 SSL**</span></span>
  
||
|:-----|
|<span data-ttu-id="687dd-444">**Oggetto**</span><span class="sxs-lookup"><span data-stu-id="687dd-444">**Subject**</span></span>|
|<span data-ttu-id="687dd-445">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-445"></span></span>|
|<span data-ttu-id="687dd-446">**Autorità di certificazione**</span><span class="sxs-lookup"><span data-stu-id="687dd-446">**Issuer**</span></span>|
|<span data-ttu-id="687dd-447">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-447"></span></span>|
|<span data-ttu-id="687dd-448">**Numero di serie**</span><span class="sxs-lookup"><span data-stu-id="687dd-448">**Serial Number**</span></span>|
|<span data-ttu-id="687dd-449">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-449"></span></span>|
|<span data-ttu-id="687dd-450">**Lunghezza chiave pubblica**</span><span class="sxs-lookup"><span data-stu-id="687dd-450">**Public Key Length**</span></span>|
|<span data-ttu-id="687dd-451">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-451"></span></span>|
|<span data-ttu-id="687dd-452">**Algoritmo di firma**</span><span class="sxs-lookup"><span data-stu-id="687dd-452">**Signature Algorithm**</span></span>|
|<span data-ttu-id="687dd-453">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-453"></span></span>|
|<span data-ttu-id="687dd-454">**Validità non prima**</span><span class="sxs-lookup"><span data-stu-id="687dd-454">**Validity Not Before**</span></span>|
|<span data-ttu-id="687dd-455">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-455"></span></span>|
|<span data-ttu-id="687dd-456">**Validità non dopo**</span><span class="sxs-lookup"><span data-stu-id="687dd-456">**Validity Not After**</span></span>|
|<span data-ttu-id="687dd-457">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-457"></span></span>|
|<span data-ttu-id="687dd-458">**Identificatore chiave del soggetto**</span><span class="sxs-lookup"><span data-stu-id="687dd-458">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="687dd-459">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-459"></span></span>|
|<span data-ttu-id="687dd-460">**Identificatore chiave dell'autorità**</span><span class="sxs-lookup"><span data-stu-id="687dd-460">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="687dd-461">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-461"></span></span>|
|<span data-ttu-id="687dd-462">**Identificazione personale (SHA-1)**</span><span class="sxs-lookup"><span data-stu-id="687dd-462">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="687dd-463">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-463"></span></span>|
|<span data-ttu-id="687dd-464">**Identificazione personale (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="687dd-464">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="687dd-465">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-465"></span></span>|
|<span data-ttu-id="687dd-466">**PIN (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="687dd-466">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="687dd-467">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-467"></span></span>|
|<span data-ttu-id="687dd-468">**URL AIA**</span><span class="sxs-lookup"><span data-stu-id="687dd-468">**AIA URLs**</span></span>|
|<span data-ttu-id="687dd-469">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-469"></span></span>|
|<span data-ttu-id="687dd-470">**URL di revoche di certificati**</span><span class="sxs-lookup"><span data-stu-id="687dd-470">**CRL URLs**</span></span>|
|<span data-ttu-id="687dd-471">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-471"></span></span>|
|<span data-ttu-id="687dd-472">**URL OCSP**</span><span class="sxs-lookup"><span data-stu-id="687dd-472">**OCSP URLs**</span></span>|
|<span data-ttu-id="687dd-473">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-473"></span></span>|
   
 <span data-ttu-id="687dd-474">**Autorità di certificazione classe 3 D protezione SSL 1 2009**</span><span class="sxs-lookup"><span data-stu-id="687dd-474">**D-TRUST SSL Class 3 CA 1 2009**</span></span>
  
||
|:-----|
|<span data-ttu-id="687dd-475">**Oggetto**</span><span class="sxs-lookup"><span data-stu-id="687dd-475">**Subject**</span></span>|
|<span data-ttu-id="687dd-476">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-476"></span></span>|
|<span data-ttu-id="687dd-477">**Autorità di certificazione**</span><span class="sxs-lookup"><span data-stu-id="687dd-477">**Issuer**</span></span>|
|<span data-ttu-id="687dd-478">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-478"></span></span>|
|<span data-ttu-id="687dd-479">**Nome alternativo soggetto**</span><span class="sxs-lookup"><span data-stu-id="687dd-479">**Subject Alternative Name**</span></span>|
|<span data-ttu-id="687dd-480">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-480"></span></span>|
|<span data-ttu-id="687dd-481">**Numero di serie**</span><span class="sxs-lookup"><span data-stu-id="687dd-481">**Serial Number**</span></span>|
|<span data-ttu-id="687dd-482">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-482"></span></span>|
|<span data-ttu-id="687dd-483">**Lunghezza chiave pubblica**</span><span class="sxs-lookup"><span data-stu-id="687dd-483">**Public Key Length**</span></span>|
|<span data-ttu-id="687dd-484">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-484"></span></span>|
|<span data-ttu-id="687dd-485">**Algoritmo di firma**</span><span class="sxs-lookup"><span data-stu-id="687dd-485">**Signature Algorithm**</span></span>|
|<span data-ttu-id="687dd-486">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-486"></span></span>|
|<span data-ttu-id="687dd-487">**Validità non prima**</span><span class="sxs-lookup"><span data-stu-id="687dd-487">**Validity Not Before**</span></span>|
|<span data-ttu-id="687dd-488">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-488"></span></span>|
|<span data-ttu-id="687dd-489">**Validità non dopo**</span><span class="sxs-lookup"><span data-stu-id="687dd-489">**Validity Not After**</span></span>|
|<span data-ttu-id="687dd-490">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-490"></span></span>|
|<span data-ttu-id="687dd-491">**Identificatore chiave del soggetto**</span><span class="sxs-lookup"><span data-stu-id="687dd-491">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="687dd-492">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-492"></span></span>|
|<span data-ttu-id="687dd-493">**Identificatore chiave dell'autorità**</span><span class="sxs-lookup"><span data-stu-id="687dd-493">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="687dd-494">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-494"></span></span>|
|<span data-ttu-id="687dd-495">**Identificazione personale (SHA-1)**</span><span class="sxs-lookup"><span data-stu-id="687dd-495">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="687dd-496">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-496"></span></span>|
|<span data-ttu-id="687dd-497">**Identificazione personale (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="687dd-497">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="687dd-498">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-498"></span></span>|
|<span data-ttu-id="687dd-499">**PIN (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="687dd-499">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="687dd-500">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-500"></span></span>|
|<span data-ttu-id="687dd-501">**URL di revoche di certificati**</span><span class="sxs-lookup"><span data-stu-id="687dd-501">**CRL URLs**</span></span>|
|<span data-ttu-id="687dd-502">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-502"></span></span>|
|<span data-ttu-id="687dd-503">**URL OCSP**</span><span class="sxs-lookup"><span data-stu-id="687dd-503">**OCSP URLs**</span></span>|
|<span data-ttu-id="687dd-504">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-504"></span></span>|
   
 <span data-ttu-id="687dd-505">**Autorità di certificazione classe 3 D protezione SSL 1 EV 2009**</span><span class="sxs-lookup"><span data-stu-id="687dd-505">**D-TRUST SSL Class 3 CA 1 EV 2009**</span></span>
  
||
|:-----|
|<span data-ttu-id="687dd-506">**Oggetto**</span><span class="sxs-lookup"><span data-stu-id="687dd-506">**Subject**</span></span>|
|<span data-ttu-id="687dd-507">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-507"></span></span>|
|<span data-ttu-id="687dd-508">**Autorità di certificazione**</span><span class="sxs-lookup"><span data-stu-id="687dd-508">**Issuer**</span></span>|
|<span data-ttu-id="687dd-509">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-509"></span></span>|
|<span data-ttu-id="687dd-510">**Nome alternativo soggetto**</span><span class="sxs-lookup"><span data-stu-id="687dd-510">**Subject Alternative Name**</span></span>|
|<span data-ttu-id="687dd-511">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-511"></span></span>|
|<span data-ttu-id="687dd-512">**Numero di serie**</span><span class="sxs-lookup"><span data-stu-id="687dd-512">**Serial Number**</span></span>|
|<span data-ttu-id="687dd-513">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-513"></span></span>|
|<span data-ttu-id="687dd-514">**Lunghezza chiave pubblica**</span><span class="sxs-lookup"><span data-stu-id="687dd-514">**Public Key Length**</span></span>|
|<span data-ttu-id="687dd-515">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-515"></span></span>|
|<span data-ttu-id="687dd-516">**Algoritmo di firma**</span><span class="sxs-lookup"><span data-stu-id="687dd-516">**Signature Algorithm**</span></span>|
|<span data-ttu-id="687dd-517">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-517"></span></span>|
|<span data-ttu-id="687dd-518">**Validità non prima**</span><span class="sxs-lookup"><span data-stu-id="687dd-518">**Validity Not Before**</span></span>|
|<span data-ttu-id="687dd-519">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-519"></span></span>|
|<span data-ttu-id="687dd-520">**Validità non dopo**</span><span class="sxs-lookup"><span data-stu-id="687dd-520">**Validity Not After**</span></span>|
|<span data-ttu-id="687dd-521">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-521"></span></span>|
|<span data-ttu-id="687dd-522">**Identificatore chiave del soggetto**</span><span class="sxs-lookup"><span data-stu-id="687dd-522">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="687dd-523">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-523"></span></span>|
|<span data-ttu-id="687dd-524">**Identificatore chiave dell'autorità**</span><span class="sxs-lookup"><span data-stu-id="687dd-524">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="687dd-525">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-525"></span></span>|
|<span data-ttu-id="687dd-526">**Identificazione personale (SHA-1)**</span><span class="sxs-lookup"><span data-stu-id="687dd-526">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="687dd-527">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-527"></span></span>|
|<span data-ttu-id="687dd-528">**Identificazione personale (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="687dd-528">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="687dd-529">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-529"></span></span>|
|<span data-ttu-id="687dd-530">**PIN (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="687dd-530">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="687dd-531">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-531"></span></span>|
|<span data-ttu-id="687dd-532">**URL di revoche di certificati**</span><span class="sxs-lookup"><span data-stu-id="687dd-532">**CRL URLs**</span></span>|
|<span data-ttu-id="687dd-533">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-533"></span></span>|
|<span data-ttu-id="687dd-534">**URL OCSP**</span><span class="sxs-lookup"><span data-stu-id="687dd-534">**OCSP URLs**</span></span>|
|<span data-ttu-id="687dd-535">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-535"></span></span>|
   
 <span data-ttu-id="687dd-536">**CA-1 di servizi Cloud DigiCert**</span><span class="sxs-lookup"><span data-stu-id="687dd-536">**DigiCert Cloud Services CA-1**</span></span>
  
||
|:-----|
|<span data-ttu-id="687dd-537">**Oggetto**</span><span class="sxs-lookup"><span data-stu-id="687dd-537">**Subject**</span></span>|
|<span data-ttu-id="687dd-538">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-538"></span></span>|
|<span data-ttu-id="687dd-539">**Autorità di certificazione**</span><span class="sxs-lookup"><span data-stu-id="687dd-539">**Issuer**</span></span>|
|<span data-ttu-id="687dd-540">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-540"></span></span>|
|<span data-ttu-id="687dd-541">**Numero di serie**</span><span class="sxs-lookup"><span data-stu-id="687dd-541">**Serial Number**</span></span>|
|<span data-ttu-id="687dd-542">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-542"></span></span>|
|<span data-ttu-id="687dd-543">**Lunghezza chiave pubblica**</span><span class="sxs-lookup"><span data-stu-id="687dd-543">**Public Key Length**</span></span>|
|<span data-ttu-id="687dd-544">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-544"></span></span>|
|<span data-ttu-id="687dd-545">**Algoritmo di firma**</span><span class="sxs-lookup"><span data-stu-id="687dd-545">**Signature Algorithm**</span></span>|
|<span data-ttu-id="687dd-546">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-546"></span></span>|
|<span data-ttu-id="687dd-547">**Validità non prima**</span><span class="sxs-lookup"><span data-stu-id="687dd-547">**Validity Not Before**</span></span>|
|<span data-ttu-id="687dd-548">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-548"></span></span>|
|<span data-ttu-id="687dd-549">**Validità non dopo**</span><span class="sxs-lookup"><span data-stu-id="687dd-549">**Validity Not After**</span></span>|
|<span data-ttu-id="687dd-550">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-550"></span></span>|
|<span data-ttu-id="687dd-551">**Identificatore chiave del soggetto**</span><span class="sxs-lookup"><span data-stu-id="687dd-551">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="687dd-552">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-552"></span></span>|
|<span data-ttu-id="687dd-553">**Identificatore chiave dell'autorità**</span><span class="sxs-lookup"><span data-stu-id="687dd-553">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="687dd-554">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-554"></span></span>|
|<span data-ttu-id="687dd-555">**Identificazione personale (SHA-1)**</span><span class="sxs-lookup"><span data-stu-id="687dd-555">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="687dd-556">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-556"></span></span>|
|<span data-ttu-id="687dd-557">**Identificazione personale (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="687dd-557">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="687dd-558">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-558"></span></span>|
|<span data-ttu-id="687dd-559">**PIN (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="687dd-559">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="687dd-560">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-560"></span></span>|
|<span data-ttu-id="687dd-561">**URL di revoche di certificati**</span><span class="sxs-lookup"><span data-stu-id="687dd-561">**CRL URLs**</span></span>|
|<span data-ttu-id="687dd-562">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-562"></span></span>|
|<span data-ttu-id="687dd-563">**URL OCSP**</span><span class="sxs-lookup"><span data-stu-id="687dd-563">**OCSP URLs**</span></span>|
|<span data-ttu-id="687dd-564">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-564"></span></span>|
   
 <span data-ttu-id="687dd-565">**Server di garanzia elevata DigiCert SHA2 autorità di certificazione**</span><span class="sxs-lookup"><span data-stu-id="687dd-565">**DigiCert SHA2 High Assurance Server CA**</span></span>
  
||
|:-----|
|<span data-ttu-id="687dd-566">**Oggetto**</span><span class="sxs-lookup"><span data-stu-id="687dd-566">**Subject**</span></span>|
|<span data-ttu-id="687dd-567">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-567"></span></span>|
|<span data-ttu-id="687dd-568">**Autorità di certificazione**</span><span class="sxs-lookup"><span data-stu-id="687dd-568">**Issuer**</span></span>|
|<span data-ttu-id="687dd-569">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-569"></span></span>|
|<span data-ttu-id="687dd-570">**Numero di serie**</span><span class="sxs-lookup"><span data-stu-id="687dd-570">**Serial Number**</span></span>|
|<span data-ttu-id="687dd-571">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-571"></span></span>|
|<span data-ttu-id="687dd-572">**Lunghezza chiave pubblica**</span><span class="sxs-lookup"><span data-stu-id="687dd-572">**Public Key Length**</span></span>|
|<span data-ttu-id="687dd-573">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-573"></span></span>|
|<span data-ttu-id="687dd-574">**Algoritmo di firma**</span><span class="sxs-lookup"><span data-stu-id="687dd-574">**Signature Algorithm**</span></span>|
|<span data-ttu-id="687dd-575">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-575"></span></span>|
|<span data-ttu-id="687dd-576">**Validità non prima**</span><span class="sxs-lookup"><span data-stu-id="687dd-576">**Validity Not Before**</span></span>|
|<span data-ttu-id="687dd-577">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-577"></span></span>|
|<span data-ttu-id="687dd-578">**Validità non dopo**</span><span class="sxs-lookup"><span data-stu-id="687dd-578">**Validity Not After**</span></span>|
|<span data-ttu-id="687dd-579">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-579"></span></span>|
|<span data-ttu-id="687dd-580">**Identificatore chiave del soggetto**</span><span class="sxs-lookup"><span data-stu-id="687dd-580">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="687dd-581">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-581"></span></span>|
|<span data-ttu-id="687dd-582">**Identificatore chiave dell'autorità**</span><span class="sxs-lookup"><span data-stu-id="687dd-582">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="687dd-583">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-583"></span></span>|
|<span data-ttu-id="687dd-584">**Identificazione personale (SHA-1)**</span><span class="sxs-lookup"><span data-stu-id="687dd-584">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="687dd-585">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-585"></span></span>|
|<span data-ttu-id="687dd-586">**Identificazione personale (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="687dd-586">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="687dd-587">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-587"></span></span>|
|<span data-ttu-id="687dd-588">**PIN (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="687dd-588">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="687dd-589">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-589"></span></span>|
|<span data-ttu-id="687dd-590">**URL di revoche di certificati**</span><span class="sxs-lookup"><span data-stu-id="687dd-590">**CRL URLs**</span></span>|
|<span data-ttu-id="687dd-591">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-591"></span></span>|
|<span data-ttu-id="687dd-592">**URL OCSP**</span><span class="sxs-lookup"><span data-stu-id="687dd-592">**OCSP URLs**</span></span>|
|<span data-ttu-id="687dd-593">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-593"></span></span>|
   
 <span data-ttu-id="687dd-594">**Server protetto DigiCert SHA2 autorità di certificazione**</span><span class="sxs-lookup"><span data-stu-id="687dd-594">**DigiCert SHA2 Secure Server CA**</span></span>
  
||
|:-----|
|<span data-ttu-id="687dd-595">**Oggetto**</span><span class="sxs-lookup"><span data-stu-id="687dd-595">**Subject**</span></span>|
|<span data-ttu-id="687dd-596">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-596"></span></span>|
|<span data-ttu-id="687dd-597">**Autorità di certificazione**</span><span class="sxs-lookup"><span data-stu-id="687dd-597">**Issuer**</span></span>|
|<span data-ttu-id="687dd-598">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-598"></span></span>|
|<span data-ttu-id="687dd-599">**Numero di serie**</span><span class="sxs-lookup"><span data-stu-id="687dd-599">**Serial Number**</span></span>|
|<span data-ttu-id="687dd-600">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-600"></span></span>|
|<span data-ttu-id="687dd-601">**Lunghezza chiave pubblica**</span><span class="sxs-lookup"><span data-stu-id="687dd-601">**Public Key Length**</span></span>|
|<span data-ttu-id="687dd-602">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-602"></span></span>|
|<span data-ttu-id="687dd-603">**Algoritmo di firma**</span><span class="sxs-lookup"><span data-stu-id="687dd-603">**Signature Algorithm**</span></span>|
|<span data-ttu-id="687dd-604">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-604"></span></span>|
|<span data-ttu-id="687dd-605">**Validità non prima**</span><span class="sxs-lookup"><span data-stu-id="687dd-605">**Validity Not Before**</span></span>|
|<span data-ttu-id="687dd-606">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-606"></span></span>|
|<span data-ttu-id="687dd-607">**Validità non dopo**</span><span class="sxs-lookup"><span data-stu-id="687dd-607">**Validity Not After**</span></span>|
|<span data-ttu-id="687dd-608">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-608"></span></span>|
|<span data-ttu-id="687dd-609">**Identificatore chiave del soggetto**</span><span class="sxs-lookup"><span data-stu-id="687dd-609">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="687dd-610">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-610"></span></span>|
|<span data-ttu-id="687dd-611">**Identificatore chiave dell'autorità**</span><span class="sxs-lookup"><span data-stu-id="687dd-611">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="687dd-612">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-612"></span></span>|
|<span data-ttu-id="687dd-613">**Identificazione personale (SHA-1)**</span><span class="sxs-lookup"><span data-stu-id="687dd-613">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="687dd-614">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-614"></span></span>|
|<span data-ttu-id="687dd-615">**Identificazione personale (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="687dd-615">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="687dd-616">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-616"></span></span>|
|<span data-ttu-id="687dd-617">**PIN (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="687dd-617">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="687dd-618">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-618"></span></span>|
|<span data-ttu-id="687dd-619">**URL di revoche di certificati**</span><span class="sxs-lookup"><span data-stu-id="687dd-619">**CRL URLs**</span></span>|
|<span data-ttu-id="687dd-620">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-620"></span></span>|
|<span data-ttu-id="687dd-621">**URL OCSP**</span><span class="sxs-lookup"><span data-stu-id="687dd-621">**OCSP URLs**</span></span>|
|<span data-ttu-id="687dd-622">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-622"></span></span>|
   
 <span data-ttu-id="687dd-623">**Affidare autorità di certificazione - L1C**</span><span class="sxs-lookup"><span data-stu-id="687dd-623">**Entrust Certification Authority - L1C**</span></span>
  
||
|:-----|
|<span data-ttu-id="687dd-624">**Oggetto**</span><span class="sxs-lookup"><span data-stu-id="687dd-624">**Subject**</span></span>|
|<span data-ttu-id="687dd-625">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-625"></span></span>|
|<span data-ttu-id="687dd-626">**Autorità di certificazione**</span><span class="sxs-lookup"><span data-stu-id="687dd-626">**Issuer**</span></span>|
|<span data-ttu-id="687dd-627">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-627"></span></span>|
|<span data-ttu-id="687dd-628">**Numero di serie**</span><span class="sxs-lookup"><span data-stu-id="687dd-628">**Serial Number**</span></span>|
|<span data-ttu-id="687dd-629">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-629"></span></span>|
|<span data-ttu-id="687dd-630">**Lunghezza chiave pubblica**</span><span class="sxs-lookup"><span data-stu-id="687dd-630">**Public Key Length**</span></span>|
|<span data-ttu-id="687dd-631">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-631"></span></span>|
|<span data-ttu-id="687dd-632">**Algoritmo di firma**</span><span class="sxs-lookup"><span data-stu-id="687dd-632">**Signature Algorithm**</span></span>|
|<span data-ttu-id="687dd-633">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-633"></span></span>|
|<span data-ttu-id="687dd-634">**Validità non prima**</span><span class="sxs-lookup"><span data-stu-id="687dd-634">**Validity Not Before**</span></span>|
|<span data-ttu-id="687dd-635">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-635"></span></span>|
|<span data-ttu-id="687dd-636">**Validità non dopo**</span><span class="sxs-lookup"><span data-stu-id="687dd-636">**Validity Not After**</span></span>|
|<span data-ttu-id="687dd-637">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-637"></span></span>|
|<span data-ttu-id="687dd-638">**Identificatore chiave del soggetto**</span><span class="sxs-lookup"><span data-stu-id="687dd-638">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="687dd-639">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-639"></span></span>|
|<span data-ttu-id="687dd-640">**Identificatore chiave dell'autorità**</span><span class="sxs-lookup"><span data-stu-id="687dd-640">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="687dd-641">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-641"></span></span>|
|<span data-ttu-id="687dd-642">**Identificazione personale (SHA-1)**</span><span class="sxs-lookup"><span data-stu-id="687dd-642">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="687dd-643">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-643"></span></span>|
|<span data-ttu-id="687dd-644">**Identificazione personale (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="687dd-644">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="687dd-645">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-645"></span></span>|
|<span data-ttu-id="687dd-646">**PIN (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="687dd-646">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="687dd-647">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-647"></span></span>|
|<span data-ttu-id="687dd-648">**URL di revoche di certificati**</span><span class="sxs-lookup"><span data-stu-id="687dd-648">**CRL URLs**</span></span>|
|<span data-ttu-id="687dd-649">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-649"></span></span>|
|<span data-ttu-id="687dd-650">**URL OCSP**</span><span class="sxs-lookup"><span data-stu-id="687dd-650">**OCSP URLs**</span></span>|
|<span data-ttu-id="687dd-651">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-651"></span></span>|
   
 <span data-ttu-id="687dd-652">**Affidare autorità di certificazione - L1K**</span><span class="sxs-lookup"><span data-stu-id="687dd-652">**Entrust Certification Authority - L1K**</span></span>
  
||
|:-----|
|<span data-ttu-id="687dd-653">**Oggetto**</span><span class="sxs-lookup"><span data-stu-id="687dd-653">**Subject**</span></span>|
|<span data-ttu-id="687dd-654">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-654"></span></span>|
|<span data-ttu-id="687dd-655">**Autorità di certificazione**</span><span class="sxs-lookup"><span data-stu-id="687dd-655">**Issuer**</span></span>|
|<span data-ttu-id="687dd-656">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-656"></span></span>|
|<span data-ttu-id="687dd-657">**Numero di serie**</span><span class="sxs-lookup"><span data-stu-id="687dd-657">**Serial Number**</span></span>|
|<span data-ttu-id="687dd-658">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-658"></span></span>|
|<span data-ttu-id="687dd-659">**Lunghezza chiave pubblica**</span><span class="sxs-lookup"><span data-stu-id="687dd-659">**Public Key Length**</span></span>|
|<span data-ttu-id="687dd-660">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-660"></span></span>|
|<span data-ttu-id="687dd-661">**Algoritmo di firma**</span><span class="sxs-lookup"><span data-stu-id="687dd-661">**Signature Algorithm**</span></span>|
|<span data-ttu-id="687dd-662">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-662"></span></span>|
|<span data-ttu-id="687dd-663">**Validità non prima**</span><span class="sxs-lookup"><span data-stu-id="687dd-663">**Validity Not Before**</span></span>|
|<span data-ttu-id="687dd-664">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-664"></span></span>|
|<span data-ttu-id="687dd-665">**Validità non dopo**</span><span class="sxs-lookup"><span data-stu-id="687dd-665">**Validity Not After**</span></span>|
|<span data-ttu-id="687dd-666">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-666"></span></span>|
|<span data-ttu-id="687dd-667">**Identificatore chiave del soggetto**</span><span class="sxs-lookup"><span data-stu-id="687dd-667">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="687dd-668">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-668"></span></span>|
|<span data-ttu-id="687dd-669">**Identificatore chiave dell'autorità**</span><span class="sxs-lookup"><span data-stu-id="687dd-669">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="687dd-670">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-670"></span></span>|
|<span data-ttu-id="687dd-671">**Identificazione personale (SHA-1)**</span><span class="sxs-lookup"><span data-stu-id="687dd-671">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="687dd-672">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-672"></span></span>|
|<span data-ttu-id="687dd-673">**Identificazione personale (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="687dd-673">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="687dd-674">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-674"></span></span>|
|<span data-ttu-id="687dd-675">**PIN (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="687dd-675">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="687dd-676">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-676"></span></span>|
|<span data-ttu-id="687dd-677">**URL di revoche di certificati**</span><span class="sxs-lookup"><span data-stu-id="687dd-677">**CRL URLs**</span></span>|
|<span data-ttu-id="687dd-678">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-678"></span></span>|
|<span data-ttu-id="687dd-679">**URL OCSP**</span><span class="sxs-lookup"><span data-stu-id="687dd-679">**OCSP URLs**</span></span>|
|<span data-ttu-id="687dd-680">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-680"></span></span>|
   
 <span data-ttu-id="687dd-681">**GlobalSign**</span><span class="sxs-lookup"><span data-stu-id="687dd-681">**GlobalSign**</span></span>
  
||
|:-----|
|<span data-ttu-id="687dd-682">**Oggetto**</span><span class="sxs-lookup"><span data-stu-id="687dd-682">**Subject**</span></span>|
|<span data-ttu-id="687dd-683">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-683"></span></span>|
|<span data-ttu-id="687dd-684">**Autorità di certificazione**</span><span class="sxs-lookup"><span data-stu-id="687dd-684">**Issuer**</span></span>|
|<span data-ttu-id="687dd-685">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-685"></span></span>|
|<span data-ttu-id="687dd-686">**Numero di serie**</span><span class="sxs-lookup"><span data-stu-id="687dd-686">**Serial Number**</span></span>|
|<span data-ttu-id="687dd-687">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-687"></span></span>|
|<span data-ttu-id="687dd-688">**Lunghezza chiave pubblica**</span><span class="sxs-lookup"><span data-stu-id="687dd-688">**Public Key Length**</span></span>|
|<span data-ttu-id="687dd-689">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-689"></span></span>|
|<span data-ttu-id="687dd-690">**Algoritmo di firma**</span><span class="sxs-lookup"><span data-stu-id="687dd-690">**Signature Algorithm**</span></span>|
|<span data-ttu-id="687dd-691">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-691"></span></span>|
|<span data-ttu-id="687dd-692">**Validità non prima**</span><span class="sxs-lookup"><span data-stu-id="687dd-692">**Validity Not Before**</span></span>|
|<span data-ttu-id="687dd-693">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-693"></span></span>|
|<span data-ttu-id="687dd-694">**Validità non dopo**</span><span class="sxs-lookup"><span data-stu-id="687dd-694">**Validity Not After**</span></span>|
|<span data-ttu-id="687dd-695">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-695"></span></span>|
|<span data-ttu-id="687dd-696">**Identificatore chiave del soggetto**</span><span class="sxs-lookup"><span data-stu-id="687dd-696">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="687dd-697">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-697"></span></span>|
|<span data-ttu-id="687dd-698">**Identificatore chiave dell'autorità**</span><span class="sxs-lookup"><span data-stu-id="687dd-698">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="687dd-699">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-699"></span></span>|
|<span data-ttu-id="687dd-700">**Identificazione personale (SHA-1)**</span><span class="sxs-lookup"><span data-stu-id="687dd-700">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="687dd-701">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-701"></span></span>|
|<span data-ttu-id="687dd-702">**Identificazione personale (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="687dd-702">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="687dd-703">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-703"></span></span>|
|<span data-ttu-id="687dd-704">**PIN (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="687dd-704">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="687dd-705">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-705"></span></span>|
|<span data-ttu-id="687dd-706">**URL di revoche di certificati**</span><span class="sxs-lookup"><span data-stu-id="687dd-706">**CRL URLs**</span></span>|
|<span data-ttu-id="687dd-707">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-707"></span></span>|
|<span data-ttu-id="687dd-708">**URL OCSP**</span><span class="sxs-lookup"><span data-stu-id="687dd-708">**OCSP URLs**</span></span>|
|<span data-ttu-id="687dd-709">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-709"></span></span>|
   
 <span data-ttu-id="687dd-710">**Versione estesa di convalida CA - SHA256 - G2 GlobalSign**</span><span class="sxs-lookup"><span data-stu-id="687dd-710">**GlobalSign Extended Validation CA - SHA256 - G2**</span></span>
  
||
|:-----|
|<span data-ttu-id="687dd-711">**Oggetto**</span><span class="sxs-lookup"><span data-stu-id="687dd-711">**Subject**</span></span>|
|<span data-ttu-id="687dd-712">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-712"></span></span>|
|<span data-ttu-id="687dd-713">**Autorità di certificazione**</span><span class="sxs-lookup"><span data-stu-id="687dd-713">**Issuer**</span></span>|
|<span data-ttu-id="687dd-714">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-714"></span></span>|
|<span data-ttu-id="687dd-715">**Numero di serie**</span><span class="sxs-lookup"><span data-stu-id="687dd-715">**Serial Number**</span></span>|
|<span data-ttu-id="687dd-716">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-716"></span></span>|
|<span data-ttu-id="687dd-717">**Lunghezza chiave pubblica**</span><span class="sxs-lookup"><span data-stu-id="687dd-717">**Public Key Length**</span></span>|
|<span data-ttu-id="687dd-718">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-718"></span></span>|
|<span data-ttu-id="687dd-719">**Algoritmo di firma**</span><span class="sxs-lookup"><span data-stu-id="687dd-719">**Signature Algorithm**</span></span>|
|<span data-ttu-id="687dd-720">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-720"></span></span>|
|<span data-ttu-id="687dd-721">**Validità non prima**</span><span class="sxs-lookup"><span data-stu-id="687dd-721">**Validity Not Before**</span></span>|
|<span data-ttu-id="687dd-722">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-722"></span></span>|
|<span data-ttu-id="687dd-723">**Validità non dopo**</span><span class="sxs-lookup"><span data-stu-id="687dd-723">**Validity Not After**</span></span>|
|<span data-ttu-id="687dd-724">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-724"></span></span>|
|<span data-ttu-id="687dd-725">**Identificatore chiave del soggetto**</span><span class="sxs-lookup"><span data-stu-id="687dd-725">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="687dd-726">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-726"></span></span>|
|<span data-ttu-id="687dd-727">**Identificatore chiave dell'autorità**</span><span class="sxs-lookup"><span data-stu-id="687dd-727">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="687dd-728">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-728"></span></span>|
|<span data-ttu-id="687dd-729">**Identificazione personale (SHA-1)**</span><span class="sxs-lookup"><span data-stu-id="687dd-729">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="687dd-730">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-730"></span></span>|
|<span data-ttu-id="687dd-731">**Identificazione personale (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="687dd-731">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="687dd-732">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-732"></span></span>|
|<span data-ttu-id="687dd-733">**PIN (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="687dd-733">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="687dd-734">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-734"></span></span>|
|<span data-ttu-id="687dd-735">**URL di revoche di certificati**</span><span class="sxs-lookup"><span data-stu-id="687dd-735">**CRL URLs**</span></span>|
|<span data-ttu-id="687dd-736">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-736"></span></span>|
|<span data-ttu-id="687dd-737">**URL OCSP**</span><span class="sxs-lookup"><span data-stu-id="687dd-737">**OCSP URLs**</span></span>|
|<span data-ttu-id="687dd-738">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-738"></span></span>|
   
 <span data-ttu-id="687dd-739">**Versione estesa di convalida CA - SHA256 - G3 GlobalSign**</span><span class="sxs-lookup"><span data-stu-id="687dd-739">**GlobalSign Extended Validation CA - SHA256 - G3**</span></span>
  
||
|:-----|
|<span data-ttu-id="687dd-740">**Oggetto**</span><span class="sxs-lookup"><span data-stu-id="687dd-740">**Subject**</span></span>|
|<span data-ttu-id="687dd-741">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-741"></span></span>|
|<span data-ttu-id="687dd-742">**Autorità di certificazione**</span><span class="sxs-lookup"><span data-stu-id="687dd-742">**Issuer**</span></span>|
|<span data-ttu-id="687dd-743">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-743"></span></span>|
|<span data-ttu-id="687dd-744">**Numero di serie**</span><span class="sxs-lookup"><span data-stu-id="687dd-744">**Serial Number**</span></span>|
|<span data-ttu-id="687dd-745">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-745"></span></span>|
|<span data-ttu-id="687dd-746">**Lunghezza chiave pubblica**</span><span class="sxs-lookup"><span data-stu-id="687dd-746">**Public Key Length**</span></span>|
|<span data-ttu-id="687dd-747">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-747"></span></span>|
|<span data-ttu-id="687dd-748">**Algoritmo di firma**</span><span class="sxs-lookup"><span data-stu-id="687dd-748">**Signature Algorithm**</span></span>|
|<span data-ttu-id="687dd-749">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-749"></span></span>|
|<span data-ttu-id="687dd-750">**Validità non prima**</span><span class="sxs-lookup"><span data-stu-id="687dd-750">**Validity Not Before**</span></span>|
|<span data-ttu-id="687dd-751">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-751"></span></span>|
|<span data-ttu-id="687dd-752">**Validità non dopo**</span><span class="sxs-lookup"><span data-stu-id="687dd-752">**Validity Not After**</span></span>|
|<span data-ttu-id="687dd-753">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-753"></span></span>|
|<span data-ttu-id="687dd-754">**Identificatore chiave del soggetto**</span><span class="sxs-lookup"><span data-stu-id="687dd-754">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="687dd-755">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-755"></span></span>|
|<span data-ttu-id="687dd-756">**Identificatore chiave dell'autorità**</span><span class="sxs-lookup"><span data-stu-id="687dd-756">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="687dd-757">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-757"></span></span>|
|<span data-ttu-id="687dd-758">**Identificazione personale (SHA-1)**</span><span class="sxs-lookup"><span data-stu-id="687dd-758">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="687dd-759">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-759"></span></span>|
|<span data-ttu-id="687dd-760">**Identificazione personale (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="687dd-760">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="687dd-761">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-761"></span></span>|
|<span data-ttu-id="687dd-762">**PIN (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="687dd-762">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="687dd-763">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-763"></span></span>|
|<span data-ttu-id="687dd-764">**URL di revoche di certificati**</span><span class="sxs-lookup"><span data-stu-id="687dd-764">**CRL URLs**</span></span>|
|<span data-ttu-id="687dd-765">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-765"></span></span>|
|<span data-ttu-id="687dd-766">**URL OCSP**</span><span class="sxs-lookup"><span data-stu-id="687dd-766">**OCSP URLs**</span></span>|
|<span data-ttu-id="687dd-767">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-767"></span></span>|
   
 <span data-ttu-id="687dd-768">**GlobalSign organizzazione convalida CA - SHA256 - G2**</span><span class="sxs-lookup"><span data-stu-id="687dd-768">**GlobalSign Organization Validation CA - SHA256 - G2**</span></span>
  
||
|:-----|
|<span data-ttu-id="687dd-769">**Oggetto**</span><span class="sxs-lookup"><span data-stu-id="687dd-769">**Subject**</span></span>|
|<span data-ttu-id="687dd-770">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-770"></span></span>|
|<span data-ttu-id="687dd-771">**Autorità di certificazione**</span><span class="sxs-lookup"><span data-stu-id="687dd-771">**Issuer**</span></span>|
|<span data-ttu-id="687dd-772">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-772"></span></span>|
|<span data-ttu-id="687dd-773">**Numero di serie**</span><span class="sxs-lookup"><span data-stu-id="687dd-773">**Serial Number**</span></span>|
|<span data-ttu-id="687dd-774">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-774"></span></span>|
|<span data-ttu-id="687dd-775">**Lunghezza chiave pubblica**</span><span class="sxs-lookup"><span data-stu-id="687dd-775">**Public Key Length**</span></span>|
|<span data-ttu-id="687dd-776">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-776"></span></span>|
|<span data-ttu-id="687dd-777">**Algoritmo di firma**</span><span class="sxs-lookup"><span data-stu-id="687dd-777">**Signature Algorithm**</span></span>|
|<span data-ttu-id="687dd-778">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-778"></span></span>|
|<span data-ttu-id="687dd-779">**Validità non prima**</span><span class="sxs-lookup"><span data-stu-id="687dd-779">**Validity Not Before**</span></span>|
|<span data-ttu-id="687dd-780">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-780"></span></span>|
|<span data-ttu-id="687dd-781">**Validità non dopo**</span><span class="sxs-lookup"><span data-stu-id="687dd-781">**Validity Not After**</span></span>|
|<span data-ttu-id="687dd-782">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-782"></span></span>|
|<span data-ttu-id="687dd-783">**Identificatore chiave del soggetto**</span><span class="sxs-lookup"><span data-stu-id="687dd-783">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="687dd-784">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-784"></span></span>|
|<span data-ttu-id="687dd-785">**Identificatore chiave dell'autorità**</span><span class="sxs-lookup"><span data-stu-id="687dd-785">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="687dd-786">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-786"></span></span>|
|<span data-ttu-id="687dd-787">**Identificazione personale (SHA-1)**</span><span class="sxs-lookup"><span data-stu-id="687dd-787">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="687dd-788">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-788"></span></span>|
|<span data-ttu-id="687dd-789">**Identificazione personale (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="687dd-789">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="687dd-790">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-790"></span></span>|
|<span data-ttu-id="687dd-791">**PIN (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="687dd-791">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="687dd-792">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-792"></span></span>|
|<span data-ttu-id="687dd-793">**URL di revoche di certificati**</span><span class="sxs-lookup"><span data-stu-id="687dd-793">**CRL URLs**</span></span>|
|<span data-ttu-id="687dd-794">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-794"></span></span>|
|<span data-ttu-id="687dd-795">**URL OCSP**</span><span class="sxs-lookup"><span data-stu-id="687dd-795">**OCSP URLs**</span></span>|
|<span data-ttu-id="687dd-796">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-796"></span></span>|
   
 <span data-ttu-id="687dd-797">**GlobalSign organizzazione convalida CA - SHA256 - G2**</span><span class="sxs-lookup"><span data-stu-id="687dd-797">**GlobalSign Organization Validation CA - SHA256 - G2**</span></span>
  
||
|:-----|
|<span data-ttu-id="687dd-798">**Oggetto**</span><span class="sxs-lookup"><span data-stu-id="687dd-798">**Subject**</span></span>|
|<span data-ttu-id="687dd-799">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-799"></span></span>|
|<span data-ttu-id="687dd-800">**Autorità di certificazione**</span><span class="sxs-lookup"><span data-stu-id="687dd-800">**Issuer**</span></span>|
|<span data-ttu-id="687dd-801">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-801"></span></span>|
|<span data-ttu-id="687dd-802">**Numero di serie**</span><span class="sxs-lookup"><span data-stu-id="687dd-802">**Serial Number**</span></span>|
|<span data-ttu-id="687dd-803">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-803"></span></span>|
|<span data-ttu-id="687dd-804">**Lunghezza chiave pubblica**</span><span class="sxs-lookup"><span data-stu-id="687dd-804">**Public Key Length**</span></span>|
|<span data-ttu-id="687dd-805">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-805"></span></span>|
|<span data-ttu-id="687dd-806">**Algoritmo di firma**</span><span class="sxs-lookup"><span data-stu-id="687dd-806">**Signature Algorithm**</span></span>|
|<span data-ttu-id="687dd-807">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-807"></span></span>|
|<span data-ttu-id="687dd-808">**Validità non prima**</span><span class="sxs-lookup"><span data-stu-id="687dd-808">**Validity Not Before**</span></span>|
|<span data-ttu-id="687dd-809">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-809"></span></span>|
|<span data-ttu-id="687dd-810">**Validità non dopo**</span><span class="sxs-lookup"><span data-stu-id="687dd-810">**Validity Not After**</span></span>|
|<span data-ttu-id="687dd-811">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-811"></span></span>|
|<span data-ttu-id="687dd-812">**Identificatore chiave del soggetto**</span><span class="sxs-lookup"><span data-stu-id="687dd-812">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="687dd-813">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-813"></span></span>|
|<span data-ttu-id="687dd-814">**Identificatore chiave dell'autorità**</span><span class="sxs-lookup"><span data-stu-id="687dd-814">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="687dd-815">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-815"></span></span>|
|<span data-ttu-id="687dd-816">**Identificazione personale (SHA-1)**</span><span class="sxs-lookup"><span data-stu-id="687dd-816">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="687dd-817">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-817"></span></span>|
|<span data-ttu-id="687dd-818">**Identificazione personale (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="687dd-818">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="687dd-819">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-819"></span></span>|
|<span data-ttu-id="687dd-820">**PIN (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="687dd-820">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="687dd-821">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-821"></span></span>|
|<span data-ttu-id="687dd-822">**URL di revoche di certificati**</span><span class="sxs-lookup"><span data-stu-id="687dd-822">**CRL URLs**</span></span>|
|<span data-ttu-id="687dd-823">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-823"></span></span>|
|<span data-ttu-id="687dd-824">**URL OCSP**</span><span class="sxs-lookup"><span data-stu-id="687dd-824">**OCSP URLs**</span></span>|
|<span data-ttu-id="687dd-825">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-825"></span></span>|
   
 <span data-ttu-id="687dd-826">**Crittografare possiamo autorità X3**</span><span class="sxs-lookup"><span data-stu-id="687dd-826">**Let's Encrypt Authority X3**</span></span>
  
||
|:-----|
|<span data-ttu-id="687dd-827">**Oggetto**</span><span class="sxs-lookup"><span data-stu-id="687dd-827">**Subject**</span></span>|
|<span data-ttu-id="687dd-828">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-828"></span></span>|
|<span data-ttu-id="687dd-829">**Autorità di certificazione**</span><span class="sxs-lookup"><span data-stu-id="687dd-829">**Issuer**</span></span>|
|<span data-ttu-id="687dd-830">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-830"></span></span>|
|<span data-ttu-id="687dd-831">**Numero di serie**</span><span class="sxs-lookup"><span data-stu-id="687dd-831">**Serial Number**</span></span>|
|<span data-ttu-id="687dd-832">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-832"></span></span>|
|<span data-ttu-id="687dd-833">**Lunghezza chiave pubblica**</span><span class="sxs-lookup"><span data-stu-id="687dd-833">**Public Key Length**</span></span>|
|<span data-ttu-id="687dd-834">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-834"></span></span>|
|<span data-ttu-id="687dd-835">**Algoritmo di firma**</span><span class="sxs-lookup"><span data-stu-id="687dd-835">**Signature Algorithm**</span></span>|
|<span data-ttu-id="687dd-836">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-836"></span></span>|
|<span data-ttu-id="687dd-837">**Validità non prima**</span><span class="sxs-lookup"><span data-stu-id="687dd-837">**Validity Not Before**</span></span>|
|<span data-ttu-id="687dd-838">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-838"></span></span>|
|<span data-ttu-id="687dd-839">**Validità non dopo**</span><span class="sxs-lookup"><span data-stu-id="687dd-839">**Validity Not After**</span></span>|
|<span data-ttu-id="687dd-840">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-840"></span></span>|
|<span data-ttu-id="687dd-841">**Identificatore chiave del soggetto**</span><span class="sxs-lookup"><span data-stu-id="687dd-841">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="687dd-842">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-842"></span></span>|
|<span data-ttu-id="687dd-843">**Identificatore chiave dell'autorità**</span><span class="sxs-lookup"><span data-stu-id="687dd-843">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="687dd-844">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-844"></span></span>|
|<span data-ttu-id="687dd-845">**Identificazione personale (SHA-1)**</span><span class="sxs-lookup"><span data-stu-id="687dd-845">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="687dd-846">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-846"></span></span>|
|<span data-ttu-id="687dd-847">**Identificazione personale (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="687dd-847">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="687dd-848">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-848"></span></span>|
|<span data-ttu-id="687dd-849">**PIN (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="687dd-849">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="687dd-850">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-850"></span></span>|
|<span data-ttu-id="687dd-851">**URL AIA**</span><span class="sxs-lookup"><span data-stu-id="687dd-851">**AIA URLs**</span></span>|
|<span data-ttu-id="687dd-852">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-852"></span></span>|
|<span data-ttu-id="687dd-853">**URL di revoche di certificati**</span><span class="sxs-lookup"><span data-stu-id="687dd-853">**CRL URLs**</span></span>|
|<span data-ttu-id="687dd-854">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-854"></span></span>|
|<span data-ttu-id="687dd-855">**URL OCSP**</span><span class="sxs-lookup"><span data-stu-id="687dd-855">**OCSP URLs**</span></span>|
|<span data-ttu-id="687dd-856">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-856"></span></span>|
   
 <span data-ttu-id="687dd-857">**Microsoft IT SSL SHA2**</span><span class="sxs-lookup"><span data-stu-id="687dd-857">**Microsoft IT SSL SHA2**</span></span>
  
||
|:-----|
|<span data-ttu-id="687dd-858">**Oggetto**</span><span class="sxs-lookup"><span data-stu-id="687dd-858">**Subject**</span></span>|
|<span data-ttu-id="687dd-859">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-859"></span></span>|
|<span data-ttu-id="687dd-860">**Autorità di certificazione**</span><span class="sxs-lookup"><span data-stu-id="687dd-860">**Issuer**</span></span>|
|<span data-ttu-id="687dd-861">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-861"></span></span>|
|<span data-ttu-id="687dd-862">**Numero di serie**</span><span class="sxs-lookup"><span data-stu-id="687dd-862">**Serial Number**</span></span>|
|<span data-ttu-id="687dd-863">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-863"></span></span>|
|<span data-ttu-id="687dd-864">**Lunghezza chiave pubblica**</span><span class="sxs-lookup"><span data-stu-id="687dd-864">**Public Key Length**</span></span>|
|<span data-ttu-id="687dd-865">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-865"></span></span>|
|<span data-ttu-id="687dd-866">**Algoritmo di firma**</span><span class="sxs-lookup"><span data-stu-id="687dd-866">**Signature Algorithm**</span></span>|
|<span data-ttu-id="687dd-867">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-867"></span></span>|
|<span data-ttu-id="687dd-868">**Validità non prima**</span><span class="sxs-lookup"><span data-stu-id="687dd-868">**Validity Not Before**</span></span>|
|<span data-ttu-id="687dd-869">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-869"></span></span>|
|<span data-ttu-id="687dd-870">**Validità non dopo**</span><span class="sxs-lookup"><span data-stu-id="687dd-870">**Validity Not After**</span></span>|
|<span data-ttu-id="687dd-871">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-871"></span></span>|
|<span data-ttu-id="687dd-872">**Identificatore chiave del soggetto**</span><span class="sxs-lookup"><span data-stu-id="687dd-872">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="687dd-873">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-873"></span></span>|
|<span data-ttu-id="687dd-874">**Identificatore chiave dell'autorità**</span><span class="sxs-lookup"><span data-stu-id="687dd-874">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="687dd-875">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-875"></span></span>|
|<span data-ttu-id="687dd-876">**Identificazione personale (SHA-1)**</span><span class="sxs-lookup"><span data-stu-id="687dd-876">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="687dd-877">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-877"></span></span>|
|<span data-ttu-id="687dd-878">**Identificazione personale (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="687dd-878">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="687dd-879">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-879"></span></span>|
|<span data-ttu-id="687dd-880">**PIN (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="687dd-880">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="687dd-881">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-881"></span></span>|
|<span data-ttu-id="687dd-882">**URL di revoche di certificati**</span><span class="sxs-lookup"><span data-stu-id="687dd-882">**CRL URLs**</span></span>|
|<span data-ttu-id="687dd-883">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-883"></span></span>|
   
 <span data-ttu-id="687dd-884">**Microsoft IT SSL SHA2**</span><span class="sxs-lookup"><span data-stu-id="687dd-884">**Microsoft IT SSL SHA2**</span></span>
  
||
|:-----|
|<span data-ttu-id="687dd-885">**Oggetto**</span><span class="sxs-lookup"><span data-stu-id="687dd-885">**Subject**</span></span>|
|<span data-ttu-id="687dd-886">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-886"></span></span>|
|<span data-ttu-id="687dd-887">**Autorità di certificazione**</span><span class="sxs-lookup"><span data-stu-id="687dd-887">**Issuer**</span></span>|
|<span data-ttu-id="687dd-888">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-888"></span></span>|
|<span data-ttu-id="687dd-889">**Numero di serie**</span><span class="sxs-lookup"><span data-stu-id="687dd-889">**Serial Number**</span></span>|
|<span data-ttu-id="687dd-890">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-890"></span></span>|
|<span data-ttu-id="687dd-891">**Lunghezza chiave pubblica**</span><span class="sxs-lookup"><span data-stu-id="687dd-891">**Public Key Length**</span></span>|
|<span data-ttu-id="687dd-892">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-892"></span></span>|
|<span data-ttu-id="687dd-893">**Algoritmo di firma**</span><span class="sxs-lookup"><span data-stu-id="687dd-893">**Signature Algorithm**</span></span>|
|<span data-ttu-id="687dd-894">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-894"></span></span>|
|<span data-ttu-id="687dd-895">**Validità non prima**</span><span class="sxs-lookup"><span data-stu-id="687dd-895">**Validity Not Before**</span></span>|
|<span data-ttu-id="687dd-896">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-896"></span></span>|
|<span data-ttu-id="687dd-897">**Validità non dopo**</span><span class="sxs-lookup"><span data-stu-id="687dd-897">**Validity Not After**</span></span>|
|<span data-ttu-id="687dd-898">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-898"></span></span>|
|<span data-ttu-id="687dd-899">**Identificatore chiave del soggetto**</span><span class="sxs-lookup"><span data-stu-id="687dd-899">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="687dd-900">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-900"></span></span>|
|<span data-ttu-id="687dd-901">**Identificatore chiave dell'autorità**</span><span class="sxs-lookup"><span data-stu-id="687dd-901">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="687dd-902">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-902"></span></span>|
|<span data-ttu-id="687dd-903">**Identificazione personale (SHA-1)**</span><span class="sxs-lookup"><span data-stu-id="687dd-903">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="687dd-904">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-904"></span></span>|
|<span data-ttu-id="687dd-905">**Identificazione personale (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="687dd-905">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="687dd-906">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-906"></span></span>|
|<span data-ttu-id="687dd-907">**PIN (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="687dd-907">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="687dd-908">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-908"></span></span>|
|<span data-ttu-id="687dd-909">**URL di revoche di certificati**</span><span class="sxs-lookup"><span data-stu-id="687dd-909">**CRL URLs**</span></span>|
|<span data-ttu-id="687dd-910">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-910"></span></span>|
|<span data-ttu-id="687dd-911">**URL OCSP**</span><span class="sxs-lookup"><span data-stu-id="687dd-911">**OCSP URLs**</span></span>|
|<span data-ttu-id="687dd-912">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-912"></span></span>|
   
 <span data-ttu-id="687dd-913">**Microsoft IT TLS CA 1**</span><span class="sxs-lookup"><span data-stu-id="687dd-913">**Microsoft IT TLS CA 1**</span></span>
  
||
|:-----|
|<span data-ttu-id="687dd-914">**Oggetto**</span><span class="sxs-lookup"><span data-stu-id="687dd-914">**Subject**</span></span>|
|<span data-ttu-id="687dd-915">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-915"></span></span>|
|<span data-ttu-id="687dd-916">**Autorità di certificazione**</span><span class="sxs-lookup"><span data-stu-id="687dd-916">**Issuer**</span></span>|
|<span data-ttu-id="687dd-917">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-917"></span></span>|
|<span data-ttu-id="687dd-918">**Numero di serie**</span><span class="sxs-lookup"><span data-stu-id="687dd-918">**Serial Number**</span></span>|
|<span data-ttu-id="687dd-919">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-919"></span></span>|
|<span data-ttu-id="687dd-920">**Lunghezza chiave pubblica**</span><span class="sxs-lookup"><span data-stu-id="687dd-920">**Public Key Length**</span></span>|
|<span data-ttu-id="687dd-921">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-921"></span></span>|
|<span data-ttu-id="687dd-922">**Algoritmo di firma**</span><span class="sxs-lookup"><span data-stu-id="687dd-922">**Signature Algorithm**</span></span>|
|<span data-ttu-id="687dd-923">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-923"></span></span>|
|<span data-ttu-id="687dd-924">**Validità non prima**</span><span class="sxs-lookup"><span data-stu-id="687dd-924">**Validity Not Before**</span></span>|
|<span data-ttu-id="687dd-925">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-925"></span></span>|
|<span data-ttu-id="687dd-926">**Validità non dopo**</span><span class="sxs-lookup"><span data-stu-id="687dd-926">**Validity Not After**</span></span>|
|<span data-ttu-id="687dd-927">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-927"></span></span>|
|<span data-ttu-id="687dd-928">**Identificatore chiave del soggetto**</span><span class="sxs-lookup"><span data-stu-id="687dd-928">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="687dd-929">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-929"></span></span>|
|<span data-ttu-id="687dd-930">**Identificatore chiave dell'autorità**</span><span class="sxs-lookup"><span data-stu-id="687dd-930">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="687dd-931">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-931"></span></span>|
|<span data-ttu-id="687dd-932">**Identificazione personale (SHA-1)**</span><span class="sxs-lookup"><span data-stu-id="687dd-932">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="687dd-933">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-933"></span></span>|
|<span data-ttu-id="687dd-934">**Identificazione personale (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="687dd-934">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="687dd-935">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-935"></span></span>|
|<span data-ttu-id="687dd-936">**PIN (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="687dd-936">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="687dd-937">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-937"></span></span>|
|<span data-ttu-id="687dd-938">**URL di revoche di certificati**</span><span class="sxs-lookup"><span data-stu-id="687dd-938">**CRL URLs**</span></span>|
|<span data-ttu-id="687dd-939">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-939"></span></span>|
|<span data-ttu-id="687dd-940">**URL OCSP**</span><span class="sxs-lookup"><span data-stu-id="687dd-940">**OCSP URLs**</span></span>|
|<span data-ttu-id="687dd-941">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-941"></span></span>|
   
 <span data-ttu-id="687dd-942">**Microsoft IT TLS CA 2**</span><span class="sxs-lookup"><span data-stu-id="687dd-942">**Microsoft IT TLS CA 2**</span></span>
  
||
|:-----|
|<span data-ttu-id="687dd-943">**Oggetto**</span><span class="sxs-lookup"><span data-stu-id="687dd-943">**Subject**</span></span>|
|<span data-ttu-id="687dd-944">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-944"></span></span>|
|<span data-ttu-id="687dd-945">**Autorità di certificazione**</span><span class="sxs-lookup"><span data-stu-id="687dd-945">**Issuer**</span></span>|
|<span data-ttu-id="687dd-946">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-946"></span></span>|
|<span data-ttu-id="687dd-947">**Numero di serie**</span><span class="sxs-lookup"><span data-stu-id="687dd-947">**Serial Number**</span></span>|
|<span data-ttu-id="687dd-948">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-948"></span></span>|
|<span data-ttu-id="687dd-949">**Lunghezza chiave pubblica**</span><span class="sxs-lookup"><span data-stu-id="687dd-949">**Public Key Length**</span></span>|
|<span data-ttu-id="687dd-950">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-950"></span></span>|
|<span data-ttu-id="687dd-951">**Algoritmo di firma**</span><span class="sxs-lookup"><span data-stu-id="687dd-951">**Signature Algorithm**</span></span>|
|<span data-ttu-id="687dd-952">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-952"></span></span>|
|<span data-ttu-id="687dd-953">**Validità non prima**</span><span class="sxs-lookup"><span data-stu-id="687dd-953">**Validity Not Before**</span></span>|
|<span data-ttu-id="687dd-954">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-954"></span></span>|
|<span data-ttu-id="687dd-955">**Validità non dopo**</span><span class="sxs-lookup"><span data-stu-id="687dd-955">**Validity Not After**</span></span>|
|<span data-ttu-id="687dd-956">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-956"></span></span>|
|<span data-ttu-id="687dd-957">**Identificatore chiave del soggetto**</span><span class="sxs-lookup"><span data-stu-id="687dd-957">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="687dd-958">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-958"></span></span>|
|<span data-ttu-id="687dd-959">**Identificatore chiave dell'autorità**</span><span class="sxs-lookup"><span data-stu-id="687dd-959">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="687dd-960">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-960"></span></span>|
|<span data-ttu-id="687dd-961">**Identificazione personale (SHA-1)**</span><span class="sxs-lookup"><span data-stu-id="687dd-961">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="687dd-962">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-962"></span></span>|
|<span data-ttu-id="687dd-963">**Identificazione personale (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="687dd-963">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="687dd-964">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-964"></span></span>|
|<span data-ttu-id="687dd-965">**PIN (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="687dd-965">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="687dd-966">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-966"></span></span>|
|<span data-ttu-id="687dd-967">**URL di revoche di certificati**</span><span class="sxs-lookup"><span data-stu-id="687dd-967">**CRL URLs**</span></span>|
|<span data-ttu-id="687dd-968">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-968"></span></span>|
|<span data-ttu-id="687dd-969">**URL OCSP**</span><span class="sxs-lookup"><span data-stu-id="687dd-969">**OCSP URLs**</span></span>|
|<span data-ttu-id="687dd-970">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-970"></span></span>|
   
 <span data-ttu-id="687dd-971">**Microsoft IT TLS CA 4**</span><span class="sxs-lookup"><span data-stu-id="687dd-971">**Microsoft IT TLS CA 4**</span></span>
  
||
|:-----|
|<span data-ttu-id="687dd-972">**Oggetto**</span><span class="sxs-lookup"><span data-stu-id="687dd-972">**Subject**</span></span>|
|<span data-ttu-id="687dd-973">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-973"></span></span>|
|<span data-ttu-id="687dd-974">**Autorità di certificazione**</span><span class="sxs-lookup"><span data-stu-id="687dd-974">**Issuer**</span></span>|
|<span data-ttu-id="687dd-975">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-975"></span></span>|
|<span data-ttu-id="687dd-976">**Numero di serie**</span><span class="sxs-lookup"><span data-stu-id="687dd-976">**Serial Number**</span></span>|
|<span data-ttu-id="687dd-977">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-977"></span></span>|
|<span data-ttu-id="687dd-978">**Lunghezza chiave pubblica**</span><span class="sxs-lookup"><span data-stu-id="687dd-978">**Public Key Length**</span></span>|
|<span data-ttu-id="687dd-979">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-979"></span></span>|
|<span data-ttu-id="687dd-980">**Algoritmo di firma**</span><span class="sxs-lookup"><span data-stu-id="687dd-980">**Signature Algorithm**</span></span>|
|<span data-ttu-id="687dd-981">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-981"></span></span>|
|<span data-ttu-id="687dd-982">**Validità non prima**</span><span class="sxs-lookup"><span data-stu-id="687dd-982">**Validity Not Before**</span></span>|
|<span data-ttu-id="687dd-983">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-983"></span></span>|
|<span data-ttu-id="687dd-984">**Validità non dopo**</span><span class="sxs-lookup"><span data-stu-id="687dd-984">**Validity Not After**</span></span>|
|<span data-ttu-id="687dd-985">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-985"></span></span>|
|<span data-ttu-id="687dd-986">**Identificatore chiave del soggetto**</span><span class="sxs-lookup"><span data-stu-id="687dd-986">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="687dd-987">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-987"></span></span>|
|<span data-ttu-id="687dd-988">**Identificatore chiave dell'autorità**</span><span class="sxs-lookup"><span data-stu-id="687dd-988">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="687dd-989">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-989"></span></span>|
|<span data-ttu-id="687dd-990">**Identificazione personale (SHA-1)**</span><span class="sxs-lookup"><span data-stu-id="687dd-990">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="687dd-991">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-991"></span></span>|
|<span data-ttu-id="687dd-992">**Identificazione personale (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="687dd-992">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="687dd-993">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-993"></span></span>|
|<span data-ttu-id="687dd-994">**PIN (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="687dd-994">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="687dd-995">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-995"></span></span>|
|<span data-ttu-id="687dd-996">**URL di revoche di certificati**</span><span class="sxs-lookup"><span data-stu-id="687dd-996">**CRL URLs**</span></span>|
|<span data-ttu-id="687dd-997">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-997"></span></span>|
|<span data-ttu-id="687dd-998">**URL OCSP**</span><span class="sxs-lookup"><span data-stu-id="687dd-998">**OCSP URLs**</span></span>|
|<span data-ttu-id="687dd-999">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-999"></span></span>|
   
 <span data-ttu-id="687dd-1000">**Microsoft IT TLS CA 5**</span><span class="sxs-lookup"><span data-stu-id="687dd-1000">**Microsoft IT TLS CA 5**</span></span>
  
||
|:-----|
|<span data-ttu-id="687dd-1001">**Oggetto**</span><span class="sxs-lookup"><span data-stu-id="687dd-1001">**Subject**</span></span>|
|<span data-ttu-id="687dd-1002">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-1002"></span></span>|
|<span data-ttu-id="687dd-1003">**Autorità di certificazione**</span><span class="sxs-lookup"><span data-stu-id="687dd-1003">**Issuer**</span></span>|
|<span data-ttu-id="687dd-1004">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-1004"></span></span>|
|<span data-ttu-id="687dd-1005">**Numero di serie**</span><span class="sxs-lookup"><span data-stu-id="687dd-1005">**Serial Number**</span></span>|
|<span data-ttu-id="687dd-1006">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-1006"></span></span>|
|<span data-ttu-id="687dd-1007">**Lunghezza chiave pubblica**</span><span class="sxs-lookup"><span data-stu-id="687dd-1007">**Public Key Length**</span></span>|
|<span data-ttu-id="687dd-1008">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-1008"></span></span>|
|<span data-ttu-id="687dd-1009">**Algoritmo di firma**</span><span class="sxs-lookup"><span data-stu-id="687dd-1009">**Signature Algorithm**</span></span>|
|<span data-ttu-id="687dd-1010">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-1010"></span></span>|
|<span data-ttu-id="687dd-1011">**Validità non prima**</span><span class="sxs-lookup"><span data-stu-id="687dd-1011">**Validity Not Before**</span></span>|
|<span data-ttu-id="687dd-1012">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-1012"></span></span>|
|<span data-ttu-id="687dd-1013">**Validità non dopo**</span><span class="sxs-lookup"><span data-stu-id="687dd-1013">**Validity Not After**</span></span>|
|<span data-ttu-id="687dd-1014">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-1014"></span></span>|
|<span data-ttu-id="687dd-1015">**Identificatore chiave del soggetto**</span><span class="sxs-lookup"><span data-stu-id="687dd-1015">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="687dd-1016">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-1016"></span></span>|
|<span data-ttu-id="687dd-1017">**Identificatore chiave dell'autorità**</span><span class="sxs-lookup"><span data-stu-id="687dd-1017">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="687dd-1018">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-1018"></span></span>|
|<span data-ttu-id="687dd-1019">**Identificazione personale (SHA-1)**</span><span class="sxs-lookup"><span data-stu-id="687dd-1019">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="687dd-1020">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-1020"></span></span>|
|<span data-ttu-id="687dd-1021">**Identificazione personale (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="687dd-1021">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="687dd-1022">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-1022"></span></span>|
|<span data-ttu-id="687dd-1023">**PIN (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="687dd-1023">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="687dd-1024">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-1024"></span></span>|
|<span data-ttu-id="687dd-1025">**URL di revoche di certificati**</span><span class="sxs-lookup"><span data-stu-id="687dd-1025">**CRL URLs**</span></span>|
|<span data-ttu-id="687dd-1026">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-1026"></span></span>|
|<span data-ttu-id="687dd-1027">**URL OCSP**</span><span class="sxs-lookup"><span data-stu-id="687dd-1027">**OCSP URLs**</span></span>|
|<span data-ttu-id="687dd-1028">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-1028"></span></span>|
   
 <span data-ttu-id="687dd-1029">**Classe Symantec EV 3 SSL CA - G3**</span><span class="sxs-lookup"><span data-stu-id="687dd-1029">**Symantec Class 3 EV SSL CA - G3**</span></span>
  
||
|:-----|
|<span data-ttu-id="687dd-1030">**Oggetto**</span><span class="sxs-lookup"><span data-stu-id="687dd-1030">**Subject**</span></span>|
|<span data-ttu-id="687dd-1031">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-1031"></span></span>|
|<span data-ttu-id="687dd-1032">**Autorità di certificazione**</span><span class="sxs-lookup"><span data-stu-id="687dd-1032">**Issuer**</span></span>|
|<span data-ttu-id="687dd-1033">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-1033"></span></span>|
|<span data-ttu-id="687dd-1034">**Nome alternativo soggetto**</span><span class="sxs-lookup"><span data-stu-id="687dd-1034">**Subject Alternative Name**</span></span>|
|<span data-ttu-id="687dd-1035">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-1035"></span></span>|
|<span data-ttu-id="687dd-1036">**Numero di serie**</span><span class="sxs-lookup"><span data-stu-id="687dd-1036">**Serial Number**</span></span>|
|<span data-ttu-id="687dd-1037">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-1037"></span></span>|
|<span data-ttu-id="687dd-1038">**Lunghezza chiave pubblica**</span><span class="sxs-lookup"><span data-stu-id="687dd-1038">**Public Key Length**</span></span>|
|<span data-ttu-id="687dd-1039">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-1039"></span></span>|
|<span data-ttu-id="687dd-1040">**Algoritmo di firma**</span><span class="sxs-lookup"><span data-stu-id="687dd-1040">**Signature Algorithm**</span></span>|
|<span data-ttu-id="687dd-1041">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-1041"></span></span>|
|<span data-ttu-id="687dd-1042">**Validità non prima**</span><span class="sxs-lookup"><span data-stu-id="687dd-1042">**Validity Not Before**</span></span>|
|<span data-ttu-id="687dd-1043">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-1043"></span></span>|
|<span data-ttu-id="687dd-1044">**Validità non dopo**</span><span class="sxs-lookup"><span data-stu-id="687dd-1044">**Validity Not After**</span></span>|
|<span data-ttu-id="687dd-1045">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-1045"></span></span>|
|<span data-ttu-id="687dd-1046">**Identificatore chiave del soggetto**</span><span class="sxs-lookup"><span data-stu-id="687dd-1046">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="687dd-1047">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-1047"></span></span>|
|<span data-ttu-id="687dd-1048">**Identificatore chiave dell'autorità**</span><span class="sxs-lookup"><span data-stu-id="687dd-1048">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="687dd-1049">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-1049"></span></span>|
|<span data-ttu-id="687dd-1050">**Identificazione personale (SHA-1)**</span><span class="sxs-lookup"><span data-stu-id="687dd-1050">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="687dd-1051">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-1051"></span></span>|
|<span data-ttu-id="687dd-1052">**Identificazione personale (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="687dd-1052">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="687dd-1053">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-1053"></span></span>|
|<span data-ttu-id="687dd-1054">**PIN (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="687dd-1054">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="687dd-1055">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-1055"></span></span>|
|<span data-ttu-id="687dd-1056">**URL di revoche di certificati**</span><span class="sxs-lookup"><span data-stu-id="687dd-1056">**CRL URLs**</span></span>|
|<span data-ttu-id="687dd-1057">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-1057"></span></span>|
|<span data-ttu-id="687dd-1058">**URL OCSP**</span><span class="sxs-lookup"><span data-stu-id="687dd-1058">**OCSP URLs**</span></span>|
|<span data-ttu-id="687dd-1059">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-1059"></span></span>|
   
 <span data-ttu-id="687dd-1060">**Classe Symantec 3 Server protetta CA - G4**</span><span class="sxs-lookup"><span data-stu-id="687dd-1060">**Symantec Class 3 Secure Server CA - G4**</span></span>
  
||
|:-----|
|<span data-ttu-id="687dd-1061">**Oggetto**</span><span class="sxs-lookup"><span data-stu-id="687dd-1061">**Subject**</span></span>|
|<span data-ttu-id="687dd-1062">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-1062"></span></span>|
|<span data-ttu-id="687dd-1063">**Autorità di certificazione**</span><span class="sxs-lookup"><span data-stu-id="687dd-1063">**Issuer**</span></span>|
|<span data-ttu-id="687dd-1064">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-1064"></span></span>|
|<span data-ttu-id="687dd-1065">**Nome alternativo soggetto**</span><span class="sxs-lookup"><span data-stu-id="687dd-1065">**Subject Alternative Name**</span></span>|
|<span data-ttu-id="687dd-1066">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-1066"></span></span>|
|<span data-ttu-id="687dd-1067">**Numero di serie**</span><span class="sxs-lookup"><span data-stu-id="687dd-1067">**Serial Number**</span></span>|
|<span data-ttu-id="687dd-1068">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-1068"></span></span>|
|<span data-ttu-id="687dd-1069">**Lunghezza chiave pubblica**</span><span class="sxs-lookup"><span data-stu-id="687dd-1069">**Public Key Length**</span></span>|
|<span data-ttu-id="687dd-1070">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-1070"></span></span>|
|<span data-ttu-id="687dd-1071">**Algoritmo di firma**</span><span class="sxs-lookup"><span data-stu-id="687dd-1071">**Signature Algorithm**</span></span>|
|<span data-ttu-id="687dd-1072">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-1072"></span></span>|
|<span data-ttu-id="687dd-1073">**Validità non prima**</span><span class="sxs-lookup"><span data-stu-id="687dd-1073">**Validity Not Before**</span></span>|
|<span data-ttu-id="687dd-1074">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-1074"></span></span>|
|<span data-ttu-id="687dd-1075">**Validità non dopo**</span><span class="sxs-lookup"><span data-stu-id="687dd-1075">**Validity Not After**</span></span>|
|<span data-ttu-id="687dd-1076">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-1076"></span></span>|
|<span data-ttu-id="687dd-1077">**Identificatore chiave del soggetto**</span><span class="sxs-lookup"><span data-stu-id="687dd-1077">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="687dd-1078">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-1078"></span></span>|
|<span data-ttu-id="687dd-1079">**Identificatore chiave dell'autorità**</span><span class="sxs-lookup"><span data-stu-id="687dd-1079">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="687dd-1080">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-1080"></span></span>|
|<span data-ttu-id="687dd-1081">**Identificazione personale (SHA-1)**</span><span class="sxs-lookup"><span data-stu-id="687dd-1081">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="687dd-1082">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-1082"></span></span>|
|<span data-ttu-id="687dd-1083">**Identificazione personale (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="687dd-1083">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="687dd-1084">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-1084"></span></span>|
|<span data-ttu-id="687dd-1085">**PIN (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="687dd-1085">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="687dd-1086">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-1086"></span></span>|
|<span data-ttu-id="687dd-1087">**URL di revoche di certificati**</span><span class="sxs-lookup"><span data-stu-id="687dd-1087">**CRL URLs**</span></span>|
|<span data-ttu-id="687dd-1088">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-1088"></span></span>|
|<span data-ttu-id="687dd-1089">**URL OCSP**</span><span class="sxs-lookup"><span data-stu-id="687dd-1089">**OCSP URLs**</span></span>|
|<span data-ttu-id="687dd-1090">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-1090"></span></span>|
   
 <span data-ttu-id="687dd-1091">**Thawte SHA256 SSL autorità di certificazione**</span><span class="sxs-lookup"><span data-stu-id="687dd-1091">**thawte SHA256 SSL CA**</span></span>
  
||
|:-----|
|<span data-ttu-id="687dd-1092">**Oggetto**</span><span class="sxs-lookup"><span data-stu-id="687dd-1092">**Subject**</span></span>|
|<span data-ttu-id="687dd-1093">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-1093"></span></span>|
|<span data-ttu-id="687dd-1094">**Autorità di certificazione**</span><span class="sxs-lookup"><span data-stu-id="687dd-1094">**Issuer**</span></span>|
|<span data-ttu-id="687dd-1095">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-1095"></span></span>|
|<span data-ttu-id="687dd-1096">**Nome alternativo soggetto**</span><span class="sxs-lookup"><span data-stu-id="687dd-1096">**Subject Alternative Name**</span></span>|
|<span data-ttu-id="687dd-1097">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-1097"></span></span>|
|<span data-ttu-id="687dd-1098">**Numero di serie**</span><span class="sxs-lookup"><span data-stu-id="687dd-1098">**Serial Number**</span></span>|
|<span data-ttu-id="687dd-1099">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-1099"></span></span>|
|<span data-ttu-id="687dd-1100">**Lunghezza chiave pubblica**</span><span class="sxs-lookup"><span data-stu-id="687dd-1100">**Public Key Length**</span></span>|
|<span data-ttu-id="687dd-1101">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-1101"></span></span>|
|<span data-ttu-id="687dd-1102">**Algoritmo di firma**</span><span class="sxs-lookup"><span data-stu-id="687dd-1102">**Signature Algorithm**</span></span>|
|<span data-ttu-id="687dd-1103">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-1103"></span></span>|
|<span data-ttu-id="687dd-1104">**Validità non prima**</span><span class="sxs-lookup"><span data-stu-id="687dd-1104">**Validity Not Before**</span></span>|
|<span data-ttu-id="687dd-1105">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-1105"></span></span>|
|<span data-ttu-id="687dd-1106">**Validità non dopo**</span><span class="sxs-lookup"><span data-stu-id="687dd-1106">**Validity Not After**</span></span>|
|<span data-ttu-id="687dd-1107">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-1107"></span></span>|
|<span data-ttu-id="687dd-1108">**Identificatore chiave del soggetto**</span><span class="sxs-lookup"><span data-stu-id="687dd-1108">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="687dd-1109">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-1109"></span></span>|
|<span data-ttu-id="687dd-1110">**Identificatore chiave dell'autorità**</span><span class="sxs-lookup"><span data-stu-id="687dd-1110">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="687dd-1111">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-1111"></span></span>|
|<span data-ttu-id="687dd-1112">**Identificazione personale (SHA-1)**</span><span class="sxs-lookup"><span data-stu-id="687dd-1112">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="687dd-1113">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-1113"></span></span>|
|<span data-ttu-id="687dd-1114">**Identificazione personale (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="687dd-1114">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="687dd-1115">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-1115"></span></span>|
|<span data-ttu-id="687dd-1116">**PIN (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="687dd-1116">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="687dd-1117">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-1117"></span></span>|
|<span data-ttu-id="687dd-1118">**URL di revoche di certificati**</span><span class="sxs-lookup"><span data-stu-id="687dd-1118">**CRL URLs**</span></span>|
|<span data-ttu-id="687dd-1119">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-1119"></span></span>|
|<span data-ttu-id="687dd-1120">**URL OCSP**</span><span class="sxs-lookup"><span data-stu-id="687dd-1120">**OCSP URLs**</span></span>|
|<span data-ttu-id="687dd-1121">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-1121"></span></span>|
   
 <span data-ttu-id="687dd-1122">**Autorità di certificazione SureServer Verizon Akamai G14-SHA2**</span><span class="sxs-lookup"><span data-stu-id="687dd-1122">**Verizon Akamai SureServer CA G14-SHA2**</span></span>
  
||
|:-----|
|<span data-ttu-id="687dd-1123">**Oggetto**</span><span class="sxs-lookup"><span data-stu-id="687dd-1123">**Subject**</span></span>|
|<span data-ttu-id="687dd-1124">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-1124"></span></span>|
|<span data-ttu-id="687dd-1125">**Autorità di certificazione**</span><span class="sxs-lookup"><span data-stu-id="687dd-1125">**Issuer**</span></span>|
|<span data-ttu-id="687dd-1126">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-1126"></span></span>|
|<span data-ttu-id="687dd-1127">**Numero di serie**</span><span class="sxs-lookup"><span data-stu-id="687dd-1127">**Serial Number**</span></span>|
|<span data-ttu-id="687dd-1128">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-1128"></span></span>|
|<span data-ttu-id="687dd-1129">**Lunghezza chiave pubblica**</span><span class="sxs-lookup"><span data-stu-id="687dd-1129">**Public Key Length**</span></span>|
|<span data-ttu-id="687dd-1130">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-1130"></span></span>|
|<span data-ttu-id="687dd-1131">**Algoritmo di firma**</span><span class="sxs-lookup"><span data-stu-id="687dd-1131">**Signature Algorithm**</span></span>|
|<span data-ttu-id="687dd-1132">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-1132"></span></span>|
|<span data-ttu-id="687dd-1133">**Validità non prima**</span><span class="sxs-lookup"><span data-stu-id="687dd-1133">**Validity Not Before**</span></span>|
|<span data-ttu-id="687dd-1134">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-1134"></span></span>|
|<span data-ttu-id="687dd-1135">**Validità non dopo**</span><span class="sxs-lookup"><span data-stu-id="687dd-1135">**Validity Not After**</span></span>|
|<span data-ttu-id="687dd-1136">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-1136"></span></span>|
|<span data-ttu-id="687dd-1137">**Identificatore chiave del soggetto**</span><span class="sxs-lookup"><span data-stu-id="687dd-1137">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="687dd-1138">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-1138"></span></span>|
|<span data-ttu-id="687dd-1139">**Identificatore chiave dell'autorità**</span><span class="sxs-lookup"><span data-stu-id="687dd-1139">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="687dd-1140">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-1140"></span></span>|
|<span data-ttu-id="687dd-1141">**Identificazione personale (SHA-1)**</span><span class="sxs-lookup"><span data-stu-id="687dd-1141">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="687dd-1142">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-1142"></span></span>|
|<span data-ttu-id="687dd-1143">**Identificazione personale (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="687dd-1143">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="687dd-1144">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-1144"></span></span>|
|<span data-ttu-id="687dd-1145">**PIN (SHA-256)**</span><span class="sxs-lookup"><span data-stu-id="687dd-1145">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="687dd-1146">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-1146"></span></span>|
|<span data-ttu-id="687dd-1147">**URL AIA**</span><span class="sxs-lookup"><span data-stu-id="687dd-1147">**AIA URLs**</span></span>|
|<span data-ttu-id="687dd-1148">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-1148"></span></span>|
|<span data-ttu-id="687dd-1149">**URL di revoche di certificati**</span><span class="sxs-lookup"><span data-stu-id="687dd-1149">**CRL URLs**</span></span>|
|<span data-ttu-id="687dd-1150">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-1150"></span></span>|
|<span data-ttu-id="687dd-1151">**URL OCSP**</span><span class="sxs-lookup"><span data-stu-id="687dd-1151">**OCSP URLs**</span></span>|
|<span data-ttu-id="687dd-1152">:-----</span><span class="sxs-lookup"><span data-stu-id="687dd-1152"></span></span>|
   
## <a name="additional-certificate-paths"></a><span data-ttu-id="687dd-1153">Percorsi aggiuntivi certificato</span><span class="sxs-lookup"><span data-stu-id="687dd-1153">Additional certificate paths</span></span>
<span data-ttu-id="687dd-1154"><a name="IntermediateCerts"> </a></span><span class="sxs-lookup"><span data-stu-id="687dd-1154"></span></span>

<span data-ttu-id="687dd-1155">Le operazioni seguenti includono i certificati legacy non vengono inclusi in precedenza e verranno uniti con l'elenco precedente nel tempo.</span><span class="sxs-lookup"><span data-stu-id="687dd-1155">The following include legacy certificates that aren't included above and will be merged with the list above over time.</span></span>
  
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


