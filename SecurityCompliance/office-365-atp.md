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
ms.openlocfilehash: fed816ec8cd0e3e7a6b5118fde35d81647b94f02
ms.sourcegitcommit: 099bbfb1d16b251fd5cf18ec6515faaf9a989176
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/09/2018
ms.locfileid: "25454353"
---
# <a name="office-365-advanced-threat-protection"></a><span data-ttu-id="3eec1-104">Office 365 Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="3eec1-104">Office 365 Advanced Threat Protection</span></span>

<span data-ttu-id="3eec1-105">Office 365 avanzate Threat Protection (degli strumenti di analisi) consente di proteggere l'organizzazione da attacchi dannosi da:</span><span class="sxs-lookup"><span data-stu-id="3eec1-105">Office 365 Advanced Threat Protection (ATP) helps to protect your organization from malicious attacks by:</span></span>
  
- <span data-ttu-id="3eec1-106">Analisi allegati di posta elettronica di malware con [Allegati sicuri degli strumenti di analisi](atp-safe-attachments.md)</span><span class="sxs-lookup"><span data-stu-id="3eec1-106">Scanning email attachments for malware with [ATP Safe Attachments](atp-safe-attachments.md)</span></span>
    
- <span data-ttu-id="3eec1-107">Indirizzi di analisi web (URL) in documenti di Office con [Collegamenti sicuro degli strumenti di analisi](atp-safe-links.md) e messaggi di posta elettronica</span><span class="sxs-lookup"><span data-stu-id="3eec1-107">Scanning web addresses (URLs) in email messages and Office documents with [ATP Safe Links](atp-safe-links.md)</span></span>
    
- <span data-ttu-id="3eec1-108">Identificazione e il blocco file dannosi nelle raccolte online con [degli strumenti di analisi di SharePoint, OneDrive e team di Microsoft](atp-for-spo-odb-and-teams.md)</span><span class="sxs-lookup"><span data-stu-id="3eec1-108">Identifying and blocking malicious files in online libraries with [ATP for SharePoint, OneDrive, and Microsoft Teams](atp-for-spo-odb-and-teams.md)</span></span>
    
- <span data-ttu-id="3eec1-109">Verifica dei messaggi di posta elettronica per lo spoofing non autorizzato a [spoofing intelligence](learn-about-spoof-intelligence.md)</span><span class="sxs-lookup"><span data-stu-id="3eec1-109">Checking email messages for unauthorized spoofing with [spoof intelligence](learn-about-spoof-intelligence.md)</span></span>
    
- <span data-ttu-id="3eec1-110">Rilevamento quando un utente tenta di rappresentare gli utenti e dei domini personalizzati dell'organizzazione le [funzionalità di protezione anti-phishing degli strumenti di analisi in Office 365](atp-anti-phishing.md)</span><span class="sxs-lookup"><span data-stu-id="3eec1-110">Detecting when someone attempts to impersonate your users and your organization's custom domains with [ATP anti-phishing capabilities in Office 365](atp-anti-phishing.md)</span></span>
    
<span data-ttu-id="3eec1-p102">**Protezione e degli strumenti di analisi di Office 365 dipende dai criteri che definisce il team di protezione dell'organizzazione per collegamenti sicuro, gli allegati sicuri e Anti-Phishing**. È importante esaminare periodicamente e modificare i criteri per mantenerle aggiornato e possono avvalersi delle nuove funzionalità che vengono aggiunti al servizio. [Sono disponibili i report](view-reports-for-atp.md) per visualizzare la modalità di funzionamento degli strumenti di analisi per l'organizzazione. Questi rapporti anche possono visualizzare le aree cui potrebbe essere necessario esaminare e aggiornare i criteri. E, se si dispongono di file che vengono contrassegnati come malware che non deve essere o file si desidera che Microsoft per esaminare, è possibile [inviare un file a Microsoft per l'analisi](#submit-a-suspicious-file-to-microsoft-for-analysis).</span><span class="sxs-lookup"><span data-stu-id="3eec1-p102">**Protection through Office 365 ATP is determined by policies that your organization's security team defines for Safe Links, Safe Attachments, and Anti-Phishing**. It's important to periodically review and revise your policies to keep them up to date and to take advantages of new features that are added to the service. [Reports are available](view-reports-for-atp.md) to show how ATP is working for your organization. These reports can also show you areas where you might need to review and update your policies. And, if you have files that are marked as malware that shouldn't be, or files you'd like Microsoft to examine, you can [submit a file to Microsoft for analysis](#submit-a-suspicious-file-to-microsoft-for-analysis).</span></span>
      
## <a name="get-office-365-atp"></a><span data-ttu-id="3eec1-116">Ottenere degli strumenti di analisi di Office 365</span><span class="sxs-lookup"><span data-stu-id="3eec1-116">Get Office 365 ATP</span></span>

> [!IMPORTANT]
> <span data-ttu-id="3eec1-p103">Office 365 degli strumenti di analisi è incluso in sottoscrizioni, ad esempio Microsoft 365 Enterprise, Office 365 Enterprise E5, A5 Education di Office 365 e [Microsoft 365 Business](https://support.office.com/article/c123694a-1efb-459e-a8d5-2187975373dc). Se l'organizzazione dispone di una sottoscrizione a Office 365 che non include degli strumenti di analisi di Office 365, è possibile acquistare potenzialmente degli strumenti di analisi come componente aggiuntivo. Per ulteriori informazioni, vedere [Office 365 avanzate Threat Protection Service Description](https://technet.microsoft.com/library/exchange-online-advanced-threat-protection-service-description.aspx).</span><span class="sxs-lookup"><span data-stu-id="3eec1-p103">Office 365 ATP is included in subscriptions, such as Microsoft 365 Enterprise, Office 365 Enterprise E5, Office 365 Education A5, and [Microsoft 365 Business](https://support.office.com/article/c123694a-1efb-459e-a8d5-2187975373dc). If your organization has an Office 365 subscription that does not include Office 365 ATP, you can potentially purchase ATP as an add-on. For more information, see [Office 365 Advanced Threat Protection Service Description](https://technet.microsoft.com/library/exchange-online-advanced-threat-protection-service-description.aspx).</span></span> 

1. <span data-ttu-id="3eec1-120">Come amministratore globale o di sicurezza, passare a [https://portal.office.com](https://portal.office.com) e accedere con l'account di lavoro o della scuola per Office 365.</span><span class="sxs-lookup"><span data-stu-id="3eec1-120">As a global or security administrator, go to [https://portal.office.com](https://portal.office.com) and sign in with your work or school account for Office 365.</span></span> 
    
2. <span data-ttu-id="3eec1-121">Scegliere **amministratore** \> **fatturazione** per verificare cosa include in abbonamento corrente.</span><span class="sxs-lookup"><span data-stu-id="3eec1-121">Choose **Admin** \> **Billing** to see what your current subscription includes.</span></span> <br/><span data-ttu-id="3eec1-122">![Come un amministratore globale acceda a portal.office.com e passare a amministrazione \> fatturazione](media/18a3546c-bd1f-4f49-82ec-0184909b42c2.png)</span><span class="sxs-lookup"><span data-stu-id="3eec1-122">![As a global admin, sign in at portal.office.com and go to Admin \> Billing](media/18a3546c-bd1f-4f49-82ec-0184909b42c2.png)</span></span>
  
3. <span data-ttu-id="3eec1-123">Se viene visualizzata **E5 Enterprise di Office 365**, **Office 365 Education A5**o **Microsoft 365 Business**, l'organizzazione dispone degli strumenti di analisi.</span><span class="sxs-lookup"><span data-stu-id="3eec1-123">If you see **Office 365 Enterprise E5**, **Office 365 Education A5**, or **Microsoft 365 Business**, then your organization has ATP.</span></span> <br/><span data-ttu-id="3eec1-p104">Se viene visualizzata una sottoscrizione diversa, ad esempio **Office 365 Enterprise E3** o **Office 365 Enterprise E1**, è possibile aggiungere degli strumenti di analisi. A tale scopo, scegliere **Aggiungi sottoscrizione +**.</span><span class="sxs-lookup"><span data-stu-id="3eec1-p104">If you see a different subscription, such as **Office 365 Enterprise E3** or **Office 365 Enterprise E1**, consider adding ATP. To do that, choose **+ Add subscription**.</span></span>
    
<span data-ttu-id="3eec1-126">Dopo avere creato degli strumenti di analisi, il passaggio successivo è per il team di protezione definire i criteri.</span><span class="sxs-lookup"><span data-stu-id="3eec1-126">Once you have ATP, the next step is for your security team to define policies.</span></span> 
  
## <a name="define-policies-for-atp"></a><span data-ttu-id="3eec1-127">Definire i criteri per strumenti di analisi</span><span class="sxs-lookup"><span data-stu-id="3eec1-127">Define policies for ATP</span></span>

- <span data-ttu-id="3eec1-128">**[Impostazione dei criteri anti-phishing degli strumenti di analisi in Office 365](set-up-atp-anti-phishing-policies.md)** inclusa attacchi basati sulla rappresentazione per la protezione dagli attacchi che inviano messaggi di posta elettronica sembrano provenire da mittenti attendibili o domini</span><span class="sxs-lookup"><span data-stu-id="3eec1-128">**[Set up ATP anti-phishing policies in Office 365](set-up-atp-anti-phishing-policies.md)** including impersonation-based attacks to protect against attackers who send email messages that appear to be from trusted people or domains</span></span> 

- <span data-ttu-id="3eec1-129">**[Impostare i criteri degli strumenti di analisi collegamenti attendibili in Office 365](set-up-atp-safe-links-policies.md)** inclusa [personalizzato bloccati gli URL](set-up-a-custom-blocked-urls-list-wtih-atp.md) ed [elenco URL "non di riscrittura" personalizzato](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md) dell'organizzazione</span><span class="sxs-lookup"><span data-stu-id="3eec1-129">**[Set up ATP Safe Links policies in Office 365](set-up-atp-safe-links-policies.md)** including your organization's [custom blocked URLs list](set-up-a-custom-blocked-urls-list-wtih-atp.md) and [custom "Do not rewrite" URLs list](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md)</span></span>
    
- <span data-ttu-id="3eec1-130">**[Configurare gli allegati sicuri degli strumenti di analisi criteri in Office 365](set-up-atp-safe-attachments-policies.md)** che può includere [Recapito dinamico e visualizzazione in anteprima](dynamic-delivery-and-previewing.md)</span><span class="sxs-lookup"><span data-stu-id="3eec1-130">**[Set up ATP Safe Attachments policies in Office 365](set-up-atp-safe-attachments-policies.md)** that can include [dynamic delivery and previewing](dynamic-delivery-and-previewing.md)</span></span>
  
## <a name="see-how-atp-is-working-by-viewing-reports"></a><span data-ttu-id="3eec1-131">Vedere funzionamento degli strumenti di analisi visualizzando i report</span><span class="sxs-lookup"><span data-stu-id="3eec1-131">See how ATP is working by viewing reports</span></span>

<span data-ttu-id="3eec1-132">Dopo aver i criteri degli strumenti di analisi, sono disponibili per mostrare come funziona il servizio di report.</span><span class="sxs-lookup"><span data-stu-id="3eec1-132">After your ATP policies are in place, reports are available to show how the service is working.</span></span>

<span data-ttu-id="3eec1-133">[![La sicurezza &amp; dashboard centro conformità risulta utile per determinare dove funzioni avanzate Threat Protection](media/6b213d34-adbb-44af-8549-be9a7e2db087.png)](view-reports-for-atp.md)</span><span class="sxs-lookup"><span data-stu-id="3eec1-133">[![The Security &amp; Compliance Center dashboard can help you see where Advanced Threat Protection is working](media/6b213d34-adbb-44af-8549-be9a7e2db087.png)](view-reports-for-atp.md)</span></span>
  
1. <span data-ttu-id="3eec1-p105">Assicurarsi di essere un amministratore globale di Office 365, amministratore della sicurezza o lettore di sicurezza. (Vedere [le autorizzazioni di sicurezza di Office 365 &amp; centro conformità](permissions-in-the-security-and-compliance-center.md).)</span><span class="sxs-lookup"><span data-stu-id="3eec1-p105">Make sure that you are an Office 365 global administrator, security administrator, or security reader. (See [Permissions in the Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md).)</span></span>
    
2. <span data-ttu-id="3eec1-136">[Visualizzare i report per la protezione avanzata di rischio](view-reports-for-atp.md).</span><span class="sxs-lookup"><span data-stu-id="3eec1-136">[View reports for Advanced Threat Protection](view-reports-for-atp.md).</span></span>
    
3. <span data-ttu-id="3eec1-p106">Se necessario, apportare modifiche per i criteri di protezione. Vedere le risorse seguenti:</span><span class="sxs-lookup"><span data-stu-id="3eec1-p106">If needed, make adjustments to your security policies. See the following resources:</span></span>

  - [<span data-ttu-id="3eec1-139">Criteri di anti-phishing degli strumenti di analisi in Office 365</span><span class="sxs-lookup"><span data-stu-id="3eec1-139">ATP anti-phishing policies in Office 365</span></span>](set-up-atp-anti-phishing-policies.md)
    
  - [<span data-ttu-id="3eec1-140">Criteri degli strumenti di analisi collegamenti attendibili in Office 365</span><span class="sxs-lookup"><span data-stu-id="3eec1-140">ATP Safe Links policies in Office 365</span></span>](set-up-atp-safe-links-policies.md)
    
  - [<span data-ttu-id="3eec1-141">Criteri degli strumenti di analisi allegati attendibili in Office 365</span><span class="sxs-lookup"><span data-stu-id="3eec1-141">ATP Safe Attachments policies in Office 365</span></span>](set-up-atp-safe-attachments-policies.md)
    
    
## <a name="submit-a-suspicious-file-to-microsoft-for-analysis"></a><span data-ttu-id="3eec1-142">Inviare un file potenzialmente dannoso a Microsoft per l'analisi</span><span class="sxs-lookup"><span data-stu-id="3eec1-142">Submit a suspicious file to Microsoft for analysis</span></span>

- <span data-ttu-id="3eec1-p107">Se viene visualizzato un file che si ritiene che potrebbe essere malware, è possibile inviare file a Microsoft per l'analisi. Visitare il [portale di Business Intelligence di protezione di Windows Defender invio](https://go.microsoft.com/fwlink/?linkid=857185).</span><span class="sxs-lookup"><span data-stu-id="3eec1-p107">If you get a file that you suspect could be malware, you can submit that file to Microsoft for analysis. Visit the [Windows Defender Security Intelligence submission portal](https://go.microsoft.com/fwlink/?linkid=857185).</span></span>

- <span data-ttu-id="3eec1-145">Se viene visualizzato un messaggio di posta elettronica, con o senza un allegato, che si desidera inviare a Microsoft per l'analisi, utilizzare il [componente aggiuntivo di report](enable-the-report-message-add-in.md).</span><span class="sxs-lookup"><span data-stu-id="3eec1-145">If you get an email message (with or without an attachment) that you'd like to submit to Microsoft for analysis, use the [Report Message add-in](enable-the-report-message-add-in.md).</span></span> 
  
## <a name="related-topics"></a><span data-ttu-id="3eec1-146">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="3eec1-146">Related topics</span></span>

[<span data-ttu-id="3eec1-147">Visualizzare i report per Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="3eec1-147">View the reports for Advanced Threat Protection</span></span>](view-reports-for-atp.md)
  
[<span data-ttu-id="3eec1-148">Gestione di Office 365 protezione delle minacce &amp; centro conformità</span><span class="sxs-lookup"><span data-stu-id="3eec1-148">Threat management in the Office 365 Security &amp; Compliance Center</span></span>](threat-management.md)
  

