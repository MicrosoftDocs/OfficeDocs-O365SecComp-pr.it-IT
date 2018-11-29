---
title: Utilizzare DKIM per convalidare la posta elettronica in uscita inviata dal dominio personalizzato in Office 365
ms.author: krowley
author: kccross
manager: laurawi
ms.date: ''
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.custom: TN2DMC
search.appverid:
- MET150
ms.assetid: 56fee1c7-dc37-470e-9b09-33fff6d94617
description: 'Riepilogo: In questo articolo viene descritto come utilizzare DomainKeys Identified Mail (DKIM) insieme a Office 365 per essere certi che i sistemi di posta elettronica di destinazione ritengano attendibili i messaggi inviati dal dominio personalizzato.'
ms.openlocfilehash: 67652fc11a42263b2666554021c018df01ad33cd
ms.sourcegitcommit: bf628da123a89d9422e8cff02165b1e2d35dfe12
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/28/2018
ms.locfileid: "26872004"
---
# <a name="use-dkim-to-validate-outbound-email-sent-from-your-custom-domain-in-office-365"></a><span data-ttu-id="8c070-103">Utilizzare DKIM per convalidare la posta elettronica in uscita inviata dal dominio personalizzato in Office 365</span><span class="sxs-lookup"><span data-stu-id="8c070-103">Use DKIM to validate outbound email sent from your custom domain in Office 365</span></span>

 <span data-ttu-id="8c070-104">**Riepilogo:** In questo articolo viene descritto come utilizzare DomainKeys Identified Mail (DKIM) insieme a Office 365 per essere certi che i sistemi di posta elettronica di destinazione ritengano attendibili i messaggi inviati dal dominio personalizzato.</span><span class="sxs-lookup"><span data-stu-id="8c070-104">**Summary:** This article describes how you use DomainKeys Identified Mail (DKIM) with Office 365 to ensure that destination email systems trust messages sent from your custom domain.</span></span> 
  
<span data-ttu-id="8c070-p101">È necessario utilizzare DKIM in aggiunta a SPF e DMARC per impedire agli spoofer di inviare messaggi che sembrano provenire dal proprio dominio. DKIM consente di aggiungere una firma digitale nell'intestazione dei messaggi di posta elettronica. Non è complicato come sembra. Quando si configura DKIM, il dominio viene autorizzato ad associare (oppure firmare) il proprio nome ai messaggi di posta elettronica utilizzando l'autenticazione di crittografia. I sistemi di posta elettronica che ricevono messaggi dal dominio dell'utente possono utilizzare questa firma digitale per stabilire la legittimità del messaggio ricevuto.</span><span class="sxs-lookup"><span data-stu-id="8c070-p101">You should use DKIM in addition to SPF and DMARC to help prevent spoofers from sending messages that look like they are coming from your domain. DKIM lets you add a digital signature to email messages in the message header. Sounds complicated, but it's really not. When you configure DKIM, you authorize your domain to associate, or sign, its name to an email message by using cryptographic authentication. Email systems that receive email from your domain can use this digital signature to help determine if incoming email that they receive is legitimate.</span></span>
  
<span data-ttu-id="8c070-p102">In sostanza, si utilizza una chiave privata per crittografare l'intestazione nel messaggio di posta elettronica in uscita dal proprio dominio. Nei record DNS del dominio viene pubblicata una chiave pubblica utilizzata dai server di ricezione per decodificare la firma. La chiave pubblica viene utilizzata per verificare che i messaggi provengano realmente dall'utente e non da qualche operazione di spoofing in atto nel dominio.</span><span class="sxs-lookup"><span data-stu-id="8c070-p102">Basically, you use a private key to encrypt the header in your domain's outgoing email. You publish a public key to your domain's DNS records that receiving servers can then use to decode the signature. They use the public key to verify that the messages are really coming from you and not coming from someone spoofing your domain.</span></span>
  
<span data-ttu-id="8c070-p103">Office 365 consente di configurare automaticamente DKIM per i domini iniziali. Il dominio iniziale è il dominio creato da Office 365 per l'utente al momento della sua registrazione per il servizio, ad esempio, contoso.onmicrosoft.com. Non è necessario eseguire nessuna operazione per configurare DKIM per il dominio iniziale. Per ulteriori informazioni sui domini, vedere [Domande frequenti sui domini](https://support.office.com/article/Domains-FAQ-1272bad0-4bd4-4796-8005-67d6fb3afc5a#bkmk_whydoihaveanonmicrosoft.comdomain).</span><span class="sxs-lookup"><span data-stu-id="8c070-p103">Office 365 automatically sets up DKIM for initial domains. The initial domain is the domain that Office 365 created for you when you signed up with the service, for example, contoso.onmicrosoft.com. You don't need to do anything to set up DKIM for your initial domain. For more information about domains, see [Domains FAQ](https://support.office.com/article/Domains-FAQ-1272bad0-4bd4-4796-8005-67d6fb3afc5a#bkmk_whydoihaveanonmicrosoft.comdomain).</span></span>
  
<span data-ttu-id="8c070-p104">È possibile scegliere di non eseguire nessuna operazione su DKIM anche per il dominio personalizzato. Se non viene configurato DKIM per il dominio personalizzato, Office 365 crea una coppia di chiave pubblica e privata, abilita la firma DKIM e configura il criterio predefinito di Office 365 per il dominio personalizzato. Sebbene questa configurazione sia sufficiente per la maggior parte dei clienti di Office 365, è necessario configurare manualmente la chiave DKIM per il dominio personalizzato nei casi seguenti:</span><span class="sxs-lookup"><span data-stu-id="8c070-p104">You can choose to do nothing about DKIM for your custom domain too. If you do not set up DKIM for your custom domain, Office 365 creates a private and public key pair, enables DKIM signing, and then configures the Office 365 default policy for your custom domain. While this is sufficient coverage for most Office 365 customers, you should manually configure DKIM for your custom domain in the following circumstances:</span></span>
  
- <span data-ttu-id="8c070-120">Sono disponibili più domini personalizzati in Office 365</span><span class="sxs-lookup"><span data-stu-id="8c070-120">You have more than one custom domain in Office 365</span></span>
    
- <span data-ttu-id="8c070-121">Si intende configurare anche DMARC (consigliato)</span><span class="sxs-lookup"><span data-stu-id="8c070-121">You're going to set up DMARC too (recommended)</span></span>
    
- <span data-ttu-id="8c070-122">Si desidera gestire la chiave privata</span><span class="sxs-lookup"><span data-stu-id="8c070-122">You want control over your private key</span></span>
    
- <span data-ttu-id="8c070-123">Si desidera personalizzare i record CNAME</span><span class="sxs-lookup"><span data-stu-id="8c070-123">You want to customize your CNAME records</span></span>
    
- <span data-ttu-id="8c070-124">Si configurano le chiavi DKIM per la posta elettronica creata da un dominio di terze parti, ad esempio, un mailer di massa di terze parti.</span><span class="sxs-lookup"><span data-stu-id="8c070-124">You want to set up DKIM keys for email originating out of a third-party domain, for example, if you use a third-party bulk mailer.</span></span>
    
<span data-ttu-id="8c070-125">Contenuto dell'articolo:</span><span class="sxs-lookup"><span data-stu-id="8c070-125">In this article:</span></span>
  
- [<span data-ttu-id="8c070-126">In che modo DKIM è più efficace di SPF per impedire lo spoofing dannoso in Office 365</span><span class="sxs-lookup"><span data-stu-id="8c070-126">How DKIM works better than SPF alone to prevent malicious spoofing in Office 365</span></span>](use-dkim-to-validate-outbound-email.md#HowDKIMWorks)
    
- [<span data-ttu-id="8c070-127">Operazioni necessarie per configurare manualmente la chiave DKIM in Office 365</span><span class="sxs-lookup"><span data-stu-id="8c070-127">What you need to do to manually set up DKIM in Office 365</span></span>](use-dkim-to-validate-outbound-email.md#SetUpDKIMO365)
    
- [<span data-ttu-id="8c070-128">Per configurare DKIM per più domini personalizzati in Office 365</span><span class="sxs-lookup"><span data-stu-id="8c070-128">To configure DKIM for more than one custom domain in Office 365</span></span>](use-dkim-to-validate-outbound-email.md#DKIMMultiDomain)
    
- [<span data-ttu-id="8c070-129">Disabilitazione del criterio di firma DKIM per un dominio personalizzato di Office 365</span><span class="sxs-lookup"><span data-stu-id="8c070-129">Disabling the DKIM signing policy for a custom domain in Office 365</span></span>](use-dkim-to-validate-outbound-email.md#DisableDKIMSigningPolicy)
    
- [<span data-ttu-id="8c070-130">Comportamento predefinito per DKIM e Office 365</span><span class="sxs-lookup"><span data-stu-id="8c070-130">Default behavior for DKIM and Office 365</span></span>](use-dkim-to-validate-outbound-email.md#DefaultDKIMbehavior)
    
- [<span data-ttu-id="8c070-131">Configurare DKIM in modo che un servizio di terze parti possa inviare la posta elettronica o effettuarne lo spoofing per conto del dominio personalizzato dell'utente</span><span class="sxs-lookup"><span data-stu-id="8c070-131">Set up DKIM so that a third-party service can send, or spoof, email on behalf of your custom domain</span></span>](use-dkim-to-validate-outbound-email.md#SetUp3rdPartyspoof)
    
- [<span data-ttu-id="8c070-132">Passaggi successivi: Dopo aver configurato DKIM per Office 365</span><span class="sxs-lookup"><span data-stu-id="8c070-132">Next steps: After you set up DKIM for Office 365</span></span>](use-dkim-to-validate-outbound-email.md#DKIMNextSteps)
    
## <a name="how-dkim-works-better-than-spf-alone-to-prevent-malicious-spoofing-in-office-365"></a><span data-ttu-id="8c070-133">In che modo DKIM è più efficace di SPF per impedire lo spoofing dannoso in Office 365</span><span class="sxs-lookup"><span data-stu-id="8c070-133">How DKIM works better than SPF alone to prevent malicious spoofing in Office 365</span></span>
<span data-ttu-id="8c070-134"><a name="HowDKIMWorks"> </a></span><span class="sxs-lookup"><span data-stu-id="8c070-134"></span></span>

<span data-ttu-id="8c070-p105">SPF consente di aggiungere informazioni alla busta del messaggio, ma DKIM esegue la crittografia di una firma all'interno dell'intestazione del messaggio. Quando si inoltra un messaggio, alcune parti della busta possono essere eliminate dal server di inoltro. Dal momento che la firma digitale rimane unita al messaggio di posta elettronica perché fa parte dell'intestazione, DKIM funziona anche quando un messaggio è stato inoltrato come mostrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="8c070-p105">SPF adds information to a message envelope but DKIM actually encrypts a signature within the message header. When you forward a message, portions of that message's envelope can be stripped away by the forwarding server. Since the digital signature stays with the email message because it's part of the email header, DKIM works even when a message has been forwarded as shown in the following example.</span></span>
  
![Diagramma che mostra il messaggio inoltrato che supera l'autenticazione DKIM anche se il controllo SPF ha esito negativo](media/28f93b4c-97e7-4309-acc4-fd0d2e0e3377.jpg)
  
<span data-ttu-id="8c070-p106">In questo esempio, se è stato pubblicato soltanto un record SPF TXT per il dominio, il server di posta del mittente avrebbe potuto contrassegnare la posta come indesiderata e generare un risultato falso positivo. L'aggiunta di DKIM in questo scenario riduce i rapporti spam falsi positivi. Dal momento che DKIM si affida alla crittografia della chiave pubblica per eseguire l'autenticazione e non soltanto agli indirizzi IP, la chiave DKIM è considerata come una forma di autenticazione più affidabile rispetto a SPF. È opportuno utilizzare sia SPF che DKIM e DMARC nella propria distribuzione.</span><span class="sxs-lookup"><span data-stu-id="8c070-p106">In this example, if you had only published an SPF TXT record for your domain, the recipient's mail server could have marked your email as spam and generated a false positive result. The addition of DKIM in this scenario reduces false positive spam reporting. Because DKIM relies on public key cryptography to authenticate and not just IP addresses, DKIM is considered a much stronger form of authentication than SPF. We recommend using both SPF and DKIM, as well as DMARC in your deployment.</span></span>
  
<span data-ttu-id="8c070-p107">In sostanza, DKIM utilizza una chiave privata per inserire una firma crittografata all'interno delle intestazioni dei messaggi. Il dominio di firma o dominio di uscita viene inserito come valore del campo **d=** nell'intestazione. Il dominio di verifica o dominio del destinatario utilizza il campo **d=** per cercare la chiave pubblica dal DNS ed esegue l'autenticazione del messaggio. Se il messaggio viene verificato, i controlli DKIM hanno esito positivo.</span><span class="sxs-lookup"><span data-stu-id="8c070-p107">The nitty gritty: DKIM uses a private key to insert an encrypted signature into the message headers. The signing domain, or outbound domain, is inserted as the value of the **d=** field in the header. The verifying domain, or recipient's domain, then use the **d=** field to look up the public key from DNS and authenticate the message. If the message is verified, the DKIM check passes.</span></span> 
  
## <a name="what-you-need-to-do-to-manually-set-up-dkim-in-office-365"></a><span data-ttu-id="8c070-147">Operazioni necessarie per configurare manualmente la chiave DKIM in Office 365</span><span class="sxs-lookup"><span data-stu-id="8c070-147">What you need to do to manually set up DKIM in Office 365</span></span>
<span data-ttu-id="8c070-148"><a name="SetUpDKIMO365"> </a></span><span class="sxs-lookup"><span data-stu-id="8c070-148"></span></span>

<span data-ttu-id="8c070-149">Per configurare DKIM, eseguire la procedura seguente:</span><span class="sxs-lookup"><span data-stu-id="8c070-149">To configure DKIM, you will complete these steps:</span></span>
  
- [<span data-ttu-id="8c070-150">Pubblicare due record CNAME per il dominio personalizzato in DNS</span><span class="sxs-lookup"><span data-stu-id="8c070-150">Publish two CNAME records for your custom domain in DNS</span></span>](use-dkim-to-validate-outbound-email.md#Publish2CNAME)
    
- [<span data-ttu-id="8c070-151">Abilitare la firma DKIM per il dominio personalizzato in Office 365</span><span class="sxs-lookup"><span data-stu-id="8c070-151">Enable DKIM signing for your custom domain in Office 365</span></span>](use-dkim-to-validate-outbound-email.md#EnableDKIMinO365)
    
### <a name="publish-two-cname-records-for-your-custom-domain-in-dns"></a><span data-ttu-id="8c070-152">Pubblicare due record CNAME per il dominio personalizzato in DNS</span><span class="sxs-lookup"><span data-stu-id="8c070-152">Publish two CNAME records for your custom domain in DNS</span></span>
<span data-ttu-id="8c070-153"><a name="Publish2CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="8c070-153"></span></span>

<span data-ttu-id="8c070-p108">Per ogni dominio al quale si intende aggiungere una firma DKIM in DNS è necessario pubblicare due record CNAME. Un record CNAME viene usato da DNS per specificare che il nome canonico di un dominio è l'alias di un altro nome di dominio.</span><span class="sxs-lookup"><span data-stu-id="8c070-p108">For each domain for which you want to add a DKIM signature in DNS, you need to publish two CNAME records. A CNAME record is used by DNS to specify that the canonical name of a domain is an alias for another domain name.</span></span> 
  
 <span data-ttu-id="8c070-p109"> Office 365 esegue la rotazione automatica delle chiavi utilizzando due record indicati dall'utente. Se è stato eseguito il provisioning di domini personalizzati oltre al dominio iniziale in Office 365, è necessario pubblicare due record CNAME per ogni dominio aggiuntivo. Pertanto, se sono disponibili due domini, è necessario pubblicare altri due record CNAME e così via.</span><span class="sxs-lookup"><span data-stu-id="8c070-p109">Office 365 performs automatic key rotation using the two records that you establish. If you have provisioned custom domains in addition to the initial domain in Office 365, you must publish two CNAME records for each additional domain. So, if you have two domains, you must publish two additional CNAME records, and so on.</span></span> 
  
<span data-ttu-id="8c070-159">Per i record CNAME, utilizzare il formato seguente:</span><span class="sxs-lookup"><span data-stu-id="8c070-159">Use the following format for the CNAME records:</span></span>
  
```
Host name:          selector1._domainkey.<domain>
Points to address or value: selector1-<domainGUID>._domainkey.<initialDomain> 
TTL:                3600

Host name:          selector2._domainkey.<domain>
Points to address or value: selector2-<domainGUID>._domainkey.<initialDomain> 
TTL:                3600
```

<span data-ttu-id="8c070-160">Dove:</span><span class="sxs-lookup"><span data-stu-id="8c070-160">Where:</span></span>
  
- <span data-ttu-id="8c070-161">Per Office 365, i selettori saranno sempre "selector1" o "selector2".</span><span class="sxs-lookup"><span data-stu-id="8c070-161">For Office 365, the selectors will always be "selector1" or "selector2".</span></span> 
    
- <span data-ttu-id="8c070-p110">_domainGUID_ corrisponde al _domainGUID_ il record MX personalizzato per il dominio personalizzato che viene visualizzata prima mail.protection.outlook.com. Ad esempio, il seguente record MX per il dominio contoso.com, _domainGUID_ è contoso-com:</span><span class="sxs-lookup"><span data-stu-id="8c070-p110">_domainGUID_ is the same as the _domainGUID_ in the customized MX record for your custom domain that appears before mail.protection.outlook.com. For example, in the following MX record for the domain contoso.com, the _domainGUID_ is contoso-com:</span></span> 
    
    ```
    contoso.com.  3600  IN  MX   5 contoso-com.mail.protection.outlook.com
    ```

- <span data-ttu-id="8c070-p111">_initialDomain_ è il dominio utilizzato quando è iscritti a Office 365. Domini iniziali terminano sempre onmicrosoft.com. Per informazioni su come determinare il dominio iniziale, vedere [Domande frequenti su domini](https://support.office.com/article/1272bad0-4bd4-4796-8005-67d6fb3afc5a#bkmk_whydoihaveanonmicrosoft.comdomain).</span><span class="sxs-lookup"><span data-stu-id="8c070-p111">_initialDomain_ is the domain that you used when you signed up for Office 365. Initial domains always end in onmicrosoft.com. For information about determining your initial domain, see [Domains FAQ](https://support.office.com/article/1272bad0-4bd4-4796-8005-67d6fb3afc5a#bkmk_whydoihaveanonmicrosoft.comdomain).</span></span>
    
<span data-ttu-id="8c070-167">Ad esempio, se si dispone di un dominio iniziale di cohovineyardandwinery.onmicrosoft.com e di due domini personalizzati cohovineyard.com e cohowinery.com, è necessario configurare due record CNAME per ogni dominio aggiuntivo, per un totale di quattro record CNAME.</span><span class="sxs-lookup"><span data-stu-id="8c070-167">For example, if you have an initial domain of cohovineyardandwinery.onmicrosoft.com, and two custom domains cohovineyard.com and cohowinery.com, you would need to set up two CNAME records for each additional domain, for a total of four CNAME records.</span></span>
  
```
Host name:          selector1._domainkey.cohovineyard.com  
Points to address or value: selector1-cohovineyard-com._domainkey.cohovineyardandwinery.onmicrosoft.com
TTL:                3600

Host name:          selector2._domainkey.cohovineyard.com  
Points to address or value: selector2-cohovineyard-com._domainkey.cohovineyardandwinery.onmicrosoft.com
TTL:                3600

Host name:          selector1._domainkey.cohowinery.com
Points to address or value: selector1-cohowinery-com._domainkey.cohovineyardandwinery.onmicrosoft.com 
TTL:                3600
 
Host name:          selector2._domainkey.cohowinery.com
Points to address or value: selector2-cohowinery-com._domainkey.cohovineyardandwinery.onmicrosoft.com 
TTL:                3600
```

### <a name="enable-dkim-signing-for-your-custom-domain-in-office-365"></a><span data-ttu-id="8c070-168">Abilitare la firma DKIM per il dominio personalizzato in Office 365</span><span class="sxs-lookup"><span data-stu-id="8c070-168">Enable DKIM signing for your custom domain in Office 365</span></span>
<span data-ttu-id="8c070-169"><a name="EnableDKIMinO365"> </a></span><span class="sxs-lookup"><span data-stu-id="8c070-169"></span></span>

<span data-ttu-id="8c070-p112">Dopo aver pubblicato i record CNAME in DNS, è possibile abilitare la firma DKIM tramite Office 365. È possibile eseguire questa operazione tramite l'interfaccia di amministrazione di Office 365 oppure PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8c070-p112">Once you have published the CNAME records in DNS, you are ready to enable DKIM signing through Office 365. You can do this either through the Office 365 admin center or by using PowerShell.</span></span>
  
#### <a name="to-enable-dkim-signing-for-your-custom-domain-through-the-office-365-admin-center"></a><span data-ttu-id="8c070-172">Per abilitare la firma DKIM del dominio personalizzato tramite l'interfaccia di amministrazione di Office 365</span><span class="sxs-lookup"><span data-stu-id="8c070-172">To enable DKIM signing for your custom domain through the Office 365 admin center</span></span>

1. <span data-ttu-id="8c070-173">[Accedere a Office 365](https://support.office.microsoft.com/article/e9eb7d51-5430-4929-91ab-6157c5a050b4) con l'account aziendale o dell'istituto di istruzione.</span><span class="sxs-lookup"><span data-stu-id="8c070-173">[Sign in to Office 365](https://support.office.microsoft.com/article/e9eb7d51-5430-4929-91ab-6157c5a050b4) with your work or school account.</span></span> 
    
2. <span data-ttu-id="8c070-174">Selezionare l'icona di avvio delle app in alto a sinistra e scegliere **Amministrazione**.</span><span class="sxs-lookup"><span data-stu-id="8c070-174">Select the app launcher icon in the upper-left and choose **Admin**.</span></span>
    
3. <span data-ttu-id="8c070-175">Nel riquadro di spostamento in basso a sinistra, espandere **Amministrazione** e scegliere **Exchange**.</span><span class="sxs-lookup"><span data-stu-id="8c070-175">In the lower-left navigation, expand **Admin** and choose **Exchange**.</span></span>
    
4. <span data-ttu-id="8c070-176">Accedere a **Protezione** \> **dkim**.</span><span class="sxs-lookup"><span data-stu-id="8c070-176">Go to **Protection** \> **dkim**.</span></span>
    
5. <span data-ttu-id="8c070-p113">Selezionare il dominio per il quale si desidera abilitare DKIM, quindi, in **Firma i messaggi per questo dominio con firme DKIM** scegliere **Abilita**. Ripetere questo passaggio per ogni dominio personalizzato.</span><span class="sxs-lookup"><span data-stu-id="8c070-p113">Select the domain for which you want to enable DKIM and then, for **Sign messages for this domain with DKIM signatures**, choose **Enable**. Repeat this step for each custom domain.</span></span>
    
#### <a name="to-enable-dkim-signing-for-your-custom-domain-by-using-powershell"></a><span data-ttu-id="8c070-179">Per abilitare la firma DKIM del dominio personalizzato usando PowerShell</span><span class="sxs-lookup"><span data-stu-id="8c070-179">To enable DKIM signing for your custom domain by using PowerShell</span></span>

1. <span data-ttu-id="8c070-180">[Connettersi a Exchange Online PowerShell](https://technet.microsoft.com/library/jj984289.aspx).</span><span class="sxs-lookup"><span data-stu-id="8c070-180">[Connect to Exchange Online PowerShell](https://technet.microsoft.com/library/jj984289.aspx).</span></span>
    
2. <span data-ttu-id="8c070-181">Eseguire il comando riportato di seguito:</span><span class="sxs-lookup"><span data-stu-id="8c070-181">Run the following command:</span></span>
    
    ```
    New-DkimSigningConfig -DomainName <domain> -Enabled $true
    ```

   <span data-ttu-id="8c070-182">Dove _dominio_ è il nome di dominio personalizzato che si desidera abilitare DKIM per la firma.</span><span class="sxs-lookup"><span data-stu-id="8c070-182">Where _domain_ is the name of the custom domain that you want to enable DKIM signing for.</span></span> 
    
   <span data-ttu-id="8c070-183">Ad esempio, per domain contoso.com:</span><span class="sxs-lookup"><span data-stu-id="8c070-183">For example, for the domain contoso.com:</span></span>
    
    ```
    New-DkimSigningConfig -DomainName contoso.com -Enabled $true
    ```

#### <a name="to-confirm-dkim-signing-is-configured-properly-for-office-365"></a><span data-ttu-id="8c070-184">Per confermare che la firma DKIM sia configurata in modo corretto in Office 365</span><span class="sxs-lookup"><span data-stu-id="8c070-184">To Confirm DKIM signing is configured properly for Office 365</span></span>

<span data-ttu-id="8c070-p114">Attendere qualche minuto prima di effettuare i passaggi seguenti e confermare di aver configurato DKIM in modo corretto. In questo modo, le informazioni DKIM sul dominio possono essere distribuite nella rete.</span><span class="sxs-lookup"><span data-stu-id="8c070-p114">Wait a few minutes before you follow these steps to confirm that you have properly configured DKIM. This allows time for the DKIM information about the domain to be spread throughout the network.</span></span>
  
- <span data-ttu-id="8c070-187">Inviare un messaggio da un account incluso nel dominio Office 365 con DKIM abilitato a un altro account di posta elettronica, ad esempio, outlook.com o Hotmail.com.</span><span class="sxs-lookup"><span data-stu-id="8c070-187">Send a message from an account within your Office 365 DKIM-enabled domain to another email account such as outlook.com or Hotmail.com.</span></span>
    
- <span data-ttu-id="8c070-p115">Non utilizzare un account aol.com per effettuare test. AOL potrebbe ignorare il controllo DKIM se la verifica SPF ha esito positivo. In questo modo, il test verrebbe annullato.</span><span class="sxs-lookup"><span data-stu-id="8c070-p115">Do not use an aol.com account for testing purposes. AOL may skip the DKIM check if the SPF check passes. This will nullify your test.</span></span>
    
- <span data-ttu-id="8c070-p116">Aprire il messaggio e osservare l'intestazione. Le istruzioni per visualizzare l'intestazione del messaggio variano in base al client di messaggistica usato. Per istruzioni sulla visualizzazione delle intestazioni dei messaggi in Outlook, vedere [Visualizzare le intestazioni dei messaggi di posta elettronica](https://support.office.com/article/CD039382-DC6E-4264-AC74-C048563D212C).</span><span class="sxs-lookup"><span data-stu-id="8c070-p116">Open the message and look at the header. Instructions for viewing the header for the message will vary depending on your messaging client. For instructions on viewing message headers in Outlook, see [View e-mail message headers](https://support.office.com/article/CD039382-DC6E-4264-AC74-C048563D212C).</span></span>

  <span data-ttu-id="8c070-p117">Il messaggio con firma DKIM conterrà il nome host e il dominio definiti durante la pubblicazione delle voci CNAME. Il messaggio avrà un aspetto analogo a quello riportato nell'esempio:</span><span class="sxs-lookup"><span data-stu-id="8c070-p117">The DKIM-signed message will contain the host name and domain you defined when you published the CNAME entries. The message will look something like this example:</span></span> 
    
    ```
    From: Example User <example@contoso.com> 
    DKIM-Signature: v=1; a=rsa-sha256; q=dns/txt; c=relaxed/relaxed; 
        s=selector1; d=contoso.com; t=1429912795; 
        h=From:To:Message-ID:Subject:MIME-Version:Content-Type; 
        bh=<body hash>; 
        b=<signed field>;
    ```

- <span data-ttu-id="8c070-p118">Cercare l'intestazione Authentication-Results. Anche se ogni servizio di ricezione utilizza un formato differente per indicare la posta in arrivo, il risultato deve includere **DKIM=pass** o **DKIM=OK**.</span><span class="sxs-lookup"><span data-stu-id="8c070-p118">Look for the Authentication-Results header. While each receiving service uses a slightly different format to stamp the incoming mail, the result should include something like **DKIM=pass** or **DKIM=OK**.</span></span> 
    
## <a name="to-configure-dkim-for-more-than-one-custom-domain-in-office-365"></a><span data-ttu-id="8c070-198">Per configurare DKIM per più domini personalizzati in Office 365</span><span class="sxs-lookup"><span data-stu-id="8c070-198">To configure DKIM for more than one custom domain in Office 365</span></span>
<span data-ttu-id="8c070-199"><a name="DKIMMultiDomain"> </a></span><span class="sxs-lookup"><span data-stu-id="8c070-199"></span></span>

<span data-ttu-id="8c070-p119">Se in futuro si decide di aggiungere un altro dominio personalizzato e di abilitare DKIM, è necessario eseguire la procedura indicata in questo articolo per ogni dominio. In particolare, completare tutti i passaggi elencati in [Operazioni necessarie per configurare manualmente la chiave DKIM in Office 365](use-dkim-to-validate-outbound-email.md#SetUpDKIMO365).</span><span class="sxs-lookup"><span data-stu-id="8c070-p119">If at some point in the future you decide to add another custom domain and you want to enable DKIM for the new domain, you must complete the steps in this article for each domain. Specifically, complete all steps in [What you need to do to manually set up DKIM in Office 365](use-dkim-to-validate-outbound-email.md#SetUpDKIMO365).</span></span>
  
## <a name="disabling-the-dkim-signing-policy-for-a-custom-domain-in-office-365"></a><span data-ttu-id="8c070-202">Disabilitazione del criterio di firma DKIM per un dominio personalizzato di Office 365</span><span class="sxs-lookup"><span data-stu-id="8c070-202">Disabling the DKIM signing policy for a custom domain in Office 365</span></span>
<span data-ttu-id="8c070-203"><a name="DisableDKIMSigningPolicy"> </a></span><span class="sxs-lookup"><span data-stu-id="8c070-203"></span></span>

<span data-ttu-id="8c070-p120">La disabilitazione del criterio di firma non disattiva completamente DKIM. Dopo un periodo di tempo, Office 365 applicherà automaticamente il suo criterio predefinito al dominio. Per ulteriori informazioni vedere [Comportamento predefinito per DKIM e Office 365](use-dkim-to-validate-outbound-email.md#DefaultDKIMbehavior).</span><span class="sxs-lookup"><span data-stu-id="8c070-p120">Disabling the signing policy does not completely disable DKIM. After a period of time, Office 365 will automatically apply the default Office 365 policy for your domain. For more information, see [Default behavior for DKIM and Office 365](use-dkim-to-validate-outbound-email.md#DefaultDKIMbehavior).</span></span>
  
### <a name="to-disable-the-dkim-signing-policy-by-using-windows-powershell"></a><span data-ttu-id="8c070-207">Per disabilitare il criterio di firma DKIM usando Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="8c070-207">To disable the DKIM signing policy by using Windows PowerShell</span></span>

1. <span data-ttu-id="8c070-208">[Connettersi a Exchange Online PowerShell](https://technet.microsoft.com/library/jj984289.aspx).</span><span class="sxs-lookup"><span data-stu-id="8c070-208">[Connect to Exchange Online PowerShell](https://technet.microsoft.com/library/jj984289.aspx).</span></span>
    
2. <span data-ttu-id="8c070-209">Eseguire uno dei comandi seguenti per ogni dominio per il quale si desidera disabilitare la firma DKIM.</span><span class="sxs-lookup"><span data-stu-id="8c070-209">Run one of the following commands for each domain for which you want to disable DKIM signing.</span></span>
    
    ```
    $p=Get-DkimSigningConfig -identity <domain>
    $p[0] | set-DkimSigningConfig -enabled $false
    ```

   <span data-ttu-id="8c070-210">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="8c070-210">For example:</span></span>
    
    ```
    $p=Get-DkimSigningConfig -identity contoso.com
    $p[0] | set-DkimSigningConfig -enabled $false
    ```

   <span data-ttu-id="8c070-211">Oppure</span><span class="sxs-lookup"><span data-stu-id="8c070-211">Or</span></span>
    
    ```
    Set-DkimSigningConfig -identity $p[<number>].identity -enabled $false
    ```

    <span data-ttu-id="8c070-p121">Dove _number_ è l'indice del criterio. Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="8c070-p121">Where _number_ is the index of the policy. For example:</span></span> 
    
    ```
    Set-DkimSigningConfig -identity $p[0].identity -enabled $false
    ```

## <a name="default-behavior-for-dkim-and-office-365"></a><span data-ttu-id="8c070-214">Comportamento predefinito per DKIM e Office 365</span><span class="sxs-lookup"><span data-stu-id="8c070-214">Default behavior for DKIM and Office 365</span></span>
<span data-ttu-id="8c070-215"><a name="DefaultDKIMbehavior"> </a></span><span class="sxs-lookup"><span data-stu-id="8c070-215"></span></span>

<span data-ttu-id="8c070-p122">Se non si abilita DKIM, Office 365 crea automaticamente una chiave pubblica DKIM da 1024 bit per il dominio personalizzato e la chiave privata associata, la quale viene archiviata nei datacenter Microsoft. Per impostazione predefinita, Office 365 utilizza una configurazione di firma predefinita per i domini che non dispongono di un criterio. Ciò significa che se l'utente non configura DKIM, Office 365 utilizza il criterio predefinito e le chiavi create per abilitare DKIM nel dominio.</span><span class="sxs-lookup"><span data-stu-id="8c070-p122">If you do not enable DKIM, Office 365 automatically creates a 1024-bit DKIM public key for your custom domain and the associated private key which we store internally in our datacenter. By default, Office 365 uses a default signing configuration for domains that do not have a policy in place. This means that if you do not set up DKIM yourself, Office 365 will use its default policy and keys it creates in order to enable DKIM for your domain.</span></span>
  
<span data-ttu-id="8c070-219">Inoltre, se si disabilita la firma DKIM dopo l'attivazione, Office 365 applica automaticamente (dopo un determinato periodo di tempo) il criterio predefinito di Office 365 per il dominio.</span><span class="sxs-lookup"><span data-stu-id="8c070-219">Also, if you disable DKIM signing after enabling it, after a period of time, Office 365 will automatically apply the Office 365 default policy for your domain.</span></span>
  
<span data-ttu-id="8c070-p123">Nell'esempio seguente, considerare che la chiave DKIM per fabrikam.com sia stata abilitata da Office 365 e non dall'amministratore del dominio. Questo errore indica che i record CNAME necessari non sono presenti nel sistema DNS. Le firme DKIM per i messaggi di posta elettronica provenienti dal dominio avranno un aspetto analogo al seguente:</span><span class="sxs-lookup"><span data-stu-id="8c070-p123">In the following example, suppose that DKIM for fabrikam.com was enabled by Office 365, not by the administrator of the domain. This means that the required CNAMEs do not exist in DNS. DKIM signatures for email from this domain will look something like this:</span></span>
  
```
From: Second Example <second.example@fabrikam.com> 
DKIM-Signature: v=1; a=rsa-sha256; q=dns/txt; c=relaxed/relaxed; 
    s=selector1-fabrikam-com; d=contoso.onmicrosoft.com; t=1429912795; 
    h=From:To:Message-ID:Subject:MIME-Version:Content-Type; 
    bh=<body hash>; 
    b=<signed field>;
```

<span data-ttu-id="8c070-p124">In questo caso, il nome host e il dominio includono i valori a cui dovrebbe puntare CNAME se la firma DKIM per fabrikam.com fosse stata abilitata dall'amministratore di dominio. Infine, ogni messaggio inviato da Office 365 sarà firmato con la chiave DKIM. Se la chiave DKIM è stata abilitata dall'utente, il dominio sarà identico a quello dell'indirizzo "Da:", in questo caso, fabrikam.com. In caso contrario, non verrà allineato e utilizzerà il dominio iniziale dell'organizzazione. Per informazioni su come determinare il dominio iniziale, vedere [Domande frequenti sui domini](https://support.office.com/article/1272bad0-4bd4-4796-8005-67d6fb3afc5a#bkmk_whydoihaveanonmicrosoft.comdomain).</span><span class="sxs-lookup"><span data-stu-id="8c070-p124">In this example, the host name and domain contain the values to which the CNAME would point if DKIM-signing for fabrikam.com had been enabled by the domain administrator. Eventually, every single message sent from Office 365 will be DKIM-signed. If you enable DKIM yourself, the domain will be the same as the domain in the From: address, in this case fabrikam.com. If you don't, it will not align and instead will use your organization's initial domain. For information about determining your initial domain, see [Domains FAQ](https://support.office.com/article/1272bad0-4bd4-4796-8005-67d6fb3afc5a#bkmk_whydoihaveanonmicrosoft.comdomain).</span></span>
  
## <a name="set-up-dkim-so-that-a-third-party-service-can-send-or-spoof-email-on-behalf-of-your-custom-domain"></a><span data-ttu-id="8c070-228">Configurare DKIM in modo che un servizio di terze parti possa inviare la posta elettronica o effettuarne lo spoofing per conto del dominio personalizzato dell'utente</span><span class="sxs-lookup"><span data-stu-id="8c070-228">Set up DKIM so that a third-party service can send, or spoof, email on behalf of your custom domain</span></span>
<span data-ttu-id="8c070-229"><a name="SetUp3rdPartyspoof"> </a></span><span class="sxs-lookup"><span data-stu-id="8c070-229"></span></span>

<span data-ttu-id="8c070-p125">Alcuni provider di servizi di posta di massa o di software come servizio consentono di configurare le chiavi DKIM per la posta elettronica che viene creata dal servizio. Per configurare i record DNS necessari, l'utente e la terza parte devono essere coordinati. Nessuna organizzazione esegue questa operazione nello stesso modo. Al contrario, il processo dipende interamente dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="8c070-p125">Some bulk email service providers, or software-as-a-service providers, let you set up DKIM keys for email that originates from their service. This requires coordination between yourself and the third-party in order to set up the necessary DNS records. No two organizations do it exactly the same way. Instead, the process depends entirely on the organization.</span></span>
  
<span data-ttu-id="8c070-234">Messaggio di esempio che mostra una chiave DKIM correttamente configurata per contoso.com e bulkemailprovider.com avrà l'aspetto seguente:</span><span class="sxs-lookup"><span data-stu-id="8c070-234">An example message showing a properly configured DKIM for contoso.com and bulkemailprovider.com might look like this:</span></span>
  
```
Return-Path: <communication@bulkemailprovider.com>
 From: <sender@contoso.com>
 DKIM-Signature: s=s1024; d=contoso.com
 Subject: Here is a message from Bulk Email Provider's infrastructure, but with a DKIM signature authorized by contoso.com
```

<span data-ttu-id="8c070-235">In questo esempio, per raggiungere il risultato:</span><span class="sxs-lookup"><span data-stu-id="8c070-235">In this example, in order to achieve this result:</span></span>
  
1. <span data-ttu-id="8c070-236">Il provider di posta elettronica di massa ha fornito a Contoso una chiave DKIM pubblica.</span><span class="sxs-lookup"><span data-stu-id="8c070-236">Bulk Email Provider gave Contoso a public DKIM key.</span></span>
    
2. <span data-ttu-id="8c070-237">Contoso ha pubblicato la chiave DKIM nel suo record DNS.</span><span class="sxs-lookup"><span data-stu-id="8c070-237">Contoso published the DKIM key to its DNS record.</span></span>
    
3. <span data-ttu-id="8c070-p126">Durante l'invio della posta elettronica, il provider della posta elettronica inviata in blocco firma la chiave con quella privata corrispondente. In questo modo, il provider della posta elettronica inviata in blocco ha allegato la firma DKIM all'intestazione del messaggio.</span><span class="sxs-lookup"><span data-stu-id="8c070-p126">When sending email, Bulk Email Provider signs the key with the corresponding private key. By doing so, Bulk Email Provider attached the DKIM signature to the message header.</span></span>
    
4. <span data-ttu-id="8c070-p127">I sistemi di ricezione della posta elettronica eseguono un confronto tra il valore d=\<domain\> della chiave DKIM firmata e il dominio nell'indirizzo Da: (5322.From) del messaggio. In questo esempio, i valori corrispondono a:</span><span class="sxs-lookup"><span data-stu-id="8c070-p127">Receiving email systems perform a DKIM check by authenticating the DKIM-Signature d=\<domain\> value against the domain in the From: (5322.From) address of the message. In this example, the values match:</span></span>
    
    <span data-ttu-id="8c070-242">mittente @**contoso.com**</span><span class="sxs-lookup"><span data-stu-id="8c070-242">sender@**contoso.com**</span></span>
    
    <span data-ttu-id="8c070-243">g =**contoso.com**</span><span class="sxs-lookup"><span data-stu-id="8c070-243">d=**contoso.com**</span></span>
    
## <a name="next-steps-after-you-set-up-dkim-for-office-365"></a><span data-ttu-id="8c070-244">Passaggi successivi: Dopo aver configurato DKIM per Office 365</span><span class="sxs-lookup"><span data-stu-id="8c070-244">Next steps: After you set up DKIM for Office 365</span></span>
<span data-ttu-id="8c070-245"><a name="DKIMNextSteps"> </a></span><span class="sxs-lookup"><span data-stu-id="8c070-245"></span></span>

<span data-ttu-id="8c070-p128">Sebbene DKIM è progettato per impedire attacchi di spoofing, DKIM funziona meglio con SPF e DMARC. Dopo aver impostato i DKIM, se non già configurati SPF è consigliabile farlo. Per una breve introduzione a SPF e per ottenere una configurazione rapidamente, vedere [impostare SPF in Office 365 per evitare attacchi di spoofing](set-up-spf-in-office-365-to-help-prevent-spoofing.md). Per una più approfondita dei come Office 365 utilizza SPF o per le distribuzioni di risoluzione dei problemi o non standard, ad esempio le distribuzioni ibride, iniziare con [la modalità di Office 365 utilizza mittente Policy Framework (SPF) per impedire attacchi di spoofing](how-office-365-uses-spf-to-prevent-spoofing.md). Successivamente, vedere [Utilizzo DMARC per convalidare la posta elettronica in Office 365](use-dmarc-to-validate-email.md). [Intestazioni messaggi della protezione da posta indesiderata](anti-spam-message-headers.md) sono inclusi i campi di intestazione e la sintassi utilizzati da Office 365 per le verifiche DKIM.</span><span class="sxs-lookup"><span data-stu-id="8c070-p128">Although DKIM is designed to help prevent spoofing, DKIM works better with SPF and DMARC. Once you have set up DKIM, if you have not already set up SPF you should do so. For a quick introduction to SPF and to get it configured quickly, see [Set up SPF in Office 365 to help prevent spoofing](set-up-spf-in-office-365-to-help-prevent-spoofing.md). For a more in-depth understanding of how Office 365 uses SPF, or for troubleshooting or non-standard deployments such as hybrid deployments, start with [How Office 365 uses Sender Policy Framework (SPF) to prevent spoofing](how-office-365-uses-spf-to-prevent-spoofing.md). Next, see [Use DMARC to validate email in Office 365](use-dmarc-to-validate-email.md). [Anti-spam message headers](anti-spam-message-headers.md) includes the syntax and header fields used by Office 365 for DKIM checks.</span></span> 
  

