---
title: Come viene garantita la protezione della posta elettronica in Exchange Online
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.date: 5/24/2018
ms.audience: ITPro
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 989ba10c-f73f-4efb-ad1b-af3322e5f376
ms.collection:
- M365-security-compliance
description: Oltre al Centro protezione di Office 365 che fornisce informazioni sulla sicurezza, la privacy e la conformità per Office 365, è possibile che si desideri sapere in che modo Office 365 consente di proteggere i segreti forniti nei propri datacenter. Viene utilizzata una tecnologia denominata Distributed Key Manager (DKM).
ms.openlocfilehash: ba4c661899273f5e07c2468631298f5500d0e32f
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/23/2019
ms.locfileid: "30218076"
---
# <a name="how-exchange-online-secures-your-email-secrets"></a>Come viene garantita la protezione della posta elettronica in Exchange Online

In questo articolo viene descritto come Microsoft garantisce la protezione della posta elettronica degli utenti nei datacenter.
  
## <a name="how-do-we-secure-secret-information-provided-by-you"></a>Come vengono protette le informazioni riservate fornite dall'utente?

Oltre al Centro protezione di Office 365 che fornisce [informazioni sulla sicurezza, la privacy e la conformità per office 365](https://go.microsoft.com/fwlink/?linkid=874644), è possibile che si desideri sapere in che modo Office 365 consente di proteggere i segreti forniti nei propri datacenter. Viene utilizzata una tecnologia denominata Distributed Key Manager (DKM).
  
Si tratta di una funzionalità lato client che usa un set di chiavi segrete per crittografare e decrittografare le informazioni. Solo i membri di un gruppo di sicurezza specifico in Servizi di dominio Active Directory possono accedere a tali chiavi per decrittografare i dati crittografati da DKM. In Exchange Online, fanno parte di quel determinato gruppo di sicurezza solo determinati account di servizio nei quali sono in esecuzione i processi di Exchange. Nell'ambito della procedura operativa standard nel datacenter, le credenziali che fanno parte del gruppo di sicurezza non vengono fornite a nessuno; pertanto, nessuno ha accesso alle chiavi in grado di decrittografare le informazioni riservate.
  
Per scopi legati al debug, alla risoluzione dei problemi o al controllo, è necessario che l'amministratore di un datacenter richieda un accesso con privilegi elevati per ottenere le credenziali temporanee relative al gruppo di sicurezza. Questo processo richiede più livelli di approvazione legale. Se viene consentito l'accesso, tutta l'attività viene registrata e controllata. Inoltre, l'accesso viene consentito solo per un determinato intervallo di tempo, al termine del quale scade automaticamente.
  
Per una protezione maggiore, la tecnologia DKM include il rollover della chiave automatico e l'archiviazione. Ciò garantisce ulteriormente che l'utente possa continuare ad accedere ai contenuti meno recenti senza dover usare la stessa chiave per un periodo di tempo indeterminato.

  
## <a name="where-does-exchange-online-make-use-of-dkm"></a>Per cosa si utilizza DKM in Exchange Online?

Microsoft utilizza DKM per crittografare i dati riservati degli utenti nei datacenter di Exchange Online. Ad esempio:
  
- Le credenziali dell'account di posta elettronica per gli account connessi. Gli account connessi sono account di terzi come quelli di Hotmail, Gmail e Yahoo!.
    
- Chiavi radice del servizio Rights Management (RMS). Queste sono le chiavi dei clienti che vengono importate da Azure RMS o dalle distribuzioni RMS di Active Directory locale dei clienti che vengono utilizzate per crittografare e decrittografare i messaggi di posta elettronica con RMS o Office 365 Message Encryption (OME).
    
## <a name="related-topics"></a>Argomenti correlati

[Crittografia in Office 365](encryption.md)
  
[Dettagli tecnici di riferimento sulla crittografia in Office 365](technical-reference-details-about-encryption.md)
  
[Garanzia del servizio nel centro sicurezza &amp; e conformità di Office 365](https://go.microsoft.com/fwlink/?linkid=874645)
  

