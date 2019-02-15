---
title: Office 365 Advanced Threat Protection
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 02/08/2019
ms.audience: Admin
ms.topic: hub-page
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: e100fe7c-f2a1-4b7d-9e08-622330b83653
ms.collection:
- M365-security-compliance
description: Office 365 Advanced Threat Protection include Intelligence spoof, collegamenti sicuri, allegati sicuri, funzionalità di anti-phishing avanzate e Threat Intelligence.
ms.openlocfilehash: d78b37ca048187a298b6e083b54ad68b949638ef
ms.sourcegitcommit: 2af6c3e8a74995294a67429530af8f085e6ca136
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/14/2019
ms.locfileid: "30051177"
---
# <a name="office-365-advanced-threat-protection"></a>Office 365 Advanced Threat Protection

## <a name="overview-of-office-365-advanced-threat-protection"></a>Panoramica di Office 365 Advanced Threat Protection

> [!IMPORTANT]
> Questo articolo è destinato ai clienti aziendali. Se si è un utente di casa che cerca informazioni sui collegamenti sicuri in Outlook, vedere [Advanced Outlook.com Security](https://support.office.com/article/advanced-outlook-com-security-for-office-365-subscribers-882d2243-eab9-4545-a58a-b36fee4a46e2).

Office 365 Advanced Threat Protection (ATP) consente di proteggere l'organizzazione da attacchi dannosi da:
  
- Scansione degli allegati di posta elettronica per malware con [allegati sicuri di ATP](atp-safe-attachments.md)
    
- Analisi degli indirizzi Web (URL) nei messaggi di posta elettronica e nei documenti di Office con [collegamenti sicuri di ATP](atp-safe-links.md)
    
- Identificazione e blocco di file dannosi nelle raccolte online con [ATP per SharePoint, OneDrive e Microsoft teams](atp-for-spo-odb-and-teams.md)
    
- Controllo dei messaggi di posta elettronica per spoofing non autorizzato con [Intelligence contraffatta](learn-about-spoof-intelligence.md)
    
- Rilevamento quando un utente tenta di impersonare gli utenti e i domini personalizzati dell'organizzazione con le [funzionalità di anti-phishing ATP in Office 365](atp-anti-phishing.md)
    
**La protezione tramite Office 365 ATP è determinata da criteri che il team di sicurezza dell'organizzazione definisce per collegamenti sicuri, allegati sicuri e anti-phishing**. È importante definire i criteri e riesaminare e rivedere periodicamente tali criteri per mantenerli aggiornati e per trarre vantaggio dalle nuove funzionalità aggiunte al servizio. 

I [report sono disponibili](view-reports-for-atp.md) per mostrare come funziona ATP per la propria organizzazione. Questi report possono inoltre visualizzare le aree in cui potrebbe essere necessario esaminare e aggiornare i criteri. Inoltre, se si dispone di file contrassegnati come malware che non dovrebbero essere o di file che si desidera esaminare da Microsoft, è possibile [inviare un file a Microsoft per l'analisi](#submit-a-suspicious-file-to-microsoft-for-analysis).

## <a name="new-features-are-continually-being-added-to-atp"></a>Nuove funzionalità vengono continuamente aggiunte a ATP

Si continua ad aggiungere nuove funzionalità a Office 365 e che include ATP. Di seguito è riportato un elenco di diverse nuove funzionalità, alcune delle quali richiedono la revisione e l'aggiornamento di un criterio ATP. Per ulteriori informazioni sulle nuove funzionalità di ATP (o Microsoft 365 in generale), visitare la Guida di [orientamento di microsoft 365](https://www.microsoft.com/microsoft-365/roadmap?filters=O365).


|Aggiornamenti delle funzionalità  |Elementi azione  |
|---------|---------|
|A partire dal febbraio 2019 e ripartiti nei prossimi mesi, le funzionalità di intelligence per le minacce vengono aggiunte al trifosfato di adenosina. Inoltre, se l'organizzazione attualmente non dispone di ATP, saranno disponibili nuove opzioni da prendere in considerazione, tra cui il piano ATP 1 e il piano ATP 2. Per ulteriori informazioni, vedere i [piani e i prezzi di office 365 Advanced Threat Protection](https://products.office.com/exchange/advance-threat-protection) e la [Descrizione del servizio Advanced Threat protection di Office 365](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description). |Esaminare la sottoscrizione dell'organizzazione e, se necessario, [acquistare o modificare un componente aggiuntivo](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/buy-or-edit-an-add-on).  |
|A partire da ottobre 2018 e distribuita nei prossimi mesi, quando gli utenti utilizzano Outlook o Outlook Web Application (OWA), i collegamenti sicuri di ATP eseguono il rendering degli URL originali e non degli URL riscritti. (Viene chiamato il rendering del collegamento nativo).<br>Quando viene eseguito il rendering del collegamento nativo per l'organizzazione, questa funzionalità funzionerà in Outlook 365 (a portata di clic) e OWA.|Nessuno         |
|A partire da settembre 2018, le [pagine di avviso ATP di Office 365](atp-safe-links-warning-pages.md) dispongono di una nuova combinazione di colori, maggiori dettagli e la possibilità di continuare a un sito nonostante gli avvisi e i suggerimenti consigliati. |Nessuno         |
|A partire dalla seconda metà del 2018, la protezione dei collegamenti sicuri di ATP è estesa per essere applicata agli URL in Office Online (Word online, Excel online, PowerPoint online e OneNote online) e Office 365 ProPlus su Mac.   |[Esaminare e modificare i criteri dei collegamenti sicuri di ATP](set-up-atp-safe-links-policies.md)  |
|A partire dalla fine di maggio [](quarantine-email-messages.md) 2018, le funzionalità di quarantena nel centro sicurezza &amp; e conformità vengono estese a [ATP per SharePoint Online, OneDrive for business e Microsoft teams](atp-for-spo-odb-and-teams.md). |[Esaminare e modificare i criteri per gli allegati sicuri di ATP](set-up-atp-safe-attachments-policies.md) |
|A partire da marzo 2018, la protezione di collegamenti sicuri di ATP è estesa per essere applicata ai messaggi di posta elettronica inviati da persone all'interno di un'organizzazione. |[Esaminare e modificare i criteri dei collegamenti sicuri di ATP](set-up-atp-safe-links-policies.md) |
|A partire dalla fine di ottobre 2017, la protezione dei collegamenti sicuri di ATP è estesa per essere applicata agli URL nella posta elettronica e negli URL dei documenti di Office 365 ProPlus, ad esempio Word, Excel, PowerPoint e Visio su Windows, nonché le app di Office sui dispositivi iOS e Android.  |Assicurarsi [di utilizzare l'autenticazione moderna per Office](https://docs.microsoft.com/office365/enterprise/modern-auth-for-office-2013-and-2016) |

## <a name="get-office-365-atp"></a>Ottenere Office 365 ATP

Office 365 ATP è incluso nelle sottoscrizioni, ad esempio [microsoft 365 Enterprise](https://www.microsoft.com/microsoft-365/enterprise/home), [Microsoft 365 Business](https://www.microsoft.com/microsoft-365/business), Office 365 enterprise E5 e Office 365 Education a5. Se nell'organizzazione è presente un abbonamento a Office 365 che non include Office 365 ATP, è possibile acquistare ATP come componente aggiuntivo. Per ulteriori informazioni, vedere i [piani e i prezzi di office 365 Advanced Threat Protection](https://products.office.com/exchange/advance-threat-protection) e la [Descrizione del servizio Advanced Threat protection di Office 365](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description). 

## <a name="define-policies-for-atp"></a>Definire i criteri per ATP

Per definire (o modificare) i criteri ATP, è necessario che sia assegnato uno dei ruoli descritti nella tabella seguente:

|Ruolo  |Dove/come assegnato  |
|---------|---------|
|Amministratore globale di Office 365 |Per impostazione predefinita, la persona che si iscrive all'acquisto di Office 365 è un amministratore globale. Per ulteriori informazioni, vedere [informazioni sui ruoli di amministratore di Office 365](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles) .         |
|Amministratore della sicurezza |Interfaccia di amministrazione di Azure Active[https://aad.portal.azure.com](https://aad.portal.azure.com)directory ()|
|Gestione dell'organizzazione di Exchange Online |Interfaccia di amministrazione di[https://outlook.office365.com/ecp](https://outlook.office365.com/ecp)Exchange () <br>oppure <br>  Cmdlet di PowerShell (vedere [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps)) |

> [!TIP]
> Per ulteriori informazioni sui ruoli e sulle autorizzazioni, vedere perMissions [in the &amp; Office 365 Security Compliance Center](permissions-in-the-security-and-compliance-center.md).

Sono disponibili diversi tipi di criteri ATP per la definizione e la revisione periodica.

1. **[Impostare i criteri anti-phishing ATP in Office 365](set-up-anti-phishing-policies.md)** , compresi gli attacchi basati sulla rappresentazione per proteggere gli utenti che inviano messaggi di posta elettronica provenienti da persone o domini attendibili. 

2. **[Configurare i criteri dei collegamenti sicuri di ATP in Office 365](set-up-atp-safe-links-policies.md)** incluso l' [elenco degli URL bloccati personalizzati](set-up-a-custom-blocked-urls-list-wtih-atp.md) dell'organizzazione e l' [elenco di URL personalizzato "non riscrivere"](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md).
    
3. **[Impostare i criteri per gli allegati sicuri di ATP in Office 365](set-up-atp-safe-attachments-policies.md)** e scegliere tra diverse opzioni, ad esempio il [recapito dinamico e l'anteprima](dynamic-delivery-and-previewing.md).
  
## <a name="see-how-atp-is-working-by-viewing-reports"></a>Vedere come funziona ATP visualizzando i report

Dopo che i criteri ATP sono sul posto, i report sono disponibili per illustrare il funzionamento del servizio. (nel centro conformità di Office 365 Security &, accedere al **** > **Dashboard**dei report).

[![Il dashboard &amp; del Centro sicurezza e conformità consente di individuare la modalità di funzionamento di Advanced Threat Protection](media/6b213d34-adbb-44af-8549-be9a7e2db087.png)](view-reports-for-atp.md)
  
1. Come un amministratore globale di Office 365, un amministratore della sicurezza o un lettore di [https://protection.office.com](https://protection.office.com) sicurezza, accedere e accedere.
    
2. Andare al **** > **Dashboard**di report. Per ottenere assistenza con questi rapporti, vedere [visualizzare i report per Advanced Threat Protection](view-reports-for-atp.md).
    
3. Se necessario, apportare le modifiche apportate ai criteri di sicurezza. Per ottenere assistenza, vedere le risorse seguenti:
    - [Criteri di anti-phishing ATP](set-up-anti-phishing-policies.md)
    - [Criteri per i collegamenti sicuri ATP](set-up-atp-safe-links-policies.md)
    - [Criteri per gli allegati sicuri ATP](set-up-atp-safe-attachments-policies.md)
    
    
## <a name="submit-a-suspicious-file-to-microsoft-for-analysis"></a>Inviare un file sospetto a Microsoft per l'analisi

- Se si ottiene un file che si sospetta potrebbe essere malware, è possibile inviare tale file a Microsoft per l'analisi. Visitare il [portale di invio di Windows Defender Security Intelligence](https://go.microsoft.com/fwlink/?linkid=857185).

- Se si riceve un messaggio di posta elettronica (con o senza allegato) che si desidera inviare a Microsoft per l'analisi, utilizzare il [componente aggiuntivo segnala messaggio](enable-the-report-message-add-in.md). 
  

