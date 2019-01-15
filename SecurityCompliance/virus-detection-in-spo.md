---
title: Rilevamento di virus in SharePoint Online
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 01/14/2019
ms.audience: Admin
ms.topic: reference
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- SPO160
- MOE150
- MET150
ms.assetid: e3c6df61-8513-499d-ad8e-8a91770bff63
description: Office 365 può proteggere l'ambiente da malware per l'individuazione dei virus nei file che gli utenti caricano con SharePoint Online. File di ricerca di virus dopo che vengono caricati. Se un file viene trovato un virus, una proprietà viene impostata in modo che gli utenti non possono scaricare o sincronizzare il file.
ms.openlocfilehash: ab02d2d4e82e9427ec6b512490f94ccc9c14b54e
ms.sourcegitcommit: 5ccc3dd0d1c087bffd3a8fc807d5d1750f046eeb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/14/2019
ms.locfileid: "28009592"
---
# <a name="virus-detection-in-sharepoint-online"></a>Rilevamento di virus in SharePoint Online

Office 365 può proteggere l'ambiente da malware per l'individuazione dei virus nei file che gli utenti caricano con SharePoint Online. File di ricerca di virus dopo che vengono caricati. Se un file viene trovato un virus, una proprietà viene impostata in modo che gli utenti non possono scaricare o sincronizzare il file.
  
> [!IMPORTANT]
> Tali funzionalità antivirus in SharePoint Online rappresentano un modo per contenere virus. Non non sono previsti come un singolo punto di sistema di difesa contro malware per l'ambiente. Microsoft incoraggia tutti i clienti di valutare e implementare protezione antimalware a diversi livelli e applicarlo procedure consigliate per la protezione dell'infrastruttura di enterprise. Per ulteriori informazioni sulle strategie e procedure consigliate, vedere [le procedure consigliate per Office 365](security-best-practices.md). 
  
## <a name="what-happens-when-an-infected-file-is-uploaded-to-sharepoint-online"></a>Cosa succede quando un file che contengono un virus caricato in SharePoint Online?

Office 365 utilizza un motore di rilevamento dei virus più comuni. Il modulo di gestione viene eseguito in modo asincrono in SharePoint Online e analizza i file dopo essere state caricate. Quando viene rilevato un file di contengono un virus, viene contrassegnata in modo che non possono essere scaricato nuovamente. In aprile 2018, viene rimosso il limite massimo 25 MB per file analizzati.
  
Ecco che cosa accade:
  
1. Un utente carica un file in SharePoint Online.
    
2. Il motore di rilevamento virus analizza i file.
    
3. Se viene rilevato un virus, il motore di virus imposta una proprietà per il file che indica che contiene.
    
## <a name="what-happens-when-a-user-tries-to-download-an-infected-file-by-using-the-browser"></a>Cosa succede quando un utente tenta di scaricare un file che contengono un virus utilizzando il browser?

Se un file contiene un virus, gli utenti non possono scaricare il file da SharePoint Online mediante l'utilizzo del browser.
  
Ecco che cosa accade:
  
1. L'utente apre un web browser e tenta di scaricare un file che contengono un virus da SharePoint Online.
    
2. L'utente ha un avviso indicante che è stato rilevato un virus. L'utente ha la possibilità di scaricare il file e tentare la pulizia mediante un software antivirus.

> [!NOTE]
> È possibile utilizzare il cmdlet Set-SPOTenant con il parametro **DisallowInfectedFileDownload** non consentire agli utenti di scaricare un file rilevato, anche nella finestra di avviso antivirus. Vedere [DisallowInfectedFileDownload] (https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant).
    
## <a name="what-happens-when-the-onedrive-sync-client-tries-to-sync-an-infected-file"></a>Cosa succede quando il client di sincronizzazione OneDrive tenta di sincronizzare un file che contengono un virus?

Se gli utenti sincronizzare i file con il nuovo client di sincronizzazione OneDrive (OneDrive.exe) o il precedente OneDrive for Business client di sincronizzazione (Groove.exe), se un file contiene un virus, il client di sincronizzazione non scaricarlo. Il client di sincronizzazione verrà visualizzata una notifica che il file non può essere sincronizzato.
  

