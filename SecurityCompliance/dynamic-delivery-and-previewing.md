---
title: Recapito dinamico e l'anteprima allegati sicuri di Office 365 degli strumenti di analisi di
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 01/08/2019
ms.audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: f16c9928-8e3d-4219-b994-271dc9a16272
ms.collection:
- M365-security-compliance
description: Quando si imposta i criteri di sicurezza degli allegati degli strumenti di analisi, si sceglie recapito dinamico per evitare ritardi messaggio e consentire agli utenti di visualizzare in anteprima degli allegati che vengono analizzati.
ms.openlocfilehash: ae027986cf5114bd024c679a59975d1e4be52d32
ms.sourcegitcommit: efccf5b4f22d34a9674bc55ebf3d88bc8bda2972
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/14/2019
ms.locfileid: "29995147"
---
# <a name="dynamic-delivery-and-previewing-with-office-365-atp-safe-attachments"></a>Recapito dinamico e l'anteprima allegati sicuri di Office 365 degli strumenti di analisi di

**Riepilogo**: recapito dinamico è un'opzione che è possibile selezionare gli allegati [sicuri degli strumenti di analisi](atp-safe-attachments.md). In questo articolo per informazioni su recapito dinamici e funzionalità di anteprima degli allegati in [Strumenti di analisi allegati attendibili in Office 365](atp-safe-attachments.md).

Quando [vengono impostati i criteri degli strumenti di analisi gli allegati sicuri](set-up-atp-safe-attachments-policies.md) per l'organizzazione, sono disponibili diverse opzioni per la modalità di Gestione allegati di posta elettronica. Sono inclusi **blocco**, **sostituire**e **Recapito dinamico**. A seconda della configurazione delle criteri gli allegati sicuri degli strumenti di analisi, i destinatari di posta elettronica potrebbero verificarsi un ritardo secondario di recapito della posta elettronica quando gli allegati vengono analizzati. Per evitare ritardi messaggio, scegliere **Recapito dinamico**.
  
## <a name="how-dynamic-delivery-works"></a>Funzionamento del recapito dinamico
  
Recapito dinamico Elimina i ritardi di posta elettronica mediante l'invio di corpo di un messaggio di posta elettronica al destinatario con un segnaposto per tutti gli allegati di posta elettronica. Segnaposto rimane fino a quando una copia dell'allegato viene analizzata ritenuta attendibili per [Gli allegati sicuri degli strumenti di analisi](atp-safe-attachments.md). 

- Quando sono deselezionato tutti gli allegati, risulta disponibile per aprire o scaricare. 

- Se un allegato è determinato da dannoso, viene inviata alla quarantena, in cui una persona nel team di protezione dell'organizzazione (ad esempio un amministratore di protezione o di amministratore globale di Office 365) possibile [gestire i messaggi in quarantena in Office 365](manage-quarantined-messages-and-files.md).

La maggior parte dei documenti PDF e l'ufficio documenti possono essere visualizzati in anteprima in modalità provvisoria durante l'analisi degli strumenti di analisi. Se un allegato non è compatibile con il Visualizzatore di recapito dinamico, un segnaposto allegato viene visualizzato dai destinatari di posta elettronica fino a completa la scansione degli allegati sicuri degli strumenti di analisi.

> [!TIP]
> Se si utilizza un dispositivo mobile e file PDF non eseguono il rendering nell'anteprima dinamica recapito inizialmente, tentare l'accesso a Office 365 con browser per dispositivi mobili.

Con recapito dinamico, persone possono leggere e rispondere ai propri messaggi di posta elettronica immediatamente, mentre gli allegati vengono analizzati. 

Gli allegati sicuri degli strumenti di analisi analisi abbia effettuare nella stessa area in cui si trovano i dati di Office 365. Per ulteriori informazioni sulle aree di centro dati, vedere [dove sono i dati si trova?](https://products.office.com/where-is-your-data-located?geo=All) 
  
## <a name="what-happens-when-someone-forwards-an-email-that-contains-an-attachment"></a>Cosa succede quando un utente inoltra un messaggio di posta elettronica contenente un allegato.

Si supponga che un'organizzazione di recapito dinamico di utilizzare i [criteri gli allegati sicuri degli strumenti di analisi](set-up-atp-safe-attachments-policies.md)e un utente riceve un messaggio di posta elettronica contenente un allegato. A questo punto si supponga che tale persona inoltra il messaggio di posta elettronica a un utente. Che succede? Dipende dal fatto altri destinatari sono inclusi nei criteri gli allegati sicuri degli strumenti di analisi.
  
- Se un destinatario è occupato da un criterio di allegati sicuri degli strumenti di analisi utilizzando l'opzione di distribuzione dinamico, il destinatario vede il segnaposto con la possibilità di visualizzare in anteprima i file compatibili.
    
- Se un destinatario non è occupato da un criterio di allegati sicuri degli strumenti di analisi, quindi il messaggio di posta elettronica e allegati verranno passate, senza allegati sicuri degli strumenti di analisi analisi o placeholders allegato.
    
## <a name="whats-required-for-dynamic-delivery-to-work"></a>Requisiti per il recapito dinamica funziona?

- L'organizzazione deve disporre di [Protezione avanzate da minacce di Office 365](office-365-atp.md)
    
- È necessario definire i criteri per gli allegati sicuri degli strumenti di analisi utilizzando l'opzione di distribuzione dinamico (vedere [Set up criteri degli strumenti di analisi allegati attendibili in Office 365](set-up-atp-safe-attachments-policies.md))
    
- Messaggio di posta elettronica dell'organizzazione deve essere ospitato in Office 365
    
## <a name="are-there-scenarios-for-which-dynamic-delivery-is-not-available"></a>Esistono scenari per i quali non è disponibile recapito dinamico?

Esistono alcuni scenari in cui non è supportato recapito dinamico. Questi sono i seguenti:
  
- Messaggi di posta elettronica per le cartelle pubbliche
    
- Messaggi di posta elettronica vengono indirizzati fuori e quindi nuovamente nella cassetta postale dell'utente tramite regole personalizzate
    
- Messaggi di posta elettronica vengono spostati (automaticamente o manualmente) all'esterno della cassetta postale ospitata e in altre posizioni, tra cui archiviare le cartelle
    
- Messaggi di posta elettronica vengono eliminati
    
- Cartella di ricerca delle cassette postali dell'utente che si trova nello stato di errore
    
- Ambienti in cui un amministratore di Exchange Online è abilitato Exclaimer. Per risolvere questo problema, vedere [i messaggi con allegati non vengono recapitati quando vengono utilizzati degli strumenti di analisi dinamica recapito ed Exclaimer](https://support.microsoft.com/help/4014438/messages-with-attachments-are-not-delivered-when-atp-dynamic-delivery)

- Messaggi crittografati con [Secure/Multipurpose Internet Mail Extensions (S/MIME)](s-mime-for-message-signing-and-encryption.md))

