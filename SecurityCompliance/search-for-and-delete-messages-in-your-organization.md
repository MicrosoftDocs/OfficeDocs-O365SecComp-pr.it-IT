---
title: Cercare ed eliminare messaggi di posta elettronica nell'organizzazione Office 365 - della Guida di amministrazione
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MET150
ms.assetid: 3526fd06-b45f-445b-aed4-5ebd37b3762a
description: Utilizzare la ricerca e funzionalità di Office 365 Security verrà eliminato &amp; centro conformità per cercare ed eliminare un messaggio di posta elettronica da tutte le cassette postali nell'organizzazione.
ms.openlocfilehash: 82ba38ef2c3c8c6b78743a4b2263dde0ef3a5b48
ms.sourcegitcommit: 9034809b6f308bedc3b8ddcca8242586b5c30f94
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/15/2019
ms.locfileid: "28015018"
---
# <a name="search-for-and-delete-email-messages-in-your-office-365-organization---admin-help"></a>Cercare ed eliminare messaggi di posta elettronica nell'organizzazione Office 365 - della Guida di amministrazione

**In questo articolo sia per gli amministratori. Si sta tentando di trovare gli elementi nella cassetta postale che si desidera eliminare. Vedere [trovare un messaggio o un elemento con ricerca immediata](https://support.office.com/article/69748862-5976-47b9-98e8-ed179f1b9e4d)**|
   
È possibile utilizzare la funzionalità di ricerca del contenuto in Office 365 per cercare ed eliminare un messaggio di posta elettronica da tutte le cassette postali nell'organizzazione. Ciò consente di trovare e rimuovere e-mail potenzialmente dannosi o ad alto rischio, ad esempio:
  
- Messaggi che contengono allegati pericolosi o virus
    
- Messaggi di phishing
    
- Messaggi contenenti dati sensibili
    
> [!CAUTION]
> Ricerca ed eliminazione è un'importante funzionalità che consente a chiunque assegnate le autorizzazioni necessarie per eliminare i messaggi di posta elettronica dalle cassette postali nell'organizzazione. 
  
## <a name="before-you-begin"></a>Informazioni preliminari

- Per creare ed eseguire una ricerca di contenuto, è necessario essere membri del gruppo di ruoli di **gestione di eDiscovery** o essere assegnato il ruolo di gestione di **Ricerca di conformità** . Per eliminare i messaggi, è necessario essere membri del gruppo di ruoli **Gestione organizzazione** o essere assegnato il ruolo di gestione **Ricerca e di eliminazione** . Per informazioni sull'aggiunta di utenti a un gruppo di ruoli, vedere [fornire agli utenti di accedere a Office 365 Security &amp; centro conformità](grant-access-to-the-security-and-compliance-center.md).
    
- È necessario utilizzare protezione &amp; PowerShell centro conformità per eliminare i messaggi. Per istruzioni su come connettere, vedere [il passaggio 2](#step-2-connect-to-security-amp-compliance-center-powershell) .
    
- È possibile rimuovere un massimo di 10 elementi per cassette postali alla volta. Dal momento che la funzionalità di ricerca e rimozione dei messaggi deve essere uno strumento di intervento, questo limite consente di garantire che i messaggi vengono rimossi rapidamente dalle cassette postali. Questa funzionalità non è progettata per pulire cassette postali degli utenti. Per eliminare più di 10 elementi, è possibile utilizzare il comando **DeleteContent Search-Mailbox** in Exchange Online PowerShell. Vedere [cercare ed eliminare i messaggi - della Guida di amministrazione](search-for-and-delete-messagesadmin-help.md).
    
- Il numero massimo di cassette postali in una ricerca di contenuto che è possibile eliminare elementi contenuti nel eseguendo una ricerca e azione di eliminazione è 50.000. Se la ricerca del contenuto (creata nel [passaggio 1](#step-1-create-a-content-search-to-find-the-message-to-delete)) ha più di 50.000 cassette postali di origine, l'azione di eliminazione (creato nel passaggio 3) avrà esito negativo. Vedere la sezione [informazioni](#more-information) per un suggerimento su come eseguire una ricerca e sulle cassette postali più di 50.000 operazione di eliminazione. 
    
- La procedura descritta in questo articolo consente solo di eliminazione degli elementi nelle cassette postali di Exchange Online e le cartelle pubbliche. È possibile utilizzare tale per eliminare il contenuto di SharePoint o OneDrive per i siti.
    
## <a name="step-1-create-a-content-search-to-find-the-message-to-delete"></a>Passaggio 1: creare una ricerca di contenuto per trovare il messaggio da eliminare

Il primo passaggio consiste nel creare ed eseguire una ricerca di contenuto per trovare il messaggio che si desidera rimuovere dalle cassette postali nell'organizzazione. È possibile creare la ricerca utilizzando la protezione &amp; centro conformità oppure eseguire i cmdlet **New-ComplianceSearch** e **ComplianceSearch Start** . I messaggi che soddisfano la query per la ricerca verranno eliminati eseguendo il cmdlet **New-ComplianceSearchAction** nel [passaggio 3](#step-3-delete-the-message). Per informazioni sulla creazione di una ricerca di contenuto e la configurazione delle query di ricerca, vedere gli argomenti seguenti: 
  
- [Ricerca del contenuto in Office 365](content-search.md)
    
- [Query con parole chiave per la ricerca del contenuto](keyword-queries-and-search-conditions.md)
    
- [New-ComplianceSearch](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/New-ComplianceSearch)
    
- [Start-ComplianceSearch](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/Start-ComplianceSearch)
    
> [!NOTE]
> I percorsi di contenuti che vengono eseguita la ricerca nella ricerca contenuto creati in questo passaggio non possono includere SharePoint o OneDrive per i siti. È possibile includere solo le cassette postali e cartelle pubbliche in una ricerca di contenuto che verrà utilizzato per i messaggi di posta elettronica. Se la ricerca del contenuto include siti, si riceverà un errore nel passaggio 3 quando si esegue il cmdlet **New-ComplianceSearchAction** . 
  
### <a name="tips-for-finding-messages-to-remove"></a>Suggerimenti per la ricerca dei messaggi da rimuovere

L'obiettivo della query di ricerca è limitare i risultati della ricerca solo al messaggio o ai messaggi da rimuovere. Di seguito sono riportati alcuni suggerimenti:
  
- Se si conosce il testo esatto o una frase utilizzato nella riga dell'oggetto del messaggio, utilizzare la proprietà **Subject** nella query di ricerca. 
    
- Se si conosce la data esatta (o l'intervallo di date) del messaggio, includere la proprietà **Received** nella query di ricerca. 
    
- Se si conosce chi ha inviato il messaggio, includere la proprietà **From** nella query di ricerca. 
    
- Visualizzare in anteprima i risultati della ricerca per verificare che la ricerca restituisca solo il messaggio (o i messaggi) che si desidera eliminare.
    
- Utilizzare le statistiche di ricerca estimate (visualizzati nel riquadro dei dettagli della ricerca per la protezione &amp; centro conformità o utilizzando il cmdlet [Get-ComplianceSearch](https://go.microsoft.com/fwlink/p/?LinkId=517934) ) per ottenere il numero totale dei risultati. 
    
Ecco due esempi di query per trovare messaggi di posta elettronica sospetti.
  
- Questa query restituisce i messaggi che sono stati ricevuti dagli utenti tra il 13 aprile 2016 e il 14 aprile 2016 e che contengono le parole "action" e "required" nella riga dell'oggetto.
    
    ```
    (Received:4/13/2016..4/14/2016) AND (Subject:'Action required')
    ```
   
- Questa query restituisce i messaggi che sono stati inviati da chatsuwloginsset12345@outlook.com e che contengono la frase esatta "Update your account information" nella riga dell'oggetto.
    
    ```
    (From:chatsuwloginsset12345@outlook.com) AND (Subject:"Update your account information")
    ```

## <a name="step-2-connect-to-security-amp-compliance-center-powershell"></a>Passaggio 2: Connettersi a protezione &amp; PowerShell centro conformità

Il passaggio successivo consiste nel connettere alla protezione &amp; PowerShell centro conformità per l'organizzazione. Per istruzioni dettagliate, vedere [Connetti a Office 365 Security &amp; PowerShell centro conformità](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell).
  
Se l'account di Office 365 utilizza l'autenticazione a più fattori (MFA) o l'autenticazione federata, è possibile utilizzare le istruzioni nell'argomento precedente nella connessione alla protezione &amp; PowerShell centro conformità. In realtà, vedere le istruzioni contenute nell'argomento [Connetti a Office 365 Security &amp; PowerShell centro conformità con l'autenticazione a più fattori](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/mfa-connect-to-scc-powershell).
  
## <a name="step-3-delete-the-message"></a>Passaggio 3: Eliminare il messaggio.

Dopo aver creato e affinamento in una ricerca di contenuto per restituire il messaggio che si desidera rimuovere e connessi alla protezione &amp; PowerShell centro conformità, il passaggio finale consiste nell'eseguire il cmdlet **New-ComplianceSearchAction** per eliminare il messaggio. È possibile soft o hard-eliminare il messaggio. Un messaggio di eliminazione reversibile viene spostato nella cartella elementi recuperabili di un utente e conservato fino alla scadenza del periodo di mantenimento elementi eliminati. Eliminata definitivamente i messaggi vengono contrassegnati per la rimozione permanente dalla cassetta postale e verranno rimossa definitivamente la cassetta postale viene elaborato dall'Assistente cartelle gestite. Se il ripristino di singoli elementi è attivato per la cassetta postale, posta eliminata rigido verrà rimossa definitivamente dopo la scadenza del periodo di mantenimento elementi eliminati. Se una cassetta postale viene messa in attesa, i messaggi eliminati vengono conservati fino a quando scade la durata di attesa per l'elemento o la conservazione viene rimosso dalla cassetta postale.
  
Nell'esempio seguente, il comando verrà soft-delete risultati della ricerca restituiti da una ricerca di contenuto denominata "Rimuovere Phishing Message". 

```
New-ComplianceSearchAction -SearchName "Remove Phishing Message" -Purge -PurgeType SoftDelete
```
Nell'esempio seguente, il comando eliminerà disco rigido per i risultati restituiti da una ricerca di contenuto denominata "Rimuovere Phishing Message". 

```
New-ComplianceSearchAction -SearchName "Remove Phishing Message" -Purge -PurgeType HardDelete
```

La ricerca specificata dal parametro *SearchName* è la ricerca del contenuto creato nel passaggio 1. 

Disco rigido-eliminare gli elementi restituiti dalla ricerca di contenuto "Rimuovere Phishing messaggio", eseguire questo comando:

```
New-ComplianceSearchAction -SearchName "Remove Phishing Message" -Purge -PurgeType HardDelete
```
  
Per ulteriori informazioni, vedere [New-ComplianceSearchAction](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/New-ComplianceSearchAction).
  

## <a name="more-information"></a>Ulteriori informazioni

- **Come si ottenere lo stato della ricerca e rimozione operazione?**

    Eseguire **Get-ComplianceSearchAction** per ottenere lo stato dell'operazione di eliminazione. Si noti che l'oggetto che viene creato quando si esegue il cmdlet **New-ComplianceSearchAction** è denominato utilizzando il seguente formato: `<name of Content Search>_Purge`. 
    
- **Cosa succede dopo l'eliminazione di un messaggio?**

   Un messaggio che viene eliminato con la `New-ComplianceSearchAction -Purge -PurgeType HardDelete` comando viene spostato nella cartella Elimina e non è accessibile dall'utente. Dopo che il messaggio viene spostato nella cartella Elimina, il messaggio viene mantenuto per la durata del periodo di mantenimento elementi eliminati se il ripristino di singoli elementi è abilitato per la cassetta postale. (In Office 365, ripristino di singoli elementi è attivato per impostazione predefinita quando si crea una nuova cassetta postale). Dopo la scadenza del periodo di mantenimento elementi eliminati, il messaggio è contrassegnato per l'eliminazione definitiva e verrà eliminato da Office 365 al successivo che alla cassetta postale viene elaborata dall'Assistente cartelle gestite. 

   Se si utilizza il `New-ComplianceSearchAction -Purge -PurgeType SoftDelete` command, i messaggi vengono spostati nella cartella eliminazioni nella cartella elementi ripristinabili dell'utente. È immediatamente non viene eseguita l'eliminazione di Office 365. L'utente può recuperare i messaggi nella cartella Posta eliminata per tutta la durata in base al periodo di mantenimento elementi eliminati configurato per la cassetta postale. Dopo la scadenza del periodo di conservazione o se l'utente elimina il messaggio prima della scadenza, il messaggio viene spostato nella cartella Elimina e non è più accessibile dall'utente. Una volta nella cartella Elimina il messaggio viene mantenuto per la durata in base al periodo di mantenimento elementi eliminati configurato per la cassetta postale se il ripristino di singoli elementi è abilitato per la cassetta postale. (In Office 365, ripristino di singoli elementi è attivato per impostazione predefinita quando si crea una nuova cassetta postale). Dopo la scadenza del periodo di mantenimento elementi eliminati, il messaggio è contrassegnato per l'eliminazione definitiva e verrà eliminato da Office 365 la volta successiva che la cassetta postale viene elaborata dall'Assistente cartelle gestite. 
    
- **Se è necessario eliminare un messaggio da più di 50.000 cassette postali?**

    Come descritto in precedenza, è possibile eseguire una ricerca e cancellare l'operazione su un massimo di 50.000 cassette postali. Se è necessario eseguire una ricerca e sulle cassette postali più di 50.000 operazione di eliminazione, prendere in considerazione la creazione dei filtri di ricerca temporanea autorizzazioni che consentano di ridurre il numero di cassette postali che verrà eseguita la ricerca a meno di 50.000 cassette postali. Ad esempio, se l'organizzazione contiene le cassette postali in diversi reparti, stati o paesi, è possibile creare un filtro di autorizzazioni di ricerca di cassette postali in base a uno di tali proprietà della cassetta postale per la ricerca di un sottoinsieme delle cassette postali nell'organizzazione. Dopo aver creato il filtro di autorizzazioni di ricerca, di creare la ricerca (descritta nel passaggio 1) e quindi Elimina il messaggio (descritto nel passaggio 3). È quindi possibile modificare il filtro per cercare ed eliminare i messaggi in un diverso set di cassette postali. Per ulteriori informazioni sulla creazione dei filtri di ricerca per le autorizzazioni, vedere [configurare autorizzazioni di filtro per la ricerca del contenuto](permissions-filtering-for-content-search.md).
    
- **Verranno eliminati non indicizzati elementi inclusi nei risultati della ricerca?**

    No, la "New-ComplianceSearchAction-comando Cancella non elimina gli elementi indicizzati. 
    
- **Cosa succede se un messaggio viene eliminato da una cassetta postale che è stata inserita nell'archiviazione sul posto o conservazione per controversia legale o assegnata a un criterio di conservazione di Office 365?**

    Dopo il messaggio eliminato e spostato nella cartella Elimina il messaggio viene mantenuto finché non scade la durata dell'attesa. Se la durata di attesa è illimitata, gli elementi vengono conservati fino alla rimozione o viene modificata la durata dell'attesa.
    
- **Perché è la ricerca e rimozione del flusso di lavoro suddiviso tra diversi gruppi di ruoli di sicurezza & centro conformità?**

    Come indicato in precedenza, una persona deve essere un membro del gruppo di ruoli gestione eDiscovery o essere assegnato il ruolo di gestione ricerca conformità per la ricerca di cassette postali. Per eliminare i messaggi, una persona deve essere un membro del gruppo di ruoli Gestione organizzazione o essere assegnato il ruolo di gestione ricerca e di eliminazione. Ciò consente di controllare che possono eseguire ricerche delle cassette postali nell'organizzazione e chi può eliminare i messaggi. 
