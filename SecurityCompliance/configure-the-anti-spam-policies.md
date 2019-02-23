---
title: Configurazione di criteri di protezione da posta indesiderata
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.date: 6/9/2015
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 31279431-828d-48bd-b979-20b6de15fa4a
ms.collection:
- M365-security-compliance
description: Il filtro posta inDesiderata viene automaticamente abilitato a livello aziendale tramite i criteri di protezione da posta indesiderata predefiniti (filtro connessioni, filtro posta indesiderata e posta indesiderata in uscita) In qualità di amministratore, è possibile visualizzare e modificare, ma non eliminare, i criteri di protezione da posta indesiderata predefiniti in modo che siano adatti per soddisfare al meglio le esigenze dell'organizzazione. Per una maggiore granularità, è anche possibile creare criteri personalizzati e applicarli a utenti, gruppi o domini specificati nell'organizzazione. Per impostazione predefinita, i criteri personalizzati hanno la precedenza sui criteri predefiniti, ma è possibile modificare la priorità dei criteri.
ms.openlocfilehash: ebd65050fb5a0d3862653e0279ef530fbcabc042
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/23/2019
ms.locfileid: "30215426"
---
# <a name="configure-the-anti-spam-policies"></a>Configurazione di criteri di protezione da posta indesiderata

Il filtro posta inDesiderata viene automaticamente abilitato a livello aziendale tramite i criteri di protezione da posta indesiderata predefiniti (filtro connessioni, filtro posta indesiderata e posta indesiderata in uscita) In qualità di amministratore, è possibile visualizzare e modificare, ma non eliminare, i criteri di protezione da posta indesiderata predefiniti in modo che siano adatti per soddisfare al meglio le esigenze dell'organizzazione. Per una maggiore granularità, è anche possibile creare criteri personalizzati e applicarli a utenti, gruppi o domini specificati nell'organizzazione. Per impostazione predefinita, i criteri personalizzati hanno la precedenza sui criteri predefiniti, ma è possibile modificare la priorità dei criteri. 
  
Per ulteriori informazioni sulla configurazione dei criteri di protezione da posta indesiderata, vedere i seguenti argomenti:
  
[Configurare i criteri di filtro delle connessioni](configure-the-connection-filter-policy.md)
  
[Configurare i criteri di filtro della posta indesiderata](configure-your-spam-filter-policies.md)
  
> [!IMPORTANT]
> Per i clienti EOP indipendenti: per impostazione predefinita, i filtri di contenuto EOP inviano messaggi rilevati dalla posta indesiderata alla cartella Posta indesiderata di ciascun destinatario. Tuttavia, per accertarsi che l'azione **Sposta messaggi nella cartella Posta indesiderata** funzioni con le cassette postali locali, è necessario configurare due regole di Trasporto Exchange nei server locali per rilevare le intestazioni di posta indesiderata aggiunte da EOP. Per ulteriori informazioni, vedere [Verifica del reindirizzamento della posta indesiderata nella cartella Posta indesiderata degli utenti](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md). 
  
[Configurare i criteri della posta indesiderata in uscita](configure-the-outbound-spam-policy.md)
  

