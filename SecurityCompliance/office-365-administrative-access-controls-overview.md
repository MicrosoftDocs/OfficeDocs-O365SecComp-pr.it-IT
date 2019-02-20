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
ms.collection:
- Strat_O365_IP
- M365-security-compliance
description: 'Riepilogo: informazioni generali sui controlli di accesso amministrativo e sulla categorizzazione dei dati di Office 365.'
ms.openlocfilehash: f5cac8b6161ea7eab6ea390e32caec1c5ddb9bac
ms.sourcegitcommit: c94cb88a9ce5bcc2d3c558f0fcc648519cc264a2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/20/2019
ms.locfileid: "30091027"
---
# <a name="administrative-access-controls-in-office-365"></a>Controlli di accesso amministrativo in Office 365 

## <a name="introduction"></a>Introduzione
Microsoft ha investito pesantemente e di conseguenza nei sistemi e nei controlli che automatizzano la maggior parte delle operazioni di Office 365, limitando intenzionalmente l'accesso di Microsoft al contenuto dei clienti. Gli esseri umani regolano il servizio e il software gestisce il servizio. Ciò consente a Microsoft di gestire Office 365 in scala, oltre a gestire i rischi di minacce interne ai contenuti dei clienti, come gli attori maligni, il Spear-phishing di un tecnico Microsoft e così via.

Per impostazione predefinita, i tecnici Microsoft dispongono di privilegi amministrativi pari a zero e di accesso a zero in piedi ai contenuti dei clienti in Office 365. Un tecnico Microsoft può disporre di un accesso limitato, controllato e protetto al contenuto di un cliente per un periodo di tempo limitato, ma solo se necessario per le operazioni di servizio e solo quando è approvato da un membro di Microsoft Senior Management (e per i clienti che sono concesso in licenza per la funzionalità archivio clienti, il cliente.

Microsoft fornisce servizi online, tra cui Office 365, utilizzando più moduli di recapito cloud:

- **Cloud pubblici** -include versioni multi-tenant di Office 365, Azure e altri servizi ospitati in Nord America, Sud America, Europa, Asia, Australia e così via.
- **Nubi nazionali** -include tutte le nubi sovrane e di terze parti al di fuori degli Stati Uniti (ad eccezione di quelle riportate sopra), come Office 365 in Cina (che è gestito da 21ViaNet) e Office 365 in Germany (che è gestito da Microsoft ma in un modello in cui un amministratore di dati tedesco, Deutsche Telekom, controlla e monitora l'accesso di Microsoft ai dati e ai sistemi dei clienti che contengono i dati dei clienti.
- **Cloud governativi** -include i servizi di Office 365 e Azure disponibili per i clienti del governo degli Stati Uniti.

Ai fini di questo articolo, i servizi di Office 365 includono [Exchange Online](https://docs.microsoft.com/Exchange/exchange-online), [Exchange Online Protection](https://docs.microsoft.com/Office365/SecurityCompliance/eop/exchange-online-protection-overview), [SharePoint Online](https://docs.microsoft.com/sharepoint/sharepoint-online) (tra cui [OneDrive for business](https://docs.microsoft.com/OneDrive/onedrive)) e [Skype for business](https://docs.microsoft.com/SkypeForBusiness/skype-for-business-online), con ulteriori informazioni informazioni su alcuni controlli di accesso di [Yammer Enterprise](https://support.office.com/article/yammer-–-admin-help-e1464355-1f97-49ac-b2aa-dd320b179dbe?ui=en-US&rs=en-US&ad=US) . Gli altri servizi di Office 365 non rientrano nell'ambito di questo articolo.

## <a name="office-365-access-controls"></a>Controlli di accesso di Office 365
Per gli scopi di controllo di accesso, i dati di Office 365 sono categorizzati come dati dei clienti o altri tipi di dati. I dati dei clienti sono tutti i dati forniti da o per conto di un cliente tramite l'utilizzo dei servizi di Office 365 da parte del cliente, ad esempio il contenuto del cliente (contenuto direttamente creato o caricato da utenti di Office 365, inclusi messaggi di posta elettronica, contenuto di SharePoint Online, messaggi istantanei, elementi del calendario, documenti e contatti archiviati in Office 365) e informazioni di identificazione degli utenti finali (EUII) (dati univoci per un utente o che sono collegabili a un singolo utente ma che non includono il contenuto del cliente). 

Altri tipi di dati includono i dati dell'account (inclusi i dati amministrativi, ovvero le informazioni fornite dagli amministratori quando eseguono la registrazione o l'acquisto di servizi e i dati di pagamento, ovvero informazioni sugli strumenti di pagamento, ad esempio i dettagli delle carte di credito) informazioni identificabili dall'organizzazione (dati che possono essere utilizzati per identificare un tenant; o dati di utilizzo; non è collegato a un singolo utente e non include il contenuto del cliente) e metadati di sistema (inclusi i registri dei servizi che contengono le impostazioni di configurazione, stato del sistema, indirizzi IP di Microsoft e informazioni tecniche sugli abbonamenti e sui tenant.

Microsoft ha stabilito meccanismi di controllo di accesso per garantire che nessuno abbia accesso non autorizzato ai dati dei clienti o ai dati di controllo di accesso (utilizzati per gestire l'accesso ad altri tipi di dati o funzioni all'interno dell'ambiente, incluso l'accesso al contenuto del cliente o EUII; it include le password Microsoft, i certificati di sicurezza e altri dati correlati all'autenticazione o l'accesso fisico, logico o remoto non approvato all'ambiente di produzione di Office 365.

I controlli di accesso utilizzati da Microsoft per l'ufficio operativo 365 possono essere raggruppati in tre categorie:
- Controlli di isolamento
- Controlli del personale
- Controlli di tecnologia

Quando vengono combinati, questi controlli consentono di prevenire e rilevare azioni dannose in Office 365. Oltre ai controlli di isolamento, del personale e della tecnologia utilizzati da Microsoft, esiste una quarta categoria di controlli: quelli implementati dai clienti.

Office 365 consente di gestire i dati in modo analogo ai dati gestiti in ambienti locali. La persona che firma un'organizzazione per Office 365 diventa automaticamente un amministratore globale. L'amministratore globale ha accesso a tutte le funzionalità dei portali di gestione (ad esempio, interfaccia di amministrazione e Remote PowerShell) e può creare o modificare gli utenti, assegnare ruoli di amministratore ad altri, reimpostare le password degli utenti, gestire le licenze degli utenti, gestire i domini e approvare l'archivio protetto dei clienti richieste, tra le altre cose. È consigliabile che ogni organizzazione designi almeno due account di amministrazione e, in base alle dimensioni dell'organizzazione, sia necessario designare diversi amministratori che svolgono funzioni diverse. Per informazioni sull'assegnazione di ruoli e autorizzazioni di amministratore, vedere [assegnazione di ruoli di amministratore in office 365](https://support.office.com/article/Assigning-admin-roles-in-Office-365-eac4d046-1afd-4f1a-85fc-8219c79e1504) e [informazioni sui ruoli di amministratore di Office 365](https://support.office.com/article/Permissions-in-Office-365-DA585EEA-F576-4F55-A1E0-87090B6AAA9D).


## <a name="related-links"></a>Collegamenti correlati

- [Controlli di isolamento](office-365-isolation-controls.md)
- [Controlli del personale](office-365-personnel-controls.md)
- [Controlli di tecnologia](office-365-technology-controls.md)
- [Monitoraggio e controllo dei controlli di accesso ](office-365-monitoring-and-auditing-access-controls.md)
- [Controlli di accesso di Yammer Enterprise](office-365-yammer-enterprise-access-controls.md)