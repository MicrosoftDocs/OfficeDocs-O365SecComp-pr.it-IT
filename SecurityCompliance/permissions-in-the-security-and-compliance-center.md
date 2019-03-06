---
title: Permissions in the Office 365 Security &amp; Compliance Center
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 6/29/2018
ms.audience: Admin
ms.topic: conceptual
f1_keywords:
- ms.o365.cc.AdminRoleGroups
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MET150
description: Il Centro sicurezza &amp; e conformità di Office 365 consente di concedere autorizzazioni a utenti che eseguono attività di conformità come la gestione dei dispositivi, la prevenzione della perdita di dati, eDiscovery, la conservazione e così via. Tali utenti possono eseguire solo le attività in cui si concede esplicitamente l'accesso. Per accedere al centro &amp; sicurezza e conformità, gli utenti devono essere un amministratore globale di Office 365 o un membro di uno o &amp; più gruppi di ruoli del Centro sicurezza e conformità.
ms.openlocfilehash: 6c558671a376f1f25efc7f7846df1c07655022b3
ms.sourcegitcommit: ed822a776d3419853453583e882f3c61ca26d4b2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/05/2019
ms.locfileid: "30410651"
---
# <a name="permissions-in-the-office-365-security-amp-compliance-center"></a>Permissions in the Office 365 Security &amp; Compliance Center

Il Centro sicurezza &amp; e conformità di Office 365 consente di concedere autorizzazioni a utenti che eseguono attività di conformità come la gestione dei dispositivi, la prevenzione della perdita di dati, eDiscovery, la conservazione e così via. Tali utenti possono eseguire solo le attività in cui si concede esplicitamente l'accesso. Per accedere al centro &amp; sicurezza e conformità, gli utenti devono essere un amministratore globale di Office 365 o un membro di uno o &amp; più gruppi di ruoli del Centro sicurezza e conformità.
  
Le autorizzazioni nel centro &amp; sicurezza e conformità si basano sul modello delle autorizzazioni del controllo di accesso basato sui ruoli (RBAC). Si tratta dello stesso modello di autorizzazioni utilizzato da Exchange, quindi se si ha familiarità con Exchange, la concessione di autorizzazioni nel centro &amp; sicurezza e conformità sarà molto simile. Tuttavia, è importante tenere presente che i gruppi di ruoli di Exchange e &amp; i gruppi di ruoli del centro conformità di sicurezza non condividono l'appartenenza o le autorizzazioni. Sebbene entrambi dispongano di un gruppo di ruoli di gestione dell'organizzazione, non sono uguali. Le autorizzazioni concesse e i membri dei gruppi di ruoli sono diverse. Di seguito è riportato un elenco &amp; di gruppi di ruoli del Centro sicurezza e conformità.
  
![Pagina delle autorizzazioni nel centro sicurezza &amp; e conformità di Office 365](media/992c20ca-e82e-497c-9c8d-6fab212deb80.png)
  
## <a name="relationship-of-members-roles-and-role-groups"></a>Relazione tra membri, ruoli e gruppi di ruoli

Un **ruolo** concede le autorizzazioni per eseguire una serie di attività. ad esempio, il ruolo di gestione dei casi consente alle persone di lavorare con eDiscovery. 
  
Un **gruppo di ruolo** è un insieme di ruoli che consentono agli utenti di svolgere il proprio &amp; lavoro nel centro sicurezza e conformità. ad esempio, il gruppo di ruoli amministratore conformità include i ruoli per la gestione dei casi, la ricerca contenuto e la configurazione dell'organizzazione (più altri) perché un amministratore di conformità avrà bisogno delle autorizzazioni necessarie per svolgere il proprio lavoro. 
  
Il centro &amp; sicurezza e conformità include i gruppi di ruoli predefiniti per le attività e le funzioni più comuni che è necessario assegnare agli utenti. È consigliabile aggiungere singoli utenti come **membri** ai gruppi di ruoli predefiniti. 
  
![Diagramma che mostra la relazione tra gruppi di ruoli e ruoli e membri](media/2a16d200-968c-4755-98ec-f1862d58cb8b.png)
  
È possibile modificare o eliminare i gruppi di ruoli esistenti, ma non è consigliabile. Invece di modificare un gruppo di ruoli predefinito, è possibile copiarlo, modificarlo e quindi salvarlo con un altro nome.
  
## <a name="permissions-needed-to-use-features-in-the-security-amp-compliance-center"></a>Autorizzazioni necessarie per utilizzare le funzionalità nel centro &amp; sicurezza e conformità

Nella tabella seguente sono elencati i gruppi di ruoli predefiniti disponibili nel centro sicurezza &amp; e conformità. Per concedere le autorizzazioni a un utente per l'esecuzione di un'attività di conformità, aggiungerle &amp; al gruppo di ruoli centro conformità di sicurezza appropriato.
  
La gestione delle autorizzazioni nel &amp; Centro sicurezza e conformità fornisce solo agli utenti l'accesso alle funzionalità di conformità disponibili all' &amp; interno del Centro sicurezza e conformità stesso. Se si desidera concedere le autorizzazioni ad altre funzionalità di conformità che non sono nel &amp; Centro sicurezza e conformità, ad esempio le regole del flusso di posta di Exchange (note anche come regole di trasporto), è necessario utilizzare l'interfaccia di amministrazione di Exchange.
  
Per informazioni su come concedere l'accesso al centro &amp; sicurezza e conformità, vedere [concedere agli utenti l'accesso all'interfaccia di amministrazione di Office 365 Compliance](grant-access-to-the-security-and-compliance-center.md).
  
|**Gruppo di ruolo**|**Descrizione**|
|:-----|:-----|
|**Amministratore di conformità** <sup>1</sup> <br/> |I membri possono gestire le impostazioni per la gestione dei dispositivi, la prevenzione della perdita di dati, i report e la conservazione.  <br/> |
|**Gestore di eDiscovery** <br/> | I membri possono eseguire ricerche e conservare posizioni su cassette postali, siti di SharePoint Online e OneDrive for business. I membri possono anche creare e gestire i casi di eDiscovery, aggiungere e rimuovere membri in un caso, creare e modificare le ricerche di contenuto associate a un caso e accedere ai dati del caso in Office 365 Advanced eDiscovery. <br/><br/>Un amministratore di eDiscovery è un membro del gruppo di ruoli di eDiscovery Manager a cui sono state assegnate altre autorizzazioni. Oltre alle attività che possono essere eseguite da un Manager di eDiscovery, un amministratore di eDiscovery può:  <br/><br/>  • Visualizzare tutti i casi di eDiscovery nell'organizzazione.  <br/>  • Gestire qualsiasi caso di eDiscovery dopo essersi aggiunti come membri del caso.  <br/><br/>La differenza principale tra un responsabile di eDiscovery e un amministratore di eDiscovery è che un Admininstrator eDiscovery può accedere a tutti i casi elencati nella pagina **casi di eDiscovery** nel &amp; Centro sicurezza e conformità. Un Manager di eDiscovery può accedere solo ai casi in cui sono stati creati o a cui sono membri.  Per ulteriori informazioni su come rendere un utente un amministratore di eDiscovery, vedere [assegnare le autorizzazioni di eDiscovery nel &amp; Centro sicurezza e conformità di Office 365](assign-ediscovery-permissions.md).  <br/>           |
|**Gestione dell'organizzazione** <sup>1</sup> <br/> |I membri possono controllare le autorizzazioni per l'accesso alle funzionalità &amp; nel centro sicurezza e conformità, nonché gestire le impostazioni per la gestione dei dispositivi, la prevenzione della perdita di dati, i report e la conservazione.  <br/> Si noti che per un utente che non è un amministratore globale per visualizzare l'elenco dei dispositivi gestiti da MDM per Office 365 ed eseguire azioni su questi dispositivi, ad esempio il ritiro di un dispositivo da MDM per Office 365, l'utente deve essere un amministratore di Exchange.  <br/> Gli amministratori globali di Office 365 vengono aggiunti automaticamente come membri di questo gruppo di ruoli.           |
|**Gestione record** <br/> |I membri possono gestire e disporne il contenuto dei record.  <br/> |
|**Reviewer** <br/> |I membri possono visualizzare solo l'elenco dei casi nella pagina casi di eDiscovery nel centro &amp; sicurezza e conformità. Non è possibile creare, aprire o gestire un caso di eDiscovery. Lo scopo principale di questo gruppo di ruoli è consentire ai membri di visualizzare e accedere ai dati del caso in Advanced eDiscovery.  <br/> Questo gruppo di ruoli ha le autorizzazioni più restrittive relative a eDiscovery.  <br/> |
|**Amministratore della sicurezza** <br/> |I membri di questo gruppo di ruolo possono includere gli amministratori tra i servizi, nonché i gruppi di partner esterni e il supporto tecnico Microsoft. Per impostazione predefinita, non è possibile assegnare alcun ruolo a questo gruppo. Tuttavia, sarà un membro del ruolo Security Administrators in Azure Active Directory e erediterà le funzionalità di quel ruolo. Per gestire le autorizzazioni in modo centralizzato, apportare modifiche a questo ruolo nell'interfaccia di amministrazione di Azure Active Directory-per ulteriori informazioni, vedere [autorizzazioni dei ruoli di amministratore in Azure Active Directory](https://docs.microsoft.com/en-us/azure/active-directory/users-groups-roles/directory-assign-admin-roles). Se si modifica questo gruppo di ruoli nel centro sicurezza & Compliance, tali modifiche verranno applicate solo al centro conformità & sicurezza e non a qualsiasi altro servizio, mentre le modifiche apportate nell'interfaccia di amministrazione di Azure Active Directory influiscono su tutti i servizi.<br/> Tutte le autorizzazioni di sola lettura del ruolo di Reader di sicurezza, oltre a una serie di autorizzazioni amministrative aggiuntive per gli stessi servizi: Azure Information Protection, Identity Protection Center, Privileged Identity Management, monitor Office 365 Service Centro sicurezza &amp; e conformità di Office 365.  <br/> |
|**Lettore di sicurezza** <br/> |I membri dispongono dell'accesso in sola lettura a diverse funzionalità di sicurezza di Identity Protection Center, gestione delle identità con privilegi, monitoraggio dell'integrità dei servizi di Office &amp; 365 e Office 365 Security Compliance Center.  <br/> L'appartenenza a questo gruppo di ruoli è sincronizzata tra i servizi e gestita centralmente. I membri di questo gruppo di ruolo possono includere gli amministratori tra i servizi, nonché i gruppi di partner esterni e il supporto tecnico Microsoft. Per impostazione predefinita, non è possibile assegnare alcun ruolo a questo gruppo. Tuttavia, sarà un membro del ruolo Security Readers in Azure Active Directory e erediterà le funzionalità di quel ruolo. Per gestire le autorizzazioni in modo centralizzato, apportare modifiche a questo ruolo nell'interfaccia di amministrazione di Azure Active Directory-per ulteriori informazioni, vedere [autorizzazioni dei ruoli di amministratore in Azure Active Directory](https://docs.microsoft.com/en-us/azure/active-directory/users-groups-roles/directory-assign-admin-roles). Se si modifica questo gruppo di ruoli nel centro sicurezza & Compliance, tali modifiche verranno applicate solo al centro conformità & sicurezza e non a qualsiasi altro servizio, mentre le modifiche apportate nell'interfaccia di amministrazione di Azure Active Directory influiscono su tutti i servizi.<br/> |
|**Utente di Service Assurance** <br/> |I membri possono accedere alla sezione Assurance del servizio nel centro sicurezza &amp; e conformità di Office 365. Service Assurance fornisce report e documenti che descrivono le procedure di sicurezza di Microsoft per i dati dei clienti archiviati in Office 365. Vengono inoltre forniti report di controllo di terze parti indipendenti su Office 365. Per ulteriori informazioni, vedere [Service Assurance nel centro sicurezza &amp; e conformità di Office 365](http://go.microsoft.com/fwlink/p/?LinkID=717765).  <br/> |
|**Revisione di superVisione** <br/> |I membri possono creare e gestire i criteri che definiscono le comunicazioni soggette a revisione in un'organizzazione. Per ulteriori informazioni, vedere [configurare i criteri di revisione di supervisione per l'organizzazione](configure-supervision-policies.md).  <br/> |
   
> [!NOTE]
> <sup>1</sup> questo gruppo di ruoli non assegna ai membri le autorizzazioni necessarie per eseguire una ricerca nel registro di controllo di Office 365 o per utilizzare i report che potrebbero includere dati di Exchange, ad esempio i report DLP o ATP. Per eseguire una ricerca nel registro di controllo o per visualizzare tutti i report, a un utente devono essere assegnate le autorizzazioni in Exchange Online. Ciò è dovuto al fatto che il cmdlet sottostante utilizzato per eseguire la ricerca nel registro di controllo è un cmdlet di Exchange Online. Gli amministratori globali di Office 365 possono eseguire una ricerca nel registro di controllo e visualizzare tutti i report perché vengono aggiunti automaticamente come membri del gruppo di ruoli Gestione organizzazione in Exchange Online. Per ulteriori informazioni, vedere [eseguire la ricerca nel log di controllo nel centro &amp; sicurezza e conformità di Office 365](https://go.microsoft.com/fwlink/p/?LinkID=708432). 
  

