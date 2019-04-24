---
title: Ricerca di contenuto in Office 365
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 4/4/2018
ms.audience: Admin
ms.topic: hub-page
ms.service: O365-seccomp
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
ms.assetid: df2d1e0f-b476-42c9-aade-4a260b24f193
description: Utilizzare lo strumento eDiscovery ricerca contenuto nel centro sicurezza e conformità & per trovare rapidamente la posta elettronica nelle cassette postali di Exchange, i documenti nei siti di SharePoint e le posizioni OneDrive e le conversazioni di messaggistica istantanea in Skype for business.
ms.openlocfilehash: fc0bea90ce9cbfc27f894985c7d3083756ab108a
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "32261354"
---
# <a name="search-for-content-in-office-365"></a>Ricerca di contenuto in Office 365

Utilizzare lo strumento di ricerca contenuto nel centro sicurezza e conformità di & per trovare rapidamente la posta elettronica nelle cassette postali di Exchange, i documenti nei siti di SharePoint e le posizioni di OneDrive e le conversazioni di messaggistica istantanea in Skype for business. È possibile utilizzare lo strumento di ricerca contenuto per cercare messaggi di posta elettronica, documenti e conversazioni di messaggistica istantanea negli strumenti di collaborazione di Office 365, ad esempio i gruppi di Microsoft teams e Office 365.
  
## <a name="search-for-content"></a>Cercare contenuto

Il primo passaggio consiste nell'iniziare a utilizzare lo strumento di ricerca contenuto per scegliere le posizioni di contenuto per la ricerca e la configurazione di una query di parole chiave per la ricerca di elementi specifici. In alternativa, è possibile lasciare vuota la query e restituire tutti gli elementi nei percorsi di destinazione.
  
- [Creare ed eseguire](content-search.md) una ricerca di contenuto 
    
- [Creare query di ricerca e condizioni di utilizzo](keyword-queries-and-search-conditions.md) per limitare la ricerca 
    
- [Configurare il filtro delle autorizzazioni di ricerca](permissions-filtering-for-content-search.md) in modo che un responsabile di eDiscovery possa cercare solo sottoinsieme di cassette postali o siti nell'organizzazione 
    
- [Eseguire una ricerca nell'elenco di ID](csv-file-for-an-id-list-content-search.md) per cercare messaggi di posta elettronica specifici 
    
- [Cercare le cassette postali basate sul cloud](search-cloud-based-mailboxes-for-on-premises-users.md) per gli utenti locali in Office 365

- [Visualizzare le statistiche sulle parole chiave](view-keyword-statistics-for-content-search.md) per i risultati di una ricerca e quindi affinare la query, se necessario. 
    
- [Ricerca di dati di terze parti](use-content-search-to-search-third-party-data-that-was-imported.md) che l'organizzazione ha importato in Office 365 
    
- [Modifica in blocco](bulk-edit-content-searches.md) delle posizioni di query e del contenuto per più ricerche 
    
- [Preservare i destinatari Ccn](https://docs.microsoft.com/exchange/policy-and-compliance/holds/preserve-bcc-recipients-and-group-members) in modo che sia possibile cercarli 

## <a name="perform-actions-on-content-you-find"></a>Eseguire azioni sul contenuto trovato

Dopo aver eseguito la ricerca e averlo affinato in base alle esigenze, il passaggio successivo consiste nel fare qualcosa con i risultati restituiti dalla ricerca. È possibile esportare e scaricare i risultati nel computer locale o nel caso di un attacco di posta elettronica per l'organizzazione, è possibile eliminare i risultati di una ricerca dalle cassette postali degli utenti.
  
- [Esportare i risultati di una ricerca di contenuto](export-search-results.md) e scaricarli nel computer locale 
    
- [Cercare ed eliminare i messaggi di posta elettronica](search-for-and-delete-messages-in-your-organization.md) , ad esempio messaggi contenenti virus, allegati pericolosi o messaggi di phishing 
    
- [Esportare un report](export-a-content-search-report.md) sui risultati di una ricerca di contenuto, senza esportare i risultati effettivi 
    
- [Aumentare la velocità di download](increase-download-speeds-when-exporting-ediscovery-results.md) quando si esportano i risultati della ricerca 
    
## <a name="learn-more-about-content-search"></a>Ulteriori informazioni sulla ricerca contenuto

La ricerca di contenuti è facile da usare, ma è anche uno strumento potente. Dietro le quinte ci sono molte cose da fare. Maggiore è la conoscenza e la comprensione del comportamento e dei relativi limiti, maggiore è il corretto utilizzo per la ricerca e le esigenze di indagine dell'organizzazione. Informazioni su:
  
- [Elementi parzialmente indicizzati in Exchange e SharePoint](partially-indexed-items-in-content-search.md) e come includerli o escluderli quando si esportano e si scaricano i risultati della ricerca 
    
- [Esaminare gli elementi parzialmente indicizzati](investigating-partially-indexed-items-in-ediscovery.md) e determinare l'esposizione dell'organizzazione all'utente 
    
- [Limiti dello strumento di ricerca del contenuto](limits-for-content-search.md), ad esempio il numero massimo di ricerche che è possibile eseguire in una sola volta e il numero massimo di posizioni di contenuto che è possibile includere in una singola ricerca 
    
- [Risultati della ricerca stimati ed effettivi](differences-between-estimated-and-actual-ediscovery-search-results.md) e i motivi per cui potrebbero esservi differenze quando si esportano e si scaricano i risultati della ricerca 
    
- [Deduplicazione nei risultati della ricerca](de-duplication-in-ediscovery-search-results.md) che è possibile abilitare quando si esportano i messaggi di posta elettronica che sono i risultati di una ricerca 
    
## <a name="use-scripts-for-advanced-scenarios"></a>Utilizzare gli script per gli scenari avanzati

A volte è necessario eseguire attività di ricerca di contenuto più avanzate, complesse e ripetitive. In questi casi, è più semplice e veloce utilizzare i comandi di PowerShell nel centro sicurezza & Compliance. Per semplificare le operazioni, è stato creato un certo numero di script di PowerShell per la sicurezza di & Compliance Center che consentono di completare le attività complesse correlate alla ricerca di contenuto.
  
- [Cartelle di cassette postali e di sito specifiche per la ricerca](use-content-search-for-targeted-collections.md) (denominato *insieme mirato* ) quando si è certi che gli elementi sensibili a un caso siano presenti in tale cartella 
    
- [Eseguire una ricerca nella cassetta postale e nel percorso di OneDrive](search-the-mailbox-and-onedrive-for-business-for-a-list-of-users.md) per un elenco di utenti 
    
- [Creare, segnalare ed eliminare più ricerche](create-report-on-and-delete-multiple-content-searches.md) in modo da identificare e abbattere rapidamente ed efficacemente i dati di ricerca 
    
- [Clonare una ricerca di contenuto](clone-a-content-search.md) e confrontare rapidamente i risultati delle diverse query di ricerca con parole chiave eseguite negli stessi percorsi di contenuto. in alternativa, utilizzare lo script per evitare di dover immettere nuovamente un numero elevato di posizioni di contenuto quando si crea una nuova ricerca 
    

