---
title: Roadmap di protezione di Office 365 - priorità superiore per i primi 30 giorni, 90 giorni e versioni successive
ms.author: bcarter
author: BrendaCarter
manager: laurawi
ms.date: 10/08/2018
ms.audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- Strat_O365_IP
search.appverid:
- MET150
ms.assetid: 28c86a1c-e4dd-4aad-a2a6-c768a21cb352
description: "Indicazioni principali alla sicurezza informatica team di Microsoft per l'implementazione della funzionalità di protezione per proteggere l'ambiente Office 365. "
ms.openlocfilehash: 58767ea9a2b825d1583d9135f9d8edcb0d20d7c2
ms.sourcegitcommit: 4a7d7717f0da05cf5a3c506df2989a9d02f33dfa
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/08/2018
ms.locfileid: "25450081"
---
# <a name="office-365-security-roadmap---top-priorities-for-the-first-30-days-90-days-and-beyond"></a>Roadmap di protezione di Office 365 - priorità superiore per i primi 30 giorni, 90 giorni e versioni successive

In questo articolo sono incluse indicazioni principali alla sicurezza informatica team di Microsoft per l'implementazione della funzionalità di protezione per proteggere l'ambiente Office 365. In questo articolo è stato adattato da una sessione di Ignite per Microsoft, ovvero [sicura Office 365 come alla sicurezza informatica pro: principali priorità per i primi 30 giorni, 90 giorni e oltre](https://www.youtube.com/watch?v=luignzNyR-o). In questa sessione è stata sviluppata e presentata da Mark Simos e Matt Kemelhar, alla sicurezza informatica architetti.
  
Contenuto dell'articolo:
  
- [Risultati roadmap](security-roadmap.md#Roadmap)
    
- [30 giorni, ovvero potenti wins veloce](security-roadmap.md#Thirdaydays)
    
- [90 giorni, ovvero avanzata protezioni](security-roadmap.md#Ninetydays)
    
- [Oltre a](security-roadmap.md#Beyond)
    
## <a name="roadmap-outcomes"></a>Risultati roadmap
<a name="Roadmap"> </a>

Questi suggerimenti della Guida di orientamento sono in fasi in tre fasi in ordine logico con gli obiettivi seguenti.

|||
|:-----|:-----|
| |Risultati
|30 giorni|Configurazione semplice e rapida:  <br/> • Protezione di amministrazione di base  <br/> Analitica e registrazione •  <br/> • Protezione di identità di base  <br/> Configurazione tenant  <br/>  Preparare le parti interessate  <br/> |
|90 giorni|Protezioni avanzate:  <br/> • Account di amministrazione  <br/>  • Dati &amp; gli account utente  <br/>  Visibilità delle esigenze di conformità, rischio e utente  <br/>  Adattare e implementare la protezione e criteri predefiniti  <br/> |
|Oltre a|Regolare e ottimizzare i controlli e criteri chiave  <br/> Estendere protezioni alle dipendenze locale  <br/> Integrazione con i processi aziendali e di sicurezza (legali, minaccia interna e così via)  <br/> |
  

   
## <a name="30-days--powerful-quick-wins"></a>30 giorni, ovvero potenti wins veloce
<a name="Thirdaydays"> </a>

Queste attività possono essere eseguite rapidamente e hanno un impatto minimo sugli utenti.
  
|||
|:-----|:-----|
|Area  <br/> |Attività  <br/> |
|Gestione della sicurezza  <br/> |• Controllo punteggio sicura e prendere nota del punteggio corrente ( [https://securescore.office.com](https://securescore.office.com)).  <br/>  • Attivare la registrazione di controllo per Office 365. Vedere [nel Registro di controllo di ricerca in Office 365 Security &amp; centro conformità](search-the-audit-log-in-security-and-compliance.md).<br/> • [Configure Office 365 tenant per aumentare la protezione](tenant-wide-setup-for-increased-security.md) .  <br/>  • Verificare regolarmente dashboard e rapporti di protezione di Office 365 e centro conformità e sicurezza App Cloud.  <br/> |
|Protezione dalle minacce  <br/> |[Connettere Microsoft Cloud App protezione di Office 365](https://docs.microsoft.com/cloud-app-security/connect-office-365-to-microsoft-cloud-app-security) per avviare il monitoraggio utilizzando i criteri di rilevamento di rischio predefiniti per i comportamenti anomali. Sono necessari sette giorni per creare una linea di base per il rilevamento anomalia.<br><br/>  Implementare la protezione per gli account di amministratore:  <br/> • Utilizzare dedicata amministratore degli account per l'attività di amministrazione.  <br/>  • Imporre l'autenticazione a più fattori (MFA) per gli account di amministratore.  <br/>  • Utilizzare un [dispositivo Windows 10 a protezione avanzata](https://docs.microsoft.com/windows-hardware/design/device-experiences/oem-highly-secure) per l'attività di amministrazione.  <br/> |
|Gestione di identità e accesso  <br/> |• [Abilitare la protezione con identità Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection-enable).  <br/> • Per gli ambienti di identità federata, applicare la protezione di account (lunghezza delle password, scadenza, complessità e così via).  <br/> |
|Protezione delle informazioni  <br/> | Esaminare i suggerimenti di protezione informazioni di esempio. Protezione delle informazioni richiede il coordinamento all'interno dell'organizzazione. Introduzione a queste risorse:<br/> • [Protezione di office 365 informazioni per PILR](http://aka.ms/o365gdpr) <br/> • [File e siti di SharePoint Online sicura](https://docs.microsoft.com/Office365/enterprise/secure-sharepoint-online-sites-and-files) (include la condivisione, classificazione, prevenzione della perdita di dati e la protezione delle informazioni di Azure)  <br/> |
   
## <a name="90-days--enhanced-protections"></a>90 giorni, ovvero avanzata protezioni
<a name="Ninetydays"> </a>

Queste attività richiedono una quantità di tempo leggermente superiore per la pianificazione e l'implementazione, ma aumentano notevolmente il livello di sicurezza. 
  
|||
|:-----|:-----|
|Area  <br/> |Attività  <br/> |
|Gestione della sicurezza  <br/> | • Verificare punteggio sicura per le azioni consigliate per l'ambiente corrente ( [https://securescore.office.com](https://securescore.office.com)).  <br/>  • Continuano a verificare regolarmente dashboard e nei report di protezione di Office 365 e centro conformità, Cloud App sicurezza e strumenti SIEM.  <br/>  • Cercare e implementare gli aggiornamenti software.  <br/>  • Simulazioni attacco condurre per spear phishing, password spray e gli attacchi di forza bruta password mediante [Simulatore di attacco](https://support.office.com/article/attack-simulator-office-365-da5845db-c578-4a41-b2cb-5a09689a551b) (incluso in [Office 365 rischio Intelligence](office-365-ti.md)).  <br/>  • Interfaccia per la condivisione dei rischi visualizzando i report predefiniti in Cloud App Security (nella scheda indagare).  <br/>  • Verificare [Responsabile della conformità](meet-data-protection-and-regulatory-reqs-using-microsoft-cloud.md) per esaminare lo stato per le regole che si applicano all'organizzazione (ad esempio PILR NIST 800 171).  <br/> |
|Protezione dalle minacce  <br/> | Implementare la protezione avanzate per gli account di amministratore:  <br/>  • Configurare [Workstation con privilegi di accesso](https://docs.microsoft.com/windows-server/identity/securing-privileged-access/privileged-access-workstations) (zampe) per l'attività di amministrazione.  <br/>  • Configurare [la gestione delle identità con privilegi di Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-privileged-identity-management-configure).  <br/>  • Configurare uno strumento di gestione (SIEM) eventi e informazioni sicurezza per la raccolta dati di registrazione di Office 365, Cloud App sicurezza e altri servizi, inclusi AD FS. Il Registro di controllo di Office 365 archivia i dati per solo 90 giorni. Acquisizione dei dati nello strumento di SIEM consente di archiviare i dati per un periodo più lungo.<br/> |
|Gestione di identità e accesso  <br/> | • Abilitare e applicare MFA per tutti gli utenti.  <br/>  • Implementare un insieme di [accesso condizionato e criteri correlati](https://docs.microsoft.com/en-us/microsoft-365/enterprise/microsoft-365-policies-configurations). |
|Protezione delle informazioni  <br/> | Adattare e implementazione dei criteri di protezione delle informazioni. Le risorse sono alcuni esempi:<br/> • [Protezione di office 365 informazioni per PILR](http://aka.ms/o365gdpr) <br/> • [File e siti di SharePoint Online sicura](https://docs.microsoft.com/Office365/enterprise/secure-sharepoint-online-sites-and-files) <br/> <br> Utilizzare criteri di prevenzione della perdita di dati e strumenti di monitoraggio in Office 365 per i dati memorizzati in Office 365 (al posto della protezione App Cloud). <br><br>Utilizzare la protezione App Cloud con Office 365 per avanzati avvisi caratteristiche (oltre prevenzione della perdita di dati).  <br/> |
   
## <a name="beyond"></a>Oltre a
<a name="Beyond"> </a>

Si tratta di misure di sicurezza importanti che generano sul lavoro precedente. 
  
|||
|:-----|:-----|
|Area  <br/> |Attività  <br/> |
|Gestione della sicurezza  <br/> |• Continuare la pianificazione azioni successive utilizzando Secure punteggio ( [https://securescore.office.com](https://securescore.office.com)).  <br/>  • Continuano a verificare regolarmente dashboard e nei report di protezione di Office 365 e centro conformità, Cloud App sicurezza e strumenti SIEM.  <br/>  • Continua cercare e l'implementazione degli aggiornamenti software.  <br/>  • Integrare eDiscovery nei legali e processi di risposta di rischio.  <br/> |
|Protezione dalle minacce  <br/> | • Implementazione [Sicura accesso privilegiato](https://docs.microsoft.com/windows-server/identity/securing-privileged-access/securing-privileged-access) (SPA) per i componenti di identità in locale (Active Directory, ADFS).  <br/>  • Utilizzare Cloud App protezione da monitorare per minacce dal.  <br/>  • Individuare l'ombreggiatura IT SaaS utilizzo utilizzando la protezione di applicazione Cloud.  <br/> |
|Gestione di identità e accesso  <br/> | Criteri di protezione delle informazioni Affina ricerca •:  <br/>  • Azure Information Protection and Office 365 prevenzione di perdita di dati (DLP).  <br/>  • Cloud App criteri e protezione degli avvisi.  <br/> |
|Protezione delle informazioni  <br/> | • Affina ricerca criteri e i processi operativi.  <br/>  • Utilizzare la protezione dell'identità di Azure Active Directory per identificare le minacce dal.  <br/> |
   
Vedere anche: [come attenuare cyberattacks rapida, ad esempio Petya e WannaCrypt](https://cloudblogs.microsoft.com/microsoftsecure/2018/02/21/how-to-mitigate-rapid-cyberattacks-such-as-petya-and-wannacrypt/). 
  

