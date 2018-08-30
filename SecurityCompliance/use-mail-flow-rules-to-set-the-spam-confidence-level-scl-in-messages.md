---
title: Usare le regole del flusso di posta per impostare il livello di probabilità di posta indesiderata (SCL) nei messaggi
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 11/17/2014
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 4ccab17a-6d49-4786-aa28-92fb28893e99
description: È possibile creare una regola di trasporto che imposta il livello di probabilità di posta indesiderata (SCL) di un messaggio di posta elettronica. Il valore SCL è una misura di probabilmente come un messaggio di posta indesiderata. Posta indesiderata è messaggi di posta elettronica indesiderati (e in genere indesiderato). Deve agire diversi per un messaggio in base al relativo la posta indesiderata. Ad esempio, è possibile ignorare la posta indesiderata filtro del contenuto per i messaggi inviati da persone all'interno dell'organizzazione in quanto si considera attendibile che un messaggio inviato internamente da un collega non è la posta indesiderata. Utilizza le regole di trasporto per impostare il valore SCL di un messaggio offre maggiore controllo nella gestione della posta indesiderata.
ms.openlocfilehash: 7abd0d1881374b1f2a4bd32ee480445f7683d1b3
ms.sourcegitcommit: e9dca2d6a7838f98bb7eca127fdda2372cda402c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/21/2018
ms.locfileid: "23002895"
---
# <a name="use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages"></a>Usare le regole del flusso di posta per impostare il livello di probabilità di posta indesiderata (SCL) nei messaggi

È possibile creare una regola di trasporto che imposta il livello di probabilità di posta indesiderata (SCL) di un messaggio di posta elettronica. Il valore SCL è una misura di probabilmente come un messaggio di posta indesiderata. Posta indesiderata è messaggi di posta elettronica indesiderati (e in genere indesiderato). Deve agire diversi per un messaggio in base al relativo la posta indesiderata. Ad esempio, è possibile ignorare la posta indesiderata filtro del contenuto per i messaggi inviati da persone all'interno dell'organizzazione in quanto si considera attendibile che un messaggio inviato internamente da un collega non è la posta indesiderata. Utilizza le regole di trasporto per impostare il valore SCL di un messaggio offre maggiore controllo nella gestione della posta indesiderata. 
  
 **Che cosa è necessario sapere prima di iniziare**
  
- Tempo stimato per eseguire questa procedura: 10 minuti.
    
- È necessario disporre delle autorizzazioni prima che è possibile eseguire queste procedure. Per verificare le autorizzazioni necessarie, vedere la voce "Regole di trasporto" in [Feature Permissions in Exchange Online](http://technet.microsoft.com/library/15073ce1-0917-403b-8839-02a2ebc96e16.aspx) o [autorizzazioni funzionalità in EOP](eop/feature-permissions-in-eop.md). 
    
- Per informazioni sui tasti di scelta rapida che è possibile utilizzare con le procedure in questo argomento, vedere **Tasti di scelta rapida nell'interfaccia di amministrazione di Exchange**.
    
### <a name="to-create-a-transport-rule-that-sets-the-scl-of-a-message"></a>Per creare una regola di trasporto che imposta il valore SCL del messaggio

1. Nell'interfaccia di amministrazione di Exchange (EAC), scegliere **flusso di posta** \> **regole**.
    
2. Scegliere **New**![Aggiungi icona](media/ITPro-EAC-AddIcon.gif), quindi selezionare **Crea una nuova regola**.
    
3. Specificare un nome per la regola.
    
4. Scegliere **altre opzioni**e quindi in **Applica questa regola se**, specificare una condizione che determinerà l'azione che verrà impostato per questa regola (che consiste nell'impostare il valore SCL).
    
    Ad esempio, è possibile impostare **il mittente** \> **è interno/esterno**e quindi nella finestra di dialogo **Selezionare mittente percorso** selezionare **all'interno dell'organizzazione**e scegliere **ok**.</br>
    ![Seleziona la località del mittente](media/EOP-ETR-SetSCL-1.jpg)
  
5. In **Fai quanto segue**, selezionare **Modifica le proprietà del messaggio** \> **Imposta il livello di probabilità di posta indesiderata**.
  
6. Nella finestra di dialogo **specificare SCL** selezionare uno dei valori seguenti e scegliere **ok**:
    
  - **Filtro posta indesiderata bypass** - questo imposta il valore SCL su -1, vale a dire che il filtro del contenuto non vengano eseguite. 
    
  - **0-4** - quando si imposta il valore SCL su uno dei valori seguenti, il messaggio verrà passato lungo per il filtro contenuto per un'ulteriore elaborazione. 
    
  - **5, 6** - quando si imposta il valore SCL su uno dei valori seguenti, l'azione specificata per la **posta indesiderata** i criteri di filtro dei contenuti applicabile verranno applicate. Per impostazione predefinita, l'azione consiste nell'inviare il messaggio nella cartella posta indesiderata del destinatario. 
    
  - **7-9** - quando si imposta il valore SCL su uno dei valori seguenti, l'azione specificata per la **posta indesiderata confidenza elevata** i criteri di filtro dei contenuti applicabile verranno applicate. Per impostazione predefinita, l'azione consiste nell'inviare il messaggio nella cartella posta indesiderata del destinatario. 
    
    Per ulteriori informazioni sulla configurazione dei criteri di filtro del contenuto, vedere [configurazione dei criteri di filtro posta indesiderata](configure-your-spam-filter-policies.md). Per ulteriori informazioni sui valori SCL del servizio, vedere [Spam confidence levels](spam-confidence-levels.md).
    
7. Specificare ulteriori proprietà per la regola e scegliere **Salva**.
    
    > [!TIP]
    > Per ulteriori informazioni sulle proprietà aggiuntive, è possibile selezionare o specificare per questa regola, vedere [utilizzare EAC per creare una regola di trasporto](http://technet.microsoft.com/library/e7a81372-b6d7-4d1f-bc9e-a845a7facac2.aspx#CreateEAC). 
  
## <a name="how-do-you-know-this-worked"></a>Come verificare se l'operazione ha avuto esito positivo

Per verificare il corretto funzionamento di questa procedura, inviare un messaggio di posta elettronica a una persona interna all'organizzazione e verificare che l'azione eseguita quando il messaggio come previsto. Ad esempio, se si **Imposta il livello di probabilità di posta indesiderata (SCL)** per **il filtro posta indesiderata di Bypass**, quindi il messaggio deve essere inviato alla posta in arrivo del destinatario specificato. Tuttavia, se si **Imposta il livello di probabilità di posta indesiderata (SCL)** a **9**e l'azione **posta indesiderata confidenza elevata** per i criteri di filtro dei contenuti applicabile consiste nello spostare il messaggio nella cartella posta indesiderata, quindi il messaggio deve essere inviato all'oggetto specificato cartella posta indesiderata del destinatario. 
  

