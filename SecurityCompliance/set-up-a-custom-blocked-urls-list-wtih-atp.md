---
title: Impostare un elenco di URL bloccato personalizzato con Office 365 degli strumenti di analisi provvisoria collegamenti
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 896a7efb-1683-465e-a394-261349e5d866
description: In questo articolo per informazioni su come configurare un elenco di URL bloccati per l'organizzazione utilizza la protezione di Office 365 avanzate rischio. Gli URL bloccati verranno applicate a messaggi di posta elettronica e documenti di Office in base ai criteri di collegamenti sicuro degli strumenti di analisi.
ms.openlocfilehash: 36d295e6924d2e9972c185657885fa25bd96bf08
ms.sourcegitcommit: 7032830867eb3fc71760e04b8342aff174c5d757
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/01/2018
ms.locfileid: "25353252"
---
# <a name="set-up-a-custom-blocked-urls-list-using-office-365-atp-safe-links"></a>Impostare un elenco di URL bloccato personalizzato con Office 365 degli strumenti di analisi provvisoria collegamenti

Con [Office 365 avanzate Threat Protection](office-365-atp.md) (degli strumenti di analisi), l'organizzazione può avere un elenco personalizzato di indirizzi di siti Web (URL) che vengono bloccati. Quando viene bloccato un URL, persone, fare clic sui collegamenti all'URL bloccati vengono indirizzate a una [pagina di avviso](atp-safe-links-warning-pages.md) simile all'immagine seguente: 
  
![In questo sito è bloccato](media/6b4bda2d-a1e6-419e-8b10-588e83c3af3f.png)
  
L'elenco degli URL bloccato è definito dal team di protezione di Office 365 dell'organizzazione e tale elenco si applica a tutti gli utenti dell'organizzazione che sono disponibili i criteri di Office 365 degli strumenti di analisi provvisoria collegamenti. 
  
In questo articolo per informazioni su come configurare personalizzato URL elenco dei domini bloccati dell'organizzazione per [Strumenti di analisi collegamenti attendibili in Office 365](atp-safe-links.md).
  
## <a name="view-or-edit-a-custom-list-of-blocked-urls"></a>Visualizzare o modificare un elenco personalizzato di URL bloccati

[Degli strumenti di analisi collegamenti attendibili in Office 365](atp-safe-links.md) utilizza più elenchi, inclusi personalizzato URL elenco dei domini bloccati dell'organizzazione. Se si dispone delle autorizzazioni necessarie, è possibile impostare elenco personalizzato dell'organizzazione. Ottenere questo risultato modificando i criteri dell'organizzazione predefinito collegamenti sicuri.
  
1. Accedere a [https://protection.office.com](https://protection.office.com) e accedere con l'account di lavoro o della scuola. 
    
2. Nel riquadro di spostamento sinistro, in **gestione rischio**, scegliere **criterio** \> **Collegamenti sicuri**.
    
3. Nella sezione **criteri che si applicano all'intera organizzazione** , selezionare **predefinito**e quindi fare clic su **Modifica** (pulsante Edit a forma di una matita). 
    
    ![Fare clic su Modifica per modificare il criterio predefinito per la protezione collegamenti sicuri](media/d08f9615-d947-4033-813a-d310ec2c8cca.png)
  
    È possibile per visualizzare l'elenco degli URL bloccati. Si noti che, inizialmente, non sarà necessario tutti gli URL elencati.
    
    ![L'elenco degli URL bloccati è nel predefinito criterio sicuri collegamenti che si applica all'intera organizzazione.](media/575e1449-6191-40ac-b626-030a2fd3fb11.png)
  
4. Selezionare la casella **Immettere un URL valido** e quindi digitare un URL e quindi fare clic sul segno più (+). Ecco alcuni aspetti da tenere presenti: 
    
  - È possibile specificare un URL solo dominio (ad esempio `contoso.com` o `tailspintoys.com`). Ciò Blocca clic in qualsiasi URL che contiene il dominio.
    
  - Non includere una barra ( **/**) alla fine dell'URL. Ad esempio, invece di immettere `http://www.contoso.com/`, immettere `http://www.contoso.com`.
    
  - È possibile includere fino a tre caratteri jolly asterischi (\*) per ogni URL. Nella tabella seguente sono elencate sono riportati alcuni esempi di è possibile immettere e quali effect tali voci.
    
|**Voce di esempio**|**Funzione**|
|:-----|:-----|
|`contoso.com`o`*contoso.com*`  <br/> |Blocca il dominio, sottodomini e percorsi, ad esempio `https://www.contoso.com`, `http://sub.contoso.com`, e`http://contoso.com/abc`  <br/> |
|`http://contoso.com/a`  <br/> |Blocca un sito `http://contoso.com/a` ma, come percorsi secondari non aggiuntive`http://contoso.com/a/b`  <br/> |
|`http://contoso.com/a*`  <br/> |Blocca un sito `http://contoso.com/a` e i percorsi secondari aggiuntive`http://contoso.com/a/b`  <br/> |
   
5. Dopo aver aggiunto gli URL, nell'angolo inferiore destro dello schermo, scegliere **Salva**.
    
## <a name="what-if-i-want-to-define-exceptions-for-certain-users-in-my-organization"></a>Se desidera definire eccezioni per determinati utenti nell'organizzazione?

Se si desidera determinati gruppi siano in grado di visualizzare gli URL che potrebbe essere bloccati per altri utenti, è possibile specificare un criterio degli strumenti di analisi collegamenti sicuri da applicare a destinatari specifici. Vedere [impostare un "non di riscrittura" URL elenco personalizzato utilizzo degli strumenti di analisi dei collegamenti sicuri](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md).
  
## <a name="related-topics"></a>Argomenti correlati

[Office 365 Advanced Threat Protection](office-365-atp.md)
  
[Collegamenti degli strumenti di analisi sicuro in Office 365](atp-safe-links.md)
  
[Impostare i criteri degli strumenti di analisi collegamenti attendibili in Office 365](set-up-atp-safe-links-policies.md)
  
[Allegati degli strumenti di analisi sicuro in Office 365](atp-safe-attachments.md)

[Le autorizzazioni di sicurezza di Office 365 &amp; centro conformità](permissions-in-the-security-and-compliance-center.md)
  

