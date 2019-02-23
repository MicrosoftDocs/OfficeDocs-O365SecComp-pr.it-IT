---
title: Criteri di rilevamento delle anomalie in Office 365 Cloud App Security
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 02/15/2019
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 88935b4e-dcb1-47f1-8aca-1bf8fb069db6
description: 'I criteri di rilevamento delle anomalie in Office 365 cloud app Security utilizzano algoritmi incorporati per consentire di individuare potenziali problemi. È necessario disporre di almeno un criterio di rilevamento delle anomalie, che è possibile sintonizzare (quando lo si crea) tramite filtri. '
ms.openlocfilehash: 5308af139a46dad0793ed7eedacab0aee62dcc6c
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/23/2019
ms.locfileid: "30220676"
---
# <a name="anomaly-detection-policies-in-office-365-cloud-app-security"></a>Criteri di rilevamento delle anomalie in Office 365 Cloud App Security

|Valutazione * *\>**|Planning * *\>**|Distribuzione * *\>**|Utilizzo * * * *|
|:-----|:-----|:-----|:-----|
|[Iniziare a valutare](office-365-cas-overview.md) <br/> |[Avviare la pianificazione](get-ready-for-office-365-cas.md) <br/> |Sei qui!  <br/> [Passaggio successivo](ocas-conditional-access-app-control.md) <br/> |[Iniziare a utilizzare](utilization-activities-for-ocas.md) <br/> |
   
A partire da [Microsoft cloud app Security release 116](new-in-office-365-cas-2018.md#office-365-cloud-app-security-release-116), Office 365 cloud app Security include diversi criteri di rilevamento delle anomalie predefinite ("out of the box") che includono l'analisi comportamentale degli utenti e delle entità (Ueba) e l'apprendimento automatico (ml).
  
![Per visualizzare i criteri di rilevamento delle anomalie \> , scegliere criteri di controllo.](media/9663baa5-98bf-45e0-9458-6e572b43ec72.png)
  
Questi criteri di rilevamento delle anomalie offrono risultati immediati fornendo rilevamenti immediati, individuando numerose anomalie comportamentali tra gli utenti e i computer e i dispositivi connessi alla rete. Inoltre, i nuovi criteri espongono ulteriori dati dal motore di rilevamento della sicurezza delle app cloud per velocizzare il processo di indagine e contenere minacce in corso.
  
In qualità di amministratore globale di Office 365 o amministratore della sicurezza, è possibile rivedere e, se necessario, rivedere i criteri predefiniti disponibili con Office 365 cloud app Security.
  
 > [!IMPORTANT]
> Vi è un periodo di apprendimento iniziale di sette (7) giorni durante il quale non vengono attivati gli avvisi sul comportamento anomalo. L'algoritmo di rilevamento delle anomalie è ottimizzato per ridurre il numero di falsi avvisi positivi. 
  
## <a name="before-you-begin"></a>Informazioni preliminari

Verificare quanto segue:
  
- L'organizzazione dispone di [Office 365 cloud app Security](office-365-cas-overview.md)e il servizio è [attivato](turn-on-office-365-cas.md).
    
- La [registrazione di controllo](turn-audit-log-search-on-or-off.md) è attivata per l'ambiente Office 365. 
    
- Si è un amministratore globale o un amministratore della sicurezza per Office 365.
    
## <a name="view-your-anomaly-detection-policies"></a>Visualizzare i criteri di rilevamento delle anomalie

1. In qualità di amministratore globale o amministratore della sicurezza, passare al cloud app Security Portal[https://portal.cloudappsecurity.com](https://portal.cloudappsecurity.com)() ed eseguire l'accesso.<br>Verrà eseguita la pagina Criteri di protezione delle app di Office 365 cloud.
    
2. Nell'elenco **tipo** , scegliere **criteri di rilevamento**delle anomalie.<br>Vengono visualizzati i criteri di rilevamento delle anomalie predefinite (o esistenti) dell'organizzazione.<br>![Criteri di rilevamento delle anomalie in Office 365 Cloud App Security](media/2e0ee770-787a-4d4a-bea8-389dc765d4c6.png)
  
3. Selezionare un criterio per esaminare o modificare le relative impostazioni.
    
4. Scegliere **Update** per salvare le modifiche. 
    
## <a name="learn-more-about-anomaly-detection-policies"></a>Ulteriori informazioni sui criteri di rilevamento delle anomalie

I criteri di rilevamento delle anomalie sono abilitati automaticamente. Tuttavia, Office 365 cloud app Security ha un periodo di apprendimento iniziale di sette giorni durante il quale non vengono generati tutti gli avvisi di rilevamento delle anomalie. Successivamente, ogni sessione viene confrontata con l'attività, quando gli utenti sono attivi, gli indirizzi IP, i dispositivi e così via sono stati rilevati nell'ultimo mese e il Punteggio di rischio di queste attività. Tali rilevamenti fanno parte del motore di rilevamento delle anomalie euristiche che profila l'ambiente e attiva gli avvisi in relazione a una linea di base appresa nell'attività dell'organizzazione. Tali rilevamenti sfruttano anche gli algoritmi di apprendimento automatico studiati per profilare gli utenti e i modelli di accesso per ridurre i falsi positivi.
  
Le anomalie vengono rilevate analizzando le attività degli utenti. Il rischio viene valutato esaminando oltre 30 indicatori di rischio diversi, raggruppati in più fattori di rischio, ad esempio l'indirizzo IP rischioso, gli errori di accesso, l'attività di amministratore, gli account inattivi, la posizione, la corsa impossibile, il dispositivo e l'agente utente e il tasso di attività.
  
In base ai risultati dei criteri, vengono attivati gli avvisi di sicurezza. Office 365 cloud app Security analizza ogni sessione degli utenti in Office 365 e avvisa ogni volta che si verifica qualcosa di diverso dalla linea di base dell'organizzazione o dall'attività regolare di un utente.
  
Nella tabella seguente vengono descritti i criteri di rilevamento delle anomalie predefiniti, le operazioni eseguite e il relativo funzionamento.
  
|**Nome del criterio di rilevamento delle anomalie**|**Funzionamento**|
|:-----|:-----|
|Viaggi imPossibili  <br/> |Identifica due attività utente (è una singola o più sessioni) provenienti da percorsi geograficamente distanti entro un periodo di tempo più breve rispetto al tempo impiegato dall'utente per spostarsi dal primo percorso alla seconda, a indicare che un altro l'utente utilizza le stesse credenziali. Questo rilevamento utilizza un algoritmo di apprendimento automatico che ignora gli evidenti "falsi positivi" che contribuiscono alla condizione di viaggio impossibile, ad esempio le connessioni VPN e i percorsi utilizzati periodicamente da altri utenti dell'organizzazione. Il rilevamento ha un periodo di apprendimento iniziale di sette giorni durante il quale viene illustrato il modello di attività di un nuovo utente.  <br/> |
|Attività da un paese infrequente  <br/> |Considera le posizioni di attività precedenti per determinare le posizioni nuove e rare. Il motore di rilevamento delle anomalie archivia le informazioni sui percorsi precedenti utilizzati dagli utenti nell'organizzazione. Viene attivato un avviso quando si verifica un'attività da una posizione non recente o mai visitata dall'utente o da un utente dell'organizzazione.  <br/> |
|Attività da indirizzi IP anonimi  <br/> |Identifica che gli utenti erano attivi da un indirizzo IP identificato come indirizzo IP proxy anonimo. Questi proxy vengono utilizzati da utenti che desiderano nascondere l'indirizzo IP del dispositivo e che possono essere utilizzati per intenti dannosi. Questo rilevamento utilizza un algoritmo di apprendimento automatico che consente di ridurre i "falsi positivi", ad esempio gli indirizzi IP con tag mis ampiamente utilizzati dagli utenti dell'organizzazione.  <br/> |
|Attività da indirizzi IP sospetti  <br/> |Identifica che gli utenti erano attivi da un indirizzo IP che è stato identificato come rischioso da Microsoft Threat Intelligence. Questi indirizzi IP sono coinvolti in attività dannose, come la botnet&amp;c c, e possono indicare un account compromesso. Questo rilevamento utilizza un algoritmo di apprendimento automatico che consente di ridurre i "falsi positivi", ad esempio gli indirizzi IP con tag mis ampiamente utilizzati dagli utenti dell'organizzazione.  <br/> |
|Attività inUsuali (per utente)  <br/> | Identifica gli utenti che eseguono attività inusuali, ad esempio:  <br/>  --Download di file multipli  <br/>  --Attività di condivisione file  <br/>  --Attività di eliminazione dei file  <br/>  --Attività di rappresentazione  <br/>  -Attività amministrative  <br/>  Questi criteri cercano attività all'interno di una singola sessione rispetto alla linea di base appresa, cosa che potrebbe indicare un tentativo di violazione. Tali rilevamenti sfruttano un algoritmo di apprendimento automatico che profila il modello di accesso degli utenti e riduce i falsi positivi. Tali rilevamenti fanno parte del motore di rilevamento delle anomalie euristiche che profila l'ambiente e attiva gli avvisi in relazione a una linea di base appresa nell'attività dell'organizzazione.  <br/> |
|Tentativi di accesso non riusciti multipli  <br/> |Identifica gli utenti che non hanno eseguito più tentativi di accesso in una singola sessione rispetto alla linea di base appresa, cosa che potrebbe indicare un tentativo di violazione.  <br/> |
   
## <a name="triage-anomaly-detection-alerts"></a>Avvisi di rilevamento delle anomalie di valutazione

Come gli avvisi sono disponibili, è possibile valutare rapidamente gli avvisi e determinare quali gestire per primo. L'utilizzo di un contesto per un avviso consente di visualizzare l'immagine più grande e determinare se è effettivamente in corso qualcosa di dannoso. Utilizzare la procedura seguente per iniziare a esplorare un avviso:
  
1. In qualità di amministratore globale o amministratore della sicurezza, passare al cloud app Security Portal[https://portal.cloudappsecurity.com](https://portal.cloudappsecurity.com)() ed eseguire l'accesso. 
    
2. Scegliere **avvisi** per visualizzare gli avvisi. 
    
3. Per ottenere il contesto di un avviso, eseguire la procedura seguente:
    
4. Scegliere **indaga** \> **log attività**.
    
5. Selezionare un elemento, ad esempio un utente o un indirizzo IP. Verrà aperto il cassetto Insights pertinente.<br>![Nel registro attività è possibile esaminare un indirizzo IP.](media/32a727c5-e406-4fe2-9443-c1a7fb6628fc.png)
  
6. Nel cassetto Insights pertinente fare clic su un comando disponibile, ad esempio un'icona nella sezione **Mostra simile** .<br> ![Fare clic sull'icona dell'orologio per visualizzare le attività eseguite entro 48 ore dall'attività selezionata](media/c6c96aa0-98e5-4205-8873-45f8d6fd0843.png)
  
7. Ottenere informazioni dettagliate sull'elemento selezionato continuando a esplorare i dettagli relativi a quell'elemento.
    
Un avviso su più accessi non riusciti potrebbe essere effettivamente sospettoso e può indicare un potenziale attacco di forza bruta. Tuttavia, un avviso di questo tipo può anche essere una configurazione errata dell'applicazione, causando l'avviso come un valore positivo vero. Se viene visualizzato un avviso per gli accessi con più errori con attività sospette aggiuntive, è probabile che un account venga compromesso. Si supponga, ad esempio, che un avviso di accesso a più errori sia seguito dall'attività di un indirizzo IP TOR e da un'attività di viaggio impossibile, entrambi indicatori forti del compromesso. Si potrebbe anche vedere che lo stesso utente ha eseguito un'attività di download di massa, che è spesso un indicatore dell'aggressore che esegue exfiltration di dati. Sono cose di questo tipo che è possibile esplorare in Office 365 cloud app Security per visualizzare e valutare gli avvisi e intraprendere le azioni laddove necessario.
  
## <a name="next-steps"></a>Passaggi successivi

- [Distribuire Controllo app per l'accesso condizionale per le app di Office 365](ocas-deploy-conditional-access-app-control.md)

- [Raggruppare gli indirizzi IP per semplificare la gestione](group-your-ip-addresses-in-ocas.md)

- [Integrare il server SIEM](integrate-your-siem-server-with-office-365-cas.md)
    
- [Esaminare e intervenire sugli avvisi](review-office-365-cas-alerts.md)
    
    

