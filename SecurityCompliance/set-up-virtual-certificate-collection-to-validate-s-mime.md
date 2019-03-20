---
title: Configurare la raccolta di certificati virtuali in Exchange Online per convalidare S/MIME
ms.author: chrisda
author: chrisda
manager: serdars
ms.date: ''
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 04a616e6-197c-490c-ae8c-c8d5f0f0b3dd
description: Gli amministratori possono ottenere informazioni su come creare una raccolta di certificati virtuali che verrà utilizzata per convalidare I certificati S/MIME in Exchange Online.
ms.openlocfilehash: 15998bce1971952286d8dd4401a92f1e9e47c25d
ms.sourcegitcommit: 0f93b37c39d807dec91f118aa671a3430c47a9ac
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/20/2019
ms.locfileid: "30693555"
---
# <a name="set-up-virtual-certificate-collection-in-exchange-online-to-validate-smime"></a><span data-ttu-id="8d658-103">Configurare la raccolta di certificati virtuali in Exchange Online per convalidare S/MIME</span><span class="sxs-lookup"><span data-stu-id="8d658-103">Set up virtual certificate collection in Exchange Online to validate S/MIME</span></span>

<span data-ttu-id="8d658-104">Come amministratore, sarà necessario configurare una raccolta di certificati virtuali in Exchange Online che verrà utilizzata per convalidare I certificati S/MIME.</span><span class="sxs-lookup"><span data-stu-id="8d658-104">As an admin, you will need to configure a virtual certificate collection in Exchange Online that will be used to validate S/MIME certificates.</span></span> <span data-ttu-id="8d658-105">Questa raccolta di certificati virtuali è configurata come archivio certificati con estensione del nome di file SST.</span><span class="sxs-lookup"><span data-stu-id="8d658-105">This virtual certificate collection is set up as a certificate store with an SST filename extension.</span></span> <span data-ttu-id="8d658-106">Il file SST contiene tutti i certificati radice e intermedi utilizzati durante la convalida del certificato S/MIME.</span><span class="sxs-lookup"><span data-stu-id="8d658-106">The SST file contains all the root and intermediate certificates that are used when validating an S/MIME certificate.</span></span>

## <a name="create-and-save-an-sst"></a><span data-ttu-id="8d658-107">Creare e salvare un SST</span><span class="sxs-lookup"><span data-stu-id="8d658-107">Create and save an SST</span></span>

<span data-ttu-id="8d658-108">È possibile creare questo file dell'archivio certificati SST esportando i certificati da un computer attendibile utilizzando il cmdlet **Export-Certificate** in Windows PowerShell e specificando il valore _Type_ come SST.</span><span class="sxs-lookup"><span data-stu-id="8d658-108">You can create this SST certificate store file by exporting the certificates from a trusted machine using the **Export-Certificate** cmdlet in Windows PowerShell and specifying the _Type_ value as SST.</span></span> <span data-ttu-id="8d658-109">Per istruzioni, vedere [Export-Certificate](https://docs.microsoft.com/powershell/module/pkiclient/export-certificate).</span><span class="sxs-lookup"><span data-stu-id="8d658-109">For instructions, see [Export-Certificate](https://docs.microsoft.com/powershell/module/pkiclient/export-certificate).</span></span>

<span data-ttu-id="8d658-110">Dopo aver utilizzato il file dell'archivio certificati SST, utilizzare la sintassi seguente in Exchange Online PowerShell per salvare il contenuto del file SST nell'archivio certificati virtuale di Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="8d658-110">Once you have the SST certificate store file, use the following syntax in Exchange Online PowerShell to save the SST file contents in the Exchange Online virtual certificate store.</span></span> <span data-ttu-id="8d658-111">Per connettersi a PowerShell di Exchange Online, vedere [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554).</span><span class="sxs-lookup"><span data-stu-id="8d658-111">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554).</span></span>

```
Set-SmimeConfig -SMIMECertificateIssuingCA (Get-Content <FileNameAndPath>.sst -Encoding Byte)
```

<span data-ttu-id="8d658-112">In questo esempio viene importato il file SST C:\My Documents\exported Rules Certificate Store. SST.</span><span class="sxs-lookup"><span data-stu-id="8d658-112">This example imports the SST file C:\My Documents\Exported Certificate Store.sst.</span></span>

```
Set-SmimeConfig -SMIMECertificateIssuingCA (Get-Content "C:\My Documents\Exported Certificate Store.sst" -Encoding Byte)
```

<span data-ttu-id="8d658-113">Per informazioni dettagliate sulla sintassi e sui parametri, vedere [set-SmimeConfig](https://docs.microsoft.com/en-us/powershell/module/exchange/encryption-and-certificates/set-smimeconfig).</span><span class="sxs-lookup"><span data-stu-id="8d658-113">For detailed syntax and parameter information, see [Set-SmimeConfig](https://docs.microsoft.com/en-us/powershell/module/exchange/encryption-and-certificates/set-smimeconfig).</span></span>

## <a name="ensuring-a-certificate-is-valid"></a><span data-ttu-id="8d658-114">Assicurasi che un certificato sia valido</span><span class="sxs-lookup"><span data-stu-id="8d658-114">Ensuring a certificate is valid</span></span>

<span data-ttu-id="8d658-115">In Exchange Online, viene utilizzato solo lo SST per la convalida dei certificati.</span><span class="sxs-lookup"><span data-stu-id="8d658-115">In Exchange Online, only the SST is used for certificate validation.</span></span>

## <a name="more-information"></a><span data-ttu-id="8d658-116">Ulteriori informazioni</span><span class="sxs-lookup"><span data-stu-id="8d658-116">More Information</span></span>

[<span data-ttu-id="8d658-117">S/MIME per la crittografia e firma dei messaggi</span><span class="sxs-lookup"><span data-stu-id="8d658-117">S/MIME for message signing and encryption</span></span>](s-mime-for-message-signing-and-encryption.md)

[<span data-ttu-id="8d658-118">Get-SmimeConfig</span><span class="sxs-lookup"><span data-stu-id="8d658-118">Get-SmimeConfig</span></span>](http://technet.microsoft.com/library/4b29fa89-0840-4fe9-8885-019fcef2e02b.aspx)
