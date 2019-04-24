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
# <a name="troubleshoot-azcopy-in-advanced-ediscovery-preview"></a><span data-ttu-id="d5ede-102">Risoluzione dei problemi relativi a AzCopy in Advanced eDiscovery (Preview)</span><span class="sxs-lookup"><span data-stu-id="d5ede-102">Troubleshoot AzCopy in Advanced eDiscovery (Preview)</span></span>

<span data-ttu-id="d5ede-103">Quando si caricano dati o documenti non di Office 365 per la correzione degli errori in Advanced eDiscovery (Preview), l'interfaccia utente fornisce un comando AzCopy di Azure che contiene parametri con il percorso in cui vengono archiviati i file che si desidera caricare e Azure percorso di archiviazione in cui verranno caricati i file.</span><span class="sxs-lookup"><span data-stu-id="d5ede-103">When loading non-Office 365 data or documents for error remediation in Advanced eDiscovery (Preview), the user interface supplies an Azure AzCopy command that contains parameters with the location of where the files that you want to upload are stored and the Azure storage location that the files will be uploaded to.</span></span> <span data-ttu-id="d5ede-104">Per caricare i documenti, è possibile copiare questo comando e quindi eseguirlo in un prompt dei comandi nel computer locale.</span><span class="sxs-lookup"><span data-stu-id="d5ede-104">To upload your documents, you copy this command and then run it in a Command Prompt on your local computer.</span></span>  <span data-ttu-id="d5ede-105">Nello screenshot seguente è riportato un esempio di un comando AzCopy:</span><span class="sxs-lookup"><span data-stu-id="d5ede-105">The follow screenshot shows an example of an AzCopy command:</span></span>

![Caricare i file non di Office 365](../media/46ba68f6-af11-4e70-bb91-5fc7973516e3.png)

<span data-ttu-id="d5ede-107">Nella maggior parte dei casi, il comando fornito funzionerà quando lo si esegue.</span><span class="sxs-lookup"><span data-stu-id="d5ede-107">In most cases, the command that's provided will work when you run it.</span></span> <span data-ttu-id="d5ede-108">Tuttavia, è possibile che i casi in cui il comando visualizzato non venga eseguito correttamente.</span><span class="sxs-lookup"><span data-stu-id="d5ede-108">However, there may be cases when the command that's displayed will not run successfully.</span></span> <span data-ttu-id="d5ede-109">Ecco alcuni possibili motivi.</span><span class="sxs-lookup"><span data-stu-id="d5ede-109">Here's a few possible reasons.</span></span>

## <a name="azcopy-isnt-installed-on-the-local-computer-or-its-not-installed-in-the-default-location"></a><span data-ttu-id="d5ede-110">AzCopy non è installato nel computer locale o non è installato nel percorso predefinito</span><span class="sxs-lookup"><span data-stu-id="d5ede-110">AzCopy isn't installed on the local computer or it's not installed in the default location</span></span>

<span data-ttu-id="d5ede-111">Se AzCopy non è installato oppure è installato in un percorso diverso da quello predefinito (ovvero `%ProgramFiles(x86)%`), quando si esegue il comando AzCopy è possibile che venga visualizzato il messaggio di errore seguente:</span><span class="sxs-lookup"><span data-stu-id="d5ede-111">If AzCopy isn't installed or it's installed in a location other than the default install location (which is `%ProgramFiles(x86)%`), you may receive the following error when you run the AzCopy command:</span></span>

    The system cannot find the path specified.

<span data-ttu-id="d5ede-112">Se AzCopy non è installato nel computer locale, è possibile installarlo da qui (accertarsi di installarlo nel percorso predefinito): [https://docs.microsoft.com/azure/storage/common/storage-use-azcopy](https://docs.microsoft.com/azure/storage/common/storage-use-azcopy).</span><span class="sxs-lookup"><span data-stu-id="d5ede-112">If AzCopy isn't install on the local computer, you can install from here (being sure to install it in the default location): [https://docs.microsoft.com/azure/storage/common/storage-use-azcopy](https://docs.microsoft.com/azure/storage/common/storage-use-azcopy).</span></span>


<span data-ttu-id="d5ede-113">Se AzCopy è installato, ma è installato in una posizione diversa da quella predefinita, è possibile copiare il comando, incollarlo in un file di testo e quindi cambiare il percorso in cui è effettivamente installato AzCopy.</span><span class="sxs-lookup"><span data-stu-id="d5ede-113">If AzCopy is installed, but it's installed in a location different than the default location, you can copy the command, paste it to a text file, and then change the path to the location where AzCopy is actually installed.</span></span> <span data-ttu-id="d5ede-114">Ad esempio, se si trova Azcopy `%ProgramFiles%`, è possibile modificare la prima parte del comando da `%ProgramFiles(x86)%\Microsoft SDKs\Azure\AzCopy.exe` a. `%ProgramFiles%\Microsoft SDKs\Azure\AzCopy`</span><span class="sxs-lookup"><span data-stu-id="d5ede-114">For example, if Azcopy is located in `%ProgramFiles%`, then you can change the first part of the command from `%ProgramFiles(x86)%\Microsoft SDKs\Azure\AzCopy.exe` to `%ProgramFiles%\Microsoft SDKs\Azure\AzCopy`.</span></span> <span data-ttu-id="d5ede-115">Dopo aver apportato questa modifica, copiarla dal file di testo e quindi eseguirla come prompt dei comandi.</span><span class="sxs-lookup"><span data-stu-id="d5ede-115">After you make this change, copy it from the text file and then run it a Command Prompt.</span></span>

> [!TIP]
> <span data-ttu-id="d5ede-116">Se AzCopy è installato in un percorso diverso dal percorso di installazione predefinito, è consigliabile disinstallarlo e quindi reinstallarlo nel percorso predefinito.</span><span class="sxs-lookup"><span data-stu-id="d5ede-116">If AzCopy is installed in a location other then the default install location, consider uninstalling it and then re-installing it in the default location.</span></span> <span data-ttu-id="d5ede-117">Ciò consentirà di prevenire questo problema in futuro.</span><span class="sxs-lookup"><span data-stu-id="d5ede-117">This will help prevent this issue in the future.</span></span>