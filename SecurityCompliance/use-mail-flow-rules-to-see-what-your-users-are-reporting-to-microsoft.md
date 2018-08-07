---
title: Utilizzare le regole del flusso di posta elettronica per vedere quali utenti inviano segnalazioni a Microsoft
ms.author: krowley
author: kccross
manager: laurawi
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
ms.assetid: 8401f520-8e7c-467b-9e06-4a9fdb2ba548
description: È possibile creare una regola di trasporto di Exchange per impedire agli utenti di inviare messaggi di posta elettronica a Microsoft per l'analisi e utilizzare nei propri processi di protezione
ms.openlocfilehash: 6c6af23e6a5f345e26c7dc09c898f2978ea51a5f
ms.sourcegitcommit: df1e9590a9fa152fa776f16d9b25c180ba7198f3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/07/2018
ms.locfileid: "22122586"
---
# <a name="use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft"></a>Utilizzare le regole del flusso di posta elettronica per vedere quali utenti inviano segnalazioni a Microsoft

Esistono diversi modi, è possibile inviare positivi e falsi messaggi falsi negativi a Microsoft per l'analisi. In qualità di amministratore, è possibile utilizzare le regole del flusso di posta per verificare quali sono segnalazione a Microsoft agli utenti come posta indesiderata e posta non indesiderata tentativi di phishing. Per ulteriori informazioni, vedere [invio della posta indesiderata, posta non indesiderata e i messaggi di phishing phishing a Microsoft per l'analisi](submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis.md). Al contrario, è possibile creare una regola di trasporto di Exchange per impedire agli utenti di inviare messaggi di posta elettronica a Microsoft per l'analisi e utilizzare nei propri processi di protezione.
  
## <a name="what-do-you-need-to-know-before-you-begin"></a>Che cosa è necessario sapere prima di iniziare?

Tempo stimato per il completamento: 5 minuti
  
La voce "Regole di trasporto" di Per eseguire queste procedure, è necessario disporre delle autorizzazioni appropriate. Per sapere quali autorizzazioni sono necessarie, vedere nell'argomento [Messaging policy and compliance permissions](http://technet.microsoft.com/library/ec4d3b9f-b85a-4cb9-95f5-6fc149c3899b.aspx) e "Criteri delle cassette postali di Outlook Web App" nell'argomento [Clients and mobile devices permissions](http://technet.microsoft.com/library/57eca42a-5a7f-4c65-89f0-7a84f2dbea19.aspx). 
  
Per informazioni sui tasti di scelta rapida che è possibile utilizzare con le procedure in questo argomento, vedere **Keyboard shortcuts in Exchange 2013**.
  
## <a name="use-the-eac-to-create-a-mail-flow-rule-to-view-users-manual-junk-phishing-and-not-junk-reports"></a>Utilizzare l'interfaccia di amministrazione di Exchange per creare una regola del flusso di posta per visualizzare report manuali dell'utente su posta indesiderata, phishing e posta non indesiderata.

1. Nell'interfaccia di amministrazione di Exchange, accedere a **Flusso di posta** \> **Regole**.
    
2. Fare clic su ![Icona Aggiungi](media/ITPro-EAC-AddIcon.png) e selezionare **Creare una nuova regola**.
    
3. Assegnare un nome alla regola, quindi fare clic su **Altre opzioni**.
    
4. In **Applica questa regola se**, selezionare **Il destinatario** e scegliere **l'indirizzo include una di queste parole**.
    
5. Nella casella **Specificare parole o frasi**, eseguire le seguenti operazioni: 
    - Tipo `abuse@messaging.microsoft.com` e quindi fare clic su ![Aggiungi icona](media/ITPro-EAC-AddIcon.png), quindi digitare `junk@office365.microsoft.com` e quindi fare clic su ![Aggiungi icona](media/ITPro-EAC-AddIcon.png). Questi indirizzi di posta elettronica vengono utilizzati per inviare messaggi falsi negativi a Microsoft.
    - Tipo `phish@office365.microsoft.com` e quindi fare clic su ![Aggiungi icona](media/ITPro-EAC-AddIcon.png). Questo indirizzo di posta elettronica viene utilizzato per inviare messaggi di phishing senza risposta a Microsoft.
    - Tipo `false_positive@messaging.microsoft.com` e quindi fare clic su ![Aggiungi icona](media/ITPro-EAC-AddIcon.png), quindi digitare `not_junk@office365.microsoft.com` e quindi fare clic su ![Aggiungi icona](media/ITPro-EAC-AddIcon.png). Questi indirizzi di posta elettronica vengono utilizzati per inviare messaggi falsi positivi a Microsoft.
    - Fare clic su **ok**.
    
6. In **Eseguire le operazioni seguenti** selezionare **Invia il messaggio in Ccn a...**, quindi selezionare le cassette postali in cui si desidera ricevere i messaggi. 
    
7. Se si desidera, è possibile effettuare le selezioni per la regola di controllo, testare la regola, abilitare la regola di un periodo di tempo specifico e le altre selezioni. Si consiglia di verificare la regola per un periodo prima di imporre. Vedere [le procedure per le regole del flusso di posta elettronica](https://docs.microsoft.com/Exchange/policy-and-compliance/mail-flow-rules/mail-flow-rule-procedures). 
    
8. Fare clic sul pulsante **salva** per salvare la regola. Viene visualizzata nell'elenco delle regole. 
    
Dopo aver creato e impostato la regola, eventuali messaggi inviati dall'organizzazione agli indirizzi di posta elettronica specificati verranno copiati alla cassetta postale specificata.
  

