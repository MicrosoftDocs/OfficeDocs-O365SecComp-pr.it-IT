---
title: Rilevare e rimediare a concessioni di consenso illecite in Office 365
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 4/23/2018
ms.audience: ITPro
ms.topic: article
ms.collection:
- o365_security_incident_response
- Strat_O365_IP
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
description: Informazioni su come riconoscere e correggere il consenso illecito Grants Attack in Office 365.
ms.openlocfilehash: 1d8df4db94129bcdcb6ecf4859f9f89a1974edbe
ms.sourcegitcommit: a80bd8626720fabdf592b84e4424cd3a83d08280
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/23/2019
ms.locfileid: "30223355"
---
# <a name="detect-and-remediate-illicit-consent-grants-in-office-365"></a>Rilevare e rimediare a concessioni di consenso illecite in Office 365

**Riepilogo**  Informazioni su come riconoscere e correggere il consenso illecito Grants Attack in Office 365.

## <a name="what-is-the-illicit-consent-grant-attack-in-office-365"></a>Che cos'è l'attacco di concessione di autorizzazioni illecite in Office 365?
In un attacco di concessione di consenso illecito, l'utente malintenzionato crea un'applicazione registrata in Azure che richiede l'accesso ai dati, ad esempio le informazioni di contatto, la posta elettronica o i documenti. L'utente malintenzionato, quindi, inganna l'utilizzatore finale per concedere a tale applicazione il consenso per accedere ai propri dati tramite un attacco di phishing o iniettando codice illecito in un sito Web attendibile. Dopo che l'applicazione illecita ha ottenuto il consenso, ha accesso ai dati a livello di account senza la necessità di un account organizzativo. I normali passaggi di correzione, come la reimpostazione delle password per gli account violati o la richiesta di autenticazione a più fattori (AMF) per gli account, non sono efficaci rispetto a questo tipo di attacco, poiché si tratta di applicazioni di terze parti e sono esterne all'organizzazione. Questi attacchi sfruttano un modello di interazione che presuppone che l'entità che chiama le informazioni sia l'automazione e non un essere umano.

## <a name="what-does-an-illicit-consent-grant-attack-look-like-in-office-365"></a>Che cosa comporta un attacco di consenso illecito per l'assenso in Office 365?
È necessario eseguire una ricerca nel **Registro di controllo** di Office 365 per individuare i segni, denominati anche indicatori di compromesso (IOC) di questo attacco. Per le organizzazioni con molte applicazioni registrate in Azure e una base di utenti di grandi dimensioni, la procedura consigliata consiste nell'esaminare le concessioni di consenso delle organizzazioni su base settimanale.
### <a name="steps-for-finding-signs-of-this-attack"></a>Passaggi per individuare i segni di questo attacco
1. Aprire il **Centro sicurezza e conformità** nel tenant di Office 365.
2. Passare al nodo di **analisi di & di ricerca** e selezionare ricerca del registro di **controllo** .
3. Creare una ricerca (tutte le attività e tutti gli utenti) e filtrare i risultati per il consenso all'applicazione e aggiungere OAuth2PermissionGrant.
4. Esaminare le proprietà estese e verificare se IsAdminContent è impostato su true.


Se questo valore è impostato su true, indica che un utente con accesso amministratore globale può aver concesso l'accesso esteso ai dati. Se questa operazione non è prevista, eseguire le operazioni necessarie per [confermare un attacco](detect-and-remediate-illicit-consent-grants.md#confirmattack).

<a name="confirmattack"> </a>
## <a name="how-to-confirm-an-attack"></a>Come confermare un attacco
Se si dispone di una o più istanze di IOCs elencate in alto, è necessario eseguire ulteriori indagini per confermare positivamente che l'attacco si è verificato. Per confermare l'attacco, è possibile utilizzare uno di questi tre metodi.
- Applicazioni di inventario e relative autorizzazioni tramite il portale di Azure Active Directory. Questo metodo è accurato, ma è possibile controllare solo un utente alla volta che può richiedere molto tempo se si dispone di molti utenti da controllare.
- Applicazioni di inventario e relative autorizzazioni tramite PowerShell. Questo è il metodo più rapido e completo, con il minor numero di overhead.
- Fare in modo che gli utenti controllino singolarmente le app e le autorizzazioni e riportino i risultati agli amministratori per la correzione.

## <a name="inventory-apps-with-access-in-your-organization"></a>App di inventario con accesso nell'organizzazione
È possibile eseguire questa operazione per gli utenti con il portale di Azure Active Directory o con PowerShell oppure fare in modo che gli utenti possano enumerare singolarmente l'accesso alle applicazioni.

### <a name="steps-for-using-the-azure-active-directory-portal"></a>Passaggi per l'utilizzo del portale di Azure Active Directory
È possibile cercare le applicazioni a cui ogni singolo utente ha concesso le autorizzazioni utilizzando il [portale di Azure Active Directory](https://portal.azure.com/). 
1. Accedere al portale di Azure con diritti amministrativi.
2. Selezionare il Blade di Azure Active Directory.
3. Selezionare **Utenti**.
4. Selezionare l'utente che si desidera esaminare.
5. Selezionare **applicazioni**.

In questo modo vengono mostrate le app che sono state assegnate all'utente e quali sono le autorizzazioni di applcations.

### <a name="steps-for-having-your-users-enumerate-their-application-access"></a>Procedure per consentire agli utenti di enumerare l'accesso alle applicazioni
Fare in modo che gli https://myapps.microsoft.com utenti accedano e rivedano l'accesso a un'applicazione. Essi dovrebbero essere in grado di visualizzare tutte le app con accesso, visualizzare i dettagli relativi (compreso l'ambito di accesso) ed essere in grado di revocare i privilegi alle app sospette o illecite.

### <a name="steps-for-doing-this-with-powershell"></a>Passaggi per eseguire questa operazione con PowerShell
Il modo più semplice per verificare l'attacco di concessione di consenso illecito consiste nell'eseguire [Get-AzureADPSPermissions. ps1](https://gist.github.com/psignoret/41793f8c6211d2df5051d77ca3728c09), che consentirà di scaricare tutti i concessioni di autorizzazione OAuth e le app OAuth per tutti gli utenti nel proprio contratto di locazione in un unico file. csv. 

#### <a name="pre-requisites"></a>Prerequisiti
- Libreria di Azure AD PowerShell installata.
- Diritti di amministratore globale sul tenant su cui verrà eseguito lo script.
- Amministratore locale nel computer da cui verranno eseguiti gli script.

> [!IMPORTANT]
> È consigliabile richiedere l'autenticazione a più fattori per l'account amministrativo.  Questo script supporta l'autenticazione Mae.

1. Accedere al computer in cui verrà eseguito lo script con i diritti di amministratore locale.
2. Scaricare o copiare lo script [Get-AzureADPSPermissions. ps1](https://gist.github.com/psignoret/41793f8c6211d2df5051d77ca3728c09) da GitHub in una cartella da cui verrà eseguito il scruipt.  Questa sarà la stessa cartella in cui verrà scritto il file di output "Permissions. csv".
3. Aprire un'istanza di PowerShell come amministratore e aprirla alla cartella in cui è stato salvato lo script.
4. Connettersi alla directory utilizzando il cmdlet [Connect-AzureAD](https://docs.microsoft.com/powershell/module/azuread/connect-azuread?view=azureadps-2.0) .
5. Eseguire la riga di comando di PowerShell come indicato di seguito:`Get-AzureADPSPermissions.ps1 | Export-csv -path "Permissions.csv" -NoTypeInformation`

Lo script produce un file denominato perMissions. csv. Eseguire la procedura seguente per cercare le autorizzazioni di autorizzazione per l'applicazione illecite: 
1. Nella colonna ConsentType (colonna G) cercare il valore "AllPrinciples". L'autorizzazione AllPrincipals consente all'applicazione client di accedere al contenuto di tutti nel contratto di locazione. Le applicazioni di Office 365 native richiedono questa autorizzazione per funzionare correttamente. Tutte le applicazioni non Microsoft con questa autorizzazione devono essere esaminate con attenzione.
2.  Nella colonna autorizzazione (colonna F) esaminare le autorizzazioni che ogni applicazione delegata deve soddisfare. Cercare l'autorizzazione "lettura" e "scrittura" o "*. All "autorizzazione e verificarne con attenzione perché potrebbero non essere appropriate.
3.  Esaminare gli utenti specifici a cui sono concessi consenzienti. Se gli utenti di alto profilo o di alto impatto hanno concessi consensi inadeguati, è necessario indagare ulteriormente.
4.  Nella colonna ClientDisplayName (colonna C) cercare le app che risultano sospette. Le app con nomi di ortografia errati, nomi Super blandi o nomi di hacker devono essere esaminate con attenzione.

## <a name="determine-the-scope-of-the-attack"></a>Determinare l'ambito dell'attacco
Dopo aver completato l'inventario dell'applicazione, esaminare il **Registro di controllo** di Office 365 per determinare l'ambito completo della violazione.  Cercare negli utenti coinvolti, i tempi di accesso dell'applicazione illecita all'organizzazione e le autorizzazioni dell'app. È possibile eseguire una ricerca nel **Registro di controllo** nel [Centro sicurezza e conformità di Office 365](https://support.office.com/article/Search-the-audit-log-in-the-Office-365-Security-Compliance-Center-0d4d0f35-390b-4518-800e-0c7ec95e946c). 

> [!IMPORTANT]
> Il controllo [delle cassette postali](https://support.office.com/article/Enable-mailbox-auditing-in-Office-365-aaca8987-5b62-458b-9882-c28476a66918) e il [controllo delle attività per gli amministratori e gli utenti](https://support.office.com/article/turn-office-365-audit-log-search-on-or-off-e893b19a-660c-41f2-9074-d3631c95a014) devono essere stati abilitati prima dell'attacco per ottenere queste informazioni.

## <a name="how-to-stop-and-remediate-an-illicit-consent-grant--attack"></a>Come arrestare e correggere un attacco di concessione di un consenso illecito
Dopo aver identificato un'applicazione con autorizzazioni illecite, sono disponibili diversi modi per rimuovere tale accesso.
- È possibile revocare l'autorizzazione dell'applicazione nel portale di Azure Active Directory per:
    - Passare all'utente coinvolto nel Blade **utente di Azure Active Directory** .
    - Selezionare **applicazioni**.
    - Selezionare l'applicazione illecita.
    - Fare clic su **Rimuovi** nell'esercitazione verso il basso.
- È possibile revocare la concessione di autorizzazione OAuth con PowerShell attenendosi alla procedura descritta in [Remove-AzureADOAuth2PermissionGrant](https://docs.microsoft.com/powershell/module/azuread/Remove-AzureADOAuth2PermissionGrant?view=azureadps-2.0).
- È possibile revocare l'assegnazione di ruolo app di servizio con PowerShell attenendosi alla procedura descritta in [Remove-AzureADServiceAppRoleAssignment](https://docs.microsoft.com/powershell/module/azuread/Remove-AzureADServiceAppRoleAssignment?view=azureadps-2.0).
- È inoltre possibile disabilitare l'accesso per l'account interessato del tutto, che disattiverà la disabilitazione dell'app ai dati di quell'account. Questo non è l'ideale per la produttività dell'utente finale, naturalmente, ma se si lavora per limitare rapidamente l'impatto, può essere una soluzione valida per la correzione a breve termine.
- È possibile disattivare le applicazioni integrate per il tuo contratto di locazione. Si tratta di un passaggio drastico che disabilita la possibilità per gli utenti finali di concedere il consenso a livello di tenant. Ciò impedisce agli utenti di concedere inavvertitamente l'accesso a un'applicazione dannosa. Questo non è fortemente consigliato perché compromette gravemente la capacità degli utenti di essere produttivi con le applicazioni di terze parti.  È possibile eseguire questa operazione attenendosi alla procedura descritta in [attivazione o](https://support.office.com/article/Turning-Integrated-Apps-on-or-off-7e453a40-66df-44ab-92a1-96786cb7fb34)disattivazione delle app integrate.

## <a name="secure-office-365-like-a-cybersecurity-pro"></a>Protezione di Office 365 come un Cybersecurity Pro
L'abbonamento a Office 365 è dotato di un potente set di funzionalità di sicurezza che è possibile utilizzare per proteggere i dati e gli utenti.  Utilizzare la Guida di [orientamento alla sicurezza di office 365: priorità principali per i primi 30 giorni, 90 giorni e oltre](https://support.office.com/article/office-365-security-roadmap-top-priorities-for-the-first-30-days-90-days-and-beyond-28c86a1c-e4dd-4aad-a2a6-c768a21cb352) per implementare le procedure consigliAte di Microsoft consigliati per la protezione del tenant di Office 365.
- Attività da eseguire nei primi 30 giorni.  Tali effetti hanno un impatto immediato e sono di scarso effetto per gli utenti.
- Attività da eseguire in 90 giorni. Questi richiedono un po' più di tempo per pianificare e implementare, ma migliorare notevolmente la posizione di sicurezza.
- Oltre 90 giorni. Questi miglioramenti vengono costruiti nei primi 90 giorni di lavoro.

## <a name="see-also"></a>Vedere anche:
- [Applicazione imprevista nell'elenco delle applicazioni](https://docs.microsoft.com/azure/active-directory/application-access-unexpected-application) gli amministratori possono eseguire le varie azioni che è possibile intraprendere dopo aver realizzato che sono presenti applicazioni inattese con accesso ai dati.
- [Integrazione di applicazioni con Azure Active Directory]  (https://docs.microsoft.com/azure/active-directory/active-directory-apps-permissions-consent) è una panoramica generale del consenso e delle autorizzazioni.  Prestare particolare attenzione alla [Panoramica della sezione relativa al Framework del consenso](https://docs.microsoft.com/azure/active-directory/develop/active-directory-integrating-applications#overview-of-the-consent-framework) .
- [Problemi durante lo sviluppo di un'applicazione](https://docs.microsoft.com/azure/active-directory/active-directory-application-dev-development-content-map) sono disponibili collegamenti a vari articoli relativi al consenso.
- [Gli oggetti Principal dell'applicazione e del servizio in Azure Active Directory (Azure ad)](https://docs.microsoft.com/azure/active-directory/develop/active-directory-application-objects) offrono una panoramica degli oggetti Principal del servizio e dell'applicazione che sono fondamentali per il modello di applicazione.
- [Manage Access to Apps](https://docs.microsoft.com/azure/active-directory/active-directory-managing-access-to-apps) è una panoramica delle funzionalità che gli amministratori devono gestire per la gestione dell'accesso degli utenti alle app.
