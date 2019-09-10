---
title: Configurare le notifiche sui criteri di posta indesiderata in uscita in Office 365
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 11/10/2016
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: a44764e9-a5d2-4c67-8888-e7fb871c17c7
ms.collection:
- M365-security-compliance
description: Gli amministratori possono ottenere informazioni su come modificare le impostazioni di notifica per i rilevamenti di posta indesiderata in uscita in Office 365.
ms.openlocfilehash: c48b6cd634417a00040fb5479313782b44f6aa8d
ms.sourcegitcommit: 81b3bff27bc60235a38004c5b0297ac454331b25
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/10/2019
ms.locfileid: "36822516"
---
# <a name="configure-outbound-spam-policy-notifications-in-office-365"></a><span data-ttu-id="85016-103">Configurare le notifiche sui criteri di posta indesiderata in uscita in Office 365</span><span class="sxs-lookup"><span data-stu-id="85016-103">Configure outbound spam policy notifications in Office 365</span></span>

<span data-ttu-id="85016-104">Il filtro di protezione da posta indesiderata in uscita è sempre abilitato se si utilizza il servizio per l'invio di messaggi di posta elettronica in uscita, proteggendo così l'organizzazione utilizzando il servizio e i destinatari previsti.</span><span class="sxs-lookup"><span data-stu-id="85016-104">Outbound spam filtering is always enabled if you use the service for sending outbound email, thereby protecting organizations using the service and their intended recipients.</span></span> <span data-ttu-id="85016-105">Come il filtro della posta in arrivo, quello per la posta indesiderata in uscita è composto da un filtro connessioni e un filtro contenuto, ma diversamente dal primo le sue impostazioni non sono configurabili.</span><span class="sxs-lookup"><span data-stu-id="85016-105">Similar to inbound filtering, outbound spam filtering is comprised of connection filtering and content filtering, however the outbound filter settings are not configurable.</span></span> <span data-ttu-id="85016-106">Se si determina che un messaggio in uscita è posta indesiderata, tale messaggio viene instradato attraverso il pool di recapito ad alto rischio in modo da ridurre la probabilità che il normale pool IP in uscita venga aggiunto all'elenco di indirizzi bloccati.</span><span class="sxs-lookup"><span data-stu-id="85016-106">If an outbound message is determined to be spam, it is routed through the higher risk delivery pool, which reduces the probability of the normal outbound-IP pool being added to a block list.</span></span> <span data-ttu-id="85016-107">Se un utente continua a inviare posta indesiderata in uscita tramite il servizio, non potrà più inviare messaggi.</span><span class="sxs-lookup"><span data-stu-id="85016-107">If a customer continues to send outbound spam through the service, they will be blocked from sending messages.</span></span>

<span data-ttu-id="85016-108">Sebbene non sia possibile disabilitare o modificare il filtro posta indesiderata in uscita, è possibile configurare le seguenti impostazioni di notifica di posta indesiderata in uscita:</span><span class="sxs-lookup"><span data-stu-id="85016-108">Although you can't disable or change outbound spam filtering, you can configure the following outbound spam notification settings:</span></span>

- <span data-ttu-id="85016-109">**Inviare copie dei messaggi sospetti**: i messaggi vengono contrassegnati come posta indesiderata (indipendentemente dal livello di protezione SCL) e non vengono rifiutati dal filtro, ma vengono instradati attraverso il pool di recapito ad alto rischio.</span><span class="sxs-lookup"><span data-stu-id="85016-109">**Send copies of suspicious messages**: These messages are marked as spam (regardless of the SCL rating) and are not rejected by the filter, but are routed through the higher risk delivery pool.</span></span> <span data-ttu-id="85016-110">È possibile utilizzare l'interfaccia di amministrazione di Exchange (EAC) o i \*\* \*cmdlet-HostedOutboundSpamFilterPolicy\*\* in PowerShell di Exchange Online o Exchange Online Protection PowerShell per specificare i destinatari di addizione per questi messaggi rilevati.</span><span class="sxs-lookup"><span data-stu-id="85016-110">You can use the Exchange admin center (EAC) or the **\*-HostedOutboundSpamFilterPolicy** cmdlets in Exchange Online PowerShell or Exchange Online Protection PowerShell to specify addition recipients for these detected messages.</span></span> <span data-ttu-id="85016-111">Si noti che i destinatari vengono aggiunti come destinatari **Ccn** (i campi **da** e **a** sono il mittente e il destinatario originali).</span><span class="sxs-lookup"><span data-stu-id="85016-111">Note that the recipients are added as **Bcc** recipients (the **From** and **To** fields are the original sender and recipient).</span></span>

- <span data-ttu-id="85016-112">**Inviare notifiche quando un mittente è bloccato**: quando una quantità significativa di posta indesiderata viene inviata da un determinato utente, l'utente è disabilitato dall'invio di messaggi di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="85016-112">**Send notifications when a sender is blocked**: When a significant amount of spam is coming from a particular user, the user is disabled from sending email messages.</span></span> <span data-ttu-id="85016-113">Gli amministratori sono informati per impostazione predefinita, ma è possibile utilizzare l'utente con restrizioni per l'invio dei [criteri di avviso](alert-policies.md) **tramite posta elettronica** nel centro sicurezza & conformità di Office 365 per configurare i destinatari di notifica aggiuntivi.</span><span class="sxs-lookup"><span data-stu-id="85016-113">Admins are notified by default, but you can use the **User restricted from sending email** [alert policy](alert-policies.md) in the Office 365 Security & Compliance Center to configure additional notification recipients.</span></span>

  <span data-ttu-id="85016-114">Per vedere come è fatta la notifica, vedere [Notifica di esempio quando a un mittente viene impedito di inviare posta indesiderata in uscita.](sample-notification-when-a-sender-is-blocked-sending-outbound-spam.md).</span><span class="sxs-lookup"><span data-stu-id="85016-114">To see what this notification looks like, see [Sample notification when a sender is blocked sending outbound spam](sample-notification-when-a-sender-is-blocked-sending-outbound-spam.md).</span></span> <span data-ttu-id="85016-115">Per informazioni su come ottenere riattivati, vedere [rimozione di un utente, dominio o indirizzo IP da un elenco di blocco dopo l'invio di posta indesiderata](http://technet.microsoft.com/library/712cfcc1-31e8-4e51-8561-b64258a8f1e5.aspx).</span><span class="sxs-lookup"><span data-stu-id="85016-115">For information about getting re-enabled, see [Removing a user, domain, or IP address from a block list after sending spam email](http://technet.microsoft.com/library/712cfcc1-31e8-4e51-8561-b64258a8f1e5.aspx).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="85016-116">Che cosa è necessario sapere prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="85016-116">What do you need to know before you begin?</span></span>

- <span data-ttu-id="85016-117">Tempo stimato per il completamento: 5 minuti</span><span class="sxs-lookup"><span data-stu-id="85016-117">Estimated time to complete: 5 minutes</span></span>

- <span data-ttu-id="85016-118">Per aprire il Centro sicurezza e conformità, vedere [Accedere al Centro sicurezza e conformità di Office 365](go-to-the-securitycompliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="85016-118">To open the Security & Compliance Center, see [Go to the Office 365 Security & Compliance Center](go-to-the-securitycompliance-center.md).</span></span>

- <span data-ttu-id="85016-119">Per aprire EAC, vedere interfaccia di amministrazione di Exchange [in Exchange Online](https://docs.microsoft.com/Exchange/exchange-admin-center) o interfaccia [di amministrazione di Exchange in Exchange Online Protection](exchange-admin-center-in-exchange-online-protection-eop.md).</span><span class="sxs-lookup"><span data-stu-id="85016-119">To open the EAC, see [Exchange admin center in Exchange Online](https://docs.microsoft.com/Exchange/exchange-admin-center) or [Exchange admin center in Exchange Online Protection](exchange-admin-center-in-exchange-online-protection-eop.md).</span></span>

- <span data-ttu-id="85016-120">Per aprire Exchange Online PowerShell, vedere [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="85016-120">To open Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="85016-121">Per aprire Exchange Online Protection PowerShell, vedere [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="85016-121">To open Exchange Online Protection PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="85016-122">Per poter eseguire questa procedura, è necessario che l'account disponga delle autorizzazioni assegnate.</span><span class="sxs-lookup"><span data-stu-id="85016-122">Your account needs to be assigned permissions before you can perform this procedure.</span></span> <span data-ttu-id="85016-123">Per sapere quali autorizzazioni sono necessarie, vedere "gestire gli avvisi" in [autorizzazioni nel centro sicurezza & conformità di Office 365](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="85016-123">To see what permissions you need, see the "Manage Alerts" role entry in [Permissions in the Office 365 Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

## <a name="use-the-eac-to-configure-additional-recipients-for-outbound-spam-messages"></a><span data-ttu-id="85016-124">Configurazione di ulteriori destinatari per i messaggi di posta indesiderata in uscita tramite EAC</span><span class="sxs-lookup"><span data-stu-id="85016-124">Use the EAC to configure additional recipients for outbound spam messages</span></span>

1. <span data-ttu-id="85016-125">Nell'interfaccia di amministrazione di Exchange, andare a **protezione** \> **posta indesiderata in uscita**.</span><span class="sxs-lookup"><span data-stu-id="85016-125">In the EAC, go to **Protection** \> **Outbound spam**.</span></span>

2. <span data-ttu-id="85016-126">Selezionare il criterio denominato **default**, quindi fare clic su **modifica** ![icona](media/ITPro-EAC-EditIcon.png)modifica.</span><span class="sxs-lookup"><span data-stu-id="85016-126">Select the policy named **Default**, and then click **Edit** ![Edit icon](media/ITPro-EAC-EditIcon.png).</span></span>

3. <span data-ttu-id="85016-127">Nella pagina delle proprietà che si apre, verificare che sia selezionata la scheda **Preferenze di posta indesiderata in uscita** e quindi configurare l'impostazione seguente:</span><span class="sxs-lookup"><span data-stu-id="85016-127">In the properties page that opens, verify that the **Outbound spam preferences** tab is selected, and then configure the following setting:</span></span>

   <span data-ttu-id="85016-128">**Inviare una copia di tutti i messaggi di posta elettronica in uscita sospetti all'indirizzo o agli indirizzi di posta elettronica seguenti**: selezionare la casella di controllo e immettere gli indirizzi di posta elettronica di uno o più amministratori che devono essere aggiunti al campo **Ccn** dei messaggi rilevati.</span><span class="sxs-lookup"><span data-stu-id="85016-128">**Send a copy of all suspicious outbound email messages to the following email address or addresses**: Select the check box and enter the email addresses of one or more administrators who should be added to the **Bcc** field of detected messages.</span></span> <span data-ttu-id="85016-129">Separare più indirizzi di posta elettronica con un punto e virgola (;).</span><span class="sxs-lookup"><span data-stu-id="85016-129">Separate multiple email addresses with a semicolon ( ; ).</span></span>

   <span data-ttu-id="85016-130">Al termine, scegliere **Salva**.</span><span class="sxs-lookup"><span data-stu-id="85016-130">When you're finished, click **Save**.</span></span>

### <a name="use-exchange-online-powershell-or-exchange-online-protection-powershell-to-configure-additional-recipients-for-outbound-spam-messages"></a><span data-ttu-id="85016-131">Utilizzare PowerShell di Exchange Online o Exchange Online Protection PowerShell per configurare i destinatari aggiuntivi per i messaggi di posta indesiderata in uscita</span><span class="sxs-lookup"><span data-stu-id="85016-131">Use Exchange Online PowerShell or Exchange Online Protection PowerShell to configure additional recipients for outbound spam messages</span></span>

<span data-ttu-id="85016-132">Per abilitare e configurare altri destinatari per i messaggi di posta indesiderata in uscita, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="85016-132">To enable and configure additional recipients for outbound spam messages, use the following syntax:</span></span>

```PowerShell
Set-HostedOutboundSpamFilterPolicy -Identity Default -BccSuspiciousOutboundMail $true -BccSuspiciousOutboundAdditionalRecipients <recipients>
```

- <span data-ttu-id="85016-133">Per specificare i destinatari che sovrascrivono tutti i valori esistenti, `emailaddress1,emailaddress2,...emailaddressN`utilizzare la sintassi.</span><span class="sxs-lookup"><span data-stu-id="85016-133">To specify recipients that overwrite all existing values, use the syntax `emailaddress1,emailaddress2,...emailaddressN`.</span></span>

- <span data-ttu-id="85016-134">Per aggiungere o rimuovere selettivamente i destinatari senza influire sulle altre voci, utilizzare la `@{Add="\<emailaddress1\>","\<emailaddress2\>"...; Remove="\<emailaddress1\>","\<emailaddress2\>"...}`sintassi.</span><span class="sxs-lookup"><span data-stu-id="85016-134">To selectively add or remove recipients without affecting the other entries, use the syntax `@{Add="\<emailaddress1\>","\<emailaddress2\>"...; Remove="\<emailaddress1\>","\<emailaddress2\>"...}`.</span></span>

<span data-ttu-id="85016-135">In questo esempio vengono abilitati e configurati chris@contoso.com, laura@contoso.com e julia@contoso.com come destinatari Ccn per i messaggi di posta indesiderata in uscita.</span><span class="sxs-lookup"><span data-stu-id="85016-135">This example enables and configures chris@contoso.com, laura@contoso.com and julia@contoso.com as Bcc recipients for outbound spam messages.</span></span>

```PowerShell
Set-HostedOutboundSpamFilterPolicy -Identity Default -BccSuspiciousOutboundMail $true -BccSuspiciousOutboundAdditionalRecipients chris@contoso.com,laura@contoso.com,julia@contoso.com
```

<span data-ttu-id="85016-136">In questo esempio viene aggiunto michelle@contoso.com come destinatario Ccn aggiuntivo.</span><span class="sxs-lookup"><span data-stu-id="85016-136">This example adds michelle@contoso.com as an additional Bcc recipient.</span></span>

```PowerShell
Set-HostedOutboundSpamFilterPolicy -Identity Default -BccSuspiciousOutboundAdditionalRecipients @{Add=michelle@contoso.com}
```

<span data-ttu-id="85016-137">Questo esempio consente di rimuovere chris@contoso.com e julia@contoso.com dall'elenco dei destinatari Ccn.</span><span class="sxs-lookup"><span data-stu-id="85016-137">This example removes chris@contoso.com and julia@contoso.com from the list of Bcc recipients.</span></span>

```PowerShell
Set-HostedOutboundSpamFilterPolicy -Identity Default -BccSuspiciousOutboundAdditionalRecipients @{Remove='chris@contoso.com','julia@contoso.com'}
```

<span data-ttu-id="85016-138">Per informazioni dettagliate sulla sintassi e sui parametri, vedere [set-HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-hostedoutboundspamfilterpolicy).</span><span class="sxs-lookup"><span data-stu-id="85016-138">For detailed syntax and parameter information, see [Set-HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-hostedoutboundspamfilterpolicy).</span></span>

<span data-ttu-id="85016-139">**Nota**: eseguire il comando `Get-HostedOutboundSpamFilterPolicy | Format-List` per visualizzare i valori correnti delle proprietà *BccSuspiciousOutboundMail* e *BccSuspiciousOutboundAdditionalRecipients* .</span><span class="sxs-lookup"><span data-stu-id="85016-139">**Note**: Run the command `Get-HostedOutboundSpamFilterPolicy | Format-List` to see the current values of the *BccSuspiciousOutboundMail* and *BccSuspiciousOutboundAdditionalRecipients* properties.</span></span>

## <a name="use-the-security--compliance-center-to-configure-notifications-when-a-sender-is-blocked"></a><span data-ttu-id="85016-140">Utilizzare il Centro sicurezza & Compliance per configurare le notifiche quando un mittente è bloccato</span><span class="sxs-lookup"><span data-stu-id="85016-140">Use the Security & Compliance Center to configure notifications when a sender is blocked</span></span>

1. <span data-ttu-id="85016-141">Nel centro sicurezza & conformità, accedere a **criteri di avviso** **avvisi** \> .</span><span class="sxs-lookup"><span data-stu-id="85016-141">In the Security & Compliance Center, go to **Alerts** \> **Alert Policies**.</span></span>

2. <span data-ttu-id="85016-142">Individuare e selezionare il criterio denominato **utente con restrizioni dall'invio di posta elettronica**.</span><span class="sxs-lookup"><span data-stu-id="85016-142">Find and select the policy named **User restricted from sending email**.</span></span>

3. <span data-ttu-id="85016-143">All'apertura del volo, fare clic su **modifica criterio**.</span><span class="sxs-lookup"><span data-stu-id="85016-143">In the fly out that opens, click **Edit policy**.</span></span>

4. <span data-ttu-id="85016-144">Nella pagina **modifica destinatari** visualizzata, configurare le impostazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="85016-144">In the **Edit recipients** page that appears, configure the following settings:</span></span>

   - <span data-ttu-id="85016-145">**Invia notifiche tramite posta elettronica**: **verificare che sia** selezionata l'opzione.</span><span class="sxs-lookup"><span data-stu-id="85016-145">**Send email notifications**: Verify that **On** is selected.</span></span>

   - <span data-ttu-id="85016-146">**Destinatari della posta elettronica**: per impostazione predefinita, **TenantAdmins** è l'unico valore qui.</span><span class="sxs-lookup"><span data-stu-id="85016-146">**Email recipients**: By default **TenantAdmins** is the only value here.</span></span> <span data-ttu-id="85016-147">Per aggiungere altri destinatari, fare clic in un punto vuoto in questa casella, iniziare a digitare il destinatario e selezionare il destinatario quando il nome viene risolto.</span><span class="sxs-lookup"><span data-stu-id="85016-147">To add additional recipients, click in an empty spot in this box, start typing the recipient, and select the recipient when their name resolves.</span></span> <span data-ttu-id="85016-148">Per rimuovere i destinatari, fare clic sulla **X** accanto ai rispettivi nomi.</span><span class="sxs-lookup"><span data-stu-id="85016-148">To remove recipients, click on the **X** next to their names.</span></span>

   - <span data-ttu-id="85016-149">**Limite di notifica giornaliero**: il valore predefinito è **Nessun limite**, ma è possibile configurare diversi limiti da 1 a 200.</span><span class="sxs-lookup"><span data-stu-id="85016-149">**Daily notification limit**: The default value is **No limit**, but you can configure various limits from 1 to 200.</span></span>

   <span data-ttu-id="85016-150">Al termine, scegliere **Salva**.</span><span class="sxs-lookup"><span data-stu-id="85016-150">When you're finished, click **Save**.</span></span>

## <a name="for-more-information"></a><span data-ttu-id="85016-151">Ulteriori informazioni</span><span class="sxs-lookup"><span data-stu-id="85016-151">For more information</span></span>

[<span data-ttu-id="85016-152">Pool di recapito ad alto rischio per i messaggi in uscita</span><span class="sxs-lookup"><span data-stu-id="85016-152">High-risk delivery pool for outbound messages</span></span>](high-risk-delivery-pool-for-outbound-messages.md)

[<span data-ttu-id="85016-153">Domande frequenti sulla protezione da posta indesiderata</span><span class="sxs-lookup"><span data-stu-id="85016-153">Anti-spam protection FAQ</span></span>](anti-spam-protection-faq.md)
