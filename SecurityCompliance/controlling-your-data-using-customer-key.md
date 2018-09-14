---
title: Controllare i dati in Office 365 con Customer Key
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 8/1/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: f2cd475a-e592-46cf-80a3-1bfb0fa17697
description: Informazioni su come configurare chiave cliente per Office 365 per Exchange Online, Skype per Business, SharePoint Online e OneDrive for Business. Con clienti chiave, controllare le chiavi di crittografia della propria organizzazione e quindi configurare Office 365 per utilizzarli per crittografare i dati statici nei Data Center di Microsoft.
ms.openlocfilehash: 3eeccd03b89aa5a79ceba536d3f13c7a881b6ca7
ms.sourcegitcommit: ef0bb05a0cf7974ae5083c7551ce3fe4ab7a9544
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/13/2018
ms.locfileid: "23965610"
---
# <a name="controlling-your-data-in-office-365-using-customer-key"></a><span data-ttu-id="b0f19-104">Controllare i dati in Office 365 con Customer Key</span><span class="sxs-lookup"><span data-stu-id="b0f19-104">Controlling your data in Office 365 using Customer Key</span></span>

<span data-ttu-id="b0f19-p102">Con clienti chiave, controllare le chiavi di crittografia della propria organizzazione e quindi configurare Office 365 per utilizzarli per crittografare i dati statici nei centri dati di Microsoft. Dati statici includono i dati da Exchange Online e Skype for Business archiviati nelle cassette postali e i file archiviati in SharePoint Online e OneDrive for Business.</span><span class="sxs-lookup"><span data-stu-id="b0f19-p102">With Customer Key, you control your organization's encryption keys and then configure Office 365 to use them to encrypt your data at rest in Microsoft's data centers. Data at rest includes data from Exchange Online and Skype for Business that is stored in mailboxes and files that are stored in SharePoint Online and OneDrive for Business.</span></span>
  
<span data-ttu-id="b0f19-p103">Prima di poter utilizzare chiave cliente per Office 365, è necessario configurare Azure. In questo argomento vengono descritti i passaggi da eseguire per creare e configurare le risorse necessarie Azure e quindi vengono fornite le procedure per la configurazione di chiave cliente in Office 365. Dopo aver eseguito il programma di installazione Azure, determinare quale criterio e conseguenza, le chiavi da assegnare alle cassette postali e i file nella propria organizzazione. Le cassette postali e i file per cui non si assegna un criterio utilizzerà i criteri di crittografia che vengono controllati e gestiti da Microsoft. Per ulteriori informazioni sulla chiave cliente o per una panoramica generale, vedere il [Codice cliente per Office 365 FAQ](service-encryption-with-customer-key-faq.md).</span><span class="sxs-lookup"><span data-stu-id="b0f19-p103">You must set up Azure before you can use Customer Key for Office 365. This topic describes the steps you need to follow to create and configure the required Azure resources and then provides the steps for setting up Customer Key in Office 365. After you have completed Azure setup, you determine which policy, and therefore, which keys, to assign to mailboxes and files in your organization. Mailboxes and files for which you don't assign a policy will use encryption policies that are controlled and managed by Microsoft. For more information about Customer Key, or for a general overview, see the [Customer Key for Office 365 FAQ](service-encryption-with-customer-key-faq.md).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="b0f19-p104">Si consiglia attenersi alle procedure consigliate in questo argomento. Questi sono definiti come **Suggerimento** e **importante**. Consente di chiave cliente di controllare le chiavi di crittografia principale il cui ambito è possibile specificarne fino a tutta l'organizzazione. Ciò significa che commessi con queste sequenze di tasti possono avere un impatto ampio e potrebbero causare interruzioni del servizio o la perdita definitiva di dati.</span><span class="sxs-lookup"><span data-stu-id="b0f19-p104">We strongly recommend that you follow the best practices in this topic. These are called out as **TIP** and **IMPORTANT**. Customer Key gives you control over root encryption keys whose scope can be as large as your entire organization. This means that mistakes made with these keys can have a broad impact and may result in service interruptions or irrevocable loss of your data.</span></span> 
  
## <a name="before-you-begin-setting-up-customer-key"></a><span data-ttu-id="b0f19-116">Prima di iniziare la configurazione di chiave cliente</span><span class="sxs-lookup"><span data-stu-id="b0f19-116">Before you begin setting up Customer Key</span></span>
<span data-ttu-id="b0f19-117"><a name="Beforeyoustart"> </a></span><span class="sxs-lookup"><span data-stu-id="b0f19-117"></span></span>

<span data-ttu-id="b0f19-p105">Prima di iniziare, assicurarsi di avere licenze appropriato per l'organizzazione. Chiave cliente in Office 365 è disponibile in Office 365 E5 o SKU di conformità avanzate.</span><span class="sxs-lookup"><span data-stu-id="b0f19-p105">Before you get started, be sure you have the appropriate licensing for your organization. Customer Key in Office 365 is offered in Office 365 E5 or the Advanced Compliance SKU.</span></span>
  
<span data-ttu-id="b0f19-p106">Per comprendere i concetti e le procedure in questo argomento, quindi, è consigliabile consultare la documentazione di [Azure chiave cassaforte](https://azure.microsoft.com/en-us/documentation/services/key-vault/) . Inoltre, acquisire familiarità con i termini utilizzati in Azure, ad esempio [tenant](https://msdn.microsoft.com/library/azure/jj573650.aspx#BKMK_WhatIsAnAzureADTenant).</span><span class="sxs-lookup"><span data-stu-id="b0f19-p106">Then, to understand the concepts and procedures in this topic, you should review the [Azure Key Vault](https://azure.microsoft.com/en-us/documentation/services/key-vault/) documentation. Also, become familiar with the terms used in Azure, for example, [tenant](https://msdn.microsoft.com/library/azure/jj573650.aspx#BKMK_WhatIsAnAzureADTenant).</span></span>
  
<span data-ttu-id="b0f19-122">Per inviare commenti e suggerimenti sulla chiave dei clienti, inclusa la documentazione, inviare idee, suggerimenti e prospettive a customerkeyfeedback@microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="b0f19-122">To provide feedback on Customer Key, including the documentation, send your ideas, suggestions and perspectives to customerkeyfeedback@microsoft.com.</span></span>
  
## <a name="overview-of-setting-up-customer-key-for-office-365"></a><span data-ttu-id="b0f19-123">Panoramica dell'installazione di chiave cliente per Office 365</span><span class="sxs-lookup"><span data-stu-id="b0f19-123">Overview of setting up Customer Key for Office 365</span></span>
<span data-ttu-id="b0f19-124"><a name="Overview"> </a></span><span class="sxs-lookup"><span data-stu-id="b0f19-124"></span></span>

<span data-ttu-id="b0f19-p107">Per configurare la chiave cliente verranno completate queste attività. Il resto di questo argomento vengono fornite istruzioni dettagliate per ogni attività o collegamenti fuori a ulteriori informazioni per ogni passaggio del processo.</span><span class="sxs-lookup"><span data-stu-id="b0f19-p107">To set up Customer Key you will complete these tasks. The rest of this topic provides detailed instructions for each task, or links out to more information for each step in the process.</span></span>
  
<span data-ttu-id="b0f19-127">**In Azure e FastTrack Microsoft:**</span><span class="sxs-lookup"><span data-stu-id="b0f19-127">**In Azure and Microsoft FastTrack:**</span></span>
  
<span data-ttu-id="b0f19-p108">Completare la maggior parte di queste attività tramite la connessione in remoto a Azure PowerShell. Per ottenere risultati migliori, utilizzare la versione 4.4.0 o versione successiva di Azure PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b0f19-p108">You will complete most of these tasks by remotely connecting to Azure PowerShell. For best results, use version 4.4.0 or later of Azure PowerShell.</span></span>
  
- [<span data-ttu-id="b0f19-130">Creare due nuove sottoscrizioni di Azure</span><span class="sxs-lookup"><span data-stu-id="b0f19-130">Create two new Azure subscriptions</span></span>](controlling-your-data-using-customer-key.md#Create2newsubs)
    
- [<span data-ttu-id="b0f19-131">Registrare le sottoscrizioni Azure per l'utilizzo di un periodo di conservazione obbligatoria</span><span class="sxs-lookup"><span data-stu-id="b0f19-131">Register Azure subscriptions to use a mandatory retention period</span></span>](controlling-your-data-using-customer-key.md#RegisterSubsforMRP)
    
    <span data-ttu-id="b0f19-132">La registrazione può richiedere da una a cinque giorni lavorativi.</span><span class="sxs-lookup"><span data-stu-id="b0f19-132">Registration can take from one to five business days.</span></span>
    
- [<span data-ttu-id="b0f19-133">Inviare una richiesta per attivare codice cliente per Office 365</span><span class="sxs-lookup"><span data-stu-id="b0f19-133">Submit a request to activate Customer Key for Office 365</span></span>](controlling-your-data-using-customer-key.md#FastTrack)
    
    <span data-ttu-id="b0f19-p109">Dopo aver creato le due nuove sottoscrizioni Azure, è necessario inviare la richiesta di offerta cliente chiave appropriata per il completamento di un modulo web è ospitato nel portale dei Microsoft FastTrack. Il team FastTrack non fornisce assistenza clienti chiave. Office utilizza semplicemente il portale FastTrack per consentono di inviare il modulo e consentiranno di tenere traccia delle offerte pertinenti per clienti chiave.</span><span class="sxs-lookup"><span data-stu-id="b0f19-p109">Once you've created the two new Azure subscriptions, you'll need to submit the appropriate Customer Key offer request by completing a web form that is hosted in the Microsoft FastTrack portal. The FastTrack team doesn't provide assistance with Customer Key. Office simply uses the FastTrack portal to allow you to submit the form and to help us track the relevant offers for Customer Key.</span></span>
  
<span data-ttu-id="b0f19-p110">Dopo l'invio di una proposta di chiave cliente, Microsoft esamina la richiesta e invia una notifica quando è possibile procedere con il resto le attività di configurazione. Questo processo può richiedere fino a cinque giorni lavorativi.</span><span class="sxs-lookup"><span data-stu-id="b0f19-p110">Once you have submitted a Customer Key offer, Microsoft reviews your request and notifies you when you can proceed with the rest of the setup tasks. This process can take up to five business days.</span></span>
    
- [<span data-ttu-id="b0f19-139">Creare un premium Azure chiave cassaforte in ogni sottoscrizione</span><span class="sxs-lookup"><span data-stu-id="b0f19-139">Create a premium Azure Key Vault in each subscription</span></span>](controlling-your-data-using-customer-key.md#CreateKeyVault)
    
- [<span data-ttu-id="b0f19-140">Assegnare le autorizzazioni per ogni archivio chiave</span><span class="sxs-lookup"><span data-stu-id="b0f19-140">Assign permissions to each key vault</span></span>](controlling-your-data-using-customer-key.md#KeyVaultPerms)
    
- [<span data-ttu-id="b0f19-141">Abilitare questa impostazione e quindi confermare l'eliminazione temporanea in archivi il chiavi</span><span class="sxs-lookup"><span data-stu-id="b0f19-141">Enable and then confirm soft delete on your key vaults</span></span>](controlling-your-data-using-customer-key.md#SoftDelete)
    
- [<span data-ttu-id="b0f19-142">Aggiungere una chiave per ogni archivio chiave sia per la creazione o l'importazione di una chiave</span><span class="sxs-lookup"><span data-stu-id="b0f19-142">Add a key to each key vault either by creating or importing a key</span></span>](controlling-your-data-using-customer-key.md#AddKeystoKeyVault)
    
- [<span data-ttu-id="b0f19-143">Selezionare il livello di ripristino delle chiavi</span><span class="sxs-lookup"><span data-stu-id="b0f19-143">Check the recovery level of your keys</span></span>](controlling-your-data-using-customer-key.md#CheckKeyRecoveryLevel)
    
- [<span data-ttu-id="b0f19-144">Backup cassaforte chiave Azure</span><span class="sxs-lookup"><span data-stu-id="b0f19-144">Backup Azure Key Vault</span></span>](controlling-your-data-using-customer-key.md#BackupAzureKeyVaultkeys)
    
- [<span data-ttu-id="b0f19-145">Verificare le impostazioni di configurazione di Azure chiave cassaforte</span><span class="sxs-lookup"><span data-stu-id="b0f19-145">Validate Azure Key Vault configuration settings</span></span>](controlling-your-data-using-customer-key.md#Validateconfiguration)
    
- [<span data-ttu-id="b0f19-146">Ottenere l'URI per ogni tasto di Azure chiave cassaforte</span><span class="sxs-lookup"><span data-stu-id="b0f19-146">Obtain the URI for each Azure Key Vault key</span></span>](controlling-your-data-using-customer-key.md#GetKeyURI)
    
<span data-ttu-id="b0f19-147">**In Office 365:**</span><span class="sxs-lookup"><span data-stu-id="b0f19-147">**In Office 365:**</span></span>
  
<span data-ttu-id="b0f19-148">Exchange Online e Skype for Business:</span><span class="sxs-lookup"><span data-stu-id="b0f19-148">Exchange Online and Skype for Business:</span></span>
  
- [<span data-ttu-id="b0f19-149">Creare un criterio di crittografia dei dati (DEP) per l'utilizzo con Exchange Online e Skype per le aziende</span><span class="sxs-lookup"><span data-stu-id="b0f19-149">Create a data encryption policy (DEP) for use with Exchange Online and Skype for Business</span></span>](controlling-your-data-using-customer-key.md#CreateDEP4EXOSkype)
    
- [<span data-ttu-id="b0f19-150">Assegnare una protezione esecuzione programmi a una cassetta postale</span><span class="sxs-lookup"><span data-stu-id="b0f19-150">Assign a DEP to a mailbox</span></span>](controlling-your-data-using-customer-key.md#assignDEPtomailbox)
    
- [<span data-ttu-id="b0f19-151">Convalidare la crittografia delle cassette postali</span><span class="sxs-lookup"><span data-stu-id="b0f19-151">Validate mailbox encryption</span></span>](controlling-your-data-using-customer-key.md#validatemailboxencryption)
    
<span data-ttu-id="b0f19-152">SharePoint Online e OneDrive for Business:</span><span class="sxs-lookup"><span data-stu-id="b0f19-152">SharePoint Online and OneDrive for Business:</span></span>
  
- [<span data-ttu-id="b0f19-153">Creare un criterio di crittografia dei dati (DEP) per ogni SharePoint Online e OneDrive per Business geo</span><span class="sxs-lookup"><span data-stu-id="b0f19-153">Create a data encryption policy (DEP) for each SharePoint Online and OneDrive for Business geo</span></span>](controlling-your-data-using-customer-key.md#CreateDEP4SPOODfB)
    
- [<span data-ttu-id="b0f19-154">Convalidare la crittografia del gruppo di siti, siti dei Team e OneDrive for Business</span><span class="sxs-lookup"><span data-stu-id="b0f19-154">Validate encryption of Group Sites, Team Sites, and OneDrive for Business</span></span>](controlling-your-data-using-customer-key.md#validateencryptionSPO)
    
## <a name="complete-tasks-in-azure-key-vault-and-microsoft-fasttrack-for-customer-key"></a><span data-ttu-id="b0f19-155">Eseguire le attività in Azure chiave cassaforte e Microsoft FastTrack chiave cliente</span><span class="sxs-lookup"><span data-stu-id="b0f19-155">Complete tasks in Azure Key Vault and Microsoft FastTrack for Customer Key</span></span>
<span data-ttu-id="b0f19-156"><a name="AzureSteps"> </a></span><span class="sxs-lookup"><span data-stu-id="b0f19-156"></span></span>

<span data-ttu-id="b0f19-p111">Completare queste attività in Azure chiave cassaforte per impostare la chiave di clienti per Office 365. È necessario completare la procedura seguente indipendentemente dal fatto che si intende configurare chiave cliente per Exchange Online e Skype per le aziende o SharePoint Online e OneDrive for Business o per tutti i servizi supportati in Office 365.</span><span class="sxs-lookup"><span data-stu-id="b0f19-p111">Complete these tasks in Azure Key Vault in order to set up Customer Key for Office 365. You will need to complete these steps regardless of whether you intend to set up Customer Key for Exchange Online and Skype for Business or SharePoint Online and OneDrive for Business or for all supported services in Office 365.</span></span>
  
### <a name="create-two-new-azure-subscriptions"></a><span data-ttu-id="b0f19-159">Creare due nuove sottoscrizioni di Azure</span><span class="sxs-lookup"><span data-stu-id="b0f19-159">Create two new Azure subscriptions</span></span>
<span data-ttu-id="b0f19-160"><a name="Create2newsubs"> </a></span><span class="sxs-lookup"><span data-stu-id="b0f19-160"></span></span>

<span data-ttu-id="b0f19-p112">Due sottoscrizioni Azure sono necessari per clienti chiave. Come procedura consigliata, si consiglia di creare nuove sottoscrizioni Azure per l'utilizzo con chiave cliente. Codici tasto cassaforte Azure possono essere autorizzati solo per le applicazioni nello stesso tenant di Azure Active Directory (AAD), è necessario creare le nuove sottoscrizioni utilizzando stesso tenant di Azure Active Directory utilizzato con l'organizzazione Office 365 in cui verrà assegnato il DEPs. Ad esempio, utilizzando l'account di lavoro o della scuola con privilegi di amministratore globale dell'organizzazione Office 365. Per ulteriori informazioni, vedere [iscrizione a Azure come un'organizzazione](https://azure.microsoft.com/en-us/documentation/articles/sign-up-organization/).</span><span class="sxs-lookup"><span data-stu-id="b0f19-p112">Two Azure subscriptions are required for Customer Key. As a best practice, Microsoft recommends that you create new Azure subscriptions for use with Customer Key. Azure Key Vault keys can only be authorized for applications in the same Azure Active Directory (AAD) tenant, you must create the new subscriptions using the same Azure AD tenant used with your Office 365 organization where the DEPs will be assigned. For example, using your work or school account that has global administrator privileges in your Office 365 organization. For detailed steps, see [Sign up for Azure as an organization](https://azure.microsoft.com/en-us/documentation/articles/sign-up-organization/).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="b0f19-p113">Chiave cliente richiede due chiavi per ogni criterio di crittografia dei dati (DEP). Per ottenere questo risultato, è necessario creare due sottoscrizioni di Azure. Per una protezione ottimale, è consigliabile avere separati membri della propria organizzazione di configurare una chiave in ogni sottoscrizione. Inoltre, le sottoscrizioni di Azure devono essere utilizzati solo per amministrare le chiavi di crittografia per Office 365. Consente di proteggere l'organizzazione nel caso in cui un l'operatore eliminato accidentalmente, intenzionalmente o manomettere o in caso contrario mismanages i tasti di cui sono responsabili.</span><span class="sxs-lookup"><span data-stu-id="b0f19-p113">Customer Key requires two keys for each data encryption policy (DEP). In order to achieve this, you must create two Azure subscriptions. As a best practice, Microsoft recommends that you have separate members of your organization configure one key in each subscription. In addition, these Azure subscriptions should only be used to administer encryption keys for Office 365. This protects your organization in case one of your operators accidentally, intentionally, or maliciously deletes or otherwise mismanages the keys for which they are responsible. </span></span><br/> <span data-ttu-id="b0f19-p114">È consigliabile configurare nuove sottoscrizioni Azure unicamente utilizzati per la gestione delle risorse di Azure chiave cassaforte per l'utilizzo con clienti chiave. Non esiste alcun limite pratico al numero di sottoscrizioni Azure che è possibile creare per l'organizzazione. Seguendo le procedure consigliate riduce al minimo l'impatto delle risorse umane errore durante il supporto per gestire le risorse utilizzate dalla chiave cliente.</span><span class="sxs-lookup"><span data-stu-id="b0f19-p114">We recommend that you set up new Azure subscriptions that are solely used for managing Azure Key Vault resources for use with Customer Key. There is no practical limit to the number of Azure subscriptions that you can create for your organization. Following these best practices will minimize the impact of human error while helping to manage the resources used by Customer Key.</span></span> 
  
### <a name="submit-a-request-to-activate-customer-key-for-office-365"></a><span data-ttu-id="b0f19-174">Inviare una richiesta per attivare codice cliente per Office 365</span><span class="sxs-lookup"><span data-stu-id="b0f19-174">Submit a request to activate Customer Key for Office 365</span></span>
<span data-ttu-id="b0f19-175"><a name="FastTrack"> </a></span><span class="sxs-lookup"><span data-stu-id="b0f19-175"></span></span>

<span data-ttu-id="b0f19-p115">Dopo aver completato i passaggi Azure, è necessario inviare una richiesta di offerta nel [portale dei Microsoft FastTrack](https://fasttrack.microsoft.com/). Dopo avere inviato una richiesta tramite il portale web FastTrack, Microsoft consente di verificare le Azure chiave archivio dati e contatto informazioni di configurazione specificate. Le selezioni eseguite nel formato offerta relativa autorizzati responsabili dell'organizzazione è necessario per il completamento della registrazione chiave cliente e non critici. I responsabili dell'organizzazione selezionato nel modulo sarà utilizzato per garantire l'autenticità del qualsiasi richiesta di revocare e distruggere tutti i tasti utilizzati con un criterio di crittografia dei dati Customer chiave. È necessario eseguire questo passaggio una volta per attivare codice cliente per Exchange Online e Skype per la copertura dell'azienda e una seconda volta attivare codice cliente per SharePoint Online e OneDrive for Business.</span><span class="sxs-lookup"><span data-stu-id="b0f19-p115">Once you've completed the Azure steps, you'll need to submit an offer request in the [Microsoft FastTrack portal](https://fasttrack.microsoft.com/). Once you have submitted a request through the FastTrack web portal, Microsoft verifies the Azure Key Vault configuration data and contact information you provided. The selections that you make in the offer form regarding the authorized officers of your organization is critical and necessary for completion of Customer Key registration. The officers of your organization that you select in the form will be the used to ensure the authenticity of any request to revoke and destroy all keys used with a Customer Key data encryption policy. You'll need to do this step once to activate Customer Key for Exchange Online and Skype for Business coverage and a second time to activate Customer Key for SharePoint Online and OneDrive for Business.</span></span>
  
<span data-ttu-id="b0f19-181">Per inviare un'offerta per attivare il codice cliente, completare la procedura seguente:</span><span class="sxs-lookup"><span data-stu-id="b0f19-181">To submit an offer to activate Customer Key, complete these steps:</span></span>
  
1. <span data-ttu-id="b0f19-182">Utilizzo di un ufficio o della scuola dell'account che disponga delle autorizzazioni di amministratore globale dell'organizzazione Office 365, eseguire l'accesso al [portale dei Microsoft FastTrack](https://fasttrack.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="b0f19-182">Using a work or school account that has global administrator permissions in your Office 365 organization, log in to the [Microsoft FastTrack portal](https://fasttrack.microsoft.com/).</span></span>
    
2. <span data-ttu-id="b0f19-183">Dopo aver eseguito, individuare il **Dashboard**.</span><span class="sxs-lookup"><span data-stu-id="b0f19-183">Once you're logged in, browse to the **Dashboard**.</span></span>
    
3. <span data-ttu-id="b0f19-184">Scegliere **offre**ed esaminare l'elenco delle offerte in corso.</span><span class="sxs-lookup"><span data-stu-id="b0f19-184">Choose **Offers**, and review the list of current offers.</span></span>
    
4. <span data-ttu-id="b0f19-185">Scegliere **Ulteriori informazioni** per la proposta in base alle esigenze:</span><span class="sxs-lookup"><span data-stu-id="b0f19-185">Choose **Learn More** for the offer that applies to you:</span></span> 
    
  - <span data-ttu-id="b0f19-186">**Exchange Online e Skype per le aziende:** Scegliere **Ulteriori informazioni** su offerta **Cliente chiave di Exchange** .</span><span class="sxs-lookup"><span data-stu-id="b0f19-186">**Exchange Online and Skype for Business:** Choose **Learn More** on the **Customer Key for Exchange** offer.</span></span> 
    
  - <span data-ttu-id="b0f19-187">**SharePoint Online e OneDrive for Business:** Scelta di **Informazioni su più** nei offerta **Cliente chiave per SharePoint e OneDrive for Business** .</span><span class="sxs-lookup"><span data-stu-id="b0f19-187">**SharePoint Online and OneDrive for Business:** Chose **Learn More** on the **Customer Key for SharePoint and OneDrive for Business** offer.</span></span> 
    
5. <span data-ttu-id="b0f19-188">Nella pagina **sono disponibili ulteriori informazioni** , scegliere **Crea richiesta**.</span><span class="sxs-lookup"><span data-stu-id="b0f19-188">On the **Offer details** page, choose **Create Request**.</span></span>
    
6. <span data-ttu-id="b0f19-p116">Compilare tutti i dettagli applicabili e le informazioni richieste nella maschera offerta. Prestare particolare attenzione alle selezioni eseguite per i responsabili dell'organizzazione si desidera autorizzare per approvare l'eliminazione definitiva e irreversibile delle chiavi di crittografia e dati. Dopo aver completato il modulo, scegliere **Invia**.</span><span class="sxs-lookup"><span data-stu-id="b0f19-p116">Fill out all applicable details and requested information on the offer form. Pay particular attention to your selections for which officers of your organization you want to authorize to approve the permanent and irreversible destruction of encryption keys and data. Once you've completed the form, choose **Submit**.</span></span>
    
    <span data-ttu-id="b0f19-192">Questo processo può richiedere fino a cinque giorni lavorativi dopo che Microsoft informato della richiesta.</span><span class="sxs-lookup"><span data-stu-id="b0f19-192">This process can take up to five business days once Microsoft has been notified of your request.</span></span>
    
7. <span data-ttu-id="b0f19-193">Continuare semplicemente la sezione periodo conservazione obbligatoria riportata di seguito.</span><span class="sxs-lookup"><span data-stu-id="b0f19-193">Continue on to the mandatory retention period section below.</span></span>
    
### <a name="register-azure-subscriptions-to-use-a-mandatory-retention-period"></a><span data-ttu-id="b0f19-194">Registrare le sottoscrizioni Azure per l'utilizzo di un periodo di conservazione obbligatoria</span><span class="sxs-lookup"><span data-stu-id="b0f19-194">Register Azure subscriptions to use a mandatory retention period</span></span>
<span data-ttu-id="b0f19-195"><a name="RegisterSubsforMRP"> </a></span><span class="sxs-lookup"><span data-stu-id="b0f19-195"></span></span>

<span data-ttu-id="b0f19-p117">Perdita temporanea o permanente radice delle chiavi di crittografia può essere molto eccesso o persino irreversibili all'operazione di servizio e può causare la perdita di dati. Per questo motivo, le risorse utilizzate con clienti chiave richiedono la protezione avanzata. Tutte le risorse Azure utilizzati con chiave cliente offrono meccanismi di protezione oltre la configurazione predefinita. Sottoscrizioni Azure possono essere contrassegnate o registrate in modo che impedisce l'annullamento immediato e irrevocabile. Questa operazione viene definita la registrazione per un periodo di conservazione obbligatoria. I passaggi necessari per registrare le sottoscrizioni Azure per un periodo di conservazione obbligatoria richiedono la collaborazione con il team di Office 365. Questo processo può richiedere da una a cinque giorni lavorativi. In precedenza, questa è stata a volte indicata come "Non annullare".</span><span class="sxs-lookup"><span data-stu-id="b0f19-p117">The temporary or permanent loss of root encryption keys can be very disruptive or even catastrophic to service operation and can result in data loss. For this reason, the resources used with Customer Key require strong protection. All the Azure resources that are used with Customer Key offer protection mechanisms beyond the default configuration. Azure subscriptions can be tagged or registered in a way that will prevent immediate and irrevocable cancellation. This is referred to as registering for a mandatory retention period. The steps required to register Azure subscriptions for a mandatory retention period require collaboration with the Office 365 team. This process can take from one to five business days. Previously, this was sometimes referred to as "Do Not Cancel".</span></span>
  
<span data-ttu-id="b0f19-204">Prima di contattare il team di Office 365, è necessario eseguire la procedura seguente per ogni sottoscrizione Azure al cliente chiave:</span><span class="sxs-lookup"><span data-stu-id="b0f19-204">Before contacting the Office 365 team, you must perform the following steps for each Azure subscription that you use with Customer Key:</span></span>
  
1. <span data-ttu-id="b0f19-p118">Eseguire l'accesso alla sottoscrizione Azure con Azure PowerShell. Per ulteriori informazioni, vedere [eseguire l'accesso con Azure PowerShell](https://docs.microsoft.com/powershell/azure/authenticate-azureps?view=azurermps-4.3.1).</span><span class="sxs-lookup"><span data-stu-id="b0f19-p118">Log in to your Azure subscription with Azure PowerShell. For instructions, see [Log in with Azure PowerShell](https://docs.microsoft.com/powershell/azure/authenticate-azureps?view=azurermps-4.3.1).</span></span>
    
2. <span data-ttu-id="b0f19-207">Eseguire il cmdlet Register-AzureRmProviderFeature per registrare le sottoscrizioni per l'utilizzo di un periodo di conservazione obbligatoria.</span><span class="sxs-lookup"><span data-stu-id="b0f19-207">Run the Register-AzureRmProviderFeature cmdlet to register your subscriptions to use a mandatory retention period.</span></span>
    
  ```
  Register-AzureRmProviderFeature -FeatureName mandatoryRetentionPeriodEnabled -ProviderNamespace Microsoft.Resources
  ```

3. <span data-ttu-id="b0f19-p119">Contatta Microsoft per avere il processo di finalizzazione. Per SharePoint e OneDrive per team di Business, contattare [spock@microsoft.com](mailto:spock@microsoft.com). Per Exchange Online e Skype per le aziende, contattare [exock@microsoft.com](mailto:exock@microsoft.com). Service Level Agreement (SLA) per il completamento di questo processo è cinque giorni lavorativi dopo che Microsoft è stata una notifica (e verificato) che si sono registrati sottoscrizioni per l'utilizzo di un periodo di conservazione obbligatoria. Includere quanto segue nella posta elettronica:</span><span class="sxs-lookup"><span data-stu-id="b0f19-p119">Contact Microsoft to have the process finalized. For the SharePoint and OneDrive for Business team, contact [spock@microsoft.com](mailto:spock@microsoft.com). For Exchange Online and Skype for Business, contact [exock@microsoft.com](mailto:exock@microsoft.com). The Service Level Agreement (SLA) for completion of this process is five business days once Microsoft has been notified (and verified) that you have registered your subscriptions to use a mandatory retention period. Include the following in your email:</span></span>
    
    <span data-ttu-id="b0f19-213">**Oggetto**: chiave cliente per \< *nome di dominio completo del tenant*\></span><span class="sxs-lookup"><span data-stu-id="b0f19-213">**Subject**: Customer Key for \<*Your tenant's fully-qualified domain name*\></span></span> 
    
    <span data-ttu-id="b0f19-214">**Corpo**: ID di sottoscrizione per il quale si desidera avere il periodo finalizzata la conservazione obbligatoria.</span><span class="sxs-lookup"><span data-stu-id="b0f19-214">**Body**: Subscription IDs for which you want to have the mandatory retention period finalized.</span></span> 
    
4. <span data-ttu-id="b0f19-215">Dopo aver ricevuto una notifica da Microsoft che la registrazione è stata completata, verificare lo stato della registrazione del eseguendo il cmdlet Get-AzureRmProviderFeature come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="b0f19-215">Once you receive notification from Microsoft that registration is complete, verify the status of your registration by running the Get-AzureRmProviderFeature cmdlet as follows:</span></span>
    
  ```
  Get-AzureRmProviderFeature -ProviderNamespace Microsoft.Resources -FeatureName mandatoryRetentionPeriodEnabled
  ```

5. <span data-ttu-id="b0f19-216">Dopo aver verificato che la proprietà **State registrazione** dal cmdlet Get-AzureRmProviderFeature restituisce un valore di **Registered**, eseguire il comando seguente per completare il processo:</span><span class="sxs-lookup"><span data-stu-id="b0f19-216">After verifying that the **Registration State** property from the Get-AzureRmProviderFeature cmdlet returns a value of **Registered**, run the following command to complete the process:</span></span>
    
  ```
  Register-AzureRmResourceProvider -ProviderNamespace "Microsoft.KeyVault"
  ```

### <a name="create-a-premium-azure-key-vault-in-each-subscription"></a><span data-ttu-id="b0f19-217">Creare un premium Azure chiave cassaforte in ogni sottoscrizione</span><span class="sxs-lookup"><span data-stu-id="b0f19-217">Create a premium Azure Key Vault in each subscription</span></span>
<span data-ttu-id="b0f19-218"><a name="CreateKeyVault"> </a></span><span class="sxs-lookup"><span data-stu-id="b0f19-218"></span></span>

<span data-ttu-id="b0f19-219">I passaggi per creare una chiave cassaforte sono documentati nella [Guida introduttiva a Azure chiave cassaforte](https://azure.microsoft.com/documentation/articles/key-vault-get-started/), cui viene descritta la procedura di installazione e lanciare Azure PowerShell, la connessione alla sottoscrizione Azure, la creazione di un gruppo di risorse e la creazione di un archivio principali in cui gruppo di risorse.</span><span class="sxs-lookup"><span data-stu-id="b0f19-219">The steps to create a key vault are documented in [Getting Started with Azure Key Vault](https://azure.microsoft.com/documentation/articles/key-vault-get-started/), which guides you through installing and launching Azure PowerShell, connecting to your Azure subscription, creating a resource group, and creating a key vault in that resource group.</span></span>
  
<span data-ttu-id="b0f19-p120">Quando si crea un archivio di chiavi, è necessario scegliere un SKU: Standard o Premium. SKU Standard consente chiavi Azure chiave cassaforte a essere protetto con - non esiste alcuna protezione chiave Hardware Security Module (HSM) - il software e SKU Premium consente l'utilizzo di HSM per la protezione dei tasti cassaforte chiave. Chiave cliente accetta archivi chiavi che utilizzano uno SKU, anche se si consiglia di utilizzare solo la SKU Premium. Il costo delle operazioni con i tasti di entrambi i tipi è lo stesso, pertanto l'unica differenza dei costi è il costo al mese per ogni tasto protetti da modulo di sicurezza hardware. Per informazioni dettagliate, vedere [chiave cassaforte prezzo](https://azure.microsoft.com/pricing/details/key-vault/) .</span><span class="sxs-lookup"><span data-stu-id="b0f19-p120">When you create a key vault, you must choose a SKU: either Standard or Premium. The Standard SKU allows Azure Key Vault keys to be protected with software - there is no Hardware Security Module (HSM) key protection - and the Premium SKU allows the use of HSMs for protection of Key Vault keys. Customer Key accepts key vaults that use either SKU, though Microsoft strongly recommends that you use only the Premium SKU. The cost of operations with keys of either type is the same, so the only difference in cost is the cost per month for each HSM-protected key. See [Key Vault pricing](https://azure.microsoft.com/pricing/details/key-vault/) for details.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="b0f19-225">Utilizzare l'archivi chiavi Premium SKU e le chiavi protetti da modulo di sicurezza hardware per i dati di produzione e utilizzare solo gli archivi chiavi SKU Standard e le chiavi per scopi di test e convalida.</span><span class="sxs-lookup"><span data-stu-id="b0f19-225">Use the Premium SKU key vaults and HSM-protected keys for production data, and only use Standard SKU key vaults and keys for testing and validation purposes.</span></span> 
  
<span data-ttu-id="b0f19-p121">Per ogni servizio Office 365 con cui si utilizzerà chiave cliente, creare una chiave cassaforte in ognuna delle due sottoscrizioni Azure creata. Per Exchange Online e Skype per Business solo o SharePoint Online e OneDrive for Business solo, ad esempio, si creerà solo una coppia di archivi. Per abilitare la chiave cliente per Exchange Online e SharePoint Online, verrà creato due coppie di archivi di chiave.</span><span class="sxs-lookup"><span data-stu-id="b0f19-p121">For each Office 365 service with which you will use Customer Key, create a key vault in each of the two Azure subscriptions that you created. For example, for Exchange Online and Skype for Business only or SharePoint Online and OneDrive for Business only, you will create only one pair of vaults. To enable Customer Key for both Exchange Online and SharePoint Online, you will create two pairs of key vaults.</span></span>
  
<span data-ttu-id="b0f19-p122">Utilizzare una convenzione di denominazione per gli archivi di chiave che indica la modalità di utilizzo della protezione esecuzione programmi a cui associare gli archivi di. Vedere la sezione procedure consigliate di sotto di suggerimenti convenzione di denominazione.</span><span class="sxs-lookup"><span data-stu-id="b0f19-p122">Use a naming convention for key vaults that reflects the intended use of the DEP with which you will associate the vaults. See the Best Practices section below for naming convention recommendations.</span></span>
  
<span data-ttu-id="b0f19-p123">Creare un insieme di archivi per ogni criterio di crittografia dei dati separato, accoppiato. Per Exchange Online, l'ambito dei criteri di crittografia dei dati sia selezionata dall'utente quando si assegna il criterio cassetta postale di. Una cassetta postale può avere un solo criterio assegnato ed è possibile creare criteri fino a 50. SharePoint Online è l'ambito dei criteri di tutti i dati all'interno dell'organizzazione in aree geografiche o geo.</span><span class="sxs-lookup"><span data-stu-id="b0f19-p123">Create a separate, paired set of vaults for each data encryption policy. For Exchange Online, the scope of a data encryption policy is chosen by you when you assign the policy to mailbox. A mailbox can have only one policy assigned, and you can create up to fifty policies. For SharePoint Online the scope of a policy is all of the data within an organization in a geographic location, or geo.</span></span>
  
<span data-ttu-id="b0f19-p124">La creazione di archivi di chiave richiede anche la creazione di gruppi di risorse Azure, in quanto gli archivi di chiave necessario capacità di archiviazione (sebbene dimensioni molto piccole) e cassaforte chiave registrazione, se abilitato, genera inoltre dati memorizzati. Come procedura consigliata è consigliabile utilizzare amministratori diversi per gestire ogni gruppo di risorse con l'amministrazione allineato con il gruppo di amministratori che gestirà tutte le risorse correlate chiave cliente.</span><span class="sxs-lookup"><span data-stu-id="b0f19-p124">The creation of key vaults also requires the creation of Azure resource groups, since key vaults need storage capacity (though very small) and Key Vault logging, if enabled, also generates stored data. As a best practice Microsoft recommends using separate administrators to manage each resource group, with the administration aligned with the set of administrators that will manage all related Customer Key resources.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="b0f19-p125">Per ottimizzare la disponibilità, il chiavi archivi devono trovarsi in aree di raggiungere il servizio Office 365. Ad esempio, se l'organizzazione Exchange Online in Nord America, effettuare il chiavi archivi in Nord America. Se l'organizzazione Exchange Online in Europa, inserire il chiavi archivi in Europa.</span><span class="sxs-lookup"><span data-stu-id="b0f19-p125">To maximize availability, your key vaults should be in regions close to your Office 365 service. For example, if your Exchange Online organization is in North America, place your key vaults in North America. If your Exchange Online organization is in Europe, place your key vaults in Europe.</span></span><br/><span data-ttu-id="b0f19-p126">Utilizzare un prefisso comune per gli archivi di chiave e includere una voce di utilizzo e l'ambito dei tasti e cassaforte chiave (ad esempio, per il servizio Contoso SharePoint gli archivi di conterrà in Nord America, una coppia di nomi possibile è Contoso-O365SP-NA-VaultA1 e Contoso-O365SP-NA-VaultA2. I nomi cassaforte sono stringhe globalmente univoche all'interno di Azure, in modo che potrebbe essere necessario provare le varianti dei nomi desiderati nel caso in cui i nomi desiderati siano già stati richiesti da altri utenti di Azure. A partire da luglio 2017 cassaforte nomi non possono essere modificati, in modo che è consigliabile disporre di un piano scritto dal programma di installazione e l'utilizzo di un secondo utente per verificare che il piano viene eseguito correttamente.</span><span class="sxs-lookup"><span data-stu-id="b0f19-p126">Use a common prefix for key vaults, and include an abbreviation of the use and scope of the key vault and keys (e.g., for the Contoso SharePoint service where the vaults will be located in North America, a possible pair of names is Contoso-O365SP-NA-VaultA1 and Contoso-O365SP-NA-VaultA2. Vault names are globally unique strings within Azure, so you may need to try variations of your desired names in case the desired names are already claimed by other Azure customers. As of July 2017 vault names cannot be changed, so a best practice is to have a written plan for setup and use a second person to verify the plan is executed correctly.</span></span><br/><span data-ttu-id="b0f19-p127">Se possibile, creare le archivi in aree non associata. Aree di Azure accoppiate garantire la disponibilità elevata tra domini di errore del servizio. Di conseguenza, coppie regionali possono essere considerate come area backup di altro. Ciò significa che una risorsa Azure che viene inserita in una regione automaticamente sta per essere la tolleranza di errore tramite l'area accoppiato. Per questo motivo, la scelta di aree per due archivi utilizzati in una protezione esecuzione programmi in cui le aree sono accoppiati significa che solo un totale di due regioni della disponibilità sono in uso. La maggior parte delle aree geografiche hanno a disposizione due aree, in modo che non è ancora possibile selezionare aree non associata. Se possibile, selezionare due aree non associata per gli archivi di due utilizzati con una protezione esecuzione programmi. Il vantaggio da un totale di quattro aree della disponibilità. Per ulteriori informazioni, vedere [Business continuity e ripristino di emergenza (BCDR): Azure accoppiato aree](https://docs.microsoft.com/azure/best-practices-availability-paired-regions) per un elenco corrente delle coppie regionali.</span><span class="sxs-lookup"><span data-stu-id="b0f19-p127">If possible, create your vaults in non-paired regions. Paired Azure regions provide high availability across service failure domains. Therefore, regional pairs can be thought of as each other's backup region. This means that an Azure resource that is placed in one region is automatically gaining fault tolerance through the paired region. For this reason, choosing regions for two vaults used in a DEP where the regions are paired means that only a total of two regions of availability are in use. Most geographies only have two regions, so it's not yet possible to select non-paired regions. If possible, choose two non-paired regions for the two vaults used with a DEP. This benefits from a total of four regions of availability. For more information, see [Business continuity and disaster recovery (BCDR): Azure Paired Regions](https://docs.microsoft.com/azure/best-practices-availability-paired-regions) for a current list of regional pairs.</span></span> 
  
### <a name="assign-permissions-to-each-key-vault"></a><span data-ttu-id="b0f19-252">Assegnare le autorizzazioni per ogni archivio chiave</span><span class="sxs-lookup"><span data-stu-id="b0f19-252">Assign permissions to each key vault</span></span>
<span data-ttu-id="b0f19-253"><a name="KeyVaultPerms"> </a></span><span class="sxs-lookup"><span data-stu-id="b0f19-253"></span></span>

<span data-ttu-id="b0f19-p128">Per ogni archivio chiave, sarà necessario definire tre set di autorizzazioni per clienti chiave, a seconda dell'implementazione separati. Ad esempio, è necessario definire un set di autorizzazioni per gli elementi seguenti:</span><span class="sxs-lookup"><span data-stu-id="b0f19-p128">For each key vault, you will need to define three separate sets of permissions for Customer Key, depending on your implementation. For example, you will need to define one set of permissions for each of the following:</span></span>
  
- <span data-ttu-id="b0f19-p129">**Gli amministratori cassaforte chiave** che verranno eseguite gestione giornaliera dell'archivio chiave per la propria organizzazione. Queste attività includono backup, creare, ottenere, importano, elencare e ripristino.</span><span class="sxs-lookup"><span data-stu-id="b0f19-p129">**Key vault administrators** that will perform day-to-day management of your key vault for your organization. These tasks include backup, create, get, import, list, and restore.</span></span> 
    
    > [!IMPORTANT]
    > <span data-ttu-id="b0f19-p130">Il set di autorizzazioni assegnate agli amministratori di cassaforte chiave non include l'autorizzazione per eliminare le chiavi. Questo comportamento è intenzionale e una procedura importante. Eliminazione delle chiavi di crittografia non viene in genere eseguita, poiché effettuare in modo permanente Elimina dati. Come procedura consigliata, non concedere questa autorizzazione per gli amministratori principali cassaforte per impostazione predefinita. In realtà, questo riservare per i collaboratori cassaforte chiave e solo assegnarlo a un amministratore in base a breve termine una volta che viene considerato comprendere chiaramente le conseguenze.</span><span class="sxs-lookup"><span data-stu-id="b0f19-p130">The set of permissions assigned to key vault administrators does not include the permission to delete keys. This is intentional and an important practice. Deleting encryption keys is not typically done, since doing so permanently destroys data. As a best practice, do not grant this permission to key vault administrators by default. Instead, reserve this for key vault contributors and only assign it to an administrator on a short term basis once a clear understanding of the consequences is understood.</span></span> 
  
    <span data-ttu-id="b0f19-p131">Per assegnare le autorizzazioni a un utente nell'organizzazione Office 365, accedere alla sottoscrizione Azure con Azure PowerShell. Per ulteriori informazioni, vedere [eseguire l'accesso con Azure PowerShell](https://docs.microsoft.com/powershell/azure/authenticate-azureps?view=azurermps-4.3.1).</span><span class="sxs-lookup"><span data-stu-id="b0f19-p131">To assign these permissions to a user in your Office 365 organization, log in to your Azure subscription with Azure PowerShell. For instructions, see [Log in with Azure PowerShell](https://docs.microsoft.com/powershell/azure/authenticate-azureps?view=azurermps-4.3.1).</span></span>
    
- <span data-ttu-id="b0f19-265">Eseguire il cmdlet Set-AzureRmKeyVaultAccessPolicy per assegnare le autorizzazioni necessarie.</span><span class="sxs-lookup"><span data-stu-id="b0f19-265">Run the Set-AzureRmKeyVaultAccessPolicy cmdlet to assign the necessary permissions.</span></span>
    
  ```
  Set-AzureRmKeyVaultAccessPolicy -VaultName <vaultname> 
  -UserPrincipalName <UPN of user> -PermissionsToKeys create,import,list,get,backup,restore
  ```

  <span data-ttu-id="b0f19-266">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="b0f19-266">For example:</span></span>
    
  ```
  Set-AzureRmKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 
  -UserPrincipalName alice@contoso.com -PermissionsToKeys create,import,list,get,backup,restore
  ```

- <span data-ttu-id="b0f19-p132">**I collaboratori cassaforte chiave** che possono modificare le autorizzazioni per l'archivio di chiave Azure stesso. Sarà necessario modificare queste autorizzazioni dipendenti lasciare o partecipare al team o in una situazione molto rara che la chiave di archivio amministratori legittimo necessario disporre dell'autorizzazione per eliminare o ripristinare una chiave. Questa serie di cassaforte principali collaboratori deve essere concesso il ruolo di **Collaboratore** dell'archivio chiave. È possibile assegnare questo ruolo con Gestione risorse di Azure. Per ulteriori informazioni, vedere [Controllo dell'accesso Use Role-Based per gestire l'accesso alle risorse della sottoscrizione di Azure](https://docs.microsoft.com/azure/active-directory/role-based-access-control-configure). L'amministratore che ha creato una sottoscrizione con questo tipo di accesso in modo implicito, nonché la possibilità di assegnare ad altri amministratori al ruolo di collaboratore.</span><span class="sxs-lookup"><span data-stu-id="b0f19-p132">**Key vault contributors** that can change permissions on the Azure Key Vault itself. You'll need to change these permissions as employees leave or join your team, or in the extremely rare situation that the key vault administrators legitimately need permission to delete or restore a key. This set of key vault contributors needs to be granted the **Contributor** role on your key vault. You can assign this role by using Azure Resource Manager. For detailed steps, see [Use Role-Based Access Control to manage access to your Azure subscription resources](https://docs.microsoft.com/azure/active-directory/role-based-access-control-configure). The administrator who creates a subscription has this access implicitly, as well as the ability to assign other administrators to the Contributor role.</span></span>
    
- <span data-ttu-id="b0f19-p133">Se si intende utilizzare chiave cliente con Exchange Online e Skype per le aziende, è necessario concedere l'autorizzazione per Office 365 utilizzino cassaforte chiave per conto di Exchange Online e Skype per le aziende. Analogamente, se si intende utilizzare chiave cliente con SharePoint Online e OneDrive for Business, è necessario aggiungere l'autorizzazione per Office 365 utilizzare l'archivio chiave per conto di SharePoint Online e OneDrive for Business. Per concedere autorizzazioni a Office 365, eseguire il cmdlet **Set-AzureRmKeyVaultAccessPolicy** utilizzando la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="b0f19-p133">If you intend to use Customer Key with Exchange Online and Skype for Business, you need to give permission to Office 365 to use the key vault on behalf of Exchange Online and Skype for Business. Likewise, if you intend to use Customer Key with SharePoint Online and OneDrive for Business, you need to add permission for the Office 365 to use the key vault on behalf of SharePoint Online and OneDrive for Business. To give permission to Office 365, run the **Set-AzureRmKeyVaultAccessPolicy** cmdlet using the following syntax:</span></span> 
    
  ```
  Set-AzureRmKeyVaultAccessPolicy -VaultName <vaultname> -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName <Office 365 appID>
  ```

    <span data-ttu-id="b0f19-276">Dove:</span><span class="sxs-lookup"><span data-stu-id="b0f19-276">Where:</span></span>
    
  - <span data-ttu-id="b0f19-277">*vaultname* è il nome dell'archivio di chiave che è stato creato.</span><span class="sxs-lookup"><span data-stu-id="b0f19-277">*vaultname* is the name of the key vault you created.</span></span> 
    
  - <span data-ttu-id="b0f19-278">Per Exchange Online e Skype per le aziende, sostituire *appID Office 365* con`00000002-0000-0ff1-ce00-000000000000`</span><span class="sxs-lookup"><span data-stu-id="b0f19-278">For Exchange Online and Skype for Business, replace  *Office 365 appID* with `00000002-0000-0ff1-ce00-000000000000`</span></span>
    
  - <span data-ttu-id="b0f19-279">Per SharePoint Online e OneDrive for Business, sostituire *appID Office 365* con`00000003-0000-0ff1-ce00-000000000000`</span><span class="sxs-lookup"><span data-stu-id="b0f19-279">For SharePoint Online and OneDrive for Business, replace  *Office 365 appID* with `00000003-0000-0ff1-ce00-000000000000`</span></span>
    
  <span data-ttu-id="b0f19-280">Esempio: Impostazione delle autorizzazioni per Exchange Online e Skype for Business:</span><span class="sxs-lookup"><span data-stu-id="b0f19-280">Example: Setting permissions for Exchange Online and Skype for Business:</span></span>
    
  ```
  Set-AzureRmKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 
  -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName 00000002-0000-0ff1-ce00-000000000000
  ```

  <span data-ttu-id="b0f19-281">Esempio: Impostazione delle autorizzazioni per SharePoint Online e OneDrive for Business</span><span class="sxs-lookup"><span data-stu-id="b0f19-281">Example: Setting permissions for SharePoint Online and OneDrive for Business</span></span>
    
  ```
  Set-AzureRmKeyVaultAccessPolicy -VaultName Contoso-O365SP-NA-VaultA1 
  -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName 00000003-0000-0ff1-ce00-000000000000
  ```

### <a name="enable-and-then-confirm-soft-delete-on-your-key-vaults"></a><span data-ttu-id="b0f19-282">Abilitare questa impostazione e quindi confermare l'eliminazione temporanea in archivi il chiavi</span><span class="sxs-lookup"><span data-stu-id="b0f19-282">Enable and then confirm soft delete on your key vaults</span></span>
<span data-ttu-id="b0f19-283"><a name="SoftDelete"> </a></span><span class="sxs-lookup"><span data-stu-id="b0f19-283"></span></span>

<span data-ttu-id="b0f19-p134">Quando è possibile ripristinare rapidamente le chiavi, hanno meno probabilità di verifica un'interruzione del servizio esteso a causa di chiavi eliminate accidentalmente o da utenti malintenzionati. È necessario attivare questa configurazione, denominata eliminare Soft, prima di poter utilizzare i tasti con clienti chiave. Abilitazione eliminare Soft consente di ripristinare le chiavi o gli archivi di 90 giorni di eliminazione senza la necessità di ripristinarli dal backup.</span><span class="sxs-lookup"><span data-stu-id="b0f19-p134">When you can quickly recover your keys, you are less likely to experience an extended service outage due to accidentally or maliciously deleted keys. You need to enable this configuration, referred to as Soft Delete, before you can use your keys with Customer Key. Enabling Soft Delete allows you to recover keys or vaults within 90 days of deletion without having to restore them from backup.</span></span>
  
<span data-ttu-id="b0f19-287">Per abilitare eliminare Soft negli archivi chiavi, completare la procedura seguente:</span><span class="sxs-lookup"><span data-stu-id="b0f19-287">To enable Soft Delete on your key vaults, complete these steps:</span></span>
  
1. <span data-ttu-id="b0f19-p135">Eseguire l'accesso alla sottoscrizione Azure con Windows Powershell. Per ulteriori informazioni, vedere [eseguire l'accesso con Azure PowerShell](https://docs.microsoft.com/powershell/azure/authenticate-azureps).</span><span class="sxs-lookup"><span data-stu-id="b0f19-p135">Log in to your Azure subscription with Windows Powershell. For instructions, see [Log in with Azure PowerShell](https://docs.microsoft.com/powershell/azure/authenticate-azureps).</span></span>
    
2. <span data-ttu-id="b0f19-p136">Eseguire il cmdlet [Get-AzureRmKeyVault](https://docs.microsoft.com/powershell/module/azurerm.keyvault/get-azurermkeyvault) . In questo esempio *vaultname* è il nome dell'archivio di chiave per la quale si desidera abilitare l'eliminazione temporanea:</span><span class="sxs-lookup"><span data-stu-id="b0f19-p136">Run the [Get-AzureRmKeyVault](https://docs.microsoft.com/powershell/module/azurerm.keyvault/get-azurermkeyvault) cmdlet. In this example, *vaultname* is the name of the key vault for which you are enabling soft delete:</span></span> 
    
   ```
   $v = Get-AzureRmKeyVault -VaultName <vaultname>
   $r = Get-AzureRmResource -ResourceId $v.ResourceId
   $r.Properties | Add-Member -MemberType NoteProperty -Name enableSoftDelete -Value 'True'
   Set-AzureRmResource -ResourceId $r.ResourceId -Properties $r.Properties
   ``` 
    
3. <span data-ttu-id="b0f19-p137">Conferma eliminazione temporanea è configurato per l'archivio chiave eseguendo il cmdlet **Get-AzureRmKeyVault** . Se eliminazione temporanea sia configurato correttamente per l'archivio di chiavi, il Soft eliminare Enabled? proprietà restituisce il valore **True**:</span><span class="sxs-lookup"><span data-stu-id="b0f19-p137">Confirm soft delete is configured for the key vault by running the **Get-AzureRmKeyVault** cmdlet. If soft delete is configured properly for the key vault, then the  Soft Delete Enabled? property returns a value of **True**:</span></span> 
    
   ```
   Get-AzureRmKeyVault -VaultName <vaultname> | fl
   ```

   
    
### <a name="add-a-key-to-each-key-vault-either-by-creating-or-importing-a-key"></a><span data-ttu-id="b0f19-294">Aggiungere una chiave per ogni archivio chiave sia per la creazione o l'importazione di una chiave</span><span class="sxs-lookup"><span data-stu-id="b0f19-294">Add a key to each key vault either by creating or importing a key</span></span>
<span data-ttu-id="b0f19-295"><a name="AddKeystoKeyVault"> </a></span><span class="sxs-lookup"><span data-stu-id="b0f19-295"></span></span>

<span data-ttu-id="b0f19-p138">Esistono due modi per aggiungere le chiavi a una cassaforte chiave Azure; è possibile creare una chiave direttamente nella chiave cassaforte oppure è possibile importare una chiave. Creazione di una chiave direttamente nella chiave cassaforte è il metodo meno complesso, durante l'importazione di una chiave consente di controllare totale come viene generata la chiave.</span><span class="sxs-lookup"><span data-stu-id="b0f19-p138">There are two ways to add keys to an Azure Key Vault; you can create a key directly in Key Vault, or you can import a key. Creating a key directly in Key Vault is the less complicated method, while importing a key provides total control over how the key is generated.</span></span>
  
<span data-ttu-id="b0f19-298">Per creare una chiave direttamente la chiave cassaforte, eseguire il cmdlet [Add-AzureKeyVaultKey](https://docs.microsoft.com/powershell/module/AzureRM.KeyVault/Add-AzureKeyVaultKey) come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="b0f19-298">To create a key directly in your key vault, run the [Add-AzureKeyVaultKey](https://docs.microsoft.com/powershell/module/AzureRM.KeyVault/Add-AzureKeyVaultKey) cmdlet as follows:</span></span> 
  
```
Add-AzureKeyVaultKey -VaultName <vaultname> -Name <keyname> -Destination <HSM|Software> -KeyOps wrapKey,unwrapKey
```

<span data-ttu-id="b0f19-299">Dove:</span><span class="sxs-lookup"><span data-stu-id="b0f19-299">Where:</span></span>
  
-  <span data-ttu-id="b0f19-300">*vaultname* è il nome dell'archivio di chiave in cui si desidera creare la chiave.</span><span class="sxs-lookup"><span data-stu-id="b0f19-300">*vaultname*  is the name of the key vault in which you want to create the key.</span></span> 
    
-  <span data-ttu-id="b0f19-301">*nome chiave* è il nome che si desidera assegnare alla nuova chiave.</span><span class="sxs-lookup"><span data-stu-id="b0f19-301">*keyname*  is the name you want to give the new key.</span></span> 
    
    > [!TIP]
    > <span data-ttu-id="b0f19-p139">Nome chiavi utilizzando la convenzione di denominazione simile, come descritto in precedenza per gli archivi di chiave. In questo modo, negli strumenti che mostra solo il nome della chiave, la stringa self-descritto.</span><span class="sxs-lookup"><span data-stu-id="b0f19-p139">Name keys using a similar naming convention as described above for key vaults. This way, in tools that show only the key name, the string is self-describing.</span></span> 
  
- <span data-ttu-id="b0f19-304">Se si prevede di proteggere la chiave con un modulo di sicurezza hardware, assicurarsi di specificare **modulo di sicurezza hardware** come valore del parametro _destinazione_ , in caso contrario, specificare **Software**.</span><span class="sxs-lookup"><span data-stu-id="b0f19-304">If you intend to protect the key with an HSM, ensure that you specify **HSM** as the value of the  _Destination_ parameter, otherwise, specify **Software**.</span></span>
    
<span data-ttu-id="b0f19-305">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="b0f19-305">For example,</span></span>
  
```
Add-AzureKeyVaultKey -VaultName Contoso-O365EX-NA-VaultA1 -Name Contoso-O365EX-NA-VaultA1-Key001 -Destination Software -KeyOps wrapKey,unwrapKey
```

<span data-ttu-id="b0f19-306">Per importare una chiave direttamente nell'archivio di chiavi, è necessario disporre di un modulo di sicurezza Hardware di nShield Thales.</span><span class="sxs-lookup"><span data-stu-id="b0f19-306">To import a key directly into your key vault, you need to have a Thales nShield Hardware Security Module.</span></span>
  
<span data-ttu-id="b0f19-307">Alcune aziende preferiscono questo approccio per stabilire provenienza per le chiavi e questo metodo offre inoltre le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="b0f19-307">Some organizations prefer this approach to establish the provenance of their keys, and the this method also provides the following:</span></span>
  
- <span data-ttu-id="b0f19-308">Il set di strumenti utilizzati per l'importazione include attestazione da Thales che non sia stato esportabile la chiave di Exchange chiave (KEK) utilizzato per crittografare la chiave che è generare e viene generato all'interno di un modulo di sicurezza autentico hardware che è stata prodotta da Thales.</span><span class="sxs-lookup"><span data-stu-id="b0f19-308">The toolset used for import includes attestation from Thales that the Key Exchange Key (KEK) that is used to encrypt the key you generate is not exportable and is generated inside a genuine HSM that was manufactured by Thales.</span></span>
    
- <span data-ttu-id="b0f19-p140">Il set di strumenti include attestazione da Thales che le funzionalità di sicurezza Azure chiave cassaforte viene generata anche in un modulo di sicurezza hardware autentico prodotto da Thales. Questo tipo di attestazione può rivelarsi a un utente che Microsoft utilizza hardware Thales autentico.</span><span class="sxs-lookup"><span data-stu-id="b0f19-p140">The toolset includes attestation from Thales that the Azure Key Vault security world was also generated on a genuine HSM manufactured by Thales. This attestation proves to you that Microsoft is also using genuine Thales hardware.</span></span>
    
<span data-ttu-id="b0f19-p141">Verificare con il gruppo di sicurezza per determinare se sono necessarie che le attestazioni sopra elencate. Per informazioni dettagliate sulla procedura creare una chiave in locale e importarlo in cassaforte la chiave, vedere [come generare e trasferire protetti da modulo di sicurezza hardware chiavi per Azure chiave cassaforte](https://azure.microsoft.com/documentation/articles/key-vault-hsm-protected-keys/). Utilizzare le istruzioni Azure per creare una chiave in ogni archivio chiave.</span><span class="sxs-lookup"><span data-stu-id="b0f19-p141">Check with your security group to determine if the above attestations are required. For detailed steps to create a key on-premises and import it into your key vault, see [How to generate and transfer HSM-protected keys for Azure Key Vault](https://azure.microsoft.com/documentation/articles/key-vault-hsm-protected-keys/). Use the Azure instructions to create a key in each key vault.</span></span>
  
### <a name="check-the-recovery-level-of-your-keys"></a><span data-ttu-id="b0f19-314">Selezionare il livello di ripristino delle chiavi</span><span class="sxs-lookup"><span data-stu-id="b0f19-314">Check the recovery level of your keys</span></span>
<span data-ttu-id="b0f19-315"><a name="CheckKeyRecoveryLevel"> </a></span><span class="sxs-lookup"><span data-stu-id="b0f19-315"></span></span>

<span data-ttu-id="b0f19-p142">Office 365 è necessario che la sottoscrizione cassaforte chiave Azure è impostata su non annullare e che i tasti utilizzati dalla chiave cliente dispongano di eliminazione temporanea abilitato. È possibile verificarlo esaminando a livello di ripristino delle chiavi.</span><span class="sxs-lookup"><span data-stu-id="b0f19-p142">Office 365 requires that the Azure Key Vault subscription is set to Do Not Cancel and that the keys used by Customer Key have soft delete enabled. You can confirm this by looking at the recovery level on your keys.</span></span>
  
<span data-ttu-id="b0f19-318">Per controllare il livello di ripristino di un tasto, in Azure PowerShell, eseguire il cmdlet Get-AzureKeyVaultKey come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="b0f19-318">To check the recovery level of a key, in Azure PowerShell, run the Get-AzureKeyVaultKey cmdlet as follows:</span></span>
  
```
(Get-AzureKeyVaultKey -VaultName <vaultname> -Name <keyname>).Attributes 
```

<span data-ttu-id="b0f19-319">Se la proprietà a _Livello di ripristino_ restituisce un valore diverso da un valore pari a **+ ProtectedSubscription reversibile**, è necessario leggere questo argomento e verificare di aver seguito tutti i passaggi per mettere la sottoscrizione nell'elenco non annullare e di avere eliminazione temporanea abilitato in ognuno degli archivi chiavi.</span><span class="sxs-lookup"><span data-stu-id="b0f19-319">If the  _Recovery Level_ property returns anything other than a value of **Recoverable+ProtectedSubscription**, you will need to review this topic and ensure that you have followed all of the steps to put the subscription on the Do Not Cancel list and that you have soft delete enabled on each of your key vaults.</span></span>
  
### <a name="backup-azure-key-vault"></a><span data-ttu-id="b0f19-320">Backup cassaforte chiave Azure</span><span class="sxs-lookup"><span data-stu-id="b0f19-320">Backup Azure Key Vault</span></span>
<span data-ttu-id="b0f19-321"><a name="BackupAzureKeyVaultkeys"> </a></span><span class="sxs-lookup"><span data-stu-id="b0f19-321"></span></span>

<span data-ttu-id="b0f19-p143">Subito dopo la creazione o qualsiasi modifica apportata a una chiave, eseguire il backup e archiviare le copie di backup, online e offline. Copie non in linea dovrebbero essere connessi non a qualsiasi rete, ad esempio in una struttura fisica di archiviazione sicura o commerciale. Almeno una copia di backup deve essere archiviata in un percorso accessibile in caso di emergenza. Gli oggetti BLOB di backup è l'unico mezzo per il ripristino chiave opportuno un codice di tasto cassaforte eliminato in modo permanente o inutilizzabile in caso contrario. Le chiavi sono esterni all'archivio chiave Azure e sono stati importati in Azure chiave archivio non possono essere come backup perché i metadati necessari per clienti chiave da utilizzare la chiave non esiste con la chiave esterna. Consente solo un backup eseguito dall'insieme di credenziali chiave Azure per operazioni di ripristino con clienti chiave. Di conseguenza, è essenziale che un backup dell'archivio di chiave Azure deve essere eseguita dopo una chiave viene caricata o creata.</span><span class="sxs-lookup"><span data-stu-id="b0f19-p143">Immediately following creation or any change to a key, perform a backup and store copies of the backup, both online and offline. Offline copies should not be connected to any network, such as in a physical safe or commercial storage facility. At least one copy of the backup should be stored in a location that will be accessible in the event of a disaster. The backup blobs are the sole means of restoring key material should a Key Vault key be permanently destroyed or otherwise rendered inoperable. Keys that are external to Azure Key Vault and were imported to Azure Key Vault do not qualify as a backup because the metadata necessary for Customer Key to use the key does not exist with the external key. Only a backup taken from Azure Key Vault can be used for restore operations with Customer Key. Therefore, it is essential that a backup of Azure Key Vault be made once a key is uploaded or created.</span></span>
  
<span data-ttu-id="b0f19-329">Per creare un backup di una chiave di Azure chiave cassaforte, eseguire il cmdlet [Backup-AzureKeyVaultKey](https://docs.microsoft.com/powershell/module/AzureRM.KeyVault/Backup-AzureKeyVaultKey) come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="b0f19-329">To create a backup of an Azure Key Vault key, run the [Backup-AzureKeyVaultKey](https://docs.microsoft.com/powershell/module/AzureRM.KeyVault/Backup-AzureKeyVaultKey) cmdlet as follows:</span></span>
```
Backup-AzureKeyVaultKey -VaultName <vaultname> -Name <keyname> 
-OutputFile <filename .backup>

```

<span data-ttu-id="b0f19-330">Verificare che il file di output viene utilizzato il suffisso `.backup`.</span><span class="sxs-lookup"><span data-stu-id="b0f19-330">Ensure that your output file uses the suffix  `.backup`.</span></span>
  
<span data-ttu-id="b0f19-p144">File di output risultanti da questo cmdlet viene crittografato e non può essere utilizzato all'esterno di Azure chiave cassaforte. Il backup può essere ripristinato solo per la sottoscrizione Azure da cui è stato eseguito il backup.</span><span class="sxs-lookup"><span data-stu-id="b0f19-p144">The output file resulting from this cmdlet is encrypted and cannot be used outside of Azure Key Vault. The backup can be restored only to the Azure subscription from which the backup was taken.</span></span>
  
> [!TIP]
> <span data-ttu-id="b0f19-p145">Il file di output, scegliere una combinazione del nome di archivio e il nome della chiave. Ciò consentirà il file nome self-descrizione. Garantisce inoltre che i nomi di file di backup non sono in conflitto.</span><span class="sxs-lookup"><span data-stu-id="b0f19-p145">For the output file, choose a combination of your vault name and key name. This will make the file name self-describing. It will also ensure that backup file names do not collide.</span></span> 
  
<span data-ttu-id="b0f19-336">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="b0f19-336">For example:</span></span>
  
```
Backup-AzureKeyVaultKey -VaultName Contoso-O365EX-NA-VaultA1 -Name Contoso-O365EX-NA-VaultA1-Key001 -OutputFile Contoso-O365EX-NA-VaultA1-Key001-Backup-20170802.backup
```

### <a name="validate-azure-key-vault-configuration-settings"></a><span data-ttu-id="b0f19-337">Verificare le impostazioni di configurazione di Azure chiave cassaforte</span><span class="sxs-lookup"><span data-stu-id="b0f19-337">Validate Azure Key Vault configuration settings</span></span>
<span data-ttu-id="b0f19-338"><a name="Validateconfiguration"> </a></span><span class="sxs-lookup"><span data-stu-id="b0f19-338"></span></span>

<span data-ttu-id="b0f19-p146">Eseguire la convalida prima di utilizzare chiavi di una protezione esecuzione programmi è facoltativa ma consigliata. In particolare, se si utilizzano passaggi per configurare le chiavi e gli archivi di diversi da quelli descritti in questo argomento, è necessario convalidare l'integrità delle risorse di Azure chiave cassaforte prima di configurare la chiave cliente.</span><span class="sxs-lookup"><span data-stu-id="b0f19-p146">Performing validation before using keys in a DEP is optional, but highly recommended. In particular, if you use steps to set up your keys and vaults other than the ones described in this topic, you should validate the health of your Azure Key Vault resources before you configure Customer Key.</span></span>
  
<span data-ttu-id="b0f19-341">Per verificare che le chiavi sono operazioni get, wrapKey e unwrapKey abilitate:</span><span class="sxs-lookup"><span data-stu-id="b0f19-341">To verify that your keys have get, wrapKey, and unwrapKey operations enabled:</span></span>
  
<span data-ttu-id="b0f19-342">Eseguire il cmdlet [Get-AzureRmKeyVault](https://docs.microsoft.com/powershell/module/AzureRM.KeyVault/Get-AzureRmKeyVault) come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="b0f19-342">Run the [Get-AzureRmKeyVault](https://docs.microsoft.com/powershell/module/AzureRM.KeyVault/Get-AzureRmKeyVault) cmdlet as follows:</span></span> 
  
```
Get-AzureRMKeyVault -VaultName <vaultname>
```

<span data-ttu-id="b0f19-p147">Nell'output, osservare per il criterio di accesso e per l'identità (GUID) di Exchange Online o l'identità (GUID) di SharePoint Online nel modo appropriato. Tutti e tre i queste autorizzazioni devono essere visualizzate in autorizzazioni alle chiavi.</span><span class="sxs-lookup"><span data-stu-id="b0f19-p147">In the output, look for the Access Policy and for the Exchange Online identity (GUID) or the SharePoint Online identity (GUID) as appropriate. All three of the above permissions must be shown under Permissions to Keys.</span></span>
  
<span data-ttu-id="b0f19-345">Se la configurazione dei criteri di accesso non è corretta, eseguire il cmdlet Set-AzureRmKeyVaultAccessPolicy come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="b0f19-345">If the access policy configuration is incorrect, run the Set-AzureRmKeyVaultAccessPolicy cmdlet as follows:</span></span>
  
```
Set-AzureRmKeyVaultAccessPolicy -VaultName <vaultname> -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName <Office 365 appID>
```

<span data-ttu-id="b0f19-346">Ad esempio, per Exchange Online e Skype for Business:</span><span class="sxs-lookup"><span data-stu-id="b0f19-346">For example, for Exchange Online and Skype for Business:</span></span>
  
```
Set-AzureRmKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 
-PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName 00000002-0000-0ff1-ce00-000000000000
```

<span data-ttu-id="b0f19-347">Ad esempio, per SharePoint Online e OneDrive for Business:</span><span class="sxs-lookup"><span data-stu-id="b0f19-347">For example, for SharePoint Online and OneDrive for Business:</span></span>
  
```
Set-AzureRmKeyVaultAccessPolicy -VaultName Contoso-O365SP-NA-VaultA1 
-PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName TBD
```

<span data-ttu-id="b0f19-348">Per verificare che la data di scadenza non è impostata per le chiavi eseguire il cmdlet [Get-AzureKeyVaultKey](https://docs.microsoft.com/powershell/module/AzureRM.KeyVault/Get-AzureKeyVaultKey) come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="b0f19-348">To verify that an expiration date is not set for your keys run the [Get-AzureKeyVaultKey](https://docs.microsoft.com/powershell/module/AzureRM.KeyVault/Get-AzureKeyVaultKey) cmdlet as follows:</span></span> 
  
```
Get-AzureKeyVaultKey -VaultName <vaultname> 
```

<span data-ttu-id="b0f19-p148">Una chiave scaduta non può essere utilizzata dalla chiave cliente e operazioni tentate con una chiave scaduta avrà esito negativo e anche comportare un'interruzione del servizio. È consigliabile che le chiavi utilizzate con chiave cliente non è una data di scadenza. Una data di scadenza, una volta impostato, non possono essere rimosse, ma può essere modificato in una data diversa. Se una chiave deve essere utilizzata con una data di scadenza impostare, modificare il valore di scadenza per 31/12/9999. Tasti con una data di scadenza per impostato un valore diverso da quello 31/12/9999 non superano la convalida di Office 365.</span><span class="sxs-lookup"><span data-stu-id="b0f19-p148">An expired key cannot be used by Customer Key and operations attempted with an expired key will fail, and possibly result in a service outage. We strongly recommend that keys used with Customer Key do not have an expiration date. An expiration date, once set, cannot be removed, but can be changed to a different date. If a key must be used that has an expiration date set, change the expiration value to 12/31/9999. Keys with an expiration date set to a date other than 12/31/9999 will not pass Office 365 validation.</span></span>
  
<span data-ttu-id="b0f19-354">Per modificare una data di scadenza che è stata impostata su un valore diverso da 31/12/9999, eseguire il cmdlet [Set-AzureKeyVaultKeyAttribute](https://docs.microsoft.com/powershell/module/AzureRM.KeyVault/Set-AzureKeyVaultKeyAttribute) come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="b0f19-354">To change an expiration date that has been set to any value other than 12/31/9999, run the [Set-AzureKeyVaultKeyAttribute](https://docs.microsoft.com/powershell/module/AzureRM.KeyVault/Set-AzureKeyVaultKeyAttribute) cmdlet as follows:</span></span> 
  
```
Set-AzureKeyVaultKeyAttribute -VaultName <vaultname> -Name <keyname> 
-Expires (Get-Date -Date "12/31/9999")
```

> [!CAUTION]
> <span data-ttu-id="b0f19-355">Non impostare date di scadenza per le chiavi di crittografia che si utilizza con clienti chiave.</span><span class="sxs-lookup"><span data-stu-id="b0f19-355">Don't set expiration dates on encryption keys you use with Customer Key.</span></span> 
  
### <a name="obtain-the-uri-for-each-azure-key-vault-key"></a><span data-ttu-id="b0f19-356">Ottenere l'URI per ogni tasto di Azure chiave cassaforte</span><span class="sxs-lookup"><span data-stu-id="b0f19-356">Obtain the URI for each Azure Key Vault key</span></span>
<span data-ttu-id="b0f19-357"><a name="GetKeyURI"> </a></span><span class="sxs-lookup"><span data-stu-id="b0f19-357"></span></span>

<span data-ttu-id="b0f19-p149">Dopo aver completato tutti i passaggi descritti in Azure per impostare il chiavi archivi e aggiungere le chiavi, eseguire il comando seguente per ottenere l'URI della chiave in ogni archivio chiave. È necessario utilizzare questi URI quando si creano e assegnare ciascuna protezione esecuzione programmi in seguito, quindi salvare le informazioni in un luogo sicuro. Ricordarsi di eseguire il comando una sola volta per ogni archivio chiave.</span><span class="sxs-lookup"><span data-stu-id="b0f19-p149">Once you have completed all the steps in Azure to set up your key vaults and added your keys, run the following command to get the URI for the key in each key vault. You will need to use these URIs when you create and assign each DEP later, so save this information in a safe place. Remember to run this command once for each key vault.</span></span>
  
<span data-ttu-id="b0f19-361">In Azure PowerShell:</span><span class="sxs-lookup"><span data-stu-id="b0f19-361">In Azure PowerShell:</span></span>
  
```
(Get-AzureKeyVaultKey -VaultName <vaultname>).Id
```

## <a name="office-365-setting-up-customer-key-for-exchange-online-and-skype-for-business"></a><span data-ttu-id="b0f19-362">Office 365: Impostazione di chiave cliente per Exchange Online e Skype per le aziende</span><span class="sxs-lookup"><span data-stu-id="b0f19-362">Office 365: Setting up Customer Key for Exchange Online and Skype for Business</span></span>
<span data-ttu-id="b0f19-363"><a name="AzureSteps"> </a></span><span class="sxs-lookup"><span data-stu-id="b0f19-363"></span></span>

<span data-ttu-id="b0f19-p150">Prima di iniziare, verificare di aver completato le attività necessarie per configurare Azure chiave cassaforte. Per informazioni, vedere [completare le attività in Azure chiave cassaforte e FastTrack Microsoft per la chiave cliente](controlling-your-data-using-customer-key.md#AzureSteps) .</span><span class="sxs-lookup"><span data-stu-id="b0f19-p150">Before you begin, ensure that you have completed the tasks required to set up Azure Key Vault. See [Complete tasks in Azure Key Vault and Microsoft FastTrack for Customer Key](controlling-your-data-using-customer-key.md#AzureSteps) for information.</span></span> 
  
<span data-ttu-id="b0f19-366">Per configurare chiave cliente per Exchange Online e Skype per le aziende, è necessario eseguire la procedura seguente tramite la connessione in remoto a Exchange Online con Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b0f19-366">To set up Customer Key for Exchange Online and Skype for Business, you will need to perform these steps by remotely connecting to Exchange Online with Windows PowerShell.</span></span>
  
### <a name="create-a-data-encryption-policy-dep-for-use-with-exchange-online-and-skype-for-business"></a><span data-ttu-id="b0f19-367">Creare un criterio di crittografia dei dati (DEP) per l'utilizzo con Exchange Online e Skype per le aziende</span><span class="sxs-lookup"><span data-stu-id="b0f19-367">Create a data encryption policy (DEP) for use with Exchange Online and Skype for Business</span></span>
<span data-ttu-id="b0f19-368"><a name="CreateDEP4EXOSkype"> </a></span><span class="sxs-lookup"><span data-stu-id="b0f19-368"></span></span>

<span data-ttu-id="b0f19-p151">Una protezione esecuzione programmi sono associata a un set di chiavi archiviate nell'archivio chiave Azure. Per assegnare una protezione esecuzione programmi a una cassetta postale in Office 365. Office 365 utilizzerà quindi le chiavi identificate nel criterio per crittografare la cassetta postale. Per creare i programmi, è necessario gli URI cassaforte chiave ottenuto in precedenza. Per istruzioni, vedere [ottenere l'URI per ogni tasto cassaforte chiave Azure](controlling-your-data-using-customer-key.md#GetKeyURI) .</span><span class="sxs-lookup"><span data-stu-id="b0f19-p151">A DEP is associated with a set of keys stored in Azure Key Vault. You assign a DEP to a mailbox in Office 365. Office 365 will then use the keys identified in the policy to encrypt the mailbox. To create the DEP, you need the Key Vault URIs you obtained earlier. See [Obtain the URI for each Azure Key Vault key](controlling-your-data-using-customer-key.md#GetKeyURI) for instructions.</span></span> 
  
<span data-ttu-id="b0f19-p152">Ricordare! Quando si creano una protezione esecuzione programmi, si specificano due chiavi che si trovano in due diversi archivi di chiave di Azure. Verificare che queste chiavi si trovano in due regioni Azure separate per garantire la ridondanza geografica.</span><span class="sxs-lookup"><span data-stu-id="b0f19-p152">Remember! When you create a DEP, you specify two keys that reside in two different Azure Key Vaults. Ensure that these keys are located in two separate Azure regions to ensure geo-redundancy.</span></span>
  
<span data-ttu-id="b0f19-377">Per creare i programmi, procedere come segue:</span><span class="sxs-lookup"><span data-stu-id="b0f19-377">To create the DEP, follow these steps:</span></span>
  
1. <span data-ttu-id="b0f19-378">Nel computer locale, utilizzando un ufficio o della scuola dell'account che disponga delle autorizzazioni di amministratore globale dell'organizzazione Office 365, [la connessione a Exchange Online PowerShell](https://technet.microsoft.com/en-us/library/jj984289%28v=exchg.160%29.aspx) aprire Windows PowerShell ed eseguendo il comando seguente.</span><span class="sxs-lookup"><span data-stu-id="b0f19-378">On your local computer, using a work or school account that has global administrator permissions in your Office 365 organization, [connect to Exchange Online PowerShell](https://technet.microsoft.com/en-us/library/jj984289%28v=exchg.160%29.aspx) by opening Windows PowerShell and running the following command.</span></span> 
    
   ```
   $UserCredential = Get-Credential
   ```

2. <span data-ttu-id="b0f19-379">Nella finestra di dialogo richiesta credenziali di Windows PowerShell immettere il proprio lavoro o scuola informazioni sull'account, fare clic su **OK**e quindi immettere il comando seguente.</span><span class="sxs-lookup"><span data-stu-id="b0f19-379">In the Windows PowerShell Credential Request dialog box, enter your work or school account information, click **OK**, and then enter the following command.</span></span> 
    
   ```
   $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/powershell-liveid/ -Credential $UserCredential -Authentication Basic -AllowRedirection
   ```

3. <span data-ttu-id="b0f19-380">Eseguire il comando riportato di seguito.</span><span class="sxs-lookup"><span data-stu-id="b0f19-380">Run the following command.</span></span>
    
   ```
   Import-PSSession $Session
   ```

4. <span data-ttu-id="b0f19-381">Per creare una protezione esecuzione programmi, utilizzare il cmdlet New-DataEncryptionPolicy digitando il comando seguente.</span><span class="sxs-lookup"><span data-stu-id="b0f19-381">To create a DEP, use the New-DataEncryptionPolicy cmdlet by typing the following command.</span></span>
    
   ```
   New-DataEncryptionPolicy -Name <PolicyName> -Description "PolicyDescription " -AzureKeyIDs <KeyVaultURI1>, <KeyVaultURI2>
   ```

   <span data-ttu-id="b0f19-382">Dove:</span><span class="sxs-lookup"><span data-stu-id="b0f19-382">Where:</span></span>
    
   -  <span data-ttu-id="b0f19-p153">*PolicyName* è il nome che si desidera utilizzare per il criterio. I nomi non possono contenere spazi. Ad esempio, USA_mailboxes.</span><span class="sxs-lookup"><span data-stu-id="b0f19-p153">*PolicyName*  is the name you want to use for the policy. Names cannot contain spaces. For example, USA_mailboxes.</span></span> 
    
   -  <span data-ttu-id="b0f19-p154">*PolicyDescription* è una descrizione descrittivo del criterio che consenta di ricordare facilmente novità per i criteri. È possibile includere spazi nella descrizione. Ad esempio, principali chiave per le cassette postali degli Stati Uniti e le aree.</span><span class="sxs-lookup"><span data-stu-id="b0f19-p154">*PolicyDescription*  is a user friendly description of the policy that will help you remember what the policy is for. You can include spaces in the description. For example, Root key for mailboxes in USA and its territories.</span></span> 
    
   -  <span data-ttu-id="b0f19-p155">*KeyVaultURI1* è l'URI per la prima chiave del criterio. Ad esempio https://contoso_EastUSvault01.vault.azure.net/keys/USA_key_01.</span><span class="sxs-lookup"><span data-stu-id="b0f19-p155">*KeyVaultURI1*  is the URI for the first key in the policy. For example, https://contoso_EastUSvault01.vault.azure.net/keys/USA_key_01.</span></span> 
    
   -  <span data-ttu-id="b0f19-p156">*KeyVaultURI2* è l'URI per la seconda chiave del criterio. Ad esempio https://contoso_EastUS2vault01.vault.azure.net/keys/USA_Key_02. Separare i due URI da una virgola e uno spazio.</span><span class="sxs-lookup"><span data-stu-id="b0f19-p156">*KeyVaultURI2*  is the URI for the second key in the policy. For example, https://contoso_EastUS2vault01.vault.azure.net/keys/USA_Key_02. Separate the two URIs by a comma and a space.</span></span> 
    
   <span data-ttu-id="b0f19-394">Esempio:</span><span class="sxs-lookup"><span data-stu-id="b0f19-394">Example:</span></span>
  
   ```
   New-DataEncryptionPolicy -Name USA_mailboxes -Description "Root key for mailboxes in USA and its territories" -AzureKeyIDs https://contoso_EastUSvault01.vault.azure.net/keys/USA_key_01, https://contoso_EastUS2vault01.vault.azure.net/keys/USA_Key_02
   ```

### <a name="assign-a-dep-to-a-mailbox"></a><span data-ttu-id="b0f19-395">Assegnare una protezione esecuzione programmi a una cassetta postale</span><span class="sxs-lookup"><span data-stu-id="b0f19-395">Assign a DEP to a mailbox</span></span>
<span data-ttu-id="b0f19-396"><a name="assignDEPtomailbox"> </a></span><span class="sxs-lookup"><span data-stu-id="b0f19-396"></span></span>

<span data-ttu-id="b0f19-p157">Assegnare la protezione esecuzione programmi a una cassetta postale utilizzando il cmdlet Set-Mailbox. Dopo aver assegnato il criterio, Office 365 possono crittografare la cassetta postale con la chiave designata la protezione esecuzione programmi.</span><span class="sxs-lookup"><span data-stu-id="b0f19-p157">Assign the DEP to a mailbox by using the Set-Mailbox cmdlet. Once you assign the policy, Office 365 can encrypt the mailbox with the key designated in the DEP.</span></span>
  
```
Set-Mailbox -Identity <MailboxIdParameter> -DataEncryptionPolicy <PolicyName>
```

<span data-ttu-id="b0f19-p158">Dove *MailboxIdParameter* specifica una cassetta postale. Per ulteriori informazioni sul cmdlet Set-Mailbox, vedere [Set-Mailbox](https://technet.microsoft.com/library/bb123981%28v=exchg.160%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="b0f19-p158">Where *MailboxIdParameter* specifies a mailbox. For more information about the Set-Mailbox cmdlet, see [Set-Mailbox](https://technet.microsoft.com/library/bb123981%28v=exchg.160%29.aspx).</span></span>
  
### <a name="validate-mailbox-encryption"></a><span data-ttu-id="b0f19-401">Convalidare la crittografia delle cassette postali</span><span class="sxs-lookup"><span data-stu-id="b0f19-401">Validate mailbox encryption</span></span>
<span data-ttu-id="b0f19-402"><a name="validatemailboxencryption"> </a></span><span class="sxs-lookup"><span data-stu-id="b0f19-402"></span></span>

<span data-ttu-id="b0f19-p159">Crittografare una cassetta postale può richiedere tempo. Per l'assegnazione di criteri prima volta, la cassetta postale inoltre necessario eseguire lo spostamento da un database a un'altra prima che il servizio può crittografare la cassetta postale. È consigliabile attendere 72 ore prima di tentare di convalidare la crittografia dopo che si modificano una protezione esecuzione programmi o la prima volta che è stata assegnata una protezione esecuzione programmi a una cassetta postale.</span><span class="sxs-lookup"><span data-stu-id="b0f19-p159">Encrypting a mailbox can take some time. For first time policy assignment, the mailbox must also complete the move from one database to another before the service can encrypt the mailbox. We recommend that you wait 72 hours before you attempt to validate encryption after you change a DEP or the first time you assign a DEP to a mailbox.</span></span>
  
<span data-ttu-id="b0f19-406">Utilizzare il cmdlet Get-MailboxStatistics per determinare se una cassetta postale viene crittografata.</span><span class="sxs-lookup"><span data-stu-id="b0f19-406">Use the Get-MailboxStatistics cmdlet to determine if a mailbox is encrypted.</span></span>
  
```
Get-MailboxStatistics -Identity <GeneralMailboxOrMailUserIdParameter> | fl IsEncrypted
```

<span data-ttu-id="b0f19-407">La proprietà IsEncrypted restituisce il valore **true** se la cassetta postale è crittografata e il valore **false** se la cassetta postale non verrà crittografata.</span><span class="sxs-lookup"><span data-stu-id="b0f19-407">The IsEncrypted property returns a value of **true** if the mailbox is encrypted and a value of **false** if the mailbox is not encrypted.</span></span> 

<span data-ttu-id="b0f19-p160">Il tempo necessario per completare spostamenti delle cassette postali dipende dal numero di cassette postali a cui si assegna una protezione esecuzione programmi per la prima volta, nonché le dimensioni delle cassette postali. Se le cassette postali non sono state crittografate dopo una settimana dal momento in cui sono assegnati i programmi, avviare uno spostamento delle cassette postali per le cassette postali non crittografate tramite il cmdlet New-MoveRequest.</span><span class="sxs-lookup"><span data-stu-id="b0f19-p160">The time to complete mailbox moves depends on the number of mailboxes to which you assign a DEP for the first time, as well as the size of the mailboxes. If the mailboxes have not been encrypted after a week from the time you assigned the DEP, initiate a mailbox move for the unencrypted mailboxes by using the New-MoveRequest cmdlet.</span></span>

```
New-MoveRequest <mailbox alias>
``` 

## <a name="office-365-setting-up-customer-key-for-sharepoint-online-and-onedrive-for-business"></a><span data-ttu-id="b0f19-410">Office 365: Impostazione di chiave cliente per SharePoint Online e OneDrive for Business</span><span class="sxs-lookup"><span data-stu-id="b0f19-410">Office 365: Setting up Customer Key for SharePoint Online and OneDrive for Business</span></span>
<span data-ttu-id="b0f19-411"><a name="AzureSteps"> </a></span><span class="sxs-lookup"><span data-stu-id="b0f19-411"></span></span>

<span data-ttu-id="b0f19-p161">Prima di iniziare, verificare di aver completato le attività necessarie per configurare Azure chiave cassaforte. Per informazioni, vedere [completare le attività in Azure chiave cassaforte e FastTrack Microsoft per la chiave cliente](controlling-your-data-using-customer-key.md#AzureSteps) .</span><span class="sxs-lookup"><span data-stu-id="b0f19-p161">Before you begin, ensure that you have completed the tasks required to set up Azure Key Vault. See [Complete tasks in Azure Key Vault and Microsoft FastTrack for Customer Key](controlling-your-data-using-customer-key.md#AzureSteps) for information.</span></span> 
  
<span data-ttu-id="b0f19-414">Per configurare chiave cliente per SharePoint Online e OneDrive for Business, è necessario eseguire la procedura seguente per una connessione remota in SharePoint Online con Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b0f19-414">To set up Customer Key for SharePoint Online and OneDrive for Business, you will need to perform these steps by remotely connecting to SharePoint Online with Windows PowerShell.</span></span>
  
### <a name="create-a-data-encryption-policy-dep-for-each-sharepoint-online-and-onedrive-for-business-geo"></a><span data-ttu-id="b0f19-415">Creare un criterio di crittografia dei dati (DEP) per ogni SharePoint Online e OneDrive per Business geo</span><span class="sxs-lookup"><span data-stu-id="b0f19-415">Create a data encryption policy (DEP) for each SharePoint Online and OneDrive for Business geo</span></span>
<span data-ttu-id="b0f19-416"><a name="CreateDEP4SPOODfB"> </a></span><span class="sxs-lookup"><span data-stu-id="b0f19-416"></span></span>

<span data-ttu-id="b0f19-p162">Una protezione esecuzione programmi sono associata a un set di chiavi archiviate nell'archivio chiave Azure. Si applicano una protezione esecuzione programmi per tutti i dati in un'unica posizione geografica, denominata anche un livello geografico. Se si utilizza la funzionalità multi-geo di Office 365 (attualmente in anteprima), è possibile creare una protezione esecuzione programmi per ogni livello geografico. Se non si utilizza multi-geo, è possibile creare una protezione esecuzione programmi in Office 365 per l'utilizzo con SharePoint Online e OneDrive for Business. Office 365 utilizzerà quindi le chiavi identificate nella protezione esecuzione programmi per crittografare i dati in tale livello geografico. Per creare i programmi, è necessario gli URI cassaforte chiave ottenuto in precedenza. Per istruzioni, vedere [ottenere l'URI per ogni tasto cassaforte chiave Azure](controlling-your-data-using-customer-key.md#GetKeyURI) .</span><span class="sxs-lookup"><span data-stu-id="b0f19-p162">A DEP is associated with a set of keys stored in Azure Key Vault. You apply a DEP to all of your data in one geographic location, also called a geo. If you use the multi-geo feature of Office 365 (currently in Preview), you can create one DEP per geo. If you are not using multi-geo, you can create one DEP in Office 365 for use with SharePoint Online and OneDrive for Business. Office 365 will then use the keys identified in the DEP to encrypt your data in that geo. To create the DEP, you need the Key Vault URIs you obtained earlier. See [Obtain the URI for each Azure Key Vault key](controlling-your-data-using-customer-key.md#GetKeyURI) for instructions.</span></span> 
  
<span data-ttu-id="b0f19-p163">Ricordare! Quando si creano una protezione esecuzione programmi, si specificano due chiavi che si trovano in due diversi archivi di chiave di Azure. Verificare che queste chiavi si trovano in due regioni Azure separate per garantire la ridondanza geografica.</span><span class="sxs-lookup"><span data-stu-id="b0f19-p163">Remember! When you create a DEP, you specify two keys that reside in two different Azure Key Vaults. Ensure that these keys are located in two separate Azure regions to ensure geo-redundancy.</span></span>
  
<span data-ttu-id="b0f19-427">Per creare una protezione esecuzione programmi, è necessario per la connessione a SharePoint Online in modalità remota tramite Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b0f19-427">To create a DEP, you need to remotely connect to SharePoint Online by using Windows PowerShell.</span></span>
  
1. <span data-ttu-id="b0f19-428">Nel computer locale, utilizzando un ufficio o della scuola dell'account che disponga delle autorizzazioni di amministratore globale dell'organizzazione Office 365, [connettersi a Powershell per SharePoint Online](https://technet.microsoft.com/library/fp161372.aspx).</span><span class="sxs-lookup"><span data-stu-id="b0f19-428">On your local computer, using a work or school account that has global administrator permissions in your Office 365 organization, [Connect to SharePoint Online Powershell](https://technet.microsoft.com/library/fp161372.aspx).</span></span>
    
2. <span data-ttu-id="b0f19-429">In Microsoft SharePoint Online Management Shell, eseguire il cmdlet [Register-SPODataEncryptionPolicy](https://technet.microsoft.com/library/mt843950.aspx) come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="b0f19-429">In the Microsoft SharePoint Online Management Shell, run the [Register-SPODataEncryptionPolicy](https://technet.microsoft.com/library/mt843950.aspx) cmdlet as follows:</span></span> 
    
   ```
   Register-SPODataEncryptionPolicy -Identity <SPOAdminSiteUrl> -PrimaryKeyVaultName <PrimaryKeyVaultName> -PrimaryKeyName <PrimaryKeyName> -PrimaryKeyVersion <PrimaryKeyVersion> -SecondaryKeyVaultName <SecondaryKeyVaultName> -SecondaryKeyName <SecondaryKeyName> -SecondaryKeyVersion <SecondaryKeyVersion>
   ```

   <span data-ttu-id="b0f19-p164">Quando si registrano i programmi, crittografia inizia dati contenuti nel livello geografico. L'operazione può richiedere alcuni minuti.</span><span class="sxs-lookup"><span data-stu-id="b0f19-p164">When you register the DEP, encryption begins on the data in the geo. This can take some time.</span></span>
    
### <a name="validate-encryption-of-group-sites-team-sites-and-onedrive-for-business"></a><span data-ttu-id="b0f19-432">Convalidare la crittografia del gruppo di siti, siti dei Team e OneDrive for Business</span><span class="sxs-lookup"><span data-stu-id="b0f19-432">Validate encryption of Group Sites, Team Sites, and OneDrive for Business</span></span>
<span data-ttu-id="b0f19-433"><a name="validateencryptionSPO"> </a></span><span class="sxs-lookup"><span data-stu-id="b0f19-433"></span></span>

<span data-ttu-id="b0f19-434">È possibile controllare lo stato di crittografia eseguendo il cmdlet Get-SPODataEncryptionPolicy come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="b0f19-434">You can check on the status of encryption by running the Get-SPODataEncryptionPolicy cmdlet as follows:</span></span>
  
```
Get-SPODataEncryptionPolicy -Identity <SPOAdminSiteUrl>
```

<span data-ttu-id="b0f19-435">L'output del cmdlet include:</span><span class="sxs-lookup"><span data-stu-id="b0f19-435">The output from this cmdlet includes:</span></span>
  
- <span data-ttu-id="b0f19-436">L'URI della chiave primaria.</span><span class="sxs-lookup"><span data-stu-id="b0f19-436">The URI of the primary key.</span></span>
    
- <span data-ttu-id="b0f19-437">L'URI della chiave secondaria.</span><span class="sxs-lookup"><span data-stu-id="b0f19-437">The URI of the secondary key.</span></span>
    
- <span data-ttu-id="b0f19-p165">Specifica lo stato di crittografia per il livello geografico. I possibili stati includono:</span><span class="sxs-lookup"><span data-stu-id="b0f19-p165">The encryption status for the geo. Possible states include:</span></span>
    
  - <span data-ttu-id="b0f19-440">**Annullare la registrazione:** La crittografia chiave clienti non è stato ancora applicata.</span><span class="sxs-lookup"><span data-stu-id="b0f19-440">**Unregistered:** Customer Key encryption has not yet been applied.</span></span> 
    
  - <span data-ttu-id="b0f19-p166">**Registrazione:** È stata applicata la crittografia chiave cliente e i file sono in corso la crittografia. Se il livello geografico questo stato, si verranno anche da visualizzare informazioni su quale percentuale di siti nel geo siano stati completati in modo che è possibile monitorare avanzamento di crittografia.</span><span class="sxs-lookup"><span data-stu-id="b0f19-p166">**Registering:** Customer Key encryption has been applied and your files are in the process of being encrypted. If your geo is in this state, you'll also be shown information on what percentage of sites in the geo are complete so that you can monitor encryption progress.</span></span> 
    
  - <span data-ttu-id="b0f19-443">**Registrato:** È stata applicata la crittografia chiave cliente e tutti i file in tutti i siti sono stati crittografati.</span><span class="sxs-lookup"><span data-stu-id="b0f19-443">**Registered:** Customer Key encryption has been applied, and all files in all sites have been encrypted.</span></span> 
    
  - <span data-ttu-id="b0f19-p167">**In sequenza:** Una chiave (in inglese) è in corso. Se il livello geografico questo stato, si verranno anche da visualizzare informazioni su quale percentuale di siti di aver completato l'operazione roll chiave in modo che è possibile monitorare l'avanzamento delle.</span><span class="sxs-lookup"><span data-stu-id="b0f19-p167">**Rolling:** A key roll is in progress. If your geo is in this state, you'll also be shown information on what percentage of sites have completed the key roll operation so that you can monitor progress.</span></span> 
    
## <a name="managing-customer-key-for-office-365"></a><span data-ttu-id="b0f19-446">Gestione dei clienti chiave per Office 365</span><span class="sxs-lookup"><span data-stu-id="b0f19-446">Managing Customer Key for Office 365</span></span>
<span data-ttu-id="b0f19-447"><a name="ManageCustomerKey"> </a></span><span class="sxs-lookup"><span data-stu-id="b0f19-447"></span></span>

<span data-ttu-id="b0f19-448">Dopo aver configurato chiave cliente per Office 365, è possibile eseguire le altre attività di gestione.</span><span class="sxs-lookup"><span data-stu-id="b0f19-448">After you've set up Customer Key for Office 365, you can perform these additional management tasks.</span></span>
  
- [<span data-ttu-id="b0f19-449">Ripristinare le chiavi Azure chiave cassaforte</span><span class="sxs-lookup"><span data-stu-id="b0f19-449">Restore Azure Key Vault keys</span></span>](controlling-your-data-using-customer-key.md#RestoreAzureKeyVaultKeys)
    
- [<span data-ttu-id="b0f19-450">Ripristino dello stato o la rotazione di una chiave in Azure chiave cassaforte al cliente chiave</span><span class="sxs-lookup"><span data-stu-id="b0f19-450">Rolling or rotating a key in Azure Key Vault that you use with Customer Key</span></span>](controlling-your-data-using-customer-key.md#RollCKkey)
    
- [<span data-ttu-id="b0f19-451">Gestire le autorizzazioni cassaforte chiave</span><span class="sxs-lookup"><span data-stu-id="b0f19-451">Manage key vault permissions</span></span>](controlling-your-data-using-customer-key.md#Managekeyvaultperms)
    
- [<span data-ttu-id="b0f19-452">Determinare la protezione esecuzione programmi assegnato a una cassetta postale</span><span class="sxs-lookup"><span data-stu-id="b0f19-452">Determine the DEP assigned to a mailbox</span></span>](controlling-your-data-using-customer-key.md#DeterminemailboxDEP)
    
### <a name="restore-azure-key-vault-keys"></a><span data-ttu-id="b0f19-453">Ripristinare le chiavi Azure chiave cassaforte</span><span class="sxs-lookup"><span data-stu-id="b0f19-453">Restore Azure Key Vault keys</span></span>
<span data-ttu-id="b0f19-454"><a name="RestoreAzureKeyVaultKeys"> </a></span><span class="sxs-lookup"><span data-stu-id="b0f19-454"></span></span>

<span data-ttu-id="b0f19-p168">Prima di eseguire un ripristino, utilizzare le funzionalità di ripristino fornite dall'eliminazione temporanea. Tutti i tasti utilizzati con chiave cliente sono necessari disporre di eliminazione temporanea abilitato. Eliminazione temporanea funge da un Cestino secondario e consente il ripristino fino a 90 giorni senza la necessità di ripristino. Ripristino in genere necessaria solo in casi extreme o insoliti, ad esempio se si perde il tasto o tasto cassaforte. Se è necessario ripristinare una chiave per l'utilizzo con clienti chiave in Azure PowerShell, utilizzare il cmdlet Restore-AzureKeyVaultKey come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="b0f19-p168">Before performing a restore, use the recovery capabilities provided by soft delete. All keys that are used with Customer Key are required to have soft delete enabled. Soft delete acts like a recycle bin and allows recovery for up to 90 days without the need to restore. Restore should only be required in extreme or unusual circumstances, for example if the key or key vault is lost. If you must restore a key for use with Customer Key, in Azure PowerShell, run the Restore-AzureKeyVaultKey cmdlet as follows:</span></span>
  
```
Restore-AzureKeyVaultKey -VaultName <vaultname> -InputFile <filename>
```

<span data-ttu-id="b0f19-460">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="b0f19-460">For example:</span></span>
  
```
Restore-AzureKeyVaultKey -VaultName Contoso-O365EX-NA-VaultA1 -InputFile Contoso-O365EX-NA-VaultA1-Key001-Backup-20170802.backup
```

<span data-ttu-id="b0f19-p169">Se esiste già una chiave con lo stesso nome nell'archivio di chiave, l'operazione di ripristino avrà esito negativo. Ripristino AzureKeyVaultKey Ripristina tutti i metadati per il tasto inclusi il nome della chiave e tutte le versioni principali.</span><span class="sxs-lookup"><span data-stu-id="b0f19-p169">If a key with the same name already exists in the key vault, the restore operation will fail. Restore-AzureKeyVaultKey restores all key versions and all metadata for the key including the key name.</span></span>
  
### <a name="rolling-or-rotating-a-key-in-azure-key-vault-that-you-use-with-customer-key"></a><span data-ttu-id="b0f19-463">Ripristino dello stato o la rotazione di una chiave in Azure chiave cassaforte al cliente chiave</span><span class="sxs-lookup"><span data-stu-id="b0f19-463">Rolling or rotating a key in Azure Key Vault that you use with Customer Key</span></span>
<span data-ttu-id="b0f19-464"><a name="RollCKkey"> </a></span><span class="sxs-lookup"><span data-stu-id="b0f19-464"></span></span>

<span data-ttu-id="b0f19-p170">In sequenza tasti non è richiesto uno cassaforte chiave Azure o dalla chiave cliente. Tasti protetti con un modulo di sicurezza hardware sono inoltre praticamente a compromessi. Anche se una chiave radice sono in possesso di un attore dannoso non esiste alcun modo realizzabili dell'utilizzo per decrittografare i dati, in quanto solo il codice di Office 365 è in grado di utilizzarlo. Ripristino dello stato di una chiave è tuttavia supportato dalla chiave cliente.</span><span class="sxs-lookup"><span data-stu-id="b0f19-p170">Rolling keys is not required by either Azure Key Vault or by Customer Key. In addition, keys that are protected with an HSM are virtually impossible to compromise. Even if a root key were in the possession of a malicious actor there is no feasible means of using it to decrypt data, since only Office 365 code knows how to use it. However, rolling a key is supported by Customer Key.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="b0f19-p171">Solo ripristinare una chiave di crittografia utilizzati con chiave cliente quando è presente un motivo deselezionare tecnico o requisiti di conformità indicano che è necessario ripristinare la chiave. Inoltre, non eliminare eventuali chiavi o sono state associate ai criteri. Quando si esegue rollback le chiavi, non è presente il contenuto crittografato con le chiavi precedenti. Ad esempio, mentre le cassette postali attive verranno nuovamente crittografate frequentemente, inattivo, le cassette postali disconnesse e su disattivato possono essere crittografate con le chiavi precedenti. SharePoint Online consente di eseguire il backup del contenuto per scopi di ripristino e il ripristino, in modo che potrebbero ancora essere archiviato il contenuto utilizzando le chiavi precedenti.</span><span class="sxs-lookup"><span data-stu-id="b0f19-p171">Only roll an encryption key that you use with Customer Key when a clear technical reason exists or a compliance requirement dictates that you have to roll the key. In addition, do not delete any keys that are or were associated with policies. When you roll your keys, there will be content encrypted with the previous keys. For example, while active mailboxes will be re-encrypted frequently, inactive, disconnected, and disabled mailboxes may still be encrypted with the previous keys. SharePoint Online performs backup of content for restore and recovery purposes, so there may still be archived content using older keys. </span></span><br/> <span data-ttu-id="b0f19-p172">Per garantire la sicurezza dei dati, SharePoint Online consentirà non più di un'operazione di rollback chiave siano in corso alla volta. Se si desidera ripristinare entrambe le chiavi in un archivio di chiave, è necessario attendere la prima operazione (in inglese) chiave per completa. È consigliabile scaglionare le operazioni (in inglese) chiave intervalli diversi, in modo che questo non è un problema.</span><span class="sxs-lookup"><span data-stu-id="b0f19-p172">To ensure the safety of your data, SharePoint Online will allow no more than one Key Roll operation to be in progress at a time. If you want to roll both of the keys in a key vault, you'll need to wait for the first key roll operation to fully complete. Our recommendation is to stagger your key roll operations at different intervals, so that this is not an issue.</span></span> 
  
<span data-ttu-id="b0f19-p173">Quando si esegue il rollback un tasto, si richiede una nuova versione di una chiave esistente. Per richiedere una nuova versione di una chiave esistente, utilizzare il cmdlet stesso, [Add-AzureKeyVaultKey](https://docs.microsoft.com/powershell/module/AzureRM.KeyVault/Add-AzureKeyVaultKey), con la stessa sintassi utilizzata per creare la chiave in primo luogo.</span><span class="sxs-lookup"><span data-stu-id="b0f19-p173">When you roll a key, you are requesting a new version of an existing key. In order to request a new version of an existing key, you use the same cmdlet, [Add-AzureKeyVaultKey](https://docs.microsoft.com/powershell/module/AzureRM.KeyVault/Add-AzureKeyVaultKey), with the same syntax that you used to create the key in the first place.</span></span>
  
<span data-ttu-id="b0f19-479">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="b0f19-479">For example:</span></span>
  
```
Add-AzureKeyVaultKey -VaultName Contoso-O365EX-NA-VaultA1 -Name Contoso-O365EX-NA-VaultA1-Key001 -Destination HSM -KeyOps @('wrapKey','unwrapKey') -NotBefore (Get-Date -Date "12/27/2016 12:01 AM")
```

<span data-ttu-id="b0f19-p174">In questo esempio, in quanto non esiste una chiave denominata **Contoso-O365EX-NA-VaultA1-Key001** già nell'archivio di **Contoso-O365EX-NA-VaultA1** , verrà creata una nuova versione chiave. Il metodo aggiunge una nuova versione chiave. Questa operazione consente di mantenere le versioni precedenti chiave nella cronologia delle versioni della chiave, in modo che i dati crittografati in precedenza con tale chiave possono comunque essere decrittografati. Dopo avere completato un tasto qualsiasi associato a una protezione esecuzione programmi di distribuzione, è necessario eseguire un cmdlet aggiuntive per garantire che chiave cliente inizia con la nuova chiave.</span><span class="sxs-lookup"><span data-stu-id="b0f19-p174">In this example, since a key named **Contoso-O365EX-NA-VaultA1-Key001** already exists in the **Contoso-O365EX-NA-VaultA1** vault, a new key version will be created. The operation adds a new key version. This operation preserves the previous key versions in the key's version history, so that data previously encrypted with that key can still be decrypted. Once you have completed rolling any key that is associated with a DEP, you must then run an additional cmdlet to ensure Customer Key begins using the new key.</span></span> 
  
#### <a name="enable-exchange-online-and-skype-for-business-to-use-a-new-key-after-you-roll-or-rotate-keys-in-azure-key-vault"></a><span data-ttu-id="b0f19-484">Abilitare Exchange Online e Skype per le aziende utilizzano una nuova chiave dopo aver rollback o ruotato tasti in Azure chiave cassaforte</span><span class="sxs-lookup"><span data-stu-id="b0f19-484">Enable Exchange Online and Skype for Business to use a new key after you roll or rotate keys in Azure Key Vault</span></span>

<span data-ttu-id="b0f19-485">Quando si ripristina una delle chiavi Azure chiave cassaforte associate a una protezione esecuzione programmi utilizzati con Exchange Online e Skype per le aziende, è necessario eseguire il comando seguente per aggiornare la protezione esecuzione programmi e attivare Office 365 iniziare a utilizzare la nuova chiave.</span><span class="sxs-lookup"><span data-stu-id="b0f19-485">When you roll either of the Azure Key Vault keys associated with a DEP used with Exchange Online and Skype for Business, you must run the following command to update the DEP and enable Office 365 to start using the new key.</span></span>
  
<span data-ttu-id="b0f19-486">Per indicare a clienti chiave da utilizzare la nuova chiave per crittografare le cassette postali in Office 365, eseguire il cmdlet Set-DataEncryptionPolicy come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="b0f19-486">To instruct Customer Key to use the new key to encrypt mailboxes in Office 365 run the Set-DataEncryptionPolicy cmdlet as follows:</span></span>
  
```
Set-DataEncryptionPolicy <policyname> -Refresh 
```

<span data-ttu-id="b0f19-p175">All'interno di 48 ore, le cassette postali attive crittografate tramite il criterio verrà associate il tasto aggiornato. Utilizzare i passaggi descritti in [Determine Protezione esecuzione programmi assegnato a una cassetta postale](controlling-your-data-using-customer-key.md#DeterminemailboxDEP) per verificare il valore della proprietà DataEncryptionPolicyID per la cassetta postale. Il valore di questa proprietà verrà modificato dopo che è stata applicata la chiave aggiornata.</span><span class="sxs-lookup"><span data-stu-id="b0f19-p175">Within 48 hours, the active mailboxes encrypted using this policy will become associated with the updated key. Use the steps in [Determine the DEP assigned to a mailbox](controlling-your-data-using-customer-key.md#DeterminemailboxDEP) to check the value for the DataEncryptionPolicyID property for the mailbox. The value for this property will change once the updated key has been applied.</span></span> 
  
#### <a name="enable-sharepoint-online-and-onedrive-for-business-to-use-a-new-key-after-you-roll-or-rotate-keys-in-azure-key-vault"></a><span data-ttu-id="b0f19-490">Abilitare SharePoint Online e OneDrive for Business utilizzare una nuova chiave dopo aver rollback o ruotato tasti in Azure chiave cassaforte</span><span class="sxs-lookup"><span data-stu-id="b0f19-490">Enable SharePoint Online and OneDrive for Business to use a new key after you roll or rotate keys in Azure Key Vault</span></span>

<span data-ttu-id="b0f19-491">Quando si ripristina una delle chiavi Azure chiave cassaforte associate a una protezione esecuzione programmi utilizzato con SharePoint Online e OneDrive for Business, è necessario eseguire il cmdlet [Update-SPODataEncryptionPolicy](https://technet.microsoft.com/library/mt843948.aspx) per aggiornare la protezione esecuzione programmi e attivare Office 365 iniziare a utilizzare la nuova chiave.</span><span class="sxs-lookup"><span data-stu-id="b0f19-491">When you roll either of the Azure Key Vault keys associated with a DEP used with SharePoint Online and OneDrive for Business, you must run the [Update-SPODataEncryptionPolicy](https://technet.microsoft.com/library/mt843948.aspx) cmdlet to update the DEP and enable Office 365 to start using the new key.</span></span> 
  
```
Update-SPODataEncryptionPolicy -Identity <SPOAdminSiteUrl> -KeyVaultName <ReplacementKeyVaultName> -KeyName <ReplacementKeyName> -KeyVersion <ReplacementKeyVersion> -KeyType <Primary | Secondary>
```

<span data-ttu-id="b0f19-p176">Verrà avviata l'operazione (in inglese) principali per SharePoint Online e OneDrive for Business. Questa azione non è immediata. Per visualizzare lo stato di avanzamento della chiave di eseguire il rollback operazione, eseguire il cmdlet Get-SPODataEncryptionPolicy come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="b0f19-p176">This will start the key roll operation for SharePoint Online and OneDrive for Business. This action is not immediate. To see the progress of the key roll operation, run the Get-SPODataEncryptionPolicy cmdlet as follows:</span></span>
  
```
Get-SPODataEncryptionPolicy -Identity <SPOAdminSiteUrl>
```

### <a name="manage-key-vault-permissions"></a><span data-ttu-id="b0f19-495">Gestire le autorizzazioni cassaforte chiave</span><span class="sxs-lookup"><span data-stu-id="b0f19-495">Manage key vault permissions</span></span>
<span data-ttu-id="b0f19-496"><a name="Managekeyvaultperms"> </a></span><span class="sxs-lookup"><span data-stu-id="b0f19-496"></span></span>

<span data-ttu-id="b0f19-p177">Sono disponibili diversi cmdlet che consentono di visualizzare e, se necessario, rimuovere le autorizzazioni cassaforte chiave. Potrebbe essere necessario rimuovere le autorizzazioni, ad esempio, quando un dipendente lascia il team.</span><span class="sxs-lookup"><span data-stu-id="b0f19-p177">Several cmdlets are available that enable you to view and, if necessary, remove key vault permissions. You might need to remove permissions, for example, when an employee leaves the team.</span></span>
  
<span data-ttu-id="b0f19-499">Per visualizzare le autorizzazioni cassaforte chiave, eseguire il cmdlet Get-AzureRmKeyVault:</span><span class="sxs-lookup"><span data-stu-id="b0f19-499">To view key vault permissions, run the Get-AzureRmKeyVault cmdlet:</span></span>
  
```
Get-AzureRmKeyVault -VaultName <vaultname>
```

<span data-ttu-id="b0f19-500">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="b0f19-500">For example:</span></span>
  
```
Get-AzureRmKeyVault -VaultName Contoso-O365EX-NA-VaultA1
```

<span data-ttu-id="b0f19-501">Per rimuovere le autorizzazioni dell'amministratore, eseguire il cmdlet Remove-AzureRmKeyVaultAccessPolicy:</span><span class="sxs-lookup"><span data-stu-id="b0f19-501">To remove an administrator's permissions, run the Remove-AzureRmKeyVaultAccessPolicy cmdlet:</span></span>
  
```
Remove-AzureRmKeyVaultAccessPolicy -VaultName <vaultname> 
-UserPrincipalName <UPN of user>
```

<span data-ttu-id="b0f19-502">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="b0f19-502">For example:</span></span>
  
```
Remove-AzureRmKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 
-UserPrincipalName alice@contoso.com
```

### <a name="determine-the-dep-assigned-to-a-mailbox"></a><span data-ttu-id="b0f19-503">Determinare la protezione esecuzione programmi assegnato a una cassetta postale</span><span class="sxs-lookup"><span data-stu-id="b0f19-503">Determine the DEP assigned to a mailbox</span></span>
<span data-ttu-id="b0f19-504"><a name="DeterminemailboxDEP"> </a></span><span class="sxs-lookup"><span data-stu-id="b0f19-504"></span></span>

<span data-ttu-id="b0f19-p178">Per determinare la protezione esecuzione programmi assegnato a una cassetta postale, utilizzare il cmdlet Get-MailboxStatistics. Il cmdlet restituisce l'identificatore univoco (GUID).</span><span class="sxs-lookup"><span data-stu-id="b0f19-p178">To determine the DEP assigned to a mailbox, use the Get-MailboxStatistics cmdlet. The cmdlet returns a unique identifier (GUID).</span></span>
  
```
Get-MailboxStatistics -Identity <GeneralMailboxOrMailUserIdParameter> | fl DataEncryptionPolicyID
```

<span data-ttu-id="b0f19-p179">Dove *GeneralMailboxOrMailUserIdParameter* specifica una cassetta postale. Per ulteriori informazioni sul cmdlet Get-MailboxStatistics, vedere [Get-MailboxStatistics](https://technet.microsoft.com/library/bb124612%28v=exchg.160%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="b0f19-p179">Where *GeneralMailboxOrMailUserIdParameter* specifies a mailbox. For more information about the Get-MailboxStatistics cmdlet, see [Get-MailboxStatistics](https://technet.microsoft.com/library/bb124612%28v=exchg.160%29.aspx).</span></span>
  
<span data-ttu-id="b0f19-509">Utilizzare il GUID per trovare il nome descrittivo della protezione esecuzione programmi a cui viene assegnata alla cassetta postale eseguendo il cmdlet seguente.</span><span class="sxs-lookup"><span data-stu-id="b0f19-509">Use the GUID to find out the friendly name of the DEP to which the mailbox is assigned by running the following cmdlet.</span></span>
  
```
Get-DataEncryptionPolicy <GUID>
```

<span data-ttu-id="b0f19-510">Dove *GUID* è il GUID restituito dal cmdlet Get-MailboxStatistics nel passaggio precedente.</span><span class="sxs-lookup"><span data-stu-id="b0f19-510">Where *GUID* is the GUID returned by the Get-MailboxStatistics cmdlet in the previous step.</span></span> 
  

