---
title: Impostare una data di scadenza per la posta elettronica crittografata tramite la crittografia avanzata dei messaggi di Office 365
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 4/30/2019
ms.audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: f87cb016-7876-4317-ae3c-9169b311ff8a
description: Con le funzionalità di crittografia dei messaggi avanzate di Office 365 in cima a Office 365 Message Encryption (OME), è possibile estendere la sicurezza della posta elettronica impostando una data di scadenza nei messaggi di posta elettronica tramite un modello personalizzato.
ms.openlocfilehash: c1fb876724bed970095e950906500ff551d93cee
ms.sourcegitcommit: 8eb3cb4ec45ae0bb75fde249e35c4bc3d263b84f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/30/2019
ms.locfileid: "33506722"
---
# <a name="set-an-expiration-date-for-email-encrypted-by-office-365-advanced-message-encryption"></a><span data-ttu-id="aa42d-103">Impostare una data di scadenza per la posta elettronica crittografata tramite la crittografia avanzata dei messaggi di Office 365</span><span class="sxs-lookup"><span data-stu-id="aa42d-103">Set an expiration date for email encrypted by Office 365 Advanced Message Encryption</span></span>

<span data-ttu-id="aa42d-104">La crittografia avanzata dei messaggi di Office 365 è disponibile nella parte superiore della crittografia messaggi di Office 365 in alcuni abbonamenti.</span><span class="sxs-lookup"><span data-stu-id="aa42d-104">Office 365 Advanced Message Encryption is available on top of Office 365 Message Encryption in certain subscriptions.</span></span> <span data-ttu-id="aa42d-105">La crittografia avanzata dei messaggi è inclusa in [Microsoft 365 Enterprise E5](https://www.microsoft.com/microsoft-365/enterprise/home), Office 365 Enterprise E5 e Office 365 Education a5.</span><span class="sxs-lookup"><span data-stu-id="aa42d-105">Advanced Message Encryption is included in [Microsoft 365 Enterprise E5](https://www.microsoft.com/microsoft-365/enterprise/home), Office 365 Enterprise E5, and Office 365 Education A5.</span></span> <span data-ttu-id="aa42d-106">Se nell'organizzazione è presente un abbonamento a Office 365 che non include la crittografia avanzata dei messaggi di Office 365, è possibile acquistare la crittografia avanzata del messaggio come componente aggiuntivo con la conformità E5 della SKU per la conformità avanzata.</span><span class="sxs-lookup"><span data-stu-id="aa42d-106">If your organization has an Office 365 subscription that does not include Office 365 Advanced Message Encryption, you can purchase Advanced Message Encryption as an add-on with E5 Compliance of the Advanced Compliance SKU.</span></span>

<span data-ttu-id="aa42d-107">È possibile utilizzare la scadenza dei messaggi nei messaggi di posta elettronica inviati dagli utenti ai destinatari esterni che utilizzano il portale OME per accedere ai messaggi di posta elettronica crittografati.</span><span class="sxs-lookup"><span data-stu-id="aa42d-107">You can use message expiration on emails that your users send to external recipients who use the OME Portal to access encrypted emails.</span></span> <span data-ttu-id="aa42d-108">È possibile forzare i destinatari a utilizzare il portale OME per visualizzare e rispondere ai messaggi di posta elettronica crittografati inviati dall'organizzazione utilizzando un modello personalizzato che specifichi una data di scadenza in Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="aa42d-108">You force recipients to use the OME portal to view and reply to encrypted emails sent by your organization by using a custom branded template that specifies an expiration date in Windows Powershell.</span></span>

<span data-ttu-id="aa42d-109">In qualità di amministratore globale di O365, quando si applica il marchio dell'azienda per personalizzare l'aspetto dei messaggi di posta elettronica dell'organizzazione di Office 365, è anche possibile specificare una scadenza per questi messaggi di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="aa42d-109">As an O365 global administrator, when you apply your company branding to customize the look of your Office 365 organization's email messages, you can also specify an expiration for these email messages.</span></span> <span data-ttu-id="aa42d-110">Con la crittografia avanzata dei messaggi di Office 365, è possibile creare più modelli per i messaggi di posta elettronica crittografati provenienti dall'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="aa42d-110">With Office 365 Advanced Message Encryption, you can create multiple templates for encrypted emails originating from your organization.</span></span> <span data-ttu-id="aa42d-111">Se si utilizza un modello, è possibile controllare la durata di accesso dei destinatari alla posta inviata dagli utenti.</span><span class="sxs-lookup"><span data-stu-id="aa42d-111">Using a template, you can control how long recipients have access to mail sent by your users.</span></span>

<span data-ttu-id="aa42d-112">Quando un utente finale riceve la posta con un set di date di scadenza, l'utente Visualizza la data di scadenza nel messaggio di posta elettronica del wrapper.</span><span class="sxs-lookup"><span data-stu-id="aa42d-112">When an end user receives mail that has an expiration date set, the user sees the expiration date in the wrapper email.</span></span> <span data-ttu-id="aa42d-113">Se un utente tenta di aprire un messaggio di posta elettronica scaduto, viene visualizzato un messaggio di errore nel portale OME.</span><span class="sxs-lookup"><span data-stu-id="aa42d-113">If a user tries to open an expired mail, an error appears in the OME portal.</span></span>

<span data-ttu-id="aa42d-114">Solo i messaggi di posta elettronica ai destinatari esterni sono scaduti.</span><span class="sxs-lookup"><span data-stu-id="aa42d-114">Only emails to external recipients are expirable.</span></span>

<span data-ttu-id="aa42d-115">Grazie alla crittografia avanzata dei messaggi di Office 365, ogni volta che si applica il marchio personalizzato, Office 365 applica il wrapper alla posta elettronica adatta alla regola del flusso di posta a cui viene applicato il modello.</span><span class="sxs-lookup"><span data-stu-id="aa42d-115">With Office 365 Advanced Message Encryption, any time you apply custom branding, the Office 365 applies the wrapper to email that fits the mail flow rule to which you apply the template.</span></span> <span data-ttu-id="aa42d-116">Inoltre, la scadenza può essere utilizzata solo se viene utilizzato il marchio personalizzato.</span><span class="sxs-lookup"><span data-stu-id="aa42d-116">In addition, expiration can only be used if custom branding is used.</span></span>

## <a name="create-a-custom-branding-template-to-force-mail-expiration-by-using-powershell"></a><span data-ttu-id="aa42d-117">Creare un modello di personalizzazione personalizzato per forzare la scadenza della posta tramite PowerShell</span><span class="sxs-lookup"><span data-stu-id="aa42d-117">Create a custom branding template to force mail expiration by using PowerShell</span></span>

1. <span data-ttu-id="aa42d-118">[Connettersi a PowerShell di Exchange Online](https://docs.microsoft.com/en-us/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell) utilizzando un account con autorizzazioni di amministratore globale nel tenant di Office 365.</span><span class="sxs-lookup"><span data-stu-id="aa42d-118">[Connect to Exchange Online PowerShell](https://docs.microsoft.com/en-us/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell) using an account with global administrator permissions in your Office 365 tenant.</span></span>

2. <span data-ttu-id="aa42d-119">Eseguire il cmdlet New-OMEConfiguration.</span><span class="sxs-lookup"><span data-stu-id="aa42d-119">Run the New-OMEConfiguration cmdlet.</span></span>

     ```powershell
     New-OMEConfiguration -Identity "Expire in 7 days" ExternalMailExpiryInDays 7
     ```

<span data-ttu-id="aa42d-120">Dove:</span><span class="sxs-lookup"><span data-stu-id="aa42d-120">Where:</span></span>

- <span data-ttu-id="aa42d-121">Identity è il nome del modello personalizzato.</span><span class="sxs-lookup"><span data-stu-id="aa42d-121">Identity is the name of the custom template.</span></span>

- <span data-ttu-id="aa42d-122">ExternalMailExpiryInDays identifica il numero di giorni in cui si desidera che i destinatari siano in grado di mantenere la posta prima della scadenza.</span><span class="sxs-lookup"><span data-stu-id="aa42d-122">ExternalMailExpiryInDays identifies the number of days you want recipients to be able to keep mail before it expires.</span></span> <span data-ttu-id="aa42d-123">È possibile utilizzare qualsiasi valore compreso tra 1 e 730 giorni.</span><span class="sxs-lookup"><span data-stu-id="aa42d-123">You can use any value between 1 to 730 days.</span></span>

## <a name="more-information-about-office-365-advanced-message-encryption"></a><span data-ttu-id="aa42d-124">Ulteriori informazioni sulla crittografia avanzata dei messaggi di Office 365</span><span class="sxs-lookup"><span data-stu-id="aa42d-124">More information about Office 365 Advanced Message Encryption</span></span>

- [<span data-ttu-id="aa42d-125">Crittografia avanzata dei messaggi di Office 365</span><span class="sxs-lookup"><span data-stu-id="aa42d-125">Office 365 Advanced Message Encryption</span></span>](ome-advanced-message-encryption.md)

- [<span data-ttu-id="aa42d-126">Revoca dei messaggi di posta elettronica crittografati da Office 365 Advanced Message Encryption</span><span class="sxs-lookup"><span data-stu-id="aa42d-126">Revoke email encrypted by Office 365 Advanced Message Encryption</span></span>](revoke-ome-encrypted-mail.md)

- [<span data-ttu-id="aa42d-127">Descrizione del servizio criteri di conformità e del messaggio</span><span class="sxs-lookup"><span data-stu-id="aa42d-127">Message policy and compliance service description</span></span>](https://docs.microsoft.com/en-us/office365/servicedescriptions/exchange-online-service-description/message-policy-and-compliance)