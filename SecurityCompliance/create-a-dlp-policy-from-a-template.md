---
title: Create a DLP policy from a template
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 6/29/2018
ms.audience: Admin
ms.topic: article
f1_keywords:
- ms.o365.cc.NewPolicyFromTemplate
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Strat_O365_IP
search.appverid:
- MET150
ms.assetid: 59414438-99f5-488b-975c-5023f2254369
description: "Il metodo più semplice e più comune per acquisire familiarità con i criteri DLP consiste nell'utilizzare uno dei modelli inclusi in Office 365. "
ms.openlocfilehash: 4e3a5d731538e4998858b5f9f7a296c43e6774ac
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/27/2018
ms.locfileid: "22530854"
---
# <a name="create-a-dlp-policy-from-a-template"></a><span data-ttu-id="a8c05-103">Creazione di un criterio DLP da un modello</span><span class="sxs-lookup"><span data-stu-id="a8c05-103">Create a DLP policy from a template</span></span>

<span data-ttu-id="a8c05-p101">Il metodo più semplice e più comune per acquisire familiarità con i criteri DLP consiste nell'utilizzare uno dei modelli inclusi in Office 365. È possibile utilizzare uno di questi modelli intatte o personalizzare le regole per soddisfare i requisiti di conformità specifici della propria organizzazione.</span><span class="sxs-lookup"><span data-stu-id="a8c05-p101">The easiest, most common way to get started with DLP policies is to use one of the templates included in Office 365. You can use one of these templates as is, or customize the rules to meet your organization's specific compliance requirements.</span></span>
  
<span data-ttu-id="a8c05-p102">In Office 365 sono disponibili più di 40 modelli pronti all'uso che consentono di soddisfare una vasta gamma di comuni necessità normative e aziendali. Ad esempio, esistono modelli di criteri DLP per:</span><span class="sxs-lookup"><span data-stu-id="a8c05-p102">Office 365 includes over 40 ready-to-use templates that can help you meet a wide range of common regulatory and business policy needs. For example, there are DLP policy templates for:</span></span>
  
- <span data-ttu-id="a8c05-108">Gramm-Leach-Bliley Act (GLBA)</span><span class="sxs-lookup"><span data-stu-id="a8c05-108">Gramm-Leach-Bliley Act (GLBA)</span></span>
    
- <span data-ttu-id="a8c05-109">Payment Card Industry Data Security Standard (PCI-DSS)</span><span class="sxs-lookup"><span data-stu-id="a8c05-109">Payment Card Industry Data Security Standard (PCI-DSS)</span></span>
    
- <span data-ttu-id="a8c05-110">United States Personally Identifiable Information (U.S. PII)</span><span class="sxs-lookup"><span data-stu-id="a8c05-110">United States Personally Identifiable Information (U.S. PII)</span></span>
    
- <span data-ttu-id="a8c05-111">United States Health Insurance Act (HIPAA)</span><span class="sxs-lookup"><span data-stu-id="a8c05-111">United States Health Insurance Act (HIPAA)</span></span>
    
<span data-ttu-id="a8c05-p103">È possibile ottimizzare un modello modificando alcune delle regole esistenti oppure aggiungendone di nuove. Ad esempio, è possibile aggiungere nuovi tipi di informazioni riservate a una regola, modificare i conteggi in una regola per renderne più difficile o più facile l'attivazione, consentire agli utenti di eseguire l'override delle azioni in una regola fornendo una motivazione aziendale oppure modificare i destinatari delle notifiche e dei rapporti sulle operazioni non consentite. Un modello di criteri DLP è un punto di partenza adatto a molti scenari di conformità comuni.</span><span class="sxs-lookup"><span data-stu-id="a8c05-p103">You can fine tune a template by modifying any of the existing rules or adding new ones. For example, you can add new types of sensitive information to a rule, modify the counts in a rule to make it harder or easier to trigger, allow people to override the actions in a rule by providing a business justification, or change who notifications and incident reports are sent to. A DLP policy template is a flexible starting point for many common compliance scenarios.</span></span>
  
<span data-ttu-id="a8c05-115">È inoltre possibile scegliere il modello personalizzato (che non dispone di regole predefinite) e configurare il criterio DLP da zero, per rispondere ai requisiti di conformità specifici dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="a8c05-115">You can also choose the Custom template, which has no default rules, and configure your DLP policy from scratch, to meet the specific compliance requirements for your organization.</span></span>
  
## <a name="example-identify-sensitive-information-across-all-onedrive-for-business-sites-and-restrict-access-for-people-outside-your-organization"></a><span data-ttu-id="a8c05-116">Esempio: Identificare le informazioni sensibili in OneDrive tutti i siti di Business e limitare l'accesso per gli utenti esterni all'organizzazione</span><span class="sxs-lookup"><span data-stu-id="a8c05-116">Example: Identify sensitive information across all OneDrive for Business sites and restrict access for people outside your organization</span></span>

<span data-ttu-id="a8c05-p104">OneDrive per gli account aziendali rendono più semplice per gli utenti di collaborare e condividere documenti all'interno dell'organizzazione. Ma un tema comune a responsabili della conformità informazioni riservate archiviate in OneDrive per gli account di Business possono essere condivisi inavvertitamente con persone esterne all'organizzazione. Un criterio DLP consente di ridurre il rischio.</span><span class="sxs-lookup"><span data-stu-id="a8c05-p104">OneDrive for Business accounts make it easy for people across your organization to collaborate and share documents. But a common concern for compliance officers is that sensitive information stored in OneDrive for Business accounts may be inadvertently shared with people outside your organization. A DLP policy can help mitigate this risk.</span></span>
  
<span data-ttu-id="a8c05-p105">In questo esempio, si creerà un criterio DLP che identifica dati PII negli Stati Uniti, che include i numeri di passaporto i numeri di identificazione singoli fiscale (ITIN), di previdenza sociale e degli Stati Uniti. Per imparare utilizzando un modello e quindi che si desidera modificare il modello per soddisfare i requisiti di conformità dell'organizzazione, in particolare, i seguenti vantaggi:</span><span class="sxs-lookup"><span data-stu-id="a8c05-p105">In this example, you'll create a DLP policy that identifies U.S. PII data, which includes Individual Taxpayer Identification Numbers (ITIN), Social Security Numbers, and U.S. passport numbers. You'll get started by using a template, and then you'll modify the template to meet your organization's compliance requirements—specifically, you'll:</span></span>
  
- <span data-ttu-id="a8c05-122">Aggiungere due tipi di numeri conto bancario riservati information—U.S. e degli Stati Uniti numero della patente, in modo che il criterio DLP protegge ulteriormente i dati riservati.</span><span class="sxs-lookup"><span data-stu-id="a8c05-122">Add a couple of types of sensitive information—U.S. bank account numbers and U.S. driver's license numbers—so that the DLP policy protects even more of your sensitive data.</span></span>
    
- <span data-ttu-id="a8c05-123">Verificare i criteri molto riservate, in modo da una singola occorrenza di informazioni riservate è sufficiente per limitare l'accesso per gli utenti esterni.</span><span class="sxs-lookup"><span data-stu-id="a8c05-123">Make the policy more sensitive, so that a single occurrence of sensitive information is enough to restrict access for external users.</span></span>
    
- <span data-ttu-id="a8c05-p106">Consentire agli utenti di ignorare le azioni da fornire una giustificazione aziendale o report un falso positivo. In questo modo, il criterio DLP non impedisce agli utenti dell'organizzazione di ottenere il loro lavoro, purché dispongano di un motivo aziendale valido per la condivisione delle informazioni riservate.</span><span class="sxs-lookup"><span data-stu-id="a8c05-p106">Allow users to override the actions by providing a business justification or reporting a false positive. This way, your DLP policy won't prevent people in your organization from getting their work done, provided they have a valid business reason for sharing the sensitive information.</span></span>
    
### <a name="create-a-dlp-policy-from-a-template"></a><span data-ttu-id="a8c05-126">Creazione di un criterio DLP da un modello</span><span class="sxs-lookup"><span data-stu-id="a8c05-126">Create a DLP policy from a template</span></span>

1. <span data-ttu-id="a8c05-127">Accedere a [https://protection.office.com](https://protection.office.com).</span><span class="sxs-lookup"><span data-stu-id="a8c05-127">Go to [https://protection.office.com](https://protection.office.com).</span></span>
    
2. <span data-ttu-id="a8c05-p107">Accedere a Office 365 utilizzando l'account di lavoro o della scuola. L'utente è ora in Office 365 protezione &amp; centro conformità.</span><span class="sxs-lookup"><span data-stu-id="a8c05-p107">Sign in to Office 365 using your work or school account. You're now in the Office 365 Security &amp; Compliance Center.</span></span>
    
3. <span data-ttu-id="a8c05-130">In sicurezza &amp; centro conformità \> riquadro di spostamento sinistro \> **prevenzione della perdita di dati** \> **criteri** \> **+ Crea un criterio**.</span><span class="sxs-lookup"><span data-stu-id="a8c05-130">In the Security &amp; Compliance Center \> left navigation \> **Data loss prevention** \> **Policy** \> **+ Create a policy**.</span></span>
    
    ![Creare un pulsante di criteri](media/b1e48a08-92e2-47ca-abdc-4341694ddc7c.png)
  
4. <span data-ttu-id="a8c05-132">Scegliere il modello di criterio DLP che consente di proteggere i tipi di informazioni riservate che è necessario \> **successivo**.</span><span class="sxs-lookup"><span data-stu-id="a8c05-132">Choose the DLP policy template that protects the types of sensitive information that you need \> **Next**.</span></span>
    
    <span data-ttu-id="a8c05-133">In questo esempio viene selezionato **Privacy** \> **dati negli Stati Uniti personalmente identificabili informazioni personali** perché già include la maggior parte dei tipi di informazioni riservate che si desidera proteggere, si aggiungerà un paio più avanti.</span><span class="sxs-lookup"><span data-stu-id="a8c05-133">In this example, you'll select **Privacy** \> **U.S. Personally Identifiable Information ‎(PII)‎ Data** because it already includes most of the types of sensitive information that you want to protect—you'll add a couple later.</span></span> 
    
    <span data-ttu-id="a8c05-134">Quando si seleziona un modello, è possibile leggere la descrizione a destra per scoprire quali tipi di informazioni riservate il modello protegge.</span><span class="sxs-lookup"><span data-stu-id="a8c05-134">When you select a template, you can read the description on the right to learn what types of sensitive information the template protects.</span></span>
    
    ![Pagina per la scelta di un modello di criterio DLP](media/775266f6-ad87-4080-8d7c-97f2e7403b30.png)
  
5. <span data-ttu-id="a8c05-136">Nome del criterio \> **successivo**.</span><span class="sxs-lookup"><span data-stu-id="a8c05-136">Name the policy \> **Next**.</span></span>
    
6. <span data-ttu-id="a8c05-137">Per scegliere i percorsi che si desidera che il criterio DLP per proteggere, effettuare una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="a8c05-137">To choose the locations that you want the DLP policy to protect, do one of the following:</span></span>
    
  - <span data-ttu-id="a8c05-138">Scegliere **tutte le posizioni in Office 365** \> **successivo**.</span><span class="sxs-lookup"><span data-stu-id="a8c05-138">Choose **All locations in Office 365** \> **Next**.</span></span>
    
  - <span data-ttu-id="a8c05-p108">Scegliere **Seleziona manualmente percorsi specifici** \> **successivo**. In questo esempio, selezionare questa opzione.</span><span class="sxs-lookup"><span data-stu-id="a8c05-p108">Choose **Let me choose specific locations** \> **Next**. For this example, choose this.</span></span>
    
    <span data-ttu-id="a8c05-141">Per includere o escludere un intero percorso, ad esempio tutta la posta elettronica Exchange o tutti gli account OneDrive, cambiare lo **stato** di tale posizione attivato o disattivato.</span><span class="sxs-lookup"><span data-stu-id="a8c05-141">To include or exclude an entire location such as all Exchange email or all OneDrive accounts, switch the **Status** of that location on or off.</span></span> 
    
    <span data-ttu-id="a8c05-p109">Per includere solo specifici siti di SharePoint o OneDrive per gli account di Business, cambiare lo **stato** su e quindi fare clic sui collegamenti in **Includi** scegliere specifici siti o gli account. Quando si applica un criterio a un sito, le regole configurate in quanto i criteri vengono applicati automaticamente a tutti i siti secondari del sito.</span><span class="sxs-lookup"><span data-stu-id="a8c05-p109">To include only specific SharePoint sites or OneDrive for Business accounts, switch the **Status** to on, and then click the links under **Include** to choose specific sites or accounts. When you apply a policy to a site, the rules configured in that policy are automatically applied to all subsites of that site.</span></span> 
    
    ![Opzioni per la posizione in cui è possibile applicare un criterio DLP](media/ee50a61a-e867-4571-a150-3eec8d83650f.png)
  
    <span data-ttu-id="a8c05-145">In questo esempio consente di disattivare lo **stato** per la **posta elettronica di Exchange** e **siti di SharePoint**per proteggere le informazioni riservate archiviate in OneDrive tutti gli account di Business e lasciare lo **stato** su per **gli account di OneDrive**.</span><span class="sxs-lookup"><span data-stu-id="a8c05-145">In this example, to protect sensitive information stored in all OneDrive for Business accounts, turn off the **Status** for both **Exchange email** and **SharePoint sites**, and leave the **Status** on for **OneDrive accounts**.</span></span>
    
7. <span data-ttu-id="a8c05-146">Scegliere **Impostazioni avanzate di utilizzo** \> **successivo**.</span><span class="sxs-lookup"><span data-stu-id="a8c05-146">Choose **Use advanced settings** \> **Next**.</span></span>
    
8. <span data-ttu-id="a8c05-p110">Un modello di criteri DLP è regole predefinite con condizioni e azioni che rileva problemi e lavorarci sopra specifici tipi di informazioni riservate. Si modificare, eliminare, o disattivare una qualsiasi delle regole esistenti o aggiungere nuove strutture. Al termine, fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="a8c05-p110">A DLP policy template contains predefined rules with conditions and actions that detect and act upon specific types of sensitive information. You can edit, delete, or turn off any of the existing rules, or add new ones. When done, click **Next**.</span></span>
    
    ![Le regole espanso in modelli di criteri di US PII](media/3bc9f1b6-f8ad-4334-863a-24448bb87687.png)
  
    <span data-ttu-id="a8c05-151">In questo esempio il modello di dati PII US include due regole predefinite:</span><span class="sxs-lookup"><span data-stu-id="a8c05-151">In this example, the U.S. PII Data template includes two predefined rules:</span></span>
    
  - <span data-ttu-id="a8c05-p111">**Bassa volume di contenuto rilevato PII negli Stati Uniti** Questa regola ricerca per i file contenenti tra 1 e 10 occorrenze di ognuno dei tre tipi di informazioni riservate (ITIN SSN, numeri e degli Stati Uniti passport), dove i file vengono condivisi con utenti esterni all'organizzazione. Se viene trovato, la regola invia una notifica tramite posta elettronica per l'amministratore della raccolta siti principale, proprietario del documento, e ultima persona che ha modificato il documento.</span><span class="sxs-lookup"><span data-stu-id="a8c05-p111">**Low volume of content detected U.S. PII** This rule looks for files containing between 1 and 10 occurrences of each of three types of sensitive information (ITIN, SSN, and U.S. passport numbers), where the files are shared with people outside the organization. If found, the rule sends an email notification to the primary site collection administrator, document owner, and person who last modified the document.</span></span> 
    
  - <span data-ttu-id="a8c05-p112">**Numero elevato di contenuto rilevato PII negli Stati Uniti** Questa regola ricerca per i file contenenti 10 o più occorrenze di ogni gli stessi tipi di informazioni riservate tre, dove i file vengono condivisi con utenti esterni all'organizzazione. Se viene trovato, questa azione Invia inoltre una notifica tramite posta elettronica, oltre limita l'accesso al file. Per il contenuto in un OneDrive for Business account, ciò significa che le autorizzazioni per il documento sono riservate per tutti gli utenti ad eccezione di amministratore della raccolta siti principale, proprietario del documento e persona che ha modificato il documento.</span><span class="sxs-lookup"><span data-stu-id="a8c05-p112">**High volume of content detected U.S. PII** This rule looks for files containing 10 or more occurrences of each of the same three sensitive information types, where the files are shared with people outside the organization. If found, this action also sends an email notification, plus it restricts access to the file. For content in a OneDrive for Business account, this means that permissions for the document are restricted for everyone except the primary site collection administrator, document owner, and person who last modified the document.</span></span> 
    
    <span data-ttu-id="a8c05-p113">Per soddisfare requisiti specifici della propria organizzazione, è possibile semplificare le regole trigger, in modo da una singola occorrenza di informazioni riservate è sufficiente per bloccare l'accesso per gli utenti esterni. Dopo aver osservando queste regole, è comprendere che non è necessario regole numero massimo e minimo, è necessario solo una singola regola che blocca l'accesso se viene trovata qualsiasi occorrenza di informazioni riservate.</span><span class="sxs-lookup"><span data-stu-id="a8c05-p113">To meet your organization's specific requirements, you may want to make the rules easier to trigger, so that a single occurrence of sensitive information is enough to block access for external users. After looking at these rules, you understand that you don't need low and high count rules—you need only a single rule that blocks access if any occurrence of sensitive information is found.</span></span>
    
    <span data-ttu-id="a8c05-159">In modo che si espande la regola denominata **bassa volume di contenuto rilevato US PII** \> **eliminare regola**.</span><span class="sxs-lookup"><span data-stu-id="a8c05-159">So you expand the rule named **Low volume of content detected U.S. PII** \> **Delete rule**.</span></span>
    
    ![Eliminazione di un pulsante regola](media/bc36f7d2-0fae-4af1-92e8-95ba51077b12.png)
  
9. <span data-ttu-id="a8c05-p114">A questo punto, in questo esempio, è necessario aggiungere due tipi di informazioni riservate, i numeri di conto bancario negli Stati Uniti e degli Stati Uniti numero della patente, consentire agli utenti di eseguire l'override di una regola e modificare il conteggio in tutte le occorrenze. È possibile eseguire queste operazioni per modificare una sola regola, se si desidera selezionare **elevato volume di contenuto rilevato US PII** \> **modificare una regola**.</span><span class="sxs-lookup"><span data-stu-id="a8c05-p114">Now, in this example, you need to add two sensitive information types (U.S. bank account numbers and U.S. driver's license numbers), allow people to override a rule, and change the count to any occurrence. You can do all of this by editing one rule, so select **High volume of content detected U.S. PII** \> **Edit rule**.</span></span>
    
    ![Regola pulsante Modifica](media/eaf54067-4945-4c98-8dd6-fb2c5d6de075.png)
  
10. <span data-ttu-id="a8c05-p115">Per aggiungere un tipo di informazioni riservate, nella sezione **condizioni** \> **tipi di aggiungere o modificare**. Quindi, in **Aggiungi o modifica tipi** \> scegliere **Aggiungi** \> selezionare **Il numero di conto bancario negli Stati Uniti** e il **Numero della patente di Guida di US** \> **Add** \> **Fine**.</span><span class="sxs-lookup"><span data-stu-id="a8c05-p115">To add a sensitive information type, in the **Conditions** section \> **Add or change types**. Then, under **Add or change types** \> choose **Add** \> select **U.S. Bank Account Number** and **U.S. Driver's License Number** \> **Add** \> **Done**.</span></span>
    
    ![Opzione per aggiungere o modificare i tipi](media/c6c3ae86-f7db-40a8-a6e4-db11692024be.png)
  
    ![Aggiungere o modificare riquadro tipi](media/fdbb96af-b914-4a6c-a97b-bbd014689965.png)
  
11. <span data-ttu-id="a8c05-p116">Per modificare il numero (numero di istanze di informazioni riservate necessaria per l'attivazione della regola), nella casella **numero di istanza** \> scegliere il valore **minimo** per ogni tipo di \> immettere 1. Il numero minimo non può essere vuoto. Il numero massimo può essere vuoto. un valore vuoto di tipo **max** convertire in **qualsiasi**.</span><span class="sxs-lookup"><span data-stu-id="a8c05-p116">To change the count (the number of instances of sensitive information required to trigger the rule), under **Instance count** \> choose the **min** value for each type \> enter 1. The minimum count cannot be empty. The maximum count can be empty; an empty **max** value convert to **any**.</span></span>
    
    <span data-ttu-id="a8c05-p117">Al termine, il numero di minuti per tutti i tipi di informazioni riservate dovrebbe essere **1** e il numero massimo deve essere **qualsiasi**. In altre parole, le occorrenze di questo tipo di informazioni riservate soddisferà questa condizione.</span><span class="sxs-lookup"><span data-stu-id="a8c05-p117">When finished, the min count for all of the sensitive information types should be **1** and the max count should be **any**. In other words, any occurrence of this type of sensitive information will satisfy this condition.</span></span>
    
    ![Numero di istanza per i tipi di informazioni riservate](media/5c6e08cb-59a9-4558-b54b-d899836d4737.png)
  
12. <span data-ttu-id="a8c05-174">Per la personalizzazione finale, per evitare che i criteri DLP per bloccare gli utenti di svolgere il lavoro quando sono motivazione aziendale valido o verificarsi un falso positivo, in modo che si desidera notifica all'utente per includere le opzioni per ignorare l'azione blocco.</span><span class="sxs-lookup"><span data-stu-id="a8c05-174">For the final customization, you don't want your DLP policies to block people from doing their work when they have a valid business justification or encounter a false positive, so you want the user notification to include options to override the blocking action.</span></span>
    
    <span data-ttu-id="a8c05-175">Nella sezione **notifiche utente** è evidente che le notifiche di posta elettronica e suggerimenti sui criteri vengono attivati per impostazione predefinita per questa regola nel modello.</span><span class="sxs-lookup"><span data-stu-id="a8c05-175">In the **User notifications** section, you can see that email notifications and policy tips are turned on by default for this rule in the template.</span></span> 
    
    <span data-ttu-id="a8c05-p118">Nella sezione **utente esegue l'override** è evidente che vengono attivate sostituzioni per motivazione aziendale, ma non sono le sostituzioni per segnalare falsi positivi. Scegliere **Ignora la regola automaticamente se si segnalarlo come falso positivo**.</span><span class="sxs-lookup"><span data-stu-id="a8c05-p118">In the **User overrides** section, you can see that overrides for a business justification are turned on, but overrides to report false positives are not. Choose **Override the rule automatically if they report it as a false positive**.</span></span>
    
    ![Nella sezione notifiche dell'utente e l'utente esegue l'override di sezione](media/62720e7a-a939-4c03-b414-67748f3d64a0.png)
  
13. <span data-ttu-id="a8c05-179">Nella parte superiore dell'editor di regole, modificare il nome della regola da quella predefinita **elevato volume di contenuto rilevato PII negli Stati Uniti** **qualsiasi contenuto rilevato con PII negli Stati Uniti** dal momento che ora è attivata per qualsiasi occorrenza dei relativi tipi di informazioni riservate.</span><span class="sxs-lookup"><span data-stu-id="a8c05-179">At the top of the rule editor, change the name of this rule from the default **High volume of content detected U.S. PII** to **Any content detected with U.S. PII** because it's now triggered by any occurrence of its sensitive information types.</span></span> 
    
14. <span data-ttu-id="a8c05-180">Nella parte inferiore dell'editor di regole \> **salvare**.</span><span class="sxs-lookup"><span data-stu-id="a8c05-180">At the bottom of the rule editor \> **Save**.</span></span>
    
15. <span data-ttu-id="a8c05-181">Leggere le condizioni e azioni per la regola \> **successivo**.</span><span class="sxs-lookup"><span data-stu-id="a8c05-181">Review the conditions and actions for this rule \> **Next**.</span></span>
    
    <span data-ttu-id="a8c05-p119">A destra, osservare lo **stato** passare per la regola. Se si disattiva un intero criterio, tutte le regole di contenuti nei criteri vengono disattivate anche. Tuttavia, qui è possibile disattivare una regola specifica senza disattivare il criterio intero. Può risultare utile quando è necessario analizzare una regola che genera un numero elevato di falsi positivi.</span><span class="sxs-lookup"><span data-stu-id="a8c05-p119">On the right, notice the **Status** switch for the rule. If you turn off an entire policy, all rules contained in the policy are also turned off. However, here you can turn off a specific rule without turning off the entire policy. This can be useful when you need to investigate a rule that is generating a large number of false positives.</span></span> 
    
16. <span data-ttu-id="a8c05-186">Nella pagina successiva, leggere e comprendere le operazioni seguenti e quindi scegliere se si desidera attivare la regola o verificare le funzionalità di \> **successivo**.</span><span class="sxs-lookup"><span data-stu-id="a8c05-186">On the next page, read and understand the following, and then choose whether to turn on the rule or test it out first \> **Next**.</span></span>
    
     <span data-ttu-id="a8c05-p120">Prima di creare i criteri DLP, è consigliabile distribuire gradualmente per valutare l'impatto e testare l'efficacia prima di imporre completamente. Ad esempio, non si desidera un nuovo criterio DLP inavvertitamente bloccare l'accesso a migliaia di documenti che necessitano di persone per ottenere il loro lavoro.</span><span class="sxs-lookup"><span data-stu-id="a8c05-p120">Before you create your DLP policies, you should consider rolling them out gradually to assess their impact and test their effectiveness before you fully enforce them. For example, you don't want a new DLP policy to unintentionally block access to thousands of documents that people require to get their work done.</span></span> 
    
    <span data-ttu-id="a8c05-189">Se si sta creando criteri DLP con un impatto potenziale di grandi dimensioni, è consigliabile sequenza indicata di seguito:</span><span class="sxs-lookup"><span data-stu-id="a8c05-189">If you're creating DLP policies with a large potential impact, we recommend following this sequence:</span></span>
    
17. <span data-ttu-id="a8c05-p121">Iniziare in modalità test senza suggerimenti per i criteri, quindi utilizzare i report DLP per valutare l'impatto. È possibile utilizzare i report DLP per visualizzare il numero, il percorso, il tipo e la gravità di corrispondenza del criterio. A seconda dei risultati, è possibile ottimizzare le regole in modo adeguato. In modalità test, i criteri DLP non avranno effetto sulla produttività degli utenti dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="a8c05-p121">Start in test mode without Policy Tips and then use the DLP reports to assess the impact. You can use DLP reports to view the number, location, type, and severity of policy matches. Based on the results, you can fine tune the rules as needed. In test mode, DLP policies will not impact the productivity of people working in your organization.</span></span> 
    
18. <span data-ttu-id="a8c05-p122">Passare alla modalità test con notifiche e suggerimenti per i criteri in modo da istruire gli utenti in merito ai criteri di conformità e prepararli all'applicazione delle regole. In questa fase, è inoltre possibile chiedere agli utenti di segnalare i falsi positivi per definire ulteriormente le regole.</span><span class="sxs-lookup"><span data-stu-id="a8c05-p122">Move to Test mode with notifications and Policy Tips so that you can begin to teach users about your compliance policies and prepare them for the rules that are going to be applied. At this stage, you can also ask users to report false positives so that you can further refine the rules.</span></span>
    
19. <span data-ttu-id="a8c05-p123">Attivare i criteri in modo che vengono applicate le regole e il contenuto del protetto. Continuare a monitorare i report DLP e qualsiasi rapporti operazioni non consentite o le notifiche per assicurarsi che i risultati sono si prevede.</span><span class="sxs-lookup"><span data-stu-id="a8c05-p123">Turn on the policies so that the rules are enforced and the content's protected. Continue to monitor the DLP reports and any incident reports or notifications to make sure that the results are what you intend.</span></span> 
    
    ![Opzioni per l'utilizzo della modalità di test e dell'attivazione dei criteri](media/49fafaac-c6cb-41de-99c4-c43c3e380c3a.png)
  
20. <span data-ttu-id="a8c05-199">Controllare le impostazioni per il criterio \> scegliere **Crea**.</span><span class="sxs-lookup"><span data-stu-id="a8c05-199">Review your settings for this policy \> choose **Create**.</span></span>
    
<span data-ttu-id="a8c05-200">Dopo aver creato e attivare un criterio DLP, viene distribuito a qualsiasi origini di contenuto che include, ad esempio siti di SharePoint Online o OneDrive per gli account aziendale, in cui il criterio inizia automaticamente applicate le regole in tale contenuto.</span><span class="sxs-lookup"><span data-stu-id="a8c05-200">After you create and turn on a DLP policy, it's deployed to any content sources that it includes, such as SharePoint Online sites or OneDrive for Business accounts, where the policy begins automatically enforcing its rules on that content.</span></span>
  
## <a name="view-the-status-of-a-dlp-policy"></a><span data-ttu-id="a8c05-201">Visualizzare lo stato di un criterio DLP</span><span class="sxs-lookup"><span data-stu-id="a8c05-201">View the status of a DLP policy</span></span>

<span data-ttu-id="a8c05-p124">In qualsiasi momento, è possibile visualizzare lo stato dei criteri DLP nella pagina **criteri** nella sezione **prevenzione della perdita di dati** della sicurezza &amp; centro conformità. Di seguito sono disponibili informazioni importanti, ad esempio se un criterio è stata corretta abilitazione o disabilitazione o se il criterio è in modalità test.</span><span class="sxs-lookup"><span data-stu-id="a8c05-p124">At any time, you can view the status of your DLP policies on the **Policy** page in the **Data loss prevention** section of the Security &amp; Compliance Center. Here you can find important information, such as whether a policy was successfully enabled or disabled, or whether the policy is in test mode.</span></span> 
  
<span data-ttu-id="a8c05-204">Di seguito sono riportati i diversi stati e il loro significato.</span><span class="sxs-lookup"><span data-stu-id="a8c05-204">Here are the different statuses and what they mean.</span></span>
  
|<span data-ttu-id="a8c05-205">**Stato**</span><span class="sxs-lookup"><span data-stu-id="a8c05-205">**Status**</span></span>|<span data-ttu-id="a8c05-206">**Spiegazione**</span><span class="sxs-lookup"><span data-stu-id="a8c05-206">**Explanation**</span></span>|
|:-----|:-----|
|<span data-ttu-id="a8c05-207">**Attivazione in corso...**</span><span class="sxs-lookup"><span data-stu-id="a8c05-207">**Turning on…**</span></span> <br/> |<span data-ttu-id="a8c05-p125">Il criterio viene distribuito alle origini del contenuto che include. Il criterio non è ancora applicato su tutte le origini.</span><span class="sxs-lookup"><span data-stu-id="a8c05-p125">The policy is being deployed to the content sources that it includes. The policy is not yet enforced on all sources.</span></span>  <br/> |
|<span data-ttu-id="a8c05-210">**Test, con notifiche**</span><span class="sxs-lookup"><span data-stu-id="a8c05-210">**Testing, with notifications**</span></span> <br/> |<span data-ttu-id="a8c05-p126">Il criterio è in modalità test. Le azioni in una regola non sono applicate, ma vengono raccolte le corrispondenze del criterio ed è possibile visualizzarle tramite i report DLP. Le notifiche relative alle corrispondenze del criterio vengono inviate ai destinatari specificati.</span><span class="sxs-lookup"><span data-stu-id="a8c05-p126">The policy is in test mode. The actions in a rule are not applied, but policy matches are collected and can be viewed by using the DLP reports. Notifications about policy matches are sent to the specified recipients.</span></span>  <br/> |
|<span data-ttu-id="a8c05-214">**Test, senza notifiche**</span><span class="sxs-lookup"><span data-stu-id="a8c05-214">**Testing, without notifications**</span></span> <br/> |<span data-ttu-id="a8c05-p127">Il criterio è in modalità test. Le azioni in una regola non sono applicate, ma vengono raccolte le corrispondenze del criterio ed è possibile visualizzarle tramite i report DLP. Le notifiche relative alle corrispondenze del criterio non vengono inviate ai destinatari specificati.</span><span class="sxs-lookup"><span data-stu-id="a8c05-p127">The policy is in test mode. The actions in a rule are not applied, but policy matches are collected and can be viewed by using the DLP reports. Notifications about policy matches are not sent to the specified recipients.</span></span>  <br/> |
|<span data-ttu-id="a8c05-218">**Attivo**</span><span class="sxs-lookup"><span data-stu-id="a8c05-218">**On**</span></span> <br/> |<span data-ttu-id="a8c05-p128">Il criterio è attivo e applicato. Il criterio è stato distribuito correttamente a tutte le origini del contenuto.</span><span class="sxs-lookup"><span data-stu-id="a8c05-p128">The policy is active and enforced. The policy was successfully deployed to all its content sources.</span></span>  <br/> |
|<span data-ttu-id="a8c05-221">**Disattivazione in corso...**</span><span class="sxs-lookup"><span data-stu-id="a8c05-221">**Turning off…**</span></span> <br/> |<span data-ttu-id="a8c05-p129">Il criterio viene rimosso dalle origini del contenuto che include. Il criterio potrebbe essere ancora attivo e applicato in alcune origini. La disattivazione di un criterio potrebbe richiedere fino a 45 minuti.</span><span class="sxs-lookup"><span data-stu-id="a8c05-p129">The policy is being removed from the content sources that it includes. The policy may still be active and enforced on some sources. Turning off a policy may take up to 45 minutes.</span></span>  <br/> |
|<span data-ttu-id="a8c05-225">**Disattivo**</span><span class="sxs-lookup"><span data-stu-id="a8c05-225">**Off**</span></span> <br/> |<span data-ttu-id="a8c05-p130">Il criterio non è attivo e non applicato. Le impostazioni del criterio (origini, parole chiave, durata e così via) vengono salvate.</span><span class="sxs-lookup"><span data-stu-id="a8c05-p130">The policy is not active and not enforced. The settings for the policy (sources, keywords, duration, etc) are saved.</span></span>  <br/> |
|<span data-ttu-id="a8c05-228">**Eliminazione in corso...**</span><span class="sxs-lookup"><span data-stu-id="a8c05-228">**Deleting…**</span></span> <br/> |<span data-ttu-id="a8c05-p131">Il criterio è in corso di eliminazione. Il criterio non è attivo e non applicato.</span><span class="sxs-lookup"><span data-stu-id="a8c05-p131">The policy is in the process of being deleted. The policy is not active and not enforced.</span></span>  <br/> |
   
## <a name="turn-off-a-dlp-policy"></a><span data-ttu-id="a8c05-231">Disattivare un criterio DLP</span><span class="sxs-lookup"><span data-stu-id="a8c05-231">Turn off a DLP policy</span></span>

<span data-ttu-id="a8c05-p132">È possibile modificare o disattivare un criterio DLP in qualsiasi momento. La disattivazione di un criterio disattiva tutte le regole del criterio.</span><span class="sxs-lookup"><span data-stu-id="a8c05-p132">You can edit or turn off a DLP policy at any time. Turning off a policy disables all of the rules in the policy.</span></span>
  
<span data-ttu-id="a8c05-234">Per modificare o disattivare un criterio DLP, nella pagina **criteri** \> selezionare il criterio \> **modificare i criteri**.</span><span class="sxs-lookup"><span data-stu-id="a8c05-234">To edit or turn off a DLP policy, on the **Policy** page \> select the policy \> **Edit policy**.</span></span>
  
![Criteri pulsante Modifica](media/ce319e92-0519-44fe-9507-45a409eaefe4.png)
  
<span data-ttu-id="a8c05-236">Inoltre, è possibile disattivare ogni regola singolarmente modificando il criterio e quindi attivazione e disattivazione disattivare lo **stato** della regola, come descritto in precedenza.</span><span class="sxs-lookup"><span data-stu-id="a8c05-236">In addition, you can turn off each rule individually by editing the policy and then toggling off the **Status** of that rule, as described above.</span></span> 
  
## <a name="more-information"></a><span data-ttu-id="a8c05-237">Ulteriori informazioni</span><span class="sxs-lookup"><span data-stu-id="a8c05-237">More information</span></span>

- [<span data-ttu-id="a8c05-238">Panoramica relativa ai criteri di prevenzione della perdita di dati</span><span class="sxs-lookup"><span data-stu-id="a8c05-238">Overview of data loss prevention policies</span></span>](data-loss-prevention-policies.md)
    
- [<span data-ttu-id="a8c05-239">Inviare notifiche e visualizzare i suggerimenti per i criteri DLP</span><span class="sxs-lookup"><span data-stu-id="a8c05-239">Send notifications and show policy tips for DLP policies</span></span>](use-notifications-and-policy-tips.md)
    
- [<span data-ttu-id="a8c05-240">Creare un criterio DLP per proteggere i documenti con FCI o altre proprietà</span><span class="sxs-lookup"><span data-stu-id="a8c05-240">Create a DLP policy to protect documents with FCI or other properties</span></span>](protect-documents-that-have-fci-or-other-properties.md)
    
- [<span data-ttu-id="a8c05-241">Elementi inclusi nei modelli di criteri di prevenzione della perdita dei dati</span><span class="sxs-lookup"><span data-stu-id="a8c05-241">What the DLP policy templates include</span></span>](what-the-dlp-policy-templates-include.md)
    
- [<span data-ttu-id="a8c05-242">Inventario dei tipi di informazioni riservate</span><span class="sxs-lookup"><span data-stu-id="a8c05-242">Sensitive information types inventory</span></span>](what-the-sensitive-information-types-look-for.md)
    
