---
title: Collegamenti sicuri ATP di Office 365
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.audience: Admin
ms.topic: overview
f1_keywords:
- "197503"
ms.service: o365-administration
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MET150
- MOE150
- ZVO160
- ZXL160
- ZPP160
- ZWD160
ms.assetid: dd6a1fef-ec4a-4cf4-a25a-bb591c5811e3
description: La caratteristica di collegamenti sicuro offre verifica momento del clic dei collegamenti ipertestuali nei documenti di Office e nei messaggi di posta elettronica. Utilizzare i collegamenti sicuri per proteggere l'organizzazione di phishing e altri attacchi.
ms.openlocfilehash: dcb5f681d8d7c2ff92aeecb46388e59c406fa0f9
ms.sourcegitcommit: ddfa0ac1f8ef95a78dcc1468241ef29363d56b5b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/30/2018
ms.locfileid: "23520135"
---
# <a name="office-365-atp-safe-links"></a><span data-ttu-id="e6032-104">Collegamenti sicuri ATP di Office 365</span><span class="sxs-lookup"><span data-stu-id="e6032-104">Office 365 ATP Safe Links</span></span>

<span data-ttu-id="e6032-p102">Collegamenti sicuro degli strumenti di analisi Office 365 (degli strumenti di analisi collegamenti sicuro) (insieme a [Office 365 degli strumenti di analisi provvisoria allegati](atp-safe-attachments.md)) è un set di caratteristiche di sicurezza distribuito come parte di [Protezione di Office 365 avanzate minaccia](office-365-atp.md) per le organizzazioni aziendali. Collegamenti sicuro degli strumenti di analisi consentono di proteggere l'organizzazione fornendo il momento del clic verifica degli indirizzi web (URL) in messaggi di posta elettronica e documenti di Office. Protezione viene definita tramite i [criteri degli strumenti di analisi collegamenti sicuri](set-up-atp-safe-links-policies.md) impostate dal team di protezione di Office 365.</span><span class="sxs-lookup"><span data-stu-id="e6032-p102">Office 365 ATP Safe Links (ATP Safe Links) (along with [Office 365 ATP Safe Attachments](atp-safe-attachments.md)) is a set of security features offered as part of [Office 365 Advanced Threat Protection](office-365-atp.md) for enterprise organizations. ATP Safe Links can help protect your organization by providing time-of-click verification of web addresses (URLs) in email messages and Office documents. Protection is defined through [ATP Safe Links policies](set-up-atp-safe-links-policies.md) that are set by your Office 365 security team.</span></span> 
  
<span data-ttu-id="e6032-p103">Dopo aver installato i criteri degli strumenti di analisi collegamenti sicuro sul posto, gli amministratori globali di Office 365, security administrators e lettori sicurezza possono [visualizzare i report per la protezione avanzata di rischio](view-reports-for-atp.md). Le informazioni contenute in questi rapporti consentono al team di protezione eseguire ulteriori passaggi per proteggere l'organizzazione o problemi di protezione di ricerca.</span><span class="sxs-lookup"><span data-stu-id="e6032-p103">Once your ATP Safe Links policies are in place, Office 365 global administrators, security administrators, and security readers can [view reports for Advanced Threat Protection](view-reports-for-atp.md). The information in those reports can help your security team take further steps to protect your organization or research security incidents.</span></span>
  
<span data-ttu-id="e6032-110">Nuove funzionalità vengono aggiunti continuamente ai collegamenti sicuro degli strumenti di analisi:</span><span class="sxs-lookup"><span data-stu-id="e6032-110">New features are continually being added to ATP Safe Links:</span></span>
  
- <span data-ttu-id="e6032-111">A partire da ritardo ottobre 2017, protezione degli strumenti di analisi collegamenti sicuro viene estesa per applicare agli URL nel messaggio di posta elettronica, nonché gli URL nei documenti di Office 365 ProPlus, ad esempio Word, Excel, PowerPoint e Visio in Windows, nonché Office apps iOS e dispositivi Android.</span><span class="sxs-lookup"><span data-stu-id="e6032-111">Beginning in late October 2017, ATP Safe Links protection is extended to apply to URLs in email as well as URLs in Office 365 ProPlus documents, such as Word, Excel, PowerPoint, and Visio on Windows, as well as Office apps on iOS and Android devices.</span></span>
    
- <span data-ttu-id="e6032-112">A partire da marzo 2018 protezione degli strumenti di analisi collegamenti sicuro viene estesa da applicare alla posta elettronica inviato tra utenti dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="e6032-112">Beginning in March 2018, ATP Safe Links protection is extended to apply to email sent between people in an organization.</span></span>
    
- <span data-ttu-id="e6032-113">A partire dalla seconda parte del 2018 protezione degli strumenti di analisi collegamenti sicuro viene estesa per applicare agli URL in Office Online (Online di Word, Excel Online, in linea di PowerPoint e OneNote Online) e Office 365 ProPlus su Mac.</span><span class="sxs-lookup"><span data-stu-id="e6032-113">Beginning in the second half of 2018, ATP Safe Links protection is extended to apply to URLs in Office Online (Word Online, Excel Online, PowerPoint Online, and OneNote Online) and Office 365 ProPlus on Mac.</span></span>
    
- <span data-ttu-id="e6032-114">Inizio in settembre 2018, [pagine di avviso degli strumenti di analisi di Office 365](atp-safe-links-warning-pages.md) caratteristica una nuova combinazione di colori, ulteriori dettagli e la possibilità di continuare a un sito nonostante assegnate gli avvisi e suggerimenti.</span><span class="sxs-lookup"><span data-stu-id="e6032-114">Beginning in September 2018, [Office 365 ATP warning pages](atp-safe-links-warning-pages.md) feature a new color scheme, more details, and the ability to continue to a site despite given warnings and recommendations.</span></span> 
         
## <a name="how-atp-safe-links-in-email-works"></a><span data-ttu-id="e6032-115">Funzionamento degli strumenti di analisi collegamenti sicuri nella posta elettronica</span><span class="sxs-lookup"><span data-stu-id="e6032-115">How ATP Safe Links in email works</span></span>

<span data-ttu-id="e6032-116">In dettaglio, ecco collegamenti sicuro degli strumenti di analisi del funzionamento della protezione per gli URL nella posta elettronica (ospitata in Office 365 non locale):</span><span class="sxs-lookup"><span data-stu-id="e6032-116">At a high level, here's how ATP Safe Links protection works for URLs in email (hosted in Office 365, not on-premises):</span></span>
  
1. <span data-ttu-id="e6032-117">Gli utenti ricevono messaggi di posta elettronica contenenti URL.</span><span class="sxs-lookup"><span data-stu-id="e6032-117">People receive email messages that contain URLs.</span></span>
    
2. <span data-ttu-id="e6032-118">Viene inoltrata tutta la posta elettronica tramite Exchange Online Protection, dove IP e busta i filtri, protezione da malware basata su firma, vengono applicati i filtri di protezione da posta indesiderata e anti-malware.</span><span class="sxs-lookup"><span data-stu-id="e6032-118">All email goes through Exchange Online Protection, where IP and envelope filters, signature-based malware protection, anti-spam and anti-malware filters are applied.</span></span>
    
3. <span data-ttu-id="e6032-119">I messaggi arrivano nella posta in arrivo di utenti.</span><span class="sxs-lookup"><span data-stu-id="e6032-119">Email arrives in people's inboxes.</span></span>
    
4. <span data-ttu-id="e6032-120">Un utente accede a Office 365 e passa alla posta in arrivo di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="e6032-120">A user signs in to Office 365, and goes to their email inbox.</span></span>
    
5. <span data-ttu-id="e6032-121">L'utente viene aperto un messaggio di posta elettronica e quindi fa clic su un URL nel messaggio di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="e6032-121">The user opens an email message, and then clicks on a URL in the email message.</span></span>
    
6. <span data-ttu-id="e6032-p104">La funzionalità degli strumenti di analisi collegamenti sicuri immediatamente controllerà l'URL prima di aprire il sito Web. L'URL viene identificato come bloccato, dannoso o sicuri.</span><span class="sxs-lookup"><span data-stu-id="e6032-p104">The ATP Safe Links feature immediately checks the URL before opening the website. The URL is identified as blocked, malicious, or safe.</span></span>
    
1. <span data-ttu-id="e6032-124">Se l'URL di un sito Web incluso in un [elenco degli URL "non di riscrittura" personalizzato](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md) per un criterio che si applica all'utente, viene aperto il sito Web.</span><span class="sxs-lookup"><span data-stu-id="e6032-124">If the URL is to a website that is included in a [custom "Do not rewrite" URLs list](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md) for a policy that applies to the user, the website opens.</span></span> 
    
2. <span data-ttu-id="e6032-125">Se l'URL di un sito Web inclusa in dell'organizzazione [personalizzato bloccati gli URL](set-up-a-custom-blocked-urls-list-wtih-atp.md), verrà visualizzata una [pagina di avviso](atp-safe-links-warning-pages.md) .</span><span class="sxs-lookup"><span data-stu-id="e6032-125">If the URL is to a website that is included in the organization's [custom blocked URLs list](set-up-a-custom-blocked-urls-list-wtih-atp.md), a [warning page](atp-safe-links-warning-pages.md) opens.</span></span> 
    
3. <span data-ttu-id="e6032-126">Se l'URL di un sito Web che è stato determinato che dannoso, verrà visualizzata una [pagina di avviso](atp-safe-links-warning-pages.md) .</span><span class="sxs-lookup"><span data-stu-id="e6032-126">If the URL is to a website that has been determined to be malicious, a [warning page](atp-safe-links-warning-pages.md) opens.</span></span> 
    
4. <span data-ttu-id="e6032-127">Se l'URL viene inserito in un file scaricabile e dell'organizzazione [degli strumenti di analisi collegamenti sicuro politiche](set-up-atp-safe-links-policies.md) sono configurati per l'analisi di questo tipo di contenuto, viene controllato il file disponibile.</span><span class="sxs-lookup"><span data-stu-id="e6032-127">If the URL goes to a downloadable file and your organization's [ATP Safe Links policies](set-up-atp-safe-links-policies.md) are configured to scan such content, the downloadable file is checked.</span></span> 
    
5. <span data-ttu-id="e6032-128">Se l'URL è determinata da sicuro, viene aperto il sito Web.</span><span class="sxs-lookup"><span data-stu-id="e6032-128">If the URL is determined to be safe, the website opens.</span></span>
    
## <a name="how-atp-safe-links-in-office-documents-works"></a><span data-ttu-id="e6032-129">Funzionamento degli strumenti di analisi collegamenti sicuri nei documenti di Office</span><span class="sxs-lookup"><span data-stu-id="e6032-129">How ATP Safe Links in Office documents works</span></span>

<span data-ttu-id="e6032-130">In dettaglio, ecco funzionamento della protezione degli strumenti di analisi collegamenti sicuri per gli URL nelle applicazioni di Office 365 ProPlus (versioni correnti di Word, Excel e PowerPoint in Windows o Mac, applicazioni di Office su iOS o dispositivi Android e Visio su Windows):</span><span class="sxs-lookup"><span data-stu-id="e6032-130">At a high level, here's how ATP Safe Links protection works for URLs in Office 365 ProPlus applications (current versions of Word, Excel, and PowerPoint on Windows or Mac, Office apps on iOS or Android devices, and Visio on Windows):</span></span>
  
1. <span data-ttu-id="e6032-131">Utenti sono installati Office 365 ProPlus nel proprio computer, smartphone o Tablet PC.</span><span class="sxs-lookup"><span data-stu-id="e6032-131">People have installed Office 365 ProPlus on their computer, smartphone, or tablet.</span></span>
    
2. <span data-ttu-id="e6032-p105">L'utente apre un Word, Excel, PowerPoint o Visio e viene effettuato l'accesso a Office 365 Enterprise utilizzando il proprio account di lavoro o della scuola. Il documento contiene gli URL.</span><span class="sxs-lookup"><span data-stu-id="e6032-p105">A user opens a Word, Excel, PowerPoint, or Visio, and is signed in to Office 365 Enterprise using their work or school account. The document contains URLs.</span></span>
    
3. <span data-ttu-id="e6032-134">Quando l'utente fa clic su un URL nel documento, il collegamento viene controllato dal servizio collegamenti sicuro degli strumenti di analisi.</span><span class="sxs-lookup"><span data-stu-id="e6032-134">When the user clicks on a URL in the document, the link is checked by the ATP Safe Links service.</span></span>
    
  - <span data-ttu-id="e6032-135">Se l'URL di un sito Web incluso in un [elenco degli URL "non di riscrittura" personalizzato](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md) per un criterio che si applica all'utente, l'utente passa al sito Web.</span><span class="sxs-lookup"><span data-stu-id="e6032-135">If the URL is to a website that is included in a [custom "Do not rewrite" URLs list](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md) for a policy that applies to the user, that user is taken to the website.</span></span> 
    
  - <span data-ttu-id="e6032-136">Se l'URL di un sito Web inclusa in dell'organizzazione [personalizzato bloccati gli URL](set-up-a-custom-blocked-urls-list-wtih-atp.md), l'utente passa a una [pagina di avviso](atp-safe-links-warning-pages.md).</span><span class="sxs-lookup"><span data-stu-id="e6032-136">If the URL is to a website that is included in the organization's [custom blocked URLs list](set-up-a-custom-blocked-urls-list-wtih-atp.md), the user is taken to a [warning page](atp-safe-links-warning-pages.md).</span></span>
    
  - <span data-ttu-id="e6032-137">Se l'URL di un sito Web che è stato determinato che dannoso, l'utente passa a una [pagina di avviso](atp-safe-links-warning-pages.md).</span><span class="sxs-lookup"><span data-stu-id="e6032-137">If the URL is to a website that has been determined to be malicious, the user is taken to a [warning page](atp-safe-links-warning-pages.md).</span></span>
    
  - <span data-ttu-id="e6032-138">Se l'URL viene inserito in un file scaricabile e i [criteri degli strumenti di analisi collegamenti attendibili](set-up-atp-safe-links-policies.md) sono configurati per l'analisi tali download, viene controllato il file disponibile.</span><span class="sxs-lookup"><span data-stu-id="e6032-138">If the URL goes to a downloadable file and the [ATP Safe Links policies](set-up-atp-safe-links-policies.md) are configured to scan such downloads, the downloadable file is checked.</span></span> 
    
  - <span data-ttu-id="e6032-139">Se l'URL è considerato sicuro, l'utente viene indirizzato al sito Web.</span><span class="sxs-lookup"><span data-stu-id="e6032-139">If the URL is considered safe, the user is taken to the website.</span></span>
    
## <a name="how-to-get-atp-safe-links-protection"></a><span data-ttu-id="e6032-140">Come ottenere protezione degli strumenti di analisi collegamenti sicuri</span><span class="sxs-lookup"><span data-stu-id="e6032-140">How to get ATP Safe Links protection</span></span>

<span data-ttu-id="e6032-p106">La funzionalità degli strumenti di analisi collegamenti sicura fa parte di avanzate di rischio protezione, è incluso in Office 365 Enterprise E5. Se l'organizzazione utilizza un'altra sottoscrizione Office 365 Enterprise, avanzate Threat Protection può essere acquistato come componente aggiuntivo. (Come un amministratore globale, nell'interfaccia di amministrazione di Office 365 scegliere **fatturazione** \> **Aggiungi sottoscrizioni**.) Per ulteriori informazioni, vedere [Office 365 Platform Service Description: protezione di Office 365 &amp; centro conformità](https://technet.microsoft.com/en-us/library/dn933793.aspx) e [acquistare o modificare un componente aggiuntivo per Office 365 per aziende](https://support.office.com/article/4e7b57d6-b93b-457d-aecd-0ea58bff07a6).</span><span class="sxs-lookup"><span data-stu-id="e6032-p106">The ATP Safe Links feature is part of Advanced Threat Protection, which is included in Office 365 Enterprise E5. If your organization is using another Office 365 Enterprise subscription, Advanced Threat Protection can be purchased as an add-on. (As a global admin, in the Office 365 admin center, choose **Billing** \> **Add subscriptions**.) For more information, see [Office 365 Platform Service Description: Office 365 Security &amp; Compliance Center](https://technet.microsoft.com/en-us/library/dn933793.aspx) and [Buy or edit an add-on for Office 365 for business](https://support.office.com/article/4e7b57d6-b93b-457d-aecd-0ea58bff07a6).</span></span>
  
<span data-ttu-id="e6032-144">Le caratteristiche degli strumenti di analisi collegamenti attendibili sono attivi quando:</span><span class="sxs-lookup"><span data-stu-id="e6032-144">The ATP Safe Links features are active when:</span></span>
  
- <span data-ttu-id="e6032-p107">**Vengono impostati i criteri degli strumenti di analisi collegamenti sicuri** per la posta elettronica e per i documenti di Word, Excel, PowerPoint e Visio. Vedere [impostazione dei criteri di strumenti di analisi collegamenti attendibili in Office 365](set-up-atp-safe-links-policies.md).</span><span class="sxs-lookup"><span data-stu-id="e6032-p107">**ATP Safe Links policies are set up** for email and for Word, Excel, PowerPoint, and Visio documents. (See [Set up ATP safe links policies in Office 365](set-up-atp-safe-links-policies.md).)</span></span>
    
- <span data-ttu-id="e6032-p108">**Gli utenti hanno effettuato l'accesso a Office 365** utilizzando il proprio account di lavoro o della scuola. Vedere [accesso a Office o Office 365](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426).</span><span class="sxs-lookup"><span data-stu-id="e6032-p108">**Users have signed into Office 365** using their work or school account. (See [Sign in to Office or Office 365](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426).)</span></span>
    
- <span data-ttu-id="e6032-149">**Che messaggio di posta elettronica dell'organizzazione è ospitata in Office 365**, non in un server locale.</span><span class="sxs-lookup"><span data-stu-id="e6032-149">**The organization's email is hosted in Office 365**, not in an on-premises server.</span></span> 
    
## <a name="make-sure-atp-safe-links-protection-is-in-place"></a><span data-ttu-id="e6032-150">Verificare che sia protezione degli strumenti di analisi collegamenti sicuro sul posto</span><span class="sxs-lookup"><span data-stu-id="e6032-150">Make sure ATP Safe Links protection is in place</span></span>

<span data-ttu-id="e6032-p109">Un modo efficace per vedere modalità di utilizzo di protezione degli strumenti di analisi collegamenti sicuri per l'organizzazione è visualizzando i [report per la protezione avanzata di rischio](view-reports-for-atp.md). Inoltre, come amministratore globale o di sicurezza, assicurarsi di esaminare i [criteri degli strumenti di analisi collegamenti sicuri](set-up-atp-safe-links-policies.md). Collegamenti sicuro degli strumenti di analisi criteri determinano se protezione si applica a collegamenti ipertestuali nei messaggi di posta elettronica solo o in anche i documenti di Office.</span><span class="sxs-lookup"><span data-stu-id="e6032-p109">One good way to see how ATP Safe Links protection is working for your organization is by [viewing reports for Advanced Threat Protection](view-reports-for-atp.md). Additionally, as a global or security administrator, be sure to review your [ATP Safe Links policies](set-up-atp-safe-links-policies.md). ATP Safe Links policies determine whether protection applies to hyperlinks in email messages only or to Office documents as well.</span></span>
  
<span data-ttu-id="e6032-p110">Nella tabella seguente vengono descritti alcuni scenari di esempio in protezione degli strumenti di analisi collegamenti attendibili potrebbero o potrebbe non essere presenti. In tutti i casi, si presuppone che l'organizzazione dispone di Office 365 Enterprise E5, che include una protezione avanzata di rischio.</span><span class="sxs-lookup"><span data-stu-id="e6032-p110">The following table describes some example scenarios where ATP Safe Links protection might or might not be in place. In all of these cases, we assume the organization has Office 365 Enterprise E5, which includes Advanced Threat Protection.</span></span>
  
|<span data-ttu-id="e6032-156">**Scenario di esempio**</span><span class="sxs-lookup"><span data-stu-id="e6032-156">**Example scenario**</span></span>|<span data-ttu-id="e6032-157">**Protezione degli strumenti di analisi collegamenti sicuro si applica in questo caso?**</span><span class="sxs-lookup"><span data-stu-id="e6032-157">**Does ATP Safe Links protection apply in this case?**</span></span>|
|:-----|:-----|
|<span data-ttu-id="e6032-p111">Jean è un membro di un gruppo con i criteri degli strumenti di analisi collegamenti provvisoria gli URL relativi alla posta elettronica e documenti di Office. Jean apre una presentazione da un utente inviato in PowerPoint 2016 e quindi fa clic su un URL nella presentazione.</span><span class="sxs-lookup"><span data-stu-id="e6032-p111">Jean is a member of a group that has ATP Safe Links policies covering URLs in email and Office documents. Jean opens a presentation that someone sent in PowerPoint 2016, and then clicks a URL in the presentation.</span></span>  <br/> |<span data-ttu-id="e6032-p112">Sì. I criteri degli strumenti di analisi collegamenti attendibili definiti si applicano a di Jean gruppo, di Jean messaggio di posta elettronica e documenti di Word, Excel, PowerPoint o Visio Jean visualizzata, purché Jean ha eseguito l'accesso e l'utilizzo Office 365 ProPlus in Windows, iOS o dispositivi Android.</span><span class="sxs-lookup"><span data-stu-id="e6032-p112">Yes. The ATP Safe Links policies that are defined apply to Jean's group, Jean's email, and Word, Excel, PowerPoint, or Visio documents that Jean opens, so long as Jean is signed in and using Office 365 ProPlus on Windows, iOS, or Android devices.</span></span>  <br/> |
|<span data-ttu-id="e6032-p113">Nell'organizzazione, non globale o sicurezza Chris gli amministratori hanno definito ancora tutti i criteri di collegamenti sicuro degli strumenti di analisi. Chris riceve un messaggio di posta elettronica contenente un URL di un sito Web dannoso. Chris in grado di riconoscere l'URL è dannoso e fa clic sul collegamento.</span><span class="sxs-lookup"><span data-stu-id="e6032-p113">In Chris's organization, no global or security administrators have defined any ATP safe links policies yet. Chris receives an email that contains a URL to a malicious website. Chris is unaware the URL is malicious and clicks the link.</span></span>  <br/> |<span data-ttu-id="e6032-p114">No. Il criterio predefinito che vengono trattati gli URL per tutti gli utenti dell'organizzazione deve essere definito nell'ordine indicato per la protezione in locale.</span><span class="sxs-lookup"><span data-stu-id="e6032-p114">No. The default policy that covers URLs for everyone in the organization must be defined in order for protection to be in place.</span></span>  <br/> |
|<span data-ttu-id="e6032-p115">In mia organizzazione non globale o security administrators definito o modificati tutti i criteri degli strumenti di analisi collegamenti sicuri ancora. PAT viene aperto un documento di Word e fa clic su un URL nel file.</span><span class="sxs-lookup"><span data-stu-id="e6032-p115">In Pat's organization, no global or security administrators have defined or edited any ATP Safe Links policies yet. Pat opens a Word document and clicks a URL in the file.</span></span>  <br/> |<span data-ttu-id="e6032-p116">Criteri A No. che includono i documenti di Office devono essere definito nell'ordine indicato per la protezione in locale. Vedere [impostare i criteri degli strumenti di analisi collegamenti attendibili in Office 365](set-up-atp-safe-links-policies.md).</span><span class="sxs-lookup"><span data-stu-id="e6032-p116">No. A policy that includes Office documents must be defined in order for protection to be in place. See [Set up ATP Safe Links policies in Office 365](set-up-atp-safe-links-policies.md).  </span></span><br/> |
|<span data-ttu-id="e6032-p117">Organizzazione di Lee dispone di un criterio degli strumenti di analisi collegamenti sicuro con `http://tailspintoys.com` elencato come un sito Web bloccato. Lee riceve un messaggio di posta elettronica contenente un URL di `http://tailspintoys.com/aboutus/trythispage`. Lee fa clic sull'URL.</span><span class="sxs-lookup"><span data-stu-id="e6032-p117">Lee's organization has a ATP Safe Links policy that has `http://tailspintoys.com` listed as a blocked website. Lee receives an email message that contains a URL to `http://tailspintoys.com/aboutus/trythispage`. Lee clicks the URL.  </span></span><br/> |<span data-ttu-id="e6032-p118">Dipende dal fatto l'intero sito tutte quelle secondarie sono inclusi nell'elenco dei bloccati gli URL. Vedere [impostare un elenco degli URL bloccato personalizzato utilizzo degli strumenti di analisi dei collegamenti sicuri](set-up-a-custom-blocked-urls-list-wtih-atp.md).</span><span class="sxs-lookup"><span data-stu-id="e6032-p118">It depends on whether the entire site and all its subpages are included in the list of blocked URLs. See [Set up a custom blocked URLs list using ATP Safe Links](set-up-a-custom-blocked-urls-list-wtih-atp.md).  </span></span><br/> |
|<span data-ttu-id="e6032-177">Chiara, importazione suggerimenti colleghi di Jean, invia un messaggio di posta elettronica a Jean, senza sapere che il messaggio di posta elettronica contiene un URL dannoso.</span><span class="sxs-lookup"><span data-stu-id="e6032-177">Jamie, Jean's colleague, sends an email to Jean, not knowing that the email contains a malicious URL.</span></span>  <br/> |<span data-ttu-id="e6032-p119">Dipende dal fatto definiti criteri degli strumenti di analisi collegamenti sicuri per la posta elettronica inviato all'interno dell'organizzazione. Vedere [impostare i criteri degli strumenti di analisi collegamenti attendibili in Office 365](set-up-atp-safe-links-policies.md).</span><span class="sxs-lookup"><span data-stu-id="e6032-p119">It depends on whether ATP Safe Links policies are defined for email sent within the organization. See [Set up ATP Safe Links policies in Office 365](set-up-atp-safe-links-policies.md).  </span></span><br/> |
   
## <a name="related-topics"></a><span data-ttu-id="e6032-180">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="e6032-180">Related topics</span></span>
<span data-ttu-id="e6032-181"><a name="howtosee"> </a></span><span class="sxs-lookup"><span data-stu-id="e6032-181"></span></span>

[<span data-ttu-id="e6032-182">Office 365 Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="e6032-182">Office 365 Advanced Threat Protection</span></span>](office-365-atp.md)
  
[<span data-ttu-id="e6032-183">Impostare i criteri degli strumenti di analisi collegamenti attendibili in Office 365</span><span class="sxs-lookup"><span data-stu-id="e6032-183">Set up ATP Safe Links policies in Office 365</span></span>](set-up-atp-safe-links-policies.md)
  
[<span data-ttu-id="e6032-184">Allegati degli strumenti di analisi sicuro in Office 365</span><span class="sxs-lookup"><span data-stu-id="e6032-184">ATP Safe Attachments in Office 365</span></span>](atp-safe-attachments.md)
  
[<span data-ttu-id="e6032-185">Le funzionalità di anti-phishing ATP in Office 365</span><span class="sxs-lookup"><span data-stu-id="e6032-185">ATP anti-phishing capabilities in Office 365</span></span>](atp-anti-phishing.md)
  
[<span data-ttu-id="e6032-186">Visualizzare i report per Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="e6032-186">View the reports for Advanced Threat Protection</span></span>](view-reports-for-atp.md)
  
