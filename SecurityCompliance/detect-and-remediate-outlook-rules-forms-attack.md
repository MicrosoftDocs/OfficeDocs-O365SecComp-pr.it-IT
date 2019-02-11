---
title: Rileva problemi e personalizzati e le regole di Outlook correggere gli attacchi di inserimento moduli gli attacchi di Office 365
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 04/23/2018
ms.audience: ITPro
ms.topic: article
ms.collection:
- o365_security_incident_response
- Strat_O365_IP
ms.service: o365-solutions
localization_priority: Normal
search.appverid:
- MET150
description: Informazioni su come riconoscere e correggere le regole di Outlook e gli attacchi di attacchi di tipo injection moduli personalizzati in Office 365
ms.openlocfilehash: 1067d7c791217c146fedea839754e45f76ef5d8e
ms.sourcegitcommit: 7e2a0185cadea7f3a6afc5ddc445eac2e1ce22eb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/11/2019
ms.locfileid: "29603757"
---
# <a name="detect-and-remediate-outlook-rules-and-custom-forms-injections-attacks-in-office-365"></a>Rilevare e risolvere gli attacchi injection alle regole e ai moduli personalizzati di Outlook in Office 365

**Riepilogo** Informazioni su come riconoscere e correggere le regole di Outlook e attacchi di attacchi di tipo injection moduli personalizzati in Office 365.

## <a name="what-is-the-outlook-rules-and-custom-forms-injection-attack"></a>Che cos'è intrusioni moduli personalizzati e le regole di Outlook?
Dopo che un utente malintenzionato ha violato un account nella tenancy e ottiene, vi saranno per tentare di stabilire un modo per mantenere o un modo per ottenere dopo aver individuati e rimosso. Si tratta di stabilire un meccanismo di persistenza. Due metodi che possono farlo sono sfruttando le regole di Outlook o inserendo moduli personalizzati in Outlook. In entrambi i casi, la regola o il modulo viene sincronizzato dal servizio cloud verso il basso per il client desktop, in modo che un formato completo e rieseguire l'installazione del software client non eliminare il meccanismo di inserimento. Ciò avviene perché quando si ricollega il software client di Outlook per la cassetta postale nel cloud verrà eseguito nuovamente il download le regole e i moduli dal cloud. Dopo che le regole e i moduli sono presenti, l'autore dell'attacco li utilizza per eseguire codice personalizzato o remoto, in genere per installare malware nel computer locale. Malware quindi sottrae nuovamente le credenziali o esegue altre attività illecita. La buona notizia è che gli aggiornamenti per i client di un'applicazione di patch per la versione più recente, non è esposto al rischio come impostazioni predefinite del client Outlook corrente bloccano entrambi i meccanismi di. 

Gli attacchi in genere seguono questi modelli:

L'Exploit di regole
1. L'autore dell'attacco sottrae il nome utente e password di uno degli utenti.
2. L'autore dell'attacco accede a tale cassetta postale di Exchange degli utenti. La cassetta postale può essere di Exchange online o in Exchange locale.
3. L'autore dell'attacco crea quindi una regola di inoltro nella cassetta postale che viene attivata quando la cassetta postale riceve un messaggio di posta elettronica che soddisfa i criteri della regola. I criteri della regola e il contenuto del messaggio di posta elettronica trigger è ideali per tra loro.
4. L'autore dell'attacco Invia messaggio di posta elettronica trigger per l'utente che utilizza in genere delle relative cassette postali.
5. Quando si riceve il messaggio di posta elettronica, viene attivata la regola. L'azione della regola è in genere per avviare un'applicazione in un server remoto (WebDAV).
6. L'applicazione in genere installa malware, ad esempio [Powershell Empire](https://www.powershellempire.com/)localmente nel computer dell'utente.
7. Malware consente l'autore dell'attacco per sottrarre nuovamente il nome utente e password o altre credenziali dal computer locale ed eseguire altre attività dannose.

L'Exploit di moduli
1. L'autore dell'attacco sottrae il nome utente e password di uno degli utenti.
2. L'autore dell'attacco quindi accedere a tale cassetta postale di Exchange degli utenti. La cassetta postale può essere di Exchange online o in Exchange locale.
3. L'autore dell'attacco successivamente consente di creare un modello di modulo di posta personalizzato e lo inserisce nella cassetta postale dell'utente.  Il modulo personalizzato viene attivato quando la cassetta postale riceve un messaggio che richiede la cassetta postale per caricare il modulo personalizzato. Il modulo personalizzato e il formato del messaggio di posta elettronica sono ideali per tra loro.
4. L'autore dell'attacco Invia messaggio di posta elettronica trigger per l'utente, che utilizza in genere delle relative cassette postali.
5. Quando si riceve il messaggio di posta elettronica, la maschera viene caricata. Il modulo viene avviata un'applicazione in un server remoto (WebDAV).
6. L'applicazione in genere installa malware, ad esempio [Powershell Empire](https://www.powershellempire.com/)localmente nel computer dell'utente.
7. Malware consente l'autore dell'attacco per sottrarre nuovamente il nome utente e password o altre credenziali dal computer locale ed eseguire altre attività dannose.


## <a name="what-a-rules-and-custom-forms-injection-attack-might-look-like-office-365"></a>Le regole e moduli personalizzati intrusioni potrebbe essere simile a Office 365?

Questi meccanismi di persistenza improbabile che risultano dagli utenti e in alcuni casi addirittura possibile invisibili loro.  In questo articolo viene illustrato come verificare se sono presenti dei segni di sette (gli indicatori di compromesso) elencati di seguito. Se una qualsiasi delle domande, è necessario eseguire la procedura di risoluzione dei problemi.

- Indicatori della violazione delle regole
    - L'azione regola consiste per avviare un'applicazione.
    - Regola fa riferimento a un file EXE, ZIP o URL.
    - Nel computer locale, cercare il nuovo processo inizia che hanno origine da PID Outlook.
- Indicatori della violazione di moduli personalizzati 
    - Modulo personalizzato presente salvato come i propri classe messaggio.
    - Classe messaggio contiene codice eseguibile.
    - In genere memorizzati nelle cartelle posta in arrivo o Libreria moduli personali.
    - Modulo viene denominato IPM. Si noti. [nome personalizzato].

## <a name="steps-for-finding-signs-of-this-attack-and-confirming-it"></a>Passaggi per la ricerca di segni di questo tipo di attacco e conferma
È possibile utilizzare uno di questi due metodi per confermare l'attacco.
- Esaminare manualmente le regole e i moduli per ciascuna cassetta postale utilizzando il client di Outlook.  Questo metodo è completo, ma è possibile controllare cassetta postale utente alla volta che è possibile richiedere molto tempo molti utenti da controllare.  Può anche comportare una violazione del computer in cui viene eseguito il controllo da.
- Utilizzare lo script di PowerShell [Get-AllTenantRulesAndForms.ps1](https://github.com/OfficeDev/O365-InvestigationTooling/blob/master/Get-AllTenantRulesAndForms.ps1) per riportare automaticamente tutta la posta moduli personalizzati per tutti gli utenti e le regole di inoltro nella tenancy. Questo è il metodo più rapido e più sicuro con la quantità minima di sovraccarico.


### <a name="confirm-the-rules-attack-using-the-outlook-client"></a>Verificare le regole di attacco tramite il client di Outlook
1. Aprire il client di Outlook agli utenti come utente.  L'utente potrebbe essere necessario una Guida in linea in esame le regole sulle cassette postali.
2. Riferimento all'articolo [Manage messaggi tramite le regole della posta elettronica](https://support.office.com/article/manage-email-messages-by-using-rules-c24f5dea-9465-4df4-ad17-a50704d66c59#ID0EAABAAA=2010) per le informazioni sulle procedure aprire l'interfaccia di regole nelle versioni 2007, 2010 o 2013 di Outlook.
3. Cercare le regole che l'utente non è stato creato, o qualsiasi impreviste regole o i cui nomi potenzialmente dannoso.
4. Esaminare la descrizione della regola di azioni delle regole di inizio e di applicazioni o fare riferimento a un. EXE. File con estensione ZIP oppure per avviare un URL.
5. Ricercare eventuali nuovi processi che iniziano con l'ID del processo di Outlook.  Fare riferimento a [trovare l'ID di processo](https://docs.microsoft.com/windows-hardware/drivers/debugger/finding-the-process-id).

### <a name="steps-to-confirm-the-forms-attack-using-the-outlook-client"></a>Passaggi per verificare l'attacco moduli utilizzando il client di Outlook
1. Aprire il client di Outlook utente dell'utente.
2. Seguire i passaggi descritti in, [visualizzare la scheda sviluppo](https://support.office.com/article/show-the-developer-tab-e1192344-5e56-4d45-931b-e5fd9bea2d45) per la versione di utenti di Outlook.
3. Aprire la scheda saranno visibili per gli sviluppatori in Outlook e fare clic su **Progetta modulo**.
4. Selezionare nell'elenco **Cerca In** **posta in arrivo** . Ricercare eventuali moduli personalizzati.  Moduli personalizzati sono sufficientemente rari che se si dispone di tutti i moduli personalizzati, è importante una descrizione più approfondita.
5. Provare a utilizzare qualsiasi modulo personalizzato, in particolare quelli contrassegnati come nascosti.
6. Aprire alcun modulo personalizzato e nel gruppo **modulo** fare clic su **Visualizza codice** per verificare cosa viene eseguito quando la maschera viene caricata.

### <a name="steps-to-confirm-the-rules-and-forms-attack-using-powershell"></a>Passaggi per verificare le regole e i moduli di attaccano tramite PowerShell
Il modo più semplice per verificare un regole o i moduli personalizzati attacco consiste nell'eseguire lo script di PowerShell [Get-AllTenantRulesAndForms.ps1](https://github.com/OfficeDev/O365-InvestigationTooling/blob/master/Get-AllTenantRulesAndForms.ps1) .  Questo script si connette a tutte le cassette postali nel tenant e dump di tutte le regole e moduli in due file CSV.

#### <a name="pre-requisites"></a>Prerequisiti
È necessario disporre di diritti di amministratore globale per eseguire lo script poiché lo script si connette a tutte le cassette postali nella tenancy di leggere le regole e i moduli.

1. Accedere al computer in cui si esegue lo script da con diritti di amministratore locale.
2. Scaricare o copiare lo script Get-AllTenantRulesAndForms.ps1 da GitHub in una cartella da cui vengono eseguiti.  Lo script verrà creati due file Data contrassegnata per questa cartella, MailboxFormsExport-aaaa-mm-dd.csv e MailboxRulesExport-aaaa-mm-dd.csv.
3. Aprire un'istanza di PowerShell come amministratore e aprire la cartella che è stato salvato lo script.
4. Eseguire la riga di comando PowerShell come indicato di seguito `.\Get-AllTenantRulesAndForms.ps1`.\Get-AllTenantRulesAndForms.ps1

#### <a name="interpreting-the-output"></a>Interpretare l'output

MailboxRulesExport -*aaaa-mm-gg*. csv-esaminare le regole (uno per riga) per le condizioni di azione che includono le applicazioni o file eseguibili.
- ActionType (colonna A) – se viene visualizzato il valore "ID_ACTION_CUSTOM", la regola sarà probabilmente dannoso.
- IsPotentiallyMalicious (colonna D) – se questo valore è "TRUE", la regola sarà probabilmente dannoso.
- ActionCommand (colonna G) – se contiene un elenco di un'applicazione o i file con un .exe, estensione zip o una voce che fa riferimento a un URL che non dovrebbero per essere disponibili, la regola sarà probabilmente dannoso.

MailboxFormsExport -*aaaa-mm-gg*. csv – di solito, l'utilizzo di moduli personalizzati è molto raro.  Se è presente uno nella cartella di lavoro, si cassetta postale dell'utente di aprire ed esamina del modulo.  Se l'organizzazione non inserirla vi intenzionalmente, è probabile dannoso.



## <a name="how-to-stop-and-remediate-the-outlook-rules-and-forms-attack"></a>Come arrestare e correggere l'attacco moduli e le regole di Outlook
Se una prova di uno di questi attacchi, risoluzione dei problemi è semplice, eliminare la regola o il modulo dalla cassetta postale. È possibile ottenere questo risultato con il client di Outlook o utilizzando PowerShell remoto per rimuovere le regole.

### <a name="using-outlook"></a>Utilizzo di Outlook
1. Identificare tutti i dispositivi che l'utente ha usato con Outlook.  Sarà tutto necessario da pulire dei potenziale malware.  Non consentire all'utente di eseguire l'accesso e utilizzo della posta elettronica fino a quando non vengono rimossi tutti i dispositivi.
2. Eseguire la procedura di [eliminare una regola](https://support.office.com/article/Delete-a-rule-2F0E7139-F696-4422-8498-44846DB9067F) per ogni dispositivo.
3. Se non si conosce la presenza di altri tipi di malware, consente di formattare e reinstallare tutto il software del dispositivo.  Per i dispositivi mobili è possibile eseguire la procedura produttori per reimpostare il dispositivo per l'immagine factory.
4. Installare le versioni aggiornate di Outlook.  Tenere presente che la versione corrente di Outlook blocca entrambi i tipi di questo tipo di attacco per impostazione predefinita.
5. Dopo che sono state rimosse tutte le copie non in linea della cassetta postale, reimpostare la password dell'utente (utilizzare uno alta qualità uno) e seguire le procedure di [autenticazione a più fattori il programma di installazione per gli utenti di Office 365](https://support.office.com/article/Set-up-multi-factor-authentication-for-Office-365-users-8f0454b2-f51a-4d9c-bcde-2c48e41621c6) se MFA non è già abilitato. In questo modo che le credenziali dell'utente non sono esposte tramite altri mezzi (ad esempio utilizzare nuovamente il phishing o la password).

### <a name="using-powershell"></a>Utilizzo di PowerShell
Esistono due cmdlet di PowerShell remoto che è possibile utilizzare per rimuovere o disattivare le regole pericolose. Seguire la procedura seguente.
 
Operazioni per le cassette postali presenti in un server Exchange

1. Connettersi al server di Exchange utilizzando PowerShell remoto. Seguire i passaggi descritti in [Connetti al server di Exchange utilizzando PowerShell remoto](https://docs.microsoft.com/powershell/exchange/exchange-server/connect-to-exchange-servers-using-remote-powershell?view=exchange-ps).
2. Se si desidera rimuovere completamente una sola regola, più regole o tutte le regole da utilizzare una cassetta postale [cmdlet regola posta in arrivo Remove ](https://docs.microsoft.com/powershell/module/exchange/mailboxes/Remove-InboxRule?view=exchange-ps)- utilizzare questa opzione per completamente più di uno, remove o tutte le regole dalla cassetta postale.
3. Se si desidera conservare la regola e il relativo contenuto per un'analisi più approfondita utilizza il [cmdlet Disable-InboxRule](https://technet.microsoft.com/en-us/library/dd298120(v=exchg.160).aspx). 

Passaggi per le cassette postali in Exchange Online
1. Seguire i passaggi della [connessione a Exchange Online tramite PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell?view=exchange-ps).
2.  Se si desidera rimuovere completamente una sola regola, più regole o tutte le regole da una cassetta postale utilizzano il [cmdlet Remove-posta in arrivo regola](https://docs.microsoft.com/powershell/module/exchange/mailboxes/Remove-InboxRule?view=exchange-ps).
3.  Se si desidera conservare la regola e il relativo contenuto per un'analisi più approfondita utilizza il [cmdlet Disable-InboxRule](https://technet.microsoft.com/en-us/library/dd298120(v=exchg.160).aspx). 

## <a name="how-to-minimize-future-attacks"></a>Come ridurre al minimo gli attacchi futuri

### <a name="first-protect-your-accounts"></a>Primo: proteggere gli account

Attacchi tramite le regole e i moduli vengono utilizzate solo da un utente malintenzionato dopo che sono furto o superata uno degli account dell'utente. Pertanto, il primo passaggio per impedire l'uso di questi exploit contro l'organizzazione è in modo aggressivo proteggere gli account utente.  Alcuni metodi più comuni che gli account sono violati sono tramite phishing o [password irrorazione](http://www.dabcc.com/microsoft-defending-against-password-spray-attacks/) gli attacchi di tipo.



Il modo migliore per proteggere gli account utente e in particolare gli account di amministratore, consiste nel [configurare l'autenticazione a più fattori per gli utenti di Office 365](https://support.office.com/article/set-up-multi-factor-authentication-for-office-365-users-8f0454b2-f51a-4d9c-bcde-2c48e41621c6).  È inoltre necessario:
<ol>
    <li>Monitorare come gli account utente sono <a href="https://docs.microsoft.com/azure/active-directory/active-directory-view-access-usage-reports">accessibili e utilizzabili</a>. Non è possibile evitare la violazione iniziale, ma si riduce la durata e l'impatto della violazione per rilevare più rapidamente. È possibile utilizzare tali: <a href="https://support.office.com/article/overview-of-office-365-cloud-app-security-81f0ee9a-9645-45ab-ba56-de9cbccab475">criteri di protezione di Office 365 Cloud App</a> monitorare gli account e avvisi attività non comune.<ol type="a">
            <li><b>Più tentativi di accesso non riuscito</b> Quando gli utenti eseguono le attività di più account di accesso non riuscito in una singola sessione per quanto riguarda la previsione acquisita che potrebbe indicare un tentativo violazione di questo criterio profili all'ambiente e gli avvisi di trigger.</li>
            <li><b>Viaggiare inviolabile non esiste</b> - Questo criterio dell'ambiente di profili e genera avvisi quando vengono rilevate da parte dell'utente stesso in sedi diverse attività all'interno di un periodo di tempo più breve rispetto all'ora viaggi previsto tra le due posizioni. Ciò potrebbe indicare che un utente diverso utilizza le stesse credenziali. Rilevamento di questo comportamento anomalo richiede un periodo di formazione iniziale di sette giorni durante il quale viene informato della presenza motivo attività del nuovo utente.</li>
            <li><b>Insolito rappresentata attività (per utente)</b> - Questo criterio dell'ambiente di profili e genera avvisi quando gli utenti eseguono più attività rappresentata in una singola sessione rispetto alla linea di base maturata, che potrebbe indicare un tentativo violazione.</li>
        </ol>
    </li>
    <li>Utilizzare uno strumento simile <a href="https://securescore.office.com/">Punteggio sicura di Office 365</a> per gestire i comportamenti e le configurazioni di protezione dell'account. 
    </li>
</ol> 

### <a name="second-keep-your-outlook-clients-current"></a>Secondo: Aggiornare i client Outlook
Versioni completamente aggiornato e le patch di Outlook 2013 e 2016 disabilitare l'azione regola/modulo "Avvia applicazione" per impostazione predefinita.  In tal modo, anche se un utente malintenzionato upera l'account, verranno bloccate le azioni regola e moduli.  È possibile installare gli ultimi aggiornamenti e patch di protezione seguendo i passaggi descritti in [aggiornamenti di installare Office](https://support.office.com/article/Install-Office-updates-2ab296f3-7f03-43a2-8e50-46de917611c5).

Di seguito sono le versioni di patch per il Outlook 2013 e 2016 client:
- Outlook 2013: 15.0.4937.1000 o versione successiva
- Outlook 2016: 16.0.4534.1001 o versione successiva

Per ulteriori informazioni sulle singole patch di protezione, vedere:

- [Patch di protezione di Outlook 2013](https://support.microsoft.com/en-us/help/3191938) 
- [Patch di protezione di Outlook 2016](https://support.microsoft.com/en-us/help/3191883)

### <a name="third-monitor-your-outlook-clients"></a>Terzo: Monitorare i client Outlook
Si noti che anche con le patch e gli aggiornamenti installati, è possibile che un utente malintenzionato modificare la configurazione del computer locale per riattivare il comportamento "Avviare Application". È possibile utilizzare [Gestione avanzata dei criteri di gruppo](https://docs.microsoft.com/microsoft-desktop-optimization-pack/agpm/) per monitorare e applicare i criteri del computer locale sui client.  
È possibile per vedere se "Avvia applicazione" nuovamente abilitata tramite un override nel Registro di sistema in base alle informazioni su [come visualizzare il Registro di sistema con le versioni a 64 bit di Windows](https://support.microsoft.com/en-us/help/305097/how-to-view-the-system-registry-by-using-64-bit-versions-of-windows).  Controllare le sottochiavi: 

- Outlook 2016: HKEY_CURRENT_USER\Software\Microsoft\Office\16.0\Outlook\Security\
- Outlook 2013: HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Outlook\Security\

Cercare la chiave EnableUnsafeClientMailRules. Se è presente ed è impostata su 1, la patch di protezione di Outlook è stata ignorata e il computer è vulnerabile ad attacchi maschera/regole. Se il valore è 0, l'azione "Avvia applicazione" è disattivata.  Se è installata la versione aggiornata e applicate le patch di Outlook e questa chiave del Registro di sistema non è presente, un sistema non è esposto a questo tipo di attacchi.

I clienti con le installazioni di Exchange locale è consigliabile utilizzare blocco delle versioni precedenti di Outlook che non dispongono di patch disponibili. Informazioni su questa procedura sono disponibili nell'articolo [Configure Outlook client blocco](https://technet.microsoft.com/en-us/library/dd335207(v=exchg.150).aspx).

## <a name="secure-office-365-like-a-cybersecurity-pro"></a>Protezione di Office 365 come alla sicurezza informatica pro
La sottoscrizione a Office 365 è dotato di un insieme completo di funzionalità di protezione che è possibile utilizzare per proteggere i dati e gli utenti.  Utilizzare il [roadmap di protezione di Office 365: principali priorità per i primi 30 giorni, 90 giorni e oltre](https://support.office.com/article/Office-365-security-roadmap-Top-priorities-for-the-first-30-days-90-days-and-beyond-28c86a1c-e4dd-4aad-a2a6-c768a21cb352) per l'implementazione Microsoft di procedure consigliate per la protezione di Office 365 tenant.
- Attività per raggiungere i primi 30 giorni.  Questi hanno effetto immediato e sono basso impatto per gli utenti.
- Attività da eseguire per 90 giorni. Queste un po' di tempo maggiore pianificare e implementare ma migliorare notevolmente le condizioni di sicurezza generali.
- Oltre a 90 giorni. Questi miglioramenti build per il lavoro di 90 giorni primo.

## <a name="see-also"></a>Vedere anche:
- [Dannoso le regole di Outlook](https://silentbreaksecurity.com/malicious-outlook-rules/) per SilentBreak protezione posta sulle regole vettoriale fornisce un esame dettagliato di come le regole di Outlook. 
- [MAPI su HTTP e Mailrule Pwnage](https://sensepost.com/blog/2016/mapi-over-http-and-mailrule-pwnage/) sul blog Sensepost su Mailrule Pwnage viene illustrato uno strumento denominato righello che consente di sfruttare le cassette postali tramite le regole di Outlook.
- [Shell e moduli di outlook](https://sensepost.com/blog/2017/outlook-forms-and-shells/) nel blog Sensepost sui moduli rischio vettoriale. 
- [Codebase righello](https://github.com/sensepost/ruler)
- [Indicatori di righello di compromissione](https://github.com/sensepost/notruler/blob/master/iocs.md)