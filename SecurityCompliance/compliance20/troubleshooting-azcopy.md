---
title: Risoluzione dei problemi relativi a AzCopy in Advanced eDiscovery (Preview)
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
ms.audience: Admin
ms.topic: article
ms.service: o365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: ''
ms.openlocfilehash: 9711bee4ec9a61510b47568df37dfd3135e1e00c
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "32241078"
---
# <a name="troubleshoot-azcopy-in-advanced-ediscovery-preview"></a>Risoluzione dei problemi relativi a AzCopy in Advanced eDiscovery (Preview)

Quando si caricano dati o documenti non di Office 365 per la correzione degli errori in Advanced eDiscovery (Preview), l'interfaccia utente fornisce un comando AzCopy di Azure che contiene parametri con il percorso in cui vengono archiviati i file che si desidera caricare e Azure percorso di archiviazione in cui verranno caricati i file. Per caricare i documenti, è possibile copiare questo comando e quindi eseguirlo in un prompt dei comandi nel computer locale.  Nello screenshot seguente è riportato un esempio di un comando AzCopy:

![Caricare i file non di Office 365](../media/46ba68f6-af11-4e70-bb91-5fc7973516e3.png)

Nella maggior parte dei casi, il comando fornito funzionerà quando lo si esegue. Tuttavia, è possibile che i casi in cui il comando visualizzato non venga eseguito correttamente. Ecco alcuni possibili motivi.

## <a name="azcopy-isnt-installed-on-the-local-computer-or-its-not-installed-in-the-default-location"></a>AzCopy non è installato nel computer locale o non è installato nel percorso predefinito

Se AzCopy non è installato oppure è installato in un percorso diverso da quello predefinito (ovvero `%ProgramFiles(x86)%`), quando si esegue il comando AzCopy è possibile che venga visualizzato il messaggio di errore seguente:

    The system cannot find the path specified.

Se AzCopy non è installato nel computer locale, è possibile installarlo da qui (accertarsi di installarlo nel percorso predefinito): [https://docs.microsoft.com/azure/storage/common/storage-use-azcopy](https://docs.microsoft.com/azure/storage/common/storage-use-azcopy).


Se AzCopy è installato, ma è installato in una posizione diversa da quella predefinita, è possibile copiare il comando, incollarlo in un file di testo e quindi cambiare il percorso in cui è effettivamente installato AzCopy. Ad esempio, se si trova Azcopy `%ProgramFiles%`, è possibile modificare la prima parte del comando da `%ProgramFiles(x86)%\Microsoft SDKs\Azure\AzCopy.exe` a. `%ProgramFiles%\Microsoft SDKs\Azure\AzCopy` Dopo aver apportato questa modifica, copiarla dal file di testo e quindi eseguirla come prompt dei comandi.

> [!TIP]
> Se AzCopy è installato in un percorso diverso dal percorso di installazione predefinito, è consigliabile disinstallarlo e quindi reinstallarlo nel percorso predefinito. Ciò consentirà di prevenire questo problema in futuro.