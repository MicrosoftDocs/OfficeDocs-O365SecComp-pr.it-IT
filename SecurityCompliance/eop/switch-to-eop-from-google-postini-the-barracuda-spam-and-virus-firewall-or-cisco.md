---
title: Passaggio a EOP da Google Postini, Barracuda Spam e Virus Firewall o Cisco IronPort
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 12/9/2016
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
ms.assetid: 81b75194-3b04-48da-8b81-951afbabedde
description: Lo scopo di questo argomento è quello di aiutare l'utente a comprendere il processo per passare a Exchange Online Protection (EOP) da un'applicazione per l'igiene della posta elettronica locale o un servizio di protezione basato su cloud, nonché di fornire risorse per iniziare.
ms.openlocfilehash: a1fa7b63dfc1e6eb193d458545722c4b5331bc48
ms.sourcegitcommit: 48fa456981b5c52ab8aeace173c8366b9f36723b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/28/2019
ms.locfileid: "30340757"
---
# <a name="switch-to-eop-from-google-postini-the-barracuda-spam-and-virus-firewall-or-cisco-ironport"></a>Passaggio a EOP da Google Postini, Barracuda Spam e Virus Firewall o Cisco IronPort

 Lo scopo di questo argomento è quello di aiutare l'utente a comprendere il processo per passare a Exchange Online Protection (EOP) da un'applicazione per l'igiene della posta elettronica locale o un servizio di protezione basato su cloud, nonché di fornire risorse per iniziare. Esistono diverse soluzioni per il filtro da posta indesiderata, ma il processo per il passaggio a EOP nella maggior parte dei casi è analogo.
  
Se non si conosce EOP e si desidera avere una panoramica sulle relative funzionalità prima di decidere di effettuare il passaggio, è possibile iniziare da [Panoramica su Exchange Online Protection](exchange-online-protection-overview.md) su TechNet. 
  
Prima di effettuare il passaggio a EOP, è importante considerare se ospitare le cassette postali protette da EOP nel cloud, con Exchange Online, in locale o in uno scenario ibrido. Ibrido significa che alcune cassette postali sono locali e altre sono ospitate su Exchange Online. Ciascuno di questi scenari di hosting: cloud, locale, ibrido è possibile. Tuttavia la procedura di impostazione può variare. Di seguito sono riportate alcune considerazioni che faciliteranno l'utente nella scelta della distribuzione appropriata:
  
- **Protezione EOP con cassette postali locali** Questo scenario è appropriato se si desidera utilizzare un'infrastruttura di hosting di posta esistente oppure se i requisiti aziendali impongono di mantenere le cassette postali in locale e si desidera una protezione EOP della posta elettronica basata su cloud. [Passare a EOP autonomo](#BKMK_SwitchStandalone.md) descrive lo scenario in maggiore dettaglio. 
    
- **Protezione EOP con cassette postali di Exchange Online** Questo scenario è appropriato se si desidera una protezione EOP e tutte le cassette postali sono ospitate nel cloud. Può facilitare la riduzione della complessità, poiché non è necessario mantenere i server di messaggistica in locale. [Passaggio a Exchange Online](switch-to-eop-from-google-postini-the-barracuda-spam-and-virus-firewall-or-cisco.md#BKMK_SwitchEXO) descrive questo scenario. 
    
- **Protezione EOP con cassette postali ibride** Consente di avere cassette postali sul cloud, tranne alcune per specifici utenti che restano locali. Scegliere questo scenario se si desidera che alcune cassette postali siano locali e altre siano ospitate su cloud con Exchange Online. [Passare a una soluzione ibrida](#BKMK_SwitchHybrid.md) descrive questo scenario. 
    
## <a name="switch-to-eop-standalone"></a>Passare a EOP autonomo
<a name="BKMK_SwitchStandalone"> </a>

Se attualmente le cassette postali sono ospitate in locale e si utilizza un'applicazione di protezione locale o un servizio di protezione della messaggistica cloud, è possibile passare a EOP per utilizzare disponibilità e funzionalità di protezione. Per impostare EOP in uno scenario autonomo, in cui le cassette postali sono ospitate in locale e utilizzano EOP per la protezione della posta elettronica, seguire la procedura indicata in [Installazione del servizio EOP](set-up-your-eop-service.md). Nell'argomento viene descritta la procedura per impostare la protezione EOP, che include l'accesso, l'aggiunta del proprio dominio e l'impostazione del flusso di posta con i connettori.
  
## <a name="switch-to-exchange-online"></a>Passaggio a Exchange Online
<a name="BKMK_SwitchEXO"> </a>

Se si dispone di cassette postali locali protette da un'applicazione locale è possibile passare alle cassette postali basate su cloud di Exchange Online e alla protezione EOP per sfruttare le funzionalità di protezione e messaggistica basata su cloud di Office 365. Per iniziare, accedere a Office 365 e aggiungere il proprio dominio. Questo scenario non richiede di impostare connettori, poiché non esistono routing alle cassette postali locali. Iniziare dalla [pagina di accesso di Office 365](https://www.microsoft.com/en-us/office365/online-software.aspx). ([Guida introduttiva a Office 365](https://go.microsoft.com/fwlink/p/?LinkId=275407) fornisce le risorse per familiarizzare con le funzionalità.) 
  
Durante il processo di impostazione di Office 365 verranno creati utenti di cassette postali basate su cloud.
  
## <a name="switch-to-a-hybrid-solution"></a>Passare a una soluzione ibrida
<a name="BKMK_SwitchHybrid"> </a>

È possibile spostare solamente una parte delle cassette postali nel cloud in base a requisiti aziendali o considerazioni normative. Quando viene distribuito uno scenario ibrido, è possibile spostare le cassette postali nel cloud come stabilito dai requisiti aziendali. La migrazione a uno scenario ibrido con protezione EOP risulta più complicata rispetto alla migrazione a uno scenario completamente cloud. Tuttavia Microsoft mette a disposizione dell'utente una vasta gamma di risorse e un'assistenza completa affinché lo spostamento allo scenario ibrido avvenga nel modo più semplice possibile.
  
Se si prende in considerazione una distribuzione ibrida, il migliore punto di partenza è [Exchange Server 2013 Hybrid Deployments](http://technet.microsoft.com/library/59e32000-4fcf-417f-a491-f1d8f9aeef9b.aspx). Inoltre, esistono alcuni metodi per indirizzare la posta a uno scenario ibrido che è importante comprendere. [Transport Routing in Exchange 2013 Hybrid Deployments](http://technet.microsoft.com/library/36c2cea3-2e2f-40ac-88bd-7e1b6bd27828.aspx) illustra ciascuno di questi metodi, in modo che sia possibile scegliere lo scenario di routing più adatto in base ai requisiti aziendali. 
  
## <a name="migration-planning"></a>Pianificazione della migrazione
<a name="sectionSection3"> </a>

Se si decide di passare a EOP, assicurarsi di prestare particolare attenzione alle seguenti aree:
  
- **Regole di filtro personalizzate** Se si dispone di un filtro personalizzato o di regole aziendali per la cattura di posta indesiderata specifica, è consigliabile provare EOP con le impostazioni predefinite per un periodo, prima di eseguire la migrazione delle regole. EOP offre protezione da posta indesiderata a livello aziendale con le impostazioni predefinite, potrebbe risultare che non è necessario eseguire la migrazione di alcune delle regole a EOP. Naturalmente, se si dispone di regole sul posto che applicano criteri aziendali personalizzati specifici, è possibile crearli. [Le regole del flusso di posta (regole di trasporto) in Exchange Online Protection](mail-flow-rules-transport-rules-0.md) sono disponibili istruzioni dettagliate per la creazione di regole del flusso di posta in EOP. 
    
- Elenchi di indirizzi IP consentiti **e di indirizzi IP bloccati** Se si dispone di elenchi di indirizzi consentiti per utente e di blocco, è possibile copiare gli elenchi in EOP come parte del processo di configurazione. Per ulteriori informazioni sugli elenchi di indirizzi IP consentiti e sugli elenchi di indirizzi IP bloccati, vedere [Configure the Connection Filter Policy](../configure-the-connection-filter-policy.md).
    
- **Comunicazione protetta** Se un partner richiede la messaggistica crittografata, si consiglia di configurarla nell'interfaccia di amministrazione di Exchange. Per configurare questo scenario, vedere [Create connectors for a secure mail channel using transport layer security (TLS)](http://technet.microsoft.com/library/1ce4d6a4-41ba-4d1e-9ca9-e826252c1041.aspx).
    
> [!TIP]
> Durante il passaggio da un'applicazione locale a EOP, è possibile lasciare che l'applicazione o server locale esegua le verifiche relative alle regole aziendali. Ad esempio, se l'applicazione esegue il filtraggio personalizzato sulla posta in uscita e si desidera procedere in questo modo, è possibile configurare EOP per inviare la posta direttamente all'applicazione per un ulteriore filtraggio prima che venga instradata in Internet. [Exchange Online Protection Connectors - Outbound Smart Host Scenario](http://technet.microsoft.com/library/431b3f02-4efd-4bd3-94e7-eecd03f8ef5e.aspx) mostra come impostare il flusso di posta in questo caso. 
  

