---
title: Isolamento e controllo di accesso di Office 365 in Azure Active Directory
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
description: "Riepilogo: funzionamento del controllo dell'isolamento e dell'accesso all'interno di Azure Active Directory."
ms.openlocfilehash: bca7dc11bc3cc76e18972eb03761775da5f5cb41
ms.sourcegitcommit: 1261a37c414111f869df5791548a768d853fda60
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/30/2019
ms.locfileid: "31004219"
---
# <a name="isolation-and-access-control-in-azure-active-directory"></a>Isolamento e controllo di accesso in Azure Active Directory

Azure Active Directory è stato creato per ospitare più tenant in modo estremamente sicuro tramite l'isolamento dei dati logici. L'accesso a Azure Active Directory è associato a un livello di autorizzazione. Azure Active Directory consente di isolare i clienti utilizzando i contenitori tenant come limiti di sicurezza per salvaguardare il contenuto di un cliente, in modo che non sia possibile accedere ai contenuti o essere compromessi dai coinquilini. Tre controlli vengono eseguiti dal livello di autorizzazione di Azure Active Directory:
- L'entità è abilitata per l'accesso al tenant di Azure Active Directory?
- L'entità è abilitata per l'accesso ai dati nel tenant?
- Il ruolo dell'entità in questo tenant è autorizzato per il tipo di accesso ai dati richiesto?

Nessuna applicazione, utente, server o servizio può accedere ad Azure Active Directory senza l'autenticazione e il token o il certificato appropriati. Le richieste vengono rifiutate se non sono accompagnate da credenziali appropriate.

In modo efficace, Azure Active Directory ospita ogni tenant nel proprio contenitore protetto, con i criteri e le autorizzazioni per e all'interno del contenitore posseduto e gestito solo dal tenant.
 
![Contenitore di Azure](media/office-365-isolation-azure-container.png)

Il concetto di contenitori tenant è profondamente radicato nel servizio directory a tutti i livelli, dai portali fino all'archiviazione persistente. Anche se più metadati tenant di Azure Active Directory sono archiviati nello stesso disco fisico, non esiste alcuna relazione tra i contenitori diversi da quelli definiti dal servizio directory, che a sua volta è dettata dall'amministratore del tenant. Non vi possono essere connessioni dirette all'archiviazione di Azure Active Directory da qualsiasi applicazione o servizio richiedente senza prima passare attraverso il livello di autorizzazione.

Nell'esempio riportato di seguito, Contoso e Fabrikam dispongono entrambi di contenitori separati e dedicati e, sebbene tali contenitori possano condividere parte della stessa infrastruttura sottostante, ad esempio i server e l'archiviazione, rimangono separati e isolati gli uni dagli altri e sono gated da livelli di autorizzazione e controllo di accesso.
 
![Contenitori dedicati di Azure](media/office-365-isolation-azure-dedicated-containers.png)

Inoltre, non sono presenti componenti dell'applicazione che possono essere eseguiti dall'interno di Azure Active Directory e non è possibile che un tenant violi forzatamente l'integrità di un altro tenant, acceda alle chiavi di crittografia di un altro tenant o legga dati non elaborati dal server.

Per impostazione predefinita, Azure Active Directory non consente tutte le operazioni emesse dalle identità in altri tenant. Ogni tenant è logicamente isolato all'interno di Azure Active Directory tramite i controlli di accesso basati sulle attestazioni. Le letture e le scritture dei dati della directory sono limitate ai contenitori tenant e sono deportate da un livello di astrazione interno e da un livello di controllo di accesso basato sui ruoli (RBAC), che insieme impongono il tenant come limite di sicurezza. Ogni richiesta di accesso ai dati di directory viene elaborata da questi layer e ogni richiesta di accesso in Office 365 è sorvegliata dalla logica precedente.

Azure Active Directory dispone del Nord America, del governo degli Stati Uniti, dell'Unione europea, della Germania e delle partizioni mondiali. Un tenant esiste in una singola partizione e le partizioni possono contenere più tenant. Le informazioni sulla partizione vengono sottratte agli utenti. Una determinata partizione (inclusi tutti i tenant all'interno) viene replicata in più datacenter. La partizione per un tenant viene scelta in base alle proprietà del tenant (ad esempio, il codice paese). I segreti e altre informazioni riservate in ogni partizione vengono crittografati con una chiave dedicata. Le chiavi vengono generate automaticamente quando viene creata una nuova partizione.

Le funzionalità di Azure Active Directory System sono un'istanza univoca per ogni sessione utente. Azure Active Directory utilizza inoltre le tecnologie di crittografia per garantire l'isolamento delle risorse di sistema condivise a livello di rete per impedire il trasferimento non autorizzato e involontario di informazioni.
