---
title: Domande frequenti sull'amministrazione delegata
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 8/28/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: d6a87ce8-2c22-433a-b430-5eab14f6afdc
description: In questo argomento vengono riportate le domande frequenti per i partner e rivenditori Microsoft che vogliono eseguire attività di amministrazione delegata in Office 365, quali la possibilità di gestire Exchange Online Protection (EOP) per altri tenant (aziende).
ms.openlocfilehash: 6de70859c7bcb5e735be8f29684c7fcd731f6ed5
ms.sourcegitcommit: 73f1db241c0686020167d43442e7b07a2199ea3a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/28/2019
ms.locfileid: "36658112"
---
# <a name="delegated-administration-faq"></a>Domande frequenti sull'amministrazione delegata

In questo argomento vengono riportate le domande frequenti per i partner e rivenditori Microsoft che vogliono eseguire attività di amministrazione delegata in Office 365, quali la possibilità di gestire Exchange Online Protection (EOP) per altri tenant (aziende).
  
 **D. Sono un rivenditore e devo gestire i tenant del mio cliente. Come posso eseguire questa operazione?**
  
R. Se si è un partner o rivenditore Microsoft e si è iscritti a Microsoft Advisor, è possibile richiedere l'autorizzazione per l'amministrazione del tenant all'interno dell'interfaccia di amministrazione. Questa operazione è nota come amministrazione delegata e consente di gestire il tenant di Office 365 (incluse le impostazioni di EOP) come se si trattasse di un amministratore all'interno della propria organizzazione. Di seguito sono riportati i passaggi per l'esecuzione di un'amministrazione delegata:
  
1. Iscriviti e diventa un [consulente di Microsoft Office 365](https://aka.ms/cloudbenefits).

2. Registrati per eseguire l'amministrazione delegata di Office 365. Prima di iniziare ad amministrare l'account di un cliente, il cliente stesso deve concedere al partner l'autorizzazione di amministratore delegato. Per ricevere la sua approvazione, devi innanzitutto [inviargli un'offerta per l'amministrazione delegata](https://go.microsoft.com/fwlink/?LinkId=396829). (Puoi anche offrire l'amministrazione delegata al cliente in un momento successivo.)

3. Creare l'account amministratore delegato utilizzando la procedura descritta in [aggiungere o eliminare un amministratore delegato](https://go.microsoft.com/fwlink/?LinkId=396831).

Visita [Partner: Sviluppo dell'attività e amministrazione dell'account Office 365](https://go.microsoft.com/fwlink/?LinkId=301485) per ulteriori informazioni su come configurare l'amministrazione delegata di Office 365.
  
 **D. Sono un cliente, non un rivenditore, come posso configurare l'amministratore delegato del mio tenant secondario?**
  
R. Attualmente, l'amministrazione delegata è disponibile soltanto per rivenditori e partner. Tuttavia, forniamo un script di Windows PowerShell di esempio che ti consente di applicare criteri ai tenant secondari (aziende). Per ulteriori informazioni, vedi [Script di esempio per l'applicazione delle impostazioni EOP a più tenant](sample-script-for-applying-eop-settings-to-multiple-tenants.md).
  
 **D. Posso impedire all'amministratore del tenant secondario di modificare i miei criteri?**
  
R. Attualmente, questa funzionalità non è compresa in Office 365.
  
 **D. Posso visualizzare report consolidati in tutti i miei tenant secondari?**
  
R. La creazione di rapporti consolidati tra le società gestite non è disponibile per i report dell'interfaccia di amministrazione di Microsoft 365 in questo momento. Tuttavia, è possibile eseguire questa operazione utilizzando Windows PowerShell remoto o il [servizio Web di Reporting](https://go.microsoft.com/fwlink/?LinkId=279926).
