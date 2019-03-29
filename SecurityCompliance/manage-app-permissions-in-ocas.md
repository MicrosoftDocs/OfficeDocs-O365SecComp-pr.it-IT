---
title: Gestire le app di OAuth con Office 365 Cloud App Security
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 12/26/2018
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 2062c312-b1e4-4ce7-8cb2-ea39bc0dfdad
description: Le app OAuth in Office 365 cloud app Security consentono di gestire le app scaricate dagli utenti per l'utilizzo con i dati di Office 365
ms.openlocfilehash: 0d9916414d55abb73fd99eaf30c3b6df0648b191
ms.sourcegitcommit: 1658be51e2c21ed23bc4467a98af74300a45b975
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/26/2019
ms.locfileid: "30862588"
---
# <a name="manage-oauth-apps-using-office-365-cloud-app-security"></a>Gestire le app di OAuth con Office 365 Cloud App Security

|Valutazione * *\>**|Planning * *\>**|Distribuzione * *\>**|Utilizzo * * * *|
|:-----|:-----|:-----|:-----|
|[Iniziare a valutare](office-365-cas-overview.md) <br/> |[Avviare la pianificazione](get-ready-for-office-365-cas.md) <br/> |[Avviare la distribuzione](turn-on-office-365-cas.md) <br/> |Sei qui!  <br/> [Passaggi successivi](#next-steps)<br/> |
   
Gli utenti amano le app e le scaricano spesso, specialmente quelle che pensano che la gente risparmierà tempo rendendo più facile ottenere informazioni sul lavoro o sulla scuola. Tuttavia, alcune app potrebbero rappresentare un rischio per la sicurezza per l'organizzazione, a seconda delle informazioni che accedono e del modo in cui gestiscono tali informazioni. Con [Office 365 cloud app Security](office-365-cas-overview.md), se si è un amministratore globale o di sicurezza, è possibile gestire le app OAuth per l'organizzazione. È possibile visualizzare le app che gli utenti utilizzano con i dati di Office 365, quali autorizzazioni hanno le app e altro ancora. 
  
In questo articolo viene descritto dove andare per gestire le app OAuth, come approvare, vietare o segnalare un'app e come creare una query app.
  
## <a name="how-to-find-the-manage-oauth-apps-page"></a>Come trovare la pagina Gestisci applicazioni OAuth

> [!NOTE]
> Le app OAuth sono gestite nel portale di sicurezza cloud app di Office 365. Per eseguire l'attività seguente, è necessario essere un amministratore globale o un amministratore della sicurezza. Per ulteriori informazioni, vedere perMissions [in the &amp; Office 365 Security Compliance Center](permissions-in-the-security-and-compliance-center.md). 
  
1. Accedere al portale[https://portal.cloudappsecurity.com](https://portal.cloudappsecurity.com)di sicurezza delle app cloud e accedere.
  
2. Scegliere **indagare** \> le **app OAuth**.<br/>![Nel portale O365 CAS, scegliere indagare.](media/OCAS-OAuthApps.png)<br/>
  
## <a name="what-youll-see-on-the-manage-oauth-apps-page"></a>Cosa verrà visualizzato nella pagina Gestisci applicazioni OAuth

Nella tabella seguente vengono descritti i controlli e le opzioni disponibili nella pagina Gestisci OAuth Apps.
  
|**Elemento**|**Descrizione**|
|:-----|:-----|
|Icona di base nella barra di query dell'app  <br/> ![Icona che indica la visualizzazione di query di base per l'esecuzione di query](media/a459bc51-e86b-43d5-a0ee-661b9fb4afc9.png)|Selezionare questa opzione per passare alla visualizzazione avanzate.  <br/> Se viene visualizzato **Basic**, si utilizza la visualizzazione avanzata.  <br/> |
|Icona avanzata nella barra di query dell'app  <br/> ![Icona che indica la visualizzazione query avanzata per l'esecuzione di query](media/9958d832-2c81-45ed-a642-d926310ba6b6.png)|Selezionare questa opzione per passare alla visualizzazione di base.  <br/> Se viene visualizzato **avanzato**, si utilizza la visualizzazione di base.  <br/> |
|Aprire o chiudere l'icona tutti i dettagli nell'elenco delle app  <br/> ![Fare clic su questa icona per aprire o chiudere tutti i dettagli per tutte le app](media/018fa996-10e8-48ff-986e-55f2b69a5753.png)|Selezionare questa icona per visualizzare i dettagli più o meno su ogni app.  <br/> |
|Icona Esporta nell'elenco delle app  <br/> ![Fare clic su questa icona per esportare un file CSV di tutte le app](media/98446851-fd96-4d09-9bb0-831db33090c1.png)|Selezionare questa icona per esportare un file CSV contenente un elenco di app, il numero di utenti per ogni app, le autorizzazioni associate all'app, il livello di autorizzazioni, lo stato dell'applicazione e il livello di utilizzo della community.  <br/> |
|Name  <br/> |Utilizzare questa pagina per visualizzare il nome di un'app. Selezionare il nome per visualizzare altre informazioni, ad esempio la descrizione, l'editore, il sito Web App e l'ID app.  <br/> |
|Autorizzato da  <br/> |Utilizzare questa procedura per visualizzare il numero di utenti autorizzati a un'app per accedere al proprio account di Office 365. Selezionare il numero per visualizzare altre informazioni, ad esempio un elenco di account utente.  <br/> |
|Livello di autorizzazioni  <br/> ![Icona che indica il livello di Permisiions per un'app](media/aaebdd29-35b6-4c62-aef1-7c7817bd803d.png)|Utilizzare questa procedura per visualizzare l'accesso ai dati di Office 365 da parte di un'app. I livelli di autorizzazione indicano **basso**, **medio**o **alto**, dove **basso** potrebbe indicare che l'applicazione accede solo al profilo e al nome di un utente. Selezionare il livello per visualizzare altre informazioni, ad esempio le autorizzazioni concesse all'app, l'utilizzo della community e l'attività correlata nel [Registro](suspend-or-restore-an-account-in-ocas.md)di governance.  <br/> |
|Ultimo autorizzato <br/> |Utilizzare questa funzione per visualizzare la data e l'ora in cui è stata autorizzata l'ultima volta un'app OAuth per accedere ai dati di Office 365 dell'organizzazione. <br/>  |
|Azioni<br/>![App OAuth](media/OCAS-OAuthAppApproveBanReport.png)<br/> |Utilizzare questa pagina per visualizzare o contrassegnare un'app come apProvata o vietata, segnalare un'app OAuth a Microsoft oppure lasciarla indeterminata.  <br/> |
   
## <a name="mark-an-app-as-approved"></a>Contrassegnare un'app come approvata

Nella pagina **Gestisci applicazioni OAuth** individuare l'app che si desidera approvare e scegliere l'icona **Contrassegna applicazione come** approvata. 
  
![Scegliere l'icona contrassegna applicazione come approvata](media/OCAS-MarkOAuthApproved.png)
  
L'icona diventa verde e l'app è approvata per tutti gli utenti di Office 365.
  
> [!NOTE]
> Quando si contrassegna un'app come approvata, l'utente finale non ha alcun effetto. Contrassegnare visivamente le app che sono approvate contribuisce a separare le app che non sono state ancora esaminate. 
  
## <a name="ban-an-app"></a>Ban un'app

1. Nella pagina **Gestisci applicazioni OAuth** individuare l'app che si desidera bannare e scegliere l'icona **Contrassegna come applicazione** non connotata.<br/>![Scegliere l'icona contrassegna come Banned](media/OCAS-MarkOAuthBanned.png)
  
2. Nella finestra di messaggio di notifica mantenere il testo esistente così com'è o personalizzare il testo. Scegliere se consentire agli utenti di sapere che la propria app è stata Bannata. <br/>![Il modello di posta elettronica per un'app vietata](media/6d132700-5f7f-472c-bfb5-a44549e69c16.jpg)<br/>
  
3. Scegliere l' **app Ban**.

## <a name="report-an-oauth-app-to-microsoft"></a>Segnalare un'app OAuth a Microsoft

Se si desidera inviare un'app OAuth a Microsoft per l'analisi, è possibile segnalarla.

1. Nella pagina **Gestisci applicazioni OAuth** individuare l'app che si desidera inviare per l'analisi.

2. Scegliere i puntini di sospensione verticali e quindi fare clic su **app report...**.<br/>![Segnalare un'app OAuth](media/OCAS-MarkOAuthReported.png)<br/>

3. Nella finestra di dialogo **segnala questa applicazione** , utilizzare l'elenco a discesa per indicare la preoccupazione. Per impostazione predefinita, **questa app è** selezionata. Tuttavia, è possibile scegliere una delle altre opzioni disponibili. <br/>![Segnalare un'app OAuth](media/OCAS-ReportOAuthApp.png)<br/>

4. Consigliato Mantenere l'opzione per contattare l'utente selezionato e confermare (o modificare) l'indirizzo di posta elettronica elencato.

5. Choose **Submit**. 
    
## <a name="create-an-app-query"></a>Creare una query app

È consigliabile utilizzare la visualizzazione avanzata, che assomiglia alla seguente: 

![Visualizzazione avanzata](media/OCAS-OAuthAppsAdvQueryView.png)

Nella barra di query dell'app, se si vede **Advanced**, si utilizza la visualizzazione di base. Fare clic su (o toccare) **Avanzate** per passare alla visualizzazione avanzata. 

![Visualizzazione di base](media/OCAS-OAuthAppsBasicQueryView.png)
    
1. Nella barra delle query, utilizzare l'elenco **Seleziona un filtro** per scegliere un'opzione. 
    - **App** App con determinati nomi
    - **Stato dell'app** App in base allo stato (approvato, vietato o indeterminato)
    - **Utilizzo della community** App basate sui livelli di utilizzo della community (rare, inusuali o comuni)
    - **Livello di autorizzazione** App basate su determinati livelli di autorizzazione 
    - **Autorizzazioni** App che richiedono determinate autorizzazioni
    - **Server di pubblicazione**  App di alcuni Publisher
    - **Utente** App autorizzate da un utente specifico
   
2. Selezionare **uguale** a o **non uguale**, quindi specificare un valore per il filtro.
    
3. Per aggiungere altri filtri, seleziona il segno più (![Aggiungere un'icona del filtro per l'esecuzione di query nelle app](media/771b2958-67cd-4e14-9302-283ef238cae5.jpg)), quindi ripetere i passaggi 2 e 3.
    
4. Per rimuovere un filtro, seleziona la x (![Rimuovere un'icona del filtro per l'esecuzione di query nelle app](media/5339277f-555d-4749-8dcc-d2574250556e.jpg)) accanto a un nome di filtro.
    
I filtri vengono applicati automaticamente e l'elenco delle app viene aggiornato di conseguenza.
  
## <a name="next-steps"></a>Passaggi successivi

- [Esaminare e intervenire sugli avvisi](review-office-365-cas-alerts.md)
    
- Esaminare i [log del traffico Web e le origini dati per Office 365 cloud app Security](web-traffic-logs-and-data-sources-for-ocas.md)
    
- Esaminare le [attività di utilizzo per Office 365 cloud app Security](utilization-activities-for-ocas.md)
    

