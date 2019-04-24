---
title: Criteri di sessione in Office 365 Cloud App Security
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.reviewer: alesibov
ms.audience: Admin
ms.topic: reference
ms.date: 02/27/2019
ms.service: O365-seccomp
localization_priority: Normal
description: I criteri di sessione di sicurezza di Office 365 cloud app consentono il monitoraggio a livello di sessione in tempo reale, offrendo una visibilità granulare nelle app di Office 365 e la possibilità di eseguire azioni diverse a seconda dei criteri impostati per una sessione utente. Invece di consentire o bloccare completamente l'accesso, con il controllo sessione è possibile consentire l'accesso durante il monitoraggio della sessione e/o limitare le attività specifiche della sessione utilizzando le funzionalità del proxy inverso del controllo delle app con accesso condizionale.
ms.openlocfilehash: e0e4b04ee8cc0f7a14adbc26b074a5f2947e44c2
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "32263030"
---
# <a name="session-policies-in-office-365-cloud-app-security"></a>Criteri di sessione in Office 365 Cloud App Security

|Valutazione * *\>**|Planning * *\>**|Distribuzione * *\>**|Utilizzo * * * *|
|:-----|:-----|:-----|:-----|
|[Iniziare a valutare](office-365-cas-overview.md) <br/> |[Avviare la pianificazione](get-ready-for-office-365-cas.md) <br/> |Sei qui!  <br/> [Passaggio successivo](ocas-access-policies.md) <br/> |[Iniziare a utilizzare](utilization-activities-for-ocas.md) <br/> |

I criteri di sessione di sicurezza di Office 365 cloud app consentono il monitoraggio a livello di sessione in tempo reale, offrendo una visibilità granulare nelle app di Office 365 e la possibilità di eseguire azioni diverse a seconda dei criteri impostati per una sessione utente. Invece di consentire o bloccare completamente l'accesso, con il controllo sessione è possibile consentire l'accesso durante il monitoraggio della sessione e/o limitare le attività specifiche della sessione utilizzando le funzionalità del proxy inverso del controllo delle app con accesso condizionale.

Ad esempio, è possibile decidere che da dispositivi non gestiti o per le sessioni provenienti da posizioni specifiche, si desidera consentire all'utente di accedere all'app, ma anche limitare il download di file sensibili o richiedere che alcuni documenti siano protetti al momento del download. I criteri di sessione consentono di impostare questi controlli relativi alla sessione utente e di consentire l'accesso e di eseguire le operazioni seguenti:

- [Monitorare tutte le attività](#monitor-all-activities)

- [Blocca tutti i download](#block-all-downloads)

- [Blocca attività specifiche](#block-specific-activities)

- [Proteggi file su download](#protect-files-on-download)

## <a name="prerequisites-to-using-session-policies"></a>Prerequisiti per l'utilizzo dei criteri di sessione

- Licenza P1 di Azure AD Premium

- Le app di Office 365 rilevanti devono essere [distribuite con il controllo delle app con accesso condizionale](ocas-deploy-conditional-access-app-control.md)

- un [criterio](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal) di accesso condizionale di Azure ad dovrebbe essere sul posto che reindirizza gli utenti a Office 365 Cloud App Security

## <a name="create-an-azure-ad-conditional-access-policy"></a>Creare un criterio di accesso condizionale di Azure AD

I criteri di accesso condizionale di Azure Active Directory e i criteri di sessione di sicurezza cloud app funzionano in tandem per esaminare ogni sessione utente e prendere decisioni sui criteri per ogni app. Per impostare un criterio di accesso condizionale in Azure Active Directory, eseguire la procedura seguente:

1. Configurare un [criterio](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal) di accesso condizionale di Azure ad con assegnazioni per un utente o un gruppo di utenti e l'app che si desidera controllare con il controllo dell'applicazione di accesso condizionale. Nota: sono interessati da questo criterio solo [le app distribuite con il controllo](ocas-deploy-conditional-access-app-control.md) delle app con accesso condizionale.

2. instradare gli utenti alla sicurezza delle app Cloud di Office 365 selezionando le  **restrizioni di utilizzo del controllo delle app con accesso condizionale applicate**nella pagina **sessione** .

## <a name="create-a-cloud-app-security-session-policy"></a>Creare un criterio di sessione di protezione delle app Cloud

Per creare un nuovo criterio di sessione, eseguire la procedura seguente:

1. Nel portale selezionare **controllo** seguito dai **criteri**.

2. Nella pagina **criteri** fare clic su **Crea criterio** e selezionare **criteri sessione**.

3. Nella finestra **criteri** di sessione assegnare un nome per il criterio

4. Nel campo **tipo** di controllo sessione:
    
    - Selezionare **monitor solo** se si desidera monitorare le attività solo dagli utenti. Questa selezione creerà un criterio di monitoraggio solo per le app selezionate in cui verranno scaricati tutti gli accessi, i download euristici e i tipi di attività.
    
    - Selezionare il **download dei file di controllo (con DLP)** se si desidera monitorare le attività degli utenti. È possibile eseguire altre operazioni come blocca o Proteggi download per gli utenti.
    
    - Selezionare **blocca attività** per bloccare attività specifiche, che è possibile selezionare utilizzando il filtro **tipo** di attività. Tutte le attività delle app selezionate verranno monitorate (e segnalate nel registro attività). Le attività specifiche selezionate verranno bloccate se si seleziona l'azione **blocca** . Le attività specifiche selezionate genereranno avvisi se si seleziona l'azione **** di testing e si attivano gli avvisi.

5. In **origine** attività nelle **attività che corrispondono a tutta la sezione seguente** selezionare filtri attività aggiuntivi da applicare al criterio. Tali filtri possono includere le opzioni seguenti:
    
    - **Tag del dispositivo**: utilizzare questo filtro per identificare i dispositivi non gestiti.
    
    - **Posizione**: utilizzare questo filtro per identificare le posizioni sconosciute (e quindi rischiose).
    
    - **Indirizzo IP**: utilizzare questo filtro per filtrare gli indirizzi IP o utilizzare i tag degli indirizzi IP assegnati in precedenza.
    
    - **Tag dell'agente utente**: utilizzare questo filtro per abilitare l'euristica per identificare le app per dispositivi mobili e desktop. Questo filtro può essere impostato su Equals o non è uguale a **Native Client**. Questo filtro deve essere testato sulle app per dispositivi mobili e desktop per ogni app cloud.<br>Nota: i criteri di sessione non supportano le app per dispositivi mobili e desktop. Le app per dispositivi mobili e le app desktop possono anche essere bloccate o consentite creando un criterio di accesso.

6. Se è stata selezionata l'opzione **per controllare il download di file (con DLP)**, in **origine** attività nei **file che corrispondono a tutta la sezione seguente** selezionare filtri di file aggiuntivi da applicare al criterio. Tali filtri possono includere le opzioni seguenti:
        
    - **Etichetta di classificazione** : utilizzare questo filtro se nell'organizzazione viene utilizzata la protezione delle informazioni di Azure e i dati sono stati protetti dalle etichette di classificazione. È possibile filtrare i file in base all'etichetta di classificazione applicata. Per ulteriori informazioni sull'integrazione con Azure Information Protection, vedere [Azure Information Protection Integration](https://docs.microsoft.com/cloud-app-security/azip-integration).
        
    - **Nome file:** utilizzare questo filtro per applicare il criterio a file specifici.
        
    - **Tipo di file** : utilizzare questo filtro per applicare il criterio a tipi di file specifici, ad esempio blocca download per tutti i file xls.
    
    - Nella sezione **controllo** contenuto impostare se si desidera abilitare il motore DLP per analizzare i documenti e il contenuto del file.
    
    - In **azioni**selezionare uno degli elementi seguenti:
        
        - **Test (monitorare tutte le attività)**: impostare questa azione in modo esplicito per consentire il download in base ai filtri di criteri impostati.
        
        - **Blocca (blocca il download di file e monitora tutte le attività)**: impostare questa azione per bloccare in modo esplicito il download in base ai filtri di criteri impostati. Per ulteriori informazioni, vedere [How Block download Works](https://docs.microsoft.com/en-us/cloud-app-security/session-policy-aad#block-download).
        
        - **Proteggi (Applica etichetta di classificazione per il download e il monitoraggio di tutte le attività)**: questa opzione è disponibile solo se è stato selezionato il **download dei file di controllo (con DLP)** in **criteri di sessione**. Se nell'organizzazione viene utilizzata la protezione delle informazioni di Azure, è possibile impostare un' **azione** per applicare un'etichetta di classificazione impostata in Azure Information Protection al file. Per ulteriori informazioni, vedere [How Protect download Works](https://docs.microsoft.com/en-us/cloud-app-security/session-policy-aad#protect-download).

7. È possibile **creare un avviso per ogni evento corrispondente con la gravità del criterio**e impostare un limite di avviso. Selezionare se si desidera che l'avviso venga inviato come un messaggio di posta elettronica, un SMS o entrambi.

## <a name="monitor-all-activities"></a>Monitorare tutte le attività

Quando si crea un criterio di sessione, ogni sessione utente che corrisponde al criterio viene reindirizzata al controllo sessione anziché all'app direttamente. L'utente vedrà una notifica di monitoraggio per fargli sapere che le sessioni sono state monitorate.

Se non si desidera inviare una notifica all'utente che si sta monitorando, è possibile disabilitare il messaggio di notifica.

1. In impostazioni COG selezionare **Impostazioni generali**.

2. Quindi, in **controllo** app di accesso condizionale selezionare **monitoraggio** utente e deseleziona la casella di spunta **Notify Users** .

Per mantenere l'utente all'interno della sessione, il controllo delle app di accesso condizionale sostituisce tutti gli URL rilevanti, gli script Java e i cookie all'interno della sessione dell'app con gli URL di protezione delle app cloud di Office 365. Ad esempio, se l'app restituisce una pagina con collegamenti i cui domini terminano `myapp.com`, il controllo delle app con accesso condizionale sostituisce i collegamenti con `myapp.com.us.cas.ms`domini che terminano con qualcosa di simile. In questo modo l'intera sessione viene monitorata da Office 365 cloud app Security.

Controllo delle app di accesso condizionale registra i log di traffico di ogni sessione utente che viene instradata attraverso di esso. I registri di traffico includono l'ora, l'IP, l'agente utente, gli URL visitati e il numero di byte caricati e scaricati. Questi registri vengono analizzati e un report continuo, il **controllo delle app di accesso condizionaLe cloud app Security**, viene aggiunto all'elenco dei report di individuazione cloud nel dashboard di individuazione cloud.

### <a name="to-export-these-logs"></a>Per esportare i registri:

1. Passare alla barra delle impostazioni e fare clic su **controllo di accesso condizionale**.

2. Sul lato destro della tabella fare clic sul pulsante Esporta.<br>![pulsante Esporta](media/image3.png)<br>

3. Selezionare l'intervallo del report e fare clic su **Esporta**. Questo processo potrebbe richiedere del tempo.

### <a name="to-download-the-exported-log"></a>Per scaricare il log esportato:

1. Dopo che il report è pronto, passare a **Impostazioni** e quindi **rapporti**esportati.

2. Nella tabella, selezionare il report pertinente dall'elenco dei **log** del traffico delle app con accesso condizionale e fare clic su Scarica.<br>![pulsante Download](media/image4.png)<br>

## <a name="block-all-downloads"></a>Blocca tutti i download

Quando il **blocco** è impostato come **azione** che si desidera eseguire nel criterio sessione cloud app Security, il controllo delle app di accesso condizionale impedisce a un utente di scaricare un file per i filtri di file del criterio. Un evento di download è riconosciuto da Office 365 cloud app Security per ogni app quando un utente avvia un download. Controllo delle app di accesso condizionale interviene in tempo reale per impedirne l'esecuzione. Quando viene ricevuto il segnale che un utente ha avviato il download, il controllo delle app di accesso condizionale restituisce un messaggio con **restrizioni** per il download all'utente e sostituisce il file scaricato con un file di testo. Il messaggio del file di testo all'utente può essere configurato e personalizzato dal criterio di sessione.

## <a name="block-specific-activities"></a>Blocca attività specifiche

Quando le **attività** bloccate sono impostate come **tipo di attività**, è possibile selezionare attività specifiche da bloccare in app specifiche. Tutte le attività delle app selezionate verranno monitorate e segnalate nel registro attività. Le attività specifiche selezionate verranno bloccate se si seleziona l'azione **blocca** . Le attività specifiche selezionate genereranno avvisi se si seleziona l'azione **** di testing e si attivano gli avvisi.

**Blocca le attività** specifiche e applicale a gruppi specifici per creare una modalità di sola lettura completa per l'organizzazione.

## <a name="protect-files-on-download"></a>Proteggi file su download

Selezionare **blocca attività** per bloccare attività specifiche, che è possibile trovare utilizzando il filtro **tipo** di attività. Tutte le attività delle app selezionate verranno monitorate (e segnalate nel registro attività). Le attività specifiche selezionate verranno bloccate se si seleziona l'azione **blocca** . Le attività specifiche selezionate genereranno avvisi se si seleziona l'azione **** di testing e si attivano gli avvisi.

Quando **Protect** è impostato come **azione** da intraprendere nel criterio sessione cloud app Security, il controllo delle app di accesso condizionale impone l'etichettatura e la successiva protezione di un file per i filtri di file del criterio. Le etichette sono configurate nella console di Azure Information Protection e **Protect** devono essere selezionati all'interno dell'etichetta affinché venga visualizzato come opzione nei criteri di protezione delle app cloud. Quando viene selezionata un'etichetta e viene scaricato un file che soddisfa i criteri dei criteri di sicurezza delle app Cloud, l'etichetta e la protezione corrispondente (con autorizzazioni) vengono applicate al file al momento del download. Il file originale rimane invariato nell'app cloud mentre il file scaricato è ora protetto. Gli utenti che tentano di accedere al file devono soddisfare i requisiti di autorizzazione stabiliti dalla protezione applicata.

## <a name="next-steps"></a>Passaggi successivi

- [Informazioni sui criteri di accesso in Office 365 cloud app Security](ocas-access-policies.md)

- [Blocco di download su dispositivi non gestiti tramite le funzionalità di controllo delle app con accesso condizionale di Azure AD](https://docs.microsoft.com/en-us/cloud-app-security/use-case-proxy-block-session-aad)

