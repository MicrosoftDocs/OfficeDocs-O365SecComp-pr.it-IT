---
title: Panoramica della sicurezza di dashboard
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 02/07/2019
ms.audience: ITPro
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: fe0b9b8f-faa9-44ff-8095-4d1b2f507b74
ms.collection: M365-security-compliance
description: Utilizzare il nuovo Dashboard di protezione di Office 365 Threat Protection stato revisione e visualizzare e gestire gli avvisi di protezione.
ms.openlocfilehash: 403c47ed09e9652a66abeafb93be02589c9b1702
ms.sourcegitcommit: efccf5b4f22d34a9674bc55ebf3d88bc8bda2972
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/14/2019
ms.locfileid: "29995127"
---
# <a name="security-dashboard"></a>Dashboard di sicurezza

## <a name="overview"></a>Panoramica

Il [protezione &amp; centro conformità](go-to-the-securitycompliance-center.md) consente all'organizzazione di gestire la protezione dei dati e conformità. Se che si dispone delle autorizzazioni necessarie, il Dashboard di protezione consente di controllare lo stato di protezione di rischio, nonché visualizzare e gestire gli avvisi di protezione. 
  
Guardare il video per una panoramica e leggere questo articolo per ulteriori informazioni.
  
> [!VIDEO https://www.microsoft.com/videoplayer/embed/3540b1f8-62d2-47fa-a07d-d7ad76f55b0f?autoplay=false]
  
In base alle quali include la sottoscrizione a Office 365 dell'organizzazione, il Dashboard di protezione include widget diverse, ad esempio Threat Management riepilogo, lo stato di protezione di rischio, globale rilevamenti rischio settimanale, Malware e ulteriori informazioni, come descritto nel Nelle sezioni seguenti.
  
Per visualizzare il Dashboard di protezione, nelle [protezione di Office 365 &amp; centro conformità](go-to-the-securitycompliance-center.md), andare alla **gestione delle minacce** \> **Dashboard**.
  
> [!NOTE]
> È necessario essere un amministratore globale di Office 365, un amministratore della sicurezza o un lettore di protezione per visualizzare il Dashboard di sicurezza. Alcuni widget richiedono autorizzazioni aggiuntive per la visualizzazione. Per ulteriori informazioni, vedere [autorizzazioni in Office 365 Security &amp; centro conformità](permissions-in-the-security-and-compliance-center.md). 
  
## <a name="threat-management-summary"></a>Threat Management riepilogo

Widget Threat Management riepilogo indica a colpo come l'organizzazione è stato protezione contro le minacce negli ultimi sette (7) giorni.

![Dashboard di sicurezza - widget Threat Management riepilogo](media/SecDash-ThreatMgmtSummary.png)

Le informazioni visualizzate nel riepilogo Threat Management dipendono cosa si sottoscrizione include. Nella tabella seguente vengono descritte le informazioni sono incluse per Office 365 Enterprise E3 e Office 365 Enterprise E5.


|Office 365 Enterprise E3  |Office 365 Enterprise E5  |
|---------|---------|
|Malware messaggi bloccati<br/>Bloccata i messaggi di phishing<br>Messaggi segnalati dagli utenti<br><br><br><br> |Malware messaggi bloccati<br>Bloccata i messaggi di phishing<br>Messaggi segnalati dagli utenti<br>Malware zero-day bloccato<br>Messaggi di phishing avanzate rilevati<br>URL dannosi bloccati |

Per visualizzare o accedere widget Threat Management riepilogo, è necessario disporre delle autorizzazioni per visualizzare i rapporti di protezione avanzata di rischio. Per ulteriori informazioni, vedere [le autorizzazioni necessarie per visualizzare i report degli strumenti di analisi?](view-reports-for-atp.md#what-permissions-are-needed-to-view-the-atp-reports). 

## <a name="threat-protection-status"></a>Stato di protezione di rischio

Widget Threat Protection stato Mostra efficacia protezione rischio con una visualizzazione delle tendenze e dettagliata per attività di phishing e malware. 

![Widget lo stato di protezione rischio](media/tpswidget.png)

I dettagli dipendono dal fatto la sottoscrizione di Office 365 include [Exchange Online Protection](eop/exchange-online-protection-eop.md) (EOP) con o senza [Protezione rischio avanzate di Office 365](office-365-atp.md) (degli strumenti di analisi).


|Se la sottoscrizione include... |Verrà visualizzato queste informazioni |
|---------|---------|
|EOP, ma non degli strumenti di analisi Office 365     |Posta elettronica dannoso che è stato rilevato e bloccato da EOP<br> Vedere [relazione sullo stato di protezione di rischio (EOP)](view-email-security-reports.md#threat-protection-status-report).| |
|Degli strumenti di analisi di Office 365 |Dannoso contenuto dannoso posta elettronica e rilevato e bloccato da EOP e degli strumenti di analisi di Office 365<br>Aggregati conteggio dei messaggi di posta elettronica univoco dannosa bloccati per il motore antimalware, [di eliminazione automatica zero ore](zero-hour-auto-purge.md)e caratteristiche degli strumenti di analisi (inclusi i [Collegamenti sicuro](atp-safe-links.md), [Gli allegati sicuri](atp-safe-attachments.md)e [degli strumenti di analisi anti-phishing](atp-anti-phishing.md)).<br>Vedere [relazione sullo stato di protezione di rischio (degli strumenti di analisi)](view-reports-for-atp.md#threat-protection-status-report). | 

Per visualizzare o accedere widget rischio lo stato di protezione, è necessario disporre delle autorizzazioni per visualizzare i rapporti di protezione avanzata di rischio. Per ulteriori informazioni, vedere [le autorizzazioni necessarie per visualizzare i report degli strumenti di analisi?](view-reports-for-atp.md#what-permissions-are-needed-to-view-the-atp-reports). 

## <a name="global-weekly-threat-detections"></a>Rilevamenti di rischio settimanale globale
 
Widget globale rilevamenti rischio settimanale Mostra le minacce quanti rilevate nei messaggi di posta elettronica negli ultimi sette (7) giorni.

![Widget settimanale rilevamenti di rischio globale](media/globalweeklythreatdetections.png)

Le metriche vengono calcolate come descritto nella tabella riportata di seguito:

|Metrica  |La modalità di calcolo  |
|---------|---------|
|Messaggi analizzati |Numero di messaggi di posta elettronica analizzati moltiplicato per il numero di destinatari |
|Minacce arrestate  |Numero di messaggi di posta elettronica identificato come contenente malware moltiplicato per il numero di destinatari |
|Bloccato da [Strumenti di analisi](office-365-atp.md) |Numero di messaggi di posta elettronica bloccato da strumenti di analisi moltiplicato per il numero di destinatari |
|Rimosse dopo il recapito |Numero di messaggi rimossi da [eliminare automaticamente zero ore](zero-hour-auto-purge.md) moltiplicato per il numero di destinatari |

## <a name="malware"></a>Malware

Malware widget Mostra informazioni dettagliate sulle tendenze di malware e tipi di sistemi operativi della famiglia di malware negli ultimi sette (7) giorni.

![Malware tendenze e tipi di sistemi operativi della famiglia](media/malwarewidgetatpe5.png)
 
## <a name="insights"></a>Approfondimenti

Informativa non solo identificare problemi principali, che è consigliabile consultare, nonché suggerimenti e le azioni da prendere in considerazione. 

![Approfondimenti smart](media/smartinsights.png)

Ad esempio, si potrebbe visualizzare che phishing messaggi di posta elettronica vengono recapitati in quanto alcuni utenti sono disabilitate le relative opzioni posta indesiderata. Per ulteriori informazioni sul funzionamento delle informazioni, vedere [report e sui concetti di Office 365 Security &amp; centro conformità](reports-and-insights-in-security-and-compliance.md).
  
## <a name="threat-intelligence"></a>Business intelligence di rischio

Se la sottoscrizione dell'organizzazione include [funzionalità di Business Intelligence di rischio](office-365-ti.md), il Dashboard di sicurezza ha una sezione di **Business Intelligence di rischio** che include strumenti avanzati. Team di protezione dell'organizzazione possono utilizzare le informazioni di questa sezione per acquisire familiarità con campagne emergenti, analizzare le minacce e gestire risolte. 
  
![Business intelligence di rischio consente di comprendere gli attacchi di tipo destinate a nell'organizzazione](media/threatintelwidget.png)
  
  
## <a name="trends"></a>Tendenze

Nella parte inferiore della Dashboard di protezione è una sezione **tendenze** , che vengono riepilogate le tendenze del flusso di posta elettronica per l'organizzazione. Report vengono fornite informazioni sulla posta elettronica classificata come posta indesiderata, malware, tentativi di phishing e posta elettronica valido. Fare clic su una tessera per visualizzare informazioni più dettagliate nel report. 
  
![La sezione tendenze vengono riepilogate le tendenze del flusso di posta elettronica per l'organizzazione](media/trends.png)
  
E, se la sottoscrizione dell'organizzazione Office 365 include [funzionalità di Business Intelligence di rischio](office-365-ti.md), è inoltre necessario un report **gli avvisi di recente threat management** in questa sezione che consente il team di protezione consente di eseguire l'azione necessaria avviso di priorità alta sicurezza. 

Per visualizzare o accedere widget inviati e ricevuti posta elettronica, è necessario disporre delle autorizzazioni per visualizzare i rapporti di protezione avanzata di rischio. Per ulteriori informazioni, vedere [le autorizzazioni necessarie per visualizzare i report degli strumenti di analisi?](view-reports-for-atp.md#what-permissions-are-needed-to-view-the-atp-reports). 

Per visualizzare o accedere widget recenti Threat Management avvisi, è necessario disporre delle autorizzazioni per visualizzare gli avvisi. Per ulteriori informazioni, vedere [RBAC autorizzazioni necessarie per visualizzare gli avvisi](alert-policies.md#rbac-permissions-required-to-view-alerts).
  
## <a name="related-topics"></a>Argomenti correlati

[Visualizzare i report di protezione posta elettronica in sicurezza &amp; centro conformità](view-email-security-reports.md)
  
[Visualizzare i report per la protezione rischio avanzate di Office 365](view-reports-for-atp.md)
  
[Office 365 Advanced Threat Protection](office-365-atp.md)
  
[Office 365 Threat Intelligence](office-365-ti.md)
  

