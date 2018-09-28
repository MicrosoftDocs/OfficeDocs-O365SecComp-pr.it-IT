---
title: Progettare un sito del team di SharePoint Online isolato
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/15/2017
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
search.appverid:
- MET150
ms.collection: Ent_O365
ms.custom: Ent_Solutions
ms.assetid: 775a4e9e-3135-4a48-b32f-bbdd9f2bd0aa
description: 'Sintesi: viene fornita la procedura dettagliata per la progettazione dei siti del team di SharePoint Online isolati.'
ms.openlocfilehash: bd36044eb16b9f6ee3ee9bbb444fe8f4efe2fd63
ms.sourcegitcommit: e0f016aca7befc8806233a492ee916cbe646094f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/27/2018
ms.locfileid: "25345808"
---
# <a name="design-an-isolated-sharepoint-online-team-site"></a>Progettare un sito del team di SharePoint Online isolato

 **Sintesi:** viene fornita la procedura dettagliata per la progettazione dei siti del team di SharePoint Online isolati.
  
In questo articolo viene fornita una descrizione dettagliata delle scelte fondamentali relative alla progettazione necessarie prima di creare un sito del team di SharePoint Online isolato.
  
## <a name="phase-1-determine-your-sharepoint-groups-and-permission-levels"></a>Fase 1: determinare i gruppi di SharePoint e i livelli di autorizzazione

Per impostazione predefinita, ogni sito del team di SharePoint Online viene creato con i seguenti gruppi di SharePoint:
  
- \<nome del sito > membri
    
- \<nome del sito > visitatori
    
- \<nome del sito > proprietari
    
Questi gruppi sono separati dai gruppi di Office 365 e Azure Active Directory (AD) e costituiscono la base per l'assegnazione di autorizzazioni per le risorse del sito.
  
Il set di autorizzazioni specifiche che determina le operazioni disponibili per un membro di un gruppo di SharePoint in un sito rappresenta un livello di autorizzazione. Esistono tre livelli di autorizzazione per impostazione predefinita per un sito del team di SharePoint Online: Modifica, Lettura e Controllo completo. Nella tabella seguente vengono illustrati la correlazione predefinita dei gruppi di SharePoint e i livelli di autorizzazione assegnati:
  
|**Gruppo di SharePoint**|**Livello di autorizzazione**|
|:-----|:-----|
|\<nome del sito > membri  <br/> |Modifica  <br/> |
|\<nome del sito > visitatori  <br/> |Lettura  <br/> |
|\<nome del sito > proprietari  <br/> |Controllo completo  <br/> |
   
 **Procedura consigliata:** È possibile creare ulteriori gruppi di SharePoint e livelli di autorizzazione. Tuttavia, è consigliabile usare questi gruppi e livelli di autorizzazione di SharePoint predefiniti per il sito di SharePoint Online isolato.
  
Di seguito sono i gruppi di SharePoint predefiniti e i livelli di autorizzazione.
  
![I gruppi e livelli di autorizzazione di SharePoint predefiniti per il sito di SharePoint Online.](media/3f892ab4-6479-42f0-a505-1ba0ef94b9c6.png)
  
## <a name="phase-2-assign-permissions-to-users-with-access-groups"></a>Fase 2: assegnare autorizzazioni agli utenti con i gruppi di accesso

È possibile assegnare autorizzazioni agli utenti aggiungendo il loro account utente (o un gruppo di Office 365 o Azure AD di cui l'account utente è membro) ai gruppi di SharePoint. Al termine di questa operazione, agli account utente di Office 365, direttamente o indirettamente tramite l'appartenenza a un gruppo di Office 365 o Azure AD, viene assegnato il livello di autorizzazione associato al gruppo di SharePoint.
  
Utilizzo di gruppi di SharePoint predefiniti, ad esempio:
  
- Membri del ** \<nome del sito > membri** gruppo di SharePoint, che può includere sia gli account utente e gruppi, viene assegnato il livello di autorizzazione **Modifica**
    
- Membri del ** \<nome del sito > visitatori** gruppo di SharePoint, che può includere sia gli account utente e gruppi, viene assegnato il livello di autorizzazione di **lettura**
    
- Membri del ** \<nome del sito > proprietari** gruppo di SharePoint, che può includere sia gli account utente e gruppi, viene assegnato il livello di autorizzazione **controllo completo**
    
 **Procedura consigliata:** Anche se è possibile gestire le autorizzazioni per singoli account utente, è consigliabile utilizzare un singolo gruppo di Azure AD, noto come gruppo di accesso. In questo modo si semplifica la gestione delle autorizzazioni tramite l'appartenenza al gruppo di accesso, anziché gestire l'elenco di account utente per ogni gruppo di SharePoint.
  
I gruppi di Azure AD per Office 365 sono diversi da quelli di Office 365. I gruppi di Azure AD vengono visualizzati nell'interfaccia di amministrazione di Office con **Tipo** impostato su **Sicurezza** e non dispongono di un indirizzo di posta elettronica. I gruppi di Azure AD possono essere gestiti all'interno di:
  
- Windows Server Active Directory (AD)
    
    Questi sono i gruppi che sono stati creati nell'infrastruttura di Windows Server AD locale e sincronizzati con l'abbonamento a Office 365. Nell'interfaccia di amministrazione di Office, questi gruppi hanno lo **Stato** impostato su **Sincronizzato con Active Directory**.
    
- Office 365
    
    Questi sono i gruppi che sono stati creati mediante l'interfaccia di amministrazione di Office, il portale di Azure o Microsoft PowerShell. Nell'interfaccia di amministrazione di Office, questi gruppi hanno lo **Stato** impostato su **Cloud**.
    
 **Procedura consigliata:** Se si usa Windows Server AD locale e si esegue la sincronizzazione con l'abbonamento a Office 365, gestire utenti e gruppi con Windows Server AD.
  
Per i siti del team di SharePoint Online isolati, la struttura del gruppo consigliata è simile alla seguente:
  
|**Gruppo di SharePoint**|**Gruppo di accesso basato su Azure AD**|**Livello di autorizzazione**|
|:-----|:-----|:-----|
|\<nome del sito > membri  <br/> |\<nome del sito > membri  <br/> |Modifica  <br/> |
|\<nome del sito > visitatori  <br/> |\<nome del sito > visualizzatori  <br/> |Lettura  <br/> |
|\<nome del sito > proprietari  <br/> |\<nome del sito > Admins  <br/> |Controllo completo  <br/> |
   
 **Procedura consigliata:** Sebbene sia possibile utilizzare i gruppi di Office 365 o di Azure AD come membri dei gruppi di SharePoint, è consigliabile utilizzare i gruppi di Azure AD. I gruppi di Azure AD, gestiti tramite Windows Server AD o Office 365, offrono una maggiore flessibilità per usare i gruppi nidificati per assegnare le autorizzazioni.
  
Di seguito è l'impostazione predefinita i gruppi di SharePoint configurati per l'utilizzo di gruppi di Azure Active Directory-based access.
  
![Utilizzo dei gruppi di accesso come membri dei gruppi del sito di SharePoint Online predefinito.](media/50a76328-ae69-483e-9029-ac4e7357b5ef.png)
  
Quando si progettano i tre gruppi di accesso, tenere presente quanto segue:
  
- È necessario solo alcuni membri il ** \<nome del sito > Admins** gruppo di accesso, corrispondente a un numero limitato di SharePoint Online amministratori che gestiscono il sito del team.
    
- La maggior parte dei membri del sito sono nel ** \<nome del sito > membri** o ** \<nome del sito > visualizzatori** accedere ai gruppi. Dal momento che i membri del sito di ** \<nome del sito > membri** gruppo di accesso hanno la possibilità di eliminare o modificare le risorse nel sito, valutare attentamente l'appartenenza al. In caso di dubbi, aggiungere il membro del sito per il ** \<nome del sito > visualizzatori** gruppo di accesso.
    
Di seguito è riportato un esempio dei gruppi di accesso per un sito isolato denominato ProjectX e i gruppi di SharePoint.
  
![Un esempio di utilizzo dei gruppi di accesso per un sito di SharePoint Online denominato ProjectX.](media/13afe542-9ffd-4671-9f48-210a0e2a502a.png)
  
## <a name="phase-3-use-nested-azure-ad-groups"></a>Fase 3: Utilizzare nidificate gruppi di Azure Active Directory

Per un progetto limitato a un numero limitato di utenti, un singolo livello dei gruppi di Azure Active Directory-based access aggiunti ai gruppi del sito di SharePoint più adatto alla maggior parte degli scenari. Tuttavia, se si dispone di un numero elevato di utenti e agli utenti che già membri di definizione dei gruppi di Azure Active Directory, è possibile più facilmente assegnare le autorizzazioni di SharePoint tramite gruppi annidati o i gruppi che contengono altri gruppi come membri.
  
Ad esempio, si desidera creare un sito del team di SharePoint Online isolato per la collaborazione tra i dirigenti dei reparti delle vendite, marketing, ingegneria, legali e del supporto e tali reparti fanno parte di gruppi di account utente della direzione esecutiva. Anziché creare un nuovo gruppo per i nuovi membri del sito e inserirvi tutti i singoli account utente esecutivi, inserire i gruppi di dirigenti esistenti per ogni reparto nel nuovo gruppo.
  
  Se si condivide un abbonamento a Office 365 tra più organizzazioni, un solo livello di appartenenza ai gruppi per un sito isolato per un'organizzazione potrebbe diventare difficile da gestire a causa del gran numero di account utente. In questo caso, è possibile utilizzare gruppi di Azure AD per ogni organizzazione con i gruppi all'interno delle organizzazioni per gestire le autorizzazioni.
  
Per utilizzare i gruppi di Azure AD nidificati:
  
1. Individuare o creare i gruppi di Azure AD che conterranno gli account utente e aggiungere gli account utente appropriati come membri.
    
2. Creare il gruppo di accesso basato su Azure AD che conterrà gli altri gruppi di Azure AD e aggiungere i gruppi come membri.
    
3.   Per il livello di accesso appropriato per il gruppo di accesso contenitore, individuare il gruppo di SharePoint e il livello di autorizzazione corrispondente.
    
> [!NOTE]
> Non è possibile utilizzare i gruppi di Office 365 nidificati. 
  
Di seguito è riportato un esempio di Azure Active Directory annidati gruppi ProjectX membri gruppo di accesso.
  
![Esempio di utilizzo dei gruppi di accesso per il gruppo di accesso come membri per il sito ProjectX.](media/2abca710-bf9e-4ce8-9bcd-a8e128264fb1.png)
  
Poiché tutti gli account utente di ricerca, Engineering e Project leads team hanno lo scopo di essere membri del sito, è più semplice aggiungere i gruppi di Azure Active Directory al gruppo accesso ProjectX membri.
  
## <a name="next-step"></a>Passaggio successivo

Quando si è pronti per creare e configurare un sito isolato nell'ambiente di produzione, vedere [Deploy an isolated SharePoint Online team site](deploy-an-isolated-sharepoint-online-team-site.md).
  
## <a name="see-also"></a>Vedere anche

[Siti del team di SharePoint Online isolati](isolated-sharepoint-online-team-sites.md)
  
[Gestire un sito del team di SharePoint Online isolato](manage-an-isolated-sharepoint-online-team-site.md)

[Distribuire un sito del team di SharePoint Online isolato](deploy-an-isolated-sharepoint-online-team-site.md)



