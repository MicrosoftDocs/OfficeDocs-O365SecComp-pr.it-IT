---
title: Recapito dinamico e l'anteprima allegati sicuri di Office 365 degli strumenti di analisi di
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 2/28/2018
ms.audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: f16c9928-8e3d-4219-b994-271dc9a16272
description: Quando si imposta i criteri di sicurezza degli allegati degli strumenti di analisi, si sceglie recapito dinamico per evitare ritardi messaggio e consentire agli utenti di visualizzare in anteprima degli allegati che vengono analizzati.
ms.openlocfilehash: 23017f4f995dfe6a90479d83af9522531d7bf96b
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/27/2018
ms.locfileid: "22530205"
---
# <a name="dynamic-delivery-and-previewing-with-office-365-atp-safe-attachments"></a>Recapito dinamico e l'anteprima allegati sicuri di Office 365 degli strumenti di analisi di

Recapito dinamico è un'opzione che è possibile selezionare per. In questo articolo per informazioni su Recapito dinamico e funzionalità di anteprima degli allegati in [Strumenti di analisi allegati attendibili in Office 365](atp-safe-attachments.md).
  
## <a name="how-dynamic-delivery-works"></a>Works recapito dinamico

Quando si [Imposta i criteri degli strumenti di analisi provvisoria allegati in Office 365](set-up-atp-safe-attachments-policies.md), è possibile scegliere tra diverse opzioni, ad esempio **blocco**, **sostituire**e **Recapito dinamico**. A seconda della modalità di configurazione dei criteri, i destinatari di posta elettronica possono verificarsi un ritardo secondario di recapito della posta elettronica quando gli allegati vengono analizzati. Per evitare ritardi messaggio, scegliere **Recapito dinamico**.
  
L'opzione di distribuzione dinamico Elimina i ritardi di posta elettronica mediante l'invio di corpo di un messaggio di posta elettronica con un segnaposto per tutti gli allegati di posta elettronica. Il segnaposto rimane fino a quando l'allegato è analizzato da [Strumenti di analisi allegati attendibili in Office 365](atp-safe-attachments.md). Destinatari di posta elettronica possono leggere e rispondere ai propri messaggi di posta elettronica subito, sapere che vengono analizzati gli allegati.
  
La maggior parte dei documenti PDF e l'ufficio documenti possono essere visualizzati in anteprima in modalità provvisoria durante l'analisi degli strumenti di analisi. Se un allegato non è compatibile con il Visualizzatore di recapito dinamico, segnaposto allegato viene visualizzato dai destinatari di posta elettronica fino a completa la scansione degli allegati sicuri degli strumenti di analisi.
  
Che tutti gli allegati sia selezionato, viene automaticamente ricollegato al messaggio di posta elettronica originale. Se un allegato è determinato da dannoso, viene inviata alla quarantena, in cui una persona nel team di protezione dell'organizzazione (ad esempio un amministratore di protezione o di amministratore globale di Office 365) possibile [gestire i messaggi in quarantena in Office 365](manage-quarantined-messages-and-files.md).
  
## <a name="what-happens-when-someone-forwards-an-email-that-contains-an-attachment"></a>Cosa succede quando un utente inoltra un messaggio di posta elettronica contenente un allegato.

Si supponga che un'organizzazione di recapito dinamico di utilizzare i [criteri gli allegati sicuri degli strumenti di analisi](set-up-atp-safe-attachments-policies.md)e un utente riceve un messaggio di posta elettronica contenente un allegato. A questo punto si supponga che tale persona deve inoltrare il messaggio di posta elettronica a un utente. Che succede? Dipende dal fatto altri destinatari sono inclusi nei criteri gli allegati sicuri degli strumenti di analisi.
  
- Se un destinatario è occupato da un criterio di allegati sicuri degli strumenti di analisi utilizzando l'opzione di distribuzione dinamico, il destinatario vede il segnaposto con la possibilità di visualizzare in anteprima i file compatibili.
    
- Se un destinatario non è occupato da un criterio di allegati sicuri degli strumenti di analisi, quindi il messaggio di posta elettronica e allegati verranno passate, senza allegati sicuri degli strumenti di analisi analisi o placeholders allegato.
    
## <a name="whats-required-for-dynamic-delivery-to-work"></a>Requisiti per il recapito dinamico funziona?

- L'organizzazione deve disporre di [Protezione avanzate da minacce di Office 365](office-365-atp.md)
    
- È necessario definire i criteri per gli allegati sicuri degli strumenti di analisi utilizzando l'opzione di distribuzione dinamico (vedere [Set up criteri degli strumenti di analisi allegati attendibili in Office 365](set-up-atp-safe-attachments-policies.md))
    
- Messaggio di posta elettronica dell'organizzazione deve essere ospitato in Office 365
    
## <a name="are-there-scenarios-for-which-dynamic-delivery-is-not-available"></a>Esistono scenari per i quali non è disponibile il recapito dinamico?

Esistono alcuni scenari in cui non è supportato recapito dinamico. Questi sono i seguenti:
  
- Messaggi di posta elettronica per le cartelle pubbliche
    
- Messaggi di posta elettronica vengono indirizzati fuori e quindi nuovamente nella cassetta postale dell'utente tramite regole personalizzate
    
- I messaggi che vengono spostati (automaticamente o manualmente) all'esterno della cassetta postale ospitata e in altre posizioni, tra cui archiviare le cartelle
    
- Messaggi che vengono eliminati
    
- Cartella di ricerca delle cassette postali dell'utente che si trova nello stato di errore
    
- Ambienti in cui un amministratore di Exchange Online è abilitato Exclaimer. (Vedere [i messaggi con allegati non vengono recapitati quando vengono utilizzati degli strumenti di analisi dinamica recapito ed Exclaimer](https://support.microsoft.com/help/4014438/messages-with-attachments-are-not-delivered-when-atp-dynamic-delivery))
    
## <a name="related-topics"></a>Argomenti correlati

[Office 365 Advanced Threat Protection](office-365-atp.md)
  
[Allegati degli strumenti di analisi sicuro in Office 365](atp-safe-attachments.md)
  
[Impostare i criteri degli strumenti di analisi allegati attendibili in Office 365](set-up-atp-safe-attachments-policies.md)
  
[Collegamenti degli strumenti di analisi sicuro in Office 365](atp-safe-links.md)

[Le autorizzazioni di sicurezza di Office 365 &amp; centro conformità](permissions-in-the-security-and-compliance-center.md)
  

