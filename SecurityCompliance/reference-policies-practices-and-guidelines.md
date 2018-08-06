---
title: Criteri, procedure consigliate e linee guida di riferimento
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 12/9/2016
ms.audience: ITPro
ms.topic: reference
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
ms.assetid: ff3f140b-b005-445f-bfe0-7bc3f328aaf0
description: Microsoft ha sviluppato diversi criteri, procedure e adottato diverse procedure ottimali del settore per proteggere gli utenti di posta elettronica offensivo, non desiderato o dannoso.
ms.openlocfilehash: 436f564f20d579c56197563c7bfac3ef903be750
ms.sourcegitcommit: 22bca85c3c6d946083d3784f72e886c068d49f4a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/06/2018
ms.locfileid: "22026273"
---
# <a name="reference-policies-practices-and-guidelines"></a>Riferimento: I criteri, consigliate e linee guida
  
Microsoft si impegna a contribuire a garantire un'esperienza utente più attendibile sul web. Di conseguenza, Microsoft ha sviluppato diversi criteri, procedure e adottato diverse procedure ottimali del settore per proteggere gli utenti di posta elettronica offensivo, non desiderato o dannoso. Verificare i mittenti tenta di inviare posta elettronica agli utenti di Office 365 siano completamente comprendere e seguire le istruzioni contenute in questo articolo per facilitare questo sforzo e al fine di evitare possibili problemi di recapito.
  
Se non si conformità con questi criteri e le linee guida, potrebbe non essere possibile per il nostro team di supporto fornire assistenza. Se si vengano soddisfatti le linee guida, procedure consigliate e i criteri presentati in questo articolo sono ancora stati riscontrati problemi di recapito in base all'indirizzo IP di invio, seguire i passaggi necessari per inviare una richiesta delisting. Per ulteriori informazioni, vedere [utilizzare il portale delist per eliminare il proprio nome nell'elenco Mittenti bloccati di Office 365](use-the-delist-portal-to-remove-yourself-from-the-office-365-blocked-senders-lis.md).
  
## <a name="general-microsoft-policies"></a>Criteri di Microsoft generale
<a name="GenMsftPolicies"> </a>

Messaggio di posta elettronica inviato agli utenti di Office 365 deve rispettare tutti i criteri di Microsoft che regolano la trasmissione di posta elettronica e l'utilizzo di Office 365.
  
- Condizioni dei servizi applicabili a Office 365; in particolare, il divieto di utilizzo del servizio di posta indesiderata o distribuire malware
    
- [Accordo sui servizi di Microsoft](https://www.microsoft.com/servicesagreement/)
    
## <a name="governmental-regulations"></a>Regolamentazioni governative
<a name="GovtRegulations"> </a>

Messaggio di posta elettronica inviato agli utenti di Office 365 deve rispettare le leggi e normative governance di comunicazioni di posta elettronica negli uffici applicabile.
  
- [Posta indesiderata CAN Act: Una Guida di conformità per le aziende](https://www.ftc.gov/tips-advice/business-center/guidance/can-spam-act-compliance-guide-business)
    
- ["Rimuovere Me" risposte e le responsabilità: marketing di posta elettronica deve rispettare "Annullare la sottoscrizione" basata sulle attestazioni](https://www.lawpublish.com/ftc-emai-marketers-unsubscribe-claims.mdl)
    
## <a name="technical-guidelines"></a>Linee guida tecniche
<a name="TechGuidelines"> </a>

Messaggio di posta elettronica inviato a Office 365 deve rispettare i suggerimenti applicabili elencati la documentazione seguente (alcuni collegamenti sono disponibili solo in inglese).
  
- [RFC documento 2505: Protezione da posta indesiderata suggerimenti per agenti di trasferimento messaggi SMTP](https://www.ietf.org/rfc/rfc2505.txt)
    
- [RFC 2920: Estensione del servizio SMTP per il Pipelining comando](https://www.ietf.org/rfc/rfc2920.txt)
    
Inoltre, il server di posta elettronica la connessione a Office 365 deve rispettare i requisiti seguenti:
  
- Mittente dovrebbe rispettino tutti i requisiti tecnici per la trasmissione di messaggi di posta elettronica Internet, pubblicati del The Internet della società Internet Engineering Task Force (IETF), inclusi RFC 5321, RFC 5322 e altri utenti. 
    
- Dopo aver specificato un codice di risposta di errore SMTP numerico compreso tra 500 e 599 (noto anche come risposta di mancato recapito permanente o rapporto di mancato recapito), il mittente non deve tentare di ritrasmettere messaggio al destinatario.
    
- Dopo aver più risposte di mancato recapito, il mittente deve cesseranno ulteriormente tenta di inviare la posta elettronica al destinatario.
    
- I messaggi non devono essere trasmesse tramite posta elettronica non protetta inoltro o proxy server.
    
- Il meccanismo per annullare la sottoscrizione, da singoli elenchi o tutti gli elenchi ospitati dal mittente, deve essere chiaramente documentati e più semplice per i destinatari trovare e utilizzare.
    
- Connessioni dallo spazio IP dinamico potrebbero non essere accettate.
    
- Server di posta elettronica deve essere valido record DNS inverso.
    
## <a name="reputation-management"></a>Gestione di reputazione
<a name="RepManagement"> </a>

I mittenti, dell'ISP e altri provider di servizi deve gestire attivamente reputazione degli indirizzi IP in uscita.
  
## <a name="office-365-limits"></a>Limiti di Office 365
<a name="sectionSection4"> </a>

I mittenti devono essere conformi ai limiti di Office 365 elencati in [Exchange Online Protection Limits](https://technet.microsoft.com/library/exchange-online-protection-limits.aspx).
  
## <a name="email-delivery-resources-and-organizations"></a>Risorse di recapito di posta elettronica e le organizzazioni
<a name="sectionSection5"> </a>

Microsoft attivamente può essere utilizzato con il corpo di settore e provider di servizi per migliorare l'ecosistema internet e di posta elettronica. Le organizzazioni sono pubblicate documenti sulle procedure ottimali supportano che è consigliabile rispondono i mittenti. Consente di migliorare la possibilità di inviare posta elettronica tra più provider di servizi di posta elettronica in tutto il mondo.
  
- [Gruppo di lavoro parte di anti-un Malware Mobile messaggistica](https://www.m3aawg.org/)
    
- [Protezione online Alliance](https://www.otalliance.org/resources)
    
- [Mittenti di posta elettronica &amp; Coalition Provider](http://www.espcoalition.org/)
    
## <a name="abuse-and-spam-reporting"></a>Abusare e rapporti spam
<a name="AbuseSpamReports"> </a>

Per segnalare illecito, offensivo, non desiderato o dannoso posta elettronica, eseguire [Report junk e-mail e tentativi di phishing in Outlook sul web ](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md). Invio di tali tipi di comunicazioni costituisce una violazione del criterio di Microsoft e verrà eseguita l'azione appropriata nel report confermato.
  
## <a name="law-enforcement"></a>Applicazione della legge
<a name="sectionSection7"> </a>

Se si è un membro dell'applicazione della legge e si desidera utilizzare Microsoft Corporation con la persona documentazione relativa a Office 365, o se dubbi sulla documentazione legale inviate a Microsoft, chiamare (1) (425) 722-1299.
  

