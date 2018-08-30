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
ms.service: o365-solutions
localization_priority: Normal
ms.custom: ''
ms.assetid: ''
search.appverid:
- MET150
description: Informazioni su come riconoscere e correggere l'attacco concede il consenso dell'utente in Office 365.
ms.openlocfilehash: 412b601af30ce87332225d271ec1a9e622012405
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/27/2018
ms.locfileid: "22531456"
---
# <a name="detect-and-remediate-illicit-consent-grants-in-office-365"></a>Rilevare e rimediare a concessioni di consenso illecite in Office 365

**Riepilogo**  Informazioni su come riconoscere e correggere l'attacco concede il consenso dell'utente in Office 365.

## <a name="what-is-the-illicit-consent-grant-attack-in-office-365"></a>Che cos'è l'attacco grant illecito consenso dell'utente in Office 365?
In un consenso illecito concedere attacco, che l'autore dell'attacco creata un'applicazione registrata Azure che richiede l'accesso ai dati, ad esempio informazioni sui contatti, posta elettronica, o documenti. L'autore dell'attacco trucchi quindi un utente finale in concedere il consenso dell'applicazione per accedere ai dati tramite un attacco di phishing o inserendo il codice nell'elenco dei siti attendibile. Dopo l'applicazione illecito è stato concesso il consenso, dispone di livello di account di accesso ai dati senza dover utilizzare un account organizzativo. Passaggi di correzione normale, come la reimpostazione delle password per gli account violati o che richiedono l'autenticazione a più fattori (MFA) su account, non sono efficaci da questo tipo di attacco, in quanto sono applicazioni di terze parti e sono esterni all'organizzazione. Questo tipo di attacchi utilizza un modello di interazione che presuppone l'entità che sta chiamando le informazioni sia automazione e non un'umane.

## <a name="what-does-an-illicit-consent-grant-attack-look-like-in-office-365"></a>Cosa un consenso illecito grant attacco sono simili a Office 365?
È necessario eseguire la ricerca di Office 365 di **Registro di controllo** per trovare segni, denominati anche gli indicatori di compromesso (IOC) di questo tipo di attacco. Per le organizzazioni con una base di utenti di grandi dimensioni e numero di applicazioni registrate Azure, la procedura consigliata è per esaminare la concede il consenso organizzazioni su base settimanale.
### <a name="steps-for-finding-signs-of-this-attack"></a>Passaggi per la ricerca di segni di questo tipo di attacco
1. Aprire il **centro conformità e sicurezza** in Office 365 tenant.
2. Passare al nodo **ricerca & indagini** e selezionare ricerca **Registro di controllo** .
3. Creare una ricerca (tutte le attività e tutti gli utenti) e filtrare i risultati il consenso all'applicazione e aggiungere OAuth2PermissionGrant.
4. Esaminare le proprietà estese per verificare se IsAdminContent è impostata su True.


Se questo valore è true, indica che un utente con privilegi di amministratore globale potrebbe concesse ampio accesso ai dati. Se si tratta di imprevisto, eseguire i passaggi per [verificare un attacco](detect-and-remediate-illicit-consent-grants.md#confirmattack).

<a name="confirmattack"> </a>
## <a name="how-to-confirm-an-attack"></a>Come verificare un attacco
Se si dispone di uno o più istanze del IOCs elencati sopra, è necessario eseguire ulteriori analisi di positivamente confermare che si è verificato l'attacco. È possibile utilizzare uno dei tre metodi di confermare l'attacco.
- Le applicazioni di inventario e le autorizzazioni mediante il portale di Azure Active Directory. Questo metodo è completo, ma è possibile archiviare un utente alla volta che è possibile richiedere molto tempo solo se si dispone di numerosi utenti di controllare.
- Le applicazioni di inventario e le relative autorizzazioni di utilizzo di PowerShell. Questo è il metodo più rapido e più completo, con la quantità minima di sovraccarico.
- Chiedi agli utenti singolarmente controllare le applicazioni e le autorizzazioni e restituiscono i risultati per gli amministratori per la risoluzione dei problemi.

## <a name="inventory-apps-with-access-in-your-organization"></a>Inventario applicazioni con accesso all'interno dell'organizzazione
È possibile eseguire questa operazione per gli utenti con il portale di Azure Active Directory o PowerShell o Chiedi agli utenti singolarmente enumerare l'accesso dell'applicazione.

### <a name="steps-for-using-the-azure-active-directory-portal"></a>Passaggi per l'utilizzo del portale di Azure Active Directory
È possibile cercare le applicazioni in cui un singolo utente è concesse le autorizzazioni tramite il [Portale di Azure Active Directory](https://portal.azure.com/). 
1. Accedere al portale di Azure con diritti amministrativi.
2. Selezionare blade Azure Active Directory.
3. Selezionare **gli utenti**.
4. Selezionare l'utente che si desidera controllare.
5. Selezionare **le applicazioni**.

Verranno visualizzate le applicazioni che vengono assegnate all'utente e quali autorizzazioni sono le applcations.

### <a name="steps-for-having-your-users-enumerate-their-application-access"></a>Procedure per gli utenti con consente di enumerare l'accesso di applicazione
Chiedi agli utenti di accedere a https://myapps.microsoft.com e controllare i propri accesso alle applicazioni disponibili. Si deve essere in grado di visualizzare tutte le app con access, visualizzare i dettagli (incluso l'ambito di accesso) e in grado di revocare i privilegi per le applicazioni potenzialmente dannoso o illecite.

### <a name="steps-for-doing-this-with-powershell"></a>Passaggi per eseguire questa operazione con PowerShell
Il modo più semplice per verificare l'attacco illecito Grant consenso consiste nell'eseguire [Get-AzureADPSPermissions.ps1](https://gist.github.com/psignoret/41793f8c6211d2df5051d77ca3728c09), che fornirà i dettagli di tutte le concede il consenso OAuth e le autorizzazioni di app per tutti gli utenti nella tenancy in un unico file con estensione csv. 

#### <a name="pre-requisites"></a>Prerequisiti
- Libreria di PowerShell di Azure Active Directory installata.
- Diritti di amministratore globale per il tenant che verrà eseguito lo script su.
- Amministratore locale nel computer da cui verrà eseguito gli script.

> [!IMPORTANT]
> È consigliabile richiedono l'autenticazione a più fattori per l'account amministrativo.  Questo script supporta l'autenticazione di MFA.

1. Accedere al computer in cui si esegue lo script da con diritti di amministratore locale.
2. Scaricare o copiare lo script [Get-AzureADPSPermissions.ps1](https://gist.github.com/psignoret/41793f8c6211d2df5051d77ca3728c09) da GitHub in una cartella da cui verrà eseguito il scruipt.  Questo valore sarà la stessa cartella in cui verrà scritto il file di output "permissions.csv".
3. Aprire un'istanza di PowerShell come amministratore e aprire la cartella che è stato salvato lo script.
4. Connetti alla directory utilizzando il cmdlet [Connect-AzureAD](https://docs.microsoft.com/powershell/module/azuread/connect-azuread?view=azureadps-2.0) .
5. Eseguire la riga di comando PowerShell come indicato di seguito:`.Get-AzureASPSPermissions.ps1 | Export-csv -path "Permissions.csv" -NoTypeInformation`

Lo script produce un file denominato Permissions.csv. Eseguire la procedura seguente per individuare la concessione di autorizzazioni illecito applicazione: 
1. Nella colonna ConsentType (colonna G) cercare il valore "AllPrinciples". L'autorizzazione AllPrincipals consente all'applicazione client di accedere al contenuto di tutti gli utenti nella tenancy. Le applicazioni di Office 365 native necessitano questa autorizzazione per il corretto funzionamento. Tutte le applicazioni di Microsoft non dispongono di questa autorizzazione è consigliabile leggere con attenzione.
2.  Nella revisione di colonna (colonna F) autorizzazioni le autorizzazioni ogni delegata applicazione è contenuto. Cercare autorizzazioni "Lettura" e "Write" o "*. Tutte le"autorizzazioni ed esaminare che queste con attenzione poiché potrebbero non essere appropriata.
3.  Esaminare gli utenti specifici a cui concedere le autorizzazioni. Nel caso alto profilo o gli utenti di grande impatto rilasciate non appropriati, è necessario verificare ulteriormente.
4.  Nella colonna ClientDisplayName (colonna C) cercare App che sembrano potenzialmente dannoso. Applicazioni con nomi errori di ortografia, nomi super troppo poco efficace o i nomi utente malintenzionato suonare è consigliabile leggere con attenzione.

## <a name="determine-the-scope-of-the-attack"></a>Determinare l'ambito di un attacco
Dopo avere accesso alle applicazioni di inventario, leggere la Office 365 di **Registro di controllo** per determinare l'ambito completo della violazione.  Ricerca utenti interessati, gli intervalli di tempo con l'applicazione illecito accedere all'organizzazione e le autorizzazioni dell'app con. È possibile cercare il **Registro di controllo** nel [centro conformità e sicurezza di Office 365](https://support.office.com/article/Search-the-audit-log-in-the-Office-365-Security-Compliance-Center-0d4d0f35-390b-4518-800e-0c7ec95e946c). 

> [!IMPORTANT]
> [Il controllo delle cassette postali](https://support.office.com/article/Enable-mailbox-auditing-in-Office-365-aaca8987-5b62-458b-9882-c28476a66918) e [il controllo attività per gli utenti e gli amministratori](https://support.office.com/article/turn-office-365-audit-log-search-on-or-off-e893b19a-660c-41f2-9074-d3631c95a014) devono sono stati abilitati prima di attacco per è possibile ottenere queste informazioni.

## <a name="how-to-stop-and-remediate-an-illicit-consent-grant--attack"></a>Come arrestare e correggere un attacco grant illecito consenso dell'utente
Dopo aver identificato un'applicazione con autorizzazioni illecite, è necessario diversi modi per rimuovere l'accesso.
- È possibile revocare autorizzazioni dell'applicazione in Azure Active Directory Portal da:
    - Passare all'utente interessato in blade **Utente di Azure Active Directory** .
    - Selezionare **le applicazioni**.
    - Selezionare l'applicazione illecito.
    - Fare clic su **Rimuovi** drill verso il basso.
- È possibile revocare la concessione consenso OAuth con PowerShell seguendo la procedura descritta in [Remove-AzureADOAuth2PermissionGrant](https://docs.microsoft.com/powershell/module/azuread/Remove-AzureADOAuth2PermissionGrant?view=azureadps-2.0).
- È possibile revocare l'assegnazione di ruolo servizio App PowerShell seguendo la procedura descritta in [Remove-AzureADServiceAppRoleAssignment](https://docs.microsoft.com/powershell/module/azuread/Remove-AzureADServiceAppRoleAssignment?view=azureadps-2.0).
- È inoltre possibile disattivare sign-in per completamente account interessati, che viene a sua volta disabilitare app l'accesso ai dati in tale account. Ovviamente, questo non è ideale per la produttività dell'utente finale, ma se si sta per limitare l'impatto rapidamente, può essere una correzione dei problemi a breve termine utilizzabile.
- È possibile disattivare le applicazioni integrate per la tenancy. Questo è un passaggio delicato che consente di disabilitare la possibilità per gli utenti finali dell'autorizzazione a livello di tenant. Ciò impedisce agli utenti di inavvertitamente la concessione dell'accesso a un'applicazione dannosa. Non è consigliabile come compromette notevolmente la possibilità degli utenti per lavorare con le applicazioni di terze parti.  È possibile farlo seguendo i passaggi descritti in [App integrata attivazione o disattivazione](https://support.office.com/article/Turning-Integrated-Apps-on-or-off-7e453a40-66df-44ab-92a1-96786cb7fb34).

## <a name="secure-office-365-like-a-cybersecurity-pro"></a>Protezione di Office 365 come alla sicurezza informatica pro
La sottoscrizione a Office 365 è dotato di un insieme completo di funzionalità di protezione che è possibile utilizzare per proteggere i dati e gli utenti.  Utilizzare il [roadmap di protezione di Office 365: principali priorità per i primi 30 giorni, 90 giorni e oltre](https://support.office.com/article/office-365-security-roadmap-top-priorities-for-the-first-30-days-90-days-and-beyond-28c86a1c-e4dd-4aad-a2a6-c768a21cb352) per l'implementazione Microsoft di procedure consigliate per la protezione di Office 365 tenant.
- Attività per raggiungere i primi 30 giorni.  Questi hanno effetto immediato e sono basso impatto per gli utenti.
- Attività da eseguire per 90 giorni. Queste un po' di tempo maggiore pianificare e implementare ma migliorare notevolmente le condizioni di sicurezza generali.
- Oltre a 90 giorni. Questi miglioramenti build per il lavoro di 90 giorni primo.

## <a name="see-also"></a>Vedere anche:
- Gli amministratori tramite diverse operazioni da eseguire dopo realizza vi sono applicazioni impreviste con l'accesso ai dati vengono illustrati in modo [imprevisto applicazione nell'elenco applicazioni](https://docs.microsoft.com/azure/active-directory/application-access-unexpected-application) .
- [Integrazione delle applicazioni con Azure Active Directory]  (https://docs.microsoft.com/azure/active-directory/active-directory-apps-permissions-consent) viene fornita una panoramica generale del consenso dell'utente e autorizzazioni.  Prestare particolare attenzione nella sezione [Panoramica del framework consenso dell'utente](https://docs.microsoft.com/azure/active-directory/develop/active-directory-integrating-applications#overview-of-the-consent-framework) .
- [Problemi relativi allo sviluppo dell'applicazione](https://docs.microsoft.com/azure/active-directory/active-directory-application-dev-development-content-map) sono disponibili collegamenti a varie consenso gli articoli correlati.
- [Oggetti Application e servizio entità di Azure Active Directory (Azure Active Directory)](https://docs.microsoft.com/azure/active-directory/develop/active-directory-application-objects) viene fornita una panoramica degli oggetti entità applicazione e il servizio di base per il modello dell'applicazione.
- [Gestire l'accesso alle App](https://docs.microsoft.com/azure/active-directory/active-directory-managing-access-to-apps) viene fornita una panoramica delle funzionalità che gli amministratori devono gestire l'accesso utente per le applicazioni.