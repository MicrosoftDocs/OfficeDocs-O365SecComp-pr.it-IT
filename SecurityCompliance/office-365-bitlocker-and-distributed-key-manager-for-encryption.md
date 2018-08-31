---
title: BitLocker di Office 365 per la crittografia
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
description: 'Riepilogo: Informazioni su BitLocker per la crittografia nel cloud.'
ms.openlocfilehash: 86c6bc9282d7c2b0a7d4e08d4636c8f9c2fa5db8
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/27/2018
ms.locfileid: "22530816"
---
# <a name="bitlocker-and-distributed-key-manager-dkm-for-encryption"></a>BitLocker e Distributed Key Manager (DKM) per la crittografia
Server di Office 365 utilizzare BitLocker per crittografare le unità disco contenente i dati dei clienti statici a livello di volume. BitLocker è una funzionalità di protezione di dati che è incorporata in Windows. BitLocker è una delle tecnologie utilizzate per la protezione contro le minacce nel caso in cui sono disponibili falle in altri processi o controlli (ad esempio, il controllo di accesso o riciclo di componenti hardware) che potrebbero causare un utente l'accesso fisico per i dischi che contengono i dati dei clienti. In questo caso, BitLocker Elimina il rischio di esposizione o furto di dati a causa di dischi e i computer perse, furto o rimozione delle autorizzazioni in modo improprio.

BitLocker viene distribuito con la crittografia a 256 bit Standard AES (Advanced Encryption) su dischi contenente i dati dei clienti di Exchange Online, SharePoint Online e Skype per le aziende. Settori del disco sono crittografati con una completa Volume crittografia chiave (FVEK), che vengono crittografati con la chiave del Volume Master (VMK), che a sua volta, è associato all'attendibili Platform Module (GPC) nel server. La VMK direttamente protegge la chiave FVEK e pertanto protezione la VMK diventa critica. Nella figura seguente viene illustrato un esempio della catena di protezione della chiave BitLocker per un determinato server (in questo caso, utilizzare un server di Exchange Online).

Nella tabella seguente vengono descritti la catena di protezione della chiave BitLocker per un determinato server (in questo caso, un server di Exchange Online).

| PROGRAMMA DI PROTEZIONE CHIAVE | LIVELLO DI DETTAGLIO | COME GENERATO? | DOVE VIENE MEMORIZZATO? | PROTEZIONE |
|--------------------------------------------------------------------------------|-------------------------------------------------|----------------|-------------------------|--------------------------------------------------------------------------------------------------|
| Chiave esterna AES a 256 bit | Per ogni Server | API BitLocker | GPC o segreta sicuro | Archivio protetto / controllo di accesso |
|  |  |  | Registro di sistema Server cassette postali | GPC crittografati |
| Password numerica 48 cifre | Per ogni disco | API BitLocker | Active Directory | Archivio protetto / controllo di accesso |
| Certificato x. 509 come dati ripristino all'agente l'acronimo di Public Key programma di protezione | Ambiente (ad esempio, i tenant Exchange Online) | Autorità di certificazione Microsoft | Sistema di compilazione | Non un utente ha la password completa per la chiave privata. La password è in protezione fisica. |


Gestione delle chiavi BitLocker comporta la gestione delle chiavi di ripristino da utilizzare per sbloccare/recupera dischi crittografati in un Data Center di Office 365. Office 365 archivia le chiavi principali in una condivisione protetta, accessibile solo da utenti che sono stato scartati e approvati. Le credenziali per le chiavi sono archiviate in un archivio protetto per i dati di controllo di accesso (cosa viene chiamato un archivio"secret"), che richiede un elevato livello delle approvazioni elevazione di privilegi e la gestione di accedere utilizzando uno strumento di elevazione di privilegi di accesso-in-time.

BitLocker supporta le chiavi che possono essere suddivisi in due categorie di gestione:
- BitLocker gestiti chiavi, che sono in genere breve durata e collegata alla durata di un'istanza del sistema operativo installata in un server o a un determinato disco. Queste sequenze di tasti vengono eliminate e reimpostare durante la reinstallazione di server o la formattazione del disco.
- Tasti di ripristino BitLocker, che vengono gestite di fuori BitLocker ma utilizzate per la decrittografia su disco. BitLocker utilizza le chiavi di ripristino per lo scenario in cui si reinstalla un sistema operativo e i dischi dati crittografati esistono già. Tasti di ripristino utilizzati anche in base alla disponibilità gestita monitoring probe di Exchange Online in cui potrebbe essere necessario un risponditore per sbloccare un disco.

Volumi protetti da BitLocker vengono crittografati con una chiave di crittografia completa del volume, a sua volta è crittografata con una chiave master del volume. BitLocker utilizza algoritmi conformi agli standard FIPS per garantire che le chiavi di crittografia vengono mai archiviate o inviate in rete in chiaro. L'implementazione di Office 365 del cliente-a-rest-protezione dei dati non si discosti dall'implementazione BitLocker predefinito.