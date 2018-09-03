---
title: Abilitare l'archiviazione illimitata in Office 365 - della Guida di amministrazione
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 6/29/2018
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MET150
ms.assetid: e2a789f2-9962-4960-9fd4-a00aa063559e
description: "Per gli amministratori: informazioni su come abilitare l'espansione automatica archiviazione in Office 365, che consente agli utenti con archiviazione illimitata per le cassette postali di Exchange Online. È possibile abilitare l'espansione automatica di archiviazione per l'intera organizzazione o semplicemente per utenti specifici."
ms.openlocfilehash: ede3e75a021d750160268ccf06ac4fe1637d219a
ms.sourcegitcommit: 81c2fd5cd940c51bc43ac7858c7bdfa207ce401a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/03/2018
ms.locfileid: "23809701"
---
# <a name="enable-unlimited-archiving-in-office-365---admin-help"></a>Abilitare l'archiviazione illimitata in Office 365 - della Guida di amministrazione

È possibile utilizzare la funzionalità di archiviazione Exchange Online espansione automatica in Office 365 per abilitare lo spazio di archiviazione illimitata per cassette postali di archiviazione. Quando è attivata l'espansione automatica di archiviazione, ulteriore spazio di archiviazione viene automaticamente aggiunto alla cassetta postale di archivio dell'utente quando si avvicina al limite di archiviazione. Il risultato è la capacità di archiviazione delle cassette postali illimitato. È possibile attivare l'archiviazione per tutti gli utenti dell'organizzazione o solo per utenti specifici l'espansione automatica. Per ulteriori informazioni sull'espansione automatica di archiviazione, vedere [Overview of archiviazione illimitato in Office 365](unlimited-archiving.md).

## <a name="before-you-begin"></a>Informazioni preliminari

- È necessario essere un amministratore globale dell'organizzazione Office 365 o un membro del gruppo di ruoli Gestione organizzazione nell'organizzazione Exchange Online per abilitare l'espansione automatica archiviazione per l'intera organizzazione o per utenti specifici. In alternativa, è necessario essere membri del gruppo di ruoli che è assegnato il ruolo destinatari di posta elettronica per consentire l'espansione automatica di archiviazione per utenti specifici.
    
- Cassetta postale di archivio dell'utente deve essere abilitata per poter abilitare l'espansione automatica di archiviazione. Un utente deve essere assegnato una licenza di Exchange Online piano 2 per abilitare la cassetta postale di archivio. Se un utente viene assegnato una licenza di Exchange Online piano 1, è necessario assegnarli una licenza separata archiviazione Exchange Online per consentire loro cassetta postale di archivio. Vedere [Enable cassette postali di archiviazione in Office 365 Security &amp; centro conformità](enable-archive-mailboxes.md).
    
- È inoltre possibile utilizzare PowerShell per abilitare cassette postali di archiviazione. Vedere la sezione [informazioni](#more-information) per un esempio del comando PowerShell che è possibile utilizzare per abilitare cassette postali di archiviazione per tutti gli utenti nell'organizzazione. 
    
- L'espansione automatica archiviazione inoltre supporta le cassette postali condivise. Per abilitare l'archivio per una cassetta postale condivisa, è necessaria una licenza di Exchange Online piano 2 o una licenza di Exchange Online piano 1 con una licenza di archiviazione Exchange Online.
    
- È possibile utilizzare l'interfaccia di amministrazione di Exchange o la sicurezza &amp; centro conformità per abilitare l'espansione automatica archiviazione. È necessario utilizzare Exchange Online PowerShell. Per connettersi all'organizzazione Exchange Online tramite remote PowerShell, vedere [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554).
    
  
## <a name="enable-auto-expanding-archiving-for-your-entire-organization"></a>Abilitare l'espansione automatica archiviazione per l'intera organizzazione

È possibile abilitare l'espansione automatica di archiviazione per l'intera organizzazione. Dopo aver attivarlo, espansione automatica archiviazione verrà abilitata per le cassette postali utente esistenti e le nuove cassette postali degli utenti creati. Quando si creano nuove cassette postali utente, è necessario abilitare cassetta postale di archivio principale dell'utente in modo che la caratteristica archiviazione espansione automatica funzionerà per la nuova cassetta postale utente.
  
1. [Connessione a Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554)
    
2. Eseguire il seguente comando in Exchange Online PowerShell per abilitare l'espansione automatica archiviazione per l'intera organizzazione.

    ```
    Set-OrganizationConfig -AutoExpandingArchive
    ```
  
## <a name="enable-auto-expanding-archiving-for-specific-users"></a>Abilitare l'espansione automatica archiviazione per utenti specifici

Anziché consentire l'espansione automatica di archiviazione per tutti gli utenti nell'organizzazione, è possibile solo abilitarla per utenti specifici. È possibile utilizzare questo perché solo ad alcuni utenti potrebbero essere necessario per un archivio di archiviazione di grandi dimensioni.
  
Quando si abilita l'espansione automatica archiviazione per un utente specifico e cassetta postale dell'utente in attesa o assegnati a un criterio di conservazione di Office 365, vengono apportate le modifiche di due configurazioni seguenti:
  
- La quota di archiviazione per la cassetta postale di archivio principale dell'utente viene aumentata a 10 GB (da 100 GB a 110 GB). La quota di avviso anche è aumentata a 10 GB (da 90 GB a 100 GB).
    
- La quota di archiviazione per la cartella elementi ripristinabili nella cassetta postale principale dell'utente viene aumentata a 10 GB (anche da 100 GB a 110 GB). La quota di avviso degli elementi recuperabili viene aumentata anche da 10 GB (da 90 GB a 100 GB). Queste modifiche sono applicabili solo se la cassetta postale in attesa o assegnati a un criterio di conservazione di Office 365.
    
In questo spazio aggiuntivo viene aggiunto per evitare problemi di archiviazione che possono verificarsi prima che viene eseguito il provisioning dell'archivio di espansione automatica. Si noti che ulteriore spazio di archiviazione spazio *non è* aggiunto quando si abilita l'espansione automatica archiviazione per l'intera organizzazione, come descritto nella sezione precedente. 
  
1. [Connessione a Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554)
    
2. Eseguire il seguente comando in Exchange Online PowerShell per abilitare l'espansione automatica archiviazione per un utente specifico. Come indicato in precedenza, è necessario abilitare cassetta postale di archivio dell'utente (archivio principale) prima che è possibile attivare l'archiviazione per tale utente l'espansione automatica.
    
    ```
    Enable-Mailbox <user mailbox> -AutoExpandingArchive
    ```


> [!IMPORTANT]
> In una distribuzione ibrida di Exchange, è possibile utilizzare il comando **Enable-Mailbox AutoExpandingArchive** per abilitare l'archiviazione per specifici di un utente la cui cassetta postale principale è locale l'espansione automatica e delle relative cassette postali di archiviazione sono basata su cloud. Per abilitare l'espansione automatica archiviazione delle cassette postali di archiviazione basata su cloud in una distribuzione ibrida di Exchange, è necessario eseguire il comando **Set-OrganizationConfig AutoExpandingArchive** di Exchange Online PowerShell per abilitare l'espansione automatica archiviazione l'intera organizzazione. Se un utente del principale e cassette postali di archiviazione sono basate su cloud, è possibile utilizzare il comando **Enable-Mailbox AutoExpandingArchive** per abilitare l'espansione automatica archiviazione per l'utente specifico. 
  
## <a name="verify-that-auto-expanding-archiving-is-enabled"></a>Verificare che sia abilitata l'espansione automatica di archiviazione

Per verificare che l'espansione automatica archiviazione sia abilitato per l'organizzazione, eseguire il seguente comando in Exchange Online PowerShell.

```
Get-OrganizationConfig | FL AutoExpandingArchiveEnabled
```

Un valore pari a `True` indica che l'espansione automatica di archiviazione è abilitata per l'organizzazione. 
  
Per verificare che l'espansione automatica archiviazione sia attiva per un utente specifico, eseguire il seguente comando in Exchange Online PowerShell.
  
```
Get-Mailbox <user mailbox> | FL AutoExpandingArchiveEnabled
```
Un valore pari a `True` indica che l'espansione automatica di archiviazione è abilitata per l'utente. 
  
Dopo aver abilitato l'espansione automatica di archiviazione, tenere presenti i seguenti aspetti:
  
- Se si esegue il comando **Set-OrganizationConfig AutoExpandingArchive** per abilitare l'espansione automatica archiviazione per l'organizzazione, non è necessario eseguire **Enable-Mailbox AutoExpandingArchive** per singole cassette postali. Si noti che l'esecuzione del cmdlet **Set-OrganizationConfig** per abilitare l'espansione automatica archiviazione per l'organizzazione non modifica la proprietà *AutoExpandingArchiveEnabled* cassette postali degli utenti a `True`.
    
- Analogamente, i valori delle proprietà della cassetta postale *ArchiveQuota* e *ArchiveWarningQuota* non vengono modificati quando si abilita l'espansione automatica archiviazione. In realtà, quando si abilita l'espansione automatica archiviazione per una cassetta postale utente e la proprietà *AutoExpandingArchiveEnabled* è impostata su `True`, le proprietà *ArchiveQuota* e *ArchiveWarningQuota* appena vengono ignorate. Di seguito è riportato un esempio di queste proprietà della cassetta postale dopo l'espansione automatica archiviazione è abilitata per la cassetta postale dell'utente. 
    
    ![ArchiveQuota e ArchiveWarningQuota vengono ignorate dopo aver abilitato l'espansione automatica di archiviazione](media/6a1c1b69-5c4c-4267-aac8-53577667f03e.png)

  
## <a name="more-information"></a>Ulteriori informazioni

- È inoltre possibile utilizzare PowerShell per abilitare cassette postali di archiviazione. Ad esempio, è possibile eseguire il comando seguente in Exchange Online PowerShell per abilitare cassette postali di archiviazione per tutti gli utenti la cui cassetta postale di archiviazione non è già abilitato.

    ```
    Get-Mailbox -Filter {ArchiveStatus -Eq "None" -AND RecipientTypeDetails -eq "UserMailbox"} | Enable-Mailbox -Archive
    ```

- Dopo aver attivato l'espansione automatica di archiviazione per l'organizzazione o di un utente specifico, una cassetta postale di archiviazione viene convertita in un archivio per l'espansione automatica quando la cassetta postale di archiviazione (inclusi la cartella elementi ripristinabili) raggiunge 90 GB. Può richiedere fino a 30 giorni per lo spazio di archiviazione aggiuntiva effettuare il provisioning.
    
- Dopo aver attivato l'archiviazione l'espansione automatica, non può essere disattivata.
    
- L'espansione automatica di archiviazione è supportato per le cassette postali di archiviazione basata su cloud in una distribuzione ibrida di Exchange per gli utenti che dispongono di una cassetta postale principale in locale. Tuttavia, dopo l'espansione automatica di archiviazione è abilitata per una cassetta postale di archiviazione basata sul cloud, è non può disattivare-area tale cassetta postale di archivio back all'organizzazione di Exchange locale.
    
- Per un elenco dei client di Outlook che gli utenti possono utilizzare per accedere agli elementi nell'area di ulteriore spazio di archiviazione nella cassetta postale di archiviazione, vedere la sezione "Requisiti di Outlook per accedere agli elementi in un archivio espanse automaticamente" in [Overview of illimitato archiviazione in Office 365](unlimited-archiving.md#outlook-requirements-for-accessing-items-in-an-auto-expanded-archive) .
    
- Come spiegato in precedenza, per la quota di archiviazione della cassetta postale di archivio principale dell'utente viene aggiunto 10 GB (e per la cartella elementi recuperabili se la cassetta postale è in attesa) quando si esegue il comando **AutoExpandingArchive Enable-Mailbox** . In tal modo spazio di archiviazione aggiuntivo fino a quando non lo spazio di archiviazione automatica espansa viene effettuato il provisioning (che può richiedere fino a 30 giorni). Questo ulteriore spazio di archiviazione non viene aggiunto durante l'esecuzione di **Set-OrganizationConfig AutoExpandingArchive** per abilitare l'espansione automatica archiviazione per tutte le cassette postali nell'organizzazione. Se è abilitata l'espansione automatica di archiviazione per l'intera organizzazione, ma è necessario aggiungere altri 10 GB di spazio di archiviazione per un utente specifico, è possibile eseguire il comando **Enable-Mailbox AutoExpandingArchive** nella cassetta postale. Si noti che verrà visualizzato un errore indicante che espansione automatica è già stata abilitata l'archiviazione, ma lo spazio di archiviazione aggiuntivo verrà aggiunto alla cassetta postale. 
