---
title: Controllare i dati in Office 365 con Customer Key
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 8/1/2018
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: f2cd475a-e592-46cf-80a3-1bfb0fa17697
ms.collection:
- M365-security-compliance
description: Informazioni su come configurare Customer Key per Office 365 per Exchange Online, Skype for business, SharePoint Online e OneDrive for business. Con il codice "Customer Key", è possibile controllare le chiavi di crittografia dell'organizzazione e quindi configurare Office 365 per utilizzarle per crittografare i dati a riposo nei datacenter di Microsoft.
ms.openlocfilehash: 219ddb94727cd2b708f734a77a8397b3bc3f1064
ms.sourcegitcommit: baf23be44f1ed5abbf84f140b5ffa64fce605478
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/26/2019
ms.locfileid: "30296669"
---
# <a name="controlling-your-data-in-office-365-using-customer-key"></a><span data-ttu-id="9ed6d-104">Controllare i dati in Office 365 con Customer Key</span><span class="sxs-lookup"><span data-stu-id="9ed6d-104">Controlling your data in Office 365 using Customer Key</span></span>

<span data-ttu-id="9ed6d-p102">Con il codice "Customer Key", è possibile controllare le chiavi di crittografia dell'organizzazione e quindi configurare Office 365 per utilizzarle per crittografare i dati a riposo nei data center di Microsoft. In altre parole, la chiave del cliente consente ai clienti di aggiungere un livello di crittografia che appartiene a loro, con le chiavi. Data at rest include i dati di Exchange Online e Skype for business archiviati nelle cassette postali e nei file archiviati in SharePoint Online e OneDrive for business.</span><span class="sxs-lookup"><span data-stu-id="9ed6d-p102">With Customer Key, you control your organization's encryption keys and then configure Office 365 to use them to encrypt your data at rest in Microsoft's data centers. In other words, Customer Key allows customers to add a layer of encryption that belongs to them, with their keys. Data at rest includes data from Exchange Online and Skype for Business that is stored in mailboxes and files that are stored in SharePoint Online and OneDrive for Business.</span></span>
  
<span data-ttu-id="9ed6d-p103">È necessario configurare Azure prima di poter utilizzare la chiave del cliente per Office 365. In questo argomento vengono descritti i passaggi da seguire per creare e configurare le risorse di Azure necessarie, quindi vengono illustrati i passaggi per la configurazione della chiave del cliente in Office 365. Dopo aver completato l'installazione di Azure, è possibile stabilire quali criteri e quindi quali chiavi, per assegnare alle cassette postali e ai file nell'organizzazione. Le cassette postali e i file per cui non si assegna un criterio utilizzeranno i criteri di crittografia controllati e gestiti da Microsoft. Per ulteriori informazioni sulla chiave del cliente o per una panoramica generale, vedere le [domande frequenti su Customer Key per Office 365](service-encryption-with-customer-key-faq.md).</span><span class="sxs-lookup"><span data-stu-id="9ed6d-p103">You must set up Azure before you can use Customer Key for Office 365. This topic describes the steps you need to follow to create and configure the required Azure resources and then provides the steps for setting up Customer Key in Office 365. After you have completed Azure setup, you determine which policy, and therefore, which keys, to assign to mailboxes and files in your organization. Mailboxes and files for which you don't assign a policy will use encryption policies that are controlled and managed by Microsoft. For more information about Customer Key, or for a general overview, see the [Customer Key for Office 365 FAQ](service-encryption-with-customer-key-faq.md).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="9ed6d-p104">È consigliabile attenersi alle procedure consigliate riportate in questo argomento. Questi sono denominati **Suggerimento** e **importante**. La chiave Customer consente di controllare le chiavi di crittografia radice il cui ambito può essere grande come l'intera organizzazione. Questo significa che gli errori commessi con queste chiavi possono avere un impatto generale e possono causare interruzioni del servizio o perdita irrevocabile dei dati.</span><span class="sxs-lookup"><span data-stu-id="9ed6d-p104">We strongly recommend that you follow the best practices in this topic. These are called out as **TIP** and **IMPORTANT**. Customer Key gives you control over root encryption keys whose scope can be as large as your entire organization. This means that mistakes made with these keys can have a broad impact and may result in service interruptions or irrevocable loss of your data.</span></span> 
  
## <a name="before-you-begin-setting-up-customer-key"></a><span data-ttu-id="9ed6d-117">Prima di iniziare a configurare la chiave del cliente</span><span class="sxs-lookup"><span data-stu-id="9ed6d-117">Before you begin setting up Customer Key</span></span>
<span data-ttu-id="9ed6d-118"><a name="Beforeyoustart"> </a></span><span class="sxs-lookup"><span data-stu-id="9ed6d-118"></span></span>

<span data-ttu-id="9ed6d-p105">Prima di iniziare, assicurarsi di disporre della licenza appropriata per la propria organizzazione. La chiave del cliente in Office 365 è disponibile in Office 365 E5 o nella SKU di conformità avanzata.</span><span class="sxs-lookup"><span data-stu-id="9ed6d-p105">Before you get started, be sure you have the appropriate licensing for your organization. Customer Key in Office 365 is offered in Office 365 E5 or the Advanced Compliance SKU.</span></span>
  
<span data-ttu-id="9ed6d-p106">Per comprendere i concetti e le procedure in questo argomento, è quindi necessario esaminare la documentazione relativa alla [chiave del Vault di Azure](https://azure.microsoft.com/en-us/documentation/services/key-vault/) . Inoltre, acquisire familiarità con i termini utilizzati in Azure, ad esempio [tenant](https://msdn.microsoft.com/library/azure/jj573650.aspx#BKMK_WhatIsAnAzureADTenant).</span><span class="sxs-lookup"><span data-stu-id="9ed6d-p106">Then, to understand the concepts and procedures in this topic, you should review the [Azure Key Vault](https://azure.microsoft.com/en-us/documentation/services/key-vault/) documentation. Also, become familiar with the terms used in Azure, for example, [tenant](https://msdn.microsoft.com/library/azure/jj573650.aspx#BKMK_WhatIsAnAzureADTenant).</span></span>
  
<span data-ttu-id="9ed6d-123">Per fornire commenti e suggerimenti sulla chiave del cliente, inclusa la documentazione, inviare le proprie idee, consigli e prospettive a customerkeyfeedback@microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="9ed6d-123">To provide feedback on Customer Key, including the documentation, send your ideas, suggestions and perspectives to customerkeyfeedback@microsoft.com.</span></span>
  
## <a name="overview-of-setting-up-customer-key-for-office-365"></a><span data-ttu-id="9ed6d-124">Panoramica della configurazione della chiave del cliente per Office 365</span><span class="sxs-lookup"><span data-stu-id="9ed6d-124">Overview of setting up Customer Key for Office 365</span></span>
<span data-ttu-id="9ed6d-125"><a name="Overview"> </a></span><span class="sxs-lookup"><span data-stu-id="9ed6d-125"></span></span>

<span data-ttu-id="9ed6d-p107">Per impostare la chiave del cliente, è necessario completare queste attività. Il resto di questo argomento fornisce istruzioni dettagliate per ogni attività o collegamenti a ulteriori informazioni per ogni passaggio del processo.</span><span class="sxs-lookup"><span data-stu-id="9ed6d-p107">To set up Customer Key you will complete these tasks. The rest of this topic provides detailed instructions for each task, or links out to more information for each step in the process.</span></span>
  
<span data-ttu-id="9ed6d-128">**In Azure e Microsoft FastTrack:**</span><span class="sxs-lookup"><span data-stu-id="9ed6d-128">**In Azure and Microsoft FastTrack:**</span></span>
  
<span data-ttu-id="9ed6d-p108">La maggior parte delle attività verrà completata tramite la connessione remota a Azure PowerShell. Per ottenere risultati ottimali, utilizzare la versione 4.4.0 o successiva di Azure PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9ed6d-p108">You will complete most of these tasks by remotely connecting to Azure PowerShell. For best results, use version 4.4.0 or later of Azure PowerShell.</span></span>
  
- [<span data-ttu-id="9ed6d-131">Creare due nuove sottoscrizioni di Azure</span><span class="sxs-lookup"><span data-stu-id="9ed6d-131">Create two new Azure subscriptions</span></span>](controlling-your-data-using-customer-key.md#Create2newsubs)
    
- [<span data-ttu-id="9ed6d-132">Registrare le sottoscrizioni di Azure per l'utilizzo di un periodo di conservazione obbligatorio</span><span class="sxs-lookup"><span data-stu-id="9ed6d-132">Register Azure subscriptions to use a mandatory retention period</span></span>](controlling-your-data-using-customer-key.md#RegisterSubsforMRP)
    
    <span data-ttu-id="9ed6d-133">La registrazione può richiedere da uno a cinque giorni lavorativi.</span><span class="sxs-lookup"><span data-stu-id="9ed6d-133">Registration can take from one to five business days.</span></span>
    
- [<span data-ttu-id="9ed6d-134">Inviare una richiesta per attivare la chiave del cliente per Office 365</span><span class="sxs-lookup"><span data-stu-id="9ed6d-134">Submit a request to activate Customer Key for Office 365</span></span>](controlling-your-data-using-customer-key.md#FastTrack)
    
    <span data-ttu-id="9ed6d-p109">Dopo aver creato le due nuove sottoscrizioni di Azure, è necessario inviare la richiesta di offerta chiave del cliente completando un modulo Web ospitato nel portale di Microsoft FastTrack. **Il team di FastTrack non fornisce assistenza per la chiave del cliente. Office utilizza semplicemente il portale FastTrack per consentire all'utente di inviare il modulo e di aiutarci a tenere conto delle offerte rilevanti per la chiave del cliente**.</span><span class="sxs-lookup"><span data-stu-id="9ed6d-p109">Once you've created the two new Azure subscriptions, you'll need to submit the appropriate Customer Key offer request by completing a web form that is hosted in the Microsoft FastTrack portal. **The FastTrack team doesn't provide assistance with Customer Key. Office simply uses the FastTrack portal to allow you to submit the form and to help us track the relevant offers for Customer Key**.</span></span>
  
<span data-ttu-id="9ed6d-p110">Dopo aver inoltrato un'offerta per la chiave del cliente, Microsoft esamina la richiesta e notifica quando è possibile procedere con le altre attività di installazione. Questo processo può richiedere fino a cinque giorni lavorativi.</span><span class="sxs-lookup"><span data-stu-id="9ed6d-p110">Once you have submitted a Customer Key offer, Microsoft reviews your request and notifies you when you can proceed with the rest of the setup tasks. This process can take up to five business days.</span></span>
    
- [<span data-ttu-id="9ed6d-139">Creare un Vault Key Azure Premium in ogni sottoscrizione</span><span class="sxs-lookup"><span data-stu-id="9ed6d-139">Create a premium Azure Key Vault in each subscription</span></span>](controlling-your-data-using-customer-key.md#CreateKeyVault)
    
- [<span data-ttu-id="9ed6d-140">Assegnare le autorizzazioni per ogni Vault chiave</span><span class="sxs-lookup"><span data-stu-id="9ed6d-140">Assign permissions to each key vault</span></span>](controlling-your-data-using-customer-key.md#KeyVaultPerms)
    
- [<span data-ttu-id="9ed6d-141">Abilitare e quindi confermare l'eliminazione morbida sui Vault delle chiavi</span><span class="sxs-lookup"><span data-stu-id="9ed6d-141">Enable and then confirm soft delete on your key vaults</span></span>](controlling-your-data-using-customer-key.md#SoftDelete)
    
- [<span data-ttu-id="9ed6d-142">Aggiungere una chiave a ogni Vault chiave creando o importando una chiave</span><span class="sxs-lookup"><span data-stu-id="9ed6d-142">Add a key to each key vault either by creating or importing a key</span></span>](controlling-your-data-using-customer-key.md#AddKeystoKeyVault)
    
- [<span data-ttu-id="9ed6d-143">Controllare il livello di ripristino delle chiavi</span><span class="sxs-lookup"><span data-stu-id="9ed6d-143">Check the recovery level of your keys</span></span>](controlling-your-data-using-customer-key.md#CheckKeyRecoveryLevel)
    
- [<span data-ttu-id="9ed6d-144">Backup della chiave del Vault di Azure</span><span class="sxs-lookup"><span data-stu-id="9ed6d-144">Backup Azure Key Vault</span></span>](controlling-your-data-using-customer-key.md#BackupAzureKeyVaultkeys)
    
- [<span data-ttu-id="9ed6d-145">ConValidare le impostazioni di configurazione di Azure Key Vault</span><span class="sxs-lookup"><span data-stu-id="9ed6d-145">Validate Azure Key Vault configuration settings</span></span>](controlling-your-data-using-customer-key.md#Validateconfiguration)
    
- [<span data-ttu-id="9ed6d-146">Ottenere l'URI per ogni chiave del Vault Key di Azure</span><span class="sxs-lookup"><span data-stu-id="9ed6d-146">Obtain the URI for each Azure Key Vault key</span></span>](controlling-your-data-using-customer-key.md#GetKeyURI)
    
<span data-ttu-id="9ed6d-147">**In Office 365:**</span><span class="sxs-lookup"><span data-stu-id="9ed6d-147">**In Office 365:**</span></span>
  
<span data-ttu-id="9ed6d-148">Exchange Online e Skype for business:</span><span class="sxs-lookup"><span data-stu-id="9ed6d-148">Exchange Online and Skype for Business:</span></span>
  
- [<span data-ttu-id="9ed6d-149">Creare un criterio di crittografia dei dati per l'utilizzo con Exchange Online e Skype for business</span><span class="sxs-lookup"><span data-stu-id="9ed6d-149">Create a data encryption policy (DEP) for use with Exchange Online and Skype for Business</span></span>](controlling-your-data-using-customer-key.md#CreateDEP4EXOSkype)
    
- [<span data-ttu-id="9ed6d-150">Assegnare una DEP a una cassetta postale</span><span class="sxs-lookup"><span data-stu-id="9ed6d-150">Assign a DEP to a mailbox</span></span>](controlling-your-data-using-customer-key.md#assignDEPtomailbox)
    
- [<span data-ttu-id="9ed6d-151">ConValidare la crittografia della cassetta postale</span><span class="sxs-lookup"><span data-stu-id="9ed6d-151">Validate mailbox encryption</span></span>](controlling-your-data-using-customer-key.md#validatemailboxencryption)
    
<span data-ttu-id="9ed6d-152">SharePoint Online e OneDrive for business:</span><span class="sxs-lookup"><span data-stu-id="9ed6d-152">SharePoint Online and OneDrive for Business:</span></span>
  
- [<span data-ttu-id="9ed6d-153">Creare un criterio di crittografia dei dati per ogni geo di SharePoint Online e OneDrive for business</span><span class="sxs-lookup"><span data-stu-id="9ed6d-153">Create a data encryption policy (DEP) for each SharePoint Online and OneDrive for Business geo</span></span>](controlling-your-data-using-customer-key.md#CreateDEP4SPOODfB)
    
- [<span data-ttu-id="9ed6d-154">ConValidare la crittografia di siti di gruppo, siti del team e OneDrive for business</span><span class="sxs-lookup"><span data-stu-id="9ed6d-154">Validate encryption of Group Sites, Team Sites, and OneDrive for Business</span></span>](controlling-your-data-using-customer-key.md#validateencryptionSPO)
    
## <a name="complete-tasks-in-azure-key-vault-and-microsoft-fasttrack-for-customer-key"></a><span data-ttu-id="9ed6d-155">Completare le attività in Azure Key Vault e Microsoft FastTrack per la chiave del cliente</span><span class="sxs-lookup"><span data-stu-id="9ed6d-155">Complete tasks in Azure Key Vault and Microsoft FastTrack for Customer Key</span></span>
<span data-ttu-id="9ed6d-156"><a name="AzureSteps"> </a></span><span class="sxs-lookup"><span data-stu-id="9ed6d-156"></span></span>

<span data-ttu-id="9ed6d-p111">Completare queste attività in Azure Key Vault per impostare la chiave del cliente per Office 365. Sarà necessario completare questi passaggi, indipendentemente dal fatto che si desideri configurare la chiave del cliente per Exchange Online e Skype for business o SharePoint Online e OneDrive for business o per tutti i servizi supportati in Office 365.</span><span class="sxs-lookup"><span data-stu-id="9ed6d-p111">Complete these tasks in Azure Key Vault in order to set up Customer Key for Office 365. You will need to complete these steps regardless of whether you intend to set up Customer Key for Exchange Online and Skype for Business or SharePoint Online and OneDrive for Business or for all supported services in Office 365.</span></span>
  
### <a name="create-two-new-azure-subscriptions"></a><span data-ttu-id="9ed6d-159">Creare due nuove sottoscrizioni di Azure</span><span class="sxs-lookup"><span data-stu-id="9ed6d-159">Create two new Azure subscriptions</span></span>
<span data-ttu-id="9ed6d-160"><a name="Create2newsubs"> </a></span><span class="sxs-lookup"><span data-stu-id="9ed6d-160"></span></span>

<span data-ttu-id="9ed6d-p112">Per la chiave del cliente sono necessarie due sottoscrizioni di Azure. Come procedura consigliata, Microsoft consiglia di creare nuove sottoscrizioni di Azure per l'utilizzo con la chiave del cliente. Le chiavi del Vault Key di Azure possono essere autorizzate solo per le applicazioni nello stesso tenant di Azure Active Directory (AAD), è necessario creare le nuove sottoscrizioni usando lo stesso tenant di Azure AD utilizzato con l'organizzazione di Office 365 in cui verrà assegnato il DEPs. Ad esempio, utilizzando l'account aziendale o dell'Istituto di istruzione con privilegi di amministratore globale nell'organizzazione di Office 365. Per la procedura dettagliata, vedere [iscriversi a Azure come organizzazione](https://azure.microsoft.com/en-us/documentation/articles/sign-up-organization/).</span><span class="sxs-lookup"><span data-stu-id="9ed6d-p112">Two Azure subscriptions are required for Customer Key. As a best practice, Microsoft recommends that you create new Azure subscriptions for use with Customer Key. Azure Key Vault keys can only be authorized for applications in the same Azure Active Directory (AAD) tenant, you must create the new subscriptions using the same Azure AD tenant used with your Office 365 organization where the DEPs will be assigned. For example, using your work or school account that has global administrator privileges in your Office 365 organization. For detailed steps, see [Sign up for Azure as an organization](https://azure.microsoft.com/en-us/documentation/articles/sign-up-organization/).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="9ed6d-p113">La chiave del cliente richiede due chiavi per ogni criterio di crittografia dei dati. Per ottenere questo risultato, è necessario creare due sottoscrizioni di Azure. Come procedura consigliata, Microsoft consiglia di disporre di membri distinti dell'organizzazione che configurano una chiave in ogni sottoscrizione. Inoltre, queste sottoscrizioni di Azure devono essere utilizzate solo per amministrare le chiavi di crittografia per Office 365. Questo consente di proteggere l'organizzazione nel caso in cui uno degli operatori involontariamente, intenzionalmente o elimini in modo doloso o meno le chiavi per le quali sono responsabili.</span><span class="sxs-lookup"><span data-stu-id="9ed6d-p113">Customer Key requires two keys for each data encryption policy (DEP). In order to achieve this, you must create two Azure subscriptions. As a best practice, Microsoft recommends that you have separate members of your organization configure one key in each subscription. In addition, these Azure subscriptions should only be used to administer encryption keys for Office 365. This protects your organization in case one of your operators accidentally, intentionally, or maliciously deletes or otherwise mismanages the keys for which they are responsible. </span></span><br/> <span data-ttu-id="9ed6d-p114">È consigliabile impostare nuove sottoscrizioni di Azure che vengono utilizzate solo per la gestione delle risorse del Vault Key di Azure per l'utilizzo con la chiave del cliente. Non esiste alcun limite pratico per il numero di sottoscrizioni di Azure che è possibile creare per l'organizzazione. Seguendo queste procedure consigliate si minimizza l'impatto dell'errore umano contribuendo a gestire le risorse utilizzate dalla chiave del cliente.</span><span class="sxs-lookup"><span data-stu-id="9ed6d-p114">We recommend that you set up new Azure subscriptions that are solely used for managing Azure Key Vault resources for use with Customer Key. There is no practical limit to the number of Azure subscriptions that you can create for your organization. Following these best practices will minimize the impact of human error while helping to manage the resources used by Customer Key.</span></span> 
  
### <a name="submit-a-request-to-activate-customer-key-for-office-365"></a><span data-ttu-id="9ed6d-174">Inviare una richiesta per attivare la chiave del cliente per Office 365</span><span class="sxs-lookup"><span data-stu-id="9ed6d-174">Submit a request to activate Customer Key for Office 365</span></span>
<span data-ttu-id="9ed6d-175"><a name="FastTrack"> </a></span><span class="sxs-lookup"><span data-stu-id="9ed6d-175"></span></span>

<span data-ttu-id="9ed6d-p115">Dopo aver completato i passaggi di Azure, è necessario inviare una richiesta di offerta nel [portale Microsoft FastTrack](https://fasttrack.microsoft.com/). Dopo aver inoltrato una richiesta tramite il portale Web di FastTrack, Microsoft verifica i dati di configurazione del Vault Key di Azure e le informazioni di contatto fornite. Le selezioni che vengono apportate nel modulo di offerta per quanto riguarda i funzionari autorizzati dell'organizzazione sono critiche e necessarie per il completamento della registrazione a chiave del cliente. Gli agenti dell'organizzazione selezionati nel modulo saranno utilizzati per garantire l'autenticità di qualsiasi richiesta di revocare e distruggere tutte le chiavi utilizzate con un criterio di crittografia dei dati chiave del cliente. È necessario eseguire questo passaggio una volta per attivare il codice "Customer Key" per Exchange Online e Skype for business e una seconda volta per attivare la chiave del cliente per SharePoint Online e OneDrive for business.</span><span class="sxs-lookup"><span data-stu-id="9ed6d-p115">Once you've completed the Azure steps, you'll need to submit an offer request in the [Microsoft FastTrack portal](https://fasttrack.microsoft.com/). Once you have submitted a request through the FastTrack web portal, Microsoft verifies the Azure Key Vault configuration data and contact information you provided. The selections that you make in the offer form regarding the authorized officers of your organization is critical and necessary for completion of Customer Key registration. The officers of your organization that you select in the form will be the used to ensure the authenticity of any request to revoke and destroy all keys used with a Customer Key data encryption policy. You'll need to do this step once to activate Customer Key for Exchange Online and Skype for Business coverage and a second time to activate Customer Key for SharePoint Online and OneDrive for Business.</span></span>
  
<span data-ttu-id="9ed6d-181">Per inviare un'offerta per attivare il codice "Customer Key", eseguire la procedura seguente:</span><span class="sxs-lookup"><span data-stu-id="9ed6d-181">To submit an offer to activate Customer Key, complete these steps:</span></span>
  
1. <span data-ttu-id="9ed6d-182">L'utilizzo di un account aziendale o dell'Istituto di istruzione con autorizzazioni di amministratore globale nell'organizzazione di Office 365, accedere al [portale di Microsoft FastTrack](https://fasttrack.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="9ed6d-182">Using a work or school account that has global administrator permissions in your Office 365 organization, log in to the [Microsoft FastTrack portal](https://fasttrack.microsoft.com/).</span></span>
    
2. <span data-ttu-id="9ed6d-183">Dopo aver effettuato l'accesso, passare al **Dashboard**.</span><span class="sxs-lookup"><span data-stu-id="9ed6d-183">Once you're logged in, browse to the **Dashboard**.</span></span>
    
3. <span data-ttu-id="9ed6d-184">Scegliere **offerte**ed esaminare l'elenco delle offerte correnti.</span><span class="sxs-lookup"><span data-stu-id="9ed6d-184">Choose **Offers**, and review the list of current offers.</span></span>
    
4. <span data-ttu-id="9ed6d-185">Scegliere **ulteriori informazioni** per l'offerta che si applica all'utente:</span><span class="sxs-lookup"><span data-stu-id="9ed6d-185">Choose **Learn More** for the offer that applies to you:</span></span> 
    
  - <span data-ttu-id="9ed6d-186">**Exchange Online e Skype for business:** Scegliere **ulteriori informazioni** sulla **chiave del cliente per l'offerta di Exchange** .</span><span class="sxs-lookup"><span data-stu-id="9ed6d-186">**Exchange Online and Skype for Business:** Choose **Learn More** on the **Customer Key for Exchange** offer.</span></span> 
    
  - <span data-ttu-id="9ed6d-187">**SharePoint Online e OneDrive for business:** Scegliere **ulteriori informazioni** sulla chiave del cliente per l'offerta di **SharePoint e OneDrive for business** .</span><span class="sxs-lookup"><span data-stu-id="9ed6d-187">**SharePoint Online and OneDrive for Business:** Chose **Learn More** on the **Customer Key for SharePoint and OneDrive for Business** offer.</span></span> 
    
5. <span data-ttu-id="9ed6d-188">Nella pagina **Dettagli offerta** scegliere **Crea richiesta**.</span><span class="sxs-lookup"><span data-stu-id="9ed6d-188">On the **Offer details** page, choose **Create Request**.</span></span>
    
6. <span data-ttu-id="9ed6d-p116">Compilare tutti i dettagli applicabili e le informazioni richieste nel modulo di offerta. Prestare particolare attenzione alle selezioni per i funzionari dell'organizzazione che si desidera autorizzare ad approvare la distruzione permanente e irreversibile delle chiavi di crittografia e dei dati. Dopo aver completato il modulo, scegliere **Submit**.</span><span class="sxs-lookup"><span data-stu-id="9ed6d-p116">Fill out all applicable details and requested information on the offer form. Pay particular attention to your selections for which officers of your organization you want to authorize to approve the permanent and irreversible destruction of encryption keys and data. Once you've completed the form, choose **Submit**.</span></span>
    
    <span data-ttu-id="9ed6d-192">Questo processo può richiedere fino a cinque giorni lavorativi una volta che Microsoft è stato informato della richiesta.</span><span class="sxs-lookup"><span data-stu-id="9ed6d-192">This process can take up to five business days once Microsoft has been notified of your request.</span></span>
    
7. <span data-ttu-id="9ed6d-193">Passare alla sezione periodo di conservazione obbligatoria seguente.</span><span class="sxs-lookup"><span data-stu-id="9ed6d-193">Continue on to the mandatory retention period section below.</span></span>
    
### <a name="register-azure-subscriptions-to-use-a-mandatory-retention-period"></a><span data-ttu-id="9ed6d-194">Registrare le sottoscrizioni di Azure per l'utilizzo di un periodo di conservazione obbligatorio</span><span class="sxs-lookup"><span data-stu-id="9ed6d-194">Register Azure subscriptions to use a mandatory retention period</span></span>
<span data-ttu-id="9ed6d-195"><a name="RegisterSubsforMRP"> </a></span><span class="sxs-lookup"><span data-stu-id="9ed6d-195"></span></span>

<span data-ttu-id="9ed6d-p117">La perdita temporanea o permanente delle chiavi di crittografia radice può essere molto dirompente o addirittura catastrofica per l'utilizzo del servizio e può causare una perdita di dati. Per questo motivo, le risorse utilizzate con la chiave del cliente richiedono una protezione sicura. Tutte le risorse di Azure utilizzate con la chiave del cliente offrono meccanismi di protezione oltre la configurazione predefinita. Le sottoscrizioni di Azure possono essere contrassegnate o registrate in un modo che impedirà l'annullamento immediato e irrevocabile. Si tratta della registrazione di un periodo di conservazione obbligatorio. I passaggi necessari per registrare le sottoscrizioni di Azure per un periodo di conservazione obbligatorio richiedono la collaborazione con il team di Office 365. Questo processo può richiedere da uno a cinque giorni lavorativi. In precedenza, questo è stato talvolta definito come "non annullare".</span><span class="sxs-lookup"><span data-stu-id="9ed6d-p117">The temporary or permanent loss of root encryption keys can be very disruptive or even catastrophic to service operation and can result in data loss. For this reason, the resources used with Customer Key require strong protection. All the Azure resources that are used with Customer Key offer protection mechanisms beyond the default configuration. Azure subscriptions can be tagged or registered in a way that will prevent immediate and irrevocable cancellation. This is referred to as registering for a mandatory retention period. The steps required to register Azure subscriptions for a mandatory retention period require collaboration with the Office 365 team. This process can take from one to five business days. Previously, this was sometimes referred to as "Do Not Cancel".</span></span>
  
<span data-ttu-id="9ed6d-204">Prima di contattare il team di Office 365, è necessario eseguire i passaggi seguenti per ogni sottoscrizione di Azure utilizzata con la chiave Customer:</span><span class="sxs-lookup"><span data-stu-id="9ed6d-204">Before contacting the Office 365 team, you must perform the following steps for each Azure subscription that you use with Customer Key:</span></span>
  
1. <span data-ttu-id="9ed6d-p118">Accedere alla sottoscrizione di Azure con Azure PowerShell. Per istruzioni, vedere [accedere con Azure PowerShell](https://docs.microsoft.com/powershell/azure/authenticate-azureps?view=azurermps-4.3.1).</span><span class="sxs-lookup"><span data-stu-id="9ed6d-p118">Log in to your Azure subscription with Azure PowerShell. For instructions, see [Log in with Azure PowerShell](https://docs.microsoft.com/powershell/azure/authenticate-azureps?view=azurermps-4.3.1).</span></span>
    
2. <span data-ttu-id="9ed6d-207">Eseguire il cmdlet Register-AzureRmProviderFeature per registrare gli abbonamenti per l'utilizzo di un periodo di conservazione obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="9ed6d-207">Run the Register-AzureRmProviderFeature cmdlet to register your subscriptions to use a mandatory retention period.</span></span>
    
  ```
  Register-AzureRmProviderFeature -FeatureName mandatoryRetentionPeriodEnabled -ProviderNamespace Microsoft.Resources
  ```

3. <span data-ttu-id="9ed6d-p119">Contattare Microsoft per eseguire il processo di completamento. Per il team di SharePoint e OneDrive for business, contattare [Spock@microsoft.com](mailto:spock@microsoft.com). Per Exchange Online e Skype for business, contattare [exock@microsoft.com](mailto:exock@microsoft.com). Il contratto di servizio per il completamento di questo processo è di cinque giorni lavorativi una volta che Microsoft è stato informato (e verificato) di aver registrato gli abbonamenti per l'utilizzo di un periodo di conservazione obbligatorio. Includere quanto segue nel messaggio di posta elettronica:</span><span class="sxs-lookup"><span data-stu-id="9ed6d-p119">Contact Microsoft to have the process finalized. For the SharePoint and OneDrive for Business team, contact [spock@microsoft.com](mailto:spock@microsoft.com). For Exchange Online and Skype for Business, contact [exock@microsoft.com](mailto:exock@microsoft.com). The Service Level Agreement (SLA) for completion of this process is five business days once Microsoft has been notified (and verified) that you have registered your subscriptions to use a mandatory retention period. Include the following in your email:</span></span>
    
    <span data-ttu-id="9ed6d-213">**Oggetto**: chiave del cliente \<per *il nome di dominio* completo del tenant\></span><span class="sxs-lookup"><span data-stu-id="9ed6d-213">**Subject**: Customer Key for \<*Your tenant's fully-qualified domain name*\></span></span> 
    
    <span data-ttu-id="9ed6d-214">**Corpo**: ID di sottoscrizione per i quali si desidera che il periodo di conservazione obbligatorio sia stato completato.</span><span class="sxs-lookup"><span data-stu-id="9ed6d-214">**Body**: Subscription IDs for which you want to have the mandatory retention period finalized.</span></span> 
    
4. <span data-ttu-id="9ed6d-215">Dopo aver ricevuto la notifica da Microsoft che la registrazione è stata completata, verificare lo stato della registrazione eseguendo il cmdlet Get-AzureRmProviderFeature come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="9ed6d-215">Once you receive notification from Microsoft that registration is complete, verify the status of your registration by running the Get-AzureRmProviderFeature cmdlet as follows:</span></span>
    
  ```
  Get-AzureRmProviderFeature -ProviderNamespace Microsoft.Resources -FeatureName mandatoryRetentionPeriodEnabled
  ```

5. <span data-ttu-id="9ed6d-216">Dopo aver verificato che la proprietà **state registrazione** del cmdlet Get-AzureRmProviderFeature restituisca il valore **registrato**, eseguire il comando seguente per completare il processo:</span><span class="sxs-lookup"><span data-stu-id="9ed6d-216">After verifying that the **Registration State** property from the Get-AzureRmProviderFeature cmdlet returns a value of **Registered**, run the following command to complete the process:</span></span>
    
  ```
  Register-AzureRmResourceProvider -ProviderNamespace "Microsoft.KeyVault"
  ```

### <a name="create-a-premium-azure-key-vault-in-each-subscription"></a><span data-ttu-id="9ed6d-217">Creare un Vault Key Azure Premium in ogni sottoscrizione</span><span class="sxs-lookup"><span data-stu-id="9ed6d-217">Create a premium Azure Key Vault in each subscription</span></span>
<span data-ttu-id="9ed6d-218"><a name="CreateKeyVault"> </a></span><span class="sxs-lookup"><span data-stu-id="9ed6d-218"></span></span>

<span data-ttu-id="9ed6d-219">La procedura per creare un Vault chiave è documentata per [iniziare con Azure Key Vault](https://azure.microsoft.com/documentation/articles/key-vault-get-started/), che guida l'utente attraverso l'installazione e l'avvio di Azure PowerShell, la connessione alla sottoscrizione di Azure, la creazione di un gruppo di risorse e la creazione di un Vault chiave in tale gruppo di risorse.</span><span class="sxs-lookup"><span data-stu-id="9ed6d-219">The steps to create a key vault are documented in [Getting Started with Azure Key Vault](https://azure.microsoft.com/documentation/articles/key-vault-get-started/), which guides you through installing and launching Azure PowerShell, connecting to your Azure subscription, creating a resource group, and creating a key vault in that resource group.</span></span>
  
<span data-ttu-id="9ed6d-p120">Quando si crea un Vault chiave, è necessario scegliere un SKU: standard o Premium. La SKU standard consente di proteggere i tasti del Vault Key di Azure con il software: non vi è alcuna protezione della chiave HSM (hardware Security Module) e la SKU Premium consente l'utilizzo di HSM per la protezione delle chiavi del Vault Key. La chiave Customer accetta i Vault chiave che utilizzano SKU, anche se Microsoft consiglia vivamente di utilizzare solo la SKU Premium. Il costo delle operazioni con chiavi di entrambi i tipi è lo stesso, quindi l'unica differenza di costo è il costo al mese per ogni chiave protetta da HSM. Per informazioni dettagliate, vedere [Key Vault pricing](https://azure.microsoft.com/pricing/details/key-vault/) .</span><span class="sxs-lookup"><span data-stu-id="9ed6d-p120">When you create a key vault, you must choose a SKU: either Standard or Premium. The Standard SKU allows Azure Key Vault keys to be protected with software - there is no Hardware Security Module (HSM) key protection - and the Premium SKU allows the use of HSMs for protection of Key Vault keys. Customer Key accepts key vaults that use either SKU, though Microsoft strongly recommends that you use only the Premium SKU. The cost of operations with keys of either type is the same, so the only difference in cost is the cost per month for each HSM-protected key. See [Key Vault pricing](https://azure.microsoft.com/pricing/details/key-vault/) for details.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="9ed6d-225">Utilizzare i Vault chiave SKU Premium e le chiavi con protezione HSM per i dati di produzione e utilizzare solo i Vault e le chiavi standard SKU per il testing e la convalida.</span><span class="sxs-lookup"><span data-stu-id="9ed6d-225">Use the Premium SKU key vaults and HSM-protected keys for production data, and only use Standard SKU key vaults and keys for testing and validation purposes.</span></span> 
  
<span data-ttu-id="9ed6d-p121">Per ogni servizio di Office 365 con cui si utilizzerà la chiave del cliente, creare un Vault Key in ognuna delle due sottoscrizioni di Azure create. Ad esempio, per Exchange Online e Skype for business solo o SharePoint Online e OneDrive for business, si creerà solo una coppia di volte. Per abilitare la chiave del cliente per Exchange Online e SharePoint Online, è possibile creare due coppie di volte chiave.</span><span class="sxs-lookup"><span data-stu-id="9ed6d-p121">For each Office 365 service with which you will use Customer Key, create a key vault in each of the two Azure subscriptions that you created. For example, for Exchange Online and Skype for Business only or SharePoint Online and OneDrive for Business only, you will create only one pair of vaults. To enable Customer Key for both Exchange Online and SharePoint Online, you will create two pairs of key vaults.</span></span>
  
<span data-ttu-id="9ed6d-p122">Utilizzare una convenzione di denominazione per i Vault chiave che riflette l'utilizzo previsto della funzionalità di protezione dei nomi con cui verranno associati i Vault. Vedere la sezione procedure consigliate di seguito per la denominazione dei consigli convenzioni.</span><span class="sxs-lookup"><span data-stu-id="9ed6d-p122">Use a naming convention for key vaults that reflects the intended use of the DEP with which you will associate the vaults. See the Best Practices section below for naming convention recommendations.</span></span>
  
<span data-ttu-id="9ed6d-p123">Creare un set di volte separato e abbinato per ogni criterio di crittografia dei dati. Per Exchange Online, l'ambito di un criterio di crittografia dei dati viene scelto dall'utente quando si assegna il criterio alla cassetta postale. Una cassetta postale può avere un solo criterio assegnato ed è possibile creare fino a 50 criteri. Per SharePoint Online l'ambito di un criterio è costituito da tutti i dati all'interno di un'organizzazione in una posizione geografica o Geo.</span><span class="sxs-lookup"><span data-stu-id="9ed6d-p123">Create a separate, paired set of vaults for each data encryption policy. For Exchange Online, the scope of a data encryption policy is chosen by you when you assign the policy to mailbox. A mailbox can have only one policy assigned, and you can create up to fifty policies. For SharePoint Online the scope of a policy is all of the data within an organization in a geographic location, or geo.</span></span>
  
<span data-ttu-id="9ed6d-p124">La creazione di Vault chiave richiede anche la creazione di gruppi di risorse di Azure, poiché è necessario che la capacità di archiviazione (anche se molto piccola) e la registrazione Key Vault, se abilitata, generano anche dati archiviati. Come procedura consigliata, Microsoft consiglia di utilizzare amministratori distinti per gestire ogni gruppo di risorse, con l'amministrazione allineata al set di amministratori che gestirà tutte le risorse chiave dei clienti correlate.</span><span class="sxs-lookup"><span data-stu-id="9ed6d-p124">The creation of key vaults also requires the creation of Azure resource groups, since key vaults need storage capacity (though very small) and Key Vault logging, if enabled, also generates stored data. As a best practice Microsoft recommends using separate administrators to manage each resource group, with the administration aligned with the set of administrators that will manage all related Customer Key resources.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="9ed6d-p125">Per massimizzare la disponibilità, i Vault delle chiavi devono trovarsi nelle aree geografiche vicino al servizio Office 365. Ad esempio, se l'organizzazione di Exchange Online è in Nord America, inserire i Vault chiave in Nord America. Se l'organizzazione di Exchange Online è in Europa, inserire i Vault chiave in Europa.</span><span class="sxs-lookup"><span data-stu-id="9ed6d-p125">To maximize availability, your key vaults should be in regions close to your Office 365 service. For example, if your Exchange Online organization is in North America, place your key vaults in North America. If your Exchange Online organization is in Europe, place your key vaults in Europe.</span></span><br/><span data-ttu-id="9ed6d-p126">Utilizzare un prefisso comune per i Vault chiave e includere un'abbreviazione dell'utilizzo e dell'ambito del Vault Key e delle chiavi (ad esempio, per il servizio contoso SharePoint in cui si trovano i Vault in Nord America, una possibile coppia di nomi è contoso-O365SP-NA-VaultA1 e Contoso-O365SP-NA-VaultA2. Il nome del Vault è una stringa univoca globale all'interno di Azure, quindi potrebbe essere necessario provare varianti dei nomi desiderati, nel caso in cui i nomi desiderati siano già stati rivendicati da altri clienti di Azure. A luglio 2017 non è possibile modificare i nomi dei Vault, quindi è consigliabile disporre di un piano scritto per il programma di installazione e utilizzare una seconda persona per verificare che il piano sia stato eseguito correttamente.</span><span class="sxs-lookup"><span data-stu-id="9ed6d-p126">Use a common prefix for key vaults, and include an abbreviation of the use and scope of the key vault and keys (e.g., for the Contoso SharePoint service where the vaults will be located in North America, a possible pair of names is Contoso-O365SP-NA-VaultA1 and Contoso-O365SP-NA-VaultA2. Vault names are globally unique strings within Azure, so you may need to try variations of your desired names in case the desired names are already claimed by other Azure customers. As of July 2017 vault names cannot be changed, so a best practice is to have a written plan for setup and use a second person to verify the plan is executed correctly.</span></span><br/><span data-ttu-id="9ed6d-p127">Se possibile, creare i Vault in aree non accoppiate. Le aree di Azure con accoppiamento offrono disponibilità elevata tra i domini di errore del servizio. Di conseguenza, le coppie regionali possono essere pensate come area di backup dell'altro. Questo significa che una risorsa di Azure inserita in un'area geografica acquisisce automaticamente la tolleranza di errore tramite l'area associata. Per questo motivo, la scelta delle aree geografiche per due volte utilizzate in una DEP in cui le aree sono abbinate significa che sono in uso solo un totale di due aree di disponibilità. La maggior parte delle geografie ha solo due aree geografiche, quindi non è ancora possibile selezionare le aree non accoppiate. Se possibile, scegliere due aree non associate per i due Vault utilizzati con una funzionalità di protezione esecuzione programmi. Questo beneficia di un totale di quattro aree di disponibilità. Per ulteriori informazioni, vedere [Business Continuity and Disaster Recovery (BCdR): aree con accoppiamento di Azure](https://docs.microsoft.com/azure/best-practices-availability-paired-regions) per un elenco corrente di coppie regionali.</span><span class="sxs-lookup"><span data-stu-id="9ed6d-p127">If possible, create your vaults in non-paired regions. Paired Azure regions provide high availability across service failure domains. Therefore, regional pairs can be thought of as each other's backup region. This means that an Azure resource that is placed in one region is automatically gaining fault tolerance through the paired region. For this reason, choosing regions for two vaults used in a DEP where the regions are paired means that only a total of two regions of availability are in use. Most geographies only have two regions, so it's not yet possible to select non-paired regions. If possible, choose two non-paired regions for the two vaults used with a DEP. This benefits from a total of four regions of availability. For more information, see [Business continuity and disaster recovery (BCDR): Azure Paired Regions](https://docs.microsoft.com/azure/best-practices-availability-paired-regions) for a current list of regional pairs.</span></span> 
  
### <a name="assign-permissions-to-each-key-vault"></a><span data-ttu-id="9ed6d-252">Assegnare le autorizzazioni per ogni Vault chiave</span><span class="sxs-lookup"><span data-stu-id="9ed6d-252">Assign permissions to each key vault</span></span>
<span data-ttu-id="9ed6d-253"><a name="KeyVaultPerms"> </a></span><span class="sxs-lookup"><span data-stu-id="9ed6d-253"></span></span>

<span data-ttu-id="9ed6d-p128">Per ogni Vault chiave, sarà necessario definire tre Set distinti di autorizzazioni per la chiave del cliente, a seconda dell'implementazione. Ad esempio, sarà necessario definire un set di autorizzazioni per ognuno dei seguenti elementi:</span><span class="sxs-lookup"><span data-stu-id="9ed6d-p128">For each key vault, you will need to define three separate sets of permissions for Customer Key, depending on your implementation. For example, you will need to define one set of permissions for each of the following:</span></span>
  
- <span data-ttu-id="9ed6d-p129">**Amministratori chiave del Vault** che eseguono la gestione quotidiana del Vault Key per l'organizzazione. Tali attività includono backup, creazione, recupero, importazione, elenco e ripristino.</span><span class="sxs-lookup"><span data-stu-id="9ed6d-p129">**Key vault administrators** that will perform day-to-day management of your key vault for your organization. These tasks include backup, create, get, import, list, and restore.</span></span> 
    
    > [!IMPORTANT]
    > <span data-ttu-id="9ed6d-p130">Il set di autorizzazioni assegnate agli amministratori delle chiavi del Vault non include l'autorizzazione per l'eliminazione delle chiavi. Si tratta di una prassi intenzionale e importante. L'eliminazione delle chiavi di crittografia non è in genere completata, poiché tale operazione distrugge definitivamente i dati. Come procedura consigliata, non concedere questa autorizzazione agli amministratori delle chiavi del Vault per impostazione predefinita. Al contrario, è necessario riservare questo elemento ai collaboratori del Vault Key e assegnarlo solo a un amministratore a breve termine dopo aver compreso la comprensione delle conseguenze.</span><span class="sxs-lookup"><span data-stu-id="9ed6d-p130">The set of permissions assigned to key vault administrators does not include the permission to delete keys. This is intentional and an important practice. Deleting encryption keys is not typically done, since doing so permanently destroys data. As a best practice, do not grant this permission to key vault administrators by default. Instead, reserve this for key vault contributors and only assign it to an administrator on a short term basis once a clear understanding of the consequences is understood.</span></span> 
  
    <span data-ttu-id="9ed6d-p131">Per assegnare queste autorizzazioni a un utente nell'organizzazione di Office 365, eseguire l'accesso alla sottoscrizione di Azure con Azure PowerShell. Per istruzioni, vedere [accedere con Azure PowerShell](https://docs.microsoft.com/powershell/azure/authenticate-azureps?view=azurermps-4.3.1).</span><span class="sxs-lookup"><span data-stu-id="9ed6d-p131">To assign these permissions to a user in your Office 365 organization, log in to your Azure subscription with Azure PowerShell. For instructions, see [Log in with Azure PowerShell](https://docs.microsoft.com/powershell/azure/authenticate-azureps?view=azurermps-4.3.1).</span></span>
    
- <span data-ttu-id="9ed6d-265">Eseguire il cmdlet Set-AzureRmKeyVaultAccessPolicy per assegnare le autorizzazioni necessarie.</span><span class="sxs-lookup"><span data-stu-id="9ed6d-265">Run the Set-AzureRmKeyVaultAccessPolicy cmdlet to assign the necessary permissions.</span></span>
    
  ```
  Set-AzureRmKeyVaultAccessPolicy -VaultName <vaultname> 
  -UserPrincipalName <UPN of user> -PermissionsToKeys create,import,list,get,backup,restore
  ```

  <span data-ttu-id="9ed6d-266">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="9ed6d-266">For example:</span></span>
    
  ```
  Set-AzureRmKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 
  -UserPrincipalName alice@contoso.com -PermissionsToKeys create,import,list,get,backup,restore
  ```

- <span data-ttu-id="9ed6d-p132">**Key Vault Contributors** che possono modificare le autorizzazioni per il Vault Key di Azure stesso. È necessario modificare queste autorizzazioni quando i dipendenti lasciano o entrano in un team o in una situazione estremamente rara in cui gli amministratori delle Key Vault devono legittimamente disporre dell'autorizzazione per eliminare o ripristinare una chiave. Questo set di collaboratori chiave del Vault deve essere concesso al ruolo **collaboratore** nel Vault Key. È possibile assegnare questo ruolo tramite Gestione risorse di Azure. Per la procedura dettagliata, vedere [utilizzare il controllo di accesso basato sui ruoli per gestire l'accesso alle risorse di sottoscrizione di Azure](https://docs.microsoft.com/azure/active-directory/role-based-access-control-configure). L'amministratore che crea una sottoscrizione ha questo accesso in modo implicito, nonché la possibilità di assegnare altri amministratori al ruolo Collaboratore.</span><span class="sxs-lookup"><span data-stu-id="9ed6d-p132">**Key vault contributors** that can change permissions on the Azure Key Vault itself. You'll need to change these permissions as employees leave or join your team, or in the extremely rare situation that the key vault administrators legitimately need permission to delete or restore a key. This set of key vault contributors needs to be granted the **Contributor** role on your key vault. You can assign this role by using Azure Resource Manager. For detailed steps, see [Use Role-Based Access Control to manage access to your Azure subscription resources](https://docs.microsoft.com/azure/active-directory/role-based-access-control-configure). The administrator who creates a subscription has this access implicitly, as well as the ability to assign other administrators to the Contributor role.</span></span>
    
- <span data-ttu-id="9ed6d-p133">Se si intende utilizzare la chiave del cliente con Exchange Online e Skype for business, è necessario concedere l'autorizzazione a Office 365 per utilizzare il Vault Key per conto di Exchange Online e Skype for business. Analogamente, se si intende utilizzare Customer Key con SharePoint Online e OneDrive for business, è necessario aggiungere l'autorizzazione per Office 365 per utilizzare il Vault chiave per conto di SharePoint Online e OneDrive for business. Per concedere l'autorizzazione a Office 365, eseguire il cmdlet **set-AzureRmKeyVaultAccessPolicy** utilizzando la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="9ed6d-p133">If you intend to use Customer Key with Exchange Online and Skype for Business, you need to give permission to Office 365 to use the key vault on behalf of Exchange Online and Skype for Business. Likewise, if you intend to use Customer Key with SharePoint Online and OneDrive for Business, you need to add permission for the Office 365 to use the key vault on behalf of SharePoint Online and OneDrive for Business. To give permission to Office 365, run the **Set-AzureRmKeyVaultAccessPolicy** cmdlet using the following syntax:</span></span> 
    
  ```
  Set-AzureRmKeyVaultAccessPolicy -VaultName <vaultname> -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName <Office 365 appID>
  ```

    <span data-ttu-id="9ed6d-276">Dove:</span><span class="sxs-lookup"><span data-stu-id="9ed6d-276">Where:</span></span>
    
  - <span data-ttu-id="9ed6d-277">*VAULTNAME* è il nome del Vault Key creato.</span><span class="sxs-lookup"><span data-stu-id="9ed6d-277">*vaultname* is the name of the key vault you created.</span></span> 
    
  - <span data-ttu-id="9ed6d-278">Per Exchange Online e Skype for business, Sostituisci *Office 365 AppID* con`00000002-0000-0ff1-ce00-000000000000`</span><span class="sxs-lookup"><span data-stu-id="9ed6d-278">For Exchange Online and Skype for Business, replace  *Office 365 appID* with `00000002-0000-0ff1-ce00-000000000000`</span></span>
    
  - <span data-ttu-id="9ed6d-279">Per SharePoint Online e OneDrive for business, sostituire *Office 365 AppID* con`00000003-0000-0ff1-ce00-000000000000`</span><span class="sxs-lookup"><span data-stu-id="9ed6d-279">For SharePoint Online and OneDrive for Business, replace  *Office 365 appID* with `00000003-0000-0ff1-ce00-000000000000`</span></span>
    
  <span data-ttu-id="9ed6d-280">Esempio: impostazione delle autorizzazioni per Exchange Online e Skype for business:</span><span class="sxs-lookup"><span data-stu-id="9ed6d-280">Example: Setting permissions for Exchange Online and Skype for Business:</span></span>
    
  ```
  Set-AzureRmKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 
  -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName 00000002-0000-0ff1-ce00-000000000000
  ```

  <span data-ttu-id="9ed6d-281">Esempio: impostazione delle autorizzazioni per SharePoint Online e OneDrive for business</span><span class="sxs-lookup"><span data-stu-id="9ed6d-281">Example: Setting permissions for SharePoint Online and OneDrive for Business</span></span>
    
  ```
  Set-AzureRmKeyVaultAccessPolicy -VaultName Contoso-O365SP-NA-VaultA1 
  -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName 00000003-0000-0ff1-ce00-000000000000
  ```

### <a name="enable-and-then-confirm-soft-delete-on-your-key-vaults"></a><span data-ttu-id="9ed6d-282">Abilitare e quindi confermare l'eliminazione morbida sui Vault delle chiavi</span><span class="sxs-lookup"><span data-stu-id="9ed6d-282">Enable and then confirm soft delete on your key vaults</span></span>
<span data-ttu-id="9ed6d-283"><a name="SoftDelete"> </a></span><span class="sxs-lookup"><span data-stu-id="9ed6d-283"></span></span>

<span data-ttu-id="9ed6d-p134">Quando è possibile recuperare rapidamente le chiavi, è meno probabile che si verifichi un'interruzione del servizio estesa a causa di chiavi accidentali o eliminate intenzionalmente. È necessario abilitare questa configurazione, denominata eliminazione temporanea, prima di poter utilizzare le chiavi con il codice "Customer Key". L'abilitazione dell'eliminazione temporanea consente di recuperare le chiavi o i Vault entro 90 giorni dall'eliminazione senza dover ripristinare il backup.</span><span class="sxs-lookup"><span data-stu-id="9ed6d-p134">When you can quickly recover your keys, you are less likely to experience an extended service outage due to accidentally or maliciously deleted keys. You need to enable this configuration, referred to as Soft Delete, before you can use your keys with Customer Key. Enabling Soft Delete allows you to recover keys or vaults within 90 days of deletion without having to restore them from backup.</span></span>
  
<span data-ttu-id="9ed6d-287">Per abilitare l'eliminazione temporanea nei Vault delle chiavi, eseguire la procedura seguente:</span><span class="sxs-lookup"><span data-stu-id="9ed6d-287">To enable Soft Delete on your key vaults, complete these steps:</span></span>
  
1. <span data-ttu-id="9ed6d-p135">Accedere alla sottoscrizione di Azure con Windows PowerShell. Per istruzioni, vedere [accedere con Azure PowerShell](https://docs.microsoft.com/powershell/azure/authenticate-azureps).</span><span class="sxs-lookup"><span data-stu-id="9ed6d-p135">Log in to your Azure subscription with Windows Powershell. For instructions, see [Log in with Azure PowerShell](https://docs.microsoft.com/powershell/azure/authenticate-azureps).</span></span>
    
2. <span data-ttu-id="9ed6d-p136">Eseguire il cmdlet [Get-AzureRmKeyVault](https://docs.microsoft.com/powershell/module/azurerm.keyvault/get-azurermkeyvault) . In questo esempio, *VAULTNAME* è il nome del Vault Key per il quale si desidera abilitare l'eliminazione morbida:</span><span class="sxs-lookup"><span data-stu-id="9ed6d-p136">Run the [Get-AzureRmKeyVault](https://docs.microsoft.com/powershell/module/azurerm.keyvault/get-azurermkeyvault) cmdlet. In this example, *vaultname* is the name of the key vault for which you are enabling soft delete:</span></span> 
    
   ```
   $v = Get-AzureRmKeyVault -VaultName <vaultname>
   $r = Get-AzureRmResource -ResourceId $v.ResourceId
   $r.Properties | Add-Member -MemberType NoteProperty -Name enableSoftDelete -Value 'True'
   Set-AzureRmResource -ResourceId $r.ResourceId -Properties $r.Properties
   ``` 
    
3. <span data-ttu-id="9ed6d-p137">Confirm soft delete è configurato per il Vault Key tramite l'esecuzione del cmdlet **Get-AzureRmKeyVault** . Se l'eliminazione morbida è configurata correttamente per il Vault chiave, l'eliminazione temporanea è abilitata? la proprietà restituisce il valore **true**:</span><span class="sxs-lookup"><span data-stu-id="9ed6d-p137">Confirm soft delete is configured for the key vault by running the **Get-AzureRmKeyVault** cmdlet. If soft delete is configured properly for the key vault, then the  Soft Delete Enabled? property returns a value of **True**:</span></span> 
    
   ```
   Get-AzureRmKeyVault -VaultName <vaultname> | fl
   ```

   
    
### <a name="add-a-key-to-each-key-vault-either-by-creating-or-importing-a-key"></a><span data-ttu-id="9ed6d-294">Aggiungere una chiave a ogni Vault chiave creando o importando una chiave</span><span class="sxs-lookup"><span data-stu-id="9ed6d-294">Add a key to each key vault either by creating or importing a key</span></span>
<span data-ttu-id="9ed6d-295"><a name="AddKeystoKeyVault"> </a></span><span class="sxs-lookup"><span data-stu-id="9ed6d-295"></span></span>

<span data-ttu-id="9ed6d-p138">Esistono due modi per aggiungere chiavi a un Vault Key di Azure; è possibile creare una chiave direttamente in Key Vault oppure è possibile importare una chiave. La creazione di una chiave direttamente in Key Vault è il metodo meno complicato, mentre l'importazione di una chiave fornisce il controllo totale sul modo in cui viene generata la chiave.</span><span class="sxs-lookup"><span data-stu-id="9ed6d-p138">There are two ways to add keys to an Azure Key Vault; you can create a key directly in Key Vault, or you can import a key. Creating a key directly in Key Vault is the less complicated method, while importing a key provides total control over how the key is generated.</span></span>
  
<span data-ttu-id="9ed6d-298">Per creare una chiave direttamente nel Vault chiave, eseguire il cmdlet [Add-AzureKeyVaultKey](https://docs.microsoft.com/powershell/module/AzureRM.KeyVault/Add-AzureKeyVaultKey) nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="9ed6d-298">To create a key directly in your key vault, run the [Add-AzureKeyVaultKey](https://docs.microsoft.com/powershell/module/AzureRM.KeyVault/Add-AzureKeyVaultKey) cmdlet as follows:</span></span> 
  
```
Add-AzureKeyVaultKey -VaultName <vaultname> -Name <keyname> -Destination <HSM|Software> -KeyOps wrapKey,unwrapKey
```

<span data-ttu-id="9ed6d-299">Dove:</span><span class="sxs-lookup"><span data-stu-id="9ed6d-299">Where:</span></span>
  
-  <span data-ttu-id="9ed6d-300">*VAULTNAME* è il nome del Vault chiave in cui si desidera creare la chiave.</span><span class="sxs-lookup"><span data-stu-id="9ed6d-300">*vaultname*  is the name of the key vault in which you want to create the key.</span></span> 
    
-  <span data-ttu-id="9ed6d-301">\*\* nome del tasto è il nome che si desidera assegnare alla nuova chiave.</span><span class="sxs-lookup"><span data-stu-id="9ed6d-301">*keyname*  is the name you want to give the new key.</span></span> 
    
    > [!TIP]
    > <span data-ttu-id="9ed6d-p139">Le chiavi dei nomi utilizzano una convenzione di denominazione simile, come descritto in alto per i Vault chiave. In questo modo, in strumenti che mostrano solo il nome della chiave, la stringa è autoesplicativa.</span><span class="sxs-lookup"><span data-stu-id="9ed6d-p139">Name keys using a similar naming convention as described above for key vaults. This way, in tools that show only the key name, the string is self-describing.</span></span> 
  
- <span data-ttu-id="9ed6d-304">Se si intende proteggere la chiave con un HSM, accertarsi di specificare **HSM** come valore del parametro Destination, __ in caso contrario, specificare il **software**.</span><span class="sxs-lookup"><span data-stu-id="9ed6d-304">If you intend to protect the key with an HSM, ensure that you specify **HSM** as the value of the  _Destination_ parameter, otherwise, specify **Software**.</span></span>
    
<span data-ttu-id="9ed6d-305">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="9ed6d-305">For example,</span></span>
  
```
Add-AzureKeyVaultKey -VaultName Contoso-O365EX-NA-VaultA1 -Name Contoso-O365EX-NA-VaultA1-Key001 -Destination Software -KeyOps wrapKey,unwrapKey
```

<span data-ttu-id="9ed6d-306">Per importare una chiave direttamente nel Vault chiave, è necessario disporre di un modulo di sicurezza hardware di Thales nShield.</span><span class="sxs-lookup"><span data-stu-id="9ed6d-306">To import a key directly into your key vault, you need to have a Thales nShield Hardware Security Module.</span></span>
  
<span data-ttu-id="9ed6d-307">Alcune organizzazioni preferiscono questo approccio per stabilire la provenienza delle chiavi e questo metodo fornisce anche gli elementi seguenti:</span><span class="sxs-lookup"><span data-stu-id="9ed6d-307">Some organizations prefer this approach to establish the provenance of their keys, and the this method also provides the following:</span></span>
  
- <span data-ttu-id="9ed6d-308">Il set di strumenti utilizzato per l'importazione include l'attestazione di Thales che la chiave Key Exchange (KEK) utilizzata per crittografare la chiave che si genera non è esportabile e che viene generata all'interno di un HSM genuino prodotto da Thales.</span><span class="sxs-lookup"><span data-stu-id="9ed6d-308">The toolset used for import includes attestation from Thales that the Key Exchange Key (KEK) that is used to encrypt the key you generate is not exportable and is generated inside a genuine HSM that was manufactured by Thales.</span></span>
    
- <span data-ttu-id="9ed6d-p140">Il set di strumenti include l'attestazione di Thales che la sicurezza di Azure Key Vault è stata generata anche su un HSM genuino prodotto da Thales. L'attestazione dimostra che Microsoft utilizza anche hardware reale Thales.</span><span class="sxs-lookup"><span data-stu-id="9ed6d-p140">The toolset includes attestation from Thales that the Azure Key Vault security world was also generated on a genuine HSM manufactured by Thales. This attestation proves to you that Microsoft is also using genuine Thales hardware.</span></span>
    
<span data-ttu-id="9ed6d-p141">Verificare con il gruppo di sicurezza se sono necessarie le attestazioni sopra riportate. Per la procedura dettagliata per creare una chiave locale e importarla nel Vault chiave, vedere [How to generate and transfer HSM-protected Keys for Azure Key Vault](https://azure.microsoft.com/documentation/articles/key-vault-hsm-protected-keys/). Utilizzare le istruzioni di Azure per creare una chiave in ogni Vault Key.</span><span class="sxs-lookup"><span data-stu-id="9ed6d-p141">Check with your security group to determine if the above attestations are required. For detailed steps to create a key on-premises and import it into your key vault, see [How to generate and transfer HSM-protected keys for Azure Key Vault](https://azure.microsoft.com/documentation/articles/key-vault-hsm-protected-keys/). Use the Azure instructions to create a key in each key vault.</span></span>
  
### <a name="check-the-recovery-level-of-your-keys"></a><span data-ttu-id="9ed6d-314">Controllare il livello di ripristino delle chiavi</span><span class="sxs-lookup"><span data-stu-id="9ed6d-314">Check the recovery level of your keys</span></span>
<span data-ttu-id="9ed6d-315"><a name="CheckKeyRecoveryLevel"> </a></span><span class="sxs-lookup"><span data-stu-id="9ed6d-315"></span></span>

<span data-ttu-id="9ed6d-p142">Office 365 richiede che la sottoscrizione di Azure Key Vault sia impostata su non Annulla e che le chiavi utilizzate dal codice "Customer Key" siano abilitate per l'eliminazione temporanea. È possibile confermarlo esaminando il livello di ripristino delle chiavi.</span><span class="sxs-lookup"><span data-stu-id="9ed6d-p142">Office 365 requires that the Azure Key Vault subscription is set to Do Not Cancel and that the keys used by Customer Key have soft delete enabled. You can confirm this by looking at the recovery level on your keys.</span></span>
  
<span data-ttu-id="9ed6d-318">Per controllare il livello di ripristino di una chiave, in Azure PowerShell, eseguire il cmdlet Get-AzureKeyVaultKey come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="9ed6d-318">To check the recovery level of a key, in Azure PowerShell, run the Get-AzureKeyVaultKey cmdlet as follows:</span></span>
  
```
(Get-AzureKeyVaultKey -VaultName <vaultname> -Name <keyname>).Attributes 
```

<span data-ttu-id="9ed6d-319">Se la proprietà del _livello di recupero_ restituisce un valore diverso da quello di **+ ProtectedSubscription**, sarà necessario esaminare questo argomento e assicurarsi di aver seguito tutti i passaggi necessari per inserire la sottoscrizione nell'elenco non annullare e che l'eliminazione temporanea è abilitata su ognuna delle volte chiave.</span><span class="sxs-lookup"><span data-stu-id="9ed6d-319">If the  _Recovery Level_ property returns anything other than a value of **Recoverable+ProtectedSubscription**, you will need to review this topic and ensure that you have followed all of the steps to put the subscription on the Do Not Cancel list and that you have soft delete enabled on each of your key vaults.</span></span>
  
### <a name="backup-azure-key-vault"></a><span data-ttu-id="9ed6d-320">Backup della chiave del Vault di Azure</span><span class="sxs-lookup"><span data-stu-id="9ed6d-320">Backup Azure Key Vault</span></span>
<span data-ttu-id="9ed6d-321"><a name="BackupAzureKeyVaultkeys"> </a></span><span class="sxs-lookup"><span data-stu-id="9ed6d-321"></span></span>

<span data-ttu-id="9ed6d-p143">Subito dopo la creazione o qualsiasi modifica apportata a una chiave, eseguire un backup e archiviare copie del backup, sia online che offline. Le copie offline non devono essere connesse a nessuna rete, ad esempio in una struttura di archiviazione sicura o commerciale fisica. Almeno una copia del backup deve essere archiviata in un percorso che sarà accessibile in caso di emergenza. Gli oggetti BLOB di backup sono gli unici strumenti per ripristinare il materiale chiave se una chiave del Vault Key deve essere definitivamente distrutta o altrimenti resa inutilizzabile. Le chiavi esterne all'archivio delle chiavi di Azure e sono state importate in Azure Key Vault non sono qualificate come backup poiché i metadati necessari per la chiave del cliente per l'utilizzo della chiave non sono presenti con la chiave esterna. È possibile utilizzare solo un backup da Vault Key di Azure per le operazioni di ripristino con il codice "Customer Key". Pertanto, è essenziale che un backup del Vault Key di Azure venga eseguito dopo il caricamento o la creazione di una chiave.</span><span class="sxs-lookup"><span data-stu-id="9ed6d-p143">Immediately following creation or any change to a key, perform a backup and store copies of the backup, both online and offline. Offline copies should not be connected to any network, such as in a physical safe or commercial storage facility. At least one copy of the backup should be stored in a location that will be accessible in the event of a disaster. The backup blobs are the sole means of restoring key material should a Key Vault key be permanently destroyed or otherwise rendered inoperable. Keys that are external to Azure Key Vault and were imported to Azure Key Vault do not qualify as a backup because the metadata necessary for Customer Key to use the key does not exist with the external key. Only a backup taken from Azure Key Vault can be used for restore operations with Customer Key. Therefore, it is essential that a backup of Azure Key Vault be made once a key is uploaded or created.</span></span>
  
<span data-ttu-id="9ed6d-329">Per creare un backup di una chiave del Vault Key di Azure, eseguire il cmdlet [backup-AzureKeyVaultKey](https://docs.microsoft.com/powershell/module/AzureRM.KeyVault/Backup-AzureKeyVaultKey) come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="9ed6d-329">To create a backup of an Azure Key Vault key, run the [Backup-AzureKeyVaultKey](https://docs.microsoft.com/powershell/module/AzureRM.KeyVault/Backup-AzureKeyVaultKey) cmdlet as follows:</span></span>
```
Backup-AzureKeyVaultKey -VaultName <vaultname> -Name <keyname> 
-OutputFile <filename .backup>

```

<span data-ttu-id="9ed6d-330">Verificare che il file di output utilizzi il `.backup`suffisso.</span><span class="sxs-lookup"><span data-stu-id="9ed6d-330">Ensure that your output file uses the suffix  `.backup`.</span></span>
  
<span data-ttu-id="9ed6d-p144">Il file di output risultante da questo cmdlet è crittografato e non può essere utilizzato all'esterno del Vault Key di Azure. Il backup può essere ripristinato solo per la sottoscrizione di Azure da cui è stato effettuato il backup.</span><span class="sxs-lookup"><span data-stu-id="9ed6d-p144">The output file resulting from this cmdlet is encrypted and cannot be used outside of Azure Key Vault. The backup can be restored only to the Azure subscription from which the backup was taken.</span></span>
  
> [!TIP]
> <span data-ttu-id="9ed6d-p145">Per il file di output, scegliere una combinazione del nome del Vault e del nome della chiave. Questo renderà il nome di file autodescrittivo. Assicurerà inoltre che i nomi dei file di backup non entrino in collisione.</span><span class="sxs-lookup"><span data-stu-id="9ed6d-p145">For the output file, choose a combination of your vault name and key name. This will make the file name self-describing. It will also ensure that backup file names do not collide.</span></span> 
  
<span data-ttu-id="9ed6d-336">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="9ed6d-336">For example:</span></span>
  
```
Backup-AzureKeyVaultKey -VaultName Contoso-O365EX-NA-VaultA1 -Name Contoso-O365EX-NA-VaultA1-Key001 -OutputFile Contoso-O365EX-NA-VaultA1-Key001-Backup-20170802.backup
```

### <a name="validate-azure-key-vault-configuration-settings"></a><span data-ttu-id="9ed6d-337">ConValidare le impostazioni di configurazione di Azure Key Vault</span><span class="sxs-lookup"><span data-stu-id="9ed6d-337">Validate Azure Key Vault configuration settings</span></span>
<span data-ttu-id="9ed6d-338"><a name="Validateconfiguration"> </a></span><span class="sxs-lookup"><span data-stu-id="9ed6d-338"></span></span>

<span data-ttu-id="9ed6d-p146">L'esecuzione della convalida prima di utilizzare le chiavi in una funzionalità DEP è facoltativa, ma è consigliabile. In particolare, se si utilizzano i passaggi necessari per configurare le chiavi e le volte diverse da quelle descritte in questo argomento, è consigliabile convalidare l'integrità delle risorse del Vault Key di Azure prima di configurare la chiave del cliente.</span><span class="sxs-lookup"><span data-stu-id="9ed6d-p146">Performing validation before using keys in a DEP is optional, but highly recommended. In particular, if you use steps to set up your keys and vaults other than the ones described in this topic, you should validate the health of your Azure Key Vault resources before you configure Customer Key.</span></span>
  
<span data-ttu-id="9ed6d-341">Per verificare che le chiavi dispongano delle operazioni get, wrapKey e unwrapKey attivate:</span><span class="sxs-lookup"><span data-stu-id="9ed6d-341">To verify that your keys have get, wrapKey, and unwrapKey operations enabled:</span></span>
  
<span data-ttu-id="9ed6d-342">Eseguire il cmdlet [Get-AzureRmKeyVault](https://docs.microsoft.com/powershell/module/AzureRM.KeyVault/Get-AzureRmKeyVault) nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="9ed6d-342">Run the [Get-AzureRmKeyVault](https://docs.microsoft.com/powershell/module/AzureRM.KeyVault/Get-AzureRmKeyVault) cmdlet as follows:</span></span> 
  
```
Get-AzureRMKeyVault -VaultName <vaultname>
```

<span data-ttu-id="9ed6d-p147">Nell'output, cercare il criterio di accesso e per l'identità di Exchange Online (GUID) o l'identità di SharePoint Online (GUID) in base alle esigenze. Tutte e tre le autorizzazioni sopra riportate devono essere visualizzate in autorizzazioni per le chiavi.</span><span class="sxs-lookup"><span data-stu-id="9ed6d-p147">In the output, look for the Access Policy and for the Exchange Online identity (GUID) or the SharePoint Online identity (GUID) as appropriate. All three of the above permissions must be shown under Permissions to Keys.</span></span>
  
<span data-ttu-id="9ed6d-345">Se la configurazione del criterio di accesso non è corretta, eseguire il cmdlet Set-AzureRmKeyVaultAccessPolicy come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="9ed6d-345">If the access policy configuration is incorrect, run the Set-AzureRmKeyVaultAccessPolicy cmdlet as follows:</span></span>
  
```
Set-AzureRmKeyVaultAccessPolicy -VaultName <vaultname> -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName <Office 365 appID>
```

<span data-ttu-id="9ed6d-346">Ad esempio, per Exchange Online e Skype for business:</span><span class="sxs-lookup"><span data-stu-id="9ed6d-346">For example, for Exchange Online and Skype for Business:</span></span>
  
```
Set-AzureRmKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 
-PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName 00000002-0000-0ff1-ce00-000000000000
```

<span data-ttu-id="9ed6d-347">Ad esempio, per SharePoint Online e OneDrive for business:</span><span class="sxs-lookup"><span data-stu-id="9ed6d-347">For example, for SharePoint Online and OneDrive for Business:</span></span>
  
```
Set-AzureRmKeyVaultAccessPolicy -VaultName Contoso-O365SP-NA-VaultA1 
-PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName TBD
```

<span data-ttu-id="9ed6d-348">Per verificare che non sia impostata una data di scadenza per le chiavi, eseguire il cmdlet [Get-AzureKeyVaultKey](https://docs.microsoft.com/powershell/module/AzureRM.KeyVault/Get-AzureKeyVaultKey) come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="9ed6d-348">To verify that an expiration date is not set for your keys run the [Get-AzureKeyVaultKey](https://docs.microsoft.com/powershell/module/AzureRM.KeyVault/Get-AzureKeyVaultKey) cmdlet as follows:</span></span> 
  
```
Get-AzureKeyVaultKey -VaultName <vaultname> 
```

<span data-ttu-id="9ed6d-p148">Non è possibile utilizzare una chiave scaduta dalla chiave del cliente e le operazioni tentate con una chiave scaduta avranno esito negativo e, eventualmente, si verificherà un'interruzione del servizio. È consigliabile che i tasti utilizzati con la chiave del cliente non abbiano una data di scadenza. La data di scadenza, una volta impostata, non può essere rimossa, ma può essere modificata in una data diversa. Se è necessario utilizzare una chiave con un set di date di scadenza, impostare il valore di scadenza su 12/31/9999. Le chiavi con una data di scadenza impostata su una data diversa da 12/31/9999 non supereranno la convalida di Office 365.</span><span class="sxs-lookup"><span data-stu-id="9ed6d-p148">An expired key cannot be used by Customer Key and operations attempted with an expired key will fail, and possibly result in a service outage. We strongly recommend that keys used with Customer Key do not have an expiration date. An expiration date, once set, cannot be removed, but can be changed to a different date. If a key must be used that has an expiration date set, change the expiration value to 12/31/9999. Keys with an expiration date set to a date other than 12/31/9999 will not pass Office 365 validation.</span></span>
  
<span data-ttu-id="9ed6d-354">Per modificare una data di scadenza impostata su un valore diverso da 12/31/9999, eseguire il cmdlet [set-AzureKeyVaultKeyAttribute](https://docs.microsoft.com/powershell/module/AzureRM.KeyVault/Set-AzureKeyVaultKeyAttribute) come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="9ed6d-354">To change an expiration date that has been set to any value other than 12/31/9999, run the [Set-AzureKeyVaultKeyAttribute](https://docs.microsoft.com/powershell/module/AzureRM.KeyVault/Set-AzureKeyVaultKeyAttribute) cmdlet as follows:</span></span> 
  
```
Set-AzureKeyVaultKeyAttribute -VaultName <vaultname> -Name <keyname> 
-Expires (Get-Date -Date "12/31/9999")
```

> [!CAUTION]
> <span data-ttu-id="9ed6d-355">Non impostare le date di scadenza per le chiavi di crittografia utilizzate con la chiave del cliente.</span><span class="sxs-lookup"><span data-stu-id="9ed6d-355">Don't set expiration dates on encryption keys you use with Customer Key.</span></span> 
  
### <a name="obtain-the-uri-for-each-azure-key-vault-key"></a><span data-ttu-id="9ed6d-356">Ottenere l'URI per ogni chiave del Vault Key di Azure</span><span class="sxs-lookup"><span data-stu-id="9ed6d-356">Obtain the URI for each Azure Key Vault key</span></span>
<span data-ttu-id="9ed6d-357"><a name="GetKeyURI"> </a></span><span class="sxs-lookup"><span data-stu-id="9ed6d-357"></span></span>

<span data-ttu-id="9ed6d-p149">Dopo aver completato tutti i passaggi in Azure per configurare i Vault chiave e aver aggiunto le chiavi, eseguire il seguente comando per ottenere l'URI per la chiave in ogni Vault Key. Sarà necessario utilizzare questi URI quando si crea e si assegna ogni DEP in un secondo momento, quindi salvare queste informazioni in una posizione sicura. Ricordarsi di eseguire questo comando una volta per ogni Vault Key.</span><span class="sxs-lookup"><span data-stu-id="9ed6d-p149">Once you have completed all the steps in Azure to set up your key vaults and added your keys, run the following command to get the URI for the key in each key vault. You will need to use these URIs when you create and assign each DEP later, so save this information in a safe place. Remember to run this command once for each key vault.</span></span>
  
<span data-ttu-id="9ed6d-361">In Azure PowerShell:</span><span class="sxs-lookup"><span data-stu-id="9ed6d-361">In Azure PowerShell:</span></span>
  
```
(Get-AzureKeyVaultKey -VaultName <vaultname>).Id
```

## <a name="office-365-setting-up-customer-key-for-exchange-online-and-skype-for-business"></a><span data-ttu-id="9ed6d-362">Office 365: impostazione della chiave del cliente per Exchange Online e Skype for business</span><span class="sxs-lookup"><span data-stu-id="9ed6d-362">Office 365: Setting up Customer Key for Exchange Online and Skype for Business</span></span>
<span data-ttu-id="9ed6d-363"><a name="AzureSteps"> </a></span><span class="sxs-lookup"><span data-stu-id="9ed6d-363"></span></span>

<span data-ttu-id="9ed6d-p150">Prima di iniziare, assicurarsi di aver completato le attività necessarie per configurare l'archiviazione delle chiavi di Azure. Per informazioni, vedere [complete tasks in Azure Key Vault e Microsoft FastTrack for Customer Key](controlling-your-data-using-customer-key.md#AzureSteps) .</span><span class="sxs-lookup"><span data-stu-id="9ed6d-p150">Before you begin, ensure that you have completed the tasks required to set up Azure Key Vault. See [Complete tasks in Azure Key Vault and Microsoft FastTrack for Customer Key](controlling-your-data-using-customer-key.md#AzureSteps) for information.</span></span> 
  
<span data-ttu-id="9ed6d-366">Per impostare la chiave del cliente per Exchange Online e Skype for business, è necessario eseguire questa procedura per la connessione remota a Exchange Online con Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9ed6d-366">To set up Customer Key for Exchange Online and Skype for Business, you will need to perform these steps by remotely connecting to Exchange Online with Windows PowerShell.</span></span>
  
### <a name="create-a-data-encryption-policy-dep-for-use-with-exchange-online-and-skype-for-business"></a><span data-ttu-id="9ed6d-367">Creare un criterio di crittografia dei dati per l'utilizzo con Exchange Online e Skype for business</span><span class="sxs-lookup"><span data-stu-id="9ed6d-367">Create a data encryption policy (DEP) for use with Exchange Online and Skype for Business</span></span>
<span data-ttu-id="9ed6d-368"><a name="CreateDEP4EXOSkype"> </a></span><span class="sxs-lookup"><span data-stu-id="9ed6d-368"></span></span>

<span data-ttu-id="9ed6d-p151">Un DEP è associato a un set di chiavi archiviate in Azure Key Vault. È possibile assegnare una DEP a una cassetta postale in Office 365. Office 365 utilizzerà quindi le chiavi identificate nel criterio per crittografare la cassetta postale. Per creare la funzionalità di protezione esecuzione programmi, è necessario disporre degli URI del Vault Key ottenuti in precedenza. Per istruzioni, vedere [ottenere l'URI per ogni chiave del Vault Key di Azure](controlling-your-data-using-customer-key.md#GetKeyURI) .</span><span class="sxs-lookup"><span data-stu-id="9ed6d-p151">A DEP is associated with a set of keys stored in Azure Key Vault. You assign a DEP to a mailbox in Office 365. Office 365 will then use the keys identified in the policy to encrypt the mailbox. To create the DEP, you need the Key Vault URIs you obtained earlier. See [Obtain the URI for each Azure Key Vault key](controlling-your-data-using-customer-key.md#GetKeyURI) for instructions.</span></span> 
  
<span data-ttu-id="9ed6d-p152">Ricordo! Quando si crea una funzionalità di protezione esecuzione programmi, si specificano due chiavi che si trovano in due diversi Vault chiave di Azure. Verificare che queste chiavi si trovino in due aree di Azure separate per garantire la ridondanza geografica.</span><span class="sxs-lookup"><span data-stu-id="9ed6d-p152">Remember! When you create a DEP, you specify two keys that reside in two different Azure Key Vaults. Ensure that these keys are located in two separate Azure regions to ensure geo-redundancy.</span></span>
  
<span data-ttu-id="9ed6d-377">Per creare la funzionalità di protezione esecuzione programmi, eseguire la procedura seguente:</span><span class="sxs-lookup"><span data-stu-id="9ed6d-377">To create the DEP, follow these steps:</span></span>
  
1. <span data-ttu-id="9ed6d-378">Nel computer locale, utilizzando un account aziendale o dell'Istituto di istruzione con autorizzazioni di amministratore globale nell'organizzazione di Office 365, [connettersi a PowerShell di Exchange Online](https://technet.microsoft.com/en-us/library/jj984289%28v=exchg.160%29.aspx) aprendo Windows PowerShell ed eseguendo il comando riportato di seguito.</span><span class="sxs-lookup"><span data-stu-id="9ed6d-378">On your local computer, using a work or school account that has global administrator permissions in your Office 365 organization, [connect to Exchange Online PowerShell](https://technet.microsoft.com/en-us/library/jj984289%28v=exchg.160%29.aspx) by opening Windows PowerShell and running the following command.</span></span> 
    
   ```
   $UserCredential = Get-Credential
   ```

2. <span data-ttu-id="9ed6d-379">Nella finestra di dialogo richiesta credenziali di Windows PowerShell, immettere le informazioni dell'account aziendale o dell'Istituto di istruzione, fare clic su **OK**e quindi immettere il comando seguente.</span><span class="sxs-lookup"><span data-stu-id="9ed6d-379">In the Windows PowerShell Credential Request dialog box, enter your work or school account information, click **OK**, and then enter the following command.</span></span> 
    
   ```
   $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/powershell-liveid/ -Credential $UserCredential -Authentication Basic -AllowRedirection
   ```

3. <span data-ttu-id="9ed6d-380">Eseguire il comando riportato di seguito.</span><span class="sxs-lookup"><span data-stu-id="9ed6d-380">Run the following command.</span></span>
    
   ```
   Import-PSSession $Session
   ```

4. <span data-ttu-id="9ed6d-381">Per creare una funzionalità di protezione esecuzione programmi, utilizzare il cmdlet New-DataEncryptionPolicy digitando il comando seguente.</span><span class="sxs-lookup"><span data-stu-id="9ed6d-381">To create a DEP, use the New-DataEncryptionPolicy cmdlet by typing the following command.</span></span>
    
   ```
   New-DataEncryptionPolicy -Name <PolicyName> -Description "PolicyDescription " -AzureKeyIDs <KeyVaultURI1>, <KeyVaultURI2>
   ```

   <span data-ttu-id="9ed6d-382">Dove:</span><span class="sxs-lookup"><span data-stu-id="9ed6d-382">Where:</span></span>
    
   -  <span data-ttu-id="9ed6d-p153">*PolicyName* è il nome che si desidera utilizzare per il criterio. I nomi non possono contenere spazi. Ad esempio, USA_mailboxes.</span><span class="sxs-lookup"><span data-stu-id="9ed6d-p153">*PolicyName*  is the name you want to use for the policy. Names cannot contain spaces. For example, USA_mailboxes.</span></span> 
    
   -  <span data-ttu-id="9ed6d-p154">*PolicyDescription* è una descrizione facile da usare per i criteri che consentiranno di ricordare a cosa serve il criterio. È possibile includere spazi nella descrizione. Ad esempio, la chiave radice per le cassette postali negli Stati Uniti e nei suoi territori.</span><span class="sxs-lookup"><span data-stu-id="9ed6d-p154">*PolicyDescription*  is a user friendly description of the policy that will help you remember what the policy is for. You can include spaces in the description. For example, Root key for mailboxes in USA and its territories.</span></span> 
    
   -  <span data-ttu-id="9ed6d-p155">*KeyVaultURI1* è l'URI per la prima chiave del criterio. Ad esempio, https://contoso_EastUSvault01.vault.azure.net/keys/USA_key_01.</span><span class="sxs-lookup"><span data-stu-id="9ed6d-p155">*KeyVaultURI1*  is the URI for the first key in the policy. For example, https://contoso_EastUSvault01.vault.azure.net/keys/USA_key_01.</span></span> 
    
   -  <span data-ttu-id="9ed6d-p156">*KeyVaultURI2* è l'URI per la seconda chiave del criterio. Ad esempio, https://contoso_EastUS2vault01.vault.azure.net/keys/USA_Key_02. Separare i due URI da una virgola e uno spazio.</span><span class="sxs-lookup"><span data-stu-id="9ed6d-p156">*KeyVaultURI2*  is the URI for the second key in the policy. For example, https://contoso_EastUS2vault01.vault.azure.net/keys/USA_Key_02. Separate the two URIs by a comma and a space.</span></span> 
    
   <span data-ttu-id="9ed6d-394">Esempio:</span><span class="sxs-lookup"><span data-stu-id="9ed6d-394">Example:</span></span>
  
   ```
   New-DataEncryptionPolicy -Name USA_mailboxes -Description "Root key for mailboxes in USA and its territories" -AzureKeyIDs https://contoso_EastUSvault01.vault.azure.net/keys/USA_key_01, https://contoso_EastUS2vault01.vault.azure.net/keys/USA_Key_02
   ```

### <a name="assign-a-dep-to-a-mailbox"></a><span data-ttu-id="9ed6d-395">Assegnare una DEP a una cassetta postale</span><span class="sxs-lookup"><span data-stu-id="9ed6d-395">Assign a DEP to a mailbox</span></span>
<span data-ttu-id="9ed6d-396"><a name="assignDEPtomailbox"> </a></span><span class="sxs-lookup"><span data-stu-id="9ed6d-396"></span></span>

<span data-ttu-id="9ed6d-p157">Assegnare la funzionalità Protezione esecuzione programmi a una cassetta postale utilizzando il cmdlet Set-Mailbox. Dopo aver assegnato il criterio, Office 365 può crittografare la cassetta postale con la chiave indicata nella DEP.</span><span class="sxs-lookup"><span data-stu-id="9ed6d-p157">Assign the DEP to a mailbox by using the Set-Mailbox cmdlet. Once you assign the policy, Office 365 can encrypt the mailbox with the key designated in the DEP.</span></span>
  
```
Set-Mailbox -Identity <MailboxIdParameter> -DataEncryptionPolicy <PolicyName>
```

<span data-ttu-id="9ed6d-p158">Dove *MailboxIdParameter* specifica una cassetta postale. Per ulteriori informazioni sul cmdlet Set-Mailbox, vedere [Set-Mailbox](https://technet.microsoft.com/library/bb123981%28v=exchg.160%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="9ed6d-p158">Where *MailboxIdParameter* specifies a mailbox. For more information about the Set-Mailbox cmdlet, see [Set-Mailbox](https://technet.microsoft.com/library/bb123981%28v=exchg.160%29.aspx).</span></span>
  
### <a name="validate-mailbox-encryption"></a><span data-ttu-id="9ed6d-401">ConValidare la crittografia della cassetta postale</span><span class="sxs-lookup"><span data-stu-id="9ed6d-401">Validate mailbox encryption</span></span>
<span data-ttu-id="9ed6d-402"><a name="validatemailboxencryption"> </a></span><span class="sxs-lookup"><span data-stu-id="9ed6d-402"></span></span>

<span data-ttu-id="9ed6d-p159">La crittografia di una cassetta postale può richiedere del tempo. Per l'assegnazione dei criteri per la prima volta, la cassetta postale deve anche completare lo spostamento da un database all'altro prima che il servizio possa crittografare la cassetta postale. È consigliabile attendere 72 ore prima di tentare di convalidare la crittografia dopo aver modificato una DEP o la prima volta che si assegna una DEP a una cassetta postale.</span><span class="sxs-lookup"><span data-stu-id="9ed6d-p159">Encrypting a mailbox can take some time. For first time policy assignment, the mailbox must also complete the move from one database to another before the service can encrypt the mailbox. We recommend that you wait 72 hours before you attempt to validate encryption after you change a DEP or the first time you assign a DEP to a mailbox.</span></span>
  
<span data-ttu-id="9ed6d-406">Utilizzare il cmdlet Get-MailboxStatistics per determinare se una cassetta postale è crittografata.</span><span class="sxs-lookup"><span data-stu-id="9ed6d-406">Use the Get-MailboxStatistics cmdlet to determine if a mailbox is encrypted.</span></span>
  
```
Get-MailboxStatistics -Identity <GeneralMailboxOrMailUserIdParameter> | fl IsEncrypted
```

<span data-ttu-id="9ed6d-407">La proprietà IsEncrypted restituisce il valore **true** se la cassetta postale è crittografata e il valore **false** se la cassetta postale non è crittografata.</span><span class="sxs-lookup"><span data-stu-id="9ed6d-407">The IsEncrypted property returns a value of **true** if the mailbox is encrypted and a value of **false** if the mailbox is not encrypted.</span></span> 

<span data-ttu-id="9ed6d-p160">Il tempo necessario per completare gli spostamenti delle cassette postali dipende dal numero di cassette postali a cui viene assegnata una DEP per la prima volta, oltre che dalle dimensioni delle cassette postali. Se le cassette postali non sono state crittografate dopo una settimana dal momento in cui è stata assegnata la funzionalità DEP, avviare lo spostamento di una cassetta postale per le cassette postali non crittografate tramite il cmdlet New-MoveRequest.</span><span class="sxs-lookup"><span data-stu-id="9ed6d-p160">The time to complete mailbox moves depends on the number of mailboxes to which you assign a DEP for the first time, as well as the size of the mailboxes. If the mailboxes have not been encrypted after a week from the time you assigned the DEP, initiate a mailbox move for the unencrypted mailboxes by using the New-MoveRequest cmdlet.</span></span>

```
New-MoveRequest <mailbox alias>
``` 

## <a name="office-365-setting-up-customer-key-for-sharepoint-online-and-onedrive-for-business"></a><span data-ttu-id="9ed6d-410">Office 365: impostazione della chiave del cliente per SharePoint Online e OneDrive for business</span><span class="sxs-lookup"><span data-stu-id="9ed6d-410">Office 365: Setting up Customer Key for SharePoint Online and OneDrive for Business</span></span>
<span data-ttu-id="9ed6d-411"><a name="AzureSteps"> </a></span><span class="sxs-lookup"><span data-stu-id="9ed6d-411"></span></span>

<span data-ttu-id="9ed6d-p161">Prima di iniziare, assicurarsi di aver completato le attività necessarie per configurare l'archiviazione delle chiavi di Azure. Per informazioni, vedere [complete tasks in Azure Key Vault e Microsoft FastTrack for Customer Key](controlling-your-data-using-customer-key.md#AzureSteps) .</span><span class="sxs-lookup"><span data-stu-id="9ed6d-p161">Before you begin, ensure that you have completed the tasks required to set up Azure Key Vault. See [Complete tasks in Azure Key Vault and Microsoft FastTrack for Customer Key](controlling-your-data-using-customer-key.md#AzureSteps) for information.</span></span> 
  
<span data-ttu-id="9ed6d-414">Per impostare la chiave del cliente per SharePoint Online e OneDrive for business, è necessario eseguire questa procedura per la connessione remota a SharePoint Online con Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9ed6d-414">To set up Customer Key for SharePoint Online and OneDrive for Business, you will need to perform these steps by remotely connecting to SharePoint Online with Windows PowerShell.</span></span>
  
### <a name="create-a-data-encryption-policy-dep-for-each-sharepoint-online-and-onedrive-for-business-geo"></a><span data-ttu-id="9ed6d-415">Creare un criterio di crittografia dei dati per ogni geo di SharePoint Online e OneDrive for business</span><span class="sxs-lookup"><span data-stu-id="9ed6d-415">Create a data encryption policy (DEP) for each SharePoint Online and OneDrive for Business geo</span></span>
<span data-ttu-id="9ed6d-416"><a name="CreateDEP4SPOODfB"> </a></span><span class="sxs-lookup"><span data-stu-id="9ed6d-416"></span></span>

<span data-ttu-id="9ed6d-p162">Un DEP è associato a un set di chiavi archiviate in Azure Key Vault. È possibile applicare una DEP a tutti i dati in una posizione geografica, denominata anche geo. Se si utilizza la caratteristica multi-geo di Office 365 (attualmente in anteprima), è possibile creare una DEP per Geo. Se non si utilizza multi-Geo, è possibile creare una DEP in Office 365 per l'utilizzo con SharePoint Online e OneDrive for business. Office 365 utilizzerà quindi le chiavi identificate nella funzionalità DEP per crittografare i dati in tale Geo. Per creare la funzionalità di protezione esecuzione programmi, è necessario disporre degli URI del Vault Key ottenuti in precedenza. Per istruzioni, vedere [ottenere l'URI per ogni chiave del Vault Key di Azure](controlling-your-data-using-customer-key.md#GetKeyURI) .</span><span class="sxs-lookup"><span data-stu-id="9ed6d-p162">A DEP is associated with a set of keys stored in Azure Key Vault. You apply a DEP to all of your data in one geographic location, also called a geo. If you use the multi-geo feature of Office 365 (currently in Preview), you can create one DEP per geo. If you are not using multi-geo, you can create one DEP in Office 365 for use with SharePoint Online and OneDrive for Business. Office 365 will then use the keys identified in the DEP to encrypt your data in that geo. To create the DEP, you need the Key Vault URIs you obtained earlier. See [Obtain the URI for each Azure Key Vault key](controlling-your-data-using-customer-key.md#GetKeyURI) for instructions.</span></span> 
  
<span data-ttu-id="9ed6d-p163">Ricordo! Quando si crea una funzionalità di protezione esecuzione programmi, si specificano due chiavi che si trovano in due diversi Vault chiave di Azure. Verificare che queste chiavi si trovino in due aree di Azure separate per garantire la ridondanza geografica.</span><span class="sxs-lookup"><span data-stu-id="9ed6d-p163">Remember! When you create a DEP, you specify two keys that reside in two different Azure Key Vaults. Ensure that these keys are located in two separate Azure regions to ensure geo-redundancy.</span></span>
  
<span data-ttu-id="9ed6d-427">Per creare una funzionalità di protezione esecuzione programmi, è necessario connettersi in remoto a SharePoint Online tramite Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9ed6d-427">To create a DEP, you need to remotely connect to SharePoint Online by using Windows PowerShell.</span></span>
  
1. <span data-ttu-id="9ed6d-428">Nel computer locale, utilizzando un account aziendale o dell'Istituto di istruzione con autorizzazioni di amministratore globale nell'organizzazione di Office 365, [connettersi a PowerShell di SharePoint Online](https://technet.microsoft.com/library/fp161372.aspx).</span><span class="sxs-lookup"><span data-stu-id="9ed6d-428">On your local computer, using a work or school account that has global administrator permissions in your Office 365 organization, [Connect to SharePoint Online Powershell](https://technet.microsoft.com/library/fp161372.aspx).</span></span>
    
2. <span data-ttu-id="9ed6d-429">In Microsoft SharePoint Online Management Shell, eseguire il cmdlet [Register-SPODataEncryptionPolicy](https://technet.microsoft.com/library/mt843950.aspx) come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="9ed6d-429">In the Microsoft SharePoint Online Management Shell, run the [Register-SPODataEncryptionPolicy](https://technet.microsoft.com/library/mt843950.aspx) cmdlet as follows:</span></span> 
    
   ```
   Register-SPODataEncryptionPolicy -Identity <SPOAdminSiteUrl> -PrimaryKeyVaultName <PrimaryKeyVaultName> -PrimaryKeyName <PrimaryKeyName> -PrimaryKeyVersion <PrimaryKeyVersion> -SecondaryKeyVaultName <SecondaryKeyVaultName> -SecondaryKeyName <SecondaryKeyName> -SecondaryKeyVersion <SecondaryKeyVersion>
   ```

   <span data-ttu-id="9ed6d-p164">Quando si registra la funzionalità DEP, la crittografia inizia sui dati del geografico. Questo può richiedere un certo tempo.</span><span class="sxs-lookup"><span data-stu-id="9ed6d-p164">When you register the DEP, encryption begins on the data in the geo. This can take some time.</span></span>
    
### <a name="validate-encryption-of-group-sites-team-sites-and-onedrive-for-business"></a><span data-ttu-id="9ed6d-432">ConValidare la crittografia di siti di gruppo, siti del team e OneDrive for business</span><span class="sxs-lookup"><span data-stu-id="9ed6d-432">Validate encryption of Group Sites, Team Sites, and OneDrive for Business</span></span>
<span data-ttu-id="9ed6d-433"><a name="validateencryptionSPO"> </a></span><span class="sxs-lookup"><span data-stu-id="9ed6d-433"></span></span>

<span data-ttu-id="9ed6d-434">È possibile controllare lo stato della crittografia eseguendo il cmdlet Get-SPODataEncryptionPolicy come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="9ed6d-434">You can check on the status of encryption by running the Get-SPODataEncryptionPolicy cmdlet as follows:</span></span>
  
```
Get-SPODataEncryptionPolicy -Identity <SPOAdminSiteUrl>
```

<span data-ttu-id="9ed6d-435">L'output di questo cmdlet include:</span><span class="sxs-lookup"><span data-stu-id="9ed6d-435">The output from this cmdlet includes:</span></span>
  
- <span data-ttu-id="9ed6d-436">URI della chiave primaria.</span><span class="sxs-lookup"><span data-stu-id="9ed6d-436">The URI of the primary key.</span></span>
    
- <span data-ttu-id="9ed6d-437">URI del tasto secondario.</span><span class="sxs-lookup"><span data-stu-id="9ed6d-437">The URI of the secondary key.</span></span>
    
- <span data-ttu-id="9ed6d-p165">Lo stato di crittografia per il Geo. Gli stati possibili includono:</span><span class="sxs-lookup"><span data-stu-id="9ed6d-p165">The encryption status for the geo. Possible states include:</span></span>
    
  - <span data-ttu-id="9ed6d-440">Non **registrato:** La crittografia a chiave del cliente non è stata ancora applicata.</span><span class="sxs-lookup"><span data-stu-id="9ed6d-440">**Unregistered:** Customer Key encryption has not yet been applied.</span></span> 
    
  - <span data-ttu-id="9ed6d-p166">**Registrazione:** È stata applicata la crittografia a chiave del cliente e i file sono in fase di crittografazione. Se il geografico è in questo stato, verranno visualizzate anche informazioni su quale percentuale di siti nel Geo sono completi, in modo da poter monitorare lo stato della crittografia.</span><span class="sxs-lookup"><span data-stu-id="9ed6d-p166">**Registering:** Customer Key encryption has been applied and your files are in the process of being encrypted. If your geo is in this state, you'll also be shown information on what percentage of sites in the geo are complete so that you can monitor encryption progress.</span></span> 
    
  - <span data-ttu-id="9ed6d-443">**Registrato:** È stata applicata la crittografia a chiave del cliente e tutti i file in tutti i siti sono stati crittografati.</span><span class="sxs-lookup"><span data-stu-id="9ed6d-443">**Registered:** Customer Key encryption has been applied, and all files in all sites have been encrypted.</span></span> 
    
  - <span data-ttu-id="9ed6d-p167">**Rolling:** È in corso un roll Key. Se il geografico è in questo stato, verranno visualizzate anche informazioni su quale percentuale di siti è stata completata l'operazione di roll Key, in modo da poter monitorare lo stato di avanzamento.</span><span class="sxs-lookup"><span data-stu-id="9ed6d-p167">**Rolling:** A key roll is in progress. If your geo is in this state, you'll also be shown information on what percentage of sites have completed the key roll operation so that you can monitor progress.</span></span> 
    
## <a name="managing-customer-key-for-office-365"></a><span data-ttu-id="9ed6d-446">Gestione della chiave del cliente per Office 365</span><span class="sxs-lookup"><span data-stu-id="9ed6d-446">Managing Customer Key for Office 365</span></span>
<span data-ttu-id="9ed6d-447"><a name="ManageCustomerKey"> </a></span><span class="sxs-lookup"><span data-stu-id="9ed6d-447"></span></span>

<span data-ttu-id="9ed6d-448">Dopo aver configurato Customer Key per Office 365, è possibile eseguire queste attività di gestione aggiuntive.</span><span class="sxs-lookup"><span data-stu-id="9ed6d-448">After you've set up Customer Key for Office 365, you can perform these additional management tasks.</span></span>
  
- [<span data-ttu-id="9ed6d-449">Ripristinare le chiavi del Vault Key di Azure</span><span class="sxs-lookup"><span data-stu-id="9ed6d-449">Restore Azure Key Vault keys</span></span>](controlling-your-data-using-customer-key.md#RestoreAzureKeyVaultKeys)
    
- [<span data-ttu-id="9ed6d-450">Rotazione o rotazione di una chiave nel Vault Key di Azure utilizzata con la chiave del cliente</span><span class="sxs-lookup"><span data-stu-id="9ed6d-450">Rolling or rotating a key in Azure Key Vault that you use with Customer Key</span></span>](controlling-your-data-using-customer-key.md#RollCKkey)
    
- [<span data-ttu-id="9ed6d-451">Gestire le autorizzazioni del Vault Key</span><span class="sxs-lookup"><span data-stu-id="9ed6d-451">Manage key vault permissions</span></span>](controlling-your-data-using-customer-key.md#Managekeyvaultperms)
    
- [<span data-ttu-id="9ed6d-452">Determinare la funzionalità DEP assegnata a una cassetta postale</span><span class="sxs-lookup"><span data-stu-id="9ed6d-452">Determine the DEP assigned to a mailbox</span></span>](controlling-your-data-using-customer-key.md#DeterminemailboxDEP)
    
### <a name="restore-azure-key-vault-keys"></a><span data-ttu-id="9ed6d-453">Ripristinare le chiavi del Vault Key di Azure</span><span class="sxs-lookup"><span data-stu-id="9ed6d-453">Restore Azure Key Vault keys</span></span>
<span data-ttu-id="9ed6d-454"><a name="RestoreAzureKeyVaultKeys"> </a></span><span class="sxs-lookup"><span data-stu-id="9ed6d-454"></span></span>

<span data-ttu-id="9ed6d-p168">Prima di eseguire un ripristino, utilizzare le funzionalità di ripristino fornite da soft delete. Tutte le chiavi utilizzate con la chiave Customer devono essere abilitate per l'eliminazione temporanea. Delete Soft agisce come un cestino e consente il ripristino per un massimo di 90 giorni senza che sia necessario ripristinarlo. Il ripristino deve essere necessario solo in caso di circostanze estreme o inusuali, ad esempio se la chiave o la chiave del Vault è persa. Se è necessario ripristinare una chiave da utilizzare con la chiave Customer, in Azure PowerShell, eseguire il cmdlet Restore-AzureKeyVaultKey come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="9ed6d-p168">Before performing a restore, use the recovery capabilities provided by soft delete. All keys that are used with Customer Key are required to have soft delete enabled. Soft delete acts like a recycle bin and allows recovery for up to 90 days without the need to restore. Restore should only be required in extreme or unusual circumstances, for example if the key or key vault is lost. If you must restore a key for use with Customer Key, in Azure PowerShell, run the Restore-AzureKeyVaultKey cmdlet as follows:</span></span>
  
```
Restore-AzureKeyVaultKey -VaultName <vaultname> -InputFile <filename>
```

<span data-ttu-id="9ed6d-460">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="9ed6d-460">For example:</span></span>
  
```
Restore-AzureKeyVaultKey -VaultName Contoso-O365EX-NA-VaultA1 -InputFile Contoso-O365EX-NA-VaultA1-Key001-Backup-20170802.backup
```

<span data-ttu-id="9ed6d-p169">Se nel Vault della chiave è già presente un tasto con lo stesso nome, l'operazione di ripristino avrà esito negativo. Restore-AzureKeyVaultKey Ripristina tutte le versioni principali e tutti i metadati per la chiave, incluso il nome della chiave.</span><span class="sxs-lookup"><span data-stu-id="9ed6d-p169">If a key with the same name already exists in the key vault, the restore operation will fail. Restore-AzureKeyVaultKey restores all key versions and all metadata for the key including the key name.</span></span>
  
### <a name="rolling-or-rotating-a-key-in-azure-key-vault-that-you-use-with-customer-key"></a><span data-ttu-id="9ed6d-463">Rotazione o rotazione di una chiave nel Vault Key di Azure utilizzata con la chiave del cliente</span><span class="sxs-lookup"><span data-stu-id="9ed6d-463">Rolling or rotating a key in Azure Key Vault that you use with Customer Key</span></span>
<span data-ttu-id="9ed6d-464"><a name="RollCKkey"> </a></span><span class="sxs-lookup"><span data-stu-id="9ed6d-464"></span></span>

<span data-ttu-id="9ed6d-p170">I tasti di scorrimento non sono richiesti da un Vault di Azure Key o dal codice del cliente. Inoltre, le chiavi protette con un HSM sono virtualmente impossibili da compromettere. Anche se una chiave radice è in possesso di un attore malevolo, non è possibile utilizzarlo per decrittografare i dati, poiché solo il codice di Office 365 sa come usarlo. Tuttavia, l'implementazione di una chiave è supportata dal codice "Customer Key".</span><span class="sxs-lookup"><span data-stu-id="9ed6d-p170">Rolling keys is not required by either Azure Key Vault or by Customer Key. In addition, keys that are protected with an HSM are virtually impossible to compromise. Even if a root key were in the possession of a malicious actor there is no feasible means of using it to decrypt data, since only Office 365 code knows how to use it. However, rolling a key is supported by Customer Key.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="9ed6d-p171">Eseguire il rollback di una chiave di crittografia da utilizzare con il codice "Customer Key" se esiste un motivo tecnico chiaro oppure se un requisito di conformità richiede che è necessario eseguire il rollforward della chiave. Inoltre, non eliminare le chiavi che sono o sono state associate ai criteri. Quando si esegue il rollback delle chiavi, verranno crittografati i contenuti con le chiavi precedenti. Ad esempio, mentre le cassette postali attive verranno crittografate di frequente, le cassette postali inattive, disconnesse e disabilitate potrebbero essere ancora crittografate con le chiavi precedenti. SharePoint Online esegue il backup del contenuto per scopi di ripristino e ripristino, per cui è possibile che il contenuto archiviato sia ancora utilizzato con i tasti precedenti.</span><span class="sxs-lookup"><span data-stu-id="9ed6d-p171">Only roll an encryption key that you use with Customer Key when a clear technical reason exists or a compliance requirement dictates that you have to roll the key. In addition, do not delete any keys that are or were associated with policies. When you roll your keys, there will be content encrypted with the previous keys. For example, while active mailboxes will be re-encrypted frequently, inactive, disconnected, and disabled mailboxes may still be encrypted with the previous keys. SharePoint Online performs backup of content for restore and recovery purposes, so there may still be archived content using older keys. </span></span><br/> <span data-ttu-id="9ed6d-p172">Per garantire la sicurezza dei dati, SharePoint Online non consentirà di eseguire più di un'operazione di rollforward della chiave alla volta. Se si desidera eseguire il rollback di entrambe le chiavi in un Vault chiave, è necessario attendere il completamento completo della prima operazione di rollforward. La nostra raccomandazione è quella di scaglionare le operazioni di rollio chiave a intervalli diversi, in modo che non si tratti di un problema.</span><span class="sxs-lookup"><span data-stu-id="9ed6d-p172">To ensure the safety of your data, SharePoint Online will allow no more than one Key Roll operation to be in progress at a time. If you want to roll both of the keys in a key vault, you'll need to wait for the first key roll operation to fully complete. Our recommendation is to stagger your key roll operations at different intervals, so that this is not an issue.</span></span> 
  
<span data-ttu-id="9ed6d-p173">Quando si esegue il rollforward di una chiave, si richiede una nuova versione di una chiave esistente. Per richiedere una nuova versione di una chiave esistente, è necessario utilizzare lo stesso cmdlet [Add-AzureKeyVaultKey](https://docs.microsoft.com/powershell/module/AzureRM.KeyVault/Add-AzureKeyVaultKey), con la stessa sintassi utilizzata per creare la chiave in primo luogo.</span><span class="sxs-lookup"><span data-stu-id="9ed6d-p173">When you roll a key, you are requesting a new version of an existing key. In order to request a new version of an existing key, you use the same cmdlet, [Add-AzureKeyVaultKey](https://docs.microsoft.com/powershell/module/AzureRM.KeyVault/Add-AzureKeyVaultKey), with the same syntax that you used to create the key in the first place.</span></span>
  
<span data-ttu-id="9ed6d-479">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="9ed6d-479">For example:</span></span>
  
```
Add-AzureKeyVaultKey -VaultName Contoso-O365EX-NA-VaultA1 -Name Contoso-O365EX-NA-VaultA1-Key001 -Destination HSM -KeyOps @('wrapKey','unwrapKey') -NotBefore (Get-Date -Date "12/27/2016 12:01 AM")
```

<span data-ttu-id="9ed6d-p174">In questo esempio, poiché una chiave denominata **Contoso-O365EX-na-VaultA1-Key001** esiste già nel Vault **Contoso-O365EX-na-VaultA1** , verrà creata una nuova versione della chiave. L'operazione aggiunge una nuova versione della chiave. Questa operazione consente di conservare le versioni precedenti nella cronologia delle versioni della chiave, in modo che i dati precedentemente crittografati con tale chiave possano ancora essere decrittografati. Dopo aver completato il rollforward di qualsiasi tasto associato a una funzionalità di protezione esecuzione programmi, è necessario eseguire un ulteriore cmdlet per assicurarsi che la chiave del cliente inizi a utilizzare la nuova chiave.</span><span class="sxs-lookup"><span data-stu-id="9ed6d-p174">In this example, since a key named **Contoso-O365EX-NA-VaultA1-Key001** already exists in the **Contoso-O365EX-NA-VaultA1** vault, a new key version will be created. The operation adds a new key version. This operation preserves the previous key versions in the key's version history, so that data previously encrypted with that key can still be decrypted. Once you have completed rolling any key that is associated with a DEP, you must then run an additional cmdlet to ensure Customer Key begins using the new key.</span></span> 
  
#### <a name="enable-exchange-online-and-skype-for-business-to-use-a-new-key-after-you-roll-or-rotate-keys-in-azure-key-vault"></a><span data-ttu-id="9ed6d-484">Abilitazione di Exchange Online e Skype for business per l'utilizzo di una nuova chiave dopo aver eseguito il rollforward o la rotazione delle chiavi in Azure Key Vault</span><span class="sxs-lookup"><span data-stu-id="9ed6d-484">Enable Exchange Online and Skype for Business to use a new key after you roll or rotate keys in Azure Key Vault</span></span>

<span data-ttu-id="9ed6d-485">Quando si esegue il rollback delle chiavi del Vault Key di Azure associate a una funzionalità di protezione dei comandi utilizzata con Exchange Online e Skype for business, è necessario eseguire il comando seguente per aggiornare la funzionalità DEP e abilitare Office 365 per iniziare a utilizzare la nuova chiave.</span><span class="sxs-lookup"><span data-stu-id="9ed6d-485">When you roll either of the Azure Key Vault keys associated with a DEP used with Exchange Online and Skype for Business, you must run the following command to update the DEP and enable Office 365 to start using the new key.</span></span>
  
<span data-ttu-id="9ed6d-486">Per indicare alla chiave del cliente di utilizzare la nuova chiave per crittografare le cassette postali in Office 365, eseguire il cmdlet Set-DataEncryptionPolicy come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="9ed6d-486">To instruct Customer Key to use the new key to encrypt mailboxes in Office 365 run the Set-DataEncryptionPolicy cmdlet as follows:</span></span>
  
```
Set-DataEncryptionPolicy <policyname> -Refresh 
```

<span data-ttu-id="9ed6d-p175">Entro 48 ore, le cassette postali attive crittografate con questo criterio diventeranno associate alla chiave aggiornata. Utilizzare la procedura descritta in [determinare la funzionalità DEP assegnata a una cassetta postale](controlling-your-data-using-customer-key.md#DeterminemailboxDEP) per controllare il valore della proprietà DataEncryptionPolicyID per la cassetta postale. Il valore di questa proprietà verrà modificato dopo l'applicazione della chiave aggiornata.</span><span class="sxs-lookup"><span data-stu-id="9ed6d-p175">Within 48 hours, the active mailboxes encrypted using this policy will become associated with the updated key. Use the steps in [Determine the DEP assigned to a mailbox](controlling-your-data-using-customer-key.md#DeterminemailboxDEP) to check the value for the DataEncryptionPolicyID property for the mailbox. The value for this property will change once the updated key has been applied.</span></span> 
  
#### <a name="enable-sharepoint-online-and-onedrive-for-business-to-use-a-new-key-after-you-roll-or-rotate-keys-in-azure-key-vault"></a><span data-ttu-id="9ed6d-490">Abilitazione di SharePoint Online e OneDrive for business per l'utilizzo di una nuova chiave dopo aver eseguito il rollforward o la rotazione delle chiavi in Azure Key Vault</span><span class="sxs-lookup"><span data-stu-id="9ed6d-490">Enable SharePoint Online and OneDrive for Business to use a new key after you roll or rotate keys in Azure Key Vault</span></span>

<span data-ttu-id="9ed6d-491">Quando si esegue il rollback delle chiavi del Vault Key di Azure associate a una funzionalità di protezione da utilizzare con SharePoint Online e OneDrive for business, è necessario eseguire il cmdlet [Update-SPODataEncryptionPolicy](https://technet.microsoft.com/library/mt843948.aspx) per aggiornare la funzionalità DEP e abilitare Office 365 per iniziare a utilizzare la nuova chiave.</span><span class="sxs-lookup"><span data-stu-id="9ed6d-491">When you roll either of the Azure Key Vault keys associated with a DEP used with SharePoint Online and OneDrive for Business, you must run the [Update-SPODataEncryptionPolicy](https://technet.microsoft.com/library/mt843948.aspx) cmdlet to update the DEP and enable Office 365 to start using the new key.</span></span> 
  
```
Update-SPODataEncryptionPolicy -Identity <SPOAdminSiteUrl> -KeyVaultName <ReplacementKeyVaultName> -KeyName <ReplacementKeyName> -KeyVersion <ReplacementKeyVersion> -KeyType <Primary | Secondary>
```

<span data-ttu-id="9ed6d-p176">Verrà avviata l'operazione di rollforward delle chiavi per SharePoint Online e OneDrive for business. Questa azione non è immediata. Per visualizzare lo stato dell'operazione di rollforward delle chiavi, eseguire il cmdlet Get-SPODataEncryptionPolicy nel modo riportato di seguito:</span><span class="sxs-lookup"><span data-stu-id="9ed6d-p176">This will start the key roll operation for SharePoint Online and OneDrive for Business. This action is not immediate. To see the progress of the key roll operation, run the Get-SPODataEncryptionPolicy cmdlet as follows:</span></span>
  
```
Get-SPODataEncryptionPolicy -Identity <SPOAdminSiteUrl>
```

### <a name="manage-key-vault-permissions"></a><span data-ttu-id="9ed6d-495">Gestire le autorizzazioni del Vault Key</span><span class="sxs-lookup"><span data-stu-id="9ed6d-495">Manage key vault permissions</span></span>
<span data-ttu-id="9ed6d-496"><a name="Managekeyvaultperms"> </a></span><span class="sxs-lookup"><span data-stu-id="9ed6d-496"></span></span>

<span data-ttu-id="9ed6d-p177">Sono disponibili diversi cmdlet che consentono di visualizzare e, se necessario, di rimuovere le autorizzazioni chiave del Vault. Potrebbe essere necessario rimuovere le autorizzazioni, ad esempio quando un dipendente lascia il team.</span><span class="sxs-lookup"><span data-stu-id="9ed6d-p177">Several cmdlets are available that enable you to view and, if necessary, remove key vault permissions. You might need to remove permissions, for example, when an employee leaves the team.</span></span>
  
<span data-ttu-id="9ed6d-499">Per visualizzare le autorizzazioni per il Vault chiave, eseguire il cmdlet Get-AzureRmKeyVault:</span><span class="sxs-lookup"><span data-stu-id="9ed6d-499">To view key vault permissions, run the Get-AzureRmKeyVault cmdlet:</span></span>
  
```
Get-AzureRmKeyVault -VaultName <vaultname>
```

<span data-ttu-id="9ed6d-500">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="9ed6d-500">For example:</span></span>
  
```
Get-AzureRmKeyVault -VaultName Contoso-O365EX-NA-VaultA1
```

<span data-ttu-id="9ed6d-501">Per rimuovere le autorizzazioni di un amministratore, eseguire il cmdlet Remove-AzureRmKeyVaultAccessPolicy:</span><span class="sxs-lookup"><span data-stu-id="9ed6d-501">To remove an administrator's permissions, run the Remove-AzureRmKeyVaultAccessPolicy cmdlet:</span></span>
  
```
Remove-AzureRmKeyVaultAccessPolicy -VaultName <vaultname> 
-UserPrincipalName <UPN of user>
```

<span data-ttu-id="9ed6d-502">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="9ed6d-502">For example:</span></span>
  
```
Remove-AzureRmKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 
-UserPrincipalName alice@contoso.com
```

### <a name="determine-the-dep-assigned-to-a-mailbox"></a><span data-ttu-id="9ed6d-503">Determinare la funzionalità DEP assegnata a una cassetta postale</span><span class="sxs-lookup"><span data-stu-id="9ed6d-503">Determine the DEP assigned to a mailbox</span></span>
<span data-ttu-id="9ed6d-504"><a name="DeterminemailboxDEP"> </a></span><span class="sxs-lookup"><span data-stu-id="9ed6d-504"></span></span>

<span data-ttu-id="9ed6d-p178">Per determinare la funzionalità DEP assegnata a una cassetta postale, utilizzare il cmdlet Get-MailboxStatistics. Il cmdlet restituisce un identificatore univoco (GUID).</span><span class="sxs-lookup"><span data-stu-id="9ed6d-p178">To determine the DEP assigned to a mailbox, use the Get-MailboxStatistics cmdlet. The cmdlet returns a unique identifier (GUID).</span></span>
  
```
Get-MailboxStatistics -Identity <GeneralMailboxOrMailUserIdParameter> | fl DataEncryptionPolicyID
```

<span data-ttu-id="9ed6d-p179">Dove *GeneralMailboxOrMailUserIdParameter* specifica una cassetta postale. Per ulteriori informazioni sul cmdlet Get-MailboxStatistics, vedere [Get-MailboxStatistics](https://technet.microsoft.com/library/bb124612%28v=exchg.160%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="9ed6d-p179">Where *GeneralMailboxOrMailUserIdParameter* specifies a mailbox. For more information about the Get-MailboxStatistics cmdlet, see [Get-MailboxStatistics](https://technet.microsoft.com/library/bb124612%28v=exchg.160%29.aspx).</span></span>
  
<span data-ttu-id="9ed6d-509">Utilizzare il GUID per individuare il nome descrittivo della funzionalità DEP a cui è assegnata la cassetta postale eseguendo il cmdlet seguente.</span><span class="sxs-lookup"><span data-stu-id="9ed6d-509">Use the GUID to find out the friendly name of the DEP to which the mailbox is assigned by running the following cmdlet.</span></span>
  
```
Get-DataEncryptionPolicy <GUID>
```

<span data-ttu-id="9ed6d-510">Dove *GUID* è il GUID restituito dal cmdlet Get-MailboxStatistics nel passaggio precedente.</span><span class="sxs-lookup"><span data-stu-id="9ed6d-510">Where *GUID* is the GUID returned by the Get-MailboxStatistics cmdlet in the previous step.</span></span> 
  

