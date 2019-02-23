---
title: Cercare ed eliminare i messaggi di posta elettronica nell'organizzazione di Office 365-Guida per gli amministratori
ms.author: markjjo
author: markjjo
manager: laurawi
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MET150
ms.assetid: 3526fd06-b45f-445b-aed4-5ebd37b3762a
description: Utilizzare la funzionalità di ricerca e spurgo nel centro sicurezza &amp; e conformità di Office 365 per cercare ed eliminare un messaggio di posta elettronica da tutte le cassette postali dell'organizzazione.
ms.openlocfilehash: ecdacd4e484d6de267e029b8e3fcdafc9b1fce4d
ms.sourcegitcommit: a80bd8626720fabdf592b84e4424cd3a83d08280
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/23/2019
ms.locfileid: "30223615"
---
# <a name="search-for-and-delete-email-messages-in-your-office-365-organization---admin-help"></a>Cercare ed eliminare i messaggi di posta elettronica nell'organizzazione di Office 365-Guida per gli amministratori

**Questo articolo è per gli amministratori. Si sta tentando di trovare gli elementi nella cassetta postale che si desidera eliminare? Vedere [trovare un messaggio o un elemento con ricerca immediata](https://support.office.com/article/69748862-5976-47b9-98e8-ed179f1b9e4d)**|
   
È possibile utilizzare la funzionalità Ricerca contenuto in Office 365 per cercare ed eliminare un messaggio di posta elettronica da tutte le cassette postali dell'organizzazione. In questo modo è possibile trovare e rimuovere messaggi di posta elettronica potenzialmente dannosi o ad alto rischio, ad esempio:
  
- Messaggi che contengono allegati o virus pericolosi
    
- Messaggi di phishing
    
- Messaggi contenenti dati sensibili
    
> [!CAUTION]
> Search and Purge è una funzionalità potente che consente a tutti gli utenti a cui vengono assegnate le autorizzazioni necessarie per eliminare i messaggi di posta elettronica dalle cassette postali dell'organizzazione. 
  
## <a name="before-you-begin"></a>Informazioni preliminari

- Per creare ed eseguire una ricerca di contenuto, è necessario essere membri del gruppo di ruoli **eDiscovery Manager** o essere assegnati al ruolo di gestione della **ricerca di conformità** . Per eliminare i messaggi, è necessario essere membri del gruppo di ruoli **Gestione organizzazione** o assegnare il ruolo di gestione di **ricerca ed eliminazione** . Per informazioni sull'aggiunta di utenti a un gruppo di ruoli, vedere [Give users access to the Office 365 Security _AMP_ Compliance Center](grant-access-to-the-security-and-compliance-center.md).
    
- Per eliminare i messaggi, è necessario utilizzare la sicurezza di & Compliance Center PowerShell. Per istruzioni su come effettuare la connessione, vedere [passaggio 2](#step-2-connect-to-security-amp-compliance-center-powershell) .
    
- Un massimo di 10 elementi per ogni cassetta postale può essere rimosso contemporaneamente. Poiché la funzionalità di ricerca e rimozione dei messaggi è destinata a essere uno strumento di risposta agli incidenti, questo limite garantisce che i messaggi vengano rimossi rapidamente dalle cassette postali. Questa funzionalità non è destinata a pulire le cassette postali degli utenti. Per eliminare più di 10 elementi, è possibile utilizzare il comando **Search-Mailbox-DeleteContent** in Exchange Online PowerShell. Vedere [cercare ed eliminare i messaggi-Guida per gli amministratori](search-for-and-delete-messagesadmin-help.md).
    
- Il numero massimo di cassette postali in una ricerca di contenuto in cui è possibile eliminare gli elementi eseguendo un'azione di ricerca ed eliminazione è 50.000. Se la ricerca di contenuto creata nel [passaggio 1](#step-1-create-a-content-search-to-find-the-message-to-delete)contiene più di 50.000 cassette postali di origine, l'azione Purge (creata nel passaggio 3) avrà esito negativo. Vedere la sezione [ulteriori informazioni](#more-information) per un suggerimento sull'esecuzione di un'operazione di ricerca ed eliminazione su più di 50.000 cassette postali. 
    
- La procedura descritta in questo articolo può essere utilizzata solo per eliminare gli elementi nelle cassette postali di Exchange Online e nelle cartelle pubbliche. Non è possibile utilizzarlo per eliminare il contenuto da siti di SharePoint o OneDrive for business.
    
## <a name="step-1-create-a-content-search-to-find-the-message-to-delete"></a>Passaggio 1: creare una ricerca di contenuto per trovare il messaggio da eliminare

Il primo passaggio consiste nel creare ed eseguire una ricerca di contenuto per trovare il messaggio che si desidera rimuovere dalle cassette postali dell'organizzazione. È possibile creare la ricerca utilizzando il Centro sicurezza &amp; e conformità o eseguendo i cmdlet **New-ComplianceSearch** e **Start-ComplianceSearch** . I messaggi che corrispondono alla query per la ricerca verranno eliminati eseguendo il comando **New-ComplianceSearchAction-Purge** nel [passaggio 3](#step-3-delete-the-message). Per informazioni sulla creazione di una ricerca di contenuto e sulla configurazione delle query di ricerca, vedere i seguenti argomenti: 
  
- [Ricerca contenuto in Office 365](content-search.md)
    
- [Query di parole chiave per la ricerca di contenuto](keyword-queries-and-search-conditions.md)
    
- [New-ComplianceSearch](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/New-ComplianceSearch)
    
- [Start-ComplianceSearch](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/Start-ComplianceSearch)
    
> [!NOTE]
> I percorsi di contenuto che vengono ricercati nella ricerca di contenuto creata in questo passaggio non possono includere siti di SharePoint o OneDrive for business. È possibile includere solo le cassette postali e le cartelle pubbliche in una ricerca di contenuto che verrà utilizzata per i messaggi di posta elettronica. Se la ricerca contenuto include siti, quando si esegue il cmdlet **New-ComplianceSearchAction** verrà visualizzato un messaggio di errore nel passaggio 3. 
  
### <a name="tips-for-finding-messages-to-remove"></a>Suggerimenti per la ricerca di messaggi da rimuovere

L'obiettivo della query di ricerca è limitare i risultati della ricerca solo al messaggio o ai messaggi da rimuovere. Di seguito sono riportati alcuni suggerimenti:
  
- Se si conosce il testo o la frase esatta utilizzata nella riga dell'oggetto del messaggio, utilizzare la proprietà **Subject** nella query di ricerca. 
    
- Se si conosce la data esatta (o l'intervallo di date) del messaggio, includere la proprietà **Received** nella query di ricerca. 
    
- Se si conosce chi ha inviato il messaggio, includere la proprietà **From** nella query di ricerca. 
    
- Visualizzare in anteprima i risultati della ricerca per verificare che la ricerca abbia restituito solo il messaggio (o i messaggi) che si desidera eliminare.
    
- Utilizzare le statistiche delle stime di ricerca (visualizzate nel riquadro dei dettagli della ricerca nel centro &amp; sicurezza e conformità utilizzando il cmdlet [Get-ComplianceSearch](https://go.microsoft.com/fwlink/p/?LinkId=517934) ) per ottenere un conteggio del numero totale di risultati. 
    
Ecco due esempi di query per trovare messaggi di posta elettronica sospetti.
  
- Questa query restituisce i messaggi che sono stati ricevuti dagli utenti tra il 13 aprile 2016 e il 14 aprile 2016 e che contengono le parole "action" e "required" nella riga dell'oggetto.
    
    ```
    (Received:4/13/2016..4/14/2016) AND (Subject:'Action required')
    ```
   
- Questa query restituisce i messaggi che sono stati inviati da chatsuwloginsset12345@outlook.com e che contengono la frase esatta "Update your account information" nella riga dell'oggetto.
    
    ```
    (From:chatsuwloginsset12345@outlook.com) AND (Subject:"Update your account information")
    ```

## <a name="step-2-connect-to-security--compliance-center-powershell"></a>Passaggio 2: connettersi a PowerShell per Centro sicurezza & Compliance

Il passaggio successivo consiste nel connettersi a PowerShell per Centro sicurezza & Compliance per l'organizzazione. Per istruzioni dettagliate, vedere [Connect to Office 365 Security &amp; Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell).
  
Se l'account di Office 365 utilizza l'autenticazione a più fattori (AMF) o l'autenticazione federata, non è possibile utilizzare le istruzioni riportate nell'argomento precedente per la connessione al centro sicurezza & Compliance PowerShell. Vedere le istruzioni riportate nell'argomento [Connect to Office 365 Security _AMP_ Compliance Center PowerShell using multi-factor authentication](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/mfa-connect-to-scc-powershell).
  
## <a name="step-3-delete-the-message"></a>Passaggio 3: eliminare il messaggio

Dopo aver creato e raffinato una ricerca di contenuto per restituire il messaggio che si desidera rimuovere e che sono connessi a PowerShell &amp; per il Centro sicurezza e conformità, il passaggio finale consiste nell'eseguire il cmdlet **New-ComplianceSearchAction** per eliminare il messaggio. È possibile eliminare il messaggio in modo soft o rigido. Un messaggio eliminato temporaneamente viene spostato nella cartella elementi ripristinabili di un utente e mantenuto fino alla scadenza del periodo di conservazione. I messaggi eliminati definitivamente vengono contrassegnati per la rimozione definitiva dalla cassetta postale e verranno rimossi in modo definitivo alla successiva elaborazione della cassetta postale da parte dell'Assistente cartelle gestite. Se il ripristino di un singolo elemento è abilitato per la cassetta postale, gli elementi eliminati in modo definitivo verranno rimossi definitivamente dopo la scadenza del periodo di conservazione degli elementi eliminati. Se una cassetta postale è in attesa, i messaggi eliminati vengono conservati fino alla scadenza della durata del blocco o fino a quando il blocco non viene rimosso dalla cassetta postale.
  
Nell'esempio seguente, il comando eliminerà temporaneamente i risultati della ricerca restituiti da una ricerca di contenuto denominata "Rimuovi messaggio di phishing". 

```
New-ComplianceSearchAction -SearchName "Remove Phishing Message" -Purge -PurgeType SoftDelete
```

Per eliminare definitivamente gli elementi restituiti dalla ricerca del contenuto "Rimuovi messaggio di phishing", eseguire il comando seguente:

```
New-ComplianceSearchAction -SearchName "Remove Phishing Message" -Purge -PurgeType HardDelete
```

Si noti che quando si esegue il comando precedente per eliminare i messaggi in modalità temporanea o con eliminazione definitiva, la ** ricerca specificata dal parametro searchname è la ricerca di contenuto creata nel passaggio 1. 
  
Per ulteriori informazioni, vedere [New-ComplianceSearchAction](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/New-ComplianceSearchAction).

## <a name="more-information"></a>Ulteriori informazioni

- **Come si ottiene lo stato nell'operazione di ricerca e rimozione?**

    Eseguire il comando **Get-ComplianceSearchAction** per ottenere lo stato dell'operazione di eliminazione. Si noti che l'oggetto creato quando si esegue il cmdlet **New-ComplianceSearchAction** è denominato utilizzando questo formato: `<name of Content Search>_Purge`. 
    
- **Cosa succede dopo l'eliminazione di un messaggio?**

   Un messaggio eliminato con il `New-ComplianceSearchAction -Purge -PurgeType HardDelete` comando viene spostato nella cartella Purges e non può essere eseguito dall'utente. Dopo che il messaggio viene spostato nella cartella Purges, il messaggio viene mantenuto per la durata del periodo di conservazione degli elementi eliminati, se il ripristino di un singolo elemento è abilitato per la cassetta postale. In Office 365, il ripristino di un singolo elemento è abilitato per impostazione predefinita al momento della creazione di una nuova cassetta postale. Dopo la scadenza del periodo di conservazione degli elementi eliminati, il messaggio viene contrassegnato per l'eliminazione definitiva e verrà eliminato da Office 365 alla successiva elaborazione della cassetta postale da parte dell'Assistente cartelle gestite. 

   Se si utilizza il `New-ComplianceSearchAction -Purge -PurgeType SoftDelete` comando, i messaggi vengono spostati nella cartella eliminazioni nella cartella elementi ripristinabili dell'utente. Non viene immediatamente eliminato da Office 365. L'utente può recuperare i messaggi nella cartella Posta eliminata per tutta la durata in base al periodo di conservazione degli elementi eliminati configurato per la cassetta postale. Dopo la scadenza del periodo di conservazione (o se l'utente elimina il messaggio prima della scadenza), il messaggio viene spostato nella cartella Purges e non può più essere eseguito dall'utente. Una volta nella cartella Purges, il messaggio viene conservato per la durata in base al periodo di conservazione degli elementi eliminati configurato per la cassetta postale se il ripristino di un singolo elemento è abilitato per la cassetta postale. In Office 365, il ripristino di un singolo elemento è abilitato per impostazione predefinita al momento della creazione di una nuova cassetta postale. Dopo la scadenza del periodo di conservazione degli elementi eliminati, il messaggio viene contrassegnato per l'eliminazione definitiva e verrà eliminato da Office 365 alla successiva elaborazione della cassetta postale da parte dell'Assistente cartelle gestite. 
    
- **Che cosa succede se è necessario eliminare un messaggio da più di 50.000 cassette postali?**

    Come indicato in precedenza, è possibile eseguire un'operazione di ricerca ed eliminazione su un massimo di 50.000 cassette postali. Se è necessario eseguire un'operazione di ricerca ed eliminazione su più di 50.000 cassette postali, prendere in considerazione la possibilità di creare filtri per le autorizzazioni di ricerca temporanea che ridurrebbero il numero di cassette postali che verrebbero cercate in meno di 50.000 cassette postali. Ad esempio, se l'organizzazione contiene cassette postali in diversi reparti, Stati o paesi, è possibile creare un filtro delle autorizzazioni per la ricerca delle cassette postali in base a una di queste proprietà della cassetta postale per eseguire la ricerca in un sottoinsieme di cassette postali nell'organizzazione. Dopo aver creato il filtro delle autorizzazioni di ricerca, è necessario creare la ricerca, descritta nel passaggio 1, quindi eliminare il messaggio (descritto nel passaggio 3). È quindi possibile modificare il filtro per cercare ed eliminare i messaggi in un set di cassette postali diverso. Per ulteriori informazioni sulla creazione di filtri per le autorizzazioni di ricerca, vedere [Configure Permissions Filtering for content search](permissions-filtering-for-content-search.md).
    
- **Gli elementi non indicizzati inclusi nei risultati della ricerca verranno eliminati?**

    No, il comando ' New-ComplianceSearchAction-Purge non elimina gli elementi non indicizzati. 
    
- **Cosa succede se un messaggio viene eliminato da una cassetta postale che è stata inserita in un blocco sul posto o in una conservazione per controversia legale o che è stata assegnata a un criterio di ritenzione di Office 365?**

    Dopo che il messaggio è stato eliminato e spostato nella cartella Purges, il messaggio viene mantenuto fino alla scadenza della durata del blocco. Se la durata del blocco è illimitata, gli elementi vengono mantenuti finché il blocco non viene rimosso o la durata del blocco non viene modificata.
    
- **Perché il flusso di lavoro di ricerca e rimozione è suddiviso tra diversi gruppi di ruoli del centro di sicurezza di & Compliance?**

    Come spiegato in precedenza, una persona deve essere un membro del gruppo di ruoli di eDiscovery Manager o essere assegnato al ruolo di gestione della ricerca di conformità per le cassette postali di ricerca. Per eliminare i messaggi, è necessario che un utente sia membro del gruppo di ruoli Gestione organizzazione o che sia assegnato il ruolo di gestione di ricerca ed eliminazione. In questo modo è possibile controllare gli utenti che possono eseguire ricerche nelle cassette postali nell'organizzazione e gli utenti che possono eliminare i messaggi. 
