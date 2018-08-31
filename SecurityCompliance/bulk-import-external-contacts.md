---
title: Contatti esterni di importazione in blocco a Exchange Online
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 6/29/2018
ms.audience: End User
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOP150
ms.assetid: bed936bc-0969-4a6d-a7a5-66305c14e958
description: Informazioni su come gli amministratori possono utilizzare Exchange Online PowerShell e un file CSV per blocco importare contatti esterni all'elenco indirizzi globale.
ms.openlocfilehash: 4bde56d49ccf94dc91993df90e1ae693e25c961a
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/27/2018
ms.locfileid: "22530288"
---
# <a name="bulk-import-external-contacts-to-exchange-online"></a>Contatti esterni di importazione in blocco a Exchange Online

**In questo articolo sia per gli amministratori. Si sta tentando di importare contatti alla propria cassetta postale? Vedere [importazione di contatti di Outlook](https://support.office.com/article/bb796340-b58a-46c1-90c7-b549b8f3c5f8)**
   
La società dispone di una quantità elevata di contatti aziendali esistenti che si desidera includere nella Rubrica condivisa (denominata anche l'elenco indirizzi globale) in Exchange Online? Si desidera aggiungere contatti esterni come membri dei gruppi di distribuzione, nello stesso modo in cui è possibile eseguire con gli utenti interni alla società? Se pertanto è possibile utilizzare Exchange Online PowerShell e un file CSV (delimitato da virgole) in blocco importare contatti esterni in Exchange Online. È un processo in tre fasi:
  
[Passaggio 1: Creare un file CSV contenente informazioni sui contatti esterni](#step-1-create-a-csv-file-that-contains-information-about-the-external-contacts)

[Passaggio 2: Creare contatti esterni PowerShell](#step-2-create-the-external-contacts-with-powershell) 

[Passaggio 3: Aggiungere informazioni alle proprietà dei contatti esterni](#step-3-add-information-to-the-properties-of-the-external-contacts)

Dopo aver completato la procedura seguente per importare contatti, è possibile eseguire le seguenti attività aggiuntive:
  
- [Aggiungere i contatti più esterni](bulk-import-external-contacts.md#AddMore)
  
- [Nascondere i contatti esterni nella Rubrica condivisa](bulk-import-external-contacts.md#Hide)
  
## <a name="step-1-create-a-csv-file-that-contains-information-about-the-external-contacts"></a>Passaggio 1: Creare un file CSV contenente informazioni sui contatti esterni

Il primo passaggio consiste nel creare un file CSV contenente informazioni su ogni contatto esterno che si desidera importare in Exchange Online. 
  
1. Copiare il testo seguente in un file di testo nel blocco note e salvarlo sul desktop come un file CSV con il suffisso nome file. csv; ad esempio, ExternalContacts.csv.
    
    > [!TIP]
    > Se la lingua dell'utente contiene caratteri speciali (ad esempio **å** **ä**e **ö** in svedese) Salva il file CSV con UTF-8 o altra codifica Unicode quando si salva il file nel blocco note. 
  
    ```
    ExternalEmailAddress,Name,FirstName,LastName,StreetAddress,City,StateorProvince,PostalCode,Phone,MobilePhone,Pager,HomePhone,Company,Title,OtherTelephone,Department,CountryOrRegion,Fax,Initials,Notes,Office,Manager
    danp@fabrikam.com,Dan Park,Dan,Park,1234 23rd Ave,Golden,CO,80215,206-111-1234,303-900-1234,555-1212,123-456-7890,Fabrikam,Shipping clerk,555-5555,Shipping,US,123-4567,R.,Good worker,31/1663,Dan Park
    pilar@contoso.com,Pilar Pinilla,Pilar,Pinilla,1234 Main St.,Seattle,WA,98017,206-555-0100,206-555-0101,206-555-0102,206-555-1234,Contoso,HR Manager,206-555-0104,Executive,US,206-555-0105,P.,Technical decision maker,31/1000,Dan Park 
    ```

    La prima riga o una riga di intestazione, del file CSV sono elencate le proprietà dei contatti che possono essere utilizzati durante l'importazione in Exchange Online. I nomi di proprietà sono separati da una virgola. Ogni riga sotto la riga di intestazione rappresenta i valori delle proprietà per l'importazione di un contatto esterno. 
    
    > [!NOTE]
    > Il testo incluso dati di esempio, è possibile eliminare. Ma non eliminare o modificare la prima riga (intestazione). Contiene tutte le proprietà per i contatti esterni. 
  
2. Aprire il file CSV in Microsoft Excel per modificare il file CSV perché è molto più semplice utilizzare Excel per modificare il file CSV.
    
3. Creare una riga per ogni contatto che si desidera importare in Exchange Online. Popolare il numero di celle come possibili. Tali informazioni verranno visualizzate nella Rubrica condivisa per ogni contatto. 
    
    > [!IMPORTANT]
    >  Le proprietà seguenti, che sono i primi quattro elementi nella riga di intestazione, sono necessari per creare un contatto esterno, è necessario specificare nel file CSV: **ExternalEmailAddress**, **nome**, **FirstName**, **LastName**. Il comando PowerShell che viene eseguita nel passaggio 2 utilizzerà i valori per le proprietà per creare i contatti. 

## <a name="step-2-create-the-external-contacts-with-powershell"></a>Passaggio 2: Creare contatti esterni PowerShell

Il passaggio successivo consiste nell'utilizzare il file CSV creato nel passaggio 1 e PowerShell al blocco importare contatti esterni elencati nel file CSV in Exchange Online. 
  
1.  Connettere PowerShell all'organizzazione Exchange Online. Per istruzioni dettagliate, vedere [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=396554). Assicurarsi di utilizzare il nome utente e la password per l'account amministratore globale di Office 365 durante la connessione a Exchange Online PowerShell. 
    
2. Dopo essersi connessi PowerShell in Exchange Online, passare alla cartella desktop di cui è stato salvato il file CSV nel passaggio 1; ad esempio `C:\Users\Administrator\desktop`.
    
3. Eseguire il comando seguente per creare contatti esterni:

    ```
    Import-Csv .\ExternalContacts.csv|%{New-MailContact -Name $_.Name -DisplayName $_.Name -ExternalEmailAddress $_.ExternalEmailAddress -FirstName $_.FirstName -LastName $_.LastName}
    ```

    Potrebbero richiedere alcuni minuti per creare nuovi contatti, in base al numero che si sta importando. Al termine del comando PowerShell in esecuzione, visualizza un elenco di nuovi contatti che sono stati creati. 
    
4. Per visualizzare i nuovi contatti esterni, passare all'interfaccia di amministrazione di Exchange (EAC) e quindi fare clic su **destinatari** \> **contatti**. 
    
    > [!TIP]
    > Per istruzioni per la connessione a EAC, vedere [Exchange admin center in Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=328197). 
  
5. Se necessario, fare clic su **Aggiorna** ![icona Aggiorna](media/O365-MDM-Policy-RefreshIcon.gif) per aggiornare l'elenco e visualizzare i contatti esterni che sono stati importati. 
    
    I contatti importati apparirà nella Rubrica condivisa in Outlook e Outlook sul web.
    
    > [!NOTE]
    > È inoltre possibile visualizzare i contatti nell'interfaccia di amministrazione di Office 365 accedendo a **utenti** \> **contatti**. 

## <a name="step-3-add-information-to-the-properties-of-the-external-contacts"></a>Passaggio 3: Aggiungere informazioni alle proprietà dei contatti esterni

Dopo aver eseguito il comando nel passaggio 2, vengono creati i contatti esterni, ma non contengono le informazioni contatto o dell'organizzazione, ovvero le informazioni dalla maggior parte delle celle nel file CSV. Ciò avviene perché quando si creano nuovi contatti esterni, vengono popolate solo le proprietà necessarie. Non bisogna preoccuparsi se non si dispongano di tutte le informazioni popolate nel file CSV. Se non è presente, non verranno aggiunti.
  
1.  Connettere PowerShell all'organizzazione Exchange Online. Per istruzioni dettagliate, vedere [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=396554).
    
2. Passare alla cartella desktop di cui è stato salvato il file CSV nel passaggio 1; ad esempio `C:\Users\Administrator\desktop`.
    
3. Eseguire i due comandi seguenti per aggiungere le altre proprietà del file CSV per i contatti esterni creato nel passaggio 2.
    
    ```
    $Contacts = Import-CSV .\ExternalContacts.csv
  
    ```

    ```
    $contacts | ForEach {Set-Contact $_.Name -StreetAddress $_.StreetAddress -City $_.City -StateorProvince $_.StateorProvince -PostalCode $_.PostalCode -Phone $_.Phone -MobilePhone $_.MobilePhone -Pager $_.Pager -HomePhone $_.HomePhone -Company $_.Company -Title $_.Title -OtherTelephone $_.OtherTelephone -Department $_.Department -Fax $_.Fax -Initials $_.Initials -Notes  $_.Notes -Office $_.Office -Manager $_.Manager}
    ```

    > [!NOTE]
    > Il parametro _Manager_ può essere problematico. Se la cella è vuota nel file CSV, si verificherà un errore e nessuna delle informazioni sulle proprietà verrà aggiunto al contatto. Se non è necessario specificare un proprietario, quindi eliminare ` -Manager $_.Manager ` del comando PowerShell precedente. 
  
    Nuovamente, potrebbe richiedere un po' di tempo per aggiornare i contatti in base al numero è stato importato nel passaggio 1. 
    
4. Per verificare che le proprietà sono state aggiunte ai contatti: 
    
1. Nell'interfaccia di amministrazione di Exchange accedere a **Destinatari** \> **Contatti**.
    
2. Fare clic su un contatto e quindi fare clic su **Modifica** ![sull'icona Modifica](media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif) per visualizzare le proprietà del contatto. 
    
Questo è tutto! Gli utenti possono visualizzare i contatti e le informazioni aggiuntive nella Rubrica di Outlook e Outlook sul web.
  
## <a name="add-more-external-contacts"></a>Aggiungere i contatti più esterni

È possibile ripetere i passaggi da 1 a passaggio 3 per aggiungere nuovi contatti esterni di Exchange Online. Gli utenti dell'azienda appena possibile aggiungere una nuova riga nel file CSV per il nuovo contatto. È quindi possibile eseguire i comandi di PowerShell di passaggio 2 e passaggio 3 per creare e aggiungere informazioni ai nuovi contatti.
  
> [!NOTE]
> Quando si esegue il comando per creare nuovi contatti, potrebbe essere visualizzato un errore indicante che i contatti che sono stati creati in precedenza già esistano. Ma viene creato un nuovo contatto aggiunto il file CSV. 
  
## <a name="hide-external-contacts-from-the-shared-address-book"></a>Nascondere i contatti esterni nella Rubrica condivisa >

Alcune aziende possono utilizzare i contatti esterni solo in modo che possono essere aggiunti come membri dei gruppi di distribuzione. In questo scenario è possibile nascondere i contatti esterni nella Rubrica condivisa. Ecco come:
  
1.  Connettere PowerShell all'organizzazione Exchange Online. Per istruzioni dettagliate, vedere [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=396554).
    
2. Per nascondere un singolo contatto esterno, eseguire il comando seguente.
    
    ```
    Set-MailContact <external contact> -HiddenFromAddressListsEnabled $true 
    ```
 
    Ad esempio, per nascondere Pilar Pinilla dalla Rubrica condivisa, eseguire questo comando:

    ```
    Set-MailContact "Pilar Pinilla" -HiddenFromAddressListsEnabled $true
    ```
   
3. Per nascondere tutti i contatti esterni nella Rubrica condivisa, eseguire questo comando:

    ```
    Get-Contact -ResultSize unlimited -Filter {(RecipientTypeDetails -eq 'MailContact')} | Set-MailContact -HiddenFromAddressListsEnabled $true  
    ```

Dopo aver nasconderle, contatti esterni non vengono visualizzati nella Rubrica condivisa, ma è comunque possibile aggiungerli come membri del gruppo di distribuzione.
