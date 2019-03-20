---
title: Supporto per la convalida di messaggi firmati con DKIM
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: a4c95148-a00c-4d12-85ed-88520b547d97
ms.collection:
- M365-security-compliance
description: Informazioni sulla convalida dei messaggi firmati di DKIM in Exchange Online Protection ed Exchange Online
ms.openlocfilehash: b1e2af0511c3aa9eb819206aa859ad96e834e3ec
ms.sourcegitcommit: 0f93b37c39d807dec91f118aa671a3430c47a9ac
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/20/2019
ms.locfileid: "30691666"
---
# <a name="support-for-validation-of-dkim-signed-messages"></a>Supporto per la convalida di messaggi firmati con DKIM

Exchange Online Protection (EOP) ed Exchange Online supportano la convalida in ingresso di messaggi Domain Keys Identified Mail ([DKIM](https://www.rfc-editor.org/rfc/rfc6376.txt)). DKIM è un metodo per confermare che il messaggio è stato inviato dal dominio di origine dichiarato e che non è stato soggetto a spoofing da parte di altri. Collega una messaggio di posta elettronica all'organizzazione che lo ha inviato. La verifica DKIM viene utilizzata automaticamente per tutti i messaggi inviati tramite comunicazioni IPv6. Per ulteriori informazioni sul supporto di IPv6, vedere [Supporto per messaggi di posta elettronica in ingresso anonimi su IPv6](support-for-anonymous-inbound-email-messages-over-ipv6.md).
  
DKIM convalida un messaggio con firma digitale visualizzato nell'intestazione DKIM-Signature nelle intestazioni del messaggio. I risultati di una convalida DKIM-Signature vengono inseriti nell'intestazione Authentication-Results, che è conforme a RFC 7001 ([Message Header Field for Indicating Message Authentication Status](https://www.rfc-editor.org/rfc/rfc7001.txt)). Il testo dell'intestazione del messaggio è simile al seguente (dove contoso.com è il mittente):
  
 `Authentication-Results: <contoso.com>; dkim=pass (signature was verified) header.d=example.com;`
  
Gli amministratori possono creare [regole del flusso di posta](http://technet.microsoft.com/library/743bd525-0ca2-426d-b76c-b4a052bc8886.aspx) di Exchange (note anche come regole di trasporto) sui risultati di una convalida DKIM per filtrare o instradare i messaggi in base alle esigenze. 
  

