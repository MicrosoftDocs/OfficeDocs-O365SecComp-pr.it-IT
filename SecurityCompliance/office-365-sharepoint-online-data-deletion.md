---
title: Eliminazione dei dati in linea di SharePoint di Office 365
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: Office 365 Administration
localization_priority: None
search.appverid:
- MET150
ms.collection: Strat_O365_Enterprise
description: Una spiegazione dell'eliminazione dei dati in SharePoint Online.
ms.openlocfilehash: 8a84859ce170a4c3ca713c751aef2b6d5b911c55
ms.sourcegitcommit: 29ba4c36af8e90ddc8d885863ef25bac2cffbe94
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2018
ms.locfileid: "27411162"
---
# <a name="sharepoint-online-data-deletion-in-office-365"></a>Eliminazione di dati in linea di SharePoint in Office 365

SharePoint Online, gli oggetti vengono memorizzate come astratto codice nel database dell'applicazione. Quando un utente carica un file in SharePoint Online, tale file disassemblato e convertito nel codice dell'applicazione e archiviati in più tabelle su più database. In SharePoint Online, tutto il contenuto che carica un cliente viene suddiviso in parti crittografate (potenzialmente con più chiavi di crittografia AES 256 bit) e distribuito nel datacenter. Per informazioni dettagliate sul processo di suddivisione in blocchi di crittografia, vedere [crittografia nel Cloud Microsoft](office-365-encryption-in-the-microsoft-cloud-overview.md). 

In SharePoint Online, gli elementi vengono mantenuti per 93 giorni dal momento in cui che sono state eliminate dalla posizione originale. Rimanere nel Cestino del sito tutto il tempo, a meno che non li elimina da quest'ultimo o un utente Svuota il Cestino secondario. In tal caso, gli elementi di passare alla raccolta siti del Cestino, dove rimanere per il resto di 93 giorni. Per informazioni sul ripristino degli elementi eliminati, vedere [ripristino di elementi nel Cestino di un sito di SharePoint](https://support.office.com/en-us/article/6df466b6-55f2-4898-8d6e-c0dff851a0be#ID0EAADAAA=Online
) e [il ripristino degli elementi dal Cestino raccolta siti eliminati](https://support.office.com/article/5fa924ee-16d7-487b-9a0a-021b9062d14b). Il periodo di mantenimento Cestino non può essere configurato in SharePoint Online.

Quando si elimina una raccolta siti, che si desidera eliminare anche la gerarchia dei siti nell'insieme e tutto il contenuto al loro interno:
- Documenti e raccolte documenti
- Elenchi e dati
- Impostazioni di configurazione del sito
- Ruoli e informazioni sulla sicurezza relativi al sito o i relativi siti secondari
- Siti secondari di informazioni di sito Web, il contenuto e utente principale

Se accidentalmente si elimina una raccolta siti, può essere ripristinato da un globale o SharePoint admin utilizzando l'interfaccia di amministrazione di SharePoint. 

Disco rigido eliminazione si verifica quando un utente elimina gli elementi eliminati dal Cestino, della raccolta siti quando scadono i periodi di conservazione e di backup oppure quando l'amministratore elimina definitivamente una raccolta siti utilizzando il [cmdlet Remove-SPODeletedSite](/powershell/module/sharepoint-online/Remove-SPODeletedSite?view=sharepoint-ps). Quando un utente rigido Elimina (Elimina in modo permanente o Elimina) contenuto di SharePoint Online, tutte le chiavi di crittografia per i blocchi eliminati vengono eliminate. I blocchi su dischi che precedentemente memorizzate blocchi eliminati vengono contrassegnati come non utilizzati e disponibili per riutilizzare.
