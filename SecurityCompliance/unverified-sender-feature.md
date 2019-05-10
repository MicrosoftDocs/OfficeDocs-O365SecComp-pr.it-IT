---
title: Mittente non verificato
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.date: 04/25/2019
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: Per impedire ai messaggi di phishing di raggiungere la propria cassetta postale, Outlook.com e Outlook sul Web verificano che il mittente sia quello che dicono di essere e contrassegnare i messaggi sospetti come posta indesiderata.
ms.openlocfilehash: 5d4315afb33964e7c466384366b7315287cf6298
ms.sourcegitcommit: d24f50347c671cf5d2d8afec2f80d37d18af8b5d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/10/2019
ms.locfileid: "33867845"
---
# <a name="unverified-sender"></a><span data-ttu-id="01f84-103">Mittente non verificato</span><span class="sxs-lookup"><span data-stu-id="01f84-103">Unverified Sender</span></span>

<span data-ttu-id="01f84-104">Per impedire ai messaggi di phishing di raggiungere la propria cassetta postale, Outlook.com e Outlook sul Web verificano che il mittente sia quello che dicono di essere e contrassegnare i messaggi sospetti come posta indesiderata.</span><span class="sxs-lookup"><span data-stu-id="01f84-104">To prevent phishing messages from reaching your mailbox, Outlook.com and Outlook on the web verify that the sender is who they say they are and mark suspicious messages as junk email.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="01f84-105">Quando un messaggio viene contrassegnato come truffa di phishing, Outlook.com e Outlook sul Web visualizzano un avviso nella parte superiore della pagina, ma qualsiasi collegamento nel messaggio può ancora essere aperto.</span><span class="sxs-lookup"><span data-stu-id="01f84-105">When a message is marked as a phishing scam, Outlook.com and Outlook on the web display a warning at the top of the page, but any links in the message can still be opened.</span></span>

## <a name="how-can-i-identify-a-suspicious-message-in-my-inbox"></a><span data-ttu-id="01f84-106">Come è possibile identificare un messaggio sospetto nella cartella posta in arrivo?</span><span class="sxs-lookup"><span data-stu-id="01f84-106">How can I identify a suspicious message in my inbox?</span></span>

<span data-ttu-id="01f84-107">Outlook.com e Outlook sul Web mostrano gli indicatori quando il mittente di un messaggio non può essere identificato o la loro identità è diversa da quella visualizzata nell'indirizzo da.</span><span class="sxs-lookup"><span data-stu-id="01f84-107">Outlook.com and Outlook on the web show indicators when the sender of a message either can't be identified or their identity is different from what you see in the From address.</span></span>

## <a name="how-to-manage-which-messages-receive-the-unverified-sender-treatment"></a><span data-ttu-id="01f84-108">Come gestire i messaggi che ricevono il trattamento dei mittenti non verificati</span><span class="sxs-lookup"><span data-stu-id="01f84-108">How to manage which messages receive the unverified sender treatment</span></span> 

<span data-ttu-id="01f84-109">Se si è un cliente di Office 365, è possibile gestire questa funzionalità tramite il Centro sicurezza & Compliance.</span><span class="sxs-lookup"><span data-stu-id="01f84-109">If you are an Office 365 customer you can manage this feature through the Security & Compliance Center.</span></span> 

- <span data-ttu-id="01f84-110">Nel centro conformità di Office 365 Security &, gli amministratori tenant possono attivarla o disattivarla tramite la protezione anti-spoofing in base ai criteri anti-phishing.</span><span class="sxs-lookup"><span data-stu-id="01f84-110">In the Office 365 Security & Compliance Center, tenant admins can turn the feature on, or off, through the Anti-spoofing protection under the Anti-Phish policy.</span></span> <span data-ttu-id="01f84-111">Inoltre, può essere gestito tramite il cmdlet ' set-AntiPhishPolicy '.</span><span class="sxs-lookup"><span data-stu-id="01f84-111">Additionally, it can be managed through the ‘Set-AntiPhishPolicy’ cmdlet.</span></span> <span data-ttu-id="01f84-112">Per ulteriori informazioni, vedere protezione anti-phishing in Office 365 e set-AntiPhishPolicy.</span><span class="sxs-lookup"><span data-stu-id="01f84-112">For more details, see Anti-phishing protection in Office 365 and Set-AntiPhishPolicy.</span></span>

    ![Modifica dei mittenti non autenticati nell'interfaccia grafica.](media/unverified-sender-article-editing-unauthenticated-senders.jpg)

- <span data-ttu-id="01f84-114">Se un amministratore ha identificato un falso positivo e un mittente non deve ricevere il trattamento del mittente non verificato, è possibile eseguire una delle azioni seguenti per aggiungere il mittente all'elenco Consenti spoof di spoofing Intelligence:</span><span class="sxs-lookup"><span data-stu-id="01f84-114">If an admin has identified a false positive, and a sender should not be receiving the unverified sender treatment they can take one of the following actions to add the sender to the Spoof Intelligence spoof allow list:</span></span>
        
    - <span data-ttu-id="01f84-115">Aggiungere la coppia di domini tramite lo spoofing Intelligence Insight.</span><span class="sxs-lookup"><span data-stu-id="01f84-115">Add the domain pair through the Spoof Intelligence Insight.</span></span> <span data-ttu-id="01f84-116">Per ulteriori informazioni, vedere Procedura dettagliata: spoofing Intelligence Insight</span><span class="sxs-lookup"><span data-stu-id="01f84-116">For more details, see Walkthrough: spoof intelligence insight</span></span>
                
    - <span data-ttu-id="01f84-117">Aggiungere la coppia di domini tramite il cmdlet PhishFilterPolicy.</span><span class="sxs-lookup"><span data-stu-id="01f84-117">Add the domain pair through the PhishFilterPolicy cmdlet.</span></span> <span data-ttu-id="01f84-118">Per ulteriori informazioni, vedere Set-PhishFilterPolicy e anti-spoofing Protection in Office 365</span><span class="sxs-lookup"><span data-stu-id="01f84-118">For more details, see Set-PhishFilterPolicy and Anti-spoofing protection in Office 365</span></span>

<span data-ttu-id="01f84-119">Inoltre, non viene applicato il trattamento del mittente non verificato se è stato recapitato nella posta in arrivo tramite un elenco di indirizzi consentiti, incluse le regole di trasporto della posta elettronica (ETRs), l'elenco dei domini attendibili (criterio di protezione dalla posta indesiderata), l'elenco dei mittenti attendibili o un utente che ha impostato questo utente come "mittente sicuro" posta in arrivo.</span><span class="sxs-lookup"><span data-stu-id="01f84-119">Additionally, we do not apply the unverified sender treatment if it was delivered to the inbox via an admin allow list, including Email Transport Rules (ETRs), Safe Domain List (Anti-Spam Policy), Safe Sender List or a user has set this user as a “Safe Sender” in their inbox.</span></span>

### <a name="you-see-a--in-the-sender-image"></a><span data-ttu-id="01f84-120">Viene visualizzato un'?' nell'immagine del mittente</span><span class="sxs-lookup"><span data-stu-id="01f84-120">You see a '?' in the sender image</span></span>

<span data-ttu-id="01f84-121">Quando Outlook.com e Outlook sul Web non sono in grado di verificare l'identità del mittente utilizzando le tecniche di autenticazione della posta elettronica, visualizzano una '?' nella foto del mittente.</span><span class="sxs-lookup"><span data-stu-id="01f84-121">When Outlook.com and Outlook on the web can't verify the identity of the sender using email authentication techniques, they display a '?' in the sender photo.</span></span> 

![Il messaggio non ha superato la verifica](media/message-did-not-pass-verification.jpg)

<span data-ttu-id="01f84-123">Non tutti i messaggi che non sono in grado di eseguire l'autenticazione sono dannosi.</span><span class="sxs-lookup"><span data-stu-id="01f84-123">Not every message that fails to authenticate is malicious.</span></span> <span data-ttu-id="01f84-124">Tuttavia, è necessario prestare particolare attenzione all'interazione con i messaggi che non eseguono l'autenticazione se non si riconosce il mittente.</span><span class="sxs-lookup"><span data-stu-id="01f84-124">However, you should be careful about interacting with messages that don't authenticate if you don't recognize the sender.</span></span> <span data-ttu-id="01f84-125">In alternativa, se si riconosce un mittente che in genere non ha un'?' nell'immagine del mittente, ma si inizia improvvisamente a vederlo, potrebbe essere un segno che il mittente viene falsificato.</span><span class="sxs-lookup"><span data-stu-id="01f84-125">Or, if you recognize a sender that normally doesn't have a '?' in the sender image, but you suddenly start seeing it, that could be a sign the sender is being spoofed.</span></span>

### <a name="the-senders-address-is-different-than-what-appears-in-the-from-address"></a><span data-ttu-id="01f84-126">L'indirizzo del mittente è diverso da quello visualizzato nell'indirizzo da</span><span class="sxs-lookup"><span data-stu-id="01f84-126">The sender's address is different than what appears in the From address</span></span>

<span data-ttu-id="01f84-127">Spesso, l'indirizzo di posta elettronica visualizzato in un messaggio è diverso da quello visualizzato nell'indirizzo mittente.</span><span class="sxs-lookup"><span data-stu-id="01f84-127">Frequently, the email address you see in a message is different than what you see in the From address.</span></span> <span data-ttu-id="01f84-128">A volte phisher tenta di ingannare l'utente a pensare che il mittente è una persona diversa da quella in cui sono realmente.</span><span class="sxs-lookup"><span data-stu-id="01f84-128">Sometimes phishers try to trick you into thinking that the sender is someone other than who they really are.</span></span>

<span data-ttu-id="01f84-129">Quando Outlook.com e Outlook sul web rilevano una differenza tra l'indirizzo effettivo del mittente e l'indirizzo dell'indirizzo da, visualizzano il mittente effettivo utilizzando il tag via, che verrà sottolineato.</span><span class="sxs-lookup"><span data-stu-id="01f84-129">When Outlook.com and Outlook on the web detect a difference between the sender's actual address and the address on the From address, they show the actual sender using the via tag, which will be underlined.</span></span>

![testo alternativo del mittente non verificato](media/unverified-sender-feature1.png)

<span data-ttu-id="01f84-131">In questo esempio, il dominio `suspicious.com` di invio viene autenticato, ma il mittente `unknown@contoso.com` è stato inserito nell'indirizzo from.</span><span class="sxs-lookup"><span data-stu-id="01f84-131">In this example, the sending domain `suspicious.com` is authenticated, but the sender put `unknown@contoso.com` in the From address.</span></span>

<span data-ttu-id="01f84-132">Non tutti i messaggi con un tag via sono sospetti.</span><span class="sxs-lookup"><span data-stu-id="01f84-132">Not every message with a via tag is suspicious.</span></span> <span data-ttu-id="01f84-133">Tuttavia, se non si riconosce un messaggio con un tag via, è consigliabile essere cauti nell'interagire con esso.</span><span class="sxs-lookup"><span data-stu-id="01f84-133">However, if you don't recognize a message with a via tag, you should be cautious about interacting with it.</span></span>

<span data-ttu-id="01f84-134">In Outlook.com e nel nuovo Outlook sul Web, è possibile posizionare il puntatore del mouse sul nome o sull'indirizzo del mittente nell'elenco dei messaggi per visualizzare l'indirizzo di posta elettronica, senza che sia necessario aprire il messaggio.</span><span class="sxs-lookup"><span data-stu-id="01f84-134">In Outlook.com and the new Outlook on the web, you can hover your cursor over a sender's name or address in the message list to see their email address, without needing to open the message.</span></span>

![Introduzione a OneDrive](media/get-started-with-onedrive-message.png)

<span data-ttu-id="01f84-136">Come si può sapere se si sta utilizzando il nuovo Outlook sul Web?</span><span class="sxs-lookup"><span data-stu-id="01f84-136">How do you know if you're using the new Outlook on the web?</span></span> <span data-ttu-id="01f84-137">Vedere gli esempi seguenti:</span><span class="sxs-lookup"><span data-stu-id="01f84-137">See the following examples:</span></span>

![Outlook vs Office 365](media/outlook-vs-outlook365.png)

## <a name="frequently-asked-questions"></a><span data-ttu-id="01f84-139">Domande frequenti</span><span class="sxs-lookup"><span data-stu-id="01f84-139">Frequently asked questions</span></span>

### <a name="what-criteria-does-outlookcom-and-outlook-on-the-web-use-to-add-the--and-the-via-properties"></a><span data-ttu-id="01f84-140">Quali criteri utilizza Outlook.com e Outlook sul Web per aggiungere le proprietà'?' è via '?</span><span class="sxs-lookup"><span data-stu-id="01f84-140">What criteria does Outlook.com and Outlook on the web use to add the '?' and the 'via' properties?</span></span>

<span data-ttu-id="01f84-141">Per il "?" nell'immagine del mittente: Outlook.com richiede che il messaggio passi l'autenticazione SPF o DKIM.</span><span class="sxs-lookup"><span data-stu-id="01f84-141">For the '?' in the sender image:  Outlook.com requires that the message pass either SPF or DKIM authentication.</span></span> <span data-ttu-id="01f84-142">Per ulteriori informazioni, vedere [set up SPF in office 365 per impedire lo spoofing](set-up-spf-in-office-365-to-help-prevent-spoofing.md) e [utilizzare DKIM per convalidare la posta elettronica in uscita inviata dal dominio personalizzato in Office 365](use-dkim-to-validate-outbound-email.md).</span><span class="sxs-lookup"><span data-stu-id="01f84-142">For more details, see [Set up SPF in Office 365 to help prevent spoofing](set-up-spf-in-office-365-to-help-prevent-spoofing.md) and [Use DKIM to validate outbound email sent from your custom domain in Office 365](use-dkim-to-validate-outbound-email.md).</span></span>

<span data-ttu-id="01f84-143">Per il tag Via: se il dominio nell'indirizzo from è diverso dal dominio nella firma di DKIM o nella posta SMTP da, Outlook.com Visualizza il dominio in uno di questi due campi (preferendo la firma di DKIM).</span><span class="sxs-lookup"><span data-stu-id="01f84-143">For the via tag: If the domain in the From address is different from the domain in the DKIM signature or the SMTP MAIL FROM, Outlook.com displays the domain in one of those two fields (preferring the DKIM signature).</span></span>

### <a name="can-i-override-these-properties-with-ip-allows-exchange-transport-rule-allows-or-safe-senders"></a><span data-ttu-id="01f84-144">È possibile ignorare queste proprietà con l'indirizzo IP consentito, la regola di trasporto di Exchange consente o i mittenti attendibili?</span><span class="sxs-lookup"><span data-stu-id="01f84-144">Can I override these properties with IP Allows, Exchange Transport Rule Allows, or safe senders?</span></span>

<span data-ttu-id="01f84-145">Non è possibile eseguire l'override di queste proprietà.</span><span class="sxs-lookup"><span data-stu-id="01f84-145">You can't override these properties.</span></span>

### <a name="how-do-i-remove-these-properties"></a><span data-ttu-id="01f84-146">Come si rimuovono queste proprietà?</span><span class="sxs-lookup"><span data-stu-id="01f84-146">How do I remove these properties?</span></span>

<span data-ttu-id="01f84-147">Per il "?" nell'immagine del mittente: come mittente, è necessario autenticare il messaggio con SPF o DKIM.</span><span class="sxs-lookup"><span data-stu-id="01f84-147">For the '?' in the sender image: As a sender, you should authenticate your message with either SPF or DKIM.</span></span>

<span data-ttu-id="01f84-148">Per il tag Via: come mittente, è necessario assicurarsi che il dominio nella firma di DKIM o la posta SMTP sia uguale a, o sia un sottodominio di, il dominio nell'indirizzo da.</span><span class="sxs-lookup"><span data-stu-id="01f84-148">For the via tag: As a sender, you should ensure that either the domain in the DKIM signature or the SMTP MAIL FROM is the same as, or is a subdomain of, the domain in the From address.</span></span>

### <a name="does-outlookcom-and-outlook-on-the-web-show-this-for-every-message-that-doesnt-pass-authentication"></a><span data-ttu-id="01f84-149">Outlook.com e Outlook sul Web mostrano questo per ogni messaggio che non passa l'autenticazione?</span><span class="sxs-lookup"><span data-stu-id="01f84-149">Does Outlook.com and Outlook on the web show this for every message that doesn’t pass authentication?</span></span>

<span data-ttu-id="01f84-150">Non necessariamente.</span><span class="sxs-lookup"><span data-stu-id="01f84-150">Not necessarily.</span></span> <span data-ttu-id="01f84-151">Outlook.com e Outlook sul Web possono avere altre proprietà all'interno del messaggio per autenticare il mittente.</span><span class="sxs-lookup"><span data-stu-id="01f84-151">Outlook.com and Outlook on the web may have other properties within the message to authenticate the sender.</span></span>

## <a name="related-topics"></a><span data-ttu-id="01f84-152">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="01f84-152">Related topics</span></span>

[<span data-ttu-id="01f84-153">Proteggi il tuo account di posta elettronica di Outlook.com</span><span class="sxs-lookup"><span data-stu-id="01f84-153">Help protect your Outlook.com email account</span></span>](https://support.office.com/article/a4f20fc5-4307-4ece-8231-6d4d4bd8a9ba)

[<span data-ttu-id="01f84-154">Gestire abusi, tentativi di phishing o spoofing in Outlook.com</span><span class="sxs-lookup"><span data-stu-id="01f84-154">Deal with abuse, phishing, or spoofing in Outlook.com</span></span>](https://support.office.com/article/0d882ea5-eedc-4bed-aebc-079ffa1105a3)

[<span data-ttu-id="01f84-155">Filtrare la posta indesiderata e la posta indesiderata in Outlook sul Web</span><span class="sxs-lookup"><span data-stu-id="01f84-155">Filter junk email and spam in Outlook on the web</span></span>](https://support.office.com/article/db786e79-54e2-40cc-904f-d89d57b7f41d)
