---
title: Funzionamento di DLP tra il centro &amp; sicurezza e l'interfaccia di amministrazione di Exchange
ms.author: stephow
author: stephow-msft
manager: laurawi
ms.date: 8/4/2017
ms.audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: a7e4342a-a0a1-4b43-b166-3d7eecf5d2fd
description: Informazioni su come DLP nel centro &amp; sicurezza e conformità funziona con le regole di trasporto e DLP nell'interfaccia di amministrazione di Exchange.
ms.openlocfilehash: 531a45308594d03dc219f50d989a08236b8b5e20
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/23/2019
ms.locfileid: "30215646"
---
# <a name="how-dlp-works-between-the-security-amp-compliance-center-and-exchange-admin-center"></a>Funzionamento di DLP tra il centro &amp; sicurezza e l'interfaccia di amministrazione di Exchange

In Office 365, è possibile creare un criterio di prevenzione della perdita di dati (DLP) in due diversi centri di amministrazione:
  
- Nel **Centro sicurezza &amp; e conformità**, è possibile creare un singolo criterio DLP per proteggere il contenuto in SharePoint, OneDrive ed Exchange. Quando possibile, si consiglia di creare un criterio DLP. Per ulteriori informazioni, vedere [DLP nel centro sicurezza &amp; e conformità](data-loss-prevention-policies.md).
    
- Nell'interfaccia di **amministrazione di Exchange**, è possibile creare un criterio DLP per proteggere il contenuto solo in Exchange. Questo criterio è in grado di utilizzare le regole di trasporto di Exchange, quindi contiene altre opzioni specifiche per la gestione della posta elettronica. Per ulteriori informazioni, vedere [DLP nell'](https://go.microsoft.com/fwlink/?linkid=852311)interfaccia di amministrazione di Exchange.
    
I criteri DLP creati in questi interfaccia di amministrazione sono affiancati-in questo argomento viene descritto come fare.
  
![Pagine DLP in centro sicurezza e conformità e interfaccia di amministrazione di Exchange](media/d3eaa7e7-3b16-457b-bd9c-26707f7b584f.png)
  
## <a name="how-dlp-in-the-security-amp-compliance-center-works-with-dlp-and-transport-rules-in-the-exchange-admin-center"></a>Funzionamento del DLP nel centro &amp; sicurezza e conformità con le regole di trasporto e DLP nell'interfaccia di amministrazione di Exchange

Dopo aver creato un criterio DLP nel centro sicurezza &amp; e conformità, i criteri vengono distribuiti in tutti i percorsi inclusi nel criterio. Se il criterio è incluso in Exchange Online, i criteri vengono sincronizzati e applicati in modo esattamente analogo a quello di un criterio DLP creato nell'interfaccia di amministrazione di Exchange. 
  
Se i criteri DLP sono stati creati nell'interfaccia di amministrazione di Exchange, tali criteri continueranno a funzionare fianco a fianco con qualsiasi criterio per la posta elettronica creato nel &amp; Centro sicurezza e conformità. Tuttavia, tenere presente che le regole create nell'interfaccia di amministrazione di Exchange hanno la precedenza. Tutte le regole di trasporto di Exchange vengono elaborate per prime e quindi vengono elaborate le regole DLP del Centro sicurezza &amp; e conformità.
  
Questo significa che:
  
- I messaggi bloccati dalle regole di trasporto di Exchange non vengono analizzati dalle regole DLP create nel &amp; Centro sicurezza e conformità.
    
- Se una regola di trasporto di Exchange modifica un messaggio in modo che corrisponda a un criterio DLP nel centro sicurezza &amp; e conformità, ad esempio l'aggiunta di utenti esterni, le regole DLP lo rileveranno e implicheranno il criterio in base alle esigenze.
    
Si noti inoltre che le regole di trasporto di Exchange che utilizzano l'azione "Interrompi l'elaborazione" non influiscono sull' &amp; elaborazione delle regole DLP nel centro sicurezza e conformità.
  
## <a name="policy-tips-in-the-security-amp-compliance-center-vs-the-exchange-admin-center"></a>Suggerimenti per i criteri nel &amp; Centro sicurezza e conformità dell'interfaccia di amministrazione di Exchange

I suggerimenti per i criteri possono essere compatibili con i criteri DLP e le regole del flusso di posta creati nell'interfaccia di amministrazione di Exchange oppure &amp; con i criteri DLP creati nel centro sicurezza e conformità, ma non in entrambi. Ciò è dovuto al fatto che questi criteri sono archiviati in posizioni diverse, ma i suggerimenti per i criteri possono essere disegnati solo da una singola posizione.
  
Se sono stati configurati suggerimenti per i criteri nell'interfaccia di amministrazione di Exchange, gli eventuali suggerimenti per &amp; i criteri configurati nel centro sicurezza e conformità non verranno visualizzati in Outlook sul Web e Outlook 2013 e versioni successive finché non si disattivano i suggerimenti nell'interfaccia di amministrazione di Exchange. Questo garantisce che le regole di trasporto di Exchange correnti continueranno a funzionare fino a quando non si sceglie di &amp; passare al centro sicurezza e conformità.
  
Si noti che, mentre i suggerimenti per i criteri possono essere disegnati solo da una singola posizione, le notifiche di posta elettronica vengono sempre inviate, anche &amp; se si utilizzano i criteri DLP sia nel centro conformità sicurezza sia nell'interfaccia di amministrazione di Exchange.
  

