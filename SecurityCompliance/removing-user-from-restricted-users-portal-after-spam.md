---
title: Rimozione di un utente dal portale Utenti con restrizioni dopo l'invio di posta indesiderata
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 07/10/2019
audience: ITPro
ms.topic: article
f1_keywords:
- ms.exch.eac.ActionCenter.Restricted.Users.RestrictedUsers
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 712cfcc1-31e8-4e51-8561-b64258a8f1e5
ms.collection:
- M365-security-compliance
description: Se un utente invia continuamente messaggi di posta elettronica provenienti da Office 365 classificati come posta indesiderata, non invierà più messaggi.
ms.openlocfilehash: 40d63bb452392041401fd1af6d0d6d4af67e5d2b
ms.sourcegitcommit: 986f40a00ab454093b21e724d58594b8b8b4a9ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "35613654"
---
# <a name="removing-a-user-from-the-restricted-users-portal-after-sending-spam-email"></a>Rimozione di un utente dal portale Utenti con restrizioni dopo l'invio di posta indesiderata

Se un utente invia continuamente messaggi di posta elettronica che vengono classificati come messaggi indesiderati provenienti da Office 365, saranno limitati dall'invio di messaggi di posta elettronica, ma saranno comunque in grado di riceverlo. L'utente verrà elencato nel servizio come mittente in uscita non valido e riceverà un rapporto di mancato recapito (NDR) che dichiara:

> "Non è stato possibile recapitare il messaggio perché non sono stati riconosciuti come mittenti validi. Il motivo più comune di questo è che l'indirizzo di posta elettronica è sospettato di inviare posta indesiderata e non è più consentito l'invio di posta elettronica.  Contattare l'amministratore della posta elettronica per ricevere assistenza. Il server remoto ha restituito "550 5.1.8 Access Denied, Bad Outbound sender".

## <a name="what-do-you-need-to-know-before-you-begin"></a>Che cosa è necessario sapere prima di iniziare
<a name="sectionSection0"> </a>

Tempo stimato per il completamento: 5 minuti
  
Per eseguire queste procedure, è necessario disporre delle autorizzazioni appropriate. Per sapere quali autorizzazioni sono necessarie, vedere "voce di protezione da posta indesiderata nell'argomento [autorizzazioni funzionalità in Exchange Online](http://technet.microsoft.com/library/15073ce1-0917-403b-8839-02a2ebc96e16.aspx) .

La seguente procedura può essere eseguita anche tramite PowerShell remota. Utilizzare il cmdlet Get-BlockedSenderAddress per ottenere l'elenco di utenti con restrizioni e Remove-BlockedSenderAddress per rimuovere la restrizione. Per informazioni su come usare Windows PowerShell per connettersi a Exchange Online, vedere [Connessione a Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554).

## <a name="remove-restrictions-for-a-blocked-office-365-email-account"></a>Rimuovere le restrizioni relative a un account di posta elettronica di Office 365 bloccato

Questa attività viene completata nel centro sicurezza & Compliance (SCC). Per ulteriori informazioni su SCC, [visitare il Centro sicurezza & Compliance](go-to-the-securitycompliance-center.md) . Per poter eseguire queste funzioni, è necessario essere nel gruppo di ruoli **Gestione organizzazione** o **amministratore sicurezza** . Per ulteriori informazioni sui gruppi di ruoli SCC, [accedere a autorizzazioni nel centro sicurezza & Compliance](permissions-in-the-security-and-compliance-center.md) .

1. Utilizzando un account aziendale o dell'Istituto di istruzione con privilegi di amministratore globale di Office 365, accedere al centro sicurezza e conformità di Office 365 e, nell'elenco a sinistra, espandere **gestione minacce**, scegliere **Revisione**e quindi fare clic su **limitato. Gli utenti**.
    
    > [!TIP]
    > Per passare direttamente alla pagina **utenti con restrizioni** (in precedenza nota come centro operazioni) nel centro sicurezza &amp; e conformità, utilizzare questo URL: >[https://protection.office.com/#/restrictedusers](https://protection.office.com/?hash=/restrictedusers)

2. Questa pagina contiene l'elenco di utenti che sono stati bloccati dall'invio di messaggi di posta elettronica.  Individuare l'utente per il quale si desidera rimuovere le restrizioni e selezionare **Sblocca**.

3. Un fly-out entrerà nei dettagli relativi all'account di cui è riservata l'invio. È consigliabile eseguire le procedure consigliate per assicurarsi di prendere le azioni appropriate nel caso in cui l'account sia effettivamente compromesso. Fare clic su **Avanti** al termine.

4. Nella schermata successiva sono disponibili suggerimenti che consentono di evitare futuri compromessi. L'abilitazione dell'autenticazione a più fattori (AMF) e la modifica delle password sono una buona difesa. Fare clic su **Sblocca utente** al termine.

5. Fare clic su **Sì** per confermare la modifica.

    > [!NOTE]
    > Prima di rimuovere le restrizioni, potrebbero essere necessari 30 minuti o più. 

## <a name="making-sure-admins-are-alerted-when-this-happens"></a>Verificare che gli amministratori siano avvisati quando questo accade

Un avviso "utente con restrizioni dall'invio di messaggi di posta elettronica" è disponibile come criterio nella pagina Criteri di avviso per la sicurezza & conformità di Office 365. Questo era in precedenza il criterio della posta indesiderata in uscita, ma ora è nativo della piattaforma di avviso di Office 365. Andare a [criteri di avviso nel centro sicurezza & conformità](alert-policies.md) per ulteriori informazioni sugli avvisi.

> [!IMPORTANT]
> Affinché gli avvisi funzionino, è necessario che la ricerca del registro di controllo sia attivata. Per ulteriori informazioni, vedere [attivazione o disattivazione della ricerca del registro di controllo di Office 365](turn-audit-log-search-on-or-off.md) .

Il criterio per questo avviso è quello predefinito e viene fornito con tutti i tenant di Office 365 e non è necessario configurarlo. È considerato un avviso di severità elevato e invierà un messaggio di posta elettronica al gruppo TenantAdmins configurato quando l'avviso viene attivato ogni volta che un utente è stato impedito di inviare messaggi di posta elettronica. Gli amministratori possono aggiornare il gruppo notificato quando questo avviso si verifica accedendo all'avviso sotto il portale SCC > avvisi > criteri di avviso > gli utenti non devono inviare messaggi di posta elettronica.

È possibile modificare l'avviso per eseguire le operazioni seguenti:
- Attivazione/disattivazione delle notifiche tramite posta elettronica
- Inviare messaggi di posta elettronica ai destinatari necessari
- Limitare le notifiche ottenibili al giorno

## <a name="checking-for-and-removing-restrictions-using-powershell"></a>Verifica e rimozione di restrizioni tramite PowerShell
I comandi di PowerShell per gli utenti con restrizioni sono:
- `Get-BlockedSenderAddress`: Run to recupera l'elenco degli utenti con limitazioni all'invio di messaggi di posta elettronica
- `Remove-BlockedSenderAddress`: Esegui per rimuovere gli utenti da restrizioni

## <a name="for-more-information"></a>Ulteriori informazioni

[Risposta a un account di posta elettronica compromesso](responding-to-a-compromised-email-account.md)

[Informazioni sull'utente con restrizioni dall'invio di messaggi di avviso tramite posta elettronica](https://docs.microsoft.com/en-us/office365/securitycompliance/alert-policies)

[Pool di recapito ad alto rischio per i messaggi in uscita](high-risk-delivery-pool-for-outbound-messages.md)

[Autorizzazioni nel Centro sicurezza e conformità](permissions-in-the-security-and-compliance-center.md)

[Criteri di avviso nel centro sicurezza & conformità](https://docs.microsoft.com/en-us/office365/securitycompliance/alert-policies)
