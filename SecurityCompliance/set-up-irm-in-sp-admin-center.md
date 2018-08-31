---
title: Set up Information Rights Management (IRM) nell'interfaccia di amministrazione di SharePoint
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 6/29/2018
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- SPO160
- MET150
ms.assetid: 239ce6eb-4e81-42db-bf86-a01362fed65c
description: Informazioni su come utilizzare SharePoint Online IRM tramite Microsoft Azure Active Directory Rights Management Services (RMS) per proteggere raccolte documenti ed elenchi di SharePoint.
ms.openlocfilehash: dea8c71ce67207b3c40a1f934f90e63740f70f29
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/27/2018
ms.locfileid: "22530802"
---
# <a name="set-up-information-rights-management-irm-in-sharepoint-admin-center"></a>Set up Information Rights Management (IRM) nell'interfaccia di amministrazione di SharePoint

In SharePoint Online, la protezione IRM viene applicata ai file a livello di elenco e libreria. Prima dell'organizzazione può utilizzare la protezione IRM, è necessario configurare Rights Management. IRM si basa su Azure Rights Management service da Azure la protezione delle informazioni per la crittografia e assegnare limitazioni di utilizzo. Alcuni piani di Office 365 includono Azure Rights Management, ma non tutte. Per ulteriori informazioni, leggere [servizi e applicazioni di Office come supportano Azure Rights Management](https://docs.microsoft.com/azure/information-protection/understand-explore/office-apps-services-support).
  
## <a name="turn-on-irm-service-using-sharepoint-admin-center"></a>Attivare il servizio IRM tramite interfaccia di amministrazione di SharePoint

Prima che l'organizzazione può raccolte ed elenchi SharePoint protetto con IRM, è necessario attivare il servizio di gestione dei diritti per l'organizzazione. Per informazioni su come visualizzare [Attivare Azure Rights Management](https://docs.microsoft.com/information-protection/deploy-use/activate-service). È necessario utilizzare un account di lavoro o della scuola con privilegi di amministratore globale di Office 365 per abilitare il servizio di gestione dei diritti. In caso contrario, non sarà in grado di utilizzare le funzionalità IRM con SharePoint Online.
  
Dopo aver attivato il servizio di gestione dei diritti, accedere all'interfaccia di amministrazione di SharePoint per attivare IRM.
  
1. Accedere a Office 365 come amministratore globale o amministratore di SharePoint.
    
2. Selezionare l'icona di avvio delle app ![Icona di avvio delle app in Office 365](media/e5aee650-c566-4100-aaad-4cc2355d909f.png) in alto a sinistra e scegliere **Amministratore** per aprire l'interfaccia di amministrazione di Office 365 (se il riquadro Amministratore non è visibile, non si dispone delle autorizzazioni di amministratore di Office 365 all'interno dell'organizzazione). 
    
3. Nel riquadro sinistro selezionare **Admin Center** \> **SharePoint**.
    
4. Nel riquadro sinistro, scegliere **Impostazioni**.
    
5. Nella sezione **Information Rights Management (IRM)** , scegliere di **utilizzare il servizio IRM specificato nella configurazione**e quindi scegliere **Aggiorna le impostazioni di IRM**. Dopo aver aggiornato le impostazioni IRM, gli utenti dell'organizzazione possono iniziare a utilizzare IRM nelle raccolte documenti ed elenchi di SharePoint. Tuttavia, le opzioni di farlo potrebbero richiedere un'ora appaiano nella raccolta di impostazioni e le impostazioni dell'elenco.
    
## <a name="irm-enable-sharepoint-document-libraries-and-lists"></a>Elenchi e raccolte documenti di SharePoint abilitare IRM
<a name="__toc220831191"> </a>

Dopo l'aggiornamento delle impostazioni di IRM, i proprietari dei siti possono protetto con IRM loro elenchi di SharePoint e raccolte documenti. Per ulteriori informazioni, vedere [Applicare Information Rights Management a un elenco o raccolta](apply-irm-to-a-list-or-library.md).
  
Quando i proprietari dei siti abilitare IRM per un elenco o raccolta, è possibile proteggere qualsiasi tipo di file supportati in tale elenco o raccolta. Se IRM è abilitato per una raccolta, gestione dei diritti si applica a tutti i file in tale raccolta. Quando si attiva IRM per un elenco, gestione dei diritti si applica solo ai file associati alle voci di elenco, non le voci dell'elenco effettivo.
  
Al momento del download di file in un elenco abilitato IRM o la raccolta, i file sono crittografati in modo che solo gli utenti autorizzati possono visualizzarli. Ogni file protetto contiene inoltre una licenza di pubblicazione che impone restrizioni sugli utenti che visualizzano il file. Le restrizioni includono in esecuzione un file di sola lettura, la disattivazione della copia del testo, impedendo agli utenti di salvare una copia locale e impedire la stampa del file di persone. Programmi client in grado di leggere i tipi di file supportati IRM utilizzano la licenza di pubblicazione all'interno del file protetto per applicare queste restrizioni. È come un file protetto mantiene la protezione anche dopo il download. Per abilitare IRM per un elenco o raccolta, vedere [Applicare Information Rights Management a un elenco o raccolta](apply-irm-to-a-list-or-library.md).
  
È possibile creare o modificare documenti in una raccolta di IRM abilitato utilizzando Office Online. In realtà, una persona per volta può scaricare e modificare i file crittografati con IRM. Utilizzare archiviazione e l'estrazione per gestire *la creazione condivisa* o creazione e modifica tra più utenti. 
  
Quando si scarica un file PDF da una libreria protetti tramite IRM, Office 365 consente di creare un file PDF protetto. Non modificherà l'estensione del file, ma il file è protetto. Per visualizzare il file è necessario il Visualizzatore di Azure Information Protection, il client Azure Information Protection completo, o un'altra applicazione che supporta la visualizzazione protetta file PDF. 
  
SharePoint Online supporta la crittografia dei tipi di file seguenti:
  
- PDF
    
- I formati di file 97-2003 per i programmi di Microsoft Office seguenti: Word, Excel e PowerPoint
    
- Formati Office Open XML per i programmi di Microsoft Office seguenti: Word, Excel e PowerPoint
    
- Il formato XML Paper Specification (XPS)
    
## <a name="next-steps"></a>Passaggi successivi
<a name="__toc220831191"> </a>

Dopo aver abilitato IRM per SharePoint Online, è possibile avviare l'applicazione di gestione dei diritti per elenchi e raccolte. Per informazioni, vedere [Applicare Information Rights Management a un elenco o raccolta](apply-irm-to-a-list-or-library.md).
  
Il nuovo client di sincronizzazione OneDrive per Windows supporta la sincronizzazione delle raccolte documenti di SharePoint protetti tramite IRM e percorsi di OneDrive (purché l'impostazione di IRM per la raccolta non è stata impostata per scadere diritti di accesso documento). Per ulteriori informazioni o per iniziare a distribuire il nuovo client di sincronizzazione, vedere [distribuire il nuovo client di sincronizzazione OneDrive per Windows](https://support.office.com/article/3f3a511c-30c6-404a-98bf-76f95c519668).
  
[Inizio pagina](set-up-irm-in-sp-admin-center.md#__top)
  

