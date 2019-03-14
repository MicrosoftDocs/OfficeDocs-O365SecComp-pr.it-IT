---
title: Configurare le impostazioni S/MIME in Exchange Online per Outlook sul Web
ms.author: chrisda
author: chrisda
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: c7dee22c-9b5b-425c-91a9-d093204ff84e
ms.collection:
- M365-security-compliance
description: Una breve descrizione di cosa devono fare gli amministratori di Exchange Online per visualizzare e configurare le impostazioni S/MIME in Outlook sul Web in Exchange Online.
ms.openlocfilehash: 005c3075ec8fe6255231ba7358e5b4cc22b92f1d
ms.sourcegitcommit: 8b36bf7949f1769f1418d740293637d60e403f87
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/28/2019
ms.locfileid: "30339444"
---
# <a name="configure-smime-settings-in-exchange-online-for-outlook-on-the-web"></a><span data-ttu-id="bf678-103">Configurare le impostazioni S/MIME in Exchange Online per Outlook sul Web</span><span class="sxs-lookup"><span data-stu-id="bf678-103">Configure S/MIME settings in Exchange Online for Outlook on the web</span></span>

<span data-ttu-id="bf678-104">In qualità di amministratore di Exchange Online, è possibile configurare Outlook sul Web (in precedenza noto come Outlook Web App) per consentire l'invio e la ricezione di messaggi protetti con S/MIME.</span><span class="sxs-lookup"><span data-stu-id="bf678-104">As an admin for Exchange Online, you can set up Outlook on the web (formerly known as Outlook Web App) to allow sending and receiving S/MIME-protected messages.</span></span> <span data-ttu-id="bf678-105">Utilizzare i cmdlet **Get-SmimeConfig** e **set-SmimeConfig** per visualizzare e gestire questa funzionalità in PowerShell di Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="bf678-105">Use the **Get-SmimeConfig** and **Set-SmimeConfig** cmdlets to view and manage this feature in Exchange Online PowerShell.</span></span> <span data-ttu-id="bf678-106">Per connettersi a PowerShell di Exchange Online, vedere [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554).</span><span class="sxs-lookup"><span data-stu-id="bf678-106">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554).</span></span>

<span data-ttu-id="bf678-107">Per informazioni dettagliate sulla sintassi e sui parametri, vedere [Get-SmimeConfig](http://technet.microsoft.com/library/4b29fa89-0840-4fe9-8885-019fcef2e02b.aspx) e [set-SmimeConfig](http://technet.microsoft.com/library/de357ce0-8143-4c36-8032-026292fc63f0.aspx).</span><span class="sxs-lookup"><span data-stu-id="bf678-107">For detailed syntax and parameter information, see [Get-SmimeConfig](http://technet.microsoft.com/library/4b29fa89-0840-4fe9-8885-019fcef2e02b.aspx) and [Set-SmimeConfig](http://technet.microsoft.com/library/de357ce0-8143-4c36-8032-026292fc63f0.aspx).</span></span>

## <a name="considerations-for-chrome"></a><span data-ttu-id="bf678-108">Considerazioni su Chrome</span><span class="sxs-lookup"><span data-stu-id="bf678-108">Considerations for Chrome</span></span>

<span data-ttu-id="bf678-109">Per utilizzare S/MIME in Outlook sul Web nel browser Web di Google Chrome, è necessario che l'utente (o un altro amministratore) debba impostare e configurare il criterio di cromo denominato **ExtensionInstallForcelist** per installare l'estensione Microsoft S/MIME in Chrome.</span><span class="sxs-lookup"><span data-stu-id="bf678-109">To use S/MIME in Outlook on the web in the Google Chrome web browser, you (or another admin) must set and configure the Chromium policy named **ExtensionInstallForcelist** to install the Microsoft S/MIME extension in Chrome.</span></span> <span data-ttu-id="bf678-110">Il criterio deve utilizzare la sintassi: `<extension-id>;https://outlook.office.com/owa/SmimeCrxUpdate.ashx` ad esempio: `maafgiompdekodanheihhgilkjchcakm;https://outlook.office.com/owa/SmimeCrxUpdate.ashx`.</span><span class="sxs-lookup"><span data-stu-id="bf678-110">The policy should use the syntax: `<extension-id>;https://outlook.office.com/owa/SmimeCrxUpdate.ashx` For example: `maafgiompdekodanheihhgilkjchcakm;https://outlook.office.com/owa/SmimeCrxUpdate.ashx`.</span></span> <span data-ttu-id="bf678-111">Si noti che l'applicazione di questo criterio richiede I computer aggiunti a un dominio, in modo che l'utilizzo di S/MIME in Chrome richiede effettivamente I computer aggiunti a un dominio.</span><span class="sxs-lookup"><span data-stu-id="bf678-111">And note that applying this policy requires domain-joined computers, so using S/MIME in Chrome effectively requires domain-joined computers.</span></span>

<span data-ttu-id="bf678-112">Questo passaggio è un prerequisito per l'utilizzo di Chrome. non sostituisce il controllo S/MIME installato dagli utenti.</span><span class="sxs-lookup"><span data-stu-id="bf678-112">This step is a prerequisite for using Chrome; it does not replace the S/MIME control that's installed by users.</span></span> <span data-ttu-id="bf678-113">Per informazioni dettagliate sul criterio **ExtensionInstallForcelist** , vedere [ExtensionInstallForcelist](http://dev.chromium.org/administrators/policy-list-3#ExtensionInstallForcelist).</span><span class="sxs-lookup"><span data-stu-id="bf678-113">For details about the **ExtensionInstallForcelist** policy, see [ExtensionInstallForcelist](http://dev.chromium.org/administrators/policy-list-3#ExtensionInstallForcelist).</span></span>

## <a name="for-more-information"></a><span data-ttu-id="bf678-114">Ulteriori informazioni</span><span class="sxs-lookup"><span data-stu-id="bf678-114">For more information</span></span>

[<span data-ttu-id="bf678-115">S/MIME per la crittografia e firma dei messaggi</span><span class="sxs-lookup"><span data-stu-id="bf678-115">S/MIME for message signing and encryption</span></span>](s-mime-for-message-signing-and-encryption.md)
