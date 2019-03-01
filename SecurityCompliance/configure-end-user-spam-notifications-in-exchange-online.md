---
title: Configurare le notifiche di posta indesiderata dell'utente finale in Exchange Online
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: bfc91c73-a955-40e1-a95f-ad466624339a
ms.collection:
- M365-security-compliance
description: È possibile configurare le notifiche di posta indesiderata dell'utente finale per il criterio di filtro della posta indesiderata a livello di società predefinito o per i criteri di filtro antispam applicati ai domini.
ms.openlocfilehash: e3e5ce044879318dab55f5d08ec2ee0e3379dfb2
ms.sourcegitcommit: 48fa456981b5c52ab8aeace173c8366b9f36723b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/28/2019
ms.locfileid: "30341367"
---
# <a name="configure-end-user-spam-notifications-in-exchange-online"></a><span data-ttu-id="97fa3-103">Configurare le notifiche di posta indesiderata dell'utente finale in Exchange Online</span><span class="sxs-lookup"><span data-stu-id="97fa3-103">Configure end-user spam notifications in Exchange Online</span></span>

> [!IMPORTANT]
> <span data-ttu-id="97fa3-p101">Questo argomento è relativo ai clienti di Exchange Online che proteggono le cassette postali ospitate nel cloud. I clienti autonomi di Exchange Online Protection (EOP) che proteggono le cassette postali locali dovrebbero invece leggere l'argomento seguente: [configurare le notifiche di posta indesiderata dell'utente finale in EOP](configure-end-user-spam-notifications-in-eop.md).</span><span class="sxs-lookup"><span data-stu-id="97fa3-p101">This topic is for Exchange Online customers who are protecting cloud-hosted mailboxes. Exchange Online Protection (EOP) standalone customers who are protecting on-premises mailboxes should read the following topic instead: [Configure end-user spam notifications in EOP](configure-end-user-spam-notifications-in-eop.md).</span></span> 
  
<span data-ttu-id="97fa3-p102">È possibile configurare le notifiche di posta indesiderata dell'utente finale per il criterio di filtro della posta indesiderata a livello di società predefinito o per i criteri di filtro antispam applicati ai domini. L'abilitazione dei messaggi di notifica di posta indesiderata dell'utente finale consente agli utenti finali di gestire autonomamente i messaggi di posta indesiderata. Non è possibile utilizzare le notifiche di posta indesiderata degli utenti finali con i criteri applicati agli utenti o ai gruppi o a un criterio con eccezioni.</span><span class="sxs-lookup"><span data-stu-id="97fa3-p102">You can configure end-user spam notifications for the default company-wide spam filter policy or for custom spam filter policies that are applied to domains. Enabling end-user spam notification messages lets your end users self-manage their own spam-quarantined messages. End-user spam notifications cannot be used with policies applied to users or groups, or to a policy with exceptions.</span></span>
  
<span data-ttu-id="97fa3-p103">Le notifiche di posta indesiderata dell'utente finale contengono un elenco di tutti i messaggi di posta indesiderata messi in quarantena ricevuti dall'utente finale durante un periodo di tempo configurato. È possibile specificare un valore compreso tra 1 e 15 giorni. È inoltre possibile configurare la lingua in cui è scritto il messaggio di notifica.</span><span class="sxs-lookup"><span data-stu-id="97fa3-p103">End-user spam notifications contain a list of all spam-quarantined messages that the end user has received during a time period that you configure (you can specify a value between 1 and 15 days). You can also configure the language in which the notification message is written.</span></span>
  
<span data-ttu-id="97fa3-111">Dopo la ricezione di un messaggio di notifica, gli utenti finali possono scegliere tra le seguenti opzioni:</span><span class="sxs-lookup"><span data-stu-id="97fa3-111">After receiving a notification message, end users can choose from the following options:</span></span>

<span data-ttu-id="97fa3-112">**Visualizzare in anteprima** il messaggio se si desidera visualizzare in anteprima il contenuto o l'intestazione prima di eseguire l'azione.</span><span class="sxs-lookup"><span data-stu-id="97fa3-112">**Preview** the message if you would like to preview the content or header prior to taking action.</span></span>

<span data-ttu-id="97fa3-113">**Scaricare** il messaggio se si desidera esaminare il messaggio e gli allegati (se presenti) del dispositivo prima di eseguire l'azione.</span><span class="sxs-lookup"><span data-stu-id="97fa3-113">**Download** the message if you would like to review the message and attachments (if any) on your device prior to taking action.</span></span>

<span data-ttu-id="97fa3-114">**Rilascia** se il messaggio non è posta indesiderata e si desidera che Office 365 invii il messaggio alla cassetta postale.</span><span class="sxs-lookup"><span data-stu-id="97fa3-114">**Release** if the message isn’t spam and you want Office 365 to send the message to your mailbox.</span></span>

<span data-ttu-id="97fa3-p104">**Release _AMP_ Allow sender** se il messaggio non è posta indesiderata e si desidera che Office 365 aggiunga il mittente all'elenco Mittenti attendibili e destinatari per i messaggi di posta elettronica futuri. Tenere presente che l'amministratore può disporre di altre configurazioni Consenti/blocca a livello di organizzazione che sostituiscono l'elenco dei mittenti attendibili.</span><span class="sxs-lookup"><span data-stu-id="97fa3-p104">**Release & Allow Sender** if the message isn’t spam and you want Office 365 to add the sender to your safe senders and recipients list for future emails. Keep in mind that your admin may have other organization wide allow/block configurations that override your safe sender list.</span></span>

<span data-ttu-id="97fa3-117">**Rilasciare il report di &**, se il messaggio non è spam e si desidera inviare il messaggio alla cassetta postale e segnalarlo a Microsoft per l'analisi.</span><span class="sxs-lookup"><span data-stu-id="97fa3-117">**Release & Report**, if the message isn’t spam and you want to send the message to your mailbox and report it to Microsoft for analysis.</span></span>

<span data-ttu-id="97fa3-118">**Blocca** se si desidera che in Office 365 venga aggiunto il mittente all'elenco dei mittenti bloccati.</span><span class="sxs-lookup"><span data-stu-id="97fa3-118">**Block** if you want Office 365 to add the sender to your blocked senders list.</span></span>
  
## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="97fa3-119">Che cosa è necessario sapere prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="97fa3-119">What do you need to know before you begin?</span></span>

<span data-ttu-id="97fa3-120">Tempo stimato per il completamento: 2 minuti</span><span class="sxs-lookup"><span data-stu-id="97fa3-120">Estimated time to complete: 2 minutes</span></span>
  
<span data-ttu-id="97fa3-p105">Prima di poter eseguire questa procedura o procedure, è necessario disporre delle autorizzazioni assegnate. Per sapere quali autorizzazioni sono necessarie, vedere "protezione da posta indesiderata" nell'argomento [Feature Permissions in Exchange Online](http://technet.microsoft.com/library/15073ce1-0917-403b-8839-02a2ebc96e16.aspx) .</span><span class="sxs-lookup"><span data-stu-id="97fa3-p105">You need to be assigned permissions before you can perform this procedure or procedures. To see what permissions you need, see the "Anti-spam" entry in the [Feature Permissions in Exchange Online](http://technet.microsoft.com/library/15073ce1-0917-403b-8839-02a2ebc96e16.aspx) topic.</span></span> 
  
<span data-ttu-id="97fa3-123">Per informazioni sui tasti di scelta rapida che è possibile utilizzare con le procedure in questo argomento, vedere **Keyboard shortcuts in Exchange 2013**.</span><span class="sxs-lookup"><span data-stu-id="97fa3-123">For information about keyboard shortcuts that may apply to the procedures in this topic, see **Keyboard shortcuts in the Exchange admin center**.</span></span>
  
## <a name="use-the-eac-to-configure-end-user-spam-notifications"></a><span data-ttu-id="97fa3-124">Utilizzo dell'interfaccia di amministrazione di Exchange per la configurazione delle notifiche di posta indesiderata</span><span class="sxs-lookup"><span data-stu-id="97fa3-124">Use the EAC to configure end-user spam notifications</span></span>

1. <span data-ttu-id="97fa3-125">In Interfaccia di amministrazione di Exchange, accedere a **Protezione** \> **Filtro posta indesiderata**.</span><span class="sxs-lookup"><span data-stu-id="97fa3-125">In the Exchange admin center (EAC), navigate to **Protection** \> **Spam filter**.</span></span>
    
2. <span data-ttu-id="97fa3-126">Selezionare il criterio di filtro della posta indesiderata per il quale si desidera abilitare le notifiche di posta indesiderata dell'utente finale (disabilitato per impostazione predefinita).</span><span class="sxs-lookup"><span data-stu-id="97fa3-126">Select the spam filter policy for which you want to enable end-user spam notifications (they are disabled by default).</span></span>
    
3. <span data-ttu-id="97fa3-127">Nel riquadro di destra, in cui sono contenute informazioni di riepilogo sul criterio, fare clic sul collegamento **Configura notifiche spam utente finale**.</span><span class="sxs-lookup"><span data-stu-id="97fa3-127">In the right pane, where the summary information about your policy appears, click the **Configure End-user spam notifications** link.</span></span> 
    
4. <span data-ttu-id="97fa3-128">Nella finestra di dialogo successiva è possibile configurare le seguenti opzioni:</span><span class="sxs-lookup"><span data-stu-id="97fa3-128">In the subsequent dialog box, you can configure the following options:</span></span>
    
1. <span data-ttu-id="97fa3-p106">**Abilita le notifiche di spam all'utente finale** Selezionare questa casella di controllo per abilitare le notifiche di posta indesiderata dell'utente finale per questo criterio. Viceversa, se questo criterio è abilitato, è possibile deselezionare la casella di controllo per disabilitare le notifiche di posta indesiderata dell'utente finale per tale criterio.</span><span class="sxs-lookup"><span data-stu-id="97fa3-p106">**Enable end-user spam notifications** Select this check box in order to enable end-user spam notifications for this policy. (Conversely, if this policy is enabled, you can clear this check box in order to disable end-user spam notifications for this policy.)</span></span> 
    
2. <span data-ttu-id="97fa3-p107">**Invia notifiche di spam agli utenti finali ogni (giorni)** Consente di specificare la frequenza di invio delle notifiche di posta indesiderata dell'utente finale. Il valore predefinito è 3 giorni. È possibile specificare un valore compreso tra 1 e 15 giorni. Se, ad esempio, si specifica 7 giorni, la notifica includerà l'elenco di tutti i messaggi che negli ultimi 7 giorni erano diretti all'utente ma che sono stati invece inviati alla quarantena della posta indesiderata.</span><span class="sxs-lookup"><span data-stu-id="97fa3-p107">**Send end-user spam notifications every (days)** Specify how often to send end-user spam notifications. The default is 3 days. You can specify between 1 and 15 days. If you specify 7 days, for example, the notification will include a list of all messages intended for that user within the past 7 days that were sent to the spam quarantine instead.</span></span> 
    
3. <span data-ttu-id="97fa3-135">**Lingua delle notifiche** Utilizzando l'elenco a discesa, selezionare la lingua in cui scrivere le notifiche di posta indesiderata dell'utente finale per il criterio in questione.</span><span class="sxs-lookup"><span data-stu-id="97fa3-135">**Notification language** Using the drop-down list, select the language in which to write end-user spam notifications for this policy.</span></span> 
    
5. <span data-ttu-id="97fa3-p108">Fare clic su **Salva**. Nel riquadro destro viene visualizzato un riepilogo delle impostazioni dei criteri di filtro della posta indesiderata, incluse le impostazioni di notifica di posta indesiderata dell'utente finale.</span><span class="sxs-lookup"><span data-stu-id="97fa3-p108">Click **save**. A summary of your spam filter policy settings, including your end-user spam notification settings, appears in the right pane.</span></span>
    
> [!NOTE]
>  <span data-ttu-id="97fa3-p109">Le notifiche di posta indesiderata dell'utente finale saranno funzionali solo per i criteri di filtro della posta indesiderata abilitati. le notifiche di posta indesiderata dell'utente finale di > vengono inviate solo una volta al giorno. Il tempo di consegna della notifica non può essere garantito per un cliente specifico e non è configurabile.</span><span class="sxs-lookup"><span data-stu-id="97fa3-p109">End-user spam notifications will only be functional for spam filter policies that are enabled. >  End-user spam notifications are only sent once per day. The delivery time of the notification cannot be guaranteed for any specific customer and is not configurable.</span></span> 
  
 <span data-ttu-id="97fa3-p110">**Suggerimento:** Se si desidera testare le notifiche di posta indesiderata dell'utente finale inviando un gruppo limitato di utenti prima di implementarle completamente, creare un criterio di filtro di posta indesiderata personalizzato che consenta le notifiche di posta indesiderata dell'utente finale per i domini in cui risiedono gli utenti. Quindi, nell'interfaccia di amministrazione di Exchange, in **regole del flusso \> di posta**, creare una regola del flusso di posta (nota anche come regola di trasporto) per bloccare i messaggi da Quarantine@messaging.microsoft.com (l'indirizzo di posta elettronica che invia le notifiche) con le eccezioni per gli utenti che si desidera per ricevere le notifiche. L'immagine seguente è un esempio di creazione di un'eccezione per due utenti (Sarad e AlexD) da Domain Contoso.com:</span><span class="sxs-lookup"><span data-stu-id="97fa3-p110">**Tip:** If you want to test end-user spam notifications by sending them to a limited set of users before fully implementing them, create a custom spam filter policy that enables end-user spam notifications for the domains in which the users reside. Then, in the EAC, under **Mail flow \> rules**, create a mail flow rule (also known as a transport rule) to block messages from quarantine@messaging.microsoft.com (the email address that sends notifications) with exceptions for the users who you want to receive the notifications. The following image is an example of creating an exception for two users (SaraD and AlexD) from domain Contoso.com:</span></span> 
  
![Regola di trasporto per verificare le notifiche di posta indesiderata dell'utente finale](media/EOP-ESN-testspecificusers.jpg)
  
## <a name="for-more-information"></a><span data-ttu-id="97fa3-145">Ulteriori informazioni</span><span class="sxs-lookup"><span data-stu-id="97fa3-145">For more information</span></span>

[<span data-ttu-id="97fa3-146">Configurare i criteri di filtro della posta indesiderata</span><span class="sxs-lookup"><span data-stu-id="97fa3-146">Configure your spam filter policies</span></span>](configure-your-spam-filter-policies.md)
  
