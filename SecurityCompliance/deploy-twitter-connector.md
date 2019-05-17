---
title: Distribuire un connettore per archiviare i dati di Twitter in Office 365
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
description: Gli amministratori possono configurare un connettore nativo per importare e archiviare i dati di Twitter in Office 365. Dopo aver importato i dati in Office 365, è possibile utilizzare le funzionalità di conformità, ad esempio la conservazione legale, la ricerca di contenuto e i criteri di ritenzione per gestire la governance dei dati di Twitter dell'organizzazione.
ms.openlocfilehash: 2f9d4842a834858b40e1d788f34f4fb8b2d5b9fd
ms.sourcegitcommit: 5bd7a97aeab1c89e0a3660ba7bdb3200224107a1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/16/2019
ms.locfileid: "34103963"
---
# <a name="deploy-a-connector-to-archive-twitter-data-in-office-365"></a><span data-ttu-id="cc796-104">Distribuire un connettore per archiviare i dati di Twitter in Office 365</span><span class="sxs-lookup"><span data-stu-id="cc796-104">Deploy a connector to archive Twitter data in Office 365</span></span>

<span data-ttu-id="cc796-105">Questo articolo contiene il processo dettagliato per la distribuzione di un connettore che utilizza il servizio di importazione di Office 365 per importare i dati dall'account Twitter dell'organizzazione a Office 365.</span><span class="sxs-lookup"><span data-stu-id="cc796-105">This article contains the step-by-step process to deploy a connector that uses the Office 365 Import service to import data from your organization's Twitter account to Office 365.</span></span> <span data-ttu-id="cc796-106">Per una panoramica generale di questo processo e un elenco dei prerequisiti necessari per distribuire un connettore Twitter, vedere [use a sample Connector to Archive Twitter data in Office 365 (Preview)](archive-twitter-data-with-sample-connector.md).</span><span class="sxs-lookup"><span data-stu-id="cc796-106">For a high-level overview of this process and a list of prerequisites required to deploy a Twitter connector, see [Use a sample connector to archive Twitter data in Office 365 (Preview)](archive-twitter-data-with-sample-connector.md).</span></span> 

## <a name="step-1-download-the-package"></a><span data-ttu-id="cc796-107">Passaggio 1: scaricare il pacchetto</span><span class="sxs-lookup"><span data-stu-id="cc796-107">Step 1: Download the package</span></span>

<span data-ttu-id="cc796-108">Scaricare il pacchetto precompilato dalla sezione Release nell'archivio GitHub all'indirizzo [https://github.com/microsoft/m365-sample-twitter-connector-csharp-aspnet/releases](https://github.com/microsoft/m365-sample-twitter-connector-csharp-aspnet/releases).</span><span class="sxs-lookup"><span data-stu-id="cc796-108">Download the prebuilt package from the Release section in the GitHub repository at [https://github.com/microsoft/m365-sample-twitter-connector-csharp-aspnet/releases](https://github.com/microsoft/m365-sample-twitter-connector-csharp-aspnet/releases).</span></span> <span data-ttu-id="cc796-109">Nella versione più recente, scaricare il file zip denominato **SampleConnector. zip**.</span><span class="sxs-lookup"><span data-stu-id="cc796-109">Under the latest release, download the zip file named **SampleConnector.zip**.</span></span> <span data-ttu-id="cc796-110">Il file zip verrà caricato in Azure nel passaggio 4.</span><span class="sxs-lookup"><span data-stu-id="cc796-110">You will upload this zip file to Azure in Step 4.</span></span>

## <a name="step-2-create-an-app-in-azure-active-directory"></a><span data-ttu-id="cc796-111">Passaggio 2: creare un'app in Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="cc796-111">Step 2: Create an app in Azure Active Directory</span></span>

1. <span data-ttu-id="cc796-112">Accedere a <https://portal.azure.com> e accedere con le credenziali di un account di amministratore globale di Office 365.</span><span class="sxs-lookup"><span data-stu-id="cc796-112">Go to <https://portal.azure.com> and sign in using the credentials of an Office 365 global admin account.</span></span>

   ![](media/TCimage01.png)

2. <span data-ttu-id="cc796-113">Nel riquadro di spostamento a sinistra, fare clic su **Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="cc796-113">In the left navigation pane, click **Azure Active Directory**.</span></span>

   ![](media/TCimage02.png)

3. <span data-ttu-id="cc796-114">Nel riquadro di spostamento a sinistra, fare clic su **registrazioni app (anteprima)** e quindi fare clic su **nuova registrazione**.</span><span class="sxs-lookup"><span data-stu-id="cc796-114">In the left navigation pane, click **App registrations (Preview)** and then click **New registration**.</span></span>

   ![](media/TCimage03.png)

4. <span data-ttu-id="cc796-115">Registrare l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="cc796-115">Register the application.</span></span> <span data-ttu-id="cc796-116">In **URI di reindirizzamento (facoltativo)** selezionare Web nell'elenco a discesa tipo di applicazione e quindi <https://portal.azure.com> digitare nella casella relativa all'URI.</span><span class="sxs-lookup"><span data-stu-id="cc796-116">Under **Redirect URI (optional)**, select Web in the application type dropdown list and then type <https://portal.azure.com> in the box for the URI.</span></span>

   ![](media/TCimage04.png)

5. <span data-ttu-id="cc796-117">Copiare l'ID dell' **applicazione (client)** e la **Directory (tenant)** e salvarli in un file di testo o in un'altra posizione sicura.</span><span class="sxs-lookup"><span data-stu-id="cc796-117">Copy the **Application (client) ID** and **Directory (tenant) ID** and save them to a text file or other safe location.</span></span> <span data-ttu-id="cc796-118">Questi ID verranno utilizzati nei passaggi successivi.</span><span class="sxs-lookup"><span data-stu-id="cc796-118">You’ll use these IDs in later steps.</span></span>

    ![](media/TCimage05.png)

6. <span data-ttu-id="cc796-119">Vai a **certificati & segreti per la nuova app** e in **segreti client** fare clic su **nuovo segreto client**.</span><span class="sxs-lookup"><span data-stu-id="cc796-119">Go to **Certificates & secrets for the new app** and under **Client secrets** click **New client secret**.</span></span>

   ![](media/TCimage06.png)

7. <span data-ttu-id="cc796-120">Creare un nuovo segreto.</span><span class="sxs-lookup"><span data-stu-id="cc796-120">Create a new secret.</span></span> <span data-ttu-id="cc796-121">Nella casella Descrizione digitare il segreto e quindi scegliere un periodo di scadenza.</span><span class="sxs-lookup"><span data-stu-id="cc796-121">In the description box, type the secret and then choose an expiration period.</span></span> 

   ![](media/TCimage08.png)

8. <span data-ttu-id="cc796-122">Copiare il valore del segreto e salvarlo in un file di testo o in un altro percorso di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="cc796-122">Copy the value of the secret and save it to a text file or other storage location.</span></span> <span data-ttu-id="cc796-123">Si tratta del segreto dell'applicazione AAD che verrà utilizzato nei passaggi successivi.</span><span class="sxs-lookup"><span data-stu-id="cc796-123">This is the AAD application secret that you will use in later steps.</span></span>

   ![](media/TCimage09.png)

9. <span data-ttu-id="cc796-124">Andare a **manifest** e copiare il identifierUris (denominato anche URI dell'applicazione AAD) come evidenziato nella schermata seguente.</span><span class="sxs-lookup"><span data-stu-id="cc796-124">Go to **Manifest** and copy the identifierUris (which is also called the AAD application Uri) as highlighted in the following screenshot.</span></span> <span data-ttu-id="cc796-125">Copiare l'URI dell'applicazione AAD in un file di testo o in un altro percorso di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="cc796-125">Copy the AAD application Uri to a text file or other storage location.</span></span> <span data-ttu-id="cc796-126">Verrà utilizzato nel passaggio 6.</span><span class="sxs-lookup"><span data-stu-id="cc796-126">You’ll use it in Step 6.</span></span>

    ![](media/TCimage10.png)

## <a name="step-3-create-an-azure-storage-account"></a><span data-ttu-id="cc796-127">Passaggio 3: creare un account di archiviazione di Azure</span><span class="sxs-lookup"><span data-stu-id="cc796-127">Step 3: Create an Azure storage account</span></span>

1.  <span data-ttu-id="cc796-128">Passare alla Home page di Azure per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="cc796-128">Go to the Azure home page for your organization.</span></span>

    ![](media/TCimage11.png)

2. <span data-ttu-id="cc796-129">Fare clic su **Crea una risorsa** e digitare **account di archiviazione** nella casella di ricerca.</span><span class="sxs-lookup"><span data-stu-id="cc796-129">Click **Create a resource** and they type **storage account** in the search box.</span></span>

   ![](media/TCimage12.png)

3. <span data-ttu-id="cc796-130">Fare clic su **spazio di archiviazione**e quindi su **account di archiviazione**.</span><span class="sxs-lookup"><span data-stu-id="cc796-130">Click **Storage**, and then click **Storage account**.</span></span>

   ![](media/TCimage13.png)

4. <span data-ttu-id="cc796-131">Nella pagina **Crea account di archiviazione** , nella casella sottoscrizione, selezionare **pay-as-you-go** o **versione di valutazione gratuita** a seconda del tipo di sottoscrizione di Azure di cui si dispone.</span><span class="sxs-lookup"><span data-stu-id="cc796-131">On the **Create storage account** page, in the Subscription box, select **Pay-As-You-Go** or **Free Trial** depending on which type of Azure subscription you have.</span></span> 

   ![](media/TCimage14.png)

5. <span data-ttu-id="cc796-132">Selezionare o creare un gruppo di risorse.</span><span class="sxs-lookup"><span data-stu-id="cc796-132">Select or create a resource group.</span></span>

   ![](media/TCimage15.png)

6. <span data-ttu-id="cc796-133">Digitare un nome per l'account di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="cc796-133">Type a name for the storage account.</span></span>

   ![](media/TCimage16.png)

7. <span data-ttu-id="cc796-134">Esaminare e quindi fare clic su **Crea** per creare l'account di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="cc796-134">Review and then click **Create** to create the storage account.</span></span>

   ![](media/TCimage17.png)

8. <span data-ttu-id="cc796-135">Dopo alcuni istanti, fare clic su **Aggiorna** e quindi su **Vai a risorsa** per passare all'account di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="cc796-135">After a few moments, click **Refresh** and then click **Go to resource** to navigate to the storage account.</span></span>

   ![](media/TCimage18.png)

9. <span data-ttu-id="cc796-136">Fare clic su **tasti di accesso** nel riquadro di spostamento a sinistra.</span><span class="sxs-lookup"><span data-stu-id="cc796-136">Click **Access keys** in the left navigation pane.</span></span>

   ![](media/TCimage19.png)

10. <span data-ttu-id="cc796-137">Copiare una **stringa di connessione** e salvarla in un file di testo o in un altro percorso di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="cc796-137">Copy a **Connection string** and save it to a text file or other storage location.</span></span> <span data-ttu-id="cc796-138">Questa operazione viene utilizzata quando si crea una risorsa Web App nel passaggio 4.</span><span class="sxs-lookup"><span data-stu-id="cc796-138">You’ll use this when creating a web app resource in Step 4.</span></span>

    ![](media/TCimage20.png)

## <a name="step-4-create-a-new-web-app-resource-in-azure"></a><span data-ttu-id="cc796-139">Passaggio 4: creare una nuova risorsa Web App in Azure</span><span class="sxs-lookup"><span data-stu-id="cc796-139">Step 4: Create a new web app resource in Azure</span></span>

1. <span data-ttu-id="cc796-140">Nella **Home** page del portale di Azure, fare clic su **Crea una \> risorsa \> tutto Web App**.</span><span class="sxs-lookup"><span data-stu-id="cc796-140">On the **Home** page in the Azure portal, click **Create a resource \> Everything \> Web app**.</span></span> <span data-ttu-id="cc796-141">Nella pagina **Web App** fare clic su **Crea**.</span><span class="sxs-lookup"><span data-stu-id="cc796-141">On the **Web app** page, click **Create**.</span></span>

   ![](media/TCimage21.png)

2. <span data-ttu-id="cc796-142">Inserire i dettagli (come illustrato di seguito) e quindi creare l'applicazione Web.</span><span class="sxs-lookup"><span data-stu-id="cc796-142">Fill in the details (as shown below) and then create the Web app.</span></span> <span data-ttu-id="cc796-143">Si noti che il nome immesso nella casella **nome app** verrà utilizzato per creare l'URL del servizio app di Azure; ad esempio twitterconnector.azurewebsites.net.</span><span class="sxs-lookup"><span data-stu-id="cc796-143">Note that the name that you enter in the **App name** box will be used to create the Azure app service URL; for example twitterconnector.azurewebsites.net.</span></span>

   ![](media/TCimage22.png)

3. <span data-ttu-id="cc796-144">Passare alla nuova risorsa Web App creata, fare clic su **Impostazioni applicazione** nel riquadro di spostamento sinistro.</span><span class="sxs-lookup"><span data-stu-id="cc796-144">Go to the newly created web app resource, click **Application Settings** in the left navigation pane.</span></span> <span data-ttu-id="cc796-145">In **Impostazioni applicazione**fare clic su **Aggiungi nuova impostazione** e quindi aggiungere le tre impostazioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="cc796-145">Under **Application settings**, click **Add new setting** and add the following three settings.</span></span> <span data-ttu-id="cc796-146">Utilizzare i valori (copiati nel file di testo dai passaggi precedenti):</span><span class="sxs-lookup"><span data-stu-id="cc796-146">Use the values (that you copied to the text file from the previous steps):</span></span> 

    - <span data-ttu-id="cc796-147">**APISecretKey** – è possibile digitare qualsiasi valore come segreto.</span><span class="sxs-lookup"><span data-stu-id="cc796-147">**APISecretKey** – You can type any value as the secret.</span></span> <span data-ttu-id="cc796-148">Questa operazione verrà utilizzata per accedere all'applicazione Web del connettore nel passaggio 7.</span><span class="sxs-lookup"><span data-stu-id="cc796-148">This will be used to access the connector web app in Step 7.</span></span>

    - <span data-ttu-id="cc796-149">**StorageAccountConnectionString** : l'URI della stringa di connessione copiato dopo la creazione dell'account di archiviazione di Azure nel passaggio 3.</span><span class="sxs-lookup"><span data-stu-id="cc796-149">**StorageAccountConnectionString** – The connection string Uri that you copied after creating the Azure storage account in Step 3.</span></span>

    - <span data-ttu-id="cc796-150">**tenantId** -l'ID tenant dell'organizzazione di Office 365 copiato dopo aver creato l'app Twitter Connector in Azure Active Directory nel passaggio 2.</span><span class="sxs-lookup"><span data-stu-id="cc796-150">**tenantId** – The tenant ID of your Office 365 organization that you copied after creating the Twitter connector app in Azure Active Directory in Step 2.</span></span>

    ![](media/TCimage23.png)

4. <span data-ttu-id="cc796-151">In **Impostazioni generali**, fare clic **su** avanti accanto a **sempre attiva**.</span><span class="sxs-lookup"><span data-stu-id="cc796-151">Under **General settings**, click **On** next to the **Always On**.</span></span> <span data-ttu-id="cc796-152">Fare clic su **Salva** nella parte superiore della pagina per salvare le impostazioni dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="cc796-152">Click **Save** at the top of the page to save the application settings.</span></span>

   ![](media/TCimage24.png)

5. <span data-ttu-id="cc796-153">Il passaggio finale consiste nel caricare il codice sorgente dell'app del connettore in Azure scaricato nel passaggio 1.</span><span class="sxs-lookup"><span data-stu-id="cc796-153">The final step is to upload the connector app source code to Azure that you downloaded in Step 1.</span></span> <span data-ttu-id="cc796-154">In un Web browser, passare a https://<AzureAppResourceName>. SCM.azurewebsites.NET/ZipDeployUi.</span><span class="sxs-lookup"><span data-stu-id="cc796-154">In a web browser, go to https://<AzureAppResourceName>.scm.azurewebsites.net/ZipDeployUi.</span></span> <span data-ttu-id="cc796-155">Ad esempio, se il nome della risorsa dell'app di Azure (denominato nel passaggio 2 di questa sezione) è **twitterconnector**, si passa a https://twitterconnector.scm.azurewebsites.net/ZipDeployUi.</span><span class="sxs-lookup"><span data-stu-id="cc796-155">For example, if the name of your Azure app resource (which you named in step 2 in this section) is **twitterconnector**, then you would go to https://twitterconnector.scm.azurewebsites.net/ZipDeployUi.</span></span>

6. <span data-ttu-id="cc796-156">Trascinare e rilasciare il SampleConnector. zip (scaricato nel passaggio 1) in questa pagina.</span><span class="sxs-lookup"><span data-stu-id="cc796-156">Drag and drop the SampleConnector.zip (that you downloaded in Step 1) to this page.</span></span> <span data-ttu-id="cc796-157">Dopo che i file sono stati caricati e la distribuzione ha esito positivo, la pagina avrà un aspetto simile alla schermata seguente.</span><span class="sxs-lookup"><span data-stu-id="cc796-157">After the files are uploaded and the deployment is successful, the page will look similar to the following screenshot.</span></span>

   ![](media/TCimage25.png)

## <a name="step-5-create-the-twitter-app"></a><span data-ttu-id="cc796-158">Passaggio 5: creare l'app Twitter</span><span class="sxs-lookup"><span data-stu-id="cc796-158">Step 5: Create the Twitter app</span></span>

1. <span data-ttu-id="cc796-159">Accedere a https://developer.twitter.com, eseguire l'accesso usando le credenziali per l'account di sviluppo per l'organizzazione, quindi fare clic su **app**.</span><span class="sxs-lookup"><span data-stu-id="cc796-159">Go to https://developer.twitter.com, log in using the credentials for the developer account for your organization, and then click **Apps**.</span></span>

   ![TCimage25-5. png](media/TCimage25-5.png)
2. <span data-ttu-id="cc796-161">Fare clic su **Crea un'app**.</span><span class="sxs-lookup"><span data-stu-id="cc796-161">Click **Create an app**.</span></span>
   
   ![](media/TCimage26.png)

3. <span data-ttu-id="cc796-162">In **Dettagli app**aggiungere informazioni sull'applicazione.</span><span class="sxs-lookup"><span data-stu-id="cc796-162">Under **App details**, add information about the application.</span></span>

   ![](media/TCimage27.png)

4. <span data-ttu-id="cc796-163">Nel dashboard per sviluppatori di Twitter, selezionare l'app appena creata e copiare l'ID app visualizzato e salvarlo in un file di testo o in un altro percorso di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="cc796-163">On the Twitter developer dashboard, select the app that you just created and copy the App ID that's displayed  and save it to a text file or other storage location.</span></span> <span data-ttu-id="cc796-164">Quindi fare clic su **Dettagli**.</span><span class="sxs-lookup"><span data-stu-id="cc796-164">Then click **Details**.</span></span>
   
   ![](media/TCimage28.png)

5. <span data-ttu-id="cc796-165">Nella scheda **tasti e token** , in **tasti API consumer** copiare la chiave segreta API e salvarla in un file di testo o in un altro percorso di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="cc796-165">On the **Keys and tokens** tab, under **Consumer API keys** copy the API secret key and save it to a text file or other storage location.</span></span> <span data-ttu-id="cc796-166">Fare quindi clic su **Crea** per generare un token di accesso e un segreto del token di accesso e copiarli in un file di testo o in un altro percorso di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="cc796-166">Then click **Create** to generate an access token and an access token secret, and copy these to a text file or other storage location.</span></span>
   
   ![](media/TCimage29.png)

   <span data-ttu-id="cc796-167">Fare quindi clic su **Crea** per generare un token di accesso e un segreto del token di accesso e copiarli in un file di testo o in un altro percorso di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="cc796-167">Then click **Create** to generate an access token and an access token secret, and copy these to a text file or other storage location.</span></span>

6. <span data-ttu-id="cc796-168">Fare clic sulla scheda **autorizzazioni** e configurare le autorizzazioni come illustrato nella schermata seguente:</span><span class="sxs-lookup"><span data-stu-id="cc796-168">Click the **Permissions** tab and configure the permissions as shown in the following screenshot:</span></span>

   ![](media/TCimage30.png)

7. <span data-ttu-id="cc796-169">Dopo aver salvato le impostazioni di autorizzazione, fare clic sulla scheda **Dettagli applicazione** e quindi fare clic su **modifica > modifica dettagli**.</span><span class="sxs-lookup"><span data-stu-id="cc796-169">After you save the permission settings, click the **App details** tab, and then click **Edit > Edit details**.</span></span>

   ![](media/TCimage31.png)

8. <span data-ttu-id="cc796-170">Eseguire le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="cc796-170">Do the following tasks:</span></span>

   - <span data-ttu-id="cc796-171">Seleziona la casella di controllo per consentire all'app del connettore di accedere a Twitter.</span><span class="sxs-lookup"><span data-stu-id="cc796-171">Select the checkbox to allow the connector app to sign in to Twitter.</span></span>
   
   - <span data-ttu-id="cc796-172">Aggiungere l'URI di reindirizzamento OAuth utilizzando il formato seguente: \*\* \<connectorserviceuri>/views/TwitterOAuth\*\*, in cui il valore di *connectorserviceuri* è l'URL del servizio app di Azure per l'organizzazione. ad esempio https://twitterconnector.azurewebsites.net/Views/TwitterOAuth.</span><span class="sxs-lookup"><span data-stu-id="cc796-172">Add the OAuth redirect Uri using the following format: **\<connectorserviceuri>/Views/TwitterOAuth**, where the value of *connectorserviceuri* is the Azure app service URL for your organization; for example https://twitterconnector.azurewebsites.net/Views/TwitterOAuth.</span></span>

   ![](media/TCimage32.png)

<span data-ttu-id="cc796-173">L'app per sviluppatori di Twitter è ora pronta per essere utilizzata.</span><span class="sxs-lookup"><span data-stu-id="cc796-173">The Twitter developer app is now ready to use.</span></span>

## <a name="step-6-configure-the-connector-web-app"></a><span data-ttu-id="cc796-174">Passaggio 6: configurare l'applicazione Web del connettore</span><span class="sxs-lookup"><span data-stu-id="cc796-174">Step 6: Configure the connector web app</span></span> 

1. <span data-ttu-id="cc796-175">Passare a https://\<AzureAppResourceName>. azurewebsites. NET (dove **AzureAppResourceName** è il nome della risorsa di Azure App denominata nel passaggio 4), ad esempio, se il nome è **twitterconnector**, andare a https://twitterconnector.azurewebsites.net.</span><span class="sxs-lookup"><span data-stu-id="cc796-175">Go to https://\<AzureAppResourceName>.azurewebsites.net (where **AzureAppResourceName** is the name of your Azure app resource that you named in Step 4) For example, if the name is **twitterconnector**, go to https://twitterconnector.azurewebsites.net.</span></span> <span data-ttu-id="cc796-176">La Home page dell'app avrà lo stesso aspetto della schermata seguente.</span><span class="sxs-lookup"><span data-stu-id="cc796-176">The home page of the app will look like the following screenshot.</span></span>

   ![](media/FBCimage41.png)

2. <span data-ttu-id="cc796-177">Fare clic su **Configura** per visualizzare una pagina di accesso.</span><span class="sxs-lookup"><span data-stu-id="cc796-177">Click **Configure** to display a sign in page.</span></span>

   ![](media/FBCimage42.png)

3. <span data-ttu-id="cc796-178">Nella casella ID tenant digitare o incollare l'ID tenant (ottenuto nel passaggio 2).</span><span class="sxs-lookup"><span data-stu-id="cc796-178">In the Tenant Id box, type or paste your tenant Id (that you obtained in Step 2).</span></span> <span data-ttu-id="cc796-179">Nella casella password digitare o incollare il APISecretKey (ottenuto nel passaggio 2), quindi fare clic su **imposta impostazioni di configurazione** per visualizzare la pagina **Dettagli di configurazione** .</span><span class="sxs-lookup"><span data-stu-id="cc796-179">In the password box, type or paste the APISecretKey (that you obtained in Step 2), and then click **Set Configuration Settings** to display the **Configuration Details** page.</span></span>

   ![](media/TCimage35.png)

4. <span data-ttu-id="cc796-180">In **Dettagli di configurazione**, immettere le impostazioni di configurazione seguenti</span><span class="sxs-lookup"><span data-stu-id="cc796-180">Under **Configuration Details**, enter the following configuration settings</span></span> 

   - <span data-ttu-id="cc796-181">**ID applicazione Twitter** -ID app per l'applicazione Twitter creata al passaggio 5.</span><span class="sxs-lookup"><span data-stu-id="cc796-181">**Twitter application ID** - The app ID for the Twitter application that you created in Step 5.</span></span>
   - <span data-ttu-id="cc796-182">**Segreto dell'applicazione Twitter** -la chiave segreta API per l'applicazione Twitter creata al passaggio 5.</span><span class="sxs-lookup"><span data-stu-id="cc796-182">**Twitter application secret** - The API secret key for the Twitter application that you created in Step 5.</span></span>
   - <span data-ttu-id="cc796-183">**Token client Twitter** -il token di accesso creato nel passaggio 5.</span><span class="sxs-lookup"><span data-stu-id="cc796-183">**Twitter client token** - The access token that you created in Step 5.</span></span>
   - <span data-ttu-id="cc796-184">**Segreto del token client Twitter** -il token di accesso segreto creato nel passaggio 5.</span><span class="sxs-lookup"><span data-stu-id="cc796-184">**Twitter client token secret** - The access token secret that you created in Step 5.</span></span>
   - <span data-ttu-id="cc796-185">**ID applicazione AAD** -ID applicazione per l'app Azure Active Directory creata al passaggio 2</span><span class="sxs-lookup"><span data-stu-id="cc796-185">**AAD application ID** - The application ID for the Azure Active Directory app that you created in Step 2</span></span>
   - <span data-ttu-id="cc796-186">**Segreto dell'applicazione AAD** : il valore del segreto di APISecretKey creato nel passaggio 4.</span><span class="sxs-lookup"><span data-stu-id="cc796-186">**AAD application secret** - The value for the APISecretKey secret that you created in Step 4.</span></span>
   - <span data-ttu-id="cc796-187">**URI dell'applicazione AAD** -URI dell'applicazione AAD ottenuto nel passaggio 2; ad esempio, https://microsoft.onmicrosoft.com/2688yu6n-12q3-23we-e3ee-121111123213.</span><span class="sxs-lookup"><span data-stu-id="cc796-187">**AAD application Uri** - The AAD application Uri obtained in Step 2; for example, https://microsoft.onmicrosoft.com/2688yu6n-12q3-23we-e3ee-121111123213.</span></span>
   - <span data-ttu-id="cc796-188">**Chiave di strumentazione Insights app** -lasciare vuota questa casella.</span><span class="sxs-lookup"><span data-stu-id="cc796-188">**App insights instrumentation key** - Leave this box blank.</span></span>

5. <span data-ttu-id="cc796-189">Fare clic su **Salva** per salvare le impostazioni del connettore.</span><span class="sxs-lookup"><span data-stu-id="cc796-189">Click **Save** to save the connector settings.</span></span>

## <a name="step-7-set-up-a-custom-connector-in-the-security-and-compliance-center"></a><span data-ttu-id="cc796-190">Passaggio 7: configurare un connettore personalizzato nel centro sicurezza e conformità</span><span class="sxs-lookup"><span data-stu-id="cc796-190">Step 7: Set up a custom connector in the security and compliance center</span></span>

1.  <span data-ttu-id="cc796-191">Andare a <https://protection.office.com> e quindi fare clic su data **governance \> Import \> Archive data di terze parti**.</span><span class="sxs-lookup"><span data-stu-id="cc796-191">Go to <https://protection.office.com> and then click **Data governance \> Import \> Archive third-party data**.</span></span>

    ![](media/TCimage36.png)

2. <span data-ttu-id="cc796-192">Fare clic su **Aggiungi connettore** e quindi su **Twitter**.</span><span class="sxs-lookup"><span data-stu-id="cc796-192">Click **Add a connector** and then click **Twitter**.</span></span>

   ![](media/TCimage37.png)

3. <span data-ttu-id="cc796-193">Nella pagina **Aggiungi applicazione del connettore** , immettere le informazioni seguenti e quindi fare clic su **convalida connettore**.</span><span class="sxs-lookup"><span data-stu-id="cc796-193">On the **Add Connector App** page, enter the following information and then click **Validate connector**.</span></span>

    - <span data-ttu-id="cc796-194">Nella prima casella digitare un nome per il connettore, ad esempio **Twitter**.</span><span class="sxs-lookup"><span data-stu-id="cc796-194">In the first box, type a name for the connector, such as **Twitter**.</span></span>
    - <span data-ttu-id="cc796-195">Nella seconda casella digitare o incollare il valore dell'APISecretKey aggiunto nel passaggio 4.</span><span class="sxs-lookup"><span data-stu-id="cc796-195">In the second box, type or paste the value of the APISecretKey that you added in Step 4.</span></span>
    - <span data-ttu-id="cc796-196">Nella terza casella digitare o incollare l'URL del servizio app di Azure; ad esempio **https://twitterconnector.azurewebsites.net**.</span><span class="sxs-lookup"><span data-stu-id="cc796-196">In the third box, type or paste the Azure app service URL; for example **https://twitterconnector.azurewebsites.net**.</span></span>

   <span data-ttu-id="cc796-197">Dopo che il connettore è stato convalidato, fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="cc796-197">After the connector is successfully validated, click **Next**.</span></span>

   ![](media/TCimage38.png)

4. <span data-ttu-id="cc796-198">Fare clic su **login con app connettore**.</span><span class="sxs-lookup"><span data-stu-id="cc796-198">Click **Login with Connector App**.</span></span>

   ![](media/TCimage39.png)

5. <span data-ttu-id="cc796-199">Digitare o incollare di nuovo il APISecretKey e quindi fare clic su **accedi al servizio connettore**.</span><span class="sxs-lookup"><span data-stu-id="cc796-199">Type or paste the APISecretKey again and then click  **Login to Connector Service**.</span></span>

   ![](media/TCimage40.png)


6. <span data-ttu-id="cc796-200">Fare clic su **continua con Twitter**.</span><span class="sxs-lookup"><span data-stu-id="cc796-200">Click **Continue with Twitter**.</span></span>

7. <span data-ttu-id="cc796-201">Nella pagina di accesso di Twitter, accedere usando le credenziali per l'account per l'account Twitter dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="cc796-201">On the Twitter sign in page, sign in using the credentials for the account for your organization’s Twitter account.</span></span>

   ![](media/TCimage42.png)

   <span data-ttu-id="cc796-202">Dopo aver eseguito l'accesso, nella pagina Twitter verrà visualizzato il messaggio seguente: "il processo del connettore di Twitter è stato configurato correttamente".</span><span class="sxs-lookup"><span data-stu-id="cc796-202">After you sign in, the Twitter page will display the following message, "Twitter Connector Job Successfully set up."</span></span>

8. <span data-ttu-id="cc796-203">Fare clic su **fine** per completare la configurazione del connettore Twitter.</span><span class="sxs-lookup"><span data-stu-id="cc796-203">Click **Finish** to complete setting up the Twitter connector.</span></span>

9. <span data-ttu-id="cc796-204">Nella pagina **Imposta filtri** è possibile applicare un filtro per importare e archiviare gli elementi di una determinata età.</span><span class="sxs-lookup"><span data-stu-id="cc796-204">On the **Set Filters** page, you can apply a filter to import (and archive) items that are a certain age.</span></span> <span data-ttu-id="cc796-205">Fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="cc796-205">Click **Next**.</span></span>

   ![](media/TCimage44.png)

10. <span data-ttu-id="cc796-206">Nella pagina **Imposta account di archiviazione** selezionare la cassetta postale di Office 365 in cui verranno importati gli elementi di Twitter.</span><span class="sxs-lookup"><span data-stu-id="cc796-206">On the **Set Storage Account** page, select the Office 365 mailbox that the Twitter items will be imported to.</span></span>

    ![](media/TCimage45.png)

11. <span data-ttu-id="cc796-207">Esaminare le impostazioni e quindi fare clic su **fine** per completare la configurazione del connettore nel centro sicurezza & Compliance.</span><span class="sxs-lookup"><span data-stu-id="cc796-207">Review your settings and then click **Finish** to complete the connector setup in the Security & Compliance Center.</span></span>

    ![](media/TCimage46.png)

    ![](media/TCimage47.png)

12. <span data-ttu-id="cc796-208">Passare alla pagina di **archiviazione dei dati di terze parti** per visualizzare lo stato di avanzamento del processo di importazione.</span><span class="sxs-lookup"><span data-stu-id="cc796-208">Go to the **Archive third-party data** page to see the progress of the import process.</span></span>

    ![](media/TCimage48.png)
