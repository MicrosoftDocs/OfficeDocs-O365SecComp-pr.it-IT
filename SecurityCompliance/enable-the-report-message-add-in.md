---
title: Attivare il componente aggiuntivo Report Message
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 2/28/2018
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 4250c4bc-6102-420b-9e0a-a95064837676
description: Informazioni su come abilitare il componente aggiuntivo di report per Outlook e Outlook sul web, per i singoli utenti o l'intera organizzazione.
ms.openlocfilehash: 2260f8823132d23e0e1f57a421fd223ea3ab14bd
ms.sourcegitcommit: edf5db9357c0d34573f8cc406314525ef10d1eb9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/28/2018
ms.locfileid: "23229998"
---
# <a name="enable-the-report-message-add-in"></a>Attivare il componente aggiuntivo Report Message

Il componente aggiuntivo di report per Outlook consente agli utenti di comunicare facilmente e-mail classificazioni non corrette, se attendibili o volontario, con Microsoft e consociate per l'analisi. Questi invii utilizzate da Microsoft per migliorare l'efficienza delle tecnologie di protezione della posta elettronica.
  
Se si è un singolo utente, è possibile abilitare il componente aggiuntivo di report per se stessi. 
  
Se si è un amministratore di Exchange Online, è possibile abilitare il componente aggiuntivo di report per l'organizzazione.
    
## <a name="get-the-report-message-add-in-for-yourself"></a>Ottenere il messaggio di rapporto componente aggiuntivo per se stessi

1. Accedere a [https://store.office.com](https://store.office.com)e la ricerca per il componente aggiuntivo di report.
    
2. Scegliere **non perdere** (o **Aggiungi** ). 
    
3. Leggere le condizioni di utilizzo e sulla privacy. Quindi fare clic su **Continua**. 
    
4. Accedere alla posta elettronica di Office 365 utilizzando il proprio lavoro o scuola account (per l'utilizzo business) o l'account Microsoft (per utilizzo personale).
    
Dopo che il componente aggiuntivo è installato e attivato, si noterà icone riportate di seguito: 

- In Outlook l'icona simile al seguente: </br> ![Icona messaggio componente aggiuntivo di report per Outlook](media/OutlookReportMessageIcon.png)</br>
- In Outlook Web App l'icona simile al seguente:</br>![Icona messaggio Report Web componente aggiuntivo per Outlook](media/d9326d0b-1769-4bc2-ae58-51f0ebc69a17.png)</br>

  
In una fase successiva, informazioni su come [utilizzare il componente aggiuntivo di report](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2).
  
## <a name="get-and-enable-the-report-message-add-in-for-your-organization"></a>Ottenere e abilitare il componente aggiuntivo di report per l'organizzazione

> [!IMPORTANT]
> È necessario essere un amministratore di Exchange Online per eseguire questa attività.
  
1. Accedere a [https://portal.office.com](https://portal.office.com) e accedere utilizzando l'account di lavoro o della scuola. 
    
2. Scegliere **amministrazione** passare al centro di amministrazione. 
    
3. Scegliere **Admin Center** \> **Exchange** per accedere all'interfaccia di amministrazione di Exchange (EAC). 
    
4. Scegliere **organizzazione** \> **componenti aggiuntivi**. 
    
5. Scegliere **+** \> **aggiungere da Office Store**. 
    
6. Cercare di report.
    
7. Nell'elenco **dei risultati di App** trovare **Report messaggio**e quindi scegliere **non perdere** (o **Aggiungi** ). 
    
8. Leggere le condizioni di utilizzo e sulla privacy. Quindi fare clic su **Continua**. 
    
    ![Fare clic su Continua per accettare i termini e l'informativa sulla privacy](media/3c813cd6-1601-4791-97dc-f8edbbd3fb6b.png)
  
9. Nella schermata di conferma scegliere **Sì**. 
    
10. Dopo aver installato il componente aggiuntivo di report, è necessario abilitarla. A tale scopo, eseguire la procedura seguente:
    
1. Tornare a EAC e aggiornare la finestra del browser.
    
2. Scegliere **organizzazione** \> **componenti aggiuntivi**. 
    
3. Nell'elenco dei componenti aggiuntivi, selezionare **Messaggio del rapporto**. 
    
    ![In EAC, è possibile abilitare il componente aggiuntivo di report per Outlook](media/b496743c-55fa-4cdb-aa06-0b2a7aec6dab.png)
  
4. Fare clic su **Modifica**e scegliere un'opzione per abilitare il componente aggiuntivo. 
    
    ![Abilitare il componente aggiuntivo di report in EAC](media/578b1b66-3620-4a8a-9819-1c9cc6836f37.png)
  
5. Fare clic su **Salva**. 
    
> [!TIP]
> Dopo che il componente aggiuntivo è installato e abilitato, gli utenti dell'organizzazione verranno visualizzato le icone seguenti: 
  
Successivamente, informazioni su come [utilizzare il componente aggiuntivo di report](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2)e set di backup di una regola per visualizzare i messaggi di posta elettronica segnalate.
  
### <a name="set-up-a-rule-to-get-a-copy-of-email-messages-reported-by-your-users"></a>Impostare una regola per ottenere una copia dei messaggi di posta elettronica segnalati dagli utenti

> [!IMPORTANT]
> È necessario essere un amministratore di Exchange Online per eseguire questa attività.
  
È possibile impostare backup di una regola per ottenere una copia dei messaggi di posta elettronica segnalato dagli utenti nell'organizzazione. A tale scopo dopo avere scaricato e abilitato il componente aggiuntivo di report per l'organizzazione.
  
1. Amministrazione di Exchange, scegliere **flusso di posta** \> **regole**. 
    
2. Scegliere **+** \> **Crea una nuova regola**. 
    
3. Nella casella **nome** digitare un nome, ad esempio invii.
    
4. Nell'elenco **Applica questa regola se** , selezionare **l'indirizzo del destinatario include...**. 
    
5. Nella schermata **specificare parole o frasi** , aggiungere junk@office365.microsoft.com e phish@office365.microsoft.com e quindi fare clic su **OK**. 
    
    ![Specificare gli indirizzi di posta elettronica indesiderata e per attività di phishing per la regola](media/018c1833-f336-4333-a45c-f2e8b75cd698.png)
  
6. Nell'elenco **eseguire le operazioni seguenti...** scegliere **Ccn del messaggio per...**. 
    
7. Aggiungere un amministratore globale, amministratore della sicurezza e/o lettore di sicurezza che deve ricevere una copia di ogni messaggio di posta elettronica che gli utenti di segnalare a Microsoft e quindi fare clic su **OK**. 
    
    ![Aggiungere un amministratore globale o di protezione per la ricezione di una copia di ogni messaggio segnalata](media/a91ab9d1-66f2-4a2e-9dc1-f9f81a2298ad.png)
  
8. Selezionare **Controlla questa regola con livello di gravità**e scegliere **medio**. 
    
9. Nella casella **scegliere una modalità per la regola**, selezionare **Applica**. 
    
    ![Impostare una regola per ottenere una copia di ogni messaggio segnalata](media/f1cd95ce-e40d-4a8a-8f48-893469eba691.png)
  
10. Fare clic su **Salva**. 
    
Con questa regola, ogni volta che qualcuno all'interno dell'organizzazione segnala un messaggio di posta elettronica utilizzando il componente aggiuntivo di report, l'amministratore globale, amministratore della sicurezza e/o lettore di sicurezza riceverà una copia del messaggio. Queste informazioni possono consentono di configurare o modificare criteri, ad esempio i criteri di [Office 365 degli strumenti di analisi provvisoria collegamenti](atp-safe-links.md) . 
  
## <a name="related-topics"></a>Argomenti correlati

[Utilizzare il componente aggiuntivo di report](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2)
  
[Office 365 Advanced Threat Protection](office-365-atp.md)
  

