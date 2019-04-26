---
title: Distribuire un connettore per archiviare i dati di Facebook in Office 365
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
ROBOTS: NOINDEX, NOFOLLOW
description: Gli amministratori possono configurare un connettore nativo per l'importazione e l'archiviazione di pagine business di Facebook in Office 365. Dopo aver importato i dati in Office 365, è possibile utilizzare le funzionalità di conformità, ad esempio la conservazione legale, la ricerca di contenuto e i criteri di ritenzione per gestire la governance dei dati di Facebook dell'organizzazione.
ms.openlocfilehash: d90714072bdeb609fe4af14208476bfa2f60b6d7
ms.sourcegitcommit: 63a10dc5ffa9d709fac437d3fc9e554b1bcd826f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/25/2019
ms.locfileid: "33308075"
---
# <a name="deploy-a-connector-to-archive-facebook-data-in-office-365"></a><span data-ttu-id="d0625-104">Distribuire un connettore per archiviare i dati di Facebook in Office 365</span><span class="sxs-lookup"><span data-stu-id="d0625-104">Deploy a connector to archive Facebook data in Office 365</span></span>

<span data-ttu-id="d0625-105">Questo articolo contiene il processo dettagliato per la distribuzione di un connettore che utilizza il servizio di importazione di Office 365 per importare i dati da pagine business di Facebook a Office 365.</span><span class="sxs-lookup"><span data-stu-id="d0625-105">This article contains the step-by-step process to deploy a connector that uses the Office 365 Import service to import data from Facebook Business pages to Office 365.</span></span> <span data-ttu-id="d0625-106">Per una panoramica generale di questo processo e un elenco dei prerequisiti necessari per distribuire un connettore Facebook, vedere [utilizzare i connettori di esempio per archiviare i dati di terze parti in Office 365](archive-third-party-data-with-sample-connector.md).</span><span class="sxs-lookup"><span data-stu-id="d0625-106">For a high-level overview of this process and a list of prerequisites required to deploy a Facebook connector, see [Use sample connectors to archive third-party data in Office 365](archive-third-party-data-with-sample-connector.md).</span></span> 


## <a name="step-1-download-the-package"></a><span data-ttu-id="d0625-107">Passaggio 1: scaricare il pacchetto</span><span class="sxs-lookup"><span data-stu-id="d0625-107">Step 1: Download the package</span></span>

<span data-ttu-id="d0625-108">Scaricare il pacchetto precompilato dalla sezione release del repository all' <https://github.com/Microsoft/m365-sample-connector-csharp-aspnet/releases>indirizzo.</span><span class="sxs-lookup"><span data-stu-id="d0625-108">Download the prebuilt package from repository’s Release section at <https://github.com/Microsoft/m365-sample-connector-csharp-aspnet/releases>.</span></span> <span data-ttu-id="d0625-109">Nella versione più recente, scaricare il file zip denominato **SampleConnector. zip**.</span><span class="sxs-lookup"><span data-stu-id="d0625-109">Under the latest release, download the zip file named **SampleConnector.zip**.</span></span> <span data-ttu-id="d0625-110">Il file zip verrà caricato in Azure nel passaggio 4.</span><span class="sxs-lookup"><span data-stu-id="d0625-110">You will upload this zip file to Azure in Step 4.</span></span>

## <a name="step-2-create-an-app-in-azure-active-directory"></a><span data-ttu-id="d0625-111">Passaggio 2: creare un'app in Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="d0625-111">Step 2: Create an app in Azure Active Directory</span></span>

1. <span data-ttu-id="d0625-112">Accedere a <https://portal.azure.com> e accedere con le credenziali di un account di amministratore globale di Office 365.</span><span class="sxs-lookup"><span data-stu-id="d0625-112">Go to <https://portal.azure.com> and sign in using the credentials of an Office 365 global admin account.</span></span>

    ![Creare un'app in AAD](media/FBCimage1.png)

2. <span data-ttu-id="d0625-114">Nel riquadro di spostamento a sinistra, fare clic su **Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="d0625-114">In the left navigation pane, click **Azure Active Directory**.</span></span>

    ![](media/FBCimage2.png)

3. <span data-ttu-id="d0625-115">Nel riquadro di spostamento a sinistra, fare clic su **registrazioni app (anteprima)** e quindi fare clic su **nuova registrazione**.</span><span class="sxs-lookup"><span data-stu-id="d0625-115">In the left navigation pane, click **App registrations (Preview)** and then click **New registration**.</span></span>

    ![](media/FBCimage3.png)

4. <span data-ttu-id="d0625-116">Registrare l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="d0625-116">Register the application.</span></span> <span data-ttu-id="d0625-117">In URI di reindirizzamento, selezionare Web nell'elenco a discesa tipo di applicazione e <https://portal.azure.com> quindi digitare nella casella per l'URI.</span><span class="sxs-lookup"><span data-stu-id="d0625-117">Under Redirect URI, select Web in the application type dropdown list and then type <https://portal.azure.com> in the box for the URI.</span></span>

   ![](media/FBCimage4.png)

5. <span data-ttu-id="d0625-118">Copiare l'ID dell' **applicazione (client)** e la **Directory (tenant)** e salvarli in un file di testo o in un'altra posizione sicura.</span><span class="sxs-lookup"><span data-stu-id="d0625-118">Copy the **Application (client) ID** and **Directory (tenant) ID** and save them to a text file or other safe location.</span></span> <span data-ttu-id="d0625-119">Questi ID verranno utilizzati nei passaggi successivi.</span><span class="sxs-lookup"><span data-stu-id="d0625-119">You’ll use these IDs in later steps.</span></span>

   ![](media/FBCimage5.png)

6. <span data-ttu-id="d0625-120">Vai a **certificati & segreti per la nuova app.**</span><span class="sxs-lookup"><span data-stu-id="d0625-120">Go to **Certificates & secrets for the new app.**</span></span>

   ![](media/FBCimage6.png)

7. <span data-ttu-id="d0625-121">Fare clic su **nuovo client segreto**</span><span class="sxs-lookup"><span data-stu-id="d0625-121">Click **New client secret**</span></span>

   ![](media/FBCimage7.png)

8. <span data-ttu-id="d0625-122">Creare un nuovo segreto.</span><span class="sxs-lookup"><span data-stu-id="d0625-122">Create a new secret.</span></span> <span data-ttu-id="d0625-123">Nella casella Descrizione digitare il segreto e quindi scegliere un periodo di scadenza.</span><span class="sxs-lookup"><span data-stu-id="d0625-123">In the description box, type the secret and then choose an expiration period.</span></span> 

    ![](media/FBCimage8.png)

9. <span data-ttu-id="d0625-124">Copiare il valore del segreto e salvarlo in un file di testo o in un altro percorso di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="d0625-124">Copy the value of the secret and save it to a text file or other storage location.</span></span> <span data-ttu-id="d0625-125">Si tratta del segreto dell'applicazione AAD che verrà utilizzato nei passaggi successivi.</span><span class="sxs-lookup"><span data-stu-id="d0625-125">This is the AAD application secret that you will use in later steps.</span></span>

   ![](media/FBCimage9.png)

10. <span data-ttu-id="d0625-126">Andare a **manifest** e copiare il identifierUris (denominato anche URI dell'applicazione AAD) come evidenziato nella schermata seguente.</span><span class="sxs-lookup"><span data-stu-id="d0625-126">Go to **Manifest** and copy the identifierUris (which is also called the AAD application Uri) as highlighted in the following screenshot.</span></span> <span data-ttu-id="d0625-127">Copiare l'URI dell'applicazione AAD in un file di testo o in un altro percorso di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="d0625-127">Copy the AAD application Uri to a text file or other storage location.</span></span> <span data-ttu-id="d0625-128">Verrà utilizzato nel passaggio 6.</span><span class="sxs-lookup"><span data-stu-id="d0625-128">You’ll use it in Step 6.</span></span>

   ![](media/FBCimage10.png)

## <a name="step-3-create-an-azure-storage-account"></a><span data-ttu-id="d0625-129">Passaggio 3: creare un account di archiviazione di Azure</span><span class="sxs-lookup"><span data-stu-id="d0625-129">Step 3: Create an Azure storage account</span></span>

1. <span data-ttu-id="d0625-130">Passare alla Home page di Azure per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="d0625-130">Go to the Azure home page for your organization.</span></span>

    ![](media/FBCimage11.png)

2. <span data-ttu-id="d0625-131">Fare clic su **Crea una risorsa** e digitare **account di archiviazione** nella casella di ricerca.</span><span class="sxs-lookup"><span data-stu-id="d0625-131">Click **Create a resource** and they type **storage account** in the search box.</span></span>

    ![](media/FBCimage12.png)

3. <span data-ttu-id="d0625-132">Fare clic su **spazio di archiviazione**e quindi su **account di archiviazione**.</span><span class="sxs-lookup"><span data-stu-id="d0625-132">Click **Storage**, and then click **Storage account**.</span></span>

    ![](media/FBCimage13.png)

4. <span data-ttu-id="d0625-133">Nella pagina **Crea account di archiviazione** , nella casella sottoscrizione, selezionare **pay-as-you-go** o **versione di valutazione gratuita** a seconda del tipo di sottoscrizione di Azure di cui si dispone.</span><span class="sxs-lookup"><span data-stu-id="d0625-133">On the **Create storage account** page, in the Subscription box, select **Pay-As-You-Go** or **Free Trial** depending on which type of Azure subscription you have.</span></span> <span data-ttu-id="d0625-134">Selezionare o creare un gruppo di risorse.</span><span class="sxs-lookup"><span data-stu-id="d0625-134">Then select or create a resource group.</span></span>

    ![](media/FBCimage14.png)

5. <span data-ttu-id="d0625-135">Digitare un nome per l'account di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="d0625-135">Type a name for the storage account.</span></span>

    ![](media/FBCimage15.png)

6. <span data-ttu-id="d0625-136">Esaminare e quindi fare clic su **Crea** per creare l'account di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="d0625-136">Review and then click **Create** to create the storage account.</span></span>

    ![](media/FBCimage16.png)

7. <span data-ttu-id="d0625-137">Dopo alcuni istanti, fare clic su **Aggiorna** e quindi su **Vai a risorsa** per passare all'account di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="d0625-137">After a few moments, click **Refresh** and then click **Go to resource** to navigate to the storage account.</span></span>

    ![](media/FBCimage17.png)

8. <span data-ttu-id="d0625-138">Fare clic su **tasti di accesso** nel riquadro di spostamento a sinistra.</span><span class="sxs-lookup"><span data-stu-id="d0625-138">Click **Access keys** in the left navigation pane.</span></span>

    ![](media/FBCimage18.png)

9. <span data-ttu-id="d0625-139">Copiare una **stringa di connessione** e salvarla in un file di testo o in un altro percorso di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="d0625-139">Copy a **Connection string** and save it to a text file or other storage location.</span></span> <span data-ttu-id="d0625-140">Questa operazione viene utilizzata durante la creazione di una risorsa Web App.</span><span class="sxs-lookup"><span data-stu-id="d0625-140">You’ll use this when creating a web app resource.</span></span>

    ![](media/FBCimage19.png)

## <a name="step-4-create-a-new-web-app-resource-in-azure"></a><span data-ttu-id="d0625-141">Passaggio 4: creare una nuova risorsa Web App in Azure</span><span class="sxs-lookup"><span data-stu-id="d0625-141">Step 4: Create a new web app resource in Azure</span></span>

1. <span data-ttu-id="d0625-142">Nella **Home** page del portale di Azure, fare clic su **Crea una \> risorsa \> tutto Web App**.</span><span class="sxs-lookup"><span data-stu-id="d0625-142">On the **Home** page in the Azure portal, click **Create a resource \> Everything \> Web app**.</span></span> <span data-ttu-id="d0625-143">Nella pagina **Web App** fare clic su **Crea**.</span><span class="sxs-lookup"><span data-stu-id="d0625-143">On the **Web app** page, click **Create**.</span></span> 

   ![](media/FBCimage20.png)

2. <span data-ttu-id="d0625-144">Inserire i dettagli (come illustrato di seguito) e quindi creare l'applicazione Web.</span><span class="sxs-lookup"><span data-stu-id="d0625-144">Fill in the details (as shown below) and then create the Web app.</span></span> <span data-ttu-id="d0625-145">Si noti che il nome immesso nella casella **nome app** verrà utilizzato per creare l'URL del servizio app di Azure; ad esempio fbconnector.azurewebsites.NET.</span><span class="sxs-lookup"><span data-stu-id="d0625-145">Note that the name that you enter in the **App name** box will be used to create the Azure app service URL; for example fbconnector.azurewebsites.net.</span></span>

   ![](media/FBCimage21.png)

3. <span data-ttu-id="d0625-146">Passare alla nuova risorsa Web App creata, fare clic su **Impostazioni applicazione** nel riquadro di spostamento sinistro.</span><span class="sxs-lookup"><span data-stu-id="d0625-146">Go to the newly created web app resource, click **Application Settings** in the left navigation pane.</span></span> <span data-ttu-id="d0625-147">In Impostazioni applicazione fare clic su Aggiungi nuova impostazione e quindi aggiungere le tre impostazioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="d0625-147">Under Application settings, click Add new setting and add the following three settings.</span></span> <span data-ttu-id="d0625-148">Utilizzare i valori (copiati nel file di testo dai passaggi precedenti):</span><span class="sxs-lookup"><span data-stu-id="d0625-148">Use the values (that you copied to the text file from the previous steps):</span></span> 

    - <span data-ttu-id="d0625-149">**APISecretKey** – è possibile digitare qualsiasi valore come segreto.</span><span class="sxs-lookup"><span data-stu-id="d0625-149">**APISecretKey** – You can type any value as the secret.</span></span> <span data-ttu-id="d0625-150">Questa operazione verrà utilizzata per accedere all'applicazione Web del connettore nel passaggio 7.</span><span class="sxs-lookup"><span data-stu-id="d0625-150">This will be used to access the connector web app in Step 7.</span></span>

    - <span data-ttu-id="d0625-151">**StorageAccountConnectionString** : l'URI della stringa di connessione copiato dopo la creazione dell'account di archiviazione di Azure nel passaggio 3.</span><span class="sxs-lookup"><span data-stu-id="d0625-151">**StorageAccountConnectionString** – The connection string Uri that you copied after creating the Azure storage account in Step 3.</span></span>

    - <span data-ttu-id="d0625-152">**tenantId** -l'ID tenant dell'organizzazione di Office 365 copiato dopo aver creato l'app Facebook Connector in Azure Active Directory nel passaggio 2.</span><span class="sxs-lookup"><span data-stu-id="d0625-152">**tenantId** – The tenant ID of your Office 365 organization that you copied after creating the Facebook connector app in Azure Active Directory in Step 2.</span></span>

    ![](media/FBCimage22.png)

4. <span data-ttu-id="d0625-153">In **Impostazioni generali**, fare clic **su** avanti accanto a **sempre attiva**.</span><span class="sxs-lookup"><span data-stu-id="d0625-153">Under **General settings**, click **On** next to the **Always On**.</span></span> <span data-ttu-id="d0625-154">Fare clic su **Salva** nella parte superiore della pagina per salvare le impostazioni di Applicaton.</span><span class="sxs-lookup"><span data-stu-id="d0625-154">Click **Save** at the top of the page to save applicaton settings.</span></span>

   ![](media/FBCimage23.png)

5. <span data-ttu-id="d0625-155">Il passaggio finale consiste nel caricare il codice sorgente dell'app del connettore in Azure scaricato nel passaggio 1.</span><span class="sxs-lookup"><span data-stu-id="d0625-155">The final step is to upload the connector app source code to Azure that you downloaded in Step 1.</span></span> <span data-ttu-id="d0625-156">In un Web browser, passare a https://<AzureAppResourceName>. SCM.azurewebsites.NET/ZipDeployUi.</span><span class="sxs-lookup"><span data-stu-id="d0625-156">In a web browser, go to https://<AzureAppResourceName>.scm.azurewebsites.net/ZipDeployUi.</span></span> <span data-ttu-id="d0625-157">Ad esempio, se il nome della risorsa dell'app di Azure (denominato nel passaggio 2 di questa sezione) è **fbconnector**, si passa a https://fbconnector.scm.azurewebsites.net/ZipDeployUi.</span><span class="sxs-lookup"><span data-stu-id="d0625-157">For example, if the name of your Azure app resource (which you named in step 2 in this section) is **fbconnector**, then you would go to https://fbconnector.scm.azurewebsites.net/ZipDeployUi.</span></span> 

6. <span data-ttu-id="d0625-158">Trascinare e rilasciare il SampleConnector. zip (scaricato nel passaggio 1) in questa pagina.</span><span class="sxs-lookup"><span data-stu-id="d0625-158">Drag and drop the SampleConnector.zip (that you downloaded in Step 1) to this page.</span></span> <span data-ttu-id="d0625-159">Dopo che i file sono stati caricati e la distribuzione ha esito positivo, la pagina avrà un aspetto simile alla schermata seguente.</span><span class="sxs-lookup"><span data-stu-id="d0625-159">After the files are uploaded and the deployment is successful, the page will look similar to the following screenshot.</span></span>

   ![](media/FBCimage24.png)

## <a name="step-5-register-the-facebook-app"></a><span data-ttu-id="d0625-160">Passaggio 5: registrare l'app Facebook</span><span class="sxs-lookup"><span data-stu-id="d0625-160">Step 5: Register the Facebook app</span></span>

1. <span data-ttu-id="d0625-161">Accedere a <https://developers.facebook.com> , eseguire l'accesso usando le credenziali per l'account per le pagine business di Facebook dell'organizzazione e quindi fare clic su **Aggiungi nuova app**.</span><span class="sxs-lookup"><span data-stu-id="d0625-161">Go to <https://developers.facebook.com> , log in using the credentials for the account for your organization’s Facebook Business pages, and then click **Add New App**.</span></span>

   ![](media/FBCimage25.png)

2. <span data-ttu-id="d0625-162">Creare un nuovo ID app.</span><span class="sxs-lookup"><span data-stu-id="d0625-162">Create a new app ID.</span></span>

   ![](media/FBCimage26.png)

3. <span data-ttu-id="d0625-163">Nel riquadro di spostamento a sinistra, fare clic su **Aggiungi prodotti** e quindi fare clic su **Configura** nella sezione **login Facebook** .</span><span class="sxs-lookup"><span data-stu-id="d0625-163">In the left navigation pane, click **Add Products** and then click **Set Up** in the **Facebook Login** tile.</span></span>

   ![](media/FBCimage27.png)

4. <span data-ttu-id="d0625-164">Nella pagina integrazione account di accesso di Facebook fare clic su **Web**.</span><span class="sxs-lookup"><span data-stu-id="d0625-164">On the Integrate Facebook Login page, click **Web**.</span></span>

   ![](media/FBCimage28.png)

5. <span data-ttu-id="d0625-165">Aggiungere l'URL del servizio app di Azure; ad esempio https://fbconnector.azurewebsites.net.</span><span class="sxs-lookup"><span data-stu-id="d0625-165">Add the Azure app service URL; for example https://fbconnector.azurewebsites.net.</span></span>

   ![](media/FBCimage29.png)

6. <span data-ttu-id="d0625-166">Completare la sezione Guida introduttiva della configurazione dell'account di accesso di Facebook.</span><span class="sxs-lookup"><span data-stu-id="d0625-166">Complete the QuickStart section of the Facebook Login setup.</span></span>

   ![](media/FBCimage30.png)

7. <span data-ttu-id="d0625-167">Nel riquadro di spostamento a sinistra in **login Facebook**, fare clic su **Impostazioni**e aggiungere l'URI di reindirizzamento OAuth nella casella valido degli URI di **Reindirizzamento di OAuth** . utilizzare il formato \*\* \<connectorserviceuri>/views/FacebookOAuth\*\*, in cui il valore di connectorserviceuri è l'URL del servizio app di Azure per l'organizzazione. ad esempio https://fbconnector.azurewebsites.net.</span><span class="sxs-lookup"><span data-stu-id="d0625-167">In the left navigation pane under **Facebook Login**, click **Settings**, and add the OAuth redirect URI in the **Valid OAuth Redirect URIs** box; use the format **\<connectorserviceuri>/Views/FacebookOAuth**, where the value for connectorserviceuri is the Azure app service URL for your organization; for example https://fbconnector.azurewebsites.net.</span></span>

   ![](media/FBCimage31.png)

8. <span data-ttu-id="d0625-168">Nel riquadro di spostamento a sinistra, fare clic su **Aggiungi prodotti** e quindi fare clic su webhook **.**</span><span class="sxs-lookup"><span data-stu-id="d0625-168">In the left navigation pane, click **Add Products** and then click **Webhooks.**</span></span> <span data-ttu-id="d0625-169">Nel menu a discesa della **pagina** , fare clic su **pagina**.</span><span class="sxs-lookup"><span data-stu-id="d0625-169">In the **Page** pull-down menu, click **Page**.</span></span> 

   ![](media/FBCimage32.png)

9. <span data-ttu-id="d0625-170">Aggiungere l'URL di callback di Webhook e aggiungere un token di verifica.</span><span class="sxs-lookup"><span data-stu-id="d0625-170">Add Webhooks Callback URL and add a verify token.</span></span> <span data-ttu-id="d0625-171">Il formato dell'URL di callback, utilizzare il formato \*\* <connectorserviceuri>/API/FbPageWebhook\*\*, in cui il valore di connectorserviceuri è l'URL del servizio app di Azure per l'organizzazione. ad esempio https://fbconnector.azurewebsites.net.</span><span class="sxs-lookup"><span data-stu-id="d0625-171">The format of the callback URL, use the format **<connectorserviceuri>/api/FbPageWebhook**, where the value for connectorserviceuri is the Azure app service URL for your organization; for example https://fbconnector.azurewebsites.net.</span></span> 

    <span data-ttu-id="d0625-172">Il token di verifica dovrebbe essere simile a una password complessa.</span><span class="sxs-lookup"><span data-stu-id="d0625-172">The verify token should similar to a strong password.</span></span> <span data-ttu-id="d0625-173">Copiare il token di verifica in un file di testo o in un altro percorso di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="d0625-173">Copy the verify token to a text file or other storage location.</span></span>

     ![](media/FBCimage33.png)

10. <span data-ttu-id="d0625-174">Testare e sottoscrivere l'endpoint per il feed.</span><span class="sxs-lookup"><span data-stu-id="d0625-174">Test and subscribe to the endpoint for feed.</span></span>

    ![](media/FBCimage34.png)

11. <span data-ttu-id="d0625-175">Aggiungere un URL di privacy, un'icona dell'app e un utilizzo aziendale.</span><span class="sxs-lookup"><span data-stu-id="d0625-175">Add a privacy URL, app icon, and business use.</span></span> <span data-ttu-id="d0625-176">Inoltre, copiare l'ID app e l'applicazione segreta in un file di testo o in un altro percorso di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="d0625-176">Also, copy the app ID and app secret to a text file or other storage location.</span></span>

    ![](media/FBCimage35.png)

12. <span data-ttu-id="d0625-177">Rendere pubblico l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="d0625-177">Make the app public.</span></span>

    ![](media/FBCimage36.png)

13. <span data-ttu-id="d0625-178">Aggiungere un utente al ruolo di amministratore o tester.</span><span class="sxs-lookup"><span data-stu-id="d0625-178">Add user to the admin or tester role.</span></span>

    ![](media/FBCimage37.png)

14. <span data-ttu-id="d0625-179">Aggiungere l'autorizzazione di **accesso al contenuto pubblico della pagina** .</span><span class="sxs-lookup"><span data-stu-id="d0625-179">Add the **Page Public Content Access** permission.</span></span>

    ![](media/FBCimage38.png)

15. <span data-ttu-id="d0625-180">Aggiungere l'autorizzazione Manage Pages.</span><span class="sxs-lookup"><span data-stu-id="d0625-180">Add Manage Pages permission.</span></span>

    ![](media/FBCimage39.png)

16. <span data-ttu-id="d0625-181">Ottenere l'applicazione recensita da Facebook.</span><span class="sxs-lookup"><span data-stu-id="d0625-181">Get the application reviewed by Facebook.</span></span>

    ![](media/FBCimage40.png)

## <a name="step-6-configure-the-connector-web-app"></a><span data-ttu-id="d0625-182">Passaggio 6: configurare l'applicazione Web del connettore</span><span class="sxs-lookup"><span data-stu-id="d0625-182">Step 6: Configure the connector web app</span></span>

1. <span data-ttu-id="d0625-183">Passare a https://\<AzureAppResourceName>. azurewebsites. NET (dove AzureAppResourceName è il nome della risorsa di Azure App denominata nel passaggio 4), ad esempio, se il nome è **fbconnector**, andare a https://fbconnector.azurewebsites.net.</span><span class="sxs-lookup"><span data-stu-id="d0625-183">Go to https://\<AzureAppResourceName>.azurewebsites.net (where AzureAppResourceName is the name of your Azure app resource that you named in Step 4) For example, if the name is **fbconnector**, go to https://fbconnector.azurewebsites.net.</span></span> <span data-ttu-id="d0625-184">La Home page dell'app avrà lo stesso aspetto della schermata seguente.</span><span class="sxs-lookup"><span data-stu-id="d0625-184">The home page of the app will look like the following screenshot.</span></span>


  ![](media/FBCimage41.png)

2. <span data-ttu-id="d0625-185">Fare clic su **Configura** per visualizzare una pagina di accesso.</span><span class="sxs-lookup"><span data-stu-id="d0625-185">Click **Configure** to display a sign in page.</span></span>
 
   ![](media/FBCimage42.png)

3. <span data-ttu-id="d0625-186">Nella casella ID tenant digitare o incollare l'ID tenant (ottenuto nel passaggio 2).</span><span class="sxs-lookup"><span data-stu-id="d0625-186">In the Tenant Id box, type or paste your tenant Id (that you obtained in Step 2).</span></span> <span data-ttu-id="d0625-187">Nella casella password digitare o incollare il APISecretKey (ottenuto nel passaggio 2), quindi fare clic su **imposta impostazioni di configurazione** per visualizzare la pagina **Dettagli di configurazione** .</span><span class="sxs-lookup"><span data-stu-id="d0625-187">In the password box, type or paste the APISecretKey (that you obtained in Step 2), and then click **Set Configuration Settings** to display the **Configuration Details** page.</span></span>

    ![](media/FBCimage43.png)


4. <span data-ttu-id="d0625-188">In **Dettagli di configurazione**, immettere le impostazioni di configurazione seguenti</span><span class="sxs-lookup"><span data-stu-id="d0625-188">Under **Configuration Details**, enter the following configuration settings</span></span> 

   - <span data-ttu-id="d0625-189">**ID applicazione Facebook** -ID app per l'applicazione Facebook ottenuta al passaggio 5.</span><span class="sxs-lookup"><span data-stu-id="d0625-189">**Facebook application ID** - The app ID for the Facebook application that you obtained in Step 5.</span></span>
   - <span data-ttu-id="d0625-190">**Segreto dell'applicazione Facebook** : il segreto dell'app per l'applicazione Facebook ottenuta al passaggio 5.</span><span class="sxs-lookup"><span data-stu-id="d0625-190">**Facebook application secret** - The app secret for the Facebook application that you obtained in Step 5.</span></span>
   - <span data-ttu-id="d0625-191">I webhook di **Facebook verificano** il token, ovvero il token di verifica creato nel passaggio 5.</span><span class="sxs-lookup"><span data-stu-id="d0625-191">**Facebook webhooks verify token** - The verify token that you created in Step 5.</span></span>
   - <span data-ttu-id="d0625-192">**ID applicazione AAD** -ID applicazione per l'app Azure Active Directory creata al passaggio 2</span><span class="sxs-lookup"><span data-stu-id="d0625-192">**AAD application ID** - The application ID for the Azure Active Directory app that you created in Step 2</span></span>
   - <span data-ttu-id="d0625-193">**Segreto dell'applicazione AAD** : il valore del segreto di APISecretKey creato nel passaggio 4.</span><span class="sxs-lookup"><span data-stu-id="d0625-193">**AAD application secret** - The value for the APISecretKey secret that you created in Step 4.</span></span>
   - <span data-ttu-id="d0625-194">**URI dell'applicazione AAD** -URI dell'applicazione AAD ottenuto nel passaggio 2; ad esempio, https://microsoft.onmicrosoft.com/2688yu6n-12q3-23we-e3ee-121111123213.</span><span class="sxs-lookup"><span data-stu-id="d0625-194">**AAD application Uri** - The AAD application Uri obtained in Step 2; for example, https://microsoft.onmicrosoft.com/2688yu6n-12q3-23we-e3ee-121111123213.</span></span>
   - <span data-ttu-id="d0625-195">**Chiave di strumentazione Insights app** -lasciare vuota questa casella.</span><span class="sxs-lookup"><span data-stu-id="d0625-195">**App insights instrumentation key** - Leave this box blank.</span></span>

5. <span data-ttu-id="d0625-196">Fare clic su **Salva** per salvare le impostazioni del connettore.</span><span class="sxs-lookup"><span data-stu-id="d0625-196">Click **Save** to save the connector settings.</span></span>

## <a name="step-7-set-up-a-custom-connector-in-the-security--compliance-center"></a><span data-ttu-id="d0625-197">Passaggio 7: configurare un connettore personalizzato nel centro sicurezza & Compliance</span><span class="sxs-lookup"><span data-stu-id="d0625-197">Step 7: Set up a custom connector in the Security & Compliance Center</span></span>

1. <span data-ttu-id="d0625-198">Andare a <https://protection.office.com> e quindi fare clic su data **governance \> Import \> Archive data di terze parti**.</span><span class="sxs-lookup"><span data-stu-id="d0625-198">Go to <https://protection.office.com> and then click **Data governance \> Import \> Archive third-party data**.</span></span>

   ![](media/FBCimage44.png)

2.  <span data-ttu-id="d0625-199">Fare clic su **Aggiungi connettore** e quindi su **personalizzato**.</span><span class="sxs-lookup"><span data-stu-id="d0625-199">Click **Add a connector** and then click **Custom**.</span></span>

    ![](media/FBCimage46.png)

3.  <span data-ttu-id="d0625-200">Nella pagina **Aggiungi applicazione del connettore** , immettere le informazioni seguenti e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="d0625-200">On the **Add Connector App** page, enter the following information and then click **Next**.</span></span>

    - <span data-ttu-id="d0625-201">Nella prima casella digitare un nome per il connettore, ad esempio **Facebook**.</span><span class="sxs-lookup"><span data-stu-id="d0625-201">In the first box, type a name for the connector, such as **Facebook**.</span></span>
    - <span data-ttu-id="d0625-202">Nella seconda casella digitare o incollare il valore dell'APISecretKey aggiunto nel passaggio 4.</span><span class="sxs-lookup"><span data-stu-id="d0625-202">In the second box, type or paste the value of the APISecretKey that you added in Step 4.</span></span>
    - <span data-ttu-id="d0625-203">Nella terza casella, digitare l'URL del servizio app di Azure; ad esempio **https://fbconnector.azurewebsites.net**.</span><span class="sxs-lookup"><span data-stu-id="d0625-203">In the third box, type of paste the Azure app service URL; for example **https://fbconnector.azurewebsites.net**.</span></span>
    
    ![](media/FBCimage47.png)

4.  <span data-ttu-id="d0625-204">Fare clic su **login con app connettore**.</span><span class="sxs-lookup"><span data-stu-id="d0625-204">Click **Login with Connector App**.</span></span>

    ![](media/FBCimage45.png)

5. <span data-ttu-id="d0625-205">Digitare o incollare di nuovo il APISecretKey e quindi fare clic su **accedi al servizio connettore**.</span><span class="sxs-lookup"><span data-stu-id="d0625-205">Type or paste the APISecretKey again and then click  **Login to Connector Service**.</span></span>

   ![](media/FBCimage48.png)


6. <span data-ttu-id="d0625-206">Fare clic su **login con Facebook.**</span><span class="sxs-lookup"><span data-stu-id="d0625-206">Click **Login with Facebook.**</span></span>

   ![](media/FBCimage49.png)

7. <span data-ttu-id="d0625-207">Nella pagina **Accedi alla pagina Facebook** accedere usando le credenziali per l'account per le pagine business di Facebook dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="d0625-207">On the **Log in to Facebook** page, log in using the credentials for the account for your organization’s Facebook Business pages.</span></span> <span data-ttu-id="d0625-208">Assicurarsi che l'account Facebook a cui è stato effettuato l'accesso sia assegnato il ruolo di amministratore per le pagine business di Facebook dell'organizzazione</span><span class="sxs-lookup"><span data-stu-id="d0625-208">Make sure the Facebook account you logged in to is assigned the admin role for your organization’s Facebook Business pages</span></span>

   ![](media/FBCimage50.png)

8. <span data-ttu-id="d0625-209">Fare clic su **Seleziona pagine** per scegliere le pagine business dell'organizzazione che si desidera archiviare in Office 365.</span><span class="sxs-lookup"><span data-stu-id="d0625-209">Click **Select Pages** to choose your organization’s business pages that you want to archive in Office 365.</span></span>

   ![](media/FBCimage51.png)

9. <span data-ttu-id="d0625-210">Viene visualizzato un elenco delle pagine business gestite dall'account di Facebook in cui è stato effettuato l'accesso.</span><span class="sxs-lookup"><span data-stu-id="d0625-210">A list of the Business pages managed by the Facebook account that you logged in to is displayed.</span></span> <span data-ttu-id="d0625-211">Selezionare la pagina da archiviare e quindi fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="d0625-211">Select the page to archive and then click **Save**.</span></span>

    ![](media/FBCimage52.png)

10. <span data-ttu-id="d0625-212">Fare clic su **fine** per uscire dal programma di installazione dell'app del servizio connettore.</span><span class="sxs-lookup"><span data-stu-id="d0625-212">Click **Finish** to exit the setup of the connector service app.</span></span>

    ![](media/FBCimage53.png)

11. <span data-ttu-id="d0625-213">Nella pagina **Imposta filtri** è possibile applicare un filtro per importare e archiviare gli elementi di una determinata età.</span><span class="sxs-lookup"><span data-stu-id="d0625-213">On the **Set Filters** page, you can apply a filter to import (and archive) items that are a certain age.</span></span> <span data-ttu-id="d0625-214">Fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="d0625-214">Click **Next**.</span></span>

    ![](media/FBCimage54.png)

12. <span data-ttu-id="d0625-215">Nella pagina **Imposta account di archiviazione** selezionare la cassetta postale di Office 365 in cui verranno importate le pagine di business di Facebook selezionate in precedenza.</span><span class="sxs-lookup"><span data-stu-id="d0625-215">On the **Set Storage Account** page, select the Office 365 mailbox that the items from the Facebook Business pages that you previously selected will be imported to.</span></span>

    ![](media/FBCimage55.png)

13. <span data-ttu-id="d0625-216">Esaminare le impostazioni e quindi fare clic su **fine** per completare la configurazione del connettore nel centro sicurezza & Compliance.</span><span class="sxs-lookup"><span data-stu-id="d0625-216">Review your settings and then click **Finish** to complete the connector setup in the Security & Compliance Center.</span></span>

    ![](media/FBCimage56.png)

14. <span data-ttu-id="d0625-217">Passare alla pagina di **archiviazione dei dati di terze parti** per visualizzare lo stato di avanzamento del processo di importazione.</span><span class="sxs-lookup"><span data-stu-id="d0625-217">Go to the **Archive third-party data** page to see the progress of the import process.</span></span>

    ![](media/FBCimage58.png)
