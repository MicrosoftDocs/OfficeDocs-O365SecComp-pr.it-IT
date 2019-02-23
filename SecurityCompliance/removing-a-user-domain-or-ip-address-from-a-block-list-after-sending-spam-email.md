---
title: Rimuovere un utente, un dominio oppure un indirizzo IP da un elenco Blocca, dopo aver inviato e-mail di posta indesiderata
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 11/01/2018
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
ms.openlocfilehash: 3ffd8b65d6994699093237e9f9a0a3aaa802f5e2
ms.sourcegitcommit: a80bd8626720fabdf592b84e4424cd3a83d08280
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/23/2019
ms.locfileid: "30223085"
---
# <a name="removing-a-user-domain-or-ip-address-from-a-block-list-after-sending-spam-email"></a>Rimuovere un utente, un dominio oppure un indirizzo IP da un elenco Blocca, dopo aver inviato e-mail di posta indesiderata

Se un utente invia continuamente messaggi di posta elettronica da Office 365 che vengono classificati come posta indesiderata, verranno bloccati dall'invio di altri messaggi. L'utente verrà elencato nel servizio come mittente in uscita non valido e riceverà un rapporto di mancato reCapito (NDR) che dichiara:

- Non è stato possibile recapitare il messaggio perché non sono stati riconosciuti come mittenti validi. Il motivo più comune è che l'indirizzo di posta elettronica è sospettato di inviare posta indesiderata e non è più consentito l'invio di messaggi all'esterno dell'organizzazione. Contattare l'amministratore della posta elettronica per ricevere assistenza.  Il server remoto ha restituito ' 550 5.1.8 Access Denied, Bad Outbound sender '

Gli amministratori del tenant riceveranno anche un avviso che indica che l'utente è stato impedito di inviare altri messaggi in uscita.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Che cosa è necessario sapere prima di iniziare
<a name="sectionSection0"> </a>

Tempo stimato per il completamento: 5 minuti
  
Prima di poter eseguire questa procedura o procedure, è necessario disporre delle autorizzazioni assegnate. Per sapere quali autorizzazioni sono necessarie, vedere "voce di protezione da posta indesiderata nell'argomento [autorizzazioni funzionalità in Exchange Online](http://technet.microsoft.com/library/15073ce1-0917-403b-8839-02a2ebc96e16.aspx) .

La procedura seguente può essere eseguita anche tramite Remote PowerShell. Utilizzare il cmdlet Get-BlockedSenderAddress per ottenere l'elenco di utenti con restrizioni e Remove-BlockedSenderAddress per rimuovere la restrizione. Per informazioni su come utilizzare Windows PowerShell per la connessione a Exchange Online, vedere [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554).

## <a name="remove-restrictions-for-a-blocked-office-365-email-account"></a>Rimuovere le restrizioni relative a un account di posta elettronica di Office 365 bloccato

Questa attività viene completata nel centro sicurezza & Compliance (SCC) di Office 365. Per ulteriori informazioni su SCC, [passare al centro conformità di Office 365 Security &](go-to-the-securitycompliance-center.md) . Per poter eseguire queste funzioni, è necessario essere nel gruppo di ruoli **Gestione organizzazione** o **amministratore sicurezza** . Per ulteriori informazioni sui gruppi di ruoli SCC, [accedere a autorizzazioni nel centro conformità di Office 365 Security &](permissions-in-the-security-and-compliance-center.md) .

1. Utilizzando un account aziendale o dell'Istituto di istruzione con privilegi di amministratore globale di Office 365, accedere al centro sicurezza e conformità di Office 365 e, nell'elenco a sinistra, espandere **gestione minacce**, scegliere **Revisione**e quindi fare clic su **limitato. Gli utenti**.
    
    > [!TIP]
    > Per passare direttamente alla pagina **utenti con restrizioni** (in precedenza nota come centro operazioni) nel centro sicurezza &amp; e conformità, utilizzare questo URL: >[https://protection.office.com/?hash=/restrictedusers](https://protection.office.com/?hash=/restrictedusers)

2. Questa pagina contiene l'elenco di utenti bloccati dall'invio di posta all'esterno dell'organizzazione.  Individuare l'utente per il quale si desidera rimuovere le restrizioni e quindi fare clic su **Sblocca**.

3. Fare clic su **Sì** per confermare la modifica. 
    
> [!NOTE]
> Esiste un limite al numero di volte in cui un account può essere sbloccato dall'amministratore del tenant. Se il limite per un utente è stato superato, verrà visualizzato un messaggio di errore. Sarà quindi necessario contattare il supporto per sbloccare l'utente.<br/><br/> Potrebbe essere necessario fino a un'ora prima che l'utente venga sbloccato.
  
## <a name="third-party-block-lists"></a>Elenchi di blocco di terze parti

Exchange Online Protection utilizza anche elenchi di blocco di terze parti per contribuire a prendere decisioni nel filtraggio della posta indesiderata. Gli utenti, i siti Web, i domini e gli indirizzi IP possono essere aggiunti agli elenchi di blocco solo per la visualizzazione in un messaggio di posta indesiderata. Come amministratore di Office 365, è consigliabile provare a rimuovere questi oggetti dai provider di elenchi di terze parti se appartengono all'utente.

> [!NOTE]
> Se un utente esterno a Office 365 non è in grado di inviare messaggi all'account di Office 365, è possibile che l'account sia presente nell'elenco Mittenti bloccati esterni. Gli utenti esterni a Office 365 possono provare a rimuoversi usando il portale di delisting [self-service](https://docs.microsoft.com/en-us/office365/SecurityCompliance/use-the-delist-portal-to-remove-yourself-from-the-office-365-blocked-senders-lis). 

## <a name="for-more-information"></a>Ulteriori informazioni

[Risposta a un account di posta elettronica compromesso](responding-to-a-compromised-email-account.md)

[Configurare i criteri della posta indesiderata in uscita](configure-the-outbound-spam-policy.md)
  
[Pool di recapito ad alto rischio per i messaggi in uscita](high-risk-delivery-pool-for-outbound-messages.md)

[Autorizzazioni nel centro conformità & sicurezza di Office 365](permissions-in-the-security-and-compliance-center.md)

  

