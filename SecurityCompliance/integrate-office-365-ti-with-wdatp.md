---
title: Integrazione di Office 365 Advanced Threat Protection con Windows Defender Advanced Threat Protection
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
ms.openlocfilehash: 832b9c6bc600366e1ed6b7c6e60442bec8b5002c
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "32254432"
---
# <a name="integrate-office-365-advanced-threat-protection-with-windows-defender-advanced-threat-protection"></a><span data-ttu-id="ea7fd-103">Integrazione di Office 365 Advanced Threat Protection con Windows Defender Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="ea7fd-103">Integrate Office 365 Advanced Threat Protection with Windows Defender Advanced Threat Protection</span></span>

<span data-ttu-id="ea7fd-104">Se si è parte del team di sicurezza dell'organizzazione, è possibile integrare Office 365 Advanced Threat Protection e le funzionalità di analisi e risposta correlate con Windows Defender Advanced Threat Protection.</span><span class="sxs-lookup"><span data-stu-id="ea7fd-104">If you are part of your organization's security team, you can integrate Office 365 Advanced Threat Protection and related investigation and response features with Windows Defender Advanced Threat Protection.</span></span> <span data-ttu-id="ea7fd-105">In questo modo è possibile capire rapidamente se i computer degli utenti sono a rischio quando si esaminano le minacce in Office 365.</span><span class="sxs-lookup"><span data-stu-id="ea7fd-105">This can help you quickly understand if users' machines are at risk when you are investigating threats in Office 365.</span></span> <span data-ttu-id="ea7fd-106">Ad esempio, una volta abilitata l'integrazione, sarà possibile visualizzare un elenco di computer utilizzati dai destinatari di un messaggio di posta elettronica rilevato, nonché il numero di avvisi recenti che tali computer hanno in Windows Defender Advanced Threat Protection.</span><span class="sxs-lookup"><span data-stu-id="ea7fd-106">For example, once integration is enabled, you will be able to see a list of machines that are used by the recipients of a detected email message, as well as how many recent alerts those machines have in Windows Defender Advanced Threat Protection.</span></span>
  
<span data-ttu-id="ea7fd-107">Nell'immagine seguente viene mostrata la scheda **dispositivi** che verrà visualizzata quando è abilitata l'integrazione di Windows Defender Advanced Threat Protection:</span><span class="sxs-lookup"><span data-stu-id="ea7fd-107">The following image shows the **Devices** tab that you'll see when have Windows Defender Advanced Threat Protection integration enabled:</span></span> 
  
![Quando Windows Defender ATP è abilitato, è possibile visualizzare un elenco di computer con avvisi.](media/fec928ea-8f0c-44d7-80b9-a2e0a8cd4e89.PNG)
  
<span data-ttu-id="ea7fd-109">In questo esempio, è possibile vedere che i destinatari del messaggio di posta elettronica dispongono di quattro dispositivi e uno ha un avviso.</span><span class="sxs-lookup"><span data-stu-id="ea7fd-109">In this example, you can see that the recipients of the email message have four devices and one has an alert.</span></span> <span data-ttu-id="ea7fd-110">Se si fa clic sul collegamento di un dispositivo, viene aperta la relativa pagina nel portale Windows Defender Advanced Threat Protection.</span><span class="sxs-lookup"><span data-stu-id="ea7fd-110">Clicking the link for a device opens its page in the Windows Defender Advanced Threat Protection portal.</span></span>
  
## <a name="requirements"></a><span data-ttu-id="ea7fd-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="ea7fd-111">Requirements</span></span>

- <span data-ttu-id="ea7fd-112">L'organizzazione deve disporre di Office 365 Advanced Threat Protection Plan 2 (o Office 365 E5) e Windows Defender ATP.</span><span class="sxs-lookup"><span data-stu-id="ea7fd-112">Your organization must have Office 365 Advanced Threat Protection Plan 2 (or Office 365 E5) and Windows Defender ATP.</span></span>
    
- <span data-ttu-id="ea7fd-113">È necessario essere un amministratore globale di Office 365 o un ruolo di amministratore della sicurezza, ad esempio amministratore della sicurezza, assegnato nel [centro conformità sicurezza &amp; ](https://protection.office.com).</span><span class="sxs-lookup"><span data-stu-id="ea7fd-113">You must be an Office 365 Global Administrator or have a security administrator role (such as Security Administrator) assigned in the [Security &amp; Compliance Center](https://protection.office.com).</span></span> <span data-ttu-id="ea7fd-114">(Vedere [Permissions in the Office &amp; 365 Security Compliance Center](permissions-in-the-security-and-compliance-center.md))</span><span class="sxs-lookup"><span data-stu-id="ea7fd-114">(See [Permissions in the Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md))</span></span>
    
- <span data-ttu-id="ea7fd-115">È necessario avere accesso a Office 365 Threat Explorer nel centro sicurezza & compliance e nel portale Windows Defender Advanced Threat Protection.</span><span class="sxs-lookup"><span data-stu-id="ea7fd-115">You must have access to both Office 365 Threat Explorer in the Security & Compliance Center and the Windows Defender Advanced Threat Protection portal.</span></span>
    
## <a name="to-integrate-office-365-advanced-threat-protection-with-windows-defender-atp"></a><span data-ttu-id="ea7fd-116">Per integrare Office 365 Advanced Threat Protection con Windows Defender ATP</span><span class="sxs-lookup"><span data-stu-id="ea7fd-116">To integrate Office 365 Advanced Threat Protection with Windows Defender ATP</span></span>

<span data-ttu-id="ea7fd-117">Integrazione di Office 365 Advanced Threat Protection con Windows Defender Advanced Threat Protection è configurato utilizzando il Centro sicurezza & compliance e il portale Windows Defender Advanced Threat Protection.</span><span class="sxs-lookup"><span data-stu-id="ea7fd-117">Integrating Office 365 Advanced Threat Protection with Windows Defender Advanced Threat Protection is set up by using both the Security & Compliance Center AND the Windows Defender Advanced Threat Protection portal.</span></span>
  
1. <span data-ttu-id="ea7fd-118">In qualità di amministratore globale di Office 365 o amministratore della sicurezza, [https://protection.office.com](https://protection.office.com) accedere a e accedere con l'account aziendale o dell'Istituto di istruzione per Office 365.</span><span class="sxs-lookup"><span data-stu-id="ea7fd-118">As an Office 365 global administrator or a security administrator, go to [https://protection.office.com](https://protection.office.com) and sign in with your work or school account for Office 365.</span></span> 
    
2. <span data-ttu-id="ea7fd-119">Scegliere \> **Esplora** **gestione minacce** .</span><span class="sxs-lookup"><span data-stu-id="ea7fd-119">Choose **Threat management** \> **Explorer**.</span></span><br><span data-ttu-id="ea7fd-120">![Explorer nel menu Gestione minacce](media/ThreatMgmt-Explorer-nav.png)</span><span class="sxs-lookup"><span data-stu-id="ea7fd-120">![Explorer in Threat Management menu](media/ThreatMgmt-Explorer-nav.png)</span></span><br>
    
3. <span data-ttu-id="ea7fd-121">Nell'angolo in alto a destra dello schermo, scegliere **impostazioni di WDATP**.</span><span class="sxs-lookup"><span data-stu-id="ea7fd-121">In the upper right corner of the screen, choose **WDATP Settings**.</span></span>
    
4. <span data-ttu-id="ea7fd-122">Nella finestra di dialogo connessione ATP di Windows Defender, abilitare la connessione a Windows ATP.</span><span class="sxs-lookup"><span data-stu-id="ea7fd-122">In the Windows Defender ATP connection dialog box, turn on Connect to Windows ATP.</span></span><br>![Connessione ATP Windows Defender](media/Explorer-WDATPConnection-dialog.png)<br>
    
5. <span data-ttu-id="ea7fd-124">Abilitare la connessione in Windows Defender Advanced Threat Protection.</span><span class="sxs-lookup"><span data-stu-id="ea7fd-124">Enable the connection in Windows Defender Advanced Threat Protection.</span></span> <span data-ttu-id="ea7fd-125">Per ulteriori informazioni, vedere [use the Windows Defender Advanced Threat Protection Portal](https://go.microsoft.com/fwlink/?linkid=859690).</span><span class="sxs-lookup"><span data-stu-id="ea7fd-125">See [Use the Windows Defender Advanced Threat Protection portal](https://go.microsoft.com/fwlink/?linkid=859690).</span></span>

  
## <a name="related-topics"></a><span data-ttu-id="ea7fd-126">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="ea7fd-126">Related topics</span></span>

[<span data-ttu-id="ea7fd-127">Indagine e risposta alle minacce di Office 365</span><span class="sxs-lookup"><span data-stu-id="ea7fd-127">Office 365 Threat Investigation and Response</span></span>](office-365-ti.md)
  
[<span data-ttu-id="ea7fd-128">Office 365 Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="ea7fd-128">Office 365 Advanced Threat Protection</span></span>](office-365-atp.md)
  

