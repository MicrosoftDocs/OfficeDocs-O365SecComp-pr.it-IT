---
title: Integrare il server SIEM con Office 365 Cloud App Security
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: dd6d2417-49c4-4de6-9294-67fdabbf8532
description: È possibile integrare il server SIEM con Office 365 cloud app Security. Leggere questo articolo per ottenere una panoramica di come funziona e come configurarlo.
ms.openlocfilehash: b4baeda3cb836c0b1aa528d29176bbf4321d1fe2
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/23/2019
ms.locfileid: "30215876"
---
# <a name="integrate-your-siem-server-with-office-365-cloud-app-security"></a>Integrare il server SIEM con Office 365 Cloud App Security
  
|Valutazione * *\>**|Planning * *\>**|Distribuzione * *\>**|Utilizzo * * * *|
|:-----|:-----|:-----|:-----|
|[Iniziare a valutare](office-365-cas-overview.md) <br/> |[Avviare la pianificazione](get-ready-for-office-365-cas.md) <br/> |Sei qui!  <br/> [Passaggio successivo](utilization-activities-for-ocas.md) <br/> |[Iniziare a utilizzare](utilization-activities-for-ocas.md) <br/> |
   
## <a name="overview-and-prerequisites"></a>Panoramica e prerequisiti

È possibile integrare [Office 365 cloud app Security](get-ready-for-office-365-cas.md) con il server di gestione eventi e informazioni di sicurezza (Siem) per abilitare il monitoraggio centralizzato degli avvisi. Questo è particolarmente vantaggioso per le organizzazioni che utilizzano i servizi cloud e le applicazioni server locali. L'integrazione con un server SIEM consente al team di sicurezza di proteggere al meglio le applicazioni di Office 365 mantenendo il flusso di lavoro di sicurezza usuale, automatizzando determinate procedure di sicurezza e correlando tra gli eventi basati su cloud e in locale.  
  
Quando si integra per la prima volta il server SIEM con Office 365 cloud app Security, gli avvisi degli ultimi due giorni vengono inoltrati al server SIEM, nonché tutti gli avvisi da quel momento in poi (in base ai filtri selezionati). Inoltre, se si disabilita questa funzionalità per un periodo di tempo prolungato, quando si abilita di nuovo, verranno inoltrati gli ultimi due giorni di avvisi e quindi tutti gli avvisi da quel momento in poi.

### <a name="siem-integration-architecture"></a>Architettura di integrazione di SIEM

Un agente di SIEM è configurato nella rete dell'organizzazione. Quando viene distribuita e configurata, l'agente di SIEM estrae i tipi di dati configurati (avvisi) con Office 365 cloud app Security RESTful APIs. Il traffico viene quindi inviato su un canale HTTPS crittografato sulla porta 443.
  
Quando un agente SIEM recupera i dati da Office 365 cloud app Security, invia i messaggi syslog al server SIEM locale utilizzando le configurazioni di rete fornite durante l'installazione (TCP o UDP con una porta personalizzata).

![Architettura di sicurezza di SIEM e cloud app](media/siem-architecture.png)

### <a name="supported-siem-servers"></a>Server SIEM supportati

Office 365 cloud app Security attualmente supporta i seguenti server SIEM:
- Micro Focus ArcSight
- CEF generico

### <a name="prerequisites"></a>Prerequisiti

- È necessario essere un amministratore globale o un amministratore della sicurezza per eseguire le attività descritte in questo articolo. Vedere [Permissions in the Office &amp; 365 Security Compliance Center](permissions-in-the-security-and-compliance-center.md)

- È necessario che [Office 365 cloud app Security sia abilitato](turn-on-office-365-cas.md) per la propria organizzazione.

- La [registrazione di controllo](turn-audit-log-search-on-or-off.md) deve essere attivata per Office 365

- Per configurare l'integrazione del server SIEM è necessario disporre di un server standard che soddisfi i requisiti seguenti:
    - SISTEMA operativo: Windows o Linux (può essere una macchina virtuale)
    - CPU: 2
    - Spazio su disco: 20 GB
    - RAM: 2 GB
    - [Oracle Java 8](http://www.oracle.com/technetwork/java/javase/downloads/index.html) installato
    - Firewall configurato come descritto in [requisiti di rete](https://docs.microsoft.com/cloud-app-security/network-requirements)

- È necessario disporre di informazioni dettagliate sull' **host syslog remoto** e sul **numero di porta di Syslot**. Un amministratore di rete o un amministratore di sicurezza dovrebbe essere in grado di individuare tali informazioni. 

- È necessario accettare le [condizioni di licenza software](https://go.microsoft.com/fwlink/?linkid=862491) per scaricare il [file jar](https://go.microsoft.com/fwlink/?linkid=838596) che è necessario integrare il server Siem.
 
## <a name="step-1-set-it-up-a-siem-agent-in-office-365-cloud-app-security"></a>Passaggio 1: conFigurarlo come agente di SIEM in Office 365 cloud app Security

1. Accedere al portale[https://portal.cloudappsecurity.com](https://portal.cloudappsecurity.com)di sicurezza delle app cloud e accedere.
  
2. Fare clic su impostazioni di **protezione**di **Settings** \> e quindi scegliere agenti Siem.<br/>
![Scegliere Settings > Security Extensions](media/Settings-SecurityExtensions.png)

3. Scegliere **Aggiungi agente Siem**.<br/>![Scegliere Aggiungi agente SIEM.](media/SIEMAgents.png)
    
4. Scegliere **Avvia procedura guidata**.<br/>![Ottenere assistenza o avviare la procedura guidata](media/HelpOrWizard.png) 
    
5. Nel passaggio **generale** , specificare un nome, quindi **selezionare il formato Siem** e impostare le **Impostazioni avanzate** rilevanti per tale formato. Fare quindi clic su **Avanti**.<br/>![Specificare un nome e un tipo](media/ChooseAgentTypeAndName.png)
    
6. Nel passaggio **syslog Remote** , specificare l'indirizzo IP o il nome host dell' **host syslog remoto** e il **numero di porta syslog**. Selezionare TCP o UDP come protocollo syslog remoto. Se non si dispone di tali informazioni, è possibile collaborare con l'amministratore di rete o con l'amministratore della sicurezza. Fare quindi clic su **Avanti**.<br/>![Specificare i dettagli di syslog remoti](media/ArcSightS1Syslog.png)
  
7. Nel passaggio **tipi di dati** effettuare una delle operazioni seguenti e quindi fare clic su **Avanti**:
    - Mantieni l'impostazione predefinita di **tutti gli avvisi**<br/>OPPURE
    - Fare clic su **tutti gli avvisi**e quindi scegliere **filtri specifici**. Definire i filtri per selezionare i tipi di avvisi che si desidera inviare al server SIEM.<br/>![Passaggio dei tipi di dati della procedura guidata](media/ArcSightS1ExportOptions.png)
  
8. Nella schermata Congratulazioni, copiare il token e salvarlo in un secondo momento.<br/>![Schermata dell'agente di SIEM creato](media/SIEMAgentFinished.png) 

> [!IMPORTANT]
> A questo punto, è stato configurato un agente SIEM in Office 365 cloud app Security, ma l'integrazione del server SIEM non è ancora stata completata. Procedere con il passaggio successivo per continuare l'integrazione del server SIEM.

Dopo aver fatto clic su Chiudi e lasciare la procedura guidata, nella schermata estensioni di sicurezza, è possibile visualizzare l'agente SIEM aggiunto nella tabella. Verrà visualizzato lo stato **creato** finché non viene connesso in un secondo momento.

![Agente di SIEM creato](media/SIEMAgentCreated.png)
    
## <a name="step-2-download-a-jar-file-and-run-it-on-your-siem-server"></a>Passaggio 2: scaricare un file JAR ed eseguirlo sul server SIEM

1. Scaricare l' [agente di Microsoft cloud app Security Siem](https://go.microsoft.com/fwlink/?linkid=838596) e decomprimere la cartella. Per continuare, è necessario accettare le [condizioni di licenza software](https://go.microsoft.com/fwlink/?linkid=862491) . 
    
2. Estrarre il file. jar dalla cartella zippata ed eseguirlo sul server SIEM.
    
3. Dopo aver eseguito il file, eseguire il comando riportato di seguito:<br/>
  ```
  java -jar mcas-siemagent-0.87.20-signed.jar [--logsDirectory DIRNAME] [--proxy ADDRESS[:PORT]] --token TOKEN
  ```
### <a name="important-notes"></a>Note importanti

- Il nome del file può variare a seconda della versione dell'agente SIEM. 

- Si consiglia di eseguire il file JAR sul server SIEM durante l'installazione del server.

    - **Windows**: eseguire come attività pianificata, assicurandosi di configurare l'attività per l' **esecuzione se l'utente è connesso o meno** e si deseleziona l'opzione **Interrompi l'attività se viene eseguito più a lungo di** Option.

    - **Linux**: aggiungere il comando Esegui con un **&** al `rc.local` file. <br/>Esempio:<br/> 
    ```
    java -jar mcas-siemagent-0.87.20-signed.jar [--logsDirectory DIRNAME] [--proxy ADDRESS[:PORT]] --token TOKEN &
    ```

- I parametri tra parentesi quadre [] sono facoltativi e devono essere utilizzati solo se rilevanti. Utilizzare le seguenti variabili:

    - **Dirname** è il percorso della directory che si desidera utilizzare per i log di debug degli agenti locali.

    - **Address [:P Ort]** è l'indirizzo del server proxy e la porta utilizzata dal server per la connessione a Internet.

    - **Token** è il token dell'agente Siem copiato nella prima procedura.

    - Per ottenere assistenza, digitare `-h`. 
  
## <a name="step-3-validate-that-the-siem-agent-is-working"></a>Passaggio 3: verificare che l'agente SIEM funzioni

1. Verificare che lo stato dell'agente SIEM nel portale di sicurezza delle app cloud di Office 365 non venga visualizzato come **errore di connessione** o disconnesso e che non vi siano notifiche di agente. ****<br/>Ad esempio, qui è possibile vedere che il server SIEM è connesso:<br/>![Server SIEM connesso](media/siem-connected.png)<br/>E qui, è possibile vedere il server SIEM è disconnesso:<br/>![Server SIEM non connesso](media/siem-not-connected.png) 
  
2. Nel server syslog/SIEM, verificare che gli avvisi siano arrivati da Office 365 cloud app Security.
  
## <a name="what-the-logfiles-look-like"></a>Aspetto dei file di log

Di seguito è riportato un esempio di file di log avvisi che potrebbe essere inviato a un server SIEM:

```
2017-07-15T20:42:30.531Z CEF:0|MCAS|SIEM_Agent|0.102.17|ALERT_CABINET_EVENT_MATCH_AUDIT|myPolicy|3|externalId=596a7e360c204203a335a3fb start=1500151350531 end=1500151350531 msg=Activity policy ''myPolicy'' was triggered by ''admin@box-contoso.com'' suser=admin@box-contoso.com destinationServiceName=Box cn1Label=riskScore cn1= cs1Label=portalURL cs1=https://cloud-app-security.com/#/alerts/596a7e360c204203a335a3fb cs2Label=uniqueServiceAppIds cs2=APPID_BOX cs3Label=relatedAudits cs3=1500151288183_acc891bf-33e1-424b-a021-0d4370789660 cs4Label=policyIDs cs4=59f0ab82f797fa0681e9b1c7

2017-07-16T09:36:26.550Z CEF:0|MCAS|SIEM_Agent|0.102.17|ALERT_CABINET_EVENT_MATCH_AUDIT|test-activity-policy|3|externalId=596b339b0c204203a33a51ae start=1500197786550 end=1500197786550 msg=Activity policy ''test-activity-policy'' was triggered by ''user@contoso.com'' suser=user@contoso.com destinationServiceName=Salesforce cn1Label=riskScore cn1= cs1Label=portalURL cs1=https://cloud-app-security.com/#/alerts/596b339b0c204203a33a51ae cs2Label=uniqueServiceAppIds cs2=APPID_SALESFORCE cs3Label=relatedAudits cs3=1500197720691_b7f6317c-b8de-476a-bc8f-dfa570e00349 cs4Label=policyIDs cs4=

2017-07-16T09:17:03.361Z CEF:0|MCAS|SIEM_Agent|0.102.17|ALERT_CABINET_EVENT_MATCH_AUDIT|test-activity-policy3|3|externalId=596b2fd70c204203a33a3eeb start=1500196623361 end=1500196623361 msg=Activity policy ''test-activity-policy3'' was triggered by ''admin@contoso.com'' suser=admin@contoso.com destinationServiceName=Office 365 cn1Label=riskScore cn1= cs1Label=portalURL cs1=https://cloud-app-security.com/#/alerts/596b2fd70c204203a33a3eeb cs2Label=uniqueServiceAppIds cs2=APPID_O365 cs3Label=relatedAudits cs3=1500196549157_a0e01f8a-e29a-43ae-8599-783c1c11597d cs4Label=policyIDs cs4=

2017-07-16T09:17:15.426Z CEF:0|MCAS|SIEM_Agent|0.102.17|ALERT_CABINET_EVENT_MATCH_AUDIT|test-activity-policy|3|externalId=596b2fd70c204203a33a3eec start=1500196635426 end=1500196635426 msg=Activity policy ''test-activity-policy'' was triggered by ''admin@contoso.com'' suser=admin@contoso.com destinationServiceName=Microsoft Office 365 admin center cn1Label=riskScore cn1= cs1Label=portalURL cs1=https://cloud-app-security.com/#/alerts/596b2fd70c204203a33a3eec cs2Label=uniqueServiceAppIds cs2=APPID_O365_PORTAL cs3Label=relatedAudits cs3=1500196557398_3e102b20-d9fa-4f66-b550-8c7a403bb4d8 cs4Label=policyIDs cs4=59f0ab35f797fa9811e9b1c7

2017-07-16T09:17:46.290Z CEF:0|MCAS|SIEM_Agent|0.102.17|ALERT_CABINET_EVENT_MATCH_AUDIT|test-activity-policy4|3|externalId=596b30200c204203a33a4765 start=1500196666290 end=1500196666290 msg=Activity policy ''test-activity-policy4'' was triggered by ''admin@contoso.com'' suser=admin@contoso.com destinationServiceName=Microsoft Exchange Online cn1Label=riskScore cn1= cs1Label=portalURL cs1=https://cloud-app-security.com/#/alerts/596b30200c204203a33a4765 cs2Label=uniqueServiceAppIds cs2=APPID_OUTLOOK cs3Label=relatedAudits cs3=1500196587034_a8673602-7e95-46d6-a1fe-c156c4709c5d cs4Label=policyIDs cs4=

2017-07-16T09:41:04.369Z CEF:0|MCAS|SIEM_Agent|0.102.17|ALERT_CABINET_EVENT_MATCH_AUDIT|test-activity-policy2|3|externalId=596b34b10c204203a33a5240 start=1500198064369 end=1500198064369 msg=Activity policy ''test-activity-policy2'' was triggered by ''user2@test15-adallom.com'' suser=user2@test15-adallom.com destinationServiceName=Google cn1Label=riskScore cn1= cs1Label=portalURL cs1=https://cloud-app-security.com/#/alerts/596b34b10c204203a33a5240 cs2Label=uniqueServiceAppIds cs2=APPID_33626 cs3Label=relatedAudits cs3=1500197996117_fd71f265-1e46-4f04-b372-2e32ec874cd3 cs4Label=policyIDs cs4=
```

Ed ecco un altro esempio, questa volta in formato CEF:


|Nome del campo CEF  | Description  |
|---------|---------|
|iniziare     | timestamp di avviso        |
|End     | timestamp di avviso        |
|RT     | timestamp di avviso        |
|msg     | Descrizione dell'avviso come mostrato nel portale di Office 365 cloud app Security        |
|sUser     | utente del soggetto di avviso        |
|destinationServiceName     | app di origine degli avvisi, ad esempio Office 365, SharePoint o OneDrive        |
|csLabel     | Varia (le etichette hanno significati diversi). In genere, le etichette sono autoesplicative, ad esempio targetObjects.        |
|cs     | Informazioni corrispondenti a un'etichetta, ad esempio l'utente di destinazione di un avviso secondo l'esempio di etichetta.        |

## <a name="additional-tasks-as-needed"></a>Altre attività (se necessario)

Dopo aver configurato il server SIEM e averlo integrato con Office 365 cloud app Security, potrebbe essere necessario rigenerare un token, modificare un agente SIEM o eliminare un agente SIEM. Nelle sezioni seguenti viene descritto come eseguire queste attività.

### <a name="regenerate-a-token"></a>Rigenerazione di un token

Se si perde il token, è possibile rigenerarne uno. 

1. In Office 365 Cloud App security[https://portal.cloudappsecurity.com](https://portal.cloudappsecurity.com)portal (), scegliere **Settings** > **security extensions**.

2. Nella tabella individuare la riga per l'agente SIEM. 

3. Fare clic sui puntini di ellisse e quindi scegliere **Rigenera token**.<br/>![Rigenerare un token facendo clic sui puntini di sospensione per l'agente SIEM](media/04de368a-b88e-4a9c-a830-58025cb98db6.png)
  
### <a name="edit-a-siem-agent"></a>Modificare un agente SIEM

1. In Office 365 Cloud App security[https://portal.cloudappsecurity.com](https://portal.cloudappsecurity.com)portal (), scegliere **Settings** > **security extensions**.

2. Individuare la riga per l'agente SIEM. 

3. Fare clic sui puntini di ellisse e quindi scegliere **modifica**. Se si modifica l'agente SIEM, non è necessario rieseguire il file. jar; si aggiorna automaticamente.<br/>![Per modificare l'agente SIEM, scegliere i puntini di ellisse e quindi fare clic su modifica.](media/96d0b362-3e0c-4dff-b2b4-d7af5b1bfb91.png)
  
### <a name="delete-a-siem-agent"></a>Eliminare un agente SIEM

1. In Office 365 Cloud App security[https://portal.cloudappsecurity.com](https://portal.cloudappsecurity.com)portal (), scegliere **Settings** > **security extensions**.

2. Individuare la riga per l'agente SIEM. 

3. Fare clic sui puntini di ellisse e quindi scegliere **Elimina**.<br/>![Per eliminare un agente SIEM, scegliere i puntini di ellissi e quindi scegliere Elimina.](media/540b5bdf-5574-4ecc-a7b0-92a499a387d7.png)

  
## <a name="next-steps"></a>Passaggi successivi

- [Attività di utilizzo dopo la distribuzione di Office 365 Cloud App Security](utilization-activities-for-ocas.md)
    
- [Esaminare e intervenire sugli avvisi](review-office-365-cas-alerts.md)
    
- [Raggruppare gli indirizzi IP per semplificare la gestione](group-your-ip-addresses-in-ocas.md)
    

