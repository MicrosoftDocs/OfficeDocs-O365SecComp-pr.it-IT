---
title: Assegnazione di autorizzazioni eDiscovery a siti OneDrive for Business
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 6/27/2018
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- SPO160
- MOE150
ms.assetid: 422858ff-917b-46d4-9e5b-3397f60eee4d
description: È possibile utilizzare il centro eDiscovery in SharePoint Online per la ricerca di OneDrive tutti per i siti all'interno dell'organizzazione per alcune parole chiave, informazioni riservate e altri criteri di ricerca. Ogni utente nell'organizzazione è il proprietario della loro OneDrive per sito aziendale, che si trova nella raccolta siti denominata https://domain-my.sharepoint.com. Per impostazione predefinita, un amministratore globale di Office 365 o responsabile della conformità non può utilizzare il centro eDiscovery in SharePoint Online per qualsiasi OneDrive per i siti di ricerca. Per eseguire la ricerca OneDrive per Business sito, gli amministratori o responsabili della conformità deve essere un amministratore della raccolta siti per tale OneDrive for sito aziendale.
ms.openlocfilehash: 61f068a03bcce599d9f1b7eb62d7b317b7feab68
ms.sourcegitcommit: 7956955cd919f6e00b64e4506605a743c5872549
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/26/2018
ms.locfileid: "25038089"
---
# <a name="assign-ediscovery-permissions-to-onedrive-for-business-sites"></a>Assegnazione di autorizzazioni eDiscovery a siti OneDrive for Business

È possibile utilizzare il centro eDiscovery in SharePoint Online per la ricerca di OneDrive tutti per i siti all'interno dell'organizzazione per alcune parole chiave, informazioni riservate e altri criteri di ricerca. Ogni utente nell'organizzazione è il proprietario della loro OneDrive per sito aziendale, che si trova nella raccolta siti denominata https://domain-my.sharepoint.com. Per impostazione predefinita, un amministratore globale di Office 365 o responsabile della conformità non può utilizzare il centro eDiscovery in SharePoint Online per qualsiasi OneDrive per i siti di ricerca. Per eseguire la ricerca OneDrive per Business sito, gli amministratori o responsabili della conformità deve essere un amministratore della raccolta siti per tale OneDrive for sito aziendale. 
  
In questo articolo viene descritta la procedura per rendere un amministratore o a compliance manager un amministratore della raccolta siti per ogni OneDrive for sito aziendale dell'organizzazione. 
  
Per suggerimenti su come utilizzare lo script in questo articolo, tra cui revisione lo script nel passaggio 3 per rimuovere un utente come amministratore della raccolta siti di OneDrive per i siti, vedere [ulteriori informazioni](#more-information) . 
  
## <a name="before-you-begin"></a>Informazioni preliminari

- Installare SharePoint Online Management Shell. Per informazioni, vedere [impostare l'ambiente di SharePoint Online Management Shell di Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkID=286318).
    
- Eseguire lo script nel passaggio 3 ogni volta che si desidera assegnare a un utente come amministratore della raccolta siti per qualsiasi OneDrive per i siti all'interno dell'organizzazione. 
    
    > [!IMPORTANT]
    > Un amministratore o a compliance manager che è un amministratore della raccolta siti relativi a OneDrive per i siti possono aprire OneDrive degli utenti per le raccolte documenti aziendali e le stesse attività come proprietario. È importante monitorare chi ha ottenuto le autorizzazioni di eDiscovery per OneDrive per i siti all'interno dell'organizzazione e controllo. 
  
- Lo script di esempio fornito in questo articolo non è supportato in qualsiasi programma Microsoft supporto standard o del servizio. Lo script di esempio viene fornito così com'è senza garanzie di alcun tipo. Microsoft ha non riconosce tutte le garanzie implicite, in via esemplificativa, una garanzia di commerciabilità o idoneità per uno scopo specifico. Tutti i rischi derivanti dall'utilizzo o di script di esempio e documentazione rimangono con l'utente. In alcun caso Microsoft, relativi autori o altre posizioni necessarie per la creazione, produzione o recapito dello script tutti gli utenti saranno responsabili per danni (incluso, in via esemplificativa, danni per mancato guadagno, interruzione delle attività, la perdita di perdita le informazioni aziendali o altre perdite economiche) derivanti dall'utilizzo di o impossibilità di utilizzare script di esempio o documentazione, anche se Microsoft è stati informati della possibilità di tali danni.
    
## <a name="step-1-collect-a-list-of-all-onedrive-for-business-sites"></a>Passaggio 1: Raccolta di un elenco di tutti i OneDrive per i siti

Il primo passaggio consiste nel creare un elenco di tutti i OneDrive per i siti all'interno dell'organizzazione. Per ulteriori informazioni, vedere [creare un elenco di tutti i percorsi di OneDrive nell'organizzazione](https://support.office.com/article/8e200cb2-c768-49cb-88ec-53493e8ad80a). Questo script in questo articolo consente di creare un file di testo contenente un elenco di tutti i siti di OneDrive. Lo script che viene eseguita nel passaggio 3 viene assegnato un utente specificato come amministratore della raccolta siti per ogni OneDrive for Business sito elencato nel file di testo che viene creato in questo passaggio. Il testo seguente viene fornito un esempio di come deve essere formattato l'elenco dei siti in questo file. Se necessario, è possibile rimuovere siti dal file.

```
/personal/annb_contoso_onmicrosoft_com/
/personal/carolt_contoso_onmicrosoft_com/
/personal/esterv_contoso_onmicrosoft_com/
/personal/hollyh_contoso_onmicrosoft_com/
/personal/jeffl_contoso_onmicrosoft_com/
/personal/joeh_contoso_onmicrosoft_com/
/personal/kaia_contoso_onmicrosoft_com/
```

## <a name="step-2-connect-sharepoint-online-management-shell-to-your-organization"></a>Passaggio 2: Connettere SharePoint Online Management Shell per l'organizzazione

1. Dal proprio computer locale, aprire SharePoint Online Management Shell ed eseguire il seguente comando:

    ```
    $credentials = Get-Credential
    ```

2. Nella finestra di dialogo **Richiesta credenziali di Windows PowerShell**, digitare il nome utente e la password per l'account dell'amministratore globale Office 365 e fare clic su **OK**.
    
3. Eseguire il seguente comando per connettere Shell alla propria organizzazione SharePoint Online:
    
    ```
    Connect-SPOService -Url https://<your organization name>-admin.sharepoint.com -credential $credentials
    ```
   
4. Per verificare di essere connessi alla propria organizzazione SharePoint Online, eseguire il seguente comando per visualizzare un elenco di tutti i siti dell'organizzazione:
    
    ```
    Get-SPOSite
    ```

## <a name="step-3-assign-a-user-as-a-site-collection-administrator-to-onedrive-for-business-sites"></a>Passaggio 3: Assegnare a un utente il ruolo di amministratore raccolta siti per siti di OneDrive for Business

Il passaggio successivo consiste nell'eseguire uno script che viene assegnato un utente specificato come amministratore della raccolta siti in ogni OneDrive per sito Business nell'organizzazione. Questo script utilizza l'elenco di OneDrive per i siti creati nel passaggio 1. Come descritto in precedenza, è necessario eseguire questo script ogni volta che si desidera assegnare un utente come amministratore della raccolta siti a OneDrive per i siti.
  
1. Salvare il seguente testo in un file di testo. Ad esempio, salvarlo in un file con il nome OD4BAssignSCA.txt.

    ```
    # Start logging, so if this script fails, you can look at the last successful change,
    # remove any OneDrive for Business paths that worked it from the input file, and then rerun the script.

    Start-Transcript

    # URL for your organization's SPO admin service

    $AdminURI = "https://<your organization name>-admin.sharepoint.com"

    # User account for an Office 365 global admin in your organization

    $AdminAccount = "<global admin account>"

    # Compliance manager to be made site collection admin on each MySite

    $eDiscoveryUser = "<eDiscovery user account>"

    # URL for your tenant's MySite domain

    $MySitePrefix = "https://<your organization name>-my.sharepoint.com"

    # Where should we read the list of MySites?
    # This file should contain partial MySite paths formatted as follows, one per line; for example
    # /personal/junminh_contoso_onmicrosoft_com/

    $MySiteListFile = 'C:\Users\<youralias>\Desktop\ListOfMysites.txt'

    # Begin by connecting to the service
    Connect-SPOService -Url $AdminURI -Credential $AdminAccount

    # Make a reader for our list of MySites

    $reader = [System.IO.File]::OpenText($MySiteListFile)

    try {
      for(;;) {

    # Read a line
          $line = $reader.ReadLine()
    # Stop if it doesn't exist
          if ($line -eq $null) { break }

    # Turn the line into a complete SharePoint site path by merging $MySitePrefix
    # Formatted like this: "https://contoso-my.sharepoint.com"
    # ...with each partial MySite path in the file, formatted like this:
    # "/personal/junminh_contoso_onmicrosoft_com/"

          $fullsitepath = "$MySitePrefix$line"

    Write-Host "Operating on $fullsitepath "

    # We need to remove the last "/" to work around an issue.
    # "/personal/junminh_contoso_onmicrosoft_com/"
    # becomes "/personal/junminh_contoso_onmicrosoft_com"

    $fullsitepath = $fullsitepath.trimend("/")

    # Make the specified eDiscovery user a site collection admin on the OneDrive for Business site
    Write-Host "Making $eDiscoveryUser a Site Collection Admin"
    Set-SPOUser -Site $fullsitepath -LoginName $eDiscoveryUser -IsSiteCollectionAdmin $true
      }
    }
    finally {
      $reader.Close()
    }
    Write-Host "Done!"
    Stop-Transcript
    Write-Host "Log written."
    ```

2. Modificare le variabili seguenti all'inizio del file di script e utilizzare le informazioni specifiche dell'organizzazione. Nell'esempio seguente si presuppongono che il nome di dominio dell'organizzazione sia contoso.onmicrosoft.com. È necessario racchiudere i valori per le variabili con virgolette doppie ("").
    
    - **$AdminURI** - consente di specificare l'URI per il servizio Amministrazione SharePoint Online, ad esempio `"https://contoso-admin.sharepoint.com"`.
    
    - **$AdminAccount** - consente di specificare un account amministratore globale dell'organizzazione Office 365, ad esempio `"admin@contoso.onmicrosoft.com"`.
    
    - **$eDiscoveryUser** - consente di specificare l'account utente di un amministratore o responsabile della conformità che verrà assegnato come amministratore della raccolta siti per ogni OneDrive for sito aziendale dell'organizzazione, ad esempio `"annb@contoso.onmicrosoft.com"`.
    
      > [!NOTE]
      > Modificare l'account utente specificata nella variabile **$eDiscoveryUser** ed eseguire nuovamente lo script per assegnare un altro utente come amministratore della raccolta siti a OneDrive per i siti specificati dalla variabile **$MySiteListFile** . 
  
    - **$MySitePrefix** Consente di specificare l'URL per il dominio dell'organizzazione sito personale. Si tratta del dominio che contiene tutte le OneDrive per i siti all'interno dell'organizzazione, ad esempio `"https://contoso-my.sharepoint.com"`.
    
    - **$MySiteListFile** Consente di specificare il percorso completo del file di testo che è stato creato nel passaggio 1. In questo file contiene un elenco di OneDrive per i siti all'interno dell'organizzazione, ad esempio, `'C:\Users\<youralias>\Desktop\ListOfMysites.txt'`. È necessario racchiudere il valore di questa variabile con virgolette singole (' '). Si noti che è necessario specificare il percorso è stato salvato il file di testo nel passaggio 1.
    
3. Salvare il file di testo come uno script PowerShell modificando il nome del suffisso del file in .ps1. Ad esempio, salvare il file OD4BAssignSCA.txt come OD4BAssignSCA.ps1.
    
4. In SharePoint Online Management Shell, accedere alla cartella che contiene lo script PowerShell creato nel passaggio precedente ed eseguire lo script, ad esempio:
    
    ```
    .\OD4BAssignSCA.ps1
    ```

    Verrà chiesto di immettere la password per l'account amministratore specificato nello script. Se lo script venga eseguito correttamente, il messaggio `"Making  _\<user specified by $eDiscoveryUser\>_ a Site Collection Admin"` visualizzate per ogni OneDrive per sito Business elencato nel file di input specificato da **$MySiteListFile**.

## <a name="more-information"></a>Ulteriori informazioni

- Lo script che è stato eseguito nel passaggio 3 utilizza il cmdlet **Set-SPOUser** per assegnare l'utente specificato come amministratore della raccolta siti per ogni OneDrive for Business è elencato nel file specificato dalla variabile **$MySiteListFile** . Se si dispone di un'organizzazione di grande dimensioni con migliaia di utenti, prendere in considerazione la procedura seguente per rendere più semplice gestire l'assegnazione delle autorizzazioni di eDiscovery. 
    
  - Modificare il file creato nel passaggio 1 che contiene l'elenco di OneDrive per i siti in modo da includere solo i siti per gli utenti sono impegnate in casi legali attivi.
    
  - Assegnare autorizzazioni a non più di 2.500 OneDrive per i siti al giorno. Si supponga, ad esempio, che è necessario 10.000 OneDrive per i siti all'interno dell'organizzazione. È possibile creare l'elenco nel passaggio 1 per la raccolta di tutti i siti. Quindi è possibile utilizzare tale file per creare i quattro file contenenti ognuno 2.500 utenti. Il primo giorno, eseguire lo script nel passaggio 3 per assegnare le autorizzazioni per la prima 2.500 OneDrive per i siti. Il secondo giorno, eseguire lo script per il successivo 2.500 OneDrive per i siti di Business e così via.
    
- Tenere traccia di OneDrive per i siti che sono state assegnate le autorizzazioni di eDiscovery e dell'utente cui è stato assegnato come amministratore della raccolta siti. Ad esempio, dopo l'assegnazione delle autorizzazioni, è possibile salvare il file di testo che contiene l'elenco di OneDrive per i siti e aggiungervi una linea che identifica l'utente cui è stato assegnato come amministratore della raccolta siti.
    
- Gli utenti possono visualizzare l'elenco dei siti insieme Administrators per il OneDrive per sito aziendale. Poiché gli utenti amministratore della raccolta siti per i propri OneDrive for sito aziendale, è possibile rimuovere gli amministratori della raccolta siti. È consigliabile eseguire le operazioni seguenti per ridurre le possibilità degli utenti quando si rimuove l'utente che è stata assegnata le autorizzazioni di eDiscovery OneDrive per i siti.
    
  - Comunicazione con gli utenti per scopi di eDiscovery e la conformità, un addetto alla conformità è stato assegnato come amministratore della raccolta siti per OneDrive per i siti all'interno dell'organizzazione.
    
  - Eseguire di nuovo lo script nel passaggio 3, se necessario, per riassegnare un utente come amministratore della raccolta siti relativi a OneDrive per i siti.
    
- È inoltre possibile utilizzare lo script è stato eseguito nel passaggio 3 per rimuovere un utente come amministratore della raccolta siti di OneDrive per i siti. Per rimuovere un utente come amministratore della raccolta siti, è necessario modificare il seguente comando (quasi alla fine dello script) da: 

    ```
    Set-SPOUser -Site $fullsitepath -LoginName $eDiscoveryUser -IsSiteCollectionAdmin $true
    ```

    a:
    
    ```
    Set-SPOUser -Site $fullsitepath -LoginName $eDiscoveryUser -IsSiteCollectionAdmin $false
    ```

    Si può anche modificare la riga seguente nello script da:

    ```
    "Making $eDiscoveryUser a Site Collection Admin"
    ```

    a:
    
    ```
    "Removing $eDiscoveryUser as a Site Collection Admin"
    ```

    Dopo aver apportato queste modifiche, salvare lo script con un nome diverso, ad esempio OD4BRemoveSCA.ps1 e quindi utilizzarla per rimuovere un utente come amministratore della raccolta siti da un gruppo di OneDrive per i siti.
