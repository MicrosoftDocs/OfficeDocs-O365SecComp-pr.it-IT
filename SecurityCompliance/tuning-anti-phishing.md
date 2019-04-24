---
title: Ottimizzare la protezione anti-phishing in Office 365
ms.author: chrisda
author: chrisda
manager: serdars
ms.date: ''
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
description: Gli amministratori possono imparare a identificare i motivi per cui e come è stato ottenuto un messaggio di phishing e cosa fare per evitare ulteriori messaggi di phishing in futuro.
ms.openlocfilehash: c3025267ad8e01c18de618c85127dfe1077a16aa
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "32264318"
---
# <a name="tune-anti-phishing-protection-in-office-365"></a>Ottimizzare la protezione anti-phishing in Office 365

Anche se Office 365 viene fornito con una vasta gamma di funzionalità di anti-phishing abilitate per impostazione predefinita, è possibile che alcuni messaggi di phishing possano continuare a passare alle cassette postali. In questo argomento vengono descritte le operazioni che è possibile eseguire per individuare il motivo per cui è stato effettuato un messaggio di phishing e cosa è possibile fare per modificare le impostazioni di anti-phishing nell'organizzazione di Exchange Online _senza peggiorare le cose_.

## <a name="first-things-first-deal-with-any-compromised-accounts-and-make-sure-you-block-any-more-phishing-messages-from-getting-through"></a>First Things First: Deal with any compromised accounts e assicuratevi di bloccare altri messaggi di phishing dall'ottenere

Se l'account di un destinatario è stato compromesso a causa del messaggio di phishing, seguire la procedura descritta in [risposta a un account di posta elettronica compromesso in Office 365](responding-to-a-compromised-email-account.md).

Se l'abbonamento include Advanced Threat Protection (ATP), è possibile utilizzare [Office 365 Threat Intelligence](office-365-ti.md) per identificare gli altri utenti che hanno ricevuto anche il messaggio di phishing. Sono disponibili altre opzioni per bloccare i messaggi di phishing:

- [Collegamenti sicuri di ATP](set-up-atp-safe-links-policies.md)

- [Allegati sicuri di ATP](set-up-atp-safe-attachments-policies.md)

- [Criteri di anti-phishing ATP](set-up-anti-phishing-policies.md). Si noti che è possibile aumentare temporaneamente le soglie di **phishing avanzate** nel criterio da **standard** a **aggressivo**, **più aggressivo**o **più aggressivo**.

Verificare che queste funzionalità ATP siano attivate.

## <a name="report-the-phishing-message-to-microsoft"></a>Segnalare il messaggio di phishing a Microsoft

La segnalazione dei messaggi di phishing è utile per ottimizzare i filtri utilizzati per proteggere tutti i clienti in Office 365.

Inviare il messaggio di phishing _come allegato_ in un nuovo messaggio, altrimenti vuoto, in **Phish@office365.microsoft.com**. Non solo inoltrare il messaggio originale; in caso contrario, non è possibile esaminare le intestazioni del messaggio originale. In alternativa, è possibile utilizzare il componente aggiuntivo [segnala messaggio](https://docs.microsoft.com/office365/securitycompliance/enable-the-report-message-add-in) in Outlook o Outlook sul Web (in precedenza noto come Outlook Web App).

Per ulteriori informazioni, vedere [Invio di messaggi di posta indesiderata e non e tentativi di phishing a Microsoft per l'analisi](submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis.md).

## <a name="inspect-the-message-headers"></a>Esaminare le intestazioni del messaggio

È possibile esaminare le intestazioni del messaggio di phishing per vedere se c'è qualcosa che può essere fatto personalmente per evitare che vengano inviati più messaggi di phishing. In altre parole, l'esame delle intestazioni dei messaggi può essere utile per identificare le impostazioni dell'organizzazione responsabili dell'autorizzazione dei messaggi di phishing.

In particolare, è necessario controllare il campo di intestazione **X-Forefront-antispam-report** nelle intestazioni del messaggio per le indicazioni relative alla posta indesiderata o al filtro di phishing nel valore del parametro di filtro posta indesiderata (SFV). I messaggi che ignorano il filtro avranno una `SCL:-1`voce di, il che significa che una delle impostazioni ha consentito questo messaggio tramite l'override dei verdetti di posta indesiderata o phishing che sono stati determinati dal servizio. Per ulteriori informazioni su come ottenere le intestazioni del messaggio e l'elenco completo di tutte le intestazioni dei messaggi di protezione da posta indesiderata e anti-phishing disponibili, vedere intestazioni di messaggi di protezione da [posta](https://docs.microsoft.com/office365/SecurityCompliance/anti-spam-message-headers)indesiderata.

## <a name="best-practices-to-stay-protected"></a>Procedure consigliate per mantenere la protezione

- Su base mensile, eseguire [office 365 Secure Score](office-365-secure-score.md) per valutare le impostazioni di sicurezza dell'organizzazione di Office 365.

- Esaminare periodicamente il [report di intelligence di spoofing](learn-about-spoof-intelligence.md) e [abilitare la protezione anti-spoofing nei criteri anti-phishing](learn-about-spoof-intelligence.md#configuring-the-anti-spoofing-policy) per mettere in **quarantena** i messaggi sospetti anziché reCapitarli nella cartella posta indesiderata dell'utente.

- Esaminare periodicamente il [rapporto sullo stato della protezione dalle minacce](view-reports-for-atp.md#threat-protection-status-report).

- Alcuni clienti consentono inavvertitamente di inviare messaggi di phishing inserendo i propri domini nell'elenco Consenti mittente o Consenti dominio nei criteri di protezione da posta indesiderata. Se si sceglie di eseguire questa operazione, è necessario utilizzare estrema cautela. Anche se questa configurazione consentirà alcuni messaggi legittimi tramite, consentirà anche messaggi dannosi che verrebbero normalmente bloccati dai filtri di posta indesiderata e/o di phishing di Office 365.

  Il modo migliore per gestire i messaggi legittimi bloccati da Office 365 (falsi positivi) che coinvolgono i mittenti nel dominio consiste nel configurare completamente e completamente i record SPF, DKIM e DMARC in DNS per _tutti_ i domini di posta elettronica in Office 365:

  - Verificare che il record SPF identifichi _tutte le_ origini della posta elettronica per i mittenti del dominio (non dimenticare i servizi di terze parti).

  - Utilizzare il fail duro\-() per garantire che i mittenti non autorizzati vengano rifiutati dai sistemi di posta elettronica configurati per tale operazione. È possibile utilizzare l' [Intelligence spoof](https://docs.microsoft.com/office365/securitycompliance/learn-about-spoof-intelligence) per identificare i mittenti che utilizzano il dominio in modo che sia possibile includere mittenti di terze parti autorizzati nel record SPF.

  Per istruzioni sulla configurazione, vedere:
  
  - [Configurazione di SPF in Office 365 per evitare lo spoofing](set-up-spf-in-office-365-to-help-prevent-spoofing.md)

  - [Utilizzare DKIM per convalidare la posta elettronica in uscita inviata dal dominio personalizzato in Office 365](use-dkim-to-validate-outbound-email.md)

  - [Utilizzo di DMARC per convalidare la posta elettronica in Office 365](use-dmarc-to-validate-email.md)

- Quando possibile, è consigliabile recapitare la posta elettronica per il dominio direttamente a Office 365. In altre parole, puntare il record MX del dominio di Office 365 a Office 365. Exchange Online Protection (EOP) è in grado di fornire la migliore protezione per gli utenti del cloud quando la posta viene recapitata direttamente a Office 365. Se è necessario utilizzare un sistema di posta elettronica di terze parti di fronte a EOP, assicurarsi di aver seguito le indicazioni [qui](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-mail-flow-using-third-party-cloud).

- L'autenticazione a più fattori è un ottimo modo per impedire gli account compromessi. È consigliabile prendere in considerazione l'abilitazione dell'AMF per tutti gli utenti. Per un approccio graduale, iniziare abilitando l'AMF per gli utenti più sensibili (amministratori, dirigenti e così via) prima di abilitare l'AMF per tutti. Per istruzioni, vedere [configurare l'autenticazione](https://docs.microsoft.com/office365/admin/security-and-compliance/set-up-multi-factor-authentication)a più fattori.

- Le regole di inoltro ai destinatari esterni vengono spesso utilizzate dagli utenti malintenzionati per estrarre i dati. Utilizzare le informazioni sulla **revisione delle regole di inoltro delle cassette postali** in [Office 365 Secure Score](office-365-secure-score.md) per individuare e persino impedire l'inoltro delle regole ai destinatari esterni. Per ulteriori informazioni, vedere [attenuaZione delle regole di inoltro esterno client con Secure Score](https://blogs.technet.microsoft.com/office365security/mitigating-client-external-forwarding-rules-with-secure-score/).
