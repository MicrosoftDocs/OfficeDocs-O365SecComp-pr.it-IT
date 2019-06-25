---
title: Definire i criteri di barriera delle informazioni
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 06/24/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.collection:
- M365-security-compliance
localization_priority: None
description: Informazioni su come definire i criteri per le barriere informative in Microsoft teams.
ms.openlocfilehash: f6a570675130410acc702ef9f8ca99bf87b7501b
ms.sourcegitcommit: 7c48ce016fa9f45a3813467f7c5a2fd72f9b8f49
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/25/2019
ms.locfileid: "35203735"
---
# <a name="define-policies-for-information-barriers-preview"></a>Definire i criteri per le barriere informative (anteprima)

## <a name="overview"></a>Panoramica

Con barriere informative, è possibile definire criteri che sono stati creati per impedire a determinati segmenti di utenti di comunicare tra loro oppure consentire a segmenti specifici di comunicare solo con determinati altri segmenti. I criteri barriera alle informazioni consentono all'organizzazione di mantenere la conformità agli standard e ai regolamenti del settore e di evitare potenziali conflitti di interesse. Per ulteriori informazioni, vedere [barriere informative (Preview)](information-barriers.md). 

In questo articolo viene descritto come pianificare, definire, implementare e gestire i criteri di barriera delle informazioni. Sono coinvolti diversi passaggi e il flusso di lavoro è suddiviso in più parti. Assicurarsi di leggere i [prerequisiti](#prerequisites) e l'intero processo prima di iniziare a definire (o modificare) i criteri di barriera delle informazioni.

> [!TIP]
> In questo articolo è incluso uno [scenario di esempio](#example-contosos-departments-segments-and-policies) e una cartella di [lavoro di Excel scaricabile](https://github.com/MicrosoftDocs/OfficeDocs-O365SecComp/raw/public/SecurityCompliance/media/InfoBarriers-PowerShellGenerator.xlsx) che consente di pianificare e definire i criteri di barriera delle informazioni.

## <a name="the-work-flow-at-a-glance"></a>Il flusso di lavoro in un colpo d'occhio

|Fase    |Elementi coinvolti  |
|---------|---------|
|[Verificare che i prerequisiti siano soddisfatti](#prerequisites)     |-Verificare di disporre delle [licenze e delle autorizzazioni necessarie](information-barriers.md#required-licenses-and-permissions)<br/>-Verificare che la directory includa dati per segmentare gli utenti<br/>-Abilitare la ricerca di directory con ambito per Microsoft Teams<br/>-Verificare che la registrazione di controllo sia attivata<br/>-Utilizzare PowerShell (vengono forniti esempi)<br/>-Fornire il consenso dell'amministratore per Microsoft Teams (sono inclusi i passaggi)          |
|[Parte 1: segmentare gli utenti nell'organizzazione](#part-1-segment-users)     |-Determinare quali criteri sono necessari<br/>-Creare un elenco di segmenti da definire<br/>-Identificare gli attributi da utilizzare<br/>-Definire i segmenti in termini di filtri per i criteri        |
|[Parte 2: definire i criteri di barriera delle informazioni](#part-2-define-information-barrier-policies)     |-Definire i criteri (non è ancora applicabile)<br/>-Scegliere tra due tipi (blocca o Consenti) |
|[Parte 3: applicare i criteri di barriera delle informazioni](#part-3-apply-information-barrier-policies)     |-Impostare i criteri per lo stato attivo<br/>-Eseguire l'applicazione per i criteri<br/>-Visualizzare lo stato dei criteri         |
|(Se necessario) [Modificare un segmento o un criterio](information-barriers-edit-segments-policies.md.md)    |-Modificare un segmento<br/>-Modificare o rimuovere un criterio<br/>-Rieseguire l'applicazione del criterio<br/>-Visualizzare lo stato dei criteri         |
|(Se necessario) [Risoluzione dei problemi](information-barriers-troubleshooting.md)|-Intervenire quando le cose non funzionano come previsto|

## <a name="prerequisites"></a>Prerequisiti

Oltre alle [licenze e le autorizzazioni necessarie](information-barriers.md#required-licenses-and-permissions), verificare che siano soddisfatti i requisiti seguenti: 
     
- **Dati della directory**. Verificare che la struttura dell'organizzazione sia riflessa nei dati della directory. Per eseguire questa operazione, verificare che gli attributi degli account utente, ad esempio appartenenza a gruppo, nome reparto e così via, siano inseriti correttamente in Azure Active Directory (o Exchange Online). Per ulteriori informazioni, vedere le risorse seguenti:
  - [Attributi per i criteri di barriera delle informazioni (anteprima)](information-barriers-attributes.md)
  - [Aggiungere o aggiornare le informazioni del profilo di un utente tramite Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal)
  - [Configurare le proprietà degli account utente con Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/configure-user-account-properties-with-office-365-powershell)

- **Ricerca nell'ambito della directory**. Prima di definire il primo criterio barriera informativo dell'organizzazione, è necessario [abilitare la ricerca nell'ambito della directory in Microsoft teams](https://docs.microsoft.com/MicrosoftTeams/teams-scoped-directory-search). Attendere almeno 24 ore dopo aver abilitato la ricerca nell'ambito della directory prima di impostare o definire i criteri di barriera delle informazioni.

- **Registrazione di controllo**. Per cercare lo stato di un'applicazione di criteri, è necessario che la registrazione di controllo sia attivata. Si consiglia di eseguire questa operazione prima di iniziare a definire segmenti o criteri. Per ulteriori informazioni, vedere [attivazione o disattivazione della ricerca del registro di controllo di Office 365](turn-audit-log-search-on-or-off.md).

- **PowerShell**. Attualmente, i criteri barriera informativi vengono definiti e gestiti nel centro conformità & sicurezza di Office 365 tramite i cmdlet di PowerShell. Anche se alcuni esempi sono disponibili in questo articolo, è necessario avere familiarità con i cmdlet e i parametri di PowerShell. [Connettersi a PowerShell di Office 365 Security & Compliance Center](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps).

- **Consenso dell'amministratore per le barriere informative in Microsoft teams**. Quando i criteri sono sul posto, gli ostacoli alle informazioni possono rimuovere persone dalle sessioni di chat di cui non si suppone che si trovino. Questo contribuisce a garantire che l'organizzazione rimanga conforme ai criteri e alle normative. Utilizzare la procedura seguente per consentire ai criteri di barriera delle informazioni di funzionare come previsto in Microsoft teams. 

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

Quando vengono soddisfatti tutti i prerequisiti, passare alla sezione successiva.

> [!TIP]
> Per preparare il piano, è incluso uno scenario di esempio in questo articolo. [Vedere Departments, Segments, and policies di Contoso](#example-contosos-departments-segments-and-policies).<p>Inoltre, è disponibile una cartella di lavoro di Excel scaricabile che consente di pianificare e definire i segmenti e i criteri (e creare i cmdlet di PowerShell). [Ottenere la cartella di lavoro](https://github.com/MicrosoftDocs/OfficeDocs-O365SecComp/raw/public/SecurityCompliance/media/InfoBarriers-PowerShellGenerator.xlsx). 

## <a name="part-1-segment-users"></a>Parte 1: segmentare gli utenti

Durante questa fase, è possibile determinare quali criteri di barriera informativi sono necessari, creare un elenco di segmenti da definire e quindi definire i segmenti.

### <a name="determine-what-policies-are-needed"></a>Determinare quali criteri sono necessari

Considerando le normative legali e industriali, quali sono i gruppi all'interno dell'organizzazione che avranno bisogno di criteri barriera informativi? Creare un elenco. Esistono gruppi a cui è necessario impedire la comunicazione con un altro gruppo? Esistono gruppi che devono essere autorizzati a comunicare solo con uno o due altri gruppi? Si pensi ai criteri necessari come appartenenti a uno dei due gruppi:
- I criteri "blocca" impediscono a un gruppo di comunicare con un altro gruppo.
- I criteri "Consenti" consentono a un gruppo di comunicare con solo alcuni gruppi specifici.

Quando si ha un elenco iniziale di gruppi e criteri, procedere all'identificazione dei segmenti necessari. 

### <a name="identify-segments"></a>Identificare i segmenti

Oltre all'elenco iniziale dei criteri, creare un elenco di segmenti per l'organizzazione. Gli utenti che saranno inclusi nei criteri di barriera delle informazioni devono appartenere a un segmento e nessun utente deve appartenere a due o più segmenti. Ogni segmento può disporre di un solo criterio barriera informativo applicato. 

Determinare gli attributi dei dati di directory dell'organizzazione che verranno utilizzati per definire i segmenti. È possibile utilizzare *Department*, *member*o uno qualsiasi degli attributi supportati. Assicurarsi di avere valori nell'attributo selezionato per gli utenti. [Vedere l'elenco degli attributi supportati per le barriere informative (Preview)](information-barriers-attributes.md).

> [!IMPORTANT]
> **Prima di procedere alla sezione successiva, verificare che i dati della directory dispongano di valori per gli attributi che è possibile utilizzare per definire i segmenti**. Se i dati della directory non contengono valori per gli attributi che si desidera utilizzare, gli account utente devono essere aggiornati per includere tali informazioni prima di procedere con le barriere informative. Per ottenere assistenza, vedere le risorse seguenti:<br/>- [Configurare le proprietà degli account utente con Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/configure-user-account-properties-with-office-365-powershell)<br/>- [Aggiungere o aggiornare le informazioni del profilo di un utente tramite Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal)

### <a name="define-segments-using-powershell"></a>Definire segmenti tramite PowerShell

> [!IMPORTANT]
> Verificare **che i segmenti non si sovrappongano**. Ogni utente che sarà influenzato dalle barriere informative dovrebbe appartenere a un solo segmento. Nessun utente deve appartenere a due o più segmenti. Vedere l' [esempio: segmenti definiti da Contoso](#contosos-defined-segments) in questo articolo.

La definizione di segmenti non ha effetto sugli utenti. imposta solo la fase per i criteri di barriera delle informazioni da definire e quindi applicare.

1. Utilizzare il cmdlet **New-OrganizationSegment** con il parametro **UserGroupFilter** che corrisponde all' [attributo](information-barriers-attributes.md) che si desidera utilizzare.
    
    Sintassi`New-OrganizationSegment -Name "segmentname" -UserGroupFilter "attribute -eq 'attributevalue'"`
    
    Esempio:  `New-OrganizationSegment -Name "HR" -UserGroupFilter "Department -eq 'HR'"`
    
    In questo esempio, un segmento denominato *HR* è definito utilizzando *HR*, un valore nell'attributo *Department* . La parte **-EQ** del cmdlet si riferisce a "uguale a". (In alternativa, è possibile utilizzare **-ne** per indicare "non uguale a". Vedere [utilizzo di "Equals" e "not equals" nelle definizioni di segmento](#using-equals-and-not-equals-in-segment-definitions).

    Dopo aver eseguito ogni cmdlet, verrà visualizzato un elenco di dettagli sul nuovo segmento. I dettagli includono il tipo di segmento, che ha creato o modificato l'ultima volta e così via. 

2. Ripetere questa procedura per ogni segmento che si desidera definire.

Dopo aver definito i segmenti, procedere alla [definizione dei criteri barriera](#part-2-define-information-barrier-policies)informativi.

### <a name="using-equals-and-not-equals-in-segment-definitions"></a>Utilizzo di "Equals" e "not equals" nelle definizioni di segmento

Nell'esempio seguente viene definito un segmento in modo che "Department sia uguale a HR". 

**Esempio**:`New-OrganizationSegment -Name "HR" -UserGroupFilter "Department -eq 'HR'"`

Si noti che la definizione del segmento include un parametro "Equals" indicato come **-EQ**. 

È inoltre possibile definire segmenti utilizzando un parametro "not equals", indicato come **-ne**, come illustrato nell'esempio seguente:

**Sintassi**:`New-OrganizationSegment -Name "segmentname" -UserGroupFilter "attribute -ne 'attributevalue'"`

**Esempio**:`New-OrganizationSegment -Name "NotSales" -UserGroupFilter "Department -ne 'Sales'"`

In questo esempio, è stato definito un segmento denominato *NotSales* che include tutti coloro che non sono nelle *vendite*. La parte **-ne** del cmdlet si riferisce a "non uguale a".

Oltre alla definizione di segmenti che utilizzano "Equals" o "not equals", è possibile definire un segmento utilizzando i parametri "Equals" e "not equals".

**Esempio**:`New-OrganizationSegment -Name "LocalFTE" -UserGroupFilter "Location -eq 'Local'" and "Position -ne 'Temporary'"`

In questo esempio, è stato definito un segmento denominato *LocalFTE* che include persone che sono situate localmente e le cui posizioni non sono elencate come *temporanee*.

## <a name="part-2-define-information-barrier-policies"></a>Parte 2: definire i criteri di barriera delle informazioni

Determinare se è necessario impedire la comunicazione tra determinati segmenti o limitare le comunicazioni a determinati segmenti. In teoria, è possibile utilizzare il numero minimo di criteri per garantire che l'organizzazione sia conforme ai requisiti legali e di settore.

Con l'elenco dei segmenti di utenti e dei criteri barriera informativi che si desidera definire, selezionare uno scenario e quindi eseguire la procedura seguente. 

- [Scenario 1: bloccare le comunicazioni tra segmenti](#scenario-1-block-communications-between-segments)
- [Scenario 2: consentire a un segmento di comunicare solo con un altro segmento](#scenario-2-allow-a-segment-to-communicate-only-with-one-other-segment)

> [!IMPORTANT]
> Assicurarsi **che durante la definizione dei criteri non venga assegnato più di un criterio a un segmento**. Ad esempio, se si definisce un criterio per un segmento denominato *Sales*, non definire un criterio aggiuntivo per le *vendite*.<p>Inoltre, quando si definiscono i criteri di barriera delle informazioni, assicurarsi di impostare tali criteri sullo stato inattivo fino a quando non si è pronti per applicarli. La definizione o la modifica dei criteri non influiscono sugli utenti finché tali criteri non sono impostati sullo stato attivo e quindi applicati.

Vedere l' [esempio: criteri di protezione delle informazioni di Contoso](#contosos-information-barrier-policies) in questo articolo.

### <a name="scenario-1-block-communications-between-segments"></a>Scenario 1: bloccare le comunicazioni tra segmenti

Se si desidera bloccare i segmenti dalla comunicazione tra loro, è possibile definire due criteri: uno per ogni direzione. Ogni criterio blocca la comunicazione solo in un modo.

Ad esempio, si supponga di voler bloccare le comunicazioni tra il segmento A e il segmento B. In questo caso, è possibile definire un criterio che impedisca al segmento A di comunicare con il segmento B e quindi definire un secondo criterio per impedire che il segmento B comunichi con il segmento A.

1. Per definire il primo criterio di blocco, utilizzare il cmdlet **New-InformationBarrierPolicy** con il parametro **SegmentsBlocked** . 

    Sintassi`New-InformationBarrierPolicy -Name "policyname" -AssignedSegment "segment1name" -SegmentsBlocked "segment2name"`

    Esempio:  `New-InformationBarrierPolicy -Name "Sales-Research" -AssignedSegment "Sales" -SegmentsBlocked "Research" -State Inactive`

    In questo esempio, è stato definito un criterio denominato *Sales-Research* per un segmento denominato *Sales*. Se attivo e applicato, questo criterio impedisce alle persone in *vendita* di comunicare con gli utenti di un segmento denominato *Research*.

2. Per definire il secondo segmento di blocco, utilizzare di nuovo il cmdlet **New-InformationBarrierPolicy** con il parametro **SegmentsBlocked** , stavolta con i segmenti invertiti.

    Esempio:  `New-InformationBarrierPolicy -Name "Research-Sales" -AssignedSegment "Research" -SegmentsBlocked "Sales" -State Inactive`

    In questo esempio, è stato definito un criterio denominato *Research-Sales* per impedire che la *ricerca* comunichi con le *vendite*.
 
2. Procedere con una delle operazioni seguenti:

   - (Se necessario) [Definire un criterio per consentire a un segmento di comunicare solo con un altro segmento](#scenario-2-allow-a-segment-to-communicate-only-with-one-other-segment) 
   - (Dopo che sono stati definiti tutti i criteri) [Applicare i criteri di barriera delle informazioni](#part-3-apply-information-barrier-policies)

### <a name="scenario-2-allow-a-segment-to-communicate-only-with-one-other-segment"></a>Scenario 2: consentire a un segmento di comunicare solo con un altro segmento

1. Per consentire a un segmento di comunicare solo con un altro segmento, utilizzare il cmdlet **New-InformationBarrierPolicy** con il parametro **SegmentsAllowed** . 

    Sintassi`New-InformationBarrierPolicy -Name "policyname" -AssignedSegment "segment1name" -SegmentsAllowed "segment2name"`

    Esempio:  `New-InformationBarrierPolicy -Name "Manufacturing-HR" -AssignedSegment "Manufacturing" -SegmentsAllowed "HR" -State Inactive`

    In questo esempio, è stato definito un criterio denominato *Manufacturing-HR* per un segmento denominato *Manufacturing*. Se attivo e applicato, questo criterio consente alle persone nella *produzione* di comunicare solo con le persone in un segmento denominato *HR*. In questo caso, la *produzione* non è in grado di comunicare con gli utenti che non fanno parte di *HR*.

    **Se necessario, è possibile specificare più segmenti con questo cmdlet, come illustrato nell'esempio seguente.**

    Sintassi`New-InformationBarrierPolicy -Name "policyname" -AssignedSegment "segment1name" -SegmentsAllowed "segment2name", "segment3name"`

    **Esempio 2: definire un criterio per consentire a un segmento di comunicare con solo altri due segmenti**    

    `New-InformationBarrierPolicy -Name "Research-HRManufacturing" -AssignedSegment "Research" -SegmentsAllowed "HR","Manufacturing" -State Inactive`

    In questo esempio, è stato definito un criterio che consente al segmento di *ricerca* di comunicare solo con le *risorse umane* e la *produzione*.

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

## <a name="view-status-of-user-accounts-segments-policies-or-policy-application"></a>Visualizzazione dello stato degli account utente, segmenti, criteri o applicazione di criteri

Con PowerShell, è possibile visualizzare lo stato degli account utente, i segmenti, i criteri e l'applicazione di criteri, come indicato nella tabella seguente.

|Per visualizzare questo  |Esegui questa operazione  |
|---------|---------|
|Account utente     |Utilizzare il cmdlet **Get-InformationBarrierRecipientStatus** con i parametri Identity. <p>Sintassi`Get-InformationBarrierRecipientStatus -Identity <value> -Identity2 <value>` <p>È possibile utilizzare qualsiasi valore che identifichi in modo univoco ogni utente, ad esempio nome, alias, nome distinto, nome di dominio canonico, indirizzo di posta elettronica o GUID. <p>Esempio:  `Get-InformationBarrierRecipientStatus -Identity meganb -Identity2 alexw` <p>In questo esempio, si fa riferimento a due account utente in Office 365: *meganb* per *Megan*e *alexw* per *Alex*. <p>È inoltre possibile utilizzare questo cmdlet per un singolo utente: `Get-InformationBarrierRecipientStatus -Identity <value>` <p>Questo cmdlet restituisce informazioni sugli utenti, ad esempio i valori degli attributi e tutti i criteri di barriera delle informazioni applicati.|
|Segmenti     |Utilizzare il cmdlet **Get-OrganizationSegment** .<p>Sintassi`Get-OrganizationSegment` <p>In questo modo verrà visualizzato un elenco di tutti i segmenti definiti per l'organizzazione.         |
|Criteri barriera di informazioni     |Utilizzare il cmdlet **Get-InformationBarrierPolicy** . <p> Sintassi`Get-InformationBarrierPolicy` <p>In questo modo verrà visualizzato un elenco di criteri barriera informativi definiti e il relativo stato.       |
|Applicazione dei criteri barriera informativa più recente     | Utilizzare il cmdlet **Get-InformationBarrierPoliciesApplicationStatus** . <p>Sintassi`Get-InformationBarrierPoliciesApplicationStatus`<p>    Verranno visualizzate informazioni sul modo in cui l'applicazione del criterio è stata completata, non è riuscita o è in corso.       |
|Tutte le applicazioni dei criteri barriera di informazioni|Utilizzare`Get-InformationBarrierPoliciesApplicationStatus -All $true`<p>Verranno visualizzate informazioni sul modo in cui l'applicazione del criterio è stata completata, non è riuscita o è in corso.|


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
|Criterio 3: Consenti alla produzione di comunicare solo con HR e marketing     | `New-InformationBarrierPolicy -Name "Manufacturing-HRMarketing" -AssignedSegment "Manufacturing" -SegmentsAllowed "HR","Marketing" -State Inactive` <p>In questo caso, il criterio barriera informativo è denominato *Manufacturing-HRMarketing*. Quando questo criterio è attivo e applicato, la produzione può comunicare solo con HR e marketing. Si noti che HR e marketing non sono limitati dalla comunicazione con altri segmenti. |

Con i segmenti e i criteri definiti, contoso applica i criteri eseguendo il cmdlet **Start-InformationBarrierPoliciesApplication** . 

Al termine, Contoso è conforme ai requisiti legali e di settore.

## <a name="related-articles"></a>Articoli correlati

[Modificare o rimuovere i criteri di barriera delle informazioni (anteprima)](information-barriers-edit-segments-policies.md.md)

[Ottenere una panoramica delle barriere informative](information-barriers.md)

[Per ulteriori informazioni, vedere barriere informative in Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/information-barriers-in-teams)

[Attributi per i criteri di barriera delle informazioni (anteprima)](information-barriers-attributes.md)

[Risoluzione dei problemi relativi alle informazioni sugli ostacoli (anteprima)](information-barriers-troubleshooting.md)
