---
title: Rilevare e correggere le regole di Outlook e gli attacchi per inIezioni di moduli personalizzati in Office 365
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 04/23/2018
ms.audience: ITPro
ms.topic: article
ms.collection:
- o365_security_incident_response
- M365-security-compliance
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
description: Informazioni su come riconoscere e correggere le regole di Outlook e gli attacchi per iniezioni di moduli personalizzati in Office 365
ms.openlocfilehash: 59d45e50e15e3709c8a041ead59b8cc6e2a38306
ms.sourcegitcommit: 8657e003ab1ff49113f222d1ee8400eff174cb54
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/16/2019
ms.locfileid: "30656062"
---
# <a name="detect-and-remediate-outlook-rules-and-custom-forms-injections-attacks-in-office-365"></a>Rilevare e risolvere gli attacchi injection alle regole e ai moduli personalizzati di Outlook in Office 365

**Riepilogo** Informazioni su come riconoscere e correggere le regole di Outlook e gli attacchi per iniezioni di moduli personalizzati in Office 365.

## <a name="what-is-the-outlook-rules-and-custom-forms-injection-attack"></a>Che cos'è l'attacco delle regole di Outlook e dell'iniezione di moduli personalizzati?
Dopo che un utente malintenzionato ha violato un account nel tuo contratto di locazione ed è entrato, ci sarà una soluzione per cercare di stabilire un modo per rimanere o un modo per tornare indietro dopo che sono stati scoperti e rimossi. Si tratta di una chiamata che istituisce un meccanismo di persistenza. Due modi per eseguire questa operazione sono lo sfruttamento delle regole di Outlook o la possibilità di inserire moduli personalizzati in Outlook.
In entrambi i casi, la regola o la maschera viene sincronizzata dal servizio cloud verso il basso nel client desktop, quindi un formato completo e una nuova installazione del software client non eliminano il meccanismo di iniezione. Ciò è dovuto al fatto che, quando il software client di Outlook si riconnette alla cassetta postale nel cloud, riscaricherà le regole e i moduli dal cloud. Dopo che le regole e i moduli sono stati attivati, l'utente malintenzionato li utilizza per eseguire codice remoto o personalizzato, in genere per installare malware nel computer locale. Il malware quindi ri-ruba le credenziali o esegue altre attività illecite. La buona notizia è che se si mantiene i client con patch per la versione più recente, non si è vulnerabili alla minaccia come le impostazioni predefinite del client Outlook correnti bloccano entrambi i meccanismi. 

Gli attacchi in genere seguono questi modelli:

Utilizzo delle regole
1. Il nome utente e la password di uno dei tuoi utenti vengono rubati dall'utente malintenzionato.
2. L'utente malintenzionato accede quindi alla cassetta postale di Exchange per gli utenti. È possibile che la cassetta postale sia in Exchange Online o in Exchange locale.
3. L'utente malintenzionato crea quindi una regola di inoltro nella cassetta postale che viene attivata quando la cassetta postale riceve un messaggio di posta elettronica che corrisponde ai criteri della regola. I criteri della regola e il contenuto della posta elettronica dei trigger sono fatti su misura per l'altro.
4. L'aggressore invia il messaggio di posta elettronica all'utente che usa la propria cassetta postale normalmente.
5. Quando viene ricevuto il messaggio di posta elettronica, viene attivata la regola. L'azione della regola è in genere quella di avviare un'applicazione su un server remoto (WebDAV).
6. L'applicazione in genere installa malware, ad esempio [PowerShell Empire](https://www.powershellempire.com/), localmente nel computer dell'utente.
7. Il malware consente all'utente malintenzionato di riportare le credenziali dal computer locale e di eseguire altre attività dannose.

L'exploit dei moduli
1. Il nome utente e la password di uno dei tuoi utenti vengono rubati dall'utente malintenzionato.
2. L'utente malintenzionato accede quindi alla cassetta postale di Exchange per gli utenti. È possibile che la cassetta postale sia in Exchange Online o in Exchange locale.
3. L'aggressore crea quindi un modello di modulo di posta elettronica personalizzato e lo inserisce nella cassetta postale dell'utente.  Il modulo personalizzato viene attivato quando la cassetta postale riceve un messaggio di posta elettronica che richiede alla cassetta postale di caricare il modulo personalizzato. Il modulo personalizzato e il formato del messaggio di posta elettronica sono fatti su misura per l'altro.
4. L'utente malintenzionato invia il messaggio di posta elettronica al mittente, che utilizza normalmente la propria cassetta postale.
5. Quando viene ricevuto il messaggio di posta elettronica, il modulo viene caricato. Il modulo avvia un'applicazione su un server remoto (WebDAV).
6. L'applicazione in genere installa malware, ad esempio [PowerShell Empire](https://www.powershellempire.com/), localmente nel computer dell'utente.
7. Il malware consente all'utente malintenzionato di riportare le credenziali dal computer locale e di eseguire altre attività dannose.


## <a name="what-a-rules-and-custom-forms-injection-attack-might-look-like-office-365"></a>Che cosa può essere simile a Office 365?

Questi meccanismi di persistenza sono improbabili da essere notati dagli utenti e, in alcuni casi, potrebbero anche essere invisibili.  In questo articolo viene descritto come cercare uno dei sette segni (indicatori di compromesso) elencati di seguito. Se si trova uno di questi, è necessario eseguire i passaggi di correzione.

- Indicatori del compromesso delle regole
    - L'azione regola consiste nell'avviare un'applicazione.
    - La regola fa riferimento a un EXE, a un ZIP o a un URL.
    - Nel computer locale, cercare le nuove partenze del processo che provengono da Outlook PID.
- Indicatori del compromesso su moduli personalizzati 
    - Modulo personalizzato presente salvato come classe del messaggio.
    - La classe Message contiene codice eseguibile.
    - In genere archiviati nella raccolta moduli personali o nella cartella posta in arrivo.
    - Il modulo è denominato IPM. Nota. [nome personalizzato].

## <a name="steps-for-finding-signs-of-this-attack-and-confirming-it"></a>Passaggi per individuare i segni di questo attacco e confermarlo
È possibile utilizzare uno dei due metodi seguenti per confermare l'attacco.
- Esaminare manualmente le regole e i moduli per ogni cassetta postale utilizzando il client di Outlook.  Questo metodo è accurato, ma è possibile controllare solo l'utente della cassetta postale in un momento che può richiedere molto tempo se si dispone di molti utenti da controllare.  Può anche provocare una violazione del computer in cui si esegue il controllo.
- Utilizzare lo script PowerShell [Get-AllTenantRulesAndForms. ps1](https://github.com/OfficeDev/O365-InvestigationTooling/blob/master/Get-AllTenantRulesAndForms.ps1) per scaricare automaticamente tutte le regole di inoltro della posta e i moduli personalizzati per tutti gli utenti nel proprio contratto di locazione. Questo è il metodo più rapido e sicuro con il minor numero di overhead.


### <a name="confirm-the-rules-attack-using-the-outlook-client"></a>Confermare l'attacco delle regole tramite il client di Outlook
1. Aprire il client Outlook degli utenti come utente.  È possibile che l'utente abbia bisogno di assistenza per esaminare le regole sulla propria cassetta postale.
2. Fare riferimento a [gestire i messaggi di posta elettronica utilizzando le regole](https://support.office.com/article/manage-email-messages-by-using-rules-c24f5dea-9465-4df4-ad17-a50704d66c59#ID0EAABAAA=2010) dell'articolo per le procedure su come aprire l'interfaccia delle regole nelle versioni 2007, 2010 o 2013 di Outlook.
3. Cercare le regole che l'utente non ha creato o qualsiasi regola imprevista o regole con nomi sospetti.
4. Esaminare la descrizione della regola per le azioni delle regole che iniziano e applicano o fanno riferimento a un oggetto. EXE,. File ZIP o per l'avvio di un URL.
5. Cercare eventuali nuovi processi che iniziano a utilizzare l'ID del processo di Outlook.  Fare riferimento a [Find the process ID](https://docs.microsoft.com/windows-hardware/drivers/debugger/finding-the-process-id).

### <a name="steps-to-confirm-the-forms-attack-using-the-outlook-client"></a>Procedura per confermare l'attacco dei moduli tramite il client di Outlook
1. Aprire il client Outlook utente come utente.
2. Attenersi alla procedura descritta in, [Mostra la scheda sviluppo](https://support.office.com/article/show-the-developer-tab-e1192344-5e56-4d45-931b-e5fd9bea2d45) per la versione degli utenti di Outlook.
3. Aprire la scheda ora visibile per gli sviluppatori in Outlook e fare clic su **Progetta modulo**.
4. Selezionare la **cartella posta in arrivo** dall'elenco **Cerca in** . Cercare eventuali moduli personalizzati.  I moduli personalizzati sono abbastanza rari che, se si dispone di tutti i moduli personalizzati, è opportuno un aspetto più approfondito.
5. Esaminare i moduli personalizzati, in particolare quelli contrassegnati come nascosti.
6. Aprire tutti i moduli personalizzati e nel gruppo **modulo** fare clic su **Visualizza codice** per vedere cosa viene eseguito quando la maschera viene caricata.

### <a name="steps-to-confirm-the-rules-and-forms-attack-using-powershell"></a>Passaggi per confermare le regole e i moduli di attacco tramite PowerShell
Il modo più semplice per verificare una regola o un attacco di moduli personalizzati consiste nell'eseguire lo script di PowerShell [Get-AllTenantRulesAndForms. ps1](https://github.com/OfficeDev/O365-InvestigationTooling/blob/master/Get-AllTenantRulesAndForms.ps1) .  Questo script si connette a tutte le cassette postali del tenant e Scarica tutte le regole e i moduli in due file. csv.

#### <a name="pre-requisites"></a>Requisiti preliminari
Sarà necessario disporre di diritti di amministratore globale per eseguire lo script perché lo script si connette a tutte le cassette postali del contratto di locazione per leggere le regole e i moduli.

1. Accedere al computer in cui verrà eseguito lo script con i diritti di amministratore locale.
2. Scaricare o copiare lo script Get-AllTenantRulesAndForms. ps1 da GitHub in una cartella dalla quale verrà eseguito.  Lo script creerà due file con timbro data in questa cartella, MailboxFormsExport-yyyy-mm-dd. csv e MailboxRulesExport-yyyy-mm-dd. csv.
3. Aprire un'istanza di PowerShell come amministratore e aprire la cartella in cui è stato salvato lo script.
4. Eseguire la riga di comando di PowerShell `.\Get-AllTenantRulesAndForms.ps1`come segue .\Get-AllTenantRulesAndForms.ps1

#### <a name="interpreting-the-output"></a>Interpretare l'output

MailboxRulesExport-*yyyy-mm-gg*. csv – esaminare le regole (una per riga) per le condizioni di azione che includono applicazioni o eseguibili.
- ActionType (colonna A) – se viene visualizzato il valore "ID_ACTION_CUSTOM", è probabile che la regola sia dannosa.
- IsPotentiallyMalicious (colonna D) – se questo valore è "TRUE", la regola è probabile che sia dannoso.
- ActionCommand (colonna G): se viene elencata un'applicazione o un file con estensione exe, zip o una voce che fa riferimento a un URL che non dovrebbe essere presente, la regola è probabilmente dannosa.

MailboxFormsExport-*yyyy-mm-gg*. csv – in generale, l'utilizzo di moduli personalizzati è molto raro.  Se si trova qualsiasi in questa cartella di lavoro, è possibile aprire la cassetta postale dell'utente ed esaminare il modulo stesso.  Se l'organizzazione non lo ha messo intenzionalmente, è probabile che sia dannoso.



## <a name="how-to-stop-and-remediate-the-outlook-rules-and-forms-attack"></a>Come arrestare e correggere le regole di Outlook e l'attacco dei moduli
Se si riscontrano prove di uno di questi attacchi, la correzione è semplice, è sufficiente eliminare la regola o la maschera dalla cassetta postale. È possibile eseguire questa operazione con il client di Outlook o tramite Remote PowerShell per rimuovere le regole.

### <a name="using-outlook"></a>Utilizzo di Outlook
1. Identificare tutti i dispositivi che l'utente ha utilizzato con Outlook.  Tutti devono essere puliti da possibili malware.  Non consentire all'utente di accedere e utilizzare la posta elettronica fino a quando tutti i dispositivi vengono puliti.
2. Seguire la procedura descritta in [eliminare una regola](https://support.office.com/article/Delete-a-rule-2F0E7139-F696-4422-8498-44846DB9067F) per ogni dispositivo.
3. Se non si è sicuri della presenza di altri malware, è possibile formattare e reinstallare tutto il software nel dispositivo.  Per i dispositivi mobili è possibile seguire i passaggi dei costruttori per reimpostare il dispositivo nell'immagine Factory.
4. Installare le versioni più aggiornate di Outlook.  Tenere presente che la versione corrente di Outlook blocca entrambi i tipi di questo attacco per impostazione predefinita.
5. Dopo che tutte le copie offline della cassetta postale sono state rimosse, reimpostare la password dell'utente (utilizzare un valore di alta qualità) e seguire i passaggi descritti nell'installazione di autenticazione a più [fattori per gli utenti di Office 365 se l'](https://support.office.com/article/Set-up-multi-factor-authentication-for-Office-365-users-8f0454b2-f51a-4d9c-bcde-2c48e41621c6) AMF non è già stata abilitata. In questo modo, le credenziali dell'utente non vengono esposte tramite altri strumenti (ad esempio, il riutilizzo di phishing o password).

### <a name="using-powershell"></a>Utilizzo di PowerShell
Sono disponibili due cmdlet di PowerShell remoti che è possibile utilizzare per rimuovere o disabilitare le regole pericolose. Basta seguire la procedura.
 
Passaggi per le cassette postali che si trovano in un server Exchange

1. Connettersi al server di Exchange tramite Remote PowerShell. Seguire la procedura descritta in [Connect to Exchange servers using Remote PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-server/connect-to-exchange-servers-using-remote-powershell?view=exchange-ps).
2. Se si desidera rimuovere completamente una singola regola, più regole o tutte le regole di una cassetta postale, utilizzare il [cmdlet Remove-Inbox Rule ](https://docs.microsoft.com/powershell/module/exchange/mailboxes/Remove-InboxRule?view=exchange-ps)-utilizzarla per rimuovere completamente una, più o tutte le regole dalla cassetta postale.
3. Se si desidera mantenere la regola e il relativo contenuto per ulteriori indagini, utilizzare il [cmdlet Disable-InboxRule](https://technet.microsoft.com/en-us/library/dd298120(v=exchg.160).aspx). 

Passaggi per le cassette postali in Exchange Online
1. Seguire la procedura descritta in [Connect to Exchange Online using PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell?view=exchange-ps).
2.  Se si desidera rimuovere completamente una singola regola, più regole o tutte le regole di una cassetta postale, utilizzare il [cmdlet Remove-Inbox Rule](https://docs.microsoft.com/powershell/module/exchange/mailboxes/Remove-InboxRule?view=exchange-ps).
3.  Se si desidera mantenere la regola e il relativo contenuto per ulteriori indagini, utilizzare il [cmdlet Disable-InboxRule](https://technet.microsoft.com/en-us/library/dd298120(v=exchg.160).aspx). 

## <a name="how-to-minimize-future-attacks"></a>Come ridurre al minimo gli attacchi futuri

### <a name="first-protect-your-accounts"></a>Primo: Proteggi gli account

Le regole e gli exploit dei moduli vengono utilizzati solo da un utente malintenzionato dopo che hanno rubato o violato uno degli account degli utenti. Pertanto, il primo passaggio per impedire l'utilizzo di tali exploit nei confronti dell'organizzazione consiste nel proteggere in modo aggressivo gli account utente.  Alcuni dei modi più comuni in cui gli account vengono violati sono gli attacchi di phishing o di spruzzatura delle [password](http://www.dabcc.com/microsoft-defending-against-password-spray-attacks/) .



Il modo migliore per proteggere gli account utente e in particolare gli account di amministratore consiste nel [configurare l'autenticazione a più fattori per gli utenti di Office 365](https://support.office.com/article/set-up-multi-factor-authentication-for-office-365-users-8f0454b2-f51a-4d9c-bcde-2c48e41621c6).  È inoltre necessario:
<ol>
    <li>Monitorare la modalità <a href="https://docs.microsoft.com/azure/active-directory/active-directory-view-access-usage-reports">di accesso e utilizzo</a>degli account utente. Non è possibile impedire la violazione iniziale, ma è possibile ridurre la durata e l'impatto della violazione rilevando prima. È possibile utilizzare questi: <a href="https://support.office.com/article/overview-of-office-365-cloud-app-security-81f0ee9a-9645-45ab-ba56-de9cbccab475">criteri di protezione delle app cloud di Office 365</a> per monitorare gli account e allertare attività inusuali. 
        <ol type="a">
            <li><b>Tentativi di accesso non riusciti multipli</b> Questo criterio profila l'ambiente e attiva gli avvisi quando gli utenti eseguono più attività di accesso non riuscite in una singola sessione rispetto alla linea di base acquisita, il che potrebbe indicare una tentativo di violazione.</li>
            <li><b>Viaggi impossibili</b> - Questo criterio profila l'ambiente e attiva gli avvisi quando vengono rilevate attività dallo stesso utente in posizioni diverse entro un periodo di tempo inferiore a quello previsto tra le due posizioni. Questo potrebbe indicare che un utente diverso utilizza le stesse credenziali. Il rilevamento di questo comportamento anomalo richiede un periodo di apprendimento iniziale di sette giorni durante il quale viene illustrato il modello di attività di un nuovo utente.</li>
            <li><b>Attività rappresentata insolita (per utente)</b> - Questo criterio profila l'ambiente e attiva gli avvisi quando gli utenti eseguono più attività rappresentate in una singola sessione rispetto alla linea di base appresa, il che potrebbe indicare una tentativo di violazione.</li>
        </ol>
    </li>
    <li>Sfruttare uno strumento come <a href="https://securescore.office.com/">Office 365 Secure Score</a> per gestire le configurazioni e i comportamenti di sicurezza degli account. 
    </li>
</ol> 

### <a name="second-keep-your-outlook-clients-current"></a>Secondo: mantenere aggiornati i client Outlook
Le versioni completamente aggiornate e con patch di Outlook 2013 e 2016 disabilitano per impostazione predefinita l'azione regola/maschera "Avvia applicazione".  In questo modo, anche se un utente malintenzionato viola l'account, la regola e le azioni del modulo verranno bloccate.  È possibile installare gli aggiornamenti più recenti e le patch di sicurezza attenendosi alla procedura descritta in [Install Office Updates](https://support.office.com/article/Install-Office-updates-2ab296f3-7f03-43a2-8e50-46de917611c5).

Ecco le versioni delle patch per i client Outlook 2013 e 2016:
- Outlook 2013:15.0.4937.1000 o versione successiva
- Outlook 2016:16.0.4534.1001 o versione successiva

Per ulteriori informazioni sulle singole patch di sicurezza, vedere:

- [Patch di sicurezza di Outlook 2013](https://support.microsoft.com/en-us/help/3191938) 
- [Patch di sicurezza di Outlook 2016](https://support.microsoft.com/en-us/help/3191883)

### <a name="third-monitor-your-outlook-clients"></a>Terzo: monitorare i client Outlook
Si noti che, anche con le patch e gli aggiornamenti installati, è possibile che un utente malintenzionato modifichi la configurazione del computer locale per riattivare il comportamento di avvio dell'applicazione. È possibile utilizzare la [Gestione avanzata dei criteri di gruppo](https://docs.microsoft.com/microsoft-desktop-optimization-pack/agpm/) per monitorare e applicare i criteri del computer locale nei client.  
È possibile verificare se l'impostazione "Avvia applicazione" è stata riattivata tramite una sostituzione nel registro di sistema utilizzando le informazioni [visualizzate in come visualizzare il registro System di Windows utilizzando le versioni a 64 bit](https://support.microsoft.com/en-us/help/305097/how-to-view-the-system-registry-by-using-64-bit-versions-of-windows).  Controllare queste sottochiavi: 

- Outlook 2016: HKEY_CURRENT_USER\Software\Microsoft\Office\16.0\Outlook\Security\
- Outlook 2013: HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Outlook\Security\

Cercare la chiave EnableUnsafeClientMailRules. Se è presente ed è impostato su 1, la patch di sicurezza di Outlook è stata ignorata e il computer è vulnerabile all'attacco maschera/regole. Se il valore è 0, l'azione "Avvia applicazione" è disattivata.  Se è installata la versione aggiornata e con patch di Outlook e questa chiave del registro di sistema non è presente, non è vulnerabile a questi attacchi.

I clienti con installazioni di Exchange locali dovrebbero considerare di bloccare le versioni precedenti di Outlook che non dispongono di patch disponibili. Informazioni dettagliate su questo processo sono disponibili nell'articolo [configure Outlook client blocking](https://technet.microsoft.com/en-us/library/dd335207(v=exchg.150).aspx).

## <a name="secure-office-365-like-a-cybersecurity-pro"></a>Protezione di Office 365 come un Cybersecurity Pro
L'abbonamento a Office 365 è dotato di un potente set di funzionalità di sicurezza che è possibile utilizzare per proteggere i dati e gli utenti.  Utilizzare la Guida di [orientamento alla sicurezza di office 365: priorità principali per i primi 30 giorni, 90 giorni e oltre](https://support.office.com/article/Office-365-security-roadmap-Top-priorities-for-the-first-30-days-90-days-and-beyond-28c86a1c-e4dd-4aad-a2a6-c768a21cb352) per implementare le procedure consigliAte di Microsoft consigliati per la protezione del tenant di Office 365.
- Attività da eseguire nei primi 30 giorni.  Tali effetti hanno un impatto immediato e sono di scarso effetto per gli utenti.
- Attività da eseguire in 90 giorni. Questi richiedono un po' più di tempo per pianificare e implementare, ma migliorare notevolmente la posizione di sicurezza.
- Oltre 90 giorni. Questi miglioramenti vengono costruiti nei primi 90 giorni di lavoro.

## <a name="see-also"></a>Vedere anche:
- Le [regole di Outlook dannose](https://silentbreaksecurity.com/malicious-outlook-rules/) da SilentBreak post sulla sicurezza su Rules Vector fornisce una panoramica dettagliata del modo in cui le regole di Outlook. 
- [MAPI su http e Mailrule Pwnage](https://sensepost.com/blog/2016/mapi-over-http-and-mailrule-pwnage/) sul Blog Sensepost su Mailrule Pwnage discute uno strumento chiamato righello che consente di sfruttare le cassette postali tramite le regole di Outlook.
- [Moduli di Outlook e Shell](https://sensepost.com/blog/2017/outlook-forms-and-shells/) sul Blog di Sensepost sul vettore di minacce di moduli. 
- [Codebase del righello](https://github.com/sensepost/ruler)
- [Indicatori del righello di compromesso](https://github.com/sensepost/notruler/blob/master/iocs.md)