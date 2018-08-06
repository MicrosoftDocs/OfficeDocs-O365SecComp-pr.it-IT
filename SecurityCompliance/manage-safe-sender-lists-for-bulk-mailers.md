---
title: Gestire gli elenchi di mittenti attendibili per Mailer di blocco
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 11/17/2014
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
ms.assetid: d48db4a3-9fbe-45e2-bbaa-1017ffdf96f8
description: "Se si desidera utilizzare gli elenchi di mittenti attendibili, è necessario conoscere in cui Exchange Online Protection (EOP) e Outlook gestiscono l'elaborazione in modo diverso. Il servizio supporta i mittenti e domini controllando l'indirizzo 5321.MailFrom RFC e l'indirizzo 5322.From RFC, mentre Outlook consente di aggiungere l'indirizzo 5322.From RFC all'elenco Mittenti attendibili dell'utente. (Nota: il servizio controlla se sia l'indirizzo 5321.MailFrom e 5322.From per domini e mittenti bloccati.)"
ms.openlocfilehash: e5d6f8440281d527e7ea1846416b785beda25f1c
ms.sourcegitcommit: 22bca85c3c6d946083d3784f72e886c068d49f4a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/06/2018
ms.locfileid: "22026543"
---
# <a name="manage-safe-sender-lists-for-bulk-mailers"></a>Gestire gli elenchi di mittenti attendibili per Mailer di blocco

Se si desidera utilizzare gli elenchi di mittenti attendibili, è necessario conoscere in cui Exchange Online Protection (EOP) e Outlook gestiscono l'elaborazione in modo diverso. Il servizio supporta i mittenti e domini controllando l'indirizzo 5321.MailFrom RFC e l'indirizzo 5322.From RFC, mentre Outlook consente di aggiungere l'indirizzo 5322.From RFC all'elenco Mittenti attendibili dell'utente. (Nota: il servizio controlla se sia l'indirizzo 5321.MailFrom e 5322.From per domini e mittenti bloccati.)
  
L'indirizzo SMTP MAIL FROM, noto anche come indirizzo 5321.MailFrom RFC, è l'indirizzo di posta elettronica che viene utilizzato per eseguire le verifiche SPF, e se Impossibile recapitare la posta elettronica, il percorso in cui viene recapitato il messaggio animato. È l'indirizzo di posta elettronica che viene inserito nel percorso di ritorno nelle intestazioni dei messaggi per impostazione predefinita, anche se è possibile che il mittente designare un indirizzo di ritorno percorso diverso.
  
From: indirizzo nelle intestazioni del messaggio, noto anche come indirizzo 5322.From RFC, è l'indirizzo di posta elettronica che viene visualizzato nel client di posta elettronica, ad esempio Outlook.
  
La maggior parte degli indirizzi ora 5321.MailFrom e 5322.From sono gli stessi. Si tratta di una tipica per la comunicazione tra due persone. Tuttavia, quando viene inviata posta elettronica per conto di qualcun altro, gli indirizzi sono diversi frequentemente. Si verifica in genere più frequentemente per i messaggi di posta elettronica in blocco.
  
Ad esempio, si supponga che la compagnia Blue Yonder Airlines ha stipulato fuori viaggi Margie per inviare il relativo annuncio di posta elettronica. Quindi viene visualizzato un messaggio nella posta in arrivo dal mittente blueyonder@news.blueyonderairlines.com. In questo caso, l'indirizzo 5321.MailFrom è blueyonder.airlines@margiestravel.com e blueyonder@news.blueyonderairlines.com corrisponde all'indirizzo 5322.From che corrisponde a quello che viene visualizzato in Outlook. Dal momento che il servizio rispetta l'indirizzo 5322.From RFC, per evitare che il messaggio filtrati, è possibile aggiungere l'indirizzo 5322.From RFC semplicemente come mittente sicuro in Outlook.
  

