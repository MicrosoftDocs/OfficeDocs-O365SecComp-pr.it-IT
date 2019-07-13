---
title: Invii di amministratore in Office 365
ms.author: brwilcox
author: briwilcox
manager: dansimp
ms.date: 07/09/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: Informazioni su come inviare messaggi, URL e file potenzialmente dannosi a Microsoft.
ms.openlocfilehash: 2e0bee0dd0a1ccc39d92ea9e175fc7fb10a5b6d3
ms.sourcegitcommit: 73d4cbcf7389935a04d2e451903ef14ebb38e096
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/12/2019
ms.locfileid: "35643907"
---
# <a name="admin-submissions-in-office-365"></a>Invii di amministratore in Office 365

Gli amministratori possono ora inviare messaggi di posta elettronica utilizzando l'ID del messaggio di rete, gli URL e i file per l'analisi da parte di Microsoft in Office 365. La sezione aggiornamenti aggiornati include ancora i messaggi segnalati dall'utente e disponibili per tutti i clienti che utilizzano EOP.

Quando si invia un messaggio di posta elettronica, si ottengono informazioni su tutti i criteri che possono aver consentito la posta elettronica in arrivo nel tenant, nonché l'esame degli URL e degli allegati della posta. I criteri che possono aver consentito a un messaggio di posta elettronica includono l'elenco dei mittenti attendibili di un singolo utente e i criteri di livello tenant, ad esempio le regole di ETR. 


## <a name="how-to-submit-content"></a>Come inviare contenuti

Per inviare contenuto a Microsoft fare clic sul pulsante **nuovo invio** nella parte superiore sinistra della pagina invii. Viene visualizzato un riquadro a comparsa sul lato destro della pagina con l'opzione per inviare un messaggio di posta elettronica, un URL o un file. 

### <a name="email"></a>Posta elettronica
![Esempio di invio tramite posta elettronica](media/submission-flyout-email.PNG)
1. Per inviare un messaggio di posta elettronica, selezionare **posta elettronica** e specificare l' **ID della rete** di posta elettronica o caricare il file di posta elettronica. 

2. Specificare il destinatario o i destinatari a cui si desidera eseguire il controllo dei criteri. Il controllo dei criteri determina se l'analisi del messaggio di posta elettronica è stata ignorata a causa dei criteri a livello di utente o tenant. 

3. Specificare se il messaggio di posta elettronica deve essere stato bloccato o meno. Se il messaggio di posta elettronica deve essere stato bloccato, specificare se deve essere stato bloccato come posta indesiderata, phishing o malware. Se non si è certi di quale tipo potrebbe essere, utilizzare il giudizio migliore.  

* Se il filtro è stato ignorato a causa di criteri al momento dell'invio, verranno visualizzate le informazioni relative a tale criterio.

* Se il filtro non è stato bypassato a causa di uno o più criteri, l'analisi verrà completata in alcuni minuti. Vedrai altre informazioni sull'invio facendo clic sul collegamento di stato. Questo include i risultati del controllo dei criteri e il verdetto di rianalisi. Si noti che non viene eseguito di nuovo il messaggio di posta elettronica tramite lo stack filtro completo ATP di Office 365 ma viene eseguita una nuova analisi parziale in base a determinati attributi di posta, URL o file. 

4. Fare clic sul pulsante **Invia** .

### <a name="url"></a>URL
![Esempio di invio tramite posta elettronica](media/submission-url-flyout.png)
1. Per inviare un URL selezionare **** URL dal riquadro a comparsa. Digitare l'URL completo, incluso il protocollo (**https://**). 

* Se è **stato selezionato deve essere stato filtrato**, specificare se l'URL è phishing o malware.

2. Fare clic sul pulsante **Invia** . 


### <a name="file"></a>File
![Esempio di invio tramite posta elettronica](media/submission-file-flyout.PNG)
1. Per inviare un file seleziona **file** dal riquadro a comparsa e caricare il file che si desidera analizzare. 

2. Fare clic sul pulsante **Invia** .


## <a name="related-topics"></a>Argomenti correlati

[Office 365 Advanced Threat Protection piano 2](office-365-ti.md)
  
[Protezione dalle minacce in Office 365](protect-against-threats.md)
  
[Visualizzare i report per Office 365 Advanced Threat Protection](view-reports-for-atp.md)
  

