---
title: Configurare il tenant di Office 365 per una maggiore sicurezza
ms.author: bcarter
author: BrendaCarter
manager: laurawi
ms.date: 10/11/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.service: o365-administration
localization_priority: Normal
search.appverid: MET150
ms.assetid: 8d274fe3-db51-4107-ba64-865e7155b355
description: Viene illustrata la configurazione consigliata per le impostazioni a livello di tenant che influiscono sulla sicurezza dell'ambiente Office 365. Le esigenze di sicurezza potrebbero richiedere più o meno della protezione. Utilizzare questi suggerimenti come punto di partenza.
ms.openlocfilehash: de3a1d19e09144105f9576b3a4eb8ed76eb08585
ms.sourcegitcommit: ba2175e394d0cb9f8ede9206aabb44b5b677fa0a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/11/2018
ms.locfileid: "25496870"
---
# <a name="configure-your-office-365-tenant-for-increased-security"></a>Configurare il tenant di Office 365 per una maggiore sicurezza

In questo argomento viene illustrata la configurazione consigliata per le impostazioni a livello di tenant che influiscono sulla sicurezza dell'ambiente Office 365. Le esigenze di sicurezza potrebbero richiedere più o meno della protezione. Utilizzare questi suggerimenti come punto di partenza.
  
## <a name="check-office-365-secure-score"></a>Controllare punteggio protetta di Office 365

Office 365 sicura punteggio analizza la protezione dell'organizzazione Office 365 in base alle normali attività e le impostazioni di sicurezza e assegna un punteggio. Per iniziare è necessario prendere nota del punteggio corrente. Modificare alcune impostazioni a livello di tenant aumenta punteggio. L'obiettivo è non per ottenere il massimo punteggio, ma per tenere conto delle opportunità per proteggere l'ambiente che non avere effetti negativi sulla produttività degli utenti. Vedere [Introduzione il punteggio protetta di Office 365](office-365-secure-score.md).
  
## <a name="tune-threat-management-policies-in-the-office-365-security-amp-compliance-center"></a>Ottimizzare i criteri di gestione delle minacce in Office 365 Security &amp; centro conformità

La protezione di Office 365 &amp; centro conformità include funzionalità che proteggere l'ambiente. Include inoltre rapporti e dashboard che è possibile utilizzare per monitorare ed eseguire l'azione necessaria. Vengono fornite alcune aree con configurazioni dei criteri predefiniti. Alcune aree non includono criteri predefiniti o le regole. Visitare questi criteri in Gestione minaccia per ottimizzare le impostazioni di gestione delle minacce per un ambiente più sicuro. 
  
|Area * * *|Include un criterio predefinito *|Suggerimento * * *|
|:-----|:-----|:-----|
|**Protezione anti-phishing** <br/> |Sì  <br/> | Se si dispone di un dominio personalizzato, creare un criterio di protezione anti-phishing per proteggere gli account di posta elettronica degli utenti più importanti, ad esempio l'amministratore delegato e per la protezione del dominio. Esaminare [impostare i criteri di anti-phishing](set-up-anti-phishing-policies.md) e creare un criterio con l'esempio come guida: "esempio: criteri Anti-phishing per proteggere un utente e un dominio."|
|**Motore antimalware** <br/> |Sì  <br/> | Modificare il criterio predefinito:  <br/> • Comuni allegati tipi di filtro, selezionare  <br/><br>  È anche possibile creare criteri di filtro malware personalizzato e applicarle a utenti specificati, gruppi o i domini nell'organizzazione.  <br/> <br> Ulteriori informazioni:  <br/> • [Protezione anti-malware](https://technet.microsoft.com/en-us/library/jj200669%28v=exchg.150%29.aspx) <br/> • [Configure anti-malware policies](https://technet.microsoft.com/en-us/library/jj200745%28v=exchg.150%29.aspx) <br/> |
|**Allegati sicuri di ATP** <br/> |No  <br/> | Nella pagina principale per gli allegati sicuri, proteggere i file in SharePoint, OneDrive e Teams Microsoft selezionando questa casella:  <br/>  • Accensione degli strumenti di analisi di SharePoint, OneDrive e team di Microsoft  <br/> <br> Aggiungere un nuovo criterio di sicurezza degli allegati con le seguenti impostazioni:  <br/>  • Blocco, blocca i messaggi di posta elettronica attuali e future e gli allegati con malware rilevato (scegliere questa opzione)  <br/>  • Abilita reindirizzamento, (questa casella di controllo e immettere un indirizzo di posta elettronica, ad esempio un account di amministratore o quarantena)  <br/>  • Applica alla selezione precedente se timeout di analisi per gli allegati antimalware o errore (questa casella di controllo)  <br/>  • Applicato a, ovvero il dominio del destinatario è (selezionare il dominio)  <br/>  <br>Ulteriori informazioni: [impostare i criteri di sicurezza degli allegati degli strumenti di analisi di Office 365](set-up-atp-safe-attachments-policies.md) <br/> |
|**Collegamenti Safe degli strumenti di analisi** <br/> |Sì  <br/> | Aggiungere questa impostazione per il criterio predefinito per l'intera organizzazione:  <br/> • Utilizzare sicuri collegamenti: Office 365 ProPlus, di Office per iOS e Android (Selezionare questa opzione).  <br/> <br>Criteri consigliati per i destinatari specifici:  <br/>  • URL verranno riscritti e confrontati con un elenco di collegamenti dannosi noti quando l'utente fa clic sul collegamento (Selezionare questa opzione).  <br/>  • Utilizzare gli allegati sicuri per analizzare contenuto scaricabile (questa casella di controllo).  <br/>  • Applicato a, ovvero il dominio del destinatario è (selezionare il dominio).  <br/> <br> Ulteriori informazioni: [collegamenti sicuri degli strumenti di analisi di Office 365](atp-safe-links.md).  <br/> |
|**Protezione da posta indesiderata (Mail filtering)** <br/> |Sì  <br/> | Gli elementi da visualizzare per:  <br/>  • Eccessivo di posta indesiderata, scegliere impostazioni personalizzate e modificare il criterio di filtro posta indesiderata predefinito.  <br/>  Business intelligence spoofing •, esaminare i mittenti che sono lo spoofing del dominio. Bloccare o consentire i mittenti.<br/>  <br>Ulteriori informazioni: [Office 365 posta Anti-Spam Protection](anti-spam-protection.md).  <br/> |
|**DKIM (DomainKeys identificato posta)** <br/> |Sì  <br/> |DKIM è un processo di autenticazione che contribuisce di proteggere mittenti e destinatari da contraffatto (spoofing) e posta elettronica di phishing. Tenant include una firma predefinita per il dominio. Creare una firma DKIM aggiuntiva se si aggiungono domini personalizzati per il tenant.<br/> <br>Ulteriori informazioni: [La utilizza per convalidare la posta elettronica inviata dal dominio personalizzato in Office 365](https://technet.microsoft.com/en-us/library/mt695945%28v=exchg.150%29.aspx) <br/> |
   
## <a name="view-dashboards-and-reports-in-the-security-amp-compliance-center"></a>Visualizzare report e dashboard per la protezione &amp; centro conformità

Visitare questi rapporti e dashboard per ulteriori informazioni sulle condizioni dell'ambiente. I dati in questi rapporti non saranno più avanzati come l'organizzazione utilizza servizi di Office 365. Per il momento, acquisire familiarità con i quali è possibile monitorare ed eseguire l'azione necessaria. Per ulteriori informazioni, vedere: [Reports in Office 365 Security &amp; centro conformità](reports-in-security-and-compliance.md).
  
|Dashboard * * *|****Description****|
|:-----|:-----|
|Dashboard di gestione dei rischi  <br/> |Nella sezione gestione del rischio di protezione &amp; conformità Allinea al centro, utilizzare il dashboard per vedere le minacce che sono già state gestite e come uno strumento utile per i report per decisori aziendali su cosa ha già eseguito Intelligence minaccia per proteggere il Business.  <br/> |
|Soluzioni di rischio  <br/> |È anche nella sezione gestione del rischio di protezione &amp; centro conformità. Se l'analisi dei o subendo un attacco con Office 365 tenant, utilizzare explorer rischio per l'analisi delle minacce. Explorer rischio viene visualizzato il volume degli attacchi nel tempo, è possibile analizzare dati famiglie di minacce, infrastruttura autore dell'attacco e altro ancora. È inoltre possibile contrassegnare qualsiasi messaggio di posta elettronica sospetto per l'elenco di problemi.  <br/> |
|Report, Dashboard  <br/> |Nella sezione report della protezione &amp; centro conformità, controllo visualizzazione rapporti per le organizzazioni di Exchange Online e SharePoint Online. È inoltre possibile accedere Azure Active Directory (AD) utente accesso rapporti, rapporti di attività dell'utente e il controllo di Azure Active Directory accedere dalla pagina Visualizza report.  <br/> |
   
![Protezione &amp; Dashboard centro conformità](media/870ab776-36d2-49c7-b615-93b2bc42fce5.png)
  
## <a name="configure-additional-exchange-online-tenant-wide-settings"></a>Configurare ulteriori impostazioni a livello di tenant Exchange Online

Molti dei controlli di sicurezza e protezione nell'interfaccia di amministrazione di Exchange sono inclusi anche nei Centro connessioni di sicurezza e conformità. Non è necessario configurare questi in entrambe le posizioni. Ecco un paio di ulteriori impostazioni consigliati. 
  
|Area * * *|Include un criterio predefinito *|Suggerimento * * *|
|:-----|:-----|:-----|
|**Flusso di posta** (Regole di trasporto)  <br/> |No  <br/> | Aggiungere una regola di flusso di posta elettronica per proteggere il ransomware. Vedere "Come utilizzare le regole di trasporto di Exchange per tenere traccia o bloccare messaggi di posta elettronica con le estensioni di file utilizzate da ransomware" in questo articolo di blog: [modalità di gestione di ransomware](https://blogs.technet.microsoft.com/office365security/how-to-deal-with-ransomware/).<br><br/> Creare una regola di trasporto per impedire l'inoltro automatico della posta elettronica ai domini esterni. Per ulteriori informazioni, vedere [Fattori Client esterno le regole di inoltro con punteggio sicura](https://blogs.technet.microsoft.com/office365security/mitigating-client-external-forwarding-rules-with-secure-score/).<br/> <br>Ulteriori informazioni: [flusso di posta regole (regole di trasporto) di Exchange Online](https://technet.microsoft.com/en-us/library/jj919238%28v=exchg.150%29.aspx) <br/> |
|**Abilitare l'autenticazione moderno** <br/> |No  <br/> | Autenticazione moderno in Office 365 è un prerequisito per l'utilizzo di autenticazione a più fattori (MFA). MFA è consigliata per la protezione dell'accesso alle risorse cloud, inclusa la posta elettronica.<br/>  <br>Vedere i seguenti argomenti:  <br/> • [Abilitare o disabilitare l'autenticazione moderno di Exchange Online](https://support.office.com/article/58018196-f918-49cd-8238-56f57f38d662) <br/> • [Skype Business online: abilitare il tenant per l'autenticazione moderno](https://social.technet.microsoft.com/wiki/contents/articles/34339.skype-for-business-online-enable-your-tenant-for-modern-authentication.aspx) <br/>  <br>Autenticazione moderno è abilitata per impostazione predefinita per Office 2016 client, SharePoint Online e OneDrive for Business.  <br/>  <br>Ulteriori informazioni: [l'autenticazione moderno con Office 365 con client di Office](https://support.office.com/article/776c0036-66fd-41cb-8928-5495c0f9168a) <br/> |
   
## <a name="configure-tenant-wide-sharing-policies-in-sharepoint-admin-center"></a>Configurare i criteri di condivisione a livello di tenant nell'interfaccia di amministrazione di SharePoint

Consigli Microsoft per la configurazione di siti del team di SharePoint all'aumento dei livelli di protezione, iniziando dalla protezione di base. Per ulteriori informazioni, vedere [file e siti di SharePoint Online sicura](https://docs.microsoft.com/microsoft-365-enterprise/secure-sharepoint-online-sites-and-files)
  
Siti del team di SharePoint configurati a livello di base consentono la condivisione di file con utenti esterni tramite collegamenti di accesso anonimo. Questo approccio consigliato anziché l'invio di file nel messaggio di posta elettronica. 
  
Per supportare gli obiettivi di protezione di base, configurare i criteri di condivisione a livello di tenant come indicato di seguito. Impostazioni per i singoli siti di condivisione possono essere più restrittive rispetto a questo criterio a livello di tenant, ma non più permissiva. 
  
|Area * * *|Include un criterio predefinito *|Suggerimento * * *|
|:-----|:-----|:-----|
|**La condivisione** (SharePoint Online e OneDrive for Business)  <br/> |Sì  <br/> | Condivisione esterna è abilitata per impostazione predefinita. Queste impostazioni sono consigliate:<br/>  • Consenti condivisione autenticati gli utenti esterni e l'utilizzo di collegamenti di accesso anonimo (impostazione predefinita).  <br/>  • L'accesso anonimo collegamenti scadono in numero di giorni. Immettere un numero, se lo si desidera, ad esempio 30 giorni.<br/>  Tipo di collegamento • predefinito, selezionare interno (persone solo all'interno dell'organizzazione). Gli utenti che si desiderano condividere con collegamenti anonimi devono scegliere questa opzione dal menu di condivisione.<br/>  <br>Ulteriori informazioni: [Panoramica della condivisione esterna](https://support.office.com/article/c8a462eb-0723-4b0b-8d0a-70feafe4be85) <br/> |
   
Interfaccia di amministrazione di SharePoint e OneDrive for Business admin center includono le stesse impostazioni. Le impostazioni nell'interfaccia di amministrazione di uno si applicano a entrambi.
  
## <a name="configure-settings-in-azure-active-directory"></a>Configurare le impostazioni di Azure Active Directory

Assicurarsi di visitare queste due aree in Azure Active Directory per completare l'installazione a livello di tenant per ambienti più sicuri.
  
### <a name="configure-named-locations-under-conditional-access"></a>Configurare i percorsi denominati (sotto condizionale access)

Se l'organizzazione include uffici con accesso alla rete sicura, aggiungere gli intervalli di indirizzi IP attendibili per Azure Active Directory come alle posizioni. Questa funzionalità consente di ridurre il numero di segnalate falsi positivi per gli eventi di rischio di accesso. 
  
Vedere: [denominata percorsi di Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-named-locations)
  
### <a name="block-apps-that-dont-support-modern-authentication"></a>Blocca App che non supportano l'autenticazione moderno

L'autenticazione a più fattori richiede applicazioni che supportano l'autenticazione moderno. Non è possibile bloccare App che non supportano l'autenticazione moderno tramite le regole di accesso condizionale.
  
Per ambienti protetti, assicurarsi di disabilitare l'autenticazione per le applicazioni che non supportano l'autenticazione moderno. È possibile ottenere questo risultato in Azure Active Directory con un controllo che sarà presto disponibili.
  
Nel frattempo, utilizzare uno dei metodi seguenti per ottenere questo risultato per SharePoint Online e OneDrive for Business:
  
- Utilizzare PowerShell, vedere [Blocca App che non utilizzano l'autenticazione moderno](https://docs.microsoft.com/intune-classic/deploy-use/block-apps-with-no-modern-authentication).
    
- Questa configurazione nell'interfaccia di amministrazione di SharePoint nel "pagina di accesso ai dispositivi, ovvero"Controllo dell'accesso da applicazioni che non utilizzano l'autenticazione moderno". Scegliere Blocca. 
    
## <a name="get-started-with-cloud-app-security-or-office-365-cloud-app-security"></a>Guida introduttiva a Cloud App protezione o a Office 365 Cloud App

Utilizzare sicurezza App Cloud di Office 365 per valutare i rischi di avvisi attività sospette e di prendere automaticamente il azione. È necessario pianificare di Office 365 E5.
  
In alternativa, è possibile utilizzare Microsoft Cloud App Security ottenere approfonditi anche dopo che viene concesso l'accesso, i controlli completi e protezione migliorata per tutte le applicazioni cloud, tra cui Office 365. 
  
Poiché questa soluzione è consigliabile pianificare EMS E5, è consigliabile che iniziare con protezione App Cloud in modo che è possibile utilizzare questo con altre applicazioni SaaS nell'ambiente in uso. Usa impostazioni e criteri predefiniti.
  
Ulteriori informazioni:
  
- [Distribuzione di Cloud App Security](https://docs.microsoft.com/cloud-app-security/getting-started-with-cloud-app-security)
    
- [Ulteriori informazioni su Microsoft Cloud App Security](https://www.microsoft.com/en-us/cloud-platform/cloud-app-security)
    
- [Panoramica di Office 365 Cloud App Security](office-365-cas-overview.md)
    
![Dashboard di Cloud App Security](media/1fb2aa65-54b8-4746-9f5e-c187d339e9f5.png)
  
## <a name="additional-resources"></a>Risorse aggiuntive

Questi articoli e guide di forniscono informazioni aggiuntive fornite per proteggere l'ambiente Office 365:
  
- [Informazioni aggiuntive sulla protezione di Microsoft per campagne politiche, ricchi e altre organizzazioni agile](https://docs.microsoft.com/microsoft-365-enterprise/microsoft-security-guidance) (è possibile utilizzare questi suggerimenti in qualsiasi ambiente, in particolare gli ambienti solo cloud) 
    
- [Criteri di protezione consigliate e le configurazioni per le identità e dispositivi](https://docs.microsoft.com/microsoft-365-enterprise/microsoft-365-policies-configurations) (queste procedure consigliate includono la Guida per gli ambienti di AD FS) 
    

