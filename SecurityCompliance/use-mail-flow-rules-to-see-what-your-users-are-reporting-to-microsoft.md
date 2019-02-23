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
search.appverid:
- MET150
ms.assetid: 8401f520-8e7c-467b-9e06-4a9fdb2ba548
description: È possibile creare una regola di trasporto di Exchange per impedire agli utenti di inviare messaggi di posta elettronica a Microsoft per l'analisi e utilizzarli nei propri processi di sicurezza.
ms.openlocfilehash: 7ee8fb2bca1071ccd4080379485c1670a5e66a73
ms.sourcegitcommit: 06d6e63225f912d0f3c6bb836c61eb11c1dbe97a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/22/2019
ms.locfileid: "30206409"
---
# <a name="use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft"></a>Utilizzare le regole del flusso di posta elettronica per vedere quali utenti inviano segnalazioni a Microsoft

È possibile inviare messaggi falsi positivi e falsi negativi a Microsoft per l'analisi in diversi modi. Come amministratore, è possibile utilizzare le regole del flusso di posta per vedere cosa gli utenti riferiscono a Microsoft come posta indesiderata, non posta indesiderata e truffe di phishing. Per ulteriori informazioni, vedere [inviare messaggi di posta indesiderata, non di posta indesiderata e phishing a Microsoft per l'analisi](submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis.md). Viceversa, è possibile creare una regola di trasporto di Exchange per impedire agli utenti di inviare messaggi di posta elettronica a Microsoft per l'analisi e utilizzarli nei propri processi di sicurezza.
  
## <a name="what-do-you-need-to-know-before-you-begin"></a>Che cosa è necessario sapere prima di iniziare?

Tempo stimato per il completamento: 5 minuti
  
Prima di poter eseguire questa procedura o procedure, è necessario disporre delle autorizzazioni assegnate. Per sapere quali autorizzazioni sono necessarie, vedere la voce "regole di trasporto" nell'argomento [criteri di messaggistica e autorizzazioni di conformità](http://technet.microsoft.com/library/ec4d3b9f-b85a-4cb9-95f5-6fc149c3899b.aspx) e "criteri cassetta postale di Outlook sul Web" nell'argomento Autorizzazioni per [client e dispositivi mobili](http://technet.microsoft.com/library/57eca42a-5a7f-4c65-89f0-7a84f2dbea19.aspx) . 
  
Per informazioni sui tasti di scelta rapida che è possibile utilizzare con le procedure in questo argomento, vedere **Keyboard shortcuts in Exchange 2013**.
  
## <a name="use-the-eac-to-create-a-mail-flow-rule-to-view-users-manual-junk-phishing-and-not-junk-reports"></a>Utilizzare l'interfaccia di amministrazione di Exchange per creare una regola del flusso di posta per visualizzare report manuali dell'utente su posta indesiderata, phishing e posta non indesiderata.

1. Nell'interfaccia di amministrazione di Exchange, accedere a **Flusso di posta** \> **Regole**.
    
2. Fare clic su ![Icona Aggiungi](media/ITPro-EAC-AddIcon.gif) e selezionare **Creare una nuova regola**.
    
3. Assegnare un nome alla regola, quindi fare clic su **Altre opzioni**.
    
4. In **Applica questa regola se**, selezionare **Il destinatario** e scegliere **l'indirizzo include una di queste parole**.
    
5. Nella casella **Specificare parole o frasi**, eseguire le seguenti operazioni: 
    - Digitare `abuse@messaging.microsoft.com` e quindi fare ![clic su](media/ITPro-EAC-AddIcon.gif)icona Aggiungi, quindi `junk@office365.microsoft.com` digitare e quindi ![fare clic](media/ITPro-EAC-AddIcon.gif)su icona Aggiungi. Questi indirizzi di posta elettronica vengono utilizzati per inviare messaggi falsi negativi a Microsoft.
    - Digitare `phish@office365.microsoft.com` e quindi fare ![clic su](media/ITPro-EAC-AddIcon.gif)icona Aggiungi. Questo indirizzo di posta elettronica viene utilizzato per inviare messaggi di phishing mancanti a Microsoft.
    - Digitare `false_positive@messaging.microsoft.com` e quindi fare ![clic su](media/ITPro-EAC-AddIcon.gif)icona Aggiungi, quindi `not_junk@office365.microsoft.com` digitare e quindi ![fare clic](media/ITPro-EAC-AddIcon.gif)su icona Aggiungi. Questi indirizzi di posta elettronica vengono utilizzati per inviare messaggi falsi positivi a Microsoft.
    - Fare clic su **ok**.
    
6. In **Eseguire le operazioni seguenti** selezionare **Invia il messaggio in Ccn a...**, quindi selezionare le cassette postali in cui si desidera ricevere i messaggi. 
    
7. Se lo si desidera, è possibile effettuare le selezioni per controllare la regola, testare la regola, attivare la regola per un periodo di tempo specifico e altre selezioni. È consigliabile testare la regola per un periodo prima di applicarlo. Vedere [procedure per le regole del flusso di posta](https://docs.microsoft.com/Exchange/policy-and-compliance/mail-flow-rules/mail-flow-rule-procedures). 
    
8. Fare clic sul pulsante **salva** per salvare la regola. Viene visualizzata nell'elenco delle regole. 
    
Dopo aver creato e impostato la regola, eventuali messaggi inviati dall'organizzazione agli indirizzi di posta elettronica specificati verranno copiati alla cassetta postale specificata.
  

