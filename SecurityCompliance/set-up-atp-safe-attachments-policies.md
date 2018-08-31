---
title: Impostare i criteri di sicurezza allegati di Office 365 degli strumenti di analisi
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 5/8/2018
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 078eb946-819a-4e13-8673-fe0c0ad3a775
description: Definire i criteri di sicurezza degli allegati per proteggere l'organizzazione da file dannosi nella posta elettronica.
ms.openlocfilehash: 03fb0b62d37dc628241a1108b4b256290c23509b
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/27/2018
ms.locfileid: "22530708"
---
# <a name="set-up-office-365-atp-safe-attachments-policies"></a>Impostare i criteri di sicurezza allegati di Office 365 degli strumenti di analisi

Persone regolarmente inviano, ricevere e condividere allegati, ad esempio documenti, presentazioni, fogli di calcolo e altro ancora. Non è sempre sapere se un allegato è sicuro o volontario semplicemente visualizzando un messaggio di posta elettronica in modo semplice. E l'ultimo elemento che si desidera che un allegato da svolgere, causando per l'organizzazione. Fortunatamente, può contribuire a [Office 365 avanzate Threat Protection](office-365-atp.md) (degli strumenti di analisi). È possibile impostare i criteri [Degli strumenti di analisi gli allegati sicuri](atp-safe-attachments.md) per contribuire a garantire che l'organizzazione è protetto contro gli attacchi per gli allegati di posta elettronica non sicuri. 
  
## <a name="what-to-do"></a>cosa fare 
  
1. [Verificare i prerequisiti](#review-the-prerequisites)
    
2. [Configurare un criterio di allegati sicuri degli strumenti di analisi](#set-up-an-atp-safe-attachments-policy)
    
3. [Informazioni sulle opzioni di criteri di allegati sicuri degli strumenti di analisi](#learn-about-atp-safe-attachments-policy-options)
    
## <a name="review-the-prerequisites"></a>Verificare i prerequisiti

- Verificare che l'organizzazione dispone di [Protezione di Office 365 avanzate rischio](office-365-atp.md).
    
- Verificare di disporre i necessari [autorizzazioni assegnate in Office 365 Security &amp; centro conformità](permissions-in-the-security-and-compliance-center.md).
    
- [Informazioni sulle opzioni di criteri di allegati sicuri degli strumenti di analisi](#learn-about-atp-safe-attachments-policy-options) (in questo articolo). Alcune opzioni, ad esempio le opzioni di monitoraggio o sostituzione possono comportare un ritardo di posta elettronica secondario quando gli allegati vengono analizzati. Per evitare ritardi messaggio, è consigliabile utilizzare [Recapito dinamico e visualizzazione in anteprima](dynamic-delivery-and-previewing.md).
    
- Consentire fino a 30 minuti per il criterio di nuovo o aggiornato da distribuire a tutti i centri dati di Office 365.
    
## <a name="set-up-an-atp-safe-attachments-policy"></a>Configurare un criterio di allegati sicuri degli strumenti di analisi

È possibile impostare un criterio di allegati sicuri degli strumenti di analisi utilizzando la protezione di Office 365 &amp; centro conformità o l'interfaccia di amministrazione di Exchange (EAC). **è consigliabile utilizzare la protezione di Office 365 &amp; centro conformità**. 
  
1. Un amministratore globale o un amministratore di protezione, passare a [https://protection.office.com](https://protection.office.com) e accedere con l'account di lavoro o della scuola. 
    
2. In Office 365 Security &amp; centro conformità, nel riquadro di spostamento a sinistra, in **gestione rischio**, scegliere **criterio** \> **Gli allegati sicuri**.
    
3. Se viene visualizzata **attivare degli strumenti di analisi di SharePoint, OneDrive e team di Microsoft**, è consigliabile selezionare questa opzione. In questo modo sarà [Office 365 avanzate Threat Protection for SharePoint, OneDrive e team di Microsoft](atp-for-spo-odb-and-teams.md) per l'ambiente Office 365. 
    
4. Scegliere **New** (nuovo pulsante è simile a un segno di addizione ( **+**)) per iniziare a creare i criteri.
    
5. Specificare il nome, descrizione e le impostazioni per il criterio.
    
    **Esempio:** Per configurare un criterio non denominato "ritardi" che consente di eseguire immediatamente i messaggi di tutti gli utenti e quindi ricollega allegati dopo che si sta analisi, è possibile specificare le impostazioni seguenti: 
    
  - Nella casella **nome** non digitare alcun ritardi.
    
  - Nella casella **Descrizione** digitare una descrizione like e fornisce messaggi immediatamente e gli allegati Ricollega dopo la scansione.
    
  - Nella sezione response scegliere l'opzione di **Recapito dinamico** . ([Informazioni relative alla consegna dinamica e l'anteprima allegati sicuri degli strumenti di analisi di](dynamic-delivery-and-previewing.md)).
    
  - Nella sezione **reindirizzare degli allegati** , selezionare l'opzione per abilitare reindirizza e digitare l'indirizzo di posta elettronica di amministratore globale, amministratore della sicurezza o analista di protezione che verrà analizzare gli allegati dannosi Office 365. 
    
  - Nella sezione **Applicato a** scegliere **il dominio del destinatario è**e quindi selezionare il dominio. Scegliere **Aggiungi**e quindi fare clic su **OK**.
    
6. Fare clic su **Salva**.
    
È possibile impostare più criteri gli allegati sicuri degli strumenti di analisi per l'organizzazione. Questi criteri da applicare in ordine che sono elencate nella pagina **Allegati sicuri degli strumenti di analisi** . Dopo un criterio è stato definito o modificato, attendere almeno 30 minuti per i criteri per rendere effettive nell'intera datacenter Microsoft. 
  
## <a name="learn-about-atp-safe-attachments-policy-options"></a>Informazioni sulle opzioni di criteri di allegati sicuri degli strumenti di analisi

Per la configurazione di criteri di allegati sicuri degli strumenti di analisi, scegliere tra varie opzioni, tra Monitor, blocca, Sostituisci, recapito dinamico e così via. Nel caso in cui si desidera sapere per sulle operazioni di queste opzioni, nella tabella seguente sono riepilogati tutti e degli effetti.
  
|**Opzione**|**Effetto**|**Utilizzare quando si desidera:**|
|:-----|:-----|:-----|
|**Off** <br/> |Non analizza allegati di malware  <br/> Non ritardare il recapito dei messaggi  <br/> |Disattivare l'analisi per mittenti interni, programmi antivirus, fax o smart host che invierà solo gli allegati e funzionante  <br/> Evitare ritardi non necessari in routing della posta interna  <br/> > [!IMPORTANT]> Questa opzione non è consigliata per la maggior parte degli utenti. Consente di disattivare la scansione degli allegati sicuri degli strumenti di analisi per un piccolo gruppo di mittenti interni.           |
|**Monitor** <br/> |Recapito dei messaggi con allegati e quindi tiene traccia cosa accade a malware rilevato  <br/> |Vedere dove malware rilevato passa all'interno dell'organizzazione  <br/> |
|**Blocco** <br/> |Impedisce che i messaggi con allegati malware rilevato dal procedere  <br/> Invia i messaggi con malware rilevato alla [quarantena in Office 365](manage-quarantined-messages-and-files.md) cui un amministratore della sicurezza o analista può esaminare e rilasciare (o eliminare) i messaggi  <br/> Blocca i messaggi futuri e allegati automaticamente  <br/> |Proteggere l'organizzazione da attacchi ripetuti utilizzando lo stessa allegati malware  <br/> |
|**Sostituisce** <br/> |Rimuove rilevato malware degli allegati  <br/> Avvisare destinatari che siano stati rimossi gli allegati  <br/> Invia i messaggi con malware rilevato alla [quarantena in Office 365](manage-quarantined-messages-and-files.md) cui un amministratore della sicurezza o analista può esaminare e rilasciare (o eliminare) i messaggi  <br/> |Aumentare la visibilità ai destinatari che gli allegati sono state rimosse a causa di malware rilevato  <br/> |
|**Recapito dinamico** <br/> |Invia messaggi immediatamente  <br/> Sostituisce gli allegati con un file segnaposto fino a quando non analisi è stato completato e quindi ricollega gli allegati se non viene rilevato alcuna malware  <br/> Include l'anteprima di funzionalità per la maggior parte dei documenti PDF e Office allegato file durante l'analisi  <br/> Invia i messaggi con malware rilevato per cui un amministratore della sicurezza o analista può esaminare e rilasciare (o eliminare) i messaggi di quarantena  <br/> [Informazioni su Recapito dinamico e l'anteprima allegati sicuri degli strumenti di analisi di](dynamic-delivery-and-previewing.md) <br/> |Evitare ritardi messaggio proteggendo al contempo i destinatari dal file dannosi  <br/> Consentire ai destinatari di visualizzare in anteprima degli allegati in modalità provvisoria durante l'analisi è in corso  <br/> |
|**Abilitare reindirizza** <br/> |Si applica quando si sceglie l'opzione Monitor, blocca o sostituzione  <br/> Invia gli allegati a un indirizzo di posta elettronica specificati in security administrators o analisti possono essere esaminate  <br/> |Consentire agli amministratori di sicurezza e agli analisti di allegati sospetti di ricerca  <br/> |
   
## <a name="related-topics"></a>Argomenti correlati

[Office 365 Advanced Threat Protection](office-365-atp.md)
  
[Allegati degli strumenti di analisi sicuro in Office 365](atp-safe-attachments.md)
  
[Collegamenti degli strumenti di analisi sicuro in Office 365](atp-safe-links.md)
  
[Impostare i criteri degli strumenti di analisi collegamenti attendibili in Office 365](set-up-atp-safe-links-policies.md)
  
[Visualizzare i report per Advanced Threat Protection](view-reports-for-atp.md)

[Le autorizzazioni di sicurezza di Office 365 &amp; centro conformità](permissions-in-the-security-and-compliance-center.md)
  

