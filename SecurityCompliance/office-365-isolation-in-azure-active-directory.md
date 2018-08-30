---
title: Isolamento di Office 365 e controllo di accesso di Azure Active Directory
ms.author: robmazz
author: robmazz
manager: laurawi
ms.date: 8/21/2018
audience: ITPro
ms.topic: article
ms.service: Office 365 Administration
localization_priority: None
search.appverid:
- MET150
ms.collection: Strat_O365_Enterprise
description: "Riepilogo: Come utilizzare l'isolamento e controllo di accesso di Azure Active Directory."
ms.openlocfilehash: db4fa0d026c6c608f09252c65bf1e0de5354f68c
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/27/2018
ms.locfileid: "22531328"
---
# <a name="isolation-and-access-control-in-azure-active-directory"></a>Isolamento e controllo di accesso in Azure Active Directory

Azure Active Directory sono stati progettati per ospitare più tenant in modo esigenze di sicurezza e isolamento logico dei dati. Accesso di Azure Active Directory viene gestita da un livello di autorizzazione. Azure Active Directory consente di isolare i clienti che utilizzano i contenitori tenant come limiti di protezione per proteggere il contenuto del cliente in modo che il contenuto non è accessibile o compromesso da CO-tenant. Tre controlli vengono eseguiti dal livello di autorizzazione di Azure Active Directory:
- L'entità è abilitato per l'accesso al tenant di Azure Active Directory?
- L'entità è abilitato per l'accesso ai dati di questo tenant?
- È il ruolo dell'entità in questa tenant dispone dell'autorizzazione per il tipo di accesso ai dati richiesto?

Nessuna applicazione, utente, server o servizio può accedere Azure Active Directory senza autenticazione appropriato e token o del certificato. Le richieste vengono rifiutate se non sono accompagnate dalla credenziali appropriate.

Azure Active Directory in modo efficace, ospita ogni tenant nel relativo contenitore protetto, con i criteri e le autorizzazioni per e all'interno del contenitore unicamente e di proprietà e gestite da tenant.
 
![Contenitore di Azure](media/office-365-isolation-azure-container.png)

Il concetto di contenitori tenant in profondità è radicato nel servizio directory a tutti i livelli di portali verso un'archiviazione persistente. Anche quando più metadati tenant di Azure Active Directory vengono archiviati nello stesso disco fisico, non esiste alcuna relazione tra i contenitori diverso da quello definito dal servizio directory, che a sua volta è determinato dall'amministratore del tenant. Non può essere Nessuna connessione diretta di archiviazione di Azure Active Directory da qualsiasi applicazione o un servizio senza prima utilizzare il livello di autorizzazione richiesta.

Nell'esempio seguente, Contoso e Fabrikam hanno contenitori dedicata e anche se tali contenitori possono condividere alcune della stessa infrastruttura sottostante, ad esempio server e archiviazione, che restano separati e isolate tra loro e gestita dalla livelli di autorizzazione e controllo di accesso.
 
![Azure contenitori dedicati](media/office-365-isolation-azure-dedicated-containers.png)

Inoltre, non sono componenti dell'applicazione che possono essere eseguiti all'interno di Azure Active Directory e non è possibile per un tenant forzatamente violare l'integrità di un altro tenant, per accedere a chiavi di crittografia di un altro tenant o leggere i dati non elaborati dal server.

Per impostazione predefinita, Azure Active Directory non ammette tutte le operazioni emesso dalle identità in altri tenant. Ogni tenant è logicamente isolato all'interno di Azure Active Directory tramite i controlli di accesso basata sulle attestazioni. Letture e scritture della directory dei dati sono come ambiti tenant contenitori e gestiti da un livello di astrazione interno e un livello di controllo di accesso basato sui ruoli, che insieme applicare il tenant come il limite di sicurezza. Tutte le richieste di accesso dati directory viene elaborata da questi livelli e tutte le richieste di accesso in Office 365 sono policed dalla logica sopra elencata.

Azure Active Directory presenta partizioni Nord America, governo degli Stati Uniti, Unione europea, in Germania e World Wide. È presente un tenant in un'unica partizione e partizioni possono contenere più tenant. Informazioni sulla partizione estratti dagli utenti. Una partizione specificata (inclusi tutti i tenant in essa contenuti) verrà replicata in più centri dati. La partizione per un tenant viene scelto in base alle proprietà del tenant (ad esempio, il codice paese). Segreti e altre informazioni riservate in ogni partizione è crittografato con una chiave dedicata. Le chiavi vengono generate automaticamente quando viene creata una nuova partizione.

Funzionalità di sistema Azure Active Directory è un'istanza univoca di ogni sessione utente. Inoltre, Azure Active Directory utilizza tecnologie di crittografia per fornire l'isolamento delle risorse di sistema condivise a livello di rete per impedire il trasferimento non autorizzato non intenzionale di informazioni.
