---
title: Progettare un sito del team di SharePoint Online isolato
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/15/2017
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
search.appverid:
- MET150
ms.collection: Ent_O365
ms.custom: Ent_Solutions
ms.assetid: 775a4e9e-3135-4a48-b32f-bbdd9f2bd0aa
description: 'Sintesi: viene fornita la procedura dettagliata per la progettazione dei siti del team di SharePoint Online isolati.'
ms.openlocfilehash: bd36044eb16b9f6ee3ee9bbb444fe8f4efe2fd63
ms.sourcegitcommit: e0f016aca7befc8806233a492ee916cbe646094f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/27/2018
ms.locfileid: "25345808"
---
# <a name="design-an-isolated-sharepoint-online-team-site"></a><span data-ttu-id="a76f8-103">Progettare un sito del team di SharePoint Online isolato</span><span class="sxs-lookup"><span data-stu-id="a76f8-103">Design an isolated SharePoint Online team site</span></span>

 <span data-ttu-id="a76f8-104">**Sintesi:** viene fornita la procedura dettagliata per la progettazione dei siti del team di SharePoint Online isolati.</span><span class="sxs-lookup"><span data-stu-id="a76f8-104">**Summary:** Step through the design process for isolated SharePoint Online team sites.</span></span>
  
<span data-ttu-id="a76f8-105">In questo articolo viene fornita una descrizione dettagliata delle scelte fondamentali relative alla progettazione necessarie prima di creare un sito del team di SharePoint Online isolato.</span><span class="sxs-lookup"><span data-stu-id="a76f8-105">This article takes you through the key design decisions you must make before creating an isolated SharePoint Online team site.</span></span>
  
## <a name="phase-1-determine-your-sharepoint-groups-and-permission-levels"></a><span data-ttu-id="a76f8-106">Fase 1: determinare i gruppi di SharePoint e i livelli di autorizzazione</span><span class="sxs-lookup"><span data-stu-id="a76f8-106">Phase 1: Determine your SharePoint groups and permission levels</span></span>

<span data-ttu-id="a76f8-107">Per impostazione predefinita, ogni sito del team di SharePoint Online viene creato con i seguenti gruppi di SharePoint:</span><span class="sxs-lookup"><span data-stu-id="a76f8-107">Every SharePoint Online team site by default is created with the following SharePoint groups:</span></span>
  
- <span data-ttu-id="a76f8-108">\<nome del sito > membri</span><span class="sxs-lookup"><span data-stu-id="a76f8-108">\<site name> Members</span></span>
    
- <span data-ttu-id="a76f8-109">\<nome del sito > visitatori</span><span class="sxs-lookup"><span data-stu-id="a76f8-109">\<site name> Visitors</span></span>
    
- <span data-ttu-id="a76f8-110">\<nome del sito > proprietari</span><span class="sxs-lookup"><span data-stu-id="a76f8-110">\<site name> Owners</span></span>
    
<span data-ttu-id="a76f8-111">Questi gruppi sono separati dai gruppi di Office 365 e Azure Active Directory (AD) e costituiscono la base per l'assegnazione di autorizzazioni per le risorse del sito.</span><span class="sxs-lookup"><span data-stu-id="a76f8-111">These groups are separate from Office 365 and Azure Active Directory (AD) groups and are the basis for assigning permissions for the resources of the site.</span></span>
  
<span data-ttu-id="a76f8-p101">Il set di autorizzazioni specifiche che determina le operazioni disponibili per un membro di un gruppo di SharePoint in un sito rappresenta un livello di autorizzazione. Esistono tre livelli di autorizzazione per impostazione predefinita per un sito del team di SharePoint Online: Modifica, Lettura e Controllo completo. Nella tabella seguente vengono illustrati la correlazione predefinita dei gruppi di SharePoint e i livelli di autorizzazione assegnati:</span><span class="sxs-lookup"><span data-stu-id="a76f8-p101">The set of specific permissions that determines what a member of a SharePoint group can do in a site is a permission level. There are three permission levels by default for a SharePoint Online team site: Edit, Read, and Full control. The following table shows the default correlation of SharePoint groups and assigned permission levels:</span></span>
  
|<span data-ttu-id="a76f8-115">**Gruppo di SharePoint**</span><span class="sxs-lookup"><span data-stu-id="a76f8-115">**SharePoint group**</span></span>|<span data-ttu-id="a76f8-116">**Livello di autorizzazione**</span><span class="sxs-lookup"><span data-stu-id="a76f8-116">**Permission level**</span></span>|
|:-----|:-----|
|<span data-ttu-id="a76f8-117">\<nome del sito > membri</span><span class="sxs-lookup"><span data-stu-id="a76f8-117">\<site name> Members</span></span>  <br/> |<span data-ttu-id="a76f8-118">Modifica</span><span class="sxs-lookup"><span data-stu-id="a76f8-118">Edit</span></span>  <br/> |
|<span data-ttu-id="a76f8-119">\<nome del sito > visitatori</span><span class="sxs-lookup"><span data-stu-id="a76f8-119">\<site name> Visitors</span></span>  <br/> |<span data-ttu-id="a76f8-120">Lettura</span><span class="sxs-lookup"><span data-stu-id="a76f8-120">Read</span></span>  <br/> |
|<span data-ttu-id="a76f8-121">\<nome del sito > proprietari</span><span class="sxs-lookup"><span data-stu-id="a76f8-121">\<site name> Owners</span></span>  <br/> |<span data-ttu-id="a76f8-122">Controllo completo</span><span class="sxs-lookup"><span data-stu-id="a76f8-122">Full control</span></span>  <br/> |
   
 <span data-ttu-id="a76f8-p102">**Procedura consigliata:** È possibile creare ulteriori gruppi di SharePoint e livelli di autorizzazione. Tuttavia, è consigliabile usare questi gruppi e livelli di autorizzazione di SharePoint predefiniti per il sito di SharePoint Online isolato.</span><span class="sxs-lookup"><span data-stu-id="a76f8-p102">**Best practice:** You can create additional SharePoint groups and permission levels. However, we recommend using the default SharePoint groups and permission levels for your isolated SharePoint Online site.</span></span>
  
<span data-ttu-id="a76f8-125">Di seguito sono i gruppi di SharePoint predefiniti e i livelli di autorizzazione.</span><span class="sxs-lookup"><span data-stu-id="a76f8-125">Here are the default SharePoint groups and permission levels.</span></span>
  
![I gruppi e livelli di autorizzazione di SharePoint predefiniti per il sito di SharePoint Online.](media/3f892ab4-6479-42f0-a505-1ba0ef94b9c6.png)
  
## <a name="phase-2-assign-permissions-to-users-with-access-groups"></a><span data-ttu-id="a76f8-127">Fase 2: assegnare autorizzazioni agli utenti con i gruppi di accesso</span><span class="sxs-lookup"><span data-stu-id="a76f8-127">Phase 2: Assign permissions to users with access groups</span></span>

<span data-ttu-id="a76f8-p103">È possibile assegnare autorizzazioni agli utenti aggiungendo il loro account utente (o un gruppo di Office 365 o Azure AD di cui l'account utente è membro) ai gruppi di SharePoint. Al termine di questa operazione, agli account utente di Office 365, direttamente o indirettamente tramite l'appartenenza a un gruppo di Office 365 o Azure AD, viene assegnato il livello di autorizzazione associato al gruppo di SharePoint.</span><span class="sxs-lookup"><span data-stu-id="a76f8-p103">You can assign permissions to users by adding their user account, or an Office 365 or Azure AD group of which the user account is a member, to the SharePoint groups. Once added, the Office 365 user accounts, either directly or indirectly via membership in an Office 365 or Azure AD group, are assigned the permission level associated with the SharePoint group.</span></span>
  
<span data-ttu-id="a76f8-130">Utilizzo di gruppi di SharePoint predefiniti, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="a76f8-130">Using the default SharePoint groups as an example:</span></span>
  
- <span data-ttu-id="a76f8-131">Membri del \*\* \<nome del sito > membri\*\* gruppo di SharePoint, che può includere sia gli account utente e gruppi, viene assegnato il livello di autorizzazione **Modifica**</span><span class="sxs-lookup"><span data-stu-id="a76f8-131">Members of the **\<site name> Members** SharePoint group, which can include both user accounts and groups, are assigned the **Edit** permission level</span></span>
    
- <span data-ttu-id="a76f8-132">Membri del \*\* \<nome del sito > visitatori\*\* gruppo di SharePoint, che può includere sia gli account utente e gruppi, viene assegnato il livello di autorizzazione di **lettura**</span><span class="sxs-lookup"><span data-stu-id="a76f8-132">Members of the **\<site name> Visitors** SharePoint group, which can include both user accounts and groups, are assigned the **Read** permission level</span></span>
    
- <span data-ttu-id="a76f8-133">Membri del \*\* \<nome del sito > proprietari\*\* gruppo di SharePoint, che può includere sia gli account utente e gruppi, viene assegnato il livello di autorizzazione **controllo completo**</span><span class="sxs-lookup"><span data-stu-id="a76f8-133">Members of the **\<site name> Owners** SharePoint group, which can include both user accounts and groups, are assigned the **Full control** permission level</span></span>
    
 <span data-ttu-id="a76f8-p104">**Procedura consigliata:** Anche se è possibile gestire le autorizzazioni per singoli account utente, è consigliabile utilizzare un singolo gruppo di Azure AD, noto come gruppo di accesso. In questo modo si semplifica la gestione delle autorizzazioni tramite l'appartenenza al gruppo di accesso, anziché gestire l'elenco di account utente per ogni gruppo di SharePoint.</span><span class="sxs-lookup"><span data-stu-id="a76f8-p104">**Best practice:** Although you can manage permissions through individual user accounts, we recommend that you use a single Azure AD group, known as an access group, instead. This simplifies the management of permissions through membership in the access group, rather than managing the list of user accounts for each SharePoint group.</span></span>
  
<span data-ttu-id="a76f8-p105">I gruppi di Azure AD per Office 365 sono diversi da quelli di Office 365. I gruppi di Azure AD vengono visualizzati nell'interfaccia di amministrazione di Office con **Tipo** impostato su **Sicurezza** e non dispongono di un indirizzo di posta elettronica. I gruppi di Azure AD possono essere gestiti all'interno di:</span><span class="sxs-lookup"><span data-stu-id="a76f8-p105">Azure AD groups for Office 365 are different than Office 365 groups. Azure AD groups appear in the Office Admin center with their **Type** set to **Security** and do not have an email address. Azure AD groups can be managed within:</span></span>
  
- <span data-ttu-id="a76f8-139">Windows Server Active Directory (AD)</span><span class="sxs-lookup"><span data-stu-id="a76f8-139">Windows Server Active Directory (AD)</span></span>
    
    <span data-ttu-id="a76f8-p106">Questi sono i gruppi che sono stati creati nell'infrastruttura di Windows Server AD locale e sincronizzati con l'abbonamento a Office 365. Nell'interfaccia di amministrazione di Office, questi gruppi hanno lo **Stato** impostato su **Sincronizzato con Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="a76f8-p106">These are groups that have been created in your on-premises Windows Server AD infrastructure and synchronized to your Office 365 subscription. In the Office Admin center, these groups have a **Status** of **Synched with active directory**.</span></span>
    
- <span data-ttu-id="a76f8-142">Office 365</span><span class="sxs-lookup"><span data-stu-id="a76f8-142">Office 365</span></span>
    
    <span data-ttu-id="a76f8-p107">Questi sono i gruppi che sono stati creati mediante l'interfaccia di amministrazione di Office, il portale di Azure o Microsoft PowerShell. Nell'interfaccia di amministrazione di Office, questi gruppi hanno lo **Stato** impostato su **Cloud**.</span><span class="sxs-lookup"><span data-stu-id="a76f8-p107">These are groups that have been created using either the Office Admin center, the Azure portal, or Microsoft PowerShell. In the Office Admin center, these groups have a **Status** of **Cloud**.</span></span>
    
 <span data-ttu-id="a76f8-145">**Procedura consigliata:** Se si usa Windows Server AD locale e si esegue la sincronizzazione con l'abbonamento a Office 365, gestire utenti e gruppi con Windows Server AD.</span><span class="sxs-lookup"><span data-stu-id="a76f8-145">**Best practice:** If you are using Windows Server AD on-premises and synchronizing with your Office 365 subscription, perform your user and group management with Windows Server AD.</span></span>
  
<span data-ttu-id="a76f8-146">Per i siti del team di SharePoint Online isolati, la struttura del gruppo consigliata è simile alla seguente:</span><span class="sxs-lookup"><span data-stu-id="a76f8-146">For isolated SharePoint Online team sites, the recommended group structure looks like this:</span></span>
  
|<span data-ttu-id="a76f8-147">**Gruppo di SharePoint**</span><span class="sxs-lookup"><span data-stu-id="a76f8-147">**SharePoint group**</span></span>|<span data-ttu-id="a76f8-148">**Gruppo di accesso basato su Azure AD**</span><span class="sxs-lookup"><span data-stu-id="a76f8-148">**Azure AD-based access group**</span></span>|<span data-ttu-id="a76f8-149">**Livello di autorizzazione**</span><span class="sxs-lookup"><span data-stu-id="a76f8-149">**Permission level**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="a76f8-150">\<nome del sito > membri</span><span class="sxs-lookup"><span data-stu-id="a76f8-150">\<site name> Members</span></span>  <br/> |<span data-ttu-id="a76f8-151">\<nome del sito > membri</span><span class="sxs-lookup"><span data-stu-id="a76f8-151">\<site name> Members</span></span>  <br/> |<span data-ttu-id="a76f8-152">Modifica</span><span class="sxs-lookup"><span data-stu-id="a76f8-152">Edit</span></span>  <br/> |
|<span data-ttu-id="a76f8-153">\<nome del sito > visitatori</span><span class="sxs-lookup"><span data-stu-id="a76f8-153">\<site name> Visitors</span></span>  <br/> |<span data-ttu-id="a76f8-154">\<nome del sito > visualizzatori</span><span class="sxs-lookup"><span data-stu-id="a76f8-154">\<site name> Viewers</span></span>  <br/> |<span data-ttu-id="a76f8-155">Lettura</span><span class="sxs-lookup"><span data-stu-id="a76f8-155">Read</span></span>  <br/> |
|<span data-ttu-id="a76f8-156">\<nome del sito > proprietari</span><span class="sxs-lookup"><span data-stu-id="a76f8-156">\<site name> Owners</span></span>  <br/> |<span data-ttu-id="a76f8-157">\<nome del sito > Admins</span><span class="sxs-lookup"><span data-stu-id="a76f8-157">\<site name> Admins</span></span>  <br/> |<span data-ttu-id="a76f8-158">Controllo completo</span><span class="sxs-lookup"><span data-stu-id="a76f8-158">Full control</span></span>  <br/> |
   
 <span data-ttu-id="a76f8-p108">**Procedura consigliata:** Sebbene sia possibile utilizzare i gruppi di Office 365 o di Azure AD come membri dei gruppi di SharePoint, è consigliabile utilizzare i gruppi di Azure AD. I gruppi di Azure AD, gestiti tramite Windows Server AD o Office 365, offrono una maggiore flessibilità per usare i gruppi nidificati per assegnare le autorizzazioni.</span><span class="sxs-lookup"><span data-stu-id="a76f8-p108">**Best practice:** Although you can use either Office 365 or Azure AD groups as members of SharePoint groups, we recommend that you use Azure AD groups. Azure AD groups, managed either through Windows Server AD or Office 365, give you more flexibility to use nested groups to assign permissions.</span></span>
  
<span data-ttu-id="a76f8-161">Di seguito è l'impostazione predefinita i gruppi di SharePoint configurati per l'utilizzo di gruppi di Azure Active Directory-based access.</span><span class="sxs-lookup"><span data-stu-id="a76f8-161">Here are the default SharePoint groups configured to use Azure AD-based access groups.</span></span>
  
![Utilizzo dei gruppi di accesso come membri dei gruppi del sito di SharePoint Online predefinito.](media/50a76328-ae69-483e-9029-ac4e7357b5ef.png)
  
<span data-ttu-id="a76f8-163">Quando si progettano i tre gruppi di accesso, tenere presente quanto segue:</span><span class="sxs-lookup"><span data-stu-id="a76f8-163">When designing the three access groups, keep the following in mind:</span></span>
  
- <span data-ttu-id="a76f8-164">È necessario solo alcuni membri il \*\* \<nome del sito > Admins\*\* gruppo di accesso, corrispondente a un numero limitato di SharePoint Online amministratori che gestiscono il sito del team.</span><span class="sxs-lookup"><span data-stu-id="a76f8-164">There should be only a few members in the **\<site name> Admins** access group, corresponding to a small number of SharePoint Online administrators who are managing the team site.</span></span>
    
- <span data-ttu-id="a76f8-p109">La maggior parte dei membri del sito sono nel \*\* \<nome del sito > membri\*\* o \*\* \<nome del sito > visualizzatori\*\* accedere ai gruppi. Dal momento che i membri del sito di \*\* \<nome del sito > membri\*\* gruppo di accesso hanno la possibilità di eliminare o modificare le risorse nel sito, valutare attentamente l'appartenenza al. In caso di dubbi, aggiungere il membro del sito per il \*\* \<nome del sito > visualizzatori\*\* gruppo di accesso.</span><span class="sxs-lookup"><span data-stu-id="a76f8-p109">Most of your site members are in the **\<site name> Members** or **\<site name> Viewers** access groups. Because site members in the **\<site name> Members** access group have the ability to delete or modify resources in the site, carefully consider its membership. When in doubt, add the site member to the **\<site name> Viewers** access group.</span></span>
    
<span data-ttu-id="a76f8-168">Di seguito è riportato un esempio dei gruppi di accesso per un sito isolato denominato ProjectX e i gruppi di SharePoint.</span><span class="sxs-lookup"><span data-stu-id="a76f8-168">Here is an example of the SharePoint groups and access groups for an isolated site named ProjectX.</span></span>
  
![Un esempio di utilizzo dei gruppi di accesso per un sito di SharePoint Online denominato ProjectX.](media/13afe542-9ffd-4671-9f48-210a0e2a502a.png)
  
## <a name="phase-3-use-nested-azure-ad-groups"></a><span data-ttu-id="a76f8-170">Fase 3: Utilizzare nidificate gruppi di Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="a76f8-170">Phase 3: Use nested Azure AD groups</span></span>

<span data-ttu-id="a76f8-p110">Per un progetto limitato a un numero limitato di utenti, un singolo livello dei gruppi di Azure Active Directory-based access aggiunti ai gruppi del sito di SharePoint più adatto alla maggior parte degli scenari. Tuttavia, se si dispone di un numero elevato di utenti e agli utenti che già membri di definizione dei gruppi di Azure Active Directory, è possibile più facilmente assegnare le autorizzazioni di SharePoint tramite gruppi annidati o i gruppi che contengono altri gruppi come membri.</span><span class="sxs-lookup"><span data-stu-id="a76f8-p110">For a project confined to a small number of people, a single level of Azure AD-based access groups added to the SharePoint groups of the site will fit most scenarios. However, if you have a large number of people and those people are already members of established Azure AD groups, you can more easily assign SharePoint permissions by using nested groups, or groups that contain other groups as members.</span></span>
  
<span data-ttu-id="a76f8-p111">Ad esempio, si desidera creare un sito del team di SharePoint Online isolato per la collaborazione tra i dirigenti dei reparti delle vendite, marketing, ingegneria, legali e del supporto e tali reparti fanno parte di gruppi di account utente della direzione esecutiva. Anziché creare un nuovo gruppo per i nuovi membri del sito e inserirvi tutti i singoli account utente esecutivi, inserire i gruppi di dirigenti esistenti per ogni reparto nel nuovo gruppo.</span><span class="sxs-lookup"><span data-stu-id="a76f8-p111">For example, you want to create an isolated SharePoint online team site for collaboration among the executives of the sales, marketing, engineering, legal, and support departments and those departments already their own groups with executive user account membership. Rather than creating a new group for the new site members and placing all the individual executive user accounts in it, put the existing executive groups for each department in the new group.</span></span>
  
 <span data-ttu-id="a76f8-p112"> Se si condivide un abbonamento a Office 365 tra più organizzazioni, un solo livello di appartenenza ai gruppi per un sito isolato per un'organizzazione potrebbe diventare difficile da gestire a causa del gran numero di account utente. In questo caso, è possibile utilizzare gruppi di Azure AD per ogni organizzazione con i gruppi all'interno delle organizzazioni per gestire le autorizzazioni.</span><span class="sxs-lookup"><span data-stu-id="a76f8-p112">If you are sharing an Office 365 subscription between multiple organizations, a single level of group membership for an isolated site for an organization might become difficult to manage due to the sheer number of user accounts. In this case, you can use nested Azure AD groups for each organization that contain the groups within their organizations to manage the permissions.</span></span>
  
<span data-ttu-id="a76f8-177">Per utilizzare i gruppi di Azure AD nidificati:</span><span class="sxs-lookup"><span data-stu-id="a76f8-177">To use nested Azure AD groups:</span></span>
  
1. <span data-ttu-id="a76f8-178">Individuare o creare i gruppi di Azure AD che conterranno gli account utente e aggiungere gli account utente appropriati come membri.</span><span class="sxs-lookup"><span data-stu-id="a76f8-178">Identify or create the Azure AD groups that will contain user accounts and add the appropriate user accounts as members.</span></span>
    
2. <span data-ttu-id="a76f8-179">Creare il gruppo di accesso basato su Azure AD che conterrà gli altri gruppi di Azure AD e aggiungere i gruppi come membri.</span><span class="sxs-lookup"><span data-stu-id="a76f8-179">Create the container Azure AD-based access group that will contain the other Azure AD groups and add those groups as members.</span></span>
    
3.  <span data-ttu-id="a76f8-180"> Per il livello di accesso appropriato per il gruppo di accesso contenitore, individuare il gruppo di SharePoint e il livello di autorizzazione corrispondente.</span><span class="sxs-lookup"><span data-stu-id="a76f8-180">For the appropriate level of access for the container access group, identify the SharePoint group and corresponding permission level.</span></span>
    
> [!NOTE]
> <span data-ttu-id="a76f8-181">Non è possibile utilizzare i gruppi di Office 365 nidificati.</span><span class="sxs-lookup"><span data-stu-id="a76f8-181">You cannot use nested Office 365 groups.</span></span> 
  
<span data-ttu-id="a76f8-182">Di seguito è riportato un esempio di Azure Active Directory annidati gruppi ProjectX membri gruppo di accesso.</span><span class="sxs-lookup"><span data-stu-id="a76f8-182">Here is an example of nested Azure AD groups for the ProjectX member access group.</span></span>
  
![Esempio di utilizzo dei gruppi di accesso per il gruppo di accesso come membri per il sito ProjectX.](media/2abca710-bf9e-4ce8-9bcd-a8e128264fb1.png)
  
<span data-ttu-id="a76f8-184">Poiché tutti gli account utente di ricerca, Engineering e Project leads team hanno lo scopo di essere membri del sito, è più semplice aggiungere i gruppi di Azure Active Directory al gruppo accesso ProjectX membri.</span><span class="sxs-lookup"><span data-stu-id="a76f8-184">Because all of the user accounts in the Research, Engineering, and Project leads teams are intended to be site members, it is easier to add their Azure AD groups to the ProjectX Members access group.</span></span>
  
## <a name="next-step"></a><span data-ttu-id="a76f8-185">Passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="a76f8-185">Next step</span></span>

<span data-ttu-id="a76f8-186">Quando si è pronti per creare e configurare un sito isolato nell'ambiente di produzione, vedere [Deploy an isolated SharePoint Online team site](deploy-an-isolated-sharepoint-online-team-site.md).</span><span class="sxs-lookup"><span data-stu-id="a76f8-186">When you are ready to create and configure an isolated site in production, see [Deploy an isolated SharePoint Online team site](deploy-an-isolated-sharepoint-online-team-site.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="a76f8-187">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a76f8-187">See Also</span></span>

[<span data-ttu-id="a76f8-188">Siti del team di SharePoint Online isolati</span><span class="sxs-lookup"><span data-stu-id="a76f8-188">Isolated SharePoint Online team sites</span></span>](isolated-sharepoint-online-team-sites.md)
  
[<span data-ttu-id="a76f8-189">Gestire un sito del team di SharePoint Online isolato</span><span class="sxs-lookup"><span data-stu-id="a76f8-189">Manage an isolated SharePoint Online team site</span></span>](manage-an-isolated-sharepoint-online-team-site.md)

[<span data-ttu-id="a76f8-190">Distribuire un sito del team di SharePoint Online isolato</span><span class="sxs-lookup"><span data-stu-id="a76f8-190">Deploy an isolated SharePoint Online team site</span></span>](deploy-an-isolated-sharepoint-online-team-site.md)



