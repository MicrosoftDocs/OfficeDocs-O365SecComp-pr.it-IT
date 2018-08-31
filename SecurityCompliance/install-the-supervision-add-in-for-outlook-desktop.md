---
title: Installare il componente aggiuntivo Supervisione per Outlook desktop
ms.author: brendonb
author: brendonb
manager: laurawi
ms.date: 6/19/2017
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
- ZOL160
ms.assetid: 6c5620e6-aba3-4910-8f3a-b55451656ff7
description: Installare il componente aggiuntivo di Office 365 supervisione per la versione desktop di Outlook
ms.openlocfilehash: 0bddf305087bf0d9552c7671da5306db8352143f
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/27/2018
ms.locfileid: "22530312"
---
# <a name="install-the-supervision-add-in-for-outlook-desktop"></a>Installare il componente aggiuntivo Supervisione per Outlook desktop

Per esaminare communications identificato da un criterio di supervisione, utilizzare i revisori la supervisione componente aggiuntivo per Outlook e Outlook web app. Il componente aggiuntivo viene installato automaticamente in Outlook web app per tutti i revisori specificato nel criterio. Tuttavia, i revisori devono eseguire alcuni passaggi per installare la versione desktop di Outlook.
  
> [!NOTE]
> Utilizzo dei criteri di supervisione richiede una sottoscrizione a Office 365 E5 per l'organizzazione. Se non sono dial plan e desidera provare supervisione, è possibile [iscrizione a una versione di valutazione di Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279). 
  
## <a name="step-1-copy-the-address-for-the-supervision-mailbox"></a>Passaggio 1: Copiare l'indirizzo della cassetta postale di supervisione

Per installare il componente aggiuntivo per desktop Outlook, è necessario l'indirizzo della cassetta postale di supervisione che è stata creata come parte dell'impostazione di criteri di supervisione. 
  
> [!NOTE]
> Se qualcuno altre posizioni creato il criterio, sarà necessario ottenere questo indirizzo da loro di installare il componente aggiuntivo. 
  
 **Per trovare l'indirizzo della cassetta postale di supervisione**
  
1. Accedere al [protezione &amp; centro conformità](https://protection.office.com) utilizzando le credenziali per un account di amministratore dell'organizzazione Office 365. 
    
2. Andare alla **governance dati** \> **supervisione**.
    
3. Fare clic sui criteri di supervisione che sono la raccolta delle comunicazioni da controllare.
    
4. Nel criterio in dettaglio comparsa, in * * cassetta postale di supervisione * *, copiare l'indirizzo. 
    
    ![La sezione 'Supervisione delle cassette postali' dell'elemento libero dei dettagli di criteri di supervisione che mostra l'indirizzo della cassetta postale di supervisione posti in evidenza](media/71779d0e-4f01-4dd3-8234-5f9c30eeb067.jpg)
  
## <a name="step-2-configure-the-supervision-mailbox-for-outlook-desktop-access"></a>Passaggio 2: Configurare la cassetta postale di supervisione per l'accesso desktop Outlook

Successivamente, saranno necessario eseguire alcuni comandi di Exchange Online PowerShell in modo da Outlook può connettersi alla cassetta postale di supervisione revisori.
  
1. Connessione a Exchange Online PowerShell. [Come eseguire l'operazione?](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)
    
2. Eseguire i comandi riportati di seguito.
    
  ```
  Add-MailboxPermission "SupervisoryReview{GUID}@domain.onmicrosoft.com" -User <alias or email address of the account that has reviewer permissions to the supervision mailbox> -AccessRights FullAccessSet-Mailbox "<SupervisoryReview{GUID}@domain.onmicrosoft.com>" -HiddenFromAddressListsEnabled: $false
  ```

    Dove *SupervisoryReview{GUID}@domain.onmicrosoft.com* è l'indirizzo che è stato copiato nel passaggio 1 sopra e *utente* è il nome del revisore che si connettono alla cassetta postale di supervisione nel passaggio successivo. 
    
3. Attendere almeno un'ora prima di passare al passaggio 3 sotto.
    
## <a name="step-3-create-an-outlook-profile-to-connect-to-the-supervision-mailbox"></a>Passaggio 3: Creare un profilo di Outlook per connettersi alla cassetta postale di supervisione

Per il passaggio finale, i revisori saranno necessario creare un profilo di Outlook per connettersi alla cassetta postale di supervisione. 
  
> [!NOTE]
> Per creare un nuovo profilo di Outlook, si utilizzerà le impostazioni di posta elettronica nel Pannello di controllo di Windows. Il percorso che è eseguire per accedere a queste impostazioni può dipendono dal sistema operativo Windows (Windows 7, Windows 8 o Windows 10) si utilizza e la versione di Outlook installata. 
  
1. Aprire il pannello di controllo e nella casella di **ricerca** nella parte superiore della finestra digitare **Mail**. 
    
    > [!NOTE]
    > Non che come ottenere il pannello di controllo? Vedere [dove è Pannello di controllo?](https://support.microsoft.com/help/13764/windows-where-is-control-panel)
  
2. Aprire l'app di **posta elettronica** . 
    
3. In **Impostazioni di posta - Outlook**fare clic su **Mostra profili**.
    
    !['Configurazione della posta - Outlook' la finestra di dialogo con il pulsante Mostra profili posti in evidenza](media/28b5dae9-d10c-4f2b-926a-294c857d555c.jpg)
  
4. Nella **posta elettronica**, fare clic su **Aggiungi**. Quindi, nel **Nuovo profilo**, immettere un nome per la cassetta postale supervisione (ad esempio **supervisione**).
    
    ![La finestra di dialogo "Nuovo profilo" la visualizzazione del nome 'Supervisione' nella casella "Nome del profilo"](media/d02ae181-b541-4ec6-8f51-698f30033204.jpg)
  
5. In **Outlook la connessione a Office 365**, fare clic su **Connetti a un account diverso**.
    
    ![Il messaggio 'Outlook connettersi a Office 365' con il collegamento a "Connetti a un altro account" evidenziato](media/fac49ff8-a7f0-4e82-a271-9ec045a95de1.jpg)
  
6. Nella **Configurazione automatica Account**, selezionare **installazione manuale o tipi di server aggiuntivi**e quindi fare clic su **Avanti**.
    
7. **Scegliere il tipo di Account**, selezionare **Office 365**. Quindi, nella casella **Indirizzo di posta elettronica** , immettere l'indirizzo della cassetta postale di supervisione che è stato copiato in precedenza. 
    
    ![La pagina "Scegliere il tipo di Account" della finestra di dialogo Aggiungi Account in Outlook che mostra la casella "Indirizzo di posta elettronica" evidenziata.](media/4f601236-9f69-4cf6-a58c-0b91204aa8cb.jpg)
  
8. Quando richiesto, immettere le credenziali di Office 365.
    
9. Se ha esito positivo, verrà visualizzato il **supervisione - \<nome criterio\> ** cartella elencata nella visualizzazione elenco cartelle in Outlook. 
    

