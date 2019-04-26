---
title: Identificare i messaggi sospetti in Outlook.com e Outlook sul Web
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
ms.openlocfilehash: edba30bb2ac0f9dc6ebc12db957a518de0c1b543
ms.sourcegitcommit: 9907bebc5f225032f681c4952de0b0be2df278ac
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/26/2019
ms.locfileid: "33345906"
---
# <a name="identify-suspicious-messages-in-outlookcom-and-outlook-on-the-web"></a><span data-ttu-id="1d4f6-103">Identificare i messaggi sospetti in Outlook.com e Outlook sul Web</span><span class="sxs-lookup"><span data-stu-id="1d4f6-103">Identify suspicious messages in Outlook.com and Outlook on the web</span></span>

<span data-ttu-id="1d4f6-104">Per impedire ai messaggi di phishing di raggiungere la propria cassetta postale, Outlook.com e Outlook sul Web verificano che il mittente sia quello che dicono di essere e contrassegnare i messaggi sospetti come posta indesiderata.</span><span class="sxs-lookup"><span data-stu-id="1d4f6-104">To prevent phishing messages from reaching your mailbox, Outlook.com and Outlook on the web verify that the sender is who they say they are and mark suspicious messages as junk email.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1d4f6-105">Quando un messaggio viene contrassegnato come truffa di phishing, Outlook.com e Outlook sul Web visualizzano un avviso nella parte superiore della pagina, ma qualsiasi collegamento nel messaggio può ancora essere aperto.</span><span class="sxs-lookup"><span data-stu-id="1d4f6-105">When a message is marked as a phishing scam, Outlook.com and Outlook on the web display a warning at the top of the page, but any links in the message can still be opened.</span></span>

## <a name="how-can-i-identify-a-suspicious-message-in-my-inbox"></a><span data-ttu-id="1d4f6-106">Come è possibile identificare un messaggio sospetto nella cartella posta in arrivo?</span><span class="sxs-lookup"><span data-stu-id="1d4f6-106">How can I identify a suspicious message in my inbox?</span></span>

<span data-ttu-id="1d4f6-107">Outlook.com e Outlook sul Web mostrano gli indicatori quando il mittente di un messaggio non può essere identificato o la loro identità è diversa da quella visualizzata nell'indirizzo da.</span><span class="sxs-lookup"><span data-stu-id="1d4f6-107">Outlook.com and Outlook on the web show indicators when the sender of a message either can't be identified or their identity is different from what you see in the From address.</span></span>

### <a name="you-see-a--in-the-sender-image"></a><span data-ttu-id="1d4f6-108">Viene visualizzato un'?' nell'immagine del mittente</span><span class="sxs-lookup"><span data-stu-id="1d4f6-108">You see a '?' in the sender image</span></span>

<span data-ttu-id="1d4f6-109">Quando Outlook.com e Outlook sul Web non sono in grado di verificare l'identità del mittente utilizzando le tecniche di autenticazione della posta elettronica, visualizzano una '?' nella foto del mittente.</span><span class="sxs-lookup"><span data-stu-id="1d4f6-109">When Outlook.com and Outlook on the web can't verify the identity of the sender using email authentication techniques, they display a '?' in the sender photo.</span></span>

![Il messaggio non ha superato la verifica](media/message-did-not-pass-verification.jpg)

<span data-ttu-id="1d4f6-111">Non tutti i messaggi che non sono in grado di eseguire l'autenticazione sono dannosi.</span><span class="sxs-lookup"><span data-stu-id="1d4f6-111">Not every message that fails to authenticate is malicious.</span></span> <span data-ttu-id="1d4f6-112">Tuttavia, è necessario prestare particolare attenzione all'interazione con i messaggi che non eseguono l'autenticazione se non si riconosce il mittente.</span><span class="sxs-lookup"><span data-stu-id="1d4f6-112">However, you should be careful about interacting with messages that don't authenticate if you don't recognize the sender.</span></span> <span data-ttu-id="1d4f6-113">In alternativa, se si riconosce un mittente che in genere non ha un'?' nell'immagine del mittente, ma si inizia improvvisamente a vederlo, potrebbe essere un segno che il mittente viene falsificato.</span><span class="sxs-lookup"><span data-stu-id="1d4f6-113">Or, if you recognize a sender that normally doesn't have a '?' in the sender image, but you suddenly start seeing it, that could be a sign the sender is being spoofed.</span></span>

### <a name="the-senders-address-is-different-than-what-appears-in-the-from-address"></a><span data-ttu-id="1d4f6-114">L'indirizzo del mittente è diverso da quello visualizzato nell'indirizzo da</span><span class="sxs-lookup"><span data-stu-id="1d4f6-114">The sender's address is different than what appears in the From address</span></span>

<span data-ttu-id="1d4f6-115">Spesso, l'indirizzo di posta elettronica visualizzato in un messaggio è diverso da quello visualizzato nell'indirizzo mittente.</span><span class="sxs-lookup"><span data-stu-id="1d4f6-115">Frequently, the email address you see in a message is different than what you see in the From address.</span></span> <span data-ttu-id="1d4f6-116">A volte phisher tenta di ingannare l'utente a pensare che il mittente è una persona diversa da quella in cui sono realmente.</span><span class="sxs-lookup"><span data-stu-id="1d4f6-116">Sometimes phishers try to trick you into thinking that the sender is someone other than who they really are.</span></span>

<span data-ttu-id="1d4f6-117">Quando Outlook.com e Outlook sul web rilevano una differenza tra l'indirizzo effettivo del mittente e l'indirizzo dell'indirizzo da, visualizzano il mittente effettivo utilizzando il tag via, che verrà sottolineato.</span><span class="sxs-lookup"><span data-stu-id="1d4f6-117">When Outlook.com and Outlook on the web detect a difference between the sender's actual address and the address on the From address, they show the actual sender using the via tag, which will be underlined.</span></span>

![testo alternativo del mittente non verificato](media/unverified-sender-feature1.png)

<span data-ttu-id="1d4f6-119">In questo esempio, il dominio `suspicious.com` di invio viene autenticato, ma il mittente `unknown@contoso.com` è stato inserito nell'indirizzo from.</span><span class="sxs-lookup"><span data-stu-id="1d4f6-119">In this example, the sending domain `suspicious.com` is authenticated, but the sender put `unknown@contoso.com` in the From address.</span></span>

<span data-ttu-id="1d4f6-120">Non tutti i messaggi con un tag via sono sospetti.</span><span class="sxs-lookup"><span data-stu-id="1d4f6-120">Not every message with a via tag is suspicious.</span></span> <span data-ttu-id="1d4f6-121">Tuttavia, se non si riconosce un messaggio con un tag via, è consigliabile essere cauti nell'interagire con esso.</span><span class="sxs-lookup"><span data-stu-id="1d4f6-121">However, if you don't recognize a message with a via tag, you should be cautious about interacting with it.</span></span>

<span data-ttu-id="1d4f6-122">In Outlook.com e nel nuovo Outlook sul Web, è possibile posizionare il puntatore del mouse sul nome o sull'indirizzo del mittente nell'elenco dei messaggi per visualizzare l'indirizzo di posta elettronica, senza che sia necessario aprire il messaggio.</span><span class="sxs-lookup"><span data-stu-id="1d4f6-122">In Outlook.com and the new Outlook on the web, you can hover your cursor over a sender's name or address in the message list to see their email address, without needing to open the message.</span></span>

![Introduzione a OneDrive](media/get-started-with-onedrive-message.png)

<span data-ttu-id="1d4f6-124">Come si può sapere se si sta utilizzando il nuovo Outlook sul Web?</span><span class="sxs-lookup"><span data-stu-id="1d4f6-124">How do you know if you're using the new Outlook on the web?</span></span> <span data-ttu-id="1d4f6-125">Vedere gli esempi seguenti:</span><span class="sxs-lookup"><span data-stu-id="1d4f6-125">See the following examples:</span></span>

![Outlook vs Office 365](media/outlook-vs-outlook365.png)

## <a name="frequently-asked-questions"></a><span data-ttu-id="1d4f6-127">Domande frequenti</span><span class="sxs-lookup"><span data-stu-id="1d4f6-127">Frequently asked questions</span></span>

### <a name="what-criteria-does-outlookcom-and-outlook-on-the-web-use-to-add-the--and-the-via-properties"></a><span data-ttu-id="1d4f6-128">Quali criteri utilizza Outlook.com e Outlook sul Web per aggiungere le proprietà'?' è via '?</span><span class="sxs-lookup"><span data-stu-id="1d4f6-128">What criteria does Outlook.com and Outlook on the web use to add the '?' and the 'via' properties?</span></span>

<span data-ttu-id="1d4f6-129">Per il "?" nell'immagine del mittente: Outlook.com richiede che il messaggio passi l'autenticazione SPF o DKIM.</span><span class="sxs-lookup"><span data-stu-id="1d4f6-129">For the '?' in the sender image:  Outlook.com requires that the message pass either SPF or DKIM authentication.</span></span> <span data-ttu-id="1d4f6-130">Per ulteriori informazioni, vedere [set up SPF in office 365 per impedire lo spoofing](set-up-spf-in-office-365-to-help-prevent-spoofing.md) e [utilizzare DKIM per convalidare la posta elettronica in uscita inviata dal dominio personalizzato in Office 365](use-dkim-to-validate-outbound-email.md).</span><span class="sxs-lookup"><span data-stu-id="1d4f6-130">For more details, see [Set up SPF in Office 365 to help prevent spoofing](set-up-spf-in-office-365-to-help-prevent-spoofing.md) and [Use DKIM to validate outbound email sent from your custom domain in Office 365](use-dkim-to-validate-outbound-email.md).</span></span>

<span data-ttu-id="1d4f6-131">Per il tag Via: se il dominio nell'indirizzo from è diverso dal dominio nella firma di DKIM o nella posta SMTP da, Outlook.com Visualizza il dominio in uno di questi due campi (preferendo la firma di DKIM).</span><span class="sxs-lookup"><span data-stu-id="1d4f6-131">For the via tag: If the domain in the From address is different from the domain in the DKIM signature or the SMTP MAIL FROM, Outlook.com displays the domain in one of those two fields (preferring the DKIM signature).</span></span>

### <a name="can-i-override-these-properties-with-ip-allows-exchange-transport-rule-allows-or-safe-senders"></a><span data-ttu-id="1d4f6-132">È possibile ignorare queste proprietà con l'indirizzo IP consentito, la regola di trasporto di Exchange consente o i mittenti attendibili?</span><span class="sxs-lookup"><span data-stu-id="1d4f6-132">Can I override these properties with IP Allows, Exchange Transport Rule Allows, or safe senders?</span></span>

<span data-ttu-id="1d4f6-133">Non è possibile eseguire l'override di queste proprietà.</span><span class="sxs-lookup"><span data-stu-id="1d4f6-133">You can't override these properties.</span></span>

### <a name="how-do-i-remove-these-properties"></a><span data-ttu-id="1d4f6-134">Come si rimuovono queste proprietà?</span><span class="sxs-lookup"><span data-stu-id="1d4f6-134">How do I remove these properties?</span></span>

<span data-ttu-id="1d4f6-135">Per il "?" nell'immagine del mittente: come mittente, è necessario autenticare il messaggio con SPF o DKIM.</span><span class="sxs-lookup"><span data-stu-id="1d4f6-135">For the '?' in the sender image: As a sender, you should authenticate your message with either SPF or DKIM.</span></span>

<span data-ttu-id="1d4f6-136">Per il tag Via: come mittente, è necessario assicurarsi che il dominio nella firma di DKIM o la posta SMTP sia uguale a, o sia un sottodominio di, il dominio nell'indirizzo da.</span><span class="sxs-lookup"><span data-stu-id="1d4f6-136">For the via tag: As a sender, you should ensure that either the domain in the DKIM signature or the SMTP MAIL FROM is the same as, or is a subdomain of, the domain in the From address.</span></span>

### <a name="does-outlookcom-and-outlook-on-the-web-show-this-for-every-message-that-doesnt-pass-authentication"></a><span data-ttu-id="1d4f6-137">Outlook.com e Outlook sul Web mostrano questo per ogni messaggio che non passa l'autenticazione?</span><span class="sxs-lookup"><span data-stu-id="1d4f6-137">Does Outlook.com and Outlook on the web show this for every message that doesn’t pass authentication?</span></span>

<span data-ttu-id="1d4f6-138">Non necessariamente.</span><span class="sxs-lookup"><span data-stu-id="1d4f6-138">Not necessarily.</span></span> <span data-ttu-id="1d4f6-139">Outlook.com e Outlook sul Web possono avere altre proprietà all'interno del messaggio per autenticare il mittente.</span><span class="sxs-lookup"><span data-stu-id="1d4f6-139">Outlook.com and Outlook on the web may have other properties within the message to authenticate the sender.</span></span>

## <a name="related-topics"></a><span data-ttu-id="1d4f6-140">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="1d4f6-140">Related topics</span></span>

[<span data-ttu-id="1d4f6-141">Proteggi il tuo account di posta elettronica di Outlook.com</span><span class="sxs-lookup"><span data-stu-id="1d4f6-141">Help protect your Outlook.com email account</span></span>](https://support.office.com/article/a4f20fc5-4307-4ece-8231-6d4d4bd8a9ba)

[<span data-ttu-id="1d4f6-142">Gestire abusi, tentativi di phishing o spoofing in Outlook.com</span><span class="sxs-lookup"><span data-stu-id="1d4f6-142">Deal with abuse, phishing, or spoofing in Outlook.com</span></span>](https://support.office.com/article/0d882ea5-eedc-4bed-aebc-079ffa1105a3)

[<span data-ttu-id="1d4f6-143">Filtrare la posta indesiderata e la posta indesiderata in Outlook sul Web</span><span class="sxs-lookup"><span data-stu-id="1d4f6-143">Filter junk email and spam in Outlook on the web</span></span>](https://support.office.com/article/db786e79-54e2-40cc-904f-d89d57b7f41d)
