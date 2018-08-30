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
# <a name="group-your-ip-addresses-to-simplify-management-in-office-365-cloud-app-security"></a>Raggruppare gli indirizzi IP per semplificare la gestione in Office 365 Cloud App Security
  
|Valutazione * *\>**|Pianificazione * *\>**|Distribuzione * *\>**|Utilizzo * * *|
|:-----|:-----|:-----|:-----|
|[Avviare la valutazione](office-365-cas-overview.md) <br/> |[Iniziare a pianificare](get-ready-for-office-365-cas.md) <br/> |Si è seguito!  <br/> [Passaggi successivi](#next-steps) <br/> |[Avviare utilizzando](utilization-activities-for-ocas.md) <br/> |
   
Per identificare facilmente i set di indirizzi IP che verrà utilizzato nella sicurezza di App per Office 365 Cloud, ad esempio gli indirizzi IP ufficio fisico, è possibile impostare i gruppi di intervalli di indirizzi IP. Definizione di questi intervalli consente tag e classificarli e quindi è possibile utilizzare i tag e categorie per personalizzare l'attività i registri e degli avvisi vengono visualizzate e analizzare.
  
Ogni gruppo di intervalli IP può essere contrassegnata con i nomi dei tag che si sceglie e quindi i tag possono essere suddivise basato su un elenco predefinito di categorie IP (ad esempio Corporate, amministrativi, Risky e VPN). Gli indirizzi IPv4 e IPv6 sono supportati.
  
> [!NOTE]
> È necessario essere un amministratore globale o sicurezza per eseguire le procedure descritte in questo articolo. Per ulteriori informazioni, vedere [autorizzazioni in Office 365 Security &amp; centro conformità](permissions-in-the-security-and-compliance-center.md). 
  
## <a name="to-set-up-an-ip-address-range-in-office-365-cloud-app-security"></a>Per impostare un intervallo di indirizzi IP in sicurezza App Cloud di Office 365

1. Un amministratore globale o un amministratore di protezione, passare a [https://protection.office.com](https://protection.office.com) e accedere utilizzando l'account di lavoro o della scuola. (Si passa alla sicurezza &amp; centro conformità.) 
    
2. In sicurezza &amp; centro conformità, selezionare **avvisi** \> **Gestione avanzata degli avvisi**.
    
3. Scegliere **Vai a Office 365 Cloud App protezione**.
    
    ![In sicurezza &amp; centro conformità, selezionare Gestisci avvisi avanzate per accedere alla sicurezza di Office 365 Cloud App](media/958632d4-03e3-4ade-8e22-d5509db6fca7.png)
  
4. Nell'angolo in basso a destra della pagina, fare clic su **Impostazioni** \> **intervalli di indirizzi IP**.
    
    ![In Office 365 Cloud App sicurezza scegliere le impostazioni di accedere alle impostazioni di sistema e dei dati](media/f6c48ee3-39b4-4b5a-8252-b6493b7bcd3d.png)
  
5. Fare clic sul pulsante nuovo, che è simile a un segno di addizione ( **+**).
    
6. Nella finestra **nuovo indirizzo IP** , specificare i valori seguenti: 
    
|**Campo o un elenco**|**cosa fare**|
|:-----|:-----|
|**Nome** <br/> |Utilizzare questo campo per gestire le impostazioni e l'intervallo di indirizzi IP. (Si potrà essere visualizzato questo valore nei registri delle attività.)  <br/> |
|**Intervalli di indirizzi IP** <br/> |Specificare un intervallo, utilizzando la notazione prefisso di rete (noto anche come notazione CIDR). Ad esempio, 192.168.1.0/27 include l'intervallo di valori 192.168.1.0 tramite 192.168.1.31 (compresi).  <br/> |
|**Percorso** e il **provider di servizi Internet registrati** <br/> |Consente di specificare il percorso e il Provider di servizi Internet (ISP) per l'intervallo di indirizzi IP. Questo sostituisce i campi pubblici definiti per gli indirizzi che è utile per i casi, ad esempio un indirizzo IP è che è considerato pubblicamente irlandese ma è effettivamente negli Stati Uniti  <br/> |
|**Tag** <br/> |Utilizzare i tag per denominare i gruppi di indirizzi IP. (A differenza di campo nome verranno visualizzati i tag di registri attività.) Digitare una parola o frase che si desidera utilizzare per un tag. È possibile aggiungere tutti i tag desiderati per ogni intervallo di indirizzi IP. E se è già stato configurato un tag e si desidera aggiungere questo intervallo di indirizzi IP, selezionare dall'elenco dei tag corrente vengono visualizzate quando si inizia a digitare.  <br/> |
|**Categoria** <br/> | Assegnare le categorie per il tag per facilitare la riconosce le attività che provengono da determinati indirizzi IP. Scegliere una delle opzioni seguenti:<br/> **Amministrazione** Tutti gli indirizzi IP del gruppo di amministratori.  <br/> **Provider cloud** L'indirizzo IP del proxy nel cloud.  <br/> **Aziendale** Tutti gli IP indirizzi nella rete interna, le filiali e gli indirizzi di roaming Wi-Fi.  <br/> **Rischioso** Tutti gli indirizzi IP che si considera rischioso, ad esempio gli indirizzi IP sospetti è siano indicato in precedenza, gli indirizzi IP nelle reti concorrenti e così via. Per impostazione predefinita, le categorie rischiose include due tag IP: **proxy anonimo** e **TR** <br/> **VPN** Tutti gli indirizzi IP che utilizzano i dipendenti remoti.  <br/> |
   
7. Fare clic su **Salva**.
    
Dopo aver impostato le intervalli di indirizzi IP, tenere presente che solo futuri eventi sono interessati da queste modifiche.
  
## <a name="next-steps"></a>Passaggi successivi

- [Avvisi e i criteri di attività](activity-policies-and-alerts.md)
    
- [Criteri di rilevamento anomalia](anomaly-detection-policies-in-ocas.md)
    
- [Integrare il server SIEM](integrate-your-siem-server-with-office-365-cas.md)
    
- [Esaminare e intervenire sugli avvisi in Office 365 Cloud App Security](review-office-365-cas-alerts.md)
    

