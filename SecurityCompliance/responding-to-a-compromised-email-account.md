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
ms.service: o365-solutions
localization_priority: Normal
search.appverid:
- MET150
ms.custom: ''
ms.assetid: ''
description: Informazioni su come riconoscere e rispondere a un account di posta elettronica compromesso in Office 365
ms.openlocfilehash: b10bf58aaebc46938e3962494ff30dfb1e226130
ms.sourcegitcommit: 411713004251ee62d29b550eabea04c08a87e41f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/27/2018
ms.locfileid: "25341421"
---
# <a name="responding-to-a-compromised-email-account-in-office-365"></a>Rispondere a un account di posta elettronica compromesso in Office 365

**Riepilogo** Informazioni su come riconoscere e rispondere a un account di posta elettronica compromesso in Office 365.

## <a name="what-is-a-compromised-email-account-in-office-365"></a>Che cos'è un Account di posta elettronica esposto a possibili violazioni in Office 365?
Accesso alle cassette postali di Office 365, dati e altri servizi, è controllata tramite l'utilizzo delle credenziali, ad esempio un nome utente e password o il PIN. Quando un utente diverso da quello previsto sottrae le credenziali, le credenziali rubate vengono considerate violazione. Con cui l'autore dell'attacco può effettuare l'accesso utente originale ed eseguire azioni illecite. Utilizzando le credenziali rubate, l'autore dell'attacco può accedere dell'utente della cassetta postale Office 365, le cartelle di SharePoint o i file di OneDrive dell'utente. Solitamente è un'azione è l'autore dell'attacco invia messaggi di posta elettronica dell'utente originale ai destinatari all'interno e all'esterno dell'organizzazione. Quando l'autore dell'attacco dati di posta elettronica a destinatari esterni, detta exfiltration dati.

## <a name="symptoms-of-a-compromised-office-365-email-account"></a>Sintomi di un Account di posta elettronica compromesso Office 365
Gli utenti possono osservare e report attività non comune nelle cassette postali di Office 365. Di seguito sono indicati alcuni sintomi comuni:
- Attività potenzialmente dannoso, ad esempio messaggi di posta elettronica mancanti o eliminati.
- Altri utenti potrebbero ricevere messaggi di posta elettronica dall'account compromesso senza messaggio di posta elettronica corrispondente esistente nella cartella **Posta inviata** del mittente.
- La presenza di regole posta in arrivo non sono stati creati dall'utente appropriati o dall'amministratore. Queste regole possono automaticamente inoltrare messaggi di posta elettronica a indirizzi sconosciuti o spostarli cartelle **note**, **Posta indesiderata**o **Le sottoscrizioni RSS** .
- Nome visualizzato dell'utente può essere modificato in elenco indirizzi globale.
- Cassetta postale dell'utente viene impedita l'invio di posta elettronica.
- Le cartelle inviato o elementi eliminati in Microsoft Outlook o in Microsoft Outlook Web App contengono messaggi account attaccato comuni, ad esempio "è bloccato Londra, invia denaro."
- Modifiche al profilo non comune, ad esempio il nome, il numero di telefono o il codice postale sono state aggiornate.
- Sono necessarie modifiche insolito credenziali, ad esempio più modifiche delle password.
- Inoltro di posta elettronica è stato aggiunto di recente.
- Una firma non comune è stato aggiunto di recente, ad esempio una firma banca FALSO o una firma drug medica.

Se un utente segnala le condizioni precedenti, è consigliabile eseguire ulteriori analisi. La protezione di Office 365 & centro conformità e il portale di Azure sono disponibili strumenti che consentono di esaminare l'attività di un account utente che si ritiene che potrebbero essere compromesse.
- Office 365 Unified i registri di controllo nel centro conformità - sicurezza esaminare tutte le attività per l'account sospetto filtrando i risultati per il relativo intervallo di data da immediatamente prima che si è verificato l'attività sospette alla data corrente. Non filtrare le attività durante la ricerca.
- Utilizzare i registri Sign-in Azure Active Directory e altri report rischi che sono disponibili nel portale di Azure Active Directory. Esaminare i valori di queste colonne:
    - Esaminare l'indirizzo IP
    - percorsi di accesso
    - tempi di accesso
    - accesso esito positivo o negativo



## <a name="how-to-secure-and-restore-email-function-to-a-suspected-compromised-office-365-account-and-mailbox"></a>Come proteggere e ripristinare funzione di posta elettronica a un potenziale violazione account Office 365 e delle cassette postali

> [!VIDEO https://videoplayercdn.osi.office.net/hub/?csid=ux-cms-en-us-msoffice&uuid=RE2jvOb&AutoPlayVideo=false]

Anche dopo che è stato rapidamente l'accesso al proprio account, l'autore dell'attacco può essere aggiunto back porta voci che consentono l'autore dell'attacco riprendere il controllo dell'account.

È necessario eseguire la procedura seguente per ottenere di nuovo l'accesso all'account prima ideale per assicurarsi che non viene ripreso il hijacker controllo dell'account. La procedura seguente consentono di rimuovere tutte le voci back porta che il hijacker possono essere aggiunti al proprio account. Dopo aver eseguito questa procedura, è consigliabile eseguire un'analisi antivirus per verificare che il computer non è esposto a possibili violazioni.

### <a name="step-1-reset-the-users-password"></a>Passaggio 1 Reimposta la password dell'utente
> [!WARNING]
> Non inviare la nuova password per l'utente designato tramite posta elettronica quando l'autore dell'attacco può ancora accedere alla cassetta postale a questo punto.

1. Seguire la password aziendali Reset Office 365 per ricevere le altre procedure illustrate in [Admins: password business reimpostare Office 365](https://support.office.com/article/admins-reset-office-365-business-passwords-7a5d073b-7fae-4aa5-8f96-9ecd041aba9c)

**Note:**
- Verificare che la password è complessa e che sia presente almeno un carattere speciale lettere maiuscole o minuscole e almeno un numero. 
- Non riutilizzare le password ultimi cinque. Anche se il requisito di cronologia delle password consente di riutilizzare una password più recente, è consigliabile selezionare un elemento che non possono suppone l'autore dell'attacco.
- Se l'identità dell'utente locale è federato con Office 365, è necessario modificare le password in locale e quindi è necessario notificare l'amministratore della violazione.

> [!TIP]
> È consigliabile abilitare l'autenticazione a più fattori (MFA) per impedirne compromesso, in particolare per account con privilegi di amministratore.  Per ulteriori informazioni [di seguito](https://support.office.com/en-us/article/Set-up-multi-factor-authentication-for-Office-365-users-8f0454b2-f51a-4d9c-bcde-2c48e41621c6).

### <a name="step-2-remove-suspicious-email-forwarding-addresses"></a>Passaggio 2 indirizzi di inoltro di posta elettronica sospetti Remove
1. Apri il **interfaccia di amministrazione di Office 365 > utenti attivi**.
2. Individuare l'account utente in questione ed espandere **Impostazioni di posta elettronica**.
3. Per l' **inoltro di posta elettronica**, fare clic su **Modifica**.
4. Rimuovere qualsiasi indirizzo di inoltro potenzialmente dannoso.

### <a name="step-3-disable-any-suspicious-inbox-rules"></a>Passaggio 3 disabilitare tutte le regole posta in arrivo sospetti
1. Accedere alla cassetta postale dell'utente tramite Outlook Web App (OWA).
2. Fare clic sull'icona dell'ingranaggio e fare clic su **posta elettronica**.
3. Fare clic su **regole posta in arrivo e segue in allontanamento** ed esaminare le regole.
4. Disattivare o eliminare regole potenzialmente dannoso.

### <a name="step-4-unblock-the-user-from-sending-mail"></a>Passaggio 4 consente di sbloccare l'utente di inviare posta elettronica
Se la cassetta postale compromessa sospetta utilizzata illecitamente per inviare la posta elettronica da posta indesiderata, è probabile che la cassetta postale è stata bloccata di inviare posta elettronica.
1. Per sbloccare una cassetta postale di inviare posta elettronica, eseguire le procedure di [rimozione di un utente, un dominio o indirizzo IP da un elenco di blocco dopo l'invio di posta elettronica da posta indesiderata](https://docs.microsoft.com/Office365/SecurityCompliance/removing-a-user-domain-or-ip-address-from-a-block-list-after-sending-spam-email ).

### <a name="step-5-optional-block-the-user-account-from-signing-in"></a>Facoltativo passaggio 5: Bloccare l'account utente di accesso in
> [!IMPORTANT]
> È possibile bloccare l'account compromesso sospetti dall'accesso di fino a quando non si ritiene che è consigliabile abilitare di nuovo l'accesso.

1. Passare all'interfaccia di amministrazione di Office 365.
2. Nell'interfaccia di amministrazione di Office 365, selezionare **gli utenti**.
3. Selezionare il dipendente che si desidera bloccare e quindi scegliere **Modifica** accanto a **stato di accesso** nel riquadro utenti
4. Nel riquadro di **stato di accesso** , scegliere **accesso bloccato** e quindi **salvare**. 
5. Nell'interfaccia di amministrazione di Office 365 nel riquadro di spostamento in basso a sinistra espandere **Interfacce di amministrazione** e selezionare **Exchange**.
6. Nell'interfaccia di amministrazione di Exchange, accedere a **destinatari > cassette postali**.
7. Selezionare l'utente e nella pagina delle proprietà utente, sotto **Dispositivi mobili**, fare clic su **Disattiva ActivcSync Exchange** e **Disabilitare OWA per dispositivi** e rispondere **Sì** a entrambi.
8. In **Connessione posta elettronica**, **disabilitare** e rispondere **Sì**. 

### <a name="step-6-optional-remove-the-suspected-compromised-account-from-all-administrative-role-groups"></a>Facoltativo passaggio 6: Rimuovere l'account compromesso sospetto da tutti i gruppi di ruoli amministrativi
> [!NOTE]
> Appartenenza al gruppo di ruolo amministrativo può essere ripristinato dopo che l'account è protetto.

1. Accedere all'interfaccia di amministrazione di Office 365 con un account amministratore globale e aprire **Utenti attivi**.
2. Trova i sospetti esposto a possibili violazioni account e verificare manualmente per verificare se esistono eventuali ruoli amministrativi assegnati all'account.
3. Aprire il **centro conformità e sicurezza**.
4. Fare clic su **autorizzazioni**.
5. Esaminare manualmente i gruppi di ruoli per verificare se il sospetti esposto a possibili violazioni account è membro di uno di essi.  In questo caso: r. fare clic sul gruppo di ruoli e fare clic su **Modifica gruppo di ruoli**.  b. fare clic su **Membri scelto** e **Modifica** per rimuovere l'utente dal gruppo di ruoli.
6. Aprire l' **Interfaccia di amministrazione di Exchange**
7. Fare clic su **autorizzazioni**.
8. Esaminare manualmente i gruppi di ruoli per verificare se il sospetti esposto a possibili violazioni account è membro di uno di essi. In questo caso: r. fare clic sul gruppo di ruoli e fare clic su **Modifica**.  b. utilizzare la sezione **membri** per rimuovere l'utente dal gruppo di ruoli.

### <a name="step-7-optional-additional-precautionary-steps"></a>Facoltativo passaggio 7: Operazioni a titolo precauzionale aggiuntivi
1. Verificare che verificare i messaggi inviati. Potrebbe essere necessario informare gli utenti nel proprio elenco contatti che l'account è stata danneggiata. L'autore dell'attacco potrebbe hanno richiesto loro denaro, lo spoofing, ad esempio, che sono stati terra a causa di un paese diverso e necessari money o l'autore dell'attacco può inviare loro un virus in anche assumere il controllo sui propri computer.
2. Qualsiasi altro servizio utilizzato l'account di Exchange quando il relativo account di posta elettronica alternativi danneggiata. Innanzitutto, eseguire la procedura seguente per la sottoscrizione a Office 365 e quindi eseguire la procedura seguente per gli altri account.
3. Verificare che le informazioni di contatto, ad esempio numeri di telefono e indirizzi, siano corrette.

## <a name="secure-office-365-like-a-cybersecurity-pro"></a>Protezione di Office 365 come alla sicurezza informatica pro
La sottoscrizione a Office 365 è dotato di un insieme completo di funzionalità di protezione che è possibile utilizzare per proteggere i dati e gli utenti.  Utilizzare il [roadmap di protezione di Office 365: principali priorità per i primi 30 giorni, 90 giorni e oltre](https://support.office.com/article/Office-365-security-roadmap-Top-priorities-for-the-first-30-days-90-days-and-beyond-28c86a1c-e4dd-4aad-a2a6-c768a21cb352) per l'implementazione Microsoft di procedure consigliate per la protezione di Office 365 tenant.
- Attività per raggiungere i primi 30 giorni.  Questi hanno effetto immediato e sono basso impatto per gli utenti.
- Attività da eseguire per 90 giorni. Queste un po' di tempo maggiore pianificare e implementare ma migliorare notevolmente le condizioni di sicurezza generali.
- Oltre a 90 giorni. Questi miglioramenti build per il lavoro di 90 giorni primo.

## <a name="see-also"></a>Vedere anche:
- [Procedure consigliate per la sicurezza per Office 365](https://support.office.com/article/Security-best-practices-for-Office-365-9295e396-e53d-49b9-ae9b-0b5828cdedc3)
- [Rilevare e correggere le regole di Outlook e injections nei moduli personalizzati in Office 365](detect-and-remediate-outlook-rules-forms-attack.md)
- [Internet Crime reclamo Center](http://www.ic3.gov/preventiontips.aspx)
- [Securities and Exchange Commission - truffe di false "Phishing"](http://www.sec.gov/investor/pubs/phishing.htm)
