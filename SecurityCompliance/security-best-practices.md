---
title: Procedure consigliate per la sicurezza per Office 365
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.date: 5/22/2018
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MBS150
- BCS160
- MET150
ms.assetid: 9295e396-e53d-49b9-ae9b-0b5828cdedc3
ms.collection:
- M365-security-compliance
- Strat_O365_IP
description: Ridurre al minimo le potenzialità di una violazione dei dati o un account compromesso attenendosi alle procedure consigliate riportate di seguito.
ms.openlocfilehash: bd4b911cd5972b7d6dc9b55c17e375d326b1d571
ms.sourcegitcommit: 2c5834235c32b2616e1813ce24eeb3419a09629f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2019
ms.locfileid: "31026337"
---
# <a name="security-best-practices-for-office-365"></a>Procedure consigliate per la sicurezza per Office 365

Ridurre al minimo le potenzialità di una violazione dei dati o un account compromesso attenendosi alle procedure consigliate riportate di seguito.
  
In questo articolo è incluso un elenco rapido delle procedure consigliate. Per ulteriori informazioni e analisi su come configurare la sicurezza, vedere [Office 365 Security Roadmap: Top priorità per i primi 30 giorni, 90 giorni e oltre](security-roadmap.md). In questo articolo, sono disponibili informazioni basate sulle indagini sugli attacchi del mondo reale, in cui i nostri esperti di Microsoft Office 365 Cybersecurity forniscono un coaching su come valutare i rischi e implementare la sicurezza, la conformità e le informazioni più importanti controlli di protezione per proteggere il tenant di Office 365. Verrà illustrato come definire la priorità delle minacce, tradurre le minacce in una strategia tecnica e quindi adottare un approccio sistematico all'implementazione di funzionalità e controlli.
  
## <a name="use-office-365-secure-score"></a>Utilizzare Office 365 Secure Score

Secure Score è uno strumento di analisi della sicurezza che consiglia le operazioni che è possibile eseguire per ridurre ulteriormente i rischi. Secure Score analizza le impostazioni e le attività di Office 365 e le confronta con una linea di base stabilita da Microsoft. Si otterrà un punteggio in base al modo in cui si è allineati con le migliori procedure di sicurezza. Per ulteriori informazioni su come ottenere un punteggio sicuro e utilizzarlo per aumentare la sicurezza dell'organizzazione di Office 365, vedere [Introducing the office 365 Secure Score](office-365-secure-score.md).
  
Vuoi provare il Punteggio sicuro?
  
Se si utilizza un account aziendale o dell'Istituto di istruzione a cui è stato assegnato il ruolo Office 365 [sui ruoli di amministratore di office 365](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) , [accedere a Office 365](https://www.office.com/signin).
  
Accedere al Punteggio sicuro [https://SecureScore.office.com](https://SecureScore.office.com)su.
  
## <a name="use-multi-factor-authentication-mfa"></a>Utilizzo dell'autenticazione a più fattori (AMF)

L'AMF aggiunge un ulteriore livello di protezione a una strategia di password complessa richiedendo agli utenti di riconoscere una telefonata, un messaggio di testo o una notifica di app sul proprio smartphone dopo aver inserito correttamente la propria password. Con AMF sul posto, gli account utente di Office 365 sono ancora protetti da accessi non autorizzati anche se la password di un utente viene compromessa. Gli account sono protetti perché non viene concesso l'accesso a un account fino a quando non è stata soddisfatta la sfida aggiuntiva. Una password compromessa o rubata non è sufficiente.
  
- [Pianificare l'autenticazione a più fattori per le distribuzioni di Office 365](https://support.office.com/article/043807b2-21db-4d5c-b430-c8a6dee0e6ba)

- [Configurare l'autenticazione a più fattori per utenti di Office 365](https://support.office.com/article/8f0454b2-f51a-4d9c-bcde-2c48e41621c6)

## <a name="use-office-365-cloud-app-security"></a>Utilizzo di Office 365 cloud app Security

Impostare i criteri in base alle esigenze aziendali per monitorare le attività anomale e agire su di esso. Configurare gli avvisi con Office 365 cloud app Security in modo che gli amministratori possano esaminare attività utente inusuali o rischiose, ad esempio il download di grandi quantità di dati, più tentativi di accesso non riusciti o accessi da un indirizzo IP sconosciuto o pericoloso. Per le organizzazioni con un piano Office 365 Enterprise E5, è possibile iniziare a usare Office 365 cloud app Security subito. Se si dispone di un piano aziendale diverso, è possibile acquistare Office 365 cloud app Security come componente aggiuntivo.
  
- [Panoramica di O365 cloud app Security](office-365-cas-overview.md)

- [Attivazione di Office 365 cloud app Security](turn-on-office-365-cas.md)

## <a name="secure-mail-flow"></a>Protezione del flusso di posta

Implementare il set di funzionalità avanzate in Exchange Online Protection e ottenere maggiore sicurezza sull'identità del mittente di ogni messaggio di posta elettronica e proteggere da malware, virus e URL dannosi sconosciuti trasmessi tramite messaggi di posta elettronica.
  
- Configurare i criteri di protezione dalla posta inDesiderata di [Office 365](anti-spam-protection.md) per l'organizzazione.

- Informazioni sull'utilizzo di [Advanced Threat Protection per gli allegati sicuri e i collegamenti sicuri](https://technet.microsoft.com/library/mt148491.aspx).

- [Aggiungere protezione anti-malware all'organizzazione](https://technet.microsoft.com/en-us/library/jj200669%28v=exchg.150%29.aspx).

- Informazioni su come abilitare i suggerimenti per la [sicurezza nei messaggi di posta elettronica in Office 365](safety-tips-in-office-365.md) per gli utenti.

- Se si usa un dominio personalizzato per l'organizzazione in Office 365, impostare SPF, DKIM e quindi DMARC per convalidare la posta inviata dall'organizzazione e contribuire a prevenire lo spoofing:

  - [Configurare SPF in Office 365 per impedire lo spoofing](https://docs.microsoft.com/office365/SecurityCompliance/set-up-spf-in-office-365-to-help-prevent-spoofing).

  - [Utilizzare DKIM per convalidare la posta elettronica in uscita inviata dal dominio personalizzato in Office 365](https://docs.microsoft.com/office365/SecurityCompliance/set-up-spf-in-office-365-to-help-prevent-spoofing).

  - [Utilizzare DMARC per convalidare la posta elettronica in Office 365](https://technet.microsoft.com/library/mt734386%28v=exchg.150%29.aspx).

## <a name="enable-mailbox-audit-logging"></a>Abilitare la registrazione di controllo della cassetta postale

Una registrazione di controllo viene automaticamente abilitata per l'utente in Office 365; Tuttavia, la registrazione di controllo delle cassette postali non è attivata per impostazione predefinita. Si attiva la registrazione di controllo per tutte le cassette postali degli utenti in Office 365 utilizzando PowerShell di Exchange Online. Per informazioni, vedere [abilitare il controllo delle cassette postali in Office 365](https://go.microsoft.com/fwlink/p/?LinkID=626109).
  
Dopo aver abilitato la registrazione di controllo, è possibile [eseguire una ricerca nel registro di controllo &amp; nel centro sicurezza e conformità di Office 365](search-the-audit-log-in-security-and-compliance.md) per scoprire chi ha effettuato l'accesso alle cassette postali degli utenti, ai messaggi inviati e ad altre attività eseguite dal proprietario della cassetta postale, un utente delegato, o da un amministratore. Per un elenco delle attività delle cassette postali incluse nel log di controllo di Office 365 per impostazione predefinita, vedere [attività Cassetta postale di Exchange](search-the-audit-log-in-security-and-compliance.md#exchange-mailbox-activities).
  
Per informazioni sulle altre azioni che è possibile eseguire con il registro di controllo, ad esempio la modifica del periodo di tempo per il salvataggio delle voci nel log di controllo, vedere [registrazione di controllo delle cassette postali in Exchange 2016](https://technet.microsoft.com/en-us/library/ff459237%28v=exchg.160%29.aspx).
  
## <a name="configure-data-loss-prevention-dlp"></a>Configurare la prevenzione della perdita di dati (DLP)

DLP consente di identificare i dati sensibili e creare criteri che consentono di impedire agli utenti di condividere accidentalmente o intenzionalmente i dati. DLP è compatibile con Office 365 incluso Exchange Online, SharePoint Online e OneDrive in modo che gli utenti possano rimanere conformi senza interrompere il flusso di lavoro. Per ulteriori informazioni, vedere [Panoramica dei criteri di prevenzione della perdita dei dati](data-loss-prevention-policies.md).
  
## <a name="use-customer-lockbox"></a>Utilizzo dell'archivio protetto dei clienti

In qualità di amministratore di Office 365, è possibile usare Customer Lockbox per controllare il modo in cui un tecnico del supporto Microsoft può accedere ai dati dell'utente durante una sessione di assistenza. Nei casi in cui il tecnico richiede l'accesso ai dati dell'utente per risolvere e correggere un problema, Customer Lockbox consente di approvare o rifiutare la richiesta di accesso. Se lo si approva, il tecnico può accedere ai dati. Ogni richiesta ha una scadenza e, dopo che il problema viene risolto, la richiesta viene chiusa e l'accesso revocato. L'archivio protetto dei clienti è incluso nel piano Office 365 Enterprise E5 oppure è possibile acquistare un abbonamento separato con qualsiasi altro piano di Office 365 Enterprise. Per informazioni, vedere [richieste dell'archivio clienti di Office 365](https://support.office.com/article/36f9cdd1-e64c-421b-a7e4-4a54d16440a2).
  
## <a name="try-it-yourself"></a>Provare da soli
<a name="SecureScore"> </a>

Vedere queste funzionalità di sicurezza che operano in una sottoscrizione di valutazione di Office 365 prima di adottarli in produzione.
  
- [Creare una sottoscrizione di valutazione di Office 365](https://technet.microsoft.com/library/mt736406.aspx)

- [Configurare e testare l'autenticazione master per un account utente](https://technet.microsoft.com/library/mt492459.aspx)

- [Configurare e testare Office 365 cloud app Security per notificare l'attività di amministratore globale](https://technet.microsoft.com/library/mt757250.aspx)

- [Configurare e testare ATP per messaggi di posta elettronica sospetti](https://technet.microsoft.com/library/mt490479.aspx)

- Controllare il [Punteggio di Office 365 Secure](https://securescore.office.com/) per la sottoscrizione di valutazione per ognuno dei passaggi precedenti.