---
title: Ricerca di contenuto in Office 365
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 4/4/2018
ms.audience: Admin
ms.topic: hub-page
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ROBOTS: NOINDEX, NOFOLLOW
ms.assetid: df2d1e0f-b476-42c9-aade-4a260b24f193
description: Utilizzare lo strumento di eDiscovery di ricerca del contenuto in Office 365 Security &amp; centro conformità per trovare rapidamente posta nelle cassette postali di Exchange, i documenti in siti di SharePoint e i percorsi di OneDrive e le conversazioni in Skype per le aziende di messaggistica immediata.
ms.openlocfilehash: b9595f66633cca762ea74eaa9402f50ec08c2d7c
ms.sourcegitcommit: edf5db9357c0d34573f8cc406314525ef10d1eb9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/28/2018
ms.locfileid: "23229978"
---
# <a name="search-for-content-in-office-365"></a>Ricerca di contenuto in Office 365

Utilizzare lo strumento di ricerca del contenuto per la protezione &amp; centro conformità per trovare rapidamente posta nelle cassette postali di Exchange, i documenti in siti di SharePoint e i percorsi di OneDrive e le conversazioni in Skype per le aziende di messaggistica immediata. È possibile utilizzare lo strumento di ricerca del contenuto per la ricerca per la posta elettronica, documenti e le conversazioni in strumenti di collaborazione di Office 365, ad esempio Microsoft Teams e Office 365 gruppi di messaggistica immediata.
  
## <a name="search-for-content"></a>Ricerca dei contenuti

Il primo passaggio consiste nel avvio utilizzando lo strumento di ricerca di contenuti per scegliere i percorsi di contenuti di ricerca e configurare una query con parole chiave ricerca di elementi specifici. In alternativa, è possibile lasciare vuota la query e restituisce tutti gli elementi nei percorsi di destinazione appena.
  
- [Creare ed eseguire](content-search.md) una ricerca di contenuto 
    
- [Creare query di ricerca e utilizzare le condizioni](keyword-queries-and-search-conditions.md) per restringere la ricerca 
    
- [Configurare il filtro autorizzazioni di ricerca](permissions-filtering-for-content-search.md) in modo che un gestore di eDiscovery può effettuare la ricerca solo sottoinsieme dei siti o cassette postali nell'organizzazione 
    
- [Eseguire una ricerca di elenco di ID](csv-file-for-an-id-list-content-search.md) per cercare i messaggi di posta elettronica specifico 
    
- [Cassette postali basate sul cloud di ricerca](search-cloud-based-mailboxes-for-on-premises-users.md) per gli utenti locali in Office 365

- [Visualizzare le statistiche di parola chiave](view-keyword-statistics-for-content-search.md) per i risultati di ricerca e quindi definire la query, se necessario 
    
- [Cercare i dati di terze parti](use-content-search-to-search-third-party-data-that-was-imported.md) che l'organizzazione è stato importato a Office 365 
    
- [Modifica in blocco](bulk-edit-content-searches.md) della query e i percorsi di contenuti per ricerche più 
    
## <a name="perform-actions-on-content-you-find"></a>Eseguire azioni su Trova il contenuto

Dopo avere eseguito una ricerca e modificarlo in base alle esigenze, il passaggio successivo consiste di eseguire un'operazione con i risultati restituiti dalla ricerca. È possibile esportare e scaricare i risultati del computer locale o nel caso di un attacco di posta elettronica nella propria organizzazione, è possibile eliminare i risultati di ricerca di cassette postali degli utenti.
  
- [Esportare i risultati di ricerca di contenuto](export-search-results.md) e scaricarli sul computer locale 
    
- [Cercare ed eliminare i messaggi di posta elettronica](search-for-and-delete-messages-in-your-organization.md) , ad esempio i messaggi che il contenuto di un virus, allegato pericoloso o messaggi di phishing 
    
- [Esportare un report](export-a-content-search-report.md) sui risultati di ricerca di contenuto, senza esportare i risultati effettivi 
    
- [Aumentare la velocità di download](increase-download-speeds-when-exporting-ediscovery-results.md) quando si esportano i risultati della ricerca 
    
## <a name="learn-more-about-content-search"></a>Per ulteriori informazioni sulla ricerca di contenuto

Ricerca del contenuto è facile da usare, ma anche è uno strumento potente. Background, è disponibile una quantità elevata succedendo. Maggiore si conosce su di esso e acquisire familiarità con il relativo comportamento e le relative limitazioni, più efficiente che verranno utilizzate per le esigenze dell'organizzazione di ricerca e indagini. Informazioni su:
  
- [Parzialmente indicizzato elementi di Exchange e SharePoint](partially-indexed-items-in-content-search.md) e su come includere o escludere loro quando si esportano e scaricare i risultati della ricerca 
    
- [Indagare parzialmente voci indicizzate](investigating-partially-indexed-items-in-ediscovery.md) e determinare la visibilità dell'organizzazione a tali 
    
- [Limiti dello strumento di ricerca di contenuto](limits-for-content-search.md), ad esempio il numero massimo di ricerche che è possibile eseguire contemporaneamente e il numero massimo di percorsi di contenuti che è possibile includere in una singola ricerca 
    
- [Stimata e risultati effettivi della ricerca](differences-between-estimated-and-actual-ediscovery-search-results.md) e i motivi perché potrebbero verificarsi le differenze tra di esse quando si esportano e scaricare i risultati della ricerca 
    
- [Deduplicazione nei risultati della ricerca](de-duplication-in-ediscovery-search-results.md) che è possibile abilitare quando si esportano i messaggi di posta elettronica sono i risultati della ricerca 
    
## <a name="use-scripts-for-advanced-scenarios"></a>Utilizzare gli script per scenari avanzati

Talvolta è necessario eseguire attività di ricerca del contenuto più avanzate, complessa e ripetute. In questi casi, è più semplice e veloce per utilizzare i comandi PowerShell la sicurezza &amp; centro conformità. Per facilitare questo, abbiamo creato un numero di sicurezza &amp; script di PowerShell centro conformità che consentono di completare le attività correlate alla ricerca di contenuto complesse.
  
- [Cassetta postale specifica di ricerca e le cartelle del sito](use-content-search-for-targeted-collections.md) (noti come una *raccolta di destinazione* ) quando si è certi che gli elementi risponde a un caso si trovano in tale cartella 
    
- [Ricerca delle cassette postali e la posizione di OneDrive](search-the-mailbox-and-onedrive-for-business-for-a-list-of-users.md) per un elenco di utenti 
    
- [Creare i rapporti ed eliminare ricerche più](create-report-on-and-delete-multiple-content-searches.md) rapido ed efficiente identificare e riforma dati di ricerca 
    
- [Clonare una ricerca di contenuto](clone-a-content-search.md) e confrontare rapidamente i risultati di diverse parole chiave ricerca query eseguite su localizzati stessi contenuti. oppure utilizzare lo script per risparmiare tempo e senza dover immettere di nuovo un numero elevato di percorsi di contenuti quando si crea una nuova ricerca 
    

