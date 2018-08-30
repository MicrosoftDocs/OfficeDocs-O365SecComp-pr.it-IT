---
title: Funzionalità di protezione in Azure Information Protection distribuzione ai tenant di Office 365 esistente
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 6/29/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 7ad6f58e-65d7-4c82-8e65-0b773666634d
description: Per agevolare il primo passaggio per la protezione delle informazioni avvio di tutti i tenant idonei Azure Information Protection 2018 luglio verranno hanno le caratteristiche di protezione in Azure Information Protection attivata per impostazione predefinita. La funzionalità di protezione in Azure Information Protection erano in precedenza noti in Office 365 come Rights Management o RMS Azure. Se l'organizzazione dispone di un piano di servizio Office E3 o un piano di servizio superiore a questo punto si otterrà un punto di partenza la protezione delle informazioni tramite la protezione delle informazioni di Azure quando è possibile distribuire le funzionalità.
ms.openlocfilehash: be0200da3032dccbcf54e67f3bdfbac800b65526
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/27/2018
ms.locfileid: "22530530"
---
# <a name="protection-features-in-azure-information-protection-rolling-out-to-existing-office-365-tenants"></a>Funzionalità di protezione in Azure Information Protection distribuzione ai tenant di Office 365 esistente

Per agevolare il primo passaggio per la protezione delle informazioni avvio di tutti i tenant idonei Azure Information Protection 2018 luglio verranno hanno le caratteristiche di protezione in Azure Information Protection attivata per impostazione predefinita. La funzionalità di protezione in Azure Information Protection erano in precedenza noti in Office 365 come Rights Management o RMS Azure. Se l'organizzazione dispone di un piano di servizio Office E3 o un piano di servizio superiore a questo punto si otterrà un punto di partenza la protezione delle informazioni tramite la protezione delle informazioni di Azure quando è possibile distribuire le funzionalità.
  
## <a name="changes-beginning-july-1-2018"></a>Modifiche apportate a partire dal 1 ° luglio 2018

Avviare il 1 ° luglio 2018 Microsoft abilitare la funzionalità di protezione in Azure Information Protection per tutti i tenant di Office 365 che dispongono di uno dei seguenti piani di sottoscrizione:
  
- Office 365 Message Encryption è disponibile come parte di Office 365 E3 ed E5, E3 Microsoft ed E5, Office 365 A1, A3 e A5 e Office 365 G3 e G5. Non è necessario disporre di una licenza per ricevere le nuove funzionalità di protezione con tecnologia per la protezione delle informazioni di Azure. 
    
- È inoltre possibile aggiungere Azure Information Protection piano 1 agli elementi seguenti piani a ricevere le nuove funzionalità di Office 365 Message Encryption: Exchange Online piano 1, Exchange Online piano 2, Office 365 F1, Essentials Business di Office 365, Office 365 Business Premium o Office 365 Enterprise E1.
    
- Ogni utente beneficiano di Office 365 Message Encryption deve disporre della licenza per da coprire con la caratteristica.
    
- Per un elenco completo vedere le [descrizioni dei servizi di Exchange Online](https://technet.microsoft.com/library/exchange-online-service-description.aspx) per Office 365 Message Encryption. 
    
Gli amministratori tenant possono controllare lo stato di protezione nel portale di amministrazione di Office 365. 
  
![Schermata che mostra che viene attivato il rights management di Office 365.](media/303453c8-e4a5-4875-b49f-e80c3eb7b91e.png)
  
## <a name="why-are-we-making-this-change"></a>Perché fa di questa modifica.

Crittografia dei messaggi di Office 365 utilizza le funzionalità di protezione in Azure Information Protection. Il fulcro di recente miglioramenti apportati a Office 365 Message Encryption e nostri investimenti più ampi per la protezione delle informazioni in Microsoft 365 stiamo più semplice per organizzazioni di attivare e utilizzare la funzionalità di protezione, come in passato, la crittografia tecnologie sono stati difficili da impostare. Attivando la funzionalità di protezione in Azure Information Protection per impostazione predefinita, è possibile iniziare rapidamente a proteggere i dati riservati.
  
## <a name="does-this-impact-me"></a>Influisce tutto questo utente?

Se l'organizzazione Office 365 ha acquistato una licenza di Office 365 idoneo, tenant verrà affetta da questa modifica.
  
 **Importante!** Se si utilizza Active Directory Rights Management Services (AD RMS) nell'ambiente locale, è necessario escludere modifica immediatamente oppure eseguire la migrazione per la protezione delle informazioni di Azure prima che è possibile distribuire questa modifica entro 30 giorni. Per informazioni su come escludere, vedere "utilizzo AD RMS, come esplicito out?" più avanti in questo articolo. Se si preferisce per eseguire la migrazione, vedere [la migrazione da AD RMS per la protezione delle informazioni di Azure.](https://docs.microsoft.com/azure/information-protection/plan-design/migrate-from-ad-rms-to-azure-rms)
  
## <a name="can-i-use-azure-information-protection-with-active-directory-rights-management-services-ad-rms"></a>È possibile utilizzare la protezione delle informazioni di Azure con Active Directory Rights Management Services (AD RMS)?

No. Non si tratta di uno scenario di distribuzione supportati. Senza eseguire i passaggi aggiuntivi con consenso esplicito, in alcuni computer potrebbe avvia automaticamente tramite il servizio di Azure Rights Management e inoltre connettersi al cluster AD RMS. In questo scenario non è supportato e ottiene risultati affidabili, pertanto è importante disattivare questa modifica entro 30 giorni prima che è possibile distribuire queste nuove funzionalità. Per informazioni su come escludere, vedere "utilizzo AD RMS, come esplicito out?" più avanti in questo articolo. Se si preferisce per eseguire la migrazione, vedere [la migrazione da AD RMS per la protezione delle informazioni di Azure.](https://docs.microsoft.com/azure/information-protection/plan-design/migrate-from-ad-rms-to-azure-rms)
  
## <a name="how-do-i-know-if-im-using-ad-rms"></a>È possibile sapere se si sta utilizzando AD RMS?

Utilizzare in queste istruzioni da [preparare l'ambiente per Azure Rights Management quando si dispone inoltre di Active Directory Rights Management Services (AD RMS)](https://docs.microsoft.com/azure/information-protection/deploy-use/prepare-environment-adrms) per verificare se è stato distribuito AD RMS: 
  
1. Sebbene facoltativo, la maggior parte delle distribuzioni di AD RMS pubblicano il punto di connessione del servizio (SCP) in Active Directory in modo che i computer del dominio consente di individuare il cluster AD RMS. 
  
Utilizzare Modifica ADSI per verificare se si dispone di un SCP pubblicato in Active Directory: CN = Configuration [nome del server], CN = Services, CN = RightsManagementServices, CN = SCP
    
2. Se non si utilizza un SCP, è necessario configurare computer Windows che si connettono a un cluster AD RMS per l'individuazione dei servizi sul lato client o il reindirizzamento delle licenze mediante il Registro di sistema di Windows: HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\MSIPC\ServiceLocation o HKEY _ LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\MSIPC\ServiceLocation 
  
Per ulteriori informazioni su queste configurazioni del Registro di sistema, vedere [Abilitazione individuazione del servizio di sul lato client tramite il Registro di sistema di Windows](https://docs.microsoft.com/azure/information-protection/rms-client/client-deployment-notes#enabling-client-side-service-discovery-by-using-the-windows-registry) e [reindirizzamento licenze traffico del server](https://docs.microsoft.com/azure/information-protection/rms-client/client-deployment-notes#redirecting-licensing-server-traffic).
    
## <a name="i-use-ad-rms-how-do-i-opt-out"></a>Utilizzare AD RMS, come esplicito?

Per non consentire la modifica future, completare la procedura seguente:
  
1. Utilizzo di un ufficio o della scuola dell'account che disponga delle autorizzazioni di amministratore globale dell'organizzazione Office 365, avviare una sessione di Windows PowerShell e connettersi a Exchange Online. Per ulteriori informazioni, vedere [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell?view=exchange-ps).
    
2. Eseguire il cmdlet Set-IRMConfiguration utilizzando la sintassi seguente:
    
  ```
  Set-IRMConfiguration -AutomaticServiceUpdateEnabled $false 
  ```

## <a name="what-can-i-expect-after-this-change-has-been-made"></a>Che cos'è previsto una volta effettuata questa modifica?

Una volta che questa opzione è attivata, purché non incluso, iniziare a utilizzare la nuova versione di Office 365 Message Encryption ha annunciato [2017 Ignite per Microsoft](https://techcommunity.microsoft.com/t5/Security-Privacy-and-Compliance/Email-Encryption-and-Rights-Protection/ba-p/110801) che sfrutta le funzionalità di crittografia e protezione delle informazioni di Azure Protezione. 
  
![Schermata che mostra un OME protetti messaggio in Outlook sul web.](media/599ca9e7-c05a-429e-ae8d-359f1291a3d8.png)
  
Per ulteriori informazioni sui miglioramenti, vedere [Office 365 Message Encryption](ome.md).
  

