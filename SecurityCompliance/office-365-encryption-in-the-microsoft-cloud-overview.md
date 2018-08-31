---
title: Crittografia nel Microsoft Cloud
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
description: Panoramica di crittografia nel Cloud Microsoft.
ms.openlocfilehash: b8dee7ca7a791878763b885ada40a1d87f074e8e
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/27/2018
ms.locfileid: "22531218"
---
# <a name="encryption-in-the-microsoft-cloud"></a>Crittografia nel Microsoft Cloud

Dati relativi ai clienti all'interno dell'organizzazione servizi cloud di Microsoft è protetto da una vasta gamma di tecnologie e processi, inclusi i vari metodi di crittografia. (Dati dei clienti di office 365 in questo documento includono il contenuto delle cassette postali di Exchange Online (corpo del messaggio di posta elettronica, le voci di calendario e il contenuto degli allegati di posta elettronica e, se applicabile, Skype per il contenuto di Business), il contenuto del sito di SharePoint Online e i file archiviati all'interno siti e i file caricati OneDrive per Business o Skype per le aziende.) Microsoft utilizza più metodi di crittografia, protocolli e cifre tra propri prodotti e servizi per fornire un percorso sicuro per i dati dei clienti di viaggiare attraverso i servizi cloud e proteggere la riservatezza dei dati relativi ai clienti archiviati all'interno i servizi cloud. Microsoft utilizza alcuni dei protocolli di crittografia più sicuro, più sicuro disponibili per fornire le barriere da accessi non autorizzati ai dati dei clienti. Gestione delle chiavi appropriata è anche un elemento essenziale di procedure consigliate di crittografia e Microsoft si impegna che tutte le chiavi di crittografia gestite Microsoft sono protette correttamente.

Indipendentemente dalla configurazione del cliente, i dati dei clienti archiviati all'interno dell'organizzazione servizi cloud di Microsoft sono protetta con uno o più moduli di crittografia. (Convalida i criteri di crittografia e il relativo l'applicazione viene verificata in modo indipendente da più revisori di terze parti e i report delle verifiche sono disponibili nel [Portale di servizi di protezione](https://aka.ms/stp))

Microsoft fornisce tecnologie lato servizio crittografare i dati dei clienti statici e in transito. Ad esempio, per i dati dei clienti statici, viene utilizzato Microsoft Azure [BitLocker](https://docs.microsoft.com/windows/device-security/bitlocker/bitlocker-overview) e [Crittografia DM](https://en.wikipedia.org/wiki/Dm-crypt)e Microsoft Office 365 utilizza servizio BitLocker, [La crittografia del servizio di archiviazione Azure](https://azure.microsoft.com/documentation/articles/storage-service-encryption/), [Gestione chiavi distribuita](https://support.office.com/article/989ba10c-f73f-4efb-ad1b-af3322e5f376) (DKM) e Office 365 crittografia. Per i dati dei clienti in transito, Azure, Office 365, supporto commerciali Microsoft, Microsoft Dynamics 365, Microsoft Power BI e Visual Studio Team Services utilizzano protocolli di trasporto sicuro standard del settore, ad esempio Internet Protocol Security (IPsec) e Sicurezza TLS (Transport Layer), tra Data Center Microsoft e dispositivi utente e datacenter Microsoft.

Oltre a livello di base di sicurezza di crittografia fornito da Microsoft, dei servizi cloud includono inoltre le opzioni di crittografia aggiuntive che è possibile gestire. Ad esempio, è possibile abilitare la crittografia per il traffico tra le macchine virtuali di Azure (VM) e agli utenti. Con [Reti virtuali di Azure](https://azure.microsoft.com/services/virtual-network/), è possibile utilizzare il protocollo IPsec standard del settore per crittografare il traffico tra il gateway VPN aziendale e Azure anche tra le macchine virtuali nella rete virtuale. Inoltre, inoltre, [le nuove funzionalità di Office 365 Message Encryption](set-up-new-message-encryption-capabilities.md) consentono di inviare posta crittografata a tutti gli utenti.

In base alle indicazioni il Public Key dell'infrastruttura operativi protezione Standard, che è un componente del [Criterio di protezione di Microsoft](https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=5868ecc8-50b7-4f91-b43f-640e2b99e86e&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_FAQ%20and%20White%20Papers), Microsoft utilizza le funzionalità incluse nel sistema operativo Windows per i certificati di crittografia e meccanismi di autenticazione, che include l'utilizzo di moduli di crittografia che soddisfano [Federal Information Processing Standards](http://csrc.nist.gov/publications/PubsFIPS.html) (FIPS FEDERAL uniti) standard 140-2. (Numeri certificato NIST pertinenti per Microsoft sono disponibili nelhttp://csrc.nist.gov/groups/STM/cmvp/documents/140-1/1401vend.htm.)

> [NOTA] Per accedere al criterio di sicurezza Microsoft come risorsa, è necessario accedere utilizzando l'account di lavoro o della scuola. Se non si dispone di una sottoscrizione ancora, [è possibile iscriversi per una versione di valutazione gratuita](https://servicetrust.microsoft.com/Home/TrialSubscriptions).

FIPS 140-2 è uno standard progettato appositamente per convalidare i moduli di prodotto che implementano crittografia anziché i prodotti che li utilizzano. Moduli di crittografia implementate all'interno di un servizio possono certificati conformi ai requisiti per la potenza hash, la gestione delle chiavi e così via. Ogni volta che vengono utilizzate funzionalità di crittografia per proteggere la riservatezza, l'integrità o disponibilità dei dati in servizi cloud Microsoft, i moduli e cifre utilizzate soddisfano il FIPS 140-2 standard.

Microsoft dichiara, i moduli di crittografia sottostanti utilizzati in dei servizi cloud ad ogni nuova versione del sistema operativo Windows:
- Azure e Azure governo degli Stati Uniti
- Dynamics 365 US governative e settoriali Dynamics 365
- Office 365, governo di Office 365 degli Stati Uniti e difesa governo di Office 365 degli Stati Uniti

Crittografia dei dati dei clienti di Office 365 statici fornita da più tecnologie di lato del servizio, inclusi BitLocker, DKM, la crittografia del servizio di archiviazione Azure e la crittografia del servizio di Exchange Online, Skype for Business, OneDrive for Business e SharePoint In linea. Crittografia di Office 365 service include un'opzione per utilizzare chiavi di crittografia gestite cliente archiviate in Azure chiave cassaforte. Questa opzione chiave cliente gestiti, denominata [Chiave dei clienti di Office 365](https://support.office.com/article/f2cd475a-e592-46cf-80a3-1bfb0fa17697), è disponibile per Exchange Online, SharePoint Online, di Skype per le aziende e OneDrive for Business.

Per i dati dei clienti in transito, tutti i server di Office 365 negoziano sessioni protette tramite TLS per impostazione predefinita con i computer client per proteggere i dati dei clienti.  Ciò vale per protocolli su qualsiasi dispositivo utilizzato dai client, ad esempio Skype per Business, Outlook e Outlook web, i client mobili e web browser.

(Tutti i server per i clienti la negoziazione per TLS 1.2 per impostazione predefinita, ma è anche supportata la negoziazione verso il basso per uno standard inferiore, se necessario)

## <a name="related-links"></a>Collegamenti correlati

- [Crittografia in Azure](office-365-azure-encryption.md)
- [BitLocker e Distributed Key Manager (DKM) per la crittografia](office-365-bitlocker-and-distributed-key-manager-for-encryption.md)
- [Servizio di crittografia di Office 365](office-365-service-encryption.md)
- [Crittografia di Office 365 per Skype for Business, OneDrive for Business, SharePoint Online ed Exchange Online](office-365-encryption-for-skype-onedrive-sharepoint-and-exchange.md)
- [Crittografia per i dati in transito](office-365-encryption-for-data-in-transit.md)
- [Funzionalità di crittografia gestite dai clienti](office-365-customer-managed-encryption-features.md)
- [Protezione e rischi della crittografa](office-365-encryption-risks-and-protections.md)
- [Crittografia in Microsoft Dynamics 365](office-365-encryption-in-microsoft-dynamics-365.md)