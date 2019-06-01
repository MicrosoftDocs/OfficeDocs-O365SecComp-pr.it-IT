---
title: Risoluzione dei problemi di barriere informative
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
description: Utilizzare questo articolo come guida per la risoluzione dei problemi relativi alle barriere informative.
ms.openlocfilehash: b37585469ec8bb299b7976f8a330f4c6b29e3f95
ms.sourcegitcommit: 4fedeb06a6e7796096fc6279cfb091c7b89d484d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/31/2019
ms.locfileid: "34668309"
---
# <a name="troubleshooting-information-barriers-preview"></a>Risoluzione dei problemi relativi alle informazioni sugli ostacoli (anteprima)

Gli ostacoli alle informazioni consentono all'organizzazione di rimanere conforme ai requisiti legali e ai regolamenti di settore. Ad esempio, con barriere informative, è possibile limitare le comunicazioni tra gruppi specifici di utenti per evitare conflitti di interesse o altri problemi. Per ulteriori informazioni, vedere [barriere informative (Preview)](information-barriers.md).

In questo articolo vengono fornite indicazioni che è possibile utilizzare per ottenere risposte a domande o risolvere problemi che possono verificarsi con barriere informative.  

## <a name="before-you-begin"></a>Prima di iniziare...

Per eseguire le attività descritte in questo articolo, è necessario essere assegnati a un ruolo appropriato, ad esempio uno dei seguenti:
- Amministratore globale di Microsoft 365 Enterprise
- Amministratore globale di Office 365
- Amministratore di conformità
- IB Compliance Management (questo è un nuovo ruolo)

Per ulteriori informazioni sui ruoli e sulle autorizzazioni, vedere Permissions [in the Office 365 Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).

Per ulteriori informazioni sui prerequisiti per le barriere informative, vedere [prerequisiti (per i criteri barriera informativi)](information-barriers-policies.md#prerequisites).

Assicurarsi inoltre di [connettersi a PowerShell di Office 365 Security & Compliance Center](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps).

## <a name="issue-people-are-unexpectedly-blocked-from-communicating-in-microsoft-teams"></a>Problema: persone inaspettatamente bloccate dalla comunicazione in Microsoft Teams 

In questo caso, gli utenti segnalano problemi imprevisti che comunicano in Microsoft teams. Esempi:
- Un utente non è in grado di trovare o comunicare con un altro utente in Microsoft teams.
- Un utente non può visualizzare o selezionare un altro utente in Microsoft teams.
- Un utente può vedere, ma non è in grado di inviare messaggi a, un altro utente in Microsoft teams.

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

1. Tenere presente che, quando si esegue il cmdlet applicazione criteri, i criteri di barriera delle informazioni vengono applicati (o rimossi), utente per utente, per tutti gli account nell'organizzazione. Se si dispone di numerosi utenti, sarà necessario un po' di tempo per elaborarli. (Come linee guida generali, è necessario circa un'ora per elaborare gli account utente di 5.000). 

2. Utilizzare il cmdlet **Get-InformationBarrierPoliciesApplicationStatus** per verificare lo stato.

    Sintassi`Get-InformationBarrierPoliciesApplicationStatus`

    Per visualizzare lo stato di tutte le applicazioni dei criteri barriera delle informazioni, utilizzare`Get-InformationBarrierPoliciesApplicationStatus -All $true`

    Verranno visualizzate informazioni sul modo in cui l'applicazione del criterio è stata completata, non è riuscita o è in corso.

3. A seconda dei risultati del passaggio 2, eseguire una delle operazioni seguenti:

    - Se l'applicazione non è stata avviata e sono passati più di 45 minuti dal momento in cui è stato eseguito il cmdlet **Start-InformationBarrierPoliciesApplication** , esaminare il log di controllo per verificare se sono presenti errori nelle definizioni dei criteri o per un altro motivo per cui l' l'applicazione non è stata avviata.

    - Se l'applicazione ha avuto esito negativo, esaminare i segmenti e i criteri. Se necessario, [modificare i segmenti](information-barriers-policies.md#edit-a-segment) e/o [modificare i criteri](information-barriers-policies.md#edit-a-policy), quindi eseguire di nuovo il cmdlet **Start-InformationBarrierPoliciesApplication** .

    - Se l'applicazione è ancora in corso, è necessario più tempo per il completamento. Se sono stati diversi giorni, contattare il supporto.

## <a name="related-topics"></a>Argomenti correlati

[Definire i criteri per le barriere informative in Microsoft Teams (anteprima)](information-barriers-policies.md)

[Barriere informative (anteprima)](information-barriers.md)



