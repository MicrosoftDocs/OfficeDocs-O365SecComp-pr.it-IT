---
title: Impostare un elenco personalizzato di URL rewrite di non eseguire tramite collegamenti attendibili di Office 365 degli strumenti di analisi
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.audience: Admin
ms.topic: article
ms.date: 02/06/2019
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 35dbfd99-da5a-422b-9b0e-c6caf3b645fa
description: Quando si imposta i criteri di collegamenti sicuro degli strumenti di analisi, è possibile includere una riscrittura di non eseguire ' elenco degli URL per abilitare alcune persone all'interno dell'organizzazione visitare i siti che includono nell'elenco.
ms.openlocfilehash: 5eb2d09f1d1d77fa9d6ffdb9f14ba9e7522da287
ms.sourcegitcommit: d6a28c4f6db6a676ca960173e8ff8f17d4aa1c4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2019
ms.locfileid: "29755287"
---
# <a name="set-up-a-custom-do-not-rewrite-urls-list-using-office-365-atp-safe-links"></a>Impostare un elenco personalizzato di URL rewrite di non eseguire tramite collegamenti attendibili di Office 365 degli strumenti di analisi

Con [Office 365 avanzate Threat Protection](office-365-atp.md) (degli strumenti di analisi), l'organizzazione può avere un [URL bloccati personalizzato](set-up-a-custom-blocked-urls-list-wtih-atp.md), in modo che quando utenti fare clic su web indirizzi (URL) in messaggi di posta elettronica o alcuni documenti di Office, viene impediti a questi URL. L'organizzazione può essere elenchi personalizzati "non di riscrittura" per gruppi specifici dell'organizzazione. Un elenco "non di riscrittura" consente alcune persone a visitare gli URL che vengono bloccati in caso contrario tramite [Degli strumenti di analisi collegamenti attendibili in Office 365](atp-safe-links.md). 
  
In questo articolo viene descritto come specificare un elenco di URL che esclusa dall'analisi dei collegamenti sicuro degli strumenti di analisi e alcune importanti considerazioni da tenere presenti.

## <a name="set-up-a-do-not-rewrite-list"></a>Impostare un elenco "non di riscrittura"

Protezione degli strumenti di analisi collegamenti sicuri utilizza più elenchi, inclusi nell'elenco degli URL bloccato dell'organizzazione e gli elenchi "non di riscrittura" per le eccezioni. Se si dispone delle autorizzazioni necessarie, è possibile impostare gli elenchi personalizzati "non di riscrittura". A tale scopo quando si aggiunge o modifica criteri sicuro collegamenti che si applicano a destinatari specifici dell'organizzazione. 

Per modificare o definire i criteri degli strumenti di analisi, è necessario assegnare uno dei ruoli descritti nella tabella riportata di seguito:

|Ruolo  |Modalità assegnato  |
|---------|---------|
|Amministratore globale di Office 365 |La persona che iscrizione acquistare Office 365 è un amministratore globale per impostazione predefinita. Vedere [ruoli di amministratore su Office 365](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles) per ulteriori informazioni.         |
|Amministratore della sicurezza |Interfaccia di amministrazione di Azure Active Directory ([https://aad.portal.azure.com](https://aad.portal.azure.com))|
|Exchange Online Organization Management |Interfaccia di amministrazione di Exchange ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp)) <br>oppure <br>  Cmdlet di PowerShell (vedere [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps)) |

> [!TIP]
> Per ulteriori informazioni sui ruoli e autorizzazioni, vedere [autorizzazioni in Office 365 Security &amp; centro conformità](permissions-in-the-security-and-compliance-center.md).

### <a name="to-view-or-edit-a-custom-do-not-rewrite-urls-list"></a>Per visualizzare o modificare un elenco degli URL "non di riscrittura" personalizzato
  
1. Accedere a [https://protection.office.com](https://protection.office.com) e accedere con l'account di lavoro o della scuola. 
    
2. Nel riquadro di spostamento sinistro, in **gestione rischio** \> **criteri** \> **Collegamenti sicuri**.
    
3. Nella sezione **criteri che si applicano a destinatari specifici** fare clic su **Nuovo** (pulsante nuovo simile a un segno di addizione ( **+**)) per creare un nuovo criterio. (In alternativa, è possibile modificare un criterio esistente.)<br/>![Selezionare nuovo per aggiungere un criterio di collegamenti sicuro per i destinatari di posta elettronica specifico](media/01073f42-3cec-4ddb-8c10-4d33ec434676.png)
  
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
   
 