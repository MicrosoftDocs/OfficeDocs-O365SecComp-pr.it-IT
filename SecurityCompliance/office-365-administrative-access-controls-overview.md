---
title: Controlli di accesso amministrativo in Office 365
ms.author: robmazz
author: robmazz
manager: laurawi
ms.date: 8/21/2018
audience: ITPro
ms.topic: article
ms.service: Office 365 Administration
localization_priority: None
search.appverid:
- MET150
ms.collection: Strat_O365_Enterprise
description: 'Riepilogo: Panoramica della classificazione dei dati e accedere a controlli amministrativi di Office 365.'
ms.openlocfilehash: afa15d37aa8542985c59dbd9e3d82368421530e8
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/27/2018
ms.locfileid: "22530807"
---
# <a name="administrative-access-controls-in-office-365"></a>Controlli di accesso amministrativo in Office 365 

## <a name="introduction"></a>Introduzione
Microsoft ha profuso fortemente e conseguenza in sistemi e controlli che consentono di automatizzare la maggior parte delle operazioni di Office 365 limitando intenzionalmente access di Microsoft al contenuto dei clienti. Persone governance del servizio e software viene eseguito il servizio. In questo modo Microsoft per gestire Office 365 in scala, nonché di gestire i rischi di minacce interne al contenuto dei clienti, ad esempio gli operatori dannosi, spear-phishing di un tecnico Microsoft e così via.

Per impostazione predefinita, tecnici Microsoft sono pari a zero privilegi amministrativi la condizione e zero la condizione l'accesso al contenuto dei clienti in Office 365. Un tecnico Microsoft può sono limitate, controllate e protetto l'accesso a un cliente contenuto per un periodo limitato di tempo, ma solo quando necessario per le operazioni del servizio e solo quando approvato da un membro di Microsoft senior management (e per i clienti che utilizzano la licenza per la funzionalità archivio protetto cliente, il cliente).

Microsoft offre servizi online, tra cui Office 365, utilizzo di più moduli di consegna cloud:

- **Cloud pubblici** - include le versioni multi-tenant di Office 365, Azure e altri servizi ospitati in Nord America, Sud America, Europe, Asia, Australia e così via.
- **Cloud nazionale** - include tutte le aree sovrani e utilizzati di terze parti di fuori degli Stati Uniti (ad eccezione di quelli sopra riportati), ad esempio Office 365 in cinese (che viene gestito dal 21Vianet) e Office 365 in Germania (che viene gestito da Microsoft, ma in un modello in cui un dominio trusted dati tedesca, Deutsche Telekom, controllo e il monitoraggio access di Microsoft per i dati dei clienti e dei sistemi che contengono i dati dei clienti).
- **Cloud pubblico** - sono inclusi i servizi di Office 365 e Azure disponibili per i clienti governativi degli Stati Uniti.

Ai fini di questo articolo, servizi di Office 365 includono [Exchange Online](https://docs.microsoft.com/Exchange/exchange-online), [Exchange Online Protection](https://docs.microsoft.com/Office365/SecurityCompliance/eop/exchange-online-protection-overview), [SharePoint Online](https://docs.microsoft.com/sharepoint/sharepoint-online) (inclusi [OneDrive for Business](https://docs.microsoft.com/OneDrive/onedrive)) e [Skype per le aziende](https://docs.microsoft.com/SkypeForBusiness/skype-for-business-online), con ulteriori informazioni alcuni controlli di accesso di [Yammer Enterprise](https://support.office.com/article/yammer-–-admin-help-e1464355-1f97-49ac-b2aa-dd320b179dbe?ui=en-US&rs=en-US&ad=US) . Altri servizi di Office 365 rientrano nell'ambito di questo articolo.

## <a name="office-365-access-controls"></a>Controlli di accesso di Office 365
Per il controllo dell'accesso, dati di Office 365 sono categorizzati come i dati dei clienti o altri tipi di dati. I dati dei clienti sono tutti i dati forniti dai o per conto di un cliente mediante l'utilizzo dei servizi di Office 365, ad esempio clienti contenuto di Office (direttamente creati o caricati dagli utenti di Office 365 inclusi messaggi di posta elettronica, SharePoint Online contenuto, i messaggi immediati, calendario gli elementi, documenti e i contatti memorizzati in Office 365) e informazioni personali dell'utente finale (EUII) (dati univoco per un utente o che è collegamento a un singolo utente, ma non includono il contenuto dei clienti). 

Altri tipi di dati includono dati di account (include i dati amministrativi, ovvero le informazioni fornite da parte degli amministratori quando vengono abbonamento o servizi di acquisto e dati di pagamento, che corrisponde a informazioni su strumenti di pagamento, ad esempio credito scheda dettagli), informazioni identificabili (dati che possono essere utilizzati per identificare un tenant; o i dati di utilizzo, non è collegamento a un singolo utente e non include il contenuto dei clienti) e i metadati di sistema (include i registri del servizio che contengono le impostazioni di configurazione lo stato del sistema, gli indirizzi IP di Microsoft e informazioni tecniche sulle sottoscrizioni e tenant).

Microsoft ha stabilito meccanismi di controllo di accesso per assicurarsi che nessuno ha non approvata accesso ai dati di controllo di accesso o i dati dei clienti (utilizzato per gestire l'accesso ad altri tipi di dati o funzioni all'interno dell'ambiente, incluso l'accesso al contenuto dei clienti o EUII; è sono incluse le password Microsoft, i certificati di sicurezza e altri dati relativi all'autenticazione) o non approvato fisico, logico o accesso remoto nell'ambiente di produzione di Office 365.

I controlli di accesso utilizzati da Microsoft per operare in Office 365 possono essere raggruppati in tre categorie:
- Isolamento dei controlli
- Controlli del personale
- Controlli di tecnologia

Quando viene utilizzato, questi controlli consentono di prevenire ed individuare azioni dannose in Office 365. Oltre all'isolamento, personale e controlli tecnologie utilizzati da Microsoft, non esiste una quarta categoria dei controlli: quelle implementate dai clienti.

Office 365 consente di gestire i dati che gran parte agli stessi dati modo in cui viene gestita in ambienti locali. La persona che accede automaticamente backup di un'organizzazione per Office 365 diventa un amministratore globale (admin). Amministratore globale dispone dell'accesso a tutte le funzionalità di portali di gestione, ad esempio, interfacce di amministrazione e PowerShell remoto e può creare o modificare gli utenti, assegnare ruoli amministratore ad altri utenti, reimpostare le password utente, gestire le licenze utente, gestire i domini e approvare archivio protetto cliente richieste, tra l'altro. È consigliabile che ogni organizzazione designare almeno due account di amministrazione e a seconda delle dimensioni dell'organizzazione, è possibile designare diversi agli amministratori che svolgono funzioni differenti. Per informazioni sull'assegnazione delle autorizzazioni e ruoli amministrativi, vedere [assegnazione di ruoli di amministratore in Office 365](https://support.office.com/article/Assigning-admin-roles-in-Office-365-eac4d046-1afd-4f1a-85fc-8219c79e1504) e [ruoli di amministratore su Office 365](https://support.office.com/article/Permissions-in-Office-365-DA585EEA-F576-4F55-A1E0-87090B6AAA9D).


## <a name="related-links"></a>Collegamenti correlati

- [Isolamento dei controlli](office-365-isolation-controls.md)
- [Controlli del personale](office-365-personnel-controls.md)
- [Controlli di tecnologia](office-365-technology-controls.md)
- [Monitoraggio e controllo dei controlli di accesso ](office-365-monitoring-and-auditing-access-controls.md)
- [Controlli di accesso di Yammer Enterprise](office-365-yammer-enterprise-access-controls.md)