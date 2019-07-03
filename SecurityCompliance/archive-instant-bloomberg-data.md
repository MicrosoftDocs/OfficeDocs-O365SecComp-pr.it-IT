---
title: Configurare un connettore per archiviare i dati di Bloomberg istantanei in Office 365 (anteprima)
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
description: Gli amministratori possono configurare un connettore nativo per importare i dati dallo strumento Instant Bloomberg chat in Office 365. In questo modo è possibile archiviare i dati provenienti da origini dati di terze parti in Office 365 per consentire l'utilizzo di funzionalità di conformità, ad esempio i criteri di conservazione legale, ricerca contenuto e ritenzione per gestire i dati di terze parti dell'organizzazione.
ms.openlocfilehash: 0b69ddaa21196bd0e149eba672fec104eabe2e5e
ms.sourcegitcommit: ab16ddf4c050a995471a058150767a0778be0b88
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/02/2019
ms.locfileid: "35431605"
---
# <a name="set-up-a-connector-to-archive-instant-bloomberg-data-in-office-365-preview"></a>Configurare un connettore per archiviare i dati di Bloomberg istantanei in Office 365 (anteprima)

La funzionalità del connettore per archiviare i dati di Bloomberg istantanei in Office 365 è in anteprima.

Utilizzare un connettore nativo nel centro sicurezza & compliance in Office 365 per importare e archiviare i dati della chat dei servizi finanziari dallo strumento [Instant Bloomberg](https://www.bloomberg.com/professional/product/collaboration/) Collaboration. Dopo aver configurato e configurato un connettore, si connette al sito FTP sicuro Bloomberg (SFTP) dell'organizzazione una volta al giorno, converte il contenuto dei messaggi di chat in un formato di messaggio di posta elettronica e quindi importa tali elementi nelle cassette postali di Office 365.

Dopo che i dati di Bloomberg istantanei vengono archiviati nelle cassette postali degli utenti, è possibile applicare le funzionalità di conformità di Office 365, ad esempio il blocco per controversia legale, la ricerca di contenuto, l'archiviazione sul posto, il controllo e i criteri di conservazione di Office 365 ai dati istantanei Ad esempio, è possibile cercare i messaggi di chat di Bloomberg istantanei usando la ricerca di contenuto o associare la cassetta postale che contiene i dati di Bloomberg istantanei con un custode in un caso avanzato di eDiscovery. L'utilizzo di un connettore Bloomberg istantaneo per l'importazione e l'archiviazione dei dati in Office 365 può aiutare l'organizzazione a rimanere conforme ai criteri governativi e normativi.

## <a name="overview-of-archiving-instant-bloomberg-data"></a>Panoramica dell'archiviazione dei dati di messaggistica istantanea di Bloomberg

Nella panoramica seguente viene illustrato il processo di utilizzo di un connettore per archiviare i dati di chat immediata di Bloomberg in Office 365. 

![Processo di importazione e archiviazione di Bloomberg istantaneo](media/InstantBloombergDataArchiving.png)

1. L'organizzazione collabora con Bloomberg per configurare un sito Bloomberg SFTP. Si lavorerà anche con Bloomberg per configurare Instant Bloomberg per copiare i messaggi di chat nel sito Bloomberg SFTP.

2. Una volta ogni 24 ore, i messaggi di chat provenienti da Instant Bloomberg vengono copiati nel sito Bloomberg SFTP.
    
3. Il connettore Bloomberg istantaneo creato nel centro sicurezza & Compliance si connette al sito Bloomberg SFTP ogni giorno e trasferisce i messaggi di chat dalle 24 ore precedenti a un'area di archiviazione di Azure sicura nel cloud Microsoft. Il connettore converte anche il contenuto di un massaggio chat in un formato di messaggio di posta elettronica.
    
4. Il connettore importa gli elementi del messaggio di chat nella cassetta postale di un utente specifico o in una cassetta postale alternativa. Il connettore viene utilizzato utilizzando il valore della proprietà *CorporateEmailAddress* . Ogni messaggio di chat contiene questa proprietà, che viene popolata con l'indirizzo di posta elettronica di ogni partecipante del messaggio di chat. Se un elemento viene importato in una cassetta postale utente specifica o nella cassetta postale alternativa, si basa sui seguenti criteri:
    
    un. **Elementi che hanno un valore nella proprietà CorporateEmailAddress che corrisponde a un account utente di office 365** – se il connettore può associare l'indirizzo di posta elettronica nella proprietà *CorporateEmailAddress* a un account utente specifico in Office 365, il l'elemento viene copiato nella cartella posta in arrivo nella cassetta postale di Office 365 dell'utente.
    
    b. **Elementi che hanno un valore nella proprietà CorporateEmailAddress che non corrisponde a un account utente di office 365** – se il connettore non è in grado di associare un indirizzo di posta elettronica nella proprietà *CorporateEmailAddress* a un account utente specifico in Office 365, l'elemento viene copiato nella cartella posta in arrivo di una cassetta postale alternativa "catch-all" in Office 365.

## <a name="before-you-begin"></a>Informazioni preliminari

Molti dei passaggi di implementazione necessari per archiviare i dati di Bloomberg istantanei sono esterni a Office 365 e devono essere completati prima di poter creare il connettore nel centro sicurezza & Compliance.

- Eseguire la sottoscrizione a [Blooomberg Anywhere](https://www.bloomberg.com/professional/product/remote-access/?bbgsum-page=DG-WS-PROF-PROD-BBA). Questa operazione è necessaria per consentire l'accesso a Bloomberg Anywhere per accedere al sito Bloomberg SFTP che è necessario impostare e configurare.

- Configurare un sito Bloomberg SFTP (Secure File Transfer Protocol). Dopo aver lavorato con Bloomberg per configurare il sito SFTP, i dati provenienti da Instant Bloomberg vengono caricati nel sito SFTP ogni giorno. Il connettore creato nel passaggio 2 si connette a questo sito SFTP e trasferisce i dati della chat alle cassette postali di Office 365. SFTP crittografa anche i dati di chat istantanea di Bloomberg inviati alle cassette postali di Office 365 durante il processo di trasferimento.

    Per informazioni su Bloomberg SFTP (denominato anche *BB-SFTP*):

    - Vedere il documento "standard di connettività SFTP" sul [supporto di Bloomberg](https://www.bloomberg.com/professional/support/documentation/).
    
    - Contattare il servizio di [assistenza clienti Bloomberg](https://service.bloomberg.com/portal/sessions/new?utm_source=bloomberg-menu&utm_medium=csc).

    Dopo aver collaborato con Bloomberg per configurare un sito SFTP, Bloomberg fornirà alcune informazioni all'utente dopo aver risposto al messaggio di posta elettronica di implementazione Bloomberg. Salvare una copia delle informazioni seguenti. È possibile utilizzarlo per configurare un connettore nel passaggio 3.

    - Codice fermo, che è un ID per l'organizzazione e che viene utilizzato per accedere al sito Bloomberg SFTP.

    - Password per il sito Bloomberg SFTP

    - URL per il sito di Bloomberg SFTP (ad esempio, sftp.bloomberg.com)

    - Numero di porta per il sito Bloomberg SFTP

- L'organizzazione deve autorizzare il servizio di importazione di Office 365 per accedere ai dati delle cassette postali nell'organizzazione. Per acconsentire a questa richiesta, accedere a [Questa pagina](https://login.microsoftonline.com/common/oauth2/authorize?client_id=570d0bec-d001-4c4e-985e-3ab17fdc3073&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent), accedere con le credenziali di un amministratore globale di Office 365 e quindi accettare la richiesta. È necessario completare questo passaggio prima di poter creare correttamente il connettore Bloomberg istantaneo nel passaggio 3.

- L'utente che crea un connettore Bloomberg istantaneo nel passaggio 3 (e che Scarica le chiavi pubbliche e l'indirizzo IP nel passaggio 1) deve essere assegnato al ruolo di importazione/esportazione delle cassette postali in Exchange Online. Questa operazione è necessaria per accedere alla pagina di **archiviazione dei dati di terze parti** nel centro sicurezza & Compliance. Per impostazione predefinita, questo ruolo non è assegnato a nessun gruppo di ruoli in Exchange Online. È possibile aggiungere il ruolo import export delle cassette postali al gruppo di ruoli Gestione organizzazione in Exchange Online. In alternativa, è possibile creare un gruppo di ruoli, assegnare il ruolo di esportazione delle cassette postali e quindi aggiungere gli utenti corretti come membri. Per ulteriori informazioni, vedere la sezione creare gruppi di [ruoli](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) o [modificare gruppi di ruoli](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) nell'articolo "gestire i gruppi di ruoli in Exchange Online".

## <a name="step-1-obtain-ssh-and-pgp-public-keys"></a>Passaggio 1: ottenere le chiavi pubbliche di SSH e PGP

Il primo passaggio consiste nell'ottenere una copia delle chiavi pubbliche per Secure Shell (SSH) e la Pretty Good Privacy (PGP). È possibile utilizzare questi tasti nel passaggio 2 per configurare il sito Bloomberg SFTP per consentire il connettore (creato nel passaggio 3) per connettersi al sito SFTP e trasferire i dati di chat immediata di Bloomberg nelle cassette postali di Office 365. È inoltre possibile ottenere un indirizzo IP in questo passaggio, che viene utilizzato per la configurazione del sito Bloomberg SFTP.

1. Passare a <https://protection.office.com> e quindi fare clic su **Importa governance \> dei dati** e quindi su **archivia dati di terze parti**.

2. Nella pagina **archiviazione dei dati di terze parti** , fare clic su **Aggiungi connettore**, quindi fare clic su **Instant Bloomberg**.

3. Nella pagina **condizioni del servizio** fare clic su **Accetto**.

4. Nel **sito Add credentials for Bloomberg SFTP** al passaggio 1, fare clic su **Scarica SSH Key** e scaricare i collegamenti per il download di **PGP Key** per salvare una copia di ogni file di chiave pubblica nel computer locale. Questi file contengono gli elementi seguenti che verranno utilizzati per configurare il sito Bloomberg SFTP nel passaggio 2:

   - Chiave pubblica SSH – questa chiave verrà utilizzata per configurare Secure Shell (SSH) per abilitare un accesso remoto sicuro quando il connettore si connette al sito Bloomberg SFTP.

   - Chiave pubblica PGP: questa chiave verrà utilizzata per configurare la crittografia dei dati trasferiti dal sito Bloomberg SFTP a Office 365.

   - Indirizzo IP: il sito Bloomberg SFTP verrà configurato per accettare una richiesta di connessione solo da questo indirizzo IP, che viene utilizzato dal connettore Bloomberg istantaneo creato nel passaggio 3. 

5. Fare clic su **Annulla** per chiudere la procedura guidata. Per creare il connettore, è possibile tornare a questa procedura guidata nel passaggio 3.

## <a name="step-2-configure-the-bloomberg-sftp-site"></a>Passaggio 2: configurare il sito Bloomberg SFTP

Il passaggio successivo consiste nell'utilizzare le chiavi pubbliche SSH e PGP e l'indirizzo IP ottenuto nel passaggio 1 per configurare l'autenticazione SSH e la crittografia PGP per il sito Bloomberg SFTP. In questo modo, il connettore Bloomberg istantaneo creato nel passaggio 3 per connettersi al sito Bloomberg SFTP e trasferire i dati di Bloomberg istantanei in Office 365. Se si necessita di assistenza, contattare il [supporto clienti di Bloomberg](https://service.bloomberg.com/portal/sessions/new?utm_source=bloomberg-menu&utm_medium=csc) .

1. Accedere al pannello di controllo di Bloomberg Ccn utilizzando un account per l'organizzazione.

2. Accedere a Ccn e fare clic sulla scheda **chiavi pubbliche** .

3. Per abilitare l'autenticazione SSH, fare clic su **Aggiungi**.

4. Nella finestra **Aggiungi chiave pubblica** fare clic sull'elenco a discesa **tipo di chiave** e quindi fare clic su **account di accesso**.

5. Copiare l'intera chiave pubblica SSH (tutti i caratteri compresi tra virgolette doppie) scaricate nel passaggio 1, incollarlo in questo campo e quindi fare clic su **Submit** per salvare la chiave.
 
    Ad esempio, è necessario copiare la seguente chiave pubblica SSH:

    `
    ssh-rsa
    AAAAB3NzaC1yc2EAAAABIwAAAQEA1dxAyc0JzCmc5NzgyzRYhnj3FGHK5Kd9T2cwZNkmL/9nFhQupQor081rmuw9gACAmeot7y+V/fmijo/q4rxDe3Auu3hfLl1NpWlIssQJHzycms8zimtdQcXbMKwDQOnRthpEocF5ySs76KE72vaYQJTvclAamWWq0D75SUmXDFFr7afvEy57F7KgMD1ecg6lH7q8seSKbiiWxX1Ul0kL15fzpUyhjDP41owb1XC/dF7fJwAmCO1+HZfDLEp62q4tnApLpdd92KoR41LZTryO5dICKhk+S+JxPLkksxL0wm5YevOr2n4ScuRdsBV8mWKZ1Xw+cOss9O6L7cCcEiB3Ow==
    `

6. Per abilitare la crittografia PGP, fare clic su **Aggiungi** di nuovo nella scheda **chiavi pubbliche** , fare clic sull'elenco a discesa **tipo di chiave** e, in questo caso, fare clic su **crittografia**.

7. Copiare l'intera chiave pubblica PGP (tutti i caratteri compresi tra virgolette doppie) scaricati nel passaggio 1, incollarli in questo campo e quindi fare clic su **Submit** per salvare la chiave. 

    Ad esempio, è necessario copiare la seguente chiave pubblica PGP:

    `
    -----BEGIN PGP PUBLIC KEY BLOCK-----
    Version: BCPG C# v1.7.4137.9688
    nmQENBFz+6UQBCACKC4ilYoVOP5b/F0CO+oQYbag79Ov4NZxM4EKW51lUAvKNExRM\nc1C/gwXm8bghht8GEODckXXqx8qSSXUEeA/ROweXNtD1u1kn7PgYEFUeD/qE739m\nm5lxXF9Vod26AtKQ9Y1EvYoQEltwztAaXg8K8LQzB+tzN079d1cxM5tbiRQLttAh\nOt5amLXuINt8+dWyNas3DfgIBUmwfkwCbUO0ElrIhvvO3A85K97SX9Q6Py0SkfkK\nQpnULuhdjSm+7k7qlVMf0s8e/9jUXYKbMFkxlOoMq052vV0l0VQNSeuKoC+m6+LT\nEPab89AMt6S4Ujum9wTUy1eWNx9vV0y/w8N7ABEBAAG0JDM5MjM4ZTg3LWI1YWIt\nNGVmNi1hNTU5LWFmNTRjNmIwN2I0MokBHAQQAQIABgUCXP7pRAAKCRAJQdjaG//S\nCy70B/wKrR2CcqtZx56yrGJFfVy3niEt16VEA3xJM3D9nX0gmgo85Nh5gkiY3ahH\nnNEmgW5vlCM1gcgFeoZWe8A80G4QoabslSUzLbq9HsHOOAQApsfhrhXpylrAVa4n\nI53XUOxWdOTa4xsOob8hSRADqJbwHPOsoAr2A87TvZ9LSi2Mii5omeTq416CLnoS\nPBAEhelZm+ruy5JhzA1yXvWYFH08wNqSHO3bskdES2yW5SyQmYlcoEztWE0Q0Z+G\nZT3kOa/W2MbcZovFCQIfqhwVfXtIzx5uYUmxgk5cFKUJJMlO0AZK/HwM22xuuIWe\ndMa6OMo/n8tvEBxrLQMdVPlz+hZ6
    =AwmP
    -----END PGP PUBLIC KEY BLOCK-----
    `
8. Indietro nella finestra principale del pannello di controllo di Ccn, sotto **Aggiungi l'indirizzo IP qui**, immettere il seguente indirizzo IP (incluso nel file keys. txt scaricato nel passaggio 1) nel **campo Aggiungi indirizzo**.

   `
   40.124.28.216
   `

## <a name="step-3-create-an-instant-bloomberg-connector"></a>Passaggio 3: creare un connettore Bloomberg istantaneo

L'ultimo passaggio consiste nel creare un connettore Bloomberg istantaneo nel centro sicurezza & Compliance. Il connettore utilizza le informazioni fornite per la connessione al sito Bloomberg SFTP e trasferisce i messaggi di chat nelle caselle della cassetta postale dell'utente corrispondente in Office 365. 

1. Passare a <https://protection.office.com> e quindi fare clic su **Importa governance \> dei dati** e quindi su **archivia dati di terze parti**.

2. Nella pagina **archiviazione dei dati di terze parti** , fare clic su **Aggiungi connettore**, quindi fare clic su **Instant Bloomberg**.

3. Nella pagina **condizioni del servizio** fare clic su **Accetto**.

4. Nella pagina **Aggiungi credenziali per il sito Bloomberg SFTP** , in passaggio 3, immettere le informazioni necessarie nelle caselle seguenti e quindi fare clic su **Avanti**.

    - **Codice azienda** -ID dell'organizzazione e utilizzato come nome utente per il sito Bloomberg SFTP.

    - **Password** : password per il sito Bloomberg SFTP

    - **URL sftp** : l'URL del sito Bloomberg SFTP (ad esempio, SFTP.Bloomberg.com).

    - **Porta SFTP** – il numero di porta per il sito Bloomberg SFTP. Il connettore utilizza questo per la connessione al sito SFTP.

5. Nella pagina **cassetta postale alternativa** , digitare l'indirizzo di posta elettronica di una cassetta postale che verrà utilizzata per archiviare i messaggi di chat provenienti da Instant Bloomberg che non possono essere associati a una cassetta postale utente nell'organizzazione.

   > [!NOTE]
   > Ogni messaggio di chat in ogni conversazione in Instant Bloomberg include una proprietà denominata *CorporateEmailAddress*, che contiene l'indirizzo di posta elettronica dell'organizzazione per il partecipante alla chat. Durante il processo di importazione, il connettore tenta di importare i messaggi di chat in una cassetta postale di un utente in Office 365 che ha gli stessi indirizzi di posta elettronica che corrispondono a quello della proprietà *CorporateEmailAddress* . Se non esiste una cassetta postale di Office 365 con lo stesso indirizzo di quella nella proprietà *CorporateEmailAddress* , il connettore importa il messaggio di chat nella cassetta postale alternativa specificata in questa pagina. In questo momento, i messaggi di chat istantanea di Bloomberg archiviati nella cassetta postale alternativa non sono monitorati da criteri di supervisione in Office 365.

6. Fare clic su **Avanti**, rivedere le impostazioni e quindi fare clic su **prepara** per creare il connettore.

7. Passare alla pagina di **archiviazione dei dati di terze parti** per visualizzare lo stato di avanzamento del processo di importazione per il nuovo connettore.
