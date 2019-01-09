---
title: Messaggio di posta elettronica dominio non registrati
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 10/17/2018
ms.audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
description: Se si invia un volume elevato di posta elettronica dominio annullare la registrazione, si corre il rischio della posta elettronica Guida bloccato. In questo articolo per ulteriori informazioni.
ms.openlocfilehash: f632c5f7ab94a200a364828408b13c0026335869
ms.sourcegitcommit: 03e64ead7805f3dfa9149252be8606efe50375df
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/08/2019
ms.locfileid: "27769784"
---
# <a name="unregistered-domain-email-what-you-need-to-know"></a>Annullare la registrazione dominio di posta elettronica: Che cosa è necessario sapere

Office 365 consente di tenant inoltrare alcuni messaggi tramite Exchange Online Protection (EOP). Un esempio supportato è quando gli utenti dispongono di una cassetta postale di Office 365 e un utente esterno Invia messaggio di posta elettronica ma inoltro della posta è configurato in modo che torna alla cassetta postale esterno dell'utente. Si tratta più comune in ambienti education cui studenti desiderano sfruttare l'interfaccia di posta elettronica personale da dispongono comunque messaggi di posta elettronica relativi a scuola. Un altro esempio è quando i clienti sono in uno scenario ibrido e sono presenti server locale per l'invio di posta elettronica da EOP.

## <a name="problems-with-unregistered-domains"></a>Problemi con i domini non registrati

Il problema è quando i server locali vengano compromessi e finiscono con l'inoltro di un volume elevato di posta indesiderata da EOP. Nella maggior parte dei casi, vengono impostati i connettori destro ma posta venga inviata da domini di annullare la registrazione, noto anche come provisioning. Office 365 consente di posta elettronica proviene da domini non registrati ragionevole, ma deve essere configurato un dominio accettato nell'interfaccia di amministrazione per ogni dominio di che se si prevede di invio.

Una volta compromesso, tenant viene impedito l'invio dei messaggi in uscita per i domini di annullare la registrazione. Gli utenti riceveranno un mancato recapito rapporto di mancato recapito indicante:

- 550 5.7.750 servizio non disponibile. Bloccata l'invio da domini annullare la registrazione client

## <a name="unblocking-tenant-in-order-to-send-again"></a>Sblocco tenant per inviare nuovamente

Esistono diversi aspetti da eseguire se ottenere bloccato per l'invio da domini annullare la registrazione:

1. Assicurarsi di registrare tutti i domini nell'interfaccia di amministrazione di Office 365. Sono disponibili ulteriori informazioni [di seguito](https://docs.microsoft.com/en-us/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains).

2. Cercare i connettori non comune. Gli operatori dannosi spesso creano nuovi connettori in ingresso nel tenant Office 365 per inviare posta indesiderata. Sono disponibili ulteriori informazioni sull'archiviazione dei connettori di [seguito](https://docs.microsoft.com/en-us/powershell/module/exchange/mail-flow/get-inboundconnector?view=exchange-ps). 

3. Bloccare i server locali e verificare che non vengano compromesse.

> [!TIP]
> Esistono molti fattori coinvolti in questo caso, in particolare se si tratta di server di terze parti. In ogni caso, è necessario poter verificare che tutti i messaggi lasciano i server siano legittimi.

4. Al termine, è necessario chiamare il supporto Microsoft e chiederà di ottenere il tenant sbloccato per inviare nuovamente da domini di annullare la registrazione.  Fornire il codice di errore è utile, ma è necessario verificare che l'ambiente è protetta e che la posta indesiderata non verrà inviata nuovamente. Sono disponibili ulteriori informazioni sull'apertura di un caso del supporto tecnico [di seguito](https://support.office.com/en-us/article/Contact-support-for-business-products-Admin-Help-32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b#ID0EAADAAA=online).
  
## <a name="for-more-information"></a>Ulteriori informazioni

[Protezione dalla posta indesiderata in Office 365](anti-spam-protection.md)

[Rapporti di mancato recapito della posta elettronica in Office 365](https://support.office.com/article/email-non-delivery-reports-in-office-365-51daa6b9-2e35-49c4-a0c9-df85bf8533c3)

[Configurare l'inoltro della posta elettronica per una cassetta postale](https://docs.microsoft.com/en-us/exchange/recipients-in-exchange-online/manage-user-mailboxes/configure-email-forwarding)

[Come configurare un dispositivo multifunzionale o un'applicazione all'invio di posta elettronica tramite Office 365](https://support.office.com/en-us/article/How-to-set-up-a-multifunction-device-or-application-to-send-email-using-Office-365-69f58e99-c550-4274-ad18-c805d654b4c4)

[Gestisci domini accettati in Exchange Online](https://docs.microsoft.com/en-us/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains).
