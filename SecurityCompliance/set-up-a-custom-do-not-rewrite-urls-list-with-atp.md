---
title: Impostare un elenco personalizzato di URL rewrite di non eseguire tramite collegamenti attendibili di Office 365 degli strumenti di analisi
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 35dbfd99-da5a-422b-9b0e-c6caf3b645fa
description: Quando si imposta i criteri di collegamenti sicuro degli strumenti di analisi, è possibile includere una riscrittura di non eseguire ' elenco degli URL per abilitare alcune persone all'interno dell'organizzazione visitare i siti che includono nell'elenco.
ms.openlocfilehash: 0ee9c87c90e6e30d6c43fb0de5291dd85b03be07
ms.sourcegitcommit: e7b87fae103a858981bdbcdf7ec55afa4751ad05
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/31/2018
ms.locfileid: "23782163"
---
# <a name="set-up-a-custom-do-not-rewrite-urls-list-using-office-365-atp-safe-links"></a><span data-ttu-id="f2a5e-103">Impostare un elenco personalizzato di URL rewrite di non eseguire tramite collegamenti attendibili di Office 365 degli strumenti di analisi</span><span class="sxs-lookup"><span data-stu-id="f2a5e-103">Set up a custom do-not-rewrite URLs list using Office 365 ATP Safe Links</span></span>

<span data-ttu-id="f2a5e-p101">Con [Office 365 avanzate Threat Protection](office-365-atp.md) (degli strumenti di analisi), l'organizzazione può avere un [URL bloccati personalizzato](set-up-a-custom-blocked-urls-list-wtih-atp.md), in modo che quando utenti fare clic su web indirizzi (URL) in messaggi di posta elettronica o alcuni documenti di Office, viene impediti a questi URL. L'organizzazione può essere elenchi personalizzati "non di riscrittura" per gruppi specifici dell'organizzazione. Un elenco "non di riscrittura" consente alcune persone a visitare gli URL che vengono bloccati in caso contrario tramite [Degli strumenti di analisi collegamenti attendibili in Office 365](atp-safe-links.md).</span><span class="sxs-lookup"><span data-stu-id="f2a5e-p101">With [Office 365 Advanced Threat Protection](office-365-atp.md) (ATP), your organization can have a [custom blocked URLs](set-up-a-custom-blocked-urls-list-wtih-atp.md), such that when people click on web addresses (URLs) in email messages or certain Office documents, they are prevented from going to those URLs. Your organization can also have custom "do not rewrite" lists for specific groups in your organization. A "do not rewrite" list enables some people to visit URLs that are otherwise blocked by [ATP Safe Links in Office 365](atp-safe-links.md).</span></span> 
  
<span data-ttu-id="f2a5e-107">In questo articolo viene descritto come specificare un elenco di URL che esclusa dall'analisi dei collegamenti sicuro degli strumenti di analisi e alcune importanti considerazioni da tenere presenti.</span><span class="sxs-lookup"><span data-stu-id="f2a5e-107">This article describes how to specify a list of URLs that are excluded from ATP Safe Links scanning, and a few important points to keep in mind.</span></span>

## <a name="set-up-a-do-not-rewrite-list"></a><span data-ttu-id="f2a5e-108">Impostare un elenco "non di riscrittura"</span><span class="sxs-lookup"><span data-stu-id="f2a5e-108">Set up a "do not rewrite" list</span></span>

<span data-ttu-id="f2a5e-p102">Protezione degli strumenti di analisi collegamenti sicuri utilizza più elenchi, inclusi nell'elenco degli URL bloccato dell'organizzazione e gli elenchi "non di riscrittura" per le eccezioni. Se si dispone delle autorizzazioni necessarie, è possibile impostare gli elenchi personalizzati "non di riscrittura". A tale scopo quando si aggiunge o modifica criteri sicuro collegamenti che si applicano a destinatari specifici dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="f2a5e-p102">ATP Safe Links protection uses several lists, including your organization's blocked URLs list and the "do not rewrite" lists for exceptions. If you have the necessary permissions, you can set up your custom "do not rewrite" lists. You do this when you add or edit Safe Links policies that apply to specific recipients in your organization.</span></span> 
  
1. <span data-ttu-id="f2a5e-112">Accedere a [https://protection.office.com](https://protection.office.com) e accedere con l'account di lavoro o della scuola.</span><span class="sxs-lookup"><span data-stu-id="f2a5e-112">Go to [https://protection.office.com](https://protection.office.com) and sign in with your work or school account.</span></span> 
    
2. <span data-ttu-id="f2a5e-113">Nel riquadro di spostamento sinistro, in **gestione rischio** \> **criteri** \> **Collegamenti sicuri**.</span><span class="sxs-lookup"><span data-stu-id="f2a5e-113">In the left navigation, under **Threat management** \> **Policy** \> **Safe Links**.</span></span>
    
3. <span data-ttu-id="f2a5e-p103">Nella sezione **criteri che si applicano a destinatari specifici** fare clic su **Nuovo** (pulsante nuovo simile a un segno di addizione ( **+**)) per creare un nuovo criterio. (In alternativa, è possibile modificare un criterio esistente.)</span><span class="sxs-lookup"><span data-stu-id="f2a5e-p103">In the **Policies that apply to specific recipients** section, choose **New** (the New button resembles a plus sign ( **+**)) to create a new policy. (Alternatively, you can edit an existing policy.)</span></span>
    
    ![Selezionare nuovo per aggiungere un criterio di collegamenti sicuro per i destinatari di posta elettronica specifico](media/01073f42-3cec-4ddb-8c10-4d33ec434676.png)
  
4. <span data-ttu-id="f2a5e-117">Consente di specificare un nome e una descrizione per il criterio.</span><span class="sxs-lookup"><span data-stu-id="f2a5e-117">Specify a name and description for your policy.</span></span>
    
5. <span data-ttu-id="f2a5e-118">Nella sezione **non riscrivere gli URL seguenti** , selezionare la casella **Immettere un URL valido** e quindi digitare un URL e quindi fare clic sul segno più (+).</span><span class="sxs-lookup"><span data-stu-id="f2a5e-118">In the **Do not rewrite the following URLs** section, select the **Enter a valid URL** box, and then type a URL, and then choose the plus sign (+).</span></span> 
    
6. <span data-ttu-id="f2a5e-p104">Nella sezione **Applicato a** scegliere **il destinatario è un membro del**e quindi fare clic su gruppi di cui che si desidera includere nel criterio. Scegliere **Aggiungi**e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="f2a5e-p104">In the **Applied To** section, choose **The recipient is a member of**, and then choose the group(s) you want to include in your policy. Choose **Add**, and then choose **OK**.</span></span>
    
7. <span data-ttu-id="f2a5e-121">Dopo aver aggiunto gli URL, nell'angolo inferiore destro dello schermo, scegliere **Salva**.</span><span class="sxs-lookup"><span data-stu-id="f2a5e-121">When you are finished adding URLs, in the lower right corner of the screen, choose **Save**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="f2a5e-p105">Assicurarsi di esaminare l'elenco personalizzato dell'organizzazione di URL bloccati. Vedere [impostare un elenco degli URL bloccato personalizzato utilizzo degli strumenti di analisi dei collegamenti sicuri](set-up-a-custom-blocked-urls-list-wtih-atp.md).</span><span class="sxs-lookup"><span data-stu-id="f2a5e-p105">Make sure to review your organization's custom list of blocked URLs. See [Set up a custom blocked URLs list using ATP Safe Links](set-up-a-custom-blocked-urls-list-wtih-atp.md).</span></span> 
  
## <a name="important-points-to-keep-in-mind"></a><span data-ttu-id="f2a5e-124">Aspetti importanti da tenere presenti</span><span class="sxs-lookup"><span data-stu-id="f2a5e-124">Important points to keep in mind</span></span>

- <span data-ttu-id="f2a5e-125">Tutti gli URL specificati nell'elenco "non di riscrittura" sono esclusi dai collegamenti sicuro degli strumenti di analisi di virus per i destinatari specificati.</span><span class="sxs-lookup"><span data-stu-id="f2a5e-125">Any URLs that you specify in the "do not rewrite" list are excluded from ATP Safe Links scanning for the recipients that you specify.</span></span>
 
- <span data-ttu-id="f2a5e-p106">Quando si specifica un elenco "non di riscrittura" per un criterio degli strumenti di analisi collegamenti sicuri, è possibile includere fino a tre caratteri jolly asterischi (\*). I caratteri jolly (\*) vengono considerati come voci `contoso.com`, che non si in modo esplicito include i prefissi o sottodomini, ad esempio `http://` o `https://`. In questo modo una voce, ad esempio `contoso.com` è simile a `\*contoso.com\*` per l'elenco "non di riscrittura".</span><span class="sxs-lookup"><span data-stu-id="f2a5e-p106">When you specify a "do not rewrite" list for an ATP Safe Links policy, you can include up to three wildcard asterisks (\*). Wildcards (\*) are assumed for entries such as `contoso.com`, which do not explicitly include prefixes or subdomains, like `http://` or `https://`. This means an entry, such as `contoso.com` is similar to `\*contoso.com\*` for your "do not rewrite" list.</span></span>

- <span data-ttu-id="f2a5e-p107">Se si dispone già di un elenco di URL nell'elenco "non di riscrittura", assicurarsi di esaminare l'elenco e aggiungere i caratteri jolly nel modo appropriato. Ad esempio, se l'elenco esistente è una voce come `http://contoso.com/a` e si desidera includere percorsi secondari come `http://contoso.com/a/b` nei criteri di aggiungere un carattere jolly per la voce in modo che sia simile `http://contoso.com/a\*`.</span><span class="sxs-lookup"><span data-stu-id="f2a5e-p107">If you already have a list of URLs in your "do not rewrite" list, make sure to review that list and add wildcards as appropriate. For example, if your existing list has an entry like `http://contoso.com/a` and you want to include subpaths like `http://contoso.com/a/b` in your policy, add a wildcard to your entry so it looks like `http://contoso.com/a\*`.</span></span>
    
- <span data-ttu-id="f2a5e-p108">Non includere una barra (/) nell'URL specificato nell'elenco "non di riscrittura". Ad esempio, invece di immettere `contoso.com/` nell'elenco "non di riscrittura", immettere `contoso.com`.</span><span class="sxs-lookup"><span data-stu-id="f2a5e-p108">Do not include a forward slash (/) in the URLs that you specify in your "do not rewrite" list. For example, rather than enter `contoso.com/` in your "do not rewrite" list, enter `contoso.com`.</span></span>
    
<span data-ttu-id="f2a5e-133">Gli esempi di è possibile immettere e quali effect tali voci di elenchi di tabella seguenti sono.</span><span class="sxs-lookup"><span data-stu-id="f2a5e-133">The following table lists examples of what you can enter and what effect those entries have.</span></span>
    
|<span data-ttu-id="f2a5e-134">**Voce di esempio**</span><span class="sxs-lookup"><span data-stu-id="f2a5e-134">**Example Entry**</span></span>|<span data-ttu-id="f2a5e-135">**Funzione**</span><span class="sxs-lookup"><span data-stu-id="f2a5e-135">**What It Does**</span></span>|
|:-----|:-----|
|`\*contoso.com\*`  <br/> |<span data-ttu-id="f2a5e-136">Consente ai destinatari specifici di visitare un dominio, sottodomini e percorsi, ad esempio `http://www.contoso.com`, `https://www.contoso.com`, `https://maps.contoso.com`, o`http://www.contoso.com/a`</span><span class="sxs-lookup"><span data-stu-id="f2a5e-136">Allows specific recipients to visit a domain, subdomains, and paths, such as `http://www.contoso.com`, `https://www.contoso.com`, `https://maps.contoso.com`, or `http://www.contoso.com/a`</span></span>  <br/> |
|`http://contoso.com/a`  <br/> |<span data-ttu-id="f2a5e-137">Consente ai destinatari specifici a visitare un sito come `http://contoso.com/a`, ma non percorsi secondari`http://contoso.com/a/b`</span><span class="sxs-lookup"><span data-stu-id="f2a5e-137">Allows specific recipients to visit a site like `http://contoso.com/a`, but not subpaths like `http://contoso.com/a/b`</span></span>  <br/> |
|`http://contoso.com/a\*`  <br/> |<span data-ttu-id="f2a5e-138">Consente ai destinatari specifici a visitare un sito come `http://contoso.com/a` e i percorsi secondari`http://contoso.com/a/b`</span><span class="sxs-lookup"><span data-stu-id="f2a5e-138">Allows specific recipients to visit a site like `http://contoso.com/a` and subpaths like `http://contoso.com/a/b`</span></span>  <br/> |
   
  

## <a name="related-topics"></a><span data-ttu-id="f2a5e-139">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="f2a5e-139">Related topics</span></span>

[<span data-ttu-id="f2a5e-140">Office 365 Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="f2a5e-140">Office 365 Advanced Threat Protection</span></span>](office-365-atp.md)
  
[<span data-ttu-id="f2a5e-141">Collegamenti degli strumenti di analisi sicuro in Office 365</span><span class="sxs-lookup"><span data-stu-id="f2a5e-141">ATP Safe Links in Office 365</span></span>](atp-safe-links.md)
  
[<span data-ttu-id="f2a5e-142">Impostare i criteri degli strumenti di analisi collegamenti attendibili in Office 365</span><span class="sxs-lookup"><span data-stu-id="f2a5e-142">Set up ATP Safe Links policies in Office 365</span></span>](set-up-atp-safe-links-policies.md)
  
[<span data-ttu-id="f2a5e-143">Impostare un elenco degli URL bloccato personalizzato utilizzo degli strumenti di analisi dei collegamenti sicuri</span><span class="sxs-lookup"><span data-stu-id="f2a5e-143">Set up a custom blocked URLs list using ATP Safe Links</span></span>](set-up-a-custom-blocked-urls-list-wtih-atp.md)

[<span data-ttu-id="f2a5e-144">Visualizzare i report per la protezione rischio avanzate di Office 365</span><span class="sxs-lookup"><span data-stu-id="f2a5e-144">View reports for Office 365 Advanced Threat Protection</span></span>](view-reports-for-atp.md)

[<span data-ttu-id="f2a5e-145">Le autorizzazioni di sicurezza di Office 365 &amp; centro conformità</span><span class="sxs-lookup"><span data-stu-id="f2a5e-145">Permissions in the Office 365 Security &amp; Compliance Center</span></span>](permissions-in-the-security-and-compliance-center.md)
  

