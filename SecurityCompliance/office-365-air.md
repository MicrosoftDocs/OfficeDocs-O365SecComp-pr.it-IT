---
title: Esaminare e rispondere automaticamente alle minacce in Office 365
keywords: ARIA, autoIR, ATP, automatizzato, investigazione, risposta, correzione, minacce, avanzate, minacce, protezione
ms.author: deniseb
author: denisebmsft
manager: dansimp
ms.date: 09/04/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection: M365-security-compliance
description: Iniziare a utilizzare le funzionalità di analisi e risposta automatizzate in Office 365 Advanced Threat Protection Plan 2.
ms.openlocfilehash: 2c64ea936170524811839db7c593d67bfe11a928
ms.sourcegitcommit: 4a2bde56178609e75c1ad7ecad2db5e049fc0c45
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/05/2019
ms.locfileid: "36762025"
---
# <a name="automatically-investigate-and-respond-to-threats-in-office-365"></a><span data-ttu-id="dc200-104">Esaminare e rispondere automaticamente alle minacce in Office 365</span><span class="sxs-lookup"><span data-stu-id="dc200-104">Automatically investigate and respond to threats in Office 365</span></span>

## <a name="overview"></a><span data-ttu-id="dc200-105">Panoramica</span><span class="sxs-lookup"><span data-stu-id="dc200-105">Overview</span></span>

<span data-ttu-id="dc200-106">[Protezione avanzata dalle minacce di Office 365](office-365-atp.md) In Plan 2 sono incluse le funzionalità di analisi e risposta automatizzate in grado di salvare il tempo e lo sforzo del team per le operazioni di sicurezza per gestire gli avvisi e le minacce.</span><span class="sxs-lookup"><span data-stu-id="dc200-106">[Office 365 Advanced Threat Protection](office-365-atp.md) Plan 2 includes automated investigation and response (AIR) capabilities that can save your security operations team time and effort in dealing with alerts and threats.</span></span> <span data-ttu-id="dc200-107">Leggere questo articolo per iniziare a usare AIR capabilities in Office 365.</span><span class="sxs-lookup"><span data-stu-id="dc200-107">Read this article to get started using AIR capabilities in Office 365.</span></span> <span data-ttu-id="dc200-108">Per ulteriori informazioni sul funzionamento dell'aria, vedere [Automatic Investigation and Response (Air) con Office 365](automated-investigation-response-office.md).</span><span class="sxs-lookup"><span data-stu-id="dc200-108">To learn more about how AIR works, see [Automated Investigation and Response (AIR) with Office 365](automated-investigation-response-office.md).</span></span>

<span data-ttu-id="dc200-109">Con l'aria, quando vengono attivati determinati avvisi, vengono avviati uno o più schemi di sicurezza e viene avviata un'indagine automatizzata.</span><span class="sxs-lookup"><span data-stu-id="dc200-109">With AIR, when certain alerts are triggered, one or more security playbooks initiate, and automated investigation begins.</span></span> <span data-ttu-id="dc200-110">Durante e dopo un processo di analisi automatizzato, il team degli amministratori e delle operazioni di sicurezza può:</span><span class="sxs-lookup"><span data-stu-id="dc200-110">During and after an automated investigation process, your administrators and security operations team can:</span></span>

- [<span data-ttu-id="dc200-111">Visualizzare i dettagli di un'indagine</span><span class="sxs-lookup"><span data-stu-id="dc200-111">View the details of an investigation</span></span>](#view-details-of-an-investigation)

- [<span data-ttu-id="dc200-112">Esaminare e approvare le azioni in seguito a un'indagine</span><span class="sxs-lookup"><span data-stu-id="dc200-112">Review and approve actions as a result of an investigation</span></span>](#review-and-approve-actions) 

- [<span data-ttu-id="dc200-113">Visualizzare i dettagli relativi a un avviso relativo a un'indagine</span><span class="sxs-lookup"><span data-stu-id="dc200-113">View details about an alert related to an investigation</span></span>](#view-details-about-an-alert-related-to-an-investigation)

> [!NOTE]
> <span data-ttu-id="dc200-114">Per eseguire le attività descritte in questo articolo, è necessario essere un amministratore globale, un amministratore della sicurezza, un operatore di sicurezza o un lettore di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="dc200-114">You must be a global administrator, security administrator, security operator, or security reader to perform the tasks described in this article.</span></span> <span data-ttu-id="dc200-115">Per ulteriori informazioni, vedere [Microsoft 365 Security Center: Roles and Permissions](https://docs.microsoft.com/office365/securitycompliance/microsoft-security-and-compliance#required-licenses-and-permissions).</span><span class="sxs-lookup"><span data-stu-id="dc200-115">To learn more, see [Microsoft 365 security center: roles and permissions](https://docs.microsoft.com/office365/securitycompliance/microsoft-security-and-compliance#required-licenses-and-permissions).</span></span>

## <a name="view-details-of-an-investigation"></a><span data-ttu-id="dc200-116">Visualizzare i dettagli di un'indagine</span><span class="sxs-lookup"><span data-stu-id="dc200-116">View details of an investigation</span></span>

1. <span data-ttu-id="dc200-117">In qualità di amministratore globale di Office 365, amministratore della sicurezza o lettore di sicurezza [https://protection.office.com](https://protection.office.com) , accedere a e accedere.</span><span class="sxs-lookup"><span data-stu-id="dc200-117">As an Office 365 global administrator, security administrator, or security reader, go to [https://protection.office.com](https://protection.office.com) and sign in.</span></span> <span data-ttu-id="dc200-118">Questo porta al centro sicurezza & Compliance.</span><span class="sxs-lookup"><span data-stu-id="dc200-118">This takes you to the the Security & Compliance Center.</span></span>

2. <span data-ttu-id="dc200-119">Eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="dc200-119">Do one of the following:</span></span>

    - <span data-ttu-id="dc200-120">Andare al > **Dashboard**di **gestione delle minacce**.</span><span class="sxs-lookup"><span data-stu-id="dc200-120">Go to **Threat management** > **Dashboard**.</span></span> <span data-ttu-id="dc200-121">Questo porta al dashboard di [sicurezza](security-dashboard.md).</span><span class="sxs-lookup"><span data-stu-id="dc200-121">This takes you to the [Security Dashboard](security-dashboard.md).</span></span> <span data-ttu-id="dc200-122">I widget aria vengono visualizzati nella parte superiore del [dashboard di sicurezza](security-dashboard.md).</span><span class="sxs-lookup"><span data-stu-id="dc200-122">Your AIR widgets appear across the top of the [Security Dashboard](security-dashboard.md).</span></span> <span data-ttu-id="dc200-123">Selezionare un widget, ad esempio **Riepilogo indagini**.</span><span class="sxs-lookup"><span data-stu-id="dc200-123">Select a widget, such as **Investigations summary**.</span></span>

    - <span data-ttu-id="dc200-124">Andare a > **indagini**sulla **gestione delle minacce**.</span><span class="sxs-lookup"><span data-stu-id="dc200-124">Go to **Threat management** > **Investigations**.</span></span> 

    <span data-ttu-id="dc200-125">Entrambi i metodi consentono di eseguire l'elenco delle indagini.</span><span class="sxs-lookup"><span data-stu-id="dc200-125">Either method takes you to a list of investigations.</span></span>

    ![Pagina di ricerca principale per AIR](media/air-maininvestigationpage.png) 

3. <span data-ttu-id="dc200-127">Nell'elenco delle indagini selezionare un elemento nella colonna **ID** .</span><span class="sxs-lookup"><span data-stu-id="dc200-127">In the list of investigations, select an item in the **ID** column.</span></span> <span data-ttu-id="dc200-128">Verrà aperta la pagina dei dettagli dell'analisi, a partire dal grafico di analisi.</span><span class="sxs-lookup"><span data-stu-id="dc200-128">This opens investigation details page, starting with the investigation graph.</span></span>

    ![Pagina del grafico dell'indagine aerea](media/air-investigationgraphpage.png)

4. <span data-ttu-id="dc200-130">Utilizzare le varie schede per ulteriori informazioni sull'indagine.</span><span class="sxs-lookup"><span data-stu-id="dc200-130">Use the various tabs to learn more about the investigation.</span></span>

## <a name="review-and-approve-actions"></a><span data-ttu-id="dc200-131">Esaminare e approvare le azioni</span><span class="sxs-lookup"><span data-stu-id="dc200-131">Review and approve actions</span></span>

<span data-ttu-id="dc200-132">In Office 365, le indagini automatizzate in genere determinano una o più azioni consigliate.</span><span class="sxs-lookup"><span data-stu-id="dc200-132">In Office 365, automated investigations typically result in one or more recommended actions.</span></span> <span data-ttu-id="dc200-133">Tuttavia, non vengono eseguite azioni finché non vengono approvate dal team di operazioni di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="dc200-133">However, no actions are taken until they are approved by your security operations team.</span></span> <span data-ttu-id="dc200-134">Utilizzare la procedura seguente per esaminare e approvare le azioni.</span><span class="sxs-lookup"><span data-stu-id="dc200-134">Use the following procedure to review and approve actions.</span></span>

1. <span data-ttu-id="dc200-135">In qualità di amministratore globale di Office 365, amministratore della sicurezza o lettore di sicurezza [https://protection.office.com](https://protection.office.com) , accedere a e accedere.</span><span class="sxs-lookup"><span data-stu-id="dc200-135">As an Office 365 global administrator, security administrator, or security reader, go to [https://protection.office.com](https://protection.office.com) and sign in.</span></span> 

2. <span data-ttu-id="dc200-136">Andare a > **indagini**sulla **gestione delle minacce**.</span><span class="sxs-lookup"><span data-stu-id="dc200-136">Go to **Threat management** > **Investigations**.</span></span>

3. <span data-ttu-id="dc200-137">Nell'elenco delle indagini selezionare un elemento nella colonna **ID** .</span><span class="sxs-lookup"><span data-stu-id="dc200-137">In the list of investigations, select an item in the **ID** column.</span></span> 

3. <span data-ttu-id="dc200-138">Nella visualizzazione dettagli analisi selezionare la scheda **azioni** . Tutte le azioni che sono in attesa di approvazione sono elencate qui.</span><span class="sxs-lookup"><span data-stu-id="dc200-138">On the investigation details view, select the **Actions** tab. Any actions that are pending approval are listed here.</span></span>

4. <span data-ttu-id="dc200-139">Selezionare un elemento nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="dc200-139">Select an item in the list.</span></span>

5. <span data-ttu-id="dc200-140">Selezionare **approva** per eseguire l'azione consigliata (o **rifiuta** per chiudere l'inchiesta senza intervenire).</span><span class="sxs-lookup"><span data-stu-id="dc200-140">Select **Approve** to take the recommended action (or **Reject** to close the investigation without taking action).</span></span>

## <a name="view-details-about-an-alert-related-to-an-investigation"></a><span data-ttu-id="dc200-141">Visualizzare i dettagli relativi a un avviso relativo a un'indagine</span><span class="sxs-lookup"><span data-stu-id="dc200-141">View details about an alert related to an investigation</span></span>

<span data-ttu-id="dc200-142">Alcuni tipi di avvisi attivano l'analisi automatizzata in Office 365.</span><span class="sxs-lookup"><span data-stu-id="dc200-142">Certain kinds of alerts trigger automated investigation in Office 365.</span></span> <span data-ttu-id="dc200-143">Per ulteriori informazioni, vedere [Alerts](automated-investigation-response-office.md#alerts).</span><span class="sxs-lookup"><span data-stu-id="dc200-143">To learn more, see [Alerts](automated-investigation-response-office.md#alerts).</span></span> <span data-ttu-id="dc200-144">Utilizzare la procedura seguente per visualizzare i dettagli relativi a un avviso associato a un'indagine automatizzata.</span><span class="sxs-lookup"><span data-stu-id="dc200-144">Use the following procedure to view details about an alert that is associated with an automated investigation.</span></span>

1. <span data-ttu-id="dc200-145">In qualità di amministratore globale di Office 365, amministratore della sicurezza o lettore di sicurezza [https://protection.office.com](https://protection.office.com) , accedere a e accedere.</span><span class="sxs-lookup"><span data-stu-id="dc200-145">As an Office 365 global administrator, security administrator, or security reader, go to [https://protection.office.com](https://protection.office.com) and sign in.</span></span> <span data-ttu-id="dc200-146">Questo porta al centro sicurezza & Compliance.</span><span class="sxs-lookup"><span data-stu-id="dc200-146">This takes you to the the Security & Compliance Center.</span></span>

2. <span data-ttu-id="dc200-147">Andare a > **indagini**sulla **gestione delle minacce**.</span><span class="sxs-lookup"><span data-stu-id="dc200-147">Go to **Threat management** > **Investigations**.</span></span>

3. <span data-ttu-id="dc200-148">Nell'elenco delle indagini selezionare un elemento nella colonna **ID** .</span><span class="sxs-lookup"><span data-stu-id="dc200-148">In the list of investigations, select an item in the **ID** column.</span></span> 

4. <span data-ttu-id="dc200-149">Per informazioni dettagliate sull'apertura di un'indagine, selezionare la scheda **avvisi** . Tutti gli avvisi che hanno attivato l'indagine sono elencati qui.</span><span class="sxs-lookup"><span data-stu-id="dc200-149">With details of an investigation open, select the **Alerts** tab. Any alerts that triggered the investigation are listed here.</span></span>

5. <span data-ttu-id="dc200-150">Selezionare un elemento nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="dc200-150">Select an item in the list.</span></span> <span data-ttu-id="dc200-151">Verrà aperto un riquadro a comparsa con informazioni dettagliate sull'avviso e collegamenti a ulteriori operazioni.</span><span class="sxs-lookup"><span data-stu-id="dc200-151">A flyout opens, with details about the alert and links to additional information and actions.</span></span>

6. <span data-ttu-id="dc200-152">Esaminare le informazioni nel riquadro a comparsa e, a seconda dell'avviso specifico, eseguire un'azione, ad esempio **risolvere**, **sopprimere**o **informare gli utenti**.</span><span class="sxs-lookup"><span data-stu-id="dc200-152">Review the information on the flyout, and, depending on the particular alert, take an action, such as **Resolve**, **Suppress**, or **Notify users**.</span></span> 

## <a name="use-the-office-365-management-activity-api-for-custom-or-third-party-reporting-solutions"></a><span data-ttu-id="dc200-153">Utilizzare l'API di attività di gestione di Office 365 per soluzioni di Reporting personalizzate o di terze parti</span><span class="sxs-lookup"><span data-stu-id="dc200-153">Use the Office 365 Management Activity API for custom or third-party reporting solutions</span></span>

<span data-ttu-id="dc200-154">Se l'organizzazione utilizza una soluzione per i report personalizzati o una soluzione di Reporting di terze parti, è possibile visualizzare le informazioni sulle indagini automatizzate in tale soluzione utilizzando l'API di gestione delle attività di Office 365.</span><span class="sxs-lookup"><span data-stu-id="dc200-154">If your organization is using a custom reporting solution, or a third-party reporting solution, you can view information about automated investigations in that solution by using the Office 365 Management Activity API.</span></span>

<span data-ttu-id="dc200-155">Per impostare questa impostazione, utilizzare le risorse seguenti:</span><span class="sxs-lookup"><span data-stu-id="dc200-155">Use the following resources to set this up:</span></span>

|<span data-ttu-id="dc200-156">Risorsa</span><span class="sxs-lookup"><span data-stu-id="dc200-156">Resource</span></span>  |<span data-ttu-id="dc200-157">Descrizione</span><span class="sxs-lookup"><span data-stu-id="dc200-157">Description</span></span>  |
|---------|---------|
|[<span data-ttu-id="dc200-158">Panoramica delle API di gestione di Office 365</span><span class="sxs-lookup"><span data-stu-id="dc200-158">Office 365 Management APIs overview</span></span>](https://docs.microsoft.com/office/office-365-management-api/office-365-management-apis-overview)     |<span data-ttu-id="dc200-159">L'API di attività di gestione di Office 365 fornisce informazioni su varie azioni e eventi relativi a utenti, amministratori, sistemi e criteri dei log attività di Office 365 e Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="dc200-159">The Office 365 Management Activity API provides information about various user, admin, system, and policy actions and events from Office 365 and Azure Active Directory activity logs.</span></span>         |
|[<span data-ttu-id="dc200-160">Iniziare a utilizzare le API di gestione di Office 365</span><span class="sxs-lookup"><span data-stu-id="dc200-160">Get started with Office 365 Management APIs</span></span>](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis)     |<span data-ttu-id="dc200-161">L'API di gestione di Office 365 utilizza Azure AD per fornire servizi di autenticazione per l'applicazione per accedere ai dati di Office 365.</span><span class="sxs-lookup"><span data-stu-id="dc200-161">The Office 365 Management API uses Azure AD to provide authentication services for your application to access Office 365 data.</span></span> <span data-ttu-id="dc200-162">Seguire la procedura descritta in questo articolo per configurare l'operazione.</span><span class="sxs-lookup"><span data-stu-id="dc200-162">Follow the steps in this article to set this up.</span></span>          |
|[<span data-ttu-id="dc200-163">Guida di riferimento all'API dell'attività di gestione di Office 365</span><span class="sxs-lookup"><span data-stu-id="dc200-163">Office 365 Management Activity API reference</span></span>](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference)     |<span data-ttu-id="dc200-164">È possibile utilizzare l'API di attività di gestione di Office 365 per recuperare le informazioni sulle azioni e sugli eventi degli utenti, dell'amministratore, del sistema e dei criteri dai registri delle attività di Office 365 e Azure AD.</span><span class="sxs-lookup"><span data-stu-id="dc200-164">You can use the Office 365 Management Activity API to retrieve information about user, admin, system, and policy actions and events from Office 365 and Azure AD activity logs.</span></span> <span data-ttu-id="dc200-165">Leggere questo articolo per ulteriori informazioni su come funziona.</span><span class="sxs-lookup"><span data-stu-id="dc200-165">Read this article to learn more about how this works.</span></span>        |
|[<span data-ttu-id="dc200-166">Schema API di attività di gestione di Office 365</span><span class="sxs-lookup"><span data-stu-id="dc200-166">Office 365 Management Activity API schema</span></span>](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema)     |<span data-ttu-id="dc200-167">Ottenere una panoramica dello [schema comune](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#common-schema) e dello [schema di analisi e risposta di Office 365 ATP and Threat](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema) per informazioni su tipi specifici di dati disponibili tramite l'API di attività di gestione di Office 365.</span><span class="sxs-lookup"><span data-stu-id="dc200-167">Get an overview of the [Common schema](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#common-schema) and the [Office 365 ATP and threat investigation and response schema](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema) to learn about specific kinds of data available through the Office 365 Management Activity API.</span></span>         |

## <a name="next-steps"></a><span data-ttu-id="dc200-168">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="dc200-168">Next steps</span></span>

[<span data-ttu-id="dc200-169">Ulteriori informazioni sugli avvisi</span><span class="sxs-lookup"><span data-stu-id="dc200-169">Learn more about alerts</span></span>](alert-policies.md)

[<span data-ttu-id="dc200-170">Trovare e studiare manualmente messaggi di posta elettronica dannosi che sono stati recapitati in Office 365</span><span class="sxs-lookup"><span data-stu-id="dc200-170">Manually find and investigate malicious email that was delivered in Office 365</span></span>](investigate-malicious-email-that-was-delivered.md)

[<span data-ttu-id="dc200-171">Informazioni su AIR in Microsoft Defender ATP</span><span class="sxs-lookup"><span data-stu-id="dc200-171">Learn about AIR in Microsoft Defender ATP</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)

[<span data-ttu-id="dc200-172">Visitare la Guida di orientamento di Microsoft 365 per vedere cosa succederà tra breve e in uscita</span><span class="sxs-lookup"><span data-stu-id="dc200-172">Visit the Microsoft 365 Roadmap to see what's coming soon and rolling out</span></span>](https://www.microsoft.com/microsoft-365/roadmap?filters=)