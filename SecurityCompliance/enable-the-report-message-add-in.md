---
title: Attivare il componente aggiuntivo Segnala messaggio
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 10/18/2018
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 4250c4bc-6102-420b-9e0a-a95064837676
description: Informazioni su come abilitare il componente aggiuntivo di report per Outlook e Outlook sul web, per i singoli utenti o l'intera organizzazione.
ms.openlocfilehash: 8c9853c78a42d6eecd0989475ef8f0a44345f812
ms.sourcegitcommit: ceb70ea863d8b97afea077a04fc7ec612b870695
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/31/2018
ms.locfileid: "25857264"
---
# <a name="enable-the-report-message-add-in"></a>Attivare il componente aggiuntivo Segnala messaggio

## <a name="overview"></a>Panoramica

Il componente aggiuntivo di report per Outlook e Outlook sul Web consente agli utenti di comunicare facilmente e-mail classificazioni non corrette, se attendibili o volontario, con Microsoft e consociate per l'analisi. Questi invii utilizzate da Microsoft per migliorare l'efficienza delle tecnologie di protezione della posta elettronica. Inoltre, se l'organizzazione utilizza [Protezione rischio avanzate di Office 365](office-365-atp.md) o [Business Intelligence di Office 365 rischio](office-365-ti.md), il componente aggiuntivo di report fornisce il team di protezione dell'organizzazione con informazioni utili, che è possibile utilizzare per esaminare e aggiornare criteri di protezione. 

Ad esempio, si supponga che le persone riportano una quantità elevata di messaggi di phishing. Nel [Dashboard di sicurezza](security-dashboard.md) e altri report le superfici di informazioni. Team di protezione dell'organizzazione possono utilizzare queste informazioni come indicazione che criteri anti-phishing potrebbero non essere aggiornate. In alternativa, se gli utenti sono report una quantità elevata di messaggi contrassegnati come posta indesiderata come posta non indesiderata tramite il componente aggiuntivo di report, team di protezione dell'organizzazione potrebbe essere necessario modificare [i criteri di protezione da posta indesiderati](configure-the-anti-spam-policies.md). 

Il componente aggiuntivo di report può essere utilizzato con la sottoscrizione a Office 365 e i prodotti seguenti:
 - Outlook sul Web
 - Outlook 2013 SP1
 - Outlook 2016
 - Outlook 2016 per Mac
 - Outlook inclusi in Office 365 ProPlus
  
Se si è un singolo utente, è possibile [abilitare il componente aggiuntivo di report per se stessi](#get-the-report-message-add-in-for-yourself). 
  
Se si è un amministratore di Exchange Online, è possibile [abilitare il componente aggiuntivo di report per l'organizzazione](#get-and-enable-the-report-message-add-in-for-your-organization).
    
## <a name="get-the-report-message-add-in-for-yourself"></a>Ottenere il messaggio di rapporto componente aggiuntivo per se stessi

1. In [Microsoft AppSource](https://appsource.microsoft.com/marketplace/apps), cercare il [componente aggiuntivo di report](https://appsource.microsoft.com/product/office/wa104381180).
    
2. Scegliere **ottenere subito**.<br/>![Report messaggio - Scarica ora](media/ReportMessageGETITNOW.png)<br/> 
    
3. Leggere le condizioni di utilizzo e sulla privacy. Quindi fare clic su **Continua**. 
    
4. Accedere alla posta elettronica di Office 365 utilizzando il proprio lavoro o scuola account (per l'utilizzo business) o l'account Microsoft (per utilizzo personale).
    

Dopo che il componente aggiuntivo è installato e attivato, si noterà icone riportate di seguito: 

- In Outlook l'icona simile al seguente: <br/> ![Icona messaggio componente aggiuntivo di report per Outlook](media/OutlookReportMessageIcon.png)<br/>
- In Outlook Web App l'icona simile al seguente:<br/>![Icona messaggio Report Web componente aggiuntivo per Outlook](media/d9326d0b-1769-4bc2-ae58-51f0ebc69a17.png)<br/>

In una fase successiva, informazioni su come [utilizzare il componente aggiuntivo di report](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2).
  
## <a name="get-and-enable-the-report-message-add-in-for-your-organization"></a>Ottenere e abilitare il componente aggiuntivo di report per l'organizzazione

> [!IMPORTANT]
> È necessario essere un amministratore globale di Office 365 o un amministratore di Exchange Online per completare questa attività.

1. Accedere a [https://portal.office.com](https://portal.office.com) e accedere utilizzando l'account di lavoro o della scuola. 
    
2. Scegliere **amministrazione** passare al centro di amministrazione. 
    
3. Scegliere **Admin Center** \> **Exchange** per accedere all'interfaccia di amministrazione di Exchange (EAC). 
    
4. Scegliere **organizzazione** \> **componenti aggiuntivi**. 
    
5. Scegliere **+**  >  **aggiungere da Office Store**.<br/>![Scegliere Aggiungi da Office Store](media/EAC-Org-AddFromOfficeStore.png)<br/>Office Store verrà aperta nel web browser.
    
6. Cercare di report.<br/>![Cercare di report](media/ReportMessageSearchOfficeStore.png)<br/>
    
7. Nell'elenco delle **App** , selezionare **Di report**e quindi fare clic su **Ottenere IT adesso**.<br/>![Scegliere GET IT ora](media/ReportMessageGETITNOW.png)<br/> 
    
8. Leggere le condizioni di utilizzo e sulla privacy. Quindi fare clic su **Continua**. 
    
    ![Fare clic su Continua per accettare i termini e l'informativa sulla privacy](media/ReportMessageTermsAndConditions.png)
  
9. Verrà visualizzata una procedura guidata che consentono di configurare le informazioni della revisione di componente aggiuntivo di report e scegliere **Avanti** per continuare.<br/>![Messaggio componente aggiuntivo Creazione guidata report per Office 365](media/ReportMessageAdminInstallUI.png)<br/> 

10. Consente di specificare l'impostazione predefinita che si desidera che gli utenti per il componente aggiuntivo di report.<br/>![Specificare le impostazioni predefinite per il componente aggiuntivo di report](media/ReportMessageUserOptionsAdminsSet.png)<br/>
    
11. Consente di specificare che ottiene il messaggio di Report di componente aggiuntivo. <br/>![Specifica che ottiene il messaggio di Report di componenti aggiuntivi](media/ReportMessageChooseWhoGetsItAdminSettings.png)<br/>

12. Scegliere **Save**. <br/>
> [!TIP]
> Si consiglia di [impostazione di una regola per ottenere una copia dei messaggi di posta elettronica segnalati dagli utenti](#set-up-a-rule-to-get-a-copy-of-email-messages-reported-by-your-users)

In base al quale è selezionata utilizzando la procedura guidata, gli utenti dell'organizzazione avranno il [componente aggiuntivo di report](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2) disponibili. Gli utenti dell'organizzazione verranno visualizzato le icone seguenti: 

- In Outlook l'icona simile al seguente: <br/> ![Icona messaggio componente aggiuntivo di report per Outlook](media/OutlookReportMessageIcon.png)<br/>
- In Outlook Web App l'icona simile al seguente:<br/>![Icona messaggio Report Web componente aggiuntivo per Outlook](media/d9326d0b-1769-4bc2-ae58-51f0ebc69a17.png)<br/>

## <a name="set-up-a-rule-to-get-a-copy-of-email-messages-reported-by-your-users"></a>Impostare una regola per ottenere una copia dei messaggi di posta elettronica segnalati dagli utenti

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
  
10. Scegliere **Save**. 
    
Con questa regola, ogni volta che qualcuno all'interno dell'organizzazione segnala un messaggio di posta elettronica utilizzando il componente aggiuntivo di report, l'amministratore globale, amministratore della sicurezza e/o lettore di sicurezza riceverà una copia del messaggio. Queste informazioni possono consentono di configurare o modificare criteri, ad esempio i criteri di [Office 365 degli strumenti di analisi provvisoria collegamenti](atp-safe-links.md) . 

## <a name="review-or-edit-the-default-settings-for-the-report-message-add-in"></a>Visualizzare o modificare le impostazioni predefinite per il componente aggiuntivo di report

È possibile esaminare e modificare le impostazioni predefinite per il componente aggiuntivo di report tramite l'interfaccia di amministrazione. 

> [!IMPORTANT]
> È necessario essere un amministratore globale di Office 365 o un amministratore di Exchange Online per completare questa attività.
    
1. Se è stato appena installato il componente aggiuntivo di report per l'organizzazione, già sarà nella pagina servizi e componenti aggiuntivi. In caso contrario, Vai [qui](https://portal.office.com/adminportal/home#/Settings/ServicesAndAddIns) e accedere utilizzando l'account di lavoro o della scuola per Office 365.

2. Cercare **Di report**e quindi selezionare.<br/>![Servizi e componenti aggiuntivi per Office 365](media/ReportMessage-o365servicesaddins.png)<br/> 
    
3. Verrà visualizzato un riquadro che visualizza le impostazioni che sono state selezionate per il componente aggiuntivo di report durante la distribuzione.<br/>![Impostazioni per il componente aggiuntivo di report](media/ReportMessage-reviewaddinsettings.png)<br/> 

4. Esaminare e, se necessario, modificare le impostazioni per il componente aggiuntivo di report e quindi salvare le modifiche.
    
## <a name="learn-how-to-use-the-report-message-add-in"></a>Informazioni su come utilizzare il componente aggiuntivo di report

Vedere [utilizzo del componente aggiuntivo di report](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2).
  
## <a name="related-topics"></a>Argomenti correlati

[Usare il componente aggiuntivo Segnala messaggio](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2)
  
[Visualizzare i report di protezione posta elettronica in sicurezza &amp; centro conformità](view-email-security-reports.md)

[Visualizzare i report per la protezione rischio avanzate di Office 365](view-reports-for-atp.md)

[Utilizzare Esplora in sicurezza &amp; centro conformità](use-explorer-in-security-and-compliance.md)
  

