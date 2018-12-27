---
title: Log del traffico Web e origini dati per Office 365 Cloud App Security
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 12/26/2018
ms.audience: ITPro
ms.topic: reference
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 290b02bf-a988-4fb9-88b2-34e408216ac8
description: Office 365 Cloud App sicurezza utilizza i registri di traffico web da una vasta gamma di provider. Leggere questo articolo per ulteriori informazioni su registri di traffico web e le origini dati è supportata per la protezione di Office 365 Cloud App.
ms.openlocfilehash: ab962e4a030d06c133ad9fc4aa62a60755793bc3
ms.sourcegitcommit: 25f72d20e76463c2f0a075dfc0116f00c934bd77
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/27/2018
ms.locfileid: "27447054"
---
# <a name="web-traffic-logs-and-data-sources-for-office-365-cloud-app-security"></a>Log del traffico Web e origini dati per Office 365 Cloud App Security
  
|Valutazione * *\>**|Pianificazione * *\>**|Distribuzione * *\>**|Utilizzo * * *|
|:-----|:-----|:-----|:-----|
|[Avviare la valutazione](office-365-cas-overview.md) <br/> |[Iniziare a pianificare](get-ready-for-office-365-cas.md) <br/> |[Avviare la distribuzione](turn-on-office-365-cas.md) <br/> |Si è seguito!  <br/> [Passaggi successivi](#next-steps) <br/> |
  
È possibile utilizzare una vasta gamma di origini dati e i file di registro del traffico web con Office 365 Cloud App protezione. Tuttavia, i file di registro del traffico web devono includere informazioni specifiche ed essere formattati in modo particolare in modo che possano funzionare con Office 365 Cloud App sicurezza app individuazione rapporti e dashboard individuazione Cloud. Utilizzare questo articolo come guida di riferimento per le origini dati da utilizzare con Office 365 Cloud App protezione e il log del traffico web.
  
> [!NOTE]
> È necessario essere un amministratore globale, l'amministratore della sicurezza o lettore di protezione per la protezione dall'accesso di &amp; portal centro conformità e sicurezza App Cloud di Office 365. Vedere [le autorizzazioni di sicurezza di Office 365 &amp; centro conformità](permissions-in-the-security-and-compliance-center.md). 
  
## <a name="web-traffic-log-requirements"></a>Requisiti di registro del traffico Web

Utilizzano Office 365 Cloud App sicurezza utilizzi dati nei file registro il traffico web utili per comprendere quali App utenti nell'organizzazione. Ulteriori informazioni incluse nei file di registro, il miglioramento della visibilità, è necessario attività dell'utente.
  
Nelle sezioni seguenti vengono elencati gli attributi e necessari ulteriori requisiti per i registri di traffico web funzioni correttamente con Office 365 Cloud App sicurezza.

### <a name="attributes"></a>Attributi

Office 365 Cloud App protezione non possono visualizzare o analizzare gli attributi che non vengono inclusi nei registri traffico web. Formato del Registro standard del Firewall ASA Cisco non dispone ad esempio, il numero di byte caricati per ogni transazione, il nome utente o un URL di destinazione (solo un indirizzo IP destinazione). Di conseguenza, questi attributi non vengono visualizzati nei dati di individuazione Cloud e della visibilità applicazioni basate su cloud è limitata. Per i firewall ASA Cisco, è necessario impostare il livello di informazioni su 6. 

I registri di traffico web devono includere i seguenti attributi:

- Data della transazione
- IP origine
- Utente di origine (scelta consigliata)
- Indirizzo IP di destinazione
- URL di destinazione (impostazione consigliata; URL offrono maggiore precisione per il rilevamento delle app cloud di indirizzi IP)
- Quantità totale di dati (scelta consigliata; informazioni sui dati è molto utile)
- Tempo di caricamento o il download dei dati (scelta consigliata; vengono fornite informazioni su cloud modelli di utilizzo app)
- Azione eseguita (consentite o bloccate)

### <a name="additional-requirements"></a>Requisiti aggiuntivi 

Oltre agli attributi elencati in precedenza in questo articolo, i registri di traffico web devono soddisfare i requisiti seguenti:

- L'origine dati per i file di registro deve essere supportata.
- Il formato di che utilizzano i file di registro deve corrispondere al formato standard. Quando viene caricato il file, l'individuazione app verifica seguente.
- Gli eventi nel registro necessario hanno avuto luogo non più di 90 giorni.
- Il file di registro deve includere informazioni sul traffico in uscita che può essere analizzate per attività di rete.
  
## <a name="data-attributes-for-different-vendors"></a>Attributi di dati per i fornitori diversi

Nella tabella seguente sono riepilogate le informazioni nel log di traffico web da vari fornitori. **è necessario contattare il fornitore per le informazioni più aggiornate.**


|                 Origine dati                  |    URL di App di destinazione    |    IP App di destinazione     |       Nome utente       |      Origine IP       |    Totale del traffico     |    Byte caricati    |
|----------------------------------------------|----------------------|----------------------|----------------------|----------------------|----------------------|----------------------|
|                  Barracuda                   | <strong>Sì</strong> | <strong>Sì</strong> | <strong>Sì</strong> | <strong>Sì</strong> |          No          |          No          |
|                  Coprire blu                   | <strong>Sì</strong> |          No          | <strong>Sì</strong> | <strong>Sì</strong> | <strong>Sì</strong> | <strong>Sì</strong> |
|                  Punto di controllo                  |          No          | <strong>Sì</strong> |          No          | <strong>Sì</strong> |          No          |          No          |
|              Cisco ASA (Registro di sistema)              |          No          | <strong>Sì</strong> |          No          | <strong>Sì</strong> | <strong>Sì</strong> |          No          |
|           Cisco ASA con FirePOWER           | <strong>Sì</strong> | <strong>Sì</strong> | <strong>Sì</strong> | <strong>Sì</strong> | <strong>Sì</strong> | <strong>Sì</strong> |
|                  Cisco FWSM                  |          No          | <strong>Sì</strong> |          No          | <strong>Sì</strong> | <strong>Sì</strong> |          No          |
|              Cisco Ironport WSA              | <strong>Sì</strong> | <strong>Sì</strong> | <strong>Sì</strong> | <strong>Sì</strong> | <strong>Sì</strong> | <strong>Sì</strong> |
|                 Cisco Meraki                 | <strong>Sì</strong> | <strong>Sì</strong> |          No          | <strong>Sì</strong> |          No          |          No          |
|           Clavister NGFW (Registro di sistema)            | <strong>Sì</strong> | <strong>Sì</strong> | <strong>Sì</strong> | <strong>Sì</strong> | <strong>Sì</strong> | <strong>Sì</strong> |
|                SonicWall (precedentemente Dell)                | <strong>Sì</strong> | <strong>Sì</strong> |          No          | <strong>Sì</strong> | <strong>Sì</strong> | <strong>Sì</strong> |
|            I filtri arte digitale             | <strong>Sì</strong> | <strong>Sì</strong> | <strong>Sì</strong> | <strong>Sì</strong> | <strong>Sì</strong> | <strong>Sì</strong> |
|                  FortiGate                   |          No          | <strong>Sì</strong> |          No          | <strong>Sì</strong> | <strong>Sì</strong> | <strong>Sì</strong> |
|                 Juniper SRX                  |          No          | <strong>Sì</strong> |          No          | <strong>Sì</strong> | <strong>Sì</strong> | <strong>Sì</strong> |
|                 Juniper SSG                  |          No          | <strong>Sì</strong> | <strong>Sì</strong> | <strong>Sì</strong> | <strong>Sì</strong> | <strong>Sì</strong> |
|                  McAfee SWG                  | <strong>Sì</strong> |          No          |          No          | <strong>Sì</strong> | <strong>Sì</strong> | <strong>Sì</strong> |
|                    TMG MS                    | <strong>Sì</strong> |          No          | <strong>Sì</strong> | <strong>Sì</strong> | <strong>Sì</strong> | <strong>Sì</strong> |
|              Reti Palo Alto              |          No          | <strong>Sì</strong> | <strong>Sì</strong> | <strong>Sì</strong> | <strong>Sì</strong> | <strong>Sì</strong> |
|                    Sophos                    | <strong>Sì</strong> | <strong>Sì</strong> | <strong>Sì</strong> | <strong>Sì</strong> | <strong>Sì</strong> |          No          |
|                Calamaro (comune)                | <strong>Sì</strong> |          No          | <strong>Sì</strong> | <strong>Sì</strong> |          No          | <strong>Sì</strong> |
|                Calamaro (nativa)                | <strong>Sì</strong> |          No          | <strong>Sì</strong> | <strong>Sì</strong> |          No          | <strong>Sì</strong> |
| Websense - rapporto dettagli indagine (con estensione CSV) | <strong>Sì</strong> | <strong>Sì</strong> | <strong>Sì</strong> | <strong>Sì</strong> | <strong>Sì</strong> | <strong>Sì</strong> |
|    Websense - registro attività Internet (il formato CEF)    | <strong>Sì</strong> | <strong>Sì</strong> | <strong>Sì</strong> | <strong>Sì</strong> | <strong>Sì</strong> | <strong>Sì</strong> |
|                   Zscaler                    | <strong>Sì</strong> | <strong>Sì</strong> | <strong>Sì</strong> | <strong>Sì</strong> | <strong>Sì</strong> | <strong>Sì</strong> |
   
## <a name="supported-vendor-firewalls-and-proxies"></a>Fornitore supportati firewall e proxy

Protezione di Office 365 Cloud App supporta i proxy e i firewall seguenti.
  
- Barracuda - Firewall di applicazioni Web (W3C)  
- Blu coprire Proxy dei gruppi di archiviazione - log di Access (W3C)
- Punto di controllo
- Cisco ASA Firewall (verificare impostare il livello di informazioni su 6)
- Cisco ASA con FirePOWER   
- Cisco IronPort WSA
- Cisco ScanSafe
- Eseguire l'accesso Cisco Merkai - URL
- Clavister NGFW (Registro di sistema)
- I filtri arte digitale
- Fortinet Fortigate
- iboss Secure Cloud Gateway
- Juniper SRX
- Juniper SSG
- Gateway Web sicuro McAfee
- Microsoft Forefront Threat Management Gateway (W3C)
- Serie Palo Alto Firewall
- SonicWALL (precedentemente Dell)   
- Sophos dei gruppi di archiviazione
- Sophos XG
- Sophos Cyberoam
- Calamaro (comune)
- Calamaro (nativa)
- Rapporto dettagli indagine Websense - soluzioni di protezione Web - (con estensione CSV)
- Registro attività tramite Internet Websense - soluzioni di protezione Web - (il formato CEF)
- Zscaler
    
> [!NOTE]
> Se non è inclusa un'origine dati che si desidera utilizzare, è possibile richiedere che aggiunto al individuazione app. A tale scopo, durante la creazione di un report, selezionare **altre** per **origine dati**. Quindi digitare il nome dell'origine dati che si sta tentando di caricare. Si verrà esaminare il registro e consentono di verificare se viene aggiunto il supporto per quel tipo di registro. In alternativa, è possibile [definire un parser personalizzato](https://docs.microsoft.com/cloud-app-security/custom-log-parser) che genera una corrispondenza per il formato. 
  
## <a name="troubleshoot-errors-when-log-files-are-uploaded"></a>Risoluzione degli errori di caricamento di file di registro

Dopo aver caricato i file di registro del traffico web, controllare il Registro di governance per verificare se si sono verificati errori di. Se sono presenti errori, utilizzare le informazioni nella tabella seguente per risolvere questi errori.
  
|**Errore**|**Descrizione**|**Soluzione**|
|:-----|:-----|:-----|
|Tipo di file non supportati  <br/> |I file caricato non è un file di registro validi. Ad esempio, un file di immagine.  <br/> |Caricare un testo, zip o file gzip che sono stati esportati direttamente da al firewall o proxy.  <br/> |
|Errore interno  <br/> |È stato rilevato un errore di risorse interno.  <br/> |Fare clic su **Riprova** per eseguire nuovamente l'attività.  <br/> |
|Il formato del registro non corrisponde a  <br/> |Il formato del registro che è stata caricata corrisponde al formato di registro previsti per l'origine dati.  <br/> |
Verificare che il registro non sia danneggiato. Confronta e corrisponde al formato di file di registro per il formato di esempio mostrato nella pagina per il caricamento. |
|Le transazioni sono più di 90 giorni  <br/> |Tutte le transazioni più di 90 giorni e pertanto vengono ignorati.  <br/> |Esportazione di un nuovo registro quando si verificano eventi recenti e caricare nuovamente.  <br/> |
|Nessuna transazione da applicazioni basate su cloud catalogo  <br/> |Delle transazioni per le applicazioni basate su cloud riconosciuto si trovano nel registro.  <br/> |Verificare che il registro contiene informazioni sul traffico in uscita.  <br/> |
|Tipo di registro non supportati  <br/> |Quando si seleziona **origine dati = altri (non supportate)**, il registro non viene analizzato. In realtà, questo verrà inviato per la revisione al team di documentazione tecnica di [Microsoft Cloud App Security](https://aka.ms/whatiscas) .<br/> |Il team di documentazione tecnico di [Microsoft Cloud App protezione](https://aka.ms/whatiscas) si basa un parser dedicato per ogni origine dati. Origini dati più popolari già sono supportate. Quando viene caricata un'origine dati non supportate, che viene esaminato e aggiunto all'elenco dei possibili nuovi parser di origine dati.<br/> Quando viene aggiunto un nuovo parser per la funzionalità, una notifica è incluso nelle note sulla versione di Microsoft Cloud App Security.  <br/> |
   
## <a name="next-steps"></a>Passaggi successivi

- [Leggere ed eseguire l'azione gli avvisi](review-office-365-cas-alerts.md)
    
- [Creare i rapporti di individuazione applicazioni](create-app-discovery-reports-in-ocas.md)
    
- [Esaminare i risultati di individuazione applicazioni](review-app-discovery-findings-in-ocas.md)
    
- [Esaminare le attività di utilizzo per la protezione di Office 365 Cloud App](utilization-activities-for-ocas.md)
    

