---
title: Disattivare la posta indesiderata in Outlook sul web reporting
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 10/9/2015
ms.audience: ITPro
ms.topic: article
ms.service: o365-administration
ms.custom: TN2DMC
localization_priority: Normal
ms.assetid: 8d57fe9e-57b8-4884-9317-80b380804b4a
description: L'amministratore di Office 365, è possibile disattivare la possibilità per gli utenti per la posta elettronica report come posta indesiderata.
ms.openlocfilehash: 8ee5ff87408b80c443e4cf950ce49f624096becb
ms.sourcegitcommit: c31424cafbf1953f2864d7e2ceb95b329a694edb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/29/2018
ms.locfileid: "23272041"
---
# <a name="turn-off-junk-email-reporting-in-outlook-on-the-web"></a><span data-ttu-id="aad10-103">Disattivare la posta indesiderata in Outlook sul web reporting</span><span class="sxs-lookup"><span data-stu-id="aad10-103">Turn off junk email reporting in Outlook on the web</span></span>

<span data-ttu-id="aad10-p101">È possibile inviare posta indesiderata e phishing messaggi di posta non indesiderata a Microsoft per l'analisi tramite Outlook sulla posta indesiderata web reporting opzioni, come descritto in [posta indesiderata di Report e i tentativi di phishing in Outlook sul web ](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md). Se non si desidera utilizzare queste opzioni, gli amministratori possono essere disattivati mediante il cmdlet [Set-OwaMailboxPolicy](http://technet.microsoft.com/library/530166f7-ab42-4609-ba73-9b5a39b567be.aspx) .</span><span class="sxs-lookup"><span data-stu-id="aad10-p101">You can send junk, phishing, and not junk messages to Microsoft for analysis using the Outlook on the web junk email reporting options, as described in [Report junk email and phishing scams in Outlook on the web ](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md). If you don't want to use these options,admins can turn them off via the [Set-OwaMailboxPolicy](http://technet.microsoft.com/library/530166f7-ab42-4609-ba73-9b5a39b567be.aspx) cmdlet.</span></span> 
  
## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="aad10-106">Che cosa è necessario sapere prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="aad10-106">What do you need to know before you begin?</span></span>
<span data-ttu-id="aad10-107"><a name="sectionSection0"> </a></span><span class="sxs-lookup"><span data-stu-id="aad10-107"></span></span>

- <span data-ttu-id="aad10-108">Tempo stimato per il completamento: 5 minuti</span><span class="sxs-lookup"><span data-stu-id="aad10-108">Estimated time to complete: 5 minutes</span></span>
    
- <span data-ttu-id="aad10-p102">È necessario disporre delle autorizzazioni prima che è possibile eseguire queste procedure. Per verificare le autorizzazioni necessarie, vedere la voce "Criteri cassetta postale di Outlook Web App" nell'argomento [autorizzazioni di Outlook Web App](http://technet.microsoft.com/library/57eca42a-5a7f-4c65-89f0-7a84f2dbea19.aspx#OutlookWebApp) .</span><span class="sxs-lookup"><span data-stu-id="aad10-p102">You need to be assigned permissions before you can perform this procedure or procedures. To see what permissions you need, see the "Outlook Web App mailbox policies" entry in the [Outlook Web App permissions](http://technet.microsoft.com/library/57eca42a-5a7f-4c65-89f0-7a84f2dbea19.aspx#OutlookWebApp) topic.</span></span> 
    
- <span data-ttu-id="aad10-111">Prima di eseguire i cmdlet necessari per disattivare la segnalazione della posta indesiderata, potrebbe essere utile esaminare le informazioni di riferimento negli argomenti [Get-OwaMailboxPolicy](http://technet.microsoft.com/library/bdd580d3-8812-4b4a-93e8-c6401b0d2f0f.aspx) e [Set-OwaMailboxPolicy](http://technet.microsoft.com/library/530166f7-ab42-4609-ba73-9b5a39b567be.aspx) .</span><span class="sxs-lookup"><span data-stu-id="aad10-111">Before you run the cmdlets required to turn off junk email reporting, it might be helpful to review the reference information in the [Get-OwaMailboxPolicy](http://technet.microsoft.com/library/bdd580d3-8812-4b4a-93e8-c6401b0d2f0f.aspx) and [Set-OwaMailboxPolicy](http://technet.microsoft.com/library/530166f7-ab42-4609-ba73-9b5a39b567be.aspx) topics.</span></span> 
    
## <a name="turn-off-junk-phishing-and-not-junk-reporting-to-microsoft"></a><span data-ttu-id="aad10-112">Disattivare la posta indesiderato, phishing, posta indesiderata e non segnalazione a Microsoft</span><span class="sxs-lookup"><span data-stu-id="aad10-112">Turn off junk, phishing, and not junk reporting to Microsoft</span></span>
<span data-ttu-id="aad10-113"><a name="sectionSection1"> </a></span><span class="sxs-lookup"><span data-stu-id="aad10-113"></span></span>

<span data-ttu-id="aad10-114">Innanzitutto, eseguire il seguente cmdlet per ottenere le directory virtuali per le quali si desidera disattivare la segnalazione:</span><span class="sxs-lookup"><span data-stu-id="aad10-114">First, run the following cmdlet to get the virtual directories for which you want to turn off reporting:</span></span>
  
```
Get-OwaMailboxPolicy -Identity <parameter>
```

<span data-ttu-id="aad10-115">Successivamente, eseguire il seguente cmdlet per disattivare la segnalazione della posta indesiderata e non in Microsoft:</span><span class="sxs-lookup"><span data-stu-id="aad10-115">Next, run the following cmdlet to turn off junk and not junk reporting to Microsoft:</span></span>
  
```
Set-OwaMailboxPolicy -Identity <parameter> -ReportJunkEmailEnabled $false
```

<span data-ttu-id="aad10-116">Ad esempio, il seguente cmdlet consente di disattivare la segnalazione per la directory virtuale Contoso\owa:</span><span class="sxs-lookup"><span data-stu-id="aad10-116">For example, the following cmdlet turns off reporting for virtual directory Contoso\owa:</span></span>
  
```
Set-OwaMailboxPolicy -Identity Default -ReportJunkEmailEnabled $false
```

## <a name="how-do-you-know-this-worked"></a><span data-ttu-id="aad10-117">Come verificare se l'operazione ha avuto esito positivo</span><span class="sxs-lookup"><span data-stu-id="aad10-117">How do you know this worked?</span></span>
<span data-ttu-id="aad10-118"><a name="sectionSection2"> </a></span><span class="sxs-lookup"><span data-stu-id="aad10-118"></span></span>

<span data-ttu-id="aad10-p103">Eseguire Get-OWAMailboxPolicy per i valori dei parametri di controllo e quindi accedere a Outlook sul web e verificare che le opzioni per segnalare posta indesiderata, phishing, posta indesiderata e non si è disponibili. Sarà comunque possibile contrassegnare i messaggi di posta indesiderata, phishing, posta indesiderata e non, ma non sarà in grado di segnalarli.</span><span class="sxs-lookup"><span data-stu-id="aad10-p103">Run Get-OWAMailboxPolicy to check the parameter values, and then access Outlook on the web and verify that the options to report junk, phishing, and not junk are not available. You'll still be able to mark messages as junk, phishing, and not junk, but you won't be able to report them.</span></span> 
  

