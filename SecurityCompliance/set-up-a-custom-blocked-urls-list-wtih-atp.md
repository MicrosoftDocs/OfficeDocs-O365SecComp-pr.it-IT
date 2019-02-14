---
title: Impostare un elenco di URL bloccato personalizzato con Office 365 degli strumenti di analisi provvisoria collegamenti
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.audience: Admin
ms.topic: article
ms.date: 02/06/2019
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 896a7efb-1683-465e-a394-261349e5d866
ms.collection: M365-security-compliance
description: Informazioni su come configurare un elenco di URL bloccati per l'organizzazione utilizza la protezione di Office 365 avanzate rischio. Gli URL bloccati verranno applicate a messaggi di posta elettronica e documenti di Office in base ai criteri di collegamenti sicuro degli strumenti di analisi.
ms.openlocfilehash: 261d85ce72de3a19ed4c2327d56fe1f32107781b
ms.sourcegitcommit: efccf5b4f22d34a9674bc55ebf3d88bc8bda2972
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/14/2019
ms.locfileid: "29995317"
---
# <a name="set-up-a-custom-blocked-urls-list-using-office-365-atp-safe-links"></a><span data-ttu-id="90f15-104">Impostare un elenco di URL bloccato personalizzato con Office 365 degli strumenti di analisi provvisoria collegamenti</span><span class="sxs-lookup"><span data-stu-id="90f15-104">Set up a custom blocked URLs list using Office 365 ATP Safe Links</span></span>

> [!IMPORTANT]
> <span data-ttu-id="90f15-p102">In questo articolo è destinato ai clienti aziendali. Se si è un utente principale per informazioni su collegamenti sicuro in Outlook, vedere [sicurezza avanzata Outlook.com](https://support.office.com/article/advanced-outlook-com-security-for-office-365-subscribers-882d2243-eab9-4545-a58a-b36fee4a46e2).</span><span class="sxs-lookup"><span data-stu-id="90f15-p102">This article is intended for business customers. If you are a home user looking for information about Safe Links in Outlook, see [Advanced Outlook.com security](https://support.office.com/article/advanced-outlook-com-security-for-office-365-subscribers-882d2243-eab9-4545-a58a-b36fee4a46e2).</span></span>

<span data-ttu-id="90f15-p103">Con [Office 365 avanzate Threat Protection](office-365-atp.md) (degli strumenti di analisi), l'organizzazione può avere un elenco personalizzato di indirizzi di siti Web (URL) che vengono bloccati. Quando viene bloccato un URL, persone, fare clic sui collegamenti all'URL bloccati vengono indirizzate a una [pagina di avviso](atp-safe-links-warning-pages.md) simile all'immagine seguente:</span><span class="sxs-lookup"><span data-stu-id="90f15-p103">With [Office 365 Advanced Threat Protection](office-365-atp.md) (ATP), your organization can have a custom list of website addresses (URLs) that are blocked. When a URL is blocked, people who click on links to the blocked URL are taken to a [warning page](atp-safe-links-warning-pages.md) that resembles the following image:</span></span> 
  
![In questo sito è bloccato](media/6b4bda2d-a1e6-419e-8b10-588e83c3af3f.png)
  
<span data-ttu-id="90f15-110">L'elenco degli URL bloccato è definito dal team di protezione di Office 365 dell'organizzazione e tale elenco si applica a tutti gli utenti dell'organizzazione che sono disponibili i criteri di Office 365 degli strumenti di analisi provvisoria collegamenti.</span><span class="sxs-lookup"><span data-stu-id="90f15-110">The blocked URLs list is defined by your organization's Office 365 security team, and that list applies to everyone in the organization who is covered by Office 365 ATP Safe Links policies.</span></span> 
  
<span data-ttu-id="90f15-111">In questo articolo per informazioni su come configurare personalizzato URL elenco dei domini bloccati dell'organizzazione per [Strumenti di analisi collegamenti attendibili in Office 365](atp-safe-links.md).</span><span class="sxs-lookup"><span data-stu-id="90f15-111">Read this article to learn how to set up your organization's custom blocked URLs list for [ATP Safe Links in Office 365](atp-safe-links.md).</span></span>
  
## <a name="view-or-edit-a-custom-list-of-blocked-urls"></a><span data-ttu-id="90f15-112">Visualizzare o modificare un elenco personalizzato di URL bloccati</span><span class="sxs-lookup"><span data-stu-id="90f15-112">View or edit a custom list of blocked URLs</span></span>

<span data-ttu-id="90f15-p104">[Degli strumenti di analisi collegamenti attendibili in Office 365](atp-safe-links.md) utilizza più elenchi, inclusi personalizzato URL elenco dei domini bloccati dell'organizzazione. Se si dispone delle autorizzazioni necessarie, è possibile impostare elenco personalizzato dell'organizzazione. Ottenere questo risultato modificando i criteri dell'organizzazione predefinito collegamenti sicuri.</span><span class="sxs-lookup"><span data-stu-id="90f15-p104">[ATP Safe Links in Office 365](atp-safe-links.md) uses several lists, including your organization's custom blocked URLs list. If you have the necessary permissions, you can set up your organization's custom list. You do this by editing your organization's default Safe Links policy.</span></span>

<span data-ttu-id="90f15-116">Per modificare o definire i criteri degli strumenti di analisi, è necessario assegnare uno dei ruoli descritti nella tabella riportata di seguito:</span><span class="sxs-lookup"><span data-stu-id="90f15-116">To edit (or define) ATP policies, you must be assigned one of the roles described in the following table:</span></span> 

|<span data-ttu-id="90f15-117">Ruolo</span><span class="sxs-lookup"><span data-stu-id="90f15-117">Role</span></span>  |<span data-ttu-id="90f15-118">Modalità assegnato</span><span class="sxs-lookup"><span data-stu-id="90f15-118">Where/how assigned</span></span>  |
|---------|---------|
|<span data-ttu-id="90f15-119">Amministratore globale di Office 365</span><span class="sxs-lookup"><span data-stu-id="90f15-119">Office 365 Global Administrator</span></span> |<span data-ttu-id="90f15-p105">La persona che iscrizione acquistare Office 365 è un amministratore globale per impostazione predefinita. Vedere [ruoli di amministratore su Office 365](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles) per ulteriori informazioni.</span><span class="sxs-lookup"><span data-stu-id="90f15-p105">The person who signs up to buy Office 365 is a global admin by default. (See [About Office 365 admin roles](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles) to learn more.)</span></span>         |
|<span data-ttu-id="90f15-122">Amministratore della sicurezza</span><span class="sxs-lookup"><span data-stu-id="90f15-122">Security Administrator</span></span> |<span data-ttu-id="90f15-123">Interfaccia di amministrazione di Azure Active Directory ([https://aad.portal.azure.com](https://aad.portal.azure.com))</span><span class="sxs-lookup"><span data-stu-id="90f15-123">Azure Active Directory admin center ([https://aad.portal.azure.com](https://aad.portal.azure.com))</span></span>|
|<span data-ttu-id="90f15-124">Exchange Online Organization Management</span><span class="sxs-lookup"><span data-stu-id="90f15-124">Exchange Online Organization Management</span></span> |<span data-ttu-id="90f15-125">Interfaccia di amministrazione di Exchange ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp))</span><span class="sxs-lookup"><span data-stu-id="90f15-125">Exchange admin center ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp))</span></span> <br><span data-ttu-id="90f15-126">oppure</span><span class="sxs-lookup"><span data-stu-id="90f15-126">or</span></span> <br>  <span data-ttu-id="90f15-127">Cmdlet di PowerShell (vedere [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps))</span><span class="sxs-lookup"><span data-stu-id="90f15-127">PowerShell cmdlets (See [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps))</span></span> |

> [!TIP]
> <span data-ttu-id="90f15-128">Per ulteriori informazioni sui ruoli e autorizzazioni, vedere [autorizzazioni in Office 365 Security &amp; centro conformità](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="90f15-128">To learn more about roles and permissions, see [Permissions in the Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

### <a name="to-view-or-edit-a-custom-blocked-urls-list"></a><span data-ttu-id="90f15-129">Per visualizzare o modificare un elenco degli URL bloccato personalizzato</span><span class="sxs-lookup"><span data-stu-id="90f15-129">To view or edit a custom blocked URLs list</span></span>
  
1. <span data-ttu-id="90f15-130">Accedere a [https://protection.office.com](https://protection.office.com) e accedere con l'account di lavoro o della scuola.</span><span class="sxs-lookup"><span data-stu-id="90f15-130">Go to [https://protection.office.com](https://protection.office.com) and sign in with your work or school account.</span></span> 
    
2. <span data-ttu-id="90f15-131">Nel riquadro di spostamento sinistro, in **gestione rischio**, scegliere **criterio** \> **Collegamenti sicuri**.</span><span class="sxs-lookup"><span data-stu-id="90f15-131">In the left navigation, under **Threat management**, choose **Policy** \> **Safe Links**.</span></span>
    
3. <span data-ttu-id="90f15-132">Nella sezione **criteri che si applicano all'intera organizzazione** , selezionare **predefinito**e quindi fare clic su **Modifica** (pulsante Edit a forma di una matita).</span><span class="sxs-lookup"><span data-stu-id="90f15-132">In the **Policies that apply to the entire organization** section, select **Default**, and then choose **Edit** (the Edit button resembles a pencil).</span></span><br/><span data-ttu-id="90f15-133">![Fare clic su Modifica per modificare il criterio predefinito per la protezione collegamenti sicuri](media/d08f9615-d947-4033-813a-d310ec2c8cca.png)</span><span class="sxs-lookup"><span data-stu-id="90f15-133">![Click Edit to edit your default policy for Safe Links protection](media/d08f9615-d947-4033-813a-d310ec2c8cca.png)</span></span><br/><span data-ttu-id="90f15-p106">In questo modo è possibile visualizzare l'elenco degli URL bloccati. Inizialmente, non si dispone di tutti gli URL elencati di seguito.</span><span class="sxs-lookup"><span data-stu-id="90f15-p106">This enables you to view your list of blocked URLs. At first, you might not have any URLs listed here.</span></span><br/><span data-ttu-id="90f15-136">![Elenco degli URL nel criterio predefinito sicuro collegamenti bloccati](media/575e1449-6191-40ac-b626-030a2fd3fb11.png)</span><span class="sxs-lookup"><span data-stu-id="90f15-136">![Blocked URLs list in the default Safe Links policy](media/575e1449-6191-40ac-b626-030a2fd3fb11.png)</span></span>
  
4. <span data-ttu-id="90f15-137">Selezionare la casella **Immettere un URL valido** , digitare un URL e quindi fare clic sul segno più (**+**).</span><span class="sxs-lookup"><span data-stu-id="90f15-137">Select the **Enter a valid URL** box, type a URL, and then choose the plus sign (**+**).</span></span> 

5. <span data-ttu-id="90f15-138">Dopo aver aggiunto gli URL, nell'angolo inferiore destro dello schermo, scegliere **Salva**.</span><span class="sxs-lookup"><span data-stu-id="90f15-138">When you are finished adding URLs, in the lower right corner of the screen, choose **Save**.</span></span>
    
## <a name="a-few-things-to-keep-in-mind"></a><span data-ttu-id="90f15-139">Alcuni aspetti da tenere presenti</span><span class="sxs-lookup"><span data-stu-id="90f15-139">A few things to keep in mind</span></span>

<span data-ttu-id="90f15-140">Quando si aggiunge gli URL all'elenco, tenere presente i punti seguenti:</span><span class="sxs-lookup"><span data-stu-id="90f15-140">While you add URLs to your list, keep the following points in mind:</span></span> 

- <span data-ttu-id="90f15-p107">Non includere una barra ( **/**) alla fine dell'URL. Ad esempio, invece di immettere `http://www.contoso.com/`, immettere `http://www.contoso.com`.</span><span class="sxs-lookup"><span data-stu-id="90f15-p107">Do not include a forward slash ( **/**) at the end of the URL. For example, instead of entering `http://www.contoso.com/`, enter `http://www.contoso.com`.</span></span>
    
- <span data-ttu-id="90f15-p108">È possibile specificare un URL solo dominio (ad esempio `contoso.com` o `tailspintoys.com`). Ciò Blocca clic in qualsiasi URL che contiene il dominio.</span><span class="sxs-lookup"><span data-stu-id="90f15-p108">You can specify a domain-only URL (like `contoso.com` or `tailspintoys.com`). This will block clicks on any URL that contains the domain.</span></span>

- <span data-ttu-id="90f15-p109">È possibile specificare un sottodominio (ad esempio `toys.contoso.com*`) senza bloccare un dominio completo (ad esempio `contoso.com`). Questo viene blocco fa clic su un URL contenente il sottodominio, ma non si blocca clic su un URL che contiene il dominio completo.</span><span class="sxs-lookup"><span data-stu-id="90f15-p109">You can specify a subdomain (like `toys.contoso.com*`) without blocking a full domain (like `contoso.com`). This will block clicks any URL that contains the subdomain, but it won't block clicks to a URL that contains the full domain.</span></span>  
    
- <span data-ttu-id="90f15-p110">È possibile includere fino a tre caratteri jolly asterischi (\*) per ogni URL. Nella tabella seguente sono elencate sono riportati alcuni esempi di è possibile immettere e quali effect tali voci.</span><span class="sxs-lookup"><span data-stu-id="90f15-p110">You can include up to three wildcard asterisks (\*) per URL. The following table lists some examples of what you can enter and what effect those entries have.</span></span>
    
|<span data-ttu-id="90f15-149">**Voce di esempio**</span><span class="sxs-lookup"><span data-stu-id="90f15-149">**Example Entry**</span></span>|<span data-ttu-id="90f15-150">**Funzione**</span><span class="sxs-lookup"><span data-stu-id="90f15-150">**What It Does**</span></span>|
|:-----|:-----|
|<span data-ttu-id="90f15-151">`contoso.com`o`*contoso.com*`</span><span class="sxs-lookup"><span data-stu-id="90f15-151">`contoso.com` or `*contoso.com*`</span></span>  <br/> |<span data-ttu-id="90f15-152">Blocca il dominio, sottodomini e percorsi, ad esempio `https://www.contoso.com`, `http://sub.contoso.com`, e`http://contoso.com/abc`</span><span class="sxs-lookup"><span data-stu-id="90f15-152">Blocks the domain, subdomains, and paths, such as `https://www.contoso.com`, `http://sub.contoso.com`, and `http://contoso.com/abc`</span></span>  <br/> |
|`http://contoso.com/a`  <br/> |<span data-ttu-id="90f15-153">Blocca un sito `http://contoso.com/a` ma, come percorsi secondari non aggiuntive`http://contoso.com/a/b`</span><span class="sxs-lookup"><span data-stu-id="90f15-153">Blocks a site `http://contoso.com/a` but not additional subpaths like `http://contoso.com/a/b`</span></span>  <br/> |
|`http://contoso.com/a*`  <br/> |<span data-ttu-id="90f15-154">Blocca un sito `http://contoso.com/a` e i percorsi secondari aggiuntive`http://contoso.com/a/b`</span><span class="sxs-lookup"><span data-stu-id="90f15-154">Blocks a site `http://contoso.com/a` and additional subpaths like `http://contoso.com/a/b`</span></span>  <br/> |
|`http://toys.contoso.com*`  <br/> |<span data-ttu-id="90f15-155">Blocca un sottodominio ("toys" in questo caso) ma Consenti clic agli altri URL di dominio (ad esempio `http://contoso.com` o `http://home.contoso.com`).</span><span class="sxs-lookup"><span data-stu-id="90f15-155">Blocks a subdomain ("toys" in this case) but allow clicks to other domain URLs (like `http://contoso.com` or `http://home.contoso.com`).</span></span>  <br/> |
   

## <a name="how-to-define-exceptions-for-certain-users-in-an-organization"></a><span data-ttu-id="90f15-156">Come definire le eccezioni per utenti specifici in un'organizzazione</span><span class="sxs-lookup"><span data-stu-id="90f15-156">How to define exceptions for certain users in an organization</span></span>

<span data-ttu-id="90f15-p111">Se si desidera determinati gruppi siano in grado di visualizzare gli URL che potrebbe essere bloccati per altri utenti, è possibile specificare un criterio degli strumenti di analisi collegamenti sicuri da applicare a destinatari specifici. Vedere [impostare un "non di riscrittura" URL elenco personalizzato utilizzo degli strumenti di analisi dei collegamenti sicuri](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md).</span><span class="sxs-lookup"><span data-stu-id="90f15-p111">If you want certain groups to be able to view URLs that might be blocked for others, you can specify an ATP Safe Links policy that applies to specific recipients. See [Set up a custom "do not rewrite" URLs list using ATP Safe Links](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md).</span></span>
  

