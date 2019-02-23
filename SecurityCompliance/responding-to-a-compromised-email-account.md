---
title: Rispondere a un account di posta elettronica compromesso in Office 365
ms.author: chrfox
author: chrfox
manager: laurawi
ms.audience: ITPro
ms.topic: article
ms.collection:
- o365_security_incident_response
- Strat_O365_IP
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.custom: ''
ms.assetid: ''
description: Informazioni su come riconoscere e rispondere a un account di posta elettronica compromesso in Office 365
ms.openlocfilehash: 8d2e7f501b6e3ee73a14d4d7b3edb4c49f99d051
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/23/2019
ms.locfileid: "30213216"
---
# <a name="responding-to-a-compromised-email-account-in-office-365"></a>Rispondere a un account di posta elettronica compromesso in Office 365

**Riepilogo** Informazioni su come riconoscere e rispondere a un account di posta elettronica compromesso in Office 365.

## <a name="what-is-a-compromised-email-account-in-office-365"></a>Che cos'è un account di posta elettronica compromesso in Office 365?
L'accesso alle cassette postali, ai dati e ad altri servizi di Office 365 è controllato tramite l'utilizzo delle credenziali, ad esempio un nome utente e una password o un PIN. Quando una persona diversa dall'utente desiderato ruba tali credenziali, le credenziali rubate vengono considerate compromesse. Con gli utenti che effettuano l'attacco possono accedere come utente originale ed eseguire azioni illecite. Utilizzando le credenziali rubate, l'utente malintenzionato può accedere alla cassetta postale di Office 365, alle cartelle di SharePoint o ai file nell'OneDrive dell'utente. Un'azione comunemente vista è l'aggressore che invia messaggi di posta elettronica come utente originale ai destinatari sia all'interno che all'esterno dell'organizzazione. Quando l'utente malintenzionato invia messaggi di posta elettronica ai destinatari esterni, viene chiamato data exfiltration.

## <a name="symptoms-of-a-compromised-office-365-email-account"></a>Sintomi di un account di posta elettronica di Office 365 compromesso
Gli utenti possono notare e segnalare attività insolite nelle cassette postali di Office 365. Di seguito sono riportati alcuni sintomi comuni:
- Attività sospette, ad esempio messaggi di posta elettronica mancanti o eliminati.
- Gli altri utenti possono ricevere messaggi di posta elettronica dall'account compromesso senza il corrispondente messaggio di posta elettronica esistente nella cartella degli **elementi inviati** del mittente.
- La presenza delle regole di posta in arrivo che non sono state create dall'utente o dall'amministratore desiderato. Queste regole possono inoltrare automaticamente messaggi di posta elettronica a indirizzi sconosciuti o spostarli nelle cartelle **Note**, **posta**IndesideraTa o **abbonamenti RSS** .
- Il nome visualizzato dell'utente potrebbe essere modificato nell'elenco indirizzi globale.
- La cassetta postale dell'utente è bloccata dall'invio di messaggi di posta elettronica.
- Le cartelle degli elementi inviati o eliminati in Microsoft Outlook o Outlook sul Web (in precedenza noto come Outlook Web App) contengono messaggi di account violati comuni, ad esempio "sono bloccato a Londra, invio di denaro".
- Sono state aggiornate le modifiche del profilo inUsuali, ad esempio il nome, il numero di telefono o il Cap.
- Modifiche inUsuali delle credenziali, ad esempio più modifiche delle password sono obbligatorie.
- L'inoltro della posta è stato aggiunto di recente.
- Una firma inusuale è stata aggiunta di recente, ad esempio una firma bancaria fasulla o una firma antidroga.

Se un utente segnala uno dei sintomi riportati sopra, è consigliabile eseguire ulteriori indagini. Il Centro sicurezza e conformità di Office 365 & e il portale di Azure offrono strumenti che consentono di analizzare l'attività di un account utente che si sospetta potrebbe essere compromesso.
- Registri di controllo unificato di Office 365 nel centro sicurezza & Compliance-esaminare tutte le attività per l'account sospetto filtrando i risultati relativi all'intervallo di date che si estende da subito prima che l'attività sospetta si sia verificata alla data corrente. Non filtrare le attività durante la ricerca.
- Utilizzare i registri di accesso di Azure AD e altri report sui rischi disponibili nel portale di Azure AD. Esaminare i valori nelle colonne seguenti:
    - Esaminare l'indirizzo IP
    - posizioni di accesso
    - Orari di accesso
    - esito positivo o negativo dell'accesso

## <a name="how-to-secure-and-restore-email-function-to-a-suspected-compromised-office-365-account-and-mailbox"></a>Come proteggere e ripristinare la funzione di posta elettronica a un account e una cassetta postale di Office 365 compromessi sospetti

> [!VIDEO https://videoplayercdn.osi.office.net/hub/?csid=ux-cms-en-us-msoffice&uuid=RE2jvOb&AutoPlayVideo=false]

Anche dopo aver riottenuto l'accesso all'account, l'utente malintenzionato può aver aggiunto voci di back-door che consentono all'utente malintenzionato di riprendere il controllo dell'account.

Per riaccedere al proprio account, è necessario eseguire tutti i passaggi seguenti, prima di tutto è preferibile verificare che il dirottatore non riprenda a controllare il proprio account. Questi passaggi consentono di rimuovere tutte le voci di back-door che il dirottatore può aver aggiunto al proprio account. Dopo aver eseguito questa procedura, è consigliabile eseguire un'analisi antivirus per assicurarsi che il computer non venga compromesso.

### <a name="step-1-reset-the-users-password"></a>Passaggio 1 reImpostare la password dell'utente
> [!WARNING]
> Non inviare la nuova password all'utente desiderato tramite posta elettronica poiché l'aggressore ha ancora accesso alla cassetta postale a questo punto.

1. Seguire la reImpostazione di una password aziendale di Office 365 per le procedure di un altro utente in [Admins: reimpostare le password di office 365 business](https://support.office.com/article/admins-reset-office-365-business-passwords-7a5d073b-7fae-4aa5-8f96-9ecd041aba9c)

**Note:**
- Verificare che la password sia elevata e che contenga lettere maiuscole e minuscole, almeno un numero e almeno un carattere speciale. 
- Non riutilizzare nessuna delle ultime cinque password. Anche se il requisito di cronologia delle password consente di riutilizzare una password più recente, è necessario selezionare qualcosa che l'utente malintenzionato non riesca a indovinare.
- Se l'identità locale è federata con Office 365, è necessario modificare la password locale e quindi informare l'amministratore del compromesso.

> [!TIP]
> È consigliabile abilitare l'autenticazione a più fattori per impedire il compromesso, soprattutto per gli account con privilegi amministrativi.  È possibile ottenere ulteriori informazioni [qui](https://support.office.com/en-us/article/Set-up-multi-factor-authentication-for-Office-365-users-8f0454b2-f51a-4d9c-bcde-2c48e41621c6).

### <a name="step-2-remove-suspicious-email-forwarding-addresses"></a>Passaggio 2 rimuovere indirizzi sospetti di inoltro della posta elettronica
1. Aprire l'interfaccia di **amministrazione di Office 365 _GT_ gli utenti attivi**.
2. Individuare l'account utente in questione ed espandere **impostazioni di posta elettronica**.
3. Per l' **inoltro della posta elettronica**, fare clic su **modifica**.
4. Rimuovere gli indirizzi di inoltro sospetti.

### <a name="step-3-disable-any-suspicious-inbox-rules"></a>Passaggio 3 Disabilitazione delle regole di posta in arrivo sospette
1. Accedere alla cassetta postale dell'utente utilizzando Outlook sul Web.
2. Fare clic sull'icona dell'ingranaggio e fare clic su **posta**.
3. Fare clic su **posta in arrivo e regole di sweep** e controllare le regole.
4. Disabilitare o eliminare le regole sospette.

### <a name="step-4-unblock-the-user-from-sending-mail"></a>Passaggio 4 sbloccare l'utente dall'invio di messaggi di posta elettronica
Se la cassetta postale sospetta è stata usata illegalmente per inviare messaggi di posta indesiderata, è probabile che la cassetta postale sia stata bloccata dall'invio della posta.
1. Per sbloccare una cassetta postale dall'invio di messaggi di posta elettronica, seguire le procedure riportate in [rimozione di un utente, dominio o indirizzo IP da un elenco di blocco dopo l'invio](https://docs.microsoft.com/Office365/SecurityCompliance/removing-a-user-domain-or-ip-address-from-a-block-list-after-sending-spam-email )di posta indesiderata.

### <a name="step-5-optional-block-the-user-account-from-signing-in"></a>Passaggio 5 facoltativo: bloccare l'account utente dall'accesso
> [!IMPORTANT]
> È possibile bloccare l'account compromesso sospettato dall'accesso fino a quando non si ritiene che sia sicuro riattivarlo.

1. Passare all'interfaccia di amministrazione di Office 365.
2. Nell'Interfaccia di amministrazione di Office 365 selezionare **Utenti**.
3. Selezionare il dipendente da bloccare e quindi fare clic su **modifica** accanto a stato di **accesso** nel riquadro utente.
4. Nel riquadro **Stato accesso** scegliere **Accesso bloccato** e quindi **Salva**. 
5. Nell'interfaccia di amministrazione di Office 365, nel riquadro di spostamento in basso a sinistra, espandere interfaccia di **Amministrazione** e selezionare **Exchange**.
6. Nell'interfaccia di amministrazione di Exchange, accedere a **destinatari _GT_ cassette postali**.
7. Selezionare l'utente e nella pagina proprietà utente, in **dispositivi mobili**, fare clic su **Disattiva Exchange ACTIVCSYNC** e **disabilitare OWA per i dispositivi** e rispondere **Sì** a entrambi.
8. In **connettività posta elettronica**, **Disabilita** e Rispondi **Sì**. 

### <a name="step-6-optional-remove-the-suspected-compromised-account-from-all-administrative-role-groups"></a>Passaggio 6 facoltativo: rimuovere l'account compromesso sospetto da tutti i gruppi di ruoli amministrativi
> [!NOTE]
> L'appartenenza a un gruppo di ruoli amministrativi può essere ripristinata dopo che l'account è stato protetto.

1. Accedere all'interfaccia di amministrazione di Office 365 con un account di amministratore globale e aprire **utenti attivi**.
2. Individuare l'account compromesso sospettato e controllare manualmente se sono presenti ruoli amministrativi assegnati all'account.
3. Aprire il **Centro sicurezza _AMP_ Compliance**.
4. Fare clic su **autorizzazioni**.
5. Esaminare manualmente i gruppi di ruoli per verificare se l'account compromesso ritenuto sospetto è un membro di uno di essi.  Se è: a. fare clic sul gruppo di ruoli e fare clic su **modifica gruppo di ruoli**.  b. fare clic su **Scegli membri** e **modifica** per rimuovere l'utente dal gruppo di ruoli.
6. Aprire l'interfaccia di **amministrazione di Exchange**
7. Fare clic su **autorizzazioni**.
8. Esaminare manualmente i gruppi di ruoli per verificare se l'account compromesso ritenuto sospetto è un membro di uno di essi. Se è: a. fare clic sul gruppo di ruoli e fare clic su **modifica**.  b. utilizzare la **** sezione Members per rimuovere l'utente dal gruppo di ruoli.

### <a name="step-7-optional-additional-precautionary-steps"></a>Passaggio 7 facoltativo: ulteriori passaggi precauzionali
1. Verificare che gli elementi inviati siano stati verificati. Potrebbe essere necessario informare gli utenti dell'elenco dei contatti che l'account è stato compromesso. L'utente malintenzionato può aver chiesto soldi, spoofing, ad esempio, che sono stati bloccati in un paese diverso e necessari soldi, o l'aggressore potrebbe inviare un virus anche per dirottare i propri computer.
2. Qualsiasi altro servizio utilizzato per l'account di Exchange come account di posta elettronica alternativo potrebbe essere stato compromesso. Per prima cosa, eseguire la procedura seguente per l'abbonamento a Office 365 e quindi eseguire questi passaggi per gli altri account.
3. Verificare che le informazioni di contatto, ad esempio i numeri di telefono e gli indirizzi, siano corrette.

## <a name="secure-office-365-like-a-cybersecurity-pro"></a>Protezione di Office 365 come un Cybersecurity Pro
L'abbonamento a Office 365 è dotato di un potente set di funzionalità di sicurezza che è possibile utilizzare per proteggere i dati e gli utenti.  Utilizzare la Guida di [orientamento alla sicurezza di office 365: priorità principali per i primi 30 giorni, 90 giorni e oltre](https://support.office.com/article/Office-365-security-roadmap-Top-priorities-for-the-first-30-days-90-days-and-beyond-28c86a1c-e4dd-4aad-a2a6-c768a21cb352) per implementare le procedure consigliAte di Microsoft consigliati per la protezione del tenant di Office 365.
- Attività da eseguire nei primi 30 giorni.  Tali effetti hanno un impatto immediato e sono di scarso effetto per gli utenti.
- Attività da eseguire in 90 giorni. Questi richiedono un po' più di tempo per pianificare e implementare, ma migliorare notevolmente la posizione di sicurezza.
- Oltre 90 giorni. Questi miglioramenti vengono costruiti nei primi 90 giorni di lavoro.

## <a name="see-also"></a>Vedere anche:
- [Procedure consigliate per la sicurezza per Office 365](https://support.office.com/article/Security-best-practices-for-Office-365-9295e396-e53d-49b9-ae9b-0b5828cdedc3)
- [Rilevare e risolvere gli attacchi injection alle regole e ai moduli personalizzati di Outlook in Office 365](detect-and-remediate-outlook-rules-forms-attack.md)
- [Centro reclami crimine Internet](http://www.ic3.gov/preventiontips.aspx)
- [Securities and Exchange Commission-frode "phishing"](http://www.sec.gov/investor/pubs/phishing.htm)
