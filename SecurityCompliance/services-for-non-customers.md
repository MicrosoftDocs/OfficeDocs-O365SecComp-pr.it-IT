---
title: Servizi per i non clienti che inviano la posta a Office 365
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.date: 5/2/2016
audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 19fd3e0f-8dbf-4049-a810-2c8ee6cefd48
ms.collection:
- M365-security-compliance
description: Per mantenere la fiducia degli utenti nell'utilizzo della posta elettronica, Microsoft ha messo a punto vari criteri e tecnologie che consentono di proteggere gli utenti.
ms.openlocfilehash: 836beea966e4c944876d418fa88e8c4f6baaf770
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/17/2019
ms.locfileid: "34156638"
---
# <a name="services-for-non-customers-sending-mail-to-office-365"></a>Servizi per i non clienti che inviano la posta a Office 365
  
Abuso di posta elettronica, posta indesiderata e messaggi di posta elettronica fraudolenti (phishing) continuano a gravare sull'intero sistema di posta elettronica. Per mantenere la fiducia degli utenti nell'utilizzo della posta elettronica, Microsoft ha messo a punto vari criteri e tecnologie che consentono di proteggere gli utenti. Tuttavia, Microsoft capisce che la posta elettronica legittima non dovrebbe essere influenzata negativamente. Pertanto, è stata configurata una serie di servizi per consentire ai mittenti di migliorare la possibilità di inviare messaggi di posta elettronica agli utenti di Office 365 per gestire in modo proattivo la propria reputazione di invio.
  
In questa panoramica vengono fornite informazioni sui vantaggi forniti all'organizzazione anche se non si è un cliente di Office 365.
  
## <a name="sender-solutions"></a>Soluzioni del mittente
<a name="sectionSection0"> </a>

|**Servizio**|**Vantaggi**|
|:-----|:-----|
|Contenuto della Guida in linea  <br/> | Fornisce  <br/>  Punto di partenza per qualsiasi problema relativo alla distribuzione di comunicazioni agli utenti di EOP  <br/>  Include una semplice guida online con i criteri e i requisiti necessari  <br/>  Una panoramica dei filtri per la posta indesiderata e delle tecnologie di autenticazione impiegate da Microsoft  <br/> |
|[Supporto tecnico Microsoft](services-for-non-customers.md#AboutSupport) <br/> |Fornisce supporto per l'escalation e la self-service per i problemi di recapito.  <br/> |
|[Portale di delist IP di protezione da posta indesiderata di Office 365](services-for-non-customers.md#DelistPortal) <br/> |Strumento per inviare la richiesta di esclusione di indirizzi IP. Prima di inoltrare la richiesta, è responsabilità del mittente garantire che qualsiasi ulteriore messaggio di posta proveniente dall'IP in questione non sia abusivo o dannoso.  <br/> |
|[Segnalazione di abusi e posta indesiderata per posta indesiderata proveniente da Exchange Online](services-for-non-customers.md#ReportOurJunk) <br/> |Consente di mantenere la posta indesiderata e gli altri messaggi non voluti inviati da Exchange Online e ingombrare Internet e il sistema di posta elettronica.  <br/> |
   
## <a name="microsoft-support"></a>Supporto tecnico Microsoft
<a name="AboutSupport"> </a>

Microsoft offre diverse opzioni di supporto per gli utenti che hanno problemi nell'invio di posta elettronica a Office 365 Inbox. È consigliabile:
  
- Seguire le istruzioni riportate in qualsiasi rapporto di mancato recapito ricevuto.
    
- Consultare i problemi più comuni riscontrati dai non clienti nella [risoluzione dei problemi relativi alla posta inviata a Office 365](troubleshooting-mail-sent-to-office-365.md).
    
- Utilizzare il portale di rimozione della [lista di Office 365](https://sender.office.com) per inviare una richiesta affinché l'IP sia stato rimosso dall'elenco dei mittenti bloccati. 
    
- Leggere i [Forum della community Microsoft](https://community.office365.com/en-us/f/).
    
- Contattare il cliente di Office 365 che si sta tentando di inviare tramite posta elettronica utilizzando un altro metodo e chiedergli di contattare il supporto tecnico Microsoft e di aprire un ticket di supporto per conto dell'utente. In alcuni casi, per motivi legali, il supporto tecnico Microsoft deve comunicare direttamente con il mittente che possiede lo spazio IP che viene bloccato. Tuttavia, i non clienti in genere non sono in grado di aprire ticket di supporto.
    
     Per ulteriori informazioni sul supporto tecnico Microsoft per Office 365, vedere [support](https://technet.microsoft.com/library/office-365-support.aspx).
    
## <a name="office-365-anti-spam-ip-delist-portal"></a>Portale di delist IP di protezione da posta indesiderata di Office 365
<a name="DelistPortal"> </a>

Si tratta di un portale self-service che è possibile utilizzare per rimuovere se stessi dall'elenco dei mittenti bloccati di Office 365. Utilizzare questo portale se si riceve un messaggio di errore quando si tenta di inviare una posta elettronica a un destinatario il cui indirizzo di posta elettronica è in Office 365 e non si ritiene di dover essere. Per altre informazioni, vedere [Usare il portale per l'esclusione di indirizzi IP dal filtro della posta indesiderata per rimuoversi dall'elenco di mittenti bloccati di Office 365](use-the-delist-portal-to-remove-yourself-from-the-office-365-blocked-senders-lis.md).
  
## <a name="abuse-and-spam-reporting-for-junk-email-originating-from-exchange-online"></a>Segnalazione di abusi e posta indesiderata per posta indesiderata proveniente da Exchange Online
<a name="ReportOurJunk"> </a>

A volte Office 365 viene utilizzato da terze parti per inviare messaggi di posta indesiderata, in violazione dei termini di utilizzo e criteri. Se si riceve un messaggio di posta indesiderata da Office 365, è possibile segnalarlo a [Junk@office365.microsoft.com](mailto:junk@office365.microsoft.com). Allegare i messaggi offensivi, inclusa l'intestazione del messaggio completo, nel formato RFC 5322 o ARF. Gli utenti di Outlook sul Web possono utilizzare gli strumenti incorporati per segnalare la posta indesiderata. Per informazioni, vedere [segnalare la posta indesiderata e i tentativi di phishing in Outlook sul Web ](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md).
  

