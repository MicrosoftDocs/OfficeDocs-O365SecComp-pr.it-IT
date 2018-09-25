---
title: Gestione di Office 365 protezione delle minacce &amp; centro conformità
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 9/24/2018
ms.audience: Admin
ms.topic: hub-page
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 0a73d5fa-b2c8-43e7-9ed4-61f0552b1c98
description: Utilizzare Threat management consentono di controllare e gestire l'accesso dei dispositivi mobili per i dati dell'organizzazione, proteggere l'organizzazione da perdita di dati e migliorare la protezione dei messaggi in ingresso e in uscita da posta indesiderata e malware. È inoltre possibile utilizzare threat management per la protezione di reputazione del dominio e per determinare se i mittenti sono da utenti malintenzionati lo spoofing degli account di dominio.
ms.openlocfilehash: 88b2727b76fad1e8d700f15717a8aeedea934093
ms.sourcegitcommit: c168410974bc90aaf55f1dcaa9e05c09b2b78d76
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/25/2018
ms.locfileid: "25011832"
---
# <a name="threat-management-in-the-office-365-security-amp-compliance-center"></a>Gestione di Office 365 protezione delle minacce &amp; centro conformità

Utilizzare Threat management consentono di controllare e gestire l'accesso dei dispositivi mobili per i dati dell'organizzazione, proteggere l'organizzazione da perdita di dati e migliorare la protezione dei messaggi in ingresso e in uscita da posta indesiderata e malware. È inoltre possibile utilizzare threat management per la protezione di reputazione del dominio e per determinare se i mittenti sono da utenti malintenzionati lo spoofing degli account di dominio.
  
## <a name="how-to-view-and-use-threat-management-in-the-security-amp-compliance-center"></a>Come visualizzare e utilizzare Gestione delle minacce per la protezione &amp; centro conformità

In Office 365, utilizzare la protezione &amp; centro conformità per la gestione delle minacce all'interno dell'organizzazione.
  
 **Per passare direttamente alla protezione &amp; centro conformità:**
  
1. Passare a [https://protection.office.com](https://protection.office.com).
    
2. Accedere a Office 365 utilizzando l'account di lavoro o della scuola.
    
3. Nel riquadro sinistro, selezionare **gestione rischio**.
    
    ![Protezione di Office 365 &amp; menu Gestione rischio centro conformità](media/dca29ff2-ad6d-4c27-becb-b5947268d55a.png)
  
 **Per passare alla protezione &amp; centro conformità con il servizio di avvio di applicazioni di Office 365:**
  
1. Accedere a Office 365 utilizzando l'account di lavoro o della scuola.
    
2. Selezionare il servizio di avvio di app ![l'icona di avvio di app in Office 365](media/7502f4ec-3c9a-435d-a7b4-b9cda85189a7.png) nell'angolo in alto a sinistra angolo e quindi selezionare il **protezione &amp; conformità** affiancate. 
    
3. Nel riquadro sinistro, selezionare **gestione rischio**.
    
## <a name="about-threat-management-in-office-365"></a>Informazioni sulla gestione delle minacce in Office 365

Queste opzioni sono disponibili nella sezione **gestione delle minacce** per la protezione &amp; centro conformità. 
  
Gestione delle minacce per la sicurezza è stiamo ancora distribuzione &amp; centro conformità, in modo che non appare tutti questi ancora o potrebbe essere presente più le opzioni elencate di seguito. Durante la distribuzione, alcuni di questi elementi, ad esempio Anti-malware, Dkim e altri utenti, continuerà a essere disponibile tramite interfaccia di amministrazione di Exchange (EAC) per un periodo limitato.

In alcuni casi, non esistono differenze tra l'interfaccia di amministrazione di Exchange e la sicurezza &amp; implementazioni centro conformità. Ad esempio caratteri supportati per i filtri posta indesiderata sono diversi tra le due piattaforme. Articoli vengono forniti che includono ulteriori informazioni sulle differenze specifiche quando si verificano. 
  
|**Strumento**|**Descrizione**|
|:-----|:-----|
|**Dashboard, explorer rischio e risolte** <br/> |Una volta abilitata, questi riquadri consentono di gestire Office 365 Analitica e rischio intelligence. Per ulteriori informazioni, vedere [Panoramica di Business Intelligence di Office 365 rischio](office-365-ti.md).<br/> |
|**Filtro della posta** <br/> |Ottimizzare e monitorare le impostazioni che consentono di evitare la posta indesiderata in Office 365. Creare Consenti e blocca elenchi, determinare chi è lo spoofing del dominio e il motivo, configurare e visualizzare i criteri di filtro da posta indesiderata. Per ulteriori informazioni, vedere [protezione anti-spam della posta elettronica Office 365](anti-spam-protection.md).<br/> È anche possibile impostare backup di un criterio per verificare che gli utenti non sono l'invio di posta indesiderata. Può accadere, ad esempio, se il computer dell'utente ottiene infetti da malware è programmata per inviare messaggi di posta elettronica. Per informazioni su come è possibile impedire posta indesiderata in uscita, vedere [configurare il criterio della posta indesiderata in uscita](https://technet.microsoft.com/library/jj200737%28v=exchg.150%29.aspx).<br/> Se attualmente si verifica un problema con la posta indesiderata, è possibile utilizzare la [risoluzione dei problemi della posta indesiderata e malware](https://configure.office.com/Scenario.aspx?sid=73).           |
|**Antimalware** <br/> |Protegge da virus e spyware da o verso l'organizzazione in Office 365. I virus sono dannosi programmi software che, quando viene eseguito, replicarsi e modificare altri programmi e i dati nel computer. Virus distribuiti in tutto il computer per programmi infetti e vengono condivisi da un computer a un altro, spesso tramite posta elettronica. Spyware raccoglie informazioni personali, ad esempio informazioni di accesso e lo invia al relativo autore. Per iniziare a configurare criteri anti-malware, vedere [Configure anti-malware policies](https://technet.microsoft.com/library/jj200745%28v=exchg.150%29.aspx).<br/> Se attualmente si verifica un problema con malware, è possibile utilizzare la [risoluzione dei problemi della posta indesiderata e malware](https://configure.office.com/Scenario.aspx?sid=73).           |
|**DKIM** <br/> |Progettato per più avanzate agli amministratori di Office 365, ma è disponibile a tutti i clienti di Office 365, DomainKeys identificato posta (DKIM) consente di assicurare che altri sistemi di posta elettronica trust i messaggi inviati da Office 365. A tale scopo, DKIM aggiungere una firma digitale univoca per i messaggi di posta elettronica inviati dall'organizzazione. Sistemi di posta elettronica ricevano della posta elettronica da è possono utilizzare la firma digitale per informazioni su come determinare se il messaggio di posta elettronica legittimo.<br/> È possibile che i dettagli del funzionamento sembrano complessi, poiché il valore predefinito in cui è installato automaticamente in Office 365 deve utilizzare per la maggior parte delle organizzazioni. Se non è impostata DKIM familiarità, Office 365 utilizza il criterio predefinito e tasti che viene creato per poter abilitare DKIM per il dominio. Inoltre, se si disabilita accesso DKIM, dopo un periodo di tempo, Office 365 attiva automaticamente il criterio predefinito di Office 365 per il dominio.<br/> Se si desidera, è possibile visualizzare questa pagina per la protezione &amp; centro conformità e vedere o meno le firme DKIM attualmente abilitate per il dominio e si possono visualizzare l'ultima volta sono state ruotate le chiavi di crittografia utilizzate da Office 365. Si possono inoltre ruotare manualmente i tasti familiarità.<br/> **Importante!** DKIM è solo un messaggio di posta elettronica autenticazione tecnica utilizzata da Office 365. Per raggiungere i migliori risultati DKIM viene utilizzato insieme altre tecniche supportati come mittente Policy Framework (SPF) e Domain-based Message Authentication, report e conformità (DMARC). Insieme, queste tecnologie di autenticazione basata su dominio per evitare la posta indesiderata e lo spoofing indesiderati.<br/>  Prima di apportare modifiche a DKIM utilizzando la sicurezza &amp; centro conformità, familiarità con la tecnologia e del relativo funzionamento. Per iniziare, vedere [oltre a informazioni di base: ulteriori modi per evitare la posta indesiderata in Office 365](anti-spam-protection.md#BeyondBasics).           |
|**Allegati sicuri** <br/> |[Gli allegati sicuri](atp-safe-attachments.md) fa parte di protezione avanzata di rischio. Se abilitato, gli allegati di posta elettronica vengono aperti in un ambiente isolato speciale che è separato da Office 365 prima che vengano inviati a destinatari posta in arrivo. Gli allegati sicuri è progettato per il rilevamento presenza di allegati anche prima antivirus firme sono disponibili. Per ulteriori informazioni, vedere [Allegati attendibili in Office 365](atp-safe-attachments.md).<br/> |
|**Collegamenti sicuri** <br/> |[Collegamenti sicura](atp-safe-links.md) fa parte di protezione avanzata di rischio. Collegamenti sicuri utili per impedire agli utenti di URL seguenti nel messaggio di posta elettronica o nei documenti di Office che puntano a siti web in cui vengono riconosciuti come dannose. Per ulteriori informazioni, vedere [Collegamenti attendibili in Office 365](atp-safe-links.md).<br/> |
|**Quarantena** <br/> |Configurazione di [quarantena](http://go.microsoft.com/fwlink/p/?LinkID=809005) per i messaggi di posta elettronica in arrivo in Office 365 dove in blocco, i messaggi che sono stati filtrati come posta indesiderata, phishing, e malware posta può essere mantenuta per un utilizzo successivo. Gli utenti e gli amministratori possono lavorare con i messaggi in quarantena. Gli utenti possono utilizzare solo i propri messaggi filtrati in quarantena. Gli amministratori possono cercare e gestire i messaggi in quarantena per tutti gli utenti.<br/> |
|**Minacce avanzate** <br/> |Visualizzare il [rapporto sullo stato di protezione rischio](https://support.office.com/article/View-the-reports-for-Advanced-Threat-Protection-E47E838C-D99E-4C0B-B9AA-E66C4FAE902F#advancedthreats) per visualizzare informazioni sul contenuto dannoso individuato e bloccati per Exchange Online Protection e protezione da minacce avanzate.  <br/> |
   

