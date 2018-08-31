---
title: Installare il componente aggiuntivo Supervisione per Outlook desktop
ms.author: brendonb
author: brendonb
manager: laurawi
ms.date: 6/19/2017
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
- ZOL160
ms.assetid: 6c5620e6-aba3-4910-8f3a-b55451656ff7
description: Installare il componente aggiuntivo di Office 365 supervisione per la versione desktop di Outlook
ms.openlocfilehash: 0bddf305087bf0d9552c7671da5306db8352143f
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/27/2018
ms.locfileid: "22530312"
---
# <a name="install-the-supervision-add-in-for-outlook-desktop"></a><span data-ttu-id="f6e7b-103">Installare il componente aggiuntivo Supervisione per Outlook desktop</span><span class="sxs-lookup"><span data-stu-id="f6e7b-103">Install the Supervision add-in for Outlook desktop</span></span>

<span data-ttu-id="f6e7b-p101">Per esaminare communications identificato da un criterio di supervisione, utilizzare i revisori la supervisione componente aggiuntivo per Outlook e Outlook web app. Il componente aggiuntivo viene installato automaticamente in Outlook web app per tutti i revisori specificato nel criterio. Tuttavia, i revisori devono eseguire alcuni passaggi per installare la versione desktop di Outlook.</span><span class="sxs-lookup"><span data-stu-id="f6e7b-p101">To review communications identified by a supervision policy, reviewers use the Supervision add-in for Outlook and Outlook web app. The add-in is installed automatically in Outlook web app for all reviewers you specified in the policy. However, reviewers must run through some steps to install it in the desktop version of Outlook.</span></span>
  
> [!NOTE]
> <span data-ttu-id="f6e7b-p102">Utilizzo dei criteri di supervisione richiede una sottoscrizione a Office 365 E5 per l'organizzazione. Se non sono dial plan e desidera provare supervisione, è possibile [iscrizione a una versione di valutazione di Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span><span class="sxs-lookup"><span data-stu-id="f6e7b-p102">Using supervision policies requires an Office 365 E5 subscription for your organization. If you don't have that plan and want to try supervision, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
## <a name="step-1-copy-the-address-for-the-supervision-mailbox"></a><span data-ttu-id="f6e7b-109">Passaggio 1: Copiare l'indirizzo della cassetta postale di supervisione</span><span class="sxs-lookup"><span data-stu-id="f6e7b-109">Step 1: Copy the address for the supervision mailbox</span></span>

<span data-ttu-id="f6e7b-110">Per installare il componente aggiuntivo per desktop Outlook, è necessario l'indirizzo della cassetta postale di supervisione che è stata creata come parte dell'impostazione di criteri di supervisione.</span><span class="sxs-lookup"><span data-stu-id="f6e7b-110">To install the add-in for Outlook desktop, you'll need the address for the supervision mailbox that was created as part of the supervision policy setup.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="f6e7b-111">Se qualcuno altre posizioni creato il criterio, sarà necessario ottenere questo indirizzo da loro di installare il componente aggiuntivo.</span><span class="sxs-lookup"><span data-stu-id="f6e7b-111">If someone else created the policy, you'll need to get this address from them to install the add-in.</span></span> 
  
 <span data-ttu-id="f6e7b-112">**Per trovare l'indirizzo della cassetta postale di supervisione**</span><span class="sxs-lookup"><span data-stu-id="f6e7b-112">**To find the supervision mailbox address**</span></span>
  
1. <span data-ttu-id="f6e7b-113">Accedere al [protezione &amp; centro conformità](https://protection.office.com) utilizzando le credenziali per un account di amministratore dell'organizzazione Office 365.</span><span class="sxs-lookup"><span data-stu-id="f6e7b-113">Sign into the [Security &amp; Compliance Center](https://protection.office.com) using credentials for an admin account in your Office 365 organization.</span></span> 
    
2. <span data-ttu-id="f6e7b-114">Andare alla **governance dati** \> **supervisione**.</span><span class="sxs-lookup"><span data-stu-id="f6e7b-114">Go to **Data governance** \> **Supervision**.</span></span>
    
3. <span data-ttu-id="f6e7b-115">Fare clic sui criteri di supervisione che sono la raccolta delle comunicazioni da controllare.</span><span class="sxs-lookup"><span data-stu-id="f6e7b-115">Click the supervision policy that's gathering the communications you want to review.</span></span>
    
4. <span data-ttu-id="f6e7b-116">Nel criterio in dettaglio comparsa, in * * cassetta postale di supervisione * *, copiare l'indirizzo.</span><span class="sxs-lookup"><span data-stu-id="f6e7b-116">In the policy details flyout, under ** Supervision mailbox **, copy the address.</span></span> 
    
    ![La sezione 'Supervisione delle cassette postali' dell'elemento libero dei dettagli di criteri di supervisione che mostra l'indirizzo della cassetta postale di supervisione posti in evidenza](media/71779d0e-4f01-4dd3-8234-5f9c30eeb067.jpg)
  
## <a name="step-2-configure-the-supervision-mailbox-for-outlook-desktop-access"></a><span data-ttu-id="f6e7b-118">Passaggio 2: Configurare la cassetta postale di supervisione per l'accesso desktop Outlook</span><span class="sxs-lookup"><span data-stu-id="f6e7b-118">Step 2: Configure the supervision mailbox for Outlook desktop access</span></span>

<span data-ttu-id="f6e7b-119">Successivamente, saranno necessario eseguire alcuni comandi di Exchange Online PowerShell in modo da Outlook può connettersi alla cassetta postale di supervisione revisori.</span><span class="sxs-lookup"><span data-stu-id="f6e7b-119">Next, reviewers will need to run a couple Exchange Online PowerShell commands so they can connect Outlook to the supervision mailbox.</span></span>
  
1. <span data-ttu-id="f6e7b-p103">Connessione a Exchange Online PowerShell. [Come eseguire l'operazione?](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)</span><span class="sxs-lookup"><span data-stu-id="f6e7b-p103">Connect to Exchange Online PowerShell. [How do I do this?](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)</span></span>
    
2. <span data-ttu-id="f6e7b-122">Eseguire i comandi riportati di seguito.</span><span class="sxs-lookup"><span data-stu-id="f6e7b-122">Run the following commands.</span></span>
    
  ```
  Add-MailboxPermission "SupervisoryReview{GUID}@domain.onmicrosoft.com" -User <alias or email address of the account that has reviewer permissions to the supervision mailbox> -AccessRights FullAccessSet-Mailbox "<SupervisoryReview{GUID}@domain.onmicrosoft.com>" -HiddenFromAddressListsEnabled: $false
  ```

    <span data-ttu-id="f6e7b-123">Dove *SupervisoryReview{GUID}@domain.onmicrosoft.com* è l'indirizzo che è stato copiato nel passaggio 1 sopra e *utente* è il nome del revisore che si connettono alla cassetta postale di supervisione nel passaggio successivo.</span><span class="sxs-lookup"><span data-stu-id="f6e7b-123">Where  *SupervisoryReview{GUID}@domain.onmicrosoft.com*  is the address you copied in Step 1 above, and  *User*  is the name of the reviewer who will be connecting to the supervision mailbox in the next step.</span></span> 
    
3. <span data-ttu-id="f6e7b-124">Attendere almeno un'ora prima di passare al passaggio 3 sotto.</span><span class="sxs-lookup"><span data-stu-id="f6e7b-124">Wait at least an hour before moving on to Step 3 below.</span></span>
    
## <a name="step-3-create-an-outlook-profile-to-connect-to-the-supervision-mailbox"></a><span data-ttu-id="f6e7b-125">Passaggio 3: Creare un profilo di Outlook per connettersi alla cassetta postale di supervisione</span><span class="sxs-lookup"><span data-stu-id="f6e7b-125">Step 3: Create an Outlook profile to connect to the supervision mailbox</span></span>

<span data-ttu-id="f6e7b-126">Per il passaggio finale, i revisori saranno necessario creare un profilo di Outlook per connettersi alla cassetta postale di supervisione.</span><span class="sxs-lookup"><span data-stu-id="f6e7b-126">For the final step, reviewers will need to create an Outlook profile to connect to the supervision mailbox.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="f6e7b-p104">Per creare un nuovo profilo di Outlook, si utilizzerà le impostazioni di posta elettronica nel Pannello di controllo di Windows. Il percorso che è eseguire per accedere a queste impostazioni può dipendono dal sistema operativo Windows (Windows 7, Windows 8 o Windows 10) si utilizza e la versione di Outlook installata.</span><span class="sxs-lookup"><span data-stu-id="f6e7b-p104">To create a new Outlook profile, you'll use the Mail settings in the Windows Control Panel. The path you take to get to these settings might depend on which Windows operating system (Windows 7, Windows 8, or Windows 10) you're using and which version of Outlook is installed.</span></span> 
  
1. <span data-ttu-id="f6e7b-129">Aprire il pannello di controllo e nella casella di **ricerca** nella parte superiore della finestra digitare **Mail**.</span><span class="sxs-lookup"><span data-stu-id="f6e7b-129">Open the Control Panel, and in the **Search** box at the top of the window, type **Mail**.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="f6e7b-p105">Non che come ottenere il pannello di controllo? Vedere [dove è Pannello di controllo?](https://support.microsoft.com/help/13764/windows-where-is-control-panel)</span><span class="sxs-lookup"><span data-stu-id="f6e7b-p105">Not sure how to get to the Control Panel? See [Where is Control Panel?](https://support.microsoft.com/help/13764/windows-where-is-control-panel)</span></span>
  
2. <span data-ttu-id="f6e7b-132">Aprire l'app di **posta elettronica** .</span><span class="sxs-lookup"><span data-stu-id="f6e7b-132">Open the **Mail** app.</span></span> 
    
3. <span data-ttu-id="f6e7b-133">In **Impostazioni di posta - Outlook**fare clic su **Mostra profili**.</span><span class="sxs-lookup"><span data-stu-id="f6e7b-133">In **Mail Setup - Outlook**, click **Show Profiles**.</span></span>
    
    !['Configurazione della posta - Outlook' la finestra di dialogo con il pulsante Mostra profili posti in evidenza](media/28b5dae9-d10c-4f2b-926a-294c857d555c.jpg)
  
4. <span data-ttu-id="f6e7b-p106">Nella **posta elettronica**, fare clic su **Aggiungi**. Quindi, nel **Nuovo profilo**, immettere un nome per la cassetta postale supervisione (ad esempio **supervisione**).</span><span class="sxs-lookup"><span data-stu-id="f6e7b-p106">In **Mail**, click **Add**. Then, in **New Profile**, enter a name for the supervision mailbox (such as **Supervision**).</span></span>
    
    ![La finestra di dialogo "Nuovo profilo" la visualizzazione del nome 'Supervisione' nella casella "Nome del profilo"](media/d02ae181-b541-4ec6-8f51-698f30033204.jpg)
  
5. <span data-ttu-id="f6e7b-138">In **Outlook la connessione a Office 365**, fare clic su **Connetti a un account diverso**.</span><span class="sxs-lookup"><span data-stu-id="f6e7b-138">In **Connect Outlook to Office 365**, click **Connect to a different account**.</span></span>
    
    ![Il messaggio 'Outlook connettersi a Office 365' con il collegamento a "Connetti a un altro account" evidenziato](media/fac49ff8-a7f0-4e82-a271-9ec045a95de1.jpg)
  
6. <span data-ttu-id="f6e7b-140">Nella **Configurazione automatica Account**, selezionare **installazione manuale o tipi di server aggiuntivi**e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="f6e7b-140">In **Auto Account Setup**, choose **Manual setup or additional server types**, and then click **Next**.</span></span>
    
7. <span data-ttu-id="f6e7b-p107">**Scegliere il tipo di Account**, selezionare **Office 365**. Quindi, nella casella **Indirizzo di posta elettronica** , immettere l'indirizzo della cassetta postale di supervisione che è stato copiato in precedenza.</span><span class="sxs-lookup"><span data-stu-id="f6e7b-p107">In **Choose Your Account Type**, choose **Office 365**. Then, in the **Email Address** box, enter the address of the supervision mailbox you copied previously.</span></span> 
    
    ![La pagina "Scegliere il tipo di Account" della finestra di dialogo Aggiungi Account in Outlook che mostra la casella "Indirizzo di posta elettronica" evidenziata.](media/4f601236-9f69-4cf6-a58c-0b91204aa8cb.jpg)
  
8. <span data-ttu-id="f6e7b-144">Quando richiesto, immettere le credenziali di Office 365.</span><span class="sxs-lookup"><span data-stu-id="f6e7b-144">When prompted, enter your Office 365 credentials.</span></span>
    
9. <span data-ttu-id="f6e7b-145">Se ha esito positivo, verrà visualizzato il **supervisione - \<nome criterio\> ** cartella elencata nella visualizzazione elenco cartelle in Outlook.</span><span class="sxs-lookup"><span data-stu-id="f6e7b-145">If successful, you'll see the **Supervision - \<policy name\>** folder listed in the Folder List view in Outlook.</span></span> 
    

