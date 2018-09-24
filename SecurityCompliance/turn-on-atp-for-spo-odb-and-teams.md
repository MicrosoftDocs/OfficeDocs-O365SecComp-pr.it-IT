---
title: Attiva per SharePoint, OneDrive e team di Microsoft Office 365 degli strumenti di analisi
ms.author: derng
author: derng
manager: laurawi
ms.date: 5/31/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 07e76024-0c80-40dc-8c48-1dd0d0f863cb
description: Informazioni su come attivare degli strumenti di analisi di SharePoint, OneDrive e team, nonché su come impostare gli avvisi per file rilevati.
ms.openlocfilehash: bb99aee0887f15f065a47d691c59ce47639bdc32
ms.sourcegitcommit: 17c7e18d7d00135b1af40cbea117c9a817a41117
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/24/2018
ms.locfileid: "24972238"
---
# <a name="turn-on-office-365-atp-for-sharepoint-onedrive-and-microsoft-teams"></a>Attiva per SharePoint, OneDrive e team di Microsoft Office 365 degli strumenti di analisi

[Degli strumenti di analisi di Office 365 per SharePoint, OneDrive e team di Microsoft](atp-for-spo-odb-and-teams.md) consente di proteggere l'organizzazione da inavvertitamente condivisione file dannosi. Quando un file dannoso viene rilevato, tale file è bloccato in modo che non possono aprire, copiare, spostare o condividerlo fino a quando non vengono intraprese azioni ulteriormente dal team di protezione dell'organizzazione. Leggere questo articolo per attivare degli strumenti di analisi di SharePoint, OneDrive e team, impostare gli avvisi per essere informati file rilevati e intraprendere le azioni successive. 
  
> [!TIP]
> Per eseguire le attività descritte in questo articolo, è necessario disporre delle autorizzazioni necessarie assegnate in Office 365 e la sicurezza &amp; centro conformità.
  
## <a name="turn-on-atp-for-sharepoint-onedrive-and-microsoft-teams"></a>Attivare ATP per SharePoint, OneDrive e Microsoft Teams

 **Prima di iniziare questa procedura, verificare che la registrazione di controllo è stata abilitata per l'ambiente Office 365**. Questo viene in genere eseguito da un utente che disponga del ruolo registri di controllo assegnato in Exchange Online. Per ulteriori informazioni, vedere [attivare Office 365 ricerca dei registri di controllo attivato o disattivato](turn-audit-log-search-on-or-off.md).
  
1. Un amministratore globale o un amministratore di protezione, passare a [https://protection.office.com](https://protection.office.com)e accedere con l'account di lavoro o della scuola.
    
2. In Office 365 Security &amp; centro conformità, nel riquadro di spostamento a sinistra, in **gestione rischio**, scegliere **criterio** \> **Gli allegati sicuri**.
    
    ![In sicurezza &amp; centro conformità, scegliere gestione rischio \> criteri](media/08849c91-f043-4cd1-a55e-d440c86442f2.png)
  
3. Selezionare **attiva degli strumenti di analisi di SharePoint, OneDrive e team di Microsoft**.
    
    ![Attivare la protezione avanzata minaccia per SharePoint Online, OneDrive for Business e team di Microsoft](media/48cfaace-59cc-4e60-bf86-05ff6b99bdbf.png)
  
4. Fare clic su **Salva**.
    
5. Esaminare (e, nel modo appropriato, modifica) [criteri gli allegati sicuri](set-up-atp-safe-attachments-policies.md) e [collegamenti sicuri criteri](set-up-atp-safe-links-policies.md)dell'organizzazione.
    
6. (Scelta consigliata) Come un amministratore globale o un amministratore di SharePoint Online, eseguire il cmdlet **[Set-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant?view=sharepoint-ps)** con il parametro **DisallowInfectedFileDownload** impostato su *true* . <br/><br/>L'impostazione del parametro a blocchi *true* tutte le azioni (ad eccezione di Elimina) per rilevato file. Utenti non possono aprire, spostare, copiare o condividere file rilevati.<br/><br/>L'impostazione del parametro su *false* blocca tutte le azioni ad eccezione di eliminazione e Download. Persone possono scegliere di accettare il rischio e scaricare un file rilevato.<br/><br/>È consigliabile impostare il parametro su *true*. 
   
7. Consentire fino a 30 minuti per le modifiche apportate da distribuire a tutti i centri dati di Office 365.
    
8. (Scelta consigliata) Procedere per impostare gli avvisi per file rilevati.
    
> [!TIP]
> Per ulteriori informazioni sull'utilizzo di PowerShell con Office 365, vedere [gestire Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-with-office-365-powershell). > Per ulteriori informazioni sull'esperienza utente quando viene rilevato un file come dannose, vedere [cosa fare quando un file dannoso viene rilevato in SharePoint Online, OneDrive o team di Microsoft](https://support.office.com/article/01e902ad-a903-4e0f-b093-1e1ac0c37ad2). 
  
## <a name="set-up-alerts-for-detected-files"></a>Configurare gli avvisi per file rilevati

Per ricevere una notifica quando un file in SharePoint Online, OneDrive per Business o Microsoft Teams è stato identificato come moleste, è possibile impostare un avviso.
  
1. In Office 365 Security &amp; centro conformità, selezionare **avvisi** \> **Gestisci avvisi**.
    
2. Scegliere **nuovo criterio di avviso**.
    
3. Specificare un nome per l'avviso. Ad esempio, è possibile digitare file dannosi nelle raccolte.
    
4. Digitare una descrizione dell'avviso. Ad esempio, è possibile digitare notifica all'admins quando vengono rilevati file dannosi in SharePoint Online, OneDrive o Teams Microsoft.
    
5. Nella sezione **Invia avviso se...** , eseguire le operazioni seguenti: 
    
  - Nell'elenco **delle attività** scegliere **malware rilevate nel file**.
    
  - Lasciare vuoto il campo **gli utenti** . 
    
6. Nella sezione **Invia avviso a...** selezionare uno o più gli amministratori globali, gli amministratori di protezione o lettori di sicurezza che devono ricevere una notifica quando viene rilevato un file dannoso. 
    
7. Fare clic su **Salva**.
    
> [!TIP]
> Per ulteriori informazioni sugli avvisi, vedere [consente di creare avvisi attività in Office 365 Security &amp; centro conformità](create-activity-alerts.md). 
  
## <a name="next-steps"></a>Passaggi successivi

- [Informazioni sul file dannosi rilevato in SharePoint, OneDrive o Teams Microsoft](malicious-files-detected-in-spo-odb-or-teams.md)
    
- [Gestire i messaggi in quarantena e i file in qualità di amministratore in Office 365](manage-quarantined-messages-and-files.md)
    
## <a name="related-topics"></a>Argomenti correlati

[Office 365 Advanced Threat Protection](office-365-atp.md)
  
[Visualizzare i report per la protezione rischio avanzate di Office 365](view-reports-for-atp.md)
  
[Le autorizzazioni di sicurezza di Office 365 &amp; centro conformità](permissions-in-the-security-and-compliance-center.md)
  

