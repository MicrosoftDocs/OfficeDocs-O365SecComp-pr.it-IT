---
title: Progettare un sito del team di SharePoint Online isolato
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/15/2017
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection: Ent_O365
ms.custom: Ent_Solutions
ms.assetid: 775a4e9e-3135-4a48-b32f-bbdd9f2bd0aa
description: 'Sintesi: viene fornita la procedura dettagliata per la progettazione dei siti del team di SharePoint Online isolati.'
ms.openlocfilehash: 19f030f5210fb6742098543ae91117a90d583242
ms.sourcegitcommit: 6122eb026c558a5126c40845e656fbb0c40cb32a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/06/2019
ms.locfileid: "36053123"
---
# <a name="design-an-isolated-sharepoint-online-team-site"></a>Progettare un sito del team di SharePoint Online isolato

 **Sintesi:** viene fornita la procedura dettagliata per la progettazione dei siti del team di SharePoint Online isolati.
  
In questo articolo viene fornita una descrizione dettagliata delle scelte fondamentali relative alla progettazione necessarie prima di creare un sito del team di SharePoint Online isolato.
  
## <a name="phase-1-determine-your-sharepoint-groups-and-permission-levels"></a>Fase 1: determinare i gruppi di SharePoint e i livelli di autorizzazione

Per impostazione predefinita, ogni sito del team di SharePoint Online viene creato con i seguenti gruppi di SharePoint:
  
- \<nome del sito> membri
    
- \<nome del sito> visitatori
    
- \<nome del sito> proprietari
    
Questi gruppi sono separati dai gruppi di Office 365 e Azure Active Directory (AD) e costituiscono la base per l'assegnazione di autorizzazioni per le risorse del sito.
  
Il set di autorizzazioni specifiche che determina le operazioni disponibili per un membro di un gruppo di SharePoint in un sito rappresenta un livello di autorizzazione. Esistono tre livelli di autorizzazione per impostazione predefinita per un sito del team di SharePoint Online: Modifica, Lettura e Controllo completo. Nella tabella seguente vengono illustrati la correlazione predefinita dei gruppi di SharePoint e i livelli di autorizzazione assegnati:
  
|**Gruppo di SharePoint**|**Livello di autorizzazione**|
|:-----|:-----|
|\<nome del sito> membri  <br/> |Modifica  <br/> |
|\<nome del sito> visitatori  <br/> |Lettura  <br/> |
|\<nome del sito> proprietari  <br/> |Controllo completo  <br/> |
   
 **Procedura consigliata:** È possibile creare ulteriori gruppi di SharePoint e livelli di autorizzazione. Tuttavia, è consigliabile usare questi gruppi e livelli di autorizzazione di SharePoint predefiniti per il sito di SharePoint Online isolato.
  
Di seguito sono disponibili i gruppi di SharePoint e i livelli di autorizzazione predefiniti.
  
![I gruppi di SharePoint e i livelli di autorizzazione predefiniti per un sito di SharePoint Online.](media/3f892ab4-6479-42f0-a505-1ba0ef94b9c6.png)
  
## <a name="phase-2-assign-permissions-to-users-with-access-groups"></a>Fase 2: assegnare autorizzazioni agli utenti con i gruppi di accesso

È possibile assegnare autorizzazioni agli utenti aggiungendo il loro account utente (o un gruppo di Office 365 o Azure AD di cui l'account utente è membro) ai gruppi di SharePoint. Al termine di questa operazione, agli account utente di Office 365, direttamente o indirettamente tramite l'appartenenza a un gruppo di Office 365 o Azure AD, viene assegnato il livello di autorizzazione associato al gruppo di SharePoint.
  
Utilizzo di gruppi di SharePoint predefiniti, ad esempio:
  
- I membri del ** \<nome del sito> membri** di gruppo di SharePoint, che possono includere sia gli account utente che i gruppi, vengono assegnati il livello di autorizzazione **modifica** .
    
- Membri del ** \<nome del sito>** gruppo di SharePoint visitatori, che può includere sia gli account utente che i gruppi, viene assegnato il livello di autorizzazione **lettura** .
    
- I membri del ** \<nome del sito> proprietari** del gruppo di SharePoint, che può includere sia gli account utente che i gruppi, vengono assegnati il livello di autorizzazione **controllo completo** .
    
 **Procedura consigliata:** Anche se è possibile gestire le autorizzazioni per singoli account utente, è consigliabile utilizzare un singolo gruppo di Azure AD, noto come gruppo di accesso. In questo modo si semplifica la gestione delle autorizzazioni tramite l'appartenenza al gruppo di accesso, anziché gestire l'elenco di account utente per ogni gruppo di SharePoint.
  
I gruppi di Azure AD per Office 365 sono diversi da quelli di Office 365. I gruppi di Azure AD vengono visualizzati nell'interfaccia di amministrazione di Microsoft 365 con il relativo **tipo** impostato su **sicurezza** e non dispongono di un indirizzo di posta elettronica. I gruppi di Azure AD possono essere gestiti all'interno di:
  
- Servizi di dominio Active Directory (AD DS)
    
    Si tratta di gruppi che sono stati creati nell'infrastruttura di servizi di dominio Active Directory locale e sincronizzati con la sottoscrizione di Office 365. Nell'interfaccia di amministrazione di Microsoft 365, questi gruppi hanno **lo stato** **sincronizzato con Active Directory**.
    
- Office 365
    
    Si tratta di gruppi che sono stati creati utilizzando l'interfaccia di amministrazione di Microsoft 365, il portale di Azure o Microsoft PowerShell. Nell'interfaccia di amministrazione di Microsoft 365, questi gruppi hanno **lo stato** **cloud**.
    
 **Procedura consigliata:** Se si utilizza servizi di dominio Active Directory in locale e si esegue la sincronizzazione con l'abbonamento a Office 365, eseguire la gestione di utenti e gruppi con servizi di dominio Active Directory.
  
Per i siti del team di SharePoint Online isolati, la struttura del gruppo consigliata è simile alla seguente:
  
|**Gruppo di SharePoint**|**Gruppo di accesso basato su Azure AD**|**Livello di autorizzazione**|
|:-----|:-----|:-----|
|\<nome del sito> membri  <br/> |\<nome del sito> membri  <br/> |Modifica  <br/> |
|\<nome del sito> visitatori  <br/> |\<nome del sito> visualizzatori  <br/> |Lettura  <br/> |
|\<nome del sito> proprietari  <br/> |\<nome del sito> amministratori  <br/> |Controllo completo  <br/> |
   
 **Procedura consigliata:** Sebbene sia possibile utilizzare i gruppi di Office 365 o Azure AD come membri dei gruppi di SharePoint, è consigliabile utilizzare i gruppi di Azure AD. I gruppi di Azure AD, gestiti tramite servizi di dominio Active Directory o Office 365, offrono maggiore flessibilità nell'utilizzo dei gruppi nidificati per assegnare le autorizzazioni.
  
Di seguito sono disponibili i gruppi di SharePoint predefiniti configurati per l'utilizzo dei gruppi di accesso basati su Azure AD.
  
![Utilizzo di gruppi di accesso come membri dei gruppi di siti di SharePoint Online predefiniti.](media/50a76328-ae69-483e-9029-ac4e7357b5ef.png)
  
Quando si progettano i tre gruppi di accesso, tenere presente quanto segue:
  
- I membri del gruppo di accesso ** \<> Admins** devono essere presenti solo alcuni utenti, che corrispondono a un numero limitato di amministratori di SharePoint Online che gestiscono il sito del team.
    
- La maggior parte dei membri del sito è presente nel ** \<nome del sito> membri** o ** \<nel nome del sito>** gruppi di accesso dei visualizzatori. Poiché i membri del sito del gruppo di ** \<accesso> membri** del sito hanno la possibilità di eliminare o modificare le risorse nel sito, è opportuno considerare con attenzione la propria appartenenza. In caso di dubbi, aggiungere il membro del sito al gruppo di accesso dei ** \<visualizzatori> nome del sito** .
    
Di seguito è riportato un esempio di gruppi di SharePoint e gruppi di accesso per un sito isolato denominato ProjectX.
  
![Un esempio di utilizzo dei gruppi di accesso per un sito di SharePoint Online denominato ProjectX.](media/13afe542-9ffd-4671-9f48-210a0e2a502a.png)
  
## <a name="phase-3-use-nested-azure-ad-groups"></a>Fase 3: utilizzare i gruppi di Azure AD nidificati

Per un progetto con un numero limitato di persone, un singolo livello di gruppi di accesso basati su Azure AD aggiunti ai gruppi di SharePoint del sito si adatterà alla maggior parte degli scenari. Tuttavia, se si dispone di un numero elevato di persone e quelle persone sono già membri di gruppi di Azure AD stabiliti, è possibile assegnare più facilmente le autorizzazioni di SharePoint utilizzando gruppi nidificati o gruppi che contengono altri gruppi come membri.
  
Ad esempio, si desidera creare un sito del team di SharePoint Online isolato per la collaborazione tra i dirigenti dei reparti delle vendite, marketing, ingegneria, legali e del supporto e tali reparti fanno parte di gruppi di account utente della direzione esecutiva. Anziché creare un nuovo gruppo per i nuovi membri del sito e inserirvi tutti i singoli account utente esecutivi, inserire i gruppi di dirigenti esistenti per ogni reparto nel nuovo gruppo.
  
  Se si condivide un abbonamento a Office 365 tra più organizzazioni, un solo livello di appartenenza ai gruppi per un sito isolato per un'organizzazione potrebbe diventare difficile da gestire a causa del gran numero di account utente. In questo caso, è possibile utilizzare gruppi di Azure AD per ogni organizzazione con i gruppi all'interno delle organizzazioni per gestire le autorizzazioni.
  
Per utilizzare i gruppi di Azure AD nidificati:
  
1. Individuare o creare i gruppi di Azure AD che conterranno gli account utente e aggiungere gli account utente appropriati come membri.
    
2. Creare il gruppo di accesso basato su Azure AD che conterrà gli altri gruppi di Azure AD e aggiungere i gruppi come membri.
    
3.   Per il livello di accesso appropriato per il gruppo di accesso contenitore, individuare il gruppo di SharePoint e il livello di autorizzazione corrispondente.
    
> [!NOTE]
> Non è possibile utilizzare i gruppi di Office 365 nidificati. 
  
Di seguito è riportato un esempio di gruppi di Azure AD nidificati per il gruppo di accesso ai membri di ProjectX.
  
![Un esempio di utilizzo dei gruppi di accesso annidati per il gruppo di accesso dei membri per il sito di ProjectX.](media/2abca710-bf9e-4ce8-9bcd-a8e128264fb1.png)
  
Poiché tutti gli account utente dei lead team di ricerca, ingegneria e progetto sono destinati a essere membri del sito, è più facile aggiungere i propri gruppi di Azure ad al gruppo di accesso dei membri di ProjectX.
  
## <a name="next-step"></a>Passaggio successivo

Quando si è pronti per creare e configurare un sito isolato nell'ambiente di produzione, vedere [Deploy an isolated SharePoint Online team site](deploy-an-isolated-sharepoint-online-team-site.md).
  
## <a name="see-also"></a>Vedere anche

[Siti del team di SharePoint Online isolati](isolated-sharepoint-online-team-sites.md)
  
[Gestire un sito del team di SharePoint Online isolato](manage-an-isolated-sharepoint-online-team-site.md)

[Distribuire un sito del team di SharePoint Online isolato](deploy-an-isolated-sharepoint-online-team-site.md)



