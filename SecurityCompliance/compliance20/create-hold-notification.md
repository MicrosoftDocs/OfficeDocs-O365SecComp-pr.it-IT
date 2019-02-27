---
title: Creare un avviso per la conservazione legale
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: ''
ms.openlocfilehash: c7fa8c7229ebb6b5304b80e15fba604c139076cd
ms.sourcegitcommit: baf23be44f1ed5abbf84f140b5ffa64fce605478
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/26/2019
ms.locfileid: "30296139"
---
# <a name="create-a-legal-hold-notice"></a><span data-ttu-id="4c695-102">Creare un avviso per la conservazione legale</span><span class="sxs-lookup"><span data-stu-id="4c695-102">Create a legal hold notice</span></span>

<span data-ttu-id="4c695-p101">Utilizzando le comunicazioni del custode avanzate di eDiscovery (Preview), le organizzazioni possono gestire il flusso di lavoro in base alla comunicazione con i depositari. Tramite lo strumento di comunicazione, i team legali possono inviare, raccogliere e tenere presenti sistematicamente le notifiche per la conservazione legale. Il processo di creazione flessibile consente inoltre ai team di personalizzare il flusso di lavoro di notifica di archiviazione e il contenuto nelle notifiche inviate ai depositari.</span><span class="sxs-lookup"><span data-stu-id="4c695-p101">Using Advanced eDiscovery (Preview) custodian communications, organizations can manage their workflow around communicating with custodians. Through the Communications tool, legal teams can systematically send, collect, and track legal hold notifications. The flexible creation process also allows teams to customize the hold notification workflow and the content in the notices sent to custodians.</span></span> 

<span data-ttu-id="4c695-106">In questo articolo vengono illustrati i passaggi del flusso di lavoro di notifica di blocco.</span><span class="sxs-lookup"><span data-stu-id="4c695-106">The article outlines the steps in the hold notification workflow.</span></span>

## <a name="step-1-specify-communication-details"></a><span data-ttu-id="4c695-107">Passaggio 1: specificare i dettagli della comunicazione</span><span class="sxs-lookup"><span data-stu-id="4c695-107">Step 1: Specify communication details</span></span>

<span data-ttu-id="4c695-108">Il primo passaggio consiste nel specificare i dettagli adeguati per le notifiche di archiviazione legale o altre comunicazioni del custode.</span><span class="sxs-lookup"><span data-stu-id="4c695-108">The first step is to specify the appropriate details for legal hold notices or other custodian communications.</span></span> 

1. <span data-ttu-id="4c695-109">Nel centro sicurezza & Compliance, passare a **eDiscovery _GT_ Advanced eDiscovery (Preview)** per visualizzare l'elenco dei casi nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="4c695-109">In the Security & Compliance Center, go to **eDiscovery > Advanced eDiscovery (Preview)** to display the list of cases in your organization.</span></span>
   
2. <span data-ttu-id="4c695-110">Fare clic sulla scheda **comunicazioni** , quindi fare clic su **nuova comunicazione**.</span><span class="sxs-lookup"><span data-stu-id="4c695-110">Click the **Communications** tab, and then click **New communication**.</span></span>
   
3. <span data-ttu-id="4c695-111">Nella pagina **nome comunicazione** specificare i seguenti dettagli di comunicazione (necessari).</span><span class="sxs-lookup"><span data-stu-id="4c695-111">On the **Name communication** page, specify the following (required) communication details.</span></span>

    - <span data-ttu-id="4c695-112">**Nome**: questo è il nome della comunicazione.</span><span class="sxs-lookup"><span data-stu-id="4c695-112">**Name**: This is the name for the communication.</span></span>
    
    - <span data-ttu-id="4c695-p102">**Responsabile del rilascio**: nell'elenco a discesa viene visualizzato un elenco di membri del caso. Ogni avviso inviato ai depositari verrà inviato per conto del responsabile del rilascio specificato.</span><span class="sxs-lookup"><span data-stu-id="4c695-p102">**Issuing officer**: The dropdown list displays a list of a case members. Each notice sent to custodians will be sent on behalf of the specified issuing officer.</span></span>

4. <span data-ttu-id="4c695-115">Fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="4c695-115">Click **Next**.</span></span>

## <a name="step-2-define-the-portal-content"></a><span data-ttu-id="4c695-116">Passaggio 2: definire il contenuto del portale</span><span class="sxs-lookup"><span data-stu-id="4c695-116">Step 2: Define the portal content</span></span>

<span data-ttu-id="4c695-p103">Successivamente, è possibile creare e aggiungere il contenuto dell'avviso di blocco. Nella pagina **Definisci contenuto portale** della creazione guidata **comunicazione** , specificare il contenuto della notifica di blocco. Questo contenuto verrà accodato automaticamente agli avvisi di emissione, riEmissione, sollecito e esCalation. Inoltre, questo contenuto verrà visualizzato nel portale di conformità del custode.</span><span class="sxs-lookup"><span data-stu-id="4c695-p103">Next, you can create and add the content of the hold notice. On the **Define portal content** page in the **Create communication** wizard, specify the contents of the hold notice. This content will be automatically appended to the Issuance, Re-Issue, Reminder, and Escalation notices. Additionally, this content will appear in the custodian's Compliance Portal.</span></span> 

<span data-ttu-id="4c695-121">Per creare il contenuto del portale:</span><span class="sxs-lookup"><span data-stu-id="4c695-121">To create the portal content:</span></span>

1. <span data-ttu-id="4c695-122">Digitare (o tagliare e incollare da un altro documento) la notifica di blocco nella casella di testo per il contenuto del portale.</span><span class="sxs-lookup"><span data-stu-id="4c695-122">Type (or cut and paster from another document) your hold notice in the textbox for the portal content.</span></span> 

2. <span data-ttu-id="4c695-123">Inserire le variabili di Unione nell'avviso per personalizzare l'avviso e condividere il portale di conformità dei depositari.</span><span class="sxs-lookup"><span data-stu-id="4c695-123">Insert merge variables into your notice to customize the notice and share the Custodian Compliance Portal.</span></span>

3. <span data-ttu-id="4c695-124">Fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="4c695-124">Click **Next**.</span></span>

  >[!Tip]
  ><span data-ttu-id="4c695-125">Per ulteriori informazioni su come personalizzare il contenuto e il formato del contenuto del portale, vedere [use the Communications editor](using-communications-editor.md).</span><span class="sxs-lookup"><span data-stu-id="4c695-125">To learn more about how to can customize the content and format of the portal content, see [Use the Communications Editor](using-communications-editor.md).</span></span>

## <a name="step-3-set-the-required-notifications"></a><span data-ttu-id="4c695-126">Passaggio 3: impostare le notifiche obbligatorie</span><span class="sxs-lookup"><span data-stu-id="4c695-126">Step 3: Set the required notifications</span></span>

<span data-ttu-id="4c695-p104">Dopo aver definito il contenuto della notifica di blocco, è possibile configurare i flussi di lavoro per l'invio e la gestione del processo di notifica. Le notifiche sono messaggi di posta elettronica inviati per la notifica e il follow-up con i depositari. Ogni custode aggiunto alla comunicazione riceverà la stessa notifica.</span><span class="sxs-lookup"><span data-stu-id="4c695-p104">After you've defined the contents of the hold notice, you can set up the workflows around sending and managing the notification process. Notifications are email messages that are sent to notify and follow-up with custodians. Every custodian added to the communication will receive the same notification.</span></span> 

<span data-ttu-id="4c695-130">Per impostare e inviare una notifica di blocco, è necessario includere le notifiche di emissione, riEmissione e rilascio.</span><span class="sxs-lookup"><span data-stu-id="4c695-130">To set up and send a hold notice, you must include Issuance, Re-Issuance, and Release notifications.</span></span>

### <a name="issuance-notification"></a><span data-ttu-id="4c695-131">Notifica di rilascio</span><span class="sxs-lookup"><span data-stu-id="4c695-131">Issuance notification</span></span> 

<span data-ttu-id="4c695-p105">Dopo aver creato la comunicazione, la **notifica di rilascio** viene avviata dal responsabile del rilascio specificato. La notifica di rilascio è la prima comunicazione inviata al custode per informarli dei loro obblighi di conservazione.</span><span class="sxs-lookup"><span data-stu-id="4c695-p105">After the communication is created, the **Issuance Notification** is initiated by the specified Issuing Officer. The Issuance notification is the first communication sent to the custodian to inform them about their preservation obligations.</span></span> 

<span data-ttu-id="4c695-134">Per creare una notifica di rilascio:</span><span class="sxs-lookup"><span data-stu-id="4c695-134">To create an issuance notification:</span></span>

1. <span data-ttu-id="4c695-135">Nel riquadro **rilascio** , fare clic su **modifica**.</span><span class="sxs-lookup"><span data-stu-id="4c695-135">In the **Issuance** tile, click **Edit**.</span></span>
   
2. <span data-ttu-id="4c695-p106">Se necessario, aggiungere ulteriori membri del caso o personale ai campi **CC** e **Ccn** . Per aggiungere più utenti a tali campi, separare gli indirizzi di posta elettronica con un punto e virgola.</span><span class="sxs-lookup"><span data-stu-id="4c695-p106">If necessary, add additional case members or staff to the **Cc** and **Bcc** fields. To add multiple users to these fields, separate email addresses with a semi-colon.</span></span>
   
3. <span data-ttu-id="4c695-138">Specificare l' **oggetto** per l'avviso (obbligatorio).</span><span class="sxs-lookup"><span data-stu-id="4c695-138">Specify the **Subject** for the notice (required).</span></span>
   
4. <span data-ttu-id="4c695-p107">Specificare il contenuto o altre istruzioni che si desidera fornire al custode (obbligatorio). Si noti che il contenuto del portale definito nel passaggio 2 viene aggiunto alla fine dell'avviso di pubblicazione.</span><span class="sxs-lookup"><span data-stu-id="4c695-p107">Specify the contents or additional instructions that you would like to provide to the custodian (required). Note that the portal content you defined in Step 2 is added to the end of the issuance notice.</span></span> 
   
5. <span data-ttu-id="4c695-141">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="4c695-141">Click **Save**</span></span> 

### <a name="re-issuance-notification"></a><span data-ttu-id="4c695-142">Notifica di riEmissione</span><span class="sxs-lookup"><span data-stu-id="4c695-142">Re-Issuance notification</span></span> 

<span data-ttu-id="4c695-p108">Quando il caso progredisce, potrebbe essere necessario che i depositari possano conservare dati aggiuntivi o meno rispetto a quelli precedentemente istruiti. Dopo aver aggiornato il contenuto dell'avviso di conservazione, la notifica di riemissione segnala ai depositari le modifiche apportate ai propri obblighi.</span><span class="sxs-lookup"><span data-stu-id="4c695-p108">As the case progresses, custodians may be required to preserve additional or less data than was previously instructed. After you update the contents of the hold notice, the re-issuance notification alerts the  custodians about the changes to their preservation obligations.</span></span>

<span data-ttu-id="4c695-145">Per creare una notifica di riemissione:</span><span class="sxs-lookup"><span data-stu-id="4c695-145">To create a re-issuance notification:</span></span> 

1. <span data-ttu-id="4c695-146">Nel riquadro **ristampa** fare clic su **modifica**.</span><span class="sxs-lookup"><span data-stu-id="4c695-146">In the **Reissue** tile, click **Edit**.</span></span>
   
2. <span data-ttu-id="4c695-p109">Se necessario, aggiungere ulteriori membri del caso o personale ai campi **CC** e **Ccn** . Per aggiungere più utenti a tali campi, separare gli indirizzi di posta elettronica con un punto e virgola.</span><span class="sxs-lookup"><span data-stu-id="4c695-p109">If necessary, add additional case members or staff to the **Cc** and **Bcc** fields. To add multiple users to these fields, separate email addresses with a semi-colon.</span></span>
   
3. <span data-ttu-id="4c695-149">Specificare l' **oggetto** per l'avviso (obbligatorio).</span><span class="sxs-lookup"><span data-stu-id="4c695-149">Specify the **Subject** for the notice (required).</span></span>
   
4. <span data-ttu-id="4c695-p110">Specificare il contenuto o altre istruzioni che si desidera fornire al custode (obbligatorio). Si noti che il contenuto del portale definito nel passaggio 2 viene aggiunto alla fine dell'avviso di riemissione.</span><span class="sxs-lookup"><span data-stu-id="4c695-p110">Specify the contents or additional instructions that you would like to provide to the custodian (required). Note that the portal content you defined in Step 2 is added to the end of the re-issuance notice.</span></span>
   
5. <span data-ttu-id="4c695-152">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="4c695-152">Click **Save**.</span></span>

>[!Note]
><span data-ttu-id="4c695-p111">Se viene modificata una notifica di blocco, la notifica di riemissione verrà inviata automaticamente a tutti i depositari assegnati alla notifica. Dopo che la notifica viene inviata, ai depositari verrà chiesto di riconfermare il proprio avviso di esenzione. Se sono stati configurati eventuali flussi di lavoro di promemoria o escalation, anche questi verranno riavviati.</span><span class="sxs-lookup"><span data-stu-id="4c695-p111">If a hold notification is modified, the re-issuance notification will be automatically sent to all custodians assigned to the notice. After the notification is sent, custodians will be asked to re-acknowledge their hold notice. If you have set up any reminder or escalation workflows, these will also re-start.</span></span> 

### <a name="release-notification"></a><span data-ttu-id="4c695-156">Notifica di rilascio</span><span class="sxs-lookup"><span data-stu-id="4c695-156">Release notification</span></span>

<span data-ttu-id="4c695-p112">Dopo aver risolto un problema o se un custode non è più soggetto alla conservazione del contenuto, è possibile rilasciare il custode da un caso. Se il custode ha precedentemente emesso un avviso di esenzione, la notifica di rilascio può essere utilizzata per avvisare i depositari che sono stati rilasciati dall'obbligo.</span><span class="sxs-lookup"><span data-stu-id="4c695-p112">After a matter is resolved or if a custodian is no longer subject to preserve content, you can release the custodian from a case. If the custodian was previously issued a hold notice, the release notification can be used to alert custodians that they have been released from their obligation.</span></span>

<span data-ttu-id="4c695-159">Per creare una notifica di rilascio:</span><span class="sxs-lookup"><span data-stu-id="4c695-159">To create a release notification:</span></span> 

1. <span data-ttu-id="4c695-160">Nella sezione **rilascia** fare clic su **modifica**.</span><span class="sxs-lookup"><span data-stu-id="4c695-160">In the **Release** tile, click **Edit**.</span></span>
   
2. <span data-ttu-id="4c695-p113">Se necessario, aggiungere ulteriori membri del caso o personale ai campi **CC** e **Ccn** . Per aggiungere più utenti a tali campi, separare gli indirizzi di posta elettronica con un punto e virgola.</span><span class="sxs-lookup"><span data-stu-id="4c695-p113">If necessary, add additional case members or staff to the **Cc** and **Bcc** fields. To add multiple users to these fields, separate email addresses with a semi-colon.</span></span>
   
3. <span data-ttu-id="4c695-163">Specificare l' **oggetto** per l'avviso (obbligatorio).</span><span class="sxs-lookup"><span data-stu-id="4c695-163">Specify the **Subject** for the notice (required).</span></span>
   
4. <span data-ttu-id="4c695-164">Specificare il contenuto o altre istruzioni che si desidera fornire al custode (obbligatorio).</span><span class="sxs-lookup"><span data-stu-id="4c695-164">Specify the contents or additional instructions that you would like to provide to the custodian (required).</span></span>
   
5. <span data-ttu-id="4c695-165">Fare clic su **Salva** e passare al passaggio successivo.</span><span class="sxs-lookup"><span data-stu-id="4c695-165">Click **Save** and go to the next step.</span></span> 

## <a name="optional-step-4-set-the-optional-notifications"></a><span data-ttu-id="4c695-166">Optional Passaggio 4: impostare le notifiche facoltative</span><span class="sxs-lookup"><span data-stu-id="4c695-166">(Optional) Step 4: Set the optional notifications</span></span>

<span data-ttu-id="4c695-167">Facoltativamente, è possibile semplificare il flusso di lavoro per la creazione e la pianificazione delle notifiche di promemoria automatica e di escalation.</span><span class="sxs-lookup"><span data-stu-id="4c695-167">Optionally, you can simplify the workflow for following up with unresponsive custodians by creating and scheduling automated reminder and escalation notifications.</span></span>

### <a name="reminders"></a><span data-ttu-id="4c695-168">Promemoria</span><span class="sxs-lookup"><span data-stu-id="4c695-168">Reminders</span></span>

<span data-ttu-id="4c695-169">Dopo aver inviato una notifica di blocco, è possibile eseguire il follow-up con i depositari non rispondenti definendo un flusso di lavoro di sollecito.</span><span class="sxs-lookup"><span data-stu-id="4c695-169">After you have sent a hold notification, you can follow-up with unresponsive custodians by defining a reminder workflow.</span></span> 

<span data-ttu-id="4c695-170">Per pianificare i promemoria:</span><span class="sxs-lookup"><span data-stu-id="4c695-170">To schedule reminders:</span></span>

1. <span data-ttu-id="4c695-171">Nel riquadro **promemoria** fare clic su **modifica**.</span><span class="sxs-lookup"><span data-stu-id="4c695-171">In the **Reminder** tile, click **Edit**.</span></span>
   
2. <span data-ttu-id="4c695-172">Abilitare il \*\*\*\* flusso di lavoro di sollecito attivando l'interruttore di **stato** (obbligatorio).</span><span class="sxs-lookup"><span data-stu-id="4c695-172">Enable the **Reminder** workflow by turning on the **Status** toggle (required).</span></span>
   
3. <span data-ttu-id="4c695-p114">Specificare l' **intervallo di sollecito (in giorni)** (obbligatorio). Questo è il numero di giorni di attesa prima dell'invio delle notifiche del primo e del promemoria di follow-up. Se ad esempio si imposta l'intervallo di sollecito su 7 giorni, il primo sollecito verrebbe inviato 7 giorni dopo l'invio iniziale della notifica di blocco. Tutti i promemoria successivi vengono inviati anche ogni 7 giorni.</span><span class="sxs-lookup"><span data-stu-id="4c695-p114">Specify the **Reminder interval (in days)** (required). This is the number of days to wait before sending the first and follow-up reminder notifications. For example, if you set the reminder interval to 7 days, then the first reminder would be sent 7 days after the hold notification was initially issued. All subsequent reminders would also be sent every 7 days.</span></span>
   
4. <span data-ttu-id="4c695-p115">Specificare il **numero di promemoria** (obbligatorio). Questo campo consente di specificare il numero di promemoria da inviare ai depositari non reattivi. Ad esempio, se si imposta il numero di promemoria su 3, un custode riceverà un massimo di tre promemoria. Dopo che un custode riconosce la notifica di blocco, i promemoria non verranno più inviati a quell'utente.</span><span class="sxs-lookup"><span data-stu-id="4c695-p115">Specify the **Number of reminders** (required). This field specifies how many reminders to send to un-responsive custodians. For example, if you set the number of reminders to 3, then a custodian would receive a maximum of 3 reminders. After a custodian acknowledges the hold notification, reminders will no longer be sent to that user.</span></span>
   
5. <span data-ttu-id="4c695-181">Specificare l' **oggetto** per l'avviso (obbligatorio).</span><span class="sxs-lookup"><span data-stu-id="4c695-181">Specify the **Subject** for the notice (required).</span></span> 
   
6. <span data-ttu-id="4c695-p116">Specificare il contenuto o altre istruzioni che si desidera fornire al custode (obbligatorio). Si noti che il contenuto del portale definito nel passaggio 2 viene aggiunto alla fine della notifica di sollecito.</span><span class="sxs-lookup"><span data-stu-id="4c695-p116">Specify the contents or additional instructions that you would like to provide to the custodian (required). Note that the portal content you defined in Step 2 is added to the end of the reminder notice.</span></span>
   
7. <span data-ttu-id="4c695-184">Fare clic su **Salva** e passare al passaggio successivo.</span><span class="sxs-lookup"><span data-stu-id="4c695-184">Click **Save** and go the the next step.</span></span>

### <a name="escalations"></a><span data-ttu-id="4c695-185">Escalation</span><span class="sxs-lookup"><span data-stu-id="4c695-185">Escalations</span></span> 

<span data-ttu-id="4c695-p117">In alcuni casi, potrebbero essere necessari ulteriori modi per eseguire il follow-up con i depositari non rispondenti. Se un custode non riconosce una notifica di blocco dopo aver ricevuto il numero specificato di promemoria, il team legale può specificare un flusso di lavoro per inviare automaticamente un avviso di escalation al custode e al relativo responsabile.</span><span class="sxs-lookup"><span data-stu-id="4c695-p117">In some situations, you may need additional ways to follow-up with unresponsive custodians. If a custodian doesn't acknowledge a hold notification after receiving the specified number of reminders, the legal team can specify a workflow to automatically send an escalation notice to the custodian and their manager.</span></span>

<span data-ttu-id="4c695-188">Per pianificare le escalation:</span><span class="sxs-lookup"><span data-stu-id="4c695-188">To schedule escalations:</span></span>

1. <span data-ttu-id="4c695-189">Nel riquadro \*\*\*\* escalation fare clic su **modifica**.</span><span class="sxs-lookup"><span data-stu-id="4c695-189">In the **Escalation** tile, click **Edit**.</span></span>
   
2. <span data-ttu-id="4c695-190">Abilitare il \*\*\*\* flusso di lavoro per l'escalation attivando l'interruttore di **stato** .</span><span class="sxs-lookup"><span data-stu-id="4c695-190">Enable the **Escalation** workflow by turning on the **Status** toggle.</span></span>
   
3. <span data-ttu-id="4c695-191">Specificare l' **intervallo di escalation (in giorni)** (obbligatorio).</span><span class="sxs-lookup"><span data-stu-id="4c695-191">Specify the **Escalation interval (in days)** (required).</span></span> 
   
4. <span data-ttu-id="4c695-p118">Specificare il **numero di** escalation (obbligatorio). Questo campo consente di specificare il numero di escalation da inviare ai depositari non reattivi. Ad esempio, se si imposta il numero di escalation su 3, un avviso di escalation verrebbe inviato al custode e al relativo Manager al massimo 3 volte. Dopo che un custode riconosce la notifica di blocco, le escalation non verranno più inviate.</span><span class="sxs-lookup"><span data-stu-id="4c695-p118">Specify the **Number of escalations** (required). This field specifies how many escalations to send to un-responsive custodians. For example, if you set the number of escalations to 3, then an escalation notice would be sent to the custodian and their manager a maximum of 3 times. After a custodian acknowledges the hold notification, escalations will no longer be sent.</span></span> 
   
5. <span data-ttu-id="4c695-196">Specificare l' **oggetto** per l'avviso (obbligatorio).</span><span class="sxs-lookup"><span data-stu-id="4c695-196">Specify the **Subject** for the notice (required).</span></span> 
   
6. <span data-ttu-id="4c695-p119">Specificare il contenuto o altre istruzioni che si desidera fornire al custode (obbligatorio). Si noti che il contenuto del portale definito nel passaggio 2 viene aggiunto alla fine dell'avviso di escalation.</span><span class="sxs-lookup"><span data-stu-id="4c695-p119">Specify the contents or additional instructions that you would like to provide to the custodian (required). Note that the portal content you defined in Step 2 is added to the end of the escalation notice.</span></span>
   
7. <span data-ttu-id="4c695-199">Fare clic su **Salva** e passare al passaggio successivo.</span><span class="sxs-lookup"><span data-stu-id="4c695-199">Click **Save** and go the the next step.</span></span>
   
## <a name="step-5-assign-custodians"></a><span data-ttu-id="4c695-200">Passaggio 5: assegnare i depositari</span><span class="sxs-lookup"><span data-stu-id="4c695-200">Step 5: Assign custodians</span></span> 

<span data-ttu-id="4c695-201">Dopo aver finalizzato il contenuto per le notifiche, selezionare i depositari ai quali inviare le notifiche.</span><span class="sxs-lookup"><span data-stu-id="4c695-201">After you have finalized the content for notifications, select the custodians to send the notifications to.</span></span> 

<span data-ttu-id="4c695-202">Per aggiungere i depositari:</span><span class="sxs-lookup"><span data-stu-id="4c695-202">To add custodians:</span></span>

1. <span data-ttu-id="4c695-203">Assegnare i depositari alla comunicazione facendo clic sulla casella di controllo accanto al nome.</span><span class="sxs-lookup"><span data-stu-id="4c695-203">Assign custodians to the communication by clicking the checkbox next to their name.</span></span>

    <span data-ttu-id="4c695-204">Dopo la creazione della comunicazione, il flusso di lavoro di notifica verrà applicato automaticamente ai depositari selezionati.</span><span class="sxs-lookup"><span data-stu-id="4c695-204">After the communication is created, the notification workflow will automatically apply to the selected custodians.</span></span>
   
2. <span data-ttu-id="4c695-205">Fare clic su **Avanti** per esaminare le impostazioni di comunicazione e i dettagli.</span><span class="sxs-lookup"><span data-stu-id="4c695-205">Click **Next** to review the communication settings and details.</span></span>
 
>[!NOTE]
><span data-ttu-id="4c695-206">È possibile aggiungere solo i depositari che sono stati aggiunti al caso e non sono stati inviati un'altra notifica all'interno del caso.</span><span class="sxs-lookup"><span data-stu-id="4c695-206">You can only add custodians who have been added to the case and haven't been sent another notification within the case.</span></span>

## <a name="step-6-review-settings"></a><span data-ttu-id="4c695-207">Passaggio 6: rivedere le impostazioni</span><span class="sxs-lookup"><span data-stu-id="4c695-207">Step 6: Review settings</span></span>

<span data-ttu-id="4c695-208">Dopo aver esaminato le impostazioni e fare clic su **Invia** per completare la comunicazione, il sistema avvierà automaticamente il flusso di lavoro di comunicazione inviando la notifica di rilascio.</span><span class="sxs-lookup"><span data-stu-id="4c695-208">After you review the settings and click **Send** to complete the communication, the system will automatically start the communication workflow by sending the issuance notice.</span></span>