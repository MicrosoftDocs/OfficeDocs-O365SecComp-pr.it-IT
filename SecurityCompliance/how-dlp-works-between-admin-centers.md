---
title: Funzionamento di DLP tra la sicurezza &amp; centro conformità e l'interfaccia di amministrazione di Exchange
ms.author: stephow
author: stephow-msft
manager: laurawi
ms.date: 8/4/2017
ms.audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: a7e4342a-a0a1-4b43-b166-3d7eecf5d2fd
description: Informazioni su come DLP nella protezione &amp; centro conformità può essere utilizzato con le regole di trasporto e DLP nell'interfaccia di amministrazione di Exchange.
ms.openlocfilehash: bc7494f504c2c0ffa668562d6e64b9f29992e24f
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/27/2018
ms.locfileid: "22531077"
---
# <a name="how-dlp-works-between-the-security-amp-compliance-center-and-exchange-admin-center"></a>Funzionamento di DLP tra la sicurezza &amp; centro conformità e l'interfaccia di amministrazione di Exchange

In Office 365, è possibile creare un criterio di criterio DLP perdita di dati in due diversi admin Center:
  
- Nella **protezione &amp; centro conformità**, è possibile creare un singolo criterio DLP per proteggere il contenuto di SharePoint, OneDrive ed Exchange. Se possibile, è consigliabile creare un criterio DLP. Per ulteriori informazioni, vedere [DLP nella protezione &amp; centro conformità](data-loss-prevention-policies.md).
    
- Nell' **Interfaccia di amministrazione di Exchange**, è possibile creare un criterio DLP per proteggere il contenuto solo in Exchange. Questo criterio è possibile utilizzare le regole di trasporto di Exchange, quindi presenta altre opzioni specifiche per la gestione di posta elettronica. Per ulteriori informazioni, vedere [DLP nell'interfaccia di amministrazione di Exchange](https://go.microsoft.com/fwlink/?linkid=852311).
    
Criteri DLP creati in queste admin Center utilizzare affiancato - questo argomento viene illustrato come.
  
![Pagine DLP in sicurezza e centro conformità e l'interfaccia di amministrazione di Exchange](media/d3eaa7e7-3b16-457b-bd9c-26707f7b584f.png)
  
## <a name="how-dlp-in-the-security-amp-compliance-center-works-with-dlp-and-transport-rules-in-the-exchange-admin-center"></a>Come DLP nella protezione &amp; centro conformità può essere utilizzato con le regole di trasporto e DLP nell'interfaccia di amministrazione di Exchange

Dopo aver creato un criterio DLP per la protezione &amp; centro conformità, il criterio viene distribuito a tutti i percorsi inclusi nel criterio. Se il criterio include Exchange Online, i criteri sono sincronizzati e applicate in esattamente a un criterio DLP creato nell'interfaccia di amministrazione di Exchange. 
  
Se sono state create criteri DLP nell'interfaccia di amministrazione di Exchange, i criteri continuerà a funzionare Affianca tutti i criteri per la posta elettronica creati in sicurezza &amp; centro conformità. Tuttavia, tenere presente che le regole create nell'interfaccia di amministrazione di Exchange hanno la precedenza. Tutte le regole di trasporto di Exchange vengono elaborate prima e quindi il DLP le regole di protezione del &amp; vengono elaborate centro conformità.
  
Ciò significa che:
  
- I messaggi che vengono bloccati dalle regole di trasporto di Exchange non ottenere analizzati dalle regole DLP create in sicurezza &amp; centro conformità.
    
- Se una regola di trasporto di Exchange consente di modificare un messaggio in modo che ne determina la corrispondenza di un criterio DLP per la protezione &amp; centro conformità, ad esempio l'aggiunta di utenti esterni - quindi regole DLP rileva questo e applicare i criteri in base alle esigenze.
    
Anche le regole di nota che le regole di trasporto di Exchange che utilizzano l'azione "arrestare l'elaborazione" non influisce sull'esecuzione di DLP nella protezione &amp; centro conformità - verranno comunque elaborate.
  
## <a name="policy-tips-in-the-security-amp-compliance-center-vs-the-exchange-admin-center"></a>Criteri di suggerimenti per la sicurezza &amp; centro conformità e l'interfaccia di amministrazione di Exchange

Suggerimenti per i criteri possono lavorare con i criteri DLP e create nell'interfaccia di amministrazione di Exchange o con i criteri DLP creati in sicurezza le regole di flusso di posta &amp; centro conformità, ma non entrambi. Ciò avviene perché questi criteri vengono archiviati in percorsi diversi, ma solo da un'unica posizione possa disegnare suggerimenti sui criteri.
  
Se è stato configurato suggerimenti sui criteri nell'interfaccia di amministrazione di Exchange, eventuali suggerimenti sui criteri che consentono di configurare la protezione &amp; centro conformità non viene visualizzato agli utenti in Outlook sul web e Outlook 2013 e versioni successive fino a quando non si disattiva i suggerimenti nell'interfaccia di amministrazione di Exchange. In questo modo che le regole di trasporto di Exchange corrente continuerà a funzionare fino a quando non è possibile passare a sicurezza &amp; centro conformità.
  
Si noti che le notifiche di posta elettronica mentre suggerimenti sui criteri possa disegnare solo da un'unica posizione, sempre inviato, anche se si utilizza criteri DLP in entrambi i Security &amp; centro conformità e l'interfaccia di amministrazione di Exchange.
  

