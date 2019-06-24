---
title: Risoluzione dei problemi di barriere informative
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 06/21/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.collection:
- M365-security-compliance
localization_priority: None
description: Utilizzare questo articolo come guida per la risoluzione dei problemi relativi alle barriere informative.
ms.openlocfilehash: b88f97cd872d4ea3b95bfac049f47cd71dfb2cb2
ms.sourcegitcommit: c603a07d24c4c764bdcf13f9354b3b4b7a76f656
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/21/2019
ms.locfileid: "35131350"
---
# <a name="troubleshooting-information-barriers-preview"></a>Risoluzione dei problemi relativi alle informazioni sugli ostacoli (anteprima)

[Barriere informative (Preview)](information-barriers.md) può aiutare l'organizzazione a rimanere conforme ai requisiti legali e ai regolamenti di settore. Ad esempio, con barriere informative, è possibile limitare le comunicazioni tra gruppi specifici di utenti per evitare conflitti di interesse o altri problemi. Per ulteriori informazioni su come configurare le barriere informative, vedere [define Policies for Information barriers (Preview)](information-barriers-policies.md).

Nel caso in cui si verifichino problemi imprevisti dopo che sono state apportate barriere alle informazioni, è possibile eseguire alcuni passaggi per risolvere questi problemi. Utilizzare questo articolo come guida.


## <a name="before-you-begin"></a>Prima di iniziare...

Per eseguire le attività descritte in questo articolo, è necessario essere assegnati a un ruolo appropriato, ad esempio uno dei seguenti:
- Amministratore globale di Microsoft 365 Enterprise
- Amministratore globale di Office 365
- Amministratore di conformità
- IB Compliance Management (questo è un nuovo ruolo)

Per ulteriori informazioni sui prerequisiti per le barriere informative, vedere [prerequisiti (per i criteri barriera informativi)](information-barriers-policies.md#prerequisites).

Assicurarsi di eseguire la [connessione a PowerShell di Office 365 Security & Compliance Center](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps).

## <a name="issue-communications-are-still-allowed-between-users-who-should-be-blocked-in-microsoft-teams"></a>Problema: le comunicazioni sono ancora consentite tra gli utenti che devono essere bloccati in Microsoft Teams

In questo caso, anche se le barriere informative sono definite, attive e applicate, le persone che devono essere impossibilitate a comunicare tra loro possono ancora essere in Microsoft teams.

### <a name="what-to-do"></a>cosa fare

Verificare che gli utenti in questione siano inclusi in un criterio barriera informativo. Utilizzare il cmdlet **Get-InformationBarrierRecipientStatus** con i parametri Identity.

Sintassi`Get-InformationBarrierRecipientStatus -Identity <value> -Identity2 <value>` 

È possibile utilizzare qualsiasi valore che identifichi in modo univoco ogni utente, ad esempio nome, alias, nome distinto, nome di dominio canonico, indirizzo di posta elettronica o GUID. 

Esempio:  `Get-InformationBarrierRecipientStatus -Identity meganb -Identity2 alexw` 

In questo esempio, si fa riferimento a due account utente in Office 365: *meganb* per *Megan*e *alexw* per *Alex*. 

È inoltre possibile utilizzare questo cmdlet per un singolo utente: `Get-InformationBarrierRecipientStatus -Identity <value>`) questo cmdlet restituisce informazioni sugli utenti, ad esempio i valori degli attributi e tutti i criteri di barriera delle informazioni applicati.


|Risultati  |Passaggi successivi  |
|---------|---------|
|Nessun segmento è elencato per l'utente o gli utenti selezionati     |Eseguire una delle operazioni seguenti:<br/>-Assegnare gli utenti a un segmento esistente modificando i profili utente in Azure Active Directory<br/>-Definire un segmento utilizzando un [attributo supportato per le barriere](information-barriers-attributes.md) informative         |
|I segmenti sono elencati ma non sono stati assegnati criteri barriera informativi a tali segmenti     |Eseguire una delle operazioni seguenti:<br/>- [Definire un criterio barriera](information-barriers-policies.md#part-2-define-information-barrier-policies) informativo per ogni segmento in questione<br/>- [Modificare un criterio barriera](information-barriers-policies.md#edit-a-policy) informativo e assegnarlo al segmento corretto         |
|I segmenti sono elencati e ognuno di essi è incluso in un criterio barriera informativo     |-Eseguire il `Get-InformationBarrierPolicy` cmdlet per verificare che i criteri di barriera delle informazioni siano attivi<br/>-Eseguire il `Get-InformationBarrierPoliciesApplicationStatus` cmdlet per verificare che i criteri vengano applicati<br/>-Eseguire il `Start-InformationBarrierPoliciesApplication` cmdlet per applicare tutti i criteri di barriera delle informazioni attive          |


## <a name="issue-people-are-unexpectedly-blocked-from-communicating-in-microsoft-teams"></a>Problema: persone inaspettatamente bloccate dalla comunicazione in Microsoft Teams 

In questo caso, gli utenti segnalano problemi imprevisti che comunicano in Microsoft teams. Esempi:
- Un utente non è in grado di trovare o comunicare con un altro utente in Microsoft teams.
- Un utente non può visualizzare o selezionare un altro utente in Microsoft teams.
- Un utente può visualizzare un altro utente, ma non è in grado di selezionare o inviare messaggi a un altro utente in Microsoft teams.

### <a name="what-to-do"></a>cosa fare

1. Determinare se gli utenti sono coinvolti in un criterio barriera informativo. A tale scopo, utilizzare il cmdlet **Get-InformationBarrierRecipientStatus** con il parametro Identity. 

    La sintassi è`Get-InformationBarrierRecipientStatus -Identity`

    È possibile utilizzare qualsiasi valore di identità che identifichi in modo univoco ogni destinatario, ad esempio nome, alias, nome distinto (DN), DN canonico, indirizzo di posta elettronica o GUID.

    Esempio:  `Get-InformationBarrierRecipientStatus -Identity meganb`

    In questo esempio viene utilizzato un alias (*meganb*) per il parametro Identity. Questo cmdlet restituirà informazioni che indicano se l'utente è influenzato da un criterio barriera informativo. (Cercare * ExoPolicyId: \<GUID>.)

    Se gli utenti non sono inclusi nei criteri di barriera delle informazioni, contattare il supporto. In caso contrario, passare al passaggio successivo.

2. Scoprire quali segmenti sono inclusi in un criterio barriera informativo. A tale scopo, utilizzare il `Get-InformationBarrierPolicy` cmdlet con il parametro Identity. Utilizzare i dettagli, ad esempio il GUID dei criteri (ExoPolicyId) ricevuto durante il passaggio precedente, come valore di identità.

    Esempio:  `Get-InformationBarrierPolicy -Identity b42c3d0f-49e9-4506-a0a5-bf2853b5df6f`

    In questo esempio, vengono fornite informazioni dettagliate sul criterio barriera informativo con ExoPolicyId *b42c3d0f-49E9-4506-a0a5-bf2853b5df6f*.
    
    Dopo aver eseguito il cmdlet, nei risultati cercare i valori **AssignedSegment**, **SegmentsAllowed**e **SegmentsBlocked** .

    Esempio: dopo aver eseguito `Get-InformationBarrierPolicy` il cmdlet, è stato riportato quanto segue nell'elenco dei risultati:

    ```powershell
        AssignedSegment      : Sales
        SegmentsAllowed      : {}
        SegmentsBlocked      : {Research}
    ```
    In questo caso, è possibile osservare che un criterio di barriera informativo interessa le persone che si trovano nei segmenti Sales and Research. In questo caso, agli utenti nelle vendite viene impedito di comunicare con gli utenti nella ricerca. Se questo sembra corretto, le barriere informative funzionano come previsto. In caso contrario, procedere al passaggio successivo.

4. Verificare che i segmenti siano definiti correttamente. A tale scopo, utilizzare il `Get-OrganizationSegment` cmdlet ed esaminare l'elenco dei risultati. 

    Per visualizzare i dettagli di un segmento specifico, utilizzare `Get-OrganizationSegment` il cmdlet con un parametro Identity. 

    Esempio:  `Get-OrganizationSegment -Identity c96e0837-c232-4a8a-841e-ef45787d8fcd`

    In questo esempio vengono riportate informazioni sul segmento con GUID *c96e0837-C232-4a8a-841E-ef45787d8fcd*.

    Esaminare i dettagli del segmento. Se necessario, [modificare un segmento](information-barriers-policies.md#edit-a-segment)e quindi riutilizzare il `Start-InformationBarrierPoliciesApplication` cmdlet.

    Se si verificano ancora problemi con il criterio barriera informativo, contattare il supporto.
    
## <a name="issue-the-information-barrier-application-process-is-taking-too-long"></a>Problema: il processo di applicazione barriera alle informazioni richiede troppo tempo

Dopo aver eseguito il cmdlet **Start-InformationBarrierPoliciesApplication** , il processo richiede molto tempo per il completamento.

### <a name="what-to-do"></a>cosa fare

Tenere presente che, quando si esegue il cmdlet applicazione criteri, i criteri di barriera delle informazioni vengono applicati (o rimossi), utente per utente, per tutti gli account nell'organizzazione. Se si dispone di numerosi utenti, sarà necessario un po' di tempo per elaborarli. (Come linee guida generali, è necessario circa un'ora per elaborare gli account utente di 5.000).

1. Utilizzare il cmdlet **Get-InformationBarrierPoliciesApplicationStatus** per verificare lo stato dell'applicazione di criteri più recente.

    Sintassi`Get-InformationBarrierPoliciesApplicationStatus`

    Per visualizzare lo stato di *tutte* le applicazioni dei criteri barriera delle informazioni, utilizzare questo cmdlet:<br/>
    `Get-InformationBarrierPoliciesApplicationStatus -All $true`)

    Verranno visualizzate informazioni sul modo in cui l'applicazione del criterio è stata completata, non è riuscita o è in corso.

2. A seconda dei risultati del passaggio precedente, eseguire una delle operazioni seguenti:
  
    |Stato  |Passaggio successivo  |
    |---------|---------|
    |**Non avviato**     |Se dopo aver eseguito il cmdlet **Start-InformationBarrierPoliciesApplication** sono stati eseguiti più di 45 minuti, esaminare il log di controllo per verificare se sono presenti errori nelle definizioni dei criteri o in qualche altro motivo per cui l'applicazione non è stata avviata. |
    |**Operazione non riuscita**     |Se l'applicazione ha avuto esito negativo, esaminare il log di controllo. Esaminare inoltre i segmenti e i criteri. Gli utenti sono assegnati a più di un segmento? I segmenti sono assegnati a più di un poliicy? Se necessario, [modificare i segmenti](information-barriers-policies.md#edit-a-segment) e/o [modificare i criteri](information-barriers-policies.md#edit-a-policy), quindi eseguire di nuovo il cmdlet **Start-InformationBarrierPoliciesApplication** .  |
    |**In corso**     |Se l'applicazione è ancora in corso, è necessario più tempo per il completamento. Se sono stati diversi giorni, raccogliere i registri di controllo e quindi contattare il supporto tecnico. |

## <a name="related-topics"></a>Argomenti correlati

[Definire i criteri per le barriere informative in Microsoft Teams (anteprima)](information-barriers-policies.md)

[Barriere informative (anteprima)](information-barriers.md)



