---
title: Office 365 ATP per SharePoint, OneDrive e Microsoft Teams
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 6/18/2018
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 26261670-db33-4c53-b125-af0662c34607
description: Estendere la protezione di Office 365 avanzate minaccia per i file in SharePoint Online, OneDrive for Business e Teams Microsoft per consentire la collaborazione più sicura per l'organizzazione.
ms.openlocfilehash: ea1c77273be70ce27f60bfaeae3544d605553a32
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/27/2018
ms.locfileid: "22531223"
---
# <a name="office-365-atp-for-sharepoint-onedrive-and-microsoft-teams"></a>Office 365 ATP per SharePoint, OneDrive e Microsoft Teams

Utenti con regolarità condividere file e collaborare con SharePoint, OneDrive e Teams Microsoft. Con [Office 365 avanzate Threat Protection](office-365-atp.md) (degli strumenti di analisi), l'organizzazione può collaborare in modo più sicuro. Degli strumenti di analisi consente di rilevare e bloccare i file che vengono identificati come dannose in siti del team e raccolte documenti. Leggere questo articolo per ottenere una panoramica degli strumenti di analisi di SharePoint Online, OneDrive for Business e Teams Microsoft e quindi eseguire i passaggi successivi. 
  
> [!TIP]
> Per eseguire le attività descritte in questo articolo, è necessario essere un amministratore globale di Office 365 o un amministratore di sicurezza. Vedere [le autorizzazioni di sicurezza di Office 365 &amp; centro conformità](permissions-in-the-security-and-compliance-center.md). 
  
## <a name="how-it-works"></a>Funzionamento

Quando un file in SharePoint Online, OneDrive for Business e Microsoft Teams è stato identificato come dannose, degli strumenti di analisi si integra direttamente con gli archivi di file per bloccare il file. Nell'immagine seguente viene illustrato un esempio di un file dannoso rilevato in una raccolta.
  
[![Cattura di schermata del file in OneDrive for Business con uno rilevato come dannosi](media/2bba71cc-7ad1-4799-8b9d-d56f923db3a7.png)](https://support.office.com/article/01e902ad-a903-4e0f-b093-1e1ac0c37ad2)
  
Anche se il file bloccato sia ancora elencato nella raccolta documenti e applicazioni web di, portatile o desktop, file bloccati non può essere aperti, copiato, spostato o condivisi. Persone, comunque possibile eliminare un file bloccati. Ecco un esempio di quali che aspetto nel dispositivo mobile dell'utente:
  
[![Cattura di schermata dell'eliminazione di un file bloccati di OneDrive for Business da app per dispositivi mobili OneDrive](media/cb1c1705-fd0a-45b8-9a26-c22503011d54.png)](https://support.office.com/article/01e902ad-a903-4e0f-b093-1e1ac0c37ad2)
  
A seconda della configurazione di Office 365, gli utenti possono o potrebbero non avere la possibilità di scaricare un file bloccato. Di seguito viene scaricato un file bloccato aspetto sul dispositivo mobile dell'utente:
  
[![Cattura di schermata di scaricare un file bloccato in OneDrive for Business](media/be288a82-bdd8-4371-93d8-1783db3b61bc.png)](https://support.office.com/article/01e902ad-a903-4e0f-b093-1e1ac0c37ad2)
  
Per ulteriori informazioni, vedere [attivare degli strumenti di analisi di Office 365 per SharePoint, OneDrive e team di Microsoft](turn-on-atp-for-spo-odb-and-teams.md).
  
### <a name="keep-the-following-points-in-mind"></a>Tenere presente quanto segue

- Degli strumenti di analisi non verrà verificata ogni singolo file in SharePoint Online, OneDrive per Business o Microsoft Teams. Questo è per impostazione predefinita. I file vengono analizzati in modo asincrono, un processo che utilizza gli eventi di attività di condivisione e guest insieme euristica smart e segnali minaccia per identificare i file dannosi.
    
- File che vengono identificati come dannoso in SharePoint Online, OneDrive for Business o Microsoft Teams verrà visualizzate nei [rapporti di protezione di Office 365 avanzate rischio](view-reports-for-atp.md) e rischio Esplora (parte di [Business Intelligence di Office 365 rischio](office-365-ti.md)).
    
- Degli strumenti di analisi fa parte della strategia dell'organizzazione complessiva threat protection, che include la protezione da posta indesiderata e protezione anti-malware, nonché collegamenti sicuri e gli allegati sicuri. Per ulteriori informazioni, vedere [protezione contro le minacce in Office 365](protect-against-threats.md).
    
- Un amministratore di SharePoint Online è possibile determinare se si desidera consentire agli utenti di scaricare file che vengono rilevati come dannose. In tal caso, l'esecuzione del cmdlet Set-SPOTenant PowerShell utilizzando il parametro DisallowInfectedFileDownload (vedere [attivare degli strumenti di analisi di Office 365 per SharePoint, OneDrive e team Microsoft che](turn-on-atp-for-spo-odb-and-teams.md)).
    
## <a name="new-quarantine-in-atp-for-sharepoint-online-onedrive-for-business-and-microsoft-teams"></a>(Nuovo)! Quarantena in strumenti di analisi di SharePoint Online, OneDrive for Business e team di Microsoft

 * * A partire da ritardo maggio 2018, funzionalità di [quarantena](quarantine-email-messages.md) in sicurezza &amp; centro conformità vengono estese a strumenti di analisi di SharePoint Online, OneDrive for Business e Microsoft Teams. **
  
Quando un file in SharePoint Online, OneDrive for Business o Microsoft Teams viene identificato come dannose, oltre a strumenti di analisi blocco dei file l'apertura o condivise, tale file è incluso in un elenco di elementi in quarantena. (Nella protezione &amp; centro conformità, passare a **gestione delle minacce** \> **revisione** \> **quarantena** e applicare un filtro contenuto.) 
  
Parte del team di protezione di Office 365 dell'organizzazione che hanno la necessità [autorizzazioni assegnate in Office 365 Security &amp; centro conformità](permissions-in-the-security-and-compliance-center.md), è possibile scaricare, versione, report ed eliminare i file che vengono rilevati come dannose da strumenti di analisi dalla quarantena.
  
- **Rilascio e report di** un file consente di rimuovere il blocco degli strumenti di analisi del file il team rispettivi siti o una raccolta documenti di SharePoint, OneDrive o Teams Microsoft. Gli utenti sono in grado di aprire, condividere e scaricare il file. E, quando è selezionata l'opzione **Invia rapporto a Microsoft** , il file viene indicato come falso positivo a Microsoft. 
    
- **Eliminazione di un file** consente di rimuovere il file dalla quarantena; Tuttavia, il file è ancora impedito viene aperto o condivisa. Il file deve eliminato nelle rispettive raccolta o un team di sito con documenti (SharePoint Online, OneDrive for Business o Microsoft Teams). 
    
- **Download di un file** consente di scaricare e analizzare il file per eventuali falsi positivi. 
    
## <a name="next-steps"></a>Passaggi successivi

- [Attiva per SharePoint, OneDrive e team di Microsoft Office 365 degli strumenti di analisi](turn-on-atp-for-spo-odb-and-teams.md)
    
- [Informazioni sul file dannosi rilevato in SharePoint, OneDrive o Teams Microsoft](malicious-files-detected-in-spo-odb-or-teams.md)
    
## <a name="related-topics"></a>Argomenti correlati

[Office 365 Advanced Threat Protection](office-365-atp.md)
  
[Visualizzare i report per la protezione rischio avanzate di Office 365](view-reports-for-atp.md)
  
[Le autorizzazioni di sicurezza di Office 365 &amp; centro conformità](permissions-in-the-security-and-compliance-center.md)
  

