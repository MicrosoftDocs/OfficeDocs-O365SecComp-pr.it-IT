---
title: Information Rights Management in Exchange Online
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 12/13/2017
ms.audience: End User
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 2c956776-0016-4be6-b4cd-133a237f4a9e
description: Spesso si utilizza la posta elettronica per scambiare informazioni riservate, come ad esempio dati finanziari, contratti legali, informazioni riservate di prodotto, rapporti e proiezioni sulle vendite, informazioni sulla salute dei pazienti o informazioni relative ai clienti e agli impiegati. Di conseguenza, le cassette postali possono diventare archivi di grandi quantità di informazioni potenzialmente riservate e la fuga di informazioni può diventare una seria minaccia per l'organizzazione.
ms.openlocfilehash: 5036fe359215de1c2674d7efabbb283c78418a19
ms.sourcegitcommit: e9dca2d6a7838f98bb7eca127fdda2372cda402c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/21/2018
ms.locfileid: "23002569"
---
# <a name="information-rights-management-in-exchange-online"></a>Information Rights Management in Exchange Online

Spesso si utilizza la posta elettronica per scambiare informazioni riservate, come ad esempio dati finanziari, contratti legali, informazioni riservate di prodotto, rapporti e proiezioni sulle vendite, informazioni sulla salute dei pazienti o informazioni relative ai clienti e agli impiegati. Di conseguenza, le cassette postali possono diventare archivi di grandi quantità di informazioni potenzialmente riservate e la fuga di informazioni può diventare una seria minaccia per l'organizzazione.
  
Per aiutare ad impedire la fuga di informazioni, in Exchange Online è inclusa la funzionalità Information Rights Management (IRM) che fornisce una protezione online e offline dei messaggi di posta elettronica e degli allegati. La protezione IRM può essere applicata dagli utenti di Microsoft Outlook o Outlook sul web, nonché dagli amministratori utilizzando le regole di protezione del trasporto o le regole di protezione di Outlook. IRM consente agli utenti di controllare chi è autorizzato ad accedere, inoltrare, stampare o copiare dati riservati all'interno di un messaggio di posta elettronica.
  
## <a name="changes-to-how-irm-works-with-office-365-message-encryption-ome-and-azure-active-directory"></a>Modifiche al funzionamento di IRM con Crittografia messaggi di Office 365 (OME) e Azure Active Directory

A partire da settembre 2017, quando si configurano le nuove funzionalità di Crittografia messaggi di Office 365 per l'organizzazione, si configura anche IRM per l'utilizzo con Azure Rights Management (Azure RMS). IRM con Azure RMS non viene più configurato separatamente. Al contrario, OME e Rights Management sono perfettamente integrati. Per ulteriori dettagli sulle nuove funzionalità, vedere [Domande frequenti su Crittografia dei messaggi di Office 365Office 365 Message Encryption](https://support.office.com/article/0432dce9-d9b6-4e73-8a13-4a932eb0081e). Se si è pronti per iniziare a usare le nuove funzionalità OME all'interno dell'organizzazione, vedere [Configurare nuove funzionalità di Office 365 Message Encryption in Azure Information Protection](https://support.office.com/article/7ff0c040-b25c-4378-9904-b1b50210d00e).
  
## <a name="how-irm-works-with-exchange-online-and-active-directory-rights-management-services"></a>Funzionamento di IRM con Exchange Online e Active Directory Rights Management Services

IRM di Exchange Online utilizza Active Directory Rights Management Services (AD RMS) in locale, una tecnologia di protezione delle informazioni in Windows Server 2008 e versioni successive. La protezione IRM viene applicata alla posta elettronica applicando un modello dei criteri dei diritti AD RMS a un messaggio di posta elettronica. I diritti sono allegati al messaggio stesso, in modo che la protezione si verifichi online e offline e all'interno e all'esterno del firewall dell'organizzazione.
  
Gli utenti possono applicare un modello a un messaggio di posta elettronica per controllare le autorizzazioni di cui i destinatari dispongono per tale messaggio. È possibile controllare azioni quali l'inoltro, l'estrazione di informazioni da un messaggio, il salvataggio o la stampa di un messaggio applicando un modello dei criteri per i diritti AD RMS al messaggio.
  
È possibile configurare IRM per l'utilizzo di un server AD RMS che esegue Windows Server 2008 o versioni successive. Il server AD RMS può essere utilizzato per gestire i modelli dei criteri per i diritti AD RMS per l'organizzazione basata sul cloud. Outlook si basa anche sul server AD RMS per consentire agli utenti di applicare la protezione IRM ai messaggi da inviare. Per dettagli, vedere [Configure IRM to use an on-premises AD RMS server](configure-irm-to-use-an-on-premises-ad-rms-server.md).  
  
Una volta abilitata, la protezione IRM può essere applicata ai messaggi come riportato di seguito:
  
- **Gli utenti possono applicare manualmente un modello utilizzando Outlook e Outlook sul web.** Gli utenti possono applicare un modello dei criteri per i diritti AD RMS a un messaggio di posta elettronica selezionando il modello dall'elenco **Imposta autorizzazioni**. Quando gli utenti inviano un messaggio protetto con IRM, qualsiasi file allegato che utilizza un formato supportato riceverà la stessa protezione IRM del messaggio. La protezione IRM viene applicata ai file associati a Word, Excel e PowerPoint, così come ai file .xps e ai messaggi di posta elettronica allegati. 
    
- **Gli amministratori possono utilizzare le regole di protezione del trasporto per applicare la protezione IRM automaticamente a Outlook e Outlook sul web.** È possibile creare regole di protezione del trasporto per proteggere i messaggi mediante IRM. Configurare l'azione della regola di protezione del trasporto per applicare un modello dei criteri per i diritti AD RMS ai messaggi che soddisfano la condizione della regola. Dopo avere abilitato IRM, i modelli dei criteri per i diritti AD RMS dell'organizzazione sono disponibili per essere utilizzati con l'azione della regola di protezione del trasporto chiamata **Applica protezione dei diritti al messaggio con**.
    
- **Gli amministratori possono creare regole di protezione di Outlook.** Le regole di protezione di Outlook applicano automaticamente la protezione IRM ai messaggi in Outlook 2010 e non in Outlook sul web, in base alle condizioni del messaggio che includono il reparto del mittente, il destinatario del messaggio e se i destinatari si trovano all'interno o all'esterno dell'organizzazione. Per ulteriori informazioni, vedere [Create an Outlook Protection Rule](http://technet.microsoft.com/library/da64750d-faaf-44de-ad8c-888eba7fbdbf.aspx).
    

