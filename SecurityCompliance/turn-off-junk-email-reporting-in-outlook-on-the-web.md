---
title: Disattivare la segnalazione della posta indesiderata in Outlook sul Web
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 8d57fe9e-57b8-4884-9317-80b380804b4a
ms.collection:
- M365-security-compliance
description: In qualità di amministratore di Office 365, è possibile disattivare la possibilità per gli utenti di segnalare la posta elettronica come indesiderata.
ms.openlocfilehash: a2a8c2f9120ff4b1d2efab4d7ae63294ce7f923b
ms.sourcegitcommit: 32ecff689ae32c59a39b7633ca0f36a304e7516e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/09/2019
ms.locfileid: "35600292"
---
# <a name="turn-off-junk-email-reporting-in-outlook-on-the-web"></a><span data-ttu-id="bd746-103">Disattivare la segnalazione della posta indesiderata in Outlook sul Web</span><span class="sxs-lookup"><span data-stu-id="bd746-103">Turn off junk email reporting in Outlook on the web</span></span>

<span data-ttu-id="bd746-104">È possibile inviare messaggi di posta indesiderata, di phishing e non a Microsoft per l'analisi utilizzando le opzioni di segnalazione della posta indesiderata di Outlook sul Web (in precedenza note come Outlook Web App), come descritto in [report posta indesiderata e truffe di phishing in Outlook sul Web ](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md).</span><span class="sxs-lookup"><span data-stu-id="bd746-104">You can send junk, phishing, and not junk messages to Microsoft for analysis using the Outlook on the web (formerly known as Outlook Web App) junk email reporting options, as described in [Report junk email and phishing scams in Outlook on the web ](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md).</span></span> <span data-ttu-id="bd746-105">Se non si desidera utilizzare queste opzioni, gli amministratori possono disattivarli tramite il cmdlet [Set-OwaMailboxPolicy](http://technet.microsoft.com/library/530166f7-ab42-4609-ba73-9b5a39b567be.aspx) .</span><span class="sxs-lookup"><span data-stu-id="bd746-105">If you don't want to use these options,admins can turn them off via the [Set-OwaMailboxPolicy](http://technet.microsoft.com/library/530166f7-ab42-4609-ba73-9b5a39b567be.aspx) cmdlet.</span></span> 
  
## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="bd746-106">Che cosa è necessario sapere prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="bd746-106">What do you need to know before you begin?</span></span>
<span data-ttu-id="bd746-107"><a name="sectionSection0"> </a></span><span class="sxs-lookup"><span data-stu-id="bd746-107"></span></span>

- <span data-ttu-id="bd746-108">Tempo stimato per il completamento: 5 minuti</span><span class="sxs-lookup"><span data-stu-id="bd746-108">Estimated time to complete: 5 minutes</span></span>
    
- <span data-ttu-id="bd746-109">Per eseguire queste procedure, è necessario disporre delle autorizzazioni appropriate.</span><span class="sxs-lookup"><span data-stu-id="bd746-109">You need to be assigned permissions before you can perform this procedure or procedures.</span></span> <span data-ttu-id="bd746-110">Per sapere quali autorizzazioni sono necessarie, vedere "criteri cassetta postale di Outlook sul Web" nell'argomento [autorizzazioni di Outlook sul Web](http://technet.microsoft.com/library/57eca42a-5a7f-4c65-89f0-7a84f2dbea19.aspx#OutlookWebApp) .</span><span class="sxs-lookup"><span data-stu-id="bd746-110">To see what permissions you need, see the "Outlook on the web mailbox policies" entry in the [Outlook on the web permissions](http://technet.microsoft.com/library/57eca42a-5a7f-4c65-89f0-7a84f2dbea19.aspx#OutlookWebApp) topic.</span></span> 

- <span data-ttu-id="bd746-111">Per informazioni su come connettersi a PowerShell per Exchange Online, vedere [Connettersi a PowerShell per Exchange Online](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="bd746-111">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span></span>

## <a name="turn-off-junk-phishing-and-not-junk-reporting-to-microsoft"></a><span data-ttu-id="bd746-112">Disattiva la segnalazione di posta indesiderata, phishing e non di posta indesiderata a Microsoft</span><span class="sxs-lookup"><span data-stu-id="bd746-112">Turn off junk, phishing, and not junk reporting to Microsoft</span></span>
<span data-ttu-id="bd746-113"><a name="sectionSection1"> </a></span><span class="sxs-lookup"><span data-stu-id="bd746-113"></span></span>

<span data-ttu-id="bd746-114">Prima di tutto, eseguire il seguente comando per ottenere i nomi dei criteri cassetta postale di Outlook sul Web disponibili:</span><span class="sxs-lookup"><span data-stu-id="bd746-114">First, run the following command to get the names of your available Outlook on the web mailbox policies:</span></span>
  
```
Get-OwaMailboxPolicy | Format-Table Name
```

<span data-ttu-id="bd746-115">Successivamente, utilizzare la seguente sintassi per abilitare o disabilitare la creazione di messaggi di posta indesiderata e non per la gestione delle cianfrusaglie a Microsoft in Outlook sul Web:</span><span class="sxs-lookup"><span data-stu-id="bd746-115">Next, use the following syntax to enable or disable junk and not junk reporting to Microsoft in Outlook on the web:</span></span>
  
```
Set-OwaMailboxPolicy -Identity "<OWAMailboxPolicyName>" -ReportJunkEmailEnabled <$true | $false>
```

<span data-ttu-id="bd746-116">In questo esempio viene disattivata la creazione di report nel criterio cassetta postale di Outlook Web App predefinito:</span><span class="sxs-lookup"><span data-stu-id="bd746-116">This example turns off reporting in the default Outlook web app mailbox policy:</span></span>
  
```
Set-OwaMailboxPolicy -Identity "OwaMailboxPolicy-Default" -ReportJunkEmailEnabled $false
```

<span data-ttu-id="bd746-117">Per informazioni dettagliate sulla sintassi e sui parametri, vedere [Get-OwaMailboxPolicy](http://technet.microsoft.com/library/bdd580d3-8812-4b4a-93e8-c6401b0d2f0f.aspx) e [Set-OwaMailboxPolicy](http://technet.microsoft.com/library/530166f7-ab42-4609-ba73-9b5a39b567be.aspx).</span><span class="sxs-lookup"><span data-stu-id="bd746-117">For detailed syntax and parameter information, see [Get-OwaMailboxPolicy](http://technet.microsoft.com/library/bdd580d3-8812-4b4a-93e8-c6401b0d2f0f.aspx) and [Set-OwaMailboxPolicy](http://technet.microsoft.com/library/530166f7-ab42-4609-ba73-9b5a39b567be.aspx).</span></span>

## <a name="how-do-you-know-this-worked"></a><span data-ttu-id="bd746-118">Come verificare se l'operazione ha avuto esito positivo</span><span class="sxs-lookup"><span data-stu-id="bd746-118">How do you know this worked?</span></span>
<span data-ttu-id="bd746-119"><a name="sectionSection2"> </a></span><span class="sxs-lookup"><span data-stu-id="bd746-119"></span></span>

<span data-ttu-id="bd746-120">Eseguire **Get-OwaMailboxPolicy** per controllare i valori dei parametri e quindi aprire Outlook sul Web per un utente in cui è stato applicato il criterio cassetta postale di Outlook sul Web e verificare che le opzioni per segnalare la posta indesiderata, il phishing e non la posta indesiderata non siano disponibili.</span><span class="sxs-lookup"><span data-stu-id="bd746-120">Run **Get-OWAMailboxPolicy** to check the parameter values, and then open Outlook on the web for an affected user (who has the Outlook on the web mailbox policy applied to them) and verify that the options to report junk, phishing, and not junk are not available.</span></span> <span data-ttu-id="bd746-121">È comunque possibile contrassegnare i messaggi come posta indesiderata, phishing e non indesiderata, ma non sarà possibile segnalarli.</span><span class="sxs-lookup"><span data-stu-id="bd746-121">You'll still be able to mark messages as junk, phishing, and not junk, but you won't be able to report them.</span></span> 
