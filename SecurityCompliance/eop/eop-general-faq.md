---
title: Domande frequenti su EOP
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 1/2/2018
ms.audience: ITPro
ms.topic: reference
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
ms.assetid: 9dbff00a-474e-4452-aeb5-5be9a6b8c6d5
description: 'Di seguito vengono riportate le risposte alle domande più frequenti sul servizio di filtro della posta elettronica ospitato su cloud di Microsoft Exchange Online Protection (EOP). Per ulteriori argomenti sulle domande frequenti (FAQ), accedere ai collegamenti seguenti:'
ms.openlocfilehash: 888cf338a3f1767ddd6ba01a2f0f60f2f8794e3e
ms.sourcegitcommit: b688d67935edb036658bb5aa1671328498d5ddd3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2019
ms.locfileid: "30670451"
---
# <a name="eop-general-faq"></a>Domande frequenti su EOP

Di seguito vengono riportate le risposte alle domande più frequenti sul servizio di filtro della posta elettronica ospitato su cloud di Microsoft Exchange Online Protection (EOP). Per ulteriori argomenti sulle domande frequenti (FAQ), accedere ai collegamenti seguenti:
  
- [Domande frequenti sui messaggi restituiti al mittente, differiti e in coda in EOP](eop-queued-deferred-and-bounced-messages-faq.md)
    
- [Domande frequenti sull'amministrazione con delega](delegated-administration-faq.md)
    
- [DOMANDE frequenti sulla protezione da posta indesiderata](../anti-spam-protection-faq.md)
    
- [Elenchi di mittenti attendibili e bloccati in Exchange Online](../safe-sender-and-blocked-sender-lists-faq.md)
    
- [Domande frequenti sulla quarantena](../quarantine-faq.md)
    
- [DOMANDE frequenti sulla protezione anti-malware](../anti-malware-protection-faq-eop.md)
    
- [Message Trace FAQ](http://technet.microsoft.com/library/aa49e3f9-a5b1-4410-aac2-ddbbf3f5bfb2.aspx)
    
- [FOPE to EOP Transition FAQ](http://technet.microsoft.com/library/e0e76b89-b0d3-4c0a-bfc8-137b579e983b.aspx)
    
 **D. Definizione di EOP**
  
R. EOP è un servizio di filtro della posta elettronica ospitato su cloud ideato per proteggere i clienti da posta indesiderata e malware e per implementare le regole criterio personalizzate.
  
 **D. Come iscriversi alla versione di valutazione o alla versione per l'acquisto di EOP.**
  
R. È possibile iscriversi alla versione di valutazione o per l'acquisto di EOP tramite il Web nella [home page di Exchange Online Protection](https://go.microsoft.com/fwlink/p/?LinkId=279912). Le funzionalità di una versione di prova sono uguali a quelle di un abbonamento a pagamento, ma quest'ultimo include anche funzionalità aggiuntive fornite con il piano di abbonamento a [Exchange Enterprise CAL with Services](https://go.microsoft.com/fwlink/p/?LinkId=320619). 
  
 **D. Qual è il prezzo di EOP.**
  
R. EOP richiede una licenza per utente. Per informazioni più recenti sul prezzo, vedere la [home page di Exchange Online Protection](https://go.microsoft.com/fwlink/p/?LinkId=279912).
  
 **D. Tempo stimato per mettere in funzione EOP.**
  
R. Quando vengono modificati il record MX, come evidenziato nella procedura in [Installazione del servizio EOP](set-up-your-eop-service.md), e i flussi di posta tramite EOP, il filtro viene immediatamente avviato. Il record MX potrebbe richiedere dalle 24 alle 48 ore per la propagazione tramite DNS. È possibile ottimizzare le impostazioni di protezione nell'interfaccia amministrativa di Exchange in qualsiasi momento del processo.
  
 **D. È necessario utilizzare tutte le funzionalità di Microsoft Office 365 per utilizzare EOP? È possibile utilizzare solamente la protezione EOP?**
  
R. È possibile utilizzare solamente EOP per proteggere le cassette postali locali senza utilizzare altre funzionalità di Office 365. Questa soluzione è nota come sottoscrizione indipendente. Un elenco di funzionalità EOP è consultabile in [Descrizione del servizio Exchange Online Protection](https://go.microsoft.com/fwlink/p/?LinkId=320619).
  
 **D. Perché è necessario un tenant di Office 365 quando si effettua la registrazione per il filtro di posta elettronica tramite EOP?**
  
R. Office 365 è il nome dato a una raccolta di prodotti e servizi a cui è possibile accedere tramite tenant di Office 365. Pensare al tenant di Office 365 come il punto di inizio a cui aggiungere licenze per il filtro della posta elettronica.
  
 **D. EOP dispone di un portale di comunicazione, nel quale è possibile trovare informazioni su problemi noti e possibili risoluzioni? Le informazioni sulle nuove funzionalità?**
  
R. L'interfaccia di amministrazione di Microsoft 365 avrà alcune di queste informazioni. Se si ha un impatto su un evento di servizio, dovrebbe essere visualizzato un avviso di comunicazione (in genere accompagnato da un'icona del campanello) dopo aver eseguito l'accesso all'interfaccia di amministrazione di Microsoft 365. Si consiglia di leggere e intervenire su tutti gli elementi, come necessario.
  
In relazione alle funzionalità EOP, la [guida a Office 365 for business](https://office.microsoft.com/en-us/products/office-365-roadmap-FX104343353.aspx) è un ottima risorsa per trovare informazioni sulle nuove imminenti funzionalità. Saranno inoltre pubblicati articoli di blog sulle nuova funzionalità sul sito Web [Office Blogs](https://go.microsoft.com/fwlink/p/?LinkId=392724). 
  
 **D. Il servizio funziona con le versioni legacy di Exchange (ad esempio, Exchange Server 2010) e negli ambienti non Exchange?**
  
R. Sì, il servizio è indipendente dal server e può essere utilizzato con qualsiasi agente di trasferimento messaggi SMTP.
  
 **D. Per utilizzare il servizio, quali dimensioni deve avere un'organizzazione?**
  
R. Qualsiasi dimensione. La rete EOP dispone di capacità sufficienti per rispondere alle esigenze di crescita dell'organizzazione, a prescindere dalla velocità di crescita.
  
 **Di quali autorizzazioni ho bisogno per configurare EOP?**
  
Per configurare EOP, l'utente deve essere Amministratore globale di Office 365 o Amministratore aziendale di Exchange (gruppo dei ruoli di gestione dell'organizzazione).
  
 **D. Come è possibile verificare che i dati e le informazioni private siano al sicuro?**
  
R. Per ulteriori informazioni sulla garanzia della sicurezza dei dati e delle informazioni private, incluse le informazioni sui contratti di servizio, vedere [Centro protezione Office 365](https://go.microsoft.com/fwlink/p/?LinkId=285405).
  
 **D. Esistono limiti che devo conoscere, ad esempio limitazioni relative alle dimensioni del messaggio?**
  
Per ulteriori informazioni sui limiti in EOP, vedere [Limiti Exchange Online Protection](https://go.microsoft.com/fwlink/p/?LinkId=402617). 
  
 **D. EOP supporta Windows PowerShell remoto?**
  
A. Sì, tutte le funzionalità EOP sono disponibili tramite Windows PowerShell remoto. Per ulteriori informazioni, vedere [PowerShell in Exchange Online Protection](http://technet.microsoft.com/library/f7918a88-774a-405e-945b-bc2f5ee9f748.aspx).
  

