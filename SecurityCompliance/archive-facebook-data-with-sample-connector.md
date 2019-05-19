---
title: Utilizzare un connettore di esempio per archiviare i dati di Facebook in Office 365 (anteprima)
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
description: Gli amministratori possono configurare un connettore nativo per importare i dati di terze parti da origini dati, ad esempio pagine business di Facebook, pagine aziendali di LinkedIn e Instant Bloomberg. In questo modo è possibile archiviare i dati provenienti da origini dati di terze parti in Office 365 per poter utilizzare le funzionalità di conformità, ad esempio i criteri di conservazione legale, ricerca contenuto e mantenimento, per gestire la governance dei dati di terze parti dell'organizzazione.
ms.openlocfilehash: 7a71eac07d3d3260809f90cd2e470c32c44e9dda
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/17/2019
ms.locfileid: "34152188"
---
# <a name="use-a-sample-connector-to-archive-facebook-data-in-office-365-preview"></a>Utilizzare un connettore di esempio per archiviare i dati di Facebook in Office 365 (anteprima)

La funzionalità di esempio del connettore per archiviare i dati di Facebook in Office 365 è in anteprima..

Utilizzare un connettore di esempio nel centro sicurezza & compliance in Office 365 per importare e archiviare i dati da origini dati di terze parti, ad esempio pagine business di Facebook, LinkedIn, Twitter e Bloomberg. Dopo aver configurato e configurato un connettore di esempio, si connette all'origine dati di terze parti (su base pianificata), converte il contenuto di un elemento in un formato di messaggio di posta elettronica e quindi importa tali elementi in una cassetta postale in Office 365.

Dopo l'importazione di dati di terze parti, è possibile applicare le funzionalità di conformità di Office 365, ad esempio il blocco per controversia legale, la ricerca di contenuto, l'archiviazione sul posto, il controllo, la supervisione e i criteri di conservazione di Office 365 ai dati di terze parti. Ad esempio, quando una cassetta postale viene inserita in un blocco per controversia legale o assegnata a un criterio di conservazione, i dati di terze parti verranno mantenuti. È possibile eseguire la ricerca di dati di terze parti utilizzando la ricerca contenuto o associarla a un custode in un caso di eDiscovery avanzato. L'utilizzo di connettori di esempio per l'importazione e l'archiviazione dei dati di terze parti in Office 365 può aiutare l'organizzazione a rimanere conforme ai criteri governativi e normativi.

> [!NOTE]
> Attualmente, solo i connettori di esempio per le pagine business di Facebook e [Twitter](archive-twitter-data-with-sample-connector.md) sono disponibili per l'anteprima. Sono disponibili più connettori di esempio.


## <a name="prerequisites-for-setting-up-a-connector-for-facebook-business-pages"></a>Prerequisiti per la configurazione di un connettore per le pagine business di Facebook

Prima di poter impostare e configurare un connettore di esempio nel centro sicurezza & Compliance, è necessario completare i seguenti prerequisiti per importare e archiviare i dati dalle pagine aziendali di Facebook dell'organizzazione. 

- Per le pagine business dell'organizzazione è necessario un account di Facebook (è necessario accedere a questo account quando si configura il connettore). Attualmente, è possibile archiviare i dati solo da pagine business di Facebook; non è possibile archiviare i dati provenienti da singoli profili Facebook.

- L'organizzazione deve disporre di una sottoscrizione di Azure valida. Se non si dispone di una sottoscrizione di Azure esistente, è possibile iscriversi a una di queste opzioni:

    - [Iscriversi a una sottoscrizione gratuita di 1 anno di Azure](https://azure.microsoft.com/free) 

    - [Iscriversi a una sottoscrizione di Azure pay-as-you-go](https://azure.microsoft.com/pricing/purchase-options/pay-as-you-go/)

    > [!NOTE]
    > La [sottoscrizione gratuita di Azure Active Directory](use-your-free-azure-ad-subscription-in-office-365.md) inclusa nell'abbonamento a Office 365 non supporta i connettori di esempio nel centro sicurezza e conformità di &.

- L'organizzazione deve autorizzare il servizio di importazione di Office 365 per accedere ai dati delle cassette postali nell'organizzazione. Per acconsentire a questa richiesta, accedere a [Questa pagina](https://login.microsoftonline.com/common/oauth2/authorize?client_id=570d0bec-d001-4c4e-985e-3ab17fdc3073&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent), accedere con le credenziali di un amministratore globale di Office 365 e quindi accettare la richiesta.

- L'utente che configura il connettore personalizzato nella conformità & sicurezza (al passaggio 7) deve essere assegnato il ruolo di importazione/esportazione delle cassette postali in Exchange Online. Per impostazione predefinita, questo ruolo non è assegnato a nessun gruppo di ruoli in Exchange Online. È possibile aggiungere il ruolo import export delle cassette postali al gruppo di ruoli Gestione organizzazione in Exchange Online. In alternativa, è possibile creare un nuovo gruppo di ruoli, assegnare il ruolo di esportazione delle cassette postali e quindi aggiungere gli utenti corretti come membri. Per ulteriori informazioni, vedere la sezione creare gruppi di [ruoli](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) o [modificare gruppi di ruoli](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) nell'articolo "gestire i gruppi di ruoli in Exchange Online".

## <a name="step-1-download-the-pre-built-connector-app-package-from-github"></a>Passaggio 1: scaricare il pacchetto di app del connettore precompilato da GitHub

Il primo passaggio consiste nel scaricare il codice sorgente per l'app del connettore Facebook precompilata che utilizzerà un'API di Facebook per connettersi alle pagine business di Facebook ed estrarre i dati di Facebook in modo da poterli importare in Office 365.

1. Accedere a [questo sito GitHub](https://github.com/Microsoft/m365-sample-connector-csharp-aspnet/releases). 
2. Nella versione più recente, fare clic sul file **SampleConnector. zip** .
3. Salvare il file ZIP in un percorso del computer locale. Il file zip verrà caricato in Azure nel passaggio 4.

## <a name="step-2-create-an-app-in-azure-active-directory"></a>Passaggio 2: creare un'app in Azure Active Directory

Il passaggio successivo consiste nel registrare una nuova app in Azure Active Directory (AAD). Questa applicazione corrisponderà alla risorsa app Web che verrà implementata nel passaggio 4 per il connettore Facebook. 

Per istruzioni dettagliate, vedere [creare un'app in Azure Active Directory](deploy-facebook-connector.md#step-2-create-an-app-in-azure-active-directory).

Durante il completamento di questo passaggio (seguendo le istruzioni dettagliate), le informazioni seguenti vengono salvate in un file di testo. I valori per questi verranno utilizzati nei passaggi successivi del processo di distribuzione.

- ID applicazione AAD
- Segreto dell'applicazione AAD
- URI dell'applicazione AAD
- ID tenant

## <a name="step-3-create-an-azure-storage-account"></a>Passaggio 3: creare un account di archiviazione di Azure

Il connettore Facebook distribuito per l'organizzazione invierà gli elementi dalle pagine di business di Facebook al percorso di archiviazione di Azure creato in questo passaggio. Dopo aver creato un connettore personalizzato nel centro sicurezza & Compliance (al passaggio 7), il servizio di importazione di Office 365 copierà i dati di Facebook dal percorso di archiviazione di Azure a una cassetta postale in Office 365. Come illustrato in precedenza nella [](#prerequisites-for-setting-up-a-connector-for-facebook-business-pages) sezione Prerequisites, è necessario disporre di una sottoscrizione di Azure valida per creare un account di archiviazione di Azure.

Per istruzioni dettagliate, vedere [creare un account di archiviazione di Azure](deploy-facebook-connector.md#step-3-create-an-azure-storage-account).

Durante il completamento di questo passaggio (seguendo le istruzioni dettagliate) si salverà l'URI della stringa di connessione generato. Questa stringa verrà utilizzata quando si crea una risorsa Web App in Azure nel passaggio 4.

## <a name="step-4-create-a-web-app-resource-in-azure"></a>Passaggio 4: creare una risorsa Web App in Azure

Il passaggio successivo consiste nel creare una risorsa Web App in Azure per il connettore Facebook. 

Per istruzioni dettagliate, vedere [creare una nuova risorsa Web App in Azure](deploy-facebook-connector.md#step-4-create-a-new-web-app-resource-in-azure).

Durante il completamento di questo passaggio (seguendo le istruzioni dettagliate), vengono fornite le informazioni seguenti, che sono state copiate in un file di testo dopo aver completato i passaggi precedenti, durante la creazione della risorsa Web App.

- APISecretKey – si creerà questo segreto durante il completamento di questo passaggio; verrà utilizzato nel passaggio 7.
- StorageAccountConnectionString: l'URI della stringa di connessione copiato dopo la creazione dell'account di archiviazione di Azure nel passaggio 3.
- tenantId-l'ID tenant dell'organizzazione di Office 365 copiato dopo aver creato l'app Facebook Connector in Azure Active Directory nel passaggio 2.

Inoltre, si caricherà il file SampleConnector. zip (scaricato nel passaggio 1) in questo passaggio per distribuire il codice sorgente per l'app connettore Facebook.

Dopo aver completato questo passaggio, assicurarsi di copiare l'URL del servizio app (ad esempio https://fbconnector.azurewebsites.net),. È necessario utilizzare questa opzione per completare il passaggio 5, il passaggio 6 e il passaggio 7.

## <a name="step-5-register-the-web-app-on-facebook"></a>Passaggio 5: registrare l'app Web su Facebook

Il passaggio successivo consiste nel creare e configurare una nuova applicazione su Facebook. Il connettore personalizzato creato nel passaggio 7 utilizzerà l'app Web Facebook per interagire con l'API di Facebook per ottenere i dati dalle pagine aziendali di Facebook dell'organizzazione.

Per istruzioni dettagliate, vedere [Register the Facebook app](deploy-facebook-connector.md#step-5-register-the-facebook-app).

Durante il completamento di questo passaggio (seguendo le istruzioni dettagliate), le informazioni seguenti vengono salvate in un file di testo. I valori di questi verranno utilizzati per configurare l'app connettore Facebook nel passaggio 6.

- ID applicazione Facebook
- Segreto dell'applicazione Facebook
- I webhook di Facebook verificano il token

## <a name="step-6-configure-the-facebook-connector-app"></a>Passaggio 6: configurare l'app del connettore Facebook

Il passaggio successivo consiste nell'aggiungere le impostazioni di configurazione all'app del connettore Facebook che è stata caricata quando è stata creata la risorsa Azure Web App nel passaggio 4. Per eseguire questa operazione, passare alla Home page dell'app del connettore e configurarla.

Per istruzioni dettagliate, vedere [passaggio 6: Configure the Connector Web App](deploy-facebook-connector.md#step-6-configure-the-connector-web-app).

Durante il completamento di questo passaggio (seguendo le istruzioni dettagliate), vengono fornite le informazioni seguenti (che sono state copiate in un file di testo dopo aver completato i passaggi precedenti):

- ID applicazione Facebook (ottenuto nel passaggio 5)
- Segreto dell'applicazione Facebook (ottenuto nel passaggio 5)
- I webhook di Facebook verificano il token (ottenuto nel passaggio 5)
- ID applicazione di Azure Active Directory (ID applicazione AAD ottenuto nel passaggio 2)
- Segreto dell'applicazione di Azure Active Directory (segreto dell'applicazione AAD ottenuto nel passaggio 2)
- URI dell'applicazione di Azure Active Directory (l'URI dell'applicazione AAD ottenuto nel passaggio 2, ad esempio,https://microsoft.onmicrosoft.com/2688yu6n-12q3-23we-e3ee-121111123213)

## <a name="step-7-set-up-a-custom-connector-in-the-security--compliance-center"></a>Passaggio 7: configurare un connettore personalizzato nel centro sicurezza & Compliance

Il passaggio finale consiste nel configurare il connettore personalizzato nel centro sicurezza & Compliance che importerà i dati dalle pagine aziendali di Facebook a una cassetta postale specificata in Office 365. Dopo aver completato questo passaggio, il servizio di importazione di Office 365 avvierà il processo di importazione dei dati dalle pagine business di Facebook a Office 365. 

Per istruzioni dettagliate, vedere [configurare un connettore personalizzato nel centro sicurezza _AMP_ Compliance](deploy-facebook-connector.md#step-7-set-up-a-custom-connector-in-the-security--compliance-center). 

Durante il completamento di questo passaggio (seguendo le istruzioni dettagliate), vengono fornite le informazioni seguenti (che sono state copiate in un file di testo dopo aver completato la procedura).

- URL del servizio app di Azure (ottenuto nel passaggio 4, ad esempiohttps://fbconnector.azurewebsites.net)
- APISecretKey (creato nel passaggio 4)
