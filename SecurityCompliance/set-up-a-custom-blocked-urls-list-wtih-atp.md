---
title: Impostare un elenco di URL bloccato personalizzato con Office 365 degli strumenti di analisi provvisoria collegamenti
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
ms.assetid: 896a7efb-1683-465e-a394-261349e5d866
description: In questo articolo per informazioni su come configurare un elenco di URL bloccati per l'organizzazione utilizza la protezione di Office 365 avanzate rischio. Gli URL bloccati verranno applicate a messaggi di posta elettronica e documenti di Office in base ai criteri di collegamenti sicuro degli strumenti di analisi.
ms.openlocfilehash: 0429546e521bf3f6b7144342ab0997e924c2f616
ms.sourcegitcommit: 099bbfb1d16b251fd5cf18ec6515faaf9a989176
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/09/2018
ms.locfileid: "25454363"
---
# <a name="set-up-a-custom-blocked-urls-list-using-office-365-atp-safe-links"></a><span data-ttu-id="85e58-104">Impostare un elenco di URL bloccato personalizzato con Office 365 degli strumenti di analisi provvisoria collegamenti</span><span class="sxs-lookup"><span data-stu-id="85e58-104">Set up a custom blocked URLs list using Office 365 ATP Safe Links</span></span>

<span data-ttu-id="85e58-p102">Con [Office 365 avanzate Threat Protection](office-365-atp.md) (degli strumenti di analisi), l'organizzazione può avere un elenco personalizzato di indirizzi di siti Web (URL) che vengono bloccati. Quando viene bloccato un URL, persone, fare clic sui collegamenti all'URL bloccati vengono indirizzate a una [pagina di avviso](atp-safe-links-warning-pages.md) simile all'immagine seguente:</span><span class="sxs-lookup"><span data-stu-id="85e58-p102">With [Office 365 Advanced Threat Protection](office-365-atp.md) (ATP), your organization can have a custom list of website addresses (URLs) that are blocked. When a URL is blocked, people who click on links to the blocked URL are taken to a [warning page](atp-safe-links-warning-pages.md) that resembles the following image:</span></span> 
  
![In questo sito è bloccato](media/6b4bda2d-a1e6-419e-8b10-588e83c3af3f.png)
  
<span data-ttu-id="85e58-108">L'elenco degli URL bloccato è definito dal team di protezione di Office 365 dell'organizzazione e tale elenco si applica a tutti gli utenti dell'organizzazione che sono disponibili i criteri di Office 365 degli strumenti di analisi provvisoria collegamenti.</span><span class="sxs-lookup"><span data-stu-id="85e58-108">The blocked URLs list is defined by your organization's Office 365 security team, and that list applies to everyone in the organization who is covered by Office 365 ATP Safe Links policies.</span></span> 
  
<span data-ttu-id="85e58-109">In questo articolo per informazioni su come configurare personalizzato URL elenco dei domini bloccati dell'organizzazione per [Strumenti di analisi collegamenti attendibili in Office 365](atp-safe-links.md).</span><span class="sxs-lookup"><span data-stu-id="85e58-109">Read this article to learn how to set up your organization's custom blocked URLs list for [ATP Safe Links in Office 365](atp-safe-links.md).</span></span>
  
## <a name="view-or-edit-a-custom-list-of-blocked-urls"></a><span data-ttu-id="85e58-110">Visualizzare o modificare un elenco personalizzato di URL bloccati</span><span class="sxs-lookup"><span data-stu-id="85e58-110">View or edit a custom list of blocked URLs</span></span>

<span data-ttu-id="85e58-p103">[Degli strumenti di analisi collegamenti attendibili in Office 365](atp-safe-links.md) utilizza più elenchi, inclusi personalizzato URL elenco dei domini bloccati dell'organizzazione. Se si dispone delle autorizzazioni necessarie, è possibile impostare elenco personalizzato dell'organizzazione. Ottenere questo risultato modificando i criteri dell'organizzazione predefinito collegamenti sicuri.</span><span class="sxs-lookup"><span data-stu-id="85e58-p103">[ATP Safe Links in Office 365](atp-safe-links.md) uses several lists, including your organization's custom blocked URLs list. If you have the necessary permissions, you can set up your organization's custom list. You do this by editing your organization's default Safe Links policy.</span></span>
  
1. <span data-ttu-id="85e58-114">Accedere a [https://protection.office.com](https://protection.office.com) e accedere con l'account di lavoro o della scuola.</span><span class="sxs-lookup"><span data-stu-id="85e58-114">Go to [https://protection.office.com](https://protection.office.com) and sign in with your work or school account.</span></span> 
    
2. <span data-ttu-id="85e58-115">Nel riquadro di spostamento sinistro, in **gestione rischio**, scegliere **criterio** \> **Collegamenti sicuri**.</span><span class="sxs-lookup"><span data-stu-id="85e58-115">In the left navigation, under **Threat management**, choose **Policy** \> **Safe Links**.</span></span>
    
3. <span data-ttu-id="85e58-116">Nella sezione **criteri che si applicano all'intera organizzazione** , selezionare **predefinito**e quindi fare clic su **Modifica** (pulsante Edit a forma di una matita).</span><span class="sxs-lookup"><span data-stu-id="85e58-116">In the **Policies that apply to the entire organization** section, select **Default**, and then choose **Edit** (the Edit button resembles a pencil).</span></span> 
    
    ![Fare clic su Modifica per modificare il criterio predefinito per la protezione collegamenti sicuri](media/d08f9615-d947-4033-813a-d310ec2c8cca.png)
  
    <span data-ttu-id="85e58-p104">È possibile per visualizzare l'elenco degli URL bloccati. Si noti che, inizialmente, non sarà necessario tutti gli URL elencati.</span><span class="sxs-lookup"><span data-stu-id="85e58-p104">This is where you go to view your list of blocked URLs. Note that at first, you won't have any URLs listed.</span></span>
    
    ![L'elenco degli URL bloccati è nel predefinito criterio sicuri collegamenti che si applica all'intera organizzazione.](media/575e1449-6191-40ac-b626-030a2fd3fb11.png)
  
4. <span data-ttu-id="85e58-p105">Selezionare la casella **Immettere un URL valido** e quindi digitare un URL e quindi fare clic sul segno più (+). Ecco alcuni aspetti da tenere presenti:</span><span class="sxs-lookup"><span data-stu-id="85e58-p105">Select the **Enter a valid URL** box, and then type a URL, and then choose the plus sign (+). Here are a few things to keep in mind:</span></span> 
    
  - <span data-ttu-id="85e58-p106">È possibile specificare un URL solo dominio (ad esempio `contoso.com` o `tailspintoys.com`). Ciò Blocca clic in qualsiasi URL che contiene il dominio.</span><span class="sxs-lookup"><span data-stu-id="85e58-p106">You can specify a domain-only URL (like `contoso.com` or `tailspintoys.com`). This will block clicks on any URL that contains the domain.</span></span>
    
  - <span data-ttu-id="85e58-p107">Non includere una barra ( **/**) alla fine dell'URL. Ad esempio, invece di immettere `http://www.contoso.com/`, immettere `http://www.contoso.com`.</span><span class="sxs-lookup"><span data-stu-id="85e58-p107">Do not include a forward slash ( **/**) at the end of the URL. For example, instead of entering `http://www.contoso.com/`, enter `http://www.contoso.com`.</span></span>
    
  - <span data-ttu-id="85e58-p108">È possibile includere fino a tre caratteri jolly asterischi (\*) per ogni URL. Nella tabella seguente sono elencate sono riportati alcuni esempi di è possibile immettere e quali effect tali voci.</span><span class="sxs-lookup"><span data-stu-id="85e58-p108">You can include up to three wildcard asterisks (\*) per URL. The following table lists some examples of what you can enter and what effect those entries have.</span></span>
    
|<span data-ttu-id="85e58-129">**Voce di esempio**</span><span class="sxs-lookup"><span data-stu-id="85e58-129">**Example Entry**</span></span>|<span data-ttu-id="85e58-130">**Funzione**</span><span class="sxs-lookup"><span data-stu-id="85e58-130">**What It Does**</span></span>|
|:-----|:-----|
|<span data-ttu-id="85e58-131">`contoso.com`o`*contoso.com*`</span><span class="sxs-lookup"><span data-stu-id="85e58-131">`contoso.com` or `*contoso.com*`</span></span>  <br/> |<span data-ttu-id="85e58-132">Blocca il dominio, sottodomini e percorsi, ad esempio `https://www.contoso.com`, `http://sub.contoso.com`, e`http://contoso.com/abc`</span><span class="sxs-lookup"><span data-stu-id="85e58-132">Blocks the domain, subdomains, and paths, such as `https://www.contoso.com`, `http://sub.contoso.com`, and `http://contoso.com/abc`</span></span>  <br/> |
|`http://contoso.com/a`  <br/> |<span data-ttu-id="85e58-133">Blocca un sito `http://contoso.com/a` ma, come percorsi secondari non aggiuntive`http://contoso.com/a/b`</span><span class="sxs-lookup"><span data-stu-id="85e58-133">Blocks a site `http://contoso.com/a` but not additional subpaths like `http://contoso.com/a/b`</span></span>  <br/> |
|`http://contoso.com/a*`  <br/> |<span data-ttu-id="85e58-134">Blocca un sito `http://contoso.com/a` e i percorsi secondari aggiuntive`http://contoso.com/a/b`</span><span class="sxs-lookup"><span data-stu-id="85e58-134">Blocks a site `http://contoso.com/a` and additional subpaths like `http://contoso.com/a/b`</span></span>  <br/> |
   
5. <span data-ttu-id="85e58-135">Dopo aver aggiunto gli URL, nell'angolo inferiore destro dello schermo, scegliere **Salva**.</span><span class="sxs-lookup"><span data-stu-id="85e58-135">When you are finished adding URLs, in the lower right corner of the screen, choose **Save**.</span></span>
    
## <a name="how-to-define-exceptions-for-certain-users-in-an-organization"></a><span data-ttu-id="85e58-136">Come definire le eccezioni per utenti specifici in un'organizzazione</span><span class="sxs-lookup"><span data-stu-id="85e58-136">How to define exceptions for certain users in an organization</span></span>

<span data-ttu-id="85e58-p109">Se si desidera determinati gruppi siano in grado di visualizzare gli URL che potrebbe essere bloccati per altri utenti, è possibile specificare un criterio degli strumenti di analisi collegamenti sicuri da applicare a destinatari specifici. Vedere [impostare un "non di riscrittura" URL elenco personalizzato utilizzo degli strumenti di analisi dei collegamenti sicuri](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md).</span><span class="sxs-lookup"><span data-stu-id="85e58-p109">If you want certain groups to be able to view URLs that might be blocked for others, you can specify an ATP Safe Links policy that applies to specific recipients. See [Set up a custom "do not rewrite" URLs list using ATP Safe Links](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md).</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="85e58-139">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="85e58-139">Related topics</span></span>

[<span data-ttu-id="85e58-140">Office 365 Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="85e58-140">Office 365 Advanced Threat Protection</span></span>](office-365-atp.md)
  
[<span data-ttu-id="85e58-141">Collegamenti degli strumenti di analisi sicuro in Office 365</span><span class="sxs-lookup"><span data-stu-id="85e58-141">ATP Safe Links in Office 365</span></span>](atp-safe-links.md)
  
[<span data-ttu-id="85e58-142">Impostare i criteri degli strumenti di analisi collegamenti attendibili in Office 365</span><span class="sxs-lookup"><span data-stu-id="85e58-142">Set up ATP Safe Links policies in Office 365</span></span>](set-up-atp-safe-links-policies.md)
  
[<span data-ttu-id="85e58-143">Allegati degli strumenti di analisi sicuro in Office 365</span><span class="sxs-lookup"><span data-stu-id="85e58-143">ATP Safe Attachments in Office 365</span></span>](atp-safe-attachments.md)

[<span data-ttu-id="85e58-144">Le autorizzazioni di sicurezza di Office 365 &amp; centro conformità</span><span class="sxs-lookup"><span data-stu-id="85e58-144">Permissions in the Office 365 Security &amp; Compliance Center</span></span>](permissions-in-the-security-and-compliance-center.md)
  

