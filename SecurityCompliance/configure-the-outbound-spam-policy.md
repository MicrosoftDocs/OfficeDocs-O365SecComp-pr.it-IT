---
title: Configurare le notifiche sui criteri di posta indesiderata in uscita in Office 365
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 11/10/2016
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: a44764e9-a5d2-4c67-8888-e7fb871c17c7
ms.collection:
- M365-security-compliance
description: Gli amministratori possono ottenere informazioni su come modificare le impostazioni di notifica per i rilevamenti di posta indesiderata in uscita in Office 365.
ms.openlocfilehash: c48b6cd634417a00040fb5479313782b44f6aa8d
ms.sourcegitcommit: 81b3bff27bc60235a38004c5b0297ac454331b25
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/10/2019
ms.locfileid: "36822516"
---
# <a name="configure-outbound-spam-policy-notifications-in-office-365"></a>Configurare le notifiche sui criteri di posta indesiderata in uscita in Office 365

Il filtro di protezione da posta indesiderata in uscita è sempre abilitato se si utilizza il servizio per l'invio di messaggi di posta elettronica in uscita, proteggendo così l'organizzazione utilizzando il servizio e i destinatari previsti. Come il filtro della posta in arrivo, quello per la posta indesiderata in uscita è composto da un filtro connessioni e un filtro contenuto, ma diversamente dal primo le sue impostazioni non sono configurabili. Se si determina che un messaggio in uscita è posta indesiderata, tale messaggio viene instradato attraverso il pool di recapito ad alto rischio in modo da ridurre la probabilità che il normale pool IP in uscita venga aggiunto all'elenco di indirizzi bloccati. Se un utente continua a inviare posta indesiderata in uscita tramite il servizio, non potrà più inviare messaggi.

Sebbene non sia possibile disabilitare o modificare il filtro posta indesiderata in uscita, è possibile configurare le seguenti impostazioni di notifica di posta indesiderata in uscita:

- **Inviare copie dei messaggi sospetti**: i messaggi vengono contrassegnati come posta indesiderata (indipendentemente dal livello di protezione SCL) e non vengono rifiutati dal filtro, ma vengono instradati attraverso il pool di recapito ad alto rischio. È possibile utilizzare l'interfaccia di amministrazione di Exchange (EAC) o i ** \*cmdlet-HostedOutboundSpamFilterPolicy** in PowerShell di Exchange Online o Exchange Online Protection PowerShell per specificare i destinatari di addizione per questi messaggi rilevati. Si noti che i destinatari vengono aggiunti come destinatari **Ccn** (i campi **da** e **a** sono il mittente e il destinatario originali).

- **Inviare notifiche quando un mittente è bloccato**: quando una quantità significativa di posta indesiderata viene inviata da un determinato utente, l'utente è disabilitato dall'invio di messaggi di posta elettronica. Gli amministratori sono informati per impostazione predefinita, ma è possibile utilizzare l'utente con restrizioni per l'invio dei [criteri di avviso](alert-policies.md) **tramite posta elettronica** nel centro sicurezza & conformità di Office 365 per configurare i destinatari di notifica aggiuntivi.

  Per vedere come è fatta la notifica, vedere [Notifica di esempio quando a un mittente viene impedito di inviare posta indesiderata in uscita.](sample-notification-when-a-sender-is-blocked-sending-outbound-spam.md). Per informazioni su come ottenere riattivati, vedere [rimozione di un utente, dominio o indirizzo IP da un elenco di blocco dopo l'invio di posta indesiderata](http://technet.microsoft.com/library/712cfcc1-31e8-4e51-8561-b64258a8f1e5.aspx).

## <a name="what-do-you-need-to-know-before-you-begin"></a>Che cosa è necessario sapere prima di iniziare

- Tempo stimato per il completamento: 5 minuti

- Per aprire il Centro sicurezza e conformità, vedere [Accedere al Centro sicurezza e conformità di Office 365](go-to-the-securitycompliance-center.md).

- Per aprire EAC, vedere interfaccia di amministrazione di Exchange [in Exchange Online](https://docs.microsoft.com/Exchange/exchange-admin-center) o interfaccia [di amministrazione di Exchange in Exchange Online Protection](exchange-admin-center-in-exchange-online-protection-eop.md).

- Per aprire Exchange Online PowerShell, vedere [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell). Per aprire Exchange Online Protection PowerShell, vedere [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/exchange-online-protection-powershell).

- Per poter eseguire questa procedura, è necessario che l'account disponga delle autorizzazioni assegnate. Per sapere quali autorizzazioni sono necessarie, vedere "gestire gli avvisi" in [autorizzazioni nel centro sicurezza & conformità di Office 365](permissions-in-the-security-and-compliance-center.md).

## <a name="use-the-eac-to-configure-additional-recipients-for-outbound-spam-messages"></a>Configurazione di ulteriori destinatari per i messaggi di posta indesiderata in uscita tramite EAC

1. Nell'interfaccia di amministrazione di Exchange, andare a **protezione** \> **posta indesiderata in uscita**.

2. Selezionare il criterio denominato **default**, quindi fare clic su **modifica** ![icona](media/ITPro-EAC-EditIcon.png)modifica.

3. Nella pagina delle proprietà che si apre, verificare che sia selezionata la scheda **Preferenze di posta indesiderata in uscita** e quindi configurare l'impostazione seguente:

   **Inviare una copia di tutti i messaggi di posta elettronica in uscita sospetti all'indirizzo o agli indirizzi di posta elettronica seguenti**: selezionare la casella di controllo e immettere gli indirizzi di posta elettronica di uno o più amministratori che devono essere aggiunti al campo **Ccn** dei messaggi rilevati. Separare più indirizzi di posta elettronica con un punto e virgola (;).

   Al termine, scegliere **Salva**.

### <a name="use-exchange-online-powershell-or-exchange-online-protection-powershell-to-configure-additional-recipients-for-outbound-spam-messages"></a>Utilizzare PowerShell di Exchange Online o Exchange Online Protection PowerShell per configurare i destinatari aggiuntivi per i messaggi di posta indesiderata in uscita

Per abilitare e configurare altri destinatari per i messaggi di posta indesiderata in uscita, utilizzare la sintassi seguente:

```PowerShell
Set-HostedOutboundSpamFilterPolicy -Identity Default -BccSuspiciousOutboundMail $true -BccSuspiciousOutboundAdditionalRecipients <recipients>
```

- Per specificare i destinatari che sovrascrivono tutti i valori esistenti, `emailaddress1,emailaddress2,...emailaddressN`utilizzare la sintassi.

- Per aggiungere o rimuovere selettivamente i destinatari senza influire sulle altre voci, utilizzare la `@{Add="\<emailaddress1\>","\<emailaddress2\>"...; Remove="\<emailaddress1\>","\<emailaddress2\>"...}`sintassi.

In questo esempio vengono abilitati e configurati chris@contoso.com, laura@contoso.com e julia@contoso.com come destinatari Ccn per i messaggi di posta indesiderata in uscita.

```PowerShell
Set-HostedOutboundSpamFilterPolicy -Identity Default -BccSuspiciousOutboundMail $true -BccSuspiciousOutboundAdditionalRecipients chris@contoso.com,laura@contoso.com,julia@contoso.com
```

In questo esempio viene aggiunto michelle@contoso.com come destinatario Ccn aggiuntivo.

```PowerShell
Set-HostedOutboundSpamFilterPolicy -Identity Default -BccSuspiciousOutboundAdditionalRecipients @{Add=michelle@contoso.com}
```

Questo esempio consente di rimuovere chris@contoso.com e julia@contoso.com dall'elenco dei destinatari Ccn.

```PowerShell
Set-HostedOutboundSpamFilterPolicy -Identity Default -BccSuspiciousOutboundAdditionalRecipients @{Remove='chris@contoso.com','julia@contoso.com'}
```

Per informazioni dettagliate sulla sintassi e sui parametri, vedere [set-HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-hostedoutboundspamfilterpolicy).

**Nota**: eseguire il comando `Get-HostedOutboundSpamFilterPolicy | Format-List` per visualizzare i valori correnti delle proprietà *BccSuspiciousOutboundMail* e *BccSuspiciousOutboundAdditionalRecipients* .

## <a name="use-the-security--compliance-center-to-configure-notifications-when-a-sender-is-blocked"></a>Utilizzare il Centro sicurezza & Compliance per configurare le notifiche quando un mittente è bloccato

1. Nel centro sicurezza & conformità, accedere a **criteri di avviso** **avvisi** \> .

2. Individuare e selezionare il criterio denominato **utente con restrizioni dall'invio di posta elettronica**.

3. All'apertura del volo, fare clic su **modifica criterio**.

4. Nella pagina **modifica destinatari** visualizzata, configurare le impostazioni seguenti:

   - **Invia notifiche tramite posta elettronica**: **verificare che sia** selezionata l'opzione.

   - **Destinatari della posta elettronica**: per impostazione predefinita, **TenantAdmins** è l'unico valore qui. Per aggiungere altri destinatari, fare clic in un punto vuoto in questa casella, iniziare a digitare il destinatario e selezionare il destinatario quando il nome viene risolto. Per rimuovere i destinatari, fare clic sulla **X** accanto ai rispettivi nomi.

   - **Limite di notifica giornaliero**: il valore predefinito è **Nessun limite**, ma è possibile configurare diversi limiti da 1 a 200.

   Al termine, scegliere **Salva**.

## <a name="for-more-information"></a>Ulteriori informazioni

[Pool di recapito ad alto rischio per i messaggi in uscita](high-risk-delivery-pool-for-outbound-messages.md)

[Domande frequenti sulla protezione da posta indesiderata](anti-spam-protection-faq.md)
