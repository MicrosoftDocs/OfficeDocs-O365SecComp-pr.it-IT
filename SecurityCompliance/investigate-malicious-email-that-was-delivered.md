---
title: Trovare e analizzare dannoso posta elettronica che è stato recapitato (Business Intelligence rischio di Office 365)
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 8/6/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 8f54cd33-4af7-4d1b-b800-68f8818e5b2a
description: Informazioni su come utilizzare Intelligence minaccia per trovare e provare a utilizzare e-mail dannoso.
ms.openlocfilehash: 9d63bd69e11bca4bc76fa6d6d00a429ed1aac508
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/27/2018
ms.locfileid: "22530633"
---
# <a name="find-and-investigate-malicious-email-that-was-delivered-office-365-threat-intelligence"></a><span data-ttu-id="00e4f-103">Trovare e analizzare dannoso posta elettronica che è stato recapitato (Business Intelligence rischio di Office 365)</span><span class="sxs-lookup"><span data-stu-id="00e4f-103">Find and investigate malicious email that was delivered (Office 365 Threat Intelligence)</span></span>

<span data-ttu-id="00e4f-p101">[Business Intelligence di Office 365 rischio](office-365-ti.md) consente di analizzare le attività che inserire gli utenti a rischio ed eseguire un'azione per proteggere l'organizzazione. Ad esempio, se si fa parte del team di protezione dell'organizzazione, è possibile trovare e analizzare i messaggi di posta elettronica sospetti che sono stati recapitati agli utenti. È possibile eseguire questo tramite [Esplora rischio](get-started-with-ti.md#threat-explorer).</span><span class="sxs-lookup"><span data-stu-id="00e4f-p101">[Office 365 Threat Intelligence](office-365-ti.md) enables you to investigate activities that put your users at risk and take action to protect your organization. For example, if you are part of your organization's security team, you can find and investigate suspicious email messages that were delivered to your users. You can do this by using [Threat Explorer](get-started-with-ti.md#threat-explorer).</span></span>
  
> [!NOTE]
> <span data-ttu-id="00e4f-p102">Business Intelligence di Office 365 rischio è disponibile in Office 365 Enterprise E5. Se l'organizzazione utilizza un'altra sottoscrizione Office 365 Enterprise, Business Intelligence di Office 365 rischio può essere acquistato come componente aggiuntivo. (Come amministratore globale, nell'interfaccia di amministrazione di Office 365 scegliere **fatturazione** \> **Aggiungi sottoscrizioni**.) Per ulteriori informazioni, vedere [Office 365 Platform Service Description: protezione di Office 365 &amp; centro conformità](https://technet.microsoft.com/en-us/library/dn933793.aspx) e [acquistare o modificare un componente aggiuntivo per Office 365 per aziende](https://support.office.com/article/4e7b57d6-b93b-457d-aecd-0ea58bff07a6).</span><span class="sxs-lookup"><span data-stu-id="00e4f-p102">Office 365 Threat Intelligence is available in Office 365 Enterprise E5. If your organization is using another Office 365 Enterprise subscription, Office 365 Threat Intelligence can be purchased as an add-on. (As a global administrator, in the Office 365 admin center, choose **Billing** \> **Add subscriptions**.) For more information, see [Office 365 Platform Service Description: Office 365 Security &amp; Compliance Center](https://technet.microsoft.com/en-us/library/dn933793.aspx) and [Buy or edit an add-on for Office 365 for business](https://support.office.com/article/4e7b57d6-b93b-457d-aecd-0ea58bff07a6).</span></span> 
  
## <a name="before-you-begin"></a><span data-ttu-id="00e4f-110">Prima di iniziare...</span><span class="sxs-lookup"><span data-stu-id="00e4f-110">Before you begin...</span></span>

<span data-ttu-id="00e4f-111">Verificare che vengano soddisfatti i seguenti requisiti:</span><span class="sxs-lookup"><span data-stu-id="00e4f-111">Make sure that the following requirements are met:</span></span>
  
- <span data-ttu-id="00e4f-112">L'organizzazione dispone di [Business Intelligence di Office 365 rischio](office-365-ti.md) e [assegnare licenze agli utenti di Office 365 per aziende](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span><span class="sxs-lookup"><span data-stu-id="00e4f-112">Your organization has [Office 365 Threat Intelligence](office-365-ti.md) and [Assign licenses to users in Office 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span></span>
    
- <span data-ttu-id="00e4f-113">[Registrazione di controllo di Office 365](turn-audit-log-search-on-or-off.md) è attivata per la propria organizzazione.</span><span class="sxs-lookup"><span data-stu-id="00e4f-113">[Office 365 audit logging](turn-audit-log-search-on-or-off.md) is turned on for your organization.</span></span> 
    
- <span data-ttu-id="00e4f-p103">L'organizzazione dispone di criteri definiti per la protezione da posta indesiderata, anti-malware, anti-phishing e così via. Vedere [management in Office 365 protezione delle minacce &amp; centro conformità](threat-management.md).</span><span class="sxs-lookup"><span data-stu-id="00e4f-p103">Your organization has policies defined for anti-spam, anti-malware, anti-phishing, and so on. See [Threat management in the Office 365 Security &amp; Compliance Center](threat-management.md).</span></span>
    
- <span data-ttu-id="00e4f-p104">Essere un amministratore globale di Office 365 o si dispone di amministratore della sicurezza o il ruolo di ricerca ed eliminazione assegnato nella protezione &amp; centro conformità. Vedere [le autorizzazioni di sicurezza di Office 365 &amp; centro conformità](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="00e4f-p104">You are an Office 365 global administrator, or you have either the Security Administrator or the Search and Purge role assigned in the Security &amp; Compliance Center. See [Permissions in the Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    
## <a name="dealing-with-suspicious-emails"></a><span data-ttu-id="00e4f-118">Gestione di messaggi di posta elettronica sospetti</span><span class="sxs-lookup"><span data-stu-id="00e4f-118">Dealing with suspicious emails</span></span>

<span data-ttu-id="00e4f-p105">Malintenzionati potrebbe essere l'invio dei messaggi a utenti di prova e per attività di phishing le proprie credenziali e accedere ai segreti aziendali! Per evitare questo problema, è consigliabile utilizzare i servizi di protezione di rischio offerti da Office 365, inclusi Exchange Online Protection e protezione da minacce avanzate. Tuttavia, vi sono alcuni quando un utente malintenzionato inviare posta elettronica per gli utenti che contiene un URL e solo in seguito apportare tale punto URL al contenuto dannoso (malware e così via). In alternativa, è possibile realizzare troppo avanzata che un utente nell'organizzazione è stato danneggiato e mentre l'utente è stata danneggiata, un utente malintenzionato utilizzato tale account per l'invio di posta elettronica ad altri utenti all'interno della società. Come parte di pulizia entrambi i casi, è possibile rimuovere i messaggi di posta elettronica dalla posta in arrivo utente. In situazioni di questo tipo, è possibile utilizzare Explorer minaccia per trovare e rimuovere i messaggi di posta elettronica!</span><span class="sxs-lookup"><span data-stu-id="00e4f-p105">Malicious attackers may be sending mail to your users to try and phish their credentials and gain access to your corporate secrets! In order to prevent this, you should use the threat protection services offered by Office 365, including Exchange Online Protection and Advanced Threat Protection. However, there are times when an attacker could send mail to your users containing a URL and only later on make that URL point to malicious content (malware, etc.). Alternatively, you may realize too late that a user in your organization has been compromised, and while that user was compromised, an attacker used that account to send email to other users in your company. As part of cleaning up both of these scenarios, you may want to remove email messages from user inboxes. In situations like these, you can leverage Threat Explorer to find and remove those email messages!</span></span>
  
## <a name="find-and-delete-suspicious-email-that-was-delivered"></a><span data-ttu-id="00e4f-125">Cercare ed eliminare messaggi sospetti è stato recapitato</span><span class="sxs-lookup"><span data-stu-id="00e4f-125">Find and delete suspicious email that was delivered</span></span>

> [!TIP]
> <span data-ttu-id="00e4f-p106">[Soluzioni di rischio](get-started-with-ti.md#threat-explorer) (anche noto come Explorer), è un referente potente che può avere diversi scopi, ad esempio ricerca e l'eliminazione dei messaggi, che identifica l'indirizzo IP del mittente messaggio di posta elettronica dannoso o avvio di un evento imprevisto per un'analisi più approfondita. La procedura seguente viene illustrato l'utilizzo di soluzioni per trovare ed eliminare dannoso posta elettronica dalle cassette postali di destinatari.</span><span class="sxs-lookup"><span data-stu-id="00e4f-p106">[Threat Explorer](get-started-with-ti.md#threat-explorer) (also referred to as Explorer), is a powerful report that can serve multiple purposes, such as finding and deleting messages, identifying the IP address of a malicious email sender, or starting an incident for further investigation. The following procedure focuses on using Explorer to find and delete malicious email from recipients mailboxes.</span></span> 
  
1. <span data-ttu-id="00e4f-p107">Accedere a [https://protection.office.com](https://protection.office.com) e accedere utilizzando l'account di lavoro o della scuola per Office 365. Verrà visualizzata la sicurezza &amp; centro conformità.</span><span class="sxs-lookup"><span data-stu-id="00e4f-p107">Go to [https://protection.office.com](https://protection.office.com) and sign in using your work or school account for Office 365. This takes you to the Security &amp; Compliance Center.</span></span> 
    
2. <span data-ttu-id="00e4f-130">Nel riquadro di spostamento sinistro, scegliere **gestione rischio** \> **Explorer**.</span><span class="sxs-lookup"><span data-stu-id="00e4f-130">In the left navigation, choose **Threat management** \> **Explorer**.</span></span>
    
3. <span data-ttu-id="00e4f-131">Nel menu Visualizza, scegliere **tutta la posta elettronica**.</span><span class="sxs-lookup"><span data-stu-id="00e4f-131">In the View menu, choose **All email**.</span></span>
    
    ![Utilizzare il menu Visualizza di scegliere tra report contenuto e di posta elettronica](media/d39013ff-93b6-42f6-bee5-628895c251c2.png)
  
4. <span data-ttu-id="00e4f-133">Osservare le etichette vengono visualizzati nel rapporto, ad esempio **recapitati**, **sconosciuto**o **recapitato alla posta indesiderata**.</span><span class="sxs-lookup"><span data-stu-id="00e4f-133">Notice the labels that appear in the report, such as **Delivered**, **Unknown**, or **Delivered to junk**.</span></span>
    
    ![Soluzioni di rischio la visualizzazione di dati per tutta la posta elettronica](media/208826ed-a85e-446f-b276-b5fdc312fbcb.png)
  
    <span data-ttu-id="00e4f-135">(A seconda delle azioni intraprese nei messaggi di posta elettronica per l'organizzazione, è possibile vedere etichette aggiuntive, ad esempio **bloccato** o **è stata sostituita**).</span><span class="sxs-lookup"><span data-stu-id="00e4f-135">(Depending on the actions that were taken on email messages for your organization, you might see additional labels, such as **Blocked** or **Replaced**.)</span></span>
    
5. <span data-ttu-id="00e4f-136">Nel rapporto, scegliere **recapitati** per visualizzare solo i messaggi di posta elettronica fine posta in arrivo degli utenti.</span><span class="sxs-lookup"><span data-stu-id="00e4f-136">In the report, choose **Delivered** to view only emails that ended up in users' inboxes.</span></span> 
    
    ![Fare clic su "Recapitato alla posta indesiderata" consente di rimuovere tali dati dalla visualizzazione](media/e6fb2e47-461e-4f6f-8c65-c331bd858758.png)
  
6. <span data-ttu-id="00e4f-138">Sotto il grafico, esaminare l'elenco di **posta elettronica** di sotto del grafico.</span><span class="sxs-lookup"><span data-stu-id="00e4f-138">Below the chart, review the **Email** list below the chart.</span></span> 
    
    ![Sotto il grafico, visualizzare un elenco di messaggi di posta elettronica che sono stati rilevati](media/dfb60590-1236-499d-97da-86c68621e2bc.png)
  
7. <span data-ttu-id="00e4f-p108">Nell'elenco, selezionare una voce per visualizzare ulteriori dettagli su tale messaggio di posta elettronica. Ad esempio, è possibile fare clic su riga dell'oggetto per visualizzare informazioni su mittente, i destinatari, gli allegati e altri messaggi di posta elettronica simile.</span><span class="sxs-lookup"><span data-stu-id="00e4f-p108">In the list, choose an item to view more details about that email message. For example, you can click the subject line to view information about the sender, recipients, attachments, and other similar email messages.</span></span>
    
    ![È possibile visualizzare ulteriori informazioni su un elemento, inclusi i dettagli e degli allegati](media/5a5707c3-d62a-4610-ae7b-900fff8708b2.png)
  
8. <span data-ttu-id="00e4f-143">Dopo la visualizzazione delle informazioni sui messaggi di posta elettronica, selezionare uno o più elementi nell'elenco per attivare **+ Azioni**.</span><span class="sxs-lookup"><span data-stu-id="00e4f-143">After viewing information about email messages, select one or more items in the list to activate **+ Actions**.</span></span>
    
9. <span data-ttu-id="00e4f-p109">Utilizzare l'elenco **+ Azioni** per applicare un'azione, ad esempio **Sposta di eliminazione** elementi. Verranno eliminati i messaggi selezionati dalle cassette postali dei destinatari.</span><span class="sxs-lookup"><span data-stu-id="00e4f-p109">Use the **+ Actions** list to apply an action, such as **Move to deleted** items. This will delete the selected messages from the recipients' mailboxes.</span></span> 
    
    ![Quando si selezionano una o più messaggi di posta elettronica, è possibile scegliere tra diverse azioni disponibili](media/ef12e10c-60a7-4f66-8f76-68d77ae26de1.png)
  
## <a name="related-topics"></a><span data-ttu-id="00e4f-147">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="00e4f-147">Related topics</span></span>

[<span data-ttu-id="00e4f-148">Office 365 Threat Intelligence</span><span class="sxs-lookup"><span data-stu-id="00e4f-148">Office 365 Threat Intelligence</span></span>](office-365-ti.md)
  
[<span data-ttu-id="00e4f-149">Protezione contro le minacce in Office 365</span><span class="sxs-lookup"><span data-stu-id="00e4f-149">Protect against threats in Office 365</span></span>](protect-against-threats.md)
  
[<span data-ttu-id="00e4f-150">Visualizzare i report per la protezione rischio avanzate di Office 365</span><span class="sxs-lookup"><span data-stu-id="00e4f-150">View reports for Office 365 Advanced Threat Protection</span></span>](view-reports-for-atp.md)
  
