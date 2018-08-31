---
title: Creare un criterio DLP per proteggere i documenti con FCI o altre proprietà
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 6/29/2018
ms.audience: Admin
ms.topic: article
f1_keywords:
- ms.o365.cc.UnifiedDLPRuleContentPropertyContainsWords
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection: Strat_O365_IP
ms.assetid: 1b9e3c6c-4308-4a20-b11e-c37b8013e177
description: Molte organizzazioni dispongono già di un processo per identificare e classificare le informazioni riservate tramite le proprietà di classificazione nell'infrastruttura di classificazione dei File (FCI) di Windows Server, le proprietà del documento in SharePoint o le proprietà del documento applicata da un sistema di terze parti. Se questo viene descritta l'organizzazione, è possibile creare un criterio DLP in Office 365 in grado di riconoscere le proprietà che sono state applicate ai documenti di Windows Server FCI o altro sistema, in modo che i documenti di Office con FCI specifica o di altro tipo può essere applicato il criterio DLP valori delle proprietà.
ms.openlocfilehash: 057cdad981249e39d6f39f231d8d60ab977e717a
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/27/2018
ms.locfileid: "23013690"
---
# <a name="create-a-dlp-policy-to-protect-documents-with-fci-or-other-properties"></a>Creare un criterio DLP per proteggere i documenti con FCI o altre proprietà

In Office 365, è possibile utilizzare un criterio di prevenzione della perdita di dati (DLP) per identificare, controllare e proteggere le informazioni riservate. Molte organizzazioni dispongono già di un processo per identificare e classificare le informazioni riservate mediante le proprietà di classificazione nell'Infrastruttura di classificazione file (FCI) di Windows Server, le proprietà dei documenti in SharePoint o le proprietà dei documenti applicate da un sistema di terze parti. Se è il caso della propria organizzazione, è possibile creare un criterio DLP in Office 365 che riconosce le proprietà che sono state applicate ai documenti da FCI di Windows Server o da un altro sistema, in modo che il criterio DLP possa essere applicato a documenti di Office con FCI specifica o altri valori di proprietà.
  
![Diagramma con Office 365 e il sistema di classificazione esterno](media/59ad0ac1-4146-4919-abd1-c74d8508d25e.png)
  
Ad esempio, l'organizzazione potrebbe utilizzare Windows Server FCI per identificare i documenti con identificazione personale informazioni personali, ad esempio numeri di previdenza sociale e quindi classificare il documento impostando le **Informazioni personali** proprietà **elevato**, **medio**, **bassa**, **pubblica**o **Non PII** in base al tipo e numero di occorrenze del PII trovato nel documento. In Office 365, è possibile creare un criterio DLP che identifica i documenti che tale proprietà è impostata su valori specifici, ad esempio **elevata** e **medie dimensioni**e quindi viene eseguita l'azione, ad esempio bloccando l'accesso a tali file. Lo stesso criterio può avere un'altra regola che ha un'azione diversa se la proprietà è impostata su **bassa**, ad esempio l'invio di una notifica tramite posta elettronica. In questo modo, DLP in Office 365 si integra con Windows Server FCI e può migliorare la protezione dei documenti di Office caricate o condivise con Office 365 dai server di file basato su Windows Server.
  
Un criterio DLP cerca semplicemente una coppia di nome/valore di proprietà specifiche. È possibile utilizzare qualsiasi proprietà del documento, purché la proprietà disponga di una proprietà gestita corrispondente per la ricerca in SharePoint. Ad esempio, una raccolta siti di SharePoint potrebbe utilizzare un tipo di contenuto denominato **Report di andata e ritorno** con un campo obbligatorio denominato **Cliente**. Ogni volta che un utente crea un report di questo tipo, è necessario immettere il nome del cliente. Questa coppia di nome/valore della proprietà può essere utilizzata anche in un criterio DLP; ad esempio, se si desidera che una regola blocchi l'accesso al documento per gli utenti esterni quando il campo **Cliente** contiene **Contoso**.
  
Nota Se si desidera applicare il criterio DLP per contenuto con le etichette di Office 365 specifici, è consigliabile non eseguire la procedura di seguito. In realtà, informazioni [sull'utilizzo di un'etichetta come condizione in un criterio DLP](data-loss-prevention-policies.md#using-a-label-as-a-condition-in-a-dlp-policy).
  
## <a name="before-you-create-the-dlp-policy"></a>Prima di creare il criterio DLP

Prima di poter utilizzare una proprietà di Windows Server FCI o altre proprietà di un criterio DLP, è necessario creare una proprietà gestita nell'interfaccia di amministrazione di SharePoint. Ecco perché.
  
Esempi
  
Questo è importante perché la prevenzione della perdita di dati in Office 365 utilizza il crawler di ricerca per identificare e classificare le informazioni riservate nei siti e quindi archiviare tali informazioni in una parte sicura dell'indice di ricerca. Quando si carica un documento in Office 365, SharePoint crea automaticamente le proprietà sottoposte a ricerca per indicizzazione in base alle proprietà del documento. Tuttavia, per utilizzare una proprietà di FCI o di altro tipo in un criterio DLP, la proprietà sottoposta a ricerca per indicizzazione deve essere mappata a una proprietà gestita in modo che il contenuto con tale proprietà venga mantenuto nell'indice.
  
Per ulteriori informazioni sulla ricerca e proprietà gestite, vedere [Manage lo schema di ricerca in SharePoint Online](http://go.microsoft.com/fwlink/p/?LinkID=627454).
  
### <a name="step-1-upload-a-document-with-the-needed-property-to-office-365"></a>Passaggio 1: Caricare un documento con la proprietà necessaria in Office 365

È necessario innanzitutto caricare un documento con la proprietà che si desidera fare riferimento nel criterio DLP. Office 365 rileva la proprietà e automaticamente il nome di una proprietà sottoposta. Nel passaggio successivo verrà creare una proprietà gestita e quindi mappare la proprietà gestita per questa proprietà.
  
### <a name="step-2-create-a-managed-property"></a>Passaggio 2: Creare una proprietà gestita

1. Accedere all'interfaccia di amministrazione di Office 365
    
2. Nel riquadro di spostamento sinistro, scegliere **Admin Center** \> **SharePoint**. L'utente è ora nell'interfaccia di amministrazione di SharePoint.
    
3. Nel riquadro di spostamento sinistro, quindi scegliere **Cerca** \> nella pagina **Amministrazione ricerca** \> **Gestisci Schema di ricerca**.
    
    ![pagina di amministrazione della ricerca nell'interfaccia di amministrazione di SharePoint](media/6bcd3aec-d11a-4f8c-9987-8f35da14d80b.png)
  
4. Nella pagina **Proprietà gestite** \> **Nuova proprietà gestita**.
    
    ![Pagina Proprietà gestite con il pulsante Nuova proprietà gestita evidenziato](media/b161c764-414c-4037-83ed-503a49fb4410.png)
  
5. Immettere un nome e una descrizione per la proprietà. Questo nome è ciò che apparirà nei criteri DLP.
    
6. Per **Tipo**, selezionare **Testo**. 
    
7. In **Caratteristiche principali**, selezionare **Disponibile per query** e **Recuperabile**.
    
8. Sotto **la ricerca per indicizzazione mapping con proprietà** \> **Aggiungi mapping**.
    
9. Nella finestra di dialogo **Selezione proprietà a ricerca per indicizzazione** \> individuare e selezionare proprietà che corrisponde alla proprietà FCI Server Windows o altre proprietà che verrà utilizzato nel criterio DLP \> **OK**.
    
    ![finestra di dialogo per la selezione di proprietà sottoposte a ricerca per indicizzazione](media/aeda1dce-1342-48bf-9594-a8e4f230e8aa.png)
  
10. Nella parte inferiore della pagina \> **OK**.
    
## <a name="create-a-dlp-policy-that-uses-an-fci-property-or-other-property"></a>Creare un criterio DLP che utilizza una proprietà FCI o un'altra proprietà

In questo esempio, un'organizzazione utilizza FCI sui server di file basato su Windows Server; in particolare, che si utilizzi la proprietà di classificazione FCI denominata **Informazioni personali** con i valori possibili di **elevato**, **medio**, **bassa**, **pubblica**e **Non PII**. Si desidera sfruttare la classificazione FCI esistente nei relativi criteri DLP in Office 365.
  
Prima di tutto, eseguire la procedura precedente per creare una proprietà gestita in SharePoint Online, che consente di eseguire il mapping alla proprietà sottoposta a ricerca per indicizzazione creata automaticamente dalla proprietà FCI.
  
Vengono successivamente, creare un criterio DLP con due regole che utilizzano la condizione **proprietà dei documenti includono uno dei valori seguenti**:
  
- **PII FCI contenuto - alto, moderato** La prima regola limita l'accesso al documento se la proprietà di classificazione delle **Informazioni personali** FCI è uguale a **elevata** o **moderato** e il documento è condiviso con utenti esterni all'organizzazione. 
    
- **PII FCI contenuto - bassa** La seconda regola invia una notifica al proprietario del documento se la proprietà di classificazione delle **Informazioni personali** FCI è uguale a **bassa** e il documento è condivisa con utenti esterni all'organizzazione. 
    
### <a name="create-the-dlp-policy-by-using-powershell"></a>Creare il criterio DLP tramite PowerShell

Si noti che la condizione **proprietà del documento contengono uno di questi valori** è temporaneamente non disponibile nell'interfaccia utente di sicurezza &amp; centro conformità, ma è comunque possibile utilizzare questa condizione utilizzando PowerShell. È possibile utilizzare il `New\Set\Get-DlpCompliancePolicy` cmdlet che consentono di utilizzare un criterio DLP e utilizzare il `New\Set\Get-DlpComplianceRule` cmdlet con il `ContentPropertyContainsWords` parametro per aggiungere la condizione **proprietà del documento contengono uno di questi valori**.
  
Per ulteriori informazioni su questi cmdlet, vedere [protezione di Office 365 &amp; cmdlet centro conformità](http://go.microsoft.com/fwlink/?LinkID=799772&amp;clcid=0x409).
  
1. [Connettersi a Office 365 Security &amp; centro conformità utilizzando PowerShell remoto](http://go.microsoft.com/fwlink/?LinkID=799771&amp;clcid=0x409)
    
2. Creare i criteri utilizzando `New-DlpCompliancePolicy`.
    
    Ecco un esempio di PowerShell che consente di creare un criterio DLP che si applica a tutte le posizioni.
    
      ```
      New-DlpCompliancePolicy -Name FCI_PII_policy -ExchangeLocation All -SharePointLocation All -OneDriveLocation All -Mode Enable
      ```

3. Creare le due regole descritte in precedenza tramite `New-DlpComplianceRule`, dove è una regola per il valore **basso** e un'altra regola è per i valori **massimo** e **medio** . 
    
    Ecco un esempio di PowerShell che vengono create le due regole. Si noti che le coppie nome/valore di proprietà vengono racchiusi tra virgolette e il nome della proprietà è possibile specificare più valori separati da virgole senza spazi, ad esempio`"<Property1>:<Value1>,<Value2>","<Property2>:<Value3>,<Value4>"....`
    
      ```
      New-DlpComplianceRule -Name FCI_PII_content-High,Moderate -Policy FCI_PII_policy -AccessScope NotInOrganization -BlockAccess $true -ContentPropertyContainsWords "Personally Identifiable Information:High,Moderate" -Disabled $falseNew-DlpComplianceRule -Name FCI_PII_content-Low -Policy FCI_PII_policy -AccessScope NotInOrganization -BlockAccess $false -ContentPropertyContainsWords "Personally Identifiable Information:Low" -Disabled $false -NotifyUser Owner
      ```

    Si noti che Windows Server FCI include numerose proprietà predefinite, incluse le **Informazioni personali** utilizzati in questo esempio. I valori possibili per ogni proprietà possono essere diversi per ogni organizzazione. **L'elevata**, **moderato**e **basso** valori utilizzati in questo esempio sono solo un esempio. Per l'organizzazione, è possibile visualizzare le proprietà di classificazione di Windows Server FCI con i valori possibili in file Server Manager delle risorse nel server di file basato su Windows Server. Per ulteriori informazioni, vedere [creare una proprietà di classificazione](http://go.microsoft.com/fwlink/p/?LinkID=627456).
    
Al termine, il criterio deve avere due nuove regole che utilizzano la condizione **proprietà del documento contengono uno di questi valori** . Si noti che questa condizione non viene visualizzato nell'interfaccia utente, anche se le altre condizioni, azioni e verranno visualizzate le impostazioni. 
  
Una regola blocca l'accesso per cui la proprietà **Informazioni personali** è uguale a **elevata** o **medio**del contenuto. Una seconda regola invia una notifica sul contenuto di cui la proprietà **Informazioni personali** uguale a **bassa**.
  
![Nuova finestra di dialogo dei criteri DLP con due regole appena create](media/5c56c13b-62a5-4f25-8eb7-ce83a844bb12.png)
  
## <a name="after-you-create-the-dlp-policy"></a>Dopo aver creato il criterio DLP

Eseguire le procedure descritte nelle sezioni precedenti verrà creato un criterio DLP che consentono di rilevare rapidamente il contenuto con tale proprietà, ma solo se tale contenuto appena caricato (in modo che il contenuto indicizzato) o se che del contenuto viene precedente ma semplicemente modificato (in modo che il contenuto reindicizzazione) .
  
Per rilevare il contenuto con tale proprietà ovunque, è possibile richiedere manualmente che la raccolta, il sito o una raccolta siti vengano reindicizzati in modo che il criterio DLP sia a conoscenza di tutto il contenuto con tale proprietà. In SharePoint Online, il contenuto viene automaticamente sottoposto a ricerca per indicizzazione in base a una pianificazione definita. Il crawler rileva il contenuto modificato dall'ultima ricerca per indicizzazione e aggiorna l'indice. Se è necessario che il criterio DLP protegga il contenuto prima della prossima ricerca per indicizzazione pianificata, è possibile eseguire questi passaggi.
  
> [!CAUTION]
> La reindicizzazione un sito può causare un notevole carico nel sistema di ricerca. Non reindicizzare il sito a meno che non lo scenario richiede assolutamente. 
  
Per ulteriori informazioni, vedere [request manualmente la ricerca per indicizzazione e la reindicizzazione di un sito, un elenco o una raccolta](http://go.microsoft.com/fwlink/p/?LinkID=627457).
  
### <a name="re-index-a-site-optional"></a>Reindicizzare un sito (facoltativo)

1. Nel sito scegliere **Impostazioni** (icona ingranaggio nella parte superiore destra) \> **Impostazioni sito**.
    
2. In **ricerca**, scegliere la **ricerca e disponibilità offline** \> **reindicizzare il sito**.
    
## <a name="more-information"></a>Ulteriori informazioni

- [Panoramica relativa ai criteri di prevenzione della perdita di dati](data-loss-prevention-policies.md)
    
- [Creare un criterio DLP da un modello](create-a-dlp-policy-from-a-template.md)
    
- [Inviare notifiche e visualizzare i suggerimenti per i criteri DLP](use-notifications-and-policy-tips.md)
    
- [Elementi inclusi nei modelli di criteri di prevenzione della perdita dei dati](what-the-dlp-policy-templates-include.md)
    
- [Inventario dei tipi di informazioni riservate](what-the-sensitive-information-types-look-for.md)
    

