---
title: Raggruppare gli indirizzi IP per semplificare la gestione in Office 365 Cloud App Security
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 2/22/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: b5e1471c-1ad6-4bc5-9e75-ce791aee283c
description: Per identificare facilmente i set di indirizzi IP che verrà utilizzato nella sicurezza di App per Office 365 Cloud, ad esempio gli indirizzi IP ufficio fisico, è possibile impostare i gruppi di intervalli di indirizzi IP.
ms.openlocfilehash: 76cb9625a46d1f5eceaab696de5dcbb72f4d2b47
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/27/2018
ms.locfileid: "22530221"
---
# <a name="group-your-ip-addresses-to-simplify-management-in-office-365-cloud-app-security"></a><span data-ttu-id="99428-103">Raggruppare gli indirizzi IP per semplificare la gestione in Office 365 Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="99428-103">Group your IP addresses to simplify management in Office 365 Cloud App Security</span></span>
  
|<span data-ttu-id="99428-104">Valutazione * *\>**</span><span class="sxs-lookup"><span data-stu-id="99428-104">****Evaluation** \>**</span></span>|<span data-ttu-id="99428-105">Pianificazione * *\>**</span><span class="sxs-lookup"><span data-stu-id="99428-105">****Planning** \>**</span></span>|<span data-ttu-id="99428-106">Distribuzione * *\>**</span><span class="sxs-lookup"><span data-stu-id="99428-106">****Deployment** \>**</span></span>|<span data-ttu-id="99428-107">Utilizzo \* \* \*</span><span class="sxs-lookup"><span data-stu-id="99428-107">****Utilization****</span></span>|
|:-----|:-----|:-----|:-----|
|[<span data-ttu-id="99428-108">Avviare la valutazione</span><span class="sxs-lookup"><span data-stu-id="99428-108">Start evaluating</span></span>](office-365-cas-overview.md) <br/> |[<span data-ttu-id="99428-109">Iniziare a pianificare</span><span class="sxs-lookup"><span data-stu-id="99428-109">Start planning</span></span>](get-ready-for-office-365-cas.md) <br/> |<span data-ttu-id="99428-110">Si è seguito!</span><span class="sxs-lookup"><span data-stu-id="99428-110">You are here!</span></span>  <br/> [<span data-ttu-id="99428-111">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="99428-111">Next steps</span></span>](#next-steps) <br/> |[<span data-ttu-id="99428-112">Avviare utilizzando</span><span class="sxs-lookup"><span data-stu-id="99428-112">Start utilizing</span></span>](utilization-activities-for-ocas.md) <br/> |
   
<span data-ttu-id="99428-p101">Per identificare facilmente i set di indirizzi IP che verrà utilizzato nella sicurezza di App per Office 365 Cloud, ad esempio gli indirizzi IP ufficio fisico, è possibile impostare i gruppi di intervalli di indirizzi IP. Definizione di questi intervalli consente tag e classificarli e quindi è possibile utilizzare i tag e categorie per personalizzare l'attività i registri e degli avvisi vengono visualizzate e analizzare.</span><span class="sxs-lookup"><span data-stu-id="99428-p101">To easily identify sets of IP addresses that you'll use in Office 365 Cloud App Security, such as your physical office IP addresses, you can set up groups of IP address ranges. Defining these ranges lets you tag and categorize them, and then you can use tags and categories to customize how your activity logs and alerts are displayed and investigated.</span></span>
  
<span data-ttu-id="99428-p102">Ogni gruppo di intervalli IP può essere contrassegnata con i nomi dei tag che si sceglie e quindi i tag possono essere suddivise basato su un elenco predefinito di categorie IP (ad esempio Corporate, amministrativi, Risky e VPN). Gli indirizzi IPv4 e IPv6 sono supportati.</span><span class="sxs-lookup"><span data-stu-id="99428-p102">Each group of IP ranges can be tagged with tag names that you choose, and then the tags can be categorized based on a default list of IP categories (such as Corporate, Administrative, Risky, and VPN). Both IPv4 and IPv6 addresses are supported.</span></span>
  
> [!NOTE]
> <span data-ttu-id="99428-p103">È necessario essere un amministratore globale o sicurezza per eseguire le procedure descritte in questo articolo. Per ulteriori informazioni, vedere [autorizzazioni in Office 365 Security &amp; centro conformità](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="99428-p103">You must be a global administrator or security administrator to perform the procedures in this article. To learn more, see [Permissions in the Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span> 
  
## <a name="to-set-up-an-ip-address-range-in-office-365-cloud-app-security"></a><span data-ttu-id="99428-119">Per impostare un intervallo di indirizzi IP in sicurezza App Cloud di Office 365</span><span class="sxs-lookup"><span data-stu-id="99428-119">To set up an IP address range in Office 365 Cloud App Security</span></span>

1. <span data-ttu-id="99428-p104">Un amministratore globale o un amministratore di protezione, passare a [https://protection.office.com](https://protection.office.com) e accedere utilizzando l'account di lavoro o della scuola. (Si passa alla sicurezza &amp; centro conformità.)</span><span class="sxs-lookup"><span data-stu-id="99428-p104">As a global administrator or security administrator, go to [https://protection.office.com](https://protection.office.com) and sign in using your work or school account. (This takes you to the Security &amp; Compliance Center.)</span></span> 
    
2. <span data-ttu-id="99428-122">In sicurezza &amp; centro conformità, selezionare **avvisi** \> **Gestione avanzata degli avvisi**.</span><span class="sxs-lookup"><span data-stu-id="99428-122">In the Security &amp; Compliance Center, choose **Alerts** \> **Manage advanced alerts**.</span></span>
    
3. <span data-ttu-id="99428-123">Scegliere **Vai a Office 365 Cloud App protezione**.</span><span class="sxs-lookup"><span data-stu-id="99428-123">Choose **Go to Office 365 Cloud App Security**.</span></span>
    
    ![In sicurezza &amp; centro conformità, selezionare Gestisci avvisi avanzate per accedere alla sicurezza di Office 365 Cloud App](media/958632d4-03e3-4ade-8e22-d5509db6fca7.png)
  
4. <span data-ttu-id="99428-125">Nell'angolo in basso a destra della pagina, fare clic su **Impostazioni** \> **intervalli di indirizzi IP**.</span><span class="sxs-lookup"><span data-stu-id="99428-125">On the upper right of the page, click **Settings** \> **IP address ranges**.</span></span>
    
    ![In Office 365 Cloud App sicurezza scegliere le impostazioni di accedere alle impostazioni di sistema e dei dati](media/f6c48ee3-39b4-4b5a-8252-b6493b7bcd3d.png)
  
5. <span data-ttu-id="99428-127">Fare clic sul pulsante nuovo, che è simile a un segno di addizione ( **+**).</span><span class="sxs-lookup"><span data-stu-id="99428-127">Click the new button, which resembles a plus sign ( **+**).</span></span>
    
6. <span data-ttu-id="99428-128">Nella finestra **nuovo indirizzo IP** , specificare i valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="99428-128">In the **New IP address range** window, specify the following values:</span></span> 
    
|<span data-ttu-id="99428-129">**Campo o un elenco**</span><span class="sxs-lookup"><span data-stu-id="99428-129">**Field or list**</span></span>|<span data-ttu-id="99428-130">**cosa fare**</span><span class="sxs-lookup"><span data-stu-id="99428-130">**What to do**</span></span>|
|:-----|:-----|
|<span data-ttu-id="99428-131">**Nome**</span><span class="sxs-lookup"><span data-stu-id="99428-131">**Name**</span></span> <br/> |<span data-ttu-id="99428-p105">Utilizzare questo campo per gestire le impostazioni e l'intervallo di indirizzi IP. (Si potrà essere visualizzato questo valore nei registri delle attività.)</span><span class="sxs-lookup"><span data-stu-id="99428-p105">Use this field to manage your IP address range and settings. (You won't see this value in activities logs.)</span></span>  <br/> |
|<span data-ttu-id="99428-134">**Intervalli di indirizzi IP**</span><span class="sxs-lookup"><span data-stu-id="99428-134">**IP address ranges**</span></span> <br/> |<span data-ttu-id="99428-p106">Specificare un intervallo, utilizzando la notazione prefisso di rete (noto anche come notazione CIDR). Ad esempio, 192.168.1.0/27 include l'intervallo di valori 192.168.1.0 tramite 192.168.1.31 (compresi).</span><span class="sxs-lookup"><span data-stu-id="99428-p106">Specify a range, using network prefix notation (also known as CIDR notation). For example, 192.168.1.0/27 includes the range of values 192.168.1.0 through 192.168.1.31 (inclusive).</span></span>  <br/> |
|<span data-ttu-id="99428-137">**Percorso** e il **provider di servizi Internet registrati**</span><span class="sxs-lookup"><span data-stu-id="99428-137">**Location** and **Registered ISP**</span></span> <br/> |<span data-ttu-id="99428-p107">Consente di specificare il percorso e il Provider di servizi Internet (ISP) per l'intervallo di indirizzi IP. Questo sostituisce i campi pubblici definiti per gli indirizzi che è utile per i casi, ad esempio un indirizzo IP è che è considerato pubblicamente irlandese ma è effettivamente negli Stati Uniti</span><span class="sxs-lookup"><span data-stu-id="99428-p107">Specify the location and Internet Service Provider (ISP) for the IP address range. This overrides the public fields defined for the addresses, which is helpful for cases, such as an IP address is that is considered publicly to be in Ireland but is actually in the U.S.</span></span>  <br/> |
|<span data-ttu-id="99428-140">**Tag**</span><span class="sxs-lookup"><span data-stu-id="99428-140">**Tags**</span></span> <br/> |<span data-ttu-id="99428-p108">Utilizzare i tag per denominare i gruppi di indirizzi IP. (A differenza di campo nome verranno visualizzati i tag di registri attività.) Digitare una parola o frase che si desidera utilizzare per un tag. È possibile aggiungere tutti i tag desiderati per ogni intervallo di indirizzi IP. E se è già stato configurato un tag e si desidera aggiungere questo intervallo di indirizzi IP, selezionare dall'elenco dei tag corrente vengono visualizzate quando si inizia a digitare.</span><span class="sxs-lookup"><span data-stu-id="99428-p108">Use tags to name your groups of IP addresses. (Unlike the Name field, you will see Tags in activity logs.) Type a word or phrase that you want to use for a tag. You can add as many tags as you like for each IP address range. And if you've already set up a tag and you want to add this IP address range to it, choose it from the list of current tags that appear as you start typing.</span></span>  <br/> |
|<span data-ttu-id="99428-145">**Categoria**</span><span class="sxs-lookup"><span data-stu-id="99428-145">**Category**</span></span> <br/> | <span data-ttu-id="99428-p109">Assegnare le categorie per il tag per facilitare la riconosce le attività che provengono da determinati indirizzi IP. Scegliere una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="99428-p109">Assign categories to your tags to make it easier to recognize activities that come from certain IP addresses. Choose from the following options:  </span></span><br/> <span data-ttu-id="99428-148">**Amministrazione** Tutti gli indirizzi IP del gruppo di amministratori.</span><span class="sxs-lookup"><span data-stu-id="99428-148">**Administrative** All of the IP addresses of your admins.</span></span>  <br/> <span data-ttu-id="99428-149">**Provider cloud** L'indirizzo IP del proxy nel cloud.</span><span class="sxs-lookup"><span data-stu-id="99428-149">**Cloud provider** The IP address of your proxy in the cloud.</span></span>  <br/> <span data-ttu-id="99428-150">**Aziendale** Tutti gli IP indirizzi nella rete interna, le filiali e gli indirizzi di roaming Wi-Fi.</span><span class="sxs-lookup"><span data-stu-id="99428-150">**Corporate** All of the IP addresses in your internal network, your branch offices, and your Wi-Fi roaming addresses.</span></span>  <br/> <span data-ttu-id="99428-p110">**Rischioso** Tutti gli indirizzi IP che si considera rischioso, ad esempio gli indirizzi IP sospetti è siano indicato in precedenza, gli indirizzi IP nelle reti concorrenti e così via. Per impostazione predefinita, le categorie rischiose include due tag IP: **proxy anonimo** e **TR**</span><span class="sxs-lookup"><span data-stu-id="99428-p110">**Risky** Any IP addresses that you consider to be risky, such as suspicious IP addresses you've seen in the past, IP addresses in your competitors' networks, and so on. By default, the Risky categories includes two IP tags: **Anonymous proxy** and **Tor**</span></span> <br/> <span data-ttu-id="99428-153">**VPN** Tutti gli indirizzi IP che utilizzano i dipendenti remoti.</span><span class="sxs-lookup"><span data-stu-id="99428-153">**VPN** Any IP addresses that your remote workers use.</span></span>  <br/> |
   
7. <span data-ttu-id="99428-154">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="99428-154">Choose **Save**.</span></span>
    
<span data-ttu-id="99428-155">Dopo aver impostato le intervalli di indirizzi IP, tenere presente che solo futuri eventi sono interessati da queste modifiche.</span><span class="sxs-lookup"><span data-stu-id="99428-155">After you set up your IP address ranges, keep in mind that only future events are affected by these changes.</span></span>
  
## <a name="next-steps"></a><span data-ttu-id="99428-156">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="99428-156">Next steps</span></span>

- [<span data-ttu-id="99428-157">Avvisi e i criteri di attività</span><span class="sxs-lookup"><span data-stu-id="99428-157">Activity policies and alerts</span></span>](activity-policies-and-alerts.md)
    
- [<span data-ttu-id="99428-158">Criteri di rilevamento anomalia</span><span class="sxs-lookup"><span data-stu-id="99428-158">Anomaly detection policies</span></span>](anomaly-detection-policies-in-ocas.md)
    
- [<span data-ttu-id="99428-159">Integrare il server SIEM</span><span class="sxs-lookup"><span data-stu-id="99428-159">Integrate your SIEM server</span></span>](integrate-your-siem-server-with-office-365-cas.md)
    
- [<span data-ttu-id="99428-160">Esaminare e intervenire sugli avvisi in Office 365 Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="99428-160">Review and take action on alerts in Office 365 Cloud App Security</span></span>](review-office-365-cas-alerts.md)
    

