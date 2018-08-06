---
title: Creazione di rapporti e traccia dei messaggi in Exchange Online Protection
ms.author: chrisda
author: chrisda
manager: serdars
ms.date: 12/18/2017
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
ms.assetid: f40253f2-50a1-426e-9979-be74ba74cb61
description: Microsoft (EOP) Exchange Online Protection offre diversi rapporti che consentono di determinare lo stato generale e l'integrità dell'organizzazione. Sono inoltre disponibili strumenti per la risoluzione dei problemi relativi a eventi specifici, ad esempio il mancato recapito di un messaggio ai destinatari desiderati, e report di controllo per assicurare il rispetto dei requisiti di conformità. Nella tabella seguente vengono descritti i report e gli strumenti per la risoluzione dei problemi disponibili per gli amministratori di EOP.
ms.openlocfilehash: 01a09b2b4b72161352af3793686c6cc888e44e29
ms.sourcegitcommit: 22bca85c3c6d946083d3784f72e886c068d49f4a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/06/2018
ms.locfileid: "22027143"
---
# <a name="reporting-and-message-trace-in-exchange-online-protection"></a>Creazione di rapporti e traccia dei messaggi in Exchange Online Protection

Microsoft Exchange Online Protection (EOP) sono disponibili numerose diversi report che consentono di determinare lo stato generale e l'integrità dell'organizzazione. Sono inoltre disponibili strumenti che consentono di risoluzione dei problemi relativi ad eventi specifici (ad esempio un messaggio in arrivo non per il destinatario) e rapporti di controllo per semplificare lo con i requisiti di conformità. 

## <a name="usage-reports"></a>Report sull'uso

**Attività di Gruppi di Office 365** Consente di visualizzare informazioni sul numero di Gruppi di Office 365 creati e utilizzati.  

**Attività di posta elettronica** Consente di visualizzare informazioni sul numero di messaggi inviati, ricevuti e letti nell'intera organizzazione e per utenti specifici.  

**Utilizzo di app di posta elettronica** Consente di visualizzare informazioni sulle app di posta elettronica utilizzati. Ciò include il numero totale di connessioni delle applicazioni e le versioni di Outlook che si connettono.  

**Utilizzo delle cassette postali** Consente di visualizzare informazioni sull'archiviazione usata, sul consumo di quota, sul numero di elementi e sull'ultima attività (invio o lettura) per le cassette postali.

Vedere le risorse seguenti per ulteriori informazioni:

- [Rapporti di Office 365 nell'interfaccia di amministrazione - gruppi di Office 365](https://go.microsoft.com/fwlink/p/?linkid=861610) 
- [Report di Office 365 nell'interfaccia di amministrazione - Attività di posta elettronica](https://go.microsoft.com/fwlink/p/?linkid=859706) 
- [Report di Office 365 nell'interfaccia di amministrazione - Utilizzo delle applicazioni di posta elettronica](https://go.microsoft.com/fwlink/p/?linkid=859707)
- [Report di Office 365 nell'interfaccia di amministrazione - Utilizzo delle cassette postali](https://go.microsoft.com/fwlink/p/?linkid=859708)

## <a name="security-amp-compliance-reports-in-the-office-365-admin-center"></a>Protezione &amp; conformità rapporti nell'interfaccia di amministrazione di Office 365

Questi rapporti avanzati offrono un'esperienza di creazione di rapporti interattiva per gli amministratori EOP, che include informazioni di riepilogo e la possibilità di eseguire il drill-down per ulteriori informazioni.  

**Protezione avanzata dalle minacce (ATP, Advanced Threat Protection)** Consente di visualizzare informazioni sui collegamenti sicuri e sugli allegati sicuri che fanno parte di ATP.  

**EOP** Visualizzare informazioni sui rilevamenti di malware, posta spoofing, i rilevamenti di posta indesiderata e flusso di posta da e verso l'organizzazione.  

[Visualizzare i report per la protezione di rischio avanzate ed Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkid=852409) 

##<a name="custom-reports-using-microsoft-graph"></a>Rapporti personalizzati tramite Microsoft Graph

Creare a livello di programmazione report in cui sono disponibili nell'interfaccia di amministrazione di Office 365 utilizzando Microsoft Graph, vedere gli argomenti di [utilizzo dei report di utilizzo di Office 365 in Microsoft Graph](https://go.microsoft.com/fwlink/p/?linkid=865135) 

##<a name="custom-reports-using-reporting-web-services"></a>Rapporti personalizzati tramite servizi Web Reporting

Creare a livello di programmazione report da disponibili Exchange Online Protection PowerShell cmdlet di segnalazione tramite REST/ODATA2 filtro di query.

Vedere [Web di Office 365 Reporting Services](https://go.microsoft.com/fwlink/p/?LinkId=279926) 

##<a name="message-trace"></a>Traccia dei messaggi

Segue della posta elettronica messaggi quando passano attraverso EOP. È possibile determinare se un messaggio di posta elettronica è stato ricevuto, rifiutato, rinviato o distribuito tramite il servizio. Viene inoltre le azioni eseguite nel messaggio prima che raggiunto il relativo stato finale.  

È possibile utilizzare queste informazioni per rispondere in modo efficiente alle domande dell'utente, risolvere i problemi relativi al flusso di posta, convalidare le modifiche apportate ai criteri e ridurre la necessità di contattare il supporto tecnico per assistenza.  

Vedere [traccia di un messaggio di posta elettronica](http://technet.microsoft.com/library/0c83cde6-5b09-4106-8587-c200cdc59094.aspx) 

## <a name="audit-logging"></a>Registrazione di controllo

Tiene traccia delle specifiche delle modifiche apportate dagli amministratori dell'organizzazione. Questi rapporti consentono di risolvere i problemi di configurazione o trovare la causa di problemi relativi alla conformità o sicurezza.  vedere [rapporti di controllo in EOP](auditing-reports-in-eop.md) 


## <a name="reporting-and-message-trace-data-availability-and-latency"></a>Rapporti e latenza e disponibilità dei dati dei messaggi

La tabella seguente descrive quando in EOP le funzionalità di creazione rapporti e dati di traccia dei messaggi sono disponibili e per quanto tempo.
  
||||
|:-----|:-----|:-----|
|**Tipo di rapporto** <br/> |**Dati disponibili per (periodo passato)** <br/> |**Latenza** <br/> |
|Rapporti di riepilogo di protezione della posta  <br/> |90 giorni  <br/> |L'aggregazione dei dati dei messaggi è quasi completa entro 24-48 ore. Alcune modifiche aggregate incrementali minori possono verificarsi in un periodo massimo di 5 giorni.  <br/> |
|Rapporti dettagliati di protezione della posta  <br/> |90 giorni  <br/> |Per dati dettagliati creati da meno di 7 giorni, i dati devono essere visualizzati entro 24 ore ma potrebbero non essere completi fino a 48 ore. Alcune modifiche incrementali minori possono verificarsi in un periodo massimo di 5 giorni.  <br/> Per visualizzare rapporti dettagliati per messaggi creati da più di 7 giorni, i risultati potrebbero richiedere alcune ore.  <br/> |
|Dati di traccia dei messaggi  <br/> |90 giorni  <br/> |Quando si esegue la traccia dei messaggi per i messaggi creati da meno di 7 giorni, i messaggi devono essere visualizzati entro un periodo compreso tra 5 e 30 minuti.  <br/> Quando si esegua la traccia dei messaggi per messaggi creati da più di 7 giorni, i risultati potrebbero richiedere alcune ore.  <br/> |
   
> [!NOTE]
> La latenza e la disponibilità dei dati è la stessa a prescindere che la richiesta venga effettuata tramite interfaccia di amministrazione di Office 365 o PowerShell remota. 
  

