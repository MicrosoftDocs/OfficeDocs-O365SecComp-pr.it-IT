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
# <a name="assign-ediscovery-permissions-to-onedrive-for-business-sites"></a><span data-ttu-id="43b93-106">Assegnazione di autorizzazioni eDiscovery a siti OneDrive for Business</span><span class="sxs-lookup"><span data-stu-id="43b93-106">Assign eDiscovery permissions to OneDrive for Business sites</span></span>

<span data-ttu-id="43b93-p102">È possibile utilizzare il centro eDiscovery in SharePoint Online per la ricerca di OneDrive tutti per i siti all'interno dell'organizzazione per alcune parole chiave, informazioni riservate e altri criteri di ricerca. Ogni utente nell'organizzazione è il proprietario della loro OneDrive per sito aziendale, che si trova nella raccolta siti denominata https://domain-my.sharepoint.com. Per impostazione predefinita, un amministratore globale di Office 365 o responsabile della conformità non può utilizzare il centro eDiscovery in SharePoint Online per qualsiasi OneDrive per i siti di ricerca. Per eseguire la ricerca OneDrive per Business sito, gli amministratori o responsabili della conformità deve essere un amministratore della raccolta siti per tale OneDrive for sito aziendale.</span><span class="sxs-lookup"><span data-stu-id="43b93-p102">You can use the eDiscovery Center in SharePoint Online to search all OneDrive for Business sites in your organization for certain keywords, sensitive information, and other search criteria. Each user in your organization is the owner of their OneDrive for Business site, which is located in the site collection named https://domain-my.sharepoint.com. By default, an Office 365 global administrator or compliance manager can't use the eDiscovery Center in SharePoint Online to search any OneDrive for Business sites. To search a OneDrive for Business site, administrators or compliance managers must be a site collection administrator for that OneDrive for Business site.</span></span> 
  
<span data-ttu-id="43b93-111">In questo articolo viene descritta la procedura per rendere un amministratore o a compliance manager un amministratore della raccolta siti per ogni OneDrive for sito aziendale dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="43b93-111">This article guides you through the steps to make an administrator or compliance manager a site collection administrator for every OneDrive for Business site in your organization.</span></span> 
  
<span data-ttu-id="43b93-112">Per suggerimenti su come utilizzare lo script in questo articolo, tra cui revisione lo script nel passaggio 3 per rimuovere un utente come amministratore della raccolta siti di OneDrive per i siti, vedere [ulteriori informazioni](#more-information) .</span><span class="sxs-lookup"><span data-stu-id="43b93-112">See the [More information](#more-information) section for tips about using the script in this article, including revising the script in Step 3 to remove a user as a site collection administrator from OneDrive for Business sites.</span></span> 
  
## <a name="before-you-begin"></a><span data-ttu-id="43b93-113">Informazioni preliminari</span><span class="sxs-lookup"><span data-stu-id="43b93-113">Before you begin</span></span>

- <span data-ttu-id="43b93-p103">Installare SharePoint Online Management Shell. Per informazioni, vedere [impostare l'ambiente di SharePoint Online Management Shell di Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkID=286318).</span><span class="sxs-lookup"><span data-stu-id="43b93-p103">Install the SharePoint Online Management Shell. For information, see [Set up the SharePoint Online Management Shell Windows PowerShell environment](https://go.microsoft.com/fwlink/p/?LinkID=286318).</span></span>
    
- <span data-ttu-id="43b93-116">Eseguire lo script nel passaggio 3 ogni volta che si desidera assegnare a un utente come amministratore della raccolta siti per qualsiasi OneDrive per i siti all'interno dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="43b93-116">Run the script in Step 3 each time you want to assign a user as a site collection administrator to any OneDrive for Business sites in your organization.</span></span> 
    
    > [!IMPORTANT]
    > <span data-ttu-id="43b93-p104">Un amministratore o a compliance manager che è un amministratore della raccolta siti relativi a OneDrive per i siti possono aprire OneDrive degli utenti per le raccolte documenti aziendali e le stesse attività come proprietario. È importante monitorare chi ha ottenuto le autorizzazioni di eDiscovery per OneDrive per i siti all'interno dell'organizzazione e controllo.</span><span class="sxs-lookup"><span data-stu-id="43b93-p104">An administrator or compliance manager who is a site collection administrator for OneDrive for Business sites can open users' OneDrive for Business document libraries and perform the same tasks as the owner. It's important to control and monitor who has been assigned eDiscovery permissions to OneDrive for Business sites in your organization.</span></span> 
  
- <span data-ttu-id="43b93-p105">Lo script di esempio fornito in questo articolo non è supportato in qualsiasi programma Microsoft supporto standard o del servizio. Lo script di esempio viene fornito così com'è senza garanzie di alcun tipo. Microsoft ha non riconosce tutte le garanzie implicite, in via esemplificativa, una garanzia di commerciabilità o idoneità per uno scopo specifico. Tutti i rischi derivanti dall'utilizzo o di script di esempio e documentazione rimangono con l'utente. In alcun caso Microsoft, relativi autori o altre posizioni necessarie per la creazione, produzione o recapito dello script tutti gli utenti saranno responsabili per danni (incluso, in via esemplificativa, danni per mancato guadagno, interruzione delle attività, la perdita di perdita le informazioni aziendali o altre perdite economiche) derivanti dall'utilizzo di o impossibilità di utilizzare script di esempio o documentazione, anche se Microsoft è stati informati della possibilità di tali danni.</span><span class="sxs-lookup"><span data-stu-id="43b93-p105">The sample script provided in this article isn't supported under any Microsoft standard support program or service. The sample script is provided AS IS without warranty of any kind. Microsoft further disclaims all implied warranties including, without limitation, any implied warranties of merchantability or of fitness for a particular purpose. The entire risk arising out of the use or performance of the sample script and documentation remains with you. In no event shall Microsoft, its authors, or anyone else involved in the creation, production, or delivery of the script be liable for any damages whatsoever (including, without limitation, damages for loss of business profits, business interruption, loss of business information, or other pecuniary loss) arising out of the use of or inability to use the sample script or documentation, even if Microsoft has been advised of the possibility of such damages.</span></span>
    
## <a name="step-1-collect-a-list-of-all-onedrive-for-business-sites"></a><span data-ttu-id="43b93-124">Passaggio 1: Raccolta di un elenco di tutti i OneDrive per i siti</span><span class="sxs-lookup"><span data-stu-id="43b93-124">Step 1: Collect a list of all OneDrive for Business sites</span></span>

<span data-ttu-id="43b93-p106">Il primo passaggio consiste nel creare un elenco di tutti i OneDrive per i siti all'interno dell'organizzazione. Per ulteriori informazioni, vedere [creare un elenco di tutti i percorsi di OneDrive nell'organizzazione](https://support.office.com/article/8e200cb2-c768-49cb-88ec-53493e8ad80a). Questo script in questo articolo consente di creare un file di testo contenente un elenco di tutti i siti di OneDrive. Lo script che viene eseguita nel passaggio 3 viene assegnato un utente specificato come amministratore della raccolta siti per ogni OneDrive for Business sito elencato nel file di testo che viene creato in questo passaggio. Il testo seguente viene fornito un esempio di come deve essere formattato l'elenco dei siti in questo file. Se necessario, è possibile rimuovere siti dal file.</span><span class="sxs-lookup"><span data-stu-id="43b93-p106">The first step is to create a list of all OneDrive for Business sites in your organization. For instructions, see [Create a list of all OneDrive locations in your organization](https://support.office.com/article/8e200cb2-c768-49cb-88ec-53493e8ad80a). This script in this article creates a text file that contains a list of all OneDrive sites. The script that you run in Step 3 assigns a specified user as a site collection administrator to each OneDrive for Business site listed in the text file that's created in this step. The following text provides an example of how the list of sites in this file should be formatted. You can remove sites from this file if necessary.</span></span>

```
/personal/annb_contoso_onmicrosoft_com/
/personal/carolt_contoso_onmicrosoft_com/
/personal/esterv_contoso_onmicrosoft_com/
/personal/hollyh_contoso_onmicrosoft_com/
/personal/jeffl_contoso_onmicrosoft_com/
/personal/joeh_contoso_onmicrosoft_com/
/personal/kaia_contoso_onmicrosoft_com/
```

## <a name="step-2-connect-sharepoint-online-management-shell-to-your-organization"></a><span data-ttu-id="43b93-131">Passaggio 2: Connettere SharePoint Online Management Shell per l'organizzazione</span><span class="sxs-lookup"><span data-stu-id="43b93-131">Step 2: Connect SharePoint Online Management Shell to your organization</span></span>

1. <span data-ttu-id="43b93-132">Dal proprio computer locale, aprire SharePoint Online Management Shell ed eseguire il seguente comando:</span><span class="sxs-lookup"><span data-stu-id="43b93-132">On your local computer, open the SharePoint Online Management Shell, and run the following command:</span></span>

    ```
    $credentials = Get-Credential
    ```

2. <span data-ttu-id="43b93-133">Nella finestra di dialogo **Richiesta credenziali di Windows PowerShell**, digitare il nome utente e la password per l'account dell'amministratore globale Office 365 e fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="43b93-133">In the **Windows PowerShell Credential Request** dialog box, type the user name and password for your Office 365 global administrator account, and then click **OK**.</span></span>
    
3. <span data-ttu-id="43b93-134">Eseguire il seguente comando per connettere Shell alla propria organizzazione SharePoint Online:</span><span class="sxs-lookup"><span data-stu-id="43b93-134">Run the following command to connect the Shell to your SharePoint Online organization:</span></span>
    
    ```
    Connect-SPOService -Url https://<your organization name>-admin.sharepoint.com -credential $credentials
    ```
   
4. <span data-ttu-id="43b93-135">Per verificare di essere connessi alla propria organizzazione SharePoint Online, eseguire il seguente comando per visualizzare un elenco di tutti i siti dell'organizzazione:</span><span class="sxs-lookup"><span data-stu-id="43b93-135">To verify that you are connected to your SharePoint Online organization, run the following command to get a list of all the sites in your organization:</span></span>
    
    ```
    Get-SPOSite
    ```

## <a name="step-3-assign-a-user-as-a-site-collection-administrator-to-onedrive-for-business-sites"></a><span data-ttu-id="43b93-136">Passaggio 3: Assegnare a un utente il ruolo di amministratore raccolta siti per siti di OneDrive for Business</span><span class="sxs-lookup"><span data-stu-id="43b93-136">Step 3: Assign a user as a site collection administrator to OneDrive for Business sites</span></span>

<span data-ttu-id="43b93-p107">Il passaggio successivo consiste nell'eseguire uno script che viene assegnato un utente specificato come amministratore della raccolta siti in ogni OneDrive per sito Business nell'organizzazione. Questo script utilizza l'elenco di OneDrive per i siti creati nel passaggio 1. Come descritto in precedenza, è necessario eseguire questo script ogni volta che si desidera assegnare un utente come amministratore della raccolta siti a OneDrive per i siti.</span><span class="sxs-lookup"><span data-stu-id="43b93-p107">The next step is to run a script that assigns a specified user as a site collection administrator in every OneDrive for Business site in your organization. This script uses the list of OneDrive for Business sites that you created in Step 1. As previously stated, you have to run this script each time that you want to assign a user as a site collection administrator to OneDrive for Business sites.</span></span>
  
1. <span data-ttu-id="43b93-p108">Salvare il seguente testo in un file di testo. Ad esempio, salvarlo in un file con il nome OD4BAssignSCA.txt.</span><span class="sxs-lookup"><span data-stu-id="43b93-p108">Save the following text to a text file. For example, you could save it to a file named OD4BAssignSCA.txt.</span></span>

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

2. <span data-ttu-id="43b93-p109">Modificare le variabili seguenti all'inizio del file di script e utilizzare le informazioni specifiche dell'organizzazione. Nell'esempio seguente si presuppongono che il nome di dominio dell'organizzazione sia contoso.onmicrosoft.com. È necessario racchiudere i valori per le variabili con virgolette doppie ("").</span><span class="sxs-lookup"><span data-stu-id="43b93-p109">Edit the following variables in the beginning of the script file, and use information that's specific to your organization. The following examples assume that the domain name of your organization is contoso.onmicrosoft.com. Be sure to surround the values for the variables with double-quotation marks (" ").</span></span>
    
    - <span data-ttu-id="43b93-145">**$AdminURI** - consente di specificare l'URI per il servizio Amministrazione SharePoint Online, ad esempio `"https://contoso-admin.sharepoint.com"`.</span><span class="sxs-lookup"><span data-stu-id="43b93-145">**$AdminURI** - This specifies the URI for your SharePoint Online admin service, for example,  `"https://contoso-admin.sharepoint.com"`.</span></span>
    
    - <span data-ttu-id="43b93-146">**$AdminAccount** - consente di specificare un account amministratore globale dell'organizzazione Office 365, ad esempio `"admin@contoso.onmicrosoft.com"`.</span><span class="sxs-lookup"><span data-stu-id="43b93-146">**$AdminAccount** - This specifies a global administrator account in your Office 365 organization, for example,  `"admin@contoso.onmicrosoft.com"`.</span></span>
    
    - <span data-ttu-id="43b93-147">**$eDiscoveryUser** - consente di specificare l'account utente di un amministratore o responsabile della conformità che verrà assegnato come amministratore della raccolta siti per ogni OneDrive for sito aziendale dell'organizzazione, ad esempio `"annb@contoso.onmicrosoft.com"`.</span><span class="sxs-lookup"><span data-stu-id="43b93-147">**$eDiscoveryUser** - This specifies the user account of an administrator or compliance manager who will be assigned as a site collection administrator for every OneDrive for Business site in your organization, for example,  `"annb@contoso.onmicrosoft.com"`.</span></span>
    
      > [!NOTE]
      > <span data-ttu-id="43b93-148">Modificare l'account utente specificata nella variabile **$eDiscoveryUser** ed eseguire nuovamente lo script per assegnare un altro utente come amministratore della raccolta siti a OneDrive per i siti specificati dalla variabile **$MySiteListFile** .</span><span class="sxs-lookup"><span data-stu-id="43b93-148">Change the user account specified by the **$eDiscoveryUser** variable and re-run the script to assign a different user as a site collection administrator to the OneDrive for Business sites that are specified by the **$MySiteListFile** variable.</span></span> 
  
    - <span data-ttu-id="43b93-p110">**$MySitePrefix** Consente di specificare l'URL per il dominio dell'organizzazione sito personale. Si tratta del dominio che contiene tutte le OneDrive per i siti all'interno dell'organizzazione, ad esempio `"https://contoso-my.sharepoint.com"`.</span><span class="sxs-lookup"><span data-stu-id="43b93-p110">**$MySitePrefix**This specifies the URL for your organization's MySite domain. This is the domain that contains all the OneDrive for Business sites in your organization, for example,  `"https://contoso-my.sharepoint.com"`.</span></span>
    
    - <span data-ttu-id="43b93-p111">**$MySiteListFile** Consente di specificare il percorso completo del file di testo che è stato creato nel passaggio 1. In questo file contiene un elenco di OneDrive per i siti all'interno dell'organizzazione, ad esempio, `'C:\Users\<youralias>\Desktop\ListOfMysites.txt'`. È necessario racchiudere il valore di questa variabile con virgolette singole (' '). Si noti che è necessario specificare il percorso è stato salvato il file di testo nel passaggio 1.</span><span class="sxs-lookup"><span data-stu-id="43b93-p111">**$MySiteListFile**This specifies the full path of the text file that you created in Step 1. This file contains a list of OneDrive for Business sites in your organization, for example,  `'C:\Users\<youralias>\Desktop\ListOfMysites.txt'`. Be sure to surround the value for this variable with single-quotation marks (' '). Note that you should specify the location that you saved the text file to in Step 1.</span></span>
    
3. <span data-ttu-id="43b93-p112">Salvare il file di testo come uno script PowerShell modificando il nome del suffisso del file in .ps1. Ad esempio, salvare il file OD4BAssignSCA.txt come OD4BAssignSCA.ps1.</span><span class="sxs-lookup"><span data-stu-id="43b93-p112">Save the text file as a PowerShell script file by changing the file name suffix to .ps1. For example, save the file OD4BAssignSCA.txt as OD4BAssignSCA.ps1.</span></span>
    
4. <span data-ttu-id="43b93-157">In SharePoint Online Management Shell, accedere alla cartella che contiene lo script PowerShell creato nel passaggio precedente ed eseguire lo script, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="43b93-157">In SharePoint Online Management Shell, go to the folder that contains the PowerShell script that you created in the previous step, and then run the script, for example:</span></span>
    
    ```
    .\OD4BAssignSCA.ps1
    ```

    <span data-ttu-id="43b93-p113">Verrà chiesto di immettere la password per l'account amministratore specificato nello script. Se lo script venga eseguito correttamente, il messaggio `"Making  _\<user specified by $eDiscoveryUser\>_ a Site Collection Admin"` visualizzate per ogni OneDrive per sito Business elencato nel file di input specificato da **$MySiteListFile**.</span><span class="sxs-lookup"><span data-stu-id="43b93-p113">You will be prompted to enter the password for the administrator account that you specified in the script. If the script runs successfully, the message `"Making  _\<user specified by $eDiscoveryUser\>_ a Site Collection Admin"` is displayed for each OneDrive for Business site that's listed in the input file specified by **$MySiteListFile**.</span></span>

## <a name="more-information"></a><span data-ttu-id="43b93-160">Ulteriori informazioni</span><span class="sxs-lookup"><span data-stu-id="43b93-160">More information</span></span>

- <span data-ttu-id="43b93-p114">Lo script che è stato eseguito nel passaggio 3 utilizza il cmdlet **Set-SPOUser** per assegnare l'utente specificato come amministratore della raccolta siti per ogni OneDrive for Business è elencato nel file specificato dalla variabile **$MySiteListFile** . Se si dispone di un'organizzazione di grande dimensioni con migliaia di utenti, prendere in considerazione la procedura seguente per rendere più semplice gestire l'assegnazione delle autorizzazioni di eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="43b93-p114">The script that you ran in Step 3 uses the **Set-SPOUser** cmdlet to assign the specified user as a site collection administrator to every OneDrive for Business that's listed in the file specified by the **$MySiteListFile** variable. If you have a very large organization with thousands of users, consider doing the following to make it easier to manage assigning eDiscovery permissions.</span></span> 
    
  - <span data-ttu-id="43b93-163">Modificare il file creato nel passaggio 1 che contiene l'elenco di OneDrive per i siti in modo da includere solo i siti per gli utenti sono impegnate in casi legali attivi.</span><span class="sxs-lookup"><span data-stu-id="43b93-163">Edit the file that you created in Step 1 that contains the list of OneDrive for Business sites so that it includes only the sites for users are that are involved in active legal cases.</span></span>
    
  - <span data-ttu-id="43b93-p115">Assegnare autorizzazioni a non più di 2.500 OneDrive per i siti al giorno. Si supponga, ad esempio, che è necessario 10.000 OneDrive per i siti all'interno dell'organizzazione. È possibile creare l'elenco nel passaggio 1 per la raccolta di tutti i siti. Quindi è possibile utilizzare tale file per creare i quattro file contenenti ognuno 2.500 utenti. Il primo giorno, eseguire lo script nel passaggio 3 per assegnare le autorizzazioni per la prima 2.500 OneDrive per i siti. Il secondo giorno, eseguire lo script per il successivo 2.500 OneDrive per i siti di Business e così via.</span><span class="sxs-lookup"><span data-stu-id="43b93-p115">Assign permissions to no more than 2,500 OneDrive for Business sites per day. For example, let's say you have 10,000 OneDrive for Business sites in your organization. You could create the list in Step 1 to collect all the sites. Then you could use that file to create four files that each contain 2,500 users. On the first day, you would run the script in Step 3 to assign permissions to the first 2,500 OneDrive for Business sites. On the second day, you would run the script for the next 2,500 OneDrive for Business sites, and so on.</span></span>
    
- <span data-ttu-id="43b93-p116">Tenere traccia di OneDrive per i siti che sono state assegnate le autorizzazioni di eDiscovery e dell'utente cui è stato assegnato come amministratore della raccolta siti. Ad esempio, dopo l'assegnazione delle autorizzazioni, è possibile salvare il file di testo che contiene l'elenco di OneDrive per i siti e aggiungervi una linea che identifica l'utente cui è stato assegnato come amministratore della raccolta siti.</span><span class="sxs-lookup"><span data-stu-id="43b93-p116">Keep a record of the OneDrive for Business sites that were assigned eDiscovery permissions and the user who is assigned as the site collection administrator. For example, after you assign permissions, you can save the text file that contains the list of OneDrive for Business sites and add a line to it that identifies the user who is assigned as the site collection administrator.</span></span>
    
- <span data-ttu-id="43b93-p117">Gli utenti possono visualizzare l'elenco dei siti insieme Administrators per il OneDrive per sito aziendale. Poiché gli utenti amministratore della raccolta siti per i propri OneDrive for sito aziendale, è possibile rimuovere gli amministratori della raccolta siti. È consigliabile eseguire le operazioni seguenti per ridurre le possibilità degli utenti quando si rimuove l'utente che è stata assegnata le autorizzazioni di eDiscovery OneDrive per i siti.</span><span class="sxs-lookup"><span data-stu-id="43b93-p117">Users can view the list of site collection administators for their OneDrive for Business site. Because users are site collection administrator for their own OneDrive for Business site, they can remove site collection administrators. Consider doing the following to mitigate the chance of users removing the user who is assigned eDiscovery permissions to OneDrive for Business sites.</span></span>
    
  - <span data-ttu-id="43b93-175">Comunicazione con gli utenti per scopi di eDiscovery e la conformità, un addetto alla conformità è stato assegnato come amministratore della raccolta siti per OneDrive per i siti all'interno dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="43b93-175">Communicate to users that for eDiscovery and compliance purposes, a compliance officer has been assigned as a site collection administrator to OneDrive for Business sites in your organization.</span></span>
    
  - <span data-ttu-id="43b93-176">Eseguire di nuovo lo script nel passaggio 3, se necessario, per riassegnare un utente come amministratore della raccolta siti relativi a OneDrive per i siti.</span><span class="sxs-lookup"><span data-stu-id="43b93-176">Re-run the script in Step 3, if necessary, to re-assign a user as the site collection administrator for OneDrive for Business sites.</span></span>
    
- <span data-ttu-id="43b93-p118">È inoltre possibile utilizzare lo script è stato eseguito nel passaggio 3 per rimuovere un utente come amministratore della raccolta siti di OneDrive per i siti. Per rimuovere un utente come amministratore della raccolta siti, è necessario modificare il seguente comando (quasi alla fine dello script) da:</span><span class="sxs-lookup"><span data-stu-id="43b93-p118">You can also use the script that you ran in Step 3 to remove a user as the site collection administrator from OneDrive for Business sites. To remove a user as a site collection administrator, you have to change the following command (near the end of the script) from:</span></span> 

    ```
    Set-SPOUser -Site $fullsitepath -LoginName $eDiscoveryUser -IsSiteCollectionAdmin $true
    ```

    <span data-ttu-id="43b93-179">a:</span><span class="sxs-lookup"><span data-stu-id="43b93-179">to:</span></span>
    
    ```
    Set-SPOUser -Site $fullsitepath -LoginName $eDiscoveryUser -IsSiteCollectionAdmin $false
    ```

    <span data-ttu-id="43b93-180">Si può anche modificare la riga seguente nello script da:</span><span class="sxs-lookup"><span data-stu-id="43b93-180">You can also change the following line in the script from:</span></span>

    ```
    "Making $eDiscoveryUser a Site Collection Admin"
    ```

    <span data-ttu-id="43b93-181">a:</span><span class="sxs-lookup"><span data-stu-id="43b93-181">to:</span></span>
    
    ```
    "Removing $eDiscoveryUser as a Site Collection Admin"
    ```

    <span data-ttu-id="43b93-182">Dopo aver apportato queste modifiche, salvare lo script con un nome diverso, ad esempio OD4BRemoveSCA.ps1 e quindi utilizzarla per rimuovere un utente come amministratore della raccolta siti da un gruppo di OneDrive per i siti.</span><span class="sxs-lookup"><span data-stu-id="43b93-182">After you make these changes, save the script with a different name, such as OD4BRemoveSCA.ps1, and then use it to remove a user as a site collection administrator from a group of OneDrive for Business sites.</span></span>
