---
title: Recapito dinamico e l'anteprima allegati sicuri di Office 365 degli strumenti di analisi di
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 01/08/2019
ms.audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: f16c9928-8e3d-4219-b994-271dc9a16272
ms.collection:
- M365-security-compliance
description: Quando si imposta i criteri di sicurezza degli allegati degli strumenti di analisi, si sceglie recapito dinamico per evitare ritardi messaggio e consentire agli utenti di visualizzare in anteprima degli allegati che vengono analizzati.
ms.openlocfilehash: ae027986cf5114bd024c679a59975d1e4be52d32
ms.sourcegitcommit: efccf5b4f22d34a9674bc55ebf3d88bc8bda2972
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/14/2019
ms.locfileid: "29995147"
---
# <a name="dynamic-delivery-and-previewing-with-office-365-atp-safe-attachments"></a><span data-ttu-id="d3c66-103">Recapito dinamico e l'anteprima allegati sicuri di Office 365 degli strumenti di analisi di</span><span class="sxs-lookup"><span data-stu-id="d3c66-103">Dynamic Delivery and previewing with Office 365 ATP Safe Attachments</span></span>

<span data-ttu-id="d3c66-p101">**Riepilogo**: recapito dinamico è un'opzione che è possibile selezionare gli allegati [sicuri degli strumenti di analisi](atp-safe-attachments.md). In questo articolo per informazioni su recapito dinamici e funzionalità di anteprima degli allegati in [Strumenti di analisi allegati attendibili in Office 365](atp-safe-attachments.md).</span><span class="sxs-lookup"><span data-stu-id="d3c66-p101">**Summary**: Dynamic Delivery is an option that can be selected for [ATP Safe Attachments](atp-safe-attachments.md). Read this article to learn about Dynamic Delivery and attachment preview capabilities in [ATP Safe Attachments in Office 365](atp-safe-attachments.md).</span></span>

<span data-ttu-id="d3c66-p102">Quando [vengono impostati i criteri degli strumenti di analisi gli allegati sicuri](set-up-atp-safe-attachments-policies.md) per l'organizzazione, sono disponibili diverse opzioni per la modalità di Gestione allegati di posta elettronica. Sono inclusi **blocco**, **sostituire**e **Recapito dinamico**. A seconda della configurazione delle criteri gli allegati sicuri degli strumenti di analisi, i destinatari di posta elettronica potrebbero verificarsi un ritardo secondario di recapito della posta elettronica quando gli allegati vengono analizzati. Per evitare ritardi messaggio, scegliere **Recapito dinamico**.</span><span class="sxs-lookup"><span data-stu-id="d3c66-p102">When [ATP Safe Attachments policies are set up](set-up-atp-safe-attachments-policies.md) for your organization, there are several options for how email attachments are handled. These include **Block**, **Replace**, and **Dynamic Delivery**. Depending on how ATP Safe Attachments policies are configured, email recipients might experience a minor delay in email delivery while their attachments are scanned. To avoid message delays, choose **Dynamic Delivery**.</span></span>
  
## <a name="how-dynamic-delivery-works"></a><span data-ttu-id="d3c66-110">Funzionamento del recapito dinamico</span><span class="sxs-lookup"><span data-stu-id="d3c66-110">How Dynamic Delivery works</span></span>
  
<span data-ttu-id="d3c66-p103">Recapito dinamico Elimina i ritardi di posta elettronica mediante l'invio di corpo di un messaggio di posta elettronica al destinatario con un segnaposto per tutti gli allegati di posta elettronica. Segnaposto rimane fino a quando una copia dell'allegato viene analizzata ritenuta attendibili per [Gli allegati sicuri degli strumenti di analisi](atp-safe-attachments.md).</span><span class="sxs-lookup"><span data-stu-id="d3c66-p103">Dynamic Delivery eliminates email delays by sending the body of an email message through to the recipient with a placeholder for each email attachment. The placeholder remains until a copy of the attachment is scanned and determined to be safe by [ATP Safe Attachments](atp-safe-attachments.md).</span></span> 

- <span data-ttu-id="d3c66-113">Quando sono deselezionato tutti gli allegati, risulta disponibile per aprire o scaricare.</span><span class="sxs-lookup"><span data-stu-id="d3c66-113">As each attachment is cleared, it is available to open or download.</span></span> 

- <span data-ttu-id="d3c66-114">Se un allegato è determinato da dannoso, viene inviata alla quarantena, in cui una persona nel team di protezione dell'organizzazione (ad esempio un amministratore di protezione o di amministratore globale di Office 365) possibile [gestire i messaggi in quarantena in Office 365](manage-quarantined-messages-and-files.md).</span><span class="sxs-lookup"><span data-stu-id="d3c66-114">If an attachment is determined to be malicious, it is sent to quarantine, where someone on your organization's security team (such as an Office 365 global administrator or security administrator) can [manage quarantined messages in Office 365](manage-quarantined-messages-and-files.md).</span></span>

<span data-ttu-id="d3c66-p104">La maggior parte dei documenti PDF e l'ufficio documenti possono essere visualizzati in anteprima in modalità provvisoria durante l'analisi degli strumenti di analisi. Se un allegato non è compatibile con il Visualizzatore di recapito dinamico, un segnaposto allegato viene visualizzato dai destinatari di posta elettronica fino a completa la scansione degli allegati sicuri degli strumenti di analisi.</span><span class="sxs-lookup"><span data-stu-id="d3c66-p104">Most PDFs and Office documents can be previewed in safe mode while ATP scanning is underway. If an attachment is not compatible with the Dynamic Delivery previewer, email recipients see an attachment placeholder until ATP Safe Attachments scanning is complete.</span></span>

> [!TIP]
> <span data-ttu-id="d3c66-117">Se si utilizza un dispositivo mobile e file PDF non eseguono il rendering nell'anteprima dinamica recapito inizialmente, tentare l'accesso a Office 365 con browser per dispositivi mobili.</span><span class="sxs-lookup"><span data-stu-id="d3c66-117">If you're using a mobile device, and PDFs are not rendering in Dynamic Delivery previewer at first, try signing into Office 365 using your mobile browser.</span></span>

<span data-ttu-id="d3c66-118">Con recapito dinamico, persone possono leggere e rispondere ai propri messaggi di posta elettronica immediatamente, mentre gli allegati vengono analizzati.</span><span class="sxs-lookup"><span data-stu-id="d3c66-118">With Dynamic Delivery, people can read and respond to their email messages right away, while their attachments are being analyzed.</span></span> 

<span data-ttu-id="d3c66-p105">Gli allegati sicuri degli strumenti di analisi analisi abbia effettuare nella stessa area in cui si trovano i dati di Office 365. Per ulteriori informazioni sulle aree di centro dati, vedere [dove sono i dati si trova?](https://products.office.com/where-is-your-data-located?geo=All)</span><span class="sxs-lookup"><span data-stu-id="d3c66-p105">ATP Safe Attachments scanning takes place in the same region where your Office 365 data resides. For more information about data center geography, see [Where is your data located?](https://products.office.com/where-is-your-data-located?geo=All)</span></span> 
  
## <a name="what-happens-when-someone-forwards-an-email-that-contains-an-attachment"></a><span data-ttu-id="d3c66-121">Cosa succede quando un utente inoltra un messaggio di posta elettronica contenente un allegato.</span><span class="sxs-lookup"><span data-stu-id="d3c66-121">What happens when someone forwards an email that contains an attachment?</span></span>

<span data-ttu-id="d3c66-p106">Si supponga che un'organizzazione di recapito dinamico di utilizzare i [criteri gli allegati sicuri degli strumenti di analisi](set-up-atp-safe-attachments-policies.md)e un utente riceve un messaggio di posta elettronica contenente un allegato. A questo punto si supponga che tale persona inoltra il messaggio di posta elettronica a un utente. Che succede? Dipende dal fatto altri destinatari sono inclusi nei criteri gli allegati sicuri degli strumenti di analisi.</span><span class="sxs-lookup"><span data-stu-id="d3c66-p106">Suppose that an organization is using Dynamic Delivery for their [ATP Safe Attachments policy](set-up-atp-safe-attachments-policies.md), and someone receives an email that contains an attachment. Now suppose that person forwards the email message to someone else. What happens? It depends on whether the additional recipients are included in ATP Safe Attachments policies.</span></span>
  
- <span data-ttu-id="d3c66-126">Se un destinatario è occupato da un criterio di allegati sicuri degli strumenti di analisi utilizzando l'opzione di distribuzione dinamico, il destinatario vede il segnaposto con la possibilità di visualizzare in anteprima i file compatibili.</span><span class="sxs-lookup"><span data-stu-id="d3c66-126">If a recipient is covered by an ATP Safe Attachments policy using the Dynamic Delivery option, then the recipient sees the placeholder, with the ability to preview compatible files.</span></span>
    
- <span data-ttu-id="d3c66-127">Se un destinatario non è occupato da un criterio di allegati sicuri degli strumenti di analisi, quindi il messaggio di posta elettronica e allegati verranno passate, senza allegati sicuri degli strumenti di analisi analisi o placeholders allegato.</span><span class="sxs-lookup"><span data-stu-id="d3c66-127">If a recipient is not covered by an ATP Safe Attachments policy, then the email and attachment will go through, without ATP Safe Attachments scanning or attachment placeholders.</span></span>
    
## <a name="whats-required-for-dynamic-delivery-to-work"></a><span data-ttu-id="d3c66-128">Requisiti per il recapito dinamica funziona?</span><span class="sxs-lookup"><span data-stu-id="d3c66-128">What's required for Dynamic Delivery to work?</span></span>

- <span data-ttu-id="d3c66-129">L'organizzazione deve disporre di [Protezione avanzate da minacce di Office 365](office-365-atp.md)</span><span class="sxs-lookup"><span data-stu-id="d3c66-129">Your organization must have [Office 365 Advanced Threat Protection](office-365-atp.md)</span></span>
    
- <span data-ttu-id="d3c66-130">È necessario definire i criteri per gli allegati sicuri degli strumenti di analisi utilizzando l'opzione di distribuzione dinamico (vedere [Set up criteri degli strumenti di analisi allegati attendibili in Office 365](set-up-atp-safe-attachments-policies.md))</span><span class="sxs-lookup"><span data-stu-id="d3c66-130">Policies must be defined for ATP Safe Attachments using the Dynamic Delivery option (See [Set up ATP Safe Attachments policies in Office 365](set-up-atp-safe-attachments-policies.md))</span></span>
    
- <span data-ttu-id="d3c66-131">Messaggio di posta elettronica dell'organizzazione deve essere ospitato in Office 365</span><span class="sxs-lookup"><span data-stu-id="d3c66-131">Your organization's email must be hosted in Office 365</span></span>
    
## <a name="are-there-scenarios-for-which-dynamic-delivery-is-not-available"></a><span data-ttu-id="d3c66-132">Esistono scenari per i quali non è disponibile recapito dinamico?</span><span class="sxs-lookup"><span data-stu-id="d3c66-132">Are there scenarios for which Dynamic Delivery is not available?</span></span>

<span data-ttu-id="d3c66-p107">Esistono alcuni scenari in cui non è supportato recapito dinamico. Questi sono i seguenti:</span><span class="sxs-lookup"><span data-stu-id="d3c66-p107">There are certain scenarios in which Dynamic Delivery is not supported. These include the following:</span></span>
  
- <span data-ttu-id="d3c66-135">Messaggi di posta elettronica per le cartelle pubbliche</span><span class="sxs-lookup"><span data-stu-id="d3c66-135">Email messages that are in public folders</span></span>
    
- <span data-ttu-id="d3c66-136">Messaggi di posta elettronica vengono indirizzati fuori e quindi nuovamente nella cassetta postale dell'utente tramite regole personalizzate</span><span class="sxs-lookup"><span data-stu-id="d3c66-136">Email messages that are routed out of and then back into the user's mailbox using custom rules</span></span>
    
- <span data-ttu-id="d3c66-137">Messaggi di posta elettronica vengono spostati (automaticamente o manualmente) all'esterno della cassetta postale ospitata e in altre posizioni, tra cui archiviare le cartelle</span><span class="sxs-lookup"><span data-stu-id="d3c66-137">Email messages that are moved (automatically or manually) out of the hosted mailbox and into other locations, including archive folders</span></span>
    
- <span data-ttu-id="d3c66-138">Messaggi di posta elettronica vengono eliminati</span><span class="sxs-lookup"><span data-stu-id="d3c66-138">Email messages that are deleted</span></span>
    
- <span data-ttu-id="d3c66-139">Cartella di ricerca delle cassette postali dell'utente che si trova nello stato di errore</span><span class="sxs-lookup"><span data-stu-id="d3c66-139">A user's mailbox search folder that is in an error state</span></span>
    
- <span data-ttu-id="d3c66-p108">Ambienti in cui un amministratore di Exchange Online è abilitato Exclaimer. Per risolvere questo problema, vedere [i messaggi con allegati non vengono recapitati quando vengono utilizzati degli strumenti di analisi dinamica recapito ed Exclaimer](https://support.microsoft.com/help/4014438/messages-with-attachments-are-not-delivered-when-atp-dynamic-delivery)</span><span class="sxs-lookup"><span data-stu-id="d3c66-p108">Environments in which an Exchange Online admin has enabled Exclaimer. To resolve this, see [Messages with attachments are not delivered when ATP Dynamic Delivery and Exclaimer are used](https://support.microsoft.com/help/4014438/messages-with-attachments-are-not-delivered-when-atp-dynamic-delivery)</span></span>

- <span data-ttu-id="d3c66-142">Messaggi crittografati con [Secure/Multipurpose Internet Mail Extensions (S/MIME)](s-mime-for-message-signing-and-encryption.md))</span><span class="sxs-lookup"><span data-stu-id="d3c66-142">Messages encrypted with [Secure/Multipurpose Internet Mail Extensions (S/MIME)](s-mime-for-message-signing-and-encryption.md))</span></span>

