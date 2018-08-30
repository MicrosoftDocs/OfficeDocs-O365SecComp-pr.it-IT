---
title: Procedure consigliate per la sicurezza per Office 365
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 5/22/2018
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MED150
- MBS150
- BCS160
- MET150
ms.assetid: 9295e396-e53d-49b9-ae9b-0b5828cdedc3
description: Ridurre al minimo la possibilità di una violazione dei dati o un account compromesso seguendo le procedure consigliate.
ms.openlocfilehash: 245302af0b08a4ee8183345fc386fe47985c93dd
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/27/2018
ms.locfileid: "22531362"
---
# <a name="security-best-practices-for-office-365"></a>Procedure consigliate per la sicurezza per Office 365

Ridurre al minimo la possibilità di una violazione dei dati o un account compromesso seguendo le procedure consigliate.
  
In questo articolo contiene un elenco rapido di procedure consigliate. Per ulteriori analisi approfondita e informazioni sull'impostazione di sicurezza, vedere [roadmap di protezione di Office 365: principali priorità per i primi 30 giorni, 90 giorni e oltre](security-roadmap.md). Nello stesso articolo sono disponibili informazioni basate su indagini di attacchi pratiche, dove gli esperti di alla sicurezza informatica principali di Microsoft Office 365 fornire ai venditori informazioni su come valutare i rischi e l'implementazione della protezione, la conformità e informazioni importanti controlli di protezione per proteggere il tenant di Office 365. Si verrà informazioni su come definire le priorità delle minacce, tradurre minacce strategiche tecniche e quindi un approccio sistematico all'implementazione della funzionalità e i controlli.
  
## <a name="use-office-365-secure-score"></a>Utilizzare punteggio protetta di Office 365

Punteggio sicura è uno strumento di analitica protezione consigliate da eseguire per ridurre ulteriormente il rischio da. Punteggio sicura legge le impostazioni di Office 365 e le attività e li confronta con una linea di base stabilita da Microsoft. Verrà visualizzato un punteggio basato sulla modalità allineato con le procedure consigliate di sicurezza. Per ulteriori informazioni su come ottenere punteggio sicura e utilizzarlo per aumentare la protezione dell'organizzazione Office 365, vedere [Introduzione il punteggio sicura di Office 365](office-365-secure-score.md).
  
Fonti di prova sicura punteggio
  
Utilizzo di un account di lavoro o della scuola che è stato assegnato il ruolo di Office 365 [ruoli di amministratore su Office 365](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) , [accedere a Office 365](https://www.office.com/signin).
  
Accesso protetto punteggio al [https://SecureScore.office.com](https://SecureScore.office.com).
  
## <a name="use-multi-factor-authentication-mfa"></a>Utilizzare l'autenticazione a più fattori (MFA)

MFA consente di aggiungere un ulteriore livello di protezione di una strategia di password complesse da richiedere agli utenti di confermare una telefonata, messaggio di testo o una notifica di app nel telefono smart dopo aver immesso correttamente le password. Con MFA sul posto, gli account utente di Office 365 sono ancora protetto da accessi non autorizzati anche se la password dell'utente viene compromesso. Gli account sono protette perché non accedere a un account solo dopo che sono stati soddisfatti difficoltà aggiuntive. Una password compromessa o rubata non è sufficiente.
  
- [Pianificare l'autenticazione a più fattori per le distribuzioni di Office 365](https://support.office.com/article/043807b2-21db-4d5c-b430-c8a6dee0e6ba)
    
- [Configurare l'autenticazione a più fattori per gli utenti di Office 365](https://support.office.com/article/8f0454b2-f51a-4d9c-bcde-2c48e41621c6)
    
## <a name="use-office-365-cloud-app-security"></a>Utilizzare la protezione di Office 365 Cloud App

Impostare i criteri in base alle esigenze dell'azienda per agire su di esso e tenere traccia di attività anomala. Impostare gli avvisi con Office 365 Cloud App protezione in modo che gli amministratori possono esaminare l'attività dell'utente non comune o rischioso, ad esempio il download di grandi quantità di dati, più non riuscito tentativi di accesso, gli accessi da un indirizzo IP sconosciuto o pericoloso. Per le organizzazioni con un piano di Office 365 Enterprise E5, iniziare a utilizzare Office 365 Cloud App protezione immediatamente. Se si dispone di un piano di organizzazione diversi, è possibile acquistare Office 365 Cloud App sicurezza come componente aggiuntivo.
  
- [Panoramica della protezione App Cloud di Office 365](office-365-cas-overview.md)
    
- [Attivare Office 365 Cloud App Security](turn-on-office-365-cas.md)
    
## <a name="secure-mail-flow"></a>Flusso di posta sicuro

Implementare il formato RTF in Exchange Online Protection set di caratteristiche e ottenere maggiori garanzie sull'identità del mittente di ogni messaggio di posta elettronica e protezione da malware sconosciuto, virus e URL dannosi trasmesse tramite messaggi di posta elettronica.
  
- Configurare i criteri di [Protezione di Office 365 posta indesiderata](anti-spam-protection.md) per l'organizzazione. 
    
- Per conoscere e quindi utilizzare [protezione rischio avanzata per gli allegati sicuri e collegamenti sicuri](https://technet.microsoft.com/library/mt148491.aspx).
    
- [Aggiungi protezione anti-malware nell'organizzazione](https://technet.microsoft.com/en-us/library/jj200669%28v=exchg.150%29.aspx).
    
- Per conoscere e abilitare [suggerimenti per la sicurezza nei messaggi di posta elettronica in Office 365](safety-tips-in-office-365.md) per gli utenti. 
    
- Se si utilizza un dominio personalizzato per l'organizzazione in Office 365, impostare SPF, DKIM e DMARC per convalidare la posta inviata dall'organizzazione e per impedire attacchi di spoofing:
    
  - [Impostare SPF in Office 365 per evitare attacchi di spoofing](https://technet.microsoft.com/en-us/library/dn789058%28v=exchg.150%29.aspx).
    
  - [Utilizzare DKIM per convalidare la posta elettronica inviata dal dominio personalizzato in Office 365](https://technet.microsoft.com/en-us/library/dn789058%28v=exchg.150%29.aspx).
    
  - [Utilizzare DMARC per convalidare la posta elettronica in Office 365](https://technet.microsoft.com/library/mt734386%28v=exchg.150%29.aspx).
    
## <a name="enable-mailbox-audit-logging"></a>Abilitare la registrazione di controllo della cassetta postale

Alcuni registrazione di controllo viene automaticamente abilitata per l'utente in Office 365; Tuttavia, la registrazione di controllo delle cassette postali non è attivata per impostazione predefinita. Attivare la registrazione di controllo per tutte le cassette postali utente in Office 365 tramite Exchange Online PowerShell. Per informazioni, vedere [abilitare il controllo in Office 365](https://go.microsoft.com/fwlink/p/?LinkID=626109).
  
Dopo avere abilitato per la registrazione di controllo può [nel Registro di controllo di ricerca in Office 365 Security &amp; centro conformità](search-the-audit-log-in-security-and-compliance.md) per scoprire chi ha effettuato l'accesso alle cassette postali utente, inviata messaggi e altre attività eseguita dal proprietario della cassetta postale, un utente delegato o da un amministratore. Per un elenco di attività di cassette postali inclusi in Office 365 Registro di controllo per impostazione predefinita, vedere [attività di cassette postali di Exchange](search-the-audit-log-in-security-and-compliance.md#exchange-mailbox-activities).
  
Per informazioni sulle altre azioni è possibile eseguire con il log di controllo, ad esempio modifica il periodo di tempo di salvataggio delle voci nel Registro di controllo, vedere [controllo delle cassette postali in Exchange 2016 la registrazione](https://technet.microsoft.com/en-us/library/ff459237%28v=exchg.160%29.aspx).
  
## <a name="configure-data-loss-prevention-dlp"></a>Configurare la prevenzione della perdita di dati (DLP)

DLP consente di identificare i dati riservati e creare i criteri che consentono di impedire agli utenti di intenzionalmente o accidentalmente i dati di condivisione. DLP può essere utilizzato in Office 365, inclusi Exchange Online, SharePoint Online e OneDrive in modo che gli utenti possono garantire la conformi senza interrompere il flusso di lavoro. Per ulteriori informazioni, vedere [Panoramica di criteri di prevenzione della perdita di dati](data-loss-prevention-policies.md).
  
## <a name="use-customer-lockbox"></a>Utilizzare archivio protetto cliente

Come un amministratore di Office 365, è possibile utilizzare archivio protetto cliente per controllare la modalità del supporto tecnico accede dei dati durante una sessione di supporto. In casi in cui il tecnico richiede l'accesso ai dati per risolvere un problema, archivio protetto cliente consente di approvare o rifiutare le richieste di accesso. Se lo si approva, il responsabile tecnico può accedere ai dati. Ogni richiesta è una data di scadenza e una volta che viene risolto, la richiesta viene chiusa e l'accesso è stato revocato. Analisi dell'archivio protetto è incluso nel piano di Office 365 Enterprise 5 oppure è possibile acquistare una sottoscrizione separata con qualsiasi altro piano di Office 365 enterprise. Per informazioni, vedere [Le richieste di archivio protetto clienti di Office 365](https://support.office.com/article/36f9cdd1-e64c-421b-a7e4-4a54d16440a2).
  
## <a name="try-it-yourself"></a>Prova personalmente
<a name="SecureScore"> </a>

Vedere le funzionalità di protezione che utilizzano una sottoscrizione di prova di Office 365 prima della loro adozione nell'ambiente di produzione.
  
- [Creazione di una sottoscrizione di prova di Office 365](https://technet.microsoft.com/library/mt736406.aspx)
    
- [Configurare e testare MFA per un account utente](https://technet.microsoft.com/library/mt492459.aspx)
    
- [Configurare e testare protezione di Office 365 Cloud App per ricevere una notifica delle attività di amministratore globale](https://technet.microsoft.com/library/mt757250.aspx)
    
- [Configurare e testare degli strumenti di analisi per la posta elettronica sospetto](https://technet.microsoft.com/library/mt490479.aspx)
    
- Verificare il [Punteggio di protezione di Office 365](https://securescore.office.com/) per la sottoscrizione di prova per ognuno dei passaggi precedenti 
    

