---
title: Bloccare la posta indesiderata nella versione autonoma di Exchange Online Protection
ms.author: tracyp
author: msfttracyp
ms.reviewer: andypunt
manager: laurawi
ms.date: 2/25/2019
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MOE150
- MET150
ms.assetid: da21c0b6-e8f0-4cc8-af2e-5029a9433d59
ms.collection:
- M365-security-compliance
description: Documento destinato agli amministratori della versione autonoma di Exchange Online Protection che contiene informazioni per evitare falsi negativi della posta indesiderata
ms.openlocfilehash: c9b17704c514fd83f8c00a51fad76cddb26e378c
ms.sourcegitcommit: baf23be44f1ed5abbf84f140b5ffa64fce605478
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/26/2019
ms.locfileid: "30306545"
---
## <a name="customize-the-office-365-anti-spam-filter-with-these-settings"></a>Personalizzare il filtro della posta indesiderata di Office 365 con queste impostazioni

Un amministratore può utilizzare diverse impostazioni del filtro protezione da posta indesiderata di Office 365 per impedire l'invio della posta indesiderata alla posta in arrivo di un utente. Il filtro protezione da posta indesiderata di Office 365 imparerà a bloccare la posta indesiderata e a evitare messaggi falsi negativi se si usano le opzioni elencate qui. In questo contesto, un falso negativo si riferisce a un messaggio di posta indesiderata inviato alla posta in arrivo di un utente.
  
### <a name="block-ip-addresses-with-a-connection-filter"></a>Bloccare gli indirizzi IP con un filtro connessioni

È possibile personalizzare il filtro protezione da posta indesiderata di Office 365 aggiungendo l'indirizzo IP del mittente all'elenco indirizzi IP bloccati del filtro connessioni:
  
1. Ottenere le intestazioni del messaggio da bloccare nel client di posta come Outlook o Outlook sul web (noto in precedenza come Outlook Web App), come descritto in [Analizzatore intestazione messaggio](https://go.microsoft.com/fwlink/p/?LinkId=306583).
    
2. Cercare l'indirizzo IP dopo il tag CIP nell'intestazione X-Forefront-Antispam-Report tramite l'[analizzatore intestazione messaggio](https://testconnectivity.microsoft.com/?tabid=mha) o manualmente. 
    
3. Aggiungere l'indirizzo IP all'elenco indirizzi IP bloccati seguendo la procedura in "Utilizzare EAC per modificare il criterio del filtro connessioni predefinito" in [Configurare il criterio del filtro connessioni](https://technet.microsoft.com/it-IT/library/jj200718%28v=exchg.150%29.aspx).
    
### <a name="block-bulk-mail-with-transport-rules-or-the-spam-filter"></a>Bloccare i messaggi in blocco con regole di trasporto o con il filtro protezione da posta indesiderata

La posta indesiderata è per lo più composta da posta inviata in massa, come ad esempio, newsletter o promozioni? È possibile personalizzare il filtro protezione da posta indesiderata in Office 365 se si [usano regole di trasporto per filtrare in modo aggressivo i messaggi di posta elettronica inviati in massa](https://technet.microsoft.com/it-IT/library/dn720438%28v=exchg.150%29.aspx) o attivare l'impostazione **Invio di posta in blocco** nelle [Opzioni ASF](https://technet.microsoft.com/it-IT/library/jj200750%28v=exchg.150%29.aspx) del filtro protezione da posta indesiderata. Nell'interfaccia di amministrazione di Exchange, iniziare facendo clic su **Protezione** \> **Filtro contenuto**, quindi fare doppio clic sul criterio del filtro da modificare. Fare clic su **Azioni posta inviata in massa e indesiderata** per modificare le impostazioni, come mostrato qui. 
  
![Impostazione del filtro di posta inviata in blocco in Exchange Online](media/a45095c2-269d-45b8-a76c-999b5e78da68.png)
  
### <a name="block-email-spam-using-spam-filter-block-lists"></a>Bloccare la posta indesiderata tramite gli elenchi elementi bloccati del filtro protezione da posta indesiderata

[Configurare i criteri del filtro protezione da posta indesiderata](https://technet.microsoft.com/it-IT/library/jj200684%28v=exchg.150%29.aspx) per aggiungere l'indirizzo del mittente all'elenco di mittenti bloccati o il dominio all'elenco di domini bloccati nel filtro protezione da posta indesiderata. I messaggi di posta elettronica di un mittente o dominio in un elenco elementi bloccati del filtro protezione da posta indesiderata verranno contrassegnati come posta indesiderata. 
  
## <a name="email-users-can-also-help-ensure-that-false-negative-and-email-spam-is-blocked-with-office-365-spam-filter"></a>Gli utenti della posta elettronica possono contribuire anche a garantire il blocco dei messaggi indesiderati e dei falsi negativi usando il filtro della posta indesiderata di Office 365

Può risultare utile per le iniziative di protezione dalla posta indesiderata di Office 365 volte a evitare falsi negativi e posta indesiderata, dire agli utenti di aggiungere l'indirizzo del mittente della posta indesiderata all'elenco dei mittenti bloccati in [Outlook](https://go.microsoft.com/fwlink/p/?LinkId=270065) o [Outlook sul web](https://go.microsoft.com/fwlink/p/?LinkId=294862). Per iniziare in Outlook sul web, fare clic su **Impostazioni** \> **Opzioni** \> **Blocca o consenti** e quindi aggiungere l'indirizzo all'elenco **Mittenti bloccati**, come illustrato di seguito. 
  
![Blocco di un mittente in Outlook sul web](media/fdf51381-2527-4819-ac2a-5dff84d2a36d.png)
  
> [!NOTE]
> Per informazioni più dettagliate sugli elenchi di mittenti attendibili, vedere [Domande frequenti sugli elenchi di mittenti attendibili e mittenti bloccati](https://technet.microsoft.com/it-IT/library/dn133608%28v=exchg.150%29.aspx). 
  
## <a name="eop-only-customers-set-up-directory-synchronization"></a>Solo clienti di Exchange Online Protection: Configurare la sincronizzazione della directory

In questo modo, sarà possibile evitare falsi negativi di posta indesiderata se si sincronizzano le impostazioni dell'utente con il servizio attraverso la sincronizzazione della directory per garantire che i mittenti bloccati siano rispettati. Per ulteriori informazioni, vedere "Usare la sincronizzazione della directory per gestire gli utenti di posta elettronica" in Gestione degli utenti di posta elettronica in EOP.
  
## <a name="eop-only-customers-who-are-not-using-directory-synchronization"></a>I clienti solo di EOP che non usano la sincronizzazione della directory

Il servizio Exchange Online Protection è progettato per applicare i mittenti attendibili e i mittenti bloccati se tali informazioni sono state condivise con il servizio. Se un cliente EOP usa Outlook, ma non ha configurato la sincronizzazione della directory per sincronizzare gli utenti con Office 365, è comunque possibile impedire che i messaggi vengano recapitato nella posta in arrivo degli utenti utilizzando i mittenti bloccati. Tuttavia, potrebbe essere necessario configurare alcune regole relative al flusso di posta di Exchange nelle seguenti situazioni:
  
- Se un messaggio supera un filtro protezione da posta indesiderata regolare attraverso EOP e viene quindi recapitato in un server Exchange locale, e EOP assegna un risultato di posta indesiderata pari a SCL 1-4 (non posta indesiderata), l'elenco dei mittenti bloccati locale dell'utente ignorerà quindi il risultato del filtro protezione da posta indesiderata EOP e invierà il messaggio nella cartella di posta indesiderata.
    
- Se a un messaggio in EOP viene assegnato il risultato SCL-1 da una regola del flusso di posta di Exchange o perché l'indirizzo IP o il dominio è uno di quelli consentiti, il livello di probabilità di posta indesiderata viene propagato nel server Exchange locale utilizzando connettori. In questo caso, l'elenco mittenti bloccati dell'utente non verrà applicato. Per modificare tale comportamento, è possibile creare una regola del flusso di posta locale che imposti il livello di probabilità di posta indesiderata su 0. In questo modo, Outlook applicherà l'elenco mittenti bloccati dell'utente.
    
**Per configurare una regola del flusso di posta per impedire che i messaggi vengano recapitati nella posta in arrivo dell'utente tramite l'elenco mittenti bloccati**
  
1. Aprire Exchange Management Shell nel server locale. Per informazioni su come aprire Shell nell'organizzazione di Exchange locale, vedere [Aprire Exchange Management Shell](https://technet.microsoft.com/library/dd638134%28v=exchg.160%29.aspx).
    
2. Eseguire il comando seguente per indirizzare i messaggi di posta indesiderata filtrati in base al contenuto alla cartella Posta indesiderata per aggiornare il livello di probabilità di posta indesiderata di ogni messaggio contrassegnato con SCL -1:
    
  ```
  New-TransportRule "NameForRule" -HeaderContainsMessageHeader "X-Forefront-Antispam-Report" -HeaderContainsWords "SCL:-1" -SetSCL 0
  ```

    Poiché il livello di probabilità di posta indesiderata è 0 nel server Exchange locale, la posta non contrassegnata come posta indesiderata verrà comunque recapitata nella posta in arrivo degli utenti, ma l'elenco mittenti bloccati locale degli utenti potrà comunque inviarla nella posta indesiderata. Se si usa la quarantena della posta indesiderata in EOP, è comunque possibile che i mittenti presenti nell'elenco mittenti attendibili vengano identificati come posta indesiderata e inviati in quarantena. Tuttavia, se si usa la cartella Posta indesiderata nella cassetta postale locale, in questo modo sarà possibile il recapito nella posta in arrivo dei mittenti attendibili.

> [!WARNING]
> Se si usa una regola del flusso di posta elettronica per impostare il valore SCL su 0 (o un valore diverso da -1), allora tutte le opzioni di posta indesiderata di Outlook verranno applicate al messaggio. Questo significa che verranno applicati gli elenchi di elementi attendibili e bloccati, ma anche che i messaggi i cui indirizzi non fanno parte di tali elenchi potrebbero essere contrassegnati come posta indesiderata dal filtro protezione da posta indesiderata sul lato client. Se si desidera che Outlook elabori gli elenchi di elementi attendibili e bloccati, ma non usi il filtro protezione da posta indesiderata sul lato client, è necessario impostare l'opzione "Filtro automatico disattivato" nelle opzioni della posta indesiderata di Outlook. "Filtro automatico disattivato" è l'opzione predefinita nelle ultime versioni di Outlook, ma è necessario verificare che tale impostazione sia attiva per garantire che il filtro protezione da posta indesiderata sul lato client non venga applicato ai messaggi. Gli amministratori possono imporre la disattivazione del filtro protezione da posta indesiderata di Outlook seguendo le istruzioni in [Outlook: impostazione dei criteri per disabilitare l'interfaccia utente della posta indesiderata e il meccanismo di filtro](https://support.microsoft.com/it-IT/kb/2180568).
  
## <a name="see-also"></a>Vedere anche

[Protezione dalla posta indesiderata in Office 365](anti-spam-protection.md)
  
[Evitare che la posta elettronica venga erroneamente contrassegnata come posta indesiderata tramite un elenco di indirizzi attendibili o altre tecniche](prevent-email-from-being-marked-as-spam.md)
