---
title: Crittografia dei messaggi di Office 365
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 6/6/2018
ms.audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: f87cb016-7876-4317-ae3c-9169b311ff8a
description: Con la crittografia dei messaggi di Office 365, l'organizzazione può inviare e ricevere messaggi di posta elettronica crittografati tra utenti all'interno e all'esterno dell'organizzazione. La crittografia dei messaggi di posta elettronica consente di verificare che solo i destinatari previsti possano visualizzare il contenuto del messaggio.
ms.openlocfilehash: 06c43bcb3364b83114e2d7b1a2ef0273858cffb0
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "32261314"
---
# <a name="office-365-message-encryption"></a>Crittografia dei messaggi di Office 365

Con la crittografia dei messaggi di Office 365, l'organizzazione può inviare e ricevere messaggi di posta elettronica crittografati tra utenti all'interno e all'esterno dell'organizzazione. La crittografia dei messaggi di Office 365 è compatibile con Outlook.com, Yahoo!, Gmail e altri servizi di posta elettronica. La crittografia dei messaggi di posta elettronica consente di verificare che solo i destinatari previsti possano visualizzare il contenuto del messaggio.
  
Questo articolo fa parte di una serie più ampia di articoli sulla crittografia dei messaggi di Office 365. Utilizzare la tabella seguente per trovare rapidamente le informazioni necessarie.
  
|||
|:-----|:-----|
|Leggere questo articolo...  <br/> |Se si è...  <br/> |
|[Informazioni sui messaggi protetti in Office 365](https://support.office.com/article/2baf3ac7-12db-40a4-8af7-1852204b4b67.aspx) <br/> |Un utente finale che desidera ottenere ulteriori informazioni sul funzionamento dei messaggi crittografati e sulle opzioni disponibili.  <br/> |
|[Come aprire un messaggio protetto](https://support.office.com/article/1157a286-8ecc-4b1e-ac43-2a608fbf3098.aspx) <br/> |Un utente finale che vuole leggere un messaggio protetto che è stato inviato. In questo articolo sono incluse informazioni sulla lettura di messaggi in diverse versioni di Outlook e su account di posta elettronica diversi, compresi quelli esterni a Office 365, ad esempio Gmail e Yahoo! account.  <br/> |
|[Inviare, visualizzare e rispondere a messaggi crittografati in Outlook](https://support.office.com/article/eaa43495-9bbb-4fca-922a-df90dee51980.aspx) <br/> |Un utente finale che desidera inviare, visualizzare o rispondere a un messaggio crittografato da Outlook. Anche se non si è membri di un'organizzazione di Office 365, viene comunque ricevuta la notifica dei messaggi crittografati inviati all'utente in Outlook. Utilizzare questo articolo per istruzioni su come visualizzare e rispondere a messaggi crittografati inviati da Office 365.  <br/> |
|[Inviare un messaggio con firma digitale o crittografato](https://support.office.com/article/a18ecf7f-a7ac-4edd-b02e-687b05eff547) <br/> |Un utente finale che desidera inviare, visualizzare o rispondere a messaggi crittografati utilizzando Outlook per Mac. Questo articolo riguarda anche l'utilizzo di metodi di crittografia diversi da OME, ad esempio S/MIME.  <br/> |
|[Visualizzazione dei messaggi crittografati sul dispositivo Android](https://support.office.com/article/83d60f17-2305-407a-a762-7d518401fdeb) <br/> |Un utente finale che ha ricevuto un messaggio crittografato con la crittografia dei messaggi di Office 365 sul dispositivo Android, è possibile utilizzare l'app gratuito OME Viewer per visualizzare il messaggio e inviare una risposta crittografata. In questo articolo viene illustrato come.  <br/> |
|[Visualizzare i messaggi crittografati sul tuo iPhone o iPad](https://support.office.com/article/4d631321-0d26-4bcc-a483-d294dd0b1caf) <br/> |Un utente finale che ha ricevuto un messaggio crittografato con la crittografia dei messaggi di Office 365 sul vostro iPhone o iPad, è possibile utilizzare l'app visualizzatore gratuito OME per visualizzare il messaggio e inviare una risposta crittografata. In questo articolo viene illustrato come.  <br/> |
|Crittografia messaggi di Office 365 (OME) (questo articolo)  <br/> |Un amministratore di Office 365 o Exchange Online Protection che vuole sapere dove è possibile trovare ulteriori risorse.  <br/> |
|[Confrontare le versioni di OME](ome-version-comparison.md)  <br/> |Un amministratore di Office 365 o Exchange Online Protection che vuole conoscere le differenze tra la crittografia dei messaggi di Office 365 legacy e le nuove funzionalità OME, nonché il modo in cui possono collaborare.  <br/> |
|[Domande frequenti su Office 365 Message Encryption](ome-faq.md) <br/> |Un amministratore di Office 365 o Exchange Online Protection che vuole rispondere alle domande più frequenti, tra cui le licenze e un confronto tra le nuove funzionalità e OME legacy.  <br/> |
|[Configurare le nuove funzionalità di Office 365 Message Encryption](set-up-new-message-encryption-capabilities.md) <br/> |Un amministratore di Office 365 o Exchange Online Protection che desidera informazioni su come configurare le nuove funzionalità di crittografia dei messaggi di Office 365 per l'organizzazione di Office 365.  <br/> |
|[Definire le regole del flusso di posta per crittografare i messaggi di posta elettronica in Office 365](define-mail-flow-rules-to-encrypt-email.md) <br/> |Un amministratore di Office 365 o Exchange Online Protection che ha già configurato la crittografia dei messaggi di Office 365 e che è possibile definire le regole del flusso di posta elettronica per crittografare automaticamente i messaggi di posta elettronica inviati dall'organizzazione.  <br/> |
|[Gestire Office 365 Message Encryption](manage-office-365-message-encryption.md) <br/> |Un amministratore di Office 365 o Exchange Online Protection che ha già configurato la crittografia dei messaggi di Office 365 e desidera configurare le impostazioni facoltative per OME.  <br/> |
|[Aggiungere il logo della propria organizzazione ai messaggi crittografati](add-your-organization-brand-to-encrypted-messages.md) <br/> |Un amministratore di Office 365 o Exchange Online Protection che desidera applicare il marchio dell'azienda per personalizzare l'aspetto dei messaggi di posta elettronica di crittografia del messaggio di Office 365 dell'organizzazione e il contenuto del portale OME.  <br/> |
|[Revoca della posta elettronica di crittografia messaggi di Office 365](revoke-ome-encrypted-mail.md) <br/> |Un amministratore di Office 365 o Exchange Online Protection che desidera revocare un messaggio di posta elettronica crittografato utilizzando la crittografia dei messaggi di Office 365.  <br/> |
|Crittografia dei messaggi di Office 365 nella [Descrizione del servizio criteri di conformità e del messaggio](https://technet.microsoft.com/en-us/library/5c43c8eb-f8f7-4b5a-a743-b1dab7dc2fc8#bkmk_O365_MessageEncryption) <br/> |Per informazioni dettagliate sulla funzionalità di crittografia dei messaggi di Office 365, incluse le SKU supportate, è disponibile da Office 365.  <br/> |
|[Aggiornamento alle nuove funzionalità di Office 365 Message Encryption](legacy-information-for-message-encryption.md) <br/> |Un amministratore di Office 365 o Exchange Online Protection che ha già configurato la crittografia dei messaggi di Office 365 e desidera informazioni su come ha funzionato OME prima del rilascio delle nuove funzionalità. Anche se non è possibile configurare una nuova distribuzione utilizzando OME senza le nuove funzionalità, Microsoft continua a supportare le distribuzioni esistenti. <br/> |
||

Il resto di questo articolo si applica alle nuove funzionalità OME.
  
## <a name="how-office-365-message-encryption-works"></a>Funzionamento della crittografia dei messaggi di Office 365

La crittografia dei messaggi di Office 365 è un servizio online basato su Microsoft Azure Rights Management (Azure RMS) che fa parte di Azure Information Protection. Sono inclusi i criteri di crittografia, identità e autorizzazione che consentono di proteggere il messaggio di posta elettronica. È possibile crittografare i messaggi utilizzando i modelli Rights Management, l' [opzione](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#do-not-forward-option-for-emails)non inoltrare e l' [opzione solo crittografia](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails).

Gli utenti possono quindi crittografare i messaggi di posta elettronica e una vasta gamma di allegati di Office 365 utilizzando queste opzioni. Per un elenco completo dei tipi di allegati supportati, vedere ["tipi di file coperti da criteri IRM quando sono allegati ai messaggi" in Introduzione a IRM per i messaggi di posta elettronica](https://support.office.com/article/bb643d33-4a3f-4ac7-9770-fd50d95f58dc#FileTypesforIRM).

In qualità di amministratore, è anche possibile definire le regole del flusso di posta per applicare la protezione. Ad esempio, è possibile creare una regola che richiede la crittografia di tutti i messaggi indirizzati a un destinatario specifico o che contiene parole specifiche nella riga dell'oggetto e specificare anche che i destinatari non possono copiare o stampare il contenuto del messaggio.

A differenza della versione precedente di OME, le nuove funzionalità forniscono un'esperienza di mittente unificata se si sta inviando posta all'interno dell'organizzazione o ai destinatari esterni a Office 365. Inoltre, i destinatari che ricevono un messaggio di posta elettronica protetto inviato a un account di Office 365 in Outlook 2016 o Outlook sul Web, non è necessario eseguire ulteriori operazioni per visualizzare il messaggio. Funziona perfettamente. Anche i destinatari che utilizzano client di posta elettronica e provider di servizi di posta elettronica dispongono di un'esperienza migliorata. Per informazioni, vedere [Learn about protected messages in Office 365](https://support.office.com/article/Learn-about-protected-messages-in-Office-365-2baf3ac7-12db-40a4-8af7-1852204b4b67) e [come aprire un messaggio protetto](https://support.office.com/article/How-do-I-open-a-protected-message-1157a286-8ecc-4b1e-ac43-2a608fbf3098).

Per un elenco dettagliato delle differenze tra la versione precedente di OME e le nuove funzionalità OME, vedere [compare versions of ome](ome-version-comparison.md).

Quando un utente invia un messaggio di posta elettronica che corrisponde a una regola del flusso di posta di crittografia, il messaggio viene crittografato prima dell'invio. Tutti gli utenti finali di Office 365 che utilizzano i client Outlook per leggere la posta ricevono le esperienze di lettura native, di prima classe per i messaggi crittografati e protetti da diritti, anche se non sono presenti nella stessa organizzazione del mittente. I client Outlook supportati includono Outlook desktop, Outlook Mac, Outlook Mobile su iOS e Android e Outlook sul Web (in precedenza noto come Outlook Web App).
  
I destinatari dei messaggi crittografati che ricevono la posta crittografata o protetta da diritti inviati ai propri account di Outlook.com, Gmail e Yahoo ricevono un messaggio di posta elettronica wrapper che li indirizza al portale OME, in cui è possibile eseguire facilmente l'autenticazione utilizzando un account Microsoft, Gmail o Credenziali Yahoo.
  
Gli utenti finali che leggono i messaggi crittografati o protetti da diritti nei client diversi da Outlook utilizzano anche il portale OME per visualizzare le informazioni crittografate e protette con i diritti ricevuti.

Inoltre, se il mittente della posta protetta è in GCC High e il destinatario è esterno a GCC High, compresi gli utenti di Office 365 commerciali, gli utenti di Outlook.com e gli utenti di altri provider di posta elettronica, ad esempio Gmail, il destinatario riceve un messaggio di posta elettronica wrapper che reindirizza a il portale OME in cui il destinatario è in grado di leggere e rispondere al messaggio. In caso contrario, se il mittente e il destinatario sono entrambi nell'ambiente GCC High, i destinatari che utilizzano i client di Outlook per leggere la posta elettronica ricevano le esperienze di lettura di prima classe per i messaggi crittografati e protetti da diritti, anche se non sono presenti nella stessa organizzazione. come mittente.
  
Sono stati aumentati i limiti di dimensione per i messaggi e gli allegati che è possibile crittografare tramite OME. Per ulteriori informazioni sui limiti, vedere [limiti di Exchange Online](https://technet.microsoft.com/en-us/library/exchange-online-limits.aspx).
  
## <a name="defining-rules-for-office-365-message-encryption"></a>Regole di definizione per la crittografia dei messaggi di Office 365

Un modo per abilitare le nuove funzionalità per la crittografia dei messaggi di Office 365 è per gli amministratori di Exchange Online e Exchange Online Protection per definire le regole del flusso di posta. Queste regole determinano in quali condizioni devono essere crittografati i messaggi di posta elettronica. Quando viene impostata un'azione di crittografia per una regola, tutti i messaggi che soddisfano le condizioni della regola vengono crittografati prima di essere inviati.
  
Le regole del flusso di posta sono flessibili, consentendo di combinare condizioni in modo da poter soddisfare requisiti di sicurezza specifici in una singola regola. Ad esempio, è possibile creare una regola per crittografare tutti i messaggi che contengono parole chiave specificate e che sono indirizzati a destinatari esterni. Le nuove funzionalità per la crittografia dei messaggi di Office 365 crittografano anche le risposte dai destinatari della posta elettronica crittografata.
  
Per ulteriori informazioni su come creare regole del flusso di posta per sfruttare le nuove funzionalità OME, vedere [definire le regole per la crittografia dei messaggi di Office 365](define-mail-flow-rules-to-encrypt-email.md).
  
## <a name="sending-viewing-and-replying-to-encrypted-email-messages"></a>Invio, risposta e visualizzazione di messaggi di posta elettronica crittografati

Con la crittografia dei messaggi di Office 365, gli utenti possono inviare messaggi di posta elettronica crittografati da Outlook e Outlook sul Web. Gli amministratori possono inoltre configurare le regole del flusso di posta in Office 365 per crittografare automaticamente le e-mail in base alle parole chiave corrispondenti o ad altre condizioni.
  
I destinatari dei messaggi crittografati che si trovano nelle organizzazioni di Office 365 saranno in grado di leggere tali messaggi senza problemi in qualsiasi versione di Outlook, tra cui Outlook per PC, Outlook per Mac, Outlook sul Web, Outlook per iOS e Outlook per Android. Gli utenti che ricevono messaggi crittografati in altri client di posta elettronica possono visualizzare i messaggi nel portale OME.
  
Per istruzioni dettagliate su come inviare e visualizzare i messaggi crittografati, vedere gli articoli seguenti:
  
- [Come aprire un messaggio protetto](https://support.office.com/article/1157a286-8ecc-4b1e-ac43-2a608fbf3098.aspx)

- [Inviare, visualizzare e rispondere a messaggi crittografati in Outlook](https://support.office.com/article/eaa43495-9bbb-4fca-922a-df90dee51980.aspx)

## <a name="get-started-with-the-new-ome-capabilities"></a>Iniziare a utilizzare le nuove funzionalità OME

Se si è pronti per iniziare a utilizzare le nuove funzionalità OME all'interno dell'organizzazione, vedere [configurare le nuove funzionalità di crittografia dei messaggi di Office 365](set-up-new-message-encryption-capabilities.md).
