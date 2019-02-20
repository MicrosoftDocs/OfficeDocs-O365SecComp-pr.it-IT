---
title: Aggiornamenti per la sicurezza delle app cloud di Office 365 durante 2017
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.audience: Admin
ms.topic: reference
ms.date: 01/25/2019
ms.service: o365-administration
localization_priority: Normal
description: Vedere cosa è stato rilasciato in 2017 per Office 365 cloud app Security
ms.openlocfilehash: cfc5d9d06c1b2296b82c35fc5fdd6e4bc0deb42b
ms.sourcegitcommit: 8679937354c1d8870ecd41519a59d2d7468c23c4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2019
ms.locfileid: "30087405"
---
# <a name="office-365-cloud-app-security-updates-during-2017"></a>Aggiornamenti per la sicurezza delle app cloud di Office 365 durante 2017
    
## <a name="office-365-cloud-app-security-release-112"></a>Office 365 cloud app Security Release 112

*RiLasciati il 24 dicembre 2017* 
  
**Dopo la [versione di sicurezza di Microsoft Cloud app 112](https://docs.microsoft.com/cloud-app-security/release-notes#cloud-app-security-release-112)**: 
  
- **Cassetto Insight pertinente**. Nel registro attività è ora possibile accedere al cassetto Insight pertinente facendo clic su un nome utente o un indirizzo IP. 
    
    ![Fare clic su un nome utente o un indirizzo IP per visualizzare il cassetto Insight pertinente nel registro attività.](media/8e32b3fa-8c0c-4c5e-b248-fe7d7e1b516d.png)
  
- **Possibilità di visualizzare altre attività con un clic**. Nel cassetto Insight pertinente, è possibile fare clic sull'icona Clock per visualizzare tutte le attività eseguite entro 48 ore dall'attività selezionata. 
    
    ![Nel cassetto Insights pertinente, è possibile fare clic sull'icona Clock per visualizzare le attività eseguite entro 48 ore dall'attività selezionata.](media/c6c96aa0-98e5-4205-8873-45f8d6fd0843.png)
  
- **Miglioramenti dei log parser per Juniper SRX**. Sono stati apportati miglioramenti all'analizzatore del registro di individuazione cloud per Juniper SRX. 
    
## <a name="office-365-cloud-app-security-release-111"></a>Office 365 cloud app Security Release 111

*RiLasciati il 10 dicembre 2017* 
  
**Dopo la [versione di sicurezza di Microsoft Cloud app 111](https://docs.microsoft.com/cloud-app-security/release-notes#cloud-app-security-release-111)**: 
  
- **Miglioramenti**relativi ai filtri temporali. I filtri temporali sono ora più facili da usare. Per accedere a un filtro tempo, in una visualizzazione, ad esempio il registro attività, i criteri, gli avvisi, utilizzando la visualizzazione avanzata, scegliere **Data** nell'elenco dei filtri. Scegliere quindi un'opzione, ad esempio prima, dopo o tra per applicare il filtro tempo. 
    
    ![Utilizzare il filtro data per visualizzare le informazioni prima, dopo o tra date.](media/9dbb2a10-f68f-413b-8b4e-88911152cb92.png)
  
## <a name="office-365-cloud-app-security-release-110"></a>Office 365 cloud app Security Release 110

*RiLasciati il 26 novembre 2017* 
  
**Dopo la [versione di sicurezza di Microsoft Cloud app 110](https://docs.microsoft.com/cloud-app-security/release-notes#cloud-app-security-release-110)**: 
  
- **Integrazione del server Siem ora generalmente disponibile**. Connettere il server SIEM a Office 365 cloud app Security. È ora possibile inviare avvisi e attività automaticamente al server SIEM di scelta configurando gli agenti di SIEM. Vedere [integrare il server Siem con Office 365 cloud app Security](integrate-your-siem-server-with-office-365-cas.md).
    
- **Accesso più facile al contenuto della Guida**. Usando il nuovo punto interrogativo nell'angolo in alto a destra, è ora possibile accedere al contenuto della Guida all'interno delle pagine del portale di protezione delle app di Office 365 cloud. Ogni collegamento è sensibile al contesto, con le informazioni necessarie, in base alla pagina in cui ci si trova. 
    
- **Inviaci commenti e suggerimenti**. Usando la faccina sorridente nell'angolo in alto a destra, è ora possibile inviare commenti e suggerimenti da ogni pagina del portale di Office 365 cloud app Security. In questo modo è possibile segnalare i bug, richiedere nuove funzionalità e condividere la propria esperienza direttamente con il team di sicurezza cloud app di Office 365. 
    
## <a name="office-365-cloud-app-security-release-102"></a>Office 365 cloud app Security Release 102

*RiLasciata il 13 agosto 2017* 
  
**Dopo la [versione di sicurezza di Microsoft Cloud app 102](https://docs.microsoft.com/cloud-app-security/release-notes#cloud-app-security-release-102)**: 
  
- Le **nuove azioni di analisi degli utenti** consentono un ulteriore livello di drill-down alle indagini degli utenti. In una pagina di ricerca è possibile posizionare il puntatore del mouse su un'attività, un utente o un account e applicarla come filtro e da tale pagina è possibile visualizzare attività o eventi correlati. 
    
## <a name="office-365-cloud-app-security-release-100"></a>Office 365 cloud app Security Release 100

*RiLasciati il 17 luglio 2017* 
  
**Dopo la [versione di sicurezza di Microsoft Cloud app 100](https://docs.microsoft.com/cloud-app-security/release-notes#cloud-app-security-release-100)**: 
  
- **Security Extensions** è un nuovo dashboard in cui è possibile gestire in modo centralizzato tutte le estensioni di sicurezza per Office 365 cloud app Security, inclusi i token API e gli agenti Siem. Per visualizzare il Dashboard delle estensioni di sicurezza, eseguire la procedura seguente: 
    
1. Accedere a [https://protection.office.com](https://protection.office.com) e accedere con l'account aziendale o dell'Istituto di istruzione per Office 365. Questo porta al centro sicurezza &amp; e conformità. 
    
2. Passare a **avvisi** \> per la **gestione degli avvisi avanzati**.
    
3. Scegliere **Vai a Office 365 cloud app Security**.
  
4. Scegliere **Settings** \> **Security Extensions**.
    
    ![Nel portale ASM, scegliere Settings \> Security Extensions](media/f03d47a1-91ff-41b9-9baf-b514cffe41a8.png)
  
- **Analisi migliorata**. Sono stati apportati miglioramenti nel meccanismo di analisi del registro di individuazione del cloud. Gli errori interni possono essere significativamente meno probabili. 
    
- **Formati di registro previsti**. Il formato di registro previsto per i registri di individuazione cloud ora fornisce esempi sia per il formato syslog che per il formato FTP. 
    
## <a name="related-topics"></a>Argomenti correlati

[Contenuto della Guida per la protezione delle app cloud di Office 365](office-365-cas-help.md)

[Novità di Office 365 cloud app Security](new-in-office-365-cas.md)
  
[Attività di utilizzo dopo la distribuzione di Office 365 Cloud App Security](utilization-activities-for-ocas.md)

