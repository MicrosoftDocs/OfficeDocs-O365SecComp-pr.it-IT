---
title: Elementi inclusi nei modelli del criterio DLP
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 6/29/2018
ms.audience: Admin
ms.topic: reference
f1_keywords:
- ms.o365.cc.DLPNewPolicyFromTemplate
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: c2e588d3-8f4f-4937-a286-8c399f28953a
description: Prevenzione perdita dati (DLP) in Office 365 Security &amp; centro conformità include modelli di criteri pronte per l'utilizzo di soddisfare i requisiti di conformità comuni, ad esempio servizio di supporto per la protezione delle informazioni riservate soggetti (U.S. Health Insurance Act HIPAA), Stati Uniti Gramm-Leach-Bliley Act (GLBA) o US Patriot Act. In questo argomento elenca tutti i criteri di modelli, quali tipi di informazioni riservate cercare e quali sono le condizioni predefinite e le azioni.
ms.openlocfilehash: 345738244b9573b1af4d55ede86a568bf136f048
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/27/2018
ms.locfileid: "22530963"
---
# <a name="what-the-dlp-policy-templates-include"></a>Elementi inclusi nei modelli del criterio DLP

Prevenzione perdita dati (DLP) in Office 365 Security &amp; centro conformità include modelli di criteri pronte per l'utilizzo di soddisfare i requisiti di conformità comuni, ad esempio servizio di supporto per la protezione delle informazioni riservate soggetti (U.S. Health Insurance Act HIPAA), Stati Uniti Gramm-Leach-Bliley Act (GLBA) o US Patriot Act. In questo argomento elenca tutti i criteri di modelli, quali tipi di informazioni riservate cercare e quali sono le condizioni predefinite e le azioni. In questo argomento non include tutti i dettagli di configurazione di ogni modello dei criteri; in realtà, l'argomento consente di Visualizza è sufficiente informazioni utili per decidere quale modello è il punto di partenza ottimale per lo scenario. Si tenga presente che è possibile personalizzare i modelli di criteri in base alle specifiche esigenze.
  
## <a name="australia-financial-data"></a>Dati finanziari Australia

|**Nome regola**|**Condizioni <br/> (inclusi i tipi di informazioni riservate)**|**Azioni**|
|:-----|:-----|:-----|
|Dati finanziari Australia: analisi dei contenuti condivisi con l'esterno - conteggio basso  <br/> | I contenuti includono informazioni riservate:  <br/>  Codice SWIFT - Conteggio minimo 1, conteggio massimo 9  <br/>  Codice fiscale Australia - conteggio minimo 1, conteggio massimo 9  <br/>  Numero di conto corrente (Australia) - conteggio minimo 1, conteggio massimo 9  <br/>  Numero di carta di credito - conteggio minimo 1, conteggio massimo 9  <br/>  I contenuti vengono condivisi con:  <br/>  Persone esterne all'organizzazione  <br/> |Inviare una notifica  <br/> |
|Dati finanziari Australia: analisi dei contenuti condivisi con l'esterno - conteggio elevato  <br/> | I contenuti includono informazioni riservate:  <br/>  Codice SWIFT - Conteggio minimo 10, conteggio massimo illimitato  <br/>  Codice fiscale Australia - conteggio minimo 10, conteggio massimo illimitato  <br/>  Numero di conto corrente (Australia) - conteggio minimo 10, conteggio massimo illimitato  <br/>  Numero di carta di credito - conteggio minimo 10, conteggio massimo illimitato  <br/>  I contenuti vengono condivisi con:  <br/>  Persone esterne all'organizzazione  <br/> | Bloccare l'accesso ai contenuti  <br/>  Inviare una notifica  <br/>  Consentire override  <br/>  Richiedere una motivazione aziendale  <br/>  Inviare rapporto operazioni non consentite  <br/> |
   
## <a name="australia-health-records-act-hrip-act"></a>Australia Health Records Act (HRIP Act)

|**Nome regola**|**Condizioni <br/> (inclusi i tipi di informazioni riservate)**|**Azioni**|
|:-----|:-----|:-----|
|HRIP Australia: analisi dei contenuti condivisi con l'esterno - conteggio basso  <br/> | I contenuti includono informazioni riservate:  <br/>  Codice fiscale Australia - conteggio minimo 1, conteggio massimo 9  <br/>  Numero libretto sanitario (Australia) - conteggio minimo 1, conteggio massimo 9  <br/>  I contenuti vengono condivisi con:  <br/>  Persone esterne all'organizzazione  <br/> |Inviare una notifica  <br/> |
|HRIP Australia: analisi dei contenuti condivisi con l'esterno - conteggio elevato  <br/> | I contenuti includono informazioni riservate:  <br/>  Codice fiscale Australia - conteggio minimo 10, conteggio massimo illimitato  <br/>  Numero libretto sanitario (Australia) - conteggio minimo 10, conteggio massimo illimitato  <br/>  I contenuti vengono condivisi con:  <br/>  Persone esterne all'organizzazione  <br/> | Bloccare l'accesso ai contenuti  <br/>  Inviare una notifica  <br/>  Consentire override  <br/>  Richiedere una motivazione aziendale  <br/>  Inviare rapporto operazioni non consentite  <br/> |
   
## <a name="australia-personally-identifiable-information-pii-data"></a>Dati di identificazione personale (PII) in Australia

|**Nome regola**|**Condizioni <br/> (inclusi i tipi di informazioni riservate)**|**Azioni**|
|:-----|:-----|:-----|
|PII Australia: analisi dei contenuti condivisi con l'esterno - conteggio basso  <br/> | I contenuti includono informazioni riservate:  <br/>  Codice fiscale Australia - conteggio minimo 1, conteggio massimo 9  <br/>  Numero della patente australiana - conteggio minimo 1, conteggio massimo 9  <br/>  I contenuti vengono condivisi con:  <br/>  Persone esterne all'organizzazione  <br/> |Inviare una notifica  <br/> |
|PII Australia: analisi dei contenuti condivisi con l'esterno - conteggio elevato  <br/> | I contenuti includono informazioni riservate:  <br/>  Codice fiscale Australia - conteggio minimo 10, conteggio massimo illimitato  <br/>  Numero della patente australiana - conteggio minimo 10, conteggio massimo illimitato  <br/>  I contenuti vengono condivisi con:  <br/>  Persone esterne all'organizzazione  <br/> | Bloccare l'accesso ai contenuti  <br/>  Inviare una notifica  <br/>  Consentire override  <br/>  Richiedere una motivazione aziendale  <br/>  Inviare rapporto operazioni non consentite  <br/> |
   
## <a name="australia-privacy-act"></a>Legge sulla privacy in Australia

|**Nome regola**|**Condizioni <br/> (inclusi i tipi di informazioni riservate)**|**Azioni**|
|:-----|:-----|:-----|
|Legge sulla privacy Australia: analisi dei contenuti condivisi con l'esterno - conteggio basso  <br/> | I contenuti includono informazioni riservate:  <br/>  Numero della patente australiana - conteggio minimo 1, conteggio massimo 9  <br/>  Numero di passaporto austrliano - conteggio minimo 1, conteggio massimo 9  <br/>  I contenuti vengono condivisi con:  <br/>  Persone esterne all'organizzazione  <br/> |Inviare una notifica  <br/> |
|Legge sulla privacy Australia: analisi dei contenuti condivisi con l'esterno - conteggio elevato  <br/> | I contenuti includono informazioni riservate:  <br/>  Numero della patente australiana - conteggio minimo 10, conteggio massimo illimitato  <br/>  Numero di passaporto austrliano - conteggio minimo 10, conteggio massimo illimitato  <br/>  I contenuti vengono condivisi con:  <br/>  Persone esterne all'organizzazione  <br/> | Bloccare l'accesso ai contenuti  <br/>  Inviare una notifica  <br/>  Consentire override  <br/>  Richiedere una motivazione aziendale  <br/>  Inviare rapporto operazioni non consentite  <br/> |
   
## <a name="canada-financial-data"></a>Dati finanziari Canada

|**Nome regola**|**Condizioni <br/> (inclusi i tipi di informazioni riservate)**|**Azioni**|
|:-----|:-----|:-----|
|Dati finanziari Canada: analisi dei contenuti condivisi con l'esterno - conteggio basso  <br/> | I contenuti includono informazioni riservate:  <br/>  Numero di carta di credito - conteggio minimo 1, conteggio massimo 9  <br/>  Numero di conto corrente (Canada) - conteggio minimo 1, conteggio massimo 9  <br/>  I contenuti vengono condivisi con:  <br/>  Persone esterne all'organizzazione  <br/> |Inviare una notifica  <br/> |
|Dati finanziari Canada: analisi dei contenuti condivisi con l'esterno - conteggio elevato  <br/> | I contenuti includono informazioni riservate:  <br/>  Numero di carta di credito - conteggio minimo 10, conteggio massimo illimitato  <br/>  Numero di conto corrente (Canada) - conteggio minimo 10, conteggio massimo illimitato  <br/>  I contenuti vengono condivisi con:  <br/>  Persone esterne all'organizzazione  <br/> | Bloccare l'accesso ai contenuti  <br/>  Inviare una notifica  <br/>  Consentire override  <br/>  Richiedere una motivazione aziendale  <br/>  Inviare rapporto operazioni non consentite  <br/> |
   
## <a name="canada-health-information-act-hia"></a>Canada Health Information Act (HIA)

|**Nome regola**|**Condizioni <br/> (inclusi i tipi di informazioni riservate)**|**Azioni**|
|:-----|:-----|:-----|
|HIA Canada: analisi dei contenuti condivisi con l'esterno - conteggio basso  <br/> | I contenuti includono informazioni riservate:  <br/>  Numero di passaporto canadese - conteggio minimo 1, conteggio massimo 9  <br/>  Numero di previdenza sociale canadese - conteggio minimo 1, conteggio massimo 9  <br/>  Tessera sanitaria canadese - conteggio minimo 1, conteggio massimo 9  <br/>  Tessera sanitaria personale (PHIN, Canada) - conteggio minimo 1, conteggio massimo 9  <br/>  I contenuti vengono condivisi con:  <br/>  Persone esterne all'organizzazione  <br/> |Inviare una notifica  <br/> |
|HIA Canada: analisi dei contenuti condivisi con l'esterno - conteggio elevato  <br/> | I contenuti includono informazioni riservate:  <br/>  Numero di passaporto canadese - conteggio minimo 10, conteggio massimo illimitato  <br/>  Numero di previdenza sociale canadese - conteggio minimo 10, conteggio massimo illimitato  <br/>  Tessera sanitaria canadese - conteggio minimo 10, conteggio massimo illimitato  <br/>  Tessera sanitaria personale (PHIN, Canada) - conteggio minimo 10, conteggio massimo illimitato  <br/>  I contenuti vengono condivisi con:  <br/>  Persone esterne all'organizzazione  <br/> | Bloccare l'accesso ai contenuti  <br/>  Inviare una notifica  <br/>  Consentire override  <br/>  Richiedere una motivazione aziendale  <br/>  Inviare rapporto operazioni non consentite  <br/> |
   
## <a name="canada-personal-health-act-phipa---ontario"></a>Canada Personal Health Act (PHIPA) - Ontario

|**Nome regola**|**Condizioni <br/> (inclusi i tipi di informazioni riservate)**|**Azioni**|
|:-----|:-----|:-----|
|PHIPA Canada: analisi dei contenuti condivisi con l'esterno - conteggio basso  <br/> | I contenuti includono informazioni riservate:  <br/>  Numero di passaporto canadese - conteggio minimo 1, conteggio massimo 9  <br/>  Numero di previdenza sociale canadese - conteggio minimo 1, conteggio massimo 9  <br/>  Tessera sanitaria canadese - conteggio minimo 1, conteggio massimo 9  <br/>  Tessera sanitaria personale (PHIN, Canada) - conteggio minimo 1, conteggio massimo 9  <br/>  I contenuti vengono condivisi con:  <br/>  Persone esterne all'organizzazione  <br/> |Inviare una notifica  <br/> |
|PHIPA Canada: analisi dei contenuti condivisi con l'esterno - conteggio elevato  <br/> | I contenuti includono informazioni riservate:  <br/>  Numero di passaporto canadese - conteggio minimo 10, conteggio massimo illimitato  <br/>  Numero di previdenza sociale canadese - conteggio minimo 10, conteggio massimo illimitato  <br/>  Tessera sanitaria canadese - conteggio minimo 10, conteggio massimo illimitato  <br/>  Tessera sanitaria personale (PHIN, Canada) - conteggio minimo 10, conteggio massimo illimitato  <br/>  I contenuti vengono condivisi con:  <br/>  Persone esterne all'organizzazione  <br/> | Bloccare l'accesso ai contenuti  <br/>  Inviare una notifica  <br/>  Consentire override  <br/>  Richiedere una motivazione aziendale  <br/>  Inviare rapporto operazioni non consentite  <br/> |
   
## <a name="canada-personal-health-information-act-phia---manitoba"></a>Canada Personal Health Information Act (PHIA) - Manitoba

|**Nome regola**|**Condizioni <br/> (inclusi i tipi di informazioni riservate)**|**Azioni**|
|:-----|:-----|:-----|
|PHIA Canada: analisi dei contenuti condivisi con l'esterno - conteggio basso  <br/> | I contenuti includono informazioni riservate:  <br/>  Numero di previdenza sociale canadese - conteggio minimo 1, conteggio massimo 9  <br/>  Tessera sanitaria canadese - conteggio minimo 1, conteggio massimo 9  <br/>  Tessera sanitaria personale (PHIN, Canada) - conteggio minimo 1, conteggio massimo 9  <br/>  I contenuti vengono condivisi con:  <br/>  Persone esterne all'organizzazione  <br/> |Inviare una notifica  <br/> |
|PHIA Canada: analisi dei contenuti condivisi con l'esterno - conteggio elevato  <br/> | I contenuti includono informazioni riservate:  <br/>  Numero di previdenza sociale canadese - conteggio minimo 10, conteggio massimo illimitato  <br/>  Tessera sanitaria canadese - conteggio minimo 10, conteggio massimo illimitato  <br/>  Tessera sanitaria personale (PHIN, Canada) - conteggio minimo 10, conteggio massimo illimitato  <br/>  I contenuti vengono condivisi con:  <br/>  Persone esterne all'organizzazione  <br/> | Bloccare l'accesso ai contenuti  <br/>  Inviare una notifica  <br/>  Consentire override  <br/>  Richiedere una motivazione aziendale  <br/>  Inviare rapporto operazioni non consentite  <br/> |
   
## <a name="canada-personal-information-protection-act-pipa"></a>Canada Personal Information Protection Act (PIPA)

|**Nome regola**|**Condizioni <br/> (inclusi i tipi di informazioni riservate)**|**Azioni**|
|:-----|:-----|:-----|
|PIPA Canada: analisi dei contenuti condivisi con l'esterno - conteggio basso  <br/> | I contenuti includono informazioni riservate:  <br/>  Numero di passaporto canadese - conteggio minimo 1, conteggio massimo 9  <br/>  Numero di previdenza sociale canadese - conteggio minimo 1, conteggio massimo 9  <br/>  Tessera sanitaria canadese - conteggio minimo 1, conteggio massimo 9  <br/>  Tessera sanitaria personale (PHIN, Canada) - conteggio minimo 1, conteggio massimo 9  <br/>  I contenuti vengono condivisi con:  <br/>  Persone esterne all'organizzazione  <br/> |Inviare una notifica  <br/> |
|PIPA Canada: analisi dei contenuti condivisi con l'esterno - conteggio elevato  <br/> | I contenuti includono informazioni riservate:  <br/>  Numero di passaporto canadese - conteggio minimo 10, conteggio massimo illimitato  <br/>  Numero di previdenza sociale canadese - conteggio minimo 10, conteggio massimo illimitato  <br/>  Tessera sanitaria canadese - conteggio minimo 10, conteggio massimo illimitato  <br/>  Tessera sanitaria personale (PHIN, Canada) - conteggio minimo 10, conteggio massimo illimitato  <br/>  I contenuti vengono condivisi con:  <br/>  Persone esterne all'organizzazione  <br/> | Bloccare l'accesso ai contenuti  <br/>  Inviare una notifica  <br/>  Consentire override  <br/>  Richiedere una motivazione aziendale  <br/>  Inviare rapporto operazioni non consentite  <br/> |
   
## <a name="canada-personal-information-protection-act-pipeda"></a>Canada Personal Information Protection Act (PIPEDA)

|**Nome regola**|**Condizioni <br/> (inclusi i tipi di informazioni riservate)**|**Azioni**|
|:-----|:-----|:-----|
|PIPEDA Canada: analisi dei contenuti condivisi con l'esterno - conteggio basso  <br/> | I contenuti includono informazioni riservate:  <br/>  Numero della patente canadese - conteggio minimo 1, conteggio massimo 9  <br/>  Numero di conto corrente (Canada) - conteggio minimo 1, conteggio massimo 9  <br/>  Numero di passaporto canadese - conteggio minimo 1, conteggio massimo 9  <br/>  Numero di previdenza sociale canadese - conteggio minimo 1, conteggio massimo 9  <br/>  Tessera sanitaria canadese - conteggio minimo 1, conteggio massimo 9  <br/>  Tessera sanitaria personale (PHIN, Canada) - conteggio minimo 1, conteggio massimo 9  <br/>  I contenuti vengono condivisi con:  <br/>  Persone esterne all'organizzazione  <br/> |Inviare una notifica  <br/> |
|PIPEDA Canada: analisi dei contenuti condivisi con l'esterno - conteggio elevato  <br/> | I contenuti includono informazioni riservate:  <br/>  Numero della patente canadese - conteggio minimo 10, conteggio massimo illimitato  <br/>  Numero di conto corrente (Canada) - conteggio minimo 10, conteggio massimo illimitato  <br/>  Numero di passaporto canadese - conteggio minimo 10, conteggio massimo illimitato  <br/>  Numero di previdenza sociale canadese - conteggio minimo 10, conteggio massimo illimitato  <br/>  Tessera sanitaria canadese - conteggio minimo 10, conteggio massimo illimitato  <br/>  Tessera sanitaria personale (PHIN, Canada) - conteggio minimo 10, conteggio massimo illimitato  <br/>  I contenuti vengono condivisi con:  <br/>  Persone esterne all'organizzazione  <br/> | Bloccare l'accesso ai contenuti  <br/>  Inviare una notifica  <br/>  Consentire override  <br/>  Richiedere una motivazione aziendale  <br/>  Inviare rapporto operazioni non consentite  <br/> |
   
## <a name="canada-personally-identifiable-information-pii-data"></a>Dati di identificazione personale (PII) in Canada

|**Nome regola**|**Condizioni <br/> (inclusi i tipi di informazioni riservate)**|**Azioni**|
|:-----|:-----|:-----|
|PII Canada: analisi dei contenuti condivisi con l'esterno - conteggio basso  <br/> | I contenuti includono informazioni riservate:  <br/>  Numero della patente canadese - conteggio minimo 1, conteggio massimo 9  <br/>  Numero di conto corrente (Canada) - conteggio minimo 1, conteggio massimo 9  <br/>  Numero di passaporto canadese - conteggio minimo 1, conteggio massimo 9  <br/>  Numero di previdenza sociale canadese - conteggio minimo 1, conteggio massimo 9  <br/>  Tessera sanitaria canadese - conteggio minimo 1, conteggio massimo 9  <br/>  Tessera sanitaria personale (PHIN, Canada) - conteggio minimo 1, conteggio massimo 9  <br/>  I contenuti vengono condivisi con:  <br/>  Persone esterne all'organizzazione  <br/> |Inviare una notifica  <br/> |
|PII Canada: analisi dei contenuti condivisi con l'esterno - conteggio elevato  <br/> | I contenuti includono informazioni riservate:  <br/>  Numero della patente canadese - conteggio minimo 10, conteggio massimo illimitato  <br/>  Numero di conto corrente (Canada) - conteggio minimo 10, conteggio massimo illimitato  <br/>  Numero di passaporto canadese - conteggio minimo 10, conteggio massimo illimitato  <br/>  Numero di previdenza sociale canadese - conteggio minimo 10, conteggio massimo illimitato  <br/>  Tessera sanitaria canadese - conteggio minimo 10, conteggio massimo illimitato  <br/>  Tessera sanitaria personale (PHIN, Canada) - conteggio minimo 10, conteggio massimo illimitato  <br/>  I contenuti vengono condivisi con:  <br/>  Persone esterne all'organizzazione  <br/> | Bloccare l'accesso ai contenuti  <br/>  Inviare una notifica  <br/>  Consentire override  <br/>  Richiedere una motivazione aziendale  <br/>  Inviare rapporto operazioni non consentite  <br/> |
   
## <a name="france-data-protection-act"></a>France Data Protection Act

|**Nome regola**|**Condizioni <br/> (inclusi i tipi di informazioni riservate)**|**Azioni**|
|:-----|:-----|:-----|
|Legge sulla protezione dei dati Francia: analisi dei contenuti condivisi con l'esterno - conteggio basso  <br/> | I contenuti includono informazioni riservate:  <br/>  Carta di identità francese - conteggio minimo 1, conteggio massimo 9  <br/>  Codice di previdenza sociale francese (INSEE) - conteggio minimo 1, conteggio massimo 9  <br/>  I contenuti vengono condivisi con:  <br/>  Persone esterne all'organizzazione  <br/> |Inviare una notifica  <br/> |
|Legge sulla protezione dei dati Francia: analisi dei contenuti condivisi con l'esterno - conteggio elevato  <br/> | I contenuti includono informazioni riservate:  <br/>  Carta di identità francese - conteggio minimo 10, conteggio massimo illimitato  <br/>  Codice di previdenza sociale francese (INSEE) - conteggio minimo 10, conteggio massimo illimitato  <br/>  I contenuti vengono condivisi con:  <br/>  Persone esterne all'organizzazione  <br/> | Bloccare l'accesso ai contenuti  <br/>  Inviare una notifica  <br/>  Consentire override  <br/>  Richiedere una motivazione aziendale  <br/>  Inviare rapporto operazioni non consentite  <br/> |
   
## <a name="france-financial-data"></a>Dati finanziari Francia

|**Nome regola**|**Condizioni <br/> (inclusi i tipi di informazioni riservate)**|**Azioni**|
|:-----|:-----|:-----|
|Dati finanziari Francia: analisi dei contenuti condivisi con l'esterno - conteggio basso  <br/> | I contenuti includono informazioni riservate:  <br/>  Numero di carta di credito - conteggio minimo 1, conteggio massimo 9  <br/>  Numero di carta di debito UE - conteggio minimo 1, conteggio massimo 9  <br/>  I contenuti vengono condivisi con:  <br/>  Persone esterne all'organizzazione  <br/> |Inviare una notifica  <br/> |
|Dati finanziari Francia: analisi dei contenuti condivisi con l'esterno - conteggio elevato  <br/> | I contenuti includono informazioni riservate:  <br/>  Numero di carta di credito - conteggio minimo 10, conteggio massimo illimitato  <br/>  Numero di carta di debito UE - conteggio minimo 10, conteggio massimo illimitato  <br/>  I contenuti vengono condivisi con:  <br/>  Persone esterne all'organizzazione  <br/> | Bloccare l'accesso ai contenuti  <br/>  Inviare una notifica  <br/>  Consentire override  <br/>  Richiedere una motivazione aziendale  <br/>  Inviare rapporto operazioni non consentite  <br/> |
   
## <a name="france-personally-identifiable-information-pii-data"></a>Dati di identificazione personale (PII) in Francia

|**Nome regola**|**Condizioni <br/> (inclusi i tipi di informazioni riservate)**|**Azioni**|
|:-----|:-----|:-----|
|Informazioni personali Francia: analisi dei contenuti condivisi con l'esterno - conteggio basso  <br/> | I contenuti includono informazioni riservate:  <br/>  Codice di previdenza sociale francese (INSEE) - conteggio minimo 1, conteggio massimo 9  <br/>  Numero della patente francese - conteggio minimo 1, conteggio massimo 9  <br/>  Numero di passaporto francese - conteggio minimo 1, conteggio massimo 9  <br/>  Carta di identità francese - conteggio minimo 1, conteggio massimo 9  <br/>  I contenuti vengono condivisi con:  <br/>  Persone esterne all'organizzazione  <br/> |Inviare una notifica  <br/> |
|Informazioni personali Francia: analisi dei contenuti condivisi con l'esterno - conteggio elevato  <br/> | I contenuti includono informazioni riservate:  <br/>  Codice di previdenza sociale francese (INSEE) - conteggio minimo 10, conteggio massimo illimitato  <br/>  Numero della patente francese - conteggio minimo 10, conteggio massimo illimitato  <br/>  Numero di passaporto francese - conteggio minimo 10, conteggio massimo illimitato  <br/>  Carta di identità francese - conteggio minimo 10, conteggio massimo illimitato  <br/>  I contenuti vengono condivisi con:  <br/>  Persone esterne all'organizzazione  <br/> | Bloccare l'accesso ai contenuti  <br/>  Inviare una notifica  <br/>  Consentire override  <br/>  Richiedere una motivazione aziendale  <br/>  Inviare rapporto operazioni non consentite  <br/> |
   
## <a name="general-data-protection-regulation-gdpr"></a>Protezione dati generali nella regolazione (PILR)

|**Nome regola**|**Condizioni <br/> (inclusi i tipi di informazioni riservate)**|**Azioni**|
|:-----|:-----|:-----|
|Volume ridotto trovare contenuto UE riservati  <br/> | I contenuti includono informazioni riservate:  <br/>  Numero di carta di debito UE - conteggio minimo 1, conteggio massimo 9  <br/>  Numero della patente di Guida di Unione europea-numero Max 9, il conteggio Min 1  <br/>  UE nazionale Identification Number, Conteggio Min 1, numero massimo di 9  <br/>  Numero di passaporto UE, Conteggio Min 1, il numero massimo 9  <br/>  Unione europea numero di previdenza sociale (SSN) o l'ID equivalenti, Min numero 1, il numero massimo 9  <br/>  Conteggio Min UE imposte identificazione numero (ID), 1, il numero massimo 9  <br/>  I contenuti vengono condivisi con:  <br/>  Persone esterne all'organizzazione  <br/> |Inviare segnalazioni di incidente all'amministratore  <br/> |
|Numero elevato di UE riservati contenuto disponibile  <br/> | I contenuti includono informazioni riservate:  <br/>  Numero di carta di debito UE - conteggio minimo 1, conteggio massimo 9  <br/>  Numero della patente di Guida di Unione europea-numero Max 9, il conteggio Min 1  <br/>  UE nazionale Identification Number, Conteggio Min 1, numero massimo di 9  <br/>  Numero di passaporto UE, Conteggio Min 1, il numero massimo 9  <br/>  Unione europea numero di previdenza sociale (SSN) o l'ID equivalenti, Min numero 1, il numero massimo 9  <br/>  Conteggio Min UE imposte identificazione numero (ID), 1, il numero massimo 9  <br/>  I contenuti vengono condivisi con:  <br/>  Persone esterne all'organizzazione  <br/> | Limitare l'accesso al contenuto per gli utenti esterni  <br/>  Notificare agli utenti con i suggerimenti di posta elettronica e dei criteri  <br/>  Consentire override  <br/>  Richiedere una motivazione aziendale  <br/>  Inviare segnalazioni di incidente all'amministratore  <br/> |
   
## <a name="germany-financial-data"></a>Dati finanziari Germania

|**Nome regola**|**Condizioni <br/> (inclusi i tipi di informazioni riservate)**|**Azioni**|
|:-----|:-----|:-----|
|Dati finanziari Germania: analisi dei contenuti condivisi con l'esterno - conteggio basso  <br/> | I contenuti includono informazioni riservate:  <br/>  Numero di carta di credito - conteggio minimo 1, conteggio massimo 9  <br/>  Numero di carta di debito UE - conteggio minimo 1, conteggio massimo 9  <br/>  I contenuti vengono condivisi con:  <br/>  Persone esterne all'organizzazione  <br/> |Inviare una notifica  <br/> |
|Dati finanziari Germania: analisi dei contenuti condivisi con l'esterno - conteggio elevato  <br/> | I contenuti includono informazioni riservate:  <br/>  Numero di carta di credito - conteggio minimo 10, conteggio massimo illimitato  <br/>  Numero di carta di debito UE - conteggio minimo 10, conteggio massimo illimitato  <br/>  I contenuti vengono condivisi con:  <br/>  Persone esterne all'organizzazione  <br/> | Bloccare l'accesso ai contenuti  <br/>  Inviare una notifica  <br/>  Consentire override  <br/>  Richiedere una motivazione aziendale  <br/>  Inviare rapporto operazioni non consentite  <br/> |
   
## <a name="germany-personally-identifiable-information-pii-data"></a>Dati di identificazione personale (PII) in Germania

|**Nome regola**|**Condizioni <br/> (inclusi i tipi di informazioni riservate)**|**Azioni**|
|:-----|:-----|:-----|
|Informazioni personali Germania: analisi dei contenuti condivisi con l'esterno - conteggio basso  <br/> | I contenuti includono informazioni riservate:  <br/>  Numero della patente tedesca - conteggio minimo 1, conteggio massimo 9  <br/>  Numero di passaporto tedesco - conteggio minimo 1, conteggio massimo 9  <br/>  I contenuti vengono condivisi con:  <br/>  Persone esterne all'organizzazione  <br/> |Inviare una notifica  <br/> |
|Informazioni personali Germania: analisi dei contenuti condivisi con l'esterno - conteggio elevato  <br/> | I contenuti includono informazioni riservate:  <br/>  Numero della patente tedesca - conteggio minimo 10, conteggio massimo illimitato  <br/>  Numero di passaporto tedesco - conteggio minimo 10, conteggio massimo illimitato  <br/>  I contenuti vengono condivisi con:  <br/>  Persone esterne all'organizzazione  <br/> | Bloccare l'accesso ai contenuti  <br/>  Inviare una notifica  <br/>  Consentire override  <br/>  Richiedere una motivazione aziendale  <br/>  Inviare rapporto operazioni non consentite  <br/> |
   
## <a name="israel-financial-data"></a>Dati finanziari Israele

|**Nome regola**|**Condizioni <br/> (inclusi i tipi di informazioni riservate)**|**Azioni**|
|:-----|:-----|:-----|
|Dati finanziari Israele: analisi dei contenuti condivisi con l'esterno - conteggio basso  <br/> | I contenuti includono informazioni riservate:  <br/>  Numero di conto corrente (Israele) - conteggio minimo 1, conteggio massimo 9  <br/>  Codice SWIFT - Conteggio minimo 1, conteggio massimo 9  <br/>  Numero di carta di credito - conteggio minimo 1, conteggio massimo 9  <br/>  I contenuti vengono condivisi con:  <br/>  Persone esterne all'organizzazione  <br/> |Inviare una notifica  <br/> |
|Dati finanziari Israele: analisi dei contenuti condivisi con l'esterno - conteggio elevato  <br/> | I contenuti includono informazioni riservate:  <br/>  Numero di conto corrente (Israele) - conteggio minimo 10, conteggio massimo illimitato  <br/>  Codice SWIFT - Conteggio minimo 10, conteggio massimo illimitato  <br/>  Numero di carta di credito - conteggio minimo 10, conteggio massimo illimitato  <br/>  I contenuti vengono condivisi con:  <br/>  Persone esterne all'organizzazione  <br/> | Bloccare l'accesso ai contenuti  <br/>  Inviare una notifica  <br/>  Consentire override  <br/>  Richiedere una motivazione aziendale  <br/>  Inviare rapporto operazioni non consentite  <br/> |
   
## <a name="israel-personally-identifiable-information-pii-data"></a>Dati di identificazione personale (PII) in Israele

|**Nome regola**|**Condizioni <br/> (inclusi i tipi di informazioni riservate)**|**Azioni**|
|:-----|:-----|:-----|
|Informazioni personali Israele: analisi dei contenuti condivisi con l'esterno - conteggio basso  <br/> | I contenuti includono informazioni riservate:  <br/>  Carta di identità (Israele) - conteggio minimo 1, conteggio massimo 9  <br/>  I contenuti vengono condivisi con:  <br/>  Persone esterne all'organizzazione  <br/> |Inviare una notifica  <br/> |
|Informazioni personali Israele: analisi dei contenuti condivisi con l'esterno - conteggio elevato  <br/> | I contenuti includono informazioni riservate:  <br/>  Carta di identità (Israele) - conteggio minimo 10, conteggio massimo illimitato  <br/>  I contenuti vengono condivisi con:  <br/>  Persone esterne all'organizzazione  <br/> | Bloccare l'accesso ai contenuti  <br/>  Inviare una notifica  <br/>  Consentire override  <br/>  Richiedere una motivazione aziendale  <br/>  Inviare rapporto operazioni non consentite  <br/> |
   
## <a name="israel-protection-of-privacy"></a>Tutela della Privacy in Israele

|**Nome regola**|**Condizioni <br/> (inclusi i tipi di informazioni riservate)**|**Azioni**|
|:-----|:-----|:-----|
|Legge sulla privacy israeliana: analisi dei contenuti condivisi con l'esterno - conteggio basso  <br/> | I contenuti includono informazioni riservate:  <br/>  Carta di identità (Israele) - conteggio minimo 1, conteggio massimo 9  <br/>  Numero di conto corrente (Israele) - conteggio minimo 1, conteggio massimo 9  <br/>  I contenuti vengono condivisi con:  <br/>  Persone esterne all'organizzazione  <br/> |Inviare una notifica  <br/> |
|Legge sulla privacy israeliana: analisi dei contenuti condivisi con l'esterno - conteggio elevato  <br/> | I contenuti includono informazioni riservate:  <br/>  Carta di identità (Israele) - conteggio minimo 10, conteggio massimo illimitato  <br/>  Numero di conto corrente (Israele) - conteggio minimo 10, conteggio massimo illimitato  <br/>  I contenuti vengono condivisi con:  <br/>  Persone esterne all'organizzazione  <br/> | Bloccare l'accesso ai contenuti  <br/>  Inviare una notifica  <br/>  Consentire override  <br/>  Richiedere una motivazione aziendale  <br/>  Inviare rapporto operazioni non consentite  <br/> |
   
## <a name="japan-financial-data"></a>Dati finanziari Giappone

|**Nome regola**|**Condizioni <br/> (inclusi i tipi di informazioni riservate)**|**Azioni**|
|:-----|:-----|:-----|
|Dati finanziari Giappone: analisi dei contenuti condivisi con l'esterno - conteggio basso  <br/> | I contenuti includono informazioni riservate:  <br/>  Numero di conto corrente (Giappone) - conteggio minimo 1, conteggio massimo 9  <br/>  Numero di carta di credito - conteggio minimo 1, conteggio massimo 9  <br/>  I contenuti vengono condivisi con:  <br/>  Persone esterne all'organizzazione  <br/> |Inviare una notifica  <br/> |
|Dati finanziari Giappone: analisi dei contenuti condivisi con l'esterno - conteggio elevato  <br/> | I contenuti includono informazioni riservate:  <br/>  Numero di conto corrente (Giappone) - conteggio minimo 10, conteggio massimo illimitato  <br/>  Numero di carta di credito - conteggio minimo 10, conteggio massimo illimitato  <br/>  I contenuti vengono condivisi con:  <br/>  Persone esterne all'organizzazione  <br/> | Bloccare l'accesso ai contenuti  <br/>  Inviare una notifica  <br/>  Consentire override  <br/>  Richiedere una motivazione aziendale  <br/>  Inviare rapporto operazioni non consentite  <br/> |
   
## <a name="japan-personally-identifiable-information-pii-data"></a>Dati di identificazione personale (PII) in Giappone

|**Nome regola**|**Condizioni <br/> (inclusi i tipi di informazioni riservate)**|**Azioni**|
|:-----|:-----|:-----|
|Informazioni personali Giappone: analisi dei contenuti condivisi con l'esterno - conteggio basso  <br/> | I contenuti includono informazioni riservate:  <br/>  Numero di registrazione all'elenco dei residenti (Giappone) - conteggio minimo 1, conteggio massimo 9  <br/>  Numero di previdenza sociale (SIN, Giappone) - conteggio minimo 1, conteggio massimo 9  <br/>  I contenuti vengono condivisi con:  <br/>  Persone esterne all'organizzazione  <br/> |Inviare una notifica  <br/> |
|Informazioni personali Giappone: analisi dei contenuti condivisi con l'esterno - conteggio elevato  <br/> | I contenuti includono informazioni riservate:  <br/>  Numero di registrazione all'elenco dei residenti (Giappone) - conteggio minimo 10, conteggio massimo illimitato  <br/>  Numero di previdenza sociale (SIN, Giappone) - conteggio minimo 10, conteggio massimo illimitato  <br/>  I contenuti vengono condivisi con:  <br/>  Persone esterne all'organizzazione  <br/> | Bloccare l'accesso ai contenuti  <br/>  Inviare una notifica  <br/>  Consentire override  <br/>  Richiedere una motivazione aziendale  <br/>  Inviare rapporto operazioni non consentite  <br/> |
   
## <a name="japan-protection-of-personal-information"></a>Protezione dei dati personali in Giappone

|**Nome regola**|**Condizioni <br/> (inclusi i tipi di informazioni riservate)**|**Azioni**|
|:-----|:-----|:-----|
|Informazioni personali Giappone: analisi dei contenuti condivisi con l'esterno - conteggio basso  <br/> | I contenuti includono informazioni riservate:  <br/>  Numero di registrazione all'elenco dei residenti (Giappone) - conteggio minimo 1, conteggio massimo 9  <br/>  Numero di previdenza sociale (SIN, Giappone) - conteggio minimo 1, conteggio massimo 9  <br/>  I contenuti vengono condivisi con:  <br/>  Persone esterne all'organizzazione  <br/> |Inviare una notifica  <br/> |
|Informazioni personali Giappone: analisi dei contenuti condivisi con l'esterno - conteggio elevato  <br/> | I contenuti includono informazioni riservate:  <br/>  Numero di registrazione all'elenco dei residenti (Giappone) - conteggio minimo 10, conteggio massimo illimitato  <br/>  Numero di previdenza sociale (SIN, Giappone) - conteggio minimo 10, conteggio massimo illimitato  <br/>  I contenuti vengono condivisi con:  <br/>  Persone esterne all'organizzazione  <br/> | Bloccare l'accesso ai contenuti  <br/>  Inviare una notifica  <br/>  Consentire override  <br/>  Richiedere una motivazione aziendale  <br/>  Inviare rapporto operazioni non consentite  <br/> |
   
## <a name="pci-data-security-standard-pci-dss"></a>PCI Data Security Standard (PCI DSS)

|**Nome regola**|**Condizioni <br/> (inclusi i tipi di informazioni riservate)**|**Azioni**|
|:-----|:-----|:-----|
|PCI DSS: analisi dei contenuti condivisi con l'esterno - conteggio basso  <br/> | I contenuti includono informazioni riservate:  <br/>  Numero di carta di credito - conteggio minimo 1, conteggio massimo 9  <br/>  I contenuti vengono condivisi con:  <br/>  Persone esterne all'organizzazione  <br/> |Inviare una notifica  <br/> |
|PCI DSS: analisi dei contenuti condivisi con l'esterno - conteggio elevato  <br/> | I contenuti includono informazioni riservate:  <br/>  Numero di carta di credito - conteggio minimo 10, conteggio massimo illimitato  <br/>  I contenuti vengono condivisi con:  <br/>  Persone esterne all'organizzazione  <br/> | Bloccare l'accesso ai contenuti  <br/>  Inviare una notifica  <br/>  Consentire override  <br/>  Richiedere una motivazione aziendale  <br/>  Inviare rapporto operazioni non consentite  <br/> |
   
## <a name="saudi-arabia---anti-cyber-crime-law"></a>Saudi Arabia - Anti-Cyber Crime Law

|**Nome regola**|**Condizioni <br/> (inclusi i tipi di informazioni riservate)**|**Azioni**|
|:-----|:-----|:-----|
|ACC Arabia Saudita: analisi dei contenuti condivisi con l'esterno - conteggio basso  <br/> | I contenuti includono informazioni riservate:  <br/>  Codice SWIFT - Conteggio minimo 1, conteggio massimo 9  <br/>  IBAN - conteggio minimo 1, conteggio massimo 9  <br/>  I contenuti vengono condivisi con:  <br/>  Persone esterne all'organizzazione  <br/> |Inviare una notifica  <br/> |
|ACC Arabia Saudita: analisi dei contenuti condivisi con l'esterno - conteggio elevato  <br/> | I contenuti includono informazioni riservate:  <br/>  Codice SWIFT - Conteggio minimo 10, conteggio massimo illimitato  <br/>  IBAN - conteggio minimo 10, conteggio massimo illimitato  <br/>  I contenuti vengono condivisi con:  <br/>  Persone esterne all'organizzazione  <br/> | Bloccare l'accesso ai contenuti  <br/>  Inviare una notifica  <br/>  Consentire override  <br/>  Richiedere una motivazione aziendale  <br/>  Inviare rapporto operazioni non consentite  <br/> |
   
## <a name="saudi-arabia-financial-data"></a>Dati finanziari Arabia Saudita

|**Nome regola**|**Condizioni <br/> (inclusi i tipi di informazioni riservate)**|**Azioni**|
|:-----|:-----|:-----|
|Dati finanziari Arabia Saudita: analisi dei contenuti condivisi con l'esterno - conteggio basso  <br/> | I contenuti includono informazioni riservate:  <br/>  Numero di carta di credito - conteggio minimo 1, conteggio massimo 9  <br/>  Codice SWIFT - Conteggio minimo 1, conteggio massimo 9  <br/>  IBAN - conteggio minimo 1, conteggio massimo 9  <br/>  I contenuti vengono condivisi con:  <br/>  Persone esterne all'organizzazione  <br/> |Inviare una notifica  <br/> |
|Dati finanziari Arabia Saudita: analisi dei contenuti condivisi con l'esterno - conteggio elevato  <br/> | I contenuti includono informazioni riservate:  <br/>  Numero di carta di credito - conteggio minimo 10, conteggio massimo illimitato  <br/>  Codice SWIFT - Conteggio minimo 10, conteggio massimo illimitato  <br/>  IBAN - conteggio minimo 10, conteggio massimo illimitato  <br/>  I contenuti vengono condivisi con:  <br/>  Persone esterne all'organizzazione  <br/> | Bloccare l'accesso ai contenuti  <br/>  Inviare una notifica  <br/>  Consentire override  <br/>  Richiedere una motivazione aziendale  <br/>  Inviare rapporto operazioni non consentite  <br/> |
   
## <a name="saudi-arabia-personally-identifiable-information-pii-data"></a>Dati di identificazione personale (PII) in Arabia Saudita

|**Nome regola**|**Condizioni <br/> (inclusi i tipi di informazioni riservate)**|**Azioni**|
|:-----|:-----|:-----|
|Informazioni personali Arabia Saudita: analisi dei contenuti condivisi con l'esterno - conteggio basso  <br/> | I contenuti includono informazioni riservate:  <br/>  Carta di identità (Arabia Saudita) - conteggio minimo 1, conteggio massimo 9  <br/>  I contenuti vengono condivisi con:  <br/>  Persone esterne all'organizzazione  <br/> |Inviare una notifica  <br/> |
|Informazioni personali Arabia Saudita: analisi dei contenuti condivisi con l'esterno - conteggio elevato  <br/> | I contenuti includono informazioni riservate:  <br/>  Carta di identità (Arabia Saudita) - conteggio minimo 10, conteggio massimo illimitato  <br/>  I contenuti vengono condivisi con:  <br/>  Persone esterne all'organizzazione  <br/> | Bloccare l'accesso ai contenuti  <br/>  Inviare una notifica  <br/>  Consentire override  <br/>  Richiedere una motivazione aziendale  <br/>  Inviare rapporto operazioni non consentite  <br/> |
   
## <a name="uk-access-to-medical-reports-act"></a>U.K. Access to Medical Reports Act

|**Nome regola**|**Condizioni <br/> (inclusi i tipi di informazioni riservate)**|**Azioni**|
|:-----|:-----|:-----|
|AMRA Regno Unito: analisi dei contenuti condivisi con l'esterno - conteggio basso  <br/> | I contenuti includono informazioni riservate:  <br/>  Tessera sanitaria Regno Unito - conteggio minimo 1, conteggio massimo 9  <br/>  Codice fiscale (NINO, Regno Unito) - conteggio minimo 1, conteggio massimo 9  <br/>  I contenuti vengono condivisi con:  <br/>  Persone esterne all'organizzazione  <br/> |Inviare una notifica  <br/> |
|AMRA Regno Unito: analisi dei contenuti condivisi con l'esterno - conteggio elevato  <br/> | I contenuti includono informazioni riservate:  <br/>  Tessera sanitaria Regno Unito - conteggio minimo 10, conteggio massimo illimitato  <br/>  Codice fiscale (NINO, Regno Unito) - conteggio minimo 10, conteggio massimo illimitato  <br/>  I contenuti vengono condivisi con:  <br/>  Persone esterne all'organizzazione  <br/> | Bloccare l'accesso ai contenuti  <br/>  Inviare una notifica  <br/>  Consentire override  <br/>  Richiedere una motivazione aziendale  <br/>  Inviare rapporto operazioni non consentite  <br/> |
   
## <a name="uk-data-protection-act"></a>U.K. Data Protection Act

|**Nome regola**|**Condizioni <br/> (inclusi i tipi di informazioni riservate)**|**Azioni**|
|:-----|:-----|:-----|
|Legge sulla protezione dei dati Regno Unito: analisi dei contenuti condivisi con l'esterno - conteggio basso  <br/> | I contenuti includono informazioni riservate:  <br/>  Codice fiscale (NINO, Regno Unito) - conteggio minimo 1, conteggio massimo 9  <br/>  Numero di passaporto Regno Unito/Stati Uniti - conteggio minimo 1, conteggio massimo 9  <br/>  Codice SWIFT - Conteggio minimo 1, conteggio massimo 9  <br/>  I contenuti vengono condivisi con:  <br/>  Persone esterne all'organizzazione  <br/> |Inviare una notifica  <br/> |
|Legge sulla protezione dei dati Regno Unito: analisi dei contenuti condivisi con l'esterno - conteggio elevato  <br/> | I contenuti includono informazioni riservate:  <br/>  Codice fiscale (NINO, Regno Unito) - conteggio minimo 10, conteggio massimo illimitato  <br/>  Numero di passaporto Regno Unito/Stati Uniti - conteggio minimo 10, conteggio massimo illimitato  <br/>  Codice SWIFT - Conteggio minimo 10, conteggio massimo illimitato  <br/>  I contenuti vengono condivisi con:  <br/>  Persone esterne all'organizzazione  <br/> | Bloccare l'accesso ai contenuti  <br/>  Inviare una notifica  <br/>  Consentire override  <br/>  Richiedere una motivazione aziendale  <br/>  Inviare rapporto operazioni non consentite  <br/> |
   
## <a name="uk-financial-data"></a>Dati finanziari Regno Unito

|**Nome regola**|**Condizioni <br/> (inclusi i tipi di informazioni riservate)**|**Azioni**|
|:-----|:-----|:-----|
|Dati finanziari Regno Unito: analisi dei contenuti condivisi con l'esterno - conteggio basso  <br/> | I contenuti includono informazioni riservate:  <br/>  Numero di carta di credito - conteggio minimo 1, conteggio massimo 9  <br/>  Numero di carta di debito UE - conteggio minimo 1, conteggio massimo 9  <br/>  Codice SWIFT - Conteggio minimo 1, conteggio massimo 9  <br/>  I contenuti vengono condivisi con:  <br/>  Persone esterne all'organizzazione  <br/> |Inviare una notifica  <br/> |
|Dati finanziari Regno Unito: analisi dei contenuti condivisi con l'esterno - conteggio elevato  <br/> | I contenuti includono informazioni riservate:  <br/>  Numero di carta di credito - conteggio minimo 10, conteggio massimo illimitato  <br/>  Numero di carta di debito UE - conteggio minimo 10, conteggio massimo illimitato  <br/>  Codice SWIFT - Conteggio minimo 10, conteggio massimo illimitato  <br/>  I contenuti vengono condivisi con:  <br/>  Persone esterne all'organizzazione  <br/> | Bloccare l'accesso ai contenuti  <br/>  Inviare una notifica  <br/>  Consentire override  <br/>  Richiedere una motivazione aziendale  <br/>  Inviare rapporto operazioni non consentite  <br/> |
   
## <a name="uk-personal-information-online-code-of-practice-piocp"></a>U.K. Personal Information Online Code of Practice (PIOCP)

|**Nome regola**|**Condizioni <br/> (inclusi i tipi di informazioni riservate)**|**Azioni**|
|:-----|:-----|:-----|
|PIOCP Regno Unito: analisi dei contenuti condivisi con l'esterno - conteggio basso  <br/> | I contenuti includono informazioni riservate:  <br/>  Codice fiscale (NINO, Regno Unito) - conteggio minimo 1, conteggio massimo 9  <br/>  Tessera sanitaria Regno Unito - conteggio minimo 1, conteggio massimo 9  <br/>  Codice SWIFT - Conteggio minimo 1, conteggio massimo 9  <br/>  I contenuti vengono condivisi con:  <br/>  Persone esterne all'organizzazione  <br/> |Inviare una notifica  <br/> |
|PIOCP Regno Unito: analisi dei contenuti condivisi con l'esterno - conteggio elevato  <br/> | I contenuti includono informazioni riservate:  <br/>  Codice fiscale (NINO, Regno Unito) - conteggio minimo 10, conteggio massimo illimitato  <br/>  Tessera sanitaria Regno Unito - conteggio minimo 10, conteggio massimo illimitato  <br/>  Codice SWIFT - Conteggio minimo 10, conteggio massimo illimitato  <br/>  I contenuti vengono condivisi con:  <br/>  Persone esterne all'organizzazione  <br/> | Bloccare l'accesso ai contenuti  <br/>  Inviare una notifica  <br/>  Consentire override  <br/>  Richiedere una motivazione aziendale  <br/>  Inviare rapporto operazioni non consentite  <br/> |
   
## <a name="uk-personally-identifiable-information-pii-data"></a>Dati di identificazione personale (PII) Regno Unito

|**Nome regola**|**Condizioni <br/> (inclusi i tipi di informazioni riservate)**|**Azioni**|
|:-----|:-----|:-----|
|Informazioni personali Regno Unito: analisi dei contenuti condivisi con l'esterno - conteggio basso  <br/> | I contenuti includono informazioni riservate:  <br/>  Codice fiscale (NINO, Regno Unito) - conteggio minimo 1, conteggio massimo 9  <br/>  Numero di passaporto Regno Unito/Stati Uniti - conteggio minimo 1, conteggio massimo 9  <br/>  I contenuti vengono condivisi con:  <br/>  Persone esterne all'organizzazione  <br/> |Inviare una notifica  <br/> |
|Informazioni personali Regno Unito: analisi dei contenuti condivisi con l'esterno - conteggio elevato  <br/> | I contenuti includono informazioni riservate:  <br/>  Codice fiscale (NINO, Regno Unito) - conteggio minimo 10, conteggio massimo illimitato  <br/>  Numero di passaporto Regno Unito/Stati Uniti - conteggio minimo 10, conteggio massimo illimitato  <br/>  I contenuti vengono condivisi con:  <br/>  Persone esterne all'organizzazione  <br/> | Bloccare l'accesso ai contenuti  <br/>  Inviare una notifica  <br/>  Consentire override  <br/>  Richiedere una motivazione aziendale  <br/>  Inviare rapporto operazioni non consentite  <br/> |
   
## <a name="uk-privacy-and-electronic-communications-regulations"></a>U.K. Privacy and Electronic Communications Regulations

|**Nome regola**|**Condizioni <br/> (inclusi i tipi di informazioni riservate)**|**Azioni**|
|:-----|:-----|:-----|
|PECR Regno Unito: analisi dei contenuti condivisi con l'esterno - conteggio basso  <br/> | I contenuti includono informazioni riservate:  <br/>  Codice SWIFT - Conteggio minimo 1, conteggio massimo 9  <br/>  I contenuti vengono condivisi con:  <br/>  Persone esterne all'organizzazione  <br/> |Inviare una notifica  <br/> |
|PECR Regno Unito: analisi dei contenuti condivisi con l'esterno - conteggio elevato  <br/> | I contenuti includono informazioni riservate:  <br/>  Codice SWIFT - Conteggio minimo 10, conteggio massimo illimitato  <br/>  I contenuti vengono condivisi con:  <br/>  Persone esterne all'organizzazione  <br/> | Bloccare l'accesso ai contenuti  <br/>  Inviare una notifica  <br/>  Consentire override  <br/>  Richiedere una motivazione aziendale  <br/>  Inviare rapporto operazioni non consentite  <br/> |
   
## <a name="us-federal-trade-commission-ftc-consumer-rules"></a>U.S. Federal Trade Commission (FTC) Consumer Rules

|**Nome regola**|**Condizioni <br/> (inclusi i tipi di informazioni riservate)**|**Azioni**|
|:-----|:-----|:-----|
|Norme FTC Stati Uniti: analisi dei contenuti condivisi con l'esterno - conteggio basso  <br/> | I contenuti includono informazioni riservate:  <br/>  Numero di carta di credito - conteggio minimo 1, conteggio massimo 9  <br/>  Numero di conto corrente (Stati Uniti) - conteggio minimo 1, conteggio massimo 9  <br/>  Codice ABA - conteggio minimo 1, conteggio massimo 9  <br/>  I contenuti vengono condivisi con:  <br/>  Persone esterne all'organizzazione  <br/> |Inviare una notifica  <br/> |
|Norme FTC Stati Uniti: analisi dei contenuti condivisi con l'esterno - conteggio elevato  <br/> | I contenuti includono informazioni riservate:  <br/>  Numero di carta di credito - conteggio minimo 10, conteggio massimo illimitato  <br/>  Numero di conto corrente (Stati Uniti) - conteggio minimo 10, conteggio massimo illimitato  <br/>  Codice ABA - conteggio minimo 10, conteggio massimo illimitato  <br/>  I contenuti vengono condivisi con:  <br/>  Persone esterne all'organizzazione  <br/> | Bloccare l'accesso ai contenuti  <br/>  Inviare una notifica  <br/>  Consentire override  <br/>  Richiedere una motivazione aziendale  <br/>  Inviare rapporto operazioni non consentite  <br/> |
   
## <a name="us-financial-data"></a>Dati finanziari USA

|**Nome regola**|**Condizioni <br/> (inclusi i tipi di informazioni riservate)**|**Azioni**|
|:-----|:-----|:-----|
|Dati finanziari Stati Uniti: analisi dei contenuti condivisi con l'esterno - conteggio basso  <br/> | I contenuti includono informazioni riservate:  <br/>  Numero di carta di credito - conteggio minimo 1, conteggio massimo 9  <br/>  Numero di conto corrente (Stati Uniti) - conteggio minimo 1, conteggio massimo 9  <br/>  Codice ABA - conteggio minimo 1, conteggio massimo 9  <br/>  I contenuti vengono condivisi con:  <br/>  Persone esterne all'organizzazione  <br/> |Inviare una notifica  <br/> |
|Dati finanziari Stati Uniti: analisi dei contenuti condivisi con l'esterno - conteggio elevato  <br/> | I contenuti includono informazioni riservate:  <br/>  Numero di carta di credito - conteggio minimo 10, conteggio massimo illimitato  <br/>  Numero di conto corrente (Stati Uniti) - conteggio minimo 10, conteggio massimo illimitato  <br/>  Codice ABA - conteggio minimo 10, conteggio massimo illimitato  <br/>  I contenuti vengono condivisi con:  <br/>  Persone esterne all'organizzazione  <br/> | Bloccare l'accesso ai contenuti  <br/>  Inviare una notifica  <br/>  Consentire override  <br/>  Richiedere una motivazione aziendale  <br/>  Inviare rapporto operazioni non consentite  <br/> |
   
## <a name="us-gramm-leach-bliley-act-glba"></a>U.S. Gramm-Leach-Bliley Act (GLBA)

|**Nome regola**|**Condizioni <br/> (inclusi i tipi di informazioni riservate)**|**Azioni**|
|:-----|:-----|:-----|
|GLBA Stati Uniti: analisi dei contenuti condivisi con l'esterno - conteggio basso  <br/> | I contenuti includono informazioni riservate:  <br/>  Numero di carta di credito - conteggio minimo 1, conteggio massimo 9  <br/>  Numero di conto corrente (Stati Uniti) - conteggio minimo 1, conteggio massimo 9  <br/>  Codice fiscale (ITIN, Stati Uniti) - conteggio minimo 1, conteggio massimo 9  <br/>  Numero di previdenza sociale (SSN, Stati Uniti) - conteggio minimo 1, conteggio massimo 9  <br/>  I contenuti vengono condivisi con:  <br/>  Persone esterne all'organizzazione  <br/> |Inviare una notifica  <br/> |
|GLBA Stati Uniti: analisi dei contenuti condivisi con l'esterno - conteggio elevato  <br/> | I contenuti includono informazioni riservate:  <br/>  Numero di carta di credito - conteggio minimo 10, conteggio massimo illimitato  <br/>  Numero di conto corrente (Stati Uniti) - conteggio minimo 10, conteggio massimo illimitato  <br/>  Codice fiscale (ITIN, Stati Uniti) - conteggio minimo 10, conteggio massimo illimitati  <br/>  Numero di previdenza sociale (SSN, Stati Uniti) - conteggio minimo 10, conteggio massimo illimitato  <br/>  I contenuti vengono condivisi con:  <br/>  Persone esterne all'organizzazione  <br/> | Bloccare l'accesso ai contenuti  <br/>  Inviare una notifica  <br/>  Consentire override  <br/>  Richiedere una motivazione aziendale  <br/>  Inviare rapporto operazioni non consentite  <br/> |
   
## <a name="us-health-insurance-act-hipaa"></a>U.S. Health Insurance Act (HIPAA)

|**Nome regola**|**Condizioni <br/> (inclusi i tipi di informazioni riservate)**|**Azioni**|
|:-----|:-----|:-----|
|Il contenuto corrispondente HIPAA negli Stati Uniti  <br/> | Contiene informazioni riservate seguenti:  <br/>  Usa numero di previdenza sociale (SSN), ovvero Min count 1, Max contare le  <br/>  Numero della Drug Enforcement Agency (DEA), ovvero Min count 1, Max contare le  <br/> **E** <br/>  Contenuto contiene una di queste condizioni:  <br/>  Classificazione delle malattie internazionale (ICD-9-CM), ovvero Min numero 1, Max contare le  <br/>  Classificazione delle malattie internazionale (ICD-10-CM), ovvero Min numero 1, Max contare le  <br/>  I contenuti vengono condivisi con:  <br/>  Persone esterne all'organizzazione  <br/> |Inviare una notifica  <br/> |
   
## <a name="us-patriot-act"></a>U.S. Patriot Act

|**Nome regola**|**Condizioni <br/> (inclusi i tipi di informazioni riservate)**|**Azioni**|
|:-----|:-----|:-----|
|U.S. Patriot Act: analisi dei contenuti condivisi con l'esterno - conteggio basso  <br/> | I contenuti includono informazioni riservate:  <br/>  Numero di carta di credito - conteggio minimo 1, conteggio massimo 9  <br/>  Numero di conto corrente (Stati Uniti) - conteggio minimo 1, conteggio massimo 9  <br/>  Codice fiscale (ITIN, Stati Uniti) - conteggio minimo 1, conteggio massimo 9  <br/>  Numero di previdenza sociale (SSN, Stati Uniti) - conteggio minimo 1, conteggio massimo 9  <br/>  I contenuti vengono condivisi con:  <br/>  Persone esterne all'organizzazione  <br/> |Inviare una notifica  <br/> |
|U.S. Patriot Act: analisi dei contenuti condivisi con l'esterno - conteggio elevato  <br/> | I contenuti includono informazioni riservate:  <br/>  Numero di carta di credito - conteggio minimo 10, conteggio massimo illimitato  <br/>  Numero di conto corrente (Stati Uniti) - conteggio minimo 10, conteggio massimo illimitato  <br/>  Codice fiscale (ITIN, Stati Uniti) - conteggio minimo 10, conteggio massimo illimitati  <br/>  Numero di previdenza sociale (SSN, Stati Uniti) - conteggio minimo 10, conteggio massimo illimitato  <br/>  I contenuti vengono condivisi con:  <br/>  Persone esterne all'organizzazione  <br/> | Bloccare l'accesso ai contenuti  <br/>  Inviare una notifica  <br/>  Consentire override  <br/>  Richiedere una motivazione aziendale  <br/>  Inviare rapporto operazioni non consentite  <br/> |
   
## <a name="us-personally-identifiable-information-pii-data"></a>Dati di identificazione personale (PII) Stati Uniti

|**Nome regola**|**Condizioni <br/> (inclusi i tipi di informazioni riservate)**|**Azioni**|
|:-----|:-----|:-----|
|Informazioni personali Stati Uniti: analisi dei contenuti condivisi con l'esterno - conteggio basso  <br/> | I contenuti includono informazioni riservate:  <br/>  Codice fiscale (ITIN, Stati Uniti) - conteggio minimo 1, conteggio massimo 9  <br/>  Numero di previdenza sociale (SSN, Stati Uniti) - conteggio minimo 1, conteggio massimo 9  <br/>  Numero di passaporto Regno Unito/Stati Uniti - conteggio minimo 1, conteggio massimo 9  <br/>  I contenuti vengono condivisi con:  <br/>  Persone esterne all'organizzazione  <br/> |Inviare una notifica  <br/> |
|Informazioni personali Stati Uniti: analisi dei contenuti condivisi con l'esterno - conteggio elevato  <br/> | I contenuti includono informazioni riservate:  <br/>  Codice fiscale (ITIN, Stati Uniti) - conteggio minimo 10, conteggio massimo illimitati  <br/>  Numero di previdenza sociale (SSN, Stati Uniti) - conteggio minimo 10, conteggio massimo illimitato  <br/>  Numero di passaporto Regno Unito/Stati Uniti - conteggio minimo 10, conteggio massimo illimitato  <br/>  I contenuti vengono condivisi con:  <br/>  Persone esterne all'organizzazione  <br/> | Bloccare l'accesso ai contenuti  <br/>  Inviare una notifica  <br/>  Consentire override  <br/>  Richiedere una motivazione aziendale  <br/>  Inviare rapporto operazioni non consentite  <br/> |
   
## <a name="us-state-breach-notification-laws"></a>U.S. State Breach Notification Laws

|**Nome regola**|**Condizioni <br/> (inclusi i tipi di informazioni riservate)**|**Azioni**|
|:-----|:-----|:-----|
|Leggi statali violazione Stati Uniti: analisi dei contenuti condivisi con l'esterno - conteggio basso  <br/> | I contenuti includono informazioni riservate:  <br/>  Numero di carta di credito - conteggio minimo 1, conteggio massimo 9  <br/>  Numero di conto corrente (Stati Uniti) - conteggio minimo 1, conteggio massimo 9  <br/>  Numero della patente statunitense - conteggio minimo 1, conteggio massimo 9  <br/>  Numero di previdenza sociale (SSN, Stati Uniti) - conteggio minimo 1, conteggio massimo 9  <br/>  I contenuti vengono condivisi con:  <br/>  Persone esterne all'organizzazione  <br/> |Inviare una notifica  <br/> |
|Leggi statali violazione Stati Uniti: analisi dei contenuti condivisi con l'esterno - conteggio elevato  <br/> | I contenuti includono informazioni riservate:  <br/>  Numero di carta di credito - conteggio minimo 10, conteggio massimo illimitato  <br/>  Numero di conto corrente (Stati Uniti) - conteggio minimo 10, conteggio massimo illimitato  <br/>  Numero della patente statunitense - conteggio minimo 10, conteggio massimo illimitato  <br/>  Numero di previdenza sociale (SSN, Stati Uniti) - conteggio minimo 10, conteggio massimo illimitato  <br/>  I contenuti vengono condivisi con:  <br/>  Persone esterne all'organizzazione  <br/> | Bloccare l'accesso ai contenuti  <br/>  Inviare una notifica  <br/>  Consentire override  <br/>  Richiedere una motivazione aziendale  <br/>  Inviare rapporto operazioni non consentite  <br/> |
   
## <a name="us-state-social-security-number-confidentiality-laws"></a>U.S. State Social Security Number Confidentiality Laws

|**Nome regola**|**Condizioni <br/> (inclusi i tipi di informazioni riservate)**|**Azioni**|
|:-----|:-----|:-----|
|Leggi statali SSN Stati Uniti: analisi dei contenuti condivisi con l'esterno - conteggio basso  <br/> | I contenuti includono informazioni riservate:  <br/>  Numero di previdenza sociale (SSN, Stati Uniti) - conteggio minimo 1, conteggio massimo 9  <br/>  I contenuti vengono condivisi con:  <br/>  Persone esterne all'organizzazione  <br/> |Inviare una notifica  <br/> |
|Leggi statali SSN Stati Uniti: analisi dei contenuti condivisi con l'esterno - conteggio elevato  <br/> | I contenuti includono informazioni riservate:  <br/>  Numero di previdenza sociale (SSN, Stati Uniti) - conteggio minimo 10, conteggio massimo illimitato  <br/>  I contenuti vengono condivisi con:  <br/>  Persone esterne all'organizzazione  <br/> | Bloccare l'accesso ai contenuti  <br/>  Inviare una notifica  <br/>  Consentire override  <br/>  Richiedere una motivazione aziendale  <br/>  Inviare rapporto operazioni non consentite  <br/> |
   

