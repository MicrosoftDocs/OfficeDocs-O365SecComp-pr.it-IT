---
title: Rimozione di un utente dal portale degli utenti con restrizioni dopo l'invio di posta indesiderata
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.date: 03/12/2019
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.exch.eac.ActionCenter.Restricted.Users.RestrictedUsers
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 712cfcc1-31e8-4e51-8561-b64258a8f1e5
ms.collection:
- M365-security-compliance
description: Se un utente invia continuamente messaggi di posta elettronica provenienti da Office 365 classificati come posta indesiderata, non invierà più messaggi.
ms.openlocfilehash: 61d52ad1f25dc3767ad51da5b3a217ace59303ce
ms.sourcegitcommit: 9918411c01e962d5c67d53dd30a8a9c28c547397
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2019
ms.locfileid: "30654553"
---
# <a name="removing-a-user-from-the-restricted-users-portal-after-sending-spam-email"></a>Rimozione di un utente dal portale degli utenti con restrizioni dopo l'invio di posta indesiderata

Se un utente invia continuamente messaggi di posta elettronica provenienti da Office 365 classificati come posta indesiderata, non invierà più messaggi in uscita. L'utente verrà elencato nel servizio come mittente in uscita non valido e riceverà un rapporto di mancato reCapito (NDR) che dichiara:

- Non è stato possibile recapitare il messaggio perché non sono stati riconosciuti come mittenti validi. Il motivo più comune è che l'indirizzo di posta elettronica è sospettato di inviare posta indesiderata e non è più consentito l'invio di messaggi all'esterno dell'organizzazione. Contattare l'amministratore della posta elettronica per ricevere assistenza. Il server remoto ha restituito ' 550 5.1.8 Access Denied, Bad Outbound sender '

## <a name="what-do-you-need-to-know-before-you-begin"></a>Informazioni preliminari
<a name="sectionSection0"> </a>

Tempo stimato per il completamento: 5 minuti
  
Per eseguire queste procedure, è necessario disporre delle autorizzazioni appropriate. Per sapere quali autorizzazioni sono necessarie, vedere "voce di protezione da posta indesiderata nell'argomento [autorizzazioni funzionalità in Exchange Online](http://technet.microsoft.com/library/15073ce1-0917-403b-8839-02a2ebc96e16.aspx) .

La seguente procedura può essere eseguita anche tramite PowerShell remota. Utilizzare il cmdlet Get-BlockedSenderAddress per ottenere l'elenco di utenti con restrizioni e Remove-BlockedSenderAddress per rimuovere la restrizione. Per informazioni su come usare Windows PowerShell per connettersi a Exchange Online, vedere [Connessione a Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554).

## <a name="remove-restrictions-for-a-blocked-office-365-email-account"></a>Rimuovere le restrizioni relative a un account di posta elettronica di Office 365 bloccato

Questa attività viene completata nel centro sicurezza & Compliance (SCC) di Office 365. Per ulteriori informazioni su SCC, [passare al centro conformità di Office 365 Security &](go-to-the-securitycompliance-center.md) . Per poter eseguire queste funzioni, è necessario essere nel gruppo di ruoli **Gestione organizzazione** o **amministratore sicurezza** . Per ulteriori informazioni sui gruppi di ruoli SCC, [accedere a autorizzazioni nel centro conformità di Office 365 Security &](permissions-in-the-security-and-compliance-center.md) .

1. Utilizzando un account aziendale o dell'Istituto di istruzione con privilegi di amministratore globale di Office 365, accedere al centro sicurezza e conformità di Office 365 e, nell'elenco a sinistra, espandere **gestione minacce**, scegliere **Revisione**e quindi fare clic su **limitato. Gli utenti**.
    
    > [!TIP]
    > Per passare direttamente alla pagina **utenti con restrizioni** (in precedenza nota come centro operazioni) nel centro sicurezza &amp; e conformità, utilizzare questo URL: >[https://protection.office.com/#/restrictedusers](https://protection.office.com/?hash=/restrictedusers)

2. Questa pagina contiene l'elenco di utenti bloccati dall'invio di posta all'esterno dell'organizzazione.  Individuare l'utente per il quale si desidera rimuovere le restrizioni e quindi fare clic su **Sblocca**.

3. Un fly-out entrerà nei dettagli relativi all'account di cui è riservata l'invio. È consigliabile eseguire le procedure consigliate per assicurarsi di prendere le azioni appropriate nel caso in cui l'account sia effettivamente compromesso. Fare clic su **Avanti** al termine.

4. Nella schermata successiva sono disponibili suggerimenti che consentono di evitare futuri compromessi. L'abilitazione dell'autenticazione a più fattori (AMF) e la modifica delle password sono una buona difesa. Fare clic su **Sblocca utente** al termine.

5. Fare clic su **Sì** per confermare la modifica.

    > [!NOTE]
    > Potrebbero essere necessari fino a 30 minuti prima che vengano rimosse le restrizioni. 

## <a name="making-sure-admins-are-alerted-when-this-happens"></a>Verificare che gli amministratori siano avvisati quando questo accade

Gli amministratori del tenant riceveranno anche un avviso che indica che l'utente è stato impedito di inviare altri messaggi in uscita. Si tratta di un avviso predefinito fornito per tutti i tenant ed è elencato nella pagina Criteri di avviso di SCC, intitolata "utente con restrizioni dall'invio di messaggi di posta elettronica". Andare a [criteri di avviso nel centro conformità di Office 365 Security &](https://docs.microsoft.com/en-us/office365/securitycompliance/alert-policies) per ulteriori informazioni sull'avviso.

## <a name="for-more-information"></a>Ulteriori informazioni

[Risposta a un account di posta elettronica compromesso](responding-to-a-compromised-email-account.md)

[Informazioni sull'utente con restrizioni dall'invio di messaggi di avviso tramite posta elettronica](https://docs.microsoft.com/en-us/office365/securitycompliance/alert-policies)

[Pool di recapito ad alto rischio per i messaggi in uscita](high-risk-delivery-pool-for-outbound-messages.md)

[Autorizzazioni nel centro conformità & sicurezza di Office 365](permissions-in-the-security-and-compliance-center.md)
