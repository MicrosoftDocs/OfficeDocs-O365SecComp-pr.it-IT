---
title: 'Zero-Hour Auto Purge: protezione contro la posta indesiderata e il malware'
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 12/05/2018
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MBS150
- MET150
ms.assetid: 96deb75f-64e8-4c10-b570-84c99c674e15
description: Eliminazione automatica zero ore (ZAP) è una funzionalità di protezione posta elettronica in grado di rilevare i messaggi con la posta indesiderata o malware che sono già stati consegnati alla posta in arrivo degli utenti e quindi viene eseguito il rendering del contenuto dannoso dannosa. Come ZAP esegue questa operazione dipende dal tipo di contenuto dannoso rilevato.
ms.openlocfilehash: 1cf14051e91801a74a0d739c69900bb3f825b318
ms.sourcegitcommit: 204fb0269b5c10b63941055824e863d77e3e9b02
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/06/2018
ms.locfileid: "27180846"
---
# <a name="zero-hour-auto-purge---protection-against-spam-and-malware"></a>Zero-Hour Auto Purge: protezione contro la posta indesiderata e il malware

## <a name="overview"></a>Panoramica

Eliminazione automatica zero ore (ZAP) è una funzionalità di protezione posta elettronica in grado di rilevare i messaggi con per attività di phishing, posta indesiderata o malware che sono già stati consegnati alla posta in arrivo degli utenti e quindi viene eseguito il rendering del contenuto dannoso dannosa. Come ZAP esegue questa operazione dipende dal tipo di contenuto dannoso viene rilevato. posta può essere zapped a causa del contenuto della posta, gli URL o gli allegati.
  
ZAP è disponibile con l'impostazione predefinita, Exchange Online Protection incluso in qualsiasi sottoscrizione a Office 365 che contiene le cassette postali di Exchange Online.

ZAP è attivata per impostazione predefinita, ma devono essere soddisfatte le condizioni seguenti:
  
- **Azione posta indesiderata** è impostata su **spostare il messaggio nella cartella posta indesiderata**. <br/>È inoltre possibile creare un nuovo criterio di filtro posta indesiderata che si applica solo a un insieme di utenti se non si desidera che tutte le cassette postali per essere analizzata da ZAP.

- Gli utenti sono mantenuti valori predefiniti delle impostazioni della posta indesiderata e la protezione della posta elettronica indesiderata non sono disattivata. (Per informazioni dettagliate sulle opzioni utente in Outlook, vedere [modificare il livello di protezione di filtro per la posta indesiderata](https://support.office.com/article/change-the-level-of-protection-in-the-junk-email-filter-e89c12d8-9d61-4320-8c57-d982c8d52f6b) ). 
  
## <a name="how-does-zap-work"></a>Funzionamento ZAP

Aggiornamenti di Office 365 firme malware e motore di protezione da posta indesiderate in tempo reale a intervalli giornalieri. Gli utenti possono comunque dannoso messaggi vengano recapitati posta in arrivo per una serie di motivi, ad esempio se il contenuto è weaponized dopo il recapito agli utenti. ZAP evitare questo problema monitorando continuamente aggiornamenti per le firme di posta indesiderata e malware Office 365. ZAP possono individuare e rimuovere contenuti ai messaggi che sono già nella posta in arrivo degli utenti. 

- Per la posta identificata come posta indesiderata, ZAP Sposta i messaggi non letti nella cartella posta indesiderata degli utenti. 

- Per la posta identificata come posta indesiderata, messaggi ZAP spostati nella cartella posta indesiderata degli utenti, indipendentemente dal fatto che il messaggio di posta elettronica è stato letto.

- Per appena rilevato malware, ZAP rimuove gli allegati di messaggi di posta elettronica, indipendentemente dal fatto che il messaggio di posta elettronica è stato letto. 
  
L'azione ZAP è semplice per l'utente della cassetta postale. essi non ricevere una notifica se un messaggio di posta elettronica viene spostato.
  
Consenti regole degli utenti finali, [regole del flusso di posta elettronica](https://go.microsoft.com/fwlink/p/?LinkId=722755)e gli elenchi o altri filtri hanno la precedenza su ZAP.
  
## <a name="to-review-or-set-up-a-spam-filter-policy"></a>Per verificare o configurare un criterio di filtro posta indesiderata
  
1. Accedere a [https://protection.office.com](https://protection.office.com) e accedere utilizzando l'account di lavoro o della scuola per Office 365.

2. In **gestione rischio**, scegliere la **protezione da posta indesiderata**.

3. Esaminare le impostazioni standard. 

4. Se si desidera personalizzare le impostazioni, fare clic sulla scheda **personalizzato** e attivare **le impostazioni personalizzate**. Modificare le impostazioni e se si desidera, sceglierne **+ Crea un criterio** per aggiungere un nuovo criterio. 
    
## <a name="to-see-if-zap-moved-your-message"></a>Per vedere se ZAP spostato il messaggio

Se si desidera visualizzare se ZAP spostato il messaggio, è possibile utilizzare sia la [relazione sullo stato di protezione di rischio](view-email-security-reports.md#threat-protection-status-report-new) (o [Esplora rischio](use-explorer-in-security-and-compliance.md)).
    
## <a name="to-disable-zap"></a>Per disabilitare ZAP
  
Se si desidera disabilitare ZAP per il tenant di Office 365 o un insieme di utenti, utilizzare il parametro **ZapEnabled** del [Set-HostedContentFilterPolicy](https://go.microsoft.com/fwlink/p/?LinkId=722758), un cmdlet EOP.
    
Nell'esempio seguente, ZAP è disabilitata per un criterio di filtro dei contenuti denominato "Test".
    
```
  Set-HostedContentFilterPolicy -Identity Test -ZapEnabled $false
```

## <a name="faq"></a>Domande frequenti

### <a name="what-happens-if-a-legitimate-message-is-moved-to-the-junk-mail-folder"></a>Cosa succede se un messaggio viene spostato nella cartella posta indesiderata?
  
È consigliabile eseguire il normale processo di creazione di rapporti per falsi positivi. È l'unico motivo il messaggio verrà spostato dalla posta in arrivo nella cartella posta indesiderata in quanto il servizio ha rilevato che il messaggio era posta indesiderata o dannosi.
  
### <a name="what-if-i-use-the-office-365-quarantine-instead-of-the-junk-mail-folder"></a>Se è possibile utilizzare alla quarantena di Office 365 anziché nella cartella posta indesiderata?
  
ZAP non vengono spostati i messaggi in quarantena dalla posta in arrivo in questa fase.
  
### <a name="what-if-i-have-a-custom-mail-flow-rule-block-allow-rule"></a>Se dispone di una regola di flusso di posta personalizzato (bloccare o consentire regola)?
  
Le regole create da admins (regole del flusso di posta elettronica) o Consenti e blocca regole hanno la precedenza. Tali messaggi vengono esclusi dai criteri di funzionalità.
  
## <a name="related-topics"></a>Argomenti correlati

[Protezione dalla posta indesiderata in Office 365](anti-spam-protection.md)
  
[Bloccare la posta indesiderata utilizzando il filtro di Office 365 al fine di evitare problemi di falsi negativi](block-email-spam-to-prevent-false-negatives.md)
  

