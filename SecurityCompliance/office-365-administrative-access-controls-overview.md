---
title: Controlli di accesso amministrativo in Office 365
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
description: 'Riepilogo: informazioni generali sui controlli di accesso amministrativo e sulla categorizzazione dei dati di Office 365.'
ms.openlocfilehash: 38519fe4e9c05e3468ac3f9f6367c096fb64d195
ms.sourcegitcommit: 7b5e4a7a51f3cdd741deb77a2d60a18e2316618d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/01/2019
ms.locfileid: "33520696"
---
# <a name="administrative-access-controls-in-office-365"></a><span data-ttu-id="4c5ea-103">Controlli di accesso amministrativo in Office 365</span><span class="sxs-lookup"><span data-stu-id="4c5ea-103">Administrative Access Controls in Office 365</span></span> 

<span data-ttu-id="4c5ea-104">Microsoft ha investito fortemente nei sistemi e nei controlli che automatizzano la maggior parte delle operazioni di Office 365, limitando intenzionalmente l'accesso ai contenuti dei clienti da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="4c5ea-104">Microsoft has invested heavily in systems and controls that automate most Office 365 operations while intentionally limiting access to customer content by Microsoft.</span></span> <span data-ttu-id="4c5ea-105">Gli esseri umani regolano il servizio e il software gestisce il servizio.</span><span class="sxs-lookup"><span data-stu-id="4c5ea-105">Humans govern the service, and software operates the service.</span></span> <span data-ttu-id="4c5ea-106">Ciò consente a Microsoft di gestire Office 365 in scala e gestire i rischi di minacce interne ai contenuti dei clienti.</span><span class="sxs-lookup"><span data-stu-id="4c5ea-106">This enables Microsoft to manage Office 365 at scale and manage the risks of internal threats to customer content.</span></span>

<span data-ttu-id="4c5ea-107">Per impostazione predefinita, i tecnici Microsoft non hanno privilegi amministrativi e non hanno accesso ai contenuti dei clienti in Office 365.</span><span class="sxs-lookup"><span data-stu-id="4c5ea-107">By default, Microsoft engineers have zero standing administrative privileges and zero standing access to customer content in Office 365.</span></span> <span data-ttu-id="4c5ea-108">Un tecnico Microsoft può disporre di un accesso limitato, controllato e protetto al contenuto di un cliente per un periodo di tempo limitato.</span><span class="sxs-lookup"><span data-stu-id="4c5ea-108">A Microsoft engineer can have limited, audited, and secured access to a customer's content for a limited amount of time.</span></span> <span data-ttu-id="4c5ea-109">L'accesso è necessario solo per le operazioni di servizio e solo quando è approvato da un membro di Microsoft Senior Management.</span><span class="sxs-lookup"><span data-stu-id="4c5ea-109">Access is only when necessary for service operations and only when approved by a member of Microsoft senior management.</span></span> <span data-ttu-id="4c5ea-110">Per i clienti con licenza archivio protetto, il cliente fornisce l'approvazione di accesso ai propri contenuti ospitati in Office 365.</span><span class="sxs-lookup"><span data-stu-id="4c5ea-110">For Customer Lockbox licensed customers, the customer provides access approval to their content hosted on Office 365.</span></span>

<span data-ttu-id="4c5ea-111">Microsoft fornisce servizi online utilizzando più moduli di recapito cloud:</span><span class="sxs-lookup"><span data-stu-id="4c5ea-111">Microsoft provides online services using multiple forms of cloud delivery:</span></span>

- <span data-ttu-id="4c5ea-112">**Cloud pubblici:** Include versioni multi-tenant di Office 365, Azure e altri servizi ospitati in Nord America, Sud America, Europa, Asia, Australia e così via.</span><span class="sxs-lookup"><span data-stu-id="4c5ea-112">**Public Clouds:** Includes multi-tenant versions of Office 365, Azure, and other services hosted in North America, South America, Europe, Asia, Australia, etc.</span></span>
- <span data-ttu-id="4c5ea-113">**Nubi nazionali:** Include tutte le nubi sovrane e di terze parti al di fuori degli Stati Uniti (ad eccezione di quelle riportate in precedenza), come Office 365 in Cina (gestito da 21Vianet) e Office 365 in Germany (gestito da Microsoft, ma in un modello in cui un amministratore di dati tedesco, Deutsche Telekom, controlla e monitora l'accesso di Microsoft ai dati e ai sistemi dei clienti che contengono i dati dei clienti.</span><span class="sxs-lookup"><span data-stu-id="4c5ea-113">**National Clouds:** Includes all sovereign and third party-operated clouds outside of the United States (except ones noted previously), such as Office 365 in China (operated by 21Vianet), and Office 365 in Germany (operated by Microsoft, but under a model in which a German data trustee, Deutsche Telekom, controls and monitors Microsoft's access to Customer Data and systems that contain Customer Data).</span></span>
- <span data-ttu-id="4c5ea-114">**Cloud governativi:** Include i servizi Office 365 e Azure che sono disponibili per i clienti del governo degli Stati Uniti.</span><span class="sxs-lookup"><span data-stu-id="4c5ea-114">**Government Clouds:** Includes Office 365 and Azure services that are available to United States government customers.</span></span>

<span data-ttu-id="4c5ea-115">Ai fini di questo articolo, i servizi di Office 365 includono:</span><span class="sxs-lookup"><span data-stu-id="4c5ea-115">For purposes of this article, Office 365 services include:</span></span>

- [<span data-ttu-id="4c5ea-116">Exchange Online</span><span class="sxs-lookup"><span data-stu-id="4c5ea-116">Exchange Online</span></span>](https://docs.microsoft.com/Exchange/exchange-online)
- [<span data-ttu-id="4c5ea-117">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="4c5ea-117">Exchange Online Protection</span></span>](https://docs.microsoft.com/Office365/SecurityCompliance/eop/exchange-online-protection-overview)
- [<span data-ttu-id="4c5ea-118">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="4c5ea-118">SharePoint Online</span></span>](https://docs.microsoft.com/sharepoint/sharepoint-online)
- [<span data-ttu-id="4c5ea-119">OneDrive for Business</span><span class="sxs-lookup"><span data-stu-id="4c5ea-119">OneDrive for Business</span></span>](https://docs.microsoft.com/OneDrive/onedrive)
- [<span data-ttu-id="4c5ea-120">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="4c5ea-120">Skype for Business</span></span>](https://docs.microsoft.com/SkypeForBusiness/skype-for-business-online)
- [<span data-ttu-id="4c5ea-121">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="4c5ea-121">Microsoft Teams</span></span>](https://docs.microsoft.com/MicrosoftTeams/Teams-overview)
- [<span data-ttu-id="4c5ea-122">Yammer</span><span class="sxs-lookup"><span data-stu-id="4c5ea-122">Yammer</span></span>](https://docs.microsoft.com/yammer/yammer-landing-page)

## <a name="office-365-access-controls"></a><span data-ttu-id="4c5ea-123">Controlli di accesso di Office 365</span><span class="sxs-lookup"><span data-stu-id="4c5ea-123">Office 365 Access Controls</span></span>

<span data-ttu-id="4c5ea-124">Per gli scopi di controllo di accesso, Microsoft categorizza i dati di Office 365 come dati dei clienti o altri tipi di dati.</span><span class="sxs-lookup"><span data-stu-id="4c5ea-124">For access control purposes, Microsoft categorizes Office 365 data as Customer data or other types of data.</span></span>

### <a name="customer-data"></a><span data-ttu-id="4c5ea-125">Dati cliente
</span><span class="sxs-lookup"><span data-stu-id="4c5ea-125">Customer data</span></span>

<span data-ttu-id="4c5ea-126">I dati dei clienti sono tutti i dati forniti da o per conto di un cliente quando si utilizzano i servizi di Office 365.</span><span class="sxs-lookup"><span data-stu-id="4c5ea-126">Customer data is all data provided by or on behalf of a customer when using Office 365 services.</span></span> <span data-ttu-id="4c5ea-127">Si tratta di contenuti dei clienti creati direttamente o caricati da utenti di Office 365, tra cui:</span><span class="sxs-lookup"><span data-stu-id="4c5ea-127">This is customer content directly created or uploaded by Office 365 users, including:</span></span>

- <span data-ttu-id="4c5ea-128">Messaggi di posta elettronica</span><span class="sxs-lookup"><span data-stu-id="4c5ea-128">Emails</span></span>
- <span data-ttu-id="4c5ea-129">Contenuto di SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="4c5ea-129">SharePoint Online content</span></span>
- <span data-ttu-id="4c5ea-130">Messaggi istantanei</span><span class="sxs-lookup"><span data-stu-id="4c5ea-130">Instant messages</span></span>
- <span data-ttu-id="4c5ea-131">Elementi del calendario</span><span class="sxs-lookup"><span data-stu-id="4c5ea-131">Calendar items</span></span>
- <span data-ttu-id="4c5ea-132">Documenti</span><span class="sxs-lookup"><span data-stu-id="4c5ea-132">Documents</span></span>
- <span data-ttu-id="4c5ea-133">Contacts</span><span class="sxs-lookup"><span data-stu-id="4c5ea-133">Contacts</span></span>
- <span data-ttu-id="4c5ea-134">Informazioni identificabili dall'utente finale (EUII) (dati univoci per un utente o che sono collegabili a un singolo utente ma che non includono il contenuto del cliente).</span><span class="sxs-lookup"><span data-stu-id="4c5ea-134">End-user identifiable information (EUII) (data that is unique to a user or that is linkable to an individual user but does not include customer content).</span></span>

### <a name="other-types-of-data"></a><span data-ttu-id="4c5ea-135">Altri tipi di dati</span><span class="sxs-lookup"><span data-stu-id="4c5ea-135">Other types of data</span></span>

<span data-ttu-id="4c5ea-136">Altri tipi di dati includono:</span><span class="sxs-lookup"><span data-stu-id="4c5ea-136">Other types of data include:</span></span>

- <span data-ttu-id="4c5ea-137">**Dati account:** Include i dati amministrativi (informazioni fornite dagli amministratori quando eseguono la registrazione o l'acquisto di servizi) e i dati di pagamento (informazioni sugli strumenti di pagamento, ad esempio i dettagli delle carte di credito).</span><span class="sxs-lookup"><span data-stu-id="4c5ea-137">**Account data:** Includes administrative data (information provided by administrators when they sign-up or purchase services), and payment data (information about payment instruments, such as credit card details).</span></span>
- <span data-ttu-id="4c5ea-138">**Informazioni identificabili dall'organizzazione:** Include i dati utilizzati per identificare un tenant, i dati di utilizzo e non collegabili a un singolo utente o inclusi nel contenuto del cliente.</span><span class="sxs-lookup"><span data-stu-id="4c5ea-138">**Organizationally identifiable information:** Includes data used to identify a tenant, usage data, and not linkable to an individual user or included in customer content.</span></span>
- <span data-ttu-id="4c5ea-139">**Metadati di sistema:** Include i registri dei servizi che contengono le impostazioni di configurazione, lo stato del sistema, gli indirizzi IP di Microsoft e le informazioni tecniche sugli abbonamenti e sui tenant.</span><span class="sxs-lookup"><span data-stu-id="4c5ea-139">**System metadata:** Includes service logs that contain configuration settings, system status, Microsoft IP addresses, and technical information about subscriptions and tenants.</span></span>

<span data-ttu-id="4c5ea-140">Microsoft ha stabilito meccanismi di controllo di accesso per garantire che nessuno abbia accesso non autorizzato ai dati dei clienti o ai dati di controllo di accesso.</span><span class="sxs-lookup"><span data-stu-id="4c5ea-140">Microsoft has established access control mechanisms to ensure that no one has unapproved access to Customer Data or access control data.</span></span> <span data-ttu-id="4c5ea-141">I dati di controllo di accesso gestiscono l'accesso ad altri tipi di dati o funzioni all'interno dell'ambiente, tra cui l'accesso al contenuto del cliente o EUII, le password Microsoft, i certificati di sicurezza e altri dati correlati all'autenticazione.</span><span class="sxs-lookup"><span data-stu-id="4c5ea-141">Access control data manages access to other types of data or functions within the environment, including access to customer content or EUII, Microsoft passwords, security certificates, and other authentication-related data.</span></span> <span data-ttu-id="4c5ea-142">I meccanismi di controllo di accesso proteggono anche dall'accesso fisico, logico o remoto non approvato all'ambiente di produzione di Office 365.</span><span class="sxs-lookup"><span data-stu-id="4c5ea-142">Access control mechanisms also guard against unapproved physical, logical, or remote access to the Office 365 production environment.</span></span>

<span data-ttu-id="4c5ea-143">Sono disponibili tre categorie di controlli di accesso utilizzati da Microsoft per l'utilizzo di Office 365:</span><span class="sxs-lookup"><span data-stu-id="4c5ea-143">There are three categories of access controls used by Microsoft for operating Office 365:</span></span>

- <span data-ttu-id="4c5ea-144">Controlli di isolamento</span><span class="sxs-lookup"><span data-stu-id="4c5ea-144">Isolation Controls</span></span>
- <span data-ttu-id="4c5ea-145">Controlli del personale</span><span class="sxs-lookup"><span data-stu-id="4c5ea-145">Personnel Controls</span></span>
- <span data-ttu-id="4c5ea-146">Controlli di tecnologia</span><span class="sxs-lookup"><span data-stu-id="4c5ea-146">Technology Controls</span></span>

<span data-ttu-id="4c5ea-147">Quando vengono combinati, questi controlli consentono di prevenire e rilevare azioni dannose in Office 365.</span><span class="sxs-lookup"><span data-stu-id="4c5ea-147">When combined, these controls help prevent and detect malicious actions in Office 365.</span></span> <span data-ttu-id="4c5ea-148">Oltre ai controlli di isolamento, del personale e della tecnologia utilizzati da Microsoft, esiste una quarta categoria di controlli: quelli implementati dai clienti.</span><span class="sxs-lookup"><span data-stu-id="4c5ea-148">In addition to the isolation, personnel, and technology controls used by Microsoft, there is a fourth category of controls: those implemented by customers.</span></span>

<span data-ttu-id="4c5ea-149">Office 365 consente di gestire i dati allo stesso modo in cui i dati vengono gestiti in ambienti locali.</span><span class="sxs-lookup"><span data-stu-id="4c5ea-149">Office 365 allows you to manage data the same way data is managed in on-premises environments.</span></span> <span data-ttu-id="4c5ea-150">La persona che firma un'organizzazione per Office 365 diventa automaticamente un amministratore globale.</span><span class="sxs-lookup"><span data-stu-id="4c5ea-150">The person who signs up an organization for Office 365 automatically becomes a global administrator.</span></span> <span data-ttu-id="4c5ea-151">L'amministratore globale ha accesso a tutte le funzionalità nei portali di gestione e può:</span><span class="sxs-lookup"><span data-stu-id="4c5ea-151">The global admin has access to all features in Management Portals and can:</span></span>

- <span data-ttu-id="4c5ea-152">Creare o modificare gli utenti</span><span class="sxs-lookup"><span data-stu-id="4c5ea-152">Create or edit users</span></span>
- <span data-ttu-id="4c5ea-153">Assegnare ruoli di amministratore ad altri utenti</span><span class="sxs-lookup"><span data-stu-id="4c5ea-153">Assign admin roles to others</span></span>
- <span data-ttu-id="4c5ea-154">Reimposta password utente</span><span class="sxs-lookup"><span data-stu-id="4c5ea-154">Reset user passwords</span></span>
- <span data-ttu-id="4c5ea-155">Gestire le licenze utente</span><span class="sxs-lookup"><span data-stu-id="4c5ea-155">Manage user licenses</span></span>
- <span data-ttu-id="4c5ea-156">Gestisci domini</span><span class="sxs-lookup"><span data-stu-id="4c5ea-156">Manage domains</span></span>
- <span data-ttu-id="4c5ea-157">Approvare le richieste dell'archivio clienti</span><span class="sxs-lookup"><span data-stu-id="4c5ea-157">Approve Customer Lockbox requests</span></span>

<span data-ttu-id="4c5ea-158">È consigliabile che ogni organizzazione configuri almeno due account di amministratore.</span><span class="sxs-lookup"><span data-stu-id="4c5ea-158">We recommend that each organization configure at least two admin accounts.</span></span> <span data-ttu-id="4c5ea-159">Per le organizzazioni aziendali di grandi dimensioni, è consigliabile disporre di account di amministrazione specializzati che svolgono funzioni diverse.</span><span class="sxs-lookup"><span data-stu-id="4c5ea-159">For large enterprise organizations, we recommend specialized admin accounts that serve different functions.</span></span>

<span data-ttu-id="4c5ea-160">Per informazioni sull'assegnazione di ruoli e autorizzazioni di amministratore, vedere [assegnazione di ruoli di amministratore in office 365](https://support.office.com/article/Assigning-admin-roles-in-Office-365-eac4d046-1afd-4f1a-85fc-8219c79e1504) e [informazioni sui ruoli di amministratore di Office 365](https://support.office.com/article/Permissions-in-Office-365-DA585EEA-F576-4F55-A1E0-87090B6AAA9D).</span><span class="sxs-lookup"><span data-stu-id="4c5ea-160">For information about assigning admin roles and permissions, see [Assigning admin roles in Office 365](https://support.office.com/article/Assigning-admin-roles-in-Office-365-eac4d046-1afd-4f1a-85fc-8219c79e1504) and [About Office 365 admin roles](https://support.office.com/article/Permissions-in-Office-365-DA585EEA-F576-4F55-A1E0-87090B6AAA9D).</span></span>

## <a name="related-links"></a><span data-ttu-id="4c5ea-161">Collegamenti correlati</span><span class="sxs-lookup"><span data-stu-id="4c5ea-161">Related Links</span></span>

- [<span data-ttu-id="4c5ea-162">Controlli di isolamento</span><span class="sxs-lookup"><span data-stu-id="4c5ea-162">Isolation Controls</span></span>](office-365-isolation-controls.md)
- [<span data-ttu-id="4c5ea-163">Controlli del personale</span><span class="sxs-lookup"><span data-stu-id="4c5ea-163">Personnel Controls</span></span>](office-365-personnel-controls.md)
- [<span data-ttu-id="4c5ea-164">Controlli di tecnologia</span><span class="sxs-lookup"><span data-stu-id="4c5ea-164">Technology Controls</span></span>](office-365-technology-controls.md)
- [<span data-ttu-id="4c5ea-165">Monitoraggio e controllo dei controlli di accesso </span><span class="sxs-lookup"><span data-stu-id="4c5ea-165">Monitoring and Auditing Access Controls</span></span>](office-365-monitoring-and-auditing-access-controls.md)
- [<span data-ttu-id="4c5ea-166">Controlli di accesso di Yammer Enterprise</span><span class="sxs-lookup"><span data-stu-id="4c5ea-166">Yammer Enterprise Access Controls</span></span>](office-365-yammer-enterprise-access-controls.md)