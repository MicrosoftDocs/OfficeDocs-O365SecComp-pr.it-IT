---
title: Integrare il server SIEM con Office 365 Cloud App Security
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: dd6d2417-49c4-4de6-9294-67fdabbf8532
description: È possibile integrare il server SIEM con Office 365 Cloud App protezione. In questo articolo per una panoramica del funzionamento e su come configurarla.
ms.openlocfilehash: 0e185dec44bed7657bed126f70dfc64ffc135611
ms.sourcegitcommit: 9034809b6f308bedc3b8ddcca8242586b5c30f94
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/15/2019
ms.locfileid: "28015028"
---
# <a name="integrate-your-siem-server-with-office-365-cloud-app-security"></a>Integrare il server SIEM con Office 365 Cloud App Security
  
|Valutazione * *\>**|Pianificazione * *\>**|Distribuzione * *\>**|Utilizzo * * *|
|:-----|:-----|:-----|:-----|
|[Avviare la valutazione](office-365-cas-overview.md) <br/> |[Iniziare a pianificare](get-ready-for-office-365-cas.md) <br/> |Si è seguito!  <br/> [Passaggio successivo](utilization-activities-for-ocas.md) <br/> |[Avviare utilizzando](utilization-activities-for-ocas.md) <br/> |
   
## <a name="overview-and-prerequisites"></a>Panoramica e i prerequisiti

È possibile integrare [Protezione di Office 365 Cloud App](get-ready-for-office-365-cas.md) con il server di gestione (SIEM) eventi e informazioni sicurezza per abilitare il monitoraggio centralizzato degli avvisi. Ciò è particolarmente utile per le organizzazioni che utilizzano servizi cloud e le applicazioni server locale. Integrazione con un server SIEM consente al team di protezione migliorare la protezione delle applicazioni di Office 365 mantenendo il flusso di lavoro normale protezione automazione alcune procedure di sicurezza e la correlazione tra basata su cloud e locali degli eventi.  
  
Quando si integra innanzitutto il server SIEM con Office 365 Cloud App protezione, gli avvisi dagli ultimi due giorni vengono inoltrati al server SIEM e tutti gli avvisi da quindi su (basato su alcun filtro selezionato). Inoltre, se si disattiva questa caratteristica per un periodo prolungato, quando si riattivarlo, inoltrerà ultimi due giorni di avvisi e quindi tutti gli avvisi in poi.

### <a name="siem-integration-architecture"></a>Architettura dell'integrazione SIEM

Un agente SIEM è impostato nella rete dell'organizzazione. Se distribuito e configurato, l'agente SIEM tutti i tipi di dati che sono stati configurati (avvisi) utilizzando l'API REST di Office 365 Cloud App sicurezza. Il traffico viene quindi inviato attraverso un canale HTTPS crittografato sulla porta 443.
  
Quando un agente SIEM recupera i dati di sicurezza di Office 365 Cloud App, invia i messaggi del Registro di sistema per server SIEM locale utilizzando le configurazioni di rete che sono disponibili durante l'installazione (TCP o UDP con una porta personalizzata).

![Architettura SIEM e sicurezza App Cloud](media/siem-architecture.png)

### <a name="supported-siem-servers"></a>Server SIEM supportati

Protezione di Office 365 Cloud App supporta attualmente server SIEM seguenti:
- Lo stato attivo Micro ArcSight
- Formato CEF generico

### <a name="prerequisites"></a>Prerequisiti

- È necessario essere un amministratore globale o sicurezza per eseguire le attività descritte in questo articolo. Vedere [le autorizzazioni di sicurezza di Office 365 &amp; centro conformità](permissions-in-the-security-and-compliance-center.md)

- È necessario che [Office 365 Cloud App protetto](turn-on-office-365-cas.md) per l'organizzazione.

- [Registrazione di controllo](turn-audit-log-search-on-or-off.md) deve essere attivata per Office 365

- Deve disporre di un server standard che soddisfi i requisiti seguenti per configurare l'integrazione del server SIEM:
    - Sistema operativo: Windows o Linux (può essere una macchina virtuale)
    - CPU: 2
    - Spazio su disco: 20 GB
    - RAM: 2 GB
    - [Oracle Java 8](http://www.oracle.com/technetwork/java/javase/downloads/index.html) installato
    - Firewall configurati come descritto in [requisiti di rete](https://docs.microsoft.com/cloud-app-security/network-requirements)

- È necessario disporre di dettagli del **Registro di sistema remoto host** e **numero di porta Syslot**. Un amministratore di rete o un amministratore di sicurezza deve essere in grado di individuare tali informazioni. 

- È necessario accettare le [condizioni di licenza software](https://go.microsoft.com/fwlink/?linkid=862491) scaricare il [file JAR](https://go.microsoft.com/fwlink/?linkid=838596) è necessario effettuare l'integrazione del server SIEM.
 
## <a name="step-1-set-it-up-a-siem-agent-in-office-365-cloud-app-security"></a>Passaggio 1: Configurarlo in un agente SIEM nella sicurezza App Cloud di Office 365

1. Accedere a [https://protection.office.com](https://protection.office.com) e accedere utilizzando l'account di lavoro o della scuola per Office 365. (Si passa alla sicurezza &amp; centro conformità.) 
    
2. Accedere agli **avvisi** \> **Gestione avanzata degli avvisi**.
    
3. Scegliere **Vai a Office 365 Cloud App protezione**.<br/>
    ![In sicurezza &amp; centro conformità, selezionare Gestisci avvisi avanzate per accedere alla sicurezza di Office 365 Cloud App](media/958632d4-03e3-4ade-8e22-d5509db6fca7.png)
  
4. Fare clic su **Impostazioni** \> **estensioni di protezione**.<br/>
![Scegliere Impostazioni > estensioni di protezione](media/Settings-SecurityExtensions.png)

5. Scegliere **Aggiungi SIEM agente**.<br/>![Selezionare Aggiungi SIEM agente.](media/SIEMAgents.png)
    
6. Scegliere **Avvia procedura guidata**.<br/>![Ottieni assistenza o avviare la procedura guidata](media/HelpOrWizard.png) 
    
7. Nel passaggio **Generale** , specificare un nome e **Selezionare il formato SIEM** e impostare le **Impostazioni avanzate** di interesse per tale formato. Quindi scegliere **Avanti**.<br/>![Specificare un nome e tipo](media/ChooseAgentTypeAndName.png)
    
8. Al passaggio del **Registro di sistema remoto** , specificare l'indirizzo IP o nome host dell' **host del Registro di sistema remoto** e il **numero di porta del Registro di sistema**. Selezionare TCP o UDP come protocollo di registro di sistema remoto. (È possibile utilizzare con l'amministratore di rete o un amministratore della sicurezza per ottenere queste informazioni dettagliate, se non disponi.) Quindi scegliere **Avanti**.<br/>![Specificare i dettagli di registro di sistema remoto](media/ArcSightS1Syslog.png)
  
9. Nel passaggio **Tipi di dati** , effettuare una delle opzioni seguenti e quindi fare clic su **Avanti**:
    - Mantenere l'impostazione predefinita di **Tutti gli avvisi**<br/>OPPURE
    - Fare clic su **tutti gli avvisi**e quindi fare clic su **filtri specifici**. Definire i filtri per selezionare i tipi di avvisi che si desidera inviare al server SIEM.<br/>![Passaggio di tipi di dati della procedura guidata](media/ArcSightS1ExportOptions.png)
  
10. Nella schermata Congratulazioni, copiare il token e salvarlo per utilizzi successivi.<br/>![Schermata agente creato SIEM](media/SIEMAgentFinished.png) 

> [!IMPORTANT]
> A questo punto è stato impostato un agente SIEM nella sicurezza App Cloud di Office 365, ma l'integrazione del server SIEM non è ancora completato. Procedere al passaggio successivo per continuare l'integrazione del server SIEM.

Dopo aver fare clic su Chiudi e uscire dalla procedura guidata, nella schermata di estensioni di protezione, è possibile visualizzare l'agente SIEM che è stato aggiunto nella tabella. Viene visualizzato lo stato **creato** fino a quando non si connette più avanti.

![Agente SIEM creato](media/SIEMAgentCreated.png)
    
## <a name="step-2-download-a-jar-file-and-run-it-on-your-siem-server"></a>Passaggio 2: Scaricare un file con estensione JAR ed eseguirlo nel server SIEM

1. Scaricare [Microsoft Cloud App sicurezza SIEM Agent](https://go.microsoft.com/fwlink/?linkid=838596) e decomprimere la cartella. (È necessario accettare le [condizioni di licenza software](https://go.microsoft.com/fwlink/?linkid=862491) per continuare.) 
    
2. Estrarre il file JAR dalla cartella compressa ed eseguirlo nel server SIEM.
    
3. Dopo aver eseguito il file, eseguire le operazioni seguenti: comando:<br/>
  ```
  java -jar mcas-siemagent-0.87.20-signed.jar [--logsDirectory DIRNAME] [--proxy ADDRESS[:PORT]] --token TOKEN
  ```
### <a name="important-notes"></a>Note importanti

- Il nome del file può variare a seconda della versione dell'agente SIEM. 

- È consigliabile eseguire il file JAR nel server SIEM durante l'installazione di server.

    - **Windows**: eseguito come attività pianificata, assicurandosi di configurare l'attività da **eseguire se l'utente è connesso o meno** e deselezionare l'opzione **interrompere l'operazione se non si verifica più di** .

    - **Linux**: aggiungere il comando Esegui con un **&** per il `rc.local` file. <br/>Esempio:<br/> 
    ```
    java -jar mcas-siemagent-0.87.20-signed.jar [--logsDirectory DIRNAME] [--proxy ADDRESS[:PORT]] --token TOKEN &
    ```

- Parametri [] tra parentesi quadre sono facoltativi e devono essere utilizzati solo se pertinenti. Utilizzare le variabili seguenti:

    - **DIRNAME** è il percorso della directory da utilizzare per i registri di debug agente locale.

    - **Indirizzo [: porta]** è l'indirizzo del server proxy e la porta utilizzati dal server per la connessione a Internet.

    - **TOKEN** è il token agente SIEM che sono stati copiati in routine prima.

    - Per visualizzare la Guida, digitare `-h`. 
  
## <a name="step-3-validate-that-the-siem-agent-is-working"></a>Passaggio 3: Verificare che l'agente SIEM funzioni correttamente

1. Verificare che lo stato dell'agente SIEM nel portale di Office 365 Cloud App protezione non viene visualizzato come **errore di connessione** o **disconnesso** e che non sono presenti notifiche agente.<br/>Ad esempio, qui è possibile visualizzare che è connesso il server SIEM:<br/>![Server SIEM connesso](media/siem-connected.png)<br/>E visualizzare in questo caso, che il server SIEM viene disconnesso:<br/>![Server SIEM non connesso](media/siem-not-connected.png) 
  
2. Nel server di registro di sistema/SIEM, verificare che sia incluso che avvisi ricevuti da sicurezza App Cloud di Office 365.
  
## <a name="what-the-logfiles-look-like"></a>Che aspetto i file di registro

Ecco un esempio di file di registro degli avvisi che può essere inviato a un server SIEM:

```
2017-07-15T20:42:30.531Z CEF:0|MCAS|SIEM_Agent|0.102.17|ALERT_CABINET_EVENT_MATCH_AUDIT|myPolicy|3|externalId=596a7e360c204203a335a3fb start=1500151350531 end=1500151350531 msg=Activity policy ''myPolicy'' was triggered by ''admin@box-contoso.com'' suser=admin@box-contoso.com destinationServiceName=Box cn1Label=riskScore cn1= cs1Label=portalURL cs1=https://cloud-app-security.com/#/alerts/596a7e360c204203a335a3fb cs2Label=uniqueServiceAppIds cs2=APPID_BOX cs3Label=relatedAudits cs3=1500151288183_acc891bf-33e1-424b-a021-0d4370789660 cs4Label=policyIDs cs4=59f0ab82f797fa0681e9b1c7

2017-07-16T09:36:26.550Z CEF:0|MCAS|SIEM_Agent|0.102.17|ALERT_CABINET_EVENT_MATCH_AUDIT|test-activity-policy|3|externalId=596b339b0c204203a33a51ae start=1500197786550 end=1500197786550 msg=Activity policy ''test-activity-policy'' was triggered by ''user@contoso.com'' suser=user@contoso.com destinationServiceName=Salesforce cn1Label=riskScore cn1= cs1Label=portalURL cs1=https://cloud-app-security.com/#/alerts/596b339b0c204203a33a51ae cs2Label=uniqueServiceAppIds cs2=APPID_SALESFORCE cs3Label=relatedAudits cs3=1500197720691_b7f6317c-b8de-476a-bc8f-dfa570e00349 cs4Label=policyIDs cs4=

2017-07-16T09:17:03.361Z CEF:0|MCAS|SIEM_Agent|0.102.17|ALERT_CABINET_EVENT_MATCH_AUDIT|test-activity-policy3|3|externalId=596b2fd70c204203a33a3eeb start=1500196623361 end=1500196623361 msg=Activity policy ''test-activity-policy3'' was triggered by ''admin@contoso.com'' suser=admin@contoso.com destinationServiceName=Office 365 cn1Label=riskScore cn1= cs1Label=portalURL cs1=https://cloud-app-security.com/#/alerts/596b2fd70c204203a33a3eeb cs2Label=uniqueServiceAppIds cs2=APPID_O365 cs3Label=relatedAudits cs3=1500196549157_a0e01f8a-e29a-43ae-8599-783c1c11597d cs4Label=policyIDs cs4=

2017-07-16T09:17:15.426Z CEF:0|MCAS|SIEM_Agent|0.102.17|ALERT_CABINET_EVENT_MATCH_AUDIT|test-activity-policy|3|externalId=596b2fd70c204203a33a3eec start=1500196635426 end=1500196635426 msg=Activity policy ''test-activity-policy'' was triggered by ''admin@contoso.com'' suser=admin@contoso.com destinationServiceName=Microsoft Office 365 admin center cn1Label=riskScore cn1= cs1Label=portalURL cs1=https://cloud-app-security.com/#/alerts/596b2fd70c204203a33a3eec cs2Label=uniqueServiceAppIds cs2=APPID_O365_PORTAL cs3Label=relatedAudits cs3=1500196557398_3e102b20-d9fa-4f66-b550-8c7a403bb4d8 cs4Label=policyIDs cs4=59f0ab35f797fa9811e9b1c7

2017-07-16T09:17:46.290Z CEF:0|MCAS|SIEM_Agent|0.102.17|ALERT_CABINET_EVENT_MATCH_AUDIT|test-activity-policy4|3|externalId=596b30200c204203a33a4765 start=1500196666290 end=1500196666290 msg=Activity policy ''test-activity-policy4'' was triggered by ''admin@contoso.com'' suser=admin@contoso.com destinationServiceName=Microsoft Exchange Online cn1Label=riskScore cn1= cs1Label=portalURL cs1=https://cloud-app-security.com/#/alerts/596b30200c204203a33a4765 cs2Label=uniqueServiceAppIds cs2=APPID_OUTLOOK cs3Label=relatedAudits cs3=1500196587034_a8673602-7e95-46d6-a1fe-c156c4709c5d cs4Label=policyIDs cs4=

2017-07-16T09:41:04.369Z CEF:0|MCAS|SIEM_Agent|0.102.17|ALERT_CABINET_EVENT_MATCH_AUDIT|test-activity-policy2|3|externalId=596b34b10c204203a33a5240 start=1500198064369 end=1500198064369 msg=Activity policy ''test-activity-policy2'' was triggered by ''user2@test15-adallom.com'' suser=user2@test15-adallom.com destinationServiceName=Google cn1Label=riskScore cn1= cs1Label=portalURL cs1=https://cloud-app-security.com/#/alerts/596b34b10c204203a33a5240 cs2Label=uniqueServiceAppIds cs2=APPID_33626 cs3Label=relatedAudits cs3=1500197996117_fd71f265-1e46-4f04-b372-2e32ec874cd3 cs4Label=policyIDs cs4=
```

Inoltre, ecco un altro esempio, questa volta nel formato il formato CEF:


|Nome del campo il formato CEF  | Descrizione  |
|---------|---------|
|avviare     | Data/ora degli avvisi        |
|fine     | Data/ora degli avvisi        |
|round trip     | Data/ora degli avvisi        |
|msg     | descrizione di avviso, come illustrato nel portale di Office 365 Cloud App Security        |
|suser     | utente soggetto degli avvisi        |
|destinationServiceName     | avviso originari app, ad esempio Office 365, SharePoint o OneDrive        |
|csLabel     | Varia (etichette avere significati diversi). In genere, le etichette sono di chiara interpretazione, ad esempio targetObjects.        |
|cs     | Informazioni corrispondente a un'etichetta (ad esempio, l'utente di destinazione di un avviso come riportato nell'esempio di etichetta)        |

## <a name="additional-tasks-as-needed"></a>Attività aggiuntive (se necessario)

Dopo aver configurato il server SIEM e hanno integrato con protezione App Cloud di Office 365, potrebbe essere necessario rigenerare un token, modificare un agente SIEM o eliminare un agente SIEM. Nelle sezioni seguenti viene descritto come eseguire queste attività.

### <a name="regenerate-a-token"></a>Rigenerare un token

Se si perde il token, sarà possibile rigenerare una. 

1. Nel portale di protezione di Office 365 Cloud App, scegliere **Impostazioni** > **estensioni di protezione**.

2. Nella tabella, individuare la riga per l'agente SIEM. 

3. Fare clic sui puntini di sospensione e quindi fare clic su **rigenerare token**.<br/>![Rigenerare un token facendo clic sui puntini di sospensione per l'agente SIEM](media/04de368a-b88e-4a9c-a830-58025cb98db6.png)
  
### <a name="edit-a-siem-agent"></a>Modificare un agente SIEM

1. Nel portale di protezione di Office 365 Cloud App, scegliere **Impostazioni** > **estensioni di protezione**.

2. Individuare la riga per l'agente SIEM. 

3. Fare clic sui puntini di sospensione e quindi fare clic su **Modifica**. (Se si modifica l'agente SIEM, non necessaria eseguire di nuovo il file JAR, aggiorna automaticamente).<br/>![Per modificare l'agente SIEM, fare clic sui puntini di sospensione e quindi scegliere Modifica.](media/96d0b362-3e0c-4dff-b2b4-d7af5b1bfb91.png)
  
### <a name="delete-a-siem-agent"></a>Eliminare un agente SIEM

1. Nel portale di protezione di Office 365 Cloud App, scegliere **Impostazioni** > **estensioni di protezione**.

2. Individuare la riga per l'agente SIEM. 

3. Fare clic sui puntini di sospensione e quindi fare clic su **Elimina**.<br/>![Per eliminare un agente SIEM, fare clic sui puntini di sospensione e quindi fare clic su Elimina.](media/540b5bdf-5574-4ecc-a7b0-92a499a387d7.png)

  
## <a name="next-steps"></a>Passaggi successivi

- [Attività di utilizzo dopo la distribuzione di Office 365 Cloud App Security](utilization-activities-for-ocas.md)
    
- [Leggere ed eseguire l'azione gli avvisi](review-office-365-cas-alerts.md)
    
- [Gli indirizzi IP per semplificare la gestione di gruppo](group-your-ip-addresses-in-ocas.md)
    

