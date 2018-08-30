---
title: Create a DLP policy from a template
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 6/29/2018
ms.audience: Admin
ms.topic: article
f1_keywords:
- ms.o365.cc.NewPolicyFromTemplate
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Strat_O365_IP
search.appverid:
- MET150
ms.assetid: 59414438-99f5-488b-975c-5023f2254369
description: "Il metodo più semplice e più comune per acquisire familiarità con i criteri DLP consiste nell'utilizzare uno dei modelli inclusi in Office 365. "
ms.openlocfilehash: 4e3a5d731538e4998858b5f9f7a296c43e6774ac
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/27/2018
ms.locfileid: "22530854"
---
# <a name="create-a-dlp-policy-from-a-template"></a>Creazione di un criterio DLP da un modello

Il metodo più semplice e più comune per acquisire familiarità con i criteri DLP consiste nell'utilizzare uno dei modelli inclusi in Office 365. È possibile utilizzare uno di questi modelli intatte o personalizzare le regole per soddisfare i requisiti di conformità specifici della propria organizzazione.
  
In Office 365 sono disponibili più di 40 modelli pronti all'uso che consentono di soddisfare una vasta gamma di comuni necessità normative e aziendali. Ad esempio, esistono modelli di criteri DLP per:
  
- Gramm-Leach-Bliley Act (GLBA)
    
- Payment Card Industry Data Security Standard (PCI-DSS)
    
- United States Personally Identifiable Information (U.S. PII)
    
- United States Health Insurance Act (HIPAA)
    
È possibile ottimizzare un modello modificando alcune delle regole esistenti oppure aggiungendone di nuove. Ad esempio, è possibile aggiungere nuovi tipi di informazioni riservate a una regola, modificare i conteggi in una regola per renderne più difficile o più facile l'attivazione, consentire agli utenti di eseguire l'override delle azioni in una regola fornendo una motivazione aziendale oppure modificare i destinatari delle notifiche e dei rapporti sulle operazioni non consentite. Un modello di criteri DLP è un punto di partenza adatto a molti scenari di conformità comuni.
  
È inoltre possibile scegliere il modello personalizzato (che non dispone di regole predefinite) e configurare il criterio DLP da zero, per rispondere ai requisiti di conformità specifici dell'organizzazione.
  
## <a name="example-identify-sensitive-information-across-all-onedrive-for-business-sites-and-restrict-access-for-people-outside-your-organization"></a>Esempio: Identificare le informazioni sensibili in OneDrive tutti i siti di Business e limitare l'accesso per gli utenti esterni all'organizzazione

OneDrive per gli account aziendali rendono più semplice per gli utenti di collaborare e condividere documenti all'interno dell'organizzazione. Ma un tema comune a responsabili della conformità informazioni riservate archiviate in OneDrive per gli account di Business possono essere condivisi inavvertitamente con persone esterne all'organizzazione. Un criterio DLP consente di ridurre il rischio.
  
In questo esempio, si creerà un criterio DLP che identifica dati PII negli Stati Uniti, che include i numeri di passaporto i numeri di identificazione singoli fiscale (ITIN), di previdenza sociale e degli Stati Uniti. Per imparare utilizzando un modello e quindi che si desidera modificare il modello per soddisfare i requisiti di conformità dell'organizzazione, in particolare, i seguenti vantaggi:
  
- Aggiungere due tipi di numeri conto bancario riservati information—U.S. e degli Stati Uniti numero della patente, in modo che il criterio DLP protegge ulteriormente i dati riservati.
    
- Verificare i criteri molto riservate, in modo da una singola occorrenza di informazioni riservate è sufficiente per limitare l'accesso per gli utenti esterni.
    
- Consentire agli utenti di ignorare le azioni da fornire una giustificazione aziendale o report un falso positivo. In questo modo, il criterio DLP non impedisce agli utenti dell'organizzazione di ottenere il loro lavoro, purché dispongano di un motivo aziendale valido per la condivisione delle informazioni riservate.
    
### <a name="create-a-dlp-policy-from-a-template"></a>Creazione di un criterio DLP da un modello

1. Accedere a [https://protection.office.com](https://protection.office.com).
    
2. Accedere a Office 365 utilizzando l'account di lavoro o della scuola. L'utente è ora in Office 365 protezione &amp; centro conformità.
    
3. In sicurezza &amp; centro conformità \> riquadro di spostamento sinistro \> **prevenzione della perdita di dati** \> **criteri** \> **+ Crea un criterio**.
    
    ![Creare un pulsante di criteri](media/b1e48a08-92e2-47ca-abdc-4341694ddc7c.png)
  
4. Scegliere il modello di criterio DLP che consente di proteggere i tipi di informazioni riservate che è necessario \> **successivo**.
    
    In questo esempio viene selezionato **Privacy** \> **dati negli Stati Uniti personalmente identificabili informazioni personali** perché già include la maggior parte dei tipi di informazioni riservate che si desidera proteggere, si aggiungerà un paio più avanti. 
    
    Quando si seleziona un modello, è possibile leggere la descrizione a destra per scoprire quali tipi di informazioni riservate il modello protegge.
    
    ![Pagina per la scelta di un modello di criterio DLP](media/775266f6-ad87-4080-8d7c-97f2e7403b30.png)
  
5. Nome del criterio \> **successivo**.
    
6. Per scegliere i percorsi che si desidera che il criterio DLP per proteggere, effettuare una delle operazioni seguenti:
    
  - Scegliere **tutte le posizioni in Office 365** \> **successivo**.
    
  - Scegliere **Seleziona manualmente percorsi specifici** \> **successivo**. In questo esempio, selezionare questa opzione.
    
    Per includere o escludere un intero percorso, ad esempio tutta la posta elettronica Exchange o tutti gli account OneDrive, cambiare lo **stato** di tale posizione attivato o disattivato. 
    
    Per includere solo specifici siti di SharePoint o OneDrive per gli account di Business, cambiare lo **stato** su e quindi fare clic sui collegamenti in **Includi** scegliere specifici siti o gli account. Quando si applica un criterio a un sito, le regole configurate in quanto i criteri vengono applicati automaticamente a tutti i siti secondari del sito. 
    
    ![Opzioni per la posizione in cui è possibile applicare un criterio DLP](media/ee50a61a-e867-4571-a150-3eec8d83650f.png)
  
    In questo esempio consente di disattivare lo **stato** per la **posta elettronica di Exchange** e **siti di SharePoint**per proteggere le informazioni riservate archiviate in OneDrive tutti gli account di Business e lasciare lo **stato** su per **gli account di OneDrive**.
    
7. Scegliere **Impostazioni avanzate di utilizzo** \> **successivo**.
    
8. Un modello di criteri DLP è regole predefinite con condizioni e azioni che rileva problemi e lavorarci sopra specifici tipi di informazioni riservate. Si modificare, eliminare, o disattivare una qualsiasi delle regole esistenti o aggiungere nuove strutture. Al termine, fare clic su **Avanti**.
    
    ![Le regole espanso in modelli di criteri di US PII](media/3bc9f1b6-f8ad-4334-863a-24448bb87687.png)
  
    In questo esempio il modello di dati PII US include due regole predefinite:
    
  - **Bassa volume di contenuto rilevato PII negli Stati Uniti** Questa regola ricerca per i file contenenti tra 1 e 10 occorrenze di ognuno dei tre tipi di informazioni riservate (ITIN SSN, numeri e degli Stati Uniti passport), dove i file vengono condivisi con utenti esterni all'organizzazione. Se viene trovato, la regola invia una notifica tramite posta elettronica per l'amministratore della raccolta siti principale, proprietario del documento, e ultima persona che ha modificato il documento. 
    
  - **Numero elevato di contenuto rilevato PII negli Stati Uniti** Questa regola ricerca per i file contenenti 10 o più occorrenze di ogni gli stessi tipi di informazioni riservate tre, dove i file vengono condivisi con utenti esterni all'organizzazione. Se viene trovato, questa azione Invia inoltre una notifica tramite posta elettronica, oltre limita l'accesso al file. Per il contenuto in un OneDrive for Business account, ciò significa che le autorizzazioni per il documento sono riservate per tutti gli utenti ad eccezione di amministratore della raccolta siti principale, proprietario del documento e persona che ha modificato il documento. 
    
    Per soddisfare requisiti specifici della propria organizzazione, è possibile semplificare le regole trigger, in modo da una singola occorrenza di informazioni riservate è sufficiente per bloccare l'accesso per gli utenti esterni. Dopo aver osservando queste regole, è comprendere che non è necessario regole numero massimo e minimo, è necessario solo una singola regola che blocca l'accesso se viene trovata qualsiasi occorrenza di informazioni riservate.
    
    In modo che si espande la regola denominata **bassa volume di contenuto rilevato US PII** \> **eliminare regola**.
    
    ![Eliminazione di un pulsante regola](media/bc36f7d2-0fae-4af1-92e8-95ba51077b12.png)
  
9. A questo punto, in questo esempio, è necessario aggiungere due tipi di informazioni riservate, i numeri di conto bancario negli Stati Uniti e degli Stati Uniti numero della patente, consentire agli utenti di eseguire l'override di una regola e modificare il conteggio in tutte le occorrenze. È possibile eseguire queste operazioni per modificare una sola regola, se si desidera selezionare **elevato volume di contenuto rilevato US PII** \> **modificare una regola**.
    
    ![Regola pulsante Modifica](media/eaf54067-4945-4c98-8dd6-fb2c5d6de075.png)
  
10. Per aggiungere un tipo di informazioni riservate, nella sezione **condizioni** \> **tipi di aggiungere o modificare**. Quindi, in **Aggiungi o modifica tipi** \> scegliere **Aggiungi** \> selezionare **Il numero di conto bancario negli Stati Uniti** e il **Numero della patente di Guida di US** \> **Add** \> **Fine**.
    
    ![Opzione per aggiungere o modificare i tipi](media/c6c3ae86-f7db-40a8-a6e4-db11692024be.png)
  
    ![Aggiungere o modificare riquadro tipi](media/fdbb96af-b914-4a6c-a97b-bbd014689965.png)
  
11. Per modificare il numero (numero di istanze di informazioni riservate necessaria per l'attivazione della regola), nella casella **numero di istanza** \> scegliere il valore **minimo** per ogni tipo di \> immettere 1. Il numero minimo non può essere vuoto. Il numero massimo può essere vuoto. un valore vuoto di tipo **max** convertire in **qualsiasi**.
    
    Al termine, il numero di minuti per tutti i tipi di informazioni riservate dovrebbe essere **1** e il numero massimo deve essere **qualsiasi**. In altre parole, le occorrenze di questo tipo di informazioni riservate soddisferà questa condizione.
    
    ![Numero di istanza per i tipi di informazioni riservate](media/5c6e08cb-59a9-4558-b54b-d899836d4737.png)
  
12. Per la personalizzazione finale, per evitare che i criteri DLP per bloccare gli utenti di svolgere il lavoro quando sono motivazione aziendale valido o verificarsi un falso positivo, in modo che si desidera notifica all'utente per includere le opzioni per ignorare l'azione blocco.
    
    Nella sezione **notifiche utente** è evidente che le notifiche di posta elettronica e suggerimenti sui criteri vengono attivati per impostazione predefinita per questa regola nel modello. 
    
    Nella sezione **utente esegue l'override** è evidente che vengono attivate sostituzioni per motivazione aziendale, ma non sono le sostituzioni per segnalare falsi positivi. Scegliere **Ignora la regola automaticamente se si segnalarlo come falso positivo**.
    
    ![Nella sezione notifiche dell'utente e l'utente esegue l'override di sezione](media/62720e7a-a939-4c03-b414-67748f3d64a0.png)
  
13. Nella parte superiore dell'editor di regole, modificare il nome della regola da quella predefinita **elevato volume di contenuto rilevato PII negli Stati Uniti** **qualsiasi contenuto rilevato con PII negli Stati Uniti** dal momento che ora è attivata per qualsiasi occorrenza dei relativi tipi di informazioni riservate. 
    
14. Nella parte inferiore dell'editor di regole \> **salvare**.
    
15. Leggere le condizioni e azioni per la regola \> **successivo**.
    
    A destra, osservare lo **stato** passare per la regola. Se si disattiva un intero criterio, tutte le regole di contenuti nei criteri vengono disattivate anche. Tuttavia, qui è possibile disattivare una regola specifica senza disattivare il criterio intero. Può risultare utile quando è necessario analizzare una regola che genera un numero elevato di falsi positivi. 
    
16. Nella pagina successiva, leggere e comprendere le operazioni seguenti e quindi scegliere se si desidera attivare la regola o verificare le funzionalità di \> **successivo**.
    
     Prima di creare i criteri DLP, è consigliabile distribuire gradualmente per valutare l'impatto e testare l'efficacia prima di imporre completamente. Ad esempio, non si desidera un nuovo criterio DLP inavvertitamente bloccare l'accesso a migliaia di documenti che necessitano di persone per ottenere il loro lavoro. 
    
    Se si sta creando criteri DLP con un impatto potenziale di grandi dimensioni, è consigliabile sequenza indicata di seguito:
    
17. Iniziare in modalità test senza suggerimenti per i criteri, quindi utilizzare i report DLP per valutare l'impatto. È possibile utilizzare i report DLP per visualizzare il numero, il percorso, il tipo e la gravità di corrispondenza del criterio. A seconda dei risultati, è possibile ottimizzare le regole in modo adeguato. In modalità test, i criteri DLP non avranno effetto sulla produttività degli utenti dell'organizzazione. 
    
18. Passare alla modalità test con notifiche e suggerimenti per i criteri in modo da istruire gli utenti in merito ai criteri di conformità e prepararli all'applicazione delle regole. In questa fase, è inoltre possibile chiedere agli utenti di segnalare i falsi positivi per definire ulteriormente le regole.
    
19. Attivare i criteri in modo che vengono applicate le regole e il contenuto del protetto. Continuare a monitorare i report DLP e qualsiasi rapporti operazioni non consentite o le notifiche per assicurarsi che i risultati sono si prevede. 
    
    ![Opzioni per l'utilizzo della modalità di test e dell'attivazione dei criteri](media/49fafaac-c6cb-41de-99c4-c43c3e380c3a.png)
  
20. Controllare le impostazioni per il criterio \> scegliere **Crea**.
    
Dopo aver creato e attivare un criterio DLP, viene distribuito a qualsiasi origini di contenuto che include, ad esempio siti di SharePoint Online o OneDrive per gli account aziendale, in cui il criterio inizia automaticamente applicate le regole in tale contenuto.
  
## <a name="view-the-status-of-a-dlp-policy"></a>Visualizzare lo stato di un criterio DLP

In qualsiasi momento, è possibile visualizzare lo stato dei criteri DLP nella pagina **criteri** nella sezione **prevenzione della perdita di dati** della sicurezza &amp; centro conformità. Di seguito sono disponibili informazioni importanti, ad esempio se un criterio è stata corretta abilitazione o disabilitazione o se il criterio è in modalità test. 
  
Di seguito sono riportati i diversi stati e il loro significato.
  
|**Stato**|**Spiegazione**|
|:-----|:-----|
|**Attivazione in corso...** <br/> |Il criterio viene distribuito alle origini del contenuto che include. Il criterio non è ancora applicato su tutte le origini.  <br/> |
|**Test, con notifiche** <br/> |Il criterio è in modalità test. Le azioni in una regola non sono applicate, ma vengono raccolte le corrispondenze del criterio ed è possibile visualizzarle tramite i report DLP. Le notifiche relative alle corrispondenze del criterio vengono inviate ai destinatari specificati.  <br/> |
|**Test, senza notifiche** <br/> |Il criterio è in modalità test. Le azioni in una regola non sono applicate, ma vengono raccolte le corrispondenze del criterio ed è possibile visualizzarle tramite i report DLP. Le notifiche relative alle corrispondenze del criterio non vengono inviate ai destinatari specificati.  <br/> |
|**Attivo** <br/> |Il criterio è attivo e applicato. Il criterio è stato distribuito correttamente a tutte le origini del contenuto.  <br/> |
|**Disattivazione in corso...** <br/> |Il criterio viene rimosso dalle origini del contenuto che include. Il criterio potrebbe essere ancora attivo e applicato in alcune origini. La disattivazione di un criterio potrebbe richiedere fino a 45 minuti.  <br/> |
|**Disattivo** <br/> |Il criterio non è attivo e non applicato. Le impostazioni del criterio (origini, parole chiave, durata e così via) vengono salvate.  <br/> |
|**Eliminazione in corso...** <br/> |Il criterio è in corso di eliminazione. Il criterio non è attivo e non applicato.  <br/> |
   
## <a name="turn-off-a-dlp-policy"></a>Disattivare un criterio DLP

È possibile modificare o disattivare un criterio DLP in qualsiasi momento. La disattivazione di un criterio disattiva tutte le regole del criterio.
  
Per modificare o disattivare un criterio DLP, nella pagina **criteri** \> selezionare il criterio \> **modificare i criteri**.
  
![Criteri pulsante Modifica](media/ce319e92-0519-44fe-9507-45a409eaefe4.png)
  
Inoltre, è possibile disattivare ogni regola singolarmente modificando il criterio e quindi attivazione e disattivazione disattivare lo **stato** della regola, come descritto in precedenza. 
  
## <a name="more-information"></a>Ulteriori informazioni

- [Panoramica relativa ai criteri di prevenzione della perdita di dati](data-loss-prevention-policies.md)
    
- [Inviare notifiche e visualizzare i suggerimenti per i criteri DLP](use-notifications-and-policy-tips.md)
    
- [Creare un criterio DLP per proteggere i documenti con FCI o altre proprietà](protect-documents-that-have-fci-or-other-properties.md)
    
- [Elementi inclusi nei modelli di criteri di prevenzione della perdita dei dati](what-the-dlp-policy-templates-include.md)
    
- [Inventario dei tipi di informazioni riservate](what-the-sensitive-information-types-look-for.md)
    

