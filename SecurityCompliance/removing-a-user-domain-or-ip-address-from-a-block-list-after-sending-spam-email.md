---
title: Rimuovere un utente, un dominio oppure un indirizzo IP da un elenco Blocca, dopo aver inviato e-mail di posta indesiderata
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 6/20/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.exch.eac.ActionCenter
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
ms.assetid: 712cfcc1-31e8-4e51-8561-b64258a8f1e5
description: "Se un utente invia continuamente messaggi di posta elettronica da Office 365 che vengono classificati come posta indesiderata, l'invio di messaggi da tale utente verrà bloccato. "
ms.openlocfilehash: ce52ddfd96b582911bb519c15bbfe90351946db8
ms.sourcegitcommit: 22bca85c3c6d946083d3784f72e886c068d49f4a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/06/2018
ms.locfileid: "22026333"
---
# <a name="removing-a-user-domain-or-ip-address-from-a-block-list-after-sending-spam-email"></a>Rimuovere un utente, un dominio oppure un indirizzo IP da un elenco Blocca, dopo aver inviato e-mail di posta indesiderata

Se un utente invia continuamente messaggi di posta elettronica da Office 365 che vengono classificati come posta indesiderata, l'invio di messaggi da tale utente verrà bloccato.  
  

Quando a un mittente viene impedito di inviare messaggi di posta elettronica, tale mittente riceve un rapporto di mancato recapito (NDR o impossibilità a inviare il messaggio) che fornisce informazioni specifiche sulla procedura da seguire per sbloccarsi.
  
Non solo ai domini di servizio, ma i siti Web specifici, possono essere bloccati singoli utenti e gli indirizzi IP possono inoltre essere bloccati. In alcuni casi, domini o siti Web possono essere aggiunti a un elenco di blocco il fatto che vengono visualizzati in un messaggio di posta indesiderata. Come amministratore di Office 365, è possibile provare a ottenere gli utenti, siti, domini e gli indirizzi IP rimossi dagli elenchi di blocco di terze parti. Utilizzare i collegamenti della tabella nella parte inferiore di questo argomento per contattare ogni terze parti e quindi seguire le istruzioni. Se qualcuno all'esterno di Office 365 non può inviare messaggi al proprio account di Office 365, il proprio account potrebbe avere è terminato nell'elenco Mittenti bloccati esterno. Gli utenti all'esterno di Office 365 possono provare a se stessi rimuovere dall'elenco dei mittenti bloccati tramite il [portale self-service di rimozione](https://technet.microsoft.com/library/mt661881%28v=exchg.150%29.aspx).
  
È possibile configurare le impostazioni di posta indesiderata in uscita in modo da ricevere una notifica quando a un utente di Office 365 viene impedito di inviare messaggi di posta elettronica classificati come posta indesiderata. Dopo aver risolto il problema relativo alla cassetta postale dell'utente, è possibile rimuovere il blocco di tale mittente.
  
## <a name="unblock-a-blocked-office-365-email-account"></a>Sbloccare un account di posta elettronica di Office 365

Completare questa attività nell'interfaccia di amministrazione di Exchange (EAC). Vedere [Exchange admin center in Exchange Online Protection](exchange-admin-center-in-exchange-online-protection-eop.md) per informazioni dettagliate sui EAC. 
  
> [!NOTE]
> A meno che non si è all'interno di EAC per Exchange Online, non verrà visualizzato alcun centro notifiche. 
  
1. In EAC, accedere a **protezione** \> **Centro**.
    
    ![Passare al centro notifiche nell'interfaccia di amministrazione di Exchange](media/9bbf0844-7b34-4a86-a2b7-8c7e9c8519a3.png)
  
2. Selezionare l'icona **Cerca** e immettere l'indirizzo SMTP dell'utente bloccato. 
    
    ![Ricerca di un utente bloccato nel centro notifiche](media/f931b5a0-7115-4d95-9f6f-b403436031ba.png)
  
3. Fare clic su **Sblocca account** nel riquadro Descrizione. 
    
    ![Sblocco di un utente nel centro notifiche](media/c5d5b1b9-8416-45aa-9631-881e94d1d056.png)
  
4. Fare clic su **Sì** per confermare la modifica. 
    
> [!NOTE]
> Esiste un limite per il numero di volte in cui un account può essere sbloccato dall'amministratore del tenant. Se tale limite è stato superato per un utente, viene visualizzato un messaggio di errore. Contattare il supporto per sbloccare l'utente. 
  
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

[Configurare i criteri di posta indesiderata in uscita](configure-the-outbound-spam-policy.md)
  
[Pool di recapito ad alto rischio per i messaggi in uscita](high-risk-delivery-pool-for-outbound-messages.md)

[Accedere al portale di esclusione per rimuoversi dall'elenco dei mittenti bloccati di Office 365](use-the-delist-portal-to-remove-yourself-from-the-office-365-blocked-senders-lis.md)
  

  

