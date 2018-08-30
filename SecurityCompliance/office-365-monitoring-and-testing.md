---
title: Monitoraggio di Office 365 e test dei limiti di Tenant
ms.author: robmazz
author: robmazz
manager: laurawi
ms.date: 8/21/2018
audience: ITPro
ms.topic: article
ms.service: Office 365 Administration
localization_priority: None
search.appverid:
- MET150
ms.collection: Strat_O365_Enterprise
description: 'Riepilogo: Informazioni sulla modalità Microsoft monitorizza e test tenant dei limiti per Office 365.'
ms.openlocfilehash: 4d57c7497bfe8bf9939f3ae785ab9fbc670bd0ae
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/27/2018
ms.locfileid: "22530534"
---
# <a name="monitoring-and-testing-tenant-boundaries"></a>Monitoraggio e verifica dei limiti del tenant
Microsoft consente di monitorare continuamente e testato in modo esplicito per i punti deboli e vulnerabilità di limiti tenant, tra cui il monitoraggio delle intrusioni, tentativi di violazione di autorizzazione e occupazione delle risorse. Vengono inoltre utilizzati più sistemi interni per monitorare continuamente per l'utilizzo delle risorse non appropriato, se viene rilevata, viene attivato il limitazione predefinite.

Office 365 dispone di sistemi di monitoraggio interni continuo verificare la presenza di eventuali errori e il ripristino automatico di unità quando viene rilevato un errore. Sistemi di Office 365 analizzare deviazioni del comportamento del servizio e avviare automatica i processi sono predefiniti del sistema. Office 365 utilizza inoltre di fuori di monitoraggio in cui il monitoraggio viene eseguito da più postazioni sia da servizi di terze parti attendibili (può essere SLA) e dei propri centri dati alla generazione di avvisi. Per la diagnostica, è possibile utilizzare la registrazione estesa, il controllo e l'analisi. Analisi delle cause traccia granulare e monitoraggio utile per noi isolare i problemi ed eseguire radice rapida ed efficace.

Mentre Office 365 ha automatizzati azioni di ripristino quando possibile, gli esperti nella chiamata Microsoft sono disponibili 24 / 7 per analizzare tutti le misure correttive sicurezza gravità 1 e vengono esaminati finale di ogni richiesta di assistenza servizio contribuisce alla formazione continua e Analisi utilizzo software. Il team include personale del supporto tecnico, sviluppatori dei prodotti, i program manager, product manager e direzione aziendale. Professionisti nella chiamata servono da backup tempestivo e spesso consente di automatizzare azioni di ripristino, in modo che successivamente che si verifica un evento, può essere autonomo screpolature.

Microsoft consente di eseguire un'analisi approfondita di post-incidente ogni volta che si verifica un problema di sicurezza di Office 365 indipendentemente dalla portata dell'impatto. Un esame post-incidente è costituita da un'analisi delle Dov'è, come viene inviata una risposta e come si evita che simile risolte in futuro. Ai fini di trasparenza e accountability è condividere verifica post-incidente per qualsiasi risolte principali di servizio con i clienti interessati. Per informazioni dettagliate, vedere [Gestione incidente protezione di Office 365](http://aka.ms/Office365SIM).

## <a name="assume-breach-methodology"></a>Si supponga violazione della metodologia
In base alle informazioni dettagliate sulla analisi delle tendenze di protezione, Microsoft sostiene e vengono evidenziati la necessità di ulteriori investimenti in processi di protezione reattiva e le tecnologie che su rilevamento e risposta alle minacce emergenti, anziché esclusivamente la prevenzione della le minacce identificate. A causa di variazioni i rischi di protezione e un'analisi approfondita, Microsoft affinamento la strategia di protezione oltre a uno dispongono degli strumenti di gestione di violazioni quando si verificano – una strategia che ritiene principale degli eventi di protezione non appena che impedisce le violazioni della protezione Per motivi di if, ma quando.

Mentre [Presuppone violazione](https://www.microsoft.com/en-us/TrustCenter/Security/default.aspx) procedure Microsoft sono stati sul posto da molti anni, molti clienti di rilevano lavoro svolto in background per la protezione avanzata Microsoft cloud. Si supponga violazione una visione che guida a livello di sicurezza, le scelte di progettazione e sicurezza operative consigliate. Si supponga di limiti violazione la relazione di trust in modalità di applicazioni, servizi, le identità e reti considerando tutte, ovvero interni ed esterni, ovvero come non sicure o già compromesso. Sebbene la strategia presuppongono violazione non è stato carico da una violazione effettiva dei servizi Microsoft cloud o enterprise, era un riconoscimento che molte organizzazioni, tra il settore sono stati viene superate nonostante tutti i tentativi di evitarlo. Mentre impedendo violazioni è un elemento essenziale di operazioni di qualsiasi dell'organizzazione, le procedure consigliate devono essere continuo testate e arricchiti per affrontare avversari moderni e avanzate minacce persistente. Per un'organizzazione preparare una violazione della loro deve prima creare e gestire le procedure di sicurezza affidabile, ripetibili e testare accuratamente risposta.

Mentre i processi di protezione impedire violazione, ad esempio modellazione, revisioni del codice e la verifica della protezione sono molto utile come parte del [Ciclo di vita dello sviluppo della protezione](http://www.microsoft.com/security/sdl/default.aspx), si supponga violazione offre numerosi vantaggi che consentono di account per la protezione generale esercitare e reattiva funzionalità in caso violazione di misura.

In Microsoft, viene impostato in uscita per ottenere questo risultato tramite continuativa war-games esercitazioni e sito attive penetrazione dei nostri piani di risposta di sicurezza con lo scopo di migliorare la funzionalità di rilevamento e risposta. Microsoft regolarmente simula violazioni pratiche, svolge la propria sicurezza continua monitoraggio e gestione degli eventi imprevisti di protezione consigliate per convalidare e migliorare la protezione di Office 365, Azure e altri servizi cloud Microsoft.

Microsoft esegue la propria strategia di protezione presuppongono violazione utilizzando due gruppi di base:
- Team rosso (gli utenti malintenzionati)
- Team di Blue (difensori)

Personale Microsoft Azure e di Office 365 separare team rosso a tempo pieno e team di colore blu.

Denominato "[Rossa che si integra](http://go.microsoft.com/fwlink/?linkid=518599)", l'approccio consiste nel testare operazioni utilizzando le stesse strategie, tecniche e le procedure come avversari reale, con l'infrastruttura di produzione, senza la disponibilità di e sistemi di Office 365 e Azure il Engineering o team operativi. Ciò consente di verificare il rilevamento di sicurezza e le funzionalità di risposta di Microsoft e consentono di identificare le vulnerabilità di produzione, gli errori di configurazione, presupposti non validi e altri problemi di protezione in modo controllato. Ogni violazione team rosso è seguito da divulgazione completa tra entrambi i team per identificare i gap, risolvere i risultati e migliorare violazione della risposta.

**Nota**: non i dati dei clienti sono prevista intenzionalmente durante l'uso combinato rosso o penetrazione sito attive. I test sono con infrastruttura di Office 365 e Azure e piattaforme, nonché tenant di Microsoft, applicazioni e dati. Mai mirate tenant di clienti, delle applicazioni e il contenuto ospitato in Office 365 o Azure.

## <a name="red-teams"></a>Team di colore rosso
Il team di colore rosso è un gruppo di dipendenti a tempo pieno all'interno di Microsoft è incentrata sulla violazione del Microsoft dell'infrastruttura, alla piattaforma e tenant di Microsoft e applicazioni. Sono avversario dedicato (un gruppo di utenti malintenzionati etici) esecuzione di destinazione e persistenti attacchi Online Services (infrastruttura Microsoft, piattaforme e applicazioni, ma non end clienti applicazioni o contenuto).

Il ruolo del team di colore rosso deve attacchi penetrare ambienti utilizzando la stessa procedura come un avversario:
 
![Fasi violazione](media/office-365-isolation-breach-stages.png)

Tra le altre cose, team di colore rosso tentano di violare limiti di isolamento tenant per trovare bug o gap nel nostro progetto di isolamento.

## <a name="blue-teams"></a>Team di colore blu
Il team di colore blu è costituito da un insieme dedicato dei risponditori protezione o i membri da tra l'intervento di protezione, progettazione e operazioni organizzazioni. Indipendentemente dalla loro make-up sono indipendenti ed essere gestito separatamente dal team di colore rosso. Segue il team blu stabilita protezione elabora e utilizza strumenti e le tecnologie più recenti per rilevare e rispondere ad attacchi e penetrazioni. Sarà simile a quello del mondo reale gli attacchi di tipo, il team di colore blu non sa quando o come gli attacchi di tipo del team rosso verificherà o possono essere utilizzati i metodi. Il proprio lavoro, se si tratta di un attacco di colore rosso team o un assault effettivo è di rilevare e rispondere a tutti i problemi di protezione. Per questo motivo, il team di blue continuamente nella chiamata e deve rispondere ai violazioni team rosso allo stesso modo che per qualsiasi altro violazione.

Quando un avversario, ad esempio un team di colore rosso, non è soddisfatta un ambiente, il team di colore blu deve:
- Raccogliere prove lasciate dell'avversario
- Rilevare gli elementi di prova come indicazione della violazione
- Il team appropriati Engineering e il corretto funzionamento di avviso
- Esaminare gli avvisi per determinare se si richiedono un'ulteriore un'analisi
- Raccogliere contesto dall'ambiente come ambito violazione
- Formare un piano di risoluzione dei problemi per contenere o ridenominazione forzata dell'avversario
- Eseguire il piano di risoluzione dei problemi e il ripristino da violazione

La procedura seguente modulo l'intervento di protezione che esegue parallelo dell'avversario, come illustrato di seguito:
 
![Fasi di violazione della risposta](media/office-365-isolation-breach-response-stages.png)

Violazioni team rosso consentono di esercitare capacità del team blu di rilevare e rispondere alle pratiche attacchi end-to-end. In particolare, consente di intervento di protezione efficace prima della violazione autentica. Inoltre, a causa di violazioni team rosso, il team di blue migliora la loro conoscenza della situazione che può essere utile quando si gestiscono violazioni future (se dal team di colore rosso o un altro avversario). Durante il processo di risposta e il rilevamento, il team di colore blu produce pronti per interventi business intelligence e ottiene le effettive condizioni virtuali che sta tentando di migliorare la difesa della visibilità. Domande questa operazione viene eseguita tramite l'analisi dei dati e legali, eseguita dal team di colore blu per la risposta ad attacchi di tipo team rosso e stabilendo gli indicatori di rischio, ad esempio gli indicatori di compromissione. Molto simile modalità con cui il team di colore rosso identifica gap nel brano della sicurezza, team di blue identificare i gap per la capacità di rilevare e rispondere. Inoltre, poiché i team di colore rossi del modello del mondo reale gli attacchi di tipo, il team di blue può essere accuratamente valutato le possibilità o impossibilità di affrontare avversari determinati e persistent. Infine, violazioni team rosso misurano sia lo stato di preparazione e l'impatto della risposta violazione.
