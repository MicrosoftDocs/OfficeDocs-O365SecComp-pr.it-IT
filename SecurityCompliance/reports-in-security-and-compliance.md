---
title: Rapporti di protezione di Office 365 &amp; centro conformità
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 2/1/2018
ms.audience: Admin
ms.topic: overview
f1_keywords:
- ms.o365.cc.AuditingHelp
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- SPO160
- MOE150
ms.assetid: 7acd33ce-1ec8-49fb-b625-43bac7b58c5a
description: "Utilizzare la protezione di Office 365 &amp; rapporti di centro conformità per ottenere diversi tipi di report per l'organizzazione Exchange Online e SharePoint Online e Azure Active Directory.  "
ms.openlocfilehash: 0b633583e14a18c7cf579d10462cf41714397812
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/27/2018
ms.locfileid: "22530280"
---
# <a name="reports-in-the-office-365-security-amp-compliance-center"></a>Rapporti di protezione di Office 365 &amp; centro conformità

È possibile utilizzare la pagina **Visualizza report** in Office 365 Security &amp; centro conformità per accedere rapidamente ai report di controllo per le organizzazioni di Exchange Online e SharePoint Online. È inoltre possibile accedere Azure Active Directory (AD) utente accesso rapporti, rapporti di attività dell'utente e il controllo di Azure Active Directory accedere dalla pagina **Visualizza report** . Ciò avviene perché la sottoscrizione a Office 365 pagamento include un abbonamento gratuito a Microsoft Azure. La prima volta che si tenta di accedere a questi rapporti Azure, è necessario eseguire un processo di registrazione occasionale. 
  
> [!TIP]
> Per visualizzare altri report sull'attività nella propria organizzazione Office 365, vedere [Rapporti attività nell'interfaccia di amministrazione di Office 365](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263). 
  
 **Prima di iniziare**
  
Sono necessarie le autorizzazioni seguenti per visualizzare i report per la protezione &amp; centro conformità.
  
- È necessario assegnare il ruolo di sicurezza lettore nell'interfaccia di amministrazione di Exchange (EAC) per visualizzare i report per la protezione &amp; centro conformità. Per impostazione predefinita, questo ruolo viene assegnato ai gruppi di ruoli Gestione organizzazione e lettore di sicurezza in EAC.
    
- È necessario assegnare il ruolo di gestione della conformità DLP in sicurezza &amp; centro conformità per visualizzare rapporti DLP (e criteri DLP) per la protezione &amp; centro conformità. Per impostazione predefinita, questo ruolo viene assegnato ai gruppi di ruoli amministratore di conformità, la gestione dell'organizzazione e amministratore della sicurezza della protezione &amp; centro conformità.
    
Inoltre, è necessario essere assegnato il ruolo di prevenzione della perdita di dati di amministrazione di Exchange per visualizzare rapporti DLP (e criteri DLP) in EAC. Per impostazione predefinita, questo ruolo viene assegnato ai gruppi di ruolo Gestione della conformità e la gestione dell'organizzazione in EAC.
  
 **Per aprire la pagina di report di visualizzazione per la protezione &amp; centro conformità:**
  
1. Accedere a [https://protection.office.com/#/viewreports](https://protection.office.com/#/viewreports).
    
2. Accedere a Office 365 utilizzando le credenziali per un account utente nell'organizzazione Office 365.
    
Nella pagina **Visualizza report** , è possibile visualizzare i tipi di report seguenti: 
  
- [Report di controllo in EOP](#auditing-reports)
- [Report revisione supervisione](#supervisory-review-report)
- [Report sulla prevenzione della perdita di dati](#data-loss-prevention-reports)
    
## <a name="auditing-reports"></a>Rapporti di controllo

Nella tabella seguente vengono descritti i report nella sezione **controllo** nella pagina **Visualizza report** nella protezione &amp; centro conformità. 
  
|**Report**|**Descrizione**|
|:-----|:-----|
|**Rapporto Registro di controllo di Office 365** <br/> |È possibile cercare il Registro di controllo di Office 365 per l'attività di amministrazione e utente nell'organizzazione Office 365. Il report contiene le voci utente e amministrazione attività in Exchange Online, SharePoint Online, OneDrive for Business e Azure Active Directory, ovvero il servizio directory per Office 365. Per ulteriori informazioni, vedere [nel Registro di controllo di ricerca in Office 365 Security &amp; centro conformità](search-the-audit-log-in-security-and-compliance.md).<br/> |
|**Report di Azure AD** <br/> |Per cercare insolito sospetti accesso attività o nella propria organizzazione Office 365, è possibile utilizzare accesso attività e i report in Microsoft Azure. È inoltre possibile visualizzare gli eventi nel Registro di controllo Azure Active Directory. Per visualizzare i rapporti in Azure, fare clic su **Azure Active Directory consente di visualizzare report**. Per ulteriori informazioni, vedere:<br/><br/>[Utilizzare la sottoscrizione di Azure Active Directory disponibile in Office 365](use-your-free-azure-ad-subscription-in-office-365.md). <br/> Consente di [visualizzare i report di utilizzo e l'accesso](http://go.microsoft.com/fwlink/p/?LinkId=506902).  <br/> |
|**Report sui controlli di Exchange** <br/> | È possibile utilizzare la funzionalità di controllo in Office 365 per tenere traccia delle modifiche apportate alla configurazione di Exchange Online da parte degli amministratori dell'organizzazione. Modifiche apportate all'organizzazione Exchange Online da un amministratore del data center Microsoft o da un amministratore delegato inoltre vengono registrate. Exchange Online, controllo dell'amministratore per la registrazione è abilitata per impostazione predefinita, in modo che non è necessario eseguire alcuna operazione per attivarlo. Exchange Online offre anche la registrazione che consentono di tenere traccia degli accessi alle cassette postali da un utente diverso da proprietario della cassetta postale di controllo delle cassette postali. È necessario abilitare la registrazione per ciascuna cassetta postale che si desidera tenere traccia degli accessi utente non proprietario di controllo delle cassette postali.<br/>  Registrazione di controllo per amministratori e delle cassette postali, è possibile eseguire report di controllo per visualizzare le voci del Registro di controllo. È inoltre possibile esportare cassette postali e amministrazione registri di controllo, vengono inviati entro 24 ore in un file XML che è collegato al messaggio di posta elettronica.<br/><br/>Per ulteriori informazioni sull'esportazione dei registri di controllo, vedere:  <br/><br/> [Esportare i log di controllo delle cassette postali](http://go.microsoft.com/fwlink/p/?LinkID=404104) <br/> [Visualizzare ed esportare il Registro di controllo amministrazione datacenter](http://go.microsoft.com/fwlink/p/?LinkId=404109) <br/> [Ricerca delle modifiche al gruppo di ruoli o i registri di controllo dell'amministratore](http://go.microsoft.com/fwlink/p/?LinkId=404105) <br/>   [Rapporti di controllo di Exchange](http://go.microsoft.com/fwlink/p/?LinkID=395232).  <br/> |
   
## <a name="supervisory-review-report"></a>Report revisione supervisione

Con il rapporto di supervisione revisione, è possibile visualizzare lo stato di tutti i criteri di supervisione revisione all'interno dell'organizzazione. Per ulteriori informazioni, vedere [Configure supervisione esaminare i criteri per l'organizzazione](configure-supervision-policies.md).
  
## <a name="data-loss-prevention-reports"></a>Report sulla prevenzione della perdita di dati

Prevenzione della perdita di dati (DLP) report contiene informazioni sui criteri DLP e le regole applicate al contenuto contengono dati riservati nella propria organizzazione Office 365. È inoltre possibile configurare il report per visualizzare informazioni sulle azioni DLP che sono stati in base al criterio DLP e regole. Per ulteriori informazioni, vedere [visualizzare il report per la prevenzione della perdita di dati](view-the-dlp-reports.md).
