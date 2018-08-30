---
title: Visualizzare i report per la protezione rischio avanzate di Office 365
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 08/06/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: e47e838c-d99e-4c0b-b9aa-e66c4fae902f
description: Informazioni su come trovare e utilizzare rapporti per Office 365 avanzate protezione da minacce per la protezione &amp; centro conformità.
ms.openlocfilehash: bd02989711629cc67f7a7d5e061862a1146ff21b
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/27/2018
ms.locfileid: "22530632"
---
# <a name="view-reports-for-office-365-advanced-threat-protection"></a>Visualizzare i report per la protezione rischio avanzate di Office 365

Se l'organizzazione dispone di [Protezione di Office 365 avanzate rischio](office-365-atp.md) (degli strumenti di analisi) e si dispone delle autorizzazioni necessarie, è possibile utilizzare diversi report degli strumenti di analisi della protezione &amp; centro conformità. (Accedere ai **rapporti** \> **Dashboard**.)
  
![La sicurezza &amp; dashboard centro conformità risulta utile per determinare dove funzioni avanzate Threat Protection](media/6b213d34-adbb-44af-8549-be9a7e2db087.png)
  
I report degli strumenti di analisi includono [relazione sullo stato di protezione rischio](view-reports-for-atp.md#advancedthreats), il [rapporto di tipi di File degli strumenti di analisi](view-reports-for-atp.md#atpfiletypes)e il [rapporto di disposizione degli strumenti di analisi del messaggio](view-reports-for-atp.md#atpmessagedisp). In questo articolo vengono descritti i report degli strumenti di analisi e include collegamenti a [ulteriori report da visualizzare](view-reports-for-atp.md#addl).
  
## <a name="threat-protection-status-report"></a>Relazione sullo stato di protezione rischio

La relazione **sullo stato di protezione di rischio** è una singola visualizzazione che combina informazioni dannoso contenuto dannoso posta elettronica e rilevato e bloccato da Exchange Online e protezione da minacce avanzate. Il rapporto fornisce un conteggio aggregato univoco dei messaggi di posta con contenuto dannoso (file o URL) bloccato il motore antimalware, [(ZAP) di eliminazione automatica zero ore](zero-hour-auto-purge.md)e caratteristiche di protezione da minacce avanzate, ad esempio [Collegamenti sicuro degli strumenti di analisi](atp-safe-links.md), [degli strumenti di analisi Gli allegati sicuri](atp-safe-attachments.md)e le [funzionalità di protezione anti-phishing degli strumenti di analisi in Office 365](atp-anti-phishing.md).
  
Per visualizzare il report di stato protezione rischio, in sicurezza &amp; centro conformità, passare a **report** \> **Dashboard** \> **lo stato di protezione di rischio**.
  
![Relazione sullo stato di protezione rischio degli strumenti di analisi](media/6bdd41eb-62e0-423b-9fd4-d1d5baf0cbd5.png)
  
Per ottenere informazioni dettagliate sullo stato di un giorno, al passaggio del mouse sopra il grafico.
  
![Dati relativi allo stato di protezione rischio degli strumenti di analisi di un giorno](media/d5c2c6ad-c002-4985-a032-c866e46fdea8.png)
  
Per impostazione predefinita, il rapporto di stato protezione rischio Mostra dati per gli ultimi sette giorni. Tuttavia, è possibile scegliere di **filtri** e modificare l'intervallo di date per visualizzare i dati per un massimo di 90 giorni. 
  
![Filtri di stato di protezione di rischio degli strumenti di analisi](media/4f703369-642b-402b-9758-b9c828283410.png)
  
È inoltre possibile utilizzare il menu di **visualizzare i dati da** per modificare le informazioni visualizzate nel report. 
  
![Opzioni di visualizzazione per la relazione sullo stato di protezione rischio degli strumenti di analisi](media/4959bf8c-d192-4542-b00b-184e101e7513.png)
  
## <a name="atp-file-types-report"></a>Report di tipi di File degli strumenti di analisi

Nel rapporto di **Tipi di File degli strumenti di analisi** viene visualizzato il tipo di file rilevato come dannoso per [Gli allegati sicuri degli strumenti di analisi](atp-safe-attachments.md).
  
Per visualizzare il report nella protezione &amp; centro conformità, passare a **report** \> **Dashboard** \> **Tipi di File degli strumenti di analisi**.
  
![Report di tipi di File degli strumenti di analisi](media/6e3f5d33-79aa-4b2d-938c-6ef135d9e54c.png)
  
Quando si sposta su un giorno particolare, è possibile visualizzare la suddivisione dei tipi di file dannosi rilevati per [Gli allegati sicuri degli strumenti di analisi](atp-safe-attachments.md) e [anti-spam &amp; protezione anti-malware in Office 365](anti-spam-and-anti-malware-protection.md).
  
![Dati del report di tipi di File degli strumenti di analisi di un giorno](media/10d18428-699a-41d2-a73e-be3a8214ada1.png)
  
## <a name="atp-message-disposition-report"></a>Report di disposizione degli strumenti di analisi del messaggio

Il rapporto di **Disposizione degli strumenti di analisi del messaggio** Mostra le azioni eseguite per i messaggi di posta elettronica che sono stati rilevati con contenuto dannoso. 
  
Per visualizzare il report nella protezione &amp; centro conformità, passare a **report** \> **Dashboard** \> **Disposizione degli strumenti di analisi del messaggio**.
  
![Rapporto di eliminazione degli strumenti di analisi messaggi](media/b0ff65c4-53d3-496d-bafa-8937a5eb69e5.png)
  
Quando passa il mouse su una barra nel grafico, è possibile visualizzare le azioni eseguite per la posta elettronica rilevato per quel giorno.
  
![Dati del Report di eliminazione degli strumenti di analisi messaggio per un giorno](media/68d2beb8-4b30-48c4-8ba6-5e8ab88ae456.png)
  
## <a name="additional-reports-to-view"></a>Altri report per visualizzare

Oltre ai rapporti degli strumenti di analisi descritti in questo articolo, sono disponibili nel titolo [rapporti sulla protezione posta elettronica](view-email-security-reports.md) &amp; centro conformità. Rapporti sulla protezione posta elettronica includono un [rapporto di destinatari e mittenti principali](view-email-security-reports.md#top-senders-and-recipients-report), un [rapporto di spoofing posta](view-email-security-reports.md#spoof-mail-report), un [rapporto sui rilevamenti di posta indesiderata](view-email-security-reports.md#spam-detections-report)e altro ancora.
  
E, se l'organizzazione dispone di [Business Intelligence di rischio di Office 365](office-365-ti.md), è anche possibile [utilizzare Esplora nella protezione &amp; centro conformità](use-explorer-in-security-and-compliance.md).
  
## <a name="what-permissions-are-needed-to-view-these-reports"></a>Autorizzazioni necessarie per visualizzare questi rapporti?

Per visualizzare e utilizzare i rapporti di protezione posta elettronica descritti in questo articolo, è necessario disporre di un ruolo appropriato assegnato nella protezione &amp; centro conformità e nell'interfaccia di amministrazione di Exchange.
  
|**Gruppo di ruoli**|**Dove assegnato**|**Altre informazioni**|
|:-----|:-----|:-----|
| Uno dei seguenti:  <br/>  Gestione organizzazione  <br/>  Amministratore della sicurezza  <br/>  Lettore di sicurezza  <br/> |Protezione &amp; centro conformità  <br/> |[Le autorizzazioni di sicurezza di Office 365 &amp; centro conformità](permissions-in-the-security-and-compliance-center.md) <br/> |
| Uno dei seguenti:  <br/>  Gestione organizzazione  <br/>  Gestione organizzazione sola visualizzazione  <br/>  Ruolo destinatari di sola visualizzazione  <br/>  Gestione della conformità  <br/> |Centro amministrativo di Exchange  <br/> |[Autorizzazioni funzionalità in Exchange Online](https://technet.microsoft.com/library/jj200673%28v=exchg.150%29.aspx) <br/> |
   
## <a name="what-if-the-reports-arent-showing-data"></a>Se il report non vengono visualizzate dati?

Se non si possono visualizzare dati nei report, verificare che i criteri siano configurati correttamente. L'organizzazione deve disporre [degli strumenti di analisi collegamenti sicuro politiche](set-up-atp-safe-links-policies.md) e [gli allegati sicuri degli strumenti di analisi criteri](set-up-atp-safe-attachments-policies.md) definiti nell'ordine indicato per la protezione degli strumenti di analisi in locale. Vedere anche [protezione antispam e antimalware in Office 365](anti-spam-and-anti-malware-protection.md).
  
## <a name="related-topics"></a>Argomenti correlati

[Report e sui concetti di Office 365 Security &amp; centro conformità](reports-and-insights-in-security-and-compliance.md)
  
[Creare una pianificazione per un report nella protezione &amp; centro conformità](create-a-schedule-for-a-report.md)
  
[Impostare e scaricare un report personalizzato per la protezione &amp; centro conformità](set-up-and-download-a-custom-report.md)
  

