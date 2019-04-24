---
title: Fornire agli utenti l'accesso al centro sicurezza &amp; e conformità di Office 365
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: ''
ms.audience: Admin
ms.topic: article
f1_keywords:
- ms.o365.cc.PermissionsHelp
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MET150
ms.assetid: 2cfce2c8-20c5-47f9-afc4-24b059c1bd76
description: Gli utenti devono disporre delle autorizzazioni per il Centro sicurezza &amp; e conformità di Office 365 prima di poter gestire qualsiasi funzionalità di sicurezza o conformità.
ms.openlocfilehash: 08b3781ceb48b9a8d5933a075106d7bd3b9ab17d
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "32253970"
---
# <a name="give-users-access-to-the-office-365-security-amp-compliance-center"></a>Fornire agli utenti l'accesso al centro sicurezza &amp; e conformità di Office 365

Gli utenti devono disporre delle autorizzazioni per il Centro sicurezza &amp; e conformità di Office 365 prima di poter gestire qualsiasi funzionalità di sicurezza o conformità. In qualità di amministratore globale di Office 365 o membro del gruppo di ruoli OrganizationManagement nel &amp; Centro sicurezza e conformità, è possibile concedere queste autorizzazioni agli utenti. Gli utenti potranno solo gestire le funzionalità di sicurezza o conformità per le quali è stato concesso loro l'accesso. 
  
Per ulteriori informazioni sulle diverse autorizzazioni che è possibile assegnare agli utenti nel centro sicurezza &amp; e conformità, vedere [autorizzazioni nel centro sicurezza &amp; e conformità di Office 365](permissions-in-the-security-and-compliance-center.md).
  
## <a name="what-do-you-need-to-know-before-you-begin"></a>Che cosa è necessario sapere prima di iniziare

- Per completare la procedura descritta in questo articolo, è necessario essere un amministratore globale di Office 365 o un membro &amp; del gruppo di ruoli OrganizationManagement nel centro sicurezza e conformità.
    
- I gruppi di ruoli per &amp; il Centro sicurezza e conformità potrebbero avere nomi simili ai gruppi di ruoli in Exchange Online, ma non sono gli stessi. 
    
- Le appartenenze ai gruppi di ruoli non sono condivise tra Exchange &amp; online e il Centro sicurezza e conformità.
    
## <a name="use-the-office-365-admin-center-to-give-another-user-access-to-the-security-amp-compliance-center"></a>Utilizzare l'interfaccia di amministrazione di Office 365 per consentire a un altro utente &amp; di accedere al centro sicurezza e conformità

1. [Accedere a Office 365 e passare all'interfaccia di amministrazione](https://go.microsoft.com/fwlink/p/?LinkId=525275).
    
2. Nell'interfaccia di amministrazione di Office 365 aprire interfaccia di **Amministrazione** e quindi fare clic su **conformità di sicurezza &amp; **. 
    
3. Nel centro sicurezza &amp; e conformità, accedere a **autorizzazioni**.
    
4. Nell'elenco scegliere il gruppo di ruoli a cui si desidera aggiungere l'utente e fare clic su **modifica** ![icona](media/O365_MDM_CreatePolicy_EditIcon.gif)modifica.
    
5. Nella pagina delle proprietà del gruppo di ruoli in **membri**fare ****![clic su Aggiungi](media/ITPro-EAC-AddIcon.gif) icona e selezionare il nome dell'utente (o degli utenti) che si desidera aggiungere. 
    
6. Dopo aver selezionato tutti gli utenti che si desidera aggiungere al gruppo di ruoli, fare clic su **Aggiungi\> ** e quindi su **OK**.
    
7. Fare clic su **Salva** per salvare le modifiche al gruppo di ruoli. 
    
### <a name="how-do-you-know-this-worked"></a>Come verificare se l'operazione ha avuto esito positivo?

1. Nel centro sicurezza &amp; e conformità, accedere a **autorizzazioni**.
    
2. Nell'elenco, selezionare il gruppo di ruoli per visualizzare i membri.
    
3. A destra, nei dettagli del gruppo di ruoli, è possibile visualizzare i membri del gruppo di ruoli.
    
## <a name="use-powershell-to-give-another-user-access-to-the-security-amp-compliance-center"></a>Utilizzo di PowerShell per concedere a un altro utente l' &amp; accesso al centro sicurezza e conformità

1. [Connettersi a Office 365 Security _AMP_ Compliance Center PowerShell](https://docs.microsoft.com/en-us/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps).
    
2. Usa il comando **Add-RoleGroupMember** per aggiungere un utente al ruolo Gestione organizzazione, come mostrato nell'esempio seguente. 
    
  ```
  Add-RoleGroupMember -Identity "OrganizationManagement" -Member MatildaS
  
  ```

 **Parametri**
  
- _-Identity_ è il gruppo di ruoli al quale aggiungere un membro. 
    
- _Member_ è la cassetta postale, il gruppo di protezione universale (USG) o il computer da aggiungere al gruppo di ruoli. Puoi specificare solo un membro per volta. 
    
Per informazioni dettagliate sulla sintassi e sui parametri, vedere [Add-RoleGroupMember](https://go.microsoft.com/fwlink/p/?LinkId=510859).
  
### <a name="how-do-you-know-this-worked"></a>Come verificare se l'operazione ha avuto esito positivo

Per verificare di aver concesso agli utenti l'accesso al centro &amp; sicurezza e conformità, utilizzare il cmdlet **Get-RoleGroupMember** per visualizzare i membri del gruppo di ruoli Gestione organizzazione, come illustrato nell'esempio seguente. 
  
```
Get-RoleGroupMember -Identity "OrganizationManagement"

```

Per informazioni dettagliate sulla sintassi e sui parametri, vedere [Get-RoleGroupMember](https://go.microsoft.com/fwlink/p/?LinkId=510860).
  

