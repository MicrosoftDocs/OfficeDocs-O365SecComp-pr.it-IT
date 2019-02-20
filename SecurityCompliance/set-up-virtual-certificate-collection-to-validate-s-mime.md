---
title: Configurazione della raccolta di certificati virtuali per convalidare S/MIME
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 12/9/2016
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 04a616e6-197c-490c-ae8c-c8d5f0f0b3dd
description: s un amministratore tenant sarà necessario configurare una raccolta di certificati virtuali che verrà utilizzata per convalidare I certificati S/MIME.
ms.openlocfilehash: 0e8226ca35e872cd8c7da16ba353bf8b99a6954d
ms.sourcegitcommit: c94cb88a9ce5bcc2d3c558f0fcc648519cc264a2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/20/2019
ms.locfileid: "30091058"
---
# <a name="set-up-virtual-certificate-collection-to-validate-smime"></a>Configurazione della raccolta di certificati virtuali per convalidare S/MIME

Come amministratore tenant, l'utente dovrà configurare una raccolta di certificati virtuali che verranno utilizzati per convalidare i certificati S/MIME. La raccolta di certificati virtuali viene configurata come un tipo di file di archivio dei certificati con un'estensione del nome file SST. Il file SST contiene tutti i certificati radice e intermedi utilizzati durante la convalida del certificato S/MIME.
  
## <a name="create-and-save-an-sst"></a>Creare e salvare un SST
<a name="sectionSection0"> </a>

È possibile utilizzare Shell solo per eseguire questa procedura. Per informazioni su come aprire Exchange Management Shell nell'organizzazione di Exchange locale, vedere **Open the Shell**. Per informazioni su come utilizzare Windows PowerShell per la connessione a Exchange Online, vedere [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554).
  
Come amministratore, è possibile creare questo file SST esportando i certificati da una macchina attendibile usando il cmdlet  `Export-Certificate` e specificando il tipo SST. Per ulteriori informazioni sul cmdlet  `Export-Certificate`, vedere l'argomento di riferimento sull'[esportazione dei certificati](https://docs.microsoft.com/en-us/powershell/module/pkiclient/export-certificate?view=win10-ps). 
  
Una volta che il file SST viene generato, utilizzare il cmdlet  `Set-Smimeconfig` per salvarlo nell'archivio dei certificati virtuali utilizzando il parametro  _-SMIMECertificateIssuingCA_. Esempio:  `Set-SmimeConfig -SMIMECertificateIssuingCA (Get-Content filename.sst -Encoding Byte)`
  
## <a name="ensuring-a-certificate-is-valid"></a>Assicurasi che un certificato sia valido
<a name="sectionSection1"> </a>

Exchange 2013 SP1 prima verifica il file SST e poi convalida il certificato. Se la convalida non riesce, controllerà l'archivio dei certificati della macchina locale per convalidare il certificato. Questo comportamento è nuovo per Exchange 2013 SP1 rispetto alle versioni precedenti di Exchange. In Exchange Online solo il SST verrà utilizzato per la convalida.
  
## <a name="more-information"></a>Ulteriori informazioni
<a name="sectionSection2"> </a>

[S/MIME per la crittografia e firma dei messaggi](s-mime-for-message-signing-and-encryption.md)
  
[Get-SmimeConfig](http://technet.microsoft.com/library/4b29fa89-0840-4fe9-8885-019fcef2e02b.aspx)
  

