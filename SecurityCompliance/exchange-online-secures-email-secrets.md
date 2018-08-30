---
title: Come viene garantita la protezione della posta elettronica in Exchange Online
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 5/24/2018
ms.audience: ITPro
ms.topic: reference
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 989ba10c-f73f-4efb-ad1b-af3322e5f376
description: Oltre a Office 365 Trust Center cui vengono fornite informazioni di conformità, Privacy e sicurezza per Office 365, è possibile sapere come aiuta a Office 365 protegge segreti fornire in relativi centri dati. Si utilizza una tecnologia denominata distribuita chiave Manager (DKM).
ms.openlocfilehash: a8fe1a2c9393958a391ec69a9a476a06de8c7576
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/27/2018
ms.locfileid: "22531324"
---
# <a name="how-exchange-online-secures-your-email-secrets"></a>Come viene garantita la protezione della posta elettronica in Exchange Online

In questo articolo viene descritto come Microsoft garantisce la protezione della posta elettronica degli utenti nei datacenter.
  
## <a name="how-do-we-secure-secret-information-provided-by-you"></a>Come vengono protette le informazioni riservate fornite dall'utente?

Oltre a Office 365 Trust Center cui vengono fornite [informazioni di conformità per Office 365, Privacy e sicurezza](https://go.microsoft.com/fwlink/?linkid=874644), è possibile sapere come aiuta a Office 365 protegge segreti fornire in relativi centri dati. Si utilizza una tecnologia denominata distribuita chiave Manager (DKM).
  
Si tratta di una funzionalità lato client che usa un set di chiavi segrete per crittografare e decrittografare le informazioni. Solo i membri di un gruppo di sicurezza specifico in Servizi di dominio Active Directory possono accedere a tali chiavi per decrittografare i dati crittografati da DKM. In Exchange Online, fanno parte di quel determinato gruppo di sicurezza solo determinati account di servizio nei quali sono in esecuzione i processi di Exchange. Nell'ambito della procedura operativa standard nel datacenter, le credenziali che fanno parte del gruppo di sicurezza non vengono fornite a nessuno; pertanto, nessuno ha accesso alle chiavi in grado di decrittografare le informazioni riservate.
  
Per scopi legati al debug, alla risoluzione dei problemi o al controllo, è necessario che l'amministratore di un datacenter richieda un accesso con privilegi elevati per ottenere le credenziali temporanee relative al gruppo di sicurezza. Questo processo richiede più livelli di approvazione legale. Se viene consentito l'accesso, tutta l'attività viene registrata e controllata. Inoltre, l'accesso viene consentito solo per un determinato intervallo di tempo, al termine del quale scade automaticamente.
  
Per una protezione maggiore, la tecnologia DKM include il rollover della chiave automatico e l'archiviazione. Ciò garantisce ulteriormente che l'utente possa continuare ad accedere ai contenuti meno recenti senza dover usare la stessa chiave per un periodo di tempo indeterminato.

  
## <a name="where-does-exchange-online-make-use-of-dkm"></a>Per cosa si utilizza DKM in Exchange Online?

Microsoft utilizza DKM per crittografare i dati riservati degli utenti nei datacenter di Exchange Online. Ad esempio:
  
- Le credenziali dell'account di posta elettronica per gli account connessi. Gli account connessi sono account di terzi come quelli di Hotmail, Gmail e Yahoo!.
    
- Le autorizzazioni di chiavi principali di gestione del servizio (RMS). Si tratta di chiavi cliente che uno importate da RMS Azure o dalle distribuzioni di Active Directory Domain Services RMS locale del cliente che vengono utilizzate per la crittografia e decrittografia RMS o Office 365 messaggio crittografia dei messaggi di posta elettronica.
    
## <a name="related-topics"></a>Argomenti correlati

[Crittografia in Office 365](encryption.md)
  
[Dettagli tecnici di riferimento sulla crittografia in Office 365](technical-reference-details-about-encryption.md)
  
[Servizio assurance in Office 365 Security &amp; centro conformità](https://go.microsoft.com/fwlink/?linkid=874645)
  

