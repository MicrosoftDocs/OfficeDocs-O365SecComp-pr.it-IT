---
title: Messaggio di posta elettronica di dominio non registrato
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 10/17/2018
ms.audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
description: Se si invia un volume elevato di posta elettronica di dominio non registrato, si rischia che la posta elettronica venga bloccata. Leggere questo articolo per ulteriori informazioni.
ms.openlocfilehash: bef39780438a6d9669354bddaed391b2364badf8
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/23/2019
ms.locfileid: "30220776"
---
# <a name="unregistered-domain-email-what-you-need-to-know"></a>Messaggio di posta elettronica di dominio non registrato: informazioni utili

Office 365 consente ai tenant di inoltrare alcuni messaggi tramite Exchange Online Protection (EOP). Un esempio supportato potrebbe essere quello in cui gli utenti dispongono di una cassetta postale di Office 365 e un utente esterno invia loro la posta elettronica, ma l'inoltro della posta elettronica è configurato in modo che rientri nella cassetta postale esterna dell'utente. Questo è il più comune negli ambienti scolastici in cui gli studenti desiderano sfruttare la propria interfaccia di posta elettronica personale, ma continuano a ricevere messaggi di posta elettronica correlati alla scuola. Un altro esempio è quando i clienti sono in uno scenario ibrido e dispongono di server locali che inviano messaggi di posta elettronica da EOP.

## <a name="problems-with-unregistered-domains"></a>Problemi relativi ai domini non registrati

Il problema è quando i server locali vengono compromessi e finiscono con l'inoltro di un volume elevato di posta indesiderata fuori EOP. In quasi tutti i casi, i connettori giusti sono configurati, ma il messaggio di posta elettronica viene inviato dall'annullamento della registrazione, noto anche come Unprovisioned, Domains. Office 365 consente una quantità ragionevole di messaggi di posta elettronica provenienti da domini non registrati, ma un dominio accettato deve essere configurato nell'interfaccia di amministrazione per ogni dominio in cui si intende inviare.

Una volta compromesso, ai tenant verrà impedito di inviare la posta in uscita per i domini non registrati. Gli utenti riceveranno un rapporto di mancato reCapito (NDR) che indica quanto segue:

- 550 servizio 5.7.750 non disponibile. Client bloccato dall'invio di domini non registrati

## <a name="unblocking-tenant-in-order-to-send-again"></a>Sblocco del tenant per l'invio di nuovo

È necessario eseguire diverse operazioni se si viene bloccati per l'invio da domini non registrati:

1. Assicurarsi di registrare tutti i domini nell'interfaccia di amministrazione di Office 365. Ulteriori informazioni sono disponibili [qui](https://docs.microsoft.com/en-us/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains).

2. Cercare connettori inusuali. Gli attori maligni spesso creano nuovi connettori in ingresso nel tenant di Office 365 per inviare la posta indesiderata. Ulteriori informazioni su come controllare i connettori sono disponibili [qui](https://docs.microsoft.com/en-us/powershell/module/exchange/mail-flow/get-inboundconnector?view=exchange-ps). 

3. Bloccare i server locali e assicurarsi che non vengano compromessi.

> [!TIP]
> Vi sono numerosi fattori coinvolti in questo articolo, soprattutto se si tratta di server di terze parti. Indipendentemente da ciò, è necessario essere in grado di confermare che tutti i messaggi che lasciano i server siano legittimi.

4. Dopo aver completato l'operazione, è necessario chiamare il supporto tecnico Microsoft e chiedere di ottenere il tenant sbloccato per inviare di nuovo i domini non registrati.  Fornire il codice di errore è utile, ma sarà necessario dimostrare che l'ambiente è protetto e che la posta indesiderata non verrà più inviata. Ulteriori informazioni sull'apertura di un caso di supporto sono disponibili [qui](https://support.office.com/en-us/article/Contact-support-for-business-products-Admin-Help-32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b#ID0EAADAAA=online).
  
## <a name="for-more-information"></a>Ulteriori informazioni

[Protezione dalla posta indesiderata in Office 365](anti-spam-protection.md)

[Rapporti di mancato recapito della posta elettronica in Office 365](https://support.office.com/article/email-non-delivery-reports-in-office-365-51daa6b9-2e35-49c4-a0c9-df85bf8533c3)

[Configurare l'inoltro della posta elettronica per una cassetta postale](https://docs.microsoft.com/en-us/exchange/recipients-in-exchange-online/manage-user-mailboxes/configure-email-forwarding)

[Come configurare un dispositivo multifunzionale o un'applicazione all'invio di posta elettronica tramite Office 365](https://support.office.com/en-us/article/How-to-set-up-a-multifunction-device-or-application-to-send-email-using-Office-365-69f58e99-c550-4274-ad18-c805d654b4c4)

[Gestire i domini accettati in Exchange Online](https://docs.microsoft.com/en-us/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains).
