---
title: Esportare i campi rapporto in Office 365 Advanced eDiscovery
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 9/14/2017
ms.audience: Admin
ms.topic: reference
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 840a5aff-ecd0-4e56-ad22-fe99bc143687
description: Descrizione dei campi inclusi nei report di esportazione di eDiscovery avanzate.
ms.openlocfilehash: a578523098248bcfa16ea8ba97d756d97ba060fa
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/27/2018
ms.locfileid: "22530487"
---
# <a name="export-report-fields-in-office-365-advanced-ediscovery"></a>Esportare i campi rapporto in Office 365 Advanced eDiscovery

> [!NOTE]
> EDiscovery avanzate richiede un Office 365 E3 con il componente aggiuntivo avanzate conformità o una sottoscrizione E5 per l'organizzazione. Se non sono dial plan e desidera provare eDiscovery avanzate, è possibile [iscrizione a una versione di valutazione di Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279). 
  
Questo argomento descrive i campi esportazione eDiscovery avanzate per lo Standard e tutti i modelli.
  
## <a name="export-report-fields"></a>Esportare i campi del report

Nella tabella seguente sono elencati i campi per ogni modello di esportazione.
  
|**Nome del campo Export**|**Gruppo**|**Descrizione**|**Disponibile nel modello Standard**|**Disponibile in tutti i modelli**|
|:-----|:-----|:-----|:-----|:-----|
|Row_number  <br/> |Generale  <br/> |Numero di righe.  <br/> |Sì  <br/> |Sì  <br/> |
|File_ID  <br/> |Generale  <br/> |ID del file.  <br/> |Sì  <br/> |Sì  <br/> |
|File_class  <br/> |Elaborazione  <br/> |Classe di file.  <br/> |Sì  <br/> |Sì  <br/> |
|Family_ID  <br/> |Elaborazione  <br/> |Identificatore numerico che viene utilizzato per raggruppare i file (in genere l'istanza di posta elettronica e i suoi allegati).  <br/> |Sì  <br/> |Sì  <br/> |
|For_review  <br/> |Elaborazione  <br/> |Flag che indica che il campo sarà incluso nell'esportazione per la revisione.  <br/> |Sì  <br/> |Sì  <br/> |
|Native_file_name  <br/> |Elaborazione  <br/> |Nome di file nativo, senza riferimenti alle cartelle e l'estensione.  <br/> |Sì  <br/> |Sì  <br/> |
|Depositari  <br/> |Generale  <br/> |Depositaria del file.  <br/> |Sì  <br/> |Sì  <br/> |
|Set_ID  <br/> |Analizzare  <br/> |"ND impostare" o "Set di posta elettronica" id.  <br/> |Sì  <br/> |Sì  <br/> |
|Inclusive_type  <br/> |Posta elettronica  <br/> |Indica se file inclusi in base ai valori seguenti: 0 - non è incluso, 1 - 2 inclusi - inclusi meno 3 - copia inclusi.  <br/> |Sì  <br/> |Sì  <br/> |
|Marked_as_pivot  <br/> |Quasi duplicati  <br/> |Indica se il file è un pivot.  <br/> |Sì  <br/> |Sì  <br/> |
|Similarity_percent  <br/> |Quasi duplicati  <br/> |Percentuale di similarità rispetto al pivot.  <br/> |Sì  <br/> |Sì  <br/> |
|Duplicate_subset  <br/> |Quasi duplicati  <br/> |Identificatore univoco del sottoinsieme di duplicati. Indica se il file ha duplicati testo esatto.  <br/> |Sì  <br/> |Sì  <br/> |
|Data  <br/> |Generale  <br/> |Data del file (dipende dal tipo di file - messaggio di posta elettronica: data di invio, documento: Data ultima modificata).  <br/> |Sì  <br/> |Sì  <br/> |
|Dominant_theme  <br/> |Analizzare  <br/> |Tema principale del file.  <br/> |Sì  <br/> |Sì  <br/> |
|Themes_list  <br/> |Temi  <br/> |Elenco di nomi di tema.  <br/> |Sì  <br/> |Sì  <br/> |
|ND_set  <br/> |EquiSet  <br/> |Identificatore numerico univoco di un set di Nearduplicate.  <br/> |Sì  <br/> |Sì  <br/> |
|Email_set  <br/> |Posta elettronica  <br/> |Identificatore numerico univoco di un insieme di posta elettronica.  <br/> |Sì  <br/> |Sì  <br/> |
|Email_thread  <br/> |Posta elettronica  <br/> |Descrive la posizione del messaggio di posta elettronica all'interno di posta elettronica impostato Consists di tutti gli ID di nodo dalla radice del messaggio di posta elettronica corrente, separato da punti.  <br/> |Sì  <br/> |Sì  <br/> |
|Email_subject  <br/> |Posta elettronica  <br/> |Oggetto del messaggio di posta elettronica.  <br/> |Sì  <br/> |Sì  <br/> |
|Email_date_sent  <br/> |Posta elettronica  <br/> |Data in cui è stato inviato il messaggio di posta elettronica.  <br/> |Sì  <br/> |Sì  <br/> |
|Email_participants  <br/> |Posta elettronica  <br/> |Indirizzi di posta elettronica di tutti i partecipanti in un thread di posta elettronica, inclusi i collegamenti mancante.  <br/> |Sì  <br/> |Sì  <br/> |
|Email_participant_domains  <br/> |Posta elettronica  <br/> |Domini di tutti i partecipanti in un thread di posta elettronica, inclusi per collegamento mancante.  <br/> |Sì  <br/> |Sì  <br/> |
|Email_sender  <br/> |Posta elettronica  <br/> |Nome mittente del messaggio di posta elettronica e/o indirizzo.  <br/> |Sì  <br/> |Sì  <br/> |
|Email_sender_domain  <br/> |Posta elettronica  <br/> |Dominio del mittente della posta elettronica.  <br/> |Sì  <br/> |Sì  <br/> |
|Email_to  <br/> |Posta elettronica  <br/> |Al destinatario del messaggio di posta elettronica.  <br/> |Sì  <br/> |Sì  <br/> |
|Email_cc  <br/> |Posta elettronica  <br/> |Destinatario CC del messaggio di posta elettronica.  <br/> |Sì  <br/> |Sì  <br/> |
|Email_bcc  <br/> |Posta elettronica  <br/> |Destinatario Ccn del messaggio di posta elettronica.  <br/> |Sì  <br/> |Sì  <br/> |
|Email_recipient_domains  <br/> |Posta elettronica  <br/> |Destinatari della posta domini (a, CC e Ccn).  <br/> |Sì  <br/> |Sì  <br/> |
|Email_date_received  <br/> |Posta elettronica  <br/> |Data in cui è stata ricevuta posta elettronica.  <br/> |Sì  <br/> |Sì  <br/> |
|Email_action  <br/> |Posta elettronica  <br/> |Valori: In base all'oggetto di posta elettronica: "Inoltra" (per "firmware:"), "Reply" (per "r:") o "Altri" (altro soggetto testo).  <br/> |Sì  <br/> |Sì  <br/> |
|Meeting_Start_Date/ora  <br/> ||Data e ora di inizio di una riunione.  <br/> |Sì  <br/> |Sì  <br/> |
|Meeting_End_Date/ora  <br/> ||Data e ora di fine di una riunione.  <br/> |Sì  <br/> |Sì  <br/> |
|File_relevance_score  <br/> |Pertinenza  <br/> |Punteggio di pertinenza (0-100). Per ogni problema.  <br/> |Sì  <br/> |Sì  <br/> |
|Family_relevance_score  <br/> |Pertinenza  <br/> |Famiglia di max punteggio di pertinenza (0-100). Per ogni problema.  <br/> |Sì  <br/> |Sì  <br/> |
|Relevance_tag  <br/> |Pertinenza  <br/> |Tagging di file, se il file è stato contrassegnato manualmente di pertinenza. Per ogni problema.  <br/> |Sì  <br/> |Sì  <br/> |
|Relevance_load_group  <br/> |Pertinenza  <br/> |Gruppo di carico pertinenza, del file specificato, con un campo per ogni problema.  <br/> |Sì  <br/> |Sì  <br/> |
|Normalized_relevance_score  <br/> |Pertinenza  <br/> |Pertinenza normalizzata punteggio (0-100), che paragonabili tra carichi e problemi.  <br/> |Sì  <br/> |Sì  <br/> |
|Marked_as_seed  <br/> |Pertinenza  <br/> |Tagging di file, se è stato impostato per essere come file di seeding di pertinenza Per/categoria del problema.  <br/> |Sì  <br/> |Sì  <br/> |
|Contrassegnati Marked_as_pre  <br/> |Pertinenza  <br/> |Tagging di file, se è stato impostato come pre-contrassegnati di pertinenza Per/categoria del problema.  <br/> |Sì  <br/> |Sì  <br/> |
|Relevance_status_description  <br/> |Pertinenza  <br/> |Descrizione dello stato della pertinenza.  <br/> |Sì  <br/> |Sì  <br/> |
|Commento  <br/> |Generale  <br/> |Commento immessa dall'utente.  <br/> |Sì  <br/> |Sì  <br/> |
|Export_input_path  <br/> |Elaborazione  <br/> |Esportazione del percorso.  <br/> |Sì  <br/> |Sì  <br/> |
|Pivot_ID  <br/> |Quasi duplicati  <br/> |Pivot l'ID del file.  <br/> |Sì  <br/> |Sì  <br/> |
|Family_size  <br/> |Elaborazione  <br/> |Numero di file in un gruppo.  <br/> |Sì  <br/> |Sì  <br/> |
|Native_type  <br/> |Elaborazione  <br/> |Tipo di file nativo. Ad esempio, fogli di calcolo o presentazione.  <br/> |Sì  <br/> |Sì  <br/> |
|Native_MD5  <br/> |Elaborazione  <br/> |Valore hash MD5 del file nativo.  <br/> |Sì  <br/> |Sì  <br/> |
|Native_size  <br/> |Elaborazione  <br/> |Dimensioni file nativo.  <br/> |Sì  <br/> |Sì  <br/> |
|Native_extension  <br/> |Elaborazione  <br/> |Estensione di file nativo.  <br/> |Sì  <br/> |Sì  <br/> |
|Doc_date_modified  <br/> |Proprietà del documento  <br/> |Data di file nativo è stato modificato, derivato dai metadati del file.  <br/> |Sì  <br/> |Sì  <br/> |
|Doc_date_created  <br/> |Proprietà del documento  <br/> |File native data è stata creata, riguarda i metadati del file.  <br/> |Sì  <br/> |Sì  <br/> |
|Doc_modified_by  <br/> |Proprietà del documento  <br/> |Utente che ha modificato file nativo, derivato dai metadati del file.  <br/> |Sì  <br/> |Sì  <br/> |
|O365_date_modified  <br/> |Proprietà del documento  <br/> |File native data è stato modificato, derivato dal campo SharePoint o Exchange.  <br/> |Sì  <br/> |Sì  <br/> |
|O365_date_created  <br/> |Proprietà del documento  <br/> |È stato creato file native data, derivato dal campi SharePoint or Exchange.  <br/> |Sì  <br/> |Sì  <br/> |
|O365_modified_by  <br/> |Proprietà del documento  <br/> |Ultimo utente che ha modificato file nativo, derivato dal campi SharePoint or Exchange.  <br/> |Sì  <br/> |Sì  <br/> |
|Compound_path  <br/> |Elaborazione  <br/> |Percorso di file nativo includendo origine composti.  <br/> |Sì  <br/> |Sì  <br/> |
|Input_path  <br/> |Elaborazione  <br/> |Percorso del file di input.  <br/> |Sì  <br/> |Sì  <br/> |
|Input_date_modified  <br/> |Elaborazione  <br/> |File di Input data dell'ultima modifica.  <br/> |Sì  <br/> |Sì  <br/> |
|ND_ET_sort_excl_attach  <br/> |Analizzare  <br/> |Imposta concatenamento di posta elettronica e ND per la revisione. Era ' aggiunta come prefisso ND insiemi e 'E' viene aggiunto al messaggio di posta elettronica imposta.  <br/> |Sì  <br/> |Sì  <br/> |
|ND_ET_sort_incl_attach  <br/> |Analizzare  <br/> |Imposta concatenamento di posta elettronica e ND impostare per la revisione potrebbe ' aggiunta come prefisso a insiemi ND ed 'E' viene aggiunto ai set di posta elettronica. Inoltre, ciascun messaggio di posta elettronica all'interno di un Email_set è seguito da suoi allegati appropriati.  <br/> |Sì  <br/> |Sì  <br/> |
|Deduped_custodians  <br/> |Generale  <br/> |Depositari dei file deprovisioning duped  <br/> |Sì  <br/> |Sì  <br/> |
|Deduped_file_IDs  <br/> |Generale  <br/> |ID dei file deprovisioning duped  <br/> |Sì  <br/> |Sì  <br/> |
|Deduped_paths  <br/> |Generale  <br/> |Percorsi di file deprovisioning duped  <br/> |Sì  <br/> |Sì  <br/> |
|File_key  <br/> |Generale  <br/> |Identificatore interno per un utilizzo futuro.  <br/> |Sì  <br/> |Sì  <br/> |
|Export_native_path  <br/> |Elaborazione  <br/> |Percorso del file nativo nel pacchetto di esportazione.  <br/> |Sì  <br/> |Sì  <br/> |
|Extracted_text_path  <br/> |Elaborazione  <br/> |Percorso del file estratto.  <br/> |Sì  <br/> |Sì  <br/> |
|Process_batch  <br/> |Elaborazione  <br/> |Identificatore batch batch di importazione.  <br/> |Sì  <br/> |Sì  <br/> |
|Process_status_ID  <br/> |Elaborazione  <br/> |Identificatore che rappresentano fase stato del processo.  <br/> |Sì  <br/> |Sì  <br/> |
|Process_status_description  <br/> |Elaborazione  <br/> |Descrizione del passaggio lo stato del processo: ha esito positivo o descrizione dell'errore.  <br/> |Sì  <br/> |Sì  <br/> |
|Export_status_ID  <br/> |Elaborazione  <br/> |ID dello stato di esportazione.  <br/> |Sì  <br/> |Sì  <br/> |
|Export_status_description  <br/> |Elaborazione  <br/> |Descrizione dello stato di esportazione; esito positivo o descrizione dell'errore.  <br/> |Sì  <br/> |Sì  <br/> |
|Read_percent  <br/> |Pertinenza  <br/> |% Lettura (0-100). Per ogni problema.  <br/> |Sì  <br/> |Sì  <br/> |
|Doc_author  <br/> |Proprietà del documento  <br/> |Nelle proprietà dei documenti: autore.  <br/> |No  <br/> |Sì  <br/> |
|Doc_comments  <br/> |Proprietà del documento  <br/> |Nelle proprietà dei documenti: commenti.  <br/> |No  <br/> |Sì  <br/> |
|Doc_keywords  <br/> |Proprietà del documento  <br/> |Nelle proprietà dei documenti: parole chiave.  <br/> |No  <br/> |Sì  <br/> |
|Doc_last_saved_by  <br/> |Proprietà del documento  <br/> |Nelle proprietà dei documenti: Autore ultimo salvata.  <br/> |No  <br/> |Sì  <br/> |
|Doc_revision  <br/> |Proprietà del documento  <br/> |Nelle proprietà dei documenti: numero di revisione.  <br/> |No  <br/> |Sì  <br/> |
|Doc_subject  <br/> |Proprietà del documento  <br/> |Nelle proprietà dei documenti: subject.  <br/> |No  <br/> |Sì  <br/> |
|Doc_template  <br/> |Proprietà del documento  <br/> |Nelle proprietà dei documenti: modello.  <br/> |No  <br/> |Sì  <br/> |
|Doc_title  <br/> |Proprietà del documento  <br/> |Nelle proprietà dei documenti: titolo.  <br/> |No  <br/> |Sì  <br/> |
|Email_has_attachment  <br/> |Posta elettronica  <br/> |Indica se il messaggio di posta elettronica è uno o più allegati.  <br/> |No  <br/> |Sì  <br/> |
|Email_importance  <br/> |Posta elettronica  <br/> |Proprietà importanza della posta elettronica.  <br/> |No  <br/> |Sì  <br/> |
|Email_level  <br/> |Posta elettronica  <br/> |Indica il livello di posta elettronica all'interno del thread di posta elettronica. Per gli allegati, il valore del messaggio di posta elettronica associato.  <br/> |No  <br/> |Sì  <br/> |
|Email_recipients  <br/> |Posta elettronica  <br/> |Indirizzi (a, CC e Ccn) e/o nome della posta elettronica dei destinatari.  <br/> |No  <br/> |Sì  <br/> |
|Email_security  <br/> |Posta elettronica  <br/> |La proprietà di protezione della posta elettronica.  <br/> |No  <br/> |Sì  <br/> |
|Email_sensitivity  <br/> |Posta elettronica  <br/> |Proprietà sensitivity della posta elettronica.  <br/> |No  <br/> |Sì  <br/> |
|Export_batch  <br/> |Elaborazione  <br/> |Esportazione batch cognome di file.  <br/> |No  <br/> |Sì  <br/> |
|Export_session  <br/> |Elaborazione  <br/> |Id tra cui data ultima sessione di esportazione di file.  <br/> |No  <br/> |Sì  <br/> |
|Extracted_text_length  <br/> |Elaborazione  <br/> |Caratteri del file di testo estratto.  <br/> |No  <br/> |Sì  <br/> |
|Family_duplicate_set  <br/> |Elaborazione  <br/> |Identificatore numerico per le famiglie che sono duplicati testo esatto di loro (rispettivamente - tutti i membri delle famiglie sono duplicati).  <br/> |No  <br/> |Sì  <br/> |
|Has_Text  <br/> |Elaborazione  <br/> |Indica se esiste un testo nel file: 0 - non; 1 - Sì.  <br/> |No  <br/> |Sì  <br/> |
|Input_file_ID  <br/> |Elaborazione  <br/> |ID del file di Input da cui è stato estratto i file da.  <br/> |No  <br/> |Sì  <br/> |
|Native_SHA_256  <br/> |Elaborazione  <br/> |Valore hash SHA-256 del file nativo.  <br/> |No  <br/> |Sì  <br/> |
|O365_authors  <br/> |Proprietà del documento  <br/> |Utenti che ha modificato file nativo, derivato dal campi SharePoint or Exchange.  <br/> |No  <br/> |Sì  <br/> |
|O365_created_by  <br/> |Proprietà del documento  <br/> |Utente che ha creato file nativo, derivato dal campi SharePoint or Exchange.  <br/> |No  <br/> |Sì  <br/> |
|Parent_node  <br/> |Posta elettronica  <br/> |Riguarda un nodo in un thread di posta elettronica per il nodo padre più vicino che non è un collegamento mancante.  <br/> |No  <br/> |Sì  <br/> |
|Set_order_inclusives_first  <br/> |Posta elettronica  <br/> |Messaggi di posta elettronica e allegati: ordine cronologico dei contatori (Inclusives prima). Documenti: ruota funzionalità e le altre per punteggio similarità, decrescente.  <br/> |No  <br/> |Sì  <br/> |
|Tagged_By  <br/> |Pertinenza  <br/> |Utente che ha contrassegnato il file di pertinenza per il problema specifico.  <br/> |No  <br/> |Sì  <br/> |
|Word_count  <br/> |Analizzare  <br/> |Numero di parole del documento.  <br/> |No  <br/> |Sì  <br/> |
|||||||||||
||||||
||||||
   
## <a name="related-topics"></a>Argomenti correlati

[Office 365 Advanced eDiscovery](office-365-advanced-ediscovery.md)
  
[Esportazione dei dati maiuscole con eDiscovery avanzate](export-case-data-in-advanced-ediscovery.md)
  
[Esportazione dei risultati](export-results-in-advanced-ediscovery.md)
  
[Visualizzazione della cronologia batch e l'esportazione dei risultati passati](view-batch-history-and-export-past-results.md)
  

