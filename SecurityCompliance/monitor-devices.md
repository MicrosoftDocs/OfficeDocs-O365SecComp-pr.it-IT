---
title: Monitorare i dispositivi in Sicurezza Microsoft 365
description: Descrive in che modo è possibile mantenere i dispositivi sicuri, aggiornati e individuare potenziali minacce nell'organizzazione
keywords: sicurezza, malware, Microsoft 365, M365, Centro sicurezza, monitoraggio, report, dispositivi
ms.prod: w10
ms.mktglfcycl: deploy
ms.localizationpriority: medium
ms.author: ellevin
author: levinec
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
search.appverid: met150
ms.openlocfilehash: 31d89b8bbcad98814ff33764bad24bffbbba4968
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "32263570"
---
# <a name="monitor-devices-in-microsoft-365-security"></a><span data-ttu-id="24627-104">Monitorare i dispositivi in Sicurezza Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="24627-104">Monitor devices in Microsoft 365 security</span></span>

<span data-ttu-id="24627-105">Mantenere i dispositivi sicuri, aggiornati e individuare potenziali minacce nel centro sicurezza Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="24627-105">Keep your devices secure, up-to-date, and spot potential threats in the Microsoft 365 security center.</span></span>

## <a name="view-device-alerts"></a><span data-ttu-id="24627-106">Visualizzare gli avvisi per i dispositivi</span><span class="sxs-lookup"><span data-stu-id="24627-106">View device alerts</span></span>

<span data-ttu-id="24627-107">Ottenere avvisi aggiornati sull'attività di violazione e altre minacce sui dispositivi da Windows Defender ATP (disponibile con una licenza E5).</span><span class="sxs-lookup"><span data-stu-id="24627-107">Get up-to-date alerts about breach activity and other threats on your devices from Windows Defender ATP (available with an E5 license).</span></span> <span data-ttu-id="24627-108">Microsoft 365 Security Center contiene diverse schede che consentono di monitorare efficacemente gli avvisi a un livello superiore, a seconda del flusso di lavoro preferito.</span><span class="sxs-lookup"><span data-stu-id="24627-108">Microsoft 365 security center has several cards that allow you to effectively monitor these alerts at a high-level, depending on your preferred workflow.</span></span>

### <a name="monitor-high-impact-alerts"></a><span data-ttu-id="24627-109">Monitorare gli avvisi ad impatto elevato</span><span class="sxs-lookup"><span data-stu-id="24627-109">Monitor high-impact alerts</span></span>

<span data-ttu-id="24627-110">Ogni avviso di Windows Defender ATP ha un livello di gravità corrispondente, alto, medio, basso o informativo, che indica il potenziale impatto della rete se non è presente.</span><span class="sxs-lookup"><span data-stu-id="24627-110">Each Windows Defender ATP alert has a corresponding severity—high, medium, low, or informational—that indicates its potential impact to your network if left unattended.</span></span>  

<span data-ttu-id="24627-111">Utilizzare la scheda **gravità avviso dispositivo** per concentrarsi in modo specifico sugli avvisi più gravi e potrebbe richiedere una risposta immediata.</span><span class="sxs-lookup"><span data-stu-id="24627-111">Use the **Device alert severity** card to focus specifically on alerts that are more severe and might require immediate response.</span></span> <span data-ttu-id="24627-112">Da questa scheda, è possibile visualizzare ulteriori informazioni su Windows Defender Security Center Portal.</span><span class="sxs-lookup"><span data-stu-id="24627-112">From this card, you can view more information on the Windows Defender Security Center portal.</span></span>

![Scheda di gravità avvisi dispositivo](./media/security-docs/device-alerts-severity.png)

### <a name="understand-sources-of-alerts"></a><span data-ttu-id="24627-114">Informazioni sulle origini degli avvisi</span><span class="sxs-lookup"><span data-stu-id="24627-114">Understand sources of alerts</span></span>

<span data-ttu-id="24627-115">Windows Defender ATP utilizza i dati provenienti da una vasta gamma di sensori di sicurezza e fonti di intelligence per generare avvisi.</span><span class="sxs-lookup"><span data-stu-id="24627-115">Windows Defender ATP leverages data from a broad range of security sensors and intelligence sources to generate alerts.</span></span> <span data-ttu-id="24627-116">Ad esempio, è possibile utilizzare le informazioni di rilevamento di Windows Defender Antivirus e antimalware di terze parti, nonché la propria Intelligence di minacce personalizzata fornita tramite l'API del servizio Web.</span><span class="sxs-lookup"><span data-stu-id="24627-116">For example, it can use detection information from Windows Defender Antivirus and third-party antimalware, as well as your own custom threat intelligence provided through the web service API.</span></span>

<span data-ttu-id="24627-117">La scheda fonti di **rilevamento avvisi dispositivo** Visualizza la distribuzione degli avvisi per origine.</span><span class="sxs-lookup"><span data-stu-id="24627-117">The **Device alert detection** sources card shows the distribution of alerts by source.</span></span> <span data-ttu-id="24627-118">Questa scheda può essere utile per monitorare le attività relative a determinate origini, in particolare le origini personalizzate.</span><span class="sxs-lookup"><span data-stu-id="24627-118">This card can help you track activity related to certain sources, particularly your custom sources.</span></span> <span data-ttu-id="24627-119">È inoltre possibile utilizzare questa pagina per concentrarsi sugli avvisi provenienti da sensori che non sono configurati per bloccare automaticamente le attività o i componenti dannosi.</span><span class="sxs-lookup"><span data-stu-id="24627-119">You can also use this to focus on alerts coming from sensors that are not configured to automatically block malicious activity or components.</span></span>

![Scheda fonti di rilevamento avvisi dispositivo](./media/security-docs/device-alert-detection-sources.png)

<span data-ttu-id="24627-121">Da questa scheda, è possibile visualizzare ulteriori informazioni su Windows Defender Security Center Portal.</span><span class="sxs-lookup"><span data-stu-id="24627-121">From this card, you can view more information on the Windows Defender Security Center portal.</span></span>

### <a name="understand-the-types-of-threats-that-trigger-alerts"></a><span data-ttu-id="24627-122">Comprendere i tipi di minacce che attivano gli avvisi</span><span class="sxs-lookup"><span data-stu-id="24627-122">Understand the types of threats that trigger alerts</span></span>

<span data-ttu-id="24627-123">Windows Defender ATP Ordina ogni avviso in una categoria che rappresenta una determinata fase della catena di attacco o un tipo di componente di minaccia.</span><span class="sxs-lookup"><span data-stu-id="24627-123">Windows Defender ATP sorts each alert into a category representing a certain stage in the attack chain or a type of threat component.</span></span> <span data-ttu-id="24627-124">Ad esempio, l'attività di minacce rilevata potrebbe essere categorizzata in "movimento laterale" per indicare che l'attività implicava un tentativo di raggiungere altri dispositivi sulla rete ed è probabile che si sia verificato dopo che i pirati informatici hanno acquisito un punto di appoggio iniziale.</span><span class="sxs-lookup"><span data-stu-id="24627-124">For example, detected threat activity might be categorized into “lateral movement” to indicate that the activity involved an attempt to reach other devices on the network and has likely occurred after attackers have gained an initial foothold.</span></span> <span data-ttu-id="24627-125">Una volta rilevato, un componente di minacce potrebbe essere classificato come "malware" o più specificamente come "ransomware", "furto di credenziali" o altri tipi di software dannoso o indesiderato.</span><span class="sxs-lookup"><span data-stu-id="24627-125">When detected, a threat component might either be classified broadly as “malware” or more specifically as “ransomware”, “credential stealing” or other types of malicious or unwanted software.</span></span>

<span data-ttu-id="24627-126">La scheda **categorie minacce dispositivo** Visualizza la distribuzione degli avvisi in queste categorie.</span><span class="sxs-lookup"><span data-stu-id="24627-126">The **Device threat categories** card shows the distribution of alerts into these categories.</span></span> <span data-ttu-id="24627-127">È possibile utilizzare queste informazioni per identificare le attività relative alle minacce, ad esempio i tentativi di furto di credenziali, che possono avere un impatto più significativo rispetto ai tentativi di social engineering.</span><span class="sxs-lookup"><span data-stu-id="24627-127">You can use this information to identify threat activity, such as attempts at credential theft, which can have more significant impact compared to attempts at social engineering, for example.</span></span> <span data-ttu-id="24627-128">È inoltre possibile utilizzare questa pagina per monitorare le minacce potenzialmente distruttive come ransomware.</span><span class="sxs-lookup"><span data-stu-id="24627-128">You can also use this to monitor for potentially destructive threats like ransomware.</span></span>

![Scheda categorie di minacce per dispositivi](./media/security-docs/device-threat-categories.png)

### <a name="monitor-active-alerts"></a><span data-ttu-id="24627-130">Monitorare gli avvisi attivi</span><span class="sxs-lookup"><span data-stu-id="24627-130">Monitor active alerts</span></span>

<span data-ttu-id="24627-131">La scheda **stato avviso dispositivo** indica il numero di avvisi che non sono stati risolti e che potrebbero richiedere attenzione.</span><span class="sxs-lookup"><span data-stu-id="24627-131">The **Device alert status** card indicates the number of alerts that have not been resolved and might require attention.</span></span> <span data-ttu-id="24627-132">Da questa scheda, è possibile visualizzare ulteriori informazioni su Windows Defender Security Center Portal.</span><span class="sxs-lookup"><span data-stu-id="24627-132">From this card, you can view more information on the Windows Defender Security Center portal.</span></span>

![Scheda stato avviso dispositivo](./media/security-docs/device-alert-status.png)

### <a name="monitor-classification-of-resolved-alerts"></a><span data-ttu-id="24627-134">Monitorare la classificazione degli avvisi risolti</span><span class="sxs-lookup"><span data-stu-id="24627-134">Monitor classification of resolved alerts</span></span>

<span data-ttu-id="24627-135">Durante la risoluzione di un avviso di Windows Defender ATP, il personale di sicurezza può specificare se un avviso è stato verificato come:</span><span class="sxs-lookup"><span data-stu-id="24627-135">When resolving a Window Defender ATP alert, your security staff can specify whether an alert has been verified as:</span></span>

* <span data-ttu-id="24627-136">Un avviso vero che identifica le attività di violazione effettive o i componenti di minaccia</span><span class="sxs-lookup"><span data-stu-id="24627-136">A true alert that identifies actual breach activity or threat components</span></span>
* <span data-ttu-id="24627-137">Un falso avviso che ha rilevato erroneamente attività normale</span><span class="sxs-lookup"><span data-stu-id="24627-137">A false alert that has incorrectly detected normal activity</span></span>

<span data-ttu-id="24627-138">La scheda di **classificazione avviso dispositivo** indica se gli avvisi risolti sono stati classificati come avvisi veri o falsi.</span><span class="sxs-lookup"><span data-stu-id="24627-138">The **Device alert classification** card shows whether your resolved alerts have been classified as true or false alerts.</span></span> <span data-ttu-id="24627-139">Da questa scheda, è possibile visualizzare ulteriori informazioni su Windows Defender Security Center Portal.</span><span class="sxs-lookup"><span data-stu-id="24627-139">From this card, you can view more information on the Windows Defender Security Center portal.</span></span>

<span data-ttu-id="24627-140">Nota: in alcuni casi, le informazioni di classificazione non sono disponibili per determinati avvisi.</span><span class="sxs-lookup"><span data-stu-id="24627-140">Note: In some cases, classification information is unavailable for certain alerts.</span></span>

![Scheda di classificazione degli avvisi dei dispositivi](./media/security-docs/device-alert-classification.png)

### <a name="monitor-determination-of-resolved-alerts"></a><span data-ttu-id="24627-142">Monitorare la determinazione degli avvisi risolti</span><span class="sxs-lookup"><span data-stu-id="24627-142">Monitor determination of resolved alerts</span></span>

<span data-ttu-id="24627-143">Oltre a classificare se un avviso è vero o falso durante la risoluzione, il personale della sicurezza può fornire una determinazione, indicando il tipo di attività normale o dannosa individuata durante la convalida dell'avviso.</span><span class="sxs-lookup"><span data-stu-id="24627-143">In addition to classifying whether an alert is true or false during resolution, your security staff can provide a determination, indicating the type of normal or malicious activity that was found while validating the alert.</span></span>

<span data-ttu-id="24627-144">La scheda di **determinazione dell'avviso del dispositivo** Visualizza la determinazione fornita per ogni avviso, in particolare:</span><span class="sxs-lookup"><span data-stu-id="24627-144">The **Device alert determination** card shows the determination provided for each alert, specifically:</span></span>

* <span data-ttu-id="24627-145">**Apt** – Advanced Persistent Threat, che indica che l'attività rilevata o il componente di minaccia è parte di una sofisticata violazione progettata per ottenere un punto di appoggio nella rete in questione</span><span class="sxs-lookup"><span data-stu-id="24627-145">**APT** – advanced persistent threat, indicating that the detected activity or threat component is part of a sophisticated breach designed to gain a foothold in the affected network</span></span>  
* <span data-ttu-id="24627-146">**Malware** : file o codice dannoso</span><span class="sxs-lookup"><span data-stu-id="24627-146">**Malware** – malicious file or code</span></span>
* <span data-ttu-id="24627-147">**Personale di sicurezza** – attività normale eseguita dal personale della sicurezza</span><span class="sxs-lookup"><span data-stu-id="24627-147">**Security personnel** – normal activity performed by security staff</span></span>
* <span data-ttu-id="24627-148">**Test di sicurezza** – attività o componenti studiati per simulare le minacce effettive e per attivare i sensori di sicurezza e generare avvisi</span><span class="sxs-lookup"><span data-stu-id="24627-148">**Security testing** – activity or components designed to simulate actual threats and expected to trigger security sensors and generate alerts</span></span>
* <span data-ttu-id="24627-149">**Software** indesiderato – app e altri software che non sono considerati dannosi, ma violano in altro modo i criteri o gli standard di utilizzo accettabili</span><span class="sxs-lookup"><span data-stu-id="24627-149">**Unwanted software** – apps and other software that are not considered malicious, but otherwise violate policy or acceptable use standards</span></span>
* <span data-ttu-id="24627-150">**Altri** – qualsiasi altra determinazione che non rientra nei tipi forniti</span><span class="sxs-lookup"><span data-stu-id="24627-150">**Others** – any other determination that does not fall under the provided types</span></span>

<span data-ttu-id="24627-151">Da questa scheda, è possibile visualizzare altre informazioni in Windows Defender Security Center.</span><span class="sxs-lookup"><span data-stu-id="24627-151">From this card, you can view more information in Windows Defender security center.</span></span>

![Scheda di determinazione dell'avviso del dispositivo](./media/security-docs/device-alert-determination.png)

### <a name="understand-which-devices-are-at-risk"></a><span data-ttu-id="24627-153">Comprendere quali dispositivi sono a rischio</span><span class="sxs-lookup"><span data-stu-id="24627-153">Understand which devices are at risk</span></span>

<span data-ttu-id="24627-154">La **protezione del dispositivo** Visualizza il livello di rischio per i dispositivi.</span><span class="sxs-lookup"><span data-stu-id="24627-154">**Device protection** shows the risk level for devices.</span></span> <span data-ttu-id="24627-155">Il livello di rischio si basa su fattori quali il tipo e la gravità degli avvisi nel dispositivo.</span><span class="sxs-lookup"><span data-stu-id="24627-155">The risk level is based on factors such as the type and severity of alerts on the device.</span></span>

![Scheda di protezione del dispositivo](./media/security-docs/device-protection.png)

## <a name="monitor-and-report-status-of-intune-managed-devices"></a><span data-ttu-id="24627-157">Monitorare e segnalare lo stato dei dispositivi gestiti da Intune</span><span class="sxs-lookup"><span data-stu-id="24627-157">Monitor and report status of Intune-managed devices</span></span>

<span data-ttu-id="24627-158">Il monitoraggio e i report seguenti contengono dati provenienti da dispositivi registrati in Intune.</span><span class="sxs-lookup"><span data-stu-id="24627-158">The following monitoring and reports contain data from devices enrolled in Intune.</span></span> <span data-ttu-id="24627-159">I dati dei dispositivi non registrati non sono inclusi.</span><span class="sxs-lookup"><span data-stu-id="24627-159">Data from unenrolled devices is not included.</span></span> <span data-ttu-id="24627-160">Solo gli amministratori globali possono visualizzare queste schede.</span><span class="sxs-lookup"><span data-stu-id="24627-160">Only Global Administrators can view these cards.</span></span>

<span data-ttu-id="24627-161">I dati dei dispositivi registrati di Intune includono:</span><span class="sxs-lookup"><span data-stu-id="24627-161">Intune enrolled device data includes:</span></span>

* <span data-ttu-id="24627-162">Conformità del dispositivo</span><span class="sxs-lookup"><span data-stu-id="24627-162">Device compliance</span></span>
* <span data-ttu-id="24627-163">Dispositivi con malware attivo</span><span class="sxs-lookup"><span data-stu-id="24627-163">Devices with active malware</span></span>
* <span data-ttu-id="24627-164">Tipi di malware nei dispositivi</span><span class="sxs-lookup"><span data-stu-id="24627-164">Types of malware on devices</span></span>
* <span data-ttu-id="24627-165">Malware nei dispositivi</span><span class="sxs-lookup"><span data-stu-id="24627-165">Malware on devices</span></span>
* <span data-ttu-id="24627-166">Dispositivi con rilevamenti di malware</span><span class="sxs-lookup"><span data-stu-id="24627-166">Devices with malware detections</span></span>
* <span data-ttu-id="24627-167">Utenti con rilevamenti di malware</span><span class="sxs-lookup"><span data-stu-id="24627-167">Users with malware detections</span></span>

### <a name="monitor-device-compliance"></a><span data-ttu-id="24627-168">Monitorare la conformità del dispositivo</span><span class="sxs-lookup"><span data-stu-id="24627-168">Monitor device compliance</span></span>

<span data-ttu-id="24627-169">La **conformità del dispositivo** indica il numero di dispositivi registrati in Intune conformi ai criteri di configurazione.</span><span class="sxs-lookup"><span data-stu-id="24627-169">**Device compliance** shows how many devices that are enrolled in Intune comply with configuration policies.</span></span>

![Scheda conformità dispositivo](./media/security-docs/device-compliance.png)

### <a name="discover-devices-with-malware-detections"></a><span data-ttu-id="24627-171">Individuare i dispositivi con rilevamenti di malware</span><span class="sxs-lookup"><span data-stu-id="24627-171">Discover devices with malware detections</span></span>

<span data-ttu-id="24627-172">I rilevamenti di **malware per dispositivi** forniscono il numero di dispositivi registrati di Intune con malware che non sono stati completamente risolti a causa di azioni in sospeso, ovvero un riavvio, un'analisi completa o azioni utente manuali oppure se l'operazione di correzione non è stata completata correttamente.</span><span class="sxs-lookup"><span data-stu-id="24627-172">**Device malware detections** provides the number of Intune enrolled devices with malware that have not been fully resolved due to pending actions—a restart, a full scan or manual user actions—or if the remediation action did not complete successfully.</span></span>

![Scheda rilevamenti malware dispositivo](./media/security-docs/device-malware-detections.png)

### <a name="understand-the-types-of-malware-detected"></a><span data-ttu-id="24627-174">Informazioni sui tipi di malware rilevati</span><span class="sxs-lookup"><span data-stu-id="24627-174">Understand the types of malware detected</span></span>

<span data-ttu-id="24627-175">I **tipi di malware nei dispositivi** mostrano diversi tipi di malware che sono stati rilevati nei dispositivi registrati in Intune.</span><span class="sxs-lookup"><span data-stu-id="24627-175">**Types of malware on devices** shows different kinds of malware that have been detected on devices enrolled in Intune.</span></span> <span data-ttu-id="24627-176">È possibile esaminare ogni tipo in Microsoft 365 Security Center.</span><span class="sxs-lookup"><span data-stu-id="24627-176">You can investigate each type in Microsoft 365 security center.</span></span>

![Tipi di malware sulla scheda dispositivi](./media/security-docs/types-of-malware-on-devices.png)

### <a name="understand-the-specific-malware-detected-on-your-devices"></a><span data-ttu-id="24627-178">Comprendere il malware specifico rilevato nei dispositivi</span><span class="sxs-lookup"><span data-stu-id="24627-178">Understand the specific malware detected on your devices</span></span>

<span data-ttu-id="24627-179">**Malware nei dispositivi** fornisce un elenco di malware specifici rilevati nei dispositivi.</span><span class="sxs-lookup"><span data-stu-id="24627-179">**Malware on devices** provides a list of the specific malware detected on your devices.</span></span>

![Scheda malware su dispositivi](./media/security-docs/malware-on-devices.png)

### <a name="understand-which-devices-have-the-most-malware"></a><span data-ttu-id="24627-181">Informazioni sui dispositivi con la maggior parte dei malware</span><span class="sxs-lookup"><span data-stu-id="24627-181">Understand which devices have the most malware</span></span>

<span data-ttu-id="24627-182">I **dispositivi con rilevamenti di malware** mostrano quali dispositivi presentano la maggior parte dei rilevamenti di malware.</span><span class="sxs-lookup"><span data-stu-id="24627-182">**Devices with malware detections** shows which devices have the most malware detections.</span></span> <span data-ttu-id="24627-183">In Microsoft 365 Security Center è possibile verificare se il malware è attivo, chi usa il dispositivo e lo stato di gestione in Intune.</span><span class="sxs-lookup"><span data-stu-id="24627-183">In Microsoft 365 security center, you can investigate whether malware is active, who uses the device, and its management status in Intune.</span></span>

![Scheda dispositivi con rilevamento malware](./media/security-docs/devices-with-malware-detections.png)

### <a name="understand-which-users-have-devices-with-the-most-malware"></a><span data-ttu-id="24627-185">Comprendere quali utenti dispongono di dispositivi con la maggior parte dei malware</span><span class="sxs-lookup"><span data-stu-id="24627-185">Understand which users have devices with the most malware</span></span>

<span data-ttu-id="24627-186">**Gli utenti con rilevamenti di malware** visualizzano gli utenti con dispositivi con la maggior parte dei rilevamenti di malware.</span><span class="sxs-lookup"><span data-stu-id="24627-186">**Users with malware detections** shows users with devices that had the most malware detections.</span></span> <span data-ttu-id="24627-187">In Microsoft 365 Security Center, è possibile visualizzare il numero di dispositivi assegnati a ciascun utente e ulteriori informazioni su ogni dispositivo e sul tipo di malware.</span><span class="sxs-lookup"><span data-stu-id="24627-187">In Microsoft 365 security center, you can see how many devices are assigned to each user and more information about each device and the type of malware.</span></span>

![Utenti con scheda di rilevamento antimalware](./media/security-docs/users-with-malware-detections.png)

## <a name="monitor-and-manage-asr-rule-deployment-and-detections"></a><span data-ttu-id="24627-189">Monitorare e gestire la distribuzione e i rilevamenti delle regole ASR</span><span class="sxs-lookup"><span data-stu-id="24627-189">Monitor and manage ASR rule deployment and detections</span></span>

<span data-ttu-id="24627-190">[Le regole di riduzione dell'attacco superficiale (ASR, Attack Surface Reduction)](https://docs.microsoft.com/en-us/windows/security/threat-protection/windows-defender-exploit-guard/attack-surface-reduction-exploit-guard) consentono di prevenire azioni e app che vengono in genere utilizzate da malware in cerca di exploit per infettare macchine</span><span class="sxs-lookup"><span data-stu-id="24627-190">[Attack Surface Reduction (ASR) rules](https://docs.microsoft.com/en-us/windows/security/threat-protection/windows-defender-exploit-guard/attack-surface-reduction-exploit-guard) help prevent actions and apps that are typically used by exploit-seeking malware to infect machines.</span></span> <span data-ttu-id="24627-191">Queste regole controllano il modo in cui è possibile eseguire i file eseguibili.</span><span class="sxs-lookup"><span data-stu-id="24627-191">These rules control when and how executables can run.</span></span> <span data-ttu-id="24627-192">Ad esempio, è possibile impedire a JavaScript o VBScript di avviare un file eseguibile scaricato, bloccare le chiamate API Win32 dalle macro di Office o bloccare i processi che vengono eseguiti da unità USB.</span><span class="sxs-lookup"><span data-stu-id="24627-192">For example, you can prevent JavaScript or VBScript from launching a downloaded executable, block Win32 API calls from Office macros, or block processes that run from USB drives.</span></span>

![Scheda riduzioni superficie attacco](./media/security-docs/attack-surface-reduction-rules.png)

<span data-ttu-id="24627-194">La scheda **regole di riduzione della superficie di attacco** fornisce una panoramica della distribuzione delle regole tra i dispositivi.</span><span class="sxs-lookup"><span data-stu-id="24627-194">The **Attack surface reduction rules** card provides an overview of the deployment of rules across your devices.</span></span>

<span data-ttu-id="24627-195">Nella barra superiore della scheda viene visualizzato il numero totale di dispositivi presenti nelle modalità di distribuzione seguenti:</span><span class="sxs-lookup"><span data-stu-id="24627-195">The top bar on the card shows the total number of devices that are in the following deployment modes:</span></span>

* <span data-ttu-id="24627-196">**Modalità di blocco** – dispositivi con almeno una regola configurata per bloccare l'attività rilevata</span><span class="sxs-lookup"><span data-stu-id="24627-196">**Block mode** – devices with at least one rule configured to block detected activity</span></span>
* <span data-ttu-id="24627-197">**Modalità di controllo** : i dispositivi con nessuna regola impostata per bloccare l'attività rilevata, ma hanno almeno un set di regole per il controllo dell'attività rilevata</span><span class="sxs-lookup"><span data-stu-id="24627-197">**Audit mode** – devices with no rules set to block detected activity, but has at least one rule set to audit detected activity</span></span>  
* <span data-ttu-id="24627-198">**Disattivato** : i dispositivi con tutte le regole ASR sono disattivati</span><span class="sxs-lookup"><span data-stu-id="24627-198">**Off** – devices with all ASR rules turned off</span></span>

<span data-ttu-id="24627-199">Nella parte inferiore della scheda sono riportate le impostazioni per regola tra i dispositivi.</span><span class="sxs-lookup"><span data-stu-id="24627-199">The lower part of this card shows settings by rule across your devices.</span></span> <span data-ttu-id="24627-200">Ogni barra indica il numero di dispositivi che sono impostati per bloccare o controllare il rilevamento oppure la regola è stata completamente disattivata.</span><span class="sxs-lookup"><span data-stu-id="24627-200">Each bar indicates the number of devices that are set to block or audit detection or have the rule completely turned off.</span></span>

### <a name="view-asr-detections"></a><span data-ttu-id="24627-201">Visualizzazione dei rilevamenti ASR</span><span class="sxs-lookup"><span data-stu-id="24627-201">View ASR detections</span></span>

<span data-ttu-id="24627-202">Per visualizzare informazioni dettagliate sui rilevamenti delle regole di ASR nella rete, selezionare **Visualizza** rilevamenti nella scheda **regole di riduzione della superficie di attacco** .</span><span class="sxs-lookup"><span data-stu-id="24627-202">To view detailed information about ASR rule detections in your network, select **View detections** on the **Attack surface reduction rules** card.</span></span> <span data-ttu-id="24627-203">Verrà \*\*\*\* aperta la scheda rilevamenti nella pagina rapporto dettagliato.</span><span class="sxs-lookup"><span data-stu-id="24627-203">The **Detections** tab in the detailed report page will open.</span></span>

![Scheda riLevamenti](./media/security-docs/detections-tab.png)

<span data-ttu-id="24627-205">Il grafico nella parte superiore della pagina Visualizza rilevamenti nel tempo di rilevamenti di sovrapposizione che sono stati bloccati o controllati.</span><span class="sxs-lookup"><span data-stu-id="24627-205">The chart at the top of the page shows detections over time stacking detections that were either blocked or audited.</span></span> <span data-ttu-id="24627-206">La tabella in basso elenca i rilevamenti più recenti.</span><span class="sxs-lookup"><span data-stu-id="24627-206">The table at the bottom lists the most recent detections.</span></span> <span data-ttu-id="24627-207">Utilizzare le informazioni seguenti nella tabella per comprendere la natura dei rilevamenti:</span><span class="sxs-lookup"><span data-stu-id="24627-207">Use the following information on the table to understand the nature of the detections:</span></span>

* <span data-ttu-id="24627-208">**File rilevato** : il file, in genere uno script o un documento, il cui contenuto ha attivato l'attività di attacco sospetta</span><span class="sxs-lookup"><span data-stu-id="24627-208">**Detected file** – the file, typically a script or a document, whose contents triggered the suspected attack activity</span></span>
* <span data-ttu-id="24627-209">**Rule** – nome che descrive le attività di attacco la regola è progettata per essere intercettata.</span><span class="sxs-lookup"><span data-stu-id="24627-209">**Rule** – name describing the attack activities the rule is designed to catch.</span></span> <span data-ttu-id="24627-210">Leggere le regole ASR esistenti</span><span class="sxs-lookup"><span data-stu-id="24627-210">Read about existing ASR rules</span></span>
* <span data-ttu-id="24627-211">**App di origine** : l'applicazione che ha caricato o eseguito contenuto che attiva l'attività di attacco sospetta.</span><span class="sxs-lookup"><span data-stu-id="24627-211">**Source app** – the application that loaded or executed content triggering the suspected attack activity.</span></span> <span data-ttu-id="24627-212">Potrebbe trattarsi di un'applicazione legittima, ad esempio il Web browser, un'applicazione di Office o uno strumento di sistema come PowerShell.</span><span class="sxs-lookup"><span data-stu-id="24627-212">This could be a legitimate application, such as web browser, an Office application, or a system tool like PowerShell</span></span>
* <span data-ttu-id="24627-213">**Publisher** : il fornitore che ha rilasciato l'app di origine</span><span class="sxs-lookup"><span data-stu-id="24627-213">**Publisher** – the vendor that released the source app</span></span>

### <a name="review-device-asr-rule-settings"></a><span data-ttu-id="24627-214">Esaminare le impostazioni della regola di ASR del dispositivo</span><span class="sxs-lookup"><span data-stu-id="24627-214">Review device ASR rule settings</span></span>

<span data-ttu-id="24627-215">Nella pagina rapporto **regole di riduzione della superficie di attacco** passare alla scheda **configurazione** per esaminare le impostazioni delle regole per i singoli dispositivi.</span><span class="sxs-lookup"><span data-stu-id="24627-215">In the **Attack surface reduction rules** report page, go to the **Configuration** tab to review rule settings for individual devices.</span></span> <span data-ttu-id="24627-216">Selezionare un dispositivo per ottenere informazioni dettagliate sul fatto che ogni regola sia in modalità di blocco, modalità di controllo o disattivata completamente.</span><span class="sxs-lookup"><span data-stu-id="24627-216">Select a device to get detailed information about whether each rule is in block mode, audit mode, or turned off entirely.</span></span>

![Scheda configurazione](./media/security-docs/configuration-tab.png)

<span data-ttu-id="24627-218">Microsoft Intune offre funzionalità di gestione per le regole di ASR.</span><span class="sxs-lookup"><span data-stu-id="24627-218">Microsoft Intune provides management functionality for your ASR rules.</span></span> <span data-ttu-id="24627-219">Se si desidera aggiornare le impostazioni, selezionare **Get Started** in **Configure Devices** nella scheda per aprire Gestione dispositivi su Intune.</span><span class="sxs-lookup"><span data-stu-id="24627-219">If you want to update your settings, select **Get started** under **Configure devices** in the tab to open device management on Intune.</span></span>

### <a name="exclude-files-from-asr-rules"></a><span data-ttu-id="24627-220">Escludi file dalle regole di ASR</span><span class="sxs-lookup"><span data-stu-id="24627-220">Exclude files from ASR rules</span></span>

<span data-ttu-id="24627-221">Escludendo i file dai rilevamenti, è possibile impedire rilevamenti falsi positivi indesiderati e distribuire in modo più sicuro le regole di riduzione delle superfici di attacco in modalità di blocco.</span><span class="sxs-lookup"><span data-stu-id="24627-221">By excluding files from detections, you can prevent unwanted false positive detections and more confidently deploy attack surface reduction rules in block mode.</span></span>

<span data-ttu-id="24627-222">Mentre le esclusioni dei file per le regole di riduzione della superficie di attacco vengono gestite su Microsoft Intune, Microsoft 365 Security Center fornisce uno strumento di analisi che consente di comprendere i file che stanno attivando i rilevamenti.</span><span class="sxs-lookup"><span data-stu-id="24627-222">While file exclusions for attack surface reduction rules are managed on Microsoft Intune, Microsoft 365 security center provides an analysis tool to help you understand the files that are triggering detections.</span></span> <span data-ttu-id="24627-223">Consente inoltre di raccogliere i nomi dei file che si desidera escludere.</span><span class="sxs-lookup"><span data-stu-id="24627-223">It also helps collect the names of the files you might want to exclude.</span></span>

<span data-ttu-id="24627-224">Per avviare l'analisi di rilevamenti e la raccolta di file per l'esclusione, passare alla scheda **Aggiungi esclusioni** nella pagina rapporto **regole di riduzione delle superfici attacco** .</span><span class="sxs-lookup"><span data-stu-id="24627-224">To start analyzing detections and collecting files for exclusion, go to the **Add exclusions** tab in the **Attack surface reduction rules** report page.</span></span>

![Scheda Aggiungi esclusioni](./media/security-docs/add-exclusions-tab.png)

<span data-ttu-id="24627-226">Nella tabella sono elencati tutti i nomi di file rilevati dalle regole di riduzione della superficie di attacco.</span><span class="sxs-lookup"><span data-stu-id="24627-226">The table lists all the file names detected by your attack surface reduction rules.</span></span> <span data-ttu-id="24627-227">Dopo aver selezionato un file o più file, è possibile esaminare l'impatto relativo all'aggiunta di tali file alle eccezioni:</span><span class="sxs-lookup"><span data-stu-id="24627-227">Once you select a file or multiple files, you can review the impact of adding those files to your exceptions:</span></span>

* <span data-ttu-id="24627-228">Riduzione del numero totale di rilevamenti</span><span class="sxs-lookup"><span data-stu-id="24627-228">The reduction in the total number of detections</span></span>
* <span data-ttu-id="24627-229">Riduzione del numero totale di dispositivi coinvolti nei rilevamenti</span><span class="sxs-lookup"><span data-stu-id="24627-229">The reduction in the total number of devices affected by the detections</span></span>

<span data-ttu-id="24627-230">Per ottenere un elenco dei file selezionati con i percorsi completi per l'esclusione, selezionare **Ottieni percorsi di esclusione**.</span><span class="sxs-lookup"><span data-stu-id="24627-230">To get a list of the selected files with their full paths for exclusion, select **Get exclusion paths**.</span></span>

<span data-ttu-id="24627-231">Per ulteriori informazioni sulle esclusioni e sulle istruzioni dettagliate su come aggiungerle, vedere [risolvere i problemi relativi alle regole di riduzione della superficie di attacco](https://docs.microsoft.com/en-us/windows/security/threat-protection/windows-defender-exploit-guard/troubleshoot-asr).</span><span class="sxs-lookup"><span data-stu-id="24627-231">For more information about exclusions and detailed instructions about how to add them, read [troubleshoot attack surface reduction rules](https://docs.microsoft.com/en-us/windows/security/threat-protection/windows-defender-exploit-guard/troubleshoot-asr).</span></span>
