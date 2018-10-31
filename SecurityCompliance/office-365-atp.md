---
title: Office 365 Advanced Threat Protection
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 10/09/2018
ms.audience: Admin
ms.topic: hub-page
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: e100fe7c-f2a1-4b7d-9e08-622330b83653
description: Protezione da minacce avanzate di Office 365 include intelligence spoofing, collegamenti sicuri, gli allegati sicuri e funzionalità avanzate di anti-phishing. Protezione avanzata di rischio viene inoltre esteso per i file in SharePoint Online, OneDrive for Business e Teams Microsoft.
ms.openlocfilehash: def22368f8bc219ebceda797dd04b234bc3c4435
ms.sourcegitcommit: cda46434094bc2837dba90256d044ba77552df12
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2018
ms.locfileid: "25850830"
---
# <a name="office-365-advanced-threat-protection"></a>Office 365 Advanced Threat Protection

Office 365 avanzate Threat Protection (degli strumenti di analisi) consente di proteggere l'organizzazione da attacchi dannosi da:
  
- Analisi allegati di posta elettronica di malware con [Allegati sicuri degli strumenti di analisi](atp-safe-attachments.md)
    
- Indirizzi di analisi web (URL) in documenti di Office con [Collegamenti sicuro degli strumenti di analisi](atp-safe-links.md) e messaggi di posta elettronica
    
- Identificazione e il blocco file dannosi nelle raccolte online con [degli strumenti di analisi di SharePoint, OneDrive e team di Microsoft](atp-for-spo-odb-and-teams.md)
    
- Verifica dei messaggi di posta elettronica per lo spoofing non autorizzato a [spoofing intelligence](learn-about-spoof-intelligence.md)
    
- Rilevamento quando un utente tenta di rappresentare gli utenti e dei domini personalizzati dell'organizzazione le [funzionalità di protezione anti-phishing degli strumenti di analisi in Office 365](atp-anti-phishing.md)
    
**Protezione e degli strumenti di analisi di Office 365 dipende dai criteri che definisce il team di protezione dell'organizzazione per collegamenti sicuro, gli allegati sicuri e Anti-Phishing**. È importante esaminare periodicamente e modificare i criteri per mantenerle aggiornato e possono avvalersi delle nuove funzionalità che vengono aggiunti al servizio. [Sono disponibili i report](view-reports-for-atp.md) per visualizzare la modalità di funzionamento degli strumenti di analisi per l'organizzazione. Questi rapporti anche possono visualizzare le aree cui potrebbe essere necessario esaminare e aggiornare i criteri. E, se si dispongono di file che vengono contrassegnati come malware che non deve essere o file si desidera che Microsoft per esaminare, è possibile [inviare un file a Microsoft per l'analisi](#submit-a-suspicious-file-to-microsoft-for-analysis).
      
## <a name="get-office-365-atp"></a>Ottenere degli strumenti di analisi di Office 365

> [!IMPORTANT]
> Office 365 degli strumenti di analisi è incluso in sottoscrizioni, ad esempio Microsoft 365 Enterprise, Office 365 Enterprise E5, A5 Education di Office 365 e [Microsoft 365 Business](https://support.office.com/article/c123694a-1efb-459e-a8d5-2187975373dc). Se l'organizzazione dispone di una sottoscrizione a Office 365 che non include degli strumenti di analisi di Office 365, è possibile acquistare potenzialmente degli strumenti di analisi come componente aggiuntivo. Per ulteriori informazioni, vedere [Office 365 avanzate Threat Protection Service Description](https://technet.microsoft.com/library/exchange-online-advanced-threat-protection-service-description.aspx). 

1. Come amministratore globale o di sicurezza, passare a [https://portal.office.com](https://portal.office.com) e accedere con l'account di lavoro o della scuola per Office 365. 
    
2. Scegliere **amministratore** \> **fatturazione** per verificare cosa include in abbonamento corrente. <br/>![Come un amministratore globale acceda a portal.office.com e passare a amministrazione \> fatturazione](media/18a3546c-bd1f-4f49-82ec-0184909b42c2.png)
  
3. Se viene visualizzata **E5 Enterprise di Office 365**, **Office 365 Education A5**o **Microsoft 365 Business**, l'organizzazione dispone degli strumenti di analisi. <br/>Se viene visualizzata una sottoscrizione diversa, ad esempio **Office 365 Enterprise E3** o **Office 365 Enterprise E1**, è possibile aggiungere degli strumenti di analisi. A tale scopo, scegliere **Aggiungi sottoscrizione +**.
    
Dopo avere creato degli strumenti di analisi, il passaggio successivo è per il team di protezione definire i criteri. 
  
## <a name="define-policies-for-atp"></a>Definire i criteri per strumenti di analisi

- **[Impostazione dei criteri anti-phishing degli strumenti di analisi in Office 365](set-up-anti-phishing-policies.md)** inclusa attacchi basati sulla rappresentazione per la protezione dagli attacchi che inviano messaggi di posta elettronica sembrano provenire da mittenti attendibili o domini 

- **[Impostare i criteri degli strumenti di analisi collegamenti attendibili in Office 365](set-up-atp-safe-links-policies.md)** inclusa [personalizzato bloccati gli URL](set-up-a-custom-blocked-urls-list-wtih-atp.md) ed [elenco URL "non di riscrittura" personalizzato](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md) dell'organizzazione
    
- **[Impostare i criteri degli strumenti di analisi allegati attendibili in Office 365](set-up-atp-safe-attachments-policies.md)** che può includere [Recapito dinamico e visualizzazione in anteprima](dynamic-delivery-and-previewing.md)
  
## <a name="see-how-atp-is-working-by-viewing-reports"></a>Vedere funzionamento degli strumenti di analisi visualizzando i report

Dopo aver i criteri degli strumenti di analisi, sono disponibili per mostrare come funziona il servizio di report.

[![La sicurezza &amp; dashboard centro conformità risulta utile per determinare dove funzioni avanzate Threat Protection](media/6b213d34-adbb-44af-8549-be9a7e2db087.png)](view-reports-for-atp.md)
  
1. Assicurarsi di essere un amministratore globale di Office 365, amministratore della sicurezza o lettore di sicurezza. (Vedere [le autorizzazioni di sicurezza di Office 365 &amp; centro conformità](permissions-in-the-security-and-compliance-center.md).)
    
2. [Visualizzare i report per la protezione avanzata di rischio](view-reports-for-atp.md).
    
3. Se necessario, apportare modifiche per i criteri di protezione. Vedere le risorse seguenti:

  - [Criteri di anti-phishing degli strumenti di analisi in Office 365](set-up-anti-phishing-policies.md)
    
  - [Criteri degli strumenti di analisi collegamenti attendibili in Office 365](set-up-atp-safe-links-policies.md)
    
  - [Criteri degli strumenti di analisi allegati attendibili in Office 365](set-up-atp-safe-attachments-policies.md)
    
    
## <a name="submit-a-suspicious-file-to-microsoft-for-analysis"></a>Inviare un file potenzialmente dannoso a Microsoft per l'analisi

- Se viene visualizzato un file che si ritiene che potrebbe essere malware, è possibile inviare file a Microsoft per l'analisi. Visitare il [portale di Business Intelligence di protezione di Windows Defender invio](https://go.microsoft.com/fwlink/?linkid=857185).

- Se viene visualizzato un messaggio di posta elettronica, con o senza un allegato, che si desidera inviare a Microsoft per l'analisi, utilizzare il [componente aggiuntivo di report](enable-the-report-message-add-in.md). 
  
## <a name="related-topics"></a>Argomenti correlati

[Visualizzare i report per Advanced Threat Protection](view-reports-for-atp.md)
  
[Threat management in the Office 365 Security &amp; Compliance Center](threat-management.md)
  

