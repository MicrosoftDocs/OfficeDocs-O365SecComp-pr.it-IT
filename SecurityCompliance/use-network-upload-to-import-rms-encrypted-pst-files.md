---
title: Utilizzare il caricamento di rete per importare i file PST crittografati con RMS su Office 365
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 5/29/2018
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: 84a595b8-cd77-4f66-ac52-57a33ddd4773
description: Informazioni su come utilizzare il caricamento di rete per importare i file PST crittografati RMS alle cassette postali utente in Office 365.
ms.openlocfilehash: 6460512e2d6085df684841248dc286d39dbd9d87
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/27/2018
ms.locfileid: "22531416"
---
# <a name="use-network-upload-to-import-rms-encrypted-pst-files-to-office-365"></a>Utilizzare il caricamento di rete per importare i file PST crittografati con RMS su Office 365

**In questo articolo sia per gli amministratori. Si sta tentando di importare i file PST alla propria cassetta postale? Vedere [posta elettronica di importazione, contatti e calendario da un file pst di Outlook](https://go.microsoft.com/fwlink/p/?LinkID=785075)**
   
Utilizzo della rete caricare opzione e il servizio Office 365 importare per importare i file PST di cassette postali degli utenti. Caricamento di rete si intende caricare i file PST area di archiviazione temporanea nel cloud Microsoft. Il servizio Office 365 importazione quindi copiati i file PST dall'area di archiviazione alle cassette postali utente di destinazione. Una nuova funzionalità del servizio di importazione consente di crittografare i file PST prima di essere caricati e archiviate nel cloud Microsoft. Questi file sarà non crittografati durante l'importazione di cassette postali degli utenti. 
  
Di seguito sono i passaggi necessari per la crittografia e importare i file PST alle cassette postali di Office 365:
  
[Passaggio 1: configurare Azure Rights Management per l'importazione PST ](#step-1-set-up-azure-rights-management-for-pst-import)

[Passaggio 2: generare una chiave di crittografia per l'importazione PST](#step-2-generate-an-encryption-key-for-pst-import)

[Passaggio 3: Ottenere ID tenant RMS e URL delle licenze](#step-3-obtain-rms-tenant-id-and-licensing-url)

[Passaggio 4: Scaricare gli strumenti di importazione di file PST e copiare l'URL SAS](#step-4-download-the-pst-import-tools-and-copy-the-sas-url)

[Passaggio 5: La crittografia e caricare i file PST in Office 365](#step-5-encrypt-and-upload-your-pst-files-to-office-365)

[(Facoltativo) Passaggio 6: Visualizzare un elenco dei file PST caricato in Office 365](#optional-step-6-view-a-list-of-the-pst-files-uploaded-to-office-365)

[Passaggio 7: Creare il file di mapping di importazione di file PST](#step-7-create-the-pst-import-mapping-file)

[Passaggio 8: creare un processo di Importazione PST in Office 365](#step-8-create-a-pst-import-job-in-office-365)
  
> [!IMPORTANT]
> È necessario eseguire il passaggio 1 a 4 passaggio una sola volta per impostare e configurare l'organizzazione per crittografare e importare i file PST alle cassette postali di Office 365. Dopo aver eseguito queste operazioni, eseguire il passaggio 5 a 8 passaggio ogni volta che si desidera crittografare, caricare e importazione di un batch di file PST. 
  
Per ulteriori informazioni sull'importazione di dati a Office 365, vedere [Overview of importare i file PST organizzazione a Office 365](importing-pst-files-to-office-365.md).
  
## <a name="before-you-begin"></a>Informazioni preliminari

- È necessario essere assegnato il ruolo di importare l'esportazione delle cassette postali di Exchange Online per importare i file PST alle cassette postali di Office 365. Per impostazione predefinita, questo ruolo non è assegnato ad alcun gruppo di ruoli di Exchange Online. È possibile aggiungere il ruolo cassette postali importazione/esportazione per il gruppo di ruoli Gestione organizzazione. Oppure creare un nuovo gruppo di ruoli, assegnare il ruolo cassette postali importazione/esportazione e quindi aggiungere l'utente come membro. Per ulteriori informazioni, vedere "Aggiungere un ruolo da un gruppo di ruoli" o "Creare un gruppo di ruoli" sezioni in [gruppi di ruoli di gestione](https://go.microsoft.com/fwlink/p/?LinkId=730688).
    
    Inoltre, per creare Importa i processi in Office 365 Security &amp; centro conformità, uno dei seguenti devono essere vere:
    
  - È necessario assegnare il ruolo destinatari di posta elettronica di Exchange Online. Per impostazione predefinita, questo ruolo viene assegnato ai gruppi di ruoli Gestione organizzazione e gestione dei destinatari.
    
    Oppure
    
  - È necessario essere un amministratore globale dell'organizzazione Office 365.
    
  > [!TIP]
  > È consigliabile creare un nuovo gruppo di ruoli in Exchange Online che è progettata in modo specifico per l'importazione di file PST in Office 365. Livello minimo di privilegi necessari per importare i file PST, assegnare i ruoli di importare l'esportazione delle cassette postali e destinatari di posta elettronica al nuovo gruppo di ruoli e quindi aggiungere membri. 
  
- È necessario archiviare i file PST che si desidera importare in Office 365 in un server di file o una cartella condivisa all'interno dell'organizzazione. Nel passaggio 5 consente di eseguire ImportTool di 365 Office, che consente di crittografare e caricare i file PST che vengono memorizzati nel server di file o cartella a Office 365 condivisa.
    
- Questa procedura è necessario copiare e salvare una copia di una chiave di crittografia, chiave di archiviazione e un numero di URL e le chiavi di identificazione. Queste informazioni verranno utilizzate nel passaggio 5 per crittografare e caricare i file PST. È necessario adottare alcune precauzioni per proteggere queste solo come si proteggono password o altre informazioni relative alla sicurezza. Ad esempio si potrebbe salvarli in un documento di Microsoft Word protetti da password o salvarli in un'unità USB crittografata. Vedere la sezione [informazioni](#more-information) per un esempio di queste chiavi, ID e gli URL. 
    
- È possibile importare file PST in una cassetta postale inattiva in Office 365. A tale scopo, che specifica il GUID della cassetta postale inattiva nel `Mailbox` parametro nel file di mapping di importazione di file PST. Per ulteriori informazioni, vedere [il passaggio 7](#step-7-create-the-pst-import-mapping-file) . 
    
- In una distribuzione ibrida di Exchange, è possibile importare file PST in una cassetta postale di archiviazione basata sul cloud per un utente la cui cassetta postale principale è locale. A tale scopo, eseguire le operazioni seguenti nel file di mapping di importazione di file PST:
    
  - Specificare l'indirizzo di posta elettronica della cassetta postale locale dell'utente nel `Mailbox` parametro. 
    
  - Specificare il valore **TRUE** nel `IsArchive` parametro. 
    
    Per ulteriori informazioni, vedere [il passaggio 7](#step-7-create-the-pst-import-mapping-file) . 
    
- Dopo l'importano dei file PST in una cassetta postale Office 365, il mantenimento di impostazione per la cassetta postale è attivata per un periodo indefinito. Ciò significa che il criterio di conservazione assegnato alla cassetta postale non verrà elaborato fino a quando non si consente di disattivare il mantenimento o si imposta una data per disattivare il blocco. Perché questa operazione è necessaria Se i vecchi messaggi importati in una cassetta postale, potrebbe essere eliminati definitivamente (cancellati) perché il periodo di conservazione è scaduto in base alle impostazioni di conservazione configurate per la cassetta postale. Per ottenere l'ora di proprietario della cassetta postale per gestire i messaggi appena importato o fornire il tempo necessario per modificare le impostazioni di conservazione per la cassetta postale, effettuare la cassetta postale in attesa di conservazione. Per suggerimenti sulla gestione di attesa di conservazione, vedere [ulteriori informazioni](#more-information) . 
    
- Se non si desidera crittografare i file PST prima di caricare Office 365, vedere [rete utilizzo caricare per importare i file PST a Office 365](use-network-upload-to-import-pst-files.md).
    
- Per le domande frequenti sull'utilizzo di caricamento di rete per importare i file PST a Office 365, vedere [domande frequenti sull'importazione di file PST a Office 365](faqimporting-pst-files-to-office-365.md).
  
## <a name="step-1-set-up-azure-rights-management-for-pst-import"></a>Passaggio 1: configurare Azure Rights Management per l'importazione PST 

Importazione di file PST utilizza la funzionalità di crittografia fornita dal servizio di Azure Rights Management (Azure RMS) in Office 365. In tal modo si per crittografare i file PST prima di caricarle a Office 365. 
  
Configurazione Azure RMS per l'importazione dei file PST comporta tre passaggi:
  
- [Attivazione di RMS Azure](#activate-azure-rms)
    
- [Configurazione RMS in Exchange Online](#configure-rms-in-exchange-online)
    
- [Installazione del Client RMS di Active Directory](#install-the-active-directory-rms-client)
    
### <a name="activating-azure-rms"></a>Attivazione di RMS Azure

RMS Azure è disabilitata per impostazione predefinita, ma un amministratore dell'organizzazione possono attivarla. Seguire le istruzioni [Attivare Azure Rights Management](https://docs.microsoft.com/azure/information-protection/deploy-use/activate-service) per installare e attivare Azure DRM.
  
### <a name="configuring-rms-in-exchange-online"></a>Configurazione RMS in Exchange Online

Dopo che è stato attivato il servizio di gestione dei diritti, il passaggio successivo è impostare di Information Rights Management (IRM) in Exchange Online utilizzare RMS Azure. Per ulteriori informazioni, vedere [Configurare IRM per utilizzare Azure Rights Management](https://go.microsoft.com/fwlink/p/?LinkId=394816).
  
1. [Connessione a Exchange Online tramite Remote PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=396554 ).
    
2. Eseguire il seguente comando per impostare l'URL di condivisione della chiave RMS.
    
    ```
    Set-IRMConfiguration -RMSOnlineKeySharingLocation <RMS key sharing location>
    ```

    Utilizzare la tabella seguente per determinare il percorso di condivisione della chiave RMS corretta in base alla posizione dell'organizzazione.
    
    |**Posizione**|**Percorso di condivisione della chiave di RMS**|
    |:-----|:-----|
    |Nord America  <br/> | `https://sp-rms.na.aadrm.com/TenantManagement/ServicePartner.svc` <br/> |
    |Unione Europea  <br/> | `https://sp-rms.eu.aadrm.com/TenantManagement/ServicePartner.svc` <br/> |
    |Asia  <br/> | `https://sp-rms.ap.aadrm.com/TenantManagement/ServicePartner.svc` <br/> |
    |Sud America  <br/> | `https://sp-rms.sa.aadrm.com/TenantManagement/ServicePartner.svc` <br/> |
    |Office 365 per il governo (Government Community Cloud)  <br/> | `https://sp-rms.govus.aadrm.com/TenantManagement/ServicePartner.svc`<sup>1</sup> <br/> |
   
    > [!NOTE]
    > <sup>1</sup> solo i clienti che hanno acquistato Office 365 per SKU governative (Government Community Cloud) devono utilizzare questo percorso di condivisione della chiave di RMS. 
  
    Ad esempio, questo comando consente di configurare la chiave di RMS Online percorso di condivisione in Exchange Online per un cliente che si trova in Nord America.
    
    ```
    Set-IRMConfiguration -RMSOnlineKeySharingLocation "https://sp-rms.na.aadrm.com/TenantManagement/ServicePartner.svc"
    ```

3. Eseguire il comando seguente per importare un Trusted Publishing Domain (TPD) da RMS Online all'organizzazione di Office 365. 
    
    ```
    Import-RMSTrustedPublishingDomain -RMSOnline -Name "RMS Online"
    ```

    In un dominio TPD sono contenute le impostazioni necessarie per utilizzare le funzionalità RMS nell'organizzazione, tra cui la crittografia dei file PST.  
    
4. Eseguire il comando seguente per abilitare IRM per l'organizzazione Office 365.
    
    ```
    Set-IRMConfiguration -InternalLicensingEnabled $true
    ```

### <a name="installing-the-active-directory-rms-client"></a>Installazione del Client RMS di Active Directory

Nell'ultimo passaggio di questa sezione è di scaricare il Client Rights Management Services (RMS) 2.1. Questo software consente di proteggere l'accesso di Azure RMS e protegge le informazioni che passa attraverso le applicazioni che utilizzano Azure RMS. installare il client RMS nello stesso computer che verrà utilizzata per crittografare e caricare i file PST nel passaggio 5. 
  
1. Scaricare [Client Rights Management Service 2.1](https://www.microsoft.com/en-us/download/details.aspx?id=38396).
    
2. Eseguire la procedura guidata del client Rights Management Service 2.1 di Active Directory per installare il client.

## <a name="step-2-generate-an-encryption-key-for-pst-import"></a>Passaggio 2: generare una chiave di crittografia per l'importazione PST

Dopo aver configurato Azure RMS, il passaggio successivo è per generare una chiave di crittografia (noti come una chiave simmetrica) che verrà utilizzata per crittografare i file PST che si carica in Office 365. Verrà fatto tramite l'aggiunta del servizio di importazione di file PST come servizio entità di Azure Active Directory. Aggiunta di questa applicazione come un'identità di servizio che consente il servizio di importazione di file PST per l'autenticazione direttamente con Azure Active Directory quando si carica crittografati i file PST nella posizione di archiviazione Azure nel passaggio 5.
  
1. Avviare il modulo di Azure Active Directory per Windows PowerShell.
    
2. Eseguire il seguente comando per connettersi al servizio online Microsoft.
    
    ```
    Connect-MsolService
    ```

3. Immettere le credenziali di un account di amministratore dell'organizzazione Office 365 e quindi fare clic su **OK**.
    
4. Eseguire il comando seguente per generare una chiave di crittografia (chiamare una chiave simmetrica). Sarà possibile farlo creando una nuova entità di protezione di crittografia PST.
    
    ```
    New-MsolServicePrincipal -DisplayName PstEncryptionPrincipal
    ```

    Il sistema visualizza la chiave simmetrica e le proprietà della nuova entità di protezione di crittografia PST.
    
    ![Copiare e salvare la chiave simmetrica che viene visualizzata](media/0003fdea-dace-41d2-b49d-f5c98c6230ca.png)
  
5. Copiare la chiave simmetrica in un testo o file di Word. Come descritto in precedenza, prendere le dovute precauzioni per proteggere il file. Poiché si tratta dell'unica volta in cui la chiave simmetrica viene visualizzata, è consigliabile acquisire la schermata della finestra e salvarla nello stesso file.  
    
    > [!IMPORTANT]
    > Dopo aver creato l'entità di protezione di crittografia PST, non sarà possibile recuperare la chiave simmetrica utilizzando il cmdlet **Get-MsolServicePrincipal**. È per questo motivo che è importante salvare la chiave. 
  
Mantenere il Azure Active Directory Module per Windows PowerShell aperta e connessa al servizio Microsoft Online. Eseguire un comando in questa finestra nel passaggio successivo.

## <a name="step-3-obtain-rms-tenant-id-and-licensing-url"></a>Passaggio 3: Ottenere ID tenant RMS e URL delle licenze

Il passaggio successivo è ottenere tenant ID e sulle licenze URL del percorso per il servizio RMS Azure per la propria organizzazione. Copiare e salvare le informazioni per lo stesso file che contiene la chiave simmetrica del passaggio 2. L'ID e l'URL da utilizzare nel passaggio 5 per crittografare i file PST.
  
1. Nella Azure Active Directory Module per Windows PowerShell (in cui è connessa al servizio Microsoft Online), eseguire il comando seguente per connettersi al servizio RMS Azure nella propria organizzazione Office 365.
    
    ```
    Connect-AadrmService 
    ```

2. Immettere le credenziali di un account di amministratore dell'organizzazione Office 365 e quindi fare clic su **OK**.
    
3. Eseguire il comando seguente per visualizzare l'ID tenant per il servizio RMS Azure nella propria organizzazione Office 365.
    
    ```
    Get-AadrmConfiguration | FL BPOSId
    ```

    Copiare e salvare il valore per il `BPOSId` proprietà. 
    
4. Eseguire il comando seguente per visualizzare la posizione delle licenze per il servizio RMS Azure.
    
    ```
    Get-AadrmConfiguration | FL LicensingIntranetDistributionPointUrl
    ```

    Copiare e salvare il valore per il `LicensingIntranetDistributionPointUrl` proprietà. 

## <a name="step-4-download-the-pst-import-tools-and-copy-the-sas-url"></a>Passaggio 4: Scaricare gli strumenti di importazione di file PST e copiare l'URL SAS

Ora che è stato configurato RMS Azure e ottenere gli ID necessari per crittografare i file PST, il passaggio successivo consiste scaricare e installare gli strumenti che vengono eseguiti nel passaggio 5 per crittografare e i file PST di caricamento per Office 365. Questi strumenti sono lo strumento AzCopy Azure e lo strumento di crittografia dei dati di Office 365. È inoltre sarà copiare l'URL SAS per l'organizzazione. Questo URL è una combinazione dell'URL di rete per il percorso di archiviazione Azure nel cloud Microsoft per l'organizzazione e una chiave di firma condivise di Access (SAS). Questa chiave viene fornita con le autorizzazioni necessarie per caricare i file PST la posizione di archiviazione Azure. Salvare il file stesso che le altre informazioni per aver copiato nel passaggio 2 e passaggio 3. Come descritto in precedenza, adottare le precauzioni per proteggere l'URL SAS. 
  
> [!IMPORTANT]
> È necessario utilizzare Azure AzCopy versione 5.0 per caricare correttamente i file PST nella posizione di archiviazione Azure. Le versioni più recenti dello strumento AzCopy non sono supportate per l'importazione di file PST in Office 365. Assicurarsi di scaricare lo strumento AzCopy dalla pagina di **caricamento dei file tramite la rete** seguendo le procedure descritte in questo passaggio. 
  
1. Accedere a [https://protection.office.com](https://protection.office.com).
    
2. Accedere a Office 365 utilizzando le credenziali di un account di amministratore dell'organizzazione Office 365.
    
3. Nel riquadro sinistro fare clic su **governance di dati** e quindi fare clic su **Importa**.
    
4. Nella pagina **Importa**, fare clic su **Vai al servizio di importazione**.
    
5. Nella pagina **Importa dati a Office 365** fare clic su **nuovo processo** ![Aggiungi icona](media/ITPro-EAC-AddIcon.gif), quindi fare clic su **messaggi di posta elettronica per il caricamento (con estensione PST)**.
    
6. Nella pagina **caricare i file di rete** nel passaggio 2, fare clic su **Mostra il caricamento di rete SAS URL**.
    
7. Dopo che viene visualizzato l'URL, copiarlo e salvarlo nel file di cui è stato salvato altre chiavi. Assicurarsi di copiare l'intero URL. 
    
8. Nel passaggio 3, fare clic su **Download dello strumento di Azure AzCopy** per scaricare e installare lo strumento AzCopy Azure. 
    
9. Nella finestra popup, fare clic su **Esegui** per installare lo strumento Azure AzCopy. 
    
    > [!IMPORTANT]
    > È necessario installare lo strumento di Azure AzCopy nel percorso predefinito, ovvero `%ProgramFiles(x86)%\Microsoft SDKs\Azure\AzCopy` in un computer che esegue Windows a 64 bit. Ciò avviene perché quando si esegue il O365ImportTool.exe nel passaggio 5, viene cercato lo strumento AzCopy in questa posizione. 
  
10. Dopo aver installato lo strumento AzCopy Azure, fare clic su **Scarica lo strumento di importazione e la crittografia dei dati di Office 365**.
    
11. Nella finestra popup, fare clic su **Salva** \> **Salva** per salvare il file O365ImportTool.zip in una cartella nel computer locale. 
    
12. Estrarre il file O365ImportTool.zip.
    
13. Fare clic su **Annulla** per chiudere la pagina di **caricamento dei file tramite la rete** . 
 
## <a name="step-5-encrypt-and-upload-your-pst-files-to-office-365"></a>Passaggio 5: La crittografia e caricare i file PST in Office 365

Dopo aver eseguito passaggio 1 tramite il passaggio 4, si è pronti utilizzare lo strumento O365ImportTool.exe per crittografare e caricare i file PST in Office 365. Questo strumento consente di crittografare i file PST e quindi le carica e li archivia in un percorso di archiviazione Azure nel cloud Microsoft. Per completare questo passaggio, al file PST devono trovarsi in una condivisione file o un file server nella propria organizzazione. Questo è noto come directory di origine nella procedura seguente. Ogni volta che si esegue lo strumento O365ImportTool.exe, si sarà possibile specificare una directory di origine diversa. 
  
1. Aprire un prompt dei comandi nel computer locale.
    
2. Accedere alla directory nella quale è stato installato lo strumento O365ImportTool.exe durante il passaggio 4.
    
3. Eseguire il comando seguente per crittografare e caricare i file PST in Office 365.
    
    ```
    O365ImportTool.exe /srcdir:<Location of PST files> /protect-rmsserver:<RMS licensing location> /protect-tenantid:<BPOSId> /protect-key:<Symmetric key> /transfer:upload /upload-dest:<Network upload URL> /upload-destSAS:<SAS key>
    ```

    Nella tabella seguente vengono descritti i parametri e i relativi valori. Tenere presente che le informazioni dei passaggi precedenti vengono utilizzate nei valori di questi parametri.
    
    |**Parametro**|**Descrizione**|**Esempio**|
    |:-----|:-----|:-----|
    | `/srcdir:` <br/> |Specifica la directory di origine all'interno dell'organizzazione che contiene i file PST che verranno caricati in Office 365.  <br/> | `/srcdir:\\FILESERVER01\PSTs` <br/> |
    | `/protect-rmsserver:` <br/> |Specifica la posizione delle licenze per il servizio RMS Azure. Utilizzare il valore del `LicensingIntranetDistributionPointUrl` proprietà ottenuto nel passaggio 3. È necessario racchiudere il valore di questo parametro con virgolette doppie ("")<br/> | `/protect-rmsserver:"https://afcbd8ec-cb2b-4a1a-8246-0b4bc22d1978.rms.na.aadrm.com/_wmcs/licensing"` <br/> |
    | `/protect-tenantid:` <br/> |Specifica l'identità dell'organizzazione Azure RMS. Utilizzare il valore del `BPOSId` proprietà ottenuto nel passaggio 3.<br/> | `/protect-tenantid:42745b33-2a5c-4726-8a2a-ca43caa0f74b` <br/> |
    | `/protect-key:` <br/> |Specifica la chiave simmetrica fornito nel passaggio 2. È necessario racchiudere il valore di questo parametro con virgolette doppie ("").  <br/> | `/protect-key:"l+R+Umc5RGmSBh1oW+DoyMxm/h5h2JJXFcNOFiNp867="` <br/> |
    | `/transfer:` <br/> |Specifica se si desidera carica i file PST in rete o trasferirli su un disco rigido. Il valore `upload` indica che si siano caricando file sulla rete. Il valore `drive` indica che si sono distribuiti i file pst su un disco rigido.<br/> | `/transfer:upload` <br/> |
    | `/upload-dest:` <br/> |Specifica la destinazione in Office 365 in cui verranno caricati i file PST. Questo è il percorso di archiviazione Azure per la propria organizzazione. Il valore per questo parametro è costituita dall'URL per il caricamento di rete dall'URL SAS copiato nel passaggio 4. È necessario racchiudere il valore di questo parametro con virgolette doppie ("").<br/><br/> **Suggerimento:** (Facoltativo) È possibile specificare una sottocartella nella posizione di archiviazione Azure per caricare i file PST crittografati. Ottenere questo risultato mediante l'aggiunta di un percorso sottocartella (dopo "ingestiondata") l'URL per il caricamento di rete. Nel primo esempio non consente di specificare una sottocartella. Ciò significa che viene caricato il file pst nella directory principale (denominato *ingestiondata* ) della posizione di archiviazione Azure. Nel secondo esempio carica i file PST in una sottocartella (denominato *EncryptedPSTs* ) nella posizione di archiviazione Azure.           | `/upload-dest:"https://3c3e5952a2764023ad14984.blob.core.windows.net/ingestiondata"` <br/> Oppure  <br/>  `/upload-dest:"https://3c3e5952a2764023ad14984.blob.core.windows.net/ingestiondata/EncryptedPSTs"` <br/> |
    | `/upload-destSAS:` <br/> |Specifica la chiave SAS per l'organizzazione. Il valore per questo parametro è costituita da chiave SAS dall'URL SAS copiato nel passaggio 4. Si noti che la chiave SAS primo carattere è un punto interrogativo ("?"). È necessario racchiudere il valore di questo parametro con virgolette doppie ("").  <br/> | `/upload-destSAS:"?sv=2012-02-12&amp;se=9999-12-31T23%3A59%3A59Z&amp;sr=c&amp;si=IngestionSasForAzCopy201601121920498117&amp;sig=Vt5S4hVzlzMcBkuH8bH711atBffdrOS72TlV1mNdORg%3D"` <br/> |
    | `/recurse` <br/> |Questo parametro facoltativo specifica la modalità ricorsiva in modo che lo strumento O365ImportTool.exe verrà copiato i file di file pst che si trovano nelle sottocartelle nella directory di origine specificato dal `/srcdir:` parametro.  <br/><br/> **Nota:** Se si include questo parametro, i file PST in sottocartelle avrà un percorso di file diverso nella posizione di archiviazione Azure dopo essere state caricate. È necessario specificare il percorso esatto nel file CSV creato nel passaggio 7.           | `/recurse` <br/> |
   
    Di seguito è riportato un esempio di sintassi dello strumento O365ImportTool.exe nella quale verranno utilizzati i valori effettivi di ogni parametro:
    
    ```
    O365ImportTool.exe /srcdir:\\FILESERVER01\PSTs /protect-rmsserver:"https://afcbd8ec-cb2b-4a1a-8246-0b4bc22d1978.rms.na.aadrm.com/_wmcs/licensing" /protect-tenantid:42745b33-2a5c-4726-8a2a-ca43caa0f74b  /protect-key:"l+R+Umc5RGmSBh1oW+DoyMxm/h5h2JJXFcNOFiNp867=" /transfer:upload /upload-dest:"https://3c3e5952a2764023ad14984.blob.core.windows.net/ingestiondata" /upload-destSAS:"?sv=2012-02-12&amp;se=9999-12-31T23%3A59%3A59Z&amp;sr=c&amp;si=IngestionSasForAzCopy201601121920498117&amp;sig=Vt5S4hVzlzMcBkuH8bH711atBffdrOS72TlV1mNdORg%3D"
    ```

    Una volta eseguito il comando, i messaggi di stato visualizzati riportano informazioni sull'avanzamento della crittografia e del caricamento dei file PST. Nel messaggio finale viene riportato il numero complessivo di file che sono stati crittografati e caricati.  
    
    > [!TIP]
    > Correttamente, eseguire il comando O365ImportTool.exe e verificare che tutti i parametri siano corretti, Salva una copia della sintassi della riga di comando per lo stesso file (protetto) in cui è stato copiato l'informazioni ottengono nei passaggi precedenti. È quindi possibile copiare e incollare il comando nel prompt dei comandi ogni volta che si desidera eseguire lo strumento O365ImportTool.exe per crittografare e caricare i file PST in Office 365. Gli unici valori potrebbe essere necessario modificare sono quelle per le `/srcdir:` e `/upload-dest:` parametri. 
  
## <a name="optional-step-6-view-a-list-of-the-pst-files-uploaded-to-office-365"></a>(Facoltativo) Passaggio 6: Visualizzare un elenco dei file PST caricato in Office 365

Come un'operazione facoltativa, è possibile installare e utilizzare Microsoft Azure archiviazione Explorer (che è uno strumento gratuito, open source) per visualizzare l'elenco dei file PST in cui è stato caricato in Azure blob. Esistono tre motivi per eseguire questa operazione:
  
- Verificare che i file PST da un file server nella propria organizzazione o la cartella condivisa sono stati caricati correttamente blob Azure.

- Verificare che i file PST vengono crittografati. I file PST crittografati hanno un `.pfile` extension al nome del file PST: ad esempio `pilarp.pst.pfile`.
    
- Verificare il nome del file (e il nome del percorso sottocartella se è stato incluso uno) per ogni file PST caricati blob Azure. Ciò è davvero utile quando si crea il file PST mapping file nel passaggio successivo, poiché non è necessario specificare il percorso di cartella e nome di file per ogni file PST. Verifica tali nomi consente di ridurre i potenziali errori nel file di mapping di file PST.
    
Microsoft Azure archiviazione Explorer è in anteprima. 
  
 > [!IMPORTANT]
>  È possibile utilizzare le soluzioni di archiviazione Azure per caricare o modificare il file PST. L'unico metodo supportato per l'importazione di file PST in Office 365 consiste nell'utilizzare AzCopy. Inoltre, è possibile eliminare i file PST che è stato caricato in Azure blob. Se si tenta di eliminare un file PST, viene visualizzato un errore relativo a non disporre delle autorizzazioni necessarie. Si noti che tutti i file PST vengono automaticamente eliminati dall'area di archiviazione Azure. Se sono presenti alcun processo di importazione in corso, tutti i file PST fare nel contenitore **ingestiondata** non viene eliminato 30 giorni dopo il processo di importazione più recente è stato creato. 
  
Per installare le soluzioni di archiviazione Azure e connettersi all'area di archiviazione Azure:
  
1. Scaricare e installare lo [strumento di Microsoft Azure archiviazione Explorer](https://go.microsoft.com/fwlink/p/?LinkId=544842).
    
2. Avviare Microsoft Azure archiviazione Explorer, **Gli account di archiviazione** fare clic nel riquadro sinistro e fare clic su **Connetti per archiviazione Azure**. 
    
    ![Il pulsante destro gli account di archiviazione e quindi fare clic su Connetti per archiviazione Azure](media/75b80cc3-c336-4f96-ad32-54ac9b96a7af.png)
  
3. Nella casella in **connessione a archiviazione Azure**, incollare l'URL SAS fornito nel passaggio 4 e quindi fare clic su **Avanti**. 
    
    ![Incolla l'URL SAS nella casella nella connessione alla pagina archiviazione Azure](media/5d034128-e087-48e1-9ebc-4c9fa262d5b7.png)
  
4. Nella pagina **connessione riepilogo** esaminare le informazioni di connessione e quindi fare clic su **Connetti**. 
    
5. In **Account di archiviazione**, espandere il nodo del **Servizio SAS ()** e quindi espandere il nodo **Contenitori Blob** . 
    
6. Pulsante destro del mouse **ingestiondata**e quindi fare clic su **Apri Blob contenitore Editor**.
    
    ![Fare clic con il pulsante destro del mouse su ingestiondata, quindi selezionare Apri editor contenitori BLOB](media/f50eee30-9202-4efc-904a-2895a0bc388d.png)
  
    Viene visualizzata l'area di archiviazione Azure, con un elenco dei file PST caricato nel passaggio 5.
    
    ![Esplora archivi di Azure mostra un elenco di file con estensione PST caricati](media/a448ae43-e744-4153-8304-22b59e93883c.png)
  
7. Una volta terminato di utilizzare Microsoft Azure archiviazione Explorer, destro **ingestiondata**e quindi fare clic su **Scollega** di disconnettersi dall'area di archiviazione Azure. In caso contrario, viene visualizzato un errore al successivo che si cerca di collegare. 
    
    ![Fare clic con il pulsante destro del mouse sull’inserimento e su Disconnetti per disconnettersi dall'area di archiviazione Azure](media/1e8e5e95-4215-4ce4-a13d-ab5f826a0510.png)
  
## <a name="step-7-create-the-pst-import-mapping-file"></a>Passaggio 7: Creare il file di mapping di importazione di file PST

Dopo che i file PST sono stati crittografati e caricati nella posizione di archiviazione Azure per la propria organizzazione Office 365, il passaggio successivo è per creare una virgola separati file CSV (valori) che specifica quali cassette postali degli utenti saranno importati per i file PST. In questo file CSV nel passaggio successivo verrà inviato quando si crea un processo di importazione di file PST.
  
1. [Scarica una copia del file di mapping di importazione di file PST](https://go.microsoft.com/fwlink/p/?LinkId=544717). 
    
2. Aprire o salvare il file CSV nel computer locale. Nell'esempio seguente viene visualizzato un file di mapping di importazione PST completo (aperto nel Blocco note). È molto più facile usare Microsoft Excel per modificare il file CSV.
    
    ```
    Workload,FilePath,Name,Mailbox,IsArchive,TargetRootFolder,ContentCodePage,SPFileContainer,SPManifestContainer,SPSiteUrl
    Exchange,,annb.pst.pfile,annb@contoso.onmicrosoft.com,FALSE,/,,,,
    Exchange,,annb_archive.pst.pfile,annb@contoso.onmicrosoft.com,TRUE,/ImportedPst,,,,
    Exchange,,donh.pst.pfile,donh@contoso.onmicrosoft.com,FALSE,/,,,,
    Exchange,,donh_archive.pst.pfile,donh@contoso.onmicrosoft.com,TRUE,/ImportedPst,,,,
    Exchange,EncryptedPSTs,pilarp.pst.pfile,pilarp@contoso.onmicrosoft.com,FALSE,,,,,
    Exchange,EncryptedPSTs,pilarp_archive.pst.pfile,pilarp@contoso.onmicrosoft.com,TRUE,/ImportedPst,,,,
    Exchange,EncryptedPSTs,tonyk.pst.pfile,tonyk@contoso.onmicrosoft.com,FALSE,,,,,
    Exchange,EncryptedPSTs,tonyk_archive.pst.pfile,tonyk@contoso.onmicrosoft.com,TRUE,/ImportedPst,,,,
    Exchange,EncryptedPSTs,zrinkam.pst.pfile,zrinkam@contoso.onmicrosoft.com,FALSE,,,,,
    Exchange,EncryptedPSTs,zrinkam_archive.pst.pfile,zrinkam@contoso.onmicrosoft.com,TRUE,/ImportedPst,,,,
    ```

    La prima riga o una riga di intestazione, del file CSV sono elencati i parametri che verranno utilizzati dal servizio di importazione di file PST per importare i file PST di cassette postali degli utenti. Ogni nome del parametro è separata da una virgola. Ogni riga sotto la riga di intestazione rappresenta i valori dei parametri per l'importazione di un file PST in una cassetta postale specifica. È necessario una riga per ogni file PST che si desidera importare una cassetta postale utente. Assicurarsi di sostituire i segnaposto i dati nel file di mapping con dati effettivi.
    
    > [!NOTE]
    > Non apportare modifiche nella riga di intestazione, compresi i parametri SharePoint; verranno ignorati durante il processo di impostazione PST. 
  
3. Utilizzare le informazioni della tabella per popolare il file CSV con i dati necessari.
    
    |**Parametro**|**Descrizione**|**Esempio**|
    |:-----|:-----|:-----|
    | `Workload` <br/> |Specifica il servizio di Office 365 per i dati verranno importati. Per importare i file PST di cassette postali degli utenti, utilizzare `Exchange`.<br/> | `Exchange` <br/> |
    | `FilePath` <br/> |Specifica il percorso della cartella nel percorso di archiviazione Azure caricato i file PST nel passaggio 5.  <br/>  Se si non includere un nome della sottocartella facoltativo l'URL di rete nel `/upload-dest:` parametro nel passaggio 5, lasciare vuoto questo parametro nel file CSV. Se è stato incluso un nome della sottocartella, è necessario specificarlo questo parametro. Il valore per questo parametro viene fatta distinzione tra maiuscole e minuscole. In entrambi i casi, *non* includere "ingestiondata" nel valore per il `FilePath` parametro.<br/> <br/>**Importante:** Caso il nome del percorso file deve essere lo stesso caso utilizzato se è stato incluso un nome della sottocartella facoltativo nell'URL SAS nel `/upload-dest:` parametro nel passaggio 5. Ad esempio, se è stato utilizzato `EncryptedPSTs` per la sottocartella nome nel passaggio 5 e quindi utilizzare `encryptedpsts` nel `FilePath` parametro nel file CSV, l'importazione del file PST avrà esito negativo. Assicurarsi di utilizzare lo stesso caso in entrambi i casi.           |(lasciare vuoto)  <br/> Oppure  <br/>  `EncryptedPSTs` <br/> |
    | `Name` <br/> |Specifica il nome del file PST che verrà importato per la cassetta postale utente. Il valore per questo parametro viene fatta distinzione tra maiuscole e minuscole. Poiché i file PST che vengono caricati nella posizione di archiviazione Azure sono crittografati, un `.pfile` estensione viene aggiunta al nome del file PST. È necessario aggiungere il `.pfile` dei file di estensione del nome del file PST in file CSV.<br/><br/> **Importante:** Caso il nome del file PST nel file CSV deve essere uguale al file PST che è stato caricato per la posizione di archiviazione Azure nel passaggio 5. Ad esempio, se si utilizza `annb.pst.pfile` nel `Name` parametro nel file CSV, ma il nome del file PST è `AnnB.pst`, l'importazione di file PST avrà esito negativo. Assicurarsi che il nome del file PST nel file CSV utilizza lo stesso caso come file PST effettivo.           | `annb.pst.pfile` <br/> |
    | `Mailbox` <br/> |Specifica l'indirizzo di posta elettronica della cassetta postale nella quale verrà importato il file PST.   <br/> Per importare un file PST di una cassetta postale inattiva, è necessario specificare il GUID della cassetta postale per questo parametro. Per ottenere il GUID, eseguire il seguente comando PowerShell in Exchange Online: "Get-Mailbox - InactiveMailboxOnly<identity of inactive mailbox> | Guid FL` <br/><br/> **Note:** In some cases, you might have multiple mailboxes with the same email address, where one mailbox is an active mailbox and the other mailbox is in a soft-deleted (or inactive) state. In these situations, you have specify the mailbox GUID to uniquely identify the mailbox to import the PST file to. To obtain this GUID for active mailboxes, run the following PowerShell command:  `Get-Mailbox -<identity of active mailbox> | Guid FL`. To obtain the GUID for soft-deleted (or inactive) mailboxes, run this command  `Get-Mailbox - <identity of soft-deleted or inactive mailbox> - SoftDeletedMailbox | Guid FL'           | `annb@contoso.onmicrosoft.com` <br/> Oppure  <br/>  `2d7a87fe-d6a2-40cc-8aff-1ebea80d4ae7` <br/> |
    | `IsArchive` <br/> | Specifica se importare o meno il file PST nella cassetta postale di archiviazione dell'utente. Esistono due opzioni:<br/> **FALSE** Consente di importare il file PST alla cassetta postale principale dell'utente.  <br/> **TRUE** Consente di importare il file PST alla cassetta postale di archivio dell'utente.  <br/>  Se si omette questo parametro, viene importato il file PST alla cassetta postale principale dell'utente.  <br/><br/> **Nota:** Per importare un file PST di una cassetta postale di archiviazione basate su cloud per un utente la cui cassetta postale principale è locale, è sufficiente specificare **TRUE** per questo parametro e specificare l'indirizzo di posta elettronica per la cassetta postale locale dell'utente per il `Mailbox` parametro.           | `FALSE` <br/> Oppure  <br/>  `TRUE` <br/> |
    | `TargetRootFolder` <br/> | Specifica la cartella delle cassette postali che viene importato il file PST.  <br/>  Se si omette questo parametro, i file PST verranno importate in una nuova cartella denominata **Imported** posizionato a livello radice della cassetta postale (allo stesso livello di cartella Posta in arrivo e le altre cartelle predefinite delle cassette postali).  <br/>  Se si specifica `/`, gli elementi del file PST verranno importati direttamente nella cartella Posta in arrivo dell'utente.  <br/>  Se si specifica `/<foldername>`, gli elementi del file PST verranno importati in una sottocartella denominata * \<foldername\> * . Ad esempio, se è stato utilizzato `/ImportedPst`, gli elementi potrebbero essere importati in una sottocartella denominata **ImportedPst**. In questa sottocartella si troverà nella cartella Posta in arrivo dell'utente.<br/><br/> **Suggerimento:** Si consiglia di eseguire alcuni test batch per provare a questo parametro è quindi possibile determinare il percorso della cartella indicato da importare file di file pst.           |(lasciare vuoto)  <br/> Oppure  <br/>  `/` <br/> Oppure  <br/>  `/ImportedPst` <br/> |
    | `ContentCodePage` <br/> |Questo parametro opzionale specifica un valore numerico per la tabella codici da utilizzare per l'importazione di file PST in formato ANSI. Questo parametro viene utilizzato per l'importazione di file PST di organizzazioni cinese e giapponese, coreano, dal momento che queste lingue utilizzano in genere un set di caratteri a byte doppio (DBCS) per la codifica dei caratteri. Se questo parametro non viene utilizzato per importare i file PST per le lingue che utilizzano DBCS per i nomi delle cartelle delle cassette postali, i nomi delle cartelle sono spesso incomprensibile dopo l'importazione. Per un elenco di valori supportati da utilizzare per questo parametro, vedere [Identificatori di pagina di codice](https://go.microsoft.com/fwlink/p/?LinkId=328514).<br/><br/> **Nota:** Come già indicato, questo è un parametro facoltativo e non è necessario includere nel file CSV. Oppure includerlo e lasciare il valore vuoto per una o più righe.           |(lasciare vuoto)  <br/> Oppure  <br/>  `932`(ovvero l'identificatore della tabella codici per ANSI/OEM giapponese)  <br/> |
    | `SPFileContainer` <br/> |Per l'importazione PST, omettere questo parametro.   <br/> |Non applicabile  <br/> |
    | `SPManifestContainer` <br/> |Per l'importazione PST, omettere questo parametro.   <br/> |Non applicabile  <br/> |
    | `SPSiteUrl` <br/> |Per l'importazione PST, omettere questo parametro.   <br/> |Non applicabile  <br/> |
  
## <a name="step-8-create-a-pst-import-job-in-office-365"></a>Passaggio 8: creare un processo di Importazione PST in Office 365

L'ultimo passaggio consiste nel creare il processo di importazione di file PST nel servizio di importazione in Office 365. Come indicato in precedenza, si invierà il file di mapping di importazione di file PST creato nel passaggio 7. Dopo aver creato il nuovo processo, il servizio di importazione verrà utilizzate le informazioni nel file di mapping di annullamento-crittografare e importare i file PST (ovvero il caricamento di Office 365 nel passaggio 5) per la cassetta postale utente specificato. 
  
1. Accedere a [https://protection.office.com](https://protection.office.com).
    
2. Accedere a Office 365 utilizzando le credenziali di un account di amministratore dell'organizzazione Office 365.
    
3. Nel riquadro sinistro fare clic su **governance di dati** e quindi fare clic su **Importa**.
    
4. Nella pagina **Importa**, fare clic su **Vai al servizio di importazione**.
    
5. Nella pagina **Importa dati a Office 365** fare clic su **nuovo processo**![Aggiungi icona](media/ITPro-EAC-AddIcon.gif), quindi fare clic su **messaggi di posta elettronica per il caricamento (con estensione PST)**.
    
6. Nella pagina **Carica file sulla rete**, fare clic sulle caselle di controllo **Ho effettuato il caricamento dei file** e **Ho accesso al file di mapping**, quindi selezionare **Avanti**.  
    
7. Immettere un nome per il processo di importazione PST e fare clic su **Avanti**.
    
8. Fare clic su **Aggiungi** ![Aggiungi icona](media/ITPro-EAC-AddIcon.gif) per selezionare il file PST Mapping creato nel passaggio 7. 
    
9. Una volta visualizzato il nome del file CSV nell'elenco, selezionarlo e fare clic su **Convalida** per verificare se nel file CSV sono presenti errori.  
    
    > [!NOTE]
    > Nel precedente è detto, quando vengono crittografati i file PST, un `.pfile` estensione viene aggiunta al nome del file PST. È necessario aggiungere il `.pfile` dei file di estensione del nome del file PST in file CSV. In caso contrario, la convalida del file CSV avrà esito negativo. 
  
    Il file CSV deve essere convalidato per creare un processo di importazione PST. Se la convalida ha esito negativo, fare clic sul collegamento **Non valido** nella colonna **Stato**. Viene aperta una copia del file di mapping di importazione PST e viene visualizzato un messaggio di errore per ogni riga del file con errore. 
    
10. Quando il file di mapping PST viene convalidato, leggere i termini e le condizioni, quindi fare clic sulla casella di controllo.
    
11. Fare clic su **Fine** per inviare il processo. 
    
    Il processo viene visualizzato nell'elenco dei processi di importazione di file PST nella pagina **Importa dati a Office 365** . 
    
12. Selezionare il processo e fare clic su **Aggiorna**![icona Aggiorna](media/O365-MDM-Policy-RefreshIcon.gif) per aggiornare le informazioni sullo stato viene visualizzate nel riquadro dei dettagli. 
    
13. In quest'ultimo, fare clic su **Visualizza dettagli** per visualizzare lo stato più recente del processo selezionato. 
 
## <a name="more-information"></a>Ulteriori informazioni

- Il motivo per cui importare i file PST a Office 365?
    
  - È un modo efficace per eseguire la migrazione di posta elettronica dell'organizzazione a Office 365.
    
  - In questo modo, è possibile soddisfare le esigenze di conformità dell'organizzazione, permettendo all'utente di:
    
  - Abilitare le cassette postali di archiviazione per fornire agli altri utenti ulteriore spazio di archiviazione per la cassetta postale.
    
  - Bloccare le cassette postali per preservarne i contenuti.
    
  - Usare gli strumenti di Microsoft eDiscovery per cercare contenuti nelle cassette postali.
    
  - Utilizzare criteri di conservazione per controllare la durata di conservazione dei contenuti della cassetta postale.
    
  - Il Registro di controllo di Office 365 per gli eventi relativi alla cassetta postale di ricerca.
    
  - Consente di proteggere la perdita di dati. I file PST importate alle cassette postali di Office 365 ereditano le caratteristiche di disponibilità elevata di Exchange Online, anziché l'archiviazione dei dati nel computer dell'utente.
    
  - I dati sono disponibili per l'utente da tutti i dispositivi in quanto vengono memorizzati nel cloud.
    
- Di seguito è riportato un esempio delle chiavi, ID e gli URL che si ottengono nei passaggi da 2, 3 e 4. In questo esempio contiene anche la sintassi del comando che si esegue nello strumento di O365ImportTool.exe per crittografare e PST per il caricamento di file a Office 365. È necessario adottare alcune precauzioni per proteggere queste solo come si proteggono password o altre informazioni relative alla sicurezza.
    
  ```
  Symmetric key: l+R+Umc5RGmSBh1oW+DoyMxm/h5h2JJXFcNOFiNp867=

  BPOSId: 42745b33-2a5c-4726-8a2a-ca43caa0f74b

  LicensingIntranetDistributionPointUrl (RMS licensing location): https://afcbd8ec-cb2b-4a1a-8246-0b4bc22d1978.rms.na.aadrm.com/_wmcs/licensing
  
  SAS URL: https://3c3e5952a2764023ad14984.blob.core.windows.net/ingestiondata?sv=2012-02-12&amp;se=9999-12-31T23%3A59%3A59Z&amp;sr=c&amp;si=IngestionSasForAzCopy201601121920498117&amp;sig=Vt5S4hVzlzMcBkuH8bH711atBffdrOS72TlV1mNdORg%3D
  
  O365ImportTool.exe /srcdir:<Location of PST files> /protect-rmsserver:<RMS licensing location> /protect-tenantid:<BPOSId> /protect-key:<Symmetric key> /transfer:upload /upload-dest:<Network upload URL from the SAS URL> /upload-destSAS:<SAS key from the SAS URL>
  
  EXAMPLES
  
  This example uploads PST files to the root of the Azure storage location:

  O365ImportTool.exe /srcdir:\\FILESERVER01\PSTs /protect-rmsserver:"https://afcbd8ec-cb2b-4a1a-8246-0b4bc22d1978.rms.na.aadrm.com/_wmcs/licensing" /protect-tenantid:42745b33-2a5c-4726-8a2a-ca43caa0f74b /protect-ownerid:45beb445-4d06-47df-8e61-6ca1a88a080e /protect-key:"l+R+Umc5RGmSBh1oW+DoyMxm/h5h2JJXFcNOFiNp867=" /transfer:upload /upload-dest:"https://3c3e5952a2764023ad14984.blob.core.windows.net/ingestiondata" /upload-destSAS:"?sv=2012-02-12&amp;se=9999-12-31T23%3A59%3A59Z&amp;sr=c&amp;si=IngestionSasForAzCopy201601121920498117&amp;sig=Vt5S4hVzlzMcBkuH8bH711atBffdrOS72TlV1mNdORg%3D"
  
  This example uploads PST files to a subfolder named EncryptedPSTs  in the Azure storage location:
  
  O365ImportTool.exe /srcdir:\\FILESERVER01\PSTs /protect-rmsserver:"https://afcbd8ec-cb2b-4a1a-8246-0b4bc22d1978.rms.na.aadrm.com/_wmcs/licensing" /protect-tenantid:42745b33-2a5c-4726-8a2a-ca43caa0f74b /protect-ownerid:45beb445-4d06-47df-8e61-6ca1a88a080e /protect-key:"l+R+Umc5RGmSBh1oW+DoyMxm/h5h2JJXFcNOFiNp867=" /transfer:upload /upload-dest:"https://3c3e5952a2764023ad14984.blob.core.windows.net/ingestiondata/EncryptedPSTs" /upload-destSAS:"?sv=2012-02-12&amp;se=9999-12-31T23%3A59%3A59Z&amp;sr=c&amp;si=IngestionSasForAzCopy201601121920498117&amp;sig=Vt5S4hVzlzMcBkuH8bH711atBffdrOS72TlV1mNdORg%3D"
  ```

- Come indicato in precedenza, il servizio Office 365 importazione consente di attivare il mantenimento impostazione (per un periodo indefinito) dopo l'importazione dei file PST in una cassetta postale. Ciò significa che la proprietà *RentionHoldEnabled* è impostata su `True` in modo che non verrà elaborato il criterio di conservazione assegnato alla cassetta postale. In questo modo il tempo di proprietario della cassetta postale per gestire i messaggi appena importato impedendo un'eliminazione o criteri di archiviazione dall'eliminazione o l'archiviazione dei messaggi meno recenti. Ecco alcuni passaggi che consentono di gestire il mantenimento: 
    
  - Dopo un determinato periodo di tempo, è possibile disattivare il mantenimento eseguendo il `Set-Mailbox -RetentionHoldEnabled $false` comando. Per ulteriori informazioni, vedere [archiviazione sul posto una cassetta postale di conservazione](https://go.microsoft.com/fwlink/p/?LinkId=544749).
    
  - È possibile configurare il mantenimento in modo che è disattivata per alcuni data in futuro. A tale scopo, che esegue il `Set-Mailbox -EndDateForRetentionHold <date>` comando. Ad esempio, supponendo che la data corrente è il 1 ° luglio 2016 e si desidera che il mantenimento disattivata in 30 giorni, eseguire il comando seguente: `Set-Mailbox -EndDateForRetentionHold 8/1/2016`. In questo scenario, è opportuno lasciare la proprietà *RentionHoldEnabled* impostata su `True`. Per ulteriori informazioni, vedere [Set-Mailbox](https://go.microsoft.com/fwlink/p/?LinkId=150317).
    
  - È possibile modificare le impostazioni per il criterio di conservazione viene assegnato alla cassetta postale in modo che gli elementi meno recenti che sono stati importati non essere immediatamente eliminati o spostati alla cassetta postale di archivio dell'utente. Ad esempio, è possibile allungare il periodo di conservazione per un criterio di eliminazione o un archivio viene assegnato alla cassetta postale. In questo scenario, potrebbe consente di disattivare il mantenimento per la cassetta postale dopo che sono state modificate le impostazioni dei criteri di conservazione. Per ulteriori informazioni, vedere [impostazione di un criterio di archiviazione e l'eliminazione delle cassette postali nell'organizzazione Office 365](set-up-an-archive-and-deletion-policy-for-mailboxes.md).
