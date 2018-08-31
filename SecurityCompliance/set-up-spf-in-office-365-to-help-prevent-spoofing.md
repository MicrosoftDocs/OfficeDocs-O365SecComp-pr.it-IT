---
title: Configurazione di SPF in Office 365 per evitare lo spoofing
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 2/19/2018
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 71373291-83d2-466f-86ea-fc61493743a6
description: "Riepilogo: In questo articolo viene descritto come aggiornare un record DNS (Domain Name Service) affinché sia possibile utilizzare Sender Policy Framework (SPF) con il dominio personalizzato in Office 365. L'utilizzo di SPF consente di convalidare la posta elettronica in uscita inviata dal dominio personalizzato."
ms.openlocfilehash: 9c03f69cfd0c962214a3adc722690a4288940541
ms.sourcegitcommit: e9dca2d6a7838f98bb7eca127fdda2372cda402c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/21/2018
ms.locfileid: "23002885"
---
# <a name="set-up-spf-in-office-365-to-help-prevent-spoofing"></a>Configurazione di SPF in Office 365 per evitare lo spoofing

 **Riepilogo:** In questo articolo viene descritto come aggiornare un record DNS (Domain Name Service) affinché sia possibile utilizzare Sender Policy Framework (SPF) con il dominio personalizzato in Office 365. L'utilizzo di SPF consente di convalidare la posta elettronica in uscita inviata dal dominio personalizzato. 
  
Per utilizzare un dominio personalizzato, Office 365 richiede l'aggiunta di un record TXT Sender Policy Framework (SPF) al record DNS per prevenire spoofing. SPF identifica quali server di posta elettronica sono autorizzati a inviare posta elettronica per conto dell'utente. In sostanza, SPF, insieme a DKIM, DMARC e altre tecnologie supportate da Office 365 aiuta a prevenire spoofing e phishing. SPF viene aggiunto come un record TXT che viene utilizzato da DNS per identificare i server di posta elettronica che possono inviare posta elettronica per conto del dominio personalizzato. I sistemi di posta elettronica del destinatario fanno riferimento al record TXT SPF per stabilire se un messaggio di un dominio personalizzato proviene da un server di messaggistica autorizzato.
  
Ad esempio, si supponga che il dominio personalizzato contoso.com utilizzi Office 365. Si aggiunge un record TXT SPF che elenca i server di messaggistica di Office 365 come server di posta elettronica legittimi per il dominio. Quando il server di messaggistica ricevente riceve un messaggio da joe@contoso.com, il server cerca il record TXT SPF per contoso.com e scopre se il messaggio è valido. Se il server di destinazione rileva che il messaggio proviene da un server di messaggistica di Office 365 diverso da quelli elencati nel record SPF, il server di posta di destinazione può scegliere di rifiutare il messaggio come posta indesiderata.
  
Inoltre, se nel dominio personalizzato non è presente un record TXT SPF, alcuni server di destinazione possono rifiutare il messaggio immediatamente. Ciò avviene perché il server di destinazione non può convalidare che il messaggio provenga da un server di messaggistica autorizzato.
  
Se la posta di Office 365 è già stata sincronizzata, i server di messaggistica Microsoft sono già stati inclusi nel sistema DNS come record TXT SPF. Tuttavia, esistono alcuni casi in cui è necessario aggiornare il record TXT SPF nel sistema DNS. Ad esempio:
  
- In precedenza, era necessario aggiungere un record SPF o TXT diverso al dominio personalizzato se si utilizzava SharePoint Online. Ciò non è più necessario. Questa modifica dovrebbe ridurre il rischio che i messaggi di notifica di SharePoint Online finiscano nella cartella Posta indesiderata. Aggiornare il record SPF o TXT se si sta raggiungendo il limite di 10 ricerche e si stanno visualizzando errori del tipo "limite di ricerche superato" e "troppi hop".
    
- Se si dispone di un ambiente ibrido con Office 365 ed Exchange in locale.
    
- Si intende configurare DKIM e DMARC (scelta consigliata).
    
## <a name="updating-your-spf-txt-record-for-office-365"></a>Aggiornamento del record TXT SPF per Office 365
<a name="sectionSection0"> </a>

Prima di aggiornare il record TXT nel sistema DNS, è necessario raccogliere alcune informazioni e determinare il formato del record. In questo modo si impedirà la generazione di errori DNS. Per esempi avanzati e una descrizione dettagliata della sintassi SPF supportata, vedere [Funzionamento di SPF per prevenire spoofing e phishing in Office 365](how-office-365-uses-spf-to-prevent-spoofing.md#HowSPFWorks).
  
Raccogliere le seguenti informazioni:
  
- Il record TXT SPF per il proprio dominio personalizzato. Per istruzioni, vedere [Raccogliere le informazioni necessarie per creare record DNS di Office 365](https://support.office.microsoft.com/en-us/article/Gather-the-information-you-need-to-create-Office-365-DNS-records-77f90d4a-dc7f-4f09-8972-c1b03ea85a67).
    
- Indirizzi IP di tutti i server di messaggistica locali. Ad esempio, **192.168.0.1**.
    
- Nomi di dominio da utilizzare per tutti i domini di terze parti che è necessario includere nel record TXT SPF. In alcuni provider di posta inviata in massa sono impostati sottodomini da utilizzare per i clienti. Ad esempio, la società MailChimp ha configurato **servers.mcsv.net**.
    
- Determinare quale regola di imposizione utilizzare per il record TXT SPF. Microsoft consiglia **-tutti**. Per informazioni dettagliate sulle altre opzioni di sintassi, vedere [Sintassi del record TXT SPF per Office 365](how-office-365-uses-spf-to-prevent-spoofing.md#SPFSyntaxO365).
    
### <a name="to-add-or-update-your-spf-txt-record"></a>Per aggiungere o aggiornare il record TXT SPF

1. Se non è già stato fatto, costituire il record TXT SPF utilizzando la sintassi della tabella seguente:
    
||**Se si sta utilizzando...**|**Comune per i clienti di Office 365?**|**Aggiungere...**|
|:-----|:-----|:-----|:-----|
|1  <br/> |Qualsiasi sistema di posta elettronica (obbligatorio)  <br/> |Comune. Tutti i record TXT SPF devono iniziare con questo valore  <br/> |v=spf1  <br/> |
|2  <br/> |Exchange Online  <br/> |Comune  <br/> |include:SPF.Protection.Outlook.com  <br/> |
|3  <br/> |Solo per Exchange Online  <br/> |Non comune  <br/> |IP4:23.103.224.0/19 ip4:206.191.224.0/19 ip4:40.103.0.0/16 include:spf.protection.outlook.com  <br/> |
|4  <br/> |Office 365 Germania, solo Microsoft Cloud Germania  <br/> |Non comune  <br/> |include:SPF.Protection.Outlook.de  <br/> |
|5  <br/> |Un sistema di posta elettronica di terze parti  <br/> |Non comune  <br/> |includere: \<nome dominio\>  <br/> Dove il nome di dominio è il nome di dominio del sistema di posta elettronica di terze parti.  <br/> |
|6  <br/> |Sistema di posta locale. Ad esempio, di Exchange Online Protection insieme a un altro sistema di posta elettronica  <br/> |Non comune  <br/> | Utilizzarne uno per ogni sistema di posta elettronica aggiuntivo:  <br/>  ip4: \<  _IP address_\>  <br/>  ip6: \<  _IP address_\>  <br/>  includere: \<  _domain name_\>  <br/>  Dove il valore per \<  _IP address_\> è l'indirizzo IP del sistema di posta elettronica e \< _domain name_\> è il nome di dominio dell'altro sistema di posta elettronica che invia un messaggio per conto del dominio.  <br/> |
|7  <br/> |Qualsiasi sistema di posta elettronica (obbligatorio)  <br/> |Comune. Tutti i record TXT SPF finiscono con questo valore  <br/> |\< _enforcement rule_\>  <br/> Può trattarsi di uno dei vari valori. Si consiglia di utilizzare **-tutti**.  <br/> |
   
1.1, ad esempio, se si è completamente ospitato in Office 365, vale a dire non sono alcun server di posta locale, il TXT SPF record deve includere le righe 1, 2 e 7 e potrebbe essere simile al seguente:
    
  ```
   v=spf1 include:spf.protection.outlook.com -all
  ```

1.2 questo è il record di Office 365 SPF TXT più comune. Questo record può essere utilizzato per praticamente a chiunque, indipendentemente dal fatto che i datacenter di Office 365 si trova negli Stati Uniti o Europa (inclusi Germania) oppure un'altra posizione.
    
1.3, tuttavia, se è stato acquistato Office 365 Germania, parte di Microsoft Cloud Germania, è consigliabile utilizzare l'istruzione Includi dalla riga 4 anziché nella riga 2. Ad esempio, se si è completamente ospitato in Office 365 Germania, vale a dire non sono alcun server di posta locale, il TXT SPF record deve includere le righe 1, 4 e 7 e potrebbe essere simile al seguente:
    
  ```
   v=spf1 include:spf.protection.outlook.de -all
  ```

1.4 già stato distribuito in Office 365 e sono state impostate i record SPF TXT per il dominio personalizzato, se esegue la migrazione a Office 365 Germania, è necessario aggiornare il record SPF TXT. A tale scopo, modificare **include:spf.protection.outlook.com** **include.spf.protection.outlook.de**.
    
2. Dopo aver creato il record TXT SPF, è necessario aggiornare il record in DNS. È possibile avere un solo record TXT SPF per un dominio Se esiste un record TXT SPF, anziché aggiungere un nuovo record, è necessario aggiornare quello esistente. Andare a [Creare record DNS per Office 365 quando si gestiscono i record DNS](https://support.office.microsoft.com/article/b0f3fdca-8a80-4e8e-9ef3-61e8a2a9ab23), quindi fare clic sul collegamento dell'host DNS. Se l'host DNS non dispone di un collegamento nella pagina, è possibile [seguire le istruzioni generali](https://support.office.microsoft.com/article/7b7b075d-79f9-4e37-8a9e-fb60c1d95166) per aggiungere i record o contattare l'host DNS per assistenza. 
    
3. Testare il record SPF TXT.
    
## <a name="more-information-about-spf"></a>Per ulteriori informazioni su SPF
<a name="sectionSection1"> </a>

Per esempi avanzati e una descrizione dettagliata della sintassi SPF supportata, dello spoofing, della risoluzione dei problemi e di come Office 365 supporta SPF, vedere [Funzionamento di SPF per prevenire spoofing e phishing in Office 365](how-office-365-uses-spf-to-prevent-spoofing.md#HowSPFWorks).
  
## <a name="next-steps-after-you-set-up-spf-for-office-365"></a>Passaggi successivi: Dopo aver configurato SPF per Office 365
<a name="sectionSection2"> </a>

Problemi con il record TXT SPF Leggere [Risoluzione dei problemi: procedure consigliate per SPF in Office 365](how-office-365-uses-spf-to-prevent-spoofing.md#SPFTroubleshoot).
  
 SPF è progettata per prevenire spoofing, ma esistono tecniche spoofing che SPF non è in grado di evitare. Per proteggersi da queste tecniche, dopo aver configurato SPF, è necessario configurare anche DKIM e DMARC per Office 365. Per iniziare, vedere [Utilizzare DKIM per convalidare la posta elettronica in uscita inviata dal dominio personalizzato in Office 365](use-dkim-to-validate-outbound-email.md). Successivamente, vedere [Utilizzare DMARC per convalidare la posta elettronica in Office 365](use-dmarc-to-validate-email.md).
  

