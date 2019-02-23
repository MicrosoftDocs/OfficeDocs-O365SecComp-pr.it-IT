---
title: Criteri di accesso in Office 365 Cloud App Security
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.reviewer: alesibov
ms.audience: Admin
ms.topic: reference
ms.date: 02/14/2019
ms.service: O365-seccomp
localization_priority: Normal
description: I criteri di accesso alla sicurezza di Office 365 cloud app consentono il monitoraggio e il controllo in tempo reale sull'accesso alle app cloud basate su utente, posizione, dispositivo e app. È possibile creare criteri di accesso per qualsiasi dispositivo, inclusi i dispositivi che non sono stati aggiunti al dominio e non gestiti da Windows Intune mediante l'implementazione di certificati client su dispositivi gestiti o utilizzando certificati esistenti, ad esempio i certificati MDM di terze parti. Ad esempio, è possibile distribuire i certificati client ai dispositivi gestiti e quindi bloccare l'accesso da dispositivi privi di un certificato.
ms.openlocfilehash: a8651cb51419c93998f2ce6e176fab7c1651b6ea
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/23/2019
ms.locfileid: "30219776"
---
# <a name="access-policies-in-office-365-cloud-app-security"></a>Criteri di accesso in Office 365 Cloud App Security

|Valutazione * *\>**|Planning * *\>**|Distribuzione * *\>**|Utilizzo * * * *|
|:-----|:-----|:-----|:-----|
|[Iniziare a valutare](office-365-cas-overview.md) <br/> |[Avviare la pianificazione](get-ready-for-office-365-cas.md) <br/> |Sei qui!  <br/> [Passaggio successivo](group-your-ip-addresses-in-ocas.md) <br/> |[Iniziare a utilizzare](utilization-activities-for-ocas.md) <br/> |

I criteri di accesso alla sicurezza di Office 365 cloud app consentono il monitoraggio e il controllo in tempo reale sull'accesso alle app cloud basate su utente, posizione, dispositivo e app. È possibile creare criteri di accesso per qualsiasi dispositivo, inclusi i dispositivi che non sono stati aggiunti al dominio e non gestiti da Windows Intune mediante l'implementazione di certificati client su dispositivi gestiti o utilizzando certificati esistenti, ad esempio i certificati MDM di terze parti. Ad esempio, è possibile distribuire i certificati client ai dispositivi gestiti e quindi bloccare l'accesso da dispositivi privi di un certificato.

Invece di consentire o bloccare completamente l'accesso, con i [criteri](ocas-session-policies.md) di sessione è possibile consentire l'accesso durante il monitoraggio della sessione e/o limitare le attività specifiche della sessione.

## <a name="prerequisites-to-using-access-policies"></a>Prerequisiti per l'utilizzo dei criteri di accesso

- Licenza P1 di Azure AD Premium

- Le app rilevanti devono essere [distribuite con il controllo delle app di accesso condizionale](https://docs.microsoft.com/en-us/cloud-app-security/proxy-deployment-aad)

- un [criterio](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal) di accesso condizionale di Azure ad dovrebbe essere sul posto che reindirizza gli utenti a Office 365 Cloud App Security, come descritto di seguito.

## <a name="create-an-azure-ad-conditional-access-policy"></a>Creare un criterio di accesso condizionale di Azure AD

I criteri di accesso condizionale di Azure Active Directory e i criteri di sessione di sicurezza cloud app funzionano in tandem per esaminare ogni sessione utente e prendere decisioni sui criteri per ogni app. Per impostare un criterio di accesso condizionale in Azure Active Directory, eseguire la procedura seguente:

1. Configurare un [criterio](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal) di accesso condizionale di Azure ad con le assegnazioni per l'utente o il gruppo di utenti e l'app che si desidera controllare con il controllo dell'applicazione di accesso condizionale.<br>Nota: sono interessati da questo criterio solo [le app distribuite con il controllo](https://docs.microsoft.com/cloud-app-security/proxy-deployment-aad) delle app con accesso condizionale.

2. instradare gli utenti a Office 365 Cloud app Security selezionando la casella di **controllo usa accesso condizionale** per le restrizioni applicate in **Session**.

## <a name="create-a-cloud-app-security-access-policy"></a>Creare un criterio di accesso alla sicurezza delle app Cloud

Per creare un nuovo criterio di accesso, eseguire la procedura seguente:

1. Nel portale selezionare **controllo** seguito dai **criteri**.

2. Nella pagina **criteri** fare clic su **Crea criterio** e selezionare **criteri di accesso**.

3. Nella finestra **criteri** di accesso assegnare un nome per il criterio, ad esempio *blocca l'accesso da dispositivi non gestiti*.

4. Nelle **attività corrispondenti a tutta la sezione seguente** , in **origine attività**, selezionare filtri attività aggiuntivi da applicare al criterio. I filtri includono le opzioni seguenti:
    
    - **Tag del dispositivo**: utilizzare questo filtro per identificare i dispositivi non gestiti.
    
    - **Posizione**: utilizzare questo filtro per identificare le posizioni sconosciute (e quindi rischiose).
    
    - **Indirizzo IP**: utilizzare questo filtro per filtrare gli indirizzi IP o utilizzare i tag degli indirizzi IP assegnati in precedenza.
    
    - **Tag dell'agente utente**: utilizzare questo filtro per abilitare l'euristica per identificare le app per dispositivi mobili e desktop. Questo filtro può essere impostato su uguale o diverso. I valori devono essere testati con le app per dispositivi mobili e desktop per ogni app cloud.

5. In **azioni**, selezionare una delle seguenti opzioni:
    
    - **Consenti**: impostare questa azione per consentire in modo esplicito l'accesso in base ai filtri di criteri impostati.
    
    - **Blocca**: impostare questa azione per bloccare in modo esplicito l'accesso in base ai filtri di criteri impostati.

6. È possibile **creare un avviso per ogni evento corrispondente con la gravità del criterio**e impostare un limite di avviso e selezionare se si desidera che l'avviso venga inviato come un messaggio di posta elettronica, un SMS o entrambi.

## <a name="next-steps"></a>Passaggi successivi

- [Raggruppare gli indirizzi IP per semplificare la gestione in Office 365 Cloud App Security](group-your-ip-addresses-in-ocas.md)