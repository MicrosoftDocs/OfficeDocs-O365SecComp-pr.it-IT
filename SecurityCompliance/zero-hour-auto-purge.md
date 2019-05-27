---
title: 'Zero-Hour Auto Purge: protezione contro la posta indesiderata e il malware'
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.date: 04/11/2019
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MBS150
- MET150
ms.assetid: 96deb75f-64e8-4c10-b570-84c99c674e15
ms.collection:
- M365-security-compliance
description: Zero-hour auto Purge (ZAP) è una funzionalità di protezione della posta elettronica che consente di rilevare i messaggi con posta indesiderata o malware che sono già stati recapitati alle cassette postali degli utenti e quindi di eseguire il rendering del contenuto dannoso innocuo. La modalità di utilizzo di ZAP dipende dal tipo di contenuto dannoso rilevato.
ms.openlocfilehash: e6faef4c123ea2db38a27b49ff0ee49b237ec75c
ms.sourcegitcommit: 2b46fba650df8d252b1dd2b3c3f080a383183a06
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/23/2019
ms.locfileid: "34408351"
---
# <a name="zero-hour-auto-purge---protection-against-spam-and-malware"></a>Zero-Hour Auto Purge: protezione contro la posta indesiderata e il malware

## <a name="overview"></a>Panoramica

Zero-hour auto Purge (ZAP) è una funzionalità di protezione della posta elettronica che consente di rilevare messaggi con phishing, posta indesiderata o malware che sono già stati recapitati alle cassette postali degli utenti e quindi viene eseguito il rendering del contenuto dannoso innocuo. La modalità di utilizzo di ZAP dipende dal tipo di contenuto dannoso rilevato. la posta può essere zapped a causa di contenuto, URL o allegati di posta elettronica.
  
ZAP è disponibile con la protezione Exchange Online predefinita inclusa con qualsiasi sottoscrizione di Office 365 che contiene cassette postali di Exchange Online.

L'opzione ZAP è attivata per impostazione predefinita, ma devono essere soddisfatte le condizioni seguenti:
  
- **Azione di posta** indesiderata è impostata per **spostare il messaggio nella cartella posta**indesiderata. È inoltre possibile creare un nuovo criterio di filtro per la posta indesiderata che si applica solo a un gruppo di utenti se non si desidera che tutte le cassette postali vengano schermate da ZAP.

- Gli utenti hanno mantenuto le impostazioni predefinite della posta indesiderata e non sono state disattivate la protezione della posta indesiderata. Per informazioni dettagliate sulle opzioni utente in Outlook, vedere [modificare il livello di protezione del filtro della posta](https://support.office.com/article/change-the-level-of-protection-in-the-junk-email-filter-e89c12d8-9d61-4320-8c57-d982c8d52f6b) indesiderata. 
  
## <a name="how-zap-works"></a>Funzionamento di ZAP

Office 365 aggiorna le firme di malware e del motore di protezione da posta indesiderata in tempo reale su base giornaliera. Tuttavia, gli utenti possono comunque ottenere messaggi dannosi recapitati alle cassette postali per una serie di motivi, incluso se il contenuto è armato dopo essere stato recapitato agli utenti. ZAP risolve questo monitoraggio continuamente gli aggiornamenti alle firme di posta indesiderata e malware di Office 365. ZAP è in grado di trovare e rimuovere i messaggi precedentemente recapitati che sono già presenti nelle cassette postali degli utenti.

- Per la posta elettronica identificata come posta indesiderata, ZAP sposta i messaggi non letti nella cartella posta indesiderata degli utenti.

- Per la posta identificata come phishing, ZAP sposta i messaggi nella cartella posta indesiderata degli utenti, indipendentemente dal fatto che il messaggio di posta elettronica sia stato letto.

- Per il malware appena rilevato, ZAP rimuove gli allegati dai messaggi di posta elettronica, indipendentemente dal fatto che il messaggio di posta elettronica sia stato letto.
  
L'azione ZAP è senza problemi per l'utente della cassetta postale; non vengono notificati se viene spostato un messaggio di posta elettronica. Il messaggio non deve superare i 2 giorni.
  
Gli elenchi Consenti, [le regole del flusso di posta](https://go.microsoft.com/fwlink/p/?LinkId=722755)e le regole degli utenti finali o i filtri aggiuntivi hanno la precedenza su Zap.
  
## <a name="to-review-or-set-up-a-spam-filter-policy"></a>Per rivedere o configurare un criterio di filtro per la posta indesiderata
  
1. Accedere a [https://protection.office.com](https://protection.office.com) e accedere con l'account aziendale o dell'Istituto di istruzione per Office 365.

2. In **gestione minacce**scegliere **protezione da posta**indesiderata.

3. Esaminare le impostazioni standard.

4. Se si desidera personalizzare le impostazioni, selezionare la scheda **personalizzato** e abilitare **le impostazioni personalizzate**. Modificare le impostazioni e, se lo si desidera, fare clic su **+ Crea un criterio** per aggiungere un nuovo criterio.

## <a name="to-see-if-zap-moved-your-message"></a>Per verificare se il messaggio è stato spostato da ZAP

Se si vuole vedere se ZAP ha spostato il messaggio, è possibile utilizzare il [rapporto sullo stato di protezione di minacce](view-email-security-reports.md#threat-protection-status-report) o l' [esploratore di minacce (e i rilevamenti in tempo reale)](threat-explorer.md).

## <a name="to-disable-zap"></a>Per disabilitare ZAP
  
Se si desidera disabilitare ZAP per il tenant di Office 365 o un gruppo di utenti, utilizzare il parametro **ZapEnabled** di [Set-HostedContentFilterPolicy](https://go.microsoft.com/fwlink/p/?LinkId=722758), un cmdlet di EOP.

Nell'esempio seguente, ZAP è disabilitato per un criterio di filtro dei contenuti denominato "test".

```Powershell
  Set-HostedContentFilterPolicy -Identity Test -ZapEnabled $false
```

## <a name="faq"></a>Domande frequenti

### <a name="what-happens-if-a-legitimate-message-is-moved-to-the-junk-mail-folder"></a>Cosa succede se un messaggio legittimo viene spostato nella cartella posta indesiderata?
  
È consigliabile seguire la procedura di creazione di report normale per i [falsi positivi](prevent-email-from-being-marked-as-spam.md). L'unico motivo per il quale il messaggio verrebbe spostato dalla posta in arrivo alla cartella posta indesiderata sarebbe perché il servizio ha determinato che il messaggio era posta indesiderata o dannoso.
  
### <a name="what-if-i-use-the-office-365-quarantine-instead-of-the-junk-mail-folder"></a>Che cosa fare se si utilizza la quarantena di Office 365 anziché la cartella posta indesiderata?
  
ZAP non sposta i messaggi in quarantena dalla posta in arrivo in questo momento.
  
### <a name="what-if-i-have-a-custom-mail-flow-rule-block-allow-rule"></a>Cosa succede se si dispone di una regola del flusso di posta personalizzata (blocco/Consenti regola)?
  
Le regole create dagli amministratori (regole del flusso di posta) o blocca e Consenti hanno la precedenza. Tali messaggi sono esclusi dai criteri di funzionalità in modo che il flusso di posta seguirà l'azione della regola (blocco/Consenti regola).

### <a name="what-if-a-message-is-moved-to-another-folder-eg-inbox-rule"></a>Cosa succede se un messaggio viene spostato in un'altra cartella (ad esempio, la regola di posta in arrivo)?
ZAP continua a funzionare in questo caso, a meno che il messaggio non sia stato eliminato o sia indesiderato.

## <a name="related-topics"></a>Argomenti correlati

[Protezione dalla posta indesiderata in Office 365](anti-spam-protection.md)
  
[Bloccare la posta indesiderata utilizzando il filtro di Office 365 al fine di evitare problemi di falsi negativi](reduce-spam-email.md)
