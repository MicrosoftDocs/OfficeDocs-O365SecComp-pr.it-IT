---
title: Visualizzare i report per la protezione rischio avanzate di Office 365
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 01/07/2019
ms.audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: e47e838c-d99e-4c0b-b9aa-e66c4fae902f
description: Informazioni su come trovare e utilizzare rapporti per Office 365 avanzate protezione da minacce per la protezione &amp; centro conformità.
ms.openlocfilehash: d387e020e5834d4961e7bda50b418ea11b9f0f4d
ms.sourcegitcommit: 30faa3ba91cab4c36e3d8d8ed5858d5269ea8a56
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/08/2019
ms.locfileid: "27749350"
---
# <a name="view-reports-for-office-365-advanced-threat-protection"></a>Visualizzare i report per la protezione rischio avanzate di Office 365

Se l'organizzazione dispone di [Protezione di Office 365 avanzate rischio](office-365-atp.md) (degli strumenti di analisi) e si dispone delle [autorizzazioni necessarie](#what-permissions-are-needed-to-view-these-reports), è possibile utilizzare diversi report degli strumenti di analisi della protezione &amp; centro conformità. (Accedere ai **rapporti** \> **Dashboard**.)
  
![La sicurezza &amp; dashboard centro conformità risulta utile per determinare dove funzioni avanzate Threat Protection](media/6b213d34-adbb-44af-8549-be9a7e2db087.png)
  
I report degli strumenti di analisi includono [relazione sullo stato di protezione di rischio](#threat-protection-status-report), il [rapporto di tipi di File degli strumenti di analisi](#atp-file-types-report)e il [report di disposizione degli strumenti di analisi del messaggio](#atp-message-disposition-report). In questo articolo vengono descritti i report degli strumenti di analisi e include collegamenti a [ulteriori report da visualizzare](#additional-reports-to-view).
  
## <a name="threat-protection-status-report"></a>Relazione sullo stato di protezione di rischio

La relazione **Sullo stato di protezione di rischio** è una singola visualizzazione che combina informazioni dannoso contenuto dannoso posta elettronica e rilevato e bloccato da [Exchange Online Protection](eop/exchange-online-protection-overview.md) (EOP) e [Degli strumenti di analisi di Office 365](office-365-atp.md). Il rapporto fornisce un conteggio aggregato univoco dei messaggi di posta con contenuto dannoso (file o indirizzi di siti Web (URL)) bloccato il motore antimalware, [(ZAP) di eliminazione automatica zero ore](zero-hour-auto-purge.md)e caratteristiche degli strumenti di analisi, ad esempio [Collegamenti sicuro degli strumenti di analisi](atp-safe-links.md), [Safe degli strumenti di analisi Allegati](atp-safe-attachments.md)e le [funzionalità di protezione anti-phishing degli strumenti di analisi](atp-anti-phishing.md).

> [!NOTE]
> Una relazione sullo stato di protezione di rischio è disponibile per i clienti che dispongono di [Strumenti di analisi di Office 365](office-365-atp.md) o [Exchange Online Protection](eop/exchange-online-protection-eop.md) (EOP); Tuttavia, le informazioni visualizzate nel rapporto di stato di protezione di rischio per i clienti degli strumenti di analisi probabile che conterrà dati diversi rispetto a ciò che potrebbe essere visualizzato EOP customers. Ad esempio, la relazione sullo stato di protezione di rischio per i clienti degli strumenti di analisi conterrà informazioni sui [file dannosi rilevato in SharePoint Online, OneDrive o team di Microsoft](atp-for-spo-odb-and-teams.md). Tali informazioni sono specifiche di strumenti di analisi, in modo che i clienti che dispongono di EOP, ma non degli strumenti di analisi non visualizzerà i dettagli nel loro relazione sullo stato di protezione di rischio.
  
Per visualizzare il report di stato di protezione di rischio, nelle [protezione &amp; centro conformità](https://security.microsoft.com), andare al **report** \> **Dashboard** \> **Lo stato di protezione di rischio**.
  
![Relazione sullo stato di protezione rischio degli strumenti di analisi](media/6bdd41eb-62e0-423b-9fd4-d1d5baf0cbd5.png)
  
Per ottenere informazioni dettagliate sullo stato di un giorno, al passaggio del mouse sopra il grafico.
  
![Dati relativi allo stato di protezione rischio degli strumenti di analisi di un giorno](media/d5c2c6ad-c002-4985-a032-c866e46fdea8.png)
  
Per impostazione predefinita, il rapporto di stato di protezione di rischio Mostra dati per gli ultimi sette giorni. Tuttavia, è possibile scegliere di **filtri** e modificare l'intervallo di date per visualizzare i dati per un massimo di 90 giorni. 
  
![Filtri di stato di protezione di rischio degli strumenti di analisi](media/4f703369-642b-402b-9758-b9c828283410.png)
  
È inoltre possibile utilizzare il menu di **visualizzare i dati da** per modificare le informazioni visualizzate nel report. 
  
![Opzioni di visualizzazione per la relazione sullo stato di protezione rischio degli strumenti di analisi](media/4959bf8c-d192-4542-b00b-184e101e7513.png)
  
## <a name="atp-file-types-report"></a>Report di tipi di File degli strumenti di analisi

Nel rapporto di **Tipi di File degli strumenti di analisi** viene visualizzato il tipo di file rilevato come dannoso per [Gli allegati sicuri degli strumenti di analisi](atp-safe-attachments.md).
  
Per visualizzare il report nel [protezione &amp; centro conformità](https://security.microsoft.com), andare al **report** \> **Dashboard** \> **Tipi di File degli strumenti di analisi**.
  
![Report di tipi di File degli strumenti di analisi](media/6e3f5d33-79aa-4b2d-938c-6ef135d9e54c.png)
  
Quando si sposta su un giorno particolare, è possibile visualizzare la suddivisione dei tipi di file dannosi rilevati per [Gli allegati sicuri degli strumenti di analisi](atp-safe-attachments.md) e [anti-spam &amp; protezione anti-malware in Office 365](anti-spam-and-anti-malware-protection.md).
  
![Dati del report di tipi di File degli strumenti di analisi di un giorno](media/10d18428-699a-41d2-a73e-be3a8214ada1.png)
  
## <a name="atp-message-disposition-report"></a>Report di disposizione degli strumenti di analisi del messaggio

Il rapporto di **Disposizione degli strumenti di analisi del messaggio** Mostra le azioni eseguite per i messaggi di posta elettronica che sono stati rilevati con contenuto dannoso. 
  
Per visualizzare il report nel [protezione &amp; centro conformità](https://security.microsoft.com), andare al **report** \> **Dashboard** \> **Disposizione degli strumenti di analisi del messaggio**.
  
![Rapporto di eliminazione degli strumenti di analisi messaggi](media/b0ff65c4-53d3-496d-bafa-8937a5eb69e5.png)
  
Quando passa il mouse su una barra nel grafico, è possibile visualizzare le azioni eseguite per la posta elettronica rilevato per quel giorno.
  
![Dati del Report di eliminazione degli strumenti di analisi messaggio per un giorno](media/68d2beb8-4b30-48c4-8ba6-5e8ab88ae456.png)
  
## <a name="additional-reports-to-view"></a>Altri report per visualizzare

Oltre ai rapporti degli strumenti di analisi descritti in questo articolo, diversi altri report disponibili, come descritto nella tabella riportata di seguito:


|Tipo di rapporto  |Ulteriori informazioni  |
|---------|---------|
|**Rapporti sulla protezione posta elettronica**, ad esempio primi mittenti e destinatari report, un report di posta elettronica di spoofing e un rapporto sui rilevamenti di posta indesiderata. | [Visualizzare i report di protezione posta elettronica in sicurezza &amp; centro conformità](view-email-security-reports.md)        |
|**Explorer** (detto anche Explorer rischio, questa è inclusa funzionalità di [Business Intelligence di Office 365 rischio](office-365-ti.md))     | [Utilizzare Esplora in sicurezza &amp; centro conformità](use-explorer-in-security-and-compliance.md)        |
|**EOP e degli strumenti di analisi dei risultati** (Questo è un report personalizzato che generare tramite PowerShell). In questo report contiene informazioni, ad esempio dominio, data, tipo di evento, Direction, azione e numero di messaggi.  | [Riferimento al cmdlet Get-MailTrafficATPReport](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/get-mailtrafficatpreport?view=exchange-ps) |
|**Rilevamenti di EOP e degli strumenti di analisi** (Questo è un report personalizzato che generare tramite PowerShell). In questo report contiene informazioni dettagliate sui file dannosi o URL, tentativi di phishing, rappresentazione e altri potenziali pericoli nel messaggio di posta elettronica o i file.   | [Riferimento al cmdlet Get-MailDetailATPReport](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/get-maildetailatpreport?view=exchange-ps)        |

  
## <a name="what-permissions-are-needed-to-view-the-atp-reports"></a>Autorizzazioni necessarie per visualizzare i report degli strumenti di analisi?

Per poter visualizzare e utilizzare i rapporti descritti in questo articolo, **è necessario disporre di un ruolo appropriato assegnato sia la sicurezza &amp; centro conformità e l'interfaccia di amministrazione di Exchange**.

- Per la sicurezza &amp; centro conformità, è necessario disporre dei seguenti ruoli assegnati:
    - Gestione organizzazione
    - Amministratore della sicurezza
    - Lettore di sicurezza

- Per Exchange Online deve essere uno dei seguenti ruoli assegnati:
    - Gestione organizzazione
    - Gestione organizzazione in sola visualizzazione
    - Ruolo Destinatari di sola lettura
    - Gestione della conformità

Per ulteriori informazioni, vedere le risorse seguenti:

- [Le autorizzazioni di sicurezza di Office 365 &amp; centro conformità](permissions-in-the-security-and-compliance-center.md)

- [Autorizzazioni funzionalità in Exchange Online](https://docs.microsoft.com/exchange/permissions-exo/feature-permissions)
   
## <a name="what-if-the-reports-arent-showing-data"></a>Se il report non vengono visualizzate dati?

Se non si possono visualizzare dati nei report degli strumenti di analisi, assicurarsi che i criteri siano configurati correttamente. L'organizzazione deve disporre [degli strumenti di analisi collegamenti sicuro politiche](set-up-atp-safe-links-policies.md) e [gli allegati sicuri degli strumenti di analisi criteri](set-up-atp-safe-attachments-policies.md) definiti nell'ordine indicato per la protezione degli strumenti di analisi in locale. Vedere anche [protezione antispam e antimalware in Office 365](anti-spam-and-anti-malware-protection.md).
  
## <a name="related-topics"></a>Argomenti correlati

[Report e sui concetti di Office 365 Security &amp; centro conformità](reports-and-insights-in-security-and-compliance.md)
  
[Creare una pianificazione per un report nella protezione &amp; centro conformità](create-a-schedule-for-a-report.md)
  
[Impostare e scaricare un report personalizzato per la protezione &amp; centro conformità](set-up-and-download-a-custom-report.md)
  

