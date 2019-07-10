---
title: Funzionamento di collegamenti sicuri di Office 365 ATP
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: Admin
ms.date: 05/19/2019
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
description: La funzionalità collegamenti sicuri fornisce il tempo di fare clic sulla verifica dei link ipertestuali nei documenti di Office e nei messaggi di posta elettronica. Leggere questo articolo per informazioni su come funzionano i collegamenti sicuri di ATP.
ms.openlocfilehash: 7570fd65a9831a6436eec8c402a2bc0c2ae09b40
ms.sourcegitcommit: 32ecff689ae32c59a39b7633ca0f36a304e7516e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/09/2019
ms.locfileid: "35599182"
---
# <a name="how-office-365-atp-safe-links-works"></a><span data-ttu-id="60184-104">Funzionamento di collegamenti sicuri di Office 365 ATP</span><span class="sxs-lookup"><span data-stu-id="60184-104">How Office 365 ATP Safe Links works</span></span>
         
## <a name="how-atp-safe-links-works-with-urls-in-email"></a><span data-ttu-id="60184-105">Funzionamento dei collegamenti sicuri di ATP con gli URL nella posta elettronica</span><span class="sxs-lookup"><span data-stu-id="60184-105">How ATP Safe Links works with URLs in email</span></span>

<span data-ttu-id="60184-106">A livello elevato, ecco come funziona la protezione dei [collegamenti sicuri di ATP](atp-safe-links.md) per gli URL nella posta elettronica (ospitati in Office 365, non in locale):</span><span class="sxs-lookup"><span data-stu-id="60184-106">At a high level, here's how [ATP Safe Links](atp-safe-links.md) protection works for URLs in email (hosted in Office 365, not on-premises):</span></span>
  
1. <span data-ttu-id="60184-107">Gli utenti ricevono messaggi di posta elettronica, alcuni dei quali contengono URL.</span><span class="sxs-lookup"><span data-stu-id="60184-107">People receive email messages, some of which contain URLs.</span></span>
    
2. <span data-ttu-id="60184-108">Tutti i messaggi di posta elettronica passano attraverso Exchange Online Protection, dove vengono applicati i filtri Internet (IP) e busta, la protezione antimalware basata sulle firme, i filtri anti-spam e antivirus.</span><span class="sxs-lookup"><span data-stu-id="60184-108">All email goes through Exchange Online Protection, where internet protocol (IP) and envelope filters, signature-based malware protection, anti-spam and anti-malware filters are applied.</span></span> 
    
3. <span data-ttu-id="60184-109">La posta elettronica arriva nelle cassette postali degli utenti.</span><span class="sxs-lookup"><span data-stu-id="60184-109">Email arrives in people's inboxes.</span></span>
    
4. <span data-ttu-id="60184-110">Un utente accede a Office 365 e passa alla posta in arrivo.</span><span class="sxs-lookup"><span data-stu-id="60184-110">A user signs in to Office 365, and goes to their email inbox.</span></span>
    
5. <span data-ttu-id="60184-111">L'utente apre un messaggio di posta elettronica e fa clic su un URL nel messaggio di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="60184-111">The user opens an email message, and clicks on a URL in the email message.</span></span>
    
6. <span data-ttu-id="60184-112">La caratteristica collegamenti sicuri ATP verifica immediatamente l'URL prima di aprire il sito Web.</span><span class="sxs-lookup"><span data-stu-id="60184-112">The ATP Safe Links feature immediately checks the URL before opening the website.</span></span> <span data-ttu-id="60184-113">L'URL viene identificato come bloccato, dannoso o sicuro.</span><span class="sxs-lookup"><span data-stu-id="60184-113">The URL is identified as blocked, malicious, or safe.</span></span>
    
    - <span data-ttu-id="60184-114">Se l'URL è associato a un sito Web incluso in un [elenco di URL personalizzato "non riscrivere"](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md) per un criterio che si applica all'utente, il sito Web verrà aperto.</span><span class="sxs-lookup"><span data-stu-id="60184-114">If the URL is to a website that is included in a [custom "Do not rewrite" URLs list](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md) for a policy that applies to the user, the website opens.</span></span> 
    
    - <span data-ttu-id="60184-115">Se l'URL è incluso nell' [elenco degli URL bloccati personalizzati](set-up-a-custom-blocked-urls-list-wtih-atp.md)dell'organizzazione, viene visualizzata una [pagina di avviso](atp-safe-links-warning-pages.md) .</span><span class="sxs-lookup"><span data-stu-id="60184-115">If the URL is to a website that is included in the organization's [custom blocked URLs list](set-up-a-custom-blocked-urls-list-wtih-atp.md), a [warning page](atp-safe-links-warning-pages.md) opens.</span></span> 
    
    - <span data-ttu-id="60184-116">Se l'URL è associato a un sito Web che è stato determinato come dannoso, viene visualizzata una [pagina di avviso](atp-safe-links-warning-pages.md) .</span><span class="sxs-lookup"><span data-stu-id="60184-116">If the URL is to a website that has been determined to be malicious, a [warning page](atp-safe-links-warning-pages.md) opens.</span></span> 
    
    - <span data-ttu-id="60184-117">Se l'URL passa a un file scaricabile e i criteri per i [collegamenti sicuri ATP](set-up-atp-safe-links-policies.md) dell'organizzazione sono configurati per l'analisi di tali contenuti, il file scaricabile viene controllato.</span><span class="sxs-lookup"><span data-stu-id="60184-117">If the URL goes to a downloadable file and your organization's [ATP Safe Links policies](set-up-atp-safe-links-policies.md) are configured to scan such content, the downloadable file is checked.</span></span> 
    
    - <span data-ttu-id="60184-118">Se l'URL è determinato per la sicurezza, il sito Web verrà aperto.</span><span class="sxs-lookup"><span data-stu-id="60184-118">If the URL is determined to be safe, the website opens.</span></span>
    
## <a name="how-atp-safe-links-works-with-urls-in-office-documents"></a><span data-ttu-id="60184-119">Funzionamento dei collegamenti sicuri di ATP con gli URL nei documenti di Office</span><span class="sxs-lookup"><span data-stu-id="60184-119">How ATP Safe Links works with URLs in Office documents</span></span>

<span data-ttu-id="60184-120">A livello elevato, ecco come funziona la protezione dei [collegamenti sicuri di ATP](atp-safe-links.md) per gli URL nelle applicazioni di ProPlus di Office 365 (versioni correnti di Word, Excel e PowerPoint su Windows o Mac, app di Office su dispositivi iOS o Android, Visio su Windows, OneNote online e Office Online):</span><span class="sxs-lookup"><span data-stu-id="60184-120">At a high level, here's how [ATP Safe Links](atp-safe-links.md) protection works for URLs in Office 365 ProPlus applications (current versions of Word, Excel, and PowerPoint on Windows or Mac, Office apps on iOS or Android devices, Visio on Windows, OneNote Online, and Office Online):</span></span>
  
1. <span data-ttu-id="60184-121">Gli utenti hanno installato Office 365 ProPlus nel computer, nello smartphone o nel tablet.</span><span class="sxs-lookup"><span data-stu-id="60184-121">People have installed Office 365 ProPlus on their computer, smartphone, or tablet.</span></span> <span data-ttu-id="60184-122">(Oppure, utilizzano Office Online nel browser).</span><span class="sxs-lookup"><span data-stu-id="60184-122">(Or, they are using Office Online in their browser.)</span></span>
    
2. <span data-ttu-id="60184-123">Un utente apre una parola, Excel, PowerPoint o Visio e accede a Office 365 Enterprise utilizzando l'account aziendale o dell'Istituto di istruzione.</span><span class="sxs-lookup"><span data-stu-id="60184-123">A user opens a Word, Excel, PowerPoint, or Visio, and signs in to Office 365 Enterprise using their work or school account.</span></span> <span data-ttu-id="60184-124">Il documento contiene gli URL.</span><span class="sxs-lookup"><span data-stu-id="60184-124">The document contains URLs.</span></span>
    
3. <span data-ttu-id="60184-125">Quando l'utente fa clic su un URL del documento, il collegamento è controllato dal servizio collegamenti sicuri di ATP.</span><span class="sxs-lookup"><span data-stu-id="60184-125">When the user clicks on a URL in the document, the link is checked by the ATP Safe Links service.</span></span>
    
      - <span data-ttu-id="60184-126">Se l'URL è associato a un sito Web incluso in un [elenco di URL personalizzato "non riscrivere"](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md) per un criterio che si applica all'utente, l'utente viene indirizzato al sito Web.</span><span class="sxs-lookup"><span data-stu-id="60184-126">If the URL is to a website that is included in a [custom "Do not rewrite" URLs list](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md) for a policy that applies to the user, that user is taken to the website.</span></span> 
    
      - <span data-ttu-id="60184-127">Se l'URL è associato a un sito Web incluso nell' [elenco degli URL bloccati personalizzati](set-up-a-custom-blocked-urls-list-wtih-atp.md)dell'organizzazione, l'utente viene indirizzato a una [pagina di avviso](atp-safe-links-warning-pages.md).</span><span class="sxs-lookup"><span data-stu-id="60184-127">If the URL is to a website that is included in the organization's [custom blocked URLs list](set-up-a-custom-blocked-urls-list-wtih-atp.md), the user is taken to a [warning page](atp-safe-links-warning-pages.md).</span></span>
    
      - <span data-ttu-id="60184-128">Se l'URL è associato a un sito Web che è stato determinato come dannoso, l'utente viene indirizzato a una [pagina di avviso](atp-safe-links-warning-pages.md).</span><span class="sxs-lookup"><span data-stu-id="60184-128">If the URL is to a website that has been determined to be malicious, the user is taken to a [warning page](atp-safe-links-warning-pages.md).</span></span>
    
      - <span data-ttu-id="60184-129">Se l'URL passa a un file scaricabile e i [criteri dei collegamenti sicuri di ATP](set-up-atp-safe-links-policies.md) sono configurati per l'analisi di tali download, viene controllato il file scaricabile.</span><span class="sxs-lookup"><span data-stu-id="60184-129">If the URL goes to a downloadable file and the [ATP Safe Links policies](set-up-atp-safe-links-policies.md) are configured to scan such downloads, the downloadable file is checked.</span></span> 
    
      - <span data-ttu-id="60184-130">Se l'URL è considerato sicuro, l'utente viene reindirizzato al sito Web.</span><span class="sxs-lookup"><span data-stu-id="60184-130">If the URL is considered safe, the user is taken to the website.</span></span>

