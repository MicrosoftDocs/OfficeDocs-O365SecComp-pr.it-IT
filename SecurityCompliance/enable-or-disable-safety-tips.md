---
title: Abilitare o disabilitare i suggerimenti per la sicurezza in Office 365
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 12/05/2018
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: f09668bd-fe1a-4c01-89e3-e88c370e66c7
description: Viene descritto come abilitare e disabilitare i suggerimenti sulla sicurezza in messaggi di posta elettronica gli amministratori di Office 365 ed EOP.
ms.openlocfilehash: 8e5d8bf1d2f831b5d74ca3accd8b434519bfeaab
ms.sourcegitcommit: 204fb0269b5c10b63941055824e863d77e3e9b02
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/06/2018
ms.locfileid: "27180856"
---
# <a name="enable-or-disable-safety-tips-in-office-365"></a><span data-ttu-id="491ca-103">Abilitare o disabilitare i suggerimenti per la sicurezza in Office 365</span><span class="sxs-lookup"><span data-stu-id="491ca-103">Enable or disable safety tips in Office 365</span></span>

<span data-ttu-id="491ca-p101">Exchange Online Protection (EOP) aggiunge o timbri, una sicurezza suggerimento per i messaggi di posta elettronica viene recapitato. Questi suggerimenti sulla sicurezza specificare i destinatari con un modo rapido e visual per determinare se un messaggio da una cassaforte verifica mittente, se il messaggio è stato contrassegnato come posta indesiderata da Office 365, se il messaggio contiene un elemento potenzialmente dannoso, ad esempio il phishing o se sono immagini esterne stati bloccati. Office 365 ed EOP autonomo gli amministratori possono modificare un'impostazione dei criteri di posta indesiderata per attivare o disattivare i suggerimenti di sicurezza non vengono visualizzate nella posta elettronica in Outlook e altri client di posta elettronica desktop.</span><span class="sxs-lookup"><span data-stu-id="491ca-p101">Exchange Online Protection (EOP) adds, or stamps, a safety tip to email messages that it delivers. These safety tips provide recipients with a quick, visual way to determine if a message is from a safe, verified sender, if the message has been marked as spam by Office 365, if the message contains something suspicious such as a phishing scam, or if external images have been blocked. Office 365 and EOP-standalone admins can edit a spam policy setting to enable or disable safety tips from being displayed in email in Outlook and other desktop email clients.</span></span> 
  
<span data-ttu-id="491ca-p102">Office 365 consente suggerimenti sulla sicurezza per impostazione predefinita per l'organizzazione ed è consigliabile lasciare loro abilitato per contro gli attacchi di posta indesiderata e phishing. È possibile disabilitare i suggerimenti sulla sicurezza per Outlook sul web.</span><span class="sxs-lookup"><span data-stu-id="491ca-p102">Office 365 enables safety tips by default for your organization and we recommend that you leave them enabled to help combat spam and phishing attacks. You can't disable safety tips for Outlook on the web.</span></span>
  
<span data-ttu-id="491ca-109">Per visualizzare esempi e per conoscere le informazioni visualizzate in suggerimenti sulla sicurezza, vedere [suggerimenti per la sicurezza nei messaggi di posta elettronica in Office 365.](safety-tips-in-office-365.md)</span><span class="sxs-lookup"><span data-stu-id="491ca-109">To see examples and to learn about the information displayed in safety tips, see [Safety tips in email messages in Office 365.](safety-tips-in-office-365.md)</span></span>
  
<span data-ttu-id="491ca-110">Contenuto dell'argomento:</span><span class="sxs-lookup"><span data-stu-id="491ca-110">In this topic:</span></span>
  
- [<span data-ttu-id="491ca-111">Per attivare o disattivare i suggerimenti di sicurezza utilizzando la protezione di Office 365 &amp; centro conformità</span><span class="sxs-lookup"><span data-stu-id="491ca-111">To enable or disable safety tips by using the Office 365 Security &amp; Compliance Center</span></span>](enable-or-disable-safety-tips.md#SandCCsafetytip)
    
- [<span data-ttu-id="491ca-112">Per attivare o disattivare i suggerimenti di sicurezza tramite PowerShell</span><span class="sxs-lookup"><span data-stu-id="491ca-112">To enable or disable safety tips by using PowerShell</span></span>](enable-or-disable-safety-tips.md#pshellsafetytip)
    
## <a name="to-enable-or-disable-safety-tips-by-using-the-office-365-security-amp-compliance-center"></a><span data-ttu-id="491ca-113">Per attivare o disattivare i suggerimenti di sicurezza utilizzando la protezione di Office 365 &amp; centro conformità</span><span class="sxs-lookup"><span data-stu-id="491ca-113">To enable or disable safety tips by using the Office 365 Security &amp; Compliance Center</span></span>
<span data-ttu-id="491ca-114"><a name="SandCCsafetytip"> </a></span><span class="sxs-lookup"><span data-stu-id="491ca-114"></span></span>

1. <span data-ttu-id="491ca-115">Passare a [https://protection.office.com](https://protection.office.com).</span><span class="sxs-lookup"><span data-stu-id="491ca-115">Go to [https://protection.office.com](https://protection.office.com).</span></span>
    
2. <span data-ttu-id="491ca-116">Accedere a Office 365 con l'account aziendale o dell'istituto di istruzione.</span><span class="sxs-lookup"><span data-stu-id="491ca-116">Sign in to Office 365 with your work or school account.</span></span>
    
3. <span data-ttu-id="491ca-117">Scegliere **Threat Management** \> **criteri**.</span><span class="sxs-lookup"><span data-stu-id="491ca-117">Choose **Threat Management** \> **Policy**.</span></span> 
    
4. <span data-ttu-id="491ca-118">Nella pagina **criteri** , selezionare **protezione da posta indesiderata**.</span><span class="sxs-lookup"><span data-stu-id="491ca-118">On the **Policy** page, choose **Anti-Spam**.</span></span>
    
    ![Schermata che mostra come ottenere la pagina Impostazioni di protezione da posta indesiderata in sicurezza &amp; centro conformità.](media/b8eb2ee3-2eb1-4ea2-b138-f6d7fb2e23de.png)
  
5. <span data-ttu-id="491ca-120">Nella pagina **impostazioni di protezione da posta indesiderata** fare clic sulla scheda **personalizzato** .</span><span class="sxs-lookup"><span data-stu-id="491ca-120">On the **Anti-spam settings** page choose the **Custom** tab.</span></span> 
    
    ![Schermata che mostra la posizione della tabulazione personalizzata nella pagina Impostazioni di protezione da posta indesiderata in sicurezza &amp; centro conformità.](media/1d688d23-e6f3-4de5-84a7-e8ce31786193.png)
  
6. <span data-ttu-id="491ca-p103">Se necessario, scegliere l'opzione **impostazioni personalizzate** per attivare le impostazioni personalizzate. Se l'opzione impostazioni personalizzate è impostato su **Off**, non sarà in grado di modificare i criteri di filtro posta indesiderata.</span><span class="sxs-lookup"><span data-stu-id="491ca-p103">If necessary, choose the **Custom settings** switch to turn on custom settings. If the custom settings switch is set to **Off**, you won't be able to modify spam filter policies.</span></span>
    
    ![Schermata che mostra le impostazioni dei criteri disattivate filtro posta indesiderata personalizzato.](media/94f900ad-b556-4a31-a3ac-acfcd72e71b8.png)
  
7. <span data-ttu-id="491ca-p104">Espandere il criterio della posta indesiderata che si desidera modificare e quindi fare clic su **Modifica criterio**. Ad esempio, fare clic sulla freccia in giù accanto a **posta indesiderata predefiniti filtrare i criteri**. In alternativa, se si desidera, è possibile creare un nuovo criterio facendo clic su **Aggiungi un criterio**.</span><span class="sxs-lookup"><span data-stu-id="491ca-p104">Expand the spam policy you want to modify and then choose **Edit policy**. For example, choose the down arrow next to **Default spam filter policy**. Or, if you want, you can create a new policy by choosing **Add a policy**.</span></span>
    
8. <span data-ttu-id="491ca-128">Espandere azioni per **la posta indesiderata e blocco** .</span><span class="sxs-lookup"><span data-stu-id="491ca-128">Expand **Spam and bulk** actions.</span></span> 
    
9. <span data-ttu-id="491ca-p105">Per abilitare suggerimenti sulla sicurezza, in **Suggerimenti sulla sicurezza**, selezionare la casella di controllo **su** . Per disattivare suggerimenti sulla sicurezza, deselezionare la casella di controllo **su** .</span><span class="sxs-lookup"><span data-stu-id="491ca-p105">To enable safety tips, under **Safety Tips**, check the **On** checkbox. To disable safety tips, clear the **On** checkbox.</span></span> 
    
10. <span data-ttu-id="491ca-131">Scegliere **Save**.</span><span class="sxs-lookup"><span data-stu-id="491ca-131">Choose **Save**.</span></span>
    
## <a name="to-enable-or-disable-safety-tips-by-using-powershell"></a><span data-ttu-id="491ca-132">Per attivare o disattivare i suggerimenti di sicurezza tramite PowerShell</span><span class="sxs-lookup"><span data-stu-id="491ca-132">To enable or disable safety tips by using PowerShell</span></span>
<span data-ttu-id="491ca-133"><a name="pshellsafetytip"> </a></span><span class="sxs-lookup"><span data-stu-id="491ca-133"></span></span>

<span data-ttu-id="491ca-p106">Gli amministratori possono utilizzare Exchange Online PowerShell per abilitare o disabilitare i suggerimenti sulla sicurezza. Utilizzare il cmdlet Set-HostedContentFilterPolicy per attivare o disattivare i suggerimenti di sicurezza in un criterio di filtro posta indesiderata.</span><span class="sxs-lookup"><span data-stu-id="491ca-p106">Admins can use Exchange Online PowerShell to enable or disable safety tips. Use the Set-HostedContentFilterPolicy cmdlet to enable or disable safety tips in a spam filter policy.</span></span>
  
1. <span data-ttu-id="491ca-p107">Connessione a Exchange Online PowerShell. Per informazioni, vedere [Connect to Exchange Online PowerShell](http://go.microsoft.com/fwlink/p/?LinkId=396554).</span><span class="sxs-lookup"><span data-stu-id="491ca-p107">Connect to Exchange Online PowerShell. For information, see [Connect to Exchange Online PowerShell](http://go.microsoft.com/fwlink/p/?LinkId=396554).</span></span>
    
2. <span data-ttu-id="491ca-138">Eseguire il cmdlet Set-HostedContentFilterPolicy per attivare o disattivare i suggerimenti di sicurezza:</span><span class="sxs-lookup"><span data-stu-id="491ca-138">Run the Set-HostedContentFilterPolicy cmdlet to enable or disable safety tips:</span></span>
    
  ```
  Set-HostedContentFilterPolicy -Identity "policy name " -InlineSafetyTipsEnabled <$true|$false>
  ```

<span data-ttu-id="491ca-139">Dove:</span><span class="sxs-lookup"><span data-stu-id="491ca-139">Where:</span></span>
    
  -  <span data-ttu-id="491ca-140">*nome del criterio* è il nome del criterio che si desidera modificare, ad esempio **predefinita**.</span><span class="sxs-lookup"><span data-stu-id="491ca-140">*policy name*  is the name of the policy you want to modify, for example **default**.</span></span>
    
  -  <span data-ttu-id="491ca-141">`$true`Abilita suggerimenti sulla sicurezza per il criterio di filtro posta indesiderata.</span><span class="sxs-lookup"><span data-stu-id="491ca-141">`$true` enables safety tips for the spam filter policy.</span></span> 
    
  -  <span data-ttu-id="491ca-142">`$false`Consente di disabilitare i suggerimenti sulla sicurezza per il criterio di filtro posta indesiderata.</span><span class="sxs-lookup"><span data-stu-id="491ca-142">`$false` disables safety tips for the spam filter policy.</span></span> 
    
    <span data-ttu-id="491ca-143">Ad esempio, per disattivare suggerimenti sulla sicurezza per il criterio di filtro posta indesiderata predefinito, eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="491ca-143">For example, to disable safety tips for the default spam filter policy, run the following command:</span></span>
    
  ```
  PS C:\> Set-HostedContentFilterPolicy -Identity "default" -InlineSafetyTipsEnabled $false
  ```

<span data-ttu-id="491ca-144">Per ulteriori informazioni su questo cmdlet, vedere [Set-HostedContentFilterPolicy](https://technet.microsoft.com/library/jj200781.aspx).</span><span class="sxs-lookup"><span data-stu-id="491ca-144">For more information about this cmdlet, see [Set-HostedContentFilterPolicy](https://technet.microsoft.com/library/jj200781.aspx).</span></span>
    
## <a name="still-need-help"></a><span data-ttu-id="491ca-145">Serve ulteriore assistenza?</span><span class="sxs-lookup"><span data-stu-id="491ca-145">Still need help?</span></span>
<span data-ttu-id="491ca-146"><a name="pshellsafetytip"> </a></span><span class="sxs-lookup"><span data-stu-id="491ca-146"></span></span>

<span data-ttu-id="491ca-147">Se si disabilitato suggerimenti sulla sicurezza, ma vengono visualizzati comunque nei messaggi di posta elettronica, verificare queste operazioni:</span><span class="sxs-lookup"><span data-stu-id="491ca-147">If you disabled safety tips but are still seeing them in your email messages, check these things:</span></span>
  
- <span data-ttu-id="491ca-p108">È possibile disabilitare i suggerimenti sulla sicurezza per Outlook sul web. Provare a visualizzazione alla stessa posta elettronica in un altro client, ad esempio Outlook.</span><span class="sxs-lookup"><span data-stu-id="491ca-p108">You can't disable safety tips for Outlook on the web. Try viewing the same email in another client, such as Outlook.</span></span>
    
- <span data-ttu-id="491ca-p109">Suggerimenti sulla sicurezza presenti per impostazione predefinita per ogni uno che utilizza EOP, include tutti gli utenti con Office 365. Per disattivare i suggerimenti di sicurezza siano visualizzati nel messaggio di posta elettronica, è necessario disattivarli utilizzando un criterio di filtro posta indesiderata, come descritto in questo argomento. Dopo aver configurato il criterio, verificare che sia abilitato. Per informazioni sull'attivazione di criteri di filtro da posta indesiderata, vedere [configurazione dei criteri di filtro posta indesiderata](https://technet.microsoft.com/library/jj200684.aspx).</span><span class="sxs-lookup"><span data-stu-id="491ca-p109">Safety tips are on by default for every one who uses EOP, this includes everyone who has Office 365. In order to disable safety tips from showing up in email, you must disable them by using a spam filter policy as described in this topic. Once you've set up the policy, ensure that it is enabled. For information on enabling spam filter policies, see [Configure your spam filter policies](https://technet.microsoft.com/library/jj200684.aspx).</span></span>
    
<span data-ttu-id="491ca-154">Per ulteriori informazioni su come protezione dalla posta indesiderata e phishing come, vedere [Office 365 posta Anti-Spam Protection](anti-spam-protection.md).</span><span class="sxs-lookup"><span data-stu-id="491ca-154">For more ways to combat spam and phishing, see [Office 365 Email Anti-Spam Protection](anti-spam-protection.md).</span></span>
  

