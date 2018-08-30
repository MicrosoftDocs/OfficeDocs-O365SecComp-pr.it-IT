---
title: Gestire la governance di dati in Office 365
ms.author: stephow
author: stephow-msft
manager: laurawi
ms.date: 5/9/2018
ms.audience: Admin
ms.topic: hub-page
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 48064107-fed2-4db0-9e5c-aa5ddd5ccb09
description: Governance di dati è incentrato sulla protezione dei dati intorno a cui è necessario e il recupero la rimozione quando non. Con governance di dati in Office 365, è possibile gestire il ciclo di vita completa del contenuto, dall'importazione e l'archiviazione dei dati al punto di partenza per la creazione di criteri di conservano e quindi eliminare in modo permanente il contenuto alla fine.
ms.openlocfilehash: ca3443c3b90a067bf171ddf89be604d262a7b9a4
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/27/2018
ms.locfileid: "22531318"
---
# <a name="manage-data-governance-in-office-365"></a>Gestire la governance di dati in Office 365

Governance di dati è incentrato sulla protezione dei dati intorno a cui è necessario e il recupero la rimozione quando non. Con governance di dati in Office 365, è possibile gestire il ciclo di vita completa del contenuto, dall'importazione e l'archiviazione dei dati al punto di partenza per la creazione di criteri di conservano e quindi eliminare in modo permanente il contenuto alla fine.
  
## <a name="import"></a>Importazione

Alcuni dati potrebbero essere memorizzati in posizioni esterne cloud, ad esempio server locali o in applicazioni di terze parti. Il servizio di importazione facilita portare in primo piano la messaggistica, SharePoint e OneDrive per i dati Business in Office 365, in base al caricamento direttamente tramite la rete o un'unità crittografata di spedizione per noi. È inoltre possibile utilizzare la caratteristica di importazione intelligente nel servizio di importazione per filtrare gli elementi in file PST in realtà, l'importazione alle cassette postali di destinazione. 
  
- [Panoramica di importazione del file PST a Office 365](https://support.office.com/article/ba688e0a-0fcb-4bd7-8e57-2b669564ea84)
    
- [Utilizzare il caricamento di rete per importare i file PST su Office 365](use-network-upload-to-import-pst-files.md)
    
- [Utilizzare la spedizione dell'unità per importare file PST in Office 365](use-drive-shipping-to-import-pst-files-to-office-365.md)
    
- [Utilizzare lo strumento PST insieme trovare, copiare ed eliminare i file PST all'interno dell'organizzazione](find-copy-and-delete-pst-files-in-your-organization.md)
    
- [Filtrare i dati per l'importazione di file PST a Office 365](filter-data-when-importing-pst-files.md)
    
- [Caricare contenuto locale in SharePoint Online tramite i cmdlet di PowerShell](https://support.office.com/article/555049c6-15ef-45a6-9a1f-a1ef673b867c)
    
## <a name="govern-i-store-data"></a>Regolamentare i: archiviare i dati

Dopo l'importazione dei dati, potrebbe essere necessario aumentare l'archiviazione. La caratteristica archiviazione illimitata in Office 365 (denominato espansione automatica archiviazione) offre una quantità di spazio di archiviazione di cassette postali di archiviazione illimitata.
  
- [Abilitare cassette postali di archiviazione in Office 365 Security &amp; centro conformità](enable-archive-mailboxes.md)

- [Panoramica di archiviazione illimitato in Office 365](unlimited-archiving.md)
    
- [Abilitare l'archiviazione illimitata in Office 365](enable-unlimited-archiving.md)
    

    
## <a name="govern-ii-create-policies-and-labels-to-retain-content"></a>Regolamentare II: Creare i criteri e le etichette per conservare il contenuto

Un criterio di conservazione aiuta a rispettare attivamente normative del settore e criteri interni accertandosi mantenere fino a quando ma non è più necessario rispetto a quello contenuto. Un unico criterio di conservazione può coprire tutta l'organizzazione. Inoltre, è possibile utilizzare le etichette per implementare un piano di file mediante la classificazione dei dati all'interno dell'organizzazione per la governance e quindi applicate le regole di conservazione in base alla stessa classificazione.
  
- [Panoramica dei criteri di conservazione](retention-policies.md)
    
- [Panoramica delle etichette](labels.md)
    
- [Blocco creare e pubblicare etichette tramite PowerShell](https://support.office.com/article/8986701b-ffa1-46ec-8fd0-8f7e81d5b25f.aspx)
    
- [Panoramica delle revisioni per l'eliminazione](disposition-reviews.md)
    
- [Panoramica della conservazione basata su eventi](event-driven-retention.md)
    
## <a name="govern-iii-retain-the-email-of-former-employees"></a>Regolamentare III: Mantenere il messaggio di posta elettronica di dipendenti precedenti

Quando un utente lascia l'organizzazione, è possibile mantenere la posta elettronica mediante la creazione di una cassetta postale inattiva. Una cassetta postale diventa inattiva quando una conservazione per controversia legale, il criterio di conservazione di Office 365, o altri tipi di conservazione applicato e quindi viene eliminato l'account utente di Office 365 corrispondente. Gli elementi in una cassetta postale inattiva vengono mantenuti per tutta la durata del criterio di conservazione o conservazione effettuata nella cassetta postale prima che venga effettuata inattivo.
  
- [Panoramica delle cassette postali inattive in Office 365](inactive-mailboxes-in-office-365.md)
    
- [Creare e gestire le cassette postali inattive in Office 365](create-and-manage-inactive-mailboxes.md)

- [Modificare la durata dell'attesa di una cassetta postale inattiva in Office 365](change-the-hold-duration-for-an-inactive-mailbox.md)
  
- [Ripristinare una cassetta postale inattiva in Office 365](recover-an-inactive-mailbox.md)
 
- [Ripristinare una cassetta postale inattiva in Office 365](restore-an-inactive-mailbox.md)

- [Eliminare una cassetta postale inattiva in Office 365](delete-an-inactive-mailbox.md)

## <a name="monitor"></a>Monitorare

Supervisione consente di definire i criteri che acquisiscono posta elettronica e le comunicazioni 3rd parti all'interno dell'organizzazione in modo che può essere esaminati dai revisori interni o esterni. I revisori possono classificare le comunicazioni, assicurarsi che siano conformi ai criteri dell'organizzazione e trasformare materiale ambigui se necessario.
  
È inoltre possibile utilizzare i report di governance di data e l'elenco delle cartelle attività etichetta per controllare che le etichette vengono applicate al contenuto come desiderato.
  
- [Configurare i criteri di supervisione per l’organizzazione](configure-supervision-policies.md)
    
- [Rapporti di supervisione](supervision-reports.md)
    
- [Visualizzare l’attività dell’etichetta per i documenti](view-label-activity-for-documents.md)
    
- [Visualizzare i rapporti della governance dei dati](view-the-data-governance-reports.md)
    
## <a name="more-information"></a>Ulteriori informazioni

- [Guarda i video sulla Governance dei dati dal team di Microsoft](https://go.microsoft.com/fwlink/?linkid=867039)
    
- [Visualizzare una panoramica dei criteri di governance di dati in Office 365](https://go.microsoft.com/fwlink/?linkid=852644)
    
- [Protezione di Office 365 &amp; cmdlet centro conformità](https://go.microsoft.com/fwlink/?linkid=852310)
    

