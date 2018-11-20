---
title: Creare, testare e ottimizzare un criterio di prevenzione della perdita dei dati
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: ''
ms.audience: Admin
ms.topic: article
f1_keywords:
- ms.o365.cc.NewPolicyFromTemplate
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Strat_O365_IP
search.appverid:
- MET150
ms.assetid: 59414438-99f5-488b-975c-5023f2254369
description: "Il metodo più semplice e più comune per acquisire familiarità con i criteri DLP consiste nell'utilizzare uno dei modelli inclusi in Office 365. "
ms.openlocfilehash: 1d4697811a5d8dd426fed80d3d60bcd2fbea6335
ms.sourcegitcommit: 42c7ad69f95fc4d2de13293b39cc44931b9f82e6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/14/2018
ms.locfileid: "26522788"
---
# <a name="create-test-and-tune-a-dlp-policy"></a>Creare, testare e ottimizzare un criterio di prevenzione della perdita dei dati

**Entità dell'autore** </br>
Paul Cunningham, Microsoft MVP </br>
[365 pratici](https://practical365.com/) </br>
[@Practical365](https://twitter.com/practical365)</br>
__________________________________________________

Prevenzione della perdita di dati è una funzionalità di conformità di Office 365 progettato per aiutare l'organizzazione impedisce l'esposizione accidentale o intenzionale delle informazioni riservate a parti indesiderate. DLP ha le sue radici in Exchange Server ed Exchange Online ed è applicabile in SharePoint Online e OneDrive for Business.

DLP utilizza un motore di analisi del contenuto per esaminare il contenuto dei messaggi di posta elettronica e dei file, alla ricerca di informazioni riservate, ad esempio numeri di carta di credito e informazioni personali (PII). Informazioni riservate consigliabile in genere non essere inviate nella posta elettronica o inclusi nei documenti, senza eseguire passaggi aggiuntivi, ad esempio la crittografia del messaggio di posta elettronica o i file. Utilizzare DLP è possibile rileva informazioni riservate e agire come:

- Registrare l'evento ai fini del controllo
- Visualizzare un messaggio di avviso all'utente finale che invia la posta elettronica o condivisione file
- Bloccare attivamente la posta elettronica o il file di condivisione da in corso

Talvolta i clienti eliminare DLP dal momento che non considerano il tipo di dati che necessita di protezione. Il presupposto è che i dati riservati, ad esempio cliniche o informazioni finanziarie, esistano solo per uso nei settori dell'assistenza sanitaria o per le aziende che eseguono negozi online. Ma qualunque azienda può gestire informazioni riservate a intervalli regolari, anche se è non realizzare. Un foglio di calcolo dei nomi dei dipendenti e le date di nascita sono riservate solo come un foglio di calcolo dei nomi dei clienti e i dettagli di carta di credito. E questo tipo di informazioni tende a float attorno numero maggiore di quello previsto, man mano che i dipendenti in modalità non interattiva va sulle attività quotidiane meditare nothing esportare un file CSV da un sistema e invio tramite posta elettronica a un utente. Potrebbe inoltre essere la frequenza con cui i dipendenti inviare messaggi di posta elettronica contenente carta di credito o bancarie senza considerare le conseguenze.

## <a name="how-sensitive-information-is-detected-by-dlp"></a>Modalità rileva informazioni riservate DLP

Informazioni riservate sono identificate da espressioni regolari (RegEx) criteri di ricerca, in combinazione con con altri indicatori, ad esempio alla prossimità di alcune parole chiave per i criteri di corrispondenza. Un esempio di questo è il numero di carta di credito. Un numero di carta di credito VISA ha 16 cifre. Tuttavia, tali cifre possono essere scritti in diversi modi, ad esempio 1111-1111-1111-1111 1111 1111 1111 1111 o 1111111111111111.

Qualsiasi stringa 16 cifre non è necessariamente un numero di carta di credito, può trattarsi di un numero di ticket da un sistema di Guida da tavolo o un numero di serie del componente hardware. Per verificare la differenza tra una stringa di 16 cifre dannosa e un numero di carta di credito, un calcolo che eseguite (checksum) per verificare che i numeri di ricerca di una corrispondenza nota da diversi marchi di carta di credito.

Inoltre, alla prossimità di parole chiave, ad esempio "VISA" o "AMEX", insieme alla prossimità per i valori di data che potrebbero essere la data di scadenza della carta di credito, è anch'essi decidere se i dati sono un numero di carta di credito o meno.

In altre parole, DLP è in genere smart di riconoscono la differenza tra queste due testi in un messaggio di posta elettronica:

- "Si ordinare me un nuovo computer portatile. Utilizzare il numero VISA 1111-1111-1111-1111, scadenza 11/22 e invia un messaggio la data di consegna stimata dopo avere".
- "Il numero di serie portatili è 2222-2222 2222 2222 ed è stato acquistato su 11/2010. Tra l'altro, sia personali visa viaggi approvato ancora?"

In questo [argomento su tipi di informazioni riservate](what-the-sensitive-information-types-look-for.md) che illustra la modalità di rilevamento di ogni tipo di informazioni è un riferimento valido per mantenere contrassegnato dal segnalibro.

## <a name="where-to-start-with-data-loss-prevention"></a>La posizione in cui iniziare con prevenzione della perdita di dati

Quando il rischio di perdita di dati non interamente chiara, è difficile scoprire dove esattamente deve iniziare con l'implementazione di DLP. Fortunatamente, è possono eseguire i criteri DLP nella "modalità test", che consente di valutare l'efficacia e accuratezza prima di attivare.

I criteri DLP per Exchange Online possono essere gestiti tramite l'interfaccia di amministrazione di Exchange. Ma è possibile configurare i criteri DLP per tutti i carichi di lavoro tramite la sicurezza e conformità tecnico, in modo che sia utilizzerà per dimostrazioni in questo articolo. Nel centro conformità protezione sono disponibili i criteri DLP in **prevenzione della perdita di dati** > **criteri**. Fare clic su **Crea un criterio** per l'avvio.

Office 365 offre una gamma di [modelli di criteri DLP](what-the-dlp-policy-templates-include.md) è possibile utilizzare per creare criteri DLP. Si supponga che l'utente sia un business australiano. È possibile filtrare i modelli di criteri per visualizzare solo a quelli di interesse per Australia, che possono essere suddivisi in categorie generali di finanziario, medici e lo stato e sulla Privacy.

![Opzione per scegliere i paesi](media/DLP-create-test-tune-choose-country.png)

Per questa dimostrazione sarà scelte dati australiano personalmente identificabili informazioni personali, che include i tipi di informazioni del numero della patente di Guida e del numero di File imposte australiano (TFN).

![Opzione per scegliere un modello di criteri](media/DLP-create-test-tune-choose-policy-template.png)

Assegnare un nome al nuovo criterio DLP. Il nome predefinito corrisponde il modello di criterio DLP, ma è necessario scegliere un nome più descrittivo personale, in quanto più criteri possono essere creati utilizzando lo stesso modello.

![Opzione denominare i criteri](media/DLP-create-test-tune-name-policy.png)

Scegliere i percorsi che il criterio verrà applicato a. I criteri DLP applicabili a Exchange Online, SharePoint Online e OneDrive for Business. Verrà lasciare questo criterio configurato per applicare a tutte le posizioni.

![Opzione per scegliere tutti i percorsi](media/DLP-create-test-tune-choose-locations.png)

Il primo passo **Le impostazioni dei criteri** solo accettare i valori predefiniti per il momento. Molti personalizzazione che è possibile procedere nei criteri DLP non esiste, ma le impostazioni predefinite sono un punto di partenza adeguato.

![Opzioni per personalizzare il tipo di contenuto per la protezione](media/DLP-create-test-tune-default-customization-settings.png)

Dopo aver fatto clic **successivo** verrà visualizzata una pagina di **Impostazioni di criteri** aggiuntiva con ulteriori opzioni di personalizzazione. Per un criterio che si sta testando appena, ecco dove è possibile apportare modifiche.

- Dopo aver disattivato i suggerimenti sui criteri per questo punto, ovvero un passaggio ragionevole da eseguire se solo test esteso e non si desidera visualizzare ancora nulla per gli utenti. Suggerimenti sui criteri visualizzare gli avvisi per gli utenti che stanno per violano un criterio DLP. Ad esempio, un utente di Outlook viene visualizzato un avviso indicante che è stato allegato il file contiene i numeri di carta di credito e genererà loro posta elettronica verranno rifiutati. L'obiettivo di suggerimenti sui criteri è per interrompere il comportamento non conforme prima che venga eseguito.
- È possibile inoltre ho diminuito il numero di istanze di 10 per 1, in modo che questo criterio è in grado di rilevare eventuali condivisione dei dati PII australiano, non appena massa condivisione dei dati.
- Ho inoltre aggiunto un altro destinatario per il posta elettronica rapporto operazioni non consentite.

![Impostazioni di sicurezza aggiuntive](media/DLP-create-test-tune-more-policy-settings.png)

Infine, è possibile una volta configurato questo criterio per l'esecuzione in modalità test inizialmente. Si noti è inoltre disponibile un'opzione per disabilitare i suggerimenti sui criteri, in modalità test. In questo modo la flessibilità necessaria per avere suggerimenti sui criteri abilitati nel criterio, ma decidere se visualizzare o eliminarli durante il test.

![Opzione consente di testare innanzitutto fuori criterio](media/DLP-create-test-tune-test-mode.png)

Nella schermata di revisione finale fare clic su **Crea** per completare la creazione del criterio.

## <a name="test-a-dlp-policy"></a>Testare un criterio DLP

Il nuovo criterio DLP inizierà effetto all'interno di circa 1 ora. È possibile sit e attendere che venga attivato da attività dell'utente normale oppure è possibile provare a attivare manualmente. In precedenza collegati a questo [argomento su tipi di informazioni riservate](what-the-sensitive-information-types-look-for.md), che consente di ottenere informazioni su come attivare DLP corrispondenze.

Ad esempio, il criterio DLP creati per questo articolo verrà rileva i numeri di file fiscale australiano (TFN). In base alla documentazione, la corrispondenza si basa sui criteri seguenti.

![Documentazione su imposte Australia-numero di File](media/DLP-create-test-tune-Australia-Tax-File-Number-doc.png)
 
Per illustrare il rilevamento TFN in modo piuttosto senza punta, un messaggio di posta elettronica con le parole "Identificativo fiscale" e una stringa di 9 cifre vicine verrà rendersi tramite senza problemi. Il motivo che non attiva il criterio DLP è che la stringa di cifre 9 deve passare il checksum indicante che è un TFN valido e non solo dannosa stringhe di numeri.

![Australia identificativo fiscale che non fornisce alcun checksum](media/DLP-create-test-tune-email-test1.png)

Nel confronto, un messaggio di posta elettronica con le parole "Identificativo fiscale" e un TFN valido che passa il valore di checksum attiverà il criterio. Per i record di seguito, TFN utilizzo è stato escluso da un sito Web che genera valido, ma non autentico TFNs. Sono disponibili i siti simili che generano [numeri validi ma falsi carta di credito](http://www.fakecreditcardgenerator.net/). Tali siti sono molto utile perché uno degli errori più comuni commessi durante il test di un criterio DLP sta utilizzando un numero fittizio che non è valido e non si passa il valore di checksum (e pertanto non attiva il criterio).

![Australia identificativo fiscale che passa il valore di checksum](media/DLP-create-test-tune-email-test2.png)

Messaggio di posta elettronica rapporto operazioni non consentite include il tipo di informazioni sensibili rilevato, il numero di istanze sono stato rilevato e il livello di probabilità del rilevamento.

![Rapporto operazioni non consentita con identificativo fiscale rilevato](media/DLP-create-test-tune-email-incident-report.png)

Se si lascia il criterio DLP in modalità test e analizzare i messaggi di posta elettronica rapporto operazioni non consentite, è possibile avviare avere un'idea dell'accuratezza dei criteri DLP e l'efficacia sarà quando viene applicata. Oltre ai rapporti operazioni non consentiti, è possibile [utilizzare i rapporti DLP](view-the-dlp-reports.md) per visualizzare una visualizzazione aggregata di corrispondenze di criteri tra il tenant.

## <a name="tune-a-dlp-policy"></a>Ottimizzare un criterio DLP

Durante l'analisi si trova il criterio è possibile apportare alcune modifiche al comportano dei criteri. Un semplice esempio, è possibile stabilire che un TFN nella posta elettronica non è un problema (è possibile considerare ancora è, ma passiamo a utilizzarlo per fini dimostrativi), ma due o più istanze è un problema. Più istanze potrebbero essere uno scenario rischioso, ad esempio un dipendente a un'esportazione CSV dal database di risorse Umane in una parte esterna, ad esempio contabilità servizio esterno. Si preferisce senza dubbio qualcosa di rilevare e bloccare.

Nel centro conformità sicurezza è possibile modificare un criterio esistente per regolare il comportamento.

![Opzione per modificare i criteri](media/DLP-create-test-tune-edit-policy.png)
 
È possibile modificare le impostazioni della posizione in modo che il criterio viene applicato solo a carichi di lavoro specifici o agli account e ai siti specifici.

![Opzioni per scegliere i percorsi specifici](media/DLP-create-test-tune-edit-locations.png)

È inoltre possibile regolare le impostazioni dei criteri e modificare le regole in base alle proprie esigenze.

![Opzione per modificare una regola](media/DLP-create-test-tune-edit-rule.png)

Quando si modifica una regola all'interno di un criterio DLP è possibile modificare:

- Le condizioni, inclusi il tipo e numero di istanze di dati riservati attiveranno la regola.
- Azioni da eseguire, ad esempio la limitazione dell'accesso al contenuto.
- Notifiche di utente, sono riportati i suggerimenti criteri visualizzati all'utente nel browser web o client posta elettronica.
- Utente ha la priorità, che determina se gli utenti possono scegliere di procedere con il messaggio di posta elettronica o comunque la condivisione di file.
- Rapporti operazioni non consentite per notificare gli amministratori.

![Opzioni per modificare parti di una regola](media/DLP-create-test-tune-editing-options.png)

Per questa dimostrazione è stata aggiunta notifiche utente per il criterio (prestare attenzione eseguire questa operazione senza formazione degli utenti adeguata), e consentita agli utenti di modificare il criterio con una giustificazione aziendale o in quanto possono contrassegnare come falso positivo. Si noti che è possibile personalizzare il testo di suggerimento messaggio di posta elettronica e criteri anche se si desidera includere informazioni aggiuntive sui criteri dell'organizzazione o richiedere agli utenti di contattare il supporto se dispongono di domande.

![Opzioni per le notifiche di utente e le sostituzioni](media/DLP-create-test-tune-user-notifications.png)

Il criterio contiene due regole per la gestione del volume elevata e ridotta, prestare attenzione per entrambi con le azioni che desidera modificare. Si tratta di un'opportunità di trattare casi in modo diverso a seconda delle relative caratteristiche. Ad esempio, può consentire l'override delle violazioni volume ridotto, ma non consentire le sostituzioni le violazioni volume elevato di.

![Una regola per volume elevato e una regola per il volume bassa](media/DLP-create-test-tune-two-rules.png)

Inoltre, se si desidera bloccare o limitare l'accesso al contenuto presente in violazione del criterio in realtà, è necessario configurare un'azione della regola non venga richiesto.

![Opzione per limitare l'accesso al contenuto](media/DLP-create-test-tune-restrict-access-action.png)

Dopo aver salvato le modifiche alle impostazioni dei criteri, è possibile inoltre necessario tornare alla pagina principale delle impostazioni per il criterio e abilitare l'opzione mostrare i suggerimenti sui criteri per gli utenti durante il criterio in modalità test. Si tratta in modo efficace per introdurre criteri DLP per gli utenti finali ed effettuare formazione degli utenti, senza mettere a rischio troppi falsi positivi sulla produttività.

![Opzione per visualizzare i suggerimenti sui criteri in modalità test](media/DLP-create-test-tune-show-policy-tips.png)

Sul server sul lato (cloud lato o se si preferisce), potrebbe non avranno effetto immediatamente, a causa di vari intervalli di elaborazione. Se si sta effettuando la modifica di un criterio DLP che visualizzerà nuovi suggerimenti dei criteri a un utente, l'utente potrebbe non visualizzare le modifiche hanno effetto immediato nei client Outlook, che controlla le modifiche apportate ai criteri ogni 24 ore. Se si desidera per velocizzare le operazioni per il test, è possibile utilizzare questa correzione del Registro di sistema per [cancellare l'ultimo download timestamp dalla chiave PolicyNudges](https://support.microsoft.com/en-au/help/2823261/changes-to-a-data-loss-prevention-policy-don-t-take-effect-in-outlook?__hstc=18650278.46377037dc0a82baa8a30f0ef07a7b2f.1538687978676.1538693509953.1540315763430.3&__hssc=18650278.1.1540315763430&__hsfp=3446956451). Outlook scaricheranno le informazioni più aggiornate di criteri successivo riavviarlo e iniziare la composizione di un messaggio di posta elettronica.

Se si dispone di suggerimenti sui criteri abilitati, l'utente inizia a visualizzare i suggerimenti forniti in Outlook e segnala falsi positivi all'utente quando si verificano.

![Suggerimento per il criterio con l'opzione per segnala falso positivo](media/DLP-create-test-tune-policy-tip-in-outlook.png)

## <a name="investigate-false-positives"></a>Analizzare i falsi positivi

Modelli di criteri DLP non sono perfetti direttamente all'esterno della casella. È probabile che sia possibile trovare alcuni falsi positivi che si verificano nell'ambiente, pertanto è pertanto importante semplificare la come in una distribuzione DLP, il tempo dedicato per testare e ottimizzare i criteri in modo adeguato.

Di seguito è riportato un esempio di un falso positivo. Questo messaggio di posta elettronica è piuttosto dannosa. L'utente è fornendo il numero di cellulare a un utente e tra loro firma di posta elettronica.

![Messaggio di posta elettronica con falso positivo](media/DLP-create-test-tune-false-positive-email.png)
 
Ma l'utente visualizza un suggerimento criterio avviso loro che il messaggio di posta elettronica contiene informazioni riservate, in particolare, il numero di licenza del driver australiano.

![Opzione per segnala falso positivo in suggerimento sul criterio](media/DLP-create-test-tune-policy-tip-closeup.png)

L'utente può segnalazione dei falsi positivi e l'amministratore può ricercare sui motivi per cui si è verificato. Posta elettronica rapporto operazioni non consentite il messaggio di posta elettronica è contrassegnato come falso positivo.

![Falsi positivi che illustra rapporto operazioni non consentite](media/DLP-create-test-tune-false-positive-incident-report.png)

Caso di licenza della patente di Guida è un ottimo esempio di approfondire. Il motivo questo falsi positivi si sono verificato che è il "australiano patente" verrà attivata tipo da qualsiasi stringa 9 cifre (anche uno che fa parte di una stringa a 10 cifre), all'interno di 300 prossimità di caratteri per le parole chiave "sydney nsw" (non maiuscole/minuscole). In modo che viene attivato per la firma di posta elettronica e numero di telefono, solo perché l'utente si trova nelle Sydney.

L'aspetto interessante, se "Sydney, NSW" con una virgola, il criterio DLP non viene attivato. È possibile si conosce il motivo per cui una virgola rende eventuali differenze in questo caso, né perché le parole chiave per tipo di informazioni della patente di Guida australiano licenza non sono inclusi altri città e gli stati di Australia, ma vi si passa. Pertanto, cosa si può fare su di esso? Non esiste un paio di opzioni.

Un'opzione è rimuovere tipo di informazioni della patente di Guida australiano licenza dal criterio. È in quest'ultimo perché fa parte del modello di criterio DLP, ma non è stiamo costretti a utilizzarlo. Se si è interessati solo i numeri di File fiscale e non le licenze della patente di Guida, è possibile solo rimuoverlo. Ad esempio, può rimuovere dalla regola volume ridotto nel criterio, ma lasciare nella regola volume elevato in modo che gli elenchi delle licenze driver più ancora rilevati.

![Opzione per eliminare il tipo di informazioni riservate dalla regola](media/DLP-create-test-tune-delete-low-volume-rule.png)
 
È inoltre possibile aumentare semplicemente il conteggio delle istanze, in modo che un volume ridotto di licenze della patente di Guida viene rilevato solo quando sono presenti più istanze.

![Opzione per modificare il conteggio delle istanze](media/DLP-create-test-tune-edit-instance-count.png)

Oltre a modificare il conteggio delle istanze, è possibile modificare la precisione di corrispondenza (o livello di probabilità). Se il tipo di informazioni riservate dispone di più modelli, è possibile modificare la precisione di corrispondenza della regola in modo che la regola corrisponda solo i modelli specifici. Ad esempio, che consentono di ridurre i falsi positivi, è possibile impostare la precisione di corrispondenza della regola in modo che corrisponda solo il motivo con il livello più alto. Informazioni sulle modalità di calcolo di livello di probabilità è difficile (ed esula dall'ambito di questo post), ma Ecco una spiegazione esauriente [dell'utilizzo per ottimizzare le regole di livello di probabilità](https://docs.microsoft.com/en-us/office365/securitycompliance/data-loss-prevention-policies#match-accuracy).

Infine, se si desidera ottenere anche un po' più avanzate, è possibile personalizzare qualsiasi tipo di informazioni riservate -, ad esempio, è possibile rimuovere "Sydney NSW" dall'elenco delle parole chiave per [australiano patente](https://docs.microsoft.com/en-us/office365/securitycompliance/what-the-sensitive-information-types-look-for#australia-drivers-license-number), per eliminare il falso positivo attivato in precedenza. Per informazioni su come eseguire questa operazione tramite XML e PowerShell, vedere questo argomento sulla [personalizzazione di un tipo di informazioni riservate incorporati](customize-a-built-in-sensitive-information-type.md).

## <a name="turn-off-a-dlp-policy"></a>Disattivare un criterio DLP

Quando si è soddisfatti che il criterio DLP è accuratamente in modo efficace il rilevamento di tipi di informazioni riservate e che gli utenti finali sono pronti per affrontare i criteri sul posto, quindi è possibile abilitare il criterio.

![Opzione per attivare il criterio](media/DLP-create-test-tune-turn-on-policy.png)
 
Se è in attesa di vedere se il criterio verrà abbia effetto, [Connetti alla sicurezza di Office 365 PowerShell centro conformità](https://docs.microsoft.com/en-us/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps) ed eseguire il [cmdlet Get-DlpCompliancePolicy](https://docs.microsoft.com/en-us/powershell/module/exchange/policy-and-compliance-dlp/get-dlpcompliancepolicy?view=exchange-ps) per visualizzare il DistributionStatus.

![L'esecuzione di cmdlet di PowerShell](media/DLP-create-test-tune-PowerShell.png)

Dopo avere attivato il criterio DLP, è consigliabile eseguire alcuni test finale personale per rendere assicurarsi che le azioni dei criteri previsti sono in corso. Se si sta tentando di testare elementi quali dati di carta di credito, sono disponibili i siti Web in linea con informazioni su come generare carta di credito esempio o altre informazioni personali che verrà passato checksum e attivano i criteri.

Criteri che consentono l'override dell'utente verranno presentati tale opzione per l'utente come parte del suggerimento sul criterio.

![Suggerimento sul criterio che consente l'override utente](media/DLP-create-test-tune-override-option.png)

Criteri che limitano il contenuto verranno presentare il messaggio di avviso all'utente come parte del suggerimento sul criterio e impedirne l'invio di posta elettronica.

![Suggerimento per il criterio questo contenuto è limitata](media/DLP-create-test-tune-restrict-warning.png)

## <a name="summary"></a>Riepilogo

Criteri di prevenzione della perdita di dati sono utili per organizzazioni di tutti i tipi. Test alcuni criteri DLP è un esercizio basso rischio per il controllo su dei suggerimenti sul criterio, override dell'utente finale e rapporti operazioni non consentite. È possibile testare in modalità non interattiva alcuni criteri DLP per visualizzare il tipo di violazioni sono già in corso nella propria organizzazione e quindi criteri di salvataggio con bassa falsi positivi, formare gli utenti che cos'è consentito e non è consentita e quindi è possibile distribuire i criteri DLP per la organizzazione.
