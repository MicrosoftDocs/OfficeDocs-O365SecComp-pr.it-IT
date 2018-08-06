---
title: Gestione utenti di posta in EOP
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 12/9/2016
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
ms.assetid: 4bfaf2ab-e633-4227-8bde-effefb41a3db
description: La definizione degli utenti di posta è una parte importante della gestione del servizio Exchange Online Protection (EOP).
ms.openlocfilehash: e985adf5659b50cf567ea798a092f809d77ca470
ms.sourcegitcommit: 22bca85c3c6d946083d3784f72e886c068d49f4a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/06/2018
ms.locfileid: "22027393"
---
# <a name="manage-mail-users-in-eop"></a>Gestione utenti di posta in EOP

La definizione degli utenti di posta è una parte importante della gestione del servizio Exchange Online Protection (EOP). In EOP è possibile gestire gli utenti in diversi modi.
  
- Utilizzare la sincronizzazione delle directory per gestire gli utenti di posta elettronica: se la società dispone di account utente esistente in un ambiente Active Directory locale, è possibile sincronizzare gli account per Azure Active Directory (AD), dove viene archiviata una copia degli account nel cloud. Quando si sincronizzano gli account utente esistente di Azure Active Directory, è possibile visualizzare gli utenti nel riquadro dei **destinatari** dell'interfaccia di amministrazione di Exchange (EAC). È consigliabile utilizzare la sincronizzazione delle directory. 
    
- Utilizzare il valore EAC per gestire gli utenti di posta: aggiungere e gestire gli utenti di posta direttamente in EAC. Si tratta del modo più semplice per aggiungere utenti di posta elettronica ed è utile per aggiungere un utente alla volta.
    
- Utilizzare Windows PowerShell remoto per gestire gli utenti di posta elettronica: aggiungere e gestire utenti di posta elettronica eseguendo Windows PowerShell remoto. Questo metodo è utile per aggiungere più record e creare script.
    
> [!NOTE]
> È possibile aggiungere utenti nell'interfaccia di amministrazione di Office 365, ma questi utenti non possono essere usati come destinatari di posta elettronica. 
  
## <a name="before-you-begin"></a>Informazioni preliminari

- Le procedure descritte in questo argomento richiedono autorizzazioni specifiche. Vedere ciascuna procedura per le informazioni sulle autorizzazioni necessarie.
    
- Per informazioni sui tasti di scelta rapida che è possibile utilizzare con le procedure in questo argomento, vedere **Tasti di scelta rapida nell'interfaccia di amministrazione di Exchange**.
    
> [!TIP]
> Problemi? È possibile richiedere supporto nei forum di Exchange. I forum sono disponibili sui seguenti siti: [Exchange Server](https://go.microsoft.com/fwlink/p/?linkId=60612),[Exchange Online](https://go.microsoft.com/fwlink/p/?linkId=267542) o [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351). 
  
## <a name="use-directory-synchronization-to-manage-mail-users"></a>Utilizzare la sincronizzazione della directory per gestire gli utenti di posta

Nella presente sezione vengono fornite informazioni sulla gestione degli utenti di posta elettronica utilizzando la sincronizzazione della directory.
  
> [!IMPORTANT]
> Se si utilizza la sincronizzazione della directory per gestire i destinatari, è comunque possibile aggiungere e gestire gli utenti nell'interfaccia di amministrazione di Office 365. Tuttavia questi non verranno sincronizzati con Active Directory in locale poiché la sincronizzazione della directory sincronizza solamente i destinatari dall'Active Directory locale al cloud. 
  
> [!TIP]
>  Si consiglia di utilizzare la sincronizzazione della directory con le seguenti funzionalità: > **Elenchi di mittenti attendibili e bloccati di Outlook**: se sincronizzati con il servizio, questi elenchi avranno la precedenza sul filtro di protezione da posta indesiderata del servizio. Ciò consente agli utenti di gestire i propri elenchi di utenti attendibili o bloccati a livello di organizzazione o a livello di singolo utente. > **Directory Based Edge Blocking (DBEB)**: per ulteriori informazioni su DBEB, vedere [Use Directory Based Edge Blocking to Reject Messages Sent to Invalid Recipients](http://technet.microsoft.com/library/ca7b7416-92ed-40ad-abdb-695be46ea2e4.aspx). > **Quarantena posta indesiderata utente finale**: per accedere alla quarantena posta indesiderata utente finale, gli utenti finali devono possedere un ID e una password per utenti di Office 365 validi. I clienti EOP che proteggono le cassette postali locali devono essere utenti di posta elettronica validi. > **Regole di trasporto**: quando si utilizza la sincronizzazione delle directory, gli utenti e i gruppi di Active Directory esistenti vengono caricati automaticamente nel cloud;ciò consente di creare regole di trasporto destinate a utenti specifici e/o gruppi senza doverli aggiungere manualmente tramite la EAC o la sessione remota di Windows PowerShell. Si noti che non è possibile sincronizzare i [gruppi di distribuzione dinamici](https://go.microsoft.com/fwlink/?LinkId=507569) tramite la sincronizzazione delle directory. 
  
 **Informazioni preliminari**
  
Ottenere le autorizzazioni necessarie e preparare la sincronizzazione della directory, come descritto in [Preparazione della sincronizzazione della directory](https://go.microsoft.com/fwlink/p/?LinkId=308908).
  
### <a name="to-synchronize-user-directories"></a>Per sincronizzare le directory degli utenti

1. Attivare la sincronizzazione della directory, come descritto in [Attivare la sincronizzazione della directory](https://go.microsoft.com/fwlink/p/?LinkId=308909).
    
2. Impostare il computer per la sincronizzazione della directory, come descritto in [Impostare il computer per la sincronizzazione della directory](http://go.microsoft.com/fwlink/p/?LinkId=308911).
    
3. Sincronizzare le directory, come descritto in [Utilizzare Configurazione guidata per sincronizzare le directory](http://go.microsoft.com/fwlink/?LinkId=308912).
    
    > [!IMPORTANT]
    > Al termine della Configurazione guidata dello strumento di sincronizzazione di Azure Active Directory, viene creato l'account **MSOL_AD_SYNC** nella foresta Active Directory. Tale account viene utilizzato per leggere e sincronizzare le informazioni dell'Active Directory locale. Per un corretto funzionamento della sincronizzazione della directory, assicurarsi che TCP 443 sul server di sincronizzazione della directory locale sia aperto. 
  
4. Attivare gli utenti sincronizzati, come descritto in [Attiva utenti sincronizzati](http://go.microsoft.com/fwlink/p/?LinkId=308913).
    
5. Gestione della sincronizzazione della directory, come descritto in [Gestione della sincronizzazione della directory](http://go.microsoft.com/fwlink/p/?LinkId=308915).
    
6. Verificare che EOP sia sincronizzato correttamente. In EAC, andare a **Destinatari** \> **Contatti** e verificare che l'elenco dei destinatari sia stato sincronizzato correttamente dall'ambiente in locale. 
    
## <a name="use-the-eac-to-manage-mail-users"></a>Utilizzare il valore EAC per gestire gli utenti di posta

In questa sezione vengono fornite informazioni sull'aggiunta e la gestione degli utenti di posta elettronica direttamente in EAC.
  
 **Informazioni preliminari**
  
Per eseguire queste procedure, è necessario disporre delle autorizzazioni appropriate. Per sapere quali autorizzazioni sono necessarie, vedere voce "Utente, Contatti e Gruppi ruolo" in [Autorizzazioni di funzionalità in EOP](feature-permissions-in-eop.md).
  
### <a name="to-add-a-mail-user-in-the-eac"></a>Per aggiungere un utente di posta in EAC

1. Per creare un utente di posta elettronica, andare a **Destinatari** \> **Contatti** in EAC, quindi fare clic su **Nuovo +**.
    
2. Nella pagina **Nuovo utente di posta**, immettere le informazioni dell'utente, incluse le seguenti: 
    
   ****

|**Proprietà utente della posta**|**Descrizione**|
|:-----|:-----|
|**Nome**, **Iniziali**, and **Cognome** <br/> |Digitare il nome completo dell'utente nelle caselle appropriate.  <br/> |
|**Nome visualizzato** <br/> |Digitare un nome, utilizzando un massimo di 64 caratteri. Per impostazione predefinita, questa casella contiene i nomi nelle caselle **Nome**, **Iniziali** e **Cognome**. Il nome visualizzato è obbligatorio.  <br/> |
|**Alias** <br/> |Digitare un alias univoco per l'utente, utilizzando un massimo di 64 caratteri. L'alias è obbligatorio.  <br/> |
|**Indirizzo di posta elettronica esterno** <br/> |Digitare l'indirizzo di posta elettronica esterno dell'utente.  <br/> |
|**ID utente** <br/> |Digitare il nome utilizzato dall'utente di posta per accedere al servizio. Il nome di accesso dell'utente è costituito da un nome utente a sinistra del simbolo @ e da un suffisso a destra del simbolo. In genere, il suffisso è costituito dal nome di dominio in cui risiede l'account utente.  <br/> |
|**Nuova password** <br/> |Digitare la password utilizzata dall'utente di posta per accedere al servizio. Verificare che la password immessa sia conforme ai requisiti di lunghezza, complessità e cronologia del dominio in cui viene creato l'account utente.  <br/> |
|**Conferma password** <br/> |Digitare nuovamente la password per confermarla.  <br/> |
   
3. Fare clic su **Salva** per creare il nuovo utente di posta elettronica. Il nuovo utente viene visualizzato nell'elenco utenti. 
    
### <a name="to-edit-or-remove-a-mail-user-in-the-eac"></a>Per modificare o rimuovere un utente di posta in EAC

- Nell'interfaccia di amministrazione di Exchange accedere a **Destinatari** \> **Contatti**. Nell'elenco degli utenti, fare clic sull'utente che si desidera visualizzare o modificare, quindi selezionare **Modifica**![Icona Modifica](../media/ITPro-EAC-EditIcon.png) per aggiornare le impostazioni dell'utente secondo necessità. È possibile modificare il nome utente, l'alias o le informazioni di contatto e registrare le informazioni dettagliate sul ruolo dell'utente nell'organizzazione. È inoltre possibile selezionare un utente e scegliere **Rimuovi**![Icona Rimuovi](../media/ITPro-EAC-RemoveIcon.png) per eliminarlo. 
    
## <a name="use-remote-windows-powershell-to-manage-mail-users"></a>Utilizzare Windows PowerShell remoto per gestire gli utenti di posta elettronica

In questa sezione vengono fornite informazioni sull'aggiunta e sulla gestione degli utenti di posta elettronica mediante l'utilizzo di Windows PowerShell remoto.
  
 **Informazioni preliminari**
  
- Per eseguire queste procedure, è necessario disporre delle autorizzazioni appropriate. Per sapere quali autorizzazioni sono necessarie, vedere voce "Utente, Contatti e Gruppi ruolo" in [Autorizzazioni di funzionalità in EOP](feature-permissions-in-eop.md).
    
- Tenere presente che quando si creano utenti di posta elettronica mediante cmdlet di PowerShell remoto, si potrebbero incontrare limitazioni.
    
- Questo cmdlet utilizza un metodo di elaborazione batch che genera un ritardo di qualche minuto nella propagazione prima che i risultati del cmdlet siano visibili.
    
- Per informazioni su come utilizzare Windows PowerShell per la connessione a Exchange Online Protection, vedere [Connessione a Exchange Online Protection tramite PowerShell remota](http://technet.microsoft.com/library/054e0fd7-d465-4572-93f8-a00a9136e4d1.aspx).
    
 **Per aggiungere un utente di posta elettronica utilizzando PowerShell remoto**
  
In questo esempio viene utilizzato il cmdlet [New-EOPMailUser](http://technet.microsoft.com/library/0520cf33-4ad0-44e4-99a3-1b485739fc05.aspx) per creare un account utente abilitato alla posta elettronica per Jeffrey Zeng in EOP con i seguenti dettagli: 
  
- Il nome è Jeffrey e il cognome è Zeng.
    
- Il nome è Jeffrey e il nome visualizzato è Jeffrey Zeng.
    
- L'alias è jeffreyz.
    
- L'indirizzo di posta elettronica esterno è jzeng@tailspintoys.com.
    
- La firma di Office 365 nel nome è jeffreyz@contoso.onmicrosoft.com.
    
- La password è Pa$$word1.
    
```
New-EOPMailUser -LastName Zeng -FirstName Jeffrey -DisplayName "Jeffrey Zeng" -Name Jeffrey -Alias jeffreyz -MicrosoftOnlineServicesID jeffreyz@contoso.onmicrosoft.com -ExternalEmailAddress jeffreyz@tailspintoys.com -Password (ConvertTo-SecureString -String 'Pa$$word1' -AsPlainText -Force)
```

 **Per verificare che è corretto**
  
Eseguire il cmdlet [Get-User](http://technet.microsoft.com/library/2a33c9e6-33da-438c-912d-28ce3f4c9afb.aspx) come segue per visualizzare le informazioni sul nuovo utente di posta elettronica Jeffrey Zeng: 
  
```
Get-User "Jeffrey Zeng"

```

 **Per modificare le proprietà di un utente di posta utilizzando PowerShell remoto**
  
Utilizzare i cmdlet di [Get-Recipient](http://technet.microsoft.com/library/2ce6250f-0ad3-4b29-870c-e1d6e1e154bc.aspx) e [Set-EOPMailUser](http://technet.microsoft.com/library/834c3de6-1485-4d50-bb96-262a2c0c8619.aspx) per visualizzare o modificare le proprietà degli utenti di posta elettronica. 
  
In questo esempio viene impostato l'indirizzo di posta elettronica esterno per Pilar Pinilla.
  
```
Set-EOPMailUser -Identity "Pilar Pinilla" -EmailAddresses pilarp@tailspintoys.com
```

In questo esempio viene impostata la proprietà Company per tutti gli utenti di posta di Contoso.
  
```
$Recip = Get-Recipient -ResultSize unlimited -Filter {(RecipientTypeDetails -eq 'mailuser')}
$Recip | foreach {Set-EOPUser -Identity $_.Alias -Company Contoso}

```

 **Per verificare che è corretto**
  
Nell'esempio precedente in cui sono stata cambiate le proprietà per l'utente di posta elettronica Pilar Pinella, utilizzare il cmdlet [Get-Recipient](http://technet.microsoft.com/library/2ce6250f-0ad3-4b29-870c-e1d6e1e154bc.aspx) per verificare le modifiche (tenere presente che è possibile visualizzare più proprietà per più contatti di posta elettronica). 
  
```
Get-Recipient -Identity "Pilar Pinilla" | Format-List 

```

Nell'esempio precedente in cui la proprietà Company è stata impostata su Contoso per tutti gli utenti di posta, utilizzare il comando seguente per verificare le modifiche:
  
```
Get-Recipient -ResultSize unlimited -Filter {(RecipientTypeDetails -eq 'mailuser')} | Format-List Name,Company
```

> [!IMPORTANT]
> Questo cmdlet utilizza un metodo di elaborazione batch che genera un ritardo di qualche minuto nella propagazione prima che i risultati del cmdlet siano visibili. 
  
 **Per rimuovere un utente di posta elettronica utilizzando PowerShell remoto**
  
In questo esempio viene utilizzato il cmdlet [Remove-EOPMailUser](http://technet.microsoft.com/library/cb91dc26-ed22-4d3c-9f64-df9df1754edb.aspx) per eliminare l'utente Jeffrey Zeng: 
  
```
Remove-EOPMailUser -Identity Jeffrey
```

 **Per verificare che è corretto**
  
Eseguire il cmdlet [Get-Recipient](http://technet.microsoft.com/library/2ce6250f-0ad3-4b29-870c-e1d6e1e154bc.aspx) nel modo seguente. Dovrebbe essere visualizzato un messaggio di errore dal momento che l'utente non esiste più. 
  
```
Get-Recipient Jeffrey | fl
```


