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
# <a name="get-details-about-devices-managed-by-mobile-device-management-mdm-for-office-365"></a>Ottenere informazioni dettagliate sui dispositivi gestiti da Mobile Device Management (MDM) per Office 365

In questo articolo viene illustrato come utilizzare Windows PowerShell per ottenere informazioni dettagliate sui dispositivi nell'organizzazione impostati per la gestione dei dispositivi mobili per Office 365. 
  
## <a name="what-device-details-can-i-get"></a>Quali dispositivi i dettagli è possibile ottenere?

Di seguito vengono illustrati.
  
|**Dettagli**|**Sugli aspetti da considerare PowerShell**|
|:-----|:-----|
|Dispositivo è [iscritti MDM per Office 365](enroll-your-mobile-device.md) <br/> |Il valore del parametro *isManaged* è:  <br/> **True** = è iscritto al dispositivo.  <br/> **False** = dispositivo non è registrato.  <br/> |
|Dispositivo è conforme ai [criteri di protezione di dispositivo](https://go.microsoft.com/fwlink/?linkid=615144) <br/> |Il valore del parametro *isCompliant* è:  <br/> **True** = risulti conformi ai criteri.  <br/> **False** = dispositivo non è compatibile con i criteri.  <br/> |
   
![Flusso che mostra i valori di parametri AAD Shell per reclamo e indica se vengono registrati devices](media/647b70f4-f886-41ef-8bff-04773a1da278.png)
  
> [!NOTE]
> I comandi e script in questo articolo anche restituirà informazioni dettagliate su tutti i dispositivi che vengono gestiti da [Microsoft Intune](https://www.microsoft.com/en-us/cloud-platform/microsoft-intune). 
  
## <a name="before-you-begin"></a>Informazioni preliminari

Esistono alcuni aspetti che sarà necessario configurare ed eseguire i comandi e gli script descritti in questo articolo.
  
### <a name="step-1-download-and-install-the-azure-active-directory-module-for-windows-powershell"></a>Passaggio 1: Scaricare e installare il Azure Active Directory Module per Windows PowerShell

Per ulteriori informazioni su questi passaggi, vedere [Connect to Office 365 PowerShell](https://docs.microsoft.com/Office365/enterprise/powershell/connect-to-office-365-powershell).
  
1. Accedere a [Microsoft Online Services Assistente per l'accesso per RTWl i professionisti IT](https://www.microsoft.com/en-us/download/details.aspx?id=41950) e fare clic su **Download** per Microsoft Online Services-Assistente per l'accesso. 
    
2. Installare il Microsoft Azure Active Directory Module per Windows PowerShell con la procedura seguente:
    
    1. Aprire un prompt dei comandi di PowerShell di livello amministrativo.
        
    2. Eseguire il `Install-Module MSOnline` comando.
        
    3. Se viene richiesto di installare il provider NuGet, digitare `Y` e premere INVIO.
        
    4. Se viene richiesto di installare il modulo da PSGallery, digitare `Y` e premere INVIO.
        
    5. Dopo l'installazione, chiudere la finestra di comando PowerShell.
    
### <a name="step-2-connect-to-your-office-365-subscription"></a>Passaggio 2: Connessione per la sottoscrizione a Office 365

1. Nel Windows Azure Active Directory Module per Windows PowerShell, eseguire il comando seguente.</br>  
  `$UserCredential = Get-Credential`

2. Nella finestra di dialogo **Richiesta credenziali di Windows PowerShell** digitare il nome utente e password per l'account amministratore globale di Office 365 e quindi fare clic su **OK**.
    
3. Eseguire il comando riportato di seguito.</br>
    `
  Connect-MsolService -Credential $UserCredential
  `

### <a name="step-3-make-sure-youre-able-to-run-powershell-scripts"></a>Passaggio 3: Verificare che si è in grado di eseguire gli script di PowerShell

> [!NOTE]
> È possibile ignorare questo passaggio se sta già configurato per l'esecuzione degli script di PowerShell. 
  
Per eseguire lo script **Get-MsolUserDeviceComplianceStatus.ps1** , è necessario abilitare l'esecuzione di script di PowerShell. 
  
1. Dal Desktop fare clic sul pulsante **Start**e quindi digitare Windows PowerShell. Fare clic con il pulsante destro **Windows PowerShell**e quindi fare clic su **Esegui come amministratore**.
    
2. Eseguire il comando riportato di seguito.</br>
  `Set-ExecutionPolicy RemoteSigned`

3. Quando richiesto, digitare `Y` e quindi premere INVIO. 
    
## <a name="run-the-get-msoldevice-cmdlet-to-display-details-for-all-devices-in-your-organization"></a>Eseguire il cmdlet Get-MsolDevice per visualizzare informazioni dettagliate per tutti i dispositivi dell'organizzazione

1. Aprire il modulo Microsoft Azure Active Directory per Windows PowerShell.
    
2. Eseguire il comando riportato di seguito.</br>
  ```
  Get-MsolDevice -All -ReturnRegisteredOwners | Where-Object {$_.RegisteredOwners.Count -gt 0}
  ```

Per ulteriori esempi, vedere [Get-MsolDevice](https://go.microsoft.com/fwlink/?linkid=841721).
  
## <a name="run-a-script-to-get-device-details"></a>Eseguire uno script per visualizzare dettagli dispositivo

### <a name="first-save-the-script-to-your-computer"></a>Per prima cosa, salvare lo script nel computer

1. Copiare e incollare il testo seguente nel blocco note.</br> 
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

2. Salvarlo come file di script di Windows PowerShell con l'estensione del file **. ps1**. </br>Esempio:</br> `Get-MsolUserDeviceComplianceStatus.ps1`.
    
### <a name="run-the-script-to-get-device-information-for-a-single-user-account"></a>Eseguire lo script per ottenere informazioni sul dispositivo per un singolo account utente

1. Aprire il modulo Microsoft Azure Active Directory per Windows PowerShell.
    
2. Passare alla cartella in cui è stato salvato lo script. Ad esempio, se è stato salvato a C:\PS-Scripts, eseguire il comando seguente.</br>
    `cd C:\PS-Scripts`

3. Eseguire il comando seguente per identificare l'utente che si desidera visualizzare dettagli dispositivo per. In questo esempio vengono ottenuti i dettagli per bar@example.com.</br>
  ```
  $u = Get-MsolUser -UserPrincipalName bar@example.com
  ```

4. Eseguire il comando seguente per avviare lo script.</br>
  ```
  .\Get-MsolUserDeviceComplianceStatus.ps1 -User $u -Export
  ```

Vengono esportate le informazioni sul desktop di Windows come file CSV. È possibile utilizzare i parametri aggiuntivi per specificare il nome di file e il percorso del file CSV.
  
### <a name="run-the-script-to-get-device-information-for-a-group-of-users"></a>Eseguire lo script per ottenere informazioni sui dispositivi di un gruppo di utenti

1. Aprire il modulo Microsoft Azure Active Directory per Windows PowerShell.
    
2. Passare alla cartella in cui è stato salvato lo script. Ad esempio, se è stato salvato a C:\PS-Scripts, eseguire il comando seguente.</br>
  `cd C:\PS-Scripts`

3. Eseguire il comando seguente per identificare il gruppo che si desidera visualizzare dettagli dispositivo per. In questo esempio vengono ottenuti i dettagli per gli utenti nel gruppo FinanceStaff.</br>
  ```
  $u = Get-MsolGroupMember -SearchString "FinanceStaff" | % { Get-MsolUser -ObjectId $_.ObjectId }
  ```

4. Eseguire il comando seguente per avviare lo script.</br>
  ```
  .\Get-MsolUserDeviceComplianceStatus.ps1 -User $u -Export
  ```

Vengono esportate le informazioni sul desktop di Windows come file CSV. È possibile utilizzare i parametri aggiuntivi per specificare il nome di file e il percorso del file CSV.
  
## <a name="more-info"></a>Altre informazioni

[Panoramica di MDM per Office 365](overview-of-mdm.md)
  
[Get-MsolDevice](https://go.microsoft.com/fwlink/?linkid=841721)
  

