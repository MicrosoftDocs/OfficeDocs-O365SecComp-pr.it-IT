---
title: Esportare i risultati in Office 365 Advanced eDiscovery
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
ms.assetid: a9951a07-10b3-48cb-b37a-0ffaa24931ad
description: "Informazioni su come definire le opzioni per l'esportazione dei risultati da Office 365 avanzate eDiscovery, compresa la procedura per specificare i parametri per un batch di esportazione. "
ms.openlocfilehash: 92ee107ad096393fbccbc9a3dbe81d8e7dd28da9
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/27/2018
ms.locfileid: "22531392"
---
# <a name="export-results-in-office-365-advanced-ediscovery"></a>Esportare i risultati in Office 365 Advanced eDiscovery

> [!NOTE]
> EDiscovery avanzate richiede un Office 365 E3 con il componente aggiuntivo avanzate conformità o una sottoscrizione E5 per l'organizzazione. Se non sono dial plan e desidera provare eDiscovery avanzate, è possibile [iscrizione a una versione di valutazione di Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279). 
  
In questo argomento vengono descritte le opzioni di installazione esportazione eDiscovery avanzate.
  
 **Contenuto dell'argomento:**
  
- [Definizione dei batch di esportazione e sessioni](export-results-in-advanced-ediscovery.md#BK_Define)
    
- [Esporta incrementali e aggiuntive](export-results-in-advanced-ediscovery.md#BK_IncrementalReports)
    
- [Impostare i parametri di esportazione batch](export-results-in-advanced-ediscovery.md#BK_SetUpExport)
    
- [Esportare i file di output di report](export-results-in-advanced-ediscovery.md#BK_ExportOutputFIles)
    
## <a name="defining-export-batches-and-sessions"></a>Definizione dei batch di esportazione e sessioni
<a name="BK_Define"> </a>

Un batch di esportazione consente l'elaborazione di esportazione utilizzando un set di parametri definiti. EDiscovery avanzate consente di definire batch per personalizzare ogni esportazione.
  
I parametri sono definiti per il batch di esportazione. Per impostazione predefinita per il primo batch di un caso, viene creato un batch denominato "Export batch 01". È inoltre possibile modificare il nome del batch e la descrizione.
  
Una sessione di esportazione è un'esecuzione dell'esportazione di eDiscovery avanzate all'interno di un batch di esportazione.
  
## <a name="incremental-and-additional-exports"></a>Esporta incrementali e aggiuntive
<a name="BK_IncrementalReports"> </a>

È possibile eseguire più sessioni di esportazione all'interno di un batch di esportazione, per assicurare risultati coerenti basati sul modello di esportazione stesso e parametri. Per ogni sessione all'interno di un batch, è possibile esportare analitica per elaborare dati maiuscole appena ed elaborare ogni "in modo incrementale."
  
Per esportare utilizzando un diverso set di parametri, è necessario innanzitutto creare un nuovo batch. La prima sessione il nuovo batch produrrà risultati per file elaborati nel caso finora, indipendentemente dal fatto questi file sono stati importati ed elaborati su una o più importazioni. Ogni blocco Ricalcola pivot, similarità, inclusives e così via. Sessioni di utilizzano i parametri definiti per il batch di e non vengono ricalcolate pivot, similarità, inclusives e così via per ogni esecuzione di sessione.
  
Si supponga ad esempio un caso è stato importato e analizzare i relativi dati. Per poter recuperare quasi duplicati e i risultati Threading posta elettronica per i dati incrementali, fare clic su **Crea esportare sessione** nello stesso batch che è stato utilizzato per esportare i dati. 
  
## <a name="set-up-batch-export-parameters"></a>Impostare i parametri di esportazione batch
<a name="BK_SetUpExport"> </a>

EDiscovery esportare strumento viene utilizzato per esportare i risultati della ricerca di eDiscovery avanzata del computer locale. Per aumentare la velocità effettiva di trasferimento dati e velocizzare il processo di esportazione, è possibile configurare un'impostazione del Registro di sistema di Windows nel computer utilizzato per esportare i risultati della ricerca. Se si desidera aumentare la velocità di download, configurare l'impostazione del Registro di sistema prima di impostare i parametri di esportazione. Per ulteriori informazioni, vedere [aumentare la velocità di download per l'esportazione dei risultati della ricerca eDiscovery da Office 365](increase-download-speeds-when-exporting-ediscovery-results.md).
  
1. In eDiscovery avanzate, selezionare un caso e fare clic su **Esporta** \> **il programma di installazione**.
    
  - Nell'elenco **Esporta batch** , selezionare il nome del batch o esportare i risultati in batch esportazione 01 (batch predefinito). 
    
  - Per esportare i risultati per i nuovi file aggiunti a un caso esistente, continuare con il batch corrente. Per creare una sessione nel batch, selezionare lo stesso numero di batch e fare clic su **Crea esportare sessione** è possibile utilizzare questa opzione per esportare gli stessi parametri come processo batch precedente, in modo incrementale. 
    
  - Per esportare in un nuovo batch, fare clic su **Aggiungi**![aggiungere icona](media/c2dd8b3a-5a22-412c-a7fa-143f5b2b5612.png)e immettere un nuovo nome nella **casella Nome Batch** (o accettare il valore predefinito) e una descrizione nella **casella Descrizione Batch**. Fare clic su **OK**.
    
  - Per modificare un nome di batch o la descrizione, selezionare il nome di **esportazione batch**, fare clic su **Modifica** ![sull'icona Modifica](media/3d613660-7602-4df2-bdb9-14e9ca2f9cf2.png)e quindi modificare i campi.
    
    > [!NOTE]
    > Dopo aver eseguito le sessioni per un batch di esportazione, non possono essere eliminate. Inoltre, solo alcuni parametri possono essere modificati dopo la prima sessione viene eseguita. 
  
  - Per creare un batch di esportazione duplicati, scegliere **Copia esportazione batch**![creare un'icona di batch esportazione duplicati](media/3f6d5f59-e842-4946-a493-473528af0119.jpg) e immettere un nome e una descrizione per il batch duplicato nel riquadro. 
    
  - Per eliminare un batch di esportazione, scegliere **Elimina**![Elimina un'icona di batch esportazione](media/92a9f8e0-d469-48da-addb-69365e7ffb6f.jpg).
    
  - Per visualizzare la cronologia di un batch, scegliere **cronologia Batch**![sull'icona di visualizzazione cronologia](media/a80cc320-d96c-4d91-8884-75fe2cb147e2.jpg).
    
2. In **popolazione**, selezionare **includere solo i file sopra punteggio di pertinenza demarcazione** e/o **batch esportazione Affina ricerca** se si desidera ottimizzare le impostazioni per il batch di esportazione. 
    
3. Se si seleziona **includere solo i file sopra punteggio di pertinenza interruzione**, il **problema** è abilitata. Se punteggio di pertinenza del file è superiore al punteggio di interruzione per il rilascio selezionato, a meno che non viene escluso dal filtro 'per la revisione' verrà esportato il file. 
  
Se si seleziona **Affina ricerca esportazione batch**, il **deprovisioning dupe** e filtrare per 'Per revisione' sono abilitati i pulsanti di campo. Se si sceglie **deprovisioning dupe**, quindi i file duplicati verranno filtrati in base ai criteri definiti [caso livello (impostazione predefinita): da ogni insieme di file duplicati nell'intero caso, sarà deprovisioning duped file tutti tranne uno. Livello depositaria: da ogni insieme di file duplicati della stessa depositaria, file tutti tranne uno sarà deprovisioning duped.] L'output export contiene un record di tutti i file duplicati. Se si sceglie campo **filtro in base a 'per la revisione'** , selezionare **Modifica in metadati** immettere le impostazioni di campo **'per la revisione'** . Selezionare **Includi file di input** per includere i file di origine di contenuto del pacchetto. È possibile deselezionare questa impostazione per accelerare il processo di esportazione. Si noti che i file nativi verranno esportati in qualsiasi caso. 
    
4. In **metadati**, selezionare le opzioni seguenti nell'elenco **Esporta modello** (una sola volta per sessione). 
    
  - **Standard**: insieme di proprietà, metadati ed elementi di dati di base. Utilizzare questa opzione quando si importa dati è stato già elaborati di eDiscovery avanzate e caricamento di esportare dati a un sistema che già contiene i file. Per impostazione predefinita, esportare modelli colonne vengono create e piena.
    
  - **Tutti**: insieme completo di metadati standard, inclusi tutti i dati di elaborazione, nonché punteggi Analyze e pertinenza. In questo modello è obbligatorio quando eDiscovery avanzate consente di eseguire l'elaborazione e caricamento di dati dei file a un sistema esterno per la prima volta.
    
  - **Problemi**: consente di selezionare **Tutti i problemi** o selezionare un particolare problema è stato creato. 
    
5. Nella sezione **destinazione**:
    
  - **Scaricare nel computer locale**
    
  - **Esporta in definita dall'utente blob Azure**: se questa opzione è selezionata, è possibile specificare un token di URL e SAS contenitore.
    
    > [!NOTE]
    > Una volta che viene archiviato un pacchetto di esportazione per l'utente definito blob Azure, i dati non è più gestiti da avanzate eDiscovery; viene gestita da blob Azure. Di conseguenza, che se si elimina il caso, i file esportati rimangono ancora in Azure blob. 
  
  - **Token SAS salvare per sessione di esportazione future**: se selezionato, il token SAS verrà crittografato nel database interno di eDiscovery avanzate per un utilizzo futuro.
    
    > [!NOTE]
    > Il token SAS attualmente scade dopo un mese. Se si tenta di scaricare dopo avere più di un mese che è necessario annullare l'ultima sessione, quindi rieseguire l'esportazione. 
  
6. Fare clic su **Modifica** per impostare il "per la revisione ' Impostazioni campo. 
    
> ![Impostare per la revisione campo impostazioni per un batch di esportazione](media/39451aba-f6fe-4a01-8ed0-0be6a6ce889a.png)
  
    In **For review field settings** panel, in **Select scenario**, select the scenario and scope of the review. The settings are displayed based on your selection.
    
    **Review all** (default): All emails, attachments, and documents are selected by default. 
    
    **Review all unique content in a set**: Inclusives and unique inclusive copies, unique attachments in email set level, representative from every set of exact duplicates.
    
    **Review all unique content in a set - no inclusive copies**: Inclusives, unique attachments in email set level, representative from every set of exact duplicates.
    
    **Review all unique content and related family files**: Inclusives, unique attachments in email set level, representative from every set of exact duplicates, expand to include family files.
    
    **Custom** (allows you to define the options in the dialog): The default is to keep current selections and enable all dialog options, to allow their selection. 
    
    If you select custom, you can then customize the settings for emails, documents, attachments and miscellaneous.
    
> Selezionare i messaggi di posta elettronica che si desidera esportare **messaggi di posta elettronica** : 
    
    **All emails**: (default) All emails are selected.
    
    **Inclusives**: An inclusive email is a last email of a thread, and it contains all the other emails from the thread.
    
    **Inclusives and unique inclusive copies**: Inclusive copies and inclusives with the same subject, body and attachments; unique inclusive copies are unique copies of these emails .
    
> Selezionare i documenti che si desidera esportare **documenti** : 
    
    **All documents**: (default) All documents are selected.
    
    **Pivots**: A file chosen as representative of near-duplicates set, which is typically used as the baseline when reviewing the set.
    
    **Representative from every set of exact duplicates**: Unique near-duplicate files (including the pivot).
    
> Selezionare gli allegati che si desidera esportare **gli allegati** 
    
    **All attachments**: (default) All attachments are selected.
    
    **Unique attachment in case level**: Unique attachment files within the specified case.
    
    **Unique attachment in email set level**: Unique attachment files within the specified email case.
    
> In **Micellaneous** è possibile scegliere di **trattare allegati come documenti**, **considera i messaggi di posta elettronica come documenti**o **Espandi per includere i file della famiglia**. Quando si sceglie **Expand per includere i file della famiglia**, per ogni file è contrassegnato per la revisione, tutti i file della stessa famiglia inoltre essere contrassegnati.
    
    Choose **Save** to save the settings. 
    
7. Dopo avere specificato i parametri di esportazione, per avviare il batch di esportazione, fare clic su **Crea esportare sessione**.
    
    Durante l'esportazione, lo stato viene visualizzato lo stato delle **attività**. I risultati vengono visualizzati **nell'esportazione riepilogo**.
    
8. Nella finestra **Download file** fare clic su **Copia negli Appunti** per copiare la chiave di esportazione. 
    
    ![Download dei file](media/99cf2c13-4954-479f-9741-80d7458c1a15.png)
  
9. Fare clic su **Chiudi**. 
    
    Strumento di esportazione di eDiscovery è stato avviato.
    
    ![Strumento di esportazione di eDiscovery](media/705756ca-ee97-4d24-b70f-8b23513f6d11.gif)
  
10. In **eDiscovery esportare strumento**:
    
1. In **incollare la firma di accesso condiviso che verrà utilizzato per la connessione all'origine**, incollare la chiave di esportazione che youcopied negli Appunti nel passaggio 7.
    
2. Fare clic su **Sfoglia** per selezionare il percorso di destinazione per archiviare i file di esportazione scaricato nel computer locale. 
    
11. Fare clic su **Start**. Esportare i file vengono scaricati nel computer locale. Se si sceglie **Esporta in blob Azure definita dall'utente** nel passaggio 4, la sessione viene esportata in una destinazione di URL di archiviazione Blob di propria scelta. 
    
Per una descrizione completa dei campi del rapporto di esportazione, vedere [esportare i campi del report](export-report-fields-in-advanced-ediscovery.md).
  
## <a name="export-report-output-files"></a>Esportare i file di output di report
<a name="BK_ExportOutputFIles"> </a>

Nella tabella seguente sono elencati i file di output generati durante l'esecuzione di un batch di esportazione.
  
|**Nome di file**|**Tipo file**|**Descrizione**|
|:-----|:-----|:-----|
|Riepilogo di esportazione  <br/> |CSV  <br/> |File di registro generato dallo strumento di esportazione di eDiscovery.  <br/> |
|Traccia  <br/> |txt  <br/> |File di registro generato dallo strumento di esportazione di eDiscovery.  <br/> |
|File di testo estratto  <br/> |Cartella del file  <br/> |Cartella che contiene i file di testo estratto del file esportati.  <br/> |
|File nativi o input  <br/> |Cartella del file  <br/> |Cartella che contiene i file nativi e di input del file esportati.  <br/> |
|Esporta elenco  <br/> |xlsx  <br/> |Metadati file esportato in formato xlsx. Campi nei file vengono fornite in base al modello utente seleziona da esportare. Se necessario, vengono creati file diversi, ognuno contiene righe 100-150 KB. Se un determinato valore contiene più caratteri di una cella di Excel può contenere (attualmente il limite è 32.767 caratteri), quindi il valore viene ritagliato per la lunghezza massima consentita. Se un valore viene tagliato, il colore di sfondo della cella è rosso a indicare che si all'utente." I partecipanti di posta elettronica"sono un esempio di un campo che può superare il limite di lunghezza, se è stato inviato il messaggio di posta elettronica a una distribuzione di grandi dimensioni. Per informazioni dettagliate sui campi di output, vedere [esportare i campi del report](export-report-fields-in-advanced-ediscovery.md) .<br/> |
|File di caricamento  <br/> |CSV  <br/> |Metadati file esportato in formato csv per il caricamento in un'altra applicazione. Campi nei file vengono fornite in base al modello utente seleziona da esportare.  <br/> |
|Indicatore di operazione riuscita  <br/> |txt  <br/> |Create solo per l'esportazione per un 3rd parti blob Azure. Se l'esportazione completata correttamente, verrà creato il file. In caso di errore, o parziale esito positivo del file non verrà creato. Verrà creato il file nella cartella radice, consentendo di rilevamento automatico in diversi stati batch/sessioni di esportazione. Si tratta di un file vuoto. È il nome: TenantId_CaseId_ExternalCaseId_CaseName_ExportBatchId_SessionId_DateTime.txt.  <br/> |
   
## <a name="see-also"></a>Vedere anche
<a name="BK_ExportOutputFIles"> </a>

[Office 365 Advanced eDiscovery](office-365-advanced-ediscovery.md)
  
[Visualizzazione della cronologia batch e l'esportazione dei risultati passati](view-batch-history-and-export-past-results.md)
  
[Impostazione rapida di Office 365 Advanced eDiscovery](quick-setup-for-advanced-ediscovery.md)

[Esportare i campi del report](export-report-fields-in-advanced-ediscovery.md)
  
[Aumentare la velocità di download per l'esportazione dei risultati della ricerca eDiscovery da Office 365](increase-download-speeds-when-exporting-ediscovery-results.md)

