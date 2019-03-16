---
title: Prepararsi per la sicurezza e la conformità di Microsoft 365
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 03/14/2019
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.collection:
- M365-security-compliance
localization_priority: Normal
description: Prepararsi per il Centro sicurezza e conformità di Microsoft 365
ms.openlocfilehash: cdea0aabec39082ce9da0001cb148fe14454e5b7
ms.sourcegitcommit: 8657e003ab1ff49113f222d1ee8400eff174cb54
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/16/2019
ms.locfileid: "30639053"
---
# <a name="get-ready-for-the-new-microsoft-365-security-center-and-microsoft-365-compliance-center"></a>Preparare l'ambiente per i nuovi Centro sicurezza Microsoft 365 e Centro conformità Microsoft 365

**Siamo lieti di annunciare il nuovissimo [Microsoft 365 Security Center](#microsoft-365-security-center) e [Microsoft 365 Compliance Center](#microsoft-365-compliance-center), a partire dalla fine di gennaio 2019 e fino al marzo 2019**. Leggere questo articolo per ottenere una panoramica di cosa succede, [cosa aspettarsi](#what-to-expect)e licenze necessarie [e autorizzazioni necessarie](#required-licenses-and-permissions).

## <a name="microsoft-365-security-center"></a>Centro sicurezza Microsoft 365

Il nuovo Centro sicurezza di Microsoft 365 include un dashboard che consente di gestire e monitorare la sicurezza in tutte le identità, i dati, i dispositivi, le app e l'infrastruttura. È inoltre possibile accedere facilmente al nuovo punteggio di Microsoft Secure, ai nuovi report sulle minacce dei dispositivi, ai nuovi rapporti sulle minacce di identità e ai report di sicurezza delle app cloud. 

![Nuovo Centro sicurezza di Microsoft 365](media/m365-security-center.png)

Quando si utilizza Microsoft 365 Security Center per la prima volta, vengono visualizzate le informazioni sulla parte superiore dello schermo per iniziare. Vedrai anche come esplorare facilmente le funzionalità di sicurezza che più ti interessano.

Dopo che il Centro sicurezza di Microsoft 365 è stato abilitato per il tenant, sarà possibile accedervi [https://security.microsoft.com](https://security.microsoft.com). 

> [!NOTE]
> Per accedere al centro sicurezza Microsoft 365 è necessario che sia assegnato un ruolo di Azure Active Directory valido. Per ulteriori informazioni, vedere la sezione relativa alle [licenze e alle autorizzazioni necessarie](#required-licenses-and-permissions) (in questo articolo).

## <a name="microsoft-365-compliance-center"></a>Centro conformità Microsoft 365

Il nuovo centro conformità di Microsoft 365 fornisce visibilità in Microsoft Compliance Manager, che rispecchia la posizione di conformità globale e fornisce le azioni consigliate per configurare le impostazioni in modo da soddisfare gli obblighi di conformità complessi. È possibile accedere facilmente alle etichette e ai criteri per la conservazione e la sensibilità, la prevenzione della perdita di dati (DLP), la governance dei dati, eDiscovery, le richieste del soggetto dei dati (richieste DSR), la gestione delle case e la sicurezza delle app cloud. Inoltre, è possibile ottenere Insight e sfruttare l'automazione intelligente per ridurre i rischi di conformità e salvaguardare la propria azienda digitale. 

![Centro conformità Microsoft 365](media/m365-compliance-center.png)

Quando si utilizza Microsoft 365 Compliance Center per la prima volta, vengono visualizzate le informazioni sulla parte superiore dello schermo per facilitare l'avvio. Vedrai come esplorare facilmente le funzionalità di conformità che più ti interessano.

Dopo aver abilitato il centro conformità Microsoft 365 per il tenant, sarà necessario accedervi [https://compliance.microsoft.com](https://compliance.microsoft.com).  

> [!NOTE]
> È necessario essere assegnati a un ruolo di Azure Active Directory valido per accedere al centro conformità Microsoft 365. Per ulteriori informazioni, vedere la sezione relativa alle [licenze e alle autorizzazioni necessarie](#required-licenses-and-permissions) (in questo articolo).

## <a name="what-to-expect"></a>Cosa aspettarsi

### <a name="coming-soon"></a>Disponibile prossimamente

Il nuovo Centro sicurezza di Microsoft 365 e il nuovo centro conformità di Microsoft 365 sono disponibili a partire da fine gennaio e fino a marzo 2019. All'interno di questo intervallo di tempo, dovrebbe essere possibile accedere al nuovo Centro sicurezza Microsoft 365 e al centro conformità Microsoft 365.

### <a name="easy-access"></a>Facile accesso!

Con una navigazione migliorata, soluzioni integrate e un'esperienza semplificata, è possibile visualizzare e accedere alle informazioni più interessate e sfruttare le potenti soluzioni di sicurezza e conformità in Microsoft 365.

### <a name="smooth-transition"></a>Transizione agevole!

È possibile prevedere una transizione graduale ai nuovi centri. Dopo che questa modifica è stata completata, si prevede di ritirare l'ex Centro protezione & Compliance Microsoft[https://protection.microsoft.com](https://protection.microsoft.com)365 (). L'esperienza dell'amministratore cambierà, ma ciò non influisce sulle configurazioni di conformità e sicurezza correnti.

Dopo l'esecuzione di questo aggiornamento, se l'organizzazione dispone di Microsoft 365 Enterprise E3 o E5, gli amministratori della sicurezza e della conformità possono:

- Passare direttamente a [https://security.microsoft.com](https://security.microsoft.com) e [https://compliance.microsoft.com](https://compliance.microsoft.com); <br>oppure  
- Passare all'interfaccia di amministrazione di Microsoft 365, quindi passare al nuovo Centro sicurezza Microsoft 365 e al centro conformità di Microsoft 365 (i collegamenti sono sotto interfaccia di amministrazione nel riquadro di spostamento a sinistra).

> [!TIP]
> Se si utilizza il Centro sicurezza & Compliance di Office 365[https://protection.office.com](http://protection.office.com)(), sarà comunque possibile configurare e gestire le impostazioni di Office 365 all'interno del centro di conformità _AMP_ di Office 365 di sicurezza esistente. Le configurazioni verranno mantenute nel centro conformità di Office 365 Security &, nonché nel nuovo Centro sicurezza Microsoft 365 e nel centro conformità Microsoft 365.  

## <a name="required-licenses-and-permissions"></a>Licenze e autorizzazioni necessarie

### <a name="licenses"></a>Licenze

Per ottenere il nuovo Centro sicurezza Microsoft 365 e il centro conformità Microsoft 365, è necessario che l'organizzazione disponga di una sottoscrizione a Microsoft 365 E3 o E5 oppure di un equivalente per contratti multiLicenza (costituito da Office 365 Enterprise E3 o E5, Enterprise Mobility + Security E3 o E5 e Windows 10 Enterprise E3/E5). Per ulteriori informazioni su questi piani, vedere [Discover the Microsoft 365 Enterprise Solution that ' s right for you](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans).

### <a name="roles-and-permissions"></a>Ruoli e autorizzazioni

Agli utenti deve essere assegnato l'amministratore globale, l'amministratore della conformità, l'amministratore della sicurezza o il ruolo di lettore di sicurezza in Azure Active Directory per accedere al nuovo Centro sicurezza Microsoft 365 o al centro conformità Microsoft 365.

- Gli amministratori globali possono accedere sia al centro sicurezza che al centro conformità

- Gli amministratori della conformità possono accedere al centro conformità

- Gli amministratori della sicurezza o i lettori di sicurezza possono accedere al centro sicurezza

> [!NOTE]
> Ulteriori ruoli, tra cui operatore di sicurezza e amministratore dei dati di conformità, saranno disponibili a breve.

Nella tabella seguente sono riepilogati gli utenti che possono accedere a vari portali in Azure, Office 365 e Windows:

|Portale  |Global<br/>Amministratore  |Sicurezza <br/>Amministratore<br>oppure<br>Sicurezza<br>Lettura |Conformità<br/>Amministratore  |
|---------|---------|---------|---------|
|[Centro sicurezza e conformità di Office 365](https://protection.office.com) |Sì |Sì  |Sì |
|[Centro sicurezza Microsoft 365](https://security.microsoft.com) |Sì  | Sì  | No        |
|[Centro conformità Microsoft 365](https://compliance.microsoft.com) | Sì | No | Sì |
|[Compliance Manager](https://aka.ms/compliancemanager) |Sì | Sì |Sì  |
|[Azure Information Protection](https://docs.microsoft.com/azure/information-protection) |Sì |Sì |No |
|[Centro sicurezza di Azure](https://docs.microsoft.com/azure/security-center/)  |Sì |Sì |No |
|[Protezione avanzata dalle minacce di Azure](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp)  |Sì |Sì |No |
|[Windows Defender ATP](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-atp/windows-defender-advanced-threat-protection?ocid=tia-260153000#windows-defender-atp) |Sì |Sì |No |
|[Protezione delle identità](https://docs.microsoft.com/azure/active-directory/identity-protection)     |Sì |Sì |No |
|[Gestione delle identità con privilegi](https://docs.microsoft.com/azure/active-directory/privileged-identity-management)     |Sì |Sì |No |
|[Intune](https://docs.microsoft.com/intune)     |Sì |Sì |Sì |
|[Cloud App Security](https://docs.microsoft.com/cloud-app-security/)     |Sì |Sì |Sì |
|[Secure Score](https://docs.microsoft.com/office365/securitycompliance/office-365-secure-score)     |Sì |Sì |No |
|[Exchange](https://docs.microsoft.com/exchange/)     |Sì |Sì |Sì |

## <a name="additional-resources"></a>Altre risorse

[Roadmap di Microsoft 365](https://www.microsoft.com/microsoft-365/roadmap)

