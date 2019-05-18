---
title: Contenuto archiviato nelle cassette postali di Exchange Online
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: ''
ROBOTS: NOINDEX, NOFOLLOW
description: I dati prodotti dalle app basate su cloud in Office 365 sono archiviati in una cassetta postale di Exchange Online di un utente nel cloud Microsoft.
ms.openlocfilehash: 380c16e65c2358961b9ee5185c40d3eb7d85950b
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/17/2019
ms.locfileid: "34157718"
---
# <a name="content-stored-in-exchange-online-mailboxes"></a>Contenuto archiviato nelle cassette postali di Exchange Online

Una cassetta postale in Exchange Online viene utilizzata principalmente per archiviare gli elementi relativi alla posta elettronica, ad esempio messaggi, elementi del calendario, attività e note. Tuttavia, la modifica del numero di app di Office 365 basate su cloud memorizza anche i dati nella cassetta postale di un utente. Uno dei vantaggi dell'archiviazione dei dati in una cassetta postale è che è possibile utilizzare gli strumenti di ricerca in ricerche di contenuto, eDiscovery, Advanced eDiscovery e indagini sui dati per individuare, visualizzare ed esportare i dati da queste app basate su cloud. Si noti che i dati di alcune di queste app sono archiviati in cartelle nascoste che si trovano in una sottostruttura di messaggi non interpersonali (non IPM) nella cassetta postale. Questo significa che i dati vengono nascosti dalla visualizzazione dell'utente quando utilizzano Outlook o altri client di posta elettronica per accedere alla propria cassetta postale.

Nella tabella seguente sono elencate le app di Office 365 che archiviano i dati in una cassetta postale basata su cloud. La tabella descrive anche il tipo di contenuto che ogni app archivia.

|App di Office 365  |Descrizione  |
|:---------|:---------|
|Forms     <br/> |I moduli (archiviati come file PDF) e le risposte a un modulo (archiviati in un file CSV) sono allegati ai messaggi di posta elettronica e archiviati in una cartella nascosta nella cassetta postale dell'utente che ha creato il modulo. Quando si esporta contenuto da moduli in un file PST, questi dati si trovano nella cartella **ApplicationDataRoot** in una sottocartella denominata con il GUID seguente: **c9a559d2-7aab-4f13-a6ed-e7e9c52aec87**.        <br/> |
|MyAnalytics    <br/> |   Analytics fornisce agli utenti informazioni dettagliate sul modo in cui passano il proprio tempo in base ai dati di posta e calendario nella propria cassetta postale. Questi dati vengono archiviati nella cassetta postale dell'utente in una cartella nascosta. Per ulteriori informazioni sui dati di analisi e su come esportarlo, vedere Exporting [data from Analytics](manage-gdpr-data-subject-requests-with-the-dsr-case-tool.md#exporting-data-from-myanalytics-and-the-office-roaming-service).      <br/> |
|Gruppi di Office 365    <br/>|  I messaggi di posta elettronica, gli elementi del calendario, i contatti (persone), le note e le attività vengono archiviati nella cassetta postale associata a un gruppo di Office 365.       <br/> |
|Outlook/Exchange Online<br/>|  I messaggi di posta elettronica, gli elementi del calendario, i contatti (persone), le note e le attività vengono archiviati nella cassetta postale di un utente.       <br/> |
|Persone    <br/> |  I contatti nell'app utenti (che sono gli stessi contatti di quelli accessibili in Outlook) vengono archiviati nella cassetta postale di un utente.      <br/> |
|Planner     <br/> |   I piani creati in Planner sono archiviati nella cassetta postale del gruppo di Office 365 corrispondente che viene provisionato quando viene creato un nuovo piano. L'alias della cassetta postale del gruppo è il nome del piano.      <br/> |
|Skype for Business    <br/>  | Le conversazioni in Skype for business sono archiviate nella cartella Cronologia conversazioni della cassetta postale di un utente. Se la cassetta postale di un partecipante a una riunione Skype viene mantenuta per controversia legale o assegnata a un criterio di conservazione, i file allegati a una riunione vengono conservati nella cassetta postale dei partecipanti.         <br/> |
|Sway     <br/> |  Gli Sway sono archiviati come file HTML collegato a un messaggio di posta elettronica e archiviati in una cartella nascosta nella cassetta postale dell'utente che ha creato il dominio. Quando si esporta contenuto da Sway in un file PST, i dati si trovano nella cartella **ApplicationDataRoot** in una sottocartella denominata con il GUID seguente **905fcf26-4EB7-48A0-9ff0-8dcc7194b5ba**.       <br/> |
|Attività    <br/> |  Le attività nell'app attività (che sono le stesse attività di quelle accessibili in Outlook) vengono memorizzate nella cassetta postale di un utente.       <br/> |
|Teams    <br/>  |Le conversazioni che fanno parte di un canale teams sono archiviate nella cassetta postale associata al team. Le conversazioni che fanno parte dell'elenco chat in teams (chiamate anche *1 x N chat*) sono archiviate nella cassetta postale degli utenti che partecipano alla chat. Inoltre, le informazioni di riepilogo per le riunioni e le chiamate in un canale di team vengono memorizzate nelle cassette postali degli utenti che hanno effettuato la chiamata alla riunione. <br/> | 
|To-Do  <br/> | Le attività (chiamate *da DOS*, che vengono salvate negli elenchi di cose da fare) nell'app da fare sono archiviate nella cassetta postale di un utente.        <br/> |
||||

> [!NOTE]
> Attualmente, se un'esenzione viene posizionata su una cassetta postale (utilizzando le esenzioni in eDiscovery e nei casi avanzati di eDiscovery), il contenuto proveniente da moduli e Sway non verrà mantenuto dall'esenzione. 