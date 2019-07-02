---
title: Controlli di accesso amministrativo in Office 365
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
description: 'Riepilogo: informazioni generali sui controlli di accesso amministrativo e sulla categorizzazione dei dati di Office 365.'
ms.openlocfilehash: 38519fe4e9c05e3468ac3f9f6367c096fb64d195
ms.sourcegitcommit: 7b5e4a7a51f3cdd741deb77a2d60a18e2316618d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/01/2019
ms.locfileid: "33520696"
---
# <a name="administrative-access-controls-in-office-365"></a>Controlli di accesso amministrativo in Office 365 

Microsoft ha investito fortemente nei sistemi e nei controlli che automatizzano la maggior parte delle operazioni di Office 365, limitando intenzionalmente l'accesso ai contenuti dei clienti da Microsoft. Gli esseri umani regolano il servizio e il software gestisce il servizio. Ciò consente a Microsoft di gestire Office 365 in scala e gestire i rischi di minacce interne ai contenuti dei clienti.

Per impostazione predefinita, i tecnici Microsoft non hanno privilegi amministrativi e non hanno accesso ai contenuti dei clienti in Office 365. Un tecnico Microsoft può disporre di un accesso limitato, controllato e protetto al contenuto di un cliente per un periodo di tempo limitato. L'accesso è necessario solo per le operazioni di servizio e solo quando è approvato da un membro di Microsoft Senior Management. Per i clienti con licenza archivio protetto, il cliente fornisce l'approvazione di accesso ai propri contenuti ospitati in Office 365.

Microsoft fornisce servizi online utilizzando più moduli di recapito cloud:

- **Cloud pubblici:** Include versioni multi-tenant di Office 365, Azure e altri servizi ospitati in Nord America, Sud America, Europa, Asia, Australia e così via.
- **Nubi nazionali:** Include tutte le nubi sovrane e di terze parti al di fuori degli Stati Uniti (ad eccezione di quelle riportate in precedenza), come Office 365 in Cina (gestito da 21Vianet) e Office 365 in Germany (gestito da Microsoft, ma in un modello in cui un amministratore di dati tedesco, Deutsche Telekom, controlla e monitora l'accesso di Microsoft ai dati e ai sistemi dei clienti che contengono i dati dei clienti.
- **Cloud governativi:** Include i servizi Office 365 e Azure che sono disponibili per i clienti del governo degli Stati Uniti.

Ai fini di questo articolo, i servizi di Office 365 includono:

- [Exchange Online](https://docs.microsoft.com/Exchange/exchange-online)
- [Exchange Online Protection](https://docs.microsoft.com/Office365/SecurityCompliance/eop/exchange-online-protection-overview)
- [SharePoint Online](https://docs.microsoft.com/sharepoint/sharepoint-online)
- [OneDrive for Business](https://docs.microsoft.com/OneDrive/onedrive)
- [Skype for Business](https://docs.microsoft.com/SkypeForBusiness/skype-for-business-online)
- [Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/Teams-overview)
- [Yammer](https://docs.microsoft.com/yammer/yammer-landing-page)

## <a name="office-365-access-controls"></a>Controlli di accesso di Office 365

Per gli scopi di controllo di accesso, Microsoft categorizza i dati di Office 365 come dati dei clienti o altri tipi di dati.

### <a name="customer-data"></a>Dati cliente


I dati dei clienti sono tutti i dati forniti da o per conto di un cliente quando si utilizzano i servizi di Office 365. Si tratta di contenuti dei clienti creati direttamente o caricati da utenti di Office 365, tra cui:

- Messaggi di posta elettronica
- Contenuto di SharePoint Online
- Messaggi istantanei
- Elementi del calendario
- Documenti
- Contacts
- Informazioni identificabili dall'utente finale (EUII) (dati univoci per un utente o che sono collegabili a un singolo utente ma che non includono il contenuto del cliente).

### <a name="other-types-of-data"></a>Altri tipi di dati

Altri tipi di dati includono:

- **Dati account:** Include i dati amministrativi (informazioni fornite dagli amministratori quando eseguono la registrazione o l'acquisto di servizi) e i dati di pagamento (informazioni sugli strumenti di pagamento, ad esempio i dettagli delle carte di credito).
- **Informazioni identificabili dall'organizzazione:** Include i dati utilizzati per identificare un tenant, i dati di utilizzo e non collegabili a un singolo utente o inclusi nel contenuto del cliente.
- **Metadati di sistema:** Include i registri dei servizi che contengono le impostazioni di configurazione, lo stato del sistema, gli indirizzi IP di Microsoft e le informazioni tecniche sugli abbonamenti e sui tenant.

Microsoft ha stabilito meccanismi di controllo di accesso per garantire che nessuno abbia accesso non autorizzato ai dati dei clienti o ai dati di controllo di accesso. I dati di controllo di accesso gestiscono l'accesso ad altri tipi di dati o funzioni all'interno dell'ambiente, tra cui l'accesso al contenuto del cliente o EUII, le password Microsoft, i certificati di sicurezza e altri dati correlati all'autenticazione. I meccanismi di controllo di accesso proteggono anche dall'accesso fisico, logico o remoto non approvato all'ambiente di produzione di Office 365.

Sono disponibili tre categorie di controlli di accesso utilizzati da Microsoft per l'utilizzo di Office 365:

- Controlli di isolamento
- Controlli del personale
- Controlli di tecnologia

Quando vengono combinati, questi controlli consentono di prevenire e rilevare azioni dannose in Office 365. Oltre ai controlli di isolamento, del personale e della tecnologia utilizzati da Microsoft, esiste una quarta categoria di controlli: quelli implementati dai clienti.

Office 365 consente di gestire i dati allo stesso modo in cui i dati vengono gestiti in ambienti locali. La persona che firma un'organizzazione per Office 365 diventa automaticamente un amministratore globale. L'amministratore globale ha accesso a tutte le funzionalità nei portali di gestione e può:

- Creare o modificare gli utenti
- Assegnare ruoli di amministratore ad altri utenti
- Reimposta password utente
- Gestire le licenze utente
- Gestisci domini
- Approvare le richieste dell'archivio clienti

È consigliabile che ogni organizzazione configuri almeno due account di amministratore. Per le organizzazioni aziendali di grandi dimensioni, è consigliabile disporre di account di amministrazione specializzati che svolgono funzioni diverse.

Per informazioni sull'assegnazione di ruoli e autorizzazioni di amministratore, vedere [assegnazione di ruoli di amministratore in office 365](https://support.office.com/article/Assigning-admin-roles-in-Office-365-eac4d046-1afd-4f1a-85fc-8219c79e1504) e [informazioni sui ruoli di amministratore di Office 365](https://support.office.com/article/Permissions-in-Office-365-DA585EEA-F576-4F55-A1E0-87090B6AAA9D).

## <a name="related-links"></a>Collegamenti correlati

- [Controlli di isolamento](office-365-isolation-controls.md)
- [Controlli del personale](office-365-personnel-controls.md)
- [Controlli di tecnologia](office-365-technology-controls.md)
- [Monitoraggio e controllo dei controlli di accesso ](office-365-monitoring-and-auditing-access-controls.md)
- [Controlli di accesso di Yammer Enterprise](office-365-yammer-enterprise-access-controls.md)