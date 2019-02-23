---
title: Creazione di un blocco per controversia legale in Office 365
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 3/13/2018
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid: MET150
ms.assetid: 39db1659-0b12-4243-a21c-2614512dcb44
ms.openlocfilehash: f2d3793eac84e8f80158842c833c30986b0549c5
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/23/2019
ms.locfileid: "30218656"
---
# <a name="create-a-litigation-hold-in-office-365"></a><span data-ttu-id="e3088-102">Creazione di un blocco per controversia legale in Office 365</span><span class="sxs-lookup"><span data-stu-id="e3088-102">Create a Litigation Hold in Office 365</span></span>

<span data-ttu-id="e3088-p101">È possibile inserire una cassetta postale sul blocco per controversia legale per mantenere tutto il contenuto delle cassette postali, inclusi gli elementi eliminati e le versioni originali degli elementi modificati. Quando si posiziona una cassetta postale utente in conservazione per controversia legale, viene conservato anche il contenuto della cassetta postale di archiviazione dell'utente (se abilitata). Quando si crea un'esenzione, è possibile specificare una durata del blocco, denominata anche *blocco basato sul tempo*, in modo che gli elementi eliminati e modificati vengano conservati per un periodo specificato e quindi eliminati definitivamente dalla cassetta postale. In alternativa, è possibile conservare il contenuto a tempo indeterminato (denominato *blocco infinito*) oppure fino a quando non viene rimosso il blocco per controversia legale. Se si specifica un periodo di durata del blocco, viene calcolato a partire dalla data di ricezione di un messaggio o dalla creazione di un elemento della cassetta postale.</span><span class="sxs-lookup"><span data-stu-id="e3088-p101">You can place a mailbox on Litigation Hold to retain all mailbox content, including deleted items and the original versions of modified items. When you place a user mailbox on Litigation Hold, content in the user's archive mailbox (if it's enabled) is also retained. When you create a hold, you can specify a hold duration (also called a *time-based hold*) so that deleted and modified items are retained for a specified period and then permanently deleted from the mailbox. Or you can just retain content indefinitely (called an *infinite hold*) or until the Litigation Hold is removed. If you do specify a hold duration period, it's calculated from the date a message is received or a mailbox item is created.</span></span> 
  
<span data-ttu-id="e3088-108">Ecco cosa succede quando si crea un blocco per controversia legale.</span><span class="sxs-lookup"><span data-stu-id="e3088-108">Here's what happens when you create a Litigation Hold.</span></span>
  
- <span data-ttu-id="e3088-109">Gli elementi eliminati in modo definitivo dall'utente vengono conservati nella cartella elementi ripristinabili nella cassetta postale dell'utente per tutta la durata del blocco.</span><span class="sxs-lookup"><span data-stu-id="e3088-109">Items that are permanently deleted by the user are retained in the Recoverable Items folder in the user's mailbox for the duration of the hold.</span></span>
    
- <span data-ttu-id="e3088-110">Gli elementi eliminati dalla cartella elementi ripristinabili da parte dell'utente vengono conservati per la durata del blocco.</span><span class="sxs-lookup"><span data-stu-id="e3088-110">Items that are purged from the Recoverable Items folder by the user are retained for the duration of the hold.</span></span>
    
- <span data-ttu-id="e3088-111">La quota di archiviazione per la cartella elementi ripristinabili è aumentata da 30 GB a 110 GB.</span><span class="sxs-lookup"><span data-stu-id="e3088-111">The storage quota for the Recoverable Items folder is increased from 30 GB to 110 GB.</span></span>
    
- <span data-ttu-id="e3088-112">Gli elementi nelle cassette postali primarie e di archiviazione dell'utente vengono conservati</span><span class="sxs-lookup"><span data-stu-id="e3088-112">Items in the user's primary and the archive mailboxes are retained</span></span>
    
## <a name="before-you-begin"></a><span data-ttu-id="e3088-113">Informazioni preliminari</span><span class="sxs-lookup"><span data-stu-id="e3088-113">Before you begin</span></span>

- <span data-ttu-id="e3088-p102">Per attivare il blocco per controversia legale in una cassetta postale di Exchange Online, deve essere assegnata una licenza di Exchange Online piano 2. Se a una cassetta postale viene assegnata una licenza di Exchange Online piano 1, è necessario assegnarle una licenza di archiviazione Exchange Online separata per inserirla in blocco.</span><span class="sxs-lookup"><span data-stu-id="e3088-p102">To place an Exchange Online mailbox on Litigation Hold, it must be assigned an Exchange Online Plan 2 license. If a mailbox is assigned an Exchange Online Plan 1 license, you would have to assign it a separate Exchange Online Archiving license to place it on hold.</span></span>
    

## <a name="place-a-mailbox-on-litigation-hold-in-the-office-365-admin-center"></a><span data-ttu-id="e3088-116">Inserire una cassetta postale in un blocco per controversia legale nell'interfaccia di amministrazione di Office 365</span><span class="sxs-lookup"><span data-stu-id="e3088-116">Place a mailbox on Litigation Hold in the Office 365 admin center</span></span>

<span data-ttu-id="e3088-117">Di seguito sono riportati i passaggi per inserire un Maibox sul blocco per controversia legale utilizzando l'interfaccia di amministrazione di Office 365.</span><span class="sxs-lookup"><span data-stu-id="e3088-117">Here are the steps to place a maibox on Litigation Hold using the Office 365 admin center.</span></span>

1. <span data-ttu-id="e3088-118">Accedere a https://portal.office.com/adminportal/home e accedere utilizzando l'account di amministratore globale.</span><span class="sxs-lookup"><span data-stu-id="e3088-118">Go to https://portal.office.com/adminportal/home and sign in using your global administrator account.</span></span>
2. <span data-ttu-id="e3088-119">Fare clic su utenti**attivi** nel riquadro di spostamento sinistro. \*\*\*\* > </span><span class="sxs-lookup"><span data-stu-id="e3088-119">Click **Users** > **Active users** in the left navigation pane.</span></span>
3. <span data-ttu-id="e3088-120">Selezionare l'utente di cui si desidera inserire la cassetta postale per il blocco per controversia legale.</span><span class="sxs-lookup"><span data-stu-id="e3088-120">Select the user whose mailbox you want to place on Litigation Hold.</span></span>
4. <span data-ttu-id="e3088-121">Nella pagina del volo, fare clic su **impostazioni di posta**, quindi fare clic su **modifica** accanto a blocco per **controversia legale**.</span><span class="sxs-lookup"><span data-stu-id="e3088-121">On the fly-out page, click **Mail settings**, and then click **Edit** next to **Litigation hold**.</span></span>
5. <span data-ttu-id="e3088-122">Nella pagina **blocco per controversIa legale** fare clic sull'interruttore per attivare il blocco per controversia legale e completare le seguenti impostazioni facoltative che vengono visualizzate:</span><span class="sxs-lookup"><span data-stu-id="e3088-122">On the **Litigation hold** page, click the toggle to turn on Litigation Hold and complete the following optional settings that are displayed:</span></span>
 
    ![O365_LitigationHold1. png](media/O365-LitigationHold1.png)

    <span data-ttu-id="e3088-p103">a. **durata del blocco (giorni)** : utilizzare questa casella per creare un blocco basato sul tempo e specificare il periodo di conservazione degli elementi della cassetta postale quando la cassetta postale viene inserita nella conservazione per controversia legale. La durata viene calcolata a partire dalla data di ricezione o creazione di un elemento della cassetta postale. Se si lascia vuota questa casella, gli elementi vengono conservati a tempo indeterminato o fino a quando non viene rimosso il blocco. Utilizzare giorni per specificare la durata.</span><span class="sxs-lookup"><span data-stu-id="e3088-p103">a. **Hold duration (days)** - Use this box to create a time-based hold and specify how long mailbox items are held when the mailbox is placed on Litigation Hold. The duration is calculated from the date a mailbox item is received or created. If you leave this box blank, items are held indefinitely or until the hold is removed. Use days to specify the duration.</span></span>
    
    <span data-ttu-id="e3088-p104">b. **Note** : utilizzare questa casella per informare l'utente che la cassetta postale è in blocco per controversia legale. La nota verrà visualizzata nella pagina informazioni account nella cassetta postale dell'utente se utilizza Outlook 2010 o versione successiva. Per accedere a questa pagina, gli utenti possono fare clic su **file** in Outlook.</span><span class="sxs-lookup"><span data-stu-id="e3088-p104">b. **Note** - Use this box to inform the user their mailbox is on Litigation Hold. The note will appear on the Account Information page in the user's mailbox if they're using Outlook 2010 or later. To access this page, users can click **File** in Outlook.</span></span>
     
    <span data-ttu-id="e3088-p105">c. **pagina Web** : utilizzare questa casella per indirizzare l'utente a un sito Web per ulteriori informazioni sul blocco per controversia legale. Questo URL viene visualizzato nella pagina informazioni account nella cassetta postale dell'utente se utilizza Outlook 2010 o versione successiva. Per accedere a questa pagina, gli utenti possono fare clic su **file** in Outlook.</span><span class="sxs-lookup"><span data-stu-id="e3088-p105">c. **Web page** - Use this box to direct the user to a website for more information about Litigation Hold. This URL appears on the Account Information page in the user's mailbox if they are using Outlook 2010 or later. To access this page, users can click **File** in Outlook.</span></span>
 
6. <span data-ttu-id="e3088-137">Fare clic su **Salva** per creare il blocco per controversia legale.</span><span class="sxs-lookup"><span data-stu-id="e3088-137">Click **Save** to create the Litigation Hold.</span></span>

<span data-ttu-id="e3088-138">Dopo aver creato il blocco, le impostazioni di posta elettronica nella pagina di volo indicano che il blocco per controversia legale è attivato per l'utente selezionato.</span><span class="sxs-lookup"><span data-stu-id="e3088-138">After you create the hold, the mail settings on the fly-out page shows that Litigation Hold is turned on for the selected user.</span></span>

![O365_LitigationHold2. png](media/O365-LitigationHold2.png)

<span data-ttu-id="e3088-140">Per ulteriori informazioni sulla creazione e sulla gestione di controversia legale e sull'utilizzo di Exchange Online PowerShell per creare in blocco la controversia legale, vedere [posizionare una cassetta postale sul blocco per controversIa legale](https://docs.microsoft.com/office365/SecurityCompliance/place-a-mailbox-on-litigation-hold).</span><span class="sxs-lookup"><span data-stu-id="e3088-140">For more information about creating and managing Litigation Holds and using Exchange Online PowerShell to bulk-create Litigation Holds, see [Place a mailbox on Litigation Hold](https://docs.microsoft.com/office365/SecurityCompliance/place-a-mailbox-on-litigation-hold).</span></span>
