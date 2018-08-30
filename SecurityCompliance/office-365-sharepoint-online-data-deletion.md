---
title: Eliminazione dei dati in linea di SharePoint di Office 365
ms.author: robmazz
author: robmazz
manager: laurawi
ms.date: 8/21/2018
audience: ITPro
ms.topic: article
ms.service: Office 365 Administration
localization_priority: None
search.appverid:
- MET150
ms.collection: Strat_O365_Enterprise
description: Una spiegazione dell'eliminazione dei dati in SharePoint Online.
ms.openlocfilehash: c281f6de9cd9e4978ac4a6997333d71d8835420f
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/27/2018
ms.locfileid: "22530397"
---
# <a name="sharepoint-online-data-deletion-in-office-365"></a>Eliminazione di dati in linea di SharePoint in Office 365

SharePoint Online, gli oggetti vengono memorizzate come astratto codice nel database dell'applicazione. Quando un utente carica un file in SharePoint Online, tale file disassemblato e convertito nel codice dell'applicazione e archiviati in più tabelle su più database. In SharePoint Online, tutto il contenuto che carica un cliente viene suddiviso in parti crittografate (potenzialmente con più chiavi di crittografia AES 256 bit) e distribuito nel datacenter. Per informazioni dettagliate sul processo di suddivisione in blocchi di crittografia, vedere [crittografia nel Cloud Microsoft](office-365-encryption-in-the-microsoft-cloud-overview.md). Per impedire la perdita di dati di SharePoint Online sono disponibili servizi di protezione. In particolare, i backup sono eseguiti ogni 12 ore e mantenere 14 giorni.

Quando si elimina il contenuto da un sito di SharePoint Online, non viene eliminato immediatamente. Viene inviato a un sito del Cestino, cui possa essere ripristinato, se necessario. Vedere [Ripristina posta eliminata dal Cestino raccolta siti](https://support.office.com/article/Restore-deleted-items-from-the-site-collection-recycle-bin-5fa924ee-16d7-487b-9a0a-021b9062d14b) per la procedura di ripristino. Il periodo di mantenimento Cestino del sito predefinito è di circa 90 giorni. Se si elimina il contenuto dal Cestino secondario sito, viene inviato per il Cestino raccolta siti, che presenta un periodo di mantenimento di 30 giorni. Il periodo di tempo per tenere il Cestino può essere configurato dall'amministratore, ma in assenza di tale, il periodo di conservazione predefinito è di circa 90 giorni. I server di archiviazione del sito recycle bin incide negativamente sulla quota di archiviazione di raccolta siti e la [Soglia della visualizzazione elenco](https://support.office.com/article/List-View-Threshold-b8588dae-9387-48c2-9248-c24122f07c59).

Quando si elimina una raccolta siti, che si desidera eliminare anche la gerarchia dei siti della raccolta, inclusi tutti i contenuti e le informazioni utente:
- Documenti e raccolte documenti
- Elenchi e dati
- Impostazioni di configurazione del sito
- Ruoli e informazioni sulla sicurezza relativi al sito o i relativi siti secondari
- Siti secondari di informazioni di sito Web, il contenuto e utente principale

Prima di eliminare una raccolta siti, è consigliabile che verificare la descrizione del servizio SharePoint Online per il piano che descrive la pianificazione di backup dei dati gestita da Microsoft per i siti di SharePoint Online. Si noti che possono ripristini da backup sono inoltre solo per le raccolte siti oppure siti secondari, non per i file, elenchi o raccolte. Se è necessario ripristinare quelli, utilizzare il Cestino.

Se si elimina accidentalmente una raccolta siti, essere ripristinato dal Cestino raccolta siti da un amministratore della raccolta siti entro 30 giorni. Se è necessaria una raccolta siti ripristinata dopo 30 giorni, essere ripristinato da Microsoft entro 14 giorni dalla scadenza 30 giorni, contattare Microsoft tramite una richiesta di servizio.

Disco rigido eliminazione viene generato quando un utente elimina gli elementi eliminati del Cestino del sito e la conservazione e periodi di backup scadono o quando l'amministratore elimina definitivamente una raccolta siti utilizzando il [cmdlet Remove-SPODeletedSite](https://docs.microsoft.com/powershell/module/sharepoint-online/Remove-SPODeletedSite?view=sharepoint-ps). Quando un utente rigido Elimina (Elimina in modo permanente o Elimina) contenuto di SharePoint Online, tutte le chiavi di crittografia per i blocchi eliminati vengono eliminate. I blocchi su dischi che precedentemente memorizzate blocchi eliminati vengono contrassegnati come non utilizzati e disponibili per riutilizzare.
