---
title: Creare una conservazione per controversia legale in Office 365
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 3/13/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid: MET150
ms.assetid: 39db1659-0b12-4243-a21c-2614512dcb44
ms.openlocfilehash: aa78d12046108aa1f1b974f01c02ff923b99b97b
ms.sourcegitcommit: 7956955cd919f6e00b64e4506605a743c5872549
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/26/2018
ms.locfileid: "25037959"
---
# <a name="create-a-litigation-hold-in-office-365"></a><span data-ttu-id="b0793-102">Creare una conservazione per controversia legale in Office 365</span><span class="sxs-lookup"><span data-stu-id="b0793-102">Create a Litigation Hold in Office 365</span></span>

<span data-ttu-id="b0793-p101">È possibile effettuare una cassetta postale di conservazione per controversia legale per mantenere tutto il contenuto delle cassette postali, inclusi gli elementi eliminati e le versioni originali degli elementi modificati. Quando si effettua una cassetta postale utente conservazione per controversia legale, contenuto nella cassetta postale di archivio dell'utente (se abilitato) viene inoltre mantenuto. Quando si crea un'esenzione, è possibile specificare un intervallo di tempo di attesa (denominato anche un' *archiviazione con scadenza*) in modo da eliminare ed elementi modificati vengono mantenuti per un periodo specificato e quindi eliminati definitivamente dalla cassetta postale. Oppure è possibile mantenere solo il contenuto per un tempo indefinito (noti come un' *attesa infinita*) fino a quando non viene rimossa la conservazione per controversia legale. Se si specifica una periodo di durata della conservazione, viene calcolata dalla data di ricezione di un messaggio o viene creato un elemento della cassetta postale.</span><span class="sxs-lookup"><span data-stu-id="b0793-p101">You can place a mailbox on Litigation Hold to retain all mailbox content, including deleted items and the original versions of modified items. When you place a user mailbox on Litigation Hold, content in the user's archive mailbox (if it's enabled) is also retained. When you create a hold, you can specify a hold duration (also called a *time-based hold*) so that deleted and modified items are retained for a specified period and then permanently deleted from the mailbox. Or you can just retain content indefinitely (called an *infinite hold*) or until the Litigation Hold is removed. If you do specify a hold duration period, it's calculated from the date a message is received or a mailbox item is created.</span></span> 
  
<span data-ttu-id="b0793-108">Ecco cosa succede quando si crea una conservazione per controversia legale.</span><span class="sxs-lookup"><span data-stu-id="b0793-108">Here's what happens when you create a Litigation Hold.</span></span>
  
- <span data-ttu-id="b0793-109">Gli elementi eliminati in modo permanente dall'utente vengono mantenuti nella cartella elementi ripristinabili nella cassetta postale dell'utente per la durata dell'esenzione.</span><span class="sxs-lookup"><span data-stu-id="b0793-109">Items that are permanently deleted by the user are retained in the Recoverable Items folder in the user's mailbox for the duration of the hold.</span></span>
    
- <span data-ttu-id="b0793-110">Gli elementi eliminati dalla cartella elementi ripristinabili dall'utente vengono mantenuti per tutta la durata dell'esenzione.</span><span class="sxs-lookup"><span data-stu-id="b0793-110">Items that are purged from the Recoverable Items folder by the user are retained for the duration of the hold.</span></span>
    
- <span data-ttu-id="b0793-111">La quota di archiviazione per la cartella elementi recuperabili viene aumentata da 30 GB a 110 GB.</span><span class="sxs-lookup"><span data-stu-id="b0793-111">The storage quota for the Recoverable Items folder is increased from 30 GB to 110 GB.</span></span>
    
- <span data-ttu-id="b0793-112">Vengono conservati gli elementi in principale dell'utente e le cassette postali di archiviazione</span><span class="sxs-lookup"><span data-stu-id="b0793-112">Items in the user's primary and the archive mailboxes are retained</span></span>
    
## <a name="before-you-begin"></a><span data-ttu-id="b0793-113">Informazioni preliminari</span><span class="sxs-lookup"><span data-stu-id="b0793-113">Before you begin</span></span>

- <span data-ttu-id="b0793-p102">Per inserire una cassetta postale di Exchange Online sulla conservazione per controversia legale, deve essere assegnato una licenza di Exchange Online piano 2. Se una cassetta postale viene assegnata una licenza di Exchange Online piano 1, è necessario assegnarlo una licenza separata archiviazione Exchange Online per mettere in attesa.</span><span class="sxs-lookup"><span data-stu-id="b0793-p102">To place an Exchange Online mailbox on Litigation Hold, it must be assigned an Exchange Online Plan 2 license. If a mailbox is assigned an Exchange Online Plan 1 license, you would have to assign it a separate Exchange Online Archiving license to place it on hold.</span></span>
    

## <a name="place-a-mailbox-on-litigation-hold-in-the-office-365-admin-center"></a><span data-ttu-id="b0793-116">Inserire una cassetta postale conservazione per controversia legale nell'interfaccia di amministrazione di Office 365</span><span class="sxs-lookup"><span data-stu-id="b0793-116">Place a mailbox on Litigation Hold in the Office 365 admin center</span></span>

<span data-ttu-id="b0793-117">Ecco la procedura per bloccare un iniziata la conservazione per controversia legale utilizzando l'interfaccia di amministrazione di Office 365.</span><span class="sxs-lookup"><span data-stu-id="b0793-117">Here are the steps to place a maibox on Litigation Hold using the Office 365 admin center.</span></span>

1. <span data-ttu-id="b0793-118">Accedere a https://portal.office.com/adminportal/home e accedere utilizzando l'account amministratore globale.</span><span class="sxs-lookup"><span data-stu-id="b0793-118">Go to https://portal.office.com/adminportal/home and sign in using your global administrator account.</span></span>
2. <span data-ttu-id="b0793-119">Fare clic su **utenti** > **utenti attivi** nel riquadro di spostamento a sinistra.</span><span class="sxs-lookup"><span data-stu-id="b0793-119">Click **Users** > **Active users** in the left navigation pane.</span></span>
3. <span data-ttu-id="b0793-120">Selezionare l'utente la cui cassetta postale desiderata per bloccare la conservazione per controversia legale.</span><span class="sxs-lookup"><span data-stu-id="b0793-120">Select the user whose mailbox you want to place on Litigation Hold.</span></span>
4. <span data-ttu-id="b0793-121">Nella pagina di accesso rapido, fare clic su **Impostazioni posta elettronica**e quindi fare clic su **Edit** accanto alla **conservazione per controversia legale**.</span><span class="sxs-lookup"><span data-stu-id="b0793-121">On the fly-out page, click **Mail settings**, and then click **Edit** next to **Litigation hold**.</span></span>
5. <span data-ttu-id="b0793-122">Scegliere Attiva o disattiva per attivare la conservazione per controversia legale e completare le seguenti opzioni facoltative che vengono visualizzate nella pagina **conservazione per controversia legale** :</span><span class="sxs-lookup"><span data-stu-id="b0793-122">On the **Litigation hold** page, click the toggle to turn on Litigation Hold and complete the following optional settings that are displayed:</span></span>
 
    ![O365_LitigationHold1.PNG](media/O365-LitigationHold1.png)

    <span data-ttu-id="b0793-p103">r. **durata della conservazione (giorni)** -utilizzare questa casella per creare un'esenzione basate sul tempo e specificare il tempo di mantenimento degli elementi della cassetta postale quando viene effettuata la cassetta postale di conservazione per controversia legale. La durata viene calcolata dalla data di ricezione o creato un elemento della cassetta postale. Se si lascia vuota questa casella, di mantenimento degli elementi per un tempo indefinito o fino alla rimozione. Utilizzare i giorni lavorativi per specificare la durata.</span><span class="sxs-lookup"><span data-stu-id="b0793-p103">a. **Hold duration (days)** - Use this box to create a time-based hold and specify how long mailbox items are held when the mailbox is placed on Litigation Hold. The duration is calculated from the date a mailbox item is received or created. If you leave this box blank, items are held indefinitely or until the hold is removed. Use days to specify the duration.</span></span>
    
    <span data-ttu-id="b0793-p104">b. **Nota** : utilizzare questa casella per informare l'utente delle relative cassette postali sono controversie legali. La nota viene visualizzata nella pagina informazioni Account nella cassetta postale dell'utente se utilizzano Outlook 2010 o versioni successive. Per accedere a questa pagina, gli utenti possono fare clic su **File** di Outlook.</span><span class="sxs-lookup"><span data-stu-id="b0793-p104">b. **Note** - Use this box to inform the user their mailbox is on Litigation Hold. The note will appear on the Account Information page in the user's mailbox if they're using Outlook 2010 or later. To access this page, users can click **File** in Outlook.</span></span>
     
    <span data-ttu-id="b0793-p105">**pagina Web** - c. utilizzare questa casella per indirizzare l'utente a un sito Web per ulteriori informazioni sulla conservazione per controversia legale. Questo URL verrà visualizzato nella pagina informazioni Account nella cassetta postale dell'utente che utilizzano Outlook 2010 o versioni successive. Per accedere a questa pagina, gli utenti possono fare clic su **File** di Outlook.</span><span class="sxs-lookup"><span data-stu-id="b0793-p105">c. **Web page** - Use this box to direct the user to a website for more information about Litigation Hold. This URL appears on the Account Information page in the user's mailbox if they are using Outlook 2010 or later. To access this page, users can click **File** in Outlook.</span></span>
 
6. <span data-ttu-id="b0793-137">Fare clic su **Salva** per creare la conservazione per controversia legale.</span><span class="sxs-lookup"><span data-stu-id="b0793-137">Click **Save** to create the Litigation Hold.</span></span>

<span data-ttu-id="b0793-138">Dopo aver creato la conservazione, le impostazioni di posta elettronica nella pagina di accesso rapido Mostra di conservazione per controversia legale è attivata per l'utente selezionato.</span><span class="sxs-lookup"><span data-stu-id="b0793-138">After you create the hold, the mail settings on the fly-out page shows that Litigation Hold is turned on for the selected user.</span></span>

![O365_LitigationHold2.PNG](media/O365-LitigationHold2.png)

<span data-ttu-id="b0793-140">Per ulteriori informazioni sulla creazione e gestione delle esenzioni controversie legali e utilizzo di Exchange Online PowerShell per creare controversia contiene, vedere [Place una cassetta postale di conservazione per controversia legale](https://docs.microsoft.com/office365/SecurityCompliance/place-a-mailbox-on-litigation-hold).</span><span class="sxs-lookup"><span data-stu-id="b0793-140">For more information about creating and managing Litigation Holds and using Exchange Online PowerShell to bulk-create Litigation Holds, see [Place a mailbox on Litigation Hold](https://docs.microsoft.com/office365/SecurityCompliance/place-a-mailbox-on-litigation-hold).</span></span>
