---
title: Recapito dinamico e l'anteprima allegati sicuri di Office 365 degli strumenti di analisi di
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: f16c9928-8e3d-4219-b994-271dc9a16272
description: Quando si imposta i criteri di sicurezza degli allegati degli strumenti di analisi, si sceglie recapito dinamico per evitare ritardi messaggio e consentire agli utenti di visualizzare in anteprima degli allegati che vengono analizzati.
ms.openlocfilehash: 23ef316ed35b89ef1fad5e9639dd10e76036a4f3
ms.sourcegitcommit: 82fd4c85b952819157fbb13175c7b2dbbdff510f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/13/2018
ms.locfileid: "23965243"
---
# <a name="dynamic-delivery-and-previewing-with-office-365-atp-safe-attachments"></a><span data-ttu-id="54b2e-103">Recapito dinamico e l'anteprima allegati sicuri di Office 365 degli strumenti di analisi di</span><span class="sxs-lookup"><span data-stu-id="54b2e-103">Dynamic delivery and previewing with Office 365 ATP Safe Attachments</span></span>

<span data-ttu-id="54b2e-p101">Recapito dinamico è un'opzione che è possibile selezionare per. In questo articolo per informazioni su Recapito dinamico e funzionalità di anteprima degli allegati in [Strumenti di analisi allegati attendibili in Office 365](atp-safe-attachments.md).</span><span class="sxs-lookup"><span data-stu-id="54b2e-p101">Dynamic delivery is an option that can be selected for . Read this article to learn about dynamic delivery and attachment preview capabilities in [ATP Safe Attachments in Office 365](atp-safe-attachments.md).</span></span>
  
## <a name="how-dynamic-delivery-works"></a><span data-ttu-id="54b2e-106">Works recapito dinamico</span><span class="sxs-lookup"><span data-stu-id="54b2e-106">How dynamic delivery works</span></span>

<span data-ttu-id="54b2e-p102">Quando si [Imposta i criteri degli strumenti di analisi provvisoria allegati in Office 365](set-up-atp-safe-attachments-policies.md), è possibile scegliere tra diverse opzioni, ad esempio **blocco**, **sostituire**e **Recapito dinamico**. A seconda della modalità di configurazione dei criteri, i destinatari di posta elettronica possono verificarsi un ritardo secondario di recapito della posta elettronica quando gli allegati vengono analizzati. Per evitare ritardi messaggio, scegliere **Recapito dinamico**.</span><span class="sxs-lookup"><span data-stu-id="54b2e-p102">When you [set up ATP Safe Attachments policies in Office 365](set-up-atp-safe-attachments-policies.md), you can choose from several options, such as **Block**, **Replace**, and **Dynamic Delivery**. Depending on how your policies are configured, email recipients can experience a minor delay in email delivery while their attachments are scanned. To avoid message delays, choose **Dynamic Delivery**.</span></span>
  
<span data-ttu-id="54b2e-p103">L'opzione di distribuzione dinamico Elimina i ritardi di posta elettronica mediante l'invio di corpo di un messaggio di posta elettronica con un segnaposto per tutti gli allegati di posta elettronica. Il segnaposto rimane fino a quando l'allegato è analizzato da [Strumenti di analisi allegati attendibili in Office 365](atp-safe-attachments.md). Destinatari di posta elettronica possono leggere e rispondere ai propri messaggi di posta elettronica subito, sapere che vengono analizzati gli allegati.</span><span class="sxs-lookup"><span data-stu-id="54b2e-p103">The dynamic delivery option eliminates email delays by sending the body of an email message through with a placeholder for each email attachment. The placeholder remains until the attachment is scanned by [ATP Safe Attachments in Office 365](atp-safe-attachments.md). Email recipients can read and respond to their email messages right away, knowing that their attachments are being analyzed.</span></span>
  
<span data-ttu-id="54b2e-p104">La maggior parte dei documenti PDF e l'ufficio documenti possono essere visualizzati in anteprima in modalità provvisoria durante l'analisi degli strumenti di analisi. Se un allegato non è compatibile con il Visualizzatore di recapito dinamico, segnaposto allegato viene visualizzato dai destinatari di posta elettronica fino a completa la scansione degli allegati sicuri degli strumenti di analisi.</span><span class="sxs-lookup"><span data-stu-id="54b2e-p104">Most PDFs and Office documents can be previewed in safe mode while ATP scanning is underway. If an attachment is not compatible with the dynamic delivery previewer, email recipients see the attachment placeholder until ATP Safe Attachments scanning is complete.</span></span>
  
<span data-ttu-id="54b2e-p105">Che tutti gli allegati sia selezionato, viene automaticamente ricollegato al messaggio di posta elettronica originale. Se un allegato è determinato da dannoso, viene inviata alla quarantena, in cui una persona nel team di protezione dell'organizzazione (ad esempio un amministratore di protezione o di amministratore globale di Office 365) possibile [gestire i messaggi in quarantena in Office 365](manage-quarantined-messages-and-files.md).</span><span class="sxs-lookup"><span data-stu-id="54b2e-p105">As each attachment is cleared, it is automatically reattached to the original email message. If an attachment is determined to be malicious, it is sent to quarantine, where someone on your organization's security team (such as an Office 365 global administrator or security administrator) can [manage quarantined messages in Office 365](manage-quarantined-messages-and-files.md).</span></span>
  
## <a name="what-happens-when-someone-forwards-an-email-that-contains-an-attachment"></a><span data-ttu-id="54b2e-117">Cosa succede quando un utente inoltra un messaggio di posta elettronica contenente un allegato.</span><span class="sxs-lookup"><span data-stu-id="54b2e-117">What happens when someone forwards an email that contains an attachment?</span></span>

<span data-ttu-id="54b2e-p106">Si supponga che un'organizzazione di recapito dinamico di utilizzare i [criteri gli allegati sicuri degli strumenti di analisi](set-up-atp-safe-attachments-policies.md)e un utente riceve un messaggio di posta elettronica contenente un allegato. A questo punto si supponga che tale persona deve inoltrare il messaggio di posta elettronica a un utente. Che succede? Dipende dal fatto altri destinatari sono inclusi nei criteri gli allegati sicuri degli strumenti di analisi.</span><span class="sxs-lookup"><span data-stu-id="54b2e-p106">Suppose that an organization is using dynamic delivery for their [ATP Safe Attachments policy](set-up-atp-safe-attachments-policies.md), and someone receives an email that contains an attachment. Now suppose that person is about to forward the email message to someone else. What happens? It depends on whether the additional recipients are included in ATP Safe Attachments policies.</span></span>
  
- <span data-ttu-id="54b2e-122">Se un destinatario è occupato da un criterio di allegati sicuri degli strumenti di analisi utilizzando l'opzione di distribuzione dinamico, il destinatario vede il segnaposto con la possibilità di visualizzare in anteprima i file compatibili.</span><span class="sxs-lookup"><span data-stu-id="54b2e-122">If a recipient is covered by an ATP Safe Attachments policy using the dynamic delivery option, then the recipient sees the placeholder, with the ability to preview compatible files.</span></span>
    
- <span data-ttu-id="54b2e-123">Se un destinatario non è occupato da un criterio di allegati sicuri degli strumenti di analisi, quindi il messaggio di posta elettronica e allegati verranno passate, senza allegati sicuri degli strumenti di analisi analisi o placeholders allegato.</span><span class="sxs-lookup"><span data-stu-id="54b2e-123">If a recipient is not covered by an ATP Safe Attachments policy, then the email and attachment will go through, without ATP Safe Attachments scanning or attachment placeholders.</span></span>
    
## <a name="whats-required-for-dynamic-delivery-to-work"></a><span data-ttu-id="54b2e-124">Requisiti per il recapito dinamico funziona?</span><span class="sxs-lookup"><span data-stu-id="54b2e-124">What's required for dynamic delivery to work?</span></span>

- <span data-ttu-id="54b2e-125">L'organizzazione deve disporre di [Protezione avanzate da minacce di Office 365](office-365-atp.md)</span><span class="sxs-lookup"><span data-stu-id="54b2e-125">Your organization must have [Office 365 Advanced Threat Protection](office-365-atp.md)</span></span>
    
- <span data-ttu-id="54b2e-126">È necessario definire i criteri per gli allegati sicuri degli strumenti di analisi utilizzando l'opzione di distribuzione dinamico (vedere [Set up criteri degli strumenti di analisi allegati attendibili in Office 365](set-up-atp-safe-attachments-policies.md))</span><span class="sxs-lookup"><span data-stu-id="54b2e-126">Policies must be defined for ATP Safe Attachments using the dynamic delivery option (See [Set up ATP Safe Attachments policies in Office 365](set-up-atp-safe-attachments-policies.md))</span></span>
    
- <span data-ttu-id="54b2e-127">Messaggio di posta elettronica dell'organizzazione deve essere ospitato in Office 365</span><span class="sxs-lookup"><span data-stu-id="54b2e-127">Your organization's email must be hosted in Office 365</span></span>
    
## <a name="are-there-scenarios-for-which-dynamic-delivery-is-not-available"></a><span data-ttu-id="54b2e-128">Esistono scenari per i quali non è disponibile il recapito dinamico?</span><span class="sxs-lookup"><span data-stu-id="54b2e-128">Are there scenarios for which dynamic delivery is not available?</span></span>

<span data-ttu-id="54b2e-p107">Esistono alcuni scenari in cui non è supportato recapito dinamico. Questi sono i seguenti:</span><span class="sxs-lookup"><span data-stu-id="54b2e-p107">There are certain scenarios in which dynamic delivery is not supported. These include the following:</span></span>
  
- <span data-ttu-id="54b2e-131">Messaggi di posta elettronica per le cartelle pubbliche</span><span class="sxs-lookup"><span data-stu-id="54b2e-131">Email messages that are in public folders</span></span>
    
- <span data-ttu-id="54b2e-132">Messaggi di posta elettronica vengono indirizzati fuori e quindi nuovamente nella cassetta postale dell'utente tramite regole personalizzate</span><span class="sxs-lookup"><span data-stu-id="54b2e-132">Email messages that are routed out of and then back into the user's mailbox using custom rules</span></span>
    
- <span data-ttu-id="54b2e-133">I messaggi che vengono spostati (automaticamente o manualmente) all'esterno della cassetta postale ospitata e in altre posizioni, tra cui archiviare le cartelle</span><span class="sxs-lookup"><span data-stu-id="54b2e-133">Messages that are moved (automatically or manually) out of the hosted mailbox and into other locations, including archive folders</span></span>
    
- <span data-ttu-id="54b2e-134">Messaggi che vengono eliminati</span><span class="sxs-lookup"><span data-stu-id="54b2e-134">Messages that are deleted</span></span>
    
- <span data-ttu-id="54b2e-135">Cartella di ricerca delle cassette postali dell'utente che si trova nello stato di errore</span><span class="sxs-lookup"><span data-stu-id="54b2e-135">A user's mailbox search folder that is in an error state</span></span>
    
- <span data-ttu-id="54b2e-p108">Ambienti in cui un amministratore di Exchange Online è abilitato Exclaimer. (Vedere [i messaggi con allegati non vengono recapitati quando vengono utilizzati degli strumenti di analisi dinamica recapito ed Exclaimer](https://support.microsoft.com/help/4014438/messages-with-attachments-are-not-delivered-when-atp-dynamic-delivery))</span><span class="sxs-lookup"><span data-stu-id="54b2e-p108">Environments in which an Exchange Online admin has enabled Exclaimer. (See [Messages with attachments are not delivered when ATP Dynamic Delivery and Exclaimer are used](https://support.microsoft.com/help/4014438/messages-with-attachments-are-not-delivered-when-atp-dynamic-delivery))</span></span>

- <span data-ttu-id="54b2e-138">Messaggi crittografati con Secure/Multipurpose Internet Mail Extensions ([S/MIME](s-mime-for-message-signing-and-encryption.md))</span><span class="sxs-lookup"><span data-stu-id="54b2e-138">Messages encrypted with Secure/Multipurpose Internet Mail Extensions ([S/MIME](s-mime-for-message-signing-and-encryption.md))</span></span>
    
## <a name="related-topics"></a><span data-ttu-id="54b2e-139">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="54b2e-139">Related topics</span></span>

[<span data-ttu-id="54b2e-140">Office 365 Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="54b2e-140">Office 365 Advanced Threat Protection</span></span>](office-365-atp.md)
  
[<span data-ttu-id="54b2e-141">Allegati degli strumenti di analisi sicuro in Office 365</span><span class="sxs-lookup"><span data-stu-id="54b2e-141">ATP Safe Attachments in Office 365</span></span>](atp-safe-attachments.md)
  
[<span data-ttu-id="54b2e-142">Impostare i criteri degli strumenti di analisi allegati attendibili in Office 365</span><span class="sxs-lookup"><span data-stu-id="54b2e-142">Set up ATP Safe Attachments policies in Office 365</span></span>](set-up-atp-safe-attachments-policies.md)
  
[<span data-ttu-id="54b2e-143">Collegamenti degli strumenti di analisi sicuro in Office 365</span><span class="sxs-lookup"><span data-stu-id="54b2e-143">ATP Safe Links in Office 365</span></span>](atp-safe-links.md)

[<span data-ttu-id="54b2e-144">Le autorizzazioni di sicurezza di Office 365 &amp; centro conformità</span><span class="sxs-lookup"><span data-stu-id="54b2e-144">Permissions in the Office 365 Security &amp; Compliance Center</span></span>](permissions-in-the-security-and-compliance-center.md)
  

