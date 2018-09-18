---
title: Messaggio di posta elettronica dominio non registrati
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 09/17/2018
ms.audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
description: Se si invia un volume elevato di posta elettronica dominio annullare la registrazione, si corre il rischio della posta elettronica Guida bloccato. In questo articolo per ulteriori informazioni.
ms.openlocfilehash: f2b60f492197bf0dadb702a1c3f184c2d7e56bf1
ms.sourcegitcommit: 7b85c22fc85ec19e4b44a07e91bfa9ade768185a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/18/2018
ms.locfileid: "23998600"
---
# <a name="unregistered-domain-email-what-you-need-to-know"></a>Annullare la registrazione dominio di posta elettronica: Che cosa è necessario sapere

Office 365 consente di tenant inoltrare alcuni messaggi tramite Exchange Online Protection (EOP). Un esempio supportato è quando gli utenti dispongono di una cassetta postale di Office 365 e un utente esterno Invia messaggio di posta elettronica ma inoltro della posta è configurato in modo che torna alla cassetta postale esterno dell'utente. Si tratta più comune in ambienti education cui studenti desiderano sfruttare l'interfaccia di posta elettronica personale da dispongono comunque messaggi di posta elettronica relativi a scuola. Un altro esempio è quando i clienti sono in uno scenario ibrido e sono presenti server locali che inviano posta elettronica da EOP.

## <a name="problems-with-unregistered-domains"></a>Problemi con i domini non registrati

Il problema è quando i server locali vengano compromessi e finiscono con l'inoltro di un volume elevato di posta indesiderata da EOP. Nella maggior parte dei casi, vengono impostati i connettori destro ma posta venga inviata da domini di annullare la registrazione, noto anche come provisioning. Office 365 consente di posta elettronica proviene da domini non registrati ragionevole, ma deve essere configurato un dominio accettato nell'interfaccia di amministrazione per ogni dominio di che se si prevede di invio.

Una volta compromesso, tenant viene impedito l'invio dei messaggi in uscita per i domini di annullare la registrazione. Gli utenti riceveranno un mancato recapito rapporto di mancato recapito indicante:

- 550 5.7.750 servizio non disponibile. Bloccata l'invio da domini annullare la registrazione client

## <a name="unblocking-tenant-in-order-to-send-again"></a>Sblocco tenant per inviare nuovamente

Esistono diversi aspetti da eseguire se ottenere bloccato per l'invio da domini annullare la registrazione:

1. Assicurarsi di registrare tutti i domini nell'interfaccia di amministrazione di Office 365. Sono disponibili ulteriori informazioni [di seguito](https://docs.microsoft.com/en-us/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains).

2. Bloccare i server locali e verificare che non vengano compromesse. Esistono molti fattori coinvolti in questo caso, in particolare se si tratta di server di terze parti, ma è necessario assicurarsi che tutti i messaggi lasciano tale server sia valido.

Al termine, è necessario chiamare il supporto Microsoft e chiederà di ottenere il tenant sbloccato per inviare nuovamente da domini di annullare la registrazione.  Fornire il codice di errore è utile, ma è necessario verificare che l'ambiente è protetta e che la posta indesiderata non verrà inviata nuovamente. Sono disponibili ulteriori informazioni [di seguito](https://support.office.com/en-us/article/Contact-support-for-business-products-Admin-Help-32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b#ID0EAADAAA=online).
  
## <a name="for-more-information"></a>Ulteriori informazioni

[Protezione dalla posta indesiderata in Office 365](anti-spam-protection.md)

[Rapporti di mancato recapito di posta elettronica in Office 365](https://support.office.com/article/email-non-delivery-reports-in-office-365-51daa6b9-2e35-49c4-a0c9-df85bf8533c3)

[Configurazione dell'inoltro della posta elettronica per una cassetta postale](https://docs.microsoft.com/en-us/exchange/recipients-in-exchange-online/manage-user-mailboxes/configure-email-forwarding)

[Come configurare un dispositivo multifunzionale o un'applicazione all'invio di posta elettronica tramite Office 365](https://support.office.com/en-us/article/How-to-set-up-a-multifunction-device-or-application-to-send-email-using-Office-365-69f58e99-c550-4274-ad18-c805d654b4c4)

[Gestisci domini accettati in Exchange Online](https://docs.microsoft.com/en-us/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains).
