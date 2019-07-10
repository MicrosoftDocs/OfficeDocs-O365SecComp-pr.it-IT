---
title: Mittente non verificato
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 04/25/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: Per impedire ai messaggi di phishing di raggiungere la propria cassetta postale, Outlook.com e Outlook sul Web verificano che il mittente sia quello che dicono di essere e contrassegnare i messaggi sospetti come posta indesiderata.
ms.openlocfilehash: a69af1efb634e1805f055d49ec5515f4b4252c3b
ms.sourcegitcommit: 32ecff689ae32c59a39b7633ca0f36a304e7516e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/09/2019
ms.locfileid: "35600262"
---
# <a name="unverified-sender"></a>Mittente non verificato

Per impedire ai messaggi di phishing di raggiungere la propria cassetta postale, Outlook.com e Outlook sul Web verificano che il mittente sia quello che dicono di essere e contrassegnare i messaggi sospetti come posta indesiderata.

> [!IMPORTANT]
> Quando un messaggio viene contrassegnato come truffa di phishing, Outlook.com e Outlook sul Web visualizzano un avviso nella parte superiore della pagina, ma qualsiasi collegamento nel messaggio può ancora essere aperto.

## <a name="how-can-i-identify-a-suspicious-message-in-my-inbox"></a>Come è possibile identificare un messaggio sospetto nella cartella posta in arrivo?

Outlook.com e Outlook sul Web mostrano gli indicatori quando il mittente di un messaggio non può essere identificato o la loro identità è diversa da quella visualizzata nell'indirizzo da.

## <a name="how-to-manage-which-messages-receive-the-unverified-sender-treatment"></a>Come gestire i messaggi che ricevono il trattamento dei mittenti non verificati 

Se si è un cliente di Office 365, è possibile gestire questa funzionalità tramite il Centro sicurezza & Compliance. 

- Nel centro sicurezza & conformità di Office 365, gli amministratori tenant possono attivarla o disattivarla tramite la protezione anti-spoofing in base ai criteri phishing. Inoltre, può essere gestito tramite il cmdlet ' set-AntiPhishPolicy '. Per ulteriori informazioni, vedere protezione anti-phishing in Office 365 e set-AntiPhishPolicy.

    ![Modifica dei mittenti non autenticati nell'interfaccia grafica.](media/unverified-sender-article-editing-unauthenticated-senders.jpg)

- Se un amministratore ha identificato un falso positivo e un mittente non deve ricevere il trattamento del mittente non verificato, è possibile eseguire una delle azioni seguenti per aggiungere il mittente all'elenco Consenti spoof di spoofing Intelligence:
        
    - Aggiungere la coppia di domini tramite lo spoofing Intelligence Insight. Per ulteriori informazioni, vedere Procedura dettagliata: spoofing Intelligence Insight
                
    - Aggiungere la coppia di domini tramite il cmdlet PhishFilterPolicy. Per ulteriori informazioni, vedere Set-PhishFilterPolicy e anti-spoofing Protection in Office 365

Inoltre, non viene applicato il trattamento del mittente non verificato se è stato recapitato nella posta in arrivo tramite un elenco di indirizzi consentiti, incluse le regole di trasporto della posta elettronica (ETRs), l'elenco dei domini attendibili (criterio di protezione dalla posta indesiderata), l'elenco dei mittenti attendibili o un utente che ha impostato questo utente come "mittente sicuro" posta in arrivo.

### <a name="you-see-a--in-the-sender-image"></a>Viene visualizzato un'?' nell'immagine del mittente

Quando Outlook.com e Outlook sul Web non sono in grado di verificare l'identità del mittente utilizzando le tecniche di autenticazione della posta elettronica, visualizzano una '?' nella foto del mittente. 

![Il messaggio non ha superato la verifica](media/message-did-not-pass-verification.jpg)

Non tutti i messaggi che non sono in grado di eseguire l'autenticazione sono dannosi. Tuttavia, è necessario prestare particolare attenzione all'interazione con i messaggi che non eseguono l'autenticazione se non si riconosce il mittente. In alternativa, se si riconosce un mittente che in genere non ha un'?' nell'immagine del mittente, ma si inizia improvvisamente a vederlo, potrebbe essere un segno che il mittente viene falsificato.

## <a name="frequently-asked-questions"></a>Domande frequenti

### <a name="what-criteria-does-outlookcom-and-outlook-on-the-web-use-to-add-the--and-the-via-properties"></a>Quali criteri utilizza Outlook.com e Outlook sul Web per aggiungere le proprietà'?' è via '?

Per il "?" nell'immagine del mittente: Outlook.com richiede che il messaggio passi l'autenticazione SPF o DKIM. Per ulteriori informazioni, vedere [set up SPF in office 365 per impedire lo spoofing](set-up-spf-in-office-365-to-help-prevent-spoofing.md) e [utilizzare DKIM per convalidare la posta elettronica in uscita inviata dal dominio personalizzato in Office 365](use-dkim-to-validate-outbound-email.md).

Per il tag Via: se il dominio nell'indirizzo from è diverso dal dominio nella firma di DKIM o nella posta SMTP da, Outlook.com Visualizza il dominio in uno di questi due campi (preferendo la firma di DKIM).

### <a name="how-do-i-remove-the-"></a>Come si rimuove il '?'

Per il "?" nell'immagine del mittente: come mittente, è necessario autenticare il messaggio con SPF o DKIM.

Per il tag Via: come mittente, è necessario assicurarsi che il dominio nella firma di DKIM o la posta SMTP sia uguale a, o sia un sottodominio di, il dominio nell'indirizzo da.

### <a name="does-outlookcom-and-outlook-on-the-web-show-this-for-every-message-that-doesnt-pass-authentication"></a>Outlook.com e Outlook sul Web mostrano questo per ogni messaggio che non passa l'autenticazione?

Non necessariamente. Outlook.com e Outlook sul Web possono avere altre proprietà all'interno del messaggio per autenticare il mittente.

## <a name="related-topics"></a>Argomenti correlati

[Proteggi il tuo account di posta elettronica di Outlook.com](https://support.office.com/article/a4f20fc5-4307-4ece-8231-6d4d4bd8a9ba)

[Gestire abusi, tentativi di phishing o spoofing in Outlook.com](https://support.office.com/article/0d882ea5-eedc-4bed-aebc-079ffa1105a3)

[Filtrare la posta indesiderata e la posta indesiderata in Outlook sul Web](https://support.office.com/article/db786e79-54e2-40cc-904f-d89d57b7f41d)
