---
title: Sincronizzare i certificati dell'utente con Office 365 per S/MIME
ms.author: chrisda
author: chrisda
manager: Serdars
ms.date: 12/9/2016
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 351c932e-99c1-4512-a6e8-788e90b7838f
description: Prima che chiunque possa inviare messaggi protetti con S/MIME, è necessario configurare i certificati appropriati. Per inviare messaggi crittografati tramite Exchange Online, il programma di posta elettronica del mittente utilizza il certificato pubblico del destinatario per crittografare il messaggio. Il certificato X.509 pubblico deve essere pubblicato in Office 365.
ms.openlocfilehash: 35de3ba34be48a8553c7034f646576e4fca8b870
ms.sourcegitcommit: baf23be44f1ed5abbf84f140b5ffa64fce605478
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/26/2019
ms.locfileid: "30294999"
---
# <a name="sync-user-certificates-to-office-365-for-smime"></a><span data-ttu-id="8ab08-105">Sincronizzare i certificati dell'utente con Office 365 per S/MIME</span><span class="sxs-lookup"><span data-stu-id="8ab08-105">Sync user certificates to Office 365 for S/MIME</span></span>

<span data-ttu-id="8ab08-p102">Prima che chiunque possa inviare messaggi protetti con S/MIME in Exchange Online, è necessario configurare i certificati corretti. Per inviare messaggi crittografati tramite Exchange Online, l'app di posta elettronica del mittente utilizza il certificato pubblico del destinatario per crittografare il messaggio. Questo certificato X. 509 pubblico deve essere pubblicato in Office 365.</span><span class="sxs-lookup"><span data-stu-id="8ab08-p102">Before anyone can send S/MIME-protected messages in Exchange Online, the appropriate certificates must be set up. To send encrypted messages through Exchange Online, the sender's email app uses the public certificate of the recipient to encrypt the message. This public X.509 certificate has to be published to Office 365.</span></span>

## <a name="to-sync-certificates-that-support-smime"></a><span data-ttu-id="8ab08-109">Per sincronizzare i certificati che supportano S/MIME</span><span class="sxs-lookup"><span data-stu-id="8ab08-109">To Sync certificates that support S/MIME</span></span>

<span data-ttu-id="8ab08-p103">Iniziare la configurazione di S/MIME emettendo I certificati e pubblicarli nel servizio di dominio Active Directory locale. Per ulteriori informazioni sulla gestione dei certificati in Exchange Server, vedere [Digital certificates and SSL](http://technet.microsoft.com/library/a9e2e08c-d46a-4135-a387-eb653212b676.aspx).</span><span class="sxs-lookup"><span data-stu-id="8ab08-p103">Begin setting up S/MIME by issuing certificates and publishing them in your local Active Directory Domain Service. For more information about managing certificates in Exchange Server, see [Digital Certificates and SSL](http://technet.microsoft.com/library/a9e2e08c-d46a-4135-a387-eb653212b676.aspx).</span></span>

<span data-ttu-id="8ab08-p104">Dopo la pubblicazione dei certificati, utilizzare lo strumento di sincronizzazione di Azure Active Directory per sincronizzare i dati degli utenti dall'ambiente di Exchange locale a Office 365. Per ulteriori informazioni su questo processo, vedere [DirSync: Directory Sync Tool version Release History](https://go.microsoft.com/fwlink/p/?LinkId=392587).</span><span class="sxs-lookup"><span data-stu-id="8ab08-p104">After your certificates are published, use the Azure Active Directory Sync tool to synchronize user data from your on-premises Exchange environment to Office 365. For more information on this process, see [DirSync: Directory Sync Tool Version Release History](https://go.microsoft.com/fwlink/p/?LinkId=392587).</span></span>

<span data-ttu-id="8ab08-114">Insieme alla sincronizzazione di altri dati di directory, per scopi S/MIME, lo strumento Sincronizza gli attributi **userCertificate** e **userSMIMECertificate** per ogni oggetto utente in modo che i dati possano essere utilizzati per firmare e crittografare i messaggi.</span><span class="sxs-lookup"><span data-stu-id="8ab08-114">Along with synchronizing other directory data, for S/MIME purposes, the tool will synchronize the  **userCertificate** and **userSMIMECertificate** attributes for each user object so the data can be used to sign and encrypt messages.</span></span>

## <a name="more-information"></a><span data-ttu-id="8ab08-115">Ulteriori informazioni</span><span class="sxs-lookup"><span data-stu-id="8ab08-115">More Information</span></span>

[<span data-ttu-id="8ab08-116">S/MIME per la crittografia e firma dei messaggi</span><span class="sxs-lookup"><span data-stu-id="8ab08-116">S/MIME for message signing and encryption</span></span>](s-mime-for-message-signing-and-encryption.md)

[<span data-ttu-id="8ab08-117">strumento di sincronizzazione di Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="8ab08-117">Azure Active Directory Sync tool</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=392587)
