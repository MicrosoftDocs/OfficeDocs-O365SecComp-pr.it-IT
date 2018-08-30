---
title: Il log del traffico web e origini dati per Office 365 Cloud App Security
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 2/26/2018
ms.audience: ITPro
ms.topic: reference
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 290b02bf-a988-4fb9-88b2-34e408216ac8
description: Office 365 Cloud App sicurezza utilizza i registri di traffico web da una vasta gamma di provider. Leggere questo articolo per ulteriori informazioni su registri di traffico web e le origini dati è supportata per la protezione di Office 365 Cloud App.
ms.openlocfilehash: 09b0358e0d8b9a6ed59393d8771237f7eaf8bb98
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/27/2018
ms.locfileid: "22530895"
---
# <a name="web-traffic-logs-and-data-sources-for-office-365-cloud-app-security"></a>Il log del traffico web e origini dati per Office 365 Cloud App Security
  
|Valutazione * *\>**|Pianificazione * *\>**|Distribuzione * *\>**|Utilizzo * * *|
|:-----|:-----|:-----|:-----|
|[Avviare la valutazione](office-365-cas-overview.md) <br/> |[Iniziare a pianificare](get-ready-for-office-365-cas.md) <br/> |[Avviare la distribuzione](turn-on-office-365-cas.md) <br/> |Si è seguito!  <br/> [Passaggi successivi](#next-steps) <br/> |
  
È possibile utilizzare una vasta gamma di origini dati e i file di registro del traffico web con Office 365 Cloud App protezione. Tuttavia, i file di registro del traffico web devono includere informazioni specifiche ed essere formattati in modo particolare in modo che possano funzionare con Office 365 Cloud App sicurezza app individuazione rapporti e dashboard individuazione Cloud. Utilizzare questo articolo come guida di riferimento per le origini dati da utilizzare con Office 365 Cloud App protezione e il log del traffico web.
  
> [!NOTE]
> È necessario essere un amministratore globale, l'amministratore della sicurezza o lettore di protezione per la protezione dall'accesso di &amp; portal centro conformità e sicurezza App Cloud di Office 365. Vedere [le autorizzazioni di sicurezza di Office 365 &amp; centro conformità](permissions-in-the-security-and-compliance-center.md). 
  
## <a name="web-traffic-log-requirements"></a>Requisiti di registro del traffico Web

Utilizzano Office 365 Cloud App sicurezza utilizzi dati nei file registro il traffico web utili per comprendere quali App utenti nell'organizzazione. Ulteriori informazioni incluse nei file di registro, il miglioramento della visibilità, è necessario attività dell'utente.
  
Nella tabella seguente sono elencati i requisiti e gli attributi necessari per i registri di traffico web funzioni correttamente con Office 365 Cloud App protezione:
  
|**Attributi**|**Requisiti aggiuntivi **|
|:-----|:-----|
| Data della transazione  <br/>  IP origine  <br/>  Utente di origine (scelta consigliata)  <br/>  Indirizzo IP di destinazione  <br/>  URL di destinazione (scelta consigliata: URL offrono maggiore precisione per il rilevamento delle app cloud di indirizzi IP)  <br/>  Quantità totale di dati (scelta consigliati)  <br/>  Tempo di caricamento o il download dei dati (scelta consigliata: vengono fornite informazioni su cloud modelli di utilizzo app)  <br/>  Azione eseguita (consentite o bloccate)  <br/> | L'origine dati per i file di registro deve essere supportata.  <br/>  Il formato di che utilizzano i file di registro deve corrispondere al formato standard. Quando viene caricato il file, l'individuazione app verifica seguente.  <br/>  Gli eventi nel registro necessario hanno avuto luogo non più di 90 giorni.  <br/>  Il file di registro deve includere informazioni sul traffico in uscita che può essere analizzate per attività di rete.  <br/> |
   
Se gli attributi non sono disponibili nei registri che vengono caricati, sicurezza App Cloud di Office 365 non possono visualizzare o analizzare le informazioni per l'utente. Formato del Registro standard del Firewall ASA Cisco, ad esempio, non include la quantità di byte caricati per transazioni, il nome utente o un URL di destinazione (solo un indirizzo IP destinazione). Poiché quest'ultimo non nei file di registro Cisco, sicurezza App Cloud di Office 365 non includerlo durante l'analisi del traffico di rete dell'organizzazione.
  
> [!NOTE]
> Per alcuni tipi di firewall, è necessario impostare un livello di informazioni per i registri di traffico web da includere gli attributi obbligatori. Ad esempio, Cisco ASA firewall è necessario impostare il livello di informazioni su 6. Verificare che verificare che i firewall siano impostati per fornire le informazioni corrette nei registri traffico web. 
  
## <a name="data-attributes-for-different-vendors"></a>Attributi di dati per i fornitori diversi
<a name="BKMK_LogAndData"> </a>

Nella tabella seguente sono riepilogate le informazioni nel log di traffico web da vari fornitori. **è necessario contattare il fornitore per le informazioni più aggiornate.**
  
|**Origine dati**|**URL di app di destinazione**|**IP app di destinazione**|**Username**|**Origine IP**|**Totale del traffico**|**Byte caricati**|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|Barracuda  <br/> |**Sì** <br/> |**Sì** <br/> |**Sì** <br/> |**Sì** <br/> |No  <br/> |No  <br/> |
|Coprire blu  <br/> |**Sì** <br/> |No  <br/> |**Sì** <br/> |**Sì** <br/> |**Sì** <br/> |**Sì** <br/> |
|Punto di controllo  <br/> |No  <br/> |**Sì** <br/> |No  <br/> |**Sì** <br/> |No  <br/> |No  <br/> |
|Cisco ASA  <br/> |No  <br/> |**Sì** <br/> |No  <br/> |**Sì** <br/> |**Sì** <br/> |No  <br/> |
|Cisco FWSM  <br/> |No  <br/> |**Sì** <br/> |No  <br/> |**Sì** <br/> |**Sì** <br/> |No  <br/> |
|Cisco Ironport WSA  <br/> |**Sì** <br/> |**Sì** <br/> |**Sì** <br/> |**Sì** <br/> |**Sì** <br/> |**Sì** <br/> |
|Cisco Meraki  <br/> |**Sì** <br/> |**Sì** <br/> |No  <br/> |**Sì** <br/> |No  <br/> |No  <br/> |
|Clavister NGFW (Registro di sistema)  <br/> |**Sì** <br/> |**Sì** <br/> |**Sì** <br/> |**Sì** <br/> |**Sì** <br/> |**Sì** <br/> |
|SonicWall Dell  <br/> |**Sì** <br/> |**Sì** <br/> |No  <br/> |**Sì** <br/> |**Sì** <br/> |**Sì** <br/> |
|FortiGate  <br/> |No  <br/> |**Sì** <br/> |No  <br/> |**Sì** <br/> |**Sì** <br/> |**Sì** <br/> |
|Juniper SRX  <br/> |No  <br/> |**Sì** <br/> |No  <br/> |**Sì** <br/> |**Sì** <br/> |**Sì** <br/> |
|Juniper SSG  <br/> |No  <br/> |**Sì** <br/> |No  <br/> |**Sì** <br/> |**Sì** <br/> |**Sì** <br/> |
|McAfee SWG  <br/> |**Sì** <br/> |No  <br/> |No  <br/> |**Sì** <br/> |**Sì** <br/> |**Sì** <br/> |
|Meraki (Cisco)  <br/> |**Sì** <br/> |**Sì** <br/> |No  <br/> |**Sì** <br/> |No  <br/> |No  <br/> |
|Microsoft Threat Management Gateway  <br/> |**Sì** <br/> |No  <br/> |**Sì** <br/> |**Sì** <br/> |**Sì** <br/> |**Sì** <br/> |
|Reti Palo Alto  <br/> |**Sì** <br/> |**Sì** <br/> |**Sì** <br/> |**Sì** <br/> |**Sì** <br/> |**Sì** <br/> |
|Sophos  <br/> |**Sì** <br/> |**Sì** <br/> |**Sì** <br/> |**Sì** <br/> |**Sì** <br/> |No  <br/> |
|Calamaro (comune)  <br/> |**Sì** <br/> |No  <br/> |**Sì** <br/> |**Sì** <br/> |No  <br/> |**Sì** <br/> |
|Calamaro (nativa)  <br/> |**Sì** <br/> |No  <br/> |**Sì** <br/> |**Sì** <br/> |No  <br/> |**Sì** <br/> |
|Websense - rapporto dettagli indagine (con estensione CSV)  <br/> |**Sì** <br/> |**Sì** <br/> |**Sì** <br/> |**Sì** <br/> |**Sì** <br/> |**Sì** <br/> |
|Websense - registro attività Internet (il formato CEF)  <br/> |**Sì** <br/> |**Sì** <br/> |**Sì** <br/> |**Sì** <br/> |**Sì** <br/> |**Sì** <br/> |
|Zscaler  <br/> |**Sì** <br/> |**Sì** <br/> |**Sì** <br/> |**Sì** <br/> |**Sì** <br/> |**Sì** <br/> |
   
## <a name="supported-vendor-firewalls-and-proxies"></a>Fornitore supportati firewall e proxy
<a name="BKMK_Supported"> </a>

Protezione di Office 365 Cloud App supporta i proxy e i firewall seguenti.
  
- Barracuda - Firewall di applicazioni Web (W3C)
    
- Blu coprire Proxy dei gruppi di archiviazione - log di Access (W3C)
    
- Punto di controllo
    
- Cisco ASA Firewall (si noti che è necessario impostare il livello di informazioni su 6)
    
- Cisco IronPort WSA
    
- Cisco ScanSafe
    
- Eseguire l'accesso Cisco Merkai - URL
    
- Sonicwall Dell
    
- Fortinet Fortigate
    
- Juniper SRX
    
- Juniper SSG
    
- Gateway Web sicuro McAfee
    
- Microsoft Forefront Threat Management Gateway (W3C)
    
- Serie Palo Alto Firewall
    
- Sophos dei gruppi di archiviazione
    
- Sophos Cyberoam
    
- Calamaro (comune)
    
- Calamaro (nativa)
    
- Rapporto dettagli indagine Websense - soluzioni di protezione Web - (con estensione CSV)
    
- Registro attività tramite Internet Websense - soluzioni di protezione Web - (il formato CEF)
    
- Zscaler
    
> [!NOTE]
> Se non è inclusa un'origine dati che si desidera utilizzare, è possibile richiedere che aggiunto al individuazione app. A tale scopo, durante la creazione di un report, selezionare **altre** per **origine dati**. Quindi digitare il nome dell'origine dati che si sta tentando di caricare. Si verrà esaminare il registro e consentono di verificare se viene aggiunto il supporto per quel tipo di registro. 
  
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
    

