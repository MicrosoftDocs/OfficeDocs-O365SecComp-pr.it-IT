---
title: Proteggere le informazioni
ms.author: bcarter
author: brendacarter
manager: laurawi
ms.date: 4/26/2019
ms.audience: Admin
ms.topic: hub-page
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: a6ef28a4-2447-4b43-aae2-f5af6d53c68e
description: pagina di destinazione per la protezione delle informazioni
ms.openlocfilehash: 1c673c2417b399c57ca7ac7e5c5a7b7351de1edd
ms.sourcegitcommit: 696c1ed6b270be3f9da7395b49a7d8fec98e6db0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/29/2019
ms.locfileid: "33473120"
---
# <a name="protect-information"></a>Proteggere le informazioni

Microsoft 365 e Office 365 includono funzionalità che possono essere applicate a tipi specifici di dati per proteggere le informazioni. 


|**Funzionalità**|**Ulteriori informazioni**|
|:-----|:-----|
|[Etichette di riservatezza](sensitivity-labels.md) <br/> |Con le etichette di riservatezza è possibile classificare e proteggere i contenuti sensibili. Le opzioni di protezione includono etichette, filigrane e crittografia. Le etichette di riservatezza utilizzano Azure Information Protection. Se si utilizzano le etichette di Azure Information Protection, è consigliabile evitare di creare nuove etichette in altri centri di amministrazione finché non si è completata la migrazione. Vedere [Azure Information Protection Migration](https://docs.microsoft.com/en-us/azure/information-protection/configure-policy-migrate-labels). <br/> Le [etichette di conservazione](retention-policies.md) sono diverse dalle etichette di riservatezza. Le etichette di conservazione consentono di conservare o eliminare il contenuto in base ai criteri definiti. Queste organizzazioni di assistenza sono conformi alle normative industriali e ai criteri interni.|
|[Prevenzione della perdita di dati](data-loss-prevention-policies.md) DLP  <br/> |Con i criteri DLP, è possibile identificare, monitorare e proteggere automaticamente le informazioni riservate in Office 365. I criteri di prevenzione della perdita di dati possono utilizzare etichette di riservatezza e tipi di informazioni riservate per identificare informazioni riservate. <br/> |
|[Tipi di informazioni riservate](what-the-sensitive-information-types-look-for.md)  <br/> |DLP include numerosi tipi di informazioni riservate pronte per l'uso nei criteri DLP. I tipi di informazioni riservate definiscono in che modo il processo automatico riconosce tipi di informazioni specifiche quali numeri di servizi di integrità e numeri di carta di credito.   <br/> |
|[Crittografia dei messaggi di Office 365](ome.md) OME  <br/> |Con la crittografia dei messaggi di Office 365, l'organizzazione può inviare e ricevere messaggi di posta elettronica crittografati tra utenti all'interno e all'esterno dell'organizzazione. La crittografia dei messaggi di Office 365 è compatibile con Outlook.com, Yahoo!, Gmail e altri servizi di posta elettronica. La crittografia dei messaggi di posta elettronica consente di verificare che solo i destinatari previsti possano visualizzare il contenuto del messaggio.  <br/> |
|[Azure Information Protection](https://docs.microsoft.com/en-us/azure/information-protection/)<br/> |Se si utilizzano le etichette di riservatezza o la crittografia dei messaggi di Office, si sta già utilizzando Azure Information Protection. Se le etichette di Azure Information Protection non sono state ancora migrate a Office 365, continuare a gestire queste informazioni in Azure Information Protection.  <br/>Lo [scanner di Azure Information Protection](https://docs.microsoft.com/en-us/azure/information-protection/deploy-aip-scanner) può essere eseguito in locale per classificare e proteggere i file su Windows Server, le condivisioni di rete e i siti e le raccolte di SharePoint Server. Questo può essere un primo passo verso l'identificazione dei dati per la migrazione a Office 365.
|Protezione delle informazioni di Azure con soluzioni di BYOK o HYOK <br/> |Alcune organizzazioni hanno bisogno di un requisito aziendale o di conformità per mantenere il controllo di una chiave Encyption in locale o nel cloud. Non si tratta di una cosa comune. Per ulteriori informazioni, vedere [tenere la propria chiave (HYOK) per Azure Information Protection](https://docs.microsoft.com/en-us/azure/information-protection/configure-adrms-restrictions) e [portare la propria chiave (BYOK) per Azure Information Protection](https://docs.microsoft.com/en-us/azure/information-protection/byok-price-restrictions). <br/> |
    

