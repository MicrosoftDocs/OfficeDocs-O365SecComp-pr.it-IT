---
title: Monitorare e segnalare lo stato delle app in Microsoft 365 Security
description: Descrive come è possibile ottenere ulteriori informazioni sull'utilizzo delle app Cloud nell'organizzazione
keywords: sicurezza, malware, Microsoft 365, M365, Centro sicurezza, monitoraggio, report, app
ms.prod: w10
ms.mktglfcycl: deploy
ms.localizationpriority: medium
ms.author: ellevin
author: levinec
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: 02cc511532f65172aba2c0f98cdf594776f586a5
ms.sourcegitcommit: ef27da3ea5340d6e7a2eaa1288e2e005ef8e4788
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2019
ms.locfileid: "30791752"
---
# <a name="monitor-and-report-app-status-in-microsoft-365-security"></a><span data-ttu-id="a53ff-104">Monitorare e segnalare lo stato delle app in Microsoft 365 Security</span><span class="sxs-lookup"><span data-stu-id="a53ff-104">Monitor and report app status in Microsoft 365 security</span></span>

[!include[Prerelease�information](prerelease.md)]

<span data-ttu-id="a53ff-105">Questi rapporti offrono maggiori informazioni su come vengono utilizzate le app Cloud nell'organizzazione, inclusi i tipi di app, il livello di rischio e gli avvisi.</span><span class="sxs-lookup"><span data-stu-id="a53ff-105">These reports provide more insight into how cloud apps are being used in your organization, including what kinds of apps, their level of risk, and alerts.</span></span>

## <a name="monitor-email-accounts-at-risk"></a><span data-ttu-id="a53ff-106">Monitorare gli account di posta elettronica a rischio</span><span class="sxs-lookup"><span data-stu-id="a53ff-106">Monitor email accounts at risk</span></span>

<span data-ttu-id="a53ff-107">La **protezione della posta** elettronica Visualizza gli account di posta elettronica a rischio.</span><span class="sxs-lookup"><span data-stu-id="a53ff-107">**Email protection** shows email accounts at risk.</span></span> <span data-ttu-id="a53ff-108">È possibile fare clic su un account per ulteriori informazioni su Windows Defender Security Center.</span><span class="sxs-lookup"><span data-stu-id="a53ff-108">You can click an account to investigate further in Windows Defender Security Center.</span></span>

![Scheda di protezione della posta elettronica](./media/security-docs/email-protection.png)

## <a name="monitor-app-permissions-granted-by-users"></a><span data-ttu-id="a53ff-110">Monitorare le autorizzazioni delle app concesse dagli utenti</span><span class="sxs-lookup"><span data-stu-id="a53ff-110">Monitor app permissions granted by users</span></span>

<span data-ttu-id="a53ff-111">**Cloud app Security-OAuth Apps** elenca le app scoperte dalla protezione delle app cloud alle quali sono state concesse le autorizzazioni per gli utenti.</span><span class="sxs-lookup"><span data-stu-id="a53ff-111">**Cloud App Security - OAuth apps** lists apps discovered by Cloud App Security that have been granted permissions by users.</span></span> <span data-ttu-id="a53ff-112">Il catalogo rischi di cloud app Security include oltre 16.000 app valutate con oltre 70 fattori di rischio.</span><span class="sxs-lookup"><span data-stu-id="a53ff-112">Cloud App Security's risk catalog includes over 16,000 apps that are assessed using over 70 risk factors.</span></span>

<span data-ttu-id="a53ff-113">I fattori di rischio partono da informazioni generali, ad esempio l'editore app, per le misure di sicurezza e i controlli, ad esempio se l'app supporta la crittografia a riposo o fornisce un registro di controllo delle attività degli utenti.</span><span class="sxs-lookup"><span data-stu-id="a53ff-113">The risk factors start from general information, such as the app publisher, to security measures and controls, such as whether the app supports for encryption at rest or provides an audit log of user activity.</span></span>

![Cloud app Security OAuth Apps Card](./media/security-docs/cloud-app-security-oauth-apps.png)

## <a name="monitor-cloud-app-user-accounts"></a><span data-ttu-id="a53ff-115">Monitorare gli account utente delle app Cloud</span><span class="sxs-lookup"><span data-stu-id="a53ff-115">Monitor cloud app user accounts</span></span>

<span data-ttu-id="a53ff-116">Gli **account delle app cloud per gli elenchi di revisione** possono richiedere attenzione.</span><span class="sxs-lookup"><span data-stu-id="a53ff-116">**Cloud app accounts for review** lists accounts that may require attention.</span></span>

![Account app cloud per la scheda di Revisione](./media/security-docs/cloud-app-accounts-for-review.png)

## <a name="understand-which-cloud-apps-are-used"></a><span data-ttu-id="a53ff-118">Informazioni sulle app Cloud utilizzate</span><span class="sxs-lookup"><span data-stu-id="a53ff-118">Understand which cloud apps are used</span></span>

<span data-ttu-id="a53ff-119">Le **app del cloud scoperte (categorie)** mostrano quali tipi di app vengono utilizzate nell'organizzazione e si collegano al dashboard di individuazione cloud in cloud app Security.</span><span class="sxs-lookup"><span data-stu-id="a53ff-119">**Discovered cloud apps (categories)** show what kinds of apps are being used in your organization and links to the Cloud Discovery dashboard in Cloud App Security.</span></span> <span data-ttu-id="a53ff-120">Per ulteriori informazioni, vedere [Guida introduttiva: lavorare con le app scoperte](https://docs.microsoft.com/cloud-app-security/discovered-apps).</span><span class="sxs-lookup"><span data-stu-id="a53ff-120">For more information, see [Quickstart: Work with discovered apps](https://docs.microsoft.com/cloud-app-security/discovered-apps).</span></span>  

![Scheda categorie di applicazioni cloud scoperte](./media/security-docs/discovered-cloud-apps-categories.png)

## <a name="monitor-where-users-access-cloud-apps"></a><span data-ttu-id="a53ff-122">Monitorare la posizione in cui gli utenti accedono alle app Cloud</span><span class="sxs-lookup"><span data-stu-id="a53ff-122">Monitor where users access cloud apps</span></span>

<span data-ttu-id="a53ff-123">Le **posizioni delle attività delle app Cloud** mostrano dove gli utenti accedono alle app cloud.</span><span class="sxs-lookup"><span data-stu-id="a53ff-123">**Cloud app activity locations** show where users are accessing cloud apps.</span></span>

![Scheda percorsi attività app Cloud](./media/security-docs/cloud-app-activity-locations.png)

## <a name="monitor-health-for-infrastructure-workloads"></a><span data-ttu-id="a53ff-125">Monitorare l'integrità dei carichi di lavoro dell'infrastruttura</span><span class="sxs-lookup"><span data-stu-id="a53ff-125">Monitor health for infrastructure workloads</span></span>

<span data-ttu-id="a53ff-126">L' **integrità dell'infrastruttura** Visualizza gli avvisi sullo stato dell'integrità per i carichi di lavoro dell'infrastruttura in Azure Security Center.</span><span class="sxs-lookup"><span data-stu-id="a53ff-126">**Infrastructure health** shows health status alerts for infrastructure workloads in Azure Security Center.</span></span>

<span data-ttu-id="a53ff-127">Azure Security Center fornisce la gestione della sicurezza unificata e la protezione avanzata dalle minacce tra carichi di lavoro locali e cloud.</span><span class="sxs-lookup"><span data-stu-id="a53ff-127">Azure Security Center provides unified security management and advanced threat protection across on-premises and cloud workloads.</span></span> <span data-ttu-id="a53ff-128">È possibile raccogliere, ricercare e analizzare i dati di sicurezza provenienti da un'ampia gamma di origini, tra cui i firewall e altre soluzioni partner.</span><span class="sxs-lookup"><span data-stu-id="a53ff-128">You can collect, search, and analyze security data from a variety of sources, including firewalls and other partner solutions.</span></span>

<span data-ttu-id="a53ff-129">Per ulteriori informazioni, vedere [documentazione relativa al centro sicurezza di Azure](https://docs.microsoft.com/azure/security-center/).</span><span class="sxs-lookup"><span data-stu-id="a53ff-129">For more information, see [Azure Security Center Documentation](https://docs.microsoft.com/azure/security-center/).</span></span>

![Scheda di integrità dell'infrastruttura](./media/security-docs/infrastructure-health.png)
