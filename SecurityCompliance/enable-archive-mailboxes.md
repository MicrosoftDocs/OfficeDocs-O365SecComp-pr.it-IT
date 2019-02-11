---
title: Abilitare cassette postali di archiviazione in Office 365 Security &amp; centro conformità
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
ms.audience: Admin
ms.topic: article
f1_keywords:
- ms.o365.cc.ArchivingHelp
ms.service: o365-administration
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MET150
ms.assetid: 268a109e-7843-405b-bb3d-b9393b2342ce
description: Utilizzare la protezione di Office 365 &amp; centro conformità per abilitare cassette postali di archiviazione per il supporto di conservazione dei messaggi della propria organizzazione, eDiscovery e i requisiti di archiviazione.
ms.openlocfilehash: 1c290cf19b396221dac702efd1395911e8a51631
ms.sourcegitcommit: 7e2a0185cadea7f3a6afc5ddc445eac2e1ce22eb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/11/2019
ms.locfileid: "28327098"
---
# <a name="enable-archive-mailboxes-in-the-office-365-security-amp-compliance-center"></a>Abilitare cassette postali di archiviazione in Office 365 Security &amp; centro conformità
  
Archiviazione in Office 365 (denominato anche l'archiviazione sul posto) fornisce agli utenti con lo spazio di archiviazione aggiuntivi delle cassette postali. Dopo avere attivato cassette postali di archiviazione, gli utenti possono accedere e archiviare i messaggi nelle cassette postali di archiviazione utilizzando Microsoft Outlook e gli utenti di Outlook Web App possono anche spostare o copiare messaggi tra loro cassetta postale di archiviazione e delle relative cassette postali principali. È inoltre possibile ripristinare gli elementi eliminati dalla cartella elementi ripristinabili nella cassetta postale di archivio mediante lo strumento Recupera posta eliminata. 
  
> [!TIP]
> Office 365 fornisce una quantità di spazio di archiviazione di archiviazione con la caratteristica archiviazione espansione automatica illimitata. Quando è attivata l'espansione automatica di archiviazione e quindi viene raggiunto la quota di archiviazione iniziali nella cassetta postale di archivio dell'utente, Office 365 automaticamente aggiunge ulteriore spazio di archiviazione. Ciò significa che gli utenti non si esaurisca lo spazio di archiviazione delle cassette postali e non sarà necessario gestire lasciare dopo aver inizialmente abilitare la cassetta postale di archiviazione e attivare l'archiviazione per l'organizzazione l'espansione automatica. Per ulteriori informazioni, vedere [Overview of archiviazione illimitato in Office 365](unlimited-archiving.md). 
  
## <a name="before-you-begin"></a>Prima di iniziare

È necessario essere assegnato il ruolo destinatari di posta elettronica di Exchange Online per abilitare o disabilitare cassette postali di archiviazione. Per impostazione predefinita, questo ruolo viene assegnato ai gruppi di ruolo Recipient Management e la gestione dell'organizzazione nella pagina **autorizzazioni** nell'interfaccia di amministrazione di Exchange. Se non è visualizzata la pagina di **archivio** nel titolo &amp; del centro conformità, chiedere all'amministratore di assegnare le autorizzazioni necessarie. 
  
## <a name="enable-an-archive-mailbox"></a>Abilitazione di una cassetta postale di archiviazione
  
1. Passare a [https://protection.office.com](https://protection.office.com).
    
2. Accedere a Office 365 usando l'account aziendale o dell'istituto di istruzione.
    
3. Nel riquadro sinistro della sicurezza &amp; centro conformità, fare clic su **governance dati** \> **Archive**.
    
    Viene visualizzata la pagina **Archivio**. La colonna **Cassetta postale di archiviazione** indica se una cassetta postale di archiviazione è abilitata o disabilitata per ciascun utente. 
    
4. Nell'elenco delle cassette postali, selezionare l'utente per il quale si desidera abilitare la cassetta postale di archiviazione.
    
    ![Fare clic su attiva nel riquadro dei dettagli dell'utente selezionato per abilitare la cassetta postale di archiviazione](media/8b53cdec-d5c9-4c28-af11-611f95c37b34.png)
  
5. Nel riquadro dei dettagli per l'utente selezionato, fare clic su **Attiva**. 
    
    Viene visualizzato un avviso indicante che se si abilita la cassetta postale di archiviazione, gli elementi nella cassetta postale dell'utente che hanno superati il criterio di archiviazione assegnato alla cassetta postale verranno spostati la nuova cassetta postale di archiviazione. I criteri di archiviazione predefiniti che fa parte del criterio di conservazione assegnato alle cassette postali di Exchange Online Sposta gli elementi nella cassetta postale di archivio di due anni dopo la data, l'elemento è stato recapitato alla cassetta postale o creato dall'utente. Per ulteriori informazioni, vedere la sezione **ulteriori informazioni** in questo articolo. 
    
6. Fare clic su **Sì** per abilitare la cassetta postale di archiviazione. 
    
    Potrebbe richiedere qualche minuto per creare la cassetta postale di archivio. Quando si crea, **cassetta postale di archiviazione: abilitato** viene visualizzato nel riquadro dei dettagli per l'utente selezionato. Potrebbe essere necessario fare clic su **Aggiorna** ![icona Aggiorna](media/O365-MDM-Policy-RefreshIcon.gif) per aggiornare le informazioni nel riquadro dei dettagli. 
    
> [!TIP]
> È anche possibile abilitare in blocco le cassette postali di archiviazione selezionando più utenti con cassette postali di archiviazione disabilitate (con i tasti Maiusc o Ctrl). Dopo aver selezionato più cassette postali, fare clic su **Abilita** nel riquadro dei dettagli.  
  
## <a name="disable-an-archive-mailbox"></a>Disabilitazione di una cassetta postale di archiviazione
  
Utilizzare la pagina di **archiviazione** per la protezione &amp; centro conformità per disabilitare la cassetta postale di archivio dell'utente. Dopo la disattivazione di una cassetta postale di archiviazione, è possibile riconnettersi alla cassetta postale principale dell'utente entro 30 giorni di disattivarlo. In questo caso, il contenuto originale della cassetta postale di archiviazione viene ripristinato. Dopo 30 giorni, il contenuto della cassetta postale di archivio originale viene eliminato definitivamente e non può essere ripristinato. In modo che se si riabilita l'archivio di più di 30 giorni dopo la disattivazione, viene creata una nuova cassetta postale di archivio. 
  
Si noti che il criterio di archiviazione predefinito assegnato alle cassette postali degli utenti elementi si sposta la cassetta postale di archiviazione due anni dopo la data l'elemento viene recapitato. Se si disabilita cassetta postale di archivio dell'utente, verrà eseguita alcuna azione sugli elementi delle cassette postali e rimangono nella cassetta postale principale dell'utente.
  
Per disabilitare una cassetta postale di archiviazione:
  
1. Passare a [https://protection.office.com](https://protection.office.com).
    
2. Accedere a Office 365 usando l'account aziendale o dell'istituto di istruzione.
    
3. Nel riquadro sinistro della sicurezza &amp; centro conformità, fare clic su **governance dati** \> **Archive**.
    
    Viene visualizzata la pagina **Archivio**. La colonna **Cassetta postale di archiviazione** indica se una cassetta postale di archiviazione è abilitata o disabilitata per ciascun utente. 
    
4. Nell'elenco delle cassette postali, selezionare l'utente per il quale si desidera disabilitare la cassetta postale di archiviazione.
    
5. Nel riquadro dei dettagli, fare clic su **Disabilita**.  
    
    Viene visualizzato un messaggio di avviso indicante che è necessario 30 giorni per riattivare la cassetta postale di archivio e che dopo 30 giorni, tutte le informazioni dell'archivio verranno eliminate definitivamente. 
    
6. Scegliere **Sì** per disabilitare la cassetta postale di archiviazione. 
    
    Potrebbe richiedere qualche minuto per disabilitare la cassetta postale di archivio. Quando è disabilitato, **cassetta postale di archiviazione: disabilitato** viene visualizzato nel riquadro dei dettagli per l'utente selezionato. Potrebbe essere necessario fare clic su **Aggiorna** ![icona Aggiorna](media/O365-MDM-Policy-RefreshIcon.gif) per aggiornare le informazioni nel riquadro dei dettagli. 
    
> [!TIP]
> È anche possibile disabilitare in blocco le cassette postali di archiviazione selezionando più utenti con cassette postali di archiviazione abilitate (con i tasti Maiusc o Ctrl). Dopo aver selezionato più cassette postali, fare clic su **Disabilita** nel riquadro dei dettagli.  
  
## <a name="use-exchange-online-powershell-to-enable-or-disable-archive-mailboxes"></a>Utilizzare Exchange Online PowerShell per abilitare o disabilitare l'archiviazione delle cassette postali

È inoltre possibile utilizzare Exchange Online PowerShell per abilitare cassette postali di archiviazione. Il motivo principale per l'utilizzo di PowerShell è che è possibile attivare rapidamente la cassetta postale di archiviazione per tutti gli utenti nell'organizzazione.

Il primo passaggio consiste nel connettere a Exchange Online PowerShell. Per ulteriori informazioni, vedere [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).

Dopo che si è connessi a Exchange Online, è possibile eseguire i comandi nelle sezioni seguenti per abilitare o disabilitare cassette postali di archiviazione.

### <a name="enable-archive-mailboxes"></a>Abilitare le cassette postali di archiviazione

Eseguire il comando seguente per abilitare la cassetta postale di archiviazione per un singolo utente.
    
  ```
  Enable-Mailbox -Identity <username> -Archive
  ```

Eseguire il comando seguente per abilitare la cassetta postale di archiviazione per tutti gli utenti all'interno dell'organizzazione (la cui cassetta postale di archiviazione non abilitato).
    
  ```
  Get-Mailbox -Filter {ArchiveStatus -Eq "None" -AND RecipientTypeDetails -eq "UserMailbox"} | Enable-Mailbox -Archive
  ```
  
### <a name="disable-archive-mailboxes"></a>Disabilitare le cassette postali di archiviazione

Eseguire il seguente comando per disabilitare la cassetta postale di archiviazione per un singolo utente.
    
  ```
  Disable-Mailbox -Identity <username> -Archive
  ```

Eseguire il seguente comando per disabilitare la cassetta postale di archiviazione per tutti gli utenti all'interno dell'organizzazione (la cui cassetta postale di archiviazione è attualmente abilitato).
    
  ```
  Get-Mailbox -Filter {ArchiveStatus -Eq "Active" -AND RecipientTypeDetails -eq "UserMailbox"} | Disable-Mailbox -Archive
  ```

## <a name="more-information"></a>Ulteriori informazioni
  
- Cassette postali di archiviazione consentono all'utente e gli utenti per soddisfare conservazione dell'organizzazione, eDiscovery e i requisiti di archiviazione. Ad esempio, è possibile utilizzare criteri di conservazione dell'organizzazione Exchange per spostare il contenuto delle cassette postali cassetta postale degli utenti di archiviazione. Quando si utilizza lo strumento di ricerca di contenuto per la protezione &amp; centro conformità per la ricerca di postale una cassetta per il contenuto specifico, cassetta postale di archivio dell'utente è anche possibile ricercare. E, quando si effettua una conservazione per controversia legale o applicare un criterio di conservazione di Office 365 per postale una cassetta, vengono mantenuti anche gli elementi nella cassetta postale di archivio.
  
- Quando una cassetta postale di archiviazione è abilitata, gli utenti possono archiviare i messaggi nella cassetta postale di archivio. Gli utenti possono accedere alle cassette postali di archiviazione utilizzando Microsoft Outlook e Outlook Web App utilizzando uno di tali applicazioni client, gli utenti possono visualizzare messaggi nella cassetta postale di archiviazione e spostare o copiare i messaggi tra cassette postali primarie e delle relative cassette postali di archiviazione. Gli utenti possono ripristinare anche gli elementi eliminati dalla cartella elementi ripristinabili nella cassetta postale di archiviazione mediante lo strumento Recupera posta eliminata. 
  
- Dopo l'archiviazione delle cassette postali sono abilitate, l'organizzazione può trarre vantaggio Exchange criterio di conservazione predefinito (denominato anche criteri di gestione dei record di messaggistica o MRM) che viene automaticamente assegnato a tutte le cassette postali. Quando una cassetta postale di archiviazione è abilitata, il criterio di conservazione predefinito Exchange esegue automaticamente le operazioni seguenti: 
  
    - Sposta gli elementi di almeno due anni dalla cassetta postale principale dell'utente alla cassetta postale di archiviazione. 
    
    - Sposta gli elementi di almeno 14 giorni dalla cartella Elementi ripristinabili nella cassetta postale principale dell'utente alla cartella Elementi ripristinabili nella cassetta postale di archiviazione.
    
- Per ulteriori informazioni sulle cassette postali di archiviazione e dei criteri di conservazione di Exchange, vedere:
  
    
  - [Tag di conservazione e criteri di conservazione](https://go.microsoft.com/fwlink/?LinkId=404424)
    
  - [Default criterio di conservazione in Exchange Online](https://go.microsoft.com/fwlink/?linkid=839418)
    
  - [Configurare un criterio di archiviazione e l'eliminazione delle cassette postali nell'organizzazione Office 365](set-up-an-archive-and-deletion-policy-for-mailboxes.md)
