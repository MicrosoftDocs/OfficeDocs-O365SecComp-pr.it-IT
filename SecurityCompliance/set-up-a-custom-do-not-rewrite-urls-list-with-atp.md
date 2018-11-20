---
title: Impostare un elenco personalizzato di URL rewrite di non eseguire tramite collegamenti attendibili di Office 365 degli strumenti di analisi
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
ms.assetid: 35dbfd99-da5a-422b-9b0e-c6caf3b645fa
description: Quando si imposta i criteri di collegamenti sicuro degli strumenti di analisi, è possibile includere una riscrittura di non eseguire ' elenco degli URL per abilitare alcune persone all'interno dell'organizzazione visitare i siti che includono nell'elenco.
ms.openlocfilehash: c954c12785659f9c025046bf3773cfec2d5dd5f9
ms.sourcegitcommit: 147768bbe44c8c98c02fa29ae9d882cee4ec2d6b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/09/2018
ms.locfileid: "26238388"
---
# <a name="set-up-a-custom-do-not-rewrite-urls-list-using-office-365-atp-safe-links"></a>Impostare un elenco personalizzato di URL rewrite di non eseguire tramite collegamenti attendibili di Office 365 degli strumenti di analisi

Con [Office 365 avanzate Threat Protection](office-365-atp.md) (degli strumenti di analisi), l'organizzazione può avere un [URL bloccati personalizzato](set-up-a-custom-blocked-urls-list-wtih-atp.md), in modo che quando utenti fare clic su web indirizzi (URL) in messaggi di posta elettronica o alcuni documenti di Office, viene impediti a questi URL. L'organizzazione può essere elenchi personalizzati "non di riscrittura" per gruppi specifici dell'organizzazione. Un elenco "non di riscrittura" consente alcune persone a visitare gli URL che vengono bloccati in caso contrario tramite [Degli strumenti di analisi collegamenti attendibili in Office 365](atp-safe-links.md). 
  
In questo articolo viene descritto come specificare un elenco di URL che esclusa dall'analisi dei collegamenti sicuro degli strumenti di analisi e alcune importanti considerazioni da tenere presenti.

## <a name="set-up-a-do-not-rewrite-list"></a>Impostare un elenco "non di riscrittura"

Protezione degli strumenti di analisi collegamenti sicuri utilizza più elenchi, inclusi nell'elenco degli URL bloccato dell'organizzazione e gli elenchi "non di riscrittura" per le eccezioni. Se si dispone delle autorizzazioni necessarie, è possibile impostare gli elenchi personalizzati "non di riscrittura". A tale scopo quando si aggiunge o modifica criteri sicuro collegamenti che si applicano a destinatari specifici dell'organizzazione. 
  
1. Accedere a [https://protection.office.com](https://protection.office.com) e accedere con l'account di lavoro o della scuola. 
    
2. Nel riquadro di spostamento sinistro, in **gestione rischio** \> **criteri** \> **Collegamenti sicuri**.
    
3. Nella sezione **criteri che si applicano a destinatari specifici** fare clic su **Nuovo** (pulsante nuovo simile a un segno di addizione ( **+**)) per creare un nuovo criterio. (In alternativa, è possibile modificare un criterio esistente.)
    
    ![Selezionare nuovo per aggiungere un criterio di collegamenti sicuro per i destinatari di posta elettronica specifico](media/01073f42-3cec-4ddb-8c10-4d33ec434676.png)
  
4. Consente di specificare un nome e una descrizione per il criterio.
    
5. Nella sezione **non riscrivere gli URL seguenti** , selezionare la casella **Immettere un URL valido** e quindi digitare un URL e quindi fare clic sul segno più (+). 
    
6. Nella sezione **Applicato a** scegliere **il destinatario è un membro del**e quindi fare clic su gruppi di cui che si desidera includere nel criterio. Scegliere **Aggiungi**e quindi fare clic su **OK**.
    
7. Dopo aver aggiunto gli URL, nell'angolo inferiore destro dello schermo, scegliere **Salva**.
    
> [!NOTE]
> Assicurarsi di esaminare l'elenco personalizzato dell'organizzazione di URL bloccati. Vedere [impostare un elenco degli URL bloccato personalizzato utilizzo degli strumenti di analisi dei collegamenti sicuri](set-up-a-custom-blocked-urls-list-wtih-atp.md). 
  
## <a name="important-points-to-keep-in-mind"></a>Aspetti importanti da tenere presenti

- Tutti gli URL specificati nell'elenco "non di riscrittura" sono esclusi dai collegamenti sicuro degli strumenti di analisi di virus per i destinatari specificati.
 
- Quando si specifica un elenco "non di riscrittura" per un criterio degli strumenti di analisi collegamenti sicuri, è possibile includere fino a tre caratteri jolly asterischi (\*). I caratteri jolly (\*) vengono considerati come voci `contoso.com`, che non si in modo esplicito include i prefissi o sottodomini, ad esempio `http://` o `https://`. In questo modo una voce, ad esempio `contoso.com` è simile a `*contoso.com*` per l'elenco "non di riscrittura".

- Se si dispone già di un elenco di URL nell'elenco "non di riscrittura", assicurarsi di esaminare l'elenco e aggiungere i caratteri jolly nel modo appropriato. Ad esempio, se l'elenco esistente è una voce come `http://contoso.com/a` e si desidera includere percorsi secondari come `http://contoso.com/a/b` nei criteri di aggiungere un carattere jolly per la voce in modo che sia simile `http://contoso.com/a*`.
    
- Non includere una barra (/) nell'URL specificato nell'elenco "non di riscrittura". Ad esempio, invece di immettere `contoso.com/` nell'elenco "non di riscrittura", immettere `contoso.com`.
    
Gli esempi di è possibile immettere e quali effect tali voci di elenchi di tabella seguenti sono.
    
|**Voce di esempio**|**Funzione**|
|:-----|:-----|
|`*contoso.com*`  <br/> |Consente ai destinatari specifici di visitare un dominio, sottodomini e percorsi, ad esempio `http://www.contoso.com`, `https://www.contoso.com`, `https://maps.contoso.com`, o`http://www.contoso.com/a`  <br/> |
|`http://contoso.com/a`  <br/> |Consente ai destinatari specifici a visitare un sito come `http://contoso.com/a`, ma non percorsi secondari`http://contoso.com/a/b`  <br/> |
|`http://contoso.com/a*`  <br/> |Consente ai destinatari specifici a visitare un sito come `http://contoso.com/a` e i percorsi secondari`http://contoso.com/a/b`  <br/> |
   
 