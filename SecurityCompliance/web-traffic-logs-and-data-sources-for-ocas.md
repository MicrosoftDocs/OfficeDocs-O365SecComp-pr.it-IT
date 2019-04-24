---
title: Log del traffico Web e origini dati per Office 365 Cloud App Security
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 12/26/2018
ms.audience: ITPro
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 290b02bf-a988-4fb9-88b2-34e408216ac8
description: Office 365 cloud app Security è compatibile con i log del traffico Web da una vasta gamma di provider. Leggere questo articolo per ulteriori informazioni sui log del traffico Web e le origini dati supportate per Office 365 cloud app Security.
ms.openlocfilehash: 67246ded0e3d39c81b5b906f753b91298309d1d8
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "32266851"
---
# <a name="web-traffic-logs-and-data-sources-for-office-365-cloud-app-security"></a>Log del traffico Web e origini dati per Office 365 Cloud App Security
  
|Valutazione * *\>**|Planning * *\>**|Distribuzione * *\>**|Utilizzo * * * *|
|:-----|:-----|:-----|:-----|
|[Iniziare a valutare](office-365-cas-overview.md) <br/> |[Avviare la pianificazione](get-ready-for-office-365-cas.md) <br/> |[Avviare la distribuzione](turn-on-office-365-cas.md) <br/> |Sei qui!  <br/> [Passaggi successivi](#next-steps) <br/> |
  
È possibile utilizzare una vasta gamma di file di registro del traffico Web e origini dati con Office 365 cloud app Security. Tuttavia, i file di registro del traffico Web devono includere informazioni specifiche ed essere formattati in modo che funzionino con i report di individuazione delle app di sicurezza di Office 365 cloud app Security e con il dashboard di individuazione cloud. Utilizzare questo articolo come guida di riferimento per i log del traffico Web e le origini dati che verranno utilizzate con Office 365 cloud app Security.
  
> [!NOTE]
> È necessario essere un amministratore globale, un amministratore della sicurezza o un lettore di sicurezza per &amp; accedere al centro sicurezza e conformità di Office 365 cloud app Security Portal. Vedere [Permissions in the Office &amp; 365 Security Compliance Center](permissions-in-the-security-and-compliance-center.md). 
  
## <a name="web-traffic-log-requirements"></a>Requisiti per i registri del traffico Web

Office 365 cloud app Security utilizza i dati nei log del traffico Web per capire quali app stanno usando le persone dell'organizzazione. Più dettagli sono inclusi nei file di log, maggiore è la visibilità che si avrà nell'attività dell'utente.
  
Nelle sezioni seguenti sono elencati gli attributi necessari e i requisiti aggiuntivi per i log del traffico Web per funzionare correttamente con Office 365 cloud app Security.

### <a name="attributes"></a>Attributi

Office 365 cloud app Security non è in grado di visualizzare o analizzare gli attributi che non sono inclusi nei log del traffico Web. Ad esempio, il formato di registro standard del firewall Cisco ASA non ha il numero di byte caricati per transazione, il nome utente o l'URL di destinazione (solo un indirizzo IP di destinazione). Pertanto, tali attributi non vengono visualizzati nei dati di individuazione del cloud e la visibilità nelle app Cloud è limitata. Per i firewall Cisco ASA, è necessario che il livello di informazioni sia impostato su 6. 

I log del traffico Web devono includere gli attributi seguenti:

- Data della transazione
- IP origine
- Utente di origine (altamente consigliato)
- Indirizzo IP di destinazione
- URL di destinazione (consigliato; Gli URL offrono maggiore accuratezza per il rilevamento delle app Cloud rispetto agli indirizzi IP)
- Quantità totale di dati (scelta consigliata; informazioni sui dati è estremamente importante)
- Quantità di dati caricati o scaricati (scelta consigliata, in cui vengono fornite informazioni dettagliate sui modelli di utilizzo delle app Cloud)
- Azione intrapresa (consentita o bloccata)

### <a name="additional-requirements"></a>Requisiti aggiuntivi 

Oltre a includere gli attributi descritti in precedenza in questo articolo, i log del traffico Web devono soddisfare i requisiti seguenti:

- L'origine dati per i file di registro deve essere supportata.
- Il formato utilizzato dai file di registro deve corrispondere al formato standard. Quando il file viene caricato, l'individuazione delle app lo verificherà.
- Gli eventi nel registro devono avere avuto luogo non più di 90 giorni fa.
- Il file di registro deve includere le informazioni sul traffico in uscita che possono essere analizzate per l'attività di rete.
  
## <a name="data-attributes-for-different-vendors"></a>Attributi dei dati per i diversi fornitori

Nella tabella seguente vengono riepilogate le informazioni contenute nei log del traffico Web di vari fornitori. **Assicurarsi di controllare con il fornitore le informazioni più aggiornate.**


|                 Origine dati                  |    URL dell'app di destinazione    |    Indirizzo IP app di destinazione     |       Nome utente       |      IP di origine       |    Traffico totale     |    Byte caricati    |
|----------------------------------------------|----------------------|----------------------|----------------------|----------------------|----------------------|----------------------|
|                  Barracuda                   | <strong>Sì</strong> | <strong>Sì</strong> | <strong>Sì</strong> | <strong>Sì</strong> |          No          |          No          |
|                  Cappotto blu                   | <strong>Sì</strong> |          No          | <strong>Sì</strong> | <strong>Sì</strong> | <strong>Sì</strong> | <strong>Sì</strong> |
|                  Checkpoint                  |          No          | <strong>Sì</strong> |          No          | <strong>Sì</strong> |          No          |          No          |
|              Cisco ASA (syslog)              |          No          | <strong>Sì</strong> |          No          | <strong>Sì</strong> | <strong>Sì</strong> |          No          |
|           Cisco ASA con potenza di fuoco           | <strong>Sì</strong> | <strong>Sì</strong> | <strong>Sì</strong> | <strong>Sì</strong> | <strong>Sì</strong> | <strong>Sì</strong> |
|                  Cisco FWSM                  |          No          | <strong>Sì</strong> |          No          | <strong>Sì</strong> | <strong>Sì</strong> |          No          |
|              Cisco IronPort WSA              | <strong>Sì</strong> | <strong>Sì</strong> | <strong>Sì</strong> | <strong>Sì</strong> | <strong>Sì</strong> | <strong>Sì</strong> |
|                 Cisco Meraki                 | <strong>Sì</strong> | <strong>Sì</strong> |          No          | <strong>Sì</strong> |          No          |          No          |
|           NGFW Clavister (syslog)            | <strong>Sì</strong> | <strong>Sì</strong> | <strong>Sì</strong> | <strong>Sì</strong> | <strong>Sì</strong> | <strong>Sì</strong> |
|                SonicWall (in precedenza dell)                | <strong>Sì</strong> | <strong>Sì</strong> |          No          | <strong>Sì</strong> | <strong>Sì</strong> | <strong>Sì</strong> |
|            Digital Arts i-FILTER             | <strong>Sì</strong> | <strong>Sì</strong> | <strong>Sì</strong> | <strong>Sì</strong> | <strong>Sì</strong> | <strong>Sì</strong> |
|                  FortiGate                   |          No          | <strong>Sì</strong> |          No          | <strong>Sì</strong> | <strong>Sì</strong> | <strong>Sì</strong> |
|                 Juniper SRX                  |          No          | <strong>Sì</strong> |          No          | <strong>Sì</strong> | <strong>Sì</strong> | <strong>Sì</strong> |
|                 Il ginepro SSG                  |          No          | <strong>Sì</strong> | <strong>Sì</strong> | <strong>Sì</strong> | <strong>Sì</strong> | <strong>Sì</strong> |
|                  McAfee SWG                  | <strong>Sì</strong> |          No          |          No          | <strong>Sì</strong> | <strong>Sì</strong> | <strong>Sì</strong> |
|                    MS TMG                    | <strong>Sì</strong> |          No          | <strong>Sì</strong> | <strong>Sì</strong> | <strong>Sì</strong> | <strong>Sì</strong> |
|              Reti di palo alto              |          No          | <strong>Sì</strong> | <strong>Sì</strong> | <strong>Sì</strong> | <strong>Sì</strong> | <strong>Sì</strong> |
|                    Sophos                    | <strong>Sì</strong> | <strong>Sì</strong> | <strong>Sì</strong> | <strong>Sì</strong> | <strong>Sì</strong> |          No          |
|                Squid (comune)                | <strong>Sì</strong> |          No          | <strong>Sì</strong> | <strong>Sì</strong> |          No          | <strong>Sì</strong> |
|                Squid (nativo)                | <strong>Sì</strong> |          No          | <strong>Sì</strong> | <strong>Sì</strong> |          No          | <strong>Sì</strong> |
| Websense-report dettagli indagine (CSV) | <strong>Sì</strong> | <strong>Sì</strong> | <strong>Sì</strong> | <strong>Sì</strong> | <strong>Sì</strong> | <strong>Sì</strong> |
|    Websense-registro attività Internet (CEF)    | <strong>Sì</strong> | <strong>Sì</strong> | <strong>Sì</strong> | <strong>Sì</strong> | <strong>Sì</strong> | <strong>Sì</strong> |
|                   ZScaler                    | <strong>Sì</strong> | <strong>Sì</strong> | <strong>Sì</strong> | <strong>Sì</strong> | <strong>Sì</strong> | <strong>Sì</strong> |
   
## <a name="supported-vendor-firewalls-and-proxies"></a>Firewall e proxy del fornitore supportati

Office 365 cloud app Security supporta i firewall e i proxy seguenti.
  
- Barracuda-Web app firewall (W3C)  
- Blue Coat proxy SG-access log (W3C)
- Punto di controllo
- Firewall Cisco ASA (accertarsi di impostare il livello di informazioni su 6)
- Cisco ASA con potenza di fuoco   
- Cisco IronPort WSA
- Cisco ScanSafe
- Cisco Merkai-URL log
- NGFW Clavister (syslog)
- Digital Arts i-FILTER
- Fortinet Fortigate
- Gateway cloud protetto di iboss
- Juniper SRX
- Il ginepro SSG
- Gateway Web McAfee sicuro
- Microsoft Forefront Threat Management Gateway (W3C)
- Firewall serie palo alto
- SonicWALL (in precedenza dell)   
- Sophos SG
- Sophos XG
- Sophos Cyberoam
- Squid (comune)
- Squid (nativo)
- Websense-soluzioni per la sicurezza Web-report dettagli indagine (CSV)
- Websense-soluzioni per la sicurezza Web-registro attività Internet (CEF)
- ZScaler
    
> [!NOTE]
> Se un'origine dati che si desidera utilizzare non è inclusa in questa sezione, è possibile richiederne l'aggiunta all'individuazione delle app. A tale scopo, quando si crea un report, selezionare **altro** per l' **origine dati**. Digitare quindi il nome dell'origine dati che si sta tentando di caricare. È possibile esaminare il registro e sapere se viene aggiunto il supporto per il tipo di registro. In alternativa, è possibile [definire un parser personalizzato](https://docs.microsoft.com/cloud-app-security/custom-log-parser) che corrisponda al formato. 
  
## <a name="troubleshoot-errors-when-log-files-are-uploaded"></a>Risoluzione degli errori di caricamento dei file di registro

Dopo aver caricato i file di registro del traffico Web, controllare il registro di governance per verificare se sono presenti errori. Se si verificano errori, utilizzare le informazioni riportate nella tabella seguente per risolvere tali errori.
  
|**Errore**|**Descrizione**|**Soluzione**|
|:-----|:-----|:-----|
|Tipo di file non supportato  <br/> |Il file caricato non è un file di registro valido. Ad esempio, un file di immagine.  <br/> |Caricare un file di testo, zip o gzip direttamente esportato dal firewall o dal proxy.  <br/> |
|Errore interno  <br/> |È stato rilevato un errore interno delle risorse.  <br/> |Fare **** clic su Riprova per rieseguire l'attività.  <br/> |
|Il formato del registro non corrisponde  <br/> |Il formato del log caricato non corrisponde al formato di registro previsto per l'origine dati.  <br/> |
Verificare che il registro non sia danneggiato. Confrontare e associare il formato di file di registro al formato di esempio visualizzato nella pagina caricamento. |
|Le transazioni hanno più di 90 giorni.  <br/> |Tutte le transazioni hanno più di 90 giorni e pertanto vengono ignorate.  <br/> |Esportare un nuovo log con gli eventi recenti e ricaricarlo.  <br/> |
|Nessuna transazione per le app del cloud Catalogo  <br/> |Nessuna transazione per le app Cloud riconosciute si trova nel registro.  <br/> |Verificare che il registro contenga informazioni sul traffico in uscita.  <br/> |
|Tipo di log non supportato  <br/> |Quando si seleziona **origine dati = altro (non supportato)**, il log non viene analizzato. Viene invece inviato per la revisione al team tecnico di [Microsoft cloud app Security](https://aka.ms/whatiscas) .  <br/> |Il team tecnico [Microsoft cloud app Security](https://aka.ms/whatiscas) crea un parser dedicato per ogni origine dati. Le origini dati più popolari sono già supportate. Quando viene caricata un'origine dati non supportata, questa viene esaminata e aggiunta all'elenco dei potenziali nuovi analizzatori di origine dati.  <br/> Quando viene aggiunto un nuovo parser alla funzionalità, viene inclusa una notifica nelle note sulla versione di sicurezza di Microsoft cloud app.  <br/> |
   
## <a name="next-steps"></a>Passaggi successivi

- [Esaminare e intervenire sugli avvisi](review-office-365-cas-alerts.md)
    
- [Creare report di individuazione delle app](create-app-discovery-reports-in-ocas.md)
    
- [Esaminare i risultati dell'individuazione delle app](review-app-discovery-findings-in-ocas.md)
    
- [Esaminare le attività di utilizzo per Office 365 cloud app Security](utilization-activities-for-ocas.md)
    

