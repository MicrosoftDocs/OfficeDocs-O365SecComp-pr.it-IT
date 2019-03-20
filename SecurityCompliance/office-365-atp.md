---
title: Office 365 Advanced Threat Protection
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 03/19/2019
ms.audience: Admin
ms.topic: hub-page
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: e100fe7c-f2a1-4b7d-9e08-622330b83653
ms.collection:
- M365-security-compliance
description: Office 365 Advanced Threat Protection include allegati sicuri, collegamenti sicuri, strumenti avanzati di anti-phishing, strumenti per la creazione di report e funzionalità di minacce di intelligence.
ms.openlocfilehash: ce4652e19f97cda6dbbea7df8083531ee0a0a1fc
ms.sourcegitcommit: 0f93b37c39d807dec91f118aa671a3430c47a9ac
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/20/2019
ms.locfileid: "30693055"
---
# <a name="office-365-advanced-threat-protection"></a>Office 365 Advanced Threat Protection

> [!IMPORTANT]
> Questo articolo è destinato ai clienti di Office 365 Enterprise. Se si utilizza Outlook.com, Office 365 Home o Office 365 Personal e si cercano informazioni sui collegamenti sicuri in Outlook, vedere [Advanced Outlook.com Security](https://support.office.com/article/advanced-outlook-com-security-for-office-365-subscribers-882d2243-eab9-4545-a58a-b36fee4a46e2).

## <a name="overview"></a>Panoramica

Office 365 Advanced Threat Protection (ATP) salvaguarda la propria organizzazione dalle minacce dannose poste da messaggi di posta elettronica, collegamenti (URL) e strumenti di collaborazione. ATP include:

- [Criteri di protezione dalle minacce](#configure-atp-policies): definire i criteri di protezione delle minacce per impostare il livello di protezione appropriato per la propria organizzazione. 

- [Report](#view-atp-reports): visualizzare i report in tempo reale per monitorare le prestazioni ATP nell'organizzazione. 

- [Analisi delle minacce e funzionalità di risposta](#use-threat-investigation-and-response-capabilities): utilizzare gli strumenti principali per esaminare, comprendere, simulare e prevenire le minacce. 
 

## <a name="configure-atp-policies"></a>Configurare i criteri ATP

Office 365 ATP offre numerosi strumenti per impostare un livello di protezione appropriato per la propria organizzazione. 

Il team di sicurezza dell'organizzazione deve definire i criteri per ogni strumento ATP nel centro conformità di Office 365 Security &. Passare a**criteri** di **gestione delle minacce** > per accedere alle opzioni dei criteri. 

I criteri definiti per l'organizzazione determinano il comportamento e il livello di protezione per le minacce predefinite. Le opzioni dei criteri sono estremamente flessibili. Ad esempio, il team di sicurezza dell'organizzazione può impostare una protezione dalle minacce specifiche a livello di utente, organizzazione, destinatario e dominio. È importante esaminare i criteri regolarmente perché emergono giornalmente nuove minacce e sfide.  

- [Allegati sicuri di ATP](atp-safe-attachments.md): fornisce una protezione zero-day per salvaguardare il sistema di messaggistica, controllando gli allegati di posta elettronica per contenuti dannosi. Consente di instradare tutti i messaggi e gli allegati che non dispongono di una firma di virus/malware in un ambiente speciale, quindi utilizza tecniche di apprendimento e analisi del computer per rilevare eventuali intenzioni dannose. Se non viene trovata alcuna attività sospetta, il messaggio viene inoltrato alla cassetta postale. Per ulteriori informazioni, vedere [configurare i criteri per gli allegati sicuri ATP di Office 365](set-up-atp-safe-attachments-policies.md).

- [Collegamenti sicuri ATP](atp-safe-links.md): fornisce la verifica del tempo di clic degli URL nei messaggi di posta elettronica e nei file di Office. La protezione è in uso e si applica all'ambiente di messaggistica e di Office. I collegamenti vengono analizzati per ogni clic: i collegamenti sicuri rimangono accessibili e i collegamenti dannosi vengono bloccati dinamicamente. Per ulteriori informazioni, vedere [configurare i criteri dei collegamenti sicuri ATP di Office 365](https://docs.microsoft.com/en-us/office365/securitycompliance/set-up-atp-safe-links-policies). 

- [ATP per SharePoint, OneDrive e Microsoft teams](atp-for-spo-odb-and-teams.md): protegge l'organizzazione quando gli utenti collaborano e condividono file, identificando e bloccando i file dannosi nei siti del team e nelle raccolte documenti. Per ulteriori informazioni, vedere [accendere Office 365 ATP per SharePoint, OneDrive e Microsoft teams](turn-on-atp-for-spo-odb-and-teams.md). 

- [Protezione anti-phishing ATP](atp-anti-phishing.md): rileva i tentativi di rappresentare gli utenti e i domini personalizzati. Applica i modelli di apprendimento automatico e gli algoritmi avanzati di rilevamento della rappresentazione per evitare attacchi di phishing. Per ulteriori informazioni, vedere [set up Office 365 ATP anti-phishing and anti-phishing Policies](set-up-anti-phishing-policies.md).

## <a name="view-atp-reports"></a>Visualizzare i report di ATP

Office 365 ATP include un [dashboard di Reporting](view-reports-for-atp.md) avanzato che consente di monitorare le prestazioni del trifosfato di adenosina. È possibile accedervi nel **dashboard report di >** nel centro sicurezza & Compliance. 

I report vengono aggiornati in tempo reale, fornendo le informazioni più recenti. Questi rapporti forniscono anche suggerimenti e avvisano l'utente di minacce imminenti. I report predefiniti includono il rapporto [sullo stato di protezione dalle minacce](view-reports-for-atp.md#threat-protection-status-report), il rapporto tipi di [file ATP](view-reports-for-atp.md#atp-file-types-report), il [rapporto disposizione dei messaggi ATP](view-reports-for-atp.md#atp-message-disposition-report) e altro ancora. 

## <a name="use-threat-investigation-and-response-capabilities"></a>Utilizzo delle funzionalità di ricerca e risposta alle minacce

Office 365 ATP Plan 2 include gli [strumenti di risposta e analisi delle minacce](office-365-ti.md) di Best-of-Class che consentono al team di sicurezza dell'organizzazione di anticipare, comprendere e prevenire attacchi dannosi. 

- Gli informatori di [minacce](threat-trackers.md) forniscono le informazioni più recenti sui problemi di Cybersecurity prevalenti. Ad esempio, è possibile visualizzare le informazioni sull'ultimo malware e adottare contromisure prima che diventi una minaccia effettiva per l'organizzazione. Gli inseguitori disponibili includono inseguitori [degni](threat-trackers.md#noteworthy-trackers)di nota, inseguitori di [tendenza](threat-trackers.md#trending-trackers), [query registrate](threat-trackers.md#tracked-queries)e [query salvate](threat-trackers.md#saved-queries).

- [Gestione risorse](use-explorer-in-security-and-compliance.md) (noto anche come Esplora minacce) è un report in tempo reale che consente di identificare e analizzare le minacce recenti. È possibile configurare Esplora risorse per visualizzare i dati per periodi personalizzati.

- [Attack Simulator](attack-simulator.md) consente di eseguire scenari di attacco realistici nell'organizzazione per identificare sia. Sono disponibili simulazioni dei tipi di attacchi correnti, tra cui un [attacco con nome visualizzato Spear-phishing](attack-simulator.md#display-name-spear-phishing-attack), un attacco spray per la [password](attack-simulator.md#password-spray-attack), un attacco con [password con forza bruta](attack-simulator.md#brute-force-password-attack)e altro ancora.
    
## <a name="permissions-required-to-use-atp-features"></a>Autorizzazioni necessarie per utilizzare le funzionalità di ATP

Per accedere alle funzionalità ATP nel centro sicurezza & Compliance, è necessario essere assegnati a un ruolo appropriato. Nella tabella seguente sono inclusi alcuni esempi:

|Ruolo o gruppo di ruoli  |Risorse per ulteriori informazioni  |
|---------|---------|
|Amministratore globale di Office 365 |[Informazioni sui ruoli di amministratore di Office 365](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles)|
|Amministratore della sicurezza |[Autorizzazioni per il ruolo di amministratore in Azure Active Directory](https://docs.microsoft.com/en-us/azure/active-directory/users-groups-roles/directory-assign-admin-roles)|
|Gestione dell'organizzazione di Exchange Online |[Autorizzazioni in Exchange Online](https://docs.microsoft.com/en-us/exchange/permissions-exo/permissions-exo) <br>e<br> [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps)|

Per ulteriori informazioni, vedere:

- [Autorizzazioni nel centro conformità & sicurezza di Office 365](permissions-in-the-security-and-compliance-center.md) 

- [Fornire agli utenti l'accesso al centro conformità & sicurezza di Office 365](grant-access-to-the-security-and-compliance-center.md)

## <a name="get-office-365-atp"></a>Ottenere Office 365 ATP

Office 365 ATP è incluso in Office 365 Enterprise E5, Office 365 Education a5 e Microsoft 365 business. Se l'abbonamento non include Office 365 ATP, è possibile acquistare ATP come componente aggiuntivo. Per ulteriori informazioni, vedere le risorse seguenti:

- Per un elenco degli abbonamenti che includono i piani ATP, vedere [disponibilità di Office 365 Advanced Threat Protection (ATP)](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#office-365-advanced-threat-protection-atp-availability) .

- Vedere la [disponibilità delle funzionalità tra i piani di Advanced Threat Protection (ATP)](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#feature-availability-across-advanced-threat-protection-atp-plans) per un elenco delle funzionalità incluse nel piano 1 e 2.

- Vedere [Get the right office 365 Advanced Threat Protection](https://products.office.com/exchange/advance-threat-protection#pmg-allup-content) per confrontare i piani e acquistare Office 365 ATP.

## <a name="new-features-in-office-365-atp"></a>Nuove funzionalità di Office 365 ATP

Nuove funzionalità vengono aggiunte a Office 365 ATP continuamente. Per ulteriori informazioni, vedere le risorse seguenti:

- Nella [Roadmap di Microsoft 365](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=advanced%2Cthreat%2Cprotection) è disponibile un elenco delle nuove funzionalità di sviluppo e implementazione.

- La [Descrizione del servizio Office 365 Advanced Threat Protection](https://docs.microsoft.com/en-us/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#whats-new-in-office-365-advanced-threat-protection-atp) descrive le caratteristiche e la disponibilità tra i piani ATP.
