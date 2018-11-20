---
title: Office 365 ATP per SharePoint, OneDrive e Microsoft Teams
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.audience: Admin
ms.date: 11/08/2018
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 26261670-db33-4c53-b125-af0662c34607
description: Estendere la protezione di Office 365 avanzate minaccia per i file in SharePoint Online, OneDrive for Business e Teams Microsoft per consentire la collaborazione più sicura per l'organizzazione.
ms.openlocfilehash: 6891184b49aa4ea03d5c13672ac9b95fc9e6d162
ms.sourcegitcommit: 147768bbe44c8c98c02fa29ae9d882cee4ec2d6b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/09/2018
ms.locfileid: "26238448"
---
# <a name="office-365-atp-for-sharepoint-onedrive-and-microsoft-teams"></a>Office 365 ATP per SharePoint, OneDrive e Microsoft Teams

## <a name="overview-of-office-365-atp-for-sharepoint-onedrive-and-microsoft-teams"></a>Panoramica di Office 365 degli strumenti di analisi di SharePoint, OneDrive e team di Microsoft

Utenti con regolarità condividere file e collaborare con SharePoint, OneDrive e Teams Microsoft. Con [Office 365 avanzate Threat Protection](office-365-atp.md) (degli strumenti di analisi), l'organizzazione può collaborare in modo più sicuro. Degli strumenti di analisi consente di rilevare e bloccare i file che vengono identificati come dannose in siti del team e raccolte documenti.  
  
## <a name="how-it-works"></a>Funzionamento

Quando un file in SharePoint Online, OneDrive for Business e Microsoft Teams è stato identificato come dannose, degli strumenti di analisi si integra direttamente con gli archivi di file per bloccare il file. Nell'immagine seguente viene illustrato un esempio di un file dannoso rilevato in una raccolta.
  
[![Cattura di schermata del file in OneDrive for Business con uno rilevato come dannosi](media/2bba71cc-7ad1-4799-8b9d-d56f923db3a7.png)](https://support.office.com/article/01e902ad-a903-4e0f-b093-1e1ac0c37ad2)
  
Anche se il file bloccato sia ancora elencato nella raccolta documenti e applicazioni web di, portatile o desktop, file bloccati non può essere aperti, copiato, spostato o condivisi. Persone, comunque possibile eliminare un file bloccati. Ecco un esempio di quali che aspetto nel dispositivo mobile dell'utente:
  
[![Cattura di schermata dell'eliminazione di un file bloccati di OneDrive for Business da app per dispositivi mobili OneDrive](media/cb1c1705-fd0a-45b8-9a26-c22503011d54.png)](https://support.office.com/article/01e902ad-a903-4e0f-b093-1e1ac0c37ad2)
  
A seconda della configurazione di Office 365, gli utenti possono o potrebbero non avere la possibilità di scaricare un file bloccato. Di seguito viene scaricato un file bloccato aspetto sul dispositivo mobile dell'utente:
  
[![Cattura di schermata di scaricare un file bloccato in OneDrive for Business](media/be288a82-bdd8-4371-93d8-1783db3b61bc.png)](https://support.office.com/article/01e902ad-a903-4e0f-b093-1e1ac0c37ad2)
  
Per ulteriori informazioni, vedere [attivare degli strumenti di analisi di Office 365 per SharePoint, OneDrive e team di Microsoft](turn-on-atp-for-spo-odb-and-teams.md).
  
## <a name="keep-these-points-in-mind"></a>Tenere presente

- Degli strumenti di analisi non verrà verificata ogni singolo file in SharePoint Online, OneDrive per Business o Microsoft Teams. Questo è per impostazione predefinita. I file vengono analizzati in modo asincrono, un processo che utilizza gli eventi di attività di condivisione e guest insieme euristica smart e segnali minaccia per identificare i file dannosi.

- Verificare che i siti di SharePoint sono configurati per utilizzare l' [esperienza moderno](https://docs.microsoft.com/sharepoint/guide-to-sharepoint-modern-experience). Quando un file viene identificato come utenti malintenzionati e bloccati, è possono notare che questo si è verificato l'esperienza moderno, ma non la visualizzazione classica. Si applica protezione degli strumenti di analisi se viene utilizzata l'esperienza moderno o nella visualizzazione classica; Tuttavia, gli indicatori visivi che un file è bloccato sono presenti solo nella versione moderno.
    
- File che vengono identificati come dannoso in SharePoint Online, OneDrive for Business o Microsoft Teams verrà visualizzate nei [rapporti di protezione di Office 365 avanzate rischio](view-reports-for-atp.md) e rischio Esplora (parte di [Business Intelligence di Office 365 rischio](office-365-ti.md)).
    
- Degli strumenti di analisi fa parte della strategia dell'organizzazione complessiva threat protection, che include la protezione da posta indesiderata e protezione anti-malware, nonché collegamenti sicuri e gli allegati sicuri. Per ulteriori informazioni, vedere [protezione contro le minacce in Office 365](protect-against-threats.md).
    
- Un amministratore di SharePoint Online è possibile determinare se si desidera consentire agli utenti di scaricare file che vengono rilevati come dannose. In tal caso, l'esecuzione del cmdlet Set-SPOTenant PowerShell utilizzando il parametro DisallowInfectedFileDownload (vedere [attivare degli strumenti di analisi di Office 365 per SharePoint, OneDrive e team Microsoft che](turn-on-atp-for-spo-odb-and-teams.md)).
    
## <a name="quarantine-in-atp-for-sharepoint-online-onedrive-for-business-and-microsoft-teams"></a>Quarantena in strumenti di analisi di SharePoint Online, OneDrive for Business e team di Microsoft

 A partire da ritardo maggio 2018, funzionalità di [quarantena](quarantine-email-messages.md) in sicurezza &amp; centro conformità vengono estese a strumenti di analisi di SharePoint Online, OneDrive for Business e Microsoft Teams.
  
Quando un file in SharePoint Online, OneDrive for Business o Microsoft Teams viene identificato come dannose, oltre a strumenti di analisi blocco dei file l'apertura o condivise, tale file è incluso in un elenco di elementi in quarantena. (Nella protezione &amp; centro conformità, passare a **gestione delle minacce** \> **revisione** \> **quarantena** e applicare un filtro **contenuto**.) 
  
Parte del team di protezione di Office 365 dell'organizzazione che hanno la necessità [autorizzazioni assegnate in Office 365 Security &amp; centro conformità](permissions-in-the-security-and-compliance-center.md), è possibile scaricare, versione, report ed eliminare i file che vengono rilevati come dannose da strumenti di analisi dalla quarantena.
  
- **Rilascio e report di** un file consente di rimuovere il blocco degli strumenti di analisi del file il team rispettivi siti o una raccolta documenti di SharePoint, OneDrive o Teams Microsoft. Gli utenti sono in grado di aprire, condividere e scaricare il file. E, quando è selezionata l'opzione **Invia rapporto a Microsoft** , il file viene indicato come falso positivo a Microsoft. 
    
- **Eliminazione di un file** consente di rimuovere il file dalla quarantena; Tuttavia, il file è ancora impedito viene aperto o condivisa. Il file deve eliminato nelle rispettive raccolta o un team di sito con documenti (SharePoint Online, OneDrive for Business o Microsoft Teams). 
    
- **Download di un file** consente di scaricare e analizzare il file per eventuali falsi positivi. 
    
## <a name="next-steps"></a>Passaggi successivi

1. [Attiva per SharePoint, OneDrive e team di Microsoft Office 365 degli strumenti di analisi](turn-on-atp-for-spo-odb-and-teams.md)
    
2. [Informazioni sul file dannosi rilevato in SharePoint, OneDrive o Teams Microsoft](malicious-files-detected-in-spo-odb-or-teams.md)
    
