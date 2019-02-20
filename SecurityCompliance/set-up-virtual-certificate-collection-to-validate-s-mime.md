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
# <a name="set-up-virtual-certificate-collection-to-validate-smime"></a><span data-ttu-id="d24ac-103">Configurazione della raccolta di certificati virtuali per convalidare S/MIME</span><span class="sxs-lookup"><span data-stu-id="d24ac-103">Set up virtual certificate collection to validate S/MIME</span></span>

<span data-ttu-id="d24ac-p101">Come amministratore tenant, l'utente dovrà configurare una raccolta di certificati virtuali che verranno utilizzati per convalidare i certificati S/MIME. La raccolta di certificati virtuali viene configurata come un tipo di file di archivio dei certificati con un'estensione del nome file SST. Il file SST contiene tutti i certificati radice e intermedi utilizzati durante la convalida del certificato S/MIME.</span><span class="sxs-lookup"><span data-stu-id="d24ac-p101">As a tenant administrator you will need to configure a virtual certificate collection that will be used to validate S/MIME certificates. This virtual certificate collection is set up as a certificate store file type with an SST filename extension. The SST file contains all the root and intermediate certificates that are used when validating an S/MIME certificate.</span></span>
  
## <a name="create-and-save-an-sst"></a><span data-ttu-id="d24ac-107">Creare e salvare un SST</span><span class="sxs-lookup"><span data-stu-id="d24ac-107">Create and save an SST</span></span>
<span data-ttu-id="d24ac-108"><a name="sectionSection0"> </a></span><span class="sxs-lookup"><span data-stu-id="d24ac-108"></span></span>

<span data-ttu-id="d24ac-p102">È possibile utilizzare Shell solo per eseguire questa procedura. Per informazioni su come aprire Exchange Management Shell nell'organizzazione di Exchange locale, vedere **Open the Shell**. Per informazioni su come utilizzare Windows PowerShell per la connessione a Exchange Online, vedere [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554).</span><span class="sxs-lookup"><span data-stu-id="d24ac-p102">You can only use the Shell to perform this procedure. To learn how to open the Exchange Management Shell in your on-premises Exchange organization, see **Open the Shell**. To learn how to use Windows PowerShell to connect to Exchange Online, see [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554).</span></span>
  
<span data-ttu-id="d24ac-p103">Come amministratore, è possibile creare questo file SST esportando i certificati da una macchina attendibile usando il cmdlet  `Export-Certificate` e specificando il tipo SST. Per ulteriori informazioni sul cmdlet  `Export-Certificate`, vedere l'argomento di riferimento sull'[esportazione dei certificati](https://docs.microsoft.com/en-us/powershell/module/pkiclient/export-certificate?view=win10-ps).</span><span class="sxs-lookup"><span data-stu-id="d24ac-p103">As an administrator, you can create this SST file by exporting the certificates from a trusted machine using the  `Export-Certificate` cmdlet and specifying the type as SST. For more information the  `Export-Certificate` cmdlet, see the [Export-Certificate](https://docs.microsoft.com/en-us/powershell/module/pkiclient/export-certificate?view=win10-ps) reference topic.</span></span> 
  
<span data-ttu-id="d24ac-p104">Una volta che il file SST viene generato, utilizzare il cmdlet  `Set-Smimeconfig` per salvarlo nell'archivio dei certificati virtuali utilizzando il parametro  _-SMIMECertificateIssuingCA_. Esempio:  `Set-SmimeConfig -SMIMECertificateIssuingCA (Get-Content filename.sst -Encoding Byte)`</span><span class="sxs-lookup"><span data-stu-id="d24ac-p104">Once the SST file is generated, use the  `Set-Smimeconfig` cmdlet to save it in the virtual certificate store by using the  _-SMIMECertificateIssuingCA_ parameter. For example:  `Set-SmimeConfig -SMIMECertificateIssuingCA (Get-Content filename.sst -Encoding Byte)`</span></span>
  
## <a name="ensuring-a-certificate-is-valid"></a><span data-ttu-id="d24ac-116">Assicurasi che un certificato sia valido</span><span class="sxs-lookup"><span data-stu-id="d24ac-116">Ensuring a certificate is valid</span></span>
<span data-ttu-id="d24ac-117"><a name="sectionSection1"> </a></span><span class="sxs-lookup"><span data-stu-id="d24ac-117"></span></span>

<span data-ttu-id="d24ac-p105">Exchange 2013 SP1 prima verifica il file SST e poi convalida il certificato. Se la convalida non riesce, controllerà l'archivio dei certificati della macchina locale per convalidare il certificato. Questo comportamento è nuovo per Exchange 2013 SP1 rispetto alle versioni precedenti di Exchange. In Exchange Online solo il SST verrà utilizzato per la convalida.</span><span class="sxs-lookup"><span data-stu-id="d24ac-p105">Exchange 2013 SP1 first checks for the SST file and validates the certificate. If the validation fails, it will look at the local machine certificate store to validate the certificate. This behavior is new for Exchange 2013 SP1 and different from prior versions of Exchange. In Exchange Online only the SST will be used for validation.</span></span>
  
## <a name="more-information"></a><span data-ttu-id="d24ac-122">Ulteriori informazioni</span><span class="sxs-lookup"><span data-stu-id="d24ac-122">More Information</span></span>
<span data-ttu-id="d24ac-123"><a name="sectionSection2"> </a></span><span class="sxs-lookup"><span data-stu-id="d24ac-123"></span></span>

[<span data-ttu-id="d24ac-124">S/MIME per la crittografia e firma dei messaggi</span><span class="sxs-lookup"><span data-stu-id="d24ac-124">S/MIME for message signing and encryption</span></span>](s-mime-for-message-signing-and-encryption.md)
  
[<span data-ttu-id="d24ac-125">Get-SmimeConfig</span><span class="sxs-lookup"><span data-stu-id="d24ac-125">Get-SmimeConfig</span></span>](http://technet.microsoft.com/library/4b29fa89-0840-4fe9-8885-019fcef2e02b.aspx)
  

