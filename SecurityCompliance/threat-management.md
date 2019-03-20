---
title: Threat management in the Office 365 Security &amp; Compliance Center
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.date: 9/24/2018
ms.audience: Admin
ms.topic: hub-page
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 0a73d5fa-b2c8-43e7-9ed4-61f0552b1c98
ms.collection:
- M365-security-compliance
description: Utilizzare la gestione delle minacce per controllare e gestire l'accesso dei dispositivi mobili ai dati dell'organizzazione, proteggere l'organizzazione dalla perdita di dati e proteggere i messaggi in ingresso e in uscita da software dannoso e dalla posta indesiderata. È inoltre possibile utilizzare la gestione delle minacce per proteggere la reputazione del dominio e determinare se i mittenti o meno eseguono lo spoofing doloso degli account provenienti dal dominio.
ms.openlocfilehash: 9c6c39b7edc008c4a44146fac8076897e705b5f5
ms.sourcegitcommit: 0f93b37c39d807dec91f118aa671a3430c47a9ac
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/20/2019
ms.locfileid: "30693175"
---
# <a name="threat-management-in-the-office-365-security-amp-compliance-center"></a>Threat management in the Office 365 Security &amp; Compliance Center

Utilizzare la gestione delle minacce per controllare e gestire l'accesso dei dispositivi mobili ai dati dell'organizzazione, proteggere l'organizzazione dalla perdita di dati e proteggere i messaggi in ingresso e in uscita da software dannoso e dalla posta indesiderata. È inoltre possibile utilizzare la gestione delle minacce per proteggere la reputazione del dominio e determinare se i mittenti o meno eseguono lo spoofing doloso degli account provenienti dal dominio.
  
## <a name="how-to-view-and-use-threat-management-in-the-security-amp-compliance-center"></a>Informazioni su come visualizzare e utilizzare la gestione delle minacce &amp; nel centro sicurezza e conformità

In Office 365 utilizzare il Centro sicurezza &amp; e conformità per gestire le minacce nell'organizzazione.
  
 **Per accedere direttamente al centro sicurezza &amp; e conformità:**
  
1. Passare a [https://protection.office.com](https://protection.office.com).

2. Accedere a Office 365 usando l'account aziendale o dell'istituto di istruzione.

3. Nel riquadro sinistro selezionare **gestione minacce**.

    ![Menu di gestione &amp; delle minacce per il Centro sicurezza e conformità di Office 365](media/dca29ff2-ad6d-4c27-becb-b5947268d55a.png)
  
 **Per accedere al centro sicurezza &amp; e conformità utilizzando l'icona di avvio delle app di Office 365:**
  
1. Accedere a Office 365 usando l'account aziendale o dell'istituto di istruzione.

2. Seleziona l'icona di avvio delle app in Office 365](media/7502f4ec-3c9a-435d-a7b4-b9cda85189a7.png) nell'angolo in alto a sinistra e quindi seleziona il riquadro **conformità &amp; di sicurezza.** ![ 

3. Nel riquadro sinistro selezionare **gestione minacce**.

## <a name="about-threat-management-in-office-365"></a>Informazioni sulla gestione delle minacce in Office 365

Queste opzioni sono disponibili in **gestione minacce** nel centro sicurezza &amp; e conformità.
  
È ancora in esecuzione la gestione delle minacce per il &amp; Centro sicurezza e conformità, quindi è possibile che non vengano visualizzate tutte queste informazioni oppure che potrebbero essere visualizzate altre opzioni elencate qui. Durante l'implementazione, alcuni di questi, ad esempio anti-malware, DKIM e altri, continueranno a essere disponibili tramite l'interfaccia di amministrazione di Exchange (EAC) per un periodo di tempo limitato.

In alcuni casi, sono presenti differenze minime tra l'interfaccia di amministrazione &amp; di Exchange e le implementazioni del centro conformità di sicurezza. Ad esempio, i caratteri supportati per i filtri per la posta indesiderata sono diversi tra le due piattaforme. Gli articoli sono forniti che forniscono ulteriori informazioni sulle differenze specifiche quando si verificano.
  
|**Strumento**|**Descrizione**|
|:-----|:-----|
|**Dashboard, Esplora minacce e operazioni non consentite** <br/> |Dopo aver abilitato, questi riquadri consentono di gestire Office 365 Analytics e le indagini e le risposte alle minacce. Per ulteriori informazioni, vedere [Office 365 Advanced Threat Protection Plan 2](office-365-ti.md).  <br/> |
|**Filtro posta** <br/> |Ottimizzare e monitorare le impostazioni che consentono di impedire la posta indesiderata in Office 365. Creare gli elenchi Consenti e blocca, determinare gli utenti che eseguono lo spoofing del dominio e perché, nonché configurare e visualizzare i criteri di filtro della posta indesiderata. Per ulteriori informazioni, vedere [Office 365 posta elettronica protezione](anti-spam-protection.md)dalla posta indesiderata.  <br/> È inoltre possibile configurare un criterio per verificare che gli utenti non inviino posta indesiderata. Ciò può verificarsi, ad esempio, se il computer di un utente viene infettato da malware programmato per l'invio di messaggi di posta elettronica. Per informazioni su come prevenire la posta indesiderata in uscita, vedere [Configure the outbound Spam Policy](https://technet.microsoft.com/library/jj200737%28v=exchg.150%29.aspx).  <br/> Se si verifica un problema con la posta indesiderata, è possibile utilizzare lo strumento di [risoluzione dei problemi di posta indesiderata e malware](https://configure.office.com/Scenario.aspx?sid=73).           |
|**Antimalware** <br/> |Protegge da virus e spyware che viaggiano da o verso la propria organizzazione in Office 365. I virus sono programmi software dannosi che, quando eseguiti, vengono replicati e modificati da altri programmi e dati nel computer. Virus distribuiti in tutto il computer in cui sono in cerca di programmi da infettare e condivisi anche da un computer a un altro, spesso tramite posta elettronica. Lo spyware raccoglie le informazioni personali, ad esempio le informazioni di accesso, e le invia nuovamente all'autore. Per iniziare a configurare i criteri anti-malware, vedere [Configure anti-malware Policies](https://technet.microsoft.com/library/jj200745%28v=exchg.150%29.aspx).  <br/> Se si verifica un problema con malware, è possibile utilizzare lo strumento di [risoluzione dei problemi relativi a posta indesiderata e malware](https://configure.office.com/Scenario.aspx?sid=73).           |
|**DKIM** <br/> |Progettato per gli amministratori di Office 365 più avanzati, ma disponibile per tutti i clienti di Office 365, la posta identificata di DomainKeys (DKIM) consente di garantire che altri sistemi di posta elettronica possano considerare attendibili i messaggi inviati da Office 365. In DKIM viene aggiunta una firma digitale univoca ai messaggi di posta elettronica inviati dall'organizzazione. I sistemi di posta elettronica che ricevono la posta elettronica da è possibile utilizzare questa firma digitale per determinare se il messaggio di posta elettronica è legittimo.  <br/> Non si preoccupi se i dettagli del funzionamento sembrano complicati, perché l'impostazione predefinita configurata per l'utente in Office 365 dovrebbe funzionare per la maggior parte delle organizzazioni. [! Nota] se non si configura DKIM personalmente, Office 365 utilizzerà i criteri predefiniti e i tasti creati per abilitare DKIM per il dominio. Inoltre, se si disattiva la firma DKIM, dopo un determinato periodo di tempo, Office 365 attiva automaticamente il criterio predefinito di Office 365 per il dominio.  <br/> Se si desidera, è possibile visualizzare questa pagina nel centro conformità &amp; sicurezza e verificare se le firme di DKIM sono attualmente abilitate per il dominio ed è possibile visualizzare l'ultima volta che le chiavi di crittografia utilizzate da Office 365 sono state ruotate. È anche possibile ruotare manualmente i tasti.  <br/> **IMPORTANTE!** DKIM è una sola tecnica di autenticazione della posta elettronica utilizzata da Office 365. Per essere più efficienti, DKIM viene utilizzato insieme ad altre tecniche supportate, come il Sender Policy Framework (SPF) e l'autenticazione dei messaggi basata sul dominio, la creazione di report e la conformità (DMARC). Insieme, queste tecnologie di autenticazione basata sul dominio consentono di prevenire la posta indesiderata e lo spoofing.<br/>  Prima di apportare modifiche a DKIM utilizzando il &amp; Centro sicurezza e conformità, è possibile familiarizzare con la tecnologia e come funziona. Per iniziare, vedere [oltre le nozioni di base: altri modi per impedire la posta indesiderata in Office 365](anti-spam-protection.md#beyond-the-basics-more-ways-to-prevent-spam-in-office-365).           |
|**Allegati sicuri**<br/>|Gli [allegati sicuri](atp-safe-attachments.md) fanno parte di Advanced Threat Protection. Se abilitato, gli allegati di posta elettronica vengono aperti in un ambiente isolato speciale separato da Office 365 prima di essere inviati alle cassette postali dei destinatari. Gli allegati sicuri sono stati creati per facilitare il rilevamento degli allegati dannosi anche prima che siano disponibili firme antivirus. Per ulteriori informazioni, vedere [allegati sicuri in Office 365](atp-safe-attachments.md).<br/> |
|**Collegamenti sicuri** <br/> |I [collegamenti sicuri](atp-safe-links.md) fanno parte di Advanced Threat Protection. I collegamenti sicuri impediscono agli utenti di seguire gli URL nei messaggi di posta elettronica o nei documenti di Office che puntano a siti Web che sono riconosciuti come dannosi. Per ulteriori informazioni, vedere [collegamenti sicuri in Office 365](atp-safe-links.md).<br/> |
|**Quarantena**<br/>|Configurare la [quarantena](http://go.microsoft.com/fwlink/p/?LinkID=809005) per i messaggi di posta elettronica in arrivo in Office 365 in cui i messaggi che sono stati filtrati come posta indesiderata, in blocco, phishing e malware possono essere conservati per la revisione successiva. Sia gli utenti che gli amministratori possono utilizzare i messaggi in quarantena. Gli utenti possono utilizzare solo i propri messaggi filtrati in quarantena. Gli amministratori possono cercare e gestire i messaggi in quarantena per tutti gli utenti.  <br/> |
|**Minacce avanzate** <br/> |Visualizzare il [rapporto sullo stato di protezione dalle minacce](https://support.office.com/article/View-the-reports-for-Advanced-Threat-Protection-E47E838C-D99E-4C0B-B9AA-E66C4FAE902F#advancedthreats) per visualizzare le informazioni relative al contenuto dannoso trovato e bloccato da Exchange Online Protection e Advanced Threat Protection.  <br/> |
