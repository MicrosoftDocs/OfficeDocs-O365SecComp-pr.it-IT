---
title: Definire i criteri di barriera delle informazioni
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 05/31/2019
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.collection:
- M365-security-compliance
localization_priority: None
description: Informazioni su come definire i criteri per le barriere informative in Microsoft teams.
ms.openlocfilehash: 3ec9d89f22456f00104135013ee6009e8e4824df
ms.sourcegitcommit: 4fedeb06a6e7796096fc6279cfb091c7b89d484d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/31/2019
ms.locfileid: "34668310"
---
# <a name="define-policies-for-information-barriers-preview"></a>Definire i criteri per le barriere informative (anteprima)

Con barriere informative, è possibile definire criteri che sono stati creati per impedire a determinati segmenti di utenti di comunicare tra loro oppure consentire a segmenti specifici di comunicare solo con determinati altri segmenti. I criteri barriera alle informazioni consentono all'organizzazione di mantenere la conformità agli standard e ai regolamenti del settore e di evitare potenziali conflitti di interesse. Per ulteriori informazioni, vedere [barriere informative (Preview)](information-barriers.md). 

> [!IMPORTANT]
> In questo articolo viene descritto come pianificare, definire, implementare e gestire i criteri di barriera delle informazioni. Sono coinvolti diversi passaggi e il flusso di lavoro è suddiviso in più parti. Assicurarsi di leggere i [prerequisiti](#prerequisites) e l'intero processo prima di iniziare a definire (o modificare) i criteri di barriera delle informazioni.

## <a name="concepts-of-information-barrier-policies"></a>Concetti relativi ai criteri di barriera delle informazioni

Prima di pianificare, definire e implementare criteri di barriera delle informazioni, è possibile conoscere i concetti sottostanti. Con gli ostacoli alle informazioni, è possibile utilizzare gli attributi degli account utente, i segmenti, i criteri di barriera delle informazioni e un processo di applicazione dei criteri descritto in questo articolo. 

- **Gli attributi degli account utente** sono definiti in Azure Active Directory (o Exchange Online). Questi attributi possono includere reparto, titolo del processo, posizione, nome del team e così via. 

- I **segmenti** sono definiti nel centro sicurezza & conformità di Office 365 utilizzando un **attributo dell'account utente**selezionato, ad esempio reparto, titolo del processo, posizione, nome del team o qualsiasi [attributo supportato](information-barriers-attributes.md). La definizione di segmenti non ha effetto sugli utenti. imposta solo la fase per i criteri di barriera delle informazioni da definire e quindi applicare.

- I **criteri di barriera delle informazioni** vengono definiti e assegnati a singoli **segmenti**. Non tutti i segmenti avranno un criterio assegnato. Inoltre, non è possibile assegnare a un singolo segmento più di un criterio. Quando si definiscono i criteri, è possibile scegliere tra due tipi di criteri:
    - Criteri che impediscono a un segmento di comunicare con un altro segmento
    - Criteri che consentono a un segmento di comunicare con solo alcuni segmenti

    In teoria, è possibile utilizzare il numero minimo di criteri per garantire che l'organizzazione sia conforme ai requisiti legali e di settore.

- L' **applicazione criterio** viene completata dopo la definizione di tutti i criteri di barriera delle informazioni e si è pronti per applicarli all'interno dell'organizzazione.

## <a name="the-work-flow-at-a-glance"></a>Il flusso di lavoro in un colpo d'occhio

|Fase    |Elementi coinvolti  |
|---------|---------|
|[Verificare che i prerequisiti siano soddisfatti](#prerequisites)     |-Verificare che la sottoscrizione includa barriere informative<br/>-Verificare di disporre delle autorizzazioni necessarie per definire/modificare segmenti e criteri<br/>-Verificare che i dati della directory riflettano la struttura dell'organizzazione<br/>-Verificare che la ricerca di directory con ambito sia abilitata in Microsoft Teams<br/>-Verificare che la registrazione di controllo sia attivata<br/>-Utilizzare PowerShell per eseguire le attività descritte in questo articolo (vengono forniti cmdlet di esempio)<br/>-Fornire il consenso dell'amministratore per le barriere informative in Microsoft Teams (sono inclusi i passaggi)          |
|[Parte 1: segmentare tutti gli utenti dell'organizzazione](#part-1-segment-users)     |-Determinare quali criteri sono necessari<br/>-Creare un elenco di segmenti da definire<br/>-Identificare gli attributi da utilizzare<br/>-Definire i segmenti in termini di filtri per i criteri        |
|[Parte 2: definire i criteri di barriera delle informazioni](#part-2-define-information-barrier-policies)     |-Definire i criteri (non è ancora applicabile)<br/>-Scegliere tra due tipi (blocca o Consenti) |
|[Parte 3: applicare i criteri di barriera delle informazioni](#part-3-apply-information-barrier-policies)     |-Impostare i criteri per lo stato attivo<br/>-Eseguire l'applicazione per i criteri<br/>-Verificare lo stato di un criterio         |
|(Se necessario) [Modificare un segmento o un criterio](#edit-a-segment-or-a-policy)     |-Modificare un segmento<br/>-Modificare o rimuovere un criterio<br/>-Eseguire l'applicazione per i criteri<br/>-Verificare lo stato di un criterio         |
|(Se necessario) [Risoluzione dei problemi](information-barriers-troubleshooting.md)|-Intervenire quando i criteri non funzionano come previsto|

## <a name="prerequisites"></a>Prerequisiti

**Attualmente, la caratteristica barriera informativa è in anteprima privata**. Quando queste funzionalità sono in genere disponibili, verranno incluse nelle sottoscrizioni, ad esempio:

- Microsoft 365 E5
- Office 365 E5
- Office 365 Advanced Compliance
- Microsoft 365 E5 Information Protection and Compliance

Per ulteriori informazioni, vedere [Compliance Solutions](https://products.office.com/business/security-and-compliance/compliance-solutions).

### <a name="permissions"></a>Autorizzazioni

Per definire o modificare i criteri di barriera delle informazioni, **è necessario essere assegnati a un ruolo appropriato**, ad esempio uno dei seguenti:
- Amministratore globale di Microsoft 365 Enterprise
- Amministratore globale di Office 365
- Amministratore di conformità
- IB Compliance Management (questo è un nuovo ruolo)

Per ulteriori informazioni sui ruoli e sulle autorizzazioni, vedere Permissions [in the Office 365 Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).
       
### <a name="directory-data"></a>Dati della directory

Verificare **che la struttura dell'organizzazione sia riflessa nei dati della directory**. Per eseguire questa operazione, verificare che gli attributi degli account utente, ad esempio appartenenza a gruppo, nome reparto e così via, siano inseriti correttamente in Azure Active Directory (o Exchange Online). Per ulteriori informazioni, vedere le risorse seguenti:
- [Attributi per i criteri di barriera delle informazioni (anteprima)](information-barriers-attributes.md)
- [Aggiungere o aggiornare le informazioni del profilo di un utente tramite Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal)
- [Configurare le proprietà degli account utente con Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/configure-user-account-properties-with-office-365-powershell)

### <a name="scoped-directory-search"></a>Ricerca nell'ambito della directory

**Prima di definire il primo criterio barriera informativo dell'organizzazione, è necessario [abilitare la ricerca nell'ambito della directory in Microsoft teams](https://docs.microsoft.com/MicrosoftTeams/teams-scoped-directory-search)**. Attendere almeno 24 ore dopo aver abilitato la ricerca nell'ambito della directory prima di impostare o definire i criteri di barriera delle informazioni.

### <a name="audit-logging"></a>Registrazione di controllo

Per cercare lo stato di un'applicazione di criteri, è necessario che la registrazione di controllo sia attivata. Si consiglia di eseguire questa operazione prima di iniziare a definire segmenti o criteri. Per ulteriori informazioni, vedere [attivazione o disattivazione della ricerca del registro di controllo di Office 365](turn-audit-log-search-on-or-off.md).

### <a name="powershell"></a>PowerShell

**Attualmente, i criteri barriera informativi vengono definiti e gestiti nel centro conformità & sicurezza di Office 365 tramite i cmdlet di PowerShell**. Anche se in questo articolo sono disponibili diversi scenari ed esempi, è necessario avere familiarità con i cmdlet e i parametri di PowerShell. 

[Connettersi a PowerShell di Office 365 Security & Compliance Center](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps).

### <a name="provide-admin-consent-for-information-barriers-in-microsoft-teams"></a>Fornire il consenso dell'amministratore per le barriere informative in Microsoft Teams

Utilizzare la procedura seguente per consentire ai criteri di barriera delle informazioni di funzionare come previsto in Microsoft teams. 

Ad esempio, quando i criteri sono sul posto, gli ostacoli alle informazioni possono rimuovere persone dalle sessioni di chat di cui non si suppone che si trovino. Questo contribuisce a garantire che l'organizzazione rimanga conforme ai criteri e alle normative. 

1. Eseguire i cmdlet di PowerShell seguenti:

    ```
    Login-AzureRmAccount 
    $appId="bcf62038-e005-436d-b970-2a472f8c1982" 
    $sp=Get-AzureRmADServicePrincipal -ServicePrincipalName $appId
    if ($sp -eq $null) { New-AzureRmADServicePrincipal -ApplicationId $appId }
    Start-Process  "https://login.microsoftonline.com/common/adminconsent?client_id=$appId"
    ```

2. Quando richiesto, accedere con l'account aziendale o dell'Istituto di istruzione per Office 365.

3. Nella finestra di dialogo **autorizzazioni richieste** esaminare le informazioni e quindi scegliere **accetta**.

## <a name="part-1-segment-users"></a>Parte 1: segmentare gli utenti

Durante questa fase, è possibile determinare quali criteri sono necessari, creare un elenco di segmenti da definire e quindi definire i segmenti.

### <a name="determine-what-policies-are-needed"></a>Determinare quali criteri sono necessari

Considerando le normative legali e industriali, quali sono i gruppi all'interno dell'organizzazione che avranno bisogno di criteri barriera informativi? Creare un elenco. Esistono gruppi a cui è necessario impedire la comunicazione con un altro gruppo? Esistono gruppi che devono essere autorizzati a comunicare solo con uno o due altri gruppi? Si pensi ai criteri necessari come appartenenti a uno dei due gruppi:
- **Blocco dei criteri** che impediscono a un gruppo di comunicare con un altro gruppo
- **Consenti ai criteri** che consentono a determinati gruppi di comunicare con solo alcuni altri gruppi.

Quando si ha un elenco iniziale di gruppi e criteri, procedere all'identificazione dei segmenti necessari.

Vedere l' [esempio: reparti di Contoso e pianificazione](#contosos-departments-and-plan) in questo articolo.

### <a name="identify-segments"></a>Identificare i segmenti

Oltre all'elenco iniziale dei criteri, creare un elenco di segmenti per l'organizzazione. Tutti gli utenti dell'organizzazione devono appartenere a un segmento e nessun utente deve appartenere a due o più segmenti. Ogni segmento può disporre di un solo criterio barriera informativo applicato. 

Determinare gli attributi dei dati di directory dell'organizzazione che verranno utilizzati per definire i segmenti. È possibile utilizzare *Department*, *member*o uno qualsiasi degli attributi supportati. Assicurarsi di avere valori nell'attributo selezionato per tutti gli utenti. Per visualizzare un elenco degli attributi supportati, fare riferimento agli [attributi per i criteri di barriera delle informazioni (Preview)](information-barriers-attributes.md).

> [!IMPORTANT]
> **Prima di procedere alla sezione successiva, verificare che i dati della directory dispongano di valori per gli attributi che è possibile utilizzare per definire i segmenti**. Se i dati della directory non contengono valori per gli attributi che si desidera utilizzare, tutti gli account utente devono essere aggiornati per includere tali informazioni prima di procedere con le barriere informative. Per ottenere assistenza, vedere le risorse seguenti:<br/>- [Configurare le proprietà degli account utente con Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/configure-user-account-properties-with-office-365-powershell)<br/>- [Aggiungere o aggiornare le informazioni del profilo di un utente tramite Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal)

### <a name="define-segments-using-powershell"></a>Definire segmenti tramite PowerShell

> [!IMPORTANT]
> Verificare **che i segmenti non si sovrappongano**. Tutti gli utenti dell'organizzazione devono appartenere a un solo segmento. Nessun utente deve appartenere a due o più segmenti. I segmenti devono essere definiti per tutti gli utenti dell'organizzazione. Vedere l' [esempio: segmenti definiti da Contoso](#contosos-defined-segments) in questo articolo.

1. Per definire un segmento di organizzazione, utilizzare il cmdlet **New-OrganizationSegment** con il parametro **UserGroupFilter** che corrisponde all' [attributo](information-barriers-attributes.md) che si desidera utilizzare. 

    Sintassi`New-OrganizationSegment -Name "segmentname" -UserGroupFilter "attribute -eq 'attributevalue'"`

    Esempio:  `New-OrganizationSegment -Name "HR" -UserGroupFilter "Department -eq 'HR'"`

    In questo esempio, un segmento denominato *HR* è definito utilizzando *HR*, un valore nell'attributo Department.

2. Ripetere il passaggio 1 per ogni segmento che si desidera definire.

    Dopo aver eseguito ogni cmdlet, verrà visualizzato un elenco di dettagli sul nuovo segmento. I dettagli includono il tipo di segmento, che ha creato o modificato l'ultima volta e così via. 

Dopo aver definito i segmenti, procedere alla definizione dei criteri barriera informativi.

## <a name="part-2-define-information-barrier-policies"></a>Parte 2: definire i criteri di barriera delle informazioni

Con l'elenco dei segmenti di utenti e dei criteri barriera informativi che si desidera definire, selezionare uno scenario e quindi eseguire la procedura seguente. 

> [!IMPORTANT]
> Assicurarsi **che durante la definizione dei criteri non venga assegnato più di un criterio a un segmento**. Ad esempio, se si definisce un criterio per un segmento denominato *Sales*, non definire un criterio aggiuntivo per le *vendite*. 

Determinare se è necessario impedire la comunicazione tra determinati segmenti o limitare le comunicazioni a determinati segmenti. Scegliere tra gli scenari riportati di seguito per definire i criteri.

- [Scenario 1: bloccare le comunicazioni tra segmenti](#scenario-1-block-communications-between-segments)
- [Scenario 2: consentire a un segmento di comunicare solo con un altro segmento](#scenario-2-allow-a-segment-to-communicate-only-with-one-other-segment)

> [!NOTE]
> Quando si definiscono i criteri di barriera delle informazioni, assicurarsi di impostare tali criteri sullo stato inattivo fino a quando non si è pronti per applicarli. La definizione o la modifica dei criteri non influiscono sugli utenti finché tali criteri non sono impostati sullo stato attivo e quindi applicati.

Vedere l' [esempio: criteri di protezione delle informazioni di Contoso](#contosos-information-barrier-policies) in questo articolo.

### <a name="scenario-1-block-communications-between-segments"></a>Scenario 1: bloccare le comunicazioni tra segmenti

Se si desidera bloccare i segmenti dalla comunicazione tra loro, è possibile definire due criteri: uno per ogni direzione. Ogni criterio blocca la comunicazione solo in un modo.

Ad esempio, si supponga di voler bloccare le comunicazioni tra il segmento A e il segmento B. In questo caso, è possibile definire un criterio che impedisca al segmento A di comunicare con il segmento B e quindi definire un secondo criterio per impedire che il segmento B comunichi con il segmento A.

1. Per definire il primo criterio di blocco, utilizzare il cmdlet **New-InformationBarrierPolicy** con il parametro **SegmentsBlocked** . 

    Sintassi`New-InformationBarrierPolicy -Name "policyname" -AssignedSegment "segmentname" -SegmentsBlocked "segmentname"`

    Esempio:  `New-InformationBarrierPolicy -Name "Sales-Research" -AssignedSegment "Sales" -SegmentsBlocked "Research" -State Inactive`

    In questo esempio, è stato definito un criterio denominato *Sales-Research* per un segmento denominato *Sales*. Se attivo e applicato, questo criterio impedisce alle persone in *vendita* di comunicare con gli utenti di un segmento denominato *Research*.

2. Per definire il secondo segmento di blocco, utilizzare di nuovo il cmdlet **New-InformationBarrierPolicy** con il parametro **SegmentsBlocked** , stavolta con i segmenti invertiti.

    Esempio:  `New-InformationBarrierPolicy -Name "Research-Sales" -AssignedSegment "Research" -SegmentsBlocked "Sales" -State Inactive`

    In questo esempio, è stato definito un criterio denominato *Research-Sales* per impedire che la ricerca comunichi con le vendite.
 
2. Procedere con una delle operazioni seguenti:

   - (Se necessario) [Definire un criterio per consentire a un segmento di comunicare solo con un altro segmento](#scenario-2-allow-a-segment-to-communicate-only-with-one-other-segment) 
   - (Dopo che sono stati definiti tutti i criteri) [Applicare i criteri di barriera delle informazioni](#part-3-apply-information-barrier-policies)

### <a name="scenario-2-allow-a-segment-to-communicate-only-with-one-other-segment"></a>Scenario 2: consentire a un segmento di comunicare solo con un altro segmento

1. Per consentire a un segmento di comunicare solo con un altro segmento, utilizzare il cmdlet **New-InformationBarrierPolicy** con il parametro **SegmentsAllowed** . 

    Sintassi`New-InformationBarrierPolicy -Name "policyname" -AssignedSegment "segmentname" -SegmentsAllowed "segmentname"`

    Esempio:  `New-InformationBarrierPolicy -Name "Manufacturing-HR" -AssignedSegment "Manufacturing" -SegmentsAllowed "HR" -State Inactive`

    In questo esempio, è stato definito un criterio denominato *Manufacturing-HR* per un segmento denominato *Manufacturing*. Se attivo e applicato, questo criterio consente alle persone nella *produzione* di comunicare solo con le persone in un segmento denominato *HR*. In questo caso, la produzione non è in grado di comunicare con gli utenti che non fanno parte di HR.

    **Se necessario, è possibile specificare più segmenti con questo cmdlet, come illustrato nei due esempi riportati di seguito.**

    Sintassi`New-InformationBarrierPolicy -Name "policyname" -AssignedSegment "segmentname" -SegmentsAllowed "segmentname, segmentname"`

    **Esempio 1: definire un criterio per consentire a più segmenti di comunicare con un solo altro segmento**

    `New-InformationBarrierPolicy -Name "ResearchManufacturing-HR" -AssignedSegment "Research, Manufacturing" -SegmentsAllowed "HR" -State Inactive`

    In questo esempio, è stato definito un criterio che consente ai segmenti di *ricerca* e *produzione* di comunicare solo con *HR*.

    **Esempio 2: definire un criterio per consentire a più segmenti di comunicare con solo alcuni segmenti**    

    `New-InformationBarrierPolicy -Name "SalesMarketing-HRManufacturing" -AssignedSegment "Sales, Marketing" -SegmentsAllowed "HR, Manufacturing" -State Inactive`

    In questo esempio, è stato definito un criterio che consente ai segmenti *vendite* e *Marketing* di comunicare solo con le *risorse umane* e la *produzione*.

    Ripetere questo passaggio per ogni criterio che si desidera definire per consentire a segmenti specifici di comunicare con solo alcuni segmenti specifici.

2. Procedere con una delle operazioni seguenti:

   - (Se necessario) [Definire un criterio per bloccare le comunicazioni tra i segmenti](#scenario-1-block-communications-between-segments) 
   - (Dopo che sono stati definiti tutti i criteri) [Applicare i criteri di barriera delle informazioni](#part-3-apply-information-barrier-policies)

## <a name="part-3-apply-information-barrier-policies"></a>Parte 3: applicare i criteri di barriera delle informazioni

I criteri di barriera delle informazioni non sono attivi finché non vengono impostati allo stato attivo e quindi vengono applicati i criteri.

1. Utilizzare il cmdlet **Get-InformationBarrierPolicy** per visualizzare un elenco di criteri definiti. Tenere presente lo stato e l'identità (GUID) di ogni criterio.

    Sintassi`Get-InformationBarrierPolicy`

2. Per impostare un criterio su stato attivo, utilizzare il cmdlet **set-InformationBarrierPolicy** con un parametro **Identity** e il parametro **state** impostato su **attivo**. 

    Sintassi`Set-InformationBarrierPolicy -Identity GUID -State Active`

    Esempio:  `Set-InformationBarrierPolicy -Identity 43c37853-ea10-4b90-a23d-ab8c93772471 -State Active`
    
    In questo esempio, viene impostato un criterio barriera informativo che include il GUID *43c37853-EA10-4b90-a23d-ab8c93772471* per lo stato attivo.

    Ripetere questo passaggio come appropriato per ogni criterio.

3. Dopo aver impostato lo stato attivo per i criteri barriera informativi, utilizzare il cmdlet **Start-InformationBarrierPoliciesApplication** nel centro sicurezza & conformità di Office 365.

    Sintassi`Start-InformationBarrierPoliciesApplication`

    Dopo circa mezz'ora, i criteri vengono applicati dall'utente per l'organizzazione. Se l'organizzazione è di grandi dimensioni, il completamento di questo processo può richiedere 24 ore (o più). (Come linee guida generali, è necessario circa un'ora per elaborare gli account utente di 5.000).

## <a name="verify-status-of-user-accounts-segments-policies-or-policy-application"></a>Verificare lo stato degli account utente, i segmenti, i criteri o l'applicazione di criteri

Tramite PowerShell, è possibile verificare lo stato degli account utente, i segmenti, i criteri e l'applicazione dei criteri, come indicato nella tabella seguente.

|Per verificare questo  |Esegui questa operazione  |
|---------|---------|
|Account utente     |Utilizzare il cmdlet **Get-InformationBarrierRecipientStatus** con i parametri Identity. <p>Sintassi`Get-InformationBarrierRecipientStatus -Identity <value> -Identity2 <value>` <p>È possibile utilizzare qualsiasi valore che identifichi in modo univoco ogni utente, ad esempio nome, alias, nome distinto, nome di dominio canonico, indirizzo di posta elettronica o GUID. <p>Esempio:  `Get-InformationBarrierRecipientStatus -Identity meganb -Identity2 alexw` <p>In questo esempio, si fa riferimento a due account utente in Office 365: *meganb* per *Megan*e *alexw* per *Alex*. <p>È inoltre possibile utilizzare questo cmdlet per un singolo utente: `Get-InformationBarrierRecipientStatus -Identity <value>` <p>Questo cmdlet restituisce informazioni sugli utenti, ad esempio i valori degli attributi e tutti i criteri di barriera delle informazioni applicati.|
|Segmenti     |Utilizzare il cmdlet **Get-OrganizationSegment** .<p>Sintassi`Get-OrganizationSegment` <p>In questo modo verrà visualizzato un elenco di tutti i segmenti definiti per l'organizzazione.         |
|Criteri barriera di informazioni     |Utilizzare il cmdlet **Get-InformationBarrierPolicy** . <p> Sintassi`Get-InformationBarrierPolicy` <p>In questo modo verrà visualizzato un elenco di criteri barriera informativi definiti e il relativo stato.       |
|Applicazione dei criteri barriera informativa più recente     | Utilizzare il cmdlet **Get-InformationBarrierPoliciesApplicationStatus** . <p>Sintassi`Get-InformationBarrierPoliciesApplicationStatus`<p>    Verranno visualizzate informazioni sul modo in cui l'applicazione del criterio è stata completata, non è riuscita o è in corso.       |
|Tutte le applicazioni dei criteri barriera di informazioni|Utilizzare`Get-InformationBarrierPoliciesApplicationStatus -All $true`<p>Verranno visualizzate informazioni sul modo in cui l'applicazione del criterio è stata completata, non è riuscita o è in corso.|

## <a name="stop-a-policy-application"></a>Arrestare un'applicazione di criteri

Se dopo aver avviato l'applicazione di criteri di barriera delle informazioni si desidera impedire l'applicazione di tali criteri, utilizzare la procedura seguente. Tenere presente che richiederà circa 30-35 minuti per l'avvio del processo.

1. Per visualizzare lo stato dell'applicazione del criterio barriera alle informazioni più recente, utilizzare il cmdlet **Get-InformationBarrierPoliciesApplicationStatus** .

    Sintassi`Get-InformationBarrierPoliciesApplicationStatus`

    Tenere presente il GUID dell'applicazione.

2. Utilizzare il cmdlet **Stop-InformationBarrierPoliciesApplication** con un parametro Identity.

    Sintassi`Stop-InformationBarrierPoliciesApplication -Identity GUID`

    Esempio:  `InformationBarrierPoliciesApplication -Identity 46237888-12ca-42e3-a541-3fcb7b5231d1`

## <a name="edit-a-segment-or-a-policy"></a>Modificare un segmento o un criterio

### <a name="edit-a-segment"></a>Modifica di un segmento

1. Per visualizzare tutti i segmenti esistenti, utilizzare il cmdlet **Get-OrganizationSegment** .
    
    Sintassi`Get-OrganizationSegment`

    Verrà visualizzato un elenco di segmenti e dettagli per ognuno, ad esempio il tipo di segmento, il valore di UserGroupFilter, che ha creato o modificato l'oggetto, il GUID e così via.

    > [!TIP]
    > Stampa o salvataggio dell'elenco dei segmenti per riferimento in un secondo momento. Ad esempio, se si desidera modificare un segmento, è necessario conoscere il nome o il valore di identificazione (utilizzato con il parametro Identity).

2. Per modificare un segmento, utilizzare il cmdlet **set-OrganizationSegment** con il parametro **Identity** e i dettagli rilevanti. 

    Sintassi`Set-OrganizationSegment -Identity GUID -UserGroupFilter "attribute -eq 'attributevalue'"`

    Esempio:  `Set-OrganizationSegment -Identity c96e0837-c232-4a8a-841e-ef45787d8fcd -UserGroupFilter "Department -eq 'HRDept'"`

    In questo esempio, per il segmento che ha il GUID *c96e0837-C232-4a8a-841E-ef45787d8fcd*, il nome del reparto è stato aggiornato in "HRDept".

Dopo aver completato i segmenti di modifica per l'organizzazione, è possibile procedere alla [definizione](#part-2-define-information-barrier-policies) o alla [modifica](#edit-a-policy) dei criteri di barriera delle informazioni.

### <a name="edit-a-policy"></a>Modificare un criterio

1. Per visualizzare un elenco dei criteri di barriera delle informazioni correnti, utilizzare il cmdlet **Get-InformationBarrierPolicy** .

    Sintassi`Get-InformationBarrierPolicy`

    Nell'elenco dei risultati, identificare il criterio che si desidera modificare. Prendere nota del GUID e del nome del criterio.

2. Utilizzare il cmdlet **set-InformationBarrierPolicy** con un parametro **Identity** e specificare le modifiche che si desidera eseguire.

    Sintassi (il blocco dei segmenti dalla comunicazione con altri segmenti): 

    `Set-InformationBarrierPolicy -Identity GUID -SegmentsBlocked "segmentname, segmentname"` 

    Sintassi (che consente ai segmenti di comunicare solo con alcuni altri segmenti):
    
    ``Set-InformationBarrierPolicy -Identity GUID -SegmentsAllowed "segmentname, segmentname"``

    Ad esempio, si supponga che sia stato definito un criterio per bloccare la ricerca dalla comunicazione con vendite e marketing. Il criterio è stato definito utilizzando il cmdlet seguente:`New-InformationBarrierPolicy -Name "Research-SalesMarketing" -AssignedSegment "Research" -SegmentsBlocked "Sales, Marketing"`
    
    Si supponga di voler cambiare in modo che gli utenti nella ricerca possano comunicare solo con le persone in HR. Per apportare questa modifica, è possibile utilizzare questo cmdlet:`Set-InformationBarrierPolicy -Identity 43c37853-ea10-4b90-a23d-ab8c93772471 -SegmentsAllowed "HR"`

3. Dopo aver completato la modifica di un criterio, accertarsi di applicare le modifiche. (Vedere [Apply Information Barrier Policies](#part-3-apply-information-barrier-policies)).

### <a name="remove-a-policy"></a>Rimozione di un criterio

1. Per visualizzare un elenco dei criteri di barriera delle informazioni correnti, utilizzare il cmdlet **Get-InformationBarrierPolicy** .

    Sintassi`Get-InformationBarrierPolicy`

    Nell'elenco dei risultati, identificare il criterio che si desidera rimuovere. Prendere nota del GUID e del nome del criterio. Verificare che il criterio sia impostato su stato inattivo.

2. Utilizzare il cmdlet **Remove-InformationBarrierPolicy** con un parametro Identity.

    Sintassi`Remove-InformationBarrierPolicy -Identity GUID`

    Esempio: Supponiamo di voler rimuovere un criterio con GUID *43c37853-EA10-4b90-a23d-ab8c93772471*. A tale scopo, viene utilizzato il cmdlet seguente:
    
    `Remove-InformationBarrierPolicy -Identity 43c37853-ea10-4b90-a23d-ab8c93772471`

    Quando richiesto, confermare la modifica.

3. Ripetere i passaggi 1-2 per ogni criterio che si desidera rimuovere.

4. Una volta terminata la rimozione dei criteri, applicare le modifiche. A tale scopo, utilizzare il cmdlet **Start-InformationBarrierPoliciesApplication** .

    Sintassi`Start-InformationBarrierPoliciesApplication`

    Le modifiche vengono applicate dall'utente per l'organizzazione. Se l'organizzazione è di grandi dimensioni, il completamento di questo processo può richiedere 24 ore (o più).

### <a name="set-a-policy-to-inactive-status"></a>Impostare un criterio su stato inattivo

1. Per visualizzare un elenco dei criteri di barriera delle informazioni correnti, utilizzare il cmdlet **Get-InformationBarrierPolicy** .

    Sintassi`Get-InformationBarrierPolicy`

    Nell'elenco dei risultati, identificare il criterio che si desidera modificare (o rimuovere). Prendere nota del GUID e del nome del criterio.

2. Per impostare lo stato del criterio su inattivo, utilizzare il cmdlet **set-InformationBarrierPolicy** con un parametro Identity e il parametro state impostato su inattivo.

    Sintassi`Set-InformationBarrierPolicy -Identity GUID -State Inactive`

    `Set-InformationBarrierPolicy -Identity 43c37853-ea10-4b90-a23d-ab8c9377247 -State Inactive`

    In questo esempio, viene impostato un criterio barriera informativo che include GUID *43c37853-EA10-4b90-a23d-ab8c9377247* su uno stato inattivo.

3. Per applicare le modifiche, utilizzare il cmdlet **Start-InformationBarrierPoliciesApplication** .

    Sintassi`Start-InformationBarrierPoliciesApplication`

    Le modifiche vengono applicate dall'utente per l'organizzazione. Se l'organizzazione è di grandi dimensioni, il completamento di questo processo può richiedere 24 ore (o più). (Come linee guida generali, è necessario circa un'ora per elaborare gli account utente di 5.000).

A questo punto, uno o più criteri barriera informazioni sono impostati sullo stato inattivo. Da qui, è possibile eseguire una delle operazioni seguenti:
- Lasciarlo come è (un criterio impostato su stato inattivo non ha alcun effetto sugli utenti)
- [Modificare un criterio](#edit-a-policy) 
- [Rimozione di un criterio](#remove-a-policy)

## <a name="example-contosos-departments-segments-and-policies"></a>Esempio: reparti, segmenti e criteri di contoso

Per sapere in che modo un'organizzazione può approcciare la definizione di segmenti e criteri, prendere in considerazione l'esempio seguente.

### <a name="contosos-departments-and-plan"></a>Piani e reparti di contoso

Contoso dispone di cinque reparti: HR, Sales, marketing, Research e Manufacturing. Per rimanere conformi alle normative industriali, gli utenti di alcuni reparti non sono tenuti a comunicare con altri reparti, come indicato nella tabella seguente:

|Segmento  |Può parlare con  |Non è possibile parlare con  |
|---------|---------|---------|
|HR     |Tutti         |(nessuna restrizione)         |
|Sales     |HR, marketing, Manufacturing         |Ricerca         |
|Marketing     |Tutti         |(nessuna restrizione)         |
|Ricerca     |HR, marketing, Manufacturing        |Sales     |
|Produzione |HR, marketing |Altre persone che non siano HR o marketing |

In questo caso, il piano di Contoso include tre criteri di barriera delle informazioni:

1. Criteri che impediscono alla vendita di comunicare con la ricerca (e un altro criterio per impedire alla ricerca di comunicare con le vendite)
2. Un criterio destinato a consentire la produzione per la comunicazione solo con HR e marketing 

Non è necessario definire i criteri per HR o marketing.

### <a name="contosos-defined-segments"></a>Segmenti definiti di contoso

Contoso utilizzerà l'attributo Department in Azure Active Directory per definire i segmenti, come indicato di seguito:

|Reparto  |Definizione di segmento  |
|---------|---------|
|HR     | `New-OrganizationSegment -Name "HR" -UserGroupFilter "Department -eq 'HR'"`        |
|Sales     | `New-OrganizationSegment -Name "Sales" -UserGroupFilter "Department -eq 'Sales'"`        |
|Marketing     | `New-OrganizationSegment -Name "Marketing" -UserGroupFilter "Department -eq 'Marketing'"`        |
|Ricerca     | `New-OrganizationSegment -Name "Research" -UserGroupFilter "Department -eq 'Research'"`        |
|Produzione     | `New-OrganizationSegment -Name "Manufacturing" -UserGroupFilter "Department -eq 'Manufacturing'"`        |

Con i segmenti definiti, contoso procede alla definizione dei criteri. 

### <a name="contosos-information-barrier-policies"></a>Criteri di barriera delle informazioni di contoso

Contoso definisce tre criteri di polizia, come descritto nella tabella seguente:

|Criteri  |Definizione criterio  |
|---------|---------|
|Criterio 1: impedire la comunicazione delle vendite con la ricerca     | `New-InformationBarrierPolicy -Name "Sales-Research" -AssignedSegment "Sales" -SegmentsBlocked "Research" -State Inactive` <p> In questo esempio, il criterio barriera informativo è denominato *Sales-Research*. Quando questo criterio è attivo e applicato, consente di impedire agli utenti che si trovano nel segmento Sales di comunicare con gli utenti nel segmento di ricerca. Si tratta di un criterio unidirezionale. non impedirà alla ricerca di comunicare con le vendite. Per questo, è necessario il criterio 2.      |
|Criterio 2: impedire alla ricerca di comunicare con le vendite     | `New-InformationBarrierPolicy -Name "Research-Sales" -AssignedSegment "Research" -SegmentsBlocked "Sales" -State Inactive` <p> In questo esempio, il criterio barriera informativo è denominato *Research-Sales*. Quando questo criterio è attivo e applicato, consente di impedire agli utenti che si trovano nel segmento di ricerca di comunicare con gli utenti nel segmento Sales.       |
|Criterio 3: Consenti alla produzione di comunicare solo con HR e marketing     | `New-InformationBarrierPolicy -Name "Manufacturing-HRMarketing" -AssignedSegment "Manufacturing" -SegmentsAllowed "HR, Marketing" -State Inactive` <p>In questo caso, il criterio barriera informativo è denominato *Manufacturing-HRMarketing*. Quando questo criterio è attivo e applicato, la produzione può comunicare solo con HR e marketing. Si noti che HR e marketing non sono limitati dalla comunicazione con altri segmenti. |

Con i segmenti e i criteri definiti, contoso applica i criteri eseguendo il cmdlet **Start-InformationBarrierPoliciesApplication** . 

Al termine, Contoso è conforme ai requisiti legali e di settore.

## <a name="related-articles"></a>Articoli correlati

[Ottenere una panoramica delle barriere informative](information-barriers.md)

[Per ulteriori informazioni, vedere barriere informative in Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/information-barriers-in-teams)

[Attributi per i criteri di barriera delle informazioni (anteprima)](information-barriers-attributes.md)

[Risoluzione dei problemi relativi alle informazioni sugli ostacoli (anteprima)](information-barriers-troubleshooting.md)
