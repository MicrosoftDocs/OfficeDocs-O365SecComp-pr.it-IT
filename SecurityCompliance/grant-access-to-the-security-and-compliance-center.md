---
title: Concedere agli utenti l'accesso a Office 365 Security &amp; centro conformità
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 8/18/2017
ms.audience: Admin
ms.topic: article
f1_keywords:
- ms.o365.cc.PermissionsHelp
ms.service: o365-administration
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MET150
ms.assetid: 2cfce2c8-20c5-47f9-afc4-24b059c1bd76
description: Gli utenti devono disporre delle autorizzazioni in Office 365 Security &amp; centro conformità prima che gestiscono le relative funzionalità di conformità o sicurezza.
ms.openlocfilehash: 976c4e21351e352672f3075d0f713e63a634ce42
ms.sourcegitcommit: da4aa7335b577148ecd61e09bbb11039b817b287
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/15/2018
ms.locfileid: "26539108"
---
# <a name="give-users-access-to-the-office-365-security-amp-compliance-center"></a>Concedere agli utenti l'accesso a Office 365 Security &amp; centro conformità

Gli utenti devono disporre delle autorizzazioni in Office 365 Security &amp; centro conformità prima che gestiscono le relative funzionalità di conformità o sicurezza. Un amministratore globale di Office 365 o membro del gruppo di ruoli OrganizationManagement nella protezione &amp; centro conformità, è possibile fornire tali autorizzazioni agli utenti. Solo gli utenti saranno in grado di gestire le funzionalità di conformità o sicurezza dispongano di accesso a. 
  
Per ulteriori informazioni sulle autorizzazioni diverse è possibile fornire agli utenti nella protezione &amp; centro conformità, check-out [autorizzazioni in Office 365 Security &amp; centro conformità](permissions-in-the-security-and-compliance-center.md).
  
## <a name="what-do-you-need-to-know-before-you-begin"></a>Che cosa è necessario sapere prima di iniziare

- È necessario essere un amministratore globale di Office 365 o un membro del gruppo di ruoli OrganizationManagement nella protezione &amp; centro conformità, per completare la procedura descritta in questo articolo.
    
- Gruppi di ruoli per la sicurezza &amp; centro conformità potrebbe essere nomi simili per i gruppi di ruoli in Exchange Online, ma non sono uguali. 
    
- Appartenenze ai gruppi di ruolo non sono condivise tra Exchange Online e la sicurezza &amp; centro conformità.
    
## <a name="use-the-office-365-admin-center-to-give-another-user-access-to-the-security-amp-compliance-center"></a>Utilizzare l'interfaccia di amministrazione di Office 365 per assegnare un altro utente l'accesso alla protezione &amp; centro conformità

1. [Accedere a Office 365 e accedere all'interfaccia di amministrazione](https://go.microsoft.com/fwlink/p/?LinkId=525275).
    
2. Nell'interfaccia di amministrazione di Office 365, aprire **Admin Center** e quindi fare clic su **protezione &amp; conformità**. 
    
3. In sicurezza &amp; centro conformità, accedere alle **autorizzazioni**.
    
4. Nell'elenco scegliere il gruppo di ruoli che si desidera aggiungere l'utente e fare clic su **Modifica** ![sull'icona Modifica](media/O365_MDM_CreatePolicy_EditIcon.gif).
    
5. Nella pagina delle proprietà del gruppo di ruoli in **membri**, fare clic su **Aggiungi**![Aggiungi icona](media/ITPro-EAC-AddIcon.gif) e selezionare il nome dell'utente (o gli utenti) si desidera aggiungere. 
    
6. Se sono state selezionate tutti gli utenti che si desidera aggiungere al gruppo di ruoli, fare clic su **aggiungere-\> ** e quindi **OK**.
    
7. Fare clic su **Salva** per salvare le modifiche al gruppo di ruoli. 
    
### <a name="how-do-you-know-this-worked"></a>Come verificare se l'operazione ha avuto esito positivo

1. In sicurezza &amp; centro conformità, accedere alle **autorizzazioni**.
    
2. Nell'elenco, selezionare il gruppo di ruoli per visualizzare i membri.
    
3. A destra e i dettagli di gruppo di ruolo, è possibile visualizzare i membri del gruppo di ruoli.
    
## <a name="use-powershell-to-give-another-user-access-to-the-security-amp-compliance-center"></a>Utilizzare PowerShell per assegnare un altro utente l'accesso alla protezione &amp; centro conformità

1. [Connettersi a PowerShell centro conformità e sicurezza di Office 365](https://docs.microsoft.com/en-us/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps).
    
2. Usa il comando **Add-RoleGroupMember** per aggiungere un utente al ruolo Gestione organizzazione, come mostrato nell'esempio seguente. 
    
  ```
  Add-RoleGroupMember -Identity "OrganizationManagement" -Member MatildaS
  
  ```

 **Parametri**
  
-  _-Identity_ è il gruppo di ruoli al quale aggiungere un membro. 
    
- - _Membro_ è la cassetta postale, gruppo di protezione universale (USG) o computer da aggiungere al gruppo di ruoli. È possibile specificare un solo membro alla volta. 
    
Per informazioni dettagliate sulla sintassi e sui parametri, vedere [Add-RoleGroupMember](https://go.microsoft.com/fwlink/p/?LinkId=510859).
  
### <a name="how-do-you-know-this-worked"></a>Come verificare se l'operazione ha avuto esito positivo

Per verificare che è stato assegnato agli utenti l'accesso per la protezione &amp; centro conformità, utilizzare il cmdlet **Get-RoleGroupMember** per visualizzare i membri nel gruppo di ruoli Gestione organizzazione, come illustrato nell'esempio seguente. 
  
```
Get-RoleGroupMember -Identity "OrganizationManagement"

```

Per informazioni dettagliate sulla sintassi e sui parametri, vedere [Get-RoleGroupMember](https://go.microsoft.com/fwlink/p/?LinkId=510860).
  

