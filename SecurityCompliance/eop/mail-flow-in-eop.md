---
title: Flusso di posta in EOP
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 3/13/2015
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: e109077e-cc85-4c19-ae40-d218ac7d0548
description: Come cliente di Exchange Online Protection (EOP), tutti i messaggi inviati all'organizzazione passano attraverso EOP prima che i dipendenti li visualizzino. A prescindere che tutte le cassette postali siano ospitate nel cloud con Exchange Online o siano locali (il cosiddetto scenario autonomo), ad esempio per continuare a sfruttare l'infrastruttura esistente, sono disponibili diverse opzioni di routing dei messaggi che passeranno attraverso EOP per l'elaborazione prima di essere instradati alle cassette postali dei dipendenti.
ms.openlocfilehash: b19db691304efeccfffa245d61f367f7b653739a
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/17/2019
ms.locfileid: "34150178"
---
# <a name="mail-flow-in-eop"></a>Flusso di posta in Exchange Online Protection

Come cliente di Exchange Online Protection (EOP), tutti i messaggi inviati all'organizzazione passano attraverso EOP prima che i dipendenti li visualizzino. A prescindere che tutte le cassette postali siano ospitate nel cloud con Exchange Online o siano locali (il cosiddetto scenario autonomo), ad esempio per continuare a sfruttare l'infrastruttura esistente, sono disponibili diverse opzioni di routing dei messaggi che passeranno attraverso EOP per l'elaborazione prima di essere instradati alle cassette postali dei dipendenti.
  
È possibile configurare il routing della posta personalizzato ai fini della conformità della messaggistica a un requisito aziendale. Ad esempio, è possibile far passare tutta la posta in uscita attraverso l'applicazione di filtro dei criteri di posta. 
  
## <a name="working-with-messages-and-message-access-options"></a>Utilizzo dei messaggi e delle opzioni di accesso ai messaggi

EOP offre molta flessibilità per il routing dei messaggi. Gli argomenti seguenti spiegano i passaggi del processo del flusso di posta.
  
[Use Directory Based Edge Blocking to Reject Messages Sent to Invalid Recipients](http://technet.microsoft.com/library/ca7b7416-92ed-40ad-abdb-695be46ea2e4.aspx) Descrive la funzionalità blocco Edge basato su directory che consente all'utente di rifiutare messaggi per destinatari non validi nel perimetro della rete di servizi. 
  
[View or Edit Managed Domains in EOP](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) descrive come gestire i domini associati al servizio EOP. 
  
Se si aggiungono sottodomini all'organizzazione, il servizio EOP può essere utile nella gestione anche di questi sottodomini. Per ulteriori informazioni sui sottodomini, vedere [Enable Mail Flow for Subdomains in Exchange Online](http://technet.microsoft.com/library/4033a30a-f506-481c-8ef0-fd9a0508ae38.aspx).
  
In [Configure mail flow using connectors in Office 365](http://technet.microsoft.com/library/854b5a50-4462-4836-a092-37e208d29624.aspx) vengono descritti i connettori EOP e come è possibile utilizzarli per personalizzare il routing della posta. Gli scenari includono la verifica relativa alla sicurezza delle comunicazioni con un'organizzazione partner e la configurazione di uno smart host. 
  
Per assicurarsi che la posta indesiderata venga instradata correttamente nella cartella Posta indesiderata di ciascun utente, è necessario eseguire un paio di passaggi per la configurazione. Queste informazioni sono dettagliate [per garantire che la posta indesiderata venga instradata alla cartella posta indesiderata di ogni utente](../ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md). Se non si intende spostare i messaggi nella cartella Posta indesiderata di ciascun utente, è possibile optare per un'altra azione modificando i criteri di filtro dei contenuti nell'interfaccia di amministrazione di Exchange. Per ulteriori informazioni, vedere [Configurare i criteri di filtro della posta indesiderata](../configure-your-spam-filter-policies.md).
  
## <a name="verify-mail-flow"></a>Verificare il flusso di posta

Per verificare che la configurazione EOP, tra cui la configurazione del connettore, funzioni correttamente, vedere la sezione "Come verificare se l'operazione ha avuto esito positivo" in [Installazione del servizio EOP](set-up-your-eop-service.md). 
  
[Test Mail Flow with the Remote Connectivity Analyzer](http://technet.microsoft.com/library/6c8c2964-d553-4329-8166-6e508dd63fa0.aspx) fornisce le istruzioni per la verifica della configurazione corretta del flusso di posta. 
  

