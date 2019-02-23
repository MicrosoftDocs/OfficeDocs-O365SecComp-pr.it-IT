---
title: Proteggere le app con Controllo app per l'accesso condizionale di Office 365 Cloud App Security
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.reviewer: alesibov
ms.audience: Admin
ms.topic: reference
ms.date: 02/14/2019
ms.service: O365-seccomp
localization_priority: Normal
description: Interrompere le violazioni e le perdite in tempo reale con Office 365 cloud app Security Conditional Access App Control.
ms.openlocfilehash: 23c4b29e86eb8ba92cfa8a544d6484965ec6372b
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/23/2019
ms.locfileid: "30217086"
---
# <a name="protect-apps-with-office-365-cloud-app-security-conditional-access-app-control"></a><span data-ttu-id="b836a-103">Proteggere le app con Controllo app per l'accesso condizionale di Office 365 Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="b836a-103">Protect apps with Office 365 Cloud App Security Conditional Access App Control</span></span>

|<span data-ttu-id="b836a-104">Valutazione \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="b836a-104">\*\*\*\*Evaluation\*\* \>\*\*</span></span>|<span data-ttu-id="b836a-105">Planning \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="b836a-105">\*\*\*\*Planning\*\* \>\*\*</span></span>|<span data-ttu-id="b836a-106">Distribuzione \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="b836a-106">\*\*\*\*Deployment\*\* \>\*\*</span></span>|<span data-ttu-id="b836a-107">Utilizzo \* \* \* \*</span><span class="sxs-lookup"><span data-stu-id="b836a-107">\*\*\*\*Utilization\*\*\*\*</span></span>|
|:-----|:-----|:-----|:-----|
|[<span data-ttu-id="b836a-108">Iniziare a valutare</span><span class="sxs-lookup"><span data-stu-id="b836a-108">Start evaluating</span></span>](office-365-cas-overview.md) <br/> |[<span data-ttu-id="b836a-109">Avviare la pianificazione</span><span class="sxs-lookup"><span data-stu-id="b836a-109">Start planning</span></span>](get-ready-for-office-365-cas.md) <br/> |<span data-ttu-id="b836a-110">Sei qui!</span><span class="sxs-lookup"><span data-stu-id="b836a-110">You are here!</span></span>  <br/> [<span data-ttu-id="b836a-111">Passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="b836a-111">Next step</span></span>](ocas-deploy-conditional-access-app-control.md) <br/> |[<span data-ttu-id="b836a-112">Iniziare a utilizzare</span><span class="sxs-lookup"><span data-stu-id="b836a-112">Start utilizing</span></span>](utilization-activities-for-ocas.md) <br/> |

<span data-ttu-id="b836a-p101">Nei luoghi di lavoro odierni, spesso non è sufficiente sapere cosa succede nell'ambiente cloud dopo il fatto. Si desidera arrestare le violazioni e le perdite in tempo reale, prima che i dipendenti imposti intenzionalmente o inavvertitamente i dati e l'organizzazione a rischio. È importante consentire agli utenti dell'organizzazione di sfruttare al meglio i servizi e gli strumenti disponibili nelle app cloud e far funzionare i propri dispositivi. Allo stesso tempo, è necessario disporre di strumenti che consentano di proteggere l'organizzazione dalle perdite di dati e dal furto dei dati in tempo reale. Insieme a Azure Active Directory, Office 365 cloud app Security offre queste funzionalità in un'esperienza olistica e integrata con il controllo delle app con accesso condizionale.</span><span class="sxs-lookup"><span data-stu-id="b836a-p101">In today’s workplace, it’s often not enough to know what’s happening in your cloud environment after the fact. You want to stop breaches and leaks in real time, before employees intentionally or inadvertently put your data and your organization at risk. It's important to enable users in your organization to make the most of the services and tools available to them in cloud apps, and let them bring their own devices to work. At the same time, you need tools to help protect your organization from data leaks, and data theft, in real time. Together with Azure Active Directory, Office 365 Cloud App Security delivers these capabilities in a holistic and integrated experience with Conditional Access App Control.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b836a-118">per utilizzare il controllo delle app per l'accesso condizionale di cloud app security, è necessaria una  [licenza di Azure active Directory P1](https://azure.microsoft.com/pricing/details/active-directory/)e una sottoscrizione di sicurezza per l'app di [Office 365 cloud](office-365-cas-overview.md) attiva.</span><span class="sxs-lookup"><span data-stu-id="b836a-118">To use Cloud App Security Conditional Access App Control, you need an [Azure Active Directory P1 license](https://azure.microsoft.com/pricing/details/active-directory/) and an active [Office 365 Cloud App Security](office-365-cas-overview.md) subscription.</span></span>

## <a name="how-it-works"></a><span data-ttu-id="b836a-119">Funzionamento</span><span class="sxs-lookup"><span data-stu-id="b836a-119">How it works</span></span>

<span data-ttu-id="b836a-p102">Controllo delle app di accesso condizionale utilizza un'architettura proxy inverso ed è integrato in modo univoco con l'accesso condizionale di Azure AD. L'accesso condizionale di Azure AD consente di applicare i controlli di accesso alle app dell'organizzazione in base a determinate condizioni. Le condizioni definiscono *chi* (utente o gruppo di utenti) e *cosa* (quali app Cloud) e *dove* (quali posizioni e reti) viene applicato un criterio di accesso condizionale. Dopo aver determinato le condizioni, è possibile instradare gli utenti a Office 365 cloud app Security, in cui è possibile proteggere i dati con il controllo delle app con accesso condizionale applicando controlli di accesso e di sessione.</span><span class="sxs-lookup"><span data-stu-id="b836a-p102">Conditional Access App Control uses a reverse proxy architecture and is uniquely integrated with Azure AD conditional access. Azure AD conditional access allows you to enforce access controls on your organization’s apps based on certain conditions. The conditions define *who* (user or group of users) and *what* (which cloud apps) and *where* (which locations and networks) a conditional access policy is applied to. After you’ve determined the conditions, you can route users to Office 365 Cloud App Security where you can protect data with Conditional Access App Control by applying access and session controls.</span></span>

<span data-ttu-id="b836a-p103">Il controllo delle app con accesso condizionale consente di monitorare e controllare le sessioni e l'accesso alle app degli utenti in tempo reale in base ai criteri di accesso e di sessione. I criteri di accesso e di sessione vengono utilizzati all'interno del portale cloud app Security per affinare ulteriormente i filtri e impostare azioni da intraprendere su un utente. Con i criteri di accesso e sessione, è possibile:</span><span class="sxs-lookup"><span data-stu-id="b836a-p103">Conditional Access App Control enables user app access and sessions to be monitored and controlled in real time based on access and session policies. Access and session policies are used within the Cloud App Security portal to further refine filters and set actions to be taken on a user. With the access and session policies, you can:</span></span>

- <span data-ttu-id="b836a-p104">**Blocca al download**: è possibile bloccare il download di documenti riservati. Ad esempio, nei dispositivi non gestiti.</span><span class="sxs-lookup"><span data-stu-id="b836a-p104">**Block on download**: You can block the download of sensitive documents. For example, on unmanaged devices.</span></span>

- <span data-ttu-id="b836a-p105">**Protect on download**: invece di bloccare il download di documenti sensibili, è possibile richiedere la protezione dei documenti tramite la crittografia al download. Questa crittografia garantisce che il documento sia protetto e che l'accesso utente sia autenticato se i dati vengono scaricati in un dispositivo non attendibile.</span><span class="sxs-lookup"><span data-stu-id="b836a-p105">**Protect on download**: Instead of blocking the download of sensitive documents, you can require documents to be protected via encryption on download. This encryption makes sure the document is protected and user access is authenticated if the data is downloaded to an untrusted device.</span></span>

- <span data-ttu-id="b836a-p106">**Monitorare le sessioni utente poco attendibili**: gli utenti rischiosi vengono monitorati quando eseguono l'accesso alle app e le loro azioni vengono registrate dall'interno della sessione. È possibile esaminare e analizzare il comportamento degli utenti per comprendere dove e in quali condizioni devono essere applicati i criteri di sessione in futuro.</span><span class="sxs-lookup"><span data-stu-id="b836a-p106">**Monitor low-trust user sessions**: Risky users are monitored when they sign into apps and their actions are logged from within the session. You can investigate and analyze user behavior to understand where, and under what conditions, session policies should be applied in the future.</span></span>

- <span data-ttu-id="b836a-133">**Blocca accesso**: è possibile bloccare completamente l'accesso a specifiche app per gli utenti provenienti da dispositivi non gestiti o da reti non aziendali.</span><span class="sxs-lookup"><span data-stu-id="b836a-133">**Block access**: You can completely block access to specific apps for users coming from unmanaged devices or from non-corporate networks.</span></span>

- <span data-ttu-id="b836a-134">**Creare la modalità**di sola lettura: monitorando e bloccando le attività personalizzate in-app, è possibile creare una modalità di sola lettura per applicazioni specifiche per utenti specifici.</span><span class="sxs-lookup"><span data-stu-id="b836a-134">**Create read-only mode**: By monitoring and blocking custom in-app activities, you can create a read-only mode to specific apps for specific users.</span></span>

- <span data-ttu-id="b836a-p107">**Limitare le sessioni utente da reti non aziendali**: gli utenti che accedono a un'app protetta da una posizione che non fa parte della rete aziendale sono autorizzati ad accedere con restrizioni. Il download dei materiali sensibili è bloccato o protetto.</span><span class="sxs-lookup"><span data-stu-id="b836a-p107">**Restrict user sessions from non-corporate networks**: Users accessing a protected app from a location that isn't part of your corporate network are allowed restricted access. The download of sensitive materials is blocked or protected.</span></span>

### <a name="how-session-control-works"></a><span data-ttu-id="b836a-137">Funzionamento del controllo sessione</span><span class="sxs-lookup"><span data-stu-id="b836a-137">How session control works</span></span>

<span data-ttu-id="b836a-p108">La creazione di un criterio di sessione con il controllo delle app di accesso condizionale consente di controllare le sessioni degli utenti reindirizzando l'utente tramite un proxy inverso anziché direttamente all'app. Da questo punto in poi, le richieste degli utenti e le risposte passano attraverso Office 365 cloud app Security invece che direttamente all'app.</span><span class="sxs-lookup"><span data-stu-id="b836a-p108">Creating a session policy with Conditional Access App Control enables you to control user sessions by redirecting the user through a reverse proxy instead of directly to the app. From then on, user requests and responses go through Office 365 Cloud App Security rather than directly to the app.</span></span>

<span data-ttu-id="b836a-p109">Per mantenere l'utente all'interno della sessione, tutti gli URL rilevanti, gli script Java e i cookie all'interno della sessione dell'app vengono sostituiti con gli URL di sicurezza delle app cloud di Office 365. Ad esempio, se l'app restituisce una pagina con collegamenti i cui domini terminano con myapp.com, il collegamento viene sostituito con domini che terminano con qualcosa di simile a: myapp.com.us.cas.ms</span><span class="sxs-lookup"><span data-stu-id="b836a-p109">To keep the user within the session, all the relevant URLs, Java scripts, and cookies within the app session are replaced with Office 365 Cloud App Security URLs. For example, if the app returns a page with links whose domains end with myapp.com, the link is replaced with domains ending with something like: myapp.com.us.cas.ms</span></span>

<span data-ttu-id="b836a-p110">Questo metodo non richiede l'installazione di alcuna operazione sul dispositivo. Questo metodo è ideale per il monitoraggio di sessioni provenienti da dispositivi non gestiti.</span><span class="sxs-lookup"><span data-stu-id="b836a-p110">This method doesn't require you to install anything on the device. This method is ideal when monitoring sessions from unmanaged devices.</span></span>

<span data-ttu-id="b836a-144">Dopo aver diretto una sessione tramite Office 365 cloud app Security, è possibile eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="b836a-144">After a session is directed through Office 365 Cloud App Security, the following actions can be done:</span></span>

1. <span data-ttu-id="b836a-145">Esaminare il traffico per le attività degli utenti</span><span class="sxs-lookup"><span data-stu-id="b836a-145">Inspect the traffic for user activities</span></span>

2. <span data-ttu-id="b836a-146">Visualizzare le attività identificate nel registro attività di protezione di Office 365 cloud app Security</span><span class="sxs-lookup"><span data-stu-id="b836a-146">Display the identified activities in the Office 365 Cloud App Security Activity log</span></span>

3. <span data-ttu-id="b836a-147">Salvare i log del traffico e analizzarli</span><span class="sxs-lookup"><span data-stu-id="b836a-147">Save the traffic logs and analyze them</span></span>

4. <span data-ttu-id="b836a-148">Consentire all'amministratore di esportare i log del traffico</span><span class="sxs-lookup"><span data-stu-id="b836a-148">Enable the admin to export the traffic logs</span></span>

5. <span data-ttu-id="b836a-149">Applicare i criteri nella sessione</span><span class="sxs-lookup"><span data-stu-id="b836a-149">Enforce policies on the session</span></span>

## <a name="managed-device-identification"></a><span data-ttu-id="b836a-150">Identificazione del dispositivo gestito</span><span class="sxs-lookup"><span data-stu-id="b836a-150">Managed device identification</span></span>

<span data-ttu-id="b836a-p111">Il controllo delle app con accesso condizionale consente di creare criteri che considerano se un dispositivo viene gestito o meno. Per determinare se un dispositivo è gestito o meno, la caratteristica utilizza:</span><span class="sxs-lookup"><span data-stu-id="b836a-p111">Conditional Access App Control enables you to create policies that take into account whether a device is managed or not. To identify whether a device is managed or not, the feature uses:</span></span>

- <span data-ttu-id="b836a-153">Dispositivi conformi</span><span class="sxs-lookup"><span data-stu-id="b836a-153">Compliant devices</span></span>

- <span data-ttu-id="b836a-154">Dispositivi associati a un dominio</span><span class="sxs-lookup"><span data-stu-id="b836a-154">Domain-joined devices</span></span>

- <span data-ttu-id="b836a-155">Distribuzione dei certificati client</span><span class="sxs-lookup"><span data-stu-id="b836a-155">Client certificates deployment</span></span>

### <a name="compliant-and-domain-joined-devices"></a><span data-ttu-id="b836a-156">Dispositivi conformi e appartenenti al dominio</span><span class="sxs-lookup"><span data-stu-id="b836a-156">Compliant and domain-joined devices</span></span>

<span data-ttu-id="b836a-p112">L'accesso condizionale di Azure AD consente di passare direttamente alla sicurezza delle app cloud di Office 365. Da qui, è possibile sviluppare un criterio di accesso o un criterio di sessione che utilizza lo stato del dispositivo come filtro. Per ulteriori informazioni, vedere l' [Introduzione alla gestione dei dispositivi in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/device-management-introduction).</span><span class="sxs-lookup"><span data-stu-id="b836a-p112">Azure AD conditional access enables compliant and domain-joined device information to be passed directly to Office 365 Cloud App Security. From there, an access policy or a session policy can be developed that uses device state as a filter. For more information, see the [Introduction to device management in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/device-management-introduction).</span></span>

### <a name="client-certificate-authenticated-devices"></a><span data-ttu-id="b836a-160">Dispositivi autenticati del certificato client</span><span class="sxs-lookup"><span data-stu-id="b836a-160">Client-certificate authenticated devices</span></span>

<span data-ttu-id="b836a-p113">Il meccanismo di identificazione del dispositivo può richiedere l'autenticazione dai dispositivi rilevanti utilizzando i certificati client. È possibile utilizzare i certificati client esistenti già distribuiti nell'organizzazione o distribuire nuovi certificati client ai dispositivi gestiti. È quindi possibile utilizzare la presenza di tali certificati per impostare i criteri di accesso e di sessione. Per informazioni su come distribuire i certificati client, vedere [deploy CONDIZIONAL Access App Control for Office 365 Apps](ocas-deploy-conditional-access-app-control.md).</span><span class="sxs-lookup"><span data-stu-id="b836a-p113">The device identification mechanism can request authentication from relevant devices using client certificates. You can either use existing client certificates already deployed in your organization or roll out new client certificates to managed devices. You then use the presence of those certificates to set access and session policies. For information on how to deploy client certificates see [Deploy Conditional Access App Control for Office 365 apps](ocas-deploy-conditional-access-app-control.md).</span></span>

## <a name="supported-apps-and-clients"></a><span data-ttu-id="b836a-165">App e client supportati</span><span class="sxs-lookup"><span data-stu-id="b836a-165">Supported apps and clients</span></span>

<span data-ttu-id="b836a-166">Il controllo delle app di accesso condizionale per Office 365 supporta le seguenti app in primo piano:</span><span class="sxs-lookup"><span data-stu-id="b836a-166">Conditional Access App Control for Office 365 supports the following featured apps:</span></span>

- <span data-ttu-id="b836a-167">Exchange Online (anteprima)</span><span class="sxs-lookup"><span data-stu-id="b836a-167">Exchange Online (preview)</span></span>

- <span data-ttu-id="b836a-168">OneDrive for business (anteprima)</span><span class="sxs-lookup"><span data-stu-id="b836a-168">OneDrive for Business (preview)</span></span>

- <span data-ttu-id="b836a-169">Power BI (anteprima)</span><span class="sxs-lookup"><span data-stu-id="b836a-169">Power BI (preview)</span></span>

- <span data-ttu-id="b836a-170">SharePoint Online (anteprima)</span><span class="sxs-lookup"><span data-stu-id="b836a-170">SharePoint Online (preview)</span></span>

- <span data-ttu-id="b836a-171">Microsoft Teams (anteprima)</span><span class="sxs-lookup"><span data-stu-id="b836a-171">Microsoft Teams (preview)</span></span>

- <span data-ttu-id="b836a-172">Yammer (anteprima)</span><span class="sxs-lookup"><span data-stu-id="b836a-172">Yammer (preview)</span></span>

<span data-ttu-id="b836a-173">Altre app vengono continuamente attivate per il controllo delle sessioni.</span><span class="sxs-lookup"><span data-stu-id="b836a-173">Additional apps are being continuously on-boarded to session control.</span></span>

## <a name="next-steps"></a><span data-ttu-id="b836a-174">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="b836a-174">Next steps</span></span>

- [<span data-ttu-id="b836a-175">Distribuire Controllo app per l'accesso condizionale per le app di Office 365</span><span class="sxs-lookup"><span data-stu-id="b836a-175">Deploy Conditional Access App Control for Office 365 apps</span></span>](ocas-deploy-conditional-access-app-control.md)

- [<span data-ttu-id="b836a-176">Informazioni sui criteri di sessione in Office 365 cloud app Security</span><span class="sxs-lookup"><span data-stu-id="b836a-176">Learn about session policies in Office 365 Cloud App Security</span></span>](ocas-session-policies.md)

- [<span data-ttu-id="b836a-177">Informazioni sui criteri di accesso in Office 365 cloud app Security</span><span class="sxs-lookup"><span data-stu-id="b836a-177">Learn about access policies in Office 365 Cloud App Security</span></span>](ocas-access-policies.md) 