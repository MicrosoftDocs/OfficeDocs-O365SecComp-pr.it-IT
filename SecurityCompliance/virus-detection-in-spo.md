---
title: Rilevamento di virus in SharePoint Online
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 4/17/2018
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
ms.openlocfilehash: 22e983d35283ff96e1469fdf913e25b8d1d1c485
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/27/2018
ms.locfileid: "22531056"
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
    
2. L'utente ha un avviso indicante che è stato rilevato un virus e ha la possibilità di scaricare il file e tenta la pulizia mediante un software antivirus.
    
## <a name="what-happens-when-the-onedrive-sync-client-tries-to-sync-an-infected-file"></a>Cosa succede quando il client di sincronizzazione OneDrive tenta di sincronizzare un file che contengono un virus?

Se gli utenti sincronizzare i file con il nuovo client di sincronizzazione OneDrive (OneDrive.exe) o il precedente OneDrive for Business client di sincronizzazione (Groove.exe), se un file contiene un virus, il client di sincronizzazione non scaricarlo. Il client di sincronizzazione verrà visualizzata una notifica che il file non può essere sincronizzato.
  

