---
title: Integrare Office 365 Threat Intelligence con Windows Defender Advanced Threat Protection
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 01/22/2019
ms.audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 414fa693-d7b7-4a1d-a387-ebc3b6a52889
ms.collection: M365-security-compliance
description: Integrare protezione rischio avanzate di Office 365 con Windows Defender avanzate rischio di protezione per visualizzare ulteriori informazioni sulla gestione di rischio.
ms.openlocfilehash: f8f5f50af10fb668aa67b68604e95e8dd19c9e69
ms.sourcegitcommit: efccf5b4f22d34a9674bc55ebf3d88bc8bda2972
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/14/2019
ms.locfileid: "29995207"
---
# <a name="integrate-office-365-threat-intelligence-with-windows-defender-advanced-threat-protection"></a><span data-ttu-id="2482c-103">Integrare Office 365 Threat Intelligence con Windows Defender Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="2482c-103">Integrate Office 365 Threat Intelligence with Windows Defender Advanced Threat Protection</span></span>

<span data-ttu-id="2482c-p101">Se si fa parte del team di protezione dell'organizzazione, è possibile integrare funzionalità di protezione di Office 365 avanzate rischio e Intelligence rischio con la protezione di Windows Defender avanzate rischio. Ciò consente di comprendere rapidamente se computer degli utenti sono a rischio durante l'analisi delle minacce in Office 365. Ad esempio, una volta integrazione è attivata, sarà in grado di visualizzare un elenco dei computer utilizzati dai destinatari di un messaggio di posta elettronica rilevato, nonché il modo in cui numero di avvisi recenti tali apparecchi dispongano di protezione di Windows Defender avanzate rischio.</span><span class="sxs-lookup"><span data-stu-id="2482c-p101">If you are part of your organization's security team, you can integrate Office 365 Advanced Threat Protection and Threat Intelligence features with Windows Defender Advanced Threat Protection. This can help you quickly understand if users' machines are at risk when you are investigating threats in Office 365. For example, once integration is enabled, you will be able to see a list of machines that are used by the recipients of a detected email message, as well as how many recent alerts those machines have in Windows Defender Advanced Threat Protection.</span></span>
  
<span data-ttu-id="2482c-107">Nell'immagine seguente è illustrata la scheda **dispositivi** che verrà visualizzato quando prevista l'integrazione con la protezione di Windows Defender avanzate rischio abilitato:</span><span class="sxs-lookup"><span data-stu-id="2482c-107">The following image shows the **Devices** tab that you'll see when have Windows Defender Advanced Threat Protection integration enabled:</span></span> 
  
![Quando è abilitata degli strumenti di analisi di Windows Defender, è possibile visualizzare un elenco di computer con gli avvisi.](media/fec928ea-8f0c-44d7-80b9-a2e0a8cd4e89.PNG)
  
<span data-ttu-id="2482c-p102">In questo esempio, è possibile visualizzare che i destinatari del messaggio di posta elettronica dispongano di quattro dispositivi e uno con un avviso. Facendo clic sul collegamento di un dispositivo verrà visualizzata la relativa pagina del portale di protezione di Windows Defender avanzate rischio.</span><span class="sxs-lookup"><span data-stu-id="2482c-p102">In this example, you can see that the recipients of the email message have four devices and one has an alert. Clicking the link for a device opens its page in the Windows Defender Advanced Threat Protection portal.</span></span>
  
## <a name="requirements"></a><span data-ttu-id="2482c-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="2482c-111">Requirements</span></span>

- <span data-ttu-id="2482c-112">L'organizzazione deve disporre degli strumenti di analisi di Windows Defender e Business Intelligence di Office 365 rischio.</span><span class="sxs-lookup"><span data-stu-id="2482c-112">Your organization must have Office 365 Threat Intelligence and Windows Defender ATP.</span></span>
    
- <span data-ttu-id="2482c-p103">È necessario essere un amministratore globale di Office 365 o disporre di un ruolo di amministratore di sicurezza (ad esempio sicurezza amministratore) assegnato nella versione di [protezione &amp; centro conformità](https://protection.office.com). (Vedere [le autorizzazioni di sicurezza di Office 365 &amp; centro conformità](permissions-in-the-security-and-compliance-center.md))</span><span class="sxs-lookup"><span data-stu-id="2482c-p103">You must be an Office 365 Global Administrator or have a security administrator role (such as Security Administrator) assigned in the [Security &amp; Compliance Center](https://protection.office.com). (See [Permissions in the Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md))</span></span>
    
- <span data-ttu-id="2482c-115">È necessario avere accesso a Business Intelligence di Office 365 rischio e il portale di protezione di Windows Defender avanzate rischio.</span><span class="sxs-lookup"><span data-stu-id="2482c-115">You must have access to both Office 365 Threat Intelligence and the Windows Defender Advanced Threat Protection portal.</span></span>
    
## <a name="to-integrate-office-365-threat-intelligence-with-windows-defender-atp"></a><span data-ttu-id="2482c-116">Per l'integrazione di Business Intelligence di rischio di Office 365 con degli strumenti di analisi di Windows Defender</span><span class="sxs-lookup"><span data-stu-id="2482c-116">To integrate Office 365 Threat Intelligence with Windows Defender ATP</span></span>

<span data-ttu-id="2482c-117">Integrazione di Business Intelligence di rischio di Office 365 con la protezione di Windows Defender avanzate rischio è configurato con entrambi i & di sicurezza di Office 365 centro conformità e il portale di protezione di Windows Defender avanzate rischio.</span><span class="sxs-lookup"><span data-stu-id="2482c-117">Integrating Office 365 Threat Intelligence with Windows Defender Advanced Threat Protection is set up by using both the Office 365 Security & Compliance Center AND the Windows Defender Advanced Threat Protection portal.</span></span>
  
1. <span data-ttu-id="2482c-118">Un amministratore della sicurezza o un amministratore globale di Office 365, passare a [https://protection.office.com](https://protection.office.com) e accedere con l'account di lavoro o della scuola per Office 365.</span><span class="sxs-lookup"><span data-stu-id="2482c-118">As an Office 365 global administrator or a security administrator, go to [https://protection.office.com](https://protection.office.com) and sign in with your work or school account for Office 365.</span></span> 
    
2. <span data-ttu-id="2482c-119">Scegliere **gestione rischio** \> **Explorer**.</span><span class="sxs-lookup"><span data-stu-id="2482c-119">Choose **Threat management** \> **Explorer**.</span></span><br><span data-ttu-id="2482c-120">![Explorer menu Threat Management](media/ThreatMgmt-Explorer-nav.png)</span><span class="sxs-lookup"><span data-stu-id="2482c-120">![Explorer in Threat Management menu](media/ThreatMgmt-Explorer-nav.png)</span></span><br>
    
3. <span data-ttu-id="2482c-121">Nell'angolo superiore destro dello schermo, scegliere **Impostazioni WDATP**.</span><span class="sxs-lookup"><span data-stu-id="2482c-121">In the upper right corner of the screen, choose **WDATP Settings**.</span></span>
    
4. <span data-ttu-id="2482c-122">Nella casella degli strumenti di analisi di Windows Defender connessione della finestra attiva connessione a Windows degli strumenti di analisi.</span><span class="sxs-lookup"><span data-stu-id="2482c-122">In the Windows Defender ATP connection dialog box, turn on Connect to Windows ATP.</span></span><br>![Connessione degli strumenti di analisi di Windows Defender](media/Explorer-WDATPConnection-dialog.png)<br>
    
5. <span data-ttu-id="2482c-p104">Abilitare la connessione di protezione di Windows Defender avanzate rischio. Vedere [utilizzo del portale di protezione di Windows Defender avanzate rischio](https://go.microsoft.com/fwlink/?linkid=859690).</span><span class="sxs-lookup"><span data-stu-id="2482c-p104">Enable the connection in Windows Defender Advanced Threat Protection. See [Use the Windows Defender Advanced Threat Protection portal](https://go.microsoft.com/fwlink/?linkid=859690).</span></span>

  
## <a name="related-topics"></a><span data-ttu-id="2482c-126">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="2482c-126">Related topics</span></span>

[<span data-ttu-id="2482c-127">Office 365 Threat Intelligence</span><span class="sxs-lookup"><span data-stu-id="2482c-127">Office 365 Threat Intelligence</span></span>](office-365-ti.md)
  
[<span data-ttu-id="2482c-128">Office 365 Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="2482c-128">Office 365 Advanced Threat Protection</span></span>](office-365-atp.md)
  

