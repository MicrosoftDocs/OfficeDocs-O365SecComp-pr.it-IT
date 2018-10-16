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
# <a name="office-365-certificate-chains"></a>Catena di certificati di Office 365

Office 365 si avvale di un numero di provider di certificati differenti. Di seguito vengono descritti l'elenco completo dei certificati radice di Office 365 noti che i clienti possono verificarsi quando si accede a Office 365. Per informazioni sui certificati potrebbe essere necessario installare un'infrastruttura, vedere [pianificare i certificati SSL di terze parti per Office 365](https://support.office.com/article/b48cdf63-07e0-4cda-8c12-4871590f59ce). Le seguenti informazioni sul certificato si applica a tutte le istanze di tutto il mondo e nazionali cloud di Office 365.
  

|**Tipo di certificato**|**Download P7b**|**Endpoint di revoche di certificati**|**Endpoint OCSP**|**Endpoint AIA**|
|:-----|:-----|:-----|:-----|:-----|
|[Pubblicamente attendibili i certificati radice](https://support.office.com/article/0c03e6b3-e73f-4316-9e2b-bf4091ae96bb#rootcerts) <br/> |[Bundle di certificati radice di Office 365 (P7B)](http://download.microsoft.com/download/A/5/A/A5AE01F3-D19B-4A11-9407-801263CEF72C/O365_Root_Certs_20170321.p7b) <br/> |CRL.GlobalSign.NET  <br/> www.d-trust.NET  <br/> |N/D  <br/> |N/D  <br/> |
|[Livello intermedi certificati pubblicamente attendibili](https://support.office.com/article/0c03e6b3-e73f-4316-9e2b-bf4091ae96bb#IntermediateCerts) <br/> |[Office 365 certificato intermedio Bundle (P7B)](http://download.microsoft.com/download/4/D/5/4D5339A4-0A4A-46AB-AE52-B179DEDA4BEC/O365_Intermediate_Certs_20170321.p7b)  <br/> |cdp1.Public trust.com  <br/> CRL.cnnic.CN  <br/> CRL.Entrust.NET  <br/> CRL.GlobalSign.com  <br/> CRL.GlobalSign.NET  <br/> CRL.identrust.com  <br/> CRL.Thawte.com  <br/> crl3.DigiCert.com  <br/> crl4.DigiCert.com  <br/> s1.symcb.com  <br/> www.d-trust.NET  <br/> |isrg.trustid.OCSP.identrust.com  <br/> OCSP.DigiCert.com  <br/> OCSP.Entrust.NET  <br/> OCSP.GlobalSign.com  <br/> OCSP.omniroot.com  <br/> OCSP.startssl.com  <br/> OCSP.Thawte.com  <br/> ocsp2.GlobalSign.com  <br/> ocspcnnicroot.cnnic.CN  <br/> radice-c3-ca2-2009.ocsp.d-trust.net  <br/> Root-C3-CA2-EV-2009.OCSP.d-trust.NET  <br/> s2.symcb.com  <br/> |AIA.startssl.com  <br/> Apps.identrust.com  <br/> cacert.omniroot.com  <br/> www.cnnic.CN  <br/> |
   
Espandere il nodo radice e intermedio nelle sezioni seguenti per visualizzare ulteriori informazioni sui provider di certificati.
  
## <a name="office-365-root-certificate-details"></a>Dettagli del certificato radice di Office 365
<a name="RootCerts"> </a>

 **Baltimore CyberTrust Root**
  
|:-----|
|**Oggetto**|
|:-----|
|**Numero di serie**|
|:-----|
|**Lunghezza chiave pubblica**|
|:-----|
|**Algoritmo di firma**|
|:-----|
|**Validità non prima**|
|:-----|
|**Validità non dopo**|
|:-----|
|**Identificatore chiave del soggetto**|
|:-----|
|**Identificazione personale (SHA-1)**|
|:-----|
|**Identificazione personale (SHA-256)**|
|:-----|
|**PIN (SHA-256)**|
|:-----|
   
 **RADICE CNNIC**
  
||
|:-----|
|**Oggetto**|
|:-----|
|**Numero di serie**|
|:-----|
|**Lunghezza chiave pubblica**|
|:-----|
|**Algoritmo di firma**|
|:-----|
|**Validità non prima**|
|:-----|
|**Validità non dopo**|
|:-----|
|**Identificatore chiave del soggetto**|
|:-----|
|**Identificatore chiave dell'autorità**|
|:-----|
|**Identificazione personale (SHA-1)**|
|:-----|
|**Identificazione personale (SHA-256)**|
|:-----|
|**PIN (SHA-256)**|
|:-----|
   
 **Autorità di certificazione radice globale DigiCert**
  
||
|:-----|
|**Oggetto**|
|:-----|
|**Numero di serie**|
|:-----|
|**Lunghezza chiave pubblica**|
|:-----|
|**Algoritmo di firma**|
|:-----|
|**Validità non prima**|
|:-----|
|**Validità non dopo**|
|:-----|
|**Identificatore chiave del soggetto**|
|:-----|
|**Identificatore chiave dell'autorità**|
|:-----|
|**Identificazione personale (SHA-1)**|
|:-----|
|**Identificazione personale (SHA-256)**|
|:-----|
|**PIN (SHA-256)**|
|:-----|
   
 **Autorità di certificazione radice convalida estesa con garanzia elevata DigiCert**
  
||
|:-----|
|**Oggetto**|
|:-----|
|**Numero di serie**|
|:-----|
|**Lunghezza chiave pubblica**|
|:-----|
|**Algoritmo di firma**|
|:-----|
|**Validità non prima**|
|:-----|
|**Validità non dopo**|
|:-----|
|**Identificatore chiave del soggetto**|
|:-----|
|**Identificatore chiave dell'autorità**|
|:-----|
|**Identificazione personale (SHA-1)**|
|:-----|
|**Identificazione personale (SHA-256)**|
|:-----|
|**PIN (SHA-256)**|
|:-----|
   
 **Autorità di certificazione radice D protezione classe 3 2 2009**
  
||
|:-----|
|**Oggetto**|
|:-----|
|**Numero di serie**|
|:-----|
|**Lunghezza chiave pubblica**|
|:-----|
|**Algoritmo di firma**|
|:-----|
|**Validità non prima**|
|:-----|
|**Validità non dopo**|
|:-----|
|**Identificatore chiave del soggetto**|
|:-----|
|**Identificazione personale (SHA-1)**|
|:-----|
|**Identificazione personale (SHA-256)**|
|:-----|
|**PIN (SHA-256)**|
|:-----|
|**URL di revoche di certificati**|
|:-----|
   
 **D-TRUST radice classe 3 CA 2 EV 2009**
  
||
|:-----|
|**Oggetto**|
|:-----|
|**Numero di serie**|
|:-----|
|**Lunghezza chiave pubblica**|
|:-----|
|**Algoritmo di firma**|
|:-----|
|**Validità non prima**|
|:-----|
|**Validità non dopo**|
|:-----|
|**Identificatore chiave del soggetto**|
|:-----|
|**Identificazione personale (SHA-1)**|
|:-----|
|**Identificazione personale (SHA-256)**|
|:-----|
|**PIN (SHA-256)**|
|:-----|
|**URL di revoche di certificati**|
|:-----|
   
 **LEGALE rootca X3**
  
||
|:-----|
|**Oggetto**|
|:-----|
|**Numero di serie**|
|:-----|
|**Lunghezza chiave pubblica**|
|:-----|
|**Algoritmo di firma**|
|:-----|
|**Validità non prima**|
|:-----|
|**Validità non dopo**|
|:-----|
|**Identificatore chiave del soggetto**|
|:-----|
|**Identificazione personale (SHA-1)**|
|:-----|
|**Identificazione personale (SHA-256)**|
|:-----|
|**PIN (SHA-256)**|
|:-----|
   
 **Affidare autorità di certificazione radice - G2**
  
||
|:-----|
|**Oggetto**|
|:-----|
|**Numero di serie**|
|:-----|
|**Lunghezza chiave pubblica**|
|:-----|
|**Algoritmo di firma**|
|:-----|
|**Validità non prima**|
|:-----|
|**Validità non dopo**|
|:-----|
|**Identificatore chiave del soggetto**|
|:-----|
|**Identificazione personale (SHA-1)**|
|:-----|
|**Identificazione personale (SHA-256)**|
|:-----|
|**PIN (SHA-256)**|
|:-----|
   
 **Entrust.net Certification Authority (2048)**
  
||
|:-----|
|**Oggetto**|
|:-----|
|**Numero di serie**|
|:-----|
|**Lunghezza chiave pubblica**|
|:-----|
|**Algoritmo di firma**|
|:-----|
|**Validità non prima**|
|:-----|
|**Validità non dopo**|
|:-----|
|**Identificatore chiave del soggetto**|
|:-----|
|**Identificazione personale (SHA-1)**|
|:-----|
|**Identificazione personale (SHA-256)**|
|:-----|
|**PIN (SHA-256)**|
|:-----|
   
 **GlobalSign**
  
||
|:-----|
|**Oggetto**|
|:-----|
|**Numero di serie**|
|:-----|
|**Lunghezza chiave pubblica**|
|:-----|
|**Algoritmo di firma**|
|:-----|
|**Validità non prima**|
|:-----|
|**Validità non dopo**|
|:-----|
|**Identificatore chiave del soggetto**|
|:-----|
|**Identificatore chiave dell'autorità**|
|:-----|
|**Identificazione personale (SHA-1)**|
|:-----|
|**Identificazione personale (SHA-256)**|
|:-----|
|**PIN (SHA-256)**|
|:-----|
|**URL di revoche di certificati**|
|:-----|
   
 **GlobalSign Root CA**
  
||
|:-----|
|**Oggetto**|
|:-----|
|**Numero di serie**|
|:-----|
|**Lunghezza chiave pubblica**|
|:-----|
|**Algoritmo di firma**|
|:-----|
|**Validità non prima**|
|:-----|
|**Validità non dopo**|
|:-----|
|**Identificatore chiave del soggetto**|
|:-----|
|**Identificazione personale (SHA-1)**|
|:-----|
|**Identificazione personale (SHA-256)**|
|:-----|
|**PIN (SHA-256)**|
|:-----|
   
 **Thawte CA radice principale - G3**
  
||
|:-----|
|**Oggetto**|
|:-----|
|**Numero di serie**|
|:-----|
|**Lunghezza chiave pubblica**|
|:-----|
|**Algoritmo di firma**|
|:-----|
|**Validità non prima**|
|:-----|
|**Validità non dopo**|
|:-----|
|**Identificatore chiave del soggetto**|
|:-----|
|**Identificazione personale (SHA-1)**|
|:-----|
|**Identificazione personale (SHA-256)**|
|:-----|
|**PIN (SHA-256)**|
|:-----|
   
 **Autorità di certificazione principale pubblica VeriSign classe 3 - G5**
  
||
|:-----|
|**Oggetto**|
|:-----|
|**Numero di serie**|
|:-----|
|**Lunghezza chiave pubblica**|
|:-----|
|**Algoritmo di firma**|
|:-----|
|**Validità non prima**|
|:-----|
|**Validità non dopo**|
|:-----|
|**Identificatore chiave del soggetto**|
|:-----|
|**Identificazione personale (SHA-1)**|
|:-----|
|**Identificazione personale (SHA-256)**|
|:-----|
|**PIN (SHA-256)**|
|:-----|
   
## <a name="office-365-intermediate-certificate-details"></a>Informazioni relative al certificato intermedio Office 365
<a name="IntermediateCerts"> </a>

 **CNNIC SHA256 SSL**
  
||
|:-----|
|**Oggetto**|
|:-----|
|**Autorità di certificazione**|
|:-----|
|**Numero di serie**|
|:-----|
|**Lunghezza chiave pubblica**|
|:-----|
|**Algoritmo di firma**|
|:-----|
|**Validità non prima**|
|:-----|
|**Validità non dopo**|
|:-----|
|**Identificatore chiave del soggetto**|
|:-----|
|**Identificatore chiave dell'autorità**|
|:-----|
|**Identificazione personale (SHA-1)**|
|:-----|
|**Identificazione personale (SHA-256)**|
|:-----|
|**PIN (SHA-256)**|
|:-----|
|**URL AIA**|
|:-----|
|**URL di revoche di certificati**|
|:-----|
|**URL OCSP**|
|:-----|
   
 **Autorità di certificazione classe 3 D protezione SSL 1 2009**
  
||
|:-----|
|**Oggetto**|
|:-----|
|**Autorità di certificazione**|
|:-----|
|**Nome alternativo soggetto**|
|:-----|
|**Numero di serie**|
|:-----|
|**Lunghezza chiave pubblica**|
|:-----|
|**Algoritmo di firma**|
|:-----|
|**Validità non prima**|
|:-----|
|**Validità non dopo**|
|:-----|
|**Identificatore chiave del soggetto**|
|:-----|
|**Identificatore chiave dell'autorità**|
|:-----|
|**Identificazione personale (SHA-1)**|
|:-----|
|**Identificazione personale (SHA-256)**|
|:-----|
|**PIN (SHA-256)**|
|:-----|
|**URL di revoche di certificati**|
|:-----|
|**URL OCSP**|
|:-----|
   
 **Autorità di certificazione classe 3 D protezione SSL 1 EV 2009**
  
||
|:-----|
|**Oggetto**|
|:-----|
|**Autorità di certificazione**|
|:-----|
|**Nome alternativo soggetto**|
|:-----|
|**Numero di serie**|
|:-----|
|**Lunghezza chiave pubblica**|
|:-----|
|**Algoritmo di firma**|
|:-----|
|**Validità non prima**|
|:-----|
|**Validità non dopo**|
|:-----|
|**Identificatore chiave del soggetto**|
|:-----|
|**Identificatore chiave dell'autorità**|
|:-----|
|**Identificazione personale (SHA-1)**|
|:-----|
|**Identificazione personale (SHA-256)**|
|:-----|
|**PIN (SHA-256)**|
|:-----|
|**URL di revoche di certificati**|
|:-----|
|**URL OCSP**|
|:-----|
   
 **CA-1 di servizi Cloud DigiCert**
  
||
|:-----|
|**Oggetto**|
|:-----|
|**Autorità di certificazione**|
|:-----|
|**Numero di serie**|
|:-----|
|**Lunghezza chiave pubblica**|
|:-----|
|**Algoritmo di firma**|
|:-----|
|**Validità non prima**|
|:-----|
|**Validità non dopo**|
|:-----|
|**Identificatore chiave del soggetto**|
|:-----|
|**Identificatore chiave dell'autorità**|
|:-----|
|**Identificazione personale (SHA-1)**|
|:-----|
|**Identificazione personale (SHA-256)**|
|:-----|
|**PIN (SHA-256)**|
|:-----|
|**URL di revoche di certificati**|
|:-----|
|**URL OCSP**|
|:-----|
   
 **Server di garanzia elevata DigiCert SHA2 autorità di certificazione**
  
||
|:-----|
|**Oggetto**|
|:-----|
|**Autorità di certificazione**|
|:-----|
|**Numero di serie**|
|:-----|
|**Lunghezza chiave pubblica**|
|:-----|
|**Algoritmo di firma**|
|:-----|
|**Validità non prima**|
|:-----|
|**Validità non dopo**|
|:-----|
|**Identificatore chiave del soggetto**|
|:-----|
|**Identificatore chiave dell'autorità**|
|:-----|
|**Identificazione personale (SHA-1)**|
|:-----|
|**Identificazione personale (SHA-256)**|
|:-----|
|**PIN (SHA-256)**|
|:-----|
|**URL di revoche di certificati**|
|:-----|
|**URL OCSP**|
|:-----|
   
 **Server protetto DigiCert SHA2 autorità di certificazione**
  
||
|:-----|
|**Oggetto**|
|:-----|
|**Autorità di certificazione**|
|:-----|
|**Numero di serie**|
|:-----|
|**Lunghezza chiave pubblica**|
|:-----|
|**Algoritmo di firma**|
|:-----|
|**Validità non prima**|
|:-----|
|**Validità non dopo**|
|:-----|
|**Identificatore chiave del soggetto**|
|:-----|
|**Identificatore chiave dell'autorità**|
|:-----|
|**Identificazione personale (SHA-1)**|
|:-----|
|**Identificazione personale (SHA-256)**|
|:-----|
|**PIN (SHA-256)**|
|:-----|
|**URL di revoche di certificati**|
|:-----|
|**URL OCSP**|
|:-----|
   
 **Affidare autorità di certificazione - L1C**
  
||
|:-----|
|**Oggetto**|
|:-----|
|**Autorità di certificazione**|
|:-----|
|**Numero di serie**|
|:-----|
|**Lunghezza chiave pubblica**|
|:-----|
|**Algoritmo di firma**|
|:-----|
|**Validità non prima**|
|:-----|
|**Validità non dopo**|
|:-----|
|**Identificatore chiave del soggetto**|
|:-----|
|**Identificatore chiave dell'autorità**|
|:-----|
|**Identificazione personale (SHA-1)**|
|:-----|
|**Identificazione personale (SHA-256)**|
|:-----|
|**PIN (SHA-256)**|
|:-----|
|**URL di revoche di certificati**|
|:-----|
|**URL OCSP**|
|:-----|
   
 **Affidare autorità di certificazione - L1K**
  
||
|:-----|
|**Oggetto**|
|:-----|
|**Autorità di certificazione**|
|:-----|
|**Numero di serie**|
|:-----|
|**Lunghezza chiave pubblica**|
|:-----|
|**Algoritmo di firma**|
|:-----|
|**Validità non prima**|
|:-----|
|**Validità non dopo**|
|:-----|
|**Identificatore chiave del soggetto**|
|:-----|
|**Identificatore chiave dell'autorità**|
|:-----|
|**Identificazione personale (SHA-1)**|
|:-----|
|**Identificazione personale (SHA-256)**|
|:-----|
|**PIN (SHA-256)**|
|:-----|
|**URL di revoche di certificati**|
|:-----|
|**URL OCSP**|
|:-----|
   
 **GlobalSign**
  
||
|:-----|
|**Oggetto**|
|:-----|
|**Autorità di certificazione**|
|:-----|
|**Numero di serie**|
|:-----|
|**Lunghezza chiave pubblica**|
|:-----|
|**Algoritmo di firma**|
|:-----|
|**Validità non prima**|
|:-----|
|**Validità non dopo**|
|:-----|
|**Identificatore chiave del soggetto**|
|:-----|
|**Identificatore chiave dell'autorità**|
|:-----|
|**Identificazione personale (SHA-1)**|
|:-----|
|**Identificazione personale (SHA-256)**|
|:-----|
|**PIN (SHA-256)**|
|:-----|
|**URL di revoche di certificati**|
|:-----|
|**URL OCSP**|
|:-----|
   
 **Versione estesa di convalida CA - SHA256 - G2 GlobalSign**
  
||
|:-----|
|**Oggetto**|
|:-----|
|**Autorità di certificazione**|
|:-----|
|**Numero di serie**|
|:-----|
|**Lunghezza chiave pubblica**|
|:-----|
|**Algoritmo di firma**|
|:-----|
|**Validità non prima**|
|:-----|
|**Validità non dopo**|
|:-----|
|**Identificatore chiave del soggetto**|
|:-----|
|**Identificatore chiave dell'autorità**|
|:-----|
|**Identificazione personale (SHA-1)**|
|:-----|
|**Identificazione personale (SHA-256)**|
|:-----|
|**PIN (SHA-256)**|
|:-----|
|**URL di revoche di certificati**|
|:-----|
|**URL OCSP**|
|:-----|
   
 **Versione estesa di convalida CA - SHA256 - G3 GlobalSign**
  
||
|:-----|
|**Oggetto**|
|:-----|
|**Autorità di certificazione**|
|:-----|
|**Numero di serie**|
|:-----|
|**Lunghezza chiave pubblica**|
|:-----|
|**Algoritmo di firma**|
|:-----|
|**Validità non prima**|
|:-----|
|**Validità non dopo**|
|:-----|
|**Identificatore chiave del soggetto**|
|:-----|
|**Identificatore chiave dell'autorità**|
|:-----|
|**Identificazione personale (SHA-1)**|
|:-----|
|**Identificazione personale (SHA-256)**|
|:-----|
|**PIN (SHA-256)**|
|:-----|
|**URL di revoche di certificati**|
|:-----|
|**URL OCSP**|
|:-----|
   
 **GlobalSign organizzazione convalida CA - SHA256 - G2**
  
||
|:-----|
|**Oggetto**|
|:-----|
|**Autorità di certificazione**|
|:-----|
|**Numero di serie**|
|:-----|
|**Lunghezza chiave pubblica**|
|:-----|
|**Algoritmo di firma**|
|:-----|
|**Validità non prima**|
|:-----|
|**Validità non dopo**|
|:-----|
|**Identificatore chiave del soggetto**|
|:-----|
|**Identificatore chiave dell'autorità**|
|:-----|
|**Identificazione personale (SHA-1)**|
|:-----|
|**Identificazione personale (SHA-256)**|
|:-----|
|**PIN (SHA-256)**|
|:-----|
|**URL di revoche di certificati**|
|:-----|
|**URL OCSP**|
|:-----|
   
 **GlobalSign organizzazione convalida CA - SHA256 - G2**
  
||
|:-----|
|**Oggetto**|
|:-----|
|**Autorità di certificazione**|
|:-----|
|**Numero di serie**|
|:-----|
|**Lunghezza chiave pubblica**|
|:-----|
|**Algoritmo di firma**|
|:-----|
|**Validità non prima**|
|:-----|
|**Validità non dopo**|
|:-----|
|**Identificatore chiave del soggetto**|
|:-----|
|**Identificatore chiave dell'autorità**|
|:-----|
|**Identificazione personale (SHA-1)**|
|:-----|
|**Identificazione personale (SHA-256)**|
|:-----|
|**PIN (SHA-256)**|
|:-----|
|**URL di revoche di certificati**|
|:-----|
|**URL OCSP**|
|:-----|
   
 **Crittografare possiamo autorità X3**
  
||
|:-----|
|**Oggetto**|
|:-----|
|**Autorità di certificazione**|
|:-----|
|**Numero di serie**|
|:-----|
|**Lunghezza chiave pubblica**|
|:-----|
|**Algoritmo di firma**|
|:-----|
|**Validità non prima**|
|:-----|
|**Validità non dopo**|
|:-----|
|**Identificatore chiave del soggetto**|
|:-----|
|**Identificatore chiave dell'autorità**|
|:-----|
|**Identificazione personale (SHA-1)**|
|:-----|
|**Identificazione personale (SHA-256)**|
|:-----|
|**PIN (SHA-256)**|
|:-----|
|**URL AIA**|
|:-----|
|**URL di revoche di certificati**|
|:-----|
|**URL OCSP**|
|:-----|
   
 **Microsoft IT SSL SHA2**
  
||
|:-----|
|**Oggetto**|
|:-----|
|**Autorità di certificazione**|
|:-----|
|**Numero di serie**|
|:-----|
|**Lunghezza chiave pubblica**|
|:-----|
|**Algoritmo di firma**|
|:-----|
|**Validità non prima**|
|:-----|
|**Validità non dopo**|
|:-----|
|**Identificatore chiave del soggetto**|
|:-----|
|**Identificatore chiave dell'autorità**|
|:-----|
|**Identificazione personale (SHA-1)**|
|:-----|
|**Identificazione personale (SHA-256)**|
|:-----|
|**PIN (SHA-256)**|
|:-----|
|**URL di revoche di certificati**|
|:-----|
   
 **Microsoft IT SSL SHA2**
  
||
|:-----|
|**Oggetto**|
|:-----|
|**Autorità di certificazione**|
|:-----|
|**Numero di serie**|
|:-----|
|**Lunghezza chiave pubblica**|
|:-----|
|**Algoritmo di firma**|
|:-----|
|**Validità non prima**|
|:-----|
|**Validità non dopo**|
|:-----|
|**Identificatore chiave del soggetto**|
|:-----|
|**Identificatore chiave dell'autorità**|
|:-----|
|**Identificazione personale (SHA-1)**|
|:-----|
|**Identificazione personale (SHA-256)**|
|:-----|
|**PIN (SHA-256)**|
|:-----|
|**URL di revoche di certificati**|
|:-----|
|**URL OCSP**|
|:-----|
   
 **Microsoft IT TLS CA 1**
  
||
|:-----|
|**Oggetto**|
|:-----|
|**Autorità di certificazione**|
|:-----|
|**Numero di serie**|
|:-----|
|**Lunghezza chiave pubblica**|
|:-----|
|**Algoritmo di firma**|
|:-----|
|**Validità non prima**|
|:-----|
|**Validità non dopo**|
|:-----|
|**Identificatore chiave del soggetto**|
|:-----|
|**Identificatore chiave dell'autorità**|
|:-----|
|**Identificazione personale (SHA-1)**|
|:-----|
|**Identificazione personale (SHA-256)**|
|:-----|
|**PIN (SHA-256)**|
|:-----|
|**URL di revoche di certificati**|
|:-----|
|**URL OCSP**|
|:-----|
   
 **Microsoft IT TLS CA 2**
  
||
|:-----|
|**Oggetto**|
|:-----|
|**Autorità di certificazione**|
|:-----|
|**Numero di serie**|
|:-----|
|**Lunghezza chiave pubblica**|
|:-----|
|**Algoritmo di firma**|
|:-----|
|**Validità non prima**|
|:-----|
|**Validità non dopo**|
|:-----|
|**Identificatore chiave del soggetto**|
|:-----|
|**Identificatore chiave dell'autorità**|
|:-----|
|**Identificazione personale (SHA-1)**|
|:-----|
|**Identificazione personale (SHA-256)**|
|:-----|
|**PIN (SHA-256)**|
|:-----|
|**URL di revoche di certificati**|
|:-----|
|**URL OCSP**|
|:-----|
   
 **Microsoft IT TLS CA 4**
  
||
|:-----|
|**Oggetto**|
|:-----|
|**Autorità di certificazione**|
|:-----|
|**Numero di serie**|
|:-----|
|**Lunghezza chiave pubblica**|
|:-----|
|**Algoritmo di firma**|
|:-----|
|**Validità non prima**|
|:-----|
|**Validità non dopo**|
|:-----|
|**Identificatore chiave del soggetto**|
|:-----|
|**Identificatore chiave dell'autorità**|
|:-----|
|**Identificazione personale (SHA-1)**|
|:-----|
|**Identificazione personale (SHA-256)**|
|:-----|
|**PIN (SHA-256)**|
|:-----|
|**URL di revoche di certificati**|
|:-----|
|**URL OCSP**|
|:-----|
   
 **Microsoft IT TLS CA 5**
  
||
|:-----|
|**Oggetto**|
|:-----|
|**Autorità di certificazione**|
|:-----|
|**Numero di serie**|
|:-----|
|**Lunghezza chiave pubblica**|
|:-----|
|**Algoritmo di firma**|
|:-----|
|**Validità non prima**|
|:-----|
|**Validità non dopo**|
|:-----|
|**Identificatore chiave del soggetto**|
|:-----|
|**Identificatore chiave dell'autorità**|
|:-----|
|**Identificazione personale (SHA-1)**|
|:-----|
|**Identificazione personale (SHA-256)**|
|:-----|
|**PIN (SHA-256)**|
|:-----|
|**URL di revoche di certificati**|
|:-----|
|**URL OCSP**|
|:-----|
   
 **Classe Symantec EV 3 SSL CA - G3**
  
||
|:-----|
|**Oggetto**|
|:-----|
|**Autorità di certificazione**|
|:-----|
|**Nome alternativo soggetto**|
|:-----|
|**Numero di serie**|
|:-----|
|**Lunghezza chiave pubblica**|
|:-----|
|**Algoritmo di firma**|
|:-----|
|**Validità non prima**|
|:-----|
|**Validità non dopo**|
|:-----|
|**Identificatore chiave del soggetto**|
|:-----|
|**Identificatore chiave dell'autorità**|
|:-----|
|**Identificazione personale (SHA-1)**|
|:-----|
|**Identificazione personale (SHA-256)**|
|:-----|
|**PIN (SHA-256)**|
|:-----|
|**URL di revoche di certificati**|
|:-----|
|**URL OCSP**|
|:-----|
   
 **Classe Symantec 3 Server protetta CA - G4**
  
||
|:-----|
|**Oggetto**|
|:-----|
|**Autorità di certificazione**|
|:-----|
|**Nome alternativo soggetto**|
|:-----|
|**Numero di serie**|
|:-----|
|**Lunghezza chiave pubblica**|
|:-----|
|**Algoritmo di firma**|
|:-----|
|**Validità non prima**|
|:-----|
|**Validità non dopo**|
|:-----|
|**Identificatore chiave del soggetto**|
|:-----|
|**Identificatore chiave dell'autorità**|
|:-----|
|**Identificazione personale (SHA-1)**|
|:-----|
|**Identificazione personale (SHA-256)**|
|:-----|
|**PIN (SHA-256)**|
|:-----|
|**URL di revoche di certificati**|
|:-----|
|**URL OCSP**|
|:-----|
   
 **Thawte SHA256 SSL autorità di certificazione**
  
||
|:-----|
|**Oggetto**|
|:-----|
|**Autorità di certificazione**|
|:-----|
|**Nome alternativo soggetto**|
|:-----|
|**Numero di serie**|
|:-----|
|**Lunghezza chiave pubblica**|
|:-----|
|**Algoritmo di firma**|
|:-----|
|**Validità non prima**|
|:-----|
|**Validità non dopo**|
|:-----|
|**Identificatore chiave del soggetto**|
|:-----|
|**Identificatore chiave dell'autorità**|
|:-----|
|**Identificazione personale (SHA-1)**|
|:-----|
|**Identificazione personale (SHA-256)**|
|:-----|
|**PIN (SHA-256)**|
|:-----|
|**URL di revoche di certificati**|
|:-----|
|**URL OCSP**|
|:-----|
   
 **Autorità di certificazione SureServer Verizon Akamai G14-SHA2**
  
||
|:-----|
|**Oggetto**|
|:-----|
|**Autorità di certificazione**|
|:-----|
|**Numero di serie**|
|:-----|
|**Lunghezza chiave pubblica**|
|:-----|
|**Algoritmo di firma**|
|:-----|
|**Validità non prima**|
|:-----|
|**Validità non dopo**|
|:-----|
|**Identificatore chiave del soggetto**|
|:-----|
|**Identificatore chiave dell'autorità**|
|:-----|
|**Identificazione personale (SHA-1)**|
|:-----|
|**Identificazione personale (SHA-256)**|
|:-----|
|**PIN (SHA-256)**|
|:-----|
|**URL AIA**|
|:-----|
|**URL di revoche di certificati**|
|:-----|
|**URL OCSP**|
|:-----|
   
## <a name="additional-certificate-paths"></a>Percorsi aggiuntivi certificato
<a name="IntermediateCerts"> </a>

Le operazioni seguenti includono i certificati legacy non vengono inclusi in precedenza e verranno uniti con l'elenco precedente nel tempo.
  
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


