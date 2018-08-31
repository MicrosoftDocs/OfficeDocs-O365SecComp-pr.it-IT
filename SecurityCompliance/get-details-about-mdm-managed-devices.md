---
title: Ottenere informazioni dettagliate sui dispositivi gestiti da Mobile Device Management (MDM) per Office 365
ms.author: brendonb
author: brendonb
manager: laurawi
ms.date: 6/12/2018
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MBS150
- MET150
ms.assetid: 5602963c-a1f2-4c21-afb9-f66cd7dca1f0
description: In questo articolo viene illustrato come utilizzare Windows PowerShell per ottenere informazioni dettagliate sui dispositivi nell'organizzazione impostati per la gestione dei dispositivi mobili per Office 365.
ms.openlocfilehash: 2e406d3583e7892531b7c74bef0db374672956c7
ms.sourcegitcommit: c31424cafbf1953f2864d7e2ceb95b329a694edb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/29/2018
ms.locfileid: "23272531"
---
# <a name="get-details-about-devices-managed-by-mobile-device-management-mdm-for-office-365"></a><span data-ttu-id="3aa48-103">Ottenere informazioni dettagliate sui dispositivi gestiti da Mobile Device Management (MDM) per Office 365</span><span class="sxs-lookup"><span data-stu-id="3aa48-103">Get details about devices managed by Mobile Device Management (MDM) for Office 365</span></span>

<span data-ttu-id="3aa48-104">In questo articolo viene illustrato come utilizzare Windows PowerShell per ottenere informazioni dettagliate sui dispositivi nell'organizzazione impostati per la gestione dei dispositivi mobili per Office 365.</span><span class="sxs-lookup"><span data-stu-id="3aa48-104">This article shows you how to use Windows PowerShell to get details about the devices in your organization that you set up for Mobile Device Management for Office 365.</span></span> 
  
## <a name="what-device-details-can-i-get"></a><span data-ttu-id="3aa48-105">Quali dispositivi i dettagli è possibile ottenere?</span><span class="sxs-lookup"><span data-stu-id="3aa48-105">What device details can I get?</span></span>

<span data-ttu-id="3aa48-106">Di seguito vengono illustrati.</span><span class="sxs-lookup"><span data-stu-id="3aa48-106">Here's a breakdown.</span></span>
  
|<span data-ttu-id="3aa48-107">**Dettagli**</span><span class="sxs-lookup"><span data-stu-id="3aa48-107">**Detail**</span></span>|<span data-ttu-id="3aa48-108">**Sugli aspetti da considerare PowerShell**</span><span class="sxs-lookup"><span data-stu-id="3aa48-108">**What to look for in PowerShell**</span></span>|
|:-----|:-----|
|<span data-ttu-id="3aa48-109">Dispositivo è [iscritti MDM per Office 365](enroll-your-mobile-device.md)</span><span class="sxs-lookup"><span data-stu-id="3aa48-109">Device is [enrolled in MDM for Office 365](enroll-your-mobile-device.md)</span></span> <br/> |<span data-ttu-id="3aa48-110">Il valore del parametro *isManaged* è:</span><span class="sxs-lookup"><span data-stu-id="3aa48-110">The value of the  *isManaged*  parameter is:</span></span>  <br/> <span data-ttu-id="3aa48-111">**True** = è iscritto al dispositivo.</span><span class="sxs-lookup"><span data-stu-id="3aa48-111">**True** = device is enrolled.</span></span>  <br/> <span data-ttu-id="3aa48-112">**False** = dispositivo non è registrato.</span><span class="sxs-lookup"><span data-stu-id="3aa48-112">**False** = device is not enrolled.</span></span>  <br/> |
|<span data-ttu-id="3aa48-113">Dispositivo è conforme ai [criteri di protezione di dispositivo](https://go.microsoft.com/fwlink/?linkid=615144)</span><span class="sxs-lookup"><span data-stu-id="3aa48-113">Device is compliant with your [device security policies](https://go.microsoft.com/fwlink/?linkid=615144)</span></span> <br/> |<span data-ttu-id="3aa48-114">Il valore del parametro *isCompliant* è:</span><span class="sxs-lookup"><span data-stu-id="3aa48-114">The value of the  *isCompliant*  parameter is:</span></span>  <br/> <span data-ttu-id="3aa48-115">**True** = risulti conformi ai criteri.</span><span class="sxs-lookup"><span data-stu-id="3aa48-115">**True** = device is compliant with policies.</span></span>  <br/> <span data-ttu-id="3aa48-116">**False** = dispositivo non è compatibile con i criteri.</span><span class="sxs-lookup"><span data-stu-id="3aa48-116">**False** = device is not compliant with policies.</span></span>  <br/> |
   
![Flusso che mostra i valori di parametri AAD Shell per reclamo e indica se vengono registrati devices](media/647b70f4-f886-41ef-8bff-04773a1da278.png)
  
> [!NOTE]
> <span data-ttu-id="3aa48-118">I comandi e script in questo articolo anche restituirà informazioni dettagliate su tutti i dispositivi che vengono gestiti da [Microsoft Intune](https://www.microsoft.com/en-us/cloud-platform/microsoft-intune).</span><span class="sxs-lookup"><span data-stu-id="3aa48-118">The commands and scripts in this article will also return details about any devices that are managed by [Microsoft Intune](https://www.microsoft.com/en-us/cloud-platform/microsoft-intune).</span></span> 
  
## <a name="before-you-begin"></a><span data-ttu-id="3aa48-119">Informazioni preliminari</span><span class="sxs-lookup"><span data-stu-id="3aa48-119">Before you begin</span></span>

<span data-ttu-id="3aa48-120">Esistono alcuni aspetti che sarà necessario configurare ed eseguire i comandi e gli script descritti in questo articolo.</span><span class="sxs-lookup"><span data-stu-id="3aa48-120">There are a few things you'll need to set up to run the commands and scripts described in this article.</span></span>
  
### <a name="step-1-download-and-install-the-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="3aa48-121">Passaggio 1: Scaricare e installare il Azure Active Directory Module per Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="3aa48-121">Step 1: Download and install the Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="3aa48-122">Per ulteriori informazioni su questi passaggi, vedere [Connect to Office 365 PowerShell](https://docs.microsoft.com/Office365/enterprise/powershell/connect-to-office-365-powershell).</span><span class="sxs-lookup"><span data-stu-id="3aa48-122">For more info on these steps, see [Connect to Office 365 PowerShell](https://docs.microsoft.com/Office365/enterprise/powershell/connect-to-office-365-powershell).</span></span>
  
1. <span data-ttu-id="3aa48-123">Accedere a [Microsoft Online Services Assistente per l'accesso per RTWl i professionisti IT](https://www.microsoft.com/en-us/download/details.aspx?id=41950) e fare clic su **Download** per Microsoft Online Services-Assistente per l'accesso.</span><span class="sxs-lookup"><span data-stu-id="3aa48-123">Go to [Microsoft Online Services Sign-In Assistant for IT Professionals RTWl](https://www.microsoft.com/en-us/download/details.aspx?id=41950) and click **Download** for Microsoft Online Services Sign-in Assistant.</span></span> 
    
2. <span data-ttu-id="3aa48-124">Installare il Microsoft Azure Active Directory Module per Windows PowerShell con la procedura seguente:</span><span class="sxs-lookup"><span data-stu-id="3aa48-124">Install the Microsoft Azure Active Directory Module for Windows PowerShell with these steps:</span></span>
    
    1. <span data-ttu-id="3aa48-125">Aprire un prompt dei comandi di PowerShell di livello amministrativo.</span><span class="sxs-lookup"><span data-stu-id="3aa48-125">Open an administrator-level PowerShell command prompt.</span></span>
        
    2. <span data-ttu-id="3aa48-126">Eseguire il `Install-Module MSOnline` comando.</span><span class="sxs-lookup"><span data-stu-id="3aa48-126">Run the `Install-Module MSOnline` command.</span></span>
        
    3. <span data-ttu-id="3aa48-127">Se viene richiesto di installare il provider NuGet, digitare `Y` e premere INVIO.</span><span class="sxs-lookup"><span data-stu-id="3aa48-127">If prompted to install the NuGet provider, type `Y` and press ENTER.</span></span>
        
    4. <span data-ttu-id="3aa48-128">Se viene richiesto di installare il modulo da PSGallery, digitare `Y` e premere INVIO.</span><span class="sxs-lookup"><span data-stu-id="3aa48-128">If prompted to install the module from PSGallery, type `Y` and press ENTER.</span></span>
        
    5. <span data-ttu-id="3aa48-129">Dopo l'installazione, chiudere la finestra di comando PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3aa48-129">After installation, close the PowerShell command window.</span></span>
    
### <a name="step-2-connect-to-your-office-365-subscription"></a><span data-ttu-id="3aa48-130">Passaggio 2: Connessione per la sottoscrizione a Office 365</span><span class="sxs-lookup"><span data-stu-id="3aa48-130">Step 2: Connect to your Office 365 subscription</span></span>

1. <span data-ttu-id="3aa48-131">Nel Windows Azure Active Directory Module per Windows PowerShell, eseguire il comando seguente.</span><span class="sxs-lookup"><span data-stu-id="3aa48-131">In the Windows Azure Active Directory Module for Windows PowerShell, run the following command.</span></span></br>  
  `$UserCredential = Get-Credential`

2. <span data-ttu-id="3aa48-132">Nella finestra di dialogo **Richiesta credenziali di Windows PowerShell** digitare il nome utente e password per l'account amministratore globale di Office 365 e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="3aa48-132">In the **Windows PowerShell Credential Request** dialog box, type the user name and password for your Office 365 global admin account, and then click **OK**.</span></span>
    
3. <span data-ttu-id="3aa48-133">Eseguire il comando riportato di seguito.</span><span class="sxs-lookup"><span data-stu-id="3aa48-133">Run the following command.</span></span></br>
    `
  Connect-MsolService -Credential $UserCredential
  `

### <a name="step-3-make-sure-youre-able-to-run-powershell-scripts"></a><span data-ttu-id="3aa48-134">Passaggio 3: Verificare che si è in grado di eseguire gli script di PowerShell</span><span class="sxs-lookup"><span data-stu-id="3aa48-134">Step 3: Make sure you're able to run PowerShell scripts</span></span>

> [!NOTE]
> <span data-ttu-id="3aa48-135">È possibile ignorare questo passaggio se sta già configurato per l'esecuzione degli script di PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3aa48-135">You can skip this step if you're already set up to run PowerShell scripts.</span></span> 
  
<span data-ttu-id="3aa48-136">Per eseguire lo script **Get-MsolUserDeviceComplianceStatus.ps1** , è necessario abilitare l'esecuzione di script di PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3aa48-136">To run the **Get-MsolUserDeviceComplianceStatus.ps1** script, you need to enable the running of PowerShell scripts.</span></span> 
  
1. <span data-ttu-id="3aa48-p101">Dal Desktop fare clic sul pulsante **Start**e quindi digitare Windows PowerShell. Fare clic con il pulsante destro **Windows PowerShell**e quindi fare clic su **Esegui come amministratore**.</span><span class="sxs-lookup"><span data-stu-id="3aa48-p101">From your Windows Desktop, click **Start**, and then type Windows PowerShell. Right click **Windows PowerShell**, and then click **Run as administrator**.</span></span>
    
2. <span data-ttu-id="3aa48-139">Eseguire il comando riportato di seguito.</span><span class="sxs-lookup"><span data-stu-id="3aa48-139">Run the following command.</span></span></br>
  `Set-ExecutionPolicy RemoteSigned`

3. <span data-ttu-id="3aa48-140">Quando richiesto, digitare `Y` e quindi premere INVIO.</span><span class="sxs-lookup"><span data-stu-id="3aa48-140">When prompted, type `Y` and then press Enter.</span></span> 
    
## <a name="run-the-get-msoldevice-cmdlet-to-display-details-for-all-devices-in-your-organization"></a><span data-ttu-id="3aa48-141">Eseguire il cmdlet Get-MsolDevice per visualizzare informazioni dettagliate per tutti i dispositivi dell'organizzazione</span><span class="sxs-lookup"><span data-stu-id="3aa48-141">Run the Get-MsolDevice cmdlet to display details for all devices in your organization</span></span>

1. <span data-ttu-id="3aa48-142">Aprire il modulo Microsoft Azure Active Directory per Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3aa48-142">Open the Microsoft Azure Active Directory Module for Windows PowerShell.</span></span>
    
2. <span data-ttu-id="3aa48-143">Eseguire il comando riportato di seguito.</span><span class="sxs-lookup"><span data-stu-id="3aa48-143">Run the following command.</span></span></br>
  ```
  Get-MsolDevice -All -ReturnRegisteredOwners | Where-Object {$_.RegisteredOwners.Count -gt 0}
  ```

<span data-ttu-id="3aa48-144">Per ulteriori esempi, vedere [Get-MsolDevice](https://go.microsoft.com/fwlink/?linkid=841721).</span><span class="sxs-lookup"><span data-stu-id="3aa48-144">For more examples, see [Get-MsolDevice](https://go.microsoft.com/fwlink/?linkid=841721).</span></span>
  
## <a name="run-a-script-to-get-device-details"></a><span data-ttu-id="3aa48-145">Eseguire uno script per visualizzare dettagli dispositivo</span><span class="sxs-lookup"><span data-stu-id="3aa48-145">Run a script to get device details</span></span>

### <a name="first-save-the-script-to-your-computer"></a><span data-ttu-id="3aa48-146">Per prima cosa, salvare lo script nel computer</span><span class="sxs-lookup"><span data-stu-id="3aa48-146">First, save the script to your computer</span></span>

1. <span data-ttu-id="3aa48-147">Copiare e incollare il testo seguente nel blocco note.</span><span class="sxs-lookup"><span data-stu-id="3aa48-147">Copy and paste the following text into Notepad.</span></span></br> 
  ```
  param (
      [PSObject[]]$users = @(),
      [Switch]$export,
      [String]$exportFileName = "UserDeviceComplianceStatus_" + (Get-Date -Format "yyMMdd_HHMMss") + ".csv",
      [String]$exportPath = [Environment]::GetFolderPath("Desktop")
   )
  [System.Collections.IDictionary]$script:schema = @{
      
      DeviceId = ''
      DeviceOSType = ''
      DeviceOSVersion = ''
      DeviceTrustLevel = ''
      DisplayName = ''
      IsCompliant = ''
      IsManaged = ''
      ApproximateLastLogonTimestamp = ''
      DeviceObjectId = ''    
      RegisteredOwnerUpn = ''
      RegisteredOwnerObjectId = ''
      RegisteredOwnerDisplayName = ''
  }
  function createResultObject
  {
      [PSObject]$resultObject = New-Object -TypeName PSObject -Property $script:schema
      return $resultObject
  }
  If ($users.Count -eq 0)
  {
      $users = Get-MsolUser
  }
  [PSObject[]]$result = foreach ($u in $users)
  {
      
      [PSObject]$devices = get-msoldevice -RegisteredOwnerUpn $u.UserPrincipalName
      foreach ($d in $devices)
      {
          [PSObject]$deviceResult = createResultObject
          $deviceResult.DeviceId = $d.DeviceId 
          $deviceResult.DeviceOSType = $d.DeviceOSType 
          $deviceResult.DeviceOSVersion = $d.DeviceOSVersion 
          $deviceResult.DeviceTrustLevel = $d.DeviceTrustLevel
          $deviceResult.DisplayName = $d.DisplayName
          $deviceResult.IsCompliant = $d.GraphDeviceObject.IsCompliant
          $deviceResult.IsManaged = $d.GraphDeviceObject.IsManaged
          $deviceResult.DeviceObjectId = $d.ObjectId
          $deviceResult.RegisteredOwnerUpn = $u.UserPrincipalName
          $deviceResult.RegisteredOwnerObjectId = $u.ObjectId
          $deviceResult.RegisteredOwnerDisplayName = $u.DisplayName
          $deviceResult.ApproximateLastLogonTimestamp = $d.ApproximateLastLogonTimestamp
          $deviceResult
      }
  }
  If ($export)
  {
      $result | Export-Csv -path ($exportPath + "\" + $exportFileName) -NoTypeInformation
  }
  Else
  {
      $result
  }
  
  ```

2. <span data-ttu-id="3aa48-148">Salvarlo come file di script di Windows PowerShell con l'estensione del file **. ps1**.</span><span class="sxs-lookup"><span data-stu-id="3aa48-148">Save it as a Windows PowerShell script file by using the file extension **.ps1**.</span></span> </br><span data-ttu-id="3aa48-149">Esempio:</span><span class="sxs-lookup"><span data-stu-id="3aa48-149">Example:</span></span></br> <span data-ttu-id="3aa48-150">`Get-MsolUserDeviceComplianceStatus.ps1`.</span><span class="sxs-lookup"><span data-stu-id="3aa48-150"></span></span>
    
### <a name="run-the-script-to-get-device-information-for-a-single-user-account"></a><span data-ttu-id="3aa48-151">Eseguire lo script per ottenere informazioni sul dispositivo per un singolo account utente</span><span class="sxs-lookup"><span data-stu-id="3aa48-151">Run the script to get device information for a single user account</span></span>

1. <span data-ttu-id="3aa48-152">Aprire il modulo Microsoft Azure Active Directory per Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3aa48-152">Open the Microsoft Azure Active Directory Module for Windows PowerShell.</span></span>
    
2. <span data-ttu-id="3aa48-p102">Passare alla cartella in cui è stato salvato lo script. Ad esempio, se è stato salvato a C:\PS-Scripts, eseguire il comando seguente.</span><span class="sxs-lookup"><span data-stu-id="3aa48-p102">Navigate to the folder where you saved the script. For example, if you saved it to C:\PS-Scripts, you'd run the following command.</span></span></br>
    `cd C:\PS-Scripts`

3. <span data-ttu-id="3aa48-p103">Eseguire il comando seguente per identificare l'utente che si desidera visualizzare dettagli dispositivo per. In questo esempio vengono ottenuti i dettagli per bar@example.com.</span><span class="sxs-lookup"><span data-stu-id="3aa48-p103">Run the following command to identify the user you want to get device details for. This example gets details for bar@example.com.</span></span></br>
  ```
  $u = Get-MsolUser -UserPrincipalName bar@example.com
  ```

4. <span data-ttu-id="3aa48-157">Eseguire il comando seguente per avviare lo script.</span><span class="sxs-lookup"><span data-stu-id="3aa48-157">Run the following command to initiate the script.</span></span></br>
  ```
  .\Get-MsolUserDeviceComplianceStatus.ps1 -User $u -Export
  ```

<span data-ttu-id="3aa48-p104">Vengono esportate le informazioni sul desktop di Windows come file CSV. È possibile utilizzare i parametri aggiuntivi per specificare il nome di file e il percorso del file CSV.</span><span class="sxs-lookup"><span data-stu-id="3aa48-p104">The information is exported to your Windows Desktop as a CSV file. You can use additional parameters to specify the file name and path of the CSV.</span></span>
  
### <a name="run-the-script-to-get-device-information-for-a-group-of-users"></a><span data-ttu-id="3aa48-160">Eseguire lo script per ottenere informazioni sui dispositivi di un gruppo di utenti</span><span class="sxs-lookup"><span data-stu-id="3aa48-160">Run the script to get device information for a group of users</span></span>

1. <span data-ttu-id="3aa48-161">Aprire il modulo Microsoft Azure Active Directory per Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3aa48-161">Open the Microsoft Azure Active Directory Module for Windows PowerShell.</span></span>
    
2. <span data-ttu-id="3aa48-p105">Passare alla cartella in cui è stato salvato lo script. Ad esempio, se è stato salvato a C:\PS-Scripts, eseguire il comando seguente.</span><span class="sxs-lookup"><span data-stu-id="3aa48-p105">Navigate to the folder where you saved the script. For example, if you saved it to C:\PS-Scripts, you'd run the following command.</span></span></br>
  `cd C:\PS-Scripts`

3. <span data-ttu-id="3aa48-p106">Eseguire il comando seguente per identificare il gruppo che si desidera visualizzare dettagli dispositivo per. In questo esempio vengono ottenuti i dettagli per gli utenti nel gruppo FinanceStaff.</span><span class="sxs-lookup"><span data-stu-id="3aa48-p106">Run the following command to identify the group you want to get device details for. This example gets details for users in the FinanceStaff group.</span></span></br>
  ```
  $u = Get-MsolGroupMember -SearchString "FinanceStaff" | % { Get-MsolUser -ObjectId $_.ObjectId }
  ```

4. <span data-ttu-id="3aa48-166">Eseguire il comando seguente per avviare lo script.</span><span class="sxs-lookup"><span data-stu-id="3aa48-166">Run the following command to initiate the script.</span></span></br>
  ```
  .\Get-MsolUserDeviceComplianceStatus.ps1 -User $u -Export
  ```

<span data-ttu-id="3aa48-p107">Vengono esportate le informazioni sul desktop di Windows come file CSV. È possibile utilizzare i parametri aggiuntivi per specificare il nome di file e il percorso del file CSV.</span><span class="sxs-lookup"><span data-stu-id="3aa48-p107">The information is exported to your Windows Desktop as a CSV file. You can use additional parameters to specify the file name and path of the CSV.</span></span>
  
## <a name="more-info"></a><span data-ttu-id="3aa48-169">Altre informazioni</span><span class="sxs-lookup"><span data-stu-id="3aa48-169">More info</span></span>

[<span data-ttu-id="3aa48-170">Panoramica di MDM per Office 365</span><span class="sxs-lookup"><span data-stu-id="3aa48-170">Overview of MDM for Office 365</span></span>](overview-of-mdm.md)
  
[<span data-ttu-id="3aa48-171">Get-MsolDevice</span><span class="sxs-lookup"><span data-stu-id="3aa48-171">Get-MsolDevice</span></span>](https://go.microsoft.com/fwlink/?linkid=841721)
  

