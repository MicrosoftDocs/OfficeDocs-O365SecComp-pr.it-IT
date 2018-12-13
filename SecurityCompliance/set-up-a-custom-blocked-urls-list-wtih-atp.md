---
title: Impostare un elenco di URL bloccato personalizzato con Office 365 degli strumenti di analisi provvisoria collegamenti
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.audience: Admin
ms.topic: article
ms.date: 12/11/2018
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 896a7efb-1683-465e-a394-261349e5d866
description: Informazioni su come configurare un elenco di URL bloccati per l'organizzazione utilizza la protezione di Office 365 avanzate rischio. Gli URL bloccati verranno applicate a messaggi di posta elettronica e documenti di Office in base ai criteri di collegamenti sicuro degli strumenti di analisi.
ms.openlocfilehash: 25f01b767726ebf02d5da5d18444fa0428f144ac
ms.sourcegitcommit: 031781d0eecf33baabcd03ea53546d41076062b4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/12/2018
ms.locfileid: "27240529"
---
# <a name="set-up-a-custom-blocked-urls-list-using-office-365-atp-safe-links"></a><span data-ttu-id="d58f8-104">Impostare un elenco di URL bloccato personalizzato con Office 365 degli strumenti di analisi provvisoria collegamenti</span><span class="sxs-lookup"><span data-stu-id="d58f8-104">Set up a custom blocked URLs list using Office 365 ATP Safe Links</span></span>

<span data-ttu-id="d58f8-p102">Con [Office 365 avanzate Threat Protection](office-365-atp.md) (degli strumenti di analisi), l'organizzazione può avere un elenco personalizzato di indirizzi di siti Web (URL) che vengono bloccati. Quando viene bloccato un URL, persone, fare clic sui collegamenti all'URL bloccati vengono indirizzate a una [pagina di avviso](atp-safe-links-warning-pages.md) simile all'immagine seguente:</span><span class="sxs-lookup"><span data-stu-id="d58f8-p102">With [Office 365 Advanced Threat Protection](office-365-atp.md) (ATP), your organization can have a custom list of website addresses (URLs) that are blocked. When a URL is blocked, people who click on links to the blocked URL are taken to a [warning page](atp-safe-links-warning-pages.md) that resembles the following image:</span></span> 
  
![In questo sito è bloccato](media/6b4bda2d-a1e6-419e-8b10-588e83c3af3f.png)
  
<span data-ttu-id="d58f8-108">L'elenco degli URL bloccato è definito dal team di protezione di Office 365 dell'organizzazione e tale elenco si applica a tutti gli utenti dell'organizzazione che sono disponibili i criteri di Office 365 degli strumenti di analisi provvisoria collegamenti.</span><span class="sxs-lookup"><span data-stu-id="d58f8-108">The blocked URLs list is defined by your organization's Office 365 security team, and that list applies to everyone in the organization who is covered by Office 365 ATP Safe Links policies.</span></span> 
  
<span data-ttu-id="d58f8-109">In questo articolo per informazioni su come configurare personalizzato URL elenco dei domini bloccati dell'organizzazione per [Strumenti di analisi collegamenti attendibili in Office 365](atp-safe-links.md).</span><span class="sxs-lookup"><span data-stu-id="d58f8-109">Read this article to learn how to set up your organization's custom blocked URLs list for [ATP Safe Links in Office 365](atp-safe-links.md).</span></span>
  
## <a name="view-or-edit-a-custom-list-of-blocked-urls"></a><span data-ttu-id="d58f8-110">Visualizzare o modificare un elenco personalizzato di URL bloccati</span><span class="sxs-lookup"><span data-stu-id="d58f8-110">View or edit a custom list of blocked URLs</span></span>

<span data-ttu-id="d58f8-p103">[Degli strumenti di analisi collegamenti attendibili in Office 365](atp-safe-links.md) utilizza più elenchi, inclusi personalizzato URL elenco dei domini bloccati dell'organizzazione. Se si dispone delle autorizzazioni necessarie, è possibile impostare elenco personalizzato dell'organizzazione. Ottenere questo risultato modificando i criteri dell'organizzazione predefinito collegamenti sicuri.</span><span class="sxs-lookup"><span data-stu-id="d58f8-p103">[ATP Safe Links in Office 365](atp-safe-links.md) uses several lists, including your organization's custom blocked URLs list. If you have the necessary permissions, you can set up your organization's custom list. You do this by editing your organization's default Safe Links policy.</span></span>
  
1. <span data-ttu-id="d58f8-114">Accedere a [https://security.microsoft.com](https://security.microsoft.com) e accedere con l'account di lavoro o della scuola.</span><span class="sxs-lookup"><span data-stu-id="d58f8-114">Go to [https://security.microsoft.com](https://security.microsoft.com) and sign in with your work or school account.</span></span> 
    
2. <span data-ttu-id="d58f8-115">Nel riquadro di spostamento sinistro, in **gestione rischio**, scegliere **criterio** \> **Collegamenti sicuri**.</span><span class="sxs-lookup"><span data-stu-id="d58f8-115">In the left navigation, under **Threat management**, choose **Policy** \> **Safe Links**.</span></span>
    
3. <span data-ttu-id="d58f8-116">Nella sezione **criteri che si applicano all'intera organizzazione** , selezionare **predefinito**e quindi fare clic su **Modifica** (pulsante Edit a forma di una matita).</span><span class="sxs-lookup"><span data-stu-id="d58f8-116">In the **Policies that apply to the entire organization** section, select **Default**, and then choose **Edit** (the Edit button resembles a pencil).</span></span><br/><span data-ttu-id="d58f8-117">![Fare clic su Modifica per modificare il criterio predefinito per la protezione collegamenti sicuri](media/d08f9615-d947-4033-813a-d310ec2c8cca.png)</span><span class="sxs-lookup"><span data-stu-id="d58f8-117">![Click Edit to edit your default policy for Safe Links protection](media/d08f9615-d947-4033-813a-d310ec2c8cca.png)</span></span><br/><span data-ttu-id="d58f8-p104">In questo modo è possibile visualizzare l'elenco degli URL bloccati. Inizialmente, non si dispone di tutti gli URL elencati di seguito.</span><span class="sxs-lookup"><span data-stu-id="d58f8-p104">This enables you to view your list of blocked URLs. At first, you might not have any URLs listed here.</span></span><br/><span data-ttu-id="d58f8-120">![Elenco degli URL nel criterio predefinito sicuro collegamenti bloccati](media/575e1449-6191-40ac-b626-030a2fd3fb11.png)</span><span class="sxs-lookup"><span data-stu-id="d58f8-120">![Blocked URLs list in the default Safe Links policy](media/575e1449-6191-40ac-b626-030a2fd3fb11.png)</span></span>
  
4. <span data-ttu-id="d58f8-121">Selezionare la casella **Immettere un URL valido** , digitare un URL e quindi fare clic sul segno più (**+**).</span><span class="sxs-lookup"><span data-stu-id="d58f8-121">Select the **Enter a valid URL** box, type a URL, and then choose the plus sign (**+**).</span></span> 

5. <span data-ttu-id="d58f8-122">Dopo aver aggiunto gli URL, nell'angolo inferiore destro dello schermo, scegliere **Salva**.</span><span class="sxs-lookup"><span data-stu-id="d58f8-122">When you are finished adding URLs, in the lower right corner of the screen, choose **Save**.</span></span>
    
## <a name="a-few-things-to-keep-in-mind"></a><span data-ttu-id="d58f8-123">Alcuni aspetti da tenere presenti</span><span class="sxs-lookup"><span data-stu-id="d58f8-123">A few things to keep in mind</span></span>

<span data-ttu-id="d58f8-124">Quando si aggiunge gli URL all'elenco, tenere presente i punti seguenti:</span><span class="sxs-lookup"><span data-stu-id="d58f8-124">While you add URLs to your list, keep the following points in mind:</span></span> 

- <span data-ttu-id="d58f8-p105">Non includere una barra ( **/**) alla fine dell'URL. Ad esempio, invece di immettere `http://www.contoso.com/`, immettere `http://www.contoso.com`.</span><span class="sxs-lookup"><span data-stu-id="d58f8-p105">Do not include a forward slash ( **/**) at the end of the URL. For example, instead of entering `http://www.contoso.com/`, enter `http://www.contoso.com`.</span></span>
    
- <span data-ttu-id="d58f8-p106">È possibile specificare un URL solo dominio (ad esempio `contoso.com` o `tailspintoys.com`). Ciò Blocca clic in qualsiasi URL che contiene il dominio.</span><span class="sxs-lookup"><span data-stu-id="d58f8-p106">You can specify a domain-only URL (like `contoso.com` or `tailspintoys.com`). This will block clicks on any URL that contains the domain.</span></span>

- <span data-ttu-id="d58f8-p107">È possibile specificare un sottodominio (ad esempio `toys.contoso.com*`) senza bloccare un dominio completo (ad esempio `contoso.com`). Questo viene blocco fa clic su un URL contenente il sottodominio, ma non si blocca clic su un URL che contiene il dominio completo.</span><span class="sxs-lookup"><span data-stu-id="d58f8-p107">You can specify a subdomain (like `toys.contoso.com*`) without blocking a full domain (like `contoso.com`). This will block clicks any URL that contains the subdomain, but it won't block clicks to a URL that contains the full domain.</span></span>  
    
- <span data-ttu-id="d58f8-p108">È possibile includere fino a tre caratteri jolly asterischi (\*) per ogni URL. Nella tabella seguente sono elencate sono riportati alcuni esempi di è possibile immettere e quali effect tali voci.</span><span class="sxs-lookup"><span data-stu-id="d58f8-p108">You can include up to three wildcard asterisks (\*) per URL. The following table lists some examples of what you can enter and what effect those entries have.</span></span>
    
|<span data-ttu-id="d58f8-133">**Voce di esempio**</span><span class="sxs-lookup"><span data-stu-id="d58f8-133">**Example Entry**</span></span>|<span data-ttu-id="d58f8-134">**Funzione**</span><span class="sxs-lookup"><span data-stu-id="d58f8-134">**What It Does**</span></span>|
|:-----|:-----|
|<span data-ttu-id="d58f8-135">`contoso.com`o`*contoso.com*`</span><span class="sxs-lookup"><span data-stu-id="d58f8-135">`contoso.com` or `*contoso.com*`</span></span>  <br/> |<span data-ttu-id="d58f8-136">Blocca il dominio, sottodomini e percorsi, ad esempio `https://www.contoso.com`, `http://sub.contoso.com`, e`http://contoso.com/abc`</span><span class="sxs-lookup"><span data-stu-id="d58f8-136">Blocks the domain, subdomains, and paths, such as `https://www.contoso.com`, `http://sub.contoso.com`, and `http://contoso.com/abc`</span></span>  <br/> |
|`http://contoso.com/a`  <br/> |<span data-ttu-id="d58f8-137">Blocca un sito `http://contoso.com/a` ma, come percorsi secondari non aggiuntive`http://contoso.com/a/b`</span><span class="sxs-lookup"><span data-stu-id="d58f8-137">Blocks a site `http://contoso.com/a` but not additional subpaths like `http://contoso.com/a/b`</span></span>  <br/> |
|`http://contoso.com/a*`  <br/> |<span data-ttu-id="d58f8-138">Blocca un sito `http://contoso.com/a` e i percorsi secondari aggiuntive`http://contoso.com/a/b`</span><span class="sxs-lookup"><span data-stu-id="d58f8-138">Blocks a site `http://contoso.com/a` and additional subpaths like `http://contoso.com/a/b`</span></span>  <br/> |
|`http://toys.contoso.com*`  <br/> |<span data-ttu-id="d58f8-139">Blocca un sottodominio ("toys" in questo caso) ma Consenti clic agli altri URL di dominio (ad esempio `http://contoso.com` o `http://home.contoso.com`).</span><span class="sxs-lookup"><span data-stu-id="d58f8-139">Blocks a subdomain ("toys" in this case) but allow clicks to other domain URLs (like `http://contoso.com` or `http://home.contoso.com`).</span></span>  <br/> |
   

## <a name="how-to-define-exceptions-for-certain-users-in-an-organization"></a><span data-ttu-id="d58f8-140">Come definire le eccezioni per utenti specifici in un'organizzazione</span><span class="sxs-lookup"><span data-stu-id="d58f8-140">How to define exceptions for certain users in an organization</span></span>

<span data-ttu-id="d58f8-p109">Se si desidera determinati gruppi siano in grado di visualizzare gli URL che potrebbe essere bloccati per altri utenti, è possibile specificare un criterio degli strumenti di analisi collegamenti sicuri da applicare a destinatari specifici. Vedere [impostare un "non di riscrittura" URL elenco personalizzato utilizzo degli strumenti di analisi dei collegamenti sicuri](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md).</span><span class="sxs-lookup"><span data-stu-id="d58f8-p109">If you want certain groups to be able to view URLs that might be blocked for others, you can specify an ATP Safe Links policy that applies to specific recipients. See [Set up a custom "do not rewrite" URLs list using ATP Safe Links](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md).</span></span>
  

