---
title: Differenza tra posta elettronica indesiderata e posta elettronica in blocco
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 1/7/2015
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 8079f193-1b40-4081-9e5d-d0e50dfbcc59
description: I clienti talvolta askwhat della differenza tra posta indesiderata e messaggi di posta elettronica in blocco. Lo scopo di questo argomento viene spiegata la differenza e vengono fornite informazioni sulle diverse opzioni disponibili per entrambi in Exchange Online ed Exchange Online Protection (EOP).
ms.openlocfilehash: ea3f27bdd9ec2aa586dd55139825fc90390ca736
ms.sourcegitcommit: b4e69c54c7bf405d37dfeadc5611803bea9554e3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/04/2019
ms.locfileid: "27733302"
---
# <a name="whats-the-difference-between-junk-email-and-bulk-email"></a>Differenza tra posta elettronica indesiderata e posta elettronica in blocco

Talvolta i clienti chiedono quale sia la differenza tra posta elettronica indesiderata e messaggi di posta elettronica in blocco. L'obiettivo di questo argomento è di spiegare la differenza e fornire informazioni sulle diverse opzioni disponibili per entrambi in Exchange Online e Exchange Online Protection (EOP).
  
 **Cos'è la posta elettronica indesiderata**
  
I messaggi di posta elettronica indesiderati sono messaggi di posta indesiderata non richiesti (e di solito non desiderati) che vengono filtrati dal servizio. Per impostazione predefinita, il servizio rifiuta il messaggio in base alla reputazione dell'indirizzo IP di invio. Tuttavia, se supera l'ispezione dell'IP ma viene classificato come posta indesiderata dai filtri del contenuto, il messaggio viene inviato alla cartella Posta indesiderata dei destinatari previsti. 
  
> [!NOTE]
> L'azione eseguita sui messaggi con filtro del contenuto può essere configurata tramite i criteri filtro contenuto nell'interfaccia di amministrazione di Exchange, come descritto in [Configurare i criteri di filtro della posta indesiderata](configure-your-spam-filter-policies.md). Inoltre, se non si è d'accordo con la classificazione della posta indesiderata, è possibile segnalare i messaggi che si considera posta indesiderata o non indesiderata a Microsoft in vari modi, come descritto in [Invio di messaggi di posta indesiderata e non e tentativi di phishing a Microsoft per l'analisi](submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis.md). 
  
 **Cos'è la posta elettronica in blocco**
  
La posta in blocco, altrimenti denominata, posta grigia, è un tipo di messaggio di posta elettronica più difficile da classificare. Mentre la posta elettronica indesiderata è una minaccia costante, la posta elettronica in blocco in genere include un messaggio pubblicitario o di marketing che non viene inviato continuamente. La posta in blocco è desiderata da alcuni utenti, che potrebbero aver sottoscritto intenzionalmente la ricezione di questi messaggi, mentre altri utenti potrebbero considerare come posta indesiderata questo tipo di messaggi. Ad esempio, alcuni utenti desiderano ricevere messaggi di posta elettronica pubblicitari da Contoso Corporation o inviti a una conferenza imminente sulla sicurezza IT, mentre altri utenti considerano posta indesiderata questi messaggi di posta elettronica.
  
## <a name="how-to-manage-bulk-email"></a>Come gestire la posta elettronica in blocco

Il modo in cui gestire la posta elettronica in blocco non è una decisione chiara, in quanto se tutta la posta in blocco viene classificata come spam, gli utenti che invece desiderano riceverla potrebbero reclamare e inviarla come messaggio falso positivo (non di posta indesiderata) erroneamente contrassegnato come posta indesiderata. D'altra parte, se si consente il passaggio di tutta la posta elettronica in blocco, gli utenti che non la desiderano potrebbero reclamare e inviarla come messaggio di posta elettronica indesiderata (falso negativo) arrivato per errore nella propria Posta in arrivo.
  
### <a name="enable-bulk-mail-sensitivity-control-in-the-content-filter-policy"></a>Abilitare il controllo della riservatezza sulla posta inviata in massa nel criterio filtro del contenuto

A seconda dei criteri della società in messaggi di posta elettronica in blocco, gli amministratori possono selezionare una soglia per assegnare il posta elettronica in blocco. L'impostazione è configurabile tramite i criteri di filtro dei contenuti in EAC. Vedere [configurazione dei criteri di filtro posta indesiderata](configure-your-spam-filter-policies.md) per i passaggi. È possibile scegliere un'impostazione di soglia compreso tra 1 e 9, dove 1 Segna la maggior parte delle posta elettronica in blocco come posta indesiderata, e 9 consente di posta elettronica in blocco più possibile recapitare. Il servizio quindi esegue l'azione configurata, ad esempio invia il messaggio nella cartella posta indesiderata del destinatario. 
  

