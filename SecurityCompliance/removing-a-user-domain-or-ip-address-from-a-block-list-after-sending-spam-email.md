---
title: Rimuovere un utente, un dominio oppure un indirizzo IP da un elenco Blocca, dopo aver inviato e-mail di posta indesiderata
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 09/05/2018
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
ms.openlocfilehash: ff5bb010f45b0c89e08239f0e37885bd7ae5c7cd
ms.sourcegitcommit: 234a22c61859133ed5e7988a9551a569781518a4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2018
ms.locfileid: "23875788"
---
# <a name="removing-a-user-domain-or-ip-address-from-a-block-list-after-sending-spam-email"></a>Rimuovere un utente, un dominio oppure un indirizzo IP da un elenco Blocca, dopo aver inviato e-mail di posta indesiderata

Se un utente invia continuamente messaggi di posta elettronica da Office 365 che vengono classificati come posta indesiderata, l'invio di messaggi da tale utente verrà bloccato.  
  

Quando a un mittente viene impedito di inviare messaggi di posta elettronica, tale mittente riceve un rapporto di mancato recapito (NDR o impossibilità a inviare il messaggio) che fornisce informazioni specifiche sulla procedura da seguire per sbloccarsi.
  
Non solo ai domini di servizio, ma i siti Web specifici, possono essere bloccati singoli utenti e gli indirizzi IP possono inoltre essere bloccati. In alcuni casi, domini o siti Web possono essere aggiunti a un elenco di blocco il fatto che vengono visualizzati in un messaggio di posta indesiderata. Come amministratore di Office 365, è possibile provare a ottenere gli utenti, siti, domini e gli indirizzi IP rimossi dagli elenchi di blocco di terze parti. Utilizzare i collegamenti della tabella nella parte inferiore di questo argomento per contattare ogni terze parti e quindi seguire le istruzioni. Se qualcuno all'esterno di Office 365 non può inviare messaggi al proprio account di Office 365, il proprio account potrebbe avere è terminato nell'elenco Mittenti bloccati esterno. Gli utenti all'esterno di Office 365 possono provare a se stessi rimuovere dall'elenco dei mittenti bloccati tramite il [portale self-service di rimozione](https://technet.microsoft.com/library/mt661881%28v=exchg.150%29.aspx).
  
È possibile configurare le impostazioni di posta indesiderata in uscita in modo da ricevere una notifica quando a un utente di Office 365 viene impedito di inviare messaggi di posta elettronica classificati come posta indesiderata. Dopo aver risolto il problema relativo alla cassetta postale dell'utente, è possibile rimuovere il blocco di tale mittente.
  
## <a name="unblock-a-blocked-office-365-email-account"></a>Sbloccare un account di posta elettronica di Office 365

Completare questa attività nel centro conformità (SCC) protezione di Office 365. Per ulteriori informazioni su controllo del codice sorgente, [passare alla sicurezza di Office 365 centro conformità](go-to-the-securitycompliance-center.md) .

1. Utilizzo di un ufficio o della scuola dell'account che disponga di privilegi di amministratore globale di Office 365, accedere a Centro connessioni di Office 365 sicurezza e conformità e nell'elenco a sinistra espandere **Threat Management**, scegliere **Rivedi**e quindi fare clic su **con restrizioni Gli utenti**.
    
    > [!TIP]
    > Per passare direttamente alla pagina **Utenti con restrizioni** per la protezione &amp; centro conformità, utilizzare questo URL: >[https://protection.office.com/?hash=/restrictedusers](https://protection.office.com/?hash=/restrictedusers)

2. In questa pagina sarà incluse nell'elenco di utenti che sono stati bloccati di inviare posta elettronica esterni all'organizzazione.  Trovare l'utente che si desidera rimuovere restrizioni e quindi fare clic su **Sblocca**.

3. Fare clic su **Sì** per confermare la modifica. 
    
> [!NOTE]
> Non vi è un limite al numero di volte in cui è possibile sbloccare un account per l'amministrazione tenant. Se è stato superato il limite per un utente, viene visualizzato un messaggio di errore. È quindi necessario contattare il supporto per sbloccare l'utente. 
  
## <a name="third-party-block-lists"></a>Elenchi di blocco di terze parti

|**Nome dell'elenco **|**Portale per la rimozione dall'elenco**|**Ulteriori informazioni**|
|:-----|:-----|:-----|
|URIBL  <br/> |[https://admin.uribl.com/?section=lookup](https://admin.uribl.com/?section=lookup) <br/> |[Sito Web URIBL](https://uribl.com/) <br/> |
|SURBL  <br/> |[http://www.surbl.org/surbl-analysis](http://www.surbl.org/surbl-analysis) <br/> |[Presentazione di dati di reputazione di URI SURBL](http://www.surbl.org/) <br/> |
|Spamhaus   <br/> |[https://www.spamhaus.org/lookup/](https://www.spamhaus.org/lookup/) <br/> |[Informazioni sui filtri di DNSBLHTTP://](https://www.spamhaus.org/whitepapers/dnsbl_function/) <br/> |
|invaluement  <br/> |[http://dnsbl.invaluement.com/lookup/](http://dnsbl.invaluement.com/lookup/) <br/> |[elenco di anti elenco di protezione da posta indesiderata](http://dnsbl.invaluement.com/) <br/> |
|Phishtank  <br/> |[https://www.phishtank.com/](https://www.phishtank.com/) <br/> |[PhishTank domande frequenti](https://www.phishtank.com/faq.php) <br/> |
   
> [!NOTE]
> Exchange Online Protection utilizza anche gli elenchi di blocco di terze parti per il filtraggio della posta indesiderata. 
   
## <a name="for-more-information"></a>Ulteriori informazioni

[Configurazione del criterio delle posta indesiderata in uscita](configure-the-outbound-spam-policy.md)
  
[Pool di recapito ad alto rischio per i messaggi in uscita](high-risk-delivery-pool-for-outbound-messages.md)

[Accedere al portale di esclusione per rimuoversi dall'elenco dei mittenti bloccati di Office 365](use-the-delist-portal-to-remove-yourself-from-the-office-365-blocked-senders-lis.md)
  

  

