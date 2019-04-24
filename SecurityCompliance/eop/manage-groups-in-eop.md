---
title: Gestione di gruppi in EOP
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 11/17/2014
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 212e68ac-6330-47e9-a169-6cf5e2f21e13
description: È possibile utilizzare Exchange Online Protection (EOP) per creare gruppi abilitati alla posta elettronica per un'organizzazione di Exchange. È inoltre possibile utilizzare EOP per definire o aggiornare le proprietà del gruppo che specificano l'appartenenza, gli indirizzi di posta elettronica e altri aspetti dei gruppi.
ms.openlocfilehash: db649e4fd955d13e50e96007e8e38fe2c1de5b4d
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "32255916"
---
# <a name="manage-groups-in-eop"></a><span data-ttu-id="dc45b-104">Gestire gruppi in Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="dc45b-104">Manage groups in EOP</span></span>

 <span data-ttu-id="dc45b-p102">È possibile utilizzare Exchange Online Protection (EOP) per creare gruppi abilitati alla posta elettronica per un'organizzazione di Exchange. È inoltre possibile utilizzare EOP per definire o aggiornare le proprietà del gruppo che specificano l'appartenenza, gli indirizzi di posta elettronica e altri aspetti dei gruppi. È possibile creare gruppi di distribuzione e gruppi di sicurezza, a seconda delle proprie esigenze. È possibile creare tali gruppi utilizzando l'interfaccia di amministrazione di Exchange o tramite Windows PowerShell remoto.</span><span class="sxs-lookup"><span data-stu-id="dc45b-p102">You can use Exchange Online Protection (EOP) to create mail-enabled groups for an Exchange organization. You can also use EOP to define or update group properties that specify membership, email addresses, and other aspects of groups. You can create distribution groups and security groups, depending on your needs. These groups can be created by using the Exchange admin center (EAC) or via remote Windows PowerShell.</span></span> 
  
## <a name="types-of-mail-enabled-groups"></a><span data-ttu-id="dc45b-109">Tipi di gruppi abilitati alla posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="dc45b-109">Types of mail-enabled groups</span></span>

<span data-ttu-id="dc45b-110">È possibile creare due tipi di gruppi per la propria organizzazione di Exchange:</span><span class="sxs-lookup"><span data-stu-id="dc45b-110">You can create two types of groups for your Exchange organization:</span></span>
  
- <span data-ttu-id="dc45b-p103">[Creare un gruppo nell'interfaccia di amministrazione di Exchange](manage-groups-in-eop.md) (detti anche gruppi di distribuzione) sono raccolte di utenti di posta elettronica, come ad esempio team o altri gruppi ad hoc, che devono ricevere o inviare posta elettronica relativa a una comune area di interesse. I gruppi di distribuzione servono esclusivamente per la distribuzione di messaggi di posta elettronica. In EOP, un gruppo di distribuzione fa riferimento a qualsiasi gruppo abilitato alla posta elettronica, a prescindere che abbia o meno un contesto di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="dc45b-p103">[Create a group in the EAC](manage-groups-in-eop.md) (also known as distribution groups) are collections of email users, such as a team or other ad hoc group, who need to receive or send email regarding a common area of interest. Distribution groups are exclusively for distributing email messages. In EOP, a distribution group refers to any mail-enabled group, whether or not it has a security context.</span></span>
    
- <span data-ttu-id="dc45b-p104">[Modificare o rimuovere un gruppo nell'interfaccia di amministrazione di Exchange](manage-groups-in-eop.md) (noti anche come gruppi di sicurezza) sono raccolte di utenti di posta elettronica che devono accedere alle autorizzazioni dei ruoli di amministratore. Ad esempio, si potrebbe voler assegnare a un gruppo specifico di utenti autorizzazioni di ruolo di amministratore in modo che possano configurare impostazioni di protezione dalla posta indesiderata e antimalware.</span><span class="sxs-lookup"><span data-stu-id="dc45b-p104">[Edit or remove a group in the EAC](manage-groups-in-eop.md) (also known as security groups) are collections of email users who need access permissions for Admin roles. For example, you might want to give specific group of users admin role permissions so they can configure anti-spam and anti-malware settings.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="dc45b-p105">Per impostazione predefinita, tutti i nuovi gruppi di sicurezza abilitati alla posta elettronica richiedono l'autenticazione di tutti i mittenti. Questo impedisce ai mittenti esterni di inviare messaggi ai gruppi di sicurezza abilitati alla posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="dc45b-p105">By default, all new mail-enabled security groups require that all senders be authenticated. This prevents external senders from sending messages to mail-enabled security groups.</span></span> 
  
## <a name="before-you-begin"></a><span data-ttu-id="dc45b-118">Informazioni preliminari</span><span class="sxs-lookup"><span data-stu-id="dc45b-118">Before you begin</span></span>

- <span data-ttu-id="dc45b-p106">Per eseguire queste procedure, è necessario disporre delle autorizzazioni appropriate. Per sapere quali autorizzazioni sono necessarie, vedere "Gruppi di distribuzione e sicurezza" nell'argomento [Autorizzazioni di funzionalità in EOP](feature-permissions-in-eop.md).</span><span class="sxs-lookup"><span data-stu-id="dc45b-p106">You need to be assigned permissions before you can perform this procedure or procedures. To see what permissions you need, see the "Distribution Groups and Security Groups" entry in the [Feature permissions in EOP](feature-permissions-in-eop.md) topic.</span></span> 
    
- <span data-ttu-id="dc45b-121">Tenere presente che quando si creano e gestiscono i gruppi tramite cmdlet di PowerShell remoto, è possibile che si verifichino limitazioni.</span><span class="sxs-lookup"><span data-stu-id="dc45b-121">Be aware that when creating and managing groups by using remote PowerShell cmdlets, you may encounter throttling.</span></span>
    
- <span data-ttu-id="dc45b-122">Questo cmdlet utilizza un metodo di elaborazione batch che genera un ritardo di qualche minuto nella propagazione prima che i risultati del cmdlet siano visibili.</span><span class="sxs-lookup"><span data-stu-id="dc45b-122">This cmdlet uses a batch processing method that results in a propagation delay of a few minutes before the results of the cmdlet are visible.</span></span>
    
- <span data-ttu-id="dc45b-123">Per informazioni su come utilizzare Windows PowerShell per la connessione a Exchange Online Protection, vedere [Connessione a Exchange Online Protection tramite PowerShell remota](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell?view=exchange-ps).</span><span class="sxs-lookup"><span data-stu-id="dc45b-123">To learn how to use Windows PowerShell to connect to Exchange Online Protection, see [Connect to Exchange Online Protection Using Remote PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell?view=exchange-ps).</span></span>
    
- <span data-ttu-id="dc45b-124">Per informazioni sui tasti di scelta rapida che è possibile utilizzare con le procedure in questo argomento, vedere **Keyboard shortcuts in Exchange 2013**.</span><span class="sxs-lookup"><span data-stu-id="dc45b-124">For information about keyboard shortcuts that may apply to the procedures in this topic, see **Keyboard shortcuts in the Exchange admin center**.</span></span>
    
> [!TIP]
> <span data-ttu-id="dc45b-p107">Problemi? È possibile richiedere supporto nei forum di Exchange. I forum sono disponibili sui seguenti siti: [Exchange Server](https://go.microsoft.com/fwlink/p/?linkId=60612),[Exchange Online](https://go.microsoft.com/fwlink/p/?linkId=267542) o [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351).</span><span class="sxs-lookup"><span data-stu-id="dc45b-p107">Having problems? Ask for help in the Exchange forums. Visit the forums at [Exchange Server](https://go.microsoft.com/fwlink/p/?linkId=60612),[Exchange Online](https://go.microsoft.com/fwlink/p/?linkId=267542), or [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351).</span></span> 
  
## <a name="create-a-group-in-the-eac"></a><span data-ttu-id="dc45b-128">Creare un gruppo nell'interfaccia di amministrazione di Exchange</span><span class="sxs-lookup"><span data-stu-id="dc45b-128">Create a group in the EAC</span></span>

1. <span data-ttu-id="dc45b-129">Nell'interfaccia di amministrazione di Exchange, andare a **Destinatari** \> **Gruppi**.</span><span class="sxs-lookup"><span data-stu-id="dc45b-129">In the Exchange admin center (EAC), go to **Recipients** \> **Groups**.</span></span>
    
2. <span data-ttu-id="dc45b-p108">Fare clic su **Nuovo**![Icona Aggiungi](../media/ITPro-EAC-AddIcon.gif), quindi fare clic su **Gruppo di distribuzione** o **Gruppo di sicurezza**, in base alle proprie esigenze. Vedere [Tipi di gruppi abilitati alla posta elettronica.](manage-groups-in-eop.md) per le differenze.</span><span class="sxs-lookup"><span data-stu-id="dc45b-p108">Click **New**![Add Icon](../media/ITPro-EAC-AddIcon.gif), and then click **Distribution group** or **Security group**, depending on your needs. See [Types of mail-enabled groups](manage-groups-in-eop.md) for the distinction.</span></span> 
    
3. <span data-ttu-id="dc45b-132">Nella pagina **Nuovo gruppo di distribuzione** o **Nuovo gruppo di sicurezza**, completare i seguenti campi:</span><span class="sxs-lookup"><span data-stu-id="dc45b-132">On the **New distribution group** or **New security group** page, complete the following fields:</span></span> 
    
  - <span data-ttu-id="dc45b-p109">**Nome visualizzato** Inserire un nome visualizzato univoco per la propria organizzazione e significativo per gli utenti EOP. Il nome visualizzato è obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="dc45b-p109">**Display name** Type a display name that's unique to your organization and meaningful to EOP users. The display name is required.</span></span> 
    
  - <span data-ttu-id="dc45b-p110">**Alias** Digitare un alias del gruppo contenente massimo 64 caratteri, esclusivo per l'organizzazione. Gli utenti EOP digitano l'alias nel campo A: di un messaggio di posta elettronica. L'alias si risolve nel nome visualizzato del gruppo. Se si modifica l'alias, verrà modificato anche l'indirizzo SMTP primario del gruppo in modo che contenga il nuovo alias. L'alias è obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="dc45b-p110">**Alias** Type a group alias of up to 64 characters that's unique to your organization. EOP users type the alias in the To: line of email messages and the alias resolves to the group's display name. If you change the alias, the primary SMTP address for the group also changes and will contain the new alias. The alias is required.</span></span> 
    
  - <span data-ttu-id="dc45b-139">**Descrizione** Inserire una descrizione del gruppo in modo che le persone possano conoscere gli scopi del gruppo.</span><span class="sxs-lookup"><span data-stu-id="dc45b-139">**Description** Type a description of the group so that people will know the purpose of the group.</span></span> 
    
  - <span data-ttu-id="dc45b-p111">**Proprietari** Per impostazione predefinita, l'utente che crea il gruppo ne diventa proprietario. È possibile aggiungere un proprietario facendo clic su **Aggiungi**![Icona Aggiungi](../media/ITPro-EAC-AddIcon.gif). Ogni gruppo deve presentare almeno un proprietario.</span><span class="sxs-lookup"><span data-stu-id="dc45b-p111">**Owners** By default, the person who creates the group is the owner. You can add an owner by choosing **Add**![Add Icon](../media/ITPro-EAC-AddIcon.gif). All groups must have at least one owner.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="dc45b-143">I proprietari non sono tenuti a essere membri del gruppo.</span><span class="sxs-lookup"><span data-stu-id="dc45b-143">Owners don't have to be members of the group.</span></span> 
  
  - <span data-ttu-id="dc45b-p112">**Membri** Utilizzare questa sezione per aggiungere membri del gruppo e specificare se è necessaria l'approvazione per unirsi al gruppo o abbandonarlo. Per aggiungere membri al gruppo, fare clic su **Aggiungi**![Icona Aggiungi](../media/ITPro-EAC-AddIcon.gif).</span><span class="sxs-lookup"><span data-stu-id="dc45b-p112">**Members** Use this section to add group members and to specify whether approval is required for people to join or leave the group. To add members to the group, click **Add**![Add Icon](../media/ITPro-EAC-AddIcon.gif).</span></span>
    
4. <span data-ttu-id="dc45b-146">Scegliere **OK** per tornare alla pagina originale.</span><span class="sxs-lookup"><span data-stu-id="dc45b-146">Click **OK** to return to the original page.</span></span> 
    
5. <span data-ttu-id="dc45b-p113">Al termine, scegliere **Salva** per creare il gruppo. Il nuovo gruppo verrà visualizzato nell'elenco dei gruppi.</span><span class="sxs-lookup"><span data-stu-id="dc45b-p113">When you've finished, click **Save** to create the group. The new group should appear in the list of groups.</span></span> 
    
## <a name="edit-or-remove-a-group-in-the-eac"></a><span data-ttu-id="dc45b-149">Modificare o rimuovere un gruppo nell'interfaccia di amministrazione di Exchange</span><span class="sxs-lookup"><span data-stu-id="dc45b-149">Edit or remove a group in the EAC</span></span>

1. <span data-ttu-id="dc45b-150">Nell'interfaccia di amministrazione di Exchange, accedere a **Destinatari** \> **Gruppi**.</span><span class="sxs-lookup"><span data-stu-id="dc45b-150">In the EAC, navigate to **Recipients** \> **Groups**.</span></span>
    
2. <span data-ttu-id="dc45b-151">Effettuare una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="dc45b-151">Do one of the following:</span></span>
    
  - <span data-ttu-id="dc45b-152">Per modificare un gruppo: nell'elenco dei gruppi fare clic sul gruppo di distribuzione o di sicurezza che si desidera visualizzare o modificare, quindi fare clic su **modifica** ![icona](../media/ITPro-EAC-EditIcon.gif)modifica.</span><span class="sxs-lookup"><span data-stu-id="dc45b-152">To edit a group: In the list of groups, click the distribution or security group that you want to view or change, and then click **Edit** ![Edit icon](../media/ITPro-EAC-EditIcon.gif).</span></span> <span data-ttu-id="dc45b-153">È possibile aggiornare le impostazioni generali, aggiungere o rimuovere proprietari del gruppo e aggiungere o rimuovere membri del gruppo, secondo necessità.</span><span class="sxs-lookup"><span data-stu-id="dc45b-153">You can update general settings, add or remove group owners, and add or remove group members, as needed.</span></span>
    
  - <span data-ttu-id="dc45b-154">Per rimuovere un gruppo: Selezionare il gruppo e fare clic su **Rimuovi**![Icona Rimuovi](../media/ITPro-EAC-RemoveIcon.gif).</span><span class="sxs-lookup"><span data-stu-id="dc45b-154">To remove a group: Select the group and click **Remove**![Remove icon](../media/ITPro-EAC-RemoveIcon.gif).</span></span>
    
3. <span data-ttu-id="dc45b-155">Dopo avere apportato tutte le modifiche, fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="dc45b-155">When you're finished making your changes, click **Save**.</span></span>
    
## <a name="create-edit-or-remove-a-group-using-remote-windows-powershell"></a><span data-ttu-id="dc45b-156">Creare, modificare o rimuovere un gruppo utilizzando Windows PowerShell remoto</span><span class="sxs-lookup"><span data-stu-id="dc45b-156">Create, edit, or remove a group using remote Windows PowerShell</span></span>

<span data-ttu-id="dc45b-p115">In questa sezione vengono fornite informazioni sulla creazione di gruppi e sulla modifica delle loro proprietà tramite Windows PowerShell remoto. Inoltre, viene illustrato come rimuovere un gruppo esistente.</span><span class="sxs-lookup"><span data-stu-id="dc45b-p115">This section provides information about creating groups and changing their properties by using remote Windows PowerShell. It also shows how to remove an existing group.</span></span> 
  
 <span data-ttu-id="dc45b-159">**Per creare un gruppo tramite Windows PowerShell remoto**</span><span class="sxs-lookup"><span data-stu-id="dc45b-159">**To create a group using remote Windows PowerShell**</span></span>
  
<span data-ttu-id="dc45b-p116">In questo esempio viene utilizzato il cmdlet [New-EOPDistributionGroup](http://technet.microsoft.com/library/4610dfe5-fca8-4ba8-be3c-535d1753e0f4.aspx) per creare un gruppo di distribuzione con alias itadmin e nome Amministratori IT. Inoltre, vengono aggiunti utenti come membri del gruppo.</span><span class="sxs-lookup"><span data-stu-id="dc45b-p116">This example uses the [New-EOPDistributionGroup](http://technet.microsoft.com/library/4610dfe5-fca8-4ba8-be3c-535d1753e0f4.aspx) cmdlet to create a distribution group with an alias of itadmin and the name IT Administrators. It also adds users as members of the group.</span></span> 
  
```Powershell
New-EOPDistributionGroup -Type "Distribution" -Name "IT Administrators" -Alias itadmin -Members @("Member1","Member2","Member3") -ManagedBy "Member1"

```

<span data-ttu-id="dc45b-162">Per creare un gruppo di sicurezza invece di un gruppo di distribuzione, specificare  `-Type "Security"`.</span><span class="sxs-lookup"><span data-stu-id="dc45b-162">To create a security group instead of a distribution group, specify  `-Type "Security"` instead.</span></span> 
  
<span data-ttu-id="dc45b-163">Per verificare che il gruppo Amministratori IT sia stato creato correttamente, eseguire il cmdlet [Get-Recipient](http://technet.microsoft.com/library/2ce6250f-0ad3-4b29-870c-e1d6e1e154bc.aspx) per visualizzare le informazioni relative al nuovo gruppo:</span><span class="sxs-lookup"><span data-stu-id="dc45b-163">To verify that you've successfully created the IT Administrators group, run the [Get-Recipient](http://technet.microsoft.com/library/2ce6250f-0ad3-4b29-870c-e1d6e1e154bc.aspx) cmdlet to display information about the new group:</span></span> 
  
```Powershell
Get-Recipient "IT Administrators" | Format-List

```

<span data-ttu-id="dc45b-164">Per visualizzare un elenco di membri del gruppo, eseguire il cmdlet [Get-DistributionGroupMember](http://technet.microsoft.com/library/15c71bc5-4246-44ac-8b34-8ccd585294b5.aspx) nel modo riportato di seguito:</span><span class="sxs-lookup"><span data-stu-id="dc45b-164">To get a list of members in the group, run the [Get-DistributionGroupMember](http://technet.microsoft.com/library/15c71bc5-4246-44ac-8b34-8ccd585294b5.aspx) cmdlet as follows:</span></span> 
  
```Powershell
Get-DistributionGroupMember "IT Administrators"

```

<span data-ttu-id="dc45b-165">Per visualizzare un elenco completo di tutti i gruppi, eseguire il cmdlet [Get-Recipient](http://technet.microsoft.com/library/2ce6250f-0ad3-4b29-870c-e1d6e1e154bc.aspx) nel modo riportato di seguito:</span><span class="sxs-lookup"><span data-stu-id="dc45b-165">To get a full list of all your groups, run the [Get-Recipient](http://technet.microsoft.com/library/2ce6250f-0ad3-4b29-870c-e1d6e1e154bc.aspx) cmdlet as follows:</span></span> 
  
```Powershell
Get-Recipient -RecipientType "MailUniversalDistributionGroup" | FT | more

```

 <span data-ttu-id="dc45b-166">**Modificare le proprietà di un gruppo utilizzando Windows PowerShell remoto**</span><span class="sxs-lookup"><span data-stu-id="dc45b-166">**To change the properties of a group using remote Windows PowerShell**</span></span>
  
<span data-ttu-id="dc45b-p117">Utilizzare i cmdlet [Get-Recipient](http://technet.microsoft.com/library/2ce6250f-0ad3-4b29-870c-e1d6e1e154bc.aspx) e [Set-EOPDistributionGroup](http://technet.microsoft.com/library/689a66c5-a524-4870-88f3-091fd6eae3b7.aspx) per visualizzare e modificare le proprietà dei gruppi. Un vantaggio dell'utilizzo di PowerShell remoto invece dell'interfaccia di amministrazione di Excel consiste nella possibilità di modificare le proprietà di più gruppi.</span><span class="sxs-lookup"><span data-stu-id="dc45b-p117">Use the [Get-Recipient](http://technet.microsoft.com/library/2ce6250f-0ad3-4b29-870c-e1d6e1e154bc.aspx) and [Set-EOPDistributionGroup](http://technet.microsoft.com/library/689a66c5-a524-4870-88f3-091fd6eae3b7.aspx) cmdlets to view and change properties for groups. An advantage of using remote PowerShell instead of the EAC is the ability to change properties for multiple groups.</span></span> 
  
<span data-ttu-id="dc45b-169">Di seguito, sono riportati alcuni esempi relativi all'utilizzo di Windows PowerShell per modificare le proprietà del gruppo.</span><span class="sxs-lookup"><span data-stu-id="dc45b-169">Here are some examples of using remote Windows PowerShell to change group properties.</span></span>
  
<span data-ttu-id="dc45b-170">In questo esempio, si utilizza il cmdlet [Set-EOPDistributionGroup](http://technet.microsoft.com/library/689a66c5-a524-4870-88f3-091fd6eae3b7.aspx) per modificare l'indirizzo SMTP principale (denominato anche indirizzo di risposta) del gruppo Seattle Employees in sea.employees@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="dc45b-170">This example uses the [Set-EOPDistributionGroup](http://technet.microsoft.com/library/689a66c5-a524-4870-88f3-091fd6eae3b7.aspx) cmdlet to change the primary SMTP address (also called the reply address) for the Seattle Employees group to sea.employees@contoso.com.</span></span> 
  
```Powershell
Set-EOPDistributionGroup "Seattle Employees" -PrimarysmptAddress "sea.employees@contoso.com"

```

<span data-ttu-id="dc45b-p118">Per verificare di aver modificato correttamente le proprietà di un gruppo, utilizzare il cmdlet [Get-Recipient](http://technet.microsoft.com/library/2ce6250f-0ad3-4b29-870c-e1d6e1e154bc.aspx) per verificare le modifiche. Uno dei vantaggi offerti dall'utilizzo di PowerShell remoto è la possibilità di visualizzare più proprietà per più gruppi. Nell'esempio precedente, in cui è stato modificato il gruppo di indirizzi SMTP, eseguire questo comando per verificare il nuovo valore:</span><span class="sxs-lookup"><span data-stu-id="dc45b-p118">To verify that you've successfully changed the properties for a group, use the [Get-Recipient](http://technet.microsoft.com/library/2ce6250f-0ad3-4b29-870c-e1d6e1e154bc.aspx) cmdlet to verify the changes. One advantage of using remote PowerShell is that you can view multiple properties for multiple groups. In the previous example where the primary SMTP address group was changed, run the following command to verify the new value:</span></span> 
  
```Powershell
Get-Recipient "Seattle Employees" | FL "PrimarySmtpAddress"

```

<span data-ttu-id="dc45b-p119">In questo esempio, viene utilizzato il cmdlet [Update-EOPDistributionGroupMember](http://technet.microsoft.com/library/a6d4f790-1b94-42f8-af6f-fa79c504d8ec.aspx) per aggiornare tutti i membri del gruppo Seattle Employees. Utilizzare una virgola per tutti i membri.</span><span class="sxs-lookup"><span data-stu-id="dc45b-p119">This example uses the [Update-EOPDistributionGroupMember](http://technet.microsoft.com/library/a6d4f790-1b94-42f8-af6f-fa79c504d8ec.aspx) cmdlet to update all the members of the Seattle Employees group. Use a comma to separate all members.</span></span> 
  
```Powershell
Update-EOPDistributionGroupMember -Identity "Seattle Employees" -Members @("Member1","Member2","Member3","Member4","Member5")

```

<span data-ttu-id="dc45b-176">Per visualizzare un elenco di tutti i membri del gruppo Seattle Employees, utilizzare il cmdlet [Get-DistributionGroupMember](http://technet.microsoft.com/library/15c71bc5-4246-44ac-8b34-8ccd585294b5.aspx) nel modo riportato di seguito:</span><span class="sxs-lookup"><span data-stu-id="dc45b-176">To get the list of all the members in the group Seattle Employees, use the [Get-DistributionGroupMember](http://technet.microsoft.com/library/15c71bc5-4246-44ac-8b34-8ccd585294b5.aspx) cmdlet as follows:</span></span> 
  
```Powershell
Get-DistributionGroupMember "Seattle Employees"

```

 <span data-ttu-id="dc45b-177">**Per rimuovere un gruppo tramite Windows PowerShell remoto**</span><span class="sxs-lookup"><span data-stu-id="dc45b-177">**To remove a group using remote Windows PowerShell**</span></span>
  
<span data-ttu-id="dc45b-178">In questo esempio viene utilizzato il cmdlet [Remove-EOPDistributionGroup](http://technet.microsoft.com/library/a17b1307-3187-40b0-a438-c7b35a34c002.aspx) per rimuovere un gruppo di distribuzione denominato Amministratori IT.</span><span class="sxs-lookup"><span data-stu-id="dc45b-178">This example uses the [Remove-EOPDistributionGroup](http://technet.microsoft.com/library/a17b1307-3187-40b0-a438-c7b35a34c002.aspx) cmdlet to remove a distribution group named IT Administrators.</span></span> 
  
```Powershell
Remove-EOPDistributionGroup -Identity "IT Administrators" 

```

<span data-ttu-id="dc45b-179">Per verificare che il gruppo è stato rimosso, eseguire il cmdlet [Get-Recipient](http://technet.microsoft.com/library/2ce6250f-0ad3-4b29-870c-e1d6e1e154bc.aspx) nel modo seguente, quindi confermare che l'eliminazione del gruppo (in questo caso, "Amministratori IT").</span><span class="sxs-lookup"><span data-stu-id="dc45b-179">To verify that the group was removed, run the [Get-Recipient](http://technet.microsoft.com/library/2ce6250f-0ad3-4b29-870c-e1d6e1e154bc.aspx) cmdlet as follows, and confirm that the group (in this case "It Administrators") was deleted.</span></span> 
  
```Powershell
Get-Recipient -RecipientType "MailUniversalDistributionGroup"

```


