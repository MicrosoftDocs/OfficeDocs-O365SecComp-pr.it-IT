---
title: Le autorizzazioni di sicurezza di Office 365 &amp; centro conformità
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 6/29/2018
ms.audience: Admin
ms.topic: overview
f1_keywords:
- ms.o365.cc.AdminRoleGroups
ms.service: o365-administration
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MET150
ms.assetid: d10608af-7934-490a-818e-e68f17d0e9c1
description: La protezione di Office 365 &amp; centro conformità consente di concedere le autorizzazioni agli utenti che conformità attività quali la gestione dei dispositivi, prevenzione della perdita di dati, eDiscovery, conservazione e così via. Questi utenti possono eseguire solo le attività che in modo esplicito concedere loro l'accesso a. Per la protezione dall'accesso di &amp; centro conformità, gli utenti devono essere un amministratore globale di Office 365 oppure membro di uno o più protezione &amp; gruppi di ruoli centro conformità.
ms.openlocfilehash: ef281ca7cda706ff78fbf1a5584674cdf41e9025
ms.sourcegitcommit: a64af0ebd0b03e4a5e60a33e9108c44c7d74f356
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/05/2019
ms.locfileid: "29741059"
---
# <a name="permissions-in-the-office-365-security-amp-compliance-center"></a>Le autorizzazioni di sicurezza di Office 365 &amp; centro conformità

La protezione di Office 365 &amp; centro conformità consente di concedere le autorizzazioni agli utenti che conformità attività quali la gestione dei dispositivi, prevenzione della perdita di dati, eDiscovery, conservazione e così via. Questi utenti possono eseguire solo le attività che in modo esplicito concedere loro l'accesso a. Per la protezione dall'accesso di &amp; centro conformità, gli utenti devono essere un amministratore globale di Office 365 oppure membro di uno o più protezione &amp; gruppi di ruoli centro conformità.
  
Le autorizzazioni di sicurezza &amp; centro conformità basati sul modello di autorizzazioni di ruolo basato su accesso controllo (RBAC). Questo è lo stesso modello di autorizzazioni utilizzato da Exchange, pertanto se si ha familiarità con Exchange, concessione di autorizzazioni di sicurezza &amp; centro conformità è molto simile. È importante ricordare, tuttavia, tale ruolo Exchange gruppi e sicurezza &amp; non condividono i gruppi di ruoli centro conformità autorizzazioni o appartenenze. Entrambi dispongono di un gruppo di ruoli Gestione organizzazione, non sono uguali. Le autorizzazioni che concesse e i membri dei gruppi di ruolo, sono diversi. Non esiste un elenco di sicurezza &amp; gruppi di ruoli centro conformità riportata di seguito.
  
![Autorizzazioni di pagina in Office 365 Security &amp; centro conformità](media/992c20ca-e82e-497c-9c8d-6fab212deb80.png)
  
## <a name="relationship-of-members-roles-and-role-groups"></a>Relazione tra membri, ruoli e gruppi di ruoli

Un **ruolo** consente di concedere autorizzazioni per eseguire una serie di attività; ad esempio, il ruolo Gestione dei casi consente agli utenti di utilizzare i casi di eDiscovery. 
  
Un **gruppo di ruoli** è un set di ruoli che consente di eseguire il proprio lavoro tra la sicurezza &amp; centro conformità; ad esempio, il gruppo di ruoli amministratore conformità include i ruoli per la gestione dei Case, ricerca contenuto e configurazione organizzazione (oltre ad altri) dal momento che un utente che è un amministratore di conformità è necessarie le autorizzazioni per le attività per il loro lavoro. 
  
La sicurezza &amp; centro conformità include i gruppi di ruoli predefinito per le attività e le funzioni che è necessario assegnare agli utenti di più comuni. È consigliabile semplicemente aggiungendo singoli utenti come **membri** a gruppi di ruolo predefinito. 
  
![Diagramma che mostra la relazione tra gruppi di ruoli e ruoli e membri](media/2a16d200-968c-4755-98ec-f1862d58cb8b.png)
  
È possibile modificare o eliminare i gruppi di ruoli esistente, ma non raccomandiamo questa. Invece di modificare un gruppo di ruoli predefinito, si può copiarlo, modificarlo e quindi salvarlo con un nome diverso.
  
## <a name="permissions-needed-to-use-features-in-the-security-amp-compliance-center"></a>Autorizzazioni necessarie per utilizzare le funzionalità di protezione &amp; centro conformità

Nella tabella seguente sono elencati i gruppi di ruoli predefiniti disponibili in sicurezza &amp; centro conformità. Per concedere autorizzazioni a un utente di eseguire un'attività di conformità, aggiungerli alla protezione appropriata &amp; gruppo di ruoli centro conformità.
  
Gestione delle autorizzazioni di sicurezza &amp; centro conformità solo offre agli utenti l'accesso alle funzionalità di conformità disponibili all'interno della protezione &amp; centro conformità stesso. Se si desidera concedere le autorizzazioni per altre funzionalità di conformità che non sono in sicurezza &amp; centro conformità, ad esempio le regole di trasporto di Exchange, è necessario utilizzare l'interfaccia di amministrazione di Exchange.
  
Per informazioni su come concedere l'accesso alla protezione &amp; centro conformità, check-out [fornire agli utenti l'accesso all'interfaccia di amministrazione di Office 365 conformità](grant-access-to-the-security-and-compliance-center.md).
  
|**Gruppo di ruoli**|**Descrizione**|
|:-----|:-----|
|**Amministratore di conformità** <sup>1</sup> <br/> |I membri possono gestire le impostazioni per la gestione dei dispositivi, prevenzione della perdita di dati, report e archiviazione.  <br/> |
|**Gestione di eDiscovery** <br/> | I membri possono eseguire ricerche e archiviazioni sul posto le cassette postali, siti di SharePoint Online e OneDrive per i percorsi di Business. I membri possono inoltre creare e gestire casi di eDiscovery, aggiungere e rimuovere membri a un caso, creare e modificare ricerche del contenuto associato a un caso e accedere ai dati casi di eDiscovery avanzate di Office 365.<br/><br/>Una ricerca eDiscovery amministratore è un membro del gruppo di ruoli gestione eDiscovery che dispone di autorizzazioni aggiuntivi. Oltre alle attività che possono eseguire una ricerca eDiscovery Manager, un'amministratore di eDiscovery può:<br/><br/>  • Consente di visualizzare tutti i casi di eDiscovery nell'organizzazione.  <br/>  • Gestire un caso eDiscovery dopo aggiungersi come membro del case.  <br/><br/>La differenza principale tra una ricerca eDiscovery Manager e un'amministratore di eDiscovery è di una ricerca eDiscovery dall'amministratore possono accedere a tutti i casi elencate nella pagina **casi di eDiscovery** in sicurezza &amp; centro conformità. Un manager eDiscovery può accedere solo il case che sono creati o di che sono membri.  Per ulteriori informazioni sull'esecuzione di un utente un'amministratore di eDiscovery, vedere [assegnare autorizzazioni di eDiscovery in Office 365 Security &amp; centro conformità](assign-ediscovery-permissions.md).<br/>           |
|**Gestione organizzazione** <sup>1</sup> <br/> |I membri possono controllare le autorizzazioni per accedere alle funzionalità di sicurezza &amp; centro conformità e inoltre gestire le impostazioni per la gestione dei dispositivi, prevenzione della perdita di dati, report e archiviazione.  <br/> Si noti che in modo che un utente che non sia un amministratore globale per visualizzare l'elenco dei dispositivi gestiti da MDM per Office 365 ed eseguire azioni su questi dispositivi, ad esempio ritirare un dispositivo da MDM per Office 365, l'utente deve essere un amministratore di Exchange.  <br/> Gli amministratori globali di Office 365 vengono automaticamente aggiunti come membri di questo gruppo di ruoli.           |
|**Gestione record** <br/> |I membri possono gestire ed eliminare del contenuto dei record.  <br/> |
|**Reviewer** <br/> |I membri possono visualizzare solo l'elenco dei casi nella pagina dei casi eDiscovery per la protezione &amp; centro conformità. Non possono creare, aprire o gestire un caso eDiscovery. Lo scopo principale di questo gruppo consiste nel consentire ai membri di visualizzazione e l'accesso caso i dati di eDiscovery avanzate.  <br/> Questo gruppo di ruoli dispone delle autorizzazioni associate a eDiscovery più restrittive.  <br/> |
|**Amministratore della sicurezza** <br/> |Membri di questo gruppo possono riguardare amministratori tra i servizi, nonché gruppi partner esterni e supporto Microsoft. Per impostazione predefinita, questo gruppo non può essere assegnato qualsiasi ruolo. Tuttavia, che è un membro del ruolo Security Administrators di Azure Active Directory ed eredita le funzionalità di tale ruolo. Per gestire le autorizzazioni in modo centralizzato, apportare modifiche a questo ruolo nell'interfaccia di amministrazione di Azure Active Directory - per ulteriori informazioni, vedere [autorizzazioni di ruolo di amministratore in Azure Active Directory](https://docs.microsoft.com/en-us/azure/active-directory/users-groups-roles/directory-assign-admin-roles). Se si modifica questo gruppo di ruoli di protezione & centro conformità, le modifiche verranno applicate solo al centro conformità & sicurezza e non altri servizi, mentre le modifiche apportate nell'interfaccia di amministrazione di Azure Active Directory interessano tutti i servizi.<br/> Tutte le autorizzazioni di sola lettura del ruolo di lettore di sicurezza, oltre a un numero di autorizzazioni amministrative aggiuntive per gli stessi servizi: Azure Information Protection, Centro protezione di identità, privilegiato Identity Management, servizio di monitoraggio Office 365 Integrità e la protezione di Office 365 &amp; centro conformità.  <br/> |
|**Lettore di sicurezza** <br/> |I membri hanno accesso in sola lettura a un numero di funzionalità di protezione di Centro protezione di identità, gestione delle identità con privilegi, dell'integrità del servizio di monitoraggio Office 365 e sicurezza di Office 365 &amp; centro conformità.  <br/> L'appartenenza al gruppo di ruoli è sincronizzato in tutti i servizi e gestito in modo centralizzato. Membri di questo gruppo possono riguardare amministratori tra i servizi, nonché gruppi partner esterni e supporto Microsoft. Per impostazione predefinita, questo gruppo non può essere assegnato qualsiasi ruolo. Tuttavia, che è un membro del ruolo Security Administrators di Azure Active Directory ed eredita le funzionalità di tale ruolo. Per gestire le autorizzazioni in modo centralizzato, apportare modifiche a questo ruolo nell'interfaccia di amministrazione di Azure Active Directory - per ulteriori informazioni, vedere [autorizzazioni di ruolo di amministratore in Azure Active Directory](https://docs.microsoft.com/en-us/azure/active-directory/users-groups-roles/directory-assign-admin-roles). Se si modifica questo gruppo di ruoli di protezione & centro conformità, le modifiche verranno applicate solo al centro conformità & sicurezza e non altri servizi, mentre le modifiche apportate nell'interfaccia di amministrazione di Azure Active Directory interessano tutti i servizi.<br/> |
|**Utente Service Assurance** <br/> |Membri possono accedere alla sezione assurance di servizio in Office 365 Security &amp; centro conformità. Garanzia di servizio sono disponibili report e i documenti vengono descritte procedure di protezione di Microsoft per i dati dei clienti archiviati in Office 365. Fornisce inoltre rapporti di controllo di terze parti indipendente in Office 365. Per ulteriori informazioni, vedere [Service assurance in Office 365 Security &amp; centro conformità](http://go.microsoft.com/fwlink/p/?LinkID=717765).<br/> |
|**Revisione supervisione** <br/> |I membri possono creare e gestire i criteri che definiscono quali comunicazioni sono soggetti a revisione in un'organizzazione. Per ulteriori informazioni, vedere [Configure supervisione esaminare i criteri per l'organizzazione](configure-supervision-policies.md).<br/> |
   
> [!NOTE]
> <sup>1</sup> questo gruppo di ruoli non assegna i membri delle autorizzazioni necessarie per cercare il Registro di controllo di Office 365 o per utilizzare i report che possono includere dati di Exchange, ad esempio i rapporti DLP o degli strumenti di analisi. Per cercare il Registro di controllo o per visualizzare tutti i report, un utente deve disporre delle autorizzazioni in Exchange Online. Ciò avviene perché il cmdlet sottostante utilizzato per cercare il Registro di controllo è un cmdlet di Exchange Online. Gli amministratori globali di Office 365 possono cercare il Registro di controllo e visualizzare tutti i report perché sta automaticamente aggiunti come membri del gruppo di ruoli Gestione organizzazione di Exchange Online. Per ulteriori informazioni, vedere [nel Registro di controllo di ricerca in Office 365 Security &amp; centro conformità](https://go.microsoft.com/fwlink/p/?LinkID=708432). 
  

