---
title: Distribuire il controllo delle app di accesso condizionale per le app di Office 365
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.reviewer: alesibov
ms.audience: Admin
ms.topic: reference
ms.date: 02/14/2019
ms.service: o365-administration
localization_priority: Normal
description: Seguire questa procedura per configurare le app di Azure AD Office 365 in modo che siano controllate da Office 365 cloud app Security Conditional Access App Control.
ms.openlocfilehash: ba3980615815fa45b1385a67560cc635506e2c22
ms.sourcegitcommit: 8679937354c1d8870ecd41519a59d2d7468c23c4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2019
ms.locfileid: "30103291"
---
# <a name="deploy-conditional-access-app-control-for-office-365-apps"></a>Distribuire il controllo delle app di accesso condizionale per le app di Office 365

|Valutazione * *\>**|Planning * *\>**|Distribuzione * *\>**|Utilizzo * * * *|
|:-----|:-----|:-----|:-----|
|[Iniziare a valutare](office-365-cas-overview.md) <br/> |[Avviare la pianificazione](get-ready-for-office-365-cas.md) <br/> |Sei qui!  <br/> [Passaggio successivo](ocas-session-policies.md) <br/> |[Iniziare a utilizzare](utilization-activities-for-ocas.md) <br/> |

Seguire questa procedura per configurare le app di Azure AD Office 365 in modo che siano controllate da Office 365 cloud app Security Conditional Access App Control.

**Passaggio 1: [creare un criterio di test di accesso condizionale di Azure ad](#step-1-create-an-azure-ad-conditional-access-test-policy)**

**Passaggio 2: [accedere con l'ambito di un utente al criterio nelle app](#step-2-sign-in-with-a-user-scoped-to-the-policy-in-the-apps)**

**Passaggio 3: se non è stato selezionato un criterio di protezione delle app cloud incorporato in Azure AD o se si desidera applicare i criteri a un'app non in primo piano, [configurare i controlli avanzati nel portale di cloud app Security](#step-3-configure-advanced-controls-in-the-cloud-app-security-portal)**

**Passaggio 4: [testare la distribuzione](#step-4-test-the-deployment)**

> [!IMPORTANT]
> per distribuire il controllo delle app di accesso condizionale per le app di office 365, è necessaria una [licenza valida per Azure ad Premium P1](https://docs.microsoft.com/azure/active-directory/license-users-groups) e una licenza di sicurezza per l'app Cloud di office 365.

## <a name="step-1-create-an-azure-ad-conditional-access-test-policy"></a>Passaggio 1: creare un criterio di test di accesso condizionale di Azure AD 

1. In Azure Active Directory, in **sicurezza**, fare clic su **accesso condizionale**.

2. Fare clic su **nuovo criterio** e creare un nuovo criterio.

3. Nei criteri di TEST, in **utenti**, assegnare un utente o un utente di test che può essere utilizzato per l'accesso iniziale e la verifica.

4. Nei criteri di TEST, in **app Cloud**, assegnare le app che si desidera controllare con il controllo di accesso condizionale.

5. In **Session**impostare il criterio per l'utilizzo di uno dei criteri predefiniti, **monitorare solo** o bloccare i **download**. Oppure selezionare **Usa criteri** personalizzati per impostare criteri avanzati nel portale cloud app Security.

6. Aggiungere tutte le **assegnazioni di condizioni** applicabili o i **controlli** di concessione (facoltativo).

> ![Accesso condizionale di Azure AD](media/image1.png)

## <a name="step-2-sign-in-with-a-user-scoped-to-the-policy-in-the-apps"></a>Passaggio 2: accedere con l'ambito di un utente al criterio nelle app 

Dopo aver creato il criterio, eseguire l'accesso a ogni applicazione configurata in tale criterio. Assicurarsi di accedere utilizzando un utente configurato nel criterio. Assicurarsi di disconnettersi prima delle sessioni esistenti.

Cloud app Security consentirà di sincronizzare i dettagli dei criteri ai server per ogni nuova applicazione a cui accedi. Questo potrebbe richiedere fino a un minuto.

## <a name="step-3-configure-advanced-controls-in-the-cloud-app-security-portal"></a>Passaggio 3: configurare i controlli avanzati nel cloud app Security Portal 

Le istruzioni sopra riportate consentono di creare un criterio di protezione delle app cloud incorporato per le app in primo piano in Azure AD.

per configurare un criterio avanzato, creare un criterio di [accesso](ocas-access-policies.md) o un [criterio](ocas-session-policies.md) di sessione nel portale di Office 365 Cloud App Security.

### <a name="to-identify-devices-using-client-certificates-this-is-optional"></a>Per identificare i dispositivi che utilizzano i certificati client (facoltativo):

1. Passare al COG impostazioni e scegliere **identificazione dispositivo**.

2. Caricare uno o più certificati radice o intermedi.

3. Dopo aver caricato il certificato, è possibile creare criteri di accesso e criteri di sessione basati sul **tag del dispositivo** e sul **certificato client valido**.

![ID del dispositivo di controllo dell'accesso condizionale](media/image2.png)

> [!NOTE]
> Un certificato viene richiesto solo da un utente se la sessione corrisponde a un criterio che utilizza il filtro certificato client valido.
> 
## <a name="step-4-test-the-deployment"></a>Passaggio 4: testare la distribuzione 

1. Primo disconnettersi da eventuali sessioni esistenti. Provare a eseguire l'accesso a ogni app che è stata distribuita correttamente. Accedere utilizzando un utente che corrisponda ai criteri configurati in Azure AD.

2. Nel portale di sicurezza delle app Cloud, in **indaga**, selezionare **log attività**e verificare che le attività di login vengano acquisite per ogni app.

3. È possibile filtrare facendo clic su **Avanzate**e quindi utilizzando il filtro **origine è uguale a controllo di accesso**.

4. Si consiglia di accedere alle app per dispositivi mobili e desktop da periferiche gestite e non gestite. In questo modo, è necessario verificare che le attività vengano acquisite correttamente nel registro attività. Per verificare la corretta acquisizione dell'attività, fare clic su un'attività di accesso Single Sign-on in modo che apra il cassetto attività. Verificare che il **tag** dell'agente utente indichi correttamente se il dispositivo è un client nativo (ovvero un'app per dispositivi mobili o desktop) oppure se il dispositivo è un dispositivo gestito (conforme, dominio aggiunto o certificato client valido).

> [!NOTE]
> Dopo la distribuzione, non è possibile rimuovere un'app dalla pagina di controllo dell'accesso condizionale. Se non si imposta una sessione o un criterio di accesso sull'app, il controllo delle app di accesso condizionale non modificherà alcun comportamento per l'app.

## <a name="next-steps"></a>Passaggi successivi

- [Informazioni sui criteri di sessione in Office 365 cloud app Security](ocas-session-policies.md)

- [Informazioni sui criteri di accesso in Office 365 cloud app Security](ocas-access-policies.md) 

- [Raggruppare gli indirizzi IP per semplificare la gestione in Office 365 Cloud App Security](group-your-ip-addresses-in-ocas.md)