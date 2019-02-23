---
title: ReCapito dinamico e anteprima con allegati sicuri ATP di Office 365
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 01/08/2019
ms.audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: f16c9928-8e3d-4219-b994-271dc9a16272
ms.collection:
- M365-security-compliance
description: Quando si configurano i criteri per gli allegati sicuri di ATP, è possibile scegliere reCapito dinamico per evitare ritardi nei messaggi e consentire agli utenti di visualizzare in anteprima gli allegati analizzati.
ms.openlocfilehash: 1fb221d28a4089db8a4278903107c610d6825f5e
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/23/2019
ms.locfileid: "30218396"
---
# <a name="dynamic-delivery-and-previewing-with-office-365-atp-safe-attachments"></a>ReCapito dinamico e anteprima con allegati sicuri ATP di Office 365

**Riepilogo**: il recapito dinamico è un'opzione che può essere selezionata per gli [allegati sicuri di ATP](atp-safe-attachments.md). Leggere questo articolo per informazioni sulle funzionalità di anteprima degli allegati e il reCapito dinamico in [ATP Safe Attachments in Office 365](atp-safe-attachments.md).

Quando i [criteri degli allegati sicuri di ATP sono](set-up-atp-safe-attachments-policies.md) configurati per l'organizzazione, sono disponibili diverse opzioni per la gestione degli allegati di posta elettronica. Sono inclusi **blocco**, **sostituzione**e **recapito dinamico**. A seconda del modo in cui vengono configurati i criteri per gli allegati sicuri di ATP, i destinatari di posta elettronica potrebbero subire un ritardo durante l'analisi dei messaggi. Per evitare ritardi nei messaggi, scegliere **recapito dinamico**.
  
## <a name="how-dynamic-delivery-works"></a>Funzionamento del reCapito dinamico
  
Il reCapito dinamico elimina i ritardi della posta elettronica inviando il corpo di un messaggio di posta elettronica al destinatario con un segnaposto per ogni allegato di posta elettronica. Il segnaposto rimane invariato fino a quando una copia dell'allegato viene analizzata e determinata a essere sicura dagli [allegati sicuri di ATP](atp-safe-attachments.md). 

- Poiché ogni allegato è deselezionato, è disponibile per l'apertura o il download. 

- Se un allegato è determinato come dannoso, viene inviato alla quarantena, in cui un utente del team di sicurezza dell'organizzazione (ad esempio un amministratore globale di Office 365 o un amministratore della sicurezza) può [gestire i messaggi in quarantena in office 365](manage-quarantined-messages-and-files.md).

La maggior parte dei file PDF e i documenti di Office possono essere visualizzati in anteprima in modalità provvisoria mentre è in corso l'analisi ATP. Se un allegato non è compatibile con l'anteprima di reCapito dinamico, i destinatari di posta elettronica visualizzano un segnaposto allegato finché non è stato completato l'analisi degli allegati sicuri di ATP.

> [!TIP]
> Se si utilizza un dispositivo mobile e i file PDF non vengono visualizzati in anteprima per il reCapito dinamico, provare a eseguire l'accesso a Office 365 utilizzando il browser per dispositivi mobili.

Con il reCapito dinamico, gli utenti possono leggere e rispondere immediatamente ai propri messaggi di posta elettronica, mentre gli allegati vengono analizzati. 

L'analisi degli allegati sicuri ATP si verifica nella stessa area in cui si trovano i dati di Office 365. Per ulteriori informazioni sulla geografia del Data Center, vedere [dove si trovano i dati?](https://products.office.com/where-is-your-data-located?geo=All) 
  
## <a name="what-happens-when-someone-forwards-an-email-that-contains-an-attachment"></a>Cosa succede quando qualcuno inoltra un messaggio di posta elettronica che contiene un allegato?

Si supponga che un'organizzazione stia utilizzando il reCapito dinamico per il [criterio degli allegati sicuri ATP](set-up-atp-safe-attachments-policies.md)e che qualcuno riceva un messaggio di posta elettronica contenente un allegato. Ora supponiamo che la persona inoltra il messaggio di posta elettronica a un altro utente. Che succede? Dipende dal fatto che i destinatari aggiuntivi siano inclusi nei criteri allegati sicuri di ATP.
  
- Se un destinatario è incluso in un criterio di allegati sicuri ATP utilizzando l'opzione di reCapito dinamico, il destinatario Visualizza il segnaposto, con la possibilità di visualizzare in anteprima i file compatibili.
    
- Se un destinatario non è incluso in un criterio per gli allegati sicuri di ATP, il messaggio di posta elettronica e l'allegato passeranno, senza l'analisi degli allegati sicuri di ATP o i segnaposto allegati.
    
## <a name="whats-required-for-dynamic-delivery-to-work"></a>Cosa è necessario per il funzionamento del reCapito dinamico?

- L'organizzazione deve disporre di [Office 365 Advanced Threat Protection](office-365-atp.md)
    
- I criteri devono essere definiti per gli allegati sicuri di ATP utilizzando l'opzione di reCapito dinamico (vedere [configurare i criteri degli allegati sicuri di ATP in Office 365](set-up-atp-safe-attachments-policies.md))
    
- La posta elettronica dell'organizzazione deve essere ospitata in Office 365
    
## <a name="are-there-scenarios-for-which-dynamic-delivery-is-not-available"></a>Esistono scenari per i quali il reCapito dinamico non è disponibile?

Esistono alcuni scenari in cui il reCapito dinamico non è supportato. Sono inclusi i seguenti:
  
- Messaggi di posta elettronica presenti nelle cartelle pubbliche
    
- Messaggi di posta elettronica instradati fuori e quindi di nuovo nella cassetta postale dell'utente utilizzando regole personalizzate
    
- Messaggi di posta elettronica spostati (automaticamente o manualmente) dalla cassetta postale ospitata e in altre posizioni, incluse le cartelle di archiviazione
    
- Messaggi di posta elettronica eliminati
    
- Cartella di ricerca della cassetta postale di un utente che si trova in uno stato di errore
    
- Ambienti in cui un amministratore di Exchange Online ha abilitato l'utente esclamativo. Per risolvere il caso, vedere [i messaggi con allegati non vengono recapitati quando viene utilizzato il recapito dinamico e l'esclamaTORE ATP](https://support.microsoft.com/help/4014438/messages-with-attachments-are-not-delivered-when-atp-dynamic-delivery)

- Messaggi crittografati con [S/MIME (Secure/Multipurpose Internet Mail Extensions)](s-mime-for-message-signing-and-encryption.md))

