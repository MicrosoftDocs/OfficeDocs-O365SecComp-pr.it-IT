---
title: Integrare Office 365 Threat Intelligence con Windows Defender Advanced Threat Protection
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 01/22/2019
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 414fa693-d7b7-4a1d-a387-ebc3b6a52889
ms.collection:
- M365-security-compliance
description: Integrazione di Office 365 Advanced Threat Protection con Windows Defender Advanced Threat Protection per visualizzare informazioni più dettagliate sulla gestione delle minacce.
ms.openlocfilehash: 892d04152d6029c48a52d37c6235d45a8ba67b81
ms.sourcegitcommit: a80bd8626720fabdf592b84e4424cd3a83d08280
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/23/2019
ms.locfileid: "30222815"
---
# <a name="integrate-office-365-threat-intelligence-with-windows-defender-advanced-threat-protection"></a><span data-ttu-id="fcaee-103">Integrare Office 365 Threat Intelligence con Windows Defender Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="fcaee-103">Integrate Office 365 Threat Intelligence with Windows Defender Advanced Threat Protection</span></span>

<span data-ttu-id="fcaee-p101">Se si è parte del team di sicurezza dell'organizzazione, è possibile integrare le funzionalità di Office 365 Advanced Threat Protection e Threat Intelligence con Windows Defender Advanced Threat Protection. In questo modo è possibile capire rapidamente se i computer degli utenti sono a rischio quando si esaminano le minacce in Office 365. Ad esempio, una volta abilitata l'integrazione, sarà possibile visualizzare un elenco di computer utilizzati dai destinatari di un messaggio di posta elettronica rilevato, nonché il numero di avvisi recenti che tali computer hanno in Windows Defender Advanced Threat Protection.</span><span class="sxs-lookup"><span data-stu-id="fcaee-p101">If you are part of your organization's security team, you can integrate Office 365 Advanced Threat Protection and Threat Intelligence features with Windows Defender Advanced Threat Protection. This can help you quickly understand if users' machines are at risk when you are investigating threats in Office 365. For example, once integration is enabled, you will be able to see a list of machines that are used by the recipients of a detected email message, as well as how many recent alerts those machines have in Windows Defender Advanced Threat Protection.</span></span>
  
<span data-ttu-id="fcaee-107">Nell'immagine seguente viene mostrata la scheda **dispositivi** che verrà visualizzata quando è abilitata l'integrazione di Windows Defender Advanced Threat Protection:</span><span class="sxs-lookup"><span data-stu-id="fcaee-107">The following image shows the **Devices** tab that you'll see when have Windows Defender Advanced Threat Protection integration enabled:</span></span> 
  
![Quando Windows Defender ATP è abilitato, è possibile visualizzare un elenco di computer con avvisi.](media/fec928ea-8f0c-44d7-80b9-a2e0a8cd4e89.PNG)
  
<span data-ttu-id="fcaee-p102">In questo esempio, è possibile vedere che i destinatari del messaggio di posta elettronica dispongono di quattro dispositivi e uno ha un avviso. Se si fa clic sul collegamento di un dispositivo, viene aperta la relativa pagina nel portale Windows Defender Advanced Threat Protection.</span><span class="sxs-lookup"><span data-stu-id="fcaee-p102">In this example, you can see that the recipients of the email message have four devices and one has an alert. Clicking the link for a device opens its page in the Windows Defender Advanced Threat Protection portal.</span></span>
  
## <a name="requirements"></a><span data-ttu-id="fcaee-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="fcaee-111">Requirements</span></span>

- <span data-ttu-id="fcaee-112">L'organizzazione deve disporre di Office 365 Threat Intelligence e Windows Defender ATP.</span><span class="sxs-lookup"><span data-stu-id="fcaee-112">Your organization must have Office 365 Threat Intelligence and Windows Defender ATP.</span></span>
    
- <span data-ttu-id="fcaee-p103">È necessario essere un amministratore globale di Office 365 o un ruolo di amministratore della sicurezza, ad esempio amministratore della sicurezza, assegnato nel [centro conformità sicurezza &amp; ](https://protection.office.com). (Vedere [Permissions in the Office &amp; 365 Security Compliance Center](permissions-in-the-security-and-compliance-center.md))</span><span class="sxs-lookup"><span data-stu-id="fcaee-p103">You must be an Office 365 Global Administrator or have a security administrator role (such as Security Administrator) assigned in the [Security &amp; Compliance Center](https://protection.office.com). (See [Permissions in the Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md))</span></span>
    
- <span data-ttu-id="fcaee-115">È necessario avere accesso sia a Office 365 Threat Intelligence sia al portale Windows Defender Advanced Threat Protection.</span><span class="sxs-lookup"><span data-stu-id="fcaee-115">You must have access to both Office 365 Threat Intelligence and the Windows Defender Advanced Threat Protection portal.</span></span>
    
## <a name="to-integrate-office-365-threat-intelligence-with-windows-defender-atp"></a><span data-ttu-id="fcaee-116">Per integrare Office 365 Threat Intelligence con Windows Defender ATP</span><span class="sxs-lookup"><span data-stu-id="fcaee-116">To integrate Office 365 Threat Intelligence with Windows Defender ATP</span></span>

<span data-ttu-id="fcaee-117">Integrazione di Office 365 Threat Intelligence con Windows Defender Advanced Threat Protection è configurato utilizzando il centro conformità di Office 365 Security & e il portale Windows Defender Advanced Threat Protection.</span><span class="sxs-lookup"><span data-stu-id="fcaee-117">Integrating Office 365 Threat Intelligence with Windows Defender Advanced Threat Protection is set up by using both the Office 365 Security & Compliance Center AND the Windows Defender Advanced Threat Protection portal.</span></span>
  
1. <span data-ttu-id="fcaee-118">In qualità di amministratore globale di Office 365 o amministratore della sicurezza, [https://protection.office.com](https://protection.office.com) accedere a e accedere con l'account aziendale o dell'Istituto di istruzione per Office 365.</span><span class="sxs-lookup"><span data-stu-id="fcaee-118">As an Office 365 global administrator or a security administrator, go to [https://protection.office.com](https://protection.office.com) and sign in with your work or school account for Office 365.</span></span> 
    
2. <span data-ttu-id="fcaee-119">Scegliere \> **Esplora** **gestione minacce** .</span><span class="sxs-lookup"><span data-stu-id="fcaee-119">Choose **Threat management** \> **Explorer**.</span></span><br><span data-ttu-id="fcaee-120">![Explorer nel menu Gestione minacce](media/ThreatMgmt-Explorer-nav.png)</span><span class="sxs-lookup"><span data-stu-id="fcaee-120">![Explorer in Threat Management menu](media/ThreatMgmt-Explorer-nav.png)</span></span><br>
    
3. <span data-ttu-id="fcaee-121">Nell'angolo in alto a destra dello schermo, scegliere **impostazioni di WDATP**.</span><span class="sxs-lookup"><span data-stu-id="fcaee-121">In the upper right corner of the screen, choose **WDATP Settings**.</span></span>
    
4. <span data-ttu-id="fcaee-122">Nella finestra di dialogo connessione ATP di Windows Defender, abilitare la connessione a Windows ATP.</span><span class="sxs-lookup"><span data-stu-id="fcaee-122">In the Windows Defender ATP connection dialog box, turn on Connect to Windows ATP.</span></span><br>![Connessione ATP Windows Defender](media/Explorer-WDATPConnection-dialog.png)<br>
    
5. <span data-ttu-id="fcaee-p104">Abilitare la connessione in Windows Defender Advanced Threat Protection. Per ulteriori informazioni, vedere [use the Windows Defender Advanced Threat Protection Portal](https://go.microsoft.com/fwlink/?linkid=859690).</span><span class="sxs-lookup"><span data-stu-id="fcaee-p104">Enable the connection in Windows Defender Advanced Threat Protection. See [Use the Windows Defender Advanced Threat Protection portal](https://go.microsoft.com/fwlink/?linkid=859690).</span></span>

  
## <a name="related-topics"></a><span data-ttu-id="fcaee-126">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="fcaee-126">Related topics</span></span>

[<span data-ttu-id="fcaee-127">Office 365 Threat Intelligence</span><span class="sxs-lookup"><span data-stu-id="fcaee-127">Office 365 Threat Intelligence</span></span>](office-365-ti.md)
  
[<span data-ttu-id="fcaee-128">Office 365 Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="fcaee-128">Office 365 Advanced Threat Protection</span></span>](office-365-atp.md)
  

