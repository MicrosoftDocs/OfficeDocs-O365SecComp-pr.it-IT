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
# <a name="identify-suspicious-messages-in-outlookcom-and-outlook-on-the-web"></a>Identificare i messaggi sospetti in Outlook.com e Outlook sul Web

Per impedire ai messaggi di phishing di raggiungere la propria cassetta postale, Outlook.com e Outlook sul Web verificano che il mittente sia quello che dicono di essere e contrassegnare i messaggi sospetti come posta indesiderata.

> [!IMPORTANT]
> Quando un messaggio viene contrassegnato come truffa di phishing, Outlook.com e Outlook sul Web visualizzano un avviso nella parte superiore della pagina, ma qualsiasi collegamento nel messaggio può ancora essere aperto.

## <a name="how-can-i-identify-a-suspicious-message-in-my-inbox"></a>Come è possibile identificare un messaggio sospetto nella cartella posta in arrivo?

Outlook.com e Outlook sul Web mostrano gli indicatori quando il mittente di un messaggio non può essere identificato o la loro identità è diversa da quella visualizzata nell'indirizzo da.

### <a name="you-see-a--in-the-sender-image"></a>Viene visualizzato un'?' nell'immagine del mittente

Quando Outlook.com e Outlook sul Web non sono in grado di verificare l'identità del mittente utilizzando le tecniche di autenticazione della posta elettronica, visualizzano una '?' nella foto del mittente.

![Il messaggio non ha superato la verifica](media/message-did-not-pass-verification.jpg)

Non tutti i messaggi che non sono in grado di eseguire l'autenticazione sono dannosi. Tuttavia, è necessario prestare particolare attenzione all'interazione con i messaggi che non eseguono l'autenticazione se non si riconosce il mittente. In alternativa, se si riconosce un mittente che in genere non ha un'?' nell'immagine del mittente, ma si inizia improvvisamente a vederlo, potrebbe essere un segno che il mittente viene falsificato.

### <a name="the-senders-address-is-different-than-what-appears-in-the-from-address"></a>L'indirizzo del mittente è diverso da quello visualizzato nell'indirizzo da

Spesso, l'indirizzo di posta elettronica visualizzato in un messaggio è diverso da quello visualizzato nell'indirizzo mittente. A volte phisher tenta di ingannare l'utente a pensare che il mittente è una persona diversa da quella in cui sono realmente.

Quando Outlook.com e Outlook sul web rilevano una differenza tra l'indirizzo effettivo del mittente e l'indirizzo dell'indirizzo da, visualizzano il mittente effettivo utilizzando il tag via, che verrà sottolineato.

![testo alternativo del mittente non verificato](media/unverified-sender-feature1.png)

In questo esempio, il dominio `suspicious.com` di invio viene autenticato, ma il mittente `unknown@contoso.com` è stato inserito nell'indirizzo from.

Non tutti i messaggi con un tag via sono sospetti. Tuttavia, se non si riconosce un messaggio con un tag via, è consigliabile essere cauti nell'interagire con esso.

In Outlook.com e nel nuovo Outlook sul Web, è possibile posizionare il puntatore del mouse sul nome o sull'indirizzo del mittente nell'elenco dei messaggi per visualizzare l'indirizzo di posta elettronica, senza che sia necessario aprire il messaggio.

![Introduzione a OneDrive](media/get-started-with-onedrive-message.png)

Come si può sapere se si sta utilizzando il nuovo Outlook sul Web? Vedere gli esempi seguenti:

![Outlook vs Office 365](media/outlook-vs-outlook365.png)

## <a name="frequently-asked-questions"></a>Domande frequenti

### <a name="what-criteria-does-outlookcom-and-outlook-on-the-web-use-to-add-the--and-the-via-properties"></a>Quali criteri utilizza Outlook.com e Outlook sul Web per aggiungere le proprietà'?' è via '?

Per il "?" nell'immagine del mittente: Outlook.com richiede che il messaggio passi l'autenticazione SPF o DKIM. Per ulteriori informazioni, vedere [set up SPF in office 365 per impedire lo spoofing](set-up-spf-in-office-365-to-help-prevent-spoofing.md) e [utilizzare DKIM per convalidare la posta elettronica in uscita inviata dal dominio personalizzato in Office 365](use-dkim-to-validate-outbound-email.md).

Per il tag Via: se il dominio nell'indirizzo from è diverso dal dominio nella firma di DKIM o nella posta SMTP da, Outlook.com Visualizza il dominio in uno di questi due campi (preferendo la firma di DKIM).

### <a name="can-i-override-these-properties-with-ip-allows-exchange-transport-rule-allows-or-safe-senders"></a>È possibile ignorare queste proprietà con l'indirizzo IP consentito, la regola di trasporto di Exchange consente o i mittenti attendibili?

Non è possibile eseguire l'override di queste proprietà.

### <a name="how-do-i-remove-these-properties"></a>Come si rimuovono queste proprietà?

Per il "?" nell'immagine del mittente: come mittente, è necessario autenticare il messaggio con SPF o DKIM.

Per il tag Via: come mittente, è necessario assicurarsi che il dominio nella firma di DKIM o la posta SMTP sia uguale a, o sia un sottodominio di, il dominio nell'indirizzo da.

### <a name="does-outlookcom-and-outlook-on-the-web-show-this-for-every-message-that-doesnt-pass-authentication"></a>Outlook.com e Outlook sul Web mostrano questo per ogni messaggio che non passa l'autenticazione?

Non necessariamente. Outlook.com e Outlook sul Web possono avere altre proprietà all'interno del messaggio per autenticare il mittente.

## <a name="related-topics"></a>Argomenti correlati

[Proteggi il tuo account di posta elettronica di Outlook.com](https://support.office.com/article/a4f20fc5-4307-4ece-8231-6d4d4bd8a9ba)

[Gestire abusi, tentativi di phishing o spoofing in Outlook.com](https://support.office.com/article/0d882ea5-eedc-4bed-aebc-079ffa1105a3)

[Filtrare la posta indesiderata e la posta indesiderata in Outlook sul Web](https://support.office.com/article/db786e79-54e2-40cc-904f-d89d57b7f41d)
