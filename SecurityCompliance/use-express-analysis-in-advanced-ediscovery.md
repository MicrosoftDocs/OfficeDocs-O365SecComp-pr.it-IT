---
title: Usare Analisi rapida in Office 365 Advanced eDiscovery
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 9/14/2017
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 50580099-3dc0-44a1-a9b6-5ca6d396316b
description: Informazioni su come eseguire la modalità di analisi Express di Office 365 avanzate eDiscovery
ms.openlocfilehash: a71e6775b1116e805e455815dca53a727d887809
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/27/2018
ms.locfileid: "22530664"
---
# <a name="use-express-analysis-in-office-365-advanced-ediscovery"></a>Usare Analisi rapida in Office 365 Advanced eDiscovery

> [!NOTE]
> EDiscovery avanzate richiede un Office 365 E3 con il componente aggiuntivo avanzate conformità o una sottoscrizione E5 per l'organizzazione. Se non sono dial plan e desidera provare eDiscovery avanzate, è possibile [iscrizione a una versione di valutazione di Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279). 
  
È possibile utilizzare **Express analisi** per analizzare rapidamente un caso ed esportare i risultati. 
  
È possibile utilizzare analysis express per calcolare quasi duplicati e thread di posta elettronica e calcolare i temi. È inoltre possibile impostare alcuni parametri per i temi, similarità documenti e i file di esportazione in [Impostazioni avanzate per l'analisi Express](use-express-analysis-in-advanced-ediscovery.md#BK_AdvancedSettings).
  
## <a name="run-express-analysis"></a>Eseguire l'analisi del Express

1. Nella scheda **analisi Express** (1), selezionare un contenitore per abilitare il * * Express analisi * * (2) e pulsanti **Impostazioni avanzate** . 
    
    ![Cattura di schermata della pagina analisi Express](media/60009974-5d1f-4971-8ebe-e5ec74e7fd2a.jpg)
  
2. Nella sezione **parametri di analisi**:
    
  - Se si desidera eseguire l'analisi di controllo **calcolare quasi duplicati e thread di posta elettronica** . È selezionata per impostazione predefinita. 
    
  - Controllare **I temi calcolare** per elaborare tutti i file e assegnare loro temi. È selezionata per impostazione predefinita. 
    
3. In **destinazione esportare**:
    
  - Controllare **il Download nel computer locale** per il download nel computer locale. 
    
  - Se si seleziona **Esporta in definita dall'utente Azure blob** è inoltre possibile specificare un token di URL e SAS contenitore. 
    
    > [!NOTE]
    > Una volta che viene archiviato un pacchetto di esportazione per l'utente definito Azure blob, i dati non è più gestiti da eDiscovery avanzate. viene gestita da blob Azure. Di conseguenza, che se si elimina il caso, i file esportati rimangono ancora in Azure blob. 
  
  - **Token SAS salvare per sessione di esportazione future**: se selezionato, il token SAS verrà crittografato nel database interno di eDiscovery avanzate per un utilizzo futuro.
    
    > [!NOTE]
    > Il token SAS attualmente scade dopo un mese. Se si tenta di scaricare dopo avere più di un mese che è necessario annullare l'ultima sessione, quindi rieseguire l'esportazione. 
  
4. Per avviare l'analisi express con predefinito delle impostazioni, scegliere **Express analisi**e verrà visualizzata la pagina **stato attività** 
    
    Nella pagina **stato dell'attività** è possibile espandere le schede **processo**, **analisi** ed **esportare** per visualizzare informazioni dettagliate sull'esecuzione express. 
    
    ![Cattura di schermata di eDiscovery Express analisi attività stato pagina avanzata](media/bf30ab02-9828-4a6d-a485-0babc2c49ae5.jpg)
  
5. Selezionare la pagina **Express analysis riepilogo** per elencare le informazioni dettagliate sull'esecuzione. 
    
    Nella parte inferiore della pagina **Express analysis riepilogo** , selezionare **Scarica ultima sessione** per scaricare l'elaborazione delle transazioni analisi dei file nel computer locale. Innanzitutto è necessario scaricare dello strumento di esportazione di eDiscovery e incollare la chiave di esportazione per lo strumento di esportazione di eDiscovery. 
    
## <a name="advanced-settings-for-express-analysis"></a>Impostazioni avanzate per l'analisi Express
<a name="BK_AdvancedSettings"> </a>

È anche possibile impostare **le impostazioni avanzate** per modificare i parametri di analisi Express predefiniti. 
  
1. Nella sezione **analisi** : 
    
  - Nella **quasi duplicati e thread di posta elettronica**, immettere il valore **similarità documento** o accettare il valore predefinito è 65%. 
    
  - Immettere il **numero massimo di temi** o selezionare un valore per il numero di temi per creare. Il valore predefinito è 200. 
    
    > [!NOTE]
    > L'aumento del numero di temi influisce sulle prestazioni, nonché la possibilità di un tema per generalizzare. Maggiore è il numero di temi, più granulare sono. Se, ad esempio, un insieme di 50 temi includa un tema, ad esempio "Pallacanestro, tramite il, elettrico, Lakers"; 300 temi possono includere i temi separati: "Tramite il", "E", "Lakers". Se si non consapevolezza del tema "Pallacanestro" e utilizzare questa caratteristica per ECA, visualizzando il tema "Pallacanestro" può essere utile. Tuttavia, se l'elaborazione hanno un numero eccessivo di temi, che non venga visualizzato la parola "Pallacanestro" e non possono essere noti che tramite il ed elettrico è buone temi pallacanestro per esaminare, anziché gli elementi da inserire nel viene avviato e utilizzato per fini. 
  
  - Scegliere **Modifica** i suggerimenti tratti tema per controllare l'elaborazione di temi **suggeriti temi** . EDiscovery avanzate verrà occuparsi di queste parole suggerite e tenta di creare uno o più temi rilevanti, in base alle impostazioni "Max numero di temi". 
    
    Ad esempio, se la parola consigliata è "computer" e specificato "2" come "numero massimo di temi", eDiscovery avanzate tenterà di generare due temi correlate alla parola "computer". Due temi potrebbero essere "computer" hardware e "software", ad esempio.
    
    ![Aggiungi tema suggerito](media/06e9ffd3-a76c-423b-b450-9e465eb9a02f.png)
  
  - **Modalità** Dall'elenco a discesa selezionare un'opzione di **temi** : 
    
  - **Creare e applicare modelli**: calcola temi dai modelli da un segmento dei file e quindi distribuisce i file tra loro.
    
  - **Crea modello**: calcola un modello di temi di un segmento dei file. Il processo di applica della divisione di file è terminato separatamente in un secondo momento.
    
  - **Applica modello**: questa opzione viene visualizzata solo se un modello è stato creato in precedenza e non ancora applicato. Ciò consente di dividere il file in base ai temi.
    
2. Nella sezione **esportazione** : 
    
1. Nel **batch di esportazione selezionare**:
    
  - Nell'elenco **Esporta batch** , selezionare il nome del batch o esportare i risultati in batch esportazione 01 (batch predefinito). 
    
  - Per esportare i risultati per i nuovi file aggiunti a un caso esistente, continuare con il batch corrente. Per creare una sessione nel batch, selezionare lo stesso numero di batch e fare clic su **Crea esportare sessione** è possibile utilizzare questa opzione per esportare gli stessi parametri come processo batch precedente, in modo incrementale. 
    
  - Per esportare in un nuovo batch, fare clic su **Aggiungi**![aggiungere icona](media/c2dd8b3a-5a22-412c-a7fa-143f5b2b5612.png) e immettere un nuovo nome nella **casella Nome Batch** (o accettare il valore predefinito) e una descrizione nella **casella Descrizione Batch**. Fare clic su **OK**.
    
  - Per modificare un nome di batch o la descrizione, selezionare il nome di **esportazione batch**, fare clic su **Modifica** ![sull'icona Modifica](media/3d613660-7602-4df2-bdb9-14e9ca2f9cf2.png)e quindi modificare i campi.
    
    > [!NOTE]
    > Dopo aver eseguito le sessioni per un batch di esportazione, non possono essere eliminate. Inoltre, solo alcuni parametri possono essere modificati dopo la prima sessione viene eseguita. 
  
  - Per creare un batch di esportazione duplicati, scegliere **Copia esportazione batch**![creare un'icona di batch esportazione duplicati](media/3f6d5f59-e842-4946-a493-473528af0119.jpg) e immettere un nome e una descrizione per il batch duplicato nel riquadro. 
    
  - Per eliminare un batch di esportazione, scegliere **Elimina**![Elimina un'icona di batch esportazione](media/92a9f8e0-d469-48da-addb-69365e7ffb6f.jpg).
    
  - Per visualizzare la cronologia di un batch, scegliere **cronologia Batch**![sull'icona di visualizzazione cronologia](media/a80cc320-d96c-4d91-8884-75fe2cb147e2.jpg).
    
2. In definire p **opulation:** selezionare **includere solo i file sopra punteggio di pertinenza demarcazione** e/o **batch esportazione Affina ricerca** se si desidera ottimizzare le impostazioni per il batch di esportazione. Se si seleziona **includere solo i file sopra punteggio di pertinenza interruzione**, il **problema** è abilitata e se punteggio di pertinenza del file è superiore al punteggio di interruzione per il rilascio selezionato, quindi viene esportato il file. Il file verrà esportato a meno che non viene escluso per il ' filtro **per la revisione** . Se si seleziona **Affina ricerca esportazione batch**, quindi il **deprovisioning dupe** e **Filter by 'Per revisione' campo** sono abilitati i pulsanti di opzione. Se si sceglie **deprovisioning dupe**, quindi i file duplicati verranno essere filtrati in uscita in base ai criteri definiti: [caso livello (impostazione predefinita): da ogni insieme di file duplicati nell'intero caso, sarà deprovisioning duped file tutti tranne uno. Livello depositaria: da ogni insieme di file duplicati della stessa depositaria, sarà deprovisioning duped file tutti tranne uno. Un record di tutti i file duplicati è disponibile nell'output di esportazione. Se si sceglie campo **filtro in base a 'per la revisione'** , selezionare **Modifica in metadati** immettere le impostazioni di campo **'per la revisione'**. Selezionare **Includi file di input**per includere i file di origine di contenuto del pacchetto. È possibile deselezionare questa opzione per accelerare il processo di esportazione. Si noti che i file nativi verranno esportati in qualsiasi caso.
    
3. In **definire metadati**, selezionare le opzioni seguenti nell'elenco **Esporta modello** (una sola volta per sessione). 
    
  - **Standard**: insieme di proprietà, metadati ed elementi di dati di base. Utilizzare questa opzione quando si importa dati è stato già elaborati di eDiscovery avanzate e caricamento di esportare dati a un sistema che già contiene i file. Per impostazione predefinita, esportare modelli colonne vengono create e piena.
    
  - **Tutti**: insieme completo di metadati standard, inclusi tutti i dati di elaborazione, nonché punteggi Analyze e pertinenza. In questo modello è obbligatorio quando eDiscovery avanzate consente di eseguire l'elaborazione e caricamento di dati dei file a un sistema esterno per la prima volta.
    
  - **Problemi**: consente di selezionare **Tutti i problemi** o selezionare un particolare problema è stato creato. 
    
Fare clic su **OK**per salvare le impostazioni avanzate, **ripristinare i valori predefiniti** per utilizzare i valori predefiniti o **Annulla** per annullare l'impostazione impostazioni avanzate. 
  
## <a name="see-also"></a>Vedere anche
<a name="BK_AdvancedSettings"> </a>

[Office 365 Advanced eDiscovery](office-365-advanced-ediscovery.md)

