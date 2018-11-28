---
title: Integrare Office 365 Threat Intelligence con Windows Defender Advanced Threat Protection
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 3/21/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 414fa693-d7b7-4a1d-a387-ebc3b6a52889
description: Integrare protezione rischio avanzate di Office 365 con Windows Defender avanzate rischio di protezione per visualizzare ulteriori informazioni sulla gestione di rischio.
ms.openlocfilehash: 1198f53c47811d69b93106c413e3d3a09d83e736
ms.sourcegitcommit: 2cf7f5bb282c971d33e00f65d9982a3f14aec74e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/27/2018
ms.locfileid: "26706140"
---
# <a name="integrate-office-365-threat-intelligence-with-windows-defender-advanced-threat-protection"></a><span data-ttu-id="4cf42-103">Integrare Office 365 Threat Intelligence con Windows Defender Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="4cf42-103">Integrate Office 365 Threat Intelligence with Windows Defender Advanced Threat Protection</span></span>

<span data-ttu-id="4cf42-p101">Se si fa parte del team di protezione dell'organizzazione, è possibile integrare Office 365 con Windows Defender avanzate Threat Protection (degli strumenti di analisi). Ciò consente di comprendere rapidamente se computer degli utenti sono a rischio durante l'analisi delle minacce in Office 365. Ad esempio, una volta integrazione è attivata, sarà in grado di visualizzare un elenco dei computer utilizzati dai destinatari di un messaggio di posta elettronica rilevato, nonché il modo in cui numero di avvisi recenti tali apparecchi sono in strumenti di analisi di Windows Defender.</span><span class="sxs-lookup"><span data-stu-id="4cf42-p101">If you are part of your organization's security team, you can integrate Office 365 with Windows Defender Advanced Threat Protection (ATP). This can help you quickly understand if users' machines are at risk when you are investigating threats in Office 365. For example, once integration is enabled, you will be able to see a list of machines that are used by the recipients of a detected email message, as well as how many recent alerts those machines have in Windows Defender ATP.</span></span>
  
<span data-ttu-id="4cf42-107">Nell'immagine seguente è illustrata la scheda **dispositivi** che verrà visualizzato quando sono integrazione degli strumenti di analisi di Windows Defender abilitata:</span><span class="sxs-lookup"><span data-stu-id="4cf42-107">The following image shows the **Devices** tab that you'll see when have Windows Defender ATP integration enabled:</span></span> 
  
![Quando è abilitata degli strumenti di analisi di Windows Defender, è possibile visualizzare un elenco di computer con gli avvisi.](media/fec928ea-8f0c-44d7-80b9-a2e0a8cd4e89.PNG)
  
<span data-ttu-id="4cf42-p102">In questo esempio, è possibile visualizzare che i destinatari del messaggio di posta elettronica sono quattro macchine e uno con un avviso in strumenti di analisi di Windows Defender. Fare clic sul collegamento a un computer apre la pagina automatica in strumenti di analisi di Windows Defender in una nuova scheda.</span><span class="sxs-lookup"><span data-stu-id="4cf42-p102">In this example, you can see that the recipients of the email message have four machines and one has an alert in Windows Defender ATP. Clicking the link to a machine opens the machine page in Windows Defender ATP in a new tab.</span></span>
  
## <a name="requirements"></a><span data-ttu-id="4cf42-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="4cf42-111">Requirements</span></span>

- <span data-ttu-id="4cf42-112">L'organizzazione deve disporre degli strumenti di analisi di Windows Defender e Business Intelligence di Office 365 rischio.</span><span class="sxs-lookup"><span data-stu-id="4cf42-112">Your organization must have Office 365 Threat Intelligence and Windows Defender ATP.</span></span>
    
- <span data-ttu-id="4cf42-p103">È necessario essere un amministratore globale di Office 365 o disporre di un ruolo di amministratore di sicurezza assegnato nella versione di [protezione &amp; centro conformità](https://security.microsoft.com). (Vedere [le autorizzazioni di sicurezza di Office 365 &amp; centro conformità](permissions-in-the-security-and-compliance-center.md))</span><span class="sxs-lookup"><span data-stu-id="4cf42-p103">You must be an Office 365 global administrator or have a security administrator role assigned in the [Security &amp; Compliance Center](https://security.microsoft.com). (See [Permissions in the Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md))</span></span>
    
- <span data-ttu-id="4cf42-115">È necessario avere accesso a Office 365 rischio Intelligence e portale degli strumenti di analisi di Windows Defender.</span><span class="sxs-lookup"><span data-stu-id="4cf42-115">You must have access to both Office 365 Threat Intelligence and the Windows Defender ATP portal.</span></span>
    
## <a name="to-integrate-office-365-threat-intelligence-with-windows-defender-atp"></a><span data-ttu-id="4cf42-116">Per l'integrazione di Business Intelligence di rischio di Office 365 con degli strumenti di analisi di Windows Defender</span><span class="sxs-lookup"><span data-stu-id="4cf42-116">To integrate Office 365 Threat Intelligence with Windows Defender ATP</span></span>

<span data-ttu-id="4cf42-117">Integrazione di Business Intelligence di rischio di Office 365 con degli strumenti di analisi di Windows Defender è configurato in Office 365 e nel portale degli strumenti di analisi di Windows Defender.</span><span class="sxs-lookup"><span data-stu-id="4cf42-117">Integrating Office 365 Threat Intelligence with Windows Defender ATP is set up both in Office 365 and in the Windows Defender ATP portal.</span></span>
  
1. <span data-ttu-id="4cf42-118">Office 365 globale o un amministratore della sicurezza, passare a [https://security.microsoft.com](https://security.microsoft.com) e accedere con l'account di lavoro o della scuola per Office 365.</span><span class="sxs-lookup"><span data-stu-id="4cf42-118">As an Office 365 global or a security administrator, go to [https://security.microsoft.com](https://security.microsoft.com) and sign in with your work or school account for Office 365.</span></span> 
    
2. <span data-ttu-id="4cf42-119">Scegliere **gestione rischio** \> **explorer rischio**.</span><span class="sxs-lookup"><span data-stu-id="4cf42-119">Choose **Threat management** \> **Threat explorer**.</span></span>
    
3. <span data-ttu-id="4cf42-120">**Ulteriori** dal menu, scegliere **Impostazioni WDATP**.</span><span class="sxs-lookup"><span data-stu-id="4cf42-120">On the **More** menu, choose **WDATP Settings**.</span></span>
    
4. <span data-ttu-id="4cf42-121">Selezionare **Connetti a Windows degli strumenti di analisi**.</span><span class="sxs-lookup"><span data-stu-id="4cf42-121">Select **Connect to Windows ATP**.</span></span>
    
<span data-ttu-id="4cf42-p104">Dopo avere modificato le impostazioni di Office 365, è necessario abilitare la connessione tra degli strumenti di analisi di Windows Defender. A tale scopo, vedere [utilizzo del portale di protezione di Windows Defender avanzate rischio](https://go.microsoft.com/fwlink/?linkid=859690).</span><span class="sxs-lookup"><span data-stu-id="4cf42-p104">After you have changed the settings in Office 365, you must enable the connection from Windows Defender ATP. To do that, see [Use the Windows Defender Advanced Threat Protection portal](https://go.microsoft.com/fwlink/?linkid=859690).</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="4cf42-124">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="4cf42-124">Related topics</span></span>

[<span data-ttu-id="4cf42-125">Office 365 Threat Intelligence</span><span class="sxs-lookup"><span data-stu-id="4cf42-125">Office 365 Threat Intelligence</span></span>](office-365-ti.md)
  
[<span data-ttu-id="4cf42-126">Office 365 Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="4cf42-126">Office 365 Advanced Threat Protection</span></span>](office-365-atp.md)
  

