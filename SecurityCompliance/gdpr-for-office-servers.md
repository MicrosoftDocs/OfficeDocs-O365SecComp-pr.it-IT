---
title: RGPD per server di Office
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
ms.custom: ''
localization_priority: Priority
description: Informazioni su come gestire i requisiti RGPD nei server locali di Office.
ms.openlocfilehash: 2f5dc98a9842d6afc70563c6d9dbc0e46b85b089
ms.sourcegitcommit: c31424cafbf1953f2864d7e2ceb95b329a694edb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/29/2018
ms.locfileid: "23272441"
---
# <a name="gdpr-for-office-on-premises-servers"></a><span data-ttu-id="d1afb-103">RGDP per server locali di Office</span><span class="sxs-lookup"><span data-stu-id="d1afb-103">GDPR for Office on-premises Servers</span></span>

<span data-ttu-id="d1afb-p101">L'RGDP presenta i requisiti delle organizzazioni per proteggere i dati personali e rispondere in modo appropriato alle richieste del soggetto dei dati. Questa serie di articoli fornisce i metodi consigliati per i carichi di lavoro locali:</span><span class="sxs-lookup"><span data-stu-id="d1afb-p101">The General Data Protection Regulation (GDPR) introduces requirements for organizations to protect personal data and respond appropriately to data subject requests. This series of articles provides recommended approaches for on-premises workloads:</span></span>

-   [<span data-ttu-id="d1afb-106">SharePoint Server</span><span class="sxs-lookup"><span data-stu-id="d1afb-106">SharePoint Server</span></span>](gdpr-for-sharepoint-server.md)

-   [<span data-ttu-id="d1afb-107">Exchange Server</span><span class="sxs-lookup"><span data-stu-id="d1afb-107">Exchange Server</span></span>](gdpr-for-exchange-server.md)

-   [<span data-ttu-id="d1afb-108">Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="d1afb-108">Skype for Business Server</span></span>](gdpr-for-skype-for-business-server.md)

-   [<span data-ttu-id="d1afb-109">Project Server</span><span class="sxs-lookup"><span data-stu-id="d1afb-109">Project Server</span></span>](gdpr-for-project-server.md)

-   [<span data-ttu-id="d1afb-110">Server Office Web Apps e Office Online Server</span><span class="sxs-lookup"><span data-stu-id="d1afb-110">Office Web Apps Server and Office Online Server</span></span>](gdpr-for-office-online-server.md)

-   [<span data-ttu-id="d1afb-111">Condivisioni file locali</span><span class="sxs-lookup"><span data-stu-id="d1afb-111">On-premises file shares</span></span>](gdpr-for-on-premises-file-shares.md)

<span data-ttu-id="d1afb-112">Per ulteriori informazioni sull'RGDP e su come Microsoft può essere di aiuto, vedere [Centro protezione Microsoft](https://www.microsoft.com/it-IT/TrustCenter/Privacy/gdpr/default.aspx).</span><span class="sxs-lookup"><span data-stu-id="d1afb-112">For more information about the GDPR and how Microsoft can help you, see the [Microsoft Trust Center](https://www.microsoft.com/it-IT/TrustCenter/Privacy/gdpr/default.aspx).</span></span>

<span data-ttu-id="d1afb-p102">Prima di iniziare una qualsiasi operazione con i dati locali, consultare il team di conformità e il team legale per cercare informazioni sugli schemi di classificazione esistenti e sugli approcci all'utilizzo dei dati personali. Microsoft fornisce suggerimenti per lo sviluppo e per l'estensione degli schemi di classificazione nel Microsoft GDPR Data Discovery Toolkit in [http://aka.ms/gdprpartners](<http://aka.ms/gdprpartners>). Il toolkit descrive anche metodi per trasferire dati locali nel cloud, dove è possibile utilizzare funzionalità di gestione dati più complesse, se necessario. Gli articoli di questa sezione contengono suggerimenti per i dati che devono rimanere in locale.</span><span class="sxs-lookup"><span data-stu-id="d1afb-p102">Before doing any work with on-premises data, consult with your legal and compliance teams to seek guidance and to learn about existing classification schemas and approaches to working with personal data. Microsoft provides recommendations for developing and extending classifications schemas in the Microsoft GDPR Data Discovery Toolkit at [http://aka.ms/gdprpartners](<http://aka.ms/gdprpartners>). This toolkit also describes approaches for moving on-premises data to the cloud where you can use more sophisticated data governance capabilities, if this is desired. The articles in this section provide recommendations for data that is intended to remain on premises.</span></span>

<span data-ttu-id="d1afb-p103">Di seguito sono elencate funzionalità consigliate per ognuno di questi carichi di lavoro per individuare, classificare, proteggere e monitorare i dati personali. Vedere gli articoli in questa sezione per ulteriori informazioni.</span><span class="sxs-lookup"><span data-stu-id="d1afb-p103">The following illustration lists recommended capabilities to use across each of these workloads to discover, classify, protect, and monitor personal data. See the articles in this section for more information.</span></span>

![](media/gdpr-for-office-servers-image1.png)

## <a name="illustration-description"></a><span data-ttu-id="d1afb-119">Descrizione dell'illustrazione</span><span class="sxs-lookup"><span data-stu-id="d1afb-119">Illustration description</span></span>

<span data-ttu-id="d1afb-120">Ai fini dell'accessibilità, la seguente tabella fornisce le stesse informazioni dell'illustrazione.</span><span class="sxs-lookup"><span data-stu-id="d1afb-120">For accessibility, the following table provides the same examples in the illustration.</span></span>

|             |<span data-ttu-id="d1afb-121">Condivisioni file di Windows Server</span><span class="sxs-lookup"><span data-stu-id="d1afb-121">Windows Server file shares</span></span>|<span data-ttu-id="d1afb-122">SharePoint Server</span><span class="sxs-lookup"><span data-stu-id="d1afb-122">SharePoint Server</span></span>|<span data-ttu-id="d1afb-123">Exchange Server</span><span class="sxs-lookup"><span data-stu-id="d1afb-123">Exchange Server</span></span>|<span data-ttu-id="d1afb-124">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="d1afb-124">Skype for Business</span></span>|<span data-ttu-id="d1afb-125">Project Server</span><span class="sxs-lookup"><span data-stu-id="d1afb-125">Project Server</span></span>|
|:------------|:-------------------------|:----------------|:--------------|:-----------------|:-------------|
|<span data-ttu-id="d1afb-126">Individuare</span><span class="sxs-lookup"><span data-stu-id="d1afb-126">Discover</span></span>|<span data-ttu-id="d1afb-127">Scanner di Azure Information Protection</span><span class="sxs-lookup"><span data-stu-id="d1afb-127">Azure Information Protection scanner\*</span></span>|<span data-ttu-id="d1afb-128">Centro ricerche o eDiscovery (dopo la classificazione dei dati); scanner di Azure Information Protection\*</span><span class="sxs-lookup"><span data-stu-id="d1afb-128">Search Center or eDiscovery (after data is classified); Azure Information Protection scanner\*</span></span>|<span data-ttu-id="d1afb-129">Portale eDiscovery di Exchange</span><span class="sxs-lookup"><span data-stu-id="d1afb-129">Exchange eDiscovery Portal</span></span>|<span data-ttu-id="d1afb-130">Portale eDiscovery di Exchange</span><span class="sxs-lookup"><span data-stu-id="d1afb-130">Exchange eDiscovery portal</span></span>|<span data-ttu-id="d1afb-131">Script SQL per l'individuazione e l'esportazione</span><span class="sxs-lookup"><span data-stu-id="d1afb-131">SQL scripts for discovery and exporting</span></span>|
|<span data-ttu-id="d1afb-132">Classificare</span><span class="sxs-lookup"><span data-stu-id="d1afb-132">Classify</span></span>|<span data-ttu-id="d1afb-133">Scanner di Azure Information Protection\*; tipi di informazioni riservate di Office 365</span><span class="sxs-lookup"><span data-stu-id="d1afb-133">Azure Information Protection scanner\*; Office 365 sensitive information types</span></span>|<span data-ttu-id="d1afb-134">Scanner di Azure Information Protection\*; tipi di informazioni riservate di Office 365</span><span class="sxs-lookup"><span data-stu-id="d1afb-134">Azure Information Protection scanner\*; Office 365 sensitive information types</span></span>|<span data-ttu-id="d1afb-135">Tag e criteri di conservazione di Exchange</span><span class="sxs-lookup"><span data-stu-id="d1afb-135">Exchange retention tags and retention policies</span></span>|<span data-ttu-id="d1afb-136">Tag e criteri di conservazione di Exchange</span><span class="sxs-lookup"><span data-stu-id="d1afb-136">Exchange retention tags and retention policies</span></span>||
|<span data-ttu-id="d1afb-137">Proteggere</span><span class="sxs-lookup"><span data-stu-id="d1afb-137">Protect</span></span>||<span data-ttu-id="d1afb-138">Regole di prevenzione della perdita dei dati di Exchange Server; autorizzazioni, protezione IRM per le raccolte</span><span class="sxs-lookup"><span data-stu-id="d1afb-138">Exchange Server data loss prevention rules; Permissions, IRM-protection for libraries</span></span>|<span data-ttu-id="d1afb-139">Regole di prevenzione della perdita dei dati di Exchange Server; integrazione IRM con Exchange Server</span><span class="sxs-lookup"><span data-stu-id="d1afb-139">Exchange Server data loss prevention rules; IRM integration with Exchange Server</span></span>|||
|<span data-ttu-id="d1afb-140">Monitorare</span><span class="sxs-lookup"><span data-stu-id="d1afb-140">Monitor</span></span>|<span data-ttu-id="d1afb-141">Integrazione di log con strumenti SIEM</span><span class="sxs-lookup"><span data-stu-id="d1afb-141">Integrate logs with SIEM tools</span></span>|<span data-ttu-id="d1afb-142">Integrazione di log con strumenti SIEM</span><span class="sxs-lookup"><span data-stu-id="d1afb-142">Integrate logs with SIEM tools</span></span>|<span data-ttu-id="d1afb-143">Integrazione di log con strumenti SIEM</span><span class="sxs-lookup"><span data-stu-id="d1afb-143">Integrate logs with SIEM tools</span></span>|<span data-ttu-id="d1afb-144">Integrazione di log con strumenti SIEM</span><span class="sxs-lookup"><span data-stu-id="d1afb-144">Integrate logs with SIEM tools</span></span>|<span data-ttu-id="d1afb-145">Integrazione di log con strumenti SIEM</span><span class="sxs-lookup"><span data-stu-id="d1afb-145">Integrate logs with SIEM tools</span></span>|

<span data-ttu-id="d1afb-p104">\*Si noti che la protezione crittografa il file, di conseguenza, SharePoint Server non riesce a individuare tipi di informazioni riservate nei file protetti.</span><span class="sxs-lookup"><span data-stu-id="d1afb-p104">\*Note that protection encrypts the file. Consequently, SharePoint Server can’t find the sensitive information types in protected files.</span></span>
