---
title: Introduzione ai criteri di prevenzione della perdita dei dati predefiniti
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 8/10/2017
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: e0ada764-6422-4b44-9472-513bed04837b
description: Prima di creare anche il primo criterio di criterio DLP perdita di dati, DLP aiuta a proteggere le informazioni sensibili con un criterio predefinito. Questo criterio predefinito e il relativo Mantieni Guida recommendation (come illustrato di seguito) il contenuto riservato sicuro ricevere una notifica quando il numero di carta di posta elettronica o documenti che contengono un credito sono condivise con una persona esterna all'organizzazione.
ms.openlocfilehash: 1b522a2c04e72353970ef5dfcd62183023a01994
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/27/2018
ms.locfileid: "22531463"
---
# <a name="get-started-with-the-default-dlp-policy"></a><span data-ttu-id="212f1-104">Introduzione ai criteri di prevenzione della perdita dei dati predefiniti</span><span class="sxs-lookup"><span data-stu-id="212f1-104">Get started with the default DLP policy</span></span>

<span data-ttu-id="212f1-p102">Prima di creare anche il primo criterio di criterio DLP perdita di dati, DLP aiuta a proteggere le informazioni sensibili con un criterio predefinito. Questo criterio predefinito e il relativo Mantieni Guida recommendation (come illustrato di seguito) il contenuto riservato sicuro ricevere una notifica quando il numero di carta di posta elettronica o documenti che contengono un credito sono condivise con una persona esterna all'organizzazione. Questo suggerimento verrà visualizzato nella Home **page della sicurezza** &amp; centro conformità.</span><span class="sxs-lookup"><span data-stu-id="212f1-p102">Before you even create your first data loss prevention (DLP) policy, DLP is helping to protect your sensitive information with a default policy. This default policy and its recommendation (shown below) help keep your sensitive content secure by notifying you when email or documents containing a credit card number were shared with someone outside your organization. You'll see this recommendation on the **Home** page of the Security &amp; Compliance Center.</span></span> 
  
<span data-ttu-id="212f1-p103">È possibile utilizzare questo widget per visualizzare rapidamente i tempi e la quantità di informazioni sensibili deve essere stato condiviso e quindi ridefinire il criterio DLP predefinito un semplice clic o due. È inoltre possibile modificare il criterio DLP predefinito in qualsiasi momento perché è completamente personalizzabile. Si noti che se non viene visualizzata l'indicazione inizialmente, provare a fare clic su **+ più** nella parte inferiore della sezione **consigliato è** .</span><span class="sxs-lookup"><span data-stu-id="212f1-p103">You can use this widget to quickly view when and how much sensitive information was shared, and then refine the default DLP policy in just a click or two. You can also edit the default DLP policy at any time because it's fully customizable. Note that if you don't see the recommendation at first, try clicking **+More** at the bottom of the **Recommended for you** section.</span></span> 
  
![Widget denominato per proteggere il contenuto condiviso](media/2bae6dbc-cc92-4f35-b54c-c36e60226b5b.png)
  
## <a name="view-the-report-and-refine-the-default-dlp-policy"></a><span data-ttu-id="212f1-112">Visualizzare il report e ridefinire il criterio DLP predefinito</span><span class="sxs-lookup"><span data-stu-id="212f1-112">View the report and refine the default DLP policy</span></span>

<span data-ttu-id="212f1-113">Quando il widget viene indicato che gli utenti sono condivisi informazioni riservate con persone esterne all'organizzazione, selezionare **criterio DLP perfezionare** nella parte inferiore.</span><span class="sxs-lookup"><span data-stu-id="212f1-113">When the widget shows you that users have shared sensitive information with people outside your organization, choose **Refine DLP policy** at the bottom.</span></span> 
  
<span data-ttu-id="212f1-p104">Il rapporto dettagliato viene illustrato come e quando quantità di contenuto che contiene numeri di carta di credito deve essere stato condiviso negli ultimi 30 giorni. Si noti che corrispondenze alla regola possono richiedere fino a 48 ore possa essere visualizzata nel widget.</span><span class="sxs-lookup"><span data-stu-id="212f1-p104">The detailed report shows you when and how much content containing credit card numbers was shared in the past 30 days. Note that rule matches can take up to 48 hours to show up in the widget.</span></span>
  
<span data-ttu-id="212f1-116">Per proteggere le informazioni riservate, il criterio DLP predefinito:</span><span class="sxs-lookup"><span data-stu-id="212f1-116">To help protect the sensitive information, the default DLP policy:</span></span>
  
- <span data-ttu-id="212f1-117">Rileva quando il contenuto di Exchange, SharePoint e OneDrive che contiene il numero di carta di credito almeno un è condivise con utenti esterni all'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="212f1-117">Detects when content in Exchange, SharePoint, and OneDrive that contains at least one credit card number is shared with people outside your organization.</span></span>
    
- <span data-ttu-id="212f1-p105">Visualizza un suggerimento sul criterio e invia una notifica tramite posta elettronica per gli utenti che tentano di condividere le informazioni sensibili con persone esterne all'organizzazione. Per ulteriori informazioni su queste opzioni, vedere [inviare notifiche tramite posta elettronica e Mostra suggerimenti sui criteri per i criteri DLP](use-notifications-and-policy-tips.md).</span><span class="sxs-lookup"><span data-stu-id="212f1-p105">Shows a policy tip and sends an email notification to users when they attempt to share this sensitive information with people outside your organization. For more information on these options, see [Send email notifications and show policy tips for DLP policies](use-notifications-and-policy-tips.md).</span></span>
    
- <span data-ttu-id="212f1-p106">Genera rapporti dettagliati attività in modo che è possibile tenere traccia di elementi quali il contenuto che ha condiviso con persone esterne all'organizzazione e quando avveniva. È possibile utilizzare i [rapporti DLP](view-the-dlp-reports.md) e [i dati del Registro di controllo](search-the-audit-log-in-security-and-compliance.md) (dove **attività** = **DLP**) per visualizzare queste informazioni.</span><span class="sxs-lookup"><span data-stu-id="212f1-p106">Generates detailed activity reports so that you can track things like who shared the content with people outside your organization and when they did it. You can use the [DLP reports](view-the-dlp-reports.md) and [audit log data](search-the-audit-log-in-security-and-compliance.md) (where **Activity** = **DLP**) to see this information.</span></span>
    
<span data-ttu-id="212f1-122">Per perfezionare rapidamente il criterio DLP predefinito, è possibile scegliere di fare in modo che:</span><span class="sxs-lookup"><span data-stu-id="212f1-122">To quickly refine the default DLP policy, you can choose to have it:</span></span>
  
- <span data-ttu-id="212f1-123">Inviare un messaggio di posta elettronica rapporto operazioni non consentite quando gli utenti di condividere informazioni sensibili con persone esterne all'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="212f1-123">Send you an incident report email when users share this sensitive information with people outside your organization.</span></span>
    
- <span data-ttu-id="212f1-124">Aggiungere altri utenti per il rapporto operazioni non consentite di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="212f1-124">Add other users to the email incident report.</span></span>
    
- <span data-ttu-id="212f1-125">Bloccare l'accesso al contenuto che contiene informazioni riservate, ma consentire all'utente di eseguire l'override e condividere o se si desidera inviare.</span><span class="sxs-lookup"><span data-stu-id="212f1-125">Block access to the content containing the sensitive information, but allow the user to override and share or send if they need to.</span></span>
    
<span data-ttu-id="212f1-126">Per ulteriori informazioni su rapporti operazioni non consentite o la limitazione dell'accesso, vedere [Panoramica di criteri di prevenzione della perdita di dati](data-loss-prevention-policies.md).</span><span class="sxs-lookup"><span data-stu-id="212f1-126">For more information on incident reports or restricting access, see [Overview of data loss prevention policies](data-loss-prevention-policies.md).</span></span>
  
<span data-ttu-id="212f1-127">Se si desidera modificare in seguito queste opzioni, è possibile modificare l'impostazione predefinita il criterio DLP in qualsiasi momento, vedere la sezione successiva.</span><span class="sxs-lookup"><span data-stu-id="212f1-127">If you want to change these options later, you can edit the default DLP policy at any time - see the next section.</span></span>
  
![Le impostazioni per widget denominato per proteggere il contenuto condiviso](media/dad30a84-2715-4c0a-a5c5-44d85492363e.png)
  
## <a name="edit-the-default-dlp-policy"></a><span data-ttu-id="212f1-129">Modificare il criterio DLP predefinito</span><span class="sxs-lookup"><span data-stu-id="212f1-129">Edit the default DLP policy</span></span>

<span data-ttu-id="212f1-130">Questo criterio è denominato **criterio predefinito Office 365 DLP** e viene visualizzato sotto **prevenzione della perdita di dati** nella pagina **criteri** di sicurezza &amp; centro conformità.</span><span class="sxs-lookup"><span data-stu-id="212f1-130">This policy is named **Default Office 365 DLP policy** and appears under **Data loss prevention** on the **Policy** page of the Security &amp; Compliance Center.</span></span> 
  
<span data-ttu-id="212f1-p107">Questo criterio è completamente personalizzabile e lo stesso qualsiasi criterio DLP è creati dall'utente da zero. È anche possibile disattivare o eliminare il criterio, in modo che gli utenti non sono più ricevano suggerimenti sui criteri o le notifiche di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="212f1-p107">This policy is fully customizable, the same as any DLP policy that you create yourself from scratch. You can also turn off or delete the policy, so that your users no longer receive policy tips or email notifications.</span></span>
  
![Il criterio DLP denominato criterio predefinito DLP di Office 365](media/260731e8-4d57-4c98-abec-07b052ec48d5.png)
  
## <a name="when-the-widget-does-and-does-not-appear"></a><span data-ttu-id="212f1-134">Quando il widget e non viene visualizzato</span><span class="sxs-lookup"><span data-stu-id="212f1-134">When the widget does and does not appear</span></span>

<span data-ttu-id="212f1-135">Widget denominato **proteggere ulteriormente il contenuto condiviso** visualizzata nella sezione **consigliato è** di **Home** page della sicurezza &amp; centro conformità.</span><span class="sxs-lookup"><span data-stu-id="212f1-135">The widget named **Further protect shared content** appears in the **Recommended for you** section of the **Home** page of the Security &amp; Compliance Center.</span></span> 
  
<span data-ttu-id="212f1-136">Questo widget viene visualizzata solo se:</span><span class="sxs-lookup"><span data-stu-id="212f1-136">This widget appears only when:</span></span>
  
- <span data-ttu-id="212f1-p108">Non esistono criteri di prevenzione della perdita di dati nella protezione &amp; centro conformità o interfaccia di amministrazione di Exchange. Questo widget devono utili per iniziare a utilizzare DLP, in modo che non viene visualizzato se si dispone già di criteri DLP.</span><span class="sxs-lookup"><span data-stu-id="212f1-p108">There are no data loss prevention policies in the Security &amp; Compliance Center or Exchange Admin Center. This widget is intended to help you get started with DLP, so it doesn't appear if you already have DLP policies.</span></span>
    
- <span data-ttu-id="212f1-139">Il contenuto che include almeno una carta di credito è stato condiviso con una persona esterna all'organizzazione negli ultimi 30 giorni.</span><span class="sxs-lookup"><span data-stu-id="212f1-139">Content containing least one credit card has been shared with someone outside your organization in the past 30 days.</span></span>
    
<span data-ttu-id="212f1-140">Si noti che corrispondenze alla regola possono richiedere fino a 48 ore sia disponibile per il widget, in modo dopo il rilevamento di informazioni riservate condivise esternamente, potrebbe richiedere fino a due giorni per il suggerimento venga visualizzata.</span><span class="sxs-lookup"><span data-stu-id="212f1-140">Note that rule matches can take up to 48 hours to be available to the widget, so after sensitive information shared externally is detected, it may take up to two days for the recommendation to appear.</span></span>
  
<span data-ttu-id="212f1-141">Infine, dopo aver utilizzato il widget per perfezionare il criterio DLP predefinito, widget viene eliminata dalla **Home** page.</span><span class="sxs-lookup"><span data-stu-id="212f1-141">Finally, after you use the widget to refine the default DLP policy, the widget disappears from the **Home** page.</span></span> 
  

