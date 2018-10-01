---
title: Siti del team di SharePoint Online isolati
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/15/2017
ms.audience: ITPro
ms.topic: overview
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom:
- Ent_Solutions
ms.assetid: 71250a04-fd2d-4c3c-a32b-b8a838b19a54
description: 'Sintesi: informazioni sugli utilizzi dei siti del team di SharePoint Online isolati.'
ms.openlocfilehash: 74995273d531ef756ac169491105fb8c8f7eccb5
ms.sourcegitcommit: e0f016aca7befc8806233a492ee916cbe646094f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/27/2018
ms.locfileid: "25345788"
---
# <a name="isolated-sharepoint-online-team-sites"></a>Siti del team di SharePoint Online isolati

 **Sintesi:** informazioni sugli utilizzi dei siti del team di SharePoint Online isolati.
  
I siti del team di SharePoint Online consentono di creare rapidamente uno spazio per la collaborazione a note, documenti, articoli, un calendario e altre risorse in Microsoft Office 365. Un sito del team di SharePoint Online si basa su un gruppo di Office 365 e dispone di un modello di amministrazione semplificato per consentire la collaborazione aperta con un set privato di membri del gruppo o con l'intera organizzazione. Un sito del team SharePoint Online predefinito consente ai membri del gruppo di Office 365 di invitare altri utenti e di tenere sotto controllo le impostazioni delle autorizzazioni.
  
In alcuni casi, tuttavia, si desidera creare un sito del team SharePoint Online per la collaborazione in cui le autorizzazioni del sito siano più controllate tramite l'appartenenza ai gruppi e livelli di autorizzazione SharePoint Online, che vengono gestiti solo dagli amministratori di SharePoint. Si tratta di ciò che viene definito un sito isolato, che è isolato per il set di utenti che collaborano nel sito, che ne visualizzano i contenuti o che lo amministrano. Potrebbe essere necessario un sito isolato nei seguenti casi:
  
- Un progetto segreto all'interno dell'organizzazione.
    
- La posizione di informazioni altamente riservate o di proprietà intellettuale importante.
    
- Le risorse per un'azione legale intrapresa dall'organizzazione o alla quale è soggetta.
    
- Per condividere un abbonamento a Office 365 tra più organizzazioni con alcune sovrapposizioni, ma per la maggior parte esistono entità aziendali separate.
    
Di seguito sono riportati i requisiti di un sito isolato:
  
- Solo gli amministratori di SharePoint Online possono gestire il sito, la cui amministrazione include l'appartenenza ai gruppi per l'accesso al sito e la configurazione di autorizzazioni personalizzate.
    
- I membri del sito non possono invitare altri membri nel sito del team.
    
- Gli utenti che non sono membri del sito isolato non possono richiedere l'accesso al sito. Quando tentano di accedere a qualsiasi URL associato al sito, viene loro negato l'accesso alla pagina Web.
    
Lo svantaggio di richiedere il controllo dell'accesso centralizzato e le autorizzazioni personalizzate dagli amministratori di SharePoint Online è che il sito rimane isolato nel tempo. Ad esempio, i membri correnti non possono, intenzionalmente o accidentalmente, invitare o configurare autorizzazioni personalizzate per altri utenti all'interno dell'abbonamento a Office 365 che non devono essere membri del sito.
  
Un sito isolato può essere usato con altre funzionalità, ad esempio:
  
- Information Rights Management per garantire che le risorse nel sito rimangano crittografate anche se vengono scaricate in locale e caricate in un altro sito disponibile per l'intera organizzazione.
    
- Prevenzione della perdita dei dati per impedire agli utenti di inviare le risorse del sito, come i file, tramite la posta elettronica.
    
## <a name="next-steps"></a>Passaggi successivi

Per provare a usare un sito del team di SharePoint Online isolato in una sottoscrizione di valutazione, vedere le istruzioni dettagliate disponibili in [Sito team di SharePoint Online isolato nell'ambiente di sviluppo e di testing di Office 365](isolated-sharepoint-online-team-site-dev-test-environment.md).
  
Quando si è pronti a distribuire un sito del team di SharePoint Online isolato in produzione, vedere le considerazioni di progettazione dettagliate in [Progettare un sito del team di SharePoint Online isolato](design-an-isolated-sharepoint-online-team-site.md).
  
## <a name="see-also"></a>Vedere anche

[Progettare un sito del team di SharePoint Online isolato](design-an-isolated-sharepoint-online-team-site.md)
  
[Gestire un sito del team di SharePoint Online isolato](manage-an-isolated-sharepoint-online-team-site.md)

[Distribuire un sito del team di SharePoint Online isolato](deploy-an-isolated-sharepoint-online-team-site.md)


