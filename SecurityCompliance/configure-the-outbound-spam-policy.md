---
title: Configurare i criteri di posta indesiderata in uscita
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 11/10/2016
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: a44764e9-a5d2-4c67-8888-e7fb871c17c7
description: Il filtro di protezione da posta indesiderata in uscita è sempre abilitato se si utilizza il servizio per l'invio di messaggi di posta elettronica in uscita, proteggendo così l'organizzazione utilizzando il servizio e i destinatari previsti.
ms.openlocfilehash: b6185cfded28613cb5a512882aefb1a99db158db
ms.sourcegitcommit: e9dca2d6a7838f98bb7eca127fdda2372cda402c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/21/2018
ms.locfileid: "23002414"
---
# <a name="configure-the-outbound-spam-policy"></a><span data-ttu-id="c67a1-103">Configurare i criteri di posta indesiderata in uscita</span><span class="sxs-lookup"><span data-stu-id="c67a1-103">Configure the outbound spam policy</span></span>

<span data-ttu-id="c67a1-p101">Il filtro di protezione da posta indesiderata in uscita è sempre abilitato se si utilizza il servizio per l'invio di messaggi di posta elettronica in uscita, proteggendo così l'organizzazione utilizzando il servizio e i destinatari previsti. Come il filtro della posta in arrivo, quello per la posta indesiderata in uscita è composto da un filtro connessioni e un filtro contenuto, ma diversamente dal primo le sue impostazioni non sono configurabili. Se si determina che un messaggio in uscita è posta indesiderata, tale messaggio viene instradato attraverso il pool di recapito ad alto rischio in modo da ridurre la probabilità che il normale pool IP in uscita venga aggiunto all'elenco di indirizzi bloccati. Se un utente continua a inviare posta indesiderata in uscita tramite il servizio, non potrà più inviare messaggi. Anche se il filtro di protezione da posta indesiderata in uscita non può essere disabilitato o modificato, è possibile configurare diverse impostazioni di posta indesiderata in uscita a livello dell'azienda tramite il criterio della posta indesiderata in uscita predefinito.</span><span class="sxs-lookup"><span data-stu-id="c67a1-p101">Outbound spam filtering is always enabled if you use the service for sending outbound email, thereby protecting organizations using the service and their intended recipients. Similar to inbound filtering, outbound spam filtering is comprised of connection filtering and content filtering, however the outbound filter settings are not configurable. If an outbound message is determined to be spam, it is routed through the higher risk delivery pool, which reduces the probability of the normal outbound-IP pool being added to a block list. If a customer continues to send outbound spam through the service, they will be blocked from sending messages. Although outbound spam filtering cannot be disabled or changed, you can configure several company-wide outbound spam settings via the default outbound spam policy.</span></span> 
  
<span data-ttu-id="c67a1-109">Nel video seguente viene illustrato come configurare il criterio della posta indesiderata in uscita:</span><span class="sxs-lookup"><span data-stu-id="c67a1-109">The following video shows how to configure the outbound spam policy:</span></span>
  
> [!VIDEO https://www.microsoft.com/videoplayer/embed/1f20d655-0d3d-4141-9cae-e57f5a6cffe8?autoplay=false]
  
## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="c67a1-110">Che cosa è necessario sapere prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="c67a1-110">What do you need to know before you begin?</span></span>
<span data-ttu-id="c67a1-111"><a name="sectionSection0"> </a></span><span class="sxs-lookup"><span data-stu-id="c67a1-111"></span></span>

<span data-ttu-id="c67a1-112">Tempo stimato per il completamento: 5 minuti</span><span class="sxs-lookup"><span data-stu-id="c67a1-112">Estimated time to complete: 5 minutes</span></span>
  
<span data-ttu-id="c67a1-p102">È necessario disporre delle autorizzazioni prima che è possibile eseguire queste procedure. Per visualizzare le autorizzazioni necessarie, vedere "protezione da posta indesiderata nell'argomento [Feature Permissions in Exchange Online](http://technet.microsoft.com/library/15073ce1-0917-403b-8839-02a2ebc96e16.aspx) .</span><span class="sxs-lookup"><span data-stu-id="c67a1-p102">You need to be assigned permissions before you can perform this procedure or procedures. To see what permissions you need, see the "Anti-spam entry in the [Feature Permissions in Exchange Online](http://technet.microsoft.com/library/15073ce1-0917-403b-8839-02a2ebc96e16.aspx) topic.</span></span> 
  
<span data-ttu-id="c67a1-115">Per informazioni sui tasti di scelta rapida che è possibile utilizzare con le procedure in questo argomento, vedere **Tasti di scelta rapida nell'interfaccia di amministrazione di Exchange**.</span><span class="sxs-lookup"><span data-stu-id="c67a1-115">For information about keyboard shortcuts that may apply to the procedures in this topic, see **Keyboard shortcuts in the Exchange admin center**.</span></span>
  
<span data-ttu-id="c67a1-p103">La procedura seguente può anche essere eseguita tramite remote PowerShell. Utilizzare il cmdlet [Get-HostedOutboundSpamFilterPolicy](http://technet.microsoft.com/library/8f15c83c-c10a-4d9d-b135-35321430bdc2.aspx) per controllare le impostazioni e [Set-HostedOutboundSpamFilterPolicy](http://technet.microsoft.com/library/665d1b04-d4b5-4a0e-811a-4e37096ccbfd.aspx) per modificare le impostazioni di criteri di posta indesiderata in uscita. Per informazioni su come utilizzare Windows PowerShell per la connessione a Exchange Online Protection, vedere [Connect to Exchange Online Protection PowerShell](https://go.microsoft.com/fwlink/p/?linkid=627290). Per informazioni su come utilizzare Windows PowerShell per la connessione a Exchange Online, vedere [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554).</span><span class="sxs-lookup"><span data-stu-id="c67a1-p103">The following procedure can also be performed via remote PowerShell. Use the [Get-HostedOutboundSpamFilterPolicy](http://technet.microsoft.com/library/8f15c83c-c10a-4d9d-b135-35321430bdc2.aspx) cmdlet to review your settings, and the [Set-HostedOutboundSpamFilterPolicy](http://technet.microsoft.com/library/665d1b04-d4b5-4a0e-811a-4e37096ccbfd.aspx) to edit your outbound spam policy settings. To learn how to use Windows PowerShell to connect to Exchange Online Protection, see [Connect to Exchange Online Protection PowerShell](https://go.microsoft.com/fwlink/p/?linkid=627290). To learn how to use Windows PowerShell to connect to Exchange Online, see [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554).</span></span>
  
## <a name="use-the-eac-to-edit-the-default-outbound-spam-policy"></a><span data-ttu-id="c67a1-120">Utilizzo di EAC per modificare il criterio della posta indesiderata in uscita predefinito</span><span class="sxs-lookup"><span data-stu-id="c67a1-120">Use the EAC to edit the default outbound spam policy</span></span>
<span data-ttu-id="c67a1-121"><a name="sectionSection1"> </a></span><span class="sxs-lookup"><span data-stu-id="c67a1-121"></span></span>

<span data-ttu-id="c67a1-122">Utilizzare la procedura seguente per modificare il criterio della posta indesiderata in uscita predefinito:</span><span class="sxs-lookup"><span data-stu-id="c67a1-122">Use the following procedure to edit the default outbound spam policy:</span></span>
  
### <a name="to-configure-the-default-outbound-spam-policy"></a><span data-ttu-id="c67a1-123">Per configurare il criterio della posta indesiderata in uscita predefinito</span><span class="sxs-lookup"><span data-stu-id="c67a1-123">To configure the default outbound spam policy</span></span>

1. <span data-ttu-id="c67a1-124">Nell'interfaccia di amministrazione di Exchange (EAC), accedere a **Protezione**\> **Posta indesiderata in uscita** e fare doppio clic sul criterio predefinito.</span><span class="sxs-lookup"><span data-stu-id="c67a1-124">In the Exchange admin center (EAC), navigate to **Protection** \> **Outbound spam**, and then double-click the default policy.</span></span>
    
2. <span data-ttu-id="c67a1-125">Selezionare l'opzione di menu **Preferenze posta indesiderata in uscita**.</span><span class="sxs-lookup"><span data-stu-id="c67a1-125">Select the **Outbound spam preferences** menu option.</span></span> 
    
3. <span data-ttu-id="c67a1-126">Selezionare le seguenti caselle di controllo appartenenti ai messaggi in uscita e specificare l'indirizzo o gli indirizzi di posta elettronica associati nella casella di input correlata (che possono essere liste di distribuzione se risolvono come destinazioni SMTP valide):</span><span class="sxs-lookup"><span data-stu-id="c67a1-126">Select the following check boxes pertaining to outbound messages, and then specify an associated email address or addresses in the accompanying input box (these can be distribution lists if they resolve as valid SMTP destinations):</span></span>
    
1. <span data-ttu-id="c67a1-p104">**Inviare una copia dei messaggi di posta elettronica in uscita sospetti ai seguenti indirizzi di posta elettronica**. Questi sono messaggi contrassegnati come posta indesiderata dal filtro (a prescindere dal livello di sicurezza della protezione contro la posta indesiderata). Non vengono rifiutati dal filtro ma instradati tramite il pool di recapito ad alto rischio. Separare più indirizzi con un carattere di due punti (:). Tenere presente che i destinatari specificati riceveranno i messaggi con l'indirizzo nel campo della copia per conoscenza nascosta (Ccn), mentre i campi Da e A contengono il destinatario e il mittente originale.</span><span class="sxs-lookup"><span data-stu-id="c67a1-p104">**Send a copy of all suspicious outbound email messages to the following email address or addresses**. These are messages that are marked as spam by the filter (regardless of the SCL rating). They are not rejected by the filter but are routed through the higher risk delivery pool. Separate multiple addresses with a semicolon. Note that the recipients specified will receive the messages as a Blind carbon copy (Bcc) address (the From and To fields are the original sender and recipient).</span></span>
    
2. <span data-ttu-id="c67a1-p105">**Inviare una notifica al seguente indirizzo di posta elettronica quando a un mittente viene impedito l'invio di posta indesiderata**. Separare più indirizzi con un carattere di due punti (:).</span><span class="sxs-lookup"><span data-stu-id="c67a1-p105">**Send a notification to the following email address when a sender is blocked sending outbound spam**. Separate multiple addresses with a semicolon.</span></span>
    
    <span data-ttu-id="c67a1-p106">Quando una grande quantità di posta indesiderata viene creato da un determinato utente, l'utente è disabilitato di inviare messaggi di posta elettronica. L'amministratore di dominio, che viene specificato l'utilizzo di questa impostazione, informa l'utente che vengono bloccati i messaggi in uscita per l'utente. Per visualizzare l'aspetto di questa notifica, vedere [esempio notifica quando un mittente viene bloccato l'invio di posta indesiderata in uscita](sample-notification-when-a-sender-is-blocked-sending-outbound-spam.md). Per informazioni sulla Guida riabilitata, vedere [rimozione di un utente, un dominio o indirizzo IP da un elenco di blocco dopo l'invio di posta elettronica da posta indesiderata](http://technet.microsoft.com/library/712cfcc1-31e8-4e51-8561-b64258a8f1e5.aspx).</span><span class="sxs-lookup"><span data-stu-id="c67a1-p106">When a significant amount of spam is originating from a particular user, the user is disabled from sending email messages. The administrator for the domain, who is specified using this setting, will be informed that outbound messages are blocked for this user. To see what this notification looks like, see [Sample notification when a sender is blocked sending outbound spam](sample-notification-when-a-sender-is-blocked-sending-outbound-spam.md). For information about getting re-enabled, see [Removing a user, domain, or IP address from a block list after sending spam email](http://technet.microsoft.com/library/712cfcc1-31e8-4e51-8561-b64258a8f1e5.aspx).</span></span>
    
4. <span data-ttu-id="c67a1-p107">Fare clic su **salva**. Nel riquadro destro viene visualizzato un riepilogo delle impostazioni dei criteri predefiniti.</span><span class="sxs-lookup"><span data-stu-id="c67a1-p107">Click **save**. A summary of your default policy settings appears in the right pane.</span></span>
    
## <a name="for-more-information"></a><span data-ttu-id="c67a1-140">Ulteriori informazioni</span><span class="sxs-lookup"><span data-stu-id="c67a1-140">For more information</span></span>
<span data-ttu-id="c67a1-141"><a name="sectionSection2"> </a></span><span class="sxs-lookup"><span data-stu-id="c67a1-141"></span></span>

[<span data-ttu-id="c67a1-142">Pool di recapito ad alto rischio per i messaggi in uscita</span><span class="sxs-lookup"><span data-stu-id="c67a1-142">High-risk delivery pool for outbound messages</span></span>](high-risk-delivery-pool-for-outbound-messages.md)
  
[<span data-ttu-id="c67a1-143">Domande frequenti sulla protezione anti-spam</span><span class="sxs-lookup"><span data-stu-id="c67a1-143">Anti-spam protection FAQ</span></span>](anti-spam-protection-faq.md)
  

