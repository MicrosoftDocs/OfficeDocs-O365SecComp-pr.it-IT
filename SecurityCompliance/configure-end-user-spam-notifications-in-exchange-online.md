---
title: Configurazione di notifiche di posta indesiderata in Exchange Online
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 11/17/2014
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
ms.assetid: bfc91c73-a955-40e1-a95f-ad466624339a
description: È possibile configurare le notifiche di posta indesiderata dell'utente finale per il criterio di filtro da posta indesiderata a livello aziendale predefinito o per i criteri di filtro posta indesiderata personalizzati che vengono applicati ai domini.
ms.openlocfilehash: 4a4c7c6b139fe0f8b0a1f6b69c1b95e321293af5
ms.sourcegitcommit: 22bca85c3c6d946083d3784f72e886c068d49f4a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/06/2018
ms.locfileid: "22027533"
---
# <a name="configure-end-user-spam-notifications-in-exchange-online"></a><span data-ttu-id="9a9b1-103">Configurazione di notifiche di posta indesiderata in Exchange Online</span><span class="sxs-lookup"><span data-stu-id="9a9b1-103">Configure end-user spam notifications in Exchange Online</span></span>

> [!IMPORTANT]
> <span data-ttu-id="9a9b1-p101">In questo argomento è per i clienti di Exchange Online che desidera proteggere le cassette postali ospitate nel cloud. I clienti autonomo di Exchange Online Protection (EOP) che sono protezione cassette postali locali è consigliabile leggere l'argomento seguente invece: [Configura notifiche di posta indesiderata in EOP](configure-end-user-spam-notifications-in-eop.md).</span><span class="sxs-lookup"><span data-stu-id="9a9b1-p101">This topic is for Exchange Online customers who are protecting cloud-hosted mailboxes. Exchange Online Protection (EOP) standalone customers who are protecting on-premises mailboxes should read the following topic instead: [Configure end-user spam notifications in EOP](configure-end-user-spam-notifications-in-eop.md).</span></span> 
  
<span data-ttu-id="9a9b1-p102">È possibile configurare le notifiche di posta indesiderata dell'utente finale per il criterio di filtro da posta indesiderata a livello aziendale predefinito o per i criteri di filtro posta indesiderata personalizzati che vengono applicati ai domini. Abilitazione di messaggi di notifica di posta indesiderata dell'utente finale consente agli utenti finali di gestire autonomamente i propri messaggi nella quarantena della posta indesiderata. Notifiche di posta indesiderata non possono essere utilizzate con i criteri applicati a utenti o gruppi o a un criterio con le eccezioni.</span><span class="sxs-lookup"><span data-stu-id="9a9b1-p102">You can configure end-user spam notifications for the default company-wide spam filter policy or for custom spam filter policies that are applied to domains. Enabling end-user spam notification messages lets your end users self-manage their own spam-quarantined messages. End-user spam notifications cannot be used with policies applied to users or groups, or to a policy with exceptions.</span></span>
  
<span data-ttu-id="9a9b1-p103">Le notifiche di posta indesiderata dell'utente finale contengono un elenco di tutti i messaggi di posta indesiderata messi in quarantena ricevuti dall'utente finale durante un periodo di tempo configurato. È possibile specificare un valore compreso tra 1 e 15 giorni. È inoltre possibile configurare la lingua in cui è scritto il messaggio di notifica.</span><span class="sxs-lookup"><span data-stu-id="9a9b1-p103">End-user spam notifications contain a list of all spam-quarantined messages that the end user has received during a time period that you configure (you can specify a value between 1 and 15 days). You can also configure the language in which the notification message is written.</span></span>
  
<span data-ttu-id="9a9b1-111">Dopo aver ricevuto un messaggio di notifica, gli utenti finali possono fare clic per spostare il messaggio di posta elettronica da posta indesiderata in posta in arrivo o la posta indesiderata di posta elettronica come non indesiderato, nel qual caso il rapporto verrà inviato al Team di analisi della posta indesiderata di Microsoft.</span><span class="sxs-lookup"><span data-stu-id="9a9b1-111">After receiving a notification message, end users can click to move the spam email to their inbox, or report the spam email as Not Junk, in which case it will be sent to the Microsoft Spam Analysis Team.</span></span> 
  
## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="9a9b1-112">Che cosa è necessario sapere prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="9a9b1-112">What do you need to know before you begin?</span></span>

<span data-ttu-id="9a9b1-113">Tempo stimato per il completamento: 2 minuti</span><span class="sxs-lookup"><span data-stu-id="9a9b1-113">Estimated time to complete: 2 minutes</span></span>
  
<span data-ttu-id="9a9b1-p104">È necessario disporre delle autorizzazioni prima che è possibile eseguire queste procedure. Per verificare le autorizzazioni necessarie, vedere la voce "Protezione da posta indesiderata" nell'argomento [Feature Permissions in Exchange Online](http://technet.microsoft.com/library/15073ce1-0917-403b-8839-02a2ebc96e16.aspx) .</span><span class="sxs-lookup"><span data-stu-id="9a9b1-p104">You need to be assigned permissions before you can perform this procedure or procedures. To see what permissions you need, see the "Anti-spam" entry in the [Feature Permissions in Exchange Online](http://technet.microsoft.com/library/15073ce1-0917-403b-8839-02a2ebc96e16.aspx) topic.</span></span> 
  
<span data-ttu-id="9a9b1-116">Per informazioni sui tasti di scelta rapida che è possibile utilizzare con le procedure in questo argomento, vedere **Keyboard shortcuts in Exchange 2013**.</span><span class="sxs-lookup"><span data-stu-id="9a9b1-116">For information about keyboard shortcuts that may apply to the procedures in this topic, see **Keyboard shortcuts in the Exchange admin center**.</span></span>
  
## <a name="use-the-eac-to-configure-end-user-spam-notifications"></a><span data-ttu-id="9a9b1-117">Utilizzo dell'interfaccia di amministrazione di Exchange per la configurazione delle notifiche di posta indesiderata</span><span class="sxs-lookup"><span data-stu-id="9a9b1-117">Use the EAC to configure end-user spam notifications</span></span>

1. <span data-ttu-id="9a9b1-118">In Interfaccia di amministrazione di Exchange, accedere a **Protezione** \> **Filtro posta indesiderata**.</span><span class="sxs-lookup"><span data-stu-id="9a9b1-118">In the Exchange admin center (EAC), navigate to **Protection** \> **Spam filter**.</span></span>
    
2. <span data-ttu-id="9a9b1-119">Selezionare il criterio di filtro posta indesiderata per il quale si desidera abilitare le notifiche di posta indesiderata dell'utente finale (che sono disabilitate per impostazione predefinita).</span><span class="sxs-lookup"><span data-stu-id="9a9b1-119">Select the spam filter policy for which you want to enable end-user spam notifications (they are disabled by default).</span></span>
    
3. <span data-ttu-id="9a9b1-120">Nel riquadro di destra, in cui sono contenute informazioni di riepilogo sul criterio, fare clic sul collegamento **Configura notifiche spam utente finale**.</span><span class="sxs-lookup"><span data-stu-id="9a9b1-120">In the right pane, where the summary information about your policy appears, click the **Configure End-user spam notifications** link.</span></span> 
    
4. <span data-ttu-id="9a9b1-121">Nella finestra di dialogo successiva è possibile configurare le seguenti opzioni:</span><span class="sxs-lookup"><span data-stu-id="9a9b1-121">In the subsequent dialog box, you can configure the following options:</span></span>
    
1. <span data-ttu-id="9a9b1-p105">**Abilita le notifiche di spam all'utente finale** Selezionare questa casella di controllo per abilitare le notifiche di posta indesiderata dell'utente finale per questo criterio. Viceversa, se questo criterio è abilitato, è possibile deselezionare la casella di controllo per disabilitare le notifiche di posta indesiderata dell'utente finale per tale criterio.</span><span class="sxs-lookup"><span data-stu-id="9a9b1-p105">**Enable end-user spam notifications** Select this check box in order to enable end-user spam notifications for this policy. (Conversely, if this policy is enabled, you can clear this check box in order to disable end-user spam notifications for this policy.)</span></span> 
    
2. <span data-ttu-id="9a9b1-p106">**Invia notifiche di spam agli utenti finali ogni (giorni)** Consente di specificare la frequenza di invio delle notifiche di posta indesiderata dell'utente finale. Il valore predefinito è 3 giorni. È possibile specificare un valore compreso tra 1 e 15 giorni. Se, ad esempio, si specifica 7 giorni, la notifica includerà l'elenco di tutti i messaggi che negli ultimi 7 giorni erano diretti all'utente ma che sono stati invece inviati alla quarantena della posta indesiderata.</span><span class="sxs-lookup"><span data-stu-id="9a9b1-p106">**Send end-user spam notifications every (days)** Specify how often to send end-user spam notifications. The default is 3 days. You can specify between 1 and 15 days. If you specify 7 days, for example, the notification will include a list of all messages intended for that user within the past 7 days that were sent to the spam quarantine instead.</span></span> 
    
3. <span data-ttu-id="9a9b1-128">**Lingua delle notifiche** Utilizzando l'elenco a discesa, selezionare la lingua in cui scrivere le notifiche di posta indesiderata dell'utente finale per il criterio in questione.</span><span class="sxs-lookup"><span data-stu-id="9a9b1-128">**Notification language** Using the drop-down list, select the language in which to write end-user spam notifications for this policy.</span></span> 
    
5. <span data-ttu-id="9a9b1-p107">Fare clic su **Salva**. Riepilogo delle impostazioni di criteri filtro posta indesiderata, incluse le impostazioni di notifica di posta indesiderata dell'utente finale, viene visualizzato nel riquadro destro.</span><span class="sxs-lookup"><span data-stu-id="9a9b1-p107">Click **save**. A summary of your spam filter policy settings, including your end-user spam notification settings, appears in the right pane.</span></span>
    
> [!NOTE]
>  <span data-ttu-id="9a9b1-p108">Notifiche di posta indesiderata dell'utente finale saranno applicate solo per i criteri di filtro posta indesiderata sono abilitati. > Notifiche di posta indesiderata vengono inviate solo una volta al giorno. I tempi di consegna della notifica non possono essere garantito per un cliente specifico e non sono configurabili.</span><span class="sxs-lookup"><span data-stu-id="9a9b1-p108">End-user spam notifications will only be functional for spam filter policies that are enabled. >  End-user spam notifications are only sent once per day. The delivery time of the notification cannot be guaranteed for any specific customer and is not configurable.</span></span> 
  
 <span data-ttu-id="9a9b1-p109">**Suggerimento:** Se si desidera testare notifiche di posta indesiderata mediante l'invio di un set limitato di utenti prima di implementarle completamente, creare un criterio di filtro posta indesiderata personalizzati che consente di notifiche di posta indesiderata per i domini in cui risiedono gli utenti. Quindi, in EAC, in **flusso di posta \> regole**, creare una regola di trasporto per bloccare i messaggi da quarantine@messaging.microsoft.com, l'indirizzo di posta elettronica che invia le notifiche, con le eccezioni per gli utenti che si desidera ricevere la notifica. Nell'immagine seguente è riportato un esempio di creazione di un'eccezione di due utenti (SaraD e AlexD) dal dominio Contoso.com:</span><span class="sxs-lookup"><span data-stu-id="9a9b1-p109">**Tip:** If you want to test end-user spam notifications by sending them to a limited set of users before fully implementing them, create a custom spam filter policy that enables end-user spam notifications for the domains in which the users reside. Then, in the EAC, under **Mail flow \> rules**, create a transport rule to block messages from quarantine@messaging.microsoft.com (the email address that sends notifications) with exceptions for the users who you want to receive the notifications. The following image is an example of creating an exception for two users (SaraD and AlexD) from domain Contoso.com:</span></span> 
  
![Regola di trasporto per verificare le notifiche di posta indesiderata dell'utente finale](media/EOP-ESN-testspecificusers.jpg)
  
## <a name="for-more-information"></a><span data-ttu-id="9a9b1-138">Ulteriori informazioni</span><span class="sxs-lookup"><span data-stu-id="9a9b1-138">For more information</span></span>

[<span data-ttu-id="9a9b1-139">Configurare i criteri di filtro della posta indesiderata</span><span class="sxs-lookup"><span data-stu-id="9a9b1-139">Configure your spam filter policies</span></span>](configure-your-spam-filter-policies.md)
  
