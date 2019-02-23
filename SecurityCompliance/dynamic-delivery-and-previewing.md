---
title: ReCapito dinamico e anteprima con allegati sicuri ATP di Office 365
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 01/08/2019
ms.audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: f16c9928-8e3d-4219-b994-271dc9a16272
ms.collection:
- M365-security-compliance
description: Quando si configurano i criteri per gli allegati sicuri di ATP, è possibile scegliere reCapito dinamico per evitare ritardi nei messaggi e consentire agli utenti di visualizzare in anteprima gli allegati analizzati.
ms.openlocfilehash: 1fb221d28a4089db8a4278903107c610d6825f5e
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/23/2019
ms.locfileid: "30218396"
---
# <a name="dynamic-delivery-and-previewing-with-office-365-atp-safe-attachments"></a><span data-ttu-id="280dc-103">ReCapito dinamico e anteprima con allegati sicuri ATP di Office 365</span><span class="sxs-lookup"><span data-stu-id="280dc-103">Dynamic Delivery and previewing with Office 365 ATP Safe Attachments</span></span>

<span data-ttu-id="280dc-p101">**Riepilogo**: il recapito dinamico è un'opzione che può essere selezionata per gli [allegati sicuri di ATP](atp-safe-attachments.md). Leggere questo articolo per informazioni sulle funzionalità di anteprima degli allegati e il reCapito dinamico in [ATP Safe Attachments in Office 365](atp-safe-attachments.md).</span><span class="sxs-lookup"><span data-stu-id="280dc-p101">**Summary**: Dynamic Delivery is an option that can be selected for [ATP Safe Attachments](atp-safe-attachments.md). Read this article to learn about Dynamic Delivery and attachment preview capabilities in [ATP Safe Attachments in Office 365](atp-safe-attachments.md).</span></span>

<span data-ttu-id="280dc-p102">Quando i [criteri degli allegati sicuri di ATP sono](set-up-atp-safe-attachments-policies.md) configurati per l'organizzazione, sono disponibili diverse opzioni per la gestione degli allegati di posta elettronica. Sono inclusi **blocco**, **sostituzione**e **recapito dinamico**. A seconda del modo in cui vengono configurati i criteri per gli allegati sicuri di ATP, i destinatari di posta elettronica potrebbero subire un ritardo durante l'analisi dei messaggi. Per evitare ritardi nei messaggi, scegliere **recapito dinamico**.</span><span class="sxs-lookup"><span data-stu-id="280dc-p102">When [ATP Safe Attachments policies are set up](set-up-atp-safe-attachments-policies.md) for your organization, there are several options for how email attachments are handled. These include **Block**, **Replace**, and **Dynamic Delivery**. Depending on how ATP Safe Attachments policies are configured, email recipients might experience a minor delay in email delivery while their attachments are scanned. To avoid message delays, choose **Dynamic Delivery**.</span></span>
  
## <a name="how-dynamic-delivery-works"></a><span data-ttu-id="280dc-110">Funzionamento del reCapito dinamico</span><span class="sxs-lookup"><span data-stu-id="280dc-110">How Dynamic Delivery works</span></span>
  
<span data-ttu-id="280dc-p103">Il reCapito dinamico elimina i ritardi della posta elettronica inviando il corpo di un messaggio di posta elettronica al destinatario con un segnaposto per ogni allegato di posta elettronica. Il segnaposto rimane invariato fino a quando una copia dell'allegato viene analizzata e determinata a essere sicura dagli [allegati sicuri di ATP](atp-safe-attachments.md).</span><span class="sxs-lookup"><span data-stu-id="280dc-p103">Dynamic Delivery eliminates email delays by sending the body of an email message through to the recipient with a placeholder for each email attachment. The placeholder remains until a copy of the attachment is scanned and determined to be safe by [ATP Safe Attachments](atp-safe-attachments.md).</span></span> 

- <span data-ttu-id="280dc-113">Poiché ogni allegato è deselezionato, è disponibile per l'apertura o il download.</span><span class="sxs-lookup"><span data-stu-id="280dc-113">As each attachment is cleared, it is available to open or download.</span></span> 

- <span data-ttu-id="280dc-114">Se un allegato è determinato come dannoso, viene inviato alla quarantena, in cui un utente del team di sicurezza dell'organizzazione (ad esempio un amministratore globale di Office 365 o un amministratore della sicurezza) può [gestire i messaggi in quarantena in office 365](manage-quarantined-messages-and-files.md).</span><span class="sxs-lookup"><span data-stu-id="280dc-114">If an attachment is determined to be malicious, it is sent to quarantine, where someone on your organization's security team (such as an Office 365 global administrator or security administrator) can [manage quarantined messages in Office 365](manage-quarantined-messages-and-files.md).</span></span>

<span data-ttu-id="280dc-p104">La maggior parte dei file PDF e i documenti di Office possono essere visualizzati in anteprima in modalità provvisoria mentre è in corso l'analisi ATP. Se un allegato non è compatibile con l'anteprima di reCapito dinamico, i destinatari di posta elettronica visualizzano un segnaposto allegato finché non è stato completato l'analisi degli allegati sicuri di ATP.</span><span class="sxs-lookup"><span data-stu-id="280dc-p104">Most PDFs and Office documents can be previewed in safe mode while ATP scanning is underway. If an attachment is not compatible with the Dynamic Delivery previewer, email recipients see an attachment placeholder until ATP Safe Attachments scanning is complete.</span></span>

> [!TIP]
> <span data-ttu-id="280dc-117">Se si utilizza un dispositivo mobile e i file PDF non vengono visualizzati in anteprima per il reCapito dinamico, provare a eseguire l'accesso a Office 365 utilizzando il browser per dispositivi mobili.</span><span class="sxs-lookup"><span data-stu-id="280dc-117">If you're using a mobile device, and PDFs are not rendering in Dynamic Delivery previewer at first, try signing into Office 365 using your mobile browser.</span></span>

<span data-ttu-id="280dc-118">Con il reCapito dinamico, gli utenti possono leggere e rispondere immediatamente ai propri messaggi di posta elettronica, mentre gli allegati vengono analizzati.</span><span class="sxs-lookup"><span data-stu-id="280dc-118">With Dynamic Delivery, people can read and respond to their email messages right away, while their attachments are being analyzed.</span></span> 

<span data-ttu-id="280dc-p105">L'analisi degli allegati sicuri ATP si verifica nella stessa area in cui si trovano i dati di Office 365. Per ulteriori informazioni sulla geografia del Data Center, vedere [dove si trovano i dati?](https://products.office.com/where-is-your-data-located?geo=All)</span><span class="sxs-lookup"><span data-stu-id="280dc-p105">ATP Safe Attachments scanning takes place in the same region where your Office 365 data resides. For more information about data center geography, see [Where is your data located?](https://products.office.com/where-is-your-data-located?geo=All)</span></span> 
  
## <a name="what-happens-when-someone-forwards-an-email-that-contains-an-attachment"></a><span data-ttu-id="280dc-121">Cosa succede quando qualcuno inoltra un messaggio di posta elettronica che contiene un allegato?</span><span class="sxs-lookup"><span data-stu-id="280dc-121">What happens when someone forwards an email that contains an attachment?</span></span>

<span data-ttu-id="280dc-p106">Si supponga che un'organizzazione stia utilizzando il reCapito dinamico per il [criterio degli allegati sicuri ATP](set-up-atp-safe-attachments-policies.md)e che qualcuno riceva un messaggio di posta elettronica contenente un allegato. Ora supponiamo che la persona inoltra il messaggio di posta elettronica a un altro utente. Che succede? Dipende dal fatto che i destinatari aggiuntivi siano inclusi nei criteri allegati sicuri di ATP.</span><span class="sxs-lookup"><span data-stu-id="280dc-p106">Suppose that an organization is using Dynamic Delivery for their [ATP Safe Attachments policy](set-up-atp-safe-attachments-policies.md), and someone receives an email that contains an attachment. Now suppose that person forwards the email message to someone else. What happens? It depends on whether the additional recipients are included in ATP Safe Attachments policies.</span></span>
  
- <span data-ttu-id="280dc-126">Se un destinatario è incluso in un criterio di allegati sicuri ATP utilizzando l'opzione di reCapito dinamico, il destinatario Visualizza il segnaposto, con la possibilità di visualizzare in anteprima i file compatibili.</span><span class="sxs-lookup"><span data-stu-id="280dc-126">If a recipient is covered by an ATP Safe Attachments policy using the Dynamic Delivery option, then the recipient sees the placeholder, with the ability to preview compatible files.</span></span>
    
- <span data-ttu-id="280dc-127">Se un destinatario non è incluso in un criterio per gli allegati sicuri di ATP, il messaggio di posta elettronica e l'allegato passeranno, senza l'analisi degli allegati sicuri di ATP o i segnaposto allegati.</span><span class="sxs-lookup"><span data-stu-id="280dc-127">If a recipient is not covered by an ATP Safe Attachments policy, then the email and attachment will go through, without ATP Safe Attachments scanning or attachment placeholders.</span></span>
    
## <a name="whats-required-for-dynamic-delivery-to-work"></a><span data-ttu-id="280dc-128">Cosa è necessario per il funzionamento del reCapito dinamico?</span><span class="sxs-lookup"><span data-stu-id="280dc-128">What's required for Dynamic Delivery to work?</span></span>

- <span data-ttu-id="280dc-129">L'organizzazione deve disporre di [Office 365 Advanced Threat Protection](office-365-atp.md)</span><span class="sxs-lookup"><span data-stu-id="280dc-129">Your organization must have [Office 365 Advanced Threat Protection](office-365-atp.md)</span></span>
    
- <span data-ttu-id="280dc-130">I criteri devono essere definiti per gli allegati sicuri di ATP utilizzando l'opzione di reCapito dinamico (vedere [configurare i criteri degli allegati sicuri di ATP in Office 365](set-up-atp-safe-attachments-policies.md))</span><span class="sxs-lookup"><span data-stu-id="280dc-130">Policies must be defined for ATP Safe Attachments using the Dynamic Delivery option (See [Set up ATP Safe Attachments policies in Office 365](set-up-atp-safe-attachments-policies.md))</span></span>
    
- <span data-ttu-id="280dc-131">La posta elettronica dell'organizzazione deve essere ospitata in Office 365</span><span class="sxs-lookup"><span data-stu-id="280dc-131">Your organization's email must be hosted in Office 365</span></span>
    
## <a name="are-there-scenarios-for-which-dynamic-delivery-is-not-available"></a><span data-ttu-id="280dc-132">Esistono scenari per i quali il reCapito dinamico non è disponibile?</span><span class="sxs-lookup"><span data-stu-id="280dc-132">Are there scenarios for which Dynamic Delivery is not available?</span></span>

<span data-ttu-id="280dc-p107">Esistono alcuni scenari in cui il reCapito dinamico non è supportato. Sono inclusi i seguenti:</span><span class="sxs-lookup"><span data-stu-id="280dc-p107">There are certain scenarios in which Dynamic Delivery is not supported. These include the following:</span></span>
  
- <span data-ttu-id="280dc-135">Messaggi di posta elettronica presenti nelle cartelle pubbliche</span><span class="sxs-lookup"><span data-stu-id="280dc-135">Email messages that are in public folders</span></span>
    
- <span data-ttu-id="280dc-136">Messaggi di posta elettronica instradati fuori e quindi di nuovo nella cassetta postale dell'utente utilizzando regole personalizzate</span><span class="sxs-lookup"><span data-stu-id="280dc-136">Email messages that are routed out of and then back into the user's mailbox using custom rules</span></span>
    
- <span data-ttu-id="280dc-137">Messaggi di posta elettronica spostati (automaticamente o manualmente) dalla cassetta postale ospitata e in altre posizioni, incluse le cartelle di archiviazione</span><span class="sxs-lookup"><span data-stu-id="280dc-137">Email messages that are moved (automatically or manually) out of the hosted mailbox and into other locations, including archive folders</span></span>
    
- <span data-ttu-id="280dc-138">Messaggi di posta elettronica eliminati</span><span class="sxs-lookup"><span data-stu-id="280dc-138">Email messages that are deleted</span></span>
    
- <span data-ttu-id="280dc-139">Cartella di ricerca della cassetta postale di un utente che si trova in uno stato di errore</span><span class="sxs-lookup"><span data-stu-id="280dc-139">A user's mailbox search folder that is in an error state</span></span>
    
- <span data-ttu-id="280dc-p108">Ambienti in cui un amministratore di Exchange Online ha abilitato l'utente esclamativo. Per risolvere il caso, vedere [i messaggi con allegati non vengono recapitati quando viene utilizzato il recapito dinamico e l'esclamaTORE ATP](https://support.microsoft.com/help/4014438/messages-with-attachments-are-not-delivered-when-atp-dynamic-delivery)</span><span class="sxs-lookup"><span data-stu-id="280dc-p108">Environments in which an Exchange Online admin has enabled Exclaimer. To resolve this, see [Messages with attachments are not delivered when ATP Dynamic Delivery and Exclaimer are used](https://support.microsoft.com/help/4014438/messages-with-attachments-are-not-delivered-when-atp-dynamic-delivery)</span></span>

- <span data-ttu-id="280dc-142">Messaggi crittografati con [S/MIME (Secure/Multipurpose Internet Mail Extensions)](s-mime-for-message-signing-and-encryption.md))</span><span class="sxs-lookup"><span data-stu-id="280dc-142">Messages encrypted with [Secure/Multipurpose Internet Mail Extensions (S/MIME)](s-mime-for-message-signing-and-encryption.md))</span></span>

