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
# <a name="bulk-import-external-contacts-to-exchange-online"></a><span data-ttu-id="099b2-103">Contatti esterni di importazione in blocco a Exchange Online</span><span class="sxs-lookup"><span data-stu-id="099b2-103">Bulk import external contacts to Exchange Online</span></span>

<span data-ttu-id="099b2-104">**In questo articolo sia per gli amministratori. Si sta tentando di importare contatti alla propria cassetta postale? Vedere [importazione di contatti di Outlook](https://support.office.com/article/bb796340-b58a-46c1-90c7-b549b8f3c5f8)**</span><span class="sxs-lookup"><span data-stu-id="099b2-104">**This article is for administrators. Are you trying to import contacts to your own mailbox? See [Import contacts to Outlook](https://support.office.com/article/bb796340-b58a-46c1-90c7-b549b8f3c5f8)**</span></span>
   
<span data-ttu-id="099b2-p101">La società dispone di una quantità elevata di contatti aziendali esistenti che si desidera includere nella Rubrica condivisa (denominata anche l'elenco indirizzi globale) in Exchange Online? Si desidera aggiungere contatti esterni come membri dei gruppi di distribuzione, nello stesso modo in cui è possibile eseguire con gli utenti interni alla società? Se pertanto è possibile utilizzare Exchange Online PowerShell e un file CSV (delimitato da virgole) in blocco importare contatti esterni in Exchange Online. È un processo in tre fasi:</span><span class="sxs-lookup"><span data-stu-id="099b2-p101">Does your company have lots of existing business contacts that you want to include in the shared address book (also called the global address list) in Exchange Online? Do you want to add external contacts as members of distribution groups, just like you can with users inside your company? If so, you can use Exchange Online PowerShell and a CSV (Comma Separated Value) file to bulk import external contacts into Exchange Online. It's a three-step process:</span></span>
  
[<span data-ttu-id="099b2-109">Passaggio 1: Creare un file CSV contenente informazioni sui contatti esterni</span><span class="sxs-lookup"><span data-stu-id="099b2-109">Step 1: Create a CSV file that contains information about the external contacts</span></span>](#step-1-create-a-csv-file-that-contains-information-about-the-external-contacts)

[<span data-ttu-id="099b2-110">Passaggio 2: Creare contatti esterni PowerShell</span><span class="sxs-lookup"><span data-stu-id="099b2-110">Step 2: Create the external contacts with PowerShell</span></span>](#step-2-create-the-external-contacts-with-powershell) 

[<span data-ttu-id="099b2-111">Passaggio 3: Aggiungere informazioni alle proprietà dei contatti esterni</span><span class="sxs-lookup"><span data-stu-id="099b2-111">Step 3: Add information to the properties of the external contacts</span></span>](#step-3-add-information-to-the-properties-of-the-external-contacts)

<span data-ttu-id="099b2-112">Dopo aver completato la procedura seguente per importare contatti, è possibile eseguire le seguenti attività aggiuntive:</span><span class="sxs-lookup"><span data-stu-id="099b2-112">After you complete these steps to import contacts, you can perform these additional tasks:</span></span>
  
- [<span data-ttu-id="099b2-113">Aggiungere i contatti più esterni</span><span class="sxs-lookup"><span data-stu-id="099b2-113">Add more external contacts</span></span>](bulk-import-external-contacts.md#AddMore)
  
- [<span data-ttu-id="099b2-114">Nascondere i contatti esterni nella Rubrica condivisa</span><span class="sxs-lookup"><span data-stu-id="099b2-114">Hide external contacts from the shared address book</span></span>](bulk-import-external-contacts.md#Hide)
  
## <a name="step-1-create-a-csv-file-that-contains-information-about-the-external-contacts"></a><span data-ttu-id="099b2-115">Passaggio 1: Creare un file CSV contenente informazioni sui contatti esterni</span><span class="sxs-lookup"><span data-stu-id="099b2-115">Step 1: Create a CSV file that contains information about the external contacts</span></span>

<span data-ttu-id="099b2-116">Il primo passaggio consiste nel creare un file CSV contenente informazioni su ogni contatto esterno che si desidera importare in Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="099b2-116">The first step is to create a CSV file that contains information about each external contact that you want to import to Exchange Online.</span></span> 
  
1. <span data-ttu-id="099b2-117">Copiare il testo seguente in un file di testo nel blocco note e salvarlo sul desktop come un file CSV con il suffisso nome file. csv; ad esempio, ExternalContacts.csv.</span><span class="sxs-lookup"><span data-stu-id="099b2-117">Copy the following text to a text file in NotePad, and save it to your desktop as a CSV file by using a filename suffix of .csv; for example, ExternalContacts.csv.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="099b2-118">Se la lingua dell'utente contiene caratteri speciali (ad esempio **å** **ä**e **ö** in svedese) Salva il file CSV con UTF-8 o altra codifica Unicode quando si salva il file nel blocco note.</span><span class="sxs-lookup"><span data-stu-id="099b2-118">If your language contains special characters (such as **å**, **ä**, and **ö** in Swedish) save the CSV file with UTF-8 or other Unicode encoding when you save the file in NotePad.</span></span> 
  
    ```
    ExternalEmailAddress,Name,FirstName,LastName,StreetAddress,City,StateorProvince,PostalCode,Phone,MobilePhone,Pager,HomePhone,Company,Title,OtherTelephone,Department,CountryOrRegion,Fax,Initials,Notes,Office,Manager
    danp@fabrikam.com,Dan Park,Dan,Park,1234 23rd Ave,Golden,CO,80215,206-111-1234,303-900-1234,555-1212,123-456-7890,Fabrikam,Shipping clerk,555-5555,Shipping,US,123-4567,R.,Good worker,31/1663,Dan Park
    pilar@contoso.com,Pilar Pinilla,Pilar,Pinilla,1234 Main St.,Seattle,WA,98017,206-555-0100,206-555-0101,206-555-0102,206-555-1234,Contoso,HR Manager,206-555-0104,Executive,US,206-555-0105,P.,Technical decision maker,31/1000,Dan Park 
    ```

    <span data-ttu-id="099b2-p102">La prima riga o una riga di intestazione, del file CSV sono elencate le proprietà dei contatti che possono essere utilizzati durante l'importazione in Exchange Online. I nomi di proprietà sono separati da una virgola. Ogni riga sotto la riga di intestazione rappresenta i valori delle proprietà per l'importazione di un contatto esterno.</span><span class="sxs-lookup"><span data-stu-id="099b2-p102">The first row, or header row, of the CSV file lists the properties of contacts that can be used when you import them to Exchange Online. Each property name is separated by a comma. Each row under the header row represents the property values for importing a single external contact.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="099b2-p103">Il testo incluso dati di esempio, è possibile eliminare. Ma non eliminare o modificare la prima riga (intestazione). Contiene tutte le proprietà per i contatti esterni.</span><span class="sxs-lookup"><span data-stu-id="099b2-p103">This text includes sample data, which you can delete. But don't delete or change the first (header) row. It contains all of the properties for the external contacts.</span></span> 
  
2. <span data-ttu-id="099b2-125">Aprire il file CSV in Microsoft Excel per modificare il file CSV perché è molto più semplice utilizzare Excel per modificare il file CSV.</span><span class="sxs-lookup"><span data-stu-id="099b2-125">Open the CSV file in Microsoft Excel to edit the CSV file because it's much easier to use Excel to edit the CSV file.</span></span>
    
3. <span data-ttu-id="099b2-p104">Creare una riga per ogni contatto che si desidera importare in Exchange Online. Popolare il numero di celle come possibili. Tali informazioni verranno visualizzate nella Rubrica condivisa per ogni contatto.</span><span class="sxs-lookup"><span data-stu-id="099b2-p104">Create a row for each contact that you want to import to Exchange Online. Populate as many of the cells as possible. This information will be displayed in the shared address book for each contact.</span></span> 
    
    > [!IMPORTANT]
    >  <span data-ttu-id="099b2-p105">Le proprietà seguenti, che sono i primi quattro elementi nella riga di intestazione, sono necessari per creare un contatto esterno, è necessario specificare nel file CSV: **ExternalEmailAddress**, **nome**, **FirstName**, **LastName**. Il comando PowerShell che viene eseguita nel passaggio 2 utilizzerà i valori per le proprietà per creare i contatti.</span><span class="sxs-lookup"><span data-stu-id="099b2-p105">The following properties (which are the first four items in the header row) are required to create an external contact and must be populated in the CSV file: **ExternalEmailAddress**, **Name**, **FirstName**, **LastName**. The PowerShell command that you run in Step 2 will use the values for these properties to create the contacts.</span></span> 

## <a name="step-2-create-the-external-contacts-with-powershell"></a><span data-ttu-id="099b2-131">Passaggio 2: Creare contatti esterni PowerShell</span><span class="sxs-lookup"><span data-stu-id="099b2-131">Step 2: Create the external contacts with PowerShell</span></span>

<span data-ttu-id="099b2-132">Il passaggio successivo consiste nell'utilizzare il file CSV creato nel passaggio 1 e PowerShell al blocco importare contatti esterni elencati nel file CSV in Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="099b2-132">The next step is to use the CSV file that you created in Step 1 and PowerShell to bulk import the external contacts listed in the CSV file to Exchange Online.</span></span> 
  
1.  <span data-ttu-id="099b2-p106">Connettere PowerShell all'organizzazione Exchange Online. Per istruzioni dettagliate, vedere [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=396554). Assicurarsi di utilizzare il nome utente e la password per l'account amministratore globale di Office 365 durante la connessione a Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="099b2-p106">Connect PowerShell to your Exchange Online organization. For step-by-step instructions, see [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=396554). Be sure to use the user name and password for your Office 365 global administrator account when you connect to Exchange Online PowerShell.</span></span> 
    
2. <span data-ttu-id="099b2-136">Dopo essersi connessi PowerShell in Exchange Online, passare alla cartella desktop di cui è stato salvato il file CSV nel passaggio 1; ad esempio `C:\Users\Administrator\desktop`.</span><span class="sxs-lookup"><span data-stu-id="099b2-136">After you connect PowerShell to Exchange Online, go to the desktop folder where you saved the CSV file in Step 1; for example `C:\Users\Administrator\desktop`.</span></span>
    
3. <span data-ttu-id="099b2-137">Eseguire il comando seguente per creare contatti esterni:</span><span class="sxs-lookup"><span data-stu-id="099b2-137">Run the following command to create the external contacts:</span></span>

    ```
    Import-Csv .\ExternalContacts.csv|%{New-MailContact -Name $_.Name -DisplayName $_.Name -ExternalEmailAddress $_.ExternalEmailAddress -FirstName $_.FirstName -LastName $_.LastName}
    ```

    <span data-ttu-id="099b2-p107">Potrebbero richiedere alcuni minuti per creare nuovi contatti, in base al numero che si sta importando. Al termine del comando PowerShell in esecuzione, visualizza un elenco di nuovi contatti che sono stati creati.</span><span class="sxs-lookup"><span data-stu-id="099b2-p107">It might take a while to create the new contacts, depending on how many you're importing. When the command is finished running, PowerShell displays a list of the new contacts that were created.</span></span> 
    
4. <span data-ttu-id="099b2-140">Per visualizzare i nuovi contatti esterni, passare all'interfaccia di amministrazione di Exchange (EAC) e quindi fare clic su **destinatari** \> **contatti**.</span><span class="sxs-lookup"><span data-stu-id="099b2-140">To view the new external contacts, go to the Exchange admin center (EAC), and then click **Recipients** \> **Contacts**.</span></span> 
    
    > [!TIP]
    > <span data-ttu-id="099b2-141">Per istruzioni per la connessione a EAC, vedere [Exchange admin center in Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=328197).</span><span class="sxs-lookup"><span data-stu-id="099b2-141">For instructions for connecting to the EAC, see [Exchange admin center in Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=328197).</span></span> 
  
5. <span data-ttu-id="099b2-142">Se necessario, fare clic su **Aggiorna** ![icona Aggiorna](media/O365-MDM-Policy-RefreshIcon.gif) per aggiornare l'elenco e visualizzare i contatti esterni che sono stati importati.</span><span class="sxs-lookup"><span data-stu-id="099b2-142">If necessary, click **Refresh** ![Refresh icon](media/O365-MDM-Policy-RefreshIcon.gif) to update the list and see the external contacts that were imported.</span></span> 
    
    <span data-ttu-id="099b2-143">I contatti importati apparirà nella Rubrica condivisa in Outlook e Outlook sul web.</span><span class="sxs-lookup"><span data-stu-id="099b2-143">The imported contacts will appear in the shared address book in Outlook and Outlook on the web.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="099b2-144">È inoltre possibile visualizzare i contatti nell'interfaccia di amministrazione di Office 365 accedendo a **utenti** \> **contatti**.</span><span class="sxs-lookup"><span data-stu-id="099b2-144">You can also view the contacts in the Office 365 admin center by going to **Users** \> **Contacts**.</span></span> 

## <a name="step-3-add-information-to-the-properties-of-the-external-contacts"></a><span data-ttu-id="099b2-145">Passaggio 3: Aggiungere informazioni alle proprietà dei contatti esterni</span><span class="sxs-lookup"><span data-stu-id="099b2-145">Step 3: Add information to the properties of the external contacts</span></span>

<span data-ttu-id="099b2-p108">Dopo aver eseguito il comando nel passaggio 2, vengono creati i contatti esterni, ma non contengono le informazioni contatto o dell'organizzazione, ovvero le informazioni dalla maggior parte delle celle nel file CSV. Ciò avviene perché quando si creano nuovi contatti esterni, vengono popolate solo le proprietà necessarie. Non bisogna preoccuparsi se non si dispongano di tutte le informazioni popolate nel file CSV. Se non è presente, non verranno aggiunti.</span><span class="sxs-lookup"><span data-stu-id="099b2-p108">After you run the command in Step 2, the external contacts are created, but they don't contain any of the contact or organization information, which is the information from the most of the cells in the CSV file. This is because when you create new external contacts, only the required properties are populated. Don't worry if you don't have all the information populated in the CSV file. If it's not there, it won't be added.</span></span>
  
1.  <span data-ttu-id="099b2-p109">Connettere PowerShell all'organizzazione Exchange Online. Per istruzioni dettagliate, vedere [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=396554).</span><span class="sxs-lookup"><span data-stu-id="099b2-p109">Connect PowerShell to your Exchange Online organization. For step-by-step instructions, see [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=396554).</span></span>
    
2. <span data-ttu-id="099b2-152">Passare alla cartella desktop di cui è stato salvato il file CSV nel passaggio 1; ad esempio `C:\Users\Administrator\desktop`.</span><span class="sxs-lookup"><span data-stu-id="099b2-152">Go to the desktop folder where you saved the CSV file in Step 1; for example `C:\Users\Administrator\desktop`.</span></span>
    
3. <span data-ttu-id="099b2-153">Eseguire i due comandi seguenti per aggiungere le altre proprietà del file CSV per i contatti esterni creato nel passaggio 2.</span><span class="sxs-lookup"><span data-stu-id="099b2-153">Run the following two commands to add the other properties from the CSV file to the external contacts that you created in Step 2.</span></span>
    
    ```
    $Contacts = Import-CSV .\ExternalContacts.csv
  
    ```

    ```
    $contacts | ForEach {Set-Contact $_.Name -StreetAddress $_.StreetAddress -City $_.City -StateorProvince $_.StateorProvince -PostalCode $_.PostalCode -Phone $_.Phone -MobilePhone $_.MobilePhone -Pager $_.Pager -HomePhone $_.HomePhone -Company $_.Company -Title $_.Title -OtherTelephone $_.OtherTelephone -Department $_.Department -Fax $_.Fax -Initials $_.Initials -Notes  $_.Notes -Office $_.Office -Manager $_.Manager}
    ```

    > [!NOTE]
    > <span data-ttu-id="099b2-p110">Il parametro _Manager_ può essere problematico. Se la cella è vuota nel file CSV, si verificherà un errore e nessuna delle informazioni sulle proprietà verrà aggiunto al contatto. Se non è necessario specificare un proprietario, quindi eliminare ` -Manager $_.Manager ` del comando PowerShell precedente.</span><span class="sxs-lookup"><span data-stu-id="099b2-p110">The  _Manager_ parameter might be problematic. If the cell is blank in the CSV file, you will get an error and none of the property information will be added to the contact. If you don't need to specify a manager, then just delete  ` -Manager $_.Manager ` from the previous PowerShell command.</span></span> 
  
    <span data-ttu-id="099b2-157">Nuovamente, potrebbe richiedere un po' di tempo per aggiornare i contatti in base al numero è stato importato nel passaggio 1.</span><span class="sxs-lookup"><span data-stu-id="099b2-157">Again, it might take a while to update the contacts, depending on how many you imported in Step 1.</span></span> 
    
4. <span data-ttu-id="099b2-158">Per verificare che le proprietà sono state aggiunte ai contatti:</span><span class="sxs-lookup"><span data-stu-id="099b2-158">To verify that the properties were added to the contacts:</span></span> 
    
1. <span data-ttu-id="099b2-159">Nell'interfaccia di amministrazione di Exchange accedere a **Destinatari** \> **Contatti**.</span><span class="sxs-lookup"><span data-stu-id="099b2-159">In the EAC, go to **Recipients** \> **Contacts**.</span></span>
    
2. <span data-ttu-id="099b2-160">Fare clic su un contatto e quindi fare clic su **Modifica** ![sull'icona Modifica](media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif) per visualizzare le proprietà del contatto.</span><span class="sxs-lookup"><span data-stu-id="099b2-160">Click a contact and then click **Edit** ![Edit icon](media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif) to display the contact's properties.</span></span> 
    
<span data-ttu-id="099b2-p111">Questo è tutto! Gli utenti possono visualizzare i contatti e le informazioni aggiuntive nella Rubrica di Outlook e Outlook sul web.</span><span class="sxs-lookup"><span data-stu-id="099b2-p111">That's it! Users can see the contacts and the additional information in the address book Outlook and Outlook on the web.</span></span>
  
## <a name="add-more-external-contacts"></a><span data-ttu-id="099b2-163">Aggiungere i contatti più esterni</span><span class="sxs-lookup"><span data-stu-id="099b2-163">Add more external contacts</span></span>

<span data-ttu-id="099b2-p112">È possibile ripetere i passaggi da 1 a passaggio 3 per aggiungere nuovi contatti esterni di Exchange Online. Gli utenti dell'azienda appena possibile aggiungere una nuova riga nel file CSV per il nuovo contatto. È quindi possibile eseguire i comandi di PowerShell di passaggio 2 e passaggio 3 per creare e aggiungere informazioni ai nuovi contatti.</span><span class="sxs-lookup"><span data-stu-id="099b2-p112">You can repeat Steps 1 through Step 3 to add new external contacts in Exchange Online. You or users in your company can just add a new row in the CSV file for the new contact. Then you can run the PowerShell commands from Step 2 and Step 3 to create and add information to the new contacts.</span></span>
  
> [!NOTE]
> <span data-ttu-id="099b2-p113">Quando si esegue il comando per creare nuovi contatti, potrebbe essere visualizzato un errore indicante che i contatti che sono stati creati in precedenza già esistano. Ma viene creato un nuovo contatto aggiunto il file CSV.</span><span class="sxs-lookup"><span data-stu-id="099b2-p113">When you run the command to create new contacts, you might get an error saying that the contacts that were created earlier already exist. But any new contact added to the CSV file is created.</span></span> 
  
## <a name="hide-external-contacts-from-the-shared-address-book"></a><span data-ttu-id="099b2-169">Nascondere i contatti esterni nella Rubrica condivisa ></span><span class="sxs-lookup"><span data-stu-id="099b2-169">Hide external contacts from the shared address book></span></span>

<span data-ttu-id="099b2-p114">Alcune aziende possono utilizzare i contatti esterni solo in modo che possono essere aggiunti come membri dei gruppi di distribuzione. In questo scenario è possibile nascondere i contatti esterni nella Rubrica condivisa. Ecco come:</span><span class="sxs-lookup"><span data-stu-id="099b2-p114">Some companies may use external contacts only so they can be added as members of distribution groups. In this scenario, they may want to hide external contacts from the shared address book. Here's how:</span></span>
  
1.  <span data-ttu-id="099b2-p115">Connettere PowerShell all'organizzazione Exchange Online. Per istruzioni dettagliate, vedere [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=396554).</span><span class="sxs-lookup"><span data-stu-id="099b2-p115">Connect PowerShell to your Exchange Online organization. For step-by-step instructions, see [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=396554).</span></span>
    
2. <span data-ttu-id="099b2-175">Per nascondere un singolo contatto esterno, eseguire il comando seguente.</span><span class="sxs-lookup"><span data-stu-id="099b2-175">To hide a single external contact, run the following command.</span></span>
    
    ```
    Set-MailContact <external contact> -HiddenFromAddressListsEnabled $true 
    ```
 
    <span data-ttu-id="099b2-176">Ad esempio, per nascondere Pilar Pinilla dalla Rubrica condivisa, eseguire questo comando:</span><span class="sxs-lookup"><span data-stu-id="099b2-176">For example, to hide Pilar Pinilla from the shared address book, run this command:</span></span>

    ```
    Set-MailContact "Pilar Pinilla" -HiddenFromAddressListsEnabled $true
    ```
   
3. <span data-ttu-id="099b2-177">Per nascondere tutti i contatti esterni nella Rubrica condivisa, eseguire questo comando:</span><span class="sxs-lookup"><span data-stu-id="099b2-177">To hide all external contacts from the shared address book, run this command:</span></span>

    ```
    Get-Contact -ResultSize unlimited -Filter {(RecipientTypeDetails -eq 'MailContact')} | Set-MailContact -HiddenFromAddressListsEnabled $true  
    ```

<span data-ttu-id="099b2-178">Dopo aver nasconderle, contatti esterni non vengono visualizzati nella Rubrica condivisa, ma è comunque possibile aggiungerli come membri del gruppo di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="099b2-178">After you hide them, external contacts aren't displayed in the shared address book, but you can still add them as members of a distribution group.</span></span>
