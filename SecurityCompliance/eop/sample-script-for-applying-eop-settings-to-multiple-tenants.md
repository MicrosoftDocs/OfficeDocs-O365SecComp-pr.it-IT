---
title: Script di esempio per l'applicazione delle impostazioni EOP a più tenant
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 11/17/2014
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
ms.assetid: e87e84e1-7be0-44bf-a414-d91d60ed8817
description: Il seguente script di esempio consente agli amministratori di Microsoft Exchange Online Protection (EOP) che gestiscono più tenant (aziende) di utilizzare Windows PowerShell per applicare le impostazioni di configurazione ai tenant.
ms.openlocfilehash: 787847721f46fc4b3caeec037e89306ef450141a
ms.sourcegitcommit: b688d67935edb036658bb5aa1671328498d5ddd3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2019
ms.locfileid: "30670411"
---
# <a name="sample-script-for-applying-eop-settings-to-multiple-tenants"></a><span data-ttu-id="14980-103">Script di esempio per l'applicazione delle impostazioni EOP a più tenant</span><span class="sxs-lookup"><span data-stu-id="14980-103">Sample script for applying EOP settings to multiple tenants</span></span>

<span data-ttu-id="14980-104">Il seguente script di esempio consente agli amministratori di Microsoft Exchange Online Protection (EOP) che gestiscono più tenant (aziende) di utilizzare Windows PowerShell per applicare le impostazioni di configurazione ai tenant.</span><span class="sxs-lookup"><span data-stu-id="14980-104">The following sample script lets Microsoft Exchange Online Protection (EOP) admins who manage multiple tenants (companies) use Windows PowerShell to apply configuration settings to their tenants.</span></span>
  
### <a name="to-run-a-script-or-cmdlet-on-multiple-tenants"></a><span data-ttu-id="14980-105">Eseguire uno script o un cmdlet su più tenant</span><span class="sxs-lookup"><span data-stu-id="14980-105">To run a script or cmdlet on multiple tenants</span></span>

1. <span data-ttu-id="14980-106">Usando un'applicazione quale Excel, creare un file .csv (ad esempio, c:\scripts\inputfile.csv):</span><span class="sxs-lookup"><span data-stu-id="14980-106">Using an application such as Excel, create a .csv file (for example, c:\scripts\inputfile.csv):</span></span>
    
1. <span data-ttu-id="14980-107">Nel file .csv, specificare due nomi di colonna: UserName e Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="14980-107">In the .csv file, specify two column names: UserName and Cmdlet.</span></span>
    
2. <span data-ttu-id="14980-p101">Per ogni riga del file .csv, aggiungere il nome dell'amministratore del tenant nella colonna NomeUtente e il cmdlet da eseguire per quel tenant nella colonna denominata Cmdlet. Ad esempio, utilizzare admin@contoso.com e Get-AcceptedDomain.</span><span class="sxs-lookup"><span data-stu-id="14980-p101">For each row in the .csv file, add the tenant's admin name in the UserName column and the cmdlet to run for that tenant in the Cmdlet column. For example, use admin@contoso.com and Get-AcceptedDomain.</span></span>
    
2. <span data-ttu-id="14980-110">Copiare lo script [RunCmdletOnMultipleTenants.ps1](sample-script-for-applying-eop-settings-to-multiple-tenants.md#RunCmdletOnMultipleTenants.ps1) in un editor, ad esempio Blocco note, quindi salvare il file in un percorso (ad esempio, c:\scripts) che facilita l'individuazione dei file .ps1.</span><span class="sxs-lookup"><span data-stu-id="14980-110">Copy the [RunCmdletOnMultipleTenants.ps1](sample-script-for-applying-eop-settings-to-multiple-tenants.md#RunCmdletOnMultipleTenants.ps1) script to an editor like Notepad, and then save the file to a location (like c:\scripts) that makes .ps1 files easy to find.</span></span> 
    
3. <span data-ttu-id="14980-111">Eseguire lo script utilizzando la seguente sintassi:</span><span class="sxs-lookup"><span data-stu-id="14980-111">Run the script by using the following syntax:</span></span>
    ```Powershell
     & "<file path>\RunCmdletOnMultipleTenants.ps1" "<file path>\inputfile.csv"
    ```
    
    <span data-ttu-id="14980-112">Di seguito viene riportato un esempio.</span><span class="sxs-lookup"><span data-stu-id="14980-112">Here's an example.</span></span> 
    
    ```Powershell
    & "c:\scripts\RunCmdletOnMultipleTenanats.ps1" "c:\scripts\inputfile.csv"
    ```

4. <span data-ttu-id="14980-113">Ogni tenant verrà connesso e il cmdlet verrà eseguito.</span><span class="sxs-lookup"><span data-stu-id="14980-113">Each tenant will be logged on to, and the cmdlet will be run.</span></span>
    
## <a name="runcmdletonmultipletenantsps1"></a><span data-ttu-id="14980-114">RunCmdletOnMultipleTenants. ps1</span><span class="sxs-lookup"><span data-stu-id="14980-114">RunCmdletOnMultipleTenants.ps1</span></span>
<span data-ttu-id="14980-115"><a name="RunCmdletOnMultipleTenants.ps1"> </a></span><span class="sxs-lookup"><span data-stu-id="14980-115"></span></span>

```Powershell
# This script runs Windows PowerShell cmdlets on multiple tenants.
# Usage: RunCmdletOnMultipleTenants.ps1 inputfile.csv
#  
# .csv input file sample: 
# UserName,Cmdlet
# admin@contoso.com,Get-AcceptedDomain | ft Name
# URI for connecting to remote Windows PowerShell
$URI = "https://ps.protection.outlook.com/powershell-liveid/"
# Get the .csv file name as an argument to this script.
$FilePath = $args[0]
# Import the UserName and Cmdlet values from the .csv file.
$CompanyList = Import-CSV $FilePath
# Loop through each entry from the .csv file.
ForEach ($Company in $CompanyList) {
# Get the current entry's UserName.
$UserName = $Company.UserName
# Get the current entry's Cmdlet.
$Cmdlet = $Company.Cmdlet
# Create a PowerShell credential object by using the current entry's UserName. Prompt for the password.
$UserCredential = Get-Credential -username $UserName
# Log on to a new Windows PowerShell session.
$Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri $URI -Credential $UserCredential -Authentication Basic -AllowRedirection
Import-PSSession $Session
# Here's where the script to be run on the tenant goes.
# In this example, the cmdlet in the .csv file runs.
Invoke-Expression $Cmdlet
# End the current PowerShell session.
remove-pssession -session $Session
}

```


