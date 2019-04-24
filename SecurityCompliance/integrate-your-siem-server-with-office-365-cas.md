---
title: Integrare il server SIEM con Office 365 Cloud App Security
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: dd6d2417-49c4-4de6-9294-67fdabbf8532
description: È possibile integrare il server SIEM con Office 365 cloud app Security. Leggere questo articolo per ottenere una panoramica di come funziona e come configurarlo.
ms.openlocfilehash: 82b5e0e6467bd42acba3c40d67e4e0363a7e0f72
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "32254758"
---
# <a name="integrate-your-siem-server-with-office-365-cloud-app-security"></a><span data-ttu-id="98f20-104">Integrare il server SIEM con Office 365 Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="98f20-104">Integrate your SIEM server with Office 365 Cloud App Security</span></span>
  
|<span data-ttu-id="98f20-105">Valutazione \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="98f20-105">\*\*\*\*Evaluation\*\* \>\*\*</span></span>|<span data-ttu-id="98f20-106">Planning \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="98f20-106">\*\*\*\*Planning\*\* \>\*\*</span></span>|<span data-ttu-id="98f20-107">Distribuzione \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="98f20-107">\*\*\*\*Deployment\*\* \>\*\*</span></span>|<span data-ttu-id="98f20-108">Utilizzo \* \* \* \*</span><span class="sxs-lookup"><span data-stu-id="98f20-108">\*\*\*\*Utilization\*\*\*\*</span></span>|
|:-----|:-----|:-----|:-----|
|[<span data-ttu-id="98f20-109">Iniziare a valutare</span><span class="sxs-lookup"><span data-stu-id="98f20-109">Start evaluating</span></span>](office-365-cas-overview.md) <br/> |[<span data-ttu-id="98f20-110">Avviare la pianificazione</span><span class="sxs-lookup"><span data-stu-id="98f20-110">Start planning</span></span>](get-ready-for-office-365-cas.md) <br/> |<span data-ttu-id="98f20-111">Sei qui!</span><span class="sxs-lookup"><span data-stu-id="98f20-111">You are here!</span></span>  <br/> [<span data-ttu-id="98f20-112">Passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="98f20-112">Next step</span></span>](utilization-activities-for-ocas.md) <br/> |[<span data-ttu-id="98f20-113">Iniziare a utilizzare</span><span class="sxs-lookup"><span data-stu-id="98f20-113">Start utilizing</span></span>](utilization-activities-for-ocas.md) <br/> |
   
## <a name="overview-and-prerequisites"></a><span data-ttu-id="98f20-114">Panoramica e prerequisiti</span><span class="sxs-lookup"><span data-stu-id="98f20-114">Overview and prerequisites</span></span>

<span data-ttu-id="98f20-115">È possibile integrare [Office 365 cloud app Security](get-ready-for-office-365-cas.md) con il server di gestione eventi e informazioni di sicurezza (Siem) per abilitare il monitoraggio centralizzato degli avvisi.</span><span class="sxs-lookup"><span data-stu-id="98f20-115">You can integrate [Office 365 Cloud App Security](get-ready-for-office-365-cas.md) with your security information and event management (SIEM) server to enable centralized monitoring of alerts.</span></span> <span data-ttu-id="98f20-116">Questo è particolarmente vantaggioso per le organizzazioni che utilizzano i servizi cloud e le applicazioni server locali.</span><span class="sxs-lookup"><span data-stu-id="98f20-116">This is especially beneficial for organizations who are using cloud services and on-premises server applications.</span></span> <span data-ttu-id="98f20-117">È possibile integrare il server SIEM per estrarre avvisi e attività da Office 365 cloud app Security nel server SIEM.</span><span class="sxs-lookup"><span data-stu-id="98f20-117">You can integrate your SIEM server to pull alerts and activities from Office 365 Cloud App Security into your SIEM server.</span></span> <span data-ttu-id="98f20-118">L'integrazione con un server SIEM consente al team di sicurezza di proteggere al meglio le applicazioni di Office 365 mantenendo il flusso di lavoro di sicurezza usuale, automatizzando determinate procedure di sicurezza e correlando tra gli eventi basati su cloud e in locale.</span><span class="sxs-lookup"><span data-stu-id="98f20-118">Integrating with a SIEM server allows your security team to better protect your Office 365 applications while maintaining your usual security workflow, by automating certain security procedures and correlating between cloud-based and on-premises events.</span></span>  
  
<span data-ttu-id="98f20-119">Quando si integra per la prima volta il server SIEM con Office 365 cloud app Security, gli avvisi degli ultimi due giorni vengono inoltrati al server SIEM, nonché tutti gli avvisi da quel momento in poi (in base ai filtri selezionati).</span><span class="sxs-lookup"><span data-stu-id="98f20-119">When you first integrate your SIEM server with Office 365 Cloud App Security, alerts from the last two days are forwarded to the SIEM server, as well as all alerts from then on (based on any filters you select).</span></span> <span data-ttu-id="98f20-120">Inoltre, se si disabilita questa funzionalità per un periodo di tempo prolungato, quando si abilita di nuovo, verranno inoltrati gli ultimi due giorni di avvisi e quindi tutti gli avvisi da quel momento in poi.</span><span class="sxs-lookup"><span data-stu-id="98f20-120">Additionally, if you disable this feature for an extended period, when you enable it again, it will forward the past two days of alerts and then all alerts from then on.</span></span>

### <a name="siem-integration-architecture"></a><span data-ttu-id="98f20-121">Architettura di integrazione di SIEM</span><span class="sxs-lookup"><span data-stu-id="98f20-121">SIEM integration architecture</span></span>

<span data-ttu-id="98f20-122">Un agente di SIEM è configurato nella rete dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="98f20-122">A SIEM agent is set up in your organization's network.</span></span> <span data-ttu-id="98f20-123">Quando viene distribuita e configurata, l'agente di SIEM estrae i tipi di dati configurati (avvisi) con Office 365 cloud app Security RESTful APIs.</span><span class="sxs-lookup"><span data-stu-id="98f20-123">When deployed and configured, the SIEM agent pulls the data types that were configured (alerts) using Office 365 Cloud App Security RESTful APIs.</span></span> <span data-ttu-id="98f20-124">Il traffico viene quindi inviato su un canale HTTPS crittografato sulla porta 443.</span><span class="sxs-lookup"><span data-stu-id="98f20-124">The traffic is then sent over an encrypted HTTPS channel on port 443.</span></span>
  
<span data-ttu-id="98f20-125">Quando un agente SIEM recupera i dati da Office 365 cloud app Security, invia i messaggi syslog al server SIEM locale utilizzando le configurazioni di rete fornite durante l'installazione (TCP o UDP con una porta personalizzata).</span><span class="sxs-lookup"><span data-stu-id="98f20-125">When a SIEM agent retrieves data from Office 365 Cloud App Security, it sends the Syslog messages to your local SIEM server using the network configurations that are provided during setup (TCP or UDP with a custom port).</span></span>

![Architettura di sicurezza di SIEM e cloud app](media/siem-architecture.png)

### <a name="supported-siem-servers"></a><span data-ttu-id="98f20-127">Server SIEM supportati</span><span class="sxs-lookup"><span data-stu-id="98f20-127">Supported SIEM servers</span></span>

<span data-ttu-id="98f20-128">Office 365 cloud app Security attualmente supporta i seguenti server SIEM:</span><span class="sxs-lookup"><span data-stu-id="98f20-128">Office 365 Cloud App Security currently supports the following SIEM servers:</span></span>
- <span data-ttu-id="98f20-129">Micro Focus ArcSight</span><span class="sxs-lookup"><span data-stu-id="98f20-129">Micro Focus ArcSight</span></span>
- <span data-ttu-id="98f20-130">CEF generico</span><span class="sxs-lookup"><span data-stu-id="98f20-130">Generic CEF</span></span>

### <a name="prerequisites"></a><span data-ttu-id="98f20-131">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="98f20-131">Prerequisites</span></span>

- <span data-ttu-id="98f20-132">È necessario essere un amministratore globale o un amministratore della sicurezza per eseguire le attività descritte in questo articolo.</span><span class="sxs-lookup"><span data-stu-id="98f20-132">You must be a global administrator or security administrator to perform the tasks described in this article.</span></span> <span data-ttu-id="98f20-133">Vedere [Permissions in the Office &amp; 365 Security Compliance Center](permissions-in-the-security-and-compliance-center.md)</span><span class="sxs-lookup"><span data-stu-id="98f20-133">See [Permissions in the Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md)</span></span>

- <span data-ttu-id="98f20-134">È necessario che [Office 365 cloud app Security sia abilitato](turn-on-office-365-cas.md) per la propria organizzazione.</span><span class="sxs-lookup"><span data-stu-id="98f20-134">You must have [Office 365 Cloud App Security enabled](turn-on-office-365-cas.md) for your organization.</span></span>

- <span data-ttu-id="98f20-135">La [registrazione di controllo](turn-audit-log-search-on-or-off.md) deve essere attivata per Office 365</span><span class="sxs-lookup"><span data-stu-id="98f20-135">[Audit logging](turn-audit-log-search-on-or-off.md) must be turned on for Office 365</span></span>

- <span data-ttu-id="98f20-136">Per configurare l'integrazione del server SIEM è necessario disporre di un server standard che soddisfi i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="98f20-136">You must have a standard server that meets the following requirements in order to configure SIEM server integration:</span></span>
    - <span data-ttu-id="98f20-137">SISTEMA operativo: Windows o Linux (può essere una macchina virtuale)</span><span class="sxs-lookup"><span data-stu-id="98f20-137">OS: Windows or Linux (this can be a virtual machine)</span></span>
    - <span data-ttu-id="98f20-138">CPU: 2</span><span class="sxs-lookup"><span data-stu-id="98f20-138">CPU: 2</span></span>
    - <span data-ttu-id="98f20-139">Spazio su disco: 20 GB</span><span class="sxs-lookup"><span data-stu-id="98f20-139">Disk space: 20 GB</span></span>
    - <span data-ttu-id="98f20-140">RAM: 2 GB</span><span class="sxs-lookup"><span data-stu-id="98f20-140">RAM: 2 GB</span></span>
    - <span data-ttu-id="98f20-141">[Oracle Java 8](http://www.oracle.com/technetwork/java/javase/downloads/index.html) installato</span><span class="sxs-lookup"><span data-stu-id="98f20-141">[Oracle Java 8](http://www.oracle.com/technetwork/java/javase/downloads/index.html) installed</span></span>
    - <span data-ttu-id="98f20-142">Firewall configurato come descritto in [requisiti di rete](https://docs.microsoft.com/cloud-app-security/network-requirements)</span><span class="sxs-lookup"><span data-stu-id="98f20-142">Firewall configured as described in [Network requirements](https://docs.microsoft.com/cloud-app-security/network-requirements)</span></span>

- <span data-ttu-id="98f20-143">È necessario disporre di informazioni dettagliate sull' **host syslog remoto** e sul **numero di porta di Syslot**.</span><span class="sxs-lookup"><span data-stu-id="98f20-143">You must have details about your **Remote syslog host** and **Syslot port number**.</span></span> <span data-ttu-id="98f20-144">Un amministratore di rete o un amministratore di sicurezza dovrebbe essere in grado di individuare tali informazioni.</span><span class="sxs-lookup"><span data-stu-id="98f20-144">A network administrator or security administrator should be able to help you locate that information.</span></span> 

- <span data-ttu-id="98f20-145">È necessario accettare le [condizioni di licenza software](https://go.microsoft.com/fwlink/?linkid=862491) per scaricare il [file jar](https://go.microsoft.com/fwlink/?linkid=838596) che è necessario integrare il server Siem.</span><span class="sxs-lookup"><span data-stu-id="98f20-145">You must agree to [software license terms](https://go.microsoft.com/fwlink/?linkid=862491) to download the [JAR file](https://go.microsoft.com/fwlink/?linkid=838596) you'll need to integrate your SIEM server.</span></span>
 
## <a name="step-1-set-it-up-a-siem-agent-in-office-365-cloud-app-security"></a><span data-ttu-id="98f20-146">Passaggio 1: conFigurarlo come agente di SIEM in Office 365 cloud app Security</span><span class="sxs-lookup"><span data-stu-id="98f20-146">Step 1: Set it up a SIEM agent in Office 365 Cloud App Security</span></span>

1. <span data-ttu-id="98f20-147">Accedere al portale[https://portal.cloudappsecurity.com](https://portal.cloudappsecurity.com)di sicurezza delle app cloud e accedere.</span><span class="sxs-lookup"><span data-stu-id="98f20-147">Go to the Cloud App Security portal ([https://portal.cloudappsecurity.com](https://portal.cloudappsecurity.com)) and sign in.</span></span>
  
2. <span data-ttu-id="98f20-148">Fare clic su impostazioni di **protezione**di **Settings** \> e quindi scegliere agenti Siem.</span><span class="sxs-lookup"><span data-stu-id="98f20-148">Click **Settings** \> **Security extensions**, and then choose SIEM agents.</span></span><br/>
<span data-ttu-id="98f20-149">![Scegliere Settings > Security Extensions](media/Settings-SecurityExtensions.png)</span><span class="sxs-lookup"><span data-stu-id="98f20-149">![Choose Settings > Security extensions](media/Settings-SecurityExtensions.png)</span></span>

3. <span data-ttu-id="98f20-150">Scegliere **Aggiungi agente Siem**.</span><span class="sxs-lookup"><span data-stu-id="98f20-150">Choose **Add SIEM agent**.</span></span><br/><span data-ttu-id="98f20-151">![Scegliere Aggiungi agente SIEM.](media/SIEMAgents.png)</span><span class="sxs-lookup"><span data-stu-id="98f20-151">![Choose Add SIEM agent.](media/SIEMAgents.png)</span></span>
    
4. <span data-ttu-id="98f20-152">Scegliere **Avvia procedura guidata**.</span><span class="sxs-lookup"><span data-stu-id="98f20-152">Choose **Start wizard**.</span></span><br/><span data-ttu-id="98f20-153">![Ottenere assistenza o avviare la procedura guidata](media/HelpOrWizard.png)</span><span class="sxs-lookup"><span data-stu-id="98f20-153">![Get help or start the wizard](media/HelpOrWizard.png)</span></span> 
    
5. <span data-ttu-id="98f20-154">Nel passaggio **generale** , specificare un nome, quindi **selezionare il formato Siem** e impostare le **Impostazioni avanzate** rilevanti per tale formato.</span><span class="sxs-lookup"><span data-stu-id="98f20-154">In the **General** step, specify a name, and **Select your SIEM format** and set any **Advanced settings** that are relevant to that format.</span></span> <span data-ttu-id="98f20-155">Fare quindi clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="98f20-155">Then choose **Next**.</span></span><br/><span data-ttu-id="98f20-156">![Specificare un nome e un tipo](media/ChooseAgentTypeAndName.png)</span><span class="sxs-lookup"><span data-stu-id="98f20-156">![Specify a name and type](media/ChooseAgentTypeAndName.png)</span></span>
    
6. <span data-ttu-id="98f20-157">Nel passaggio **syslog Remote** , specificare l'indirizzo IP o il nome host dell' **host syslog remoto** e il **numero di porta syslog**.</span><span class="sxs-lookup"><span data-stu-id="98f20-157">In the **Remote Syslog** step, specify the IP address or hostname of the **Remote syslog host** and the **Syslog port number**.</span></span> <span data-ttu-id="98f20-158">Selezionare TCP o UDP come protocollo syslog remoto.</span><span class="sxs-lookup"><span data-stu-id="98f20-158">Select TCP or UDP as the Remote Syslog protocol.</span></span> <span data-ttu-id="98f20-159">Se non si dispone di tali informazioni, è possibile collaborare con l'amministratore di rete o con l'amministratore della sicurezza. Fare quindi clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="98f20-159">(You can work with your network administrator or security administrator to get these details if you don't have them.) Then choose **Next**.</span></span><br/><span data-ttu-id="98f20-160">![Specificare i dettagli di syslog remoti](media/ArcSightS1Syslog.png)</span><span class="sxs-lookup"><span data-stu-id="98f20-160">![Specify Remote Syslog details](media/ArcSightS1Syslog.png)</span></span>
  
7. <span data-ttu-id="98f20-161">Nel passaggio **tipi di dati** effettuare una delle operazioni seguenti e quindi fare clic su **Avanti**:</span><span class="sxs-lookup"><span data-stu-id="98f20-161">In the **Data Types** step, do one of the following, and then click **Next**:</span></span>
    - <span data-ttu-id="98f20-162">Mantieni l'impostazione predefinita di **tutti gli avvisi**</span><span class="sxs-lookup"><span data-stu-id="98f20-162">Keep the default setting of **All Alerts**</span></span><br/><span data-ttu-id="98f20-163">O</span><span class="sxs-lookup"><span data-stu-id="98f20-163">OR</span></span>
    - <span data-ttu-id="98f20-164">Fare clic su **tutti gli avvisi**e quindi scegliere **filtri specifici**.</span><span class="sxs-lookup"><span data-stu-id="98f20-164">Click **All alerts**, and then choose **Specific filters**.</span></span> <span data-ttu-id="98f20-165">Definire i filtri per selezionare i tipi di avvisi che si desidera inviare al server SIEM.</span><span class="sxs-lookup"><span data-stu-id="98f20-165">Define filters to select the kinds of alerts you want to send to your SIEM server.</span></span>
<br/><span data-ttu-id="98f20-166">![Passaggio dei tipi di dati della procedura guidata](media/ArcSightS1ExportOptions.png)</span><span class="sxs-lookup"><span data-stu-id="98f20-166">![Data Types step of the wizard](media/ArcSightS1ExportOptions.png)</span></span>
  
8. <span data-ttu-id="98f20-167">Nella schermata Congratulazioni, copiare il token e salvarlo in un secondo momento.</span><span class="sxs-lookup"><span data-stu-id="98f20-167">On the Congratulations screen, copy the token and save it for later.</span></span><br/>![Schermata dell'agente di SIEM creato](media/SIEMAgentFinished.png) 

> [!IMPORTANT]
> <span data-ttu-id="98f20-169">A questo punto, è stato configurato un agente SIEM in Office 365 cloud app Security, ma l'integrazione del server SIEM non è ancora stata completata.</span><span class="sxs-lookup"><span data-stu-id="98f20-169">At this point, you have set up a SIEM agent in Office 365 Cloud App Security, but your SIEM server integration is not yet finished.</span></span> <span data-ttu-id="98f20-170">Procedere con il passaggio successivo per continuare l'integrazione del server SIEM.</span><span class="sxs-lookup"><span data-stu-id="98f20-170">Proceed to the next step to continue your SIEM server integration.</span></span>

<span data-ttu-id="98f20-171">Dopo aver fatto clic su Chiudi e lasciare la procedura guidata, nella schermata estensioni di sicurezza, è possibile visualizzare l'agente SIEM aggiunto nella tabella.</span><span class="sxs-lookup"><span data-stu-id="98f20-171">After you click Close and leave the wizard, on the Security extensions screen, you can see the SIEM agent you added in the table.</span></span> <span data-ttu-id="98f20-172">Verrà visualizzato lo stato **creato** finché non viene connesso in un secondo momento.</span><span class="sxs-lookup"><span data-stu-id="98f20-172">It will show a status of **Created** until it's connected later.</span></span>

![Agente di SIEM creato](media/SIEMAgentCreated.png)
    
## <a name="step-2-download-a-jar-file-and-run-it-on-your-siem-server"></a><span data-ttu-id="98f20-174">Passaggio 2: scaricare un file JAR ed eseguirlo sul server SIEM</span><span class="sxs-lookup"><span data-stu-id="98f20-174">Step 2: Download a JAR file and run it on your SIEM server</span></span>

1. <span data-ttu-id="98f20-175">Scaricare l' [agente di Microsoft cloud app Security Siem](https://go.microsoft.com/fwlink/?linkid=838596) e decomprimere la cartella.</span><span class="sxs-lookup"><span data-stu-id="98f20-175">Download the [Microsoft Cloud App Security SIEM Agent](https://go.microsoft.com/fwlink/?linkid=838596) and unzip the folder.</span></span> <span data-ttu-id="98f20-176">Per continuare, è necessario accettare le [condizioni di licenza software](https://go.microsoft.com/fwlink/?linkid=862491) .</span><span class="sxs-lookup"><span data-stu-id="98f20-176">(You must agree to [software license terms](https://go.microsoft.com/fwlink/?linkid=862491) in order to proceed.)</span></span> 
    
2. <span data-ttu-id="98f20-177">Estrarre il file. jar dalla cartella zippata ed eseguirlo sul server SIEM.</span><span class="sxs-lookup"><span data-stu-id="98f20-177">Extract the .jar file from the zipped folder and run it on your SIEM server.</span></span>
    
3. <span data-ttu-id="98f20-178">Dopo aver eseguito il file, eseguire il comando riportato di seguito:</span><span class="sxs-lookup"><span data-stu-id="98f20-178">After running the file, run the following: command:</span></span><br/>
  ```
  java -jar mcas-siemagent-0.87.20-signed.jar [--logsDirectory DIRNAME] [--proxy ADDRESS[:PORT]] --token TOKEN
  ```
### <a name="important-notes"></a><span data-ttu-id="98f20-179">Note importanti</span><span class="sxs-lookup"><span data-stu-id="98f20-179">Important notes</span></span>

- <span data-ttu-id="98f20-180">Il nome del file può variare a seconda della versione dell'agente SIEM.</span><span class="sxs-lookup"><span data-stu-id="98f20-180">The file name may differ depending on the version of the SIEM agent.</span></span> 

- <span data-ttu-id="98f20-181">Si consiglia di eseguire il file JAR sul server SIEM durante l'installazione del server.</span><span class="sxs-lookup"><span data-stu-id="98f20-181">We recommend that you run the JAR file on your SIEM server during server setup.</span></span>

    - <span data-ttu-id="98f20-182">**Windows**: eseguire come attività pianificata, assicurandosi di configurare l'attività per l' **esecuzione se l'utente è connesso o meno** e si deseleziona l'opzione **Interrompi l'attività se viene eseguito più a lungo di** Option.</span><span class="sxs-lookup"><span data-stu-id="98f20-182">**Windows**: Run as a scheduled task, making sure to configure the task to **Run whether the user is logged on or not** and clear the **Stop the task if it runs longer than** option.</span></span>

    - <span data-ttu-id="98f20-183">**Linux**: aggiungere il comando Esegui con un **&** al `rc.local` file.</span><span class="sxs-lookup"><span data-stu-id="98f20-183">**Linux**: Add the run command with an **&** to the `rc.local` file.</span></span> <br/><span data-ttu-id="98f20-184">Esempio:</span><span class="sxs-lookup"><span data-stu-id="98f20-184">Example:</span></span><br/> 
    ```
    java -jar mcas-siemagent-0.87.20-signed.jar [--logsDirectory DIRNAME] [--proxy ADDRESS[:PORT]] --token TOKEN &
    ```

- <span data-ttu-id="98f20-185">I parametri tra parentesi quadre [] sono facoltativi e devono essere utilizzati solo se rilevanti.</span><span class="sxs-lookup"><span data-stu-id="98f20-185">Parameters in brackets [] are optional, and should be used only if relevant.</span></span> <span data-ttu-id="98f20-186">Utilizzare le seguenti variabili:</span><span class="sxs-lookup"><span data-stu-id="98f20-186">Use the following variables:</span></span>

    - <span data-ttu-id="98f20-187">**Dirname** è il percorso della directory che si desidera utilizzare per i log di debug degli agenti locali.</span><span class="sxs-lookup"><span data-stu-id="98f20-187">**DIRNAME** is the path to the directory you want to use for local agent debug logs.</span></span>

    - <span data-ttu-id="98f20-188">**Address [:P Ort]** è l'indirizzo del server proxy e la porta utilizzata dal server per la connessione a Internet.</span><span class="sxs-lookup"><span data-stu-id="98f20-188">**ADDRESS[:PORT]** is the proxy server address and port that the server uses to connect to the Internet.</span></span>

    - <span data-ttu-id="98f20-189">**Token** è il token dell'agente Siem copiato nella prima procedura.</span><span class="sxs-lookup"><span data-stu-id="98f20-189">**TOKEN** is the SIEM agent token you copied in the first procedure.</span></span>

    - <span data-ttu-id="98f20-190">Per ottenere assistenza, digitare `-h`.</span><span class="sxs-lookup"><span data-stu-id="98f20-190">To get help, type `-h`.</span></span> 
  
## <a name="step-3-validate-that-the-siem-agent-is-working"></a><span data-ttu-id="98f20-191">Passaggio 3: verificare che l'agente SIEM funzioni</span><span class="sxs-lookup"><span data-stu-id="98f20-191">Step 3: Validate that the SIEM agent is working</span></span>

1. <span data-ttu-id="98f20-192">Verificare che lo stato dell'agente SIEM nel portale di sicurezza delle app cloud di Office 365 non venga visualizzato come **errore di connessione** o disconnesso e che non vi siano notifiche di agente. \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="98f20-192">Make sure the status of the SIEM agent in the Office 365 Cloud App Security portal is not displayed as **Connection error** or **Disconnected** and that there are no agent notifications.</span></span><br/><span data-ttu-id="98f20-193">Ad esempio, qui è possibile vedere che il server SIEM è connesso:</span><span class="sxs-lookup"><span data-stu-id="98f20-193">For example, here we can see the SIEM server is connected:</span></span><br/><span data-ttu-id="98f20-194">![Server SIEM connesso](media/siem-connected.png)</span><span class="sxs-lookup"><span data-stu-id="98f20-194">![SIEM server connected](media/siem-connected.png)</span></span><br/><span data-ttu-id="98f20-195">E qui, è possibile vedere il server SIEM è disconnesso:</span><span class="sxs-lookup"><span data-stu-id="98f20-195">And here, we can see the SIEM server is disconnected:</span></span><br/><span data-ttu-id="98f20-196">![Server SIEM non connesso](media/siem-not-connected.png)</span><span class="sxs-lookup"><span data-stu-id="98f20-196">![SIEM server not connected](media/siem-not-connected.png)</span></span> 
  
2. <span data-ttu-id="98f20-197">Nel server syslog/SIEM, verificare che gli avvisi siano arrivati da Office 365 cloud app Security.</span><span class="sxs-lookup"><span data-stu-id="98f20-197">In your Syslog/SIEM server, make sure you see that alerts have arrived from Office 365 Cloud App Security.</span></span>
  
## <a name="what-the-logfiles-look-like"></a><span data-ttu-id="98f20-198">Aspetto dei file di log</span><span class="sxs-lookup"><span data-stu-id="98f20-198">What the logfiles look like</span></span>

<span data-ttu-id="98f20-199">Di seguito è riportato un esempio di file di log avvisi che potrebbe essere inviato a un server SIEM:</span><span class="sxs-lookup"><span data-stu-id="98f20-199">Here's an alerts logfile example that might be sent to a SIEM server:</span></span>

```
2017-07-15T20:42:30.531Z CEF:0|MCAS|SIEM_Agent|0.102.17|ALERT_CABINET_EVENT_MATCH_AUDIT|myPolicy|3|externalId=596a7e360c204203a335a3fb start=1500151350531 end=1500151350531 msg=Activity policy ''myPolicy'' was triggered by ''admin@box-contoso.com'' suser=admin@box-contoso.com destinationServiceName=Box cn1Label=riskScore cn1= cs1Label=portalURL cs1=https://cloud-app-security.com/#/alerts/596a7e360c204203a335a3fb cs2Label=uniqueServiceAppIds cs2=APPID_BOX cs3Label=relatedAudits cs3=1500151288183_acc891bf-33e1-424b-a021-0d4370789660 cs4Label=policyIDs cs4=59f0ab82f797fa0681e9b1c7

2017-07-16T09:36:26.550Z CEF:0|MCAS|SIEM_Agent|0.102.17|ALERT_CABINET_EVENT_MATCH_AUDIT|test-activity-policy|3|externalId=596b339b0c204203a33a51ae start=1500197786550 end=1500197786550 msg=Activity policy ''test-activity-policy'' was triggered by ''user@contoso.com'' suser=user@contoso.com destinationServiceName=Salesforce cn1Label=riskScore cn1= cs1Label=portalURL cs1=https://cloud-app-security.com/#/alerts/596b339b0c204203a33a51ae cs2Label=uniqueServiceAppIds cs2=APPID_SALESFORCE cs3Label=relatedAudits cs3=1500197720691_b7f6317c-b8de-476a-bc8f-dfa570e00349 cs4Label=policyIDs cs4=

2017-07-16T09:17:03.361Z CEF:0|MCAS|SIEM_Agent|0.102.17|ALERT_CABINET_EVENT_MATCH_AUDIT|test-activity-policy3|3|externalId=596b2fd70c204203a33a3eeb start=1500196623361 end=1500196623361 msg=Activity policy ''test-activity-policy3'' was triggered by ''admin@contoso.com'' suser=admin@contoso.com destinationServiceName=Office 365 cn1Label=riskScore cn1= cs1Label=portalURL cs1=https://cloud-app-security.com/#/alerts/596b2fd70c204203a33a3eeb cs2Label=uniqueServiceAppIds cs2=APPID_O365 cs3Label=relatedAudits cs3=1500196549157_a0e01f8a-e29a-43ae-8599-783c1c11597d cs4Label=policyIDs cs4=

2017-07-16T09:17:15.426Z CEF:0|MCAS|SIEM_Agent|0.102.17|ALERT_CABINET_EVENT_MATCH_AUDIT|test-activity-policy|3|externalId=596b2fd70c204203a33a3eec start=1500196635426 end=1500196635426 msg=Activity policy ''test-activity-policy'' was triggered by ''admin@contoso.com'' suser=admin@contoso.com destinationServiceName=Microsoft Office 365 admin center cn1Label=riskScore cn1= cs1Label=portalURL cs1=https://cloud-app-security.com/#/alerts/596b2fd70c204203a33a3eec cs2Label=uniqueServiceAppIds cs2=APPID_O365_PORTAL cs3Label=relatedAudits cs3=1500196557398_3e102b20-d9fa-4f66-b550-8c7a403bb4d8 cs4Label=policyIDs cs4=59f0ab35f797fa9811e9b1c7

2017-07-16T09:17:46.290Z CEF:0|MCAS|SIEM_Agent|0.102.17|ALERT_CABINET_EVENT_MATCH_AUDIT|test-activity-policy4|3|externalId=596b30200c204203a33a4765 start=1500196666290 end=1500196666290 msg=Activity policy ''test-activity-policy4'' was triggered by ''admin@contoso.com'' suser=admin@contoso.com destinationServiceName=Microsoft Exchange Online cn1Label=riskScore cn1= cs1Label=portalURL cs1=https://cloud-app-security.com/#/alerts/596b30200c204203a33a4765 cs2Label=uniqueServiceAppIds cs2=APPID_OUTLOOK cs3Label=relatedAudits cs3=1500196587034_a8673602-7e95-46d6-a1fe-c156c4709c5d cs4Label=policyIDs cs4=

2017-07-16T09:41:04.369Z CEF:0|MCAS|SIEM_Agent|0.102.17|ALERT_CABINET_EVENT_MATCH_AUDIT|test-activity-policy2|3|externalId=596b34b10c204203a33a5240 start=1500198064369 end=1500198064369 msg=Activity policy ''test-activity-policy2'' was triggered by ''user2@test15-adallom.com'' suser=user2@test15-adallom.com destinationServiceName=Google cn1Label=riskScore cn1= cs1Label=portalURL cs1=https://cloud-app-security.com/#/alerts/596b34b10c204203a33a5240 cs2Label=uniqueServiceAppIds cs2=APPID_33626 cs3Label=relatedAudits cs3=1500197996117_fd71f265-1e46-4f04-b372-2e32ec874cd3 cs4Label=policyIDs cs4=
```

<span data-ttu-id="98f20-200">Ed ecco un altro esempio, questa volta in formato CEF:</span><span class="sxs-lookup"><span data-stu-id="98f20-200">And here's another sample, this time in CEF format:</span></span>


|<span data-ttu-id="98f20-201">Nome del campo CEF</span><span class="sxs-lookup"><span data-stu-id="98f20-201">CEF field name</span></span>  | <span data-ttu-id="98f20-202">Descrizione</span><span class="sxs-lookup"><span data-stu-id="98f20-202">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="98f20-203">iniziare</span><span class="sxs-lookup"><span data-stu-id="98f20-203">start</span></span>     | <span data-ttu-id="98f20-204">timestamp di avviso</span><span class="sxs-lookup"><span data-stu-id="98f20-204">alert timestamp</span></span>        |
|<span data-ttu-id="98f20-205">End</span><span class="sxs-lookup"><span data-stu-id="98f20-205">end</span></span>     | <span data-ttu-id="98f20-206">timestamp di avviso</span><span class="sxs-lookup"><span data-stu-id="98f20-206">alert timestamp</span></span>        |
|<span data-ttu-id="98f20-207">RT</span><span class="sxs-lookup"><span data-stu-id="98f20-207">rt</span></span>     | <span data-ttu-id="98f20-208">timestamp di avviso</span><span class="sxs-lookup"><span data-stu-id="98f20-208">alert timestamp</span></span>        |
|<span data-ttu-id="98f20-209">msg</span><span class="sxs-lookup"><span data-stu-id="98f20-209">msg</span></span>     | <span data-ttu-id="98f20-210">Descrizione dell'avviso come mostrato nel portale di Office 365 cloud app Security</span><span class="sxs-lookup"><span data-stu-id="98f20-210">alert description as shown in the Office 365 Cloud App Security portal</span></span>        |
|<span data-ttu-id="98f20-211">sUser</span><span class="sxs-lookup"><span data-stu-id="98f20-211">suser</span></span>     | <span data-ttu-id="98f20-212">utente del soggetto di avviso</span><span class="sxs-lookup"><span data-stu-id="98f20-212">alert subject user</span></span>        |
|<span data-ttu-id="98f20-213">destinationServiceName</span><span class="sxs-lookup"><span data-stu-id="98f20-213">destinationServiceName</span></span>     | <span data-ttu-id="98f20-214">app di origine degli avvisi, ad esempio Office 365, SharePoint o OneDrive</span><span class="sxs-lookup"><span data-stu-id="98f20-214">alert originating app, such as Office 365, SharePoint, or OneDrive</span></span>        |
|<span data-ttu-id="98f20-215">csLabel</span><span class="sxs-lookup"><span data-stu-id="98f20-215">csLabel</span></span>     | <span data-ttu-id="98f20-216">Varia (le etichette hanno significati diversi).</span><span class="sxs-lookup"><span data-stu-id="98f20-216">Varies (labels have different meanings).</span></span> <span data-ttu-id="98f20-217">In genere, le etichette sono autoesplicative, ad esempio targetObjects.</span><span class="sxs-lookup"><span data-stu-id="98f20-217">Typically, labels are self-explanatory, like targetObjects.</span></span>        |
|<span data-ttu-id="98f20-218">cs</span><span class="sxs-lookup"><span data-stu-id="98f20-218">cs</span></span>     | <span data-ttu-id="98f20-219">Informazioni corrispondenti a un'etichetta, ad esempio l'utente di destinazione di un avviso secondo l'esempio di etichetta.</span><span class="sxs-lookup"><span data-stu-id="98f20-219">Information corresponding to a label (such as the target user of an alert as per the label example)</span></span>        |

## <a name="additional-tasks-as-needed"></a><span data-ttu-id="98f20-220">Altre attività (se necessario)</span><span class="sxs-lookup"><span data-stu-id="98f20-220">Additional tasks (as needed)</span></span>

<span data-ttu-id="98f20-221">Dopo aver configurato il server SIEM e averlo integrato con Office 365 cloud app Security, potrebbe essere necessario rigenerare un token, modificare un agente SIEM o eliminare un agente SIEM.</span><span class="sxs-lookup"><span data-stu-id="98f20-221">After you have configured your SIEM server and have integrated it with Office 365 Cloud App Security, you might need to regenerate a token, edit a SIEM agent, or delete a SIEM agent.</span></span> <span data-ttu-id="98f20-222">Nelle sezioni seguenti viene descritto come eseguire queste attività.</span><span class="sxs-lookup"><span data-stu-id="98f20-222">The following sections describe how to perform these tasks.</span></span>

### <a name="regenerate-a-token"></a><span data-ttu-id="98f20-223">Rigenerazione di un token</span><span class="sxs-lookup"><span data-stu-id="98f20-223">Regenerate a token</span></span>

<span data-ttu-id="98f20-224">Se si perde il token, è possibile rigenerarne uno.</span><span class="sxs-lookup"><span data-stu-id="98f20-224">If you lose your token, you can regenerate one.</span></span> 

1. <span data-ttu-id="98f20-225">In Office 365 Cloud App security[https://portal.cloudappsecurity.com](https://portal.cloudappsecurity.com)portal (), scegliere **Settings** > **security extensions**.</span><span class="sxs-lookup"><span data-stu-id="98f20-225">In the Office 365 Cloud App Security portal ([https://portal.cloudappsecurity.com](https://portal.cloudappsecurity.com)), choose **Settings** > **Security extensions**.</span></span>

2. <span data-ttu-id="98f20-226">Nella tabella individuare la riga per l'agente SIEM.</span><span class="sxs-lookup"><span data-stu-id="98f20-226">In the table, locate the row for the SIEM agent.</span></span> 

3. <span data-ttu-id="98f20-227">Fare clic sui puntini di ellisse e quindi scegliere **Rigenera token**.</span><span class="sxs-lookup"><span data-stu-id="98f20-227">Click the ellipses, and then choose **Regenerate token**.</span></span><br/><span data-ttu-id="98f20-228">![Rigenerare un token facendo clic sui puntini di sospensione per l'agente SIEM](media/04de368a-b88e-4a9c-a830-58025cb98db6.png)</span><span class="sxs-lookup"><span data-stu-id="98f20-228">![Regenerate a token by clicking the ellipsis for your SIEM agent](media/04de368a-b88e-4a9c-a830-58025cb98db6.png)</span></span>
  
### <a name="edit-a-siem-agent"></a><span data-ttu-id="98f20-229">Modificare un agente SIEM</span><span class="sxs-lookup"><span data-stu-id="98f20-229">Edit a SIEM agent</span></span>

1. <span data-ttu-id="98f20-230">In Office 365 Cloud App security[https://portal.cloudappsecurity.com](https://portal.cloudappsecurity.com)portal (), scegliere **Settings** > **security extensions**.</span><span class="sxs-lookup"><span data-stu-id="98f20-230">In the Office 365 Cloud App Security portal ([https://portal.cloudappsecurity.com](https://portal.cloudappsecurity.com)), choose **Settings** > **Security extensions**.</span></span>

2. <span data-ttu-id="98f20-231">Individuare la riga per l'agente SIEM.</span><span class="sxs-lookup"><span data-stu-id="98f20-231">Locate the row for the SIEM agent.</span></span> 

3. <span data-ttu-id="98f20-232">Fare clic sui puntini di ellisse e quindi scegliere **modifica**.</span><span class="sxs-lookup"><span data-stu-id="98f20-232">Click the ellipses, and then choose **Edit**.</span></span> <span data-ttu-id="98f20-233">Se si modifica l'agente SIEM, non è necessario rieseguire il file. jar; si aggiorna automaticamente.</span><span class="sxs-lookup"><span data-stu-id="98f20-233">(If you edit the SIEM agent, you do not need to re-run the .jar file; it updates automatically.)</span></span> <br/><span data-ttu-id="98f20-234">![Per modificare l'agente SIEM, scegliere i puntini di ellisse e quindi fare clic su modifica.](media/96d0b362-3e0c-4dff-b2b4-d7af5b1bfb91.png)</span><span class="sxs-lookup"><span data-stu-id="98f20-234">![To edit your SIEM agent, choose the ellipses, and then choose Edit.](media/96d0b362-3e0c-4dff-b2b4-d7af5b1bfb91.png)</span></span>
  
### <a name="delete-a-siem-agent"></a><span data-ttu-id="98f20-235">Eliminare un agente SIEM</span><span class="sxs-lookup"><span data-stu-id="98f20-235">Delete a SIEM agent</span></span>

1. <span data-ttu-id="98f20-236">In Office 365 Cloud App security[https://portal.cloudappsecurity.com](https://portal.cloudappsecurity.com)portal (), scegliere **Settings** > **security extensions**.</span><span class="sxs-lookup"><span data-stu-id="98f20-236">In the Office 365 Cloud App Security portal ([https://portal.cloudappsecurity.com](https://portal.cloudappsecurity.com)), choose **Settings** > **Security extensions**.</span></span>

2. <span data-ttu-id="98f20-237">Individuare la riga per l'agente SIEM.</span><span class="sxs-lookup"><span data-stu-id="98f20-237">Locate the row for the SIEM agent.</span></span> 

3. <span data-ttu-id="98f20-238">Fare clic sui puntini di ellisse e quindi scegliere **Elimina**.</span><span class="sxs-lookup"><span data-stu-id="98f20-238">Click the ellipses, and then choose **Delete**.</span></span><br/><span data-ttu-id="98f20-239">![Per eliminare un agente SIEM, scegliere i puntini di ellissi e quindi scegliere Elimina.](media/540b5bdf-5574-4ecc-a7b0-92a499a387d7.png)</span><span class="sxs-lookup"><span data-stu-id="98f20-239">![To delete a SIEM agent, choose the ellipses, and then choose Delete.](media/540b5bdf-5574-4ecc-a7b0-92a499a387d7.png)</span></span>

  
## <a name="next-steps"></a><span data-ttu-id="98f20-240">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="98f20-240">Next steps</span></span>

- [<span data-ttu-id="98f20-241">Attività di utilizzo dopo la distribuzione di Office 365 Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="98f20-241">Utilization activities after rolling out Office 365 Cloud App Security</span></span>](utilization-activities-for-ocas.md)
    
- [<span data-ttu-id="98f20-242">Esaminare e intervenire sugli avvisi</span><span class="sxs-lookup"><span data-stu-id="98f20-242">Review and take action on alerts</span></span>](review-office-365-cas-alerts.md)
    
- [<span data-ttu-id="98f20-243">Raggruppare gli indirizzi IP per semplificare la gestione</span><span class="sxs-lookup"><span data-stu-id="98f20-243">Group your IP addresses to simplify management</span></span>](group-your-ip-addresses-in-ocas.md)
    

