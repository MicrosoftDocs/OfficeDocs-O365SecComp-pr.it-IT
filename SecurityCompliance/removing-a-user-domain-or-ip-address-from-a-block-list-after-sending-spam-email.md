---
title: Rimuovere un utente, un dominio oppure un indirizzo IP da un elenco Blocca, dopo aver inviato e-mail di posta indesiderata
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 10/16/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.exch.eac.ActionCenter
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 712cfcc1-31e8-4e51-8561-b64258a8f1e5
description: "Se un utente invia continuamente messaggi di posta elettronica da Office 365 che vengono classificati come posta indesiderata, l'invio di messaggi da tale utente verrà bloccato. "
ms.openlocfilehash: 295d92fc6a1cd26783b18304a2d119d2ea0d7f1f
ms.sourcegitcommit: b164d4af65709133e0b512a4327a70fae13a974d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2018
ms.locfileid: "25577065"
---
# <a name="removing-a-user-domain-or-ip-address-from-a-block-list-after-sending-spam-email"></a>Rimuovere un utente, un dominio oppure un indirizzo IP da un elenco Blocca, dopo aver inviato e-mail di posta indesiderata

Se un utente in modo continuo invia messaggi di posta elettronica da Office 365 classificata come posta indesiderata, essi verranno bloccate di inviare messaggi più. L'utente verrà elencato nel servizio come mittente in uscita non valido e verrà visualizzato un mancato recapito rapporto di mancato recapito indicante:

- Non è stato recapitato il messaggio perché non sono state riconosciute come mittente valido. La causa più comune per l'oggetto è che l'indirizzo di posta elettronica sospetta l'invio di posta indesiderata e non ha non è più consentito inviare messaggi di fuori dell'organizzazione. Per assistenza, contattare l'amministratore di posta elettronica.  Server remoto ha restituito "550 5.1.8 accesso negato, mittente in uscita non valido"

È possibile configurare le impostazioni di criteri di posta indesiderata in uscita in modo che si riceve una notifica quando un utente di Office 365 impedito l'invio di posta elettronica. Dopo aver risolto il problema con la cassetta postale dell'utente, è possibile rimuovere il blocco di tale mittente.
  
## <a name="unblock-a-blocked-office-365-email-account"></a>Sbloccare un account di posta elettronica di Office 365

Completare questa attività nel centro conformità (SCC) protezione di Office 365. Per ulteriori informazioni su controllo del codice sorgente, [passare alla sicurezza di Office 365 centro conformità](go-to-the-securitycompliance-center.md) .

1. Utilizzo di un ufficio o della scuola dell'account che disponga di privilegi di amministratore globale di Office 365, accedere a Centro connessioni di Office 365 sicurezza e conformità e nell'elenco a sinistra espandere **Threat Management**, scegliere **Rivedi**e quindi fare clic su **con restrizioni Gli utenti**.
    
    > [!TIP]
    > Per passare direttamente alla pagina **Utenti con restrizioni** (precedentemente nota come centro) la sicurezza &amp; centro conformità, utilizzare questo URL: >[https://protection.office.com/?hash=/restrictedusers](https://protection.office.com/?hash=/restrictedusers)

2. In questa pagina sarà incluse nell'elenco di utenti che sono stati bloccati di inviare posta elettronica esterni all'organizzazione.  Trovare l'utente che si desidera rimuovere restrizioni e quindi fare clic su **Sblocca**.

3. Fare clic su **Sì** per confermare la modifica. 
    
> [!NOTE]
> Non vi è un limite al numero di volte in cui è possibile sbloccare un account per l'amministrazione tenant. Se è stato superato il limite per un utente, viene visualizzato un messaggio di errore. È quindi necessario contattare il supporto per sbloccare l'utente.
  
## <a name="third-party-block-lists"></a>Elenchi di blocco di terze parti

Exchange Online Protection utilizza anche gli elenchi di blocco di terze parti per prendere decisioni nel filtro posta indesiderata. Gli utenti, siti, domini e gli indirizzi IP possono aggiunti da bloccare elenchi solo per la visualizzazione in un messaggio di posta indesiderata. Come amministratore di Office 365, è consigliabile ottenere questi oggetti rimossi i provider dell'elenco di terze parti se appartengono a un utente.

> [!NOTE]
> Se qualcuno all'esterno di Office 365 non può inviare messaggi al proprio account di Office 365, potrebbe essere il proprio account nell'elenco Mittenti bloccati esterni. Gli utenti all'esterno di Office 365 è possono provare a rimuovere se stessi mediante il [portale self-service di rimozione](https://docs.microsoft.com/en-us/office365/SecurityCompliance/use-the-delist-portal-to-remove-yourself-from-the-office-365-blocked-senders-lis). 

## <a name="for-more-information"></a>Per altre informazioni

[Rispondere a un account di posta elettronica compromesso](responding-to-a-compromised-email-account.md)

[Configurare i criteri della posta indesiderata in uscita](configure-the-outbound-spam-policy.md)
  
[Pool di recapito ad alto rischio per i messaggi in uscita](high-risk-delivery-pool-for-outbound-messages.md)

  

  

