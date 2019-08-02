---
title: Gestione utenti di posta in EOP
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 12/9/2016
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 4bfaf2ab-e633-4227-8bde-effefb41a3db
description: La definizione degli utenti di posta è una parte importante della gestione del servizio Exchange Online Protection (EOP).
ms.openlocfilehash: 6d982b635513050d931397bbc517ae3d76ee3752
ms.sourcegitcommit: bc25ea19c0b6d318751eadc4f27902b0054d5e2b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/01/2019
ms.locfileid: "36054728"
---
# <a name="manage-mail-users-in-eop"></a><span data-ttu-id="d4862-103">Gestire utenti di posta in Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="d4862-103">Manage mail users in EOP</span></span>

<span data-ttu-id="d4862-p101">La definizione degli utenti di posta è una parte importante della gestione del servizio Exchange Online Protection (EOP). In EOP è possibile gestire gli utenti in diversi modi.</span><span class="sxs-lookup"><span data-stu-id="d4862-p101">Defining mail users is an important part of managing the Exchange Online Protection (EOP) service. There are several ways that you can manage users in EOP:</span></span>
  
- <span data-ttu-id="d4862-106">Utilizzare la sincronizzazione della directory per gestire gli utenti di posta: se in azienda sono presenti account utente in un ambiente di Active Directory locale, è possibile sincronizzarli con Azure Active Directory (AD), dove una copia di tali account è memorizzata nel cloud.</span><span class="sxs-lookup"><span data-stu-id="d4862-106">Use directory synchronization to manage mail users: If your company has existing user accounts in an on-premises Active Directory environment, you can synchronize those accounts to Azure Active Directory (AD), where a copy of the accounts is stored in the cloud.</span></span> <span data-ttu-id="d4862-107">Durante la sincronizzazione degli account utente esistenti su Azure Active Directory, è possibile visualizzare tali utenti nel riquadro **Destinatari** nell'interfaccia di amministrazione di Exchange (EAC).</span><span class="sxs-lookup"><span data-stu-id="d4862-107">When you synchronize your existing user accounts to Azure Active Directory, you can view those users in the **Recipients** pane of the Exchange admin center (EAC).</span></span> <span data-ttu-id="d4862-108">Si consiglia di utilizzare la sincronizzazione delle directory.</span><span class="sxs-lookup"><span data-stu-id="d4862-108">Using directory synchronization is recommended.</span></span> 
    
- <span data-ttu-id="d4862-109">Utilizzare il valore EAC per gestire gli utenti di posta: aggiungere e gestire gli utenti di posta direttamente in EAC.</span><span class="sxs-lookup"><span data-stu-id="d4862-109">Use the EAC to manage mail users: Add and manage mail users directly in the EAC.</span></span> <span data-ttu-id="d4862-110">Si tratta del modo più semplice per aggiungere utenti di posta elettronica ed è utile per aggiungere un utente alla volta.</span><span class="sxs-lookup"><span data-stu-id="d4862-110">This is the easiest way to add mail users and is useful for adding one user at a time.</span></span>
    
- <span data-ttu-id="d4862-111">Utilizzare Windows PowerShell remoto per gestire gli utenti di posta elettronica: aggiungere e gestire utenti di posta elettronica eseguendo Windows PowerShell remoto.</span><span class="sxs-lookup"><span data-stu-id="d4862-111">Use remote Windows PowerShell to manage mail users: Add and manage mail users by running remote Windows PowerShell.</span></span> <span data-ttu-id="d4862-112">Questo metodo è utile per aggiungere più record e creare script.</span><span class="sxs-lookup"><span data-stu-id="d4862-112">This method is useful for adding multiple records and creating scripts.</span></span>
    
> [!NOTE]
> <span data-ttu-id="d4862-113">È possibile aggiungere utenti nell'interfaccia di amministrazione di Microsoft 365, ma questi utenti non possono essere utilizzati come destinatari della posta.</span><span class="sxs-lookup"><span data-stu-id="d4862-113">You can add users in the Microsoft 365 admin center, however these users can't be used as mail recipients.</span></span> 
  
## <a name="before-you-begin"></a><span data-ttu-id="d4862-114">Informazioni preliminari</span><span class="sxs-lookup"><span data-stu-id="d4862-114">Before you begin</span></span>

- <span data-ttu-id="d4862-p105">Le procedure descritte in questo argomento richiedono autorizzazioni specifiche. Vedere ciascuna procedura per le informazioni sulle autorizzazioni necessarie.</span><span class="sxs-lookup"><span data-stu-id="d4862-p105">Procedures in this topic require specific permissions. See each procedure for its permissions information.</span></span>
    
- <span data-ttu-id="d4862-117">Per informazioni sui tasti di scelta rapida che è possibile utilizzare con le procedure in questo argomento, vedere **Tasti di scelta rapida nell'interfaccia di amministrazione di Exchange**.</span><span class="sxs-lookup"><span data-stu-id="d4862-117">For information about keyboard shortcuts that may apply to the procedures in this topic, see **Keyboard shortcuts in the Exchange admin center**.</span></span>
    
> [!TIP]
> <span data-ttu-id="d4862-p106">Problemi? È possibile richiedere supporto nei forum di Exchange. I forum sono disponibili sui seguenti siti: [Exchange Server](https://go.microsoft.com/fwlink/p/?linkId=60612),[Exchange Online](https://go.microsoft.com/fwlink/p/?linkId=267542) o [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351).</span><span class="sxs-lookup"><span data-stu-id="d4862-p106">Having problems? Ask for help in the Exchange forums. Visit the forums at [Exchange Server](https://go.microsoft.com/fwlink/p/?linkId=60612),[Exchange Online](https://go.microsoft.com/fwlink/p/?linkId=267542), or [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351).</span></span> 
  
## <a name="use-directory-synchronization-to-manage-mail-users"></a><span data-ttu-id="d4862-121">Utilizzare la sincronizzazione della directory per gestire gli utenti di posta</span><span class="sxs-lookup"><span data-stu-id="d4862-121">Use directory synchronization to manage mail users</span></span>

<span data-ttu-id="d4862-122">Nella presente sezione vengono fornite informazioni sulla gestione degli utenti di posta elettronica utilizzando la sincronizzazione della directory.</span><span class="sxs-lookup"><span data-stu-id="d4862-122">This section provides information about managing email users by using directory synchronization.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="d4862-123">Se si utilizza la sincronizzazione della directory per gestire i destinatari, è comunque possibile aggiungere e gestire gli utenti nell'interfaccia di amministrazione di Microsoft 365, ma non verranno sincronizzati con Active Directory locale.</span><span class="sxs-lookup"><span data-stu-id="d4862-123">If you use directory synchronization to manage your recipients, you can still add and manage users in the Microsoft 365 admin center, but they will not be synchronized with your on-premises Active Directory.</span></span> <span data-ttu-id="d4862-124">Tuttavia questi non verranno sincronizzati con Active Directory in locale poiché la sincronizzazione della directory sincronizza solamente i destinatari dall'Active Directory locale al cloud.</span><span class="sxs-lookup"><span data-stu-id="d4862-124">This is because directory synchronization only syncs recipients from your on-premises Active Directory to the cloud.</span></span> 
  
> [!TIP]
>  <span data-ttu-id="d4862-125">Si consiglia di utilizzare la sincronizzazione della directory con le seguenti funzionalità: > **Elenchi di mittenti attendibili e bloccati di Outlook**: se sincronizzati con il servizio, questi elenchi avranno la precedenza sul filtro di protezione da posta indesiderata del servizio.</span><span class="sxs-lookup"><span data-stu-id="d4862-125">Using directory synchronization is recommended for use with the following features: > **Outlook safe sender and blocked sender lists** - When synchronized to the service, these lists will take precedence over spam filtering in the service.</span></span> <span data-ttu-id="d4862-126">Ciò consente agli utenti di gestire i propri elenchi di utenti attendibili o bloccati a livello di organizzazione o a livello di singolo utente.</span><span class="sxs-lookup"><span data-stu-id="d4862-126">This lets users manage their own safe sender and blocked sender lists on a per-user or per-domain basis.</span></span><span data-ttu-id="d4862-127"> > **Directory Based Edge Blocking (DBEB)**: per ulteriori informazioni su DBEB, vedere [Use Directory Based Edge Blocking to Reject Messages Sent to Invalid Recipients](http://technet.microsoft.com/library/ca7b7416-92ed-40ad-abdb-695be46ea2e4.aspx).</span><span class="sxs-lookup"><span data-stu-id="d4862-127"> > **Directory Based Edge Blocking (DBEB)** - For more information about DBEB, see [Use Directory Based Edge Blocking to Reject Messages Sent to Invalid Recipients](http://technet.microsoft.com/library/ca7b7416-92ed-40ad-abdb-695be46ea2e4.aspx).</span></span><span data-ttu-id="d4862-128"> > **Quarantena posta indesiderata utente finale**: per accedere alla quarantena posta indesiderata utente finale, gli utenti finali devono possedere un ID e una password per utenti di Office 365 validi.</span><span class="sxs-lookup"><span data-stu-id="d4862-128"> > **End user spam quarantine** - In order to access the end user spam quarantine, end users must have a valid Office 365 user ID and password.</span></span> <span data-ttu-id="d4862-129">I clienti EOP che proteggono le cassette postali locali devono essere utenti di posta elettronica validi.</span><span class="sxs-lookup"><span data-stu-id="d4862-129">EOP customers protecting on-premises mailboxes must be valid email users.</span></span><span data-ttu-id="d4862-130"> > **Regole del flusso di posta** : quando si utilizza la sincronizzazione della directory, gli utenti e i gruppi di Active Directory esistenti vengono caricati automaticamente nel cloud ed è quindi possibile creare regole del flusso di posta (note anche come regole di trasporto) che si rivolgono a utenti specifici e/o gruppi senza dover aggiungerli manualmente tramite l'EAC o Exchange Online Protection PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d4862-130"> > **Mail flow rules** - When you use directory synchronization, your existing Active Directory users and groups are automatically uploaded to the cloud, and you can then create mail flow rules (also known as transport rules) that target specific users and/or groups without having to manually add them via the the EAC or Exchange Online Protection PowerShell.</span></span> <span data-ttu-id="d4862-131">Si noti che non è possibile sincronizzare i [gruppi di distribuzione dinamici](https://go.microsoft.com/fwlink/?LinkId=507569) tramite la sincronizzazione delle directory.</span><span class="sxs-lookup"><span data-stu-id="d4862-131">Note that [dynamic distribution groups](https://go.microsoft.com/fwlink/?LinkId=507569) can't be synchronized via directory synchronization.</span></span> 
  
 <span data-ttu-id="d4862-132">**Informazioni preliminari**</span><span class="sxs-lookup"><span data-stu-id="d4862-132">**Before you begin**</span></span>
  
<span data-ttu-id="d4862-133">Ottenere le autorizzazioni necessarie e preparare la sincronizzazione della directory, come descritto in [Preparazione della sincronizzazione della directory](https://go.microsoft.com/fwlink/p/?LinkId=308908).</span><span class="sxs-lookup"><span data-stu-id="d4862-133">Get the necessary permissions and prepare for directory synchronization, as described in [Prepare for directory synchronization](https://go.microsoft.com/fwlink/p/?LinkId=308908).</span></span>
  
### <a name="to-synchronize-user-directories"></a><span data-ttu-id="d4862-134">Per sincronizzare le directory degli utenti</span><span class="sxs-lookup"><span data-stu-id="d4862-134">To synchronize user directories</span></span>

1. <span data-ttu-id="d4862-135">Attivare la sincronizzazione della directory, come descritto in [Attivare la sincronizzazione della directory](https://go.microsoft.com/fwlink/p/?LinkId=308909).</span><span class="sxs-lookup"><span data-stu-id="d4862-135">Activate directory synchronization, as described in [Activate directory synchronization](https://go.microsoft.com/fwlink/p/?LinkId=308909).</span></span>
    
2. <span data-ttu-id="d4862-136">Impostare il computer per la sincronizzazione della directory, come descritto in [Impostare il computer per la sincronizzazione della directory](http://go.microsoft.com/fwlink/p/?LinkId=308911).</span><span class="sxs-lookup"><span data-stu-id="d4862-136">Set up your directory synchronization computer, as described in [Set up your directory sync computer](http://go.microsoft.com/fwlink/p/?LinkId=308911).</span></span>
    
3. <span data-ttu-id="d4862-137">Sincronizzare le directory, come descritto in [Utilizzare Configurazione guidata per sincronizzare le directory](http://go.microsoft.com/fwlink/?LinkId=308912).</span><span class="sxs-lookup"><span data-stu-id="d4862-137">Synchronize your directories, as described in [Use the Configuration Wizard to sync your directories](http://go.microsoft.com/fwlink/?LinkId=308912).</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="d4862-p109">Al termine della Configurazione guidata dello strumento di sincronizzazione di Azure Active Directory, viene creato l'account **MSOL_AD_SYNC** nella foresta Active Directory. Tale account viene utilizzato per leggere e sincronizzare le informazioni dell'Active Directory locale. Per un corretto funzionamento della sincronizzazione della directory, assicurarsi che TCP 443 sul server di sincronizzazione della directory locale sia aperto.</span><span class="sxs-lookup"><span data-stu-id="d4862-p109">When you finish the Azure Active Directory Sync Tool Configuration Wizard, the **MSOL_AD_SYNC** account is created in your Active Directory forest. This account is used to read and synchronize your on-premises Active Directory information. In order for directory synchronization to work correctly, make sure that TCP 443 on your local directory synchronization server is open.</span></span> 
  
  4. <span data-ttu-id="d4862-141">Gestione della sincronizzazione della directory, come descritto in [Gestione della sincronizzazione della directory](http://go.microsoft.com/fwlink/p/?LinkId=308915).</span><span class="sxs-lookup"><span data-stu-id="d4862-141">Manage directory synchronization, as described in [Manage directory synchronization](http://go.microsoft.com/fwlink/p/?LinkId=308915).</span></span>
    
  5. <span data-ttu-id="d4862-p110">Verificare che EOP sia sincronizzato correttamente. In EAC, andare a **Destinatari** \> **Contatti** e verificare che l'elenco dei destinatari sia stato sincronizzato correttamente dall'ambiente in locale.</span><span class="sxs-lookup"><span data-stu-id="d4862-p110">Verify that EOP is synchronizing correctly. In the EAC, go to **Recipients** \> **Contacts** and view that the list of users was correctly synchronized from your on-premises environment.</span></span> 
    
## <a name="use-the-eac-to-manage-mail-users"></a><span data-ttu-id="d4862-144">Utilizzare il valore EAC per gestire gli utenti di posta</span><span class="sxs-lookup"><span data-stu-id="d4862-144">Use the EAC to manage mail users</span></span>

<span data-ttu-id="d4862-145">In questa sezione vengono fornite informazioni sull'aggiunta e la gestione degli utenti di posta elettronica direttamente in EAC.</span><span class="sxs-lookup"><span data-stu-id="d4862-145">This section provides information about adding and managing email users directly in the EAC.</span></span>
  
 <span data-ttu-id="d4862-146">**Informazioni preliminari**</span><span class="sxs-lookup"><span data-stu-id="d4862-146">**Before you begin**</span></span>
  
<span data-ttu-id="d4862-p111">Per eseguire queste procedure, è necessario disporre delle autorizzazioni appropriate. Per sapere quali autorizzazioni sono necessarie, vedere voce "Utente, Contatti e Gruppi ruolo" in [Autorizzazioni di funzionalità in EOP](feature-permissions-in-eop.md).</span><span class="sxs-lookup"><span data-stu-id="d4862-p111">You need to be assigned permissions before you can perform this procedure or procedures. To see what permissions you need, see the "Users, Contacts, and Role Groups" entry in [Feature permissions in EOP](feature-permissions-in-eop.md).</span></span>
  
### <a name="to-add-a-mail-user-in-the-eac"></a><span data-ttu-id="d4862-149">Per aggiungere un utente di posta in EAC</span><span class="sxs-lookup"><span data-stu-id="d4862-149">To add a mail user in the EAC</span></span>

1. <span data-ttu-id="d4862-150">Per creare un utente di posta elettronica, andare a **Destinatari** \> **Contatti** in EAC, quindi fare clic su **Nuovo +**.</span><span class="sxs-lookup"><span data-stu-id="d4862-150">Create an email user by going to go to **Recipients** \> **Contacts** in the EAC, and then clicking **New +**.</span></span>
    
2. <span data-ttu-id="d4862-151">Nella pagina **Nuovo utente di posta**, immettere le informazioni dell'utente, incluse le seguenti:</span><span class="sxs-lookup"><span data-stu-id="d4862-151">On the **New mail user** page, enter the user's information, including the following:</span></span> 
    
   ****

|<span data-ttu-id="d4862-152">**Proprietà utente della posta**</span><span class="sxs-lookup"><span data-stu-id="d4862-152">**Mail user property**</span></span>|<span data-ttu-id="d4862-153">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="d4862-153">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="d4862-154">**Nome**, **Iniziali**, and **Cognome**</span><span class="sxs-lookup"><span data-stu-id="d4862-154">**First name**, **Initials**, and **Last name**</span></span> <br/> |<span data-ttu-id="d4862-155">Digitare il nome completo dell'utente nelle caselle appropriate.</span><span class="sxs-lookup"><span data-stu-id="d4862-155">Type the user's full name in the appropriate boxes.</span></span>  <br/> |
|<span data-ttu-id="d4862-156">**Nome visualizzato**</span><span class="sxs-lookup"><span data-stu-id="d4862-156">**Display name**</span></span> <br/> |<span data-ttu-id="d4862-p112">Digitare un nome, utilizzando un massimo di 64 caratteri. Per impostazione predefinita, questa casella contiene i nomi nelle caselle **Nome**, **Iniziali** e **Cognome**. Il nome visualizzato è obbligatorio.  </span><span class="sxs-lookup"><span data-stu-id="d4862-p112">Type a name, using up to 64 characters. By default, this box shows the names in the **First name**, **Initials**, and **Last name** boxes if any. The display name is required.  </span></span><br/> |
|<span data-ttu-id="d4862-160">**Alias**</span><span class="sxs-lookup"><span data-stu-id="d4862-160">**Alias**</span></span> <br/> |<span data-ttu-id="d4862-p113">Digitare un alias univoco per l'utente, utilizzando un massimo di 64 caratteri. L'alias è obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="d4862-p113">Type a unique alias, using up to 64 characters, for the user. The alias is required.</span></span>  <br/> |
|<span data-ttu-id="d4862-163">**Indirizzo di posta elettronica esterno**</span><span class="sxs-lookup"><span data-stu-id="d4862-163">**External email address**</span></span> <br/> |<span data-ttu-id="d4862-164">Digitare l'indirizzo di posta elettronica esterno dell'utente.</span><span class="sxs-lookup"><span data-stu-id="d4862-164">Type the external email address of the user.</span></span>  <br/> |
|<span data-ttu-id="d4862-165">**ID utente**</span><span class="sxs-lookup"><span data-stu-id="d4862-165">**User id**</span></span> <br/> |<span data-ttu-id="d4862-p114">Digitare il nome utilizzato dall'utente di posta per accedere al servizio. Il nome di accesso dell'utente è costituito da un nome utente a sinistra del simbolo @ e da un suffisso a destra del simbolo. In genere, il suffisso è costituito dal nome di dominio in cui risiede l'account utente.</span><span class="sxs-lookup"><span data-stu-id="d4862-p114">Type the name that the mail user will use to sign in to the service. The user sign-in name consists of a user name on the left side of the at (@) symbol and a suffix on the right side. Typically, the suffix is the domain name in which the user account resides.</span></span>  <br/> |
|<span data-ttu-id="d4862-169">**Nuova password**</span><span class="sxs-lookup"><span data-stu-id="d4862-169">**New password**</span></span> <br/> |<span data-ttu-id="d4862-p115">Digitare la password utilizzata dall'utente di posta per accedere al servizio. Verificare che la password immessa sia conforme ai requisiti di lunghezza, complessità e cronologia del dominio in cui viene creato l'account utente.</span><span class="sxs-lookup"><span data-stu-id="d4862-p115">Type the password that the mail user will use to sign in to the service. Make sure that the password you supply complies with the password length, complexity, and history requirements of the domain in which you're creating the user account.</span></span>  <br/> |
|<span data-ttu-id="d4862-172">**Conferma password**</span><span class="sxs-lookup"><span data-stu-id="d4862-172">**Confirm password**</span></span> <br/> |<span data-ttu-id="d4862-173">Digitare nuovamente la password per confermarla.</span><span class="sxs-lookup"><span data-stu-id="d4862-173">Retype the password to confirm it.</span></span>  <br/> |
   
3. <span data-ttu-id="d4862-p116">Fare clic su **Salva** per creare il nuovo utente di posta elettronica. Il nuovo utente viene visualizzato nell'elenco utenti.</span><span class="sxs-lookup"><span data-stu-id="d4862-p116">Click **Save** to create the new email user. The new user should appear in the list of users.</span></span> 
    
### <a name="to-edit-or-remove-a-mail-user-in-the-eac"></a><span data-ttu-id="d4862-176">Per modificare o rimuovere un utente di posta in EAC</span><span class="sxs-lookup"><span data-stu-id="d4862-176">To edit or remove a mail user in the EAC</span></span>

- <span data-ttu-id="d4862-177">Nell'interfaccia di amministrazione di Exchange accedere a **Destinatari** \> **Contatti**.</span><span class="sxs-lookup"><span data-stu-id="d4862-177">In the EAC, go to **Recipients** \> **Contacts**.</span></span> <span data-ttu-id="d4862-178">Nell'elenco degli utenti, fare clic sull'utente che si desidera visualizzare o modificare, quindi selezionare **modifica** ![icona](../media/ITPro-EAC-EditIcon.gif) modifica per aggiornare le impostazioni utente in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="d4862-178">In the list of users, click the user that you want to view or change, and then select **Edit** ![Edit icon](../media/ITPro-EAC-EditIcon.gif) to update the user settings as needed.</span></span> <span data-ttu-id="d4862-179">È possibile modificare il nome utente, l'alias o le informazioni di contatto e registrare le informazioni dettagliate sul ruolo dell'utente nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="d4862-179">You can change the user's name, alias, or contact information, and you can record detailed information about the user's role in the organization.</span></span> <span data-ttu-id="d4862-180">È inoltre possibile selezionare un utente e scegliere **Rimuovi**![Icona Rimuovi](../media/ITPro-EAC-RemoveIcon.gif) per eliminarlo.</span><span class="sxs-lookup"><span data-stu-id="d4862-180">You can also select a user and then choose **Remove**![Remove icon](../media/ITPro-EAC-RemoveIcon.gif) to delete it.</span></span> 
    
## <a name="use-remote-windows-powershell-to-manage-mail-users"></a><span data-ttu-id="d4862-181">Utilizzare Windows PowerShell remoto per gestire gli utenti di posta elettronica</span><span class="sxs-lookup"><span data-stu-id="d4862-181">Use remote Windows PowerShell to manage mail users</span></span>

<span data-ttu-id="d4862-182">In questa sezione vengono fornite informazioni sull'aggiunta e sulla gestione degli utenti di posta elettronica mediante l'utilizzo di Windows PowerShell remoto.</span><span class="sxs-lookup"><span data-stu-id="d4862-182">This section provides information about adding and managing mail users by using remote Windows PowerShell.</span></span>
  
 <span data-ttu-id="d4862-183">**Informazioni preliminari**</span><span class="sxs-lookup"><span data-stu-id="d4862-183">**Before you begin**</span></span>
  
- <span data-ttu-id="d4862-p118">Per eseguire queste procedure, è necessario disporre delle autorizzazioni appropriate. Per sapere quali autorizzazioni sono necessarie, vedere voce "Utente, Contatti e Gruppi ruolo" in [Autorizzazioni di funzionalità in EOP](feature-permissions-in-eop.md).</span><span class="sxs-lookup"><span data-stu-id="d4862-p118">You need to be assigned permissions before you can perform this procedure or procedures. To see what permissions you need, see the "Users, Contacts, and Role Groups" entry in [Feature permissions in EOP](feature-permissions-in-eop.md).</span></span>
    
- <span data-ttu-id="d4862-186">Tenere presente che quando si creano utenti di posta elettronica mediante cmdlet di PowerShell remoto, si potrebbero incontrare limitazioni.</span><span class="sxs-lookup"><span data-stu-id="d4862-186">Be aware that when creating mail users by using remote PowerShell cmdlets, you may encounter throttling.</span></span>
    
- <span data-ttu-id="d4862-187">Questo cmdlet utilizza un metodo di elaborazione batch che genera un ritardo di qualche minuto nella propagazione prima che i risultati del cmdlet siano visibili.</span><span class="sxs-lookup"><span data-stu-id="d4862-187">This cmdlet uses a batch processing method that results in a propagation delay of a few minutes before the results of the cmdlet are visible.</span></span>
    
- <span data-ttu-id="d4862-188">Per informazioni su come utilizzare Windows PowerShell per la connessione a Exchange Online Protection, vedere [Connessione a Exchange Online Protection tramite PowerShell remota](http://technet.microsoft.com/library/054e0fd7-d465-4572-93f8-a00a9136e4d1.aspx).</span><span class="sxs-lookup"><span data-stu-id="d4862-188">To learn how to use Windows PowerShell to connect to Exchange Online Protection, see [Connect to Exchange Online Protection Using Remote PowerShell](http://technet.microsoft.com/library/054e0fd7-d465-4572-93f8-a00a9136e4d1.aspx).</span></span>
    
 <span data-ttu-id="d4862-189">**Per aggiungere un utente di posta elettronica utilizzando PowerShell remoto**</span><span class="sxs-lookup"><span data-stu-id="d4862-189">**To add a mail user using remote PowerShell**</span></span>
  
<span data-ttu-id="d4862-190">In questo esempio viene utilizzato il cmdlet [New-EOPMailUser](http://technet.microsoft.com/library/0520cf33-4ad0-44e4-99a3-1b485739fc05.aspx) per creare un account utente abilitato alla posta elettronica per Jeffrey Zeng in EOP con i seguenti dettagli:</span><span class="sxs-lookup"><span data-stu-id="d4862-190">This example uses the [New-EOPMailUser](http://technet.microsoft.com/library/0520cf33-4ad0-44e4-99a3-1b485739fc05.aspx) cmdlet to create a mail-enabled user account for Jeffrey Zeng in EOP with the following details:</span></span> 
  
- <span data-ttu-id="d4862-191">Il nome è Jeffrey e il cognome è Zeng.</span><span class="sxs-lookup"><span data-stu-id="d4862-191">The first name is Jeffrey and the last name is Zeng.</span></span>
    
- <span data-ttu-id="d4862-192">Il nome è Jeffrey e il nome visualizzato è Jeffrey Zeng.</span><span class="sxs-lookup"><span data-stu-id="d4862-192">The name is Jeffrey and the display name is Jeffrey Zeng.</span></span>
    
- <span data-ttu-id="d4862-193">L'alias è jeffreyz.</span><span class="sxs-lookup"><span data-stu-id="d4862-193">The alias is jeffreyz.</span></span>
    
- <span data-ttu-id="d4862-194">L'indirizzo di posta elettronica esterno è jzeng@tailspintoys.com.</span><span class="sxs-lookup"><span data-stu-id="d4862-194">The external email address is jzeng@tailspintoys.com.</span></span>
    
- <span data-ttu-id="d4862-195">La firma di Office 365 nel nome è jeffreyz@contoso.onmicrosoft.com.</span><span class="sxs-lookup"><span data-stu-id="d4862-195">The Office 365 sign in name is jeffreyz@contoso.onmicrosoft.com.</span></span>
    
- <span data-ttu-id="d4862-196">La password è Pa$$word1.</span><span class="sxs-lookup"><span data-stu-id="d4862-196">The password is Pa$$word1.</span></span>
    
```Powershell
New-EOPMailUser -LastName Zeng -FirstName Jeffrey -DisplayName "Jeffrey Zeng" -Name Jeffrey -Alias jeffreyz -MicrosoftOnlineServicesID jeffreyz@contoso.onmicrosoft.com -ExternalEmailAddress jeffreyz@tailspintoys.com -Password (ConvertTo-SecureString -String 'Pa$$word1' -AsPlainText -Force)
```

 <span data-ttu-id="d4862-197">**Per verificare che è corretto**</span><span class="sxs-lookup"><span data-stu-id="d4862-197">**To verify that this worked**</span></span>
  
<span data-ttu-id="d4862-198">Eseguire il cmdlet [Get-User](http://technet.microsoft.com/library/2a33c9e6-33da-438c-912d-28ce3f4c9afb.aspx) come segue per visualizzare le informazioni sul nuovo utente di posta elettronica Jeffrey Zeng:</span><span class="sxs-lookup"><span data-stu-id="d4862-198">Run the [Get-User](http://technet.microsoft.com/library/2a33c9e6-33da-438c-912d-28ce3f4c9afb.aspx) cmdlet as follows to display information about new mail user Jeffrey Zeng:</span></span> 
  
```Powershell
Get-User "Jeffrey Zeng"

```

 <span data-ttu-id="d4862-199">**Per modificare le proprietà di un utente di posta utilizzando PowerShell remoto**</span><span class="sxs-lookup"><span data-stu-id="d4862-199">**To edit the properties of a mail user using remote PowerShell**</span></span>
  
<span data-ttu-id="d4862-200">Utilizzare i cmdlet di [Get-Recipient](http://technet.microsoft.com/library/2ce6250f-0ad3-4b29-870c-e1d6e1e154bc.aspx) e [Set-EOPMailUser](http://technet.microsoft.com/library/834c3de6-1485-4d50-bb96-262a2c0c8619.aspx) per visualizzare o modificare le proprietà degli utenti di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="d4862-200">Use the [Get-Recipient](http://technet.microsoft.com/library/2ce6250f-0ad3-4b29-870c-e1d6e1e154bc.aspx) and [Set-EOPMailUser](http://technet.microsoft.com/library/834c3de6-1485-4d50-bb96-262a2c0c8619.aspx) cmdlets to view or change properties for mail users.</span></span> 
  
<span data-ttu-id="d4862-201">In questo esempio viene impostato l'indirizzo di posta elettronica esterno per Pilar Pinilla.</span><span class="sxs-lookup"><span data-stu-id="d4862-201">This example sets the external email address for Pilar Pinilla.</span></span>
  
```Powershell
Set-EOPMailUser -Identity "Pilar Pinilla" -EmailAddresses pilarp@tailspintoys.com
```

<span data-ttu-id="d4862-202">In questo esempio viene impostata la proprietà Company per tutti gli utenti di posta di Contoso.</span><span class="sxs-lookup"><span data-stu-id="d4862-202">This example sets the Company property for all mail users to Contoso.</span></span>
  
```Powershell
$Recip = Get-Recipient -ResultSize unlimited -Filter {(RecipientTypeDetails -eq 'mailuser')}
$Recip | foreach {Set-EOPUser -Identity $_.Alias -Company Contoso}

```

 <span data-ttu-id="d4862-203">**Per verificare che è corretto**</span><span class="sxs-lookup"><span data-stu-id="d4862-203">**To verify that this worked**</span></span>
  
<span data-ttu-id="d4862-p119">Nell'esempio precedente in cui sono stata cambiate le proprietà per l'utente di posta elettronica Pilar Pinella, utilizzare il cmdlet [Get-Recipient](http://technet.microsoft.com/library/2ce6250f-0ad3-4b29-870c-e1d6e1e154bc.aspx) per verificare le modifiche (tenere presente che è possibile visualizzare più proprietà per più contatti di posta elettronica).</span><span class="sxs-lookup"><span data-stu-id="d4862-p119">In the previous example where we changed the properties for mail user Pilar Pinella, use the [Get-Recipient](http://technet.microsoft.com/library/2ce6250f-0ad3-4b29-870c-e1d6e1e154bc.aspx) cmdlet to verify the changes. (Note that you can view multiple properties for multiple mail contacts.)</span></span> 
  
```Powershell
Get-Recipient -Identity "Pilar Pinilla" | Format-List 

```

<span data-ttu-id="d4862-206">Nell'esempio precedente in cui la proprietà Company è stata impostata su Contoso per tutti gli utenti di posta, utilizzare il comando seguente per verificare le modifiche:</span><span class="sxs-lookup"><span data-stu-id="d4862-206">In the previous example where the Company property was set to Contoso for all mail users, run the following command to verify the changes:</span></span>
  
```Powershell
Get-Recipient -ResultSize unlimited -Filter {(RecipientTypeDetails -eq 'mailuser')} | Format-List Name,Company
```

> [!IMPORTANT]
> <span data-ttu-id="d4862-207">Questo cmdlet utilizza un metodo di elaborazione batch che genera un ritardo di qualche minuto nella propagazione prima che i risultati del cmdlet siano visibili.</span><span class="sxs-lookup"><span data-stu-id="d4862-207">This cmdlet uses a batch processing method that results in a propagation delay of a few minutes before the results of the cmdlet are visible.</span></span> 
  
 <span data-ttu-id="d4862-208">**Per rimuovere un utente di posta elettronica utilizzando PowerShell remoto**</span><span class="sxs-lookup"><span data-stu-id="d4862-208">**To remove a mail user using remote PowerShell**</span></span>
  
<span data-ttu-id="d4862-209">In questo esempio viene utilizzato il cmdlet [Remove-EOPMailUser](http://technet.microsoft.com/library/cb91dc26-ed22-4d3c-9f64-df9df1754edb.aspx) per eliminare l'utente Jeffrey Zeng:</span><span class="sxs-lookup"><span data-stu-id="d4862-209">This example uses the [Remove-EOPMailUser](http://technet.microsoft.com/library/cb91dc26-ed22-4d3c-9f64-df9df1754edb.aspx) cmdlet to delete user Jeffrey Zeng:</span></span> 
  
```Powershell
Remove-EOPMailUser -Identity Jeffrey
```

 <span data-ttu-id="d4862-210">**Per verificare che è corretto**</span><span class="sxs-lookup"><span data-stu-id="d4862-210">**To verify that this worked**</span></span>
  
<span data-ttu-id="d4862-p120">Eseguire il cmdlet [Get-Recipient](http://technet.microsoft.com/library/2ce6250f-0ad3-4b29-870c-e1d6e1e154bc.aspx) nel modo seguente. Dovrebbe essere visualizzato un messaggio di errore dal momento che l'utente non esiste più.</span><span class="sxs-lookup"><span data-stu-id="d4862-p120">Run the [Get-Recipient](http://technet.microsoft.com/library/2ce6250f-0ad3-4b29-870c-e1d6e1e154bc.aspx) cmdlet as follows. You should get an error message since the user no longer exists.</span></span> 
  
```Powershell
Get-Recipient Jeffrey | fl
```


