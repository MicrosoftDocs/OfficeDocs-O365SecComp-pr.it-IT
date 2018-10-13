---
title: Informazioni sul file dannosi rilevato in SharePoint, OneDrive o Teams Microsoft
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 5ed8abf1-c0e9-4e5b-a5b7-2059cea50b61
description: Informazioni su dove è possibile per visualizzare informazioni sui file dannosi rilevato in SharePoint, OneDrive o team e come eseguire l'azione necessaria tali file.
ms.openlocfilehash: 37cd721c9ec2608ddcd74f9ae1ed6991b5f0cea7
ms.sourcegitcommit: e0c6f99d5514d8da8a70d9bd3616d1a1c0851254
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/13/2018
ms.locfileid: "25552384"
---
# <a name="view-information-about-malicious-files-detected-in-sharepoint-onedrive-or-microsoft-teams"></a>Informazioni sul file dannosi rilevato in SharePoint, OneDrive o Teams Microsoft

[Degli strumenti di analisi di Office 365 per SharePoint, OneDrive e team Microsoft che](atp-for-spo-odb-and-teams.md) consente di proteggere l'organizzazione da file dannosi nelle raccolte documenti e siti del team. Quando un file dannoso viene rilevato, tale file è bloccato in modo che non possono aprire, copiare, spostare o condividerlo fino a quando non vengono intraprese azioni ulteriormente dal team di protezione dell'organizzazione. In questo articolo per informazioni su come visualizzare informazioni sui file rilevati e le azioni da intraprendere. 

Per eseguire le attività descritte in questo articolo, è necessario disporre di volte necessario [autorizzazioni assegnate in Office 365 Security &amp; centro conformità](permissions-in-the-security-and-compliance-center.md). 
  
## <a name="view-reports-with-information-about-detected-files"></a>Visualizzare i report con informazioni sul file rilevati

Per visualizzare lo stato e informazioni dettagliate sui file che sono stati rilevati da strumenti di analisi di Office 365, è possibile utilizzare la relazione sullo stato di protezione di rischio.
  
1. In Office 365 Security &amp; centro conformità, selezionare **rapporti** \> **Dashboard** \> **Lo stato di protezione di rischio**.
    
2. Nell'angolo superiore destro del report, scegliere **Visualizza dettagli tabella**.
    
3. Visualizzare l'elenco dei file che sono stati rilevati nel report.
    
4. Selezionare un elemento nell'elenco per visualizzare informazioni dettagliate, incluse le azioni intraprese, il nome del file, il percorso del file e altro ancora.
    
5. Fare clic sulla scheda **Analisi avanzate** per visualizzare informazioni, ad esempio osservato comportamento e analisi dei dettagli. 
  
## <a name="view-and-take-action-on-files-in-quarantine"></a>Visualizza ed esegue azioni sui file in quarantena

1. In Office 365 Security &amp; centro conformità, scegliere **gestione rischio** \> **revisione** \> **quarantena**.
    
2. Nell'angolo superiore sinistro, modificare il filtro di **posta elettronica** al **contenuto**.
    
3. Selezionare un elemento nell'elenco per visualizzare informazioni dettagliate, incluso l'URL del file.
    
4. Scegliere un'azione disponibile.
    
  - Scegliere **versione &amp; report** per sbloccare il file. 
    
    Selezionare **Invia segnalazione a Microsoft** per segnalare il file come falso positivo a Microsoft. 
    
  - Scegliere **Download file** per analizzare ulteriormente il file. 
    
  - Scegliere **Elimina** per rimuovere il file dall'elenco di elementi in quarantena. Se si sceglie questa opzione, è necessario eliminare anche il file dalla libreria rispettivo in SharePoint Online, OneDrive per Business o Microsoft Teams. Questa opzione non sbloccare un file vengano aperti o condivisa. 
    
5. Scegliere **Chiudi** per chiudere i dettagli per l'elemento selezionato. 
  
## <a name="related-topics"></a>Argomenti correlati

[Office 365 Advanced Threat Protection](office-365-atp.md)
  
[Visualizzare i report per la protezione rischio avanzate di Office 365](view-reports-for-atp.md)
  
[Le autorizzazioni di sicurezza di Office 365 &amp; centro conformità](permissions-in-the-security-and-compliance-center.md)

[Gestire i messaggi in quarantena e i file in qualità di amministratore in Office 365](manage-quarantined-messages-and-files.md)
  

