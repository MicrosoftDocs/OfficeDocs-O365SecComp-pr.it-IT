---
title: Gestione di destinatari in EOP
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 11/17/2014
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
ms.assetid: 2921f544-8257-4bae-8e3a-ce9250e9f162
description: Microsoft Exchange Online Protection (EOP) offre diversi modi per gestire i destinatari della posta. Come amministratore, è possibile effettuare alcune attività di gestione all'interno dell'interfaccia di amministrazione di Exchange (EAC) o utilizzando Windows PowerShell remoto, quindi verificare altre attività di gestione eseguite nell'interfaccia di amministrazione di Microsoft Office 365.
ms.openlocfilehash: 55b28dcb107df85052ff623f653eecaaf88c7bda
ms.sourcegitcommit: 48fa456981b5c52ab8aeace173c8366b9f36723b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/28/2019
ms.locfileid: "30341657"
---
# <a name="manage-recipients-in-eop"></a><span data-ttu-id="b4a37-104">Gestione di destinatari in EOP</span><span class="sxs-lookup"><span data-stu-id="b4a37-104">Manage recipients in EOP</span></span>

<span data-ttu-id="b4a37-p102">Microsoft Exchange Online Protection (EOP) offre diversi modi per gestire i destinatari della posta. Come amministratore, è possibile effettuare alcune attività di gestione all'interno dell'interfaccia di amministrazione di Exchange (EAC) o utilizzando Windows PowerShell remoto, quindi verificare altre attività di gestione eseguite nell'interfaccia di amministrazione di Microsoft Office 365.</span><span class="sxs-lookup"><span data-stu-id="b4a37-p102">Microsoft Exchange Online Protection (EOP) offers several ways to manage your mail recipients. As an administrator, you can perform certain management tasks within the Exchange admin center (EAC) or using remote Windows PowerShell, and verify other management tasks performed in the Microsoft Office 365 admin center.</span></span>
  
<span data-ttu-id="b4a37-107">EOP supporta i seguenti tipi di destinatari:</span><span class="sxs-lookup"><span data-stu-id="b4a37-107">EOP supports the following types of recipients:</span></span>
  
- <span data-ttu-id="b4a37-p103">**Utenti di posta elettronica** Gli utenti di posta elettronica sono destinatari nei domini gestiti di EOP. Questi destinatari dispongono di credenziali di accesso nella propria organizzazione di Office 365, ma dispongono di indirizzi di posta elettronica esterni, ovvero le cassette postali dei destinatari sono situate all'esterno dell'organizzazione cloud. È possibile aggiungere utenti di posta elettronica in modo che possano ricevere messaggi di posta elettronica ed è anche possibile creare regole del flusso di posta (note anche come regole di trasporto) per utenti specifici. È inoltre possibile assegnare ruoli agli utenti di posta elettronica nell'organizzazione. Gli utenti con privilegi del gruppo di ruoli di gestione possono accedere all'interfaccia di amministrazione di Exchange (EAC) ed eseguire determinate attività di gestione. Per ulteriori informazioni sui ruoli utente e sulla modalità di assegnazione dei ruoli utente in EOP, vedere [Manage admin Group Role Permissions in EOP](manage-admin-role-group-permissions-in-eop.md).</span><span class="sxs-lookup"><span data-stu-id="b4a37-p103">**Mail Users** Mail users are recipients in your EOP managed domains. These recipients have logon credentials in your Office 365 organization, but they have external email addresses, meaning that their recipient mailboxes are located outside of your cloud organization. You can add mail users so that they can receive mail and you can also create mail flow rules (also known as transport rules) for specific users. You can also assign roles to mail users in your organization; users with management role group privileges can access the Exchange admin center (EAC) and perform certain management tasks. To learn more about user roles and how to assign user roles in EOP, see [Manage admin role group permissions in EOP](manage-admin-role-group-permissions-in-eop.md).</span></span>
    
    <span data-ttu-id="b4a37-113">Per ulteriori informazioni sulla gestione degli utenti di posta elettronica in EOP, vedere [Gestione utenti di posta in EOP](manage-mail-users-in-eop.md).</span><span class="sxs-lookup"><span data-stu-id="b4a37-113">For more information about managing mail users in EOP, see [Manage mail users in EOP](manage-mail-users-in-eop.md).</span></span>
    
- <span data-ttu-id="b4a37-114">**Gruppi** Gli utenti di posta elettronica possono essere raggruppati in gruppi di distribuzione o gruppi di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="b4a37-114">**Groups** Mail users can be grouped together into distribution groups or security groups.</span></span> 
    
    <span data-ttu-id="b4a37-115">Per ulteriori informazioni sulla gestione dei gruppi in EOP, vedere [Gestione di gruppi in EOP](manage-groups-in-eop.md).</span><span class="sxs-lookup"><span data-stu-id="b4a37-115">For more information about managing groups in EOP, see [Manage groups in EOP](manage-groups-in-eop.md).</span></span>
    
<span data-ttu-id="b4a37-p104">Per la ricerca della versione di Exchange Online in questo argomento, vedere [Recipients in Exchange Online](http://technet.microsoft.com/library/50d16941-5cd7-435d-8715-e2b69f8410ab.aspx).</span><span class="sxs-lookup"><span data-stu-id="b4a37-p104">Looking for the Exchange Online version of this topic? See [Recipients in Exchange Online](http://technet.microsoft.com/library/50d16941-5cd7-435d-8715-e2b69f8410ab.aspx).</span></span>
  
<span data-ttu-id="b4a37-p105">Per la ricerca della versione di Exchange Server in questo argomento, vedere [Recipients](http://technet.microsoft.com/library/40300ed4-85a5-463d-bb3a-cf787bd44e9d.aspx).</span><span class="sxs-lookup"><span data-stu-id="b4a37-p105">Looking for the Exchange Server version of this topic? See [Recipients](http://technet.microsoft.com/library/40300ed4-85a5-463d-bb3a-cf787bd44e9d.aspx).</span></span>
  

