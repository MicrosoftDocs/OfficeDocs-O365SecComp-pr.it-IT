---
title: Configurare un elenco di URL bloccati personalizzato utilizzando i collegamenti sicuri ATP di Office 365
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.audience: Admin
ms.topic: article
ms.date: 02/06/2019
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 896a7efb-1683-465e-a394-261349e5d866
ms.collection: M365-security-compliance
description: Informazioni su come configurare un elenco di URL bloccati per l'organizzazione utilizzando Office 365 Advanced Threat Protection. Gli URL bloccati verranno applicati ai messaggi di posta elettronica e ai documenti di Office in base ai criteri dei collegamenti sicuri di ATP.
ms.openlocfilehash: ad9c613221b94e61022b11541ee068e35e47cc70
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/23/2019
ms.locfileid: "30213026"
---
# <a name="set-up-a-custom-blocked-urls-list-using-office-365-atp-safe-links"></a><span data-ttu-id="6234b-104">Configurare un elenco di URL bloccati personalizzato utilizzando i collegamenti sicuri ATP di Office 365</span><span class="sxs-lookup"><span data-stu-id="6234b-104">Set up a custom blocked URLs list using Office 365 ATP Safe Links</span></span>

> [!IMPORTANT]
> <span data-ttu-id="6234b-p102">Questo articolo è destinato ai clienti aziendali. Se si è un utente di casa che cerca informazioni sui collegamenti sicuri in Outlook, vedere [Advanced Outlook.com Security](https://support.office.com/article/advanced-outlook-com-security-for-office-365-subscribers-882d2243-eab9-4545-a58a-b36fee4a46e2).</span><span class="sxs-lookup"><span data-stu-id="6234b-p102">This article is intended for business customers. If you are a home user looking for information about Safe Links in Outlook, see [Advanced Outlook.com security](https://support.office.com/article/advanced-outlook-com-security-for-office-365-subscribers-882d2243-eab9-4545-a58a-b36fee4a46e2).</span></span>

<span data-ttu-id="6234b-p103">Con [Office 365 Advanced Threat Protection](office-365-atp.md) (ATP), l'organizzazione può disporre di un elenco personalizzato di indirizzi Web (URL) bloccati. Quando viene bloccato un URL, gli utenti che fanno clic sui collegamenti all'URL bloccato vengono indirizzati a una [pagina di avviso](atp-safe-links-warning-pages.md) simile all'immagine seguente:</span><span class="sxs-lookup"><span data-stu-id="6234b-p103">With [Office 365 Advanced Threat Protection](office-365-atp.md) (ATP), your organization can have a custom list of website addresses (URLs) that are blocked. When a URL is blocked, people who click on links to the blocked URL are taken to a [warning page](atp-safe-links-warning-pages.md) that resembles the following image:</span></span> 
  
![Questo sito è bloccato](media/6b4bda2d-a1e6-419e-8b10-588e83c3af3f.png)
  
<span data-ttu-id="6234b-110">L'elenco degli URL bloccati è definito dal team di sicurezza di Office 365 dell'organizzazione e questo elenco si applica a tutti gli utenti dell'organizzazione che sono soggetti ai criteri dei collegamenti sicuri di Office 365 ATP.</span><span class="sxs-lookup"><span data-stu-id="6234b-110">The blocked URLs list is defined by your organization's Office 365 security team, and that list applies to everyone in the organization who is covered by Office 365 ATP Safe Links policies.</span></span> 
  
<span data-ttu-id="6234b-111">Leggere questo articolo per informazioni su come configurare l'elenco degli URL bloccati personalizzati dell'organizzazione per i [collegamenti sicuri di ATP in Office 365](atp-safe-links.md).</span><span class="sxs-lookup"><span data-stu-id="6234b-111">Read this article to learn how to set up your organization's custom blocked URLs list for [ATP Safe Links in Office 365](atp-safe-links.md).</span></span>
  
## <a name="view-or-edit-a-custom-list-of-blocked-urls"></a><span data-ttu-id="6234b-112">Visualizzazione o modifica di un elenco personalizzato di URL bloccati</span><span class="sxs-lookup"><span data-stu-id="6234b-112">View or edit a custom list of blocked URLs</span></span>

<span data-ttu-id="6234b-p104">I [collegamenti sicuri di ATP in Office 365](atp-safe-links.md) utilizzano diversi elenchi, tra cui l'elenco URL bloccati personalizzato dell'organizzazione. Se si dispone delle autorizzazioni necessarie, è possibile configurare l'elenco personalizzato dell'organizzazione. A tale scopo, modificare il criterio collegamenti sicuri predefinito dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="6234b-p104">[ATP Safe Links in Office 365](atp-safe-links.md) uses several lists, including your organization's custom blocked URLs list. If you have the necessary permissions, you can set up your organization's custom list. You do this by editing your organization's default Safe Links policy.</span></span>

<span data-ttu-id="6234b-116">Per modificare (o definire) i criteri ATP, è necessario essere assegnati a uno dei ruoli descritti nella tabella seguente:</span><span class="sxs-lookup"><span data-stu-id="6234b-116">To edit (or define) ATP policies, you must be assigned one of the roles described in the following table:</span></span> 

|<span data-ttu-id="6234b-117">Ruolo</span><span class="sxs-lookup"><span data-stu-id="6234b-117">Role</span></span>  |<span data-ttu-id="6234b-118">Dove/come assegnato</span><span class="sxs-lookup"><span data-stu-id="6234b-118">Where/how assigned</span></span>  |
|---------|---------|
|<span data-ttu-id="6234b-119">Amministratore globale di Office 365</span><span class="sxs-lookup"><span data-stu-id="6234b-119">Office 365 Global Administrator</span></span> |<span data-ttu-id="6234b-p105">Per impostazione predefinita, la persona che si iscrive all'acquisto di Office 365 è un amministratore globale. Per ulteriori informazioni, vedere [informazioni sui ruoli di amministratore di Office 365](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles) .</span><span class="sxs-lookup"><span data-stu-id="6234b-p105">The person who signs up to buy Office 365 is a global admin by default. (See [About Office 365 admin roles](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles) to learn more.)</span></span>         |
|<span data-ttu-id="6234b-122">Amministratore della sicurezza</span><span class="sxs-lookup"><span data-stu-id="6234b-122">Security Administrator</span></span> |<span data-ttu-id="6234b-123">Interfaccia di amministrazione di Azure Active[https://aad.portal.azure.com](https://aad.portal.azure.com)directory ()</span><span class="sxs-lookup"><span data-stu-id="6234b-123">Azure Active Directory admin center ([https://aad.portal.azure.com](https://aad.portal.azure.com))</span></span>|
|<span data-ttu-id="6234b-124">Gestione dell'organizzazione di Exchange Online</span><span class="sxs-lookup"><span data-stu-id="6234b-124">Exchange Online Organization Management</span></span> |<span data-ttu-id="6234b-125">Interfaccia di amministrazione di[https://outlook.office365.com/ecp](https://outlook.office365.com/ecp)Exchange ()</span><span class="sxs-lookup"><span data-stu-id="6234b-125">Exchange admin center ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp))</span></span> <br><span data-ttu-id="6234b-126">oppure</span><span class="sxs-lookup"><span data-stu-id="6234b-126">or</span></span> <br>  <span data-ttu-id="6234b-127">Cmdlet di PowerShell (vedere [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps))</span><span class="sxs-lookup"><span data-stu-id="6234b-127">PowerShell cmdlets (See [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps))</span></span> |

> [!TIP]
> <span data-ttu-id="6234b-128">Per ulteriori informazioni sui ruoli e sulle autorizzazioni, vedere perMissions [in the &amp; Office 365 Security Compliance Center](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="6234b-128">To learn more about roles and permissions, see [Permissions in the Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

### <a name="to-view-or-edit-a-custom-blocked-urls-list"></a><span data-ttu-id="6234b-129">Per visualizzare o modificare un elenco di URL bloccati personalizzato</span><span class="sxs-lookup"><span data-stu-id="6234b-129">To view or edit a custom blocked URLs list</span></span>
  
1. <span data-ttu-id="6234b-130">Accedere a [https://protection.office.com](https://protection.office.com) e accedere con l'account aziendale o dell'Istituto di istruzione.</span><span class="sxs-lookup"><span data-stu-id="6234b-130">Go to [https://protection.office.com](https://protection.office.com) and sign in with your work or school account.</span></span> 
    
2. <span data-ttu-id="6234b-131">Nella barra di spostamento a sinistra, in **gestione minacce**, scegliere **collegamenti sicuri**per i **criteri** \> .</span><span class="sxs-lookup"><span data-stu-id="6234b-131">In the left navigation, under **Threat management**, choose **Policy** \> **Safe Links**.</span></span>
    
3. <span data-ttu-id="6234b-132">Nei **criteri che si applicano all'intera sezione organizzazione** selezionare **predefinita**e quindi fare clic su **modifica** (il pulsante modifica è simile a una matita).</span><span class="sxs-lookup"><span data-stu-id="6234b-132">In the **Policies that apply to the entire organization** section, select **Default**, and then choose **Edit** (the Edit button resembles a pencil).</span></span><br/><span data-ttu-id="6234b-133">![Fare clic su modifica per modificare il criterio predefinito per la protezione dei collegamenti sicuri](media/d08f9615-d947-4033-813a-d310ec2c8cca.png)</span><span class="sxs-lookup"><span data-stu-id="6234b-133">![Click Edit to edit your default policy for Safe Links protection](media/d08f9615-d947-4033-813a-d310ec2c8cca.png)</span></span><br/><span data-ttu-id="6234b-p106">In questo modo è possibile visualizzare l'elenco degli URL bloccati. All'inizio, potrebbe non essere presente alcun URL.</span><span class="sxs-lookup"><span data-stu-id="6234b-p106">This enables you to view your list of blocked URLs. At first, you might not have any URLs listed here.</span></span><br/><span data-ttu-id="6234b-136">![Elenco degli URL bloccati nel criterio collegamenti sicuri predefinito](media/575e1449-6191-40ac-b626-030a2fd3fb11.png)</span><span class="sxs-lookup"><span data-stu-id="6234b-136">![Blocked URLs list in the default Safe Links policy](media/575e1449-6191-40ac-b626-030a2fd3fb11.png)</span></span>
  
4. <span data-ttu-id="6234b-137">Selezionare la casella **immettere un URL valido** , digitare un URL e quindi scegliere il segno di addizione**+**().</span><span class="sxs-lookup"><span data-stu-id="6234b-137">Select the **Enter a valid URL** box, type a URL, and then choose the plus sign (**+**).</span></span> 

5. <span data-ttu-id="6234b-138">Dopo aver aggiunto gli URL, fare clic su **Salva**nell'angolo in basso a destra dello schermo.</span><span class="sxs-lookup"><span data-stu-id="6234b-138">When you are finished adding URLs, in the lower right corner of the screen, choose **Save**.</span></span>
    
## <a name="a-few-things-to-keep-in-mind"></a><span data-ttu-id="6234b-139">Alcuni aspetti da tenere presenti</span><span class="sxs-lookup"><span data-stu-id="6234b-139">A few things to keep in mind</span></span>

<span data-ttu-id="6234b-140">Quando si aggiungono URL all'elenco, tenere presente quanto segue:</span><span class="sxs-lookup"><span data-stu-id="6234b-140">While you add URLs to your list, keep the following points in mind:</span></span> 

- <span data-ttu-id="6234b-p107">Non includere una barra ( **/**) alla fine dell'URL. Ad esempio, invece di immettere `http://www.contoso.com/`, immetti `http://www.contoso.com`.</span><span class="sxs-lookup"><span data-stu-id="6234b-p107">Do not include a forward slash ( **/**) at the end of the URL. For example, instead of entering `http://www.contoso.com/`, enter `http://www.contoso.com`.</span></span>
    
- <span data-ttu-id="6234b-p108">È possibile specificare un URL di solo dominio (come `contoso.com` or `tailspintoys.com`). Questo bloccherà gli scatti su qualsiasi URL che contiene il dominio.</span><span class="sxs-lookup"><span data-stu-id="6234b-p108">You can specify a domain-only URL (like `contoso.com` or `tailspintoys.com`). This will block clicks on any URL that contains the domain.</span></span>

- <span data-ttu-id="6234b-p109">È possibile specificare un sottodominio (come `toys.contoso.com*`) senza bloccare un dominio completo (come `contoso.com`). Questo blocco farà clic su qualsiasi URL contenente il sottodominio, ma non bloccherà i clic su un URL che contiene il dominio completo.</span><span class="sxs-lookup"><span data-stu-id="6234b-p109">You can specify a subdomain (like `toys.contoso.com*`) without blocking a full domain (like `contoso.com`). This will block clicks any URL that contains the subdomain, but it won't block clicks to a URL that contains the full domain.</span></span>  
    
- <span data-ttu-id="6234b-p110">È possibile includere fino a tre asterischi jolly (\*) per URL. Nella tabella seguente sono elencati alcuni esempi di elementi che è possibile immettere e quali sono gli effetti di tali voci.</span><span class="sxs-lookup"><span data-stu-id="6234b-p110">You can include up to three wildcard asterisks (\*) per URL. The following table lists some examples of what you can enter and what effect those entries have.</span></span>
    
|<span data-ttu-id="6234b-149">**Voce di esempio**</span><span class="sxs-lookup"><span data-stu-id="6234b-149">**Example Entry**</span></span>|<span data-ttu-id="6234b-150">**Cosa fa**</span><span class="sxs-lookup"><span data-stu-id="6234b-150">**What It Does**</span></span>|
|:-----|:-----|
|<span data-ttu-id="6234b-151">`contoso.com`o`*contoso.com*`</span><span class="sxs-lookup"><span data-stu-id="6234b-151">`contoso.com` or `*contoso.com*`</span></span>  <br/> |<span data-ttu-id="6234b-152">Blocca il dominio, i sottodomini e i percorsi, ad esempio `https://www.contoso.com` `http://sub.contoso.com`, e`http://contoso.com/abc`</span><span class="sxs-lookup"><span data-stu-id="6234b-152">Blocks the domain, subdomains, and paths, such as `https://www.contoso.com`, `http://sub.contoso.com`, and `http://contoso.com/abc`</span></span>  <br/> |
|`http://contoso.com/a`  <br/> |<span data-ttu-id="6234b-153">Blocca un sito `http://contoso.com/a` , ma non altri percorsi secondari come`http://contoso.com/a/b`</span><span class="sxs-lookup"><span data-stu-id="6234b-153">Blocks a site `http://contoso.com/a` but not additional subpaths like `http://contoso.com/a/b`</span></span>  <br/> |
|`http://contoso.com/a*`  <br/> |<span data-ttu-id="6234b-154">Blocca un sito `http://contoso.com/a` e altri percorsi secondari come`http://contoso.com/a/b`</span><span class="sxs-lookup"><span data-stu-id="6234b-154">Blocks a site `http://contoso.com/a` and additional subpaths like `http://contoso.com/a/b`</span></span>  <br/> |
|`http://toys.contoso.com*`  <br/> |<span data-ttu-id="6234b-155">Blocca un sottodominio ("giocattoli" in questo caso), ma consente di fare clic su altri URL `http://contoso.com` di `http://home.contoso.com`dominio (come or).</span><span class="sxs-lookup"><span data-stu-id="6234b-155">Blocks a subdomain ("toys" in this case) but allow clicks to other domain URLs (like `http://contoso.com` or `http://home.contoso.com`).</span></span>  <br/> |
   

## <a name="how-to-define-exceptions-for-certain-users-in-an-organization"></a><span data-ttu-id="6234b-156">Come definire le eccezioni per alcuni utenti di un'organizzazione</span><span class="sxs-lookup"><span data-stu-id="6234b-156">How to define exceptions for certain users in an organization</span></span>

<span data-ttu-id="6234b-p111">Se si desidera che alcuni gruppi siano in grado di visualizzare gli URL che potrebbero essere bloccati per gli altri utenti, è possibile specificare un criterio per i collegamenti sicuri ATP che si applica a destinatari specifici. Vedere [configurare un elenco di URL "non riscrivere" personalizzato utilizzando i collegamenti sicuri di ATP](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md).</span><span class="sxs-lookup"><span data-stu-id="6234b-p111">If you want certain groups to be able to view URLs that might be blocked for others, you can specify an ATP Safe Links policy that applies to specific recipients. See [Set up a custom "do not rewrite" URLs list using ATP Safe Links](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md).</span></span>
  

