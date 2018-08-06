---
title: Gestione di gruppi in EOP
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 11/17/2014
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
ms.assetid: 212e68ac-6330-47e9-a169-6cf5e2f21e13
description: È possibile utilizzare Exchange Online Protection (EOP) per creare gruppi abilitati alla posta elettronica per un'organizzazione di Exchange. È inoltre possibile utilizzare EOP per definire o aggiornare le proprietà di gruppo che specificano l'appartenenza, indirizzi di posta elettronica e altri aspetti dei gruppi.
ms.openlocfilehash: 744a28d2003496650e7350108797cc5cc4eaad4f
ms.sourcegitcommit: 22bca85c3c6d946083d3784f72e886c068d49f4a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/06/2018
ms.locfileid: "22026343"
---
# <a name="manage-groups-in-eop"></a>Gestione di gruppi in EOP

 È possibile utilizzare Exchange Online Protection (EOP) per creare gruppi abilitati alla posta elettronica per un'organizzazione di Exchange. È inoltre possibile utilizzare EOP per definire o aggiornare le proprietà del gruppo che specificano l'appartenenza, gli indirizzi di posta elettronica e altri aspetti dei gruppi. È possibile creare gruppi di distribuzione e gruppi di sicurezza, a seconda delle proprie esigenze. È possibile creare tali gruppi utilizzando l'interfaccia di amministrazione di Exchange o tramite Windows PowerShell remoto. 
  
## <a name="types-of-mail-enabled-groups"></a>Tipi di gruppi abilitati alla posta elettronica.

È possibile creare due tipi di gruppi per la propria organizzazione di Exchange:
  
- [Creare un gruppo nell'interfaccia di amministrazione di Exchange](manage-groups-in-eop.md) (detti anche gruppi di distribuzione) sono raccolte di utenti di posta elettronica, come ad esempio team o altri gruppi ad hoc, che devono ricevere o inviare posta elettronica relativa a una comune area di interesse. I gruppi di distribuzione servono esclusivamente per la distribuzione di messaggi di posta elettronica. In EOP, un gruppo di distribuzione fa riferimento a qualsiasi gruppo abilitato alla posta elettronica, a prescindere che abbia o meno un contesto di sicurezza.
    
- [Modificare o rimuovere un gruppo nell'interfaccia di amministrazione di Exchange](manage-groups-in-eop.md) (noti anche come gruppi di sicurezza) sono raccolte di utenti di posta elettronica che devono accedere alle autorizzazioni dei ruoli di amministratore. Ad esempio, si potrebbe voler assegnare a un gruppo specifico di utenti autorizzazioni di ruolo di amministratore in modo che possano configurare impostazioni di protezione dalla posta indesiderata e antimalware.
    
    > [!NOTE]
    > Per impostazione predefinita, tutti i nuovi gruppi di sicurezza abilitati alla posta elettronica richiedono l'autenticazione di tutti i mittenti. Questo impedisce ai mittenti esterni di inviare messaggi ai gruppi di sicurezza abilitati alla posta elettronica. 
  
## <a name="before-you-begin"></a>Informazioni preliminari

- Per eseguire queste procedure, è necessario disporre delle autorizzazioni appropriate. Per sapere quali autorizzazioni sono necessarie, vedere "Gruppi di distribuzione e sicurezza" nell'argomento [Autorizzazioni di funzionalità in EOP](feature-permissions-in-eop.md). 
    
- Tenere presente che quando si creano e gestiscono i gruppi tramite cmdlet di PowerShell remoto, è possibile che si verifichino limitazioni.
    
- Questo cmdlet utilizza un metodo di elaborazione batch che genera un ritardo di qualche minuto nella propagazione prima che i risultati del cmdlet siano visibili.
    
- Per informazioni su come utilizzare Windows PowerShell per la connessione a Exchange Online Protection, vedere [Connessione a Exchange Online Protection tramite PowerShell remota](http://technet.microsoft.com/library/054e0fd7-d465-4572-93f8-a00a9136e4d1.aspx).
    
- Per informazioni sui tasti di scelta rapida che è possibile utilizzare con le procedure in questo argomento, vedere **Keyboard shortcuts in Exchange 2013**.
    
> [!TIP]
> Problemi? È possibile richiedere supporto nei forum di Exchange. I forum sono disponibili sui seguenti siti: [Exchange Server](https://go.microsoft.com/fwlink/p/?linkId=60612),[Exchange Online](https://go.microsoft.com/fwlink/p/?linkId=267542) o [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351). 
  
## <a name="create-a-group-in-the-eac"></a>Creare un gruppo nell'interfaccia di amministrazione di Exchange

1. Nell'interfaccia di amministrazione di Exchange, andare a **Destinatari** \> **Gruppi**.
    
2. Fare clic su **Nuovo**![Icona Aggiungi](../media/ITPro-EAC-AddIcon.png), quindi fare clic su **Gruppo di distribuzione** o **Gruppo di sicurezza**, in base alle proprie esigenze. Vedere [Tipi di gruppi abilitati alla posta elettronica.](manage-groups-in-eop.md) per le differenze. 
    
3. Nella pagina **Nuovo gruppo di distribuzione** o **Nuovo gruppo di sicurezza**, completare i seguenti campi: 
    
  - **Nome visualizzato** Inserire un nome visualizzato univoco per la propria organizzazione e significativo per gli utenti EOP. Il nome visualizzato è obbligatorio. 
    
  - **Alias** Digitare un alias del gruppo contenente massimo 64 caratteri, esclusivo per l'organizzazione. Gli utenti EOP digitano l'alias nel campo A: di un messaggio di posta elettronica. L'alias si risolve nel nome visualizzato del gruppo. Se si modifica l'alias, verrà modificato anche l'indirizzo SMTP primario del gruppo in modo che contenga il nuovo alias. L'alias è obbligatorio. 
    
  - **Descrizione** Inserire una descrizione del gruppo in modo che le persone possano conoscere gli scopi del gruppo. 
    
  - **Proprietari** Per impostazione predefinita, l'utente che crea il gruppo ne diventa proprietario. È possibile aggiungere un proprietario facendo clic su **Aggiungi**![Icona Aggiungi](../media/ITPro-EAC-AddIcon.png). Ogni gruppo deve presentare almeno un proprietario.
    
    > [!NOTE]
    > I proprietari non sono tenuti a essere membri del gruppo. 
  
  - **Membri** Utilizzare questa sezione per aggiungere membri del gruppo e specificare se è necessaria l'approvazione per unirsi al gruppo o abbandonarlo. Per aggiungere membri al gruppo, fare clic su **Aggiungi**![Icona Aggiungi](../media/ITPro-EAC-AddIcon.png).
    
4. Scegliere **OK** per tornare alla pagina originale. 
    
5. Al termine, scegliere **Salva** per creare il gruppo. Il nuovo gruppo verrà visualizzato nell'elenco dei gruppi. 
    
## <a name="edit-or-remove-a-group-in-the-eac"></a>Modificare o rimuovere un gruppo nell'interfaccia di amministrazione di Exchange

1. Nell'interfaccia di amministrazione di Exchange, accedere a **Destinatari** \> **Gruppi**.
    
2. Effettuare una delle operazioni seguenti:
    
  - Per modificare un gruppo: Nell'elenco dei gruppi, fare clic sul gruppo di distribuzione o sicurezza da visualizzare o modificare, quindi fare clic su **Modifica**![Icona Modifica](../media/ITPro-EAC-EditIcon.png). È possibile aggiornare le impostazioni generali, aggiungere o rimuovere proprietari del gruppo e aggiungere o rimuovere membri del gruppo, secondo necessità.
    
  - Per rimuovere un gruppo: Selezionare il gruppo e fare clic su **Rimuovi**![Icona Rimuovi](../media/ITPro-EAC-RemoveIcon.png).
    
3. Dopo avere apportato tutte le modifiche, fare clic su **Salva**.
    
## <a name="create-edit-or-remove-a-group-using-remote-windows-powershell"></a>Creare, modificare o rimuovere un gruppo utilizzando Windows PowerShell remoto

In questa sezione vengono fornite informazioni sulla creazione di gruppi e sulla modifica delle loro proprietà tramite Windows PowerShell remoto. Inoltre, viene illustrato come rimuovere un gruppo esistente. 
  
 **Per creare un gruppo tramite Windows PowerShell remoto**
  
In questo esempio viene utilizzato il cmdlet [New-EOPDistributionGroup](http://technet.microsoft.com/library/4610dfe5-fca8-4ba8-be3c-535d1753e0f4.aspx) per creare un gruppo di distribuzione con alias itadmin e nome Amministratori IT. Inoltre, vengono aggiunti utenti come membri del gruppo. 
  
```
New-EOPDistributionGroup -Type "Distribution" -Name "IT Administrators" -Alias itadmin -Members @("Member1","Member2","Member3") -ManagedBy "Member1"

```

Per creare un gruppo di sicurezza invece di un gruppo di distribuzione, specificare  `-Type "Security"`. 
  
Per verificare che il gruppo Amministratori IT sia stato creato correttamente, eseguire il cmdlet [Get-Recipient](http://technet.microsoft.com/library/2ce6250f-0ad3-4b29-870c-e1d6e1e154bc.aspx) per visualizzare le informazioni relative al nuovo gruppo: 
  
```
Get-Recipient "IT Administrators" | Format-List

```

Per visualizzare un elenco di membri del gruppo, eseguire il cmdlet [Get-DistributionGroupMember](http://technet.microsoft.com/library/15c71bc5-4246-44ac-8b34-8ccd585294b5.aspx) nel modo riportato di seguito: 
  
```
Get-DistributionGroupMember "IT Administrators"

```

Per visualizzare un elenco completo di tutti i gruppi, eseguire il cmdlet [Get-Recipient](http://technet.microsoft.com/library/2ce6250f-0ad3-4b29-870c-e1d6e1e154bc.aspx) nel modo riportato di seguito: 
  
```
Get-Recipient -RecipientType "MailUniversalDistributionGroup" | FT | more

```

 **Modificare le proprietà di un gruppo utilizzando Windows PowerShell remoto**
  
Utilizzare i cmdlet [Get-Recipient](http://technet.microsoft.com/library/2ce6250f-0ad3-4b29-870c-e1d6e1e154bc.aspx) e [Set-EOPDistributionGroup](http://technet.microsoft.com/library/689a66c5-a524-4870-88f3-091fd6eae3b7.aspx) per visualizzare e modificare le proprietà dei gruppi. Un vantaggio dell'utilizzo di PowerShell remoto invece dell'interfaccia di amministrazione di Excel consiste nella possibilità di modificare le proprietà di più gruppi. 
  
Di seguito, sono riportati alcuni esempi relativi all'utilizzo di Windows PowerShell per modificare le proprietà del gruppo.
  
In questo esempio, si utilizza il cmdlet [Set-EOPDistributionGroup](http://technet.microsoft.com/library/689a66c5-a524-4870-88f3-091fd6eae3b7.aspx) per modificare l'indirizzo SMTP principale (denominato anche indirizzo di risposta) del gruppo Seattle Employees in sea.employees@contoso.com. 
  
```
Set-EOPDistributionGroup "Seattle Employees" -PrimarysmptAddress "sea.employees@contoso.com"

```

Per verificare di aver modificato correttamente le proprietà di un gruppo, utilizzare il cmdlet [Get-Recipient](http://technet.microsoft.com/library/2ce6250f-0ad3-4b29-870c-e1d6e1e154bc.aspx) per verificare le modifiche. Uno dei vantaggi offerti dall'utilizzo di PowerShell remoto è la possibilità di visualizzare più proprietà per più gruppi. Nell'esempio precedente, in cui è stato modificato il gruppo di indirizzi SMTP, eseguire questo comando per verificare il nuovo valore: 
  
```
Get-Recipient "Seattle Employees" | FL "PrimarySmtpAddress"

```

In questo esempio, viene utilizzato il cmdlet [Update-EOPDistributionGroupMember](http://technet.microsoft.com/library/a6d4f790-1b94-42f8-af6f-fa79c504d8ec.aspx) per aggiornare tutti i membri del gruppo Seattle Employees. Utilizzare una virgola per tutti i membri. 
  
```
Update-EOPDistributionGroupMember -Identity "Seattle Employees" -Members @("Member1","Member2","Member3","Member4","Member5")

```

Per visualizzare un elenco di tutti i membri del gruppo Seattle Employees, utilizzare il cmdlet [Get-DistributionGroupMember](http://technet.microsoft.com/library/15c71bc5-4246-44ac-8b34-8ccd585294b5.aspx) nel modo riportato di seguito: 
  
```
Get-DistributionGroupMember "Seattle Employees"

```

 **Per rimuovere un gruppo tramite Windows PowerShell remoto**
  
In questo esempio viene utilizzato il cmdlet [Remove-EOPDistributionGroup](http://technet.microsoft.com/library/a17b1307-3187-40b0-a438-c7b35a34c002.aspx) per rimuovere un gruppo di distribuzione denominato Amministratori IT. 
  
```
Remove-EOPDistributionGroup -Identity "IT Administrators" 

```

Per verificare che il gruppo è stato rimosso, eseguire il cmdlet [Get-Recipient](http://technet.microsoft.com/library/2ce6250f-0ad3-4b29-870c-e1d6e1e154bc.aspx) nel modo seguente, quindi confermare che l'eliminazione del gruppo (in questo caso, "Amministratori IT"). 
  
```
Get-Recipient -RecipientType "MailUniversalDistributionGroup"

```


