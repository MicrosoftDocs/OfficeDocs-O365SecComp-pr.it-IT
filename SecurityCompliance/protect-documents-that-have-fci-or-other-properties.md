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
# <a name="create-a-dlp-policy-to-protect-documents-with-fci-or-other-properties"></a><span data-ttu-id="1b198-104">Creare un criterio DLP per proteggere i documenti con FCI o altre proprietà</span><span class="sxs-lookup"><span data-stu-id="1b198-104">Create a DLP policy to protect documents with FCI or other properties</span></span>

<span data-ttu-id="1b198-p102">In Office 365, è possibile utilizzare un criterio di prevenzione della perdita di dati (DLP) per identificare, controllare e proteggere le informazioni riservate. Molte organizzazioni dispongono già di un processo per identificare e classificare le informazioni riservate mediante le proprietà di classificazione nell'Infrastruttura di classificazione file (FCI) di Windows Server, le proprietà dei documenti in SharePoint o le proprietà dei documenti applicate da un sistema di terze parti. Se è il caso della propria organizzazione, è possibile creare un criterio DLP in Office 365 che riconosce le proprietà che sono state applicate ai documenti da FCI di Windows Server o da un altro sistema, in modo che il criterio DLP possa essere applicato a documenti di Office con FCI specifica o altri valori di proprietà.</span><span class="sxs-lookup"><span data-stu-id="1b198-p102">In Office 365, you can use a data loss prevention (DLP) policy to identify, monitor, and protect sensitive information. Many organizations already have a process to identify and classify sensitive information by using the classification properties in Windows Server File Classification Infrastructure (FCI), the document properties in SharePoint, or the document properties applied by a third-party system. If this describes your organization, you can create a DLP policy in Office 365 that recognizes the properties that have been applied to documents by Windows Server FCI or other system, so that the DLP policy can be enforced on Office documents with specific FCI or other property values.</span></span>
  
![Diagramma con Office 365 e il sistema di classificazione esterno](media/59ad0ac1-4146-4919-abd1-c74d8508d25e.png)
  
<span data-ttu-id="1b198-p103">Ad esempio, l'organizzazione potrebbe utilizzare Windows Server FCI per identificare i documenti con identificazione personale informazioni personali, ad esempio numeri di previdenza sociale e quindi classificare il documento impostando le **Informazioni personali** proprietà **elevato**, **medio**, **bassa**, **pubblica**o **Non PII** in base al tipo e numero di occorrenze del PII trovato nel documento. In Office 365, è possibile creare un criterio DLP che identifica i documenti che tale proprietà è impostata su valori specifici, ad esempio **elevata** e **medie dimensioni**e quindi viene eseguita l'azione, ad esempio bloccando l'accesso a tali file. Lo stesso criterio può avere un'altra regola che ha un'azione diversa se la proprietà è impostata su **bassa**, ad esempio l'invio di una notifica tramite posta elettronica. In questo modo, DLP in Office 365 si integra con Windows Server FCI e può migliorare la protezione dei documenti di Office caricate o condivise con Office 365 dai server di file basato su Windows Server.</span><span class="sxs-lookup"><span data-stu-id="1b198-p103">For example, your organization might use Windows Server FCI to identify documents with personally identifiable information (PII) such as social security numbers, and then classify the document by setting the **Personally Identifiable Information** property to **High**, **Moderate**, **Low**, **Public**, or **Not PII** based on the type and number of occurrences of PII found in the document. In Office 365, you can create a DLP policy that identifies documents that have that property set to specific values, such as **High** and **Medium**, and then takes an action such as blocking access to those files. The same policy can have another rule that takes a different action if the property is set to **Low**, such as sending an email notification. In this way, DLP in Office 365 integrates with Windows Server FCI and can help protect Office documents uploaded or shared to Office 365 from Windows Server-based file servers.</span></span>
  
<span data-ttu-id="1b198-p104">Un criterio DLP cerca semplicemente una coppia di nome/valore di proprietà specifiche. È possibile utilizzare qualsiasi proprietà del documento, purché la proprietà disponga di una proprietà gestita corrispondente per la ricerca in SharePoint. Ad esempio, una raccolta siti di SharePoint potrebbe utilizzare un tipo di contenuto denominato **Report di andata e ritorno** con un campo obbligatorio denominato **Cliente**. Ogni volta che un utente crea un report di questo tipo, è necessario immettere il nome del cliente. Questa coppia di nome/valore della proprietà può essere utilizzata anche in un criterio DLP; ad esempio, se si desidera che una regola blocchi l'accesso al documento per gli utenti esterni quando il campo **Cliente** contiene **Contoso**.</span><span class="sxs-lookup"><span data-stu-id="1b198-p104">A DLP policy simply looks for a specific property name/value pair. Any document property can be used, as long as the property has a corresponding managed property for SharePoint search. For example, a SharePoint site collection might use a content type named **Trip Report** with a required field named **Customer**. Whenever a person creates a trip report, they must enter the customer name. This property name/value pair can also be used in a DLP policy — for example, if you want a rule that blocks access to the document for external users when the **Customer** field contains **Contoso**.</span></span>
  
<span data-ttu-id="1b198-p105">Nota Se si desidera applicare il criterio DLP per contenuto con le etichette di Office 365 specifici, è consigliabile non eseguire la procedura di seguito. In realtà, informazioni [sull'utilizzo di un'etichetta come condizione in un criterio DLP](data-loss-prevention-policies.md#using-a-label-as-a-condition-in-a-dlp-policy).</span><span class="sxs-lookup"><span data-stu-id="1b198-p105">Note that if you want to apply your DLP policy to content with specific Office 365 labels, you should not follow the steps here. Instead, learn how to [Using a label as a condition in a DLP policy](data-loss-prevention-policies.md#using-a-label-as-a-condition-in-a-dlp-policy).</span></span>
  
## <a name="before-you-create-the-dlp-policy"></a><span data-ttu-id="1b198-120">Prima di creare il criterio DLP</span><span class="sxs-lookup"><span data-stu-id="1b198-120">Before you create the DLP policy</span></span>

<span data-ttu-id="1b198-p106">Prima di poter utilizzare una proprietà di Windows Server FCI o altre proprietà di un criterio DLP, è necessario creare una proprietà gestita nell'interfaccia di amministrazione di SharePoint. Ecco perché.</span><span class="sxs-lookup"><span data-stu-id="1b198-p106">Before you can use a Windows Server FCI property or other property in a DLP policy, you need to create a managed property in the SharePoint admin center. Here's why.</span></span>
  
<span data-ttu-id="1b198-p107">Esempi</span><span class="sxs-lookup"><span data-stu-id="1b198-p107">In SharePoint Online and OneDrive for Business, the search index is built up by crawling the content on your sites. The crawler picks up content and metadata from the documents in the form of crawled properties. The search schema helps the crawler decide what content and metadata to pick up. Examples of metadata are the author and the title of a document. However, to get the content and metadata from the documents into the search index, the crawled properties must be mapped to managed properties. Only managed properties are kept in the index. For example, a crawled property related to author is mapped to a managed property related to author.</span></span>
  
<span data-ttu-id="1b198-p108">Questo è importante perché la prevenzione della perdita di dati in Office 365 utilizza il crawler di ricerca per identificare e classificare le informazioni riservate nei siti e quindi archiviare tali informazioni in una parte sicura dell'indice di ricerca. Quando si carica un documento in Office 365, SharePoint crea automaticamente le proprietà sottoposte a ricerca per indicizzazione in base alle proprietà del documento. Tuttavia, per utilizzare una proprietà di FCI o di altro tipo in un criterio DLP, la proprietà sottoposta a ricerca per indicizzazione deve essere mappata a una proprietà gestita in modo che il contenuto con tale proprietà venga mantenuto nell'indice.</span><span class="sxs-lookup"><span data-stu-id="1b198-p108">This is important because DLP in Office 365 uses the search crawler to identify and classify sensitive information on your sites, and then store that sensitive information in a secure portion of the search index. When you upload a document to Office 365, SharePoint automatically creates crawled properties based on the document properties. But to use an FCI or other property in a DLP policy, that crawled property needs to be mapped to a managed property so that content with that property is kept in the index.</span></span>
  
<span data-ttu-id="1b198-133">Per ulteriori informazioni sulla ricerca e proprietà gestite, vedere [Manage lo schema di ricerca in SharePoint Online](http://go.microsoft.com/fwlink/p/?LinkID=627454).</span><span class="sxs-lookup"><span data-stu-id="1b198-133">For more information on search and managed properties, see [Manage the search schema in SharePoint Online](http://go.microsoft.com/fwlink/p/?LinkID=627454).</span></span>
  
### <a name="step-1-upload-a-document-with-the-needed-property-to-office-365"></a><span data-ttu-id="1b198-134">Passaggio 1: Caricare un documento con la proprietà necessaria in Office 365</span><span class="sxs-lookup"><span data-stu-id="1b198-134">Step 1: Upload a document with the needed property to Office 365</span></span>

<span data-ttu-id="1b198-p109">È necessario innanzitutto caricare un documento con la proprietà che si desidera fare riferimento nel criterio DLP. Office 365 rileva la proprietà e automaticamente il nome di una proprietà sottoposta. Nel passaggio successivo verrà creare una proprietà gestita e quindi mappare la proprietà gestita per questa proprietà.</span><span class="sxs-lookup"><span data-stu-id="1b198-p109">You first need to upload a document with the property that you want to reference in your DLP policy. Office 365 will detect the property and automatically create a crawled property from it. In the next step, you'll create a managed property, and then map the managed property to this crawled property.</span></span>
  
### <a name="step-2-create-a-managed-property"></a><span data-ttu-id="1b198-138">Passaggio 2: Creare una proprietà gestita</span><span class="sxs-lookup"><span data-stu-id="1b198-138">Step 2: Create a managed property</span></span>

1. <span data-ttu-id="1b198-139">Accedere all'interfaccia di amministrazione di Office 365</span><span class="sxs-lookup"><span data-stu-id="1b198-139">Sign in to the Office 365 admin center.</span></span>
    
2. <span data-ttu-id="1b198-p110">Nel riquadro di spostamento sinistro, scegliere **Admin Center** \> **SharePoint**. L'utente è ora nell'interfaccia di amministrazione di SharePoint.</span><span class="sxs-lookup"><span data-stu-id="1b198-p110">In the left navigation, choose **Admin centers** \> **SharePoint**. You're now in the SharePoint admin center.</span></span>
    
3. <span data-ttu-id="1b198-142">Nel riquadro di spostamento sinistro, quindi scegliere **Cerca** \> nella pagina **Amministrazione ricerca** \> **Gestisci Schema di ricerca**.</span><span class="sxs-lookup"><span data-stu-id="1b198-142">In the left navigation, choose **search** \> on the **search administration** page \> **Manage Search Schema**.</span></span>
    
    ![pagina di amministrazione della ricerca nell'interfaccia di amministrazione di SharePoint](media/6bcd3aec-d11a-4f8c-9987-8f35da14d80b.png)
  
4. <span data-ttu-id="1b198-144">Nella pagina **Proprietà gestite** \> **Nuova proprietà gestita**.</span><span class="sxs-lookup"><span data-stu-id="1b198-144">On the **Managed Properties** page \> **New Managed Property**.</span></span>
    
    ![Pagina Proprietà gestite con il pulsante Nuova proprietà gestita evidenziato](media/b161c764-414c-4037-83ed-503a49fb4410.png)
  
5. <span data-ttu-id="1b198-p111">Immettere un nome e una descrizione per la proprietà. Questo nome è ciò che apparirà nei criteri DLP.</span><span class="sxs-lookup"><span data-stu-id="1b198-p111">Enter a name and description for the property. This name is what will appear in your DLP policies.</span></span>
    
6. <span data-ttu-id="1b198-148">Per **Tipo**, selezionare **Testo**.</span><span class="sxs-lookup"><span data-stu-id="1b198-148">For **Type**, choose **Text**.</span></span> 
    
7. <span data-ttu-id="1b198-149">In **Caratteristiche principali**, selezionare **Disponibile per query** e **Recuperabile**.</span><span class="sxs-lookup"><span data-stu-id="1b198-149">Under **Main characteristics**, select **Queryable** and **Retrievable**.</span></span>
    
8. <span data-ttu-id="1b198-150">Sotto **la ricerca per indicizzazione mapping con proprietà** \> **Aggiungi mapping**.</span><span class="sxs-lookup"><span data-stu-id="1b198-150">Under **Mappings to crawled properties** \> **Add a mapping**.</span></span>
    
9. <span data-ttu-id="1b198-151">Nella finestra di dialogo **Selezione proprietà a ricerca per indicizzazione** \> individuare e selezionare proprietà che corrisponde alla proprietà FCI Server Windows o altre proprietà che verrà utilizzato nel criterio DLP \> **OK**.</span><span class="sxs-lookup"><span data-stu-id="1b198-151">In the **crawled property selection** dialog box \> find and select the crawled property that corresponds to the Windows Server FCI property or other property that you will use in your DLP policy \> **OK**.</span></span>
    
    ![finestra di dialogo per la selezione di proprietà sottoposte a ricerca per indicizzazione](media/aeda1dce-1342-48bf-9594-a8e4f230e8aa.png)
  
10. <span data-ttu-id="1b198-153">Nella parte inferiore della pagina \> **OK**.</span><span class="sxs-lookup"><span data-stu-id="1b198-153">At the bottom of the page \> **OK**.</span></span>
    
## <a name="create-a-dlp-policy-that-uses-an-fci-property-or-other-property"></a><span data-ttu-id="1b198-154">Creare un criterio DLP che utilizza una proprietà FCI o un'altra proprietà</span><span class="sxs-lookup"><span data-stu-id="1b198-154">Create a DLP policy that uses an FCI property or other property</span></span>

<span data-ttu-id="1b198-p112">In questo esempio, un'organizzazione utilizza FCI sui server di file basato su Windows Server; in particolare, che si utilizzi la proprietà di classificazione FCI denominata **Informazioni personali** con i valori possibili di **elevato**, **medio**, **bassa**, **pubblica**e **Non PII**. Si desidera sfruttare la classificazione FCI esistente nei relativi criteri DLP in Office 365.</span><span class="sxs-lookup"><span data-stu-id="1b198-p112">In this example, an organization is using FCI on its Windows Server-based file servers; specifically, they're using the FCI classification property named **Personally Identifiable Information** with possible values of **High**, **Moderate**, **Low**, **Public**, and **Not PII**. Now they want to leverage their existing FCI classification in their DLP policies in Office 365.</span></span>
  
<span data-ttu-id="1b198-157">Prima di tutto, eseguire la procedura precedente per creare una proprietà gestita in SharePoint Online, che consente di eseguire il mapping alla proprietà sottoposta a ricerca per indicizzazione creata automaticamente dalla proprietà FCI.</span><span class="sxs-lookup"><span data-stu-id="1b198-157">First, they follow the steps above to create a managed property in SharePoint Online, which maps to the crawled property created automatically from the FCI property.</span></span>
  
<span data-ttu-id="1b198-158">Vengono successivamente, creare un criterio DLP con due regole che utilizzano la condizione **proprietà dei documenti includono uno dei valori seguenti**:</span><span class="sxs-lookup"><span data-stu-id="1b198-158">Next, they create a DLP policy with two rules that both use the condition **Document properties contain any of these values**:</span></span>
  
- <span data-ttu-id="1b198-159">**PII FCI contenuto - alto, moderato** La prima regola limita l'accesso al documento se la proprietà di classificazione delle **Informazioni personali** FCI è uguale a **elevata** o **moderato** e il documento è condiviso con utenti esterni all'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="1b198-159">**FCI PII content - High, Moderate** The first rule restricts access to the document if the FCI classification property **Personally Identifiable Information** equals **High** or **Moderate** and the document is shared with people outside the organization.</span></span> 
    
- <span data-ttu-id="1b198-160">**PII FCI contenuto - bassa** La seconda regola invia una notifica al proprietario del documento se la proprietà di classificazione delle **Informazioni personali** FCI è uguale a **bassa** e il documento è condivisa con utenti esterni all'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="1b198-160">**FCI PII content - Low** The second rule sends a notification to the document owner if the FCI classification property **Personally Identifiable Information** equals **Low** and the document is shared with people outside the organization.</span></span> 
    
### <a name="create-the-dlp-policy-by-using-powershell"></a><span data-ttu-id="1b198-161">Creare il criterio DLP tramite PowerShell</span><span class="sxs-lookup"><span data-stu-id="1b198-161">Create the DLP policy by using PowerShell</span></span>

<span data-ttu-id="1b198-p113">Si noti che la condizione **proprietà del documento contengono uno di questi valori** è temporaneamente non disponibile nell'interfaccia utente di sicurezza &amp; centro conformità, ma è comunque possibile utilizzare questa condizione utilizzando PowerShell. È possibile utilizzare il `New\Set\Get-DlpCompliancePolicy` cmdlet che consentono di utilizzare un criterio DLP e utilizzare il `New\Set\Get-DlpComplianceRule` cmdlet con il `ContentPropertyContainsWords` parametro per aggiungere la condizione **proprietà del documento contengono uno di questi valori**.</span><span class="sxs-lookup"><span data-stu-id="1b198-p113">Note that the condition **Document properties contain any of these values** is temporarily not available in the UI of the Security &amp; Compliance Center, but you can still use this condition by using PowerShell. You can use the  `New\Set\Get-DlpCompliancePolicy` cmdlets to work with a DLP policy, and use the  `New\Set\Get-DlpComplianceRule` cmdlets with the  `ContentPropertyContainsWords` parameter to add the condition **Document properties contain any of these values**.</span></span>
  
<span data-ttu-id="1b198-164">Per ulteriori informazioni su questi cmdlet, vedere [protezione di Office 365 &amp; cmdlet centro conformità](http://go.microsoft.com/fwlink/?LinkID=799772&amp;clcid=0x409).</span><span class="sxs-lookup"><span data-stu-id="1b198-164">For more information on these cmdlets, see [Office 365 Security &amp; Compliance Center cmdlets](http://go.microsoft.com/fwlink/?LinkID=799772&amp;clcid=0x409).</span></span>
  
1. [<span data-ttu-id="1b198-165">Connettersi a Office 365 Security &amp; centro conformità utilizzando PowerShell remoto</span><span class="sxs-lookup"><span data-stu-id="1b198-165">Connect to the Office 365 Security &amp; Compliance Center using remote PowerShell</span></span>](http://go.microsoft.com/fwlink/?LinkID=799771&amp;clcid=0x409)
    
2. <span data-ttu-id="1b198-166">Creare i criteri utilizzando `New-DlpCompliancePolicy`.</span><span class="sxs-lookup"><span data-stu-id="1b198-166">Create the policy by using  `New-DlpCompliancePolicy`.</span></span>
    
    <span data-ttu-id="1b198-167">Ecco un esempio di PowerShell che consente di creare un criterio DLP che si applica a tutte le posizioni.</span><span class="sxs-lookup"><span data-stu-id="1b198-167">Here is a PowerShell example that creates a DLP policy that applies to all locations.</span></span>
    
      ```
      New-DlpCompliancePolicy -Name FCI_PII_policy -ExchangeLocation All -SharePointLocation All -OneDriveLocation All -Mode Enable
      ```

3. <span data-ttu-id="1b198-168">Creare le due regole descritte in precedenza tramite `New-DlpComplianceRule`, dove è una regola per il valore **basso** e un'altra regola è per i valori **massimo** e **medio** .</span><span class="sxs-lookup"><span data-stu-id="1b198-168">Create the two rules described above by using  `New-DlpComplianceRule`, where one rule is for the **Low** value, and another rule is for the **High** and **Moderate** values.</span></span> 
    
    <span data-ttu-id="1b198-p114">Ecco un esempio di PowerShell che vengono create le due regole. Si noti che le coppie nome/valore di proprietà vengono racchiusi tra virgolette e il nome della proprietà è possibile specificare più valori separati da virgole senza spazi, ad esempio`"<Property1>:<Value1>,<Value2>","<Property2>:<Value3>,<Value4>"....`</span><span class="sxs-lookup"><span data-stu-id="1b198-p114">Here is a PowerShell example that creates these two rules. Note that the property name/value pairs are enclosed in quotation marks, and a property name may specify multiple values separated by commas with no spaces, like  `"<Property1>:<Value1>,<Value2>","<Property2>:<Value3>,<Value4>"....`</span></span>
    
      ```
      New-DlpComplianceRule -Name FCI_PII_content-High,Moderate -Policy FCI_PII_policy -AccessScope NotInOrganization -BlockAccess $true -ContentPropertyContainsWords "Personally Identifiable Information:High,Moderate" -Disabled $falseNew-DlpComplianceRule -Name FCI_PII_content-Low -Policy FCI_PII_policy -AccessScope NotInOrganization -BlockAccess $false -ContentPropertyContainsWords "Personally Identifiable Information:Low" -Disabled $false -NotifyUser Owner
      ```

    <span data-ttu-id="1b198-p115">Si noti che Windows Server FCI include numerose proprietà predefinite, incluse le **Informazioni personali** utilizzati in questo esempio. I valori possibili per ogni proprietà possono essere diversi per ogni organizzazione. **L'elevata**, **moderato**e **basso** valori utilizzati in questo esempio sono solo un esempio. Per l'organizzazione, è possibile visualizzare le proprietà di classificazione di Windows Server FCI con i valori possibili in file Server Manager delle risorse nel server di file basato su Windows Server. Per ulteriori informazioni, vedere [creare una proprietà di classificazione](http://go.microsoft.com/fwlink/p/?LinkID=627456).</span><span class="sxs-lookup"><span data-stu-id="1b198-p115">Note that Windows Server FCI includes many built-in properties, including **Personally Identifiable Information** used in this example. The possible values for each property can be different for every organization. The **High**, **Moderate**, and **Low** values used here are only an example. For your organization, you can view the Windows Server FCI classification properties with their possible values in the file Server Resource Manager on the Windows Server-based file server. For more information, see [Create a classification property](http://go.microsoft.com/fwlink/p/?LinkID=627456).</span></span>
    
<span data-ttu-id="1b198-p116">Al termine, il criterio deve avere due nuove regole che utilizzano la condizione **proprietà del documento contengono uno di questi valori** . Si noti che questa condizione non viene visualizzato nell'interfaccia utente, anche se le altre condizioni, azioni e verranno visualizzate le impostazioni.</span><span class="sxs-lookup"><span data-stu-id="1b198-p116">When you finish, your policy should have two new rules that both use the **Document properties contain any of these values** condition. Note that this condition won't appear in the UI, though the other conditions, actions, and settings will appear.</span></span> 
  
<span data-ttu-id="1b198-p117">Una regola blocca l'accesso per cui la proprietà **Informazioni personali** è uguale a **elevata** o **medio**del contenuto. Una seconda regola invia una notifica sul contenuto di cui la proprietà **Informazioni personali** uguale a **bassa**.</span><span class="sxs-lookup"><span data-stu-id="1b198-p117">One rule blocks access to content where the **Personally Identifiable Information** property equals **High** or **Moderate**. A second rule sends a notification about content where the **Personally Identifiable Information** property equals **Low**.</span></span>
  
![Nuova finestra di dialogo dei criteri DLP con due regole appena create](media/5c56c13b-62a5-4f25-8eb7-ce83a844bb12.png)
  
## <a name="after-you-create-the-dlp-policy"></a><span data-ttu-id="1b198-181">Dopo aver creato il criterio DLP</span><span class="sxs-lookup"><span data-stu-id="1b198-181">After you create the DLP policy</span></span>

<span data-ttu-id="1b198-182">Eseguire le procedure descritte nelle sezioni precedenti verrà creato un criterio DLP che consentono di rilevare rapidamente il contenuto con tale proprietà, ma solo se tale contenuto appena caricato (in modo che il contenuto indicizzato) o se che del contenuto viene precedente ma semplicemente modificato (in modo che il contenuto reindicizzazione) .</span><span class="sxs-lookup"><span data-stu-id="1b198-182">Doing the steps in the previous sections will create a DLP policy that will quickly detect content with that property, but only if that content is newly uploaded (so that the content's indexed), or if that content is old but just edited (so that the content's re-indexed).</span></span>
  
<span data-ttu-id="1b198-p118">Per rilevare il contenuto con tale proprietà ovunque, è possibile richiedere manualmente che la raccolta, il sito o una raccolta siti vengano reindicizzati in modo che il criterio DLP sia a conoscenza di tutto il contenuto con tale proprietà. In SharePoint Online, il contenuto viene automaticamente sottoposto a ricerca per indicizzazione in base a una pianificazione definita. Il crawler rileva il contenuto modificato dall'ultima ricerca per indicizzazione e aggiorna l'indice. Se è necessario che il criterio DLP protegga il contenuto prima della prossima ricerca per indicizzazione pianificata, è possibile eseguire questi passaggi.</span><span class="sxs-lookup"><span data-stu-id="1b198-p118">To detect content with that property everywhere, you may want to manually request that your library, site, or site collection be re-indexed, so that the DLP policy is aware of all the content with that property. In SharePoint Online, content is automatically crawled based on a defined crawl schedule. The crawler picks up content that has changed since the last crawl and updates the index. If you need your DLP policy to protect content before the next scheduled crawl, you can take these steps.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="1b198-p119">La reindicizzazione un sito può causare un notevole carico nel sistema di ricerca. Non reindicizzare il sito a meno che non lo scenario richiede assolutamente.</span><span class="sxs-lookup"><span data-stu-id="1b198-p119">Re-indexing a site can cause a massive load on the search system. Don't re-index your site unless your scenario absolutely requires it.</span></span> 
  
<span data-ttu-id="1b198-189">Per ulteriori informazioni, vedere [request manualmente la ricerca per indicizzazione e la reindicizzazione di un sito, un elenco o una raccolta](http://go.microsoft.com/fwlink/p/?LinkID=627457).</span><span class="sxs-lookup"><span data-stu-id="1b198-189">For more information, see [Manually request crawling and re-indexing of a site, a library or a list](http://go.microsoft.com/fwlink/p/?LinkID=627457).</span></span>
  
### <a name="re-index-a-site-optional"></a><span data-ttu-id="1b198-190">Reindicizzare un sito (facoltativo)</span><span class="sxs-lookup"><span data-stu-id="1b198-190">Re-index a site (optional)</span></span>

1. <span data-ttu-id="1b198-191">Nel sito scegliere **Impostazioni** (icona ingranaggio nella parte superiore destra) \> **Impostazioni sito**.</span><span class="sxs-lookup"><span data-stu-id="1b198-191">On the site, choose **Settings** (gear icon in upper right) \> **Site Settings**.</span></span>
    
2. <span data-ttu-id="1b198-192">In **ricerca**, scegliere la **ricerca e disponibilità offline** \> **reindicizzare il sito**.</span><span class="sxs-lookup"><span data-stu-id="1b198-192">Under **Search**, choose **Search and offline availability** \> **Reindex site**.</span></span>
    
## <a name="more-information"></a><span data-ttu-id="1b198-193">Ulteriori informazioni</span><span class="sxs-lookup"><span data-stu-id="1b198-193">More information</span></span>

- [<span data-ttu-id="1b198-194">Panoramica relativa ai criteri di prevenzione della perdita di dati</span><span class="sxs-lookup"><span data-stu-id="1b198-194">Overview of data loss prevention policies</span></span>](data-loss-prevention-policies.md)
    
- [<span data-ttu-id="1b198-195">Creare un criterio DLP da un modello</span><span class="sxs-lookup"><span data-stu-id="1b198-195">Create a DLP policy from a template</span></span>](create-a-dlp-policy-from-a-template.md)
    
- [<span data-ttu-id="1b198-196">Inviare notifiche e visualizzare i suggerimenti per i criteri DLP</span><span class="sxs-lookup"><span data-stu-id="1b198-196">Send notifications and show policy tips for DLP policies</span></span>](use-notifications-and-policy-tips.md)
    
- [<span data-ttu-id="1b198-197">Elementi inclusi nei modelli di criteri di prevenzione della perdita dei dati</span><span class="sxs-lookup"><span data-stu-id="1b198-197">What the DLP policy templates include</span></span>](what-the-dlp-policy-templates-include.md)
    
- [<span data-ttu-id="1b198-198">Inventario dei tipi di informazioni riservate</span><span class="sxs-lookup"><span data-stu-id="1b198-198">Sensitive information types inventory</span></span>](what-the-sensitive-information-types-look-for.md)
    
