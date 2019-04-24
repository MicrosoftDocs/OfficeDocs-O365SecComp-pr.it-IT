---
title: Attivazione di Office 365 ATP per SharePoint, OneDrive e Microsoft Teams
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.audience: ITPro
ms.topic: article
ms.date: 02/06/2019
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 07e76024-0c80-40dc-8c48-1dd0d0f863cb
ms.collection:
- M365-security-compliance
description: Informazioni su come abilitare ATP per SharePoint, OneDrive e teams, inclusa la procedura per impostare gli avvisi per i file rilevati.
ms.openlocfilehash: 30eb28bfc5156664656ca1c200f9e999661b3b0c
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "32264300"
---
# <a name="turn-on-office-365-atp-for-sharepoint-onedrive-and-microsoft-teams"></a>Attivazione di Office 365 ATP per SharePoint, OneDrive e Microsoft Teams

[Office 365 ATP per SharePoint, OneDrive e Microsoft teams](atp-for-spo-odb-and-teams.md) protegge l'organizzazione dalla condivisione involontaria di file dannosi. Quando viene rilevato un file dannoso, il file viene bloccato in modo che nessuno possa aprirlo, copiarlo, spostarlo o condividerlo fino a quando non vengono intraprese altre azioni da parte del team di sicurezza dell'organizzazione. Leggere questo articolo per abilitare ATP per SharePoint, OneDrive e teams, impostare gli avvisi per ricevere una notifica sui file rilevati e seguire i passaggi successivi. 
  
Per definire (o modificare) i criteri ATP, è necessario essere assegnati a un ruolo appropriato. Alcuni esempi sono descritti nella tabella seguente:

|Ruolo  |Dove/come assegnato  |
|---------|---------|
|Amministratore globale di Office 365 |Per impostazione predefinita, la persona che si iscrive all'acquisto di Office 365 è un amministratore globale. Per ulteriori informazioni, vedere [informazioni sui ruoli di amministratore di Office 365](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles) .         |
|Amministratore della sicurezza |Interfaccia di amministrazione di Azure Active[https://aad.portal.azure.com](https://aad.portal.azure.com)directory ()|
|Gestione dell'organizzazione di Exchange Online |Interfaccia di amministrazione di[https://outlook.office365.com/ecp](https://outlook.office365.com/ecp)Exchange () <br>oppure <br>  Cmdlet di PowerShell (vedere [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps)) |
  
## <a name="turn-on-atp-for-sharepoint-onedrive-and-microsoft-teams"></a>Attivare ATP per SharePoint, OneDrive e Microsoft Teams

**Prima di iniziare questa procedura, verificare che la registrazione di controllo sia già attiva per l'ambiente Office 365**. Questa operazione viene in genere fatta da una persona a cui è stato assegnato il ruolo registri di controllo in Exchange Online. Per ulteriori informazioni, vedere [attivazione o disattivaZione della ricerca del registro di controllo di Office 365](turn-audit-log-search-on-or-off.md).
  
1. Passare a [https://protection.office.com](https://protection.office.com)e accedere con l'account aziendale o dell'Istituto di istruzione.
    
2. nel centro &amp; sicurezza e conformità di Office 365, nel riquadro di spostamento a sinistra, in **gestione delle minacce**, scegliere **allegati sicuri**per i **criteri** \> . <br/>![Nel centro sicurezza &amp; e conformità scegliere criteri di gestione \> delle minacce](media/08849c91-f043-4cd1-a55e-d440c86442f2.png)
  
3. Selezionare **attiva ATP per SharePoint, OneDrive e Microsoft teams**.<br/>![Abilitare Advanced Threat Protection per SharePoint Online, OneDrive for business e Microsoft Teams](media/48cfaace-59cc-4e60-bf86-05ff6b99bdbf.png)
  
4. Fare clic su **Salva**.
    
5. Rivedere (e, a seconda dei casi, modificare) i [criteri per gli allegati sicuri](set-up-atp-safe-attachments-policies.md) dell'organizzazione e i [criteri collegamenti sicuri](set-up-atp-safe-links-policies.md).
    
6. Consigliato In qualità di amministratore globale o amministratore di SharePoint Online, eseguire il cmdlet **[set-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant?view=sharepoint-ps)** con il parametro **DisallowInfectedFileDownload** impostato su *true*. <br/>
      - L'impostazione del parametro su *true* blocca tutte le azioni (eccetto Delete) per i file rilevati. Gli utenti non possono aprire, spostare, copiare o condividere i file rilevati.
      - Se si imposta il parametro su *false* , vengono bloccate tutte le azioni ad eccezione di Delete e download. Gli utenti possono scegliere di accettare il rischio e scaricare un file rilevato.  
   
7. Consentono fino a 30 minuti affinché le modifiche vengano estese a tutti i datacenter di Office 365.
    
8. Consigliato Procedere alla configurazione degli avvisi per i file rilevati.
    
Per ulteriori informazioni sull'utilizzo di PowerShell con Office 365, vedere [gestione di office 365 con PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-with-office-365-powershell). 

Per ulteriori informazioni sull'esperienza utente quando un file è stato rilevato come dannoso, vedere [cosa fare quando si trova un file dannoso in SharePoint Online, OneDrive o Microsoft teams](https://support.office.com/article/01e902ad-a903-4e0f-b093-1e1ac0c37ad2). 
  
## <a name="set-up-alerts-for-detected-files"></a>Configurare gli avvisi per i file rilevati

Per ricevere una notifica quando un file in SharePoint Online, OneDrive for business o Microsoft teams è stato identificato come dannoso, è possibile impostare un avviso.
  
1. nel [centro sicurezza &amp; e conformità di Office 365](https://protection.office.com)scegliere **avvisi** \> **gestione avvisi**.
    
2. Scegliere **nuovi criteri di avviso**.
    
3. Specificare un nome per l'avviso. Ad esempio, è possibile digitare file dannosi nelle raccolte.
    
4. Digitare una descrizione per l'avviso. Ad esempio, è possibile digitare notifiche agli amministratori quando vengono rilevati file dannosi in SharePoint Online, OneDrive o Microsoft teams.
    
5. Nella sezione **Invia questo avviso quando...** eseguire le operazioni seguenti: 
    
    un. Nell'elenco **attività** scegliere **rilevato malware nel file**.
    
    b. Lasciare vuoto **** il campo Users. 
    
6. Nella sezione **Invia questo avviso a...** selezionare uno o più amministratori globali, amministratori della sicurezza o lettori di sicurezza che dovrebbero ricevere una notifica quando viene rilevato un file dannoso. 
    
7. Fare clic su **Salva**.
    
Per ulteriori informazioni sugli avvisi, vedere [creare avvisi di attività nel centro sicurezza &amp; e conformità di Office 365](create-activity-alerts.md). 
  
## <a name="next-steps"></a>Passaggi successivi

1. [Visualizzare informazioni sui file dannosi rilevati in SharePoint, OneDrive o Microsoft Teams](malicious-files-detected-in-spo-odb-or-teams.md)
    
2. [Gestire i messaggi e i file in quarantena come amministratore in Office 365](manage-quarantined-messages-and-files.md)
    

  

