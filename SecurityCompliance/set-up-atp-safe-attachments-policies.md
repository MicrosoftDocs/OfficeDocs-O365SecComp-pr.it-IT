---
title: Impostare i criteri di sicurezza allegati di Office 365 degli strumenti di analisi
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.audience: Admin
ms.topic: article
ms.date: 02/05/2019
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 078eb946-819a-4e13-8673-fe0c0ad3a775
description: Definire i criteri di sicurezza degli allegati per proteggere l'organizzazione da file dannosi nella posta elettronica.
ms.openlocfilehash: 229f5eb4ec1af4302f724151f599bd33b15055e1
ms.sourcegitcommit: a64af0ebd0b03e4a5e60a33e9108c44c7d74f356
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/05/2019
ms.locfileid: "29741119"
---
# <a name="set-up-office-365-atp-safe-attachments-policies"></a>Impostare i criteri di sicurezza allegati di Office 365 degli strumenti di analisi

Persone regolarmente inviano, ricevere e condividere allegati, ad esempio documenti, presentazioni, fogli di calcolo e altro ancora. Non è sempre sapere se un allegato è sicuro o volontario semplicemente visualizzando un messaggio di posta elettronica in modo semplice. E l'ultimo elemento che si desidera che un allegato da svolgere, causando per l'organizzazione. Fortunatamente, può contribuire a [Office 365 avanzate Threat Protection](office-365-atp.md) (degli strumenti di analisi). È possibile impostare i criteri [Degli strumenti di analisi gli allegati sicuri](atp-safe-attachments.md) per contribuire a garantire che l'organizzazione è protetto contro gli attacchi per gli allegati di posta elettronica non sicuri. 
  
## <a name="what-to-do"></a>cosa fare 
  
1. [Verificare i prerequisiti](#review-the-prerequisites)
    
2. [Configurare un criterio di allegati sicuri degli strumenti di analisi](#set-up-an-atp-safe-attachments-policy)
    
3. [Informazioni sulle opzioni di criteri di allegati sicuri degli strumenti di analisi](#learn-about-atp-safe-attachments-policy-options)
    
## <a name="step-1-review-the-prerequisites"></a>Passaggio 1: Verificare i prerequisiti

- Verificare che l'organizzazione dispone di [Protezione di Office 365 avanzate rischio](office-365-atp.md).
    
- Verificare di disporre delle autorizzazioni necessarie. Per definire o modificare i criteri degli strumenti di analisi, è necessario assegnare uno dei ruoli descritti nella tabella riportata di seguito: <br>

    |Ruolo  |Modalità assegnato  |
    |---------|---------|
    |Amministratore globale di Office 365 |La persona che iscrizione acquistare Office 365 è un amministratore globale per impostazione predefinita. Vedere [ruoli di amministratore su Office 365](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles) per ulteriori informazioni.         |
    |Amministratore di protezione di Office 365 |Interfaccia di amministrazione ([https://aka.ms/admincenter](https://aka.ms/admincenter))|
    |Exchange Online Organization Management |Interfaccia di amministrazione di Exchange ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp)) <br>oppure <br>  Cmdlet di PowerShell (vedere [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps)) |
    
- [Informazioni sulle opzioni di criteri di allegati sicuri degli strumenti di analisi](#learn-about-atp-safe-attachments-policy-options) (in questo articolo). Alcune opzioni, ad esempio le opzioni di monitoraggio o sostituzione possono comportare un ritardo di posta elettronica secondario quando gli allegati vengono analizzati. Per evitare ritardi messaggio, è consigliabile utilizzare [Recapito dinamico e visualizzazione in anteprima](dynamic-delivery-and-previewing.md).
    
- Consentire fino a 30 minuti per il criterio di nuovo o aggiornato da distribuire a tutti i centri dati di Office 365.
    
## <a name="step-2-set-up-or-edit-an-atp-safe-attachments-policy"></a>Passaggio 2: Configurare un criterio di allegati sicuri degli strumenti di analisi (o modifica)
  
1. Accedere a [https://protection.office.com](https://protection.office.com) e accedere con l'account di lavoro o della scuola. 
    
2. In Office 365 Security &amp; centro conformità, nel riquadro di spostamento a sinistra, in **gestione rischio**, scegliere **criterio** \> **Gli allegati sicuri**.
    
3. Se viene visualizzata **attivare degli strumenti di analisi di SharePoint, OneDrive e team di Microsoft**, è consigliabile selezionare questa opzione. In questo modo sarà [Office 365 avanzate Threat Protection for SharePoint, OneDrive e team di Microsoft](atp-for-spo-odb-and-teams.md) per l'ambiente Office 365. 
    
4. Scegliere **New** (nuovo pulsante è simile a un segno di addizione ( **+**)) per iniziare a creare i criteri.
    
5. Specificare il nome, descrizione e le impostazioni per il criterio.<br/><br/>**Esempio:** Per configurare un criterio non denominato "ritardi" che consente di eseguire immediatamente i messaggi di tutti gli utenti e quindi ricollega allegati dopo che si sta analisi, è possibile specificare le impostazioni seguenti: 
    
      - Nella casella **nome** non digitare alcun ritardi.
    
      - Nella casella **Descrizione** digitare una descrizione like e fornisce messaggi immediatamente e gli allegati Ricollega dopo la scansione.
    
      - Nella sezione response scegliere l'opzione di **Recapito dinamico** . ([Ulteriori informazioni sul recapito dinamico e l'anteprima allegati sicuri degli strumenti di analisi di](dynamic-delivery-and-previewing.md)).
    
      - Nella sezione **reindirizzare degli allegati** , selezionare l'opzione per abilitare reindirizza e digitare l'indirizzo di posta elettronica di amministratore globale, amministratore della sicurezza o analista di protezione che verrà analizzare gli allegati dannosi Office 365. 
    
      - Nella sezione **Applicato a** scegliere **il dominio del destinatario è**e quindi selezionare il dominio. Scegliere **Aggiungi**e quindi fare clic su **OK**.
    
6. Scegliere **Save**.
    
È possibile impostare più criteri gli allegati sicuri degli strumenti di analisi per l'organizzazione. Questi criteri da applicare in ordine che sono elencate nella pagina **Allegati sicuri degli strumenti di analisi** . Dopo un criterio è stato definito o modificato, attendere almeno 30 minuti per i criteri per rendere effettive nell'intera datacenter Microsoft. 
  
## <a name="step-3-learn-about-atp-safe-attachments-policy-options"></a>Passaggio 3: Informazioni sulle opzioni di criteri di allegati sicuri degli strumenti di analisi

Per la configurazione di criteri di allegati sicuri degli strumenti di analisi, scegliere tra varie opzioni, tra Monitor, blocca, Sostituisci, recapito dinamico e così via. Nel caso in cui si desidera sapere per sulle operazioni di queste opzioni, nella tabella seguente sono riepilogati tutti e degli effetti.
  
|**Opzione**|**Effetto**|**Utilizzare quando si desidera:**|
|:-----|:-----|:-----|
|**Off** <br/> |Non analizza allegati di malware  <br/> Non ritardare il recapito dei messaggi  <br/> |Disattivare l'analisi per mittenti interni, programmi antivirus, fax o smart host che invierà solo gli allegati e funzionante  <br/> Evitare ritardi non necessari in routing della posta interna  <br/> **Questa opzione non è consigliata per la maggior parte degli utenti. Consente di disattivare la scansione degli allegati sicuri degli strumenti di analisi per un piccolo gruppo di mittenti interni.**           |
|**Monitor** <br/> |Recapito dei messaggi con allegati e quindi tiene traccia cosa accade a malware rilevato  <br/> |Vedere dove malware rilevato passa all'interno dell'organizzazione  <br/> |
|**Blocco** <br/> |Impedisce che i messaggi con allegati malware rilevato dal procedere  <br/> Invia i messaggi con malware rilevato alla [quarantena in Office 365](manage-quarantined-messages-and-files.md) cui un amministratore della sicurezza o analista può esaminare e rilasciare (o eliminare) i messaggi  <br/> Blocca i messaggi futuri e allegati automaticamente  <br/> |Proteggere l'organizzazione da attacchi ripetuti utilizzando lo stessa allegati malware  <br/> |
|**Sostituisce** <br/> |Rimuove rilevato malware degli allegati  <br/> Avvisare destinatari che siano stati rimossi gli allegati  <br/> Invia i messaggi con malware rilevato alla [quarantena in Office 365](manage-quarantined-messages-and-files.md) cui un amministratore della sicurezza o analista può esaminare e rilasciare (o eliminare) i messaggi  <br/> |Aumentare la visibilità ai destinatari che gli allegati sono state rimosse a causa di malware rilevato  <br/> |
|**Recapito dinamico** <br/> |Invia messaggi immediatamente  <br/> Sostituisce gli allegati con un file segnaposto fino a quando non analisi è stato completato e quindi ricollega gli allegati se non viene rilevato alcuna malware  <br/> Include l'anteprima di funzionalità per la maggior parte dei documenti PDF e Office allegato file durante l'analisi  <br/> Invia i messaggi con malware rilevato per cui un amministratore della sicurezza o analista può esaminare e rilasciare (o eliminare) i messaggi di quarantena  <br/> [Informazioni su Recapito dinamico e l'anteprima allegati sicuri degli strumenti di analisi di](dynamic-delivery-and-previewing.md) <br/> |Evitare ritardi messaggio proteggendo al contempo i destinatari dal file dannosi  <br/> Consentire ai destinatari di visualizzare in anteprima degli allegati in modalità provvisoria durante l'analisi è in corso  <br/> |
|**Abilitare reindirizza** <br/> |Si applica quando si sceglie l'opzione Monitor, blocca o sostituzione  <br/> Invia gli allegati a un indirizzo di posta elettronica specificati in security administrators o analisti possono essere esaminate  <br/> |Consentire agli amministratori di sicurezza e agli analisti di allegati sospetti di ricerca  <br/> |
   
## <a name="next-steps"></a>Passaggi successivi

Una volta criteri di allegati sicuri degli strumenti di analisi, è possibile visualizzare la modalità di utilizzo degli strumenti di analisi per l'organizzazione visualizzando i report. Le risorse seguenti per ulteriori informazioni, vedere:
- [Visualizzare i report per la protezione rischio avanzate di Office 365](view-reports-for-atp.md)
- [Utilizzare Esplora in sicurezza &amp; centro conformità](use-explorer-in-security-and-compliance.md)

Mantenersi in primo piano rispetto a nuove funzionalità di punta degli strumenti di analisi. visita il sito Web [Microsoft 365 Roadmap](https://www.microsoft.com/microsoft-365/roadmap?filters=O365) e informazioni sulle [nuove funzionalità che vengono aggiunti degli strumenti di analisi](office-365-atp.md#new-features-are-continually-being-added-to-atp).
 