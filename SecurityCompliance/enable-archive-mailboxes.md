---
title: Abilitare le cassette postali di archiviazione nel &amp; Centro sicurezza e conformità di Office 365
ms.author: markjjo
author: markjjo
manager: laurawi
ms.audience: Admin
ms.topic: article
f1_keywords:
- ms.o365.cc.ArchivingHelp
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: 268a109e-7843-405b-bb3d-b9393b2342ce
description: Utilizzare il Centro sicurezza &amp; e conformità di Office 365 per abilitare le cassette postali di archiviazione per supportare i requisiti di conservazione, eDiscovery e blocco dei messaggi dell'organizzazione.
ms.openlocfilehash: 39cd5fd8d7991b787d95e39e4994dc9b0786522c
ms.sourcegitcommit: 48fa456981b5c52ab8aeace173c8366b9f36723b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/28/2019
ms.locfileid: "30341797"
---
# <a name="enable-archive-mailboxes-in-the-office-365-security-amp-compliance-center"></a>Abilitare le cassette postali di archiviazione nel &amp; Centro sicurezza e conformità di Office 365
  
L'archiviazione in Office 365 (detta anche archiviazione sul posto) fornisce agli utenti un ulteriore spazio di archiviazione per le cassette postali. Dopo aver attivato le cassette postali di archiviazione, gli utenti possono accedere e archiviare i messaggi nelle cassette postali di archiviazione utilizzando Microsoft Outlook e Outlook sul Web (in precedenza noto come Outlook Web App). Gli utenti possono anche spostare o copiare i messaggi tra la cassetta postale principale e la cassetta postale di archiviazione. È inoltre possibile recuperare gli elementi eliminati dalla cartella elementi ripristinabili nella cassetta postale di archiviazione utilizzando lo strumento Recupera elementi eliminati. 
  
> [!TIP]
> Office 365 fornisce una quantità illimitata di archivio di archiviazione con la funzionalità di archiviazione in espansione automatica. Quando l'archiviazione in espansione automatica è attivata e quindi viene raggiunta la quota di archiviazione iniziale in una cassetta postale di archivio dell'utente, Office 365 aggiunge automaticamente ulteriore spazio di archiviazione. Ciò significa che gli utenti non si esauriranno nello spazio di archiviazione delle cassette postali e non sarà necessario gestire nulla dopo aver inizialmente abilitato la cassetta postale di archiviazione e aver attivato l'espansione automatica dell'archiviazione per l'organizzazione. Per ulteriori informazioni, vedere [Overview of Unlimited Archiving in Office 365](unlimited-archiving.md). 
  
## <a name="before-you-begin"></a>Informazioni preliminari

Per abilitare o disabilitare le cassette postali di archiviazione, è necessario che venga assegnato il ruolo Mail Recipients in Exchange Online. Per impostazione predefinita, questo ruolo viene assegnato ai gruppi di ruoli Gestione destinatari e gestione organizzazione nella pagina **autorizzazioni** nell'interfaccia di amministrazione di Exchange. Se non si visualizza la pagina di **archiviazione** nel centro &amp; sicurezza e conformità, chiedere all'amministratore di assegnare le autorizzazioni necessarie. 
  
## <a name="enable-an-archive-mailbox"></a>Abilitazione di una cassetta postale di archiviazione
  
1. Passare a [https://protection.office.com](https://protection.office.com).
    
2. Accedere a Office 365 usando l'account aziendale o dell'istituto di istruzione.
    
3. &amp; Nel riquadro sinistro del Centro sicurezza e conformità fare clic su **Archivio**sulla governance **** \> dei dati.
    
    Viene visualizzata la pagina **Archivio**. La colonna **Cassetta postale di archiviazione** indica se una cassetta postale di archiviazione è abilitata o disabilitata per ciascun utente. 
    
4. Nell'elenco delle cassette postali, selezionare l'utente per il quale si desidera abilitare la cassetta postale di archiviazione.
    
    ![Fare clic su Abilita nel riquadro dei dettagli dell'utente selezionato per abilitare la cassetta postale di archiviazione](media/8b53cdec-d5c9-4c28-af11-611f95c37b34.png)
  
5. Nel riquadro dei dettagli per l'utente selezionato, fare clic su **Abilita**. 
    
    Viene visualizzato un messaggio di avviso che indica che se si Abilita la cassetta postale di archiviazione, gli elementi nella cassetta postale dell'utente precedenti al criterio di archiviazione assegnato alla cassetta postale verranno spostati nella nuova cassetta postale di archiviazione. Il criterio di archiviazione predefinito che fa parte del criterio di conservazione assegnato alle cassette postali di Exchange Online sposta gli elementi nella cassetta postale di archiviazione due anni dopo la data in cui l'elemento è stato recapitato alla cassetta postale o è stato creato dall'utente. Per ulteriori informazioni, vedere la sezione **altre informazioni** in questo articolo. 
    
6. Fare clic su **Sì** per abilitare la cassetta postale di archiviazione. 
    
    Potrebbe essere necessario qualche minuto per creare la cassetta postale di archiviazione. Quando viene creata, la **cassetta postale di archiviazione: abilitata** viene visualizzata nel riquadro dei dettagli per l'utente selezionato. Potrebbe essere necessario fare clic **** ![su Aggiorna l'](media/O365-MDM-Policy-RefreshIcon.gif) icona Aggiorna per aggiornare le informazioni nel riquadro dei dettagli. 
    
> [!TIP]
> È anche possibile abilitare in blocco le cassette postali di archiviazione selezionando più utenti con cassette postali di archiviazione disabilitate (con i tasti Maiusc o Ctrl). Dopo aver selezionato più cassette postali, fare clic su **Abilita** nel riquadro dei dettagli.  
  
## <a name="disable-an-archive-mailbox"></a>Disabilitazione di una cassetta postale di archiviazione
  
È inoltre possibile utilizzare la pagina di **archiviazione** nel centro &amp; sicurezza e conformità per disabilitare la cassetta postale di archiviazione di un utente. Dopo la disattivazione di una cassetta postale di archiviazione, è possibile riconnetterla alla cassetta postale principale dell'utente entro 30 giorni dalla disattivazione. In questo caso, il contenuto originale della cassetta postale di archiviazione viene ripristinato. Dopo 30 giorni, i contenuti della cassetta postale di archiviazione originale vengono eliminati definitivamente e non possono essere recuperati. Pertanto, se si riabilita l'archivio più di 30 giorni dopo averlo disabilitato, viene creata una nuova cassetta postale di archiviazione. 
  
Si noti che il criterio di archiviazione predefinito assegnato alle cassette postali degli utenti sposta gli elementi nella cassetta postale di archiviazione due anni dopo la data in cui l'elemento viene recapitato. Se si disattiva la cassetta postale di archiviazione di un utente, non verrà eseguita alcuna azione sugli elementi della cassetta postale e rimarranno nella cassetta postale principale dell'utente.
  
Per disabilitare una cassetta postale di archiviazione:
  
1. Passare a [https://protection.office.com](https://protection.office.com).
    
2. Accedere a Office 365 usando l'account aziendale o dell'istituto di istruzione.
    
3. &amp; Nel riquadro sinistro del Centro sicurezza e conformità fare clic su **Archivio**sulla governance **** \> dei dati.
    
    Viene visualizzata la pagina **Archivio**. La colonna **Cassetta postale di archiviazione** indica se una cassetta postale di archiviazione è abilitata o disabilitata per ciascun utente. 
    
4. Nell'elenco delle cassette postali, selezionare l'utente per il quale si desidera disabilitare la cassetta postale di archiviazione.
    
5. Nel riquadro dei dettagli, fare clic su **Disabilita**.  
    
    Viene visualizzato un messaggio di avviso che indica che avrai 30 giorni per riattivare la cassetta postale di archiviazione e che dopo 30 giorni tutte le informazioni nell'archivio verranno eliminate definitivamente. 
    
6. Scegliere **Sì** per disabilitare la cassetta postale di archiviazione. 
    
    La disattivazione della cassetta postale di archiviazione potrebbe richiedere alcuni istanti. Quando è disabilitata, la **cassetta postale di archiviazione:** disattivata viene visualizzata nel riquadro dei dettagli per l'utente selezionato. Potrebbe essere necessario fare clic **** ![su Aggiorna l'](media/O365-MDM-Policy-RefreshIcon.gif) icona Aggiorna per aggiornare le informazioni nel riquadro dei dettagli. 
    
> [!TIP]
> È anche possibile disabilitare in blocco le cassette postali di archiviazione selezionando più utenti con cassette postali di archiviazione abilitate (con i tasti Maiusc o Ctrl). Dopo aver selezionato più cassette postali, fare clic su **Disabilita** nel riquadro dei dettagli.  
  
## <a name="use-exchange-online-powershell-to-enable-or-disable-archive-mailboxes"></a>Utilizzo di PowerShell di Exchange Online per abilitare o disabilitare le cassette postali di archiviazione

È inoltre possibile utilizzare PowerShell di Exchange Online per abilitare le cassette postali di archiviazione. Il motivo principale dell'utilizzo di PowerShell è la possibilità di abilitare rapidamente la cassetta postale di archiviazione per tutti gli utenti dell'organizzazione.

Il primo passaggio consiste nel connettersi a PowerShell di Exchange Online. Per istruzioni, vedere [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).

Dopo aver effettuato la connessione a Exchange Online, è possibile eseguire i comandi nelle sezioni seguenti per abilitare o disabilitare le cassette postali di archiviazione.

### <a name="enable-archive-mailboxes"></a>Abilitare le cassette postali di archiviazione

Per abilitare la cassetta postale di archiviazione per un singolo utente, eseguire il comando riportato di seguito.
    
  ```
  Enable-Mailbox -Identity <username> -Archive
  ```

Eseguire il seguente comando per abilitare la cassetta postale di archiviazione per tutti gli utenti dell'organizzazione (la cui cassetta postale di archiviazione non è attualmente abilitata).
    
  ```
  Get-Mailbox -Filter {ArchiveStatus -Eq "None" -AND RecipientTypeDetails -eq "UserMailbox"} | Enable-Mailbox -Archive
  ```
  
### <a name="disable-archive-mailboxes"></a>Disabilitare le cassette postali di archiviazione

Per disabilitare la cassetta postale di archiviazione per un singolo utente, eseguire il comando riportato di seguito.
    
  ```
  Disable-Mailbox -Identity <username> -Archive
  ```

Eseguire il seguente comando per disabilitare la cassetta postale di archiviazione per tutti gli utenti dell'organizzazione (la cui cassetta postale di archiviazione è attualmente abilitata).
    
  ```
  Get-Mailbox -Filter {ArchiveStatus -Eq "Active" -AND RecipientTypeDetails -eq "UserMailbox"} | Disable-Mailbox -Archive
  ```

## <a name="more-information"></a>Ulteriori informazioni
  
- Le cassette postali di archiviazione consentono a tutti gli utenti di soddisfare i requisiti di conservazione, eDiscovery e mantenimento dell'organizzazione. Ad esempio, è possibile utilizzare i criteri di conservazione di Exchange dell'organizzazione per spostare il contenuto delle cassette postali nella cassetta postale di archiviazione degli utenti. Quando si utilizza lo strumento di ricerca contenuto nel centro &amp; sicurezza e conformità per cercare contenuto specifico in una cassetta postale di un utente, verrà eseguita la ricerca anche nella cassetta postale di archiviazione dell'utente. Inoltre, quando si attiva un blocco per controversia legale o si applica un criterio di conservazione di Office 365 alla cassetta postale di un utente, vengono conservati anche gli elementi della cassetta postale di archiviazione.
  
- Quando una cassetta postale di archiviazione è abilitata, gli utenti possono archiviare i messaggi nella loro cassetta postale di archiviazione. Gli utenti possono accedere alle proprie cassette postali di archiviazione utilizzando Microsoft Outlook e Outlook sul Web. Se si utilizza una di queste applicazioni client, gli utenti possono visualizzare i messaggi nella cassetta postale di archiviazione e spostare o copiare i messaggi tra la cassetta postale principale e la cassetta postale di archiviazione. Gli utenti possono anche recuperare gli elementi eliminati dalla cartella elementi ripristinabili nella cassetta postale di archiviazione utilizzando lo strumento Recupera elementi eliminati. 
  
- Dopo che le cassette postali di archiviazione sono abilitate, l'organizzazione può usufruire dei criteri di conservazione di Exchange predefiniti (denominati anche criteri di gestione dei record di messaggistica) assegnati automaticamente a tutte le cassette postali. Quando una cassetta postale di archiviazione è abilitata, il criterio di conservazione di Exchange predefinito esegue automaticamente le operazioni seguenti: 
  
    - Sposta gli elementi di almeno due anni dalla cassetta postale principale dell'utente alla cassetta postale di archiviazione. 
    
    - Sposta gli elementi di almeno 14 giorni dalla cartella Elementi ripristinabili nella cassetta postale principale dell'utente alla cartella Elementi ripristinabili nella cassetta postale di archiviazione.
    
- Per ulteriori informazioni sulle cassette postali di archiviazione e sui criteri di conservazione di Exchange, vedere:
    
  - [Tag di conservazione e criteri di conservazione](https://go.microsoft.com/fwlink/?LinkId=404424)
    
  - [Criteri di conservazione predefiniti in Exchange Online](https://go.microsoft.com/fwlink/?linkid=839418)
    
  - [Configurare un criterio di archiviazione ed eliminazione per le cassette postali nell'organizzazione di Office 365](set-up-an-archive-and-deletion-policy-for-mailboxes.md)
