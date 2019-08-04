---
title: Funzionamento di collegamenti sicuri di Office 365 ATP
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: Admin
ms.date: 05/19/2019
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
description: La funzionalità collegamenti sicuri fornisce il tempo di fare clic sulla verifica dei link ipertestuali nei documenti di Office e nei messaggi di posta elettronica. Leggere questo articolo per informazioni su come funzionano i collegamenti sicuri di ATP.
ms.openlocfilehash: 67779560e279028c158179c265196199b5d37d1c
ms.sourcegitcommit: 7c1cb9e8adb1c3e9c667f4cf02ca3cec3ec1e171
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/18/2019
ms.locfileid: "35792042"
---
# <a name="how-office-365-atp-safe-links-works"></a>Funzionamento di collegamenti sicuri di Office 365 ATP
         
## <a name="how-atp-safe-links-works-with-urls-in-email"></a>Funzionamento dei collegamenti sicuri di ATP con gli URL nella posta elettronica

A livello elevato, ecco come funziona la protezione dei [collegamenti sicuri di ATP](atp-safe-links.md) per gli URL nella posta elettronica (ospitati in Office 365, non in locale):
  
1. Gli utenti ricevono messaggi di posta elettronica, alcuni dei quali contengono URL.
    
2. Tutti i messaggi di posta elettronica passano attraverso Exchange Online Protection, dove vengono applicati i filtri Internet (IP) e busta, la protezione antimalware basata sulle firme, i filtri anti-spam e antivirus. 
    
3. La posta elettronica arriva nelle cassette postali degli utenti.
    
4. Un utente accede a Office 365 e passa alla posta in arrivo.
    
5. L'utente apre un messaggio di posta elettronica e fa clic su un URL nel messaggio di posta elettronica.
    
6. La caratteristica collegamenti sicuri ATP verifica immediatamente l'URL prima di aprire il sito Web. L'URL viene identificato come bloccato, dannoso o sicuro.
    
    - Se l'URL è associato a un sito Web incluso in un [elenco di URL personalizzato "non riscrivere"](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md) per un criterio che si applica all'utente, il sito Web verrà aperto. 
    
    - Se l'URL è incluso nell' [elenco degli URL bloccati personalizzati](set-up-a-custom-blocked-urls-list-wtih-atp.md)dell'organizzazione, viene visualizzata una [pagina di avviso](atp-safe-links-warning-pages.md) . 
    
    - Se l'URL è associato a un sito Web che è stato determinato come dannoso, viene visualizzata una [pagina di avviso](atp-safe-links-warning-pages.md) . 
    
    - Se l'URL passa a un file scaricabile e i criteri per i [collegamenti sicuri ATP](set-up-atp-safe-links-policies.md) dell'organizzazione sono configurati per l'analisi di tali contenuti, il file scaricabile viene controllato. 
    
    - Se l'URL è determinato per la sicurezza, il sito Web verrà aperto.
    
## <a name="how-atp-safe-links-works-with-urls-in-office-documents"></a>Funzionamento dei collegamenti sicuri di ATP con gli URL nei documenti di Office

A livello elevato, ecco come funziona la protezione dei [collegamenti sicuri di ATP](atp-safe-links.md) per gli URL nelle applicazioni di ProPlus di Office 365 (versioni correnti di Word, Excel e PowerPoint su Windows o Mac, app di Office su dispositivi iOS o Android, Visio su Windows, OneNote in un browser e Office in un browser):
  
1. Gli utenti hanno installato Office 365 ProPlus nel computer, nello smartphone o nel tablet. (Oppure, utilizzano Office nel browser).
    
2. Un utente apre una parola, Excel, PowerPoint o Visio e accede a Office 365 Enterprise utilizzando l'account aziendale o dell'Istituto di istruzione. Il documento contiene gli URL.
    
3. Quando l'utente fa clic su un URL del documento, il collegamento è controllato dal servizio collegamenti sicuri di ATP.
    
      - Se l'URL è associato a un sito Web incluso in un [elenco di URL personalizzato "non riscrivere"](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md) per un criterio che si applica all'utente, l'utente viene indirizzato al sito Web. 
    
      - Se l'URL è associato a un sito Web incluso nell' [elenco degli URL bloccati personalizzati](set-up-a-custom-blocked-urls-list-wtih-atp.md)dell'organizzazione, l'utente viene indirizzato a una [pagina di avviso](atp-safe-links-warning-pages.md).
    
      - Se l'URL è associato a un sito Web che è stato determinato come dannoso, l'utente viene indirizzato a una [pagina di avviso](atp-safe-links-warning-pages.md).
    
      - Se l'URL passa a un file scaricabile e i [criteri dei collegamenti sicuri di ATP](set-up-atp-safe-links-policies.md) sono configurati per l'analisi di tali download, viene controllato il file scaricabile. 
    
      - Se l'URL è considerato sicuro, l'utente viene reindirizzato al sito Web.

